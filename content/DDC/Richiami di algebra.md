Sia dato un insieme di elementi $X$ e una legge di composizione interna "+", si definisce **gruppo** l'insieme di questi due elementi se la legge di composizione gode delle seguenti proprietà:
- Associativa: $a+(b+c)=(a+b)+c$ con $a,b \text{ e }c$ elementi dell'insieme $X$.
- Elemento neutro: esiste un elemento neutro $\vec{o}:a+\vec{o}=\vec{o}+a=a$ e per questo vale la proprietà commutativa.
- Elemento simmetrico: esiste un elemento simmetrico $a':a+a'=\vec{o}$.
Si dice allora che $X$ è il *sostegno* della struttura algebrica.
Se la proprietà commutativa vale per tutti gli elementi del gruppo, allora questo è detto *commutativo* o abeliano.

Al gruppo si aggiunge l'operazione "$\cdot$" di moltiplicazione, si ha un **campo** se:
- $X$ è un gruppo abeliano rispetto a "+" con $\vec{o}$.
- $X-\left\{ \vec{o} \right\}$ è un gruppo abeliano con "$\cdot$".
- se "$\cdot$" è distribuita: $a\cdot(b+c)=ab+ac$

Dato un insieme di vettori non vuoto $V$, una legge di composizione interna "+" e un campo $\mathbb{K}$ allora $V$ sarà uno **spazio vettoriale** sul campo $\mathbb{K}$ anche detto $K-\text{spazio}$ se:
- $V$ è un gruppo abeliano rispetto a "+"
- $(a+b)\vec{v} = a\vec{v}+b\vec{v}$
- $a\left( \vec{v}_{1}+\vec{v}_{2} \right) = a\vec{v}_{1}+a\vec{v}_{2}$
- $(ab)\vec{v}=a\left( b\vec{v} \right)=b\left( a\vec{v} \right)$
gli elementi di $V$ sono chiamati *vettori* mentre gli elementi di $\mathbb{K}$ sono chiamati *scalari*.

## Combinazione lineare
Estendendo l'operazione di addizione si definisce la *combinazione lineare*, dato un insieme di vettori $\left\{ \vec{v}_{1},\vec{v}_{2},\vec{v}_{3},\dots,\vec{v}_{N} \right\}\in V$ e un vettore $\vec{w}\in V$ si dirà che $\vec{w}$ è combinazione lineare dei vettori $\vec{v}$ se:
$$
\vec{w} = \sum_{k=1}^N \alpha_{k}\vec{v}_{k}
$$
con $\alpha_{1},\alpha_{2},\alpha_{3},\dots,\alpha_{n}\in \mathbb{K};\alpha_{k}\neq 0$.

I vettori si dicono **linearmente dipendenti** se
$$
\sum_{k=1}^{N} \alpha_{k}\vec{v}_{k}=0
$$
oppure si dicono **linearmente indipendenti** e costituiscono una *famiglia libera* di vettori di $V$ se:
$$
\sum_{k=1}^{N} \alpha_{k}\vec{v}_{k}=0 \text{ solo se }\alpha_{k}=0\ \forall\ {k}
$$
La famiglia è detta **massimale libera** se sono presenti $N$ vettori linearmente indipendenti e questi diventano dipendenti con l'aggiunta di un singolo vettore.

Si dimostra che in uno spazio vettoriale, una famiglia massimale libera genera tutto lo spazio, ovvero ogni vettore presente nello spazio vettoriale può essere espresso come combinazione lineare dei vettori della famiglia massimale libera.
Se la famiglia massimale libera è di dimensione finita, allora questa coinciderà con la dimensione dello spazio vettoriale.
La famiglia massimale libera che genera uno spazio vettoriale, prende anche il nome di **base** dello spazio vettoriale.
Uno spazio vettoriale può anche essere non finitamente generabile se la sua base ha dimensione infinita.

## Sottospazi
Dato un $\mathbb{K}$-spazio e un sottoinsieme $W$ di $V$ allora $W$ è un **sottospazio** se $\forall\ \vec{w}_{1},\vec{w}_{2}\in W$:
- $\vec{w}_{1}+\vec{w}_{2}\in W$
- $\alpha \vec{w}\in W$ con $\alpha \in\mathbb{K}$

## Applicazione lineare
Si definisce $f:(V,\mathbb{K})\to(W,\mathbb{K})\ V\neq W$, è un'applicazione lineare se:
- $f\left( \vec{a}+\vec{b} \right) = f\left( \vec{a} \right)+f\left( \vec{b} \right)$
- $f\left( a\vec{b} \right)=af\left( \vec{b} \right)$
con $\vec{a},\vec{b} \in V;\ \alpha \in \mathbb{K};\ f\left( \vec{a} \right),f\left( \vec{b} \right)\in\ W$.
Se $V=W$ allora l'applicazione lineare è un **endomorfismo**, ovvero un'applicazione in sé stessa.
L'applicazione è **biettiva** se ad ogni elemento di $V$ coincide uno ed un solo elemento di $W$ e viceversa.
Se un'applicazione è lineare e biettiva, si parla di **isomorfismo**.
Un esempio di spazio vettoriale sono le funzioni continue.

Gli spazi isomorfi conservano la struttura algebrica, ad esempio l'uso del metodo fasoriale, mediante la trasformata di Steinmetz, è definito su uno spazio delle funzioni periodiche di periodo $T$ e restituisce valori in $\mathbb{C}$ che è un ulteriore spazio vettoriale. L'applicazione è biettiva e permette il passaggio da uno spazio all'altro, trasformando le equazioni differenziali in equazioni algebriche.

## Metrica di uno spazio vettoriale
Uno spazio vettoriale $X$ definito su $\mathbb{K}$ si dice **metrico** se si può definire una funzione $d:X\times X\to\mathbb{R}_{0}^+$ definita metrica.
Si chiama *distanza* di $\vec{x}$ da $\vec{y}$ la funzione metrica applicata ai due vettori:
- $d\left( \vec{x},\vec{y} \right)\geq 0\quad\quad d\left( \vec{x},\vec{y} \right)=0\Leftrightarrow \vec{x}\equiv\vec{y}$
- $d\left( \vec{x},\vec{y} \right)=d\left( \vec{y},\vec{x} \right)$
- $d\left( \vec{x},\vec{z} \right)\leq d\left( \vec{x},\vec{y} \right)+d\left( \vec{y},\vec{z} \right)$
La metrica permette di definire il concetto di *intorno* di un punto, così come il punto di accumulazione, il limite, la derivata.
Intorno chiuso: $\left\{ \vec{x}:d\left( \vec{x},\vec{x}_{0} \right)\leq R \right\}$
Intorno aperto: $\left\{ \vec{x}:d\left( \vec{x},\vec{x}_{0} \right)< R \right\}$
entrambi di centro $\vec{x}_{0}$ e raggio $R$.

# Metrica holderiana
Si definisce una metrica generalizzata *holderiana* tra due funzioni $f$ e $g$:
$$
d_{p}(f,g)=\left\{ \int_{a}^b \left|f(x)-g(x)\right|^p \right\}^{1/p}
$$
Questa funzione rispetta le proprietà della metrica.
Si può anche calcolare la metrica tra due vettori di ordine $n$:
$$
d_{p}\left( \vec{x},\vec{y} \right) = \left\{ \sum_{k=1}^n \left| x_{k}-y_{k} \right|^p\right\}^{1/p}
$$
per $p=2$ la metrica si chiama **euclidea** (teorema di Pitagora).

# Successione di Cauchy
Dato uno spazio metrico $X$, si considera una successione di elementi $x_{n}$ nello spazio.
Si dice che la successione è di Cauchy se
$$
\forall \ \varepsilon>0 \ \exists\  N>0: \forall\ n,m>N \Rightarrow d(x_{n},x_{m})<\varepsilon
$$
ovvero dopo un certo numero $N$ di elementi della successione, la distanza tra questi si riduce ad un valore $\varepsilon$ arbitrario.
Le successioni convergenti sono tutte successioni di Cauchy ma non è sempre vero il viceversa, ad esempio la successione
$$
\{a_{n}\} : a_{n}=\left( 1+\frac{1}{n} \right)^n
$$
è di Cauchy perché la distanza tra i suoi elementi si riduce all'aumentare dell'ordine $n$ ma non converge.
La somma della serie tende al numero di Nepero che è irrazionale mentre gli elementi della serie sono stati definiti nello spazio dei numeri razionali $\mathbb{Q}$.

