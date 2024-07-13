<b><u>Per rendere un canale affidabile, il ricevente controlla il frame per dei possibili errori di trasmissione</u></b>, ritornando un segnale di ACK positivo o negativo (NACK) in modo da richiedere nuovamente il frame

i protocolli che vedremo in realtà non utilizzano il messaggio di controllo $NACK$, ma possono utilizzare un $ACK$ con due significati diversi : 
- <span style=color:yellow>ACK selettivo</span> = <b><u>selettivamente mi dice se ho ricevuto correttamente l'i-frame con numero di sequenza K. </u></b>.

-  <span style=color:yellow>ACK comulativo</span> = <b><u>Indico al trasmettitore che il ricevitore è arrivato a ricevere correttamente dei frame fino al numero di sequenza indicato nell'ACK</b></u>. Inoltre con <b><u>questa semantica permette di riuscire a gestire situazioni in cui gli ACK vengono persi</u></b> rispetto alla semantica precedente. 


Questo tipo di controllo dell'errore viene detto `Automatic Repeat Request ARQ`

Tipi di ARQ:
- [[Idle RQ]]
- [[Continuous RQ]]