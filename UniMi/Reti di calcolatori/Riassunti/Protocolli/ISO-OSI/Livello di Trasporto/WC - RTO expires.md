<span style=color:cyan>Gestione degli errori nella fase di s</span>
<b><u>Dobbiamo tener conto se l'errore è rilevato tramite il time out (più grave) o tramite fast retrasmit (meno grave)</u></b>. 


SE RTO scade, NON ho ricevuto nessun ACK
La `congestione è molto grave` in quanto lo scadere del RTO è considerato come un evento raro

Quando scade l'RTO, si riparte con $W_C = 1$ quindi con uno Slow Start MA la SST viene diminuita in particolare alla meta della finestra in cui è scaduta l'RTO