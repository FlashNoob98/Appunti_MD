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

# Criteri di dimensionamento dell'impianto elettrico
Esistono tre criteri per dimensionare un impianto elettrico:
quello elettrico, che tiene conto della caduta di tensione lungo la linea, quello termico e quello economico.

Nel criterio elettrico si modella la linea con una serie RL, si calcola la caduta di tensione lungo la linea con un'approssimazione:
$$
\Delta V = RI\cos \varphi + XI\sin \varphi
$$
Si può utilizzare la caduta percentuale e le potenze attiva e reattiva:
$$
\Delta V_{\%} = \frac{RP+XQ}{V_{n}^2}
$$
Questa seconda forma è più comoda per il calcolo dei sistemi di rifasamento.

Si tende a trascurare il termine induttivo, considerando solo il valore della resistenza variabile con la lunghezza, si assume la reattanza costante pari a $k$:
$$
\Delta V = k+RI\cos \varphi
$$
## Linea a sbalzo
Una linea alimenta un carico all'estremità, si assume $\cos \varphi=1$:
$$
\Delta V = RI = \frac{\rho L}{S}I \leq \Delta V_{\text{amm}}
$$
si definisce il momento amperometrico $M=LI$ ottenendo la sezione minima del conduttore:
$$
S \geq 2 \frac{\rho M}{\Delta V_{\text{amm}}}
$$
Il fattore 2 per un carico monofase (2 conduttori).

Trovata la sezione si può calcolare la reattanza del cavo e verificare che la $\Delta V_{\text{amm}}$ sia maggiore della $\Delta V$ effettiva del cavo:
$$
\Delta V = RI\cos \varphi + XI\sin \varphi
$$
con $R$ ed $X$ forniti dal costruttore del cavo, fissata la sezione, moltiplicati per la lunghezza complessivo del circuito.

## Carichi distribuiti lungo la linea
Lungo una linea sono distribuiti più carichi disposti ad una certa distanza, si identificano le lunghezze $l_{1},l_{2},\dots,l_{n}$ le distanze tra le varie utenze e con $L_{1},L_{2},\dots, L_{n}$ le distanze dei carichi dall'alimentazione.

In questo caso la condizione da verificare è a fine linea, (la più critica) dunque la $\Delta V$ totale a fine linea si calcola:
$$
\Delta V = \sum_{i=1}^N I_{i}\cdot\sum_{j=1}^i r_{j} = \frac{2\rho}{S} \sum_{i=1}^{N}I_{i}L_{i} = \frac{2\rho}{S}\sum_{i=1}^N M_{i} \leq \Delta V_{\text{amm}}
$$
con
$$
r_{j} = \frac{\rho l_{j}}{S_{j}}
$$
le resistenze parziali della linea tra i carichi.
Si assume la sezione costante lungo tutta la linea.

