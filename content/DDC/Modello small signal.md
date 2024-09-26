# Prolungamento per continuità
Per il teorema fondamentale del calcolo integrale, se una funzione è continua, ammette almeno un integrale ed esso è pari al valore assunto dalla primitiva negli estremi di integrazione.
$$
\int_{t-T}^T x_{1(\tau)}d\tau = F(t) - F(t-T)
$$
dunque
$$
\frac{d}{dt}\langle \vec{x}_{0} \rangle = \frac{1}{T}\frac{d}{dt} (F(t)-F(t-T)) = \frac{1}{T}[x_{1}(t)-x_{1}(t-T)] = \frac{1}{T} \int_{t-T}^T \frac{d}{dt} [x_{1}(\tau)d\tau] = \frac{\langle dx_{1}\rangle_{0}}{dt}
$$
Una funzione è **generalmente continua** se contiene discontinuità al massimo in un insieme
numerabile di punti, ovvero i punti di discontinuità non sono punti di accumulazione, si può ancora eseguire l'integrale.
Sia $C$ il punto di discontinuità, si può eventualmente prolungare la funzione per continuità se esiste finito il limite dell'integrale quando $\tau$ tende a $C$.
$$
\begin{aligned}
&[t-T,C[ \quad\cup \quad ]C,T] \\
&G(\tau) = G(t-\tau) + \int_{t-\tau}^\tau x_{1}'(\tau)d\tau \quad \forall \tau \in [t-T,C[ 
\end{aligned}
$$
Si calcola la funzione integrale nel punto di discontinuità
$$
G_{1}(C) = G_{1}(C^-) = G_{1}(t-T) + \lim_{ \tau \to C^- } \int_{t-T}^C x_{1}'(\tau) d \tau
$$
Siano $G_1$ e $G_2$ delle primitive, si indica con $\phi_{1}$ e $\phi_2$  le loro rispettive famiglie:
$$
\begin{aligned}
\phi_{1}(\tau) &= G_{1}(\tau) + K_{1}\\
\phi_{2}(\tau) &= G_{2}(\tau) + K_{2}
\end{aligned}
$$
Si scelgono $K_1$ e $K_2$ tali che $G_1(C^-) = G_2(C^+)$ ricavando il seguente integrale:
$$
\frac{1}{T} \int_{t-T}^{t} x_{1}'(\tau) d\tau = \frac{1}{T} \left[\cancel{G_{1}(C^-)} - G_{1}(t-T) + G_{2}(t) - \cancel{G_{2}(C^+)}\right] = G_{2}(t) - G_{1}(t-T)
$$
dato che $G_{1}(C^-) =G_{2}(C^+)$.
La funzione ricavata sarà continua in tutto l'intervallo ma derivabile ovunque eccetto il punto $C$.
# Linearizzazione del [[Modello Averaged|modello averaged]]
Sia data una forma differenziale $F$ appartenente al modello averaged di un convertitore:
$$
\frac{d}{dt} \left<\vec{x}\right>_{0} = f\left(\langle \vec{x} \rangle_{0} \right) + G\left( \langle \vec{x} \rangle_{0} \right)\vec{d} = F\left(\langle \vec{x} \rangle_{0},\vec{d} \right)
$$
essa è definita su un dominio bidimensionale ovvero:
$$
F:\Omega \subset \mathbb{R}^n \times \mathbb{R}^m \to \mathbb{R}^n 
$$
Sia un punto $\vec{S}_{0}$ appartenente al dominio $\Omega$:
$$
\vec{S}_{0} \equiv \left(\left\langle  \vec{x_{0}}  \right\rangle ,\ \vec{d}_{0} \right)
$$
si esegue una piccola variazione sommando un vettore $\vec{h}$ tale che 
$$
\vec{S}_{0} +\vec{h} = \vec{S}_{1} \subset \Omega
$$
ovvero si ha una *piccola* variazione intorno $\vec{S}_{0}$ contenuta nel dominio iniziale $\Omega$. Il vettore $\vec{h}$ dovrà avere le stesse dimensioni di $\vec{S}$ e può essere così generalmente indicato:
$$
\vec{h} = (\langle \delta x_{1} \rangle, \dots, \langle \delta x_{n} \rangle, \delta d_{1} ,\dots, \delta d_{m}    )
$$
Se la funzione $F$ è almeno di classe $\mathbb{C}^2$, non deve essere necessariamente $\mathbb{C}^\infty$, esiste dunque una forma di Taylor nel punto $\vec{S}_{1}$ a partire da $\vec{S}_{0}$, ovvero:
$$
F\left( \vec{S}_{1} \right) = F\left( \vec{S}_{0} +\vec{h}\right) = \left.F\left( \vec{S}_{0} \right) + J_{F}\right|_{\vec{S}_{0}} \cdot \vec{h} + \vec{r}\left( {h} \right)
$$
si è indicato con $J_F$ la matrice *Jacobiana* di $F$ e con $\vec{r}(h)$ il resto di Lagrange.
La matrice Jacobiana è così definita:
$$
J_{F} = \begin{pmatrix}
\frac{\partial f_{1}}{\partial \langle x_{1} \rangle }, & \frac{\partial f_{1}}{\partial \langle x_{2} \rangle }, &\dots, & \frac{\partial f_{1}}{\partial \langle x_{n} \rangle }, & \frac{\partial f_{1}}{\partial  d_{1} }, & \dots, & \frac{\partial f_{1}}{\partial  d_{m} } \\ 
\vdots \\ 
\frac{\partial f_{n}}{\partial \langle x_{1} \rangle }, & \frac{\partial f_{n}}{\partial \langle x_{2} \rangle }, &\dots, & \frac{\partial f_{n}}{\partial \langle x_{n} \rangle }, & \frac{\partial f_{n}}{\partial  d_{1} }, & \dots, & \frac{\partial f_{n}}{\partial  d_{m} }
\end{pmatrix}
$$
ha dimensioni $n\times (n+m)$.

