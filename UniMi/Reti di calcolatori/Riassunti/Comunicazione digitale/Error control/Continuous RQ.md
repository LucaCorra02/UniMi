Opera in modalità duplex
Il mittente `invia I-frame in modo continuativo` <b><u>senza aspettare il ritorno di un ACK. Il mittente conserverà quindi una copia dell'I-frame trasmesso in un lista di ritrasmissione</u></b>. 

<b><u>Il destinatario</u></b>, anche in questo caso, invierà un ACK per ogni frame ricevuto correttamente, <b><u>conservandolo in una lista di ricezione</u></b>. Anche in questo caso <b><u>sarà necessario avere nei frame e negli ACK un numero di sequenza identificativo</u></b>.
Alla ricezione del ACK, viene rimosso dalla lista il corrispettivo frame

- Il mittente conserva una variabile di sequenza $V(S)$ che indica <b><u>il frame da trasmettere: viene incrementato quando riceve l'ACK</u></b>.
- Il destinatario invece conserva una variabile di sequenza $V(R)$ che <b><u>indica il prossimo frame che sta aspettando</u></b>: viene incrementato quando riceve il frame che stava aspettando, senza errori

Strategie di ritrasmissione:
- [[Selective repeat]]
- [[Go back-N]]

Il TCP, lato trasmettitore, usa Go back-N mentre lato ricevitore usa Selective repeat