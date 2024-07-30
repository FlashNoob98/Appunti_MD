Il modello affine nel controllo permette di esplicitare le grandezze di controllo,
partendo dal [[Modello dinamico alle configurazioni|modello alle configurazioni]] è possibile esplicitare il sistema mediante funzioni [[Definizione di mappa|mappa]], in questo caso la $F$ e la $C$.

L'equazione della dinamica del modello è:
$$
\frac{d}{dt}\vec{x} = F(t,\vec{x},\vec{u})
$$
Mentre per le uscite:
$$
\vec{y} = C(t,\vec{x},\vec{u})
$$
Dove $\vec{x}$ è il vettore di stato e $\vec{u}$ è quello delle grandezze di controllo totali o parziali.
La $F$ può essere però espressa in forma *autonoma* dunque non dipendente esplicitamente dal tempo e separata in altre due funzioni nel seguente modo:
$$
F(\vec{x},\vec{u}) = f(\underline{x})+G(\underline{x})\underline{u}
$$
dunque
$$
\frac{d \vec{x}}{dt} = f(\underline{x})+ G(\underline{x})\underline{u}
$$

dove $f$ è un campo vettoriale $f:\mathbb{R}^n\to\mathbb{R}^n$ ovvero
$$
f(\underline{x}) = \begin{bmatrix}
f_{1}(x_{1},x_{2}\dots x_{n}) \\ 
f_{2}(x_{1},x_{2}\dots x_{n}) \\ 
\vdots \\
f_{n}(x_{1},x_{2}\dots x_{n}) 
\end{bmatrix}
$$

$G$ è invece una mappa, $G(\underline{x}):\mathbb{R}^n\rightarrow\mathbb{R}^{n\times m}$ ed è così rappresentata:
$$
G(\underline{x}) = \begin{bmatrix}
g_{11}(\underline{x}),\ \dots,\ g_{1m}(\underline{x}) \\ 
g_{21}(\underline{x}),\ \dots,\ g_{2m}(\underline{x})\\ 
\vdots \\
g_{n1}(\underline{x}),\ \dots,\ g_{nm}(\underline{x}) 
\end{bmatrix}
$$

$m$ è la dimensione del vettore di controllo $\underline{u}$, ogni sua componente appartiene allo spazio discreto $u_1 \in\{0,1\},\ u_2 \in\{0,1\}\dots$ dunque $\underline{u}\in\{0,1\}^{m}\subset\mathbb{R}^n$  

Risolvendo il prodotto cartesiano $G(\underline{x})\underline{u}$ si ottiene che ogni colonna della $G$ è moltiplicata per un elemento della $\underline{u}$, sfruttando tale proprietà si riscrive il modello dinamico nella seguente forma:
$$
\frac{d\underline{x}}{dt} = f(\underline{x}) + \sum_{\nu = 1}^m g_{\nu}(\underline{x})u_{\nu}
$$
Ogni singola funzione $g_{\nu}$ è un campo vettoriale in quanto definita $g_{\nu}:\mathbb{R}^n\to\mathbb{R}^n$ 
Tale modello può infine essere utilizzato come algoritmo di controllo, a causa della presenza esplicita del vettore $\underline{u}$. 

