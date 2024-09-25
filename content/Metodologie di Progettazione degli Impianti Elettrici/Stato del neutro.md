Fondamentale per la sicurezza e la [[Progettazione degli Impianti Elettrici|progettazione degli impianti elettrici]] è lo studio dello stato del neutro.
# Materializzazione del neutro
Avviene mediante la realizzazione di tre impedenze uguali connesse alle rispettive fasi e tra loro, la terna di tensioni esercita sulle impedenze sarà pari a:
$$
\begin{bmatrix}
\vec{E_{1}} \\ \vec{E_{2}} \\ \vec{E_{3}}
\end{bmatrix} = 
\begin{bmatrix}
\dot{Z_{1}} \vec{I_{1}} \\ \dot{Z_{2}} \vec{I_{2}}  \\ \dot{Z_{3}} \vec{I_{3}} 
\end{bmatrix}
$$
Quasi tutte le macchine elettriche si prestano alla materializzazione del neutro data la loro simmetria costruttiva sono spesso modellate con tre impedenze uguali tra loro.

## Guasto monofase a terra con neutro isolato
Si sfruttano ancora i [[circuiti di sequenza]] per studiare il guasto con neutro isolato, per ricavare le grandezze del guasto si analizza il circuito trifase:
<center>

![[guasto_monofase_neutro_isolato.svg]]
</center>

