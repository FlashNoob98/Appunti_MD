Fondamentale il calcolo della corrente di impiego dell'impianto:
$$
I_{b} = \frac{P}{\sqrt{ 3 }V\cos \varphi}
$$
Per il calcolo del $\cos \varphi$ si può considerare un valore medio o considerando il rifasamento da attuare nell'impianto si può considerare quello previsto dalla normativa.
La potenza da considerare dipende dai carichi ma anche dalla parte dell'impianto in cui ci si trova.

Nella progettazione preliminare si determina la tipologia di impianto e si può utilizzare l'informazione dei VA/m^2 per calcolare la potenza convenzionale di quell'applicazione.
Esistono delle tabelle sui manuali in base agli impianti.

Si definisce il *coefficiente di utilizzazione*:
$$
K_{u} = \frac{P}{P_{n}}
$$
utilizzando le tabelle del coefficiente di utilizzazione si ricava la potenza assorbita a partire da quella nominale.
È solitamente compreso tra 0 ed 1 a meno di eventuali sovraccarichi.

Si definisce il *coefficiente di contemporaneità*:
$$
K_{c} = \frac{P_{t}}{\sum_{i=1}^n P_{i}}
$$
dunque si calcola la potenza totale:
$$
P_{t} = K_{c}(P_{1}+P_{2}+\dots+P_{n})
$$
con $n$ carichi, ci si aspetta che non tutti gli utilizzatori funzionino contemporaneamente. Questo coefficiente è minore di 1 ed implica che la potenza assorbita da una sezione di impianto composta da più carichi non è pari alla somma algebrica di tutti i carichi, dato che questi non verranno necessariamente utilizzati insieme (in contemporanea appunto).

Si possono raccogliere i due coefficienti in un unico coefficiente chiamato *coefficiente di riduzione*:
$$
K_{p} = K_{c}\cdot K_{u} ???
$$
Per le prese varia tra 0.05 a 0.4.
