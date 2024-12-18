Programmazione lineare quando:
- le variabili hanno un dominio continuo
- i vincoli sono equazioni e disequazioni lineari (<=, >=, =)
- la funzione obiettivo è una funzione lineare delle variabili

Forma generale problema PL
1. maximize/minimize $z = cx$ funzione $z$ data dalla combinazione lineare di variabili x
2. subject to (introduzione del sistema di vincoli)
	- $A_1 x >= b_1$ con A1 la matrice dei coefficienti e b1 i termini noti
	- $A_2 x <= b_2$
	- $A_3 x = b_3$
	- $x' >=0$ variabile soggetta a condizione di non negatività
	- $x''$ variabili libere / non ristrette

Forma alle disuguaglianze
I problemi di PL sono riformulati nella formula alle disuguaglianze, per avere un utile interpretazione geometrica
Per passare dalla forma generale alla forma alle disuguaglianze occorre eliminare i vincoli di uguaglianza e le variabili libere.

Si puo sempre passare da un problema in forma generale a forma alle disuguaglianze

Eliminazione vincoli di uguaglianza: sostituzione
Eliminazione variabili libere: sostituisco ogni variabile libera con la differenza tra due variabili non libere che introduco

es
Eliminazione uguaglianze

| Item        | $x_1$     | $x_2$      | $x_3$      | Vincolo |
| ----------- | ------ | ------- | ------- | ------- |
| maximize  z | $3x_1$ | $-2x_2$ | $+5x_3$ |         |
| Subject to  | $2x_1$ | $-x_2$  | $-x_3$  | <=  8   |
|             | $3x_1$ | $+2x_2$ |         | >= -6   |
|             |        | $x_2$   | $-2x_3$ | = 1     |
|             |        | $x_2$ ,        | $x_3$        | >= 0        |

Per sostituzione considerando $x_2 -2x_3 = 1$ come $x_2 = 2x_3 +1$

| Item        | $x_1$     | $x_3$         | Vincolo |
| ----------- | ------ |  ------- | ------- |
| maximize  z | $3x_1$ |  $+x_3$ |  -2       |
| Subject to  | $2x_1$ |  $-3x_3$  | <=  9   |
|             | $3x_1$ |  $+4x_3$       | >= -8   |
|             |         $2x_3$ | >= -1     |
|             |         $x_3$        | >= 0        |

Eliminazione variabili libere
Ponendo $x_1 = x_4 -x_5$

| Item        | $x_3$      | $x_4$  | $x_5$  | Vincolo |
| ----------- | ------- | --- | --- | ------- |
| maximize  z | $+x_3$  | $+3x_4$    | $-3x_5$    | -2      |
| Subject to  | $-3x_3$ | $+2x_4$    | $-2x_5$    | <=  9   |
|             | $+4x_3$ | $+3x_4$    | $-3x_5$    | >= -8   |
|             | $2x_3$  |     |     | >= -1   |
|             | $x_3$ ,   | $x_4$ ,   | $x_5$    | >= 0    |

Vincolo ridondante: $2x_3 >=-1$

| Item        | $x_3$      | $x_4$  | $x_5$  | Vincolo |
| ----------- | ------- | --- | --- | ------- |
| maximize  z | $+x_3$  | $+3x_4$    | $-3x_5$    |    |
| Subject to  | $-3x_3$ | $+2x_4$    | $-2x_5$    | <=  9   |
|             | $+4x_3$ | $+3x_4$    | $-3x_5$    | >= -8   |
|             | $x_3$ ,   | $x_4$ ,   | $x_5$    | >= 0    |


E' semplice identificare i vincoli ridondanti 
Possiamo poi togliere i termini noti o costanti nella funzione obiettivo perche non cambia il ranking delle soluzioni (poi correggeremo il valore ottimo)
Rendiamo poi coerenti tutte le disequazioni: (tranne quello di condizione di non negatività)
- <= SE obiettivo di massimizzazione
- >= SE obiettivo di minimizzazione

Rappresentazione matriciale
Possiamo rappresentare lo stesso modello in maniera piu compatta come
maximize $w = c^T x$
subject to $A_x <= b$
$x >= 0$

es 


| Item        | $x_3$      | $x_4$  | $x_5$  | Vincolo |
| ----------- | ------- | --- | --- | ------- |
| maximize  z | $+x_3$  | $+3x_4$    | $-3x_5$    |    |
| Subject to  | $-3x_3$ | $+2x_4$    | $-2x_5$    | <=  9   |
|             | $-4x_3$ | $-3x_4$    | $+3x_5$    | <= 8   |
|             | $x_3$ ,   | $x_4$ ,   | $x_5$    | >= 0    |


$$c^T = \begin{bmatrix}1 && 3  && -3\end{bmatrix}$$
$$A = \begin{bmatrix}-3 && 2  && -2 \\ -4 && -3 && 3\end{bmatrix}$$
$$x = \begin{bmatrix} x_3 \\ x_4 \\ x_5 \end{bmatrix}$$
$$b = \begin{bmatrix} 9 \\ 8 \end{bmatrix}$$
Interpretazione geometrica della PL
Ogni soluzione x è un assegnamento di valore alle variabili, quindi un punto in uno spazio continuo ad n dimensioni, con n il numero di variabili.

Ogni vincolo di uguaglianza $ax = b$ corrisponde ad un iperpiano
Ogni vincolo di disuguaglianza $ax <= b$ corrisponde ad un semispazio

Il sistema dei vincoli nel modello alle disuguaglianze corrisponde all'intersezione dei corrispondenti semispazi, un poliedro

I semispazi sono convessi quindi l'intersezione di insiemi convessi è un insieme convesso QUINDI i poliedri sono convessi
Un insieme è convesso quando presi due qualunque punti nell'insieme, tutti i punti dei segmenti fanno parte dell'insieme convesso

Regione ammissibile
I "baffetti" dicono da quale parte il vincolo è violato

Poliedri ottenibili
- Poliedro limitato / politopo
- Poliedro illimitato: esiste una direzione per cui se parto da un punto e continuo per quella direzione, non incontro mai una frontiera 
- Poliedro vuoto: i vincoli sono combinati tali da non avere una soluzione ammissibile (e quindi una regione)

Tutte le soluzioni equivalenti giacciono su uno stesso iperpiano
La funzione obiettivo corrisponde ad un fascio di iperpiani paralleli ordinati come i corrispondenti valori dell'obiettivo
La direzione di ottimizzazione definisce l'ordinamento degli iperpiano del fascio

es
minimize z = 2x1 - 3x2
essendo x2 l'asse delle y e considerando che ha segno negativo, la direzione di ottimizzazione e verso l alto in quanto cosi x1 diminuisce e x2, aumentando, fa diminuire z

Considerando
- Convessità del poliedro = regione ammissibile
- Linearità delle curve di livello della funzione obiettivo
ne derivano 3 casi
- SE poliedro vuoto, non ci sono soluzioni ammissibili
- SE poliedro è illimitato nella direzione di ottimizzazione, allora non esiste un valore ottimo finito
- ALTRIMENTI esiste almeno un vertice del poliedro che corrisponde al valore ottimo, proprietà fondamentale della PL


Forma standard
Poniamo tutti i vincoli in forma di uguaglianza introducendo opportune variabili non negativo di scarto (slack) o di surplus

Mettendo in forma standard un problema alle disuguaglianze con $m$ vincoli e $n$ variabili, si ottiene un modello con m vincoli e $n + m$ variabili tutte non negative

Il sistema dei vincoli è un sistema di $m$ equazioni lineari in $n+m$ variabili
SE non ci sono vincoli ridondanti, la matrice dei coefficienti ha rango $m$
Il sistema quindi ha una soluzione univocamente determinabile SE eliminiamo gli n gradi di liberata fissando n variabili

Ad ogni variabile nulla nella forma standard corrisponde un vincolo attivo nella forma alle disuguaglianze
Fissare $n$ variabili a 0 nella forma standard, corrisponde a scegliere un punto in cui n vincoli sono attivi nella forma alle disuguaglianze

es
dato

| Item        | $x_1$      | $x_2$  | $x_3$  | Vincolo |
| ----------- | ------- | --- | --- | ------- |
| maximize  z | $+x_1$  | $+3x_2$    | $-3x_3$    |    |
| Subject to  | $-3x_1$ | $+2x_2$    | $-2x_3$    | <=  9   |
|             | $-4x_1$ | $-3x_2$    | $+3x_3$    | <= 8   |
|             | $x_1$ ,   | $x_2$ ,   | $x_3$    | >= 0    |

La forma standard è

| Item        |  $x_1$      | $x_2$  | $x_3$       | $x_4$   | $x_5$  | Vincolo |
| ----------- | ------- | ------- | ------- | ---- | --- | ------- |
| maximize  z | $+x_1$  | $+3x_2$ | $-3x_3$ |      |     |         |
| Subject to  | $-3x_1$ | $+2x_2$ | $-2x_3$ | $+x_4$     |     | =  9    |
|             | $-4x_1$ | $-3x_2$ | $+3x_3$ |      | $+x_5$     | = 8     |
|             | $x_1$ , | $x_2$ , | $x_3$ ,   | $x_4$ , | $x_5$    |   >= 0       |


Soluzione di base
Una base è un sottoinsieme di $m$ variabili scelte tra le $n+m$ della forma standard 
$$[ B|N ]$$
Il numero di basi è combinatorio, crescendo esponenzialmente con $m$ e $n$
Una volta scelta la base, il sistema si puo riscrivere come 
$$B*x_B + N*x_N = b$$

La soluzione del sistema $m * m$ che si ottiene dopo aver fissato a 0 le n variabili fuori base è una soluzione di base
Per ottenerla bisogna invertire la matrice B formata dalla base

$$x_B = B^{-1} * b - B^{-1} * N*x_N$$
da cui 
- Variabili fuori base $x_N = 0$ 
- Variabili in base $x_B = B^{-1}*b$

Esistono soluzioni di base non ammissibili quando $x_B < 0$
Per verificare ciò basta controllare che le variabili di base siano ancora >=0


Degenerazione
Quando una variabile in base risulta avere valore nullo, si ha degenerazione in quanto piu soluzioni di base coincidono
Piu di $n$ vincoli sono attivi nello stesso punto in uno spazio ad n dimensioni

