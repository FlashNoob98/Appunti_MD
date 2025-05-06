Si collegano due periferiche mediante due pin ciascuna, un pin Tx ed uno Rx connessi rispettivamente.

Per avviare la comunicazione la linea Tx del dispositivo trasmettitore viene attestata per un certo tempo e si invia la sequenza di 8 bit. Il pin Rx monitora il potenziale della linea e legge il dato, la velocità di trasmissione è accordata in anticipo.

I dati vengono letti e vengono inseriti in registri, che verranno letti insieme.
La comunicazione full-duplex, la comunicazione è bidirezionale e può avvenire contemporaneamente.

Se il registro TXE è 1 posso aggiornare il dato nel registro TDR altrimenti indica che la comunicazione del dato ancora non è completa.
Viceversa dobbiamo leggere il RDR read data register quando il registro RXE è 1, ovvero è not empty, se non lo prelevo in tempo il dato viene sovrascritto dal successivo.

Se un dato è composto da più byte devo costituire un protocollo per ricostruire il dato a partire dai byte inviati all'USART.

