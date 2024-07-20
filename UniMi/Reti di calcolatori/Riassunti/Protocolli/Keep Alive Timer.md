 <span style=color:red>Problema</span> = Una delle due entità è attiva mentre l'altra no. <b><u>L'entità attiva alloca spazio e tempo ad una conessione inattiva</b></u> . *Ad esempio il trasmettitore decide di spengere il pc senza chiudere prima la connessione.*

<span style=color:green>Soluzione</span> = Introduco il timer <span style=color:yellow>keep alive</span>, <b><u>settato di default a 2 ore</u></b>. 
Alla scadenza del timer, verranno <b><u>inviati una serie di probe</u></b> per vedere se l'altra entità è viva. Da cui abbiamo una <b><u>Sequenza di </u></b> <span style=color:yellow>keep alive timer</span> : 
- Secondo timer, durata di 75 secondi 
- Terzo timer : Closed. 