Teorema fondamentale della PL
Dato un problema lineare in forma standard
$$z = min\{c^T x : A*x = b, x>=0\} $$
con A di rango $m$
- SE esiste una soluzione ammissibile, esiste anche una soluzione ammissibile di base 
(SE un poliedro non è vuoto, deve avere almeno un vertice)
- SE esiste una soluzione ottima, esiste anche una soluzione ottima di base 
(SE il poliedro non è illimitato verso la direzione di ottimizzazione, ci deve essere un vertice del poliedro che ha il valore ottimo)

Perciò un problema lineare nel continuo può essere risolto come problema combinatorio discreto, limitandosi a considerare solo le soluzioni di base.

Metodi risolutivi
La complessita della programmazione lineare è polinomiale (all'aumentare di n e m) tramite l algoritmo dell'ellissoide (Khachiyan 1979)
Il metodo piu utilizzato per risolvere i problemi di PL è l'algoritmo del simplesso (Dantzig 1947)

L'algoritmo del simplesso non da garanzia di terminare in un numero di iterazioni limitato da un polinomio MA è molto veloce 

L'algoritmo garantisce di terminare in un numero finito di passi, garantendo una di queste tre situazioni
- la soluzione corrente è ottima
- NON esiste una soluzione ammissibile
- NON esiste soluzione ottima finita

L'algoritmo del simplesso procede iterativamente da una soluzione di base ad una adiacente


L'algoritmo del simplesso
Forma canonica
- Dalla forma standard del problema di PL
minimize $z = c^T x$
subject to $Ax = b$
$x>=0$

- Scegliendo una base e permutando le colonne di conseguenza si ha
minimize $z = c^{T}_B x_B + c^T_N x_N$
subject to $Bx_B + Nx_N = b$
$x_B, x_N >= 0$

- Moltiplicando a sinistra per $B^{-1}$
minimize $z = c^{T}_B x_B + c^T_N x_N$
subject to $I_{X_B} + (B^{-1} N) x_N = B^{-1} b$
$x_B, x_N >=0$
con $I$ matrice di identità

La soluzione di base $x_B = B^{-1} b - (B^{-1} N) x_N$

- Sostituendo $x_B = B^{-1} b - (B^{-1} N) x_N$ in z
minimize $z = c^T_B B^{-1} b + (c^T_N - c^T_B B^{-1} N) x_N$
subject to $I_{X_B} + (B^{-1} N) x_N = B^{-1} b$
$x_B, x_N >=0$

- Riscrivendo z
minimize $z = z_B + \overline{c}^T_N x_N$
subject to $I_{x_B} + \overline{N}x_N = \overline{b}$

con $z_B$ costante che dipende da B, come abbiamo scelta la base
con $\overline{c}$ perche sono diversi dai c coefficienti iniziali

- Quando si pone $x_N = 0$ si ha $x_B = B^{-1} b = \overline{b}$
SE $\overline{b}$ >= 0 ALLORA la soluzione di base è ammissibile 

Esistono quindi un numero combinatorio di forme canoniche, tante quante le possibili scelte della base
Un problema di PL è in forma canonica SE e SOLO SE
- i coefficienti delle variabili di base, $x_B$, formano una matrice identità $m * m$
- le variabili di base $x_B$ NON compaiono nella funzione obiettivo

La forma canonica è forte SE e SOLO SE i termini noti dei vincoli sono non negativi, $\overline{b} >=0$
Una forma canonica debole implica una soluzione di base non ammissibile 


Una volta posto in forma canonica un problema di PL si puo rappresentare in una matrice, tableau.
E' una struttura dati fondamentale sulla quale opera l'algoritmo del simplesso

es

| Item       | $x_1$   | $x_2$   | $x_3$   | $x_4$   | $x_5$ | Vincolo |
| ---------- | ------- | ------- | ------- | ------- | ----- | ------- |
| minimize z | $-x_1$  | $-2x_2$ |         |         |       |         |
| subject to | $-x_1$  | $+2x_2$ | $+x_3$  |         |       | = 8     |
|            | $x_1$   | $+x_2$  |         | $+x_4$  |       | = 10    |
|            | $x_1$   |         |         |         | $x_5$ | = 7     |
|            | $x_1$ , | $x_2$ , | $x_3$ , | $x_4$ , | $x_5$ | >= 0    |

Forma canonica

| $-z_B$ | $\overline{c}^T_N$    | 0    |
| ------ | --- | --- |
|   $\overline{b}$     | $\overline{N}$    | $I$    |

| 0   | -1  | -2  | 0   | 0   | 0   |
| --- | --- | --- | --- | --- | --- |
| 8   | -1  | 2   | 1   | 0   | 0   |
| 10  | 1   | 1   | 0   | 1   | 0   |
| 7   | 1   | 0   | 0   | 0   | 1   |

Pseudocodice algoritmo del simplesso
```c
while (!Infeasible(b,c)) AND (!FeasibleBase(b)) do
	Pivot(A,b,c)
if Infeasible(b, c) then
	"Stop: problema inammissibile"
else 
	while (!Optimal(c)) AND (!Unbounded(A, c)) do
		Pivot(A, b, c)
	if Optimal(c) then 
		"Stop: soluzione ottima"
	else 
		"Stop: problema illimitato"
```

Nella prima parte si trova una soluzione di base ammissibile.
Wile finche la base non è Ammissibile e non abbiamo dimostrato che il problema è Infeasible
L'iterazione fondamentale del simplesso è il Pivot step

SE il problema è inammissibile, allora l algoritmo termina
Nella seconda parte si cerca una soluzione ottima
Ogni iterazione conserva l ammissibilita
O si trova la soluzione ottima o si scopre che il problema è illimitato

Infeasible = Ammissibile
Unbounded = Test che verifica che il problema sia illimitato

- Pivot(A, b, c)
Ogni iterazione consiste in un cambio di base
Una variabile in base esce dalla base e una variabile fuori base entra in base 
Geometricamente è come se ci muovessimo dal un vertice a un vertice adiacente

1. Si scegli un elemento pivot positivo posto su una colonna fuori base
2. Divido la riga del pivot per il pivot, in modo che il pivot diventi 1
3. Sottraggo ad ogni riga diversa da quella del pivot, la riga del pivot moltiplicata per $a_{ic}$ cioè il coefficiente sulla riga i-esimo e sulla colonna del pivot. Nella colonna del pivot compariranno tutti 0 tranne il pivot. entra quindi in base la colonna del pivot ed esce di base la colonna corrispondente alla riga del pivot

es

| 0   | -1  | -2  | 0   | 0   | 0   |
| --- | --- | --- | --- | --- | --- |
| 8   | -1  | 2   | 1   | 0   | 0   |
| 10  | 1   | 1   | 0   | 1   | 0   |
| 7   | 1   | 0   | 0   | 0   | 1   |

1. Scelgo 2, quindi riga = 1, colonna=2

| 0   | -1  | -2  | 0   | 0   | 0   |
| --- | --- | --- | --- | --- | --- |
| 8   | -1  | ==2==   | 1   | 0   | 0   |
| 10  | 1   | 1   | 0   | 1   | 0   |
| 7   | 1   | 0   | 0   | 0   | 1   |

2. Divido la riga 1 per il pivot, quindi 2

| 0   | -1  | -2  | 0   | 0   | 0   |
| --- | --- | --- | --- | --- | --- |
| 4   | -1/2  | ==1==   | 1/2   | 0   | 0   |
| 10  | 1   | 1   | 0   | 1   | 0   |
| 7   | 1   | 0   | 0   | 0   | 1   |

3. Sottraggo ad ogni riga tranne la 1, la riga 1 moltiplicata per 

| 8   | -2  | 0  | 1   | 0   | 0   |
| --- | --- | --- | --- | --- | --- |
| 4   | -1/2  | ==1==   | 1/2   | 0   | 0   |
| 6  | 3/2   | 1   | -1/2   | 1   | 0   |
| 7   | 1   | 0   | 0   | 0   | 1   |

Entra in base la colonna del pivot, quindi la 2 ed esce dalla base la colonna corrispondente alla riga del pivot, cioe la 1

| Vettore delle x | |  z   |  |
| --------------- | ---| --- | --- |
| prima | dopo | prima | dopo | 
| 0     | 0    | 0 | -8 | 
| 0     | 4    | | |
| 8     | 0    | | |
| 10    | 6    | | |
| 7     | 7    |                |     |




Interpretazione
- Algebrica
Il tableau è un sistema di equazioni
L'iterazione corrisponde a riformare in modo equivalente il sistema di m equazioni e n variabili
Si prende la riga del pivot riscrivendo l'equazione nuova incognita =... e poi per sostituzione otteniamo un nuovo sistema

es
Da $x_3 = 8+x_1-2x_2$  
a $x_2 = 4+\frac{1}{2}x_1 -\frac{1}{2}x_3$

Applico poi la sostituzione di $x_2$ nel sistema

- Geometrica
Associato ad ogni vincolo un indice, la corrispondente variabile che quando è a 0, il vincolo è attivo
indice (1) è associato a $x_2$ e (2) a $x_1$ perche quando $x_1=0$, allora è attivo $x_2$

es

Per determinare l'elemento pivot sono necessarie una regola di scelta della colonna e una regola di scelta della riga


Test di ottimalità: Optimal(c)
I test di ottimalità Optimal(c) riguarda i coefficienti di costo ridotto
$z = z_B + \bar{c}^T_N * x_N$
I coefficienti $\bar{c}^T_N$ indicano di quanto aumenterebbe la funzione obiettivo da minimizzare SE le variabili fuori base $x_N$ aumentassero di valore, cioè entrassero in base

Quando tutti i coefficienti di costo ridotto sono non negativi, non esistono direzioni ammissibili miglioranti e questo garantisce l'ottimalità della soluzione correte, SE è ammissibile
$z^* = z_B$

OSS possono esistere soluzioni degeneri nelle quali la condizione di ottimalità risulta verificata o meno a seconda della scelta della base


Regola di scelta della colonna
Per ogni iterazione dell'algoritmo del simplesso si sceglie una colonna, variabile entrante in base, che abbia costo ridotto negativo. Facendo entrare tale variabile la funzione obiettivo migliora (passi sempre miglioranti)

Ci possono essere diversi modi per effettuare tale scelta, quando ho piu colonne con costo ridotto negativo

es
...

Dobbiamo stare attenti ai casi degeneri che potrebbe causare dei cicli infiniti
La regola di scelta della colonna garantisce che l'algoritmo del simplesso raggiunge l'ottimalità
Diverse strategie
- colonna scelta casualmente tra quelle con costo ridotto negativo
- colonna col minimo coefficiente di costo ridotto
- colonna che produce il maggior miglioramento di z (passi di Pivot piu efficaci)
- la prima colonna con costo ridotto negativo (regola di Bland permette di NON generare mai cicli infiniti) 
La regola di scelta della colonna garantisce che l'algoritmo del simplesso raggiunga l'ottimalità

Regola di scelta della riga
Scelta la variabile che entra in base, è necessario scegliere la variabile uscente dalla base. Tale scelta deve garantire l'ammissibilità
Data la variabile entrante $x_j$, cioe lo spigolo del poliedro lungo il quale la soluzione cambia, l unica possibilita corretta è
- muoversi verso l'interno del poliedro
	- considerare solo candidati pivot $a_{ij}$ positivi
- fermarsi appena si incontra una soluzione di base
	- tra le righe $i$ ad essi corrispondenti, scegliere quella che rende minimo il rapporto tra il termine noto $b_i$ e il candidato pivot $a_ij$

Nel caso di parità di rapporto minimo, la regola di Bland impone di scegliere la riga di indice minimo (garanzia di assenza di cicli negativi)

esempio

Test di illimitatezza
SE non esistono candidati pivot positivi su una colonna con costo ridotto negativo, il problema è illimitato

Esempio

Variabili limitate
Le variabili possono essere limitate sia inferiormente che superiormente
I vincoli $x >= I$ e $x <= U$ possono essere trattati come vincoli qualsiasi aumentando pero le dimensioni del modello

Estendiamo la definizione di soluzione di base, considerando che una variabile fuori base:
Una soluzione di base è estesa SE è una soluzione nella quale $n$ variabili hanno valore pari al loro limite inferiore/superiore e le altre $m$ formano un sistema lineare indipendente cioe una base

L'algoritmo del simplesso puo lavorare con le soluzione di base estese


Inizializzazione
L'algoritmo del simplesso mantiene l'ammissibilità e cerca l'ottimalità quando è inizializzato con una soluzione di base ammissibile MA puo accadere che la soluzione di base iniziale non si ammissibile
Modi
- Metodo delle variabili artificiali
Dato un modello PL in forma standard (anche in forma non canonica) con $n$ variabili e $m$ vincoli
$$1)z = min\{c^Tx:Ax = b, x \in R^n_+\}$$
Con $b\geq 0$ si introduce una variabile artificiale $u_i >= 0$ con coefficiente unitario in ogni vincolo $i=1, ..., m$ definendo cosi un problema artificiale
$$2) z^a = min\{e^Tu:Ax+Iu=b, x,u \in R^n_+\}$$
Tutte le variabili artificiali $u$ compaiono in $e^T$ con coefficiente $1$

