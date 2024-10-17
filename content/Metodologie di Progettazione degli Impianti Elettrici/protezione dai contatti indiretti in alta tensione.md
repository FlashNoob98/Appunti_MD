Non ci si riferisce in questo caso a sistemi con tensione nominale superiore a 30kV ma anche ai sistemi di seconda categoria, con tensione nominale superiore a 1kV.

# Dispersori interrati
Si consideri un dispersore emisferico, se si avesse un dispersore di diversa forma si avrebbe un problema di interfaccia tra il dispersore e la superficie del terreno.
In questo caso l'andamento del potenziale, rispetto alla distanza dal dispersore è costante su superfici radiali, ha un andamento di tipo iperbolico all'aumentare della distanza:
$$
U(r) = \frac{\rho I}{2\pi r}
$$
Si considera il dispersore a resistività nulla e il suo potenziale varrà proprio
$$
U(r_{0}) = \frac{\rho I}{2\pi r_{0}}
$$
da cui il gradiente del potenziale:
$$
\frac{dU}{dr} = -\frac{\rho I}{2\pi} \frac{1}{r^2}
$$
Questa formula non cambia se si considera un dispersore più piccolo ma il potenziale sarà più alto.

Si può identificare un valore $U_{i}$ limite a distanza $r_{i}$:
$$
r_{i} = \frac{\rho I}{2\pi U_{i}}
$$
Si può identificare un'**area di influenza** per tutta la regione dove $r<r_{i}$ in cui si può considerare la sicurezza dovuta alle tensioni di passo o all'influenza che avrebbe il dispersore su altri dispersori dell'impianto di terra.

Maggiore è la resistività del terreno o il valore della corrente, tanto più aumenta il potenziale a pari distanza $r$, ovvero la curva sale verso l'alto e cresce l'area di influenza.
La corrente chiamata a disperdere è comunque data dal progetto, dipende dalle correnti differenziali da interrompere o delle correnti capacitive dei [[Sistema IT|sistemi IT]].

Nella realtà però il dispersore non è allineato con la superficie del terreno ma è un picchetto conficcato nel terreno, ad una certa profondità.
Per semplicità si suppone di avere una sfera posta ad una profondità $h$ dalla superficie, connesso mediante un conduttore isolato al nodo equipotenziale dell'impianto di terra.

Se si trovasse in un mezzo uniforme vi sarebbero delle linee sferiche equipotenziali ma si ha un problema all'interfaccia con l'aria, il problema va risolto mediante il metodo delle immagini, si pone un conduttore speculare anch'esso a distanza $h$ ma speculare rispetto alla superficie.

Anche la presenza del conduttore in realtà altera l'uniformità del terreno, nonostante si usi il metodo delle immagini, dunque si deve supporre che il raggio del dispersore sia molto più piccolo della distanza tra i dispersori reale e immagine.

Sia una corrente $I$ che si richiude nei dispersori, si vuole calcolare il potenziale in un generico punto $P$ caratterizzato da una distanza $r$ dall'asse che congiunge i due dispersori.
La distanza del punto $P$ dal dispersore sarà: $\sqrt{ h^2 + r^2 }$ e quindi il potenziale:
$$
U(P) = \frac{\rho I}{4\pi \sqrt{ h^2 +r^2}} + \frac{\rho I}{4\pi \sqrt{ h^2+r^2 }} = \frac{\rho I}{2\pi \sqrt{ h^2+r^2 }}
$$
sono presenti due termini a causa della presenza del dispersore immagine.
Il termine al denominatore dei primi due termini è la superficie della sfera di raggio $\sqrt{ h^2+r^2 }$.
Ancora una volta si calcola il gradiente:
$$
\frac{dU}{dr} = -\frac{\rho I}{2\pi} \frac{r}{(r^2+h^2)^{3/2}}
$$
dove $h$ si suppone fisso essendo la distanza alla quale si pone il dispersore.

Si supponga di avere una massa collegata al dispersore che disperda una certa corrente di guasto $I$, si vuole calcolare il potenziale in $r=0$ ovvero sopra il dispersore
$$
U(r=0)= \frac{\rho I}{2\pi h}
$$
ma il potenziale a cui si trova la massa è la stessa del dispersore, si suppone il collegamento mediante un conduttore con bassa impedenza rispetto al terreno, dunque
$$
U(E) = \frac{\rho I}{4\pi r_{0}} + \frac{\rho I}{4\pi(2h-r_{0})}
$$
Questo è il massimo valore che il potenziale può assumere rispetto a qualsiasi altro punto sul terreno.
In base alla distanza $P$ vi sarà una tensione $U_{vt}$ di contatto pari alla differenza tra $U_E$ e $U(P)$.
Al variare di $h$ varia $U_E$, al limite se $h=r_0$ con dispersore affiorante, ci si riconduce al caso del dispersore emisferico:
$$
U(E) = \frac{\rho I}{4\pi r_{0}} + \frac{\rho I}{4\pi r_{0}}
$$
In questo caso coincide con il valore massimo.
Il contatto è "sicuro" se ci si pone sul dispersore di terra, la differenza di potenziale tra la massa e il terreno è nulla, all'aumentare di $h$ e della distanza $r$ dal dispersore, aumenta la tensione di contatto a vuoto.

## Dispersori multipli
In questo caso la corrente disperde attraverso più dispersori, il potenziale è più alto nella regione compressa tra i due dispersori a causa della sovrapposizione degli effetti.
