
| Classe             | Bit NetID | Bit HostID | Numero di reti          | Host per reti               |
| ------------------ | --------- | ---------- | ----------------------- | --------------------------- |
| Unicast Classe A   | 7         | 24         | $2^7$ reti possibili    | Ogni rete ha $2^{24}$ host  |
| Unicast Classe B   | 14        | 16         | $2^{14}$ reti possibili | Ogni rete ha $2^{16}$ host. |
| Unicast Classe C   | 21        | 8          |                         |                             |
| Multicast Classe F | 28        |            |                         |                             |
| Reserved Classe E  |           |            |                         |                             |

---

| Casi particolare | Significato |
| ---- | ---- |
| NetID di soli 0 | indica la stessa rete del mittente |
| Indirizzo a tutti 1 | broadcast nella stessa rete del mittente |
| HostID di soli 1 | broadcast sulla rete destinazione |
| Un indirizzo di classe A di soli 1 | utilizzato per il test, loopback address |

La gerarchia è utile per i router intermedi di rete che non devono quindi ispezionare tutti i 32 bit, ma SOLO il NET ID
Grazie alla gerarchia nelle tabelle di instradamento dei router intermedi conservo solo i NET ID