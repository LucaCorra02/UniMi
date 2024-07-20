Situazione: `produttore veloce e consumatore lento`. Il problema è analogo al [[TCP - Algoritmo di Nagle]] ma lato ricevitore, <b><u>abbiamo un ricevitore che svuota il buffer di ricezione molto lentamente e un produttore veloce</u></b>.

<span style=color:yellow>Silly Window Syndrome</span>:= Problema che si ha nelle applicazioni che fanno uso di una sliding window, <b><u>il trasmettitore potrebbe richiedere inviare un basso numero di byte, mentre il ricevitore potrebbe leggere molto lentamente dal buffer di ricezione (oppure entrambe le sistuazioni), intasando la rete con moltissimi segmenti</u></b>. 

<b><u>Lato ricevente, ipotizziamo che l'applicazione legga un byte alla volta</u></b>. MA <b><u>ogni volta che si libera la finestra, dovrei inviare un ACK solo per notificare una finestra di 1 byte</u></b> e la sorgente invierebbe un segmento solo per un byte (con un header da ... byte). 
<b><u>Questa situazione causerebbe un messaggio di windows update ogni byte letto, provocando uno storm di windows update</u></b>.
Siccome gli <span style=color:yellow> windows update message</span> <b><u>sono dei messaggi di controllo (solo header), vanno a generare del traffico inutile sulla rete </u></b>. 

<span style=color:green>Soluzione</span>: algoritmo di Clark. 
Prima di inviare uno <span style=color:yellow> windows update message</span>, <b><u>aspetto l'intercorrere del seguente tempo</u></b> : 
     $Min(1/2 * BufferSize, MaximumSegmentSize)$

Prima di rispondere, il ricevitore aspetta il minimo tra: 
- <b><u>Aver svuotato almeno 1/2 del buffer di ricezione</u></b> 
- Oppure la <b><u>massima dimensione dei segmenti TCP</u></b>. 