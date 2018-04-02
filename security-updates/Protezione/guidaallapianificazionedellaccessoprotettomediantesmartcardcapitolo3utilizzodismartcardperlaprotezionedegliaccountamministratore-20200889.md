---
TOCTitle: 'Guida alla pianificazione dell''accesso protetto mediante smart card - Capitolo 3 -Utilizzo di smart card per la protezione degli account amministratore'
Title: 'Guida alla pianificazione dell''accesso protetto mediante smart card - Capitolo 3 -Utilizzo di smart card per la protezione degli account amministratore'
ms:assetid: '86fdfba1-4929-4279-99e4-903367b98ee0'
ms:contentKeyID: 20200889
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536290(v=TechNet.10)'
---

Guida alla pianificazione dell'accesso protetto mediante smart card
===================================================================

### Capitolo 3 -Utilizzo di smart card per la protezione degli account amministratore

Aggiornato: 25/5/2005

Microsoft® Windows Server™ 2003 consente alle organizzazioni di proteggere gli account amministrativi attraverso una serie di funzionalità specifiche di protezione degli account. Oltre al requisito in base al quale gli amministratori devono eseguire l'accesso con smart card, Windows Server 2003 supporta l'autenticazione mediante smart card con le operazioni secondarie di seguito elencate:

-   Creazione di un'unità mappata mediante il comando **net use**.

-   Utilizzo del servizio Accesso secondario digitando **runas** nel prompt dei comandi.

-   Installazione del servizio directory Active Directory® utilizzando l'Installazione guidata di Active Directory (a cui è possibile accedere digitando **dcpromo** nel prompt dei comandi).

-   Accesso tramite sessioni di Desktop remoto di Windows Server 2003.

-   Accesso tramite sessioni di Terminal Server di Windows Server 2003.

**Nota:** Sebbene Microsoft Windows® 2000 supporti l'accesso con smart card per l'autenticazione, non supporta tali funzionalità aggiuntive, che sono disponibili unicamente in Windows Server 2003.

##### In questa pagina

