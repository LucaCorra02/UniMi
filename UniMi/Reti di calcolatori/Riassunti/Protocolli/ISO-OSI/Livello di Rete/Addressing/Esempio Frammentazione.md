![[Pasted image 20240716111819.png]]

- T = livello trasporto, parla con il livello trasporto lato destinazione. Da informazioni al livello 3 sulle frame da trasmettere. L'unità generata da questo livello è di <b><u>7000b</u></b>. 

- Struttura token ring interfacciata con internet. <b><u>La rete token ring gestisce frame da massimo 4000b</u></b>. 

- Struttura di destinazione ethernet con un gateway da/verso la rete internet. <b><u>La rete ethernet, gestisce frame da massimo 1500b</u></b> .

<span style=color:cyan>Lato Sorgente</span> : 
- Divido la struttura dati originale da 7000b in frammenti da 
   - <b><u>Frame1</u></b> = 3976 byte  + 20byte header ip. <b><u>3976 + 20 è il primo multiplo di 8 minore di 4000</u></b>. 
   
   - <b><u>Frame 2</u></b> = $7000 - 3976$ = 3024 byte payload+ 20byte header ip. 
	Campi frammento 2:

Campi frammento 1: 

| Campo  | Valore |     |
| ------ | ------ | --- |
| ID     | 20     |     |
| ToTLen | 7000   |     |
| Offset | 0      |     |
| M      | 1      |     |
Campi Frammento 2: 

| Campo  | Valore                                                     |
| ------ | ---------------------------------------------------------- |
| ID     | 20                                                         |
| ToTLen | 7000                                                       |
| Offset | 497 -> ho inviato fino ad ora i primi 487 gruppi di 8 byte |
| M      | 0 -> ultimo frammento, bit disattivato                     |

<span style=color:cyan>Lato Secondo gatway</span> :
Il gateway dell'end system di destinazione, dato che la rete di destinazione accetta frame di dim massima 1500b, deve effettuare ulteriore frammentazione. 

- Pacchetto 1, arriva il primo frammento di 3976 byte. 
  <b><u>Dim Frame = 1480 + 20 byte = 1500. 1480 è il primo numero multiplo di 8 minore di 1500</u></b>. 

  Il pacchetto viene diviso in 3 frammenti dal gateway : 
   - $F_1$ = Payload 1480
   - $F_2$= Payload 1480
   - $F_3$ =Payload 1016

| Campo  | Valore                      |     | Campo  | Valore       |     | Campo  | Valore                    |     |
| ------ | --------------------------- | --- | ------ | ------------ | --- | ------ | ------------------------- | --- |
| ID     | 20                          |     | ID     | 20           |     | ID     | 20                        |     |
| ToTLen | 7000                        |     | ToLen  | 7000         |     | ToTLen | 7000                      |     |
| Offset | 0 -> perchè primo frammento |     | Offset | 185 = 1480/8 |     | Offset | 370 = $\dfrac{1480*2}{8}$ |     |
| M      | 1                           |     | M      | 1            |     | M      |                           |     |

- Pacchetto 2 da 3024 byte 
  Il pacchetto viene diviso in 3 frammenti dal gateway : 
   - $F_1$ = Payload 1480 byte
   - $F_2$= Payload 1480 byte
   - $F_3$ =Payload 64 byte -> <b><u>dimensione minima delle frame ethernet, non ho bisogno di fare padding</u></b>. 

| Campo  | Valore                  |     | Campo  | Valore                         |     | Campo  | Valore |
| ------ | ----------------------- | --- | ------ | ------------------------------ | --- | ------ | ------ |
| ID     | 20                      |     | ID     | 20                             |     | ID     | 20     |
| ToTLen | 7000                    |     | ToLen  | 7000                           |     | ToTLen | 7000   |
| Offset | 497 = $\dfrac{3976}{8}$ |     | Offset | 682 = $\dfrac{3976 + 1480}{8}$ |     | Offset | 867    |
| M      | 1                       |     | M      | 1                              |     | M      | 0      |

