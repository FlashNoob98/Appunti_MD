# Caratteristiche generali

Un sistema di generazione fotovoltaica è composto da una sorgente primaria, il Sole, un generatore
fotovoltaico (PVG) e infine c'è un inverter, solitamente a doppio stadio: uno stadio in ingresso
DC/DC e un secondo stadio che è il vero inverter DC/AC, infine un filtro e poi il collegamento
alla rete.
Sono necessarie diverse competenze per costruire un generatore fotovoltaico, a partire dalla 
fisica dei semiconduttori ad una serie di conoscenze economiche per gestire la connessione alla rete.

  

I pannelli fotovoltaici possono essere connessi in serie e/o in parallelo fino al raggiungimento
di una tensione a vuoto massima di 1000 V, per normativa europea.
Il Sole è un emettitore perfetto di radiazioni ad una temperatura di circa 5800 K.
Molte radiazioni sono bloccate dall'atmosfera.

  

La conversione fotovoltaica è una delle sorgenti più pulite per generare energia elettrica; è considerata
una sorgente inesauribile, non ha parti in movimento, non produce rumore e questo la rende robusta
e affidabile.

L'energia associata alla radiazione solare è pari a: $E = hc/\lambda$ dove $h$ è la costante di Plank, $c$ la velocità 
della luce e $\lambda$ la lunghezza d'onda,
espressa in elettronvolt: $1.24/\lambda[\mu m]$

Nel generatore fotovoltaico ha luogo l'effetto fotovoltaico, ovvero la conversione dell'energia luminosa
in elettrica.

Il fenomeno dell'effetto fotovoltaico si genera nella cella, composta solitamente da un materiale 
semiconduttore, solitamente silicio.



Per quanto riguarda il convertitore statico di potenza, è a doppio stadio: DC/DC, solitamente di tipo
boost (potrebbe anche essere un buck), si occupa dell'inseguimento del punto di massimo
sul pannello fotovoltaico; l'inverter controlla invece la corrente in uscita verso la rete.

Il filtro in uscita è di natura prevalentemente induttiva per la connessione alla rete elettrica o ad un 
carico.

  

Definizione di rete elettrica fornita da ARERA:
Un sistema elettrico a configurazione complessa che, per
effetto dei rapporti intercorrenti fra i diversi utenti del sistema, non può essere ricondotto a uno
schema semplificato in cui ci sia un unico punto di connessione, un unico produttore di energia
elettrica responsabile della gestione degli impianti di produzione connessi al predetto sistema e un
unico cliente finale. Un tale sistema è pertanto riconducibile a uno schema in cui coesistono una
pluralità di clienti finali e/o produttori di energia elettrica, chiamati anche prosumer (producer and consumer).


Avendo le fonti rinnovabili, saranno necessari sempre più produttori; le rinnovabili sono però non
predicibili. Il prezzo dell'energia è calcolato sull'ultimo kWh, ovvero dalle centrali a gas che hanno un 
elevato costo in ingresso dovuto al combustibile e un basso rendimento di impianto; se il prezzo fosse imposto
dalle fonti rinnovabili si avrebbero invece costi decisamente più bassi, non c'è un costo di materia
prima.

  

# Giunzione P-N

È alla base della conversione fotovoltaica; il silicio è tra i materiali semiconduttori più utilizzati per i dispositivi
elettronici assieme a germanio e gallio, ed è uno degli elementi più abbondanti in natura, in forma di 
silicati costituisce circa il 25\% della crosta terrestre.

I materiali si possono classificare in base alla conducibilità:
Isolanti e conduttori hanno valori fissi di conducibilità, mentre i semiconduttori possono variare la loro conducibilità in 
un intervallo che può essere reso più ampio in seguito ad operazioni di drogaggio.
Il silicio è nella quarta colonna della tavola periodica, ha quattro elettroni di valenza, ha la struttura
del diamante: un atomo al centro e quattro disposti ai vertici di un tetraedro. Alla temperatura di 0 K gli elettroni sono 

vincolati al reticolo, non sono disponibili per la conduzione; a temperature superiori, come quella ambiente, acquistano 
una sufficiente energia termica per cui la vibrazione termica consente di rompere
un legame covalente e un elettrone si rende disponibile alla conduzione, viene detto elettrone libero o di conduzione,
generato per generazione termica, esclusivamente grazie alla vibrazione termica, ovvero che la temperatura sia
maggiore dello 0 K.

La concentrazione intrinseca di portatori liberi è pari a $1.45 \times 10^{10} cm^{-3}$, il numero di atomi di silicio in un $cm^3$ è pari a $5\times 10^{22}$; si avrebbe un elettrone libero ogni 3500 miliardi di atomi; se applicassi una 
differenza
di potenziale esterna al materiale, darei origine ad un campo elettrico in grado di accelerare questi elettroni e 
quindi determinare una conduzione elettrica, ovvero
una corrente elettrica diversa da zero. Questo meccanismo di trasporto dovuto al campo elettrico
prende il nome di corrente di trascinamento o di *drift*.

Ad una temperatura maggiore di 0 K
un elettrone può prendere energia sufficiente rompendo un legame covalente passando dalla banda di valenza
a quella di conduzione e lasciando una 
lacuna che potrebbe essere colmata da un altro elettrone; la lacuna è definita come una particella fittizia di carica positiva che esprime il moto
degli elettroni di valenza che passano in banda di conduzione; un altro elettrone occupa la lacuna che si sposta in verso opposto. Ho elettroni in banda di conduzione e lacune in banda di valenza.

