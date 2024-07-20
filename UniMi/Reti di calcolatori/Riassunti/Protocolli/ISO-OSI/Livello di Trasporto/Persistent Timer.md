<span style=color:red>Problema</span>:= Supponiamo che <b><u>il ricevitore indichi al trasmettitore che il buffer di ricezione è pieno</u></b>, $W_r = 0$. 
il trasmettitore entrerà in stato di `wait`. 
L'unico modo in cui <b><u>riavvio l'invio di segmenti è con l'ACK da destinazione a sorgente</u></b> con $WIN = N$, <span style=color:red>SE tale segmento viene perso il trasmettitore rimane in wait, si crea una situazione di deadlock</span>.


Per risolvere ciò, quando viene settata la finestra $W_S$, parte un `Persist Timer` che, SE prima del suo scadere, non viene ricevuto un segmento con $WIN = N$, allora TCP manda un `Window Probe`. 
SE perdo tale segmento, potrò inviarlo nuovamente allo scadere del Timer.
Alla ricezione, viene riconosciuto come messaggio Window Probe e viene inviato nuovamente l'ACK con $WIN = N$ e $ACK = X + 2001$