---
TOCTitle: 'Guida alla difesa antivirus a più livelli, Capitolo 2: Pericoli correlati a software dannoso'
Title: 'Guida alla difesa antivirus a più livelli, Capitolo 2: Pericoli correlati a software dannoso'
ms:assetid: 'a2b52bfd-e169-480a-a668-035777e31c0f'
ms:contentKeyID: 20200784
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536184(v=TechNet.10)'
---

Guida alla difesa antivirus a più livelli
=========================================

### Capitolo 2: Pericoli correlati a software dannoso

Pubblicato: 20 maggio 2004

##### In questa pagina

[](#ehaa)[Introduzione](#ehaa)
[](#egaa)[L'evoluzione dei virus dei computer](#egaa)
[](#efaa)[Definizione di software dannoso](#efaa)
[](#eeaa)[Caratteristiche del software dannoso](#eeaa)
[](#edaa)[Definizione di software non dannoso](#edaa)
[](#ecaa)[Software antivirus](#ecaa)
[](#ebaa)[Tempi tipici del software dannoso "in azione"](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

In questo capitolo della** *Guida alla difesa antivirus a più livelli* è riportata una spiegazione concisa dell'evoluzione dei virus dei computer, dai primi virus relativamente semplici al vario assortimento di software dannoso o *malware* attualmente esistente. In questo capitolo sono elencati i tipi di software dannoso e le relative tecniche e sono inoltre riportate informazioni sulla propagazione del software dannoso e sui rischi rappresentati per organizzazioni di qualsiasi dimensione.

A causa della natura di tale argomento, in continua evoluzione, in questa Guida non si intende elencare e illustrare tutti gli elementi di software dannoso e le possibili variazioni. In ogni caso, questa Guida costituisce un significativo primo passo per tentare di comprendere la natura dei vari elementi di cui è costituito il software dannoso. Sono inoltre illustrati e definiti altri elementi, che non rappresentano software dannoso, come *spyware* (programmi che eseguono determinate attività su un computer senza ottenere il consenso dell'utente), *spam* (posta elettronica non desiderata) e *adware* (annunci integrati nel software).

[](#mainsection)[Inizio pagina](#mainsection)

### L'evoluzione dei virus dei computer

I primi virus per computer sono stati introdotti nei primi anni '80. Questi primi tentativi erano ampiamente sperimentali ed erano costituiti da file autoreplicanti relativamente semplici che visualizzavano insulti o scherzi quando eseguiti.

**Nota:** fornire una storia completa dell'evoluzione dei virus è un'impresa impossibile. La natura illegale del software dannoso implicitamente spiega l'interesse degli autori a nascondere le origini del software. Viene pertanto riportata la storia comunemente accettata del software dannoso da parte dei ricercatori di virus e del settore antivirus.

Nel 1986 sono stati segnalati i primi virus ad attaccare i personal computer Microsoft® MS-DOS®; il virus Brain è considerato in genere come il primo di tali virus. Altri erano Virdem (il primo virus basato su file) e PC-Write (il primo *cavallo di Troia*, un programma che sembra utile o innocuo ma che contiene codice nascosto progettato per attaccare o danneggiare il sistema sul quale viene eseguito). Nel caso di PC-Write, il cavallo di Troia era mascherato dalla diffusa applicazione di elaborazione testi shareware con lo stesso nome.

Man mano che altre persone iniziavano ad esplorare la tecnologia dei virus, il numero, la complessità e la diversità dei virus, insieme alle piattaforme di destinazione cominciarono a crescere in modo sostanziale. Per un certo periodo di tempo i virus si sono concentrati sui settori di avvio, quindi hanno iniziato a infettare i file eseguibili. Nel 1988, è apparso il primo *worm* Internet (un tipo di software che utilizza codice dannoso che si propaga autonomamente, in grado di distribuirsi automaticamente da un computer a un altro attraverso le connessioni di rete). Il Morris Worm ha causato un sostanziale rallentamento delle comunicazioni via Internet. In risposta a questo e al crescente numero di attacchi, è stato fondato il CERT Coordination Center all'indirizzo: <http://www.cert.org/> (in inglese), per contribuire ad assicurare la stabilità di Internet assistendo gli utenti nel coordinamento delle risposte a violazioni o attacchi.

Nel 1990 è stato attivato in linea il servizio Virus Exchange BBS per consentire agli autori di virus di collaborare tra loro e condividere le loro conoscenze. È stato inoltre pubblicato il primo testo sulla creazione di virus ed è stato sviluppato il primo virus *polimorfico*, comunemente denominato Chameleon o Casper. Un virus polimorfico è un tipo di software dannoso che utilizza un numero limitato di routine di crittografia per evitare di essere rilevato. I virus polimorfici sono in grado di modificarsi ogni volta che si replicano, il che ne rende difficile l'individuazione da parte dei programmi antivirus basati sulla *firma*, progettati per "riconoscere" i virus. Dopo poco è stato sferrato il primo grande attacco di un virus polimorfico, Tequila. Nel 1992 sono quindi emersi il primo motore di virus polimorfici e i toolkit di scrittura di virus.

Da allora, i virus sono diventati più sofisticati: hanno iniziato ad accedere alle rubriche di posta elettronica e a inviarsi automaticamente ai contatti in esse contenuti, virus macro si sono allegati a diversi file di applicazioni tipo ufficio e li hanno attaccati, inoltre, sono stati rilasciati virus scritti specificamente per violare le vulnerabilità di sistemi operativi e applicazioni. Posta elettronica, reti per la condivisione di file peer-to-peer (P2P), siti Web, unità condivise e vulnerabilità dei prodotti sono stati sfruttati per la replica e l'attacco da parte dei virus. Sono state create *backdoor* (punti di ingresso nella rete segreti o nascosti introdotti dal software dannoso) sui sistemi infetti per consentire agli autori di virus, o *hacker*, di tornare ed eseguire qualsiasi software desiderassero. Un hacker nel contesto di questa Guida è un programmatore o utente di computer che tenta di accedere illegalmente a un sistema di computer o a una rete. Il software dannoso è illustrato in modo dettagliato nella sezione successiva di questo capitolo.

Alcuni virus sono dotati di motori di posta elettronica integrati che consentono a un sistema infetto di propagare il virus direttamente tramite posta elettronica, ignorando qualsiasi impostazione del client o del server di posta elettronica dell'utente. Gli autori di virus hanno inoltre iniziato a strutturare con cura gli attacchi e a utilizzare l'individuazione di persone vulnerabili per sviluppare messaggi di posta elettronica dall'aspetto autentico. Questo approccio cerca di sfruttare la fiducia degli utenti per l'apertura dei file contenenti virus allegati e aumenta in modo drastico la probabilità di un'infezione su larga scala.

Durante l'evoluzione del software dannoso, anche il software antivirus ha continuato a evolversi. Tuttavia la maggioranza del software antivirus attuale è quasi interamente basato sulle *firme* dei virus o sull'identificazione delle caratteristiche del software dannoso per identificare codice potenzialmente pericoloso. Esiste ancora un'opportunità tra il rilascio iniziale di un virus e il momento in cui i relativi file di firma vengono distribuiti dai produttori di antivirus. Di conseguenza, molti virus rilasciati oggi mostrano una velocità di infezione estremamente rapida nei primissimi giorni e sono quindi seguiti da un brusco declino una volta distribuiti i file di firma per contrastarli.

[](#mainsection)[Inizio pagina](#mainsection)

### Definizione di software dannoso

In questa Guida viene utilizzato il termine *software dannoso* come nome collettivo per riferirsi a virus, worm e cavalli di Troia che eseguono intenzionalmente attacchi dannosi a un sistema di computer.

Ma che cos'è esattamente un virus o un worm? In che modo si differenziano dai cavalli di Troia? E le applicazioni antivirus sono in grado di funzionare solo contro worm e cavalli di Troia o solo contro i virus?

Sono queste le domande che emergono dal mondo confuso e spesso non correttamente rappresentato del codice dannoso. Il significativo numero e la varietà di codice dannoso esistenti rende difficile fornire una definizione perfetta di ciascuna categoria di software dannoso.

Per un discorso generale sugli antivirus, è possibile applicare le seguenti semplici definizioni di categorie di software dannoso:

-   **Cavallo di Troia**: un programma che può sembrare utile o innocuo ma che contiene codice nascosto progettato per violare o danneggiare il sistema sul quale viene eseguito. I cavalli di Troia sono spesso distribuiti tramite messaggi di posta elettronica che nascondono il reale scopo e la funzione del programma. Denominato anche codice di Troia, un cavallo di Troia funziona distribuendo un *payload* o un'attività dannosa quando viene eseguito.

-   **Worm**: un worm utilizza codice dannoso che si propaga autonomamente, in grado di distribuirsi automaticamente da un computer a un altro attraverso le connessioni di rete. Un worm può eseguire azioni dannose, come utilizzare risorse della rete o del sistema locale, causando potenzialmente un attacco di tipo negazione del servizio. Alcuni worm sono in grado di eseguirsi e diffondersi senza l'intervento dell'utente, mentre altri richiedono che gli utenti eseguano il codice worm direttamente per potersi diffondere. I worm possono distribuire un payload oltre al replicarsi.

-   **Virus**: un virus utilizza codice scritto con l'esplicita intenzione di replicarsi e tenta di diffondersi da un computer all’altro associandosi a un programma ospite. Può danneggiare l’hardware, il software o i dati. Quando si esegue il programma ospite, viene eseguito anche il codice del virus, che infetta nuovi ospiti e a volte distribuisce un ulteriore payload.

Nell'ambito di questa Guida, *payload* è un termine collettivo relativo alle azioni eseguite da un attacco di software dannoso sul computer infetto. Queste definizioni delle diverse categorie di software dannoso consentono di illustrare le differenze attraverso un semplice diagramma di flusso. Nella figura riportata di seguito sono illustrati gli elementi che consentono di determinare se un programma o uno script rientra in una di queste categorie:

![](images/Dd536184.AVFG0201(it-it,TechNet.10).gif)

**Figura 2.1 Struttura decisionale di codice dannoso**

Questa figura consente di operare una distinzione tra ciascuna delle comuni categorie di software dannoso nell'ambito di questa Guida. Tuttavia è importante comprendere che un singolo attacco può introdurre codice che in realtà rientra in una o più categorie. Questi tipi di attacchi, cui viene fatto riferimento come a *pericoli vari* composti da più tipi di software dannoso che utilizzano più vettori di attacco, sono in grado di diffondersi rapidamente. Un *vettore di* *attacco* rappresenta il percorso che il software dannoso può utilizzare per montare un attacco. Per questi motivi può essere particolarmente difficile difendersi dai pericoli vari.

Nella sezione che segue è riportata una spiegazione più dettagliata di ciascuna categoria di software dannoso, per illustrare alcuni degli elementi principali di ciascuna di esse.

#### Cavalli di Troia

Un cavallo di Troia non è considerato un virus o un worm perché non si propaga autonomamente. Può essere tuttavia utilizzato un virus o un worm per copiare un cavallo di Troia sul sistema di destinazione come parte del payload dell'attacco, un processo cui viene fatto riferimento come al *rilascio*. Il tipico scopo di un cavallo di Troia è quello di interrompere il lavoro degli utenti o il normale funzionamento del sistema. Il cavallo di Troia può ad esempio fornire una backdoor nel sistema che consente a un hacker di utilizzare dati o di modificare le impostazioni del sistema.

Esistono altri due termini utilizzati spesso quando ci si riferisce ai cavalli di Troia o alle relative attività identificate e spiegate come segue:

-   **Cavalli di Troia ad accesso remoto**: alcuni cavalli di Troia consentono all'hacker o a colui che si appropria dei dati di controllare un sistema in modo remoto. Tali programmi sono denominati *Cavalli di Troia ad accesso remoto* (RAT, Remote Access Trojan) o backdoor. Esempi di RAT comprendono Back Orifice, Cafeene e SubSeven.

    Per una spiegazione dettagliata di questo tipo di cavallo di Troia, vedere l'articolo "Danger: Remote Access Trojans" sul sito Microsoft TechNet all'indirizzo:
    [http://www.microsoft.com/technet/security/topics/virus/virusrat.mspx](http://www.microsoft.com/technet/security/alerts/info/virusrat.mspx) (in inglese).

-   **Rootkit**: si tratta di raccolte di programmi software che gli hacker possono utilizzare per ottenere l'accesso remoto non autorizzato a un computer per lanciare altri attacchi. Questi programmi possono utilizzare una serie di tecniche diverse, incluso il monitoraggio della pressione dei tasti, la modifica dei file di registro del sistema o di applicazioni esistenti, la creazione di una backdoor nel sistema e l'avvio di attacchi contro altri computer della rete. I rootkit sono in genere organizzati in una serie di strumenti regolati e indirizzati a uno specifico sistema operativo. I primo rootkit sono stati identificati nei primi anni '90 e in quel periodo gli obiettivi principali erano costituiti dai sistemi operativi Sun e Linux. Attualmente sono disponibili rootkit per una serie di sistemi operativi, inclusa la piattaforma Microsoft® Windows®.

    **Nota**: i RAT e alcuni degli strumenti che comprendono i rootkit possono essere utilizzati per scopi legittimi di controllo remoto e monitoraggio. Tuttavia, i problemi di protezione e privacy che tali strumenti possono sollevare aumentano il rischio globale per gli ambienti nei quali vengono utilizzati.

#### Worm

Se il codice dannoso si replica, non si tratta di un cavallo di Troia, per cui la domanda successiva alla quale rispondere per definire più chiaramente il software dannoso è: "Il codice è in grado di replicarsi senza bisogno di un vettore?" Vale a dire, può replicarsi senza infettare un file eseguibile? Se la risposta a questa domanda è "Sì" il codice può essere considerato una qualche forma di worm.

La maggior parte dei worm tenta di copiarsi in un computer host e utilizza quindi i canali di comunicazione del computer per replicarsi. Ad esempio, il worm Sasser si basa su una vulnerabilità del servizio per infettare inizialmente un sistema e utilizza quindi la connessione alla rete del sistema infetto per tentare di replicarsi. Se si sono installati i più recenti aggiornamenti della protezione (per arrestare l'infezione), o si sono attivati i firewall nel proprio ambiente per bloccare le porte della rete utilizzate dal worm (per arrestare la replica), l'attacco non riuscirà.

#### Virus

Se il codice dannoso aggiunge una copia di sè stesso a un file, documento o settore di avvio di un'unità disco per replicarsi, è considerato un virus. Questa copia può essere una copia diretta del virus originale o può essere una versione modificata dell'originale. Per ulteriori dettagli, vedere la sezione "Meccanismi di difesa" più avanti in questo capitolo. Come accennato in precedenza, un virus contiene spesso un payload che può rilasciare su un computer locale, come un cavallo di Troia, che eseguirà quindi una o più azioni dannose, come l'eliminazione dei dati dell'utente. Tuttavia un virus che si limita a replicarsi ma non ha un payload rappresenta comunque un problema di software dannoso perché il virus stesso può danneggiare dati, utilizzare risorse del sistema e sfruttare la larghezza di banda della rete mentre si replica.

[](#mainsection)[Inizio pagina](#mainsection)

### Caratteristiche del software dannoso

Le varie caratteristiche che ciascuna categoria di software dannoso mostra sono spesso molto simili. Ad esempio, un virus e un worm possono entrambi utilizzare la rete come meccanismo di trasporto. Tuttavia, il virus cercherà file da infettare mentre il worm tenterà semplicemente di copiarsi. Nella sezione seguente sono illustrate le caratteristiche tipiche del software dannoso.

#### Ambienti di destinazione

Quando il software dannoso tenta di attaccare un sistema host, è possibile che esista un numero di componenti specifici richiesti prima che l'attacco possa riuscire. Sono riportati di seguito esempi tipici dei possibili requisiti per un attacco all'host da parte del software dannoso:

-   **Periferiche**: alcuni software sono specificamente indirizzati a un tipo di periferica, come un personal computer, un computer Apple Macintosh o un'agenda elettronica (PDA), anche se in realtà il software dannoso per PDA è attualmente raro.

-   **Sistemi operativi**: il software dannoso può richiedere uno specifico sistema operativo per essere efficace. Ad esempio, il virus CIH o Chernobyl della fine degli anni '90 poteva attaccare solo computer che eseguivano Microsoft Windows® 95 o Windows® 98.

-   **Applicazioni**: il software dannoso può richiedere che sia installata una specifica applicazione sul computer di destinazione per poter distribuire un payload o replicarsi. Ad esempio il virus LFM.926 del 2002 poteva attaccare solo nei casi in cui era possibile eseguire file Shockwave Flash (.swf) sul computer locale.

#### Oggetti vettore

Se il software dannoso è un virus, tenterà di attaccare un oggetto vettore o un ospite per infettarlo. Il numero e il tipo di oggetti vettore obiettivo di attacchi varia molto a seconda del software, ma nell'elenco seguente sono riportati esempi dei vettori obiettivi più comuni:

-   **File eseguibili**: sono l'obiettivo del tipo di virus "classico" che si replica allegandosi a un programma ospite. Oltre ai tipici file eseguibili che utilizzano l'espressione .exe, a questo scopo possono anche essere utilizzati file con le seguenti espressioni: .com, .sys, .dll, .ovl, .ocx e .prg.

-   **Script**: attacchi che utilizzano script come file di destinazione con un linguaggio di script quale Microsoft Visual Basic® Script, JavaScript, AppleScript o Perl Script. Le estensioni per i file di questo tipo comprendono: .vbs, .js, .wsh e .prl.

-   **Macro**: questi vettori sono file che supportano un linguaggio di script di macro di una particolare applicazione come un elaboratore testi, un foglio di calcolo o un'applicazione di database. Ad esempio, i virus possono utilizzare i linguaggi macro in Microsoft Word e Lotus Ami Pro per produrre una serie di effetti, che vanno dal dispettoso (modifica della posizione delle parole all'interno del documento o modifica dei colori) al dannoso (formattazione dell'unità disco rigido del computer).

-   **Settore di avvio**: aree specifiche dei dischi dei computer (dischi rigidi e supporti rimovibili di avvio), come il record di avvio principale (MBR) o il record di avvio DOS, possono anch'esse essere considerate vettori, perché in grado di eseguire codice dannoso. Quando un disco viene infettato, la replica viene raggiunta quando viene utilizzato per avviare altri sistemi di computer.

    **Nota:** se il virus è destinato sia a file che a settori di avvio può essere denominato virus *multipartito*.

#### Meccanismi di trasporto

Un attacco può utilizzare uno o più diversi metodi per tentare di replicarsi tra i sistemi di computer. In questa sezione sono riportate informazioni su alcuni dei più comuni meccanismi di trasporti utilizzati dal codice dannoso.

-   **Supporti rimovibili**: il mezzo di trasmissione originale e probabilmente più prolifico di virus e di altro software dannoso (almeno fino a poco fa) è il trasferimento di file. Questo meccanismo è iniziato con i dischi floppy, si è quindi spostato alle reti e ora sta trovando nuovi supporti come le periferiche USB e Firewire. La velocità dell'infezione non è così rapida come nel caso del software dannoso basato sulla rete, ma il pericolo è sempre presente e difficile da sradicare completamente a causa della necessità di scambio di dati tra i sistemi.

-   **Condivisioni di reti**: quando i computer sono stati dotati di un meccanismo per connettersi gli uni agli altri direttamente tramite una rete, agli autori di software dannoso è stato presentato un altro meccanismo di trasporto con potenzialità che superavano quelle dei supporti rimovibili per diffondere codice dannoso. Una protezione implementata in modo non sufficiente sulle condivisioni di rete produce un ambiente nel quale il software dannoso può replicarsi su un gran numero di computer connessi alla rete. Questo metodo ha ampiamente sostituito il metodo manuale che prevedeva l'uso dei supporti rimovibili.

-   **Scansione della rete**: gli autori di software dannoso utilizzano questo meccanismo per cercare in rete i computer vulnerabili o per attaccare indirizzi IP in modo casuale. Con questo meccanismo è ad esempio possibile inviare un pacchetto di attacco mediante una specifica porta della rete a una serie di indirizzi IP con lo scopo di individuare un computer vulnerabile da attaccare.

-   **Reti peer-to-peer (P2P)**: per effettuare trasferimenti di file P2P, l'utente deve installare prima un componente client dell'applicazione P2P che utilizzerà una delle porte di rete autorizzate a passare, ad esempio la porta 80. Le applicazioni utilizzano questa porta per attraversare il firewall e trasferire i file direttamente da un computer all'altro. Queste applicazioni sono disponibili su Internet e forniscono un meccanismo di trasporto che gli autori di software dannoso possono utilizzare direttamente per diffondere un file infetto sul disco rigido di un client.

-   **Posta elettronica**: la posta elettronica è diventata il meccanismo di trasporto prescelto per molti attacchi di software dannoso. La facilità con la quale centinaia di migliaia di persone possono essere raggiunte tramite posta elettronica senza che sia necessario che gli autori di software dannoso lascino i loro computer ha reso la posta elettronica un mezzo di trasporto particolarmente efficace. È stato relativamente semplice ingannare gli utenti e fare in modo che aprissero allegati di posta elettronica infetti, mediante tecniche di individuazione di persone vulnerabili. Pertanto molti degli attacchi più riusciti di software dannoso hanno utilizzato la posta elettronica come meccanismo di trasporto. I tipi di software dannoso che utilizzano la posta elettronica come trasporto sono fondamentalmente due:

    -   **Mailer**: questo tipo di software dannoso si spedisce automaticamente a un numero limitato di indirizzi di posta elettronica, utilizzando il software di posta installato sull'host (ad esempio, Microsoft Outlook® Express), oppure un proprio motore integrato SMTP.

    -   **Mailer di massa**: questo tipo di software dannoso cerca nei computer infetti gli indirizzi di posta elettronica e quindi si invia automaticamente a tali indirizzi, utilizzando il software di posta installato sull'host oppure un proprio motore integrato SMTP.

-   **Attacco remoto**: il software dannoso può tentare di sfruttare una particolare vulnerabilità in un sevizio o applicazione per replicarsi. Questo comportamento è spesso diffuso nei worm: ad esempio il worm Slammer sfruttava una vulnerabilità di Microsoft SQL Server™ 2000. Il worm generava un sovraccarico del buffer che consentiva a una parte della memoria del sistema di essere sovrascritta da codice che poteva essere eseguito nello stesso contesto di protezione del servizio SQL Server. Un sovraccarico del buffer è una condizione che risulta dall'aggiungere a un buffer più informazioni di quante possa contenere. L'autore di un attacco a un sistema può sfruttare questa vulnerabilità, identificata e corretta in realtà mesi prima che Slammer fosse rilasciato. Tuttavia pochi sistemi erano stati aggiornati per cui il worm riuscì a diffondersi facilmente.

#### Payload

Una volta che il software dannoso ha raggiunto la macchina host tramite il trasporto, esegue in genere un'azione cui viene fatto riferimento come *payload*, che può assumere diversi aspetti. In questa sezione sono identificati alcuni dei tipi di payload più comuni:

-   **Backdoor**: questo tipo di payload consente l'accesso non autorizzato a un computer. Può offrire l'accesso completo ma essere anche limitato ad accessi come FTP tramite la porta 21 del computer. Se l'attacco intendeva abilitare Telnet, un hacker potrebbe utilizzare il computer infetto come base per attacchi Telnet su altri computer. Come accennato in precedenza, a una backdoor viene a volte fatto riferimento come a un cavallo di Troia ad accesso remoto.

-   **Danneggiamento o eliminazione di dati**: uno dei tipi di payload più distruttivo può essere codice dannoso che danneggia o elimina i dati, rendendo inutili le informazioni presenti sui computer degli utenti. L'autore del software dannoso in questo caso ha due scelte: la prima possibilità è progettare il payload per una rapida esecuzione. Sebbene potenzialmente disastroso per il computer infettato, questo tipo di software sarà rapidamente scoperto e avrà quindi possibilità limitate di replicarsi senza essere rilevato. L'altra possibilità è lasciare il payload sul sistema locale sotto forma di cavallo di Troia per un certo periodo di tempo (per qualche esempio, vedere la sezione "Meccanismi di attivazione" più avanti in questo capitolo) per consentire al software di diffondersi prima di tentare di distribuire il payload, allertando in tal modo l'utente della sua presenza.

-   **Appropriazione indebita di informazioni**: un tipo di payload particolarmente preoccupante è quello progettato per l'appropriazione di informazioni. Se un payload è in grado di compromettere la protezione di un computer host, può essere anche in grado di fornire un meccanismo per passare informazioni agli autori del software dannoso. Questa operazione può avvenire in diversi modi: ad esempio potrebbe essere automatizzato un trasferimento, in modo che il software acquisisca semplicemente file locali o informazioni, quali i tasti premuti dall'utente, nella speranza di ottenere un nome utente e una password. Un altro meccanismo è fornire un ambiente sull'host locale che consenta all'autore dell'attacco di controllare in remoto l'host o di ottenere l'accesso diretto ai file del sistema.

-   **Negazione del servizio (DoS, Denial of Service)**: uno dei tipi di payload più semplice da distribuire è l'attacco di negazione del servizio. Un attacco DoS viene lanciato da un utente malintenzionato per sovraccaricare o arrestare un servizio di rete, come un server Web o un file server. Gli attacchi DoS intendono semplicemente rendere inutilizzabile uno specifico servizio per un periodo di tempo.

    -   **Negazione del servizio distribuito (DDoS, Distributed Denial of Service)**: questi tipi di attacchi utilizzano in genere client infetti del tutto all'oscuro del loro ruolo in tale attacco. Durante un attacco DDoS un utente malintenzionato utilizza software dannoso installato su diversi computer per attaccare un singolo obiettivo. Questo metodo consente di ottenere un effetto maggiore sull'obiettivo rispetto a quanto sia possibile con un singolo computer d'attacco. La struttura di tali attacchi varia di caso in caso, ma in genere si basa sull'invio di grandi quantità di dati a uno specifico host o sito Web che ha come risultato l'interruzione della risposta al traffico legittimo. In tal modo la larghezza di banda disponibile sul lato della vittima viene riempita e il sito viene costretto non in linea.

        Contro questo tipo di attacco può essere estremamente difficile difendersi, perché gli ospiti responsabili degli attacchi sono in realtà anch'essi vittime inconsapevoli. Gli attacchi DDoS sono in genere condotti da *bot* (programmi che eseguono azioni ripetitive), come i bot *Eggdrop* di Internet relay chat (IRC), che gli hacker possono utilizzare per controllare i computer “vittima” mediante un canale IRC. Quando i computer sono sotto il controllo degli hacker diventano *zombi* e possono infettare un obiettivo a comando dell'hacker, senza che il proprietario del computer ne sia consapevole.

    Sia l'approccio DoS che quello DDoS possono comprendere una serie di diverse tecniche di attacco, tra le quali:

    -   **Arresti del sistema**: se il software dannoso è in grado di arrestare in modo corretto o anomalo un sistema, può essere in grado di interrompere uno o più servizi. L'attacco a un sistema host richiede che il software dannoso individui una debolezza nell'applicazione o nel sistema operativo che può causare l'arresto del sistema.

    -   **Occupazione della larghezza di banda**: la maggior parte dei servizi di rete forniti in Internet sono collegati attraverso una connessione di rete a larghezza di banda limitata che consente la connessione ai relativi client. Se un autore di software dannoso è in grado di distribuire un payload che occupi la larghezza di banda con falso traffico di rete, è possibile produrre un attacco DoS semplicemente impedendo ai client di connettersi direttamente al servizio.

    -   **Attacchi di negazione del servizio di rete**: questo tipo di payload tenta di sovraccaricare le risorse disponibili sull'host locale. Risorse come la capacità di memoria e microprocessore sono state sovraccaricate da attacchi di tipo *SYN flood*, in cui viene utilizzato un programma per inviare un flusso di richieste TCP SYN per riempire la coda della connessione in attesa sul server e impedire il traffico di rete legittimo in entrata e uscita dal server. Anche gli attacchi di tipo *bomba di posta elettronica* esauriscono le risorse di memorizzazione per creare un attacco DoS in cui un'eccessiva quantità di dati di posta elettronica viene inviata a un indirizzo di posta elettronica nel tentativo di bloccare il programma di posta elettronica o di impedire al destinatario di ricevere altri messaggi legittimi.

    -   **Interruzione del servizio**: questo tipo di payload può utilizzare anche un attacco di tipo DoS. Se ad esempio un attacco su un server DNS (Domain Name System) disattiva il servizio DNS, sarà stata utilizzata una tale tecnica di attacco DoS. Tuttavia tutti gli altri servizi sul sistema potranno restare intatti.

#### Meccanismi di attivazione

I meccanismi di attivazione sono una caratteristica del software dannoso utilizzata per avviare la replica o la distribuzione del payload. Meccanismi tipici di attivazione comprendono:

-   **Esecuzione manuale**: questo tipo di meccanismo di attivazione è semplicemente l'esecuzione del software dannoso eseguita direttamente dalla vittima.

    -   **Individuazione di persone vulnerabili**: il software dannoso utilizza spesso una qualche forma di individuazione e sfruttamento delle persone vulnerabili per ingannare le vittime e costringerle a eseguire manualmente il codice dannoso. L'approccio può essere relativamente semplice, come quelli utilizzati nei worm di mailing di massa in cui l'elemento di individuazione della vulnerabilità si concentra sulla selezione del testo da immettere nel campo oggetto del messaggio di posta elettronica con la maggiore probabilità di essere aperto da una vittima potenziale. Gli autori di software dannoso possono anche utilizzare lo *spoofing* per tentare di portare la vittima a credere che un messaggio di posta elettronica provenga da un'origine sicura. Per spoofing si intende un'operazione attraverso la quale ci si sostituisce a un sito Web o a una trasmissione di dati per farli apparire autentici. Ad esempio, il worm Dumaru originale apparso nel 2003 modificava il campo **Da:** dei messaggi di posta elettronica perché riportasse come mittente security@microsoft.com. Per ulteriori informazioni su tale caratteristica, vedere la sezione relativa agli "Hoax" più avanti in questo capitolo.

-   **Esecuzione semi-automatica**: questo tipo di meccanismo di attivazione viene avviato inizialmente da una vittima ed eseguito quindi in modo automatico da quel punto in poi.

-   **Esecuzione automatica**: questo tipo di meccanismo di attivazione non richiede alcuna esecuzione manuale. Il software dannoso esegue il proprio attacco senza che sia necessario che la vittima esegua codice dannoso sul computer di destinazione.

-   **Bomba a orologeria**: questo tipo di meccanismo di attivazione esegue un'azione dopo un certo periodo. Questo periodo può essere un ritardo rispetto alla prima esecuzione del file infetto o una data o un intervallo di date prestabilito. Ad esempio il worm MyDoom.B avviava le routine del payload contro il sito Web Microsoft.com solo il 3 febbraio 2004 e contro il sito Web di SCO Group il 1 febbraio 2004. Interrompeva le repliche il 1 marzo 2004, anche se il componente della backdoor della bomba a orologeria è rimasto attivo dopo tali date.

-   **Condizionale**: questo tipo di meccanismo utilizza una qualche condizione predeterminata come attivazione per distribuire il suo carico. Ad esempio, un file rinominato, una serie di pressioni di tasti o l'avvio di un'applicazione. Il software dannoso che utilizza questo tipo di attivazione viene a volte denominato anche *bomba logica*.

#### Meccanismi di difesa

Molti esempi di software dannoso utilizzano qualche tipo di meccanismo di difesa per ridurre la probabilità di rilevamento e rimozione. Nell'elenco seguente sono riportati degli esempi di alcune delle tecniche utilizzate:

-   **Armatura**: questo tipo di meccanismo di difesa impiega una qualche tecnica che tenta di confondere l'analisi del codice dannoso. Tali tecniche comprendono il rilevamento durante l'esecuzione di un debugger e il tentativo di impedire che funzioni correttamente, o l'aggiunta di una quantità di codice senza senso per rendere difficile determinare lo scopo del codice dannoso.

-   **Azione furtiva**: il software dannoso utilizza questa tecnica per nascondersi intercettando le richieste di informazioni e restituendo dati falsi. Ad esempio un virus può memorizzare un'immagine del settore di avvio non infetto e visualizzarla ogni volta che viene effettuato un tentativo di visualizzare il settore di avvio infetto. Il primo virus noto, denominato “Brain,” utilizzava questa tecnica nel 1986.

-   **Crittografia**: il software dannoso che utilizza questo meccanismo di difesa crittografa il proprio codice o il payload, e a volte perfino i dati del sistema, per evitare il rilevamento o il recupero dei dati. Il software crittografato contiene una routine di decrittografia statica, una chiave di crittografia e il codice dannoso crittografato, che include a sua volta una routine di crittografia. Quando viene eseguito, il software utilizza la routine di decrittografia e la chiave per decrittografare il codice dannoso. Il software dannoso crea quindi una copia del codice e genera una nuova chiave di crittografia utilizzata insieme alla relativa routine di crittografia per crittografare la nuova copia di codice, aggiungendo la nuova chiave con la routine di decrittografia all'inizio della nuova copia. A differenza dei virus polimorfici, il software dannoso di crittografia utilizza sempre le stesse routine di decrittografia, così, sebbene il valore della chiave (e quindi la firma del codice dannoso crittografato) cambi in genere da un'infezione all'altra, il software antivirus può cercare la routine di decrittografia statica per rilevare il software che utilizza tale meccanismo di difesa.

-   **Oligomorfico**: il software dannoso con questa caratteristica utilizza la crittografia come meccanismo per difendersi ed è in grado di modificare la routine di crittografia un numero fisso, generalmente limitato, di volte. Ad esempio, un virus in grado di generare due diverse routine di decrittografia verrebbe classificato come *oligomorfico*.

-   **Polimorfico**: il software dannoso di questo tipo utilizza la crittografia come meccanismo di difesa per modificarsi ed evitare il rilevamento, in genere crittografando il codice con una routine di crittografia e quindi fornendo una diversa chiave di decrittografia per ciascuna mutazione. Così, il software *polimorfico* utilizza un numero limitato di routine di crittografia per evitare di essere rilevato. Quando si replica, una parte del codice di decrittografia viene modificato. A seconda dello specifico codice dannoso, il payload o altre azioni eseguite possono utilizzare o meno la crittografia. In genere esiste un *motore di mutazione*, che è un componente autonomo del software dannoso con crittografia che genera routine di crittografia casuali. Il motore e il codice sono quindi entrambi crittografati e la nuova chiave di decrittografia viene distribuita insieme ad essi.

[](#mainsection)[Inizio pagina](#mainsection)

### Definizione di software non dannoso

Esistono molteplici tipi di codice che non sono considerati software dannoso perché non si tratta di programmi scritti con scopi pericolosi. Tale codice può comunque avere implicazioni finanziarie e di protezioni per le organizzazioni. Per tali motivi, può essere utile comprendere il pericolo che rappresentano per l'infrastruttura IT della propria organizzazione e per la produttività degli utenti IT.

#### Software Joke

Le applicazioni Joke (scherzi) sono progettate per far sorridere o nel peggiore dei casi per far perdere tempo agli utenti. Tali applicazioni esistono da quando si è iniziato a utilizzare i computer. Poiché non sono state sviluppate a scopo dannoso e sono chiaramente identificate come scherzi, non sono considerate software dannoso in questa Guida. Esistono numerosi esempi di applicazioni joke, con risultati che vanno da interessanti effetti video a divertenti animazioni o giochi.

#### Hoax

In genere è più facile ingannare un utente e fare in modo che compia una determinata azione rispetto a scrivere del software che compia tale operazione senza che l'utente ne sia consapevole. Per questo motivo nella comunità IT è presente una notevole quantità di applicazioni hoax.

Come altre forme di software dannoso, un'applicazione *hoax* utilizza tecniche di individuazione di persone vulnerabili per tentare di far eseguire agli utenti di computer determinate operazioni. Tuttavia, nel caso di un'applicazione hoax non esiste codice da eseguire, l'unico scopo è quello di ingannare la vittima. Questo tipo di software ha assunto varie forme negli anni, ma un esempio particolarmente comune è costituito da un messaggio di posta elettronica che avvisa che è stato scoperto un nuovo tipo di virus e consiglia di avvisare gli amici inoltrando loro il messaggio. Questi hoax fanno sprecare tempo, occupano risorse del server di posta elettronica e utilizzano larghezza di banda della rete.

#### Scam

Praticamente tutte le forme di comunicazione sono state utilizzate, prima o poi, da utenti malintenzionati per tentare di ingannare gli utenti e fare in modo che compiano azioni che producano un qualche guadagno finanziario. Internet, i siti Web e la posta elettronica non costituiscono un'eccezione. Un messaggio di posta elettronica che tenta di ingannare il destinatario e di fargli rivelare informazioni personali che possono essere utilizzate per fini non legali (ad esempio informazioni sul conto in banca) è un esempio comune. Un particolare tipo di scam è diventato noto come *phishing*, pronunciato come “fishing” (pesca) e cui viene anche fatto riferimento come *spoofing di marche* o *carding*.

Esempi includono casi in cui i mittenti imitano note aziende come eBay per tentare di accedere alle informazioni sul conto dell'utente. Questi scam utilizzano spesso un sito Web che copia l'aspetto del sito Web ufficiale di un'azienda. Sono utilizzati dei messaggi di posta elettronica per reindirizzare l'utente al falso sito e per ingannarlo e fare in modo che specifichi informazioni sull'account utente che viene salvato e utilizzato a scopi non leciti. Questi casi vanno affrontati con serietà e segnalati alle autorità competenti.

#### Spam

Il termine *Spam* indica messaggi di posta elettronica non sollecitati generati per pubblicizzare servizi o prodotti. Tale fenomeno è in genere considerato noioso, ma non si tratta di software dannoso. Tuttavia, l'enorme crescita del numero di messaggi spam inviati rappresenta un problema per l'infrastruttura di Internet che ha come risultato perdita della produttività di utenti obbligati a destreggiarsi e a eliminare tali messaggi ogni giorno.

L'origine del termine spam è discussa, ma indipendentemente dalle origini non c'è dubbio che il termine si riferisca a una delle più irritanti e persistenti attività delle comunicazioni basate su Internet. Molti considerano lo spam un problema significativo che minaccia le comunicazioni via posta elettronica in tutto il mondo. Tuttavia va notato che a parte il carico sopportato dai server di posta elettronica e dal software anti-spam, lo spam non è effettivamente in grado di replicarsi o di minacciare il funzionamento dei sistemi IT di un'organizzazione.

Software dannoso è spesso stato utilizzato da creatori di spam (denominati *spammer*) per installare un piccolo servizio di server di posta elettronica SMTP su un computer host, utilizzato quindi per inoltrare messaggi spam ad altri destinatari di posta elettronica.

#### Spyware

A questo tipo di software viene a volte fatto riferimento come a *spybot* o a *software di rilevamento*. Lo *spyware* utilizza altre forme di software e programmi ingannevoli che eseguono determinate attività su un computer senza ottenere l'appropriato consenso da parte dell'utente. Queste attività possono includere la raccolta di informazioni personali e la modifica delle impostazioni di configurazione del browser Internet. Oltre a rappresentare un fastidio, lo spyware ha come risultato una serie di problemi che vanno dal peggioramento delle prestazioni generali del computer alla violazione della privacy.

I siti Web che distribuiscono lo spyware utilizzano una serie di astuzie per convincere gli utenti a scaricarlo e installarlo nei computer. Tali astuzie comprendono la creazione di esperienze utente false e la creazione di pacchetti comprendenti spyware e altro software richiesto dagli utenti, come software gratuito di condivisione di file.

#### Adware

L'*adware* è spesso combinato con un'applicazione host fornita gratuitamente purché l'utente accetti l'adware. Poiché le applicazioni adware sono in genere installate dopo che l'utente ha accettato un accordo di licenza che dichiara lo scopo dell'applicazione, non viene commesso alcun crimine. Tuttavia, gli annunci a comparsa possono diventare un fastidio e in alcuni casi peggiorare le prestazioni del sistema. Inoltre, le informazioni raccolte da alcune di queste applicazioni possono causare problemi di protezione agli utenti non completamente consapevoli dei termini del contratto di licenza.

**Nota:** sebbene i termini *spyware* e *adware* siano spesso utilizzati in modo interscambiabile, è solo l'adware non autorizzato alla pari dello spyware. L'adware che fornisce agli utenti avviso, scelta e controllo appropriati non è ingannevole e non deve essere classificato come spyware. Inoltre, le applicazioni spyware che dichiarano di eseguire una particolare funzione ma in realtà ne eseguono un'altra, agiscono in realtà come cavalli di Troia.

#### Cookie Internet

I cookie Internet sono file di testo collocati sul computer dell'utente da siti Web visitati. I cookie contengono e forniscono informazioni di identificazione sull'utente ai siti Web che li collocano sul computer dell'utente, insieme a eventuali informazioni che il sito desidera conservare sulla visita dell'utente.

I cookie sono strumenti legittimi utilizzati da molti siti Web per rilevare informazioni sui visitatori. Ad esempio un utente potrebbe acquistare un articolo in un punto vendita in linea, ma una volta inserito l'articolo nel carrello, potrebbe volere spostarsi in un altro sito per una qualche ragione. Il punto vendita può scegliere di salvare le informazioni sui prodotti presenti nel carrello in un cookie sul computer dell'utente in modo che quando l'utente tornerà sul sito, l'articolo sarà ancora nel carrello, pronto per essere acquistato se l'utente desidera completare l'acquisto.

Gli sviluppatori di siti Web devono solo essere in grado di recuperare le informazioni memorizzate nei cookie da essi creati. Questo approccio dovrebbe assicurare la privacy dell'utente facendo in modo che solo gli sviluppatori dei siti possano accedere ai cookie lasciati sui computer degli utenti.

Purtroppo, è stato scoperto che alcuni sviluppatori di siti Web hanno utilizzato cookie per ottenere informazioni senza il consenso dell'utente. Alcuni possono ingannare gli utenti o omettere i criteri adottati. Possono ad esempio rilevare i siti visitati abitualmente dall'utente senza informarlo. Gli sviluppatori di siti possono utilizzare queste informazioni per personalizzare gli annunci visualizzati dagli utenti su un sito Web, il che è considerato un'invasione della privacy. È difficile identificare questa forma di annunci "su misura" e altre forme di abuso dei cookie, il che rende difficile decidere e, quando e come bloccarli fuori dal sistema. Inoltre, il livello accettabile in informazioni condivise varia tra gli utenti di computer, rendendo difficile creare un programma "anti-cookie" che risponda alle esigenze di tutti gli utenti di un ambiente.

[](#mainsection)[Inizio pagina](#mainsection)

### Software antivirus

Il software antivirus è scritto specificamente per difendere un sistema contro i pericoli presentati dal software dannoso. Microsoft consiglia agli utenti di utilizzare i software antivirus, in quanto consentono di difendere i sistemi di computer contro qualsiasi forma di software dannoso, non solo dai virus.

Esiste una serie di tecniche utilizzate dal software antivirus per rilevare il software dannoso. In questa sezione è illustrato il funzionamento di queste tecniche, incluso:

-   **Scansione delle firme**: la maggior parte dei programmi di software antivirus utilizza attualmente questa tecnica, che prevede la ricerca di uno schema che possa rappresentare software dannoso nella destinazione (computer host, unità disco o file). Questi schemi sono in genere memorizzati in file cui viene fatto riferimento come file di firma, aggiornati regolarmente dai fornitori di software per assicurare che le funzioni di scansione antivirus riconoscano il numero maggiore possibile di attacchi di software dannoso conosciuto. Il problema principale con questa tecnica è che il software antivirus deve essere già aggiornato per contrastare il software dannoso prima che la funzione di scansione lo riconosca.

-   **Scansione euristica**: questa tecnica tenta di rilevare forme note e nuove di software dannoso cercandone le caratteristiche generali. Il vantaggio principale di questa tecnica è che non si basa sui file delle firme per identificare e contrastare il software dannoso. Tuttavia, la scansione euristica presenta una serie di problemi specifici, tra i quali:

    -   **Falsi positivi**: questa tecnica usa caratteristiche generali del software ed è pertanto possibile che segnali software legittimo come software dannoso se le caratteristiche sono simili in entrambi i casi.

    -   **Scansione più lenta**: il processo di ricerca delle caratteristiche è più difficile rispetto alla ricerca di uno schema di software dannoso già noto. Per questa ragione, per la la scansione euristica può essere necessario più tempo rispetto alla scansione delle firme.

    -   **Nuove caratteristiche possono essere saltate**: se l'attacco di un nuovo software dannoso presenta caratteristiche non identificate in precedenza, è possibile che la scansione euristica le salti fino a quando non sarà aggiornata.

-   **Blocco del funzionamento**: questa tecnica si basa sul funzionamento del codice dannoso anzichè sul codice stesso. Se ad esempio un'applicazione tenta di aprire una porta di rete, un programma antivirus con blocco del funzionamento potrebbe individuare questa come una tipica attività di software dannoso e contrassegnare quindi il comportamento come possibile attacco di software dannoso.

Molti produttori di software antivirus usano attualmente una combinazione di queste tecniche nelle soluzioni antivirus create, nel tentativo di migliorare il livello di protezione generale dei sistemi di computer dei clienti.

Software antivirus è prodotto da molteplici partner Microsoft. Per un elenco completo e aggiornato, vedere la pagina relativa ai partner Microsoft antivirus sul sito Web Microsoft.com all'indirizzo: [http://www.microsoft.com/security/partners/antivirus.asp](http://www.microsoft.com/windows/antivirus-partners/windows-vista.aspx) (in inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Tempi tipici del software dannoso "in azione"

È emerso uno schema per definire la durata degli attacchi di nuovi software dannosi disponibili sulle reti pubbliche o quando il software dannoso entra *in azione*. Esaminare tale schema potrà essere d'aiuto per comprendere il rischio posto dagli attacchi di nuovo software dannoso una volta rilasciato.

Una nuova cronologia inizia con il primo sviluppo del software dannoso e termina quando tutte le tracce del software sono state rimosse dalle reti monitorate. Le fasi cronologiche sono definite come segue:

1.  **Ideazione**: lo sviluppo di software dannoso spesso inizia quando un nuovo metodo di attacco o di sfruttamento delle vulnerabilità viene suggerito e quindi condiviso tra le comunità di hacker. I metodi sono discussi o esplorati fino a quando viene scoperto un approccio che può essere sviluppato in un attacco.

2.  **Sviluppo**: la creazione di software dannoso richiedeva la comprensione del linguaggio di assembly del computer e dell'intricato funzionamento del sistema da attaccare. Tuttavia, grazie all'avvento dei toolkit e delle chat su Internet è stato possibile praticamente per chiunque ne avesse l'intenzione creare software dannoso.

3.  **Replica**: dopo che il software dannoso è stato sviluppato e messo in azione, dovrà replicarsi su potenziali periferiche ospite per un certo periodo di tempo prima di poter eseguire la sua funzione principale o distribuire il payload.

    **Nota:** anche se esistono decine di migliaia di programmi di software dannoso noti, attualmente è in azione solo una piccola frazione di essi. La stragrande maggioranza dei programmi di software dannoso non vengono rilasciati al pubblico e viene spesso fatto loro riferimento come a *virus dello Zoo*.

4.  **Distribuzione del payload**: dopo che il software ha infettato un ospite può distribuire il payload. Se il codice è dotato di un'attivazione condizionale per il payload, questa fase rappresenta il momento in cui vengono soddisfatte le condizioni del meccanismo di distribuzione. Ad esempio, alcuni payload vengono attivati quando un utente esegue una determinata azione o quando l'orologio sulla macchina host raggiunge una specifica data. Se il software viene attivato da una azione diretta, inizierà semplicemente a distribuire il payload quando l'infezione sarà completa. Ad esempio, nel caso di payload di registrazione di dati il programma inizierà semplicemente a registrare i dati necessari.

5.  **Identificazione**: a questo punto della cronologia il software dannoso viene identificato dalle comunità antivirus. Nella maggioranza dei casi questa fase si verifica prima della fase 4 o anche prima della fase 3, ma non è sempre così.

6.  **Rilevamento**: una volta identificato il pericolo, gli sviluppatori di software antivirus devono analizzare il codice per determinare un metodo di rilevamento affidabile. Determinato il metodo, aggiornano i file di firme antivirus per consentire alle applicazioni antivirus esistenti di rilevare il nuovo software dannoso. La durata di questo processo è fondamentale per tentare di controllare un attacco.

7.  **Rimozione**: quando l'aggiornamento è disponibile al pubblico, è responsabilità degli utenti dell'applicazione antivirus applicare l'aggiornamento in modo tempestivo per proteggere i computer contro l'attacco (o per pulire i sistemi già infetti).

    **Nota:** il mancato aggiornamento dei file delle firme locali in modo tempestivo può portare a uno scenario ad alto rischio di utenti che credono di disporre della protezione di un prodotto antivirus, ma in realtà non sono protetti.

Man mano che più utenti aggiornano il software antivirus il software diventerà lentamente meno pericoloso. Questo processo rimuove raramente tutte le istanze del software dannoso in azione, poiché in genere restano alcuni computer connessi a Internet con una protezione antivirus bassa o inesistente in cui il software dannoso può risiedere. Tuttavia, il pericolo insito nell'attacco stesso è diminuito.

Anche se questa cronologia si ripete per tutti gli attacchi di nuovo software dannoso sviluppato, non è tipica di tutti gli attacchi. Molti attacchi sono semplicemente versioni modificate di una parte originale di codice dannoso, per cui il codice di base e l'approccio sono gli stessi, ma vengono effettuate piccole modifiche per fare in modo che l'attacco eviti il rilevamento e la successiva rimozione. In genere, un attacco di software dannoso riuscito genererà una serie di revisioni nelle settimane e nei mesi successivi. Questa situazione porta a una sorta di "competizione" in cui gli autori di software dannoso tentano di evitare il rilevamento, per ottenere scopi finanziari, notorietà o per semplice curiosità. Le difese antivirus sono di nuovo aggiornate, corrette mediante patch o modificate a seconda delle necessità per ridurre il rinnovato pericolo.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

L'area della tecnologia informatica relativa al software dannoso è complessa e in costante evoluzione. Di tutti gli altri problemi riscontrati nel settore IT, pochi hanno la medesima importanza e gli stessi costi degli attacchi del software dannoso e delle necessarie risposte. Comprenderne il funzionamento, l'evoluzione nel tempo e individuare i vettori dell'attacco utilizzabili può essere d'aiuto per affrontare il problema in modo proattivo, il che, a sua volta può consentire di applicare un processo di reazione più efficiente ed efficace in caso di attacco alla propria organizzazione.

Dato che il software dannoso utilizza un tal numero di tecniche per creare, distribuire e sfruttare le vulnerabilità dei sistemi di computer, può essere difficile comprendere come sia possibile proteggere i sistemi in modo da contrastare tali attacchi. Tuttavia, una volta compresi i rischi e le vulnerabilità, sarà possibile gestire il sistema in modo che renda altamente improbabile la possibilità di un attacco riuscito.

Il passaggio successivo è costituito dall'analisi dei rischi in vari punti dell'infrastruttura IT per progettare una difesa appropriata, argomento del capitolo successivo. La progettazione di un efficace piano di ripristino è argomento del capitolo finale di questa Guida.

[](#mainsection)[Inizio pagina](#mainsection)
