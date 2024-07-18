Misurazione di U rispetto alla soglia e al valore ottimo : 
- Se il valore<span style=color:yellow> di utilizzo U</span>, tende a collocarsi nella zona critica (rispetto al valore ottimo e di soglia) , <b><u>utilizzo ICMP</u></b>, il quale propaga pacchetti  <span style=color:yellow>cook packet</span>: 
  <b><u>Si tratta di pacchetti di controllo che vengono propagati backword rispetto alla direzione del traffico</u></b>. 
  <b><u>Il router che misura una soglia di U eccessiva, segnala alla sorgente del traffico (mandando il cook pachet agli adiacenti) che sta andando in congestione, con lo scopo di segnalare alla sorgente S di diminuire il flusso di traffico</u></b>. 

- Nel caso in cui <b><u>U arrivi al picco massimo</u></b> (lo supera) effettua <span style=color:yellow>Packet dropping</spaN> = Ammessa nella reti, vado a droppare i pacchetti quando la coda è piena. 
  <b><u>Il dropping di un pacchetto non può essere casuale, ma vado a droppare pacchetti in base alla priorità del tipo di qualità di servizio associata</u></b>. 
  Le tecnica utilizzata è <span style=color:yellow>RED Random Early Detection</span>  
    
  <b><u>Il dropping dei pacchetti è ammessa ed è funzionale per non far andare i router in congestione</u></b>. 

<b><u>TCP è un esempio di algoritmo che quando riceve dei pacchetti di tipo cock packet, esegue una riduzione e apertura del traffico smooth</u></b>, in base alla situazione percepita del traffico in rete. 

La coda di output dei router è gestita con due blocchi
- <b><u>Servizio affidabile</u></b>: solitamente pacchetti generati dal [[QoS (L3) da TCP]]
- <b><u>Servizio sensibile al delay</u></b>, [[QoS (L3) da UDP]]

[[Differentiated services]]
[[Call Admision]]

