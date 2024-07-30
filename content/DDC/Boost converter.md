Qui si presenteranno i modelli del boost converter
# Modello dinamico
Se si ipotizza la conduzione continua (CCM) si hanno due stati del convertitore se
l'istante di tempo "t" è maggiore o minore di t_on, considerato come il tempo di conduzione del dispositivo dinamico.
## t <  ton
Si presenta il modello dinamico del boost converter

![Immagine](https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Boost_conventions.svg/1920px-Boost_conventions.svg.png)
Durante la fase iniziale quindi per t<T_on lo switch è in conduzione, il diodo è interdetto dunque

$$
\left\{\begin{aligned} L\frac{di_L}{dt} &= V_s \\ C\frac{dv_c}{dt} &= -i_0 = -\frac{v_C}{R} \\ i_L(0^+) & = i_L(0^-) = 0\\ v_C(0^+) &= v_C(0^-) = 0 \end{aligned}\right.
$$
con condizioni iniziali nulle;
questo si ricava applicando la [[Leggi di Kirchhoff#Legge di Kirchhoff per le tensioni|LKT]] alla prima maglia e la [[Leggi di Kirchhoff#Legge di Kirchhoff per le correnti|LKC]] al nodo tra carico e condensatore.
$$
\frac{d\vec{x}}{dt} = \frac{d}{dt}\begin{bmatrix} i_L \\ v_C \end{bmatrix} = \begin{bmatrix} 0 & 0 \\ 0 & \frac{-1}{RC} \end{bmatrix} \cdot \begin{bmatrix} i_L \\ v_C \end{bmatrix} + \begin{bmatrix} \frac{1}{L} \\0 \end{bmatrix}\cdot V_s
$$


## t  > ton
Aperto lo switch si ha l'andata in conduzione del diodo, cambia il modello del sistema che diventa:
$$
\left\{\begin{aligned} L\frac{di_L}{dt} & = V_s - v_C \\ i_c = i_L &- i_0 = C\frac{dv_c}{dt} = i_L - \frac{v_C}{R} \\ i_L(t_{on}^*) &= i_L(t_{on}^-) \\ v_C(t_{on}^+) & = v_C(t_{on}^-) \end{aligned}\right.
$$
Le incognite saranno le grandezze di stato, ovvero le quantità in grado di immagazzinare energia, associate ai componenti dinamici.
$$
\frac{d\vec{x}}{dt} = \frac{d}{dt}\begin{bmatrix} i_L \\ v_C \end{bmatrix} = \begin{bmatrix} 0 & \frac{-1}{L} \\ \frac{1}{C} & \frac{-1}{RC} \end{bmatrix} \cdot \begin{bmatrix} i_L \\ v_C \end{bmatrix} + \begin{bmatrix} \frac{1}{L} \\0 \end{bmatrix}\cdot V_s
$$
La prima è la matrice *A*, la seconda la matrice *B*

## Funzioni di attivazione
Si riportano dunque le funzioni di attivazione del boost che permettono di *selezionare* i due stati del convertitore.

$$
\begin{aligned}
h_{1} &= \left\{\begin{aligned}
1 \ & t\in [0,t_{on}[\\
0 \ & t\notin [0,t_{on}[\\
\end{aligned}
\right. \\
h_{2} &= \left\{\begin{aligned}
1 \ & t\in [t_{on},T[\\
0 \ & t\notin [t_{on},T[\\
\end{aligned}
\right.
\end{aligned}
$$

# Modello affine e bilineare


