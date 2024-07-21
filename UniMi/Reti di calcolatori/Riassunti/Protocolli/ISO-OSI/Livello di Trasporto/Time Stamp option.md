<b><u>Il trasmettitore indica in fase di apertura della connessione, di liberarsi dal vincolo di calcolare il RTO ad ogni invio di segmento</u></b>.
RTO verrà calcolato a scelta del trasmettitore, con aiuto di alcuni parametri forniti dal ricevitore. 

La sorgente ha un orologio. Quando manda il segmento S1 (con sequenza X), avrà a bordo il campo <span style=color:yellow>time-stamp</span> = <b><u>tempo preso dall'orologio, ovvero T1 (istante di tempo in cui viene mandato il segmento s1)</u></b>
  il segmento S1 viene timbrato con il time-stamp preso dal riferimento.

- il ricevitore risponde con un ACK in cui valida X + 1 e riporterà <span style=color:cyan>il time stamp di riferimento</span> = <b><u>Questo è l'ack per il segmento con time-stamp T1</u></b>. 

- il segmento viene ricevuto dal trasmittente al istante T2, $RTT = T2 - T1$. <b><u>Il trasmettitore calcola RTT in base al tempo riportato nell'ACK e all'istante di tempo in cui ha ricevuto l'ACK</u></b>