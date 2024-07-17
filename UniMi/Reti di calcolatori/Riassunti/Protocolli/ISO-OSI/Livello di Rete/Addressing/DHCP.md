`DHCP - Dynamic Host Configuration Protocol` 
<b><u>Si tratta di un protocollo che permette di assegnare dinamicamente IP ad host situati in una VLAN</u></b> . La struttura del protocollo è <span style=color:cyan>Client-server</span>. Questo viene fatto tramite il <span style=color:yellow>DHCP SERVER</span> : 
- <b><u>Possiede un pool di indirizzi ip privati e li assegna ai dispositivi all'interno della LAN che ne fanno richiesta</u></b>. 
- Solitamente può essere montato all'interno del gateway NAT. 
- Sulle reti grosse possono essere presenti più DHCP server. 










permette di ottenere un indirizzo IP a nome dell'host
Devo ovviamente garantire che l'IP che assegno dinamicamente, rimanga unico per il periodo di utilizzo
Le macchine si rivolgono automaticamente al server DHCP della rete, solitamente il gateway della rete
Nelle organizzazioni piu complesse, ci possono essere diversi DHCP server 

DHCP funziona a `4 vie (Discover-Offer-Request-ACK)` perche i server possono essere piu di uno
1. Il client fa una richiesta, `DHCP Discover`, a tutti gli host in broadcast (IPDestinazione = 255.255.255.255) e l'indirizzo mittente di 0.0.0.0. Il messaggi contiene un `TID TransactionID` cosicche il client riconosca la sua richiesta una volta che riceve una risposta dal server
2. Il server associa MAC address - TID, mandando una `DHCP Offer` che manda al client contenente ID della transazione, una proposta di un IP, la maschera per l'IP e la durata della validità dell'indirizzo. Per verificare che l'IP address non sia gia in utilizzo dagli altri, `il server fa un ping con l'IP address che sta offrendo`
3. Il client prende atto dell'offerta, potenzialmente piu di una (se ci sono piu server), producendo una `DHCP Request`. Campi: IP Sorgente (0.0.0.0), IP Destinazione (IP Server sempre in broadcast), TID
4. Da quel momento in poi al client è assegnato quell'IP, il server manda quindi un `DHCP ACK`. Da quando il client ricevo ACK, diventa indirizzabile MA prima `il client fa check attraverso un ARP request` (non dovrebbe rispondermi nessuno)

Vengono inseriti controlli per la discover e la request, ripetendo nel caso la ritrasmissione per al massimo k tentativi
