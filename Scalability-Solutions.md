> _**Una delle più grandi sfide di un consenso distribuito come il Proof-of-Work è che, pur rendendo la rete sicura, non scala facilmente. Questo è dovuto al compromesso tra decentralizzazione, sicurezza e scalabilità.**_

Disclaimer: La ricerca e lo sviluppo sulle soluzioni di scalabilità è ancora in corso e influenzata dagli eventi attuali. Questo capitolo darà una panoramica generale, ma non è affatto completo nel delineare tutte le possibili soluzioni e/o i loro compromessi.  

Il "trilemma della scalabilità" descrive il compromesso nel consenso distribuito tra decentralizzazione, sicurezza e scalabilità.  La decentralizzazione è la premessa di una rete distribuita, la sicurezza è l'aspetto più importante quando la rete coinvolge un insieme di attori non fidati, e la scalabilità si riferisce al numero di transazioni che un sistema può elaborare al secondo. Per permettere un alto grado di inclusione di nodi computazionalmente più deboli, la dimensione del blocco in una rete Proof-of-Work è limitata e i blocchi sono creati con un ritardo. Altrimenti, poiché i blocchi più grandi sono più difficili da elaborare, la latenza della rete impedirebbe ai nodi più deboli di partecipare al processo di creazione del blocco. Tali limitazioni, tuttavia, riducono la quantità di transazioni che possono essere convalidate in un dato lasso di tempo e, di conseguenza, i meccanismi Proof-of-Work sono sicuri ma presentano limiti di scalabilità. Nei primi tempi delle reti blockchain, la scalabilità era poco considerata dalla comunità degli sviluppatori, poiché il traffico in quelle reti era ancora basso. Oggi la scalabilità delle reti blockchain pubbliche è uno dei principali colli di bottiglia per la adozione di massa, ed è anche una delle tematiche di ricerca e sviluppo su cui si lavora di più..

La scalabilità di Blockchain è paragonabile ai primi giorni di Internet, i tempi in cui si tiravano cavi telefonici attraverso i nostri appartamenti per collegare a Internet i nostri computer. Per quanto riguarda la connessione, la larghezza di banda era bassa e la comunicazione era lenta; si doveva aspettare che le pagine si accumulassero pixel per pixel. L'introduzione dei modem a 56k era considerata un grande miglioramento rispetto al modem a 28k, ma lo streaming video era considerato un sogno lontano. Questi problemi sono stati alla fine risolti, e certamente non hanno fermato l'evoluzione di Internet fino a diventare quello che è oggi. Nel contesto delle reti blockchain, sono state proposte molte soluzioni per rendere le transazioni più veloci ed economiche, pur mantenendo la sicurezza e un certo livello di decentralizzazione. Le soluzioni di scalabilità possono affrontare questi problemi a (i) livello di protocollo, o a (ii) livello di secondo strato. 

Quando sono affrontati a livello di protocollo, spesso portano alla centralizzazione. Un maggior volume di transazioni al secondo spesso richiede la concessione di più poteri a certi nodi, aumentando così il livello di centralizzazione. Meccanismi alternativi di consenso cercano di risolvere il problema della scalabilità introducendo qualche tipo di livello di autorizzazione per garantire la fiducia. Il capitolo "Bitcoin, Blockchain e Altri Distributed Ledger" presente nella prima parte di questo libro ha un intera sezione dedicata ad elencare soluzioni alternative di ledger distribuiti e protocolli di consenso che cercano - tra l'altro - di risolvere le questioni di throughput. Le soluzioni più popolari per raggiungere livelli più alti di throughput sono protocolli di consenso alternativi come la Proof of Stake delegata (dPoS), la practical Bizantine Fault Tolerance (pBFT), o le reti autorizzate. Altri mezzi per affrontare il problema della scalabilità a livello di protocollo sono lo sharding del ledger o algoritmi crittografici alternativi, descritti in questo capitolo. 

Come alternativa, sono stati fatti vari tentativi per spostare le soluzioni di scalabilità su un secondo livello, come le "catene laterali" o i "canali di stato". In entrambi i casi le interazioni degli utenti vengono spostate dal livello della blockchain a un secondo "strato", garantendo allo stesso tempo transazioni P2P senza rischi tra i partecipanti.

## Canali di Stato