Poiché una lacuna si forma quando un elettrone si è liberato, in un semiconduttore intrinseco il 
numero di lacune è pari a quello di elettroni; sia $n$ la concentrazione di elettroni, pari a
$p$ la concentrazione di lacune e sono pari ad $n_i$ la concentrazione intrinseca. La legge dell'azione di massa afferma 
che $n \times p = n_i^2$.

Per passare dalla banda di valenza a quella di conduzione, gli elettroni devono avere un'energia $E_g$ pari all'ampiezza
della banda proibita; nel caso del silicio, $1.12 eV$ (elettronVolt).

Nel semiconduttore si ha una certa banda proibita; nel caso di un isolante è maggiore di $5 eV$, molto ampia, gli 
elettroni
non hanno solitamente energia sufficiente per passare in banda di conduzione,
mentre in un conduttore è praticamente nulla.

## Drogaggio

Se si introducono delle impurità mediante il processo di drogaggio, allora gli atomi droganti introducono
i livelli energetici delle impurità; un atomo drogante va a sostituire un atomo di silicio nella struttura
cristallina del silicio puro. Gli atomi droganti possono essere quelli pentavalenti come l'arsenico, il fosforo o l'antimonio o quelli trivalenti come il boro, il gallio e l'indio (5ª o 3ª colonna
della tavola periodica).

Se si sostituisce un elemento pentavalente si ha un silicio di tipo **n**; gli elettroni saranno maggioritari perché

l'atomo drogante ha un elettrone in più;
mentre se sostituisco un elemento della terza colonna ottengo silicio di tipo **p**, le lacune saranno 
maggioritarie.

Nel caso dell'atomo di fosforo, è pentavalente; se va a sostituire un atomo di silicio, ha 5 elettroni di valenza, 4 coprono i legami
covalenti con gli atomi di silicio vicini e un elettrone resta libero per la conduzione; si dice che dona un
elettrone diventando uno ione donatore, avendo donato un elettrone avrà carica positiva. Discorso
inverso per gli atomi trivalenti; acquista un elettrone, diventa uno ione accettore e diventa uno ione negativo.

Con l'introduzione controllata di droganti si possono controllare le cariche libere nel semiconduttore
mediante un processo di ionizzazione dell'atomo drogante.
Dato che l'energia di ionizzazione necessaria ad attivare questo processo è piccola e molto minore di quella termica a temperatura ambiente
si ottiene una concentrazione di ioni e di cariche libere superiore a quella presenti in un cristallo intrinseco, dunque un
cristallo drogato si dice estrinseco.

  

Si hanno due meccanismi di generazione di cariche libere: l'azione termica e quella di ionizzazione degli atomi di
impurità introdotti nel cristallo puro;
dato che il meccanismo di ionizzazione è più efficiente di quello di generazione termica, si ha la maggior parte degli elettroni in banda di conduzione a temperatura ambiente grazie alla ionizzazione.


I meccanismi di trasporto delle cariche libere dipendono dalla corrente di trascinamento associata alla presenza di
un campo elettrico, sotto l'effetto del quale si muovono sa gli elettroni che le lacune e 
e dalla corrente di diffusione che è invece associata al gradiente di concentrazione dei portatori.

La seconda è dovuta alla differente concentrazione delle cariche in zone differenti al fine di raggiungere
l'equilibrio.

Per avere diffusione ho bisogno di una distribuzione non uniforme delle cariche all'interno del cristallo di silicio e grazie
al drogaggio è possibile generare
zone a concentrazioni differenti per attivare questo meccanismo di trasporto delle cariche.
La corrente di diffusione è, per convenzione, in verso opposto al moto degli elettroni.


La giunzione PN si ottiene drogando con atomi donatori (N) la regione superficiale di un semiconduttore già
drogato di tipo P.

Si avrà un'alta concentrazione di lacune nella regione P e un'alta concentrazione di elettroni nella regione di tipo N.
In virtù di questa differenza le lacune diffonderanno da P ad N e gli elettroni in verso opposto, da N verso P.
Nel momento in cui una lacuna si sposta da P verso N, lascia uno ione accettore non più compensato; nella
giunzione si accumuleranno ioni negativi verso la regione P non più compensati, e invece degli ioni donatori non 
compensati nella regione N, in cui si accumulerà una carica positiva.

La regione intermedia prende il nome di regione di carica spaziale, in cui si ha una corrente di 
trascinamento a causa dell'effetto del campo elettrico, che attiva il meccanismo del trasporto.
Le lacune si muovono nella stessa direzione del campo elettrico e gli elettroni in verso opposto,
le correnti di trascinamento sono entrambe nella direzione del campo elettrico; dunque la corrente
di trascinamento fluisce in verso opposto a quella di diffusione.

Le lacune diffondono da P ad N, gli elettroni diffondono da N a P; sotto l'effetto del campo elettrico
gli elettroni si muovono in direzione opposta al campo elettrico; la corrente di trasporto si oppone a
quella di diffusione.

Il verso del campo elettrico è tale da costringere sempre e comunque i portatori minoritari, ovvero gli elettroni
che si trovano nel lato P e le lacune che si trovano nel lato N ad 
attraversare la giunzione.

