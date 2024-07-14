
Alcune criticità: 
- Non tutte le comunicazioni sono broadcast, vogliamo <span style=color:red>trovare il modo per effettuare una comunicazione punto a punto</span> anche in una tipologia del genere. 
  <span style=color:green>Soluzione= </span> <b><u>Se la destinazione nell'header del pachetto è B, gli altri nodi a livello di driver di i/0 sanno che devono scartare il pacchetto non destinato a loro</u></b>. 


- <span style=color:red>Gli Hub e i Bus lineari sono delle regioni critiche e nelle regioni critiche può accedere un solo processo, acesso mutalmente esclusivo</span>. Se tutte le stazioni hanno la stessa priorità di parlare, in caso di traffico, si creerebbe una congestione. <b><u>Devo definire di un protocollo di accesso al canale condiviso</u></b>, <b><u>acesso mutualmente esclusivo</u></b>.

  Una <span style=color:yellow>collisione</span> si verifica quando due o piu stazioni provano a trasmettere un frame sul bus nello stesso tempo. 

<b><u>Protocolli di accesso condiviso per reti broadcast</u></b>
- [[Protocollo token-ring]]
- [[Protocollo Ethernet]]