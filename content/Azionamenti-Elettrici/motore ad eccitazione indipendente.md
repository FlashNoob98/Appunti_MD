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

<center>

![[coppia_velocita_avviamento_CC_indipendente_variazione_tensione.svg]]
</center>

Non ha senso variare la tensione di eccitazione per l'avviamento in quanto si avrebbe una corrente più bassa, quindi coppia inferiore.

# Regolazione di velocità
Si vuole spostare il punto di lavoro, si può intervenire su $V_a$, sul flusso $\Phi$ o su $R_{a}$.
## Regolazione reostatica
Si inserisce sempre una resistenza variabile a monte del circuito di armatura, inserendo la resistenza aggiuntiva, analogamente al caso dell'avviamento si ha una nuova caratteristica a pendenza inferiore, la coppia motrice è inferiore alla coppia resistente e la macchina rallenta, non è detto che segua la curva caratteristica, non è una traiettoria ma un insieme di punti di equilibrio.
## Regolazione con variazione di tensione
Si varia la tensione di armatura con un valore inferiore a quello nominale, $V_a$ minore implica lo spostamento della curva verso sinistra, il transitorio è simile a quello della regolazione reostatica, la macchina si porta in un nuovo punto di equilibrio.

In questo caso si ha un assorbimento di potenza inferiore rispetto all'altro metodo di regolazione. Il metodo non è dissipativo rispetto al precedente.

Con entrambi i metodi si può coprire la parte sinistra del piano rispetto alla velocità di sincronismo, si sottintenderà il metodo con variazione di tensione per evitare le perdite dissipative sul reostato.

## Regolazione con variazione di flusso
Si può agire sul flusso di eccitazione, proporzionale alla corrente:
$$
\Phi = \Phi_{e} = L_{e}I_{e} = \frac{L_{e}V_{e}}{R_{e}} 
$$
dunque diminuendo la tensione di eccitazione si riduce la corrente e quindi il flusso di eccitazione, a parità di coppia però si ha la minore coppia possibile se si lavora a flusso nominale, lo si può al massimo diminuire e non aumentare, *deflussaggio* in inglese *flux reduction(?)*.
Si ha una variazione sia del coefficiente angolare che del punto di intersezione della caratteristica.
Sicuramente il punto di intersezione aumenta, dunque si sposta verso destra e diminuisce il coefficiente angolare.
Si coprono in questo modo punti del piano a velocità maggiori rispetto a quella di sincronismo.

Il circuito di eccitazione ha una potenza di pochi punti percentuali la nominale, è più semplice variare la tensione in un circuito di bassa potenza, sembrerebbe più conveniente variare il flusso. Per una fissata coppia però, se il flusso diminuisce troppo deve aumentare la corrente, che non può superare a regime la nominale.

Nel transitorio la variazione della tensione di eccitazione ha una costante di tempo più elevata rispetto ai metodi precedenti, nell'ordine delle frazioni del secondo. La tensione di armatura ha una variazione negli ordini dei millisecondi.
È comunque l'unico metodo possibile per superare la velocità di sincronismo.

Riassumendo **per velocità inferiori alla velocità di sincronismo si interviene sulla tensione di armatura, per velocità maggiori della velocità di sincronismo si riduce il flusso, mantenendo la tensione di armatura nominale**.

Riducendo il flusso, a corrente limitata, si riduce la coppia massima, tutti i punti compresi nella regione limitata dalla coppia nominale e dalla caratteristica verticale nominale (1).
In questa regione il flusso può essere mantenuto pari al flusso nominale.

Nella regione con velocità superiori al sincronismo è necessario ridurre il flusso, si mantiene la tensione pari alla nominale e la corrente pari alla nominale per tracciare la curva limite a destra, in realtà se la macchina è auto-raffreddata, la corrente nominale dipende anche dalla velocità.
Dunque anche la potenza elettrica è pari alla nominale, a meno delle perdite (joule+ferro+meccaniche) coincide tipicamente con la potenza meccanica.
Le perdite nel ferro e meccaniche possono comunque essere solitamente trascurate:
$$
P_{\text{mecc}} = P_{\text{el},n}-R_{a}I_{a,n}^2
$$
Ma la potenza meccanica è anche pari a $M\cdot \omega$ dunque si traccia un ramo di iperbole, la velocità massima è pari a 2 volte la velocità nominale.

Si chiama **dominio di regolazione** in regime continuativo la porzione di piano compresa nelle aree (1) e (2).

Aumentando la corrente limite si potrebbe avere un dominio traslato verso l'alto che delimiti una regione di sovraccarico, potrebbe essere utile però durante l'accelerazione iniziale della macchina, avere una coppia superiore alla nominale.

Questa corrente attraversa però il **[[Dinamica dei convertitori elettrici|convertitore]]**, dunque il fattore pari a circa 2 volte la corrente nominale, potrebbe essere molto più alto sull'asincrono ma ciò non viene fatto a causa del limite del convertitore, non è facilmente sovraccaricabile, i dispositivi a semiconduttore tendono a rompersi in seguito a sovracorrenti..
Con l'aggiunta del convertitore dunque si alimenta con un range molto ampio il motore.

L'intervento sul flusso è dissipativo? A pari coppia e flusso, la corrente deve aumentare.

# Frenatura elettrica
Per frenare un moto è necessario sviluppare una forza o una coppia che si opponga al verso del moto o della rotazione.
Se questa forza è sviluppata elettricamente, si parla di frenatura elettrica.

