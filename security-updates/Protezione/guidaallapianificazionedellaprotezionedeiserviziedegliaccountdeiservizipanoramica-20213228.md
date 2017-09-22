---
TOCTitle: 'Guida alla pianificazione della protezione dei servizi e degli account dei servizi - Panoramica'
Title: 'Guida alla pianificazione della protezione dei servizi e degli account dei servizi - Panoramica'
ms:assetid: '551a769e-d7c1-41c2-8c2e-301350aedfbb'
ms:contentKeyID: 20213228
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc170953(v=TechNet.10)'
---

Guida alla pianificazione della protezione dei servizi e degli account dei servizi
==================================================================================

### Panoramica

Aggiornato : maggio 31, 2005

Questa guida è una risorsa importante per la pianificazione di strategie per l'esecuzione protetta dei servizi nei sistemi operativi Microsoft® Windows Server™ 2003 e Windows® XP. Nella guida viene affrontato il problema comune che riguarda i servizi di Windows impostati per l'esecuzione con il livello di privilegio più alto possibile. Questi servizi, infatti, potrebbero essere compromessi da un utente malintenzionato che otterrebbe quindi l'accesso completo e senza limitazioni al computer, al dominio o persino all'intero insieme di strutture. Viene descritto come individuare i servizi che possono essere eseguiti con livelli di privilegio inferiori e viene spiegato come abbassare di livello questi privilegi in modo sistematico. Questa guida consente di ottenere una valutazione dell'infrastruttura corrente dei servizi e di prendere alcune decisioni importanti per la pianificazione delle future distribuzioni dei servizi.

I servizi inclusi in Windows Server 2003 e Windows XP sono già stati testati per l'esecuzione con i relativi account di accesso predefiniti, per garantire che vengano eseguiti con il livello di privilegio minimo e che siano sufficientemente protetti. Questi servizi non richiedono alcuna modifica. Le informazioni riportate in questa guida riguardano essenzialmente la protezione dei servizi che non sono inclusi nel sistema operativo ma vengono forniti come componenti di altri prodotti server Microsoft, ad esempio Microsoft SQL Server™ o Microsoft Operations Manager (MOM). È possibile che i servizi installati con applicazioni software di terze parti e applicazioni line-of-business sviluppate internamente possano richiedere alcune modifiche aggiuntive a livello di protezione.

Lo scopo principale di questa guida è di consentire agli amministratori di ridurre gli effetti di un servizio compromesso in un sistema operativo host. Queste istruzioni si fondano sull'esperienza maturata dal Microsoft Security Center of Excellence (SCoE) negli ambienti dei clienti e rappresentano procedure consigliate da Microsoft.

##### In questa pagina

