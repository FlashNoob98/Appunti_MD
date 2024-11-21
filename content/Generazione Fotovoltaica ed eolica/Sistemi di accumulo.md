Le fonti rinnovabili possono essere programmabili o non programmabili. In particolare quella fotovoltaica ed eolica sono aleatorie, per questo motivo è nata la necessità di creare dei sistemi di accumulo, con lo scopo di far sovrapporre temporalmente e spazialmente la curva di domanda di generazione con quella del carico.

Quando non esiste una differenza temporale e spaziale c'è una differenza tra la curva di domanda del carico con quella di generazione.

Quando c'è produzione non è detto che la potenza  prodotta sia assorbita dal  carico o dalla rete, questo è particolarmente evidente perché legato alla disponibilità della sorgente.
La principale modalità per rendere disponibile l'energia prodotta in orari differenti da quando ne è richiesto il consumo è proprio il sistema di accumulo, ciò è valido sia per sistemi grid-connected che sistemi isolati.

# Definizione
Un sistema di accumulo è definito dall'insieme dei dispositivi in cui l'energia viene accumulata o rilasciata, in forma diversa e tutti i sistemi atti a gestire i flussi di potenza da e verso il dispositivo di accumulo.

Il sistema di accumulo di energia elettrica può essere visto come un carico attivo, in grado di assorbire energia e in altri intervalli di tempo di restituire l'energia accumulata, comportandosi come generatore, con una potenza limitata nel tempo.

Tutti i sistemi ausiliari, di gestione dei flussi di potenza, di protezione e sicurezza, di manovra, i sistemi di controllo, costituiscono nel loro insieme il sistema di accumulo, non è solo il dispositivo di accumulo vero e proprio. Principalmente i dispositivi di accumulo elettrico sono le batterie e i supercondensatori. Un altro sistema di accumulo interessante è quello ad idrogeno.

La batteria è costituita da una cella in grado di immagazzinare energia, un sistema di accumulo è caratterizzato da tre processi:
- Carica: processo di immagazzinamento dell'energia
- Immagazzinamento: processo in cui viene conservata l'energia
- Scarica: processo in cui si fornisce energia al carico
A ciascuno di questi tre processi corrispondono delle conversioni, in alcuni casi intrinseci al dispositivo di accumulo, in altri casi sono necessari dispositivi esterni al fine di gestire questi processi.

La cella di elettrolita ad esempio non può gestire il processo di carica o scarica, il processo di scarica è l'unico stabile, non quello di carica, devo gestire esternamente come fornire l'energia alla batteria, disponendo eventualmente di sistemi ausiliari di conversione per controllare questo processo.

I tre processi sono caratterizzati da perdite, vi sarà in ingresso una certa energia per caricare ill sistema di accumulo, delle perdite disperse sotto varie forme: effetto Joule, perdite interne alla batteria.. ovvero perdite connesse alla gestione del processo di carica.
Il rapporto tra l'energia in uscita e quella in ingresso è definita come rendimento di carica.

L'energia viene immagazzinata dal dispositivo di accumulo ma durante l'immagazzinamento esistono delle perdite, quando la batteria è scollegata dai convertitori o dal carico. Durante questa fase vi sono dei fenomeni interni al sistema che causano le perdite:
- Scariche interne, ovvero fenomeni di **auto scarica** intrinseci al dispositivo, possono essere nell'ordine di giorni o settimane. Per sistemi come i super condensatori invece il fenomeno di auto scarica è molto più veloce nell'ordine dei minuti.
- Perdite di standby, per mantenere costante il livello di carica, è necessario addurre energia addizionale, sono necessari dei dispositivi che forniscano energia costantemente.

Rendimento di scarica, è equivalente al processo di carica e il suo rendimento è analogo a quello di carica.

## Classificazione dei sistemi di accumulo
Il ruolo principale dipende dalla tipologia del dispositivo, vengono classificati in base alla forma di energia con cui si può immagazzinare l'energia, come elettrico o elettrochimico (supercap e batterie o celle a combustibile), forme di energia meccanica (cinetica o potenziale), termica (termofotovoltaico).


Oggi le batterie sono nell'ordine di 200-300Wh/kg mentre i supercondensatori hanno un'energia accumulabile di 10-20 Wh/kg mentre in termini di potenza i supercap hanno una densità di potenza superiore alle batterie, anche 10kW/kg.
In scarica sono paragonabili, in carica hanno una differenza notevole, le batterie hanno dei tempi della reazione chimica che vanno rispettati, negli ordini delle ore, mentre i supercondensatori che sono dispositivi elettrostatici hanno tempi molto più piccoli, nell'ordine dei minuti.
I fenomeni elettrostatici sono molto più veloci di quelli elettrochimici.

