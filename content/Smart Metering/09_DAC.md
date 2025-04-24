La linea TEN prevede l'abilitazione del trigger, il dato va dal DHR al DOR, nel DHR inseriamo la tensione desiderata/quanto, ad esempio per ottenere 0,75V il quanto è 3/4095=0,000732, dunque il DHR sarà 0,75/0,000732=1024.

Il dato finirà dal DHR al DOR in automatico dopo qualche colpo di clock in assenza di trigger

# Generazione forma d'onda
Una forma d'onda ad esempio sinusoidale si descrive nel continuo ad esempio mediane una funzione seno.
Nel microcontrollore possiamo solo fornire una forma d'onda campionata, in un numero finito di punti, dunque una successione di campioni.
$$
V(t_{i}) = V_{max}\sin\left( \frac{2\pi t_{i}}{T} \right)
$$
se il campionamento è uniforme i campioni distano tutti $dt$, pari a $\frac{T}{N_{pp}}$ dove $N_{pp}$ è il numero di punti per periodo, maggiore è il numero di punti e maggiore sarà la risoluzione con la quale è definita la curva.
$$
V({i}) = V_{max}\sin\left( \frac{2\pi \cdot i}{N_{pp}} \right)
$$
non si ha più il valore del periodo nella funzione, posso assegnare una forma d'onda e poi impostare la frequenza variando con un timer la velocità con la quale si susseguono i campioni.

Per definire una sinusoide dobbiamo fornire un offset di 2048 (1.5V) per generare la parte negativa della sinusoide, Vmax sarà dunque anch'essa 2048.

$\frac{2\pi}{N_{pp}}$ sarà il $dx$ della sinusoide, un incremento unitario.
```
x=0;
dx = 2pi/Npp;

for (i=0;i<Npp;i++){
y(i) = 2048 + 2048*sin(x);
x = x + dx;
}
```
Poi richiamo un timer con base di tempi $dt=\frac{T}{Npp}$, dunque ad ogni UIF del timer incremento la variabile del DAC.

Il DAC1 si trova sul BUS APB1, il dato passa dal DHR al DOR dopo un colpo di clock dell'APB1.
Quando si seleziona invece una modalità di trigger (TEN=1) allora dovrò attendere un segnale di trigger per aggiornare il dato.

DAC1OUT1 è PA4, è accanto a PA2, quindi si possono collegare con un jumper il DAC con l'ingresso dell'ADC su PA2.

