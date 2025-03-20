FPU sta per Floating Point Unit, permette i calcoli su dati di tipo FLOAT, ovvero con virgola mobile, mentre la CPU lavora su tipi interi.

Si può eseguire un'operazione con FLOAT per trasformare un numero intero in un valore comprensibile, acquisito ad esempio dall'ADC, oppure posso fare queste operazioni esternamente.

Alla CPU è collegato u BUS matrix, delle linee di comunicazione per trasferire dati alla CPU, le due freccette intendono che lo scambio di dati è bidirezionale.

Il bus matrix prende il nome di AHB, un tipo di BUS molto veloce in grado di effettuare trasferimenti in un solo colpo di clock.
I bus più veloci devono garantire un'elaborazione veloce, la FLASH ad esempio non può essere disposta lontana dalla CPU e deve essere collegata sul bus principale e vicino la CPU.

Il programma di BOOTSTRAP si trova su una ROM, viene scritto in fase di produzione del chip.

La RAM è suddivisa in CCM RAM, più piccola al quale il programma dispone le variabili accessibili più frequentemente e SRAM dove vengono conservate le altre variabili.

A partire dal BusMatrix si dirama un "albero di clock" che fornisce il clock a tutte le periferiche, esiste ad esempio una periferica chiamata RCC reset and clock control, ha il compito di "distribuire il clock" alle varie periferiche.

Le periferiche timer permettono di fare i conteggi, SPI è una perfierica di comunicazione, come la USART I2C, il BUS CAN o la USB.

Il DAC permette di generare forme d'onda.
I timer possono essere utilizzati per realizzare la base dei tempi di un'ADC per fare un campionamento coerente.

Sono presenti ad esempio 4 ADC che possono lavorare separatamente, in parallelo.

Per trasferire i dati dall'ADC alla memoria possiamo usare un DMA, ovvero un DirectMemoryAccess, permette di gestire uno stream di dati da ADC a memoria o da memoria a memoria.
Il timer gestisce il tempo di trasferimento mediante il DMA.

NVIC, Nexted Vector Interrupt Control, tutti i programmi possono essere interrotti da un Interrupt, ovvero una chiamata che proviene ad esempio da una periferica o essere interna, l'Interrupt richiama l'attenzione della CPU permettendole di accedere ad un programma differente da quello che stava eseguendo all'inizio.

Ad ogni cella di memoria è associato un indirizzo, che fa riferimento al byte meno significativo.

Anche le periferiche hanno dei registri di configurazione, presenti nella memoria.

I pin GPIO sono suddivisi in PORTE, ogni porta controlla 15 pin, numerati con la lettera della porta e il numero incrementale.
Il registro he contiene lo stato dei pin nella specifica porta prende il nome di ODR, Output Data Register 

La periferica RCC può stabilire se una periferica è accesa o spenta.
Ovvero può decidere di fornire o meno un clock alle periferiche.

