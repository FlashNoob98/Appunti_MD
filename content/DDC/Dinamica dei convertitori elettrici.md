# Modelli dei convertitori
Per ogni convertitore è possibile descrivere la sua dinamica mediante la giustapposizione di differenti modelli rappresentanti le differenti configurazioni, si ottiene il [[Modello dinamico alle configurazioni|modello dinamico alle configurazioni]].

A causa dei numerosi limiti del [[Modello dinamico alle configurazioni|modello dinamico alle configurazioni]], si è cercato 
negli anni un'alternativa, un modello che esplicitasse le [[Grandezze di controllo|grandezze di controllo]], si è quindi definito il modello dinamico [[Modello dinamico affine nel controllo|affine nel controllo]].

Tutti i convertitori possono essere scritti nella forma affine del controllo, quando le funzioni $f$ e $g_\nu$ sono in forma affine dello stato allora il modello può essere espresso in [[Forma bilineare|forma bilineare]]. 

Si vede che la dimensione dello spazio di controllo $m$ deve rispettare un valore minimo affinché si possano ottenere tutti gli $N$ stati possibili di un convertitore, si sottolinea ad esempio il caso del convertitore [[Boost converter#DCM|boost in DCM]] in cui il numero di stati passa da 2 a 3 ed è necessario uno spazio di controllo di un grado più grande, vale infatti la seguente:
$$
2^m \geq N
$$
Non avrebbe senso avere due segnali di controllo con un singolo componente da controllare, va esteso il concetto di [[Grandezze di controllo|grandezza di controllo]].
## [[Modello Averaged]]
Non è sempre semplice ricavare il modello dinamico di un convertitore, inoltre è di difficile da particolarizzare a regime, per questo motivo nel 1976 presso il *Californian Institute of Technology*, [R. D. Middlebrook](https://www.venableinstruments.com/blog/dr-middlebrook) e Slobodan Ćuk, svilupparono i primi modelli per l'analisi dei convertitori elettronici, successivamente nel 1992 fu introdotto il concetto di *State space averaging* da Krein e successivamente fu formalizzato il [[Modello Averaged|modello Averaged]].
# Richiami matematici
È importante rivedere alcuni concetti matematici come il [[Problema di Cauchy|problema di Cauchy]] in quanto nel caso dei convertitori elettrici la funzione che descrive il sistema può essere di classe $C$ infinito, talvolta analitica ma quasi mai continua nel tempo a causa della non linearità dei dispositivi switching. Non esiste dunque secondo il teorema di Cauchy-Lipschitz una soluzione.
## Ciclo limite
Mediante questo teorema è possibile ricavare ad esempio il [[Boost converter#Curva integrale|ciclo limite]] di un convertitore, ovvero la traiettoria nel tempo delle sue variabili di stato.
L'orbita descritta dal vettore di stato è sempre una traiettoria isolata, è un'orbita che non si incrocia con nessun'altra orbita che non venga assorbita dall'orbita del ciclo limite stesso.

