Sia dato un ponte monofase a tiristori, total-controllato, composto da 4 tiristori.
Essendo il componente di switching non completamente controllato, non si può far coincidere lo spazio di switching con quello di controllo, si definirà una funzione di switching dipendente dallo stato e dal tempo.

In particolare nel ponte monofase total-controllato ogni coppia di tiristori conduce sempre per un periodo di $\pi$ in CCM, non è però garantito che la conduzione sia esclusiva per ogni gamba, si può avere un certo angolo $\mu$ di *commutazione* durante il quale tutti e quattro i tiristori conducono.
Dunque in questo caso ogni coppia conduce per un periodo $\pi+\mu$, e dunque $\mu$ è proprio il periodo in cui c'è conduzione condivisa.

La funzione di switching in questo caso riguarderà lo stato di conduzione del componente e non solo il segnale di comando ad esso associato. Ad esempio nel caso in cui ci sia commutazione, l'interdizione di una coppia di tiristori è determinata dall'andata in conduzione dell'altra. Per convertitori che commutano alla frequenza di rete (50Hz) non è più trascurabile questa commutazione.

Ad esempio il valore medio di tensione sul carico in assenza di commutazione:
$$
V_{0} = \frac{2}{\pi} \sqrt{ 2 }V\cos\alpha
$$
mentre con un'induttanza di commutazione $L_{c}$ si ha una caduta:
$$
V_{x} = \frac{2}{\pi} \omega L_{c}I_{0}
$$
che espressa in funzione dell'angolo $\mu$ diventa:
$$
V_{x} = \frac{2}{\pi}\sqrt{ 2 }V \left[ \frac{\cos\alpha-\cos(\alpha+\mu)}{2} \right]
$$
Non è più valida la relazione $2^m\geq N$, vale ancora la condizione di complementarità dei segnali di switching ovvero:
$$
S_{T_{1}} + S_{T_{2}} = 1
$$

Considerando un generico carico $RL$, indicando con $i_{S}$ la corrente assorbita dalla rete, $L_{c}$ l'induttanza in serie al generatore e $i_{D}$ la corrente nel carico, si presenta l'equazione differenziale della maglia di conduzione:
$$
\begin{aligned}
V_{S} - L_{c} \frac{di_{S}}{dt} - L \frac{di_{D}}{dt}  - Ri_{D} &= 0 \\
\text{Durante }T_{1}\text{ le due correnti} &\text{ coincidono} \\
V_{S} - (L_{c}+L) \frac{di_{D}}{dt} - Ri_{D} &= 0\\
\frac{d}{dt}i_{D} &= \frac{V_{S}-Ri_{D}}{L+L_{c}}
\end{aligned}
$$
il modello dinamico si riconduce ad un'equazione del primo ordine valida da $\alpha$ a $\pi$.
Analogamente per $\pi<\omega t\leq \pi+\alpha$ la corrente $i_{S}$ avrà cambiato verso rispetto al carico (ma sarà anche diventata negativa) e quindi $i_{S}=-i_{D}$ implica che:
$$
\frac{d}{dt}i_{D} = \frac{-V_{S}-Ri_{D}}{L+L_{c}}
$$
Tutto ciò è valido in CCM con angolo di commutazione nullo (Come faccio ad avere commutazione nulla se ho considerato proprio la $L_{c}$?)

Aggiungendo l'ipotesi di complementarietà si ricava un [[modello dinamico alle configurazioni]] globalmente valido di ordine 1:
$$
\begin{aligned}
\frac{d}{dt}i_{D} &= \frac{S_{1}V_{S}-S_{2}V_{S}-Ri_{D}}{L+L_{c}} \\
&= \frac{V_{S}(2S_{1}-1)-Ri_{D}}{L+L_{c}}
\end{aligned}
$$
con $S_{1}+S_{2}=1$ i segnali di switching.

