Si vuole presentare il sistema di controllo di una macchina in corrente continua ad eccitazione indipendente, si vuole controllare la corrente o il flusso della macchina per regolare la coppia.

Nel dominio di lavoro a potenza costante, per aumentare la velocità va diminuito il flusso, mantenuto nominale fino alla velocità nominale.
Per diminuire il flusso si diminuisce la corrente di eccitazione.

La corrente di eccitazione non avverte il flusso sostenuto dalla corrente di armatura, le due regolazioni possono essere fatte in maniera indipendente.
Il flusso di armatura fornisce ai capi dell'avvolgimento una tensione indotta $E$.

Per il circuito di armatura si usa un sistema in cascata, per quello di eccitazione un singolo regolatore per regolare la corrente di eccitazione.

Le variabili di stato da controllare dipendono dal controllo, ad esempio si vuole fornire un riferimento di coppia, sarà sufficiente controllare la corrente, agendo sulla tensione, quindi un'unica variabile di stato.

Se si volesse invece controllare la velocità si fa riferimento all'equazione di d'Alembert
$$
J \frac{d\omega_{r}}{dt} = M_{e} - M_{r}
$$
La velocità in questo caso è una variabile di stato, alla quale è associata un'energia cinetica $J\omega_{r}^2$, controllando la sua derivata.
In questo caso il forzamento è la coppia motrice, $M_r$ è invece considerata una perturbazione.

Per il controllo di posizione, si usa la definizione di velocità
$$
\frac{d\theta}{dt} = \omega_{r}
$$
quindi controllare la posizione implica ancora forzare una coppia con una certa legge di controllo.

Nelle macchine elettriche le variabili di stato sono la corrente di armatura e la velocità, sono grandezze fisiche che hanno costanti di tempo diverso tra loro, per confrontare queste costanti di tempo è necessario normalizzare le grandezze, ovvero rispetto ad un termine di riferimento omogeneo, ad esempio alla corrente si associa come termine di paragone la corrente nominale, per la velocità si usa la velocità nominale.
Ad esempio in quanto tempo la corrente va da 0 al valore nominale?
In quanto tempo la velocità va da 0 alla nominale?
Si confrontano questi due tempi per vedere quale variabile di stato è più veloce.

Presa una macchina elettrica tradizionale (non un servomotore), di fissata potenza, ad esempio 11kW, la corrente di armatura ha un tempo di evoluzione di centinaia di microsecondi, quello della velocità di centinaia di millisecondi, ci sono 3 ordini di grandezza di differenza.
Questa caratteristica permette di utilizzare il controllo in cascata, ogni anello di controllo non risente dell'azione dell'azione dell'anello addizionale.

Un anello di corrente controlla il valore della corrente misurata sulla base della corrente di riferimento, quello di velocità è analogo, l'anello di corrente è più veloce perché agisce su una variabile di stato con una dinamica più rapida.
Su questa supposizione, che durante il controllo della corrente, la velocità resti invariata, è fondamentale per permettere il controllo in cascata.

L'anello di corrente confronta la corrente con quella di riferimento e fornisce in uscita il valore del forzamento (tensione di armatura) da fornire alla macchina.

Un generatore di tensione di armatura $V_a$ stabilita dal controllore, in realtà l'armatura non è alimentata da un generatore ideale ma da un chopper, a due o quattro quadranti, non si usa quasi mai quello ad un quadrante, non potrebbe frenare la macchina o recuperare energia, inoltre soffre del fenomeno della conduzione discontinua.
Oppure si può usare un chopper a 4 quadranti se si vuole invertire la velocità.

In ogni caso il convertitore fornisce un'onda rettangolare, a noi interessa il valore medio di questa tensione rispetto all'intervallo di modulazione. La modulazione fornisce un ritardo nel tempo di controllo pari alla metà del tempo di modulazione. Questo ritardo è fondamentale per il controllo della macchina.

Un chopper a 10kW arriva anche a frequenze di modulazione di 40kHz (quindi tempi di centinaia di microsecondi).
Anche un raddrizzatore ha un tempo di modulazione equivalente, in quanto tempo riesce a modulare il valore medio, nel caso del raddrizzatore invece dipende dal raddrizzatore, nel caso del monofase ad esempio il ponte monofase avrebbe una frequenza di modulazione di 100Hz, un ponte trifase 300Hz, rispetto ad una frequenza di alimentazione a 50Hz, almeno un ordine di grandezza superiore a quello del chopper.
Per questo motivo è necessario utilizzare il chopper.

