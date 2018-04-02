---
TOCTitle: Introduzione alla soluzione Protezione delle reti LAN senza fili con Servizi certificati
Title: Introduzione alla soluzione Protezione delle reti LAN senza fili con Servizi certificati
ms:assetid: '30f90d1c-7faa-432f-b6c8-d4927fe36229'
ms:contentKeyID: 20213242
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc527055(v=TechNet.10)'
---

Cenni preliminari
=================

Pubblicato: 10/11/2004 | Aggiornato: 24/11/2004

### Protezione delle reti LAN senza fili con Servizi certificati

*La soluzione Protezione delle reti LAN senza fili con*  *Servizi certificati* fornisce istruzioni sull'identificazione delle vulnerabilità presenti nelle odierne reti senza fili. Molte organizzazioni hanno tentato di utilizzare le reti LAN senza fili (WLAN), ma sono state spesso scoraggiate da operazioni di distribuzione di grandi dimensioni. Nonostante i numerosi vantaggi offerti dalle reti WLAN da un punto di vista tecnologico e produttivo, il problema di ottenere un buon grado di protezione ne ha impedito l'implementazione da parte di molte organizzazioni. Altre aziende hanno implementato le reti WLAN 802.11 avvalendosi di funzioni di protezione incorporate limitate o inesistenti.

Questa guida è stata aggiornata con lo scopo di migliorare il livello di utilizzabilità e fornire ulteriori informazioni dettagliate sui vantaggi e gli svantaggi dei diversi metodi di protezione senza fili. La guida contiene una Guida alla pianificazione che tratta dell'implementazione di un'infrastruttura senza fili e una Guida alla creazione che fornisce dettagli relativi all'implementazione. È altresì inclusa una Guida operativa che fornisce informazioni sul mantenimento di un ambiente senza fili protetto e una Guida per i test che illustra la strategia adottata per verificare il contenuto della documentazione e contiene istruzioni su come convalidare l'implementazione.

Analogamente alla guida Protezione delle reti LAN senza fili con PEAP e password pubblicata agli inizi dell'anno, questa guida fornisce istruzioni sull'identificazione delle vulnerabilità presenti nelle odierne reti senza fili ed è rivolta alle organizzazioni che intendono distribuire la tecnologia WLAN con un elevato grado di protezione. Questa guida, tuttavia, è concepita per le organizzazioni che prevedono dalle centinaia alle migliaia di utenti della rete senza fili e si basa sulla distribuzione WLAN di Microsoft.

Questa guida fornisce ai professionisti IT informazioni su come progettare, implementare e rendere operativa un'infrastruttura di protezione senza fili realizzata con l'autenticazione 802.1X e la crittografia WLAN, RADIUS e un'infrastruttura a chiave pubblica (PKI). Per i pianificatori aziendali e gli architetti IT, la guida presenta un esame delle vulnerabilità della rete senza fili e una valutazione delle varie opzioni di protezione disponibili. Viene, inoltre, descritta una progettazione dettagliata di una soluzione completa e delle sue componenti. Per i responsabili delle operazioni e dell'implementazione IT, la guida offre istruzioni dettagliate e script correlati per implementare e gestire un'infrastruttura di protezione senza fili.

