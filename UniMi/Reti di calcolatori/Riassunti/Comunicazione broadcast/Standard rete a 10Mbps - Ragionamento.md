<b><u>In una rete di grandi dimensione il tempo per rilevare la collisione non è un operazioni istantanea. Dipendono dal tempo di propagazione</u></b>. 

  Supponiamo che A e B stanno agli estremi della rete. 
  - Al tempo $T_0$ a fa carrier sense. Vendendo il canale libero inizia a trasmettere. 
  
  - Passa il tempo $T_0 + T_p$, a questo istante il primo bit del pacchetto inviato da A raggiunge la stazione remota B. 
  
  - <span style=color:red>Problema</span> = <b><u>La stazione B prima di trasmettere deve fare carrier sense. B ha tutto il tempo Tp per trovare la rete libera, quando invece non lo è, A sta trasmettendo (abbiamo così una collisione)</u></b>. 

    Per un tempo massimo a $2T_p$, <b><u>c'è un cono d'ombra in cui la stazione trasmittente non riesce a rilevare la collisione istantanea</u></b> ( i bit collisi devono tornare indietro alla stazione A) . A non riesce a capire se i bit corrotti sono i suoi o quelli appartenenti ad un altra stazione in quanto ha già smesso di trasmettere (trascorso il tempo TX). 

	![[Pasted image 20240712191132.png]]

<span style=color:green>Soluzione</span> = <b><u>In una rete Ethernet per garantire il colision detection</u></b>, devo garantire che il tempo di trasmissione di una stazione $T_x$, non finisca per l'intero tempo $2Tp$ . <b><u>La stazione trasmittente deve ancora trasmettere  quando riceve i bit corrotti, solo in questo modo riesce ad associare une errore alla sua trasmissione</u></b>. 

<b><u>Devo garantire</u></b> che $T_x$ >= $2T_p$ . <b><u>Vincolo del protocollo, altrimenti collision detection non funziona</u></b>.


<h5 style=color:cyan>Standard</h5> 
il valore standard di $2 T_p$ è $51.2 us$ = <b><u>Tempo minimo di trasmissione in rete, almeno per 51.2 us la stazione deve trasmettere per rilevare uan collisione</u></b>, <span style=color:yellow>si tratta dell'unità base di ethernet</span>. 
<span style=color:cyan>Ricavo la dimensione delle frame minima e l'unità di tempo</span> per il <span style=color:yellow>BEB Binary Explonential BackOff</span>. 

- <b><u>Le frame trasmesse non possono essere più piccole del numero di bit</u></b> che serve per occupare un $T_x$ di $51.2 us$ : 
   - Dato che ho un clock di $10 Mbps$
   - Con un $T_x$ di $51.2 us$
   - <b><u>Le frame di ethernet non possono essere più piccole di 512 bit o 64 byte.</u></b> Dovremmo dunque inserire un padding nel caso in cui i pacchetti fossere più piccoli di tali dimensione. 

- <b><u>Unità di tempo</u></b>. Suppongo $i = 2$, $BEB = [0,2^i-1]$. 
   - Devo trovare un tempo fra 0 e 3 unità di tempo 
   - Se l'unità di tempo è 51.2 us, l'intervallo che devo cercare con il random è fra $0$ e $[3 * 51.2us]$. 
