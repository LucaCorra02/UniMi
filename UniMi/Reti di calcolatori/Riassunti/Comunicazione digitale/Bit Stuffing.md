<span style=color:yellow>Bit stuffing come funziona </span> : 
 Supponiamo di avere il seguente campo utente : 
 ``` c 
<- 0[01111110]00
sequenza trasmessa 0011111[0]1000

<- 0011111000
seqeunza trasmessa 0011111[0]000
```
<span style=color:green>Lato trasmettitore</span> : 
- <b><u>Il bit stuffing conta i bit, nello shift register abbiamo un contatore, che conta i bit consecutivi a 1. </u></b>

 - <u><b>Quando il contatore conta 5 bit consecutivi a 1, inserisco uno zero</u></b> all'interno della sequenza. 

<span style=color:green>Lato ricevente</span>: 
 - Conto gli uni consecutivi nel campo utente di un pacchetto. 

- Quando il contatore arriva a 5 (uni consecutivi), salva il bit successivo in un registro : 
   - <b><u>se il bit che segue è uno zero lo toglie, in quanto è un bit inserito dalla porta di i/0</u></b>. Quel bit non fa parte della sequenza di bit originale. 

   - <b><u>se il bit è un uno allora vuol dire che la sequenza è una flag</u></b>

<span style=color:yellow>il bit stuffing</span> inoltre <b><u>non provoca neanche un ritardo di un bit nell'esplorazione della sequenza</u></b>. 