[![](images/Cc527055.00fig0-1(it-it,TechNet.10).gif "Figure 1 Panoramica della soluzione Protezione delle reti LAN senza fili con Servizi certificati")](https://technet.microsoft.com/it-it/cc527055.00fig0-1_big(it-it,technet.10).gif)

**Figure 1 Panoramica della soluzione Protezione delle reti LAN senza fili con Servizi certificati**

#### Contenuto della soluzione

*La soluzione Protezione delle reti LAN senza fili* *con Servizi certificati* è organizzata in una serie di guide relative a ciascuna delle varie fasi dell'implementazione di una soluzione di protezione per reti WLAN e contiene una Guida per la consegna inclusa in un'appendice. Insieme alla documentazione vengono forniti alcuni strumenti, inclusi i piani di rischio e un esempio di progetto, gli script e i file di configurazione che consentono di automatizzare le attività di implementazione e operazioni e un insieme dettagliato di casi pratici di test per la verifica della funzionalità una volta implementata la soluzione nel proprio ambiente aziendale.

##### Guida alla pianificazione

La [**Guida alla pianificazione**](http://tnstage.redmond.corp.microsoft.com/it-it/library/dd536248.aspx) fornisce le seguenti informazioni agli architetti IT:

-   Motivi aziendali e tecnici per l'implementazione di una soluzione di protezione senza fili.

-   Strategie per la protezione senza fili.

-   Descrizione dettagliata delle decisioni di progettazione che influiscono sulla soluzione nel suo insieme e sui relativi componenti.

I capitoli sulla progettazione includono, inoltre, trattazioni approfondite su argomenti tecnici e altre informazioni correlate che consentono di personalizzare la progettazione, se necessario.

##### Guida alla creazione

La [**Guida alla creazione**](http://tnstage.redmond.corp.microsoft.com/it-it/library/dd536191.aspx) fornisce ai responsabili dell'implementazione IT istruzioni dettagliate per l'implementazione di tutti i componenti della soluzione: un’infrastruttura PKI basata sui Servizi certificati Microsoft® Windows Server™ 2003, un’infrastruttura RADIUS basata sul Servizio autenticazione Internet (IAS) di Microsoft e informazioni su come configurare i client e i punti di accesso senza fili. Ogni capitolo contiene procedure dettagliate per l'installazione e la protezione del sistema operativo, la configurazione dei componenti software e la relativa integrazione nella soluzione. Tutti i passaggi principali sono collegati ad alcune procedure di verifica che consentono di ridurre eventuali errori.

##### Guida operativa

La [**Guida operativa**](http://tnstage.redmond.corp.microsoft.com/it-it/library/dd536214.aspx) descrive le procedure necessarie per mantenere i componenti della soluzione a lungo termine. Basata su Microsoft Solutions for Management (MSM), questa guida fornisce una serie completa di attività e istruzioni per rendere operativi, monitorare, modificare e supportare i Servizi certificati e i componenti IAS. Sono incluse informazioni sulle attività di configurazione richieste per implementare il sistema di gestione e sulle operazioni giornaliere e settimanali. Vengono, inoltre, forniti gli script di monitoraggio e controllo dello stato del sistema, le procedure per il backup e il ripristino, le tecniche di risoluzione dei problemi e vari strumenti.

##### Guida per i test

La [**Guida per i test**](http://tnstage.redmond.corp.microsoft.com/it-it/library/cc527057.aspx) spiega la strategia complessiva adottata da Microsoft per convalidare questa soluzione e descrive i casi pratici di test principali che l'utente può eseguire per convalidare la soluzione nei propri laboratori. Insieme alla soluzione, viene fornita la serie completa dei casi pratici di test per la guida.

#### Download

Questa soluzione e i relativi strumenti e modelli associati sono disponibili per il [download](http://go.microsoft.com/fwlink/?linkid=14844) nell'area di download del sito Web Microsoft.

#### Supporto

Per ulteriori informazioni sul supporto offerto per i componenti Microsoft Windows Server 2003 utilizzati in questa soluzione (inclusi procedure per la risoluzione dei problemi, programmi di assistenza, risorse e livelli di supporto), visitare la pagina Web [Supporto Tecnico Microsoft](http://support.microsoft.com/) sul sito Microsoft.com all'indirizzo http://support.microsoft.com/.

#### Altre risorse

Tra le altre risorse che potrebbero risultare utili, figurano:

-   [Windows Deployment and Resource Kits](http://www.microsoft.com/windows/reskits/) all'indirizzo http://www.microsoft.com/windows/reskits/.

-   Il sito Web [Microsoft TechNet Security Resource Center](http://technet.microsoft.com/security/default.aspx) all'indirizzo http://technet.microsoft.com/security/default.aspx.

-   La pagina [Wi-Fi](http://www.microsoft.com/wifi) del sito Web Microsoft Windows Server 2003 all'indirizzo http://www.microsoft.com/wifi.

-   Il sito Web [WiFi Alliance](http://www.wi-fialliance.org/opensection/index.asp) all'indirizzo http://www.wi-fialliance.org/OpenSection/index.asp.

-   La pagina Web [IEEE 802 LAN/MAN Standards Committee](http://www.ieee802.org/%20(in%20inglese).) all'indirizzo http://www.ieee802.org/.

#### Commenti e suggerimenti

Microsoft è lieta di ricevere commenti e suggerimenti dei lettori su questo materiale. È particolarmente gradito l'invio di commenti sui seguenti argomenti:

-   Livello di utilità delle informazioni fornite.

-   Accuratezza delle procedure.

-   Livello di chiarezza e interesse dei capitoli.

-   Valutazione complessiva della soluzione.

Inviare i commenti e i suggerimenti al seguente indirizzo di posta elettronica: [SecWish@Microsoft.com](mailto:secwish@microsoft.com?subject=feedback%20re:%20microsoft%20solution%20for%20secure%20wireless%20lans)

#### Riconoscimenti

Responsabile del rilascio: Flicka Crandell

Autori: Ian Hellen e Stirling Goetz

Collaboratori: Carsten Kinder e Andrew Hawkins

Team di test: Mehul Mediwala e Jon Stone

Curatori: Wendy Cleary, John Cobb, e Steve Wacker

Responsabili di programma: Jeff Coon, Karl Grunwald e Bomani Siwatu

Responsabile del rilascio: Flicka Crandell

**Scarica la soluzione completa**
[Protezione delle reti LAN senza fili con Servizi certificati](http://go.microsoft.com/fwlink/?linkid=14844)

[](#mainsection)[Inizio pagina](#mainsection)
