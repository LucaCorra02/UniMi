Nel `router` abbiamo una `coda di ingresso` per ogni porta di I/O e una `coda di uscita` per ogni porta di I/O
I pacchetti vengono processati da un processo `Forwarder` e smistati nella specifica coda di uscita, scegliendo in base ad una `tabella di instradamento` permette di ruotare ogni pacchetto ad ogni altro network in Internet in base ad un indirizzo IP destinazione, indicando una porta di I/O
Il processo di routing che popola la tabella in modo asincrono rispetto al processo di Forwarding

<b><u>Come un pacchetto viene inviato</u></b> in una rete IP standard
1. Alla ricezione del pacchetto da una linea di input, il router legge <b><u>l'IP destinazione nell'header per determinare il NetID</u></b> utilizzando la maschera
2. Usa poi il <b><u>NetID per determinare la porta di uscita grazie alla tabella di instradamento</u></b>
3. Il campo <b><u>ToS nell'header viene passato al classificatore di pacchetti che determina la coda e le regole di scheduling da applicare al pacchetto</u></b>. Ciò determina la porta di uscita da utilizzare per mandare il pacchetto al prossimo hop.

Una regola di coda e scheduling vengono usate per ogni classe per assicurare che i requisiti di [[QoS]] vengano rispettati

Vediamo il router diviso in 2:
- `piano dati`
- `piano controllo` = Messaggi di controllo utilizzati per costruire e aggiornare la tabella di routing.

<b><u>Il processo di routing deve avere una certa conoscenza di tutta la rete in modo tale da costruirsi il cammino minimo</u></b> anche se nella tabella non troviamo tutto il percorso ma solo il successivo nodo da raggiungere per raggiungere l'IP destinazione
Per il cammino minimo come `metriche` utilizzeremo il `delay` e/o il `numero di hop`.

[[Architettura della rete]]

![[Pasted image 20231219132337.png|600]]