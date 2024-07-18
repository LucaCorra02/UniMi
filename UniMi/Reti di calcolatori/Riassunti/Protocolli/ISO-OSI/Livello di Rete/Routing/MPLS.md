<span style=color:cyan>Idea</span> = <b><u>La tabella di routing viene riempita in modo asincrono rispetto alle funzionalità del forwording dal router</u></b>. <b><u>La divisione tra dati e controllo rende la funzione di instradamento indipendente dalla singola macchina</u></b>.








Nella realizzazione delle aree0 si richiede l'efficienza dei router
Tecnica `MPLS Multi Protocol Label Switching` utilizzata nelle aree0 degli AS
Si ragiona attraverso le `etichette`, sovrapponendosi all'indirizzo IP, MA *le etichette valgono solo all'interno del singolo router*
MPLS agisce sulla parte del router che si occupa del forwarder, facendolo operare come uno switch
Trasformo il router in un apparato che fa forwarding SENZA curarsi del routing

LS continua ad essere a bordo del router, MA è funzionale a far funzionare il router come uno switch
Il router di gateway dell'area0 si chiamano `Area Border Router`: qui si compie la trasformazione da LS a MPLS

[[Router MPLS]]

L'header di MPLS contiene
- Label su 20bit
- CoS Class of Service su 3bit per selezionare la specifica coda 
- TTL time to leave su 8bit

Viene utilizzato un approccio CR `Constraint Routed` LSP in modo che ci sia un Network Management che riempie le tabelle utilizzate per fare label switching
In questo modo otteniamo aree0 il piu veloce possibili perche non si deve ispezionare l'IP MA viene fatto tutto piu velocemente come se fosse uno switch