Current war e vantaggi e svantaggi delle due tecnologie

Corrente DC:
- Full active power utilization
- Full utilization of conductors
- Difficult to interrupt
- Hard voltage transformation

Corrente AC:
- Reactive power
- Skin effect
- Easy to interrupt (passaggio per lo zero)
- Easy transformation

La variazione di tensione è importante per facilitare il trasferimento di energia (corrente più bassa).

Funzionamento del trasformatore: legge di Faraday
$$
\oint_{\gamma} \vec{E}\cdot \hat{t}\cdot dl = - \int \int_{S_{\gamma}}  \frac{\partial\vec{B}}{\partial t}\cdot \hat{n}\cdot dS
$$
Il comportamento rispetto alle correnti è spiegato dalla legge di Ampère

Voltage regulation mediante i "tap changer"

Mediante i dispositivi elettronici di potenza si possono realizzare conversioni mediante i cambi di topologia del circuito, esistono numerose tipologie di convertitori, step-down, step-up ecc.

Un convertitore SST prevede l'uso di due convertitori interconnessi da un trasformatore; questo permette di mantenere l'isolamento galvanico, ma usando frequenze maggiori si riesce a ridurre la dimensione del trasformatore.
I costi sono più elevati e l'efficienza tende a diminuire; aumenta la complessità del sistema.
Sono già ampiamente usati nei sistemi in BT; le attività di ricerca si rivolgono a sistemi a MT e AT ad elevata potenza.

Sistemi che ne potrebbero beneficiare sono quelli fotovoltaici, i sistemi di ricarica dei veicoli elettrici, trasporti ferroviari, tramviari e navali, sistemi per smart grids e smart cities, data centers.

I trasformatori SST possono prevedere uno o due stadi di conversione a monte e a valle del trasformatore.

Le principali tipologie di convertitori DC/DC per gli SST sono i dual active bridge e i convertitori risonanti.

Il dual active bridge è composto da due full bridge e il trasformatore ad alta frequenza interposto.
Nel caso più comune viene generata un'onda quadra al primario e una al secondario; il flusso di potenza dipende dallo sfasamento tra le due onde.

Esistono anche modulazioni triangolari o trapezoidali.
Il DAB prevede facilmente lo zero-voltage switching; si riducono le perdite dovute alla commutazione.
Questo sistema prevede però un controllo sincronizzato dei due sistemi; è principalmente problematico nei sistemi ad alte frequenze, una piccola latenza ad alta frequenza diventa incidente nella conversione.

SRC (series resonant converter): un full bridge al primario, uno stadio non controllabile al secondario e lo stadio in AC comprende un trasformatore e un condensatore; mediante l'interazione tra la capacità e l'induttanza del trasformatore si ottiene una risonanza.
Dando una tensione primaria come un'onda quadra, alla frequenza di risonanza del "tank" si ottiene una corrente sinusoidale che permette lo switching proprio al passaggio per lo zero; non si ha però controllo sul flusso di potenza, si preferisce farli lavorare in subrisonanza o superrisonanza.

In condizioni di risonanza perfetta il rapporto di tensione è unitario, a meno del rapporto spire.
Viceversa, in subrisonanza si lavora sempre in ZCS (zero current switch), in superrisonanza invece si lavora sempre in ZVS (zero voltage); la corrente circola nei diodi di ricircolo; in entrambi i casi però il rapporto di trasformazione è leggermente più basso; in entrambi i casi si riducono però le perdite di commutazione.

Rispetto al DAB il controllo di frequenza è limitato, così come il controllo del flusso di potenza. Non è però necessaria alcuna sincronizzazione; si controlla un solo stadio.

All'aumentare della frequenza però aumentano le perdite nel trasformatore per isteresi e correnti parassite.
Si possono stimare mediante l'equazione di Steinmetz e dipendono da una potenza della frequenza e una dell'induzione elettromagnetica.
Con una superficie più piccola è inoltre più difficile dissipare la potenza dovuta alle perdite; bisogna scegliere materiali diversi e diversi form-factor, ognuno con i propri vantaggi e svantaggi.

Materiali:
- Silicon Steel (basse frequenze e trasformatori convenzionali): pessima scelta per questa applicazione, dissipazioni troppo elevate.
- Materiali amorfi: si garantisce un buon funzionamento a flussi elevati, un ciclo di isteresi più piccolo ma un costo elevato.
- Ferriti: soluzioni più utilizzate soprattutto a basse tensioni, hanno basse isteresi e correnti parassite ma sono fragili e un basso flusso di saturazione. Nei dispositivi SPS (switching power supply) si usano ferriti; non si può aumentare troppo il valore di flusso.
- Nanocristallini: garantiscono delle perdite basse e alti flussi di saturazione ma sono molto costosi.

Anche gli avvolgimenti, se lavorano ad elevate frequenze, sono caratterizzati dall'effetto pelle e dagli effetti di prossimità; presi due conduttori affiancati, il campo di un conduttore può influenzare la distribuzione di corrente in quello adiacente.
Anche in questo caso le perdite negli avvolgimenti aumentano. Anche in questo caso esistono diverse tecnologie per gli avvolgimenti in SST: i Litz wire, foil windings, hollow bars, PCB windings.
Le cavità interne possono essere utilizzate per il raffreddamento.

Inoltre il volume dell'isolante non è influenzato dall'aumento di frequenza; ad elevate frequenze sono presenti inoltre effetti parassiti, scariche parziali, differenti rigidità dielettriche ecc.

