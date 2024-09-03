Sia espresso un [problema differenziale ai valori iniziali](https://it.wikipedia.org/wiki/Problema_di_Cauchy):
$$
\left\{\begin{aligned}
\frac{d}{dt}\underline{x} &= F(t,\underline{x}) \\
\underline{x}(t_{0}) & = \underline{x_0}
\end{aligned}
\right.
$$
e sia $F$ [funzione continua](https://it.wikipedia.org/wiki/Funzione_continua) in $t$ e [[Funzione lipschitziana|lipschitziana]] rispetto ad $\underline{x}$, allora
$$
\exists\  \varepsilon > 0\ \forall\ t \in [t_{0}-\varepsilon, t_{0} + \varepsilon]
$$
tale che la soluzione esiste ed è unica.
Quanto enunciato è il [teorema di Cauchy-Lipschitz](https://it.wikipedia.org/wiki/Teorema_di_esistenza_e_unicit%C3%A0_per_un_problema_di_Cauchy) e fornisce la soluzione locale al problema di Cauchy, se $\varepsilon$ tende all'infinito allora la soluzione esiste globalmente ed è unica.