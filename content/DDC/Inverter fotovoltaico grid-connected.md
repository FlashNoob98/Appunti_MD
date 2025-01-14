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
