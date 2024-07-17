![[Pasted image 20240717173030.png]]

*Esempio count to infinity*   :
Supponiamo di avere un guasto sul link 2. il guasto viene rilevato da B. 
Tabelle Per ogni nodo verso C :

| Da A To C       | Da B a C              | C   | Da D a C       | Da E a D       |
| --------------- | --------------------- | --- | -------------- | -------------- |
| Link 1, costo 2 | Link 2 costo infinito | -   | Link 3 costo 2 | Link 5 costo 3 |

Supponiamo che B rilevi il guasto (può farlo utilizzando ICMP) : 
- B nella sua tabella segna il collegamento verso C come : `Link 2 -> costo infinito`.
- B propaga il suo distance vector ai suoi vicini. 
- Dato che i distance vector vengono propagati in modo asincrono, la situazione di guasto potrebbe non essere rilevata dagli altri nodi. 

Supponiamo che B prima di spedire il distance vector che segnala `To C -> Costo infinito`, riceva un distance vector da A : 
- B riceve il distance vector da A := `Destinazione C -> Costo 2`. 

- B alla ricezione aggiorna l'entry in tabella `Link 1 -> Costo 3`, in quanto è  convinto che A riesca ancora a raggiungere C con costo inferiore . a questo punto per il trigger manda il seguente distance vector ad A : `Destinazione C -> costo 3`. 

- L'entri di A per C diventa `To C, Link 1, Costo 4`. A l'aggiorna in quanto cambia la situazione della rete. 

Vado ad aumentare all'infinito i costi. i pacchetti rimangono intrappolati tra i Link A e B. 