La giunzione P-N è composta da due regioni neutre e una regione di carica spaziale chiamata regione di svuotamento;
la concentrazione di ioni sarà maggiore di quella di portatori liberi.

Al campo elettrico all'interno della regione di carica spaziale si può associare una differenza di potenziale, chiamata 
potenziale di contatto o intrinseco o built-in; questa differenza di potenziale crea un gap su quelli che sono i movimenti
degli elettroni e delle lacune, nel senso che le successive cariche che vorranno diffondere 
incontreranno questa barriera di potenziale, pari a $qV_{bi}$ con $V_{bi}$ il potenziale del campo elettrico e
$q$ la carica elettrica; chi si muove invece per meccanismo
di trasporto è agevolato; all'equilibrio quelli che si muovono per effetto del campo elettrico sono i minoritari, quindi
 saranno
pochi e riescono a compensare i pochi elettroni che si muovono per diffusione che abbiano una energia sufficiente a superare questa barriera, all'equilibrio termodinamico i due fenomeni si equilibrano.

Se applico una polarizzazione alla giunzione, ovvero una differenza di potenziale all'esterno, in polarizzazione diretta, la 
barriera si abbassa e vi saranno più portatori in grado di diffondere,
si ha la conduzione delle cariche maggioritarie che attraversano la giunzione.
Nel caso della polarizzazione inversa si ha un incremento della barriera; i maggioritari avranno una maggiore
difficoltà ad attraversare la barriera; non vi sarà differenza invece
per i minoritari; non cambia il loro numero, si avrà comunque una piccola corrente detta di polarizzazione inversa.

La giunzione P-N ha fondamentalmente la caratteristica di un diodo.
In caso di polarizzazione diretta, l'abbassamento della barriera di potenziale determina un incremento notevole del 
numero di portatori maggioritari in grado di attraversare la giunzione e si ha quindi un incremento esponenziale della corrente.

In polarizzazione inversa si ha solo una piccola corrente di polarizzazione inversa, dell'ordine di $10^{-11}\sim 10^{-9}\ A/cm^2$.
 

L'equazione della corrente nel diodo:

$$
I = I_0(e^{V/nV_t}-1)
$$
Con $I_0$ la corrente di polarizzazione inversa,
$V$ la tensione ai capi del diodo, ovvero della giunzione,
$V_t$ è la tensione termica pari a $kT/q$ con $k$ la costante di Boltzmann,
$n$ è il fattore di idealità del diodo, che tiene conto delle non idealità presenti nella giunzione
ad esempio la ricombinazione nella regione di svuotamento, ovvero che un elettrone che sta diffondendo
attraverso la regione di svuotamento si ricombina con una lacuna, annullando il suo contributo di corrente.
Una non idealità della giunzione possono essere anche difetti nel cristallo; la giunzione è tanto più ideale
quanto più $n$ tende ad 1 per valori elevati di corrente, può arrivare a 2 per valori più bassi di corrente.
La tensione ai capi del diodo in conduzione è solitamente molto piccola; può essere considerato un 
cortocircuito, viceversa un circuito aperto per tensione inversa.

# Generatore fotovoltaico

La conducibilità di un semiconduttore dipende dalla concentrazione di portatori liberi; per rompere un 
legame covalente formato da una coppia elettrone-lacuna è necessaria un'energia minima pari alla banda proibita, pari 
a 1.12 eV nel caso del silicio.

Se i fotoni della radiazione solare che incidono sulla cella hanno energia sufficiente a generare una coppia elettrone-lacuna,
si ha l'aumento della conducibilità del materiale; questo fenomeno prende il nome di fotoconducibilità. Si generano 
delle coppie nel cristallo di silicio, ma 
in maniera "confusa"; ne è solo aumentata la conducibilità, non si ha però alcuna generazione di
energia.

Per costringere le cariche ad attraversare il cristallo di silicio, questo deve essere drogato di tipo PN.
Con l'incidenza della radiazione sulla giunzione P-N si genera una coppia elettrone-lacuna in prossimità della 
regione di svuotamento, e vien separata dal campo elettrico.
Si avrà oltre ad un aumento della conduzione, un accumulo di elettroni da un lato e di lacune dall'altro, ovvero la 
giunzione si auto-polarizza; se chiusa su un carico si avrà una corrente elettrica, questo fenomeno prende il nome
di effetto fotovoltaico.

La corrente fotogenerata è dovuta ai portatori minoritari, perché si muovono sotto l'effetto del campo.
elettrico.
Supponiamo di essere in regione P; si crea la coppia elettrone-lacuna; sotto l'effetto del campo elettrico, l'elettrone si sposta, 
è minoritario nella regione P, la lacuna è costretta a rimanere in regione P.
La cosa opposta si ottiene se la coppia elettrone-lacuna si forma nella regione N, saranno le lacune ad attraversare
la giunzione.

Per creare la giunzione si fa un doppio drogaggio, prima P e poi si inserisce un drogaggio di tipo N per formare
la giunzione.

Il processo produttivo inizia con la sabbia che è ricca di silicio e silicati,
viene disposta in un forno, ottenendo un cristallo puro al 98%, composto da grani cristallini
con differenti orientazioni reticolari.

