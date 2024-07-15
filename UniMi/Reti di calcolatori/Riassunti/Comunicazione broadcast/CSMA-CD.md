Protocollo `CSMA-CD Carrier Sense Multiple Access - Collision Detection `
Standardizzato come `IEEE 802.3`: [[CSMA-CD - Formato]]

CSMA-CD  può adottare due schemi : 
- `1-persistent` <b><u>cioè appena trova libero il canale, trasmette</u></b> (Standard)
- `0-persistent` invece <b><u>appena trova libero il canale aspetta un tempo casuale</u></b>

Quando una stazione vuole trasmettere, prima di farlo fa <span style=color:yellow>Carrier Sense</span>, <b><u>cioè legge dal canale ciò che passa, rilevando se il canale sia in idle o meno</u></b>.
Il punto forte di questo protocollo è che <span style=color:green>il controllo è distribuito, non è centralizzato</span>. 

<b><u>Le collisioni sono sempre possibile se due stazioni effettuano</u></b> <span style=color:yellow>carrier sense</span> <b><u>nello stesso istante</u></b>. Siccome il canale risulta libero immettono entrambe il loro pacchetto. 
Ogni stazione è in grado di leggere dal canale di ricezione quello che sta trasmettendo e lo confronto. <b><u>Se due stazioni collidono quello che sto trasmettendo è diverso da quello che dovrei trasmettere</u></b>, <b><u>in questo caso blocco la trasmissione evitando di sprecare canale per pacchetti corrotti</u></b>. 
<b><u>Viene anche introdotto un tempo casuale per disaccoppiare le stazione che collidono.</u></b> 


<b><u>La probabilità di collisione è tanto maggiore tanto piu stazioni ci sono sul canale</u></b>.
Le collisioni si possono ancora verificare SE una stazione $B$ sta trasmettendo e una stazione $C$ fa CS, quest'ultima aspetta che $B$ finisca. Tuttavia se un altro nodo $A$ fa CS, sia $A$ che $C$ stanno aspettando la terminazione della comunicazione di $B$ e ciò causa ancora una collisione

![[photo_5769355704325488862_y.jpg|600]]

Per risolvere la collisione, prima di ritrasmettere, ogni nodo aspetta un tempo determinato dal  [[BEB -Binary Exponential Backoff]]

Tutti i frame sono trasmessi usando la [[Codifica di Manchester]]
[[Standard rete a 10Mbps]]
[[Standard rete a 1Gbps]]