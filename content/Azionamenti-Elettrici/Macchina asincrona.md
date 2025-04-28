# Metodi di avviamento di una macchina asincrona
Ci si pone il problema di avviare la macchina asincrona a causa delle elevate sovracorrenti (4-7 volte la nominale) che avvengono durante l'avviamento diretto.

Dal punto di vista termico nella maggior parte delle applicazioni non ha problemi, la macchina raggiunge lo scorrimento nominale in poco tempo.
Questa fase può essere però gravosa per la rete di alimentazione.
La temperatura massima degli avvolgimenti è quella tollerabile dagli isolanti, dipende dalla classe di isolamento, la maggio parte è in classe H quindi 180°C.

Si analizza il circuito ad $L$ di fase, si suppone che la macchina sia simmetrica.

Si ha una reattanza trasversale $X_m$, dovuta alla magnetizzazione.
In serie si ha una resistenza di statore, una reattanza di dispersione (totale) e una resistenza di rotore, riportata attraverso il fattore di scorrimento, la corrente di rotore è $\vec{I}_{r}$.
Il fasore di corrente di rotore varia con una frequenza pari a $s\omega$, coincide con la frequenza di rete solo quando il rotore è fermo (scorrimento unitario).

La curva di coppia varia da un valore pari alla coppia di avviamento, per la coppia di rovesciamento, fino a coppia nulla al sincronismo.
La coppia al rovesciamento è solitamente 2-3 volte la coppia nominale.

Alla velocità di sincronismo la corrente di statore è pari alla corrente magnetizzante $I_{\mu}$, solitamente tra il 30 e il 50% della nominale.
La corrente diminuisce dalla corrente di avviamento fino alla corrente magnetizzante quando si raggiunge il sincronismo, successivamente aumenta nuovamente nel funzionamento da generatore.

Per ridurre questa corrente all'avviamento si possono inserire in serie allo statore delle resistenze o degli induttori, si usano solitamente le resistenze se gli avviamenti sono poco frequenti o viceversa si possono usare degli induttori se si vogliono ottimizzare le perdite.

