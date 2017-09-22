---
TOCTitle: 'Capitolo 5: Opzioni di protezione'
Title: 'Capitolo 5: Opzioni di protezione'
ms:assetid: '668266f5-94b3-439c-8e2f-feaec0a9ae33'
ms:contentKeyID: 20200876
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536277(v=TechNet.10)'
---

Pericoli e contromisure
=======================

### Capitolo 5: Opzioni di protezione

La sezione Opzioni di protezione dei Criteri di gruppo consente di abilitare o disabilitare le impostazioni di protezione dei computer per la firma digitale dei dati, i nomi degli account Administrator e Guest, l'accesso all'unità disco floppy e CD–ROM, il funzionamento di installazione del driver e i prompt di accesso. La cartella di lavoro Microsoft Excel "Windows Default Security and Services Configuration" (in inglese, inclusa nella versione scaricabile di questa guida) riporta le impostazioni predefinite.

##### In questa pagina

[](#ebaa)[Impostazioni delle opzioni di protezione](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Impostazioni delle opzioni di protezione

È possibile configurare le impostazioni delle opzioni di protezione all'interno dell'Editor oggetti Criteri di gruppo nella posizione seguente:

**Configurazione computer\\Impostazioni di Windows\\Impostazioni di protezione\\**
**Criteri locali\\Opzioni di protezione**

#### Account: stato account Administrator

Questa impostazione di criterio attiva o disattiva l'account Administrator per le normali condizioni di funzionamento. Quando il computer viene avviato in modalità provvisoria, l'account Administrator è sempre attivato, indipendentemente dal tipo di configurazione di questa impostazione di criterio.

I possibili valori dell'impostazione **Account: stato account Administrator** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

In alcune organizzazioni, conservare un piano regolare delle modifiche periodiche alle password di account locali può rappresentare un'attività di gestione piuttosto impegnativa. Per proteggere l'account Administrator da eventuali attacchi, è quindi possibile disattivarlo, invece di ricorrere regolarmente alle modifiche della password. Un altro motivo valido per disabilitare tale account è che non è possibile bloccarlo, indipendentemente dal numero di tentativi di accesso non riusciti che ne derivano e per questo motivo costituisce il primo obiettivo di attacchi di tipo "brute force", che tentano di determinare le password. Questo account include inoltre un identificatore di protezione noto (SID) che, in alcuni strumenti di terze parti, viene specificato al posto del nome di account per l'autenticazione. Questa caratteristica consente quindi a un pirata informatico che vuole effettuare l'accesso, di eseguire un attacco di tipo "brute force" utilizzando il SID, anche quando l'account Administrator viene rinominato.

##### Contromisura

Configurare l'impostazione **Account: stato account Administrator** su **Disabilitato** in modo che l'account Administrator integrato non sia più utilizzabile in un normale avvio del sistema.

##### Impatto potenziale

In alcuni casi, quando l'account Administrator viene disattivato, possono verificarsi problemi di manutenzione. Ad esempio, se per qualsiasi motivo il canale protetto tra un computer membro e il controller di dominio non funziona e non è disponibile un altro account Administrator locale, per risolvere il problema che ha interrotto il canale protetto è necessario riavviare il sistema in modalità provvisoria.

Se la password di amministratore corrente non è conforme ai requisiti delle password, non sarà possibile abilitare di nuovo l'account Administrator dopo la relativa disabilitazione. In questo caso, un altro membro del gruppo **Administrators** deve impostare la password sull'account Administrator mediante lo strumento Utenti e gruppi locali.

#### Account: stato account Guest

Questa impostazione di criterio determina se l’account Guest deve essere abilitato o disabilitato.

I possibili valori dell'impostazione **Account: stato account Guest** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

L'account Guest predefinito consente agli utenti della rete non autenticati di connettersi come Guest, senza alcuna password. Tali utenti non autorizzati possono accedere a tutte le risorse di rete a cui è consentito l'accesso con l'account Guest. Questa caratteristica consente a qualsiasi condivisione di rete con autorizzazioni che consentono l'accesso all'account Guest, al gruppo **Guest**, o al gruppo **Everyone,** di poter essere accessibile in rete, rischiando di provocare l'esposizione e il danneggiamento dei dati.

##### Contromisura

Configurare l'impostazione **Account: stato account Guest** su **Disabilitato** in modo che non sia più possibile utilizzare l'account Guest integrato.

##### Impatto potenziale

Tutti gli utenti della rete dovranno eseguire l'autenticazione prima di poter accedere alle risorse condivise. Se l'account Guest è disattivato e l'opzione **Accesso di rete: modello di condivisione e protezione** è impostata su **Solo Guest**, non sarà possibile effettuare gli accessi alla rete, come ad esempio quelli eseguiti da Server di rete Microsoft (servizio SMB). Questa impostazione di criterio dovrebbe avere un impatto minimo sulla maggior parte delle organizzazioni in quanto rappresenta l'impostazione predefinita in Microsoft Windows 2000, Windows XP e Windows Server 2003.

#### Account: limitare l'uso locale di account con password vuote all'accesso alla console

Questa impostazione di criterio determina se gli accessi interattivi remoti di servizi di rete quali Servizi terminal, Telnet e File Transfer Protocol (FTP) sono consentiti o meno per gli account locali con password vuote. Se questa impostazione di criterio è abilitata, un account locale deve disporre di una password non vuota affinché sia possibile utilizzarlo per eseguire un accesso di rete o interattivo da un client remoto.

I possibili valori dell'impostazione **Account: limitare l'uso locale di account con password vuote all'accesso alla console** sono:

-   Abilitato

-   Disabilitato

-   Non definito

**Nota**: questa impostazione non influisce sugli accessi interattivi alla console eseguiti fisicamente o sugli accessi basati sugli account di dominio.

**Avviso**: per le applicazioni di terze parti che utilizzano accessi interattivi remoti è possibile ignorare questo criterio.

##### Vulnerabilità

Le password vuote rappresentano un serio pericolo per la protezione dei computer ed è consigliabile impedirne l'utilizzo mediante criteri aziendali e misure tecniche appropriate. In Windows Server 2003, le impostazioni predefinite per il servizio Active Directory richiedono password complesse costituite almeno da sette caratteri. Se tuttavia un utente in grado di creare nuovi account riesce a superare i criteri password di dominio, tali account possono creare account con password vuote. Ad esempio, un utente può creare un computer autonomo, creare uno o più account con password vuote e aggiungere quindi il computer al dominio. In tal caso, gli account locali con password vuote funzionano comunque. Chi conosce il nome di uno di questi account non protetti può utilizzarlo per effettuare l'accesso.

##### Contromisura

Abilitare l'impostazione **Account: limitare l'uso locale di account con password vuote all'accesso alla console**.

##### Impatto potenziale

Nessuno. Si tratta della configurazione predefinita.

#### Account: rinomina account amministratore

Questa impostazione di criterio determina se associare o meno un nome di account diverso al SID per l'account Administrator.

I possibili valori dell'impostazione **Account: rinomina account amministratore** sono:

-   Testo definito dall'utente

-   Non definito

##### Vulnerabilità

L'account Administrator esiste in tutti i computer con sistema operativo Windows 2000, Windows Server 2003 o Windows XP Professional. La ridenominazione dell'account rende più complessa per gli utenti non autorizzati l'identificazione di questa combinazione privilegiata di nome utente e password.

L'account Administrator integrato non può essere bloccato, indipendentemente dal numero di tentativi eseguiti da un pirata informatico mediante l'utilizzo di una password non valida. Pertanto l'account Administrator rappresenta un obiettivo tipico per gli attacchi di determinazione della password di tipo "brute force". La validità di questa contromisura risulta ridotta, in quanto questo account dispone di un SID noto ed esistono strumenti di terze parti che consentono l'autenticazione utilizzando il SID invece del nome di account. Se si rinomina l'account Administrator, quindi, un pirata informatico potrebbe comunque eseguire un attacco di tipo "brute force" utilizzando il SID per effettuare l'accesso.

##### Contromisura

Specificare un nuovo nome nell'impostazione **Account: rinomina account amministratore** per rinominare l'account Administrator.

**Nota**: nei capitoli successivi l'impostazione di questo criterio non viene configurata nei modelli di protezione, né viene indicato un nuovo nome utente per l'account nella guida. I modelli omettono l'impostazione di questo criterio per evitare che le tante organizzazioni che si servono di queste indicazioni non implementino lo stesso nuovo nome utente nei rispettivi ambienti.

##### Impatto potenziale

È necessario comunicare il nuovo nome dell'account agli utenti autorizzati ad utilizzare questo account (la guida per questa impostazione presuppone che l'account Administrator non sia stato disattivato, come quanto consigliato in precedenza nel presente capitolo).

#### Account: rinomina account guest

L'opzione **Account: rinomina account guest** determina se associare o meno un nome di account diverso al SID per l'account Guest.

I possibili valori per questa impostazione dei criteri di gruppo sono:

-   Testo definito dall'utente

-   Non definito

##### Vulnerabilità

L'account Guest è presente in tutti i computer con sistema operativo Windows 2000, Windows Server 2003 o Windows XP Professional. Se questo account viene rinominato, l'identificazione di questa combinazione privilegiata di nome utente e password è resa più complessa per gli utenti non autorizzati.

##### Contromisura

Specificare un nome nuovo nell'impostazione **Account: rinomina account guest** per rinominare l'account Guest.

**Nota**: nei capitoli successivi l'impostazione di questo criterio non viene configurata nei modelli di protezione, né viene indicato un nuovo nome utente per l'account nella guida. I modelli omettono l'impostazione di questo criterio per evitare che le tante organizzazioni che si servono di queste indicazioni non implementino lo stesso nuovo nome utente nei rispettivi ambienti.

##### Impatto potenziale

In genere l'impatto risulta minimo in quanto l'account Guest è disabilitato per impostazione predefinita in Windows 2000, Windows XP e Windows Server 2003.

#### Controllo: controllo accesso oggetti di sistema globale

Se questa impostazione di criterio viene abilitata, quando il computer crea oggetti di sistema come i mutex, gli eventi, i semafori e le periferiche M-DOS, viene applicato un elenco di controllo di accesso di sistema (SACL) predefinito. Se viene abilitata anche l'impostazione di controllo **Controlla accesso agli oggetti** come descritto nel Capitolo 3 di questa guida, verrà controllato l'accesso a questi oggetti di sistema.

Gli oggetti di sistema globale, noti anche come "oggetti di sistema di base" o "oggetti denominati di base", sono oggetti del kernel effimeri a cui vengono assegnati dei nomi dall'applicazione o dal componente di sistema utilizzato per crearli. Tali oggetti vengono utilizzati generalmente per sincronizzare più applicazioni o più parti di un'applicazione complessa. Poiché sono provvisti di un nome, questi oggetti dispongono di un ambito globale e pertanto sono visibili a tutti i processi del computer. Tutti gli oggetti di questo tipo includono un descrittore di protezione ma in genere dispongono di un SACL NULL. Se questa impostazione di criterio viene abilitata al momento dell'avvio, il kernel assegnerà un SACL a questi oggetti durante la relativa creazione.

I possibili valori dell'impostazione **Controllo: controllo accesso oggetti di sistema globale** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

In caso di protezione inadeguata, un oggetto denominato visibile a livello globale è soggetto potenzialmente al rischio di attacco da parte di un programma dannoso a conoscenza del nome dell'oggetto. Se ad esempio un oggetto di sincronizzazione quale un mutex dispone di un elenco di controllo di accesso discrezionale (DACL) inadeguato, un programma dannoso potrebbe accedere a tale mutex in base al nome e causare un malfunzionamento dell'applicazione utilizzata per la creazione dell'oggetto. Tuttavia, il rischio che ciò si verifichi è limitato.

##### Contromisura

Attivare l'impostazione **Controllo: controllo accesso oggetti di sistema globale**.

##### Impatto potenziale

Se l'impostazione **Controllo: controllo accesso oggetti di sistema globale** viene abilitata, potrebbe essere generato un numero elevato di eventi di protezione, specialmente in controller di dominio e server di applicazioni con un carico di lavoro notevole. Di conseguenza potrebbero verificarsi un rallentamento dei tempi di risposta dei server e la memorizzazione forzata di un numero elevato di eventi di scarso interesse nel registro eventi protezione. Questa impostazione di criterio può essere solo attivata o disattivata, poiché non è possibile filtrare gli eventi da registrare ed escludere gli altri. Persino nel caso di organizzazioni dotate di risorse per l'analisi degli eventi generati in seguito all'abilitazione di questa impostazione, è improbabile che sia disponibile il codice sorgente o una descrizione del tipo di utilizzo di ciascun oggetto denominato. Pertanto è difficile che un numero elevato di organizzazioni possa trarre vantaggio dall'**abilitazione** di questa impostazione.

#### Controllo: controllo utilizzo dei privilegi di backup e di ripristino

Questa impostazione di criterio determina se controllare l'utilizzo di tutti i privilegi utente, incluso Backup e ripristino, quando l'impostazione **Controlla uso dei privilegi** è attiva. Se si attivano entrambi i criteri, sarà generato un evento di controllo per ogni file del quale viene eseguito il backup o che viene ripristinato.

Se questa impostazione viene abilitata insieme all'impostazione **Controlla uso dei privilegi**, nel registro protezione viene memorizzata qualsiasi istanza dei diritti utente esercitati. Nel caso in cui venga disabilitata questa impostazione, quando gli utenti utilizzano i privilegi di backup o ripristino, tali eventi non vengono controllati anche se l'opzione **Controlla uso dei privilegi** è abilitata.

I possibili valori dell'impostazione **Controllo: controllo utilizzo dei privilegi di backup e di ripristino** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Se si abilita questa opzione quando è abilitata anche l'impostazione **Controlla uso dei privilegi**, viene generato un evento di controllo per ogni file del quale viene eseguito il backup o che viene ripristinato. In questo modo è possibile risalire a un account che, accidentalmente o intenzionalmente, è stato utilizzato per ripristinare i dati senza apposita autorizzazione.

##### Contromisura

Attivare l'impostazione **Controlla l'utilizzo dei privilegi di backup e di ripristino.** In alternativa, implementare il backup automatico del registro configurando la chiave del Registro di sistema AutoBackupLogFiles, descritta nell'articolo della Microsoft Knowledge Base "[Il registro eventi interrompe la registrazione degli eventi prima che venga raggiunta la dimensione massima del registro](http://support.microsoft.com/kb/312571/it)" all'indirizzo http://support.microsoft.com/kb/312571/it.

##### Impatto potenziale

L'abilitazione di questa impostazione potrebbe generare un numero elevato di eventi di protezione, con conseguente rallentamento dei tempi di risposta dei server e memorizzazione forzata di numerosi eventi di scarso interesse nel registro eventi protezione. Se la dimensione del registro di protezione viene aumentata per ridurre le probabilità di un arresto del sistema, una dimensione troppo ampia del file di registro potrebbe avere ripercussioni sulle prestazioni del sistema.

#### Controllo: arresto del sistema immediato se non è possibile registrare i controlli di protezione

Questa impostazione di criterio determina se il sistema debba essere arrestato quando non è in grado di registrare gli eventi di protezione. I criteri TCSEC (Trusted Computer System Evaluation Criteria) di classe C2 e la certificazione Criteri comuni richiedono che il computer impedisca il verificarsi di eventi controllabili nel caso in cui questi non possano essere registrati dal sistema di controllo. Microsoft ha scelto di garantire la conformità a tale requisito mediante l'arresto del sistema e la visualizzazione di un messaggio di interruzione in caso di errore del sistema di controllo. Qualora non sia possibile registrare un controllo di protezione per un qualsiasi motivo, l'abilitazione di questa impostazione determinerà l'arresto del computer. In genere, un evento non viene memorizzato quando il registro degli eventi di protezione è pieno e il relativo criterio di gestione specificato è **Non sovrascrivere eventi** o **Sovrascrivi eventi ogni giorno**.

Con questa impostazione di criterio abilitata, nel caso in cui il registro protezione sia pieno e non sia possibile sovrascrivere una voce esistente viene visualizzato il seguente messaggio di interruzione:

C0000244 {Controllo fallito}

Tentativo di generare un controllo della protezione fallito.

Per il ripristino, un amministratore deve eseguire l'accesso, archiviare il registro (facoltativo), cancellarlo e disattivare questa opzione per consentire al computer di essere riavviato. Potrebbe quindi essere necessario cancellare manualmente il contenuto del registro eventi protezione prima di configurare questa impostazione di criterio** **su **Abilitato.**

I possibili valori dell'impostazione **Controllo: arresto del sistema immediato se non è possibile registrare i controlli di protezione** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Se il computer non può memorizzare gli eventi nel registro protezione, dopo un problema di protezione non saranno disponibili elementi probatori fondamentali o informazioni importanti per la risoluzione dei problemi. Un pirata informatico potrebbe inoltre generare una grande quantità di messaggi del registro eventi protezione per forzare intenzionalmente l'arresto del computer.

##### Contromisura

Attivare l'impostazione **Arresta il sistema immediatamente se non è possibile registrare i controlli di protezione**.

##### Impatto potenziale

Gli oneri amministrativi derivanti dall'abilitazione di questa impostazione possono essere notevoli, specialmente se si configura anche l'opzione **Criteri** gestione registro protezione su **Non sovrascrivere eventi** **(pulizia manuale del registro)**. Questa configurazione consente di trasformare un pericolo di ripudio (un operatore di backup potrebbe negare di aver eseguito operazioni di backup o ripristino dei dati) in una vulnerabilità Denial of Service (DoS), in quanto è possibile provocare l'arresto forzato di un server sovraccaricandolo con eventi di accesso e altri eventi di protezione memorizzati nel registro protezione. Inoltre, poiché l'arresto è forzato, potrebbe determinare danni irreversibili al sistema operativo, alle applicazioni o ai dati. Sebbene il file system NTFS garantisca il mantenimento della propria integrità in caso di arresto forzato del sistema, non consente di assicurare che ogni file di dati di ciascuna applicazione sia ancora utilizzabile al riavvio del computer.

