Il microcontrollore (MCU) è un dispositivo elettronico integrato su un singolo chip, nato come evoluzione del microprocessore per applicazioni *special purpose* di controllo digitale.
A differenza di un microprocessore, l'MCU integra al suo interno tutti gli elementi necessari al suo funzionamento: memoria di programma, memorie dati, clock, gestione interrupt, moduli di comunicazione, periferiche analogiche tipo ADC, DAC e PWM.
Interagisce con il mondo esterno tramite un programma residente nella propria memoria interna e attraverso numerosi pin specializzati o configurabili.
Sono disponibili in tre fasce di ampiezza del bus dati: 8, 16, 32 bit.
I microprocessori hanno capacità di calcolo estremamente ridotta rispetto ai tradizionali microprocessori
$$
\begin{matrix} 
&\text{Microcontrollore} & \text{Microprocessore}\\
\text{Velocità massima di clock } &200 MHz & 4 GHz  \\
\text{Capacità elaborativa in MegaFLOPS} & 200 & 5000  \\
\text{Potenza minima dissipata}&1mW & 50W
\end{matrix}
$$

Per *implementazione del software* si intende la **generazione del codice macchina** a partire da un linguaggio di programmazione:
- Stesura di un programma in *alto livello* come il C
- Compilazione del programma in un linguaggio a basso livello come l'*Assembly* da parte di un *compilatore* e successivamente assemblaggio in codice macchina eseguibile.
È possibile programmare direttamente tramite MATLAB, eventualmente a partire dallo schema Simulink e generare automaticamente il codice per il microcontrollore.
Tale modalità è utile per esigenze di *rapid prototyping* è possibile inoltre generare codice *standardizzato*.
Il modello Simulink viene tradotto in C e successivamente compilato e caricato sulla piattaforma di controllo.

Su una MCU possono essere presenti numerosi moduli, come la FPU ovvero Floating Point Unit, Trigonometric Math Unit, Viterbi, Complex Math e CRC Unit per l'esecuzione di algoritmi complessi come FFT, filtri ecc...
Ad ogni CPU è associata una CLA, Control Low Accelerator, indipendente a 32 bit per eseguire calcoli matematici onerosi in virgola mobile.
Ogni CPU ha 14 linee di interrupt di cui due riservate e 12 disponibili.
Un eventuale modulo di espansione PIE può multiplexare fino a 16 segnali di interrupt, su ogni linea per un totale di 16x12=192 segnali di interrupt gestibili da ogni CPU.

4 ADC indipendenti per la conversione a 12 o 16 bit di segnali analogici.
Ogni ADC presenta un circuito di Sample&Hold ed un multiplexer per il campionamento di 15 diversi canali di ingresso, il multiplexer esegue in successione i vari campionamenti.

L'operazione dell'ADC è gestita da 15 registri SOC, ognuno dei quali gestisce una operazione di conversione, ogni registro indica il canale da campionare e la sorgente trigger di campionamento. Nel nostro caso ad esempio l'evento di trigger è il counter del PWM. 
Associare più SOC allo stesso trigger permette di implementare il **multi sampling**, si misurano più campioni consecutivi dello stesso canale di corrente per effettuare una media e ridurre l'errore dovuto ai ripple di corrente.
Ogni ADC può generare un segnale di interrupt, per un totale di 4 per far eseguire alla CPU la routine di controllo.

Due moduli ePWM permettono di produrre due segnali PWM indipendenti e produrre degli interrupt a partire dal confronto del Period Register (Contatore del period) o del Compare Register (Contatore del duty cycle), ogni PWM può avere fino a 4 valori di Compare.