I canali di stato offrono un secondo livello al di sopra di una rete blockchain, permettendo alle transazioni che potrebbero avvenire sulla catena di essere completate fuori dalla catena, mantenendo la sicurezza di tutti i partecipanti alla rete. In questo processo, gli insediamenti delle transazioni sono esternalizzati ad un canale di stato privato, che potrebbe essere descritto come un percorso a due vie tra due utenti. Questi canali di stato sono formalizzati ed elaborati da uno smart contract. I "canali di stato" permettono il trasferimento di qualsiasi informazione per qualsiasi tipo di applicazione decentralizzata. I "canali di pagamento" permettono solo il trasferimento di pagamenti. Sono utili se due parti, Alice e Bob, hanno una relazione commerciale in corso con continui pagamenti avanti e indietro. 

I token sono temporaneamente bloccati come meccanismo di sicurezza nel caso si manifestino controversie: (i) I token possono essere inviati da Alice a Bob e viceversa usando i canali di stato nel quale sono bloccati tramite uno schema a più firme o uno smart contract per un periodo di tempo predefinito. (ii) Sia Alice che Bob firmano ogni transazione con la loro chiave privata, ma le transazioni sono tenute private e non vengono trasmesse alla rete blockchain. (iii) Dopo che il periodo è passato, il saldo di tutte le transazioni bilaterali viene trasmesso alla rete blockchain, che chiude il canale di stato. 

Supponiamo che Alice abbia 200 ETH e Bob abbia 100 ETH. In un certo periodo di tempo, Alice invia dieci pagamenti di 10 ETH e Bob invia ad Alice due pagamenti di 25 ETH. Se tutte le transazioni fossero regolate direttamente sulla rete Ethereum, i nodi della rete registrerebbero dodici transazioni individuali. Non solo questo farebbe aumentare il numero di transazioni e rallenterebbe quindi la rete, ma sarebbe anche più costoso sia per Alice che per Bob, poiché ogni singola transazione incorrerebbe in una fee di transazione. Usando un canale di stato per regolare tali transazioni bilaterali, solo il saldo di tutte le transazioni deve essere scritto direttamente sulla blockchain una volta passato il tempo predefinito. Questo significa che solo due transazioni saranno registrate dalla rete: le transazioni di apertura e chiusura del canale.

![alt_text](images/image1.jpg "image_tooltip")

Mantenere le transazioni off-chain (fuori dalla catena) ed esclusivamente tra entrambe le parti non è solo più economico e veloce, ma anche più rispettoso della privacy. Tutto avviene all'interno di un canale, piuttosto che essere trasmesso pubblicamente su tutta la rete. Le uniche transazioni che sono registrate sulla catena e visibili al pubblico sono quelle di apertura e chiusura. Il lato negativo di questo processo è che i canali di stato hanno bisogno della piena disponibilità di tutti i partecipanti coinvolti. Altrimenti, se la chiusura finale del canale, e quindi la presentazione finale dello stato, dovesse essere presentata da un attore malevolo, i token potrebbero essere a rischio. Per contestare gli attacchi malevoli i token bloccati possono essere trattenuti dal contratto intelligente per penalizzare l'attaccante. Questo richiede un monitoraggio e potrebbe essere esternalizzato a terzi, i cosiddetti "contratti giudice", in cambio di una fee. I canali di stato sono quindi utili solo nei casi in cui i partecipanti si scambiano molti aggiornamenti di stato per un lungo periodo di tempo, per mitigare il costo iniziale della creazione di un canale e della distribuzione di un contratto giudice.