#### DCOM: limitazioni di accesso al computer in SDDL (Security Descriptor Definition language)

Questa impostazione di criterio consente agli amministratori di definire i controlli degli accessi distribuiti in tutto l'ambiente che regolano l'accesso a tutte le applicazioni DCOM (Distributed Component Object Model) su un computer. Questi controlli limitano la chiamata, l'attivazione, o la richiesta di avvio sul computer. Questi controlli degli accessi possono essere considerati una chiamata di controllo degli accessi aggiuntiva effettuata in un ACL (computer-wide access control list) su ogni chiamata, attivazione, o richiesta di avvio di qualsiasi server COM presente sul computer. Se il controllo degli accessi fallisce, la richiesta di avvio, attivazione o chiamata non verrà eseguita (questo controllo viene aggiunto a qualsiasi controllo degli accessi eseguito su ACL specifici dei server). Fornisce infatti uno standard di autorizzazione minimo che deve essere superato per poter accedere a qualsiasi server COM presente sul computer. L'impostazione **DCOM: limitazioni di accesso al computer in SDDL (Security Descriptor Definition language)** controlla che le autorizzazioni di accesso ricoprano i diritti di chiamata.

Gli ACL distribuiti in tutto l'ambiente consentono di ignorare le impostazioni di protezione deboli, specificate da una determinata applicazione attraverso CoInitializeSecurity, oppure mediante impostazioni di protezione specifiche dell'applicazione. Forniscono uno standard di protezione minimo che deve essere superato, indipendentemente dalle impostazioni del server specifico.

Gli ACL consentono all'amministratore di impostare i criteri di autorizzazione generali applicabili ai server COM del computer da una posizione centrale.

L'impostazione **DCOM: limitazioni di accesso al computer in SDDL (Security Descriptor Definition language)** consente di specificare un ACL in due modi diversi. È possibile inserire il descrittore di protezione nella SDDL oppure scegliere gli utenti e i gruppi cui concedere o negare le autorizzazioni di accesso locale e accesso remoto. Per specificare il contenuto dell'ACL da applicare con l'impostazione prescelta Microsoft consiglia di utilizzare l'interfaccia utente integrata.  

##### Vulnerabilità

Numerose applicazioni COM sono dotate di un codice specifico per la protezione (ad esempio, per richiamare CoInitializeSecurity), ma si servono di impostazioni deboli, che spesso concedono l'accesso non autenticato al processo. Gli amministratori non possono sovrascrivere queste impostazioni per imporre un maggior livello di protezione nelle versioni precedente, senza modificare l'applicazione. Un pirata informatico potrebbe tentare di sfruttare una protezione debole di una singola applicazione, attaccandola attraverso chiamate COM.

Inoltre, l'infrastruttura COM comprende l'RPCSS, un servizio di sistema che viene eseguito all'avvio del sistema e resta attivo durante la sessione. Questo servizio gestisce l'attivazione di oggetti COM e la tabella dell'oggetto in esecuzione e fornisce servizi Helper ai servizi remoti DCOM. Questo sistema visualizza le interfacce RPC che è possibile richiamare in modalità remota. Poiché alcuni server COM consentono l'accesso remoto non autenticato (come illustrato nella sezione precedente), queste interfacce possono essere chiamate da chiunque, compresi gli utenti non autorizzati. Di conseguenza, l'RPCSS può essere attaccato da utenti malintenzionati che si servono di computer remoti non autenticati.

##### Contromisura

Per proteggere le singole applicazioni o servizi COM, configurare l'impostazione **DCOM: limitazioni di accesso al computer in SDDL (Security Descriptor Definition language)** su un ACL appropriato distribuito in tutto l'ambiente.

##### Impatto potenziale

Windows XP con SP2 e Windows Server 2003 con SP1 implementano ACL COM predefinite, come specificato nella rispettiva documentazione. Se un server COM viene implementato e vengono sovrascritte le impostazioni di protezione predefinite, confermare che l'ACL delle autorizzazioni di chiamata specifica dell'applicazione assegni l'autorizzazione corretta agli utenti appropriati. In caso contrario, per fornire agli utenti appropriati i diritti di attivazione, in modo che le applicazioni e i componenti di Windows che utilizzano DCOM possano funzionare correttamente, sarà necessario modificare l'ACL dell'autorizzazione specifica dell'applicazione.

