La sicurezza elettrica è fondamentale nella stesura di un progetto, il concetto stesso di sicurezza guida la progettazione di un impianto elettrico, soprattutto quando c'è l'interazione tra gli apparecchi elettrici e l'uomo, per questo motivo si pone particolare accento per la sicurezza degli impianti in BT.

Il termine sicurezza proviene dal concetto di proteggere l'uomo dai malfunzionamenti dei componenti, essi dipendono dall'affidabilità dei componenti.

L'introduzione della sicurezza è posta nell'articolo 32 della costituzione italiana in cui si definisce l'Italia come una Repubblica garante della sicurezza e dell'incolumità delle persone, a valle di quest'ultimo sono posti numerosi articoli che fanno riferimento alla sicurezza in ambito lavorativo.

Si parla di sicurezza anche in termini di risarcimenti del danno, quindi sono presenti riferimenti al codice civile e penale.
Va citato il **testo unico sulla sicurezza** ovvero decreto legislativo 88 che fa riferimento alla

Legge 136 del 1968 introduce all'articolo 1 la regola dell'arte, un impianto o un progetto deve essere realizzato secondo la regola dell'arte e il progettista deve rilasciare un attestato che attesti appunto che l'impianto rispetti tale caratteristica

Il CEI è il normatore delle regole per definire la realizzazione di un impianto a regola d'arte, il CEI non definisce le leggi ma definisce lo stato dell'arte.
Se un impianto è realizzato secondo le norme CEI può essere definito a regola d'arte e rispondente alle leggi.

Non deve esistere un limite al miglioramento tecnologico, un impianto non deve per forza rispettare le norme CEI a patto che si riesca a dimostrare di aver raggiunto un livello di sicurezza superiore, è legato al principio di sviluppo tecnologico, non si deve impedire la messa in atto di misure superiore alle norme CEI.

Il comitato elettrotecnico italiano nacque come ente normatore e comitato di enti che lavoravano nell'ambito elettrico come ENEL, per garantire la sicurezza.

Con l'IMQ, Istituto Marchio di Qualità, fornisce la marchiatura di qualità agli apparecchi e agli impianti, si parla sempre di enti italiani.
Il marchio IMQ garantisce l'approvazione del costruttore, l'approvazione del prototipo e il controllo della produzione.

L'approvazione del costruttore implica che il costruttore abbia predisposto un impianto di  produzione approvato dell'IMQ.
L'approvazione del prototipo implica che l'IMQ abbia approvato un prototipo e ne garantisca le prestazioni in termini di sicurezza.
Il controllo di produzione 'IMQ' prevede dei controlli periodici sul processo di produzione del prodotto lungo tutta la catena di montaggio.

In riferimento ai marchi di qualità, con la comunità Europea è nata l'esigenza di garantire il funzionamento di prodotti in tutta Europa, il CENELEC, ente europeo è disposto a fornire le normative per abbattere le barriere commerciali e fornire le caratteristiche dei prodotti europei.

Direttiva 35 2014 riguarda le apparecchiature in Bassa Tensione ed è una delle più importanti perchè garantiscono la sicurezza degli utenti finali e del personale non esperto.

Questi concetti si applicano all'ambito elettrico ma sono applicabili in ogni ambiente lavorativo, anche un'operazione di manutenzione è sottoposta a specifiche procedure in accordo con i criteri di sicurezza.

# Curve di pericolosità
Sono curve $V/\text{tempo}$, il sistema funziona a  tensione impressa, la protezione si garantisce limitando la tensione a cui una persona viene a contatto.

La pericolosità della corrente sul corpo umano è in realtà legata agli effetti della corrente e dalla sua persistenza nel corpo umano, quindi si studiano anche le **curve di pericolosità** del tipo $i/\text{tempo}$, indicano la pericolosità della corrente all'interno del corpo umano.

Si trasformano poi le curve di pericolosità in curve di sicurezza, tra le due è presente la resistenza offerta dal corpo umano.

Gli effetti sull'uomo dovuti alla presenza di una corrente nel corpo umano possono essere la scossa e lo shock:
- La scossa si identifica con la percezione della corrente nel corpo, non causa effetti permanenti
- Lo shock ha degli effetti, eventualmente permanenti
<center>

![[curva_sicurezza_elettrica_BT_no_BG.png]]

</center>

Esiste una prima soglia (1) pari a $0.5mA$ per la quale non c'è percezione della corrente, è chiamata appunto **soglia di percezione**. 

Successivamente una regione (2) in cui non ci sono effetti permanenti sul corpo umano ma la corrente inizia a sovrapporsi con la normale attività elettrica del sistema nervoso; sono presenti  andamenti decrescenti $t/A$ da 50 a 200$mA$, (3) la curva limite è chiamata **curva di tetanizzazione**, indica il limite in cui inizia l'irrigidimento dei muscoli. Fin quando persiste la corrente non si riesce a controllare la reazione del corpo.

La regione superiore (4) è invece la curva di **fibrillazione** (ventricolare) oltre la quale la corrente interagisce con il muscolo cardiaco, si può avere **l'arresto respiratorio** fino ad arrivare all'**arresto cardiaco**, con il passare del tempo anche ustioni.

È importante sapere come intervenire in caso di shock elettrico, come effettuare un massaggio cardiaco e l'utilizzo di un defibrillatore.