Con processi di distillazione si ottiene un silicio di grado elettronico, policristallino, è più puro del precedente.
Si ottengono man mano cristalli di silicio sempre più puri, ottenendo un cilindro di nome carotone, 
un pezzo di silicio monocristallino.
Da ogni fetta del wafer si tagliano delle celle rettangolari.
Sulla cella sono disposti i "fingers" che sono contattati dai i bus-bar della cella, ovvero delle stringhe leggermente più grandi che ne permettono il collegamento in serie tra le varie celle.
Per formare un modulo fotovoltaico, le celle sono connesse in serie.

Una giunzione PN ha una tensione piccola; per questo motivo vanno connesse in serie; in un pannello
commerciale ci sono tre sottomoduli dove sono connesse in serie, poi connessi in serie tra loro.
Ciascun sottomodulo è connesso ad un diodo di bypass, necessario a bypassare il modulo in caso di un differente
irraggiamento. Un modulo commerciale è composto da tre sotto-moduli, connessi in serie.

## Definizione di irradianza

La potenza specifica per unità di area in $W/m^2$ associata alla radiazione luminosa di lunghezza
d'onda $\lambda$, è dunque una potenza così definita:
$$
P = \Phi \times hc/\lambda
$$
dove $\Phi$ è il numero di fotoni che incide sulla superficie di aria unitaria nell'unità di tempo.

Non tutti i fotoni sono necessari alla conduzione fotovoltaica; solo quelli con energia sufficiente
a generare una coppia elettrone-lacuna; nel caso della lunghezza d'onda deve essere inferiore a $1.1 \mu m$,
ovvero un'energia superiore o uguale a quella della banda proibita del silicio ($1.12 eV$).

L'energia dei fotoni a lunghezza d'onda superiore è dispersa in calore; quella a lunghezza inferiore
serve a generare le coppie elettrone-lacune, ma quella che avanza anche si dissipa in calore.
Non tutta la radiazione incidente sulla cella solare produce energia:,
C'è un fenomeno di mismatch spettrale.
Un fotone genera una coppia se ha energia sufficiente; dunque la capacità di generare cariche 
elettriche dipende anche dal numero di fotoni; dunque è fondamentale anche il numero di fotoni che incidono.
L'efficienza di conversione di un sistema fotovoltaico, è definita come il rapporto tra la potenza massima che è possibile 
ricavare e la potenza luminosa incidente; il limite assoluto di questo rapporto è dovuto al mismatch
spettrale e dunque dal semiconduttore utilizzato per realizzare la cella solare.

Il limite si calcola con il principio dell'equilibrio dettagliato (che non vedremo); si basa su considerazioni
di natura termodinamica; il risultato invece è un grafico che mostra che l'efficienza massima raggiungibile da un 
materiale, in funzione della sua banda proibita,
si ottiene proprio con il silicio; è il materiale che teoricamente potrebbe raggiungere la massima
efficienza di circa il 40\%; questo è il limite superiore massimo che nessuna tecnologia fotovoltaica potrà mai
superare, è un limite intrinseco del materiale.

Attualmente si raggiunge a livello pratico un'efficienza del 24\% delle celle presenti sul mercato.
È un'efficienza bassa, ma non si paga l'energia primaria; dunque non teniamo conto dell'energia solare
incidente per calcolare l'efficienza di conversione del convertitore; consideriamo solo l'energia elettrica
effettivamente prodotta dalle celle per iniziare il calcolo di efficienza di conversione.

## Caratteristica corrente-tensione di una cella solare
A partire da una giunzione P-N direttamente polarizzata,
la corrente è dovuta principalmente alla diffusione dei maggioritari a causa dell'abbassamento della
barriera di potenziale.
L'incidenza della radiazione solare fa si che questa si auto-polarizzi, si determina una differenza di potenziale che va a 
ridurre la barriera di potenziale per i maggioritari che possono diffondere più facilmente.
La corrente fotogenerata è dovuta ai minoritari che si muovono per il campo elettrico; si hanno quindi
tre contributi di corrente:
- Diffusione
- Trasporto
- Fotogenerata

Il meccanismo di diffusione si oppone a quello di fotogenerazione; la corrente di fotogenerazione complessiva
è data dalla somma delle correnti degli elettroni e delle lacune.
Per ottenere in modo semplice la caratteristica si utilizza il principio di sovrapposizione degli effetti.

La corrente fotogenerata è considerata come una corrente costante; dunque modellata da un generatore ideale
di corrente.

La giunzione è un diodo con la sua caratteristica esponenziale; a tensione nulla si ha una corrente $I$
pari alla corrente di cortocircuito; è uguale a $I_{ph}$ (fotogenerata); per $V < V_{soglia}$ del diodo invece
la corrente $I$ è ancora uguale a $I_{ph}$, come schematizzato in figura.

<center>

![[cella_PV_diodo_semplice.svg]]

</center>

Quando la tensione supera la tensione di soglia del diodo, il valore della corrente $I$ diventa $I_{ph}-I_d$ e
tende verso il basso;
la $I_d$ cresce esponenzialmente all'aumentare della tensione, fino alla tensione di circuito aperto 
in cui la corrente si annulla e quella fotogenerata sarà pari alla corrente che circola nella giunzione, ovvero ogni portatore fotogenerato
che attraversa la giunzione per effetto del campo elettrico, è compensato da quello che lo attraversa per diffusione, alla tensione di circuito aperto $V_{oc}$.

