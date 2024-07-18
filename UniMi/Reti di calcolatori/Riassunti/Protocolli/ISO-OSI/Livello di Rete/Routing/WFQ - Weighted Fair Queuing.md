<b><u>La fairness viene ottenuta assegnando un peso ad ogni coda, il tempo di servizio assegnato ad ogni coda è in funzione del peso di tutte le code</u></b>.

Per ogni coda $i$ abbiamo un tempo di servizio che è = $\dfrac{W_i}{Somma_ {pesi}}$ o $pesoCoda / totPesi * Rate$. 

<b><u>La capacità del canale viene fatta a fette tra le varie code, ai pacchetti in una coda verrà garantito una certa fetta del canale in base al tipo di traffico</u></b>.







Per assicurare che il limite di delay per ogni flow sia rispettato, l'ordine di trasmissione, quindi la coda, viene modificato ogni volta che un pacchetto arriva
Quando un nuovo pacchetto arriva, gli viene assegnato un `time-stamp` determinato dal tempo di arrivo e dal tempo di partenza previsto
Il time-stamp è utilizzato per compararlo a quello degli altri pacchetti in coda, `inviando quello con time-stamp piu piccolo`
In questo modo vengono rispettati i limiti sul delay

SE voglio differenziare le code in base a diversi livelli di sensibilità del delay, associo ad ogni coda un peso, la frazione di canale che assegna al traffico.

$(w_i / somma k w_k) * RateDisponibile$
$pesoCoda / totPesi * Rate$

`Non discrimina secondo il Jitter o il delay richiesto`

SE un router gestisce una coda come WFQ, la slice del canale è determinato dal peso
Alcuni router (solitamente di accesso) fanno `shaping`, cioè se viene dichiarato all'ingresso 1/4 del canale viene verificato se viene prodotto effettivamente 1/4

es 
con i = 1 a 4, $w_i=4, 2, 2, 2$ peso della coda
$w_1 = 4/10 = 2/5 R$
$w_{2,3,4} = 2/10 = 1/5 R$

Considerando un canale da 1Mbps, a $w_1$ assegno 500kb e a ognuno degli altri 125kb
w1 si svuoterà prima delle altre code