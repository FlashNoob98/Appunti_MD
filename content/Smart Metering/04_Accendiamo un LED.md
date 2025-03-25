La posizione del led sulla board è indicato sullo schema elettrico della scheda.
I LED della scheda sono connessi alla porta E, dunque devo abilitare la porta E, abilitando un particolare FLAG GPIOE all'interno della configurazione dell'RCC, abilitandone il clock.
`RCCAHBENR`, leggendo l'indirizzo di offset rispetto all'indirizzo base, che si trova invece nel datasheet.

L'indirizzo dell' `RCC_AHBEN` sarà: `0x40021014`
Il valore presente nel registro allo stato di reset sarà invece:
`0x0000 0014`, per scrivere un 1 in posizione 21 dovrò scrivere un 2 in esadecimale, ovvero scrivere: `0x0020 0014`.

Il registro è composto da 32 bit, numerati da 0 a 31,
da 0 a 15 per i flag "inferiori" e 16-31 quelli superiori, ogni 4 bit sono rappresentati da una cifra esadecimale.

In alternativa per modificare il bit 21 posso usare la procedura di "shift" ovvero piazzo un 1 in posizione 0, lo shifto di 21 posizioni, indicata nel linguaggio C con `1<<21`.

`RCC_AHBENR|=(1<<21)`
ovvero una operazione di "OR" bitwise, è un'operazione che conserva lo stato precedente dei bit.

Ad esempio per semplicità considero un singolo byte (8bit)
`0b 01011000` voglio portare ad `1` il bit in terza posizione, potrei sommare 2^2 ovvero eseguire un'operazione di OR su ogni bit.
Senza l'operazione di OR avrei invece azzerato i bit precedenti.

Viceversa per passare da 1 a 0 si deve usare una maschera negata, usando l'operazione di AND. Sono "maschere" quelle che hanno un solo bit diverso nella posizione che si vuole modificare.

Un modo semplice per scrivere una maschera negata in C e l'operazione di AND sarebbe:
`RCC_AHBENR &= ~(1<<21)` negando la maschera con la tilde.
In esadecimale sarebbe `0xFFDFFFFF` 

Esempio di programma:
```
int main(void){
	unsigned int* pippo;

	pippo=(unsigned int*)0x40021014;//RCC_AHBENR = 0x4002 1000 + 0x14 Offset

	*pippo|=(1<<21); //Enable GPIOE EN (IOPEEN in Debug)

	pippo=(unsigned int*)0x48001000;//GPIOE_MODER Offset 0x00

	//*pippo|=(1<<16); //PE8 OUTPUT, modifica bit 16, ovvero moder8
	//*pippo |= 0x55550000; // Abilita tutti e gli 8 i led
	*pippo |= 0x55400000; // Abilita 5 led

	pippo=(unsigned int*)0x48001014; //GPIOE_ODR offset 0x14

	//*pippo|=(1<<8); // ODR8 > PE8=1
	*pippo |= 0xF800;  //ODR11-ODR15 = 1 Accendi 5 LED
}//end main
```

con l'* intendo che quello dichiarato è un indirizzo e non un valore.
Per accedere all'indirizzo contenuto dal puntatore scrivo l'istruzione con l'*

Una volta inizializzata la porta va impostato il pin, può essere configurato in lettura/scrittura digitale, lettura analogica o funzione alternata.
Di default tutti i pin sono configurati come digital-input, hanno una struttura ad alta impedenza.

Per ogni pin sono presenti 2 bit di configurazione
Input
Output digitale
Alternate function
Analog

Alternate function il pin è controllato da una periferica, ad esempio connesso ad un timer.

Per impostare il pin 8 come uscita devo scrivere `1<<16`, vedi `MODER` nel reference manual per configurare le funzionalità dei pin.

Per accendere effettivamente il PIN devo modificare l'output data register `ODR8`
