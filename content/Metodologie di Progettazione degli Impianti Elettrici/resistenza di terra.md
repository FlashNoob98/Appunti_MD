L'elemento principale dell'impianto di terra è il **dispersore**, è un elemento metallico e serve a disperdere una certa corrente verso terra, definita dal seguente rapporto:
$$
R_{E} = \frac{U_{E}}{I}
$$
dove $U_E$ è la **tensione totale verso terra** e la $I$ la corrente da disperdere.
Il dispersore non ha nella realtà una forma semisferica ma cilindrica, in ogni caso si può utilizzare la semisfera per semplicità di calcolo.
Per simmetria geometrica la corrente sarà chiamata a disperdersi in maniera radiale rispetto al dispersore.

Sia $x$ una distanza radiale rispetto al dispersore, il campo elettrico nel terreno e nel punto $x$ sarà:
$$
\vec{E}(x) = -\nabla(U(x)) \Rightarrow E(x) = - \frac{d}{dx} U(x) \Rightarrow E(x)dx = -dU(x)
$$
Si vuole definire una tensione, dunque è necessario calcolare il potenziale, va risolta l'equazione differenziale, deve essere noto il campo elettrico, ricavabile con la legge di Ohm:
$$
E(x) = \rho J(x) = \frac{\rho I}{2\pi x^2}
$$
ad una generica distanza $x$ si ha una corrente che si è uniformemente distribuita (per ipotesi) in tutte le direzioni.

Si è ipotizzato che la forma del dispersore sia emisferico, nella realtà da una distanza di circa $3m$ in poi tale ipotesi è valida, inoltre si ipotizza che la resistività del terreno sia uniforme, così il campo.

Il campo sulla superficie del dispersore, di raggio $r$:
$$
E(x=r) = \rho\frac{ I}{2 \pi r^2}
$$
Si vuole calcolare il potenziale in un punto causato dalla dispersione della corrente nel terreno, dunque si integra il campo elettrico, quindi il gradiente del potenziale:
$$
U(x_{2}) - U(x_{1}) = \int_{x_{1}}^{x_{2}} dU(x) = -\frac{\rho I}{2\pi} \int_{x_{1}}^{x_{2}} \frac{1}{x^2} dx =- \frac{\rho I}{2\pi} \left[ \frac{1}{x} \right]_{x_{1}}^{x_{2}} = \frac{\rho I}{2\pi}\left( \frac{1}{x_{1}}-\frac{1}{x_{2}} \right)
$$

Si considera una semisfera di spessore $dx$ con la stessa forma del dispersore, posta ad una certa distanza dal dispersore, la sua resistenza infnitesima $dR$ sarà:
$$
dR = \frac{\rho dx}{2 \pi x^2}
$$
per ottenere dunque la resistenza di terra, si deve effettuare l'integrale da $r$ ad $\infty$ dove $r$ è il raggio del dispersore, l'infinito è il punto in cui si pone il potenziale nel calcolo della massima tensione di terra, per questo motivo ha senso calcolare la resistenza in questo modo.
$$
R_{E} = \int_{r}^{\infty} \frac{\rho }{2 \pi x^2}dx = -\frac{\rho}{2\pi}\left[ \frac{1}{x} \right]_{r}^{\infty} = \frac{\rho}{2\pi r}
$$
Anche in questo caso si può ricavare il potenziale a partire dalla resistenza e quindi al campo elettrico.

## Ridurre la resistenza di terra
Un valore troppo elevato di resistenza di terra non è utile per la sicurezza dell'impianto, si possono utilizzare più strategie per ridurre la resistenza come la dimensione e/o il numero dei dispersori, o la riduzione della resistività mediante modifica chimica del terreno.
L'aggiunta di soluzioni saline o argillose permettono di ridurre il valore di resistività.

## Combinazione di più dispersori
Si vuole studiare la differenza di potenziale tra due dispersori differenti collegati tra loro mediante un generatore per garantire una certa tensione tra loro. Si ha una certa corrente $I$ che li attraversa entrambi in versi opposti.
Siano i dispersori numerati 1 e 2 di raggio $r_1$ ed $r_2$, la tensione $E$ tra i dispersori sarà:
$$
E = U_{1} - U_{2} 
$$
ovvero pari alla differenza di potenziale tra i due dispersori, si può sfruttare il PSE (Principio di sovrapposizione degli effetti) per calcolare il potenziale sui due dispersori, utilizzando la formula precedente:
$$
U(x_{1}) - U(x_{2}) = \frac{\rho I}{2\pi}\left( \frac{1}{x_{1}} - \frac{1}{x_{2}} \right)
$$
Per il dispersore 1, la $x_1$ è pari ad $r_1$ mentre $x_2= D-r_{1}$ con $D$ la distanza tra i dispersori.
La corrente nei due dispersori ha segno opposto quindi:
$$
U_{1} = \frac{\rho I}{2\pi r_{1}} - \frac{\rho I}{2\pi(D-R_{1})}
$$
Analogamente per il potenziale $U_2$:
$$
U_{2} = \frac{\rho I}{2\pi(D-r_{2})} - \frac{\rho I}{2\pi r_{2}}
$$
La tensione $E$ è pari alla somma dei due termini:
$$
E = \frac{\rho I}{2\pi} \left[ \frac{1}{r_{1}} - \frac{1}{ D}-\frac{1}{D} +\frac{1}{r_{2}}\right] = \frac{\rho I}{2\pi}\left[ \frac{1}{r_{1}}-\frac{2}{D} + \frac{1}{r_{2}} \right]
$$
con $D\gg r$.
$$
E = \frac{\rho I}{2\pi r_{1}}+\frac{\rho I}{2\pi r_{2}} - \frac{\rho I}{\pi D}
$$
Il campo elettrico è legato ai campi generati dai semplici dispersori e diminuito di un termine inversamente proporzionale alla loro distanza $D$, a grandi distanze si può trascurare l'interferenza tra i dispersori.

