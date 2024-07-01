<b><u>Se il canale di comunicazione è inaffidabile</u></b> o asincrono (non sincronizzato) ( introduce dei delay non calcolabili), Dobbiamo andare a risolvere il problema dell'accordo, ovvero<b><u>garantire affidabilità fra un punto e l'latro</u></b> (<span style=color:yellow>Controllo del flusso</span> )

<span style=color:yellow>Protocollo</span> = <b><u>insieme di regole che tutti gli host devono rispettare affinchè vogliano operare in un ambiente distribuito</u></b>. il protocollo deve essere <b><u>standard</b></u>. Le due macchine che comunicano devono avere delle regole convenzionate condivise per poter comunicare ( standard formato paacchetti, ecc..). 

Elementi <span style=color:cyan>necessari in una rete asincrona e tempi</span> vedere [[Tempi della trasmissione]]:

 - <span style=color:yellow>ACK acknowlogement</span> = dice a chi ha trasmesso il messaggio che il ricevitore ha ricevuto corretamente il pacchetto. <b><u>Si tratta di un pacchetto di controllo del traffico in rete</u></b> ( non trasporta informazioni utili all'utente), <b><u>aggiunge altro overhead</u></b>. 
   <b><u>Tutti gli algoritmi che hanno come base l'esigenza di rendere un traffico affidabile, prevedono la spedizione di un</u></b> <span style=color:yellow>ACK</span>. 

- <span style=color:yellow>Ritardo di trasmissione T o RTT </span> = <b><u>Si tratta del tempo che trascorre dalla trasmissione del pachetto alla ricezione dell'ACK</u></b>.  Tanto più lungo è T, tanto più lenta sarà la trasmissione del pacchetto successivo. Ovviamente bisogna cercare di <b><u>minimizzare T</u></b>.

- <b><u> Ci vuole un orologio lato trasmissione</u></b> <span style=color:yellow>timer di trasmissione (Tr)</span>.

Supponiamo di voler inviare un file <span style=color:cyan>F</span> : 
   ![[Pasted image 20240329211222.png]]

 il primo frammento di F (<span style=color:yellow>Fx</span>), arriva sul nodo A in una coda di trasmissione. Il <b><u>processo in esecuzione su A, prende il pacchetto e lo trasmette</u></b> alla destinazione opportuna. Inoltre viene avviato il <span style=color:yellow>timer di trasmissione Tr</span>. <b><u>A entra in uno stato  di wait</u></b>
	
- Il destinatario quando riceve il frammento <span style=color:yellow>Fx</span>, manderà un messaggio di conferma positiva <span style=color:cyan>ACK</span>. il destinatario ha ricevuto correttamente l'unità dati. 

- Quando A riceve il messaggio di <span style=color:cyan>ACK</span> viene resettato il <span style=color:yellow>timer di trasmissione Tr</span>, A può passare allo stato successivo. Passa ad inviare il frammento successivo <span style=color:green>Fy</span> . 

- Tutta via se il <span style=color:yellow>timer di trasmissione Tr</span> scade prima che A riceva il messaggio di <span style=color:cyan>ACK</span>, significa che il messaggio <span style=color:yellow>Fx</span> è andato perso, <b><u>dovrà essere ritrasmesso</u></b>. Devo mantenere una copia del pachetto per tutti il periodo <span style=color:yellow>Tr</span>. 
	