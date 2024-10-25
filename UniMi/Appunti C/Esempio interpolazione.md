Dati : 
- Polinomio $A(x)$ = $X^5+2X^4+3X^3+4X^2+5X+6$
- Polinomio $B(x) =2X^5+3X^4+4X^3+5X^2+6X+7$
- $m=6$
- $i=3$
- $n=2$

Suddivido i due polinomi : 
- $A(X)=A_0​(X)+X^2A_1​(X)+X^4A_2​(X)$
  - $A_0(X)=5x+6$
  - $A_1(X)=3x+4$
  - $A_2(X)=x+2$
  $A(X) = (5x+6)+x^2(3x+4)+x^4(x+2)$

- $B(X)=B_0​(X)+B^2A_1​(X)+B^4A_2​(X)$
  - $B_0(X) = 6x+7$
  - $B_1(X) = 4x+5$
  - $B_2(X) = 2x+3$
  $B(X) = (6x+7)+x^2(4x+5)+x^4(2x+3)$

Passo all'anello $F[X,Y]$, costruisco i polinomi $\tilde{A}(X,Y)$ e $\tilde{B}(X,Y)$.
- $\tilde{A}(X,Y) = (5X+6)+Y(4x^2+3X^3)+Y^2(2X^4+X^5)$

- $\tilde{B}(X,Y) = (6X + 7) + Y(5X^2 + 4X^3) + Y^2(3X^4 + 2X^5)$

$A~(X,Y)⋅B~(X,Y)=\sum_{j=0}^{2i-2} Y^i*R_j(X)$


Dove:

Rj(X)=∑v+w=jAv(X)Bw(X)R_j(X) = \sum_{v+w=j} A_v(X) B_w(X)Rj​(X)=v+w=j∑​Av​(X)Bw​(X)


