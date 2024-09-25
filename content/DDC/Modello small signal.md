# Prolungamento per continuità
Per il teorema fondamentale del calcolo integrale, se una funzione è continua, ammette almeno un integrale ed esso è pari al valore assunto dalla primitiva negli estremi di integrazione.
$$
\int_{t-T}^T x_{1(\tau)}d\tau = F(t) - F(t-T)
$$
dunque
$$
\frac{d}{dt}<\vec{x}_{0}>= \frac{1}{T}\frac{d}{dt} (F(t)-F(t-T)) = \frac{1}{T}[x_{1}(t)-x_{1}(t-T)] = \frac{1}{T} \int_{t-T}^T \frac{d}{dt} [x_{1}(\tau)d\tau] = \frac{<dx_{1}>_{0}}{dt}
$$
Una funzione è *generalmente continua* se contiene discontinuità al massimo in un insieme
numerabile di punti, ovvero i punti di discontinuità non sono punti di accumulazione, si può ancora eseguire l'integrale.
Sia $C$ il punto di discontinuità, si può eventualmente prolungare la funzione per continuità se esiste finito il limite dell'integrale quando $\tau$ tende a $C$.
$$
\begin{aligned}
&[t-T,C[ \quad\cup \quad ]C,T] \\
&G(\tau) = G(t-\tau) + \int_{t-\tau}^\tau x_{1}'(\tau)d\tau \quad \forall \tau \in [t-T,C[ 
\end{aligned}
$$
Si calcola la funzione nel punto di discontinuità
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
\frac{1}{T} \int_{t-T}^{t} x_{1}'(\tau) d\tau = \frac{1}{T} [\cancel{G_{1}(C^-)} - G_{1}(t-T) + G_{2}(t) - \cancel{G_{2}(C^+)}] = G_{2}(t) - G_{1}(t-T)
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
\vec{S}_{0} \equiv \left(\left\langle  \vec{x}  \right\rangle_{0} ,\ \vec{d}_{0} \right)
$$
si esegue una piccola variazione sommando un vettore $\vec{h}$ tale che 
$$
\vec{S}_{0} +\vec{h} = \vec{S}_{1} \subset \Omega
$$
ovvero si ha una piccola variazione intorno $\vec{S}_{0}$ contenuta nel dominio iniziale $\Omega$.
