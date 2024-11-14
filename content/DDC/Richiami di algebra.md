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
È una forma bilineare simmetrica definita su un campo reale nello spazio $V$ cartesiano su se stesso, deve essere:
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

Nel caso di un sistema elettrico trifase, si può dunque considerare un generico vettore di tensione così definito:
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
C_{T} = \sqrt{ \frac{2}{3} } 
\begin{pmatrix}
1 & \cos\left( \frac{2\pi}{3} \right) & \cos\left( \frac{4\pi}{3} \right)  \\
0 & \sin\left( \frac{2\pi}{3} \right) & \sin\left( \frac{4\pi}{3} \right) \\ 
\frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }} & \frac{1}{\sqrt{ 2 }}
\end{pmatrix}
$$
La matrice è ancora ortogonale perché deriva dalla precedente, che era ortogonale per ogni $t$.
La matrice $C_{T}$ permette il passaggio dal sistema di riferimento cartesiano a quello ortonormale di Clarke.
