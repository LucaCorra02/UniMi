<b><u>La ritrasmissione dei frame coinvolti nella collisione avviene dopo un tempo</u></b> $\tau$ casuale ottenuto con la tecnica `BEB Binary Exponenzial Backoff`
$$BEB = [0:2^i-1]*UT$$
con $i$ il <b><u>numero di collisioni</u></b> ($1<i<16$) della stazione e $UT$ unità di tempo. 
Con il BEB i frame potrebbero ancora collidere se viene generato lo stesso numero ma è probabilisticamente improbabile.

Ogni stazione ha un contatore per generare il numero casuale, in particolare per l'indice $i$ nel BEB
<span style=color:red>Svantaggi</span>: 
- <b><u>l'algoritmo dilata l'accesso</u></b> `NON garantendo la fairness`

<span style=color:green>Vantaggi</span>: 
 - è un `algoritmo adattivo al traffico percepito`, <b><u>in quanto dipende dal numero di collisioni</u></b> $i$

Osservando :$$U = {t_x \over t_x+2t_p * {1 \over A}}$$
Con: 
- $1 \over A$ = Numero medio di stazioni che deve aspettare prima di accedere
- $A= k*p * (1-p)^{kp}$
- $k$ numero di stazioni
- $p$ probabilità che quella stazione possa accedere al canale 