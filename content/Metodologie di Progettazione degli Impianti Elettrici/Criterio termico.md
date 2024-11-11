Un criterio utilizzato per la progettazione degli impianti elettrici, soprattutto per impianti in cavo, è il criterio termico.
Si  supponga di avere un conduttore cilindrico separato dall'ambiente mediante un materiale isolante, attraversato da una certa corrente $i(t)$, nel conduttore si dissipa una potenza termica proporzionale alla sua resistenza, pari a $Ri^2(t)$. Con il trascorrere del tempo $dt$ corrisponderà una variazione della temperatura $d\theta$ e una conseguente variazione dell'energia dissipata $dW_{p}$ composta dall'energia immagazzinata nell'isolante e quella scambiata con l'ambiente circostante.

L'equazione di bilancio termico è la seguente:
$$
dW_{p} = dW_{i} + dW_{c}
$$
esprimibile anche come:
$$
dP_{p}dt = mcd(\Delta\theta) + KS\Delta\theta dt
$$
dove $m$ è la massa dell'isolante espressa in $kg$ e $c$ è il calore specifico dell'isolante per unità di massa conseguente ad una variazione della temperatura di 1 grado (C° o K), ha dimensione $\left[ \frac{J}{kg\cdot °C} \right]$.
Il termine $KS$ indica la variazione di energia a seguito dello scambio termico con l'esterno mediante la superficie $S$.
$K$ è il coefficiente globale di scambio termico $\left[ \frac{m^2}{m^2°C} \right]$.

L'equazione differenziale è del primo ordine:
$$
\frac{d\Delta \theta}{dt} + \frac{KS}{mc}\Delta \theta - \frac{dP_{p}}{mc} = 0
$$
le soluzioni di questa equazione sono del tipo:
$$
\Delta\theta(t) = Ae^{-t/\tau} + B
$$
con $\tau$ la costante di tempo del problema pari a $\frac{mc}{KS}$ ovvero $\left[ \frac{kgJm^2°C}{kg°CWm^2} \right] = [s]$.
Per l'istante iniziale si può sostituire l'equazione con temperatura iniziale pari a quella ambiente (dunque sovratemperatura $\Delta\theta=0$) e ricavare i valori iniziali:
$$
t=0 \ A+B=0
$$
Per $t\to \infty$ si trascura il termine esponenziale:
$B=\Delta\theta_{r}=\theta_{r}-\theta_{a}$ e dunque il termine $A$ sarà pari a $-\Delta\theta_{r}$.
In sintesi:
$$
\Delta\theta(t) = \Delta\theta_{r}(1-e^{-t/\tau})
$$
Se si suppone il cavo a regime, la sua temperatura non varia ulteriormente e la potenza termica dissipata sarà pari a:
$$
RI_{rms}^2 = KS\Delta\theta
$$
e dunque la corrente del cavo:
$$
I = \sqrt{ \frac{KS^2}{\rho L}(\theta_{r}-\theta_{a}) }
$$
quando la temperatura del cavo $\theta_{r}=\theta_{s}$ è pari alla temperatura di servizio, con la precedente si ricava la corrente $I_{z}$ detta **portata** del cavo.

## Legge di Arrhenius
Per ogni tipologie di impianti si può applicare la legge di Arrhenius secondo la quale la temperatura ammissibile varia con l'età del cavo.
Inoltre i conduttori sono isolati in EPR o PLC o XLPE e al variare di questi varia la temperatura di sevizio.

## Intervento dell'interruttore termico
A seguito di un sovraccarico ci sarà una riduzione della temperatura del carico, con la stessa costante di tempo, non ci sarà più corrente e quindi dissipazione di potenza elettrica, si ottiene un'equazione omogenea del raffreddamento del cavo:
$$
\frac{d\Delta\theta}{dt} + \frac{KS}{mc}\Delta\theta = 0
$$
tutta l'energia termica immagazzinata nell'isolante viene rilasciata in ambiente, con conseguente raffreddamento dell'isolante, con una legge del tipo:
$$
\Delta\theta(t) = \Delta\theta_{r}\left(1-e^{t/\tau}\right)
$$
Si intende con invecchiamento dell'isolante la riduzione della sua capacità di sostenere una determinata tensione sulla sua superficie.
Per questo motivo si definiscono in ogni caso delle temperature massime dell'isolante, che possono essere sostenute per un determinato periodo di tempo, breve, durante l'intervento degli interruttori.

<center>

| Materiale | $\theta_{s}$ |   $\theta_m$     |
| --------- | ------------ |   --------------|
|      PVC     |   70°C           |    160°C     |
|  EPR-LXPE  | 90°C | 250°C |
| stagno | 70°C  | 160°C  |

</center>

# Corto circuito
In caso di corto circuito, si suppone che non sia presente scambio termico con l'ambiente esterno, si suppone che la dinamica sia veloce, dunque tutta l'energia dissipata si accumula nel isolante.
$$
dW_{p} = dW_{i} + \cancel{dW_{c}}
$$
dunque
$$
\frac{\rho L}{S} i^2(t)dt = mcd\Delta\theta = Slcd\Delta\theta
$$
si considera il calore specifico rispetto ad una "massa volumetrica" $Sl$ dove $S$ è la sezione del cavo.
Si ricava l'integrale nel tempo:
$$
\int_{0}^{t_{i}} i^2(t)dt = \int_{\theta_{0}}^{\theta_{f}} \frac{S^2cd\Delta\theta }{\rho}d\theta = S^2C \int_{\theta_{0}}^{\theta_{f}} \frac{d\Delta\theta}{\rho_{0}(1+\alpha\Delta\theta)} d\theta = \frac{S^2C}{\rho_{0}} \left[\ln(1+\alpha\Delta\theta)\right]_{\theta_{0}}^{\theta_{f}}
$$
Il primo termine è **l'integrale di Joule** e rappresenta l'energia specifica che attraversa il conduttore.
$$
\int_{0}^{t_{i}} i^2(t)dt = \left[ \frac{cS^2}{\rho_{0}{\alpha}}\ln\left( \frac{1+\alpha\Delta\theta_{f}}{1+\alpha\Delta\theta_{0}} \right) \right] = K^2S^2
$$
Il secondo termine prende il nome di energia specifica massima sopportabile dal cavo, quando $\theta_{f}$ coincide con la temperatura massima ammissibile $\theta_{f}$ e $\theta_{0}=\theta_{s}$.
Nel caso di corto circuito l'integrale di Joule deve essere minore dell'energia specifica attraversante il cavo.

Si introduce la caratteristica di intervento dell'interruttore magneto termico, composto da una caratteristica a tempo inverso fino ad un certo valore di corrente, poi un intervento a tempo costante.
La curva di $i^2t$ presenta invece un andamento prima decrescente, fino ad un minimo e poi crescente, l'andamento di $K^2S^2$ è invece praticamente costante. L'intersezione delle due curve determina una regione di protezione per il cavo limitata.

La corrente di corto circuito deve essere interna a questa regione, non può essere troppo elevata ma non può nemmeno permanere per troppo tempo se piccola.
Nel caso di un fusibile la curva di intervento è monotona decrescente, si ha solo una condizione di intervento minima.
