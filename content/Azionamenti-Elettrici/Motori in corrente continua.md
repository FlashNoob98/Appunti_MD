# Realizzazione del rotore
Il rotore di un motore in corrente continua è solitamente realizzato da una o più spire, queste possono essere alimentate da un circuito esterno, fisso, si possono montare due anelli sull'albero che diventeranno i morsetti terminali del rotore, mediante delle spazzole si crea un contatto strisciante che permette la circolazione di corrente nel rotore.
Così facendo si avrebbe una corrente di verso costante nell'avvolgimento, superato il piano neutro però si avrebbe una forza in verso opposto, dunque si avrebbe un allineamento della spira con il campo, senza produrre una rotazione continua.

Non si possono dunque usare gli anelli, si usano invece due "mezzi anelli", ai quali sono rispettivamente saldati i conduttori della spira; se la sorgente esterna è costante si ha l'inversione della corrente ogni mezzo giro nella spira, ciò permette di avere una risultante delle forze diversa da zero nell'intero giro.
**Il campo si inverte sul piano neutro**.
Il contatto spazzola-rotore prende il nome di **collettore** o, esclusivamente per la macchina in corrente continua, prende il nome di **commutatore**.

Se anziché usare una spira si usa una matassa di $N$ spire, la forza sarà allora moltiplicata per $N$, anche il collettore dovrà essere formato da $2N$ contatti differenti.
Analogamente alle macchine in corrente alternata, il rotore è formato da lamierini ferromagnetici contenenti apposite cave per ospitare i conduttori, filiformi o a piattina per le macchine di grossa taglia.
Le cave potrebbero essere aperte, semi aperte o chiuse (raramente).

L'avvolgimento del rotore è chiuso su sé stesso, ovvero ogni matassa è collegata a quella adiacente, il punto in comune tra due matasse è collegato ad una lamella del collettore, formata da rame molto raffinato e levigato, ciascuna lamella è isolata da quella adiacente, solitamente con della mica, esistono tante lamelle per quante sono le matasse. Se anche si portasse in rotazione il rotore, la forza elettromotrice indotta dallo statore sarebbe complessivamente nulla a causa della disposizione geometrica delle matasse.
Il collettore comporta comunque una serie di problemi legati alla sua usura e manutenzione.

Se si alimenta il rotore mediante le spazzole quindi si avrà una forza elettromotrice diversa da zero, le matasse sono in serie dunque la corrente che attraversa i morsetti di alimentazione impegnerà tutto il rotore in ogni momento.
La corrente incontra metà avvolgimenti "in un verso", gli altri in verso opposto.
Durante il passaggio da un collettore all'altro, cambierà il verso della corrente nel conduttore, questo sarà dello stesso segno durante mezza rotazione, il passaggio da un semipiano all'altro e dunque il cambio del verso della corrente, si ha la commutazione.

La lamella è leggermente più stretta della spazzola per questo motivo ci saranno sempre alcuni istanti in cui le spazzole tocchino due differenti lamelle, in questo momento l'avvolgimento è cortocircuitato. Si assume che la commutazione sia lineare.

Ad aumentare il numero di matasse, aumenta la precisione con la quale si può approssimare la caduta di forza magnetomotrice ad una funzione lineare, si ottiene una forma a triangolo, con il picco ortogonale all'asse polare, chiamato **asse interpolare**. È la posizione delle spazzole a determinare l'asse magnetico del rotore, dato che questo è simmetrico rispetto al suo asse.

Se si suppone la linearità della macchina, si ha che sommando i campi di induzione si ottiene un contributo solo dal campo di eccitazione, il campo di armatura fornisce un flusso nullo, indipendente dal carico, dunque si può affermare che **la macchina in corrente continua è a flusso costante**.

