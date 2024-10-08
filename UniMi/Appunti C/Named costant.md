C'è una distinzione in C tra costanti e <b><u>const-qualified objects. Questi ultimi sono solamente read-only e non possiamo modificarli</u></b>.

Esempio di costante : 

```c 
char const*const bird[3] = {
	"we",
	"you",
	"they",
};
for (unsigned i = 0; i < 3; i++){
	printf("%s\n",bird[i])
}
```

L'array *bird* usa un tipo puntatore *char constconst* per riferirsi a un litterale stringa. 
<b><u>Questo permette di non salvare i letterali stirnga direttamente nell'array, ma l'array contiene nelle celle un riferimento a quest'ultime memorizzate in un altra parte della memoria</u></b>. 

<h3 style=color:cyan>ENUM</h3>
<b><u>Gli enum possono contenere solamente costanti di tipo signed_int.</u></b>
Servono per wrappare un certo valore in una costante, da utilizzare al posto del valore. 

```c 
enum Level {  
  LOW = 25,  
  MEDIUM = 50,  
  HIGH = 75  
};
enum Level myVar = MEDIUM;   
printf("%d", myVar);

num { p0 = 1, p1 = 2*p0 , p2 = 2*p1 , p3 = 2*p2 , };
```

*Esempio per avere le key dell'enum come stringa*
```c 
enum corvid { magpie , raven , jay , corvid_num , };
char const * const bird [ corvid_num ] = {
	[ raven ] = " raven ",
	[ magpie ] = " magpie ",
	[jay ] = "jay ",
};

for ( unsigned i = 0; i < corvid_num ; ++i)
	printf (" Corvid  %u is  the  %s\n", i, bird [i]);
```

<h3 style=color:cyan>Macros</h3>
<b><u>Permette di definire costanti per litterali numerici diversi dal tipo signed int</u></b>. 
Permette di definire costanti per : 
- Unsigned 
- site_t
- double

```c 
# define M_PI 3.1455858
```

Se vogliamo andare a definire delle macro per tipi non basici, come le stringhe dobbiamo utilizzare i <span style=color:yellow>compound litterals</span> : 
```c 
# define CORVID_NAME /* */ \  -> il commento indica che ci vuole uno spazio.
( char const * const [ corvid_num ]){ \
	[ chough ] = " chough ", \
	[ raven ] = " raven ", \
	[ magpie ] = " magpie ", \
	[jay ] = "jay ", \
}

for ( unsigned i = 0; i < corvid_num ; ++i)
	printf (" Corvid  %u is  the  %s\n", i, CORVID_NAME [i]);

```