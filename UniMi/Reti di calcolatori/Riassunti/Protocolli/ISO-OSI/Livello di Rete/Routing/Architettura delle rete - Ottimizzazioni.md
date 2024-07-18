SE aree0 molto grandi, avremo grandi costi di traffico e computazione. 
Per ridurre la complessità computazionale, un nodo viene eletto come <span style=color:yellow>Designated router</span> = <b><u>Si tratta di un router che calcola le tabella di routing per tutti quanti i nodi </u></b>, in modo che il costo computazionale sia centralizzato. 

Tramite il Designeted router <b><u>vado a rimuovere il fluding</u></b> : 
- <b><u>Ogni nodo misura le adiacenze e le invia al designated router</u></b>. 

 - <b><u>Il calcolo dei caminimi minimi viene centralizzato</u></b>, il deigneted router esegue dijikstra per tutti i nodi e per tutti le destinazione. 
 
 - <b><u>Successivamente le tabelle di routing vengono restituite</u></b>. 

<span style=color:red>Problematiche: </span> 
- <b><u>Il dispositivo può rompersi</u></b>, dobbiamo avere una riserva pronta 
- il <b><u>designeted router è sottoposto ad un notevole sforzo computazionale</u></b>.
- <b><u>Convergenza del traffico verso il designeted router</u></b>

<b><u>Ad oggi il designeted router ( e altre funzionalità della rete) viene messo in cloud</u></b>.
<b><u>Tutti i messaggi di controllo della rete vengono mandati in cloud</u></b>. Abbiamo così inventato un  <span style=color:yellow>SDN Software Defined Network</span>, tutte le reti oggi funzionano con SDN. 
<b><u>Tutto questo è possibile perchè abbiamo separato</u></b> il routing dal forwording, ovvero <b><u>il piano di controllo dal piano dati</u></b>. 
