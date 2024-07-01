Consideriamo due nodi $A$ e $B$ collegati da un solo cavo
- <span style=color:yellow>Tempo di trasmissione</span> $t_x = {datiDaTrasmettere \over capacitaCanale}$  
	- dipende dalla capacita del canale e dalla velocità di immissione del mittente.
	- per tutto il tempo $t_x$ il driver sicuramente è occupato
	
- <span style=color:yellow>Tempo di propagazione</span> $t_p = {distanza \over velocita}$ 
	- è il tempo che un pacchetto impiega ad arrivare da A a B
	- <b><u>dipende unicamente dalle caratteristiche fisiche del canale su cui viaggiano i dati (lunghezza e materiale fisico)</u></b>
	- In $T_p$ consideriamo il tempo del singolo bit perche la capienza del messaggio totale è utilizzata nel calcolo di $t_xP_1$
   -    $t_p+t_x$ tempo che intercorre da quando il primo bit esce a quando l'ultimo bit arriva
	- $t_p$ aumenta molto fino a superare $t_x$ quando le distanze aumentano (comunicazioni satellitari, continentali)
	
- <span style=color:yellow>RTT o T Round Trip Time</span>: tempo dall'invio del primo frame all'arrivo dell'ultimo ACK. <b><u>Formula</u></b>  $T = T_x + T_xack+ T_p+ T_pack$
	- <span style=color:cyan>Txack</span>= è un tempo finito misurabile, tutta via L'ACK è molto piccolo, <b><u> il suo tempo di trasmissione è trascurabile</u></b>. 
	-  <span style=color:cyan>Tp</span> = <b><u>Tempo di propragazione dell'informazione su un canale</u></b>. 
     <b><u>Tale velocità dipende dal tipo di canale di comunicazione utilizzato e dalla sua lunghezza</u></b>.
	- <span style=color:cyan>Tpack</span> = <b><u>il tempo dovuto alla propragazione del segnale ack sul canale, non può essere trascurabile, in quanto dipende dalla lunghezza del canale</u></b> e non dalla lunghezza del pacchetto.  

	Formula finale = $T = T_x + 2T_P$.
	Si tratta del tempo di ritardo della trasmissione di un pacchetto ( il tempo che intercorre tra la trasmissione di un pacchetto e la ricezione dell'ack relativo)

<span style=color:red>N.B</span> = Anche se tutti i dati per il calcolo di T sono noti <b><u>è bene non rendere T uguale a quello calcolato, ma renderlo un pò più grande</u></b> (andrà quantificato il quanto )

 - <span style=color:yellow>Timer di trasmissione Tr</span> = Esso deve essere dimensionato opportunamente, perchè se l'ACK non raggiunge il mittente, la macchina a stati deve sbloccarsi. <b><u>La macchina a stati del mittente può sbloccarsi in due situazioni</u></b> : 
   - <b><u>Riceve il messaggio ACK </u></b>. 
   - <b><u>Riceve l'interrupt del timer di trasmissione</u></b>. 
	
	Le due situazioni sono esclusive, o riceve uno o l'altro ( non entrambi). 
	- Quando il timer lato mittente scade, lancia un interrupt, sbloccando la macchina stati del mittente. Si entra poi in una <span style=color:yellow>situazione di ricovero dell'errore</span>. <b><u>il mittente, inoltre, deve tenere una copia di tutto quello che trasmette per tutta la durata di Tr.</u></b> In modo da ritrasmettere il pacchetto in caso di errori.
	
	- Se invece arriva un ACK, il timer mittente viene resettato. 

	i<b><u>l timer, inoltre deve essere dimensionato correttamente</u></b> :  $T_r >  T = T_x + 2T_p$  
	 - Se setto Tr troppo grande sono inefficente. 
    - Se lo setto troppo piccolo sono sia inefficiente ( ritrasmetto pacchetti inutilmente) che ho il problema della copia. 
    
   <b><u>il problema della duplicazione lo ho quando decido di ritrasmettere Fx, ma L'ACK è ancora in viaggio, ho dunque sotto-dimensionato Tr</u></b>. 


*Esercizio*: 
![[Pasted image 20240329211009.png]]

Dati questi tempi ricaviamo l'[[Efficienza della rete]]
[[Dimensionamento clock]]
[[Jitter]]