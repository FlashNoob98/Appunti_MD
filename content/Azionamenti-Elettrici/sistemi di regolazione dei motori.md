Prima dell'avvento dei [[Dinamica dei convertitori elettrici|convertitori]] esistevano delle macchine elettriche che svolgevano il compito di alimentatori a tensione variabile, erano detti convertitori rotanti, con tutti i problemi annessi a rumore eingombri.
L'evoluzione è stata quella di sostituire tutte le variazioni di tensione reostatiche e mediante convertitori rotanti con dei convertitori statici, che possano effettuare la conversione in uno o più stadi.

Nel caso dei [[Motori in corrente continua|motori in corrente continua]] vengono utilizzati convertitori come i chopper (come il [[Boost converter|boost]]) se la tensione in ingresso è continua, oppure se la sorgente è alternata si può utilizzare un raddrizzatore, variando eventualmente l'angolo di innesco dei componenti.

I quadranti dei convertitori riguardano la loro capacità di gestire il flusso di energia elettrica, in ingresso o uscita.
Sono diagrammi tensione corrente e si pone la tensione sull'asse delle ascisse, e la corrente sulle ordinate. La velocità del [[motore ad eccitazione indipendente]] è proporzionale alla tensione di armatura, proporzionale alla tensione di alimentazione. La coppia è proporzionale alla corrente quando si hanno  macchine compensate.

