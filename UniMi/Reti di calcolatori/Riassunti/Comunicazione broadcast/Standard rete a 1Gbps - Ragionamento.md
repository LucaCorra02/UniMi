<b><u>MA tutto quello che abbiamo fatto finora è per una rete a 10Mbit, se ho una rete a 1Gbps</u></b>?

Sostituisco nella formula := $U = \dfrac{1}{1+2*\dfrac{BL}{CF}*e}$
Con : 
- B = banda, velocità 
- L = lunghezza 
- C = capacità del mezzo fisico 
- F = Lunghezza in bit

Per non diminuire troppo l'efficienza del canale, all'aumentare della banda (passo da mega a gigabit), posso : 
- <b><u>Diminuire la lunghezza del cavo</u></b>. 
- <b><u>Aumentare la grandezza delle frame</u></b>. 

A livello di Standard, con il Gigabit Ethernt, <b><u>le stazioni non possono distare più di 200 metri per tratta</u></b>. 
Suppongo 3 Stazioni $A,B,C$ = $400m*2$= $800m$ andata e ritorno.

$2T_p$ =  $\dfrac{8*10^2}{2*10^8}$ = $4*10^{-6}$ = $4us$. 

So che $T_x >= 2T_P$ , $T_x$ è almeno $4us$. Quanti bit riesco a trasmettere ? : 
- $Tp$ = $\dfrac{4us}{2}$ = $2us$
- $T_x= \dfrac{x}{10^9} >= 4us$ -> $x >= 4*10^{-6} * 10^9$ = $4*10^3$ = 4000 bit 
- $\dfrac{4000bit}{8}$ = $500 byte$

<b><u>La dimensione minima di una frame Gigabit ethernet è 512byte</u></b>.

<span style=color:cyan>Come lavora il Mac layer</span> = le frame non devono più avere una dimensione di 64byte, ma di 512 (non voglio andare a cambiare le schede). 
<b><u>il MAC è indipendente dal livello fisico sotto-stante, produce frame di 64byte.</u></b> <b><u>Sarà la porta di I/0 che in base alla tecnologia si occuperà di aggiungere del padding per costuire una frame da 512 byte</u></b>. 