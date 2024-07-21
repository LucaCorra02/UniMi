- (NH = 0) <span style=color:cyan>hop-by-hop options</span>
 Viene utilizzato per i <span style=color:yellow>Jumbo packet</span> = <b><u>Pacchetti più grandi di 65kb. Utili quando devo trasferire pacchetti su link molto lunghi (tratte intercontinentali)</u></b>.
  In queste tratte <b><u>domina il tempo di propagazione, più riesco a mandare roba concatenate</u></b> <b><u>meno ho impatto sull'utilizzo del canale</u></b>.

![[Pasted image 20231219092831.png]]

- (NH = 43) <span style=color:cyan>Routing option</span>

<span style=color:yellow>Permette di specificare il source routing</span>, oltre agli indirizzi IP dei nodi intermedi, contiene `24 bit di strict/loose bit map` :
 - SE il bit $= 1$, <b><u>l'indirizzo specificato deve essere raggiunto in modo diretto</u></b>,
 - SE bit $= 0$, <b><u>l'indirizzo puo essere raggiunto passando da altri indirizzi</u></b>.
<b><u>Contiene quindi al massimo 24 indirizzi</u></b> a cui fa riferimento la mappa

![[Pasted image 20231219092858.png]]

- <span style=color:cyan>Fragment</span>: <b><u>informazioni per permettere alla destinazione di riassemblare il pacchetto</u></b> (vengono infatti tolti i campi della frammentazione dal formato base del pacchetto)