Dunque si analizza lo spostamento dello stato, escludendo il vettore $\vec{d}$:
$$
F\left( \vec{S}_{1} \right) = \frac{d}{dt}\left( \vec{X}_{0}+ \left\langle  \delta \vec{x}  \right\rangle_{0}  \right) =  \frac{d}{dt} \left( \vec{X}_{1} \right)
$$
Se $\vec{S}_{0}$ è un punto di equilibrio stazionario, allora $F\left( \vec{S}_{0} \right)=0 = \frac{d}{dt}\left( \left\langle  \vec{x}  \right\rangle_{0} \right)$ e il limite del resto tende a zero:
$$
\lim_{ ||h|| \to 0 } \frac{r\left(\vec{h} \right)}{\vec{h}} = 0
$$
si può scegliere uno spostamento $\vec{h}$ piccolo, in tali ipotesi la forma di Taylor diventa la seguente:
$$
\left.F\left( \vec{S}_{0} + \vec{h}\right) =  J_{F}\right|_{\vec{S}_{0}} \cdot \vec{h}
$$
Si può dividere la matrice Jacobiana in due sotto-matrici affiancate, la prima $A_s$ quadrata di dimensioni $n\times n$, la seconda $B_s$ di dimensioni $n\times m$, in questo modo si può scomporre l'applicazione dello Jacobiano al vettore $\vec{h}$ degli spostamenti nel seguente modo:
$$
F\left( \vec{S}_{0} + \vec{h}\right) = A_{s} \left\langle  \delta \vec{x}  \right\rangle + B_{s}   \delta \vec{d} = \frac{d}{dt}\left( \vec{X}_{0} + \left\langle  \delta \vec{x}  \right\rangle  \right)
$$
ma $\frac{d}{dt}\vec{X}_{0}=0$ per ipotesi di stazionarietà, dunque
$$
\left.\left. \frac{d}{dt}\left( \left\langle  \delta \vec{x}  \right\rangle  \right) = A_{s}\right|_{\vec{S}_{0}} \left\langle  \delta \vec{x}  \right\rangle + B_{s}\right|_{\vec{S}_{0}}   \delta \vec{d}  
$$
Il modello è lineare, si è sostituita una varietà geometrica differenziabile con un iperpiano tangente al punto di equilibrio.

## Linearizzazione del modello bilineare
Se il modello Averaged è in [[Forma bilineare|forma bilineare]] è allora banale ricavare il modello small signal.
$$
\frac{d}{dt} \left\langle  \vec{x}  \right\rangle_{0} = A \left\langle  \vec{x}  \right\rangle_{0} +\vec{a}_{0}  + \sum_{\nu = 1}^{m} \left[ \vec{B}_{\nu} \left\langle  \vec{x}  \right\rangle_{0} + b_{\nu}  \right]d_{\nu}
$$
dunque le matrici $A_s$ e $B_s$:
$$
\begin{aligned}
A_{s} &= \left. \frac{\partial f}{\partial \left\langle  \vec{x}  \right\rangle }\right|_{\text{eq.}}  = A + \sum_{\nu=1}^m B_{\nu}D_{\nu,\text{eq.}} \\
B_{s} &= \left. \frac{\partial f}{\partial d }\right|_{\text{eq.}}  =\sum_{\nu=1}^n \left[B_{\nu}X_{\text{eq.}}+b_{\nu}\right]
\end{aligned}
$$
dove $D_{\nu,\text{eq.}}$ e $X_{\text{eq.}}$ sono calcolate nel punto di equilibrio.
Questo modello è stato calcolato per il [[Boost converter#Modello small signal|boost converter]]. 
