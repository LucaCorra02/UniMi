<span style=color:yellow>Soluzione</span>: `Split Horizon `
Convenzione che prevede che ogni nodo quando propaga il proprio costo per una destinazione: 
- <b><u>Propaga il costo reale su tutte le adiacenze che non intende usare per raggiungere la destinazione</u></b>
- <b><u>Mentre propaga costo infinito sulle adiacenze che intende utilizzare per raggiungere la destinazione</u></b>.

<b><u>Si tratta un trucco per evitare di scrivere il link che voglio utilizzare nel distance vector</u></b>, risparmio header. 

  Supponiamo la seguente topologia di rete : 
  ![[Pasted image 20240717175603.png]]

- B misura il costo verso A, aggiornando la sua tabella. 
  `Destinazione: A, Link 1, Costo 1`
 - B propaga il distance vector ad A e C. 
 - C conosce l'esistenza di A, `C: Destinazione A, Link 1 -> Costo 2`. 
 - C propaga il distance vector a B e D. 
 - D entra a conoscenza di A e B : `Destinazione A, Link 1 -> Costo 3`. 

Supponiamo che il link tra A e B, si guasti : 
- Il guasto viene rillevato da B, tutta via il distance vector viene perso. 
- C manda un DV con infinito verso B e un distance vector con il costo reale a D. 
- B a questo punto propaga il suo distance vector a C, l'entry verso B nella tabella di C viene aggiornata. 
- Per il meccanismo di triggering, C invia un DV a D. D aggiorna l'entry nella sua tabella verso A con peso a infinito. 

![[Pasted image 20240717180604.png]]

*La destinazione sotto-intesa è A, ogni colonna rappresenta il costo di ogni nodo verso A*.