C'è corrispondenza tra i quadranti dei convertitori e quelli dei motori, un convertitore è attivo(?) se presenta il funzionamento nel primo e terzo quadrante.
Un convertitore che possa funzionare da [[motore ad eccitazione indipendente#Frenatura a recupero|freno]] ha invece due quadranti di corrente con corrente positiva, oppure può funzionare con due quadranti di tensione con corrente positiva per la [[motore ad eccitazione indipendente#Frenatura in controcorrente (tensione invertita)|frenatura a tensione invertita]].

I dispositivi più utilizzati nei convertitori sono gli SCR, ovvero Silicon-Controlled-Rectifier, possono essere messi in conduzione quando la tensione ai suoi capi è positiva e si spengono naturalmente quando la corrente attraversa lo zero.
I diodi funzionano analogamente ma non si può comandare l'accensione, entrano in conduzione appena la tensione ai loro capi diventa positiva.

# Chopper Step-Down
Partendo da una tensione in continua, esiste un dispositivo comandato, in accensione e spegnimento, in serie all'alimentazione e al motore, un diodo in antiparallelo al carico permette la richiusura delle correnti di ricircolo (scarica delle induttanze).
Questo convertitore lavora nel primo quadrante.

La conduzione dei componenti elettronici non è idealmente mai contemporanea, durante la conduzione del componente attivo $C$ si ha la tensione di alimentazione ai capi della macchina elettrica, il diodo è contropolarizzato e non può condurre.
Viceversa quando il componente attivo è aperto il diodo conduce e porta ai capi del carico la tensione nulla.

In questo modo è possibile fornire alla macchina elettrica una tensione periodica con un tempo di conduzione variabile, è possibile variare la frequenza di questa tensione periodica, la frazione in cui il componente attivo conduce è chiamato $t_{on}$, il periodo della tensione $T$ e si definisce di conseguenza il *duty cycle* $\alpha=\frac{t_{on}}{T}$.
Il valore medio $V_d$ della tensione fornito al carico, con tensione in ingresso $V_L$ sarà:
$$
V_{d} = \frac{V_{L}t_{on}}{T} = \alpha V_{L}
$$
Dunque il valore medio è variabile tra $0$ e $V_L$.

Se la tensione è periodica, a valor medio diverso da $0$ allora la corrente non è costante ma varia anch'essa attorno un valore medio.
Frequenze tipiche del sistema sono nell'ordine del $kHz$, l'onda di corrente sarebbe quasi triangolare, nella realtà sono tratti di esponenziale del primo ordine ma essendo la costante di tempo del motore più grande di quella del convertitore, si può approssimare l'esponenziale con la sua tangente nell'origine, quindi lineare.

Per quanto riguarda la corrente di linea invece, questa è periodica ma durante il $t_{on}$  è identica a quella nel motore, durante il $t_{off}$ è invece nulla, si sta assorbendo quindi dalla linea una corrente fortemente distorta.

A rigore si desidererebbe avere una coppia costante, di conseguenza una corrente costante, le ondulazioni di corrente si riflettono con una oscillazione della coppia, se la coppia resistente è costante, non vi sarà mai un equilibrio preciso, dunque anche la velocità della macchina oscillerà di un certo valore, nonostante vi sia l'equilibrio dei valori medi.
$$
M_{m} - M_{r} = J \frac{d\omega_{r}}{dt}
$$
È un regime periodico permanente ma non stazionario.
Questo effetto è apprezzabile però solo con un valore di inerzia $J$ piccolo, viceversa se l'inerzia (di tutto ciò che è connesso all'albero motore) è grande, la velocità varia di una quantità anche infinitesima. Resta comunque la sollecitazione all'albero che, nonostante non vari molto la sua velocità, subisce la variazione di coppia. Si avrà una eventuale **rottura a fatica**, l'albero può eventualmente rompersi in un tempo inferiore a quanto stimato.

Un ulteriore problema può essere quello della **risonanza**, se le oscillazioni hanno la stessa frequenza caratteristica del sistema, questo può subire delle vibrazioni amplificate rispetto a quelle emesse dal motore.
Le frequenze di risonanza degli alberi possono essere negli ordini degli $Hz$, usando frequenze di commutazione più elevate non si rischia la risonanza.

Avendo una corrente distorta, questa ha un contenuto armonico, solo il valore medio fornisce una componente utile di coppia, le altre, fornendo valori di coppia alternativi hanno un effetto medio nullo all'asse ma aumentano comunque il valore efficace della corrente e dunque le perdite elettriche ad esso legato, si ha una riduzione del rendimento.
$$
I_{RMS}^2 = I_{0}^2+I_{1}^2+I_{2}^2+\dots+I_{n}^2
$$
Si calcola l'ampiezza di ondulazione della corrente con:
$$
\Delta I = I_{\text{max}}-I_{\text{min}} \simeq \frac{\alpha(1-\alpha)V_{L}}{f L_{C}}
$$
l'ondulazione varia con $\alpha$, il massimo di questa funzione si ha per $\alpha=0.5$, aumentando l'induttanza, la funzione $\Delta I$ trasla verso il basso riducendo anche l'ampiezza massima.

Si supponga di alimentare un motore con una tensione nominale di $100V$, per regolare la sua velocità deve ricevere una tensione inferiore alla nominale, si potrebbe avere una linea a $100V$ con un chopper con $\alpha$ variabile da 0 a 1 ma se la linea fosse ad esempio a $200V$ allora la regolazione di $\alpha$ sarebbe limitato tra 0 e 0.5, così via aumentando la tensione di linea.
Non sempre si può variare la tensione della linea, per questo motivo è utile scegliere un motore con tensione nominale prossima a quella della linea, in modo da lavorare con $\alpha$ elevati per ridurre l'ondulazione.
Non ha dunque senso usare il chopper per adattare la tensione di alimentazione diversa da quella di targa del motore, si perde la capacità di regolazione, riducendo la risoluzione dell'angolo di innesco e si aumentano le oscillazioni di corrente.

Inoltre esiste un problema di isolamento, se per assurdo si collegasse una macchina da $100V$ su una linea da $1000V$, in valore medio sarebbe possibile mediante un angolo $\alpha$ di 0.1, ma la macchina sarebbe comunque stata sollecitata a $1000V$ per un certo periodo, danneggiando irrimediabilmente l'isolamento in poco tempo.

Un ulteriore metodo per ridurre il $\Delta I$ è quello di aumentare $L_c$, se la macchina è compensata l'avvolgimento di compensazione ha un'induttanza negativa rispetto a quella di armatura e ad essa coincidente.
A pari resistenza la costante di tempo si riduce per macchine compensate, probabilmente dovrò aggiungere un'induttanza esterna sulla linea, che influenzi l'ondulazione di corrente fornita al motore, avrà un costo e dimensioni proporzionali con la taglia della macchina.

In alternativa un aumento della frequenza del chopper porta ad una riduzione dell'ondulazione senza modificare il circuito, aumentano però le perdite di commutazione, inoltre bisogna rispettare il limite di commutazione dei componenti elettronici, solitamente il limite di *frequenza di switching* del dispositivo è inversamente proporzionale alla sua taglia. MOSFET per applicazioni di microelettronica possono raggiungere frequenze di commutazione negli ordini dei $GHz$, mentre tiristori di potenza possono commutare solo con frequenze negli ordini dei $kHz$.
Ulteriori componenti in sviluppo sono i $GaN$ (Nitruro di Gallio) che permettono il raggiungimento di frequenze più elevate.

## Dispositivi utilizzati nei chopper
Alcuni componenti tipicamente utilizzati nei chopper sono i GTO, ovvero Gate-Turn-Off, si può inviare un segnale di spegnimento, possono condurre elevate correnti, hanno una frequenza massima di $1kHz$.

Gli IGBT invece hanno frequenze più elevate ma potenze inferiori.

Un'alternativa al GTO è usare un IGBT con un circuito di spegnimento, la rete è in continua dunque non sarebbe possibile uno spegnimento "naturale" non essendoci mai il passaggio per lo zero della tensione di linea.
Si usava un IGBT in parallelo connessi con una capacità e un diodo per contro polarizzare il componente principale.
Le dimensioni del circuito di spegnimento erano notevolmente più grandi del dispositivo principale, si è eliminato un problema enorme con l'avvento dei dispositivi total-controllati.

## Conduzione discontinua
Se il valore di corrente è piccola, al limite per un angolo $\alpha$ si può avere una corrente nella macchina pari a zero per un certo intervallo, in tale intervallo si avrebbe l'interdizione di entrambi i componenti a stato solido, non si può più determinare il valore medio della tensione, senza la polarizzazione del diodo infatti ci sarebbe ai capi della macchina elettrica la tensione indotta $E$ dovuta alla sua rotazione.
Non c'è più una corrispondenza biunivoca tra $\alpha$ e $V_{d}$, analogamente con la velocità, si rischia di perdere il controllo della macchina.
Per ridurre la probabilità di avere conduzione discontinua si può aumentare l'induttanza.

## Filtri in uscita
Interponendo un filtro LC tra il chopper e la macchina elettrica si possono ridurre le ondulazioni di corrente e di tensione ai capi della macchina, la capacità manterrà la tensione quasi costante, con piccole oscillazioni.
Ciò comporterebbe però un forte rallentamento della dinamica della macchina, per questo motivo spesso è sconsigliato usare dei filtri capacitivi in uscita.

# Chopper Step-Up
Utilizzato quando si vuole fornire corrente verso la rete e avere corrente negativa nel carico, effettuando una [[motore ad eccitazione indipendente#Frenatura a recupero|frenatura a tensione variabile]], riducendo la tensione in ingresso, rispetto al motore quindi la tensione di alimentazione $V_{L}$ è minore della tensione indotta $E$, in questo caso il convertitore è uno step-up.
Ai capi del componente attivo $C$ vi sarà una tensione pari a $0$ e $V_L$ se questo conduce o meno, il valore medio $V_D$ si riduce all'aumentare di $d$.

L'apertura del componente attivo prevede lo strappo di una corrente anche elevata, che tende a mantenersi costante nel tempo, se fosse un interruttore si avrebbe un arco, nel caso di dispositivi a semiconduttore si ha una sovratensione inversa che supera il valore $V_L$ e che polarizza il diodo, a patto che questo sia sufficientemente veloce ad andare in conduzione.

# Chopper a due quadranti
Per effettuare sia una frenatura che un controllo di velocità è dunque necessario utilizzare chopper a 2 o a 4 quadranti.
In questo caso i comandi devono sempre essere inviati in maniera complementare ai due chopper, si potrebbe avere però una conduzione contemporanea durante la commutazione, che metterebbe in corto circuito la linea.

Devo per questo garantire un tempo minimo, chiamato *dead-time* che garantisca lo spegnimento completo di un componente prima dell'andata in conduzione del componente complementare per evitare il corto circuito sulla linea.

Si può in alternativa inserire un'induttanza di commutazione tra i due dispositivi, che impedisca il corto circuito, ma ho un aumento dell'induttanza del circuito con conseguente aumento dei tempi caratteristici.

# Chopper a quattro quadranti
In caso si voglia fornire alla macchina una tensione positiva e negativa, si può utilizzare una struttura a ponte che permetta di fornire una tensione al carico eventualmente invertita rispetto alla $V_L$.
Anche in questo caso va garantito un certo periodo di tensione nulla sul carico per evitare corto circuiti sulla linea.
In questo caso si può fornire una tensione bipolare al carico ma la corrente è comunque unidirezionale.

Utilizzando quattro componenti attivi, con una opportuna configurazione si può anche eventualmente invertire la corrente.