Si può calcolare una linea con una lunghezza equivalente tale che:
$$
\sum_{i=1}^NI_{i}L_{i} = \sum_{i=1}^N I_{i}\cdot L_{eq} \Rightarrow L_{eq} = \frac{\sum_{i=1}^NI_{i}L_{i}}{\sum_{i=1}^N I_{i}}
$$
## Linea con sezioni differenti
Si definisce con $I_{i}'$ una corrente "di tratto" pari, successivamente ad ogni carico alla somma dei carichi a valle, si semplifica la formula della caduta di tensione:
$$
\Delta V = \sum_{i=1}^N \rho \frac{ l_{i}}{S_{i}}I_{i}'
$$
Si può introdurre una funzione costo:
$$
f(S_{1},S_{2},\dots,S_{N})=S_{1}l_{1}+S_{2}l_{2}+\dots+S_{N}l_{n}
$$
pari al volume di materiale utilizzato, può essere moltiplicata per 2 con linee monofase o per $\sqrt{ 3 }$ per linee trifase, si vuole minimizzare la funzione rispetto ad $S$ mantenendo però il vincolo su $\Delta V$.
$$
\left\{
\begin{aligned}
&\stackrel{\text{min}}{S} f\left( \vec{S} \right)\\
&\varphi\left( \vec{S} \right) = \Delta V
\end{aligned}
\right.
$$
Si può risolvere il problema di ottimizzazione mediante i moltiplicatori di Lagrange, fissando la caduta di tensione si minimizza la funzione obiettivo.
$$
\begin{aligned}
\mathcal{L} &= f\left( \vec{S} \right) + \lambda\left( \varphi\left( \vec{S} \right)-\Delta V \right) \\
\frac{\partial\mathcal{L}}{\partial S_{i}} &=0 \\
\frac{\partial\mathcal{L}}{\partial \lambda} &=0 \Rightarrow \varphi\left( \vec{S} \right) = \Delta V
\end{aligned}
$$
Si svolge la derivata rispetto alle sezioni:
$$
\frac{\partial\mathcal{L}}{\partial S_{i}} = \frac{\partial f}{S_{1}} + \lambda\frac{\partial \varphi}{\partial S_{1}}
$$
ottenendo (per cavo monofase)
$$
\begin{aligned}
&2l_{1}-\lambda\frac{2\rho l_{1}}{S_{1}^2}I_{1}' = 0\\
&\vdots\\
&2l_{i}-\lambda\frac{2\rho l_{i}}{S_{i}^2}I_{i}' = 0
\end{aligned}
$$
un set di equazioni per ogni sezione del cavo, semplificando:
$$
\frac{S_{i}^2}{I_{i}'}=\lambda \rho \Rightarrow \frac{S_{i}}{\sqrt{ I_{i}' }} = \sqrt{ \lambda \rho } = \alpha
$$
dunque il rapporto tra $S_{i}$ e $I_{i}'$ è costante e pari a $\sqrt{ \lambda \rho }$, in altre parole:
$$
\frac{S_{1}}{\sqrt{ I_{1}' }} =\frac{S_{2}}{\sqrt{ I_{2}' }} = \dots =\frac{S_{N}}{\sqrt{ I_{N}' }} = \alpha
$$
Si sostituisce la sezione i-esima con la radice della corrente per $\alpha$:
$$
\Delta V = 2\rho \sum_{i=1}^N \frac{l_{i}I_{i}'}{\sqrt{ I_{i}' }\alpha}
$$
da cui si può calcolare il coefficiente $\alpha$:
$$
\alpha = \frac{2\rho}{\Delta V} \sum_{i=1}^N {l_{i}\sqrt{  I_{i}'}}
$$
e dividendo per $\rho$ si può ricavare il moltiplicatore di Lagrange $\lambda$.

## Carichi equidistanti
Se i carichi sono equidistanti lungo la linea, ovvero $l_{1}=l_{2}=\dots=l_{N}$ come nel caso di sistemi di illuminazione, la caduta di tensione diventa:
$$
\Delta V = \frac{2\rho}{S}lI(n+(n-1)+(n-2)+\dots+1) = \frac{2\rho}{S}Il \frac{n(n+1)}{2}\leq \Delta V_{\text{amm}}
$$
oppure
$$
\Delta V = \frac{2\rho}{S} I_{t}\left( \frac{L}{2}  +\frac{l}{2} \right) \leq \Delta V_{\text{amm}}
$$
se il numero di carichi tende all'infinito si ottiene l'equazione di un carico uniformemente distribuito.

## Carico alimentato da due estremità
Si ha una linea alimentata da due punti $A$ e $B$ con un carico centrale, si suppone che si possa separare questa linea in due linee separate attraversate da due differenti correnti $I_{A}$ e $I_B$ virtuali, si assume che la tensione nei due punti di alimentazione sia la stessa, la corrente si ripartirà in maniera inversa rispetto alla resistenza dei due differenti tratti di linea $R_{A}$ e $R_{B}$ ovvero mediante un partitore di corrente:
$$
I_{A} = I \frac{R_{B}}{R_{A}+R_{B}}\quad I_{B }=I \frac{R_{A}}{R_{A}+R_{B}}
$$
supponendo che le due sezioni siano le stesse, la resistenza è $\frac{\rho L}{S}$, il partitore dipenderà solo dalla lunghezza dei due tratti di linea:
$$
I_{A} = I \frac{L_{B}}{L_{A}+L_{B}}=\frac{M_{B}}{L}\qquad I_{B}=I \frac{L_{A}}{L_{a}+L_{B}}=\frac{M_{A}}{L}
$$
definendo i momenti amperometrici e con $L=L_{A}+L_{B}$ la lunghezza della linea.

La caduta di tensione dal punto $A$:
$$
\Delta V_{A} = \frac{2\rho I_{A}L_{A}}{S} = \frac{2\rho L_{A}}{S} \frac{M_{B}}{L} \leq \Delta V_{\text{amm}}\rightarrow S\geq S_{A}
$$
caduta di tensione dal punto $B$:
$$
\Delta V_{B} = \frac{2\rho I_{B}L_{B}}{S} = \frac{2\rho L_{B}}{S} \frac{M_{A}}{L} \leq \Delta V_{\text{amm}}\rightarrow S\geq S_{B}
$$
si sceglierà come sezione minima la massima sezione tra $S_A$ e $S_B$:
$$
S\geq \text{max}(S_{A},S_{B})
$$
si è assunto che le due sezioni fossero uguali, se invece si vede che le sezioni $S_A$ ed $S_{B}$ sono molto diverse tra loro, allora andrebbe eseguito il calcolo senza poter passare alle lunghezze ma considerando tutta la resistenza.

## Carichi multipli su linea alimentata da due punti
In questo caso la procedura è analoga, si calcola la corrente $I_{A}$ mediante un partitore di corrente:
$$
I_{A} = \frac{(L_{2}+L_{3}+L_{4})}{4} + I_{2}\left( \frac{L_{3}+L_{4}}{L} \right) + I_{3} \frac{L_{4}}{L}
$$
Per la corrente $I_B$:
$$
I_{B} = I_{1} \frac{L_{1}}{L} + \frac{I_{2}(L_{1}+L_{2})}{L} + I_{3} \frac{L_{1}+L_{2}+L_{{3}}}{L} 
$$

Se i punti di alimentazione avessero tensione diversa:
$$
I_{A} = \sum_{i=1}^{N} \frac{M_{Bi}}{L} + \frac{V_{A}-V_{B}}{R_{AB}}
$$
e
$$
I_{B} = \sum_{i=1}^{N} \frac{M_{Ai}}{L} + \frac{V_{B}-V_{A}}{R_{AB}}
$$

## Linea radiale
Si suppone di avere una dorsale A-B, nel punto B sono poste altre linee di derivazione, si deve garantire la massima caduta di tensione per ogni dorsale.
$$
\Delta V_{0} = 2\rho \left[ \frac{L_{0}}{S_{0}}\sum_{j=1}^{n}I_{dj} + \sum_{i=1}^{n_{0}} \frac{M_{Ai}}{S_{0}} \right]
$$
La caduta di tensione tra il punto $B$ e un punto finale di un ramo è pari a:
$$
\Delta V_{j} = \frac{2\rho}{S_{j}} \sum_{i=1}^{n_{j}} M_{Bi,j} = \frac{2\rho}{S_{j}} M_{Bj} = \Delta V'
$$
con $j$ si intende la linea, $i$ il carico.

Si ottiene una costante $k$:
$$
\frac{M_{Bj}}{S_{j}} = \frac{\Delta V'}{2\rho} = \frac{1}{k} \Rightarrow S_{j} = kM_{Bj}
$$
Si può assumere che la sezione della linea a monte sia pari alla somma delle sezioni dei rami:
$$
S_{0} = \sum_{j=1}^{n}S_{j} = k\sum_{j=1}^n M_{Bj} \Rightarrow k = \frac{S_{0}}{\sum_{j=1}^n M_{Bj} }
$$
Si riscrive la caduta $j$-esima rispetto alla sezione $S_{0}$:
$$
\Delta V_{j} = \frac{2\rho}{S_{0}} \sum_{j=1}^{n_{j}} M_{Bj} 
$$
Raggruppando le due cadute:
$$
\Delta V = \Delta V_{0}  +\Delta V_{j} = \frac{2\rho}{S_{0}}\left[ L_{0} \sum_{j=1}^n I_{dj} + \sum_{i=1}^{n_{0}} M_{Ai} + \sum_{j=1}^{n} M_{Bj} \right] \leq \Delta V_{\text{amm}}
$$
Si ricava infine la sezione $j$-esima:
$$
S_{j} = k M_{Bj} = S_{0} \frac{M_{Bj}}{\sum_{j=1}^{n} M_{Bj}}
$$
ovvero la sezione di ogni ramo è proporzionale al momento amperometrico di quel ramo.

## Metodo di Coltri
Sia data una rete complessa, si calcola la corrente lungo un tratto $AB$:
$$
I_{AB} = \sum_{i=1}^{n_{A}} \frac{M_{Bi}}{L_{AB}} + \frac{V_{A}-V_{B}}{R_{AB}}
$$
e così via per tutti i rami connessi ad $A$:
$$
I_{AC} = \sum_{i=1}^{n_{A}} \frac{M_{Ci}}{L_{AC}} + \frac{V_{A}-V_{C}}{R_{AC}}
$$
ma la somma di tutte queste correnti è nulla:
$$
0= \sum_{i=1}^{n_{A}} \frac{M_{Bi}}{L_{AB}} + \sum_{i=1}^{n_{A}} \frac{M_{Ci}}{L_{AC}} + \dots  + \frac{V_{A}-V_{B}}{R_{AB}} +\frac{V_{A}-V_{C}}{R_{AC}} + \dots
$$
Le incognite sono le tensioni ai nodi, si scriveranno tante equazioni simili per quanti nodi sono presenti, si può utilizzare come metodo di verifica.
In alternativa si può usare un metodo iterativo per calcolare le sezioni delle linee, questo metodo permette di utilizzare il criterio elettrico nelle reti magliate.
