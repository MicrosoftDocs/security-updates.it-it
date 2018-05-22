---
TOCTitle: 'Guida alla pianificazione della protezione dei servizi e degli account dei servizi - Capitolo 3'
Title: 'Guida alla pianificazione della protezione dei servizi e degli account dei servizi - Capitolo 3'
ms:assetid: '795b3f6b-fd1d-498a-a54c-b6ac4213b8e6'
ms:contentKeyID: 20200870
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536271(v=TechNet.10)'
---

Guida alla pianificazione della protezione dei servizi e degli account dei servizi
==================================================================================

### Capitolo 3 - Esecuzione protetta dei servizi

Aggiornato : maggio 31, 2005

In questo capitolo verranno illustrate le attività che devono essere eseguite per aumentare la protezione durante l'esecuzione dei servizi, sfruttando gli approcci e i principi discussi nel capitolo precedente.

Per proteggere i servizi, è necessario effettuare le seguenti attività:

-   Controllo di tutti i server allo scopo di determinare le proprietà dei servizi essenziali

-   Determinazione dei servizi effettivamente necessari

-   Individuazione ed eliminazione di tutti gli account Administrator del dominio per i servizi

-   Distribuzione dei servizi mediante una gerarchia basata sul privilegio minimo

-   Creazione di un gruppo di server con livello di protezione alto per le eccezioni di amministratore del dominio

-   Gestione dei cambiamenti delle password degli account computer

-   Utilizzo di password complesse

-   Test automatici per la ricerca delle password amministratore vulnerabili

##### In questa pagina

