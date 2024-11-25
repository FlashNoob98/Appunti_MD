Si definisce la corrente di inserzione:
$$
i_{si}(t) = \frac{I_{0i}}{\sqrt{ 2 }} e^{-t/t_{i}}
$$
I valori $I_{oi}$ sono tabellati.
Per garantire che non ci sia un intervento intempestivo dell'interruttore a protezione del trasformatore devo avere che $I_{s}>0.7I_{oi}$.


## Esempio
Trasformatore con la seguente targa:

<center>

| $A_n$      | 2000kVA |
| ---------- | ------ |
| $V_{1n}$   | 20kV   |
| $V_{2n}$   | 0.4kV  |
| $V_{cc\%}$ | 5%     |

</center>

Dato che è un trasformatore in olio: $K_{i}=8,\quad T_{i}=0.45$
Si calcolano le correnti:
$$
I_{n}' = \frac{2000\cdot{1}0^3}{\sqrt{ 3 }\cdot20\cdot 10^3} = 57.73A
$$
e dunque moltiplicando per $K_{i}$:
$$
I_{0i} = K_{i}I_{n}' = 8\cdot 57.73A = 461.84\ A
$$
e dunque la corrente di intervento del dispositivo pari a:
$$
I_{s} = 250 A
$$

# Il trasformatore
Il regolamento europeo 548/14 prevede un livello di efficienza minima del trasformatore messo in vendita, si definisce un livello **PEI**:
$$
PEI = 1 - \frac{2(P_{0}+P_{C0})}{A_{n}\sqrt{ \frac{P_{0}+P_{C 0}}{P_{k}} }}
$$
Il termine $P_{C0}$ tiene conto delle perdite per il sistema di raffreddamento mentre $P_{k}$ sono le perdite sotto carico nelle condizioni nominali.
Per il sistema di raffreddamento vanno dimensionate le aperture della cabina, se non è presente un sistema di convezione forzata per raffreddare il trasformatore si considera la seguente formula:
$$
A = 0.238 \frac{P_{diss}}{\sqrt{ h }}
$$
dove $h$ è la distanza in altezza tra le due aperture.

In caso di convezione forzata invece:
$$
A = \frac{Q}{3600\cdot v}\quad Q= 343P_{diss}
$$
e $v$ è la velocità dell'aria.

Un trasformatore può essere sovradimensionato per alcuni carichi, la norma CEI EN 50160 afferma che il THD del distributore deve essere inferiore al 2% su misurazioni ogni 10 minuti.
Questo è un vincolo per il distributore e non per l'utente.
Definito anche come il rapporto tra la terna inversa e quella diretta.

L'effettiva potenza del trasformatore:
$$
A_{e} = kA
$$
con $k$ definito nella CEI 14-22, funzione del numero di carichi non lineari.

## Parallelo di trasformatori
Per disporre dei trasformatori in parallelo, si deve garantire che abbiano lo stesso rapporto di trasformazione e siano dello stesso gruppo.

Il rapporto tra le potenze nominali non deve superare $\frac{2}{3}$.
La condizione ideale se il $\cos{\phi_{cc}}$ è identico, e la tensione di corto circuito è identica, anche se non è una condizione vincolante.

Si supponga di avere tre trasformatori in parallelo:
$$
\frac{\Delta E_{i\%}}{\Delta V_{cc\%}} = \frac{\Delta E_{i}}{\Delta V_{cc}} = \frac{I_{i}}{I_{in}} = \frac{A_{i}}{A_{in}}
$$
La corrente si ripartisce nei trasformatori al variare della loro impedenza di corto circuito e della tensione di corto circuito.

Ad esempio le tre tensioni di corto circuito:
$$
\begin{aligned}
V_{cc_{1}} &= 5\%\Rightarrow A_{1} = 100 \cdot \frac{4}{5} = 80kVA\\
V_{cc_{2}} &= 4\%\Rightarrow A_{2} = 200\cdot \frac{4}{4} = 200kVA\\
V_{cc_{3}} &= 5\%\Rightarrow A_{3} = 300\cdot \frac{4}{6} = 200 kVA
\end{aligned}
$$
I tre trasformatori hanno una potenza apparente di 100, 200 e 300 kVA.
Solo il trasformatore centrale ha raggiunto la potenza nominale.
Una richiesta successiva di potenza richiederà un sovraccarico del trasformatore 2.

