
| Classe             | Bit NetID | Bit HostID | Numero di reti          | Host per reti               |
| ------------------ | --------- | ---------- | ----------------------- | --------------------------- |
| Unicast Classe A   | 7         | 24         | $2^7$ reti possibili    | Ogni rete ha $2^{24}$ host  |
| Unicast Classe B   | 14        | 16         | $2^{14}$ reti possibili | Ogni rete ha $2^{16}$ host. |
| Unicast Classe C   | 21        | 8          |                         |                             |
| Multicast Classe F | 28        |            |                         |                             |
| Reserved Classe E  |           |            |                         |                             |

---

| Casi particolare                   | Significato                              |
| ---------------------------------- | ---------------------------------------- |
| NetID di soli 0                    | indica la stessa rete del mittente       |
| Indirizzo a tutti 1                | broadcast nella stessa rete del mittente |
| HostID di soli 1                   | broadcast sulla rete destinazione        |
| Un indirizzo di classe A di soli 1 | utilizzato per il test, loopback address |
Il router quando riceve un pacchetto esegue <b><u>l'operazione di processing nel seguente modo</u></b> : 
- <b><u>Prima processa i bit del net-id, capendo se il pacchetto è destinato alla sua sotto-rete</u></b>, altrimenti è solamente in transito. 
- <b><u>Se il pacchetto è destinato alla sotto-rete del router vengono valutati i bit di host-id</u></b>. 

<span style=color:red>Svantaggi</span> = <b><u>Frammentazione interna ad una classe</u></b>, una volta assegnata una classe è difficile che vengano utilizzati tutti gli indirizzi possibili per gli host. 