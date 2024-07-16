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


*es Tabella di instradamento*

| Location | Indirizzi che richiede                           | IP inizo      | ip fine       | tot indirizzi        | base             | mashera              |
| -------- | ------------------------------------------------ | ------------- | ------------- | -------------------- | ---------------- | -------------------- |
| Milano   | 248 indirizzi                                    | `194.24.0._`  | `194.24.7._`  | `8*256 = 2048 host`  | `194.24.0.0 /21` | $2^{11}$ $=32-11=21$ |
| Roma     | $(31-16)+1=15$. blocchi.<br>$16*256$ = 4096 host | `194.24.16._` | `194.24.31._` | `16*256 = 4096 host` | `194.24.16.0/20` | $2^{12}=32-12=20$    |
| Torino   | (11-8) +1 =                                      | `194.24.8._`  | `194.24.11._` |                      |                  |                      |

Maschera \\n = n bit a 1 e 31-n bit a 0

Arriva pacchetto con indirizzo 194.24.17.4
SE applicando la maschera all'address ottengo l'indirizzo base della location, l'indirizzo appartiene a tale rete
Prova a mappare l indirizzo su Milano
1100 0010 0001 1000 0001 0001 0000 0100 base
1111 1111 1111 1111 1111 1000 0000 0000 maschera
1100 0010 0001 1000 0001 0000 0000 0000 base AND maschera

Non ottengo la base di Milano
Facendo la stessa cosa con Roma, ottengo l'indirizzo base di Roma
Il pacchetto viene quindi instradato verso il SubNet di Roma

