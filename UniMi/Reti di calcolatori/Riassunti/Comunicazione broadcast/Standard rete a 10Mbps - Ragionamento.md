<b><u>In una rete di grandi dimensione il tempo per rilevare la collisione non è un operazioni istantanea. Dipendono dal tempo di propagazione</u></b>. 

  Supponiamo che A e B stanno agli estremi della rete. 
  - Al tempo $T_0$ a fa carrier sense. Vendendo il canale libero inizia a trasmettere. 
  
  - Passa il tempo $T_0 + T_p$, a questo istante il primo bit del pacchetto inviato da A raggiunge la stazione remota B. 
  
  - <span style=color:red>Problema</span> = <b><u>La stazione B prima di trasmettere deve fare carrier sense. B ha tutto il tempo Tp per trovare la rete libera, quando invece non lo è, A sta trasmettendo (abbiamo così una collisione)</u></b>. 

    Per un tempo massimo a $2T_p$, <b><u>c'è un cono d'ombra in cui la stazione trasmittente non riesce a rilevare la collisione istantanea</u></b> ( i bit collisi devono tornare indietro alla stazione A) . A non riesce a capire se i bit corrotti sono i suoi o quelli appartenenti ad un altra stazione in quanto ha già smesso di trasmettere (trascorso il tempo TX). 

	![[Pasted image 20240712191132.png]]

<span style=color:green>Soluzione</span> = <b><u>In una rete Ethernet per garantire il colision detection</u></b>, devo garantire che il tempo di trasmissione di una stazione $T_x$, non finisca per l'intero tempo $2Tp$ . <b><u>La stazione trasmittente deve ancora trasmettere  quando riceve i bit corrotti, solo in questo modo riesce ad associare une errore alla sua trasmissione</u></b>. 

<b><u>Devo garantire</u></b> che $T_x$ >= $2T_p$ . <b><u>Vincolo del protocollo, altrimenti collision detection non funziona</u></b>.
il valore standard di $2 T_p$ è 51.2 us = <b><u>Tempo minimo di trasmissione in rete, almeno per 51.2 us la stazione deve trasmettere per rilevare uan collisione</u></b>, <span style=color:yellow>si tratta dell'unità base di ethernet</span>. 
<span style=color:cyan>Ricavo la dimensione delle frame minima e l'unità di tempo</span> per il <span style=color:yellow>BEB Binary Explonential BackOff</span>. 

- <b><u>Le frame trasmesse non possono essere più piccole del numero di bit</u></b> che serve per occupare un $T_x$ di 51.2 us : 
   - Dato che ho un clock di 10 Mbps
   - Con un Tx di 51.2 us
   - <b><u>Le frame di ethernet non possono essere più piccole di 512 bit o 64 byte.</u></b> Dovremmo dunque inserire un padding nel caso in cui i pacchetti fossere più piccoli di tali dimensione. 

- <b><u>Unità di tempo</u></b>. Suppongo $i = 2$, $BEB = [0,2^i-1]$. 
   - Devo trovare un tempo fra 0 e 3 unità di tempo 
   - Se l'unità di tempo è 51.2 us, l'intervallo che devo cercare con il random è fra $0$ e $[3 * 51.2us]$. 

TO FIX

1. Lunghezza massima del cavo: `2.5km`: SE una rete LAN deve essere maggiore di piu di 2.5km, ne creo un altra e le compongo
2. $t_x$ minimo: $51.2\mu s$

Problema:
Stazione $A$ trasmette ma il CS arriva dopo $t_p$ alla stazione B che, non vedendo il canale occupato, aveva iniziato a trasmettere cosi $A$, dopo aver finito di trasmettere, riceve dopo $t_p$ il frame corrotto di B
$A$ non è in grado di rilevare la collisione 
![[photo_5769355704325488864_y.jpg|400]]

Soluzione: 
Imporre di usare la propria porta di I/O di trasmissione almeno per $2 * T_p$
$$T_x \geq 2 * T_p$$
$A$ cosi sta ancora trasmettendo quando arriva il messaggio corrotto, rilevando cosi la collisione 

${25*10^2m \over 2*10^8} = 12.5 * 10^{-6}m/s = 12.5 \mu s$
$2 * T_p = 25 \mu s$
L'ente standardizzatore lo ha fatto diventare $51.2 \mu s$
Da ciò deriva che l'UT utilizzato nel BEB è di $51.2 \mu s$

3. Size minima del frame: 64Byte

Al massimo produce $512 bit -> 64 Byte$
Come min devo avere $64byte$, MA con DestinationA, SourceA, L e CRC ho solo 18 byte
Ho quindi un campo padding per arrivare ai 64byte: parte da 0 a 46 byte

Pero come min il livello 3 mette un header di 20byte, quindi avremmo gia 38byte