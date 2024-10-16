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


In caso di secondo guasto una corrente di guasto incide in una maglia che coinvolge due fasi e l'impianto di terra, se questo è diverso per ogni massa allora il sistema si "riduce" ad un sistema TT, per questo motivo è necessario utilizzare un interruttore differenziale.
Se invece l'impianto di terra è unico ci si riconduce ad un sistema TN, vengono utilizzati in questo caso dei sistemi di protezione da sovracorrente.

Al fine di garantire la continuità di servizio, è necessario risolvere il guasto prima che avvenga il secondo, si monitorano le tensioni "stellate", si pongono delle lampade sulle tre fasi connesse e il neutro. Si avrà infatti una variazione di tensione in caso di guasto, e di luminosità delle lampade.

Un sistema di protezione che monitori la tensione sulle fasi è quello di utilizzare un sistema "a trasformatore" utilizzando un primario a stella e un secondario a triangolo con in serie un *relee* di rilevazione, in caso di guasto si ha una tensione al secondario più elevata. Si passa da una tensione al secondario di $\sqrt{ 3 }E$ a $3E$.

Si preferisce comunque usare sempre un impianto di terra comune per evitare l'utilizzo di interruttori differenziali, riconducendo il sistema IT in sistema TN in caso di doppio guasto a terra.

# Dimensionamento di un sistema IT
In caso di doppio guasto, con impianto di terra comune per le masse, si deve garantire che 
$$
I_{a}\dot{Z}_{s} = \sqrt{ 3 }U_{0}
$$
Ma la tensione di alimentazione è somma di due fasi, dunque compare un termine $\sqrt{ 3 }$.
Si dimensiona la corrente di intervento degli interruttori o l'impedenza di linea:
$$
I_{a} \leq \frac{\sqrt{ 3 }U_{0}}{2\dot{Z}_{s}} \qquad \dot{Z}_{s}\leq \frac{\sqrt{ 3 }U_{0}}{2I_{a}}
$$
In questo caso, a differenza del sistema TN, l'anello di guasto è lungo il doppio.
Dato che l'impedenza di guasto dipende dal punto in cui avviene il guasto, si dimensiona per il punto di massima distanza, in modo da avere un'impedenza massima e quindi la minima corrente di guasto, che deve essere maggiore della corrente di interruzione dell'interruttore magneto-termico.

Il tempo di intervento è identico a quello del sistema TN:
$$
\begin{matrix}
U_{0} / U & \text{tempo C.O.} &\text{tempo C.P.}\\
120 / 230 & 0.8s & 0.4s \\
230 / 400 & 0.4s  &0.2s \\
400 / 690 & 0.2s &  0.06s\\
690 / 1000 & 0.1 & 0.02s
\end{matrix}
$$
I valori sono legati ai livelli di isolamento dei cavi, in caso di guasto a terra di una fase, incide sul cavo, rispetto a terra la tensione concatenata.

In caso di guasto fase neutro, è la tensione stellata $U_0$ ad incidere sull'anello di guasto, si rimuove il $\sqrt{ 3 }$.
Dunque è sufficiente soddisfare la relazione 
$$
I_{a} \leq \frac{U_{0}}{2\dot{Z}_{s}}
$$
e non la precedente con il $\sqrt{ 3 }$.
Il sistema di protezione potrebbe non essere sufficientemente veloce.

In aree differenti si possono usare impianti di terra differenti, in tal caso potrebbe essere necessario l'uso di un interruttore differenziale.


Va ricordata la presenza di accoppiamenti capacitivi nel sistema IT, in  caso di guasto della fase 3 a terra, vi sarà una corrente di guasto che si richiude appunto mediante gli accoppiamenti capacitivi, uno spostamento del centro stella:
$$
\vec{U}_{EN} = \frac{\vec{U}_{01}(j\omega C_{0})+\vec{U}_{02}(j\omega C_{0})+\vec{U}_{03}\left( j\omega C_{0}+\frac{1}{R} \right)}{\frac{1}{R}+3j\omega C_{0}}
$$
semplificando:
$$
\vec{U}_{EN} = \frac{\vec{U}_{03}}{1+3j\omega C_{0}R}
$$
dove $R$ è la resistenza di guasto a terra, il centro stella si sposta.
La tensione $\vec{U}_{3E}$ della fase rispetto a terra sarà:
$$
\vec{U}_{3E} = \vec{U}_{03}-\vec{U}_{EN}
$$
Si sposta su una semicirconferenza dall'origine al punto $\vec{E}_{3}$, al variare della resistenza di guasto $R$.
La tensione sulle altre fasi aumenta, la $\vec{U}_{3E}$ è proprio la tensione alla quale si porterà la massa guasta.


