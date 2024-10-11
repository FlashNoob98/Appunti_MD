Si vedrà il **field vector control** uno dei più utilizzati, è un controllo ad alte prestazioni in termini di risposta, momento della coppia elettromagnetica rispetto al flusso.
Si sceglie l'orientamento del flusso di rotore.

Un controllo scalare ragiona in termini di regime stazionario sinusoidale, si può agire sulla velocità di sincronismo variando la frequenza e di conseguenza la tensione dello statore.
A meno della caduta sulla resistenza, la tensione impressa sullo statore è circa pari alla tensione indotta, dipende dal flusso di mutua e dunque dalla frequenza, se variassi la frequenza mantenendo la tensione fissa, il flusso varierebbe, aumentando se diminuisse la frequenza e diminuendo se aumentasse la frequenza.

Il momento della coppia dipende dalla relazione tra la corrente negli avvolgimenti di statore e il flusso al rotore(?).
Per controllare rapidamente la coppia, devo cercare di mantenere l'ampiezza del flusso costante, ottimizzando i circuiti magnetici con cui ho realizzato la macchina, sono comunque limitato nell'aumento di flusso, posso al massimo diminuirlo ma aumentarlo richiederebbe un aumento di corrente magnetizzante.

Se si controlla la componente simmetrica della corrente, posso ottenere un controllo dinamico con prestazioni superiori a quello scalare.