L'espressione della coppia:
$$
M_{e} = \frac{3p}{\omega} \frac{V_{s}^2}{\left( R_{s}+\frac{R'_{r}}{s} \right)^2 + X_{d,t}^2} \frac{R_{r}'}{s}
$$
lo scorrimento di rovesciamento:
$$
s_{k} = \frac{R_{r}'}{X_{d,t}}
$$
è solitamente il 10%.

La coppia di rovesciamento si calcola sostituendo lo scorrimento di rovesciamento:
$$
M_{k} = \frac{3p}{\omega} \frac{V_{s}^2}{2X_{d,t}}
$$

SI può trascurare la resistenza dello statore e considerare la coppia di avviamento:
$$
M_{e,\text{avv}} = \frac{3p}{\omega}\frac{V_{s}^2}{X_{d,t}^2}
$$
Dimezzando la tensione si riduce la coppia di 1/4.
Ottenuta la coppia minima, si calcola la corrente necessaria, si ricava la riduzione di tensione necessaria.

Esistono vari sistemi per variare l'alimentazione:
- Autotrasformatore, ha solitamente un rapporto di trasformazione costante
- Avviatore stella-triangolo, si riduce la corrente nella linea di $\sqrt{ 3 }$, la coppia di $1/3$.
- Soft-starter (sistema a TRIAC)
Il soft starter è costituito da un contattore, ovvero un attuatore elettromeccanico di potenza (simile al relee ma di potenza).
Un contattore viene rappresentato con dei cerchietti sui terminali di contatto.

Si ha a monte un contattore trifase che collega la linea, comandata da un'unica bobina.
Si dispone un altro contattore trifase sui morsetti "inferiori" della macchina.
Un terzo contattore trifase permette il collegamento a triangolo, va chiuso dopo aver aperto il contattore di centro stella, devo attendere un certo tempo prima di chiudere quello a triangolo per non mandare la linea in corto circuito.

# Avviamento diretto da rete
Nel caso in cui la rete fosse dimensionata per avviare la macchina, si dovrebbe utilizzare un contattore per avviare una macchina e non solo un interruttore, questo dispositivo infatti garantisce la chiusura contemporanea delle tre fasi, a differenza dell'interruttore.
Inoltre il contattore è pilotabile da un relè esterno.
È inoltre possibile allontanare i comandi del contattore dalla macchina, si può programmare l'intervento in base a fenomeni esterni, l'interruttore invece interviene solo per qualche fenomeno che avviene sullo stesso circuito.
Il contattore interviene mediante lo spostamento di una bobina su una guida, attraversata da corrente, essa si muoverà sempre con la stessa forza a pari corrente.

Per compiere un avviamento stella-triangolo, la macchina deve essere 400/690V e non 230/400.

# Controllo della macchina asincrona
Un modo semplice per controllare la macchina asincrona è quello di variare la resistenza di rotore, se questo è ad anelli, oppure variare il numero di coppie polari, in maniera discreta. Questi sistemi offrono però una capacità limitata di regolare le velocità.

Trascurando la caduta nello statore si può approssimare la tensione di fase con la tensione indotta $\vec{V}\simeq \vec{E}$.
La tensione indotta è proporzionale al flusso di mutua:
$$
{E} = \omega \Phi_{m}N_{s}\xi_{s} = 2\pi N_{s}\xi_{s}f\Phi_{m}
$$
ma il flusso di mutua:
$$
\Phi_{m} = B_{m}\tau_{p}L
$$
Al variare dei parametri della macchina variano le prestazioni della macchina, può variare il punto di magnetizzazione del ferro.
$$
L_{m} = \frac{N^2}{\mathbf{R}} = \frac{N^2}{\frac{l}{\mu S}}
$$
Al variare dell'induttanza varierà la corrente, per questo motivo si cerca di lavorare a flusso costante.
Si cerca di mantenere dunque la seguente legge di controllo:
$$
V = k f
$$
fino alla frequenza nominale in cui si ha la tensione nominale, oltre si mantiene la tensione costante al valore nominale, per non danneggiare l'isolamento della macchina. Per frequenze maggiori della nominale, inoltre, il flusso diminuisce, non si va in saturazione ma in deflussaggio.
Va implementata la legge nel convertitore, si regola solo la $f$ e si ricava la tensione di conseguenza, non possono essere indipendenti.

Si analizza il circuito a T della macchina:
$$
\vec{\Phi}_{m} = L_{m}\vec{I}_{\mu} = L_{m}\left( \vec{I}_{s} + \vec{I}'_{r} \right)
$$
ma la corrente di rotore si può esprimere in funzione di quella di statore:
$$
\left( \frac{R'_{r}}{s} +j\omega L'_{dr} \right)\vec{I}_{r}' + jL_{m}\left( \vec{I}_{s}+\vec{I}_{r}' \right) = 0
$$
dunque
$$
\left( \frac{R_{r}'}{s} + j\omega L_{r}' \right)\vec{I}_{r}' = -j\omega L_{m}\vec{I}_{s}
$$
ovvero
$$
\vec{I}_{r}' = -\frac{j\omega L_{m}}{R_{r}' + js\omega L_{r}'}\vec{I}_{s}
$$
avendo posto
$$
L_{r}'=L'_{dr}+L_{m}
$$
Si riscrive l'equazione del flusso:
$$
\vec{\Phi}_{m} = L_{m}\vec{I}_{s} \frac{R_{r}' + js\omega L_{dr}'}{R_{r}' + js\omega L_{r}'}
$$
ovvero dipende dalla corrente di statore e dallo scorrimento, fissata la $\omega$, non è vero che il flusso resta costante, come ipotizzato nel circuito ad L.
Al variare della frequenza varia anche la coppia della macchina, se questa diminuisce allora diminuisce anche la coppia.
Ciò è dovuto ad una diminuzione del flusso con la frequenza, a basse frequenze soprattutto prevale la caduta sulla resistenza di statore rispetto all'induttanza di dispersione, la $\vec{E}$ non varia linearmente con la variazione di $\vec{V}$.

A basse velocità si può ovviare questo problema usando una tensione maggiore, compensata, la legge di controllo diventa:
$$
V = kf + V_{0}
$$
ovvero a frequenza nulla, le induttanze sono corto circuiti, si fa in modo in cui
$$
\frac{V_{0}}{R_{s}} = I_{n}
$$
Devo conoscere la resistenza dello statore per ricavare questa seconda legge, in fase di avvio della macchina, il convertitore potrebbe effettuare la misura di questa resistenza per calcolare la tensione minima $V_{0}$.


## Coppia limite costante
Si vuole ricavare una legge di controllo per avere la coppia limite (alla corrente limite) costante al variare della frequenza.
La coppia elettromagnetica:
$$
M = \frac{3R'_{r}}{s}I_{r}'^{2}\cdot \frac{1-s}{\omega_{r}}
$$
ma $\omega_{r}=(1-s)\frac{\omega}{p}$ quindi
$$
M = 3p \frac{R_{r}'}{s\omega} I_{r}'^2
$$
ma la corrente di rotore:
$$
\vec{I}_{r}' = -\frac{js\omega L_{m}}{R_{r}'+js\omega L_{r}'} \vec{I}_{s}
$$
svolgendo il quadrato del modulo:
$$
M = 3p \frac{R_{r}'}{\cancel{s\omega}} \cdot \frac{(s\omega)^{\cancel{2}} L_{m}^2I_{s}^2}{R_{r}'^2 + (s\omega)^2 L_{r}'^2}
$$
si calcola la coppia limite imponendo la corrente limite:
$$
M_{L} = 3p \frac{R_{r}' (s\omega)_{L}L_{m}^2 I_{sL}}{R_{r}'^2 + (s\omega)_{L}^2 L_{r}'^2}
$$
dunque la coppia resta costante se $(s\omega)$ è costante e quindi se il flusso è costante.

Si ricava la tensione di alimentazione rispetto ai parametri di macchina nel circuito a T:
$$
\vec{V} = \vec{I}_{s}\dot{Z}_{eq} = \vec{I}_{s} \left[ R_{s}+j\omega L_{ds} + \frac{j\omega L_{m}(R_{r}'+js\omega L_{dr}')}{R_{r}' + js\omega L_{r}'} \right]
$$
Separando in parte reale e immaginaria:
$$
\vec{V} = \vec{I}_{s}(R_{s}+j\omega \dot{\gamma}) = \vec{I}_{s}[R_{s}-\omega \gamma_{I}+j\omega \gamma_{R}]
$$
svolgendo il modulo:
$$
V = I_{s}\sqrt{ (R_{s}-\omega \gamma_{I})^2 + \omega^2\gamma_{R}^2 }
$$
sviluppando il binomio:
$$
V = I_{s} \sqrt{ R_{s}^2 -2R_{s}\omega\gamma_{I} +\omega^2\gamma^2 }
$$
con $\gamma^2 = \gamma_{I}^2+\gamma_{R}^2$.
Questa condizione deve valere anche nelle condizioni limite, imponendo i valori di gamma limite e corrente limite, si ottiene una legge $V-\omega$ che permette di mantenere flusso e coppia costante anche a frequenze minori, senza sovraccaricare la macchina.
Questa legge dipende però dai parametri elettrici della macchina.

Non è però detto che i parametri restino costanti in ogni punto di funzionamento della macchina.
Il dominio di funzionamento della macchina si può costruire fornendo una retta orizzontale nel piano coppia-velocità che garantisca la coppia nominale per velocità inferiori a quella nominale.
Tutte le caratteristiche al di sotto di questa retta sono ottenibili in egual modo con la stessa legge precedente ma un valore di $(s\omega)$ più piccolo, nel caso in cui si desideri una coppia inferiore.

Oltre la frequenza nominale, la caduta sulla resistenza di statore diventa trascurabile rispetto a quella sull'induttanza di dispersione, si può considerare la $V\simeq E=kf\Phi$. Le curve di funzionamento saranno più piccole, i punti a corrente nominale formano una curva a coppia decrescente.
Lungo questa curva la potenza apparente assorbita è costante in quanto la tensione e la corrente sono pari alla nominale.
Se la potenza è costante anche la potenza meccanica è costante, dunque la caratteristica coppia velocità è un ramo di iperbole, per frequenza superiore alla nominale.

Si può utilizzare una forma approssimata della coppia per scorrimenti piccoli:
$$
M = \frac{3p}{\omega} \frac{V^2}{\left(\frac{R_{r}'}{s}\right)} = \frac{3p}{\omega} \frac{V^2s}{R_{r}'}
$$
Si ha la velocità massima in rapporto alla coppia di rovesciamento, ovvero se la coppia di rovesciamento è il doppio della nominale, la velocità massima è il doppio della velocità nominale.

Si analizzano i [[convertitori per la macchina asincrona]].

# Modello ai valori istantanei della macchina asincrona
La macchina è costituita da tre avvolgimenti elettrici spaziati di 120° nello spazio, si suppone che siano distribuiti e si abbia un campo spazialmente quasi sinusoidale, non è invece vero per le correnti che attraversano gli avvolgimenti, di forma generica:
$$
B^{(1)}_{s,k}(\alpha,t) =\mu_{0}\frac{\cancel{4}2}{\pi}\frac{N_{s}\xi_{s}}{\cancel{2}p\delta} i_{s,k}(t)\cos\left( p\alpha-\frac{2\pi}{3}(k-1) \right)
$$
il termine $\frac{4}{\pi}$ dipende dall'ampiezza della prima armonica spaziale dell'onda quadra.
Ciascun avvolgimento crea un campo magnetico al traferro fisso nello spazio, di ampiezza variabile nel tempo. Nell'ipotesi in cui $i(t)$ sia sinusoidale, l'ampiezza del campo è fissa.

Se ogni avvolgimento di statore crea un campo magnetico al traferro, allora il campo complessivo sarà la somma dei tre campi:
$$
B_{s}^{(1)}(\alpha,t) = \sum_{k=1}^3B_{s,k}^{(1)}(\alpha,t) = \frac{2\mu_{0}N_{s}\xi_{s}}{\pi p\delta}\sum_{k=1}^3 \mathrm{Re}\left\{i_{s,k}(t)e^{jp\alpha}e^{-j2\pi/3(k-1)}\right\}
$$
raccogliendo i termini che non dipendono da $k$ e moltiplicando per $\frac{3}{2}$:
$$
B_{s}^{(1)}(\alpha,t) = \frac{3\mu_{0}N_{s}\xi_{s}}{\pi \delta p}\mathrm{Re}\left\{ \vec{i}_{s}e^{jp\alpha} \right\}
$$
con $\vec{i}_{s}$ il componente simmetrico, o in inglese lo *space vector* pari a:
$$
\vec{i}_{s}\stackrel{\Delta}{=}\frac{2}{3}\sum_{k=1}^3 i_{s,k}(t) e^{-j 2\pi/3(k-1)}
$$
è un vettore complesso, il termine $\frac{2}{3}$ è tale che il risultato della sommatoria ha la stessa ampiezza della prima fase.

A meno di una costante posso estendere l'operatore parte reale anche al valore del campo:
$$
B_{s}^{(1)}(\alpha,t) = \mathrm{Re}\left\{ \vec{B}_{s}e^{jp\alpha} \right\}
$$
Si può utilizzare la stessa definizione anche per le tensioni:
$$
\vec{V}_{s} = \frac{2}{3} \sum_{k=1}^3 v_{s,k}(t)e^{j 2\pi/3(k-1)}
$$
Per calcolare il campo di rotore e quindi la corrente di rotore è necessario conoscere il numero di fasi del rotore $m_{r}$ e il componente simmetrico della corrente di rotore diventa:
$$
\vec{i}_{r} = \frac{2}{m_{r}}\sum_{k=1}^3 i_{r,k}(t)e^{-j{2}\pi/m_{r}(k-1)}
$$
Siano i due angoli di statore e rotore $\alpha$ e $\beta$ si ha che:
$$
\beta = \alpha - \theta_{r}(t)
$$
con $\theta_{r}$ l'angolo percorso dal rotore.
Il campo al traferro sarà pari alla somma di quello di statore e quello di rotore:
$$
B_{\delta}^{(1)}(\alpha,t) = B_{s}^{(1)}(\alpha,t) + B_{r}^{(1)}(\alpha,t)
$$
L'equazione di equilibrio alle varie fasi di statore:
$$
\begin{aligned}
v_{s,1} &= R_{s}i_{s{1}} \\
v_{s,2} &= R_{s}i_{s 2} \\
v_{s,3} &= R_{s}i_{s 3}
\end{aligned}
\Rightarrow
\begin{aligned}
v_{s,1} &= R_{s}i_{s{1}} \\
e^{-j{2}\pi/3}v_{s,2} &= R_{s}i_{s 2}e^{-j{2}\pi/3} \\
e^{-j{4}\pi/3}v_{s,3} &= R_{s}i_{s 3}e^{-j{4}\pi/3}
\end{aligned} \Rightarrow
\vec{v}_{s} = R_{s}\vec{i}_{s}
$$
moltiplicando ambo i membri per dei termini esponenziali si ottiene la stessa espressione scritta in funzione dei componenti simmetrici.

Usando i componenti simmetrici si può scrivere il modello della macchina:
$$
\begin{aligned}
\vec{v}_{s} &= R_{s}\vec{i}_{s} + L_{s} \frac{d}{dt}\vec{i}_{s} + L_{m} \frac{d}{dt} \left( \vec{i}_{r}'e^{jp\theta_{r}} \right)\\
0 &= R_{r}'\vec{i}_{r}' + L_{r}' \frac{d}{dt} \vec{i}_{r}' + L_{m} \frac{d}{dt} \left( \vec{i}_{s}e^{j p \theta_{r}} \right)\\
\frac{d^2\theta_{r}}{dt^2} &= \frac{1}{J}(M_{e}-M_{L})\quad \text{con }M_{e}=\frac{3}{2}p L_{m}\mathrm{Im}\left\{ \vec{\hat{i}}\ \vec{i}_{r}' e^{jp\theta_{r}} \right\}
\end{aligned}
$$
L'ultima equazione è l'equilibrio meccanico ed è valida solo nell'ipotesi di albero rigido, ovvero tutti i punti ruotino alla stessa velocità.

Il calcolo del momento elementare:
$$
m_{e}^{(1)} = \frac{LD}{2} \int_{0}^{2\pi} B_{\delta}^{(1)}(\alpha,t)\cdot \Theta_{r}(\alpha,t)d\alpha
$$
con $L$ la lunghezza della macchina e $D$ il suo diametro.
Il momento risultante dipende fisicamente dal flusso per la corrente, se moltiplico però il flusso di statore per la corrente di statore ottengo una componente reale nulla, dunque non c'è coppia tra il flusso e la corrente che la genera, per questo devo considerare il flusso di statore con la corrente di rotore o dal flusso di statore generato dalla corrente di rotore.

L'equazione della coppia si può anche scrivere nel seguente modo:
$$
m_{e} = \frac{3}{2}pL_{m} i_{s}i_{r}' \sin(\varphi_{s}-\varphi_{r}+\theta_{r})
$$
Possiamo riportare il sistema rispetto allo statore:
$$
\vec{i}_{r}^s = \vec{i}_{r}'e^{jp\theta_{r}}
$$
ottenendo:
$$
\begin{aligned}
\vec{v}_{s}^s &= R_{s}\vec{i}_{s}^s + L_{s} \frac{d}{dt} \vec{i}_{s}^s + L_{m}{\frac{d}{dt}} \vec{i}_{r}^s \\
0 &= -jp\omega_{r}L_{m}\vec{i}_{s}^s +L_{m} \frac{d}{dt} \vec{i}_{s}^s + (R_{r}'-jp\omega_{r}L_{r}')\vec{i}_{r}^s + L_{r}'\frac{d}{dt}\vec{i}_{r}^s \\
M_{e} &= \frac{3}{2} p L_{m} \mathrm{Im} \left\{ \vec{i}_{r}^s\hat{\vec{i}}_{s^s} \right\}
\end{aligned}
$$

di queste due incognite la $\vec{i}_{s}$ è misurabile ma non la $\vec{i}_{r}^r$, effettuando il cambio di variabile tra la corrente e il flusso si ottiene:
$$
0= (R_{r}' - j\omega L_{r}')\vec{i}_{r}' -j\omega_{r}L_{m} \vec{i}_{s}^s + L_{m}\frac{d}{dt}\left( L_{m}\vec{i}_{s}^s + L'_{r}\vec{i}_{r}^s \right)
$$
raggruppando i termini e sostituendo con il flusso:
$$
0 = (R_{r}'-j\omega_{r}L_{r}') \left( \frac{-L_{m}\vec{i}_{s}^s + \vec{\Phi}_{r}^s}{L_{r}'} \right) -j\omega_{r}L_{m}\vec{i}_{s}^s  + L_{m}\frac{d}{dt} \vec{\Phi}_{r}^s
$$
e quindi ponendo $\sigma_{r} = \frac{R_{r}'}{L_{r}'}$ e $k_{r} = \frac{L_{m}}{L_{r}'}$:
$$
0 = -\sigma_{r} L_{m} \vec{i}_{s}^s + (\sigma_{r}-j\omega_{r})\vec{\Phi}_{r}^s + L_{m} \frac{d}{dt}\vec{\Phi}_{r}^s
$$

Si considera adesso un sistema di riferimento solidale al vettore di flusso $\vec{\Phi}_{r}^s$, si considera un sistema di assi cartesiani $d-q$ traslati di un angolo $\Psi$ rispetto al riferimento fisso (di statore).
In questo caso il vettore $\vec{\Phi}_{r}$ sarà reale, avrà solo componente lungo $d$.
$$
\vec{\Phi}_{r} = \vec{\Phi}_{r}^s e^{-j\Psi} \quad \text{e}\quad \vec{i}_{s} = \vec{i}_{s}^s e^{-j\Psi}
$$
Si sostituisce nelle equazioni precedenti:
$$
0 = -\sigma_{r} L_{m} \vec{i}_{s}e^{j\Psi} + (\sigma_{r}-j\omega_{r}){\Phi}_{r}e^{j\Psi} + \frac{d}{dt} \Phi_{r}e^{j\Psi}
$$
sviluppando la derivata:
$$
e^{j\Psi} \frac{d}{dt}\Phi_{r} + j \frac{d\Psi}{dt} \Phi_{r}e^{j\Psi}
$$
Dunque si scompone in due equazioni, reale e immaginaria:
$$
\begin{aligned}
0 &= -\sigma_{r} L_{m} i_{sd} + \sigma_{r}\Phi_{r} + \frac{d}{dt} \Phi_{r} \\
0 &= -\sigma_{r} L_{m} i_{sq} + (\omega-\omega_{r})\Phi_{r} \\
M_{e} &= \frac{3}{2} p k_{r} i_{sq} \Phi_{r}
\end{aligned}
$$
con $\omega= \frac{d\Psi}{dt}$.
La coppia si è ottenuta sempre per sostituzione:
$$
M_{e} = -\frac{3}{2} p k_{r}\Phi_{r} \mathrm{Im}\left\{ \Phi_{r}\cancel{e^{j\Psi}} \hat{\vec{i}}_{s}\cancel{e^{-j\Psi}} \right\} = \frac{3}{2} p k_{r}\Phi_{r} \mathrm{Im}\left\{ \vec{i}_{s} \right\}
$$
In questo riferimento è possibile variare il flusso variando la corrente in asse diretto e variare la coppia con la corrente di asse in quadratura.
