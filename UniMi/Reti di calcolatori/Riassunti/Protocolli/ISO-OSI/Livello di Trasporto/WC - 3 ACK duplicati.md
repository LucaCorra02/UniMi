Alla destinazione arrivano i segmenti MA fuori ordine. 
C'è una `congestione ma non è una situazione grave` in quanto la destinazione resta raggiungibile

Errore rilavato tramite <span style=color:yellow>Fast Retrasmit, dopo 3 ACK consecutivi fuori seqeunza ritrasmetto</span> : 

- $SST = \dfrac{W_c{size}}{2}$
  
- $WC = SST$ -> <b><u>La finestra parte dalla fase di congestion recovery, salto la fase di slow start</u></b>.

Data $W_C = k$ appena ricevo 3 ACK duplicati, dimezzo la finestra ($W_C = k/2$) e riprendo ad aumentare la finestra in modo lineare cioè con la fase di prevenzione della congestione, ottenendo cosi un `fast recovery`

![[Pasted image 20240720171116.png]]
