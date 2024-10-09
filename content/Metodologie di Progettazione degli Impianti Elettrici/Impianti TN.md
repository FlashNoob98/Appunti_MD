Nel caso di impianti TN è presente un unico collegamento a terra in cabina mediante una resistenza $R_N$, viene distribuito il neutro come conduttore di protezione (conduttore PEN, sistema TN-C) o eventualmente un conduttore di protezione separato (sistema TN-S).

# Sistema TN-S
Si studia questo caso perché più completo rispetto al TN-C da studiare.
Si decide di alimentare un utilizzatore con la massa connessa a terra mediante il conduttore di protezione al neutro di cabina, a sua volta connesso a terra mediante una resistenza $R_N$.

Si supponga il contatto tra una parte attiva e la massa, si richiude la corrente di guasto mediante il conduttore di protezione e la fase (o le fasi) interessata al guasto.

Si deve garantire la sicurezza in caso di contatti indiretti, dunque si valuta la tensione di contatto, in questo caso la tensione totale di terra.
Il circuito equivalente di guasto è composto dal generatore, dall'impedenza del conduttore di fase, il punto di guasto e l'impedenza del conduttore di protezione.

Le impedenze $\dot{Z}_p$ e $\dot{Z}_{f}$ di guasto dipendono dalla distanza a cui avviene il guasto e l'impedenza del conduttore di protezione.
Si considera la tensione di contatto come la tensione totale di terra, dunque collegare il ponto a valle di $R_{EB}$ al potenziale di terra.
L'anello di guasto è composto da conduttori a bassa impedenza, il conduttore attivo è quello di fase  e quello di neutro, non quello di protezione.

Il conduttore attivo può essere interrotto, non il conduttore di protezione, dunque quando il sistema diventa TN-C, nonostante il conduttore di neutro sia attivo non può essere interrotto.

In caso di contatto la persona è in parallelo alla maglia di guasto a bassa impedenza con una sua resistenza serie $R_B$ e $R_{EB}$, l'impedenza dell'anello di guasto è data dalla serie dell'impedenza del conduttore di fase e quello di protezione.
Calcolando l'equivalente di Thevenin tra il punto di contatto e la terra, in assenza di contatto la resistenza $R_N$ non è attraversata da corrente, dunque
$$
\vec{U}_{eq} = \vec{U}_{0} \frac{\dot{Z}_{p}}{\dot{Z}_{p}+\dot{Z}_{f}} = \frac{\vec{U}_{0}}{1+\frac{\dot{Z}_{f}}{\dot{Z}_{p}}} \Rightarrow |U_{eq}| \simeq \frac{|U_{0}|}{2}
$$
Si può ipotizzare che i due conduttori abbiano la stessa impedenza.
Si può avere un conduttore di protezione più piccolo di quello di fase, in tal caso:
$$
\dot{Z}_{p}=2\dot{Z}_{f} \Rightarrow |U_{eq}|\simeq \frac{2}{3}|U_{0}|
$$
Per correnti fino a $32A$ solitamente le sezioni dei conduttori sono identiche.
mentre l'impedenza equivalente:
$$
\dot{Z}_{eq} = R_{N} + \frac{\dot{Z}_{p}\dot{Z}_{f}}{\dot{Z}_{p}+\dot{Z}_{f}}
$$
Una prima approssimazione prevede che la $U_{eq}$ è data dal partitore dei due conduttori, prossima alla tensione a vuoto, si potrebbe ridurre soltanto riducendo il modulo di $\dot{Z}_{p}$ aumentandone la sezione, per valori tecnicamente inaccettabili, anche le correnti di guasto sarebbero poi inaccettabili.

Il corto circuito tra i piedi della persona e il punto di messa a terra è legato all'ipotesi di equi-potenzialità del terreno, ad una distanza adeguata dall'impianto di messa a terra.

Nell'ipotesi in cui la persona che entri in contatto con la parte guasta si trovi all'interno dell'edificio, questa non sarà connessa francamente a terra ma sarà connessa mediante un'ulteriore resistenza dovuta al dispersore di fatto costituito dall'armatura del cemento, questa ulteriore resistenza, di natura aleatoria aggiunge un potenziale rispetto a terra, riducendo la differenza  di potenziale effettiva alla quale si pone la persona.
Si identifica una zona di equipotenzialità identifica una regione in cui la tensione rispetto alla quale si trova la massa è inferiore alla tensione totale di terra.