Vale la prima condizione per la forma canonica ma non la seconda
I coefficienti di $u$ formano una matrice identità MA le variabili $u$ non hanno coefficienti nulli nell'obiettivo
Per ottenere una forma canonica si effettua la sostituzione nell'obiettivo
$u_i = b_i - \sum_{j=1}^{n} a_{ij}x_j$
Ottengo la riga 0 del tableau in forma canonica

La soluzione iniziale $x=0$, $u=b$ è ammissibile per costruzione e quindi si puo eseguire l'algoritmo del simplesso sul problema artificiale (2)

SE il valore ottimo del problema artificiale è nullo ($z^a=0$), allora si è trovata una soluzione ammissibile per il problema originario (tutto le u=0 e le x invece hanno dei valori)
ALTRIMENTI si è dimostrata l'inammissibilita del problema originario (1)

Vantaggio: si puo sempre applicare
Svantaggio: puo comportare nella prima fase molti passi di pivot, almeno n passi di pivot e inoltre lavora su un tablue piu grande


Per evitare di dover eseguire $m$ passi di pivot per espellere dalla base le $m$ variabili artificiali, partendo da un problema in forma alle disuguaglianze, riscrivo in modo che il termine noto $b$ sia $\geq 0$.
Posso usare le variabili di slack o surplus come variabili artificiali

Per i vincoli di $\leq$: introduco variabili di slack positive
Per i vincoli di $\geq$: introduco variabili di slack negative

Le variabili di slack $\hat{x}_i$ per i vincoli $i \in I_1$ soddisfano gia la prima condizione per la forma canonica

Sia $h \in I_2$ l'indice del vincolo col massimo valore del termine noto.
$$h = argmax_{i \in I_2}\{b_i\}$$
Sottraendo ogni riga $i \in I_2 \backslash \{h\}$ dalla riga $h$, si ottengono vincoli equivalenti con termine noto non negativo e variabile $\hat{x}_i$ con coefficiente unitario

Bisognerà introdurre variabili artificiali per il vincolo $h$ e per i vincoli in $I_3$

- Metodo big M
Anziché eliminare dalla formulazione del problema artificiale le variabili $x$, è possibile mantenerle e penalizzare nell'obiettivo le variabili $u$ con coefficienti molto grandi
$$z^a = min\{c^Tx+w^Tu:Ax+Iu  = b, x,u \in R^n_+\}$$
con $w^T=[M, ..., M]$ vettore di coefficienti abbastanza grandi, t.c. ogni soluzione con una variabile $u_i > 0$, abbia costo maggiore del valore ottimo $z^*$ del problema 
Vantaggio: non serve una fase di inizializzazione
Svantaggio:
- il valore $M$ potrebbe provocare instabilità numerica
- non è detto che sia facile determinare il valore appropriato per $M$

- Metodo di Blainskki-Gomory
L'algoritmo trascura temporaneamente la funzione obiettivo e minimizza una misura dell'ammissibilità rispetto ad un vincolo violato, ripetendo l operazione per tutti i vincoli violati finche non raggiunge un base ammissibile oppure dimostra che il problema è inammissibile

Per ogni vincolo violato una misura della violazione è data dal valore assoluto della corrispettiva variabile, valore negativo
Maggiore è il valore assoluto, maggiore è la violazione del vincolo

OSS la forma canonica si conserva rispetto ai vincoli originali

In pratica scambio il vincolo violato con la funzione obiettivo, pensando il vincolo violato come la funzione obiettivo
ATT il valore della funzione obiettivo puo essere peggiorato perche non stavamo ottimizzando quello
Esempio

Test di inammissibilità
SE l'inammissibilità rispetto ad un vincolo violato è stato minimizzata MA il valore è ancora negativo, questo dimostra che il problema è inammissibile e l'algoritmo termina

L'algoritmo se ne accorge perche ha ancora un termine noto negativo MA tutti gli altri coefficienti di costo ridotto (sulla riga 0) sono positivi, quindi il problema è stato risolto 
Esempio

Problema ausiliario illimitato
Puo capitare che il problema ausiliario sia illimitato anche se il problema originale non lo è

Lo si capisce quando il pivot da scegliere è l'elemento negativo sulla riga del vincolo violato
Esempio


Teoria della dualità
E' il fondamento su cui si possono progettare algoritmi di ottimizzazione e di approssimazione e dimostrare le loro proprietà
Ogni problema di PL, il problema primale, ammette un altro problema di PL, problema duale

| Problema primale                              | Problema duale                             |
| --------------------------------------------- | ------------------------------------------ |
| Minimizzazione                                | Massimizzazione                            |
| $m$ vincoli                                   | $m$ variabili                              |
| $n$ variabili                                 | $n$ vincoli                                |
| i coefficienti della f.o. diventano           | i termini noti dei vincoli                 |
| i termini noti dei vincoli diventano          | i coefficienti della f.o.                  |
| matrice dei coefficienti A                    | matrice dei coefficienti $A^T$ (trasposta) |
| ogni vincolo di uguaglianza diventa           | una variabile libera                       |
| ogni variabile libera diventa                 | un vincoli di uguaglianza                  |
| ogni vincolo di disuguaglianza $\geq$ diventa | una variabile non negativa                 |
| ogni variabile non negativa diventa           | un vincolo di disuguaglianza $\leq$        |

---

| Problema primale P              | Problema duale D                    |
| ------------------------------- | ----------------------------------- |
| minimize $z=c_1^Tx_1+c_2^Tx_2$  | maximize $w=b_1^Ty_1+b_2^Ty_2$      |
| $A_{11}x_1 + A_{12}x_2\geq b_1$ | $A^T_{11}y_1 + A^T_{21}y_2\leq c_1$ |
| $A_{21}x_1 + A_{22}x_2 = b_2$   | $A^T_{12}y_1 + A^T_{22}y_2 = c_2$   |
| $x_1\geq 0$                     | $y_1\geq 0$                         |
| $x_2$ libera                    | $y_2$ libera                        |
La relazione è simmetrica: quindi il duale del duale di P è P

Teorema della dualità in forma debole
Data la coppia primale duale
- $P$: maximize $z(x)$, s.t. $x \in X$
- $D$: minimize $w(y)$, s.t. $y  \in Y$
Per ogni soluzione ammissibile $\bar{x} \in X$ di $P$ e per ogni soluzione ammissibile $\bar{y} \in Y$ di $D$ si ha 
$$z(\bar{x}) \leq w(\bar{y})$$
DIM
Dati
- $P$: maximize $z = c^Tx$, s.t. $Ax \leq b$, $x \geq 0$
- $D$: minimize $w = b^Ty$, s.t. $A^Ty \geq c$, $y \geq 0$
$$\forall\bar{x} \in X, \bar{y} \in Y, c^T\bar{x}\leq b^T\bar{y}$$
$A^T\bar{y} \geq c, \bar{x} \geq 0$ (sostituendo le soluzioni nei vincoli)
$\bar{x}^TA^T\bar{y} \geq  \bar{x}^T c$ (se multiplico per $\bar{x}^T$ il segno rimane lo stesso)
$c^T\bar{x} \leq \bar{x}^TA^T\bar{y}$ (leggo la disequazione da destra a sinistra)
Analogamente
$A\bar{x} \leq b$, $\bar{y} \geq 0$ (sostituendo le soluzioni nei vincoli)
$\bar{y}^TA\bar{x} \leq \bar{y}^Tb$ (se multiplico per $\bar{y}^T$ il segno rimane lo stesso)
$b^T\bar{y} \geq \bar{y}^T A\bar{x}$
In entrambi i casi, il secondo membro è uno scalare (e sapendo che lo scalare è uguale al suo trasposto)
$\bar{x}^TA^T\bar{y} = (\bar{x}^TA^T\bar{y})^T = \bar{y}^T (A^T)^T (\bar{x}^T)^T =  \bar{y}^T A\bar{x}$
$c^T\bar{x} \leq \bar{x}^TA^T\bar{y} = \bar{y}^TA\bar{x} \leq b^T\bar{y}$

