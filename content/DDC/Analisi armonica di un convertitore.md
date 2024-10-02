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

Se la funzione contiene punti di discontinuità di prima specie, la serie converge alla semisomma 
della funzione in quel punto:
$$
\frac{f(t_0^-)-f(t_0^+)}{2} = \sum_{k=-\infty}^{\infty} \dot{C}_k(f)e^{jk\omega t_0}
$$
Una funzione continua in un intervallo compatto è limitata (Teorema di Weierstrass) dunque è sommabile
allora esiste l'integrale del suo modulo.
Si prolunga periodicamente una funzione considerata nell'intervallo compatto, ad esempio
$[-1,1]$ e "periodarlo" infinitamente, ovvero ripetere la funzione all'infinito.
Si ottiene dunque una funzione periodica a partire da una funzione non periodica, considerando
un certo intervallo $T$.
La funzione prolungamento periodico di $x_1(t_1)$ è sommabile e sviluppabile in serie di 
Fourier.
$$
\left\langle x_1 \right\rangle_k(t) = \frac{1}{T} \int_{t-T}^{t}\dot{x}_1(\tau)e^{-jk\omega \tau }d\tau
$$
Posso ottenere infiniti prolungamenti periodici ad ogni $dt$ variabile, per ogni prolungamento
periodico posso calcolare i coefficienti della serie.
È come se si eseguisse la media mobile su ogni armonica, pesati per il termine esponenziale.
Steinmetz ha avuto l'intuizione di trasformare le funzioni nel dominio del tempo a quelle nel
dominio della frequenza, considerando la seguente trasformata integrale:
$$
\dot{C}(t) = \frac{2}{T}\int_{0}^{T} f(\tau)e^{- j\omega \tau} d\tau
$$
Applicata ad una grandezza sinusoidale restituisce il "fasore" di questa grandezza,
coincide in realtà ad un coefficiente di ordine 1 della serie di Fourier.
Dunque le medie mobili di ordine k prima calcolate possono essere considerati "fasori dinamici"
perché variabili nel tempo.