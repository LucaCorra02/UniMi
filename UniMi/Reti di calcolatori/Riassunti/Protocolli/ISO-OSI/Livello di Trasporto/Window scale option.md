<span style=color:cyan>Buffer di ricezione</span> = <b><u>Ad ogni connessione proveniente da un client è associato un buffer di ricezione, grande k byte</u></b>. 

La dimensione del <span style=color:yellow>Buffer di ricezione </span> è importante per i seguenti motivi : 
- Ad <b><u>ogni client deve essere nota</u></b>, in modo che esso non possa mandare una quantità di dati che non superi la dimensione del buffer.

- <b><u>Deve essere aggiornata dinamicamente</u></b> = il buffer è situato sull'interfaccia tra il livello 4 e il livello 7







Il campo window size nell'header è di 16 bit, permettendo una dimensione massima di $2^{16}$.
Tuttavia per avere una dimensione maggiore, si utilizza la window scale option (inclusa nel segmento SYN)


Formato

| Campo       | Dimensione | Descrizione                                                                                                                                |
| ----------- | ---------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| NOP option  | 8 bit      | con kind=1, è usato come padding per raggiungere i 32 byte                                                                                 |
| kind = 3    |            |                                                                                                                                            |
| length = 3  |            |                                                                                                                                            |
| Shift count |            | il window size è ottenuto moltiplicando per $2^n$ con $n$ il valore nello shift count. es shift count = 14 (il suo max), $65 535 * 2^{14}$ |