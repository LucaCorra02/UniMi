Ogni nodo contiene una <span style=color:yellow>tabella delle adiacenze</span>, con le seguenti entry : 
- <b><u>Router di destinazione</u></b>
- <b><u>Link per raggiungere il router</u></b> 
- <b><u>Costo</u></b>.

 `I costi dei link sono derivanti da un ICMP `

<b><u>Le tabella di adiacenza permettono di costuire la conoscenza locale</u></b>. Capisco queli sono le macchine adiacenti al nodo e quanto costa raggiungere quella macchina. 
Per passare alla <span style=color:cyan>conoscenza globale</span>, <b><u>si sfruttano le informazioni provenienti dagli altri router</u></b>. 

Periodicamente ogni router trasmette il <span style=color:yellow>Distance Vector</span>, contenente le seguenti informazioni :
- `ip address router`
- `costo per raggiugnerlo`.

<b><u>Non specifica il link da utilizzare per raggiungere il router</u></b>.
Quando un Router riceve un Distance vector, <b><u>se la distanza è minore rispetto a quella salvata, viene modificata in tabella la entry sia il link che il costo.</u></b>.







S<b><u>i tratta di un vettore che contiene ip address router  -> costo per raggiungerlo</u></b>. Non c'è scritto su quale link viene inoltrata l'informazione. 









`Il vettore delle distanze viene propagato ai nodi adiacenti` in modo da trasmettere la conoscenza della rete, inizialmente ciò che c'è nella tabella di adiacenza (gli indirizzi dei nodi ed i costi associati MA nei DV non vi è il link utilizzato in quanto è un info locale inutile)

Ricevendo il DV, il nodo scopre nuovi indirizzi raggiungibili (senza comprenderne la topologia) e capisce quanto costa arrivare ai nuovi indirizzi e quindi aggiungendo una nuova entry nella tabella di routing, dato dall'indirizzi e dal costo uguale alla somma tra il costo nel distant vector e il costo per raggiungere il nodo da cui proviene il distant vector 
Il diametro della rete influenza il tempo con cui si viene a conoscenza degli indirizzi da un nodo
La conoscenza si diffonde in base al diametro della rete

Quando per un entry gia esistente, si ottiene un costo minore, si cancella la entry e aggiorna costo e link.

Il Distant Vector viene mandato periodicamente MA `l'invio non è sincronizzato tra i link` (ed è meglio cosi)
Quindi non è detto che le tabelle di routing convergano immediatamente per il cammino minimo

Ottimizzazione: [[Split Horizon]]
Implementazione: [[RIP]]
