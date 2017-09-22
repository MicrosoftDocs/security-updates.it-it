---
TOCTitle: 'Data Encryption Toolkit for Mobile PC: Capitolo 1: discussione sui rischi'
Title: 'Data Encryption Toolkit for Mobile PC: Capitolo 1: discussione sui rischi'
ms:assetid: 'df2c6d71-98f7-4212-b3b7-b9eb2f501348'
ms:contentKeyID: 20213185
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc162822(v=TechNet.10)'
---

Data Encryption Toolkit for Mobile PC - Analisi della protezione
================================================================

### Capitolo 1: discussione sui rischi

Pubblicato: 4 aprile 2007

I dati sensibili, come tutti i dati, hanno un ciclo di vita complesso e, in genere, vengono spostati da un posto a un altro poiché eseguono la funzione aziendale ad essi collegata. È necessario proteggere i dati durante tutto il periodo di utilizzo, ma molte tecnologie e processi verranno applicati in diverse fasi del ciclo di vita dei dati.

![](images/Cc162822.4e80aa2b-2eba-421f-aeb8-d6021778e75d(it-it,TechNet.10).gif)

**Figura 1.1. Esempio del ciclo di vita dei dati**

In questa guida viene trattato il livello di protezione che può essere raggiunto grazie alle tecnologie Microsoft per la protezione dei dati, quando vengono copiati o creati sui PC portatili, come i laptop.

Le discussioni sulla protezione dei dati per i seguenti scenari non vengono riportate in questa guida, fatta eccezione per le situazioni in cui i dati vengono memorizzati nella cache localmente:

-   Quando i dati transitano nelle reti interne o esterne.

-   Quando i dati vengono presentati nelle applicazioni Web (thin-client).

-   Quando i dati vengono utilizzati nelle applicazioni dopo essere stati decrittografati.

##### In questa pagina