Il discorso è diverso per il circuito di eccitazione, la variazione è molto più lenta, la dinamica è confrontabile con la dinamica meccanica, dunque si può usare un raddrizzatore.
Inoltre ci si aspetta un ripple di tensione di eccitazione, ha una costante di tempo molto elevata essendo fortemente induttivo, dunque è sufficiente utilizzare un ponte semi-controllato monofase.

Riassumendo: $V_a$ armatura, $V_e$ eccitazione.

Il circuito di armatura è una serie RLE, connessa ad un generatore $V_a$, la $E$ è la tensione sostenuta dal flusso di eccitazione, per la velocità del rotore.

Il circuito di eccitazione non presenta la tensione indotta e ha parametri RL differenti, alimentato da $V_e$.

Il circuito di armatura vede quello di eccitazione ma non il viceversa.

Vanno controllate le due correnti tenendo conto dei ritardi indotti dalla modulazione del chopper o dal raddrizzatore.
Il chopper ha un ritardo di 1/2T_m mentre il ponte monofase 1/4T_s (5ms a 50Hz).

# Circuito più interno
Si regola la corrente di armatura, è la variabile più veloce:
corrente di riferimento $i_a^*$ nel nodo sommatore, si sottrae la corrente misurata $i_{a}$ proveniente da un trasduttore di corrente.
In uscita dal nodo sommatore l'errore $\varepsilon_{i}$ che entra nel regolatore, ad esempio il PI, in uscita dal controllore la tensione di riferimento $V_a^*$, sarebbe proprio uguale alla $V_a$ se il generatore fosse ideale. In realtà va prima compensato il disturbo $E$, ovvero la tensione indotta è vista dal regolatore come un disturbo, affinché il controllo sia efficace.
ma $E=k\Phi \omega_{r}$, se si conosce la macchina si possono stimare $k\Phi$ mentre la velocità è misurata.

Si scompone la tensione $V_a^*$ in due componenti $\tilde{V}_{a}$ e $V_{a,c}$ , misurando la $E$ istante per istante, pongo $V_{ac}=E$, mi resta solo 
$$
\tilde{V}_{a}=R_{a}i_{a}+L_{a} \frac{d_{i}}{dt}
$$
Dunque in uscita dal regolatore ho $\tilde{V}_a^*$ al quale devo sommare la $V_{a,c}=E$, in uscita ho la $V_{a}^*$.

Per controllare la velocità necessito di un altro regolatore, che controlli la velocità, fornendo il riferimento di coppia, si usa ancora un PI, si potrebbe usare qualsiasi regolatore.
Velocità di riferimento - velocità misurata > ho l'errore, in uscita dal regolatore ho la coppia di riferimento $M_e^*$ ma devo passare alla corrente, dunque divido per $k\Phi$.
Ma $\Phi$ può variare, soprattutto se andiamo in deflussaggio, dunque dovrei usare un blocco divisore dove $k\Phi$ proviene dall'esterno, è un riferimento della strategia di controllo.
Per ipotesi $\Phi=\Phi_{n}$ se $i_{e}=i_{e,n}$.

Lo schema di controllo dell'eccitazione si basa su un flusso di riferimento, fornito dalla strategia di controllo.
La strategia di controllo deve innanzitutto far fornire alla macchina una coppia pari alla coppia di riferimento. Un limite superiore della coppia può essere quella nominale o quella di sovraccarico.
Nel dominio a potenza costante la coppia limite varia con la velocità, va regolato di conseguenza anche il flusso.

Dunque in funzione della coppia fornita di riferimento e della velocità di funzionamento effettiva si sceglie una strategia di controllo, e si stabiliscono le correnti da variare nella macchina elettrica.
$$
\begin{aligned}
i_{a}^* &= f_{a}(M_{e}^*,\omega_{r})\\
i_{e}^*&=f_{e}(M_{e}^*,\omega_{r})
\end{aligned}
$$
Ad esempio dominio di regolazione a coppia costante, la strategia di controllo permette di raggiungere il punto di funzionamento in maniera ottimale, rispetto al rendimento, ad esempio siamo in un punto inferiore alla velocità in cui inizia il deflussaggio, dunque posso vincolare la corrente di eccitazione pari alla nominale.
$$
\begin{aligned}
i_{a}^* = \frac{M_{e}^*}{k\Phi_{n}}\\
i_{e}^* = I_{e,n}
\end{aligned}
$$
Nel dominio a potenza costante invece esistono due approcci, uno più rigoroso ed uno semplificato. Nel deflussaggio il flusso varia come un ramo d'iperbole rispetto alla velocità, così come la corrente di eccitazione ad esso proporzionale, ricavato il flusso si ricava la $i_a^*$.
Devo prima saturare il dominio di regolazione del regolatore, non posso fornire una coppia superiore a quella ammessa dal dominio di regolazione.

