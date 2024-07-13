<span style=color:green> Obbiettivo</span> = <b><u>Risolvono il problema dell'utilizzo del canale</u></b> (tempo di RTT dominato dal tempo di propragazione), <b><u>per ogni frame non devo più aspettare di ricevere l'ack relativo, ma posso trasmettere frame in serie</u></b>, i relativi ACK arriveranno in seguito. 

$UtilizzoCanale = k* \dfrac{T_x}{T_x+2T_p}$ 
introduciamo un parametro <span style=color:yellow>k </span>= <b><u>numero di frame che il trasmettitore è abilitato a trasferire al ricevitore senza aspettare l'ACK relativo</u></b>. Più basso è il rapporto, maggiore sarà il numero di frame che il trasmettitore piò spedire. 

<span style=color:yellow>Finestra</span> = <b><u>insieme di K frame che in un certo istante di tempo T, sono abilitato a trasmettere (frame di cui posso aspettare un ACK)</u></b>.

SE $k=1$, stiamo usando un idle RQ
La finestra tuttavia non è facile da dimensionare 
Idle RQ e go-back N necessitano solo di un buffer mentre per il selective repeat sono necessari $k$ frame. 

`MxSq Max Sequence Number` Numero di identificatori necessari:
- `Idle RQ`: le finestre di ricezione e invio sono entrambe 1.
- `Go back N`: data una finestra di $k$, il numero di identificatori deve essere di almeno $k+1$ in quanto con k usato, il ricevente non sarebbe in grado di determinare se il un frame ricevuto sia nuovo o il duplicato del precedente
- `Selective repeat`: data una finestra di $k$, il numero di identificatori deve essere di almeno $2k$, in quanto nel caso peggiore in cui vengano inviati k frame e tutti gli ACK siano corrotti, il destinatario deve essere in grado di determinare se uno dei successivo k frame sia un nuovo frame.

es
$4 bit$ seq --> al massimo $16$ identificatori GBN --> finestra massima $k=15$
$4 bit$ seq --> al massimo $16$ identificatori SR --> finestra massima $k=8$

$3 bit$ seq --> al massimo $8$ identificatori GBN --> finestra massima $k=7$
$3 bit$ seq --> al massimo $8$ identificatori SR --> finestra massima di $k=4$