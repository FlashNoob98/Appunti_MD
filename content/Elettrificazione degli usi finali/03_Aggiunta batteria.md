Si riprende l'esempio della [[02_Storia e obiettivi della transizione energetica|lezione 2]]
Si suppone che la turbina a gas sia un sistema di cogenerazione ed alimenti anche la potenza termica.

Si considera ora un istante di tempo costante ma si aggiunge un sistema di accumulo, ad esempio elettrico.

Il sistema si trasforma:
$$
\begin{bmatrix}
L_{E} \\L_{H}
\end{bmatrix}=
\begin{bmatrix}
\eta_{t} &\eta_{ge} & 0 \\
0 &  \eta_{gh} & \eta_{h}
\end{bmatrix}\begin{bmatrix}
P_{E} \\ P_{G} \\ P_{H}
\end{bmatrix} + 
\begin{bmatrix}
-P_{in} + P_{out}  \\
0
\end{bmatrix}
$$
la matrice del sistema di accumulo si può anche scrivere come:
$$
\begin{bmatrix}
-P_{in} + P_{out}  \\
0
\end{bmatrix}=
\begin{bmatrix}
-1 & 1  \\ 
0 & 0
\end{bmatrix}
\begin{bmatrix}
P_{in}\\P_{out}
\end{bmatrix}
$$
in questo caso $P_{in}$ e $P_{out}$ sono variabili di stato, dipendono dalla carica del sistema di accumulo, non hanno un ruolo diretto nel calcolo dei costi.

Si vuole realizzare un'unica matrice del sistema con un unico vettore di variabili:
$$
\begin{bmatrix}
L_{E} \\
L_{H}
\end{bmatrix}=
\begin{bmatrix}
\eta_{t} &\eta_{ge} & 0 & -1 & 1 \\
0 &  \eta_{gh} & \eta_{h} & 0 & 0
\end{bmatrix}\begin{bmatrix}
P_{E} \\ P_{G} \\ P_{H} \\P_{in} \\ P_{out}
\end{bmatrix} 
$$

Si ha la seguente funzione di carica della batteria:
$$
C = C_{0} + \left( \eta_{car}P_{in}-\frac{P_{out}}{\eta_{dis}} \right) \Delta t
$$
in forma matriciale:
$$
C = C_{0} + \begin{bmatrix}
0 & 0 & 0 & \eta_{car} & \frac{1}{\eta_{dis}}
\end{bmatrix}\begin{bmatrix}
P_{E} \\ P_{G} \\ P_{H} \\P_{in} \\ P_{out}
\end{bmatrix} \Delta t
$$
il valore di $C$ è compreso tra un valore minimo ed uno massimo che sono parametri della batteria.
$$
C_{min} \leq C \leq C_{max}
$$
dividendo per il $\Delta t$ e cambiando i segni per ottenere un'unica matrice:
$$
\frac{1}{\Delta t}\begin{bmatrix}
C_{min}-C_{0}\\ -C_{max}+C_{0}
\end{bmatrix} \leq
\begin{bmatrix}
0 & 0 & 0 & \eta_{car} & -\frac{1}{\eta_{dis}}\\ 
0 & 0 & 0 & -\eta_{car} & \frac{1}{\eta_{dis}}
\end{bmatrix}
\begin{bmatrix}
P_{E} \\ P_{G} \\ P_{H} \\P_{in} \\ P_{out}
\end{bmatrix}
$$
Queste saranno le matrici $A$ e $b$ ma ```fmincon``` risolve la disuguaglianza $A\cdot x\leq b$ dunque vanno invertiti i segni:
$$
\begin{bmatrix}
0 & 0 & 0 & -\eta_{car} & \frac{1}{\eta_{dis}}\\ 
0 & 0 & 0 & \eta_{car} & -\frac{1}{\eta_{dis}}
\end{bmatrix}
\begin{bmatrix}
P_{E} \\ P_{G} \\ P_{H} \\P_{in} \\ P_{out}
\end{bmatrix} \leq
\frac{1}{\Delta t}\begin{bmatrix}
-C_{min}+C_{0}\\ C_{max}-C_{0}
\end{bmatrix} 
$$
Va aggiunto un vincolo tra la carica e la scarica della batteria.
