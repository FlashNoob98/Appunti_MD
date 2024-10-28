Per guasti in media tensione il distributore interviene per tempi superiori a 10s, dunque la tensione massima di contatto a vuoto è pari a $80V$, di conseguenza la resistenza di terra del neutro deve essere inferiore a 1.6Ohm.
In realtà anche con una resistenza maggiore, la norma preveda che la tensione di contatto sia superiore a 80V, dunque si può inserire un coefficiente $k$ moltiplicativo la $U_{TP}$ pari ad 1.5 se si garantisce una zona di equipotenzialità, ovvero con un impianto di terra magliato.
Ciò è valido per il sistema TN.

Nel sistema IT si preferisce il collegamento delle masse allo stesso impianto di terra, di conseguenza un eventuale guasto causerebbe una sovratensione, quindi il problema viene gestito allo stesso modo di un guasto in bassa tensione del sistema IT.

Nei sistemi TT il neutro è connesso a terra in cabina e le masse lo sono altrettanto con il loro impianto di terra caratterizzato da una resistenza $R_{BT}$, la sovratensione dovuta al guasto in MT si manifesta sul neutro, non sulle masse.
La tenuta degli isolanti degli apparecchi però sono sottoposti ad una tensione superiore, dovranno rispettare le seguenti tensioni di isolamento in base al tempo di interruzione del gusto:
$$
\left\{
\begin{aligned}
\leq & 250\ V\ \text{se } t_{f}\leq {5}s\\
\leq & 500\ V \ \text{se }t_{f} > 5s
\end{aligned}
\right.
$$

In realtà la CEI 99/3 porta i 500V a 1200V.
Allo stesso modo il distributore deve garantire questa tensione massima per $R_{N}I_{E}$ minore di 250V o 1200V in base al tempo di intervento.

In caso di cabina proprietaria si decide di non collegare l'impianto di terra del sistema in AT a quello in BT, per evitare la propagazione di sovratensioni sulle masse in caso di guasto in AT.
Nel caso del trasformatore però, la sua massa va collegata all'impianto di AT.

Si deve garantire che
$$
U_{0} + R_{AT}I_{E} \leq U'_{t}
$$
dove $U'_{t}$ è la tensione di tenuta dell'isolamento a 50Hz, dunque l'isolamento del secondario del trasformatore deve essere dimensionato considerando ipotetici guasti in AT.
Il valore di $I_{E}$ è in realtà dovuto ad un guasto capacitivo della linea in MT, sono presenti degli sfasamenti, non si dovrebbe eseguire la somma aritmetica, ma in maniera cautelativa si considera il valore massimo.
Ciò è comunque vero se si considera che il guasto è capacitivo e il trasformatore è solitamente del tipo triangolo stella gruppo 11, dunque esiste uno sfasamento di 30 gradi in anticipo tra le tensioni del secondario e primario, si troverà dunque una delle tre fasi allineata alla tensione di guasto.

Si pone l'impianto di terra del neutro in BT esterno alla cabina, solitamente in caso di linea aerea sul primo palo disponibile.
Scelta obbligata quando la corrente $I_{E}$ è particolarmente elevata.

In caso di guasto a terra lato BT, si richiuderà una corrente mediante la resistenza del neutro, per la protezione dai contatti indiretti ci si pone nella curva di sicurezza a 50V, si dimensiona la resistenza $R_{E}$ in base al valore di intervento dell'interruttore differenziale.
Dimensionata la $R_E$ si procede a dimensionare la $R_{N}$ mantenendo il rapporto
$$
\frac{U_{0}}{R_{N}+R_{E}} \geq 1
$$
o comunque il valore di corrente di intervento scelto per il differenziale.
$$
R_{N} \leq U_{0}-R_{E}I_{Dn} = 230-50 = 180 \Omega 
$$
con differenziale da 1A, il valore di corrente è elevato per garantire la selettività.
