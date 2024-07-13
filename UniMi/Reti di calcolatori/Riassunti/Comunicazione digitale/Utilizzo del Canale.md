Dobbiamo andare ad introdurre il termine <span style=color:yellow>Utilizzo del canale</span> = <b><u>si tratta di una metrica che indica quanto il mio protocollo è efficiente nell'utilizzare la capacità del canale fisico</u></b>. *Se ho comprato un canale da 1mbps, mi aspetto che il protocollo sia in grado di occupare con dei frame successivi il 100% della capacità*

L'utilizzo è dunque definito come il rapporto tra il tempo reale per trasmettere una frame (tempo di trasmissione) e il tempo di RTT (tempo con delay aggiuntivo) : 
<span style=color:yellow>Utilizzo canale o U</span> = $U= \dfrac{T_x}{Tx+2Tp}$  :
 - U tende a 1 = Buon utilizzo del canale
 - U tende a 0 = Pessimo utilizzo del canale
<b><u>Più grande è</u></b> $T_p$ <b><u>più la percentuale di utilizzo del canale è bassa</u></b>

<b><u>Mandando un frame e aspettando l'arrivo dell'ack per un tempo al più come</u></b> $T$, non invio frame in sequenza (una dietro l'altra come un servizio *Best effort*).  

il nostro protocollo si complica, in quanto per avere un utilizzo del canale del 100% (sempre occupato a trasmettere), non vorremo aspettare ogni volta il relativo ack. <b><u>Devo ammettere nel protocollo la trasmissione di più frame uno dietro l'altra e non vincolare la trasmissione della singola frame nell'attesa del ack per quella frame.</u></b> Voglio avere libertà di mandare frame una dietro l'altra alla capacità del mio trasmettitore, gli ack arriveranno poi di conseguenza. Vado dunque a realizzare un <span style=color:yellow>protocollo affidabile a finestra</span>.

<span style=color:cyan>Perchè mandare più frame aumenta l'utilizzo del canale</span> : 
- Suppongo di voler spedire $1000 bit$
- Canale da $1 Mbps$ di rame
- Cavo lungo $2Km$

- $T_x= \dfrac{10^3}{10^6}$ = $10^{-3}$  = $1 ms$
- $T_p$ = $\dfrac{2*10^3}{2*10^8}$ = $10us$
- $T = 1ms + 2 *10us$

  Calcolo l'utilizzo del canale (quanto la nostra macchina è capace di utilizzare il canale) :
  $U = \dfrac{T_x}{T}$ = $\dfrac{1ms}{1,02 ms}$ = Tende a 98%

*Altro esercizio*
- $1000 bit$ 
- $1Mbps$
- $200Km$
- $T_x = 1ms$
- $T_p = \dfrac{2*10^5}{2*10^8}$ = $10^{-3}$ = 1ms
- U = $\dfrac{1}{3}$ = 30%

  Nei 2/3 in cui il canale non è occupato, potrei mandare 2 frame anzichè non inviare nulla. 