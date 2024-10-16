Fondamentale per la [[Sicurezza elettrica in BT|sicurezza elettrica]] elettrica è l'utilizzo di interruttori automatici. Vanno innanzitutto distinte le due tipologie di contatto elettrico: **diretto** e **indiretto**.

Il primo si ha in caso di contatto con una parte dell'impianto normalmente in tensione, il secondo se avviene un contatto con la **massa**, una parte di impianto normalmente non in tensione che va in tensione a causa di un guasto dell'isolamento principale.

# Contatti indiretti
Il sistema principale per proteggere dai contatti indiretti è quello di utilizzare un doppio isolamento, garantisce di poter sopportare un guasto all'isolamento principale, non sempre è fattibile se le apparecchiature sono grandi, può non convenire da un punto di vista economico.
Si deve dunque garantire che nel caso in cui una massa vada in tensione, quel valore non deve essere pericoloso. Oppure si deve disporre di dispositivi in grado di disalimentare l'impianto in caso di guasto.

Il contatto può non avvenire con una massa appartenente all'impianto ma mediante una *massa estranea* ovvero non facente parte dell'impianto, in questo caso si potrebbe avere un potenziale diverso da quello di terra, aumentando di fatto la resistenza di terra pari al rapporto tra la tensione totale e la corrente dispersa.

È considerata massa estranea **qualsiasi parte metallica non facente parte dell'impianto con resistenza inferiore ai $1000\Omega$ negli impianti ordinari e $200\Omega$** in quelli particolari.

Si considera la $U_{tp}$ (touch-permissible) la tensione di contatto massima ammissibile, espressa dalle curve di sicurezza, è la tensione che si ha durante il contatto della persona.
In condizioni cautelative si trascura la resistenza di contatto, ponendo la resistenza del corpo in parallelo alla resistenza $R_E$ che invece è quella che fornisce la tensione di contatto  a vuoto. 
La $U_{tp}$ va confrontata con la $U_{stp}$, ovvero la tensione di contatto a vuoto.

La tensione $U_{sp}$ è la tensione di passo permissibile, si instaura tra due piedi posti a distanza di un metro in caso di guasto a terra, è superiore alle precedenti, circa 3 volte la $U_{tp}$ a causa della minore pericolosità di un contatto piede-piede.

Esistono inoltre tre tipologie di sistemi in bassa tensione, in base allo stato del neutro in cabina e delle masse:
- IT, neutro in cabina isolato, masse connesse a terra nell'impianto, si hanno correnti di guasto piccole a causa delle piccole capacità parassite, si ha però una sovratensione delle altre fasi. L'energia immagazzinata dalle capacità parassite passa da $3\frac{1}{2}CE^2$ a $3CE^2$, inoltre le sovratensioni, in dinamica sono intermittenti, per questo motivo si preferisce spesso usare gli altri due sistemi. 
- TT, entrambi messi a terra, se la cabina è pubblica.
- TN(S-C), neutro in cabina messo a terra, masse connesse al neutro, mediante un conduttore Separato o mediante il conduttore di neutro (conduttore PEN), se la cabina è privata.

## Sistema TN
Non esiste un collegamento diretto a terra delle masse ma un collegamento mediante il conduttore di neutro, si può usare lo stesso conduttore di neutro oppure uno dedicato.
Esiste un unico impianto di terra in cabina, l'anello di guasto dunque prevede la richiusura attraverso l'intero sistema di conduttori attivi, dunque la corrente di guasto è molto elevata, limitata solo dalla resistenza dei conduttori.
In questo caso il guasto è riconosciuto e interrotto dall'interruttore magneto-termico, già predisposto alla protezione della linea da eventuali sovraccarichi.

In caso di contatto però si pone in parallelo la resistenza della persona in contatto, in serie con la resistenza del neutro in cabina.
Idealmente la corrente attraverserebbe tutta il circuito a bassa impedenza, costituito dalla linea, per un tempo prolungato però potrebbe esserci un rischio per la persona.

Va dimensionato l'apparecchio di protezione per il carico nominale da proteggere. La resistenza $R_n$ non è sempre controllabile se la cabina non è privata ma di proprietà del distributore, esso non è tenuto a garantire un determinato valore della resistenza di neutro. Di norma per realizzare un sistema TN non si dovrebbe superare una resistenza di neutro di $180\Omega$, in ogni caso non è semplice determinare la corrente che si richiude nella persona in caso di guasto.

## Sistema TT
In caso di cabina pubblica è richiesto un sistema di protezione mediante un impianto di terra dedicato e connesso alle masse.
In caso di guasto, la maglia di guasto si richiude attraverso la resistenza dell'impianto di terra e del terreno fino al raggiungimento del neutro in cabina.
Questa corrente sarà sicuramente molto piccola, per questo motivo non si può interrompere l'alimentazione mediante un interruttore automatico.

Si traccia il circuito equivalente

Si calcola il circuito equivalente di Thevenin, ai cui capi c'è la tensione applicata alla persona in contatto con la massa in tensione a causa del guasto.
$$
E_{eq} = U_{0} \frac{R_{E}}{R_{E}+R_{N}}\quad R_{eq}=\frac{R_{E}R_{N}}{R_{E}+R_{N}}
$$
La resistenza $R_N$ è comunque più piccola della $R_E$, dunque prevale nel parallelo.

Il calcolo della resistenza di terra parte a prescindere dalla massima tensione di contatto
$$
R_{E}\leq \frac{50}{180}R_{n} \simeq 0.28R_{n}
$$