Nella realtà il punto di magnetizzazione del ferro è vicino al ginocchio della curva, dunque è presente una magnetizzazione non lineare del circuito magnetico, il flusso diminuisce sotto carico, si suppone che lungo un polo si possano considerare due effetti, il primo che aumenta il flusso, l'altro lo diminuisce, teoricamente della stessa quantità ma a causa della caratteristica magnetica appena citata si ha un effetto complessivo *smagnetizzante*, la pendenza della curva magnetica a sinistra è maggiore.
Si vuole limitare questo effetto, si può aumentare il traferro, siccome 
$$
B_{a}=\mu_{0}H_{a} = \mu_{0} \frac{N_{a}i_{a}}{\delta}
$$
si riduce in questo modo la riduzione di flusso, chiamata anche reazione di armatura ma si chiama campo di armatura. Se aumento il traferro diminuisce però anche il campo di eccitazione, devo aumentare la corrente di eccitazione per ottenere la stessa induzione, aumentano le perdite di eccitazione.

In alternativa si usa l'**avvolgimento di compensazione**, ovvero un ulteriore avvolgimento disposto nei poli ma connesso elettricamente in serie al rotore e contravvolto a quest'ultimo, si ipotizza che il campo di armatura sia interamente compensato dal campo di compensazione, in questo modo al traferro sarà presente solo il campo di eccitazione.
Questa caratteristica è in teoria valida punto per punto e non solo complessivamente in ogni semiasse.

Con uno di questi due sistemi si può realizzare una macchina approssimativamente a flusso costante.

# Caratteristiche delle spazzole
Realizzare una spazzola sfaldabile permette di salvaguardare lo stato del rotore, è più semplice ed economico sostituire le spazzole piuttosto che riparare il rotore; si richiede una manutenzione ordinaria che può avere anche cadenza giornaliera.

Tra le spazzole e il collettore inoltre si possono avere delle tensioni elevate causate dalla continua commutazione della corrente nel rotore, rappresentabile con un carico ohmico-induttivo, questo immagazzina sempre una energia magnetica. Un motore in movimento produce un numero di commutazioni proporzionale al numero di collettori e alla velocità del rotore. Lo stato di scintillio è praticamente costante nella regione del collettore, ciò comporta un aumento della temperatura dei materiali, soprattutto del rame che tende a deformarsi ed ovalizzarsi, accentuando ulteriormente questo fenomeno a causa degli "sbacchettamenti" con le spazzole.

Per ridurre lo scintillio si può pensare di indurre nell'avvolgimento in commutazione un flusso di segno opposto, durante la commutazione, che riducendo il flusso riduce le sovratensioni generate. Si realizzano dunque dei poli ausiliari, presenti sempre nello statore, disposti lungo l'asse polare, connesso in serie all'armatura, ha un'azione locale sulla commutazione, senza interferire troppo nel bilancio energetico della macchina.
Viene sempre utilizzato nelle macchine da una certa taglia in poi.

Il circuito di armatura vede in serie una resistenza ed un'induttanza dovuta ai poli ausiliari, in serie a quelli di compensazione, connessi poi alla macchina; devo tener conto delle ulteriori resistenze nel calcolo della resistenza totale di armatura.

Se la macchina è compensata, l'induttanza di armatura è molto bassa, dunque la macchina ha una costante di tempo relativamente piccola, la resistenza prevale sull'induttanza, se la macchina è compensata, è più semplice da controllare, ciò può comportare però l'utilizzo di filtri a valle dei convertitori se l'induttanza è troppo bassa, per livellare la corrente in uscita.

# Classificazione dei motori in corrente continua
Vengono classificate dal collegamento dell'avvolgimento di eccitazione rispetto a quello di armatura, quindi in *serie*, in *parallelo*, o *compound* per le macchine ad **eccitazione dipendente**, collegate ad un'unica rete. 
L'eccitazione può essere **indipendente** se questa è connessa ad una rete differente oppure è realizzata mediante magneti permanenti.

La macchina ad eccitazione indipendente ha preso piede negli ultimi anni con lo sviluppo dei convertitori e la facilità di realizzare alimentazioni differenti, prima più difficili da realizzare.
