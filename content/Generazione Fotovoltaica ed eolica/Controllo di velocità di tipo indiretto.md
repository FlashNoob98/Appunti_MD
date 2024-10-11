Ipotesi semplificativa: si trascura il convertitore e si suppone di imporre direttamente le correnti di rotore.

Supponendo di conoscere il valore della coppia, posso ricavare $i_{sd}$ e $i_{sq}$, ovvero conoscere la velocità e sfruttare l'equazione di d'Alembert.
È importante saturare i valori di controllo per non superare i valori di sovraccarico, spesso il limite di corrente e tensione ad esempio è quello dell'inverter, può essere sovraccaricato meno della macchina elettrica.
L'inerzia termica della macchina è molto più elevata mentre i componenti elettronici sono più piccoli e subiscono di più degli stress termici.

Analogamente il valore di coppia avrà una saturazione, positiva e negativa, leggermente superiore alla coppia massima.
Dalla terza equazione ricavo la $\omega_r$ che è in realtà quella desiderata, successivamente dovrò effettuare una nuova trasformazione da sistema rotante a fisso, sempre conoscendo la fase del flusso di motore.
A partire dalla conoscenza del componente simmetrico, nel riferimento stazionario, devo poi ricavare le tre correnti.
Si impone il principio di Kirchoof in cui la somma delle tre correnti è nulla e la definizione del componente simmetrico.

# Algoritmo di controllo in retroazione
Misurata la corrente nella macchina, questa può essere inserita in retroazione e sottratta alla corrente di riferimento, l'errore viene poi inviato ad un regolatore "PI".
In alternativa si può usare un regolatore ad isteresi anziché un PI.
Le bande dovrebbero avere un errore relativo costante, dunque variare al variare della grandezza imposta.
Il limite del PI è che le grandezze di riferimento sono sinusoidi e non continue.

Si potrebbe anche fare una regolazione di corrente nel riferimento rotante e poi calcolare le parti reali. È più semplice il controllo in questo caso, in tal caso però il segnale di retroazione deve essere anch'esso riportato nel riferimento rotante.

Continuando con il controllo in PWM si pone a monte del regolatore del VSR un blocco di conversione da componente simmetrico a valori trifase e ancora a monte il blocco di calcolo dal riferimento rotante a quello fisso, in ingresso a quest'ultimo va inserito il valore della fase $\hat{\Psi}_{r}^s$, il cappello indica che è una grandezza stimata.

A monte è presente l'algoritmo di controllo che a seconda della strategia e del punto di funzionamento della macchina impone il flusso pari a quello nominale (o in deflussaggio per velocità maggiori), dunque il flusso di riferimento e la coppia di riferimento sono ricavati dal blocco di controllo di velocità, è quella che vogliamo imporre, dunque un PI con saturatore impone la coppia a partire dalla differenza di velocità tra il riferimento e quella velocità.

Il regolatore di flusso invece ha in ingresso la velocità misurata, rispetto alla nominale e determina la regione di controllo se a flusso costante o flusso decrescente per $\omega>\omega_{n}$ ovvero la condizione ausiliaria del modello.

A partire dall'encoder incrementale di posizione si ricava la velocità $\omega_{r}$, ricavo poi la $\omega_{\sigma}$ necessaria al calcolo della fase $\Psi_{r}^s$ mediante un integratore.

In realtà si utilizza il modello della macchina per realizzare un osservatore, potrei realizzare un modello più robusto inserendo regolatori di coppia e flusso a partire da valori *osservati*.

