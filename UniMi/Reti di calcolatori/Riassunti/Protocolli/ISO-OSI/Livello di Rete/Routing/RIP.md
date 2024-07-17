RIP è un protocollo di routing che utilizza la tecnica dei DV. <b><u>Avendo il problema del counting infinity rende il protocollo obsoleto</u></b>. 

Per accelelare i tempi in fase di conoscenza (soprattutto in fase di boot), RIP utilizza <span style=color:yellow>triggered update</span> = <b><u>Aggiornamento con spedizione di Distance Vector relativo, triggerato da un evento che prevede un cambiamento nella conoscenza</u></b>. Il distance vector viene spedito immediatamente al verificarsi di un evento senza aspettare lo scadere del timer.

<b><u>In fase di boot i router scambiano subito gli istance vector</u></b>. 



`Come metrica RIP utilizza SOLO hop count`
L'infinito è considerato $n>16$: <b><u>non si utilizza quindi RIP per reti con diametro maggiore di 16</u></b>
Usa un random per il trigger, tutte le volte che rilevo un costo infinito non faccio un update instantaneo ma aspetto un tempo casuale per evitare storm.