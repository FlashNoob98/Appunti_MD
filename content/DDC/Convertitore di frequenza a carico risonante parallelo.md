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
-\frac{R_{f}}{L_{f}} & +\frac{1}{L_{f}} & 0  \\
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
.