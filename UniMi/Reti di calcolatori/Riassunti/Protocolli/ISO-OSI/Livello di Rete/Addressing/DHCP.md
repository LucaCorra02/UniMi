`DHCP - Dynamic Host Configuration Protocol` 
<b><u>Si tratta di un protocollo che permette di assegnare dinamicamente IP ad host situati in una LAN</u></b> . La struttura del protocollo è <span style=color:cyan>Client-server</span>. 

Questo viene fatto tramite il <span style=color:yellow>DHCP SERVER</span> : 
- <b><u>Possiede un pool di indirizzi ip privati e li assegna ai dispositivi all'interno della LAN che ne fanno richiesta</u></b>. 
- Solitamente può essere montato all'interno del gateway NAT. 
- Sulle reti grosse possono essere presenti più DHCP server. 

<b><u>Gli indirizzi ip prodotti da una richiesta DHCP sono temporanei, hanno un TTL (time to leave)</u></b>
<h5 style=color:cyan>Funzionamento DHCP</h5>
DHCP funziona a <span style=color:yellow>4 vie (Discover-Offer-Request-ACK)</span> perche i server possono essere piu di uno: 

 - l client fa una richiesta, <span style=color:yellow>DHCP discovery</span>, ed è una <b><u>richiesta broadcast</u></b>.   
   La <span style=color:yellow>dhcp discover</span> <b><u>è un pacchetto ip che viaggia con</u></b> : 
    - <span style=color:cyan>IP sorgente settato a zero</span> =  `IP sorgente = 0.0.0.0`.
    - <span style=color:cyan>IP Destinazione</span> = `255.255.255`.  Pacchetto broadcast all'interno della LAN. 
    - <span style=color:cyan>TID Transaction Id</span> = <b><u>Inizializzato con un transaction id univoco generato internamente alla macchina client</u></b>, e sarà associato all'indirizzo IP del richiedente.  
     <b><u>In modo tale da poter associare una replay ad una specifica richiesta (siccome la richiesta è broadcast)</u></b>. 

	  <b><u>Per associare univocamente la risposta ad una richiesta di un certo client potremmo associare il TL al MAC address</u></b> (siccome l'ip non è conosciuto). 


 - Prima di eseguire una <span style=color:yellow>dhcp offer</span>, <b><u>il server effettua un check</u></b>. Il server controlla attraverso <span style=color:yellow>ICMP</span> <b><u>che l'ip che sta offrendo non sia già stato assegnato ad un altro client</u></b>. Il server (o i server) ricevono la richiesta e rispondono con una <span style=color:yellow>dhcp offer</span>. formato che segue : 
   - <span style=color:cyan>IP sorgente</span> =Ip del server 
   - <span style=color:cyan>IP Destinazione</span> = brodcast
   - <span style=color:cyan>IP assegnatoli</span> = <b><u>Indirizzo ip assegnato al client associato al Transaction id del client (univocamente associato al MAC address del client)</u></b> 
   - <span style=color:cyan>Durata IP</span>
   - <span style=color:cyan>Maschera</span>

- Il client potrebbe ricevere più offert (<b><u>viaggia in broadcast</u></b>), <b><u>tuttavia dovrà decidere quale delle k offerte scegliere</u></b>. Viene aggiunta una fase di <span style=color:yellow>commit</span>. 
  Fase di <span style=color:yellow>commit</span>. Il client esegue una <span style=color:yellow>DHCP request</span> . i campi della request sono formati nel seguente modo : 
   - <span style=color:cyan>Ip Sorgente</span> = vuoto `IP sorgente = 0.0.0.0`.
   - <span style=color:cyan>ip Destinazione</span> = broadcast
   - <span style=color:cyan>Scelta</span> = <b><u>Il client specifica l'ip del server DHCP di cui  vuole accettare l'offerta</u></b>. 

- <b><u>Nel momento in cui i server S1,...,SK riceveranno la request, solo il server selezionato, risponderà con una</u></b> <span style=color:yellow>DHCP ACK</span>, che interrompe la fase di comitment (mandata in broadcast).   Gli altri server marcheranno l'offerta come non asserita. 

- l client nel momento in cui riceve una <span style=color:yellow>DHCP ACK</span> <b><u>esegue un altro check</u></b>. <b><u>Per scoprire se l'ip è già attivo in rete viene utilizzato un altro strumento rispetto ICMP</u></b>  (usato dal server), viene utilizzato <span style=color:yellow>ARP</span>. 

<b><u>Per tutta la durata abbiamo un timer lato client</u></b>, esso scade se non ricevo una offert dopo un certo lasso di tempo. In quel coso trasmetterò una nuova richiesta con un nuovo transaction id. 
<b><u>il numero di retry  per la fase di commitment è al massimo K (numero di Server DHCP)</u></b>, Se ho un numero di try > K ritorno alla fase di <span style=color:yellow>discover </span>, ri-iniziando da capo.