[](#ecaa)[Approcci alla protezione degli account amministratore mediante smart card](#ecaa)
[](#ebaa)[Problemi e requisiti](#ebaa)
[](#eaaa)[Progettazione della soluzione](#eaaa)

### Approcci alla protezione degli account amministratore mediante smart card

Il supporto di Windows Server 2003 dell'autenticazione mediante smart card di operazioni secondarie consente un migliore isolamento degli account utente e amministratore. Per le operazioni quotidiane, gli amministratori possono accedere alle workstation con account non amministrativi. Nel caso debbano eseguire un'attività amministrativa, possono utilizzare le proprie smart card per autenticare l'operazione mediante un'operazione secondaria. Si tratta di un metodo più sicuro e agevole rispetto alla procedura in base alla quale viene richiesto all'amministratore di immettere un nome utente e una password oppure di disconnettersi ed eseguire nuovamente l'accesso con un account amministratore.

#### Identificazione degli account amministratore e dei gruppi

L'implementazione di smart card per gli amministratori richiede che un'organizzazione identifichi gli account amministratore che necessitano di autenticazione a due fattori. Al fine di eseguire correttamente questo passaggio, è necessario conoscere le caratteristiche dei vari gruppi e account amministratore all'interno di Windows XP e Windows Server 2003.

I gruppi consentono agli amministratori di gestire diversi account utente contemporaneamente. Microsoft Windows NT® e i sistemi operativi successivi includono gruppi di protezione con diritti amministrativi incorporati.

Tali gruppi di protezione possono essere gruppi locali (su computer aggiunti al dominio quali workstation e server membri) oppure gruppi predefiniti (su controller di dominio). Gli account amministratore ricevono i privilegi attraverso l'appartenenza a uno o più dei suddetti gruppi di protezione.

##### Gruppi locali

I gruppi locali su computer aggiunti al dominio hanno vari livelli di diritti amministrativi. Ad esempio:

-   **Administrators**. I membri di questo gruppo hanno il controllo completo del computer locale. Per impostazione predefinita, l'account utente Administrator è membro di questo gruppo. Se il computer è membro di un dominio, il gruppo Domain Admins di tale dominio è anch'esso membro di questo gruppo.

-   **Backup Operators (tutti i tipi di computer)**. I membri di questo gruppo possono eludere le autorizzazioni del file system NTFS per eseguire il backup di file e cartelle. I membri del gruppo Backup Operators hanno inoltre il diritto di arrestare i server membri.

-   **Power Users**. I membri di questo gruppo hanno diritti amministrativi limitati sulle risorse di una workstation locale o di un server membro. Possono inoltre arrestare un server membro.

-   **Print Operators**. I membri di questo gruppo possono gestire server di stampa, stampanti e processi di stampa. Possono inoltre arrestare un server membro.

Per una descrizione dettagliata dei gruppi predefiniti in Windows Server 2003, vedere l'argomento [Default Local Groups](http://technet.microsoft.com/en-us/library/cc785098.aspx) all'indirizzo www.microsoft.com/resources/documentation/WindowsServ/2003/standard/proddocs/en-us/lsm\_local\_groups.asp.

È opportuno che i criteri di protezione dell'organizzazione definiscano quali membri dei gruppi Administrators, Server Operators e Power Users necessitano di smart card per l'accesso e l'amministrazione.

##### Gruppi predefiniti

Ogni dominio possiede un determinato numero di gruppi predefiniti che garantiscono funzioni amministrative sui controller di dominio. Tali gruppi includono:

-   **Administrators**. I membri di questo gruppo hanno il controllo amministrativo completo sui controller di dominio. Per impostazione predefinita, l'account Administrator e il gruppo Domain Admins sono membri di questo gruppo.

-   **Backup Operators**. I membri di questo gruppo possono eludere le autorizzazioni del file system NTFS per eseguire il backup di file e cartelle. I membri del gruppo Backup Operators possono inoltre eseguire l'accesso locale e arrestare i controller di dominio.

-   **Server Operators**. Questo gruppo ha diritti amministrativi limitati sui controller di dominio, analogamente al gruppo Power Users per quanto riguarda le workstation. I membri del gruppo Server Operators possono eseguire l'accesso locale e arrestare i controller di dominio.

-   **Print Operators**. I membri di questo gruppo gestiscono server di stampa, stampanti e processi di stampa. Possono inoltre eseguire l'accesso locale e arrestare i controller di dominio.

-   **Account Operators**.** **I membri di questo gruppo hanno diritti limitati per la gestione di account utente e gruppi. Possono accedere in modalità interattiva ma non possono arrestare i controller di dominio.

Per ulteriori informazioni sui gruppi predefiniti, vedere l'argomento [Default groups](http://technet.microsoft.com/en-us/library/cc756898.aspx) all'indirizzo www.microsoft.com/resources/documentation/WindowsServ/2003/standard/proddocs/en-us/sag\_ADgroups\_9builtin\_intro.asp.

È opportuno che i criteri dell'organizzazione specifichino che tutti i membri di questi gruppi necessitano di smart card per l'amministrazione.

##### Gruppi predefiniti del dominio e degli insiemi di strutture

Oltre ai gruppi predefiniti, la creazione di un insieme di strutture di Active Directory consente la configurazione dei seguenti gruppi di protezione:

-   **Domain Admins**. I membri di questo gruppo hanno il controllo completo su tutti gli oggetti del dominio. Ogni dominio successivo nell'insieme di strutture possiede anche un gruppo Domain Admins.

-   **Enterprise Admins (solo domini principali degli insiemi di strutture)**.** **I membri di questo gruppo hanno il controllo completo su tutti gli oggetti dell'insieme di strutture.

-   **Schema Admins (solo domini principali degli insiemi di strutture)**. I membri di questo gruppo possono creare classi e attributi nello schema, nonché gestire il master operazioni schema.

    **Nota:** per incrementare il livello di protezione, mantenere al minimo l'appartenenza a questi tre gruppi.

Tutti i membri di questi gruppi dovrebbero necessitare di smart card per l'amministrazione.

#### Come rendere necessaria la smart card per l'accesso interattivo

Esistono due metodi per rendere necessario l'uso di una smart card per l'accesso interattivo. È possibile configurare:

-   Le proprietà degli account utente in Utenti e computer di Active Directory.

-   Le impostazioni Criteri di gruppo per computer specifici o per gruppi di computer specifici.

Nella maggior parte degli ambienti, il metodo più gestibile consiste nell'utilizzo delle impostazioni Criteri di gruppo.

##### Proprietà degli account utente    

È possibile configurare qualunque account utente in modo che richieda una smart card per l'accesso interattivo. A tale scopo, in Utenti e computer di Active Directory, fare doppio clic sull'utente, scegliere la scheda **Account**, in **Opzioni account**, selezionare la casella di controllo **Per l'accesso interattivo è necessaria una smart card**. Selezionando questa opzione, si sostituisce la password dell'utente con un valore casuale complesso e si imposta la proprietà **Nessuna scadenza password**. Se in seguito si disattiva il requisito relativo alla smart card, è necessario anche reimpostare la password dell'utente.

Dato che l'impostazione del requisito della smart card reimposta la password dell'utente su un valore sconosciuto, l'utente non è più in grado di utilizzare una combinazione di nome utente e password per accedere al dominio. Di conseguenza, l'utente non può accedere a programmi quali Microsoft Outlook® Web Access per Microsoft Exchange Server 2003 con nome utente e password.

È possibile utilizzare uno script per abilitare questa impostazione durante la registrazione. Tuttavia, questo metodo richiede lo sviluppo di script adatti che possano abilitare e disabilitare il requisito della smart card per determinati utenti.

Se è selezionato il requisito relativo alla smart card dell'account utente, l'amministratore deve utilizzare una smart card per accedere in modalità interattiva a qualunque computer nel dominio, non solo ai server protetti. Ciò può costituire un inconveniente se non tutti i computer sono dotati di lettori di smart card.

Se si impone l'utilizzo di smart card attraverso le proprietà degli account utente, gli amministratori non sono in grado di amministrare in remoto i computer che eseguono Windows 2000 Server. Le sessioni di Servizi terminal di Windows 2000 Server non supportano il reindirizzamento di smart card e l'amministratore deve quindi eseguire l'accesso locale per gestire i computer che eseguono Windows 2000. Questo requisito può rivelarsi problematico se l'amministratore si trova in una postazione diversa dal server.

##### Criteri di gruppo

Un metodo più gestibile consiste nell'utilizzare le impostazioni Criteri di gruppo per specificare che alcuni computer richiedono le smart card per l'accesso interattivo e per controllare ciò che accade quando un utente rimuove una smart card. È possibile creare oggetti Criteri di gruppo per cui siano configurate tali impostazioni e collegare questi oggetti all'unità organizzativa che contiene il computer per il quale è richiesto l'accesso con smart card. Il percorso delle opzioni delle smart card in Criteri di gruppo è Configurazione computer\\Impostazioni Windows\\Impostazioni protezione\\Criteri locali\\Opzioni di protezione. Le impostazioni sono **Accesso interattivo: richiedi smart card** e **Accesso interattivo: funzionamento rimozione smart card**.

**Nota:** questa impostazione richiede Windows XP con Service Pack 2 oppure un aggiornamento per l'impostazione. Per ulteriori informazioni, consultare l'articolo della Knowledge Base relativo all'[aggiornamento per l'impostazione di protezione "Accesso interattivo: richiedi smart card" in Windows XP](http://support.microsoft.com/?id=834875) all'indirizzo http://support.microsoft.com/?id=834875.

Per garantire una maggiore protezione, è opportuno richiedere le smart card per l'accesso interattivo e successivamente impostare il criterio di rimozione delle smart card per bloccare la workstation o disconnettere l'utente. Le impostazioni Criteri di gruppo dovrebbero entrare a far parte di un oggetto Criteri di gruppo personalizzato da applicare agli amministratori. Gli oggetti Criteri di gruppo possono essere applicati a livello di sito, dominio oppure di unità organizzativa. Nella maggior parte dei casi, gli oggetti Criteri di gruppo che applicano impostazioni relative alle smart card si applicano a un'unità organizzativa.

**Nota:** Microsoft consiglia di non modificare l'oggetto Criterio controller di dominio predefinito né l'oggetto Criterio dominio predefinito allo scopo di includere impostazioni delle smart card o altre modifiche dei criteri. Creare sempre un nuovo oggetto Criteri di gruppo oppure utilizzare un oggetto Criteri di gruppo esistente per configurare le impostazioni Criteri di gruppo per l'accesso con smart card.

Le impostazioni Criteri di gruppo per le smart card controllano l'accesso interattivo e non influiscono sull'accesso a un server nella rete. L'accesso interattivo include l'accesso con Desktop remoto o Servizi terminal.

Microsoft consiglia di implementare le smart card per gli amministratori con altri meccanismi di controllo quali IPSec o le impostazioni Criteri di gruppo per impedire la gestione di un server con strumenti di amministrazione remota come Microsoft Management Console (MMC).

#### Gestione dell'accesso con smart card in più domini e insiemi di strutture

L'implementazione delle smart card per gli amministratori richiede che si conoscano i problemi relativi alla presenza di più domini e insiemi di strutture. Ad esempio, gli amministratori membri del gruppo Domain Admins in più insiemi di strutture potrebbero necessitare di una smart card per ciascun insieme di strutture sul quale hanno diritti amministrativi. Di conseguenza, tali amministratori dovrebbero possedere diverse smart card.

Sebbene le smart card possano contenere più certificati, attualmente Windows Server 2003 può accettare soltanto un unico certificato di accesso con smart card (il certificato posto nello slot 0 della smart card) per ciascuna autorità di certificazione (CA) principale. Tale limite potrebbe comportare che alcuni amministratori di rete debbano possedere più smart card, a meno che l'organizzazione non abbia relazioni di trust tra gli insiemi di strutture.

#### Protezione dei server

I computer che eseguono servizi, quali i servizi di gestione file e di stampa, servizi di database, posta elettronica e directory richiedono un livello più alto di protezione rispetto alle workstation. In particolare, è opportuno considerare l'utilizzo dell'autenticazione mediante smart card per tutti gli account che amministrano computer con i seguenti ruoli:

-   Controller di dominio

-   Server di database

-   Server di certificazione

-   File server e server di stampa

##### Protezione dei controller di dominio

I controller di dominio sono i computer più importanti per l'utilizzo dell'autenticazione a due fattori, poiché tali computer contengono e controllano tutte le informazioni sugli account di dominio e applicano regole di protezione a ogni account. Se un utente malintenzionato compromette un controller di dominio, potrebbe successivamente creare un nuovo account, acquisire privilegi più elevati o accedere a tutti i controller di dominio come amministratore.

##### Protezione dei server di database

Un server di database contiene informazioni fondamentali per il funzionamento di un'organizzazione. Le informazioni memorizzate potrebbero essere oggetto di rigorosi processi di archiviazione ed estrazione, con il controllo delle richieste di accesso ai dati. Sono esempi di server di database i server che memorizzano il codice sorgente di una società produttrice di software, le ricette segrete di un produttore di bibite o le informazioni sugli account dei clienti. L'autenticazione mediante smart card dovrebbe proteggere l'accesso a tutti i server di database.

Un'organizzazione dovrebbe identificare i server ad alta protezione e, in collaborazione con i rispettivi proprietari, modificare il tipo di account sul quale viene eseguito il servizio o l'attività pianificata, oppure inserire gli account e i server in gruppi di protezione speciali che abbiano maggiori restrizioni in termini di utenti e accesso.

##### Protezione dei server di certificazione

I server che ospitano autorità di certificazione e Servizi certificati devono avere un elevato livello di protezione. La violazione dell'autorità di certificazione compromette l'integrità dell'organizzazione, rendendo insicuri tutti i certificati emessi. I server che ospitano Servizi certificati devono avere la massima priorità dal punto di vista della protezione per quanto riguarda l'accesso fisico e dalla rete.

##### Protezione dei file server e dei server di stampa

Un file server può contenere documenti aziendali importanti e informazioni riservate. La violazione di tali informazioni può compromettere i ricavi futuri o comportare sanzioni da parte di organismi di regolamentazione. L'autenticazione mediante smart card deve assolutamente proteggere i server di stampa che stampano fatture o assegni bancari.

Per ulteriori informazioni sulle funzionalità di protezione in Windows Server 2003, consultare [Windows Server 2003 Security Guide](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db) all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyID=8a2643c1-0685-4d89-b655-521ea6c7b4db

#### Installazione di lettori di smart card sui server

È necessario collegare un lettore di smart card a ogni server sul quale le impostazioni Criteri di gruppo richiedano le smart card per l'accesso interattivo. La maggior parte dei computer montati su rack dispongono sul lato posteriore di porte USB adatte all'utilizzo di lettori di smart card. Una volta collegato, è possibile posizionare il lettore di smart card sul lato frontale del rack per l'accesso degli utenti. È importante etichettare in modo chiaro i lettori di smart card, in modo che gli amministratori sappiano a quali server appartengono determinati lettori.

Se un amministratore ha necessità di accedere a un altro server, deve rimuovere la smart card dal primo lettore e inserirla nel lettore collegato all'altro computer. Questo inconveniente rende molto più interessante l'amministrazione dei server con Desktop remoto.

#### Distribuzione di smart card

La pianificazione del processo di distribuzione di smart card per gli amministratori include le seguenti attività:

-   Creazione di gruppi adatti alla distribuzione di smart card.

-   Nomina di responsabili della protezione che possano svolgere il ruolo di agenti di registrazione.

-   Selezione di un metodo adatto al trasporto delle smart card.

-   Esecuzione di rigorosi controlli dell'identificazione.

È opportuno creare un gruppo di protezione temporaneo contenente gli account amministratore selezionati. È inoltre necessario un gruppo di protezione per gli account attivati. Parte del processo di registrazione comporta che gli account amministratore vengano spostati dal gruppo temporaneo al gruppo attivato.

Il processo di distribuzione richiede la nomina di responsabili della protezione. Tali responsabili della protezione possono quindi:

-   Distribuire le smart card alla stazione di registrazione.

-   Svolgere il ruolo di agenti di registrazione.

-   Svolgere controlli dell'identificazione.

I controlli dell'identificazione devono essere rigorosi. È opportuno che i responsabili della protezione verifichino personalmente i documenti di identità, quali il passaporto o la patente, degli amministratori e che la loro identità sia confermata dai rispettivi line manager.

È opportuno che le organizzazioni eseguano controlli delle precedenti esperienze dei propri amministratori. Tali controlli sono particolarmente importanti nel settore finanziario e per le organizzazioni che devono rispettare i requisiti di organismi di regolamentazione. Per ulteriori informazioni sui controlli relativi alle esperienze precedenti degli amministratori, consultare la [Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://technet.microsoft.com/it-it/library/dd547357.aspx) all'indirizzo http://www.microsoft.com/italy/technet/security/topics/serversecurity/administratoraccounts/default.mspx.

#### Attivazione delle smart card

L'attivazione delle smart card dovrebbe avvenire in un luogo protetto, ad esempio l'ufficio utilizzato per emettere i permessi che consentono l'accesso alla sede dell'azienda. Il responsabile della protezione configura una stazione di registrazione con due lettori di smart card ed esegue l'accesso utilizzando la propria smart card.

Una volta che il responsabile della protezione ha confermato l'identità dell'amministratore, effettua una richiesta di certificato per l'account utente corrispondente. Apre una nuova smart card e installa il certificato richiesto. Il responsabile della protezione sposta quindi l'account amministratore dal gruppo temporaneo al gruppo attivato. Infine, prende nota del numero di serie della smart card prima di consegnarla all'amministratore.

L'amministratore utilizza quindi lo strumento per il ripristino del PIN per ripristinare il PIN predefinito oppure utilizza lo strumento per l'annullamento del blocco del PIN in combinazione con il server Web di attivazione per impostare un nuovo PIN. La smart card dell'amministratore è pronta all'uso.

#### Gestione delle smart card

L'implementazione delle smart card non è un'operazione che richiede un solo intervento, poiché i certificati di protezione incorporati nelle smart card devono essere gestiti ed è necessario risolvere situazioni in cui gli amministratori dimenticano o smarriscono le smart card oppure ne subiscono il furto. È opportuno stabilire procedure attuabili e prevedere un budget adeguato per la gestione delle smart card.

##### Gestione delle eccezioni

Si consiglia di creare un gruppo temporaneo di eccezioni degli account per gestire situazioni in cui gli amministratori perdono le proprie smart card o ne subiscono il furto. Gli amministratori restano in questo gruppo per un intervallo di tempo compreso tra 24 e 48 ore (nel caso di smart card dimenticate) o fino a quando un agente di registrazione è in grado di emettere una nuova smart card (nel caso di smart card smarrite o rubate). Una volta consegnata la nuova smart card, è possibile rimuovere gli amministratori dal gruppo temporaneo di eccezioni.

A tale scopo, creare un nuovo gruppo di protezione per contenere gli account che riportano eccezioni. Configurare quindi le autorizzazioni sui criteri di gruppo per l'applicazione di smart card in modo da negare al gruppo di eccezioni le autorizzazioni **Lettura** e **Applica criteri di gruppo**. Ai membri del gruppo di eccezioni non si applica più il requisito dell'utilizzo di una smart card per l'accesso interattivo. Per ulteriori informazioni su come configurare le impostazioni di protezione dei criteri di gruppo, vedere l'argomento [To filter the scope of Group Policy according to security group membership](http://technet.microsoft.com/en-us/library/cc786636.aspx) all'indirizzo www.microsoft.com/resources/documentation/WindowsServ/2003/standard/proddocs/en-us/filter.asp.

Potrebbe inoltre essere necessario gestire account che dispongono di privilegi amministrativi ma non possono utilizzare smart card per l'accesso, ad esempio nel caso di servizi o attività pianificate eseguiti con privilegi amministrativi. A tale scopo, aggiungere gli account di servizio a un gruppo di protezione permanente relativo alle eccezioni e configurare autorizzazioni dei criteri di gruppo per tale gruppo come descritto nel precedente paragrafo.

Per ulteriori informazioni su come configurare gli account di servizio, consultare [Guida alla pianificazione della protezione dei servizi e degli account dei servizi](http://technet.microsoft.com/it-it/library/dd550631.aspx) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=41311.

##### Revoca dei certificati

In determinate circostanze, potrebbe essere necessario revocare un certificato, ad esempio se viene violata la chiave privata, se l'utente della smart card cambia mansione oppure se lascia l'organizzazione. Quando viene revocato un certificato, vengono pubblicati i dettagli relativi al certificato nel percorso dell'elenco di revoche dei certificati (CRL). Tale percorso è di norma un URL o un percorso di rete UNC.

Un certificato emesso comprende un elenco di punti di distribuzione dove un server di autenticazione può verificare lo stato del certificato a fronte del CRL. Per ulteriori informazioni, vedere l'argomento [Revoking certificates and publishing CRLs](http://technet.microsoft.com/en-us/library/cc782162.aspx) all'indirizzo www.microsoft.com/resources/documentation/WindowsServ/2003/standard/proddocs/en-us/sag\_CS\_SrvAdCRL.asp.

##### Rinnovo dei certificati

La data di scadenza del certificato digitale su una smart card dipende dalle impostazioni presenti nel modello di certificato che crea il certificato della smart card. I certificati per l'utilizzo di smart card hanno in genere una durata che varia da sei mesi a due anni.

Quando un certificato si avvicina alla scadenza, è necessario il rinnovo per garantire che il proprietario possa continuare a utilizzarlo o lo possa sostituire. In caso di rinnovo di un certificato, il richiedente possiede già un certificato. Il processo di rinnovo prende in considerazione le informazioni del certificato corrente quando viene sottoposta la richiesta di rinnovo. È quindi possibile rinnovare un certificato con una nuova chiave oppure utilizzare la chiave corrente.

##### Registrazione automatica dei certificati

La registrazione automatica dei certificati è una funzionalità di Servizi certificati di Windows Server 2003, Enterprise Edition che automaticamente firma una richiesta di rinnovo utilizzando il certificato esistente per ottenerne uno nuovo. Questa funzionalità agevola la gestione di elevate quantità di certificati. Per ulteriori informazioni sulla registrazione automatica dei certificati, vedere [Certificate Autoenrollment in Windows Server 2003](http://technet.microsoft.com/en-us/library/cc778954.aspx) all'indirizzo http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/autoenro.mspx.

#### Monitoraggio dell'utilizzo delle smart card

Gli amministratori utilizzano account abilitati all'uso di smart card durante l'esecuzione di operazioni che richiedono privilegi elevati, come il riavvio dei server, la gestione degli account utente e la configurazione di autorizzazioni per i file. Amministratori malintenzionati o con una formazione inadeguata possono probabilmente danneggiare l'infrastruttura di rete. Di conseguenza, è opportuno monitorare i registri di protezione per eseguire la registrazione degli accessi e delle disconnessioni mediante smart card da parte degli amministratori.

Strumenti di gestione aziendale quali Microsoft Operations Manager (MOM) 2005, che sono in grado di monitorare e valutare i registri eventi di protezione, sono adatti al monitoraggio dell'utilizzo di smart card. Per ulteriori informazioni sul monitoraggio dei registri eventi di protezione, consultare la [Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://technet.microsoft.com/it-it/library/dd547357.aspx) all'indirizzo http://www.microsoft.com/italy/technet/security/topics/serversecurity/administratoraccounts/default.mspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Problemi e requisiti

Nella presente sezione vengono descritti i problemi e i requisiti specifici riscontrati da Woodgrove National Bank durante la progettazione di una soluzione per proteggere gli account amministratore con le smart card.

#### Situazione esistente

Woodgrove National Bank possiede diversi server critici che richiedono un rigoroso controllo amministrativo e l'accesso protetto. Gli amministratori attualmente eseguono l'autenticazione per i suddetti server utilizzando una combinazione di nome utente e password. Sono stati eseguiti tentativi di accesso ai server critici da parte di utenti non autorizzati in possesso di credenziali rubate.

#### Problematiche aziendali

Woodgrove National Bank ha identificato le seguenti tre problematiche relative alla responsabilità degli amministratori e alla continuità operativa:

-   **Responsabilità**. Il reparto IT non è in grado di verificare le modifiche importanti apportate ai server da amministratori che utilizzano l'autenticazione con nome utente e password poiché gli amministratori spesso condividono le credenziali.

-   **Protezione delle credenziali**. Gli utenti malintenzionati che rubano le credenziali degli amministratori possono seriamente danneggiare la reputazione dell'organizzazione e provocare perdite finanziarie dovute ai tempi di inattività. L'autenticazione mediante smart card ridurrebbe in modo significativo la possibilità di furto delle credenziali degli amministratori.

-   **Continuità operativa**. Woodgrove National Bank non può permettere che modifiche alla configurazione di rete interrompano i servizi aziendali; pertanto è fondamentale adottare un approccio attentamente pianificato durante la fase di implementazione della soluzione basata su smart card.

#### Problemi tecnici

Il reparto IT di Woodgrove National Bank ha individuato i seguenti problemi tecnici che è necessario superare per implementare una soluzione basata su smart card:

-   **Supporto di lettori di smart card**. Ogni server al quale gli amministratori devono accedere mediante una smart card deve garantire il supporto hardware per lettori di smart card.

-   **Implementazione di procedure operative consigliate**. L'integrità di una distribuzione di smart card dipende da un'efficiente attività di gestione e manutenzione a lungo termine. È opportuno che il reparto IT di Woodgrove National Bank implementi le procedure operative consigliate delineate da Microsoft Operations Framework (MOF).

-   **Attività pianificate eseguite con diritti di amministratore su un server accessibile mediante smart card**.** **Woodgrove National Bank esegue attività pianificate che utilizzano account con privilegi di amministratore. Woodgrove National Bank ha l'esigenza di esaminare tali account e, se possibile, utilizzare account che non richiedano privilegi amministrativi. Woodgrove National Bank deve inoltre implementare un gruppo di esclusione permanente contenente tutti gli account che eseguono attività pianificate, in modo che tali account non siano soggetti al requisito relativo all'accesso mediante smart card.

-   **Integrazione con UNIX**. Woodgrove National Bank utilizza un ambiente eterogeneo e, di conseguenza, l'integrazione delle smart card con computer che eseguono UNIX è un aspetto da prendere in considerazione. Woodgrove National Bank intende esaminare prodotti quali TrustBroker di CyberSafe Limited che forniscono autenticazione integrata mediante smart card per Windows e UNIX.

#### Problemi relativi alla protezione

La finalità dell'utilizzo di smart card per proteggere gli account amministratore è il miglioramento della protezione e della responsabilità. Il dipartimento IT di Woodgrove National Bank IT ha identificato i seguenti problemi di protezione che la banca deve affrontare prima di poter distribuire la soluzione:

-   **Distribuzione e attivazione**.** **La** **distribuzione e attivazione di smart card è importante per salvaguardare l'integrità dell'intera soluzione. Poiché Woodgrove National Bank ha sedi in tutto il mondo, il reparto IT di Woodgrove non può distribuire smart card da un'unica posizione di origine. La verifica dei destinatari delle smart card è un fattore chiave per mantenere l'integrità del progetto. Woodgrove National Bank intende impiegare team di protezione che utilizzano i dati di identificazione del reparto risorse umane per garantire che ogni smart card venga emessa per la persona corretta.

-   **Approccio ai diritti amministrativi secondo il criterio del privilegio minimo**. È opportuno che Woodgrove National Bank analizzi l'attuale modello di amministrazione di rete e riduca il numero di account utente e di servizio che vengono eseguiti con privilegi amministrativi completi. La banca dovrebbe assegnare solo i privilegi necessari agli amministratori per svolgere le proprie mansioni. L'analisi e la riduzione del numero di account amministratore possono contribuire alla distribuzione, al monitoraggio e alla gestione continuata della soluzione basata su smart card.

-   **Gestione degli account di servizio**.** **Il reparto IT di Woodgrove National Bank ha analizzato gli account di servizio relativi ai programmi e ha assicurato che un contesto di protezione a livello di amministrazione è necessario al minor numero di servizi possibile. Molti programmi sono contrassegnati per l'aggiornamento o la sostituzione.

-   **Una smart card per ogni insieme di strutture in una relazione di trust completa**. Woodgrove National Bank ha due insiemi di strutture collegati da una relazione di trust bidirezionale. Sebbene una smart card possa contenere più certificati, Windows Server 2003 utilizza soltanto il certificato posto nello slot 0 della smart card per eseguire l'accesso interattivo. Questa architettura richiede che gli amministratori che operano su più insiemi di strutture non collegate dispongano di più smart card. Tuttavia, un amministratore in possesso di una smart card ha accesso alle risorse di tutti gli insiemi di strutture che hanno una relazione di trust completa con l'insieme di strutture che ha eseguito l'autenticazione dell'amministratore, a meno che su tale accesso non prevalga una restrizione di protezione nell'insieme di strutture trusting.

-   **Gestione dei PIN**. La sicurezza e l'integrità della soluzione basata su smart card aumentano se gli utenti sono in grado di modificare agevolmente i propri PIN. Di conseguenza, il reparto IT di Woodgrove National Bank ha acquistato adeguati strumenti di gestione dei PIN dai produttori di smart card.

#### Requisiti delle soluzioni

Dopo l'analisi del progetto pilota iniziale, il reparto IT di Woodgrove National Bank ha sviluppato specifici requisiti della soluzione. La soluzione utilizzata da Woodgrove National Bank per la protezione degli account amministratore che possiedono smart card deve:

-   Garantire che i server protetti richiedano una smart card valida per l'accesso interattivo, secondario o con Desktop remoto.

-   Distribuire e attivare smart card in modo protetto e tempestivo.

-   Fornire un controllo dell'accesso ai server protetti e raccogliere i dati di protezione risultanti in un archivio centrale.

-   Abilitare la gestione e il monitoraggio dell'utilizzo di smart card.

-   Garantire una revoca rapida dei certificati compromessi, ad esempio su smart card smarrite o rubate.

-   Fornire una struttura per la gestione continuativa.

Woodgrove National Bank ha identificato numerosi problemi importanti, emersi nel piano iniziale, dal punto di vista aziendale, tecnico e della protezione. Il reparto IT di Woodgrove National Bank ha eseguito un'analisi per affrontare tali problemi e ha condotto test di soluzioni e correzioni. Woodgrove National Bank ha creato piani dettagliati per la fase di distribuzione della soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Progettazione della soluzione

Una volta compresi i problemi aziendali, tecnici e di protezione che devono essere risolti dalla soluzione basata su smart card, è possibile progettare una soluzione adatta al proprio ambiente. l processo di progettazione identifica gli elementi essenziali e analizza a livello logico i requisiti per la pianificazione della soluzione.

Woodgrove National Bank ha eseguito questa valutazione. Nella presente sezione vengono descritti i problemi emersi nel piano iniziale che sono stati presi in considerazione dagli architetti di sistema di Woodgrove National Bank, le conclusioni a cui sono giunti e le decisioni che hanno preso a livello di progettazione.

Vengono illustrate le scelte di progettazione effettuate dal reparto IT di Woodgrove National Bank per garantire la protezione degli account amministratore mediante l'utilizzo di smart card. Inoltre, vengono spiegati nel dettaglio la soluzione concettuale e i relativi prerequisiti e viene descritta l'architettura pianificata da Woodgrove National Bank.

#### Soluzione concettuale

Nella soluzione proposta, l'intera attività di amministrazione dei server richiede l'autenticazione dell'identità dell'amministratore mediante la presentazione di un certificato archiviato su una smart card e del PIN corrispondente. La soluzione utilizza una combinazione di impostazioni Criteri di gruppo, certificati utente X.509 versione 3 (v3), smart card e lettori di smart card. La soluzione richiede l'installazione di un certificato X.509 v3 sulla smart card.

Per accedere a un server, l'amministratore inserisce la smart card in un lettore di smart card installato sul computer. Quando viene inserita la smart card, il sistema operativo visualizza un prompt che richiede il PIN. L'amministratore inserisce quindi il PIN della smart card. Se il PIN è corretto, l'amministratore può accedere al server con diritti amministrativi.

#### Requisiti della soluzione

Quando si realizza un progetto di questa natura, è necessario rispettare diversi prerequisiti. Tali prerequisiti includono la selezione del team del progetto, la consultazione degli utenti, l'implementazione di test o progetti pilota e la necessità di aggiornare hardware e software per soddisfare i requisiti della soluzione.

##### Consultazione dei team di amministrazione

Quando si modifica di un servizio utente è essenziale consultare gli utenti e i gruppi coinvolti. Dal canto loro, gli utenti devono comprendere cosa possono aspettarsi realmente dal servizio. La consultazione reciproca e la gestione delle aspettative degli utenti è spesso fondamentale affinché gli utenti possano accettare il progetto. È necessario stabilire obiettivi misurabili per valutare la riuscita finale del progetto in modo razionale. Tali obiettivi possono includere la riduzione dei problemi di protezione associati al furto di credenziali.

Woodgrove National Bank opera in diversi paesi e regioni in tutto il mondo e si avvale di servizi di supporto tecnico regionali. Il team di progettazione iniziale ha collaborato in modo esauriente con i team di tutte le sedi al fine di identificare i server adatti per la soluzione basata su smart card. Il team ha inoltre identificato i server che non potrebbero essere aggiornati in tempi adeguati per soddisfare i prerequisiti della soluzione.

##### Selezione del team del progetto

È fondamentale disporre delle competenze e del personale adatti all'implementazione di un progetto di questo tipo. È probabile che il team del progetto necessiti del contributo delle seguenti figure rappresentative:

-   Program manager

-   Architetto di sistemi informativi

-   Analista o integratore di sistemi

-   Tecnici di sistema

-   Product release manager

-   Testing manager

-   Responsabile help desk o responsabile supporto tecnico

-   Specialisti del supporto tecnico per gli utenti

-   Responsabili della protezione

Per ulteriori informazioni sulle figure rappresentative e sulle associazioni di ruoli MOF, consultare [The Microsoft Solutions Framework Supplemental Whitepapers – IT Occupation Taxonomy](http://www.microsoft.com/downloads/details.aspx?familyid=839058c3-d998-4700-b958-3bedfee2c053) all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyID=839058c3-d998-4700-b958-3bedfee2c053

Se l'azienda non dispone di personale con competenze specifiche al suo interno, deve provvedere ad assumere personale aggiuntivo. Dal momento che di norma il progetto non richiede la partecipazione dell'intero organico in ogni fase, è necessario determinare il livello di disponibilità che ciascuno deve assicurare per tutta la durata del progetto.

#### Architettura della soluzione

Per implementare una soluzione basata su smart card per proteggere gli account amministratore, sono necessari i seguenti elementi:

-   Active Directory

-   Criteri di gruppo

-   Windows Server 2003, Enterprise Edition, infrastruttura a chiave pubblica (PKI)

-   Lettori di smart card sui server che eseguono Windows Server 2003

-   Stazioni di registrazione

-   Personalizzazione delle smart card

-   Strumenti di gestione dei PIN

Prima di implementare la soluzione, Woodgrove National Bank ha eseguito le seguenti procedure:

-   Aggiornamento di Servizi certificati a Windows Server 2003, Enterprise Edition o versioni successive.

-   Aggiornamento di tutti i server gestiti a Windows Server 2003 per supportare l'accesso interattivo attraverso Servizi terminal. Questo requisito dipende dalla compatibilità delle applicazioni.

-   Personalizzazione dei modelli utente dei certificati di smart card e impostazione delle autorizzazioni adeguate.

-   Creazione e verifica degli oggetti Criteri di gruppo (GPO) per l'applicazione di smart card, le esclusioni temporanee e le esclusioni permanenti.

Il reparto IT di Woodgrove National Bank ha inoltre implementato soluzioni per le seguenti problematiche:

-   Distribuzione delle smart card

-   Attivazione delle smart card

-   Gestione e supporto delle smart card

-   Gestione delle eccezioni

##### Distribuzione delle smart card

Prima di distribuire le smart card, il reparto IT di Woodgrove National Bank ha inserito i propri amministratori in un gruppo di protezione temporaneo di Active Directory. È stato necessario un team di responsabili della protezione per la verifica dell'identità degli amministratori e la distribuzione delle smart card. Una volta consegnata la smart card, il reparto IT ha spostato ogni amministratore dal gruppo temporaneo al gruppo di utenti delle smart card. Gli amministratori hanno quindi avuto accesso al server Web di attivazione per l'attivazione della smart card e la modifica del PIN.

##### Attivazione delle smart card

Poiché gli amministratori hanno ricevuto le proprie smart card in stato di sospensione, tali smart card devono essere attivate prima dell'uso. Un amministratore attiva la propria smart card inserendola in un lettore di smart card, immettendo una richiesta e modificando il PIN.

##### Gestione e supporto delle smart card

Sebbene gli amministratori di Woodgrove National Bank costituiscano un gruppo di tecnici esperti, il team di distribuzione delle smart card ha dovuto collaborare assiduamente con l'help desk. Il personale addetto all'help desk ha richiesto istruzioni adeguate alla corretta gestione dei problemi rilevati.

###### Gestione delle eccezioni

Woodgrove National Bank ha elaborato una serie di criteri aziendali per affrontare i casi di smart card smarrite, rubate o dimenticate. Per la perdita o il furto di smart card, il reparto IT revoca tutti i certificati assegnati ed emette nuove smart card entro 24 ore. Il reparto IT affronta i problemi di amministratori che dimenticano di portare sul luogo di lavoro le proprie smart card e sposta i rispettivi account in un gruppo di eccezioni per un periodo di 24 ore. L'appartenenza al gruppo di eccezioni elimina il requisito di accesso mediante smart card. Anche se un certificato viene revocato, ciò non significa che la smart card venga contemporaneamente disattivata. Woodgrove National Bank deve riesaminare i propri criteri relativi al CRL in modo da farli corrispondere ai criteri di protezione.

Un gruppo separato contiene le eccezioni permanenti al requisito relativo alle smart card, ad esempio gli account di servizio e le attività pianificate.

###### Revoca dei certificati

I certificati di accesso con smart card per gli amministratori di Woodgrove National Bank utilizzano URL della rete Intranet per individuare il CRL e controllare la presenza di certificati revocati. Il reparto IT ha implementato il bilanciamento del carico di rete (NLB) di Windows per garantire elevata disponibilità per il sito Web che ospita il CRL.

###### Rinnovo dei certificati

Il reparto IT di Woodgrove National Bank ha sviluppato un processo di rinnovo dei certificati che richiede l'approvazione della richiesta di rinnovo della smart card da parte del responsabile dell'amministratore. Dopo l'approvazione della richiesta da parte del responsabile, il certificato corrente viene utilizzato per firmare la richiesta di certificato e il certificato della smart card viene rinnovato.

##### Monitoraggio della soluzione

Woodgrove National Bank utilizza Microsoft Operations Manager (MOM) 2005 per raccogliere e analizzare i registri eventi di protezione e per monitorare la disponibilità e le prestazioni della soluzione. La soluzione basata su smart card si integra con MOM, consente di monitorare i registri eventi di protezione, fornisce avvisi e crea report di utilizzo. Woodgrove National Bank intende esaminare il servizio con frequenza trimestrale e creare report a partire dai dati di MOM.

#### Procedura di funzionamento della soluzione

Nella presente sezione vengono descritti i processi dettagliati che si verificano durante l'autenticazione dell'accesso con smart card.

1.  Un amministratore inserisce la smart card nel lettore di smart card collegato a un computer e la DLL Microsoft Graphical Identification and Authentication (MSGINA) e il computer richiedono all'utente l'inserimento del PIN.

2.  MSGINA passa il PIN all'autorità di protezione locale (LSA) e il computer utilizza il PIN per accedere alla smart card.

3.  Il pacchetto Kerberos sul lato client legge il certificato X.509 v3 e la chiave privata dalla smart card dell'amministratore.

4.  Il pacchetto Kerberos invia una richiesta di servizio di autenticazione al centro distribuzione chiavi (KDC) eseguito su un controller di dominio, per richiedere l'autenticazione e un ticket di concessione ticket (TGT). La richiesta di servizio di autenticazione è costituita da un certificato PAC (Privilege Attribute Certificate), contenente l'identificatore di protezione (SID) dell'utente, i SID di tutti i gruppi di cui fa parte l'utente e una richiesta per il servizio di concessione ticket (TGS), insieme ai dati di pre-autenticazione.

5.  Il KDC verifica il percorso di certificazione del certificato dell'utente per garantire che il certificato provenga da un'origine attendibile. Il KDC utilizza CryptoAPI per creare un percorso di certificazione dal certificato dell'amministratore a un certificato della CA principale che risiede nell'archivio principale sul controller di dominio. Il KDC utilizza quindi CryptoAPI per verificare la firma digitale sull'autenticatore che è stata inclusa come dato firmato nei campi dati della pre-autenticazione. Il controller di dominio verifica la firma e utilizza la chiave pubblica proveniente dal certificato dell'amministratore per dimostrare che la richiesta ha avuto origine dal proprietario della chiave pubblica. Il KDC verifica inoltre che l'autorità emittente sia attendibile e che sia inclusa nell'archivio di certificati NTAUTH.

6.  Il servizio KDC recupera le informazioni sull'account utente da Active Directory in base al nome principale utente (UPN) indicato nel campo **Nome alternativo oggetto** del certificato dell'amministratore. Il KDC crea un TGT dalle informazioni dell'account utente recuperate da Active Directory. Il TGT include il SID dell'amministratore, i SID di ogni gruppo di dominio al quale l'amministratore appartiene e (nel caso di ambienti con più domini) i SID di ogni gruppo universale di cui è membro l'utente. I campi dati dell'autorizzazione del TGT includono l'elenco dei SID.

    **Nota:** un SID è un identificatore di protezione che viene creato per ogni utente o gruppo al momento della creazione di un account utente o di gruppo all'interno del database degli account di protezione locale su Windows NT o versioni successive oppure all'interno di Active Directory. Il SID non subisce mai modifiche anche nel caso in cui l'account utente o di gruppo venga rinominato.

7.  Il controller di dominio restituisce il TGT al client. Il client o la smart card eseguono la decrittografia del TGT e utilizzano la chiave privata per ottenere la chiave segreta del KDC. Questo dipende dal tipo di smart card o di certificato utilizzato.

8.  Il client convalida la risposta del KDC. Verifica innanzitutto la firma del KDC creando un percorso di certificazione dal certificato del KDC a una CA principale attendibile, quindi utilizza la chiave pubblica del KDC per verificare la firma della risposta.

Questo processo viene illustrato nella seguente figura:

[![](images/Dd536290.PGFG0301(it-it,TechNet.10).gif "Figura 3.1 Processo di autenticazione dell'accesso con smart card")](https://technet.microsoft.com/it-it/dd536290.pgfg0301_big(it-it,technet.10).gif)

**Figura 3.1 Processo di autenticazione dell'accesso con smart card**

Il reparto IT di Woodgrove National Bank ha collegato un oggetto Criteri di gruppo alle unità organizzative che contengono i server per i quali è necessario l'accesso con smart card. Questo oggetto Criteri di gruppo applica le modifiche alle seguenti impostazioni della configurazione dei computer:

-   L'accesso interattivo richiede una smart card

-   La rimozione della smart card forza la disconnessione dell'account

Queste impostazioni evitano che gli amministratori condividano le smart card o lascino incustodito un server mentre sono connessi.

#### Estensione della soluzione

Woodgrove National Bank prevede di integrare la soluzione basata su smart card nel processo di gestione delle modifiche a server e applicazioni. Il piano stabilisce l'autenticazione di ogni fase del processo di gestione delle modifiche e l'integrazione di tale processo nel flusso di lavoro. Ad esempio, le modifiche al server Web di Woodgrove National Bank richiederebbero la verifica da parte di due o più amministratori Web.

#### Riepilogo

L'utilizzo di smart card per autenticare gli account utente amministratore riduce le possibilità di accesso non autorizzato ai computer critici e aumenta il livello di integrità e responsabilità dell'amministrazione dei server. L'implementazione delle smart card per gli amministratori offre all'organizzazione il vantaggio della riduzione dei problemi di protezione e dell'aumento della qualità delle procedure amministrative.

##### Download

[![](images/Dd536290.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://go.microsoft.com/fwlink/?linkid=41314)

[](#mainsection)[Inizio pagina](#mainsection)
