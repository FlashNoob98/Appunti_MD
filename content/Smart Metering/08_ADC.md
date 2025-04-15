Gli ADC permettono l'acquisizione single ended o differenziale, nel primo caso il riferimento è la massa che se ha un rumore viene riportato nella misura.
La misura su canali differenziali prevede la misura tra due canali, l'eventuale rumore sulla massa viene eliminato per sottrazione:
$$
V_{in}+V_{noise}-(V_{min}+V_{noise}) = V_{in}-V_{noise}
$$

Si usa l'ENOB per quantificare la qualità del convertitore, più vicino è al nominale e più l'AD è ideale, ad esempio il convertitore è a 12 bit ma l'ENOB è 11.3 bit in modalità differenziale.

Sono presenti 4 ADC, possono lavorare indipendentemente o in maniera dual mode, hanno canali interni o esterni che possono essere campionati.
Posso collegare qualsiasi tensione compresa tra 0 e 3.3 V ad un pin e misurarne il valore, oppure posso usare dei canali interni, provenienti da un sensore interno al microcontrollore o una linea collegata alla metà della tensione di batteria.

Maggiore è la tensione di batteria e migliori saranno le performance dell'alimentatore interno, non potrei misurare il valore della batteria, sarebbe superiore a 3.3V, per questo motivo leggo la tensione dimezzata.

Un'altra linea è la tensione di alimentazione oppure le uscite degli OPAMP interni.

Il convertitore SAR permette di offrire un'uscita con una risoluzione variabile, (approssimazioni successive), se passo da 12 a 6 bit ho una velocità maggiore con una risoluzione più bassa e viceversa.

Esistono canali FAST e SLOW, i secondi sono condivisi tra più AD, si passa da 5.1 a 4.8 Ms/s.

Il periodo di conversione dell'AD può essere indipendente dal clock del bus, se gli fornisco un clock esterno asincrono rispetto al clock di sistema.

Posso chiedere all'ADC una fase di calibrazione interna, automatica.

