La periferica timer permette di effettuare misure di tempo mediante un conteggio

Il processore ha un segnale di clock ad 8MHz con un contatore che conta i fronti di salita, accedendo al conteggio del contatore posso avere l'intervallo di tempo, moltiplicando il numero di impulsi per il Delta_t, conoscendo la frequenza di clock 8MHz > 125ns

Timer2 è l'unica periferica a 32bit, le altre sono a 16bit.
Il numero massimo di impulsi contabili saranno rispettivamente 2^32 e 2^16.

Nel reference manual timer6 e timer7 sono le più "semplici" da usare, funzionano solo da timer, le altre invece possono essere sfruttate per generare PWM

Il cuore della periferica è il registro di conteggio CNT, è in comunicazione con l'ARR auto reload register.
Inoltre il registro di conteggio è preceduto dal prescaler PSC.

Il dispositivo TIMER si può usare come base dei tempi, ovvero che mi avverta ogni volta che trascorre un certo intervallo di tempo Delta_T.
È una modalità leggermente diversa di funzionamento, è il timer che fornirà gli eventi di stop, comunico al contatore lo start e il contatore fornirà lo stop dopo l'intervallo di tempo prefissato.

La modalità counting è più semplice. Il numero massimo di conteggi è 2^16 -1 ovvero 65535 quando tutti i 16bit sono pari ad 1, l'impulso di clock successivo provoca l'overflow, il contatore si azzera segnalando mediante una linea di overflow. Dunque la massima durata di tempo misurabile sarebbe di circa 8ms.. sarebbe troppo poco anche per misurare una frequenza di rete.
Per questo motivo si introduce un divisore di frequenza tra il clock e l'unità di conteggio. Se ad esempio divido la frequenza per 2, ottengo gli impulsi distanti un periodo doppio, dunque 2Tck, posso contare circa 16ms con un singolo conteggio. Questo blocco divisore prende il nome di prescaler, restituisce il segnale di clock con un periodo aumentato di un certo fattore che dipende dal valore inserito nel registro di prescaler.

In realtà il valore di prescaler di default è 0, ma vuol dire che non altera la frequenza di clock, mentre se inseriamo 1 vuol dire che dimezziamo una sola volta la frequenza di clock.
$$
T_{CNT} = (PSC+1)\cdot T_{ck}
$$
Il prescaler è **bufferizzato**, se viene modificato durante un conteggio, diventerà effettivo solo dopo il primo overflow del contatore.
Per ogni periferica sono presenti i registri di controllo CR e quelli di status SR

CR1 è il bit counter enable bit, CEN, ovvero quello che abilita il conteggio, se lo modifichiamo da 1 a zero interrompiamo il conteggio.

Analogamente il prescaler è un registro a 16 bit e possiamo inserire qualsiasi valore tra 0 e 2^16 -1.

Per contare la base dei tempi devo inserire nel registro dei tempi (ARR) Delta_T/(Tck(PSC+1)) <= 65536

Per avere la migliore risoluzione possibile imposto ARR al valore massimo 65535 e calcolo il più piccolo valore di PSC:

$$
\Delta_{t} = \text{ARR}\cdot 125ns (\text{PSC}+1)
$$
Se il PSC ottenuto non è intero, devo ridurre ARR per ottenere un prescaler intero, altrimenti commetto errori di quantizzazione