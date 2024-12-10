Si segue una trattazione simile al [[Ponte monofase a tiristori|ponte monofase]] per la stella trifase, è presente un'induttanza di commutazione $L_{c}$ su ogni linea, un'induttanza $L_{d}$ sul carico.

Per la $k$-esima fase vale la seguente relazione:
$$
(L+Lc) \frac{d}{dt}i_{D} = v_{k0} - Ri_{D}
$$
dunque complessivamente in un periodo
$$
\frac{d}{dt}i_{D} = \frac{v_{10}S_{1}+v_{20}S_{2}+v_{30}S_{3}-Ri_{D}}{L+L_{c}}
$$
Con l'ipotesi di complementarietà si avrà uno spazio di controllo di ordine 2.
In DCM saranno presenti delle commutazioni, ad esempio nella commutazione dalla fase 1 alla fase 3 si ricava la seguente equazione differenziale, somma dei due contributi:
$$
\begin{aligned}
V_{3}-L_{c} \frac{d}{dt}i_{3} - L \frac{di_{D}}{dt}-Ri_{D}&=0\\ &+ \\
V_{1}-L_{c} \frac{d}{dt}i_{1} - L \frac{di_{D}}{dt}-Ri_{D}&=0 \\ &= \\
V_{3}+V_{1}-L_{c}\frac{d}{dt}i_{D} - 2L \frac{d}{dt}i_{D} -2Ri_{D} &=0
\end{aligned}
$$
Dunque dalla LKC si ricava:
$$
i_{3}+i_{1} = i_{D} \Rightarrow di_{3} + di_{1} = di_{D}
$$
.
Si vuole calcolare la commutazione tra tutte e tre le gambe per ottenere un modello generico:
$$
\frac{d}{dt} i_{D} = \frac{(S_{1}-u_{1})v_{1}+(S_{2}-u_{2})v_{2}+(S_{3}-u_{3})v_{3}-Ri_{D}[S_{1}-u_{1}+S_{2}-u_{2}+S_{3}-u_{3}]}{L+L_{c}}
$$
ricordando che si deve sempre rispettare $S_{1}+S_{2}+S_{3}=1$ si può raccogliere il secondo termine:
$$
\frac{d}{dt} i_{D} = \frac{(S_{1}-u_{1})v_{1}+(S_{2}-u_{2})v_{2}+(S_{3}-u_{3})v_{3}-Ri_{D}[1-(u_{1}+u_{2}+u_{3})]}{L+L_{c}}
$$
con il comando di impulso, ad esempio $S_{1}$ così imposto:
$$
S_{1} = \left\{\begin{aligned}
1 \quad & \forall t \in \left[\alpha, \frac{2\pi}{3}+\alpha \right] \frac{1}{\omega}\\
0  \quad &  \forall t \notin \left[\alpha, \frac{2\pi}{3}+\alpha \right] \frac{1}{\omega}
\end{aligned}\right.
$$
e
$$
u_{1} = \left\{\begin{aligned}
1  \quad & T_{3}\& T_{1} \text{ durante commutazione}\\
0 \quad & \text{altrove}
\end{aligned}
\right.
$$
Durante la commutazione la tensione in uscita sarà pari alla semisomma delle due tensioni che alimentano la maglia di commutazione:
$$
\frac{d}{dt}i_{D} = \frac{\frac{v_{1}+v_{3}}{2}}{\frac{L_{c}}{2}+L} - \frac{R}{\frac{L_{c}}{2}+L}i_{D}
$$
Sommando le semitensioni alle precedenti equazioni si ottiene il modello globalmente valido del convertitore:
$$
\begin{aligned}
\frac{d}{dt}i_{D} &= \frac{(S_{1}-u_{1})v_{1}+(S_{2}-u_{2})v_{2}+(S_{3}-u_{3})v_{3}-Ri_{D}[1-(u_{1}+u_{2}+u_{3})]}{L+L_{c}}+ \\
&+ \frac{(v_{1}+v_{3})u_{1} + (v_{1}+v_{2})u_{2} + (v_{2}+v_{3})u_{3} - 2Ri_{D}(u_{1}+u_{2}+u_{3})}{2L+L_{c}}
\end{aligned}
$$

Si definiscono le correnti di commutazione $i_{C_{k}}$:
$$
\begin{aligned}
\frac{d}{dt}i_{C_{1}} &= \frac{v_{3}-v_{1}}{L_{c}}\\
\frac{d}{dt}i_{C_{2}} &= \frac{v_{1}-v_{2}}{L_{c}} \\
\frac{d}{dt}i_{C_{3}} &= \frac{v_{2}-v_{3}}{L_{c}}
\end{aligned}
$$
che permettono di completare il modello dinamico.

Formalizzando per una singola corrente:
$$
\begin{aligned}
\frac{d}{dt}i_{1} &= \frac{1}{2}\left[ \frac{v_{1}+v_{3}}{2L+L_{c}} -\frac{2Ri_{D}}{2L+L_{c}} - \frac{v_{3}-v_{1}}{2L+L_{c}} \right]u_{1} + \\
&+ \frac{(S_{1}-u_{1})v_{1} - Ri_{D}(S_{1}-u_{1})}{L+L_{c}} + \\
&+ \frac{1}{2}\left[ \frac{v_{1}+v_{2}-2Ri_{D}}{2L+L_{c}}+ \frac{v_{1}-v_{2}}{L_{c}} \right]u_{2}
\end{aligned}
$$
Dove il primo termine rappresenta la commutazione da $T_{3}$ a $T_{1}$ovvero il turn-on del componente $T_{1}$, il secondo termine modella la dinamica durante la conduzione pura.
Il  terzo modella la dinamica di turn-off da $T_{1}$ a $T_{2}$.
Sviluppato diventa:
$$
\begin{aligned}
\frac{d}{dt}i_{1} &=\frac{v_{1}(S_{1}-u_{1})}{L_{c}+L} - \frac{R(S_{1}-u_{1})i_{D}}{L_{c}+L} + \\
+& \frac{1}{L_{c}(2L + L_{c})}\cdot [(L_{c}+L)v_{1}(u_{1}+u_{2}) - Lv_{2}u_{2}-Lv_{3}u_{1}]-\\
-& \frac{Ri_{D}}{L_{c}+2L}(u_{1}+u_{2})
\end{aligned}
$$
.