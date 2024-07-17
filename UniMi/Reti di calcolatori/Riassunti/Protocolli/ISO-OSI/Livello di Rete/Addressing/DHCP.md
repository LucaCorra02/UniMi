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























1. Il client fa una richiesta, `DHCP Discover`, a tutti gli host in broadcast (IPDestinazione = 255.255.255.255) e l'indirizzo mittente di 0.0.0.0. Il messaggi contiene un `TID TransactionID` cosicche il client riconosca la sua richiesta una volta che riceve una risposta dal server
2. Il server associa MAC address - TID, mandando una `DHCP Offer` che manda al client contenente ID della transazione, una proposta di un IP, la maschera per l'IP e la durata della validità dell'indirizzo. Per verificare che l'IP address non sia gia in utilizzo dagli altri, `il server fa un ping con l'IP address che sta offrendo`
3. Il client prende atto dell'offerta, potenzialmente piu di una (se ci sono piu server), producendo una `DHCP Request`. Campi: IP Sorgente (0.0.0.0), IP Destinazione (IP Server sempre in broadcast), TID
4. Da quel momento in poi al client è assegnato quell'IP, il server manda quindi un `DHCP ACK`. Da quando il client ricevo ACK, diventa indirizzabile MA prima `il client fa check attraverso un ARP request` (non dovrebbe rispondermi nessuno)

Vengono inseriti controlli per la discover e la request, ripetendo nel caso la ritrasmissione per al massimo k tentativi