Un altro esempio se si definisce uno spazio $X:]-1,1[$ , la successione
$$
a_{n}=\left( 1-\frac{1}{n} \right)
$$
è di Cauchy ma converge ad 1 che è esterno dello spazio di definizione.
Uno spazio metrico si dice **completo** se ogni successione di Cauchy converge ad un elemento dello spazio metrico.

# Spazi normati
Sia $X$ un $\mathbb{K}$-spazio, si definisce l'operatore norma "$||\cdot||$"$:X\to\mathbb{R}_{0}^+$, see quest'ultimo ha le seguenti proprietà lo spazio si dice **normato**:
- $||\vec{x}||\geq 0\quad\quad ||\vec{x}||=0\Leftrightarrow\vec{x}=\vec{0}$
- $||\lambda \vec{x}||=|\lambda|\cdot||\vec{x}||\quad \lambda\in\mathbb{K}$
- $||\vec{x}+\vec{y}||\leq||\vec{x}||+||\vec{y}||$
Il concetto di norma amplia il concetto di ampiezza di un vettore, il modulo è una particolare norma.
La norma può indurre una metrica:
$$
d\left( \vec{x},\vec{y} \right)\stackrel{\Delta}{=} ||\vec{x}-\vec{y}||
$$
Uno spazio normato che sia completo rispetto alla metrica indotta dalla norma prende il nome di **spazio di Banach**.

## Forma bilineare
Sia $f$ un'applicazione tra due spazi vettoriali su uno stesso campo $\mathbb{K}$, si dice che $f$ è **bilineare** se:
$$
\begin{aligned}
\text{Lineare rispetto al}&\text{ primo argomento}\\
f\left( \alpha \vec{v}_{1}+\beta \vec{v}_{2},\vec{v}' \right) &= \alpha f\left( \vec{v}_{1},\vec{v}' \right) + \beta f\left( \vec{v}_{2},\vec{v} '\right) \\
\text{Lineare rispetto al}&\text{ secondo argomento}\\
f\left( \vec{v},\alpha\vec{v}_{1}'+\beta \vec{v}_{2}' \right) &= \alpha f\left( \vec{v},\vec{v}_{1}' \right) + \beta f\left( \vec{v}, \vec{v}_{2}\right) \\
f\left( \vec{v},\vec{v}' \right) &= f\left( \vec{v}',\vec{v} \right)
\end{aligned}
$$
se vale la terza relazione è anche **simmetrica**.

### Prodotto scalare
Si definisce *prodotto scalare*:
$$
S\left( \vec{x},\vec{y} \right): V\times V \to \mathbb{R}
$$
È una [[forma bilineare]] simmetrica definita su un campo reale nello spazio $V$ cartesiano su se stesso, deve essere:
- Non degenere: $S\left( \vec{x},\vec{y} \right)=0\quad \forall\ \vec{x}\in V\Rightarrow \vec{y}=0$
- Definito positivo: $S\left( \vec{x},\vec{x} \right)>0\ \forall\ \vec{x}\neq {0}$
Si riporta il prodotto scalare di uno spazio vettoriale numerico $\mathbb{R}^n$ sul campo $\mathbb{R}$:
$$
\left\langle  \vec{x},\vec{y}  \right\rangle = \sum_{k=1}^n x_{k}y_{k}\quad \vec{x},\vec{y}\in\mathbb{R}^n 
$$
ovvero la sommatoria delle componenti di pari ordinata.

# Forma sesquilineare
Siano dati due spazi vettoriali sullo stesso campo $\mathbb{K}$, si dice che $f$ è una forma **sesquilineare** se:
$$
\begin{aligned}
\text{Lineare rispetto al}&\text{ primo argomento}\\
f\left( \alpha \vec{v}_{1}+\beta \vec{v}_{2},\vec{v}' \right) &= \alpha f\left( \vec{v}_{1},\vec{v}' \right) + \beta f\left( \vec{v}_{2},\vec{v} '\right) \\
\text{Antilineare rispetto al}&\text{ secondo argomento}\\
f\left( \vec{v},\alpha\vec{v}_{1}'+\beta \vec{v}_{2}' \right) &=  \check{\alpha} f\left( \vec{v},\vec{v}_{1}' \right) + \check{\beta} f\left( \vec{v}, \vec{v}_{2}\right) \\
f\left( \vec{v},\vec{v}' \right) &= \overline{f\left( \vec{v}',\vec{v} \right)} \text{ complesso coniugato}
\end{aligned}
$$
Se il campo $\mathbb{K}=\mathbb{R}$ la forma sesquilineare degenera nella bilineare dato che $\alpha=\check{\alpha}\ \forall \alpha\in\mathbb{R}$.
## Proprietà hermitiana
Un prodotto scalare *hermitiano* è una forma sesquilineare simmetrica così definita:
$$
h\left( \vec{x},\vec{y} \right) \longrightarrow h:V\times V \in\mathbb{C}
$$
dove $V$ è uno spazio vettoriale definito su un campo complesso $\mathbb{C}$.
Ad esempio il prodotto hermitiano canonico su uno spazio $V\in\mathbb{C}^n$:
$$
\left\langle  \vec{x},\vec{y}  \right\rangle = \sum_{k=1}^n x_{k}\check{y}_{k} 
$$
con $\check{y}_{k}$ il complesso coniugato di $y_{k}$.

# Metrica euclidea
Sia un campo vettoriale $V\in\mathbb{R}^n$ dotato di prodotto scalare, si dice che questo spazio è *euclideo*, il prodotto scalare può indurre una norma, dunque una metrica.
Si definisce la norma indotta:
$$
\left\langle  \vec{x},\vec{x}  \right\rangle = \sum_{k=1}^nx_{k}^2 \Rightarrow 
||\vec{x}|| \stackrel{\Delta}{=} \sqrt{ \left\langle  \vec{x},\vec{x}  \right\rangle  }
$$

## Spazio pre-hilbertiano
Si definisce spazio pre-hilbertiano uno spazio vettoriale su cui si definisce un prodotto scalare che induce una norma e quindi una metrica, si introduce allora il concetto di **angolo**, dato che:
$$
\left\langle  \vec{x},\vec{y}  \right\rangle \leq ||\vec{x}||\cdot||\vec{y}|| 
$$
allora
$$
\cos \theta \stackrel{\Delta}{=}  \frac{\left\langle  \vec{x},\vec{y}  \right\rangle }{||\vec{x}||\cdot||\vec{y}||} \leq 1\quad \theta\in[-\pi,\pi] 
$$
ed esiste un solo angolo $\theta$ che verifica la precedente uguaglianza.

# Spazio di Hilbert
Lo spazio di Hilbert è uno spazio pre-hilbertiano che, rispetto alla norma indotta dal prodotto scalare, è anche uno spazio metrico completo, ovvero è uno spazio di [[#Spazi normati|Banach]].

Si definisce con $\mathbb{L}^2$ lo spazio delle funzioni di quadrato sommabile, sono uno spazio di Hilbert e si può definire in questo spazio il **valore efficace**:
$$
V_{rms} \stackrel{\Delta}{=} \sqrt{ \frac{1}{T}\int_{0}^T v^2(t)dt }
$$
In questo spazio è anche possibile definire il prodotto scalare hermitiano:
$$
\langle f,g \rangle \stackrel{\Delta}{=} \frac{1}{T}\int_{0}^Tf(t) \check{g}(t)dt
$$
e di conseguenza una norma:
$$
||f|| = \sqrt{ \langle f,f \rangle  } =\sqrt{ \frac{1}{T}\int_{0}^T f^2(t)dt }
$$
dunque il valore efficace è una norma in uno spazio hilbertiano.

## Base dello spazio di Hilbert
Si può calcolare il prodotto scalare tra un generico vettore $\vec{x}$ di uno spazio di Hilbert e il termine $e^{jk\omega t}$:
$$
\left\langle  \vec{x}  \right\rangle_{k} = \left\langle  \vec{x},e^{j\omega k\tau}  \right\rangle  = \frac{1}{T} \int_{0}^T x(\tau)e^{-jk\omega \tau}d\tau
$$
quello ottenuto è per definizione il coefficiente della serie di Fourier di $\vec{x}$ di ordine $k$, coincide con la proiezione di $\vec{x}$ lungo la direzione $e^{j\omega k\tau}$, dunque una generica funzione $x(t)$ esprimibile in serie di Fourier è contenuta in uno spazio di Hilbert:
$$
x(t) = \sum_{k=-\infty}^{+\infty} \left\langle  \vec{x}  \right\rangle_{k}e^{jk\omega t} 
$$
dunque infiniti termini generano la funzione $x(t)$, questo concetto si può estendere al concetto di base, ovvero dati $N$ vettori $\{e_{1},e_{2},\dots,e_{N}\}\in H$ contenuti nello spazio di Hilbert, formano una base hilbertiana se:
$$
\begin{aligned}
\langle e_{i},e_{j} \rangle &= 0 \ \forall\ k\neq j \\
\langle e_{i},e_{j} \rangle &= 1 \ \forall\ k = j 
\end{aligned}
$$
ovvero sono linearmente indipendenti.

Questi vettori sono un sistema ortogonale completo e formano quindi una base dello spazio di Hilbert di dimensione infinita.
Costituiscono anche la base per le funzioni $\mathbb{L}^2$ che sono esprimibili in serie di Fourier, che può infatti esprimersi come combinazione lineare della base di Hilbert.

## Trasformata di Steinmetz
Il prodotto scalare nello spazio di Hilbert di ordine nullo $\left\langle  \vec{x}  \right\rangle_{0}$ viene chiamato *trasformata di Steinmetz*, restituisce uno scalare complesso, chiamato **fasore**. Dato che il prodotto scalare produce un isomorfismo nello spazio, si conserva la struttura algebrica tra le funzioni sinusoidali e i fasori.

## Teorema delle proiezioni
Sia definito uno spazio di Hilbert $H$ su un campo $\mathbb{K}$, un sottospazio $M\subset H$, per ogni vettore $\vec{x}$ appartenente allo spazio, esiste ed è unico il vettore proiezione di $\vec{x}$ su $M$:
$$
\forall\ \vec{x} \in H, \exists{!}\ \vec{m}_{0}:||\vec{x}-\vec{m}_{0}|| \leq ||\vec{x}-\vec{m}||\ \forall\ \vec{m}\in M
$$
Ovvero esiste un unico vettore che minimizza la distanza tra $\vec{x}$ e il sottospazio $M$, questo vettore è ortogonale al sottospazio e dunque a qualsiasi altro vettore di $M$. Ogni vettore dello spazio di Hilbert si può scomporre in una somma di due vettori, uno appartenente ad un sottospazio, l'altro ad esso ortogonale.

# Proprietà dei coefficienti della serie di Fourier
Si riporta i legame tra i coefficienti della serie bilatera e unilatera:
$$
C_{k} = \frac{A_{k}-jB_{k}}{2} \Rightarrow |C_{k}|^2 =  \frac{A_{k}^2+B_{k}^2}{4} 
$$
espressione delle due serie:
$$
v(t) = \sum_{k=1}^{+\infty} A_{k}\cos(k\omega t) + B_{k}\sin(k\omega t) = \sum_{k=1}^{+\infty} S_{k}\sin(k\omega t+\varphi_{k}) 
$$
Relazione con i valori efficaci:
$$
S_{k}^2 = A_{k}^2 + B_{k}^2 = 2\left[A_{k,\text{rms}}^2+B_{k,\text{rms}}^2\right] = 2S_{k,\text{rms}}^2
$$
Per la serie bilatera:
$$
2C_{k}^2 = \frac{A_{k}^2+B_{k}^2}{2} = A_{k,\text{rms}}^2 + B_{k,\text{rms}}^2 = S_{k,\text{rms}}^2
$$

Identità di Parseval:
$$
V_{\text{rms}} = \sqrt{ \sum_{k=1}^{+\infty}V_{k,\text{rms}}^2 }
$$
# Spazi affini
Si consideri un insieme $\mathbb{A}\neq 0$ e sia $\mathbb{K}-V$ uno spazio vettoriale $V$ sul campo $\mathbb{K}$, sia possibile un'applicazione $\Pi$ tra due spazi vettoriali, si definisce **spazio affine** associato allo spazio $V$ sul campo $\mathbb{K}$ la terna $(\mathbb{A},V,\Pi)$ con $\Pi:\mathbb{A}\times\mathbb{A}\to V$ se gode delle seguenti proprietà:
- L'applicazione $\Pi$ è suriettiva: $\forall\ P \in\mathbb{A},\forall\ \vec{v}\in V\ \exists{!}\ Q\in\mathbb{A}:\Pi(P,Q)=\vec{V}$
- Gode dell'identità di Charles: $P,Q,Z \in\mathbb{A}\Rightarrow \Pi(Q,Z)=\Pi(P,Q)+\Pi(Q,Z)$
Un'applicazione è suriettiva se e solo se ogni elemento di $B$ è immagine di almeno un elemento di $A$, ovvero tutti gli elementi di $B$ sono immagini di almeno un elemento di $A$, l'insieme immagine coincide col codominio della funzione.
$F:A\to B$.

Non vale il viceversa, l'applicazione inversa $\Pi^{-1}(P,Q)$ fornisce un sottoinsieme di $\mathbb{A}$, fornisce ovvero anche infinite coppie di $P$ e $Q$ in $\mathbb{A}$.
Fissato un punto $P$ e un vettore $\vec{V}\ \exists!\ Q : \Pi(P,Q)=\vec{v}$ ma dato $\vec{v}$ esistono infinite coppie di $P$ e $Q$ che forniscono $\vec{v}$.

L'applicazione $\Pi(P,Q)$ è detta segmento orientato di $PQ$, oppure vettore applicato in $P$ con estremo in $Q$ tale che:
$$
\vec{PQ} = Q-P
$$
e gode delle ulteriori proprietà:
- $\Pi(P,P)=0$
- $\Pi(P,Q)=0\Leftrightarrow P\equiv Q$
- $\Pi(P,Q)=-\Pi(Q,P)$

Come già espresso, l'applicazione $\Pi$ è suriettiva, tuttavia fissato un $P$, si considera l'applicazione indotta con $P$ fisso $\Pi_{P}(Q)=\vec{v}$ in questo caso $Q$ è unico quindi l'applicazione è biunivoca; viceversa dato $\vec{v}$ esiste un solo punto $Q_1$ raggiunto dal vettore $\vec{v}$ centrato in $P$ fissato.

Questo insieme è un isomorfismo, conserva la struttura algebrica, induce in $\mathbb{A}$ una struttura algebrica simile a quella degli spazi vettoriali, dunque la struttura algebrica di $\mathbb{A}$ verrà
indotta dalla struttura di $V$, dunque se $V$ ha dimensione $n$ anche $\mathbb{A}$ avrà dimensione $n$.

Lo spazio $(\mathbb{A},V,\Pi)$ in cui si è fissato il punto $P$ si dice spazio affine, se si considera una coppia data dal punto $O$ di $A$ e la base $B$, si può definire in questo spazio affine il seguente sistema $S$ fatto dalla base $B$ e il punto $O$. $B$ è uno spazio vettoriale di dimensione $n$, in $V$.
$$
S= (O,B)
$$
In questo spazio affine, ogni vettore $\vec{v}$ è sempre formato da componenti dello spazio vettoriale.
Fissati $P$ ed $O$, si può descrivere il punto $P$ rispetto ad $O$ mediante le sue coordinate.
Dunque i punti dello spazio $\mathbb{A}$ sono associati ai vettori applicati all'origine, con i vettori $\vec{v}$ pari a $P-O$ e le componenti di $\vec{v}$ sono le sue coordinate rispetto ad $O$.

## Sottospazio di Hilbert
Si consideri uno spazio $\mathbb{R}^3$ di Hilbert, si definisce il prodotto scalare:
$$
\langle x,y \rangle \stackrel{\Delta}{=} \sum_{k=1}^{3}x_{k}y_{k}
$$
che induce una metrica ed una distanza.
Si definisce uno spazio affine associato a $\mathbb{R}^3$ un piano ortogonale ad un dato vettore $\vec{w}$ tale che $\vec{w}$ sia ortogonale a tutti i vettori $PQ$ giacenti sul piano.

$\vec{w}=a\hat{i}+b\hat{j}+c\hat{k}$ con $\hat{i},\hat{j},\hat{k}$ una base hilbertiana dato che i tre versori sono tra loro ortogonali. I coefficienti $a,b,c$ sono anch'essi costanti perché coefficienti di $\vec{w}$ rispetto alla base, si definiscono le coordinate dei punti $P$ e $Q$ rispetto l'origine ovvero:
$P=(x,y,z)$ e $Q=(x_{Q},y_{Q},z_{Q})$, l'applicazione del prodotto scalare restituisce:
$$
\left\langle  \vec{w},P-Q  \right\rangle = a(x-x_{Q})  + b(y-y_{Q}) + c(z-z_{Q}) = d
$$
Fissato $Q$ saranno presenti infiniti punti $P$ giacenti sul piano, si ottiene proprio l'espressione del piano ortogonale al vettore $\vec{w}$.
Se $Q$ coincide con l'origine allora $d=0$, si ottiene un piano ortogonale a $\vec{w}$ che passa per l'origine, dunque il prodotto scalare fornisce l'equazione di un iperpiano.

### Spazio delle funzioni di quadrato sommabile
Si indica con $\vec{v}$ l'elemento di un campo su $\mathbb{R}^3$ con componenti $v_{1},v_{2},v_{3}$ funzioni sinusoidali sfasate tra loro di 120°.
Si riprende la precedente equazione del piano, se il punto $Q$ giace nell'origine avrà componenti nulle e di conseguenza l'equazione del piano è del tipo:
$$
ax+by+cz = 0
$$
o più in generale:
$$
\sum_{k=1}^n a_{k}x_{k}=0
$$
per un iperpiano in $\mathbb{R}^n$ di dimensione $n$.

Nel caso di un [[sistema elettrico]] trifase, si può dunque considerare un generico vettore di tensione così definito:
$$
\vec{v} = \left[v_{1}(t),v_{2}(t),v_{3}(t)\right]^T
$$
Espressi in un riferimento cartesiano $\mathbb{R}^3$ tale che $\vec{w}=\hat{i}+\hat{j}+\hat{k}$ il vettore diventa:
$$
\vec{v} = v_{1}\hat{i} + v_{2}\hat{j} + v_{3}\hat{k}
$$
Se si annulla il prodotto scalare tra $\vec{v}$ e $\vec{w}$ allora si dice che il sistema di tensioni è simmetrico ovvero:
$$
\left\langle  \vec{v},\vec{w}  \right\rangle =v_{1}+v_{2}+v_{3} =0  
$$
dunque $\vec{w}\perp \vec{v}:\vec{v}\neq0$ cioè $\vec{v}$ giace sul piano ortogonale a $\vec{w}$ che passa per l'origine degli assi.

Questa considerazione vale per qualsiasi vettore tale che la somma delle sue componenti sia nulla, ad esempio la somma di correnti che incidono in un nodo sarà necessariamente nulla, si possono allora rappresentare mediante un vettore che giace sul piano ortogonale al vettore composto dalla somma dei versori della base; in questo modo non sono più necessarie tre componenti per rappresentare il vettore ma solo due (la terza è sostituita dal vincolo di somma nulla, non si è ridotto il grado di libertà ma si usa solo una rappresentazione diversa).

# Rappresentazione del vettore di tensione con due componenti
Si definisce una terna di tensioni simmetriche e sinusoidali nel seguente modo:
$$
v_{k} = \sqrt{ 2 }V_{\Delta} \cos\left( \omega t - \frac{2k\pi}{3} \right)\quad k=0,1,2
$$
Si definisce un primo versore $\vec{v}_{d}$ che giace sul piano:
$$
\vec{v}_{d} = \frac{\vec{v}}{||\vec{v}||}
$$
con $\vec{v}=[v_{1},v_{2},v_{3}]$ mentre il modulo:
$$
\begin{aligned}
||\vec{v}|| &= \sqrt{ (\sqrt{ 2 }V_{\Delta})^2 \left[ \cos^2\omega t + \cos^2\left( \omega t-\frac{2\pi}{3} \right) + \cos^2\left( \omega t - \frac{4\pi}{3} \right) \right] } = \\
&= \sqrt{ 2 }V_{\Delta} \sqrt{ \frac{1}{2} + \frac{\cos 2\omega t}{2} + \frac{1}{2} + \frac{\cos\left( 2\omega t-\frac{2\pi}{3} \right)}{2} + \frac{1}{2} + \frac{\cos\left( 2\omega t-\frac{4\pi}{3} \right)}{2} } = \\
&= \sqrt{ 2 }V_{\Delta} \frac{\sqrt{ 3 }}{\sqrt{ 2 }} = \sqrt{ 3 }V_{\Delta}
\end{aligned}
$$
Raggruppando il numeratore e il denominatore:
$$
\begin{aligned}
\hat{v}_{d} &=  \frac{\sqrt{ 2 }V_{\Delta}\left[ \cos (\omega t)\hat{i} + \cos\left( \omega t-\frac{2\pi}{3} \right)\hat{j} +\cos\left( \omega t - \frac{4\pi}{3} \right)\hat{k}  \right]}{\sqrt{ 3 }V_{\Delta}} = \\
&= \sqrt{ \frac{2}{3} }\left[ \cos (\omega t)\hat{i} + \cos\left( \omega t-\frac{2\pi}{3} \right)\hat{j} +\cos\left( \omega t - \frac{4\pi}{3} \right)\hat{k}  \right]
\end{aligned}
$$
Il secondo vettore, chiamato $\hat{v}_{q}$ deve giacere anch'esso nello stesso piano ma ortogonale a $\hat{v}_{d}$, dunque si sfrutta la formula di Poisson, che ci garantisce queste caratteristiche mediante la derivata del vettore stesso:
$$
\hat{v}_{q} = \frac{\frac{d}{dt}\hat{v}_{d}}{|| \frac{d}{dt} \hat{v}_{d} ||}
$$
Si calcola il numeratore:
$$
\frac{d}{dt}\hat{v}_{d} = -\frac{\sqrt{ 2 }\cancel{V_{\Delta}}\left[ \omega \sin (\omega t)\hat{i} + \omega \sin\left( \omega t-\frac{2\pi}{3} \right)\hat{j} +\omega \sin\left( \omega t-\frac{4\pi}{3} \right)\hat{k}\right]}{\frac{\cancel{\sqrt{ 2 }V_{\Delta}}\sqrt{ 3 }}{\cancel{\sqrt{ 2 }}}}
$$
mentre il modulo della derivata:
$$
\left|\left| \frac{d}{dt} \hat{v}_{d} \right|\right| = \frac{\sqrt{ \omega^2\sin^2(\omega t)+\omega^2\sin^2\left( \omega t-\frac{2\pi}{3} \right)+\omega^2\sin^2\left( \omega t-\frac{4\pi}{3} \right) }}{\frac{\sqrt{ 2 }}{\sqrt{ 3 }}} = \sqrt{ \frac{3}{2} }\omega
$$
effettuando il rapporto:
$$
\hat{v}_{q} = -\left[  \sin (\omega t)\hat{i} +  \sin\left( \omega t-\frac{2\pi}{3} \right)\hat{j} + \sin\left( \omega t-\frac{4\pi}{3} \right)\hat{k}\right]
$$

Infine si riporta il terzo versore, che individua il piano pari alla somma dei tre versori (o al versore del vettore somma $\vec{w}$):
$$
\hat{v}_{\gamma} = \frac{\vec{w}}{||\vec{w}||} = \frac{\hat{i}+\hat{j}+\hat{k}}{\sqrt{ 3 }}
$$
Con questi tre versori si può ricavare la matrice di cambiamento di base tra il riferimento cartesiano $(\hat{i},\hat{j},\hat{k})$ e quello ortonormale di Park $(\hat{v}_{d},\hat{v}_{q},\hat{v}_{\gamma})$:
$$
P_{\perp} = \sqrt{ \frac{2}{3} }
\begin{pmatrix}
\cos (\omega t) & \cos\left( \omega t-\frac{2\pi}{3} \right) & \cos\left( \omega t-\frac{4\pi}{3} \right)\\ \\
-\sin(\omega t) & - \sin \left( \omega t-\frac{2\pi}{3} \right) & -\sin\left( \omega t-\frac{4\pi}{3} \right)\\  \\
\frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }}
\end{pmatrix}
$$
è una matrice ortogonale perché moltiplicata per la sua inversa fornisce come risultato la matrice identità, ovvero la sua inversa coincide con la trasposta.

Dunque i vettori $\hat{v}_{d}$ e $\hat{v}_{q}$ giacciono su un piano ortogonale a $\hat{v}_{\gamma}$ e sono ortogonali tra loro; entrambi ruotano su una circonferenza con pulsazione $\omega$ in verso antiorario, formano un sistema di riferimento ortogonale rotante.

Posso riportare il vettore di tensione $\vec{v}$ di modulo pari a $\sqrt{ 3 }V_{\Delta}$ nel nuovo riferimento di Park:
$$
\begin{bmatrix}
v_{d} \\ v_{q} \\ v_{\gamma}
\end{bmatrix} = 
\sqrt{ \frac{2}{3} }\cdot 
\begin{pmatrix}
\cos (\omega t) & \cos\left( \omega t-\frac{2\pi}{3} \right) & \cos\left( \omega t-\frac{4\pi}{3} \right)\\ 
-\sin(\omega t) & - \sin \left( \omega t-\frac{2\pi}{3} \right) & -\sin\left( \omega t-\frac{4\pi}{3} \right)\\  
\frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }}
\end{pmatrix}\cdot
\begin{bmatrix}
\sqrt{ 2 }V_{\Delta}\cos (\omega t) \\ 
\sqrt{ 2 }V_{\Delta}\cos \left( \omega t - \frac{2\pi}{3} \right) \\
\sqrt{ 2 }V_{\Delta}\cos \left( \omega t-\frac{4\pi}{3} \right)
\end{bmatrix}
$$
si ottiene:
$$
\begin{aligned}
v_{d} &= \sqrt{ \frac{2}{3} }\sqrt{ 2 }V_{\Delta} = \frac{2\sqrt{ 3 }}{3}V_{\Delta}\\
v_{q} &= 0 \\
v_{\gamma} &= 0
\end{aligned}
$$
Dunque nel nuovo riferimento il vettore è fisso, il modulo resta invariato, anche se cambia l'ampiezza delle sue componenti:
$$
||\vec{v}|| = \sqrt{ 3} V_{\Delta} = ||v_{a,b,c}||
$$

## Riferimento di Clarke
Fissando un istante di tempo $t=0$ si può ricavare un sistema di riferimento fisso nello spazio e ortonormale:
$$
C_{T} = { \frac{2}{3} } 
\begin{pmatrix}
1 & \cos\left( \frac{2\pi}{3} \right) & \cos\left( \frac{4\pi}{3} \right)  \\
0 & \sin\left( \frac{2\pi}{3} \right) & \sin\left( \frac{4\pi}{3} \right) \\ 
\frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }}
\end{pmatrix}
$$
La matrice è ancora ortogonale perché deriva dalla precedente, che era ortogonale per ogni $t$.
La matrice $C_{T}$ permette il passaggio dal sistema di riferimento cartesiano a quello ortonormale di Clarke.

