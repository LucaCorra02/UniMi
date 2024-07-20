<span style=color:red>Problema</span>:= Supponiamo che <b><u>il ricevitore indichi al trasmettitore che il buffer di ricezione è pieno</u></b>, $W_r = 0$. 
il trasmettitore entrerà in stato di `wait`. 
L'unico modo in cui <b><u>riavvio l'invio di segmenti è con l'ACK da destinazione a sorgente</u></b> con $WIN = N$, <span style=color:red>SE tale segmento viene perso il trasmettitore rimane in wait, si crea una situazione di deadlock</span>.

<span style=color:green>Soluzione</span> = Introduco un <span style=color:yellow>Persist Timer</span>. quando viene settata la finestra $W_S$=0,  <b><u>Il timer parte</u></b>.  <b><u>Se prima del suo scadere, non viene ricevuto un segmento con</u></b> $WIN = N$, allora <b><u>TCP manda un</u></b> `Window Probe`. 
Se perdo tale segmento, potrò inviarlo nuovamente allo scadere del Timer.

<b><u>Alla ricezione, viene riconosciuto come messaggio Window Probe e viene inviato nuovamente l'ACK con</u></b> $WIN = N$ e $ACK = X + 2001$




