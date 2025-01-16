Un array fotovoltaico può essere schematizzato mediante un generatore di corrente variabile ed una resistenza interna in parallelo e un condensatore di livellamento.

Il convertitore è composto da sei componenti total-controllati che alimentano una rete trifase, teoricamente sono switch completamente controllati
dunque dovremmo avere $2^m>=N$, con 6 componenti
sarebbero 64 commutazioni differenti, libere.
Nel funzionamento da inverter, a 180° ogni switch conduce per un semi-periodo, i semi-periodi
di conduzione di ogni gamba non possono sovrapporsi, metterebbero in corto l'array fotovoltaico
dunque si iniziano ad imporre i vincoli:
$$
S_{k}+S'_{k}=1 \qquad k=1,2,3
$$
I gradi di libertà scendono a 3, o si scelgono i tre componenti superiori o i 3 inferiori; per comodità si sceglie di considerare gli interruttori superiori, con gli altri 3 componenti vincolati, si ottengono dunque 8 configurazioni possibili $N=8$, dunque lo spazio di controllo del convertitore $m$ è $3$.

Si deve avere un vettore di controllo di dimensione 3, ovvero da 3 componenti $u_{1}, u_{2} , u_{3}$,
ciascuno di questi componenti apparterrà all'insieme discreto $[0,1]$, lo spazio di controllo
è dunque $\{0,1\}^3$ incluso in $\mathbb{R}^3$.

Considerati anche i componenti dinamici, lo spazio di stato è $\mathbb{R}^4:\{i_{1},i_{2},i_{3},v_{C}\}\subset \mathbb{R}^4$.
Le tensioni di rete:
$$
V_{gk} = \sqrt{ 2 }V_{Y}\cos\left( \omega t-\frac{2\pi}{3}(k-1) \right)\quad k=1,2,3
$$
Si applica il secondo principio di Kirchhoff a ciascuna maglia durante la conduzione:
$$
\begin{aligned}
&V_{10} - Ri_{1} - L\frac{di_{1}}{dt} - V_{g{1}} - V_{NO} = 0 \\
&V_{20} - Ri_{2} - L\frac{di_{2}}{dt} - V_{g{2}} - V_{NO} = 0 \\
&V_{30} - Ri_{3} - L\frac{di_{3}}{dt} - V_{g{3}} - V_{NO} = 0
\end{aligned}
$$
considerando la rete simmetrica e le tre correnti equilibrate, si può effettuare la somma:
$$
\sum_{k=1}^3 V_{k0} = 3V_{N0}
$$
con $V_{k0}= [V_{C}\text{ se }u_{k}=1;{0}\text{ se }u_{k}=0]$, in altre parole $V_{k0}=V_{C}\cdot u_{k}$ dove $u_{k}$ indica lo stato dello switch superiore.
Si può allora riscrivere la sommatoria:
$$
3V_{N0} = V_{C}(u_{1}+u_{2}+u_{3})
$$

