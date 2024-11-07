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
&= \frac{3}{2} (-R_{s}(I_{sd}^2 + I_{sq}^2) + X_{m}(I_{rd}I_{sq}-I_{sd}I_{rq}))
\end{aligned}
$$