In caso di angolo $\mu$ di commutazione
$$
\mu = \arccos\left[ \cos\alpha-\frac{I}{I_{\text{cc}}} \right]-\alpha
$$
si avranno due maglie di corrente durante la commutazione, ad esempio dopo un tempo $\alpha$, si impulsa $T_1$, con $T_{2}$ che era precedentemente in conduzione:
$$
\left\{
\begin{aligned}
-L \frac{d}{dt}i_{D}-Ri_{D}&=0\\
V_{S} - L_{c} \frac{d}{dt}i_{S_{c}} &=0
\end{aligned}\right.
$$
ovvero riscrivendo in funzione dei valori di $\mu$, il modello durante le due commutazioni diviene:
$$
\left\{
\begin{aligned}
\frac{d}{dt}i_{D}&= - \frac{R}{L}i_{D}(u_{1}+u_{2})\\
\frac{d}{dt}i_{S_{c}} &= \frac{V_{S}}{L_{c}}(u_{1}+u_{2})
\end{aligned}\right.
$$
Durante la commutazione invece il modello diventa del secondo ordine.
In DCM il tempo $S_{1}$ si riduce di $\mu_{1}$ e analogamente $S_{2}$ si riduce di $\mu_{2}$.
$$
\left\{
\begin{aligned}
\frac{d}{dt}i_{D} &= \frac{v_{S}(S_{1}-u_{1})-v_{S}(s_{2}-u_{2})-Ri_{D}[S_{1}-u_{1}+S_{2}-u_{2}]}{L+L_{c}} - \frac{Ri_{D}(u_{1}+u_{2})}{L}\\
\frac{d}{dt}i_{sc} &= \frac{v_{S}}{L_{c}}(u_{1}+u_{2})
\end{aligned}
\right.
$$
raccogliendo i termini:
$$
\left\{
\begin{aligned}
\frac{d}{dt}i_{D} &= \frac{v_{S}[2S_{1}-1-u_{1}+u_{2}]-Ri_{D}[1-(u_{1}+u_{2})]}{L+L_{c}} - \frac{Ri_{D}(u_{1}+u_{2})}{L}\\
\frac{d}{dt}i_{sc} &= \frac{v_{S}}{L_{c}}(u_{1}+u_{2})
\end{aligned}
\right.
$$
mettendo in relazione la corrente dell'alimentazione con quella del carico
$$
i_{s} = i_{sc}(u_{1}+u_{2}) + i_{d}[2S_{1}-1-(u_{1}+u_{2})]
$$
si può scrivere il modello globale in forma matriciale:
$$
\frac{d}{dt}
\begin{bmatrix}
i_{D}\\ \\ i_{sc}
\end{bmatrix}  =
\begin{pmatrix}
\frac{-v_{S}-Ri_{D}}{L+L_{c}} \\ \\ 0
\end{pmatrix} +
\begin{pmatrix}
\frac{2V_{s}}{L+L_{c}} & \frac{-V_{s}+Ri_{D}}{L+L_{c}} - \frac{Ri_{D}}{L} & \frac{v_{S}+Ri_{D}}{L+L_{c}}-\frac{Ri_{D}}{L}\\  \\
0 & \frac{v_{S}}{L_{c}} & \frac{v_{S}}{L_{c}}
\end{pmatrix}
\begin{pmatrix}
S_{1}\\ u_{1}\\ u_{2}
\end{pmatrix}
$$

# [[Modello ROAM]]
Si può sostituire il carico a corrente impressa con un carico $RL$, la dinamica della corrente nel carico sarà:
$$
\frac{d}{dt}i_{0} = \frac{v_{s}[(2S_{1}-1)-u_{1}+u_{2}]-Ri_{0}[1-(u_{1}+u_{2})]}{L+L_{c}} - \frac{Ri_{0}}{L}(u_{1}+u_{2})
$$
mentre quella di commutazione:
$$
\frac{d}{dt} i_{sc} = \frac{V_{s}}{L_{c}}(u_{1}+u_{2})
$$
La caduta di tensione induttiva:
$$
V_{x} = \frac{2}{\pi} \omega L_{c}I_{0}
$$
dunque il valore medio di tensione sul carico:
$$
\langle v_{0} \rangle_{0} = \frac{2}{\pi} \sqrt{ 2 }V\cos\alpha - \frac{2}{\pi}\omega L_{c}I_{0} 
$$
ma $I_{0}$ è il valor medio di corrente e per la sua stima andrebbero calcolati i valori medi di $u_{1}$ e $u_{2}$ che dipendono invece dallo stato del sistema e sono discontinue.

Se l'induttanza di carico $L$ è molto maggiore rispetto a quella di commutazione $L_{c}$, inoltre la corrente di commutazione persiste per un tempo certamente inferiore al periodo del sistema di $20ms$ (se alimentato a 50 Hz).

Se calcola la media esatta del modello:
$$
\frac{d}{dt}\langle i_{0} \rangle_{0} = \frac{\langle V_{S}(2S_{1}-1) \rangle_{0} }{L+L_{c}} +\frac{\langle V_{S}(u_{2}-u_{1}) \rangle_{0} }{L+L_{c}} - \frac{\langle Ri_{D} [1-(u_{1}+u_{2})] \rangle_{0} }{L+L_{c}} - \frac{\langle R(u_{1}+u_{2})i_{D} \rangle_{0} }{L}
$$
si esegue la media di ordine $k$ sulla funzione di comando:
$$
\langle 2S_{1}-1 \rangle_{k} = \frac{J}{(2k-1)\pi} [e^{-j(2k-1)\pi}-1]
$$
la media di ordine 1:
$$
\langle 2S_{1} -1\rangle_{1} = \frac{J(-2)}{\pi}e^{j\alpha} = \frac{2}{\pi}\left[ \sin\alpha-j \frac{2}{\pi}\cos\alpha \right] 
$$
Per quanto riguarda i termini di commutazione invece:
$$
\begin{aligned}
\langle u_{1} \rangle_{0} &= \frac{u_{1}}{2\pi} \\
A_{1} & = \frac{2}{2\pi} \int_{0}^{2\pi} u_{1}(\omega t) \cos \omega t\ d\omega t = \frac{1}{\pi}\int_{\alpha}^{\alpha+\mu_{1}} \cos \omega t \ d\omega t = \frac{\sin(\alpha+\mu_{1})-\sin\alpha}{\pi} \\
B_{1} & = \frac{2}{2\pi} \int_{0}^{2\pi} u_{1}(\omega t) \sin \omega t\ d\omega t = \frac{1}{\pi}\int_{\alpha}^{\alpha+\mu_{1}} \sin \omega t \ d\omega t = \frac{\cos\alpha-\cos(\alpha+\mu_{1})}{\pi} \\
\langle u_{1} \rangle_{1} &= \frac{A_{1}-jB_{1}}{2} = \frac{\sin(\alpha+\mu_{1})-\sin\alpha}{2\pi} - \frac{j\cos\alpha+j\cos(\alpha+\mu_{1})}{2\pi} 
\end{aligned}
$$
Per $\langle u_{2} \rangle_{1}$ il ragionamento è analogo ma l'intervallo di integrazione diventa $[\alpha+\pi, \alpha+\pi+\mu_{2}]$:
$$
\langle u_{2} \rangle_{1} = \frac{\sin\alpha-\sin(\alpha+\mu)}{2\pi} - \frac{j[\cos(\alpha+\mu_{2})-\cos\alpha]}{2\pi}
$$
Per quanto riguarda la tensione di alimentazione, è presente solo la prima armonica:
$$
\langle V_{s} \rangle_{1} = \frac{1}{T} \int_{0}^T \sqrt{ 2 }V\sin \omega t \cdot e^{-j\omega t} dt = \frac{1}{\cancel{T}}\cdot \frac{\sqrt{ 2 }}{2j}\cancel{T} = -j \frac{\sqrt{ 2 }}{2}V
$$
Si può quindi calcolare il seguente prodotto:
$$
\begin{aligned}
\langle V_{s}(2S_{1}-1) \rangle_{0} &= \langle V_{s} \rangle_{1}\langle 2S_{1}-1 \rangle_{-1} + \langle V_{s} \rangle_{-1}\langle 2S_{1-1} \rangle_{1} = \\
&= 2\left( -\frac{\sqrt{ 2 }V}{2} \right) \left( -\frac{2}{\pi} \cos\alpha\right) = \frac{2}{\pi}\sqrt{ 2 }V\cos\alpha
\end{aligned}
$$
con qualche passaggio in più si calcola anche
$$
\begin{aligned}
\langle V_{s}(u_{2}-u_{1}) \rangle_{0} &= \langle V_{s} \rangle_{1} \langle u_{2}-u_{1} \rangle_{-1} + \langle V_{s} \rangle_{-1}\langle u_{2}-u_{1} \rangle_{1} =  \\
&=\left( -\frac{\sqrt{ 2 }}{2}V\cdot {2} \right)\left( \frac{2\cos\alpha - \cos(\alpha+\mu_{1})-\cos(\alpha+\mu_{2})}{2\pi} \right)=\\
&= -\sqrt{ 2 }V \frac{2\cos\alpha-\cos(\alpha+\mu_{1})-\cos(\alpha+\mu_{2})}{2\pi} 
\end{aligned}
$$

Unendo i vari termini si riporta la media esatta del modello:
$$
\begin{aligned}
\frac{d}{dt} \langle i_{0} \rangle_{0} &= \left[ \frac{2}{\pi}\sqrt{ 2 }V\cos\alpha - \sqrt{ 2 }V\left[ \frac{2\cos\alpha-\cos(\alpha+\mu_{1})-\cos(\alpha+\mu_{2})}{2\pi} \right] \right] \frac{1}{L+L_{c}} - \\
&- \frac{R\langle i_{0} \rangle_{0} }{L+L_{c}} + \cancel{\frac{R\langle i_{0} \rangle_{0} }{L+L_{c}}\left( \frac{\mu_{1}+\mu_{2}}{2\pi} \right)}
-\cancel{\frac{R\langle i_{0} \rangle_{0} }{L+L_{c}}\left( \frac{\mu_{1}+\mu_{2}}{2\pi} \right)}
\end{aligned}
$$
Per rimuovere i termini in $\mu$ si calcola la corrente nella sorgente, a regime:
$$
\frac{d}{dt}i_{sc} = \frac{V_{s}}{L}\Rightarrow \int_{-\langle i_{0} \rangle_{0} }^{+\langle i_{0} \rangle_{0} } d i_{sc} = \int_{\alpha}^{\alpha+\mu_{1}} \frac{V_{s}}{\omega LC} d\omega t = 2\langle i_{0} \rangle_{0} = \frac{\sqrt{ 2 }V}{\omega L_{c}}[\cos\alpha-\cos(\alpha+\mu_{1})] 
$$
analogamente nel periodo $[\pi+\alpha,\pi+\alpha+\mu_{2}]$ si ottiene:
$$
2\langle i_{0} \rangle_{0} = \frac{\sqrt{ 2 }V}{\omega L_{c}}[\cos\alpha-\cos(\alpha+\mu_{2})] 
$$
A regime i due termini di commutazione sono identici $\mu_{1}=\mu_{2}=\mu$ dunque:
$$
2\omega L_{c} \langle i_{0} \rangle_{0} = \frac{\sqrt{ 2 }V}{\omega L_{c}} [\cos\alpha-\cos(\alpha+\mu)]
$$
Sostituendo nel termine generale:
$$
\frac{d}{dt} \langle i_{0} \rangle_{0} =\frac{\frac{2}{\pi}\sqrt{ 2 }V\cos\alpha-\frac{2}{\pi}\omega L_{c}\langle i_{0} \rangle_{0} }{L+L_{c}} - \frac{R\langle i_{0} \rangle_{0} }{L+L_{c}}
$$
A regime periodico $\frac{d}{dt}\langle i_{0} \rangle_{0}=0$ si ricava quanto già ottenuto in un precedente corso:
$$
R\langle i_{0} \rangle_{0}=V_{0} = \frac{2}{\pi}\sqrt{ 2 }V\cos\alpha-\frac{2}{\pi}\omega L_{c}I_{0} 
$$
.