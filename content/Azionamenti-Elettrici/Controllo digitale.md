Il controllo digitale appartiene alla teoria secondo la quale si può controllare un sistema analogico mediante un dispositivo digitale, si può demandare la legge di controllo ad un calcolatore.
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