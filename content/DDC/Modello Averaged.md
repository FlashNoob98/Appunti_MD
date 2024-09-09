Si considerino le configurazioni di un convertitore a partire dal modello dinamico, si ipotizza che queste *agiscano* sul sistema per un certo periodo di tempo, pari al *duty ratio* $d$, si ipotizza dunque che ogni configurazione ha un effetto "pesato" sul sistema.
Sia $d$ la frazione di periodo nel quale è attiva la configurazione (1) del sistema e di conseguenza $(1-d)$ quella in cui sia attiva la seconda configurazione, si ottiene:
$$
\begin{aligned}
\frac{d}{dt}\vec{x} &= \left(A_{1}\vec{x} + B_{1}\vec{v}\right)d\\
\frac{d}{dt}\vec{x} &= \left(A_{2}\vec{x} + B_{2}\vec{v}\right)(1-d)
\end{aligned}
$$
effettuando la somma
$$
\frac{d}{dt}\vec{x} = A_{2}\vec{x}+B_{2}\vec{v} +(A_{1}-A_{2})\vec{x}d +(B_{1}-B_{2})\vec{v}d
$$
Il modello ottenuto è sempre risolvibile nel tempo, se si trascura il *ripple* delle grandezze di stato si possono risolvere i valori medi.
Generalizzando si applica la [[Media Mobile|media mobile]] al modello [[Modello dinamico affine nel controllo|affine nel controllo]] ottenendo:
$$
\left<\frac{d\vec{x}}{dt}\right>_{0} = \left<f(\vec{x}) \right>_{0} + \left<G(\vec{x})\vec{u}\right>_{0}
$$
Il modello richiede due semplificazioni:
- $\left<f (\vec{x})\right>_{0} = f(<\vec{x}>_{0})$
- $\left<G(\vec{x})\cdot \vec{u}\right>_{0}=\left<G (\vec{x})\right>_{0}\cdot\left<\vec{u}\right>_{0}$

La prima ipotesi è un'uguaglianza esatta se il modello è [[Forma bilineare|bilineare]]:
$$
f(\vec{x}) = A \vec{x} + a_{0} \Rightarrow \left<f(\vec{x})\right>_{0} = A\left<\vec{x}\right>_{0} + \left<a_{0}\right>_{0} = A\left<\vec{x}\right>_{0} + a_{0} = f(\left<\vec{x}\right>_{0})
$$
La seconda ipotesi è più forte ed è valida solo quando i [[Ripple Factor|ripple factor]] sono trascurabili:
$$
\begin{aligned}
\left<x(t)\cdot y(t)\right>_{0} &= C_{0} =\sum_{j=-\infty}^{+\infty} \left<x\right>_{-j}\cdot\left<y\right>_{j} = \left<x\right>_{0}\cdot\left<y\right>_{0} + \sum_{\stackrel{j \neq{0}}{j=-\infty}}^{+\infty}\left<x\right>_{-j}\cdot\left<y\right>_{j} \\
\sum_{\stackrel{j \neq{0}}{j=-\infty}}^{+\infty}\left<x\right>_{-j}\cdot\left<y\right>_{j} & \leq \sum_{j}\left|\left<x\right>_{-j}\right|\cdot \left|\left<y\right>_{j}\right| \leq \sum_{j}\sqrt{ \left|\left<x\right>_{-j}\right|^2 }\cdot\sqrt{ \left|\left<y\right>_{j}\right|^2 } \leq\\
&\leq \sum_{j}\sqrt{ \frac{\left|\left<x\right>_{-j}\right|^2 \left<x\right>_{0}^2}{\left<x\right>_{0}^2} }\cdot \sqrt{ \frac{\left|\left<y\right>_{j}\right|^2 \left<y\right>_{0}^2}{\left<y\right>_{0}^2} } \leq \left[ \text{Rf}(x)\cdot \text{Rf}(y)\right] \left<x\right>_{0}\left<y\right>_{0}
\end{aligned}
$$
sostituendo nella prima:
$$
\left<x(t)\cdot y(t)\right>_{0} \leq \left<x\right>_{0}\cdot\left<y\right>_{0} +\left[ \text{Rf}(x)\cdot \text{Rf}(y)\right] \left<x\right>_{0}\left<y\right>_{0} \leq \left<x\right>_{0}\cdot\left<y\right>_{0} \left[1+ \text{Rf}(x)\cdot \text{Rf}(y) \right]
$$
si ha il prodotto di due termini che tendono a zero, dunque è trascurabile, analogamente queste ipotesi sono valide se il periodo di switching $T$ è molto piccolo.

Si definisce con $\vec{d}$ il vettore dei *duty ratio* ovvero ogni componente switching del convertitore può avere un suo periodo di funzionamento indipendente, applicando le ipotesi appena mostrate si formalizza il modello averaged per una generica struttura:
$$
\left<\frac{d\vec{x}}{dt}\right>_{0} = \frac{d}{dt}\left<\vec{x}\right>_{0} = f\left(\left<\vec{x}\right>_{0}\right) + G\left(\left<\vec{x}\right>_{0}\right)\cdot \vec{d}
$$
Questo modello è continuo e verifica le condizioni di [[Problema di Cauchy|Cauchy]].