Se si fa coincidere il piano di Clarke $\Sigma$ con quello di Gauss si può utilizzare la seguente notazione:
$$
\begin{aligned}
v_{\alpha} &= \mathrm{Re}\vec{v}\\
v_{\beta} &= \mathrm{Im}\vec{v}
\end{aligned}
$$
applicando la definizione si ottengono le componenti di un generico vettore di tensione nel riferimento di Clarke a partire dal riferimento cartesiano:
$$
\begin{bmatrix}
v_{\alpha}\\ v_{\beta}\\ v_{\gamma}
\end{bmatrix} = 
{ \frac{2}{3} } 
\begin{pmatrix}
1 & \cos\left( \frac{2\pi}{3} \right) & \cos\left( \frac{4\pi}{3} \right)  \\
0 & \sin\left( \frac{2\pi}{3} \right) & \sin\left( \frac{4\pi}{3} \right) \\ 
\frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }}
\end{pmatrix} \cdot
\begin{bmatrix}
v_{1}(t) \\ v_{2}(t) \\ v_{3}(t)
\end{bmatrix}
$$
dunque:
$$
\begin{aligned}
v_{\alpha} &= \frac{2}{3}\left[ v_{1}+v_{2}\cos\left( \frac{2\pi}{3} \right) + v_{3}\cos\left( \frac{4\pi}{3} \right) \right]\\
v_{\beta} &= \frac{2}{3}\left[v_{2}\sin\left( \frac{2\pi}{3} \right) + v_{3}\sin\left( \frac{4\pi}{3} \right) \right] \\
v_{\gamma} &= \frac{1}{3} \left[v_{1} +v_{2} + v_{3}\right]
\end{aligned}
$$
Riportati nel piano di Gauss, i primi due vettori si riscrivono:
$$
\begin{aligned}
\vec{v}&= v_{\alpha} + jv_{\beta} = \frac{2}{3}\left[ v_{1}+v_{2}\left( \cos\left( \frac{2\pi}{3} \right) + j\sin\left( \frac{2\pi}{3} \right) \right) + v_{3}\left( \cos\left( \frac{4\pi}{3} \right) + j\sin\left( \frac{4\pi}{3} \right) \right) \right] =\\
&= \frac{2}{3} \left[v_{1}+v_{2}e^{j{2}\pi/3} + v_{3}e^{j{4}\pi/3}\right]
\end{aligned}
$$
Ma quella ottenuta è proprio la definizione di componente simmetrico.
Nel riferimento di Clark o Park si possono scrivere i vettori utilizzando due componenti e non più tre, semplificando la trattazione, inoltre i vettori che rappresentano grandezze sinusoidali nel riferimento cartesiano, diventano costanti in quello di Park.
Questo può essere comodo per applicare ad esempio il [[modello averaged]] ad un inverter che fornisce in uscita una tensione sinusoidale, in questo caso lo schema di controllo diventa lineare e si può applicare il [[modello averaged]].

