Il campo <span style=color:yellow>Window Size</span> <b><u>di ogni segmento indica il numero di byte che il TCP ricevente puo ricevere nel buffer di ricezione</u></b>. In questo modo si garantisce che ci sia sempre spazio libero nel buffer del ricevente prima che la sorgente mandi i dati.

Introduciamo 2 variabili: 
- $W_S$ (`Finestra di invio`). Il flusso si ferma quando $W_S$ = 0 
- $W_R$ (`Finestra di ricezione`) che <b><u>utilizzeremo nell'header del TCP in window size</u></b>

$W_R$ <b><u>è aumentata quando la destinazione riceve dei dati privi di errore</u></b> mentre <b><u>viene diminuita quando l'applicativo destinatario legge dei byte dal buffer</u></b>.

[[TCP - Controllo del flusso Esempio]]

- Perdita dell'ACK -> [[Persistent Timer]]
- Silly Window Syndrome -> [[Algoritmo di Clark]]