## Coppia di dispersori collegati in parallelo
Si analizza il caso in cui una coppia di dispersori sia collegata in parallelo e posti a disperdere una certa corrente complessiva $I$.
Ciascun dispersore è attraversato da una corrente $I_1$ e $I_2$, la tensione di terra $U_E$ è pari alla resistenza di terra per la corrente:
$$
U_{E} = \frac{\rho}{2\pi r_{1}} I_{1} + \frac{\rho}{2\pi(D-r_{1})}I_{2} = \frac{\rho}{2\pi r_{1}} I_{1} + \frac{\rho}{2\pi D}I_{2}
$$
La resistenza del secondo dispersore è riferita rispetto al riferimento fissato nel primo dispersore.
Nei casi tipici $D\gg (r_{1},r_{2})$ dunque si può approssimare il secondo termine.

Si vuole generalizzare per $n$ dispersori:
$$
U_{E} = R_{11}I_{1} + R_{12}I_{2}\dots
$$
Si calcola il potenziale dovuto alla corrente nel secondo dispersore:
$$
U_{E} = \frac{\rho}{2\pi(D-r_{2})}I_{1} + \frac{ \rho}{2\pi r_{2}}I_{2} =\frac{\rho}{2\pi D}I_{1} + \frac{ \rho}{2\pi r_{2}}I_{2}= R_{21}I_{1} + R_{22}I_{2}
$$
Uguagliando le due relazioni:
$$
\left\{
\begin{aligned}
U_{E} &= R_{11}I_{1} + R_{12}I_{2} \\ U_{E} &=R_{21}I_{1}+R_{22}I_{2}
\end{aligned}
\right.
$$
La resistenza totale di terra è pari al rapporto tra la tensione totale di terra $U_E$ e la corrente dispersa $I$.
Si risolve il sistema con cramer:
$$
\left\{
\begin{aligned}
I_{1} &= \frac{U_{E}R_{22}-U_{E}R_{12}}{R_{11}R_{22}-R_{12}R_{21}} & =  U_{E}\frac{R_{22}-R_{12}}{R_{11}R_{22}-R_{12}R_{21}} \\
I_{2} &= \frac{U_{E}R_{11}-U_{E}R_{21}}{R_{11}R_{22}-R_{12}R_{21}}& =  U_{E}\frac{R_{11}-R_{21}}{R_{11}R_{22}-R_{12}R_{21}}
\end{aligned}
\right.
$$
Il denominatore è identico, è semplice sommare le correnti e raccogliere i termini:
$$
I = U_{E} \frac{R_{22}+R_{11}-R_{12}-R_{21}}{R_{11}R_{22}-R_{12}R_{21}}
$$
Immediatamente, invertendo questo rapporto si ottiene la resistenza di terra $R_T=\frac{U_{E}}{I}$.

All'aumentare di $D$ le resistenze "miste" $R_{12}$ e $R_{21}$ tendono ad essere piccole rispetto a $R_{11}$ e $R_{22}$, dunque la resistenza di terra diventa il parallelo delle resistenze mutue dei dispersori:
$$
R_{T} \simeq \frac{R_{11}R_{22}}{R_{11}+R_{22}}
$$

## Caso generico con $n$ dispersori
Posti $n$ dispersori in parallelo si hanno le seguenti espressioni:
$$
U_{E} = R_{11}I_{1}+R_{12}I_{2} + \dots +R_{1n}I_{n}
$$
in forma compatta con la forma matriciale:
$$
\begin{bmatrix}
U_{E} \\ \vdots\\ U_{E}
\end{bmatrix} = \begin{bmatrix}
 \text{} \\ R \\ \text{}
\end{bmatrix}\cdot
\begin{bmatrix}
I_{1} \\ \vdots \\ I_{n}
\end{bmatrix}\Rightarrow
\begin{bmatrix}
I_{1} \\ \vdots \\ I_{n}
\end{bmatrix} =  \begin{bmatrix}
 \text{} \\ G \\ \text{}
\end{bmatrix} \cdot \begin{bmatrix}
U_{E} \\ \vdots\\ U_{E}
\end{bmatrix}
$$
dove $G=R^{-1}$ la matrice delle conduttanze.
La corrente totale sarà la somma delle correnti $I_j$ dei singoli dispersori, dunque:
$$
I = \sum_{j=1}^n U_{E}\sum_{k=1}^n G_{j,k} = U_{E}
\sum_{j=1}^n \sum_{k=1}^n G_{j,k}
$$
dunque la resistenza di terra:
$$
R_{E} = \frac{U_{E}}{I} = \frac{1}{\sum_{j=1}^n \sum_{k=1}^n G_{j,k}}
$$
In questo caso è più difficile sostenere l'ipotesi di $D$ grande, dunque sono presenti anche le conduttanze mutue, non è detto che siano trascurabili e si possa calcolare la resistenza totale con la formula del parallelo.

La generica resistenza parziale si può calcolare con:
$$
R_{i,j} = \frac{\rho}{2\pi(D_{i,j}-r_{j})}\ ;\ R_{i,i}=\frac{\rho}{2\pi r_{i}}
$$
.
