---
TOCTitle: Processo di gestione delle patch
Title: Processo di gestione delle patch
ms:assetid: '6ff9a7c3-6adf-4a30-94a0-a0666c4d05d3'
ms:contentKeyID: 20213219
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc700833(v=TechNet.10)'
---

Processo di gestione delle patch
================================

### Fase 4 - Distribuzione

Aggiornato: 1 giugno 2007

##### In questa pagina

[](#ejaa)[Argomenti del modulo](#ejaa)
[](#eiaa)[Obiettivi](#eiaa)
[](#ehaa)[Ambito di applicazione](#ehaa)
[](#egaa)[Utilizzo del modulo](#egaa)
[](#efaa)[Panoramica](#efaa)
[](#eeaa)[Preparazione della distribuzione](#eeaa)
[](#edaa)[Distribuzione dell'aggiornamento software ai computer di destinazione](#edaa)
[](#ecaa)[Esame successivo all'implementazione](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Fasi successive](#eaaa)

### Argomenti del modulo

Questo modulo descrive la quarta fase, la distribuzione, del processo di gestione degli aggiornamenti in quattro passaggi. L'obiettivo durante la fase di distribuzione è quello di distribuire correttamente l'aggiornamento software approvato nell'ambiente di produzione in maniera che sia conforme a tutti i requisiti di qualsiasi Service Level Agreement (SLA) di distribuzione in atto.

Lo scopo di questo modulo è descrivere i principi della fase di distribuzione del processo di gestione degli aggiornamenti e introdurre i tipi di attività che consentono di eseguire la distribuzione con Microsoft Windows Server Update Service (WSUS) e Microsoft Systems Management Server (SMS).

N**ota**: la versione di valutazione del successivo rilascio di SMS, chiamata System Center Configuration Manager 2007, è ora disponibile per il download all'indirizzo <http://technet.microsoft.com/configmgr/cc761485.aspx> (in inglese). Grazie ai notevoli investimenti in semplificazione, configurazione, distribuzione e protezione, Configuration Manager 2007 rende radicalmente più facile la distribuzione dei sistemi, l'automazione delle attività, la gestione della conformità e la gestione della protezione basata su criteri, aumentando l'agilità dell'azienda.

Dopo aver letto questo modulo si sarà in grado di pianificare le attività necessarie per:

-   Distribuire l'aggiornamento software approvato.

-   Applicare le contromisure necessarie.

Senza un processo di distribuzione, non si avranno le attività testate e sperimentate richieste per distribuire un aggiornamento software nell'ambiente di produzione o per applicare le contromisure o la procedura di attenuazione necessarie.

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Il modulo consente di:

-   Preparare la distribuzione.

-   Distribuire un aggiornamento software ai computer di destinazione.

-   Esaminare la distribuzione, dopo l'implementazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Questo modulo si applica a tutti i prodotti e a tutte le tecnologie Microsoft.

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

In questo modulo sono descritte le attività di base necessarie per effettuare una valutazione utilizzando WSUS e SMS. Informazioni più dettagliate sono fornite nelle Technical Library elencate di seguito.

Per trarre il massimo vantaggio dal modulo:

-   Leggere l'introduzione del modulo sul processo di gestione degli aggiornamenti. Si avrà così una panoramica di tutte e quattro le fasi del processo di gestione degli aggiornamenti e un'introduzione agli strumenti disponibili per supportare la gestione degli aggiornamenti negli ambienti con il sistema operativo Microsoft Windows.

-   Utilizzare le Technical Library WSUS e SMS per altri materiali di riferimento specifici. Queste librerie si trovano all'indirizzo:

    -   [Windows Server Update Services (WSUS) Technical Library (in inglese)](http://technet.microsoft.com/en-us/library/cc706995.aspx)

    -   [Technical Library for Systems Management Server 2003 (in inglese)](http://technet.microsoft.com/en-us/library/cc181833.aspx)

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica

La distribuzione è la quarta fase del processo di gestione degli aggiornamenti illustrato nella Figura 1.

![alt text](images/Cc700833.gr35(it-it,TechNet.10).gif "Figura 1. Il processo di gestione degli aggiornamenti")

**Figura 1. Il processo di gestione degli aggiornamenti**

La fase di distribuzione è dedicata alle attività richieste per distribuire un aggiornamento software nell'ambiente di produzione. Potrebbero essere necessarie attività supplementari per applicare eventuali contromisure o procedure di attenuazione.

La prima azione di questa fase consiste nel determinare se l'aggiornamento software è pronto per essere distribuito nella produzione e se si è in possesso dell'approvazione necessaria per farlo.

L'obiettivo della fase di distribuzione è quello di distribuire correttamente l'aggiornamento software approvato e/o le contromisure nell'ambiente di produzione.

La distribuzione di un aggiornamento software è articolata nelle seguenti attività:

-   Preparazione della distribuzione.

-   Distribuzione dell'aggiornamento software ai computer di destinazione.

-   Esame successivo all'implementazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Preparazione della distribuzione

L'ambiente di produzione deve essere preparato per ogni nuovo rilascio. Qui di seguito sono elencati i passaggi richiesti per preparare la distribuzione dell'aggiornamento software:

-   Comunicazione della pianificazione della distribuzione all'organizzazione.

-   Se WSUS è distribuito:

    -   Distribuzione graduale degli aggiornamenti sui server SUS.

-   Se SMS è distribuito:

    -   Importazione dei programmi e degli annunci dall'ambiente di testing.

    -   Assegnazione dei punti di distribuzione.

    -   Distribuzione graduale degli aggiornamenti sui punti di distribuzione.

    -   Selezione dei gruppi di distribuzione.

Per ulteriori informazioni sulla preparazione alla distribuzione in WSUS e SMS, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) o [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese).

#### Comunicazione della pianificazione della distribuzione all'organizzazione

È importante informare gli utenti finali e gli amministratori sull'imminente rilascio di un aggiornamento. È opportuno inviare un messaggio di posta elettronica chiaro e facilmente identificabile agli utenti e agli amministratori con cui li si informa dell'aggiornamento e si danno loro indicazioni su come installarlo. È opportuno contrassegnare il messaggio per il completamento per ricordare agli utenti e agli amministratori le azioni che devono intraprendere.

Se si sta per procedere alla distribuzione di un aggiornamento su desktop al di fuori delle ore di attività principali dell'azienda, è opportuno comunicare agli utenti di non spegnere i computer nel giorno specificato. Se il messaggio è contrassegnato per il completamento come indicato nella Figura 2, gli utenti riceveranno un promemoria alle ore 16:30 del 30 maggio in cui si ricorda loro di lasciare i computer accesi durante la notte.

[![alt text](images/Cc700833.gr36(it-it,TechNet.10).gif "Figura 2. In questa figura viene illustrato come un messaggio di posta elettronica contrassegnato per il completamento può essere utilizzato come promemoria")](https://technet.microsoft.com/it-it/cc700833.gr36_big(it-it,technet.10).gif)

**Figura 2. In questa figura viene illustrato come un messaggio di posta elettronica contrassegnato per il completamento può essere utilizzato come promemoria**

Se si utilizza WSUS, il processo delle comunicazioni include altre considerazioni, che dipendono dalle impostazioni del criterio di installazione e di download per il client WSUS:

-   **Notifica del download e notifica dell'installazione.** Un utente che ha effettuato l'accesso con diritti di amministratore locale dovrà selezionare l'opzione per scaricare l'aggiornamento ogni volta che sulla barra delle attività appare la notifica **Nuovo aggiornamento disponibile per il download**. Per completare l'installazione, dovrà poi installare l'aggiornamento software quando appare la notifica **Nuovo aggiornamento disponibile per l'installazione**.

-   **Download automatico e notifica dell'installazione.** Gli aggiornamenti appena approvati che si applicano al computer client vengono scaricati automaticamente dal client Aggiornamenti automatici. Per installare gli aggiornamenti, un utente che abbia effettuato l'accesso con diritti di amministratore locale dovrà selezionare l'opzione per installare l'aggiornamento software quando appare la notifica **Nuovo aggiornamento disponibile per l'installazione**.

-   **Download automatico e pianificazione dell'installazione.** Un utente che si sia collegato con diritti di amministratore locale può installare un aggiornamento prima dell'orario di installazione pianificato, oppure ritardare il riavvio (se richiesto) al termine dell'installazione. Se gli utenti non possiedono diritti di amministratore locale, l'aggiornamento verrà installato in background all'ora pianificata. Questi utenti possono solo ritardare il riavvio di un computer, se è stata attivata l'impostazione del criterio **Escludi riavvio automatico per installazioni pianificate di Aggiornamenti automatici**.

Per informazioni dettagliate sull'utilizzo di WSUS nella fase di distribuzione, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese).

#### Preparazione della distribuzione utilizzando SMS

Se si utilizza SMS 2003, la preparazione della distribuzione richiede che vengano presi in considerazione diversi passaggi aggiuntivi:

-   Importazione dei programmi e degli annunci dall'ambiente di testing. Prima di tutto, è necessario importare nell'ambiente di produzione SMS 2003 i pacchetti generati e testati nell'ambiente di testing.

-   **Assegnazione dei punti di distribuzione.** Quindi, è necessario assegnare i punti di distribuzione; i file binari dell'aggiornamento software devono essere inseriti nei punti di distribuzione in tutti i siti in cui si trovano i client di destinazione. Se è possibile utilizzare **Distribute Software Updates Wizard**, i punti di distribuzione possono essere assegnati tramite la procedura guidata e modificati manualmente dopo la creazione del pacchetto.

-   **Distribuzione graduale degli aggiornamenti sui punti di distribuzione**. Il passaggio successivo consiste nel controllare che i server dei punti di distribuzione contengano le copie di tutti i file. L'invio dei file binari dell'aggiornamento software ai punti di distribuzione implica l'invio dei file tra i siti SMS e da questi ai punti di distribuzione locali.

-   **Selezione dei gruppi di distribuzione.** Se si utilizza **Distribute Software Updates Wizard** per distribuire un nuovo aggiornamento software, non è necessario scegliere con precisione i computer di destinazione. La procedura guidata distribuisce infatti un agente intelligente che viene richiamato quando si rende necessario installare un nuovo aggiornamento. L'agente stabilisce automaticamente se un aggiornamento è applicabile a quel determinato computer e se è già stato installato. Se gli aggiornamenti vengono distribuiti tramite un pacchetto personalizzato e una raccolta, potrebbe essere necessario creare una o più query SMS per la distribuzione ai computer appropriati.

Per ulteriori informazioni sull'uso di SMS nella fase di distribuzione, vedere [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Distribuzione dell'aggiornamento software ai computer di destinazione

Il processo scelto per distribuire l'aggiornamento software nell'ambiente di produzione dipende dal tipo e dalla natura del rilascio e dal meccanismo di rilascio prescelto.

Inoltre dipende moltissimo dal livello di urgenza. Dato che l'urgenza associata a un'emergenza cambia, vi saranno alcune differenze nella modalità di distribuzione. Queste differenze verranno illustrate dettagliatamente in tutta questa sezione.

Idealmente, gli aggiornamenti software dovrebbero essere rilasciati gradualmente, per ridurre l'impatto di eventuali problemi o effetti indesiderati che potrebbero derivare dalla distribuzione iniziale.

Qui di seguito sono riportati i passaggi richiesti per distribuire un aggiornamento software nella produzione:

-   Annuncio dell'aggiornamento software ai computer client.

-   Monitoraggio e report sull'andamento della distribuzione.

-   Gestione delle distribuzioni non riuscite.

#### Annuncio dell'aggiornamento software ai computer client

Se si utilizza WSUS e non è richiesta una distribuzione graduale, è sufficiente approvare l'aggiornamento sul server padre WSUS per renderlo disponibile per i client. I client WSUS inizieranno a scaricare l'aggiornamento appena approvato al ciclo di rilevamento successivo o quando richiesto dall'amministratore locale, se il client Aggiornamenti automatici è configurato per notificare all'amministratore locale quando i nuovi aggiornamenti sono disponibili.

In caso di distribuzione graduale, tuttavia, è prima necessario approvare l'aggiornamento solo sul server padre WSUS. Successivamente, una volta che l'aggiornamento è stato distribuito correttamente ai client supportati da quel server, è necessario attivare la sincronizzazione dell'elenco delle approvazioni sul server figlio WSUS che supporta i client nella fase successiva della distribuzione.

Per informazioni dettagliate sull'utilizzo di WSUS nella fase di distribuzione, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese).

Se si utilizza SMS e **Distribute Software Updates Wizard**, viene creato automaticamente un annuncio ripetitivo che esegue l'agente di installazione dell'aggiornamento software nei computer del gruppo di destinazione. Se necessario, è possibile impostare l'intervallo di ripetizione su un valore diverso da quello predefinito di sette giorni. Un gruppo che include, ad esempio, diversi server può eseguire l'agente una volta al giorno. Utilizzando lo stesso pacchetto e lo stesso programma è possibile creare annunci per più gruppi, se sono richieste pianificazioni diverse in base al tipo di computer. Se la distribuzione è graduale, si dovrà modificare la query dopo ogni fase, in maniera da includere i client nella fase successiva.

Se non si utilizza **Distribute Software Updates Wizard**, quando un annuncio è impostato per installare un aggiornamento, la sua pianificazione deve essere configurata in modo che venga ripetuto a intervalli. In questo caso, un'installazione non riuscita viene ritentata automaticamente. L'intervallo di ripetizione dell'annuncio deve essere scelto con attenzione, perché i client che hanno già installato correttamente l'aggiornamento rimarranno nel gruppo di destinazione fino alla raccolta di un nuovo inventario, che può essere attivata dal programma di installazione, o finché l'inventario non è stato aggiornato nel database SMS e la raccolta non è stata sottoposta a una nuova valutazione. Pertanto, il programma potrebbe essere eseguito di nuovo in un client in cui è già stato eseguito correttamente una volta. Per questo motivo, è fondamentale che all'esecuzione il programma controlli prima di tutto se gli aggiornamenti software sono installati e, in caso affermativo, che venga chiuso subito.

Per ulteriori informazioni sull'uso di SMS nella fase di distribuzione, vedere [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese).

**Richiesta di modifica di emergenza**

Per informazioni su come gestire richieste di modifica di emergenza utilizzando WSUS, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) e per sapere come gestire le richieste di modifica di emergenza utilizzando SMS, vedere [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese).

Monitoraggio e report sull'andamento della distribuzione

L'installazione nei computer di un aggiornamento può non riuscire per diverse ragioni, tra cui:

-   Il computer non è in linea.

-   Il computer è in fase di rigenerazione o ricostruzione dell'immagine.

-   Lo spazio su disco del computer è insufficiente.

-   Negli ambienti WSUS:

    -   Il computer non comunica con il server WSUS (in caso di computer con il client Aggiornamenti automatici).

    -   Il servizio del client Aggiornamenti automatici è stato interrotto.

-   Negli ambienti SMS:

    -   I client SMS del computer non comunicano con i server del sito SMS.

    -   Il servizio agente del computer è stato interrotto da un utente o per manutenzione.

-   Negli ambienti SMS 2003:

    -   Il computer ha MSXML 3 fino a SP1 (SMS 2003 richiede MSXML 3.0 SP4).

Per informazioni dettagliate sull'utilizzo di WSUS nella fase di distribuzione, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese).

Per monitorare il rilascio corretto di un aggiornamento in SMS, è possibile utilizzare **Advertisement Status Viewer** per visualizzare lo stato di distribuzione degli annunci, sulla base dei messaggi sullo stato. I messaggi sullo stato riportano solo se l'annuncio ripetitivo è stato eseguito, non se l'aggiornamento è stato installato. Per ottenere queste informazioni, è necessario analizzare i messaggi sullo stato per stabilire quando è stato eseguito correttamente per l'ultima volta il programma di **installazione patch** su ciascun client; se l'intervallo di tempo dall'ultima esecuzione è superiore al periodo di ripetizione per uno dei client, è opportuno effettuare delle indagini.

Nel caso degli aggiornamenti software identificati tramite Security Updates Inventory Tool, Inventory Tool for Microsoft Updates o Microsoft Office Inventory Tool for Updates, è possibile utilizzare i report incorporati per controllare la correttezza della distribuzione. Il report Compliance by Software ID può essere utilizzato per fornire un riepilogo sul numero totale di sistemi in cui l'aggiornamento risulta installato o mancante, nonché sullo stato relativo alla distribuzione dell'aggiornamento software.

Per ulteriori informazioni sull'uso di SMS nella fase di distribuzione, vedere [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese).

#### Gestione delle distribuzioni non riuscite

Se, durante una normale distribuzione, vengono rilevate delle eccezioni, si dovrebbe disporre di tempo sufficiente per interrompere il processo, individuare la causa e rieffettuare la distribuzione. Tuttavia, durante una distribuzione di emergenza, il tempo disponibile per l'individuazione e la valutazione della causa sarà molto inferiore.

L'organizzazione potrebbe anche decidere che una distribuzione non è riuscita e deve essere interrotta e ripristinata. È pertanto opportuno disporre di un piano per interrompere la distribuzione, disinstallare gli aggiornamenti non riusciti e poi ridistribuirli.

##### Negli ambienti WSUS

In caso di distribuzioni non riuscite in un ambiente WSUS, è necessario annullare l'approvazione dell'aggiornamento sul server WSUS, per impedire ulteriori installazioni. Sui client in cui l'aggiornamento è già stato scaricato ma non ancora installato, gli amministratori locali possono manualmente rimuoverlo dall'elenco degli aggiornamenti da installare. Se in un computer è stato installato un aggiornamento approvato, l'aggiornamento può essere rimosso solo tramite l'**opzione Installazione applicazioni** nel Pannello di controllo (presumendo che l'aggiornamento possa essere disinstallato). Per informazioni dettagliate sull'utilizzo di WSUS nella fase di distribuzione, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese).

##### Negli ambienti SMS

Se si utilizza SMS, la gestione delle distribuzioni non riuscite comporta quattro attività principali:

-   Interruzione della distribuzione del pacchetto attivo, fino alla risoluzione del problema.

-   Identificazione e risoluzione del problema, ovvero risoluzione dell'errore nella distribuzione.

-   Ripubblicazione del pacchetto.

-   Disinstallazione dell'aggiornamento software, tramite la creazione di un pacchetto di disinstallazione, se l'aggiornamento può essere disinstallato.

Per ulteriori informazioni sull'uso di SMS nella fase di distribuzione, vedere [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Esame successivo all'implementazione

L'esame successivo all'implementazione in genere deve essere effettuato entro una-quattro settimane dal rilascio della distribuzione per identificare i miglioramenti da apportare al processo di gestione degli aggiornamenti.

Un tipico programma di riesame include le seguenti azioni:

-   Controllare che le vulnerabilità siano state aggiunte ai report sull'analisi delle vulnerabilità e agli standard dei criteri di protezione, per evitare il ripetersi dell'attacco.

-   Controllare che le immagini del sistema siano state aggiornate per includere gli ultimi aggiornamenti software successivi alla distribuzione.

-   Esaminare i risultati pianificati a fronte di quelli reali.

-   Esaminare i rischi associati al rilascio.

-   Esaminare le prestazioni dell'organizzazione durante l'intero incidente. Cogliere questa opportunità per migliorare il piano di risposta per includere tutti gli insegnamenti tratti.

-   Esaminare le modifiche agli intervalli di assistenza.

-   Valutare il danno e i costi complessivi provocati dall'incidente, compresi i costi dei tempi di inattività e di ripristino.

-   Creare un'altra configurazione di base o aggiornare quella esistente per l'ambiente.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

Durante la fase di distribuzione, è necessario:

-   Aver stabilito l'ordine in cui gli aggiornamenti software verranno distribuiti nella produzione.

-   Aver controllato l'ambiente di produzione per essere certi che sia in grado di gestire l'aggiornamento software.

-   Aver posizionato i file dell'aggiornamento software nei punti di distribuzione SMS e nei server WSUS.

-   Aver distribuito l'aggiornamento software nella produzione.

-   Aver rieffettuato l'analisi dell'ambiente per valutare la riuscita della distribuzione e aver aggiornato i computer in cui l'installazione dell'aggiornamento software non è riuscita.

-   Aver effettuato un esame del processo di gestione degli aggiornamenti al termine della distribuzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Fasi successive

Dopo aver distribuito l'aggiornamento software, ritornare alla fase di valutazione in cui è possibile continuare a:

-   Fare l'inventario/individuare le risorse informatiche presenti.

-   Valutare i pericoli per la protezione e le vulnerabilità.

-   Stabilire la fonte migliore di informazioni sugli aggiornamenti software.

-   Valutare l'infrastruttura di distribuzione esistente del software.

-   Valutare l'efficienza operativa.

[](#mainsection)[Inizio pagina](#mainsection)