Corollario 1
SE $\bar{x} \in X$ e $\bar{y} \in Y$ e si ha $z(\bar{x}) = w(\bar{y})$, ALLORA $\bar{x} = x^*$, $\bar{y} = y^*$, $z(\bar{x})= z^*$, $w(\bar{y}) = w^*$
ALLORA potremmo concludere che sono entrambe soluzioni ottime per i rispettivi problemi

Corollario 2
SE un problema di PL $P$ è illimitato, ALLORA il suo duale D è inammissibile (se esistesse non rispetterebbe il teorema della dualità in forma debole)
NON VALE il viceversa

Teorema fondamentale dell'algebra
Dato un sistema di equazioni lineare $Ax=b$, con $A$ di dimensione $m$ x $n$ e $b$ di dimensione $m$, una e una sola di queste alternative è vera
$$\exists x \in R^n:Ax=b$$
$$\exists y \in R^m: y^TA = 0, y^Tb \neq 0$$
Quindi o esiste un certificato di ammissibilità x, la cui esistenza dimostra che il sistema ha soluzione, o esiste un certificato di inammissibilità y, la cui esistenza dimostra che il problema non ha soluzione

Il teorema delle alternative dimostra la stessa cosa per i sistemi di disequazioni


Lemma di Farkas
Dato un sistema di equazioni lineari $Ax = b$, $x\geq 0$, con $A$ di dimensione $m$ x $n$ e $b$ di dimensione $m$, una e una sola di queste alternative è vera
$$\exists x \in R^n:Ax=b, x\geq 0$$
$$\exists y \in R^m: A^Ty \geq 0, b^Ty \leq 0$$
Quindi o esiste un vettore x soluzione per il primale o esiste un vettore y per il duale
DIM
Parte 1: SE la prima è vera, la seconda è falsa
E' vera $\exists x \in R^n:Ax=b, x\geq 0$
ALLORA
$\exists \bar{x} \in R^n:A\bar{x}=b, \bar{x}\geq 0$
$A^Ty \geq 0 \implies \bar{x}^TA^Ty\geq 0$ (moltiplicando per la trasposta di $\bar{x}$ non dovrebbe cambiare segno)
$\bar{x}^TA^T=b^T \implies b^Ty \geq 0$ (MA sapendo che y è negativo, o è vera la riga sopra o questa)
QUINDI la seconda è falsa

Parte 2: SE la prima è falsa, la seconda è vera
Definiamo il cono l'insieme dei vettori $q$ in $m$ dimensioni t.c. SE li sostituissi a $b$, darebbero una soluzione
$C = \{q \in R^m: \exists x(q) \in R^n : x(q) \geq 0, Ax(q)=q\}$
C è convesso
Dato che la prima parte è falsa, $b \notin C$
Secondo il teorema dell'iperpiano separatore (esiste un iperpiano che separa il vettore e il cono)
$$\exists y  \in R^m \backslash \{0\} : q^Ty \geq 0, \forall q \in C, b^Ty < 0$$
Poiché $q=Ax(q)$,  $\forall q \in C$, per sostituzione (con $x(q)$ il vettore che quando $b=q$ risolve il sistema)
$$q^Ty \geq 0, \forall q \in C \implies x(q)^TA^Ty \geq 0, \forall q \in C$$
Poiché $x(q) \geq 0$, $\forall q \in C$
$x(q)^TA^Ty \geq 0, \forall q \in C \implies A^Ty \geq 0$
QUINDI la seconda parte è vera

Interpretazione geometrica 

Lemma di Farkas: variante (forma forte)
Dato un sistema di disequazioni lineari $Ax \leq b$, $x \geq 0$ con A di dimensione $m$ x $n$ e $b$ di dimensione m, una e una sola di queste alternative è vera 
$$\exists x \in R^n : Ax \leq b, x \geq 0$$
$$\exists y \in R^m : A^Ty \geq 0, b^Ty <0, y \geq 0$$
OSS $y\geq 0$ non c era prima
DIM 
Introduciamo variabili di slack non negative
La condizione 1 diventa
$\exists x \in R^n, s \in R^m : Ax+Is = b, x \geq 0, s \geq 0$
Definendo $A' = [A|I]$ di dimensioni ($m$ x ($n + m$)) e $x' = \begin{bmatrix} x \\ s \end{bmatrix}$ di dimensioni ($n+m$) x 1, la condizione 1 diventa
$\exists x' \in R^{n+m} : A'x' = b, x' \geq 0$
Per il teorema di Farkas, essa è alternativa alla condizione
$\exists y \in R^m : A'^Ty \geq 0, b^Ty < 0$
Il sistema di disequazioni $A'^T y \geq 0$ equivale a $A^Ty \geq 0, y \geq 0$


Teorema della dualità in forma forte
Data una coppia primale-duale
- $P$: maximize $z=c^Tx$, s.t. $Ax\leq b$, $x \geq 0$
- $D$: minimize $w=b^Ty$, s.t. $A^Ty \geq c$, $y \geq 0$
SE uno dei due problemi ammette una soluzione ottima finita, ALLORA anche l'altro ammette una soluzione ottima finita e i due valori ottimi coincidono

DIM
Sia $y^* \in R^m$ la soluzione ottima finita del duale $D$ e $w^* = b^Ty^*$ il suo valore
Vogliamo dimostrare che $\exists x^* \in R^n : x^* \leq b$, $x^* \geq 0$ e che il suo valore soddisfa la disequazione $c^Tx^* \geq b^Ty^*$

Procedendo per assurdo, supponiamo che tale soluzione $x^*$ del primale $P$ non esista e utilizzando il lemma di Farkas, dimostriamo che in tal caso sarebbe violata l'ipotesi di ottimalità di $y^*$
$\nexists x \in R^n : Ax \leq b, x \geq 0, c^Tx \geq w^*$
$\nexists x \in R^n : Ax \leq b, x \geq 0, -c^Tx \leq -w^*$
Definiamo
$A' = \begin{bmatrix} A \\ -c^T \end{bmatrix}, b' = \begin{bmatrix} b \\ -w^* \end{bmatrix}$
$A'$ di dimensione $(m+1)$ x $n$ e ($m+1$) x 1
$\nexists x \in R^n : A'x \leq b', x \geq 0$

Per il Lemma di Farkas, ciò implica che 
$\exists y' \in R^{m+1} : A'^Ty' \geq 0, b'^Ty' < 0, y' \geq 0$
Sia
$y' = \begin{bmatrix} y \\ \lambda \end{bmatrix}$
con $y \in R^m$ e $\lambda \in R$, allora il sistema equivale a 
$A^Ty-c\lambda \geq 0, b^Ty-w^*\lambda < 0, y  \geq 0, \lambda \geq  0$
Studiamo i casi $\lambda >0$  e $\lambda = 0$
1. $\lambda  > 0$
Dividiamo tutte le disequazione per $\lambda$ e poniamo $\hat{y} = \frac{y}{\lambda}$
$\begin{cases} A^T\hat{y} \geq c \\ b^T \hat{y}<w^* \\ \hat{y} \geq 0 \end{cases}$
Ciò implica che esista una soluzione ammissibile per il duale, il cui valore è minore del valore minimo il che genera una contraddizione
2. $\lambda = 0$
Otteniamo $A^Ty \geq 0, b^Ty^*  = w^*, y^* \geq 0$
Ponendo $\hat{y} = y^*+y$ e osservando che $y^*$ soddisfa le condizioni, si ottiene
$A^T\hat{y} \geq c, b^T\hat{y} < w^*, \hat{y} \geq 0$
Anche in questo caso si ha una contraddizione perche $\hat{y}$ è una soluzione ammissibile per il duale e il suo valore è minore del valore minimo

Questa dimostrazione per assurdo consente di affermare che
$\exists x \in R^n : Ax^* \leq b, x^* \geq 0, c^Tx^* \geq w^*$
Per il teorema della dualità in forma debole, non è possibile che $c^Tx^* >w^*$, quindi
$$z^*=c^Tx^*=b^Ty^*=w^*$$


Teorema fondamentale della dualità lineare
Data una coppia primale-duale
- $P$: maximize $z(x)$, s.t. $x \in X$
- $D$: minimize $w(x)$, s.t. $y \in Y$
Esiste una sequenza finita di passi di pivot che porta l'algoritmo del simplesso a terminare, riconoscendo uno di questi quattro possibili casi
- Soluzione ottima di $P$ e $D$
- $P$ è illimitato e $D$ è inammissibile
- $D$ è illimitato e $P$ è inammissibile
- Sia $P$ che $D$ sono inammissibili

Teorema dello scarto complementare
- $P$: maximize $z=c^Tx$, s.t. $Ax\leq b$, $x \geq 0$
- $D$: minimize $w=b^Ty$, s.t. $A^Ty \geq c$, $y \geq 0$
Condizione necessaria e sufficiente per l'ottimalità di due soluzioni ammissibili $\bar{x}$ e $\bar{y}$ è che valgano le equazioni seguenti
$\bar{y}^T(b-A\bar{x}) = 0$
$(A^T\bar{y} - c)\bar{x} = 0$

OSS stiamo usando la forma alle disuguaglianze, per i vincoli di uguaglianza sono già implicate dall'ammissibilità delle soluzioni.

Esempio

Le lettere che individuano i punti in un problema corrispondono al punto con lettera in maiuscolo/minuscolo nell'altro problema secondo lo scarto complementare
OSS $\in X$ indica se la soluzione sia ammissibile
D/d è l'unica soluzione ammissibile per entrambi


Algoritmo del simplesso duale
Osservazione
Dato che i coefficienti di $P$ e $D$ sono gli stessi, entrambi i problemi di coppia primale-duale si possono rappresentare sullo stesso tableau

Esempio

Tableau ristretto

Data questa osservazione, è possibile lavorare sul tableau del problema primale, eseguendo su di esso gli stessi passi di pivot che l'algoritmo del simplesso eseguirebbe se lavorasse sul tableau del problema duale
L'algoritmo risultante è l'algoritmo del simplesso duale
Simplesso primale: conserva l'ammissibilità e persegue l'ottimalità
Simplesso duale: conserva l'ottimalità e persegue l'ammissibilità
Nell'algoritmo del simplesso duale le regole di scelta del pivot sono duali:
- la riga del pivot viene scelta prima della colonna: il suo termine noto deve essere negativo (vincolo violato)
- il pivot deve essere negativo
- la colonna del pivot viene scelta minimizzando il valore assoluto del rapporto tra il coefficiente di costo ridotto ed il candidato pivot

