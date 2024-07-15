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
Suppongo 3 Stazioni $A,B,C$ = $400m*2$= $$








<b><u>Cambia la dimensione minima del pacchetto</u></b>  :
- $T_x$ Cambia, in particolare a 512 ns 
- $T_p$ non è cambiato e quindi il protocollo non rileva le collisioni

Nello standard sarà necessario cambiare la dimensione minima del frame, in particolare sarebbero necessari 50k bit, diminuendo U moltissimo (es segnale di ACK). 

Inizialmente la lunghezza massima del cavo era stata proposta a 15m ma poi era stata rigettata, optando per 200m.
$$2*T_p = {10^2 \over {2*10^8}} = 0.5 \micro s$800m$ andata e ritorno 

Standard
- 200m di lunghezza del cavo massima massimo -> 2$t_p$ su 800m -> 2$t_p$ = 4 ms
- taglie minime di frame a 512Byte (da 64bytes). Ho un padding duplice: uno che lo fa fino a 64byte ma poi quando un frame con meno di 512 bytes viene trasmesso, la MAC interface del mittente gli aggiungerà un padding per raggiungere la grandezza minima 