Il segno di $M_e$ dipende sia dal flusso che dalla corrente di armatura ma la costante di tempo del flusso, come già anticipato è maggiore, dunque si preferisce invertire il verso della corrente di armatura, ancora una volta si sfrutta il convertitore.
Dall'equazione di equilibrio del circuito di armatura si ricava:
$$
I_{a} = \frac{V_{a}-E}{R_{a}} \Rightarrow V_{a}<E
$$
la tensione indotta $E$ varia lentamente, è funzione della velocità del rotore, inoltre non avrebbe senso aumentare la velocità per effettuare una frenatura!
## Frenatura a recupero
Dunque si agisce sulla tensione di armatura, dunque
$$
V_{a} < E \Rightarrow k\Phi \omega_{s} < k\Phi \omega_{r} \Rightarrow \omega_{s}<\omega_{r}
$$
Si supponga inizialmente di essere sulla caratteristica nominale e avere una coppia resistente costante con la velocità, si trova il punto di lavoro della macchina.
Si mantiene la tensione di eccitazione costante e si riduce quella di armatura, intervenendo sull'angolo di innesco del convertitore, avviene in tempi molto brevi, inferiori alla caratteristica dinamica meccanica della macchina, che mantiene la stessa velocità precedente, si raggiunge un punto $P'$ con ordinata negativa (coppia frenante) $M_F$, la coppia sarà inferiore alla resistente, riportando la macchina in una curva a coppia negativa, ho rallentato la macchina.

Tra i punti $P'$ e $P''$ la corrente è negativa, la tensione resta positiva, dunque fornisce energia alla rete, la potenza meccanica sarà anch'essa negativa.
Viene per questo motivo chiamata frenatura a recupero di energia.

Se si annulla la tensione, ho comunque una frenatura ma non reimmetto energia in rete, non ho recupero.
Devo usare un convertitore a doppia polarità di tensione, per arrestare il motore nell'ultimo tratto, devo fornire energia alla rete.

## Frenatura reostatica
La frenatura è tanto più rapida quanto maggiore è la coppia frenante, ma la corrente è maggiore, si hanno perdite Joule maggiori.

La corrente però durante l'avviamento, se venisse fatto a flusso costante, sarebbe attraversata da una corrente troppo elevata; si inserisce in questo caso una resistenza di frenatura.
$$
I_{a}=\frac{E=k\Phi \Omega_{r}}{R_{a}+R_{F}}
$$
Per mantenere elevata la coppia frenante, si può diminuire progressivamente la resistenza inserita, mantenendo la coppia frenante elevata. Si può eseguire questa operazione anche con una serie di resistenze da bypassare.

## Frenatura in controcorrente (tensione invertita)
È possibile effettuare una frenatura invertendo il verso della tensione di armatura:
$$
I_{a} = - \frac{{V_{a}+E}}{R_{a}}
$$
La corrente sarebbe eccessivamente più grande, per questo motivo anche con questo metodo devo inserire una resistenza durante la frenatura.

Muovendomi lungo la caratteristica frenante avrei successivamente un funzionamento da motore in verso opposto, raggiungendo un nuovo punto di equilibrio con velocità inversa, va dunque disalimentato il motore quando si raggiunge la velocità nulla. In questo caso non è necessario inserire una resistenza variabile. Anche in questo caso la frenatura è dissipativa.

## Calcolo dell'energia dissipata
Si vuole calcolare l'energia dissipata durante i processi di avviamento e/o frenatura:
$$
W_{e} = \int_{0}^{t_{avv}} R_{a}I_{a}^2dt = \int_{0}^{t_{avv}} R_{a}I_{a}I_{a}dt = \int_{0}^{t_{avv}} (V_{a}-E)\frac{M_{e}}{k \Phi} dt
$$
utilizzando l'equazione di d'Alembert si sostituisce la coppia con la variazione di velocità, cambiando la variabile di integrazione:
$$
W_{e} = \int_{0}^{\omega_{s}} \left( \frac{V_a}{k\Phi} -\frac{k\Phi\omega_{r}}{k\Phi} \right) Jd\omega_{r} =
J\int_{0}^{\omega_{s}} (\omega_{s}-\omega_{r})d\omega_{r} = J\omega_{s}^2 - \frac{J}{2}\omega_{s}^2 = \frac{1}{2}J\omega_{s}^2
$$
Si è supposto di avviare la macchina a vuoto, partendo da velocità nulla fino alla velocità di sincronismo.

La macchina ha dissipato la stessa energia cinetica che conteneva durante il moto, ovvero si ha un rendimento di avviamento del 50%, dell'energia totale fornita dalla rete, metà è necessaria all'avviamento, metà viene immagazzinata dal rotore.

Si è assunto nel calcolo la tensione $V_a$ costante, come per l'avviamento reostatico, a prescindere dal numero e dal tipo di resistenze utilizzate.

Durante l'avviamento a tensione variabile, si suppone di mantenere la corrente costante, non posso usare le tensioni nell'integrale perché non saprei integrarle, dunque:
$$
W_{e} = \int_{0}^{t_{avv}} R_{a}I_{a,lim} \frac{M_{e}}{k\Phi} dt = \frac{R_{a}I_{a,lim}J}{k\Phi} \int_{0}^{\omega_{s}}d\omega_{r} = \frac{R_{a}I_{a,lim}J}{k\Phi} \omega_{s}
$$
Ma la corrente $I_{a,lim} = \alpha I_{a,n}$ dunque:
$$
W_{e} = J\alpha I_{a,n} \frac{R_{a}V_{a,n}\omega_{s}}{k\Phi V_{a,n}} = J\alpha \beta \omega_{s}^2 = \frac{1}{2}j\omega_{s}^22\alpha \beta
$$
avendo posto $R_{a}I_{a,n} = \beta V_{a,n}$ si è ridotta l'energia dissipata al 20%, dato che $2\alpha \beta\ll{1}$ in certe condizioni (?).
