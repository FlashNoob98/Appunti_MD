A prescindere dal tipo di controllo utilizzato, nei vari riferimenti, o il [[Controllo digitale#Controllore risonante|controllo risonante]], tutti forniscono in uscita uno o più valori di duty cycle.

Si suppone di lavorare con un inverter trifase su un carico con centro stella isolato, si suppone che la tensione di DC-Link sia suddivisa in due parti $\frac{V_{dc}}{2}$ e $-\frac{V_{dc}}{2}$, dunque la tensione della gamba rispetto al centro stella, con segnale $S_k$ vale:
$$
V_{k}=\frac{V_{dc}}{2}(2S_{k}-1) = V_{dc}d_{k}-\frac{V_{dc}}{2}
$$
Il duty cycle della PWM oscilla però tra 0 ed 1, non ammette valori negativi, dunque va traslato il segnale di 0.5.
$$
d_{1}=\frac{V_{1}^{+}}{V_{dc}}  + \frac{1}{2}
$$
# Space vector modulation
Si ottiene il duty cycle non considerando le tensioni di riferimento di fase ma usando un formalismo vettoriale.
(vedi anche [[space vector modulation]]).

Il valore medio di una gamba, pilotata con un certo duty cycle, il suo valore medio sarà $d_{k}V_{dc}$, ovvero il valore del punto centrale rispetto al negativo, non è però la tensione sul carico, che invece sarà,applicando le leggi di kirchoof:
$$
[d_{k}v_{dc}]=V_{c_{1}}^{*}+V_{o'o}
$$
Il termine omopolare non influisce sul carico.

Le tre tensioni di riferimento, nel piano complesso hanno solo il componente simmetrico $\vec{v}^*(t) = \frac{2}{3}\left( v_{1}^*+v_{2}^*e^{j{2}\pi/3}+v_{3}^*e^{j4\pi/3} \right)$

Per le gambe dell'inverter, il componente simmetrico dipende da $S$:
$$
\vec{V}_{N}=\frac{2}{3}V_{dc}[S_{1}+S_{2}e^{j{2}\pi /3}+S_{3}e^{j}4\pi /3]
$$
Dunque si hanno 3 valori discreti che determinano in totale 8 posizioni del vettore del componente simmetrico nello spazio.
Nel caso degli stati $[1,1,1]$ e $[0,0,0]$ la tensione sul carico è nulla, c'è un corto tra le gambe dell'inverter e il positivo o il negativo dell'alimentazione.
Gli altri vettori sono disposti a formare un esagono.

Questo può essere suddiviso in 6 settori, ogni settore è la parte di piano compresa tra due vettori attivi contigui.
Una buona modulazione prevede che nel settore $i$-esimo, il valore medio di tensione sia pari a quello di riferimento.
$$
\vec{V}^* = \frac{1}{T_{c}} \int_{t}^{t+T_{c}}\vec{V}_{N}(t)dt = \alpha V_{i}  +\beta V_{i+1}+\gamma \vec{0}
$$
dove $\alpha,\beta,\gamma$ sono i tempi per i quali permangono certe tensioni.
$$
\vec{V}^* = \vec{v}_{i} \frac{t_{i}}{T_{c}} + \vec{v}_{i+1} \frac{t_{i+1}}{T_{c}} + \vec{0}\frac{t_{0}}{T_{c}}
$$

Vanno identificati i singoli settori, l'angolo di ogni settore ha un angolo di 60°.
Si effettua una trasformazione di clark separando il componente simmetrico in parte reale e immaginaria, per individuare il settore confronto questi due termini, si individua il quadrante confrontando i segni dei componenti, poi individuato il quadrante si vede quale termine è maggiore, con un fattore  angolare:
$$
v_{x}> \frac{v_{y}}{\sqrt{ 3 }}?
$$
.
Si individua facilmente il settore senza eseguire trigonometria.

Si effettua poi l'**operazione di riporto al settore primario di riferimento**.
$$
\vec{v}^*=\vec{v}e^{j\phi^*} = \vec{v}e^{j\pi/3(i-1)}e^{j\Delta \phi t}
$$
Se si ha un vettore di riferimento nel secondo quadrante ad esempio:
$$
\vec{v}^*=\frac{2}{3}V_{dc}e^{j\pi_{3}} = \frac{2}{3}V_{dc}(\alpha e+ \beta e^{-j\pi/{3}})
$$
si ottiene una scomposizione di riporto.
$$
\vec{v}_{rp}^* = \vec{v}^*e^{-j\pi/3} = (v_{x}^*+jv_{y}^*)\left( \cos \left(\frac{\pi}{3}\right) + j\sin\left( \frac{\pi}{3} \right) \right)


$$
.

La parte immaginaria della tensione di riferimento:
$$
v_{yrip}^* = \frac{2}{3}V_{dc}\beta
$$
mentre la parte reale:
$$
v_{xrip}^*
$$
fornisce $\alpha$.

Se $\alpha+\beta<1$ il restante $d-1$ sarà il vettore nullo, viceversa se $\alpha+\beta>1$ allora sto esprimendo il vettore con componenti maggiori, si sta "scavallando" l'esagono, si usa un $\alpha$ normalizzato.
$$
\alpha_{new} = \frac{\alpha}{\alpha+\beta},\qquad \beta_{new}=\frac{\beta}{\alpha+\beta}
$$

Sono al limite dell'esagono, dunque $\gamma$ sarà nullo, viceversa se il vettore di riferimento è piccolo, fornirò principalmente il vettore nullo.

Sommando i componenti dei vettori, ottengo i valori dei duty ratio:
$$
d_{1} = \alpha+\frac{\gamma}{2} \qquad d_{2}=\alpha+\beta+\frac{\gamma}{2}\qquad d_{3}=\frac{\gamma}{2}
$$
il vettore nullo è diviso a metà tra 000 e 111.
In tal modo ci sarà la commutazione di un singolo componente ogni variazione del valore di $\gamma$.

Con una modulazione SVM ho una regione di linearità maggiore rispetto alla sottoscillazione sinusoidale.
Per costruzione si vede il raggio della circonferenza iscritta nell'esagono che ha lato interno pari a $\frac{2}{3}V_{dc}$:
$$
\frac{2}{3}V_{dc}\sin{60} = \frac{V_{dc}}{\sqrt{ 3 }} = 1.15V_{dc}
$$
Si è esteso il range di modulazione lineare del 15%.
L'omopolare delle forme d'onda in SVM è una triangolare.

# Sotto oscillazione sinusoidale
Si realizza con il confronto di due segnali, una sinusoide alla frequenza desiderata in uscita,
un'onda triangolare ad alta frequenza, ovvero alla frequenza di campionamento.
Quando la forma triangolare è maggiore della sinusoide, si fornisce un segnale nullo in uscita,
altrimenti si fornisce una tensione positiva (s=1).

Senza eseguire calcoli si vede che la distanza tra due intervalli del segnale sono grandi
nelle zone in cui la sinusoide è maggiore, più piccoli dove la sinusoide ha un valore più basso.

La tensione di fase continua a poter assumere due soli valori $V_s$ e $0$.
Per ridurre il contenuto armonico e ottenere una modulazione simmetrica si deve avere che il
rapporto tra la frequenza del triangolo e della sinusoide sia un numero intero dispari, se è intero
si ha continuità del campionamento tra un periodo e l'altro, si parla ovvero di modulazione sincrona.

Se è dispari, si ha un numero dispari di semi onde del triangolo in ogni semi onda della
sinusoide, ciò comporta che si è sincroni anche rispetto al semi periodo, creando però una successione
di intervalli simmetrica, se fosse pari ciò non sarebbe vero.

Per assicurarsi che in ogni periodo del triangolo ci siano due intersezioni con la sinusoide,
allora la frequenza del triangolo indica il numero di commutazioni.

Affinché ci sia sempre intersezione tra la portante e la modulante, l'ampiezza della portante deve
essere maggiore della modulante, ovvero l'ampiezza del triangolo deve essere superiore alla sinusoide.

La forma d'onda di corrente resta molto distorta, la sottoscillazione non è sufficiente a migliorare
lo spettro in frequenza.
Il precedente spettro di tensione ottenuto con l'onda rettangolare, aveva un andamento regolare
decrescente, in questo caso invece è vero che non è presente la 5 armonica ma sono presenti
armoniche superiori ad ampiezza maggiore.

Per quanto riguarda la corrente invece si ha uno spettro regolare decrescente, è più ricca di armoniche
rispetto all'onda rettangolare ma la prima armonica è la 7 e non la 5.

Sia $R_f$ il rapporto tra le frequenze, la prima armonica dopo la principale è $R_f-2$, in questo
caso 7.
Aumentando dunque $R_f=21$ si ha un'analoga forma d'onda rispetto alla precedente ma con più commutazioni.
In questo caso si vede che la forma d'onda di corrente nel tempo è migliorata, lo spettro di tensione
ha come prima armonica la 19 esima, lo spettro non è regolare decrescente, si hanno armoniche superiori
di ampiezza maggiore, sono inoltre a grappoli, centrati su frequenze multiple di $R_f$, in questo caso
ad esempio non è presente l'armonica 21 ma sono presenti 19 e 23, analogamente 41 e 43 e così via...

La sottoscillazione, anche con alto $R_f$ non ha migliorato il contenuto armonico di tensione, è migliorato
però quello della corrente, alle alte frequenze la macchina elettrica presenta un'impedenza più alta.

Solitamente una macchina a 50Hz viene modulata a 1000Hz, ad esempio con $R_f=99$ 
si ha uno spettro di tensione con armoniche a 97 e 101, queste due vengono attenuate da un'impedenza
97 volte maggiore cioè quasi 100, si riduce moltissimo lo spettro di corrente rendendola praticamente sinusoidale.
Se la fondamentale è 50Hz, con $R_f=99$ siamo a 5kHz, è una frequenza disponibile per il convertitore.

Usando una tensione distorta però si ha una sollecitazione maggiore dell'isolante, a causa degli elevati fronti d'onda.
Rispetto all'onda rettangolare, la prima armonica è di ampiezza minore, questa differenza si riduce
ad aumentare il rapporto di modulazione, se si supera 1 si ha un'ampiezza tra $V_1$ e $V$ di $1/2$.
fino ad un limite pari a $2/\pi$.

Esistono delle condizioni per cui la sinusoide ha valori maggiori del triangolo, in alcuni periodi
del triangolo non avverrebbe la commutazione, questo fenomeno si chiama **sovra modulazione**.
Al limite si può ottenere un'onda rettangolare. La sovra modulazione può essere utile comunque per ottenere
una tensione maggiore, a discapito del contenuto armonico.

Nel caso di un treno, la frequenza di alimentazione è crescente all'aumentare delle velocità.
Se il sistema modula a 1kHz si può avere in uscita una tensione variabile da 1Hz ad esempio fino a 100Hz dunque
il contenuto armonico sarà variabile al variare della velocità, cambierebbe il rapporto $R_f$.

Un'altra proprietà utile del rapporto tra le frequenze è che questo sia multiplo di 3, in tal caso è necessario
un singolo triangolo per pilotare le tre fasi.

Se le frequenze sono alte non è più necessario che la modulazione sia sincrona, l'errore sul periodo diventa trascurabile.
Viceversa a potenze alte e frequenze base più basse, devo allora variare anche la frequenza dell'onda triangolare,
che siano sempre multipli della frequenza base, garantendo il valore del rapporto $R_f$, non si esegue quest'operazione
in ogni istante ma si fa per un certo intervallo di tempo sufficientemente grande.

Si può iniettare una terza armonica sulla fondamentale per aumentare il limite di sovra modulazione, si riduce l'ampiezza massima della sinusoide.

Nella trazione ferroviaria, si modula solitamente a 1000Hz, il rapporto $R_f$ con un'onda a 50Hz sarebbe 10-12, troppo
poco, si può pensare allora di inserire i "buchi" di tensione in un modo differente, mediante un microprocessore si possono calcolare i $2n$ istanti in cui inserire $n$ buchi (un fronte di salita e uno di discesa).
Per fare ciò si scrive l'equazione dell'armonica n-esima e la si pone uguale a zero, si ottiene un insieme di equazioni
trascendentali complesse.

Per un inverter trifase esistono 8 stati possibili, due di questi forniscono in uscita una tensione nulla, dunque solo
6 attive, distanziate tra loro di 60 gradi.

# Regolatore ad isteresi
Una tipologia di regolatore relativamente semplice è quello ad **isteresi**, dal confronto della corrente desiderata
e quella misurata si ottiene un certo errore, quando l'errore esce fuori banda si agisce sul convertitore, invertendo
di volta in volta l'andamento della corrente. In questo caso non è predeterminata la commutazione del sistema.
Si stabilisce solo il limite dell'oscillazione di corrente attorno al valore desiderato.
Al diminuire della banda aumenta la frequenza di commutazione, in ogni caso non si può superare il limite
del convertitore.
Non si usa questo sistema per macchine di alta potenza. Mi conviene però usare un sistema analogico per intercettare
sempre l'intersezione dell'errore con la banda, altrimenti in analogico potrei perdere la misura tra due periodi di campionamento.

Posso dunque garantire una frequenza media di commutazione senza avere la certezza di operare con la massima frequenza possibile.
Non devo comunque danneggiare i componenti quindi devo scegliere una banda che vada bene per le condizioni peggiori.

Se si usa l'isteresi digitale, si limita la massima frequenza di commutazione alla frequenza di campionamento, si
perde leggermente il controllo della banda.

Se uso il controllo ad isteresi su un convertitore VSI ottengo di fatto un convertitore a corrente impressa a causa
dell'anello di retroazione, si può imporre in questo caso qualsiasi forma d'onda di corrente, vengono chiamati CR-VSI,
ovvero Current-Regulated-Voltage-Source-Inverter.

In questo caso il controllo della macchina è dovuto solo dal secondo stadio, non si ha più il problema del transitorio sulla capacità.
Il VSI migliora sensibilmente lo spettro di corrente, rispetto alla modulazione del CSI.

In alternativa al regolatore ad isteresi, si può usare un PI sull'errore di corrente, che fornirà una tensione
di riferimento, che viene inviata ad un modulatore che effettuando la sottoscillazione pilota il VSI.