**Nota**: per maggiori informazioni sulle limitazioni di accesso predefinite del computer COM applicate a Windows XP con SP2, vedere la guida "[Managing Windows XP Service Pack 2 Features Using Group Policy](http://technet.microsoft.com/en-us/library/bb491069.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/winxppro/maintain/mangxpsp2/mngsecps.mspx. Per informazioni sulle restrizioni applicate in Windows Server 2003 con SP1, consultare la sezione "DCOM Security Enhancements" della guida "[Changes to Functionality in Microsoft Windows Server 2003 Service Pack 1](http://technet.microsoft.com/en-us/library/cc784458.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/
BookofSP1/ed9975ba-3933-4e28-bcb4-72b80d7865b7.mspx. Per maggiori informazioni sulle autorizzazioni di avvio, vedere la pagina “[LaunchPermission](http://technet.microsoft.com/en-us/library/cc738214.aspx)” su Microsoft MSDN all'indirizzo http://go.microsoft.com/fwlink/?LinkId=20924.

#### DCOM: limitazioni di avvio del computer in SDDL (Security Descriptor Definition Language)

Questa impostazione di criterio è simile all'impostazione **DCOM: limitazioni di avvio del computer in SDDL (Security Descriptor Definition Language)** poiché consente agli amministratori di definire i controlli degli accessi distribuiti in tutto l'ambiente che regolano l'accesso a tutte le applicazioni DCOM (Distributed Component Object Model) su un computer. Tuttavia, gli ACL specificati in *questa* impostazione di criterio controllano le *richieste di avvio* (non le richieste di accesso) COM locali e remote sul computer. Questo controllo degli accessi può essere considerato come una chiamata di controllo degli accessi aggiuntiva effettuata in un ACL su ogni richiesta di avvio di qualsiasi server COM presente sul computer. Se il controllo degli accessi fallisce, la richiesta di avvio, attivazione o chiamata non verrà eseguita. (Questo controllo viene aggiunto a qualsiasi controllo degli accessi eseguito su ACL specifici dei server). Fornisce infatti uno standard di autorizzazione minimo che deve essere superato per poter avviare qualsiasi server COM presente sul computer. Il primo criterio differisce da questo perché fornisce un controllo degli accessi minimo, applicato ai tentativi di connessione a un server COM già avviato.

Gli ACL distribuiti in tutto l'ambiente consentono di ignorare le impostazioni di protezione deboli, specificate da una determinata applicazione attraverso CoInitializeSecurity, oppure mediante impostazioni di protezione specifiche dell'applicazione. Forniscono uno standard di protezione minimo che deve essere superato, indipendentemente dalle impostazioni del server COM specifico. Gli ACL consentono all'amministratore di impostare i criteri di autorizzazione generali applicabili ai server COM del computer da una posizione centrale.

L'impostazione **DCOM: limitazioni di avvio del computer in SDDL (Security Descriptor Definition Language)** consente di specificare un ACL in due modi diversi. È possibile inserire il descrittore di protezione nella SDDL oppure scegliere gli utenti e i gruppi cui concedere o negare le autorizzazioni di accesso locale e accesso remoto. Per specificare il contenuto dell'ACL da applicare con l'impostazione prescelta Microsoft consiglia di utilizzare l'interfaccia utente integrata.

##### Vulnerabilità

Numerose applicazioni COM sono dotate di un codice specifico per la protezione (ad esempio, per richiamare CoInitializeSecurity), ma si servono di impostazioni deboli, che spesso concedono l'accesso non autenticato al processo. Gli amministratori non possono sovrascrivere queste impostazioni per imporre un maggior livello di protezione nelle versioni precedente, senza modificare l'applicazione. Un pirata informatico potrebbe tentare di sfruttare una protezione debole di una singola applicazione, attaccandola attraverso chiamate COM.

Inoltre, l'infrastruttura COM comprende l'RPCSS, un servizio di sistema che viene eseguito all'avvio del sistema e resta attivo durante la sessione. Questo servizio gestisce l'attivazione di oggetti COM e la tabella dell'oggetto in esecuzione e fornisce servizi Helper ai servizi remoti DCOM. Questo sistema visualizza le interfacce RPC che è possibile richiamare in modalità remota. Poiché alcuni server COM consentono un'attivazione del componente remoto non autorizzata (come spiegato nella sezione precedente), queste interfacce possono essere chiamate da chiunque, compresi gli utenti non autorizzati. Di conseguenza, l'RPCSS può essere attaccato da utenti malintenzionati che si servono di computer remoti non autenticati.

##### Contromisura

Per proteggere le singole applicazioni o servizi basati su COM, configurare l'impostazione **DCOM: limitazioni di avvio del computer in SDDL (Security Descriptor Definition Language)** su un ACL appropriato distribuito in tutto l'ambiente.

##### Impatto potenziale

Windows XP con SP2 e Windows Server 2003 con SP1 implementano ACL COM predefinite, come specificato nella rispettiva documentazione. Se un server COM viene implementato e vengono sovrascritte le impostazioni di protezione predefinite, confermare che l'ACL delle autorizzazioni di avvio specifiche dell'applicazione assegni l'autorizzazione di attivazione agli utenti appropriati. In caso contrario, per fornire agli utenti appropriati i diritti di attivazione, in modo che le applicazioni e i componenti di Windows che utilizzano DCOM possano funzionare correttamente, sarà necessario modificare l'ACL dell'autorizzazione di avvio specifico dell'applicazione.

**Nota**: per ulteriori informazioni sulle limitazioni di avvio predefinite del computer COM applicate a Windows XP con SP2, vedere la guida "[Managing Windows XP Service Pack 2 Features Using Group Policy](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/sp2/mngsecps.mspx)" (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/winxppro/maintain/mangxpsp2/mngsecps.mspx. Per informazioni sulle restrizioni applicate in Windows Server 2003 con SP1, consultare la sezione "DCOM Security Enhancements" della guida "[Changes to Functionality in Microsoft Windows Server 2003 Service Pack 1](http://technet.microsoft.com/it-it/library/cc784458.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/
BookofSP1/ed9975ba-3933-4e28-bcb4-72b80d7865b7.mspx. Per maggiori informazioni sulle autorizzazioni di avvio, vedere la pagina “[LaunchPermission](http://technet.microsoft.com/en-us/library/cc738214.aspx)” su MSDN all'indirizzo http://go.microsoft.com/fwlink/?LinkId=20924.

#### Periferiche: consenti il disinserimento senza dover effettuare l'accesso

Questa impostazione di criterio determina se un utente deve eseguire o meno l'accesso al fine di richiedere l'autorizzazione necessaria per rimuovere un computer portatile da un alloggiamento di espansione. Se questa impostazione di criterio viene attivata, gli utenti potranno premere il pulsante di rimozione di un computer portatile per rimuovere in modo sicuro il computer dall'alloggiamento. Se questa impostazione di criterio viene disattivata, l'utente deve eseguire l'accesso in modo da ottenere l'autorizzazione per il disinserimento. Solo gli utenti che dispongono del privilegio **Rimozione del computer dall'alloggiamento** possono ottenere tale autorizzazione.

**Nota**: è consigliabile disabilitare questa impostazione solo per i computer portatili che non è possibile rimuovere meccanicamente. I computer che è possibile rimuovere meccanicamente possono essere rimossi fisicamente dall'utente indipendentemente dall'utilizzo della funzione di disinserimento di Windows.

I possibili valori dell'impostazione **Periferiche: consenti il disinserimento senza dover effettuare l'accesso** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Se si abilita questa impostazione, qualsiasi utente in grado di accedere fisicamente ai computer portatili inseriti nell'alloggiamento di espansione può rimuoverli ed eventualmente manometterli. Questa impostazione di criterio non avrà alcun effetto sui computer privi di alloggiamento di espansione.

##### Contromisura

Disattivare l'impostazione **Periferiche: consenti il disinserimento senza dover effettuare l'accesso**.

##### Impatto potenziale

Gli utenti che hanno inserito i propri computer nell'alloggiamento di espansione dovranno eseguire l'accesso alla console locale prima di poterli rimuovere.

#### Periferiche: è consentita la formattazione e la rimozione dei supporti rimovibili

Questa impostazione di criterio determina chi può formattare e rimuovere supporti removibili.

I possibili valori dell'impostazione **Periferiche: è consentita la formattazione e la rimozione dei supporti rimovibili** sono:

-   Amministratori

-   Administrators e Power Users

-   Administrators e Interactive Users

-   Non definito

##### Vulnerabilità

Gli utenti possono spostare dati su dischi rimovibili in un computer diverso per cui dispongono di privilegi amministrativi. Quindi possono diventare proprietari di qualsiasi file, assegnarsi il controllo completo e visualizzare o modificare qualsiasi file. Il vantaggio di questa impostazione è limitato dal fatto che la maggior parte delle periferiche di archiviazione rimovibili consente l'espulsione dei supporti mediante un apposito pulsante.

##### Contromisura

Configurare l'impostazione **è consentita la formattazione e la rimozione dei supporti rimovibili** su **Administrators.**

##### Impatto potenziale

Solo gli amministratori potranno estrarre i supporti rimovibili NTFS.

#### Periferiche: non consentire agli utenti di installare i driver della stampante

Per utilizzare una stampante di rete, è necessario installare il relativo driver nel computer locale. L'impostazione **Periferiche: non consentire agli utenti di installare i driver** della stampante consente di stabilire gli utenti autorizzati a installare un driver di stampante durante l'aggiunta di una stampante di rete. Se questa impostazione di criterio viene abilitata, soltanto i membri dei gruppi **Administrators** e **Power User** potranno installare un driver di stampante durante l'aggiunta di una stampante di rete. Se questa impostazione di criterio viene disabilitata, qualsiasi utente può installare i driver di stampante durante l'aggiunta di una stampante di rete. Questa impostazione impedisce agli utenti normali di scaricare e installare un driver di stampante non attendibile.

**Nota**: questa impostazione non avrà alcun effetto se un amministratore ha configurato un percorso di trust per il download dei driver. In caso di utilizzo di percorsi di trust, il sottosistema di stampa tenta di scaricare il driver attraverso tali percorsi. Se il download basato sui percorsi di trust ha esito positivo, il driver viene installato per conto di qualsiasi utente. In caso contrario, il driver non viene installato e la stampante non viene aggiunta.

I possibili valori dell'impostazione **Periferiche: non consentire agli utenti di installare i driver della stampante** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

In alcune organizzazioni può essere opportuno consentire agli utenti di installare i driver delle stampanti nelle relative workstation. Tuttavia, è necessario impedire agli utenti di effettuarlo sui server. L'installazione di un driver di stampante in un server potrebbe determinare accidentalmente una minore stabilità del computer. Nei server, questo privilegio deve essere assegnato solo agli amministratori. Un utente malintenzionato potrebbe tentare deliberatamente di danneggiare il computer installando driver di stampanti non appropriati, oppure un utente potrebbe inconsapevolmente installare codice dannoso mascherato da driver di stampante.

##### Contromisura

Configurare l'impostazione **Periferiche: non consentire agli utenti di installare i driver della stampante** su **Abilitato.**

##### Impatto potenziale

Solo gli utenti con i privilegi Administrators, Power Users o Server Operators potranno installare le stampanti nei server. Se questo criterio è abilitato ma nel computer locale esiste già il driver di una stampante di rete, gli utenti possono comunque aggiungere la stampante di rete.

#### Periferiche: limita accesso al CD-ROM agli utenti che hanno effettuato l'accesso locale

determina se un CD-ROM è accessibile contemporaneamente agli utenti sia locali che remoti. L'attivazione di questa impostazione consente ai soli utenti connessi interattivamente di accedere ai supporti nell'unità CD-ROM. Se questo criterio è abilitato e nessun utente è connesso interattivamente, è possibile accedere al CD–ROM in rete.

I possibili valori dell'impostazione **Periferiche: limita accesso al CD-ROM agli utenti che hanno effettuato l'accesso locale** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Un utente remoto potrebbe accedere potenzialmente a un CD-ROM montato con all'interno informazioni importanti Il rischio è contenuto poiché le unità CD-ROM non sono disponibili automaticamente come condivisioni di rete, gli amministratori devono scegliere deliberatamente di condividere tali unità. Tuttavia, gli amministratori possono negare agli utenti la possibilità di visualizzare dati o eseguire applicazioni dai supporti rimovibili sul server.

##### Contromisura

Abilitare l'impostazione **Periferiche: limita accesso al CD-ROM agli utenti che hanno effettuato l'accesso locale**.

##### Impatto potenziale

Gli utenti che si connettono al server in rete non potranno utilizzare nessuna unità CD-ROM installata nel server quando un altro utente sta utilizzando la console locale del server. Gli strumenti di sistema che richiedono l'accesso all'unità CD-ROM non funzioneranno correttamente. Ad esempio, quando viene inizializzato, il servizio Copia shadow del volume tenta di accedere a tutte le unità CD-ROM e floppy presenti sul computer e, se il servizio non può accedere a una di queste unità, non funzionerà correttamente. Questa condizione provocherà un errore nell'utilità di backup di Windows se sono state specificate copie shadow del volume per il processo di backup. Anche i prodotti di backup di terze parti che utilizzano le copie shadow del volume non funzioneranno. Questa impostazione non è adatta nel caso di un computer che svolga la funzione di juke-box di CD per gli utenti della rete.

#### Periferiche: limita accesso al disco floppy agli utenti che hanno effettuato l'accesso locale

determina se un supporto floppy rimovibile è accessibile contemporaneamente agli utenti sia locali che remoti. L'attivazione di questa impostazione consente ai soli utenti connessi interattivamente di accedere ai supporti floppy rimovibili. Se questo criterio è abilitato e nessun utente è connesso interattivamente, è possibile accedere ai dischi floppy in rete.

I possibili valori dell'impostazione **Periferiche: limita accesso al disco floppy agli utenti che hanno effettuato l'accesso locale** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Un utente remoto potrebbe accedere a un floppy montato che contiene informazioni importanti. Il rischio è contenuto poiché le unità floppy non sono disponibili automaticamente come condivisioni di rete, gli amministratori devono scegliere deliberatamente di condividere tali unità. Tuttavia, gli amministratori possono negare agli utenti la possibilità di visualizzare dati o eseguire applicazioni dai supporti rimovibili sul server.

##### Contromisura

Abilitare l'impostazione **Limita accesso al disco floppy agli utenti che hanno effettuato l'accesso locale**.

##### Impatto potenziale

Gli utenti che si connettono al server in rete non potranno utilizzare nessuna unità floppy installata nel server quando un altro utente sta utilizzando la console locale del server. Gli strumenti di sistema che richiedono l'accesso alle unità floppy non funzioneranno correttamente. Ad esempio, quando viene inizializzato, il servizio Copia shadow del volume tenta di accedere a tutte le unità CD-ROM e floppy presenti sul computer e, se il servizio non può accedere a una di queste unità, non funzionerà correttamente. Questa condizione provocherà un errore nell'utilità di backup di Windows se sono state specificate copie shadow del volume per il processo di backup. Anche i prodotti di backup di terze parti che utilizzano le copie shadow del volume non funzioneranno.

#### Periferiche: funzionamento installazione driver privo di firma digitale

Questa impostazione di criterio determina l'azione conseguente a un tentativo di installazione di un driver di periferica che non è stato certificato né dotato di firma digitale WHQL (Windows Hardware Quality Lab) mediante l'interfaccia API (Application Programming Interface) del programma di installazione.

I possibili valori dell'impostazione **Periferiche: funzionamento installazione driver privo di firma digitale** sono:

-   Installa senza avvisare

-   Avvisa ma consenti installazione

-   Non consentire installazione

-   Non definito

##### Vulnerabilità

Questa impostazione di criterio consente di impedire l'installazione di driver privi di firma digitale oppure di avvisare l'amministratore che è in corso un tentativo di installazione di un driver privo di firma digitale. Questa funzionalità può impedire l'utilizzo dell'API del programma di installazione per installare driver non certificati per Windows XP o Windows Server 2003. Questa impostazione non è in grado di assicurare la protezione da un metodo utilizzato da strumenti di attacco, che prevedono la copia e la registrazione di file dannosi con estensione sys per avviarne l'esecuzione come servizi di sistema.

##### Contromisura

Configurare l'impostazione **Periferiche: funzionamento installazione driver privo di firma digitale** su **Avvisa ma consenti installazione**, configurazione predefinita in Windows XP con SP2. La configurazione predefinita in Windows Server 2003 è **Non definito.**

##### Impatto potenziale

Gli utenti con privilegi sufficienti per l'installazione dei driver di periferica potranno installare driver privi di firma digitale. Tuttavia, tale operazione potrebbe causare problemi di stabilità nei server. Un altro possibile problema con una configurazione **Avvisa ma consenti installazione** consiste nel fatto che non è possibile eseguire script di installazione automatica se si tenta di installare driver privi di firma digitale.

#### Controller di dominio: consente agli operatori dei server di pianificare le operazioni

Questa impostazione di criterio determina se Server Operator è consentito inviare processi mediante la funzione di pianificazione AT.

**Nota**: questa impostazione di opzione di protezione influisce solo sulla funzionalità di pianificazione AT; non ha effetto invece sull'Utilità di pianificazione.

I possibili valori dell'impostazione **Controller di dominio: consente agli operatori dei server di pianificare le operazioni** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Se si abilita questa impostazione, i processi creati dagli operatori dei server tramite il servizio AT verranno eseguiti nel contesto dell'account di gestione di tale servizio, che, per impostazione predefinita, corrisponde all'account SYSTEM locale. Se si abilita questa impostazione di criterio, gli operatori dei server possono eseguire le attività consentite all'account SYSTEM, ma per le quali non sono generalmente autorizzati, ad esempio l'aggiunta del proprio account al gruppo **Administrators** locale.

##### Contromisura

Disattivare l'impostazione **Controller di dominio: consente agli operatori dei server di pianificare le operazioni**.

##### Impatto potenziale

L'impatto dovrebbe essere minimo per la maggior parte delle autorizzazioni. Gli utenti (compresi quelli nel gruppo **Server Operators**) potranno comunque creare processi tramite l’Utilità di pianificazione. Tuttavia, questi processi verranno eseguiti nel contesto dell’account con cui l'utente è stato autenticato quando ha impostato il processo.

#### Controller di dominio: requisiti di accesso al server LDAP

Questa impostazione di criterio determina se il server LDAP (Lightweight Directory Access Protocol) richiede o meno ai client LDAP di negoziare la firma dei dati.

I possibili valori dell'impostazione **Controller di dominio: requisiti di accesso al server LDAP** sono:

-   **Nessuno**. Per il binding con il server non sono necessarie le firme dei dati. Se il client la richiede, il server è comunque il grado di supportarla.

-   **Richiedi firma**. L'opzione per la firma dei dati LDAP deve essere negoziata, a meno che venga utilizzato il protocollo TLS/SSL (Transport Layer Security/Secure Socket Layer).

-   **Non definito**.

##### Vulnerabilità

Il traffico di rete privo di firma è esposto ad attacchi di tipo "man-in-the-middle". Sono attacchi in cui un intruso prende possesso dei pacchetti inviati dal server al client e li modifica prima di inoltrarli al client. Di conseguenza, nel caso di un server LDAP, un pirata informatico potrebbe indurre un client a prendere decisioni sulla base di record falsi della directory LDAP. È possibile ridurre il rischio di questo tipo di intrusione in una rete aziendale implementando misure di protezione fisica efficaci a tutela dell'infrastruttura di rete. Inoltre è possibile ostacolare in modo significativo l'esecuzione degli attacchi di tipo "man-in-the-middle" implementando la modalità AH (Authentication Header) della tecnologia IPSec, che esegue l'autenticazione reciproca e la funzionalità Integrità pacchetto per il traffico IP (Internet Protocol).

##### Contromisura

Configurare l'impostazione **Controller di dominio: requisiti di accesso al server LDAP** su **Richiedi firma.**

##### Impatto potenziale

I client che non supportano la firma LDAP non potranno eseguire le query LDAP ai controller di dominio. Tutti i computer dell'organizzazione con Windows 2000 e gestiti da Windows Server 2003 o da computer basati su Windows XP e che utilizzano l'autenticazione Challenge/Response (NTLM) di Windows NT devono avere Windows 2000 Service Pack 3 (SP3) installato. In alternativa, è necessario apportare al Registro di sistema di questi client la modifica descritta nell'articolo Q325465 della Microsoft Knowledge Base "[I controller di dominio Windows 2000 richiedono SP3 o versione successiva per utilizzare gli strumenti di amministrazione di Windows Server 2003](http://support.microsoft.com/default.aspx?scid=325465)" disponibile all'indirizzo http://support.microsoft.com/default.aspx?scid=325465. Inoltre, alcuni sistemi operativi di terze parti non supportano la firma LDAP. Se questa impostazione di criterio viene abilitata, i computer client che utilizzano tali sistemi operativi potrebbero non riuscire ad accedere alle risorse del dominio.

#### Controller di dominio: rifiuta cambio password account computer

Questa impostazione di criterio determina se un controller di dominio accetterà o meno le richieste di modifica della password per gli account dei computer.

I possibili valori dell'impostazione **Controller di dominio: rifiuta cambio password account computer** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Se si attiva questa impostazione di criterio su tutti i controller di dominio di un dominio, i membri del dominio non saranno in grado di modificare le password degli account del computer, che saranno così più suscettibili agli attacchi.

##### Contromisura

Disattivare l'impostazione **Controller di dominio: rifiuta cambio password account computer**.

##### Impatto potenziale

Nessuno. Si tratta della configurazione predefinita.

#### Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (più impostazioni correlate)

Le impostazioni seguenti determinano se è possibile stabilire o meno un canale protetto con un controller di dominio che non è in grado di firmare o crittografare il traffico di tale canale:

-   **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)**

-   **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)**

-   **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)**

Se l'impostazione **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)** si impedisce di stabilire un canale protetto con qualsiasi controller di dominio che non è in grado di firmare o crittografare tutti i dati di tale canale.

Per proteggere il traffico di autenticazione da attacchi di rete "man-in-the-middle", di riproduzione e di altro tipo, i computer Windows creano un canale di comunicazione denominato "canale protetto" attraverso NetLogon. Tali canali autenticano account computer e account utente presenti in un dominio trusted quando un utente remoto si connette a una risorsa di rete. Tale processo di autenticazione, chiamato autenticazione pass-through, consente a un computer aggiunto a un dominio di accedere al database di account utente nel dominio di appartenenza e in qualsiasi dominio trusted.

**Nota**: per attivare l'impostazione **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)** in una workstation o in un server membro, è necessario che tutti i controller del dominio a cui appartiene il membro siano in grado di firmare o crittografare i dati del canale protetto. Questo requisito richiede quindi che tutti questi controller di dominio eseguano Windows NT 4.0 con Service Pack 6a o una versione successiva del sistema operativo Windows.

Se l'impostazione **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)** viene attivata, **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)** viene automaticamente attivato.

I possibili valori per questa impostazione di criterio sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Quando un computer Windows Server 2003, Windows XP, Windows 2000, o Windows NT entra a far parte di un dominio, viene creato un account computer. Dopo l'aggiunta al dominio, ad ogni riavvio il computer utilizza la password di tale account per creare un canale protetto con il controller del proprio dominio di appartenenza. Le richieste inviate sul canale protetto vengono autenticate e le informazioni riservate (ad esempio le password) vengono crittografate, ma l'integrità del canale non viene controllata e non tutte le informazioni vengono crittografate. Se un computer è configurato per crittografare o firmare *sempre* i dati del canale protetto ma il controller di dominio non è in grado di firmare o crittografare alcuna parte di tale canale, il computer ed il controller di dominio non possono stabilire un canale protetto. Nel caso in cui il computer sia configurato per crittografare o firmare i dati del canale protetto *quando è possibile*, il canale protetto viene stabilito ma è necessario negoziare il livello di crittografia e di firma.

##### Contromisura

-   Configurare l'impostazione **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)** su **Abilitato.**

-   Configurare l'impostazione **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)** su **Abilitato.**

-   Configurare l'impostazione **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)** su **Abilitato.**

##### Impatto potenziale

Se supportate, la crittografia e la firma digitale del "canale protetto" rappresentano una scelta ottimale. Attraverso il canale protetto, le credenziali di dominio vengono tutelate durante l'invio al controller di dominio. Tuttavia, soltanto Windows NT 4.0 Service Pack 6a (SP6a) e le versioni successive del sistema operativo Windows supportano la crittografia e la firma digitale del canale protetto. I client Windows 98 Second Edition non supportano tali funzionalità, a meno che non sia installato Dsclient. Non è quindi possibile abilitare l'impostazione **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (sempre)** sui controller di dominio che supportano i client Windows 98 clienti come membri del dominio. Gli impatti potenziali possono includere:

-   la possibilità di disattivare l'opzione per la creazione o l'eliminazione delle relazioni di trust di livello inferiore.

-   La disattivazione degli accessi dai client di livello inferiore.

-   La disattivazione della capacità di autenticare gli utenti di altri domini da un dominio trusted di livello inferiore.

È possibile abilitare questo criterio dopo aver eliminato tutti i client Windows 9x dal dominio e aver aggiornato tutti i server Windows NT 4.0 e i controller di dominio da domini trusted o trusting a Windows NT 4.0 SP6a. È possibile attivare le altre due impostazioni di criterio, **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale protetto (quando possibile)** e **Membro di dominio: aggiunta crittografia o firma digitale ai dati del canale (quando possibile)**, in tutti i computer del dominio che le supportano senza influire sui client e sulle applicazioni di livello inferiore.

#### Membro di dominio: disabilitazione cambio password account computer

Questa impostazione di criterio determina se un membro di dominio può modificare periodicamente la password dell'account del computer. Se si attiva questa impostazione di criterio, il membro di dominio non può modificare la password dell'account del computer. Se si disattiva questa impostazione di criterio, il membro di dominio può modificare la password dell'account del computer come specificato dall'impostazione **Membro di dominio: validità massima password account computer**, ovvero ogni 30 giorni per impostazione predefinita.

**Avviso**: non abilitare questa impostazione. Le password degli account dei computer vengono utilizzare per stabilire comunicazioni basate su un canale protetto tra i membri e i controller di dominio nonché, all'interno del dominio, tra i controller di dominio stessi. Dopo aver stabilito tali comunicazioni, il canale protetto trasmette informazioni riservate necessarie per fini di autenticazione e autorizzazione.

Non utilizzare questo criterio al fine di supportare scenari di avvio multiplo basati sullo stesso account del computer. Per supportare tale scenario per due installazioni aggiunte allo stesso dominio, assegnare nomi di computer diversi alle due installazioni. Questa impostazione è stata introdotta in Windows per agevolare le organizzazioni in cui vengono accumulati computer già predisposti da inserire successivamente in produzione. Non sarà quindi necessario aggiungere nuovamente tali computer al dominio. Questa impostazione di criterio viene a volte utilizzata anche con computer preconfigurati o in cui si impedisce la modifica a livello di software o hardware. Le procedure di acquisizione immagini corrette utilizzano questo criterio, non necessario per i computer preconfigurati.

I possibili valori dell'impostazione **Membro di dominio: disabilitazione cambio password account computer** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

La configurazione predefinita per i computer che eseguono Windows Server 2003 e appartengono a un dominio prevede ogni 30 giorni la modifica automatica delle password per i relativi account. Se questa impostazione di criterio viene disattivata, i computer che eseguono Windows Server 2003 conserveranno le stesse password per i relativi account. I computer che non possono più modificare automaticamente la password del proprio account sono esposti ad attacchi da parte di pirati informatici, che possono determinare la password relativa all'account di dominio del computer.

##### Contromisura

Verificare che l'impostazione **Membro di dominio:disabilitazione cambio password account computer** sia configurata su **Disabilitato.**

##### Impatto potenziale

Nessuno. Si tratta della configurazione predefinita.

#### Membro di dominio: validità massima password account computer

Questa impostazione di criterio determina la durata massima consentita alla password dell'account di un computer. Questa impostazione viene applicata anche ai computer con sistema operativo Windows 2000, ma in tal caso non è disponibile tramite gli strumenti per la gestione della configurazione della protezione.

I possibili valori dell'impostazione **Membro di dominio: validità massima password account computer** sono:

-   Un numero di giorni specificato dall'utente compreso tra 0 e 999

-   Non definito

##### Vulnerabilità

Nei domini di Active Directory, ogni computer dispone di un account e di una password esattamente come un utente. Per impostazione predefinita, le password dei membri di dominio vengono modificate automaticamente ogni 30 giorni. Se si aumenta in modo significativo tale intervallo o si imposta il numero di giorni su 0 in modo che i computer non possano più modificare le password, i pirati informatici avranno a disposizione più tempo per eseguire un attacco di tipo "brute force" contro gli account dei computer.

##### Contromisura

Configurare l'impostazione **Membro di dominio: validità massima password account computer** su 30 giorni.

##### Impatto potenziale

Nessuno. Si tratta della configurazione predefinita.

#### Membro di dominio: chiave di sessione avanzata (Windows 2000 o versioni successive)

Questa impostazione di criterio determina se è possibile stabilire o meno un canale protetto con un controller di dominio che non è in grado di crittografare il traffico di tale canale con una chiave di sessione avanzata a 128 bit. Se si abilita questa impostazione, si impedisce di stabilire un canale protetto con qualsiasi controller di dominio che non sia in grado di crittografare i dati di tale canale con una chiave avanzata. Se si disattiva questa impostazione di criterio, è possibile utilizzare chiavi di sessione a 64 bit.

**Nota**: per abilitare questa impostazione in una workstation o in un server membro, è necessario che tutti i controller di dominio a cui appartiene il membro siano in grado di crittografare i dati del canale protetto con una chiave avanzata a 128 bit. Tutti questi controller di dominio devono quindi eseguire Windows 2000 o una versione successiva del sistema operativo Windows.

I possibili valori dell'impostazione **Membro di dominio: chiave di sessione avanzata (Windows** **2000 o versioni successive)** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Le chiavi di sessione utilizzate per stabilire comunicazioni basate su un canale protetto tra i controller di dominio e i computer membro sono di gran lunga più avanzate in Windows 2000 che nei sistemi operativi Microsoft precedenti.

Se possibile, sfruttare i vantaggi offerti dalle chiavi di sessione avanzate per tutelare le comunicazioni basate su un canale protetto da attacchi che tentano di dirottare le sessioni di rete e di effettuare intercettazioni. (L'intercettazione è una forma di pirateria informatica che consiste nella lettura o nell'alterazione dei dati di rete durante il relativo trasferimento. I dati possono essere modificati per nascondere o cambiare il mittente oppure per reindirizzarli).

##### Contromisura

Configurare l'impostazione **Membro di dominio: chiave di sessione avanzata (Windows** **2000 o versioni successive)** su **Abilitato.**

se questo criterio è attivato, tutto il traffico del canale protetto in uscita richiederà una chiave di crittografia complessa (Windows 2000 o versioni successive). Se questo criterio è disattivato, la forza della chiave viene negoziata. Abilitare questa impostazione di criterio solo se i controller di dominio di tutti i domini trusted supportano chiavi avanzate. Per impostazione predefinita, questo criterio è disattivato.

##### Impatto potenziale

I computer in cui questa impostazione di criterio è attivata, non potranno essere aggiunti nei domini Windows NT 4.0 e i trust tra i domini Active Directory e i domini di tipo Windows NT potrebbero non funzionare correttamente. Inoltre, i computer che non supportano questa impostazione di criterio non potranno essere aggiunti ai domini che includono controller di dominio in cui è abilitato tale criterio.

#### Accesso interattivo: non visualizzare l'ultimo nome utente

Determina se il nome dell'ultimo utente che ha eseguito l'accesso al computer viene visualizzato o meno nella finestra di dialogo **Accesso a Windows**. Se si abilita questa impostazione, il nome dell'ultimo utente che ha eseguito l'accesso non verrà visualizzato nella finestra Accesso a Windows. Se si disabilita questa impostazione, verrà visualizzato il nome dell'ultimo utente che ha eseguito l'accesso.

I possibili valori dell'impostazione **Accesso interattivo: non visualizzare l'ultimo nome utente** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Un pirata informatico con accesso alla console, ad esempio una persona che può accedervi fisicamente o è in grado di connettersi al server tramite i Servizi terminal, potrebbe visualizzare il nome dell'ultimo utente che ha eseguito l'accesso al server. Per cercare di accedere, il pirata informatico potrebbe quindi tentare di decifrare la password, di utilizzare un dizionario, o di eseguire un attacco di tipo "brute force".

##### Contromisura

Configurare l'impostazione **Non visualizzare l'ultimo nome utente nella schermata di accesso** su **Abilitato.**

##### Impatto potenziale

Gli utenti dovranno digitare sempre i relativi nomi utente durante l'accesso ai server.

#### Accesso interattivo: non richiedere CTRL + ALT + CANC

Questa impostazione di criterio determina se gli utenti devono premere CTRL + ALT + CANC prima di effettuare l'accesso. Se si attiva questa impostazione di criterio, gli utenti possono effettuare l'accesso senza immettere questa combinazione di tasti. Se si disattiva questa impostazione di criterio, gli utenti devono premere CTRL+ALT+CANC prima di effettuare l'accesso a Windows a meno che non utilizzino una smart card per l’accesso a Windows. Una smart card è un token a prova di manomissione in cui vengono archiviate informazioni di protezione.

I possibili valori dell'impostazione **Accesso interattivo: non richiedere CTRL + ALT + CANC** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Microsoft ha sviluppato questa funzionalità per facilitare l'accesso di utenti con determinati tipi di problemi fisici ai computer che eseguono Windows. Se non è necessario che gli utenti immettano CTRL+ALT+CANC, potrebbero essere esposti ad attacchi di intercettazione delle password. Se prima di effettuare l'accesso è necessario immettere CTRL+ALT+CANC, le password degli utenti vengono comunicate tramite un percorso di trust.

Un pirata informatico potrebbe installare un programma cavallo di Troia identico in apparenza alla finestra di dialogo standard per l'accesso a Windows, in modo da acquisire la password dell'utente. Quindi potrebbe accedere all'account compromesso con qualsiasi livello di privilegio concesso a tale utente.

##### Contromisura

Configurare l'impostazione **Disabilita requisito di accesso CTRL+ALT+CANC** su **Disabilitato.**

##### Impatto potenziale

A meno che utilizzino una smart card per l'accesso, gli utenti devono premere contemporaneamente tre tasti prima che venga visualizzata la finestra di dialogo di accesso.

#### Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso

Le impostazioni **Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso** e **Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso** sono strettamente correlate. La prima impostazione di criterio consente di specificare un messaggio di testo che viene visualizzato agli utenti quando effettuano l'accesso, mentre la seconda consente di specificare il titolo da visualizzare nella barra del titolo della finestra che contiene il messaggio di testo. Molte organizzazioni utilizzano questo testo per motivi legali, ad esempio per informare gli utenti delle conseguenze di un uso improprio delle informazioni aziendali o per avvisarli che le loro azioni potrebbero essere controllate.

**Avviso:** Windows XP Professional include il supporto per la configurazione delle intestazioni di accesso, che possono superare la lunghezza di 512 caratteri e contengono inoltre sequenze di avanzamento riga e ritorno a capo. Tuttavia, i client Windows 2000 non possono interpretare e visualizzare il testo del messaggio. Per creare criteri relativi al messaggio di accesso applicabili ai computer che eseguono Windows 2000, è necessario utilizzare computer basati su tale sistema operativo. Se i criteri relativi al messaggio di accesso vengono creati accidentalmente in un computer con sistema operativo Windows XP Professional e il messaggio non viene visualizzato correttamente nei computer basati su Windows 2000, attenersi alla seguente procedura:

-   Riconfigurare l'impostazione su **Non definito.**

-   Configurare nuovamente l'impostazione utilizzando un computer con sistema operativo Windows 2000.

Non è sufficiente modificare l'impostazione del messaggio di accesso definita in Windows  XP Professional su un computer Windows 2000. È necessario per prima cosa riconfigurare l'impostazione su **Non definito.**

I possibili valori per queste impostazioni di criterio sono:

-   Testo definito dall'utente

-   Non definito

##### Vulnerabilità

La visualizzazione di un messaggio prima dell'accesso può consentire di evitare un attacco avvisando il pirata informatico della sua azione prima che avvenga. Può inoltre rafforzare i criteri aziendali, comunicando ai dipendenti i criteri appropriati durante il processo di accesso.

##### Contromisura

Configurare le impostazioni **Testo del messaggio per gli utenti che tentano l'accesso** e **Titolo del messaggio per gli utenti che tentano l'accesso** su un valore appropriato per l'organizzazione.

**Nota**: qualsiasi avviso visualizzato deve essere approvato dai responsabili legali e del personale dell'organizzazione.

##### Impatto potenziale

Prima che gli utenti possano accedere alla console del server, verrà visualizzata una finestra di dialogo con un messaggio.

#### Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)

Questa impostazione di criterio determina il numero di utenti univoci che possono accedere a un dominio Windows utilizzando le informazioni sull'account memorizzate nella cache. Le informazioni di accesso per gli account di domino possono essere memorizzate nella cache locale, in modo che un utente possa accedere comunque anche se non è possibile contattare un controller di dominio per gli accessi successivi. Questa impostazione di criterio determina il numero di utenti univoci di cui è possibile memorizzare le informazioni di accesso nella cache locale.

Se non è disponibile un controller di dominio e le informazioni di accesso dell'utente sono memorizzate nella cache verrà visualizzato il seguente messaggio:

Impossibile contattare il controller di dominio per questo dominio. L'accesso è avvenuto in base a informazioni sull'account presenti nella memoria cache. Le modifiche effettuate al profilo dopo l'ultimo accesso potrebbero non essere disponibili.

Se non è disponibile un controller di dominio e le informazioni di accesso dell'utente non sono memorizzate nella cache verrà visualizzato il seguente messaggio:

Impossibile accedere adesso. Il dominio *&lt;NOME\_DOMINIO&gt;*; non è disponibile.

I possibili valori dell'impostazione **Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)** sono:

-   Numero definito dall'utente (compreso tra 0 e 50)

-   Non definito

##### Vulnerabilità

Il valore assegnato a questa impostazione indica il numero di utenti le cui informazioni di accesso sono state memorizzate dai server nella cache locale. Se il numero è impostato su 10, il server memorizza nella cache le informazioni di accesso relative a 10 utenti. Quando l'undicesimo utente accede al computer, il server sovrascrive la sessione di accesso meno recente memorizzata nella cache.

Le credenziali di accesso degli utenti che accedono alla console del server verranno memorizzate nella cache di tale server. Un pirata informatico in grado di accedere al file system del server potrebbe individuare le informazioni memorizzate nella cache e determinare le password degli utenti mediante un attacco di tipo "brute force".

Per ridurre questo tipo di attacchi, Windows esegue la crittografia delle informazioni e oscura la loro posizione fisica.

##### Contromisura

Configurare l'impostazione **Accesso interattivo**:  **numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)** su **0**, che disabilita la memorizzazione delle informazioni di accesso nella cache locale. Tra le contromisure aggiuntive sono incluse l'applicazione di criteri relativi alle password complesse e di luoghi fisici protetti dei computer.

##### Impatto potenziale

Se non è disponibile un controller di dominio per l'autenticazione, gli utenti non potranno accedere ad alcun computer. Nel caso di sistemi per utenti finali, in particolare per gli utenti mobili, le organizzazioni possono decidere di impostare questa opzione su 2. Di conseguenza, le informazioni di accesso dell'utente rimarranno nella cache anche se un membro del reparto IT ha eseguito di recente l'accesso al computer per effettuare operazioni di manutenzione nel sistema. In questo modo, gli utenti potranno accedere ai relativi computer quando non sono connessi alla rete aziendale.

#### Accesso interattivo: richiesta cambio password prima della scadenza

Questa impostazione di criterio determina con quanti giorni di anticipo gli utenti vengono avvisati della scadenza imminente della password. Grazie a questo preavviso, l'utente ha a disposizione il tempo necessario per creare una password sufficientemente complessa.

I possibili valori dell'impostazione **Accesso interattivo: richiesta cambio password prima della scadenza** sono:

-   Numero di giorni definito dall'utente (compreso tra 1 e 999)

-   Non definito

##### Vulnerabilità

Microsoft consiglia di impostare una scadenza periodica per le password degli utenti. Gli utenti dovranno essere avvisati in merito alla scadenza della password, per evitare che, una volta scaduta, il computer resti bloccato. Questa situazione potrebbe causare problemi agli utenti che accedono alla rete da un computer locale oppure potrebbe impedire l'accesso degli utenti alla rete dell'organizzazione in caso di utilizzo di connessioni remote o VPN.

##### Contromisura

Configurare l'impostazione **Accesso interattivo: richiesta cambio password prima della scadenza** su 14 giorni.

##### Impatto potenziale

Tutte le volte che gli utenti effettueranno l'accesso al dominio, se la loro password è configurata per scadere entro 14 giorni, sarà visualizzata una finestra di dialogo che li solleciterà a cambiare password.

#### Accesso interattivo: richiesta autenticazione controller di dominio per effettuare lo sblocco della workstation

Per sbloccare un computer sono necessarie le informazioni di accesso. Per quanto riguarda gli account di dominio, l'impostazione **Accesso interattivo: richiesta autenticazione controller di dominio per effettuare lo sblocco della workstation** determina se è necessario o meno contattare un controller di dominio per sbloccare un computer. Per abilitare questa impostazione, è necessario che un controller di dominio esegua l'autenticazione dell'account di dominio che verrà utilizzato per sbloccare il computer. Se si disabilita questa impostazione, non sarà necessaria la conferma delle informazioni di accesso da parte di un controller di dominio per sbloccare il computer. Tuttavia, se l'impostazione **Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)** viene configurata su un valore superiore a zero, per sbloccare il computer verranno utilizzate le credenziali dell'utente memorizzate nella cache.