[](#eeaa)[Panoramica](#eeaa)
[](#edaa)[Vantaggi dell'esecuzione protetta dei servizi](#edaa)
[](#ecaa)[Destinatari della guida](#ecaa)
[](#ebaa)[Panoramica della Guida alla pianificazione](#ebaa)
[](#eaaa)[Commenti e suggerimenti](#eaaa)

### Panoramica

L'esecuzione protetta dei servizi è un requisito fondamentale per le organizzazioni. Mediante la creazione di criteri e procedure consigliate è possibile impedire che venga sfruttata un'eventuale protezione insufficiente dei servizi. In caso di vulnerabilità della protezione è possibile accedere ai nomi utente e alle password utilizzate da un servizio per l'autenticazione quando questo viene avviato o si connette ad altri computer nel dominio. Nello scenario peggiore, un utente non autorizzato può ottenere l'accesso come amministratore a livello di dominio.

I servizi di Windows sono programmi che vengono eseguiti all'esterno della sessione dell'utente attualmente connesso. Questi servizi vengono eseguiti in background, in modo indipendente da una qualsiasi sessione utente. I servizi possono essere configurati per l'avvio automatico insieme al computer, possono essere sospesi e riavviati e, anche se in genere comunicano con un'interfaccia utente per il controllo e la gestione del servizio, non prevedono la visualizzazione di un'interfaccia utente. Per questo motivo, i servizi sono ideali per essere utilizzati in un server o quando sono necessarie funzionalità permanenti che non interferiscano con gli altri utenti che stanno lavorando sullo stesso computer. Oltre ai servizi creati da Microsoft, esistono molti prodotti di terze parti appositamente progettati per la distribuzione come servizi da eseguire continuamente in background.

La vulnerabilità dei servizi a livello di protezione deriva dal modo in cui i servizi vengono in genere distribuiti all'interno delle organizzazioni. Come avviene per gli utenti, i servizi richiedono un metodo di autenticazione per l'utilizzo delle risorse del computer o della rete. Prima del rilascio di Windows 2000, i servizi che accedevano alle risorse di rete dovevano utilizzare un account utente di dominio per eseguire l'autenticazione a ciascun server remoto utilizzato, poiché l'account di sistema locale non poteva essere utilizzato per l'autenticazione nell'ambito della rete. Con il rilascio di Windows 2000, l'account di sistema locale è stato modificato per consentire l'autenticazione alle risorse di rete, proprio come gli account utente di dominio. In questo caso, tuttavia, per l'autenticazione vengono utilizzate le credenziali del computer. Tenere presente che un account computer è essenzialmente un account utente senza l'attributo UserAccountControl. Di conseguenza, gli account computer possono accedere alle risorse proprio come un normale account utente. A seguito di queste modifiche, l'account di sistema locale è diventato uno degli account più utilizzati per la distribuzione dei servizi. Con il rilascio di Windows Server 2003 la situazione è nuovamente cambiata, poiché sono stati aggiunti due nuovi tipi di account predefiniti simili all'account di sistema locale, ovvero account del servizio di rete e account del servizio locale.

Sebbene utilizzi anch'esso le credenziali del computer per l'autenticazione in remoto, il nuovo account del servizio di rete ha un livello di privilegio molto più basso sul server e non dispone quindi dei privilegi di amministratore locale. Il nuovo account del servizio locale dispone degli stessi privilegi limitati dell'account del servizio di rete ma, come indica il nome, non ha la capacità di eseguire l'autenticazione alle risorse di rete.

L'esecuzione protetta dei servizi è un aspetto importante per le organizzazioni che cercano di aumentare la protezione delle risorse di rete interne.

[](#mainsection)[Inizio pagina](#mainsection)

### Vantaggi dell'esecuzione protetta dei servizi

L'esecuzione protetta dei servizi assicura vantaggi significativi alle organizzazioni. Migliorando la protezione dei servizi, è possibile ridurre rapidamente la dimensione della superficie di attacco dei computer, migliorare la protezione globale dell'organizzazione, aumentare la protezione delle informazioni critiche e riservate, nonché aumentare la stabilità dei computer e il tempo di attività dei sistemi. È possibile inoltre diminuire i costi amministrativi, riducendo quindi il costo di proprietà dei server presenti all'interno dell'organizzazione.

Questa guida consente di fornire una valutazione dell'infrastruttura corrente dei servizi e di prendere alcune decisioni importanti per la pianificazione delle future distribuzioni dei servizi.

[](#mainsection)[Inizio pagina](#mainsection)

### Destinatari della guida

Questa guida è rivolta principalmente ai consulenti, agli specialisti della protezione, agli architetti di sistemi e ai professionisti IT responsabili delle fasi di pianificazione dello sviluppo di applicazioni o infrastrutture e della distribuzione di Windows Server 2003. Di seguito sono elencate le descrizioni di alcune mansioni comuni per questi ruoli:

-   Architetti e addetti alla pianificazione responsabili dell'implementazione dei sistemi client all'interno dell'organizzazione.

-   Specialisti della protezione IT che si occupano della protezione tra le varie piattaforme utilizzate nell'organizzazione.

-   Architetti aziendali che hanno il compito di gestire l'intera rete aziendale anziché una specifica rete.

-   Responsabili IT che hanno il compito di scegliere la tecnologia da utilizzare per la risoluzione di determinati problemi aziendali.

-   Analisti e responsabili dei processi decisionali che devono soddisfare obiettivi e requisiti aziendali critici che dipendono dal supporto client.

-   Consulenti di servizi Microsoft e partner che devono disporre di informazioni dettagliate relative ai clienti e ai partner dell'organizzazione.

Sebbene sia stata scritta essenzialmente per questi ruoli, la *Guida alla pianificazione della protezione dei servizi e degli account dei servizi* può essere utile anche agli altri addetti IT delle organizzazioni di medie e grandi dimensioni, nonché ai ruoli team Infrastruttura, Operazioni e Protezione indicati nel modello di team Microsoft Operations Framework (MOF).

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica della Guida alla pianificazione

La guida è composta dai seguenti capitoli:

**Capitolo 1: Introduzione**

In questo capitolo vengono fornite alcune informazioni di carattere generale, vengono illustrati i problemi e i vantaggi per le aziende, viene indicato il tipo di utenti a cui si rivolge la guida e viene fornita una panoramica dei capitoli contenuti nella guida.

**Capitolo 2: Strategie per l'esecuzione protetta dei servizi**

In questo capitolo viene fornita una panoramica dei tipi di account utilizzati per l'accesso ai servizi e vengono descritti i principi e le strategie da applicare per consentire l'esecuzione protetta dei servizi.

**Capitolo 3: Esecuzione protetta dei servizi**

In questo capitolo viene illustrato come aumentare la protezione nell'esecuzione dei servizi sfruttando i principi e le strategie discussi nel capitolo precedente. Viene inoltre descritta la nuova Configurazione guidata impostazioni di sicurezza disponibile in Windows Server 2003 con Service Pack 1, una risorsa indispensabile per pianificare l'esecuzione dei servizi in un ambiente protetto.

**Capitolo 4: Riepilogo**

In questo capitolo viene fornito un riepilogo sugli aspetti e sui problemi principali affrontati in questa guida. Sono inoltre riportati i collegamenti ad alcune risorse in cui sono disponibili informazioni aggiuntive sull'argomento.

[](#mainsection)[Inizio pagina](#mainsection)

### Commenti e suggerimenti

Microsoft è lieta di ricevere commenti e suggerimenti dei lettori su questo materiale. Sono particolarmente gradite le osservazioni sui seguenti argomenti:

-   Livello di utilità delle informazioni fornite

-   Accuratezza delle procedure

-   Livello di chiarezza e interesse dei capitoli

-   Valutazione complessiva della soluzione

Inviare i commenti e i suggerimenti al seguente indirizzo di posta elettronica: [cisfdbk@microsoft.com](mailto:cisfdbk@microsoft.com?subject=the%20services%20and%20service%20accounts%20security%20planning%20guide)

##### Download

[![](images/Cc170953.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione della protezione dei servizi e degli account dei servizi](http://go.microsoft.com/fwlink/?linkid=41312)

[](#mainsection)[Inizio pagina](#mainsection)
