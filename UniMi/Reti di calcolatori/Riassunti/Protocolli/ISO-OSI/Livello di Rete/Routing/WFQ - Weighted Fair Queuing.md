Per questa tecnica é necessario un dispositivo che faccia look-up del type of service, esso prende il nome di  <span style=color:yellow>Classifier</span>, <b><u>leggendo i TOS bit smista i pacchetti nelle code opportune in funzione del diverso livello di priorità</u></b>.
 
<b><u>La fairness viene ottenuta assegnando un peso ad ogni coda, il tempo di servizio assegnato ad ogni coda è in funzione del peso di tutte le code</u></b>.

Per ogni coda $i$ abbiamo un tempo di servizio che è = $\dfrac{W_i}{Somma_ {pesi}} * rate$ o $pesoCoda / totPesi * Rate$. 
<span style=color:cyan>Non discrimina secondo il Jitter o il delay richiesto</span>

<b><u>La capacità del canale viene fatta a fette tra le varie code, ai pacchetti in una coda verrà garantito una certa fetta del canale in base al tipo di traffico</u></b>.

*es* con 
- $i$ = 4. 
- $w_i=4, 2, 2, 2$ peso della coda $i$
- $w_1 = 4/10 = 2/5 * R$
- $w_{2,3,4} = 2/10 = 1/5 * R$

Supponiamo di avere un classifier smistera i pacchetti con un jitter più alto nella cosa v1.
Considerando un canale da 1Mbps, a $w_1$ assegno 500kb e a ognuno degli altri 125kb
w1 si svuoterà prima delle altre code.


<span style=color:red>Problema</span> = Come facciamo a <b><u>garantire una qualità di servizio</u></b> su una dichiarazione del flusso di ingresso se poi chi <b><u>generà traffico non rispetta tale dichiarazione mandando più traffico del previsto</u></b>.

<span style=color:green>Soluzione</span>:
<b><u>Devo effettuare un controllo in ingresso, il flusso di ingresso effettivo deve corrispondere con quello dichiarato</u></b>. Questa politica di sicurezza prende il nome di <span style=color:yellow>Traffic Sharig</span> e fa parte delle <span style=color:yellow>Call Admision</span>.

<span style=color:yellow>Traffic Sharig</span> = <b><u>L'eccesso di traffico viene eliminato se supera quanto dichiarato da chi generà traffico</u></b>. 
<b><u>Si tratta di una politica preventiva, il traffico viene limato alla sorgente in modo da evitare di intervenire con politiche di dropping nelle code durante la trasmissione</u></b>.



