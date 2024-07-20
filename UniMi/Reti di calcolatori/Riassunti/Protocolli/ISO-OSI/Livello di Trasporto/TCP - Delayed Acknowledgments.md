<span style=color:red>Problema</span> = <b><u>Abbiamo un produttore molto lento e un consumatore veloce</u></b>. La situazione è critica in quanto abbiamo 1 carattere di payload e 20 byte di header. <b><u>Rischiamo di mandare in rete un sacco di segmenti con basso contenuto informativo</u></b>, la ridondanza maggiore è dovuta all'header. 


<span style=color:green>Soluzioni</span> = Per ridurre il numero di segmenti inviati, <b><u>TCP NON ritorna immediatamente l'ACK (lato trasmettitore) quando riceve un segmento senza errori MA aspetta, tipicamente</u></b> $200ms$ (<span style=color:yellow>piggybacking timer</span>), per vedere se ci sono dati che vengono messi nel buffer send: `Delayed Acknowledgments`. 

<b><u>Alla ricezione del primo carattere aspetto 200ms per riempire un segmento di ritorno per evitare di inviare segmenti multipli</u></b>. 
<b><u>Il segmento cumulativo raggiungerà il trasmettitore in un tempo pari</u></b> a $RTT_{real} + Timer$

<b><u>Lato trasmettitore accumulo le informazioni che l'utente vuole spedire (essendo lento)</u></b>, esse saranno accumulato e spedite nel segmento successivo. 

<b><u>Non ho un timer lato trasmettitore</u></b> <span style=color:yellow>schema di self-clocking</span>. 

Quindi il segmento avra $PSH=1$, $ACK=1$, $ACK=X+1$, $SEQ=Y$, Data='d'

MA viene aggiunto cosi del delay aggiuntivo in cui si aspetta che l applicazione debba inviare qualcosa
Soluzione: [[TCP - Algoritmo di Nagle]]

*Esempio*