**Nota:** questa impostazione si riferisce ai computer Windows 2000, ma non è disponibile mediante lo strumento Security Configuration Manager.

I possibili valori dell'impostazione **Accesso interattivo: richiesta autenticazione controller di dominio per effettuare lo sblocco della workstation** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Per impostazione predefinita, il computer memorizza nella cache le credenziali di qualsiasi utente autenticato in locale. Quindi utilizza le credenziali contenute nella cache per autenticare gli utenti che tentano di sbloccare la console. Quando vengono utilizzate le credenziali memorizzate nella cache, eventuali modifiche apportate di recente all'account (ad esempio assegnazioni dei diritti utente, blocco o disabilitazione dell'account) non vengono considerate oppure vengono applicate dopo l'autenticazione dell'account. I privilegi degli utenti non vengono aggiornati ma (cosa più importante) gli account disabilitati possono comunque sbloccare la console del computer.

##### Contromisura

Configurare l'impostazione **Accesso interattivo: richiesta autenticazione controller di dominio per effettuare lo sblocco della workstation** su **Abilitato** e l'impostazione **Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)** su **0.**

##### Impatto potenziale

Quando la console di un computer viene bloccata manualmente dall'utente oppure automaticamente in base al timeout dello screen saver, è possibile sbloccarla solo se l'utente è in grado di eseguire nuovamente l'autenticazione nel controller di dominio. Se non è disponibile alcun controller di dominio, gli utenti non possono sbloccare le relative workstation. Se l'impostazione **Accesso interattivo: numero di accessi precedenti da memorizzare nella cache (nel caso in cui il controller di dominio non sia disponibile)** viene configurata su **0, **gli utenti con controller di dominio non disponibili (come gli utenti mobili o remoti) non saranno in grado di effettuare l'accesso.

#### Accesso interattivo: richiedi smart card

Questa impostazione di criterio richiede agli utenti l'accesso al computer tramite smart card.

**Nota:** questa impostazione si riferisce ai computer Windows 2000, ma non è disponibile mediante lo strumento Security Configuration Manager.

I possibili valori dell'impostazione **Accesso interattivo: richiedi smart card** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Se si richiede di utilizzare password lunghe e complesse per l'autenticazione, si garantisce una migliore protezione della rete, specialmente se gli utenti devono modificare regolarmente le password. In questo modo, si riducono le probabilità che un pirata informatico riesca a determinare la password di un utente tramite un attacco di tipo "brute force". Tuttavia, creare password complesse per gli utenti non è un processo semplice e inoltre, se un pirata informatico dispone di tempo sufficiente e di risorse informatiche, anche le password complesse sono vulnerabili ad attacchi di tipo "brute force".  Se per l'autenticazione vengono utilizzate smart card invece delle password, la protezione aumenta drasticamente, poiché l'attuale tecnologia rende quasi impossibile per un pirata informatico rappresentare un altro utente. Le smart card che richiedono i codici PIN (Personal Identification Number) consentono l'autenticazione basata su due fattori. L'utente deve quindi disporre della smart card e conoscere il proprio PIN. Dopo aver acquisito il traffico di autenticazione tra il computer dell'utente e il controller di dominio, per un pirata informatico risulta estremamente difficile decrittografarlo; anche se ci riesce, al successivo accesso in rete dell'utente verrà generata una nuova chiave di sessione per crittografare il traffico tra l'utente e il controller di dominio.

##### Contromisura

Per gli account sensibili, rilasciare le smart card agli utenti e configurare l'impostazione **Accesso interattivo: richiedi smart card** su **Abilitato.**

##### Impatto potenziale

Poiché tutti gli utenti dovranno utilizzare le smart card per accedere alla rete, l'organizzazione deve predisporre un'infrastruttura a chiave pubblica (PKI) affidabile, le smart card e i relativi lettori per tutti gli utenti. Questi requisiti rappresentano un compito impegnativo, in quanto la pianificazione e la distribuzione di queste tecnologie richiede competenze e risorse specifiche. Windows Server 2003 include tuttavia Servizi certificati, un servizio estremamente avanzato per l'implementazione e la gestione dei certificati Quando i Servizi certificati sono utilizzati insieme a Windows XP, sono disponibili funzioni quali la registrazione e il rinnovo automatici di utenti e computer.

#### Accesso interattivo: funzionamento rimozione Smart card

determina l'azione conseguente alla rimozione della smart card dal lettore da parte di un utente connesso.

I possibili valori dell'impostazione **Accesso interattivo: funzionamento rimozione Smart card** sono:

-   Nessuna operazione

-   Blocca workstation

-   Imponi disconnessione

-   Non definito

##### Vulnerabilità

Se per l'autenticazione viene utilizzata una smart card, quando questa viene rimossa il computer si blocca automaticamente. Questo approccio evita che utenti malintenzionati accedano ai computer di utenti che dimenticano di bloccare manualmente le workstation prima di assentarsi.

##### Contromisura

Configurare l'impostazione **Funzionamento rimozione Smart card** su **Blocca workstation**.

Se si seleziona **Blocca workstation** nella finestra di dialogo **Proprietà** relativa a questo criterio, la workstation si blocca quando viene rimossa la smart card. Gli utenti possono quindi allontanarsi dalla postazione, portare con sé la smart card e mantenere comunque una sessione protetta.

Se si seleziona **Imponi disconnessione** nella finestra di dialogo **Proprietà** relativa a questa impostazione di criterio, l'utente viene disconnesso automaticamente quando viene rimossa la smart card.

##### Impatto potenziale

Quando ritornano alle rispettive workstation, gli utenti dovranno reinserire le smart card e immettere nuovamente i codici PIN.

#### Client e server di rete Microsoft: aggiungi firma digitale alle comunicazioni (quattro impostazioni correlate)

Sono disponibili quattro impostazioni distinte relative all'aggiunta della firma digitale alle comunicazioni SMB (Server Message Block):

-   **Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)**

-   **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)**

-   **Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (se autorizzato dal server)**

-   **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (se autorizzato dal server)**

I possibili valori per ciascuna di queste impostazioni di criterio sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

