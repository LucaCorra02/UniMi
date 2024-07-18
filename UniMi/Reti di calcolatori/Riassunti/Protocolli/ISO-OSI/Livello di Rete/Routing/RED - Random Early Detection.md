Usato con le `code best-efford`, cerca di `prevenire` <b><u>l'insorgenza del problema di traffico a burst</u></b>

<b><u>Un router normalmente scarta i pacchetti se la coda è piena</u></b>. Con TCP ogni volta che un pacchetto è perso, la sorgente lo rileva e dimezza il suo rate per nuovi pacchetti. Questo pero causa un riempimento dello code e una perdita di pacchetti.  

<b><u>Con RED quando un pacchetto arriva e la coda è piena, viene scelto un pacchetto che è nella coda in modo randomico e viene scartato</u></b>. Solitamente la scelta non è randomico ma dipende anche dalla `QoS` 

In questo modo un numero ridotto di diversi applicativi è coinvolto e viene migliorato l'utilizzo di banda

<b><u>Vengono prese due soglie</u></b>
- `MIN threshold`
- `MAX threshold`
- Viene definita continuamente una `AvrLEN`
$L_{AVG} = \alpha^{L_{OLD}} + (1-\alpha)*L_{CURRENT}$
con $0.5 < \alpha < 0.8$

Casi:
- SE : il nuovo pacchetto entra nella coda
- SE AvrLEN < MaxTH: il nuovo pacchetto è scartato
- SE MaxTH < AvrLEN < MinTH: un pacchetto nella coda viene randomicamente selezione, scartato e il nuovo pacchetto entra nella coda
