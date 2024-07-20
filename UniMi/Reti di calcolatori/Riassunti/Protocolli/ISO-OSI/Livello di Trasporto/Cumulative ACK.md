Per ottimizzare la trasmissione <b><u>possono essere inviati piu segmenti e lato ricezione, non viene inviato subito ACK</u></b> in modo che, quando mi arrivi il secondo segmento (in ordine), il ricevente mandi un singolo ACK con SEQ dato dalla somma dei due (`Cumulative ACK`)

Due osservazioni da fare : 
- <b><u>Lato ricevente stiamo lavorando come se fossimo in</u></b> <span style=color:yellow>Selective repeat</span>. Ovvero i segmenti fuori sequenza non vengono scartati, successivamente quando si completa la sequenza si utilizza un ACK cumulativo. 

- <b><u>Lato trasmissione stiamo lavorando in </u></b> <span style=color:yellow>go back n</span>. <b><u>Quando scade il timer torna indietro e ritrasmette il segmento perso fino a quando non si sincronizza con il ricevitore</u></b>. 

<span style=color:red>NON sempre il cumulative ACK è possibile</span>. 