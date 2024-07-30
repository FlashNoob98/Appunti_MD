# Modelli dei convertitori
Per ogni convertitore è possibile descrivere la sua dinamica mediante la giustapposizione di differenti modelli rappresentanti le differenti configurazioni, si ottiene il [[Modello dinamico alle configurazioni|modello dinamico alle configurazioni]].

A causa dei numerosi limiti del modello dinamico alle configurazioni, si è cercato 
negli anni un'alternativa, un modello che esplicitasse le grandezze di controllo, si è quindi definito il modello dinamico [[Modello dinamico affine nel controllo|affine nel controllo]].

Tutti i convertitori possono essere scritti nella forma affine del controllo, quando le funzioni $f$ e $g_\nu$ sono in forma affine dello stato allora il modello può essere espresso in [[Forma bilineare|forma bilineare]]. 

Si vede che la dimensione dello spazio di controllo $m$ deve rispettare un valore minimo affinché si possano ottenere tutti gli $N$ stati possibili di un convertitore, si sottolinea ad esempio il caso del convertitore [[Boost converter#DCM|boost in DCM]] in cui il numero di stati passa da 2 a 3 ed è necessario uno spazio di controllo di un grado più grande, vale infatti la seguente:
$$
2^m \geq N
$$