## Algoritmo di alimentazione
Si osserva il modello della macchina (slide SCIG FOC algorithm)
$$
\left\{
\begin{aligned}
\vec{v}_{s}^s = R\cdot \vec{i}_{s} 
\end{aligned}
\right.
$$
Le correnti che attraversano lo statore sono sfasate nel tempo allo stesso modo in cui sono sfasati gli avvolgimenti nello spazio.

L'apice primo è riportato al rotore...

Se alimentassi la macchina con un componente simmetrico di tensione, e avessi un carico meccanico all'albero, il modello ammetterebbe un un'unica soluzione a regime, il sistema è matematicamente determinato.

Le incognite sono le componenti simmetriche di corrente di statore e rotore(4 equazioni, sono complesse), l'angolo di rotore e la coppia.

L'algoritmo di alimentazione è **il modello invertito della macchina unito ad un set di equazioni ausiliare che rendono il sistema unicamente determinato**.
Questo algoritmo risponde alla seguente domanda:
Che grandezza di ingresso devo fornire alla macchina affinché segua un certo profilo di velocità o coppia o angolare?

Fissato un punto di lavoro sulla curva di coppia resistente della turbina, devo scegliere una condizione ausiliaria altrimenti avrei infiniti modi per attraversare questo punto.

Si supponga di assegnare un profilo di coppia, ci sono 7 grandezze incognite (2 di tensione, 2 di corrente, posizione, velocità(?)), va aggiunta un'equazione scalare.

Una condizione di ottimo è far attraversare alla macchina sempre il flusso nominale al fine di sfruttare al massimo i circuiti magnetici, ho il minimo di corrente da fornire alla macchina.
Il momento è dato dall'ampiezza del flusso di rotore per la corrente di statore $i_{s,q}$.
La macchina è alimentabile solo dallo statore, il rotore è chiuso in corto circuito, le grandezze sono indotte, tradizionalmente nelle macchine elettriche, la macchina che aveva maggiore facilità di regolazione era la macchina in corrente continua ad eccitazione indipendente.
In questo caso la coppia era data dal prodotto del flusso di eccitazione (statore) e la corrente di armatura (corrente rotorica).

Utilizzando i convertitori si può controllare la corrente di statore mantenendo il flusso di rotore costante, entro certi limiti, dipende dalla velocità della macchina.
La condizione ausiliaria dell'algoritmo di controllo è dunque il flusso costante per velocità inferiori alla nominale, per velocità superiori invece sono costretto a deflussare, non potrei aumentare ulteriormente la tensione oltre il valore nominale per non danneggiare precocemente l'isolamento o danneggiarlo irrimediabilmente.
$V\simeq E=\Phi \omega\leq V_{n}$.

### Impostazione del problema
Le grandezze che si vogliono controllare sono il flusso di rotore e la corrente di statore in quadratura rispetto ad un certo orientamento.
Si scriverà il modello matematico della macchina asincrona solidale al flusso di rotore, ruotato di un certo angolo, supponendo di conoscere la posizione istantanea del flusso di rotore nel riferimento statorico.
Successivamente verrà ricavata questa fase dal modello della macchina.

Il flusso di rotore si sposta nel tempo, oltre a ruotare a velocità costante.
Ponendo un sistema di riferimento $d,q$ tale che l'asse reale sia allineato con il flusso di rotore, in questo modo sarà una grandezza reale.
L'asse in quadratura non avrà componenti del flusso, riportando tutte le grandezze nel nuovo riferimento, e si moltiplicano per $e^{-j \Psi}$ dove $\Psi$ è la fase di rotore.
In questo modo le due componenti della corrente di statore sono disaccoppiate, quella reale controlla il flusso, quella in quadratura controlla la coppia.

Si suppone che lo statore è controllato a corrente impressa opportuna, si scrive il rotore nel riferimento di rotore riportandolo nel sistema di riferimento rotante, ovvero moltiplicando prima per $e^{-j\Psi}$ e poi per $e^{-jp\theta_{r}}$.
Devo però scrivere tutte le variabili in termini di flusso di rotore e corrente di statore, successivamente si esegue il passaggio di fase.

Scomponendo le equazioni in parte reale e immaginaria si evidenziano poi le due dinamiche accoppiate per quanto riguarda la coppia e il flusso, si introdurrà infine il modello dello statore per passare dal controllo a corrente impressa alla tensione effettiva da fornire alla macchina.

**L'algoritmo di alimentazione** è il modello della macchina + una equazione ausiliaria.
È un controllo vettoriale perché controlliamo ampiezza e fase nel tempo di grandezze proporzionali alla corrente e al flusso.


# Equazione di rotore
Si vuole eseguire il cambio di sistema di riferimento dallo statore a rotore, si suppone di sovrapporre il piano assiale della macchina con quello dei componenti simmetrici.
Le grandezze che più comunemente vengono controllate sono il flusso di rotore e le correnti di statore.

Definizione flusso di rotore:
$$
\vec{\Phi}_{r}^s = L_{r}'\vec{I}_{r}^s + L_{m}\vec{I}_{s}^s
$$
Equazione di rotore:
$$
0 = R_{r}'\vec{i}_{r}' + L_{r}' \frac{d}{dt} \vec{i}_{r}' + L_{m}\frac{d}{dt} \left( \vec{i}_{s}^se^{-jp\theta_{r}} \right) = 
R_{r}'\vec{i}_{r}' + \frac{d}{dt}\vec{\Phi}_{r}'
$$
Si moltiplicano ambo i membri per due esponenziali che riportano al rotore e al riferimento rotante: $e^{jp\theta_{r}}e^{-j\Psi_{r}^s}$ ottenendo:
$$
0 = R_{r}'\vec{i}_{r}'e^{jp\theta_{r}}e^{-j\Psi_{r}^s} + e^{jp\theta_{r}}e^{-j\Psi_{r}^s}\frac{d}{dt}\vec{\Phi}_{r}'
$$
si portano gli esponenziali nella derivata:
$$
e^{jp\theta_{r}}e^{-j\Psi_{r}^s}\frac{d}{dt}\vec{\Phi}_{r}' =
\frac{d}{dt}\left[ \vec{i}_{r}'e^{jp\theta_{r}}e^{-j\Psi_{r}^s} \right] - (jp\omega_{r}-\omega )\vec{\Phi}_{r}'e^{jp\theta_{r}}e^{-j\Psi_{r}^s} = 
\frac{d}{dt}\vec{\Phi}_{r}' + j(\omega-p\omega_{r})\vec{\Phi}_{r}'
$$
con $\omega=\frac{d}{dt}\Psi_{r}^s$.
Si riscrive l'equazione nel nuovo sistema di riferimento rotante:
$$
0 = R_{r}'\vec{i}_{r}' + \frac{d}{dt}\vec{\Phi}_{r} + j(\omega-p\omega_{r})\vec{\Phi}_{r}
$$
si ricorda che
$$
\vec{i}_{r} = \frac{1}{L_{r}'}\left( \vec{\Phi}_{r} - L_{m}\vec{i}_{s} \right)
$$
e quindi:
$$
\frac{d}{dt} \vec{\Phi}_{r} + j(\omega-p\omega_{r})\vec{\Phi}_{r} + \sigma_{r}\vec{\Phi}_{r} = \sigma_{r}L_{m}\vec{i}_{s}
$$
con $\sigma_{r}=\frac{R_{r}'}{L_{r}'}$ e $k_{r}=\frac{L_{m}}{L_{r}'}$.

Proiettando in parte reale e immaginaria si ottiene un sistema di due equazioni, ricordando il flusso solidale al sistema di riferimento e dunque con componente solo reale.
$$
\vec{i}_{s} = i_{sd} + ji_{sq}\qquad \vec{\Phi}_{r}=\phi
$$
si ricava:
$$
\left\{
\begin{aligned}
0 &= -\sigma_{r}L_{m}i_{sd} + \sigma_{r}\phi_{r} + \frac{d}{dt}\phi_{r} \\
0 &= -\sigma_{r}L_{m}i_{sq} + (\omega-p\omega_{r})\phi_{r}
\end{aligned}
\right.
$$
Se $i_{sd}$ è costante nel tempo, essa è pari al flusso di rotore, superata la dinamica, dunque la componente di asse diretto di statore mantiene il flusso costante se essa è costante.
Controllando questa corrente si impone il valore del flusso al valore desiderato.

La seconda equazione è un legame algebrico tra la velocità, il flusso e la corrente in quadratura.

# Equazione di statore
Si sviluppano le equazioni di statore:
$$
\begin{aligned}
\vec{V}_{s}^s &= R_{s}\vec{i}_{s}^s + L_{s} \frac{d}{dt} \vec{i}_{s}^s + L_{m} \frac{d}{dt}\left( \vec{i}_{r}'e^{jp\theta_{r}} \right) \\
\vec{V}_{s}^s &= R_{s}\vec{i}_{s}^s + L_{s} \frac{d}{dt}\vec{i}_{s}^s + L_{m} \frac{d}{dt}\vec{i}_{r}^s \\
&\text{trasformazione nel riferimento rotante} \\
\vec{V}_{s}^se^{-j\psi_{r}^s} &= R_{s} \vec{i}_{s}^se^{-j\psi_{r}^s} + L_{s}e^{-j\psi_{r}^s} \frac{d}{dt}\vec{i}_{s}^s + L_{m}e^{-j\psi_{r}^s} \frac{d}{dt}\vec{i}_{r}^s \\
&\text{portando l'esponenziale nella derivata} \\
\vec{V}_{s} &= R_{s}\vec{i}_{s} + L_{s}\frac{d}{dt} \vec{i}_{s} + j\omega L_{s} \vec{i}_{s} + L_{m} \frac{d}{dt} \vec{i}_{r} + j\omega L_{m}\vec{i}_{r} \\
&\text{ponendo } \vec{i}_{r} = \frac{1}{L_{r}'}\left( \vec{\Phi}_{r}-L_{m} \vec{i}_{s} \right) \\
\vec{V}_{s} &= R_{s}\vec{i}_{s} + L_{s} \frac{d}{dt} \vec{i}_{s} + j\omega L_{s} \vec{i}_{s} + \frac{L_{m}}{L_{r}'} \frac{d}{dt} \vec{\Phi}_{r} - \frac{L_{m}^2}{L_{r}'}\frac{d}{dt}\vec{i}_{s} + \frac{j\omega L_{m}}{L_{r}'}\Phi_{r} - \frac{j\omega L_{m}^2}{L_{r}'}\vec{i}_{s} \\
\vec{V}_{s} &= R_{s}\vec{i}_{s} + \sigma_{s}L_{s} \frac{d}{dt} \vec{i}_{s} + j\omega \sigma_{s}L_{s} \vec{i}_{s} + k_{r} \frac{d}{dt} \vec{\Phi}_{r} + j\omega k_{r}\vec{\Phi}_{r}
\end{aligned}
$$
Avendo posto, per l'ultima equazione: 
$$
\left\{
\begin{aligned}
\sigma_{s} &= L_{s} \left( 1- \frac{L_{m}^2}{L_{s}L_{r}'} \right)\\
k_{r}&= \frac{L_{m}}{L_{r}'}
\end{aligned}
\right.
$$

La tensione impressa nel sistema di riferimento rotante è pari alla somma delle cadute più i due termini di tensione indotta trasformatorica più il termine mozionale $j\omega L_{m}\vec{i}_{r}$.
Ancora una volta si scompone la corrente nelle due componenti diretta e in quadratura, ottenendo un'equazione reale ed una immaginaria:
$$
\begin{aligned}
v_{sd} &= r_{s}i_{sd} + \sigma_{s}L_{s} \frac{d}{dt}i_{sd} + k_{r} \frac{d}{dt} \Phi_{r} - \omega \sigma_{s}L_{s}i_{sq}\\
v_{sq} &= r_{s} i_{sq} + \sigma_{s}L_{s} \frac{d}{dt} i_{sq} + \omega \sigma_{s}L_{s}i_{sd} + \omega k_{r}\Phi_{r}
\end{aligned}
$$

In questo caso le equazioni non possono essere disaccoppiate, i termini di caduta resistivi e trasformatorici si trovano sullo stesso asse mentre i termini mozionali agiscono sull'asse opposto.

Queste equazioni possono essere utilizzate sia per calcolare i valori da fornire alla macchina, sia per misurare le grandezze di stato.

# Momento della coppia
È una grandezza scalare, è invariante rispetto ai sistemi di riferimento:
$$
T_{m}=\frac{3}{2}pL_{m}\mathrm{Im}\left\{ \vec{i}_{s}^s \vec{i}_{r}^{s*} \right\} = \frac{3}{2} p \frac{L_{m}}{\dot{L}_{r}} \mathrm{Im} \left\{ \vec{i}_{s}^s e^{-j\Psi_{r}^s} \left( \vec{\Phi}_{r}^{s*} - L_{m}\vec{i}_{s}^{s*} \right)\right\} = \frac{3}{2}p \frac{L_{m}}{\dot{L}_{r}}\mathrm{Im}\left\{ \vec{i}_{s}\vec{\Phi}_{r}^* \right\}
$$
dunque l'unica parte immaginaria è quella della corrente:
$$
T_{m} = \frac{3}{2}pk_{r}\phi_{r}i_{sq}
$$
dove $\phi_{r}$ è il modulo.
Assieme alla prima equazione realizza il disaccoppiamento tra flusso di rotore e corrente di statore, come ciò che avviene in una macchina a corrente continua ad eccitazione indipendente.

(controllo a orientamento di campo del flusso di rotore indiretto)


## Condizione ausiliaria completa
Si considerala condizione di funzionamento limite per il flusso:
$$
\vec{\Phi}_{r} = f(\omega_{r}) = \left\{ 
\begin{aligned}
\vec{\Phi}_{r,n} &\qquad 0\leq \omega_{r} \leq \omega_{r,n}\\
\frac{\vec{\Phi}_{r,n}}{\omega_{r,n}} \frac{1}{\omega_{r}} &\qquad \omega_{r} > \omega_{r,n}
\end{aligned}
\right.
$$
Il modello della strategia di controllo si calcola sempre ad anello aperto, si trascura in prima ipotesi ad esempio la saturazione del circuito magnetico. Per avere un sistema robusto dal punto di vista del controllo, il sistema deve rispondere a variazioni dei riferimenti in maniera efficace.
Per fare ciò è utile utilizzare un sistema in retroazione, ad esempio mediante un controllo in cascata.

Il modello feed-forward verrà utilizzato inoltre per calcolare grandezze non direttamente misurabili.
Si usano ad esempio gli *osservatori di stato* che permettono la stima dello stato del sistema mediante questi modelli.

Queste equazioni permettono la realizzazione del [[Controllo di velocità di tipo indiretto|controllo della macchina asincrona]].
