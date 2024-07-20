 <span style=color:yellow>La procedura di apertura di una connessione in TCP è a 3-vie</span> 
`Tree-way-handshake`: 
- SYN 
- ACK 
- ACK 

 <b><u>Ogni entità TCP generà usando come seed una parte del clock locale</u></b> un <span style=color:yellow>nuemro di sequenza iniziale pseudorandom</span>




Sia la sorgente che la destinazione scelgono un `SEQ SequenceNumber` 
SEQ non parte sempre da 0, per evitare che segmenti di una vecchia connessione ancora nella rete causino sovrapposizione
(Oggi non viene piu usato un approccio incrementale ma viene usata una funzione crittografica)

All'inizio della connessione le due entità contrattano il `MSS Max Segment Size`. SE non viene definito esplicitamente (attraverso la [[MSSO - Max Segment Size Option]]), è di 536byte (perche si evita una frammentazione)

Fasi
1. La sorgente invia una richiesta di connessione, un segmento in cui flag $SYN=1$ e $SEQ=X$ (con $X$ il SEQ della sorgente; ACK non verra guardato perche il flag è a 0). Il sorgente è in stato di `SYN_SENT`
2. Il ricevitore controlla il checksum e, se corretto, risponde con un segmento in cui $SYN=1$ e $ACK=1$ con $SEQ=Y$ e $ACK = X+1$. Il ricevente entra in stato di `SYN_RCVD`. (ACK = Ciò che mi aspetto ora -> ho ricevuto X, ora mi aspetto X+1)
3. La sorgente è ora in stato di `connessione established` ma il ricevente non sa se la sorgente ha ricevuto il segmento precedente, quindi viene inviato un segmento al ricevente con $ACK=1$ e $ACK=Y+1$
4. Alla ricezione dell'ACK, entrambi hanno una connessione bidirezionale indipendente (indipendente perche ci sono due SEQ indipendenti)

Problemi possibili:
- `Non c è una porta in ascolto` nella socket ricevente
	- Viene mandato (al punto 2) un segmento con $RST=1$
- ACK da ricevente a mittente non arriva in tempo. -> [[RTO]]