Data una linea con dei carichi distribuiti lungo una linea, si può stimare la caduta di tensione:
$$
\Delta V_{k} = \frac{ \sum_{i=1}^{K} r_{i}l_{i} \sum_{j=i}^{n}P_{j}[\text{pu}]}{V_{n}}
$$
Ad esempio per la prima tratta 
$$
\Delta V_{1} = \frac{r_{1}l_{1}(P_{1}-P_{2}-P_{3})}{V_{n}^2}
$$
e così via:
$$
\Delta V_{2} = \frac{r_{1}l_{1}(P_{1}-P_{2}-P_{3})-r_{2}l_{2}(P_{2}+P_{3})}{V_{n}^2}
$$
e
$$
\Delta V_{3} = \frac{r_{1}l_{1}(P_{1}-P_{2}-P_{3})-r_{2}l_{2}(P_{2}+P_{3})-r_{3}l_{3}(P_{3})}{V_{n}^2}
$$
Tutte queste cadute devono essere contenute in una variazione del 10%.
Dunque si avranno sei differenti relazioni:
$$
\begin{aligned}
1)& \frac{r_{1}l_{1}P_{2}}{V_{n}^2} \leq 0.1 + \frac{r_{1}l_{1}(P_{1}-P_{3})}{V_{n}^2}\\
2) & \frac{-r_{1}l_{1}P_{2}}{V_{n}^2} \leq 0.1 - \frac{r_{1}l_{1}(P_{1}-P_{3})}{V_{n}^2}\\
3) & \frac{(r_{1}l_{1}+r_{2}l_{2})P_{2}}{V_{n}^2} \leq 0.1 + \frac{r_{1}l_{1}(P_{1}-P_{3}) - r_{2}l_{2}P_{3}}{V_{n}^2} \\
4) & -\frac{(r_{1}l_{1}+r_{2}l_{2})P_{2}}{V_{n}^2} \leq 0.1 - \frac{r_{1}l_{1}(P_{1}-P_{3})- r_{2}l_{2}P_{3}}{V_{n}^2} \\
5) & \frac{r_{1}l_{1}+r_{2}l_{2}P_{2}}{V_{n}^2} \leq 0.1 + \frac{r_{1}l_{1}(P_{1}-P_{3})-(r_{2}l_{2}+r_{3}l_{3})P_{3}}{V_{n}^2}\\
6) & -\frac{(r_{1}l_{1}+r_{2}l_{2})P_{2}}{V_{n}^2} \leq 0.1 -\frac{r_{1}l_{1}(P_{1}-P_{2}) + (r_{2}l_{2}+r_{3}l_{3})P_{3}}{V_{n}^2}
\end{aligned}
$$
Si stimano alcuni parametri:
$$
\begin{aligned}
r_{1} &= 0.08 \frac{\Omega}{km} \\
r_{2} &= 0.285 \frac{\Omega}{km} \\
r_{3} &= 0.57 \frac{\Omega}{Km}
\end{aligned}
$$
$$
\begin{aligned}
C_{n} &= 200 kWh \\
C_{min} &= SOC_{min}C_{n}\\
C_{max} &= SOC_{max}C_{n} \\
P_{max_{cogen}} &= 800kW
\end{aligned}
$$
Si suppone che la batteria abbia un numero di cicli stimati pari a 1300, il costo della batteria è di 400€, dunque il costo di scarica è:
$$
C_{s} = \frac{Costo_{BESS}}{N_{cicli}(C_{max}-C_{min})\eta_{s}\eta_{c}}
$$
Il cogeneratore ha una potenza in ingresso gas massima di  800 kW
Il costo del gas è 40 centesimi da mezzanotte alle 5 e dalle 19 alle 7 del giorno dopo ??
altrimenti 1.20 euro (rivedi)

