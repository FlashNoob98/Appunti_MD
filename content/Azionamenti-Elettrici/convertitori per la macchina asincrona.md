I convertitori elettrici per tensioni alternate, che alimentano le macchine asincrone sono divisi prevalentemente in convertitori in due stadi e convertitori a singolo stadio. I componenti principali che compongono questi convertitori sono gli IGBT, i GTO, gli SCR o per piccole potenze i MOSFET.
I dati di targa dei componenti indicano correnti e tensioni nominali ma non è detto che queste due caratteristiche si possano sempre raggiungere in contemporanea, spesso il valore di frequenza è inversamente proporzionale alla potenza.
Questi componenti possono essere venduti singolarmente o assemblati già in moduli che possono formare una o più gambe, o comprendere l'intero convertitore, questo formato riduce le resistenze di connessione tra i vari dispositivi.

# Tipologie di convertitori
## Convertitori monostadio
### Cicloconvertitori
Costituiti da due raddrizzatori in antiparallelo, ad esempio due ponti monofase montati in antiparallelo, su un carico resistivo.
#### Doppio ponte monofase
Partendo da un'onda sinusoidale, si può ritardare l'angolo di innesco del convertitore per avere un'onda sinusoidale in uscita composta dalla sovrapposizione di più frazioni di onde sinusoidali, si può decidere ogni quante frazioni di onde invertire il funzionamento del convertitore per ottenere una desiderata frequenza in uscita.
#### Doppio ponte trifase
Si desidera avere una tensione monofase a partire da una rete trifase, la logica di controllo è simile alla precedente ma le forme d'onda sono differenti, si riduce il contenuto armonico dell'onda in uscita.
Se si volesse eseguire quest'operazione su un carico trifase sarebbero necessari 6 ponti in totale, ovvero 36 tiristori!
La frequenza massima è comunque quella di rete, quindi non si possono superare i 50Hz, possono trovare applicazioni ad esempio su motori navali dove le velocità di rotazione richieste sono basse.
Durante la commutazione tra un ponte e l'altro esistono comunque dei tempi morti durante i quali non c'è tensione sul carico, inoltre bisogna rispettare i tempi di spegnimento dei tiristori.

### Convertitori a matrice
Partendo da una rete trifase, si può decidere in ogni istante, mediante un convertitore a matrice, di collegare una determinata fase della rete ad un particolare morsetto del carico, dunque si può combinare il collegamento delle fasi in ogni istante di tempo.

## Convertitori a due stadi
Esistono due grandi famiglie di convertitori a due stadi, se nello stadio intermedio è presente un'induttanza prendono il nome di CSI, ovvero convertitori a corrente impressa, se invece è presente una capacità prendono il nome di VSI, ovvero convertitori a tensione impressa.

In alternativa alla capacità si può interporre un chopper sulla linea in continua che fornisce una tensione continua variabile per il VSI.
### CSI con componenti comandati in spegnimento
Convertitori a corrente impressa presentano un'induttanza nello stadio in continua, percorsa da una corrente continua, se questa è alta rispetto a quella del motore, la corrente resta praticamente costante.
Il ponte di conversione è composto da GTO o IGBT a seconda della potenza, in serie a dei diodi e con delle capacità in derivazione, questi due ultimi componenti sono necessari allo spegnimento dei tiristori, problema che non sussiste nel caso in cui si usino dei GTO.

Durante la conduzione di una coppia di componenti, la corrente nel ramo in continua è pari a quella che attraversa una coppia di convertitori e una coppia di fasi in uscita.
Durante la commutazione conducono tre componenti, c'è un transitorio durante il quale c'è una chiusura sul carico, il tempo di spegnimento dipende dunque dall'induttanza del carico.

Se le correnti in uscita sono una terna simmetrica, allora il campo impresso nel motore è rotante nel tempo, in questo caso però le correnti sono costanti ogni 60° dunque si ha un numero discreto di direzioni spaziali del campo. C'è un contenuto armonico relativamente alto, solitamente l'andamento delle ampiezze delle armoniche $k$ in un'onda rettangolare è:
$$
\frac{I_{k}}{I_{1}} = \frac{1}{k}
$$
La forma d'onda di tensione in uscita è pseudo sinusoidale a causa dell'induttanza del carico ma sono comunque presenti delle sovratensioni distanziate 60° localizzate nei punti di commutazione, ogni 120° su ogni fase, possono incidere sulla vita utile dell'isolante;
le capacità interfasiche assorbono i picchi di tensione.
Anche la coppia presenta delle ondulazioni a causa del contenuto armonico di corrente.

### VSI six-step
A monte è presente un raddrizzatore, successivamente il VSI fornisce per 180° la tensione a monte su una determinata fase, così via sulle altre fasi, sfasate di 120°, si costruisce una terna trifase di onde quadre, le concatenate saranno la combinazione di due tensioni stellate.
Collegando il motore a stella, si ottiene una forma d'onda di fase con tensione che va da $2V/3$ a $-2V/3$ con un valore intermedio.
Anche in questo caso lo spettro è ricco di armoniche in tensione e identico allo spettro ricavato precedentemente per il CSI.
A causa dell'impedenza però si riduce il contenuto armonico delle correnti nella macchina.
$$
Z_{k} = \frac{R'_{r}}{s_{k}} + jk\omega L
$$
Per alimentare un motore elettrico conviene utilizzare un VSI perché dal punto di vista delle armoniche è migliore ma in realtà si utilizzava comunque il CSI perché i circuiti di spegnimento erano più semplici, erano molto più voluminosi rispetto all'inverter.

## Modulazione PWM
In alternativa si può utilizzare una modulazione **PWM** per fornire la tensione in uscita, esistono infinite forme di modulazione, lineare, simmetrica, sinusoidale o vettoriale.
### Modulazione sinusoidale
Si suppone di dividere il periodo fondamentale della tensione desiderata in tanti intervalli più piccoli, si può far in modo da fornire in ogni intervallo una tensione rettangolare con durata tale che il valore medio sia pari al valore medio della sinusoide nello stesso intervallo.
Se l'intervallo $\Delta$ è molto piccolo si può approssimare meglio la sinusoide.
Il principale vantaggio di questa tecnica è che si può controllare anche l'ampiezza della tensione in uscita agendo sul secondo stadio, nei casi precedenti invece era il primo stadio a controllare le ampiezze e il secondo controllava solo la frequenza.
I convertitori VSI con modulazione permettono di isolare il comportamento della capacità di filtro, è più rapido eseguire variazioni di tensione.

Vedi [[controllo scalare della macchina asincrona]].
