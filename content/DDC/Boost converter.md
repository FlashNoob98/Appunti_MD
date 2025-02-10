Si presentano i diversi modelli con i quali si può studiare il boost converter
# Modello dinamico
Se si ipotizza la conduzione continua (CCM) si hanno due stati del convertitore se
l'istante di tempo $t$ è maggiore o minore di $t_{on}$, considerato come il tempo di conduzione del dispositivo dinamico.
## $t <  t_{on}$
Si presenta il modello dinamico del boost converter
<center>

![[boost_converter.svg]]

</center>


Durante la fase iniziale quindi per $t<T_{on}$ lo switch è in conduzione, il diodo è interdetto dunque

$$
\left\{\begin{aligned} L\frac{di_L}{dt} &= V_s \\ C\frac{dv_c}{dt} &= -i_0 = -\frac{v_C}{R} \\ i_L(0^+) & = i_L(0^-) = 0\\ v_C(0^+) &= v_C(0^-) = 0 \end{aligned}\right.
$$
con condizioni iniziali nulle;
questo si ricava applicando la [[Leggi di Kirchhoff#Legge di Kirchhoff per le tensioni|LKT]] alla prima maglia e la [[Leggi di Kirchhoff#Legge di Kirchhoff per le correnti|LKC]] al nodo tra carico e condensatore.
$$
\frac{d\vec{x}}{dt} = \frac{d}{dt}\begin{bmatrix} i_L \\ v_C \end{bmatrix} = \begin{bmatrix} 0 & 0 \\ 0 & \frac{-1}{RC} \end{bmatrix} \cdot \begin{bmatrix} i_L \\ v_C \end{bmatrix} + \begin{bmatrix} \frac{1}{L} \\0 \end{bmatrix}\cdot V_s
$$

## $t  \geq t_{on}$
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
\frac{Vs}{L}-\frac{x_{2}}{L}\\ 
\frac{x_{1}}{C}  -\frac{x_{2}}{RC}
\end{bmatrix}
\quad G(\underline{x}) = \begin{bmatrix}
\frac{x_{2}}{L} \\ 
-\frac{x_{1}}{C}
\end{bmatrix}
$$

dove il vettore delle incognite $\underline{x} = [i_{l},v_{c}]^T$ mentre $u\in\mathbb{R}$ .
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

# Grandezze di switching
Il convertitore boost presenta due dispositivi switching, uno di questi però, il diodo, non è controllabile dall'esterno, se si vuole includere il suo stato nel modello globale alle configurazioni è necessario includere una ulteriore variabile di switching $u_2$ che tenga appunto conto dello stato del diodo, ciò aggiunge una ulteriore configurazione al modello, in cui il tiristore non conduce ma il diodo sì a causa della scarica dell'induttore.

$$
\left\{
\begin{aligned}
\frac{d}{dt} i_{l} &= \left[\frac{Vs}{L} - \frac{v_{c}}{L}(1-u_{1})\right]u_{2}\\
\frac{d}{dt} v_{c} &= \frac{i_{l}}{C}(1-u_{1})u_{2} - \frac{v_{c}}{RC}
\end{aligned}\right.
$$

Per determinare il valore di $u_2$ si può usare la [[funzione signum]] nel seguente modo:

$$
u_{2} = \frac{sign(i_{L})+1}{2}
$$
dunque $u_1$ dipende prettamente dal tempo (tempo in cui si impulsa il tiristore) mentre la $u_2$ dipende unicamente dalla corrente nell'induttore, dunque una variabile di stato del sistema.

Sviluppando i prodotti si ottiene un modello non più esprimibile nella forma del controllo:

$$
\left\{
\begin{aligned}
\frac{d}{dt} i_{l} &= \frac{Vs}{L}u_{2} - \frac{v_{c}}{L}(u_{2}-u_{1}u_{2})\\
\frac{d}{dt} v_{c} &= \frac{i_{l}}{C}(u_{2}-u_{1}u_{2}) - \frac{v_{c}}{RC}
\end{aligned}\right.
$$

dato che $u_2$ sarà sempre pari ad 1 per un periodo di tempo superiore ad $u_1$, il loro prodotto sarà allora pari ad $u_1$:

$$
\left\{
\begin{aligned}
\frac{d}{dt} i_{l} &= \frac{Vs}{L}u_{2} - \frac{v_{c}}{L}(u_{2}-u_{1})\\
\frac{d}{dt} v_{c} &= \frac{i_{l}}{C}(u_{2}-u_{1}) - \frac{v_{c}}{RC}
\end{aligned}\right.
$$
Si definisce la grandezza di controllo del diodo $u_{d}$:
$$
u_{d} = u_{2} - u_{1}
$$
Il modello diventa:
$$
\left\{
\begin{aligned}
\frac{d}{dt} i_{l} &= \frac{Vs}{L}(u_{d}+u_{1}) - \frac{v_{c}}{L}u_{d}\\
\frac{d}{dt} v_{c} &= \frac{i_{l}}{C}u_{d} - \frac{v_{c}}{RC}
\end{aligned}\right.
$$
da cui si ricava il nuovo [[#Modello affine e bilineare|modello affine]] nel controllo:
$$
f(\underline{x}) = \begin{bmatrix}
0 \\ -\frac{x_{2}}{RC}
\end{bmatrix} \quad
G(\underline{x}) = \begin{bmatrix}
\frac{x_{2}}{L} & \frac{V_{s}-x_{2}}{L} \\ \\
-\frac{x_{1}}{C} & \frac{x_{1}}{C}
\end{bmatrix}\cdot\begin{bmatrix}
u_{1} \\ \\ u_{2}
\end{bmatrix}
$$
riportato in [[Forma bilineare|forma bilineare]]:
$$
\begin{aligned}
A &= \begin{bmatrix}
0 & 0  \\
0 & -\frac{1}{RC}
\end{bmatrix};\ a_{0} = 0\ \\
B_{1} &= \begin{bmatrix}
0 & \frac{1}{L} \\ 
-\frac{1}{C} & 0
\end{bmatrix} ;\ b_{1} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}
 \\
B_{2} &= \begin{bmatrix}
0 & -\frac{1}{L} \\ 
\frac{1}{C} & 0
\end{bmatrix} ;\ b_{2} = \begin{bmatrix} \frac{V_{s}}{L} \\ 0 \end{bmatrix}
\end{aligned}
$$

# Modello ROAM
Si può utilizzare il [[modello ROAM]] per studiare la dinamica in DCM.
Riprendendo il sistema alle configurazioni:
$$
\left\{
\begin{aligned}
\frac{d}{dt} i_{l} &= \frac{Vs}{L}u_{2} - \frac{v_{c}}{L}(u_{2}-u_{1})\\
\frac{d}{dt} v_{c} &= \frac{i_{l}}{C}(u_{2}-u_{1}) - \frac{v_{c}}{RC}
\end{aligned}\right.
$$
In questo caso non si conosce in anticipo il valore di $t_1$ in cui si annulla la corrente $i_L$ in quanto è proprio un'incognita del sistema.
La dinamica di $v_C$ è però molto più lenta rispetto al periodo $T$ di switching con cui varia la corrente $i_L$, dunque la si assume costante.
Le variabili di stato sono inoltre associate allo stato energetico di un sistema, in questo caso, in ogni periodo di switching la corrente parte da un valore nullo, dunque si può supporre che non influisca lo stato del sistema.

La dinamica della corrente è dunque:
$$
\left\{
\begin{aligned}
\frac{V_{S}}{L}t &\qquad 0\leq t<t_{on}\\
\frac{V_{S}-\langle v_{C} \rangle_{0} }{L}(t-t_{on})+I_{M} & \qquad t_{on} \leq t < t_{on}+t_{1} \\
0 &\qquad t_{on}+t_{1}\leq t < T
\end{aligned}
\right.
$$
Ci si sofferma sulla dinamica funzione di $t_1$:
$$
\left\{
\begin{aligned}
\frac{d}{dt} i_{L} &= \frac{V_{s}}{L} - \frac{\langle v_{C} \rangle_{0}}{L} \qquad t_{on} \leq t < t_{on}+t_{1} \\
i_{L}(t_{on}) &= I_{M}
\end{aligned}
\right.
$$
si riporta invece la dinamica $\vec{x}_{LF}$ con il [[modello averaged]] esatto:
$$
\frac{d}{dt} \langle v_{C} \rangle_{0} = \frac{\langle i_{L}(u_{2}-u_{1}) \rangle_{0} }{C} - \frac{\langle v_{C} \rangle_{0}}{RC}  
$$
al fine di stimare il valor medio si ricava il tempo $t_1$ in funzione di $v_C$:
$$
\begin{aligned}
i_{L}(t_{on}+t_{1}) =0 &= \frac{V_{S}-\langle v_{C} \rangle_{0} }{L}t_{1} +\frac{V_{S}}{L}t_{on} \\
-V_{S}t_{on} &= (V_{S}-\langle v_{C} \rangle_{0} )t_{1} \\
t_{1} &= \frac{V_{S}\cdot t_{on}}{\langle v_{C} \rangle_{0}-V_{S} }
\end{aligned}
$$
Con l'ultima relazione si può ricavare il valor medio del prodotto, vedendo anche la forma d'onda della corrente:
$$
\langle i_{L}(u_{2}-u_{1}) \rangle_{0} = \frac{I_{M}\cdot t_{1}}{2T} = \frac{V_{S}t_{on}}{2LT}\cdot \frac{V_{S}t_{on}}{\langle v_{C} \rangle_{0}-V_{S} } = \frac{V_{S}^2d^2T}{2L(\langle v_{C} \rangle_{0}-V_{S} )}
$$
e quindi l'espressione completa della tensione:
$$
\frac{d}{dt}\langle v_{C} \rangle_{0} = \frac{V_{S}^2d^2T}{2LC(\langle v_{C} \rangle_{0}-V_{S} )} - \frac{\langle v_{C}\rangle_{0}}{RC}  
$$
tutto in funzione di $\langle v_{C} \rangle_{0}$.
Se si calcolasse il ripple:
$$
R_{PP}(i_{L}) = \frac{\Delta i_{L}}{\langle i_{L} \rangle_{0} } = \frac{I_{\text{max}}\cdot2T}{I_{\text{max}}(t_{on}+t_{1})} = \frac{2T}{t_{on}+t_{1}} \gg 1
$$
Non è trascurabile il ripple e dunque non si può utilizzare in questo caso il [[Modello Averaged|modello averaged]].

# Curva integrale
 Utilizzando il [[Problema di Cauchy|teorema di Cauchy]] si vuole risolvere il [[#Modello dinamico|modello dinamico in CCM]] del convertitore, separato nelle due differenti configurazioni.
## $t<t_{on}$
Si mostra l'integrale del modello nella prima configurazione:
$$
\begin{aligned}
v_{C}(t) & = -\frac{I_{0}}{C}t + V_{C_{0}} \\
i_{L}(t) & = \frac{V_{s}}{L}t + I_{L_{0}}
\end{aligned}
$$
dove $I_{L_0}$ e $V_{C_{0}}$ sono i valori iniziali, $I_0$ la corrente costante assorbita dal carico.
Si ricava il tempo in funzione della $V_c$  e lo si sostituisce nella funzione della corrente per ricavare la traiettoria parametrica.
$$
\begin{aligned}
t &= \left[V_{C_{0}}-v_{C}(t)\right]\frac{C}{I_{0}} \\
i_{L}(t) & = \frac{V_{s}}{L}\left[V_{C_{0}}-v_{C}(t)\right]\frac{C}{I_{0}} + I_{L_{0}} \\
i_{L}(t) & = f(v_{C}(t))
\end{aligned}
$$
Si ottiene l'equazione di un segmento.
## $t\geq t_{on}$
Per la seconda configurazione si deriva ulteriormente l'equazione della corrente e si sostituisce la derivata della tensione con la seconda equazione del sistema ottenendo la seguente equazione differenziale del secondo ordine:
$$
\frac{d^2i_{L}}{dt^2} + {i_{L}}{\omega_{0}^2} = {I_{0}}\omega_{0}^2
$$
dove $\omega_0^2=\frac{1}{LC}$. Per l'ipotesi di continuità i valori iniziali delle variabili di stato sono pari al valore finale raggiunto nel precedente periodo, saranno indicate con $I_{on}$ e $V_{on}$.
Si risolve l'omogenea associata:
$$
\lambda^2 + \omega_{0}^2 = 0 \Rightarrow \lambda_{1 /2} = \pm j \omega 
$$
Dunque l'equazione della dinamica sarà:
$$
i_{L}(t) = A\cos \left( \omega_{0}(t-t_{on})\right) + B \sin (\omega_{0}(t-t_{on}) )+ I_{0}
$$
dunque
$$
\begin{aligned}
i_{L}(t_{on}) &= I_{on} = A+I_{0} & \Rightarrow & & A = I_{on} - I_{0} \\
\frac{di_{L}}{dt}(t_{on}) &= B\omega_{0} = \frac{V_{s}-V_{C_{on}}}{L} & \Rightarrow & & B = \frac{V_{s}-V_{C_{on}}}{L\cdot \omega_{0}} 
\end{aligned}
$$
Si pongono ora
$$
\begin{aligned}
A & = C\sin \varphi \\
B & = C\cos \varphi \\
C & = \sqrt{A^2+B^2}
\end{aligned}
$$
 sostituendo nelle precedenti si ottiene una forma più compatta:
 $$
\begin{aligned}
i_{L}(t) &= \sqrt{ A^2+B^2 }\cdot \sin \left(\omega_{0}(t-t_{{on}})+\arctan \frac{A}{B} \right) \\
\frac{d}{dt}i_{L}(t) &= \sqrt{ A^2+B^2 }\cdot \omega _{0} \cos \left(\omega_{0}t+\arctan \frac{A}{B} \right)= \\
&= \sqrt{ A^2+B^2 }\cdot \omega _{0} \cos \left[\arcsin\frac{\left(i_{L}(t)-I_{0}\right)}{\sqrt{ A^2+B^2 }} \right]  = \\
&=\sqrt{A^2+B^2} \cdot \omega_{0} \sqrt{ 1- \frac{(i_{L}(t)-I_{0})^2}{A^2+B^2} } = \frac{V_{s}-V_{c}(t)}{L} \\
\left(A^2+B^2\right) \cdot & \left[\frac{A^2+B^2-(i_{L}(t)-I_{0})^2}{A^2+B^2}\right] = \frac{(V_{s}-V_{c}(t))^2}{\omega_{0}^2L^2} \\
\frac{(V_{s}-V_{c}(t))^2}{\omega_{0}^2L^2} & + (i_{L}(t)-I_{0})^2 = A^2+B^2
\end{aligned}
$$
Quella ottenuta è l'espressione di un ellisse dunque la traiettoria del sistema è *semi-ellittica*, si è trovato il [[Dinamica dei convertitori elettrici#Ciclo limite|ciclo limite]] del convertitore.

# Modello small signal
Si ricava il [[modello small signal]] a partire dall'averaged per il boost converter.
Partendo dal [[#Modello affine e bilineare|modello affine e bilineare]]:
$$
\frac{d}{dt} \begin{bmatrix}
\langle i_{L} \rangle \\ \langle v_{C} \rangle  
\end{bmatrix} = \begin{bmatrix}
0 & -\frac{1}{L} \\ \frac{1}{C} & -\frac{1}{RC}
\end{bmatrix} 
\begin{bmatrix}
\langle \delta i_{L} \rangle \\ \langle \delta v_{C} \rangle  
\end{bmatrix} +
\begin{bmatrix}
\frac{V_{s}}{L} \\ 0
\end{bmatrix} + 
\begin{bmatrix}
0 & \frac{1}{L} \\ -\frac{1}{C} & 0
\end{bmatrix}
\begin{bmatrix}
\langle i_{L} \rangle \\ \langle v_{C} \rangle  
\end{bmatrix}
$$
si ricava la matrice $A_s = A+B_{\nu}\cdot D_{\nu}$ ovvero
$$
A_{s} = \begin{bmatrix}
0 & -\frac{1}{L} \\ \frac{1}{C} & -\frac{1}{RC}
\end{bmatrix} + 
\begin{bmatrix}
0 & \frac{1}{L} \\ -\frac{1}{C} & 0
\end{bmatrix} D = 
\begin{bmatrix}
0 & -\frac{1}{L}(1-D) \\ \frac{1}{C}(1-D) & -\frac{1}{RC}
\end{bmatrix}
$$
mentre per il calcolo della matrice $B_s$ sono necessari $\langle v_{C} \rangle = \frac{V_{s}}{1-D}$ e $\langle i_{L} \rangle=\frac{\left\langle  v_{C}  \right\rangle}{R(1-D)} = \frac{V_{s}}{R(1-D)^2}$ calcolati nel punto di equilibrio, dunque:
$$
B_{s} = \begin{bmatrix}
0 & \frac{1}{L} \\ -\frac{1}{C} & 0
\end{bmatrix}\cdot
\begin{bmatrix}
\frac{V_{s}}{R(1-D)^2} \\ \frac{V_{s}}{1-D}
\end{bmatrix} =
\begin{bmatrix}
\frac{V_{s}}{L(1-D)} \\ -\frac{V_{s}}{RC(1-D)^{2}}
\end{bmatrix}
$$

Si ipotizza di sostituire il valor medio delle grandezze con un valore costante ed una variazione $\delta$ ottenendo
$$
\begin{aligned}
\frac{d}{dt} \langle i_{L} \rangle &= \frac{d}{dt}(I_{L}+ \langle \delta i_{L} \rangle ) = \frac{V_{s}}{L} - \frac{\left\langle  V_{c} + \delta v_{C}  \right\rangle}{L} [1-(D+\delta d)] \\
\frac{d}{dt}  \langle v_{C} \rangle &= \frac{d}{dt}(V_{c}+\langle \delta v_{C} \rangle ) = \frac{I_{L}+\langle \delta i_{L} \rangle }{C} [1-(D+\delta d)] - \frac{V_{C}+\langle \delta v_{C} \rangle }{RC}
\end{aligned}
$$

ricordando che a regime i valori medi sono legati dalla seguente relazione: $V_{s}=V_{c}(1-D)$ si semplifica la prima relazione:
$$
\frac{d}{dt}(\langle \delta i_{L} \rangle +I_{L} ) = \cancel{\frac{V_{S}}{L} - \frac{V_{C}}{L}[1-D]} + \frac{V_{C}\cdot\delta d}{L} - \frac{\delta v_{C}}{L}(1-D) + \frac{{\langle\delta v_{C}\rangle\langle \delta d \rangle}}{L}
$$
L'ultimo termine è trascurabile se le variazioni sono piccole, si ottiene un termine del secondo ordine.
Analogamente per la tensione:
$$
\frac{d}{dt}(V_{C}+\langle \delta v_{C} \rangle ) = \frac{I_{L}+\langle \delta i_{L} \rangle}{C} [1-(D+\delta d)] - \frac{V_{C}+\left\langle\delta v_{C}\right\rangle}{RC}
$$
Il modello è stato però calcolato in un punto di regime, dunque si trascurano i valori costanti e si valutano le medie delle variazioni, in sintesi il modello diventa:
$$
\left\{
\begin{aligned}
\frac{d}{dt}\langle \delta i_{L} \rangle  & =   \frac{V_{s}}{(1-D)}\cdot\frac{\delta d}{L} - \frac{\delta v_{C}}{L}(1-D) \\
\frac{d}{dt}\langle \delta v_{C} \rangle  &=  \frac{\langle \delta i_{L} \rangle }{C}(1-D)
- \frac{\langle \delta v_{C} \rangle }{RC}
\end{aligned}
\right.
$$
Può essere riscritto nella seguente forma per ricavare la [[funzione di trasferimento]]:
$$
\left\{
\begin{aligned}
\frac{d}{dt} \left\langle  \delta \vec{x}  \right\rangle &= A_{s} \left\langle  \delta \vec{x}  \right\rangle  +B_{s} \cdot\delta d\\
\frac{d}{dt}y &= C\delta \vec{x}\\
&\text{ovvero}\\
L \frac{d}{dt} \left\langle  \delta i_{L}  \right\rangle &= V_{C}\delta d - (1-D) \langle \delta v_{C} \rangle \\
C \frac{d}{dt} \langle \delta v_{C} \rangle &= (1-D) \langle \delta i_{L} \rangle -\frac{ \left\langle  \delta v_{C} \right\rangle}{R} - I_{L}\delta d   
\end{aligned}
\right.
$$
Si trasformano le equazioni nel dominio di Laplace:
$$
\left\{
\begin{aligned}
sL\delta i_{L} &= V_{c}\delta d - (1-D)\delta v_{C}\\
sC\delta v_{C} &= (1-D)\left[ \frac{V_{c}\delta d - (1-D)\delta v_{C}}{sL} \right] - \frac{\delta v_{C}}{R} - I_{L}\delta d
\end{aligned}
\right.
$$
raccogliendo la seconda equazione e ricordando che $I_{L}=\frac{V_{C}}{R(1-D)}$:
$$
\begin{aligned}
&\left[ sC + \frac{(1-D)^2}{sL} +\frac{1}{R} \right]\delta v_{C} = \left[ \frac{(1-D)v_{C}}{sL} -I_{L}\right]\delta d\\
&\frac{s^2RLC +sL+ (1-D)^2s}{sRL}\delta v_{C}= \frac{(1-D)v_{C}}{sL} - \frac{v_{C}}{R(1-D)}= \frac{R(1-D)^2 -sL}{sLR(1-D)}v_{C}\delta d
\end{aligned}
$$
Si esprime la [[funzione di trasferimento]]:
$$
\frac{\delta v_{C}}{\delta d} = \frac{\frac{R(1-D)^2 -sL}{\cancel{sLR}(1-D)}v_{C}}{\frac{s^2RLC +sL+ (1-D)^2s}{\cancel{sRL}}} = \frac{(R(1-D)^2-sL)v_{C}}{(1-D)(s^2RLC+sL+R(1-D)^2)}
$$
dividendo per $R(1-D)^2$ si ottiene una forma canonica:
$$
\frac{\delta v_{C}}{\delta d} = \frac{v_{C}\left( 1-\frac{sL}{R(1-D)^2} \right)}{(1-D)\left( 1+\frac{sL}{R(1-D)^2}+\frac{s^2LC}{(1-D)^2} \right)}
$$
dalla quale si possono definire dei parametri caratteristici per il boost:
$$
\begin{matrix}
G_{d{0}} = \frac{v_{C}}{1-D} & \omega_{z}=\frac{R(1-D)^2}{L}\\ Q = (1-D)R\sqrt{ \frac{C}{L} } & \omega_{0}^2 = \frac{1-D}{LC}
\end{matrix}
$$
e riscrivere la [[funzione di trasferimento]] in una [[funzione di trasferimento#FdT dei convertitori|forma generale]]:
$$
\frac{\delta v_{C}}{\delta d} = G_{d 0} \frac{1-\frac{s}{\omega_{z}}}{1 + \frac{s}{Q\omega_{0}} + \frac{s^2}{\omega_{0}^2}}
$$
.

# Modello GAM
Assumendo che la tensione in uscita dal convertitore sia praticamente costante a causa della capacità, si possono trascurare le armoniche di tensione e considerare per semplicità solo la prima armonica di corrente.
Dunque le grandezze in esame saranno: $\langle i_{L} \rangle_{k}, k=[-1,0,1]$ e $\langle v_{L} \rangle_{k},k=0$.
Si valuta il modello dinamico per ogni armonica:
$$
\begin{aligned}
\frac{ \left\langle  di_{L} \right\rangle_{0}}{dt} &= \frac{{\langle  V_{S}\rangle_{0}}}{L} - \frac{\left\langle  v_{C}(1-u) \right\rangle_0}{L}  \\
\frac{ \left\langle  di_{L} \right\rangle_{1}}{dt} &= \frac{{\langle  V_{S}\rangle_{1}}}{L} - \frac{\left\langle  v_{C}(1-u) \right\rangle_1}{L} \\
\frac{ \left\langle  di_{L} \right\rangle_{-1}}{dt} &= \frac{{\langle  V_{S}\rangle_{-1}}}{L} - \frac{\left\langle  v_{C}(1-u) \right\rangle_{-1}}{L}\\
\frac{ \left\langle  dv_{C} \right\rangle_{0}}{dt} &= \frac{{\langle  i_{L}(1-u)\rangle_{0}}}{C} - \frac{\left\langle  v_{C} \right\rangle_0}{RC}
\end{aligned}
$$
In realtà la terza equazione è complessa coniugata della seconda e potrebbe omettersi.
La tensione $V_S$ si assume costante, dunque non ha contenuto armonico:
$\frac{\langle V_{S}\rangle_{0}}{L}=\frac{V_{S}}{L}$ e $\frac{\langle V_{S}\rangle_{1}}{L}=0$.
Si ricorda inoltre la formula della derivata della media:
$$
\left\langle  \frac{d}{dt}  \right\rangle_{k} = \frac{d}{dt}\left\langle  \vec{x}  \right\rangle _{k} + j\omega k\left\langle  \vec{x}  \right\rangle_{k} 
$$
applicata alla seconda equazione, si porta il segno di derivata fuori dall'operatore media:
$$
\frac{d \left\langle  i_{L} \right\rangle_{1}}{dt} = -j\omega \langle i_{L} \rangle_{1}  - \frac{\left\langle  v_{C}(1-u) \right\rangle_1}{L} 
$$
Si è ottenuta un'equazione complessa in due incognite, ottenendo un sistema complessivo di quattro equazioni in quattro incognite:
$$
\left\{
\begin{aligned}
\langle i_{L} \rangle_{0} &= x_{1}\\
\langle i_{L} \rangle_{1} &= x_{2} + jx_{3}\\
\langle v_{C} \rangle_{0} &= x_{4} 
\end{aligned}
\right.
$$
Inoltre va sviluppata la media del prodotto di $v_C$ e $i_L$ per la funzione di controllo $u$, in questo caso è una funzione gradino periodico, di cui si [[media generalizzata funzione gradino|sviluppano le medie]] di ordine $k$ e si ottiene: $\langle u \rangle_{k}=M_{k}+jN_{k}$ e quindi per $k=1\Rightarrow \langle 1-u \rangle_{k}=-(M_{k}+jN_{k})$, dato che la media di ordine 0 è proprio $1-d$.

Si calcolano tutte le medie dei prodotti presenti nel modello:
$$
\begin{aligned}
\langle v_{C} (1-u)\rangle_{0} &= \langle v_{C} \rangle_{0}(1-d) = x_{4}(1-d) \\
\langle v_{C}(1-u) \rangle_{1} &= \langle v_{C} \rangle_{0}\langle (1-u) \rangle_{1} = -\langle v_{C} \rangle_{0}(M_{1}+jN_{1}) = - x_{4}(M_{1}+jN_{1}) \\
\langle i_{L}(1-u) \rangle_{0} &= \langle i_{L} \rangle_{-1}\langle 1-u \rangle_{1} + \langle i_{L} \rangle_{1}\langle 1-u \rangle_{-1} + \langle i_{L} \rangle_{0}(1-d) = \\
&= -2x_{2}M_{1} + (-2x_{3}N_{1}) + x_{1}(1-d)
\end{aligned}
$$
Somma di due numeri complessi coniugati:
$$
\begin{aligned}
\dot{x}\cdot \dot{y} + \check{x}\cdot \check{y} &\Rightarrow (x_{R}+jx_{I})(y_{R}-jy_{I}) + (x_{R}-jx_{I})(y_{R}+jy_{I}) = \\
&= 2 \mathrm{Re}\{\dot{x}\}\mathrm{Re}\{\dot{y}\} + 2 \mathrm{Im}\{\dot{x}\}\mathrm{Im}\{\dot{y}\}
\end{aligned}
$$
Si riorganizzano le equazioni e si riscrive il sistema in forma canonica con il vettore di incognite $x$:
$$
\left\{
\begin{aligned}
\frac{d}{dt} x_{1} &= \frac{V_{S}}{L} - \frac{x_{4}}{L}(1-d) \\
\frac{d}{dt} x_{2} &= \frac{x_{4}}{L}M_{1} + \omega x_{3}\\
\frac{d}{dt}x_{3} &= \frac{x_{4}}{L}N_{1} - \omega x_{2} \\
\frac{d}{dt} x_{4} &= \frac{\left(x_{1}(1-d)-2x_{2}M_{1}-2x_{3}N_{1}\right)}{C} -\frac{x_{4}}{RC}
\end{aligned}
\right.
$$
Risolto il sistema differenziale si può ricostruire la dinamica delle grandezze di stato mediante l'equazione di sintesi armonica:
$$
\begin{aligned}
i_{L}(t) &= \langle i_{L} \rangle_{-1}e^{-j\omega t} + \langle i_{L} \rangle_{0} + \langle i_{L} \rangle_{1}e^{j\omega t} \\
v_{C}(t) &= \langle v_{C} \rangle_{0} 
\end{aligned}
$$
.
# Modello discreto
Si suppone che il convertitore lavori in CCM e sia composto da soli due stati:
$$
\vec{x}_{1} = e^{A_{1}dT_{s}}\vec{x}_{k-1} + A_{1}^{-1} \left[ e^{A_{1}dT_{s}}-\hat{I} \right]B V_{s}
$$
per lo stato successivo:
$$
\vec{x}_{k+1} = \vec{x}_{2}=e^{A_{2}(1-d)T_{s}}\vec{x}_{1} + A_{2}^{-1}\left[e^{A_{2}(1-d)T_{s}}-\hat{I}\right]BV_{s}
$$
La matrice $B$ resta costante per le due configurazioni in questo caso.

Sostituendo:
$$
\vec{x}_{2} = e^{A_{2}(1-d)T_{s}}\left[e^{A_{1}dT}\right]\vec{x}_{k-1} + \left\{ e^{A_{2}(1-d)T_{s}}\cdot A_{1}^{-1} \left[e^{A_{1}dT_{s}}-\hat{I}\right]B + A_{2}^{-1}\left[e^{A_{2}(1-d)T_{s}}-\hat{I}\right]B \right\}V_{s}
$$
generalizzando
$$
\Phi_{k}= \prod_{\rho=1}^{N}e^{A_{\rho}d_{\rho}T_{s}}
$$
è il termine di forma ricorrente mentre
$$
\Gamma_{k}=e^{A_{N}d_{n}T_{s}}\cdot A_{N-1}^{-1}\left[e^{A_{N-1}d_{n-1}T}-\hat{I}\right]B_{N-1} + \sum_{\rho=1}^{N}A_{\rho}^{-1}\left[e^{A_{\rho}d_{\rho}T_{s}}-\hat{I}\right]B_{\rho}
$$
il termine incrementale.

# Sliding mode
Premessa l'analisi svolta per ricavare il [[Controllo sliding mode|controllo sliding mode]] per qualsiasi struttura, questo può essere applicato al boost converter.
## Controllo in corrente
A partire dal [[#Modello affine e bilineare|modello affine]] si sceglie una superficie di sliding, ad esempio $\sigma(x)=x_{1}-x_{1}^*$, dal [[#modello averaged]] si ricava invece
$$
\langle i_{L} \rangle = \frac{\langle v_{C} \rangle }{R(1-D)} \Rightarrow x_{1}^* = \frac{x_{2}^*}{R(1-D^*)}
$$
di conseguenza la grandezza di controllo $D^* = 1-\frac{V_{s}}{x_{2}^*}$.
Sostituendo nella precedente:
$$
x_{1}^* = \frac{{x_{2}^*}^2}{R\cdot V_{s}}
$$
Si calcolano inizialmente le derivate di Lie:
$$
\mathcal{L}_{f}(\sigma) = \frac{V_{s}-x_{2}}{L}\ \ ; \ \ \mathcal{L}_{g}(\sigma) = \frac{x_{2}}{L}
$$
dunque si cerca la legge di controllo equivalente:
$$
\frac{d}{dt}\sigma =  \mathcal{L}_{f}(\sigma) + \mathcal{L}_{g}(\sigma)u = \frac{V_{s}}{L} -\frac{x_{2}}{L} + \frac{x_{2}}{L}u = \frac{V_{s}}{L} - \frac{x_{2}}{L}(1-u)
$$
I valori della funzione di controllo:
$$
\begin{aligned}
&u^+ \text{ se } \sigma(x)>0 \Rightarrow \frac{d\sigma}{dt}< 0 \\
&u^- \text{ se } \sigma(x)<0 \Rightarrow \frac{d\sigma}{dt}> 0 
\end{aligned}
$$
dunque
$$
u = \left.\left.\frac{1}{2}\right[1-\mathrm{{sign}}(\sigma(x))\right]
$$
eseguendo il rapporto tra $-\mathcal{L}_{f}$ ed $\mathcal{L}_{g}$ si ricava la funzione di controllo equivalente:
$$
u_{eq} = \frac{\frac{x_{2}}{L}-\frac{V_{s}}{L}}{\frac{x_{2}}{L}} = 1 - \frac{V_{s}}{x_{2}}
$$
si limita la funzione tra 0 ed 1: $x_{2}\geq Vs$.

Sostituendo $u_{eq}$ in $u$ si ottiene:
$$
\begin{aligned}
\frac{d}{dt}x_{1} &= 0 \text{ è sulla superficie di sliding}\\
\frac{d}{dt}x_{2} &= \frac{x_{1}}{C} - \frac{x_{2}}{RC} - \frac{x_{1}}{C}\left( 1-\frac{V_{s}}{x_{2}} \right)\\
\frac{d}{dt}x_{2} &= \frac{x_{1}^*}{C} \frac{V_{s}}{x_{2}} - \frac{x_{2}}{RC} \\
x_{2} \frac{d}{dt}x_{2} &= \frac{x_{1}^*}{C}\cdot V_{s} - \frac{x_{2}^2}{RC} =\\
&= \frac{1}{2} \frac{d}{dt} (x_{2}^2) = x_{1}^* \frac{V_{s}}{C} - \frac{x_{2}^2}{RC}
\end{aligned}
$$
effettuando una sostituzione
$$
y=x_{2}^2
$$
si ottiene:
$$
\frac{d}{dt}y + \frac{2y}{RC} = 2x_{1}^* \frac{V_{s}}{C}
$$
a regime $y= x_{1}^*RV_{s}$ ovvero 
$$
x_{1}^*=\frac{x_{2}^2}{RV_{s}}
$$
ma ricordando che avevamo già imposto il limite $x_{2}\geq V_{s}$ si ottiene come condizione per la superficie di sliding:
$$
x_{1}^*\geq \frac{V_{s}}{R}
$$

## Controllo in tensione
Si decide di controllare in tensione:
$$
\sigma\left( {x} \right) = x_{2}-x_{2}^*
$$
la derivata di Lie:
$$
\mathcal{L}_{g}(\sigma) = -\frac{x_{1}}{C}
$$
ma non è una soluzione accettabile.

Si potrebbe ipotizzare come superficie di sliding:
$$
\begin{aligned}
\sigma\left( \vec{x} \right) &= -x_{1} + k(x_{2}-x_{2}^*)\\
\sigma\left( \vec{x} \right) &= x_{2} -x_{2}^* + \lambda \frac{d}{dt}x_{2}\\
\sigma\left( \vec{x} \right) &= P^T\cdot\vec{x} = P_{1}x_{1}+P_{2}x_{2}+ \dots + p_{n}x_{n} \\
\sigma\left( \vec{x} \right) &= P_{1}(x_{1}-x_{1}^*) + P_{2}(x_{2}-x_{2}^*)
\end{aligned}
$$
Le soluzioni dovranno essere tutte a parte reale negativa.

La derivata di $f$ invece:
$$
\mathcal{L}_{f}(\sigma) = \frac{x_{1}}{C}-\frac{x_{2}}{RC}
$$
per ricavare la derivata della superficie di sliding:
$$
\begin{aligned}
\frac{d\sigma}{dt} &= \mathcal{L}_{f}(\sigma) + \mathcal{L}_{g}(\sigma)u \\
\frac{d\sigma}{dt} &= \frac{x_{1}}{C} - \frac{x_{2}}{RC} - \frac{x_{1}}{C}u\\
\frac{d\sigma}{dt} &= \frac{x_{1}}{C}(1-u) - \frac{x_{2}}{RC}
\end{aligned}
$$
dunque per $u=1$ 
$$
\frac{d}{dt}\sigma = - \frac{x_{2}}{RC} < 0 
$$
per $u=0$ 
$$
\frac{d}{dt}\sigma = \frac{x_{1}}{C} - \frac{x_{2}}{RC}
$$
dunque per garantire l'attrattività si ha che $x_{1}>\frac{x_{2}}{R}$.
Il calcolo della $u_{eq}$:
$$
u_{eq} = \frac{-\mathcal{L}_{f}(\sigma)}{\mathcal{L}_{g}(\sigma)} = \left( \frac{x_{2}}{RC}-\frac{x_{1}}{C} \right)\cdot \left( -\frac{x_{1}}{C} \right)^{-1} = 1-\frac{x_{2}}{Rx_{1}}
$$
Condizione necessaria e sufficiente affinché il sistema converga alla superficie di sliding:
$$
\begin{aligned}
u_{eq} > 0 &\Rightarrow 1> \frac{x_{2}}{x_{1}R} &\Rightarrow & & x_{1} &> \frac{x_{2}}{R}\\
u_{eq}<0 &\Rightarrow 1-\frac{x_{2}}{Rx_{1}} <1 &\Rightarrow & & \frac{x_{2}}{Rx_{1}}&>0
\end{aligned}
$$
dunque la superficie di sliding plausibile:
$$
\hat{\Sigma} = \left\{ (x_{1},x_{2})\in\Omega:x_{1} > \frac{x_{2}}{R}\ ,\ \begin{aligned}
x_{1}&>0\\
x_{2}&>0
\end{aligned}  \right\}
$$
Se si sostituisce la $u_{eq}$ nel sistema ai valori istantanei si ottengono una condizione di equilibrio
ed una derivata diversa da zero, non lineare.
$$
\frac{d}{dt}x_{1} = \frac{V_{s}}{L} - \frac{x_{2}^*}{L} + \frac{x_{2}^*}{L}\left(  1-\frac{x_{2}^*}{Rx_{1}} \right) = \frac{V_{s}}{L} - \frac{{x_{2}^*}^2}{LRx_{1}}
$$
Si suppone di trovare un punto di equilibrio:
$$
\frac{d}{dt}x_{1}=0 \Rightarrow x_{1} = \frac{{x_{2}^*}^2}{RV_{s}}
$$
L'equazione differenziale è non lineare si può applicare Taylor al primo ordine intorno al punto di equilibrio.
$$
\frac{d}{dt} \delta x_{1} = \left. \frac{\partial h}{\partial x_{1}} \right|_{{\begin{aligned}
x_{1} &= x_{10}\\
x_{2} &= x_{2}^*
\end{aligned}}} \cdot \delta x_{1} + \left.\frac{\partial h}{\partial x_{2}^*}\right|_{\begin{aligned}
x_{1}&=x_{10}\\
x_{2} &= x_{2}^*
\end{aligned}}\cdot \delta x_{2}^*
$$
si calcolano separatamente i due termini:
$$
\frac{\partial h}{\partial x_{1}} = \left.\frac{{x_{2}^*}^2}{RLx_{1^2}}\right|_{\begin{aligned}
x_{10}\ ; \ x_{2}^*
\end{aligned}} = \frac{{x_{2}^*}^2}{RLx_{10}^2} = \frac{{x_{2}^*}^2}{RL \frac{{x_{2}^*}^4}{V_{s}^2R^2}} = \frac{V_{s}^2R}{L{x_{2}^*}^2}
$$

$$
\frac{\partial h}{\partial x_{2}^*} = \left. -\frac{2x_{2}^*}{LRx_{1}} \right|_{x_{10}\ ; \ x_{2}^*} = -\frac{2x_{2}^*}{RL \frac{{x_{2}^*}^2}{V_{s}R}} = -\frac{2V_{s}}{Lx_{2}^*}
$$
Si può ora comporre l'equazione differenziale lineare:
$$
\frac{d}{dt} \delta x_{1} = \frac{V_{s}^2R}{L{x_{2}^*}^2} \delta{x_{1}} - \frac{2V_{s}}{L x_{2}^*} \delta x_{2}^*
$$
Si sfrutta il dominio di Laplace:
$$
\left( s-\frac{V_{s}^2R}{L{x_{2}^*}^2} \right)\delta x_{1} = -\frac{2V_{s}}{L{x_{2}^*}} \delta x_{2}^*
$$
ovvero
$$
\frac{\delta x_{1}}{\delta x_{2}^*} = -\frac{2 \frac{V_{s}}{L{x_{2}^*}}}{\left( s - \frac{V_{s}R}{L{x_{2}^*}} \right)}
$$
Il denominatore si annulla per $s=\frac{V_{s}R}{L{x_{2}^*}}>0$ dunque il polo è a parte reale positiva, dunque la superficie di sliding $x_{2}-x_{2}^*$ non può essere utilizzata.

# Formulazione hamiltoniana
Un diverso formalismo può essere utilizzato per modellare il convertitore boost, come accennato nei [[Richiami di algebra#Sistemi lagrangiani|richiami]].
Si definiscono l'energia cinetica e potenziale del sistema
$$
T_{1} = \frac{1}{2} L \dot{q}_{L}^2\qquad \qquad V_{1} = \frac{1}{2C} q_{C}^2
$$
e la funzione di azione per $u=1$:
$$
\mathcal{F}_{0}(q_{C}) = \frac{1}{2} R \dot{q}_{C}^2
$$
e per $u=0$:
$$
\mathcal{F}_{0}(q_{L,}q_{C}) = \frac{1}{2} R \left[q_{L -} \dot{q}_{C}\right]^2
$$
raggruppando si ottengono le funzioni con i parametri globalmente validi:
$$
\begin{aligned}
&\mathcal{L}(q_{L},q_{C},\dot{q}_{L},\dot{q}_{C}) = \frac{1}{2} L \dot{q}_{L}^2 - \frac{1}{2C} q_{C}^2\\
F(\dot{q}_{L},\dot{q}_{C}) &= \frac{1}{2}R \left[ (1-u) \dot{q}_{L}-\dot{q}_{C} \right]^2 = \\
& = \frac{1}{2}R \left[(1-u)^2\dot{q}_{L}^2 +\dot{q}_{C}^2 - 2(1-u)\dot{q}_{L}\dot{q}_{C} \right]
\end{aligned}
$$
da cui si ricava l'equazione di Lagrange:
$$
\frac{d}{dt}\left( \frac{\partial\mathcal{L}}{\partial \dot{\vec{q}}} \right) - \frac{\partial\mathcal{L}}{\partial \vec{q}} = Q
$$
in questo caso saranno presenti due equazioni come la dimensione di $\vec{q}$ :
$$
\begin{aligned}
L \ddot{q}_{L} &= V_{s} - \frac{1}{2}R \left[(1-u)^2\cdot{2}\dot{q}_{L} -2(1-u) \dot{q}_{C} \right] = \\
&= V_{s} - R(1-u) \left[(1-u) \dot{q}_{L} - \dot{q}_{C}\right]
\end{aligned}
$$
analogamente con $q_{C}$ :
$$
\begin{aligned}
\frac{q_{C}}{C} &= -\frac{1}{2}R \left[2\dot{q}_{C} - 2(1-u)\dot{q}_{L}\right] \\
&= R \left[(1-u)\dot{q}_{L}-\dot{q}_{C}\right]
\end{aligned}
$$
dunque la sua derivata:
$$
\dot{q}_{C} = -\frac{q_{C}}{RC} + (1-u)\dot{q}_{L}
$$
da cui il sistema completo:
$$
\begin{aligned}
L \ddot{q}_{L} &= V_{S} - (1-u) \frac{q_{C}}{C}\\
\dot{q}_{C} &= (1-u) \dot{q}_{L}  \frac{q_{C}}{RC}
\end{aligned}
$$
coincide con il modello dinamico ai valori istantanei.