La banda passante del regolatore mi dà una misura della velocità di controllo, sono presenti dei ritardi che garantiscono la stabilità del sistema con un certo margine (di fase).

Per i sistemi di controllo si usano solitamente margini di 30 e 60 gradi, in particolare devo regolare $K_p$ mentre la $K_i$ annulla l'errore a regime, è la $K_p$ a regolare il transitorio, dove c'è l'influenza della banda passante. Fissata la $K_p$ fisso la banda passante del sistema e quindi il margine di fase, oltre un certo valore il sistema va in instabilità. Il valore di $K_i$ incide solo sull'azione di regime, ci interessa solo che ci siano piccole sovraelongazioni o sottoelongazioni, va dimensionata per ridurli al minimo.
Un minimo di sovraelongazione è richiesto per il raggiungimento del regime, se anche il sistema fosse ideale avrei un errore causato dalla tensione in ingresso che non è costante ma fornita dal convertitore.

# Trasformata di Laplace dell'equazione di armatura compensata
$$
\begin{aligned}
\tilde{V}_{a} &= R_{a}i_{a} + L_{a}\frac{d}{dt}i_{a} \\
\tilde{V}_{a}(s) &= R_{a}I_{a}(s) + sL_{a}I_{a}(s) \\
&\Rightarrow I_{a}(s) = \frac{\tilde{V}_{a}(s)}{R_{a}+sL_{a}}
\end{aligned}
$$
ma l'equazione del regolatore, che ha in ingresso l'errore è:
$$
\begin{aligned}
\tilde{V}_{a} &= K_{p}\varepsilon_{i} + K_{i}s\varepsilon_{i}\\
\tilde{V}_{a}(s) &= \left( K_{p}+\frac{K_{i}}{s} \right)\varepsilon_{i}(s)
\end{aligned}
$$
La funzione di regolazione ad anello aperto $F_a$ è pari al prodotto delle due funzioni:
$$
F_{a} = \left( \frac{K_{p}s+K_{i}}{s} \right) \left( \frac{1}{R_{a}+sL_{a}} \right)
$$
La banda passante è la frequenza alla quale il modulo della funzione di trasferimento è pari ad 1.
Si passa nel dominio della frequenza sostituendo $j\omega$ ad $s$, dunque:
$$
F_{a}(j\omega) = \frac{K_{p}j\omega+K_{i}}{j\omega}\left( \frac{1}{R_{a}+j\omega L_{a}} \right)
$$
La componente proporzionale lavora nel transitorio e l'integrale controlla il regime, a frequenze confrontabili con la banda passante, la parte proporzionale è preponderante rispetto all'integrale.
A frequenze prossime alla banda passante, chiamata $\omega_{t}$ si può dire che (se abbiamo dimensionato bene il regolatore) allora $K_{p}\omega\gg K_{i}$ e dunque si può approssimare:
$$
F_{o}(\omega) = \frac{K_{p}j\omega_{t}+K_{i}}{j\omega_{t}}\left( \frac{1}{R_{a}+j\omega_{t}L_{a}} \right)
$$
semplificando $K_i$ nella frequenza di taglio, si ottiene:
$$
F_{o}(\omega) = K_{p}\left( \frac{1}{R_{a}+j\omega_{t}L_{a}} \right)
$$
Ma è presente un ritardo $t_{d}$, che in Laplace si rappresenta con un esponenziale $e^{-st_{d}}$, nel dominio della frequenza $e^{-j\omega t_{d}}$.
Ovvero si sottrae la fase $\omega t_{d}$ all'intero sistema, uno sfasamento dell'intero sistema proporzionale con la frequenza.
Si riduce il margine di fase, ovvero la distanza della fase da $180°$ quando il modulo della funzione di trasferimento è unitario.
A pari omega, all'aumentare di $t_d$ si riduce il margine di fase, riducendo la stabilità del sistema, si riduce la banda passante concessa.
