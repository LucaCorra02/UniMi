Situazione: `produttore lento e consumatore veloce`. Problema opposto rispetto al problema di [[Algoritmo di Clark]]:

<b><u>Lato destinazione è una variazione del delayed acknowledgement, aspetto che SOLO un segmento riceva il relativo ACK. Quando l'ACK arriva, tutti i caratteri nel buffer, vengono inviati in un unico segmento</u></b>.

<b><u>Lato trasmettitore accumulo le informazioni che l'utente vuole spedire (essendo lento)</u></b>, esse saranno accumulato e spedite nel segmento successivo. 

<b><u>Non ho un timer lato trasmettitore, misuro il tempo che intercorre tra la send e l'ack associato e lo uso come timer incorporato per la trasmissione del segmento successivo, si tratta di uno</u></b> <span style=color:yellow>schema di self-clocking</span>. Ogni tempo $RTT$ invio un segmento con più byte accumulati. 

*ES*
Lato sender :
- Produce 1Byte di dati ogni 20 msec. 
- link avente banda di 100 Kbps 
- $T_p$ = 100 msec. 

Primo segmento 1Byte+20Byte = 21Byte
$t_x = \frac{21*8}{100000} = 1.68*10^{-3}$
$t_p= 100msec$
ack arriva dopo $1.68+2* 100 = 201.68msec$
In questo tempo sono stati prodotti $201.68/20 = 10$ B

Secondo segmento: 10B+20B = 30B
$t_x = \frac {30*8}{100000} = 2.4*10^{-3}$
ack arriva dopo $2.4 + 2*100 = 202.4msec$
In questo tempo sono stati prodotti $202.4/20 = 10B$

Terzo segmento (e tutti i successivi): 10B+20B = 30B