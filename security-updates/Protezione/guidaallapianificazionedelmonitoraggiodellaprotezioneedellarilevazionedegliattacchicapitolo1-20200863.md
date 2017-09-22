---
TOCTitle: 'Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi - Capitolo 1'
Title: 'Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi - Capitolo 1'
ms:assetid: '78f07bdb-b0d2-4ee5-8890-56d1db3dbd06'
ms:contentKeyID: 20200863
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536264(v=TechNet.10)'
---

Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi
==============================================================================================

### Capitolo 1 - Introduzione

Aggiornato: 23 maggio 2005

##### In questa pagina

[](#ebaa)[Riepilogo generale](#ebaa)
[](#eaaa)[Panoramica della Guida alla pianificazione](#eaaa)

### Riepilogo generale

Con l'aumento delle notizie riportate dai media sulla diffusione di programmi software dannosi tramite Internet, le minacce esterne hanno assunto un'importanza sempre maggiore nelle strategie di protezione delle risorse di rete delle organizzazioni. Tuttavia, alcune delle minacce più pericolose per l'infrastruttura di un'organizzazione sono costituite dagli attacchi provenienti dalla rete interna. Gli attacchi interni che potrebbero causare potenzialmente i danni maggiori sono quelli risultanti dalle attività di persone a cui sono assegnati i privilegi più alti, ad esempio gli amministratori di rete. Grazie all'analisi delle minacce interne ed esterne, molte organizzazioni possono ora analizzare i sistemi per il monitoraggio delle reti e la rilevazione degli attacchi.

Per le organizzazioni che hanno l'obbligo di rispettare determinati vincoli normativi, il monitoraggio della protezione è un requisito essenziale. Con l'aumentare dei requisiti normativi richiesti da numerose istituzioni a livello mondiale, le organizzazioni hanno la necessità di implementare un sistema in grado di monitorare le reti interne, controllare le richieste di accesso alle risorse nonché individuare gli utenti che si connettono e si disconnettono dalla rete. In alcuni casi, è anche possibile che le aziende siano obbligate a mantenere in archivio i dati relativi alla protezione per un determinato periodo di tempo.

I registri di protezione disponibili in Microsoft® Windows® forniscono la base iniziale per una qualsiasi applicazione di monitoraggio della protezione, ma non forniscono informazioni sufficienti per pianificare una risposta adeguata a un determinato problema. Utilizzati in combinazione con altre tecnologie per la raccolta e l'analisi dei registri di protezione, questi ultimi costituiscono un elemento fondamentale di un sistema di monitoraggio della protezione e di rilevazione degli attacchi.

In questa guida viene illustrato come pianificare un sistema di monitoraggio della protezione in una rete basata su Windows. Questo sistema consente di rilevare eventuali attacchi provenienti da origini sia interne che esterne. La funzione principale di un sistema di monitoraggio della protezione è di individuare eventi insoliti nella rete che potrebbero indicare attività dannose o errori procedurali.

#### La sfida per le aziende

Per poter implementare un sistema di monitoraggio della protezione efficace in una rete di grandi dimensioni, le aziende devono affrontare e risolvere alcuni aspetti importanti, ad esempio:

-   Individuazione della necessità di protezione delle informazioni.

-   Definizione dei livelli di autorizzazione per gli amministratori e gli utenti.

-   Implementazione di un criterio di monitoraggio completo.

-   Definizione di una correlazione tra questo criterio e gli eventi di protezione rilevati.

Queste problematiche sono valide anche per le organizzazioni in cui sono previsti requisiti di rete meno complessi.

#### Vantaggi per le aziende

Il monitoraggio della protezione fornisce alle organizzazioni, indipendentemente dalla dimensione, due vantaggi principali, ovvero la possibilità di individuare immediatamente gli attacchi e di eseguire un'analisi legale sugli eventi che si sono verificati prima, durante e dopo un attacco.

Grazie alla possibilità di rilevare gli attacchi nel momento esatto in cui si verificano, il personale addetto alla protezione può reagire rapidamente in modo da ridurre al minimo i danni apportati all'infrastruttura di rete. Inoltre, sfruttando i dati ottenuti dall'analisi legale, sarà possibile determinare l'entità dell'attacco. Di seguito sono riportati gli altri vantaggi offerti dal monitoraggio della protezione:

-   Riduzione degli effetti degli attacchi.

-   Individuazione rapida da parte del personale di protezione di schemi di comportamento insoliti.

-   Creazione di informazioni di controllo per soddisfare i requisiti normativi.

Per ulteriori informazioni su questi vantaggi, vedere il Capitolo 2 "Strategie di monitoraggio della protezione".

#### Destinatari della guida

In questa guida vengono fornite informazioni utili per le organizzazioni con requisiti di protezione elevati, in particolare quelle che hanno l'obbligo di rispettare specifiche normative. Tali informazioni sono valide per qualsiasi organizzazione, indipendentemente dalla dimensione, che richiede un sistema efficace per la protezione delle identità e il controllo dell'accesso ai dati.

Questa guida è rivolta principalmente ai responsabili e agli specialisti del settore IT, ad esempio gli architetti dell'infrastruttura e i responsabili della protezione all'interno dell'azienda, ma può essere utile anche ai responsabili delle decisioni tecniche e ai consulenti che devono pianificare, distribuire o gestire reti basate su Windows.

#### Prerequisiti per i lettori

Per poter comprendere le soluzioni presentate in questa guida, è necessario avere una certa dimestichezza con le problematiche legate alla protezione nonché conoscere il profilo di rischio della propria rete e il servizio di registrazione degli eventi di Windows.

In questa guida vengono utilizzate le fasi operativa e di supporto del modello di processo MOF (Microsoft Operations Framework) nonché le funzioni di gestione dei servizi (SMF, Service Management Function) Amministrazione della protezione e Gestione delle emergenze MOF. Per ulteriori informazioni su MOF, visitare il sito Web [Microsoft Operations Framework](http://www.microsoft.com/mof) all'indirizzo www.microsoft.com/mof (informazioni in lingua inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica della Guida alla pianificazione

In questa guida vengono illustrati in dettaglio le problematiche e i concetti principali per la pianificazione di una soluzione di monitoraggio della protezione e di rilevazione degli attacchi. La guida è composta dai seguenti quattro capitoli:

**Capitolo 1: Introduzione**

In questo capitolo vengono fornite alcune informazioni di carattere generale, vengono illustrati i problemi e i vantaggi per le aziende, viene indicato il tipo di utenti a cui si rivolge la guida, vengono elencati i prerequisiti per i lettori e viene fornita una panoramica dei capitoli e degli scenari di soluzione contenuti nella guida.

**Capitolo 2: Strategie di monitoraggio della protezione**

In questo capitolo viene fornita una panoramica delle diverse opzioni disponibili per l'implementazione di una soluzione di monitoraggio della protezione e di rilevazione degli attacchi basata su tecnologie Microsoft e di terze parti.

**Capitolo 3: Problemi e requisiti**

In questo capitolo viene illustrato come mettere in relazione la funzione del monitoraggio della protezione con gli altri requisiti aziendali e con le minacce e gli attacchi che possono potenzialmente compromettere una rete aziendale. Vengono illustrate le problematiche a livello aziendale, tecnico e di protezione dei seguenti tre scenari:

-   Rilevazione delle violazioni dei criteri

-   Individuazione degli attacchi esterni

-   Implementazione dell'analisi legale

Una violazione dei criteri è definita come una qualsiasi deviazione dai criteri dell'organizzazione. Verranno infine elencati i requisiti della soluzione per un sistema di monitoraggio della protezione e di rilevazione degli attacchi.

**Capitolo 4: Progettazione della soluzione**

In questo capitolo vengono fornite informazioni dettagliate su come utilizzare il monitoraggio della protezione per la rilevazione degli attacchi e l'implementazione di archivi dei controlli di protezione. Vengono illustrate le impostazioni di configurazione consigliate per un sistema di monitoraggio della protezione efficace nonché le modifiche che le organizzazioni devono apportare ai criteri di protezione.

In questo capitolo vengono inoltre fornite istruzioni dettagliate su come implementare un sistema di monitoraggio della protezione nelle organizzazioni di grandi dimensioni. Viene inoltre indicato come risolvere i problemi di archiviazione per volumi elevati di eventi di protezione e come pianificare una strategia di rilevazione degli attacchi nelle reti distribuite.

##### Download

[![](images/Dd536264.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://go.microsoft.com/fwlink/?linkid=41310)

[](#mainsection)[Inizio pagina](#mainsection)
