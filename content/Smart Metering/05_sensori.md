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
