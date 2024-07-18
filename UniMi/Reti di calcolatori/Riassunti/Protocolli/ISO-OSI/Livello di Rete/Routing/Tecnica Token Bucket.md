La regolazione del flusso di ingresso avviene tramite un <span style=color:yellow>Token Bucket</span>, utilizzato per `garantire i requisiti di banda, delay e Jitter`.

<b><u>Ad ogni flusso viene associato un contenitore</u></b>, `bucket di token` che vengono <b><u>immessi ad un rate determinato dalla larghezza di banda richiesta</u></b>. 

Ogni Token Bucket,  <b><u>Generà un Token con Rate R</u></b>.
- Ogni Token viene messo nel Bucket. 
- Dal Bucket esce un Token alla volta 
- In entrata al Bucket abbiamo una coda di ingresso. <b><u>I pacchetti aspettano che ci sia un token disponibile da consumare, per poter spedire un pacchetto</u></b>.
- il pachetto viene messo in rete e raggiungerà un classificatore.

<b><u>Ogni unità di tempo (specificata da R), viene generato un token.</u></b>
<b><u>Un Bucket può contenere al massimo B token (Dove B è la grandezza massima della coda )</u></b> : 

- SE ci sono sufficienti token, il pacchetto è messo in coda e il corrispondente numero di token viene prelevato mentre 
- SE non ci sono abbastanza token, il pacchetto viene scartato (perché sto andando ad un Rate superiore)








<b><u>Vado a garantire che in ingresso non ci siano più pacchetti di quanti stabiliti nel contratto</u></b>.
