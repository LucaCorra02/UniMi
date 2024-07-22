Situazione: <span style=color:cyan>il client ha finito di inviare dati MA server deve ancora inviare dati al client</span>. 

`shoutdown()` = la shutdown da’ la possibilita’ di effettuare chiusure asimmetriche di una connessione, specificando quale direzione deve essere interrotta.

1. Client usa la primitiva `shoutdown()` <b><u>per notificare che si è finito di inviare dati</u></b>. <b><u>La socket viene lasciata aperta in ricezione</u></b> ma non in scrittura, il client non può più mandare dati.  Client manda segmento $FIN$ e entrando in `FIN_WAIT1`.
2. Anche in questo caso L'applicativo  del server riceve EOF, <b><u> MA il server non ha finito di inviare dati</u></b>, cosi continua con le proprie `send(NByte)` mandandoli insieme a 
    - $ACK = 1$, $ACK = X+1$ 
    - $SEQ = Y$ 
    - $NByte$. 

 3. <b><u>Il canale Server-Client è ancora attivo, riuscendo quindi a mandare l'ACK al server per il segmento ricevuto</u></b>
1. Quando avrà terminato l invio dei dati, <b><u>l'Applicazione lato server userà a sua volta la primitiva</u></b> `shutdown()`, e il TCP manderà un segmento di $FIN = 1$, $SEQ =  Y + N$.
2. In risposta, il client manderà $ACK=1$, $ACK=Y+N+1$. Entra cosi in una fase di `TIMED_WAIT` in cui allo scadere del timer di $2MSL$, chiude la connessione
3. Il server, alla ricezione dell'ACK, chiude la connessione

![[Pasted image 20240722104156.png]]