## Prodotto scalare
La potenza istantanea è definita come il prodotto tra tensione e corrente nel tempo, per grandezze multidimensionali si usa la definizione di prodotto scalare euclideo:
$$
p(t) = \left\langle  \vec{v},\vec{i}  \right\rangle \stackrel{\Delta}{=} \sum_{k=1}^3 v_{k}i_{k}
$$
mentre la potenza attiva è definita come il prodotto scalare hermitiano:
$$
P_{\text{att}} \stackrel{\Delta}{=} \left\langle  \vec{v},\vec{i}  \right\rangle = \frac{1}{T} \int_{0}^T \vec{v}^T \cdot\vec{i}\ dt  = \frac{1}{T} \left\{  \int_{0}^T v_{1},i_{1}dt + \int_{0}^T v_{2},i_{2}dt +\dots+\int_{0}^T v_{n},i_{n}dt \right\}
$$
Se nel cambio di riferimenti si conservano le norme e gli angoli, allora è possibile semplificare il calcolo della potenza:
$$
\begin{aligned}
P(t) = v_{d}i_{d} + v_{q}i_{q}\quad &\text{nel riferimento di Park} \\
P(t) = v_{\alpha}i_{\alpha} + v_{\beta}i_{\beta}\quad &\text{nel riferimento di Clarke}
\end{aligned}
$$
Moltiplicando per $\sqrt{ \frac{2}{3} }$ si rende il sistema di riferimento ortonormale e dunque si eguagliano i moduli delle potenze calcolate nel riferimento cartesiano e in quelli di Park e Clarke.

