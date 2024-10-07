Il problema principale dell'analisi di un convertitore,come è stato già [[Modello dinamico affine nel controllo|anticipato]], è la sua forte non linearità e la conseguente non linearità delle forme d'onda che lo caratterizzano. Uno strumento di analisi può essere la scomposizione in serie di Fourier.

Si dice che la funzione reale definita su $\mathbb{R}$ è di classe $P_T$ se:
- La funzione è periodica di un certo periodo $T \in \mathbb{R}^+$ escluso l'infinito
- È misurabile secondo Lebesgue
- È sommabile su ogni intervallo compatto in $\mathbb{R}$, ovvero esiste finito l'integrale del suo modulo

Per funzioni di questo tipo si può definire il seguente coefficiente complesso:
$$
\dot{C}_k(f)_t = \frac{1}{T}\int_{t-T}^{t}f(\tau)e^{-jk\omega \tau} d\tau
$$
con $k\in\mathbb{Z}$ e di conseguenza può esistere la serie trigonometrica bilatera di Fourier:
$$
f(t) \sim \sum_{k=-\infty}^{+\infty} \dot{C}_k(f)e^{jk\omega t}
$$
con la seguente posizione $\dot{C}_k = \frac{A_k - jB_k}{2}$ si può anche ricavare la forma trigonometrica monolatera:
$$
f(t) = A_0 +\sum_{k=1}^{\infty} A_k\cos(k\omega t) + B_k\sin(k\omega t) = A_0 +\sum_{k=1}^{\infty} S_k\sin(k\omega t + \varphi_k)
$$
con $S_k = \sqrt{A_k^2+B_K^2}\quad \varphi_k = \arctan\frac{A_k}{B_k}$.

Si vuole calcolare il Ripple Factor di una grandezza periodica mediante questi coefficienti, dalla definizione:
$$
R.F.(V) = \sqrt{\frac{\sum_{k=0}^{\infty}V_K^2 - V_0^2}{V_0^2}} = \sqrt{\frac{\sum_{k=1}^{\infty}V_K^2}{V_0^2}}
$$
nel caso si usi la serie monolatera con un singolo coefficiente, allora $V_{k}^2=S_k^2 = 2S_{k_{RMS}}^2$ e di conseguenza il RF(V) si calcola con:
$$
R.F.(V) = \sqrt{\frac{\sum_{k=1}^{\infty}S_k^2}{2S_0^2}} = \sqrt{\frac{\sum_{k=-\infty}^{\infty}S_{k_{RMS}}^2}{4S_0^2}}
$$

Se la funzione contiene punti di discontinuità di prima specie, la serie converge alla semisomma della funzione in quel punto:
$$
\frac{f(t_0^-)-f(t_0^+)}{2} = \sum_{k=-\infty}^{\infty} \dot{C}_k(f)e^{jk\omega t_0}
$$
Una funzione continua in un intervallo compatto è limitata (Teorema di Weierstrass) dunque è sommabile allora esiste l'integrale del suo modulo.
Si prolunga periodicamente una funzione considerata nell'intervallo compatto, ad esempio $[-1,1]$ e "periodarlo" infinitamente, ovvero ripetere la funzione all'infinito.
Si ottiene dunque una funzione periodica a partire da una funzione non periodica, considerando un certo intervallo $T$.
La funzione prolungamento periodico di $x_1(t_1)$ è sommabile e sviluppabile in serie di Fourier.
$$
\left\langle x_1 \right\rangle_k(t) = \frac{1}{T} \int_{t-T}^{t}\dot{x}_1(\tau)e^{-jk\omega \tau }d\tau
$$
Posso ottenere infiniti prolungamenti periodici ad ogni $dt$ variabile, per ogni prolungamento periodico posso calcolare i coefficienti della serie.
È come se si eseguisse la media mobile su ogni armonica, pesati per il termine esponenziale.
Steinmetz ha avuto l'intuizione di trasformare le funzioni nel dominio del tempo a quelle nel dominio della frequenza, considerando la seguente trasformata integrale:
$$
\dot{C}(t) = \frac{2}{T}\int_{0}^{T} f(\tau)e^{- j\omega \tau} d\tau
$$
Applicata ad una grandezza sinusoidale restituisce il "fasore" di questa grandezza, coincide in realtà ad un coefficiente di ordine 1 della serie di Fourier.
Dunque le medie mobili di ordine k prima calcolate possono essere considerati "fasori dinamici" perché variabili nel tempo.

