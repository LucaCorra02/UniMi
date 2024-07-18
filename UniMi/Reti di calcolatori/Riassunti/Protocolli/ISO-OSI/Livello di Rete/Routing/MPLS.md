<span style=color:cyan>Obbiettivo</span> = <b><u>La tabella di routing viene riempita in modo asincrono rispetto alle funzionalità del forwording dal router</u></b>. <b><u>La divisione tra dati e controllo rende la funzione di instradamento indipendente dalla singola macchina</u></b>.

<b><u>Ci interessa rendere efficiente l'operativa dei router interni all'area zero di un Autonomus system</u></b>,in quanto qui passa tutto il traffico di tutte le varie aree di un AS e il traffico di internet in ingresso e in uscita dall'AS.

<span style=color:cyan>Soluzione= </span> <b><u>Dato che la funzione di forwarder richiede di operare sull'header IP, in particolare sul Source e Destination Address</u></b>, con <span style=color:yellow>MPLS Multi Packet Label Switching</span> andiamo a <b><u>ridurre la dimensione dei tag sui quali dobbiamo lavorare (indirizzi ip da 32 o 128 bit), riducendo così la dimensione delle tabelle</u></b>. 

<b><u>Non utilizzo più IP, ma effettuo un label switching usando un etichetta</u></b>
l'header di Ip con il suo payload continuano a viaggiare ma in un <span style=color:yellow>tunnel in un pacchetto di MPLS</span>. 
<b><u>Vado ad etichettare tutto il traffico in entrata nell'area zero aggiungendo un header, esso viaggerà secondo la policy di MPLS</u></b>. 

MPLS non ha funzionalità di routing particolari, ma è solo funzionale ad aumentare la velocità nello switching, <b><u>Trasformo il router in un apparato che fa forwarding SENZA curarsi del routing</u></b>

<h5 style=color:cyan>Funzionamento</h5>
<b><u>Il router di gateway dell'area0 si chiamano</u></b> <span style=color:yellow>Area Border Router</span> = <b><u>qui si compie la trasformazione da LS a MPLS</u></b>. Viene costruito un <span style=color:yellow>Header MPLS</span>, nel quale il pacchetto viene incapsulato : 

<span style=color:yellow>L'header MPLS</span> è formato da 32 bit : 
- `Label 20 bit` 
- `TTL 8 bit` 
- `S 1 bit` 
- `Class of service 3 bit` = equivalente del type of service. In questo caso class <b><u>in quanto voglio costruire flussi di traffico omogenei tra una sorgente e una destinazione</u></b>. L'omogeneità è data dalla classe di servizio a cui appartengono i pacchetti. 

Il Router al suo interno ha una tabella chiamata <span style=color:yellow>label switching table</span>, contenente le seguenti entrate : 
- `Output Port` 
- `Label` 
 - `Quality of Service` = <b><u>Posso etichettare con la stessa etichetta un flusso di pacchetti</u></b> (non solo il singolo pacchetto) con la stessa origine e destinazione. Tutta via <b><u>i pacchetti contenuti nel flusso devono essere omogenei dal punto di vista della qualità che il sevizio deve avere</u></b>.


 <b><u>La validità dell'etichetta è locale al router</u></b>, <b><u>ogni singolo router gestisce la propria numerazione ed ha validità locale</u></b>. Dobbiamo solamente costruire le label switching table correttamente.  
  <span style=color:green>I nostri router diventano velocissimi, in quanto effettuano solamente una operazione di switching</span> (non devono fare la maschera, ecc..). 

 <b><u>L'unico router che osserva l'header IP è l'ultimo router che funge da gateway</u></b> con la rete di destinazione, esso rimuoverà la <span style=color:yellow>label switching table</span>. 

 Il <span style=color:yellow>designeted router</span>, <b><u>si occupa di calcolare i cammini minimi e propagare all'interno dell'area 0 le tabelle di switching</u></b>. 
 Viene utilizzato un approccio CR `Constraint Routed` LSP in modo che ci sia un Network Management che riempie le tabelle utilizzate per fare label switching
[[Router MPLS]]

*Esempio* : 

![[Pasted image 20240718161117.png]]

 - Abbiamo un Pacchetto prodotto da un area 1 destinato per un host situata nell'area 2. 
 -   Nell'esempio, <b><u>ogni volta che arriva sulla porta di i/0 1 un pacchetto con etichetta 1, esso verrà mandato sulla porta di i/0 2, con etichetta 27</u></b>.  Il pacchetto viene switchato senza pensarci in base all'etichetta. 

