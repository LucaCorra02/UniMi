`OSPF - Open Shortest Path First`
Si tratta di un algoritmo di routing che implementa la tecnica Link State. 
<b><u>Algoritmo che ogni nodo della rete esegue tutte le volte che riceve un update di un LS, in particolare usa l'algoritmo di Dijkstra</u></b>.

<span style=color:green>Vantaggi</span> : 
- <b><u>OSPF lavorando sull'intera topologia di rete, scopre anche</u></b> i <span style=color:yellow>multipath</span> il traffico può essere bilanciato su cammini equivalenti (non possibile con distance vector).

- Con OSPF è <b><u>possibile effettuare</u></b> <span style=color:yellow>source routing</span> = Avendo la conoscenza di tutta la tipologia della rete <b><u>posso obbligare un pacchetto a seguire un certo itinerario</u></b> (anche se non è il cammino migliore). Questa <b><u>informazione viene contenuta nell'header del pacchetto</u></b>. 

- <b><u>Convergenza verso il cammino minimo assicurata</u></b>

<span style=color:red>Svantaggi</span>: 
 - <b><u>allento traffico e ho un costo computazionale</u></b>

Come ragiona un nodo
Livelli di tabelle
- Tabella di `adiacenze` che popolo attraverso le ICMP: dato il nodo della rete destinazione, indica la porta del router associata
- Tabella di `routing`: dato il nodo della rete destinazione, indica l'hop da eseguire e il costo totale del cammino
- Tabella `NetID`: dato il NetID della destinazione, indica il nodo a cui mandare il pacchetto

Uso combinazione routing (guardo le 3 tabelle) e forwarding (faccio un hop). Fasi:
1. Ispeziono la NetID table per ricavare, dato il NetID destinazione, il nodo a cui inviare il pacchetto
2. Ispezione la routing table per capire come raggiungere il nodo destinazione
3. Ispezione la tabella di adiacenza per ricavare la porta del router a cui inviare il pacchetto per raggiungere il nodo destinazione

![[photo_5769355704325488902_y.jpg|400]]

[[Spanning tree broadcast]]