Un controllo retroazionato che controlla la coppia della macchina a regime, mediante un controllo sulla corrente, imponendo una determinata tensione.
Non si tiene sotto controllo la transizione della macchina tra il regime corrente e quello di riferimento, ci si basa sull'ipotesi che le costanti di tempo elettriche siano più rapide di quelle meccaniche.

Si utilizza il circuito equivalente a $T$, con i parametri di statore $R_{s}$ e 
$X_{ds}$, la reattanza di mutua $X_m$ e i parametri di rotore $R'_{r}/s$ e $X'_{ds}$, questi parametri sono valutati alla frequenza nominale $\omega$ della macchina.
Dato che si vuole controllare la velocità della macchina andrà variata anche la $\omega$, per evidenziare il fatto che la $\omega$ sia un parametro del controllo della macchina si indicano gli elementi reattivi come il prodotto della frequenza per l'induttanza e non con i termini di reattanza (che assumono implicitamente un valore di $\omega$), dunque $\omega L_{s}$ e $\omega L'_{r}$.

Relazione della coppia:
$$
M_{e} = \frac{3p}{\omega} I_{r}^{'2} \frac{R'_{r}}{s}
$$
La coppia di riferimento può essere imposta dall'utente o da un regolatore di velocità.
Conviene esprimere la corrente in funzione della corrente assorbita di statore, usando la legge del partitore di corrente:
$$
\vec{I}_{r}'= \frac{j\omega L_{m}}{\frac{R_{r}'}{s}+j\omega L'_{r}}\vec{I}_{s} 
$$
si è definita l'induttanza totale di rotore: $L'_{r}=L_{m}+L'_{dr}$.
Si svolge il quadrato del rapporto:
$$
I_{r}^{'2} = \frac{s^2\omega^2L_{m}^{2}}{R_{r}^{'2}+(s\omega)^2L_{r}^{'2}}
$$
dunque la coppia
$$
M_{e} = \frac{3p}{\omega}I_{s}^2  \frac{s^2\omega^2L_{m}^2}{R_{r}^{'2}+(s\omega)^2L_{r}^{'2}} = 3pR_{r}' \frac{s\omega L_{m}^2}{R_{r}^{'2} +(s\omega)^2 R_{r}^{'2}}I_{s}^2
$$
Posso controllare la coppia variando il valore efficace di corrente o la sua frequenza, ma ho una sola equazione, dunque mi serve un'ulteriore condizione di vincolo, ad esempio posso usare la condizione MTpA ovvero Maximum Torque per Ampere, in cui si minimizza il valore efficace di corrente per minimizzare le perdite.

In alternativa si possono usare differenti approcci, si considera ad esempio il limite magnetico di saturazione del ferro, non si deve superare il flusso di saturazione, si avrebbe un aumento smisurato della corrente.
Si può imporre proprio il flusso nominale, ci si avvicina molto alla condizione di ottimo della corrente, sarà proprio la condizione utilizzata.

## Calcolo del flusso di statore
Si definisce il flusso di statore:
$$
\vec{\Phi}_{s} = L_{s}\vec{I}_{s} + L_{m}\vec{I}'_{r}
$$
con $L_{s}=L_{m}+L_{ds}$.

Il flusso di mutua:
$$
\vec{\Phi}_{m} = L_{m}\left( \vec{I}_{s}+\vec{I}'_{r} \right)
$$
e il flusso di rotore:
$$
\vec{\Phi}_{r} = L_{r}'\vec{I}'_{r} + L_{m}\vec{I}_{s}
$$
Si mantiene costante il flusso di statore ma il ragionamento può essere applicato a quello di mutua, viceversa per $\vec{\Phi}_{r}$ le formule sono più semplici.

La corrente di statore della fase $k$ esima:
$$
i_{s,k} = \sqrt{ 2 }I_{s}\cos\left( (s\omega+p\omega_{r})-\frac{2\pi}{3}(k-1) + \psi \right)
$$
in questo caso la fase $\psi$ si può trascurare dato che il controllo viene eseguito a regime, non controlliamo le componenti diretta e in quadratura e quindi il vettore spaziale di corrente ma solo il suo valore efficace e la pulsazione.

$$
\begin{aligned}
\vec{\Phi}_{s} &= L_{s}\vec{I}_{s} + L_{m}\vec{I}_{r}' = L_{s}\vec{I}_{s} - \left( \frac{j\omega L_{m}}{\frac{R_{r}'}{s}+j\omega L_{r}'} \right)\vec{I}_{s} = \\
&= \left( L_{s}-\frac{j\omega L_{m}^2}{\frac{R_{r}'}{s}+j\omega L_{r}'} \right)\vec{I}_{s} = \left(\frac{{\frac{R_{r}'}{s}L_{s}+j\omega L_{r}'L_{s}-j\omega L_{m}^2}L_{s}}{{\frac{R_{r}'}{s}+j\omega L_{r}'}}\right)\vec{I}_{s} = \\
&= \left(\frac{{\frac{R_{r}'}{s}L_{s}+ j\omega L_{s}( L_{r}'- L_{m}^2})}{{\frac{R_{r}'}{s}+j\omega L_{r}'}}\right)\vec{I}_{s} = \left(\frac{{{R_{r}'}L_{s}+ j\omega s L_{s}( L_{r}'- L_{m}^2})}{{{R_{r}'}+j\omega sL_{r}'}}\right)\vec{I}_{s} = \\
&= \left(\frac{{\frac{{R_{r}'}L_{s}}{L_{r}'}+ j\omega s \frac{L_{s}}{L_{r}'}( L_{r}'- L_{m}^2})}{{{\frac{R_{r}'}{L_{r}}}+j\omega s}}\right)\vec{I}_{s} = \left(\frac{{{\sigma_{r}L_{s}}+ j\omega s \frac{L_{s}}{L_{r}'}( L_{r}'- L_{m}^2})}{{{\sigma_{r}}+j\omega s}}\right)\vec{I}_{s}
\end{aligned}
$$
con $\sigma_{r}=\frac{R_{r}'}{L_{r}'}$

infine:
$$
\vec{\Phi}_{s} = \frac{\sigma_{r}+js\omega\Delta}{\sigma_{r}+js\omega}L_{s}\vec{I}_{s} \Rightarrow I_{s}^2 = \frac{1}{L_{s}^2} \frac{\sigma_{r}^2+(s\omega)^2}{\sigma_{r}^2 + (s\omega)^2\Delta^2}\Phi^2
$$
Si divide l'equazione della coppia per $L_{r}'^2$ ottenendo:
$$
M_{e} = 3pR_{r}' \frac{\frac{s\omega L_{m}^2}{L_{r}'^2}}{\sigma_{r}^2 + (s\omega)^2}I_{s}^2
$$
si definisce $k_{r}=\frac{L_{m}^2}{L_{r}'^2}$ ottenendo:
$$
M_{e} = \frac{3pR_{r}'}{L_{s}^2} \frac{{s\omega}K_{r}^2}{\sigma_{r}^2 + (s\omega)^2\Delta^2} \Phi_{s}^2
$$
imposto il flusso di statore pari a quello nominale si ricava il valore di $\omega$
per controllare la coppia.
Per $s\omega=0$ la coppia è nulla dato che la frequenza delle correnti di rotore è nulla e non ci sarebbe induzione, analogamente per $s\omega\to \infty$ la coppia è nulla per il rapporto tra infiniti di ordine differente.

Analogamente la corrente di statore $I_{s}$ per $s\omega=0$ e per $s\omega\to \infty$ è pari alla sola componente magnetizzante $\frac{\Phi}{L_{s}}$.

## Flusso di rotore
Si calcola il flusso di rotore:
$$
\begin{aligned}
\vec{\Phi}_{r} &= L_{m}\vec{I}_{s} - L_{r}' \frac{j\omega L_{m}}{\frac{R_{r}'}{s} + j\omega L_{r}'}\vec{I}_{s} = \frac{\frac{L_{m}R_{r}'}{s} + \cancel{j\omega L_{m}L_{r}'}-\cancel{j\omega L_{m}L_{r}'}}{\frac{R_{r}'}{s}+j\omega L_{r}'} \vec{I}_{s}=\\ &= \frac{L_{m}R_{r}'}{R_{r}' + j\omega sL_{r}'}\vec{I}_{s} = 
\frac{k_{r}R_{r}'}{\sigma_{r}+js\omega}\vec{I}_{s} \Rightarrow I_{s}^2 = \Phi_{r}^2 \frac{\sigma_{r}^2+(s\omega)^2}{k_{r}^2R_{r}^2}
\end{aligned}
$$
con $k_r=\frac{L_{m}}{L_{r}'}$
Si ricava nuovamente la coppia:
$$
M_{e} = 3p\cancel{R_{r}'} \frac{s\omega \cancel{k_{r}^2}}{\cancel{k_{r}^2}R_{r}'^{\cancel{2}}}\Phi_{r}^2 = 3p\frac{s\omega }{R_{r}'}\Phi_{r}^2
$$

ovvero la coppia è lineare con lo scorrimento.
La corrente tende ad infinito per $s\omega\to \infty$, il limite superiore è la sovra modulazione dell'inverter.
Questa condizione fornisce condizioni di utilizzo più semplici rispetto al flusso di statore costante.
Imporre il flusso di mutua costante pone risultati simili al flusso di statore costante.

Per controllare la macchina si ricava l'$s\omega$ di riferimento determinata la coppia e il flusso, determinato $s\omega$ si ricava la corrente di statore da imporre.
Per determinare $\omega$ si deve sommare $p\omega_{r}$ ad $s\omega$.

Ottenuti $\omega^*$ e $I_{s}^*$ di riferimento si devono calcolare i valori istantanei di riferimento per pilotare l'inverter.
La fase istantanea delle correnti è l'integrale di omega, si ottengono le tre fasi sottraendo $\frac{2\pi}{3}$ e $\frac{4\pi}{3}$ si calcola il coseno e si moltiplica per l'ampiezza $\sqrt{ 2 }I_{s}^*$, si ottengono le tre correnti di riferimento che vengono inviate ai regolatori di corrente, ad esempio tre regolatori PI.

L'uscita del regolatore PI è la tensione di riferimento della singola fase, va quindi modulata per ottenere i valori dei duty ratio per pilotare l'inverter.
In questo caso si può utilizzare una modulazione a sotto oscillazione sinusoidale, oppure si può usare direttamente un regolatore ad isteresi senza ricorrere alla modulazione PWM.
