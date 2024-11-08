Molt generatori eolici presentano una macchina elettrica asincrona, con lo statore connesso rigidamente alla rete e sul rotore sono presenti tre spazzolo che permettono il collegamento ad un convertitore "back-to-back",  in questo modo il convertitore è dimensionato non per tutta la potenza generata ma solo per una potenza di scorrimento.

Se fosse una macchina asincrona con rotore in corto circuito, funzionerebbe da generatore solo con velocità superiori al sincronismo, la regolazione di velocità sarebbe comunque limitata.

Alimentando il rotore si ha un sistema chiamato **Double fed induction generator** o (DFIG), si può avere generazione di energia anche con scorrimenti inferiori ad 1.

Si riporta l'equazione di statore:
$$
\vec{V}_{s} = -R_{s}\vec{i}_{s} - L_{s} \frac{d}{dt}\vec{i}_{s} + L_{m} \frac{d}{dt} \vec{i}_{r}^{(s)}
$$
dove 
$$
\vec{i}_{r}^{(s)} = \vec{i}_{r} \frac{N_{s}}{N_{r}} e^{jp\theta_{r}}
$$
Per il rotore invece non sarà più chiuso in corto circuito:
$$
\vec{V}_{r}^s = R_{r}\vec{i}_{r}^s + L_{r} \frac{d}{dt}\vec{i}_{r}^s - jp\omega _{r} L_{r}\vec{i}_{r}^s -L_{m} \frac{d}{dt}\vec{i}_{s} + jp\omega_{r}L_{m}\vec{i}_{s}
$$
Si aggiunge l'equazione della coppia:
$$
M_{e} = -\frac{3}{2} p \mathrm{Im}\left( {\vec{I}_{s}}\check{\vec{\Phi}}_{s} \right)
$$

