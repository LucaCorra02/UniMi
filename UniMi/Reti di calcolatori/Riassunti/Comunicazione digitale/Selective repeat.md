Una possibile soluzione per rendere più efficiente il protocollo $Go Back N$ è quello di <b><u>rendere il buffer di ricezione grande quanto la finestra di trasmissione</u></b>, in questo modo<b><u> se ricevo in disordine le frame (devono essere corrette) le tengo nel buffer, senza passarle al livello superiore</u></b>. <b><u>Quantd ho riempito i buchi della sequenza mando un</u></b> $ACK$ <b><u>comulativo, validando tutta la sequenza della finestra</u></b>. <span style=color:green>soluzione più efficiente</span>. 

*Esempio*
        ![[Pasted image 20240713183123.png]]

 - $I(N)$ viene ricevuta correttamente 
 
 - $I(N+1)$ viene perso. Quando il ricevente riceve un frame fuori sequenza, ovvero $I(N+2)$, il ricevente conferma con un $ACK$ comulativo di aver ricevuto la sequenza correttamente fino al frame con numero $I(N)$. 
 
 - il trasmettitore sa di aver spedito l'intera finestra, tutta via si vede arrivare un $ACK ->I(N)$. L'ACK comulativo tutta via permette al trasmettitore di sapere che qualche pacchetto della sequenza è arrivato coretto a destinazione. <b><u>il trasmettitore inizia a ritrasmettere da N+1</u></b>. 

- Dopo che il ricevente ottiene $I(N+1)$, dato che la sequenza è completa, il ricevitore manda un $ACK->I(N+4)$.
  Nel caso di perdita di un $ACK$ con il selective e ACK comulativi non ho bisogno di ritrasmettere la frame allo scadere del timer. 






