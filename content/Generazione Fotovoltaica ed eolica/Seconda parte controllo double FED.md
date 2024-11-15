Passaggi essenziali della volta precedente: si è ricavato il modello matematico del double fed induction generator.
Sulle slide sono presenti piccole variazioni di notazione, si trovano anche gli schemi, si realizza oggi uno schema nuovo ma simile a quanto già presente sulle slide.

L'ultima volta si era rappresentato il modello nel riferimento d-q solidale al flusso di statore e si sono riscritte le equazioni di statore e di rotore nel nuovo sistema di riferimento, siamo arrivati al suddetto sistema di equazioni (rivedi altra lezione)

Le variaibli di stato sono le correnti rotoriche nel riferimento dq i_rd e i_rq, flusso di statore secondo l'asse diretto
I forzamenti sono Vsd e vsq, Vrd e Vrq.
L'espressione della coppia è 
$$
\frac{3}{2} \frac{pL_{m}}{L_{s}}\Phi_{sq}i_{sq}
$$
L'ultima volta dicemmo che guarando la prima equazione (Vsd) dipende dalla componente di corrente secondo l'asse diretto, Ciò ci permette di affermare che se si vuole mantenere il fkusso $phisd$ costante, è necessario usare l'equazione (qiella rossa) che governa il flusso e la corrente $i_{rd}$ deve essere pari a phisd/lm - Lsd/...
Se ird è pari a zero si ottiene il flusso pari al ??????
Essendo una macchina in cuo lo statore è alimentato a frequenza fissa, le componenti di flusso di statore sono a frequenza fissa, dunque si ottiene un flusso fpi sd anche con corrente ird = 0
A regime l'equazione fornisce un valore di flussso anche con ird = 0.

I_rd= 0 si può garantire che il flusso non cambi, se volessi cambiare il valore del flusso e mantenerlo costante dovrei dare un valore di ird diverso da zero dato che Vrd è vincolato dalla rete, la parte statorica è collegata direttamente alla tensione direte.

Si rappresenta tramite queste equazioni lo schema a blocchi, si prova a costruirlo: (vedi xournal)
Come ragionare per costurire lo schema ablocchi? si vedono le equaizoni necessarie da implementare, in teoria ci servono tutte le quaizioni, dobbiamo ccapire quali possono essere utili alla stima della fase del flusso di statore e quali sono utili a imporre i valori di coppia e vellocità, stiamo ancora eseguendo un controllo di velocità assoggettata alla richiesta dalla turbina a monte.

Così come svolto nel FOC, il valore di riferimento di velocità provoiene dalla carattteristica della turbina che lega la velocità della turbina alla velocità del vento massimizzando la potenza di generazione (?)
(Inserisci curva potenza meccanica velocità)

Partendo dall'anello più esterno di velocità, cosa si ottiene in uscita  dal regolatore di velcoità? Si ottiene in uscita dal regolatore la coppia di riferimento e quindi i_rq (come si vede dall'espressione della coppia), avendo imposto il flusso phi_sd costante.


## Analisi sperimentale del controllo vettoriale sul DFIG
Si vede sperimentalmente l'andamento nel tempo della velocità del rotore e delle correnti di asse diretto e in quadratura.
Mantenendo la corrente di asse diretto pari a zero, si mantiene il flusso costante, varia la componente in quadratura, che modificherà la coppia elettrica resistente, all'aumentare della velocità del vento va aumentata la coppia della macchina e dunque la corrente in quadratura.
Sarà il regolatore di velocità a fornire il valore di coppia resistente della macchina.

In questo caso il regolatore di velocità non interviene istantaneamente all'aumentare della velocità richiesta dalla turbina, questo per permettere un'accelerazione rapida del sistema, non fornisce istantaneamente la corrente in quadratura diversa da zero, quest'ultima crescerà solo raggiunta la velocità di riferimento, in cui la macchina elettrica inizierà a fornire la nuova coppia richiesta per mantenere costante la nuova velocità raggiunta.

Analogamente durante la decelerazione della macchina, ci sarà un aumento di corrente in quadratura per aumentare la coppia resistente e rallentare il sistema.

In ogni caso la potenza massima estraibile dalla turbina è saturata dalla potenza nominale della macchina, non si prende più il punto di massima potenza della turbina, mi porto ad una velocità inferiore rispetto a quella di potenza massima estraibile dalla turbina.

Al rotore sono collegati dunque due convertitori, il primo regola la velocità, il secondo la potenza trasferita alla rete, per questo secondo convertitore si usano i riferimenti fissi di statore, dobbiamo fornire energia alla rete. La regolazione di potenza attiva è garantita mantenendo costante la tensione sul DC-Link, se questa resta costante allora tutta la potenza trasferita viene iniettata in rete.
Controllare la tensione del DC-Link implica controllare la corrente di asse diretto nel riferimento di statore, ovvero la tensione di rete.
L'inverter deve essere **sincronizzato** con la tensione di rete, ovvero conoscere la fase della tensione di rete rispetto al riferimento dell'inverter.
Le potenze trasferite sono:
$$
\begin{aligned}
P &= 3(v_{d}i_{d}+v_{q}i_{q})\\
Q &= 3(v_{d}i_{q}+v_{q}i_{d})
\end{aligned}
$$
Il riferimento di tensione sul DC-Link $E^*$ serve al funzionamento dell'inverter mentre la corrente $i_{q}$ e quindi la potenza reattiva erogata può essere richiesta o meno dalla rete.
I riferimenti di tensione e corrente sulla rete sono presi a valle delle induttanze di filtro poste in uscita all'inverter.
