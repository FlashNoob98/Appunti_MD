Si vuole ricavare la media di ordine $k$ della funzione gradino $u$, è pari ad 1 per $t<=t_{on}$ e 0 altrimenti.
$$
\begin{aligned}
\langle u \rangle_{k} &= \frac{1}{T}\int_{0}^Tu(\tau)e^{-jk\omega \tau}d\tau = \frac{1}{T}\int_{0}^{t_{{on}}} e^{-jk\omega \tau}d\tau = \frac{1}{-j\omega Tk}\left[e^{-j\omega \tau} \right]_{0}^{t_{{on}}} = \\
&=\frac{1}{-j \frac{2\pi}{T} Tk}\left[e^{-j \frac{2\pi}{T}k\tau}\right]_{0}^{t_{{on}}} = \frac{j}{2k\pi}\left(e^{-j2k\pi d}-1\right) = \frac{j}{2k\pi}\left[\cos(2k\pi d) - j\sin(2k\pi d) -1 \right] = \\
&= \frac{\sin(2k\pi d)}{2k\pi} + j\left[\frac{\cos(2k\pi d)}{2k\pi} - \frac{1}{2k\pi}\right] = M_{k}+ jN_{k}
\end{aligned}
$$
Si sono considerate le sostituzioni $\omega=\frac{2\pi}{T}$ e $d=\frac{t_{{on}}}{T}$.
Considerando che il termine costante "1" non ha armoniche si ottengono le medie per i due valori $\langle u\rangle_{k}=M_{k}+jN_{k}$ e $\langle 1-u\rangle_{k} = -(M_{k}+jN_{k})$.
