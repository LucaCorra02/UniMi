<h3 style=color:cyan>1.1 Concetti preliminari</h3>
Alcune definizioni di concetti preliminari : 
- <span style=color:yellow>Popolazione</span> = è l'insieme di individui da cui si vorrebbero acquisire i dati. <b><u>Spesso per questioni di praticità non è possibile effettuare la raccolta dati su tutta la popolazione. Si utilizza un campione</u></b>.

- <span style=color:yellow>Campione</span> = <b><u>Sotto-insieme rappresentativo della popolazione</u></b>. Un buon campione <span style=color:green>deve essere casuale</span> (<span style=color:red>evitando il sotto-campionamento</span> di sotto-insiemi della popolazione), <b><u>la scelta id un individuo non deve influenzare la scelta dei successivi</u></b>.  
  Per fare il modo che il campione sia casuale si usano due tecniche :  
	 - <span style=color:cyan>Campionamento casuale</span> = <b><u>Ogni individuo deve avere le stesse probabilità di essere estratto</u></b>, così da ottenere un campione rappresentativo di tutta la popolazione.
	 
	 - <span style=color:cyan>Campionamento stratificato</span> = Da utilizzare quando la popolazione è divisa in sotto-insiemi non omogenei. 
	  <b><u>In base alla frequenza relativa di ogni sotto-insieme si sceglie un certo numero di elementi di esso da inserire nel campione</u></b>. Gli elementi del campione si pesano in base alla frequenza relativa. 

Un altro concetto base è quello di <span style=color:yellow>Freqeunza</span> : 
- <b><u>Frequenza assoluta</u></b> $f_j$  = Numero di volte che un certo dato compare nel campione. 
- <b><u>Frequenza relativa</u></b> $f_j'$ = Frazione di volte che un dato compare nel campione. Si calcola come il rapporto tra la frequenza assoluta di un dato e la grandezza del campione (<b><u>è sempre compresa tra 0 e 1</u></b>) : $f_j'= \dfrac{f_j}{n}$ 

<h3 style=color:cyan>1.2 Tipi di dati</h3>
Le categoria di dati si dividono in due grandi categorie : 
- <span style=color:yellow>Dati quantitativi</span> = <b><u>il risultato di una misurazione è una quantità numerica</u></b>. Ulteriore distinzione : 
   - <b><u>Dati Discreti</u></b> = <b><u>Si lavora su singoli valori</u></b> (solitamente interi) *numero di figli*
   - <b><u>Dati Continui</u></b> = <b><u>Si lavora con un range di intervalli</u></b>, ci saranno infiniti valori tra un numero interno e un altro *peso o altezza, probabilità*
   
- <span style=color:yellow>Dati quantitativi</span> = <b><u>il risultato di una misurazione è un etichetta</u></b>. Ulteriore distinzione 
  - <b><u>Binari</u></b> = <b><u>L'osservazione può avere solamente due esiti possibili, tra di loro non confrontabili</u></b>. 
  - <b><u>Nominali</u></b> = <b><u>Possibile stabilire una relazione di equivalenza tra i valori osservabili</u></b>.  
  - <b><u>Ordinali</u></b> = <b><u>Possibile stabilire una relazione d'ordine tra i valori osservabili</u></b>; è possibile distinguere tra due dati diversi quale sia il più piccolo e quale sia il più grande. 

<h3 style=color:cyan>1.3 Indici di centralità</h3>
<b><u>Gli indici di centralità danno delle informazioni sulla grandezza dei dati nel campione</u></b> e descrivono attorno a quale valore si forma la rosa dei valori. 
Notazione : 
- Per tutti gli indici si utilizza $n$ per <b><u>indicare la taglia del campione</u></b> (dimensione).
- Il campione stesso viene indicato con {$x_1,....,x_n$}
<h4 style=color:blue>1.3.1 Media campionaria</h4>
<span style=color:yellow>Media campionaria</span> = indicata con $\bar{x}$ è la media aritmetica degli elementi del campione -> il rapporto tra la somma dei valori presenti nel campione e la taglia del campione.
 Media campionaria = $\boxed{\bar{x}=\frac{1}{n}\sum_{i}xi}$ 

Si tratta di un <b><u>operatore lineare</u></b>, ovvero si <span style=color:green>comporta bene con le operazioni di traslazione e scalatura</span>:
    $\boxed{\forall i,  y_i = ax_i+b = \bar{y}=a\bar{x}+b}$  : 
- Supponiamo che $\bar{x}$ sia la media campionaria di un campione $X={x_1,..,x_n}$. Supponiamo ora di costuire un campione $Y={y_1,....,y_n}$, dove gli elementi di $Y$ differiscano dagli elementi $X$ di una traslazione $(+b)$ : 
      $\bar{y} = \bar{x}+b$
      
- Se invece definiamo gli elementi di $Y$ come una scalatura $(*a)$ degli elementi di $X$, possiamo osservare che : 
     $\bar{y}=a*\bar{x}$ 

Il principale <span style=color:red>difetto</span> della media campionaria è che <span style=color:red> non è uno stimatore robusto rispetto agli outlier</span>. <span style=color:yellow>Outlier</span> = <b><u>valori molto più grandi o molto più piccoli della media</u></b>, che possono falsare notevolmente le conclusioni. 

<span style=color:yellow>Scarti</span> = <b><u>Differenza tra ciascun valore dei dati del campione e la media campionaria. </b></u> La somma degli scarti è sempre 0. 

Altre formule per la media campionaria : 
- <b><u>Tabella delle frequenze assolute</u></b> = Si tratta di una tabella che contiene per ogni elemento $x$ il corrispettivo valore della frequ $f_i$