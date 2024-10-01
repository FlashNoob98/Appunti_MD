Si studia il modello matematico del motore in corrente continua ad eccitazione indipendente, a partire dalle grandezze di armatura:
$$
\begin{aligned}
V_{a } + e_{a} &= R_{a } i_{a} \\
v_{a} &= R_{a} i_{a} -e_{a} \\
&= R_{a}i_{a} -e_{da} - e_{ma}\\
e_{da} &= -N_{a} \frac{d\Phi_{da}}{dt} \\
L_{a}&= \frac{N_{a}\Phi_{da}}{i_{a}} \\
e_{da} &= -L_{da}  \frac{di_{a}}{dt}
\end{aligned}
$$
il pedice $da$ indica i termini di dispersione mentre $ma$ quelli di mutua, dunque si riporta tutto in funzione della tensione e corrente di armatura:
$$
v_{a} = R_{a}i_{a} + \frac{L_{da}d_{ia}}{dt} - e_{ma}
$$
Con l'ipotesi di macchina compensata, il flusso di armatura coincide con il flusso di eccitazione(?).

La forza elettromotrice in $N$ conduttori in una cava che si trovino ad una certa ascissa $\alpha$ subiscono una f.e.m. indotta:
$$
e_{\alpha,\text{tot}} = Bl\omega_{r}\cdot r\cdot N_{\text{cava}}
$$
La f.e.m. di mutua di armatura è pari all'integrale:
$$
e_{ma} = lN_{\text{cava}}\omega_{r}\cdot r \int_{-\frac{\pi}{2}}^{ \frac{\pi}{2}} B_{\alpha} d\alpha = k\Phi \omega_{r}
$$
Prende il nome di tensione indotta mozionale.
Dunque l'equazione di equilibrio di armatura diviene:
$$
v_{a} = R_{a} i_{a} + L_{da} \frac{di_{a}}{dt} + \cancel{\left(L_{ma} \frac{di_{a}}{dt} -L_{ma} \frac{di}{dt}\right)}+k\Phi \omega_{r}
$$
Devo tener conto che l'avvolgimento di armatura, potrebbe non appartenere ad una macchina compensata, dunque il campo di armatura $B_a$ ha un andamento triangolare, si dovrebbe tener conto della eventuale sovrapposizione degli effetti dei due campi (l'altro è quello di eccitazione).
Il flusso di eccitazione è proporzionale al movimento della macchina, sarebbe nullo a rotore fisso, se invece è presente un avvolgimento di compensazione si aggiunge il termine $-L_{ma} \frac{di}{dt}$ che annullerebbe il termine di induttanza di armatura.

Il termine $k\Phi \omega_{r}=e$ si intende la tensione indotta pari alla **controforza elettromotrice**, le forze elettromotrici sono date dalla legge di induzione, portata al secondo termine prende invece questo nome, per semplicità viene chiamata tensione indotta.

In generale si scrive:
$$
v_{a} = R_{a } i_{a} + L_{da}\frac{di_{a}}{dt} +e
$$


## Circuito di eccitazione
Facendo le stesse considerazioni precedenti:
$$
\begin{aligned}
v_{e} + e_{e} &= R_{e}i_{e}\\
v_{e} &= R_{e}i_{e} + L_{de} \frac{di_{e}}{dt} + \frac{N_{e}d\Phi_{m}}{dt}\\
v_{e}&= R_{e}i_{e} +  L_{e} \frac{di_{e}}{dt} \\
&L_{e} = L_{de} + L_{me}
\end{aligned}
$$
Anche in questo caso $\Phi_{m}=\Phi_{e}$.
Il circuito di eccitazione non risente del campo di armatura, lo statore non vede ciò che accade nel rotore, gli avvolgimenti sono disaccoppiati ma non avviene il contrario: il rotore si muove nel campo magnetico fisso dello statore, dunque si ha la tensione indotta.
Se il rotore fosse fermo, anche con una tensione variabile nel tempo nell'armatura, il rotore non vedrebbe alcuna tensione indotta se fosse fermo.

