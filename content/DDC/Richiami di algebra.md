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
- L'applicazione $P$ è suriettiva: $\forall\ P \in\mathbb{A},\forall\ \vec{v}\in V\ \exists{!}\ Q\in\mathbb{A}:\Pi(P,Q)=\vec{V}$
- Gode dell'identità di Charles: $P,Q,Z \in\mathbb{A}\Rightarrow \Pi(Q,Z)=\Pi(P,Q)+\Pi(Q,Z)$
Un'applicazione è suriettiva se e solo se ogni elemento di $B$ è immagine di almeno un elemento di $A$, ovvero tutti gli elementi di $B$ sono immagini di almeno un elemento di $A$, l'insieme immagine coincide col codominio della funzione.
$F:A\to B$.

Non vale il viceversa, l'applicazione inversa $\Pi^{-1}(P,Q)$ fornisce un sottoinsieme di $\mathbb{A}$, fornisce ovvero anche infinite coppie di $P$ e $Q$ in $\mathbb{A}$.
Fissato un punto $P$ e un vettore $\vec{V}\ \exists!\ Q : \Pi(P,Q)=\vec{v}$ ma dato $\vec{v}$ esistono infinite coppie di $P$ e $Q$ che forniscono $\vec{v}$.
Segmento orientato...