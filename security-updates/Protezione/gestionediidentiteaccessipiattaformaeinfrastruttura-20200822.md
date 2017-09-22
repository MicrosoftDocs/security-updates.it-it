---
TOCTitle: 'Gestione di identità e accessi: Piattaforma e infrastruttura'
Title: 'Gestione di identità e accessi: Piattaforma e infrastruttura'
ms:assetid: 'a2b7e156-0ecf-4e17-8a96-ef650a0d7dcb'
ms:contentKeyID: 20200822
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536223(v=TechNet.10)'
---

Piattaforma e infrastruttura
============================

Aggiornato: 29 agosto 2004

### Riepilogo operativo

Nel presente documento vengono illustrati i problemi tipici correlati alla gestione di identità e accessi affrontati dalla maggior parte delle organizzazioni. Nel documento viene inoltre fornita la descrizione di una piattaforma tecnologica progettata come base per le soluzioni di gestione di identità e accessi, utilizzando un'organizzazione fittizia denominata Contoso Pharmaceuticals. Vengono esaminati i problemi e le opportunità che devono essere affrontati mediante efficaci tecnologie per la gestione di identità e accessi, nonché i potenziali pericoli e le relative contromisure.

Questo documento fa parte della [*Serie Microsoft Gestione di identità e accessi*](http://technet.microsoft.com/it-it/library/dd536198.aspx) disponibile sul sito Web Microsoft TechNet.

#### La sfida per le aziende

La gestione di identità e accessi è diventata più complessa con la crescita dell'importanza assunta dall'utilizzo delle identità digitali nelle modalità di interazione fra gli utenti e le reti informatiche. È necessario che le organizzazioni siano in grado di identificare gli utenti in modo efficace prima di concedere loro l'accesso a risorse su computer locali o in rete. Tuttavia, anche le aziende che utilizzano reti di piccole dimensioni raramente archiviano le relative informazioni sulle identità in un'unica posizione. Reparti numerosi, sedi in paesi e regioni differenti, divisioni aziendali e una vasta gamma di applicazioni software, oltre che fusioni e acquisizioni, hanno come risultato la proliferazione di archivi delle identità specifici per database, servizi di directory e applicazioni.

Lo sviluppo di un'efficace e coerente strategia di gestione di identità e accessi richiede una comprensione profonda degli approcci e delle tecnologie che è possibile utilizzare per la gestione di identità digitali sempre in crescita. Le organizzazioni e i reparti IT devono implementare approcci sia strategici che a breve termine per il controllo e l'utilizzo delle identità.

Un'ulteriore sfida in merito alla gestione di identità e accessi è rappresentata dal fatto che i problemi di protezione devono garantire il continuo funzionamento dell'operatività aziendale. Esiste sempre un compromesso tra il livello di protezione all'interno di un'organizzazione e la funzionalità. In questo documento vengono trattate queste problematiche e viene illustrato come gestire i problemi di protezione senza compromettere in alcun modo la capacità degli utenti di svolgere regolarmente le proprie mansioni.

#### I vantaggi per le aziende

La risoluzione di queste problematiche con una piattaforma di gestione di identità e accessi appropriata fornirà all'organizzazione i seguenti vantaggi:

-   Accesso degli utenti alle risorse migliorato e più vantaggioso in termini economici.

-   Amministrazione centralizzata delle identità digitali.

-   Sovraccarico ridotto che prevede la necessità di un minor numero di amministratori per l'implementazione e la gestione delle identità digitali e l'applicazione della gestione degli accessi.

-   Requisiti dei profili di protezione coerenti in modo da fornire misure di protezione più appropriate per le risorse della società.

-   Maggiori opportunità di collaborazione protetta con i partner, i clienti e i dipendenti aziendali che lavorano in remoto.

#### Destinatari della guida

Questo documento è rivolto ad architetti di sistema, professionisti e responsabili IT, responsabili dei processi decisionali a livello tecnico e consulenti coinvolti nelle attività di gestione di identità e accessi.

#### Prerequisiti per i lettori

In questo documento si presume che il lettore disponga di una discreta conoscenza dei concetti e delle tecnologie di gestione di identità e accessi, come descritto nel documento "Concetti di base" in questa serie.

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica

Le problematiche aziendali illustrate in questo documento sono identiche a quelle che la maggior parte delle organizzazioni deve affrontare durante il processo di gestione di identità e accessi. Le organizzazioni necessitano di una piattaforma tecnologica che fornisca quanto segue:

-   Conformità agli standard LDAP (Lightweight Directory Access Protocol).

-   Servizi di autenticazione avanzati, quale il protocollo di autenticazione Kerberos versione 5.

-   Supporto integrato per le attività di sviluppo e una gamma completa di interfacce API (Application Programming Interfaces) per sviluppatori.

-   Controllo dell'accesso basato sui ruoli (RBAC).

-   Supporto per scenari Intranet ed Extranet.

-   Supporto per l'autenticazione, l'autorizzazione e il controllo in un ambiente di directory distribuito.

La possibilità per un'organizzazione di collaborare con partner, clienti e dipendenti garantisce ulteriori opportunità di profitto e consente di incrementare la flessibilità aziendale. Tuttavia, i tentativi non autorizzati di accesso ai dati, i requisiti normativi e le legislazioni che regolano la protezione dei dati, unitamente alla propagazione di virus, worm e posta indesiderata, generano la necessità di una stretta integrazione delle attività di pianificazione, monitoraggio e analisi e di una costante vigilanza.

Questo documento è costituito da sei capitoli in cui vengono trattati i seguenti argomenti:

[**Capitolo 1: Introduzione**](http://technet.microsoft.com/it-it/library/dd536224)

Nell'introduzione vengono riportati un riepilogo operativo, i principali destinatari a cui questo documento è rivolto e una panoramica su ciascun capitolo della Guida.

[**Capitolo 2: Approcci alla scelta di una piattaforma**](http://www.microsoft.com/italy/technet/security/topics/identity/p1plat_1.mspx)

In questo capitolo viene illustrata la creazione di una piattaforma per la gestione di identità e accessi, un'operazione che prevede la necessità di prendere alcune decisioni significative che hanno un notevole impatto sulle funzionalità IT di un'organizzazione. Queste decisioni comprendono la scelta tra l'acquisto di una soluzione di un singolo fornitore o di più prodotti leader del settore che è possibile integrare in modo da formare una soluzione completa.

Nella parte rimanente del capitolo vengono illustrate le opzioni relative alla scelta di una singola piattaforma o dei migliori prodotti disponibili sul mercato e viene descritto l'impatto di entrambi gli approcci sulle aree di tecnologia dei servizi directory, della gestione dell'accesso, dei servizi di attendibilità, degli strumenti di gestione del ciclo di vita delle identità e della piattaforma in uso.

[**Capitolo 3: Problemi e requisiti**](http://technet.microsoft.com/it-it/library/dd536225)

In questo capitolo viene presentata l'organizzazione fittizia Contoso Pharmaceuticals, utilizzata per descrivere i numerosi requisiti comuni a livello aziendale, di tecnologia e di protezione richiesti dalla maggior parte delle organizzazioni a una piattaforma per la gestione di identità e accessi. Nel capitolo vengono inoltre illustrate le vulnerabilità a livello di protezione presenti nell'ambiente di Contoso Pharmaceuticals che generano la necessità di molti di questi requisiti.

[**Capitolo 4: Progettazione dell'infrastruttura**](http://www.microsoft.com/italy/technet/security/topics/identity/p1plat_3.mspx)

In questo capitolo viene illustrata l'architettura tecnologica di Contoso Pharmaceuticals, in base alla decisione di utilizzare la piattaforma Microsoft di Gestione di identità e accessi. L'architettura di questa piattaforma offre un insieme di base di sistemi operativi, di servizi di protezione e directory e di tecnologie che verranno utilizzati da un'ampia gamma di soluzioni, applicazioni e processi aziendali come base per una gestione di identità e accessi efficace adottata dalla società.

[**Capitolo 5: Implementazione dell'infrastruttura**](http://technet.microsoft.com/it-it/library/dd536226)

In questo capitolo vengono fornite le linee guida per la modalità di preparazione dell'infrastruttura di Contoso Pharmaceuticals. Vengono presentati inoltre strumenti e modelli che è possibile utilizzare per stabilire l'ambiente di base, che costituisce un prerequisito di implementazione per gli altri documenti di questa serie. Le linee guida in questo capitolo sono state create per consentire ai consulenti e ai clienti di stabilire gli scenari relativi alla soluzione Microsoft di Gestione di identità e accessi in un laboratorio o in un ambiente di verifica funzionale.

[**Capitolo 6: Funzionamento dell'infrastruttura**](http://technet.microsoft.com/it-it/library/dd536227)

Una volta implementata l'infrastruttura, è necessario eseguire una serie di attività operative continue a intervalli pianificati per assicurarsi che la piattaforma continui a funzionare correttamente. In questo capitolo vengono forniti i riferimenti operativi per i servizi di infrastruttura descritti nel presente documento.

[](#mainsection)[Inizio pagina](#mainsection)
