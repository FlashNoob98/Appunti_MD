Il controllo digitale appartiene alla teoria secondo la quale si può controllare un sistema analogico mediante un [[Schede a microcontrollore|dispositivo digitale]], si può demandare la legge di controllo ad un calcolatore.
I segnali utilizzati sono digitali.
I controlli digitali hanno vari vantaggi:
- Flessibilità, la possibilità di fornire funzioni di controllo anche non lineari mediante righe di codice, senza dover riconfigurare un circuito
- Scalabilità: si può ampliare facilmente l'algoritmo di controllo, l'unico limite è lo spazio di memoria sul controllore
- Versatilità: possibilità di integrare altre funzioni nel dispositivo di controllo come monitoraggio, supervisione, diagnostica e comunicazione tra varie periferiche.
- Robustezza: elevata reiezione del rumore e dei disturbi esterni sui segnali monitorati
- Economicità: il prezzo dei microcontrollori tende sempre a diminuire.

Bolzen: controllo a tempo discreto
Digital controller in power electronics (Padova)

RIvedi trasformata Z
Definita su successioni numeriche:
$$
X(z) = Z\{x[k]\} = \sum_{k=0}^{+\infty} x[k]z^{-k} = x[0] + x[1]z^{-1} + \dots + x[h]z^{-h} + \dots
$$
Proprietà di ritardo:
$$
Z\{x[k-1]\} = \sum_{k=0}^{+\infty} x[k-1]z^{-k} = \sum_{h=0}^{+\infty} x[h]z^{-(h+1)} = z^{-1}X(z)
$$
Proprietà di anticipo:

DTFT - Discrete Time Fourier Transform

Least significant bit: quanto, quantifica la minima variazione del segnale in ingresso.
L'errore di quantizzazione può essere di $\pm \frac{1}{2}LSB$ dunque si riduce all'aumentare del numero di bit.

Il legame fondamentale tra il segnale digitale e quello analogico è dato dal legame tra $\omega$ e $\theta$, ovvero
$$
\theta = \omega T_{c} = 2 \pi f T_{c} = 2 \pi \frac{f}{f_{c}} = 2 \pi \nu
$$
dove $T_c$ è il tempo di campionamento.

Se si campiona un segnale sinusoidale con passo $T_c$, si ricostruisce lo stesso segnale in ritardo di $\frac{T_c}{2}$. 

# Sintesi del controllore digitale
Si riconduce il controllore come un sistema lineare tempo invariante lineare, il suo modello differenziale può essere analizzato in forma algebrico mediante la *Z-transform* e in forma razionale fratta.
Antitrasformando nel dominio del tempo, l'uscita all'istante $k$ è combinazione lineare degli ingressi e delle uscite precedenti $k-\nu$, il controllore memorizza un totale di $2\nu+1$ valori.

Esistono due principali metodi per sintetizzare un regolatore digitale, la **sintesi diretta** in cui si discretizza il modello continuo $G(s)$ e lo si trasforma in un sistema equivalente a tempo discreto $\tilde{G}(z)$, successivamente si realizza nel dominio del tempo il regolatore discreto.
In alternativa la **sintesi indiretta**, più semplice, si realizza prima il controllore nel tempo continuo per rispettare le caratteristiche, poi lo si discretizza.

Si consideri ad esempio un regolatore integrale:
$$
\frac{d}{dt}y = u \Leftrightarrow \frac{Y(s)}{U(s)} = \frac{1}{s}
$$
Esistono vari metodi per discretizzare l'integrale, Eulero avanti o Eulero inidetro sono i più semplici, si approssima il valore in ogni periodo $T_s$ pari a quello assunto all'inizio o alla fine dell'intervallo discreto.
In alternativa c'è il metodo dei trapezi, o *tustin*, ovvero integrazione trapezoidale, è un'approssimazione di ordine 1, si considera l'integrazione della secante tra i due punti all'estremità di ogni periodo.

Trasformando le equazioni alle differenze dei tre metodi, si ottengono tre differenti funzioni di trasferimento:
$$
\begin{aligned}
- \ &s\rightarrow  \frac{{z-1}}{T_{c}}\ (\text{FE}) \\
- \ &s\rightarrow \frac{{z-1}}{zT_{c}}\ (\text{BE}) \\
- \ &s\rightarrow \frac{2}{T_{c}}\frac{{z-1}}{z+1} (\text{TU})
\end{aligned}
$$
Alcune discretizzazioni potrebbero però tagliare alcuni poli del sistema, si potrebbe avere, a causa di una mancata accuratezza di discretizzazione, uno *shifting* della frequenza massima misurata ad esempio.

Fissato il tempo di campionamento $T_c$ è fissata la pulsazione di Nyquist.

