Dato un problema P, un problema R è un rilassamento di P
minimize $z_P(x)$ s.t. $x \in X_P$
minimize $z_R(x)$ s.t. $x \in X_R$
SE e SOLO SE valgono le due condizioni
- $X_P \subseteq X_R$
- $z_R(x) \leq z_P(x), \forall x \in X_P$

Il valore ottimo del rilassamento non è mai peggiore del valore ottimo del problema originale
$z^*_R \leq z^*_P$

Corollario 1: SE $R$ è inammissibile, anche $P$ è inammissibile
Corollario 2: SE $x^*$ è ottima per $R$ ed è ammissibile per $P$ e $z_R(x)=z_P(x)$, ALLORA $x^*$ è ottima anche per $P$
Corollario 3: SE $z^*_R \geq \overline{z}$, ALLORA $z^*_P \geq \overline{z}$ (SE la soluzione ottima del problema rilassato è peggiore di una soluzione ammissibile che conosciamo, allora tutte le soluzione del problema originario sono peggiore, QUINDI sono trascurabili)
Il corollario 3 è utilizzato nell'operazione di bounding