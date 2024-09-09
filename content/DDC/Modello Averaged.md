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
- $\left<G(\vec{x}\cdot \vec{u})\right>_{0}=\left<G (\vec{x})\right>_{0}\cdot\left<\vec{u}\right>_{0}$

La prima ipotesi è un'uguaglianza esatta se il modello è [[Forma bilineare|bilineare]] 