L'implementazione della firma digitale nelle reti con livello di protezione Alto consente di impedire la rappresentazione di client e server. Questo tipo di rappresentazione è noto come dirottamento di sessione, in cui vengono utilizzati appositi strumenti per consentire ai pirati informatici che hanno ottenuto l'accesso alla stessa rete del client o del server di interrompere, terminare o rubare una sessione in corso. I pirati informatici sono potenzialmente in grado di intercettare e modificare i pacchetti SMB privi di firma digitale, di modificare quindi il traffico e di inoltrarlo in modo che il server possa eseguire azioni non autorizzate. In alternativa, il pirata informatico potrebbe rappresentare il server o il client dopo un'autenticazione legittima e ottenere l'accesso non autorizzato ai dati.

SMB è il protocollo di condivisione delle risorse supportato da numerosi sistemi operativi Microsoft. Costituisce la base del sistema NetBIOS e di molti altri protocolli. Le firme SMB autenticano sia gli utenti che i server host dei dati. Se uno dei due non supera il processo di autenticazione, la trasmissione dei dati non verrà eseguita.

**Nota**: una contromisura alternativa che consente di proteggere tutto il traffico di rete consiste nell'implementazione delle firme digitali tramite IPsec. Esistono acceleratori hardware per la crittografia IPSec e la firma che consentono di ridurre al minimo l'impatto sulle prestazioni dovuto alla CPU dei server. Tali acceleratori non sono tuttavia disponibili per la firma SMB.

##### Contromisura

Configurare le impostazioni come segue:

-   **Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)** su **Disabilitato**

-   **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)** su **Disabilitato**

-   **Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (se autorizzato dal server)** su **Abilitato**

-   **Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (se autorizzato dal server)** su **Abilitato**

Alcuni esperti consigliano di configurare tutte queste impostazioni su **Abilitato**. Tale scelta potrebbe tuttavia causare una riduzione delle prestazioni nei computer client e impedire a questi ultimi di comunicare con le applicazioni SMB e i sistemi operativi precedenti.

##### Impatto potenziale

Le implementazioni del protocollo SMB per la condivisione di file e stampanti, disponibili in Windows 2000 Server, Windows 2000 Professional, Windows Server 2003, and Windows XP Professional, consentono l'autenticazione reciproca. Questa modalità di autenticazione evita gli attacchi con dirottamento di sessione e supporta l'autenticazione dei messaggi, impedendo in tal modo gli attacchi di tipo man-in-the-middle. La firma SMB fornisce questa autenticazione inserendo una firma digitale in ogni pacchetto SMB, che viene quindi verificato sia dal client che dal server. L'implementazione della firma SMB può influire negativamente sulle prestazioni, in quanto ciascun pacchetto deve essere firmato e verificato. Se i computer vengono configurati in modo da ignorare tutte le comunicazioni SMB prive di firma digitale, le applicazioni e i sistemi operativi precedenti non possono connettersi. Se si disabilitano completamente tutte le firme SMB, i computer rimangono vulnerabili agli attacchi con dirottamento di sessione.

#### Client di rete Microsoft: invia password non crittografata per la connessione ai server di SMB di terzi

Questa impostazione di criterio consente al redirector SMB di inviare password non crittografate ai server SMB non Microsoft che non supportano la crittografia delle password durante l'autenticazione.

I possibili valori dell'impostazione **Client di rete Microsoft: invia password non crittografata per la connessione ai server di SMB di terzi** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Se si abilita questa impostazione, il server può trasmettere password non crittografate agli altri computer attraverso la rete offrendo i servizi SMB. È possibile che gli altri sistemi non utilizzino nessuno dei meccanismi di protezione SMB inclusi in Windows Server 2003.

##### Contromisura

Configurare l'impostazione **Client di rete Microsoft: invia password non crittografata per la connessione ai server di SMB di terzi** su **Disabilitato.**

##### Impatto potenziale

È possibile che alcuni sistemi operativi e applicazioni molto vecchi quali MS-DOS, Windows per Workgroup 3.11 e Windows 95a non siano in grado di comunicare con i server della propria organizzazione tramite il protocollo SMB.

#### Server di rete Microsoft: periodo di inattività richiesto prima di sospendere la sessione

Questa impostazione di criterio determina il periodo di inattività continua che deve trascorrere prima che una sessione SMB venga sospesa per tale motivo Gli amministratori possono utilizzare questa impostazione per controllare quando un computer deve sospendere una sessione SMB inattiva. La sessione viene ristabilita automaticamente alla ripresa dell'attività del client. Un valore **0** comporta la disconnessione di una sessione inattiva nel più breve tempo possibile. Il valore massimo è 99999, corrispondente a 208 giorni; questo valore implica in realtà la disabilitazione dell'impostazione.

I possibili valori dell'impostazione **Server di rete Microsoft: periodo di inattività richiesto prima di sospendere la sessione** sono:

-   Periodo di tempo in minuti definito dall'utente

-   Non definito

##### Vulnerabilità

Ogni sessione SMB occupa le risorse del server e un numero elevato di sessioni Null può rallentarlo o provocarne l'arresto. Un pirata informatico potrebbe stabilire ripetutamente sessioni SMB fino a quando si verifica un rallentamento o l'interruzione della risposta del servizio SMB del server.

##### Contromisura

Configurare l'impostazione **Server di rete Microsoft: periodo di inattività richiesto prima del termine sessione** su **15 minuti.**

##### Impatto potenziale

L'impatto sarà minimo in quanto le sessioni SMB verranno ristabilite automaticamente se il client riprende la propria attività.

#### Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso

L'impostazione di questo criterio determina se scollegare gli utenti connessi a un computer locale al di fuori dell'orario di connessione valido per l'account. Influisce sul componente SMB. Se si attiva questa impostazione di criterio, le sessioni dei client con il servizio SMB saranno disconnesse forzatamente al termine dell'orario di accesso del client. Se questa impostazione viene disattivata, le sessioni client stabilite verranno conservate anche dopo la scadenza dell'orario di connessione del client. Se si abilita questa impostazione del criterio, è consigliabile abilitare anche **Protezione di rete: impone la disconnessione al termine dell'orario di accesso**.

I possibili valori dell'impostazione **Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Se nell'organizzazione è stato configurato l'orario di accesso, è consigliabile abilitare questa impostazione di criterio. In caso contrario, gli utenti privi dei diritti di accesso alle risorse di rete al di fuori dell'orario di accesso, potrebbero continuare effettivamente a utilizzare tali risorse tramite le sessioni stabilite durante l'orario di accesso.

##### Contromisura

Abilitare l'impostazione **Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso**.

##### Impatto potenziale

Se nell'organizzazione non viene utilizzato l'orario di accesso, l'abilitazione di questa impostazione non avrà alcun effetto. In caso di utilizzo dell'orario di accesso, le sessioni utente esistenti verranno terminate forzatamente al termine di tale orario.

#### Accesso di rete: consenti conversione anonima SID/NOME

Questa impostazione del criterio determina se un utente anonimo può richiedere o meno gli attributi SID di un altro utente.

I possibili valori dell'impostazione **Accesso di rete: consenti conversione anonima SID/nome** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Se questa impostazione è abilitata, un utente con accesso locale potrebbe utilizzare il SID degli amministratori noto per conoscere il nome reale dell'account Administrator predefinito, anche se tale account è stato rinominato. Tale persona potrebbe quindi utilizzare il nome dell'account per avviare un attacco di determinazione della password.

##### Contromisura

Configurare l'impostazione **Accesso di rete: consenti conversione anonima SID/nome** su **Disabilitato.**

##### Impatto potenziale

L'impostazione predefinita di questa impostazione di criterio nei computer membri è **Disabilitato**, quindi non avrà alcun effetto su tali computer. L'impostazione predefinita per i controller di dominio è **Abilitato**. Se questa impostazione di criterio viene disattivata sui controller di dominio, è possibile che i computer precedenti non siano in grado di comunicare con i domini di Windows Server 2003. Ad esempio, i computer seguenti potrebbero non funzionare:

-   Server con Servizio di Accesso remoto basati su Windows NT 4.0.

-   Microsoft SQL Server eseguito sui computer basati su Windows NT 3.x o Windows NT 4.0.

-   Server con Servizio di Accesso remoto o Microsoft SQL Server eseguiti nei computer basati su Windows 2000 che si trovano nei domini di Windows NT 3.x o di Windows NT 4.0.

#### Accesso di rete: non consentire l'enumerazione anonima degli account SAM

Questa impostazione di criterio determina le autorizzazioni aggiuntive che verranno concesse per le connessioni anonime al computer. Gli utenti anonimi di Windows possono svolgere determinate attività, ad esempio l'enumerazione dei nomi degli account di dominio e delle condivisioni di rete. Questa funzionalità risulta utile, ad esempio, quando un amministratore intende concedere agli utenti l'accesso a un dominio attendibile in cui non venga mantenuta una relazione di trust reciproca. Tuttavia, anche quando l'impostazione è abilitata, gli utenti anonimi avranno comunque accesso a tutte le risorse per le quali dispongono di autorizzazioni che includono in modo esplicito il gruppo predefinito speciale **ACCESSO ANONIMO**.

In Windows 2000, l'impostazione simile del criterio detta **Restrizioni addizionali per connessioni anonime** gestiva un valore di registro denominato **RestrictAnonymous**, che si trovava nella chiave del registro **HKLM\\SYSTEM\\CurrentControlSet\\Control\\LSA**. In Windows Server 2003, le impostazioni di criterio **Accesso di rete: non consentire l'enumerazione anonima degli account SAM** e **Accesso di rete: non consentire l'enumerazione anonima degli account e** **delle condivisioni SAM** sostituiscono l'impostazione di criterio di Windows 2000. Tali criteri gestiscono rispettivamente i valori del Registro di sistema **RestrictAnonymousSAM** e **RestrictAnonymous**, che si trovano entrambi nella chiave di registro **HKLM\\System\\CurrentControlSet\\Control\\Lsa\\**.

I possibili valori dell'impostazione **Accesso di rete: non consentire l'enumerazione anonima degli account SAM** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Un utente non autorizzato potrebbe visualizzare in modo anonimo i nomi degli account e utilizzare le informazioni ottenute per eseguire tentativi di determinazione delle password o altri tipi di attacchi (gli attacchi ai soggetti vulnerabili tentano di ingannare gli utenti in modo da ottenere le password o altre informazioni sulla protezione).

##### Contromisura

Configurare l'impostazione **Accesso di rete: non consentire l'enumerazione anonima degli account SAM** su **Abilitato.**

##### Impatto potenziale

È impossibile stabilire relazioni di trust con i domini di Windows NT 4.0. I computer client che eseguono versioni precedenti del sistema operativo Windows come Windows NT 3.51 e Windows 95 incontreranno anch'essi alcuni problemi quando cercheranno di utilizzare le risorse sul server.

#### Accesso di rete: non consentire l'enumerazione anonima degli account e delle condivisioni SAM

Questa impostazione di criterio determina se deve essere consentita o meno l'enumerazione di account e condivisioni di Gestione account di protezione (SAM, Security Account Manager). Come sottolineato nella sezione precedente, Windows consente agli utenti anonimi di svolgere determinate attività, ad esempio l'enumerazione dei nomi degli account di dominio e delle condivisioni di rete. Questa funzionalità risulta utile, ad esempio, quando un amministratore intende concedere agli utenti l'accesso a un dominio attendibile in cui non venga mantenuta una relazione di trust reciproca. È possibile abilitare questa impostazione di criterio se non si desidera consentire l'enumerazione anonima di account e condivisioni SAM. Tuttavia, anche quando l'impostazione è abilitata, gli utenti anonimi avranno comunque accesso a tutte le risorse per le quali dispongono di autorizzazioni che includono in modo esplicito il gruppo predefinito speciale **ACCESSO ANONIMO**.

In Windows 2000, l'impostazione simile del criterio detta **Restrizioni addizionali per connessioni anonime** gestiva un valore di registro denominato **RestrictAnonymous**, che si trovava nella chiave del registro **HKLM\\SYSTEM\\CurrentControlSet\\Control\\LSA**. In Windows Server 2003, le impostazioni di criterio **Accesso di rete: non consentire l'enumerazione anonima degli account SAM** e **Accesso di rete: non consentire l'enumerazione anonima degli account e delle condivisioni SAM** sostituiscono l'impostazione di criterio di Windows 2000. Tali criteri gestiscono rispettivamente i valori del Registro di sistema **RestrictAnonymousSAM** e **RestrictAnonymous**, che si trovano entrambi nella chiave di registro **HKLM\\System\\CurrentControlSet\\Control\\Lsa\\**.

I possibili valori dell'impostazione **Accesso di rete: non consentire l'enumerazione anonima degli account e delle condivisioni SAM** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Un utente non autorizzato potrebbe visualizzare in modo anonimo i nomi degli account e le risorse condivise, nonché utilizzare le informazioni ottenute per eseguire tentativi di determinazione delle password o altri tipi di attacchi.

##### Contromisura

Configurare l'impostazione **Accesso di rete: non consentire l'enumerazione anonima degli account e delle condivisioni SAM** su **Abilitato.**

##### Impatto potenziale

Non è possibile consentire l'accesso agli utenti di un altro dominio attraverso un trust unidirezionale, in quanto gli amministratori del dominio trusting non potranno enumerare gli elenchi di account nell'altro dominio. Gli utenti che accedono in modo anonimo ai file server e ai server di stampa non potranno elencare le risorse di rete condivise in tali server; prima di poter visualizzare l'elenco delle cartelle e delle stampanti condivise dovranno infatti eseguire l'autenticazione.

#### Accesso di rete: non consentire l'archiviazione di credenziali o di profili .NET Passport per l'autenticazione di rete

Questa impostazione di criterio determina se Gestione nomi utente e password archiviati salva o meno le password o le credenziali per utilizzarle in seguito quando ottiene l'autenticazione del dominio. Se si abilita questa opzione, si impedisce alla funzionalità Gestione nomi utente e password archiviati di Windows di archiviare le password e le credenziali.

I possibili valori dell'impostazione **Accesso di rete: non consentire l'archiviazione di credenziali o di profili .NET Passport per l'autenticazione di rete** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Le password memorizzate in questo modo nella cache sono accessibili all'utente quando si connette al computer. Tale aspetto può risultare ovvio ma potrebbe causare problemi se l'utente esegue accidentalmente codice dannoso che legge le password e le inoltra a un altro utente non autorizzato.

**Nota**: le probabilità di riuscita di questo tentativo di sfruttamento delle vulnerabilità e di altri attacchi che implicano l'utilizzo di codice dannoso verranno ridotte in modo significativo nelle organizzazioni che implementano e gestiscono con efficienza una soluzione anti-virus unitamente a criteri di restrizione software estremamente rigorosi. Per ulteriori informazioni sui criteri di restrizione software, vedere il Capitolo 8 "Criteri di restrizione software".

##### Contromisura

Configurare l'impostazione **Accesso di rete: non consentire l'archiviazione di credenziali o di profili .NET Passport per l'autenticazione di rete** su **Abilitato.**

##### Impatto potenziale

Gli utenti verranno obbligati a immettere le password ogni volta che accedono al relativo account Passport o ad altre risorse di rete che non sono accessibili all'account di dominio. Questa impostazione di criterio non dovrebbe avere alcun effetto sugli utenti che accedono alle risorse di rete configurate per consentire l'accesso al relativo account di dominio basato su Active Directory.

#### Accesso di rete: consenti l'accesso libero agli utenti anonimi

Questa impostazione di criterio determina le autorizzazioni aggiuntive che verranno concesse per le connessioni anonime al computer. Se si attiva questa impostazione di criterio, gli utenti anonimi possono enumerare i nomi degli account di dominio e delle condivisioni di rete e svolgere altre attività. Questa funzionalità risulta utile, ad esempio, quando un amministratore intende concedere agli utenti l'accesso a un dominio attendibile in cui non venga mantenuta una relazione di trust reciproca.

Per impostazione predefinita, il token creato per le connessioni anonime non include il SID Everyone. Pertanto le autorizzazioni concesse al gruppo **Everyone** non sono valide per gli utenti anonimi. Se si attiva questa impostazione di criterio, il SID Everyone viene aggiunto al token creato per le connessioni anonime e gli utenti anonimi possono accedere a qualsiasi risorsa che disponga delle autorizzazioni concesse al gruppo **Everyone**.

I possibili valori dell'impostazione **Accesso di rete: consenti l'accesso libero agli utenti anonimi** sono:

-   Abilitato

-   Disabilitato

-   Non definito

##### Vulnerabilità

Un utente non autorizzato potrebbe elencare in modo anonimo i nomi degli account e le risorse condivise, nonché utilizzare le informazioni per eseguire tentativi di determinazione delle password, effettuare attacchi DoS o altri tipi di attacchi.

##### Contromisura

Configurare l'impostazione **Accesso di rete: consenti l'accesso libero agli utenti anonimi** su **Disabilitato.**

##### Impatto potenziale

Nessuno. Si tratta della configurazione predefinita.

#### Accesso di rete: named pipe a cui è possibile accedere in modo anonimo

Questa impostazione di criterio determina le sessioni di comunicazione (pipe) a cui verranno assegnati gli attributi e le autorizzazioni che consentono l’accesso anonimo.

I possibili valori dell'impostazione **Accesso di rete: named pipe a cui è possibile accedere in modo anonimo** sono:

-   Un elenco di condivisioni definito dall'utente

-   Non definito

Per rendere effettiva questa impostazione di criterio, è necessario abilitare anche **Accesso di rete: limita accesso anonimo a named pipe e condivisioni**.

##### Vulnerabilità

La restrizione dell'accesso nelle named pipe quali COMNAP e LOCATOR consente di impedire l'accesso non autorizzato alla rete. Nella seguente tabella viene riportato l'elenco delle named pipe e lo scopo di ognuna di esse.

