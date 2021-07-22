> _**Le reti Blockchain e altri sistemi di ledger distribuiti usano la crittografia a chiave pubblica per l'identificazione degli attori della rete. Questi sistemi di identità, tuttavia, sono insufficienti per la gamma di possibili applicazioni Web3. Gli identificatori decentralizzati (DID) in combinazione con i ledger distribuiti possono fornire soluzioni di identità "user-centrica" adatte al Web3, permettendo più privacy e controllo sui propri beni digitali e sull'impronta digitale rispetto alle soluzioni "server-centriche" usate nel Web2.**_

Disclaimer: L'intenzione di questo capitolo è quella di dare una panoramica generale, e far luce sull'urgenza e l'importanza di adeguate soluzioni di identità digitale come elemento fondamentale per il Web3. Tuttavia, l'argomento delle identità digitali è molto più complesso di quanto delineato in questo capitolo e non può essere discusso in dettaglio, in quanto andrebbe oltre lo scopo di questo libro.

La gestione dell'identità si riferisce al processo attraverso il quale organizzazioni, individui e oggetti possono essere identificati, autenticati e certificati in modo affidabile. I servizi di identità fidati sono la base per la gestione dei diritti di accesso su Internet e un prerequisito necessario per molte attività socio-economiche in generale - offline o online. I casi d'uso relativi all'identità possono essere trovati nel governo (certificati di nascita, carte d'identità nazionali, passaporti o patenti di guida), nell'istruzione (certificazioni e licenze), nella sanità (registri di dati personali relativi alla salute), nell'e-commerce, nelle banche o nella finanza (dati dei clienti, B2B e dei dipendenti). Nell'Internet-of-Things, un numero crescente di oggetti connessi a Internet ha anche bisogno di sistemi di identificazione adeguati (come i numeri di serie). Da un punto di vista informatico il termine "identità" può essere riferito agli elementi di dati relativi al processo di gestione dell'identità: "identificatore", "autenticazione" e "credenziali”. 

Gli <span style="text-decoration:underline;">identificatori </span>sono necessari per identificare in modo univoco una persona, un'istituzione o un oggetto. Un numero di telefono o un indirizzo e-mail sono unici per natura e si qualificano come identificatori. Il nome di una persona non è necessariamente unico e non sempre si qualifica come identificatore. D'altra parte, mentre l'indirizzo di residenza e il numero di telefono di una persona sono unici per natura, possono cambiare nel tempo. Idealmente, un identificatore deve essere unico e persistente nel tempo. Un codice fiscale, un numero di passaporto o un numero di patente di guida potrebbe essere un identificatore unico per una persona, se non cambia nel tempo. Il fatto che tali identificatori persistano o meno nel tempo dipende dal paese e dal fatto che i numeri dei documenti scadano o meno. Identificatori unici esistono anche per oggetti e aziende: Un numero di serie è un identificatore unico per un oggetto. Un numero di registrazione di un'azienda è un identificatore unico per un'organizzazione a scopo di lucro, usato dalle autorità pubbliche per identificare le aziende per la riscossione delle tasse o la concessione di sussidi.

