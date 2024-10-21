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