## Analisi armonica del modello bilineare
A partire dal [[Forma bilineare|modello bilineare]] si può applicare il calcolo della media mobile di ordine $k$:
$$
\begin{aligned}
\left\langle  \frac{d}{dt}\vec{x}  \right\rangle_{k} &= \left\langle  A \vec{x}  \right\rangle_{k} + \left\langle  \vec{a}_{0}  \right\rangle_{k} + \sum_{\nu=1}^m \left\langle  \left[ B_{\nu} \vec{x} +b_{\nu}\right]u_{\nu}  \right\rangle_{k} \\
&= A \left\langle  \vec{x}  \right\rangle_{k} + \left\langle  \vec{a}_{0}  \right\rangle_{k} + \sum_{\nu=1}^m \left\langle  B_{\nu} \vec{x}\cdot u_{\nu}  \right\rangle_{k} + \langle b_{\nu}u_{\nu} \rangle_{k} 
\end{aligned}
$$
sfruttando la seguente proprietà
$$
\left\langle  \frac{d}{dt}  \right\rangle_{k} = \frac{d}{dt}\left\langle  \vec{x}  \right\rangle _{k} + j\omega k\left\langle  \vec{x}  \right\rangle_{k}
$$
si ricava la versione finale del modello averaged generalizzato o GAM:
$$
\frac{d}{dt} \left\langle  \vec{x}  \right\rangle_{k} = -j \omega k\left\langle  \vec{x}  \right\rangle_{k} + A \left\langle  \vec{x}  \right\rangle_{k} + \left\langle  \vec{a}_{0}  \right\rangle_{k} +\sum_{\nu=1}^m \left\langle  B_{\nu} \vec{x}\cdot u_{\nu}  \right\rangle_{k} + \langle b_{\nu}u_{\nu} \rangle_{k} 
$$
## Analisi armonica modello bilineare
Si può applicare la stessa analisi al [[Forma bilineare|modello bilineare]]:
$$
\frac{d}{dt}\left\langle  \vec{x}  \right\rangle_{k} = \left\langle  f\left( \vec{x} \right)  \right\rangle_{k} + \left\langle  G\left( \vec{x} \right)  \vec{u}\right\rangle_{k} - j\omega k \left\langle  \vec{x}  \right\rangle_{k}
$$
A partire da entrambi i modelli è possibile ricostruire la dinamica nel tempo del vettore di stato con la seguente formula di sintesi:
$$
\vec{x}(t) = \sum_{k=-\infty}^{+\infty} \left\langle  \vec{x}  \right\rangle_{k} (t) e^{jk\omega t}
$$
La convergenza puntuale nei punti di discontinuità è garantita per ipotesi dall'analisi armonica di Fourier.
Il limite di questo modello è il numero di armoniche calcolabili.

## Media del prodotto
Siano date due serie entrambi convergenti di pari pulsazione, entrambe convergenti in un aperto $\Omega$ di $\mathbb{R}^n$, il prodotto delle due serie segue il
teorema della serie prodotto secondo Cauchy, se entrambe le serie sono convergenti e almeno una delle due serie è assolutamente convergente (converge la serie dei moduli del termine generale), allora si dimostra che il prodotto tra le due serie converge ed è pari alla serie prodotto secondo Cauchy:
$$
x(t) = \sum_{k=-\infty}^{+\infty} \left\langle  \vec{x}  \right\rangle_{k} e^{jk\omega t} \qquad y(t) = \sum_{k=-\infty}^{+\infty} \left\langle  \vec{y}  \right\rangle_{k} e^{jk\omega t}
$$
dunque:
$$
\left\langle  \vec{x}  \right\rangle\cdot \left\langle  \vec{y}  \right\rangle  =\left( \sum x \right)\cdot\left( \sum y \right) = \sum_{k=-\infty}^{+\infty}\dot{c}_{k}
$$
il coefficiente $\dot{c}_k$ calcolato mediante il prodotto di convoluzione delle medie:
$$
\dot{c}_{k} = \sum_{j=-\infty}^{+\infty} \left\langle  \vec{x}  \right\rangle_{k-j} \left\langle  \vec{y}  \right\rangle_{j} = \left\langle  \vec{x} \circledast \vec{y}  \right\rangle_{k}
$$
