Una rete per essere <span style=color:yellow>affidabile</span>, deve garantire le seguenti proprietà : 
 - <b><u>Non posso perdere l'ordine di partenza dei pacchetti</u></b> = ogni pachetto segue un percorso indipendente. 
- <b><u>Non avere duplicati</u></b> = Se controllo la correttezza di un pachetto attraverso una cheksum, imponendo la ritrasmissione del pachetto, al ricevitore potrebbero arrivare due copie dello stesso frammento. 
- <b><u>il pachetto ricevuto deve essere corretto</u></b>.

Per vedere gli elementi necessari -> [[Connessione Affidabile Elementi]]

Chi garantisce l'affidabilità della comunicazione ? 
 - Possono farlo gli <b><u>host</u></b>
 - Ogni <b><u>router</u></b> garantisce l'affidabilità tra una coppia di nodi. 

<b><u>L'affidabilità, oltre ai messaggi, riguarda anche l'identificazione del malfunzionamento di un link.</u></b>
Ci possono essere diversi livelli di tolleranza dell'errore (verra demandata al TCP, affidabile se END to END)

Tipi di allocazione
- <b><u>allocazione a commutazione di circuito</u></b>: è richiesta una comunicazione completa, senza interruzione del traffico (es voce)
- <b><u>allocazione a commutazione di pacchetto</u></b>: come condividere i canali a disposizione dei vari host
	Usiamo tecniche di multiplexing per condividere i canali da piu host 
	- time division multiplexing TDM: usata nell'ambito delle reti fisse, in particolare per l upload. MA non tiene conto della priorità

Controllo per garantire l'affidabilità della rete
- [[Controllo di flusso - Introduzione]]
- [[Controllo di congestione - Introduzione]]

La maggior parte delle rete mette a disposizione:
- Servizio non affidabile o <span style=color:yellow>Reti Best Effort</span> = Reti che fanno del loro meglio per trasmettere un pacchetto, <b><u>senza però garantire affidabilità certa</u></b> : 
    - L'affidabilità del singolo pacchetto viene gestita a livello di host ( TCP ).
    - Tutta via la velocità di trasmissione risulterà maggiore. 
    - La rete internet è best effort, all'interno della rete è stata disabilitatà la funzione di affidabilità tra ogni nodo per ragioni di efficienza. è stata delegata a livelli più alti. 
  
-   <span style=color:yellow>Reti Connection Oriented</span> = <b><u>Reti che garantiscono affidabilità</u></b>, utilizzano maggiori protocolli.  Più overhead in ogni pacchetto 