Nel sistema IT il neutro è isolato, le masse sono collegate a terra mediante una propria resistenza $R_E$ dell'impianto di terra.
È caratterizzato da correnti di dispersione piccolissime, si richiudono solo mediante le capacità delle linee a terra.
Viene utilizzato in alcuni impianti ospedalieri dove è necessario garantire continuità di servizio, è legato alla non necessità di interrompere la corrente in caso di guasto.
Lo svantaggio principale sono le sovratensioni dovute agli eventuali guasti, in caso di guasto di una fase a terra, si ha lo spostamento del centro stella e le altre fasi offriranno una tensione verso terra pari alla concatenata, si incrementa la tensione di oltre il 70%.

Gli utilizzatori e i cavi dovranno avere isolamenti opportunamente dimensionati, con una tensione di isolamento superiore alla concatenata.
Le correnti di guasto sono piccole, non richiudendosi mediante il terreno ma solo mediante le capacità parassite.

Le correnti di guasto valgono: $0.4A/1000\ kVA$ dunque dipendono dai carichi. Ancora una volta la condizione di sicurezza:
$$
I_{g}R_{E} \leq U_{L}
$$
Essendo la $I_g$ piccola si possono avere anche valori di $R_E$ elevati.
La capacità dei cavi è circa: $2nF/kVA$, dunque durante le condizioni nominali, la corrente, che attraversa le tre capacità è pari a:
$$
I_{c}=3\omega C_{0}E = 3\cdot 314 \cdot 2\times {10}^{-9}\cdot 1000 kVA \simeq 0.4A
$$
nella realtà i valori saranno ancora più piccoli.

Guasto con due masse, si realizza un impianto di terra per ogni utilizzatore o gruppo di utilizzatori, nasce il problema che in caso di un primo guasto a terra non c'è alcun intervento di un sistema di protezione, in caso di un secondo guasto, di un'ulteriore linea, si ha un corto circuito che si richiude nel terreno.
Questa corrente può portare le masse a tensioni differenti. Andrebbe installato un sistema differenziale oppure realizzare un unico impianto di terra, in tal caso non ci sarà corrente nel terreno ma un corto circuito franco.


L'obbiettivo è risolvere il guasto prima che avvenga il secondo, si monitorano le tensioni "stellate", si pongono delle lampade sulle tre fasi connesse e il neutro. Si avrà infatti una variazione di tensione in caso di guasto, e di luminosità delle lampade.