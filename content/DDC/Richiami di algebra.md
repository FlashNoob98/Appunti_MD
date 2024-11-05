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


Sia un insieme $\mathbb{A}$ non vuoto, un campo $\mathbb{K}-V$. 