**Tabella 5.1: named pipe predefinite accessibili in modo anonimo**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Named pipe</p></th>
<th><p>Scopo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>COMNAP</p></td>
<td style="border:1px solid black;"><p>Named pipe per SnaBase. SNA (Systems Network Architecture) è un insieme di protocolli di rete sviluppati originariamente per i computer mainframe IBM.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>COMNODE</p></td>
<td style="border:1px solid black;"><p>Named pipe per SNA Server.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>SQL\QUERY</p></td>
<td style="border:1px solid black;"><p>Named pipe predefinita per SQL Server.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>SPOOLSS</p></td>
<td style="border:1px solid black;"><p>Named pipe per il servizio Spooler di stampa.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>EPMAPPER</p></td>
<td style="border:1px solid black;"><p>Named pipe per il mapping degli endpoint.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>LOCATOR</p></td>
<td style="border:1px solid black;"><p>Named pipe per il servizio RPC (Remote Procedure Call).</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>TrkWks</p></td>
<td style="border:1px solid black;"><p>Named pipe per Manutenzione collegamenti distribuiti client.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>TrkSvr</p></td>
<td style="border:1px solid black;"><p>Named pipe per Manutenzione collegamenti distribuiti server.</p></td>
</tr>  
</tbody>  
</table>
  
##### Contromisura
  
Configurare l'impostazione **Accesso di rete: named pipe a cui è possibile accedere in modo anonimo** su un valore Null (abilitare l'impostazione senza immettere le named pipe nella casella di testo).
  
##### Impatto potenziale
  
In questo modo verrà disabilitato l'accesso della sessione Null alle named pipe e alle applicazioni basate su questa funzionalità oppure non sarà più possibile eseguire l'accesso non autenticato alle named pipe. In Microsoft Commercial Internet System 1.0, ad esempio, il servizio di posta Internet viene eseguito nell'ambito del processo Inetinfo. Inetinfo viene avviato nel contesto dell'account di sistema. Quando il servizio di posta Internet deve eseguire la query al database Microsoft SQL Server, utilizza l'account di sistema che si basa sulle credenziali Null per accedere a una pipe SQL nel computer che esegue SQL Server.
  
Per evitare questo problema, fare riferimento all'articolo della Microsoft Knowledge Base "[Come accedere ai file di rete da applicazioni IIS](http://support.microsoft.com/default.aspx?scid=207671)" all'indirizzo http://support.microsoft.com/default.aspx?scid=207671.
  
#### Accesso di rete: percorsi del Registro di sistema ai quali è possibile accedere in modo remoto.
  
Questa impostazione di criterio determina i percorsi del Registro di sistema che saranno accessibili dopo aver fatto riferimento alla chiave **WinReg** per stabilire le autorizzazioni di accesso.
  
I possibili valori dell'impostazione **Accesso di rete: percorsi del Registro di sistema ai quali è possibile accedere in modo remoto** sono:
  
-   Un elenco di percorsi definito dall'utente
  
-   Non definito
  
##### Vulnerabilità
  
Il Registro di sistema è un database che contiene le informazioni di configurazione del computer, che per la maggior parte sono riservate. Un pirata informatico potrebbe utilizzare queste informazioni per semplificare eventuali attività non autorizzate. Per ridurre tale rischio, nel Registro di sistema vengono assegnati ACL appropriati al fine di proteggerlo dall'accesso di utenti non autorizzati.
  
##### Contromisura
  
Configurare l'impostazione **Accesso di rete: percorsi del Registro di sistema ai quali è possibile accedere in modo remoto** su un valore Null (abilitare l'impostazione senza immettere alcun percorso nella casella di testo).
  
##### Impatto potenziale
  
Alcuni strumenti per la gestione remota, ad esempio Microsoft Baseline Security Analyzer e Microsoft Systems Management Server, richiedono l'accesso remoto al Registro di sistema per controllare e gestire i computer in modo corretto. Se i percorsi predefiniti del Registro di sistema dall'elenco dei percorsi accessibili vengono rimossi, si potrebbe verificare un errore negli strumenti di gestione.
  
**Nota:** se si desidera consentire l'accesso remoto, è necessario abilitare anche il servizio Registro di sistema remoto.
  
#### Accesso di rete: percorsi e sottopercorsi del Registro di sistema ai quali è possibile accedere in modo remoto
  
Questa impostazione di criterio determina i percorsi e i sottopercorsi del Registro di sistema che saranno accessibili dopo aver fatto riferimento alla chiave **WinReg** per stabilire le autorizzazioni di accesso.
  
I possibili valori dell'impostazione **Accesso di rete: percorsi e sottopercorsi del Registro di sistema ai quali è possibile accedere in modo remoto** sono:
  
-   Un elenco di percorsi definito dall'utente
  
-   Non definito
  
##### Vulnerabilità
  
Come accennato in precedenza, il Registro di sistema contiene informazioni di configurazione del computer riservate che potrebbero essere utilizzate da un pirata informatico per semplificare eventuali attività non autorizzate. Assegnando al Registro di sistema ACL con restrizioni appropriate, che consentono di proteggerlo dall'accesso di utenti non autorizzati, viene ridotto il rischio di tale attacco.
  
##### Contromisura
  
Configurare l'impostazione **Accesso di rete: percorsi e sottopercorsi del Registro di sistema ai quali è possibile accedere in modo remoto** su un valore Null (abilitare l'impostazione senza immettere alcun percorso nella casella di testo).
  
##### Impatto potenziale
  
Alcuni strumenti per la gestione remota, ad esempio Microsoft Baseline Security Analyzer e Microsoft Systems Management Server, richiedono l'accesso remoto al Registro di sistema per controllare e gestire i computer in modo corretto. Se i percorsi predefiniti del Registro di sistema dall'elenco dei percorsi accessibili vengono rimossi, si potrebbe verificare un errore negli strumenti di gestione.
  
**Nota:** se si desidera consentire l'accesso remoto, è necessario abilitare anche il servizio Registro di sistema remoto.
  
#### Accesso di rete: limita accesso anonimo a named pipe e condivisioni
  
Quando attivata, questa impostazione di criterio limita l'accesso anonimo solamente a condivisioni e pipe che sono nominate nelle impostazioni **Accesso di rete: named pipe a cui è possibile accedere in modo anonimo** e **Accesso di rete: condivisioni a cui è possibile accedere in modo anonimo**. Questa impostazione permette di controllare l'accesso di una sessione Null alle condivisioni sui computer aggiungendo **RestrictNullSessAccess** con il valore **1** nella chiave di registro **HKLM\\System\\CurrentControlSet\\Services\\LanManServer\\Parameters**. Questo valore di registro attiva o disattiva le condivisioni delle sessioni Null per stabilire se il servizio Server limita l'accesso dei client senza autenticazione alle risorse nominate.
  
I possibili valori dell'impostazione **Accesso di rete: limita accesso anonimo a named pipe e condivisioni** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
Le sessioni Null rappresentano un punto debole che può essere sfruttato tramite le varie condivisioni (comprese le condivisioni predefinite) presenti nei computer del proprio ambiente.
  
##### Contromisura
  
Configurare l'impostazione **Accesso di rete: limita accesso anonimo a named pipe e condivisioni** su **Abilitato.**
  
##### Impatto potenziale
  
Questa impostazione di criterio può essere abilitata per limitare l'accesso degli utenti non autenticati alle sessioni Null per tutte le pipe server e le condivisioni, ad eccezione di quelle elencate nelle voci **NullSessionPipes** e **NullSessionShares**.
  
#### Accesso di rete: condivisioni a cui è possibile accedere in modo anonimo
  
Questa impostazione di criterio determina a quali condivisioni di rete possono accedere gli utenti anonimi.
  
I possibili valori dell'impostazione **Accesso di rete: condivisioni a cui è possibile accedere in modo anonimo** sono:
  
-   Un elenco di condivisioni definito dall'utente
  
-   Non definito
  
##### Vulnerabilità
  
È molto pericoloso attivare questa impostazione. Qualsiasi condivisione elencata è accessibile a tutti gli utenti della rete e ciò potrebbe provocare l'esposizione o il danneggiamento di dati riservati.
  
##### Contromisura
  
Configurare l'impostazione **Accesso di rete: condivisioni a cui è possibile accedere in modo anonimo** su un valore Null.
  
##### Impatto potenziale
  
Poiché si tratta dell'impostazione predefinita, l'impatto dovrebbe essere minimo. Solamente gli utenti autenticati potranno accedere alle risorse condivise sul server.
  
#### Accesso di rete: modello di condivisione e protezione per gli account locali
  
Questa impostazione di criterio determina la modalità di autenticazione degli accessi in rete che utilizzano account locali. Se questa impostazione viene configurata su **Classico**, gli accessi di rete che utilizzano le credenziali di account locali verranno autenticati mediante tali credenziali. Se questa impostazione viene configurata su **Solo Guest**, gli accessi di rete che utilizzano account locali vengono associati automaticamente all'account Guest. L'opzione **Classico** consente un controllo preciso dell'accesso alle risorse, compresa la possibilità di assegnare tipi di accesso differenti a utenti diversi per la stessa risorsa. Al contrario, se si utilizza il modello **Solo Guest**, tutti gli utenti vengono considerati come account utente Guest e ricevono lo stesso livello di accesso per una determinata risorsa, ovvero Sola lettura o Modifica.
  
In un ambiente Windows XP Professional autonomo, l'impostazione predefinita è **Solo Guest**. Per i computer Windows XP aggiunti a un dominio e i computer Windows Server 2003, l'impostazione predefinita è **Classico**.
  
**Nota**: questa impostazione non influisce sugli accessi di rete che utilizzano account locali. Inoltre non ha alcun effetto sugli accessi interattivi eseguiti in modo remoto tramite servizi quali Telnet o Servizi terminal.
  
Se il computer non è stato aggiunto a un dominio, l'impostazione personalizza anche le schede **Condivisione** e **Protezione** di Esplora risorse in modo che corrispondano al modello di condivisione e protezione utilizzato.
  
Questa impostazione non ha alcun effetto sui computer con sistema operativo Windows 2000.
  
I possibili valori dell'impostazione **Accesso di rete: modello di condivisione e protezione per gli account locali** sono:
  
-   Classico. Gli utenti locali effettuano l'autenticazione di se stessi.
  
-   Solo Guest. Gli utenti locali effettuano l'autenticazione come Guest.
  
-   Non definito
  
##### Vulnerabilità
  
Con il modello **Solo Guest**, gli utenti che possono effettuare l'autenticazione su un altro computer in rete utilizzano a tale scopo i privilegi Guest, il che significa che probabilmente non avranno accesso in scrittura a risorse condivise su quel computer. Sebbene questa limitazione aumenti la protezione, risulterà più difficile per gli utenti autorizzati accedere alle risorse condivise su quei computer, in quanto negli ACL di tali risorse devono essere presenti le voci di controllo degli accessi (ACE, Access Control Entry) dell'account Guest. Con il modello **Classico**, gli account locali devono essere protetti da password. In caso contrario, se l'accesso Guest è abilitato, qualsiasi utente può utilizzare tali account per accedere alle risorse condivise.
  
##### Contromisura
  
Per i server di rete, configurare l'impostazione **Accesso di rete: modello di condivisione e protezione per gli account locali** su **Classico: gli utenti locali effettuano l'autenticazione di se stessi.** Nei computer per utenti finali, configurare questa impostazione di criterio su **Solo Guest: gli utenti locali effettuano l'autenticazione come Guest**.
  
##### Impatto potenziale
  
Nessuno. Si tratta della configurazione predefinita.
  
#### Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password
  
Questa impostazione di criterio determina se il LAN Manager (LM) può memorizzare un valore hash per la nuova password al successivo cambio di password.
  
I possibili valori dell'impostazione **Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
Il file SAM può essere preso di mira dai pirati informatici che tentano di accedere agli hash di nomi utente e password. Tali attacchi utilizzano strumenti speciali per individuare le password, che possono quindi essere utilizzate per rappresentare altri utenti e accedere alle risorse della rete. Se questa impostazione di criterio viene abilitata, non sarà possibile impedire questi tipi di attacchi, ma sarà molto più difficile che abbiano esito positivo.
  
##### Contromisura
  
Configurare l'impostazione **Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password** su **Abilitato.** Richiedere a tutti gli utenti di impostare nuove password al prossimo accesso al dominio, in modo che vengano rimossi gli hash di LAN Manager.
  
##### Impatto potenziale
  
In sistemi operativi precedenti quali Windows 95, Windows 98 e Windows ME e in alcune applicazioni di terze parti si verificheranno degli errori.
  
#### Protezione di rete: impone la disconnessione al termine dell'orario di accesso
  
L'impostazione di questo criterio determina se scollegare gli utenti connessi a un computer locale al di fuori dell'orario di connessione valido per l'account. Influisce sul componente SMB. Se si attiva questa impostazione di criterio, le sessioni dei client con il server SMB saranno disconnesse al termine dell'orario di accesso del client. Se questa impostazione viene disattivata, le sessioni client stabilite verranno conservate anche dopo la scadenza dell'orario di connessione del client.
  
I possibili valori dell'impostazione **Protezione di rete:** **impone la disconnessione al termine dell'orario di accesso** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
Se questa impostazione è disabilitata, un utente potrebbe rimanere connesso al computer al di fuori del relativo orario di accesso assegnato.
  
##### Contromisura
  
Configurare l'impostazione **Protezione di rete: impone la disconnessione al termine dell'orario di accesso** su **Abilitato.** Questa impostazione di criterio non viene applicata agli account degli amministratori.
  
##### Impatto potenziale
  
Le sessioni SMB verranno terminate alla scadenza dell'orario di accesso dell'utente. L'utente non sarà in grado di accedere al computer fino all'inizio del successivo orario di accesso pianificato.
  
#### Protezione di rete: livello di autenticazione di LAN Manager
  
LAN Manager (LM) è una delle prime famiglie di software client/server Microsoft che consente agli utenti di collegare tra loro i computer in una rete singola. Tra le funzionalità di rete sono inclusi la condivisione di file e stampanti, le funzionalità di protezione dell'utente e gli strumenti di amministrazione della rete. Nei domini di Active Directory, Kerberos è il protocollo di autenticazione predefinito. Tuttavia, se il protocollo Kerberos non viene negoziato per qualche motivo, Active Directory utilizzerà LM, NTLM o NTLMv2.
  
L'autenticazione di LAN Manager comprende le varianti LM, NTLM e NTLM versione 2 (NTLMv2) ed è il protocollo utilizzato per autenticare tutti i client di Windows durante le seguenti operazioni:
  
-   Unirsi a un dominio
  
-   Autenticazione tra insiemi di strutture in Active Directory
  
-   Autenticazione nei domini di livello inferiore
  
-   Autenticazione a computer che non eseguono Windows 2000, Windows Server 2003, o Windows XP
  
-   Autenticazione a computer non presenti nel dominio
  
I possibili valori dell'impostazione **Protezione di rete: livello di autenticazione di LAN Manager** sono:
  
-   Invia risposte LM e NTLM
  
-   Invia LM e NTLM. Utilizza la protezione sessione NTLMv2 se negoziata
  
-   Invia solo risposta NTLM
  
-   Invia solo risposte NTLMv2
  
-   Invia solo risposta NTLMv2\\Rifiuta LM
  
-   Invia solo risposta NTLMv2\\Rifiuta LM e NTLM
  
-   Non definito
  
L'impostazione **Protezione di rete: livello di autenticazione di LAN Manager** determina il protocollo di autenticazione challenge/response utilizzato per gli accessi alla rete. Questa scelta influisce sul livello del protocollo di autenticazione utilizzato dai client, sul livello di protezione della sessione negoziato dai computer e sul livello di autenticazione accettato dai server, in base al seguente meccanismo:
  
-   **Invia risposte LM e NTLM.** I client utilizzano l'autenticazione LM e NTLM; non utilizzano mai la protezione di sessione NTLMv2. I controller di dominio accettano l'autenticazione LM, NTLM e NTLMv2.
  
-   **Invia LM e NTLM. Utilizza la protezione sessione NTLMv2 se negoziata.** I client utilizzano l'autenticazione LM e NTLM, nonché la protezione di sessione NTLMv2 se supportata dal server. I controller di dominio accettano l'autenticazione LM, NTLM e NTLMv2.
  
-   **Invia solo risposta NTLM**: i client utilizzano solo l'autenticazione NTLM, nonché la protezione di sessione NTLMv2 se supportata dal server. I controller di dominio accettano l'autenticazione LM, NTLM e NTLMv2.
  
-   **Invia solo risposta NTLMv2**: i client utilizzano solo l'autenticazione NTLMv2, nonché la protezione di sessione NTLMv2 se supportata dal server. I controller di dominio accettano l'autenticazione LM, NTLM e NTLMv2.
  
-   **Invia solo risposta NTLMv2\\Rifiuta LM**: i client utilizzano solo l'autenticazione NTLMv2, nonché la protezione di sessione NTLMv2 se supportata dal server. I controller di dominio rifiutano l'autenticazione LM, ovvero accettano solo l'autenticazione NTLM e NTLMv2.
  
-   **Invia solo risposta NTLMv2\\Rifiuta LM e NTLM**: i client utilizzano solo l'autenticazione NTLMv2, nonché la protezione di sessione NTLMv2 se supportata dal server. I controller di dominio rifiutano l'autenticazione LM e NTLM, ovvero accettano solo l'autenticazione NTLMv2.
  
Queste impostazioni corrispondono ai seguenti livelli descritti in altri documenti Microsoft:
  
-   **Livello 0 - Invia risposta LM e NTLM. Non utilizzare mai la protezione di sessione NTLMv2**. I client utilizzano l'autenticazione LM e NTLM; non utilizzano mai la protezione di sessione NTLMv2. I controller di dominio accettano l'autenticazione LM, NTLM e NTLMv2.
  