La giunzione PN, dal punto di vista della conversione fotovoltaica, agisce come un elemento parassita; la corrente
di polarizzazione diretta  della giunzione si oppone alla corrente fotogenerata, ma è proprio quella che permette la 
conversione dell'energia solare in energia elettrica. Se non esistesse la giunzione si avrebbe solo un aumento della
conducibilità del silicio, se esposto alla radiazione solare.

Se si chiude il circuito su un carico, il punto di lavoro dipenderà dall'intersezione delle caratteristiche della
cella e del carico;
si può avere un punto a bassa tensione e alta corrente o alta tensione e bassa corrente; esiste
un punto di massima potenza, Maximum Power Point (MPP), nel quale si vuole lavorare; proprio
per questo motivo è necessario l'inverter DC-DC per inseguire il MPP ed estrarre la massima potenza dal pannello,
variando l'impedenza vista dal pannello.

## Efficienza della cella solare

Si calcola considerando la massima potenza erogabile dalla cella rispetto alla potenza posseduta dalla radiazione solare 
incidente, corrispondente allo spettro standard normalizzato, ovvero $1 kW/m^2$.
Si mostra la caratteristica della cella allo spettro standard uniforme e ad un irraggiamento con potenza inferiore di 
$800w/m^2$, come mostrato in figura:

<center>

![[grafico_MPP.svg]]

</center>


Non è detto che la cella sia irraggiata in maniera uniforme; potrebbero verificarsi dei massimi
locali in caso di irraggiamenti non uniformi.
In questo caso si riduce il valore di corrente; il punto di massimo si sposta.
In caso di irraggiamento disuniforme, una parte del pannello è a 1 kW, un'altra è a 0,8 kW, per 
qualsiasi motivo ambientale.
In questo caso la caratteristica (ingrandita) si modifica come mostrato in figura:

<center>

![[grafico_MPP_modificato.svg]]

</center>


Ho due massimi locali; integrando l'area
posso capire il punto a potenza maggiore;
quindi dovrò avere un boost per rispettare
la minore tensione del pannello e avere una
tensione sul DC link elevata per far funzionare
l'inverter; per questo motivo devo usare il boost.
Se usassi un buck potrei non riuscire ad imporre la massima potenza sul pannello perché dovrei rispettare come
vincolo la minima tensione sul DC-Link per garantire il funzionamento dell'inverter presso la rete.

## Definizioni delle potenze e dei rendimenti

Si riportano alcune grandezze caratteristiche delle celle fotovoltaiche:

-  La massima potenza ideale è $V_{oc} \times I_{sc}$, come se la cella potesse erogare la corrente di cortocircuito fotogenerata alla tensione di circuito aperta.
- La massima potenza reale è invece il prodotto tensione-corrente nel punto di massimo sulla caratteristica.
	$$
   P_{\text{max real}} = V_{MPP}\cdot I_{MPP}
   $$
  
- Il fill factor (fattore di riempimento) è il rapporto tra la potenza reale e quella ideale, si potrebbe riscrivere l'efficienza in funzione del fill factor considerando la potenza ideale anzichè quella reale, moltiplicando per il fill factor.
  $$
  \text{Fill Factor} = \frac{P_{\text{max real}}}{V_{oc}I_{sc}} = \frac{V_{MPP}\cdot I_{MPP}}{V_{oc}I_{sc}}
  $$
  Se il fill factor tende ad 1, la cella si comporta come un generatore ideale di corrente, ma nella realtà una buona cella ha un fill factor di 0,78 fino a 0,82.

Si potrebbe massimizzare l'efficienza massimizzando separatamente la tensione e la corrente nel punto di massimo
ma si può dimostrare che il punto di massimo si trova solitamente all'85-90\% della $V_{oc}$.
Le non idealità causano un limite all'efficienza reale che non supera il 27%.

## Effetto della temperatura

A causa del mismatch spettrale, molta radiazione si perde in calore; se il fotone incidente ha lunghezza d'onda
maggiore non si assorbe energia dal materiale; se ha una lunghezza d'onda inferiore, una parte
viene convertita in energia elettrica, mentre una restante viene comunque convertita in calore; fenomeno chiamato
termalizzazione; solitamente la temperatura della cella eccede i 50 °C; all'incrementarsi della 
temperatura si riduce la $V_{oc}$ ma aumenta la $I_{cc}$, ma questo incremento non è tale da compensare la riduzione
di tensione $V_{oc}$; dunque l'effetto netto è una riduzione della potenza generata all'aumentare della 
temperatura di esercizio; nei datasheet vengono ad esempio forniti i coefficienti di correzione 
della temperatura di esercizio.

Questo sarà positivo per la $I_{cc}$ ma negativo per la  $V_{oc}$ e in misura maggiore, dunque complessivamente il
coefficiente correttivo della potenza massima sarà negativo.
Si ha una riduzione della potenza massima che è possibile generare all'aumentare della temperatura.
I coefficienti vengono calcolati nelle condizioni NOCT (Normal Operating Cell Temperature),
ovvero una cella sottoposta a $800 W/m^2$ con temperatura ambiente di 20 °C e velocità del vento di $1 m/s$.

Si caratterizzano i parametri parassiti: la tensione $V$ ai capi della cella è misurata ai terminali
esterni e non alla giunzione; c'è un certo percorso; ci sono i contatti elettrici esterni e quindi degli effetti
resistivi che determinano una caduta di tensione; la tensione all'esterno della cella è minore
di quella presente ai capi della giunzione; gli effetti dissipativi vengono tenuti in conto da una resistenza
serie; la caratteristica diventa:

$$

I = I_{ph} - I_0\left( e^{\frac{V+R_s}{nV_t}} -1\right)

$$

Al crescere della resistenza serie,
non varia la tensione $V_{oc}$ ma si riduce la corrente di cortocircuito; si dice che la $R_s$ modula
la pendenza della caratteristica nell'intorno della tensione di circuito aperto. La corrente di cortocircuito diminuisce: se lo 
chiudessi infatti in cortocircuito, la $R_s$ sarebbe in parallelo alla giunzione, 
dunque $V_d = R_s \cdot I_{sc}$; se $R_s$ aumenta, aumenta $V_d$ che se diventa maggiore della tensione di soglia
del diodo aumenta la corrente del diodo, in maniera esponenziale, ma se $I_d$ cresce, $I_{sc}$ pari a $I_{ph}-I_d$ 
diminuisce; tiene conto delle cadute
ohmiche lungo il percorso dalla giunzione ai terminali. A rigore la resistenza serie non è un vero e proprio parametro
parassita perché si potrebbe in teoria calcolare mediante considerazioni costruttive e geometriche; esiste però un altro 

effetto di natura ohmica dovuta ai difetti del cristallo, che si manifestano in
eventuali percorsi preferenziali della corrente fotogenerata rispetto alla giunzione, dunque difetti che tendono
a bypassare la giunzione; si tengono
in conto con una resistenza di shunt messa in parallelo alla giunzione ($R_{sh}$).

La diminuzione della $R_{sh}$ non muove la corrente di cortocircuito ma riduce la $V_{oc}$; nella
realtà questa è una resistenza molto elevata; il suo effetto è quasi sempre trascurabile; ha un peso più alto
quanto più è piccola la corrente foto-generata; se questa corrente diventa piccola può essere confrontabile con 
quella drenata dalla resistenza shunt; se riduco di 10 volte la corrente foto-generata ho un peso 10 volte
maggiore della resistenza di shunt; se prima pesava 0,3\%, ora peserà per il 3\%.

In ogni caso una buona cella fotovoltaica deve avere una resistenza di shunt nell'ordine dei $k\Omega$.
Il modello circuitale completo:

<center>

![[cella_PV_completo.svg]]

</center>
 
La relazione caratteristica si modifica con un modello a 5 parametri:

$$
I = I_{ph} - I_0\left(e^{\frac{V_d}{nV_t}}-1\right) - \frac{V_d}{R_{sh}} = I_{ph} - I_0\left(e^{\frac{V+R_sI}{nV_t}}-1\right)- \frac{V+R_sI}{R_{sh}}
$$

# Pannello fotovoltaico
In commercio possono esistere pannelli costituiti da materiali differenti, questo per catturare più bande in frequenza e ridurre il fenomeno del mismatch; questo aumenta l'efficienza di conversione.
La tensione a vuoto tipica di una singola cella è di $0.5\sim0.7V$ con dimensioni di 10x10cm o 15x15cm, da cui si può estrarre un valore di corrente $I_{cc}$ di $5\sim 10A$.
È necessario disporre le celle in serie per aumentare la tensione fino ad un valore utile per applicazioni industriali, si dispongono poi in parallelo per aumentare la corrente.

Ogni singolo pannello (o modulo) è composto da celle disposte in serie fino a tensioni di 36V o 48V.
La potenza di taglia del pannello si riferisce al valore di picco in condizioni di massima irradianza (con 1 $\frac{W}{m^2}$).
Il limite imposto dalla legge è di 1000V.

Una serie di pannelli prende il nome di stringa, è una parte del campo fotovoltaico.
Il campo fotovoltaico è composto da stringhe, quindi sottocampi, disposti in serie e in parallelo.
Ogni sistema di generazione comprende l'insieme dei dispositivi fotovoltaici e dei dispositivi di conversione, oltre ai dispositivi di accumulo.
Un sistema fotovoltaico può essere grid-connected o stand alone.

Riassumendo dalla lezione precedente la corrente fotogenerata varia molto con l'irraggiamento ma non la tensione a vuoto, viceversa al variare della temperatura varia molto la tensione a vuoto e poco la corrente di corto circuito.
Ridurre la tensione a vuoto peggiora di molto però l'efficienza rispetto alla variazione di corrente di corto circuito, per questo caso in alcune applicazioni che richiedono particolare efficienza si può pensare di disporre di sistemi di raffreddamento.

Le potenze di picco vanno dai 2 ai 5 W per celle 10x10 e 15x15.
La caratteristica di un pannello, composto dalla serie di più celle, si ottiene aumentando la tensione a vuoto e mantenendo la corrente costante. $N$ saranno le celle in serie e $M$ quelle in parallelo.
Questo vale nell'ipotesi di tre celle perfettamente irradiate alla stessa maniera, è importante durante il posizionamento dell'impianto il **disegno delle ombre** si cerca di evitare se possibile di avere zone d'ombra anche su una parte dell'impianto.