Per passare dal riferimento di Clarke a quello di Park si esegue la seguente operazione:
$$
\vec{v}_{dq} = \vec{v}_{\alpha,\beta} e^{-j\theta}
$$
o l'inversa:
$$
\vec{v}_{\alpha,\beta} = \vec{v}_{dq} e^{j\theta}
$$
# Potenze generalizzate
Akagi introduce nel 1977 il concetto di potenza istantanea nel riferimento di Clarke, in un sistema trifase a quattro fili, la somma delle correnti lungo le tre fasi può essere diversa da zero, così come la somma delle tensioni.
Le quattro potenze erano così definite:
$$
\begin{pmatrix}
P \\ q_{\alpha} \\ q_{\beta} \\ q_{0}
\end{pmatrix} = 
\begin{pmatrix}
v_{\alpha} & v_{\beta} & v_{0} \\
0& -v_{0} & v_{\beta} \\
v_{0}& 0 & -v_{\alpha} \\
-v_{\beta} & v_{\alpha} & 0
\end{pmatrix}\cdot
\begin{pmatrix}
i_{\alpha}\\ 
i_{\beta} \\
i_{0}
\end{pmatrix}
$$
Il primo termine è la potenza attiva istantanea:
$$
P(t) = v_{\alpha}i_{\alpha} + v_{\beta}i_{\beta} + v_{0}i_{0}
$$
i rimanenti termini:
$$
\begin{aligned}
q_{\alpha} &= -v_0i_{\alpha} + v_{\beta}i_{0} \\
q_{\beta} &= v_{0}i_{\alpha} - v_{\alpha}i_{0} \\
q_{0} &= -v_{\beta}i_{\alpha} + v_{\alpha}i_{\beta}
\end{aligned}
$$
Se il sistema è trifase, sinusoidale e simmetrico:
$$
\begin{aligned}
q_{\alpha} &= q_{\beta} = 0\qquad q_{0}\neq {0}\\
P &= v_{\alpha}i_{\alpha} + v_{\beta}i_{\beta}
\end{aligned}
$$
In questo caso la potenza istantanea coincide con la potenza attiva:
$$
\begin{aligned}
p(t) &= \sqrt{ 2 }V\sqrt{ 2 }I \left[ \cos \omega t\cdot \cos (\omega t-\varphi) + \cos \left( \omega t-\frac{2\pi}{3} \right)\cdot \cos\left( \omega t-\frac{2\pi}{3}-\varphi \right) + \right. \\
& + \left. \cos\left( \omega t-\frac{4\pi}{3} \right)\cdot \cos\left( \omega t-\frac{4\pi}{3}-\varphi \right) \right]
\end{aligned}
$$
ricordando che 
$$
\cos \alpha \cos\beta = \frac{\cos(\alpha+\beta)+\cos(\alpha-\beta)}{2}
$$
si ottiene
$$
p(t) = 2VI \frac{3}{2}\cos \varphi = 3VI\cos \varphi
$$
con $V$ la tensione stellata, si è ricavata la formula della potenza attiva su un carico trifase simmetrico ed equilibrato.