L'algoritmo del simplesso duale è  utile quando la base è inammissibile e super-ottima
E' una tipica situazione che si verifica negli algoritmi "cutting planes", che vengono usati per risolvere rilassamenti continui di problemi di PL intera o binaria


Iterazione del simplesso duale: nel problema duale, nella colonna del -4, scelgo il pivot scegliendo il minimo tra 1/1 e 2/1, scegliendo quindi la prima riga

Iterazione: nel problema duale scelgo la colonna -2, scegliendo il pivot 2

Analisi post-ottimale
Si possono fare in maniera semplice con i problemi PL
Dopo aver calcolato la soluzione ottima del problema, MA prima di prendere una decisione conseguente, è importante valutare la robustezza della soluzione
I dati sono spesso affetti da errori, approssimazioni

Quanto è robusta la soluzione ottima rispetto a possibili cambiamenti nel valore dei dati che sono stati usati per calcolarla?

- Analisi di sensitività

Input (dati che cambiano): $A$, $b$, $c$
con 
- $A$ matrice dei coefficienti dei vincoli
- $b$ termini noti
- $c$ coefficienti della funzione obiettivo
Output: $B^*$, $x^*$, $z^*$
con
- $B^*$ la base ottima
- $x^*$ il valore delle variabili
- $z^*$ la soluzione ottima

Scopo: valutare l'intervallo nel quale puo variare ogni coefficiente $c_j$ e $b_i$ SENZA che cambi la base ottima $B^*$
La base rimane ottima finche valgono le condizioni di ammissibilità e di ottimalità
- Ammissibilità: $x_B = B^{-1}b \geq 0$
- Ottimalità: $\bar{c}_N = c_N - c_BB^{-1}N \geq 0$
Le condizioni di ammissibilità dipendono solo da $b$
Le condizioni di ottimalità dipendono solo da $c$


Variazione di un coefficiente $c_j$
Intuizione geometrica

Quando $c_1$ diminuisce, pesa meno nella funzione obiettivo, tanto che per $c_1 = 1$ la base ottima cambia
Quando $c_1$ aumenta, le curve di livello tendono a diventare verticali per $c_1 -> \infty$ e quindi la base ottima non cambia
$B^* = \{1, 2, 3\}$ è ottima per $1 \leq c_1 < \infty$
OSS anche se $B^*$ e $x^*$ non cambia, $z^*$ cambia


Supponiamo di analizzare un problema che nella forma alle disuguaglianze ha 
- funzione obiettivo da massimizzare 
- vincoli di disuguaglianza $\leq$
Considerando la colonna $\bar{j}$ e $\Delta c_{\bar{j}}$ la variazione possibile
1. $\bar{j} \in B$ e $\bar{r}$ è la riga corrispondente
$$\max\{-\infty, \max_{j \in N}\{\frac{-c_j^*}{a^{*+}_{\bar{r}j}}\}\} \leq \Delta c_{\bar{j}} \leq \min\{\min\{\frac{-c_j^*}{a^{*+}_{\bar{r}j}}\} + \infty\}\}$$
Interpretazione: per i valore negativi (numeratore negativi e denominatore positivo) cerchiamo il max mentre di quelli positivi il min, che sono i primi valori che ci fanno cambiare base
2. $\bar{j} \in N$
$$\Delta c_{\bar{j}} \leq c^*_{\bar{j}}$$

Esempio

Variazione di un coefficiente $b_i$
Intuizione geometrica

Quando $b_3$ diminuisce, il vincolo 3 trasla verso il basso e a sinistra finche il vincolo 2 diventa attivo con $b_3 = 8$
Quando $b_3$ aumenta, il vincolo 3 trasla verso l'alto e a destra finche il vincolo 1 diventa attivo con $b_4 = 24$

Quindi $B^* = \{1,2,3\}$ è ottima per $8 \leq b_3 \leq 24$
OSS anche se $B^*$ non cambia, $z^*$ e $x^*$ cambiano

Supponiamo di analizzare un problema che nella forma alle disuguaglianze ha 
- funzione obiettivo da massimizzare 
- vincoli di disuguaglianza $\leq$
Considerando una riga $\bar{i}$ e sia la colonna della variabile di slak $\bar{j}$ e $\Delta b_{\bar{i}}$ la variazione possibile
1. $\bar{i} \in B$
$$\max\{-\infty, \max_{i}\{\frac{-b_i^*}{a^{*+}_{i\bar{j}}}\}\} \leq \Delta b_{\bar{i}} \leq \min\{\min_{i}\{\frac{-b_i^*}{a^{*+}_{i\bar{j}}}\} + \infty\}\}$$
Interpretazione: per i valore negativi (numeratore negativi e denominatore positivo) cerchiamo il max mentre di quelli positivi il min, che sono i primi valori che ci fanno cambiare base
2. $\bar{i} \in N$
$$\Delta b_{\bar{i}} \geq -x^*_{\bar{j}}$$

- Analisi parametrica
Studia come $z^*$ dipende dal valore del termine noto di un vincolo prescelto
Il risultato è una funzione lineare a tratti: ogni suo segmento corrisponde ad una base ottima ed ogni punto di discontinuità ad un cambio di base


Interpretazione economica della PL

1. le n variabili rappresentano le quantità prodotte per gli n prodotti
2. i coefficienti rappresentano i profitti unitari
3. i termini noti rappresentano le quantita di risorsa disponibili

I c.c.r. delle colonne di slack all’ottimo indicano i prezzi-ombra delle corrispondenti risorse, cioe il massimo prezzo a cui conviene comprare la risorsa e il minimo prezzo a cui conviene venderla. Il prezzo-ombra di risorse non scarse e nullo.

il costo ridotto $\bar{c}_j - \sum_{i}{a_{ij}\lambda_i}$
dove 
- $c_j$ coefficiente di $x_j$ nella funzione obiettivo
- $a_{ij}$ coefficiente sulla riga $i$ e colonna $j$ nella matrice dei vincoli
- $\lambda _i$ è il prezzo ombra del vincolo $i$

---

Programmazione lineare a molti obiettivi
Programmazione lineare a molti obiettivi è l'estensione della programmazione matematica in cui ci siano piu funzioni obiettivo in conflitto tra loro (il miglioramento di una funzione porta il peggioramento dell'altra)

Ci limitiamo a considerare programmazione lineare con due obiettivi

Fasi
- Prima fase: calcolo della regione Pareto-ottima, l'insieme delle soluzioni ammissibili non dominate
- Seconda fase: scelta di una soluzione tra quelle Paretiane individuate nella fase uno

La prima fase è algoritmica mentre la seconda implica scelte del decisore
SE gli obiettivi sono in conflitto, nessuna decisione è ottima
Il concetto di soluzione ottima viene quindi sostituito da quello di soluzione non dominata

Prima fase
Dominanza
Dati gli obiettivi $f_1(x), ..., f_k(x)$ da minimizzare e date due soluzioni ammissibili $x'$ e $x''$, 
$x'$ domina $x''$ SE e SOLO SE
$$\begin{cases} f_i(x') \leq f_i(x''), \forall i=1,...,k \\ \exists j \in \{1,...,k\}:f_j(x')<f_j(x'')\end{cases}$$

(in caso di massimizzazione invertire i segni di <)
OSS non ho un confronto tra 2 soluzioni, ma tra coppie di soluzioni
SE una soluzione non è dominata da nessun'altra, allora è una soluzione Pareto-ottima

L'insieme delle soluzioni non dominate è la regione Pareto-ottima del problema

Rappresentazione Regione Pareto-ottima
Le soluzione e la regione Pareto-ottima possono essere rappresentate anche nello spazio 
degli obiettivi
es se le funzioni fossero da massimizzare, A ed E domina B

Metodo dei pesi
Il metodo dei pesi consiste nell'ottimizzare una combinazione convessa delle funzioni obiettivo

Date maximize $f_1(x), ...,$ maximize $f_k(x)$ s.t. $x \in X$
maximize $\sum_{i=1}^{k}{\lambda _if_i(x)}$ s.t. $x \in X$
con $\lambda _i \geq 0 \forall i=1,...,k$ e $\sum_{i=1}^{k}{\lambda _i = 1}$

La soluzione ottima del problema risultante dipende dal vettore di pesi $\lambda$ (scelti arbitrariamente)
Con due obiettivi lineari e vincoli lineari si puo calcolare la regione Paretiana con l'analisi parametrica
OSS l'analisi parametrica è fatta su $\lambda$ è nell'obiettivo e NON nei termini noti MA non è un problema grazie alla dualità

Esempio

Metodo dei vincoli
Il metodo dei vincoli consiste nell'ottimizzare una delle funzioni obiettivo trasformando le altre in vincoli con un termine noto parametrico

Date maximize $f_1(x), ...,$ maximize $f_k(x)$ s.t. $x \in X$
maximize $f_1(x)$ s.t. $x \in X$, $f_i \geq \beta  _i, \forall i =2,...,k$

La soluzione ottima del problema risultante dipende dal vettore dei termini noti $\beta$
Con due obiettivi lineari e vincoli lineari si puo calcolare la regione Paretiana con l'analisi parametrica

Esempio

Regioni paretiane continue e discrete
Per problemi lineari nel continuo, il metodo dei pesi e dei vincoli generano correttamente la regione paretiana
Per problemi lineare nel discreto, il metodo dei pesi in generale non garantisce di trovare tutte le soluzioni paretiane

es non esiste una combinazione t.c. riesca a trovare una soluzione ottima nel punto segnato

Seconda fase
La seconda fase del processo decisionale puo essere supportata da metodi quantitativi anche se richiede una scelta da parte del decisore
- Metodo delle curve di indifferenza
La soluzione scelta è quella in cui delle curve di indifferenza risulta tangente alla regione Paretiana

es ipotizzando di voler massimizzare $f_1$ e $f_2$

Alcune curve di indifferenza comunemente usate per avere un'espressione analitica
$w(f(x)) = [\sum_{i=1}^{k} (\lambda _i f_i(x))^p]$

es con $k=1$ e $\lambda _1 = \lambda _2 = 1$


- Criterio del punto di massima curvatura 
La soluzione scelta è quella per cui ad un piccolo miglioramento di un obiettivo corrisponde un grande peggioramento dell'altro

es

- Criterio del punto utopia
Il punto utopia è la soluzione che nello spazio degli obiettivi ha come coordinate i valori ottimi di ciascuno
Ovviamente se siamo in un contesto di programmazione a molti obiettivi il punto utopia non sarà ammissibile

