<b><u>Si tratta delle codifica delle frame adottata in ethernet</u></b>..
<span style=color:cyan>Obbiettivo delle codifica</span>  = <b><u>riuscire a trasmettere nella codifica, sia il contenuto informativo che informazioni riguardanti il clock, in modo da sincronizzare quello del ricevente e del destinatario</u></b>.

Funzionamento : 
- <span style=color:cyan>Scelta 1</span> : =<b><u>Codifica manchester centra il clock di trasmissione sulla metà del bit che vogliamo trasmettere (sulla metà del tempo corrispondente al periodo di un bit )</u></b>. Nella distorsione che il bit può avere, il punto che ne ha meno è il centro. 
		 
 - <span style=color:cyan>Scelta 2</span> := <b><u>Per ogni bit manchester impone una transizione di stato stato</u></b>. 
	 - Trasmetto 1 producendo una transizione verso l'alto. (alto- basso)
	 - Trasmetto uno 0 producendo una transizione verso il basso (basso - alto)

      ![[Pasted image 20240712154602.png]]


<b><u>Il segnale di clock si ottiene shiftando di mezzo bit cell dal centro</u></b>

![[Pasted image 20240712152140.png]]

<b><u>Per estrarre il clock in ricezione il livello fisico aggiunge 7+1 byte</u></b>,  <span style=color:yellow>un preambolo</span>. il preambolo è costituito da 7byte +1. <b><u>Gli ultimi due bit a 11, servono per indicare l'inizio della frame effettiva</u></b>. 

``` c 
Preambolo = 10 10 10 10 11
```
    
Utilizzando la codifica di manchester, <b><u>il formato del preambolo è funzionale a sincronizzare il clock del ricevente sui fronti di salita e di discesa del clock del trasmettitore (disambigua lo stato di idle dall'inizio della trasmissione)</u></b>.

<span style=color:red>N:B</span> = Quando il bit rate supera i 10Mbps NON è piu possibile utilizzare la codifica di Manchester
