Si scrive il modello della macchina asincrona nel riferimento di statore:
$$
\vec{V}_{s} = R_{s}\vec{i}_{s} + L_{d,s} \frac{d}{dt}\vec{i}_{s} + L_{m} \frac{d}{dt} \left( \vec{i}_{s} + \vec{i}_{r}' \right)
$$
si definisce il flusso di statore:
$$
\vec{\Phi}_{s} = L_{s}\vec{i}_{s} + L_{m} \vec{i}_{r}'
$$
dunque si riscrive l'equazione di statore:
$$
\vec{V}_{s} = R_{s}\vec{i}_{s} + \frac{d}{dt} \vec{\Phi}_{s}
$$
e la coppia:
$$
M_{e} = -\frac{3}{2 p}\mathrm{Im} \left\{ \vec{\Phi}_{s} \hat{\vec{i}}_{s} \right\}
$$
Si può trascurare il termine resistivo rispetto alla tensione indotta complessiva:
$$
\vec{V}_{s} \simeq \frac{d\vec{\Phi}_{s}}{dt}
$$

In ogni periodo di commutazione si ha che la tensione applicata dall'inverter coincide con una variazione del flusso, questa variazione è funzione però della posizione del vettore di flusso.

Si realizza una circonferenza che rappresenta la traiettoria desiderata del vettore di flusso $\vec{\Phi}^*_{s}$, con una fascia di incertezza $\pm\Delta$.
In ogni istante in cui il flusso tende ad uscire dalla regione di isteresi, andrà fornito un differente vettore di tensione, è possibile determinare in anticipo i vettori di tensione da fornire in funzione dei settori angolari in cui il flusso fuoriesce dalla regione di isteresi.

Si realizzano 6 settori da 60 gradi tali che ogni vettore di tensione sia la loro bisettrice, ad esempio il settore 1 è compreso tra -30 e 30, il settore 2 tra 30 e 90 ecc..
Si può supporre che per tutto il settore 1, l'effetto del vettore di tensione 1 sul vettore flusso sia sempre lo stesso.
Si ha in realtà un differente effetto sulla fase del vettore di flusso, nella regione tra 0 e 30 si ha un anticipo di fase, tra 0 e -30 si avrebbe un ritardo, sempre considerando il vettore $V_{1}$.
Per questo motivo si decide di escludere il vettore centrale $V_1$ quando il vettore di flusso si trova nella regione 1 e si considerano solo i vettori di tensione successivo e precedente, ovvero $V_{2}$ e $V_{6}$.


<center>

| Settore | $\lambda_{\Phi}$ | Rotazione antioraria | Rotazione oraria |
| ------- | ---------------- | -------------------- | ---------------- |
| k       | 1                | $\vec{V}_{k+1}$      | $\vec{V}_{k-1}$  |
| k       | 0                | $\vec{V}_{k+2}$      | $\vec{V}_{k-2}$  |

</center>

La differenza tra il flusso e il riferimento viene inviata ad un regolatore ad isteresi che fornisce 1 se l'errore è maggiore del valore di isteresi o 0 se è minore del minimo valore di isteresi.


Riprendendo l'equazione della coppia si esplicitano i due vettori di flusso e corrente:
$$
\vec{i}_{s} = I_{s}e^{j \phi_{s}}\qquad \vec{\Phi}_{s} = \Phi_{s}e^{j \Psi_{s}}
$$
sostituendo nell'equazione della coppia:
$$
M_{e} = \frac{3}{2}p \Phi_{s}I_{s} \sin(\phi_{s}-\Psi_{s}) = \frac{3}{2} \Phi_{s} i_{q}^{\Psi}
$$

L'angolo $(\Phi_{s}-\Psi_{s})$ è l'angolo tra la corrente il flusso, dunque il seno è la proiezione in quadratura della corrente rispetto al flusso $i_{q}^{\Psi}$.
Si cerca come sempre di mantenere il flusso costante intorno al punto di saturazione, si controlla la coppia con la corrente $i_{q}^\Psi$.

Si dovrà avere in questo caso un controllo ad isteresi anche sulla coppia.
In questo caso il regolatore ad isteresi di coppia avrà due bande, una positiva ed una negativa:

<center>


| Settore | $\lambda_{M}$ | Rotazione antioraria              | Rotazione oraria                  |
| ------- | ------------- | --------------------------------- | --------------------------------- |
| k       | 1             | $\vec{V}_{k+1}$ o $\vec{V}_{k+2}$ | $\vec{V}_{k-1}$ o $\vec{V}_{k-2}$ |
| k       | 0             | $\vec{V}_{0}$ o $\vec{V}_{7}$     | $\vec{V}_{0}$ o $\vec{V}_{7}$     |
| k       | -1            | $\vec{V}_{k-1}$ o $\vec{V}_{k-2}$ | $\vec{V}_{k+1}$ o $\vec{V}_{k+2}$ |

</center>


Si ottiene una combinazione di quattro casi in totale tra il controllo di flusso e quello di corrente. Si può pensare di compilare la tabella per tutti i settori.

<center>


| $\lambda_{\Phi}=1$ | $\lambda_{\Phi}=1$ | $\lambda_{\Phi}=0$ | $\lambda_{\Phi}=0$ |
| ------------------ | ------------------ | ------------------ | ------------------ |
| $\lambda_{M}=1$    | $\lambda_{M}=0$    | $\lambda_{M}=1$    | $\lambda_{M}=0$    |
| $V_{k+1}$          | $V_{k-1}$          | $V_{k+2}$          | $V_{k-2}$          |

</center>

Se si deve diminuire la coppia si può però ipotizzare di fornire una tensione nulla, questo perché si ha una riduzione più lenta della coppia. Per questo motivo il regolatore ad isteresi ha una certa forma.
