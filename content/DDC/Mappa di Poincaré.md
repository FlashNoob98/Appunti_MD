È un iperpiano in cui si interseca la traiettoria di stato del convertitore, si può verificare il raggiungimento
del regime quando queste intersezioni restano costanti nell'iperpiano.

Utile per il controllo di un sistema, soprattutto nel controllo digitale la mappa può rappresentare il campionamento dello stato del sistema con un certo intervallo periodico $T_s$.
Il campionamento può avvenire mediante l'utilizzo di una *rampa periodica* di periodo $T_s$, il segnale digitale sarà alto fin quando il valore fisico sia superiore al valore della rampa, raggiunta eventualmente l'intersezione esso torna a 0 fino alla fine del periodo.

Si può formalizzare la rampa di periodo $T$ con:
$$
\text{tri}_{T}(t) = \frac{t}{T} - \text{int}\left( \frac{t}{T} \right)
$$
dove $\text{int}$ è una funzione che restituisce la parte intera dell'argomento.

Si può utilizzare la funzione di *Heaviside* per realizzare l'onda quadra di ampiezza variabile:
$$
u\left( t,\vec{x} \right)=H[du-\text{tri}_{T}(t)]
$$
Questa tipologia di campionamento prende il nome di *switching asimmetrica* dato che l'istante di tempo in cui viene acquisito il campione varia al variare della sua ampiezza.

Si possono realizzare *mappe stroboscopiche* se il campionamento avviene all'inizio di ogni periodo in cui avvenga un'intersezione oppure una *mappa stroboscopica* se l'acquisizione avviene a prescindere dall'avvenuta intersezione.

