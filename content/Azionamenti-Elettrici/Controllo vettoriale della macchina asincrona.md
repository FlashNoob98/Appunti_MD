Partendo dalle equazioni nel riferimento di statore:
$$
\begin{aligned}
\vec{\Phi}_{r}^s &= L_{m} \vec{i}_{s}^s + L_{r}' \vec{i}_{r}'^s\\
0 &= -\sigma_{r} L_{m} \vec{i}_{r}^s + (\sigma_{r}-j\omega_{r})\vec{\Phi}_{r}^s +\frac{d}{dt} \vec{\Phi}_{r}^s
\end{aligned}
$$
Si riporta il flusso di rotore con un certo angolo di ritardo $\Psi$, mentre il componente simmetrico $\vec{i}_{s}^s$ pari a:
$$
\vec{i}_{s}^s = \frac{2}{3}(i_{s_{1}}+i_{s_{2}}e^{j{2}\pi/3} + i_{s_{3}}e^{j 4\pi/3})
$$
con connessione a stella $i_{s_{3}}=-i_{s_{1}}-i_{s_{2}}$, sviluppando gli esponenti:
$$
\begin{aligned}
i_{sx}+ji_{sy} &= \frac{2}{3} \left[ i_{s_{1}}+i_{s_{2}}\left( -\frac{1}{2}+\frac{j\sqrt{ 3 }}{2} \right) + i_{s_{3}}\left( -\frac{1}{2} -\frac{j\sqrt{ 3 }}{2} \right) \right] = \\
&= \frac{2}{3}\left[ \left( \frac{3}{2}+\frac{j\sqrt{ 3 }}{2} \right)i_{s_{1}} + \frac{j\sqrt{ 3 }}{2}2i_{s_{2}} \right]
\end{aligned}
$$
dunque
$$
\begin{aligned}
i_{sx}& = i_{s_{1}} \\
i_{sy} &= \frac{\sqrt{ 3 }}{3}i_{s_{1}} + \frac{2\sqrt{ 3 }}{3}i_{s_{2}}
\end{aligned}
$$
prende il nome di trasformazione $2\to 3$, per la trasformazione inversa invece:
$$
\begin{aligned}
i_{s_{1}} &= i_{sx}\\
i_{s_{2}} &= \left( -\frac{\sqrt{ 3 }}{3} i_{sx} + i_{sy} \right) \frac{3}{2\sqrt{ 3 }} \\
i_{s_{3}}&= -i_{s_{1}} - i_{s_{2}}
\end{aligned}
$$
Queste equazioni sono ancora nel riferimento di statore.