Lo smart contract usato per bloccare lo stato deve conoscere in anticipo i partecipanti ad un dato canale. I canali di stato funzionano bene con un insieme definito di partecipanti, ma l'aggiunta e la rimozione dei partecipanti richiede un cambiamento nello smart contract, o la creazione di un nuovo canale. Progetti come Lightning Network (Bitcoin) o Raiden Network (Ethereum) hanno proposto soluzioni basate su una rete di partecipanti, creando una rete di tutti i canali in modo da non dover creare un nuovo canale per ogni nuovo partecipante. Le transazioni possono essere instradate sui canali di altre persone, ma solo fino a quando c'è una connessione diretta del canale sulla rete. Ecco una lista selezionata di soluzioni di canali di stato per varie reti blockchain con diversi gradi di maturità e successo: “[Celer](http://www.celer.network/),” “[Counterfactual](http://www.counterfactual.com/),” “[Fun Fair](https://funfair.io/),” “[Liquidity](https://liquidity.network/),” “[Lightning](https://lightning.network/)” “[Machinomy](https://machinomy.com/),” “[Perun](http://www.perun.network/),” “[Raiden](https://raiden.network/),”  “[Spankchain](https://spankchain.com/),” o  “[Trinity](https://trinity.tech/).” La maggior parte delle soluzioni sono specializzate su una rete blockchain - come Bitcoin, Ethereum o Neo -, altre sono agnostiche.


## Sidechains 

Le sidechains sono reti blockchain separate, compatibili con la mainchain. Le sidechain hanno il proprio meccanismo di consenso, il proprio livello di sicurezza e i propri token. La sidechain non deve necessariamente essere pubblica e può anche essere un ledger gestito privatamente. Se la sicurezza di una rete sidechain è compromessa, il danno non influenzerà la mainchain o altre sidechain. Le due reti sono collegate tra loro tramite un "peg bidirezionale" e possono trasferire qualsiasi informazione. In questo modo, i token possono essere scambiati ad un tasso predeterminato tra la mainchain e la sidechain. La mainchain garantisce la sicurezza generale e la risoluzione delle controversie, e le transazioni che sono esternalizzate alla sidechain possono sacrificare la decentralizzazione in cambio della scalabilità. 

A differenza dei canali di stato, le transazioni che avvengono su una sidechain non sono private tra i partecipanti di una transazione. Sono pubblicate sulla rete sidechain e quindi visibili a chiunque abbia accesso al ledger. Alice e Bob non devono essere sempre disponibili, e non ci sono costi amministrativi extra per aggiungere o rimuovere partecipanti. Creare una sidechain, tuttavia, è molto costoso in quanto comporta la costruzione di un'intera infrastruttura da zero.

![alt_text](images/image2.jpg "image_tooltip")

La sidechain interagisce con il livello di calcolo sulla mainchain e richiede che i token siano bloccati per facilitare le controversie. Un gruppo di server (federazione) media tra una mainchain e le sue sidechain e determina quando i token che un utente ha usato vengono bloccati e rilasciati. Questo aggiunge un altro livello di sicurezza tra la mainchain e la sidechain. La federazione è scelta dagli sviluppatori della sidechain. Tuttavia, tale federazione aggiunge un altro livello tra la mainchain e la sidechain e potrebbe introdurre ulteriori vettori di attacco. Ecco un elenco selezionato di soluzioni sidechain per varie reti blockchain con diversi gradi di maturità e successo: "Bitcoin Codex," "Bitcoin Extended", “[Elements Projects](https://elementsproject.org/)”, “[Hivemind](http://bitcoinhivemind.com)”, “[Loom](https://loomx.io/)”, “[Liquid](https://blockstream.com/liquid/)”, “[Mimblewimble](https://github.com/mimblewimble/grin)”, “[Plasma](https://plasma.io/)”, “[Poa Network](https://poa.network/)”, o “[Rootstock](https://www.rsk.co/).” 


## Interoperabilità tra Blockchain

Il numero di reti blockchain e altri ledger distribuiti sta crescendo. Tuttavia, tutti questi sistemi di ledger distribuiti sono, per la maggior parte, sistemi isolati e lavorano come silos. Le reti non hanno alcuna conoscenza dello stato dei token gestiti in altre reti. Inoltre non hanno visibilità della capacità disponibile in altre reti per elaborare transazioni. Le sidechain potrebbero essere viste come un primo passo verso la piena interoperabilità e scalabilità della blockchain. Una soluzione più efficace e globale potrebbe essere fornita da reti di interoperabilità, come[ “Cosmos](https://cosmos.network/),”[ “Polkadot](https://polkadot.network/),” o[ “Wanchain](https://wanchain.org/),” che potrebbero risolvere il problema della scalabilità per più reti contemporaneamente.

L'interoperabilità, nel contesto dei ledger distribuiti, si riferisce alla capacità di condividere liberamente i token e i dati correlati tra reti diverse. In un ambiente completamente interoperabile, un utente della rete A potrebbe inviare token ad un altro utente della rete B senza la necessità di un intermediario, come un exchange centralizzato. L'interoperabilità della blockchain è un'idea contraria a ciò che alcuni ipotizzano possa accadere: una situazione nella quale, a causa degli effetti di rete, solo una rete blockchain sopravviverà nel lungo periodo. L'idea di "una catena che le domini tutte" è contraria all'idea principale della decentralizzazione. Il futuro del Web3 potrebbe, quindi, dipendere dalla capacità delle reti blockchain di interagire tra loro.


## Sharding

Alcuni sviluppatori propongono che lo sharding dello stato della rete potrebbe essere una soluzione al problema della scalabilità delle reti blockchain. Lo sharding è un concetto adottato dai database distribuiti, che non è stato ancora testato su scala globale nel contesto delle reti blockchain. Lo sharding potrebbe rispondere ai vincoli di scalabilità degli attuali protocolli di consenso, nei quali ogni nodo deve aggiornare regolarmente il proprio libro mastro e mantenere la storia completa, dal blocco della genesi fino ad oggi. Si suggerisce che la storia del ledger potrebbe essere divisa in pezzi separati, ognuno dei quali avrebbe il proprio "shard" ("scheggia") dello stato della rete. Più shard sono mantenuti da diversi nodi di rete in parallelo tra loro, migliorando così la scalabilità complessiva della rete. Gli shard rappresenterebbero dei "sotto-stati", parti dell'intero stato della rete. La rete nel suo complesso dovrebbe ancora operare sotto un unico stato, ma ogni shard dovrebbe essere coerente in se stesso. La comunicazione tra shard sarebbe gestita attraverso regole di protocollo. In un tale processo, gli indirizzi della blockchain, i bilanci e lo stato generale sarebbero contenuti negli shard. Gli shard forniscono prove alla mainchain e possono comunicare con altri shard attraverso un apposito protocollo di sharding. Esempi di progetti che lavorano su soluzioni di sharding sono:[ “Prysmatic Labs](https://prysmaticlabs.com/)”,[ “Drops of Diamond](https://github.com/Drops-of-Diamond/diamond_drops)”,[ “Status](https://medium.com/@status.im)” e[ “PegaSys](https://medium.com/@pegasyseng)”. 


## Algoritmi Crittografici Alternativi

Una delle maggiori sfide della rete Bitcoin e di reti simili è la gestione delle transazioni non spese. Queste transazioni contribuiscono alla crescita esponenziale del ledger. In Bitcoin, per esempio, sono chiamate UTXO, e contribuiscono a un carico maggiore, transazioni più costose e un throughput più basso. Quando una nuova transazione grezza viene creata e successivamente convalidata, prima della firma gli input possono provenire solo da output non spesi di transazioni precedenti. Pertanto, per la creazione di transazioni, la convalida e la firma, le transazioni non spese sono più importanti di quelle spese (output). Per la coerenza del ledger, le transazioni non spese sono importanti per operazioni come il timestamping, la prova di esistenza, l'immagazzinamento dei dati, e anche la creazione di blocchi e il mining. Le reti blockchain orientate alle transazioni sono tutte centrate sulle transazioni non spese. Questo è il motivo per cui la dimensione del ledger è così pesantemente legato ad esse. Gestire la dimensione del payload dell'UTXO, la quantità di UTXO sul ledger, e il grado fino al quale diventa possibile tenerli fuori dalla catena rimedia alla eccessiva crescita della catena in quanto tale. Infatti, tutto ciò che mantiene il payload più piccolo contribuisce a contenere la dimensione complessiva.

Algoritmi crittografici alternativi usati nelle firme collettive, come le firme multiple[^1], le firme ad anello, le firme a soglia,[^2] or le firme di Schnorr,[^3] potrebbero risolvere alcuni problemi di scalabilità, per esempio riducendo le informazioni aggiunte al ledger, o eliminando informazioni con le firme multiple e gli script di riscatto. Con le transazioni multi-firma, per esempio, gli indirizzi dei ricevitori sono aggregati in un indirizzo del ricevitore multisig e fanno sì che il relativo script di riscatto sia memorizzato offline. Questo riduce anche il numero di output e la dimensione dello script all'interno della transazione. Lo stesso vale per le firme ad anello, le firme a soglia e le firme collettive. 

Le multi-firme sono divise in una transazione di finanziamento, che si trasforma in una UTXO e una transazione di spesa, e risultano in una transazione spesa. Per le transazioni di finanziamento UTXO, l'aggregazione di più ricevitori in un unico indirizzo di ricezione e l'uso di un numero minore di output, più l'off-chaining dello script di riscatto, normalmente portano ad una dimensione di dati minore. Gli schemi di firma alternativi appartengono al set di strumenti per contenere la dimensione dei dati, ma rispetto alla transazione media non-multisig, la riduzione della dimensione dei dati non è sempre verificata e dipende dal caso d'uso specifico. “[Mimblewimble](https://github.com/mimblewimble/grin),” per esempio, è una proposta per Bitcoin che prevede un approccio diverso alla costruzione delle transazioni. Rimuove la maggior parte dei dati storici della blockchain, compresi i risultati delle transazioni trascorse, permettendo comunque agli utenti di verificare completamente la catena. Permette anche una maggiore privacy rispetto alle attuali implementazioni di Bitcoin. “[Dfinity](https://dfinity.org/)” e “[Hyperledger Fabric](https://www.hyperledger.org/projects/fabric)” per ottenere lo stesso risultato usano firme a soglia.

### Riferimenti e approfondimenti 

* Madeira, Antonio: "What are State Channels", CryptoCompare.  7 Apr 2017: https://www.cryptocompare.com/coins/guides/what-are-state-channels/
* Ray, Shaan:  "What are Sidechains?", Hackernoon: https://hackernoon.com/what-are-sidechains-1c45ea2daf3
* Stathakopoulou, C.; Cachin, C.: “Threshold Signatures for Blockchain Systems “, IBM Research, Published in: RZ3910 in 2017: https://domino.research.ibm.com/library/cyberdig.nsf/papers/ CA80E201DE9C8A0A852580FA004D412F/$File/rz3910.pdf
* Saini, Vaibhav: “Difference Between SideChains and State Channels”, Hackernoon, June 26 2018: https://hackernoon.com/difference-between-sidechains-and-state-channels-2f5dfbd10707
* Saini, Vaibhav: “10 State Channel Projects Every Blockchain Developer Should Know About”, Hackernoon, Jun 25, 2018: https://hackernoon.com/10-state-channel-projects-every-blockchain-developer-should-know-about-293514a516fd
* Saini, Vaibhav. “11 sidechain projects every blockchain developer should know about,” April 26th 2018: https://hackernoon.com/13-sidechain-projects-every-blockchain-developer-should-know-about-804b65364107
* Tual, Stephan: “What are State Channels?”, Jan 4, 2017: https://blog.stephantual.com/what-are-state-channels-32a81f7accab
* Alpha Elements: https://elementsproject.org/
* Counterfactual: http://counterfactual.com/
* Celer Network: http://celer.network/
* Drops of Diamond: https://github.com/Drops-of-Diamond/diamond_drops
* FunFair: https://funfair.io/
* Hivemind: http://bitcoinhivemind.com/
* Loom: https://loomx.io/
* Liquid: https://blockstream.com/liquid/
* Liquidity Network: https://liquidity.network/
* Machinomy: https://machinomy.com/
* Lightning Network: https://lightning.network/
* PegaSys: https://medium.com/@pegasyseng
* Perun Network: https://perun.network/
* Plasma: https://plasma.io/
* POA Network: https://poa.network/
* Prysmatic Labs: https://prysmaticlabs.com/
* Raiden Network: https://raiden.network/
* Rootstock RSK: https://rsk.co/
* SpankChain: https://spankchain.com/
* Status: https://medium.com/@status.im
* Trinity Network: https://trinity.tech

### Note a piè di pagina

[^1]:
Le firme multiple permettono la creazione di un caveau con più serrature e chiavi e assegnano le chiavi a più parti. Permettono anche la creazione di un meccanismo di cassaforte che richiede solo una parte di queste chiavi per essere aperta. Anche se una delle chiavi viene copiata, gli attaccanti non sono in grado di aprire il caveau..

[^2]:
Le firme a soglia permettono a un gruppo arbitrario di firmatari di costruire una firma, a patto che ce ne siano abbastanza. Sono più efficienti, perché quasi tutto il calcolo può essere fatto dai firmatari prima di inviarlo ad una rete blockchain.

[^3]:
Le firme Schnorr sono basate sull'algoritmo di firma di Schnorr, che è noto per la sua semplicità, è efficiente e genera firme di dimensione contenuta.