 <b><u>Alcuni nodi potrebbero subire congestione. il traffico in ingresso è troppo elevato rispetto alla caratteristiche di forwarding e di elaborazione</u></b>. Può capitare che il tasso di pacchetti su un link è superiore rispetto alla capacità del router di elaborare pacchetti nella coda di ingresso. 

Ogni router deve tenere sotto-controllo lo <span style=color:yellow>stato di congestione</span> delle proprie code, oppure <b><u>l'utilizzo che il router ha in base al traffico di ingresso dei propri link</u></b> : 
Ogni router tiene in memoria una variabile <span style=color:yellow>di utilizzo U</span>, calcolata nel seguente modo : 
 - $m$ = <b><u>misura</u></b>, solitamente la l<b><u>lunghezza della coda di ingresso</u></b>. 
 
 - $alfa$ = <b><u>alfa è il parametro critico, da l'indicazione di quanto nella formula vale la storia passata</u></b>. 
    - Se alpha = 0,5, la nuova misurazione influisce su U quanto il vecchio valore di U.
    - Se alpha = 0,8, la storia vecchia vale più della misura attuale (magari momentanea congestione del link, non la peso più di tanto)
    
	  $U = \delta * U_{old} + (1-\delta) * m$ 

<b><u>Aggiorno periodicamente lo stato di utilizzo di ogni link</u></b>, ad esempio misurando il numero di frame nella coda. 
<b><u>Ogni link ha una soglia ottima di U e un area di pericolo, devo bilanciare U in modo da rimanere nella zona ottima</u></b>. 




