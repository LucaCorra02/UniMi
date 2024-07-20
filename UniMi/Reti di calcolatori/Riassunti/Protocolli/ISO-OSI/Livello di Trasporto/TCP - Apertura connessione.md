 <span style=color:yellow>La procedura di apertura di una connessione in TCP è a 3-vie</span> 
`Tree-way-handshake`: 
- SYN 
- ACK 
- ACK 

 <b><u>Ogni entità TCP generà usando come seed una parte del clock locale</u></b> un <span style=color:yellow>nuemro di sequenza iniziale pseudorandom</span>.
`SEQ SequenceNumber` <b><u>non parte sempre da 0</u></b>, per evitare che segmenti di una vecchia connessione ancora nella rete causino sovrapposizione
(Oggi non viene piu usato un approccio incrementale come nel LV2, ma viene usata una funzione crittografica) : 
- Tutto il flusso di dati che viaggia dal <b><u>server al client viene valido con numero di sequenza che parte da Y</u></b>
- Tutto il flusso di dati che viaggia dal <b><u>cleint al server viene valido con numero di sequenza che parte da X</u></b>


<b><u>All'inizio della connessione le due entità contrattano il</u></b> `MSS Max Segment Size`. SE non viene definito esplicitamente (attraverso la [[MSSO - Max Segment Size Option]]), è di <b><u>default 536byte</u></b> (perche si evita una frammentazione)

Fasi : 






1. La sorgente invia una <b><u>richiesta di connessione</u></b>, un segmento in cui : 
   - $SYN=1$
   - $SEQ=X$ (con $X$ il SEQ della sorgente; ACK non verra guardato perche il flag è a 0). 
   - Il sorgente è in stato di `SYN_SENT`
2. <b><u>Il ricevitore controlla il checksum e, se corretto, risponde con un segmento</u></b> in cui:  
   - $SYN=1$ 
   - $ACK=1$ 
   - $SEQ=Y$ 
   - $ACK = X+1$ 
   - Il ricevente entra in stato di `SYN_RCVD`. (ACK = Ciò che mi aspetto ora, ho ricevuto X, ora mi aspetto X+1)
3. <b><u>La sorgente è ora in stato di</u></b> `connessione established` ma <b><u>il ricevente non sa se la sorgente ha ricevuto il segmento precedente</u></b>, quindi viene inviato un segmento al ricevente con:  
    - $ACK=1$ 
    - $ACK=Y+1$
4. <b><u>Alla ricezione dell'ACK, entrambi hanno una connessione bidirezionale indipendente</u></b> (indipendente perche ci sono due SEQ indipendenti)

<span style=color:red>Problemi possibili</span>:
- `Non c è una porta in ascolto` nella socket ricevente
	- Viene mandato (al punto 2) un segmento con $RST=1$, resetto la connessione.
- <b><u>ACK da ricevente a mittente non arriva in tempo</u></b>. -> [[RTO]]