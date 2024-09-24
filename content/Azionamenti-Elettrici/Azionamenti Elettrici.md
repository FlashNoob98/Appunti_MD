 Esistono varie tipologie di azionamenti, esistono quelli *meccanici*, *idraulici*, *pneumatici* ed *elettrici*, questi ultimi si fanno apprezzare per l'elevata flessibilità di impiego, la maggiore semplicità di controllo, gli elevati livelli di precisione e rapidità di controllo, la semplicità realizzativa, elevati rendimenti e bassi consumi senza carico, bassa rumorosità, conseguenza anche della grande diffusione dell'energia elettrica.

Secondo la norma CEI 301-1 possiamo definire azionamento o PDS (Power Drive System) **un qualunque sistema che converta energia elettrica in energia meccanica mediante l’ausilio di apparecchiature elettroniche di supporto di potenza**.

Hanno una densità di potenza più bassa rispetto a quelli idraulici ad esempio, ma possono fornire potenza a velocità maggiori rispetto agli altri azionamenti.
L'elemento imprescindibile di un azionamento elettrico è il *motore elettrico*, è quello più semplice. Ogni tipologia di motore elettrico ha bisogno di una certa *tipologia* di energia elettrica, ad esempio continua o alternata, monofase o trifase, per questo motivo vengono spesso accoppiati ai convertitori elettrici, che trasformano l'energia elettrica a partire dalla sorgente e alimentano il motore che viene collegato ad una macchina operatrice.

A monte del convertitore viene solitamente posto un dispositivo di manovra, che può essere azionato manualmente o automaticamente se funge anche da dispositivo di protezione.
Tra il motore elettrico e la macchina operatrice viene solitamente posto un organo di trasmissione.

All'azionamento realizzato viene sovrapposto un sistema di trasduttori connessi ad un sistema di misura che elabora le grandezze del sistema e le invia al sistema di diagnostica, che potrebbe segnalare ad esempio la presenza di guasti o valori fuori soglia, eventualmente questo sistema può pilotare il sistema di protezione nel caso in cui i valori siano critici.
Il sistema di diagnostica è fondamentale inoltre per programmare le manutenzioni dei componenti del sistema.

Al fine di poter incidere sul comportamento del sistema e se ne desideri cambiare le caratteristiche, si può utilizzare un *[[Controllo digitale|controllore]]*, ovvero un dispositivo che presi dei riferimenti esterni, solleciti il sistema affinché questo si comporti nella maniera desiderata, la parte *flessibile* del sistema è il convertitore, si potranno modificare ad esempio gli angoli di innesco dei dispositivi switching.
Un controllo che impone una certa azione a seguito di un riferimento desiderato, è chiamato *a catena aperta*, se invece si osserva il sistema e si corregge l'azione di conseguenza, si ha un controllo *a catena chiusa*.

Nello studio di un azionamento elettrico sono coinvolte numerose discipline, a partire dalla [[Richiami di meccanica|meccanica]], all'[[Dinamica dei convertitori elettrici|elettronica di potenza]], industriale, digitale o analogica, sistemi elettrici, controlli automatici e informatica industriale, compatibilità elettromagnetica, affidabilità e sicurezza o energetica.

L'azionamento più semplice è composto da un convertitore ed un motore, chiamato *monomotore*, oppure un unico convertitore può pilotare più motori, in questo caso viene chiamato *plurimotore* oppure possono esistere più azionamenti coordinati, è un sistema *pluri-azionamenti*. A monte di un azionamento elettrico è importante disporre un trasformatore ed un filtro al fine di controllare le correnti assorbite dalla rete.

Gli azionamenti possono essere unidirezionali o reversibili se il flusso di energia va unicamente dalla rete al motore oppure è possibile avere un recupero di energia.

Un tipo di azionamento prevede il controllo della *coppia*, è una grandezza che spesso si vuole controllare in un azionamento ma non è semplice da misurare direttamente, per questo motivo si misurano altre grandezze come la velocità angolare e la posizione angolare e la si calcola successivamente mediante un modello matematico. Questo valore è confrontato con la coppia di riferimento, ottenendo dalla loro differenza l'*errore* che viene successivamente inviato al regolatore che di conseguenza agisce sul sistema, variando ad esempio la tensione.

Successivamente si può effettuare un controllo "più esterno" che controlli, sempre in catena chiusa, la velocità, l'uscita del regolatore di velocità è proprio la coppia di riferimento da imporre al regolatore interno; quello descritto viene definito **controllo in cascata**.
Analogamente si può realizzare un regolatore di posizione, esterno a quello di velocità.