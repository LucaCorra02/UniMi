Abbiamo un <span style=color:yellow>architettura a strati indipendenti organizzati gerarchicamente</span>. 
Il <b><u>modello teorico</u></b> adottato come standard nella costruzioni di reti è il modello <span style=color:yellow>ISO-OSI</span>. 
Gli strati del modello sono 7, dove : 
- il livello 1 sarà quello più vicino al canale fisico. 
- il livello 7 sarà quello più vicino all'utente finale. 

I<b><u>nternet in realtà non utilizza il modello OSI</u></b> come riferimento ma il modello <span style=color:yellow>TCP-IP</span> il quale presenta 5 livelli gerarchici. 

La comunicazione è <span style=color:yellow>peer-to-peer</span>, ovvero solo tra livelli pari. Deve essere sempre specificata l'interfacci di input e di output (sono bilaterali). Gli unici livelli che non ne hanno uno sovrastante, sono: 
- Lato Host, il livello 7
- Lato apparati applicativi di rete, il livello 3. 

<b><u>Ogni livello inoltre prende la struttura dati del livello superiore e applica il suo header</u></b>, ad ogni livello la struttura dati si ingrandisce. Più piccola è l'unità dati utente, maggiore sarà <span style=color:yellow>l'overhead</span> aggiunto.

<span style=color:green>Livelli</span> : 
 - <b><u>Livello 1</u></b> o <span style=color:cyan>livello fisico</span> = Abbiamo una porta di i/0 e un clock di trasmissione, infilando bit su bit in serie sul cavo in base alla velocità del clock. <b><u>I dati da trasmettere vengono presi da un buffer situato nell'interfaccia con il livello 2, il quale fornisce i dati da trasmettere</u></b>.
   Ovviamente deve essere in grado sia di trasmettere che estrarre dati dal cavo.

 - <b><u>Livello 2</u></b> <span style=color:cyan>Data Link o Link Layer</span> = <b><u>Da formato logico alle informazioni che viaggiano fra un nodo e il nodo successivo</u></b> ( da formato ai dati che viaggiano sul sinoglo link). Ci occupiamo di tutto quello che riguarda la <b><u>trasmissione con il nodo adiacente</u></b>. 
   *Se un nodo A a  2 vicini, avremo 2 livelli data-link*

- <b><u>Livello 3</u></b> <span style=color:cyan>Network Layer</span> = <b><u>Troviamo le funzioni di instradamento e indirizzamento, lavorano sull'intera topologia di rete</u></b>, la comunicazione con il singolo link la delego al livello 2. Qui ad esempio troveremo il protocollo IP. <b><u>Dipende dalle esigenze della topologia della reta in cui sto lavorando</u></b>. 

<b><u>Da qui finiscono i livelli interni agli apparati comunicativi della rete</u></b>. 
Una parte dei livelli host è uguale al router.  Lato Host troveremo tutte quelle funzioni che permettono di far comunicare due processi utente remoti attraverso i router. 

- <b><u>Livello 4</u></b> o <span style=color:cyan>Transport Layer</span> = <b><u>Si occupa dell'affidabilità</u></b>, parlando con il livello 4 della macchina remota. Troviamo il protocollo TCP, ovvero un protocollo <span style=color:yellow>end to end</span>, l'unico interlocutore è l'end system. 
  Qui vengono riordinati anche i pacchetti, in quanto il riordinamento è una sotto-funzionalità dell'affidabilità. 

  <b><u>Inoltre, troviamo anche una funzione non affidabile</u></b>, la quale utilizza il protocollo UDP. Ho due moduli a livello 4, UDP e TCP. Quale protocollo utilizzare verrà scelto dal livello superiore (in internet application layer).

- <b><u>Livello 5</u></b> o <span style=color:cyan>Session Layer</span> = <b><u>Ogni singolo processo della macchina che sta cercando di comunicare con una contro-parte dovrà essere indirizzato a livello di sessione</u></b>. 

  In internet non ho il problema di andare ad indirizzare i processi all'interno della macchina.  
  Non ho un protocollo vero e proprio, ma ho uno strato di interfaccia specifico della macchina chiamato socket. 
  <span style=color:yellow>Socket</span> = <b><u>modo attraverso il quale in internet è possibile specificare sessioni tra processi utente</u></b>. 

- <b><u>Livello 6</u></b> o <span style=color:cyan>Presentation Layer</span> =  Presentazione di un formato dati, formati diversi devono essere compatibili tra di loro. <b><u>Devo presentare i dati in un modo uniforme</u></b>. Viene specificato come convertire il formato dello specifico sistema operativo utente in un formato di rete, comprensibile alla destinazione. 

  Con internet, abbiamo ridotto la disomogeneità dei formati. il livello 6 in internet è stato compresso attraverso dei plugin nel livello 7. 

- <b><u>Livello 7</u></b> o <span style=color:cyan>Application Layer</span> = Livello funzionale che sta sotto l'utente finale. Qui troviamo alcuni protocolli come l'HTTP, Email, ecc .. Protocolli anche questi end-to-end. 

Standard teorico
- [[Livello Applicazione]]: protocollo che mette in comunicazione due applicazioni (es HTTP, DNS, IMAP, REST)
- Presentazione: fare in modo che i dati siano presentati opportunamente, quindi i dati sono compressi e decompressi
- Sessione: mantenimento di una connessione virtuale tra i due host
- [[Livello di Trasporto]]
- [[Livello di Rete]]: (es IP, Internet Protocol)si occupa di fare instradamento data una sorgente e una destinazione in multi hop (passando per piu nodi)
- [[Data link]]: (es Ethernet) si occupa di trasferire un pacchetto da una porta di un apparato dall'altro lato del cavo
- [[Livello Fisico]]

Fino al livello 4 tra i protocolli, i peer, comunicano direttamente 
[[Unità di misura]]