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