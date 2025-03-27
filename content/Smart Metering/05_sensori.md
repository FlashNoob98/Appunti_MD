Un sistema di misura a microcontrollore è costituito da 4 blocchi principali:
- Il cuore di tutto il sistema di misure a microcontrollore che è proprio il micrcocontrollore.. in questo caso l'STM32MCU
- Il sensore, che interfaccia il microcontrollore con l'ambiente esterno, in questa categoria vengono inglobati due concetti in uno, il sensore vero e proprio e il trasduttore.
  Il sensore è quell'elemento sensibile ad una variazione di grandezza fisica, è la parte fisica più a contatto con la grandezza da misurare, come un sensore di temperatura, come il termometro a mercurio, sarà il mercurio il sensore vero e proprio che si dilata con l'aumento della temperatura.
  Se si considera invece un sensore di tipo resistivo, ovvero una resistenza variabile che varia al variare della temperatura, oppure una termocoppia ecc..
  
  Tutto ciò che si modifica con la grandezza da misurare è il sensore.
  Il trasduttore invece permette di trasformare la grandezza variabile del sensore in una grandezza elettrica.
  Sensore e trasduttore possono coincidere nel momento in cui il sensore offre direttamente una variazione di una grandezza elettrica proporzionale alla variazione fisica.
  
  Viceversa un sensore di posizione offre una variazione meccanica, sarà necessaria una fase di trasduzione per trasformare questa grandezza meccanica in elettrica.
  I sensori di tensioni e correnti ad esempio in maniera diretta o indiretta offrono direttamente dei segnali elettrici proporzionali alla grandezza da misurare.
  Nel caso del MCU però anche una misura di tensione o corrente domestica deve essere riportata ad una tensione massima di 3.3Vpp per essere gestita dal MCU, analogamente per i sensori di corrente, devono offrire dei segnali compatibili.
  
  I sensori hanno delle specifiche come l'accuracy che ne aumenta sicuramente il costo.
- Un altro elemento fondamentale è l'alimentazione del sistema di misura, può essere diretta dalla rete, per alimentare il microcontrollore a 5V ho bisogno comunque di un alimentatore, trasformatore, step-down ecc..
  Oppure posso avere un'alimentazione da batteria, che avrà bisogno a sua volta di un BMS che è a sua volta un microcontrollore.
- Trasmissione dei dati ad un'interfaccia accessibile all'utente, può essere cablata mediante protocolli TCP-IP o wireless oppure protocolli LoRaWAN a lunga distanza.
  Il segnale può essere bidirezionale e si può decidere di comandare il sensore da remoto e attivare o disattivare un carico ad esempio, o comunque effettuare un'attuazione.
  La capacità di fare sensing e attuazione rende il sistema *smart* da cui il nome del corso.
- Eventualmente si può aggiungere al sistema di misura un display.

La sensibilità è la minima variazione della grandezza fisica che determina una variazione apprezzabile dell'uscita del sensore.
Se uno strumento è sensibile deve fornire una grandezza in uscita rispetto ad una variazione dell'ingresso.

L'elemento fisico sensibile modifica il suo stato prelevando energia dall'ambiente.

Può essere necessario un circuito di condizionamento del segnale, per renderlo accessibile al microcontrollore e aumentare ad esempio la capacità di lettura della misura.

Un sensore può essere accurato e preciso, non accurato ma preciso ecc..
Una misura accurata e precisa implica che il sensore restituisce un valore molto prossimo a quello di riferimento.
Una misura precisa fornisce una deviazione standard molto stretta.
Una misura accurata fornisce misure molto prossime al valore reale, ma in media.. ovvero si potrebbe avere una media prossima al valore di riferimento ma deviazione elevata.

La condizione migliore è un sensore preciso e accurato.
Posso avere un sensore preciso ma non accurato, è la seconda condizione migliore.
Un sensore accurato ma non preciso fornisce comunque una media prossima al valore vero, si avrebbe però un'incertezza maggiore, sono necessarie parecchie medie per determinare il picco della campana, che sarà più larga.

Un sensore nè accurato e nè preciso.. si butta.

Il valore di Accuracy fornito dal costruttore del sensore è solitamente cautelativo, ogni sensore proveniente dallo stesso lotto può avere comunque un'accuracy più bassa.

La sensibilità è legata al guadagno del sensore, una variazione di ingresso quanta variazione di uscita determina?
Un sensore poco sensibile richiede un convertitore con più bit, ma al segnale del sensore si sommerà poi l'errore, di vario tipo, rendendo difficile la misura. Aumenta il costo del sistema di misura e la quantità di dati da misurare.

Se invece la sensibilità è elevata, il valore in uscita sarà più facile da misurare rispetto alle variazioni di ingresso, posso ridurre il numero di bit dell'ADC.
$$
S = \left.\frac{\partial U}{\partial I}\right|_{0}
$$
Si calcola, se la curva è lineare intorno allo zero.

Alcuni sensori possono avere caratteristiche di sensibilità non lineari, ovvero la sensibilità varia con il punto di misura.
Ciò implica cambiare il fattore di conversione della caratteristica in funzione del punto di lavoro, sarebbe necessaria modellare e memorizzare nel MCU la caratteristica richiedendo uno calcolo maggiore.

Solitamente se la sensibilità del sensore non è lineare si usano dei circuiti di condizionamento per linearizzare il sensore il più possibile.

La caratteristica uscita-ingresso del sensore è una generica curva chiamata *responsivity* del sensore, nel caso ideale è lineare.
Nel funzionamento reale del sensore ci sarà sempre un distacco tra la responsivity ideale e quella reale.

La taratura stima l'accuracy, permettendo di determinare la caratteristica dello strumento.
La calibrazione invece è la messa a punto del sensore, modificando la sua curva caratteristica a quella che meglio approssima la curva di taratura.

Per tarare e calibrare uno strumento è necessario un altro strumento più accurato.

Si può calcolare l'errore di linearità in percentuale come lo scostamento massimo del valore misurato dalla retta di fitting.

La stabilità è la capacità di mantenere le caratteristiche di misura nel tempo.

Rumorosità - SNR

Isteresi - Differenti curve per la direzione in cui si esegue la misura tra due differenti punti