[](#efaa)[Rischi per la protezione dei dati](#efaa)
[](#eeaa)[Concetti di crittografia per la protezione dei dati](#eeaa)
[](#edaa)[Informazioni sui rischi per i dati](#edaa)
[](#ecaa)[Approcci alla protezione dei dati](#ecaa)
[](#ebaa)[Ulteriori informazioni](#ebaa)

### Rischi per la protezione dei dati

Le due tecnologie descritte in questa guida, Encrypting File System (EFS) e Crittografia unità BitLocker™ Microsoft® (BitLocker), sono esempi di due diversi ma complementari approcci alla crittografia dei dati. EFS è un meccanismo di crittografia che protegge i dati nei file e nelle cartelle su base per utente. BitLocker è un meccanismo di crittografia completa dei volumi che crittografa tutti i settori che si trovano sul volume del sistema, incluso il sistema operativo, le applicazioni e i file di dati, su base per computer. BitLocker fornisce la crittografia e il controllo dell'integrità prima dell'avvio, ma non l'autenticazione dell'utente. EFS completa la protezione di BitLocker restringendo l'accesso ai file crittografati agli utenti autenticati in modo appropriato su un computer in esecuzione.

A causa dei loro approcci e implementazioni fondamentalmente diversi, EFS e BitLocker hanno punti deboli e punti di forza e forniscono diversi livelli di protezione per una serie comune di scenari di attacco. In questa guida vengono descritti dettagliatamente tali scenari e viene esaminata la modalità con cui le due tecnologie di crittografia vengono applicate e ognuno di questi.

#### Informazioni sui tipi di dati

Esistono diversi tipi di dati riservati e molti scenari differenti per cui tali dati possono essere compromessi. In questa guida vengono illustrate le diverse tecnologie di crittografia per i seguenti tipi di dati.

-   **Informazioni personali**. Informazioni riservate sui clienti o i collaboratori di un'organizzazione, compresi i numeri di previdenza sociale, i numeri della carta di credito, informazioni sulla salute e così via. I dati di questo tipo sono protetti da uno o più regolamenti del settore o governativi, come Health Insurance Portability and Accountability Act (HIPAA), la Direttiva europea sulla tutela dei dati e la legge SB1386 della California. La perdita di questo tipo di dati generalmente provoca un impatto finanziario immediato e a lungo termine all'organizzazione, anche se potrebbe non essere mai provato che i dati sono stati letti dal computer.

-   **Proprietà intellettuale (IP)**. Dati considerati riservati o confidenziali da un'organizzazione, compresi piani di marketing, ricerche precedenti al brevetto su nuovi prodotti, algoritmi software, elenchi di nuovi potenziali clienti e così via. Se questi dati vengono persi o scoperti dalle persone sbagliate o se si trovano su un dispositivo che viene deliberatamente rubato, si potrebbe verificare una serie di effetti negativi tra cui la perdita del vantaggio competitivo. La cosa più importante da ricordare è che esistono implicazioni tipicamente finanziarie per l'utilizzo dei dati IP; per questo motivo il costo dell'attenuazione dei rischi può essere bilanciato confrontandolo con le implicazioni finanziarie derivanti dall'esposizione. Tuttavia, questo tipo di calcolo può non essere sempre utile. Anche il danneggiamento dell'immagine può costituire un fattore motivante. Per questo motivo potrebbe essere una buona idea crittografare i dati sul computer del CEO per evitare pubblicità negativa.

#### Scenari di attacco: dall'interno e dall'esterno

Quando si parla di attacchi e tecnologie di attenuazione, viene fatta una distinzione tra minacce provenienti dall'interno o dall'esterno. Un attacco effettuato dall'interno ha capacità che un attacco effettuato dall'esterno non ha. Di seguito viene riportato un parziale elenco delle differenze:

-   Chi effettua l'attacco dall'interno potrebbe accedere legittimamente al computer utilizzando il proprio account.

-   Chi effettua l'attacco dall'interno potrebbe accedere al computer sulla rete per un lungo periodo di tempo, mentre il computer viene utilizzato dai legittimi utenti. Tale opportunità potrebbe aumentare le probabilità di trovare un punto debole da sfruttare.

-   Dall'interno è più semplice effettuare attacchi a più fasi.

-   Dall'interno è più semplice riuscire a ottenere una password utente (o parte di essa) attraverso attacchi di social engineering.

Per confrontare i punti di forza e i punti deboli dei diversi approcci alla crittografia dei dati, è necessario illustrare alcuni concetti di crittografia che vengono applicati alla crittografia in generale e a EFS e BitLocker in particolare.

[](#mainsection)[Inizio pagina](#mainsection)

### Concetti di crittografia per la protezione dei dati

La crittografia può essere implementata in molti modi. Ad esempio, può essere eseguita in strati o in modelli complessi integrati in algoritmi univoci. L'utilizzo della chiave crittografica viene spesso trattato in termini di lunghezza della chiave, ma il modo in cui tali chiavi vengono calcolate, archiviate e utilizzate spesso è molto più importante. L'archiviazione e la protezione della chiave crittografica, pur essendo argomenti molto importanti per comprendere quale possa essere il punto debole della tecnologia di crittografia, raramente vengono trattate in dettaglio nella documentazione tecnica del prodotto.

![](images/Cc162822.note(it-it,TechNet.10).gif)**Nota:**

Questa sezione della guida non costituisce un manuale generale sulle tecnologie di crittografia. Se non si conoscono almeno i principi fondamentali della crittografia come la crittografia simmetrica e asimmetrica, sarebbe opportuno consultare l'articolo "[Cryptography for Network and Information Security](http://www.microsoft.com/technet/prodtechnol/windows2000serv/reskit/distrib/dsch_key_rveg.mspx)" (in inglese).

L'algoritmo di crittografia ottimale è progettato e implementato in modo che l'unico modo di decifrare la crittografia sia indovinare quale chiave sia stata utilizzata da un grande *spazio di chiavi* possibile, che corrisponde alla gamma di valori che una chiave potrebbe assumere. Questo tipo di attacco viene definito attacco a *forza bruta*.

Gli algoritmi a chiave simmetrica, in genere, hanno uno spazio di chiavi che oscilla tra 40 e 512 bit; il che significa che il numero di valori possibili per la chiave corrisponde al massimo valore numerico che può essere espresso dal numero di bit utilizzato. 40 bit consentono un massimo valore numerico di 1.099.511.627.775 (2(40) -1), che è certamente un numero significativo, sebbene i computer attualmente disponibili potrebbero tentare ogni valore possibile di uno spazio di chiavi a 40 bit come chiave crittografica, nel tentativo di decifrare i dati. Tuttavia, ogni bit aggiunto allo spazio di chiavi raddoppia il numero di chiavi possibili, quindi uno spazio di chiavi a 41 bit offrirebbe 2.199.023.255.552 chiavi possibili. Il rapido aumento dello spazio di chiavi provoca l'aumento delle chiavi possibili fino al punto in cui gli attacchi a forza bruta divengono irrealizzabili, se si utilizzano le tecniche di attacco note e hardware correnti.

Le tecnologie di crittografia, tuttavia, raramente forniscono una protezione così potente. Molte implementazioni della crittografia presentano uno o più dei seguenti punti deboli:

-   **L'algoritmo di crittografia non è valido**. Gli algoritmi di crittografia a volte vengono trovati fondamentalmente non validi dopo la revisione peer o dopo un attacco riuscito. A volte, questo si scopre solo dopo molti anni dalla pubblicazione e nel frattempo l'algoritmo viene utilizzato.

-   **L'implementazione non è corretta**. Gli algoritmi vengono implementati dagli sviluppatori che, a volte, introducono bug che ne riducono l'efficacia.

-   **Le chiavi hanno un livello ridotto di entropia**. Il solo fatto che uno spazio di chiavi sia a 128 bit, ad esempio, non significa che il processo di generazione del numero a 128 bit sia realmente casuale o che utilizzi l'intero spazio di chiavi.

-   **Le chiavi vengono rilevate facilmente**. Le chiavi devono essere conservate da qualche parte. Se il posto può essere scoperto e la chiave recuperata, i dati crittografati potrebbero essere compromessi.

Se le tecnologie di crittografia presentano questi punti deboli, è facile immaginare perché tutti se ne preoccupano. In pratica, esistono due fattori che consentono di ridurre l'occorrenza di questi punti deboli. Un fattore è costituito dal fatto che Microsoft investe molto nella convalida e nella verifica della correttezza di queste implementazioni di crittografia. Questo processo inizia con la scelta di algoritmi maturi e ben compresi che consentono un'innata resistenza ad alcuni tipi di attacco e continua attraverso l'impegno costante di Microsoft nell'avere le implementazioni degli algoritmi di crittografia certificate come richiesto dagli standard statunitensi [Federal Information Processing Standards (FIPS) 140 Evaluation](http://www.microsoft.com/technet/archive/security/topics/issues/fipseval.mspx) (in inglese) e nel far ottenere ai propri sistemi operativi la certificazione Common Criteria. Per ulteriori informazioni sulla certificazione Common Criteria, consultare la pagina [Windows Platform Common Criteria Certification](http://www.microsoft.com/technet/security/prodtech/windowsxp/ccc/default.mspx) (in inglese) su Microsoft TechNet. Il processo [The Trustworthy Computing Security Development Lifecycle](http://msdn2.microsoft.com/en-us/library/ms995349.aspx) (SDL) (in inglese), inoltre, è stato integrato nei processi di sviluppo Microsoft per assicurare che la protezione sia considerata un componente principale durante lo sviluppo del prodotto.

Il secondo fattore è costituito dal fatto che la crittografia può essere resa sufficientemente resistente agli attacchi da fornire un grado di protezione appropriato per i dati protetti. In altre parole, non è importante se un grande governo riesce a decifrare la crittografia che protegge il database dei clienti utilizzando tutte le risorse di cui dispone. La cosa che conta è che la soluzione di crittografia che dovrebbe impedire che i dati siano facilmente rilevabili sia in grado di garantire che i dati non possano essere rilevati da chi dispone di risorse e conoscenze ridotte. Un altro modo di valutare le esigenze di crittografia è accertarsi che qualsiasi dato si decida di crittografare venga valutato adeguatamente e quindi confrontato con il costo stimato che sarebbe necessario per decifrare la crittografia. Ad esempio, se il database dei clienti viene valutato 100.000 dollari da un concorrente e il costo stimato per decifrare la crittografia è di 1 milione di dollari, il livello di crittografia utilizzato probabilmente è sufficiente.

![](images/Cc162822.note(it-it,TechNet.10).gif)**Nota:**

Per ulteriori informazioni sul modo di accertarsi che un'implementazione crittografica sia sicura, fare riferimento al capitolo 19 di [Special Publication 800-12 – An Introduction to Computer Security: The NIST Handbook](http://csrc.nist.gov/publications/nistpubs/800-12/) (in inglese), pubblicato dal US National Institute of Standards and Technology (NIST).

Per valutare i meriti degli approcci di crittografia, è necessario esaminare i dettagli dell'implementazione di crittografia nella sua interezza. La figura che segue mostra una catena di eventi tipo che si verifica quando i dati vengono crittografati e decrittografati.

![](images/Cc162822.a42ab380-80b9-41a7-8f54-50ad34a59ee1(it-it,TechNet.10).jpg)

**Figura 1.2. Crittografia e decrittografia dei dati**

I fattori che seguono sono importanti per comprendere la valutazione di una tecnologia di crittografia:

-   **Scelta dell'algoritmo**. La protezione di un'implementazione crittografica dipende dalla qualità dell'implementazione e dagli algoritmi che implementa. Per questo motivo, la maggior parte delle tecnologie commerciali implementa un numero relativamente ridotto di algoritmi sperimentati e maturi che vengono considerati sicuri contro vari tipi di attacchi. Esempi di questi algoritmi sono 3DES (Triple Data Encryption Standard), AES (Advanced Encryption Standard) e Blowfish, ognuno dei quali è un algoritmo simmetrico e RSA (Rivest-Shamir-Adelman) e ECC (Elliptic Curve Cryptography), algoritmi a chiave pubblica.

-   **Generazione della chiave**. Le tecnologie di crittografia spesso utilizzano più chiavi. Alcune di queste chiavi verranno generate da hardware o software, alcune vengono fornite da persone e altre sono derivate dalle chiavi generate, dalle chiavi fornite da persone o da una combinazione di entrambe. La potenza delle chiavi generate si basa sulla possibilità di predire il valore della chiave se i fattori ambientali sono noti. In altre parole, una chiave deve essere sufficientemente casuale e lunga per essere efficace.

-   **Derivazione della chiave**. Molte implementazioni di crittografia derivano alcune chiavi da altre chiavi, come una password fornita dall'utente. La modalità con cui ogni chiave viene derivata è molto importante per la sicurezza generale dell'implementazione. La cosa importante da ricordare è che le chiavi non possono essere rese più forti dalla derivazione. È possibile creare una chiave AES a 256 bit da una chiave DES (Data Encryption Standard) a 56 bit, ma la forza della chiave che ne risulta non è maggiore di quella della chiave DES a 56 bit, che potrebbe essere derivata da una chiave anche più debole.

-   **Archiviazione della chiave**. Tutte le tecnologie di crittografia devono archiviare e utilizzare il materiale della chiave. La modalità con cui il materiale della chiave viene archiviato è molto importante per la sicurezza dell'implementazione. Risorse importanti come le chiavi di firma di autorità dei certificati principali vengono spesso protette utilizzando moduli hardware a prova di intrusione che forniscono una valida resistenza agli attacchi. Molte organizzazioni scelgono di distribuire smart card perché forniscono una protezione delle chiavi più forte delle soluzioni basate sul software, con l'ulteriore vantaggio costituito dal fatto che l'utente non può, neanche inavvertitamente, ripristinare e divulgare il materiale della chiave delle smart card. È necessario considerare anche i problemi pratici legati al comportamento degli utenti, controllando se proteggono in modo appropriato le password e il materiale della chiave. Le tecnologie di crittografia che rendono più facile per l'utente la scelta della cosa giusta da fare sono molto più sicure e hanno maggiori probabilità di riuscita rispetto a quelle che non lo fanno.

-   **Memorizzazione della chiave nella cache**. Le operazioni di crittografia spesso sono complesse dal punto di vista informatico. Per migliorare le prestazioni, le tecnologie di crittografia spesso si basano su ottimizzazioni che prevedono chiavi memorizzate nella cache o prodotti intermedi di operazioni crittografiche. Questi dati sono estremamente riservati e, se la tecnologia non li protegge in modo appropriato, potrebbero essere soggetti ad attacchi. Ad esempio, una tecnologia che memorizza nella cache una chiave crittografica potrebbe consentire ad un utente malintenzionato di recuperare tale chiave dalla memoria del sistema o dal file di paging, se la cache non è implementata e protetta correttamente.

-   **Punti deboli**. La protezione generale di un'implementazione di crittografia deve essere basata sulla protezione dei punti deboli. Conoscere i punti deboli di qualsiasi tecnologia di crittografia costituisce l'aspetto più importante della valutazione di un'implementazione di crittografia. In molti ambienti, gli utenti costituiscono il punto debole ed è importante implementare le misure tecniche che proteggono i dati sui PC portatili attraverso una formazione appropriata per l'utente.

-   **Utilizzabilità contro protezione**. In effetti, nessuna soluzione di crittografia è perfetta. Tutte queste soluzioni possono essere attaccate tramite un attacco a forza bruta, il problema è quanto tempo viene impiegato per effettuare questo tipo di attacco. Le implementazioni efficaci tendono a essere più o meno equivalenti alla validità della tecnologia di crittografia su cui vengono applicate. Tuttavia, la potenza della crittografia spesso non è il fattore più importante. Altri fattori, come l'interazione con l'utente, sono molto importanti. Le misure di protezione possono quasi sempre essere migliorate fino al punto in cui risulti difficile per gli utenti accedere ai propri dati, ma il grado di difficoltà dovrebbe essere analizzato attentamente per determinare se per l'organizzazione vale la pena affrontarne i costi. Nessuno vorrebbe implementare una soluzione tanto complessa da utilizzare che gli utenti preferiscano utilizzare carta e matita!

#### Difficoltà dell'attacco

Non tutti gli attacchi contro una soluzione di crittografia sono uguali. Come descritto in precedenza, un utente malintenzionato sfrutterà sempre il punto più debole. Per valutare il livello di protezione di una soluzione di crittografia, puoi elencare i possibili attacchi contro le tecnologie di crittografia che esso implementa e quindi classificare gli attacchi per difficoltà.

Un attacco con difficoltà bassa è un attacco in cui non sono necessarie risorse per leggere i dati a cui si è interessati. In altre parole, questo tipo di attacco corrisponde alla situazione in cui un utente malintenzionato non deve fare altro che alzare il coperchio del computer portatile e iniziare a leggere. La difficoltà di un attacco spesso è legata al contesto e ad altri fattori di una particolare soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Informazioni sui rischi per i dati

L'obiettivo di una soluzione di crittografia è quello di crittografare tutti i dati importanti affinché nessun utente malintenzionato, casuale o determinato, esperto o non esperto, possa accedere ai dati come testo non crittografato. Tuttavia, le soluzioni di crittografia possono essere sovvertite attraverso una massiccia applicazione di risorse, trovando errori sconosciuti in una specifica tecnologia di crittografia o semplicemente per errore dell'utente. Le tecnologie di crittografia hanno caratteristiche dei rischi univoci basate sulle decisioni di implementazione e progetto e sul modo in cui vengono utilizzate. Alcuni potenziali rischi vengono elencati nelle seguenti sottosezioni e indicati nelle descrizioni di scenario, riportate di seguito in questa guida. Tenere presente che non tutti i rischi elencati riguardano tutte le organizzazioni. È necessario considerare l'attenuazione dei rischi che riguardano l'organizzazione, dopo aver determinato quali rischi siano rilevanti e giustifichino un'azione appropriata.

#### Computer in modalità di ibernazione

La maggior parte dei computer portatili ha una funzionalità denominata ibernazione che consente agli utenti di arrestare i computer affinché non utilizzino energia e di riavviarli partendo dallo stesso identico stato in cui si trovavano prima dell'ibernazione. Tuttavia, lasciare il computer in modalità di ibernazione non protetta significa che un utente malintenzionato può avere accesso illimitato a tutte le informazioni contenute nel computer. Come per la modalità sospensione, i computer possono essere configurati in modo che richiedano le credenziali dell'utente alla ripresa dalla modalità di ibernazione. È possibile trovare informazioni relative all'attivazione di questa impostazione in [To password-protect your computer during standby or hibernation](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/pwrmn_passwordprotect_standby.mspx?mfr=true) (in inglese), che fa parte della documentazione online del prodotto Windows XP Professional.

![](images/Cc162822.important(it-it,TechNet.10).gif)**Importante:**

Microsoft suggerisce di richiedere l'utilizzo delle credenziali per sbloccare un computer dalla modalità di ibernazione.

#### Computer lasciato in modalità sospensione (standby)

È possibile che un computer portatile venga configurato in modo da non richiedere all'utente una password o una smart card alla ripresa dalla modalità sospensione; il che significa che il computer viene effettivamente lasciato acceso e utilizzabile da chiunque. Gli utenti che configurano il proprio computer in modo da utilizzare la modalità sospensione, corrono un grandissimo rischio se il computer non richiede l'accesso alla ripresa dalla modalità sospensione. È possibile trovare informazioni relative all'attivazione di questa impostazione in [To password-protect your computer during standby or hibernation](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/pwrmn_passwordprotect_standby.mspx?mfr=true) (in inglese), che fa parte della documentazione online del prodotto Windows XP Professional.

![](images/Cc162822.important(it-it,TechNet.10).gif)**Importante:**

Microsoft suggerisce di richiedere l'utilizzo delle credenziali per sbloccare un computer dalla modalità sospensione.

#### Computer lasciato con accesso effettuato e desktop sbloccato

Un numero molto ridotto di tecnologie di crittografia risulterà utile se un computer viene lasciato in un luogo pubblico quando un utente autorizzato ha effettuato l'accesso. Alcuni attacchi potrebbero riuscire anche se effettuati contro un computer con un desktop bloccato. Un utente malintenzionato può semplicemente prendere il computer, portarlo in un luogo privato e iniziare a leggere o copiare i dati. Alcune tecnologie di crittografia hanno opzioni che richiedono una chiave esterna ogni volta che viene effettuato l'accesso a un file, ma l'impatto sull'utilizzabilità è così forte che poche organizzazioni scelgono una soluzione così restrittiva. Un'attenuazione più comune è costituita dall'utilizzo di una chiave esterna o token, come una smart card, con memorizzazione nella cache che consente al computer di conservare una copia crittografata della chiave per una migliore utilizzabilità.

#### Individuazione della password di dominio/locale

Un utente malintenzionato che ottiene le credenziali dell'utente potrebbe essere in grado di ottenere l'accesso ai dati crittografati in due modi, in base all'implementazione della crittografia: le credenziali possono essere utilizzate per decrittografare direttamente il materiale oppure possono essere utilizzate per avere accesso al materiale della chiave attraverso attacchi alle credenziali memorizzate nella cache o archiviate dal sistema operativo.

In qualsiasi sistema di protezione, il punto più debole della tecnologia di crittografia è spesso costituito dalla password utente perché le password selezionate dall'utente in genere sono più deboli persino delle chiavi più deboli utilizzate dai comuni algoritmi di crittografia. L'autore di [Avoiding bogus encryption products: Snake Oil FAQ](http://www.faqs.org/faqs/cryptography-faq/snake-oil/) (in inglese) sostiene che persino una frase in inglese di 20 caratteri ha solo 40 bit di casualità, invece dei 20x8=160 bit di casualità previsti. Una password di 8 caratteri avrebbe molto meno di 40 bit di casualità, in base all'opinione espressa da questo autore. Tuttavia, persino questo scenario non ha niente a che vedere con chi scrive la password su carta e la registra sul portatile; cosa che realmente sovverte qualsiasi soluzione di crittografia basata sulla password utente.

![](images/Cc162822.note(it-it,TechNet.10).gif)**Nota:**

Gli attacchi che rilevano la password utente tramite social engineering o altri metodi di attacco non tecnici non vengono trattati in questa guida. Gli attacchi per individuare la password vengono trattati principalmente per illustrare attacchi crittografici a forza bruta o altri attacchi tecnici contro gli archivi delle credenziali.

#### Dati crittografati leggibili dall'interno

Questo rischio è diverso da quelli trattati precedentemente perché l'utente malintenzionato attacca dall'interno piuttosto che dall'esterno. Questo rischio richiama l'attenzione sul fatto che alcune tecnologie di crittografia, specialmente la crittografia per computer come descritta nella seguente sezione, consentono l'accesso ai dati crittografati a qualsiasi utente che possa accedere al computer. L'account utente potrebbe essere locale o in rete (ad esempio, un account nel servizio directory Active Directory®) e l'accesso potrebbe essere effettuato localmente o attraverso la rete.

#### Individuazione della chiave tramite attacchi offline

In questo tipo di attacchi, l'utente malintenzionato monta un disco con i dati crittografati in un sistema operativo diverso o modificato. Tramite una conoscenza approfondita dell'implementazione, l'utente malintenzionato può tentare di isolare le chiavi utilizzate per crittografare i dati e provare a effettuare un attacco a forza bruta sul meccanismo di memorizzazione utilizzato per le chiavi. In questo tipo di attacco viene applicata la regola del minimo sforzo e l'utente malintenzionato tenterà di isolare e attaccare il punto più debole nel meccanismo di memorizzazione. Gli attacchi a forza bruta sulle chiavi moderatamente forti sono molto difficoltosi e richiedono una straordinaria quantità di risorse informatiche. Se la soluzione di crittografia viene implementata in modo adeguato e un attacco a forza bruta risulti essere l'unica possibilità per l'utente malintenzionato, gli obiettivi della protezione dei dati dell'organizzazione si possono considerare raggiunti.

#### Attacchi offline contro il sistema operativo

Questo tipo di attacco tenta di modificare i file di sistema o le impostazioni quando il sistema operativo non è in esecuzione, per rendere più semplice l'accesso ai dati crittografati. Tali attacchi sono tecnicamente difficoltosi e richiedono un'approfondita conoscenza del sistema operativo. Nel contesto di una tecnologia di crittografia completa dei volumi, un possibile attacco è costituito dal fatto che un utente malintenzionato può modificare alcuni dati crittografati su disco nella speranza che questo modifichi un singolo valore di registro o valore hardcoded in un sistema operativo eseguibile che renda il computer meno sicuro.

#### Attacchi online contro il sistema operativo

Questo tipo di attacco tenta di sovvertire le protezioni del sistema operativo quando è in esecuzione. Gli esempi comprendono gli attacchi di acquisizione dei privilegi o i tentativi di eseguire il codice in remoto. Se un utente malintenzionato può riuscire a completare questo tipo di attacco, può recuperare i dati crittografati eseguendo un codice sul computer.

#### Dati non crittografati individuati nel computer

L'esistenza di dati riservati non crittografati costituisce un rischio che qualsiasi soluzione di crittografia deve attenuare. Quasi tutte le soluzioni di crittografia attenuano questo rischio, a meno che l'algoritmo di crittografia utilizzato non possa essere infranto facilmente. Entrambe le tecnologie di crittografia Microsoft trattate in questa guida utilizzano algoritmi di crittografia noti del settore affinché questo rischio possa essere attenuato in generale per tutte le opzioni analizzate. Tuttavia, in alcuni casi, la tecnologia di crittografia potrebbe non essere applicata a file specifici che contengono dati riservati. In molte delle discussioni sui rischi affrontate nella restante parte di questa guida vengono descritti tali casi.

#### Perdita di dati non crittografati tramite il file ibernazione

La modalità di ibernazione è simile al concetto di paging del sistema, ma differisce per il fatto che in questa modalità il computer effettua un'istantanea di tutta la memoria fisica e scrive i dati sul disco in un *file ibernazione*. Se alcuni dati sensibili si trovano nella memoria fisica al momento in cui viene effettuata l'istantanea, verranno scritti sul disco come parte del file ibernazione. Come gli attacchi sul file di paging, gli attacchi contro il file ibernazione in genere vengono eseguiti offline.

#### Perdita di dati non crittografati tramite il file di paging del sistema

I moderni sistemi operativi forniscono una grande quantità di memoria virtuale alle applicazioni effettuando lo swapping dei dati che si trovano in memoria e che non vengono utilizzati su un file di paging archiviato sul disco rigido. Questa funzionalità, tuttavia, crea un rischio perché un'applicazione in esecuzione sul computer può caricare i dati crittografati dal disco, decrittografarli in memoria per utilizzarli e quindi scriverli come dati non crittografati sul disco rigido, sotto forma di file di paging. Alcuni sistemi operativi eliminano il file di paging durante le operazioni di arresto, ma esistono metodi noti per impedire l'eliminazione di tale file (tra cui provocare l'arresto anomalo del sistema operativo). Inoltre, non eliminare il file di paging e vederne il contenuto potrebbe essere inutile. Gli attacchi contro il file di paging quasi sempre prevedono la rimozione del disco rigido dal computer che verrà poi montato su un altro computer oppure l'avvio di un altro sistema operativo sullo stesso computer. Questi attacchi sono noti come *attacchi offline*.

![](images/Cc162822.note(it-it,TechNet.10).gif)**Nota:**

È possibile che il materiale riservato come le chiavi crittografiche, compresi i file temporanei scritti su disco, venga perso attraverso un altro sistema operativo o i meccanismi di memorizzazione nella cache dell'applicazione. Le misure descritte in Data Encryption Toolkit for Mobile PC riguardano l'attenuazione dei rischi per la perdita di dati attraverso il file di paging del sistema, ma possono attenuare anche la perdita dei dati da altri meccanismi di memorizzazione nella cache specifici dell'applicazione.

#### Attacchi alla piattaforma

Alcuni attacchi sono rivolti alle funzionalità hardware o software di una particolare piattaforma. Ad esempio, alcuni attacchi utilizzano la funzionalità di accesso diretto alla piattaforma (DMA) offerta dall'interfaccia IEEE 1394 (FireWire) per tentare di leggere o scrivere sulla memoria di sistema senza che questo sia rilevato dal sistema operativo. Altri attacchi includono la possibilità di accesso alla memoria basato su DMA, eseguito da un dispositivo PCI attivo, e attacchi che sfruttano le funzionalità o le vulnerabilità nei chip bridge del bus PCI e RAM. Il costo dell'implementazione di questi attacchi è sempre stato abbastanza significativo, ma sta diminuendo grazie alla crescente disponibilità di tecniche e apparecchiature richieste.

#### Fattore di autenticazione richiesto nel computer

Questo rischio riguarda le tecnologie di crittografia che possono utilizzare un dispositivo esterno, come una smart card o un dispositivo USB, per conservare le chiavi di crittografia. Gli utenti inconsapevoli di tale rischio potrebbero non essere attenti e lasciare il dispositivo collegato al computer o conservato nella stessa borsa. Poiché questo succede frequentemente, la maggior parte delle organizzazioni non si affida a un unico fattore fisico per la soluzione di crittografia. Questo rischio riguarda anche gli utenti che annotano i codici PIN o le passphrase su carta, ma questo problema dovrebbe essere risolto principalmente tramite la formazione dell'utente e non viene trattato in questa guida.

#### Errore dell'utente

Gli utenti non sempre comprendono appieno la tecnologia che utilizzano o non fanno molta attenzione ai criteri come vorrebbero gli amministratori IT. Questo rischio riguarda gli utenti che non si attengono alle direttive perché non sanno come attivare la crittografia, perché dimenticano di crittografare un particolare file o perché non prestano attenzione ai criteri di protezione dei dati.

[](#mainsection)[Inizio pagina](#mainsection)

### Approcci alla protezione dei dati

Il progetto e l'implementazione della tecnologia di protezione dei dati riguardano le scelte che influiscono sulla protezione, l'utilizzabilità e la gestione operativa della tecnologia stessa, quando viene distribuita. Sebbene non sia completa, la discussione sulle tecnologie del seguente elenco faciliterà la comprensione del materiale presentato in questa guida. Queste tecnologie di protezione dei dati includono quanto segue:

-   Crittografia basata su software

-   Crittografia basata su hardware

-   Crittografia prima dell'avvio (precedente al sistema operativo)

-   Crittografia dopo l'avvio (sistema operativo)

-   Crittografia a livello dell'applicazione

-   Crittografia a livello di cartella/file

-   Crittografia completa dei volumi

-   Crittografia per utente

-   Crittografia per computer

#### Crittografia basata su software

La crittografia basata su software è lo standard per la maggior parte dei prodotti e delle tecnologie di protezione dei dati. L'alternativa, la crittografia basata su hardware, necessita di hardware crittografico specializzato che non è mai stato molto diffuso sui PC. Con la crittografia basata su software, le operazioni di crittografia vengono eseguite nella CPU dei computer. Quando il computer viene spento, entra in modalità di ibernazione o di sospensione, le chiavi di crittografia vengono generalmente memorizzate crittografate su disco. Un'opzione tipica consiste nel conservare una chiave iniziale separata dal computer, ad esempio su un dispositivo USB, utilizzata per decrittografare il materiale della chiave memorizzato. Quando il computer è in funzione, le chiavi di crittografia, in genere, vengono conservate in memoria.

I punti di forza della crittografia basata su software comprendono:

-   **La capacità di aggiornare l'implementazione**. Le tecnologie di crittografia basata su software possono essere aggiornate in qualsiasi momento per correggere eventuali errori, aggiungere nuove funzionalità o sfruttare nuovi algoritmi.

-   **Nessun requisito hardware particolare**. Dato che non viene richiesto hardware particolare, le tecnologie di crittografia basata su software possono, in genere, essere applicate a tutti i computer dell'organizzazione.

I punti deboli e i problemi della crittografia basata su software comprendono:

-   **Punti deboli del software**. Nelle implementazioni che si basano solo su software, il software potrebbe essere attaccato nel tentativo di sovvertire la modalità protetta di funzionamento. Un tipico attacco costituisce nel modificare i file binari del sistema operativo in modo da poter impedire la crittografia, manipolare in qualche modo le chiavi o indebolire significativamente l'operazione di crittografia.

-   **Individuazione della chiave**. Se una chiave di crittografia viene conservata nel computer, un attacco potrebbe individuarne il valore. È importante capire come viene protetta la chiave. Se la chiave viene decrittografata utilizzando solo altro materiale della chiave che si trova sullo stesso computer, considerare che un utente malintenzionato abile e determinato potrebbe individuare la chiave.

#### Crittografia basata su hardware

Alcuni meccanismi di crittografia sfruttano hardware crittografico speciale per isolare le operazioni di crittografia dalla CPU principale e per fornire una maggiore protezione per la memorizzazione della chiave. Tale hardware generalmente include i mezzi per memorizzare in modo sicuro una o più chiavi crittografiche e potrebbe anche includere funzioni per l'esecuzione di operazioni crittografiche nell'hardware in modo che la chiave non venga mai resa disponibile ad altri componenti software e hardware.

I punti di forza della crittografia basata su hardware comprendono:

-   **Le chiavi di crittografia sono protette da vulnerabilità del software e del sistema operativo**. La crittografia basata su hardware generalmente assicura che le parti private delle coppie di chiavi siano separate dalla memoria controllata dal sistema operativo.

-   **Le operazioni di crittografia sono protette da vulnerabilità del software e del sistema operativo.** La crittografia basata su hardware è indipendente dal sistema operativo e non è esposta a vulnerabilità del software esterne.

I punti deboli e i problemi della crittografia basata su hardware comprendono:

-   **Disponibilità limitata**. L'hardware di crittografia non è sempre disponibile. Ad esempio, il modulo TPM utilizzato da BitLocker non può essere applicato a computer più vecchi e non è disponibile su tutti i computer più recenti.

-   **Difficile da aggiornare**. Se viene trovato un difetto in un sistema basato su hardware, generalmente deve essere sostituito. La stessa cosa vale se il produttore desidera aggiungere nuove funzionalità o supporto per nuovi algoritmi all'hardware.

#### Crittografia prima dell'avvio (precedente al sistema operativo)

È possibile aggiungere firmware a livello BIOS ai computer affinché tutti i dati scritti su un volume del disco rigido vengano crittografati e tutti i dati letti dal disco vengano decrittografati. Questa operazione può essere trasparente al sistema operativo e quindi essere applicata ai file del sistema operativo stesso.

Se un hardware crittografico come un TPM è disponibile, può essere utilizzato per rendere la decrittografia e la crittografia prima dell'avvio più sicure. I computer che contengono un TPM possono creare anche una chiave crittografata e collegata a determinate misure della piattaforma come il codice record di avvio principale (MBR), il settore di avvio NTFS, il blocco di avvio NTFS e il Boot Manager NTFS. Questo tipo di chiave può essere decrittografato solo quando tali misure della piattaforma hanno gli stessi valori che avevano quando la chiave è stata creata. Questo processo è noto come *esecuzione del sealing* della chiave sul TPM e la decrittografia è nota come *rimozione del sealing*.

Il TPM può anche eseguire il sealing e rimuovere il sealing dei dati generati esternamente al TPM. L'effetto pratico di questa funzionalità è che la capacità di annullare la chiave può dipendere dalla modifica di alcune caratteristiche della piattaforma, presumibilmente effettuata attraverso l'alterazione dannosa che tenta di annullare le misure di protezione come la crittografia.

Poiché la crittografia viene applicata ai file del sistema operativo, la chiave per decrittografare questi file deve essere fornita prima della sequenza di avvio del sistema operativo. La chiave può variare tra diverse soluzioni e può essere derivata da un codice PIN o una chiave archiviata su un dispositivo hardware come una smart card o un token USB.

I punti di forza della crittografia prima dell'avvio includono quanto segue:

-   **I file del sistema operativo sono protetti contro gli attacchi offline**. Tutti i file di configurazione e di sistema sono protetti dalla soluzione di crittografia completa dei volumi. Anche se un utente malintenzionato può montare un volume protetto con un sistema operativo diverso, un *attacco offline*, non potrà fare altro che rendere inattivo il sistema operativo.

-   **Protezione maggiore per i file del sistema operativo**. L'hardware crittografico come il TPM v1.2 con gli aggiornamenti BIOS compatibili consentono di convalidare l'integrità dei componenti di avvio importanti.

I punti deboli e i problemi della crittografia prima dell'avvio comprendono quanto segue:

-   **La strategia di ripristino dei dati è obbligatoria**. Qualsiasi errore di BIOS, TPM o meccanismo di memorizzazione della chiave renderà tutti i dati nel computer illeggibili. Gli errori hardware spesso sono più difficili da diagnosticare, classificare e riparare rispetto agli errori software. Le riparazioni possono richiedere più tempo se l'hardware deve essere restituito al produttore o riparato da una struttura esterna. È necessario sviluppare e sperimentare frequentemente una strategia affidabile ed efficace per il backup e il ripristino della chiave.

-   **Gli aggiornamenti software possono essere più difficoltosi**. Poiché i file del sistema operativo e altri file sono crittografati e convalidati contro una firma, l'aggiornamento potrebbe richiedere un processo particolare. Tale requisito costituisce costi operativi aggiuntivi per i computer che utilizzano la tecnologia di crittografia prima dell'avvio.

#### Crittografia dopo l'avvio (sistema operativo)

La crittografia dopo l'avvio può essere eseguita dal sistema operativo o da qualsiasi applicazione in esecuzione sul computer. EFS è un esempio di tecnologia di crittografia dopo l'avvio. Si tratta di una funzionalità integrata nel sistema operativo Windows e quindi non può essere utilizzata per crittografare il sistema operativo stesso. Tuttavia, costituisce un metodo efficace per la protezione dei dati dell'utente e dell'applicazione.

I punti di forza della crittografia dopo l'avvio includono quanto segue:

-   **Gli errori di crittografia non rendono il computer inutilizzabile**. Anche se la tecnologia di crittografia non riesce, il computer potrà essere utilizzato. Pertanto, è possibile recuperare i dati crittografati senza utilizzare un secondo computer.

I punti deboli e i problemi della crittografia dopo l'avvio comprendono quanto segue:

-   **Nessuna protezione per configurazione e file del sistema operativo**. Se viene effettuato l'accesso al disco rigido che contiene dati riservati quando è montato su un altro computer o quando il portatile viene avviato con un sistema operativo diverso, è possibile alterare il sistema operativo originale in modo che consenta la sovversione della crittografia.

-   **La strategia di ripristino dei dati è obbligatoria**. Qualsiasi errore del sistema operativo o del software applicativo potrebbe rendere i dati protetti illeggibili. È necessario sviluppare e sperimentare frequentemente una strategia affidabile ed efficace per il backup e il ripristino della chiave.

#### Crittografia a livello dell'applicazione

La crittografia può essere implementata anche esternamente al BIOS o ai livelli del sistema operativo e può essere eseguita a livello dell'applicazione. Molte applicazioni oggi offrono diverse funzionalità di crittografia dei dati, incluse WinZip, Microsoft Office e Intuit Quicken.

I punti di forza della crittografia a livello dell'applicazione includono quanto segue:

-   **Indipendenza della piattaforma**. Se l'applicazione viene eseguita su diversi sistemi operativi, i dati dell'applicazione crittografati possono generalmente essere spostati da una piattaforma a un'altra ed essere decrittografati, se è presente la chiave corretta.

-   **Spostamento dei dati quando sono crittografati**. Quando i dati sono crittografati a livello del sistema operativo, in genere, vengono decrittografati quando vengono eseguite operazioni del file system quali la copia e lo spostamento. Se la cartella di destinazione o il sistema è configurato per la crittografia, i dati possono essere crittografati con una serie di chiavi completamente diversa. La crittografia a livello dell'applicazione generalmente consente all'utente di spostare i dati nel formato crittografato di origine in un'altra posizione.

I punti deboli e i problemi della crittografia a livello dell'applicazione comprendono quanto segue:

-   **Dipendenza dell'applicazione**. I dati spostati da un contenitore o formato dell'applicazione a un altro contenitore o formato, solitamente non possono mantenere la crittografia. Ad esempio, un utente può estrarre un file da un archivio di WinZip crittografato e il file estratto verrà decrittografato. Se l'utente non elimina il file una volta finito di lavorarci, i dati potrebbero essere compromessi.

#### Crittografia a livello di cartella/file

La crittografia a livello di cartella e file è un modo per proteggere alcuni file e cartelle con i dati che contengono. Con questa soluzione, vengono protetti solo i file appositamente configurati per essere crittografati. Tutti gli altri dati nel computer non sono crittografati. Un approccio tipico alla crittografia a livello di cartella/file è quello di creare una chiave di crittografia univoca per ogni file o cartella. Questo approccio ha l'ulteriore vantaggio di rendere possibile l'implementazione della crittografia per utente, come descritto in seguito in questo capitolo.

I punti di forza della crittografia a livello di cartella/file ben implementata includono quando segue:

-   **Migliori prestazioni rispetto alla crittografia completa dei volumi**. Le prestazioni del computer non dovrebbero subire cambiamenti drastici. Tuttavia, qualche cambiamento sarà inevitabile. La crittografia a livello di cartella/file riduce l'impatto generale sulle prestazioni della crittografia perché il costo aggiuntivo è applicabile solo ai file che devono essere crittografati per soddisfare i criteri di protezione dei dati dell'organizzazione.

-   **Crittografia selettiva**. I controlli precisi di questa soluzione consentono agli utenti di crittografare solo i dati sensibili e consentono agli amministratori di imporre o bloccare la crittografia di tipi di cartelle, file o dati specifici.

-   **Supporto per più utenti**. I proprietari dei file possono consentire a utenti aggiuntivi di leggere o modificare i file mantenendoli crittografati. Questa funzionalità fa sì che i file crittografati siano condivisi in modo sicuro tra gli utenti.

I punti deboli della crittografia a livello di cartella/file includono quanto segue:

-   **È possibile che si verifichi una perdita dei dati riservati attraverso i file generati dal sistema operativo o dalle applicazioni**. In genere, il sistema operativo scrive i dati dell'applicazione contenuti in memoria sui file su disco. Questi dati dell'applicazione possono contenere dati riservati. Nel sistema operativo Windows, questi file comprendono il file di paging del sistema e il file ibernazione. Il sistema operativo può anche generare file di registro o altri tipi di file innocui che potrebbero contenere dati riservati.

-   **È possibile che si verifichi una perdita dei dati riservati attraverso la memorizzazione nella cache dei dati a livello dell'applicazione**. Le applicazioni possono implementare i meccanismi di registrazione o di memorizzazione nella cache, come i file temporanei, tramite cui è possibile che si verifichi una perdita dei dati riservati. Un buon esempio è costituito dai file di ripristino creati da Microsoft Word. Questo punto debole per certi versi può essere attenuato configurando l'applicazione in modo che crei sempre i file temporanei in una directory specifica e quindi configurando la soluzione di crittografia in modo che crittografi tutti i file che si trovano in quella cartella.

-   **I file potrebbero essere copiati accidentalmente su una cartella o un file non crittografato**. Poiché solo alcuni file e cartelle sono crittografati, è possibile che un utente copi inavvertitamente il contenuto di un file su un altro file contenuto in una cartella non configurata per la crittografia.

#### Crittografia completa dei volumi

La crittografia completa dei volumi costituisce un completamento della crittografia a livello di cartella/file in quanto previene i problemi comuni di quest'ultima. Se il volume da proteggere contiene file del sistema operativo, la crittografia prima dell'avvio è necessaria per l'approccio alla crittografia completa dei volumi. Se un'organizzazione sceglie di configurare una soluzione di crittografia completa dei volumi che contiene i file del sistema operativo, sarebbe opportuno considerare i punti deboli e i punti di forza della crittografia prima dell'avvio.

I seguenti punti di forza principali della crittografia completa dei volumi sono innanzitutto attenuazioni effettuate ai punti deboli della crittografia a livello di cartella/file, precedentemente descritti.

-   **I file temporanei del sistema operativo sono crittografati**. Poiché l'intero volume è crittografato, i file scritti sul volume vengono automaticamente crittografati, inclusi il file di paging del sistema e il file ibernazione.

-   **I file temporanei dell'applicazione vengono crittografati**. Tutti i file temporanei creati da un'applicazione vengono scritti sul volume crittografato e quindi vengono automaticamente crittografati.

-   **Tutti i file creati dall'utente vengono automaticamente crittografati**. Anche nel caso in cui l'utente copi un file in una cartella diversa del volume, verrà crittografato automaticamente. Con la crittografia completa dei volumi è più difficile che l'utente sovverta per errore la soluzione di crittografia.

I punti deboli e i problemi della crittografia completa dei volumi comprendono quanto segue:

-   **Prestazioni ridotte**. Ogni blocco che si trova su un volume protetto deve essere decrittografato quando viene letto e crittografato di nuovo al momento in cui viene riscritto su disco. Questa funzionalità si applica ai file di configurazione ed eseguibili del sistema operativo, ai file di configurazione ed eseguibili dell'applicazione e a tutti i file di dati. Sebbene la crittografia moderna sia relativamente efficace, con la crittografia completa dei volumi è prevedibile che si verifichi una riduzione delle prestazioni del sistema che può variare dal 5 al 15 percento.

-   **Protezione limitata contro gli attacchi effettuati dall'interno**. La crittografia completa dei volumi fornisce protezione contro una serie di attacchi offline, ma generalmente fornisce una protezione limitata contro gli attacchi effettuati dall'interno, che, di solito, hanno (o riescono a ottenere) la capacità di accedere a un computer con un account legittimo.

#### Crittografia per utente

La crittografia può essere implementata in modo che più utenti possano decrittografare le chiavi necessarie per crittografare e decrittografare i file di dati sul computer utilizzando la propria chiave univoca, che potrebbe essere una password o una chiave conservata su un USB o dispositivo simile. Quando questo approccio è combinato con la crittografia a livello cartella/file a chiave singola, è possibile fornire l'accesso a singoli utenti su base file per file.

I punti di forza della crittografia per utente includono quanto segue:

-   **Controllo accurato su chi può leggere i dati crittografati**. Gli altri utenti del computer non possono leggere i dati crittografati a meno che non sia specificatamente concesso dal proprietario del file. Questa funzionalità fornisce un livello di controllo degli accessi e di riservatezza dei dati.

-   **La possibilità di crittografare selettivamente solo i dati sensibili**. Con un sistema di crittografia per utente correttamente implementato, è possibile selezionare con esattezza quali file e cartelle sono protette.

-   **La possibilità di crittografare i file per più utenti**. Un sistema di crittografia per utente correttamente implementato consente al proprietario di un file di crittografare un unico file per più utenti, consentendo la condivisione e mantenendo al tempo stesso una buona protezione. Inoltre, questa funzionalità può essere utilizzata per implementare il ripristino dei dati consentendo a un agente di recupero autorizzato di decrittografare i file protetti.

I punti deboli e i problemi della crittografia per utente comprendono quanto segue:

-   **Protezione solo come chiave/credenziale debole**. Con questo approccio, ogni chiave di crittografia/decrittografia deve essere crittografata con più chiavi (una per ogni utente univoco). Ogni chiave crittografata può essere attaccata separatamente da un utente malintenzionato che cerca una chiave particolarmente debole, in particolar modo in caso di accesso locale, di rete o quando le password non di accesso vengono utilizzate per ricavare il materiale della chiave.

#### Crittografia per computer

Alcune implementazioni di crittografia dei dati non forniscono la possibilità a diversi utenti, ognuno con una chiave o password differente, di decrittografare la o le chiavi master per decrittografare i dati nel computer. In simili implementazioni esiste esclusivamente una chiave che può essere utilizzata per accedere al computer, ivi compresi tutti i dati crittografati.

I punti di forza della crittografia per computer includono quanto segue:

-   **Sequenza di derivazione della chiave più semplice**. Dato che può essere utilizzata solo una chiave per iniziare la sequenza di derivazione della chiave, l'intero meccanismo risulta essenzialmente più semplice. La riduzione della difficoltà può, anche se non sempre, portare a una maggiore protezione.

I punti deboli e i problemi della crittografia per computer comprendono quanto segue:

-   **Nessuna protezione contro gli attacchi effettuati dall'interno**. Qualsiasi utente autorizzato dal criterio ad accedere al computer protetto può accedere a qualsiasi file non crittografato sul computer.

[](#mainsection)[Inizio pagina](#mainsection)

### Ulteriori informazioni

-   [Cryptography for Network and Information Security (in inglese)](http://www.microsoft.com/technet/prodtechnol/windows2000serv/reskit/distrib/dsch_key_rveg.mspx)

-   [To password-protect your computer during standby or hibernation (in inglese)](http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/pwrmn_passwordprotect_standby.mspx?mfr=true)

-   [Avoiding bogus encryption products: Snake Oil FAQ (in inglese)](http://www.faqs.org/faqs/cryptography-faq/snake-oil/)

-   [Special Publication 800-12 – An Introduction to Computer Security: The NIST Handbook (in inglese)](http://csrc.nist.gov/publications/nistpubs/800-12/)

-   [Federal Information Processing Standards (FIPS) 140 Evaluation](http://www.microsoft.com/technet/archive/security/topics/issues/fipseval.mspx) standards (in inglese)

-   [Windows Platform Common Criteria Certification (in inglese)](http://www.microsoft.com/technet/security/prodtech/windowsxp/ccc/default.mspx)

-   [The Trustworthy Computing Security Development Lifecycle (in inglese)](http://msdn2.microsoft.com/en-us/library/ms995349.aspx)

**Download**

[Get the Data Encryption Toolkit for Mobile PCs (in inglese)](http://go.microsoft.com/fwlink/?linkid=81666)

**Partecipa**

[Iscriviti per partecipare al programma Data Encryption Toolkit Beta](https://connect.microsoft.com/invitationuse.aspx?programid=790&invitationid=desa-r7gd-3f73&siteid=14)

**Notifiche di aggiornamento**

[Iscriviti per ricevere informazioni su aggiornamenti e nuovi rilasci](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti**

[Inviaci i tuoi commenti o suggerimenti](mailto:secwish@microsoft.com?oggetto=analisi%20della%20protezione%20di%20data%20encryption%20toolkit%20for%20mobile%20pc%20su%20technet)

[](#mainsection)[Inizio pagina](#mainsection)
