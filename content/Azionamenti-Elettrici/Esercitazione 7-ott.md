Si vuole controllare un half bridge con una tensione in ingresso $V_{dc}$ da $500V$ su un carico attivo $RLE$, si vuole controllare la corrente $i$ in ingresso al carico.
Le equazioni del sistema sono sempre del tipo:
$$
v = Ri + L\frac{d}{dt}i + E
$$
Dal modello ideale dell'half bridge, con $s$ la variabile di controllo discreta, la tensione in uscita è:
$$
v = sV_{dc}
$$
Se si conosce il modello della macchina ed eventualmente la tensione indotta $E$, questa può essere compensata nel controllore, in alternativa si dovrebbe settare il controllore in maniera "sufficientemente robusta" rispetto ai disturbi esterni.

Si può sfruttare il blocco Zero-Order Hold per "digitalizzare" il segnale di controllo da inviare poi alla PWM.

Usando il blocco trigger-port si può scegliere di eseguire un blocco ad un certo segnale, ad esempio il fronte di salita del segnale di clock.
Si ha un blocco a tempo discreto, non ancora digitale perché manca la quantizzazione.
In questo caso cambia il tipo di integratore, che diventa nel dominio Z, è possibile anche scegliere il tipo di integrazione.
Sample time a -1 per utilizzare il tempo di controllo del trigger.
Il saturatore limita il duty cycle tra 0 e 1.

Si aggiunge uno "unit delay" per inserire il ritardo reale del controllore digitale, la ritarda in questo caso di Tc, un sample time.
