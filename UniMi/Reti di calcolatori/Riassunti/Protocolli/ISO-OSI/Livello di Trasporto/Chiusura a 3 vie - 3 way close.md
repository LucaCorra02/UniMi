Situazione: <span style=color:cyan>il client chiede la chiusura della connessione nonostante non abbia ricevuto tutti gli ACK</span>
<b><u>Il server ha ancora dei segmenti di cui deve mandare l'ACK</u></b>

L'applicazione del server, ricevendo EOF, fa la `close()` MA, dato che deve mandare al client un ACK, manda in un unico segmento $FIN = 1$, $ACK = 1$, $ACK=X+N+1$ (con $N$ ACK mancanti)