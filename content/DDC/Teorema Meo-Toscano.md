Sia $x_T(t)$ la soluzione del seguente problema differenziale:
$$
\left\{
\begin{aligned}
\frac{d}{dt} \vec{x} &= f_{0} (\vec{x}) + \sum_{k=1}^n f_{k}(\vec{x}) \cdot u_{k}(\vec{x},t) \\
\vec{x}(t_{0}) &= \vec{x}_{0}
\end{aligned}
\right.
$$
con $f_0$ e $f_k \in \mathbb{C}^\infty$ e sia 
$$
\left\{
\begin{aligned}
\frac{d}{dt} \vec{y} &= f_{0} (\vec{y}) + \sum_{k=1}^n f_{k}(\vec{y}) \cdot d_{k}(\vec{y},t) \\
\vec{y}(t_{0}) &= \vec{y}_{0}
\end{aligned}
\right.
$$
un altro [[problema di Cauchy]] espresso in una variabile differente.

Sia fissato $T_\eta>0$ il massimo periodo di switching di un convertitore e $L>0$ l'intervallo di osservazione, se 
$$
\vec{y}_{0}\equiv \vec{x}_{0}\ \ \forall\  T \in [0,T_{\eta}[ \text{ e }
\forall\ t \in [0,L]
$$
si ha:
$$
\Big\|\vec{x}_{T}(t)-\vec{y}(t)\Big\| < \eta
$$
con
$$
\eta = aT_{\eta}\left[ 1+\sqrt{ 1+\frac{b}{T_{\eta}} } \right]
$$
e $\vec{x}=\sqrt{ \sum_{k=1}^n x^2_{k} }$ dove $a$ e $b$ dipendenti dalle costanti di Lipschitz del convertitore e da $L$.

L'errore del [[modello averaged]] tende a 0 se il periodo di switching tende a 0, è solitamente considerato accettabile un errore del 10% sul ripple delle correnti e un errore dell'1% su quello delle tensioni del convertitore.
Oltre a stimare l'errore del modello si può fissare un errore desiderato e calcolare il massimo periodo di switching con la seguente formula inversa:
$$
T_{\eta} = g\eta \cdot e^{-[t_{0}-L]q}
$$
ancora una volta $g$ e $q$ dipendono dal convertitore.
Un secondo teorema enunciato nel 2020, afferma che se il numero di discontinuità $u_k$ è finito, fenomeno
chiamato "*no chattering*", allora la soluzione al primo sistema esiste ed è unica.