Nel caso in cui si abbia un guasto dissimmetrico, molto frequente, si deve studiare cosa accade nel circuito con una dissimmetria.
Quando l'impianto non è simmetrico non si può semplificare il modello con un circuito monofase equivalente, per questo motivo si studia l'impianto alle terne di sequenza diretta, inversa e omopolare.

L'impianto può essere rappresentato mediante un sistema di tre conduttori con il neutro, siano le lettere senza apice quelle che indicano i punti di "partenza" e quelle con l'apice i punti di "arrivo", sono presenti sei tensioni differenti rispetto al neutro.

tre correnti che interessano i conduttori e la matrice delle impedenze mutue completano le equazioni del circuito, scritte in forma matriciale:
$$
\begin{bmatrix}
\vec{V_a} \\ \vec{V_b} \\ \vec{V_c}
\end{bmatrix} = 
\begin{bmatrix}
\vec{V_a'} \\ \vec{V_b'} \\ \vec{V_c'}
\end{bmatrix} +
\begin{bmatrix}
\dot{Z}_s & \dot{Z}_m & \dot{Z}_m \\
\dot{Z}_m & \dot{Z}_s & \dot{Z}_m \\
\dot{Z}_m & \dot{Z}_m & \dot{Z}_s
\end{bmatrix}
\cdot
\begin{bmatrix}
\vec{I_a} \\ \vec{I_b} \\ \vec{I_c}
\end{bmatrix}
$$
Le impedenze presentano sia caratteristiche induttive che capacitive, si considera in questo caso per esercizio solo la parte induttiva
$$
\begin{aligned}
\vec{V_1} &= \vec{I_1} j\omega L_1 + \vec{I}_2 j\omega M + \vec{I}_3 j \omega M =
 \vec{I}_1 j \omega L_1 + j \omega M (\vec{I}_2 + \vec{I}_3) =
 I_1 j \omega\frac{(L_1-M)}{L_s}
\end{aligned}
$$
In questo caso si considerano le mutue induzioni uguali per tutte le fasi, ipotesi vera se c'è simmetria nel carico, si è ricavata l'induttanza di servizio $L_s$.
La capacità di servizio è pari alla somma delle capacità più 3 volte quella verso terra.

Le terne di tensione lungo il circuito, dovute al guasto non saranno più simmetriche a causa della dissimmetria del guasto e quindi delle correnti.

La terna di fasori è diretta se le tensioni si susseguono in verso orario e ruotano in verso antiorario, la terna è inversa se le tensioni si susseguono in verso antiorario e ruotano inverso antiorario, è omopolare se non c'è sfasamento tra le tensioni.

Sia $\vec{A}$ una terna di fasori, può essere così rappresentata:
$$
\begin{aligned}
\vec{A}_a &= \vec{A_o} + \vec{A_{ad}} + \vec{A_{ai}}\\
\vec{A}_b &= \vec{A_o} + \vec{A_{bd}} + \vec{A_{bi}}\\
\vec{A}_c &= \vec{A_o} + \vec{A_{cd}} + \vec{A_{ci}}
\end{aligned}
$$
si introduce un fattore di rotazione che anticipa il fasore di 120°: $\alpha = e^{j2\pi/3} = -1/2 + j \sqrt{3}/2$ ed $\alpha^2 = e^{j4\pi/3} = -1/2 - j \sqrt{3}/2$,
si vuole esprimere la terna di fasori reali come la somma dei tre fasori di sequenza.
Si introduce la *matrice di sequenza*:

$$
\begin{bmatrix}
\vec{A}_a \\ \vec{A}_b \\ \vec{A}_c
\end{bmatrix} = 
\begin{bmatrix}
1&1 & 1\\
1 &\alpha^2 &\alpha \\
1 & \alpha & \alpha^2
\end{bmatrix}
\begin{bmatrix}
\vec{A}_0 \\ \vec{A}_d \\ \vec{A}_i
\end{bmatrix}
$$
che moltiplicando le terne di sequenza restituisce i fasori reali.
In realtà noi conosciamo i fasori reali e vogliamo ricavare i fasori delle sequenze, dunque l'inversa della matrice di sequenza:
$$
\begin{bmatrix}
\vec{A}_0 \\ \vec{A}_d \\ \vec{A}_i
\end{bmatrix} = 
\frac{1}{3}
\begin{bmatrix}
1&1 & 1\\
1 &\alpha &\alpha^2 \\
1 & \alpha^2 & \alpha
\end{bmatrix}
\begin{bmatrix}
\vec{A}_a \\ \vec{A}_b \\ \vec{A}_c
\end{bmatrix}
$$
.
Si vuole applicare la rappresentazione alle sequenze al circuito appena presentato, formato da un carico RL equilibrato.
$$
[T_{s}]^{-1} = \begin{pmatrix}
\vec{E}_{1} \\ \vec{E_{2}} \\ \vec{E_{3}}    
\end{pmatrix} -
\begin{pmatrix}
\vec{E}_{1}' \\ \vec{E_{2}}' \\ \vec{E_{3}}'   
\end{pmatrix} = -\frac{1}{3}
\begin{bmatrix}
1 & 1 &1 \\ 
1 & \alpha & \alpha^{2} \\ 
1 & \alpha^2 & \alpha
\end{bmatrix} 
\begin{bmatrix}
Z_{s} & Z_{m} & Z_{m} 
\end{bmatrix}
\begin{bmatrix}
1 & 1 &1 \\ 
1 & \alpha^2 & \alpha  \\
1 & \alpha & \alpha^2
\end{bmatrix} 
\begin{bmatrix}
\vec{I_{0}} \\ \vec{I_{d}} \\ \vec{I_{i}}
\end{bmatrix}
$$
$$
\begin{pmatrix}
\vec{{E}_{1}} \\ \vec{E_{2}} \\ \vec{E_{3}}  \end{pmatrix} -
\begin{pmatrix}
\vec{E}_{1}' \\ \vec{E_{2}}' \\ \vec{E_{3}}'   
\end{pmatrix} = 
\frac{1}{3}\begin{bmatrix}
\dot{Z}_{s} + 2\dot{Z}_{m} & \dot{Z}_{s}+2 Z_{m} & \dot{Z}_{s} + 2Z_{m}\\ 
(\alpha + \alpha^2)Z_{M} + Z_{s}
\end{bmatrix}
$$
Continuando lo svolgimento
$$
\begin{pmatrix}
\vec{E}_{0} \\ \vec{E_{d}} \\ \vec{E_{i}}    
\end{pmatrix} -
\begin{pmatrix}
\vec{E}_{0}' \\ \vec{E_{d}}' \\ \vec{E_{i}}'   
\end{pmatrix} =
\begin{bmatrix}
Z_{s}+2Z_{m} & 0 & 0 \\ 
0 & Z_{s} - Z_{m} & 0  \\
0 & 0 & Z_{s} - Z_{m}
\end{bmatrix}
\begin{bmatrix}
\vec{I_{0}} \\ \vec{I_{d}} \\ \vec{I_{i}}
\end{bmatrix}
$$
Si sono disaccoppiate le tre terne e si possono ricavare i tre circuiti equivalenti, va poi calcolato il tipo di collegamento tra questi tre circuiti a seconda della tipologia di guasto.
Il forzamento ha solitamente solo la componente diretta, si considera il forzamento reale che è solitamente una terna simmetrica diretta.

## Guasto trifase a terra
Si utilizzano in questo caso le terne di sequenza per studiare il corto circuito trifase a terra.

## Guasto monofase a terra
Delle tre fasi della linea, solo una fase è guasta verso terra, si vuole capire come collegare i tre circuiti alle sequenze. Si considera la fase $\vec{E_{1}}=0$ a terra, dunque
$$
\begin{bmatrix}
\vec{E_{1}} \\ \vec{E_{2}}\\ \vec{E_{3}}
\end{bmatrix} = 
\begin{bmatrix}
1 & 1&1\\ 1 &\alpha^2 & \alpha \\ 1 & \alpha & \alpha^2
\end{bmatrix}
\begin{bmatrix}
\vec{E_{0}} \\ \vec{E_{d}} \\ \vec{E_{i}}
\end{bmatrix}
$$
Dunque la prima riga è nulla. Si riprende la trasformazione inversa rispetto alle correnti, sapendo che c'è corrente solo nel primo conduttore,
$\vec{I_{1}}=\vec{I_{g}},\vec{I_{2}}=0,\vec{I_{3}}=0$ ma rispetto alle terne di sequenza le tre correnti sono uguali, dunque i tre circuiti sono in serie.
$$
\begin{bmatrix}
I_{0} \\ I_{d} \\ I_{i}
\end{bmatrix} = \frac{1}{3}
\begin{bmatrix}
1 & 1 & 1 \\ 1 & \alpha & \alpha^2
\end{bmatrix}
\begin{bmatrix}
I_{g} \\ 0 \\ 0
\end{bmatrix}
$$

$$
\frac{\vec{I_{g}}}{3} = \frac{\vec{E_{d}^0}}{Z_{d}+Z_{i}+Z_{0}}
$$
## Guasto monofase mediante impedenza
In questo caso è presente una impedenza di guasto $Z_g$, dunque sarà presente una tensione $E_1=Z_{g}I_{g}$ pari alla impedenza di guasto moltiplicata la corrente di guasto, valgono ancora le considerazioni precedenti sulla serie tra i circuiti di guasto a causa della relazione sulle correnti. Si posiziona l'impedenza di guasto (moltiplicata per 3) sul ramo comune tra i tre circuiti, affinché si rispetti la condizione:
$$
\cancel{3}Z_{g}\frac{I_{g}}{\cancel{3}} = E_{d}+E_{i}+E_{0} = E_{1}
$$
.