Se si assegna una certa potenza assorbita dal carico e la tensione di corto circuito dei trasformatori, si può calcolare la caduta di tensione percentuale:
$$
\frac{\Delta_{1n}\Delta E}{\Delta V_{cc_{1}}} + \frac{\Delta_{2n}\Delta E}{\Delta V_{cc_{2}}} +\frac{\Delta_{3n}\Delta E}{\Delta V_{cc_{3}}} = 500
$$
Si ricava:
$$
\Delta E \left( \frac{100}{5} + \frac{200}{4} + \frac{300}{6} \right) = 500 \Rightarrow \Delta E = 4.16\%
$$
E quindi le tre potenze assorbite dai trasformatori:
$$
\begin{aligned}
\Delta_{1n} &= 100\cdot \frac{{4}.16}{5} = 83.2 kVA\\
\Delta_{2n} &= 200\cdot \frac{4.16}{4} = 208kVA\\
\Delta_{3n} &= 300 \cdot \frac{4.16}{6} = 208kVA
\end{aligned}
$$
Dunque il trasformatore 2 è ancora in sovraccarico.
Se le tensioni di corto circuito fossero identiche, si avrebbero tutti e tre i trasformatori caricati allo stesso modo.


## Protezione dei trasformatori lato BT
In caso di cabina con trasformatori in parallelo, sono disposti degli interruttori lato BT per ogni macchina, a monte della sbarra BT. 
In caso di guasto, a causa della piccola lunghezza della sbarra potrebbe essere difficoltoso avere una selettività degli interruttori, il guasto sarebbe alimentato da entrambi i trasformatori.

Il problema diventa delicato se ci sono più di due trasformatori in parallelo. In caso di guasto a monte dell'interruttore e tre trasformatori in parallelo, si avrebbe una corrente di guasto pari a $2I$ se $I$ è la corrente di guasto che si avrebbe con un singolo trasformatore.

Sembrerebbe che gli interruttori lato BT dovrebbero essere in grado di interrompere una corrente doppia rispetto ad una configurazione non in parallelo.
Per questo motivo non è mai consigliabile di utilizzare trasformatori in parallelo, solo in casi particolari come guasti di uno dei trasformatori, si può utilizzare un *congiuntore di sbarra*.
Il carico va partizionato sui vari trasformatori durante il normale funzionamento.
In questo caso si potrebbero considerare anche trasformatori di taglia differente, solitamente le cabine utente presentano tre trasformatori di cui uno di riserva fredda, ovvero non in uso ma pronto ad essere utilizzato.
Se uno degli interruttori a valle di un trasformatore si apre, sarà necessaria la chiusura del *congiuntore di sbarra*.

## Comando del dispositivo di protezione generale
Il dispositivo di Protezione Generale (PG o PG0) interviene in seguito a misure effettuate sulla linea a monte, mediante TA, TV o TO (trasformatori omopolari, per i guasti a terra in MT).
Sia il distributore che l'utente devono attenersi alla CEI 0-16.
Il PG è necessario in caso di guasti in media tensione, dei trasformatori o degli elementi di manovra, è necessario al fine di non causare un'interruzione in cabina primaria, che causerebbe la disalimentazione dell'intera linea.

