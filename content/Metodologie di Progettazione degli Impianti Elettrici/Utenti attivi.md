Per gli utenti attivi sarà sicuramente presente un dispositivo di protezione generale che risponderà agli stessi requisiti indicati nella CEI 0-16 come nel caso di utenti passivi.

Saranno presenti in più dei dispositivi di interfaccia tali che permettano il distacco del'impianto di produzione dalla rete.
Il dispositivo di interfaccia separa una parte di impianto non abilitata all'utilizzo in isola, dalle utenze privilegiate e quelle abilitate invece al funzionamento in isola.
Può essere presente un sistema di accumulo, può essere connesso sul lato DC del generatore oppure direttamente alla rete, mediante un raddrizzatore aggiuntivo.

Si potrebbe anche dedicare un ulteriore dispositivo di interfaccia che gestisca il dispositivo di accumulo, interbloccato a quello connesso alla rete, utilizzato in caso di sistemi di accumulo con taglie rilevanti.
Saranno presenti in questo caso due dispositivi generatori.

Il sistema di accumulo è visto dalla rete come un generatore a tutti gli effetti, o come carico se è prevista una ricarica dalla rete.
Qualsiasi sia il sistema di accumulo, e anche se non prevede l'immissione di energia in rete, se presente configura l'utente come **attivo** dal punto di vista del gestore.

Il dispositivo di interfaccia interviene in caso di problemi lato rete, in caso di buchi di tensione oppure tensioni troppo elevate.
In caso di assenza di tensione di rete, vi sarà il non intervento del dispositivo generale, ma ciò non garantirebbe la protezione del generatore utente che potrebbe continuare ad alimentare la rete, rendendo una eventuale manutenzione della rete, da parte del gestore, pericolosa.

Inoltre, in caso di guasto, questo non dovrebbe essere alimentato dall'utente, potrebbe però causare l'intervento dei dispositivi di massima corrente, ciò dipenderebbe dalla distanza dal guasto.

Un sistema di produzione non deve alterare le caratteristiche della rete, pertubandone le tensioni o la frequenza, l'immissione di potenza deve avvenire in maniera sincrona con la rete.

Per potenze superiori ad 1MW è necessario un dispositivo di controllo centrale (**CCI**) necessario ad abilitare funzioni e servizi aggiuntivi al fine di sfruttare le proprie risorse per aiutare la rete.

L'intervento del dispositivo di interfaccia non è semplice da gestire, in caso di funzionamento connesso in rete il controllo di un impianto fotovoltaico ad esempio richiede solo di inseguire il MPP, viceversa durante il funzionamento in isola è richiesta la generazione di tensioni sinusoidali a 230V e 50Hz, dunque il convertitore deve avere la capacità di fornire questa tensione, scollegato dalla rete, si parla di grid-following e grid-forming.

Nel caso in cui la potenza dell'impianto di produzione sia inferiore a 400kW, il gestore richiede un limite di potenza erogata con un $\cos \varphi$ non inferiore a 0.9, viceversa per potenze superiori può essere richiesta qualsiasi potenza reattiva, al fine di regolare la caduta di tensione sulla linea.

## FRT Fault-Ride-Through
La normativa prevede una zona in un piano tensione-tempo entro la quale l'impianto di produzione non deve essere disconnesso dalla rete.
Ad esempio l'impianto non si deve disconnettere in caso di un buco di tensione fino al 5% per un tempo massimo di 200ms, aumenta linearmente fino all'85% della tensione nominale per un tempo di 1.5s.
Per quanto riguarda l'overvoltage invece c'è una sovratensione del 25% ammissibile per 100ms, fino a diminuire al 15% di tensione oltre il mezzo secondo.
Questi fenomeni sono legati ad eventuali guasti e le sovratensioni possono essere dovute agli interventi degli organi di manovra.
Con questi valori vanno tarati i relee di minima e massima tensione.