Raccogliendo le derivate delle correnti si esplicita il modello dinamico:
$$
\begin{aligned}
\frac{d}{dt}i_{1} &= \frac{V_{C}}{L}u_{1} - \frac{Ri_{1}}{L} -\frac{V_{g1}}{L} - \frac{V_{C}}{3L}(u_{1}+u_{2}+u_{3})\\
\frac{d}{dt}i_{2} &= \frac{V_{C}}{L}u_{2} - \frac{Ri_{2}}{L} -\frac{V_{g_{2}}}{L} - \frac{V_{C}}{3L}(u_{1}+u_{2}+u_{3})\\
\frac{d}{dt}i_{3} &= \frac{V_{C}}{L}u_{3} - \frac{Ri_{3}}{L} -\frac{V_{g_{3}}}{L} - \frac{V_{C}}{3L}(u_{1}+u_{2}+u_{3})\\
\frac{d}{dt}v_{C} &= \frac{i_{s}}{C}-\frac{v_{C}}{R_{f}C}-  \frac{i_{1}u_{1}+i_{2}u_{2}+i_{3}u_{3}}{C}
\end{aligned}
$$
Dal modello ai valori istantanei si ricava facilmente la forma affine nel controllo:
$$
\frac{d}{dt}\vec{x}=
\begin{bmatrix}
-\frac{R}{L}x_{1}-\frac{v_{g1}}{L}\\ -\frac{R}{L}x_{2}-\frac{v_{g2}}{L}\\ -\frac{R}{L}x_{3}-\frac{v_{g3}}{L}  \\
\frac{i_{S}}{C} - \frac{x_{4}}{R_{F}C}
\end{bmatrix} + 
\begin{bmatrix}
\frac{2}{3} \frac{x_{4}}{L} & -\frac{x_{4}}{3L} & -\frac{x_{4}}{3L}  \\
-\frac{x_{4}}{3L} & \frac{2}{3} \frac{x_{4}}{L} & -\frac{x_{4}}{3L} \\
-\frac{x_{4}}{3L} & -\frac{x_{4}}{3L} & \frac{2}{3}\frac{x_{4}}{3L} \\
-\frac{x_{1}}{C} & -\frac{x_{2}}{C} & -\frac{X_{3}}{C}
\end{bmatrix} \cdot
\begin{bmatrix}
u_{1} \\ u_{2} \\ u_{3}
\end{bmatrix}
$$
In [[forma bilineare]]:
$$
\begin{aligned}
\frac{d}{dt}\vec{x} &= 
\begin{bmatrix}
-\frac{R}{L} & 0 & 0 & 0 \\
0 & -\frac{R}{L}  & 0 & 0  \\ 
0 & 0 & -\frac{R}{L}  & 0 \\ 
0 & 0 & 0 & -\frac{1}{R_{F}C} 
\end{bmatrix}\vec{x} + 
\begin{bmatrix}
-\frac{v_{g1}}{L} \\
-\frac{v_{g2}}{L} \\
-\frac{v_{g3}}{L} \\
\frac{i_{5}}{C}
\end{bmatrix} \\
B_{1} &= \begin{bmatrix}
0 & 0 & 0 & \frac{2}{3} \frac{1}{L}\\ 
0 & 0 &0 &-\frac{1}{3} \frac{1}{L} \\
0 & 0 & 0 & -\frac{1}{3} \frac{1}{L} \\
-\frac{1}{C} & 0 & 0 & 0 
\end{bmatrix}; b_{1} = 0\quad B_{2} = 
\begin{bmatrix}
0 & 0 & 0 & -\frac{1}{3} \frac{1}{L}\\ 
0 & 0 &0 & \frac{2}{3} \frac{1}{L} \\
0 & 0 & 0 & -\frac{1}{3} \frac{1}{L} \\
0 & -\frac{1}{C} & 0 & 0 
\end{bmatrix}; b_{2}=0\\
B_{3} &= \begin{bmatrix}
0 & 0 & 0 & -\frac{1}{3} \frac{1}{L}\\ 
0 & 0 &0 & -\frac{1}{3} \frac{1}{L} \\
0 & 0 & 0 & \frac{2}{3} \frac{1}{L} \\
0 & 0 &-\frac{1}{C}  & 0 
\end{bmatrix}; b_{3}=0
\end{aligned}
$$

Nello spazio euclideo e di Clarke i segnali di controllo sono discreti, nello spazio di Park invece saranno continui e sinusoidali.
Viceversa le grandezze sinusoidali in $\mathbb{R}^3$ sono costanti nello spazio di Park.

Si semplifica il modello, eliminando la dinamica del condensatore, eliminando la tensione di rete, si supponga ad esempio una batteria, a tensione costante, connessa  mediante l'inverter ad un carico passivo $RL$ trifase.

Il modello si semplifica e diventa: 
$$
\begin{aligned}
\frac{d}{dt}i_{1}&= \frac{V_{s}}{L}u_{1} - \frac{R}{L}i_{1} - \frac{V_{s}}{3L}(u_{1}+u_{2}+u_{3}) \\
\frac{d}{dt}i_{2}&= \frac{V_{s}}{L}u_{2} - \frac{R}{L}i_{2} - \frac{V_{s}}{3L}(u_{1}+u_{2}+u_{3}) \\
\frac{d}{dt}i_{3}&= \frac{V_{s}}{L}u_{3} - \frac{R}{L}i_{3} - \frac{V_{s}}{3L}(u_{1}+u_{2}+u_{3})
\end{aligned}
$$
dunque usando come riferimento il punto tra i due condensatori:
$$
v_{1O'} -Ri_{1} -L \frac{d}{dt}i_{1} - V_{NO'} = 0
$$
sommando:
$$
\sum_{k=1}^{3}V_{kO'} = 3V_{NO'} = \frac{1}{3} \frac{V_{s}}{2} \sum_{k=1}^{3} (2u_{k}-1) = \frac{1}{3}V_{s} \left(\sum_{k=1}^{3}u_{k} -3\right) = \frac{1}{3}V_{s} \sum_{k=1}^{3}u_{k} - \frac{V_{s}}{2}
$$
dunque la dinamica di corrente:
$$
\frac{d}{dt}i_{1} = \frac{V_{s}}{\cancel{2}L}(\cancel{2}u_{1}-\cancel{1}) - \frac{R}{L}i_{1} - \frac{1}{3} \frac{V_{s}}{L} \sum_{k=1}^{3}u_{k} + \cancel{\frac{V_{s}}{2L}}
$$
Si ottiene la stessa dinamica a prescindere dal valore di riferimento, potrebbe però cambiare la strategia di controllo e si potrebbe preferire uno dei due riferimenti presentati.

