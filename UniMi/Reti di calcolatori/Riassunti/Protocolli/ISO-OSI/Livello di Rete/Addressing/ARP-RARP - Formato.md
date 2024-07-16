
formato pacchetti 802.3

| Campo       | Bytes  | Note                |
| ----------- | ------ | ------------------- |
| DA          | 6      | Destination Address |
| SA          | 6      | Source Address      |
| Type/lenght | 2      | 0806 = ARP          |
| Data        | <=1500 |                     |
| PAD         |        | Padding             |
| FCS         | 4      | Cheksum             |
<b><u>Il campo type</u></b> non è utilizzato solo per discriminare con 8100Hex le frame che seguono il formato 1Q, ma <b><u>serve anche per far capire alla scheda ethernet che tipo di pacchetto stiamo trasportando nel payload</u></b> : 

- `0806 HEX `= <b><u>specifica una ARP request</u></b>
- `08035 HEX ` = <b><u>RRARP requests</u></b>.


formato pacchetto ARP/RARP

| Campo                   | bit  |                                                                     |
| ----------------------- | ---- | ------------------------------------------------------------------- |
| HW type                 | 16   | specifica il tipo di indirizzo MAC                                  |
| Protocol Type           | 16   | indica il tipo di indirizzo di rete usato (es per IP è 0800 in HEX) |
| Operation               | 16   | di seguito le opzioni possibili                                     |
| Operation: ARP request  | 0001 |                                                                     |
| Operation: ARP reply    | 0002 |                                                                     |
| Operation: RARP request | 0003 |                                                                     |
| Operation: RARP reply   | 0004 |                                                                     |
| Sender MAC address      | 16   | MAC del gateway                                                     |
| Sender IP address       | 16   |                                                                     |
| Target MAC address      | 16   |                                                                     |
| target IP address       | 16   |                                                                     |
|                         |      |                                                                     |

<b><u>La requests viaggerà con tutti i campi settati tranne il </u></b>`target hardware address `, sarà la response a settare quel campo. 

![[Pasted image 20231219092315.png|500]]