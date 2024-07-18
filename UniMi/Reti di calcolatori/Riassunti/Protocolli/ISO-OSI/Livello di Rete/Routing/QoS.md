<b><u>Ad oggi internet è un servizio best effort</u></b>, tutta via siccome è anche general purpose ,traffici di tipo etereogeno, il principio best effort non va bene per tutti i tipi di traffico. 
<u><b>Dobbiamo differenziare le diverse tipologie di traffico in base alle sue caratteristiche</u></b>,  `Indicato dai TOS bit dell'header`.

<b><u>Oltre ad una gerarchia di etichette, dobbiamo prevedere una serie di code di output e input diverse, schedulate in maniera opportuna in base al tipo di traffico che contengono</u></b>. Il problema diventa un problema di <span style=color:yellow>scheduling nelle code e di differenziazione del traffico</span>.

<span style=color:red>N.B</span> = <b><u>Le tecniche che vedremo accentuano la probabilità di fornire un servizio di qualità in base al tipo di traffico, ma non c'è la garanzia</u></b>, in quanto la rete è comunque best-effort.

| Tipo di traffico - Esigenze | Affidabilita | Delay | Jitter | Banda |
| --------------------------- | ------------ | ----- | ------ | ----- |
| email                       | Alta         | Basso | Basso  | Basso |
| web (come FTP)              | Alta         | Basso | Basso  | Medio |
| FTP                         | Alto         | Basso | Basso  | Medio |
| audio streaming             | Basso        | Medio | Alto   | Basso |
| video streaming             | Basso        | Alto  | Alto   | Alto  |
| Internet telephone          | Basso        |       |        |       |
| video conference            | Basso        | Alto  | Alto   | Alto  |

Jitter: tempo da quando il messaggio parte a quando arriva al destinatario
NON tutti i pacchetti hanno lo stesso ritardo




