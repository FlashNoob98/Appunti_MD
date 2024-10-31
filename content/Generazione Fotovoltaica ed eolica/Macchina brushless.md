Si suppone per semplicità che la macchina sia isotropa, trovano impiego in tanti settori, anche nell'ambito del trasporto veicolare e nella generazione. Grazie alla presenza di magneti permanenti è possibile avere densità di potenza elevate, realizzare inoltre un numero di coppie polari elevato, ovvero una velocità di sincronismo più bassa. Questa caratteristica può essere utile per l'accoppiamento con una turbina eolica, che ha solitamente un numero di giri più basso.

Appartiene alla famiglia delle macchine sincrone, raggiunge il sincronismo del campo alla velocità $\omega/p$, storicamente è una macchina che nasce dall'evoluzione della macchina in corrente continua, l'esigenza era quella di rimuovere le spazzole. Il vantaggio della macchina in corrente continua era la sua capacità di essere controllata in velocità facilmente, si portò quindi l'eccitazione dallo statore al rotore nella macchina brushless.

Con l'avvento dei convertitori di potenza è stato possibile controllare lo statore della macchina brushless. La velocità di sincronismo può essere qualsiasi su una rete passiva.
Se invece la macchina è posta su una rete prevalente, è necessario interporre un convertitore.

Le equazioni della macchina si semplificano in una macchina brushless, non c'è un avvolgimento disposto nel magnete permanente.
I magneti hanno però un costo più alto. Nascono come generatori, sono comunque costruttivamente diverse dalle asincrone.

$$
\vec{v}_{s}^s = r_{s}\vec{i}_{s}^s + \frac{d}{dt} \vec{\Phi}_{s}^s
$$
si indica il flusso per la macchina a magneti permanenti e per quella sincrona:
$$
\text{PM: }\ \vec{\Phi}_{s}^s =l_{d,s}\vec{i}_{s}^s + L_{m}\vec{i}_{s}^s + \vec{\Phi}_{m} = l_{d,s}\vec{i}_{s}^s + L_{m}\vec{i}_{s}^s + {\Phi}_{m}e^{jp\theta_{r}} = L_{s}\vec{i}_{s}^s + \Phi_{M}e^{jp\theta_{r}}
$$
il terzo termine è il componente simmetrico del flusso prodotto dai magneti permanenti.

Nella macchina sincrona invece:
$$
\text{SM: }\ \vec{\Phi}_{s}^s = L_{s}\vec{i}_{s}^s + L_{m}i_{\text{ecc}}e^{jp\theta_{r}}
$$
si sostituisce il flusso dei magneti con l'eccitazione del rotore.

Nella macchina sincrona si misura la posizione con un encoder, la spira equivalente di statore deve seguire esattamente quella del campo prodotta dal magnete permanente.
La coppia sviluppata sarà data dall'interazione tra il campo del magnete permanente (o del rotore) e quello dello statore.

Si portano le equazioni nel riferimento di rotore:
$$
\vec{v}_{s}^s e^{-jp\theta_{r}} = \left(r_{s}\vec{i}_{s}^s + L_{s} \frac{d}{dt} \vec{i}_{s}^s + jp\omega_{r}\vec{\Phi}_{m}\right) e^{-jp\theta_{r}}
$$
si ottiene:
$$
\vec{v}_{s} = r_{s} \vec{i}_{s} + L_{s}\frac{d}{dt} \vec{i}_{s} +jp\omega_{r}L_{s}\vec{i}_{s} + jp\omega_{r}\Phi_{m}
$$
il flusso è ora uno scalare e non più un fasore.
Scomponendo nei due termini in fase e in quadratura:
$$
v_{sd}= r_{s}i_{sd} + L_{s}\frac{d}{dt} i_{sd} -p\omega_{r}L_{s}i_{sq}
$$
il termine in quadratura:
$$
v_{sq} = r_{s}i_{sq} + L_{s} \frac{d}{dt}i_{sq} + p\omega_{r}(L_{s}i_{sd} + \Phi_{m})
$$
Si può deflussare la macchina imponendo una corrente diretta negativa, il limite massimo è la smagnetizzazione dei magneti.

L'equazione della coppia è particolarmente semplice:
$$
T_{el} = \frac{3}{2}p \Phi_{m}i_{sq}
$$
.
Si vuole massimizzare la coppia prodotta in funzione della corrente:
$$
\text{Max}\left( \frac{T_{el}}{\left|I_{s}\right|} \right)
$$
Si vogliono minimizzare le perdite per effetto Joule a pari coppia, ciò avviene quando il componente diretto è nullo, c'è quadratura perfetta tra la corrente e il flusso. A parità di corrente si vuole avere la massima coppia.

