<h5 style=color:cyan>Funzioni Best effort</h5>
La modalità best Effort del livello 2, funziona nel seguente modo. <b><u>Funzionamento in trasferimento</u></b>:

- Prelevo il pacchetto di livello 3 dal buffer presente nell'interfaccia. 

- Aggiungo <b><u>l'header di livello 2 all'unità dati</u></b>.

- Passo l'unità dati all'interfaccia di livello fisico, sarà trasmessa come sequenza di bit. 

<span style=color:red>Problema</span> = l'unità dati di livello 2 (frame) viene trasmessa come una sequenza di bit sul canele. <b><u>Come faccio a distinguere quando inizia e finisce la trasmissione di un pacchetto sul canale rispetto alla fase idle di quest'ultimo</u></b> (tutti bit a 1 o tutti bit a 0)?

<b><u>Utilizzo una sequenza di bit ben definita (uguale per segnalare inizio e fine trasmissione )</u></b> che prende il nome di <span style=color:yellow>flag</span>. 
Per quando riguarda il protocollo HDLC, la <span style=color:yellow>flag</span> è lunga un byte, ed è costituita nel seguente modo : 

``` c 
Flag = 01111110
```

<b><u>Potrebbe capitare di avere all'interno del campo dati utente ( livello 3) una sequenza di bit uguali</u></b> alla <span style=color:yellow>flag</span>. In questo caso non duplico la flag (troppo overhead), ma <span style=color:cyan>introduco un unico bit di overhead, per disaccopiare dati utente e flag</span> . 
<b><u>Tutte le porte di i/0 delle reti funzionano con questa politica che prende il nome di</u></b> <span style=color:yellow>bit stuffing</span>, <b><u>Eseguito dalle porte di i/0 al livello fisico</u></b> ( *le uniche flag che viaggiano "pulite" sono quelle situate fuori dal campo dati utente*).