es possiamo prendere il punto utopia e dall'origine vedere se c è un punto ammissibile che passa per la retta

- Criterio degli standard
Gli standard sono valori soglia al di sotto dei quali non si vuole che gli obiettivi possano peggiorare

es stavolta dato un S ammissibile, posso per esempio vedere se c è un punto che passa per la retta dall origine alla regione Pareto-ammissibile


---

PLI
Esistono diverse classi di problemi di ottimizzazione con variabili discrete
- IP Integer Programming: variabili vincolate ad assumere valori interi
- BP Binary Programming: variabili vincolate ad assumere solo due valori
- MIP Mixed Integer Programming: alcune variabili discrete e alcune continue
- CO Combinatorial Optimization: delle variabili indicano gli elementi dell insieme 
Noi consideriamo solo modelli lineari PLI

NON si puo calcolare la derivata, NON si puo considerare il vertice del poliedro perche potrebbe avere coordinate non intere
Per ottimizzare nel discreto possiamo
- selezionare buone formulazioni lineari e migliorarle fino a poterle risolvere un problema di PLI come PL
- scomporre il problema in sottoproblemi piu piccoli e piu facili
- eseguire una enumerazione implicita delle soluzioni

Dato un problema di ottimizzazione discreta P
$$z^* = max{z(x) : x \in X \subseteq Z^n}$$
L'ottimalità si dimostra calcolando un upper bound $\bar{z}$ e un lower bound $\underline{z}$ t.c. $\underline{z} \leq z \leq \bar{z}$
SE P è di minimizzazione, $\bar{z}$ è primale e $\underline{z}$ è duale
SE P è di massimizzazione, $\underline{z}$ è primale e $\bar{z}$ è duale
La differenza $\bar{z}-\underline{z}$ è detto gap di ottimalità
SE $\bar{z}-\underline{z} = 0$, si ha la garanzia di ottimalità

Un bound primale $\bar{z}$ è dato dal valore della funzione obiettivo $z(x)$ in una qualsiasi soluzione ammissibile $\bar{x} \in X$
$$\bar{z} = z(\bar{x}), \bar{x} \in X$$
Il bound primale puo essere calcolato in vari modi
- algoritmi euristici/meta euristici
- algoritmi di approssimazione con garanzia (in tal caso si ha anche un bound duale)
Per alcuni problemi di ottimizzazione discreta è difficile trovare una soluzione ammissibile

Il bound duale è dato dal valore della funzione obiettivo in z(x) in corrispondenza di una soluzione super ottima $\bar{x}$ in generale non ammissibile

Tecniche principali
- risolvere all'ottimo un rilassamento R di P
- trovare una soluzione ammissibile al duale D di P
OSS nel discreto il teorema della dualità in forma debole resta vero mentre quello in forma forte in generale non è piu vero

Rilassamento
Dato un problema $P = min\{z_P(x) : x \in X(P)\}$
un problema $R = min\{z_R(x) : x \in X(R)\}$
è un rilassamento di P SE valgono
- $X(P) \subseteq X(R)$ //sulle regioni ammissibili
- $z_R(x) \leq z_P(x), \forall x \in X(P)$ //sugli obiettivi
OSS in caso di massimizzazione le disequazioni sono invertite

Corollario: $z^*_R \leq z^*_P$
Ci sono molti tipi di versi di rilassamento
Un rilassamento è tanto migliore quando piu il suo valore ottimo è vicino a $z^*_P$

- Rilassamento lineare continuo
Quando P è un problema di ottimizzazione discreta, il suo rilassamento continuo C è ottenuto da P trascurando le condizioni di integralità
$$P: min\{z(x) \in X, x \in Z^n_+\}$$
$$C: min\{z(x) \in X, x \in R^n_+\}$$
Quando P è un problema di ottimizzazione lineare discreta, il suo rilassamento continuo LP è un problema di programmazione lineare
$$P: min\{cx:Ax \leq b, x \in Z^n_+ \}$$
$$LP: min\{cx:Ax \leq b, x \in R^n_+ \}$$
SE $x^*_{LP} \in Z^n_+$ ALLORA $x^*_P=x^*_{LP}$

- Rilassamenti combinatori
Il rilassamento combinatorio C di un problema di ottimizzazione combinatoria P è ancora un problema di ottimizzazione combinatoria ma tipicamente molto piu facile da risolvere

- Rilassamento Lagrangeano
Il rilassamento Lagrangeano LR di un problema di ottimizzazione lineare discreto P si ottiene rimuovendo alcuni vincoli e aggiungendo all'obiettivo termini di penalità per la loro violazione
$$P: min\{z(x): Ax \leq b, x \in X \subseteq Z^n_+\}$$
$$LR: min\{z_{LR}(x, \lambda) = z(x) + \lambda (Ax-b) : x \in X \subseteq Z^n_+ \}$$
con $\lambda \geq 0$ moltiplicatori lagrangiani

Esso soddisfa le condizioni per essere un rilassamento
- Vincoli: $\{x: Ax \leq b, x \in X\} \subseteq \{x:x \in X\}$
- Obiettivo
	- $Ax -b \leq 0$ per tutte le soluzioni ammissibili per P
	- $\lambda (Ax-b) \leq 0$ per tutte le soluzioni ammissibili per P
	- $z_{LR}(x, \lambda) = z(x) + \lambda (Ax-b) \leq 0$ per tutte le soluzioni ammissibili per P

- Rilassamento surrogato
Il rilassamento surrogato S di un problema di ottimizzazione lineare discreto P si ottiene sostituendo un insieme di vincoli con un loro combinazione convessa
$$P: min\{z(x): Ax \leq b, x \in X \subseteq Z^n_+\}$$
$$LR: min\{z(x) : \lambda ^TAx \leq \lambda^T b, x \in X \subseteq Z^n_+\}$$
con $\lambda \geq 0$

Esso soddisfa le condizioni per essere un rilassamento
- Vincoli: $Ax \leq b$ implica $\lambda ^TAx \leq \lambda^T b$ MA non viceversa
- Obiettivo: non cambia


Si puo dimostrare che, scegliendo i migliori moltiplicatori $\lambda$, in caso di minimizzazione
$$z^*_{LP} \leq z^*_{LR} \leq  z^*_S \leq z^*$$

Dualità
Problema lineare duale
$$P: z^* = min\{cx: Ax \geq b, x \in R^n_+\}$$
$$D:w^* = max\{yb: yA \leq c, y \in R^m_+\}$$

Formulazioni lineari
I problemi di ottimizzazione lineare discreti NON hanno un unica formulazione
Ha senso quindi
- confrontare formulazioni
- migliorare formulazioni
Una formulazione migliore si traduce in un algoritmo piu efficiente

La formulazione ideale di un problema di programmazione lineare discreta è quella che consente di risolverlo come se fosse un problema di programmazione lineare nel continuo

La formulazione di un problema di programmazione lineare corrisponde ad un poliedro, e ce sono infiniti che racchiudono le soluzioni
I vincoli della formulazione ideale corrispondono al guscio convesso delle soluzioni intere

Guscio convesso
Dato un insieme discreto X, il suo guscio convesso è il poliedro
$$X = \{x_1,  ..., x_t\}, x_i \in R^n,  \forall i=1,..., t$$
$conv(X) = \{x \in R^n : x = \sum_{i=1}^t \lambda_i x_i, \sum_{i=1}^t \lambda _i = 1, \lambda _i \geq 0, \forall i =1,...,t\}$
E' un poliedro i cui punti estremi sono elementi dell'insieme discreto X
Data una formulazione P e l'insieme discreto X delle sue soluzioni ammissibili vale
$$X \subseteq conv(X) \subseteq P$$
In generale non conosciamo la formulazione ideale dei problemi di ottimizzazione lineare discreta (es problema del cammino minimo su grafo...)
Il numero dei vincoli del guscio convesso puo crescere esponenzialmente con la dimensione dell'istanza

Conosciamo la formulazione ideale solo per alcuni problemi di ottimizzazione discreta
La disciplina che studia tale questione è la polyhedral combinatorics


Algoritmi cutting planes
Dato un problema di PLI (all iterazione $k$), consideriamo il suo rilassamento continuo e la sua soluzione ottima $x^{*(k)}$
$$P^{(k)} = max\{cx : Ax \leq b, x \in Z^n_+\}$$
$$L^{(k)} = max\{cx : Ax \leq b, x \in R^n_+\}$$
Generiamo un insieme di disuguaglianze valide/cutting planes $Qx \leq q$ t.c.
- $Qx \leq q, \forall x \in Z^n_+ : Ax \leq b$ //non devono escludere nessuna soluzione ammissibile
- $Qx^{*(k)} > q$ //devono rendere inammissibile il punto frazionario $x^{*(k)}$
e otteniamo cosi una formulazione piu stretta
$$P^{(k+1)} = max\{cx : Ax \leq b, Qx \leq q, x \in Z^n_+\}$$
es

Procedura di Chvatal-Gomory
Considerando un problema di PLI con insieme ammissibile
$$X = \{x \in Z^n_+ : Ax \leq b\}$$
dove A ha $m$ righe e $n$ colonne
Scegliamo un vettore $u \in R^n_+$
- $\sum_{j=1}^{n}{ua_jx_j} \leq ub$ è valida perche $ax \leq b$ e $u \geq 0$ 
- $\sum_{j=1}^{n}{\lfloor{ua_j}\rfloor x_j} \leq ub$ è valida perché $x \geq 0$
	- arrotondando per difetto vuol dire mantenere uguale o diminuire il primo membro
- $\sum_{j=1}^{n}{\lfloor{ua_j}\rfloor x_j} \leq \lfloor ub \rfloor$ è valida perché $x$ è intero
	- arrotondando per difetto anche il secondo termine vuol dire mantenere uguale o anche il secondo 0

Otteniamo quindi una disuguaglianza valida MA la sua efficienza dipenda dalla scelta di $u$
Ogni disuguaglianza valida puo essere generata con questa procedura in un numero finito di passi