Esistono dei diagrammi detti di *Ragone* che permettono di classificare i dispositivi di accumulo.

Parametri che classificnao i sistemi di accumulo:
- Densità di energia
- Densità di potenza
- Ciclo di vita: determina valutazioni economiche in termini di manutenzione e sostituzione dei sistemi di accumulo

# Batterie
Una batteria è un dispositivo costituito da due elettrodi detti anodo e catodo, disposti all'interno di un elettrolita, solitamente una soluzione liquida (acquosa?) composta da acido con un'elevata concentrazione di ioni disciolti in soluzione.
I due elettrodi immersi in questa soluzione elettrolitica, sui due elettrodi vengono disposti i materiali attivi sui quali avviene il processo chimico tra la soluzione e gli elettrodi, solitamente composti da due metalli diversi, nel caso della batteria agli ioni di litio si ha un ossido di metallo sul catodo (+) es litio-ferro-fosfato, si ha un ossido di ferro fosfato sul catodo, oppure litio-manganese-cobalto.

L'anodo invece è solitamente composto da grafite, dove avviene l'accumulo degli ioni elettrici.

Hanno cicli di vita tra i 1000 e i 3000 in cui si ha una completa carica e una completa scarica.
Si parla di cicli equivalenti quando si considerano ricariche parziali, ad esempio un ciclo equivalente è composto da due cicli di scarica e carica fino al 50%.
A seconda della stima dei cicli rimanenti si parla di stato di salute delle batterie.

Si dice che le batterie abbiano due vite, si dice che la prima termina quando la capacità della batteria espressa in Ah (amperora) che è l'integrale della corrente erogata nel tempo, è un dato di targa della batteria, si riduce nel tempo con l'aumentare del numero di cicli.

Quando si è ridotta del 20% si dice che la vita della batteria è terminata, insieme ad un altro parametro che è la resistenza interna, ovvero quando si crea uno strato chiamato SI (Solid Interface) che si realizza sull'anodo riducendone la conducibilità elettrica.

Quando la resistenza  interna raggiunge il 150% il valore nominale, è terminata la prima vita della batteria.
Questa può essere ritargata ed utilizzata in altre applicazioni con prestazioni diverse, esistono diversi progetti che riutilizzano le batterie dei veicoli elettrici per costituire il sistema di accumulo di impianti fotovoltaici, come ad esempio nello stadio dell'Ajax.

Un parametro fondamentale per la vita utile delle batterie è la temperatura di esercizio, temperature estremamente alte o estremamente basse ne riducono la vita utile, soprattutto durante i processi di carica e scarica.

Le celle delle batterie possono essere laminari, cilindriche o prismatiche, un pacco batterie cilindrico ha una densità di energia volumetrica superiore a quelle laminari.
Le celle prismatiche sono sempre avvolte come le cilindriche ma disposte su una geometria più estesa.

## Caratteristiche di una batteria
Assegnata una capacità della batteria in Ah, si parla di C-rate, se con la corrente nominale di 1A, ci metto 10 ore per estrarre tutta l'energia da una batteria di 10Ah, dunque un C-rate di 0.1C.

Se la batteria non la scarico ad 1A e quindi 0.1C ma ad 1C ovvero a 10A esiste un legame non proporzionale, ci impiegherò un tempo inferiore, ovvero estrarrò una quantità di carica minore rispetto a quella che estrarrei a corrente nominale.
Normalmente si definisce una corrente nominale di carica ed una di scarica.
$$
C_{B} = I^k t
$$
dove $k$ è la costante di Peukert.

Le batterie hanno un valore di tensione di cut-off massima e minima oltre i quali la batteria si danneggia.

Lo stato di carica della batteria è così definito:
$$
SOC(t) = \frac{\int_{t_{0}}^tI_{b}(\tau)d\tau}{Q_{0}}\times{100}\%
$$
detto anche Coulomb counting.
Per eseguire questo calcolo con precisione posso caricare la batteria al valore massimo e poi calcolare la corrente scaricata, oppure devo necessariamente conoscere lo stato di carica all'inizio del calcolo.
Il valore di $Q_{0}$ diminuisce con l'invecchiamento della batteria.

Il complementare dello stato di carica è il Depth of Discharge, ovvero la profondità di scarica:
$$
DOD_{(t)} = \frac{Q_{0} -\int_{t_{0}}^tI_{b}(\tau)d\tau }{Q_{0}} \times 100\%
$$
