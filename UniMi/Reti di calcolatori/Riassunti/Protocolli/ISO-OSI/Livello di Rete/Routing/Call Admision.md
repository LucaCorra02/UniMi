<b><u>Prima del classificatore, andiamo ad applicare sulla sorgente una funzione di </u></b><span style=color:yellow>Call Admision</span>, validazione delle regole dichiarate in ingresso da parte della sorgente del traffico.  

Misure importanti : 
- <span style=color:yellow>Tasso Medio</span> = <b><u>numero medio di pacchetti che possono essere accettati nell'unità di tempo</u></b>.
- <span style=color:yellow>Tasso di picco</span> =<b><u> Ammettiamo dei periodo di picco del traffico, non troppo rigidi</u></b>. 
- <span style=color:yellow>Burst size</span> =  <b><u>Ammetto dei periodi in cui il traffico non viene erogato dalla sorgente in modo uniforme, specificandone durata e picco</u></b>.

La regolazione del flusso di ingresso avviene tramite un <span style=color:yellow>Token Bucket</span> = <b><u>Generà un Token con Rate R</u></b>.
- Ogni Token viene messo nel Bucket. 
- Dal Bucket esce un Token alla volta 
- In entrata al Bucket abbiamo una coda di ingresso. <b><u>I pacchetti aspettano che ci sia un token disponibile da consumare, per poter spedire un pacchetto</u></b>.
- il pachetto viene messo in rete e raggiungerà un classificatore.

<b><u>Ogni unità di tempo (specificata da R), vien generato un token.</u></b>
<b><u>Un Bucket può contenere al massimo B token (Dove B è la dimensione del burst )</u></b>. 
Ammetto al massimo che nell'unità di tempo ci siano x pacchetti, spediti con un tasso che dipende da R. In caso di traffico burst andrei a consumare tutti i token nel bucket. 
<b><u>Vado a garantire che in ingresso non ci siano più pacchetti di quanti stabiliti nel contratto</u></b>.



Utilizzato per `garantire i requisiti di banda, delay e Jitter`
Ad ogni flusso viene associato un contenitore, `bucket di token` che vengono immessi ad un rate determinato dalla larghezza di banda richiesta

La dimensione del bucket è la stessa del massimo spazio della coda
In questo modo SE ci sono sufficienti token, il pacchetto è messo in coda e il corrispondente numero di token viene prelevato mentre SE non ci sono abbastanza token, il pacchetto viene scartato (perché sto andando ad un Rate superiore)

La coda che va in overflow eventualmente sarà quella di input