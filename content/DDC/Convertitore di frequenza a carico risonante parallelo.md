Composto da un ponte trifase connesso alla rete, in serie un filtro RL alimenta un ponte monofase total-controllato, connesso ad un carico RL con capacità C in parallelo.

Si ipotizza, per semplificare le analisi di considerare solo il valor medio della corrente di filtro $I_f$ e la media di ordine 1 per il valore di tensione sul carico $v_c$. 
Essendo presenti tre componenti dinamici, saranno necessarie almeno tre equazioni differenziali per rappresentare la dinamica del sistema.

Si riporta la pulsazione di risonanza del carico $\omega_{r}$:
$$
\omega_{r} = \sqrt{ \frac{L-R^2C}{L^2C} }
$$
è solitamente molto maggiore della pulsazione $\omega$ dell'alimentazione, dunque si può trascurare il fenomeno di risonanza almeno per le prime armoniche.

Sono presenti 4 componenti controllati, ma non si vuole mettere in corto circuito l'alimentazione dunque dovranno condurre comunque al massimo due alla volta, l'impulso di entrata in conduzione viene inviato ad una gamba e si invia sempre il suo negato all'altro componente sulla stessa gamba, il grado di libertà è sceso a 2.

Inoltre nell'ipotesi di CCM sarà sempre presente almeno una coppia di dispositivi in conduzione, esistono allora solo due configurazioni possibili del sistema.
La dimensione dello spazio di controllo si ricava con la solita formula
$$
2^m\geq N \rightarrow m=1
$$
nell'ipotesi di commutazione istantanea.

