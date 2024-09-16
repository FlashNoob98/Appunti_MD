Nel caso in cui si abbia un guasto dissimmetrico, molto frequente, si deve studiare cosa accade nel circuito con una dissimmetria.
Quando l'impianto non è simmetrico non si può semplificare il modello con un circuito monofase equivalente, per questo motivo si studia l'impianto alle terne di sequenza diretta, inversa e omopolare.

L'impianto può essere rappresentato mediante un sistema di tre conduttori con il neutro, siano le lettere senza apice quelle che indicano i punti di "partenza" e quelle con l'apice i punti di "arrivo", sono presenti sei tensioni differenti rispetto al neutro.

tre correnti che interessano i conduttori e la matrice delle impedenze mutue completano le equazioni del circuito, scritte in forma matriciale:
$$
\begin{bmatrix}
\vec{V_a} \\ \vec{V_b} \\ \vec{V_c}
\end{bmatrix} = 
\begin{bmatrix}
\vec{V_a'} \\ \vec{V_b'} \\ \vec{V_c'}
\end{bmatrix} +
\begin{bmatrix}
\dot{Z}_s & \dot{Z}_m & \dot{Z}_m \\
\dot{Z}_m & \dot{Z}_s & \dot{Z}_m \\
\dot{Z}_m & \dot{Z}_m & \dot{Z}_s
\end{bmatrix}
\cdot
\begin{bmatrix}
\vec{I_a} \\ \vec{I_b} \\ \vec{I_c}
\end{bmatrix}
$$
Le impedenze presentano sia caratteristiche induttive che capacitive, si considera in questo caso per esercizio solo la parte induttiva
$$
\begin{aligned}
\vec{V_1} &= \vec{I_1} j\omega L_1 + \vec{I}_2 j\omega M + \vec{I}_3 j \omega M =
 \vec{I}_1 j \omega L_1 + j \omega M (\vec{I}_2 + \vec{I}_3) =
 I_1 j \omega\frac{(L_1-M)}{L_s}
\end{aligned}
$$
In questo caso si considerano le mutue induzioni uguali per tutte le fasi, si è ricavata l'induttanza di servizio $L_s$.
La capacità di servizio è pari alla somma delle capacità più 3 volte quella verso terra.

Le terne di tensione lungo il circuito, dovute al guasto non saranno più simmetriche a causa della dissimmetria del guasto e quindi delle correnti.

La terna di fasori è diretta se le tensioni si susseguono in verso orario e ruotano in verso antiorario, la terna è inversa se le tensioni si susseguono in verso antiorario e ruotano inverso antiorario, è omopolare se non c'è sfasamento tra le tensioni.

Sia $\vec{A}$ una terna di fasori, può essere così rappresentata:
$$
\begin{aligned}
\vec{A}_a &= \vec{A_o} + \vec{A_{ad}} + \vec{A_{ai}}\\
\vec{A}_b &= \vec{A_o} + \vec{A_{bd}} + \vec{A_{bi}}\\
\vec{A}_c &= \vec{A_o} + \vec{A_{cd}} + \vec{A_{ci}}
\end{aligned}
$$
si introduce un fattore di rotazione $\alpha = e^{j2\pi/3} = -1/2 + j \sqrt{3}/2$ ed $\alpha^2 = e^{j4\pi/3} = -1/2 - j \sqrt{3}/2$,
si vuole esprimere la terna di fasori reali come la somma dei tre fasori di sequenza.
Si introduce la *matrice di sequenza*:

$$
\begin{bmatrix}
\vec{A}_a \\ \vec{A}_b \\ \vec{A}_c
\end{bmatrix} = 
\begin{bmatrix}
1&1 & 1\\
1 &\alpha^2 &\alpha \\
1 & \alpha & \alpha^2
\end{bmatrix}
\begin{bmatrix}
\vec{A}_0 \\ \vec{A}_d \\ \vec{A}_i
\end{bmatrix}
$$
che moltiplicando le terne di sequenza restituisce i fasori reali.
In realtà noi conosciamo i fasori reali e vogliamo ricavare i fasori delle sequenze, dunque l'inversa della matrice di sequenza:
$$
\begin{bmatrix}
\vec{A}_0 \\ \vec{A}_d \\ \vec{A}_i
\end{bmatrix} = 
\frac{1}{3}
\begin{bmatrix}
1&1 & 1\\
1 &\alpha &\alpha^2 \\
1 & \alpha^2 & \alpha
\end{bmatrix}
\begin{bmatrix}
\vec{A}_a \\ \vec{A}_b \\ \vec{A}_c
\end{bmatrix}
$$
.