Per il calcolo della potenza $q_{0}$ si riportano le tensioni e le correnti di asse diretto e in quadratura:
$$
\begin{aligned}
v_{\alpha} &= \sqrt{ 2 }V\cos \omega t\quad i_{\alpha} = \sqrt{ 2 }I\cos(\omega t-\varphi) \\
v_{\beta} &= \sqrt{ 2 }V\sin \omega t \quad i_{\beta} = \sqrt{ 2 }I\sin(\omega t-\varphi)
\end{aligned}
$$
dunque
$$
q_{0} = 2VI[\cos \omega t\sin(\omega t-\varphi)-\sin \omega t\cos(\omega t-\varphi)] = -2VI \frac{3}{2} \sin \varphi = -3VI\sin \varphi
$$
indica proprio la potenza reattiva assorbita dal sistema.

Se il sistema non è equilibrato, le componenti omopolari saranno diverse da zero, dunque si avrà un vettore di potenze $\vec{q}= \vec{v}_{\alpha,\beta}\times \vec{i}_{\alpha,\beta}= q(q_{\alpha},q_{\beta},q_{0})$ così definito:
$$
\begin{vmatrix}
\hat{e}_{\alpha} & \hat{e}_{\beta} & \hat{e}_{0}\\ 
v_{\alpha} & v_{\beta} &v_{0}\\  
i_{\alpha} & i_{\beta} & i_{0} 
\end{vmatrix}
$$
Coincide con un vettore ortogonale al piano $\alpha,\beta$ quando $i_{0}$ e $v_{0}$ sono nulle.

Nel riferimento di Park la formulazione è analoga:
$$
P = v_{d}i_{d}+v_{q}i_{q}+v_{\gamma}i_{\gamma}
$$
se il sistema è simmetrico ed equilibrato:
$$
v_{q}=0, v_{\gamma}=0 \Rightarrow P = v_{d}i_{d}
$$
e 
$$
q_{\gamma} = v_{d}i_{q} - v_{q}i_{d}
$$
che diventa
$$
q_{\gamma} = v_{d}i_{q}
$$
se la rete è simmetrica.
La variazione della componente di corrente $i_{d}$ permette dunque la regolazione di $P$ senza variare $q_{\gamma}$ e viceversa.

## Prodotto scalare hermitiano
Si definisce lo spazio vettoriale su cui verrà definito il prodotto scalare euclideo:
$$
\left( \coprod^2_T \right)^n = \coprod_{T}^2\times\coprod_{T}^2\times\dots \times\coprod_{T}^2
$$
ovvero il prodotto cartesiano delle funzioni di quadrato sommabile di periodo $T$, in questo caso $\vec{v},\vec{i}\in\left( \coprod_{T}^2 \right)^3$.

Se si esegue il prodotto scalare in questo spazio si ottiene la potenza istantanea:
$$
\left\langle  \vec{v},\vec{i}  \right\rangle \stackrel{\Delta}{=} \left.\sum_{k=1}^{n} v_{k}i_{k}\right|_{n=3} = v_{1}i_{i} + v_{2}i_{2} + v_{3}i_{3}
$$
Se si costruisce uno spazio di Banach, in cui si introduce un prodotto scalare che introduce a sua volta una metrica, si definisce uno spazio di Hillbert.

La norma introdotta da questo prodotto scalare:
$$
||\vec{v}|| \stackrel{\Delta}{=} \sqrt{ \left\langle  \vec{v},\vec{v}  \right\rangle  } = \sqrt{ \vec{v}\cdot \vec{v}^T } = \sqrt{ \sum_{k=1}^{n} v_{k}^2 }
$$
non coincide con il valore efficace come invece accade con il prodotto scalare hermitiano:
$$
\left\langle  \vec{v},\vec{i}  \right\rangle =\frac{1}{T} \int_{0}^T \vec{v}\cdot \hat{i}\ d\tau
$$
il vettore di corrente è reale dunque il suo coniugato coincide con il vettore stesso, se ne considera il trasposto:
$$
\left\langle  \vec{v},\vec{i}^T  \right\rangle \stackrel{\Delta}{=} \frac{1}{T}\int_{0}^T \vec{v}\cdot \vec{i}^T\ d\tau = \frac{1}{T} \int_{0}^T [v_{1}i_{1} +v_{2}i_{2} + \dots  + v_{n}i_{n}]\  d\tau
$$
Per la linearità dell'integrale si stanno sommando le potenze attive per ogni fase.
La norma introdotta da questo prodotto scalare:
$$
||\vec{v}|| = \sqrt{ \left\langle  \vec{v},\vec{v}  \right\rangle  } = \sqrt{ \frac{1}{T}\int_{0}^T \vec{v}\cdot \vec{v}^T\  d\tau} = \sqrt{ \frac{1}{T} \left[ \int_{0}^T v_{1}^2\ d\tau +  \int_{0}^T v_{2}^2\ d\tau + \dots +  \int_{0}^T v_{n}^2\ d\tau \right] }
$$
Dunque il valore efficace del vettore è pari alla somma dei valori efficaci delle sue componenti.

## Disuguaglianza di Cauchy-Scwartz
Dalle proprietà degli spazi vettoriali:
$$
\left\langle  \vec{v},\vec{i}  \right\rangle \leq ||\vec{v}||\cdot||\vec{i}|| 
$$
L'identità di Lagrange fornisce la differenza fra i due termini:
$$
||\vec{v}||^2\cdot||\vec{i}||^2 = \left\langle  \vec{v},\vec{i}  \right\rangle^2 + \frac{1}{2T} \sum_{\rho=1}^n \sum_{\sigma=1}^n \int_{0}^T \int_{0}^T (v_{\rho}i_{\sigma}-v_{\sigma}i_{\rho})^2d\tau dt
$$
Il primo termine coincide con la potenza apparente  $V^2\cdot I^2=S^2=P_{att}^2+Q^2$.
Ci si aspetta che il secondo termine (gli integrali) sia pari alla potenza reattiva.
Si esplicita il secondo termine in forma matriciale:
$$
\begin{aligned}
\left[ \vec{v}^T\cdot \vec{i} - \vec{i}^T\vec{v} \right] &= \begin{bmatrix}
v_{1}i_{1} & v_{1}i_{2} & v_{1}i_{3}  \\
v_{2}i_{1} & v_{2}i_{2} & v_{2}i_{3} \\
v_{3}i_{1} & v_{3}i_{2} & v_{3}i_{3}
\end{bmatrix} -
\begin{bmatrix}
i_{1}v_{1} & i_{1}v_{2} & i_{1}v_{3} \\
i_{2}v_{1} & i_{2}v_{2} & i_{2}v_{3} \\
i_{3}v_{1} & i_{3}v_{2} & i_{3}v_{3}
\end{bmatrix} =\\
&= \begin{bmatrix}
0 & v_{1}i_{2}-i_{1}v_{2} & v_{1}i_{3}-i_{1}v_{3} \\
v_{2}i_{1} - i_{2}v_{1} & 0 & v_{2}i_{3}-i_{2}v_{3}  \\
v_{3}i_{1}-i_{3}v_{1} &  v_{3}i_{2}-i_{3}v_{3} & 0
\end{bmatrix}
\end{aligned}
$$
ottenendo una matrice antisimmetrica perché $a_{i,j} = -a_{\hat{j},\hat{i}}$ con $\hat{i}\neq i$ e $\hat{j}\neq j$, è anche isomorfa in $\mathbb{R}^3$.