La normativa prevede che se l'oggetto da proteggere si trova in una zona equipotenziale, allora si può ridurre la tensione $U_{eq}$ dell'20%:
$$
U_{eq} = \frac{U_{0}}{2}\cdot 0.8 = 230\cdot \frac{4}{10} = 92V
$$
Nel caso in cui i conduttori siano identici.

Utilizzando le curve di sicurezza si trova che per una tensione di $92V$ c'è un tempo massimo di esposizione per evitare la fibrillazione di $0.4s$, mentre per la tensione di $50V$ si avevano $5s$.
In condizioni particolari la curva è più a sinistra e i $92V$ possono essere sostenuti per $0.2s$.
Va dimensionato il sistema di protezione entro questi tempi, in questo caso l'interruttore magneto-termico.
Ciò non è sempre possibile se le portate dei cavi siano troppo elevate, si potrebbero utilizzare degli interruttori differenziali oppure accettare zone di rischio.

I tempi sono più lunghi in impianti a tensioni più basse, ad esempio in America 120V si hanno dei tempi di intervento di 0.8s e 0.4s nelle condizioni ordinarie e particolari.
Per impianti a 400V invece > 0.2s e 0.06s e per impianti con tensioni superiori a 400V (fino a 1000V) un tempo di intervento di 0.1s e 0.01s.
$$
\begin{matrix}
U_{0} & \text{C.O} & \text{C.P}\\ 
120V & 0.8s & 0.4s  \\
230V & 0.4s & 0.2s  \\
400V & 0.2s & 0.06s  \\
>400V & 0.1s & 0.02s
\end{matrix}
$$
La corrente di guasto è pari alla corrente di corto circuito, dunque un unico apparecchio può funzionare da sistema di protezione da sovracorrenti e da sistema di protezione dai contatti indiretti.
Dunque la corrente nominale dell'apparecchio di protezione deve essere minore della corrente di guasto e garantire un tempo di intervento inferiore a quelli tabellati.
$$
I_{a}\leq \frac{U_{0}}{\dot{Z}_{s}}
$$
Ponendo $\dot{Z}_{s}=\dot{Z}_{p}+\dot{Z}_{f}$.
Se si usasse un interruttore differenziale, allora $I_{dn}=I_{a}$ ma potrebbe esserci un intervento troppo frequente e superfluo. L'interruttore differenziale è da collegare a monte del carico.
Si può utilizzare solo in un impianto TN-S, non devo **mai** interrompere il conduttore di protezione.
Inoltre il potere di interruzione del differenziale deve essere dimensionato sulla corrente di corto circuito e non su quella nominale di esercizio.

In caso di guasto inoltre la tensione di contatto verso terra sarà presente su tutte le masse connesse al conduttore di protezione, ma la corrente di guasto dipende dalla distanza del guasto, e quindi dalla lunghezza dei conduttori.
Dunque la corrente di guasto deve essere calcolata alla fine dell'impianto, l'interruttore deve intervenire per la più piccola corrente di guasto, che potrebbe essere quindi solo in un punto lontano dal quadro dell'impianto.

Un unico *circuito di distribuzione* comune alimenta i circuiti terminali, i *circuiti terminali* invece alimentano i carichi.
Il circuito di distribuzione è una linea in un canale metallico, si considera quindi poco probabile un guasto, per questo motivo si può sopportare la tensione di $92V$ anche per $5s$, mentre nel caso dei circuiti terminali i dispositivi di protezione devono intervenire entro i tempi stabiliti in tabella.
Diventa inoltre difficile coordinare un interruttore veloce da $0.4s$ con correnti molto grandi. CD e CT($I_n>32A\rightarrow 5s)$.

L'interruttore differenziale per correnti molto elevate è di difficile impiego, inoltre si sceglie di utilizzare un sistema TN proprio per non usare i differenziali, garantire continuità di servizio e sopportare correnti di dispersione elevate.

In caso di guasto, la tensione di contatto aumenta all'aumentare della distanza dalla cabina, a causa dell'aumento dell'impedenza del cavo, fino a raggiungere il punto di guasto, oltre quel punto la tensione resta costante e si porta allo stesso valore su tutte le masse.

Nel sistema TT invece c'era un collegamento a terra della massa del carico, per questo motivo cambia la filosofia della protezione dai contatti indiretti.
Inoltre la corrente che circola nel conduttore di protezione è molto piccola, non causa una caduta di tensione.
In prossimità del trasformatore la tensione di contatto è minima.