-   **Livello 1 - Utilizza la protezione sessione NTLMv2 se negoziata**. I client utilizzano l'autenticazione LM e NTLM, nonché la protezione di sessione NTLMv2 se supportata dal server. I controller di dominio accettano l'autenticazione LM, NTLM e NTLMv2.
  
-   **Livello 2 - Invia solo risposta NTLM**. I client utilizzano solo l'autenticazione NTLM, nonché la protezione di sessione NTLMv2 se supportata dal server. I controller di dominio accettano l'autenticazione LM, NTLM e NTLMv2.
  
-   **Livello 3 - Invia solo risposta NTLMv2**. I client utilizzano l'autenticazione NTLMv2, nonché la protezione di sessione NTLMv2 se supportata dal server. I controller di dominio accettano l'autenticazione LM, NTLM e NTLMv2.
  
-   **Livello 4 - I controller di dominio rifiutano le risposte LM**. I client utilizzano l'autenticazione NTLM, nonché la protezione di sessione NTLMv2 se supportata dal server. I controller di dominio rifiutano l'autenticazione LM, ovvero accettano solo l'autenticazione NTLM e NTLMv2.
  
-   **Livello 5 - I controller di dominio rifiutano le risposte LM e NTLM, ovvero accettano solo l'autenticazione NTLMv2**. I client utilizzano l'autenticazione NTLMv2, nonché la protezione di sessione NTLMv2 se supportata dal server. I controller di dominio rifiutano l'autenticazione LM e NTLM, ovvero accettano solo l'autenticazione NTLMv2.
  
##### Vulnerabilità
  
I client Windows 2000, Windows Server 2003 e Windows XP sono configurati per impostazione predefinita in modo da inviare le risposte di autenticazione LM e NTLM (ad eccezione dei client Windows 9x che inviano solo risposte LM). Nei server, l'impostazione predefinita consente a tutti i client di eseguire l'autenticazione nei server e di utilizzarne le risorse. Tuttavia, ciò significa che le risposte LM, ovvero il tipo di risposte di autenticazione più vulnerabili, vengono inviate in rete consentendo potenzialmente ai pirati informatici di eseguire lo sniffing del traffico per riprodurre facilmente la password dell'utente.
  
Nei sistemi operativi Windows 9x e Windows NT non è possibile utilizzare per l'autenticazione la versione 5 del protocollo Kerberos. Per tale motivo, in un dominio di Windows Server 2003 questi computer eseguono l'autenticazione di rete utilizzando per impostazione predefinita sia il protocollo LM che il protocollo NTLM. Per Windows 9x e Windows NT è possibile applicare un protocollo di autenticazione più sicuro, ovvero NTLMv2. Durante la procedura di accesso, NTLMv2 utilizza un canale protetto per tutelare il processo di autenticazione. Anche se si utilizza NTLMv2 per i client e i server precedenti, i client e i server Windows che sono membri del dominio eseguiranno l'autenticazione nei controller di dominio Windows Server 2003 mediante il protocollo Kerberos.
  
Per ulteriori informazioni sull'abilitazione di NTLMv2, vedere l'articolo della Microsoft Knowledge Base "[Attivazione dell'autenticazione NTLM 2](http://support.microsoft.com/kb/239869/it)" all'indirizzo http://support.microsoft.com/default.aspx?scid=239869. Per supportare NTLMv2, Microsoft Windows NT 4.0 richiede il Service Pack 4 (SP4) mentre per le piattaforme Windows 9x è necessario installare il client Servizio directory.
  
##### Contromisura
  
Configurare l'impostazione **Protezione di rete: livello di autenticazione di LAN Manager** su **Invia solo risposte NTLMv2.** Questo livello di autenticazione è consigliato da Microsoft e da varie organizzazioni indipendenti in cui tutti i client supportano NTLMv2.
  
##### Impatto potenziale
  
I client che non supportano l'autenticazione NTLMv2 non potranno eseguire l'autenticazione nel dominio né accedere alle risorse di dominio mediante LM e NTLM.
  
**Nota**: per ulteriori informazioni sugli aggiornamenti rapidi per assicurare che questa impostazione venga supportata nelle reti che includono una combinazione di computer Windows NT 4.0 e computer Windows 2000, Windows XP e Windows Server 2003, fare riferimento all'articolo della Microsoft Knowledge Base "[Problemi di autenticazione in Windows 2000 con livelli NTLM 2 superiori a 2 in dominio Windows NT 4.0](http://support.microsoft.com/default.aspx?scid=305379)" all'indirizzo http://support.microsoft.com/default.aspx?scid=305379.
  
#### Protezione di rete: requisiti per la firma client LDAP
  
Questa impostazione di criterio determina il livello di firma dei dati richiesto per conto dei client che emettono richieste di binding LDAP, come illustrato di seguito:
  
-   **Nessuno**. la richiesta di binding LDAP viene emessa in base alle opzioni specificate dal chiamante.
  
-   **Negozia firma**: se non è stato avviato TLS/SSL (Transport Layer Security/Secure Sockets Layer), la richiesta di binding LDAP inizia in base all'impostazione dell'opzione di firma digitale LDAP, oltre alle opzioni specificate dal chiamante. Se TLS/SSL è stato avviato, la richiesta di binding LDAP inizia in base alle opzioni specificate dal chiamante.
  
-   **Richiedi firma**. È equivalente all'opzione **Negozia firma**. Se tuttavia la risposta intermedia saslBindInProgress del server LDAP non indica che è necessaria la firma del traffico LDAP, il chiamante viene avvisato che la richiesta del comando di binding non è riuscita.
  
**Nota**: questa impostazione non ha alcun effetto su ldap\_simple\_bind or ldap\_simple\_bind\_s. Nessun client Microsoft LDAP incluso in Windows XP Professional utilizza ldap\_simple\_bind o ldap\_simple\_bind\_s per comunicare con un controller di dominio.
  
I possibili valori dell'impostazione **Protezione di rete: requisiti per la firma client LDAP** sono:
  
-   Nessuna
  
-   Negozia firma
  
-   Richiedi firma
  
-   Non definito
  
##### Vulnerabilità
  
Il traffico di rete privo di firma è esposto ad attacchi di tipo "man-in-the-middle", in cui un intruso acquisisce i pacchetti tra il client e il server e li modifica prima di inoltrarli al server. Nel caso di un server LDAP, questa vulnerabilità può consentire a un pirata informatico di indurre un server a prendere decisioni sulla base di dati falsi o modificati dalle query LDAP. Per ridurre questo rischio in una rete è possibile implementare misure di protezione fisica efficaci a tutela dell'infrastruttura di rete. La richiesta di firme digitali su tutti i pacchetti di rete tramite le intestazioni di autenticazione IPSec rende inoltre molto più difficili gli attacchi di tipo "man-in-the-middle".
  
##### Contromisura
  
Configurare l'impostazione **Protezione di rete: requisiti per la firma server LDAP** su **Richiedi firma.**
  
##### Impatto potenziale
  
Se si imposta il server in modo che richieda firme LDAP, è necessario configurare anche il client. Se il client non viene configurato, non potrà comunicare con il server e pertanto potrebbero verificarsi errori in molte funzionalità, tra cui l'autenticazione degli utenti, i criteri di gruppo e gli script di accesso.
  
#### Protezione di rete: protezione sessione minima per client basati su NTLM SSP (incluso l'RPC protetto)
  
Questa impostazione di criterio consente a un computer client di richiedere la negoziazione della riservatezza (crittografia) dei messaggi, l'integrità dei messaggi, la crittografia a 128 bit o la protezione di sessione NTLMv2. Questi valori dipendono da quello dell'impostazione di criterio **Livello di autenticazione di LAN Manager**.
  
I possibili valori dell'impostazione **Protezione di rete: protezione sessione minima per client basati su NTLM SSP (incluso l'RPC protetto)** sono:
  
-   **Richiedi riservatezza messaggio**. Se non viene negoziata la crittografia, non sarà possibile stabilire la connessione. La crittografia consente di convertire i dati in un formato non leggibile fino a quando non vengono decrittografati.
  
-   **Richiedi integrità messaggio**. Se non viene negoziata l'integrità del messaggio, non sarà possibile stabilire la connessione. L'integrità di un messaggio può essere verificata attraverso la firma. Per garantire che il messaggio non sia stato alterato, ad esso viene associata una firma crittografata, che identifica il mittente e ne fornisce una rappresentazione numerica del contenuto.
  
-   **Richiedi crittografia a 128 bit**. Se non viene negoziata una crittografia avanzata a 128 bit, non sarà possibile stabilire la connessione.
  
-   **Richiedi protezione sessione NTLMv2**. Se non viene negoziato il protocollo NTLMv2, non sarà possibile stabilire la connessione.
  
-   **Non definito**.
  
##### Vulnerabilità
  
È possibile abilitare tutte le opzioni indicate per l'impostazione di questo criterio, per proteggere il traffico di rete basato sul Provider supporto protezione NTLM (NTLM SSP) dal rischio di esposizione o alterazione da parte di un pirata informatico, che ha ottenuto l'accesso alla stessa rete. Queste opzioni, quindi, consentono di proteggere il sistema dagli attacchi di tipo "man-in-the-middle".
  
##### Contromisura
  
Abilitare tutte e quattro le opzioni disponibili per l'impostazione **Protezione di rete: protezione sessione minima per client basati su NTLM SSP (incluso l'RPC protetto)**.
  
##### Impatto potenziale
  
I computer client che applicano queste impostazioni non potranno comunicare con i server precedenti che non le supportano.
  
#### Protezione di rete: protezione sessione minima per server basati su NTLM SSP (incluso l'RPC protetto)
  
Questa impostazione di criterio consente a un server di richiedere la negoziazione della riservatezza (crittografia) dei messaggi, l'integrità dei messaggi, la crittografia a 128 bit o la protezione di sessione NTLMv2. Questi valori dipendono da quello dell'impostazione **Livello di autenticazione di LAN Manager**.
  
I possibili valori dell'impostazione **Protezione di rete: protezione sessione minima per server basati su NTLM SSP (incluso l'RPC protetto)** sono:
  
-   **Richiedi riservatezza messaggio**. Se non viene negoziata la crittografia, non sarà possibile stabilire la connessione. La crittografia consente di convertire i dati in un formato non leggibile fino a quando non vengono decrittografati.
  
-   **Richiedi integrità messaggio**. Se non viene negoziata l'integrità del messaggio, non sarà possibile stabilire la connessione. L'integrità di un messaggio può essere verificata attraverso la firma. Per garantire che il messaggio non sia stato alterato, ad esso viene associata una firma crittografata, che identifica il mittente e ne fornisce una rappresentazione numerica del contenuto.
  
-   **Richiedi crittografia a 128 bit**. Se non viene negoziata una crittografia avanzata a 128 bit, non sarà possibile stabilire la connessione.
  
-   **Richiedi protezione sessione NTLMv2**. Se non viene negoziato il protocollo NTLMv2, non sarà possibile stabilire la connessione.
  
-   **Non definito**.
  
##### Vulnerabilità
  
È possibile abilitare tutte le opzioni indicate per l'impostazione di questo criterio, per proteggere il traffico di rete basato sul Provider supporto protezione NTLM (NTLM SSP) dal rischio di esposizione o alterazione da parte di un pirata informatico, che ha ottenuto l'accesso alla stessa rete. Queste opzioni, quindi, consentono di proteggere il sistema dagli attacchi di tipo "man-in-the-middle".
  
##### Contromisura
  
Abilitare tutte e quattro le opzioni disponibili per l'impostazione **Protezione di rete: protezione sessione minima per server basati su NTLM SSP (incluso l'RPC protetto)**.
  
##### Impatto potenziale
  
I client precedenti che non supportano queste impostazioni di protezione non potranno comunicare con il computer.
  
#### Console di ripristino di emergenza: consente l'accesso di amministrazione automatico
  
Questa impostazione di criterio determina se deve essere specificata la password dell’account Administrator prima di accedere al computer. Se si abilita questa impostazione di criterio, l'account Administrator ha accesso automatico alla console di ripristino di emergenza del computer; non sono necessarie password.
  
I possibili valori dell'impostazione **Console di ripristino di emergenza: consente l'accesso di amministrazione automatico** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
La Console di ripristino di emergenza può essere molto utile per la risoluzione dei problemi e la riparazione di computer che non si avviano. Tuttavia, è pericoloso consentire la connessione automatica alla console. Qualsiasi persona potrebbe accedere fisicamente al server, arrestarlo disattivando l'alimentazione, riavviarlo, scegliere **Console di ripristino di emergenza** dal menu **Riavvia**, quindi assumere il controllo completo del server.
  
##### Contromisura
  
Configurare l'impostazione **Console di ripristino di emergenza: consente l'accesso di amministrazione automatico** su **Disabilitato.**
  
##### Impatto potenziale
  
L'utente dovrà immettere un nome utente e una password per accedere alla Console di ripristino di emergenza.
  
#### Console di ripristino di emergenza: consente la copia di dischi floppy e l'accesso a tutte le unità e cartelle
  
Questa impostazione di criterio rende disponibile il comando SET della Console di ripristino di emergenza, che consente di impostare le seguenti variabili di ambiente della console.
  
-   **AllowWildCards**. abilita il supporto dei caratteri jolly per alcuni comandi, ad esempio per il comando DEL.
  
-   **AllowAllPaths**. consente l'accesso a tutti i file e a tutte le cartelle del computer.
  
-   **AllowRemovableMedia**. consente di copiare i file su supporti rimovibili, ad esempio su dischi floppy.
  
-   **NoCopyPrompt**. Sopprime il prompt visualizzato di norma prima di sovrascrivere un file esistente.
  
I possibili valori dell'impostazione **Console di ripristino di emergenza: consente la copia di dischi floppy e l'accesso a tutte le unità e cartelle** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
Un pirata informatico che provochi il riavvio del sistema nella Console di ripristino di emergenza potrebbe rubare i dati riservati senza lasciare itinerari di controllo o di accesso.
  
##### Contromisura
  
Configurare l'impostazione **Console di ripristino di emergenza: consente la copia di dischi floppy e l'accesso a unità e cartelle** su **Disabilitato.**
  
##### Impatto potenziale
  
Gli utenti che hanno avviato un server tramite la Console di ripristino di emergenza e hanno eseguito l'accesso con l'account Administrator predefinito non potranno copiare i file e le cartelle in un disco floppy.
  
#### Arresto del sistema: consente di arrestare il sistema senza effettuare l'accesso
  
Questa impostazione di criterio determina se è possibile arrestare un computer senza prima accedere a Windows. Se questa impostazione di criterio è attivata, il comando **Chiudi sessione** è disponibile sulla schermata di accesso di Windows. Se questa impostazione di criterio è disattivata, l'opzione **Chiudi sessione** viene rimossa dalla schermata di accesso di Windows. Questa configurazione richiede che gli utenti siano in grado di accedere normalmente al computer e disporre del diritto utente **Arresto del sistema** prima di eseguire un nuovo arresto del computer.
  
I possibili valori dell'impostazione **Arresto del sistema: consente di arrestare il sistema senza effettuare l'accesso** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
Gli utenti in grado di accedere localmente alla console possono arrestare il computer.
  
I pirati informatici potrebbero anche accedere fisicamente alla console locale e riavviare il server, in modo da provocare una condizione di tipo DoS. I pirati informatici potrebbero inoltre provocare l'arresto del server in modo che i relativi servizi e applicazioni non siano più disponibili.
  
##### Contromisura
  
Configurare l'impostazione **Consente di arrestare il sistema senza effettuare l'accesso** su **Disabilitato**.
  
##### Impatto potenziale
  
Gli operatori dovranno accedere ai server per arrestarli o riavviarli.
  
#### Arresto del sistema: cancella il file di paging della memoria virtuale
  
Questa impostazione di criterio determina se il contenuto del file di paging della memoria virtuale deve essere cancellato all’arresto del computer. Il supporto della memoria virtuale utilizza un file di paging di sistema per trasferire le pagine di memoria su disco quando non vengono utilizzate. In un computer in esecuzione, il file di paging viene aperto esclusivamente dal sistema operativo ed è ben protetto. Tuttavia, nel caso di computer configurati per consentirne l'avvio ad altri sistemi operativi, potrebbe essere necessario verificare che il relativo file di paging sia stato cancellato prima dell'arresto. In questo modo si impedisce che le informazioni riservate della memoria del processo eventualmente trasferite nel file di paging siano disponibili per gli utenti non autorizzati che tentano di accedere direttamente al file.
  
Se questa impostazione è abilitata, il file di paging viene cancellato all'arresto regolare del sistema. Inoltre, nei computer portatili in cui è disabilitata la sospensione, l'abilitazione di questa impostazione di criterio forzerà il computer a cancellare automaticamente il file di sospensione hiberfil.sys
  
I possibili valori dell'impostazione **Arresto del sistema: cancella il file di paging della memoria virtuale** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
È possibile scrivere periodicamente nel file di paging informazioni importanti conservate nella memoria reale, facilitando la gestione di funzioni multitasking in Windows Server 2003. Un pirata informatico con accesso fisico a un server di cui è stato eseguito l'arresto potrebbe visualizzare il contenuto del file di paging, spostare il volume di sistema in un computer diverso e analizzare quindi il contenuto del file di paging. Questo processo richiede tempo ma potrebbe esporre i dati memorizzati nella cache dalla RAM (Random Access Memory) al file di paging.
  
**Avviso**: un pirata informatico con accesso fisico al server potrebbe aggirare questa contromisura semplicemente scollegando il server dalla presa di alimentazione.
  
##### Contromisura
  
Configurare l'impostazione **Arresto del sistema: cancella il file di paging della memoria virtuale** su **Abilitato**. Abilitando questa configurazione, Windows Server 2003 cancella il file di paging all'arresto del computer. Il tempo richiesto per completare questo processo dipende dalla dimensione del file di paging. Questo processo potrebbe richiedere diversi minuti prima dell'arresto completo del sistema.
  