L'<span style="text-decoration:underline;">autenticazione </span>è il processo con cui una persona, un'istituzione o un oggetto possono provare che sono chi dicono di essere. Una persona può autenticarsi provando la proprietà di un oggetto (carta d'identità, portafoglio hardware, portafoglio software), la conoscenza di un segreto (password o PIN), o esibendo una proprietà personale (dati biometrici, firma). Spesso si usa una combinazione di questi sistemi. Deve esistere almeno un metodo efficace e affidabile per autenticare una persona, un'istituzione o un oggetto. La forma più efficace per dimostrare l'autenticazione delle persone è la biometria. Una carta d'identità è una forma analogica di autenticazione, poiché l'immagine e la firma scritta a mano sulla carta d'identità sono metodi di autenticazione. Le password sono l'equivalente digitale nella rete Internet di una firma scritta a mano. I nomi utente, le password e tutti gli altri dati personali sono controllati da istituzioni per lo più private come banche, università, o Facebook, Twitter e Google. Le reti Blockchain e altri ledger distribuiti hanno reso popolari sistemi di identità più centrati sull'utente, applicando la crittografia a chiave pubblica come metodo di autenticazione.

<span style="text-decoration:underline;">Rivendicazioni e credenziali</span>: un'identità è inutile senza un collegamento di quelle informazioni a una persona (dati personali), un'istituzione (dati istituzionali), o un oggetto (dati relativi all'oggetto). I dati personali, per esempio, coinvolgono rivendicazioni fatte dalla persona stessa (rivendicazione) o da altre persone o istituzioni (credenziale). Tali affermazioni possono includere informazioni su chi siamo, dove viviamo, dove siamo nati, o quali lauree abbiamo conseguito, le quali devono essere attestate da autorità fidate. I dati personali possono anche includere dati aggiuntivi, come la cronologia di navigazione personale, le attività dei social media, o le geo-localizzazioni, che sono automaticamente autenticate dalle macchine e legate all'identificatore personale. 

Storicamente gli strumenti di identità come passaporti, patenti di guida, carte di sicurezza sociale o numeri di serie per le merci sono stati emessi da istituzioni centralizzate come i governi locali e nazionali, o altre istituzioni fidate. L'emergere di Internet ha creato la necessità di sistemi di identificazione digitale. Tuttavia, l'attuale Internet non fornisce un livello di identità nativo per persone, istituzioni o oggetti diversi dai nodi operativi in una rete di computer. Problemi come "Posso fidarmi che il mio cliente paghi le bollette?" o "Posso fidarmi che il fornitore di servizi consegni i miei beni?" non possono essere risolti dal solo protocollo Internet. Le aziende e le istituzioni pubbliche iniziarono a implementare soluzioni a livello applicativo, spesso usando database interni e combinazioni di username e password - il tipo di sistemi di identificazione che erano stati in uso fin dai tempi dei computer mainframe e prima della nascita di Internet. 


## Identità Server-Centriche

Il protocollo Internet non ha un formato nativo per gestire le identità di persone, organizzazioni e oggetti. Per rimediare sono state costruite soluzioni a livello applicativo utilizzando database interni (infrastruttura privata) per gestire tutti i dati coinvolti nei processi di gestione delle identità digitali. A causa della struttura client-server di Internet, qualsiasi servizio basato sul web - dai siti universitari all'online banking, ai social media e ai siti di e-commerce - offre il proprio servizio di gestione delle identità. Questo significa che tutti i dati relativi agli utenti sono gestiti dal fornitore del servizio, sulla sua infrastruttura informatica privata. Tutti gli elementi relativi al processo di gestione dell'identità - come l'emissione di un identificatore, la fornitura di un metodo di autenticazione, la fornitura delle credenziali e la gestione dei dati relativi all'utente - sono centralizzati. Il risultato è una serie di silos di dati incompatibili, con servizi di gestione dell'identità proprietari - e spesso anch’essi incompatibili tra loro - che hanno creato costi e richiesto compromessi significativi sia per le aziende che per gli utenti, come:

**<span style="text-decoration:underline;">Caos di password</span>**: nel corso dei decenni, con la crescita del numero di servizi Internet, la gestione delle password è diventata un compito caotico. Gli utenti devono gestire centinaia di coppie username-password per ogni applicazione o nuovo servizio online a cui si registrano. Frammenti dei loro dati personali sono sparsi per tutto il web. Agli albori di Internet ogni servizio online richiedeva agli utenti di registrarsi con un nome utente e una password per utilizzare i loro servizi, includendo altri dati se necessario. Oggi gli utenti possono utilizzare soluzioni di “single sign-on" fornite da aziende come Google, Facebook o Twitter, con lo svantaggio che queste identità possono essere osservate e revocate unilateralmente da quei fornitori di servizi in qualsiasi momento, e questo può avere come effetto “a cascata” il blocco dell’accesso a tutti gli altri servizi che si utilizzano con questa modalità. 

**<span style="text-decoration:underline;">Protezione contro attori malevoli</span>**: in una configurazione di e-commerce le aziende hanno bisogno di identificare attori malevoli che, ad esempio, ordinano merci senza mai pagarle, al fine di prevenire potenziali perdite aziendali. A causa della natura frammentata degli attuali sistemi di identità digitale, il processo di identificazione di questi attori per la protezione dalle frodi rappresenta un costo elevato per il business. "L'82% delle aziende lotta contro utenti falsi, e in media il 10% della base di utenti di un'organizzazione che si affaccia sul web risulta falso. Il costo medio del rivenditore per ogni record rubato contenente informazioni sensibili e riservate è di 165 dollari. 15 miliardi di dollari di perdite da 13,1 milioni di consumatori nel 2015 sono solo gli Stati Uniti"[^1]

**<span style="text-decoration:underline;">Protezione dei dati e costi di custodia</span>**: gli utenti devono fidarsi dei fornitori di servizi per mantenere l'integrità e la privacy dei loro dati. Un numero crescente di dati personali è sotto la custodia di istituzioni spesso private che gestiscono una quantità crescente di dati dei clienti sui loro server privati, il che si traduce in quello che molti attivisti della privacy hanno definito "capitalismo di sorveglianza"[^2]. Le combinazioni di username e password sono spesso compromesse da violazioni di dati interni o esterni. Per mitigare questo problema sono state introdotte soluzioni come i metodi di autenticazione a più fattori. Ma la gestione della sicurezza - contro il furto o la perdita - dei dati relativi all'identità rimane ancora un compito costoso e frammentario. Con l'emergere di un crescente numero di leggi sulla protezione dei dati, e alla luce di potenziali cause legali e multe governative, per le aziende la raccolta di informazioni sensibili sui loro utenti e l'archiviazione di tali dati sui loro server è diventata un rischio commerciale crescente.

**<span style="text-decoration:underline;">Portabilità dei dati</span>**: nelle applicazioni B2B la portabilità è particolarmente rilevante lungo la supply chain per elaborare dati relativi alla provenienza di beni e servizi e ridurre i costi di gestione dei documenti. Nelle applicazioni B2C, la nuova legislazione come l'articolo 20 del Regolamento generale sulla protezione dei dati dell'Unione europea (GDPR) garantisce agli utenti il diritto di portabilità dei loro dati personali da un'azienda all'altra, e obbliga le aziende a fornire tale servizio. In una configurazione client-server, tuttavia, la portabilità dei dati tra istituzioni diverse comporta alti costi operativi.

**<span style="text-decoration:underline;">Mancanza di controllo e sovranità**:</span> gli utenti non hanno alcun controllo diretto su ciò che accade ai loro dati, e non sanno se e a chi sono stati trasmessi. A seconda della regolamentazione di un paese, gli utenti dei servizi basati su Internet possono essere bloccati dall'uso dei servizi (e dei loro dati) in qualsiasi momento. La protezione dei dati dipende dall'etica commerciale applicata dall'azienda che fornisce i servizi d'identità, ed è anche soggetta alla giurisdizione del paese in cui l'azienda ricade. 

**<span style="text-decoration:underline;">Ri-centralizzazione di Internet:</span>** gli effetti di rete hanno la tendenza a bloccare i clienti e i partner commerciali ad usare un solo fornitore di servizi. Prendiamo l'esempio di Amazon o eBay. Una volta che gli utenti hanno subito un processo di autenticazione con Amazon o eBay, tendono a rimanere su Amazon o Ebay, piuttosto che comprare prodotti su altri siti online. L'acquisto di un prodotto sul sito web di un negozio di quartiere richiederebbe un processo di autenticazione separato sul sito web di quel negozio e creare una nuova identità (username e password), comprese le informazioni di pagamento, che molte persone tendono ad evitare a causa della natura dispendiosa in termini di tempo di questo processo. D'altra parte, più utenti hanno Amazon ed eBay, più questi servizi diventano attraenti per i venditori, e viceversa. Come risultato di questi effetti di rete, il potere ha iniziato ad accumularsi intorno a queste piattaforme. Questo ha portato a una ricentralizzazione di Internet intorno ai fornitori di piattaforme Internet, che non solo gestiscono le identità dei loro utenti, ma controllano anche tutti gli altri dati relativi agli utenti. La "impronta digitale" di tutti gli utenti è spesso memorizzata in chiaro (non criptata) sui server delle aziende e utilizzata per il data mining mirato a creare algoritmi di raccomandazione, marketing mirato e altre forme di profilazione degli utenti che generano sempre maggiori ricavi per queste piattaforme Internet.


## Storia della gestione dell’identità digitale

Nel corso dei decenni diverse iniziative hanno cercato soluzioni alternative alla gestione centralizzata dell'identità. Nel 1999 Microsoft ha lanciato "Microsoft Passport" per fornire una "soluzione di identità federata" che le persone potevano usare per accedere a vari servizi Internet. L'idea principale era quella di fornire un servizio di identità online che mitigasse il caos delle password per gli utenti. Tuttavia, questa soluzione metteva Microsoft al centro della federazione. Sun Microsoft iniziò la "Liberty Alliance" nel 2001 come una soluzione più distribuita, dove il controllo sulle identità digitali era ora diviso tra diverse istituzioni, ma i dati personali rimanevano ancora sotto l'autorità di ogni singolo sito. Nel 2001, la "Identity Commons" ha iniziato a consolidare tutti i lavori sull'identità digitale con un focus sulla decentralizzazione, che alla fine ha portato alla creazione di "Internet Identity Workshop" nel 2005. La comunità di sviluppatori open-source ha iniziato a lavorare su concetti alternativi, come "OpenID", che ha contrastato il "modello server-centrico" con un "modello user-centrico" in cui gli individui potevano controllare la loro identità utilizzando il loro nome di dominio personale, e riempire il loro negozio di dati con dati personali che potevano essere forniti ad altre organizzazioni con il permesso dell'individuo. Tuttavia, queste soluzioni non erano molto facili da usare e richiedevano un certo know-how tecnico. 

Nel frattempo aziende come Facebook hanno adottato l'idea di "OpenID" ma hanno fornito una migliore usabilità, che è stata una delle ragioni per cui "Facebook Connect" ha avuto più successo di "OpenID" intorno al 2008. Chiunque poteva usare la propria identità di Facebook per iscriversi ad altri servizi Internet, che ora potevano usare una API di Facebook invece di gestire le proprie identità. Questo era molto utile per le piccole startup di Internet che potevano risparmiare costi sulla gestione delle identità, e per gli utenti che potevano risparmiare tempo e mal di testa per la gestione delle password. Presto anche Google, Amazon, Apple e Twitter hanno iniziato a fornire simili soluzioni di identità "server-centriche", e ora tutte queste società controllano la maggior parte del mercato dell'identità online. Questo include anche la storia personale di navigazione, il comportamento dei social media e la geo-localizzazione dei loro utenti. 

Nel frattempo, una serie crescente di iniziative ha continuato a lavorare sull'idea di soluzioni di identità più "user-centric", come l'iniziativa Web-of-Trust, che aveva le sue radici nel movimento Pretty Good Privacy (PGP). Queste iniziative hanno proposto l'uso della crittografia asimmetrica dove chiunque potrebbe essere un validatore di identità. Sfortunatamente, entrambe si concentravano sugli indirizzi e-mail come identificatori, il che significava che dipendevano ancora da istituzioni come l'ICANN[^3] per emettere i nomi di dominio su cui si basano questi indirizzi e-mail. Per una varietà di ragioni, PGP non è mai stato adottato su larga scala. 

Anni dopo, individui come Christopher Allen e iniziative come Rebooting-the-Web-of-Trust hanno ripreso questo lavoro, specialmente quando le reti blockchain sono emerse e hanno permesso l'uso della crittografia a chiave pubblica per l'identificazione pseudo-anonima senza collegare le identità a un indirizzo email. L'emergere delle reti blockchain e di altri ledger distribuiti ha fornito una naturale continuazione dei precedenti progetti di decentralizzazione. Christopher Allen e altri individui hanno elevato la discussione sulla gestione dell'identità a un livello politico e hanno proposto il concetto di "Self-sovereign Identity” (_Identità Auto-Sovrana_) o _SSI_, un sistema di gestione dell'identità centrato sull'utente che deve soddisfare una serie di principi guida:

**<span style="text-decoration:underline;">Accesso e controllo</span>**: controllo diretto dei propri dati di identità personale, gli utenti sono l'autorità ultima e hanno il controllo sul livello di anonimato dei loro dati.

**<span style="text-decoration:underline;">Trasparenza e interoperabilità</span>**: gli algoritmi che governano i dati relativi all'identità dovrebbero essere trasparenti, open source e indipendenti da qualsiasi infrastruttura particolare. I dati relativi all'identità devono avere validità di lunga durata (dovrebbero preferibilmente durare per sempre, o almeno per tutto il tempo che l'utente desidera).

**<span style="text-decoration:underline;">Portabilità</span>**: i dati relativi all'identità devono essere portabili ad altri servizi, altrimenti sono soggetti a censura o controllo. Le identità portabili assicurano che gli utenti mantengano il controllo delle loro identità indipendentemente dai servizi che usano.

**<span style="text-decoration:underline;">Consenso e minimizzazione</span>**: gli utenti devono sempre acconsentire all'accesso di terzi ai loro dati personali. Inoltre, quando i dati personali vengono divulgati, tale divulgazione dovrebbe coinvolgere solo la quantità minima di dati necessari.

Nel suo manifesto Allen ha delineato il delicato equilibrio tra il diritto alla privacy e la necessità di rivelare certe informazioni per la sicurezza dell'intera rete di persone. Ha segnalato come questi principi possano essere un'arma a doppio taglio, utilizzabile sia per scopi benefici che malevoli, concludendo che un sistema di identità deve bilanciare la trasparenza, l'equità e il sostegno degli interessi comuni di un gruppo e allo stesso tempo garantire la protezione dell'individuo. Tuttavia, tali discussioni non sono nuove e sono state soggette alla scienza politica, così come a secoli di dibattiti che sono stati risolti in varia misura a seconda del regime politico e delle leggi di governo dello stato nazionale in questione. L'equilibrio tra la privacy individuale e l'interesse pubblico è stato - ed è ancora - un argomento di diritto costituzionale in molti paesi democratici, soggetto a regolamentazione relativa alla "segretezza della corrispondenza" o alla "inviolabilità della abitazione" (per approfondire: Parte 3 - I privacy token).

Nel corso degli anni i principi sopra menzionati hanno ispirato e sono stati inclusi  in una serie di iniziative e gruppi di lavoro sul tema della identità user-centrica, come "Social Linked Data", "Rebooting the Web of Trust", "WebIDs", e più recentemente il "W3C Working Group on Decentralized Identifiers (DIDs)". L'obiettivo di tutte queste iniziative è stato quello di definire standard aperti internazionali che disaccoppiano il processo di emissione di una credenziale e di identificazione di un diritto da quello della loro verifica da parte di un insieme di attori, rimuovendo molti dei problemi che una soluzione server-centrica deve affrontare.


![alt_text](images/image1.jpg "image_tooltip")


## Identità User-Centriche basate su DID 

Le reti Blockchain attualmente offrono solo un set minimo di attributi di identità, che non sono sufficienti per molte interazioni socio-economiche sul web. Tuttavia, se impostato correttamente, il ledger può offrire componenti essenziali per un sistema di gestione dell'identità centrata sull'utente e che preservi la privacy, offrendo maggiore semplicità e costi inferiori per tutti i soggetti coinvolti. Gli identificatori decentralizzati (DID) in combinazione con i ledger distribuiti permettono un sistema di gestione delle identità più sofisticato. 

Un identificatore decentralizzato (DID) è un identificatore digitale unico, pubblico e pseudo-anonimo associato a una persona, un'azienda o un oggetto, che garantisce a ciascuno il controllo personale sulla propria identità digitale senza la necessità di avvalersi per la sua gestione di istituzioni centralizzate. Per garantire l'indipendenza dai registri centralizzati, i DID devono avere alcune proprietà: devono essere permanenti in modo che non possano essere riassegnati ad altre entità da chiunque ne abbia il controllo; devono essere “risolvibili”, nel senso di consentire a chiunque di capire come interagire con il soggetto identificato dal DID; e infine devono essere verificabili crittograficamente.

 L'infrastruttura a chiave pubblica, inerente ai ledger distribuiti, permette la registrazione dei DID di tutti gli attori coinvolti in modo pubblicamente verificabile. Qualsiasi utente può creare e registrare un DID quando attiva un nuovo wallet blockchain, che crea una coppia di chiavi private e pubbliche. Ogni DID può essere collegato a credenziali che sono emesse da altre persone e istituzioni che attestano caratteristiche specifiche per un proprietario di identità (autocertificazioni), come nome, indirizzo, e-mail, età, titoli conseguiti, o altre certificazioni come una patente di guida. 

Il wallet è l'equivalente digitale di un portafoglio fisico, che - oltre a conservare i propri contanti - funge anche da contenitore per le carte d'identità, come la patente di guida, la carta bancaria, l'iscrizione alla palestra, la carta d'identità nazionale, la tessera sanitaria con il codice fiscale, o le carte fedeltà. Un portafoglio Web3 può essere usato per gestire tutte le credenziali digitali crittograficamente protette che altri hanno emesso su di noi: credenziali tokenizzate che rappresentano la versione digitale della nostra patente di guida, carta bancaria, abbonamento alla palestra, carta d'identità nazionale, codice fiscale, carte fedeltà, ecc. Proprio come quando apriamo il portafoglio per mostrare la carta d'identità, occorre attivare il nostro wallet Web3 per mostrare a terzi le nostre credenziali digitali (usando una password). Nessuno può vedere il contenuto del nostro wallet Web3 senza il nostro consenso. Il contenuto del wallet rimane nascosto fino a quando si sceglie di mostrare qualcosa. Gli attori in questo scenario sono:

> <span style="text-decoration:underline;">Gestori di identità</span>: istituzioni fidate come governi locali, università e altre istituzioni pubbliche e private e, in alcuni casi, anche singoli individui. Possono fornire credenziali ad un proprietario di identità (come nome, età e data di nascita), e attestare la validità dei dati personali.

> <span style="text-decoration:underline;">Proprietari di identità</span>: gestiscono, utilizzando il loro wallet Web3, le credenziali che sono state emesse dalle terze parti menzionate sopra, e possono usarle in qualsiasi momento per provare a terzi le dichiarazioni sulla loro identità.

> <span style="text-decoration:underline;">Verificatori di identità:</span> terze parti che forniscono servizi previa verifica di alcune informazioni relative all'identità. Per esempio, se c'è un limite di età per comprare alcolici, o per guardare un film, il verificatore di identità (il negozio o il cinema) può convalidare la firma del governo che ha rilasciato e certificato questa credenziale. 


![alt_text](images/image2.jpg "image_tooltip")


Le credenziali sono firmate dai loro emittenti utilizzando la crittografia a chiave pubblica. Una volta firmate da un emittente, le credenziali possono essere gestite dal proprietario dell'identità per presentare rivendicazioni semplicemente utilizzando il loro wallet . I proprietari di identità usano il loro wallet per rivelare quali dati vogliono condividere con il mondo esterno. Possono decidere e controllare non solo con chi vogliono condividere i loro dati, ma anche quando condividerli. Per fare questo, hanno bisogno di dichiarare alla rete il loro consenso a condividere i dati selezionati con le istituzioni autorizzate. 

Sia gli emittenti che i proprietari di identità devono essere registrati su un registro pubblico con i loro DID. In una tale configurazione, i ledger distribuiti possono essere utilizzati per attestare l'autenticità dei dati e delle certificazioni, registrando solo "puntatori" indiretti ai fini della verifica. I ledger distribuiti possono essere usati come infrastruttura pubblica per facilitare la verifica dei dati relativi all'identità. Chiunque in una rete blockchain può verificare se una dichiarazione fatta da un proprietario di identità è valida e quali istituzioni hanno attestato la validità della dichiarazione, senza dover rivelare i dati stessi.

L'uso simultaneo della chiave privata e di un identificatore DID permette, ad esempio, al proprietario dell'identità di creare un codice QR che rappresenta quell'identificatore verificato. Scansionando il codice QR, un fornitore di servizi può ora sottomettere i dati ad una rete blockchain o un altro ledger distribuito e verificare se al DID di quella persona è associato un attestato di autenticità. La chiave pubblica viene utilizzata per attestare l'autenticità della firma dell'autorità emittente associata a una credenziale. Se l'attestazione e il DID corrispondono l'accesso è concesso, e l’interessato può qualificarsi per comprare alcolici, noleggiare un'auto, ecc. Oltre a questi dati certificati, qualsiasi altra informazione può essere associata a un DID e controllata direttamente dal proprietario dell'identità attraverso il software del wallet. Esempi di tali dati "non certificati" sono le cronologie di navigazione personale o i post sui social media. In uno scenario di questo tipo non occorrerebbe più fare affidamento su fornitori terzi di identità digitale come Google o Facebook. Il browser “Brave" è un esempio pratico di come un wallet Web3 permette il controllo diretto della propria identità (per approfondire: Parte 4 - Basic attention token).

I registri di revoca offrono agli emittenti di identità la possibilità di revocare un reclamo poiché alcuni dati relativi all'identità possono cambiare nel tempo. I dati personali come indirizzo, stato civile e numero di bambini possono cambiare nel tempo e quindi devono essere aggiornati.

Separare le operazioni di (i) emissione di una credenziale, (ii) avanzamento di una richiesta, e (iii) convalida di queste richieste con le credenziali è cruciale per una configurazione centrata sull'utente. Può essere visto come un sistema di controlli ed equilibri in un'economia guidata dai dati che garantisce il livello di autonomia e privacy relative alla propria identità digitale: una situazione molto diversa da come oggi è impostata la rete Internet.

KERI (Key Event Receipt Infrastructure) è una nuova tecnologia, un tipo di rete di consenso, che permette di spostare alcune funzioni dei sistemi decentralizzati di gestione dell'identità fuori dalla catena ponendoli ad un livello diverso, riducendo al minimo il ruolo del ledger distribuito. L'obiettivo è quello di fornire un sistema di gestione dell'identità semplice, scalabile, più modulare e più interoperabile tra reti blockchain diverse tra loro, o altri ledger distribuiti. È attualmente adottato da molti attori nel contesto dell'identità user-centrica, per il quale è in grado di agire come un catalizzatore.

  
## Prospettiva

Le soluzioni di identità user-centrica basate su ledger distribuiti e DID tendono a disintermediare l'industria dell'identità. Possono aumentare l'efficienza operativa con l'auditing on-the-fly e l'accesso diretto ai dati in tempo reale, riducendo i costi. Se impostate correttamente, forniscono una maggiore sicurezza dei dati e protezione dagli impostori, e forniscono una conformità normativa più efficiente, garantendo un maggiore controllo ai proprietari dei dati. Le soluzioni di identità user-centriche possono fornire la portabilità dei dati, fornendo a individui e istituzioni la possibilità di riutilizzare facilmente le credenziali per autenticarsi nuovamente per l’accesso a nuovi servizi. Per le aziende questo può ridurre i costi e il tempo per la registrazione dei clienti, i tassi di abbandono e i costi-opportunità complessivi legati a un processo di identificazione completo di tipo KYC (Know-Your-Customer).

Per l'archiviazione dei dati personali, le soluzioni di identità user-centrica possono utilizzare sia archivi di dati personali sia reti di archiviazione di file distribuiti. Le credenziali possono essere memorizzate direttamente sul dispositivo dell'utente o in modo sicuro presso un gestore privato di identità (o hub di identità) come "TrustGraph" o "3Box". I dati meno sensibili alla privacy possono essere gestiti collettivamente da reti di archiviazione di file distribuiti come "InterPlanetary File System" (IPFS) o "OrbitDB" per ridurre le ridondanze dei dati e disintermediare il processo di gestione delle identità. In entrambe le configurazioni la struttura dei dati è progettata in modo specifico per l'utente, e consente quindi interoperabilità tra fornitori di servizi diversi che possono usare lo stesso set di informazioni per scopi differenti. I dati degli utenti non sono vincolati a risiedere su una sola piattaforma.

Mentre alcune forme della cosiddetta crittografia a “zero-knowledge proof” sono già in uso nelle soluzioni di identità user-centrica, c'è ancora spazio per migliorare strumenti crittografici per preservare la privacy rendendoli ancora più forti. Un insieme di reti Web3 sta già lavorando per incorporare meccanismi crittografici più rispettosi della privacy nei ledger distribuiti, come la "Zero-Knowledge Proof" implementata da "Zcash," o le _Firme ad Anello_ (“Ring Signatures") implementato da "Monero," o per eseguire calcoli su informazioni criptate usando metodi di "Secure-Multi-Party-Computation" (per approfondire: Parte 3 - I privacy token). Da questo punto di vista KERI potrebbe rappresentare una soluzione totalmente innovativa.

Uno dei casi d'uso più interessanti nel prossimo futuro sarà l'identificazione digitale degli oggetti. Attualmente, la maggior parte dei dispositivi Internet-of-Things (IoT) non hanno alcuna identità digitale sicura nè capacità di gestione degli accessi. Un numero di serie basato su DID può rendere indirizzabile qualsiasi oggetto nel Web3. Una volta che iniziamo a etichettare gli oggetti utilizzando computer miniaturizzati (acceleratori crittografici) dotati di un numero di serie basato su DID e che comunicano con un ledger distribuito, qualsiasi oggetto lungo la catena di fornitura può dimostrare ad altri nella rete la proprietà e le credenziali utilizzando prove crittografiche. Gli oggetti che hanno una univoca identità Web3 e un wallet Web3 possono diventare entità economiche autonome e affidabili. Un tale "legame cyber-fisico" tra oggetti e DID permette un'efficace tracciabilità del prodotto e la condivisione dei dati sulla provenienza di beni e servizi tra produttori e consumatori.

Tra le più rilevanti soluzioni di gestione di identità basate su Web3 figurano:  “[Ageify](https://age-ify.com/),” “[Civic](https://www.civic.com/),” “[Edge](https://edge.app/),” “[Hu-manity.co](http://hu-manity.co/),”  “[Jolocom](https://jolocom.io/),”  “[Keyp](https://keyp.io/),” “[Madana](https://www.madana.io/),” “[Metadium](https://www.metadium.com/),” “[NewBanking Identity](https://newbanking.com/),”“[ObjectTech](https://www.objecttechgroup.com/),” “[THEKEY](https://www.thekey.vip/#/homePage),” “[Trusti,”](https://trusti.com/) “[PeerMountain](https://www.peermountain.com/),” “[REMME](https://remme.io/),” “[Riddle & Code](https://www.riddleandcode.com/ ),” “[Spherity](https://spherity.com/),” “[uPort](https://www.uport.me/),”“[UniquID](https://uniquid.com/),” “[ValidatedID](https://www.validatedid.com/),” and “[WoTT](https://www.wott.io/).” 


### Riassunto del capitolo 

> Storicamente strumenti  di identità come passaporti, patenti di guida, codice fiscale o numeri di serie per le merci sono stati emessi da istituzioni centralizzate come i governi locali e nazionali e altre istituzioni fidate. L'emergere di Internet ha creato la necessità di sistemi di identificazione digitale.

> Da un punto di vista informatico il termine "identità" può essere ridotto agli elementi informativi relativi al processo di gestione dell'identità: "identificatore", "autenticazione" e "credenziali".

> Gli identificatori sono necessari per identificare in modo univoco una persona, un'istituzione o un oggetto. Un identificatore deve essere unico e persistente nel tempo.

> L'autenticazione è il processo con il quale una persona, un'istituzione o un oggetto può dimostrare di essere chi dice di essere. Una persona può autenticarsi dimostrando il possesso di un oggetto (carta d'identità, portafoglio hardware, portafoglio software), la conoscenza di un segreto (password o PIN), o una proprietà personale (dati biometrici, firma). Spesso si usa una combinazione di questi sistemi.

> Un'identità è inutile senza collegare all’identificatore i dati relativi a una persona (dati personali), un'istituzione (dati istituzionali) o un oggetto (dati relativi all'oggetto).

> L'attuale Internet è stata costruita intorno alla connessione di macchine, non di persone. Internet non fornisce un livello di identità nativo per persone, istituzioni o oggetti diversi dai nodi operativi in una rete di computer. Soluzioni a questa carenza sono state costruite a livello di applicazione utilizzando database interni (infrastruttura privata) per gestire tutti i dati coinvolti nei processi di gestione dell'identità digitale. Tutti i dati relativi agli utenti sono gestiti dal fornitore di servizi, su una infrastruttura server privata, e tutti gli elementi relativi al processo di gestione dell'identità sono centralizzati. 

> Questi silos di dati e le soluzioni di identità proprietarie hanno portato a notevoli costi e compromessi, sia per le aziende che per gli utenti, come (i) il caos delle password, (ii) la protezione contro soggetti malevoli, (iii) la protezione dei dati e i costi di custodia, (iv) la portabilità dei dati, (v) la mancanza di controllo e sovranità sui dati, e (vi) la ricentralizzazione di Internet.

> Le reti Blockchain e ledger distribuiti analoghi usano la crittografia a chiave pubblica per l'identificazione di tutti gli attori della rete, ma sono insufficienti per una fiorente economia tokenizzata. Tuttavia, combinati con i DID, possono offrire componenti fondamentali per soluzioni di identità più "user-centric" adatte al Web3, e fornire più privacy e controllo rispetto alle soluzioni "server-centric" usate nel Web2.

> Il processo di identità user-centrica richiede tre attori: (i) emittenti di identità, (ii) proprietari di identità, e (iii) verificatori di identità. Se impostato correttamente, chiunque in una rete blockchain può verificare se un dato (credenziale) è valido e quali istituzioni hanno certificato la validità dei dati, senza rivelare i dati stessi.

> Mentre i dati in chiaro non dovrebbero mai essere memorizzati su un ledger pubblico, un sistema di gestione dell'identità che preservi la privacy può usare ledger distribuiti per permettere a una persona di provare che i suoi dati personali relativi all'identità soddisfano certi requisiti senza rivelare i dati effettivi. In tale configurazione, i ledger distribuiti possono essere utilizzati per certificare l'autenticità dei dati e delle attestazioni, registrando solo "puntatori" indiretti ai fini della verifica.

> Un utente può creare e registrare un DID quando attiva un wallet blockchain, che genera una coppia di chiavi (privata e pubblica). La crittografia a chiave pubblica è usata per l'autenticazione e la crittografia. Solo la chiave privata può provare la propria identità. La chiave privata agisce come blocco personale del wallet.

> Qualsiasi DID può essere collegato ad attestati (credenziali verificabili) rilasciati da altre persone e istituzioni che certificano caratteristiche specifiche per un utente (proprietario di identità) come nome, indirizzo, email, età, titoli di studio, o altre certificazioni come la patente di guida. Le credenziali sono firmate dai rispettivi emittenti utilizzando la crittografia a chiave pubblica. Una volta firmate da un emittente, le credenziali possono essere gestite utilizzando direttamente il wallet del proprietario dell'identità.

> La separazione di "identificatore", "autenticazione" e "dati" è cruciale per una configurazione centrata sull'utente. Può essere visto come un sistema di controlli ed equilibri in un'economia guidata dai dati che garantisce il livello di autonomia e privacy sulla propria identità, i modo molto diverso da come è impostata oggi la rete Internet. L’uso di una infrastruttura pubblica come un ledger distribuito mantenuto collettivamente come fonte unica di verità, separando allo stesso tempo i ruoli nel processo di gestione dell'identificazione, rende i sistemi di gestione dell'identità user-centrici "decentralizzati". \
~ \
Il wallet agisce come un contenitore personale che ti permette di controllare le tue identità digitali. Il wallet è l'equivalente digitale di un portafoglio fisico, che di solito funge da contenitore per tutti i documenti di identità come patente, carta bancaria, abbonamento alla palestra, carta d'identità nazionale, codice fiscale, o carte fedeltà, oltre al tuo denaro. Inizialmente vuoto, il wallet nel tempo si può riempire con credenziali che rappresentano la versione digitale della patente di guida, della carta bancaria, dell'abbonamento alla palestra, della carta d'identità nazionale, del codice fiscale, delle carte fedeltà, ecc.

> Così come apriamo il nostro portafoglio per mostrare la carta d'identità, è necessario attivare il wallet Web3 per mostrare le credenziali digitali a terzi (utilizzando una password). Nessuno può vedere il contenuto del wallet Web3 senza il nostro consenso. Siamo noi a scegliere con chi condividere queste credenziali. Il contenuto del wallet rimane nascosto fino a quando scegliamo di rivelare qualcosa. Il wallet digitale è portatile, come un dispositivo hardware dedicato o un'applicazione nel nostro cellulare o notebook.


### Riferimenti e approfondimenti

_* Allan, Christoper: “The Path to Self-Sovereign Identity,” March 1 2017, [https://github.com/ChristopherA/self-sovereign-identity/blob/master/ThePathToSelf-SovereignIdentity.md](https://github.com/ChristopherA/self-sovereign-identity/blob/master/ThePathToSelf-SovereignIdentity.md)_

_* Ellison,[ ](http://irl.cs.ucla.edu/index.html)Carl: “Establishing Identity without Certification Authority,” 1996, [https://irl.cs.ucla.edu/index.html](https://irl.cs.ucla.edu/index.html)_

_* Feisthammel, Patrick: “[Pretty good Privacy, PGP](https://www.rubin.ch/pgp/weboftrust.en.html), Web of Trust,” Oct 7 2004, [https://www.rubin.ch/pgp/weboftrust.en.html](https://www.rubin.ch/pgp/weboftrust.en.html)_

_* Jordan, Ken; Hauser, Jan; Foster, Steven: “The Augmented Social Network,” White paper, 2000, [https://firstmonday.org/ojs/index.php/fm/article/view/1068/988](https://firstmonday.org/ojs/index.php/fm/article/view/1068/988)_

_* Kameron, Kim: “The Laws of Identity,” March 2007, [https://docs.microsoft.com/en-us/previous-versions/dotnet/articles/ms996456(v=msdn.10)?redirectedfrom=MSDN](https://docs.microsoft.com/en-us/previous-versions/dotnet/articles/ms996456(v=msdn.10)?redirectedfrom=MSDN)_

_* Kütt, Andres: "MyData Webinar #5: Identity in the Digital Era," Mydata Global, Youtube Video, retrieved from: [https://www.youtube.com/watch?v=XjzJeys7PvM&fbclid=IwAR0qMDGYuZVk0c6aDHOX46AdFQMGdsI24SSZ6-lMfj7XZY-TrbkbT5LFlqk](https://www.youtube.com/watch?v=XjzJeys7PvM&fbclid=IwAR0qMDGYuZVk0c6aDHOX46AdFQMGdsI24SSZ6-lMfj7XZY-TrbkbT5LFlqk)_

_* Many authors: “[Rebooting the Web of Trust](http://www.weboftrust.info/papers.html),” Papers and Specs, [http://www.weboftrust.info/papers.html](http://www.weboftrust.info/papers.html)_

_* Many authors: “Charta for Digital Human Rights,” Version: 01.12.2016 Unofficial English translation of the German original text, published by ZEIT-Stiftung Ebelin und Gerd Bucerius [https://digitalcharta.eu/wp-content/uploads/2016/12/Digital-Charta-EN.pdf](https://digitalcharta.eu/wp-content/uploads/2016/12/Digital-Charta-EN.pdf)_

_* Many authors: “Self-sovereign Identity A position paper on blockchain enabled identity and the road ahead,”  October 23 2018, Identity Working Group of the German Blockchain Association, [https://www.bundesblock.de/wp-content/uploads/2019/01/ssi-paper.pdf](https://www.bundesblock.de/wp-content/uploads/2019/01/ssi-paper.pdf)_

_* Many authors: “The Respect Trust Framework, “ Version 2.1,  Feb 2016,  [https://oixnet.org/wp-content/uploads/2016/02/respect-trust-framework-v2-1.pdf](https://oixnet.org/wp-content/uploads/2016/02/respect-trust-framework-v2-1.pdf)_

_* Marlinspike, Moxie: “Sovereign Source Authority,” Moxytongue, Feb 2012, [https://www.moxytongue.com/2012/02/what-is-sovereign-source-authority.html](https://www.moxytongue.com/2012/02/what-is-sovereign-source-authority.html)_

_* Miller, Ron: "[The Promise of managing identities on the blockchain](https://techcrunch.com/2017/09/10/the-promise-of-managing-identity-on-the-blockchain/?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_recent_activity_details_all%3BknkLT7NkR5Cex9bx3zogKg%3D%3D),” Sep 10, 2017, [https://techcrunch.com/2017/09/10/the-promise-of-managing-identity-on-the-blockchain/?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_recent_activity_details_all%3BknkLT7NkR5Cex9bx3zogKg%3D%3D&guccounter=1](https://techcrunch.com/2017/09/10/the-promise-of-managing-identity-on-the-blockchain/?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_recent_activity_details_all%3BknkLT7NkR5Cex9bx3zogKg%3D%3D&guccounter=1)_

_* Mire, Sam: “Blockchain Research Technologies Blockchain For Identity Management: 7 Possible Use Cases” Dec 5 2018, [https://www.disruptordaily.com/blockchain-use-cases-identity-management/](https://www.disruptordaily.com/blockchain-use-cases-identity-management/)_

_* N.N.: “Enterprise Ethereum Blockchain in Digital Identity,” Consensys website, [https://consensys.net/blockchain-use-cases/digital-identity/#usecases](https://consensys.net/blockchain-use-cases/digital-identity/#usecases)_

_* N.N.: “Identity Management with Blockchain: The Definitive Guide (2020 Update),”  TYKN website: [https://tykn.tech/identity-management-blockchain/](https://tykn.tech/identity-management-blockchain/)_

_* Preukschat, Alex; Reed , Drummond: "Self-Sovereign Identity Decentralized Digital Identity and Verifiable Credentials" MEAP began December 2019  Publication in January 2021 (estimated) ISBN 9781617296598  300 pages (estimated), electronically retrieved from:[https://www.manning.com/books/self-sovereign-identity](https://www.manning.com/books/self-sovereign-identity)_

_* Reed, Drummond; Tobin, Andrew: “[Sovereign White Paper](https://sovrin.org/wp-content/uploads/2017/07/The-Inevitable-Rise-of-Self-Sovereign-Identity.pdf),” Sept 29 2016, [https://sovrin.org/wp-content/uploads/2017/07/The-Inevitable-Rise-of-Self-Sovereign-Identity.pdf](https://sovrin.org/wp-content/uploads/2017/07/The-Inevitable-Rise-of-Self-Sovereign-Identity.pdf)_

_* Reed, Drummond; Sabadello, Markus: "Chapter 8 Decentralized identifiers" in Self Sovereign Identity, retrieved from on October 27, 2020: in [https://livebook.manning.com/book/self-sovereign-identity/chapter-8](https://livebook.manning.com/book/self-sovereign-identity/chapter-8)_
_* Ruff, Timothy: "When Explaining SSI, Start with the Wallet," Apr 21 2020, [https://medium.com/@rufftimo/when-explaining-ssi-start-with-the-wallet-bee5d2af6696](https://medium.com/@rufftimo/when-explaining-ssi-start-with-the-wallet-bee5d2af6696)_

_* Sabadello, Markus: “Human Rights in the Information Society,” 2011, [https://danubetech.com/download/Human-Rights-in-the-Information-Society.pdf](https://danubetech.com/download/Human-Rights-in-the-Information-Society.pdf)_

_* Shea, Michael;Smith, Samuel M.; Stöcker,Carsten, Caballero, Juan; Condon, Matt G.: “Decentralized Identity as a Meta-platform: How Cooperation Beats Aggregation a white paper from Rebooting the Web of Trust IX, [https://nbviewer.jupyter.org/github/WebOfTrustInfo/rwot9-prague/blob/master/final-documents/CooperationBeatsAggregation.pdf](https://github.com/SmithSamuelM/rwot9-prague.githttps://nbviewer.jupyter.org/github/WebOfTrustInfo/rwot9-prague/blob/master/final-documents/CooperationBeatsAggregation.pdf)_

_* Spike, Marlin: “Self Sovereign Identity, how the term has evolved,” Feb 2016, [https://www.moxytongue.com/2016/02/self-sovereign-identity.html](https://www.moxytongue.com/2016/02/self-sovereign-identity.html)_

_* Smith, Samuel M.: "Key Event Receipt Infrastructure (KERI)", Cornell University, retrieved from: [https://arxiv.org/abs/1907.02143](https://arxiv.org/abs/1907.02143)_

_* Smolenski, Natalie: ”The EU General Data Protection Regulation and the Blockchain,” Aug 2 2017, [https://medium.com/learning-machine-blog/the-eu-general-data-protection-regulation-and-the-blockchain-1f1d20d24951](https://medium.com/learning-machine-blog/the-eu-general-data-protection-regulation-and-the-blockchain-1f1d20d24951)_

_* Stöcker, Carsten: “The Economic Value of Decentralized Identity — Part 2 Reimagining the economics of trust and reputation,” Mar 11 2020, [https://medium.com/spherity/the-economic-value-of-decentralized-identity-part-2-733aa977eaf8](https://medium.com/spherity/the-economic-value-of-decentralized-identity-part-2-733aa977eaf8)_

_* Stöcker, Carsten: “Spherity’s Identity Tech Predictions for the decade of the 2020’s — Part 1,” Jan 16 2020 [https://medium.com/spherity/spheritys-identity-tech-predictions-for-the-decade-of-the-2020-s-part-1-410bc9b48be4](https://medium.com/spherity/spheritys-identity-tech-predictions-for-the-decade-of-the-2020-s-part-1-410bc9b48be4)_

_* Stöcker, Carsten: “Spherity’s Identity Tech Predictions for the decade of the 2020’s — Part 2,” Feb 13 2020 [https://medium.com/spherity/spheritys-identity-tech-predictions-for-the-decade-of-the-2020-s-part-2-6e480d2a57ea](https://medium.com/spherity/spheritys-identity-tech-predictions-for-the-decade-of-the-2020-s-part-2-6e480d2a57ea)_

_* Stöcker, Carsten: “SSI201: Upgrading products with intelligent serial numbers and DIDs How smart can an object’s identifier be? How can it enable cradle-to-grave traceability and other innovative capabilities?” Nov 26, 2019 ·, [https://medium.com/spherity/ssi201-upgrading-products-with-intelligent-serial-numbers-and-dids-78da623b91dd](https://medium.com/spherity/ssi201-upgrading-products-with-intelligent-serial-numbers-and-dids-78da623b91dd)_

_* Stöcker, Karsten: "KERI: A more Performant Ledger for Trusted Identities Securing the control of decentralized identifiers at the root with ambient verifiability", Medium, Sperity Blog, July 2 2020, [https://medium.com/@cstoecker](https://medium.com/@cstoecker)_

_* Voshmgir, Shermin: “Identity as a Bottleneck for Blockchain,” Oct 17, 2017, [https://stories.jolocom.com/identity-blockchain-the-road-to-self-sovereign-identity-f9f4439c52cb](https://stories.jolocom.com/identity-blockchain-the-road-to-self-sovereign-identity-f9f4439c52cb)_

_* Voshmgir, Shermin: “Self Sovereign — Identity vs Data?” Feb 27 2018, [https://stories.jolocom.com/self-sovereign-identity-vs-data-5abe5947a62](https://stories.jolocom.com/self-sovereign-identity-vs-data-5abe5947a62)_

_* Wikipedia contributors: "Pretty Good Privacy," Wikipedia, The Free Encyclopedia, https://en.wikipedia.org/w/index.php?title=Pretty_Good_Privacy&oldid=959437666 (accessed May 31, 2020)._

_* Zuboff, Shoshana: “ The Age of Surveillance Capitalism: The Fight for a Human Future at the New Frontier of Power.” New York: PublicAffairs, 2019._

_* Ageif: [https://age-ify.com/](https://age-ify.com/)_

_* Civic: [https://www.civic.com/wallet/](https://www.civic.com/wallet/)_

_* Edge: https://edge.app/_

_* General Data Protection Regulation (GDPR): [https://gdpr-info.eu/](https://gdpr-info.eu/)_

_* Hu-manity.co: [https://hu-manity.co/](https://hu-manity.co/)_

_* Jolocom: [https://jolocom.io/](https://jolocom.io/)_

_* Keyp: [https://keyp.io/](https://keyp.io/)_

_* List of Blockchain & Identity Solutions: [https://github.com/peacekeeper/blockchain-identity](https://github.com/peacekeeper/blockchain-identity)_

_* Madana: [https://www.madana.io/](https://www.madana.io/)_

_* Metadium: [https://www.metadium.com/](https://www.metadium.com/)_

_* NewBanking Identity: [https://newbanking.com/#/](https://newbanking.com/#/)_

_* ObjectTech: [https://www.objectivetgg.com/](https://www.objectivetgg.com/)_

_* THEKEY: [https://www.thekey.vip/#/homePage](https://www.thekey.vip/#/homePage)_

_* Trusti: [https://trusti.com/](https://trusti.com/)_

_* PeerMountain: [https://www.peermountain.com/](https://www.peermountain.com/)_

_* PGP WOT: [https://www.linux.com/training-tutorials/pgp-web-trust-core-concepts-behind-trusted-communication/](https://www.linux.com/training-tutorials/pgp-web-trust-core-concepts-behind-trusted-communication/)_

_* Rebooting the Web of Trust:[http://www.weboftrust.info/papers.html](http://www.weboftrust.info/papers.html)_

_* REMME: [https://remme.io/](https://remme.io/)_

_* Riddle & Code: [https://www.riddleandcode.com/](https://www.riddleandcode.com/)_

_* Spherity: [https://spherity.com/](https://spherity.com/)_

_* SPKI/SDSI project: [http://world.std.com/~cme/html/spki.html](http://world.std.com/~cme/html/spki.html)_

_* SoLid (Social Linked Data: [https://github.com/solid/solid-spec](https://github.com/solid/solid-spec)_

_* uPort: [https://www.uport.me/](https://www.uport.me/)_

_* UniquID: [https://uniquid.com/](https://uniquid.com/)_

_* ValidatedID: [https://www.validatedid.com](https://www.validatedid.com/)_

_* WebIDs: [https://www.w3.org/2005/Incubator/webid/spec/tls/](https://www.w3.org/2005/Incubator/webid/spec/tls/)_

_* WoTT: [https://wott.io/](https://wott.io/)_

_* W3C working group on verifiable claims: [https://www.w3.org/2017/vc/WG/](https://www.w3.org/2017/vc/WG/)_

_* W3C Verifiable Claims Task Force FAQ: [https://w3c.github.io/webpayments-ig/VCTF/charter/faq.html](https://w3c.github.io/webpayments-ig/VCTF/charter/faq.html)_

_* W3C initiative of Decentralized Identifiers (DIDs): [https://w3c.github.io/did-core](https://w3c.github.io/did-core/)_

## Note a piè di pagina

[^1]:
Sovereign Website: [https://sovrin.org/wp-content/uploads/2017/07/The-Inevitable-Rise-of-Self-Sovereign-Identity.pdf](https://sovrin.org/wp-content/uploads/2017/07/The-Inevitable-Rise-of-Self-Sovereign-Identity.pdf)

[^2]:
Come Zuboff, Shoshana in "L'era del capitalismo di sorveglianza: La lotta per un futuro umano alla nuova frontiera del potere". New York: PublicAffairs, 2019. Zuboff descrive la mercificazione delle informazioni personali. Descrive la tendenza all'accumulo di dati, criticando che molte aziende e istituzioni raccolgono e capitalizzano i dati personali senza meccanismi di consenso. Confronta il "capitalismo industriale" e il "capitalismo di sorveglianza", spiegando il "capitalismo industriale" come sfruttamento della natura, e il "capitalismo di sorveglianza" come sfruttamento della natura umana.

[^3]:
ICANN (Internet Corporation for Assigned Names and Numbers) è un'organizzazione senza scopo di lucro che coordina il mantenimento e le procedure di diversi database relativi agli spazi dei nomi e agli spazi numerici di Internet, garantendo il funzionamento stabile e sicuro della rete. È un gruppo multi-stakeholder con sede negli Stati Uniti.

