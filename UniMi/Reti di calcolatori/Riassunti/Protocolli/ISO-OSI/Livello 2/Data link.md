Avremo un entità per ciascun link in entrata/uscita dal nostro nodo. 
<h5 style=color:cyan>Struttura Frame livello 2</h5>
Il frame a livello 2 è strutturato nel seguente modo : 

- Flag inizio
- Header di frame
- Dati utente
- CRC (check sum)
- Flag fine (coincide a quello di inizio )
	
<h5 style=color:cyan>Funzioni di livello 2</h5>
 Il livello 3 in base al cammino che ha selezionato (in base alla politica di instradamento adottata), attiva la porta di i/0 del router e chiede alla specifica entità di livello 2 il seguente compito : 
 <B><u>Prendere il pacchetto confezionato dal livello 3 e trasferirlo in un frame al livello sotto-stante inviandolo al nodo di destinazione selezionato</u></b>. Il trasferimento può avvenire con due modalità:

-  <b><u>Affidabile</u></b> =  Presente sugli apparati applicativi della rete ma difficilmente utilizzata nella pratica. 
- <b><u>Best effort</u></b>

<span style=color:red>N.B</span> =  <b><u>A livello 2 si privilegia il servizo best-effort</u></b> = è inutile sovraccaricare le comunicazioni su tutti i link per renderla affidabile, quando possiamo alleggerire  la rete fisica di questo compito e scaricare tale responsabilità al livello 4, situato interno all' host.  

<b><u>il livello Data Link, in realtà, è costituito da due sotto livelli</u></b> <span style=color:yellow>il MAC e Logical Link Controller</span>: 

- In una rete con canale condiviso, dobbiamo andare ad aggiungere il <span style=color:yellow>il MAC (Multiple Acess Control) layer</span> = <b><u>Si tratta del protocollo che garantisce l'accesso al canale condiviso</u></b>. Su rete ethernet, il nostro MAC layer è l'802.3. <b><u>Permette di gestire il mondo broadcast</u></b>. funzionalità di Carrier Sense, BEB, Collision Control. 
	Definisce delle primitive che verranno rese disponibili a LLC
	Ogni scheda ethernet ha un indirizzo MAC unico di 48 bit
	

 - <span style=color:yellow>Logical Link Layer</span> = <b><u>in una scheda Ethernet troviamo un altro modulo che interfaccia il MAC layer</u></b>, utilizza il MAC per accedere al canale, o riceve dal MAC dei messaggi quando la stazione riceve dalla rete delle frame. <b><u>Crea una visione logica indipendente dal mondo broadcast in cui la connettività fra le varie stazioni è punto a punto</u></b>, viene costruito un grafo paragonabile ad una maglia totalmente connessa. 
   Si basa su [[Funzione affidabile HDLC]]. La comunicazione sul canale logico può essere : 
     - Di tipo Best effort.
     - Di tipo Affidabile.
