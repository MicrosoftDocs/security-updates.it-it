---
TOCTitle: 'Capitolo 2: Meccanismi di protezione avanzata di Windows Server 2003'
Title: 'Capitolo 2: Meccanismi di protezione avanzata di Windows Server 2003'
ms:assetid: '7cc50ea6-80d8-4ef6-81de-f47a60ebf8fa'
ms:contentKeyID: 20213202
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163110(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Capitolo 2: Meccanismi di protezione avanzata di Windows Server 2003

##### In questa pagina

[](#eeaa)[Panoramica](#eeaa)
[](#edaa)[Aumento della protezione con la Configurazione guidata impostazioni di sicurezza](#edaa)
[](#ecaa)[Aumento della protezione dei server con i criteri di gruppo Active Directory](#ecaa)
[](#ebaa)[Panoramica del processo](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

Questo capitolo introduce i meccanismi che possono essere utilizzati per implementare le impostazioni di protezione su Microsoft Windows Server 2003. Il Service Pack 1 (SP1) di Windows Server 2003 fornisce la Configurazione guidata impostazioni di sicurezza (SCW), un nuovo strumento basato sui ruoli, che può essere usato per aumentare la protezione dei server. Quando è utilizzato assieme agli oggetti Criteri di gruppo (GPO), lo strumento SCW consente un maggior controllo, flessibilità e uniformità del processo di aumento della protezione.

Questo capitolo si concentra sui seguenti argomenti:

-   Come utilizzare SCW per creare, verificare e implementare i criteri di aumento della protezione basati sui ruoli.

-   Come il servizio directory Active Directory facilita l'aumento costante dell'organizzazione grazie all'uso di GPO.

-   Come la progettazione del dominio Active Directory, dell'unità organizzativa (OU), dei Criteri di gruppo e del gruppo amministrativo influisce sull'implementazione della protezione.

-   Come utilizzare sia SCW sia i Criteri di gruppo per creare un metodo gestibile e basato sui ruoli per aumentare la protezione di server che eseguono Windows Server 2003 con SP1.

Queste informazioni offrono una base e una visione che possono essere sviluppate per passare da un ambiente LC (Legacy Client) a uno SSLF (Specialized Security – Limited Functionality) entro un'infrastruttura di dominio.

[](#mainsection)[Inizio pagina](#mainsection)

### Aumento della protezione con la Configurazione guidata impostazioni di sicurezza

Lo scopo di SCW è quello di fornire un processo flessibile e dettagliato per ridurre la superficie esposta agli attacchi sui server che eseguono Windows Server 2003 con SP1. SCW è una raccolta di strumenti abbinata a un database con regolamento XML. Esso si prefigge di aiutare gli amministratori a determinare in modo rapido e preciso la funzionalità minima richiesta per i ruoli che i server specifici devono soddisfare.

Con SCW, gli amministratori possono redigere, verificare, localizzare i guasti e implementare criteri di protezione che disattivano tutte le funzionalità non essenziali. Offre anche la possibilità di ripristinare i criteri di protezione. SCW fornisce il supporto nativo per la gestione di criteri di protezione sia su server singoli sia su gruppi di server che condividono la suddetta funzionalità.

SCW è uno strumento completo che può aiutare a svolgere le seguenti funzioni:

-   Determinare quali servizi devono essere attivi, quali servizi devono essere eseguiti quando richiesto e quali servizi possono essere disabilitati.

-   Gestire il filtraggio della porta di rete unitamente a Windows Firewall.

-   Controllare quali estensioni IIS Web sono permesse per i server Web.

-   Ridurre l'esposizione del protocollo ai protocolli SMB (Server Message Block), NetBIOS, CIFS (Common Internet File System) e LDAP (Lightweight Directory Access Protocol).

-   Creare utili criteri di controllo per acquisire eventi interessanti.

Istruzioni dettagliate su come installare, utilizzare e localizzare i guasti SCW sono disponibili in una versione scaricabile della documentazione[Configurazione guidata impostazioni di protezione](http://www.microsoft.com/downloads/details.aspx?familyid=903fd496-9eb9-4a45-aa00-3f2f20fd6171&displaylang=en) all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyID=903fd496-9eb9-4a45-aa00-3f2f20fd6171&displaylang=en.

**Nota**: SCW può essere utilizzato soltanto con Windows Server 2003 con SP1. Non può essere utilizzato per creare i criteri per Windows 2000 Server, Windows XP o Windows Small Business Server 2003. Per aumentare la protezione di un numero notevole di computer che eseguono questi sistemi operativi, ci si può avvalere dei meccanismi di aumento della protezione basati sui Criteri di gruppo descritti più avanti in questo capitolo.

#### Creazione e verifica dei criteri

Si può utilizzare SCW per creare e verificare rapidamente i criteri di protezione per i server multipli o per gruppi di server da un unico computer. Questa funzionalità consente di gestire criteri in ogni parte dell'organizzazione da un'unica postazione. Questi criteri offrono delle misure per aumentare la protezione, supportate e costanti, mirate alle funzioni che ogni server svolge nell'organizzazione. Se SCW è utilizzato per creare e verificare i criteri, lo si deve implementare anche su tutti i server di destinazione. Sebbene si crei il criterio su una stazione di gestione, SCW tenterà di comunicare con i server di destinazione per ispezionare la loro configurazione e mettere a punto un criterio idoneo.

SCW fa parte integrante dei sottosistemi IPsec e Windows Firewall e modificherà come richiesto tali impostazioni. Se non glielo si impedisce, SCW configurerà Windows Firewall per permettere l'accesso del traffico di rete in ingresso alle porte importanti richieste dal sistema operativo e anche dalle applicazioni in ascolto. Se sono necessari altri filtri porta, SCW li può creare. Di conseguenza, i criteri creati da SCW soddisfano il bisogno di script personalizzati per impostare o modificare i filtri IPsec per bloccare il traffico superfluo. Questa funzionalità semplifica la gestione dell'aumento della protezione di rete. Può anche essere semplificata la configurazione di filtri di rete per i servizi che utilizzano le porte RPC o quelle dinamiche.

SCW fornisce anche le funzionalità per personalizzare notevolmente i criteri creati. Questa flessibilità aiuta a creare una configurazione che rende disponibili le necessarie funzionalità riducendo al tempo stesso i rischi di protezione. Oltre ai comportamenti e alle impostazioni di base, è possibile sovrascrivere SCW nelle seguenti aree:

-   Servizi

-   Porte di rete

-   Applicazioni approvate da Windows Firewall

-   Impostazioni del Registro di sistema

-   Impostazioni IIS

-   Inclusione di modelli di protezione preesistenti (file .inf)

SCW consiglia l'amministratore relativamente ad alcune delle più importanti impostazioni di registro. Per ridurre la complessità dello strumento, i progettisti hanno scelto di includere solo le impostazioni che esercitano l'impatto maggiore sulla protezione. Questa guida si occupa comunque di molte altre impostazioni di registro. Per superare le limitazioni inerenti a SCW, è possibile abbinare i modelli di protezione ai risultati di SCW per creare una configurazione più completa.

Quando si utilizza SCW per creare un nuovo criterio, SCW utilizza la configurazione attuale di un server quale configurazione iniziale. Si deve quindi individuare un server di tipo analogo a quello sul quale si intende implementare il criterio in modo da poter descrivere con precisione la configurazione dei ruoli del server. Quando viene utilizzata l'interfaccia utente grafica (GUI) di SCW per creare un nuovo criterio, essa crea un file XML e, per impostazione predefinita, lo salva nella cartella **%systemdir%\\security\\msscw\\Policies**. Dopo aver creato i criteri, è possibile utilizzare sia la GUI SCW sia lo strumento della riga di comando Scwcmd, per applicare tali criteri ai server di test.

Quando si verificano i criteri, potrebbe essere necessario eliminare quello che è stato utilizzato. È possibile utilizzare sia la GUI sia lo strumento della riga di comando Scwcmd per ripristinare l'ultimo criterio applicato a un server o a un gruppo di server. SCW salva le impostazioni della configurazione precedente nei file XML.

Per le organizzazioni che hanno risorse limitate per la progettazione e verifica delle configurazioni di protezione, SCW può essere sufficiente. Le organizzazioni a cui mancano tali risorse non devono neppure tentare di aumentare la protezione dei server, perché tali sforzi spesso causano problemi imprevisti e la perdita di produttività. Se l'organizzazione non ha la capacità e il tempo necessario per occuparsi di queste problematiche, è meglio concentrarsi su altre importanti attività di protezione, come ad esempio il potenziamento delle applicazioni e del sistema operativo ai livelli attuali e l'aggiornamento della gestione.

#### Distribuzione dei criteri

È possibile utilizzare tre opzioni diverse per implementare i criteri:

-   Applicazione del criterio con la GUI SCW

-   Applicazione del criterio con lo strumento della riga di comando Scwcmd

-   Conversione del criterio SCW in un oggetto Criteri di gruppo e suo collegamento a un dominio o a una OU

Ogni opzione presenta vantaggi e limitazioni, descritti nelle seguenti sottosezioni.

##### Applicazione del criterio con la GUI SCW

Il principale vantaggio offerto dall'opzione GUI SCW è la semplicità. La GUI permette agli amministratori di scegliere facilmente un criterio predefinito e di applicarlo su un unico computer.

Lo svantaggio dell'opzione GUI SCW è che permette l'applicazione di criteri su di un solo computer alla volta. Dato che questa opzione non può essere ampliata per ambienti di grandi dimensioni, la presente guida non utilizza questo metodo.

##### Applicazione del criterio con lo strumento della riga di comando Scwcmd

Per applicare i criteri SCW nativi a computer multipli senza Active Directory è possibile utilizzare lo strumento Scwcmd. È anche possibile abbinare l'uso di Scwcmd alle tecnologie di script per fornire un certo grado di implementazione automatica del criterio, forse nell'ambito di un processo esistente, utilizzato per costruire e implementare i server.

Lo svantaggio principale dell'opzione Scwcmd consiste nel fatto che non è automatica. Dato che è necessario specificare il criterio e il server di destinazione, sia manualmente sia utilizzando degli script, vi sono delle probabilità maggiori di inviare il criterio sbagliato al computer sbagliato. Se si dispone di server in un gruppo con configurazioni leggermente diverse, si dovrà creare un criterio distinto per ognuno di quei computer e applicarlo individualmente. Viste le limitazioni, questa guida non utilizza questo metodo.

##### Conversione del criterio SCW in un oggetto Criteri di gruppo

La terza opzione per l'implementazione di un criterio SCW è quella di utilizzare lo strumento Scwcmd per convertire i criteri basati su XML in un oggetto Criteri di Gruppo (GPO). Anche se, all'inizio, questa conversione potrebbe dare l'impressione di essere una fase inutile, essa presenta i seguenti vantaggi:

-   I criteri sono replicati, distribuiti e applicati con meccanismi noti basati su Active Directory.

-   Dato che non si tratta di GPO nativi, i criteri possono essere utilizzati con le OU, con l'eredità dei criteri e con criteri di incremento per mettere a punto l'aumento della protezione dei server che sono configurati in modo simile, ma non precisamente uguale agli altri server. Con i criteri di gruppo, questi server sono stati posti in un'unità organizzativa figlio ed è stato applicato un criterio di incremento, mentre con SCW sarebbe stato necessario creare un nuovo criterio per ciascuna configurazione esclusiva.

-   I criteri sono applicati automaticamente a tutti i server collocati nelle OU corrispondenti. I criteri SCW nativi devono essere applicati manualmente oppure utilizzati unitamente a delle soluzioni di script personalizzate.

[](#mainsection)[Inizio pagina](#mainsection)

### Aumento della protezione dei server con i criteri di gruppo Active Directory

Active Directory consente alle applicazioni di individuare, utilizzare e gestire risorse di directory in un ambiente di elaborazione distribuito. Anche se le informazioni dettagliate su come progettare un'infrastruttura Active Directory potrebbero riempire un libro intero, questa sezione discute brevemente questi concetti per stabilire il contesto per il resto della guida. Queste informazioni di progetto sono necessarie per permettere di capire l'utilizzo dei criteri di gruppo per amministrare in modo sicuro i domini dell'organizzazione, i controller di dominio e i ruoli specifici dei server. Qualora l'organizzazione disponga già di una struttura Active Directory, questo capitolo offrirà informazioni utili su alcuni dei vantaggi o dei potenziali problemi relativi alla sicurezza.

Questa guida non offre delle istruzioni specifiche su come proteggere il database Active Directory. Per avere tali istruzioni, consultare il documento "[Best Practice Guide for Securing Active Directory Installations"](http://www.microsoft.com/downloads/details.aspx?familyid=2eaa45c7-d936-413e-9586-a8bb6ff739d9&displaylang=en&tm) al quale si fa riferimento nella sezione "Ulteriori informazioni" alla fine di questo capitolo.

Quando si crea un'infrastruttura Active Directory occorre valutare attentamente i limiti di protezione dell'ambiente. Una pianificazione adeguata della tempistica di implementazione e di delega della protezione di un'organizzazione comporterà una progettazione molto più sicura di Active Directory per l'organizzazione. La ristrutturazione della progettazione dovrebbe rendersi necessaria solo in caso di modifiche di grande entità dell'ambiente, come ad esempio un'acquisizione o una riorganizzazione.

#### Limiti Active Directory

Esistono diversi tipi di limiti nell'ambito di Active Directory. Tali limiti definiscono l'insieme di strutture, il dominio, la topologia del sito e la delega di autorizzazioni e sono automaticamente stabiliti quando si installa Active Directory. È comunque necessario garantire che i limiti di autorizzazione incorporino i requisiti e i criteri dell'organizzazione. La delega di autorizzazioni amministrative può essere piuttosto flessibile per adattarsi ai diversi requisiti delle organizzazioni. Se si desidera, ad esempio, mantenere un equilibrio adeguato tra funzionalità di protezione e funzionalità amministrative, è possibile suddividere ulteriormente i limiti relativi alla delega di autorizzazioni in limiti di protezione e limiti amministrativi.

##### Limiti di protezione

I limiti di protezione consentono di definire l'autonomia o l'isolamento di gruppi differenti all'interno di un'organizzazione. È difficile bilanciare la garanzia di un'adeguata sicurezza (basata sulle modalità di definizione dei limiti aziendali), con l'esigenza di continuare a fornire un solido livello di funzionalità di base. Per raggiungere tale equilibrio, occorre valutare attentamente gli eventuali pericoli per l'organizzazione in rapporto alle implicazioni a livello di protezione che potrebbero derivare dalla delega di autorizzazioni amministrative e di altre scelte relative all'architettura di rete dell'ambiente.

L'insieme di strutture costituisce il vero limite di protezione dell'ambiente di rete. Questa guida raccomanda la creazione di un insieme di strutture separate per proteggere l'ambiente da potenziali compromissioni da parte di amministratori di altri domini. Questo metodo serve anche a garantire che la compromissione di un insieme di strutture non comprometta automaticamente l'intera organizzazione.

Un dominio rappresenta il limite di gestione di Active Directory, non un limite di protezione. Nel caso di un'organizzazione in cui operano persone corrette e affidabili, i limiti di dominio garantiranno la gestione autonoma dei servizi e dei dati all'interno di ogni dominio dell'organizzazione. Sfortunatamente, quando si parla di sicurezza, l'isolamento non è così facile da realizzare. Un dominio, ad esempio, non è in grado di assicurare il completo isolamento da eventuali attacchi di amministratori disonesti. Un simile grado di separazione può essere raggiunto solo a livello dell'insieme di strutture.

All'interno del dominio, l'unità organizzativa (OU) fornisce un altro livello di limite di gestione. Le OU offrono un modo flessibile per raggruppare le risorse e delegare l'accesso per la gestione agli addetti più idonei senza dar loro la capacità di gestire l'intero dominio. Come i domini, le OU non costituiscono un vero limite alla protezione. Sebbene si possano assegnare delle autorizzazioni a una OU, tutte le OU nello stesso dominio autenticano le risorse rispetto a quelle del dominio e dell'insieme di strutture. Tuttavia, una gerarchia di OU ben progettate faciliterà sviluppo, implementazione e gestione di misure di protezione efficaci.

Può rivelarsi necessario per l'organizzazione prendere in considerazione l'opportunità di suddividere il controllo amministrativo dei servizi e dei dati nell'ambito della progettazione di Active Directory. Un'efficace progettazione di Active Directory richiede una comprensione approfondita delle esigenze a livello di autonomia e isolamento dei servizi oltre che dell'autonomia e dell'isolamento dei dati.

##### Limiti amministrativi

Per sopperire alla potenziale esigenza di segmentare servizi e dati, occorre definire i diversi livelli di amministrazione necessari. Oltre agli amministratori che possono eseguire servizi esclusivi per l'organizzazione, queste istruzioni raccomandano di prendere in considerazione i seguenti tipi di amministratori.

###### Amministratori di servizi

Gli amministratori di servizi Active Directory sono responsabili della configurazione e dell'erogazione del servizio di directory. Gli amministratori dei servizi si occupano, ad esempio, di gestire i server controller di dominio nonché di controllare le impostazioni di configurazione a livello di directory e garantiscono la disponibilità del servizio. Gli amministratori di Active Directory devono essere considerati gli amministratori di servizi all'interno dell'organizzazione

In molti casi, la configurazione dei servizi Active Directory è determinata dai valori degli attributi. Questi valori degli attributi corrispondono alle impostazioni relative ai rispettivi oggetti archiviati nella directory. Di conseguenza, gli amministratori di servizi Active Directory sono anche amministratori di dati. Le esigenze dell'organizzazione possono richiedere di prendere in considerazione altri gruppi di amministratori di servizi per la progettazione del servizio Active Directory. Alcuni di questi sono:

-   Un gruppo di amministrazione dei domini, responsabile principalmente dei servizi directory.

    L'amministratore di un insieme di strutture è responsabile della scelta del gruppo di amministrazione di ciascun dominio. Dato che dispongono di un elevato livello di accesso per ciascun dominio, questi amministratori devono essere estremamente affidabili. Gli amministratori del dominio controllano i domini tramite il gruppo **Amministratori di dominio** e altri gruppi incorporati.

-   Gruppi di amministratori che gestiscono DNS.

    Il gruppo di amministratori DNS completa il progetto DNS e gestisce l'infrastruttura DNS. L'amministratore DNS gestisce l'infrastruttura DNS mediante il gruppo di **Amministratori DNS.**

-   Gruppi di amministratori che gestiscono OU.

    L'amministratore OU designa un gruppo o un singolo individuo come gestore di ciascuna unità organizzativa. Ogni amministratore OU gestisce i dati archiviati all'interno dell'unità organizzativa di Active Directory assegnatagli. Questi gruppi possono controllare come viene delegata l'amministrazione e come i criteri vengono applicati agli oggetti all'interno delle unità organizzative. Inoltre, gli amministratori OU possono creare nuove sottostrutture e delegare l'amministrazione delle unità organizzative di cui sono responsabili.

-   Gruppi di amministratori che gestiscono i server dell'infrastruttura.

    Il gruppo che è responsabile dell'amministrazione del server dell'infrastruttura gestisce WINS, DHCP e, potenzialmente, l'infrastruttura DNS. In alcuni casi il gruppo di amministrazione dei domini provvederà alla gestione dell'infrastruttura DNS poiché Active Directory è integrato con DNS ed è archiviato e gestito sui controller di dominio.

###### Amministratori di dati

Gli amministratori di dati Active Directory gestiscono i dati memorizzati in Active Directory o sui computer che appartengono ad Active Directory. Essi non dispongono di alcun controllo sulla configurazione o l'erogazione del servizio di directory. Gli amministratori di dati sono membri di un gruppo di protezione creato dall'organizzazione. Può accadere che i gruppi di protezione predefiniti di Windows non risultino appropriati per tutte le situazioni che possono presentarsi all'interno di un'azienda. Pertanto, ogni organizzazione può sviluppare significati e standard propri per la denominazione di gruppi di protezione, in modo da soddisfare al meglio le esigenze dei singoli ambienti. Tra le attività svolte quotidianamente dagli amministratori di dati figurano:

-   Controllo di un sottoinsieme di oggetti all'interno della directory. Mediante un controllo di accesso ereditabile a livello di attributo, agli amministratori di dati può essere concesso il controllo di sezioni specifiche della directory, senza però avere alcuna forma di controllo sulla configurazione del servizio in sé.

-   Gestione dei computer membri all'interno della directory e dei dati archiviati su tali computer.

**Nota**: in molti casi i valori degli attributi relativi agli oggetti archiviati nella directory determinano la configurazione del servizio di directory.

Riepilogando, per consentire ai proprietari di strutture di directory e di servizi Active Directory di connettersi a un insieme di strutture o un'infrastruttura di domini è necessario che l'organizzazione riponga piena fiducia in tutti gli amministratori di servizi nell'ambito dell'insieme di strutture e di tutti i domini. I programmi per la protezione aziendale devono inoltre sviluppare criteri e procedure standard che eseguano i corretti controlli in background per gli amministratori. Nel contesto specifico di questa guida sulla protezione, considerare affidabili gli amministratori di servizi significa:

-   Ritenere ragionevolmente che gli amministratori di servizi agiranno principalmente nell'interesse dell'organizzazione. Le organizzazioni devono evitare di connettersi a un insieme di strutture o a un dominio nel caso in cui i relativi proprietari possano disporre di motivi fondati per agire ai danni dell'organizzazione.

-   Ritenere ragionevolmente che gli amministratori di servizi si atterranno alle procedure consigliate e limiteranno l'accesso fisico ai controller di dominio.

-   Conoscere e accettare i rischi in cui l'organizzazione può incorrere a causa di:

    -   **Amministratori inaffidabili**. È sempre possibile che amministratori normalmente affidabili si rivelino malintenzionati e abusino dei diritti di cui dispongono sulla rete. Un amministratore inaffidabile all'interno di un insieme di strutture potrebbe facilmente cercare l'identificatore di protezione (SID) relativo a un altro amministratore di un dominio diverso. Dopo averlo individuato, potrà quindi utilizzare uno strumento API (Application Programming Interface), un editor di dischi o un debugger per aggiungere il SID rubato all'elenco cronologia SID di un account all'interno del proprio dominio. Aggiungendo il SID rubato alla cronologia SID dell'utente, l'amministratore inaffidabile potrà godere di privilegi amministrativi non solo nel proprio dominio, ma anche in quello del SID rubato.

    -   **Amministratori sotto coercizione** Amministratori normalmente affidabili potrebbero essere costretti o indotti a eseguire operazioni che possono violare la protezione di un computer o di una rete. Un utente o un amministratore possono usare tecniche di individuazione di persone vulnerabili o la minaccia di lesioni fisiche o di altro tipo contro gli amministratori legittimi di un computer al fine di ottenere i nomi utente e le password di cui hanno bisogno per accedere al computer.

Alcune organizzazioni possono considerare accettabile il rischio di violazioni della protezione da parte di amministratori di servizi malintenzionati o sotto coercizione provenienti da altre parti dell'organizzazione. È possibile infatti che ritengano che i vantaggi in termini di collaborazione e di risparmio sui costi derivanti dalla partecipazione a un'infrastruttura condivisa compensino tale rischio. Altre organizzazioni, al contrario, possono non accettare il rischio poiché reputano troppo gravi le potenziali conseguenze di una violazione della protezione.

#### Active Directory e criteri di gruppo

Le OU rappresentano non solo un metodo semplice per raggruppare computer, utenti, gruppi e altre identità di protezione, ma anche uno strumento efficiente per segmentare i limiti amministrativi. Le OU forniscono inoltre una struttura importante per l'implementazione di oggetti Criteri di Gruppo (GPO) perché possono segmentare le risorse in base alle esigenze di protezione e consentire una protezione differente a OU diverse. L'utilizzo di OU per gestire e assegnare criteri di protezione basati sui ruoli del server è una parte integrante dell'architettura complessiva di protezione dell'organizzazione.

##### Delega dell'amministrazione e applicazione di criteri di gruppo

LE OU sono dei contenitori entro la struttura di directory di un dominio. Questi contenitori possono contenere qualsiasi identità di protezione nel dominio, sebbene siano di solito usati per contenere oggetti di carattere specifico. Per concedere o revocare le autorizzazioni di accesso delle OU a un gruppo o a un utente individuale, si possono impostare degli elenchi di controllo dell'accesso specifici (ACL) sulla OU e le autorizzazioni saranno ereditate da tutti gli oggetti all'interno della OU.

È possibile utilizzare una OU per fornire le funzionalità amministrative basate sui ruoli. Per esempio, un gruppo di amministratori potrebbe essere responsabile delle OU utente e di gruppo, mentre un altro gruppo potrebbe gestire le OU che contengono i server. È anche possibile creare un'unità organizzativa per contenere un gruppo di server di risorse che devono essere amministrati da altri utenti tramite un processo denominato delega di controllo. Questo metodo fornisce al gruppo delegato il controllo autonomo su di una particolare OU, senza isolarle dal resto del dominio.

Gli amministratori che delegano il controllo su OU specifiche sono molto probabilmente amministratori di servizi. A un livello inferiore di autorità, gli utenti che dispongono del controllo sulle unità organizzative sono in genere amministratori di dati.

##### Gruppi amministrativi

Gli amministratori possono creare dei gruppi amministrativi per segmentare cluster di utenti, gruppi di protezione o i server in contenitori per l'amministrazione autonoma.

Si considerino, ad esempio, i server infrastruttura che risiedono in un dominio. Tali server includono tutti i controller non di dominio su cui vengono eseguiti servizi di rete di base, compresi i server che eseguono servizi WINS e DHCP. Spesso questi server sono gestiti da un gruppo per l'amministrazione delle infrastrutture o da un gruppo per la gestione in esercizio. È possibile utilizzare una OU per fornire a questi server le funzionalità amministrative.

La figura riportata di seguito illustra in maniera dettagliata una tale configurazione di un'unità organizzativa.

![](images/Cc163110.sgfg0201(it-it,TechNet.10).gif "Figura 2.1 Delega dell'amministrazione dell'unità operativa")

**Figura 2.1 Delega dell'amministrazione dell'unità operativa**

Quando al gruppo **Amministratori infrastruttura** viene delegato il controllo dell'OU dell'infrastruttura, i membri di questo gruppo avranno il controllo totale dell'OU dell'infrastruttura e di tutti i server e oggetti nell'OU. Questa funzionalità consente ai membri del gruppo di proteggere i ruoli di server con i criteri di gruppo.

Questo metodo non è che uno di vari modi in cui è possibile utilizzare le unità organizzative per fornire una segmentazione amministrativa. Per organizzazioni più complesse, fare riferimento alla sezione "Ulteriori informazioni" alla fine di questo capitolo.

**Nota**: dato che Active Directory dipende così fortemente dal DNS, di solito si esegue il servizio DNS sui controller di dominio. I controller di dominio sono collocati nell'OU dei Controller di dominio incorporati per impostazione predefinita. Gli esempi in questa guida seguono questa prassi, per cui il ruolo di server dell'infrastruttura non comprende il servizio DNS.

##### Applicazione dei criteri di gruppo

Utilizzare i criteri di gruppo e delegare l'amministrazione per applicare impostazioni, diritti e comportamenti specifici a tutti i server all'interno di un'unità organizzativa. Se si utilizzano i criteri di gruppo anziché le procedure manuali, risulta semplificato l'aggiornamento di più server con modifiche aggiuntive eventualmente necessarie in futuro.

I criteri di gruppo vengono accumulati e applicati nell'ordine visualizzato nella figura seguente.

[![](images/Cc163110.sgfg0202(it-it,TechNet.10).gif "Figura 2.2 Gerarchia di applicazione di GPO")](https://technet.microsoft.com/it-it/cc163110.sgfg0202_big(it-it,technet.10).gif)

**Figura 2.2 Gerarchia di applicazione di GPO**

Come da figura, i criteri sono applicati in primo luogo a livello di criterio locale del computer. Successivamente, tutti gli oggetti Criteri di gruppo vengono applicati a livello di sito, quindi a livello di dominio. Se il server è nidificato in più unità organizzative, vengono applicati per primi i GPO dell'unità organizzativa di livello più elevato. Il processo di applicazione dei GPO prosegue, quindi, in base alla struttura gerarchica della OU. L'ultimo GPO da applicare è a livello dell'unità organizzativa figlio contenente l'oggetto server. L'ordine di precedenza per l'elaborazione dei criteri di gruppo si estende dall'unità organizzativa di livello più elevato (quella più lontana dall'account dell'utente o del computer) fino a quella di livello più basso (che contiene davvero l'account dell'utente o del computer).

Nella progettazione dei criteri di gruppo, tenere presenti le seguenti considerazioni di base:

-   È necessario impostare l'ordine di applicazione dei GPO per i livelli di criteri di gruppo con più GPO. Se più criteri specificano la stessa opzione, l'ultimo applicato avrà la precedenza.

-   È necessario configurare un criterio di gruppo con l'opzione **Non sovrascrivere** se non si vuole che altri GPO lo sovrascrivano. Se si usa la Console di gestione Criteri di gruppo (GPMC) per gestire i GPO, il nome di questa opzione è **Imposto.**

##### Impostazione dell'ora

Molti servizi di protezione, soprattutto l'autenticazione, fanno affidamento su di un orologio di precisione nel computer per eseguire le loro funzioni. È necessario verificare che l'ora del computer sia precisa e che tutti i server dell'organizzazione utilizzino la stessa origine ora. Il servizio W32Time di Windows Server 2003 consente la sincronizzazione dell'ora del computer con il sistema operativo Windows Server 2003 o Microsoft Windows XP in esecuzione in un dominio Active Directory.

Il servizio W32Time consente di sincronizzare gli orologi dei computer con Windows Server 2003 con i controller di dominio all'interno di un dominio. Questa sincronizzazione è necessaria per consentire al protocollo Kerberos e agli altri protocolli di autenticazione di funzionare correttamente. La sincronizzazione e la precisione dell'ora sono indispensabili per il corretto funzionamento di numerosi componenti della famiglia di server Windows. Se gli orologi sui client non sono sincronizzati, il protocollo di autenticazione Kerberos potrebbe negare l'accesso agli utenti.

Un altro importante vantaggio che la sincronizzazione dell'ora offre è la correlazione degli eventi su tutti i client dell'azienda. Gli orologi sincronizzati sui client dell'ambiente in uso consentono di analizzare correttamente gli eventi che hanno luogo in sequenza uniforme su quei client a livello aziendale.

Il servizio W32Time utilizza il protocollo NTP (Network Time Protocol) per sincronizzare gli orologi sui computer che eseguono Windows Server 2003. In un insieme di strutture di Windows Server 2003, l'ora viene sincronizzata, per impostazione predefinita, nel modo seguente:

-   Il master operazioni dell'emulatore PDC (Primary Domain Controller) nel dominio principale dell'insieme di strutture rappresenta l'origine ora autorevole per l'organizzazione.

-   Tutti i master operazioni PDC di altri domini dell'insieme di strutture seguono la gerarchia dei domini quando viene selezionato un emulatore PDC per la sincronizzazione dell'ora.

-   Tutti i controller di dominio all'interno di un dominio sincronizzano l'ora con il master operazioni dell'emulatore PDC del loro dominio quale partner orario in ingresso.

-   Tutti i server membro e i computer desktop client utilizzano il controller di dominio di autenticazione come partner orario in ingresso.

Per accertarsi che l'ora sia precisa, l'emulatore PDC del dominio principale dell'insieme di strutture può essere sincronizzato con un'origine ora autorevole, ad esempio un'origine NTP affidabile o un orologio della massima precisione sulla rete. Notare che la sincronizzazione NTP utilizza il traffico 123 della porta UDP. Prima di sincronizzarsi con un server esterno, si devono valutare i vantaggi dati dall'apertura di questa porta rispetto ai potenziali rischi per la protezione.

Inoltre, se ci si sincronizza con un server esterno sul quale non si ha alcun controllo, si rischia di configurare i server con l'ora inesatta. Il server esterno potrebbe essere compromesso o attaccato da un aggressore per manipolare in modo doloso gli orologi sui computer. Come spiegato prima, il protocollo di autenticazione Kerberos richiede la sincronizzazione degli orologi dei computer. Se non sono sincronizzati, si potrebbe verificare una negazione del servizio.

##### Gestione dei modelli di protezione

I modelli di protezione sono dei file di testo che possono essere usati per applicare una configurazione di protezione a un computer. È possibile modificare i modelli di protezione con lo Snap-in Modelli di protezione di Microsoft Management Console (MMC) o con un editor di testo, ad esempio Blocco note. Alcune sezioni dei file modello contengono ACL specifici, scritti nel linguaggio SDDL (Security Descriptor Definition Language). Si possono trovare ulteriori informazioni su come modificare i modelli di protezione e l'SDDL alla pagina "[Security Descriptor Definition Language](http://msdn.microsoft.com/en-us/library/aa379567.aspx)" su Microsoft MSDN all'indirizzo http://msdn.microsoft.com/library/
en-us/secauthz/security/security\_descriptor\_definition\_language.asp.

Per impostazione predefinita, gli utenti autenticati hanno il diritto di leggere tutte le impostazioni contenute in un oggetto Criteri di gruppo. Pertanto, è molto importante archiviare i modelli di protezione utilizzati per un ambiente di produzione in un luogo protetto, al quale solo gli amministratori responsabili dell'implementazione dei criteri di gruppo possano accedere. L'obiettivo non è impedire la visualizzazione dei file \*.inf, quanto piuttosto impedire modifiche non autorizzate ai modelli di protezione di origine.

Tutti i computer che eseguono Windows Server 2003 archiviano i modelli di protezione nella cartella locale **%SystemRoot%\\security\\templates**. Questa cartella non è replicata in più controller di dominio e sarà pertanto necessario designare un luogo in cui conservare la copia master dei modelli di protezione in modo che non si verifichino problemi di controllo della versione relativi ai modelli. Dopo la modifica del modello centrale, è possibile implementarlo sui computer appropriati. Adottando tale procedura, si assicurerà che venga modificata sempre la stessa copia dei modelli.

##### Eventi di applicazione corretta dei GPO

Oltre a effettuare una verifica manuale di tutte le impostazioni per assicurarsi che siano state applicate in modo appropriato ai server dell'organizzazione, occorre anche controllare che un evento venga visualizzato nel registro eventi per informare l'amministratore che i criteri di dominio sono stati scaricati correttamente su ciascuno dei server. Un evento simile a quello illustrato di seguito deve essere visualizzato nel registro Applicazioni con un numero di identificazione univoco:

**Tipo**: Informazioni

**ID origine**: SceCli

**ID evento**: 1704

**Descrizione**: Applicazione del criterio di protezione agli oggetti Criteri di gruppo riuscita.

Per impostazione predefinita, le impostazioni di protezione vengono aggiornate ogni 90 minuti su una workstation o un server e ogni 5 minuti su un controller di dominio. Si potrà rilevare questo evento se, durante gli intervalli di tempo specificati, si verifica un cambiamento. Le impostazioni sono inoltre aggiornate ogni 16 ore, indipendentemente dal fatto che siano state apportate o meno delle modifiche. È possibile imporre manualmente le impostazioni dei criteri di gruppo per l'aggiornamento, utilizzando la procedura descritta più avanti in questo capitolo.

##### Unità organizzative di ruoli di server

L'esempio precedente ha mostrato un modo per gestire i server dell'infrastruttura dell'organizzazione. Questo metodo può essere esteso ad altri server e servizi in un'organizzazione. L'obiettivo è creare criteri di gruppo ottimizzati estesi a tutti i server, garantendo al contempo che i server che risiedono all'interno di Active Directory soddisfino gli standard di protezione relativi all'ambiente dell'organizzazione.

Questo tipo di criteri di gruppo costituisce una base coerente per la definizione di impostazioni standard su tutti i server dell'organizzazione. La struttura delle unità organizzative e l'applicazione di criteri di gruppo devono inoltre offrire una progettazione dettagliata in modo da fornire impostazioni di protezione per tipi specifici di server all'interno di un'organizzazione. Così, ad esempio, i server IIS (Internet Information Server), i file server, i server di stampa, quelli IAS (Internet Authentication Server) e i Servizi certificati non rappresentano che una piccola parte dei ruoli server in un'organizzazione che possono richiedere criteri di gruppo univoci.

**Importante**: per maggiore semplicità, negli esempi di questo capitolo verrà utilizzato l'ambiente client di organizzazione. Se si utilizza uno degli altri due ambienti, sostituire i nomi dei file appropriati. Le differenze tra i tre ambienti e la loro funzionalità sono discusse nel Capitolo 1, "Presentazione della guida per la protezione di Windows  Server 2003".

###### Criteri di base dei server membro

Il primo passo per la definizione di unità organizzative di ruoli server consiste nel creare un criterio di base. Per creare tale criterio, si può utilizzare SCW su un server membro standard per formare un file Member Server Baseline.xml. Nell'ambito della creazione di XML, usare SCW per includere uno dei modelli di protezione dei server membro di base forniti (LC-Member Server Baseline.inf, EC-Member Server Baseline.inf, o SSLF-Member Server Baseline.inf).

Dopo aver generato il criterio SCW, lo si converte in un GPO e lo si collega all'OU dei server membro. Questo nuovo GPO di base applicherà le impostazioni dei Criteri di gruppo di base a qualunque server nell'OU dei Server membro, come pure a qualunque server nelle OU figlio. Il criterio di base del server membro è analizzato nel capitolo "Creazione di criteri di base dei server membro per Windows Server 2003".

È necessario definire le impostazioni desiderate per la maggior parte dei server nell'organizzazione nei criteri di gruppo di base. Potrebbe verificarsi che ci siano server che non devono ricevere il criterio di base, tuttavia non si dovrebbe trattare di molte unità. Se si creano i propri criteri di gruppo, si consiglia di renderli il più restrittivi possibile e di segmentare tutti i server ai quali non devono essere applicati tali criteri in unità organizzative separate specifiche dei server.

###### Unità organizzative e tipi di ruoli server

Ogni ruolo di server identificato richiede un criterio SCW aggiuntivo, un modello di protezione e un'unità organizzativa, oltre a quella di base. Questo metodo permette la creazione di criteri separati per le modifiche di incremento richieste da ogni ruolo.

In un esempio precedente, i server di infrastruttura erano stati collocati nell'infrastruttura dell'** **OU, che è un figlio dell'OU dei server membro. La fase successiva consiste nell'applicare la configurazione appropriata a questi server. I modelli di protezione sono forniti con questa soluzione, una per ogni ambiente di protezione: LC-Infrastructure Server.inf, EC-Infrastructure Server.inf, e** **SSLF-Infrastructure Server.inf. Quando sono utilizzati insieme a SCW, questi modelli di protezione aiutano a creare un criterio di protezione che contiene le regolazioni specifiche richieste da DHCP e WINS. Il criterio risultante è poi convertito in un nuovo GPO e collegato all'OU dell'infrastruttura.

Questo GPO utilizza le impostazioni **Gruppi con Restrizioni** per aggiungere i seguenti tre gruppi al gruppo **Amministratori locali** di tutti i server nell'OU dell'infrastruttura:

-   **Amministratori di dominio**

-   **Amministratori dell'organizzazione**

-   **Amministratori dell'infrastruttura**

Come si è detto precedentemente in questo capitolo, il metodo appena illustrato non è che una delle tante soluzioni disponibili per creare una struttura OU per l'implementazione di oggetti Criteri di gruppo. Per ulteriori informazioni su come creare le OU per l'implementazione di Criteri di gruppo, vedere "[Progettazione della struttura Active Directory](http://technet.microsoft.com/en-us/library/cc960542.aspx)" e soggetti correlati all'indirizzo www.microsoft.com/resources/documentation/Windows/2000/server/reskit/
en-us/deploy/dgbd\_ads\_heqs.asp?frame=true.

La seguente tabella elenca i ruoli di server di Windows Server 2003 e i corrispondenti file di modello descritti in questa guida. I nomi di file del modello di protezione hanno come prefisso la variabile *&lt;Env&gt;*, che, a seconda dei casi, sarà sostituita da LC (per Legacy Client), EC (per Enterprise Client) o SSLF (per Specialized Security – Limited Functionality).

**Tabella 2.1. Ruoli di server per Windows Server 2003**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Ruolo del server</th>
<th style="border:1px solid black;" >Descrizione</th>
<th style="border:1px solid black;" >Nome di file del modello di protezione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Server membro</td>
<td style="border:1px solid black;">Tutti i server che sono membri del dominio e risiedono all'interno dell'unità organizzativa dei server membro o a un livello inferiore.</td>
<td style="border:1px solid black;"><em>&lt;Env&gt;-</em>Member Server Baseline.inf<br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controller di dominio</td>
<td style="border:1px solid black;">Tutti i controller di dominio Active Directory Questi server sono anche i server DNS.</td>
<td style="border:1px solid black;"><em>&lt;Env&gt;-</em>Domain Controller.inf<br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Server infrastruttura</td>
<td style="border:1px solid black;">Tutti i server WINS e DHCP bloccati.</td>
<td style="border:1px solid black;"><em>&lt;Env&gt;-</em>Infrastructure Server.inf<br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">File server</td>
<td style="border:1px solid black;">Tutti i file server bloccati.</td>
<td style="border:1px solid black;"><em>&lt;Env&gt;-</em>File Server.inf</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Server di stampa</td>
<td style="border:1px solid black;">Tutti i server di stampa bloccati.</td>
<td style="border:1px solid black;"><em>&lt;Env&gt;-</em>Print Server.inf</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Web server</td>
<td style="border:1px solid black;">Tutti i server Web IIS bloccati.</td>
<td style="border:1px solid black;"><em>&lt;Env&gt;-</em>Web Server.inf</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Server IAS</td>
<td style="border:1px solid black;">Tutti i server IAS bloccati.</td>
<td style="border:1px solid black;"><em>&lt;Env&gt;-</em>IAS Server.inf</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Server servizi certificati</td>
<td style="border:1px solid black;">Tutti i server CA (Certification Authority) bloccati.</td>
<td style="border:1px solid black;"><em>&lt;Env&gt;-</em>CA Server.inf</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Host Bastion</td>
<td style="border:1px solid black;">Tutti i server Internet.</td>
<td style="border:1px solid black;"><em>&lt;Env&gt;-</em>Bastion Host.inf</td>
</tr>
</tbody>
</table>
  
Tutti i file del modello tranne quelli per i server host Bastion sono applicati alle unità organizzative figlio corrispondenti. Ciascuna di queste unità organizzative figlio richiede l'applicazione di una configurazione specifica per definire il ruolo che ciascun computer svolgerà nell'organizzazione.
  
I requisiti di protezione relativi a ognuno di questi ruoli server sono differenti. Le impostazioni di protezione appropriate per ciascun ruolo saranno analizzate in dettaglio nei prossimi capitoli. Notare che non tutti i ruoli hanno dei modelli che corrispondono a tutti gli ambienti. Per esempio, si ritiene sempre che il ruolo di host Bastion si trovi nell'ambiente SSLF.
  
**Importante**: questa guida parte dal presupposto che i computer con sistema operativo Windows Server 2003 svolgeranno ruoli definiti in maniera specifica. Qualora i server dell'organizzazione non corrispondano a questi ruoli, o qualora si disponga di server che svolgono più ruoli, utilizzare le impostazioni definite nella presente pubblicazione come linee guida per la creazione di modelli di protezione specifici per l'organizzazione. Si consiglia, però, di tenere presente che quanto più è elevato il numero di funzioni che ciascun server svolge, tanto più quest'ultimo risulterà vulnerabile a eventuali attacchi.
  
Nella seguente figura si illustra un esempio della progettazione OU finale in grado di supportare adeguatamente i ruoli server definiti.
  
[![](images/Cc163110.sgfg0203(it-it,TechNet.10).gif "Figura 2.3. Esempio di progettazione OU")](https://technet.microsoft.com/it-it/cc163110.sgfg0202_big(it-it,technet.10).gif)
  
**Figura 2.3. Esempio di progettazione OU**
  
#### Progettazione di OU, GPO e gruppi amministrativi
  
Le OU e i criteri consigliati discussi nella sezione precedente creano una linea di base o un nuovo ambiente per ristrutturare la struttura OU già presente nell'organizzazione per i computer con Windows Server 2003. Gli amministratori utilizzano i propri limiti di amministrazione predefiniti per creare i rispettivi gruppi amministrativi. La correlazione di questi gruppi con le unità organizzative che gestiscono è illustrata nella seguente tabella.
  
**Tabella 2.2. OU e Gruppi amministrativi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome OU</th>
<th style="border:1px solid black;" >Gruppo amministrativo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Controller di dominio</td>
<td style="border:1px solid black;">Progettazione di domini</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Server membri</td>
<td style="border:1px solid black;">Progettazione di domini</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Infrastruttura</td>
<td style="border:1px solid black;">Amministratori dell'infrastruttura</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">File</td>
<td style="border:1px solid black;">Amministratori dell'infrastruttura</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">File di stampa</td>
<td style="border:1px solid black;">Amministratori dell'infrastruttura</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IAS</td>
<td style="border:1px solid black;">Progettazione di domini</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Web</td>
<td style="border:1px solid black;">Servizi Web</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CA</td>
<td style="border:1px solid black;">Amministratori dell'organizzazione</td>
</tr>
</tbody>
</table>
  
Ogni gruppo amministrativo è stato creato come gruppo globale entro il dominio dai membri di **Progettazione di domini**, che sono responsabili per l'infrastruttura Active Directory e la protezione. Essi hanno utilizzato il GPO corrispondente per aggiungere ciascuno di questi gruppi amministrativi al gruppo con restrizioni appropriato. I gruppi amministrativi elencati nella tabella saranno membri solo del gruppo **Amministratori locali** per i computer situati nelle OU che contengono in modo specifico i computer relativi alle loro funzioni di lavoro.
  
E per finire, i membri di **Progettazione di domini** impostano le autorizzazioni per ogni oggetto Criteri di gruppo in modo che solo gli amministratori appartenenti al gruppo siano in grado di modificarle.
  
Notare che la creazione e la configurazione di questi gruppi fa parte del processo di progettazione e implementazione generale di Active Directory. Esso non è trattato in questa guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Panoramica del processo
  
Questa guida riunisce in sé i punti di forza dei metodi basati su SCW e sui criteri di gruppo. Questo metodo ibrido permette di creare e verificare più facilmente le configurazioni della protezione, pur fornendo la flessibilità e la scalabilità necessaria nelle reti di Windows di grandi dimensioni.
  
Il processo utilizzato per creare, verificare e implementare i criteri è il seguente:
  
1.  Creare l'ambiente Active Directory, comprendendo gruppi e OU. Creare anche i gruppi amministrativi appropriati e delegare le autorizzazioni OU ai gruppi corrispondenti.
  
2.  Configurare la sincronizzazione sul controller di dominio che ospita l'FSMO dell'emulatore PDC.
  
3.  Configurare i criteri di dominio.
  
4.  Creare i criteri di base con SCW.
  
5.  Verificare i criteri di base con SCW.
  
6.  Convertire i criteri di base in GPO e collegarli al GPO appropriato.
  
7.  Creare i criteri per il ruolo con SCW e i modelli di protezione allegati.
  
8.  Verificare i criteri per il ruolo con SCW.
  
9.  Convertire i criteri di base in GPO e collegarli ai GPO appropriati.
  
Le sezioni indicate di seguito descrivono dettagliatamente queste fasi.
  
**Nota**: per maggiore semplicità, gli esempi in questa sezione presumono l'utilizzo dell'ambiente client di organizzazione (EC). Se si utilizza uno degli altri due ambienti, sostituire i nomi dei file appropriati. Le differenze tra i tre ambienti e la loro funzionalità sono discusse nel Capitolo 1, "Presentazione della guida per la protezione di Windows  Server 2003".
  
#### Creare l'ambiente Active Directory
  
Prima di poter avviare il processo di aumento della protezione, è necessario avere approntato un dominio Active Directory e una struttura OU. La seguente procedura elenca le fasi da seguire per creare le OU e i gruppi utilizzati in questa guida e per configurarli per il corretto accesso amministrativo.
  
1.  Aprire lo Snap-in MMC utenti e computer di Active Directory (Dsa.msc).
  
2.  Nella Directory principale dell'oggetto dominio, creare un'OU denominata Server membri.
  
3.  Navigare fino a questa nuova OU e creare al suo interno un'OU figlio denominata Infrastruttura.
  
4.  Spostare tutti i server WINS e DHCP nella OU Infrastruttura.
  
5.  Creare un gruppo di protezione globale denominato **Amministratori dell'infrastruttura** e aggiungere gli account di dominio pertinenti.
  
6.  Eseguire la Delega guidata del controllo per fornire al gruppo **Amministratori dell'infrastruttura** il controllo totale della OU.
  
7.  Ripetere i punti dal 3 al 6 per il file server, il server di stampa, il server Web, il server IAS e i ruoli di server dei Servizi certificati. Utilizzare le informazioni nella Tabella 2.2 per i nomi OU e di gruppo pertinenti.
  
#### Configurazione della sincronizzazione degli orologi
  
La seguente procedura consente di sincronizzare con un'origine ora esterna. i controller di dominio e i server membro. Questa sincronizzazione aiuterà a garantire che l'autenticazione Kerberos funzioni correttamente e consenta di mantenere sincronizzato il dominio Active Directory con qualunque altro computer esterno.
  
1.  Sul controller di dominio con l'FSMO dell'emulatore PDC, aprire un prompt dei comandi ed eseguire il seguente comando, dove *&lt;PeerList&gt;* è un elenco di nomi DNS o di indirizzi IP separati da virgola per le origini dell'ora desiderate:
  
    <codesnippet language displaylanguage containsmarkup="false">w32tm /config /syncfromflags:manual /manualpeerlist:&lt;PeerList&gt;  
```
  
2.  Per aggiornare la configurazione, eseguire il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">w32tm /config /update  
```
  
3.  Controllare il registro eventi. Se il computer non è in grado di raggiungere i server, la procedura non ha esito positivo e viene inserita una voce nel registro eventi.
  
In genere, la procedura descritta viene utilizzata per sincronizzare l'origine ora autorevole della rete interna con un'origine ora esterna molto precisa. Può essere però eseguita su qualsiasi computer che abbia come sistema operativo Windows XP o un membro della famiglia Windows Server 2003. In molti casi, può non essere necessario che l'ora di tutti i server sia sincronizzata con un'origine esterna, purché però sia sincronizzata con la stessa origine interna. Per impostazione predefinita, i computer membri sincronizzano sempre i loro orologi con i controller di dominio.
  
**Nota**: per un'analisi di registro accurata, si devono sincronizzare anche gli orologi dei computer di rete con sistemi operativi diversi da Windows in base all'emulatore PDC di Windows Server 2003 o alla medesima origine ora di quel server.
  
#### Configurazione dei Criteri di dominio
  
La procedura seguente consente di importare i modelli di protezione inclusi in questa guida per il criterio a livello di dominio. Questo criterio è fornito come modello di protezione, dato che SCW non si occupa di criteri a livello di dominio. Prima di implementare la seguente procedura, posizionare sul computer il file specifico del criterio (.inf).
  
**Avviso**: i modelli di protezione illustrati in questa guida sono stati progettati per incrementare il livello di protezione dell'ambiente in uso. È possibile che la loro installazione possa causare la perdita di parte delle funzionalità nell'ambiente in uso e che delle applicazioni critiche possano non funzionare.
  
Pertanto è **essenziale** verificare accuratamente queste impostazioni prima di implementarle in un ambiente di produzione Occorre inoltre eseguire il backup di ogni controller di dominio e server dell'ambiente prima di applicare qualsiasi nuova impostazione di protezione. Verificare che lo stato del sistema sia incluso nel backup, che permetterà il ripristino, se necessario, delle impostazioni di registro e degli oggetti Active Directory.
  
**Importazione dei modelli di protezione dei criteri di dominio**
  
1.  In utenti e computer di Active Directory fare clic con il pulsante destro del mouse sul dominio, quindi scegliere **Proprietà**.
  
2.  Nella scheda **Criteri di gruppo,** fare clic su **Nuovo** per aggiungere un nuovo oggetto Criteri di gruppo.
  
3.  Digitare **Criterio EC-Domain** e premere INVIO.
  
4.  Fare clic con il pulsante destro del mouse su **Criterio EC-Domain** e scegliere **Non sovrascrivere**.
  
5.  Selezionare **Criterio EC-Domain** e poi fare clic su **Modifica.**
  
6.  Nella finestra Editor oggetto Criteri di gruppo, fare clic su **Computer Configuration\\Windows Settings**. Fare clic con il pulsante destro del mouse su **Impostazioni di protezione**, quindi fare clic su **Importa criterio**.
  
7.  Nella finestra di dialogo **Importa criterio da** passare alla cartella "**\\Tools and Templates\\Security Guide\\Security Templates**" e poi fare doppio clic su **EC-Domain.inf**.
  
8.  Chiudere i Criteri di gruppo modificati.
  
9.  Chiudere la finestra **Proprietà** del dominio.
  
10. Se non si desidera attendere l'applicazione Criteri di gruppo pianificata, è possibile avviare manualmente il processo. Per farlo:
  
    -   Aprire un prompt dei comandi, digitare **gpupdate /Force** e premere INVIO.
  
11. Controllare nel registro eventi che i criteri di gruppo siano stati scaricati e che il server sia in grado di comunicare con gli altri controller di dominio all'interno del dominio.
  
**Avviso**: quando si creano i criteri di dominio relativi al client dell'organizzazione, assicurarsi che sia stata attivata l'opzione **Non sovrascrivere** per applicare i suddetti criteri in tutto il dominio. Si tratta dell'unico tipo di criteri di gruppo tra quelli trattati in questa guida in cui l'opzione **Non sovrascrivere** deve essere attivata. Non attivare mai questa opzione negli altri criteri di gruppo specificati in questa guida. Si consiglia, inoltre, di non modificare i criteri di dominio predefiniti di Windows Server 2003, in caso si presenti la necessità di ripristinare le impostazioni predefinite.
  
Per assicurarsi che questo nuovo criterio abbia la precedenza su quello predefinito, posizionarlo in modo da assegnargli la priorità più alta tra i collegamenti GPO.
  
**Importante**: importare questi criteri di gruppo in tutti i domini aggiuntivi nell'organizzazione per assicurare l'applicazione costante del criterio di password. Non è tuttavia raro imbattersi in ambienti in cui il criterio password del dominio principale presenta restrizioni più rigide che per qualsiasi altro dominio. Si consiglia anche di accertarsi che tutti gli altri domini che utilizzeranno questo stesso criterio dispongano degli stessi requisiti aziendali. Poiché il criterio password può essere impostato solo a livello di dominio, è possibile che a causa di determinati requisiti aziendali o legali alcuni utenti vengano inclusi in un dominio separato semplicemente per poter imporre a tale gruppo un criterio password più rigoroso.
  
**Deselezione dell'opzione Consenti propagazione delle autorizzazioni.**
  
Per impostazione predefinita, la nuova struttura OU eredita molte impostazioni di protezione dal contenitore padre. Per ogni OU, deselezionare la casella di controllo per **Consenti propagazione delle autorizzazioni ereditabili dall'oggetto padre a questo oggetto e a tutti gli oggetti figlio.**
  
1.  Aprire utenti e computer di Active Directory.
  
2.  Fare clic su **Visualizza** e quindi su **Caratteristiche avanzate** per scegliere la visualizzazione avanzata.
  
3.  Fare clic con il pulsante destro del mouse sull'unità organizzativa appropriata, quindi selezionare **Proprietà.**
  
4.  Selezionare la scheda **Protezione**, quindi fare clic sul pulsante **Avanzate**.
  
5.  Deselezionare la casella di controllo **Consenti propagazione delle autorizzazioni ereditabili dall'oggetto padre a questo oggetto e a tutti gli oggetti figlio. Casella di controllo Aggiungi tali autorizzazioni a quelle qui specificate.**
  
Rimuovere tutti i gruppi superflui precedentemente aggiunti dagli amministratori, quindi aggiungere il gruppo di dominio corrispondente a ciascuna unità organizzativa di ruoli server. Mantenere l'impostazione **Controllo completo** per il gruppo **Amministratori di dominio**.
  
#### Creare i criteri di base manualmente usando SCW
  
La fase successiva consiste nell'utilizzare SCW per creare il criterio di base del server membro.
  
Per iniziare il lavoro di configurazione, in modo da garantire che non vi siano impostazioni o software legacy di configurazioni precedenti, utilizzare un'installazione nuova del sistema operativo. Per garantire la massima compatibilità, utilizzare, se possibile, un hardware simile a quello usato in fase di implementazione. L'installazione nuova è chiamata *computer di riferimento.*
  
Durante le fasi di creazione del criterio di base del server membro (MSBP), tenere presente che si elimina il ruolo di File server dall'elenco di ruoli rilevati. Questo ruolo è comunemente configurato sui server che non lo richiedono e potrebbe essere considerato un rischio di protezione. Per abilitare il ruolo di File server per i server che lo richiedono, è possibile applicare successivamente un secondo criterio nel corso di questo processo.
  
**Creazione di criteri di base dei server membro (MSBP, Member Server Baseline Policy).**
  
1.  Creare una nuova installazione di Windows Server 2003 con SP1 su un computer di riferimento nuovo.
  
2.  Installare il componente di Configurazione guidata impostazioni di sicurezza (SCW) sul computer tramite il Pannello di controllo, Aggiungi/rimuovi programmi, Aggiungi/rimuovi componenti di Windows.
  
3.  Aggiungere il computer al dominio.
  
4.  Installare soltanto le applicazioni obbligatorie che dovrebbero essere presenti su ogni server dell'ambiente in uso. Gli esempi contengono agenti di software e di gestione, agenti di backup su nastro e le utilità antivirus o antispyware.
  
5.  Lanciare SCW, selezionare **Crea il nuovo criterio** e scegliere il computer di riferimento.
  
6.  Rimuovere il ruolo di File server dall'elenco di ruoli rilevati.
  
7.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
8.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
9.  Assicurarsi che tutti i servizi aggiuntivi richiesti per l'implementazione di base, come agenti di backup o software antivirus, siano rilevati.
  
10. Decidere come gestire i servizi non specificati nell'ambiente in uso. Per una maggior protezione, è possibile configurare questa impostazione di criterio su **Disabilita**. Verificare questa configurazione prima di implementarla nella rete di produzione, in quanto potrebbe causare problemi se i server di produzione eseguono servizi aggiuntivi che non sono duplicati sul computer di riferimento.
  
11. Riesaminare le impostazioni di rete e accertarsi che le porte e le applicazioni appropriate siano state rilevate e che saranno configurate come eccezioni per Windows Firewall.
  
12. Ignorare la sezione "Impostazioni di Registro".
  
13. Ignorare la sezione "Criterio di controllo".
  
14. Allegare il modello di protezione idoneo (ad esempio EC-Member Server Baseline.inf).
  
15. Salvare il criterio con un nome idoneo (ad esempio, Member Server Baseline.xml).
  
**Creazione del criterio Controller di dominio**
  
Si deve usare un computer configurato come controller di dominio per creare il criterio di Controller di dominio. È possibile utilizzare un controller di dominio esistente o creare un computer di riferimento e utilizzare lo strumento Dcpromo per trasformare il computer in un controller di dominio. Tuttavia, la maggior parte delle organizzazioni non vuole aggiungere un controller di dominio al proprio ambiente di produzione perché può violare i loro criteri di protezione. Se si utilizza un controller di dominio esistente, fare attenzione a non applicarvi nessuna impostazione con SCW o a non modificarne la configurazione.
  
1.  Installare il componente di Configurazione guidata impostazioni di sicurezza (SCW) sul computer tramite il Pannello di controllo, Aggiungi/rimuovi programmi, Aggiungi/rimuovi componenti di Windows.
  
2.  Installare soltanto le applicazioni obbligatorie che dovrebbero essere presenti su ogni server dell'ambiente in uso. Gli esempi contengono agenti di software e di gestione, agenti di backup su nastro e le utilità antivirus o antispyware.
  
3.  Lanciare la SCW GUI, selezionare **Crea il nuovo criterio**, e scegliere il computer di riferimento.
  
4.  Accertarsi che le funzionalità client rilevate siano idonee all'ambiente in uso.
  
5.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
6.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
7.  Assicurarsi che tutti i servizi aggiuntivi richiesti per l'implementazione di base, come agenti di backup o software antivirus, siano rilevati.
  
8.  Decidere come gestire i servizi non specificati nell'ambiente in uso. Per una maggior protezione, è possibile configurare questa impostazione di criterio su **Disattiva.** Verificare questa configurazione prima di implementarla nella rete di produzione, in quanto potrebbe causare problemi se i server di produzione eseguono servizi aggiuntivi che non sono duplicati sul computer di riferimento.
  
9.  Riesaminare le impostazioni di rete e accertarsi che le porte e le applicazioni appropriate siano state rilevate e che saranno configurate come eccezioni per Windows Firewall.
  
10. Ignorare la sezione "Impostazioni di Registro".
  
11. Ignorare la sezione "Criterio di controllo".
  
12. Allegare il modello di protezione idoneo (ad esempio, EC-Domain Controller.inf).
  
13. Salvare il criterio con un nome idoneo (ad esempio, Domain Controller.xml).
  
#### Verificare i criteri di base con SCW.
  
Dopo aver creato e salvato i criteri di base, Microsoft consiglia vivamente di implementarli nell'ambiente di prova. Idealmente, i server di prova avranno la medesima configurazione di hardware e software dei server di produzione. Questo approccio consentirà di trovare e riparare potenziali problemi, come la presenza di servizi imprevisti richiesti da specifiche periferiche hardware.
  
Per verificare i criteri sono disponibili due opzioni. È possibile utilizzare le funzionalità di sviluppo SCW native, o implementare i criteri tramite un GPO.
  
Quando si iniziano a creare i criteri, prendere in considerazione l'utilizzo di funzionalità di sviluppo SCW native. È possibile utilizzare SCW per inviare criteri a un unico server alla volta, oppure Scwcmd per inviare i criteri a un gruppo di server. Il metodo di sviluppo nativo offre la possibilità di rieseguire facilmente i criteri utilizzati dallo SCW. Questa funzionalità può essere molto utile quando, durante il processo di prova, si apportano modifiche multiple ai criteri.
  
I criteri vengono verificati per accertarsi che la loro applicazione a server di destinazione non ne comprometta le funzioni critiche. Dopo aver applicato le modifiche alla configurazione, è necessario iniziare a verificare la funzionalità di base del computer. Per esempio, se il server è configurato come un'autorità di certificazione (CA), accertarsi che i client possano richiedere e ottenere dei certificati, scaricare un elenco di revoche di certificati e così via.
  
Quando si è certi delle proprie configurazioni di criterio, è possibile utilizzare Scwcmd come mostrato nella seguente procedura per convertire i criteri in GPO.
  
Per ulteriori dettagli su come verificare i criteri SCW, consultare la "[Guida di sviluppo per la configurazione guidata delle impostazioni di sicurezza](http://technet.microsoft.com/en-us/library/cc776871.aspx)"* *all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/  
library/SCWDeploying/5254f8cd-143e-4559-a299-9c723b366946.mspx* *e la versione scaricabile di [Documentazione di configurazione guidata impostazioni di sicurezza](http://go.microsoft.com/fwlink/?linkid=43450) all'indirizzo http://go.microsoft.com/fwlink/?linkid=43450.
  
#### Conversione dei Criteri di base in GPO
  
Dopo aver verificato a fondo i criteri di base, completare le seguenti fasi per trasformarli in GPO e collegarli alle OU appropriate:
  
1.  Al prompt dei comandi digitare quanto segue:
  
    <codesnippet language displaylanguage containsmarkup="false">scwcmd transform /p:&lt;PathToPolicy.xml&gt; /g:&lt;GPODisplayName&gt;  
```
  
    e premere INVIO. Ad esempio:
  
    <codesnippet language displaylanguage containsmarkup="false">scwcmd transform /p:"C:\\Windows\\Security\\msscw\\Policies\\Infrastructure.xml" /g:"Infrastructure Policy"  
```
  
    **Nota**: le informazioni che devono essere inserite al prompt dei comandi occupano qui più di una riga a causa delle limitazioni del display. Queste informazioni dovrebbero essere inserite tutte su una riga.
  
2.  Utilizzare la Console di gestione Criteri di gruppo per collegare il GPO appena creato all'unità operativa adeguata.
  
Se il file dei criteri di protezione di SCW contiene le impostazioni di Windows Firewall, Windows Firewall dovrà essere attivo sul computer locale, affinché questa procedura possa essere completata con successo. Per verificare che Windows Firewall sia attivo, aprire il Pannello di controllo e fare doppio clic su **Windows Firewall**.
  
Eseguire ora una prova finale per accertarsi che il GPO applichi le impostazioni desiderate. Per completare questa procedura, confermare sia l'esecuzione delle impostazioni appropriate sia l'integrità della funzionalità.
  
#### Creazione dei Criteri per il ruolo utilizzando SCW
  
La successiva fase consiste nell'utilizzare SCW per creare i criteri per il ruolo di ciascun server.
  
Le fasi per creare i criteri specifici per i ruoli sono simili a quelle seguite per la creazione di MSBP. Usare nuovamente un computer di riferimento in modo da garantire che non vi siano impostazioni o software legacy di configurazioni precedenti.
  
**Creazione dei criteri per i ruoli**
  
1.  Creare una nuova installazione di Windows Server 2003 con SP1 su un computer di riferimento nuovo.
  
2.  Installare il componente di Configurazione guidata impostazioni di sicurezza (SCW) sul computer tramite il Pannello di controllo, Aggiungi/rimuovi programmi, Aggiungi/rimuovi componenti di Windows.
  
3.  Aggiungere il nuovo server al dominio.
  
4.  Installare soltanto le applicazioni obbligatorie che dovrebbero essere presenti su ogni server dell'ambiente in uso. Gli esempi contengono agenti di software e di gestione, agenti di backup su nastro e le utilità antivirus o antispyware.
  
5.  Configurare i ruoli appropriati per il computer. Per esempio, se i server di destinazione eseguono DHCP e WINS, installare quei componenti. Anche se non devono essere configurati esattamente come i server utilizzati, è comunque necessario installare i ruoli.
  
6.  Lanciare SCW.
  
7.  Selezionare **Crea il nuovo criterio** e scegliere il computer di riferimento.
  
8.  Accertarsi che le funzionalità client rilevate siano idonee all'ambiente in uso.
  
9.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
10. Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
11. Assicurarsi che tutti i servizi aggiuntivi richiesti per l'implementazione di base, come agenti di backup o software antivirus, siano rilevati.
  
12. Decidere come gestire i servizi non specificati nell'ambiente in uso. Per ottenere una maggior protezione (e una funzionalità ridotta) è possibile configurare configurare questa impostazione di criterio su **Disabilita**, che disabiliterà qualsiasi servizio nuovo non esplicitamente consentito tramite SCW. Verificare questa configurazione prima di implementarla nella rete di produzione, in quanto potrebbe causare problemi se i server di produzione eseguono servizi aggiuntivi che non sono duplicati sul computer di riferimento.
  
13. Confermare tutte le modifiche di servizio elencate.
  
14. Riesaminare le impostazioni di rete e accertarsi che SCW abbia rilevato le porte e le applicazioni appropriate da configurare quali eccezioni per Windows Firewall.
  
15. Ignorare la sezione "Impostazioni di Registro".
  
16. Ignorare la sezione "Criterio di controllo".
  
17. Se il server è configurato con il ruolo di server Web, completare le fasi nella sezione “Internet Information Services (IIS)” per accertarsi che SCW sia configurato per supportare le funzionalità IIS necessarie.
  
18. Fare clic su **Includi modelli di protezione** per aggiungere il modello di protezione idoneo.
  
19. Salvare il criterio con un nome idoneo.
  
#### Creazione di Criteri per il ruolo utilizzando SCW
  
Come per i criteri di base, ci sono due modi diversi di verificare i criteri. È possibile utilizzare le funzionalità di sviluppo SCW native, o implementare i criteri tramite GPO. Anche in questo caso, Microsoft raccomanda vivamente di implementare i criteri per il ruolo in un ambiente di prova prima di utilizzarli in produzione. Questo metodo serve a ridurre al minimo i tempi di inattività e i guasti nell'ambiente di produzione. Dopo aver verificato a fondo la nuova configurazione, è possibile convertire i criteri in GPO come illustrato nella seguente procedura e applicarli all'OU idonea.
  
#### Conversione dei Criteri per il ruolo in GPO
  
Dopo aver verificato a fondo i criteri per il ruolo, completare le seguenti fasi per trasformarli in GPO e collegarli alle OU appropriate:
  
1.  Al prompt dei comandi digitare quanto segue:
  
    <codesnippet language displaylanguage containsmarkup="false">scwcmd transform /p:&lt;PathToPolicy.xml&gt; /g:&lt;GPODisplayName&gt;  
```
  
    e premere INVIO. Ad esempio:
  
    <codesnippet language displaylanguage containsmarkup="false">scwcmd transform /p:"C:\\Windows\\Security\\msscw\\Policies\\Infrastructure.xml" /g:"Infrastructure Policy"  
```
  
    **Nota**: le informazioni che devono essere inserite al prompt dei comandi occupano qui più di una riga a causa delle limitazioni del display. Queste informazioni dovrebbero essere inserite tutte su una riga.
  
2.  Utilizzare la Console di gestione criteri di gruppo per collegare il GPO appena creato all'OU appropriata e assicurarsi di spostarlo sopra al criterio dei controller di dominio predefiniti in modo che riceva la massima priorità.
  
Se il file dei criteri di protezione di SCW contiene le impostazioni di Windows Firewall, Windows Firewall dovrà essere attivo sul computer locale, affinché questa procedura possa essere completata con successo. Per verificare che Windows Firewall sia attivo, aprire il Pannello di controllo e fare doppio clic su Windows Firewall.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Gli amministratori di protezione hanno bisogno di capire i punti forti e quelli deboli di SCW rispetto ai metodi tradizionali di aumento della protezione basati sui criteri di gruppo in modo da poter scegliere la corretta metodologia per l'ambiente in uso. SCW e i criteri di gruppo possono essere utilizzati insieme per poter riprodurre in modo rapido e costante i criteri forniti da SCW unitamente alla distribuzione scalabile e alle funzionalità di gestione dei criteri di gruppo.
  
Entrano in gioco parecchie considerazioni di progettazione quando si rivede la progettazione di insiemi di strutture, domini e OU per proteggere un ambiente.
  
È importante individuare e documentare eventuali esigenze dell'organizzazione riguardo all'autonomia e all'isolamento dei servizi. L'autonomia politica, l'isolamento operativo e l'indipendenza legale o normativa costituiscono motivi validi per valutare la progettazione di insiemi di strutture complessi.
  
È importante comprendere come controllare gli amministratori di servizi. Un amministratore di servizi malintenzionato può costituire un rischio notevole per un'organizzazione. Al livello più basso, gli amministratori di dominio malintenzionati possono accedere ai dati presenti in qualsiasi dominio dell'insieme di strutture.
  
Sebbene possa risultare difficile modificare la progettazione di un insieme di strutture o di un dominio in un'organizzazione, in alcuni casi risulta indispensabile per arginare rischi specifici per la protezione. È altrettanto importante pianificare l'implementazione di unità organizzative nell'organizzazione in base alle esigenze sia degli amministratori di servizi sia degli amministratori di dati. Questo capitolo ha fornito informazioni dettagliate su come creare un modello OU che promuova l'uso di GPO per la gestione continua di ruoli di server diversi nell'organizzazione.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono informazioni aggiuntive sulla protezione avanzata dei server che eseguono Windows Server 2003 con SP1.
  
-   Per ulteriori informazioni sulla protezione e la privacy in ambito Microsoft, vedere la pagina [Sistemi informatici attendibili: protezione](http://www.microsoft.com/mscorp/twc/default.mspx) all'indirizzo www.microsoft.com/scora/tac/default.msp.
  
-   Per delle linee guida valide sulla protezione, vedere “[10 regole fondamentali della protezione](http://www.microsoft.com/technet/archive/community/columns/security/essays/10imlaws.mspx)” all'indirizzo www.microsoft.com/technet/archive/community/columns/security/essays/10imlaws.msp.
  
-   Per istruzioni su come proteggere il database Active Directory, vedere “[Best Practice Guide for Securing Active Directory Installations](http://www.microsoft.com/downloads/details.aspx?familyid=4e734065-3f18-488a-be1e-f03390ec5f91&displaylang=en)” all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyID=4e734065-3f18-488a-be1e-f03390ec5f91&.
  
-   Per informazioni su considerazioni relative alla progettazione di Active Directory, vedere “[Design Considerations for Delegation of Administration in Active Directory](http://www.microsoft.com/technet/prodtechnol/windows2000serv/technologies/activedirectory/plan/addeladm.mspx)” all'indirizzo www.microsoft.com/technet/prodtechnol/windows2000serv/  
    technologies/activedirectory/plan/addeladm.msp.
  
-   Per informazioni su come configurare un server di riferimento per l'ora, vedere l'articolo della Microsoft Knowledge Base "[Come configurare un server di riferimento orario di fiducia in Windows 2000](http://support.microsoft.com/kb/216734/it)" all'indirizzo http://support.microsoft.com/kb/216734/it.
  
-   Per informazioni sulle porte di rete usate dalle applicazioni Microsoft, vedere l'articolo della Microsoft Knowledge Base "[Panoramica dei servizi e requisiti per le porte di rete per il sistema server Windows](http://support.microsoft.com/kb/832017/it/it)" all'indirizzo http://support.microsoft.com/kb/832017/it/it.
  
-   Per le informazioni sulla delega di autorizzazioni di Active Directory, vedere "[Best Practices for Delegating Active Directory Administration](http://www.microsoft.com/downloads/details.aspx?familyid=631747a3-79e1-48fa-9730-dae7c0a1d6d3&displaylang=en)” all'indirizzo http://www.microsoft.com/technet/prodtechnol/windowsserver2003  
    /technologies/activedirectory/actdid1.mspx .
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)
