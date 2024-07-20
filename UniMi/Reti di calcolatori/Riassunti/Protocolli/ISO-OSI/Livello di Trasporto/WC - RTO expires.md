<span style=color:cyan>Gestione degli errori:</span>
<b><u>Dobbiamo tener conto se l'errore è rilevato tramite il time out (più grave) o tramite fast retrasmit (meno grave)</u></b>. 

Standard  `RFC 5681`. 

SE RTO scade, NON ho ricevuto nessun ACK
La <span style=color:red>congestione è molto grave</span> in quanto<b><u> lo scadere del RTO è considerato come un evento raro</u></b>.

  - $WC = 1 * MSS$ -> <b><u>La finestra di congestione rincomincia da capo, riparto con la fase di slow_start</u></b>.
  
  - $SST = \dfrac{W_c{size}}{2}$ =  La SST viene diminuita in particolare alla <b><u>meta della finestra in cui è scaduta l'RTO</u></b>.

![[Pasted image 20240720171205.png]]
