
<b><u>Grandezza header</u></b>:= `20 byte`. Stessa dimensione dell'header di IPV4. 

<b><u>Lato ricezione come faccio a distinguere un segmento di un associazione da un altra</u></b>, dato che ho solo il numero di porta? Nell'header non è possibile farlo, nasce lo <span style=color:yellow>pseudo header</span>. 

| Campo                 | Dimensione | Descrizione                                                                                                                                                                                                                      |
| --------------------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Porta sorgente        | 16 bit     | scelta dalla sorgente stessa                                                                                                                                                                                                     |
| Porta destinazione    | 16 bit     | porta nota                                                                                                                                                                                                                       |
| Sequence number (SEQ) | 32 bit     | <b><u>numero di sequenza del segmento</u></b>, utilizzato per la ritrasmissione essendo TCP un protocollo affidabile. <br><b><u>il sequence number non serve per numerare frame o segmenti ma numera byte</u></b>                |
| ACK number            | 32 bit     | <b><u>Identifica il byte successivo che mi aspetto</u></b> (es 10 vuol dire che ho mandato correttamente i primi 9 quindi mi aspetto il 10)                                                                                      |
| Flag bits             | 6 bit      | Elenco qui di seguito                                                                                                                                                                                                            |
| 1. URG flag           | 1 bit      | Se il bit è attivo, il campo <span style=color:cyan>Urgent Pointer</span>, contiene un <b><u>Puntatore ad una porzione nella sequenza di byte contenente dei comandi che devono essere mandati subito alla destinazione</u></b>. |
| 2. ACK flag           | 1 bit      | Se attivo, indica che il <b><u>segmento contiene un segnale di ACK di qualche tipo</u></b>.                                                                                                                                      |
| 3. PSH flag           | 1 bit      | Indica che la sequenza di byte contenuta nel segmento deve essere spinta nelle code di output per essere trasferita più velocemente. il servizio prende il nome di <span style=color:yellow>extelited</span>.                    |
| 4. RST flag           | 1 bit      | Bit che permette di resettare la connessione.                                                                                                                                                                                    |
| 5. SYN flag           | 1 bit      | Se attivo, indica che il <b><u>segmento è di apertura di connessione</u></b>.                                                                                                                                                    |
| 6. FIN flag           | 1 bit      | Se attivo, <b><u>indica che il segmento è di fine connessione</u></b>.                                                                                                                                                           |
| Window size           |            | <b><u>è il campo che permette di concordare tra client e al server la dimensione</u></b> del <span style=color:yellow>Buffer di ricezione </span><b><u> in fase di apertura della connessione</u></b>.                           |
| Checksum              |            | per verificare se il segmento è corretto                                                                                                                                                                                         |
| Urgent pointer        | 16 bit     | usato un tempo per mandare CTRL C prima del comando che voglio annullare, è l offset dei dati dove iniziano i dati urgent                                                                                                        |
| N [[TCP - Option]]    | $N*32bit$  |                                                                                                                                                                                                                                  |
<h5 style=color:cyan>Pseudo Header</h5>
<b><u>Lato ricezione come faccio a distinguere un segmento di un associazione da un altra</u></b>, dato che ho solo il numero di porta? Nell'header non è possibile farlo, nasce lo <span style=color:yellow>pseudo header</span>, contenente :

 - <span style=color:cyan>Ip sorgente</span>
- <span style=color:cyan>ip destinazione</span>
- <span style=color:cyan>protocol selector</span> 
- <span style=color:cyan>segment lenght</span>

<b><u>Il checksum non viene calcolato solo sul TCP ma anche sullo pseudo header</u></b>:
- <b><u>header vero</u></b> 
- <b><u>header virtuale</u></b> 