##### Impatto potenziale
  
Richiederà più tempo per arrestare e riavviare il server, specialmente nel caso di server con file di paging di notevoli dimensioni. Per un server con 2 gigabyte (GB) di RAM e un file di paging da 2 GB, questa impostazione comporta da 20 a 30 minuti aggiuntivi per il processo di arresto. Per alcune organizzazioni, questo tempo di inattività non è conforme agli SLA (Service Level Agreement) interni. Si consiglia pertanto di prestare attenzione durante l'implementazione di questa contromisura nel proprio ambiente.
  
#### Crittografia di sistema: imponi protezione chiave avanzata per chiavi utente archiviate nel computer
  
Questa impostazione di criterio determina se gli utenti possono utilizzare o meno le chiavi private, ad esempio la chiave S/MIME, senza una password.
  
I possibili valori dell'impostazione **Crittografia di sistema: imponi protezione chiave avanzata per chiavi utente archiviate nel computer** sono:
  
-   Non è richiesto alcun input utente per l'archiviazione e l'utilizzo di nuove chiavi
  
-   L'utente riceve una richiesta al primo utilizzo della chiave
  
-   L'utente deve immettere una password ogni volta che utilizza una chiave
  
-   Non definito
  
##### Vulnerabilità
  
È possibile configurare questa impostazione in modo che gli utenti debbano specificare una password diversa da quella di dominio ogni volta che utilizzano una chiave. Questa configurazione renderà più difficile per un pirata informatico l'accesso alle chiavi utente archiviate localmente, anche nel caso in cui assuma il controllo del computer dell'utente e individui la password di accesso.
  
##### Contromisura
  
Configurare l'impostazione **Crittografia di sistema: imponi protezione chiave avanzata per chiavi utente archiviate nel computer** su **L'utente deve immettere una password ogni volta che utilizza una chiave**.
  
##### Impatto potenziale
  
Gli utenti dovranno immettere la relativa password ogni volta che accedono a una chiave archiviata nel computer in uso. Se ad esempio gli utenti utilizzano un certificato S-MIME per aggiungere la firma digitale ai messaggi di posta elettronica, verranno obbligati a immettere la password per tale certificato ogni volta che inviano un messaggio con firma digitale. Per alcune organizzazioni, il sovraccarico dovuto all'utilizzo di questa configurazione potrebbe essere eccessivo. Questa opzione dovrebbe essere impostata per lo meno su **L'utente riceve una richiesta al primo utilizzo della chiave.**
  
#### Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash e firma
  
Questa impostazione di criterio determina se il provider di protezione TLS/SSL supporterà solo il pacchetto di crittografia avanzata noto come TLS\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA, il che significa che il provider supporta solo il protocollo TSL come client e server, se applicabile. Questo provider utilizza esclusivamente l'algoritmo 3DES (Triple Data Encryption Standard) per la crittografia del traffico TLS, l'algoritmo a chiave pubblica RSA (Rivest-Shamir-Adleman) per l'autenticazione e lo scambio di chiave TLS e l'algoritmo SHA-1 (Secure Hash Algorithm versione 1) per i requisiti di hash TLS.
  
Se questa impostazione di criterio è abilitata, il servizio Crittografia file system (EFS) supporta esclusivamente l'algoritmo Triple DES per crittografare i dati dei file. Per impostazione predefinita, l'implementazione di Windows Server 2003 di EFS utilizza AES (Advanced Encryption Standard) con una chiave a 256 bit. L'implementazione di Windows XP utilizza DESX.
  
I possibili valori dell'impostazione **Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia,hashe firma** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
Se si abilita questo criterio, i computer utilizzeranno gli algoritmi più potenti disponibili per crittografia, hash e firma. L'utilizzo di questi algoritmi ridurrà al minimo il rischio di manomissione di dati con firma o crittografia digitale da parte di un utente non autorizzato.
  
##### Contromisura
  
Configurare l'impostazione **Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia,hashe firma** su **Abilitato.**
  
##### Impatto potenziale
  
I computer client in cui questa impostazione di criterio è abilitata non saranno in grado di comunicare mediante protocolli firmati o crittografati digitalmente con i server che non supportano questi algoritmi. I client di rete che non supportano gli algoritmi non potranno utilizzare i server che ne richiedono l'impiego per le comunicazioni di rete. Molti server Web basati su Apache, ad esempio, non sono configurati per il supporto di TLS. Se si abilita questa impostazione, sarà necessario configurare anche Internet Explorer per l'utilizzo di TLS. Questa impostazione di criterio interessa anche il livello di crittografia utilizzato per RDP (Remote Desktop Protocol, Protocollo desktop remoto). Lo strumento di Connessione desktop remoto utilizza il protocollo RDP per comunicare con i server che eseguono Servizi terminal e i computer client configurati per il controllo remoto; non sarà possibile stabilire le connessioni RDP se entrambi i computer non sono configurati per utilizzare gli stessi algoritmi di crittografia.
  
**Per abilitare Internet Explorer all'utilizzo di TLS**
  
1.  Nel menu **Strumenti** di Internet Explorer, aprire la finestra di dialogo **Opzioni Internet**.
  
2.  Selezionare la scheda **Avanzate**.
  
3.  Selezionare la casella di controllo **Usa TLS 1.0**.
  
È possibile configurare l'impostazione anche mediante i criteri di gruppo o il kit per amministratori di Internet Explorer.
  
#### Oggetti di sistema: proprietario predefinito per gli oggetti creati dai membri del gruppo Administrators
  
Questa impostazione di criterio determina se il proprietario predefinito dei nuovi oggetti di sistema deve essere il gruppo **Administrators** o l'utente che ha creato l'oggetto.
  
I possibili valori dell'impostazione **Oggetti di sistema: proprietario predefinito per gli oggetti creati dai membri del gruppo Administrators** sono:
  
-   Gruppo Administrators
  
-   Creatore oggetto
  
-   Non definito
  
##### Vulnerabilità
  
Se questa impostazione del criterio è configurata sul **gruppo** **Administrators**, non sarà possibile assegnare a singoli utenti la responsabilità della creazione di nuovi oggetti di sistema.
  
##### Contromisura
  
Configurare l'impostazione **Oggetti di sistema: proprietario predefinito per gli oggetti creati dai membri del gruppo Administrators** su **Creatore oggetto**.
  
##### Impatto potenziale
  
Quando vengono creati oggetti di sistema, come proprietario di un nuovo oggetto verrà indicato l'account che ha lo creato anziché, in modo più generico, il gruppo **Administrators**. Una conseguenza di questa impostazione di criterio è che quando gli account utente vengono eliminati, gli oggetti diventano orfani. Ad esempio, quando un membro del gruppo IT lascia il gruppo, gli oggetti da lui creati in qualsiasi punto del dominio non avranno più un proprietario. Questa situazione potrebbe comportare un onere amministrativo, in quanto per aggiornare le loro autorizzazioni, gli amministratori dovranno acquisire manualmente la proprietà degli oggetti orfani. Questo onere potenziale può essere ridotto al minimo assicurando che **Controllo completo** venga sempre assegnato ai nuovi oggetti di un gruppo di dominio, ad esempio **Domain Admins**.
  
#### Oggetti di sistema: non richiedere differenziazione tra maiuscole e minuscole per sottosistemi diversi da Windows
  
Questa impostazione di criterio determina se per tutti i sottosistemi deve essere ignorata la differenza tra maiuscole e minuscole. Nel sottosistema Microsoft Win32 viene ignorata la differenza tra maiuscole e minuscole. Tuttavia il kernel supporta la differenziazione tra maiuscole e minuscole per altri sottosistemi, ad esempio per POSIX (Portable Operating System Interface for UNIX). Se si abilita questa impostazione, la differenza tra maiuscole e minuscole viene ignorata per tutti gli oggetti di directory, i collegamenti simbolici e gli oggetti IO, inclusi gli oggetti file. Se si disabilita questa impostazione, il sottosistema Win32 non potrà effettuare comunque la differenza tra maiuscole e minuscole.
  
I possibili valori dell'impostazione **Oggetti di sistema: non richiedere differenziazione tra maiuscole e minuscole per sottosistemi diversi da Windows** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
Poiché Windows ignora la differenza tra maiuscole e minuscole ma il sottosistema POSIX non supporta tale funzionalità, nel caso in cui questa impostazione non venga applicata un utente di tale sottosistema potrebbe creare un file con lo stesso nome di un altro file ma con una combinazione diversa delle lettere maiuscole e minuscole. Questa situazione potrebbe creare confusione quando gli utenti tentano di accedere a questi file con normali strumenti Win32, in quanto sarà disponibile solo uno dei due file.
  
##### Contromisura
  
Configurare l'impostazione **Oggetti di sistema: non richiedere differenziazione tra maiuscole e minuscole per sottosistemi diversi da Windows** su **Abilitato.**
  
##### Impatto potenziale
  
Tutti i sottosistemi verranno forzati a ignorare la differenza tra maiuscole e minuscole. Questo requisito potrebbe confondere gli utenti che in genere utilizzano uno dei sistemi operativi UNIX, in cui tale differenza viene invece osservata.
  
#### Oggetti di sistema: potenzia le autorizzazioni predefinite degli oggetti di sistema interni (ad esempio, i collegamenti simbolici)
  
Questa impostazione determina il livello di potenza del DACL predefinito per gli oggetti. Windows gestisce un elenco globale delle risorse del computer condivise (ad esempio i nomi delle periferiche MS-DOS, i mutex e i semafori), in modo da localizzare e condividere gli oggetti tra i processi.
  
I possibili valori dell'impostazione **Oggetti di sistema: potenzia le autorizzazioni predefinite degli oggetti di sistema interni (ad esempio, i collegamenti simbolici)** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
Questa impostazione determina il livello di potenza del DACL predefinito per gli oggetti. Windows Server 2003 gestisce un elenco globale delle risorse del computer condivise, in modo da localizzare e condividere gli oggetti tra i processi. Ogni tipo di oggetto viene creato con un DACL predefinito che specifica gli utenti a cui è consentito accedere agli oggetti e le autorizzazioni concesse. Se questa impostazione è attivata, il DACL predefinito risulta rafforzato e consente agli utenti che non sono amministratori di leggere gli oggetti condivisi, ma non di modificare quelli non creati da loro.
  
##### Contromisura
  
Configurare l'impostazione **Oggetti di sistema: potenzia le autorizzazioni predefinite degli oggetti di sistema globali (ad esempio,** **i collegamenti simbolici)** su **Abilitato**.
  
##### Impatto potenziale
  
Nessuno. Si tratta della configurazione predefinita.
  
#### Impostazioni di sistema: sottosistemi facoltativi
  
Questa impostazione di criterio determina i sottosistemi che supportano le applicazioni in uso. Mediante questa impostazione di protezione è possibile specificare il numero desiderato di sottosistemi di supporto necessari per il proprio ambiente.
  
I possibili valori dell'impostazione **Impostazioni di sistema: sottosistemi facoltativi** sono:
  
-   Un elenco di sottosistemi definito dall'utente
  
-   Non definito
  
##### Vulnerabilità
  
Il sottosistema POSIX è uno standard IEEE (Institute of Electrical and Electronic Engineers) che definisce un insieme di servizi per il sistema operativo. Questo sottosistema POSIX è necessario se il server supporta applicazioni che utilizzano tale sottosistema.
  
Il sottosistema POSIX introduce un rischio relativo ai processi potenzialmente permanenti tra un accesso e l'altro. Se un utente avvia un processo e quindi si disconnette, l'utente successivo che si collega al computer potrebbe accedere al processo dell'utente precedente. Tale implicazione comporta un certo pericolo, perché qualsiasi operazione eseguita dal secondo utente mediante tale processo sarà basata sui privilegi del primo utente.
  
##### Contromisura
  
Configurare l'impostazione **Impostazioni di sistema: sottosistemi facoltativi** su un valore Null. Il valore predefinito è **POSIX**.
  
##### Impatto potenziale
  
Le applicazioni basate sul sottosistema POSIX non potranno più funzionare. Ad esempio, Microsoft Services for Unix (SFU) 3.0 installa una versione aggiornata del sottosistema POSIX che richiede tale sottosistema; pertanto sarà necessario riconfigurare questa impostazione nei criteri di gruppo per qualsiasi server che utilizza SFU.
  
#### Impostazioni di sistema: impostazioni di sistema: utilizza regole certificati con i file eseguibili di Windows per i criteri di restrizione software
  
Questa impostazione di criterio determina se elaborare o meno i certificati digitali quando i criteri di restrizione software sono abilitati e un utente o un processo sta tentando di eseguire software con un'estensione del nome file exe. Questa impostazione consente di abilitare o disabilitare le regole certificati, ovvero un tipo di criteri di restrizione software. Mediante i criteri di restrizione software è possibile creare un regola certificato che consenta o impedisca l'esecuzione di software con firma Microsoft Authenticode, in base al relativo certificato digitale associato. Per consentire alle regole certificato di funzionare nei criteri di restrizione software, è necessario abilitare questa impostazione di protezione.
  
I possibili valori dell'impostazione **Impostazioni di sistema: impostazioni di sistema: utilizza regole certificati con i file eseguibili di Windows per i criteri di restrizione software** sono:
  
-   Abilitato
  
-   Disabilitato
  
-   Non definito
  
##### Vulnerabilità
  
I criteri di restrizione software aiutano a proteggere gli utenti e i computer, in quanto sono in grado di impedire l'esecuzione di un codice non autorizzato, come ad esempio virus e cavalli di Troia.
  
##### Contromisura
  
Configurare l'impostazione **Impostazioni di sistema: impostazioni di sistema: utilizza regole certificati con i file eseguibili di Windows per i criteri di restrizione software** su **Abilitato.**
  
##### Impatto potenziale
  
Quando l'impostazione delle regole certificati è attivata, i criteri di restrizione software controllano un elenco di certificati revocati (CRL, Certificate Revocation List) per accertare che il certificato e la firma del software siano validi. All'avvio dei programmi firmati, il processo di verifica potrebbe influire negativamente sulle prestazioni. È possibile disabilitare questa funzionalità modificando i criteri di restrizione software nell'oggetto Criteri di gruppo desiderato. Nella finestra di dialogo **Proprietà - Autori attendibili**, deselezionare le caselle di controllo **Autore** e **Timestamp**.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
I seguenti collegamenti forniscono ulteriori informazioni sulle opzioni di protezione in Windows Server 2003 e Windows XP.
  
-   Per maggiori informazioni sulle limitazioni di accesso predefinite del computer COM in Windows XP, vedere la guida "[Managing Windows XP Service Pack 2 Features Using Group Policy: Security-Related Policy Settings](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/sp2/mngsecps.mspx)" (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/winxppro/maintain/mangxpsp2/mngsecps.mspx.
  
-   Per informazioni sulle limitazioni di accesso COM predefinite in Windows Server 2003 con SP1, consultare la sezione "DCOM Security Enhancements" della guida "[Changes to Functionality in Microsoft Windows Server 2003 Service Pack 1](http://technet.microsoft.com/it-it/library/cc784458.aspx)" (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/BookofSP1/.
  
-   Per ulteriori informazioni sull'abilitazione di NTLMv2, vedere l'articolo della Microsoft Knowledge Base "[Attivazione dell'autenticazione NTLM 2](http://support.microsoft.com/kb/239869/it)" all'indirizzo http://support.microsoft.com/default.aspx?scid=239869.
  
-   Per ulteriori informazioni su come assicurare che le impostazioni di livello di autenticazione di LAN Manager più sicure collaborino su reti miste Windows 2000 e Windows NT 4.0, consultare l'articolo della Microsoft Knowledge Base "[I problemi di autenticazione in Windows 2000 con NTLM 2 livellano sopra 2 in un dominio di Windows NT 4.0](http://support.microsoft.com/kb/305379/it)" all'indirizzo http://support.microsoft.com/kb/305379/it.
  
-   Per ulteriori informazioni sui livelli di compatibilità del LAN Manager, vedere l'articolo della Microsoft Knowledge Base "[Possibili incompatibilità tra client, servizi e programmi quando si modificano le impostazioni di protezione e le assegnazioni diritti utente](http://support.microsoft.com/kb/823659/it)" all'indirizzo http://support.microsoft.com/kb/823659/it.
  
-   Per ulteriori informazioni sull'autenticazione NTLMv2, vedere l'articolo della Microsoft Knowledge Base "[Attivazione dell'autenticazione NTLM 2](http://support.microsoft.com/kb/239869/it)" all'indirizzo http://support.microsoft.com/kb/239869/it.
  
-   Per ulteriori informazioni su come ripristinare le impostazioni di protezione predefinite a livello locale, consultare l'articolo della Microsoft Knowledge Base “[How to: Reimpostare le opzioni di protezione predefinite](http://support.microsoft.com/kb/313222/it)” all'indirizzo http://support.microsoft.com/kb/313222/it.
  
-   Per ulteriori informazioni su come ripristinare le impostazioni di protezione predefinite negli oggetti dei criteri di gruppo integrati del dominio, consultare l'articolo della Microsoft Knowledge Base “[Reimpostazione dei diritti utente nei criteri di gruppo di dominio predefiniti in Windows Server 2003](http://support.microsoft.com/kb/324800/it)” a http://support.microsoft.com/kb/324800/it.
  
**Download**
  
[Scaricare la Guida a pericoli e contromisure](http://go.microsoft.com/fwlink/?linkid=15160)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:secwish@microsoft.com?subject=guida%20a%20pericoli%20e%20contromisure)
  
[](#mainsection)[Inizio pagina](#mainsection)