Algoritmi cutting planes
Gli algoritmi cutting planes iterativamente risolvono il rilassamento continuo L di un problema discreto P e rafforzano la sua formulazione generando ulteriori vincoli (cutting planes) in modo tale che la soluzione ottima di rilassamento continuo all'iterazione $k$ diventi inammissibile all'iterazione $k+1$
Vantaggi: 
- SE i piani di taglio sono generati in modo efficace, l'algoritmo di trovare la soluzione ottima discreta
- una formulazione piu ristretta puo fornire bounds duale (non ideali) utilizzabili in algoritmi branch-and-bound (algoritmi branch and cut)
Svantaggio:
- Non ci da garanzie su quanti passi ci vogliono per arrivare all ottimo
- è necessaria una procedura apposita, algoritmo di separazione, per generare iterativamente disuguaglianze valide e utili
	- SE il problema è NP-hard, anche il problema di separazione lo è

Pseudo codice
Begin
//con $P$ il rilassamento continuo e $t$ indice dell'iterazione
t := 0; $P^{(0)}$ := $P$; 
repeat
	// risolvo il problema rilassato con $z^{*(t)}$ il valore ottimo e $x^{*(t)}$ la soluzione ottima
	$z^{*(t)} := max\{cx : x \in P^{(t)}\}$ 
	$x^{*(t)} := argmax\{cx : x \in P^{(t)}\}$ 
	if  $x^{*(t)} \notin Z^n$ then // soluzione ottima non intera
		genera un disuguaglianza valida $\pi x \leq \pi_0 : \pi x^{*(t)} > \pi_0$
		$P^{(t+1)} := P^{(t)} \cap \{x : \pi x \leq \pi_0\}$
		t := t+1
	end if
until $(x^{*(t)} \in Z^n)$ AND non riusciamo a trovare nessuna disuguaglianza valida (ANCHE SE esiste)
End

Dopo ogni iterazione, $z^{*(t)}$ è un bound duale valido che si avvicina sempre piu all ottimo

Tagli di Gomory
A differenza di quando usiamo un algoritmo di separazione euristico, con i tagli di Gomory si riesce sempre ad andare avanti. Usano la procedura di Chvatal-Gomory

Data una soluzione frazionaria $x^*$ del rilassamento continuo di un problema di PLI, si utilizza la procedura di Chvatal-Gomory sul vincolo associato a una variabile frazionaria in modo da ottenere una disuguaglianza valida violata da $x^*$

Dato un problema P di PLI e il suo rilassamento continuo LP
$$P) max\{cx : ax = b, x\geq 0, x \in Z^n\}$$
$$LP) max\{cx : ax = b, x\geq 0\}$$
siano $x^*$ e $z^*$ la sua soluzione ottima di LP e il suo valore 
$z^* = \overline{a}_{00} + \sum_{j \in NB^*}{\overline{a}_{0j}x_j^*}$
$$\begin{cases} x^*_{B*i} + \sum _{j \in NB^*}{\overline{a}_{ij} x^*_j = \overline{a}_{i0}, \forall i = 1,...,m} \\ x^* \geq 0 \end{cases}$$

La soluzione ottima sappiamo che è la somma di una costante (in alto a sinistra nel tableau) e dalla somma delle colonne fuori base (NB) dei coefficienti che leggo sulla riga 0 del tableau moltiplicate per le $x^*_j$
variabili in base piu la somma delle altre deve dare il termine nodo della riga

SE $x^*$ non è intero, esiste almeno un involo $\hat{i}$ t.c. $\overline{a}_{\hat{i}0}$ non è intero
Eseguendo la procedura di Chvatal-Gomory su di esso si ottiene
$$x_{B*\hat{i}} + \sum _{j \in NB^*}{\lfloor\overline{a}_{\hat{i}j} \rfloor x_j} \leq \lfloor\overline{a}_{\hat{i}0}\rfloor$$
Sottraendo questa disuguaglianza dal vincolo di uguaglianza (riportata di seguito)
$$x^*_{B*\hat{i}} + \sum _{j \in NB^*}{\overline{a}_{\hat{i}j} x^*_j} = \overline{a}_{\hat{i}0}$$
Si ottiene il taglio di Gomory
$$\sum _{j \in NB^*}{f_{\hat{i}j}x_j \geq f_{\hat{i}0}}$$
Dove 
- $f_{\hat{i}j} = \overline{a}_{\hat{i}j} - \lfloor \overline{a}_{\hat{i}j} \rfloor$
- $f_{\hat{i}0} = \overline{a}_{\hat{i}0} - \lfloor \overline{a}_{\hat{i}0} \rfloor$
- Anche la variabile di slack associata a questa disuguaglianza è intera

es

---

Branch-and-bound
In un algoritmo branch-and-bound
Dato un problema difficile $P$, viene ricorsivamente scomposto in piu sottoproblemi $F_1, ...,F_n$ piu facili
La scomposizione/branching/ramificazione deve rispettare una condizione per assicurare la correttezza dell'algoritmo (non perdere la soluzioni ottime dei figli)
$$X(P) = \bigcup_{i=1}^{n}{X(F_i)}$$
La soluzione ottima di $P$ è determinata confrontando le soluzioni ottime dei sotto problemi originati da esso
es in caso di minimizzazione
$$z^*(P) = min_{i=1,...,n}\{z^*(F_i)\}$$
La scomposizione ricorsiva di problemi genera un'arborescenza o decision tree o search tree in cui la radice corrisponde al problema originale $P$ ed ogni altro nodo corrisponde ad un sotto problema


Branching
A scopo di efficienza, la scomposizione implica una partizione di X(P) in sottoinsiemi disgiunti di modo che nessuna soluzione debba essere considerata piu di una volta
$$X(F_i) \cap X(F_j) = 0, \forall i \neq j = 1,...,n$$
Modi per fare branching
- Fissare le variabili
- Inserire dei vincoli
Ogni sotto problema è una restrizione del suo predecessore ed un rilassamento dei suoi successori

Branching binario
Regole di branching comuni
- Branching su una variabile binaria
Viene selezionata una variabile binaria $x$ (solitamente una variabile che ha un valore frazionario, quindi sto impedendo la soluzione del padre)
Due sotto problemi vengono generati fissando $x=0$ e $x=1$ 
- Branching su un vincolo intero
Vengono scelti un vettore di variabili intere ($x_1$, ..., $x_n$), un opportuno vettore di coefficienti interi ($a_1$, ..., $a_n$) e un opportuno termine noto intero $k$
Vengono generati due sotto problemi inserendo i vincoli $ax \leq k$ e $ax \geq k+1$

Branching n-ario
Regole di branching n-ario
- Branching su una variabile intera
Viene selezionata una variabile intera $x \in [1, ..., n]$
Vengono generati n sotto problemi fissando $x=1$, ..., $x=n$
- Branching su $n$ variabili binarie
Viene scelto un vettore di $n$ variabili binarie ($x_1$, ..., $x_n$)
Vengono generati $n+1$ sotto problemi fissando alcune variabili (una riga per ogni problema)
Potrebbe sembrare che si generi un albero sbilanciato se una parte scelgo un numero piu alto/basso di variabili rispetto ad un altra zona. Di solito gli alberi di branch si cerca di tenerli bilanciati MA in realta ciò che conta non sono il numero di variabili, ma l'effetto vincolante delle variabili fissate (es x=0 non conta niente, x=1 ha un effetto forte)



es fissaggio di variabili
es inserzione di vincoli

Foglie dell'albero
La procedura ricorsiva di branching termina quando il sotto problema corrente 
- è inammissibile
- è risolto all ottimo
- puo essere trascurato
Tutti i casi si possono rilevare risolvendo un rilassamento del sotto problema corrente

Rilassamenti
Dato un problema P, un problema R è un rilassamento di P
minimize $z_P(x)$ s.t. $x \in X_P$
minimize $z_R(x)$ s.t. $x \in X_R$
SE e SOLO SE valgono le due condizioni
- $X_P \subseteq X_R$
- $z_R(x) \leq z_P(x), \forall x \in X_P$

Il valore ottimo del rilassamento non è mai peggiore del valore ottimo del problema originale
$z^*_R \leq z^*_P$

Corollario 1: SE $R$ è inammissibile, anche $P$ è inammissibile
Corollario 2: SE $x^*$ è ottima per $R$ ed è ammissibile per $P$ e $z_R(x)=z_P(x)$, ALLORA $x^*$ è ottima anche per $P$
Corollario 3: SE $z^*_R \geq \overline{z}$, ALLORA $z^*_P \geq \overline{z}$ (SE la soluzione ottima del problema rilassato è peggiore di una soluzione ammissibile che conosciamo, allora tutte le soluzione del problema originario sono peggiore, QUINDI sono trascurabili)
Il corollario 3 è utilizzato nell'operazione di bounding

Bounding
Il bounding consiste nell'associare un bound duale ad ogni sotto problema $F$
Poiché $z^*_R \leq z^*_P$, il valore ottimo $R(F)$ fornisce un bound duale ogni sotto problema $F$
$$z^*_{R(F)} \leq z^*_F$$
Il bound duale è confrontato con un bound primale che corrisponde al valore $z_P(\overline{x})$ di una soluzione ammissibile $\overline{x} \in X(P)$
SE il bound duale di $F$ risulta essere non migliore del bound primale, ALLORA $F$ puo essere scartato
if $z^*_{R(F)} \geq z_P(\overline{x})$ then Fathom $F$

La correttezza è data dalla concatenazione di due disuguaglianze
1. Nessuna soluzione puo esistere in $X(F)$ con un valore migliore di $z^*_{R(F)}$ poiché
$$z^*_F \geq z^*_{R(F)}$$
2. $z^*_{R(F)} \geq z_P(\overline{x})$
Concatenando:
$$z_F^* \geq z^*_{R(F)} \geq z_P(\overline{x})$$
Significa che risolvere un problema $F$ all'ottimo è inutile, poiche non fornirà una soluzione migliore di quella gia nota $\overline{x}$

OSS Scartare sotto-problemi è cruciale per risparmiare tempo e memoria

es ho due sottoproblemi divisi da un branching orizzontale. Sapendo che esiste una soluzione ammissibile $\overline{x}$, per il problema rosso la curva di livello che rappresenta la soluzione ottima nel continuo è peggiore della tratteggiata nera, quindi il sotto problema rosso puo essere scartato

Strategia di visita dell'albero
Ogni volta che due o piu sotto problemi vengono generati, essi vengono appesi ad una lista di nodi aperti, cioe sotto problemi da risolvere

La politica seguita per decidere quali nodi visitare per primi è detta search strategy.
Il sotto problema corrente è quello che viene risolto ad un generico istante durante l'esecuzione

Criteri 
- FIFO
- LIDO
- Lista ordinata: best first search (basata sul valore del bound duale) (si utilizza un heap)

---

