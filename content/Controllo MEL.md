Controllo a minimizzazione delle perdite.

Convertitore back-back a doppio stadio, su una macchina asincrona.
L'algoritmo di alimentazione implementa come funzione ausiliaria la minimizzazione delle perdite.

Ci si pone sempre nel riferimento solidale al flusso di rotore
Si esplicitano le perdite:
$$
P_{\text{loss}} = 3R_{s}\left(I_{ds}^2+I_{qs}^2\right) + 3R_{r}\left(I_{dr}^2+I_{qr}^2\right) + c_{\text{Fe}}\omega_{e}^2\psi_{m}^2 + c_{\text{str}}\omega_{e}^2
\left(I_{dr}^2+I_{qr}^2\right)$$
Si possono riassumere con due coefficienti:
$$
P_{\text{loss}} = aI_{ds}^2 + bI_{qs}^2
$$
Con 
$$
a = 3R_{s} + c_{\text{Fe}}\omega_{e}^2L_{m}^2
$$
e 
$$
b = \left[ 3R_{s} + 3R_{r} \frac{L_{m}^2}{L_{r}^2} \right] + \left[c_{\text{Fe}}\left( L_{m}-\frac{L_{m}^2}{L_{r}} \right)^2 + c_{\text{str}} \frac{L_{m}^2}{L_{r}^2}\right]\omega_{e}^2
$$
Si vuole minimizzare la funzione rispetto alla corrente $I_{ds}$.
Si impone poi che la variazione della coppia sia solo funzione della corrente in quadratura, e non dell'asse diretto, dunque
$$
\left.\frac{\partial P_{\text{loss}}}{\partial I_{ds}}\right|_{\omega_{c}=\text{const}} =0 \Rightarrow
aI_{ds}+bI_{ds}\frac{\partial I_{qs}}{\partial I_{ds}} =0
$$
si vuole estrarre la massima potenza meccanica dalla turbina, non cambia la velocità di riferimento nell'algoritmo di controllo ma i valori delle correnti.

$$
\left.\frac{\partial T_{e}}{\partial I_{ds}}\right|_{\omega_{c}=\text{const}}  = 0 \Rightarrow T_{e}=\frac{3}{2}p \frac{L_{m^2}}{L_{r}}I_{qs}I_{ds} \Rightarrow \frac{\partial I_{qs}}{\partial I_{ds}} = -\frac{I_{qs}}{I_{ds}}
$$
Si sostituisce l'ultima condizione nella precedente relazione ottenendo:
$$
aI_{ds}^2 - bI_{qs}^2=0 \Rightarrow  \left( \frac{I_{ds}}{I_{qs}} \right) = \sqrt{ \frac{b}{a} }
$$
Dunque si può ricavare la $I_{ds,\text{opt}}$ ottimale:
$$
I_{ds,\text{opt}} = |I_{qs}| G_{d} \sqrt{ \frac{1+T_{a}^2\omega_{e}^2}{1+T_{b}^2\omega_{e}^2} }
$$
con la funzione $G_{d}$:
$$
G_{d} = \sqrt{ 1+ \frac{R_{r}L_{m}^2}{R_{s}L_{r}^2} }
$$
e $T_a$:
$$
T_{a} = L_{m} \sqrt{ \frac{c_{\text{Fe}}(L_{r}-L_{m})^2+c_{\text{str}}}{3(R_{s}L_{r}^2 + R_{r}L_{m}^2)} }
$$
il coefficiente $T_b$:
$$
T_{b} = L_{m}\sqrt{ \frac{c_{\text{Fe}}}{3R_{s}} }
$$

Per dimensionare il controllore si esprime la coppia della turbina in funzione della sua velocità ottimale:
$$
T_{\omega_{t},\text{opt}} = \rho \pi\dots
$$
Dunque per ogni valore di velocità si ha il momento della coppia, a partire da questa si ottiene l'espressione della corrente $I_{qs,\text{opt}}$:
$$
I_{qs,\text{opt}} = G_{q}\frac{\omega_{r,\text{opt}}^2}{I_{ds}}
$$
Controllando la velocità della macchina si controlla di fatto la coppia, a meno di conoscere il valore di $I_{ds}$, determinata con la conoscenza di $G_{q}$ e utilizzando l'equazione di minima perdita.
$$
I_{ds,\text{opt}} = \omega_{r}\sqrt{ G_{d}G_{q} }\left[ \frac{1+T_{a}^2\omega_{e}^2}{1+T_{b}^2\omega_{e}^2} \right]^{1/4}
$$
In ogni caso il controllo della corrente $I_{ds}$ non può far aumentare il flusso oltre il valore nominale, per questo motivo viene saturata.
