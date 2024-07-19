
TCP è il primo <span style=color:yellow>protocollo orientato alla connessione</span> . <b><u>Per connessione intendiamo la capacità del protocollo di associare univocamente un processo lato client con un processo lato server in un legame di livello 4 che gestisce solamente il traffico tra questa coppia di processi (end-to-end)</u></b>.

<span style=color:red>N.B</span> = <b><u>La connessione TCP</u></b> è in realtà una <span style=color:yellow>Pipe di byte stream, sul TCP non passa uno stream di pacchetti ma uno stream di byte</span>. 

<b><u>Sulla singola connessione il TCP deve garantire l'affidabilità</u></b>, affidabile sulla singola associazione.
<b><u>Una connessione TCP, deve essere</u></b> : 
- <span style=color:cyan>Open</span>
- Avere una fase di <span style=color:cyan>Data Transfer</span>
- <span style=color:cyan>Close</span>

In TCP,  si allocano le porte da 1024 a 5000
Le porte da 1 a 1023 sono tipicamente riservate (es porta 21 riservata a FTP)

[[TCP - Formato]]
[[TCP - Fasi]]
[[TCP - Controllo del flusso]]
[[TCP - Controllo di congestione]]
