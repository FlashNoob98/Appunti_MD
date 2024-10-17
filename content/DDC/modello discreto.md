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