[](#ehaa)[Controllo di tutti i server allo scopo di individuare le proprietà dei servizi essenziali](#ehaa)  
[](#egaa)[Determinazione dei servizi effettivamente necessari](#egaa)  
[](#efaa)[Individuazione ed eliminazione di tutti gli account Administrator del dominio per i servizi](#efaa)  
[](#eeaa)[Distribuzione dei servizi mediante una gerarchia basata sul privilegio minimo](#eeaa)  
[](#edaa)[Creazione di un gruppo di server con livello di protezione alto per le eccezioni di amministratore del dominio](#edaa)  
[](#ecaa)[Gestione dei cambiamenti delle password degli account computer](#ecaa)  
[](#ebaa)[Utilizzo di password complesse](#ebaa)  
[](#eaaa)[Test automatici per la ricerca delle password amministratore vulnerabili](#eaaa)

### Controllo di tutti i server allo scopo di individuare le proprietà dei servizi essenziali

Per un'organizzazione è indispensabile conoscere il numero esatto dei server presenti nella rete interna. Sebbene possa sembrare un compito abbastanza semplice, nelle organizzazioni di grandi dimensioni può essere estremamente complicato riuscire a individuare tutti i server disponibili e determinare il livello di gestione richiesto dai servizi in esecuzione su ciascun computer. I computer in esecuzione nella rete perimetrale richiedono, ad esempio, livelli di gestione dei servizi molto più alti per ridurre la superficie di attacco di questi computer.

È necessario controllare ciascun server in modo da elencare tutti i servizi in esecuzione e registrare le credenziali di accesso utilizzate da ciascun servizio per l'autenticazione. A questo scopo, è possibile utilizzare i seguenti strumenti:

-   **System Information in Microsoft® Windows Server™ 2003**. È possibile utilizzare System Information per visualizzare l'elenco completo delle proprietà di tutti i servizi in esecuzione sul computer locale o su altri computer remoti. Questo metodo, tuttavia, non è adatto alle situazioni in cui è necessario controllare un numero elevato di server. Per accedere a questo strumento, scegliere **Start**, **Tutti i programmi**, quindi **Accessori**, **Utilità di sistema** e infine **System Information**.

-   **Console Gestione Servizi**. Nella console di amministrazione Servizi è possibile utilizzare la scheda **Connessione** nella pagina delle proprietà di un servizio per determinare l'account di accesso utilizzato dal servizio per l'autenticazione. È anche possibile utilizzare la scheda **Relazioni di dipendenza** per visualizzare i servizi da cui dipende il servizio corrente e quelli che dipendono dal servizio corrente. Le informazioni sulla dipendenza sono essenziali per il controllo dei server. Questo metodo, tuttavia, non è adatto alle situazioni in cui è necessario controllare un numero elevato di server.

-   **Strumentazione gestione Windows (WMI)**.Lo strumento WMI consente di ottenere informazioni sui servizi in esecuzione su tutti server. È possibile utilizzare WMI con strumenti di programmazione o utilità di script, ad esempio Windows Scripting Host, per recuperare i dettagli di configurazione relativi alla maggior parte degli aspetti dei computer o per apportare modifiche ai computer. Numerosi strumenti di gestione, ad esempio Proprietà del sistema, System Information e il componente Relazioni di dipendenza della console Servizi, sono compatibili con la tecnologia WMI. Le relazioni di dipendenza indicano i servizi da cui dipende il servizio corrente e quelli che dipendono dal servizio corrente.

-   **Strumentazione gestione Windows da riga di comando (WMIC)**.WMI fornisce una semplice interfaccia da riga di comando per la gestione dei computer remoti su cui sono in esecuzione sistemi operativi Windows. WMIC è in grado di interagire con le shell e i comandi di utilità esistenti e può essere facilmente esteso con script o altre applicazioni di amministrazione.

    È possibile, ad esempio, utilizzare il comando **wmic service get** per ottenere informazioni su tutte le proprietà di un determinato servizio, tra cui:

    -   Description

    -   DisplayName

    -   ErrorControl

    -   InstallDate

    -   PathName

    -   ProcessId

    -   StartMode

    -   StartName

    -   Status

    Esempio di sintassi:

    **Nota:** per facilitare la lettura, alcune parti del seguente frammento di codice sono state visualizzate su più righe. Il comando, tuttavia, deve essere immesso in un'unica riga.
    
     ```
     SERVICE GET Name,DisplayName,ProcessId,Started, StartMode,StartName
     ```

    È possibile utilizzare il comando **wmic service list brief** per visualizzare le seguenti proprietà di base di tutti i servizi installati:

    -   ExitCode

    -   Name

    -   ProcessId

    -   StartMode

    -   State

    -   Status

    Lo strumento WMIC può essere utilizzato da qualsiasi computer in cui è installato WMIC per gestire un qualsiasi computer remoto su cui è in esecuzione WMI. Per la gestione remota, non è necessario che nel computer di destinazione sia installato o in esecuzione WMIC. Per gestire un computer in remoto, è necessario utilizzare il comando **/node:***&lt;nomecomputer&gt;*, che consente di aggiungere il computer all'elenco dei nodi da cui si desidera recuperare le informazioni.

    Esempio di sintassi:

    **Nota:** per facilitare la lettura, alcune parti del seguente frammento di codice sono state visualizzate su più righe. Il comando, tuttavia, deve essere immesso in un'unica riga.

    ```
    WMIC /NODE:Server1,Server2,Server3 SERVICE GET Name,DisplayName,ProcessId,Started,StartMode, SystemName
    ```

    È anche possibile specificare il percorso di un file di testo in cui sono elencati i computer remoti sui quali si desidera utilizzare WMIC per eseguire azioni.

    Esempio di sintassi:

    ```
    WMIC /NODE:@"C:\ElencoServer.txt" SERVICE LIST BRIEF
    ```

    Di seguito sono elencati alcuni scenari tipici in cui è possibile utilizzare WMIC per facilitare l'esecuzione delle attività:

    -   **Gestione locale di un computer**. L'utente utilizza il comando WMIC dal computer in uso per la gestione di quest'ultimo.

    -   **Gestione remota di un computer**. L'utente utilizza il comando WMIC dal computer in uso per la gestione di un altro computer.

    -   **Gestione remota di più computer**. L'utente utilizza WMIC dal computer in uso per la gestione di più computer con un unico comando.

    -   **Gestione remota di un computer mediante una sessione remota**. L'utente utilizza strumenti di connessione remota, ad esempio Telnet o Servizi terminal, per connettersi a un computer remoto ed eseguirne la gestione con WMIC.

-   **Gestione automatica mediante la creazione di script amministrativi**.È possibile utilizzare WMIC per creare un semplice script in modo da automatizzare la gestione di uno o più computer (locali o remoti), sia in serie che simultaneamente.

    Per ulteriori informazioni su WMI, vedere l'articolo [WMI: Introduction to Windows Management Instrumentation](http://msdn.microsoft.com/it-it/library/ms799738.aspx) all'indirizzo www.microsoft.com/whdc/system/pnppwr/wmi/
    WMI-intro.mspx (informazioni in lingua inglese) e la pagina [Windows Management Instrumentation overview](http://technet.microsoft.com/it-it/library/cc736575.aspx) all'indirizzo www.microsoft.com/windows2000/en/server/
    help/windows\_WMI\_overview.htm?id=751 (informazioni in lingua inglese).

-   **Altri strumenti di gestione aziendale**. Sono disponibili numerosi altri strumenti di gestione a scopo di controllo, tra cui:

    -   Microsoft Systems Management Server

    -   Tivoli

    -   OpenView

    -   Lieberman Software Service Account Manager

La creazione di un elenco principale di server e relativi servizi consente di individuare ed eliminare eventuali rischi di protezione associati ai servizi.

È possibile utilizzare il sistema di controllo per creare un inventario di tutti i servizi che utilizzano uno dei seguenti account:

-   Account utente di dominio con privilegi di amministratore del dominio

-   Singolo account utente di dominio utilizzato su più server

[](#mainsection)[Inizio pagina](#mainsection)

### Determinazione dei servizi effettivamente necessari

La prima volta che si installa Windows Server 2003 vengono creati automaticamente alcuni servizi predefiniti, che vengono quindi configurati per essere eseguiti all'avvio del computer. Nella cartella di lavoro Microsoft Excel "Windows Default Security and Services Configuration", fornita con [*Threats and Countermeasures Guide*](http://www.microsoft.com/technet/security/topics/serversecurity/tcg/tcgch00.mspx) (informazioni in lingua inglese), sono indicate le impostazioni predefinite per il tipo di avvio di tutti i servizi di sistema.

Questi servizi predefiniti assicurano la compatibilità delle applicazioni o dei client, facilitando quindi la gestione dei sistemi. È probabile, tuttavia, che non tutti questi servizi siano effettivamente necessari nell'ambiente dell'organizzazione. Si consiglia, quindi, di effettuare un'analisi approfondita per determinare con esattezza i servizi necessari.

L'individuazione dei servizi effettivamente necessari e di quelli da disattivare può essere un processo abbastanza complicato. Per alcuni servizi la disattivazione può sembrare ovvia, mentre per altri potrebbe non essere lo stesso. Si consiglia di utilizzare la seguente strategia di base:

-   Se non si ha un motivo specifico per utilizzare un determinato servizio, disattivarlo.

-   Se si ritiene che il servizio potrebbe essere utile in futuro, disattivarlo fino a quando non deve essere utilizzato.

I servizi che devono essere eseguiti in un computer dipendono in maniera significativa dal ruolo del computer. Internet Information Services (IIS), ad esempio, deve essere installato soltanto in un server Web o in un computer che richiede IIS, ad esempio un server applicazioni. Se il server non deve contenere servizi di accesso remoto o sessioni Telnet, è opportuno disattivarli o rimuoverli. Esistono alcune situazioni in cui determinate applicazioni software, ad esempio gli strumenti per la gestione dei sistemi, aggiungono servizi propri a quelli in esecuzione sui computer. È importante essere a conoscenza di questi servizi, degli account utilizzati per l'accesso e del livello di accesso richiesto.

Microsoft ha pubblicato diverse guide in cui viene spiegato come individuare i servizi da bloccare in base al ruolo dei computer. In queste guide vengono indicati i servizi necessari per determinati ruoli, ad esempio controller di dominio, server Web, client Windows XP, e così via. Per ulteriori informazioni, vedere:

-   [*Introduzione alla protezione di Windows 2003*](http://go.microsoft.com/fwlink/?linkid=14845) all'indirizzo http://go.microsoft.com/fwlink/?linkid=14845

-   [*Guida per la protezione di Windows XP*](http://technet.microsoft.com/it-it/library/cc163061.aspx) all'indirizzo http://go.microsoft.com/
    fwlink/?LinkId=14839

-   [*Windows 2000 Security Hardening Guide*](http://go.microsoft.com/fwlink/?linkid=22380) all'indirizzo http://go.microsoft.com/fwlink/?LinkID=22380 (informazioni in lingua inglese)

-   [*Requisiti delle porte per il sistema di server Microsoft Windows*](http://support.microsoft.com/?kbid=832017) all'indirizzo http://support.microsoft.com/
    ?kbid=832017

In un ambiente di test o di preproduzione, per determinare se un servizio è necessario, è possibile disattivarlo e quindi monitorare il computer per un certo periodo di tempo allo scopo di individuare eventuali problemi di funzionamento. Tenere presente, tuttavia, che per alcuni servizi di base, ad esempio RPC (Remote Procedure Call) e Plug and Play, non sarà possibile, dalla console Servizi, né arrestare il servizio né modificare il tipo di avvio. Per altri servizi, invece, ad esempio Registro eventi e Gestione account di protezione (SAM), non sarà possibile arrestare il servizio ma sarà comunque consentita la modifica del tipo di avvio.

Se non si è sicuri sulla funzione di un determinato servizio, effettuare una o più delle seguenti operazioni per ottenere ulteriori informazioni:

-   Vedere le descrizioni più dettagliate dei servizi nel Capitolo 7 "System Services" in [*Threats and Countermeasures Guide*](http://technet.microsoft.com/it-it/library/dd162275.aspx), disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15160 (informazioni in lingua inglese).

-   Leggere la descrizione del servizio. Per accedere alla descrizione, aprire la console Servizi, individuare il servizio di interesse, fare clic con il pulsante destro del mouse sul nome del servizio, quindi scegliere **Proprietà**.

-   Utilizzare la Configurazione guidata impostazioni di sicurezza per ottenere la descrizione di un servizio.

La Configurazione guidata impostazioni di sicurezza, fornita con Windows Server 2003 con Service Pack 1 (SP1), può risultare estremamente utile per l'individuazione dei servizi effettivamente necessari.

#### Riduzione della superficie di attacco con la Configurazione guidata impostazioni di sicurezza

La Configurazione guidata impostazioni di sicurezza (SCW) consente di eseguire in modo semplice e rapido la configurazione dei server con Microsoft Windows in base ai requisiti funzionali dell'organizzazione (server Web, controller di dominio, e così via), consentendo inoltre di definire criteri di protezione per ridurre al minimo la vulnerabilità dei computer agli attacchi. Per installare SCW, nel Pannello di controllo fare doppio clic su **Installazione applicazioni**, fare clic su **Installazione componenti di Windows**, quindi nell'elenco **Componenti** della pagina **Componenti di Windows** selezionare la casella di controllo **Configurazione guidata impostazioni di sicurezza**, fare clic su **Avanti** e, al termine della procedura guidata, fare clic su **Fine**. A questo punto, verrà aggiunto un collegamento Configurazione guidata impostazioni di sicurezza alla cartella Strumenti di amministrazione.

La Configurazione guidata impostazioni di sicurezza consente di individuare i servizi attualmente in esecuzione nei server dell'organizzazione nonché le eventuali dipendenze da altri servizi. Questa procedura può anche essere utile durante la distribuzione dei nuovi server per determinare i servizi effettivamente necessari. Per implementare i criteri generati da SCW è possibile utilizzare Criteri di gruppo, che consente di distribuire contemporaneamente specifici ruoli server su più computer simili all'interno di un'unità organizzativa o di una gerarchia di unità organizzative.

Il termine *ruolo server* definisce le funzioni principali svolte da un computer all'interno dell'organizzazione, ad esempio file server, controller di dominio o server Web. Poiché i servizi necessari, le porte in ingresso e le impostazioni variano in base al ruolo, i criteri SCW creati devono corrispondere al ruolo che si desidera assegnare a ciascun computer.

È possibile utilizzare la Configurazione guidata impostazioni di sicurezza per ridurre la superficie di attacco dei computer su cui è in esecuzione Windows Server 2003 con SP1. Durante la procedura guidata viene illustrato come creare un criterio di protezione in base ai ruoli svolti da un determinato server. Una volta creato, il criterio può essere applicato a uno o più server configurati in modo simile.

La Configurazione guidata impostazioni di sicurezza è costituita dalle seguenti sezioni:

-   Configurazione dei servizi in base ai ruoli

-   Protezione di rete

-   Impostazioni del Registro di sistema

-   Criteri di controllo

-   Internet Information Services (visibile solo quando è selezionato il ruolo Server Web)

Ai fini della presente guida, l'unica sezione rilevante è Configurazione dei servizi in base ai ruoli, che consente di configurare i servizi in base ai ruoli e ad altre funzionalità del server selezionato.

Il criterio di protezione viene creato in base ai ruoli installati nel server selezionato. Quest'ultimo può essere un server a cui si desidera applicare il criterio oppure un server utilizzato semplicemente per la creazione del criterio che verrà quindi applicato a un gruppo di server in cui sono definiti ruoli simili.

#### Funzionamento della Configurazione guidata impostazioni di sicurezza

La Configurazione guidata impostazioni di sicurezza consente di ridurre la superficie di attacco dei server su cui è in esecuzione Windows. A questo scopo, viene chiesto all'utente di rispondere a una serie di domande appositamente studiate per determinare i requisiti funzionali di un server e vengono quindi disattivate le funzionalità non richieste dai ruoli svolti dal server. Oltre a costituire una fondamentale procedura di protezione consigliata, la riduzione della superficie di attacco consente di aumentare la diversificazione dell'ambiente Windows dell'organizzazione, riducendo quindi il numero dei computer che richiedono un aggiornamento immediato in caso di individuazione di eventuali vulnerabilità.

La Configurazione guidata impostazioni di sicurezza consente di risolvere uno dei principali problemi relativi a Windows Server 2003, ovvero l'individuazione dei servizi che possono essere disattivati.

Finora, trovare una risposta a questo problema è sempre stato difficile a causa dell'enorme quantità di combinazioni possibili di tecnologie installate, ognuna delle quali con una gerarchia di dipendenze presenti in un qualsiasi computer Windows. Quando si aggiungono altri server, ad esempio Microsoft Exchange Server o SQL Server™, le dipendenze cambiano nuovamente. La Configurazione guidata impostazioni di sicurezza consente di risolvere questo problema fornendo all'amministratore uno strumento per configurare i server in modo che vengano eseguiti soltanto i servizi effettivamente richiesti dai ruoli assegnati a un server. A questo scopo, viene utilizzato un database Extensible Markup Language (XML) in cui sono contenuti i dati necessari relativi a Windows Server 2003 e ai prodotti Microsoft in esecuzione in Windows Server 2003.

#### Vantaggi della Configurazione guidata impostazioni di sicurezza

L'utilizzo della Configurazione guidata impostazioni di sicurezza per la scelta dei ruoli funzionali consente di ottenere automaticamente i seguenti vantaggi:

-   Disattivazione dei servizi non necessari

-   Disattivazione delle estensioni Web di IIS

-   Blocco delle porte non utilizzate

#### Limitazioni della Configurazione guidata impostazioni di sicurezza

Sebbene la Configurazione guidata impostazioni di sicurezza non blocchi le impostazioni di protezione, ad esempio il livello di autenticazione LM e la firma SMB (Server Message Block), nelle guide sulla protezione di Windows Server 2003 e Windows XP elencate precedentemente in questa sezione vengono fornite ulteriori informazioni su questo argomento insieme ad alcuni suggerimenti per queste impostazioni.

[](#mainsection)[Inizio pagina](#mainsection)

### Individuazione ed eliminazione di tutti gli account Administrator del dominio per i servizi

Utilizzando le informazioni ottenute dal controllo dei server, è possibile individuare ed eliminare tutti i possibili account Administrator del dominio utilizzati per i servizi. L'eliminazione del più alto numero possibile di servizi che utilizzano account Administrator del dominio è un'operazione fondamentale per la protezione dei servizi. Se possibile, si consiglia di ripetere la distribuzione dei servizi utilizzando gli account del servizio locale, del servizio di rete e di sistema locale, come descritto nella sezione successiva di questo capitolo.

Di seguito sono indicate alcune distribuzioni di servizi che le organizzazioni dovrebbero tentare di eliminare:

-   Account utente con privilegi equivalenti a quelli di amministratore che accedono come servizio.

-   Account amministratore predefiniti che accedono come servizio.

-   Account Administrator del dominio che accedono come servizio a server con livello di protezione basso.

[](#mainsection)[Inizio pagina](#mainsection)

### Distribuzione dei servizi mediante una gerarchia basata sul privilegio minimo

Si dovrebbe sempre utilizzare l'account che dispone del privilegio minimo richiesto per l'esecuzione di un servizio. I servizi distribuiti con account con livelli di privilegio più alti dovrebbero essere ridistribuiti utilizzando account con livelli di privilegio inferiori.

Di seguito è riportato l'ordine di utilizzo degli account in una strategia basata sul privilegio minimo:

1.  **Servizio locale**. Questo account è simile a quello di sistema locale, anche se dispone del livello di privilegio minimo sul computer locale. I servizi che accedono al sistema con l'account del servizio locale possono accedere alle risorse di rete utilizzando una sessione Null con credenziali anonime. L'account deve disporre soltanto dei privilegi necessari per il corretto funzionamento del servizio.

2.  **Servizio di rete**. Questo account è simile a quello di sistema locale, anche se dispone del livello di privilegio minimo sul computer locale. I servizi che accedono al sistema con l'account del servizio di rete possono accedere alle risorse di rete utilizzando le credenziali dell'account computer, dove il computer è indicato come &lt;*nome\_dominio\\nome\_computer*&gt;$. L'account deve disporre soltanto dei privilegi necessari per il corretto funzionamento del servizio.

3.  **Account utente univoco**. Un servizio deve essere eseguito come account utente univoco solo se non è possibile eseguirlo come account del servizio locale o del servizio di rete. Si dovrebbe utilizzare un account utente locale univoco per l'esecuzione dei servizi che richiedono soltanto privilegi sul computer locale, ad esempio IIS e SQL Server. Tuttavia, le applicazioni che devono essere eseguite su computer distribuiti, ad esempio Systems Management Server e Microsoft Operations Manager, dovranno utilizzare un account utente di dominio univoco. Quest'ultimo dovrà essere utilizzato anche per le applicazioni che richiedono l'accesso alle risorse di rete. È necessario utilizzare un account utente di dominio univoco separato per ciascuna applicazione che richiede tale account. Se ad esempio vengono eseguite più applicazioni ASP.NET, occorre assicurarsi che ciascuna applicazione utilizzi il proprio account utente univoco e che ciascuno di questi disponga soltanto dei privilegi necessari per il corretto funzionamento del servizio. È possibile assegnare a questo account privilegi amministrativi aggiuntivi per i quali il servizio è configurato, ma solo se necessario. Occorre inoltre che l'account utente univoco appartenga soltanto ai gruppi effettivamente richiesti. Gli account utente univoci devono rispettare i criteri dell'organizzazione per l'utilizzo delle password di protezione. Se più computer utilizzano lo stesso servizio o servizi correlati, è necessario inoltre che le password di ciascun account utente siano univoche.

4.  **Sistema locale**. Tenere presente che i servizi che accedono come account di sistema locale dispongono di privilegi estesi sul computer locale e presentano sulla rete le credenziali del computer, indicate come &lt;*nome\_dominio\\nome\_computer*&gt;$. L'account deve disporre soltanto dei privilegi necessari per il corretto funzionamento del servizio.

5.  **Account amministratore locale**. Un servizio deve essere eseguito con un account amministratore locale solo se non è possibile eseguirlo come account del servizio locale, del servizio di rete, di sistema locale o utente di dominio. Per abbassare di livello un servizio eseguito come amministratore locale, in alcuni casi è possibile utilizzare un account utente locale e aggiungere determinati privilegi necessari o modificare le voci dell'elenco di controllo di accesso di sistema (SACL). È preferibile utilizzare uno di questi approcci anziché un servizio di terze parti di cui non si hanno informazioni certe su eventuali vulnerabilità in caso di esecuzione con un account amministratore del computer. È consigliabile inoltre coinvolgere i fornitori di software nei processi di valutazione e acquisto dei prodotti, in modo che siano consapevoli dell'importanza di disporre di servizi basati sul principio del privilegio minimo nell'ambito dell'organizzazione. Si dovrebbe inoltre convincere i fornitori di software a eseguire i propri servizi con l'account amministratore. A questo scopo, è necessario che il fornitore sia a conoscenza delle risorse a cui il servizio deve effettivamente accedere e dei livelli di autorizzazione richiesti. È necessario assegnare i privilegi di amministratore locale dell'account soltanto al computer in cui il servizio è configurato, e solo se necessario. L'account amministratore locale deve rispettare i criteri dell'organizzazione per l'utilizzo delle password di protezione. Se più computer utilizzano lo stesso servizio o servizi correlati, è necessario inoltre che le password di ciascun account amministratore locale siano univoche.

6.  **Account Administrator del dominio**. Lo scenario peggiore per la protezione è rappresentato dall'esecuzione di un servizio con un account Administrator del dominio. Le organizzazioni dovrebbero fare il possibile per eliminare questo tipo di situazioni. Con questo approccio, tutti i computer in questo scenario devono essere gestiti come server con livello di protezione alto utilizzando le stesse misure di protezione dei controller di dominio o di altre risorse di rete critiche. Nelle sezioni successive verranno fornite informazioni più dettagliate sui server con livello di protezione alto.

Nel diagramma di flusso riportato nella seguente figura sono indicati gli aspetti da prendere in considerazione per la scelta del tipo di account da utilizzare per l'esecuzione protetta dei servizi.

[![](images/Dd536271.PGFG0301(it-it,TechNet.10).jpg "Dd536271.PGFG0301(it-it,TechNet.10).jpg")](https://technet.microsoft.com/it-it/dd536271.pgfg0301_big(it-it,technet.10).gif)

**Figura 3.1. Distribuzione dei servizi mediante una gerarchia basata sul privilegio minimo**

[](#mainsection)[Inizio pagina](#mainsection)

### Creazione di un gruppo di server con livello di protezione alto per le eccezioni di amministratore del dominio

Se si determina che un servizio richiede l'autenticazione a livello di amministratore del dominio, è necessario ospitare tale servizio su un server con livello di protezione alto. Questi server in genere includono:

-   Controller di dominio.

-   Server che eseguono servizi configurati per l'accesso come account con privilegi equivalenti a quelli di amministratore del dominio.

-   Server di tipo trusted per la delega all'interno di un insieme di strutture.

-   Server che eseguono servizi che sono stati resi trusted per la delega all'interno di un insieme di strutture mediante il metodo di delega vincolata in Windows Server 2003. Per ulteriori informazioni su questa funzionalità, vedere [Kerberos Protocol Transition and Constrained Delegation](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/constdel.mspx) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/
    technologies/security/constdel.mspx (informazioni in lingua inglese).

Di seguito viene riportata la procedura per la creazione di un gruppo di server con livello di protezione alto:

1.  Scegliere i server da designare come server con livello di protezione alto.

2.  Creare un gruppo di protezione universale in ciascun insieme di strutture dell'organizzazione denominato, ad esempio, Server con livello di protezione alto.

3.  Aggiungere gli account computer dei server protetti designati ai nuovi gruppi universali.

4.  In ogni dominio di ciascun insieme di strutture creare un gruppo locale di dominio denominato, ad esempio, Tutti gli account amministratore del dominio, quindi aggiungere a questo nuovo gruppo gli account utente con privilegi equivalenti a quelli di amministratore del dominio.

5.  In ogni dominio di ciascun insieme di strutture creare un oggetto Criteri di gruppo a livello di dominio, quindi impostare su tutti i computer il criterio per limitare l'utilizzo degli account amministratore a livello di dominio per l'esecuzione dei servizi. Impostare il criterio sui diritti utente **Nega accesso come servizio** e **Nega accesso come processo batch**, quindi applicare **Consenti-Lettura e Consenti-Applica autorizzazioni** sull'oggetto Criteri di gruppo al gruppo locale di dominio Tutti gli account amministratore del dominio appena creato.

6.  In ogni dominio di ciascun insieme di strutture utilizzare la funzionalità filtro di Criteri di gruppo per il gruppo di server con livello di protezione alto su ciascun oggetto Criteri di gruppo per consentire ai membri di questo gruppo di utilizzare comunque gli account amministratore a livello di dominio per l'esecuzione dei servizi. A questo scopo, applicare **Consenti-Lettura e Nega-Applica autorizzazioni** sull'oggetto Criteri di gruppo soltanto al gruppo universale Server con livello di protezione alto.

Per gestire correttamente l'appartenenza del gruppo universale Server con livello di protezione alto, è necessario definire un processo flusso di lavoro interno per la richiesta di aggiunte al gruppo. Se si aggiunge il server richiesto al gruppo, questo processo deve includere i passaggi per la convalida della richiesta e la valutazione dei relativi rischi di protezione. Sebbene il processo flusso di lavoro sia semplice come l'invio di un messaggio di posta elettronica a un alias di richiesta, è consigliabile eseguirlo come procedura automatica. In [Solution Accelerator for Business Desktop Deployment Enterprise Edition](http://go.microsoft.com/fwlink/?linkid=37676) è incluso un componente Zero Touch Provisioning (ZTP), che fornisce una procedura automatica per questo processo.

Per ulteriori informazioni, vedere le seguenti guide (informazioni in lingua inglese):

-   [Zero Touch Provisioning Deployment Feature Team Guide](http://www.microsoft.com/technet/itsolutions/cits/dsd/enterprise/ztpdftguide_1.mspx) all'indirizzo www.microsoft.com/technet/itsolutions/
    cits/dsd/enterprise/ZTPDFTGuide\_1.mspx

-   [Zero Touch Provisioning Developer Guide](http://www.microsoft.com/technet/itsolutions/cits/dsd/enterprise/zertpd_1.mspx) all'indirizzo www.microsoft.com/technet/itsolutions/cits/
    dsd/enterprise/zertpd\_1.mspx

-   [Zero Touch Provisioning End-User Guide](http://www.microsoft.com/technet/itsolutions/cits/dsd/enterprise/ztpeugiude_1.mspx) all'indirizzo www.microsoft.com/technet/itsolutions/cits/
    dsd/enterprise/ZTPEUGiude\_1.mspx

[](#mainsection)[Inizio pagina](#mainsection)

### Gestione dei cambiamenti delle password degli account computer

Quando si assegna un account a un servizio, prima di effettuare l'assegnazione Gestione controllo servizi richiede la password corretta per tale account. Se viene fornita una password non corretta, l'assegnazione viene respinta.

Se si configura un account dei servizi in modo che venga utilizzato l'account di sistema locale, del servizio locale o del servizio di rete, non è necessario gestire la password dell'account dei servizi poiché verrà gestita automaticamente dal sistema operativo. Di conseguenza, per le password di questi account dei servizi non è richiesta alcuna gestione.

Per altri account dei servizi, la password corrispondente viene memorizzata nel database dei servizi. Una volta assegnata la password, Gestione controllo servizi non verifica che la password memorizzata nel database dei servizi corrisponda a quella assegnata all'account utente nel servizio directory Active Directory®. Potrebbe quindi verificarsi una situazione di questo tipo:

1.  Un servizio viene configurato in modo che venga eseguito con un determinato account utente.

2.  Il servizio viene avviato con tale account utilizzando la password corrente dell'account.

3.  La password dell'account utente viene cambiata.

4.  Il servizio continua a essere eseguito. Se viene arrestato, tuttavia, il servizio non potrà essere riavviato poiché Gestione controllo servizi continua a utilizzare la password precedente, non più valida. Questo problema si verifica perché il cambiamento della password in Active Directory non implica il cambiamento della password memorizzata nel database dei servizi.

Se si eseguono servizi con gli account utente locali e di dominio standard, è necessario aggiornare le password di questi servizi ogni volta che si cambia la password dell'account utente. Se non si è sicuri dei servizi in esecuzione con tale account o dei computer su cui sono in esecuzione servizi con tale account, questa operazione può richiedere molto tempo. È necessario documentare e garantire la protezione dei dati relativi all'utilizzo di questi tipi di account dei servizi e delle relative password. In un'organizzazione di grandi dimensioni, ciò significa che può essere necessario disporre di un documento di dati crittografati non in linea da collocare in un luogo sicuro. In un'organizzazione più piccola, invece, potrebbe risultare più appropriato collocare il documento in un cassetto dotato di serratura o in una cassaforte.

**Importante:** se si utilizzano le console Utenti e computer di Active Directory o Utenti e gruppi locali per cambiare la password di un account dei servizi per un'applicazione quale Exchange Server o SQL Server, è necessario cambiare la password anche nell'interfaccia dell'applicazione.

**Nota:** per ulteriori informazioni su come sviluppare uno strumento in grado di eseguire automaticamente l'aggiornamento delle password degli account dei servizi, vedere [Changing the Password on a Service's User Account](http://msdn.microsoft.com/library/default.asp?url=/library/%20en-us/ad/ad/changing_the_password_on_a_serviceampaposs_user_account.asp) all'indirizzo http://msdn.microsoft.com/library/default.asp?url=/library/
en-us/ad/ad/changing\_the\_password\_on
\_a\_serviceampaposs\_user\_account.asp (informazioni in lingua inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo di password complesse

È necessario richiedere agli amministratori di rete dell'organizzazione di imporre agli utenti l'utilizzo di password complesse. Si dovrebbero definire criteri password in Criteri di gruppo per avvisare gli utenti di cambiare le proprie password dopo un periodo di tempo prestabilito. Una password complessa deve essere di almeno 10 caratteri (preferibilmente 15 o più) e deve contenere una combinazione di lettere maiuscole e minuscole, numeri e simboli. In Windows 2000 Server e Windows Server 2003 è possibile utilizzare Criteri di gruppo per imporre l'utilizzo di password complesse. Per ulteriori informazioni, vedere [Accounts Passwords and Policies](http://technet.microsoft.com/it-it/library/cc783860.aspx) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/
technologies/security/bpactlck.mspx (informazioni in lingua inglese) e [Introduzione alla protezione di Windows 2003](http://technet.microsoft.com/it-it/library/cc163140.aspx) all'indirizzo http://go.microsoft.com/fwlink/?linkid=14845.

[](#mainsection)[Inizio pagina](#mainsection)

### Test automatici per la ricerca delle password amministratore vulnerabili

È necessario richiedere agli amministratori di rete dell'organizzazione di utilizzare periodicamente strumenti di test automatici allo scopo di individuare eventuali server distribuiti che utilizzano password vulnerabili per i relativi account amministratore locali. L'obiettivo del test è di cercare di indovinare la password dell'account amministratore locale predefinito presente in ogni computer basato su Windows.

Le password vulnerabili costituiscono uno dei punti di vulnerabilità più comuni in una rete, nonché uno dei modi più semplici per un intruso per ottenere l'accesso amministratore al computer e compromettere eventuali credenziali degli account dei servizi archiviate.

#### Utilizzo di Microsoft Baseline Security Analyzer

È possibile utilizzare lo strumento Microsoft Baseline Security Analyzer (MBSA) per analizzare ogni computer nella rete alla ricerca di eventuali password vulnerabili. Per ulteriori informazioni su MBSA e per scaricare lo strumento, visitare il sito Web [Microsoft Baseline Security Analyzer V1.2.1](http://www.microsoft.com/technet/security/tools/mbsahome.mspx) all'indirizzo www.microsoft.com/technet/security/tools/mbsahome.mspx (informazioni in lingua inglese).

Lo strumento MBSA consente di enumerare tutti gli account utente e di controllare le seguenti vulnerabilità a livello di password:

-   La password è vuota

-   La password coincide con il nome dell'account utente

-   La password coincide con il nome del computer

-   La password corrisponde alla parola "password"

-   La password corrisponde alla parola "admin" o "administrator"

Questo strumento consente inoltre di notificare all'utente eventuali account disattivati o attualmente bloccati.

MBSA utilizzerà ciascuna delle password nell'elenco per tentare di cambiare la password sul computer di destinazione. Se l'operazione riesce, verrà indicato l'account che utilizza tale password. Lo scopo di questo strumento non è di reimpostare o cambiare la password in modo permanente, ma semplicemente di segnalare che la password utilizzata è troppo semplice e rappresenta quindi un rischio per la protezione del sistema.

Sebbene sia in grado di individuare alcuni casi di utilizzo di password deboli comuni, in MBSA non vengono fornite funzionalità complete per il controllo e il ripristino delle password, come quelle presenti in alcuni strumenti e applicazioni di analisi non in linea di terze parti attualmente disponibili sul mercato.

**Nota:** per evitare il blocco di singoli account utente durante la routine di controllo delle password, MBSA reimposta eventuali criteri di blocco degli account rilevati sul computer. Questi controlli sulle password non vengono eseguiti sui computer configurati come controller di dominio.

##### Download

[![](images/Dd536271.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione della protezione dei servizi e degli account dei servizi](http://go.microsoft.com/fwlink/?linkid=41312)

[](#mainsection)[Inizio pagina](#mainsection)
