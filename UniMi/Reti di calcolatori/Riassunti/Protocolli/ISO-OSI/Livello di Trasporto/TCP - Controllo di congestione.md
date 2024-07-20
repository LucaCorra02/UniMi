<span style=color:red>Problema</span> = <b><u>Siamo in mancanza di un informazione importante in TCP, ovvero lo stato della rete</u></b>
Anche se il buffer di ricezione è vuoto e pronto a ricevere tutto il traffico potrebbe accadere che la rete sia `congestionata`, code dei router piene, causando <b><u>packet dropping</u></b>.

TCP rileva la congestione come un errore di trasmissione
- `thougthput`: utilizzo del canale nel tempo
- `goodput`: thougthput - utilizzo canale per ritrasmissioni

L'obiettivo del TCP quando viene utilizzato per l'invio di grandi quantita di dati, è mandare in parallelo piu segmenti possibili. 

<span style=color:green>Soluzione</span> = Dobbiamo mettere appunto uno schema che <b><u>permetta all'entità TCP di trasmissione di dimensionare la finestra di trasmissione</u></b> in base al minimo tra : 
             $Min(Rete,BufferRicezione)$

 <b><u>Vogliamo che un entità TCP sia in grado di determinare il grado di saturazione della rete, e in funzione della maggiore o minore capacità recettiva della rete aumentare o diminuire il traffico sulal connessione</u></b>.  

<b><u>Un sensore utilizzato da TCP</u></b>, che non ha bisogno di segnali di controllo, per rilevare un eventuale guasto della rete è <span style=color:yellow>il mancato arrivo dei segnali di ACK</span> 
Se i buffer del router si saturano, i segmenti vengono eliminati e TCP rileva l'errore di trasmissione. 
<b><u>La sorgente come stima quanti segmenti inviare nell'unita di tempo</u></b>?

La <span style=color:yellow>finestra di congestione</span><b><u> indica quanti byte si possono immettere nella rete</u></b> 
La sorgente sa che se invio un segmento e ne ricevo l'ACK, allora il segmento ha lasciato la rete.
L'unica cosa sicura è l'ACK arrivano con il tempo piu lento della rete, essendo di piccole dimensioni
[[Dimensionamento della finestra di congestione]]

