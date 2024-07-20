Variabile $W_C$ (`Finestra di congestione`) <b><u>viene aggiunta solo nella sorgente</u></b>
Caso rete senza congestione :
1. <span style=color:cyan>Slow Start</span>: partendo da $W_C=1$, <b><u>ogni volta che ricevo un ACK, raddoppio la </u></b>$W_C$, risultando in un aumento veloce della finestra (Slow = cauto) <b><u>fino ad una soglia, la</u></b> <span style=color:yellow>SST Slow Start Threshold</span>. 
2. Fase di <span style=color:cyan>Congestion advoidence</span> : al raggiungimento della `SST`, aumento $W_C$ di 1 (MSS) ogni $W_C$ ACK ricevuti 
3. Continuo ad aumentare $W_C$ fino a raggiungere una fase di crociera in cui non lo aumento piu 

Numero di byte che posso trasmettere è dato dal $min(W_C, W_S)$

Tipi di congestione:
- [[WC - RTO expires]] 
- [[WC - 3 ACK duplicati]]

[[Explicit Congestion Notification]]
