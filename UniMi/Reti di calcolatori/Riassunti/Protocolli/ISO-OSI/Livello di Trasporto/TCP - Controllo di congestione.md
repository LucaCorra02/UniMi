<span style=color:red>Problema</span> = <b><u>Siamo in mancanza di un informazione importante in TCP, ovvero lo stato della rete</u></b>
Anche se il buffer di ricezione è vuoto e pronto a ricevere tutto il traffico potrebbe accadere che la rete sia `congestionata`, code dei router piene, causando <b><u>packet dropping</u></b>.

TCP rileva la congestione come un errore di trasmissione
- `thougthput`: utilizzo del canale nel tempo
- `goodput`: thougthput - utilizzo canale per ritrasmissioni

L'obiettivo del TCP quando viene utilizzato per l'invio di grandi quantita di dati, è mandare in parallelo piu segmenti possibili

Ipotizziamo di avere la trasmissione di segmenti verso una destinazione in cui in un primo tratto, ho una trasmissione veloce MA poi dal router alla destinazione ho un canale lento (collo di bottiglia). 
SE la rete ce la fa, si nota solo un aumento di RTT
SE i buffer del router si saturano, i segmenti vengono eliminati e TCP rileva l'errore di trasmissione MA la sorgente come stima $quanti$ segmenti inviare nell'unita di tempo?

La `finestra di congestione` indica quanti byte si possono immettere nella rete 
La sorgente sa che se invio un segmento e ne ricevo l'ACK, allora il segmento ha lasciato la rete 
L'unica cosa sicura è l'ACK arrivano con il tempo piu lento della rete, essendo di piccole dimensioni
[[Dimensionamento della finestra di congestione]]

