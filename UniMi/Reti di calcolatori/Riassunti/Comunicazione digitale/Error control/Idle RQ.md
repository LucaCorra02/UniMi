Questo schema viene anche chiamato `send-and-wait` o `stop-and-wait`
<b><u>Opera in modalità half-duplex</u></b>

Il mittente invia <span style=color:yellow>solo 1 I-frame alla volta</span>, <b><u>facendo partire un timer ogni volta che ne invia uno</u></b>: 

- Il ricevente informa il mittente della corretta ricezione del frame con un `acknowledgment` o `ACK-frame`, in modo che il mittente resetti il timer e invii il successivo.

- <b><u>SE l'I-frame contiene degli errori</u></b>, viene `inviato un negative acknowledgment o NAK-frame` , in modo che il mittente proceda ad inviarne un altra copia, restartando il timer.

- <b><u>SE invece P non riceve l'ACK entro lo scadere del timer</u></b>, `P ritrasmette l'I-frame di cui stava aspettando l'ACK`. <b><u>Il destinatario riconosce che il frame ricevuto è un duplicato e provvede a scartarlo</u></b> e a mandare l'ACK del frame.

<b><u>Per fare in modo che il destinatario determini che il frame ricevuto sia o meno un duplicato, ogni frame contiene un identificativo numerico di sequenza</u></b> come anche ogni ACK associato all'i-esimo frame
`NACK` non piace perché è un messaggio di controllo in piu e perché non serve a molto, inducendo un `ACK` con semantica selettiva .