Modelli di ottimizzazione discreta
Variabili binarie
Molto spesso le variabili nei problemi di ottimizzazione rappresentano quantita che possono essere sia continue che discrete

- Le variabili binarie rappresentano scelte logiche con un dominio {0, 1}
Cioe quando
- non hanno un'unita di misura 
- non ammettono approssimazioni

Le variabili binarie hanno un enorme importanza dal punto di vista modellistico
$x_i = 1$ SE capita l'evento $i$
$x_i = 0$ SE NON capita l'evento $i$

- Le relazioni tra variabili binarie esprimono condizioni logiche

| Condizione                   | Significato                                               |
| ---------------------------- | --------------------------------------------------------- |
| $\sum_{i=1}^{N}{x_i} \leq 1$ | Non deve capitare piu di uno tra N eventi                 |
| $\sum_{i=1}^{N}{x_i} = 1$    | Deve capitare uno tra N possibili eventi                  |
| $\sum_{i=1}^{N}{x_i} \geq 1$ | Deve capitare almeno uno di N possibili eventi            |
| $x_1=x_2$                    | I due eventi devono capitare entrambi o nessuno dei due   |
| $x_1 \leq x_2$               | L'evento 1 puo verificarsi solo se si verifica l'evento 2 |
- Le variabili binarie sono usate per selezionare sotto insiemi di un insieme
$$\sum_{i=1}^{N}{c_ix_i} \Leftrightarrow \sum_{i \in S}{c_i}$$
dove $S$ è un sottoinsieme di {$1, ..., N$} corrispondente al vettore $x$
$$x_i = \begin{cases} 1, i \in S \\ 0, i \notin S \end{cases}$$
Le variabili binarie sono usate per eliminare i "se" dai modelli
$$\begin{cases} 0 \leq y \leq u, \text{SE } x= 1 \\ y=0, \text{SE } x=0 \end{cases} \Leftrightarrow 0 \leq y  \leq ux$$
es costi fissi

- Le variabili binarie possono essere usate anche per attivare e disattivare i vincoli
Dato il vincolo, aggiungendo M abbastanza grande
$$y \leq Q + Mx$$
Qualunque sia il valore di y, in realta dopo aver aggiunto Mx il vincolo risulta soddisfatto e quindi è come se lo disattivassi
Equivale a 
$$\begin{cases} y \leq Q, \text{SE } x = 0 \\ y, \text{SE } x = 1 \end{cases}$$

es vincoli disgiunti
$$|a-b|\geq k$$
essendo $a$ e $b$ due variabili continue non negative e $k >0$
Il vincolo non è lineare ed è un vincolo disgiunto
$$|a-b|\geq k \Leftrightarrow (a-b \geq k) \text{ OR } (a-b  \leq -k)$$
Si puo linearizzare introducendo una variabile binaria $x$ ed una costante $M$ grande
$$\begin{cases} a-b\geq k - Mx \\ a-n \leq -k+M(1-x) \end{cases}$$
A seconda del valore di x, uno dei due vincoli viene imposto mentre l'altro risulta disattivato

es regioni ammissibili non convesse 
es problema dello scheduling

---

Programmazione non lineare - PNL
La programmazione non lineare studia problemi di ottimizzazione in cui la funzione obiettivo o alcuni vincoli sono non lineari

Forma generale
minimize $z = f(x)$
s.t. $h_i(x) = 0, \forall i$
$g_j(x) \leq 0, \forall j$
$x \in R^n$

Dove $f(x)$, $g(x)$ e $h(x)$ possono essere funzioni non lineari

Proprieta:
- La soluzione ottima puo non essere all'intersezione dei vincoli
![[Pasted image 20240328164131.png]]
- La soluzione ottima puo non essere necessariamente sulla frontiera della regione ammissibile
![[Pasted image 20240328164213.png]]

Soluzione ottima locale e globale
In generali gli algoritmi PNL garantiscono solo l ottimalità locale
Una soluzione $x^* \in X$ è un minimo globale SE e SOLO SE 
$$f(x^*) \leq f(x), \forall x \in X$$
Una soluzione $\overline{x} \in X$ è minimo locale SE e SOLO SE
$\exists \epsilon > 0 : f(\overline{x}) \leq f(x), \forall x \in X : ||\overline{x}-x|| \leq \epsilon$
L'insieme delle soluzioni $x \in X : ||\overline{x}-x|| \leq \epsilon$ è un intorno di $\overline{x}$
es le soluzioni $x_1$ e $x_2$ sono ottimi locali mentre $x_3$ è un ottimo globale
![[Pasted image 20240328164435.png]]

Per trovare un ottimo globale si dovrebbero enumerare tutti gli ottimi locali e scegliere il migliore
Tuttavia l'enumerazione completa degli ottimi locali in generale non è fattibile in pratica sia per il loro grande numero sia perché non è noto un metodo algoritmico per eseguirla in modo efficiente

Un'importante eccezione positiva è la programmazione convessa
Un problema di minimizzazione non lineare è convesso quando
- la funzione obiettivo è una funzione convessa
	- Una funzione è convessa SE e SOLO SE per ogni copia di punti x_1 e x_2 nel suo dominio e per $0 \leq \lambda \leq 1$
		$$f(\lambda x_1+(1-\lambda)x_2) \leq \lambda f(x_1)+(1-\lambda)f(x_2)$$
- la regione ammissibile è un insieme convesso
	-  Un insieme X è convesso SE e SOLO SE per ogni coppia di punti x_1 e x_2, tutte le loro combinazioni convesse appartengono all'insieme
		$$\forall x_1,x_2 \in X, \forall 0 \leq \lambda \leq 1, \lambda x_1 + (1-\lambda)x_2 \in X$$
		es![[Pasted image 20240328165627.png]]

Programmazione convessa
1. La regione ammissibile è convessa SE
	- TUTTI i vincoli di uguaglianza h(x) = 0 sono lineari
	- tutti i vincoli di disuguaglianza, riscritti come $g(x) \leq  0$ sono convessi
2. La funzione obiettivo da minimizzare deve essere convessa
SE entrambe le condizioni  sono soddisfatte, il problema è di programmazione convessa e ciò garantisce che 
- ottimalità locale implica quella globale
- SE esistono piu ottimi, essi formano un insieme convesso


Ottimizzazione vincolata e non vincolata
Distinguiamo tra
- Unconstrained NLP: minimizzare una funzione non lineare senza alcun vincolo
- Constrained NLP: minimizzare $f(x)$ con $x \in X$: le non linearità possono essere sia nell'obiettivo che nei vincoli

Ottimizzazione non vincolata
Assumiamo che la funzione obiettivo $f(x)$ da minimizzare sia continua e differenziabile
Il gradiente di una funzione $f(x_1, ..., x_n)$ è il vettore delle su derivate parziali di primo ordine
$$\bigtriangledown f(x) = [\frac{\partial f}{\partial x_1}...\frac{\partial f}{\partial x_n}]^T$$
L'Hessiano di una funzione $f(x_1, ..., x_n)$ è la matrice delle sue derivate parziali di secondo ordine (matrice simmetrica perchè è indifferente derivare prima per x e poi per y)
![[Pasted image 20240328170725.png]]

Caratterizzazione dei minimi locali
Condizioni necessarie del primo ordine $\bigtriangledown f(\overline{x}) = 0$
Condizioni necessario del secondo ordine $\bigtriangledown ^2 f(\overline{x}) \geq 0$ (semi definita positiva)
Condizioni sufficienti del secondo ordine $\bigtriangledown ^2 f(\overline{x}) > 0$ (definita positiva)

Algoritmi
SE le derivate prime e seconde sono note, si possono enumerare i punti nei quali sono soddisfatte le condizioni analitiche

Gli algoritmi per l'ottimizzazione non lineare sono algoritmi iterativi, che convergono verso un minimo  locale
Partono da una soluzione data $x^{(0)}$ e calcolano una sequenza di soluzioni t.c. il valore di f(x) diminuisca monotonicamente
Si fermano quando il miglioramento ottenuto o il passo compiuto sono piu piccoli di una data soglia

Ad ogni iterazione k, l'algoritmo calcola una direzione $d^{(k)}$ (un vettore) e un passo $s_k$ (uno scalare) t.c. $x^{(k+1)} = x^{(k)} + s_kd^{(k)}$
Caratteristiche che devono avere questi algoritmi
- Convergenza globale: l'algoritmo converge sempre in un minimo locale a partire da qualsiasi punto
Una volta noto che un algoritmo converge in modo globale analizziamo la sua velocita di convergenza
Sia $\{x_k\}$ una sequenza in $R^n$ che converge a $x^*$
- Convergenza lineare: l'errore che commettono rispetto all'iterazione prima è minore di 1
$$\lim _{k-> \infty} \frac{||x_{k+1}-x^*||}{||x_k-x^*||} = r < 1$$
- Convergenza superlineare
$$\lim _{k-> \infty} \frac{||x_{k+1}-x^*||}{||x_k-x^*||} = 0$$
- Convergenza quadratica: considero il quadrato dell'errore dell'iterazione prima (elevando al quadrato è piu piccola perche mi sto avvicinando)
$$\lim _{k-> \infty} \frac{||x_{k+1}-x^*||}{||x_k-x^*||^2} = M$$

Le due principali strategie per costruire algoritmi iterativi che scelgono il passo e la direzione sono
- line search: prima si sceglie la direzione e poi il passo
- trust regions: prima si sceglie il passo e poi la direzione

Negli algoritmi line search, le scelte piu comuni per definire la direzione $d^{(k)}$ sono
- metodo del gradiente: scelgo la direzione opposta a quella del gradiente, $-\bigtriangledown f(x^{(k)})$
- metodo di Newton: scelgo una direzione $-B^-1\bigtriangledown f(x^{(k)})$, con B una matrice semi definita positiva
- metodo del gradiente coniugato: una direzione $-\bigtriangledown f(x^{(k)}) + \beta _kd^{(k-1)}$ che considera anche la direzione del passo precedente

Metodo del gradiente
Per il teorema di Taylor
$f(x^{(k)} + s_kd^{(k)}) = f(x^{(k)}) + s_kd^{(k)T} \bigtriangledown f(x^{(k)}) + ...$
Questa approssimazione decresce piu rapidamente nella direzione opposta a quella del gradiente
$$d^{(k)} = - \frac{\bigtriangledown f(x^{(k)})}{||\bigtriangledown f(x^{(k)})||}$$
Vantaggio: questo metodo (steepest descent method) richiede solo il calcolo del gradiente e non delle derivate seconde


Metodo di Newton