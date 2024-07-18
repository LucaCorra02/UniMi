`BGP Border Gateway Protocol` 
Protocollo che viene utilizzato in quello che viene chiamato <span style=color:yellow>internet backbone</span>. Punto in cui tutti gli <b><u>Automous system convergono</u></b>. 

<b><u>BGP è una funzionalità di livello 3</u></b>, tutta via dal punto di vista implementativo <b><u>è implementato a livello applicazione e funziona su TCP</u></b>. 
Tutte le entità BGP interagiscono attraverso sessioni permanenti di TCP, utilizzando la `Porta well-khown 179`

<b><u>Opera su TCP, in modo da garantire una comunicazione affidabile per quanto riguarda le informazioni di controllo</u></b>. 

BGP, utilizza la tecnica dei <span style=color:yellow>path vector per costruire le tabelle di instradamento</span>. I path vector contengono informazioni di : 
- <b><u>Informazioni di costo</u></b>. 

- <b><u>informazioni di path</u></b>. <b><u>Viene indicato oltre alla destinazione anche il cammino che si vuole seguire per raggiungerla, evitando così di incorrere nel count to infinity.</u></b> 

<b><u>Vengono propagati senza fare flooding.</u></b>

*Esempio*

![[Pasted image 20240718130300.png]]

Link tra F e B si guasta.
Supponiamo di studiare la destinazione C. 
- F avrà il seguente path  `F::FBC x` 
- A avrà il seguente path  `A:ABC 5`
- E avrà il seguente path  `E:EFBC 3`

Cosa succede : 
- F riceve i path vector dai vicini, da A e da E. 
- E propaga il suo path vector `E:EFBC costo 3`. <b><u>Viene scartata da F in quanot il path vector riporta F come elemento da attraversare, tutta via il link è guasto</u></b>.  
- A propaga il suo path vector `A:ABC costo 5`
