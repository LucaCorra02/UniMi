<span style=color:yellow>Link State Routing</span>

<span style=color:green>Obbiettivo</span> = <b><u>Voglio una politica che misura le adiacenze e i relativi costi e che permetta ad ogni nodo della rete di venire a conoscenza dell'intera topologia della rete con i relativi costi sui vari link</u></b> (non solo i nodi che ne fanno parte).
Vado a costuire il grafo di connettività della rete su cui sto operando. 

<b><u>Il costo per raggiungere il vicino viene stimato attraverso i ping, con il protocollo ICMP</u></b>.


1. <b><u>Costruzione adiacenza</u></b>: le tabelle di adiacenza vengono costruite nello stesso modo del DV 
2. <b><u>Diffusione Link State</u></b>: una volta misurato il costo delle adiacenze, questa informazione non viene propagata ai nodi adiacenti, Ma <span style=color:yellow>gli ls vengono mandati a tutti i nodi della rete, non solo ai nodi adiacenti</span>.

La tecnica che si usa per propagare il <span style=color:cyan>link state</span> nella rete è il <span style=color:yellow>flooding</span> := La principale caratteristica del <b><u>flooding è che propaga in avanti e non sulle porte da cui ha ricevuto il messaggio da propagare</u></b>. 

  <b><u>Bisogna andare ad intercettare i duplicati</u></b>, se un nodo ha già ricevuto un <span style=color:cyan>link state</span> lo scarta e non lo ripropaga, <b><u>in modo da andare ad interrompere la propagazione di questi messaggi di controllo</u></b>.

 <span style=color:green>Soluzione</span> = Si utilizza un <span style=color:yellow>Sequence Number</span>, <b><u>un numero di sequenza associato univocamente al nodo sorgente</u></b>. <b><u>Ogni nodo tiene in memoria l'indirizzo di sorgente e il sequence number dei link state che ha ricevuto</u></b>. 

Ogni nodo appena riceve un LS da un nodo adiacente, `manda un segnale di ACK`. Questo cerca di garantire la consistenza. SE non ricevo l'ACK, viene ritrasmesso il LS (`ridondanza locale`) ma non viene rinviato all infinito in quanto sappiamo che nelle altre direzioni verrà ripropagato `(ridondanza temporale`). 

<b><u>Ogni nodo manda a tutti gli altri nodi la propria visione della rete.</u></b> Supponendo di avere N nodi, avremo una complessità dell'ordine di $O(n^2)$. 

<h5 style=color:cyan>Struttura Link State: </h5>
Un link state è costituito dai seguenti campi : 
- `indirizzo ip sorgente nodo`
- `Sequence number` = numero di sequenza associato univocamente al nodo sorgente. 
- `TTL` = Numero di Hop massimi che il link state può fare nella rete prima di essere cancellato. 
- `(ridondanza temporale` =Nel formato indirizzo nodo -> costo. 




LS composto da: Sorgente, Sequence, TimeToLive, NumeroHop, 
Il Sequence è assegnato dalla sorgente in modo da evitare le coppie di LS gia ricevuti

Inondando la rete di traffico di controllo TUTTI conoscono esattamente la topologia della rete
Questo ci permette di superare il problema dei DV, `count to infinity`

Per ogni link ho un costo bidirezionale

![[photo_5769355704325488905_y.jpg|500]]
Implementazione: [[OSPF]]