In caso di guasto, ci sarà una corrente di guasto $I_g$ che andrà rilevata dall'interruttore differenziale, va fatto il seguente coordinamento:
$$
R_{E}\cdot I_{dn} \leq U_{L} \Rightarrow R_{E} \leq \frac{U_{L}}{I_{dn}} = \frac{50}{30}\cdot 10^3 \simeq 1800 \Omega
$$
con un interruttore differenziale da $30mA$.
In ambito industriale può essere utilizzato anche un interruttore da $50mA$, aumentano le correnti di dispersione a causa della grandezza dell'impianto.
I valori normalmente utilizzati sono $10, 30, 100, 300,1000mA$ a seconda dell'applicazione, la dimensione dell'impianto e la selettività.

Per la normativa, il costruttore dell'interruttore differenziale deve fornire i tempi di intervento per $I_{dn},2I_{dn}, 5I_{dn}$ pari a $0.3,0.15,0.04s$ al fine di rimanere al di sotto della curva $C_1$ e garantire la sicurezza.

### Interruttori differenziali in parallelo
Si ipotizzi di avere due interruttori differenziali con eventualmente un valore di interruzione differente, va calcolata la $R_E$ in base al valore del differenziale più alto.
$$
R_{E} \leq \frac{U_{L}}{I_{dn}}
$$
L'interruttore differenziale con la corrente più grande garantisce la massima resistenza di terra, se si rieseguisse il calcolo con una corrente inferiore si otterrebbe una resistenza più alta.

### Interruttore differenziale con più carichi
Questa situazione può essere pericolosa nel caso in cui ci sia un primo guasto del neutro, un guasto della fase in un secondo momento si richiuderebbe nel neutro guasto, senza richiudersi in cabina, non verrebbe rilevato dall'interruttore differenziale.
Per questo motivo è fondamentale utilizzare un unico impianto di terra, in caso di doppio guasto si avrebbe una corrente di corto circuito.

### Interruttori differenziali a cascata
Si ha un interruttore differenziale principale, a cui sono collegati più interruttori differenti, ognuno alla propria linea, si sceglie questa soluzione quando l'impianto è molto vasto oppure un impianto molto vecchio può avere correnti di dispersione troppo elevate che sollecitino l'interruttore unico, non garantendo la continuità del servizio.
Possono essere ad esempio interruttori trifase o monofase, tutta la parte di impianto dall'interruttore generale ai singoli differenziali non sarebbe protetta, si deve garantire che non vi siano masse tra queste due parti, oppure garantire un doppio isolamento.
Se ciò non è possibile va necessariamente posto un differenziale a monte, producendo appunto il sistema di interruttori differenziali in serie, va risolto però il problema della selettività.

Ad un interruttore differenziale sono legati dei valori di corrente differenziale e il tempo di massimo intervento associato a quella corrente:
$$
\begin{aligned}
I_{dn}\ \quad &  2I_{dn} & 5I_{dn} \\
0.3s\ \quad & 0.15s & 0.04s
\end{aligned}
$$
Il valore del tempo massimo di intervento non è sufficiente a garantire la selettività, va osservata una fascia di tempo che indichi un minimo (curva di non intervento, detta anche tempo di tempo massimo di non intervento) ed un massimo. Entrambe le curve devono essere al di sopra della curva di massimo intervento del differenziale a valle, che deve intervenire prima.

## Interruttori differenziali selettivi
Detti anche interruttori di tipo $S$ sono più lenti dei precedenti, hanno i seguenti tempi minimi e massimi di intervento:
$$
\begin{aligned}
I_{dn}\ \quad &  2I_{dn} & 5I_{dn} \\
0.5s\ \quad & 0.2s & 0.15s \\
0.13s\ \quad & 0.06 & 0.05
\end{aligned}
$$
La curva di non intervento del selettivo non deve essere al di sotto della curva di massimo intervento dell'interruttore a valle.
(rivedi sulle norme)


## Masse estranee
Si ha un carico monofase connesso al proprio impianto di terra, rappresentata da una resistenza $R_E$. Si supponga ci sia una massa estranea come ad esempio una tubatura, collegata al terreno; si supponga il contatto contemporaneo tra la massa estranea e la massa dell'apparecchio connessa all'impianto di terra, mediante una resistenza del corpo $R_B$.
In un impianto TT, in condizioni ordinarie va garantita una tensione limite $U_L$ di $50V$. 
La massa estranea, connessa a terra presenta una propria resistenza di terra, aggiuntiva, le curve di pericolosità erano state calcolate usando una resistenza verso terra di $1000\Omega$ in condizioni ordinarie e $200\Omega$ in condizioni particolari. Se la resistenza verso terra della massa estranea è superiore a questi valori, va allora connessa all'impianto di terra mediante un conduttore equipotenziale principale.

Inoltre si potrebbe avere una interruzione della continuità della massa estranea, generando una ulteriore resistenza di terra equivalente, di valore diverso, per questo motivo per ogni *radice* della massa estranea va garantito il collegamento all'impianto di terra, altrimenti introdurrebbero un potenziale differente dal potenziale di terra.

## Impianto industriale con schermo
In caso di impianto industriale che presenti conduttori in guaina o sbarra, con un isolamento principale ed una guaina esterna, schermante, questa guaina viene utilizzata come conduttore di protezione e connessa a terra.
L'interruttore differenziale è composto da un dispositivo toroidale che circondi tutti i cavi.
Si separa il conduttore di protezione dal cavo e lo si fa circolare due volte attraverso il toroide, in modo da avere un flusso indotto in caso di guasto sullo schermo che solleciti l'interruttore.

