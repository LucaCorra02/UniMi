<b><u>Prima del classificatore, andiamo ad applicare sulla sorgente una funzione di </u></b><span style=color:yellow>Call Admision</span>, validazione delle regole dichiarate in ingresso da parte della sorgente del traffico.  

Misure importanti : 
- <span style=color:yellow>Tasso Medio</span> = <b><u>numero medio di pacchetti che possono essere accettati nell'unità di tempo</u></b>.
- <span style=color:yellow>Tasso di picco</span> =<b><u> Ammettiamo dei periodo di picco del traffico, non troppo rigidi</u></b>. 
- <span style=color:yellow>Burst size</span> =  <b><u>Ammetto dei periodi in cui il traffico non viene erogato dalla sorgente in modo uniforme, specificandone durata e picco</u></b>.

La regolazione del flusso di ingresso avviene tramite un <span style=color:yellow>Token Bucket</span>.

![[Pasted image 20240718214312.png]]