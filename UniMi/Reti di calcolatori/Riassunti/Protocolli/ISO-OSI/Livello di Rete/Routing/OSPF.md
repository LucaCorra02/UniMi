`OSPF - Open Shortest Path First`
Si tratta di un algoritmo di routing che implementa la tecnica Link State. 
<b><u>Algoritmo che ogni nodo della rete esegue tutte le volte che riceve un update di un LS, in particolare usa l'algoritmo di Dijkstra</u></b>.

<span style=color:green>Vantaggi</span> : 
- <b><u>OSPF lavorando sull'intera topologia di rete, scopre anche</u></b> i <span style=color:yellow>multipath</span> il traffico può essere bilanciato su cammini equivalenti (non possibile con distance vector).

- Con OSPF è <b><u>possibile effettuare</u></b> <span style=color:yellow>source routing</span> = Avendo la conoscenza di tutta la tipologia della rete <b><u>posso obbligare un pacchetto a seguire un certo itinerario</u></b> (anche se non è il cammino migliore). Questa <b><u>informazione viene contenuta nell'header del pacchetto</u></b>. 

- <b><u>Convergenza verso il cammino minimo assicurata</u></b>

<span style=color:red>Svantaggi</span>: 
 - <b><u>allento traffico e ho un costo computazionale</u></b>


Come ragiona un nodo, Livelli di tabelle
- Tabella di `adiacenze` che popolo attraverso le ICMP: <b><u>dato il nodo della rete destinazione, indica la porta del router associata</u></b>>
- Tabella di `routing`: <b><u>dato il nodo della rete destinazione, indica l'hop da eseguire e il costo totale del cammino</u></b>
- Tabella `NetID`: <b><u>dato il NetID della destinazione, indica il nodo a cui mandare il pacchetto</u></b>

Uso combinazione routing (guardo le 3 tabelle) e forwarding (faccio un hop). Fasi:
1. Ispeziono la NetID table per ricavare, <b><u>dato il NetID destinazione, il nodo a cui inviare il pacchetto</u></b>
2. <b><u>Ispezione la routing table</u></b> per capire come raggiungere il nodo destinazione
3. <b><u>Ispezione la tabella di adiacenza per ricavare la porta del router a cui inviare il pacchetto</u></b> per raggiungere il nodo destinazione

![[Pasted image 20240718114221.png]]

<span style=color:yellow>Routing table</span> : 

| Destinazione | Router | Costo |
| ------------ | ------ | ----- |
| R1           | -      | 0     |
| R2           | R2     | 2     |
| R3           | R2     | 3     |
| R4           | R4     | 2     |
<span style=color:yellow>Tabelle adiacenze</span> (caso di R1):

|     | Destinazione | Numero porta |     |
| --- | ------------ | ------------ | --- |
|     | G            | 1            |     |
|     | R2           | 2            |     |
|     | R4           | 3            |     |
 




[[Spanning tree broadcast]]