Riassumendo il modello matematico elettrico:
$$
\left\{
\begin{aligned}
v_{a} &= R_{a} i_{a} + L_{da} \frac{di_{a}}{dt}  +k\Phi \omega_{r} \\
v_{e} &= R_{e}i_{e} +  L_{e} \frac{di_{e}}{dt} \\
\end{aligned}
\right.
$$

## Equilibrio meccanico
Con l'ipotesi di albero rigido, in ogni istante vale la legge di d?Alembert:
$$
m_{e} - m_{r} = J \frac{d\omega_{r}}{dt}
$$
dove $m_e$ è il momento risultante, su ogni conduttore agisce una forza in modulo pari a:
$$
F = lB_{e}i_{a}
$$
Si suppone che le linee di forza siano tutte radiali, ortogonali alla superficie del rotore, per questo motivo non compare alcun angolo nella formula della forza $(\sin(90))$.

Si deve moltiplicare per il numero di conduttori in cava ed integrare le forze in ogni polo, moltiplicare per il numero di poli, effettuando l'integrale si ottiene nuovamente il flusso:
$$
F_{\text{risultante}} = 2N_{\text{cave}} \Phi li_{a}
$$
Si ottiene la coppia moltiplicando la forza per il braccio:
$$
m_{e} = k \Phi i_{a}
$$
dove $k$ nel SI è identico al precedente nell'espressione della tensione di armatura.
Queste ultime due espressioni vanno aggiunte al modello.

# Regime stazionario
È caratterizzato dalla velocità $\omega_{r}$ costante e dalle tensioni di armatura $V_a$ e di eccitazione $V_{e}$ costanti nel tempo.
L'equazione di eccitazione diventa:
$$
\left\{
\begin{aligned}
V_{e} &= R_{e}I_{e}\\
V_{a} &= R_{a}I_{a} + E & E&=k\Phi \omega_{r} \\
M_{e} &= M_{r} & M_{e} &= k\Phi I_{a}
\end{aligned}
\right.
$$
Si nota che il modello è molto semplice, si vuole ricavare il legame coppia-velocità.
$$
\begin{aligned}
V_{a} &= R_{a}I_{a} + k\Phi \omega_{r} = R_{a} \frac{M_{e}}{k\Phi} + k\Phi \omega_{r} \\
\omega_{r} &= \frac{V_{a}}{k\Phi} - \frac{R_{a}}{(k\Phi)^2}M_{e}
\end{aligned}
$$
Quella trovata è una retta, la variabile indipendente è la coppia resistente, all'equilibrio pari alla motrice, dunque si determina la velocità a partire dalla coppia, in funzione anche della tensione e del flusso.
Per questo motivo ha senso esprimere la velocità in funzione della coppia e non il viceversa.

Non è agevole riportare la caratteristica in questa forma nella macchina asincrona, per questo motivo, solo per eseguire un confronto fra le due macchine si può rappresentare anche la caratteristica della macchina in corrente continua con la coppia in funzione della velocità, semplicemente invertendo l'equazione.
<center>

![[coppia_velocita_CC_indipendente.svg]]

Caratteristica coppia-velocità
</center>

La velocità di rotazione a vuoto, quando la coppia è nulla è pari a:
$$
\omega_{s} = \frac{V_{a}}{k\Phi}
$$
chiamata *velocità di sincronismo* anche se non ha nulla a che fare con questo fenomeno, solo per analogia con l'asincrono, è la massima velocità raggiungibile dalla macchina con tensione fissata.

A rotore bloccato invece:
$$
V_{a} = \frac{R_{a}}{k\Phi}M_{e,\text{avv}} \Rightarrow M_{e,\text{avv}} = \frac{V_{a}}{R_{a}} k\Phi = k\Phi I_{\text{avv}}
$$
si ricava la coppia e la corrente di avviamento.

La massima coppia si sviluppa all'avviamento, la massima velocità la si sviluppa a coppia nulla.

All'aumentare della velocità, la $I_a$ diminuisce, infatti:
$$
I_{a} = \frac{V_{a}-E}{R_{a}}
$$
La tensione indotta nominale $E$ è circa il 90-98% della $V_a$, a seconda della taglia della macchina.
Se ad esempio la $E=95$% e la $R_a=1$ si avrebbe una corrente nominale di $5A$ con una corrente di avviamento di $100A$, si ha una corrente di avviamento decisamente superiore alla nominale.

Questo è giustificato dal fatto che in corrente continua la macchina si offre come un carico puramente resistivo, a differenza dell'asincrono alimentato in corrente alternata, ha una componente induttiva anche all'avviamento.

Questo pone un problema per l'avviamento del motore sincrono, il valore di sovracorrente è distruttivo per la macchina, deve attraversare le spazzole, è una macchina più delicata. 
La massima corrente ammissibile da una macchina in corrente continua non supera 2.5 volte la corrente nominale.

Solo una piccola parte della caratteristica coppia-velocità viene rappresentata, con un valore della coppia massima pari a circa due volte la nominale, con un tratto utilizzabile in regime continuativo ed uno utilizzabile solo in sovraccarico transitorio.

Al variare della coppia resistente si ha una velocità sempre minore, anche se la variazione di velocità è piccola, è un comportamento simile all'asincrono.

La caratteristica coppia-corrente è una retta crescente.
Per questo motivo è una macchina relativamente semplice da controllare, mentre la $V_a\simeq E$ a meno della caduta resistiva, riassumendo:
$$
\begin{aligned}
V_{a} &\propto k \omega_{r}\\
I_{a} &\propto k M_{e}
\end{aligned}
$$

# Avviamento
Per avviare la macchina si alimenta prima il circuito di eccitazione, ha una caratteristica molto induttiva, è necessario aspettare anche 3-4 secondi per raggiungere il regime.
Successivamente si alimenta l'armatura, se si facesse il contrario si avrebbe una sovracorrente distruttiva, è necessario un sistema di avviamento che riduca le sovracorrenti.

## Reostatico
Per diminuire la corrente di avviamento, storicamente si inserivano delle resistenze in serie, chiamato avviamento reostatico.

Non cambia il punto di intersezione a coppia nulla, ma cambia il coefficiente angolare della caratteristica coppia-velocità:
$$
\omega_{r} = \frac{V_{a}}{k\Phi} - \frac{(R_{a}+R_{\text{avv}})M_{e}}{(k\Phi)^2}
$$
Si hanno ovviamente perdite joule maggiori, sviluppate però sulla resistenza esterna, la macchina non subisce riscaldamenti aggiuntivi.

Dunque raggiunta la coppia resistente con una certa resistenza di avviamento, la si può ridurre per aumentare la velocità, ciò comporta un nuovo aumento della coppia dovuto alla nuova caratteristica della coppia, più pendente (la resistenza è stata diminuita), si ipotizza che la corrente vari molto più rapidamente della velocità; successivamente aumenta anche la velocità e la coppia torna al valore precedente.

Il procedimento si può ripetere in successione riducendo a piccoli passi la resistenza, fino a raggiungere la velocità massima.
<center>

![[coppia_velocita_avviamento_CC_indipendente_resistenze_aggiuntive.svg]]
</center>

Un reostato "continuo" sotto carico non potrebbe essere realizzato con un contatto strisciante a causa della rapida usura o dei costi elevati, per questo motivo si realizzavano dei reostati "discreti" composti da una serie di resistenze che venivano shuntate una alla volta.

<center>

![[circuito_resistenze_aggiuntive_CC_indipendente.svg]]
</center>

## Tensione variabile
Variando la tensione invece si ha la variazione del punto di intersezione con l'ascisse, la retta caratteristica si "sposta" rigidamente lungo l'ascisse, con conseguente variazione di velocità alla coppia limite, si può avviare la macchina con una tensione progressivamente superiore.

In questo caso va aumentato l'angolo di innesco di un convertitore, può essere eseguita quasi con continuità (alla frequenza di switching dei convertitori), si possono eseguire variazioni talmente piccole da "nascondere" in pratica le oscillazioni della coppia.

Non ha senso variare la tensione di eccitazione per l'avviamento in quanto si avrebbe una corrente più bassa, quindi coppia inferiore.

# Regolazione di velocità
Si vuole spostare il punto di lavoro, si può intervenire su $V_a$, sul flusso $\Phi$ o su $R_{a}$.
## Regolazione reostatica
Si inserisce sempre una resistenza variabile a monte del circuito di armatura, inserendo la resistenza aggiuntiva, analogamente al caso dell'avviamento si ha una nuova caratteristica a pendenza inferiore, la coppia motrice è inferiore alla coppia resistente e la macchina rallenta, non è detto che segua la curva caratteristica, non è una traiettoria ma un insieme di punti di equilibrio.
## Regolazione con variazione di tensione
Si varia la tensione di armatura con un valore inferiore a quello nominale, $V_a$ minore implica lo spostamento della curva verso sinistra, il transitorio è simile a quello della regolazione reostatica, la macchina si porta in un nuovo punto di equilibrio.
In questo caso si ha un assorbimento di potenza inferiore rispetto all'altro metodo di regolazione. Il metodo non è dissipativo rispetto al precedente.
