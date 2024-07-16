`CIDR - Classless Inter Domain Routing`
<b><u>Si tratta di una tecnica di routing utilizzata per aumentare la vita ad IPV4</u></b>. 
<b><u>Lo spazio degli indirizzi è diviso in blocchi autonomi ed indipendenti e non in classi</u></b>, ad ogni continente è stato assegnato uno spazio di indirizzi omogeneo. 

<b><u>A varie organizzazioni viene allocata una certa porzione di indirizzamento libera (dimensione arbitraria)</u></b>. 

Ogni router dovrà contenere per gli indirizzi CIDR, la <span style=color:yellow>base e mask</span>. 
- <span style=color:yellow>mask</span> = <b><u>La maschera separa lo spazio di indirizzamento inferiore fornito dalla base e lo spazio superiore fornito dall'ultimo indirizzo utile per sapere quale pagina stiamo enumerando</u></b>. 

  Se la <b><u>maschera applicata è quella corretta, il risultato sarà uguale all'indirizzo base dello spazio di indirizzamento in cui cade tale indirizzo</u></b>. 

- <span style=color:yellow>base</span> = indirizzo base da cui parte lo spazio di indirizzamento di una certa organizzazione. 

<span style=color:green>Vantaggi</span> : 
- <b><u>Consentendo l'alocazione specifica ad ogni operatore di un numero di indirizzi a scelta nello spazio di indirizzi disponibili, riduce lo spreco </u></b> 

<span style=color:red>Svantaggi</span> : 
- <b><u>Possono esserci fenomeni di frammentazione esterna</u></b>. Alcuni slot di indirizzi Ip potrebbero rimanere non utilizzati.  

<h5 style=color:cyan>Lavoro del router con CIDR</h5>
<b><u>Il router applica le maschere delle organizzazioni conosciute al campo destinazione dei pacchetti che intercetta e ne osserva il risultato</u></b> : 

- Se la <b><u>maschera applicata è quella corretta, il risultato sarà uguale all'indirizzo base dello spazio di indirizzamento in cui cade tale indirizzo</u></b>. 

 - il router applica tutte le maschere che conosce all'indirizzo di destinazione e <b><u>se non matcha con nessun indirizzo base di sua conoscenza lo manda ad un altro gatawey</u></b>. 

Il router esegue più lavoro dal punto di vista computazionale, ad ogni pacchetto devono essere applicate tutte le maschere del router fino ad un match. 

*es Tabella di instradamento*

| Location | Indirizzi che richiede                           | IP inizo      | ip fine       | tot indirizzi        | base             | mashera              |
| -------- | ------------------------------------------------ | ------------- | ------------- | -------------------- | ---------------- | -------------------- |
| Milano   | 248 indirizzi                                    | `194.24.0._`  | `194.24.7._`  | `8*256 = 2048 host`  | `194.24.0.0 /21` | $2^{11}$ $=32-11=21$ |
| Roma     | $(31-16)+1=15$. blocchi.<br>$16*256$ = 4096 host | `194.24.16._` | `194.24.31._` | `16*256 = 4096 host` | `194.24.16.0/20` | $2^{12}=32-12=20$    |
| Torino   | (11-8) +1 = 4 blocchi                            | `194.24.8._`  | `194.24.11._` | `4*256 = 1024 host`  | `194.24.8.0/22`  | $2^{10}=32-10=22$    |
*Esempio* : 
- Supponiamo di avere un router che conosce le basi e maschere delle 3 organizzazioni precedenti. 

 - Supponiamo che i router riceva un pacchetto con campo address = `194.24.17.4`. il router applica tutte le maschere, fino a quando non matcha con un indirizzo di sua conoscenza. 

- Nell'esempio l'indirizzo appartiene allo spazio di indirizzamento di ROMA : 
  $\dfrac{11000010 . 00011000.00010001.00000100}{11111111.11111111.11110000.00000000} = 11000010.00011000.00010000.000000000$ 


