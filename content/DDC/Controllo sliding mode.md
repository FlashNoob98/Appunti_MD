Sfruttando il lemma di Ljapunov si vuole imporre una determinata traiettoria o un regime al sistema dinamico, si ricerca dunque una superficie $\Sigma$ tale che:
$$
\Sigma:\left\{ \vec{x}\in\mathbb{R}^n: e(x)=\sigma(x) = \vec{x}-\vec{x}_{d}=0 \right\}
$$
Questa superficie divide lo spazio in due sottospazi, si vuole forzare lo stato del sistema a rimanere sulla superficie $\Sigma$.
La legge di controllo deve prevedere due forzamenti diversi al fine di spostare lo stato del sistema su $\Sigma$ in base alla direzione in cui questo è deviato, si può avere il fenomeno di *chattering* per il quale il sistema oscilla intorno alla traiettoria desiderata ma non riesce a convergere in maniera puntuale.

Un sistema non lineare presenta delle discontinuità, queste possono essere di ordine 0 se la funzione è semplicemente discontinua, di ordine 1 se è discontinua la sua derivata, vi saranno cambi bruschi della curvatura.

Il sistema può essere rappresentato mediante due diverse funzioni se si trova sopra o sotto la superficie di controllo, ad esempio $F^+$ ed $F^-$, si ha la condizione di *crossing* nel passaggio da un sistema all'altro se il sistema attraversa la superficie di controllo senza convergere ad essa.
Questa condizione si può descrivere mediante le derivate di Lie, in questa condizione infatti esse sono concordi, ovvero:
$$
\begin{aligned}
\mathcal{L}F^+&<0 & \mathcal{L}F^+&>0\\
\mathcal{L}F^-&<0 & \mathcal{L}F^-&>0
\end{aligned}
$$
prese due differenti regioni (ovvero tali per cui il verso di attraversamento è diverso) le derivate sono concordi.

Si verifica la *condizione di sliding*, ovvero il sistema converge alla superficie se le due derivate sono discordi:
$$
\mathcal{L}F^+<0\qquad\mathcal{L}F^->0
$$
La funzione $F_{S}$ deve essere tangente alla superficie di sliding, ovvero
$$
F_{S} = (1-\alpha)F^-  +\alpha F^+ \qquad \alpha \in[0,1]
$$

Se le derivate di Lie sono discordi in senso opposto si ha invece la *condizione di repulsività* ovvero il sistema tende ad allontanarsi dalla superficie:
$$
\mathcal{L}F^+>0\qquad\mathcal{L}F^-<0
$$

Un sistema può presentare comportamenti differenti nelle due regioni individuate dalla superficie di sliding, analogamente queste differenze possono essere usate proprio per determinare la superficie di sliding.

