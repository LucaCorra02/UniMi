Router non convenzionale (MPLS) differenze:
- le informazioni di routing popolano anche la Label switching table
- <b><u>l'IP header e l'IP payload vengono trasformati in un MPLS</u></b> pacchetto. Questo avviene tramite [[Tunneling]], <b><u>incapsulando quindi il pacchetto IP</u></b>
- <b><u>Labeling</u></b>: assegnamento della label al pacchetto
- <b><u>Gestisco le code in base all'etichetta</u></b>

<b><u>Il ruoter ragiona solo in base alla porta di ingresso - etichettaRilevata - etichettaNuova - porta di uscita</u></b>. Ci sarà una tabella per ogni porta

![[Pasted image 20231219131850.png|400]]
