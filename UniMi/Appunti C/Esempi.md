Dati: 
- $A(X)=X^6+3X^5+5X^4+7X^3+9X^2+11X+13$
- $m=6$ grado del polinomio
- $i=3$ divido il polinomio in "3" blocchi. 

Calcolo $n$, come : 
$⌈︂\dfrac{m}{i}⌉︂ ≤ n ≤ ⌊︃\dfrac{2m}{2i − 1} ⌋ = ⌈︂\dfrac{6}{3}⌉︂ ≤ n ≤ ⌊︃\dfrac{12}{5} ⌋ = 3≤n≤4$










Stiamo usando l'algoritmo di _i_-split con i=3i = 3i=3, il che significa che dobbiamo dividere il polinomio in 3 blocchi con potenze di X2X^2X2.

### Step 1: Determinare il valore di nnn

Poiché stiamo dividendo il polinomio in i=3i = 3i=3 blocchi, calcoliamo nnn:

n=⌈6+13⌉=2n = \left\lceil \frac{6 + 1}{3} \right\rceil = 2n=⌈36+1​⌉=2

Quindi, ogni blocco coprirà termini associati a potenze di X2X^2X2.

### Step 2: Suddivisione del polinomio

Il polinomio sarà scritto come somma di tre blocchi, moltiplicati da potenze di X2X^2X2:

A(X)=A0(X)+X2A1(X)+X4A2(X)A(X) = A_0(X) + X^2 A_1(X) + X^4 A_2(X)A(X)=A0​(X)+X2A1​(X)+X4A2​(X)

Ora, troviamo i termini che vanno in ogni blocco.

### Step 3: Calcolo di A0(X)A_0(X)A0​(X)

A0(X)A_0(X)A0​(X) contiene i termini di grado inferiore a X2X^2X2, cioè i termini di grado 0 e 1 del polinomio. Guardando il polinomio originale, questi sono:

A0(X)=11X+13A_0(X) = 11X + 13A0​(X)=11X+13

### Step 4: Calcolo di A1(X)A_1(X)A1​(X)

A1(X)A_1(X)A1​(X) contiene i termini di grado compreso tra 2 e 3, che verranno poi moltiplicati per X2X^2X2. I termini di grado 2 e 3 nel polinomio originale sono:

A1(X)=9X+7A_1(X) = 9X + 7A1​(X)=9X+7

Questi verranno moltiplicati per X2X^2X2 nella ricostruzione finale.

### Step 5: Calcolo di A2(X)A_2(X)A2​(X)

A2(X)A_2(X)A2​(X) contiene i termini di grado compreso tra 4 e 6, che verranno moltiplicati per X4X^4X4. I termini di grado 4, 5, e 6 nel polinomio originale sono:

A2(X)=X2+3X+5A_2(X) = X^2 + 3X + 5A2​(X)=X2+3X+5

Questi verranno moltiplicati per X4X^4X4 nella ricostruzione finale.

### Step 6: Ricostruzione del polinomio

Dopo la suddivisione, possiamo riscrivere il polinomio A(X)A(X)A(X) come:

A(X)=(11X+13)+X2(9X+7X)+X4(X2+3X+5)A(X) = (11X + 13) + X^2(9X + 7X) + X^4(X^2 + 3X + 5)A(X)=(11X+13)+X2(9X+7X)+X4(X2+3X+5)