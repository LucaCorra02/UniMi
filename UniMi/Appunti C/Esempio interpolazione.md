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

$\tilde{A}(X,Y)*\tilde{B}(X,Y)=\sum_{j=0}^{2i-2} Y^i*R_j(X)$
$R_j(X)=\sum_{v+w=j,0<=v,w<=i-1} A_v(X)*B_w(X)$

Calcolo i vari $R_j(X)$ da 0 a 4.
- con $v+w=0$ : 
  - $R_0​(X)=A_0​(X)B_0​(X)=(5X+6)(6X+7)=30X^2+65X+42$

- con $v+w=1$: 
  - $R_1​(X)=A_0​(X)B_1(X)+A_1​(X)B_0​(X)$ = $41X^4+73X^3+30x^2$

- con $v+w=2$: 
  - $R_2​(X)=A_0​(X)B_2​(X)+A_1​(X)B_1​(X)+A_2​(X)B_0​(X)$ = $16x^7+39x^6+42X^5+20X^4$

- con $v+w=3$ : 
  - $R_3​(X)=A_1​(X)B_2​(X)+A_2​(X)B_1​(X)$ = $10X^8+30X^7+22X^6$

- con $v+w=4$:
  - $R_4​(X)=A_2​(X)B_2​(X)$ = $2X^{10}+7X^9+6X^8$

Prendo i punti per l'interpolazione su un estensione $G$ (nel mio caso C) estensione di $F$ (R). Suppongo di prendere i seguenti punti per l'interpolazione := $x_0​=1,x_1​=2,x_2​=3,x_3​=4,x_4​=5$

ottengo il sistema : 
$P_0​(X)​=R0​(X)+R1​(X)+R2​(X)+R3​(X)+R4​(X)$
$P_1(X)=R_0​(X)+2R_1​(X)+4R_2​(X)+8R_3​(X)+16R_4​(X)$
$P_2(X)=R_0​(X)+3R_1​(X)+9R_2​(X)+27R_3​(X)+81R_4​(X)$
$P_3(X)=R_0​(X)+4R_1​(X)+16R_2​(X)+64R_3​(X)+256R_4​(X)$
$P_4(X)=R_0​(X)+5R_1​(X)+25R_2​(X)+125R_3​(X)+625R_4​(X)$
​



