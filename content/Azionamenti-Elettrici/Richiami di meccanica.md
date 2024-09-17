# Equazione del moto
Nella formulazione di D'Alembert (secondo principio della dinamica) la sommatoria delle forze attive e la somma delle forze resistenti è pari alla variazione della quantità di moto $Q = m\cdot v$, derivando si ottiene:
$$
\vec{F} - \vec{F_r} = \frac{d\vec{Q}}{dt} = \frac{d(m\vec{v})}{dt} = m \frac{d\vec{v}}{dt} + \vec{v} \cancel{\frac{dm}{dt}}
$$
si suppone la massa costante, se il corpo è libero di muoversi la variazione di velocità diventa accelerazione
$$
\vec{F} - \vec{F_{r}} = m \frac{d\vec{v}}{dt} =  m \vec{a}
$$
Analogamente se il moto è circolare si considera l'equazione duale per i momenti.
Si indica con $\vec{J}$ il momento di inerzia di tutte le masse in rotazione.

L'accelerazione è anche pari a:
$$
a = \frac{M_{\text{motore}} - M_{\text{resistente}}}{J}
$$
## Calcolo del momento di inerzia
Il momento di inerzia si calcola rispetto all'asse di rotazione
$$
J_{a} = \int_{C}r^2dm
$$
con $r$ la distanza della massa elementare $dm$ rispetto all'asse di rotazione.
Solitamente le macchine analizzate nel corso vengono considerate omogenee e si usa la densità del ferro.

Si semplifica il momento di inerzia con la massa equivalente del corpo, se fosse puntiforme, posta ad una distanza $\rho$ dall'asse detto *raggio giratore*.
$$
J = m \rho^2
$$
Si riportano i raggi giratori di alcuni corpi
- **Cilindro omogeneo pieno** di raggio $R$: $\rho = R /\sqrt{ 2 }$ e $J = \pi R^4 L \gamma / 2\ [kg\ m^2]$ con $\gamma$ la densità del materiale. Il momento di inerzia è proporzionale con la lunghezza ma è proporzionale con la potenza quarta del raggio. Se si desiderano accelerazioni forti è necessario costruire macchine di raggio piccolo e più lunghe, viceversa se è richiesta una grande inerzia si costruiscono macchine di raggio maggiore.
- **Cilindro omogeneo cavo** con raggio interno $R_i$ e raggio esterno $R$, si calcola il momento di inerzia del cilindro esterno con la formula precedente e si sottrae quello calcolato sul raggio interno, essendo vuoto, 
  dunque:
  $$
    \rho = \sqrt{ (R_{i}^2+R^2) /2 } \quad J = \pi(R^4 - R^4_{i}) L \gamma /  2
    $$
- **Linea d'albero**: si suppongano n masse di raggio differente calettate sullo stesso albero, se il collegamento è rigido e tutte le masse ruotano alla stessa velocità allora il momento di inerzia complessivo è pari alla somma dei singoli momenti di inerzia.
  $$
      J_{\text{tot}} = \sum_{k=1}^n J_{n}
     $$
Derivando due volte l'equazione del moto si ottiene l'espressione rispetto alla posizione $\theta$.


# Trasmissioni meccaniche
La trasmissione meccanica più semplice è quella mediante il collegamento diretto degli assi di rotazione del motore e del carico, mediante giunti meccanici rigidi, elastici o cardanici.
Si possono usare in alternativa trasmissioni mediante ruote, ovvero due ruote con assi paralleli ma con un punto di contatto tangenziale, possono essere di frizione o dentate, supponendo che non ci sia slittamento, i punti di contatto hanno la stessa velocità, di conseguenza la ruota di raggio inferiore avrà una velocità angolare maggiore.
Nel caso di ruote dentate è importante che questi siano della stessa dimensione per garantire il corretto accoppiamento.
Gli assi di rotazione possono anche essere ortogonali tra loro come ad esempio nel caso del differenziale di un'automobile.

Spesso le applicazioni richiedono una velocità inferiore rispetto a quella del motore, per questo si usano dei riduttori meccanici di vario tipo.
La trasmissione può inoltre essere con cinghia ed eventuali pulegge.
Trasmissione a cremagliera: permette di trasformare un moto circolare in un moto lineare (cancello elettrico), la cremagliera è un sistema dentato lineare.

## Riporto del momento di inerzia ad un unico asse
Se gli alberi sono diversi, nel caso di ruote di raggio differente, come già anticipato, queste avranno velocità angolari differenti in modulo e verso.
Le forze agenti sull'albero motore $1$ ad esempio della ruota movente è pari al momento di inerzia della ruota $1$ insieme al momento resistente della ruota $2$ ad essa collegata.
$$
\left\{
\begin{aligned}
M - f_{2}R_{1} &= J_{1} \frac{d\omega_{1}}{dt}\\
f_{1}R_{2} - M_{L} &= J_{2} \frac{d\omega_{2}}{dt}
\end{aligned}
\right.
$$
supponendo  le forze tangenziali $f$ identiche e sommando:
$$
\frac{M}{R_{1}} - \frac{M_{L}}{R_{2}} = \frac{J_{1}}{R_{1}} \frac{d\omega_{1}}{dt} + \frac{J_{2}}{dt} \frac{d\omega_{2}}{dt}
$$
si sostituisce $\omega_{2}R_{2}=\omega_{1}R_{1}$:
$$
M-M_{L} \frac{R_{1}}{R_{2}} = \left[ J_{1}+J_{2}\left( \frac{R_{1}}{R_{2}} \right)^2 \right] \frac{d\omega_{1}}{dt} \Rightarrow M-M_{L,eq} = J_{1,eq} \frac{d\omega_{1}}{dt}
$$
Si sono riportate tutte le grandezze al primo asse, anche il momento di inerzia resistente, visto dal motore è dunque più basso a causa del riduttore di giri meccanico.

## Analisi energetica
Un modo analogo per calcolare tale riduzione è quello di sfruttare il principio di conservazione dell'energia (cinetica).
L'energia cinetica di una massa in rotazione, connessa ad un'altra che ruota a velocità differente è pari a:
$$
W_{r,cin} = \frac{1}{2} J_{r} \omega^2_{r} = \frac{1}{2} J'_{r}\omega^2_{1}
$$

Analogamente si può calcolare rapidamente il riporto sfruttando l'uguaglianza delle potenze:

$$
M_{2}\omega_{2} = M'_{2} \omega_{1} \Rightarrow M_{2}' = M_{2} \frac{\omega_{2}}{\omega_{1}} = M_{2}\frac{{R_{1}}}{R_{2}}
$$
Si possono riportare le potenze e le energie anche per moti misti circolari e lineari.

# Punto di lavoro e stabilità
Il punto di lavoro è considerato il punto di equilibrio tra il motore e il carico, la caratteristica del motore è l'insieme dei possibili punti di regime. Anche il momento resistente può variare  con la velocità, è il caso dell'attrito con l'aria ad esempio, anche la caratteristica del carico è un insieme di possibili punti di funzionamento; il punto di lavoro appartiene ad entrambe le caratteristiche, può esserci una sola intersezione tra le due curve oppure potrebbero esserci più intersezioni nel caso in cui ci siano ad esempio problemi di avviamento.

Il punto di lavoro deve inoltre essere **stabile**, ci interessa che il sistema resti in quella condizione anche a seguito di perturbazioni esterne.
Preso il punto di equilibrio, se a destra la coppia resistente è maggiore della coppia motrice allora il punto è stabile, viceversa è instabile.