## Guasto induttivo
Può esserci un problema di risonanza in caso di guasto induttivo, sarà sufficiente installare una resistenza $R_{0}$ nel punto di neutro, riapplicando l'equazione precedente si sostituisce l'impedenza $j\omega L$ ad $R$:
$$
\vec{U}_{EN} = \frac{\vec{U}_{01}(j\omega C_{0})+\vec{U}_{02}(j\omega C_{0})+\vec{U}_{03}\left( j\omega C_{0}+\frac{1}{j\omega L} \right)}{\frac{1}{j\omega{L}}+3j\omega C_{0}}
$$
semplificando:
$$
\vec{U}_{EN} = \frac{\vec{U}_{03}}{1-3\omega^2LC_{0}}
$$
La tensione $\vec{U}_{EN}$ si porta ad un valore superiore alla $\vec{U}_{03}$, al limite la condizione di risonanza:
$$
3\omega^2LC_{0} = 1 \Rightarrow L=\frac{1}{3\omega^2C_{0}}
$$
in tal caso la tensione "diverge". Collegando il neutro a terra mediante una resistenza aggiuntiva $R_{0}$, **non confonderla con la resistenza dell'impianto di terra del neutro per i sistemi TT e TN**.
La resistenza aggiuntiva modifica il calcolo della tensione nel seguente modo:
$$
\vec{U}_{EN} = \frac{\vec{U}_{01}(j\omega C_{0})+\vec{U}_{02}(j\omega C_{0})+\vec{U}_{03}\left( j\omega C_{0}+\frac{1}{j\omega L} \right)}{\frac{1}{j\omega{L}}+3j\omega C_{0} + \frac{1}{R_{0}}}
$$
e quindi:
$$
\vec{U}_{EN} = \frac{\vec{U}_{03}}{(j\omega L)\left( \frac{1}{j\omega L}+\frac{1}{R_{0}}+3j\omega C_{0} \right)} = \frac{\vec{U}_{03}}{1+\frac{j\omega L}{R_{0}}-3\omega^2C_{0}L}
$$
dunque in condizioni di risonanza resta il termine $\frac{j\omega L}{R_{0}}$ con il quale dimensionare $R_0$, conosciuta la $L^*$ di risonanza.
$$
\frac{\omega L^*}{R_{0}} = 1 \Rightarrow \frac{\omega}{3\omega^2C_{0}} =R_{0} \leq \frac{1}{3\omega C_{0}}
$$
un valore tipico è circa
$$
\frac{10^7}{3\cdot 2\pi f\cdot 5000} \simeq 100\Omega
$$
conviene in realtà mettersi al limite del valore massimo, altrimenti ci si riconduce ad un sistema TT.

## Esercizio sul sistema IT con impianti di terra separati
Questo è il caso sconsigliato dalle norme.
Bisogna garantire la tensione di contatto non pericolosa al secondo guasto, il sistema diventa TT.
Si deve garantire l'intervento dell'interruttore differenziale solo al secondo guasto e non al primo.

Al primo guasto saranno presenti gli accoppiamenti capacitivi, tra le fasi e anche il conduttore di neutro, distribuito; saranno quindi presenti quattro accoppiamenti capacitivi.

La tensione verso terra del neutro, con la fase 2 guasta con una resistenza $R_E$:
$$
\vec{U}_{EN} = \frac{\vec{U}_{01}j\omega C_{0}+\vec{U}_{02}\left( j\omega C_{0}+\frac{1}{R_{E}} \right)+\vec{U}_{03}j\omega C_{0}}{4j\omega C_{0} + \frac{1}{R_{E}}}
$$
mettendo in evidenza:
$$
\vec{U}_{EN} = \frac{\vec{U}_{0}\frac{1}{R_{e}}}{\frac{1}{R_{E}}+4j\omega C_{0}} = \frac{\vec{U}_{0}}{1+4j\omega C_{0}R_{E}}
$$
Si vuole calcolare la corrente di guasto $\vec{I}_{g}$, quella che si richiude attraverso la resistenza di guasto, non è l'intera corrente che attraversa la fase guasta.
$$
\vec{I}_{g} = \frac{\vec{U}_{02}-\vec{U}_{EN}}{R_{E}} = \vec{U}_{0}\cdot \frac{\frac{1}{R_{E}}}{1+4j\omega C_{0}R_{E}}
$$
In realtà la corrente è prevalente sugli accoppiamenti capacitivi al primo guasto, si può trascurare il termine resistivo.

$$
R_{E}\cdot \vec{I}_{g}\leq \vec{U}_{L} \Rightarrow \frac{R_{E}\vec{U}_{0}}{R_{E}+\frac{1}{4j\omega C_{0}}}\leq \vec{U}_{L}\Rightarrow \frac{R_{E}U_{0}}{\sqrt{ R_{E}^2 +\frac{1}{16\omega^2C_{0}^2} }} \leq U_{L}
$$

Si configura un sistema TT con il collegamento del neutro mediante una capacità.
Normativa: 
$$
R_{E} \leq \frac{U_{L}}{\sqrt{ U_{0}^2 - U_{L^2} }}\cdot \frac{1}{4\omega C_{0}}
$$
supponendo che $\vec{U}_{0}$ e $\vec{U}_{L}$ siano in quadratura.