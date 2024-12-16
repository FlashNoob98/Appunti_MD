Rileggi il Conte sulla classificazione delle sovratensioni, esistono sovratensioni di varia natura, esiste una classificazione rispetto alla forma d'onda, possono infatti essere di tipo
- A frequenza di rete
- Oscillatorio
- Impulsivo
Le sovratensioni a frequenza di rete riguardano la tensione di alimentazione, possono essere causate da produzione di energia eccessiva rispetto al carico o viceversa, varia l'ampiezza della sinusoide fondamentale; per proteggere la rete da queste sovratensioni sarà necessario agire direttamente sulla produzione, mediante dei relee collegati ai dispositivi di interfaccia, con valori di minima e massima tensione.
Agendo inoltre sui controlli delle centrali si può controllare il valore della tensione.

Le sovratensioni oscillatorie, sono causate da elevati contenuti armonici, sono causate dall'intervento degli apparecchi di manovra, ad esempio le aperture di interruttori.
In questo caso si cerca di agire sugli interruttori per ridurre queste sovratensioni, ad esempio coordinando opportunamente l'apertura quando la corrente è prossima allo zero.

Le sovratensioni di carattere impulsivo hanno un andamento nel tempo dato da un fronte crescente ripido ed uno decrescente, sarà caratterizzata da un tempo di salita $t_{s}$ come il tempo necessario a partire da zero fino al valore di picco; un tempo di discesa $t_{f}??$ definito a partire dal valore di picco all'emivalore, ovvero fino ad una diminuzione al 50% della tensione di picco.

Le sovratensioni possono inoltre essere di origine esterna in caso di fulminazioni o di origine interna in caso di manovra.
Le prime sono tipicamente di forma impulsiva mentre quelle di origine interna sono tipicamente di tipo oscillatorio.
Le sovratensioni di manovra hanno solitamente un valore massimo pari al doppio del valore di picco di normale esercizio, non sono rilevanti dal punto di visto della protezione.

Le sovratensioni dovute a fulminazioni possono essere causate dall'accoppiamento elettromagnetico tra la fulminazione e la linea.
La fulminazione può avvenire direttamente sulla linea e causare una corrente di scarica anche se è un evento raro, tipicamente esistono ostacoli e oggetti più alti della linea in BT, è più probabile un accoppiamento elettromagnetico per fulminazione di oggetti vicini.

L'accoppiamento elettromagnetico sarà semplicemente:
$$
e = - \frac{d\varphi}{dt}
$$

È invece probabile avere una fulminazione sulla linea di trasmissione, inoltre la sovratensione da fulminazione raggiunge valori di picco di gran lunga superiore a quella da manovra o in generale alle sovratensioni di origine interna.
Si studia se è necessario prevedere un parafulmine, ovvero un sistema di schermatura.
Si dispongono le funi di guardia sulla linea in AT per proteggerla dalle fulminazioni diretta, in AT le sovratensioni di manovra sarebbero maggiori delle sovratensioni esterne.

Sugli edifici si parla invece di LPS, ovvero Lightning protection System.

Le protezioni di tipo repressivo invece agiscono durante la sovratensione, il dispositivo classico è lo scaricatore o SPD, Surge Protection Device.
L'utilizzatore ha la massa collegata a terra, nel caso monofase ad esempio si ha la linea di alimentazione e il terreno, la sovratensione può essere di tipo differenziale se agisce tra i conduttori attivi, tra fase e neutro oppure di modo normale se agisce tra un conduttore e la terra.

Lo scaricatore SPD, va appunto a *scaricare* a terra la corrente conseguente ad una sovratensione, in maniera da limitare la tensione ad apparecchi utilizzatori;
va studiato il posizionamento dello scaricatore.
Il modo più semplice per proteggere l'impianto dalle sovratensioni è quello di aumentare l'isolamento, in questo caso si proteggerebbe però l'apparecchio solo da *piccole* sovratensioni, non si riuscirebbe nella realtà a realizzare la protezione dell'utilizzatore con un aumento di isolante.

Si definisce un livello di tensione detto livello di immunità, sotto il quale è presente il livello di normale funzionamento finchè non si presenta un valore di tensione talmente elevato da limitare i danni, prende il nome di tensione di tenuta all'impulso, si accetta un funzionamento dell'apparecchio nel range compreso tra queste due tensioni.

Si può utilizzare il valore di tenuta all'impulso per caratterizzare gli apparecchi utilizzatori.

Si definiscono le categorie degli apparecchi in base alle tenute all'impulso:

| Cat | Tenuta |
| --- | ------ |
| IV  | 6kV    |
| III | 4kV    |
| II  | 2.5kV  |
| I   | 1.5kV  |
Gli apparecchi in categoria IV sono quelli ad esempio all'esterno dell'impianto, in prossimità del punto di consegna della linea.

## Sistemi di protezione
Esistono quelli di tipo preventivo e di tipo repressivo.
L'impianto va protetto da un sistema LPS (parafulmine)?
La corrente di fulmine, in caso di parafulmine dovrà essere scaricata mediante il conduttore di protezione, non si può installare a prescindere un impianto parafulmine, va eseguita un'analisi di rischio.
L'analisi di rischio viene caratterizzata su più livelli di rischio:

