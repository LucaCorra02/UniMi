RIP è un protocollo di routing che utilizza la tecnica dei DV. <b><u>Avendo il problema del counting infinity rende il protocollo obsoleto</u></b>. 

Per accelelare i tempi in fase di conoscenza (soprattutto in fase di boot), RIP utilizza <span style=color:yellow>triggered update</span> = <b><u>Aggiornamento con spedizione di Distance Vector relativo, triggerato da un evento che prevede un cambiamento nella conoscenza</u></b>. Il distance vector viene spedito immediatamente al verificarsi di un evento senza aspettare lo scadere del timer.

<b><u>In fase di boot i router scambiano subito gli istance vector</u></b>. 

`Come metrica RIP utilizza SOLO hop count`
<span style=color:green>Soluzione Tabella</span> :
<b><u>Per ogni entry in tabella andiamo a inserire un timer</u></b>, 30 secondi di default. 
Ogni 30 secondi le tabelle di RIP vengono resettate e bisogna riempirle, questo per cercare di <b><u>risolvere eventuali situazioni di bouncing effect</u></b>. 

<span style=color:green>Soluzione implementativa</span> :
Quando il costo raggiunge 16, considero il costo infinito. 

<span style=color:green>Soluzione storm di update</span> :
Soluzione implementativa riguardo all'esistenza del triggering update. <b><u>Su reti molto grosse con il triggering update, non appena si rileva un errore, è probabile che molti nodi mandino il proprio update, generando una congestione di segnali di controllo</u></b>.
Dobbiamo dunque evitare momenti in cui la rete si sovraccarica di segnali di controllo. 

<b><u>La soluzione consiste nel generare un random fra uno e 5 secondi per spalmare la produzione di update in un intervallo di tempo più lungo</u></b> -> $r = [1/5]s$. 

<span style=color:red>Side effect</span> := <b><u>Aumento la possibilità di bouncing effect</u></b>, in quanto ritardo la comunicazione dei guasti. 