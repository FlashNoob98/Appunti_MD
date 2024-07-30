Qui si presenteranno i modelli del boost converter
# Modello dinamico
Se si ipotizza la conduzione continua (CCM) si hanno due stati del convertitore se
l'istante di tempo $t$ è maggiore o minore di $t_{on}$, considerato come il tempo di conduzione del dispositivo dinamico.
## t <  $t_{on}$
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


## t  > $t_{on}$
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

Unendo le configurazioni precedenti mediante le funzioni di attivazione si ottiene il modello dinamico globalmente valido:
$$
\left\{
\begin{aligned}
\frac{d}{dt} i_{l} &= \frac{Vs}{L} - \frac{v_{c}}{L}(1-u)\\
\frac{d}{dt} v_{c} &= \frac{i_{l}}{C}(1-u) - \frac{v_{c}}{RC}
\end{aligned}\right.
$$
Quando $u=1$ il componente controllato conduce.

Ottenute le matrici della dinamica si riporta il [[Modello dinamico affine nel controllo|modello affine nel controllo]] 

$$
f(\underline{x}) = \begin{bmatrix}
\frac{Vs}{L}-\frac{x_{2}}{L}\\ \\
\frac{x_{1}}{C}  -\frac{x_{2}}{RC}
\end{bmatrix}
\quad G(\underline{x}) = \begin{bmatrix}
\frac{x_{2}}{L} \\ 
-\frac{x_{1}}{C}
\end{bmatrix}
$$

dove il vettore delle incognite $\underline{x} = [i_{l,v_{c}}]^T$ mentre $u\in\mathbb{R}$ .
Si può ora riportare in [[Forma bilineare|forma bilineare]]:

$$
\begin{aligned}
A &= \begin{bmatrix}
0 & -\frac{1}{L} \\ 
\frac{1}{C} & -\frac{1}{RC}
\end{bmatrix};\quad \underline{a}_{0}=
\begin{bmatrix}
\frac{Vs}{L} \\ 0
\end{bmatrix}\\
B &= \begin{bmatrix}
0 & \frac{1}{L} \\ 
-\frac{1}{C} & 0
\end{bmatrix};\quad \underline{b}_{1}=
\begin{bmatrix}
0 \\ 0
\end{bmatrix}
\end{aligned}
$$

# DCM
Se cade l'ipotesi di conduzione continua si ha il fenomeno di conduzione discontinua, la corrente nell'induttore ovvero raggiunge il valore nullo per un certo periodo di tempo, in ogni periodo di switching, ciò comporta il passaggio da 2 a 3 configurazioni, dunque $m$ dovrà essere pari a 2 (e non più 1).
