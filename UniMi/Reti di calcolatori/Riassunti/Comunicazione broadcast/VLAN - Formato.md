L'header della frame nel formato `IEEE 802.1Q` risulta lunga 22 byte, rispetto ai 18 byte di una frame nel formato `IEEE 802.3`


- Le frame che viaggiano da un sitema client ad uno switch, seguono il formato 802.3 e prendono il nome di <span style=color:yellow>frame untagged</span>. 

- Le frame che viaggiano tra due switch prende il nome di <span style=color:yellow>tagged</span>. Non seguono lo standard 802.3 che non ha il tag ma seguono lo standard <span style=color:yellow>802.1Q</span>, <b><u>le frame 802.3 vengono rielaborate in 802.1Q dallo switch</u></b>. 

  Il <b><u>collegamento tra due switch dove viaggiano frame tagged, prende il nome di</u></b> <span style=color:yellow>trunk</span>. 

| Campo             | Dimensione | Descrizione                                                    |
| ----------------- | ---------- | -------------------------------------------------------------- |
| DAddress/SAddress | 48 bit     |                                                                |
| VLAN protocol ID  | 16 bit     | settato a `8100Hex`. Utilizzato per distingure i tipo di frame |
| PRI               | 3 bit      |                                                                |
| CFI               | 1 bit      |                                                                |
| VLAN identifier   | 12 bit     | permette l'identificazione della VLAN del mittente             |
| length            | 16 bit     | lunghezza del payload                                          |
| FCS               | 32 bit     |                                                                |

![[Pasted image 20231219134144.png]]
