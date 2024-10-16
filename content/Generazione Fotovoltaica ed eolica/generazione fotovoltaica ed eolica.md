Link al [team](https://teams.microsoft.com/l/channel/19%3AG3aszN35A4R9Um_91E96NsYbEkhPjUZNQETL6nPlZvw1%40thread.tacv2/?groupId=70286a7a-d5e2-4d75-aebe-3c5e17495f61&tenantId=2fcfe26a-bb62-46b0-b1e3-28f9da0c45fd)

# Definizione di fonte rinnovabile
Con questo termine ci si riferisce spesso al solare fotovoltaico ed eolico o altre forme di sorgenti.
Vengono denominate fonti rinnovabili le risorse naturali che **si rinnovano nel tempo**, ovvero hanno un tasso di rinnovamento maggiore o uguale al tasso di consumo.
Devono essere reintegrate in una scala temporale umana.

Una risorsa rinnovabile si dice anche **sostenibile** se il tasso di rigenerazione è maggiore o uguale a quello di utilizzo.

La direttiva 2009/28/CE specifica quali sono le fonti rinnovabili e quali possono essere considerate sostenibili. Questa direttiva è stata recepita in italia con il Decreto Legislativo 28 del 03/03/2011.

Le fonti di energia rinnovabile sono:
- Energia Solare
	- termico e termodinamico
	- **fotovoltaico**
- Energia **Eolica**
- Energia geotermica
- Energia da Biomassa
	- biocarburanti
	- oli vegetali
	- olio di alghe
	- cippato (legno in scaglie)
- Energia Marina
	- correnti marine
	- energia a gradiente salino (osmotica)
	- mareomotrice (o delle maree)
	- moto ondoso: si dispongono delle boe a largo delle coste che convertano l'energia meccanica in elettrica
	- talassotermica (OTEC)
- Idroelettrica: è la più comune ed utilizzata, soprattutto in Italia, una delle più antiche ad essere utilizzata.
- Acqua di falda: legata alle profondità nel sottosuolo
- Aerotermica
- Gas di discarica
- Gas residuati dai processi di depurazione

## Fonti programmabili e non programmabili
Le fonti rinnovabili vengono inoltre classificate come fonti *programmabili* e *non programmabili*, in buona parte le fonti rinnovabili sono non programmabili ma non tutte.

Gli impianti idroelettrici a serbatoio e bacino ad esempio, o i rifiuti solidi urbani o le biomasse o gli impianti assimilati che utilizzano combustibili fossili, di processo o residui; sono fonti programmabili, si può determinare la fornitura e la riserva di energia dell'impianto.

Fonti come gli impianti idroelettrici fluenti, eolici, geotermici, fotovoltaici o biogas sono considerati non programmabili, in quanto la produzione è legata a fenomeni aleatori.

### Problematiche degli impianti non programmabili
L'aleatorietà o l'intermittenza delle fonti energetiche non programmabili pone alcuni problemi per la gestione della rete, deve sempre esistere un bilancio tra la potenza immessa in rete e quella consumata affinché il sistema sia stabile, potrebbero altrimenti determinarsi degli incrementi o decrementi di tensione, o una condizione più gravosa un'alterazione della frequenza elettrica.

Devono essere disposti dei sistemi di **stoccaggio** di energia, sia per la problematica elettrica appena citata, sia per una questione economica, (un'energia prodotta ma non consumata comporterebbe una perdita per il proprietario dell'impianto di produzione|senza fonte).

Il sistema di accumulo viene posto in parallelo al carico elettrico, in passato era previsto per i sistemi **in isola** ovvero sistemi che potevano essere isolati dalla rete di distribuzione.
Oggi invece anche per i sistemi **grid-connected** può convenire disporre di un sistema di accumulo locale, utile nei momenti *necessari* ovvero quando non c'è generazione, oppure per fornire il peak-shaping e ridurre i picchi di energia assorbiti dalla rete per ridurre i costi dell'energia.

Tecnicamente un sistema di accumulo per un sistema grid-connected potrebbe non servire, se non per sistemi critici che richiedano una continuità di servizio ininterrotta, il sistema di accumulo ha comunque un costo iniziale.
Su un carico domestico ad esempio un sistema di accumulo non ha molto senso, le interruzioni sono poco frequenti e non comportano solitamente alcun danno.

Se si ha un sistema di produzione fotovoltaico invece ha senso usare un sistema di accumulo affinché si riesca ad immettere in rete tutta l'energia prodotta, la potenza di produzione dell'impianto non sempre coincide con quella richiesta dalla rete, in aggiunta il costo dell'energia durante la fase di produzione può non coincidere con il costo dell'energia durante l'utilizzo.

# Definizione di sistema di accumulo
Si intende solitamente l'insieme di più sistemi composti dal **dispositivo di accumulo** ovvero il dispositivo che fisicamente accumula l'energia e da tutti i sistemi che servono a gestire l'energia durante le fasi di **carica** e **scarica**;
si può riassumere un sistema di accumulo in tre processi
- Carica, quando il sistema di accumulo si comporta come un carico per la rete e accumula energia
- Mantenimento dell'energia
- Scarica quando il sistema di accumulo fornisce energia alla rete e si comporta come un generatore

Il **dispositivo di accumulo** è invece il dispositivo che accumula l'energia, ad esempio la cella elettrolitica del pacco batterie.
Il **sistema di accumulo** è invece l'insieme del dispositivo di accumulo e dei dispositivi ausiliari che gestiscono questi tre processi. Per le batterie ad esempio si cita spesso il *BMS* (Battery-Management-System) composto sia dal circuito elettrico che gestisce il flusso di energia, sia dal software di controllo.

# Sistemi di conversione da fonte eolica
Vengono denominati anche **WECS**, Wind Energy Conversion System, esiste una prima classificazione a seconda della tipologia di generatore utilizzato, al variare di questo si ha un impatto sulla tipologia del sistema di conversione.

Seguendo la catena del flusso di potenza, a partire dalla potenza meccanica fornita dal vento alla turbina, fino alla rete si hanno i seguenti elementi:
- Turbina: organo meccanico composto da pale, anche di grandi dimensioni, possono essere a pala orizzontale o verticale per ridurre l'impatto visivo, le prime sono principalmente utilizzate per l'elevata produzione di energia.
- Riduttore di velocità
- Generatore elettrico, dove viene effettuata la conversione da energia meccanica ad elettrica, esistono quattro tipologie di generatori:
	- SCIG - Squirrel-cage induction generator
	- WRIG/DFIG - Wound rotor induction generator/ Doubly fed induction generator
	- PMSG - Permanent magnet generator
	- WRSG - Wound rotor generator
- Generator-side Harmonic Filter
- Power converter
- Grid-side Harmonic Filter
- Step-up transformer
- Three Phase grid
Questo schema può essere anche lo stesso di un impianto mini o micro eolico, di potenze installate non superiori al kW, non sono solitamente a pala orizzontale.

## Configurazioni del sistema di conversione
A seconda della tipologia di generatore si usa un nome diverso per il sistema eolico, analogamente anche il convertitore elettronico dovrà essere differente.
Al variare della velocità del vento la turbina fornisce una potenza differente al sistema, si deve intersecare la curva a campana Coppia-Velocità della turbina con la coppia resistente fornita dalla macchina elettrica, per ogni curva si può cercare di raggiungere il punto di massimo della curva, variando la curva resistente della macchina elettrica.

Per questo motivo il [[Azionamenti Elettrici|controllo]] della macchina elettrica è fondamentale, per effettuare tale controllo va utilizzato un sistema diverso in funzione della tecnologia della macchina, per questo motivo posso avere un sistema a **velocità fissa** o a **velocità variabile** o **semi-variabile**.
Converrebbe in teoria lavorare sempre a velocità variabile per inseguire i punti di massimo della sorgente, aleatoria.

### Sistema a velocità fissa
Si ha una connessione diretta di una macchina asincrona a gabbia di scoiattolo con la rete, interconnessa solo con un "soft starter". Tale macchina deve assorbire dalla rete la corrente magnetizzante negli avvolgimenti dello statore, assorbe dunque potenza reattiva dalla rete, eroga a tensione e frequenza fissa a patto che la velocità del rotore sia superiore alla velocità di sincronismo $\omega/p$ dove $p$ è il numero di coppie polari o analogamente a **scorrimento** negativo.

Il tratto stabile della caratteristica è compresa tra i punti di massimo e minimo, oltre si supera il ginocchio e si incontrano i problemi di avviamento.

È detta a velocità fissa perché la caratteristica è vincolata alla rete, non c'è manovra di velocità, se non nel range di scorrimento stabile, circa l'1%.
Dunque sulla caratteristica coppia-velocità della turbina non è detto che riesca ad avere il punto di lavoro sul punto di massimo, potrebbe addirittura non esserci intersezione tra le due curve.

Anche se il rendimento del sistema è elevato, non ho un rendimento complessivo del sistema elevato, a causa dell'incapacità di generare alla massima potenza rispetto a quella fornita dal vento a quella velocità.

Riassumendo i principali problemi di questo sistema sono:
- Bassa efficienza di conversione
- Un cambiamento della velocità del vento si riflette interamente sulla rete
- Guasti della rete possono causare forti stress meccanici al sistema
I vantaggi invece:
- Si ha un sistema altamente affidabile ed economico
- Si possono installare in mare aperto per la bassa richiesta di manutenzione
- Possono essere utilizzati in caso di venti costanti e permanenti
Hanno preso piede a largo delle coste della Danimarca a causa dei venti costanti presenti in quella zona.

Il soft starter serve all'avviamento della macchina elettrica e portarla alla velocità di sincronismo, viene poi bypassato con uno switch.
Il power factor compensator, come dice il nome, compensa la potenza reattiva assorbita dalla rete per magnetizzare lo statore.

La macchina asincrona può funzionare su una *rete prevalente* dove tensione e frequenza sono fissate, non funzionerebbe su una rete passiva, a meno di utilizzare un sistema di condensatori a valle, non ci sarebbe un assorbimento di potenza reattiva altrimenti. Non è una soluzione utilizzabile in soluzioni stand-alone.
Il limite di questa macchina è che ha una caratteristica molto ripida, mentre la caratteristica della turbina è a campana per diversi valori di velocità del vento, la velocità della macchina può variare poco e di conseguenza quella della turbina, non è detto che riesca a stare vicino al punto di massima potenza della turbina.
Potrei solo pensare di utilizzare un sistema di riduzione variabile ma perderei la caratteristica di affidabilità e minima manutenzione richiesta.

Il soft-starter è necessario all'avviamento, inizialmente la turbina è avviata dalla rete mediante il funzionamento da motore della macchina asincrona, quando la coppia fornita dalla turbina è sufficientemente elevata da aumentare la velocità oltre il sincronismo, il soft starer viene disinserito.


## Sistema a velocità semi-variabile
Si usa ancora una macchina asincrona ma il rotore non è a gabbia ma avvolto, utilizzando degli anelli disposti sul rotore, è possibile inserire delle resistenze variabili, è un sistema dissipativo. Si può variare la caratteristica del motore intorno la velocità di scorrimento, si ha una variazione maggiore della velocità, circa il 10% ma ha una caratteristica dissipativa.
Il pacco di condensatori di filtro può essere disposto in prossimità della macchina elettrica o alla base del pilone, vicino l'attacco alla rete.

## Sistema a velocità completamente variabile
Può essere composto da 3 principali soluzioni, macchina sincrona a gabbia, a magneti permanenti e a rotore avvolto.
Sono sempre connesse alla rete mediante almeno due convertitori: un raddrizzatore e un inverter.
Avere due convertitori indipendenti permette di controllare indipendentemente la potenza che fornisce la turbina e quella da fornire alla rete.
L'inverter deve garantire un certo valore di fattore di potenza, inoltre devo garantire la stabilità della tensione dello stadio in continua, se questo resta costante allora tutta la potenza prodotta dalla turbina viene convertita in potenza elettrica.

Variando la frequenza della macchina elettrica si può variare la velocità della macchina e di conseguenza sfruttare tutto il range di velocità della turbina.


## Sistema a doppia alimentazione
Unisce le soluzioni del sistema a resistenze rotoriche e di quello con il convertitore. Gli avvolgimenti di statore sono alimentati dalla rete, l'avvolgimento di rotore è invece connesso ad un convertitore a tensione e frequenza variabile, ma legata allo scorrimento.

Il limite della variazione di velocità e di circa il 30% della velocità di sincronismo, il rotore assorbe una potenza pari al 30% della potenza apparente, in questo modo si riduce il costo di installazione del convertitore che sarà più piccolo.

# Modello matematico
Vedi il modello matematico dell'asincrono sulle slide 1
Convenzione da motore scritto usando come variabili di stato il flusso di rotore e statore.

Nel caso di un generatore completamente variabile, il controllo è indipendente sui singoli convertitori, entrambi attraversati dall'intera potenza attiva, ho un range di variabilità della velocità completo.
Su entrambi i convertitori si esegue una [[space vector modulation]].
Il primo convertitore è un 2L-VSR, solitamente si usano gli IGBT, sono componente completamente controllabili, a valle è posto un inverter con la stessa struttura e gli stessi componenti.

Il controllo regola la tensione da fornire alla macchina, in funzione della coppia fornita dalla turbina, cercando di mantenere la velocità ottima.

Devo garantire la tensione costante sul condensatore del DC-Link, altrimenti una eventuale variazione sarebbe a scapito della potenza fornita dalla macchina.

È fondamentale garantire un power quality in uscita dall'inverter, in particolare bisogna ridurre al minimo le armoniche di corrente, va limitato il THD di corrente per non distorcere la tensione a causa dell'impedenza di rete.

Il DC-Link deve essere posto ad una tensione pari a $\frac{3}{2}$ il valore massimo di rete, se si usa una PWM, per evitare il rischio di sovra modulazione, la tensione di prima armonica deve essere proporzionale, linearmente, con la tensione in continua, mediante un coefficiente $M$ di modulazione.
Se si raggiunge un indice di modulazione maggiore di 1, il legame non è più lineare, si va  verso "soluzioni a onda quadra", aumenta l'ampiezza della prima armonica ma aumentano le armoniche più alte, riducendo la power quality.


