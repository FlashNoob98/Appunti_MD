
Esistono sistemi di misura dell'energia elettrica a microcontrollore in numerose applicazioni, come i veicoli tradizionali, o maggiormente nei veicoli elettrici, una grande diffusione di sistemi elettronici che controllano i sistemi elettrici, un sistema elettronico a microcontrollore è utilizzato per generare i segnali PWM del controllo motore.

L'elettronica che controlla la trazione del motore elettrico, o il monitoraggio dello stato di carica e di salute delle batterie elettriche, sistemi come i BMS, in grado di monitorare tensioni, correnti e temperature delle batterie.

La stessa rete elettrica ha una complessa struttura topologica attualmente, si è passati da un semplice schema radiale, con la centrale al centro,con unbilancio energetico tout-court ad un sistema con una differente topologia, essa è composta da generazione distribuita, non si trova più inun unico posto ma possono esservi più sistemi che generano contemporaneamente all'interno della rete. È inoltre intermittente, i sistemi rinnovabili dipendono dalle condizioni metereologiche, come nel caso del fotovoltaico o del vento nel caso dell'eolico.

In alternativa possono essere presenti momenti in cui la quantità di energia sia sovrabbondante, non si ha il semplice controllo che si può avere con le centrali a combustibile tradizionali.
I picchi di produzione vanno stoccati nei farm battery.

Parallelamente alla rete elettrica sta crescendo una rete parallela di scambio di informazioni tra i sistemi, in cui intervengono l'elettronica e le telecomunicazioni.
Questa rete ha lo scopo di misurare e controllare i dispositivi della rete elettrica e monitorare i flussi di potenza.

Con il microcontrollore si realizzano tutti i sistemi oggi utilizzati, probabilmente senza nemmeno sapere dove essi sono ubicati.
Misurano, eseguono degli algoritmi di misura.

Sono presenti ad esempio due microcontrollori, il fitbit e un energy meter, cambierà sicuramente la grandezza da misurare e le dimensioni del display, il microcontrollore è probabilmente lo stesso, esso consiste in un chip hardware general purpose, cambierà l'algoritmo di misura e dunque il firmware del microcontrollore, scrivendo l'algoritmo di misura si specializzerà il microcontrollore per quella particolare applicazione.

Durante il corso si utilizzerà una scheda
STM32F3Discovery

Il microcontorllore è presente al centro, sono presenti dei led di segnalazione, un tasto di reset ed un tasto utente programmabile.
Si realizzeranno dei sistemi di misura con questa scheda, vedremo la PWM, le misure di tensione, eventualmente dei regolatori PID, si useranno gli interrupt interni ed esterni.

Ad aprile si studieranno componenti hardware specializzate del microcotrollore come il DAC ecc

Nella parte finale del corso si vedranno i protocolli di comunicazione, USART o SPI

Si terranno delle lezioni di condizionamento dei segnali, teoriche fino al condizionamento circuitale dei sensori.
L'obiettivo èdi realizzare un progettino, come quello di realizzare un sistema di monitoraggio real time dei consumi elettrici, in grado di misurare i consumi in maniera affidabile, comunicarli mediante un display, realizzare un sistema di trasmissione dei dati e visualizzarli mediante una piattaforma.

Si potrebbe fare la replica di un articolo (liccardo)
