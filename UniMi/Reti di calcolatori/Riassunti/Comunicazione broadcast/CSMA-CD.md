Protocollo `CSMA-CD Carrier Sense Multiple Access - Collision Detection `
Standardizzato come `IEEE 802.3`: [[CSMA-CD - Formato]]

CSMA-CD  può adottare due schemi : 
- `1-persistent` = <b><u>Si controlla continuamente se il canale è libero, appena è libero si trasmette. Se non è libero continuo a fare CS in modo persistente</u></b>. 

- `0-persistent` = è detto non persistente perché <b><u>si controlla una prima volta se il canale è libero, se non lo è si attende un intervallo casuale</u></b> (strettamente maggiore del tempo di trasmissione di una trama) <b><u>prima di ricontrollare il canale</u></b>.

Quando una stazione vuole trasmettere, prima di farlo fa <span style=color:yellow>Carrier Sense</span>, <b><u>cioè legge dal canale ciò che passa, rilevando se il canale sia in idle o meno</u></b>.
Il punto forte di questo protocollo è che <span style=color:green>il controllo è distribuito, non è centralizzato</span>. 

<b><u>Le collisioni sono sempre possibile se due stazioni effettuano</u></b> <span style=color:yellow>carrier sense</span> <b><u>nello stesso istante</u></b>. Siccome il canale risulta libero immettono entrambe il loro pacchetto. 
Ogni stazione è in grado di leggere dal canale di ricezione quello che sta trasmettendo e lo confronto. <b><u>Se due stazioni collidono quello che sto trasmettendo è diverso da quello che dovrei trasmettere</u></b>, <b><u>in questo caso blocco la trasmissione evitando di sprecare canale per pacchetti corrotti</u></b>. 

<b><u>La probabilità di collisione è tanto maggiore tanto piu stazioni ci sono sul canale</u></b>.
Le collisioni si possono ancora verificare SE una stazione $B$ sta trasmettendo e una stazione $C$ fa CS, quest'ultima aspetta che $B$ finisca. Tuttavia se un altro nodo $A$ fa CS, sia $A$ che $C$ stanno aspettando la terminazione della comunicazione di $B$ e ciò causa ancora una collisione

![[photo_5769355704325488862_y.jpg|600]]

<b><u>Per risolvere la collisione, prima di ritrasmettere, ogni nodo aspetta un tempo determinato dal</u></b>  [[BEB -Binary Exponential Backoff]].

Tutti i frame sono trasmessi usando la [[Codifica di Manchester]]
[[Standard rete a 10Mbps]]
[[Standard rete a 1Gbps]]

<span style=color:cyan>Prestazioni</span> 
Vediamo la curva di efficienza di questo protocollo. All'aumentare delle stazioni, l'uso del canale raggiunge il 90%/95%. <span style=color:green>Prestazione ottime</span>. <b><u>Tale percentuale la raggiunge in un punto ottimo, non sempre</u></b>. 
Se continuo ad avere collisioni (troppe stazioni) raggiungo lo 0 di efficienza, uso il canale solamente per ritrasmettere bit corrotti e non per trasmettere bit utili utente. 

L'efficienza è il<span style=color:yellow> troughtput </span>= <b><u>il numero di bit nell'unità di tempo trasmessi utilmente. </u></b>



