Protocollo a livello data link che definisce il formato standard del frame:

| Campo          | Dimensione | Descrizione                                 |
| -------------- | ---------- | ------------------------------------------- |
| Flag           | 8 bit      | `0 111 111 0`                               |
| Indirizzo      | 8/16 bit   |                                             |
| Controllo      | 8/16 bit   | composto da 4 campi                         |
| 0              | 1 bit      | indica la tipologia di frame: I-frame       |
| V(S)           | 3/7 bit    | sequence number del mittente (sender)       |
| P/F            | 1 bit      |                                             |
| V(R)           | 3/7 bit    | sequence number del destinatario (receiver) |
| check sequence | 16/32 bit  | controllo dell'errore                       |
| Flag           | 8 bit      | `0 111 111 0`                               |

<b><u>il livello 2 avrà il compito di capire e in caso non trasmettere a livello superiore i duplicati, effettuando una propria numerazione dei frame</u></b>. 
Vado a introdurre due variabili : 
- <span style=color:yellow>Variabile di send</span> $V_s$ = inizializzata a 0. Lato trasmettitore la prima frame che trasmetto avrà numero di sequenza 0. <b><u>La variabile verrà incrementata quando la sequenza send e ack lato trasmettitore è stata completata correttamente</u></b>. Se il trasmettitore riceve un ack di un frame con numero di sequenza inferiore a quello previsto, scarta quello che ha nel buffer e ritrasmette. 

- <span style=color:yellow>Variabile di recive</span> $V_r$ = inizializzata a 0. Lato ricevitore la prima frame che mi aspetto di ricevere avrà frame 0. <b><u>Rappresenta il numero del prossimo frame che mi aspetto</u></b>.  
  <b><u>La variabile verrà incrementata quando il ricevente riceve il frame che si aspetta</u></b>. 
  Quando il ricevitore si vede arrivare una frame che non è quella che si aspetta, cancella quella che ha nel buffer e <b><u>valida il frame che ha ricevuto</u></b>. 

<b><u>Ho quindi un protocollo affidabile che lavora a livello 2</u></b> (quindi su un singolo link), in grado di trasmettere una sequenza di frame evitando : 
- <b><u>Corruzione</u></b> = ritrasmissione in caso di corruzione 
- <b><u>Ordine e non duplicazione dei frame</u></b>.

<span style=color:cyan>Elementi necessari</span> a costruire questo protocollo : 
- <b><u>Buffer</u></b> dove mettere la copia della frame che sto trasmettendo 
- <b><u>Clock</u></b> dimensionato in base al RTT
- <b><u>Sequencing</u></b>, per gestire le due variabili, lato trasmittente e lato ricevente. 
<h6 style=color:red>Si tratta di un protocollo inefficiente</h6>