Per il rilevamento delle sovracorrenti si usa il relee 51, con soglia termica, magnetica e
Esistono infatti tre soglie:
$$
\left\{
\begin{aligned}
51.S{1}&\ I>\text{ facoltativa}\\
51.S 2&\ I>> 250A\ 500 ms\\
51.S3&\ I >>> 600A\ 120 ms\\
\end{aligned}\right.
$$
La prima soglia è facoltativa, potrebbe causare degli interventi intempestivi, ha la caratteristica di una curva termica a tempo inverso.
Se si usa va coordinato con il distributore che deve fornire le soglie.
Con la soglia S2 si indica il valore minimo oltre il quale intervenire.
La soglia S3 richiede l'intervento "istantaneo" del relee, ovvero $50ms$ per individuare il guasto e $70ms$ per estinguere l'arco.
Tutti gli interruttori a valle del sistema dovranno essere al di sotto di queste soglie.

Le soglie vanno stabilite in funzione del TA, ad esempio con un TA di rapporto $m:300/5=60$ allora la soglia $IS_{2}=\frac{250}{60}=4.16A$ mentre la soglia $I{S}_{3} = \frac{600}{60}=10A$.

Per quanto riguarda il tempo, i TA sono caratterizzati da una classe di precisione 5p, con valori tabellati che indicano il massimo tempo, a  cui vanno sottratti $70ms$ quindi i valori di soglia dei relee diventano $430ms$ e $50ms$ per S_2 e S_15 a causa dei delay introdotti dai TA.

### Protezione omopolare
Il trasformatore lato MT è collegato a triangolo, il relee omopolare rileva correnti omopolari nel punto di collegamento della macchina, in caso di guasti monofase a terra determinano correnti di guasto mediante gli accoppiamenti capacitivi. La presenza di un guasto è identificata dalle correnti omopolari, la taratura del relee dipende sostanzialmente dai parametri della rete.

È importante determinare per quali guasti NON intervenire, in caso di guasti lato distributore ad esempio, vi saranno degli accoppiamenti capacitivi anche nell'impianto utente, dunque
una corrente di guasto si richiuderà nella parte a monte del punto di connessione ma anche attraverso l'impianto utente.
In questo caso la corrente di guasto attraverserà il relee in verso opposto.

Il relee omopolare ha sigla 51N con soglia S1 ed S2, non sono due soglie sulla stessa caratteristica ma alternative, in caso di neutro isolato o compensato.
Va posto il più vicino possibile al punto di arrivo della linea.

La prima soglia S1 è valida se non è presente un relee NO67N, ovvero un relee direzionale.
In caso contrario se è presente il relee direzionale si considera la seconda soglia S2, funzione della corrente di corto circuito monofase fornita dal distributore.

<center>

| Nome soglia | Neutro isolato            | Neutro compensato         |
| ----------- | ------------------------- | ------------------------- |
| 51N.S1      | 2A - 170ms                | 2A - 450ms                |
| 51N.S2      | $140\%I_{cc_{m}}$ - 170ms | $140\%I_{cc_{m}}$ - 170ms |

</center>

Il relee 67N è dunque un relee omopolare direzionale, è in grado di discernere se il guasto avviene a monte lato distributore o a valle lato utente.
Maggiore è la dimensione dell'impianto lato MT, maggiori saranno le correnti capacitive che si richiuderebbero a causa di un guasto lato distributore, in tal caso la corrente di guasto potrebbe superare i 2A e richiedere quindi l'utilizzo del relee direzionale.

<center>

| Nome soglia                | Soglia                                                             |
| -------------------------- | ------------------------------------------------------------------ |
| 67N.S1 (Neutro compensato) | $I_s = 2A,\ U_0 = 5V,\ \angle{U_{0}I_{0} = (60\div 120)°}$ - 450ms |
| 67N.S2 (Neutro isolato)    | $I_s = 2A,\ U_0 = 5V,\ \angle{U_{0}I_{0} = (60\div 250)°}$ - 170ms |

</center>

Entrambi hanno comunque una soglia istantanea a 120A e 120ms.


# Selettività
Considerato un interruttore PG0 con le soglie di intervento 51:S2 e 51.S3 (50), un eventuale dispositivo di protezione del trasformatore DG1 dovrà avere una corrente di intervento più bassa e tempi inferiori, per garantire la selettività, la seconda soglia sarà comunque limitata da un tempo minimo di rilevazione ed estinzione del guasto di 120ms.

Prima dei trasformatori potrebbero esserci altre parti in MT, con le rispettive protezioni sempre inferiori al PG0.
Per quanto riguarda il tempo di intervento siamo limitati tra i 500ms dell'interruttore a monte e i 120ms minimi di intervento, considerando anche gli errori di temporizzazione, tempo di estinzione e margini di sicurezza.

Ad esempio:
- tempo di apertura 60ms, 
- inerzia della protezione 20ms, 
- errore del temporizzatore 60ms,
- margine di sicurezza 50 $\div$ 100 ms, in funzione della qualità dei dispositivi
Sommando tutti questi valori si ottiene un tempo totale di $190\div 240\ ms$, inserendo anche solamente due interruttori in serie, per garantire la selettività si avrebbe un tempo totale di quasi $500ms$.

In caso di selettività logica i due relee sono connessi mediante un cavo dati, il relee a monte non interviene entro un certo ritardo, aspettando l'intervento del relee a valle.