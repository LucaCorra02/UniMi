Si tratta dell'algoritmo per l'accesso al canale condiviso adottato inizialmente da ethetnet (<b><u>Predecessore di CSMA-CD</u></b>)

<span style=color:cyan>Principio</span> = <b><u>Si tratta di un algoritmo che contempla le collisioni</u></b>. 
Per <span style=color:yellow>rilevare la collisione</span> <b><u>le stazioni fanno complemento bit a bit di ciò che inviano e ciò che ricevono</u></b>, sospendendo la trasmissione.  

Quando due <b><u>stazioni collidono, viene introdotto un ritardo casuale</u></b> $T$, in modo tale che la <b><u>probabilità di collisione del traffico di stazioni che vogliono trasmettere contemporaneamente diminuisca</u></b>. Tale probabilità non viene elliminata ed aumenta in base al numero di stazioni che voglio trasmettere. 

<span style=color:red>Svantaggi </span>:= <b><u>La curva di</u></b> `ALOHA` <b><u>di efficienza sul carico ha una forma di campana in quanto all'aumentare delle stazioni ho un utilizzo maggiore ma fino a un certo punto in cui ci sono troppe stazioni che causano collisioni</u></b>. 

Il picco di utilizzo della canale è del 18%.
Le prestazioni sono dovute a : 
- <b><u>il  pacchetto può collidere in un qualsiasi punto, per tutti il lasso di tempo della trasmissione</u></b>
- <b><u>Anche se la collisione avviene all'inizio della trasmissione, la trasmissione non viene interrotta immediatamente</u></b>.

![[Pasted image 20231210103041.png]]