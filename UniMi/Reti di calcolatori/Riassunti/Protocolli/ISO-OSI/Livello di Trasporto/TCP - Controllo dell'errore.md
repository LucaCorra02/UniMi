Manteniamo una variabile sia nel mittente che nel destinatario ($V_S$/$V_R$) con la `Initial Sequence Number`

<b><u>TCP ritrasmette un segmento SOLO quando riceve 3 ACK duplicati per lo stesso segmento</u></b>.
Questo sistema funziona finche ho qualcosa da trasmettere, difatti non verrà mai mandato un ACK al mittente. 
<b><U>Per ogni trasmissione, un RTO inizia per il nuovo segmento </u></b>
Per ottimizzazione è essenziale un'accurata [[Calibrazione RTO|calibrazione dell'RTO]]

<b><u>Quando la ritrasmissione avviene prima dello scadere dell'RTO, in quanto ho ricevuto 3 ACK duplicati, si parla di</u></b> `Fast Retrasmission`
[[Fast Retrasmission - Esempio]]