Nel circuito reale si può approssimare la resistenza serie totale come la somma delle resistenze serie e analogamente per quelle shunt.
$$
I = I_{ph}-I_{0}\left(e^{\frac{V+R_{s,serie}I}{nNV_{t}}}-1\right) - \left( \frac{V+R_{s,serie}I}{R_{sh,serie}} \right)
$$
Se una delle celle è completamente ombreggiata, si troverà nel punto di funzionamento a vuoto, con tensione $V_{oc}$ e corrente nulla, ciò interromperebbe l'intera serie ma la corrente fotogenerata delle singole celle si richiude nella giunzione. Inoltre la cella in ombra vede ai suoi capi una tensione opposta pari alla somma delle tensioni a vuoto delle altre celle, si possono avere fenomeni di breakdown per serie numerose.

Per questo motivo si usano i diodi di by-pass, si usano solitamente per ogni sottomodulo, è difficile che vada in ombra una singola cella e non l'intero modulo.

Nella realtà in ogni caso la corrente si richiude nella resistenza di shunt della cella in ombra, che per la cella è un carico, dunque causa un surriscaldamento della cella.
Può essere usato come sistema di diagnostica, cercare degli hotspot permette di determinare celle in ombra oppure celle annerite, a causa ad esempio di residui o sporcizia.

Con il diodo di bypass si esclude la cella (o il modulo) in ombra, finchè la tensione ai capi delle celle illuminate è maggiore della tensione sul carico.
Per una tensione in uscita maggiore della somma delle tensioni delle celle illuminate, si ha una caratteristica corrispondente a quella di 1 cella parzialmente ombreggiata, senza diodo di bypass, ovvero la corrente in uscita sarà limitata dalla cella ombreggiata.

In caso di più celle o pannelli in ombra si formeranno più punti di massimo, serviranno strategie di controllo in grado di trovare il massimo assoluto, algoritmi chiamati MPPT, Maximum-Power-Point-Tracking.
Ciascun modulo è spesso suddiviso in due sottomoduli, ciascuno con il suo diodo di bypass.

## Stringa
Una stringa è per definizione una serie di pannelli, stringhe in parallelo costituiscono un sottocampo.

Il fenomeno di mismatch visto per le celle, è analogo per le stringhe, quando sono disposte in parallelo, in caso di ombreggiamento, si può avere un funzionamento nella regione di breakdown della stringa in ombra.

Si supponga di avere una stringa con 5 moduli ed una con 4, quella con 4 non può fornire la tensione di quella a 5.
La caratteristica complessiva, data dalla somma delle due caratteristiche fornirebbe una tensione ideale per la stringa da 5 ma una corrente negativa per quella da 4, ipoteticamente si avrebbe la tensione a vuoto dove prima era presente il punto di massimo.
Si deve ridurre la tensione su un nuovo punto di massimo, a potenza inferiore.

Per evitare che una stringa si comporti da carico rispetto alle altre si può disporre un diodo di blocco a valle di ogni stringa, si ottiene una caratteristica simile a quella di condizione di irraggiamento non uniforme.

# Producibilità dei pannelli fotovoltaici
Il livello di producibilità di un impianto varia con l'inclinazione e la sua posizione geografica.
La producibilità del pannello si calcola in funzione dell'irradianza standard, in tutte le situazioni differenti dal punto di producibilità massima hanno una producibilità inferiore, riducendo anche il tempo del ROI (Return of Investment), un tempo tipico è di circa 10 anni.
Altre condizioni che influenzano la producibilità si riferiscono alla radiazione diffusa, oltre a quella diretta.

Alcuni impianti fotovoltaici prevedono un sistema di inseguimento della traiettoria del Sole, sono solitamente sistemi molto costosi e previsti solo in particolari impianti.

## Angoli caratteristici dei pannelli fotovoltaici
L'angolo $\alpha$ rappresenta **l'altitudine solare**, ovvero l'angolo dei raggi rispetto al piano dell'orizzonte.
L'angolo di **zenit** invece $\theta_{z}$ è il suo complementare, ovvero l'angolo tra i raggi solari e l'asse perpendicolare al piano dell'orizzonte, ovvero lo zenit.
L'angolo $\beta$ è quello di **inclinazione del pannello** rispetto al piano dell'orizzonte.
L'angolo $\theta$ è **l'angolo di incidenza**, quello che effettivamente determina la producibilità del pannello, compreso tra i raggi solari e la normale del pannello, si cerca di minimizzare quest'angolo.

Il valore di irradianza diretta $P_{b0}$ è quella che si avrebbe se i raggi incidessero in maniera perpendicolare al pannello.
L'irradianza incidente sarà dunque:
$$
P_{b}=P_{b0}\cos \theta
$$
L'irradianza diretta incidente sul pannello orizzontale invece:
$$
P_{bh} = P_{b0}\sin \alpha
$$
e quindi si può esprimere l'irradianza in funzione di quella del pannello orizzontale:
$$
P_{b} = P_{bh} \frac{\cos \theta}{\sin\alpha} = P_{bh} \frac{\cos \theta}{\cos \theta_{z}}
$$
L'altezza solare $\alpha$ varia anche durante la stessa giornata.
Si definisce inoltre un altro angolo $\delta$ compreso tra il raggio solare e il piano equatoriale.
L'angolo $\delta$ varia tra -23.45° durante il solstizio d'estate e 23.45° durante il solstizio d'inverno; è nullo durante gli equinozi.
Un modo per stimare il valore di questo angolo, con $n$ il giorno dell'anno:
$$
\delta[°] = 23.45 \sin\left[ \frac{360}{365}\cdot(284+n) \right]
$$
dunque $\delta=0$ per $n=81$ il 22 Marzo o $\delta=\delta_{\text{max}}$ per $n=173$ il 22 Giugno.

