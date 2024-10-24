Dati: 
- $A(X)=X^6+3X^5+5X^4+7X^3+9X^2+11X+13$
- $m=6$ grado del polinomio
- $i=3$ divido il polinomio in "3" blocchi. 

Calcolo $n$, come : 
$⌈︂\dfrac{m}{i}⌉︂ ≤ n ≤ ⌊︃\dfrac{2m}{2i − 1} ⌋ = ⌈︂\dfrac{6}{3}⌉︂ ≤ n ≤ ⌊︃\dfrac{12}{5} ⌋ = 2≤n≤2$ 
Scelgo $n=2$.

il polinomio è composto da 3 blocchi : $A(X)=A_0​(X)+X^2A_1​(X)+X^4A_2​(X)$
- Blocco $A_0(x)$ $0≤deg(x)<2$: 
  -  $A_0​(X)=11X+13$ 
  - $n$ termini di grado $n-1$

- Blocco $X^2A_1(x)$ $2≤deg(x)<4$: 
  -  $A_1​(X)=7X + 9$
  - $n$ termini di grado $n-1$
  
- Blocco $x^4A_2(x)$ $4≤deg(x)≤6$: 
  -  $A_2​(X)=x^2+3X+5$
  - $k$ termini, ovvero il resto.

Vado ad unire i vari "blocchi". Posso riscrivere il polinomio come: $A(X)=(11X+13)+X^2(9X+7X)+X^4(X2+3X+5)$.

