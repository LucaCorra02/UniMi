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
- Deciamale = utilizzato per esprimere costanti negative
- Ottale.
- Esadecimale. 


<span style=color:red>N.B</span> = <b><u>i letterali numeri non sono mai negativi</u></b>. Se li dichiariamo come -34 o -1.53, il - è interpretato come operazione di complemento. I litterali devono avere un tipo. <b><u>Una costante con un valore positivo, può essere tipo signed. </u></b>