Si definisce l'angolo di azimut del pannello quello compreso tra la normale del pannello e la direzione Sud e l'angolo azimut del sole $\gamma_{S}$ rispetto alla direzione Nord.

L'angolo di incidenza $\theta$ è così determinato:
$$
\begin{aligned}
\cos\theta&=(\sin\phi \sin\beta \cos \gamma+\cos \phi \cos\beta)\cos\delta \cos \omega+\\
&+\sin\delta(\cos\beta \sin \phi-\sin\beta \cos \phi \cos\gamma) + \\
&+\cos\delta \sin\omega \sin\gamma \sin\beta
\end{aligned}
$$
Il valore che più incide sulla scelta di inclinazione del pannello è quello della latitudine, è comunque un valore di compromesso.

# Convertitore elettrico fotovoltaico
Il sistema di conversione, in questo caso un inverter, è un dispositivo fondamentale del sistema di produzione fotovoltaico, la tensione in uscita dai pannelli è continua e si vuole collegare l'impianto alla rete di distribuzione in alternata.

L'inverter oltre a creare l'interfaccia di connessione alla rete alternata deve anche gestire la potenza attiva estratta dai pannelli, affinché lavorino nel punto di massima producibilità.
Deve inoltre garantire la power quality.

La configurazione base di un inverter grid connected è rappresentato da un impianto PV, un condensatore in ingresso, un inverter a ponte monofase e un collegamento alla rete monofase mediante un'induttanza di filtro.
L'induttanza agisce da filtro rispetto alla corrente ma ha un importante ruolo perchè la tensione in uscita dall'inverter è modulata e può variare tra Vd e 0 (unipolare) o Vd e -Vd, compreso lo 0 (bipolare).

La commutazione bipolare fornisce una frequenza di modulazione doppia rispetto alla unipolare.
L'induttore disaccoppia la tensione del pannello dalla tensione di rete, fornendo questa caduta di tensione permette proprio il funzionamento della struttura, regolando la corrente che attraversa l'induttore regolo proprio la potenza attiva fornita dal pannello, facendogli vedere inoltre uno specifico punto di lavoro.

L'induttore si comporta come un "volano energetico"
Per il calcolo della potenza si può considerare sinusoidale la tensione in uscita dall'inverter.

Il ruolo del condensatore è quello di gestire la **potenza fluttuante** a pulsazione doppia tra i pannelli e la rete:
$$
P_{\text{grid}}(t) = v_{\text{grid}}(t)\cdot i_{\text{grid}}(t)
$$
Si avrebbe una corrente unidirezionale nel pannello, con valor medio diverso da zero e a frequenza doppia.
In realtà è calcolata a tensione sul pannello costante ma al variare della corrente varierà anche la tensione del pannello per la sua caratteristica costitutiva.
Ci si sposterebbe sulla caratteristica del pannello fotovoltaico.

Il condensatore per filtrare la tensione dovrà assorbire questa corrente sinusoidale a pulsazione doppia.
Maggiore è la capacità del condensatore e minore sarà l'oscillazione di tensione e quindi l'oscillazione di corrente sul pannello.
L'oscillazione di corrente non sarà mai nulla.
Inoltre il condensatore deve assorbire la corrente dovuta all'apertura dei componenti, mediante i diodi di free-wheeling.

Per garantire una modulazione lineare la tensione ai capi del dc-link deve essere superiore di quella massima di rete.
Si usa solitamente un trasformatore per non ridurre la tensione necessaria al DC-Link.

La regione di lavoro del sistema
è determinata alle tensioni massime e minimi, la corrente massima del pannello, la potenza massima dell'inverter. La tensione $V_{dc}$ minima deve essere superiore al valore di picco della rete.

Il rendimento MPPT, l'unico che può essere pari ad 1, definito come la potenza fornita dal pannello rispetto alla potenza nel punto di massimo.
$$
\eta_{MPPT} = \frac{P_{pv}}{P_{MPP}}
$$
Il rendimento del convertitore, legato al convertitore appunto:
$$
\eta_{conv} = \frac{P_{ac}}{P_{dc}}
$$
Il rendimento globale:
$$
\eta = \eta_{{MPPT}}\cdot\eta_{{conv}} = \frac{P_{pv}}{P_{MPP}}\cdot \frac{P_{ac}}{P_{dc}}
$$
Non si tiene conto del rendimento del pannello, ovvero del rendimento di conversione della radiazione solare, la sorgente di energia non ha costi.

## Inseguimento del punto di massimo (MPPT)
Esistono molteplici algoritmi, esistono algoritmi di stima o algoritmi di inseguimento iterativo.
Quello di stima prevede appunto la stima del valore di tensione ottimale.

Mediante l'inverter regolo la potenza attiva erogata. L'algoritmo iterativo prende il nome di *perturba e osserva*
ovvero conoscendo la curva tipica a campana Potenza-Tensione di un pannello fotovoltaico, mi è sufficiente valutare la derivata della potenza rispetto alla tensione per capire in che direzione portare la tensione.
L'incremento del duty cycle causa un incremento della tensione e viceversa un decremento.

Questo algoritmo entra in crisi nel caso in cui ci siano punti di massimo locale, potrebbe bloccarsi su un massimo locale inferiore al massimo assoluto del pannello.
