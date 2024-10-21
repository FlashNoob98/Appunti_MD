Se si controlla e analizza un convertitore con una [[Schede a microcontrollore|scheda a microcontrollore]], l'osservazione delle grandezze di stato avviene con un certo intervallo di tempo chiamato *periodo di campionamento* $T_s$, solitamente multiplo del periodo di switching dei convertitori.
Considerando ad esempio il [[Modello dinamico alle configurazioni]] di un generico convertitore, questo sarà composto da un insieme discreto di equazioni:
$$
\frac{d}{dt}\vec{x} = \sum_{\rho=1}^{N} \left( A_{\rho}\vec{x} +{B}_{\rho}\vec{V}_{\rho} \right)h_{\rho}
$$
dove $N$ è il numero di configurazioni del sistema.

Si suppone che in ogni periodo di switching il sistema attraversa tutte le configurazioni e dunque esistono dei *cicli* del sistema che si ripetono, in cui le varie configurazioni permangono per tempi diversi, ciò si traduce in:
$$
T_{k}+t_{\rho-1} \leq t < T_{k} + t_{\rho}
$$
dove $T_{k}=kT_{s}$, si ottiene il primo ciclo per $k=0$.
Si possono assumere le $V_\rho$ costanti in ogni ciclo, e dipendenti solo da $k$ perché variano più lentamente rispetto alle correnti dunque la soluzione della $\rho\text{-esima}$ soluzione diventa:
$$
\frac{d}{dt}\vec{x} = \left( A_{\rho}\vec{x}+B_{\rho}\vec{V}_{k} \right)h_{\rho}
$$
Per la continuità delle variabili di stato si può assumere $\vec{x}_{\rho-1}$ come condizione iniziale e usare la formula esponenziale per risolvere l'equazione differenziale:
$$
\vec{x}_{\rho}(t_{\rho}) = e^{A_{\rho}(t_{\rho}-t_{\rho-1})} \vec{x}_{\rho-1} + \int_{t_{\rho-1}}^{t_{\rho}} e^{A(t_{\rho}-\tau)}B_{\rho}\vec{V}_{k}d\tau
$$
Si ricorda la definizione di matrice esponenziale $e^A$:
$$
e^A = \sum_{k=0}^{+\infty} \frac{A^k}{k!} 
$$
Si suppone di campionare lo stato di un sistema ad ogni cambio di configurazione, dunque per un ciclo se ci fossero $N$ configurazioni si avrebbero $N$ campioni.

Si effettua un cambio di variabile:
$$
\lambda = \tau-t_{\rho-1} \Rightarrow \tau=\lambda+t_{\rho-1}\Rightarrow d\tau=d\lambda
$$
Si definisce il duty-ratio $\rho$-esimo $d\rho=\frac{t_{\rho}-t_{\rho-1}}{T_{s}}$ e si sostituisce nella formula esponenziale precedente:
$$
\vec{x_{\rho}}(t_{\rho}) = e^{A_{\rho}d_{\rho}T_{s}}\vec{x}_{\rho-1} + \int_{0}^{d_{\rho}T_{s}}e^{A_{\rho}(d_{\rho}T_{s}-\lambda)}B_{\rho}\vec{V}_{k}d\lambda
$$
Supponendo la variazione di tensione infinitesima tra un ciclo e l'altro si può portare il termine $\vec{V}_{k}$ fuori dall'integrale e si effettua un cambio di variabile:
$$
\eta = d_{\rho}T_{s} -\lambda
$$
$$
\vec{x}_{\rho}=e^{A_{\rho}d_{\rho}T_{s}}\vec{x}_{\rho-1} + \vec{V}_{k}\int_{0}^{d_{\rho}T_{s}} e^{A_{\rho}\eta}B_{\rho}d\eta
$$
Si calcola la soluzione $N$ volte per ogni configurazione e per ogni ciclo $K$:
$$
X_{k+1} = \Phi_{k}\vec{X}_{k} + \Gamma_{k}\vec{V}_{k}
$$
ottenendo il **modello discreto esatto**.

Svolgendo l'integrale:
$$
\int_{0}^{d_{\rho}T_{s}}e^{A_{\rho}\eta}B_{\rho}d \eta = \left[A_{\rho}^{-1}e^{A_{\rho}\eta}\cdot B_{\rho}\right]_{0}^{d_{\rho}T_{s}} = 
A_{\rho}^{-1}\left[e^{A_{\rho}d_{\rho}T_{s}}-\hat{I}\right]B_{\rho}
$$
Sostituendo si ottiene:
$$
\vec{x}_{\rho}=e^{A_{\rho}d_{\rho}T_{s}}\vec{x}_{\rho-1} + A_{\rho}^{-1}\left[e^{A_{\rho}d_{\rho}T_{s}}-\hat{I}\right]B_{\rho} \vec{V}_{k}
$$
