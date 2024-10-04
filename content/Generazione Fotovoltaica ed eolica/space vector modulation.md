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

