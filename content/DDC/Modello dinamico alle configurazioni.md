Si ipotizzi che i componenti passivi dei convertitori siano costanti durante tutto il periodo di funzionamento, sia **x** il vettore dei componenti di stato, di dimensione *N* dunque si ha:
$$
\frac{d}{dt}\vec{x} =\frac{d}{dt}\begin{bmatrix} i_{L1} \\ i_{L2} \\ \vdots \\ v_{C1} \\ v_{C2} \end{bmatrix} =A_k\vec{x} + B_k\vec{v}
$$
Dove le $A_k$ sono le matrici di stato e $B_k$ le matrici associate ai forzamenti nu.

Sono riportate le configurazioni nel caso del [[Boost converter#Modello dinamico|boost converter]] 

Siano date *N* configurazioni differenti, si ottiene il modello complessivo:

$$
\frac{d}{dt}\vec{x} = \sum_{k=1}^{N} (A_k\vec{x} + B_k\vec{v}_k)h_k
$$
dove $h_k$ è detta funzione di attivazione, indica per quale intervallo di tempo è attiva la configurazione k-esima, dunque è funzione del tempo, ad esempio si riportano le due [[Boost converter#Funzioni di attivazione|funzioni di attivazione del boost]] ma nel caso più generico si ha:
$$
h_{k} = \left\{\begin{aligned}
1 \ & t\in [t_{k},t_{k+1}[\\
0 \ & t\notin [t_{k},t_{k+1}[\\
\end{aligned}
\right.
$$
Il modello è per questo motivo chiamato modello dinamico alle configurazioni.
Il limite di questo modello è la possibilità di applicare criteri dei controlli automatici, non rappresenta un modello reale del sistema in quanto cambia dinamicamente l'intera struttura del sistema. Non espone inoltre in maniera esplicita le [[grandezze di controllo]].

