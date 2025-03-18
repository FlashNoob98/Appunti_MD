La memoria FLASH è una memoria non volatile dove verrà caricato il firmware del microcontrollore, contenente, in sequenza, le istruzioni da eseguire.

Sulla scheda di sviluppo è presente un controllore denominato `st-link` si occupa anche del debug, oltre a caricare il firmware (flashare appunto).

Mediante il debugger si può eseguire il programma step-by step dal compilatore ed analizzare una istruzione per volta.

Il clock del microcontrollore è dato da un oscillatore al quarzo da 8MHz, il microcontrollore sfrutta un circuito chiamato PLL, può moltiplicare fino a 9 volte il clock, raggiungendo velocità fino a 72MHz.

L'architettura del microcontrollore è di proprietà dell'azienda ARM, da cui prende il nome, la STMicroelectronics compra l'architettura da ARM e decide come e quali periferiche aggiungere nel microcontrollore come gli ADC, i contatori, i timer ecc...
L'architettura è a 32bit, ovvero lo spazio di indirizzamento è di 32 bit.

Un microcontrollore esegue un'istruzione alla volta, in 3 colpi di clock, esegue una prima fase di FETCH in cui prende l'istruzione dalla memoria e la porta all'interno del processore (nella cache?), al secondo colpo la DECODIFICA dell'istruzione, in questa fase il processore carica gli operandi da utilizzare, ho bisogno di un terzo colpo di clock chiamato EXECUTE per compiere l'operazione e mettere il risultato in memoria.

Durante l'esecuzione di una delle tre fasi di un'istruzione posso iniziare una fase dell'istruzione successiva e così via..
Trascorso il ritardo iniziale si ha un EXECUTE ogni colpo di clock.
SI parla dunque non sempre di 72MHz ma di 72Mps, ovvero milioni di istruzioni per secondo.

La memoria è organizzata in più parti, 1byte = 8 bit, una WORD è 32bit, ovvero 4 bytes.
Si dice che la memoria flash è dunque organizzata su WORD a 32 bit, è grande per questo microcontrollore 256kB, dunque può contenere 256/4=64k ovvero può contenere un codice di 64 mila istruzioni.

Chi dice al microcontrollore di prendere la prima istruzione in memoria? è un programma chiamato BOOTSTRAP

La memoria RAM è invece quella che contiene gli operandi prodotti dalle istruzioni, ad esempio le variabili, organizzata anch'essa su WORD da 32 bit (4bytes) grande 48kBytes, dunque può contenere 12 mila variabili da 4 bytes.

Bisogna tener conto di questi limiti hardware durante la scrittura e l'esecuzione di un nuovo firmware.
