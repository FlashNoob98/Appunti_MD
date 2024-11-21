Si definisce la corrente di inserzione:
$$
i_{si}(t) = \frac{I_{0i}}{\sqrt{ 2 }} e^{-t/t_{i}}
$$
I valori $I_{oi}$ sono tabellati.
Per garantire che non ci sia un intervento intempestivo dell'interruttore a protezione del trasformatore devo avere che $I_{s}>0.7I_{oi}$.


## Esempio
Trasformatore con la seguente targa:

<center>

| $A_n$      | 2000kVA |
| ---------- | ------ |
| $V_{1n}$   | 20kV   |
| $V_{2n}$   | 0.4kV  |
| $V_{cc\%}$ | 5%     |

</center>

Dato che è un trasformatore in olio: $K_{i}=8,\quad T_{i}=0.45$
Si calcolano le correnti:
$$
I_{n}' = \frac{2000\cdot{1}0^3}{\sqrt{ 3 }\cdot20\cdot 10^3} = 57.73A
$$
e dunque moltiplicando per $K_{i}$:
$$
I_{0i} = K_{i}I_{n}' = 8\cdot 57.73A = 461.84\ A
$$
e dunque la corrente di intervento del dispositivo pari a:
$$
I_{s} = 250 A
$$

# Il trasformatore
Il regolamento europeo 548/14 prevede un livello di efficienza minima del trasformatore messo in vendita, si definisce un livello **PEI**:
$$
PEI = 1 - \frac{2(P_{0}+P_{C0})}{A_{n}\sqrt{ \frac{P_{0}+P_{C 0}}{P_{k}} }}
$$
Il termine $P_{C0}$ tiene conto delle perdite per il sistema di raffreddamento mentre $P_{k}$ sono le perdite sotto carico nelle condizioni nominali.
Per il sistema di raffreddamento vanno dimensionate le aperture della cabina, se non è presente un sistema di convezione forzata per raffreddare il trasformatore si considera la seguente formula:
$$
A = 0.238 \frac{P_{diss}}{\sqrt{ h }}
$$
dove $h$ è la distanza in altezza tra le due aperture.

In caso di convezione forzata invece:
$$
A = \frac{Q}{3600\cdot v}\quad Q= 343P_{diss}
$$
e $v$ è la velocità dell'aria.

Un trasformatore può essere sovradimensionato per alcuni carichi, la norma CEI EN 50160 afferma che il THD del distributore deve essere inferiore al 2% su misurazioni ogni 10 minuti.
Questo è un vincolo per il distributore e non per l'utente.
Definito anche come il rapporto tra la terna inversa e quella diretta.

L'effettiva potenza del trasformatore:
$$
A_{e} = kA
$$
con $k$ definito nella CEI 14-22, funzione del numero di carichi non lineari.

## Parallelo di trasformatori
Per disporre dei trasformatori in parallelo, si deve garantire che abbiano lo stesso rapporto di trasformazione e siano dello stesso gruppo.

Il rapporto tra le potenze nominali non deve superare $\frac{2}{3}$.
La condizione ideale se il $\cos{\phi_{cc}}$ è identico, e la tensione di corto circuito è identica, anche se non è una condizione vincolante.

Si supponga di avere tre trasformatori in parallelo:
$$
\frac{\Delta E_{i\%}}{\Delta V_{cc\%}} = \frac{\Delta E_{i}}{\Delta V_{cc}} = \frac{I_{i}}{I_{in}} = \frac{A_{i}}{A_{in}}
$$
La corrente si ripartisce nei trasformatori al variare della loro impedenza di corto circuito e della tensione di corto circuito.

Ad esempio le tre tensioni di corto circuito:
$$
\begin{aligned}
V_{cc_{1}} &= 5\%\Rightarrow A_{1} = 100 \cdot \frac{4}{5} = 80kVA\\
V_{cc_{2}} &= 4\%\Rightarrow A_{2} = 200\cdot \frac{4}{4} = 200kVA\\
V_{cc_{3}} &= 5\%\Rightarrow A_{3} = 300\cdot \frac{4}{6} = 200 kVA
\end{aligned}
$$
I tre trasformatori hanno una potenza apparente di 100, 200 e 300 kVA.
Solo il trasformatore centrale ha raggiunto la potenza nominale.
Una richiesta successiva di potenza richiederà un sovraccarico del trasformatore 2.

Se si assegna una certa potenza assorbita dal carico e la tensione di corto circuito dei trasformatori, si può calcolare la caduta di tensione percentuale:
$$
\frac{\Delta_{1n}\Delta E}{\Delta V_{cc_{1}}} + \frac{\Delta_{2n}\Delta E}{\Delta V_{cc_{2}}} +\frac{\Delta_{3n}\Delta E}{\Delta V_{cc_{3}}} = 500
$$
Si ricava:
$$
\Delta E \left( \frac{100}{5} + \frac{200}{4} + \frac{300}{6} \right) = 500 \Rightarrow \Delta E = 4.16\%
$$
E quindi le tre potenze assorbite dai trasformatori:
$$
\begin{aligned}
\Delta_{1n} &= 100\cdot \frac{{4}.16}{5} = 83.2 kVA\\
\Delta_{2n} &= 200\cdot \frac{4.16}{4} = 208kVA\\
\Delta_{3n} &= 300 \cdot \frac{4.16}{6} = 208kVA
\end{aligned}
$$
Dunque il trasformatore 2 è ancora in sovraccarico.
Se le tensioni di corto circuito fossero identiche, si avrebbero tutti e tre i trasformatori caricati allo stesso modo.
