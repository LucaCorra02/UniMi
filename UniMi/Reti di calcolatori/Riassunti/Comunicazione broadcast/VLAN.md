Le `VLAN` <b><u>è un astrazione delle macchine collegate ad una LAN, consente di aggregare macchine omogenee dal punto di vista funzionale</u></b>. Introduco un nuovo livello di aggregazione, indipendentemente da dove sono fisicamente collegate le macchine. 

Standard `IEEE 802.1Q`

<b><u>I frame nelle VLAN non vengono solo instradate secondo il loro MAC address, ma anche secondo il proprio</u></b> <span style=color:yellow>VLAN identifier</span> in quanto end system di due VLAN diverse non possono comunicare. Le frame



<span style=color:red>Svantaggi: </span>
    Tutta via la <b><u>comunicazione tra VLAN diverse a volte può essere comoda, se mi limito al forwarding questo non sarà mai possibile</u></b>. Devo chiedere aiuto ad una macchina di livello superiore, <b><u>con il routing posso far comunicare macchine in VLAN differenti</u></b>. 

[[VLAN - Formato]]

Per poterla realizzare è necessario modificare il bridge/switch in modo tale che nel processo di learning, impari anche il colore/gruppo della stazione. 
Inoltre è necessario cambiare le schede di rete delle stazioni in modo che includa anche il colore del gruppo a cui appartiene

Opinione del Rossi: se cambia volendo una VLAN, dovro aprire il mio dispositivo, cambiare la scheda di rete per tutti i device, rischia di diventare oneroso

Solitamente si prende uno switch non cambiando la scheda delle singole stazioni, lavorando solo sullo switch, taggando le porte a configuration time 
Permetto alle stazioni di generare traffico untagged e appena arriva allo switch si ha il tag

![[photo_5769355704325488874_y.jpg]]