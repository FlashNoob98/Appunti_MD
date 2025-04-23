Si può considerare un'unica variabile per valutare lo stato della batteria, $P_{bess}$ che se maggiore o minore di zero comporta una differente variazione del $SOC$ ovvero:
$$
\begin{aligned}
P_{bess}\geq{0} & \\
SOC_{i} &= SOC_{i-1} + \eta_{C}P_{bess} \leq SOC_{MAX} \\
P_{bess}<{0} & \\
SOC_{i} &= SOC_{i-1} + \frac{P_{bess}}{\eta_{D}} \geq SOC_{MIN}
\end{aligned}
$$
La matrice $A_{eq}$ diventa:
$$
\begin{bmatrix}
\eta_{e} & \eta_{ge} & -1 & 0 \\
0 & \eta_{gh} & 0 & -1 
\end{bmatrix}
$$
Posso creare una function non lineare in cui valuto il segno di $P_{bess}$ e decido come aggiornare il SOC.

Ovviamente sarà $P_{bess}((i-{1})\cdot4+3)$ per indicare sempre il terzo elemento del vettore di potenze ad ogni iterazione mentre il vettore $C$ conterrà i due valori per l'accumulo termico e quello elettrico.

# Analisi HUB differenti con interazione linee
Si hanno tre centri industriali con carico elettrico.
Il primo e il terzo hanno anche un carico termico.
Il secondo ha anche un carico gas.
$$
\begin{aligned}
L_{e_{1}} &= \eta_{e}P_{e_{1}}+P_{PV_{1}}\\
L_{e_{2}} &= \eta_{e}P_{e_{2}} + P_{PV_{2}} + \eta_{CHP_{2}}P_{g_{2}}\\
L_{e_{3}} &= \eta_{e} P_{e_{3}} + P_{PV_{3}} \\
P_{PV} &= P_{PV_{1}} + P_{PV_{2}} + P_{PV_{3}} \\
L_{h_{1}} &= \eta_{CHP_{1}}P_{g_{1}} + \eta_{CHP_{2}}P_{g_{2}} \\
L_{g_{2}}&=  \bar{P}_{g_{2}} \\
0 & \leq P_{g_{2}} + \bar{P}_{g_{2}} \leq P_{g_{max}}
\end{aligned}
$$


