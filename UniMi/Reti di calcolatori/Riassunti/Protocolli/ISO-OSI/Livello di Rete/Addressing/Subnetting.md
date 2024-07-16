<b><u>Utilizzato per la suddivisione logica di reti grandi, riduce la dimensione delle tabelle di instradamento interne ad un organizzazione</u></b> ,Sfrutto al meglio lo spazio di indirizzamento che una rete ha già a disposizione. <span style=color:red>All'esterno non si avrà alcuna informazione sulal struttura della rete interna</span>.

Un indirizzo IP, sarà così composto : `Indirizzo IP = NETID | SubNetID | HostID`. 
<b><u>Aggiungiamo un livello di gerarchia all'interno dello spazio degli host id</u></b>. Questo campo prendere il nome di <span style=color:yellow>subnet</span> di <b><u>dimensione variabile</u></b>. L'organizzazione in SubNet `non è definita da uno standard`, ma è demandata al livello IP che sceglie quanti bit degli host ID demandare al SubNetID. 

Per discriminare SubNet e Host ID, aggiungo ad ogni entry nella tabella di routing la <span style=color:yellow>SubNetMask</span> con `tanti 1 quanti bit sono usati dal SubNetID`. 
<b><u>Facendo l'AND bit a bit tra il mio indirizzo e la mask, maschero i bit dell'host id</u></b>.

<span style=color:green>Perchè si usa il subnetting</span> : 
- <b><u>Organizzazione logica</u></b>
- <b><u>Disaccoppia i router associati ad una rete con le funzioni di routing della rete globale</u></b>
- <b><u>Ragioni di sicurezza</u></b> = Può essere più semplice identificare e localizzare un apparato infetto che genera traffico anomalo in rete. 

<span style=color:red>Svantaggio</span> = <b><u>Complica le tabelle di routing.</u></b>

Analisi dell'IP nei router:
1. <b><u>Viene analizzato il NetID</u></b>
	1.1 SE è lo stesso della rete a cui è collegato il router, manda il pacchetto
2. <b><u>Viene controllato il SubNetID</u></b>
3. <b><u>Viene controllato il HostID</u></b>

![[Pasted image 20231219132636.png|300]]

*Esempio*: `16bit NET ID | 6bit SubNet ID | 10bit Host ID`
 Netmask = `11111111 11111111 111111 0000000000 = /22 cioè ha bisogno di 22 1`

IP Esempio = `130.50.15.6`
`xxx . xxx . 000011 11.00000110`
`111..111. 111111 00.00000000`
Come risultato rimarranno solo i bit del SubNet:  `000011 = SubNet ID 3`