Si definisce con **norma di Frobenius** di una matrice, la sommatoria al quadrato di tutti i suoi elementi.
Portando l'integrale all'interno della precedente matrice, si associa la potenza reattiva generalizzata alla norma di Frobenius della matrice degli integrali delle differenze.

Per come è definita però non conserva il segno e dunque non rispetta il principio di conservazione dell'energia.

## Prodotto esterno
Per come sono definiti gli elementi $v_{\sigma}$ e $i_{\rho}$ sono ortogonali fra loro, si può definire un prodotto *esterno* che non sarà un prodotto scalare ma un *bi-vettore* che ha per ampiezza l'area del parallelepipedo ottenuto da $V_{\rho}\cdot I_{\sigma}$ (la stessa del prodotto vettoriale) ma il vettore giace nel piano stesso, è ancora un'area orientata ma la direzione è interna al piano.

Nell'algebra esterna vale la seguente regola, applicata ai versori del riferimento cartesiano:
$$
\hat{i},\hat{i}=1\qquad \hat{i},\hat{j}=-\hat{j},\hat{i}
$$
dunque siano $\vec{a}$ e $\vec{b}$ due vettori in questo riferimento definiti con due coefficienti:
$$
\vec{a}= a_{1}\hat{i} + a_{2}\hat{j}\qquad \vec{b}=b_{1}\hat{i} + b_{2}\hat{j} 
$$
il loro prodotto:
$$
\begin{aligned}
\vec{a}\vec{b}&= a_{1}\hat{i}b_{1}\hat{i} + a_{1}\hat{i}b_{2}\hat{j}  +a_{2}\hat{j}b_{1}\hat{i} +a_{2}\hat{j}b_{2}\hat{j}=\\
&=a_{1}b_{1}\cancel{\hat{i}\hat{i}} + a_{2}b_{2}\cancel{\hat{j}\hat{j}} + (a_{1}b_{2}-a_{2}b_{1})\hat{i}\hat{j} = \\
&= \left\langle  \vec{a},\vec{b}  \right\rangle + \vec{a} \land \vec{b} 
\end{aligned}
$$
con $\vec{a}\land \vec{b}$ si definisce il prodotto esterno tra i due vettori, il cui risultato rappresenta un parallelogramma con lati i due vettori e area pari al prodotto vettoriale di questi due.

Dalla disuguaglianza di Cauchy-Swartz si può definire l'angolo di un prodotto scalare:
$$
\cos \theta \stackrel{\Delta}{=} \frac{\left\langle  \vec{v},\vec{i}  \right\rangle }{||\vec{v}||\cdot||\vec{i}||} \leq 1
$$
dunque il segno di $P$ dipende da quest'angolo mentre il segno di $Q$, definita con la norma di Frobenius della matrice $\mathbf{R}$ è sempre positivo.
Questa matrice $\mathbf{R}^{3\times 3}$ è emisimmetrica e può essere associata in maniera biunivoca ad un vettore di tre elementi, pari a quelli del triangolo superiore o inferiore della matrice, dunque
$$
q_{n} = \begin{bmatrix}
v_{1}i_{2} - i_{1}v_{2} \\
v_{1}i_{3}-i_{1}v_{3} \\
v_{2}i_{3}-i_{2}v_{3}
\end{bmatrix}
$$
Nel caso di uno spazio $\mathbb{R}^3$ il prodotto vettoriale e il prodotto esterno coincidono, il valore dell'area del parallelepipedo è proiettata sul vettore ortogonale al piano stesso.
Se si proietta il vettore $q_{n}$ lungo un vettore facente parte della base dello spazio, allora tutte le altre componenti saranno nulle, il segno dell'unica componente diversa da zero definirà la natura della potenza reattiva se induttiva o capacitiva.
Gli elementi della matrice associata a questo vettore, costruito nel seguente modo rispettano il teorema di Tellegen.