Nella regione di fibrillazione sono in realtà indicate tre curve $C_1$, $C_2$ e $C_3$, la curva $C_1$ si riferisce ad un percorso specifico della corrente nel corpo, mentre $C_2$ e $C_3$ si riferiscono al 5% e al 50% degli eventi che causano fibrillazione. Ci si riferisce sempre a considerazioni statistiche in quanto gli effetti della corrente, a pari tensione dipende dal singolo individuo.

La scienza che studia il comportamento del corpo umano sottoposto ad una sollecitazione elettrica esterna prende il nome di **elettrofisiologia**.

Lo scopo della sicurezza elettrica è garantire che la scossa non diventi shock, e non causi danni irreversibili, dunque la curva di tetanizzazione è il limite superiore ammissibile, la soglia ideale sarebbe quella di $0.5mA$ ma sarebbero necessari interruttori differenziali molto sensibili e costosi ma si confonderebbero in ogni caso i guasti con le normali correnti di dispersione, per questo motivo ci si pone verso destra sul grafico accettando un certo rischio, assicurandosi però che i rischi sul corpo umano non siano permanenti.

# Definizione del rischio
Il *rischio* si definisce in maniera accoppiata ad un evento e alla probabilità che avvenga un evento, in questo caso il guasto e il contatto con una parte in tensione, all'evento va moltiplicato il danno, per questo motivo se il danno è reversibile, il rischio è accettabile, pesato per la probabilità che il guasto avvenga.

In BT si ipotizza il rischio con probabilità unitaria, mentre in MT e AT la sicurezza diventa troppo costosa se si usasse questo approccio, per questo motivo si considera la probabilità del guasto per calcolare il rischio.
Ad esempio non sempre si usano sistemi di protezione da fulminazione in AT se la probabilità che questa avvenga sia bassa.

La curva $C_1$ si riferisce al percorso di corrente mani-piedi nel corpo umano che può portare alla fibrillazione ventricolare.
Si ha una distribuzione di probabilità di fibrillazione ventricolare, si considera il valore corrispondente ad una probabilità del 5%, questo corrisponde alla curva $C_2$.
Si definisce il valore di corrente per il quale il 50% dei campioni ha avuto fibrillazione ventricolare con la curva $C_3$.

La curva $C_1$ è dunque inferiore al 5% e viene utilizzata per il dimensionamento dell'impianto.

# Curve di sicurezza
Per passare alle curve di sicurezza, a partire da quelle di pericolosità, va utilizzata una resistenza elettrica, quella del corpo umano.

Dal punto di contatto è posta una resistenza della pelle con in parallelo una capacità, in serie la resistenza del corpo e successivamente l'impedenza del secondo punto di contatto.

Le resistenze di contatto $R_p$ vengono però trascurate rispetto alla resistenza interna, quest'ultima dipende dal percorso della corrente nel corpo umano, per questo motivo lo si schematizza secondo gli arti: due gambe e due braccia, associate a quattro resistenze identiche.

In caso di contatto tra due piedi si ha una resistenza totale di 2R, analogamente al contatto tra due mani ma il secondo interessa il cuore e per questo motivo più pericoloso.
Il caso più frequente è invece mano e due piedi: $R_{B}=R+\frac{R}{2}$ mentre il caso più pericoloso è due mani e due piedi, la resistenza complessiva è dunque $R_{B}=\frac{R}{2}+\frac{R}{2}=R$.

Anche il valore della $R$ è calcolato in maniera statistica, esiste una densità di probabilità della resistenza, si considera il valore di resistenza pari al 5%, ovvero si considera che il danno può colpire al 5% una persona che abbia un valore di resistenza più basso.

Il valore di resistenza del corpo umano in realtà dipende anche dalla tensione, un ulteriore considerazione da fare è la tipologia di collegamento a terra, si considera solitamente una sezione circolare con una resistività pari a quella del terreno, si assume un valore di $1000\Omega$ per le condizioni ordinarie e $200\Omega$ per le condizioni particolari come ambienti umidi, piscine, sale operatorie ecc...

I valori di tensione da utilizzare per determinare la resistenza del corpo sono:
$$
\begin{aligned}
\text{tensione} &\quad R_{B} & R_{EB} \\
& & 1000\Omega \quad 200\Omega \\
25V &\rightarrow 875\Omega & 13mA\quad  23 mA \\
50V & \rightarrow 725\Omega & 29mA \quad 54mA \\
75V & \rightarrow 625\Omega \\
\vdots \\
1000V & \rightarrow 350\Omega
\end{aligned}
$$
Ad esempio in condizioni ordinarie $I^* = \frac{25}{1875} = 13mA$, si ha un tempo superiore ai 10 secondi.
Aumentando la tensione a $50V$ in condizioni ordinarie:
$$
I^* = \frac{50}{1725} = 29mA
$$
Il tempo di intervento diminuisce all'aumentare della tensione e al diminuire della resistenza.

Si vuole infine costruire la curva di sicurezza $t/V$, sulla soglia di $50V$ si ha un asintoto verticale per tempi superiori a $5s$, segue poi un andamento simile a quello della curva $C_1$.

<center>

![[curva_sicurezza_elettrica_BT_tensione_tempo.png]]

</center>

Le curve di pericolosità e sicurezza sono considerazioni fatte in BT perché gli utenti non sono esperti.
In caso di ambienti speciali in MT, accessibili solo a personale autorizzato e qualificato, si possono utilizzare le curve più a destra e si considera il valore del 50% per i valori di resistenza, il tempo limite non è più 5 secondi ma 10 e la tensione asintotica riportata nella curva di sicurezza diventa $80V$ e non più $50$.
