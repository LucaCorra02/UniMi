<span style=color:yellow>Soluzione</span>: `Split Horizon `
Convenzione che prevede che ogni nodo quando propaga il proprio costo per una destinazione: 
- <b><u>Propaga il costo reale su tutte le adiacenze che non intende usare per raggiungere la destinazione</u></b>
- <b><u>Mentre propaga costo infinito sulle adiacenze che intende utilizzare per raggiungere la destinazione</u></b>.

<b><u>Si tratta un trucco per evitare di scrivere il link che voglio utilizzare nel distance vector</u></b>, risparmio header. 

  Supponiamo la seguente topologia di rete : 
  ![[Pasted image 20240717175603.png]]