La condizione $i_{sd}=0$ ha un limite che dipende la tensione limite della macchina e la corrente limite, ovvero il minimo tra il massimo delle correnti del convertitore e del brushless, quasi sempre il limite è la condizione di sovraccarico del convertitore.
Riassumendo:
$$
\begin{aligned}
|V_{s}| &\leq V_{L}\\
|\vec{i}_{s}| &\leq I_{L} \Leftrightarrow i_{sd}^2 + i_{sq}^2 \leq I_{L}^2
\end{aligned}
$$
c'è una frontiera circolare di limite per la corrente. Il limite di tensione dipende dalla velocità.
$$
V_{s}^2 \leq V_{L}^2 \Leftrightarrow V_{sd}^2 + V_{sq}^2 \leq V_{L}^2
$$
Si possono trascurare i termini trasformatorici e le cadute resistive:
$$
(p\omega_{r}L_{s}i_{sq})^2 + ( p\omega_{r}(L_{s}i_{sd} + \Phi_{m}))^2 \Leftrightarrow (L_{s}i_{sq})^2 + \left(i_{sd} +\frac{\Phi_{m}}{L_{s}}\right)^2 \leq \left( \frac{V_{L}}{p\omega_{r}L_{s}} \right)^2
$$
Questa circonferenza è traslata lungo l'asse diretto, a seconda del valore del flusso, può essere interna o esterna alla circonferenza data dal limite di corrente, se fosse esterna, il vincolo di corrente imporrebbe il limite di velocità, al limite non ci sono più intersezioni tra i domini.

Si assume la velocità base quella per la quale $i_{sd}=0$ e $i_{sq}=I_{L}$, tutte le velocità superiori hanno un valore di corrente limite inferiore se si impone $i_{sd}=0$, sto quindi riducendo la coppia massima.

Nel grafico coppia-velocità c'è un limite di frontiera a coppia costante, fino alla velocità di base, successivamente decresce con un andamento di un ramo di parabola, si indica la $\omega_{r,l}$ a  coppia nulla, non sto comunque facendo deflussaggio, la corrente $i_{sd}$ non è negativa ma nulla.

Per superare la velocità limite devo deflussare, ovvero spostare la curva di tensione verso destra, viceversa per aumentare la coppia devo necessariamente aumentare la corrente e non rispettare il limite coppia su corrente massimo.

$$
\omega_{r,0}= \frac{V_{L}}{p\Phi_{r}}
$$
La velocità $\omega_{r,0}$ è quella per cui a corrente $i_{sq }=0$ si ha coppia nulla???
$$
\vec{i}_{sq} = \frac{1}{L_{s} }\sqrt{ \frac{V_{L}^2}{(p\omega_{r})^2}-\vec{\Phi}_{r}^2 }
$$
Per correnti $i_{sd}$ negative si ha una  corrente massima maggiore.

# Schema di controllo
L'anello più esterno di controllo è sempre quello di velocità, in uscita dal regolatore di velocità c'è il valore di coppia.
Mediante una costante di proporzionalità si associa alla coppia un valore di $i_{sq}$, da cui si ricava $i_{sd}$ in base alla condizione ausiliaria.
Per velocità inferiori alla velocità base (analogamente correnti di $i_{sq}\leq \bar{i}_{sq}$ ovvero la frontiera di corrente), $i_{sd}$ sarà nulla.

Viceversa per $\bar{i}_{sq}<i_{sq}\leq i_{sq,M}$ allora la $i_{sd}$ si ricava invertendo questa relazione:
$$
\left( i_{sd}^* + \frac{\Phi_{r}}{L_{s}} \right)^2 + i_{sq}^2 = \left( \frac{V_{L}}{p\omega_{r}L_{s}} \right)^2
$$
ovvero:
$$
i_{sd}^* = \frac{1}{L_{s}}[\sqrt{ (\dots) }]
$$
.
Le due correnti di riferimento vengono poi inviate ai PI o ai regolatori ad isteresi connessi al driver de motore.
In alternativa si possono usare le equazioni di statore per realizzare una compensazione e utilizzare il controllo SVM.
$$
v_{sd}^* = \tilde{v}_{sd} - Q \hat{i}_{sq}
$$
e
$$
v_{sq}^*= \tilde{v}_{sq} + Q\hat{i}_{sd} + E
$$
dove $Q=p\omega_{r}L_s$ ed $E=p\omega_{r}\phi_{r}$.
