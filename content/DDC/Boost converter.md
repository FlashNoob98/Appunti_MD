Qui si presenteranno i modelli del boost converter
# Modello dinamico
Se si ipotizza la conduzione continua (CCM) si hanno due stati del convertitore se
l'istante di tempo $t$ è maggiore o minore di $t_{on}$, considerato come il tempo di conduzione del dispositivo dinamico.
## $t <  t_{on}$
Si presenta il modello dinamico del boost converter
![Immagine](https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Boost_conventions.svg/1920px-Boost_conventions.svg.png)
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
Si ricava il modello small signal a partire dall'averaged per il boost converter.
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