Si esprime anche la coppia:
$$
T_{el} = -\frac{3}{2}pk_{r} \mathrm{Im}\left\{ \vec{\Phi}_{r}^s \vec{i}_{s}^s \right\}
$$
con $k_{r}=\frac{L_{m}}{L_{r}'}$ e $\sigma_{r}=\frac{R_{r}'}{L_{r}'}$.

Si effettua poi un cambio di riferimento, ponendo l'asse diretto sul flusso, chiamato $d$ e quello in quadratura $q$, proiettando le grandezze:
$$
\vec{\Phi}_{r} = \vec{\Phi}_{r}^se^{-j\Psi} = \Phi_{r}e^{j\Psi}e^{-j\Psi} = \Phi_{r}
$$
In questo riferimento il flusso ha solo parte reale che coincide con il suo modulo. Analogamente la corrente di statore:
$$
\vec{i}_{s} = \vec{i}_{s}^s
e^{-j\Psi}
$$
scomposto sui due assi:
$$
\vec{i}_{s} =i_{sd} + ji_{sq} = (i_{sx}+ji_{sy})e^{-j\Psi} = (i_{sx}+ji_{sy})(\cos\Psi - j \sin\Psi)
$$
Scomponendo i due termini:
$$
\begin{aligned}
i_{sd} &= i_{sx}\cos \Psi + i_{sy}\sin\Psi \\
i_{sq} &= i_{sy}\cos\Psi - i_{sx}\sin\Psi
\end{aligned}
$$
queste formule prendono il nome di passaggio $x,y\to d,q$.

Riassumendo le equazioni di rotore nel riferimento $d,q$:
$$
\left\{
\begin{aligned}
0 &= -\sigma_{r} L_{m}I_{sd} + \sigma_{r}\Phi_{r} - \frac{d}{dt}\Phi_{r} \\
0&= -\sigma_{r}L_{m}i_{sq} + (\omega-\omega_{r})\Phi_{r} \\
T_{el} &= \frac{3}{2} pk_{r}\Phi_{r} i_{sq}
\end{aligned}
\right.
$$
con $\omega=\frac{d}{dt}\Phi$.
Questo riferimento permette di disaccoppiare le due componenti per controllare rispettivamente il flusso e la coppia.
Questo permette di semplificare il controllo della macchina.

L'idea di prendere il riferimento sul flusso deriva dalla macchina in corrente continua dove il riferimento è preso sul polo magnetico, ovvero sul flusso di statore.
Nel sincrono analogamente l'eccitazione è sul rotore e il riferimento si prende sul rotore, sul suo asse polare.

In questo caso la differenza è che il flusso non è solidale a nessuno dei due elementi di macchina, ci si sta "sincronizzando" su qualcosa che non esiste fisicamente, ci si pone il problema di ricavare $\Psi$.

Il numero di incognite supera di uno il numero di equazioni, il problema ancora non è definito, esisterebbero infinite soluzioni, per questo motivo si sceglie una condizione ausiliaria, ad esempio minimizzare la corrente a parità di coppia, ciò sarà possibile se il flusso sarà posto al suo valore massimo, alle soglie della saturazione magnetica, dunque $\Phi_{r}=\Phi_{r_{\text{nom}}}$ o più in generale $\Phi_{r}=\text{cost}$.

In questa condizione, la prima equazione perde il termine differenziale, dunque la prima equazione diviene:
$$
\Phi_{r} = L_{m}i_{sd}
$$

Per controllare la macchina asincrona sarà necessario un convertitore, lo si assume ideale, in uscita vi saranno tre correnti $i_{s_{1}},i_{s_{2}},i_{s_{3}}$ che alimenteranno il motore.
Si decide di fare un controllo di coppia, è un classico controllo che si sceglie di usare solitamente sulle macchine elettriche (o meno).

# Controllo in coppia
Le grandezze di riferimento saranno la coppia desiderata e il flusso di riferimento.
Dal flusso di riferimento divido per $L_m$ e ottengo il riferimento della corrente di asse diretto $i_{sd}^*$.
Con il riferimento di coppia divido per $\frac{3}{2}pk_{r}\Phi_{r}^*$ e ottengo il riferimento di corrente in quadratura $i_{sq}^*$.

Queste due correnti finiscono in un blocco di conversione $d,q\to x,y$ ottenendo i riferimenti rispetto allo statore del componente simmetrico. Devo ottenere le tre componenti delle correnti mediante il blocco di conversione $x,y\to 1,2,3$ ottenendo i riferimenti dei tre componenti di corrente $i_{s_{1}}^*,i_{s_{2}}^*,i_{s_{3}}^*$, questi tre valori serviranno infine al controllo del convertitore.

Per svolgere il cambio $d,q\to x,y$ è necessario conoscere $\Psi$, ovvero la posizione del flusso, per determinare tale posizione furono svolti diversi tentativi, il primo fu di inserire una sonda ad effetto Hall su uno dei denti della macchina, appositamente lavorato per accogliere tale sonda senza alterare le dimensioni del traferro.
Il flusso che attraversa tale sonda genera una tensione ai capi della sonda, costante o meno nel tempo, dunque ad ogni valore del flusso coincide una condizione ridotta.
Ciò implica costruire motori appositamente per essere controllati, in realtà misurare il flusso con tali sonde forniva dei risultati completamente alterati.

In alternativa usando delle spire si può ricavare la tensione indotta dal flusso, integrando tale risultato si può ricavare il flusso.
Anche questa soluzione richiedeva la costruzione di un motore apposito per fornire tale risultato, anche in questo caso erano presenti numerose irregolarità nella misura a causa di fenomeni locali.
Le matasse potevano essere disposte alla base delle cave per ridurre gli errori di misura.

In alternativa si pensò di inserire delle sonde amperometriche sulla testata della macchina, ovvero sulla parte esterna degli avvolgimenti.

I giapponesi trovarono la soluzione:

si definisce $\omega_{\sigma} = \omega-\omega_{r}$ e la seconda equazione (quella in quadratura) del rotore diventa:
$$
0 = -\sigma_{r}L_{m}i_{sq} + \omega_{\sigma}\Phi_{r}
$$
e dunque
$$
\omega_{\sigma} = \frac{\sigma_{r}L_{m}i_{sq}}{\Phi_{r}}
$$
Nello schema di controllo si possono usare $i_{sq}^*$ e $\Phi_{r}^*$ di riferimento per calcolare $\omega_{\sigma}^*$, si somma il valore di $\omega_{r}$ misurato mediante un trasduttore di velocità sull'albero della macchina, il risultato è proprio $\omega$
pari alla derivata di $\Psi$, dunque integrando questo valore si ottiene il valore di $\Psi$, ovvero la posizione del flusso, calcolata a partire dai riferimenti e dalla velocità del rotore, prende il nome di metodo indiretto.
L'integrazione determina però degli errori che si cumulano, il valore di $\Psi$ deriva e ciò causerebbe un errore nella trasformazione $d,q\to x,y$.

In realtà il controllo delle macchine era spesso eseguito imponendo una velocità di riferimento, questa viene confrontata con la velocità misurata e l'errore inviato in un PI, si ottiene la coppia di riferimento da inviare al controllore di coppia.
La coppia desiderata non è più una grandezza costante ma varia al variare dell'errore di velocità, ciò implica che se anche ci fosse un errore sulla stima di $\Psi$, si avrebbe una correzione automatica mediante una variazione di coppia di riferimento, dovuta al controllore di velocità retroazionato.

Il convertitore non è ideale, dunque sarà necessario un regolatore di corrente, retroazionato con le correnti di linea che fornisca gli impulsi di comando del convertitore.

Questo controllo si chiama metodo indiretto feed-forward, indiretto per il modo in cui viene calcolato l'angolo $\Psi$.
Feed-forward perché non è presente retroazione su $\omega_{\sigma}$.

Il flusso di riferimento può essere calcolato da un blocco che lo limiti al flusso nominale alla velocità nominale e porti poi la macchina in deflussaggio per velocità della macchina maggiori di quella nominale.
Dunque anche il valore di $\Phi_{r}^*$ sarà variabile.


Si potrebbe in teoria usare il modello della macchina per convertire dei riferimenti in corrente in riferimenti in tensione, non si ha però il disaccoppiamento tra la componente di asse diretto e quello in quadratura e andrebbero dunque corretti, per questo motivo conviene quasi sempre usare i regolatori di corrente per pilotare l'inverter anziché calcolare le tensioni.

Analogamente si è provato a riportare il flusso allo statore ma si è visto che non si semplificava il modello.

Ricavata la tensione diretta, in uscita dal regolatore di corrente, si deve trovare una strategia di controllo per pilotare l'inverter, la strategia più utilizzata è quella di scegliere i due vettori che delimitano la regione che contiene il vettore di tensione nell'intervallo $\Delta t$ di calcolo, insieme al vettore nullo.
Si divide dunque $\Delta t$ in tre intervalli in cui si applicano i tre vettori, tali che la loro somma sia comunque $\Delta t$.
$$
\alpha\Delta t + \beta\Delta t + \gamma\Delta t = \Delta t \Rightarrow \alpha + \beta + \gamma = 1
$$
Vi sono due gradi di libertà fissato l'intervallo $\Delta t$.
$$
\begin{aligned}
\alpha\Delta t &= \vec{v}_{1}\\
\beta\Delta t &= \vec{v}_{2} \\
\gamma\Delta t &= \vec{0}
\end{aligned}
$$

Valore medio della tensione:
$$
\frac{1}{\Delta T}\int_{0}^{\Delta t} \vec{v}^* dt = \frac{1}{\Delta t} \left[ \int_{0}^{\alpha\Delta t} \vec{v}_{1}dt +  \int_{\alpha\Delta t}^{(\alpha+\beta)\Delta t} \vec{v}_{2}dt  + \int_{(\alpha+\beta)\Delta t}^{\Delta t} \vec{0}dt \right]
$$
E dunque ottenere:
$$
\vec{v}^*\Delta t =\vec{v}_{1}\alpha\Delta t + \vec{v}_{2}\beta\Delta t
$$
che nel riferimento $x-y$ diventa:
$$
\begin{aligned}
V_{x}^* &= \alpha v_{1x} + \beta v_{2x} \\
V_{y}^* &= \alpha v_{1y} + \beta v_{2y}
\end{aligned}
$$
Si può dividere il periodo $\Delta t$ in quattro semi periodi, suddividere il tempo $\gamma$ in due sotto intervalli a monte e a valle di $\alpha$ e $\beta$, però nell'intervallo $\Delta t$ successivo avrei una commutazione inutile passando da 111 a 000. Per ovviare a questo problema si divide l'intervallo in sette parti:
$$
\left|\frac{\gamma}{4}\right| \left. \frac{\alpha}{2} \right|\left. \frac{\beta}{2} \right| \frac{\gamma}{2}\left| \frac{\beta}{2}\right.\left| \frac{\alpha}{2} \right.\left|\frac{\gamma}{4}\right|
$$
ottenuto con:
$$
000 - 100 - 110 - 111 - 110 - 100 - 000
$$
inizia e termina con la stessa combinazione, ogni fase commuta una sola volta nell'intervallo dunque $\Delta t$ diventa proprio la frequenza di commutazione del convertitore.
La tensione risultante giace all'interno dell'esagono ottenuto dai 6 vettori dell'inverter.
Se si desidera una tensione maggiore, si finisce in sovramodulazione.

## Inverter multilivello
Con l'aumentare delle tensioni di alimentazione delle macchine, è necessario fornire tensioni più elevate, ciò pone un limite tecnologico sull'isolamento dei componenti, per questo motivo si realizzano degli inverter *multilivello* che abbiano più stadi per ogni gamba, e non più solo due, ottenendo anche i vettori intermedi.

## Modello predittivo
A partire dall'equazione di statore si può supporre di integrare l'equazione di corrente in un $\Delta t$ piccolo nel limite del sistema, si calcola poi la coppia che si otterrebbe applicando $v_{1}$, la coppia per $v_{2}$ e così via per le 7 coppie ottenibili, si sceglie infine il vettore che minimizza l'errore con la coppia di riferimento.. sono necessari processori molto veloci per eseguire un calcolo simile.

Mediante un sistema detto *osservatore* posso eseguire l'identificazione dei parametri con precisione, osservando i valori di tensione e corrente della macchina.
