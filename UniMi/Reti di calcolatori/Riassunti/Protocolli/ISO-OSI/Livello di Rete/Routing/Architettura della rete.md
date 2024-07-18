La struttura di Internet è una `rete di reti`: 
- Al centro della struttura troviamo <span style=color:yellow>L'internet backbone</span> = <b><u>Qui i pacchetti vengono con</u></b>  `BGP`. 
- Al `internet backbone` sono collegati le varie `aree 0 /backbone` degli <span style=color:yellow>Autonomous system </span> = <b><u>Qui i pacchetti vengono ruotati con </u></b> `MPLS o OSPF`. <b><u>Nell'area 0, passa tutto il traffico intra e extra AS</u></b>.
- All' `area 0 di un AS` sono collegati altri AS = Qui i pacchetti vengono ruotati con `RIP o OSPF`.

![[Pasted image 20240718124633.png]]

![[Pasted image 20231219132229.png|600]]

[[Architettura delle rete - Ottimizzazioni]]


