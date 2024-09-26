In media tensione si vuole limitare la corrente di guasto, non ci sono grossi problemi legati alla sicurezza o alla risonanza, le linee spesso sono in cavo e vengono considerate "lunghe" già a partire da $1km$.
Si pone una bobina $L$ in cabina attraversata da una certa corrente, in caso di guasto franco, $\vec{I}_L=\frac{\vec{E}_{1}}{j \omega L}$ tale che ([[Leggi di Kirchhoff#Legge di Kirchhoff per le correnti|LKC]])
$$
\vec{I}_{L} + \vec{I}_{C_{2}} + \vec{I}_{C_{3}}+  \vec{I}_{g} = 0
$$
Va dimensionata la bobina $L$ affinché si annulli la corrente di guasto, ricordando il grafico precedente sarà pari alla $I_g$:
$$
\vec{I}_{L} = -\left( \vec{I}_{C_{2}}-\vec{I}_{C_{3}} \right) = -j 3\omega C_{0} \vec{E}_{1} \Rightarrow I_{L} = 3E\omega C_{0}
$$
quindi la $L$:
$$
I_{L} = \frac{E}{\omega L} \Rightarrow L = \frac{1}{3 \omega^2 C_{0}}
$$
Si crea un fenomeno di risonanza parallelo, le tre correnti che nel circuito omopolare attraversano le capacità, si richiudono tutte nell'unica induttanza $L$, per questo motivo il fattore 3.
Non si ha mai un accoppiamento perfetto a causa dell'incertezza della $C_0$ e della resistenza di guasto, esistono dunque le normative che forniscono il valore ideale della $L$ in funzione della massima corrente di guasto in media tensione.

Alla sequenza omopolare l'impedenza della bobina di Petersen è attraversata da 3 correnti, per questo motivo nel modello ai circuiti di sequenza l'induttanza è moltiplicata per 3.

## Guasto monofase
.
$$
\vec{I}_{g} = 3\vec{E}_{1}\left( j\omega C_{0} + \frac{1}{3j\omega L} \right)
$$

....

$$
\vec{I}_{L} = - \left[ \left( \vec{E}_{2}- \vec{E}_{2} \right) j\omega C_{0} + \left( \vec{E}_{3} - \vec{E}_{1} \right) j\omega C_{0} \right] = -j\omega C_{0}\left( \vec{E}_{2} -\vec{E}_{1} + \vec{E}_{3} - \vec{E}_{1} \right) = j\omega C_{0}\left( 3\vec{E}_{1} \right)
$$
con
$$
\vec{E}_{2} + \vec{E}_{3} = -\vec{E}_{1}
$$
.