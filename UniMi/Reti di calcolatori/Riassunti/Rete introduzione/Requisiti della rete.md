- [[Affidabilita]] <b><u>Affidabilità</u></b> = se un nodo A manda un contenuto a un nodo S o viceversa, quel trasferimento è privo di errori. 
- <b><u>Sicurezza</u></b>: ma non è un problema di chi progetta la rete, è di chi progetta l'applicazione
- <b><u>Prestazioni: misurabili</u></b> 
	- Nella **velocità di trasferimento** in funzione del bit rate dei canali
	- Verificare se la mia rete riesce ad erogare all'utente finale la velocita promessa
- <b><u>Indirizzamento</u></b>: la rete deve poter indirizzare il contenuto al destinatario connesso. <b><u>Ogni destinatario o mittente deve essere indirizzabile</u></b>. 
- <b><u>Instradamento</u></b>
- <b><u>Qualità di servizio QoS</u></b> = La rete deve essere il piu possibile <b><u>general purpose</u></b> per offrire diverse qualità di servizi in base all'applicazione utente. 
  La rete fornisce gli strumenti per essere configurata dalle varie applicazioni, quindi deve essere abbastanza flessibile da potersi adattare alle richieste degli applicativi.
	
	Le richieste/parametri di qualità di servizi sono il Jitter, il data rate, il massimo degli utenti...
	SE non c'è la possibilita di raggiungere le richieste, si attua una negoziazione.
	QoS sono definiti mediante classi di servizi a cui viene assegnata una relativa priorità
	
	<span style=color:red>Difficoltà</span>: <b><u>le applicazioni che utilizzano la rete sono moltissime e molto variegate</u></b>
	E' necessario che il router applichi una politica per la gestione delle code specifica in base all'uso applicativo, per far ciò nel pacchetto <b><u>i parametri di QoS sono presenti nell'header o sono presenti dei bit per identificare la classe di QoS a cui appartiene il pacchetto</u></b>