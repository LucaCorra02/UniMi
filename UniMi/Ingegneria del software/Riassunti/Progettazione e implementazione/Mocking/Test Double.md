`Test Double` è un termine generico utilizzato per indicare un qualunque oggetto con cui si sostituisce un DOC reale a scopo di test.

Ovviamente, a seconda del tipo di test che si sta eseguendo, si può codificare diversamente il comportamento del Test Double. 
Non è necessario che questo si comporti come il DOC reale: il suo scopo è solo quello di fornire le stesse API in modo che la sua presenza risulti essere trasparente al SUT. 

In altre parole, `per il SUT interagire con il DOC reale o con il Test Double deve essere esattamente la stessa cosa`. L’utilizzo di Test Double rende possibile la scrittura di test che precedentemente risultavano troppo articolati, complicati o dispersivi da realizzare.