L'equazione dello statore ai fasori:
$$
\vec{V}_{s} = -R_{s}\vec{I}_{s} - j\omega_{s}L_{s}\vec{I}_{s} + j\omega L_{m}\vec{I}_{r}^s
$$
il rotore:
$$
\vec{V}_{r}^s e^{j\omega st} = R_{r}\vec{I}_{r}^se^{j\omega st} + j\omega_{s}L_{r}\vec{I}_{r}e^{j\omega st} - jp\omega_{r}L_{r}\vec{I}_{r} e^{j\omega st} - j\omega_{s}L_{m}\vec{I}_{s} e^{j\omega st} + jp\omega_{r}L_{m}\vec{I}_{s}e^{j\omega st}
$$
Si definisce la pulsazione di scorrimento:
$$
(\omega_{s}-p\omega_{r}) = \omega_{s} = s\omega_{s}
$$
Si semplifica l'equazione di rotore:
$$
\vec{V}_{r}^s = R_{r}\vec{I}_{r}^s + js\omega_{s}L_{r}\vec{I}_{r}^s - js\omega_{s}L_{m}\vec{I}_{s}
$$
Si divide per lo scorrimento per ottenere due equazioni isofrequenziali:
$$
\left\{
\begin{aligned}
\vec{V}_{s} &= -R_{s}\vec{I}_{s} - j\omega_{s}L_{s}\vec{I}_{s} + j\omega L_{m}\vec{I}_{r}^s \\
\frac{\vec{V}_{r}^s}{s} &= \frac{R_{r}\vec{I}_{r}^s}{s} + j\omega_{s}L_{r}\vec{I}_{r}^s - j\omega_{s}L_{m}\vec{I}_{s}
\end{aligned}
\right.
$$

Si calcola la coppia in regime sinusoidale:
$$
M_{e} = -\frac{3}{2}p\mathrm{Im}\left\{ \vec{i}_{s} \check{\vec{\Phi}}_{s} \right\} = -\frac{3}{2}p L_{m} \mathrm{Im}\left\{ \vec{i}_{s}\check{\vec{i}_{r}^s} \right\} = -\frac{3}{2}pL_{m} \mathrm{Im}\left\{ \vec{I}_{s}\check{\vec{I}_{r}^s} \right\}
$$
A regime si sostituiscono i fasori.

$$
\vec{I}_{s} = \left[ \frac{\vec{V}_{r}^s}{s} - \left( \frac{R_{r}}{s}+jX_{r} \right)\vec{I}_{r}^s \right]\cdot \frac{j}{X_{m}}
$$
Si sostituisce nell'espressione della coppia:
$$
M_{e} = -\frac{3}{2} \frac{p}{\omega s} \mathrm{Im}\left\{ \left[ \frac{\vec{V}_{r}^s}{s} \check{\vec{I}_{r}^s} -\left( \frac{R_{r}}{s}+jX_{r} \right)\vec{I}_{r}^s\check{I_{r}^s}  \right]j \right\}
$$
si ottiene:
$$
M_{e} = \frac{3}{2} \frac{p}{s\omega_{s}} \mathrm{Re}\left\{ R_{r}{I_{r}^s}^2- \vec{V}_{r}^s\check{\vec{I}_{r}^s} \right\}
$$
Il termine di rotore aggiuntivo può rendere la coppia negativa anche per scorrimenti positivi, quel termine è proprio la potenza attiva iniettata nel rotore.
Posso traslare la curva caratteristica del motore, ricercando sempre la condizione di ipersincornismo e generare energia.

Equazioni del circuito equivalente:
$$
\frac{\vec{V}_{r}^{s}}{s} = - \left( \frac{R_{r}}{s} + jX_{\sigma r} \right)\vec{I}_{r} + jX_{m} \left( \vec{I}_{r}^s -\vec{I}_{s} \right)
$$
Si separano le equazioni in parte reale e immaginaria, si sceglie un riferimento di fase assoluto, in questo caso su $\vec{V}_s$:
$$
\left\{\begin{aligned}
V_{sd} &= V_{s} = -R_{s}I_{sd} + X_{s}I_{sq} - X_{m}I_{rq}\\
V_{sq} &= 0 = -R_{s}I_{sq} - X_{s}I_{sd} + X_{m}I_{rd}\\
\frac{V_{rd}}{s} &= \frac{R_{r}}{s} I_{rd} - X_{r}I_{rq} + X_{m} I_{sq} \\
\frac{V_{rq}}{s} &= \frac{R_{r}}{s} I_{rq} + X_{r}I_{rd} - X_{m}I_{sd}
\end{aligned}
\right.
$$
Una classica approssimazione è trascurare la resistenza di statore:
$$
\left\{\begin{aligned}
V_{sd} &= V_{s} =  X_{s}I_{sq} - X_{m}I_{rq} = -\omega_{s} \vec{\Phi}_{sq}\\
V_{sq} &= 0 = - X_{s}I_{sd} + X_{m}I_{rd} = \omega_{s}\vec{\Phi}_{sd}\\
\frac{V_{rd}}{s} &= \frac{R_{r}}{s} I_{rd} - X_{r}I_{rq} + X_{m} I_{sq} \\
\frac{V_{rq}}{s} &= \frac{R_{r}}{s} I_{rq} + X_{r}I_{rd} - X_{m}I_{sd}
\end{aligned}
\right.
$$
Dunque a regime il flusso rispetto al riferimento di fase di statore:
$$
\left\{\begin{aligned}
\Phi_{sd} &= 0 \\
\Phi_{sq} &= -\frac{V_{s}}{\omega_{s}}
\end{aligned}\right.
$$
La velocità meccanica del rotore: $\omega_{r} = \frac{(1-s)\omega_{s}}{p}$, si introduce anche una potenza di traferro $P_{\delta}$, ovvero la potenza di interazione tra i due avvolgimenti al traferro:
$$
M_{e} = \frac{P_{\text{mecc}}}{\frac{(1-s)\omega_{s}}{p}} = \frac{P_{\delta}}{\frac{\omega_{s}}{p}} \Rightarrow P_{\text{mecc}} = (1-s)P_{\delta}
$$
ancora la coppia:
$$
M_{e} = -\frac{3}{2} p \mathrm{Im} \left\{ (i_{sd}+ji_{sq})\left( 0+\frac{jV_{s}}{\omega_{s}} \right) \right\} = -\frac{3}{2}p \left\{ \frac{i_{sd}V_{s}}{\omega_{s}} \right\}
$$
Usando la seconda equazione ($V_{sq}$ ecc):
$$
M_{e} = -\frac{3}{2}p \left\{ \frac{L_{m}}{L_{s}}i_{rd} \frac{V_{s}}{\omega_{s}} \right\}
$$

Bilancio delle potenze:
$$
P_{s} = \frac{3}{2} \mathrm{Re}\left\{ \vec{V}_{s}\check{\vec{I}_{s}} \right\} = \frac{3}{2}\left(V_{sd}I_{sd}+V_{sq}I_{sq}\right) \text{ potenza statore}
$$
In questo caso i fasori si riferiscono ai valori di picco!

Sostituendo $V_{sd}$ e $V_{sq}$:
$$
\begin{aligned}
P_{s} &= \frac{3}{2} (-R_{s}(I_{sd}^2 + I_{sq}^2) + \cancel{X_{s}I_{sq}I_{sd}} - X_{m}I_{rq}I_{sd} - \cancel{X_{s}I_{sd}I_{sq}}+ X_{m}I_{rd}I_{sq}) = \\
&= \frac{3}{2} (-R_{s}(I_{sd}^2 + I_{sq}^2) + X_{m}(I_{rd}I_{sq}-I_{sd}I_{rq})) = \\
& = -\frac{3}{2}(R_{s}(I_{sd}^2+I_{sq}^2))- \frac{\frac{\omega}{p}M_{e}}{3/2} = -P_{\omega,s}-P_{\delta}
\end{aligned}
$$
ricordando che 
$$
M_{e} = -\frac{3}{2}p\mathrm{Im}\{(I_{sd}+jI_{sq})(\cancel{\Phi_{sd}}- j\Phi_{sq})\} 
$$
La potenza di rotore:
$$
\begin{aligned}
P_{r} &= \frac{3}{2}\mathrm{Re}\left( \vec{V}_{r}\check{\vec{I}_{r}^s} \right) = \frac{3}{2}(V_{rd}I_{rd}^s + V_{rq}I_{rq})  =\\
&= \frac{3}{2} \left[R_{r}(I_{rd}^2-I_{rq}^2)-s (X_{r}I_{rq}^s-X_{m}I_{sq})I_{rd}^s + s(X_{r}I_{rd}^s-X_{m}I_{sd})I_{rq}^s\right] = \\
&= \frac{3}{2}[R_{r}({I_{rd}^s}^2+{I_{rq}^s}^2)] - sP_{\delta} = P_{\omega,r} - sP_{\delta}
\end{aligned}
$$
È stata fatta la convenzione del generatore per la $P_s$ e dell'utilizzatore la $P_{r}$, dunque la potenza elettrica generata $P_{el}=P_{s}-P_{r}$:
$$
P_{s}-P_{r} = P_{el} =  -P_{\omega,s} - P_{\omega,r} - (1-s)P_{\delta} = -P_{\omega,\text{tot}} - P_{\text{mecc}}
$$
A regime la potenza della turbina è pari alla potenza meccanica assorbita dal motore:
$$
P_{t}>0 = -(1-s)P_{\delta}
$$
la potenza di traferro è sempre negativa, dunque la potenza iniettata nel rotore è maggiore di zero per scorrimenti positivi e viceversa per scorrimenti negativi.

# Controllo
Si riprendono le equazioni (1:04:18)
$$
\left\{
\begin{aligned}
V_{sd} &= \frac{R_{s}}{L_{s}}\Phi_{sd} - \frac{L_{m}}{L_{s}}{R_{s}} {i}_{rd} + \frac{d}{dt} \Phi_{sd}\\
V_{sq } &= -\frac{L_{m}}{L_{s}}R_{s}i_{rq} + \omega_{s}\Phi_{sd} \\
V_{rd} &= R_{r}i_{rd} + \sigma_{r}L'_{r} \frac{d}{dt} i_{rd} - (\omega_{s} - p\omega_{r}) \sigma_{r}L_{r}i_{rq} + K_{s} \frac{d}{dt}\Phi_{sd} \\
V_{rq} &= R_{r}i_{rq}  + \sigma_{r}L'_{r} \frac{d}{dt} i_{rq} + (\omega_{s}-p\omega_{r})\sigma_{r}L_{r}i_{rq} + (\omega_{s}-p\omega_{r})K_{s}\Phi_{sd} \\
T_{el} &= \frac{3}{2}p \frac{L_{m}}{L_{s}} \Phi_{sd} i_{rq}
\end{aligned}
\right.
$$
In queste equazioni (terza e quarta) si potrebbero sostituire la derivata di $\Phi_{sd}$ in funzione di $i_{sd}$ e $i_{sq}$.
Si può ancora una volta imporre una condizione ausiliaria, come mantenere il flusso di asse diretto costante, è un pò più complesso perchè nella prima equazione si è realizzato il disaccoppiamento tra il flusso  di statore e la corrente di rotore secondo l'asse inquadratura:
$$
\frac{d}{dt} \Phi_{sd} + \frac{R_{s}}{L_{s}} \Phi_{sd} = V_{sd} + \frac{L_{m}}{L_{s}}R_{s}i_{rd}
$$
si ottiene una cosa simile al FOC, ma la componente $V_{sd}$ non può essere variata, solo la corrente di rotore può variare il flusso rispetto all'asse diretto.
Se si riesce ad imporre la derivata del flusso pari a zero, ovvero imporre un valore di $i_{rd}$:
$$
\Phi_{sd}=\text{cost}=\Phi_{sd,\text{nom}} : \frac{\Phi_{s}R_{s}}{L_{s}} = V_{sd} + \frac{L_{m}}{L_{s}}R_{s} i_{rd}
$$
ovvero:
$$
i_{rd} = \frac{\Phi_{s}}{L_{m}} - \frac{V_{sd}}{R_{s}} \frac{L_{s}}{L_{m}}
$$
Si sottrae un termine proporzionale alla tensione all'asse diretto alla componente di $i_{rd}$, imponendo questa equazione si ottiene il flusso costante e si possono trascurare i termini differenziali del flusso (ultimo termine terza equazione $K_{s} \frac{d}{dt}\Phi_{sd}$).

Si avrà un controllo sulla corrente $i_{rq}$ per regolare la coppia, mantenendo poi il flusso costante controllando la corrente $i_{rd}$.
