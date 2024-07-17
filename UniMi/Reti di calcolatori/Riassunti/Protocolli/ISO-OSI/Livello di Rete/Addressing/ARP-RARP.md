`ARP - Address Resolution Protocol`

ARP è infatti <b><u>utilizzato per determinare l'indirizzo MAC di un host della rete LAN dato l'indirizzo IP</u></b>
Ogni host ha infatti associato un indirizzo IP e un indirizzo MAC in una ARP cache.
<span style=color:yellow>ARP</span> = <b><u>è un modulo che lavora a livello</u></b> <b><u>3</u></b>, si interfaccia direttamente con il modulo IP e con il livello sotto-stante. 

<h5 style=color:cyan>Funzionamento</h5>
<span style=color:cyan>Dispositivi nella stessa rete</span> : 
   Suppongo che A voglia mandare un pacchetto a B : 
   - Il livello 3 produrrà un pacchetto IP con Ip sorgente A e ip destinazione B e lo spedirà al livello sotto-stante. 

  - il livello sotto-stante mappa l'IP di destinazione con il corrispettivo MAC. <b><u>A chiede al suo modulo ARP di risolvere L'IP di B nel MAC di B, generando così una ARP requests (se non è presente nella cache)</u></b>. 

  -  <span style=color:yellow>ARP requests</span> <b><u>viene mandata in broadcast a tutti i dispositivi della LAN</u></b>
    Solamente il diretto interessato risponderà (confronto IP dispositivo con IP nella Arp Requets). B generà una <span style=color:yellow> ARP response</span> e la <b><u>inoltrerà solo a chi ha generato la requets (punto a punto)</u></b>. 

ARP tiene traccia delle replay, in modo da non inoltrare una richiesta broadcast ogni volta, in una chache chiamata <span style=color:yellow>ARP chache</span> := <b><u>Mappa l'ip sul corrispondente MAC</u></b>. 
<b><u>Viene popolata anche in base alla requests</u></b>, tutti quelli che ricevono il messaggio possono associare l'ip address della sorgente con il MAC address della sorgente. 

<span style=color:cyan>Dispositivi in due LAN diverse </span> : 
   A vule Parlare con un Dispositivo K in una rete diversa da A. 
   - K non è presente nella ARP-Cache di A 
   
   - A esegue una ARP requests-in broadcast. <b><u>La request viaggia per tutta la rete LAN di A, ma nessuno risponde, interviene dunque L'access gatewey</u></b> (che riceve anch'esso la requests essendo in broadcast).

   - <b><u>il modulo ARP dell'acces gateway capisce che il dispositivo K non è nella rete di A, dai bit del NET ID dell'indirizzo ip</u></b>. 
	 il Gateway risponde ad A con un <span style=color:yellow>ARP replay</span> <b><u>contente il suo indirizzo MAC (indirizzo MAC del gateway)</u></b> Questa politica prende il nome di <span style=color:yellow>proxy-arp</span>. 
	 <b><u>Tutto il traffico verso K verrà indirizzato verso l'access gateway, sarà poi il router a preoccuparsi di come instradarlo</u></b>. 

`RARP - Reverse Address Resolution Protocol`

<b><u>E' utilizzato dagli host non appena entrano in servizio in modo che inviino in broadcast il proprio MAC cosicche lo riceva il server ARP</u></b>.
Il server, riconoscendo che è un messaggio RARP, crea una RARP reply contenente la coppia MAC/IP

[[ARP-RARP - Formato]]