Si sfrutta il [teorema di Millman](https://it.wikipedia.org/wiki/Teorema_di_Millman) tra il centro stella e la terra:
$$
\vec{V}_{o'o} = \frac{\vec{E_{1}}\dot{Y_{1}} +\vec{E_{2}}\dot{Y_{2}} +\vec{E_{3}}\dot{Y_{3}}}{\dot{Y_{1}}+\dot{Y_{2}}+\dot{Y_{3}}}
$$
con $\dot{Y}$ le ammettenze dei singoli rami, si ipotizzano uguali per le tre fasi $\dot{Y_{i}}=j \omega C_{0}$ se si effettua la trasposizione. Se non fossero uguali si avrebbe uno spostamento del centro stella, la tensione delle tre fasi rispetto al terreno sarebbe diversa, si introdurrebbe una dissimmetria della tensione lungo la linea.
A causa del guasto c'è uno spostamento "banale" del centro stella sulla fase $\vec{E_{1}}$ a causa del collegamento a terra, si trascura la capacità della fase guasta, dunque sulle altre due linee agirà la tensione concatenata $\vec{E_2}-\vec{E_1}$ e $\vec{E_3}-\vec{E_1}$ rispettivamente.
La corrente capacitiva sulla linea 2 ad esempio sarà:
$$
\vec{I_{C}}_{2} = j \vec{V_{2}} \omega C_{0} = j \sqrt{ 3 } \vec{E_{2}} \omega C_{0}
$$
Il fasore di corrente è ruotato in anticipo di 90° rispetto alla tensione.
La relazione sulle correnti è la seguente:
$$
\vec{I_{g}} + \vec{I_{C}}_{1} + \vec{I_{C}}_{2} =  0
$$
La corrente di guasto è dunque pari alla somma delle correnti capacitive.


## 25 settembre
A prescindere dal sistema in esame va sempre considerato l'accoppiamento capacitivo della linea con il terreno. Le correnti calcolate sono sempre a regime, nella realtà si vuole interrompere queste correnti quindi vengono considerate *presunte*, si assume che il sistema non raggiunga mai quei valori di correnti.
Si vogliono calcolare le correnti $\vec{I}_{C_{2}}$ e $\vec{I}_{C_{3}}$, nella condizione di normale funzionamento le tre tensioni formano una terna simmetrica diretta, la tensione del centro stella rispetto al terreno è nulla. Dunque anche le tensioni rispetto al terreno delle linee corrispondono alla terna simmetrica diretta, è semplice calcolare le correnti capacitive pari alle tensioni nominali sull'impedenza di linea e quella capacitiva.

In caso di guasto il centro stella si sposta sul punto $\vec{E}_{1}$ dunque le tensioni sulle fasi non guaste saranno le concatenate.
In alternativa per calcolare lo spostamento del centro stella si può applicare la [[Leggi di Kirchhoff#Legge di Kirchhoff per le correnti|LKC]] alle maglie sane:
$$
\vec{E}_{2} - \vec{V}_{C_{2}} = \vec{V}_{o'o} \Rightarrow \vec{V}_{C_{2}} = \vec{E}_{2} - \vec{V}_{o'o}
$$
dalla maglia di guasto si vede che $\vec{V}_{o'o} = \vec{E_{1}}$.
La corrente di guasto è in anticipo di 90° rispetto alla tensione che agiva sulla fase guasta.
Si può calcolare il modulo della corrente di guasto geometricamente, le correnti $\vec{I}_{C_{2}}$ e $\vec{I}_{C_{3}}$ sono identiche e formano un triangolo isoscele, dunque:
$$
\left|\vec{I}_{C_{2}}+\vec{I}_{C_{3}}\right| = 2\sqrt{ 3 } E \omega C_{0} \cos(30°) =  2\sqrt{ 3 } E \omega C_{0} \frac{\sqrt{ 3 }}{2} = 3E \omega C_{0}
$$
Non sarebbe così semplice usare l'interpretazione grafica nel caso in cui ci sia una impedenza di guasto diversa da zero.

## Spostamento del centro stella con Millman
Si vuole utilizzare il [teorema di Millman](https://it.wikipedia.org/wiki/Teorema_di_Millman).
Sia $R_g$ la resistenza di guasto, piccola, comunque trascurabile rispetto alla $C_0$, si può non trascurare usando Millman, si pone in parallelo nel ramo di guasto, evitando approssimazioni, la corrente di guasto sarà esclusivamente quella che circola nella $R_g$.
Si calcola lo spostamento del centro stella:
$$
\begin{aligned}
\vec{V}_{o'o} &= \frac{\vec{E}_{1} \left( \frac{1}{R_{g}} + j \omega C_{0} \right) + \vec{E}_{2} (j \omega C_{0}) + \vec{E}_{3} j\omega C_{0}}{\frac{1}{R_{g}} + 3 j \omega C_{0}} \\
&= \frac{\frac{\vec{E}_{1}}{R_{g}}}{\frac{1}{R_{g}} + 3 \omega C_{0}} = \frac{\vec{E}_{1}}{1 + 3 j \omega C_{0}R_{g}}
\end{aligned}
$$
ricordando che la somma delle tre tensioni è pari a zero dato che la terna è simmetrica.
Si calcola dunque la corrente di guasto pari alla tensione sul parallelo diviso la resistenza di guasto:
$$
\vec{I}_{g} = \frac{\vec{E}_{1}-\vec{V}_{o'o}}{R_{g}} = \frac{\vec{E}_{1}}{R_{g}} - \frac{\vec{E}_{1}}{(1+3j \omega C_{0}R_{g})R_{g}} = \frac{\vec{E}_{1}}{R_{g}}
\left[ \frac{\cancel{1} + 3 j \omega C_{0}R_{g} -\cancel{1}}{1 + 3 j \omega C_{0 }R_{g}} \right] =  \frac{3j \omega C_{0}\vec{E}_{1}}{1 + 3 j \omega C_{0}R_{g}}
$$
 coerente con la formula precedente se $R_{g}=0$.
## Applicazione delle reti di sequenza
Si riportano i tre circuiti alle terne di sequenza, forzati dalla terna simmetrica, in questo caso $\dot{Z}_g=R_g$:
<center>

![[circuiti_sequenza_cc_monofase_impedenza.svg]]
</center>

Si ricorda ancora una volta che **la corrente di guasto è solo quella che si richiude attraverso la resistenza di guasto**, non tutta la corrente che attraversa la linea guasta.
In questo caso il calcolo di $\vec{I}_g$ diventa:
$$
\vec{I}_{g} = \frac{3 \vec{E}}{\cancel{\dot{Z}_{d}+\dot{Z}_{i}}+\dot{Z}_{0} + 3R_{g}} = \frac{3\vec{E}}{3R_{g} + \frac{1}{j \omega C_{0}}} = \frac{3\vec{E}j\omega C_{0}}{3R_{g}j\omega C_{0}+1}
$$
Le impedenze induttive della rete $(jX_{d},jX_{i})$ sono trascurabili rispetto all'impedenza capacitiva dovuta all'accoppiamento verso terra e vista dalla sequenza omopolare, dunque $\dot{Z_{0}} =\frac{1}{j\omega C_{0}}$ prevale sulle altre (negli altri casi la sommatoria delle correnti è nulla e non c'è richiusura mediante gli accoppiamenti capacitivi).

## Incidenza dei parametri sul valore di corrente
Si suppone ad esempio che il corto circuito avvenga mediante un contatto accidentale, dunque la resistenza di guasto diventa la serie della resistenza del corpo e di quella di contatto con la terra, dunque $R_{g} = R_{B}+R_{EB} = 2000\Omega+1000\Omega$, in BT con neutro connesso a terra, la corrente di guasto è circa $76mA$:
$$
I_{g} = \frac{230}{3000} \simeq 76 mA
$$
In BT si può trascurare $C_0$ se la lunghezza dei cavi è piccola, ciò non è sempre vero se l'impianto si estende per alcuni metri, ad esempio in un impianto industriale.
Un cavo di $2km$ fornisce un valore di $C_0\simeq{0.8\mu F}$ e dunque una corrente di guasto,calcolata con la formula precedente, pari a $60 \sim 70 mA$ sicuramente pericolosa per il corpo umano.
Mettere a terra il neutro in BT elimina l'incertezza sulle capacità parassite, si ha più certezza di controllare la corrente di guasto.

In Alta Tensione invece la capacità $C_{0}$ aumenta, dunque la reattanza diminuisce fino a a raggiungere gli ordini di grandezza delle reattanze induttive, si può incorrere in sovratensioni dovute a fenomeni di risonanza. Collegando il neutro a terra si trascura l'impedenza capacitiva.

## Bobina di Petersen
In media tensione si vuole limitare la corrente di guasto, non ci sono grossi problemi legati alla sicurezza o alla risonanza, le linee spesso sono in cavo e vengono considerate "lunghe" già a partire da $1km$.
Si pone una bobina $L$ in cabina attraversata da una certa corrente, in caso di guasto franco, $\vec{I}_L=\frac{\vec{E}_{1}}{j \omega L}$ tale che ([[Leggi di Kirchhoff#Legge di Kirchhoff per le correnti|LKC]])
$$
\vec{I}_{L} + \vec{I}_{C_{2}} + \vec{I}_{C_{3}}+  \vec{I}_{g} = 0
$$
Va dimensionata la bobina $L$ affinché si annulli la corrente di guasto, ricordando il grafico precedente sarà pari alla $I_g$:
$$
\vec{I}_{L} = -\left( \vec{I}_{C_{2}}-\vec{I}_{C_{3}} \right) \Rightarrow I_{L} = 3E\omega C_{0}
$$
quindi la $L$:
$$
I_{L} = \frac{E}{\omega L} \Rightarrow L = \frac{1}{3 \omega^2 C_{0}}
$$
Si crea un fenomeno di risonanza parallelo, le tre correnti che nel circuito omopolare attraversano le capacità, si richiudono tutte nell'unica induttanza $L$, per questo motivo il fattore 3.
Non si ha mai un accoppiamento perfetto a causa dell'incertezza della $C_0$ e della resistenza di guasto, esistono dunque le normative che forniscono il valore ideale della $L$ in funzione della massima corrente di guasto in media tensione.
