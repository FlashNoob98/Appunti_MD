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


