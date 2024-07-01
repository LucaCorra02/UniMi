Un <span style=color:yellow>Protocollo</span> <b><u>è un insieme di regole e convenzioni che permettono a due processi in esecuzione su macchine remote di evolvere in modo sincronizzato</u></b>. Ovviamente le due entità devono usare lo stesso protocollo.

Tali processi utilizzano delle <span style=color:yellow>funzioni di rete</span>. <b><u>Sarà compito della funzione eseguire il servizio promesso, usando il protocollo specificato</u></b>, ognuna di esse è specificata da due attributi : 

 - <b><u> il protocollo</u></b> = legato alla specifica funzione. Mi consente di parlare con l'interlocutore remoto. il protocollo è una specifica di un sistema distribuito. <b><u>Ad ogni funzione di rete è associato almeno un protocollo</u></b>. 
 
 - <b><u>interfaccia di servizio</u></b> = <b><u>per accedere al servizio offerto dalla funzione</u></b>, serve a chi la utilizza. Si tratta di un interfaccia interna alla macchina. 
 
Due modalità di utilizzo di protocollo
- Servizi `orientati alla connessione`: fare una connessione significare istaurare un canale (setup), il dialogo e infine una fase di rilascio.

- Servizi `senza connessione`: appena ho il dato lo mando, senza contrattare i QoS

Protocolli di rete:
- [[Reti di calcolatori/Riassunti/Protocolli/ISO-OSI/ISO-OSI|ISO-OSI]]
- [[Reti di calcolatori/Riassunti/Protocolli/TCP-IP|TCP-IP]]

Trasporto e Internet implementato nel SO
Ente di standardizzazione IEEE 802.
802.3 LAN
802.11 WiFi
802.15 Bluethoot
SE cambiano i protocolli, NON devono cambiare le interfacce tra i livelli