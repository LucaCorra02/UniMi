La regolazione del flusso di ingresso avviene tramite un <span style=color:yellow>Token Bucket</span>, utilizzato per `garantire i requisiti di banda, delay e Jitter`.

<b><u>Ad ogni flusso viene associato un contenitore</u></b>, `bucket di token` che vengono <b><u>immessi ad un rate determinato dalla larghezza di banda richiesta</u></b>. 

Ogni Token Bucket,  <b><u>Generà un Token con Rate R</u></b>.
- Ogni Token viene messo nel Bucket. 
- Dal Bucket esce un Token alla volta 
- In entrata al Bucket abbiamo una coda di ingresso. <b><u>I pacchetti aspettano che ci sia un token disponibile da consumare, per poter spedire un pacchetto</u></b>.
- il pachetto viene messo in rete e raggiungerà un classificatore.








La dimensione del bucket è la stessa del massimo spazio della coda
In questo modo SE ci sono sufficienti token, il pacchetto è messo in coda e il corrispondente numero di token viene prelevato mentre SE non ci sono abbastanza token, il pacchetto viene scartato (perché sto andando ad un Rate superiore)

La coda che va in overflow eventualmente sarà quella di input