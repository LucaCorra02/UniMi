Un importante misura è <span style=color:yellow>Velocità di trasmissione su un Link (Tx)</span> = <b><u>Rappresenta il tempo richiesto per trasmettere un unità di informazione sul canale</u></b>. 

Supponiamo di avere due nodi della rete ( A e B): 
- Supponiamo un canale con velocità 1Mbps

- Entrambi i router hanno sul canale una porta i/0, entrambe collegate al <b><u>data bus e all'address bus</u></b>.

     ![[Pasted image 20240329165417.png]]

Una volta che indirizzata la porta, la cpu butta sul data bus un numero di bit in parallelo in base all'ampiezza del canale, essi verranno depositati su buffer. Quando il buffer è pieno e la porta viene indirizzati <b><u>i bit presenti nel buffer saranno trasferiti in serie sul link</u></b>. 
<b><u>La porta di i/0 quindi, trasferisce un canale parralelo (come i data bus) su una sequenza di bit in seriale (link)</u></b>. <span style=color:cyan>Effettua quindi una traduzione Parrallel-to serial e serial to parrallel</span>. 

Come fanno i bit ad essere trasferiti in serie ad una velocità di 1 Mbps ? 
- Devo introdurre il <span style=color:yellow>Clock di trasmissione</span> = un onda quadra con un certo periodo. Ogni tempo nativo del clock produce un impulso (una transizione da 0 ad 1). 

- <b><u>Con il clock di trasmissione stabilisco il ritmo (costantemente mantenuto nel tempo), con cui i bit vengono spediti sul canale seriale (link). Il ritmo è costantemente mantenuto nel tempo</u></b>.  

*Esercizo* : 
- Supponiamo di avere un informazione di 1000 bit 
- Canale da 1 Mbps
  Qual'è il tempo necessario alla porta di i/0 per trasferire 1000bit ?
	Tx = 10^3 / 10^6 = 10^-3 
	Tx = 1ms. Meno di 1ms non ci può mettere, non può andare più veloce. 