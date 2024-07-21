<b><u>La scelta del dimensionamento dell RTO è un fattore critico delle performance</u></b>.
<span style=color:red>Problema</span> = <b><u>TCP ha il problema di dimensionare RTO in quanto non sa stimare il reale RTT per ogni segmento inviato</u></b>. <b><u>Non posso campionare RTT a diversi istanti di tempo, in quanto è molto variabile</u></b> (dipende dallo stato della rete). A livello 4 abbiamo più link che il segmento deve attraversare, a differenza del livello 2. 

<span style=color:green>Soluzione</span> = <b><u>TCP per ogni segmento inviato risponde con un ACK relativo, lato trasmettitore posso ottenere una misura sistematica del RTT</u></b>. 

<b><u>il trasmettitore misura il RTT per ogni segmento inviato</u></b>. A questo punto le varie misure vengono utilizzate per comporre la distribuzione di ritardo, tenendo conto della storia. 
`Come outliner consideriamo il caso in cui l'ACK si perda`
Utilizziamo una distribuzione normale con media e deviazione standard
Considerando lo scadere dell'RTO come un outliner: $\mu + k*\sigma$

Fasi: https://chatgpt.com/share/8974add4-f592-45c1-b17e-094fef5319ec

---
- $T_0$ Momento in cui la <b><u>connessione viene aperta</u></b>: 

<b><u>Non ho informazioni sul</u></b> `RTT Round Trip Time`: da quando mando il segmento a quando ricevo l'ACK. 
<b><u>Di default :</u></b> = `RT0 3 secondi`.

Mantengo due variabili: 
- $SRTT = NULL$ (`Smoothing RTT` stima $\mu$) media ponderata del RTT (Round Trip Time) corrente e delle misurazioni precedenti. 
- $RTTVAR = NUL$L (`RTT Variance` stima $\sigma$,) 
- $G <= 100ms$ (G è la granularità del timer) = ovvero l'unità minima di tempo con cui il sistema misura e gestisce il tempo

SE al $T_0$ <b><u>scade l'RTO, raddoppio l'RTO</u></b> (fino a un massimo di 2 minuti) in quanto non ho informazioni

---
I<b><u> calcoli qua sotto valgono solamente per il primo ACK ricevuto</u></b>. 

- $T_1$ Momento in cui <b><u>ricevo un segmento di ACK</u></b> con un $RTT = R$
- $R$ = Misura dell'RTT attuale.

Imposto $SRTT = R$ e $RTTVAR = \frac{R}{2}$. $$RTO = SRTT + max(G, k*RTTVAR)$$con $k = 4$ (<b><u>suggerito</u></b>).
es 
$R = 10 ms$, 
$RTO = 10ms + 4*5ms = 30ms$, quindi da 3 secondi siamo passati a 30ms

---
- $T_k$, con $k>2$, quando arriva un $RTT = R$, 
- $0<\beta<1$ = <b><u>Bilancia la reattività del sistema alle variazioni di RTT</u></b> e la stabilità delle misurazioni nel tempo.
- $0<\alpha<1$ = <b><u>Server per bilanciare la storia e il valore attuale</u></b>, quanto un valore nuovo può spostare il valore storico di $SRTT$ : 
   - Se $a=1$ -> <b><u>Peso di più la storia</u></b> 
  - Se $a=0$ -> <b><u>Peso di più la misurazione di RTT attuale rispetto alla storia</u></b>.

<span style=color:yellow>Standard</span> $\alpha=\frac{1}{8}$ e $\beta=\frac{1}{4}$

Con $0<\beta<1$, imposto $$RTTVAR = (1-\beta)*RTTVAR + \beta*|SRTT-R|,$$
OSS piu $\beta$ è vicino a 0, piu tenderò ad aggiornare meno il mio valore
- Piu $\beta$ <b><u>è alto, piu sono sensibile agli sbalzi di R</u></b> MA se è solo un rumore temporaneo rischio di cambiare troppo
- Piu $\beta$ <b><u>è basso, piu RTTVAR è smussato MA non cattura una variazione</u></b>

Con $0<\alpha<1$, imposto
 $$SRTT = (1-\alpha)*SRTT + \alpha*R$$

Di conseguenza aggiornero l'RTO come 
$$RTO = SRTT + max(G, k*RTTVAR)$$con $k = 4$
SE a $T_k$ <b><u>RTO scade, raddoppio e poi quando riceverò R faro di nuovo la stima</u></b>

---
<span style=color:red>Problemi</span>:
Quando l'RTO scade, viene raddoppiato l'RTO E viene ritrasmesso il segmento. <b><u>MA se l'ACK del segmento precedente arriva molto dopo, ho un ambiguità perche non si capisce a quale trasmissione del segmento appartiene</u></b>.

<span style=color:yellow>Policy Karn, adottata dal TCP</span> =  <b><u>A seguito dello scadere del timer di ritrasmissione</u></b>: 
    $RTO_{new} = y * RTO_{old}$. Con $Gamma=2$
non considero RTT di nessuno dei due segmenti, non aggiornando quindi ne la media ne la varianza.

*Esempio*



