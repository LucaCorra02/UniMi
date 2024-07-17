Ogni nodo contiene una <span style=color:yellow>tabella delle adiacenze</span>, con le seguenti entry : 
- <b><u>Router di destinazione</u></b>
- <b><u>Link per raggiungere il router</u></b> 
- <b><u>Costo</u></b> = Costo uguale alla <b><u>somma tra il costo nel distant vector e il costo per raggiungere il nodo da cui proviene il distant vector</u></b>.  `I costi dei link sono derivanti da un ICMP `.

<b><u>Le tabella di adiacenza permettono di costuire la conoscenza locale</u></b>. Capisco queli sono le macchine adiacenti al nodo e quanto costa raggiungere quella macchina. 
Per passare alla <span style=color:cyan>conoscenza globale</span>, <b><u>si sfruttano le informazioni provenienti dagli altri router</u></b>. 

Periodicamente ogni router trasmette il <span style=color:yellow>Distance Vector</span>, contenente le seguenti informazioni :
- `ip address router`
- `costo per raggiugnerlo`.

<b><u>Non specifica il link da utilizzare per raggiungere il router</u></b>.
Quando un Router riceve un Distance vector, <b><u>se la distanza è minore rispetto a quella salvata, viene modificata in tabella la entry sia il link che il costo.</u></b>.

<b><u>Ogni nodo così va a conoscere l'esistenza dei nodi e il costo per raggiungerli</u></b>, <span style=color:red>ma non conosce la topologia della rete</span>. 

<h5 style=color:cyan>Tempi</h5>
  <b><u>Un nodo impiega il diametro della rete per scoprire l'esistenza di tutti i nodi della rete</u></b>, ci vogliono un numero di istance vector pari al diametro della rete. Il cammino minimo può essere non disponibile fin da subito (dipende dalla propagazione degli istance vector), tutta via dopo un certo lasso di tempo si stabilizza. 

<h5 style=color:red>Problematiche</h5>

- <b><u>I distance vector possono arrivare in modo sparso, non vengono mandati in modo sincronizzato</u></b>. 

- <b><u>I distance vector possono essere persi</u></b>. 

- <b><u>L'algoritmo apprende molto facile il miglioramento, ma non il peggioramento</u></b> (caso di un link che si guasta ad esempio). Tale anomalia prende il nome <span style=color:yellow>count to infinity</span>, <b><u>si verifica quanto il distance vector contente il guasto rilevato arriva dopo o viene perso (essendo asincrono) e arriva prima un distance vector che indica che la destinazione può essere raggiunta attraverso il link guasto con un costo qualsiasi, portando così ad</u></b> un <span style=color:yellow>buoncing effect</span> di pacchetti, <b><u>che portano all'aumento della distanza verso la destinazione non raggiungibile  all'inifnito</u></b>.
  
  I nodi credono di poter raggiungere la destinazione guasta tramite altri nodi, l'anomalia si verifica anche perchè <b><u>nel distance vector, non viene indicato il link che viene utilizzato</u></b>. <b><u>I router aggiornano il costo verso una destinazione su uno specifico link guasto, senza accorgersi che il cammino passa per loro stessi</u></b>. 

Ottimizzazione: [[Split Horizon]]
Implementazione: [[RIP]]
