Fondamentale per la [[Sicurezza elettrica in BT|sicurezza elettrica]] elettrica è l'utilizzo di interruttori automatici. Vanno innanzitutto distinte le due tipologie di contatto elettrico: **diretto** e **indiretto**.

Il primo si ha in caso di contatto con una parte dell'impianto normalmente in tensione, il secondo se avviene un contatto con la **massa**, una parte di impianto normalmente non in tensione che va in tensione a causa di un guasto dell'isolamento principale.

# Contatti indiretti
Il sistema principale per proteggere dai contatti indiretti è quello di utilizzare un doppio isolamento, garantisce di poter sopportare un guasto all'isolamento principale, non sempre è fattibile se le apparecchiature sono grandi, può non convenire da un punto di vista economico.
Si deve dunque garantire che nel caso in cui una massa vada in tensione, quel valore non deve essere pericoloso. Oppure si deve disporre di dispositivi in grado di disalimentare l'impianto in caso di guasto.

Il contatto può non avvenire con una massa appartenente all'impianto ma mediante una *massa estranea* ovvero non facente parte dell'impianto, in questo caso si potrebbe avere un potenziale diverso da quello di terra, aumentando di fatto la resistenza di terra pari al rapporto tra la tensione totale e la corrente dispersa.

È considerata massa estranea **qualsiasi parte metallica non facente parte dell'impianto con resistenza inferiore ai $1000\Omega$ negli impianti ordinari e $200\Omega$** in quelli particolari.

Si considera la $U_{tp}$ (touch-permissible) la tensione di contatto massima ammissibile, espressa dalle curve di sicurezza, è la tensione che si ha durante il contatto della persona.
In condizioni cautelative si trascura la resistenza di contatto, ponendo la resistenza del corpo in parallelo alla resistenza $R_E$ che invece è quella che fornisce la tensione di contatto  a vuoto. 
La $U_{tp}$ va confrontata con la $U_{stp}$, ovvero la tensione di contatto a vuoto.

La tensione $U_{sp}$ è la tensione di passo permissibile, si instaura tra due piedi posti a distanza di un metro in caso di guasto a terra, è superiore alle precedenti, circa 3 volte la $U_{tp}$ a causa della minore pericolosità di un contatto piede-piede.

Esistono inoltre tre tipologie di sistemi in bassa tensione, in base allo stato del neutro e delle masse:
- IT, neutro in cabina isolato, masse connesse a terra nell'impianto, si hanno correnti di guasto piccole a causa delle piccole capacità parassite, si ha però una sovratensione delle altre fasi. L'energia immagazzinata dalle capacità parassite passa da $3\frac{1}{2}CE^2$ a $3CE^2$, inoltre le sovratensioni, in dinamica sono intermittenti, per questo motivo si preferisce spesso usare gli altri due sistemi. 
- TT, entrambi messi a terra, se la cabina è pubblica.
- TN(S-C), neutro in cabina messo a terra, masse connesse al neutro, mediante un conduttore Separato o mediante il conduttore di neutro (conduttore PEN), se la cabina è privata.

