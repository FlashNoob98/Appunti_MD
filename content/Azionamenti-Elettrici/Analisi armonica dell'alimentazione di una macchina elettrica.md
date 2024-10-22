Una macchina elettrica in [[Motori in corrente continua|corrente continua]] può essere alimentata da un [[sistemi di regolazione dei motori|convertitore]], esso fornisce in uscita una tensione che non è quasi mai costante ma presenta un contenuto armonico, utilizzando lo sviluppo in serie di Fourier della tensione si può analizzare il circuito per ogni armonica $k$ supponendo la linearità del sistema.
Di conseguenza anche le correnti nella macchina avranno un contenuto armonico del tipo:
$$
I_{k} = \frac{V_{k}}{Z_{k}} = \frac{V_{k}}{\sqrt{ R_{a}^2 + \omega^2L_{a}^2k^2 }} = \frac{V_{k}}{R_{a}\sqrt{ 1+k^2\omega^2\tau_{a}^2 }}
$$
con $\tau_{a}=\frac{L_{a}}{R_{a}}$ la costante di tempo di armatura.

Si definisce il **fattore di ondulazione della corrente**:
$$
\xi_{i} = \frac{1}{I_{d}}\sqrt{ \sum_{k=1}^{\infty} I_{rms,k}^2 } = \frac{1}{I_{d}}\sqrt{ I_{rms}^2-I_{d}^2 } = \sqrt{ F^2 -1}
$$
Si suppone di analizzare solo la prima armonica di corrente, si riporta il calcolo del fattore di ondulazione in funzione della tensione.
$$
\xi_{i} = \frac{V_{1}}{I_{d}R_{a}\sqrt{ 1+\omega^2\tau_{a}^2 }}
$$
Dunque il fattore di ondulazione varia con l'angolo di innesco dei convertitori $\alpha$ ma vale anche il valore medio di tensione e dunque di velocità della macchina.

Si vuole confrontare le prestazioni dei diversi convertitori, dunque si ipotizza che la macchina lavori sempre a coppia e quindi corrente nominale.
Si suppone che la tensione indotta sia il 90% della nominale, e la caduta nominale sia $\Delta_{n}$:
$$
R_{a}I_{a,n} = \frac{\Delta_{n}}{V_{a,n}}V_{a,n}
$$
Se si definisse un fattore di oscillazione per la tensione, si avrebbe un'ondulazione pari anche a 4 o 6 volte per tensioni molto più basse della nominale, ciò però ha anche un effetto minore sulla corrente che sarà in ogni caso meno ondulata.
Il fattore di ondulazione della corrente infatti diminuisce all'aumentare della costante di tempo $\tau_{a}$.
