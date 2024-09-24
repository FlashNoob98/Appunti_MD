Fondamentale per la sicurezza e la [[Progettazione degli Impianti Elettrici|progettazione degli impianti elettrici]] è lo studio dello stato del neutro.
# Materializzazione del neutro
Avviene mediante la realizzazione di tre impedenze uguali connesse alle rispettive fasi e tra loro, la terna di tensioni esercita sulle impedenze sarà pari a:
$$
\begin{bmatrix}
\vec{E_{1}} \\ \vec{E_{2}} \\ \vec{E_{3}}
\end{bmatrix} = 
\begin{bmatrix}
\dot{Z_{1}} \vec{I_{1}} \\ \dot{Z_{2}} \vec{I_{2}}  \\ \dot{Z_{3}} \vec{I_{3}} 
\end{bmatrix}
$$
Quasi tutte le macchine elettriche si prestano alla materializzazione del neutro data la loro simmetria costruttiva sono spesso modellate con tre impedenze uguali tra loro.

## Guasto monofase a terra con neutro isolato
Si sfruttano ancora i [[circuiti di sequenza]] per studiare il guasto con neutro isolato, per ricavare le grandezze del guasto si analizza il circuito trifase:
<center>

![[guasto_monofase_neutro_isolato.svg]]
</center>

Si sfrutta il [teorema di Millman](https://it.wikipedia.org/wiki/Teorema_di_Millman) tra il centro stella e la terra:
$$
\vec{V}_{o'o} = \frac{\vec{E_{1}}\dot{Y_{1}} +\vec{E_{2}}\dot{Y_{2}} +\vec{E_{3}}\dot{Y_{3}}}{\dot{Y_{1}}+\dot{Y_{2}}+\dot{Y_{3}}}
$$
con $\dot{Y}$ le ammettenze dei singoli rami, si ipotizzano uguali per le tre fasi $\dot{Y_{i}}=j \omega C_{0}$ se si effettua la trasposizione. Se non fossero uguali si avrebbe uno spostamento del centro stella, la tensione delle tre fasi rispetto al terreno sarebbe diversa, si introdurrebbe una dissimmetria della tensione lungo la linea.
A causa del guasto c'è uno spostamento "banale" del centro stella sulla fase $\vec{E_{1}}$ a causa del collegamento a terra, dunque sulle altre due linee agirà la tensione concatenata $\vec{E_2}-\vec{E_1}$ e $\vec{E_3}-\vec{E_1}$ rispettivamente.
La corrente capacitiva sulla linea 2 ad esempio sarà:
$$
\vec{I_{C}}_{2} = j \vec{V_{2}} \omega C_{0} = j \sqrt{ 3 } \vec{E_{2}} \omega C_{0}
$$
La relazione sulle correnti è la seguente:

$$
\vec{I_{g}} + \vec{I_{C}}_{1} + \vec{I_{C}}_{2} =  0
$$
La corrente di guasto è dunque pari alla somma delle correnti capacitive.
