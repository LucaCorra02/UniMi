Le `VLAN` <b><u>è un astrazione delle macchine collegate ad una LAN, consente di aggregare macchine omogenee dal punto di vista funzionale</u></b>. Introduco un nuovo livello di aggregazione, indipendentemente da dove sono fisicamente collegate le macchine. 

Standard `IEEE 802.1Q`

<b><u>I frame nelle VLAN non vengono solo instradate secondo il loro MAC address, ma anche secondo il proprio</u></b> <span style=color:yellow>VLAN identifier</span> in quanto end system di due VLAN diverse non possono comunicare. 

<span style=color:red>Svantaggi: </span> Tutta via la <b><u>comunicazione tra VLAN diverse a volte può essere comoda, se mi limito al forwarding questo non sarà mai possibile</u></b>. Devo chiedere aiuto ad una macchina di livello superiore, <b><u>con il routing posso far comunicare macchine in VLAN differenti</u></b>. 


<b><u>La stazione non indica la VLAN di appartenenza, ma è lo switch a taggare le porte di i/0</u></b>. Il colore delle porte di I/0 dello switch vengono impostate dall'amministratore. Il dispositivo che si attacca alla porta di I/0 con tag rosso apparterrà alla VLAN rossa. 

I dispositivi invieranno quindi traffico di tipo <span style=color:yellow>untagged</span>, sarà lo switch a taggarle,  prenderanno il nome di <span style=color:yellow>tagged</span> e viaggeranno nel formato `IEEE 802.1Q`. 

![[photo_5769355704325488874_y.jpg]]