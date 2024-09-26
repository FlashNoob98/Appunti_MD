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
ovvero pari alla differenza di potenziale tra i due dispersori, si può sfruttare il PSE per calcolare il potenziale sui due dispersori, utilizzando la formula precedente:
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
