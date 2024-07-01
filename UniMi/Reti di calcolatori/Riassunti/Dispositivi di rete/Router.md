 i nodi della rete prendono il nome di <span style=color:yellow>Router</span> e <b><u>si occupano principalmente della funzione di instradamento</u></b>, ovvero instradare i pacchetti sul camino migliore da una sorgente A a un destinatario B, operano quindi a <b><u>livello 3</u></b>. 
<b><u>Non sono delle macchine general purpose</u></b>, ma sono delle macchine dedicate ad effettuare le funzioni di instradamento in una rete di calcolatori. 

I vari algoritmi di instradamento presente sul routing possono utilizzare <b><u>diverse metriche per decidere il cammino</u></b> (più semplice <span style=color:cyan>hop</span> , il cammino migliore viene determinato in base a numero di salti).

<span style=color:green>Componenti di un router</span>: 
- Abbiamo un <b><u>link di ingresso e di uscita</u></b> a tutti i dispositivi collegati al router, in quanto il canale è bidirezionale. 

- <b><u>Ad ogni link è associata una porta di i/0</u></b> con un buffer ([[Porte I-0 e Link]]). I buffer vengono gestiti come delle code FIFO (*il primo messaggio che raggiunge il nodo 4 dal nodo 2 viene accodato*). 

- <b><u>Abbiamo un processo che fa da scheduler</u></b>, gestisce il traffico in ingresso e uscita del nodo. il processo pesca dalle varie code, interpreta l'informazione (<b><u>in realtà un secondo processo detto processo di routing</u></b>), risolvendo l'indirizzo di destinazione.  

- Attraverso un opportuna <b><u>Tabella di routing</u></b> e la destinazione dell'informazione, il router identifica una porta per raggiungere la destinazione, indicando allo scheduler di imboccare l'informazione nella coda di uscita corretta. 
  Tutte le misure di costo nella rete, vengono raccolte da ogni singolo nodo e raccolte nella tabelle di routing. 

<span style=color:yellow>il collo di bottiglia</span> <b><u>di una rete sono i nodi router</u></b>, la complessità lievità all'aumentare del numero di link. I router <b><u>possono dunque rappresentare un elemento di congestione nella rete</u></b> : 
- in passato i colli di bottiglia delle reti erano la velocità di trasmissione dei collegamenti, i link ( oggi si ha la fibra otticha)

Al fine di ridurre il collo di bottiglia, <b><u>l'unità dati a livello utente viene</u></b>  <span style=color:yellow>frammentata</span>. Viene fissata una dimensione massima, creando <span style=color:yellow>pacchetti</span>. 
La <span style=color:yellow>frammentazione</span> deve <b><u>avviene lato mittente, il quale aggiunge un header o intestazione con delle informazioni necessarie per il funzionamento della rete</u></b>, quali il proprio indirizzo. 

<span style=color:green>Funzionamento: </span>
- I router hanno un piccolo SW di instradamento che periodicamente, facendo una codifica dei pacchetti (in particolare lo header che sicuramente contiene sorgente e destinazione), decide in che porta mandare il pacchetto. secondo la tabella di routing.

- <b><u>La tabella di instradamento contiene dato un destinatario, la porta di uscita associata che permette di seguire il percorso migliore</u></b> per ogni indirizzo raggiungibile.

Piu piccoli sono i pacchetti, meno spazio occuperemo nelle code ma avremo un overhead a causa dell'header di ogni pacchetto. 
<b><u>Serve un compromesso tra lo spazio occupato nelle code e l'overhead</u></b>

Man mano che il pacchetto viene processato dai router, aumenta di dimensione, diminuendo quando arriva al destinatario <span style=color:yellow>fragmentation-assembly-deassembly</span>.
La sequenza prelevamento-decodifica-forward deve essere effettuata il piu velocemente possibile. 
Difatti l'header è posizionato nei primi bit cosi il router sia piu veloce nella lettura

![[photo_5769355704325488878_y.jpg|400]]