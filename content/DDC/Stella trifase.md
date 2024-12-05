Si segue una trattazione simile al [[Ponte monofase a tiristori|ponte monofase]] per la stella trifase, è presente un'induttanza di commutazione $L_{c}$ su ogni linea, un'induttanza $L_{d}$ sul carico.

Per la $k$-esima fase vale la seguente relazione:
$$
(L+Lc) \frac{d}{dt}i_{D} = v_{k0} - Ri_{D}
$$
dunque complessivamente in un periodo
$$
\frac{d}{dt}i_{D} = \frac{v_{10}S_{1}+v_{20}S_{2}+v_{30}S_{3}-Ri_{D}}{L+L_{c}}
$$
Con l'ipotesi di complementarietà si avrà uno spazio di controllo di ordine 2.
In DCM saranno presenti delle commutazioni, ad esempio nella commutazione dalla fase 1 alla fase 3 si ricava la seguente equazione differenziale, somma dei due contributi:
$$
\begin{aligned}
V_{3}-L_{c} \frac{d}{dt}i_{3} - L \frac{di_{D}}{dt}-Ri_{D}&=0\\ &+ \\
V_{1}-L_{c} \frac{d}{dt}i_{1} - L \frac{di_{D}}{dt}-Ri_{D}&=0 \\ &= \\
V_{3}+V_{1}-L_{c}\frac{d}{dt}i_{d} - 2L \frac{d}{dt}i_{D} -2Ri_{D} &=0
\end{aligned}
$$
Dunque dalla LKC si ricava:
$$
i_{3}+i_{1} = i_{d} \Rightarrow di_{3} + di_{1} = di_{D}
$$
.