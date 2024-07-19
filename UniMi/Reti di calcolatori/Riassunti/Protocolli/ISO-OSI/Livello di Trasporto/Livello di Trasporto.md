Le funzioni principiali del livello 4 sono : 
-  <span style=color:yellow>Affidabilità</span>
- <span style=color:yellow>Indirizzamento</span> = deve essere risolto ad ogni livello. 
  Si tratta di un indirizzamento diverso da quello di livello 3 <b><u>(indirizziamo host finale, apparato di rete)</u></b>.

<b><u>TCP può servire più processi di livello 7 contemporaneamente</u></b>. Come fa TCP a discriminare in ricezione/invio quale processo indicare come destinatario/sorgente di un segmento.

Viene introdotto il concerto di <span style=color:yellow>Porta</span> = <b><u>il sistema operativo genera un identificatore univoco che associa la sessione del client (processo del client) sul tcp</u></b>.
<b><u>La primitiva che permette questa associazione prende il nome</u></b> di <span style=color:yellow>socket</span>, una volta chiamata ritorna una port descriptor. La <span style=color:yellow>port descriptor</span> <b><u>ha solamente validità internamente alla macchina nella quale viene fatta la richiesta</u></b>. 

<b><u>Un associazione di livello 4 è univocamente identificata da</u></b>:
- <span style=color:cyan>Porta Destinazione</span> = Informazione di Livello 4

- <span style=color:cyan>Porta Sorgente</span> = I primi due indirizzi legano il processo di livello 7 al TCP.

- <span style=color:cyan>Ip Destinazione</span> = informazione di livello 3. Per entrare in possesso di questa informazione dobbiamo utilizzare il <span style=color:yellow>Porta DNS Domain Name Server</span> = <b><u>protocollo che su richiesta esplicita, dato un nome logico, lo risolve e restituisce il corrispondente indirizzo ip</u></b>. 

- <span style=color:cyan>Ip Sorgente</span> = <b><u>In quanto le porte hanno solo validità locale e non a livello di rete internet</u></b>. Locale

 - <span style=color:cyan>Protocol Selector</span> = Consente di smistare le ricezioni verso l'entità di livello 4 corretta. 

Supponiamo di avere un Server Web (Porta 80), supponiamo di avere un associazione TCP, quanti client possono essere gestiti ? 
- <b><u>Potremo avere K clienti che stanno cercando di parlare con il server</u></b>. Tutti i client indicano lo stesso Ip e porta destinazione. 

- Il web server per gestire tutti e k i client contemporaneamente usano la <span style=color:yellow>fork</span>, <b><u>creano tante istanze del servizio server, ognuna delle quali è dedicata ad uno specifico client</u></b>. 

<span style=color:red>Problema</span> = Le varie <b><u>istanze figlie generate con la fork non possono essere associate tutte alla porta 80 del TCP</u></b>, altrimenti perdo l'univocità. Ogni figlio avrà associata la sua porta dinamica generata. 

<span style=color:green>Soluzione</span> = Vado a <span style=color:yellow>creare una tabella di Mapping</span> situata internamente nella macchina destinazione = <b><u>Per una specifica porta (ad esempio 80), contiene le associazioni X (id porta figlio ) e Y (client, ip e porta sorgente)</u></b>. 

<b><u>I segmenti entrati nel TCP indicheranno sempre la porta 80, tutta via in base alla sorgente il traffico sarà smistato sulla porta del figlio dedicato a quel client</u></b>.

A questo livello troviamo principalmente i seguenti protocolli: 
- [[TCP]] Transmission Control Protocol: <u><b>eroga un servizio affidabile</u></b>
- [[UDP]] User Datagram Protocol: <b><u>eroga un servizio best-efford</u></b>
- [[QUIC]]