Fondamentale per la sicurezza e la [[Progettazione degli Impianti Elettrici|progettazione degli impianti elettrici]] è lo studio dello stato del neutro.
# Materializzazione del neutro
Avviene mediante la realizzazione di tre impedenze uguali connesse alle rispettive fasi e tra loro, la terna di tensioni esercita sulle impedenze sarà pari a:
$$
\begin{bmatrix}
E_{1} \\ E_{2} \\ E_{3}
\end{bmatrix} = 
\begin{bmatrix}
Z_{1} I_{1} \\ Z_{2} I_{2} \\ Z_{3} I_{3}
\end{bmatrix}
$$
Quasi tutte le macchine elettriche si prestano alla materializzazione del neutro data la loro simmetria costruttiva sono spesso modellate con tre impedenze uguali tra loro.

## Guasto monofase a terra con neutro isolato
Utilizzando Millmann tra il centro stella e la terra:
$$
V_{o'o} = \frac{E_{1}Y_{1} + E_{2}Y_{2} + E_{3}Y_{3}}{Y_{1}+Y_{2}+Y_{3}}
$$
con $Y$ le ammettenze dei singoli rami, si ipotizzano uguali per le tre fasi $Y=j \omega C_{0}$ se si effettua la trasposizione. Se non fossero uguali si avrebbe uno spostamento del centro stella, la tensione delle tre fasi rispetto al terreno sarebbe diversa, si introdurrebbe una dissimmetria della tensione lungo la linea.
In questo caso c'è uno spostamento "banale" del centro stella sulla fase $E_1$ a causa del collegamento a terra, dunque sulle altre due linee agirà la tensione concatenata $E_2-E_1$ e $E_3-E_1$ rispettivamente.
La corrente capacitiva sulla linea 2 ad esempio sarà:
$$
I_{C_{2}} = j \vec{V_{2}} \omega C_{0} = j \sqrt{ 3 } \vec{E_{2}} \omega C_{0}
$$
La relazione sulle correnti è la seguente:
$$
I_{g} + I_{C_{1}} + I_{C_{2}} =  0
$$
La corrente di guasto è dunque pari alla somma delle correnti capacitive.