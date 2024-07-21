Variabile $W_C$ (`Finestra di congestione`) <b><u>viene aggiunta solo nella sorgente</u></b>
Caso rete senza congestione :
1. <span style=color:cyan>Slow Start</span>: partendo da $W_C=1*MSS$, <b><u>ogni volta che ricevo un ACK, aumento  di  1 MSS </u></b>$W_C$ , $W_c$ = $W_c{old}*1*MSS$  risultando in un aumento veloce della finestra (Slow = cauto) <b><u>fino ad una soglia, la</u></b> <span style=color:yellow>SST Slow Start Threshold</span>. 
2. Fase di <span style=color:cyan>Congestion advoidence</span> : In questa fase, <b><u> Dal valore di TrashHold, fino al</u></b> valore <span style=color:yellow>massimo ovvero la dimensione del buffer di ricezione</span><b><u> ho una crescita lineare </u></b> di $W_c$.
	La $W_c$ <b><u>cresce di un segmento (MMS) ogni finestra ricevuta correttamente</u></b>, ogni $W_C$ ACK ricevuti. 
   Crescita : $\dfrac{1}{W_{c}size}$  
3. Continuo ad aumentare $W_C$ fino a raggiungere una fase di crociera in cui non lo aumento piu oppure fino al raggiungimento della dimensione del <b><u>buffer di ricezione</u></b>

<b><u>Numero di byte che posso trasmettere è dato da</u></b>l $min(W_C, W_S)$

![[Pasted image 20240720165947.png]]


Tipi di congestione:
- [[WC - RTO expires]] 
- [[WC - 3 ACK duplicati]]

[[Explicit Congestion Notification]]
