---
TOCTitle: 'Determinazione dello stato corrente dell''infrastruttura IT'
Title: 'Determinazione dello stato corrente dell''infrastruttura IT'
ms:assetid: 'f8e1db59-5ff2-47fb-aa95-0fbd06aeea6c'
ms:contentKeyID: 20200806
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536206(v=TechNet.10)'
---

Isolamento del server e del dominio tramite IPsec e criteri di gruppo
=====================================================================

### Capitolo 3: Determinazione dello stato corrente dell'infrastruttura IT

Aggiornato: 16 febbraio 2005

Il presente capitolo contiene indicazioni su come ottenere le informazioni necessarie per la pianificazione e la distribuzione di una soluzione di isolamento del server e del dominio. Affinché la distribuzione abbia esito positivo, è necessario disporre di un quadro preciso e aggiornato dell'infrastruttura informatica. Dopo aver letto questo capitolo, risulterà chiaro quali informazioni sono necessarie per completare la progettazione di una soluzione di isolamento del server e del dominio.

La parte finale di questo capitolo è dedicata al processo di individuazione e documentazione di quali dei computer identificati possono essere utilizzati come computer "attendibili" all'interno della soluzione. Il team di progettazione dovrà utilizzare queste informazioni per elaborare i piani della soluzione.

##### In questa pagina

