I costrutti If non si usano, vengono usati i pattern matching per definire funzioni
```ocaml
match expression with 
	| pattern when boolean expression -> expression 
	| pattern when boolean expression -> expression
 ```

Catchall si dovrebbe sempre mettere con un \_ , in modo da catturare i casi non previsti nei pattern

es
```ocaml
let invert = function
	| pattern when boolean expression -> expression 
 ```
Nasconde l ultimo argomento (in questo caso l'unico) rendendolo implicito 