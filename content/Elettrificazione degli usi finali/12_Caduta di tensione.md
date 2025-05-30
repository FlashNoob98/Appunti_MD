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



## Esempio con due energy Hub
Matrice A:
$$
A=
\begin{bmatrix}
-\frac{r_{1}l_{1}}{V_{n}^2} & -\frac{r_{1}l_{1}}{V_{n}^2} &0 & 0  \\
\frac{r_{1}l_{1}}{V_{n}^2} & \frac{r_{1}l_{1}}{V_{n}^2} &0 & 0
\end{bmatrix}
$$
per semplicità non si riportano tutti gli elementi, il vettore $b$ sarà dunque:
$$
b=\begin{bmatrix}
0.1- \frac{r_{1}l_{1}P_{1}}{V_{n}^2}  \\
0.1+ \frac{r_{1}l_{1}P_{1}}{V_{n}^2} 
\end{bmatrix}
$$
![[energy_hub_1.png]]
L'hub 1 è quello mostrato in foto ma il carico $L_{e_{2}}$ è connesso alla linea a monte dunque con $L_{e_{1}}$.
Il secondo energy Hub è invece composto solo dalla pare elettrica del primo, senza collegamento gas.

Tra i due energy hub si collega un ulteriore carico $L_{5}$ variabile, da prendere dai dati storici.

$\frac{\Omega}{km}$ della linea: 2.08 impedenza vista rispetto al trasformatore a monte della linea, lunga 1km.
Impedenza della linea in cavo 0.57 $\frac{\Omega}{km}$ mentre quella aerea 0.08 $\frac{\Omega}{km}$.
una 3 km e l'altra 5 km.

Per il cogeneratore si hanno valori di efficienza elettrica pari a 0.3 e termica pari a 0.6.

Limite potenza gas: 150 kW.

Si inserisce una variabile $\Delta L_{e_{2}}\leq {1}0\%L_{e}$.
Per i fotovoltaici si vedono i dati nel file su teams.

La capacità della batteria: 50 kWh, potenza massima in carica e scarica 25kW.
SoC minimo 15%, massimo 100%.
Rendimento carica 0.95, scarica 0.90.

Limite massimo potenza termica 85kW.

Fine traccia 1

I dati delle fonti rinnovabili le prendi dal file "solar_panel_325"
## Traccia 2

Per il bess nel primo hub soc min 15 % e soc max 100%

Il secondo hub resta come quello in traccia.
Si collega il cogeneratore lato elettrico alla linea a monte, dove non saranno più presenti il sistema di accumulo e il fotovoltaico.
Il cogeneratore è invece connesso ad un sistema di accumulo termico.
0.65 i rendimenti dell'accumulo termico.
Si aggiunge un Delta Lg con un coso di 2eur/kwh

## Terza traccia
Primo hub identico

Per ogni colonna relativa ad un profilo termico è presente un COP variabile della pompa di calore.

## Traccia quattro
Rendimento trasformatore 0.9909
