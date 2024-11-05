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
- $d\left( \vec{x},\vec{y} \right)\geq 0\ d\left( \vec{x},\vec{y} \right)=0\Leftrightarrow \vec{x}\equiv\vec{y}$
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
