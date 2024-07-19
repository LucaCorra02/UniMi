Le funzioni principiali del livello 4 sono : 
-  <span style=color:yellow>Affidabilità</span>
- <span style=color:yellow>Indirizzamento</span> = deve essere risolto ad ogni livello. 
  Si tratta di un indirizzamento diverso da quello di livello 3 <b><u>(indirizziamo host finale, apparato di rete)</u></b>.

<b><u>TCP può servire più processi di livello 7 contemporaneamente</u></b>. Come fa TCP a discriminare in ricezione/invio quale processo indicare come destinatario/sorgente di un segmento.

Viene introdotto il concerto di <span style=color:yellow>Porta</span> = <b><u>il sistema operativo genera un identificatore univoco che associa la sessione del client (processo del client) sul tcp</u></b>.
<b><u>La primitiva che permette questa associazione prende il nome</u></b> di <span style=color:yellow>socket</span>, una volta chiamata ritorna una port descriptor.
La <span style=color:yellow>port descriptor</span> <b><u>ha solamente validità internamente alla macchina nella quale viene fatta la richiesta</u></b>. 

<b><u>Un associazione di livello 4 è univocamente identificata dalla coppia</u></b>, Devo identificare un associazione a livello di macchina fisica e processo nella macchina: 
- <span style=color:cyan>Porta Destinazione</span> = Informazione di Livello 4

- <span style=color:cyan>Porta Sorgente</span> = I primi due indirizzi legano il processo di livello 7 al TCP.

- <span style=color:cyan>Ip Destinazione</span> = informazione di livello 3. Per entrare in possesso di questa informazione dobbiamo utilizzare il <span style=color:yellow>Porta DNS Domain Name Server</span> = <b><u>protocollo che su richiesta esplicita, dato un nome logico, lo risolve e restituisce il corrispondente indirizzo ip</u></b>. 

- <span style=color:cyan>Ip Sorgente</span> = <b><u>In quanto le porte hanno solo validità locale e non a livello di rete internet</u></b>. Locale

 - <span style=color:cyan>Protocol Selector</span> = Consente di smistare le ricezioni verso l'entità di livello 4 corretta. 










A questo livello troviamo principalmente i seguenti protocolli: 
- [[TCP]] Transmission Control Protocol: <u><b>eroga un servizio affidabile</u></b>
- [[UDP]] User Datagram Protocol: <b><u>eroga un servizio best-efford</u></b>
- [[QUIC]]