Si vuole modellare un controllore PI, ovvero $K_{P}+\frac{K_{I}}{s}=\frac{K_I}{s} \left( 1  + \frac{s}{\omega_{z}} \right)$ con $\omega_{z}=\frac{K_{I}}{K_{P}}$.
Mantenendo elevata la distanza tra la pulsazione $\omega_{z}$ e quella di Nyquist si mantiene una buona approssimazione tra il modello discreto e quello continuo, al limite se $\omega_{\text{Nyquist}}\geq 50\omega_{z}$ allora i modelli quasi coincidono.

Solitamente si usano sempre i metodi di Backward Euler e Tustin, poche volte il Forward Euler. 
Si parla di *compressione* in frequenza, alle altre frequenze c'è una grande differenza tra la funzione di trasferimento del regolatore a tempo continuo e a tempo discreto.
Ovvero la funzione di trasferimento a tempo discreto è traslata in avanti rispetto a quella a tempo continuo.
Se si vuole avere l'errore nullo, tra i due modelli, in una certa frequenza (non si può mai avere in tutto lo spettro) si può utilizzare la trasformazione di Tustin modificata ed effettuare il *pre-warping*:
$$
s \to R\left(\frac{\tilde{\omega}}{\frac{2}{T_{c}}\tan\left( \frac{\tilde{\omega}T_{c}}{2} \right)} \frac{2}{T} \frac{e^j\tilde{\omega}T_{c-1}}{ej\omega T_{c}+1}\right) = R(j\tilde{\omega})
$$
Può essere richiesta nel caso in cui si cerchino prestazioni più elevate ad una certa frequenza.

Se si vuole discretizzare l'intera catena SISO di controllo si hanno i seguenti tre step:
- Campionamento dell'errore: $E(e^{j\omega T_{c}}) \simeq\frac{{1}}{T_{c}}E_{a}(j\omega)$ in banda base
- Controllo digitale: $D(e^{j\omega T_{c}} )=\tilde{R}(e^{j\omega T_{c}})e^{-j\omega T_{c}}E(e^{j\omega T_{c}})$
- PWM digitale: $V_{MO} = T_{c}e^{-j\omega \frac{T_{c}}{2}}D(e^{j\omega T_{c}})$
Complessivamente:
$$
\frac{V_{MO}(j\omega)}{E_{a}(j\omega)} =\tilde{R}(e^{j\omega T_{c}})e^{-j \frac{3}{2}}\dots
$$
È sempre introdotto un ritardo nel sistema di controllo digitale, è fondamentale scegliere opportunamente il tempo di campionamento, evitare il fenomeno di frequency warping e inoltre scegliere la massima frequenza di switching dei componenti, minore della massima frequenza ammissibile del convertitore.
Al massimo se la PWM è double update deve essere la frequenza del controllore pari al doppio della frequenza di switching dei componenti.


Nella libreria Simscape Electrical, two-level-converter si utilizza il model type **Switching function** per il convertitore.
Simulink > Dashboard > Edit per creare un campo editabile per modificare un parametro eventuale della workspace o di SImulink.

SI imposta il riferimento di corrente dall'esterno, si moltiplica per $\omega*t$ e si generano le tre fasi.
Un PI non annulla però l'errore su un ingresso sinusoidale ma solo al gradino, quindi il controllore PI mi fornisce un errore residuo, che aumenta all'aumentare della frequenza.
Anche a 50Hz ho comunque un ritardo.

Se si passa nel riferimento di Clarke, si calcola il componente simmetrico di una grandezza omopolare..
Dunque la tensione del centro stella, in un sistema a tre fili, non entra nella dinamica della corrente.
Moltiplicando ambo i membri dell'espressione per una rotazione $e^{-j\theta}$ si ottiene un riferimento in componente diretta e in quadratura.
In questo caso la compensazione avviene sia con la contro fem che con i *termini mozionali* $j\omega L$..

# Controllore risonante
Si piazza un polo alla frequenza delle correnti da controllare nel carico, ovvero la pulsazione dei riferimenti.
$$
\vec{i}^* = {I}_{d}e^{j\omega_{0} t} + I_{i}e^{-j\omega_{0} t}
$$
posso usare un controllore di questo tipo:
$$
\frac{1}{s-j\omega_{0}}+ \frac{1}{s+j\omega_{0}} = \frac{2s}{s^2+\omega_{0}^2}
$$
Si ottiene un controllore a banda passante con un picco elevato ad $\omega_{0}$, l'errore di corrente viene fornito ad un $K_p$ e un $K_{i}$ di questo secondo controllore.
In MATLAB la funzione *c2d* mi permette di discretizzare la funzione di trasferimento.
Anche in questo caso all'aumentare della frequenza si ha un peggioramento del regolatore a causa della discretizzazione.
Si può fare un pre-warping per avere un regolatore che coincida con quello a tempo continuo alla frequenza di risonanza.
Si annulla nuovamente l'errore.