Si suppone la conduzione della coppia di tiristori $T_1$ e $T_{1}'$ ovvero quelli che forniscono una tensione positiva al carico, si riporta la configurazione in forma matriciale:
$$
\frac{d}{dt} \begin{bmatrix}
i_{f} \\ v_{C} \\ i_{0}
\end{bmatrix}=
\begin{bmatrix}
-\frac{R_{f}}{L_{f}} & -\frac{1}{L_{f}} & 0  \\
\frac{1}{C} & 0 & -\frac{1}{C} \\
0 & \frac{1}{L} & -\frac{R}{L}
\end{bmatrix}\cdot
\begin{bmatrix}
i_{f} \\ v_{C} \\ i_{0}
\end{bmatrix} + 
\begin{bmatrix}
\frac{1}{L_{f}} \\ 0 \\ 0
\end{bmatrix}V_{d}
$$
In questo caso il raddrizzatore a monte è visto come un generatore di tensione costante $V_d$.
La prima equazione si ricava applicando la [[Leggi di Kirchhoff#Legge di Kirchhoff per le tensioni|LKT]] alla maglia centrale:
$$
\frac{di_{f}}{dt} = \frac{V_{d}-R_{f}i_{f}-v_{C}}{L_{f}}
$$
la seconda ancora con Kirchhoff:
$$
\frac{dv_{C}}{dt} = \frac{i_{f}-i_{0}}{C}
$$
mentre la terza studiando la maglia del carico:
$$
\frac{di_{0}}{dt} = \frac{v_{C}-Ri_{0}}{L}
$$

Per la seconda configurazione si inverte la tensione sul carico, conduce l'altra coppia di tiristori:
$$
\frac{d}{dt} \begin{bmatrix}
i_{f} \\ v_{C} \\ i_{0}
\end{bmatrix}=
\begin{bmatrix}
-\frac{R_{f}}{L_{f}} & \frac{1}{L_{f}} & 0  \\
-\frac{1}{C} & 0 & -\frac{1}{C} \\
0 & \frac{1}{L} & -\frac{R}{L}
\end{bmatrix}\cdot
\begin{bmatrix}
i_{f} \\ v_{C} \\ i_{0}
\end{bmatrix} + 
\begin{bmatrix}
\frac{1}{L_{f}} \\ 0 \\ 0
\end{bmatrix}V_{d}
$$
I componenti da controllare nel sistema sono 4, dunque vi saranno quattro segnali di controllo ma vanno sempre rispettate le seguenti condizioni:
$$
\begin{aligned}
\text{Impedire CC sulla linea:}& \\
u_1 + u_2 = 1& \\ u_1' + u_2' = 1& \\ 
\text{Garantire maglia di conduzione:}& \\
u_1 = u_1'& \\ u_2 = u_2'&
\end{aligned}
$$
Dunque lo spazio di controllo è l'insieme dei segnali di controllo linearmente indipendenti,
è un sottoinsieme dell'insieme di controllo, ovvero una sua base, è la famiglia libera massimale.
L'insieme di controllo è invece l'insieme dei segnali che verranno inviati ai componenti, pari al numero dei componenti da controllare.
Se si usassero tutti e quattro i segnali si avrebbe la relazione tra la tensione in ingresso e in uscita:
$$
v = \frac{v_c}{2}\left[u_1+u_1'-u_2-u_2'\right] = v_{c}(2u_{1}-1)
$$
I vincoli tra le variabili sarebbero inclusi nel modello differenziale ottenendo un sistema di 7 equazioni, considerando solo il "comando libero" si semplifica il calcolo del modello dinamico alle configurazioni.
# Modello ai valori istantanei
Si rappresenta il modello ai valori istantanei:
$$
\left\{
\begin{aligned}
\frac{di_{F}}{dt} &= \frac{v_{d}-R_{F}i_{F}-v_{C}(2u_{1}-1)}{L_{F}} \\
\frac{dv_{C}}{dt} &= \frac{(2u_{1}-1)i_{F}-i_{0}}{C}\\
\frac{di_{0}}{dt} &= \frac{v_{C}}{L} - \frac{R}{L}i_{0}
\end{aligned}
\right.
$$
# Modello GAM
Analogamente a quanto fatto per il [[Boost converter#Modello GAM|boost converter]] si può ricavare il modello GAM, nell'ipotesi in cui si trascurino le armoniche di corrente $i_{F}$ nel filtro e tensione e corrente sul carico abbiano solo la prima componente.
$$
\left\{
\begin{aligned}
\frac{d}{dt} \langle i_{F} \rangle_{0} &= \frac{\langle v_{d} \rangle_{0} }{L_{F}} - \frac{R_{F}}{L_{F}} \langle i_{F} \rangle_{0} -  \frac{\langle v_{C}u_{1} \rangle_{0} }{L_{F}} \\
\frac{d}{dt} \langle v_{C} \rangle_{1} &= -j\omega \langle v_{C} \rangle_{1} + \frac{\langle i_{F}u_{1} \rangle_{1} }{C} - \frac{\langle i_{0} \rangle_{1} }{C} \\
\frac{d}{dt}\langle i_{0} \rangle_{1} &= -j\omega \langle i_{0} \rangle_{1} + \frac{\langle v_{C} \rangle_{1} }{L} -\frac{R}{L}\langle i_{0} \rangle_{1}  
\end{aligned}
\right.
$$

Si indicano le variabili di stato:
$$
\begin{aligned}
\langle i_{F} \rangle_{0} &= x_{1}\\
\langle v_{C} \rangle_{1} &= x_{2} + jx_{3} \\
\langle i_{0} \rangle_{1} &= x_{4} +jx_{5} 
\end{aligned}
$$
La tensione e la corrente sul carico sono sinusoidali, dunque si è assunto che il loro valore medio sia nullo.
Il segnale di controllo $u$ è un'onda quadra simmetrica, che assume valori $[-1,1]$ e cambia segno, per semplicità, a $\frac{T}{2}$, dunque ne si calcola il contenuto armonico.
$$
\begin{aligned}
\langle u \rangle_{k} &= \frac{1}{T} \int_{0}^T u(\tau) e^{-j\omega k\tau}d\tau = \frac{1}{T}\int_{0}^{T/2} u(\tau) e^{-j\omega k\tau}d\tau - \frac{1}{T} \int_{\frac{T}{2}}^T u(\tau) e^{-j\omega k\tau}d\tau = \\
&=\frac{1}{T}\cdot \frac{1}{-j\omega k} \left\{ \left[e^{-j\omega k\tau}\right]_{0}^{T/2} - \left[e^{-j\omega k\tau}\right]_{T/2}^{T} \right\} = \frac{j}{2\pi k}\left[ e^{-jk\pi} -1 -e^{-j2k\pi} + e^{-jk\pi} \right] = \\
&= \frac{\cancel{2}j}{\cancel{2}\pi k} \left[e^{-jk\pi}-1\right]
\end{aligned}
$$
In conclusione per $k$ pari la media è nulla, per $k$ dispari vale:
$$
\langle u \rangle_{k} = -\frac{2j}{k\pi} 
$$
Si calcolano i prodotti:
$$
\langle v_{C}u \rangle_{0} = \langle v_{C} \rangle_{1}\langle u \rangle_{-1} + \langle v_{C} \rangle_{-1}\langle u \rangle_{1} = -\frac{4}{\pi}x_{3}
$$
e ancora:
$$
\langle i_{F}u \rangle_{1} = \langle i_{F} \rangle_{0}\langle u \rangle_{1} = -\frac{2j}{\pi}x_{1}   
$$
mentre il valor medio di tensione in uscita dal ponte a diodi è:
$$
\langle v_{d} \rangle_{0} = \frac{3\sqrt{ 2 }}{\pi}V_{\Delta}
$$
Si può dunque rappresentare il modello GAM nelle variabili di stato generalizzate:
$$
\left\{
\begin{aligned}
\frac{dx_{1}}{dt} &= \frac{3}{\pi}\frac{\sqrt{ 2 }V_{\Delta}}{L_{F}} - \frac{R_{F}}{L_{F}}x_{1} + \frac{4}{\pi L_{F}}x_{3}\\
\frac{dx_{2}}{dt} &= \omega x_{3}-\frac{x_{4}}{C} \\
\frac{dx_{3}}{dt} &= -\omega x_{2} -\frac{2}{\pi} \frac{x_{1}}{C} -\frac{x_{5}}{C} \\
\frac{dx_{4}}{dt} &= \omega x_{5} +\frac{1}{L}x_{2} -\frac{R}{L}x_{4} \\
\frac{dx_{5}}{dt} &= -\omega x_{4} +\frac{1}{L}x_{3} - \frac{R}{L}x_{5}
\end{aligned}
\right.
$$

# Modello ROAM
Si può considerare la dinamica della corrente nel filtro più lenta rispetto a quella delle grandezze di stato del convertitore a valle, per questo motivo si può studiare il sistema mediante il [[modello ROAM]] analizzando la dinamica della seconda e terza equazione:
$$
\begin{aligned}
j\omega \vec{V}_{C} &= -\frac{2}{\pi}j \frac{\langle i_{F} \rangle_{0} }{C} - \frac{\vec{I}_{0}}{C} \\
j\omega \vec{I}_{0} &= \frac{\vec{V}_{C}}{L} - \frac{R}{L}\vec{I}_{0} \Rightarrow (R+j\omega L)\vec{I}_{0} =\vec{V}_{C}
\end{aligned}
$$
sostituendo la $\vec{I}_{0}$ nella prima:
$$
\begin{aligned}
j\omega C\vec{V}_{C} &= -\frac{2}{\pi} jx_{1} - \frac{\vec{V}_{C}}{R+j\omega L} \\
\left( j\omega C +\frac{1}{R+j\omega L} \right)\vec{V}_{C} &= -\frac{2}{\pi}jx_{1} \\
\left[ \frac{j\omega RC - \omega^2LC +1}{R+J\omega L} \right]\vec{V}_{C} &= -\frac{2}{\pi}jx_{1} \\
\vec{V}_{C} &= -\frac{2}{\pi}jx_{1} \cdot \frac{R+j\omega L}{1 -\omega^2LC+j\omega RC} \\
\vec{V}_{C} &= -2jx_{1}\cdot \frac{(R+j\omega L)\left[(1-\omega^2LC)-j\omega RC\right]}{\left[ (1-\omega^2LC)^2 + (\omega RC)^2\right]} \\
\vec{V}_{C}&= x_{2}+jx_{3}
\end{aligned}
$$
Va sostituita nella dinamica della prima equazione la media di ordine zero del prodotto $V_{C}u$:
$$
\langle v_{C}u \rangle_{0} = -\frac{4}{\pi}x_{3} = -\frac{4}{\pi} \mathrm{Im}\{{\vec{V}_{C}}\}
$$
dunque $x_3$:
$$
x_{3} = -\frac{2}{\pi} x_{1} \frac{(R - \cancel{R\omega^2LC} + \cancel{R\omega^2LC})}{(1-\omega^2LC)^2+(\omega RC)^2} = x_{1}R(\omega)
$$
sostituendo nella prima equazione:
$$
\frac{d}{dt}x_{1} = \frac{3}{\pi}\frac{\sqrt{ 2 }V_{\Delta}}{L_{F}} - \frac{R_{F}}{L_{F}}x_{1} + \frac{4}{\pi L_{F}}x_{1}R(\omega)
$$
Raccogliendo i termini si ottiene un'equazione differenziale del primo ordine:
$$
L \frac{di}{dt} = V - Ri
$$
dove 
$$
R = \frac{R_{F}}{L_{F}} -\frac{4}{\pi L_{F}}R(\omega)
$$
Si ricavano le altre variabili:
$$
\begin{aligned}
V_{C} &= \langle V_{C} \rangle_{-1} e^{-j\omega t} + \langle V_{C} \rangle_{1} e^{j\omega t}   \\
i_{0} &= \langle i_{0} \rangle_{-1} e^{-j\omega t} + \langle i_{0} \rangle_{1} e^{j\omega t}  \\
\langle i_{F} \rangle_{0} &= x_{1}  
\end{aligned}
$$
Non si ricava dunque il valore istantaneo nel tempo con precisione ma si ritiene che coincidano con la prima armonica (nel caso delle grandezze sul carico) o il valore medio per la corrente di filtro.
