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

# Esercizio di dimensionamento 1 (Conte - Cap 5 pag 60)
Calcolo della potenza convenzionale e corrente di impiego di un impianto in BT civile, esistono due tipologie di prese da 10 A e 16 A, la scelta delle protezioni terrà conto dell'utilizzo effettivo di queste prese.
Ad esempio per il punto luce si calcola:
$$
\text{luce: } N\cdot P_{n}\cdot K_{u}\cdot K_{0}
$$
La corrente di impiego delle lampade:
$$
I_{b} = \frac{P_{t}}{V_{n}\cos \varphi} 
$$
Potenza complessiva dei punti luce, con un fattore di utilizzazione di 0.6 e una potenza totale installata di 2kW:
$$
P_{1} = P_{t}\cdot K_{c} = 2000\cdot 0.6=1200\ W
$$
Per le prese si considera un $\cos \varphi=0.9$, i fattori di contemporaneità saranno diversi per le prese da 10A e 16A ovvero 0..05 e 0.2.
Le potenze massime delle prese saranno:
$$
P_{M2} =V_{n}I_{n}\cos \varphi = 230\cdot 16 \cdot 0.9 \simeq 3300\ W
$$
mentre per quelle da 10A:
$$
P_{M3} =V_{n}I_{n}\cos \varphi = 230\cdot 10 \cdot 0.9 \simeq 2070\ W
$$
In totale ci sono 4 prese da 16A e si stima un fattore di utilizzazione di 0.20:
$$
P_{2} = N_{2}\cdot P_{M2}\cdot K_{p2} = 4 \cdot 3300 \cdot 0.2 \simeq 2600\ W
$$
le prese da 10A sono più numerose (18) e avranno un fattore di utilizzazione più basso
$$
P_{3} = N_{3}\cdot P_{M{3}}\cdot K_{p{3}} = 18 \cdot 2070 \cdot 0.05 \simeq 1860\ W
$$
Si calcolano le correnti di impiego per dimensionare le linee:
$$
I_{b} = \frac{P}{V_{n}\cos \varphi} 
$$
ottenendo:
$$
\begin{aligned}
I_{b_{1}} &= 5.49A\\
I_{b_{2}} &= 12.6A\\
I_{b_{3}} &= 9A
\end{aligned}
$$
La potenza convenzionale totale è la somma delle tre potenze convenzionali dei tre circuiti: $P_{t}=P_{1}+P_{2}+P_{3}=1200+2600+1860=5660\ W$
si ricava la potenza contrattuale più vicina pari a 6kW, corrispondente ad una potenza specifica di $43\ W/m^2$.

