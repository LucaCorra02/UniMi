<span style=color:yellow>Rete di calcolatori</span> = Una rete di calcolatori, è un <b><u>sistema distribuito che interconnette host distribuiti geograficamente, attraverso un sistema di rete o sotto-sistema di comunicazione</u></b>. il sistema di rete sarà composto non solo da cavi, ma anche da nodi di rete. 

<span style=color:yellow>Host</span>  = Si tratta dell'apparato finale della rete, solitamente qui vengono eseguite le applicazioni finali in uso all'utente. 
<b><u>i nodi di una rete prendono il nome di</u></b> [[Router]]
<h3 style=color:cyan>Unità dati</h3>
In rete l'unità dati delle applicazioni che gli host utilizzano non viene spedita così com'è. <b><u>Dal punto di vista della gestione della memoria all'interno di un router è impossibile dare possibilità agli host di spedire le proprie unità dati host sulla rete</u></b>, è necessario <span style=color:yellow>frammentare</span> quelle unità. 

Le unità dati delle applicazioni degli host, viaggeranno in rete frammentate, <span style=color:yellow>segmenti dell'unità utente a dimensione massima fissata</span>, in modo da avere porzioni di memoria a dimensione fissa, <b><u>gestisco delle pagine di memoria a dimensione massima fissa</u></b>.
<b><u>Ogni frammento dell'unità dati host viene spedito in maniera indipendente e singolarmente sulla rete</u></b>. Queste unità dati sulla rete prendono il nome di <span style=color:yellow>pacchetti</span>.

Tutta via la pachettizazione delle strutture dati host, agevola la costruzione dei router che devono gestire i pachetti. Tuttavia abbiamo un <span style=color:red>possibile contro, ovverro aggiunge overhead</span> : 
	Ogni pacchetto non può essere trasmesso così com'è. <b><u>Ma devo riuscire ad aggiungere al pachetto un intestazione</u></b> (<span style=color:yellow>header</span> ), in cui sono presenti informazioni aggiuntive : 
    - Da che host è stato spedito, <b><u>indirizzo dell' host di spedizione</u></b> 
	- A che Host devo arrivare. <b><u>indirizzo dell'host di arrivo</u></b>.
	- <b><u>Indirizzo all'interno della rete del punto di ingresso</u></b>
	- <b><u>indirizzo all'interno della rete del punto di uscita</u></b>

<b><u>Tanto è più piccolo il pachetto, tanto è più grande l'overhead che viene aggiunto</u></b> in proporzione, le reti devono sempre trovare un compromesso tra overhead e funzionalità. 

<b><u>La frammentazione della struttura dati utenti viene eseguita dall'host</u></b>. Siccome i pachetti seguono un percorso autonomo indipendente (il migliore in base allo stato della rete).  <b><u>i frammenti devono poi essere ricomposti nell'unità dati originaria</u></b>, la funzione simmetrica alla frammentazione prende il nome di <span style=color:yellow>assembling</span>, eseguita sempre dell'host (ovviamente l'host destinazione ha come obbiettivo quello di riassemblare il file nell'ordine corretto). 

Parliamo dunque di <span style=color:yellow>reti a pacchetto</span>, ovvero il pacchetto è l'unità dati base che viaggia nel nostro sotto-sistema di comunicazione:
- [[Requisiti della rete]]
- Livelli della rete
	1. [[Rete di accesso]]: qualsiasi sistema di rete (es LAN) che collega le macchine e consente di aggregare tutto il traffico da e verso la rete. Tipi di aggregatori di traffico
		1. Rete locali fissi
		2. Rete locali wireless
		3. Rete cellulare: è mobile fino a che manda il traffico ad una rete locale wireless (antenna)
	2. [[Rete fissa]]

[[Comunicazione digitale (L2)]]
[[Dispositivi di rete]]
[[Rete - Principi di realizzazione]]