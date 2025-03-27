Come visto in precedenza si usava il pin in configurazione write (01 nel moder) e con la lettura dell'output data register si impostava lo stato del pin (LED)

C'è un driver elettrico che pone lo stato di due mosfet PN e porta il pin a 3.3 o 0V.

In modalità alternate function sono disabilitati i data register, il PIN viene controllato da una periferica sul microcontrollore, ad esempio per un protocollo di comunicazione, il pin deve sia leggere che scrivere.

In modalità analogica la linea può essere sfruttata dall'ADC

In questo caso dobbiamo considerare il "debouncing" del tasto.

Per leggere dal registro si fa una AND bit a bit con una maschera, che avrà tutti 0 tranne il bit 1 nella locazione di IDR0 (per il pin 0)

dunque 
```
*punt &= 0x00000001
```
L'operazione di AND restituirà 0 in ogni posizione 0 della maschera e 1 se anche la posizione in memoria corrispondente alla maschera sarà 1.