| Livello | Rischio                           |
| ------- | --------------------------------- |
| R1      | Perdita di vita umana             |
| R2      | Interruzione di pubblico servizio |
| R3      | Danneggiamento di beni culturali  |
| R4      | Perdita economica                 |
Si deve moltiplicare il rischio per la probabilità dell'evento di fulminazione.

Si suppone che in caso di fulminazione sia presente una corrente di fulminazione nel conduttore di protezione, in parallelo saranno collegate le masse degli apparecchi, si ha un innalzamento della tensione dovuta dalla corrente di fulminazione per la resistenza del conduttore, inserendo uno schermo si riduce l'accoppiamento galvanico e in generale la resistenza del conduttore di protezione.

Lo scaricatore può essere ad innesco, o a limitazione come il MOV, o varistore.

Ad innesco è uno spinterometro, situato sui pali, quando la tensione supera il valore della rigidità dielettrica dell'aria per quella distanza si ha la scarica.
Durante la conduzione della corrente di arco si ha una diminuzione della tensione.
Nel caso in cui l'innesco non sia in aria si parla di GDT.

Il varistore è realizzato da un materiale che fornisce una resistenza non lineare, che dimminuisce all'aumentare della tensione, quando la tensione sulla linea supera un certo valore, la resistenza diventa sufficientemente bassa da rendere il dispositivo quasi un corto circuito, questo dispositivo è realizzato solitamente da un impasto ceramico drogato con metalli (MOV) Metal Oxide Varistor.

Nel caso della GDT il valore di sovratensione è molto alto, è quello che deve innescare la scarica, nel caso del MOV è invece molto più basso.
Nel caso dello scaricatore ad innesco (GDT) è possibile che vi sia una corrente residua, che prende il nome di $I_{sx}$ ovvero una corrente susseguente, a seguito della scarica.

Gli svantaggi dei GDT sono la corrente susseguente e il livello di tensione massima alta.
Nel caso invece del MOV si ha un problema dovuto all'invecchiamento e ai successivi interventi che lo deteriorano, non c'è interruzione galvanica dunque vi sarà sempre una corrente di dispersione (o di fuga) $I_{c}$ che tende a zero con il MOV appena installato, fino a richiedere una completa sostituzione per valori di correnti eccessive.
È diversa dalla corrente susseguente.
Il livello di protezione $U_{p}$ è invece basso (a vantaggio della sicurezza).

Si possono installare coppie di scaricatori in serie o in parallelo per combinare vantaggi e svantaggi di entrambi.

La linea sarà caratterizzata da un'impedenza fino allo scaricatore e successivamente un'altra induttanza fino al nodo collettore, la tensione alla quale si troverà il dispositivo da proteggere non sarà legato solo al livello $U_{p}$ ma anche alle cadute sulle induttanze $L \frac{di}{dt}$, la corrente è di tipo impulsivo e la sua variazione può portare comunque a delle tensioni maggiori del livello di protezione dello scaricatore, è tanto più pericoloso quanto più è veloce la corrente di scarica e quanto più è grande $L$ associata all'induttanza del cavo, proporzionale alla sua lunghezza, si vuole ridurre il più possibile almeno l'induttanza tra lo scaricatore e il collettore.

Per collegamento a terra si intende il collegamento più veloce all'impianto di terra, si può scegliere di collegarsi al conduttore di protezione o il collettore di terra.
L'induttanza a monte invece dipende dalla distanza di installazione dello scaricatore se all'inizio o alla fine dell'impianto, dipenderà dalla categoria di rischio prima definita.

Si definiscono tre tipi di SPD in funzione della forma d'onda, con i tempi di salita e discesa, si definiscono:

<center>

| Tipologia di scaricatore | Forma d'onda   |
| ------------------------ | -------------- |
| SPD Tipo 1               | $10 -350\mu s$ |
| SPD Tipo 2               | $8 -20 \mu s$  |
| SPD Tipo 3               | $1.2 -50\mu s$ |


</center>

I valori indicati sono le tensioni di prova con le quali deve funzionare lo scaricatore.
Questi valori si possono avere in caso di fulmine (tipo 1), si installerà all'arrivo linea, lontano dagli utilizzatori, è legato a tensioni di fulminazione.
La sovratensione può essere indotta per accoppiamento galvanico o induttivo, all'avvicinarsi dell'impianto si avranno sovratensioni più veloci (tipo2) e così via.

La norma CEI-EN:62305 indica delle zone definite dalla sigla LPZX con X un numero, nel caso della LPZ0, quella esterna può essere di tipo A o B se presente o meno il LPS (parafulmine).
In questa regione la normativa prevede l'installazione di uno scaricatore di tipo 1 al confine con la zona LPZ1, dove sono presenti i quadri, in questo punto si installa uno SPD di tipo 1.

All'interno dei locali, tra la zona LPZ1 e LPZ2 si collegano scaricatori di tipo 2, in questo punto si proteggono gli utilizzatori di categoria II.
Al confine con la LPZ3 sono presenti i dispositivi di categoria I come server ecc... e vanno protetti da scaricatori di tipo 3.

Le zone definite dalla norma definiscono il rapporto tra la tipologia di scaricatori e la categoria di utilizzatori da proteggere.
