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
.