Lo stesso modello vuole essere riscritto nello spazio di Clarke, dunque è necessario ricavare il componente simmetrico di corrente:
$$
\vec{i} = \frac{2}{3} \left(i_{1}+i_{2}e^{j{2}\pi/3} + i_{3}e^{j{4}\pi/3}\right)
$$
e quello di $V_{s}$ con il quale si ricava il modello completo:
$$
\vec{i} = \left(\frac{2}{3}i_{1}+\frac{2}{3}i_{2}e^{j{2}\pi/3}+\frac{2}{3}i_{3}e^{j4\pi/3}\right) 
$$
$$
\left\{
\begin{aligned}
\frac{d}{dt}\vec{i} &= \frac{V_{C}}{L}\left(\frac{2}{3}u_{1}+\frac{2}{3}u_{2}e^{j{2}\pi/3}+\frac{2}{3}u_{3}e^{j4\pi/3}\right) -\frac{R}{L}\vec{i} - \frac{1}{L}\vec{v}_{g} \\
\frac{d}{dt}V_{C} &= \frac{i_{S}}{C} - \frac{v_{C}}{R_{F}C} - \frac{1}{C} \frac{3}{2} (u_{\alpha}i_{\alpha} + u_{\beta}i_{\beta})
\end{aligned}\right. 
$$
Nel riferimento di Park:
$$
v_{d,q} = v_{\alpha,\beta}e^{-j\omega t}
$$
dunque
$$
e^{-j\omega t}\frac{d}{dt} \vec{i}_{\alpha,\beta} = \left[ \frac{v_{C}}{L} \vec{u}_{\alpha,\beta} - \frac{R}{L}\vec{i}_{\alpha,\beta} - \frac{v_{g\alpha,\beta}}{L} \right]e^{-j\omega t} = \frac{v_{C}}{L}\vec{u}_{d,q} - \frac{R}{L}\vec{i}_{d,q} - \frac{v_{g,d,q}}{L}
$$
si ricorda che 
$$
\frac{d}{dt}\left( \vec{i}_{\alpha,\beta}e^{-j\omega t} \right) = \frac{d}{dt} \vec{i}_{d,q}
$$
dunque il modello diventa:
$$
\left\{
\begin{aligned}
\frac{d}{dt} i_{dq} &= \frac{V_{c}}{L}\vec{v}_{dq} - \frac{R}{L} \vec{i}_{dq} -\frac{\vec{v}_{g,dq}}{L} - j\omega \cdot i_{dq} \\
\frac{d}{dt} V_{C} &= \frac{i_{S}}{C} -\frac{V_{C}}{R_{F}C} - \frac{3}{2} \frac{1}{C}\left(u_{d}i_{d}+u_{q}i_{q}\right)
\end{aligned}
\right.
$$
si possono separare le equazioni in parte reale e immaginaria:
$$
\left\{
\begin{aligned}
\frac{d}{dt}i_{d} &= \frac{v_{C}}{L}u_{d}-\frac{R}{L}i_{d} - \frac{v_{g,d}}{L} + \omega i_{q} \\
\frac{d}{dt}i_{q} &= \frac{v_{C}}{L}u_{q}-\frac{R}{L}i_{q} - \frac{v_{g,q}}{L} - \omega i_{d} \\
\frac{d}{dt}V_{C} &= \frac{i_{S}}{C} - \frac{v_{C}}{R_{F}C} - \frac{3}{2C}(i_{d}u_{d}+u_{q}i_{q})
\end{aligned}
\right.
$$
Id ed Iq saranno costanti a regime, mentre le $u_{d}$ e $u_q$ saranno sinusoidali.
Saranno più semplici da controllare le grandezze di stato, saranno costanti e non sinusoidali.

Vantaggi del riferimento di Park: volendo formulare un  controllo delle grandezze di stato, queste saranno costanti a regime, il secondo vantaggio è che è possibile ricavare  facilmente il [[modello averaged]], posso ricavare le relazioni a regime periodico.

Se considero il sistema di alimentazione facendo coincidere $V_{g,dq}$ sull'asse $d$, allora la componente $V_{gq}$ sarà nulla.

Inoltre calcolando la potenza:
$$
P(t) = V_{g{1}}i_{1} + V_{g2}i_{2} + V_{g3}i_{3} = \frac{3}{2}(V_{gd}i_{d}+\cancel{V_{gq}}i_{q})
$$
controllando singolarmente le due correnti $i_{d}$ e $i_{q}$ se il sistema è simmetrico è possibile controllare in maniera indipendente la potenza attiva e quella reattiva.
$$
\left|\left|\vec{q}\right|\right| = - v_{d}i_{q}
$$

## Controllo dell'inverter fotovoltaico
Il convertitore connesso al campo fotovoltaico deve agganciarsi alla rete a 50Hz, 400V trifase, che viene modellata con delle induttanze e delle resistenze serie che rappresentano la linea di collegamento.

Si vuole eseguire un controllo di stato, in particolare saranno presenti due anelli di controllo, il primo più interno in corrente che pilota il regolatore connesso all'inverter.
A monte è posto un ulteriore controllore che impone la corrente desiderata al controllore più interno, eseguendo a monte un controllo sulla tensione in uscita rispetto a quella di riferimento fornita dall'algoritmo di MPPT, ovvero *maximum power point tracking* ovvero l'inseguimento del punto di potenza massima, i pannelli fotovoltaici infatti presentano caratteristiche di potenza/tensione variabili al variare dell'irradianza, per questo motivo per massimizzare la potenza prodotta è necessario variare la tensione fornita ai pannelli.

Per massimizzare la potenza immessa in rete invece si scompone la corrente in uscita dall'inverter connesso in rete nel riferimento di Park e si impone la corrente di asse in quadratura pari a zero per ottenere la massima potenza trasferita alla rete, inoltre in tale condizione $\delta v_{c}^* = \delta v_{c}$. 

Dal dominio di Park si vuole ricavare il modello tangente, si applica una variazione al punto di equilibrio nella prima equazione del modello:
$$
L\frac{d}{dt} (I_{d}+\delta i_{d}) = \left(V_{c}+\delta v_{c}\right)(D_{d}+\delta d_{d}) - 
R(I_{d}+\delta i_{d}) - V_{g,d}+ \omega L(I_{q}+\delta i_{q})
$$
Si trascurano le oscillazioni della rete e si annullano i termini costanti, il sistema a regime avrà la derivata dei valori medi pari a zero.
Il modello del sistema applicando gli stessi ragionamenti alle altre due equazioni del sistema diventa:
$$
\begin{aligned}
L \frac{d}{dt} (\delta i_{d}) &= V_{c}\delta d_{d} + D_{d} \delta v_{c} - R\delta i_{d} + \omega L\delta i_{q}\\
L \frac{d}{dt} (\delta i_{q}) &= V_{c}\delta d_{q} + D_{d}\delta v_{c} - R\delta i_{q} + \omega L\delta i_{d} \\
C \frac{d}{dt}(\delta v_{c}) &=  \delta i_{s} - R_{s}\delta v_{c} - \frac{3}{2} (I_{d}\delta d_{d} + D_{d}\delta i_{d}+I_{q}\delta d_{q}+D_{q}\delta i_{q})
\end{aligned}
$$
Per quanto esposto in precedenza, in caso di controllo in cascata si possono separare le due dinamiche e in questo caso il controllo in corrente non vede le variazioni della tensione $v_{C}$ che si può assumere costante nel modello della corrente.

### Controllo della corrente di asse diretto
Preso un sistema retroazionato si vuole ricavare la funzione di trasferimento, a partire dalla relazione ingresso-uscita:
$$
y = (r-y)(R_{c}F_{d}) \Rightarrow \frac{y}{r} = \frac{R_{c}F_{d}}{1 + R_{c}F_{d}}
$$
Nel casso di un regolatore proporzionale-integrale (PI) la relazione ingresso uscita diventa:
$$
y = K_{p}x + \frac{K_{i}}{s}x = \left( K_{p}+ \frac{K_{i}}{s} \right)x
$$
e dunque la f.d.t.:
$$
\frac{y}{x} = K_{p}\left( 1+ \frac{K_{i}}{K_{p}s} \right) = K_{p}\left( 1 +\frac{1}{T_{1}s} \right) = K_{p}\left( \frac{T_{1}s+1}{T_{1}s} \right)
$$
con $T_{1}=\frac{K_{p}}{K_{i}}$.

La f.d.t. del sistema è del tipo:
$$
F = \frac{K_{c}}{T_{c}s +1}
$$
Dunque il sistema con regolatore, a ciclo chiuso diventa:
$$
\begin{aligned}
\frac{y}{r} &= \frac{K_{p}K_{c} \frac{1+sT_{1}}{T_{1}s}\cdot \frac{1}{T_{c}s+1}}{1 + \frac{T_{1}s+1}{T_{1}T_{c}s^2 + T_{1}s}K_{p}K_{c}} = \frac{K_{p}K_{c}(T_{1}s+1)}{T_{1}T_{c}s^2+T_{1}s+ K_{p}K_{c}T_{1}s+K_{p}K_{c}} =\\
&= \frac{T_{1}s+1}{\frac{T_{1}T_{c}s^2}{K_{p}K_{c}}+T_{1}\left( 1+\frac{1}{K_{p}K_{c}} \right)s+1}
\end{aligned}
$$
Si effettuano le seguenti posizioni:
$$
\frac{K_{p}K_{c}}{T_{1}T_{c}} = \omega_{0}^2 \qquad
T_{1}\left( \frac{K_{p}K_{c}+1}{K_{p}K_{c}} \right) = \frac{2\xi}{\omega_{0}}
$$
e per risolvere le incognite si assumono dei valori convenzionali di smorzamento e pulsazione di risonanza:
$$
\xi=0.7\qquad \omega_{0} = 5\omega_{c} = 5 \frac{2\pi}{T_{c}}
$$
Si mettono in relazione i due termini:
$$
\begin{aligned}
\frac{2\xi}{\omega_{0}}&= T_{1}+ \frac{T_{1}}{K_{p}K_{c}} \\
\frac{K_{p}K_{c}}{T_{i}} &= \omega_{0}^2 T_{c}\\
\frac{2\xi}{\omega_{0}} &= T_{1} + \frac{1}{\omega_{0}^2T_{c}}
\end{aligned}
$$
dunque
$$
\begin{aligned}
\frac{T_{1}T_{c}\omega_{0}^2+1}{T_{c}\omega_{0}^2} &= \frac{2\xi}{\omega_{0}} & T_{1}&= \frac{2\xi T_{c}\omega-1}{T_{c}\omega_{0}^2} \\
K_{p} &= \frac{\omega_{0}^2T_{1}T_{c}}{K_{c}} &
\end{aligned}
$$

### Dimensionamento del regolatore di tensione
Per il regolatore di tensione, più esterno, si considera la seguente equazione nel caso in cui si sia posta $I_{q}=0$:
$$
\left( Cs + \frac{1}{Rs} \right)\delta v_{c} = -\frac{3}{2}I_{d}\delta d_{d}
$$
sviluppando:
$$
\begin{aligned}
\frac{R_{s}C_{s}+1}{R_{s}}\delta v_{c} &= -\frac{3}{2} I_{d}\delta d_{d}\\
\frac{\delta v_{c}}{\delta d_{d}} &= -\frac{3}{2} \frac{I_{d}\delta d_{d} R_{s}}{R_{s}C_{s}+1} = \frac{-\frac{3}{2}I_{d}R_{s}}{RsCs+1} = \frac{K_{v}}{1+sT_{v}}
\end{aligned}
$$
Il regolatore di tensione si sintetizza:
$$
R_{v} = K_{2}\left( \frac{T_{2}s+1}{T_{2}s} \right)
$$
e
$$
H_{v} = \frac{T_{2}s+1}{\frac{T_{2}T_{v}}{K_{2}K_{v}}s^2 + T_{2}\left( 1+\frac{1}{K_{v}K_{2}} \right)s+1}
$$
Per ricavare i parametri si pone
$$
\frac{K_{2}K_{v}}{T_{2}T_{v}} = \omega_{0v}^2 \qquad T_{2}\left( 1 + \frac{1}{K_{v}K_{2}} \right)= \frac{2\xi_{v}}{\omega_{0v}}
$$
ponendo sempre $\xi_{v}=0.7$ e $T_{2}<T_{v}$.

Il valore di riferimento di tensione viene fornito dall'algoritmo di MPPT, mediante un algoritmo come il *Perturbe & Observe* che valuta la variazione di potenza al variare della tensione, inseguendo gli incrementi di potenza, fin quando non si raggiunge la potenza massima.
