<b><u>SE la dimensione del pacchetto è maggiore della dimensione massima del frame </u></b>(`MTU Maximum Transmission Unit`), <b><u>è necessario dividere il payload in un numero di pacchetto con dimensione ridotta</u></b>, i frammenti. Abbiamo detto che la massima dimensione di un pacchetto IP è $64K$, una LAN con CSMA-CD gestite frame da $1500byte$, dobbiamo frammentare l'unità dati di livello 3. 

Campo <span style=color:yellow>Campo Fraggment Offsett</span> =<b><u> Frammenta l'unità dati di livello 3. Dato che può contare fino a</u></b> $2^{13}$, <b><u>conta gli ottetti (blocchi di 8byte) dell'unità dati di livello 3</u></b>, la quale può essere grande al massimo $2^{16}$. 
<b><u>Andremo dunque a frammentare in pacchetti con dimensione multipla di 8</u></b>.

<b><u>La frammentazione e l'assembling a livello IP vengono eseguite solamente dagli end-system, in modo da non andare a sovraccaricare la rete</u></b>. 

[[Esempio Frammentazione]]