Nel riferimento di Clarke
$$
\begin{aligned}
v_{\alpha} &= \sqrt{ 3 }V\cos \omega t & v_{\beta}&=\sqrt{ 3 }V\sin \omega t\\
i_{\alpha} &= \sqrt{ 3 }I\cos (\omega t-\varphi) & i_{\beta}&=\sqrt{ 3 }I\sin (\omega t-\varphi)
\end{aligned}
$$
Si vuole costruire la matrice $\mathbf{R}$ per il calcolo della potenza reattiva:
$$
\mathbf{R} = \frac{1}{2T^2} \int_{0}^T \int_{0}^T [v_{\alpha\beta}^T i_{\alpha\beta} - i_{\alpha\beta}^T v_{\alpha\beta}]d\tau dt
$$
dunque
$$
v_{\alpha\beta}^T i_{\alpha\beta} = \begin{bmatrix}
v_{\alpha}i_{\alpha} & v_{\alpha}i_{\beta} & 0 \\
v_{\beta}i_{\alpha} & v_{\beta}i_{\beta} & 0 \\
0&0&0
\end{bmatrix} \qquad
i_{\alpha\beta}^T v_{\alpha\beta} = \begin{bmatrix}
i_{\alpha}v_{\alpha} & i_{\alpha}v_{\beta} & 0 \\
i_{\beta}v_{\alpha} & i_{\beta}v_{\beta} & 0 \\
0&0&0
\end{bmatrix}
$$
la cui differenza:
$$
[v_{\alpha\beta}^T i_{\alpha\beta} - i_{\alpha\beta}^T v_{\alpha\beta}] = \begin{bmatrix}
0 & v_{\alpha}i_{\beta}-i_{\alpha}v_{\beta} & 0 \\
v_{\beta}i_{\alpha} - i_{\beta}v_{\alpha} & 0 & 0 \\
0&0&0
\end{bmatrix}
$$
sostituendo con i termini trigonometrici si ricava $\mathbf{R}'$:
$$
\begin{aligned}
\mathbf{R'} &= 
\begin{bmatrix}
0 & 3VI[\cos \omega t\sin(\omega t-\varphi) - \sin \omega t\cos(\omega t-\varphi)] & 0 \\
 3VI[\sin \omega t\cos(\omega t-\varphi) - \cos \omega t\sin(\omega t-\varphi)] & 0 & 0 \\
0&0&0
\end{bmatrix} = \\
&= \begin{bmatrix}
0 & -3VI\sin \varphi & 0  \\
3VI\sin \varphi &0 &0 \\
0 & 0  &0
\end{bmatrix}
\end{aligned}
$$
dunque
$$
\mathbf{R} = \begin{bmatrix}
0 & -\frac{3}{2}VI\sin \varphi \\
\frac{3}{2}VI\sin \varphi &0
\end{bmatrix}
$$
la cui norma
$$
||\mathbf{R}||^2 = \frac{2(3VI\sin \varphi)}{4} \Rightarrow Q_{i} = \left|\frac{3VI\sin \varphi}{\sqrt{ 2 }}\right| \Rightarrow Q = ||\mathbf{R}||\sqrt{ 2 }
$$
in questo caso il $\sin \varphi$ ci garantisce il segno della potenza.

## Rifasamento
Per rifasare un impianto è necessario minimizzare la norma della corrente assorbita dall'utente, a pari potenza attiva assorbita.
$$
\min\left\{ \vec{I} \right\}:\left\langle  \vec{v},\vec{i}  \right\rangle =P 
$$
scomponendo:
$$
\begin{aligned}
\left\langle  \vec{v},\vec{i}_{1}  \right\rangle &=P_{1}\\
\left\langle  \vec{v},\vec{i}_{2}  \right\rangle &=P_{2}\\
&\vdots\\
\left\langle  \vec{v},\vec{i}_{n}  \right\rangle &=P_{n}
\end{aligned}
$$
Dato uno spazio di Hilbert, esiste un sottospazio $\mathcal{M}$ dei vettori di tensione $\vec{v}_{1},\vec{v}_{2},\dots, \vec{v}_{m}\in\mathcal{M}$ tali che essi siano una base per $\vec{v}$ che permettono la *ortonormalizzazione di Gransmith*:
$$
\vec{I}_{a} = \sum_{k=1}^m \beta_{k}\vec{v}_{k}
$$
ovvero:
$$
\begin{aligned}
\beta_{1}\left\langle  \vec{v}_{1},\vec{v}_{1}  \right\rangle + \beta_{2}\left\langle  \vec{v}_{2},\vec{v}_{1}  \right\rangle  +& \dots + \beta_{n}\left\langle  \vec{v}_{n},\vec{v}_{1}  \right\rangle =P_{1} \\
\beta_{1}\left\langle  \vec{v}_{1},\vec{v}_{2}  \right\rangle + \beta_{2}\left\langle  \vec{v}_{2},\vec{v}_{2}  \right\rangle  + & \dots + \beta_{n}\left\langle  \vec{v}_{n},\vec{v}_{2}  \right\rangle =P_{2} \\
& \vdots\\
\beta_{1}\left\langle  \vec{v}_{1},\vec{v}_{n}  \right\rangle + \beta_{2}\left\langle  \vec{v}_{2},\vec{v}_{n}  \right\rangle  + & \dots + \beta_{n}\left\langle  \vec{v}_{n},\vec{v}_{n}  \right\rangle =P_{n} 
\end{aligned}
$$
Nello spazio $\mathbb{R}^3$ le componenti di $\vec{I}_{a}$ corrispondono tutte ad una proiezione sullo stesso piano e dunque alla stessa $P$.

Si definisce la corrente in eccesso
$$
I_{\text{ecc}}=\vec{I}-\vec{I}_{a}
$$
e i due termini sono tra loro ortogonali, dunque si può applicare pitagora:
$$
I^2 = I^2_{a} + I^2_{\text{ecc}}
$$
Iniettando una corrente pari a $-I_{\text{ecc}}$si può compensare interamente il sistema:
$$
||I||^2 = ||I_{a}||^2 + ||I_{\text{ecc}}||^2 \Rightarrow
||V||^2||I||^2 = ||V||^2||I_{a}||^2 + ||V||^2||I_{\text{ecc}}||^2
$$
ovvero
$$
S^2 = P_{\text{att}}^2 + Q^2
$$

# Passaggio da Clarke a Park
Si riporta il passaggio dal sistema di riferimento di Clarke a quello di Park:
$$
\begin{aligned}
\vec{v}_{d,q} &= \vec{v}_{\alpha,\beta}e^{-j\theta}\\
\theta &= \theta_{0} + \int_{0}^t \omega(\tau) d\tau
\end{aligned}
$$
Dal sistema di riferimento cartesiano a Clarke ortogonale invece si utilizza la seguente matrice:
$$
C =\frac{2}{3} \begin{pmatrix}
1 & -\frac{1}{2} & -\frac{1}{2}  \\
0 & \frac{\sqrt{ 3 }}{2} & -\frac{\sqrt{ 3 }}{2} \\
\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{pmatrix}
$$
dunque:
$$
\begin{bmatrix}
v_{\alpha}  \\
v_{\beta}
\end{bmatrix} = C
\begin{bmatrix}
v_{a} \\
v_{b} \\
v_{c}
\end{bmatrix}
$$
sviluppando il primo termine:
$$
v_{\alpha} = \left( v_{a}-\frac{v_{b}}{2} - \frac{v_{c}}{2} \right)\cdot \frac{2}{3}
$$
ricordando che il sistema è simmetrico:
$$
v_{a} + v_{b} + v_{c} = 0 \Rightarrow v_{a} = -v_{b}-v_{c}
$$
e sostituendo nella precedente:
$$
v_{\alpha} = \frac{2}{3}\left( v_{a}+\frac{1}{2}v_{a}  \right) = v_{a} = V_{M} \cos \theta
$$
di conseguenza il termine $V_{\beta}$:
$$
v_{\beta} = \frac{2}{3} \frac{\sqrt{ 3 }}{2} (v_{b}-v_{c}) = \frac{v_{b}-v_{c}}{\sqrt{ 3 }}
$$
Allineando il vettore $v_{\alpha}$ con $v_{a}$ ed utilizzando la precedente relazione, è semplice passare nel riferimento di Park.
Applicando la definizione invece:
$$
\begin{aligned}
v_{\beta} &= \frac{1}{\sqrt{ 3 }} \left[ \cos \theta \cos \frac{2\pi}{3} + \sin \theta \sin \frac{2\pi}{3} - \cos \theta \cos \frac{4\pi}{3} - \sin \theta \sin \frac{4\pi}{3} \right] = \\
&= \frac{\sqrt{ 3 }}{3}2V_{M} \sin \theta \sin \frac{2\pi}{3} = V_{M} \sin \theta
\end{aligned}
$$

Per passare da un sistema di riferimento all'altro è necessario moltiplicare per $e^{-j\theta}$ e l'angolo $\theta$ si può ricavare con:
$$
\theta = \arctan \frac{v_{\beta}}{v_{\alpha}}
$$
infatti
$$
\vec{v}_{\alpha,\beta} = V_{M}\cos \theta + jV_{M}\sin \theta = V_{M}e^{j\theta}\Rightarrow \vec{v}_{d,q} = \vec{v}_{\alpha,\beta} e^{-j\hat{\theta}}
$$
un errore sulla stima di $\theta$ comporta un errore nella trasformazione:
$$
V_{M}e^{j\theta}\cdot e^{-j\hat{\theta}} = V_{M}e^{j(\theta-\hat{\theta})}
$$
Nel riferimento di Park, se la stima dell'angolo fosse corretta, si avrebbe la rappresentazione della terna di tensioni mediante un unico termine, reale e costante ma una stima errata porta alla seguente scomposizione:
$$
\begin{aligned}
v_{d} &= V_{M}\cos(\theta-\hat{\theta})\\
v_{q} &= V_{M}\sin(\theta-\hat{\theta})
\end{aligned}
$$
ciò si vede nei sistemi di distribuzione in cui una frequenza di rete di 50 Hz può provocare errori considerevoli sulla stima della fase.

I sistemi per compensare questo fenomeno possono essere algoritmi di calcolo in retroazione, come il [[Phase Locked Loop]] o il Frequency Locked Loop.

# Derivate di Lie
Le derivate di Lie definiscono gli angoli tra i campi vettoriali e le superfici attraversate dai campi, restituiscono dunque uno scalare.

Siano
$$
\begin{aligned}
f&:\mathbb{R}^n\to\mathbb{R}^n\\
h&:\mathbb{R}^n\to\mathbb{R}
\end{aligned}
$$
con $h$ una superficie ed $n$ pari a $3$ ad esempio:
$$
\mathcal{L}_{f}(h) = \nabla h\cdot f = \frac{\partial h}{\partial \vec{x}}\cdot f = \left( \frac{\partial h}{\partial x_{1}},\frac{\partial h}{\partial x_{2}},\frac{\partial h}{\partial x_{3}} \right)\begin{pmatrix}
f_{1} \\
f_{2} \\
f_{3}
\end{pmatrix}
$$
Se la derivata è nulla, la funzione $f$ è tangente alla superficie.
Si definiscono le derivate n-esime:
$$
\mathcal{L}^2_{f}(h) = \mathcal{L}_{f}(\mathcal{L}_{f}(h)) = \mathcal{L}_{f}(\nabla h\cdot f)
$$
Ad esempio si considera il seguente campo vettoriale:
$$
\dot{x}=f(x)=\begin{pmatrix}
8x_{1}-x_{2}\\ 
2x_{2}+x_{1} \\
x_{1}^4-x_{2}^2+x_{1}
\end{pmatrix}
$$
la terza componente è non lineare. Si considera la superficie di esempio $h=x_{1}+x_{2}$ e si esegue la derivata del primo ordine:
$$
(1,1,0)\begin{pmatrix}
8x_{1}-x_{2} \\
2x_{2}+x_{1} \\
x_{1}^4-x_{2}+x_{1}
\end{pmatrix} = 8x_{1}-x_{2}+2x_{2}+x_{1} = 9x_{1}+x_{2}
$$
Il risultato ottenuto diventa la superficie per eseguire la derivata del secondo ordine $h=9x_{1}+x_{2}$:
$$
(9,1,0)\begin{pmatrix}
8x_{1}-x_{2} \\
2x_{2}+x_{1} \\
x_{1}^4-x_{2}+x_{1}
\end{pmatrix} = 72x_{1}-x_{2}+12x_{2}+x_{1}=73x_{1}+17x_{2}
$$
