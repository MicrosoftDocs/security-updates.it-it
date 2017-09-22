---
TOCTitle: 'Guida operativa - Introduzione alla Guida operativa'
Title: 'Guida operativa - Introduzione alla Guida operativa'
ms:assetid: '62813113-630f-4157-91a6-55ff91db206f'
ms:contentKeyID: 20200811
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536211(v=TechNet.10)'
---

Capitolo 10: Introduzione alla Guida operativa
==============================================

Pubblicato: 11 ottobre 2004 | Aggiornato: 24/11/2004

##### In questa pagina

[](#edaa)[Utilizzo della guida](#edaa)
[](#ecaa)[Introduzione al modello Microsoft Operations Framework](#ecaa)
[](#ebaa)[Convenzioni di struttura per le attività](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Utilizzo della guida

A differenza dei capitoli precedenti, la Guida operativa non necessita di essere letta per intero. Infatti, è stata strutturata in modo leggermente diverso. Mentre in genere i capitoli della Guida alla creazione vengono utilizzati una sola volta durante il processo di distribuzione, quelli della Guida operativa vengono consultati regolarmente durante l'intero ciclo di vita della soluzione. È essenziale comprendere come è strutturata la Guida operativa in modo da trarre il massimo dalle informazioni contenute in essa.

I capitoli di questa guida si basano sul modello Solutions Operations Guide (SOG) ideato dal team Microsoft Solutions for Management (MSM). Ogni guida SOG utilizza la struttura MOF (Microsoft Operations Framework) per analizzare e classificare tutte le attività necessarie per gestire, supportare e migliorare il funzionamento della soluzione nel corso del suo ciclo di vita. La prossima sezione comprende una breve introduzione alla struttura MOF, ma per comprenderla a fondo è preferibile consultare anche i riferimenti riportati alla fine di questo capitolo.

Ogni capitolo è formato da una sezione da leggere subito e da una parte di riferimento più approfondita. La sezione da leggere subito è composta dai seguenti elementi:

-   Un elenco di attività di "configurazione" che devono essere eseguite per la messa in pratica delle operazioni, quali le modalità di configurazione dei backup e del monitoraggio.

-   Un elenco di operazioni periodiche che devono essere effettuate per garantire il funzionamento della soluzione (nell’elenco sono contenute attività quali il rinnovamento dei certificati CA).

-   Istruzioni per assegnare i ruoli operativi al personale operativo.

La parte restante di ciascun capitolo è composta da procedure dettagliate relative ad attività operative e di supporto. L'elenco delle attività di configurazione e operazioni periodiche menzionato in precedenza si riferisce alle attività illustrate in questa sezione.

La parte di riferimento di ciascun capitolo è organizzata in base alle categorie MOF descritte nella successiva sezione. Segue una breve sezione sulla struttura di ciascuna attività. È preferibile leggere questa parte prima di passare ai capitoli 11 e 12.

[](#mainsection)[Inizio pagina](#mainsection)

### Introduzione al modello Microsoft Operations Framework

Le guide operative fornite per questa soluzione si basano su Microsoft Solutions for Management (MSM), che combina procedure consigliate e relativi servizi di implementazione e metodi di automazione, con cui ottenere prestazioni operative eccellenti caratterizzate da servizi di alta qualità, affidabilità, disponibilità, protezione e ridotto costo totale di proprietà (TCO, Total Cost of Ownership).

Le procedure consigliate si basano sul modello MOF (Microsoft Operations Framework), che include linee guida relative alla modalità di pianificazione, distribuzione e gestione dei processi operativi IT a supporto delle soluzioni per servizi aziendali mission-critical.

MOF rappresenta un approccio strutturato ma flessibile basato su ITIL (IT Infrastructure Library), che descrive i processi e le procedure consigliate necessarie per fornire soluzioni per servizi aziendali mission-critical. Le sezioni che seguono forniscono un'introduzione a MOF e MSM.

Per la comprensione della struttura di questa guida e un uso appropriato, è fondamentale capire il modello di processo MOF e il modello di team MOF.

#### Il modello di processo MOF

Il modello di processo MOF è diviso in quattro fasi, ciascuna delle quali tratta un aspetto del ciclo di vita del sistema: operatività, supporto, ottimizzazione e modifica. Ogni fase comprende a sua volta una serie di funzioni di gestione dei servizi (SMF, Service Management Function). In ciascuna funzione di gestione dei servizi viene esaminata un'area di attività, tra cui la gestione dell'archiviazione, la gestione delle emergenze o la gestione delle modifiche. Nella figura seguente viene delineato graficamente il modello di processo MOF.

[![](images/Dd536211.10fig10-1(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536211.10fig10-1_big(it-it,technet.10).gif)

**Figura 10.1 Il modello di processo MOF**

##### Fase di operatività

In questa fase, sono incluse tutte le attività necessarie per mantenere un sistema in buono stato di funzionamento, tra cui il backup dei dati, il monitoraggio dello stato dei servizi e la gestione di directory e protezione. In questa sezione, vengono indicate tutte le attività della fase operativa che sono correlate a questa soluzione, comprendenti le attività quotidiane di esercizio, nonché suggerimenti per il monitoraggio e il controllo. Per entrambe queste aree è possibile utilizzare gli script di gestione inclusi nella soluzione.

##### Fase di supporto

Questa fase riguarda la gestione e la soluzione dei problemi del sistema. Include il ripristino dei server e dei servizi, l'helpdesk, l'analisi e la risoluzione dei problemi. Nella fase relativa al supporto, è possibile trovare attività correlate al supporto della gestione della soluzione per la protezione di una rete senza fili.

##### Fase di ottimizzazione

Questa fase riguarda le modalità di miglioramento del servizio offerto dal sistema. In questa sezione è possibile reperire informazioni chiave su funzioni quali la pianificazione della capacità, la disponibilità e la gestione della continuità.

##### Fase di modifica

Questa fase riguarda la pianificazione e l'implementazione delle modifiche nell'ambiente. Include la gestione delle modifiche e del rilascio, oltre alla gestione della configurazione. Vengono identificati i più comuni sottoinsiemi di modifiche apportabili all'infrastruttura della soluzione e descritti i processi di modifica e rilascio a esse associati. Vengono inoltre indicate le informazioni utilizzate in un sistema di gestione della configurazione.

#### Modello di team MOF

Il modello di team MOF e i relativi cluster di ruoli rappresentano una guida valida per garantire l'assegnazione del personale adeguato ai ruoli operativi. Tali ruoli e team funzionali sono illustrati nella figura seguente nella quale vengono anche associati ai cluster di ruoli MOF a cui potrebbero essere assegnati.

[![](images/Dd536211.10fig10-2(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536211.10fig10-2_big(it-it,technet.10).gif)

**Figura 10.2 Il modello di processo MOF**

È possibile utilizzare le descrizioni del modello di team MOF fornite in precedenza per assegnare le responsabilità di ciascuna attività alla persona adatta e, quindi, stabilire la suddivisione di attività e responsabilità per ogni individuo coinvolto nella gestione dell'infrastruttura PKI.

#### Implementazione pratica dei ruoli

I ruoli definiti dal modello di team MOF sono raggruppati in base alle responsabilità dei processi di gestione piuttosto che in base ai componenti tecnologici o alle divisioni organizzative. Nelle aziende di piccole dimensioni, uno o due membri del personale IT possono assumersi le responsabilità di tutti i ruoli. Anche in organizzazioni di maggiori dimensioni, in cui il reparto IT è molto più specializzato, può accadere che non vi sia un chiaro mapping tra i ruoli del processo MOF e i ruoli dei singoli membri del personale IT.

In ognuno dei seguenti capitoli della Guida operativa sono stati definiti i ruoli amministrativi e i corrispondenti gruppi di protezione. Sarà necessario associare tali ruoli e gruppi di protezione al personale dell'organizzazione. È opportuno prendere visione delle procedure operative definite nei capitoli seguenti per poter delineare un quadro delle persone responsabili dell'espletamento dell'attività all'interno dell'organizzazione.

Nello svolgimento di questo compito è necessario prendere in considerazione quanto segue:

-   Evitare sempre di avere una sola persona responsabile di un ruolo, in quanto ciò può causare problemi qualora tale persona abbandoni l'azienda.

-   Evitare di utilizzare account generici condivisi da diverse persone, poiché ciò rende impossibile le operazioni di controllo e non favorisce la responsabilizzazione.

-   La maggior parte dei professionisti della protezione consiglia di tenere separato almeno il ruolo di controllore, anche se tutti gli altri ruoli vengono concentrati in poche persone.

[](#mainsection)[Inizio pagina](#mainsection)

### Convenzioni di struttura per le attività

Tutte le attività descritte nei capitoli della Guida operativa sono raggruppate in base alla fase MOF e alla classificazione delle funzioni SMF descritte in precedenza. Ai livelli superiori, le attività sono raggruppate per fase e, a sua volta, ogni fase si suddivide in diverse funzioni SMF. L'ordine delle attività all'interno di ciascuna funzione SMF e delle funzioni SMF in ogni fase non ha particolare importanza.

**Nota:** non tutte le funzioni SMF hanno attività associate nella guida. Alcune funzioni SMF, tra cui la gestione della forza lavoro e la gestione finanziaria, devono essere definite nell'ambito della propria azienda.

Ciascuna attività è strutturata come segue:

-   Nome attività

-   Scopo attività e breve descrizione

-   Riepilogo attributi attività

-   Dettagli attività

Lo scopo e il titolo dell'attività non richiedono spiegazioni. Il riepilogo degli attributi dell'attività elenca i requisiti di protezione (in termini di appartenenza ai gruppi di protezione), la frequenza con cui l'attività deve essere svolta e le eventuali tecnologie necessarie per completare l'attività. Di seguito è riportato un esempio:

**Riepilogo delle informazioni**

-   **Requisiti di protezione**: account con diritti di creazione di unità organizzative in una parte specifica del servizio directory Active Directory®.

-   **Frequenza**: attività di configurazione.

-   **Requisiti di tecnologia**: snap-in Console di gestione (MMC) Utenti e computer di Active Directory.

La sezione dei dettagli dell'attività in genere contiene la procedura dettagliata richiesta per completare l'attività. I dettagli di alcune attività, quali le attività di configurazione, possono contenere informazioni (come la descrizione degli ID del registro eventi) necessarie per effettuare un'attività, piuttosto che istruzioni procedurali.

[](#mainsection)[Inizio pagina](#mainsection)

### Ulteriori informazioni

-   Per informazioni generali su MOF, vedere [Microsoft Operations Framework](http://www.microsoft.com/mof) all'indirizzo www.microsoft.com/mof (in inglese).

-   Per ulteriori informazioni su MOF, vedere l'articolo [“Team Model for Operations”](http://technet.microsoft.com/en-us/library/cc539261.aspx) all'indirizzo www.microsoft.com/technet/itsolutions/techguide/mof/moftml.mspx (in inglese).

[](#mainsection)[Inizio pagina](#mainsection)
