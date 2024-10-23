# Metodi di avviamento di una macchina asincrona
Ci si pone il problema di avviare la macchina asincrona a causa delle elevate sovracorrenti (4-7 volte la nominale) che avvengono durante l'avviamento diretto.

Dal punto di vista termico nella maggior parte delle applicazioni non ha problemi, la macchina raggiunge lo scorrimento nominale in poco tempo.
Questa fase può essere però gravosa per la rete di alimentazione.
La temperatura massima degli avvolgimenti è quella tollerabile dagli isolanti, dipende dalla classe di isolamento, la maggio parte è in classe H quindi 180°C.

Si analizza il circuito ad $L$ di fase, si suppone che la macchina sia simmetrica.

Si ha una reattanza trasversale $X_m$, dovuta alla magnetizzazione.
In serie si ha una resistenza di statore, una reattanza di dispersione (totale) e una resistenza di rotore, riportata attraverso il fattore di scorrimento, la corrente di rotore è $\vec{I}_{r}$.
Il fasore di corrente di rotore varia con una frequenza pari a $s\omega$, coincide con la frequenza di rete solo quando il rotore è fermo (scorrimento unitario).

La curva di coppia varia da un valore pari alla coppia di avviamento, per la coppia di rovesciamento, fino a coppia nulla al sincronismo.
La coppia al rovesciamento è solitamente 2-3 volte la coppia nominale.

Alla velocità di sincronismo la corrente di statore è pari alla corrente magnetizzante $I_{\mu}$, solitamente tra il 30 e il 50% della nominale.
La corrente diminuisce dalla corrente di avviamento fino alla corrente magnetizzante quando si raggiunge il sincronismo, successivamente aumenta nuovamente nel funzionamento da generatore.

Per ridurre questa corrente all'avviamento si possono inserire in serie allo statore delle resistenze o degli induttori, si usano solitamente le resistenze se gli avviamenti sono poco frequenti o viceversa si possono usare degli induttori se si vogliono ottimizzare le perdite.

L'espressione della coppia:
$$
M_{e} = \frac{3p}{\omega} \frac{V_{s}^2}{\left( R_{s}+\frac{R'_{r}}{s} \right)^2 + X_{d,t}^2} \frac{R_{r}'}{s}
$$
lo scorrimento di rovesciamento:
$$
s_{k} = \frac{R_{r}'}{X_{d,t}}
$$
è solitamente il 10%.

La coppia di rovesciamento si calcola sostituendo lo scorrimento di rovesciamento:
$$
M_{k} = \frac{3p}{\omega} \frac{V_{s}^2}{2X_{d,t}}
$$

SI può trascurare la resistenza dello statore e considerare la coppia di avviamento:
$$
M_{e,\text{avv}} = \frac{3p}{\omega}\frac{V_{s}^2}{X_{d,t}^2}
$$
Dimezzando la tensione si riduce la coppia di 1/4.
Ottenuta la coppia minima, si calcola la corrente necessaria, si ricava la riduzione di tensione necessaria.

Esistono vari sistemi per variare l'alimentazione:
- Autotrasformatore, ha solitamente un rapporto di trasformazione costante
- Avviatore stella-triangolo, si riduce la corrente nella linea di $\sqrt{ 3 }$, la coppia di $1/3$.
- Soft-starter (sistema a TRIAC)
Il soft starter è costituito da un contattore, ovvero un attuatore elettromeccanico di potenza (simile al relee ma di potenza).
Un contattore viene rappresentato con dei cerchietti sui terminali di contatto.

Si ha a monte un contattore trifase che collega la linea, comandata da un'unica bobina.
Si dispone un altro contattore trifase sui morsetti "inferiori" della macchina.
Un terzo contattore trifase permette il collegamento a triangolo, va chiuso dopo aver aperto il contattore di centro stella, devo attendere un certo tempo prima di chiudere quello a triangolo per non mandare la linea in corto circuito.

