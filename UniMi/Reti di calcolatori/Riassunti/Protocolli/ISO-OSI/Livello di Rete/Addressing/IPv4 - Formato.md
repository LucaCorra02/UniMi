- Campo version: specifica se sia un IPv4 o IPv6
- Campo IHL Intermediate Header Length specifica la lunghezza dell'header come multiplo di 32 bit. La lunghezza minima senza opzioni è di 5, mentre il massimo permesso è 15.
- Campo TOS Type Of Service specifica la priorita dell'applicativo e gli attributi relativi al path da seguire
- Total lenght su 16bit: definisce la lunghezza totale del pacchetto (header+payload). La lunghezza massima del pacchetto è di 64k-1 bytes. Questo campo sarà utilizzato dalla destinazione per riassemblare il payload
- Campo Flag bits (3 bit): 
	- -
	- D bit indica se il pacchetto è stato frammentato o meno
	- M bit More fragment indica SE se ci sono altri frammenti del pacchetto (sarà 0 sull'ultimo frammento)
- Campo Fragment Offset: indica l'offset, in multipli di 8 bytes, rispetto all inizio del pacchetto
- TTL Time To Live: definisce il tempo massimo per il pacchetto in transito, verra decrementato in ogni gateway/router. E' usato per rilevare eventuali loop 
- Campo Protocol: usato per permettere alla destinazione IP di passare il all'interno di ogni pacchetto ricevuto allo stesso protocollo che ha mandato i dati (es ICMP or TCP or UDP)
- Campo Header checksum: per rilevare errori
- Source IPv4 su 32bit
- Destination IPv4 su 32bit
- Option: puo contenere per esempio il path da seguire per raggiungere la destinazione 
- Payload

[[NetID]]
