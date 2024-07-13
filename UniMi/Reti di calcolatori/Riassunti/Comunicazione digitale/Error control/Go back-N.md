 <b><u>Se ho un errore torno indietro all'ultima sequenza coretta, ipotizzando che sia N</u></b>.
  Mi basta un buffer lato ricevente.  <b><u>Se mando N frame e il K-esimo è sbagliato</u></b>, devo tornare indietro all'ultima sequenza corretta. 
  
  <span style=color:red>Altamente inefficiente</span> = <b><u>Abbiamo un buffer di ricezione grande 1</u></b>, qualsiasi sia la dimensione della finestra viene accettata solo una frame di quella sequenza, <b><u>essa verrà mandata al livello superiore se e solo se è in sequenza</u></b>. 

*Esempio: *
          ![[Pasted image 20240713181748.png]]

- i(N) arriva giusta, parte l'ACK di I(N)

- i(N+1) viene persa, ma vengono spedite I(N+2), I(N+3), i(N+4). Tutte queste frame vengono inviate correttamente ma <b><u>non vengono passati al livello superiore ma scartati</u></b>.

- Al posto di $NACK N-1$, con la sequenza cumulativa, avrei dovuto inviare ACK N, ovvero il ricevitore ha ricevuto i pacchetti corretti fino a quello di sequenza N. 