Channel-Wise sampling programming time, prima dell'AD è presente un elemento importante, il Sample-and-Hold, per mantenere la tensione costante durante la conversione, potrebbe essere necessario un tempo di carica più o meno lungo a seconda della sorgente del segnale.
Se la sorgente del segnale è ad alta impedenza, posso aumentare il tempo di carica nel SH, questa impostazione è indipendente per ogni canale.
Posso rallentare un singolo canale e non tutti nel caso in cui una singola linea sia ad alta impedenza (carica del'SH più lenta).

Ogni ADC ha 5 canali FAST dedicati, esterni (GPIO), fino ad 11 canali LENTI dai GPIO esterni.
Sono presenti 7 canali interni, uno collegato al sensore di temperatura e collegato ad ADC1 ed uno con 1/2 tensione di batteria, ADC1, poi il riferimento interno di tensione, connesso a tutti gli ADC, infine quelli degli OPAMP che possono essere connessi ai singoli ADC.

Posso avviare una conversione via codice o mediante un trigger hardware, ad esempio un timer, ogni volta che termina un conteggio del timer, l'ADC avvia la conversione, in alternativa posso controllarlo via codice.

Ogni ADC può convertire un singolo canale o una sequenza di canali mediante un trigger, software o hardware.

Posso avere un'acquisizione singola nel caso in cui desideri una singola acquisizione ad ogni segnale di trigger, senza ripeterla in automatico.

Modalità continua invece implica una conversione continua appunto.

Modalità discontinua.

Modalità ADC dual, può rendere gli ADC interlacciati (interleaved) o simultanei.

Ogni ADC è caratterizzato da 3 watchdog, ad esempio si osserva una tensione e si impongono due livelli di trigger, minimo e massimo.

EXT_0:16 sono i trigger che possono essere esterni o i timer interni.

I canali SLOW hanno una nomenclatura leggermente diversa, sono condivisi tra due ADC.

La coppia ADEN e ADIS controllano l'alimentazione dell'ADC.

In modalità double ended devo abilitare due pin in modalità analogica, e non uno. Se scelgo la modalità differenziale, IN AUTOMATICO verrà scelto il canale negativo.

i bit SMPx dove x  l'indice del canale posso indicare la configurazione di chiusura del SH, ho 8 configurazioni dalla più veloce alla più lenta.

In caso di sequenza di conversioni, viene scritto il risultato nel data register alla fine della conversione, se questo non viene letto in tempo verrà sovrascritto dalla successiva conversione, se c'era l'EOC alto (END OF CONVERSION) si abiliterà il flag OVR, overrun che segnala la perdita di un campione.

AWDx indica valori di tensione fuori range.(?)

Si può impostare il DMA per scrivere in automatico il valore misurato in memoria, senza interrogare il processore.

Per avviare un ADC:
Abilita il regolatore di tensione dell'ADC, aspetta 10us di warm-up.

Disabilitare l'ADC alla fine delle misure per risparmiare potenza.(ADEN=0)

ADVREGEN per abilitare il regolatore, da 10 disabilitato a 00 (reset) e infine 01 per abilitato.
Il contrario per spegnerlo.

DIFSEL permette di selezionare la modalità differenziale per il singolo canale dell'ADC, se metto 0 è single ended, se metto 1 è differenziale.
Devo sempre ricordarmi di abilitare i pin in Analogico nel MODER.

ADCAL gestisce la calibrazione, il fattore di calibrazione sarà diverso per un canale single ended o differenziale, per questo motivo il micro ADCALDIF=0 implica che si vuole calibrare l'AD per canali single ended, se pari ad 1 si vuole calibrare per canali differenziali. Devo impostare ADCAL ad 1, si può fare solo mentre ADEN=0 ovvero esso è spento.
Viene posto a 0 quando terminata la calibrazione, questi fattori vengono posti nel registro CALFACT_S o CALFACT_D se single ended o differential.

Se voglio fare sia misure differenziali che single ended devo fare entrambe le calibrazioni, sarà poi l'ADC a gestire il valore corretto di calibrazione a seconda del canale usato.

Finita la calibrazione posso accendere l'AD, impostando ADEN=1, avvia una fase di warm-up del convertitore che termina quando il bit ADRDY del registro ISR sale ad 1.

Per spegnere l'AD devo porre ad 1 l'ADDIS (ADDISABLE).

Il tempo del SAR può essere fornito da una sorgente esterna oppure dal clock, CKMODE=00 in maniera asincrona o sincrona, nel secondo caso posso usare un fattore di divisione intero del clock, 1, 2 o 4 volte.

## Channel selection
Ogni ADC può gestire una sequenza di canali, posso fare in sequenza una misura su più canali, posso anche convertire un canale più volte, ogni volta che termino una conversione si alza un flag EOC, end of conversion.
Finita la sequenza si alza il flag EOS, End Of Sequence.
Gli ADC hanno una serie di registri ADCSQRx dove x va da 1 a 4, i primi 4 bit del primo registro contengono il parametro L, ovvero Length, ovvero quanti elementi ci sono nella sequenza? posso inserire, in 3 bit i numeri da 0 a 15 ovvero da 1 a 16 conversioni, per questo avrò SQ1 grande 5 bit nel quale indico il numero del primo canale da convertire, in SQ2 metto il numero del secondo canale da convertire e così via.


É il valore di L a determinare quanti canali leggere.

Se scelgo un canale come differenziale non posso usare l'i+1esimo canale per fare single ended o viceversa.

SMP determina i multipli dei colpi di CLOCK per determinare il tempo di campionamento del singolo canale, ovvero SMP2 = 100, il canale 2 avrà un sampling time di 19.5 t_AD, SEMPRE, in qualsiasi posizione della sequenza.

C'è un registro SMP per ogni canale.

Il tempo totale di conversione inteso come tempo di sampling e quantizzazione saranno nel caso migliore 1.5 t_AD e di quantizzazione pari a 12.5 t_AD = 14t_ADC che con la frequenza massima di 72MHz corrispondono a 149?? us.


In single mode (CONT=0) ad ogni ADSTART si esegue una conversione.

Se CONT=1 continuous, si ritorna ad ogni EOC.

