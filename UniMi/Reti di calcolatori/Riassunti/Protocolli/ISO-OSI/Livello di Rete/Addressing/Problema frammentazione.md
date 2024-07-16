<b><u>SE la dimensione del pacchetto è maggiore della dimensione massima del frame </u></b>(`MTU Maximum Transmission Unit`), <b><u>è necessario dividere il payload in un numero di pacchetto con dimensione ridotta</u></b>, i frammenti. Abbiamo detto che la massima dimensione di un pacchetto IP è $64K$, una LAN con CSMA-CD gestite frame da $1500byte$, dobbiamo frammentare l'unità dati di livello 3. 










Nel caso di perdita del segmento, l'IP se ne accorge grazie al TCP che ritrasmette i dati MA rimanda tutto, non solo quello che manca perché è il livello 3 che sa quale non è arrivato

[[Esempio Frammentazione]]


