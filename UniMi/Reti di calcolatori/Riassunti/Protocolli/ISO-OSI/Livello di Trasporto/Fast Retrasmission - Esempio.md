<span style=color:yellow>Fast Retransmit</span> =  è un <b><u>meccanismo che si attiva quando il mittente riceve tre duplicati dello stesso (ACK)</u></b>. In TCP, un ACK duplicato indica che un pacchetto è stato ricevuto, ma altri pacchetti precedenti potrebbero essere stati persi. <b><u>Se il mittente riceve tre duplicati dello stesso ACK, presume che il pacchetto successivo nell'ordine sia stato perso e lo ritrasmette immediatamente senza aspettare il timeout</u></b>.

- <span style=color:green>Vantaggi</span> := <b><u>Riduce il tempo di attesa per il timeout per la ritrasmissione</u></b> (Non devo aspettare che $RTO$ scade per la ritrasmissione), migliorando l'efficienza della rete.
    
- <span style=color:red>Limitazioni</span>:= <b><u>Non funziona bene in caso di perdite multiple di pacchetti, poiché non fornisce informazioni dettagliate su quali pacchetti sono stati persi</u></b>.

Assumiamo ACK immediato. 

- Destinatario risponde con ACK alla sorgente, questa aggiorna il proprio Vs con `X+500`. 
- Sorgente manda un secondo e un terzo messaggio, supponiamo che il secondo venga perso.
- Il SEQ è diverso da quello che si aspetta il ricevente (riceve il terzo messaggio e non il terzo), quindi lo conservo nel buffer di TCP SENZA passarlo al buffer dell'applicazione. NON posso rispondere con un `ACK = X+1000`, quindi rispondo con un`ACK = X+500` ACK perche è quello che mi aspetto
- Lato mittente, si aspettava un `ACK = X+1500`. <b><u>il segmento 2 non viene rinviato subito in quanto potrebbe arrivare in ritardo alla destinazione</u></b>. Nel caso non arrivi però, viene ignorato il problema e vengono inviati altri segmenti SENZA togliere pero dal buffer il 2o e 3o dal buffer perche non sono arrivati in ordine. 

Se altri messaggi arrivano al ricevente, verrà inviato lo stesso ACK errato precedente, quindi viene ritrasmesso il segmento X+500 (Fast Retrasmission) che stavolta arriva al ricevente.
Il ricevente ha quindi nel buffer i segmenti in "ordine", mandando un ACK cumulativo. La sorgente quando riceve l ACK cumulativo, ripulisce il proprio buffer 