Si consideri il seguente sistema di esempio:
$$
\left\{
\begin{aligned}
A\vec{x} - b ,\ C^T\vec{x}>0\\
A\vec{x} + b,\ C^T\vec{x}<0
\end{aligned}
\right.
$$
con le seguenti matrici:
$$
A=
\begin{bmatrix}
0 & -1  \\
1 & -1
\end{bmatrix}
\qquad
B=
\begin{bmatrix}
1  \\
1
\end{bmatrix}\qquad
C=
\begin{bmatrix}
0  \\
1
\end{bmatrix}
$$
La superficie di sliding sarà quella in cui $\sigma\left( \vec{x} \right)=0$:
$$
\sigma\left( \vec{x} \right) =C^T\vec{x}=0\cdot x_{1}+1x_{2} = x_{2}
$$
Dunque si individua la superficie di sliding:
$$
\sigma\left( \vec{x} \right)=0\Rightarrow x_{2}=0
$$

Le due funzioni a monte e valle della superficie sono:
$$
F^+=\begin{bmatrix}
-x_{2}-1 \\
x_{1}-x_{2}-1
\end{bmatrix}\qquad
F^-=\begin{bmatrix}
-x_{2}+1 \\
x_{1}-x_{2}+1
\end{bmatrix}
$$
Si possono ora calcolare le derivate di Lie per entrambe le funzioni:
$$
\mathcal{L}F^+(\sigma) = \begin{pmatrix}
0 & 1
\end{pmatrix} F^+ = x_{1}-x_{2}-1
$$
viceversa
$$
\mathcal{L}F^-(\sigma) =x_{1}-x_{2}-{3}
$$
Si sostituiscono i punti che annullano la derivata, ovvero $x_{2}=0$ e si ottengono le tre condizioni:
- Crossing
$$
\left\{
\begin{aligned}
x_{1}-&1>0\\
x_{1}+&1>0
\end{aligned}
\right.\qquad \bigcup\quad \left\{
\begin{aligned}
x_{1}-&1<0\\
x_{1}+&1<0
\end{aligned}
\right. 
$$

- Sliding 
$$
\left\{
\begin{aligned}
x_{1}-&1<0\\
x_{1}+&1>0
\end{aligned}
\right.\qquad \Rightarrow -1<x_{1}<1\to \Sigma\text{ reg. di sliding}
$$
  
- Repulsivo  
$$ 
\left\{
\begin{aligned}
x_{1}-&1>0\\
x_{1}+&1<0
\end{aligned}
\right.\qquad \nexists\ \ x_{1}
$$
  
Si definisce come campo vettoriale di sliding quello che nasce dalla continua commutazione dei due campi, si ricorda la definizione convessa di funzione di sliding:
$$
F_{S}=(1-\alpha)F^- + \alpha F^+
$$
Si calcola la derivata di Lie:
$$
\begin{aligned}
&\nabla \sigma \cdot[(1-\alpha)F^- +\alpha F^+]=0\\
&\nabla \sigma \cdot(1-\alpha)F^- + \nabla \sigma \cdot\alpha F^+=0\\
&(1-\alpha)\mathcal{L}F^-(\sigma) + \alpha\mathcal{L}F^+(\sigma) = 0\\
&\mathcal{L}F^-(\sigma) - \alpha\mathcal{L}F^-(\sigma) + \alpha\mathcal{L}F^+(\sigma)=0
\end{aligned}
$$
Si cerca il valore $\hat{\alpha}$ per il quale $\mathcal{L}F_{s}(\sigma)=0$:
$$
\hat{\alpha} = \frac{-\mathcal{L}F^-(\sigma)}{\mathcal{L}F^+(\sigma)-\mathcal{L}F^-(\sigma)}
$$
Con tale valore di $\alpha$ il sistema converge e insegue la superficie.
Il sistema va forzato in maniera opportuna al fine di ottenere il fenomeno di sliding, considerata la forma affine nel controllo:
$$
\begin{aligned}
\dot{x} &= f(x)  + g(x)u \\
u &= \left\{\begin{aligned}
u^+ \text{ se } \sigma(x)>0\\
u^- \text{ se } \sigma(x)<0
\end{aligned}
\right. \\
\dot{x} &= \left\{\begin{aligned}
f(x)+g(x)u^+ \text{ se } \sigma(x)>0\\
f(x)+g(x)u^- \text{ se } \sigma(x)<0
\end{aligned}
\right.
\end{aligned}
$$
Si impone la convergenza mediante le derivate di Lie nella forma affine:
$$
\begin{aligned}
&\mathcal{L}F^+(\sigma)<0\text{ e } \mathcal{L}F^-(\sigma)>0 \\
&\nabla \sigma \cdot[f(x)+ g(x)u^+]<0\\
&\nabla \sigma \cdot[f(x)+ g(x)u^-]>0
\end{aligned}
$$
Si vuole formulare la condizione di attrattività in una forma più compatta:
$$
\dot{\sigma}(x) = \frac{\partial \sigma}{\partial t} = \frac{\partial\sigma}{\partial x} \cdot \frac{\partial x}{\partial t} = \nabla \sigma \cdot\dot{x} = \mathcal{L}_{f}(\sigma)
$$
L'attrattività si verifica se:
$$
\begin{aligned}
\sigma &>0 & \rightarrow & &\dot{\sigma}<0\\
\sigma &<0 & \rightarrow & &\dot{\sigma}>0
\end{aligned}
$$
in maniera compatta:
$$
\sigma \cdot \dot{\sigma} < 0
$$

Esiste una relazione equivalente tra la stabilità di sigma e l'attrattività del campo, si cerca
una funzione di sigma tale che valga la condizione di Ljapunov
$$
V(\sigma(x)):\text{Ljapunov}
$$
Ad esempio con la funzione di prova $V=\frac{1}{2}\sigma^2(x)$, il punto di equilibrio $\sigma^*(x)=0$, la funzione è di classe $\mathbb{C}^1$, $V(\sigma^*(x))=V(0)=0$, $V(\sigma)>0$, resta da verificare la derivata, in questo caso:
$$
\dot{V}(\sigma)\leq{0}\ ? 
$$
si vede che la derivata è proprio la definizione compatta dell'attrattività ovvero:
$$
\dot{V} = \frac{\cancel{2}}{\cancel{2}} \sigma \dot{\sigma} = \sigma \dot{\sigma} \leq 0
$$
Vale la relazione che se un sistema è asintoticamente stabile è anche attrattivo e viceversa.

Va garantito anche l'intrappolamento del sistema mediante un ingresso equivalente $u_{eq}$ tale che:
$$
\dot{x}=f(x)+g(x)u_{eq}=F_{s} : \mathcal{L}F_{s}(\sigma)=0
$$
ovvero
$$
\begin{aligned}
&\nabla \sigma  \cdot[f(x)+g(x)u_{eq}]=0\\
&\nabla \sigma  \cdot f(x) + \nabla \sigma \cdot g(x)u_{eq}=0 \\
&\mathcal{L}_{f}(\sigma)  + \mathcal{L}_{g}(\sigma)u_{eq}=0
\end{aligned}
$$
si ricava il forzamento equivalente:
$$
u_{eq}\leq - \frac{\mathcal{L}_{f}(\sigma)}{\mathcal{L}_{g}(\sigma)}
$$
Imponendo l'esistenza del rapporto si ricava il criterio per determinare la superficie incognita $\sigma_{x}$:
$$
\nabla \sigma \cdot g\neq {0}
$$
la funzione $g$ è necessariamente diversa da zero altrimenti il sistema sarebbe non controllabile, non è però sufficiente avere $\nabla \sigma\neq 0$ ma va verificata la condizione sul prodotto, ad esempio:
$$
g=\begin{pmatrix}
1 \\ 0
\end{pmatrix},\ \sigma(x) = x_{2}-x_{2d}
$$
dove $x_{2d}$ è il valore desiderato per la seconda variabile di stato; il loro prodotto è nullo:
$$
\mathcal{L}_{g}(\sigma) = \begin{pmatrix}
0 & 1
\end{pmatrix}\cdot
\begin{pmatrix}
0 \\ 1
\end{pmatrix} = 0
$$
In tal caso è necessario ricercare una differente superficie di sliding:
$$
\begin{aligned}
\sigma_{2}(x) =P_{1}(x_{1}) + P_{2}(x_{2}-x_{2d})
\end{aligned}
$$
dunque
$$
\mathcal{L}g(\sigma_{2}) = \begin{pmatrix}
P_{1} & P_{2}
\end{pmatrix}\cdot \begin{pmatrix}
1 \\ 0
\end{pmatrix} = P_{1} \neq 0
$$
Riassumendo, dato un sistema di esempio:
$$
\begin{aligned}
\vec{\dot{x}} = \vec{f}\left( \vec{x} \right) + \vec{g}\left( \vec{x} \right)u
\end{aligned}
$$
con il sistema così definito:
$$
\vec{\dot{x}} = \begin{pmatrix}
\dot{x}_{1} =& f_{1}\left( \vec{x} \right)+g_{1}\left( \vec{x} \right)u \\
\dot{x}_{2} =& x_{1} \\
\vdots \\
\dot{x}_{n} =& x_{n}-1
\end{pmatrix}
$$
la traiettoria desiderata è $\vec{x}=0$.

Riassumendo:
 1. Scelta di $\sigma(x)$, deve rispettare la condizione di trasversalità:

$$
\sigma(x) = P^Tx - p_{1}x_{1}
+p_{2}x_{2} +\dots + p_{n}x_{n}
$$
 con $P^T=(P_{1}\ \ P_{2}\ \ \dots\ \ P_{n})$. La condizione di trasversalità implica che:
 $$
\mathcal{L}_{g}(\sigma) = \nabla \sigma \cdot g \neq 0 \Rightarrow P^T\cdot g\neq {0}
$$

 2. Calcolo di $u_{eq}$:
$$
u_{eq} = \frac{-\mathcal{L}_{f}(\sigma)}{\mathcal{L}_{g}(\sigma)} = -\frac{P^Tf(x)}{P^Tg(x)}
$$
3. Assegnazione dei coefficienti di $P^T$:
$$
\mathrm{Re}\left\{P^T\right\}<0
$$
4. Verifica dell'attrattività:
   ricordando che:
$$
\dot{\sigma}(x)= \frac{\partial \sigma}{\partial x}\frac{\partial x}{\partial t} = P^T\dot{x}
$$
si ricava la condizione di attrattività:
$$
\dot{V}(\sigma(x))<0 \Longleftrightarrow \sigma \cdot \dot{\sigma} = \sigma \cdot[P^T\cdot\dot{x}] = \sigma P^T\left[ \vec{f}(x)+\vec{g}(x)u \right]<0
$$

Dunque la funzione $u$ sarà composta da due termini, il primo che verifica la trasversalità alla superficie di sliding, la seconda che verifica l'attrattività:
$$
u = u_{eq}+u_{sw}\Rightarrow \sigma \cdot P^T\cdot[f(x)+g(x)(u_{eq}+u_{sw})]<0
$$
La componente switchata può essere scelta con il seguente criterio:
$$
u_{sw} = -\frac{1}{P^Tg(x)}u\cdot\mathrm{sign}(\sigma)
$$
dunque:
$$
\begin{aligned}
&\sigma \cdot P^T\left[ f(x)+g(x)\left( -\frac{P^Tf(x)}{P^Tg(x)}  - \frac{1}{P^Tg(x)} u \cdot\mathrm{sign}(\sigma) \right) \right]<0\\
&\sigma \cdot \left[ \cancel{P^Tf(x)}+\cancel{P^Tg(x)}\left( -\frac{\cancel{P^Tf(x)}}{\cancel{P^Tg(x)}}  - \frac{1}{\cancel{P^Tg(x)}} u \cdot\mathrm{sign}(\sigma) \right) \right]<0
\end{aligned}
$$
si semplifica in
$$
-\sigma u\cdot\mathrm{sign}(\sigma)=-u|\sigma|<0
$$
dunque la $u_{sw}$ scelta verifica l'attrattività per ogni $\sigma$.
Se non si conosce il sistema si può effettuare una stima di $u$ per garantire l'attrattività, si verifica infatti che
$$
-u|\sigma| + \sigma P^T(f_{\text{reale}}-f_{\text{stimata}}) < 0 \Rightarrow u|\sigma|>  \sigma P^T(f_{\text{reale}}-f_{\text{stimata}})
$$
una $u$ sufficientemente grande permette di compensare l'errore nella stima della funzione del sistema.
Al fine di garantire l'attrattività è inoltre necessario che la funzione di controllo equivalente:
$$
0 < u_{eq} < 1
$$
Inoltre la superficie di sliding $\hat{\Sigma}$ deve essere compresa nel dominio $\Omega$ della funzione del sistema:
$$
\hat{\Sigma} \cap \Omega\neq {0}
$$
Va infine verificato il seguente sistema:
$$
\left\{\begin{aligned}
\frac{d}{dt} \vec{x} &=f\left( \vec{x} \right) + g\left( \vec{x} \right) u_{eq}\\
\sigma\left( \vec{x} \right)&= 0\ \ ;\ \ \frac{d\sigma}{dt}=0
\end{aligned}
\right.
$$
## Sliding mode sul Buck converter
Si analizza l'uso del controllo sliding mode con un convertitore Buck.

<center>

![[buck_converter.svg]]

</center>

Il modello in forma affine nel controllo è il seguente:
$$
\left\{\begin{aligned}
\frac{d}{dt} i_{L}&= \frac{V_{s}}{L} u - \frac{v_{C}}{L}\\
\frac{d}{dt} v_{C} &= \frac{i_{L}}{C} - \frac{v_{C}}{RC}
\end{aligned}
\right.
$$
ovvero
$$
\frac{d}{dt}\begin{bmatrix}
x_{1} \\  x_{2}
\end{bmatrix} = \begin{bmatrix}
-\frac{x_{2}}{L}   \\ \frac{x_{1}}{C} - \frac{x_{2}}{RC}
\end{bmatrix} + \begin{bmatrix}
\frac{V_{s}}{L}  \\ 0
\end{bmatrix}u
$$
a regime si hanno le seguenti relazioni in valor medio, ricordando che la derivata di $v_{C}$ si assume nulla:
$$
\langle i_{L} \rangle = \frac{\langle v_{C}\rangle}{R} \qquad ; \qquad 
\langle v_{C} \rangle =V_{s}d
$$
si vuole imporre un certo valore di $v_{C}$ ma controllarlo mediante la corrente $i_{L}$:
$$
\langle v_{C} \rangle =x_{2}^* \Rightarrow x_{1}^* = \frac{x_{2}^*}{R}
$$
dunque la superficie di sliding sarà la seguente:
$$
\sigma\left( \vec{x} \right) = x_{1}-x_{1}^*
$$
Si verifica la condizione di trasversalità:
$$
\mathcal{L}_{g}(\sigma) = \langle \nabla\sigma,g \rangle = \begin{bmatrix}
1,0
\end{bmatrix}\cdot \begin{bmatrix}
\frac{V_{s}}{L} \\ 0
\end{bmatrix} = \frac{V_s}{L}\neq 0
$$
dato che $\nabla \sigma=(1,0)$.
Svolgendo la derivata si ricerca la funzione di controllo discontinuo:
$$
\begin{aligned}
\frac{d}{dt} \sigma\left( \vec{x} \right) &= \mathcal{L}_{\frac{d}{dt}\vec{x}}(\sigma) = \left\langle  \nabla\sigma, \frac{d}{dt}\vec{x}  \right\rangle =\\
&= \left\langle  \nabla\sigma,f\left( \vec{x} \right)  \right\rangle + \left( \left\langle  \nabla\sigma,g\left( \vec{x} \right)  \right\rangle  \right)\cdot u = \\
&= \mathcal{L}_{f}(\sigma) + \mathcal{L}_{g}(\sigma)u = -\frac{x_{2}}{L} +\frac{V_{s}}{L}u
\end{aligned}
$$
ovvero per $u=0$:
$$
\frac{d}{dt} \sigma(x) < 0 = -\frac{x_{2}}{2} \Rightarrow u^+ = 0
$$
invece per $u=1$:
$$
\frac{d}{dt}\sigma(x) > 0 \Rightarrow u^- = 1
$$
dato che $V_{s}\geq x_{2}\forall t$ , si può riassumere la funzione di controllo con:
$$
u = \frac{1}{2}\left[ 1-\text{sign}\left[ \sigma \left(  \vec{x} \right) \right] \right]
$$
Si calcola la $u_{eq}$ per verificare la stabilità:
$$
0<u_{eq} = -\frac{\mathcal{L}_{f}(\sigma)}{\mathcal{L}_{g}(\sigma)} = 
\frac{-\left( -\frac{x_{2}}{L} \right)}{\frac{V_{s}}{L}} = \frac{x_{2}}{V_{s}} <1
$$
dunque eccetto gli estremi, la $u_{eq}$ rispetta la condizione di attrattività, in particolare $\Sigma$ coincide con $\Omega$.
Il sistema resta intrappolato sulla superficie di sliding?
Si sostituisce la $u_{eq}$ nel modello del sistema:
$$
\frac{d}{dt}\begin{bmatrix}
x_{1} \\  x_{2}
\end{bmatrix} = \begin{bmatrix}
-\frac{x_{2}}{L}   \\ \frac{x_{1}}{C} - \frac{x_{2}}{RC}
\end{bmatrix} + \begin{bmatrix}
\frac{V_{s}}{L}  \\ 0
\end{bmatrix} \cdot\frac{x_{2}}{V_{s}} = \begin{bmatrix}
0 \\
\frac{x_{1}}{C} - \frac{x_{2}}{RC}
\end{bmatrix}
$$
ovvero si annulla la dinamica di $x_{1}$, ossia si trova sulla superficie di sliding; se si vuole annullare anche la dinamica di $x_{2}$:
$$
\frac{dx_{2}}{dt}= 0 \Rightarrow \frac{x_{1}}{\cancel{C}}=\frac{x_{2}}{R\cancel{C}}\Rightarrow x_{1}^* =i_{L}^* = \frac{x_{2}}{R}
$$
I vincoli strutturali per il funzionamento del convertitore prevedono che la corrente sia sempre maggiore di zero (ipotesi di CCM ad esempio) e che il valore massimo di corrente sia pari a $\frac{V_{s}}{R}$.
Si può quindi delimitare la regione nella quale si può disporre la superficie di sliding.

Se viceversa si volesse eseguire direttamente un controllo in tensione, ad esempio con una superficie di sliding del tipo:
$$
\sigma\left( \vec{x} \right) = x_{2}-x_{2}^*\Rightarrow \nabla \sigma= \begin{bmatrix}
0 & 1
\end{bmatrix}
$$
non si rispetterebbe l'ipotesi di trasversalità:
$$
\mathcal{L}_{g}(\sigma) = \begin{bmatrix}
0  &1
\end{bmatrix}\cdot \begin{bmatrix}
\frac{V_{s}}{L}  \\ 0
\end{bmatrix} = 0
$$
Resta il problema del chattering, il controllo mediante superficie di sliding non può avvenire a frequenza infinita ma deve comunque rispettare il limite imposto dai componenti reali. La funzione di controllo $u_{eq}$ è stata infatti ricavata a partire dal [[modello averaged]], si applica correttamente al modello ai valori istantanei solo per frequenze infinite.

Analogamente si può applicare tale controllo per il [[boost converter#Sliding mode|boost converter]].