[](#ehaa)[Prima di iniziare](#ehaa)
[](#egaa)[Destinatari di questo capitolo](#egaa)
[](#efaa)[Identificazione dello stato corrente](#efaa)
[](#eeaa)[Considerazioni sulla capacità](#eeaa)
[](#edaa)[Considerazioni pre-implementazione](#edaa)
[](#ecaa)[Determinazione dell'attendibilità](#ecaa)
[](#ebaa)[Acquisizione dei costi di aggiornamento degli host](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Prima di iniziare

Prima di utilizzare le informazioni contenute nel presente capitolo, accertarsi che l'organizzazione e gli addetti che le utilizzeranno rispondano ai seguenti prerequisiti. Le istruzioni riportate in questo capitolo sono state appositamente concepite per soddisfare le esigenze di organizzazioni che presentano i requisiti descritti di seguito. La soddisfazione di questi requisiti assicura infatti la possibilità di sfruttare al massimo le istruzioni fornite che, in caso contrario, potrebbero avere un impatto negativo.

#### Prima di iniziare

È necessario conoscere i concetti fondamentali del protocollo IPsec e possedere un'approfondita competenza nei seguenti campi:

-   Servizi di autenticazione di Microsoft® Windows® (in particolare del protocollo di autenticazione Kerberos versione 5)

-   Concetti relativi al servizio di directory Active Directory®, inclusi la struttura e gli strumenti di Active Directory, la gestione di utenti, gruppi e altri oggetti di Active Directory e l’utilizzo dei criteri di gruppo

-   La protezione dei sistemi Windows, inclusi concetti quali utenti, gruppi, controllo ed elenchi di controllo dell'accesso (ACL)

-   Convenzioni di denominazione dell'organizzazione

-   Ubicazioni fisiche e logiche dell'organizzazione

-   Pratiche di gestione dei rischi utilizzate dall'organizzazione

-   Concetti di base sulle rete, incluso il filtraggio delle porte tramite firewall  

Prima di leggere il presente capitolo, è inoltre necessario aver letto i capitoli precedenti di questa guida e conoscere a fondo l'architettura e i concetti di progettazione della soluzione.

#### Prerequisiti organizzativi

La pianificazione dei gruppi di isolamento di un'organizzazione è un'attività che solitamente coinvolge numerosi soggetti. Le informazioni necessarie per definire le precise esigenze spesso provengono da fonti diverse all'interno dell'organizzazione. È necessario consultarsi con le persone dell'organizzazione che potrebbero essere coinvolte nella pianificazione dei gruppi, fra le quali:

-   Sponsor esecutivi

-   Personale addetto alla protezione e al controllo

-   Personale addetto alla progettazione, amministrazione e gestione di Active Directory

-   Proprietari di DNS (Domain Name System), server Web e applicazioni

-   Amministratori di rete e personale operativo

-   Personale addetto alla formazione interna e all'help desk  

    **Nota:** a seconda della struttura dell'organizzazione IT, questi ruoli possono essere ricoperti da più persone oppure un numero ristretto di addetti può ricoprire più ruoli.

Oltre ad acquisire le informazioni dai team sopra elencati, è importante comprendere che le pratiche operative in vigore dovranno essere aggiornate dopo l'introduzione di IPsec nell'ambiente. È inoltre possibile che sia necessario aggiornare il software e l'hardware, ad esempio aggiornamenti del BIOS e del firmware per le periferiche di rete. Infine potrebbero essere necessari strumenti di rete aggiuntivi, che facilitino i processi di supporto e risoluzione dei problemi relativi all'ambiente IPsec.

#### Prerequisiti per l'infrastruttura IT

Il presente capitolo presuppone inoltre l'esistenza della seguente infrastruttura IT:

-   Un dominio Active Directory basato su Microsoft Windows Server™ 2003 in modalità nativa o mista. Questa soluzione utilizza gruppi universali per l'applicazione dell'oggetto Criteri di gruppo (GPO, Group Policy Object). Se l'organizzazione non utilizza la modalità nativa o mista, è comunque possibile applicare l'oggetto Criteri di gruppo tramite l'uso di configurazioni di gruppo standard globali e locali. Tuttavia, poiché questa opzione è più complessa da gestire, la presente soluzione non la utilizza.

    **Nota**: Windows Server 2003 include numerosi miglioramenti relativi ai criteri IPsec. Nessun aspetto specifico della presente soluzione ne impedisce l'utilizzo con Windows 2000. Tuttavia, la soluzione è stata testata solo su un sistema Windows Server 2003 con servizio Active Directory.
    Per ulteriori informazioni sui miglioramenti apportati a IPsec in Windows Server 2003, consultare la pagina [New features for IPsec](http://www.microsoft.com/resources/documentation/windowsserv/2003/standard/proddocs/en-us/ipsec_whatsnew.asp) sul sito Web Microsoft all'indirizzo www.microsoft.com/resources/documentation/WindowsServ/
    WindowsServ/2003/standard/
    proddocs/en-us/ipsec\_whatsnew.asp (in lingua inglese).

-   Competenze ed esperienza necessarie per eseguire il monitoraggio di rete, analizzare i dati di monitoraggio e adottare decisioni di pianificazione della capacità sulla base di detti dati.

    **Nota**: in numerose organizzazioni l'impiego degli strumenti di monitoraggio della rete è limitato; sarà pertanto necessario assicurarsi che vengano seguite procedure operative corrette per l'utilizzo di questi strumenti.

-   Uno strumento che consenta di acquisire i dati della configurazione di rete relativi a host presenti sulla rete. Per raccogliere queste informazioni, è possibile, ad esempio, utilizzare i sistemi esistenti di gestione delle risorse. Per ulteriori informazioni, vedere la sezione "Rilevamento degli host" in questo capitolo.

[](#mainsection)[Inizio pagina](#mainsection)

### Destinatari di questo capitolo

Questo capitolo è stato concepito per i professionisti IT responsabili dell'elaborazione dell'inventario dell'infrastruttura IT, che verrà utilizzato dagli architetti e dai progettisti della soluzione. Questi professionisti IT sono solitamente parte dello staff del servizio di supporto o del personale operativo dell'organizzazione. Per poter trarre il massimo vantaggio da questo capitolo, è necessario un buon livello di conoscenze tecniche delle tecnologie e degli strumenti utilizzati nel processo di raccolta delle informazioni e dell'infrastruttura dell'organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Identificazione dello stato corrente

Il processo di acquisizione e gestione di un archivio affidabile di computer, software e periferiche di rete di un'organizzazione rappresenta una delle sfide classiche del settore IT. Per attuare un progetto di successo, le informazioni acquisite tramite questo processo sono essenziali. Prima di avviare il processo di pianificazione di un progetto di isolamento del server e del dominio, è necessario raccogliere ed analizzare informazioni aggiornate su computer, rete e servizi di directory già distribuiti all'interno dell'organizzazione. Queste informazioni consentiranno di progettare una configurazione che consideri tutti i possibili elementi dell'infrastruttura esistente. Pertanto, se le informazioni raccolte non sono precise, potrebbero verificarsi dei problemi in fase di implementazione, correlati alle periferiche e ai computer non considerati nella fase di pianificazione. Le sezioni seguenti delineano le informazioni necessarie per ciascuna area e riportano esempi delle informazioni acquisite per la soluzione di isolamento del server e del dominio della Woodgrove Bank.

#### Rilevamento della rete

L'aspetto forse più importante della pianificazione di uno scenario di isolamento del server e del dominio è l'architettura della rete, visto che IPsec si *sovrappone* al protocollo Internet stesso. Una comprensione incompleta o imprecisa della rete impedirà infatti il successo della soluzione di isolamento. La comprensione della disposizione delle subnet, degli schemi di indirizzamento IP e dei modelli di traffico rientrano in questo ambito, ma i due componenti seguenti sono essenziali per completare la fase di pianificazione di questo progetto:

-   Documentazione sulla segmentazione della rete

-   Documentazione sul modello di traffico di rete in uso

L'obiettivo consiste nell'acquisire informazioni sufficienti a identificare una risorsa in base alla sua posizione sulla rete oltre che alla sua posizione fisica.

È opportuno iniziare con un'architettura di rete molto accurata, con intervalli di indirizzi facilmente individuabili e con il minor numero possibile di sovrapposizioni o intervalli discontinui. Potrebbero però esistere esigenze aziendali specifiche o circostanze (quali ad esempio fusioni e acquisizioni) che non consentono di creare una rete standardizzata. Se, però, lo stato corrente è documentato e chiaro, l'attività di identificazione della rete e delle sue risorse gestite risulta più semplice. Evitare di utilizzare reti complesse e scarsamente documentate come punto di partenza per la progettazione, poiché è possibile che rimangano numerose aree non identificate, che possono causare problemi durante l'implementazione.

Queste istruzioni facilitano il reperimento delle informazioni utili per la pianificazione dell'isolamento del server e del dominio, ma non si pongono come obiettivo quello di affrontare altri aspetti, quali l'indirizzamento TCP/IP e le subnet mask a lunghezza variabile, la segmentazione delle VLAN (Virtual Local Area Netework) o altri metodi e tecniche di ottimizzazione della rete. Le informazioni acquisite verranno utilizzate per formulare l'implementazione e definire i componenti operativi della soluzione di isolamento del server e del dominio.

##### Documentazione sulla segmentazione della rete

Se l'organizzazione non dispone di una documentazione relativa all'architettura di rete in uso che possa essere utilizzata come riferimento, questa documentazione dovrà essere acquisita non appena possibile e prima di procedere all'implementazione della soluzione. Se la documentazione non è aggiornata o non è stata recentemente convalidata, sono disponibili due opzioni di base:

-   Accettare che le informazioni possano causare rischi inutili per il progetto.

-   Avviare un progetto di rilevamento, sia tramite processi manuali che mediante uno strumento di analisi della rete, che possa fornire le informazioni necessarie a documentare la topologia della rete.

Nonostante le informazioni necessarie possano essere organizzate in numerosi modi diversi, il metodo più efficace include una serie di diagrammi che illustrino e chiariscano la configurazione di rete in uso. Quando si elaborano i diagrammi di rete, evitare di inserire un numero eccessivo di informazioni. Se necessario, è preferibile utilizzare più diagrammi che mostrino diversi livelli di dettaglio.

Nello scenario Woodgrove Bank, ad esempio, il team ha creato il diagramma seguente, che rappresenta una vista generale della rete WAN (Wide Area Network) esistente e dell'ambiente del sito:

[![](images/Dd536206.SGFG0301(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536206.sgfg0301_big(it-it,technet.10).gif)

**Figura 3.1. Diagramma della rete WAN e del sito della Woodgrove Bank**

Dopo aver elaborato questo diagramma, il team si è dedicato alla creazione di diagrammi più dettagliati per ciascun sito e, infine, per ciascuna subnet dei siti.

È possibile che durante la fase di elaborazione della documentazione di rete si individuino alcuni servizi di rete e applicazioni non compatibili con IPsec. Esempi attuali di queste incompatibilità sono:

-   Tecnologia Cisco NetFlow su router, che non consente l'analisi dei pacchetti scambiati fra membri di un ambiente IPsec sulla base di protocolli o porte.

-   Qualità del servizio (QoS, Quality of Service) basata su router, che non consente di utilizzare porte o protocolli per definire priorità del traffico. È tuttavia possibile utilizzare indirizzi IP specifici per definire queste priorità. Ad esempio, una regola del tipo "Da qualsiasi a qualsiasi, con porta 80 prioritaria" non funzionerebbe, mentre una regola del tipo "Da qualsiasi a 10.0.1.10 prioritario" non creerebbe problemi.

-   Periferiche che non supportano o non consentono il protocollo IP 50, vale a dire la porta utilizzata da ESP (Encapsulating Security Payload).

-   Servizi WFQ (Weighted Fair Queuing) o altri metodi per definire le priorità del traffico dei router basati sul flusso.

-   Sistemi di monitoraggio di rete, che potrebbero non essere in grado di analizzare i pacchetti ESP non crittografati (ESP senza crittografia).

    **Nota:** la versione 2.1 di Microsoft Network Monitor integra un parser ESP che facilita la risoluzione dei problemi dei pacchetti IPsec non crittografati. Network Monitor è incluso in Microsoft Systems Management Server (SMS). Per ulteriori informazioni, consultare la pagina [Microsoft Systems Management Server](http://www.microsoft.com/smserver/default.asp) all'indirizzo www.microsoft.com/italy/smserver//.

-   Per le periferiche che non sono in grado di analizzare i pacchetti ESP, eventuali ACL che specifichino le regole per porte o protocolli non verranno elaborati sui pacchetti ESP.

-   Per le periferiche dotate di parser ESP e che utilizzano la crittografia, eventuali ACL che specifichino le regole per porte o protocolli non verranno elaborati sui pacchetti ESP.

Quando si utilizzano porte e protocolli, IPsec non rispetta le priorità basate sulla rete e la gestione del traffico basata su porte o protocolli. Purtroppo non esistono soluzioni alternative per i pacchetti crittografati. Se la gestione del traffico o delle priorità deve essere basata su porte o protocolli, l'host stesso deve essere in grado di eseguire le funzioni di gestione del traffico o delle priorità.

È quindi importante registrare con precisione quali informazioni sono necessarie per le varie periferiche di rete.

###### Periferiche dell’infrastruttura di rete

Quando la soluzione verrà implementata, le periferiche che costituiscono l'infrastruttura di rete (router, switch, unità di bilanciamento del carico e firewall) comunicheranno utilizzando IPsec. Per questa ragione, è molto importante esaminare le seguenti caratteristiche di queste periferiche presenti sulla rete, al fine di garantire che esse saranno in grado di soddisfare i requisiti tecnici e fisici del progetto:

-   **Marca/Modello**. È possibile utilizzare queste informazioni per verificare le funzionalità supportate da ciascuna periferica. È inoltre necessario verificare il BIOS o il software in esecuzione sulle periferiche, per accertarsi che IPsec sia supportato.

-   **Quantità di RAM**. Questa informazione è utile quando si calcolano le capacità o l'impatto di IPsec sulle periferiche.

-   **Analisi del traffico**. Queste informazioni (picchi di utilizzo e tendenze quotidiane/settimanali che indicano l'utilizzo quotidiano della periferica) possono sempre essere utili. Per quanto concerne IPsec, questi dati forniscono un'istantanea della periferica e del suo utilizzo nel tempo. Se insorgono dei problemi dopo l'implementazione di IPsec, queste informazioni possono aiutare a comprendere se la causa è legata a un utilizzo eccessivo della periferica.

-   **ACL che interferiscono direttamente su IPsec**. Gli ACL interferiscono direttamente sulla funzionalità di alcuni protocolli. Se, ad esempio, il protocollo Kerberos (UDP \[User Datagram Protocol\] e porta TCP 88) o il protocollo IP (protocollo e non porta) 50 o 51 non sono consentiti, IPsec non potrà funzionare. Se si utilizza l'attraversamento del NAT, le periferiche devono essere configurate in modo da consentire il traffico IKE (Internet Key Exchange - UDP 500 e 4500).

-   **Reti/Subnet connesse a interfacce di periferiche**. Queste informazioni consentono di eseguire la migliore analisi possibile della configurazione della rete interna. La definizione del confine della rete sulla base di un intervallo di indirizzi è immediata e consente di individuare se altri indirizzi sono non gestiti o estranei alla rete interna (come, ad esempio, un indirizzo Internet). Queste informazioni sono necessarie per le decisioni che riguardano i criteri IPsec, illustrate nei capitoli seguenti di questa guida.

-   **Periferiche che eseguono il servizio NAT (Network Address Translation)**. I servizi NAT vengono solitamente utilizzati per convertire un intero intervallo di indirizzi in un solo IP per una rete connessa o per Internet. I responsabili della pianificazione della soluzione devono sapere in quale posizione della rete viene effettuato questo processo.

    **Nota:** l'articolo numero 818043 "[Aggiornamento L2TP/IPSec NAT-T per Windows XP e per Windows 2000](http://support.microsoft.com/kb/818043)" della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/kb/818043, consente di scaricare la funzionalità NAT-T per l'aggiornamento di Windows XP Service Pack (SP) 1 e Windows 2000 SP4. Tuttavia, i risponditori IPsec funzionano correttamente soltanto con il sistema operativo Windows XP SP2 o Windows Server 2003 SP1.

-   **Segmentazione delle VLAN**. Rilevando l'implementazione in uso delle VLAN sulla rete, è possibile comprendere i modelli di traffico o i requisiti di protezione in atto, nonché stabilire come IPsec aumenterà o potenzialmente interferirà con questi requisiti.

-   **Collegamenti a cui sono connesse le periferiche**. Queste informazioni sono utili per rilevare le connessioni dalle periferiche alle reti. Facilitano inoltre l'identificazione della rete logica e delle connessioni a varie posizioni su un'interfaccia specifica.

-   **Dimensioni dell'unità di trasmissione massima (MTU, Maximum Transmission Unit) sulle interfacce delle periferiche**. L'MTU definisce il datagramma di dimensioni massime che può essere trasmesso su un'interfaccia specifica senza suddivisione in parti più piccole (processo noto come "frammentazione"). Per le comunicazioni IPsec, l'MTU è necessario al fine di stabilire le aree in cui avverrà la frammentazione. È necessario individuare i punti di frammentazione dei pacchetti per il protocollo per l'associazione di protezione Internet e la gestione delle chiavi (ISAKMP, Internet Security Association and Key Management Protocol). IPsec configurerà le dimensioni dell'MTU per la sessione in base all'MTU minimo rilevato lungo il percorso di comunicazione in uso e imposterà il bit che impedisce la frammentazione (DF) su 1.

    **Nota:** se il rilevamento dell'MTU del percorso (PMTU) è attivato e funziona correttamente, non è necessario acquisire le dimensioni dell'MTU sulle interfacce delle periferiche. Alcune fonti, quali la *Guida per la protezione di Windows Server 2003*, consigliano di disattivare il rilevamento della PMTU. D'altro canto, però, affinché IPsec funzioni correttamente, questo rilevamento deve essere attivato.

Si noti inoltre che IPsec può influire sui sistemi di rilevamento delle intrusioni (IDS, Intrusion Detection System), perché è necessario utilizzare un parser specifico per interpretare i dati all'interno dei pacchetti. Se questi sistemi IDS non sono dotati di parser, non possono esaminare i dati contenuti nei pacchetti per stabilire se una sessione rappresenta una potenziale minaccia. In tal caso, se l'organizzazione decide di utilizzare IPsec, significa che questo servizio risponde alle sue esigenze più del sistema IDS.

Le informazioni rilevate in base alla procedura riportata in questa sezione sono critiche per il successo del progetto, poiché consentono di comprendere la configurazione attuale e lo stato di "salute" dell'infrastruttura di rete, prima di configurare le periferiche per l'utilizzo di IPsec (o di assegnare loro un maggiore carico, se le periferiche sono già configurate per consentire il traffico IPsec). Analizzando le informazioni relative ai picchi di utilizzo, è possibile stabilire se la periferica è in grado di utilizzare IPsec nello stato in cui si trova oppure se necessita di integrazioni di memoria o aggiornamenti del firmware per supportare il carico previsto. Le informazioni sulla marca e il modello si dimostreranno utili per reperire l'eventuale hardware necessario per aggiornare le periferiche. Potrebbero essere utili anche informazioni sui parametri di configurazione o le caratteristiche peculiari di una marca o un modello. Il numero di ACL configurati sulle periferiche consente di stimare l'impegno necessario per configurare le periferiche stesse per il supporto di IPsec. Se nessuna delle periferiche della rete è configurata per consentire il traffico IPsec e la rete include un numero elevato di router, la configurazione potrebbe richiedere un notevole impegno.

Dopo aver raccolto queste informazioni, è possibile stabilire rapidamente se è necessario aggiornare le periferiche per renderle conformi ai requisiti del progetto, modificare gli ACL o adottare altre misure che assicurino che queste periferiche saranno in grado di gestire i carichi previsti.

##### Analisi del modello di traffico di rete in uso

Dopo aver acquisito le informazioni sull'infrastruttura di rete e l'indirizzamento, la fase logica successiva consiste nell'analizzare attentamente il flusso delle comunicazioni. Se, ad esempio, un reparto quale quello delle risorse umane è distribuito in diversi edifici e si desidera utilizzare IPsec per crittografare i suoi dati, si dovranno acquisire informazioni sui collegamenti fra questi edifici, al fine di stabilire il livello di "attendibilità" da assegnare alla connessione. Un edificio con un grado di protezione elevato e collegato tramite cavi in rame a un altro edificio che però non è protetto può essere oggetto di intercettazioni non autorizzate o di attacchi di tipo ripetizione. Se questo tipo di attacchi rappresenta una minaccia, IPsec potrebbe risultare utile per la mutua autenticazione e la crittografia del traffico per gli host attendibili. Tuttavia, questa soluzione non può compensare il fatto che una mancanza di protezione fisica sugli host attendibili rimane una minaccia.

Quando si analizza il flusso del traffico, esaminare attentamente come le periferiche gestite e non gestite interagiscono, comprese quelle non basate su Windows, quali Linux, UNIX e Mac, e quelle con versioni di Windows precedenti a Windows 2000 SP4. È opportuno porsi domande del tipo: "Alcune comunicazioni avvengono a livello di porta/protocollo?", "Vengono stabilite numerose sessioni fra gli stessi host che attraversano numerosi protocolli?", "Come comunicano fra di loro server e client?" oppure "Esistono attualmente numerose periferiche di protezione o progetti in fase di implementazione o pianificazione che potrebbero interferire con il progetto di isolamento?". Se, ad esempio, si utilizza Windows XP SP2 e Windows Firewall per "chiudere" alcune porte, quali UDP 500, la negoziazione IKE non verrà completata.

Quando si utilizza il processo di modellazione dei pericoli, illustrato nel capitolo 2 "Descrizione dell'isolamento del server e del dominio", per esaminare i diversi tipi di traffico di rete, è possibile individuare facilmente i protocolli e le applicazioni che generano traffico che deve essere protetto da periferiche non attendibili e non gestite. Tra le applicazioni e i protocolli più comunemente utilizzati, figurano:

-   **NetBIOS su TCP/IP (NetBT) e SMB (Server Message Block)**. Su una rete LAN, solitamente le porte 137, 138 e 139 sono abilitate per NetBT e la porta 445 per SMB. Queste porte forniscono, in aggiunta ad altre funzionalità, i servizi di risoluzione dei nomi NetBIOS. Sfortunatamente, esse generano anche le cosiddette sessioni Null. Una *sessione Null* è una sessione che viene stabilita su un host che non utilizza il contesto di protezione di un'identità o utente noto. Queste sessioni sono spesso anonime.

-   **RPC (Remote Procedure Call).** Solitamente, il servizio RPC opera offrendo a un'applicazione una porta di ascolto (nota anche come agente di mapping degli endpoint, porta TCP 135), che comunica poi al "chiamante" (spesso un'altra applicazione) di avviare la comunicazione su un'altra porta dell'intervallo effimero. In una rete segmentata da firewall, questa comunicazione RPC rappresenta una sfida di configurazione, perché implica l'apertura della porta di ascolto di RIPC e di tutte le porte oltre la 1024. L'apertura di un numero così elevato di porte allarga la superficie attaccabile della rete e riduce l'efficacia dei firewall. D'altro canto, il vantaggio di RPC è rappresentato dal fatto che offre un'astrazione della funzionalità nei livelli 1-4 del modello OSI (Open Systems Interconnection) per le applicazioni che lo utilizzano e quindi gli sviluppatori non devono generare chiamate di basso livello verso la rete per le applicazioni distribuite. Visto che numerose applicazioni dipendono da RPC per le loro funzionalità di base, il criterio IPsec dovrà tenerne conto. Per ulteriori informazioni sulla creazione dei criteri IPsec, vedere il capitolo 5 "Creazione dei criteri IPsec per i gruppi di isolamento".

-   **Altro traffico**. IPsec può essere utile per proteggere le trasmissioni fra gli host mediante l'autenticazione dei pacchetti e la crittografia dei dati che essi contengono. L'operazione importante da svolgere consiste nell'identificare *quale* traffico deve essere protetto e le minacce che devono essere tenute sotto controllo. Eventuale altro traffico o tipi di traffico da proteggere dovranno essere analizzati e adeguatamente pianificati. Ad esempio, potrebbe trattarsi di un database speciale a cui possono accedere soltanto alcuni client o un'applicazione appositamente sviluppata per il reparto risorse umane e che deve essere utilizzata soltanto dai responsabili di questo reparto.

Dopo aver documentato lo stato fisico e logico della rete, la fase successiva consiste nell'esaminare i modelli di traffico in uso e nel rispondere alle domande seguenti:

-   "Esistono delle subnet dedicate a tipi specifici di traffico (ad esempio, workstation Mac e UNIX o connessioni mainframe-terminal)?" oppure

-   "È necessario separare diversi tipi di traffico o il traffico di diverse ubicazioni?".

#### Active Directory

Dopo la rete, Active Directory è il secondo elemento in ordine di importanza sul quale raccogliere informazioni. È necessario comprendere l'architettura dell'insieme di strutture, incluse quelle del dominio e dell'unità organizzativa (UO), nonché la topologia del sito. Queste informazioni consentono di rilevare dove sono attualmente posizionati i computer e quale sarà l'impatto delle modifiche da apportare ad Active Directory per l'implementazione di IPsec. L'elenco seguente riporta le informazioni necessarie per completare questa parte del rilevamento.

-   **Numero di insiemi di strutture**. Poiché nelle implementazioni di Active Directory l'insieme di strutture rappresenta il confine della protezione, è necessario comprendere l'architettura di Active Directory, al fine di stabilire quali host devono essere isolati e in quali modalità attuare l'isolamento.

-   **Nomi e numero di domini**. L'autenticazione IPsec avviene come risultato del processo di negoziazione IKE. Nella presente soluzione, il metodo di autenticazione utilizzato è il protocollo Kerberos. Questo protocollo presuppone che i computer siano uniti al dominio e che rispondano ai requisiti relativi al sistema operativo (Windows 2000, Windows XP o Windows Server 2003).

-   **Numero e tipi di relazioni di trust**. L'acquisizione di informazioni relative al numero e ai tipi di relazioni di trust è importante perché esse modificano i confini logici dell'isolamento e inoltre definiscono come avviene (o come dovrebbe avvenire) l'autenticazione IKE all'interno della soluzione.

-   **Nomi e numero di siti**. L'architettura del sito è solitamente allineata alla topologia della rete. Comprendendo come sono specificati i siti in Active Directory, è possibile approfondire i processi di replica e altri dettagli. Per questa soluzione, l'architettura del sito fornisce informazioni approfondite sull'implementazione di Active Directory allo stato attuale.

-   **Struttura della UO**. Effettuando una pianificazione di massima in fase di creazione della struttura di una UO, è possibile incrementare sensibilmente l'efficienza operativa. Le UO sono costrutti logici che possono essere plasmati in modo da soddisfare numerosi requisiti ed esigenze. La struttura della UO è il punto ideale per esaminare le modalità d'uso dei criteri di gruppo e la configurazione delle UO. I capitoli 4 e 5 della presente guida illustrano l'architettura delle UO e forniscono dettagli su come è possibile utilizzarla per applicare i criteri IPsec.

-   **Attuale utilizzo dei criteri IPsec**. Poiché questo processo culmina con l'implementazione dei criteri IPsec, è molto importante comprendere come la rete utilizza IPsec allo stato attuale (se lo utilizza). Sia che si utilizzino semplici filtri IPsec (quali quelli riportati in una guida per il rafforzamento della protezione) o che si implementino criteri completi, la comprensione dell'utilizzo corrente e dei requisiti garantirà una più semplice integrazione con questa soluzione.

Lo scenario della Woodgrove Bank utilizza un solo insieme di strutture (corp.woodgrovebank.com), che contiene quattro domini distribuiti fra cinque siti. Ciascun sito può contenere un controller di dominio (DC), un controller di dominio primario (PDC) o un server del catalogo globale (GC), come riportato nella tabella seguente:

**Tabella 3.1. Informazioni su Active Directory della Woodgrove Bank**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Sito fisico</p></th>
<th><p>Dominio</p></th>
<th><p>Utenti</p></th>
<th><p>Tipo di controller di dominio</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>New York, NY</p></td>
<td style="border:1px solid black;"><p>corp.woodgrovebank.com<br />
americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>5.000</p></td>
<td style="border:1px solid black;"><p>Catalogo globale dell'insieme di strutture principale<br />
PDC<br />
GC continentale - Americhe<br />
DC continentale - Europa<br />
DC continentale - Asia</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Chicago, IL</p></td>
<td style="border:1px solid black;"><p>americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>750</p></td>
<td style="border:1px solid black;"><p>GC continentale - Americhe</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Atlanta, GA</p></td>
<td style="border:1px solid black;"><p>americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>1.450</p></td>
<td style="border:1px solid black;"><p>GC continentale - Americhe</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Boston, MA</p></td>
<td style="border:1px solid black;"><p>americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>480</p></td>
<td style="border:1px solid black;"><p>GC continentale - Americhe</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>San Francisco, CA</p></td>
<td style="border:1px solid black;"><p>americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>250</p></td>
<td style="border:1px solid black;"><p>GC continentale - Americhe</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Pittsburgh, PA</p></td>
<td style="border:1px solid black;"><p>americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>50</p></td>
<td style="border:1px solid black;"><p>GC continentale - Americhe</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Phoenix, AZ</p></td>
<td style="border:1px solid black;"><p>americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>50</p></td>
<td style="border:1px solid black;"><p>GC continentale - Americhe</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Miami, FL</p></td>
<td style="border:1px solid black;"><p>americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>50</p></td>
<td style="border:1px solid black;"><p>GC continentale - Americhe</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Washington, DC</p></td>
<td style="border:1px solid black;"><p>americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>75</p></td>
<td style="border:1px solid black;"><p>GC continentale - Americhe</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Cambridge, MA</p></td>
<td style="border:1px solid black;"><p>americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>36</p></td>
<td style="border:1px solid black;"><p>GC continentale - Americhe</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Toronto, Canada</p></td>
<td style="border:1px solid black;"><p>americas.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>25</p></td>
<td style="border:1px solid black;"><p>GC continentale - Americhe</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Londra, Regno Unito</p></td>
<td style="border:1px solid black;"><p>europe.corp.woodgrovebank.com<br />
corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>5.200</p></td>
<td style="border:1px solid black;"><p>GC insieme di strutture principale<br />
Emulatore PDC<br />
GC Europa<br />
DC continentale - Americhe<br />
DC continentale - Asia</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Ginevra, Svizzera</p></td>
<td style="border:1px solid black;"><p>europe.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>350</p></td>
<td style="border:1px solid black;"><p>GC Europa</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Amsterdam, Paesi Bassi</p></td>
<td style="border:1px solid black;"><p>europe.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>295</p></td>
<td style="border:1px solid black;"><p>GC Europa</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Monaco, Germania</p></td>
<td style="border:1px solid black;"><p>europe.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>149</p></td>
<td style="border:1px solid black;"><p>GC Europa</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Roma, Italia</p></td>
<td style="border:1px solid black;"><p>europe.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>80</p></td>
<td style="border:1px solid black;"><p>GC Europa</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Dublino, Irlanda</p></td>
<td style="border:1px solid black;"><p>europe.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>79</p></td>
<td style="border:1px solid black;"><p>GC Europa</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Edimburgo, Scozia</p></td>
<td style="border:1px solid black;"><p>europe.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>40</p></td>
<td style="border:1px solid black;"><p>GC Europa</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Johannesburg, Sud Africa</p></td>
<td style="border:1px solid black;"><p>europe.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>37</p></td>
<td style="border:1px solid black;"><p>GC Europa</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Tokyo, Giappone</p></td>
<td style="border:1px solid black;"><p>asia.corp.woodgrovebank.com<br />
corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>500</p></td>
<td style="border:1px solid black;"><p>GC insieme di strutture principale<br />
Emulatore PDC<br />
GC continentale - Asia<br />
DC continentale - Europa<br />
DC continentale - Americhe</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Hong Kong, Cina</p></td>
<td style="border:1px solid black;"><p>asia.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>100</p></td>
<td style="border:1px solid black;"><p>GC continentale - Asia</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Bangkok, Thailandia</p></td>
<td style="border:1px solid black;"><p>asia.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>150</p></td>
<td style="border:1px solid black;"><p>GC continentale - Asia</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Singapore</p></td>
<td style="border:1px solid black;"><p>asia.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>210</p></td>
<td style="border:1px solid black;"><p>GC continentale - Asia</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Sydney, Australia</p></td>
<td style="border:1px solid black;"><p>asia.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>45</p></td>
<td style="border:1px solid black;"><p>GC continentale - Asia</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Bangalore, India</p></td>
<td style="border:1px solid black;"><p>asia.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>35</p></td>
<td style="border:1px solid black;"><p>GC continentale - Asia</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Taipei, Taiwan</p></td>
<td style="border:1px solid black;"><p>asia.corp.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>65</p></td>
<td style="border:1px solid black;"><p>GC continentale - Asia</p></td>
</tr>
</tbody>
</table>
  
La configurazione di Active Directory della Woodgrove Bank utilizza le relazioni di trust bidirezionali che vengono create automaticamente dall'insieme di strutture. Non sono stati implementati altri insiemi di strutture supplementari o trust esterni.
  
La figura seguente illustra un esempio della struttura generale della UO utilizzata dalla Woodgrove Bank. Questa struttura è stata coerentemente utilizzata per tutti i tre principali domini continentali: *Americhe*, *Europa* e *Asia*.
  
[![](images/Dd536206.SGFG0302(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536206.sgfg0302_big(it-it,technet.10).gif)
  
**Figura 3.2. Esempio di struttura della UO della Woodgrove Bank**
  
Poiché il progetto di isolamento del server e del dominio era la prima implementazione di IPsec per la Woodgrove Bank, non esisteva alcun criterio IPsec.
  
#### Rilevamento degli host
  
Il vantaggio principale derivante da un progetto di rilevamento delle risorse è rappresentato dalla grande quantità di dati che è possibile ottenere sugli host (workstation e server) presenti sulla rete. Il processo illustrato nel capitolo 4 "Progettazione e pianificazione dei gruppi di isolamento" include decisioni che devono essere basate su informazioni precise riguardo allo stato di tutti gli host, al fine di garantire la loro idoneità a partecipare alle comunicazioni IPsec.
  
##### Dati sugli host
  
Questa sezione descrive le informazioni necessarie sugli host e illustra come rappresentarle sia dal punto di vista fisico che logico.
  
-   **Nome del computer**. Si tratta del nome NetBIOS o DNS del computer che identifica il computer sulla rete. Visto che un computer può disporre di più indirizzi MAC (Media Access Control) e/o IP, il nome del computer è uno dei criteri che è possibile utilizzare per definirne l'univocità sulla rete. I nomi dei computer potrebbero essere duplicati in alcune circostanze e quindi l'univocità non deve essere considerata assoluta.
  
-   **Indirizzi IP per ciascuna scheda di interfaccia di rete (NIC, Network Interface Card)**. L'indirizzo IP è l'indirizzo utilizzato insieme alla subnet mask per identificare un host sulla rete. Si noti che l'indirizzo IP non costituisce un metodo efficace per identificare una risorsa, perché è spesso soggetto a modifiche.
  
-   **Indirizzo MAC per ciascuna NIC**. L'indirizzo MAC è un indirizzo univoco a 48 bit che viene utilizzato per identificare un'interfaccia di rete. Può essere utile per differenziare le diverse interfacce di rete della medesima periferica.
  
-   **Versioni di sistema operativo, service pack e aggiornamenti rapidi**. La versione del sistema operativo è un fattore chiave per stabilire se un host è in grado di comunicare tramite IPsec. È inoltre importante rilevare lo stato corrente dei service pack e degli aggiornamenti rapidi installati, perché questi dati consentono di stabilire gli standard di protezione minimi implementati.
  
-   **Appartenenza al dominio**. Questa informazione è utile per stabilire se un computer è in grado di acquisire un criterio IPsec da Active Directory o se dovrà invece utilizzare un criterio IPsec locale.
  
-   **Posizione fisica**. Questa informazione indica semplicemente la posizione della periferica nell'organizzazione. Può essere utilizzata per stabilire se una periferica deve partecipare a uno specifico gruppo di isolamento in base alla sua posizione o alla posizione delle periferiche con cui comunica.
  
-   **Tipo/Funzione dell'hardware**. Potrebbe non essere possibile reperire questa informazione tramite un processo automatico. Alcuni strumenti che eseguono il rilevamento degli host sono in grado di acquisire questa informazione eseguendo delle query a livello hardware e avviando delle applicazioni, al fine di stabilirne il tipo (ad esempio server, workstation o tablet PC). Queste informazioni possono essere utilizzate per stabilire se un computer specifico può partecipare all'isolamento e in quale gruppo di isolamento deve essere inserito.
  
    **Nota:** le informazioni sul tipo di hardware vengono ottenute tramite interpolazione dei dati o mediante un software che esegue query per reperire queste informazioni. Considerando, ad esempio, il computer mobile HP Evo n800, se è possibile eseguire una query a livello di hardware (o se si dispone di un numero di serie che lo identifichi come tale), si potrà stabilire più rapidamente il criterio IPsec da assegnare a questa periferica.
  
Dopo aver raccolto tutte queste informazioni e averle consolidate in un database, è necessario eseguire delle attività di rilevamento a intervalli regolari, affinché esse rimangano aggiornate. Per creare una configurazione che soddisfi i requisiti della propria organizzazione, è necessario poter contare su un quadro il più possibile completo e aggiornato degli host gestiti.
  
L'acquisizione dei dati dagli host presenti sulla rete può avvenire ricorrendo a vari metodi, che vanno dai sistemi di fascia alta completamente automatici alla raccolta interamente manuale. In generale, è preferibile utilizzare metodi automatici per ragioni di rapidità e precisione. Nonostante ciò, le informazioni da acquisire sono le medesime, indipendentemente dal metodo che si utilizza; varierà, infatti, soltanto il tempo necessario per completare la raccolta delle informazioni. I problemi tipici dei processi manuali includono quelli di duplicazione delle informazioni, di precisa definizione dell'ambito di lavoro (ad esempio, l'analisi di tutte le reti e la raccolta di informazioni di tutti gli host o soltanto delle subnet dei client) e di tempestività dei processi in funzione della tempistica del progetto. La trattazione di tutti gli elementi che rientrano in un'analisi completa dei sistemi IT non rientra nell'ambito di questo progetto. È tuttavia importante comprendere che le informazioni derivanti dall'analisi devono essere disponibili all'interno dell'organizzazione per varie ragioni, che vanno oltre le esigenze di questa soluzione. La catalogazione delle risorse e la gestione dei rischi di protezione sono soltanto due importanti esempi dei processi che richiedono un inventario accurato e aggiornato dei sistemi.
  
##### Rilevamento automatico
  
L'utilizzo di un sistema di gestione automatico del controllo della rete, quale SMS, consentirà di ottenere numerose informazioni utili sullo stato corrente dell'infrastruttura IT. D'altro canto, uno dei problemi dei sistemi automatici consiste nel fatto che gli host non in linea, disconnessi o in altro modo fisicamente o logicamente non in grado di rispondere alle query di richiesta di informazioni, non verranno inseriti nel database finale. Anche i sistemi con il più elevato grado di automatizzazione richiedono quindi un intervento manuale, che garantisca che gli host siano accessibili e vengano analizzati.
  
I prodotti e gli strumenti offerti da vari fornitori sono numerosi. Alcuni metodi utilizzano un meccanismo centralizzato di analisi, mentre altri installano degli agenti sui computer client. Non rientrano nell'ambito di trattazione di questa guida il confronto fra questi prodotti né i consigli di acquisto. La soluzione impone però che i dati rilevati indicati in questo capitolo siano disponibili, per valutare le possibilità di configurazione illustrate nei capitoli 4 e 5.
  
Per ulteriori informazioni su come utilizzare SMS 2003 al fine di facilitare la gestione delle risorse (o semplificare la raccolta delle informazioni necessarie per questo progetto), vedere la demo e la scheda tecnica riguardante la gestione delle risorse alla pagina [Gestione delle risorse con SMS 2003](http://www.microsoft.com/smserver/evaluation/capabilities/asset.asp) all'indirizzo www.microsoft.com/italy/smserver/evaluation/capabilities/  
asset.asp.
  
##### Rilevamento manuale
  
La principale differenza fra i metodi di rilevamento manuale e quelli automatici è da ricercarsi nei tempi. Per raccogliere manualmente le informazioni necessarie per questo progetto, potrebbero essere necessarie varie decine di giornate/uomo o settimane, se non addirittura un tempo ancora superiore per le imprese di grandi dimensioni. Se si intende utilizzare un metodo manuale per verificare lo stato corrente dell'infrastruttura, è importante che le informazioni acquisite siano disponibili in formato elettronico, ad esempio in fogli di calcolo o database. L'elevatissimo volume di dati da acquisire potrebbe complicare notevolmente il processo di filtraggio e analisi, se non è possibile generare query specifiche che restituiscano le informazioni necessarie. Per ottenere le informazioni o convalidare quelle raccolte precedentemente, è inoltre possibile ricorrere al supporto degli amministratori IT.
  
Anche se l'organizzazione non dispone di uno strumento automatico di analisi, è comunque possibile implementare un certo grado di automatizzazione utilizzando la gestione remota standard e le interfacce di scripting incluse nella piattaforma Windows. L'aspetto fondamentale correlato all'utilizzo di questi strumenti consiste nell'accertarsi di non tralasciare alcun client semplicemente perché non compatibile con lo strumento o script di gestione.
  
Per creare un file di script che acquisisca le informazioni di configurazione di un sistema, è possibile utilizzare Windows Scripting Host (WSH), Microsoft Visual Basic® Scripting Edition (VBScript) e Strumentazione gestione Windows (WMI, Windows Management Instrumentation). La tabella seguente indica la disponibilità di VBScript e WMI per ciascuna piattaforma.
  
**Tabella 3.2. Disponibilità di VBScript e WMI per piattaforma**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Piattaforma</p></th>
<th><p>VBScript</p></th>
<th><p>WMI</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Windows 95</p></td>
<td style="border:1px solid black;"><p>Installare WSH 5.6</p></td>
<td style="border:1px solid black;"><p>Installare WMI CORE 1.5</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Windows 98</p></td>
<td style="border:1px solid black;"><p>Incorporato</p></td>
<td style="border:1px solid black;"><p>Installare WMI CORE 1.5</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Windows Millennium</p></td>
<td style="border:1px solid black;"><p>Incorporato</p></td>
<td style="border:1px solid black;"><p>Incorporato</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Microsoft Windows NT® versione 4.0</p></td>
<td style="border:1px solid black;"><p>Installare WSH 5.6</p></td>
<td style="border:1px solid black;"><p>Installare WMI CORE 1.5</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Windows 2000</p></td>
<td style="border:1px solid black;"><p>Incorporato</p></td>
<td style="border:1px solid black;"><p>Incorporato</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Windows XP</p></td>
<td style="border:1px solid black;"><p>Incorporato</p></td>
<td style="border:1px solid black;"><p>Incorporato</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
<td style="border:1px solid black;"><p>Incorporato</p></td>
<td style="border:1px solid black;"><p>Incorporato</p></td>
</tr>
</tbody>
</table>
  
**Nota:** è possibile scaricare l'aggiornamento di Microsoft Windows Script 5.6 dall'area di [download del sito Web Microsoft](http://www.microsoft.com/downloads/details.aspx?familyid=c717d943-7e4b-4622-86eb-95a22b832caa&displaylang=it) all'indirizzo http://msdn.microsoft.com/library/default.asp?url=/  
downloads/list/webdev.asp.  
È possibile scaricare il file di installazione di [Windows Management Instrumentation (WMI) CORE 1.5](http://www.microsoft.com/downloads/details.aspx?familyid=afe41f46-e213-4cbf-9c5b-fbf236e0e875&displaylang=it) dall'area di download del sito Web Microsoft all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyID=afe41f46-e213-4cbf-9c5b-fbf236e0e875&DisplayLang=it.
  
Nella cartella Strumenti e modelli della presente soluzione, è disponibile uno script VB di esempio denominato **Discovery.vbs**. Questo script utilizza WMI per recuperare tutte le informazioni elencate nella sezione "Dati sugli host" del presente capitolo, fatta eccezione per la funzione e la posizione fisica. Le informazioni vengono salvate in un file di testo denominato **C:\\Discovery\\&lt;*nomesistema*&gt;\_info.txt** sul computer locale. È possibile modificare lo script per acquisire informazioni aggiuntive o affinché le informazioni raccolte vengano posizionate in una condivisione file remota.
  
Se WMI o VBScript non sono disponibili sul computer host, è possibile acquisire alcune informazioni utilizzando uno script batch e strumenti esterni. La difficoltà è data dal fatto che il linguaggio batch dispone di funzionalità estremamente limitate, oltre al fatto che nelle prime versioni di Windows non è facile ottenere le informazioni sulla configurazione utilizzando la riga di comando.
  
Per effettuare un rilevamento degli host, è necessario eseguire query sugli host e indicare una posizione di archiviazione dei risultati di queste query.
  
Sia che si utilizzi un metodo automatico, manuale o ibrido per raccogliere le informazioni, gli aspetti principali che possono causare problemi in fase di progettazione sono quelli di acquisizione delle modifiche dal momento dell'analisi di inventario originaria a quello in cui l'implementazione sarà pronta per essere avviata. Dopo aver completato la prima analisi, si dovrà quindi informare tutto il personale di supporto che le eventuali successive modifiche dovranno essere registrate e aggiornate nell'inventario.
  
Questo inventario sarà molto importante per la pianificazione e l'implementazione dei criteri IPsec, che verranno trattate nei capitoli seguenti.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Considerazioni sulla capacità
  
Una volta conclusa la fase di raccolta delle informazioni, è necessario passare a quella di valutazione dell'impatto di IPsec (inclusa una pianificazione preliminare delle capacità). Questa sezione illustra alcuni degli aspetti essenziali per pianificare correttamente l'implementazione di IPsec in un ambiente.
  
#### Impatto di IPsec
  
Poiché IPsec utilizza varie tecniche di crittografia, può costituire un sovraccarico notevole per i computer. Gli scenari che dovranno essere analizzati più accuratamente sono quelli che richiedono la crittografia. Potrebbe, ad esempio, essere necessario utilizzare lo standard 3DES (Triple Data Encryption Standard) e l'algoritmo SHA-1 (Secure Hash Algorithm) per verificare l'integrità nelle situazioni che richiedono il livello massimo di crittografia disponibile e la protezione dello scambio di chiavi. Un altro possibile scenario riguarda invece le associazioni di protezione (SA, Security Association). Si potrebbe, ad esempio, utilizzare una durata inferiore per le SA in modalità principale (3 ore) ma, come spesso avviene in materia di protezione, è necessario accettare dei compromessi. Una SA in modalità principale occupa circa 5 KB di RAM e, in una situazione in cui il server deve mediare centinaia di migliaia di connessioni contemporanee, questa scelta potrebbe portare a un utilizzo eccessivo. Altri fattori includono l'utilizzo della CPU sui server d'infrastruttura della rete, un maggiore sovraccarico su server e workstation che eseguono IPsec (in particolare sui server, perché nella maggior parte dei casi su di essi risiede un maggior numero di SA stabilite in modalità principale) e un incremento della latenza di rete, derivante dalla negoziazione IPsec.
  
**Nota:** nella distribuzione di questa soluzione implementata da Microsoft, si è riscontrato che è normale prevedere un aumento dall'uno al tre percento dell'utilizzo sulla rete, come conseguenza diretta dell'implementazione di IPsec.
  
Un altro importante aspetto riguarda le reti connesse tramite periferiche NAT. Il problema risiede nel fatto che il NAT non consente comunicazioni AH (Authentication Header) fra gli host, perché questo servizio viola il principio di base di AH, vale a dire l'autenticazione di pacchetti non modificati, intestazione inclusa. Se sulla rete interna sono presenti delle periferiche NAT, sarà necessario selezionare ESP invece di AH. ESP rende disponibile la crittografia dei dati, che però non è obbligatoria. Questo fattore è importante dal punto di vista della capacità, perché la crittografia genera un sovraccarico che deve essere valutato nelle fasi di pianificazione e progettazione. ESP può essere implementato anche senza crittografia e consente quindi di ottenere la migliore comunicazione peer-to-peer possibile protetta da IPsec, senza però interrompere le comunicazioni con i servizi NAT. In questo caso, ci sarà anche un impatto minore rispetto a ESP con crittografia.
  
#### Impatto dei criteri
  
I criteri IPsec e i criteri di gruppo hanno un impatto sui tempi di avvio dei computer, nonché sui tempi necessari per l'accesso degli utenti. Nella fase di raccolta delle informazioni, è utile prendere nota dei tempi di avvio dei computer e di quelli di accesso degli utenti prima dell'implementazione della soluzione. Il rilevamento di questi tempi nella suddetta fase fornirà un punto di partenza per i confronti con i sistemi di test durante il progetto pilota, volti a determinare l'impatto sul tempo totale necessario a un utente per completare l'accesso.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Considerazioni pre-implementazione
  
Nelle sezioni precedenti, sono elencate le informazioni che è necessario acquisire dalla rete, da Active Directory e dagli host, per implementare con successo la soluzione di isolamento. Questa sezione elenca le aree da analizzare accuratamente prima di distribuire IPsec.
  
#### Infrastruttura di rete
  
L'acquisizione di informazioni consente di pianificare l'isolamento IPsec sulla rete. Dopo aver raccolto queste informazioni, è opportuno procedere con un'accurata analisi dei dati, che metterà in luce la maggior parte dei problemi che si dovranno affrontare durante il progetto pilota e la distribuzione. Nonostante gli elementi seguenti non costituiscano un elenco esauriente, è importante tenerli presente in fase di analisi delle informazioni acquisite e prima di eseguire test e distribuzioni.
  
##### Periferiche sovrautilizzate
  
Potrebbe essere necessario aggiornare o riconfigurare switch o router che superano il 75% di utilizzo, al fine di poter incrementare il traffico su queste periferiche e consentire un utilizzo extra per i picchi. La corretta pianificazione della capacità per l'implementazione di IPsec include essenzialmente test e previsioni dei carichi di traffico, piuttosto che calcoli esatti. Poiché è estremamente improbabile che lo scenario, i modelli di traffico, le concentrazioni di utenti e le applicazioni siano esattamente i medesimi per due diversi clienti, la corretta pianificazione e la valutazione degli impatti sulle periferiche di rete è imprescindibile. Alcuni aspetti di IPsec sono, ad esempio, totalmente prevedibili. Un pacchetto che utilizza IPsec con ESP sarà di esattamente 36 byte più grande rispetto al medesimo pacchetto che invece non utilizza IPsec. Inoltre, visto che i messaggi necessari per stabilire una SA in modalità principale sono sei, è facile valutare l'impatto sull'utilizzo per una periferica specifica. È possibile utilizzare strumenti quali PROVISO di (www.quallaby.com) o altre soluzioni per l'analisi della rete, che facilitano la pianificazione della capacità per IPsec nell'ambiente IT specifico.
  
##### Periferiche non compatibili
  
Le periferiche che non sono compatibili con IPsec non possono partecipare alle comunicazioni protette da questo servizio. Se queste periferiche devono comunicare con una periferica gestita, è necessario inserirle in un elenco di esenzioni IPsec. In alternativa, è possibile aggiornare l'hardware o il software, affinché le periferiche possano supportano IPsec. Un'altra possibile alternativa consiste nel consentire a queste periferiche non gestite di comunicare con i computer del gruppo Limite, quando essi passano alla modalità non crittografata per le comunicazioni in uscita.
  
##### Periferiche configurate in modo errato
  
Le periferiche configurate in modo errato possono incrementare le possibilità di problemi di comunicazione e aumentare il carico sulla periferica stessa, se non addirittura danneggiarla. Per ridurre queste possibilità, è opportuno attenersi alle procedure consigliate per la configurazione, amministrazione e protezione delle periferiche.
  
##### Indirizzamento IP
  
Gli indirizzi IP sono l'elemento di base di una soluzione IPsec ed è quindi essenziale che l'indirizzamento sia per quanto possibile "lineare". La sovrapposizione degli spazi degli indirizzi, la duplicazione degli indirizzi, le subnet mask errate e altri errori simili possono complicare il normale funzionamento della rete. L'integrazione di IPsec in questi tipi di reti renderà più complessi i processi di risoluzione dei problemi e farà sì che il personale consideri IPsec come l'origine dei problemi. La crescita dell'organizzazione, le fusioni, le acquisizioni e altri fattori possono in breve tempo rendere obsoleto e impreciso il quadro dell'indirizzamento IP sulla rete. Per evitare i problemi più gravi correlati a IPsec, accertarsi che la rete sia suddivisa in subnet che non si sovrappongono, che le tabelle di routing siano ordinatamente riepilogate e che sia facile stabilire l'aggregazione degli indirizzi.
  
#### Informazioni su Active Directory
  
Se l'implementazione corrente di Active Directory funziona adeguatamente (vale a dire risoluzione dei nomi, DHCP \[Dynamic Host Configuration Protocol\], applicazione di criteri di gruppo, relazioni di trust, ecc.), non dovrebbe interferire con IPsec. È necessario esaminare attentamente tutte le eventuali modifiche apportate dal momento in cui è stata completata l'analisi di Active Directory a quello in cui si avvia il progetto di isolamento, al fine di evitare problemi di compatibilità.
  
#### Informazioni sugli host
  
Le sezioni precedenti contengono istruzioni utili per acquisire informazioni sugli host della rete. Dopo aver stabilito quali client e server sono in grado di utilizzare IPsec, è necessario valutare come isolare queste periferiche e quali applicazioni devono essere analizzate accuratamente per prevedere l'impatto che la soluzione di isolamento avrà su di esse.
  
##### Partecipazione di client e server
  
Dopo aver raccolto le informazioni sugli host, è relativamente semplice stabilire quali host sono idonei per l'integrazione nella soluzione di isolamento. Ad esempio, solo i computer basati su Windows 2000, Windows Server 2003 e Windows XP possono comunicare utilizzando IPsec. D'altro canto, però, potrebbe non essere necessario integrare tutti i client idonei. Una parte importante del processo di progettazione consiste nello stabilire, in base alle informazioni riportate in questo capitolo, quali computer e periferiche devono essere inclusi nella soluzione e in quale gruppo.
  
##### Individuazione dei servizi che devono essere isolati
  
Nel contesto del progetto di isolamento del server e del dominio, un servizio è un'applicazione, quale Microsoft Exchange Server, Microsoft SQL Server™ o Internet Information Services (IIS), che fornisce i propri servizi a client presenti sulla rete. Sarebbe opportuno esaminare singolarmente questi servizi e stabilire se sono candidati adeguati per l'isolamento del server e del dominio. Le ragioni che possono giustificare un'inclusione di questi servizi nella soluzione sono numerose, fra le quali quelle di politica aziendale, quelle legate alle normative di governo o ad altre esigenze aziendali. Potrebbe, ad esempio, esistere una politica aziendale che stabilisce che tutte le comunicazioni fra i server di posta elettronica devono essere protette tramite IPsec, ma che le comunicazioni fra client e server non richiedono questo tipo di protezione. Il capitolo 4, "Progettazione e pianificazione dei gruppi di isolamento" illustra il processo di isolamento nei dettagli. Quando si deve procedere all'isolamento dei servizi, analizzare con attenzione i server che erogano vari servizi, quali ad esempio un file server che fornisce FTP (File Transfer Protocol) e servizi Web e che funge anche da server di posta.
  
##### Bilanciamento del carico di rete e clustering
  
Le organizzazioni che utilizzano l'isolamento del server e del dominio possono decidere di esentare i computer che utilizzano il bilanciamento del carico di rete (NLB, Network Load Balancing) e il clustering. IPsec non è compatibile con il bilanciamento del carico in "assenza di affinità", perché IPsec impedisce a computer diversi di utilizzare la medesima connessione client. A causa di questa incompatibilità, non utilizzare NLB con IPsec in assenza di affinità.
  
##### Gestione delle eccezioni
  
La gestione delle eccezioni è una parte importante della pianificazione di IPsec. Elemento cruciale dell'isolamento consiste infatti nello stabilire dove utilizzare computer che consentano l'accesso da host non attendibili e nel controllare gli accessi fra computer gestiti e non gestiti. In generale, è consigliabile ridurre al minimo il numero di eccezioni. Esigenze tecniche potrebbero imporre che alcuni computer e servizi vengano esentati da IPsec, quali ad esempio i controller di dominio e i server DHCP, DNS e WINS. Visto che questi computer saranno comunque gestiti, il rischio potenziale è inferiore rispetto a quello generato dalle comunicazioni fra computer non gestiti e computer gestiti e attendibili.
  
##### Periferiche non basate su Windows
  
La maggior parte delle reti aziendali non è omogenea. In fase di pianificazione della distribuzione di IPsec, è necessario considerare una vasta gamma di aspetti, quali i sistemi operativi, l'infrastruttura di rete e le piattaforme hardware. Se l'organizzazione utilizza computer non basati su Windows, è necessario considerare che attualmente i criteri IPsec non possono essere utilizzati al di fuori dell'area di autenticazione Windows. L'organizzazione potrebbe decidere di gestire questa limitazione considerando come attendibili alcune piattaforme, ma visto che esse non possono utilizzare i criteri IPsec, la soluzione di isolamento del server e del dominio non sarà in grado di proteggerle. La sezione seguente illustra come stabilire l'attendibilità.
  
##### Gestione e monitoraggio delle periferiche
  
Uno degli aspetti di IPsec che viene solitamente sottovalutato durante la fase iniziale di pianificazione è quello dell'impatto sulla gestione e sul monitoraggio del traffico di rete. Poiché IPsec richiede l'autenticazione e consente l'uso della crittografia, alcune periferiche non saranno più in grado di monitorare o gestire i computer su cui questo servizio è attivato. Nei casi in cui si decide di utilizzare la crittografia, si accetta implicitamente che la protezione è più importante delle esigenze operative di monitoraggio dei dati durante il transito sulla rete. In altri casi, sarà invece necessario valutare quali modifiche è possibile apportare ad applicazioni o periferiche per consentire il monitoraggio di IPsec (ad esempio, un parser ESP che possa monitorare il traffico ESP). Se non è possibile aggiornare le periferiche di monitoraggio o di gestione per il supporto di IPsec, è essenziale registrare questa informazione. L'architetto o il team di architetti della soluzione utilizzeranno queste informazioni nelle fasi illustrate nel capitolo 4 "Progettazione e pianificazione dei gruppi di isolamento".
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Determinazione dell'attendibilità
  
Dopo aver acquisito le informazioni sulle periferiche host dell'infrastruttura IT in uso, è necessario stabilirne l'idoneità a partecipare alla soluzione. Si tratta di una valutazione molto importante, che consiste nel definire quando un host può essere considerato attendibile. Il termine *attendibile* può assumere significati diversi ed è quindi necessario stabilire una definizione chiara per tutti coloro che partecipano al progetto. In assenza di una definizione chiara potrebbero insorgere dei problemi relativamente alla protezione dell'ambiente attendibile, perché la protezione generale non può superare il livello di protezione definito dal client meno protetto giudicato attendibile.
  
Per comprendere questo concetto, è opportuno fare ricorso ai quattro stati di base degli host in un'infrastruttura IT tipica. Questi stati sono (in ordine di rischio a partire da quello con livello di rischio più basso):
  
1.  Attendibile
  
2.  Idoneo
  
3.  Non attendibile/Noto
  
4.  Non attendibile/Non noto
  
La parte restante di questa sezione riporta le definizioni di questi stati e illustra come stabilire quali host dell'organizzazione rientrano in ognuno di essi.
  
#### Host attendibile
  
Quando un host viene classificato come attendibile, non significa che esso sia perfettamente protetto o invulnerabile. Fondamentalmente l'attendibilità implica che i rischi vengono gestiti. La responsabilità di questa gestione è a carico degli amministratori IT e degli utenti che sono responsabili della configurazione dell'host. Un host attendibile non gestito in modo appropriato potrebbe trasformarsi in un punto debole per tutta la soluzione.
  
Quando un host viene giudicato attendibile, altri host attendibili devono poter ragionevolmente presumere che questo host non avvierà azioni dannose. Gli host attendibili devono, ad esempio, presumere che altri host attendibili non eseguiranno virus che possano attaccarli, poiché tutti gli host attendibili utilizzano per definizione meccanismi (quali ad esempio software antivirus) che riducono il rischio di minacce virali.
  
La comunicazione fra gli host attendibili non deve essere ostacolata dall'infrastruttura di rete. Visto che un host attendibile può, ad esempio, presumere che altri host attendibili non abbiano intenzioni dannose, il blocco dei pacchetti a livello IP per limitare l'accesso ad altri host attendibili non è generalmente necessario. Si dovranno implementare tutte le limitazioni necessarie per controllare le comunicazioni fra gli host tramite porte o protocolli, utilizzando un firewall basato su host installato sul computer stesso, ma non tramite IPsec.
  
Nello scenario della Woodgrove Bank, il team di protezione ha definito i seguenti cinque obiettivi chiave, che sono stati utilizzati per stabilire quali tecnologie implementare sugli host per acquisire lo stato di attendibilità:
  
-   L'identità del computer o dell'utente non è stata compromessa.
  
-   Le risorse necessarie sono protette e disponibili, indipendentemente dalla posizione in cui risiedono nell'ambiente gestito.
  
    -   Una risorsa si definisce *protetta* quando non può essere alterata, è priva di virus e non è accessibile senza autorizzazione.
  
    -   Una risorsa si definisce *disponibile* quando assicura i tempi di attività previsti e non presenta punti vulnerabili per quanto concerne la protezione.
  
    -   Un ambiente si definisce *gestito* quando i computer che lo costituiscono eseguono Windows 2000 SP4 o versioni successive, quando le patch necessarie sono installate e la configurazione è corretta.
  
-   I dati e le comunicazioni sono privati, vale a dire che le informazioni vengono lette e utilizzate soltanto dai rispettivi destinatari.
  
-   Il proprietario/operatore della periferica conosce e rispetterà le procedure che assicurano il mantenimento di un ambiente attendibile.
  
-   La risposta a rischi e minacce è tempestiva.
  
Il team di supporto della Woodgrove Bank ha utilizzato questi obiettivi per definire una serie di requisiti tecnologici, volti a stabilire se un host poteva essere considerato attendibile.
  
Quando si definisce lo stato di attendibilità, accertarsi che i proprietari della risorsa siano liberi di imporre requisiti di protezione aggiuntivi che rispondano alle esigenze aziendali della risorsa specifica. Il reparto delle risorse umane potrebbe, ad esempio, necessitare di un meccanismo di accesso biometrico per server specifici. Questa esigenza non avrà alcun impatto sull'attendibilità dei server nel contesto della presente soluzione. Si dovrà però verificare che i requisiti di una risorsa specifica non entrino in conflitto con quelli dello status di attendibilità.
  
È opportuno dedicare tempo alla definizione degli obiettivi e dei requisiti tecnologici che l'organizzazione considera adeguati come configurazione minima per giudicare attendibile un host.
  
Nello scenario della Woodgrove Bank, il team di progettazione ha utilizzato l'elenco seguente di requisiti tecnologici:
  
-   **Sistema operativo**. Un host attendibile deve eseguire Windows XP SP2 o Windows Server 2003 oppure, come requisito minimo, Windows 2000 SP4.
  
-   **Appartenenza al dominio**. Un host attendibile deve appartenere a un dominio gestito, vale a dire che il reparto IT dovrà disporre dei diritti di gestione della protezione.
  
-   **Client di gestione**. Tutti gli host attendibili devono eseguire un client specifico di gestione della rete, che consenta la gestione centralizzata e il controllo dei criteri di protezione, delle configurazioni e del software.
  
-   **Software antivirus**. Tutti i client affidabili devono eseguire un software antivirus configurato per controllare e aggiornare automaticamente i più recenti file di firma su base quotidiana.
  
-   **File system**. Tutti gli host attendibili dovranno essere dotati di file system NTFS.
  
-   **Impostazioni BIOS**. Tutti i computer mobili devono essere configurati con una password a livello di BIOS, gestita dal team di supporto IT.
  
-   **Requisiti delle password**. I client attendibili devono utilizzare password avanzate.  
  
È essenziale comprendere che lo stato di attendibilità non è costante; si tratta di una condizione transitoria soggetta a standard di protezione variabili e alla conformità a questi standard. Si presentano infatti sempre nuove minacce e nascono nuove difese. Per questa ragione è essenziale che i sistemi di gestione dell'organizzazione verifichino costantemente gli host attendibili, per accertarne la compatibilità. Inoltre, questi sistemi devono essere in grado di rilasciare aggiornamenti o modifiche di configurazione, quando necessario per consentire all'host di rimanere attendibile.
  
Un host che soddisfa sempre tutti questi requisiti di protezione può essere considerato attendibile. È tuttavia molto probabile che la maggior parte dei computer host, identificati durante il processo di rilevamento precedentemente illustrato in questo capitolo, non sia conforme a questi requisiti. È quindi importante individuare quali host possono diventare attendibili e quali invece dovranno essere considerati non attendibili. Per facilitare questo processo è possibile creare uno stato di idoneità intermedio. La parte restante di questa sezione illustra i tre diversi stati e le relative implicazioni.
  
#### Host idoneo
  
È utile individuare il più rapidamente possibile gli host dell'infrastruttura corrente che, se necessario, possono acquisire lo stato di attendibilità. Lo stato di idoneità può essere assegnato per indicare che l'host non è attualmente in grado, dal punto di vista fisico, di acquisire lo stato di attendibilità e richiede modifiche a livello di configurazione e software.
  
Per tutti i computer a cui viene assegnato lo stato di idoneità, sarà necessario aggiungere una nota accompagnatoria di configurazione che indichi i requisiti necessari perché l'host possa acquisire lo stato di attendibilità. Queste informazioni sono particolarmente importanti sia per il team di progettazione (per stimare i costi di inserimento dell'host nella soluzione) che per il personale di supporto (per consentire loro di applicare la configurazione prevista). In generale, gli host idonei rientrano in uno dei due gruppi seguenti:
  
-   **Configurazione necessaria**. Hardware, sistema operativo e software in uso consentono il raggiungimento dell'attendibilità dell'host. Sono tuttavia necessarie modifiche aggiuntive della configurazione, per poter garantire la conformità ai livelli di protezione richiesti. Se, ad esempio, l'organizzazione richiede l'utilizzo di un file system protetto per giudicare un host attendibile, gli host con un disco rigido FAT32 non soddisferanno questo requisito.
  
-   **Aggiornamento necessario**. Questo gruppo di computer richiede aggiornamenti del sistema per poter essere considerato attendibile. Di seguito vengono elencati alcuni esempi di tipi di aggiornamento per i computer di questo gruppo:
  
    -   Aggiornamento del sistema operativo. Se il sistema operativo installato sull'host non supporta i requisiti di protezione dell'organizzazione, sarà necessario eseguire l'aggiornamento affinché l'host possa essere considerato attendibile.
  
    -   Software. Un host non dotato di un'applicazione di protezione, quale ad esempio un programma di scansione antivirus o un client di gestione, non può essere considerato attendibile fino a quando non si procede a installare e attivare queste applicazioni.
  
    -   Aggiornamento hardware. In alcuni casi, potrebbe essere necessario eseguire un aggiornamento hardware specifico, per rendere l'host attendibile. Questo tipo di host solitamente necessita di un aggiornamento del sistema operativo o di software aggiuntivo che imponga il necessario aggiornamento hardware, ad esempio, un software di protezione che richiede spazio di memorizzazione aggiuntivo sul computer e quindi impone l'installazione di un disco rigido di capacità superiore.
  
    -   Sostituzione del computer. Questa categoria è riservata agli host che non sono in grado di supportare i requisiti di protezione della soluzione, perché il loro hardware non supporta la configurazione minima accettabile. Potrebbe trattarsi, ad esempio, di un computer che non consente di installare un sistema operativo protetto a causa di un processore obsoleto (ad esempio x86 a 100 MHz).
  
Questi gruppi consentono di stimare i costi di implementazione della soluzione sui computer che richiedono aggiornamenti.
  
#### Non attendibile/Noto
  
Durante il processo di categorizzazione degli host dell'organizzazione, è possibile che vengano individuati host che non possono diventare attendibili per una serie di ragioni chiare e ben definite. Queste ragioni possono essere suddivise nei seguenti tipi:
  
-   **Finanziarie**. Non sono disponibili i fondi necessari per aggiornare l'hardware o il software dell'host.
  
-   **Politiche**. L'host potrebbe dover rimanere non attendibile a causa di una condizione politica o aziendale che non consente di renderlo conforme ai requisiti minimi di protezione dell'organizzazione. Si consiglia di contattare il titolare dell'azienda o il fornitore di software indipendente (ISV) in merito all'host, al fine di discutere il valore aggiunto dell'isolamento del server e del dominio.
  
-   **Funzionali**. Host che, per svolgere il loro ruolo, devono eseguire un sistema operativo non protetto od operare in modo non protetto. Questi host potrebbero, ad esempio, eseguire un sistema operativo meno recente perché un'applicazione aziendale specifica funziona soltanto su questo sistema operativo.
  
Potrebbero esistere numerose ragioni funzionali che obbligano a mantenere lo stato di non attendibilità nota dell'host. L'elenco seguente include alcuni esempi di ragioni funzionali che possono giustificare questa classificazione:
  
-   **Computer con sistema operativo Windows 9*x*** **o Windows Millennium Edition**. I computer che eseguono queste specifiche versioni del sistema operativo Windows non possono essere classificati come attendibili, perché questi sistemi operativi non supportano un'infrastruttura di protezione di base. In effetti, questi sistemi operativi non includono alcuna infrastruttura di protezione. Inoltre, dispongono di funzionalità rudimentali di gestione centralizzata delle configurazioni di utenti e computer (tramite criteri di sistema e script di accesso degli utenti). Infine, questi sistemi operativi non offrono le necessarie funzionalità di gestione della protezione.
  
-   **Computer che eseguono Windows NT**. I computer che eseguono Windows NT non possono essere classificati come attendibili nel contesto dell'isolamento del server e del dominio perché questo sistema operativo non supporta un'infrastruttura di protezione di base. Windows NT non supporta, ad esempio, gli ACL di negazione sulle risorse locali, i metodi che proteggono la confidenzialità e l'integrità delle comunicazioni, le smart card per l'autenticazione avanzata o la gestione centralizzata delle configurazioni dei computer (nonostante sia supportata una limitata gestione centralizzata delle configurazioni utente). Windows NT, inoltre, non offre un metodo per proteggere la confidenzialità dei dati e per assicurarne l'integrità (come Encrypting File System di Windows 2000).
  
    Windows NT non supporta neanche tutte le funzionalità di protezione necessarie. Non supporta, ad esempio, i criteri di gruppo né i criteri IPsec e non offre alcun meccanismo che assicuri la possibilità di ottenere l'accesso al livello di amministratore locale. Inoltre, le configurazioni di protezione non vengono riapplicate a intervalli regolari per assicurare che rimangano attive.
  
    **Nota:** la definizione di Windows NT come non idoneo riguarda esclusivamente l'implementazione dell'isolamento del server e del dominio e non si riferisce al suo utilizzo come sistema operativo in genere. Per i server inclusi in questo progetto, l'aggiornamento a Windows Server 2003 rappresenta la soluzione più protetta e gestibile.
  
-   **Computer autonomi**. I computer che eseguono una versione qualsiasi di Windows e che sono configurati come autonomi o come membri di un gruppo di lavoro solitamente non possono acquisire lo stato di idoneità. Anche se i loro sistemi operativi possono supportare tutta l'infrastruttura di protezione minima, le funzionalità di gestione della protezione sono difficili da acquisire, se il computer non rientra in un dominio attendibile.
  
-   **Computer di domini non attendibili**. Un computer membro di un dominio giudicato non attendibile dal reparto IT di un'organizzazione non può essere classificato come attendibile. Un dominio attendibile è un dominio che non può garantire ai propri membri le necessarie funzionalità di protezione. Anche se i sistemi operativi dei computer che sono membri di un dominio non attendibile possono supportare l'infrastruttura di protezione minima, le necessarie funzionalità di gestione della protezione non possono essere completamente garantite, quando i computer non sono membri di un dominio attendibile. In un dominio non attendibile, non sono, ad esempio, disponibili meccanismi che consentano l'accesso al livello di amministratore locale da parte di un utente attendibile. Inoltre, gli amministratori del dominio non attendibile possono facilmente disattivare le configurazioni di protezione (anche quelle che possono essere gestite centralmente). Infine, la conformità a configurazioni, software, criteri e standard di protezione non può essere garantita e non sono disponibili misure per monitorare efficacemente questa conformità.
  
-   **Computer di domini Windows NT**. I computer membri di un dominio basato su Windows NT non possono essere classificati come attendibili. Anche se i loro sistemi operativi possono supportare tutta l'infrastruttura di protezione minima, le necessarie funzionalità di gestione della protezione non sono pienamente supportate, quando i computer fanno parte di un dominio Windows NT.
  
    Tuttavia, se l'host deve rientrare nella configurazione, poiché svolge una funzione necessaria per l'organizzazione, si dovrà classificarlo come "Non attendibile/Noto". Ciò sta a indicare che è stato individuato un rischio che la soluzione non è in grado di attenuare. Per ridurre i rischi di questa minaccia nota, è necessario utilizzare tecniche supplementari. Vista la svariata natura degli host che rientrano in questa categoria, non è possibile fornire istruzioni specifiche su queste tecniche. Lo scopo di queste tecniche di contenimento deve in ogni caso essere quello di ridurre al minimo i rischi generati dagli host.  
  
#### Non attendibile/Non noto
  
Questo stato deve essere considerato come quello predefinito di tutti gli host. Poiché la configurazione degli host a cui viene assegnato questo stato non è nota, non è possibile valutarne l'attendibilità. Tutta la pianificazione relativa agli host a cui viene assegnato questo stato deve presupporre che l'host sia stato o possa essere compromesso e rappresenti quindi un rischio non accettabile per l'organizzazione. I progettisti della soluzione devono fare tutto quanto possibile per ridurre al minimo l'impatto che possono avere sull'organizzazione i computer a cui viene assegnato questo stato.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Acquisizione dei costi di aggiornamento degli host
  
La fase finale illustrata nel presente capitolo riguarda il processo di registrazione del costo approssimativo stimato per l'aggiornamento dei computer, affinché essi possano essere inseriti nella soluzione. Durante la fase di progettazione di questa soluzione, è necessario adottare numerose decisioni chiave, che devono essere basate sulle risposte alle domande seguenti:
  
-   "Il computer presenta i requisiti hardware minimi necessari per l'isolamento?",
  
-   "Il computer presenta i requisiti software minimi necessari per l'isolamento?",
  
-   "Quali modifiche di configurazione devono essere apportate per integrare questo computer nella soluzione di isolamento?" oppure
  
-   "Qual è il costo del progetto o l'impatto delle modifiche proposte per poter assegnare al computer lo stato di attendibilità?"
  
Rispondendo a queste domande, è possibile stabilire rapidamente il grado di impegno e il costo approssimativo da sostenere per inserire un host o un gruppo di host specifici nel progetto. È alquanto improbabile che una sola persona (o diverse persone che svolgono il medesimo ruolo) possano raccogliere tutti questi dati. Alcuni di essi possono essere acquisiti dal personale dell'help desk o dai tecnici di supporto, ma per gli altri sarà necessario un intervento a livello di architetti o dirigenti che sostengono l'iniziativa. È importante ricordare che lo stato di un computer è transitorio e che, implementando le azioni correttive elencate, è possibile modificare lo stato, trasformandolo da non attendibile ad attendibile. Dopo aver deciso se un computer deve essere reso attendibile, è possibile passare alla fase di pianificazione e progettazione dei gruppi di isolamento, illustrata nel capitolo 4, "Progettazione e pianificazione dei gruppi di isolamento", della presente guida.
  
La tabella seguente riporta alcuni dati di esempio e può essere utilizzata per facilitare la raccolta delle informazioni sullo stato corrente di un host e sugli elementi necessari per trasformarne lo stato in attendibile.
  
**Tabella 3.3. Esempi di dati relativi agli host**
  
<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome host</p></th>
<th><p>Requisiti hardware soddisfatti</p></th>
<th><p>Requisiti software soddisfatti</p></th>
<th><p>Configurazione necessaria</p></th>
<th><p>Dettagli</p></th>
<th><p>Costo previsto</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>HOST-NYC-001</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Aggiornare hardware e software.</p></td>
<td style="border:1px solid black;"><p>Il sistema operativo corrente è Windows NT 4.0. Hardware precedente non compatibile con Windows XP SP2.</p></td>
<td style="border:1px solid black;"><p>€<em>XXX</em>.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>SERVER-LON-001</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Unire a dominio attendibile e aggiornare da Windows NT 4.0 a Windows 2000 SP4 (o versioni successive).</p></td>
<td style="border:1px solid black;"><p>Software antivirus assente.</p></td>
<td style="border:1px solid black;"><p>€<em>XXX</em>.</p></td>
</tr>
</tbody>
</table>
  
L'elenco seguente descrive le colonne della tabella 3.3:
  
**Nome host**. Nome della periferica host sulla rete.
  
-   **Requisiti hardware soddisfatti**. Indica se un computer soddisfa i requisiti hardware minimi necessari per essere inserito nella soluzione.
  
-   **Requisiti software soddisfatti**. Indica se un computer soddisfa i requisiti software minimi necessari per essere inserito nella soluzione. Per la Woodgrove Bank, il requisito minimo era Windows 2000 SP4, Windows XP SP2 o Windows Server 2003, con tutte le patch di protezione critiche per ciascun sistema operativo. Inoltre, i computer dovevano essere membri di un dominio attendibile (vale a dire, un dominio gestito centralmente dal personale IT della Woodgrove Bank) e dovevano specificatamente consentire agli amministratori IT di accedere ad essi.
  
-   **Configurazione necessaria**. Indica quali azioni devono essere effettuate affinché il computer possa essere giudicato attendibile.
  
-   **Dettagli**. Descrive perché al computer non può essere attualmente assegnato lo stato di attendibilità.
  
-   **Costo del progetto**. Indica il costo stimato per rendere attendibile la periferica. Questo costo deve includere le stime relative a software, hardware, riduzione della produttività e supporto. Queste informazioni saranno utili per stabilire se è opportuno e fattibile, dal punto di vista aziendale, inserire un computer specifico nella soluzione come computer attendibile.
  
Nella tabella precedente, all'host HOST-NYC-001 è stato assegnato lo stato "Non attendibile/Noto". Può però essere considerato idoneo, se è possibile eseguire gli aggiornamenti necessari. Tuttavia, nel caso in cui un numero elevato di computer richieda lo stesso tipo di aggiornamento, il costo totale della soluzione sarà notevolmente superiore.
  
L'host SERVER-LON-001 soddisfa i requisiti hardware, ma deve essere aggiornato con un sistema operativo in grado di utilizzare i criteri IPsec ed essere unito a un dominio. È inoltre necessario installare un software antivirus. Il costo stimato indica il livello di impegno necessario per aggiornare il sistema operativo e installare un software antivirus, unito al costo delle licenze del sistema operativo e del software antivirus.
  
Dopo aver acquisito le informazioni riportate nella tabella 3.3, è necessario salvarle con le altre informazioni elencate in questo capitolo, affinché l'architetto o il team di architetti le possano utilizzare. Queste informazioni rappresentano il punto di partenza essenziale per le attività illustrate nel capitolo 4, che tratta la progettazione dei gruppi di isolamento.
  
Si noti che i costi indicati in questa sezione si riferiscono soltanto al costo stimato per l'aggiornamento degli host. Esistono altri costi aggiuntivi, che dovranno essere calcolati per questo progetto, quali quelli di progettazione, supporto, test e formazione. Se è necessario stimare un costo preciso, questi costi supplementari dovranno essere considerati nel piano generale del progetto.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questo capitolo include una panoramica delle informazioni necessarie per elaborare un progetto di isolamento del server e del dominio, incluse le considerazioni sul suo impatto. È possibile utilizzare le istruzioni fornite nel presente capitolo per completare le seguenti attività:
  
-   Identificazione delle risorse di rete
  
-   Acquisizione di informazioni sulla rete
  
-   Acquisizione di informazioni sugli host
  
-   Acquisizione di informazioni aggiornate sul traffico
  
-   Analisi dell'architettura di Active Directory in uso e acquisizione dal servizio stesso di informazioni pertinenti
  
-   Analisi delle considerazioni sulla capacità per IPsec
  
-   Analisi delle considerazioni pre-implementazione per IPsec
  
-   Descrizione delle periferiche attendibili e non attendibili e delle relative modalità di classificazione nello scenario della Woodgrove Bank
  
Completando queste attività, si acquisiranno tutte le informazioni necessarie per avviare la progettazione del gruppo di isolamento, illustrata nel capitolo seguente.
  
#### Ulteriori informazioni
  
Questa sezione contiene collegamenti alle aree in cui sono disponibili ulteriori informazioni che potrebbero essere utili per implementare questa soluzione:
  
-   Per ulteriori informazioni sulla configurazione dei firewall per il supporto di IPsec in Windows Server 2003, consultare la pagina [Configuring Firewalls](http://technet.microsoft.com/en-us/library/cc779912.aspx) della documentazione relativa a Windows Server 2003, all'indirizzo www.microsoft.com/resources/documentation/  
    WindowsServ/2003/all/deployguide/en-us/  
    dnsbj\_ips\_schx.asp.
  
-   È possibile scaricare il pacchetto di installazione di [Windows Management Instrumentation (WMI) CORE 1.5 (Windows 95/98/NT 4.0)](http://www.microsoft.com/downloads/details.aspx?familyid=afe41f46-e213-4cbf-9c5b-fbf236e0e875&displaylang=it) dall'area di download del sito Web Microsoft all'indirizzo www.microsoft.com/downloads/details.aspx?  
    FamilyID=afe41f46-e213-4cbf-9c5b-fbf236e0e875&DisplayLang=it.
  
-   Per ulteriori informazioni su WMI, consultare la documentazione [Windows Management Instrumentation](http://msdn.microsoft.com/en-us/library/aa394582(vs.85).aspx) sul sito Web MSDN® all'indirizzo http://msdn.microsoft.com/library/en-us/wmisdk/  
    wmi/wmi\_start\_page.asp.
  
-   È possibile scaricare [Microsoft Windows Script 5.6 per Windows 2000 e XP](http://www.microsoft.com/downloads/details.aspx?familyid=c717d943-7e4b-4622-86eb-95a22b832caa&displaylang=it) dall'area di download del sito Web Microsoft all'indirizzo www.microsoft.com/downloads/details.aspx?  
    FamilyId=C717D943-7E4B-4622-86EB-95A22B832CAA&displaylang=it.
  
-   È possibile scaricare [Windows Script 5.6 Documentation](http://www.microsoft.com/downloads/details.aspx?familyid=01592c48-207d-4be1-8a76-1c4099d7bbb9&displaylang=en) dall'area di download del sito Web Microsoft all'indirizzo www.microsoft.com/downloads/details.aspx?  
    FamilyId=01592C48-207D-4BE1-8A76-1C4099D7BBB9&displaylang=en (in lingua inglese).
  
**Scarica la soluzione completa**
  
[Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=33947)
  
[](#mainsection)[Inizio pagina](#mainsection)
