Situazione: il <span style=color:cyan>client ha ricevuto tutti gli ACK e il server non ha niente in sospeso da inviare</span>. 

 `close()` = Chiude entrambe le direzioni della connessione, e quindi impedisce di usare con quel socket sia primitive di input sia di output.


1. <b><u>L'applicazione sorgente chiama la primitiva</u></b> `close()`. Viene mandato il segmento al server con : 
   - flag $FIN=1$ 
   - $SEQ = X$ (con $V(S) = X$). 
   Il client entra in stato di `FIN_WAIT1 `
2. <b><u>Il server, quando riceve il segmento</u></b> (in particolare l'applicazione `receive(EOF)`), entra in stato `CLOSE_WAIT` inviando un segmento con :
  -  $ACK = 1, ACK=X+1$ 
3. <b><u>Nel frattempo la sorgente, alla ricezione dell'ACK, entra in uno stato di</u></b> `FIN_WAIT2` <b><u>attendendo il segmento con FIN dall altro host</u></b>
4. Dopo un certo tempo, <b><u>l'applicazione del server chiama la</u></b> `close()`, mandando un segmento con : 
   - $FIN = 1$ 
   - $SEQ=Y$ (con $V(R) = Y$) 
   entrando in uno stato di `LAST_ACK`
5. <b><u>Quando il client riceve il segmento entra in</u></b> `TIMED_WAIT` in un loop e manda un segmento $ACK = 1$, $ACK = Y$
2. <b><u>Il server ricevendo l'ACK, chiude la connessione</u></b> 
3. <b><u>Lato client dopo</u></b> $2MSL$ (`Max Segment LifeTime`) la <b><u>socket viene chiusa</u></b>.  Sta aspettando eventuali pacchetti in ritardo (massimo ritardo 4 minuti. ). 

![[Pasted image 20240722104104.png]]

