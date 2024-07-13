Opera in modalità duplex
Il mittente `invia I-frame in modo continuativo` <b><u>senza aspettare il ritorno di un ACK. Il mittente conserverà quindi una copia dell'I-frame trasmesso in un lista di ritrasmissione</u></b>. 

<b><u>Il destinatario</u></b>, anche in questo caso, invierà un ACK per ogni frame ricevuto correttamente, <b><u>conservandolo in una lista di ricezione</u></b>. Anche in questo caso <b><u>sarà necessario avere nei frame e negli ACK un numero di sequenza identificativo</u></b>.
Alla ricezione del ACK, viene rimosso dalla lista il corrispettivo frame

- Il mittente conserva una variabile di sequenza $V(S)$ che indica <b><u>il frame da trasmettere: viene incrementato quando riceve l'ACK</u></b>.
- Il destinatario invece conserva una variabile di sequenza $V(R)$ che <b><u>indica il prossimo frame che sta aspettando</u></b>: viene incrementato quando riceve il frame che stava aspettando, senza errori

<b><u>Nei protocolli a finestra esistono due modi per gestire la ritrasmissione delle frame errate</u></b>: 

- [[Go back-N]].
  
-  [[Selective repeat]] = Una possibile soluzione per rendere più efficiente il protocollo $Go Back N$ è quello di <b><u>rendere il buffer di ricezione grande quanto la finestra di trasmissione</u></b>, in questo modo se ricevo in disordine le frame (devono essere corrette) le tengo nel buffer, senza passarle al livello superiore. <b><u>Quantd ho riempito i buchi della sequenza mando un</u></b> $ACK$ <b><u>comulativo, validando tutta la sequenza della finestra</u></b>. <span style=color:green>soluzione più efficiente</span>. 

<b><u>i due protocolli differiscono per la gestione del buffer di ricezione</u></b>
Il TCP, lato trasmettitore, usa Go back-N mentre lato ricevitore usa Selective repeat