Inoltre i dispositivi switching hanno un limite in tensione che dipende spesso anche dalla frequenza; si può solitamente scegliere di avere alte tensioni di bloccaggio o alte frequenze di commutazione.
Attualmente la ricerca è orientata verso i Silicon Carbide MOSFET; sono però molto costosi e fragili, non attualmente commercializzati.
Si usano invece i GaN con tensioni massime di 600 V; ce ne sono alcuni sperimentali a 900 V ma non sono ancora pronti per la commercializzazione; la media tensione parte da 9 kV, dunque questi dispositivi da soli comunque non bastano; solitamente si realizzano dispositivi in serie, ad esempio 4 dispositivi da 1000 V potrebbero reggere 4 kV ma ci sono problemi di bilanciamento statico e dinamico; si deve garantire lo stesso istante di switching e anche in condizioni statiche devono garantire la stessa tensione.

Se commutasse un solo dispositivo si avrebbe la tensione sui restanti tre; si avrebbe un effetto a catena che potrebbe portare alla rottura dei rimanenti dispositivi.

Si può optare per convertitori multilivello, che possono garantire in uscita valori intermedi della tensione di alimentazione. Esistono varie tipologie; le più diffuse sono i Neutral Point Clamped, Flying Capacitor converter con dei condensatori interni della struttura che possono essere collegati in serie o in antiserie alla sorgente principale. I Modular Multilevel Converter, utilizzando strutture più semplici, si riesce a garantire uno stress minore sui componenti in caso di commutazione non contemporanea.


Si riducono inoltre le armoniche di tensione usando convertitori multilivello; sono richiesti filtri più economici. C'è una maggiore complessità dal punto di vista del controllo; c'è un problema sul bilanciamento dei condensatori; vanno monitorate le tensioni sui condensatori.

Si possono però realizzare strutture SST modulari (ISOP), ad esempio collegate in serie al primario e in parallelo al secondario; è un'estensione del concetto di multilivello; saranno presenti più moduli sull'intera struttura SST; si possono gestire tensioni più elevate al primario e più alte correnti al secondario; può essere scalato.
Anche in questo caso il controllo è più complesso e l'isolamento deve essere garantito per l'intera tensione, su ogni trasformatore.

Anche lo stadio a monte deve essere posto in serie; si può garantire un profilo armonico a monte più basso per il sistema.
Si può inoltre collegare una serie di stadi primari ad un unico trasformatore multi-avvolgimento con un unico secondario; si riducono in questo caso dimensioni e pesi.
Si apre la strada alla ricerca di trasformatori a matrice "matrix transformers".

Si deve tenere in considerazione in questo caso gli accoppiamenti dei vari avvolgimenti del trasformatore.

È necessario inoltre controllare la tensione tra i vari moduli per evitare sbilanciamenti; è presente inoltre una problematica sulla conversione monofase; sarà presente un ripple di tensione sulla tensione continua; la potenza attiva non è equivalente a quella istantanea.
Sarà presente un termine fluttuante al doppio della frequenza, dunque un ripple alla seconda armonica; problema rilevante su sistemi ferroviari a 16 Hz ad esempio, richiedono filtri elevati.
Il ripple inoltre si può propagare al secondario dell'SST.

Per filtrare armoniche a 100 Hz si possono realizzare filtri capacitivi sovradimensionati oppure filtri passabanda "LC trap"; le dimensioni non sono trascurabili.

Si possono invece usare filtri attivi; esistono diverse tecnologie come buck-boost ecc.; si ha un'ulteriore complessità del sistema; inoltre l'APF (active power filter) influenza non solo il modulo su cui è installato ma anche sugli altri; è necessario gestire le instabilità che si potrebbero avere sul sistema; si ottiene un sistema MIMO, con il quale è necessario utilizzare un criterio di Nyquist generalizzato.


Mediante il controllo del convertitore DC-DC è possibile spostare l'armonica al primario sui sistemi monofase oppure al secondario sui sistemi trifase, sfruttando il bilanciamento automatico delle fasi.

## MDR-SST
Mediante l'utilizzo di due diodi è possibile realizzare la conversione alternata continua su una singola fase, usando DC-DC isolati per una conversione DC-DC isolata o AC-AC isolata senza stadi con inverter, alle spese di avere un'utilizzazione del 50% dei convertitori.
Si può facilmente estendere questo concetto ad una struttura trifase a stella; ogni 120 gradi si utilizzeranno due dei tre convertitori.
Ogni diodo deve garantire però il bloccaggio della tensione concatenata e non stellata; i secondari possono ancora una volta essere collegati in serie o in parallelo per output in DC o a stella per output in AC.

Si possono realizzare questi convertitori anche per le strutture a ponte, monofase o trifase.
È il nuovo tipo di famiglie di SST, che utilizza un solo stadio di conversione senza usare dispositivi di bloccaggio bidirezionali ma convertitori tradizionali.
Questi DC-DC sono però operati con tensioni pulsate.

Si può estendere questo funzionamento in media tensione utilizzando una serie di diversi diodi e collegando tutti i secondari in parallelo.
Si possono gestire tensioni più elevate ma è necessario garantire il bilanciamento della tensione nel convertitore DC-DC.
Si può cortocircuitare attivamente lo stato primario dei singoli DC-DC.
Si possono poi integrare magneticamente i trasformatori dei vari branch o delle singole fasi.

Si può inoltre avere un controllo parziale della potenza attiva e reattiva, anche in maniera bidirezionale.

L'SST può essere visto come l'anello di congiunzione tra il mondo in continua e in alternata.
