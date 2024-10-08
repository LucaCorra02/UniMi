C'è una distinzione in C tra costanti e <b><u>const-qualified objects. Questi ultimi sono solamente read-only e non possiamo modificarli</u></b>.

Esempio di costante : 

L'array *bird* usa un tipo puntatore *char constconst* per riferirsi a un litterale stringa. 
<b><u>Questo permette di non salvare i letterali stirnga direttamente nell'array, ma l'array contiene nelle celle un riferimento a quest'ultime memorizzate in un altra parte della memoria</u></b>. 

