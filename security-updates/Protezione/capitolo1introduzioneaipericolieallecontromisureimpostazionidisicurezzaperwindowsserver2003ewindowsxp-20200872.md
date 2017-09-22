---
TOCTitle: 'Capitolo 1: Introduzione ai pericoli e alle contromisure: Impostazioni di sicurezza per Windows Server 2003 e Windows XP'
Title: 'Capitolo 1: Introduzione ai pericoli e alle contromisure: Impostazioni di sicurezza per Windows Server 2003 e Windows XP'
ms:assetid: '940e06d5-6d45-4804-9a6f-b78905de734d'
ms:contentKeyID: 20200872
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536273(v=TechNet.10)'
---

Pericoli e contromisure
=======================

### Capitolo 1: Introduzione ai pericoli e alle contromisure: Impostazioni di sicurezza per Windows Server 2003 e Windows XP

Questa guida ha lo scopo di fornire il materiale di riferimento per tutte le impostazioni di protezione da adottare come contromisure a pericoli specifici che minacciano le versioni correnti dei sistemi operativi Microsoft Windows.

Questa guida affianca altre due pubblicazioni Microsoft:

-   [*Guida per la protezione di Windows Server 2003*](http://go.microsoft.com/fwlink/?linkid=14845), disponibile in linea all'indirizzo
    http://go.microsoft.com/fwlink/?LinkId=14845

-   [*Guida per la protezione di Windows XP*](http://go.microsoft.com/fwlink/?linkid=14839), disponibile in linea all'indirizzo
    http://go.microsoft.com/fwlink/?LinkId=14839* *

Molte delle contromisure ivi descritte non sono destinate a specifici ruoli dei computer riportati nelle guide correlate e, in alcuni casi, non sono destinate ad alcun ruolo. Le contromisure aiutano a garantire compatibilità, possibilità d'impiego, gestibilità, disponibilità e prestazioni.

Come è già stato affermato spesso, protezione e funzionalità sono gli estremi opposti di un continuum; più alto è il livello di protezione, più basso è il livello di funzionalità e viceversa. Naturalmente vi sono delle eccezioni a questa regola e applicando alcune contromisure è possibile migliorare la funzionalità, ma nella maggior parte dei casi l'affermazione precedente risulta vera.

La struttura dei capitoli di questa guida cerca di riprodurre quanto più possibile quella delle sezioni delle principali impostazioni dell'Editor oggetti Criteri di gruppo. Ogni capitolo inizia con una breve spiegazione di ciò che è in esso contenuto, seguita dall'elenco dei titoli delle sottosezioni, ciascuna delle quali si riferisce a una impostazione o gruppo di impostazioni. (Queste impostazioni sono elencate nella cartella di lavoro Microsoft Excel descritta successivamente in questo capitolo). Ogni sottosezione fornisce una breve spiegazione degli effetti della contromisura e contiene le seguenti tre sottosezioni aggiuntive:

-   **Vulnerabilità**. Illustra come un pirata informatico può sfruttare una funzione o la sua configurazione.

-   **Contromisura**. Illustra come implementare una contromisura.

-   **Impatto potenziale**. Illustra le conseguenze negative possibili una volta attuata la contromisura.

Ad esempio, il Capitolo 2, "Criteri a livello di dominio", ha inizio con le seguenti sezioni:

**Criteri di account**

-   Imponi cronologia delle password

    -   Vulnerabilità

    -   Contromisura

    -   Impatto potenziale

-   Validità massima password

    -   Vulnerabilità

    -   Contromisura

    -   Impatto potenziale

Questo schema viene riproposto nell'intera Guida. Le impostazioni strettamente collegate vengono presentate in un'unica sezione. Ad esempio, nel modulo "Opzioni di protezione" vi sono quattro impostazioni nella sezione Client e server di rete Microsoft: aggiungi firma digitale alle comunicazioni (quattro impostazioni correlate)”. Le impostazioni sono:

-   Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)

-   Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (sempre)

-   Client di rete Microsoft: aggiungi firma digitale alle comunicazioni (se autorizzato dal server)

-   Server di rete Microsoft: aggiungi firma digitale alle comunicazioni (se autorizzato dal server)

Sebbene molte impostazioni dei criteri di gruppo siano documentate, questa guida non riporta le impostazioni destinate ad aiutare le organizzazioni a gestire i propri ambienti. Questa guida esamina solo le impostazioni e le funzionalità di Microsoft Windows Server 2003 con SP1 e Windows XP con SP2 in termini di protezione delle organizzazioni contro pericoli specifici. Le impostazioni e le funzioni aggiunte ai Service Pack in un momento successivo o le funzionalità che possono essere state aggiunte da versioni software successive a detti Service Pack, non sono esaminate in questa sede. Anche le funzioni di gestione e le funzioni di protezione che non sono configurabili dagli amministratori non sono descritte in questa guida.

Le informazioni contenute all'interno della presente guida sono utili per comprendere le contromisure disponibili nelle versioni correnti del sistema operativo Windows. Tuttavia, per indicazioni precise sulle impostazioni da utilizzare per scenari specifici, fare riferimento alle due guide correlate:

-   *Guida per la protezione di* *Windows* *Server 2003*, disponibile in linea all'indirizzo
    [http://go.microsoft.com/fwlink/?LinkId=14845](http://go.microsoft.com/fwlink/?linkid=14845)

-   *Guida per la protezione di* *Windows XP*, disponibile in linea all'indirizzo
    [http://go.microsoft.com/fwlink/?LinkId=14839](http://go.microsoft.com/fwlink/?linkid=14839)* *

La cartella di lavoro di Microsoft Excel "Configurazione dei servizi e della protezione predefinita di Windows" della presente guida, riporta le impostazioni predefinite. Il primo foglio di lavoro ("Windows Server 2003 Defaults") fornisce informazioni dettagliate su tutte le impostazioni predefinite dei criteri di gruppo disponibili in Windows Server 2003. Le colonne contenute nel foglio di lavoro sono:

-   La colonna H, **Policy Setting Name in User Interface** è il nome dell'impostazione così come appare nel modulo snap-in Editor dei criteri di gruppo di Windows Server 2003.

-   La colonna J, **Default Domain Policy**, contiene il valore dell'impostazione nel Criterio dominio predefinito incorporato, creato quando si promuove il primo controller di dominio in un nuovo dominio del servizio directory Active Directory.

-   La colonna K, **Default Domain Controller Policy**, contiene il valore dell'impostazione nel Criterio controller di dominio predefinito incorporato, creato quando si promuove il primo controller di dominio in un nuovo dominio Active Directory.

-   La colonna L, **Stand-Alone Server Default Settings**, contiene il valore predefinito dell'impostazione in un computer Windows Server 2003 autonomo.

-   La colonna M, **Domain Controller Effective Default Settings**, contiene il valore delle impostazioni predefinite di un controller di dominio.

-   La colonna N, **Member Server Effective Default Settings**, contiene il valore effettivo delle impostazioni predefinite di un membro.

"Effective Default Setting" (impostazione predefinita) significa che questa è l'impostazione utilizzata dal sistema se le impostazioni di protezione non sono state modificate. Le impostazioni effettive di un sistema sono determinate dal motore dei criteri di gruppo all'avvio del computer. Il motore assegna le priorità delle impostazioni come descritto nella sezione "Applicazione dei criteri di gruppo" del Capitolo 2, "Meccanismi di protezione avanzata di Windows Server 2003" nella *Guida* *per la protezione di*  *Windows Server 2003*.

Per rendere i fogli di calcolo più leggibili, sono state aggiunte delle colonne per illustrare la gerarchia degli oggetti all'interno dell'Editor dei criteri di gruppo. Ciascuna delle colonne da A a G rappresenta un livello diverso della gerarchia. Ad esempio, la voce **Computer Configuration** che appare nella colonna A e **Security Settings** riportata nella colonna C. La colonna I è stata inserita per rendere il foglio di calcolo più leggibile.

Il secondo foglio di lavoro ("Windows Server 2003 System Services"), contiene un elenco di tutti i servizi disponibili in Windows Server 2003. Le colonne contenute nel foglio di lavoro sono:

-   La colonna A, **Full Service Name**, contiene un elenco di servizi in base al nome visualizzato negli strumenti di gestione grafica come Gestione servizi dell'estensione MMC (Microsoft Management Console).

-   La colonna B, **Service Name**, contiene un elenco di servizi in base al nome breve, formato utilizzato da molti strumenti della riga di comando.

-   La colonna C, **DC Startup Type**, contiene lo stato di avvio predefinito del servizio su un controller di dominio Windows Server 2003.

-   La colonna D, **Member Server Startup Type**, contiene lo stato di avvio predefinito del servizio su un computer Windows Server 2003 membro di un dominio basato su Active Directory.

-   La colonna E, **Stand-Alone Server Startup Type**, contiene lo stato di avvio predefinito del servizio su un computer autonomo Windows Server 2003.

-   La colonna H, **Logon As**, contiene l'account utilizzato da un servizio per accedere a una configurazione predefinita.

Il formato dei fogli di lavoro aggiuntivi ("Windows XP Defaults" e "Windows XP System Services") è simile a quello di questi due fogli, che forniscono informazioni sulle impostazioni e i servizi di protezione di Windows XP.

##### In questa pagina

[](#ebaa)[Riepilogo dei capitoli](#ebaa)
[](#eaaa)[Strumenti e modelli](#eaaa)

### Riepilogo dei capitoli

Windows Server 2003 con SP1 e Windows XP con SP2 sono attualmente le versioni più affidabili di questi sistemi operativi, con funzionalità avanzate per protezione e privacy. Questa guida si compone di dodici capitoli: i capitoli da 2 a 6 esaminano le procedure che consentono la creazione di un ambiente protetto. Ogni capitolo si serve di un processo end-to-end che consente di proteggere i computer che utilizzano i sistemi operativi in esame.

#### Capitolo 1: Introduzione ai pericoli e alle contromisure: Impostazioni di sicurezza per Windows Server 2003 e Windows XP

Questo capitolo contiene informazioni generali sulla guida, tra cui i destinatari del documento, nonché le problematiche esaminate e lo scopo complessivo della guida.

#### Capitolo 2: Criteri a livello di dominio

Questo capitolo esamina le impostazioni dei criteri di gruppo applicati a livello di dominio, ovvero i criteri di password, di blocco account e del protocollo di autenticazione Kerberos. Nel complesso, questi criteri vengono definiti come criteri di account.

#### Capitolo 3: Criteri di controllo

Questo capitolo esamina l'impiego dei criteri di controllo per eseguire il monitoraggio ed imporre le relative misure di protezione. Descrive le varie impostazioni e propone esempi delle modifiche subite dalle informazioni di controllo quando le impostazioni vengono cambiate.

#### Capitolo 4: Diritti utente

Questo capitolo esamina le tipologie dei diritti e dei privilegi di accesso assegnati dai sistemi operativi Windows, indicando a quali account assegnare tali diritti.

#### Capitolo 5: Opzioni di protezione

Questo capitolo introduce la sezione "Opzioni di Protezione" di Criterio di Gruppo e fornisce indicazioni sulle impostazioni di protezione per firme digitali dei dati, nomi degli account Amministratore e Guest, accesso alle unità per dischi floppy e CD-ROM, comportamento dell'installazione del driver e prompt di accesso.

#### Capitolo 6: Registro eventi

Questo capitolo fornisce indicazioni su come configurare le impostazioni relative ai vari registri evento dei computer Windows Server 2003 e Windows  XP.

#### Capitolo 7: Servizi di sistema

Windows XP e Windows Server 2003 offrono una serie di servizi di sistema. Molti servizi sono attivi per impostazione predefinita, mentre per altri si richiede l'installazione di componenti specifici. Questo capitolo elenca i servizi offerti dai vari sistemi operativi, suggerendo in modo specifico quali è necessario mantenere attivi e quali è possibile disabilitare, senza conseguenze negative.

#### Capitolo 8: Criteri di restrizione software

Questo capitolo fornisce brevi cenni sul meccanismo dei criteri di restrizione software, introdotto in Windows XP e Windows Server 2003. Fornisce collegamenti ad altre risorse per progettare e utilizzare i criteri di restrizione del software.

#### Capitolo 9: Modelli amministrativi di Windows XP e Windows Server 2003

Questo capitolo elenca le impostazioni disponibili nei modelli amministrativi per i criteri di gruppo. Non esamina tutte le impostazioni disponibili, si concentra essenzialmente sulle impostazioni relative alla protezione.

#### Capitolo 10: Voci aggiuntive di registro

Questo capitolo fornisce informazioni sulle voci aggiuntive di registro non elencate nel file del modello amministrativo, che sono tuttavia presenti nel modello di protezione di base. Fornisce istruzioni su come modificare l'interfaccia dell'Editor di configurazione della protezione per visualizzare tali voci nell'interfaccia di utente. Inoltre, propone voci di registro aggiuntive disponibili in Windows XP SP2 e Windows Server 2003 SP1.

#### Capitolo 11: Ulteriori contromisure

Questo capitolo descrive una serie di misure di protezione aggiuntive che potrebbe essere necessario applicare al computer. Si sottolinea, tuttavia, che queste contromisure non possono essere applicate facilmente attraverso i criteri di gruppo o altri metodi automatizzati. Tra le contromisure descritte, si segnalano la protezione degli account sui server membri, le impostazioni NTFS, la segmentazione di dati e applicazioni, le impostazioni del nome di comunità SNMP, la disattivazione dei binding NetBIOS, la configurazione dei Servizi terminal, Dr. Watson, i criteri di IPsec, nonché indicazioni per altre guide più approfondite su Windows Firewall.

#### Capitolo 12: Conclusioni

Il capitolo finale riesamina i punti salienti della guida offrendo brevi cenni generali su quanto discusso nei capitoli precedenti.

[](#mainsection)[Inizio pagina](#mainsection)

### Strumenti e modelli

Insieme a questa guida è contenuta una raccolta di file che consentono di valutare, verificare e implementare le contromisure consigliate. Questi file sono denominati in genere strumenti e modelli.

I file sono contenuti nell'archivio WinZip autoestraente che contiene la guida, disponibile presso l'area di download del sito Web Microsoft all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15160. Quando viene eseguito il file .msi, nel percorso specificato viene creata la seguente struttura di cartelle:

-   La cartella **\\Strumenti e modelli della Guida a pericoli e contromisure** contiene il foglio di lavoro Microsoft Excel "Windows Default Security and Services Configuration.xls", che propone un riepilogo dei servizi e delle impostazioni predefinite di Windows Server 2003 con SP1 e Windows XP con SP2.

-   La cartella **\\Strumenti e modelli della Guida a pericoli e contromisure\\Aggiornamento SCE** contiene i file di testo e file script. I file di testo consentono di modificare e personalizzare l'interfaccia utente dell'Editor di configurazione della protezione. I file script consentono di applicare automaticamente le impostazioni o di ripristinarle. Le relative procedure sono descritte in dettaglio nel Capitolo 10, "Voci aggiuntive di registro".

**Download**

[Scaricare la Guida a pericoli e contromisure](http://go.microsoft.com/fwlink/?linkid=15160)

**Notifiche di aggiornamento**

[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti e suggerimenti**

[Inviare commenti o suggerimenti](mailto:secwish@microsoft.com?subject=guida%20a%20pericoli%20e%20contromisure)

[](#mainsection)[Inizio pagina](#mainsection)
