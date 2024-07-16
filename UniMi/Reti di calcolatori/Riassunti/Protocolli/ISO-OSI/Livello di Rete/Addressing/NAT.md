`NAT-  Network Address Traslation `

Ogni organizzazione introduce un <span style=color:yellow>dispositivo NAT</span> (con un <b><u>proprio indirizzo IP pubblico</u></b>) <b><u>al confine tra la LAN e internet</u></b>. <b><u>Ogni dispositivo della LAN avrà un indirizzo ip privato</u></b>.   
<b><u>il NAT è dunque una sorta di firewall tra lo spazio di indirizzamento pubblico e quello privato</u></b>.

<span style=color:cyan>Pubblico vs Privato</span> : 
- <b><u>Pubblico</u></b> = un indirizzo pubblico deve essere unico su scala globale 
- <b><u>Privato</u></b> = Un indirizzo privato non è visibile da nessuno all'esterno della LAN, ma sono conosciuti solo dal NAT. 
  Le classi di indirizzamento privato sono : 
  - `10.0.0.0.0 -> 10.0.0.0.255`
  - `172.0.0.0 -> 172.0.0.255`
  - `192.0.0.0 -> 192.0.0.255 `

<span style=color:green>Vantaggi</span> : 
- <b><u>Gli indirizzi ip privati possono essere riutilizzati da diverse organizzazioni</u></b>. Ammortizza il consumo di indirizzi ip pubblici. 
- <b><u>Protezione dal punto di vista della sicurezza</u></b>.
 - <b><u>Più di ogni altra tecnica va ad ottimizzare il consumo degli indirizzi IP</u></b>. Non è stato risolto del tutto ma quasi. 
 
<span style=color:red>Svantaggi</span> : 
- <b><u>Il NAT esegue una notevole elaborazione</u></b>, dal punto di vista computazionale, su ogni pacchetto che riceve IN/OUT. 
- <b><u>Gerarchia infranta, modifica payload di livello superiore</u></b>. 
<h5 style=color:cyan>Funzionamento NAT</h5>
<span style=color:green>Operazioni del NAT</span> : 
- <b><u>Un qualsiasi dispositivo con indirizzo privato nella area privata deve poter accedere ad un qualsiasi dispositivo con indirizzo ip pubblico</u></b> (ad esempio un server web). 

- <b><u>Una volta che il server risponde al client situato nell' area privata, la risposta deve essere inoltrata correttamente</u></b>. La risposta raggiunge il NAT ed esso deve indirizzarlo verso la macchina privata che ha effettuato la richiesta. 

Nel NAT è presente una <span style=color:yellow>tabella</span> . Essa contiene l'associazione tra : 
- <b><u>IPCLIENT</u></b> = indirizzo ip privato 
- <b><u>IPNAT</u></b> = indirizzo ip pubblico 
- <b><u>IPDEST</u></b> = indirizzo ip del destinatario
- <b><u>Numero di porta sorgente</u></b>. 
- <b><u>Numero di porta destinazione</u></b>
- <b><u>Porta Nat</u></b> = Numerazione interna al Nat, <b><u>non può essere duplicata</u></b> 

Il NAT effettua le seguenti sostituzione per ogni pacchetto IP : 
- <b><u>Sostituisce il campo ipSorgente con l'IP NAT</u></b>, viene sostituito l'ip privato 
- <b><u>Sostituisce nel payload la porta sorgente con la porta NAT</u></b>. 

<span style=color:cyan>Da Area privata a dispositivo pubblico</span> : 
- il client generà una richiesta verso il dispositivo di destinazione 

- <b><u>La richiesta viene intercettata dal NAT, il quale sostituisce nel header del pacchetto generato dal client il campo sorgente</u></b> con l'indirizzo pubblico del NAT.  

<span style=color:cyan>Da Dispositivo pubblico ad area privata</span> :

<b><u>Per gestire le response, bisogna andare ad aggiungere anche un informazione aggiuntiva</u></b> per permettere al NAT di inoltrare la risposta al dispositivo corretto nell'area privata. Utilizzo il <span style=color:yellow>numero di porta</span>. 

<span style=color:yellow>numero di porta</span> = il numero di porta è un informazione di livello superiore, <b><u>TCP identifica i processi applicativi con un numero di porta</u></b>. <b><u>Permette di associare univocamente all'interno della macchina un processo collegato al TCP</u></b>. 
<b><u>Il numero di porta è contenuto nel payload, in particolare il payload conterrà il segmento TCP</u></b> a 

<span style=color:red>Problema</span> = <b><u>Dato che le porte hanno validità solo sul singolo host, potrebbe capitare che due host nell'area privata generano entrambe lo stesso identificativo</u></b>. 

<span style=color:green>Soluzione</span> = Introduciamo un ulteriore campo nella tabella chiamata <span style=color:yellow>Porta del NAT</span >= <b><u>Numerazione interna fatta dal NAT, non può essere duplicata</u></b>.
<b><u>Non solo viene scoperta la porta sorgente nel payload, ma viene anche sostituita nel pacchetto da quella del NAT</u></b>. 


 Supponiamo di avere un server web all'interno dell'area privata. Nessuno dall'esterno è a conoscenza del indirizzo IP privato. NAT consentono di lasciare al server  web il suo ip privato. <b><u>il NAT può essere configurato lasciando aperta in ingresso una specifica porta</u></b>. Viene quindi indirizzato l'ip pubblico del NAT e la porta. 

[[NAT - Esempio]]