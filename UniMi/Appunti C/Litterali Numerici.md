in c esistono dei tipi chiamati <b><u>narrow type</u></b>. In questa categoria troviamo : 
- <b><u>Bool</u></b>
- <b><u>Unsigned char</u></b>
- <b><u>Unsigned short</u></b>
- Corrispettive varianti signed. 

Questa tipologia <b><u>viene convertita prima delle operazioni aritmetiche a</u></b> <span style=color:yellow>signed int </span>. 
- <span style=color:yellow>Size_t</span> = <b><u>Per sizes, cardinalità o numeri ordinali</u></b>. I tipi unsigned sono molto più comodi e efficenti rispetto ai tipi unsigned. il compilatore può predisporre ottimizzazioni in quanto <b><u>le operazioni su questo tipo non causano overflow, operazione di modulo ben definita</u></b>. 
- <span style=color:yellow>unsigned</span> = <b><u>Utilizzare per piccole quantità che non possono essere negative</u></b>
- <span style=color:yellow>signed</span> = <b><u>piccole quantità con segno</u></b>
- <span style=color:yellow>double</span> = per floating-point calcolation
- <span style=color:yellow>double complex</span> = per calcoli complessi. 

tipi semantici : 
![[Pasted image 20241007185556.png]]

Abbiamo diversi modi per specificare dei litterali numerici : 
- Decimale = utilizzato per esprimere costanti negative, <b><u>hanno come tipo signed (il più piccolo che può contenere la costante</u></b>)
- Ottale.
- Esadecimale. 

<span style=color:red>N.B</span> = <b><u>Un errore comune è quello di provare ad assegnare una costante esadecimale o ottale a un tipo signed, con l'aspettativa che il valore di tale costante rappresenti un numero negativo </u></b>

<span style=color:red>N.B</span> = <b><u>i letterali numeri non sono mai negativi</u></b>. Se li dichiariamo come -34 o -1.53, il - è interpretato come operazione di complemento. I litterali devono avere un tipo. <b><u>Una costante con un valore positivo, può essere tipo signed. </u></b>

Le costanti di tipo integer, possono essere forzate ad essere unsignedf oppure un tipo con dimensione minima minore. Si appendono alla dichiarazione le seguenti keyword : 
- <span style=color:cyan>U</span> = <b><u>Unsigned</u></b>
- <span style=color:cyan>L</span> = <b><u>signed Long</u></b>
- <span style=color:cyan>LL</span> = <b><u>signed long long</u></b>

<h3 style=color:cyan>Numeri con virgola</h3>
I numeri con la virgola in realtà sono un approssimazione rappresentato dal litterale, questo in quanto i bit della parte frazionaria possono essere troncati o arrotondati. 
<b><u>Il valore effettivo di una costante float potrebbe essere diverso dal valore rappresentato dal litterale</u></b>, ad esempio *float a = 0.2. il suo valore reale è 0.200000000111*.

Possiamo accostare alcuen keyword a delle costanti di litterali con virgola : 
- <span style=color:cyan>f o F</span> = <b><u>Denota un float</u></b>
- <span style=color:cyan>l o L</span> = <b><u>Denota un long dobule</u></b>
- <b><u>Se non specificato un litterale con virgola è di tipo</u></b> <span style=color:cyan>double</span> 

<span style=color:green>Costanti complesse</span> (includere l'header *complex.h*): 
- CMPLX = Compara due valori floating-point
- CMPLXF = Variante float
- CMPLXL = Per long double 
- <span style=color:cyan>I</span>  = <b><u>rappresenta una costante di tipo</u></b> *float complex*, tale che $I*I = -1$ 
  $0.5+(0.5*I)$ = Risultato di tipo *double complex*
  $0.5f + 0.5f*I$ = Risultato di tipo *float complex*

<h3 style=color:cyan>Conversioni implicite</h3> 
<b><u>I tipi degli operandi influenza il risultato di un operazione aritmetica, ad esempio</u></b> :
- *-1* = è di tipo signed int
- *-1U* = <b><u>è di tipo unsigned int, ma non corrisponde a -1 ma al valore massimo nel dominio dei signed int</u></b> (modulo)

![[Pasted image 20241008121135.png]]

![[Pasted image 20241008122226.png]]

![[Pasted image 20241008122547.png]]

<span style=color:red>Regola generale</span> := <b><u>Se il tipo di uno dei due operandi è contenuto nel tipo dell'altro operando, il risultato dell'operazione avrà il tipo più grande tra i due</u></b>.
<b><u>In generale è meglio evitare operazioni tra operandi con segno differente e usare tipi unsigned ovunque si può</u></b>. 

