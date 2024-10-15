Se un sistema evolve con costanti di tempo differenti, nel caso di un convertitore, ad esempio, la tensione in uscita e la corrente nei componenti switching, si può pensare di utilizzare il modello ROAM (Reduced Order Average Model) per studiarne la dinamica.

In tale ipotesi si riduce l'ordine del sistema, in generale possono esistere $r$ variabili di stato con dinamica confrontabile, minore di $n$ l'ordine del sistema; separando le variabili si può studiare un sistema più semplice.

Dunque se $r$ variabili hanno una dinamica veloce, studio prima queste e poi le considero a regime nelle restanti $n-r$ equazioni.
Indicando con $LF$ le variabili *lente* (Low Frequency) e con $HF$ quelle veloci (High Frequency) si può riportare il [[Forma bilineare|modello bilineare]] nella seguente forma:
$$
\left\{
\begin{aligned}
\frac{d}{dt} \vec{x}_{LF} &= A_{11} \vec{x}_{LF} + A_{12}\vec{x}_{HF} +\vec{a}_{0}^{(1)} + \sum_{\nu=1}^{m} \left[ B_{\nu}^{(1,1)}\vec{x}_{LF} + B_{\nu}^{(1,2)}\vec{x}_{HF}+b_{\nu}^{(1)} \right]u_{\nu} \\
\frac{d}{dt} \vec{x}_{HF} &= A_{21} \vec{x}_{LF} + A_{22}\vec{x}_{HF} +\vec{a}_{0}^{(2)} + \sum_{\nu=1}^{m} \left[ B_{\nu}^{(2,1)}\vec{x}_{LF} + B_{\nu}^{(2,2)}\vec{x}_{HF}+b_{\nu}^{(2)} \right]u_{\nu} 
\end{aligned}
\right.
$$
Le dimensioni delle sotto-matrici dipendono da $r$.
Dunque nella risoluzione del sistema si ritengono le $\vec{x}_{LF}$ costanti e pari al valore medio di regime.
Si applica questo modello al [[Boost converter#Modello ROAM|boost converter in DCM]].
