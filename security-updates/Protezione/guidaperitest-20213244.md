---
TOCTitle: Guida per i test
Title: Guida per i test
ms:assetid: '4d249b34-b07e-46af-b8c7-e2ab85f0c26e'
ms:contentKeyID: 20213244
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc527056(v=TechNet.10)'
---

Guida per i test
================

Pubblicato: 10/11//2004 | Aggiornato: 24/11/2004

##### In questa pagina

[](#ehaa)[Introduzione](#ehaa)
[](#egaa)[Finalità dei test](#egaa)
[](#efaa)[Obiettivi dei test](#efaa)
[](#eeaa)[Strategia dei test](#eeaa)
[](#edaa)[Strumenti di test](#edaa)
[](#ecaa)[Casi pratici di test](#ecaa)
[](#ebaa)[Criteri di rilascio](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Introduzione

La Guida per i test consente di verificare il corretto funzionamento dell'implementazione della soluzione *Protezione di reti LAN senza fili con Servizi certificati*. La guida contenuta in questo capitolo è stata sviluppata e utilizzata dal team di test Microsoft Solutions for Security (MSS) come parte del testing interno della soluzione. La guida descrive la finalità, la strategia, gli obiettivi, l'ambiente di prova e i casi pratici dei test, nonché gli strumenti utilizzati. Infine, vengono riportati anche i risultati ottenuti con i test dai laboratori MSS.

#### Scopo del documento

Scopo di questo documento è fornire un modello predefinito da utilizzare per eseguire il testing della distribuzione della soluzione. Dopo aver eseguito i casi pratici dei test, la soluzione implementata dovrebbe funzionare come previsto, sia in un laboratorio di prova che in produzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Finalità dei test

La soluzione sottoposta a test è stata basata sul profilo aziendale fittizio descritto nel capitolo 3, “Architettura della soluzione di rete LAN senza fili protetta”.

#### Finalità perseguite

Per convalidare la soluzione, il team ha condotto diversi tipi di test. In ogni fase, sono state eseguite combinazioni differenti dei test, i cui tipi vengono elencati di seguito:

-   Test di base

-   Test funzionali

-   Test operativi

La descrizione dei test è riportata nella successiva sezione relativa ai casi pratici di test.

Il team ha eseguito i tre tipi di test elencati sui seguenti componenti utilizzati nella soluzione:

-   L'infrastruttura PKI, che comprende:

    -   Autorità di certificazione (CA, Certification Authority) principale

    -   CA di emissione

-   Servizio autenticazione Internet (IAS) di Microsoft

-   Client senza fili

    -   Microsoft® Windows® XP Professional con Service Pack 1 (SP1)

    -   Windows XP Tablet PC Edition con SP1

I test sono stati eseguiti con l'obiettivo di verificare se, a seguito dell'installazione di ciascun componente della soluzione, i client possano accedere ai seguenti servizi con lo stesso livello di funzionalità che avevano in precedenza. Ciò è stato concepito con l'intento di mostrare la regressione nella funzionalità dovuta all'introduzione di uno dei qualsiasi dei componenti elencati in precedenza o le modifiche ad essi apportate durante il processo di configurazione:

-   Connettività di rete

-   Controller di dominio

-   Configurazione IP: protocollo DHCP (Dynamic Host Configuration Protocol)

-   Servizi di risoluzione dei nomi: DNS (Domain Name System)

-   Servizi di gestione file: file server

-   Servizi Web: IIS (Internet Information Services)

-   Servizi di posta elettronica: Microsoft Exchange 2000

-   Accesso a reti senza fili

#### Finalità non perseguite

Nelle finalità dei test non rientrano le aree seguenti:

-   Valutazione delle vulnerabilità e test di penetrazione della soluzione. Consulenza di protezione commerciale eseguita sulla valutazione e il test suddetti.

-   Integrazione con un'infrastruttura a chiave pubblica (PKI) di terze parti.

-   Esecuzione di test esaustivi dei ruoli di server seguenti (escluso quello richiesto per verificare il corretto funzionamento della soluzione):

    -   Controller di dominio, protocollo DHCP (Dynamic Host Configuration Protocol) e nome del dominio DNS (Domain Name System)

    -   Exchange Server 2000

    -   Server Web, file server e server di stampa

    -   Microsoft Operations Manager (MOM)

-   Esecuzione di test esaustivi dei servizi client seguenti (utilizzati per verificare la funzionalità della soluzione):

    -   DNS e DHCP

    -   File

    -   Web

    -   Posta elettronica

-   Dalle finalità dei test sono stati esclusi i client con il software seguente:

    -   Windows 2000 Professional

    -   Pocket PC con Windows CE

    -   Microsoft Windows NT® versione 4.0

    -   Windows 9*x*

    -   Client diversi da Windows

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi dei test

I test sono stati eseguiti per verificare quanto segue.

1.  Tutte le istruzioni incluse nella soluzione sono chiare, complete e tecnicamente corrette.

2.  La soluzione offre una rete LAN senza fili (WLAN) protetta con i Servizi certificati che non comporta effetti negativi sulla funzionalità, le prestazioni e i criteri di protezione dell'infrastruttura esistente.

3.  La soluzione può essere facilmente distribuita. I professionisti IT in possesso della certificazione Microsoft Certified Systems Engineer (MCSE) per Windows 2000 (o Server 2003) o di un livello di competenze equivalente e di una buona conoscenza dei Servizi certificati e del servizio IAS sono in grado di utilizzare questa guida.

[](#mainsection)[Inizio pagina](#mainsection)

### Strategia dei test

Per realizzare gli obiettivi dei test, il team di test ha sviluppato un laboratorio presso Woodgrove Bank, una società fittizia di 15.000 utenti. L'ambiente di prova è descritto più avanti nel capitolo. I test sono stati suddivisi nelle seguenti fasi:

-   La soluzione è stata sottoposta a test come parte del processo di sviluppo.

-   Superamento test di sistema uno.

-   Superamento test di sistema due.

-   Test di regressione del sistema.

I server dell'infrastruttura di base per i test comprendevano i ruoli seguenti (alcuni di essi combinati su un server):

-   Controller di dominio, DHCP e DNS

-   Server Web, file server e server di stampa

-   Server di posta elettronica Microsoft Exchange Server

-   Server Microsoft Outlook® Web Access

-   Controller di dominio Active Directory®

Questi servizi sono stati verificati mediante l'esecuzione dei test di base prima dell'implementazione dei componenti della soluzione. Una copia dell'immagine di ciascun server dell'infrastruttura è stata scattata per poter essere utilizzata nel secondo test. Il test di regressione ha utilizzato la stessa infrastruttura del secondo test.

I test di sistema (uno e due) sono stati suddivisi in due fasi di creazione incrementale:

1.  Fase dei Servizi certificati dell'infrastruttura PKI

2.  Fase WLAN

Le fasi vengono descritte dettagliatamente più avanti.

Tutti i problemi importanti sorti in una fase specifica sono stati documentati dal team di test come errori e risolti nell'ambito della stessa fase, prima del passaggio alla fase successiva di test. Questa strategia ha agevolato la rapida soluzione dei problemi critici e ha consentito di evitare l'impegno di tempo e i costi associati al debug.

L'esecuzione di più test (o cicli di test), inoltre, ha consentito di risolvere tutti i problemi non critici del ciclo *N* nel ciclo di test di regressione *N+1,* garantendo l'elevata qualità della soluzione. La soluzione si è dimostrata stabile alla fine del terzo ciclo di test di regressione.

La figura seguente illustra il metodo di test a fasi utilizzato in questa guida.

[![](images/Cc527056.13fig13-1(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc527056.13fig13-1_big(it-it,technet.10).gif)

**Figure 13.1. Il metodo di test a fasi utilizzato per la soluzione**

#### Fasi di test

I test sono stati condotti con una sequenza di fasi logiche. Ogni fase, incrementale rispetto alla precedente, è stata suddivisa nei passaggi indicati di seguito.

1.  Criterio iniziale: inizio della fase

2.  Creazione del componente

3.  Esecuzione di diversi tipi di test sul componente creato

4.  Criterio finale: fine della fase

#### Fase PKI

Il criterio iniziale è l'esecuzione, con esito positivo, dei test di base nei server dell'infrastruttura. Questa prima fase è stata suddivisa nei passaggi riportati di seguito.

1.  **Creazione PKI:** implementazione dei Servizi certificati per la rete. Sono state eseguite l'installazione, la creazione e la configurazione dei server della CA principale e della CA di emissione. Si è eseguita, inoltre, la creazione dei componenti della fase.

2.  **Esecuzione test di base:** in questa fase si è verificato che l'installazione dei Servizi certificati non influisse negativamente sull'infrastruttura e sui servizi client esistenti.

3.  **Esecuzione test funzionali:** in questa fase si è verificata la corretta implementazione e il perfetto funzionamento delle CA nella rete di test.

4.  **Esecuzione test operativi:** in questa fase si è verificata la possibilità di gestire e amministrare le CA mediante i ruoli amministrativi appropriati. Durante i test sono state controllate le diverse procedure operative dei componenti dei Servizi certificati citate nella Guida della soluzione.

Il criterio di uscita dalla fase è la riuscita di tutti i test precedenti.

#### Fase WLAN

La seconda fase incrementale, ossia la fase WLAN, è iniziata dopo il completamento con esito positivo della fase PKI. Il criterio di ingresso in questa fase è il completamento con esito positivo dell'installazione della fase PKI. La seconda fase è iniziata con l'installazione dei server IAS ed è proseguita con la configurazione dei componenti WLAN. La fase è stata suddivisa nei passaggi riportati di seguito.

1.  **Creazione IAS:** in questa fase sono stati installati e configurati i server IAS della rete, sia nell'area della sede centrale che in quella della filiale, secondo le indicazioni della Guida della soluzione.

2.  **Componenti WLAN:** in questa fase sono stati creati e configurati i componenti WLAN.

3.  **Client WLAN:** in questa fase sono stati configurati i client WLAN.

4.  **Esecuzione test di base completa:** in questa fase è stata verificata l'assenza di impatti negativi sull'infrastruttura di base e sui servizi client.

5.  **Esecuzione test funzionali completa:** in questa fase è stata verificata la riuscita della creazione e dell'implementazione della soluzione. Sono stati verificati i servizi di accesso protetto senza fili nella rete e il relativo utilizzo dell'infrastruttura PKI creata nella fase precedente.

6.  **Esecuzione test operativi completa:** in questa fase è stata verificata la possibilità di gestire e amministrare correttamente la rete protetta. Sono stati inoltre eseguiti nuovamente i test operativi e di gestione dei componenti dei Servizi certificati.

Il criterio di uscita dalla fase è la riuscita di tutti i test precedenti.

#### Ambiente di test

L'ambiente di test è stato concepito come un sottoinsieme funzionale dei servizi IT di cui potrebbe avvalersi una società come Woodgrove Bank. Tutti i principali servizi dell'infrastruttura richiesti dalla soluzione sono stati rappresentati nell'ambiente di prova. In laboratorio sono state emulate la sede centrale e una filiale di piccole dimensioni collegate tra loro da una connessione WAN di routing. In laboratorio sono stati inoltre installati i seguenti server dell'infrastruttura:

-   Controller di dominio, DHCP e DNS (sede centrale e filiale)

-   Microsoft Exchange 2000 (su Windows Advanced Server 2000) nella sede centrale

-   Server Web, file server e server di stampa nella sede centrale

-   MOM nella sede centrale

Per la soluzione sono stati installati i server:

-   CA principale nella sede centrale

-   CA di emissione nella sede centrale

-   Server IAS primario e secondario nella sede centrale e servizio IAS secondario nel controller di dominio della filiale.

#### Hardware

La configurazione hardware del laboratorio di test dei computer server è stata basata sui profili hardware forniti nella Guida della soluzione e sui seguenti componenti:

-   Client di computer desktop standard

-   Client di computer portatili standard

-   Client di Tablet PC standard

-   Punti di accesso senza fili conformi allo standard 802.1X nella sede centrale e nella filiale

-   Computer desktop per la simulazione del routing e della rete WAN

-   Switch di livello 3

#### Software

Il sistema operativo di base utilizzato nel laboratorio di test per i ruoli dei server, ad eccezione di Microsoft Exchange 2000, è stato Microsoft Windows Server™ 2003. Per l'esecuzione dei test, è stato inoltre utilizzato il software seguente:

-   Windows 2000 Advanced Server con SP3

-   Windows Server 2003 Enterprise Edition

-   Windows Server 2003 Standard Edition

-   Exchange 2000 con SP3

-   Windows XP Professional con SP1

-   Windows XP Professional con SP1 (versione Tablet)

-   MOM 2000 con SP1

-   Microsoft SQL Server™ 2000 con SP3

-   Outlook 2000 con SP1

Per eseguire i test relativi all'accesso senza fili protetto, nei client del laboratorio di test sono stati utilizzati i sistemi operativi seguenti:

-   Windows XP Professional con SP1

-   Windows XP Tablet PC Edition con SP1

#### Diagramma della rete

Di seguito viene riportato un diagramma schematico dettagliato dell'ambiente di prova.

[![](images/Cc527056.13fig13-2(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc527056.13fig13-2_big(it-it,technet.10).gif)

**Figura 13.2. Diagramma della rete del laboratorio di test**

#### Configurazioni e impostazioni

La figura precedente illustra la rete creata nel laboratorio di test per simulare lo scenario di Woodgrove Bank. In questo scenario, la rete della sede centrale contiene la maggior parte dei server dell'infrastruttura e della soluzione, mentre la rete della filiale prevede un solo server in cui vengono eseguiti i relativi servizi dell'infrastruttura e della soluzione. Il computer che simula la rete WAN provvede a creare la latenza della rete e la limitazione della larghezza di banda tra le reti. La configurazione e le impostazioni utilizzate sono identiche a quelle indicate nella Guida della soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Strumenti di test

Questa sezione descrive i diversi tipi di strumento utilizzati per il test della soluzione. La maggior parte di questi strumenti sono disponibili nella guida all'installazione del sistema operativo in uso. Negli altri casi, è possibile installare gli strumenti dalla cartella Support\\Tools del supporto di installazione di Windows Server 2003.

#### Software

Per il test, sono stati utilizzati gli strumenti indicati di seguito.

-   Certutil. Potente strumento di utilità dei Servizi certificati utilizzabile per l'installazione, la configurazione e la risoluzione dei problemi relativi alle CA.

-   Certreq. Strumento utilizzato per richiedere manualmente un certificato a una CA, disponibile nel supporto di installazione di Windows Server 2003.

-   Ldifde. Strumento utilizzato per importare ed esportare le informazioni di Active Directory tramite i file LDIF (LDAP Data Interchange Format). Questo strumento è stato utilizzato per alcune operazioni relative ai modelli di certificato della soluzione.

-   Ntbackup. Strumento utilizzato per il backup e il ripristino di file, disponibile nel supporto di installazione di Windows Server 2003.

#### Monitoraggio del sistema

Per il monitoraggio del sistema durante i test, sono stati utilizzati gli strumenti indicati di seguito.

-   Dcdiag. Strumento che consente di analizzare lo stato dei controller di dominio in un insieme di strutture di Active Directory e di segnalare eventuali inconvenienti per agevolare la risoluzione dei problemi.

-   Jetpack. Strumento utilizzato per verificare la coerenza del database DHCP.

-   Agenthelper. Utilità MOM che verifica il servizio OnePoint in esecuzione negli agenti gestiti da MOM.

-   PerfMon. Strumento che consente di visualizzare registri, avvisi e contatori relativi alle prestazioni del sistema.

-   NetMon. Strumento che acquisisce e filtra i frame del traffico di rete in arrivo e in partenza dal computer in cui l'utilità è installata.

-   IASparse. Strumento che interpreta i file registro di IAS e ne evidenzia i dettagli relativi ai parametri RADIUS (Remote Authentication Dial-In User Service).

-   Visualizzatore eventi. Strumento che consente di visualizzare, filtrare ed esportare i registri di monitoraggio di applicazioni, protezione e sistema di Windows.

-   MOM MMC. Console di MOM che controlla le informazioni, le avvertenze, gli avvisi, gli errori e gli errori critici nei file registro degli agenti gestiti dal server MOM.

-   PKIHealth. Strumento utilizzato per diagnosticare i problemi relativi ai punti di distribuzione CRL (CDP) e all'accesso alle informazioni dell'autorità (AIA) per tutte le CA all’interno dell’organizzazione.

#### Script personalizzati

Durante le diverse fasi di test definite dalla soluzione, sono stati utilizzati gli script personalizzati indicati di seguito.

-   ca\_setup.wsf. Contiene i comandi di processo necessari per la configurazione e la creazione dei Servizi certificati.

-   ca\_setup.vbs. Contiene il codice funzionale necessario per implementare i processi definiti nello script ca\_setup.wsf.

-   ca\_monitor.wsf. Contiene i comandi di processo necessari per il monitoraggio dei servizi CA.

-   ca\_monitor.vbs. Contiene il codice funzionale necessario per implementare i processi definiti nello script ca\_monitor.wsf.

-   ca\_operations.wsf. Contiene i comandi di processo necessari per le attività operative e di monitoraggio dei Servizi certificati.

-   ca\_operations.vbs. Contiene il codice funzionale necessario per implementare i processi definiti nello script ca\_operations.wsf.

-   constants.vbs. Contiene i parametri costanti per i Servizi certificati utilizzati in altri script.

-   helper.vbs. Contiene funzioni e variabili comuni utilizzate dagli script correlati a certificati, IAS e WLAN.

-   IASAccessPrep.txt. Questo file di testo contiene le righe di intestazione da aggiungere ai file registro IAS per convertire questi ultimi in file di Microsoft Access.

-   IASClientExport.bat. File batch che esporta la configurazione dei client RADIUS dal server IAS in un file di testo sull'unità A:\\.

-   IASClientImport.bat. File batch che importa nel server IAS la configurazione dei client RADIUS da un file di testo dell'unità A:\\.

-   IASExport.bat. File batch che esporta in un file di testo le configurazioni specifiche IAS.

-   IASImport.bat. File batch che importa nel server IAS le configurazioni specifiche IAS da un file di testo.

-   ias\_tools.wsf. Contiene i comandi di processo necessari per la configurazione dei server IAS.

-   ias\_tools.vbs. Contiene il codice funzionale necessario per implementare i processi definiti nello script ias\_tools.wsf script.

-   IAS\_Data.bat. File batch che contiene un comando necessario per la configurazione dei server IAS per la soluzione.

-   pkiparms.vbs. Contiene le costanti specifiche dell'utente utilizzate durante il processo di configurazione dei Servizi certificati.

-   wl\_tools.wsf. Contiene i comandi di processo necessari per la configurazione dei componenti WLAN.

-   wl\_tools.vbs. Contiene il codice funzionale necessario per implementare i processi definiti nello script wl\_tools.wsf script.

Tutti gli script indicati sono inclusi nel pacchetto disponibile per il download della soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Casi pratici di test

Questa sezione descrive in dettaglio i test utilizzati per verificare la soluzione e per assicurarne la rispondenza agli obiettivi fissati. La sezione include, inoltre, i criteri che consentono di determinare la riuscita o meno del caso pratico di test. I principali test elencati costituiscono un piccolo sottoinsieme della serie completa dei casi pratici di test. L'elenco completo dei casi pratici di test viene documentato in due fogli di calcolo di Microsoft Excel inclusi nel pacchetto disponibile per il download della soluzione (consultare i riferimenti ai file dei fogli di calcolo alla pagina successiva).

Gli scenari di test riportati nell'elenco seguente sono stati verificati dopo la creazione completa del laboratorio in base alle indicazioni incluse nella guida della soluzione. I computer e gli utenti del dominio sono stati aggiunti nei servizi certificati e nei gruppi di protezione dell'accesso senza fili appropriati. Gli utenti sono stati connessi alla rete con un collegamento cablato ed è stato eseguito l'accesso in modo da poter applicare correttamente i criteri di gruppo ai computer client senza fili.

Per convalidare la soluzione, sono stati eseguiti test di laboratorio sulla base dei seguenti scenari principali.

-   **Registrazione automatica dei certificati per utenti e computer**. I criteri di gruppo vengono applicati a utenti e computer quando l'utente accede al dominio con una connessione di rete cablata. I certificati di autenticazione di utenti e computer vengono rilasciati correttamente dal CA di emissione e i certificati sono disponibili negli archivi dei certificati personali del profilo utente e del computer.

-   **Certificati di CA principali e di emissione nell'archivio principale attendibile**. I criteri di gruppo vengono applicati a utenti e computer quando l'utente accede al dominio con una connessione cablata. Gli archivi dei certificati di utenti e computer vengono verificati mediante la console MMC Certificati; nella cartella Autorità di certificazione principale attendibili, viene verificata la presenza del certificato della CA principale. Viene inoltre verificata la presenza di un certificato della CA di emissione in Autorità di certificazione intermedie.

-   **Certificato di autenticazione del server IAS.** Dopo aver completato la creazione e aver aggiunto i server IAS nei gruppi e nelle unità organizzative (OU) appropriati, i server IAS sono stati riavviati (il riavvio era richiesto per assegnare ai computer una nuova appartenenza ai gruppi). Ogni server IAS riceve un nuovo certificato di autenticazione del server. Ciò è stato verificato mediante la console MMC Certificati in modo da visualizzare l'archivio dei certificati del computer.

-   **Certificati di CA di emissione e principali e CRL disponibili sul server Web.** Da Internet Explorer su un computer client, è stato eseguito l'accesso alla directory virtuale PKI del server Web per verificare che il client potesse visualizzare i certificati di CA di emissione e principali e i CRL. Questa verifica deve corrispondere alla posizione del protocollo HTTP (Hypertext Transfer Protocol) configurata nel certificato del client nella scheda **Dettagli**.

-   **Accesso senza fili alla rete mediante i certificati di autenticazione.** Dopo aver ricevuto i nuovi certificati di autenticazione validi per utenti e computer, la scheda di rete senza fili è stata inserita e la connessione cablata è stata rimossa. Dopo aver riavviato il computer, è stata eseguita l'autenticazione del computer alla rete WLAN che è stata verificata consultando il Registro eventi di sistema del server IAS. A questo punto, l'utente ha potuto eseguire l'accesso al dominio tramite la rete WLAN. L'autenticazione dell'utente alla rete WLAN è stata verificata mediante una voce del Registro eventi di sistema generata sul server IAS.

-   **Disponibilità del server IAS per utenti di filiali**. Se il servizio IAS di una filiale non è disponibile, gli utenti possono eseguire l'autenticazione su uno dei server IAS presenti nelle sedi centrali. Per questo test, è stato necessario impostare, nei punti di accesso senza fili della filiale, il server IAS della sede centrale come server IAS secondario. Il servizio IAS della filiale è stato quindi disattivato. In tal caso, gli utenti hanno potuto comunque eseguire l'autenticazione e connettersi alla rete WLAN. L'autenticazione è stata confermata consultando gli eventi di autenticazione memorizzati nel Registro eventi di sistema sul server IAS della sede centrale.

I dettagli sui diversi casi pratici di test eseguiti dal team incaricato per la soluzione sono descritti nelle sezioni seguenti.

#### Test di base

Questi test consentono di convalidare i servizi dell'infrastruttura di base e includono test di base sulla funzionalità di server e client ai quali si è fatto riferimento durante il test del sistema.

Per quanto riguarda i client, i test di base comprendono il test dei servizi di base del client, come l'autenticazione al dominio e l'accesso a file server, server Web e server di posta elettronica. I test di base vengono rieseguiti dopo ogni fase della soluzione creata per verificare che l'applicazione della configurazione della soluzione non determini problemi nella funzionalità del sistema esistente.

Per quanto riguarda i server, i test di base sono volti a verificarne il corretto funzionamento e a garantire che l'implementazione della soluzione non abbia alcun impatto negativo sul loro ruolo.

Per ulteriori informazioni sui casi pratici di test utilizzati per la fase dei test di base, fare riferimento al file Baseline Test Cases.xls incluso nella soluzione.

#### Test funzionali

Questi test sono ideati per verificare che sia possibile creare la soluzione come indicato nella documentazione e riportano la funzionalità prevista. I casi pratici dei test funzionali includono la verifica delle funzioni, dello stato e dell'interoperabilità di servizi e componenti PKI, IAS e WLAN come previsto nella guida.

Per ulteriori informazioni sui casi pratici di test utilizzati per la fase dei test funzionali, fare riferimento al file Functional & Operational Test Cases.xls incluso nella soluzione.

#### Test operativi

Questi test consentono di convalidare le operazioni, la manutenzione e l'amministrazione dei server della soluzione. Tali fattori sono documentati nelle procedure di gestione della Guida operativa descritte nel capitolo 11, “Gestione dell'infrastruttura a chiave pubblica”, e nel capitolo 12, “Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili”.

Per ulteriori informazioni sui casi pratici di test utilizzati per la fase dei test operativi, fare riferimento al file Functional & Operational Test Cases.xls incluso nella soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Criteri di rilascio

Il rilascio principale della soluzione è collegato alla gravità e alla priorità degli errori non risolti in base ai seguenti criteri:

-   Non sono presenti errori non risolti con gravità 1 o 2.

-   Non sono presenti errori non risolti con priorità 1 o 2 di qualsiasi livello di gravità.

-   Tutte le guide della soluzione sono prive di commenti e revisioni.

-   Tutti gli errori non risolti sono stati analizzati e suddivisi in categorie dal team.

-   Tutti i casi pratici di test eseguiti in laboratorio hanno avuto esito positivo.

-   Nell'ambito della soluzione, tutte le istruzioni non sono in contraddizione tra loro.

#### Classificazione degli errori

Nella tabella seguente vengono indicate le definizioni di gravità e priorità degli errori utilizzate in laboratorio.

**Table 13.1. Classificazione degli errori**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Valutazione</p></th>
<th><p>Definizione di gravità</p></th>
<th><p>Definizione di priorità</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>1</p></td>
<td style="border:1px solid black;"><p>Errori che determinano arresti anomali del sistema o perdita di dati.</p></td>
<td style="border:1px solid black;"><p>La soluzione deve essere individuata il più rapidamente possibile. L'errore impedisce l'ulteriore avanzamento nell'area.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>2</p></td>
<td style="border:1px solid black;"><p>Errori che determinano problemi per le funzioni principali o altri inconvenienti gravi. Il prodotto è soggetto ad arresti anomali in circostanze non chiarite.</p></td>
<td style="border:1px solid black;"><p>Il team deve individuare la soluzione prima del rilascio del prodotto.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>3</p></td>
<td style="border:1px solid black;"><p>Errori che determinano problemi per le funzioni secondarie o che influiscono negativamente sulla qualità.</p></td>
<td style="border:1px solid black;"><p>La soluzione può essere individuata qualora il tempo a disposizione lo consenta. Spesso si tratta di problemi banali. La soluzione può essere rinviata.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>4</p></td>
<td style="border:1px solid black;"><p>Errori tipografici, testo redatto in modo non chiaro o messaggi di errore visualizzati in campi con visibilità ridotta.</p></td>
<td style="border:1px solid black;"><p>Non definito.</p></td>
</tr>  
</tbody>  
</table>
  
#### Controllo dei risultati
  
Tutti i casi pratici di test sono stati superati con risultati positivi. Non sono stati riscontrati errori non risolti con gravità 1 e 2 e priorità 1 o 2. Questo dimostra che gli obiettivi fissati per i test sono stati soddisfatti e che la soluzione è pronta per il rilascio.
  
#### Informazioni diagnostiche
  
Per la risoluzione dei problemi durante il test, si sono rivelate utili le tecniche indicate di seguito.
  
-   Creare il valore {**DWORD** HKCU\\Software\\Microsoft\\Cryptography\\Autoenrollment\\AEEventLogLevel impostato su **0**}. In tal modo, la funzione di registrazione automatica utilizza il Registro eventi applicazioni. Creare la stessa chiave del Registro di sistema in HKLM per la registrazione del computer.
  
-   Assicurarsi che il segreto condiviso del punto di accesso senza fili sia identico a quello del server IAS e verificarne la correttezza (utilizzare la funzione di copia e incolla dal file dei segreti). In caso contrario, il punto di accesso non esegue l'autenticazione per il server IAS come client RADIUS e nei file registro degli errori del server IAS viene visualizzato
  
    -   un messaggio che indica la non validità dell'autenticazione
  
        o
  
    -   di un attributo di autenticazione del messaggio.
  
-   Se il server IAS crea nel registro un avviso con ID evento pari a 2 segnalando la mancata riuscita dell'autenticazione a causa di un nome utente sconosciuto o di una password errata, assicurarsi che il criterio di accesso remoto senza fili nel server IAS sia corretto. Verificare, inoltre, che l'utente sia stato aggiunto ai gruppi di protezione senza fili appropriati.
  
-   Se il server IAS crea nel registro un avviso con ID evento pari a 2 segnalando che la catena dei certificati è stata elaborata correttamente, ma che uno dei certificati CA risulta non attendibile per il provider criteri, assicurarsi che sia possibile convalidare il certificato del server IAS e dell'utente a fronte del certificato della CA di emissione. Assicurarsi, inoltre, che nell'archivio certificati dell'utente siano presenti i certificati validi della CA di emissione e della CA principale.
  
-   Se SChannel crea nel registro un avviso con ID evento pari a 36877 segnalando che il certificato ricevuto dall'applicazione client remota non è risultato valido, che il codice di errore è 0x80096004 e che i dati allegati includono il certificato del client, assicurarsi che i certificati dell'utente, utilizzati per l'autenticazione senza fili del computer, non siano scaduti o non siano stati revocati.
  
-   Per ulteriori informazioni diagnostiche, fare riferimento alle sezioni “Risoluzione dei problemi” riportate nei capitoli della Guida operativa.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
È possibile reperire ulteriori informazioni sui test nella Guida alla pianificazione, nella Guida alla creazione e nella Guida operativa. I collegamenti indicati di seguito, infine, offrono informazioni di riferimento utili per la risoluzione dei problemi durante i test.
  
-   Per informazioni sulla risoluzione dei problemi, vedere il white paper “[Troubleshooting Windows XP IEEE 802,11 Wireless Access](http://technet.microsoft.com/en-us/library/bb457017.aspx)” all'indirizzo http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/wifitrbl.mspx.
  
-   Per informazioni sulla registrazione automatica dei certificati in Windows XP, vedere il white paper “[Certificate Autoenrollment in Windows XP](http://technet.microsoft.com/en-us/library/bb456981.aspx)” all'indirizzo http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/certenrl.mspx.
  
-   Per informazioni sui miglioramenti dell'infrastruttura PKI, vedere il white paper “[PKI Enhancements in Windows XP Professional and Windows Server 2003](http://technet.microsoft.com/en-us/library/bb457034.aspx)” all'indirizzo http://www.microsoft.com/technet/prodtechnol/winxppro/plan/pkienh.mspx.
  
-   Per una panoramica dei componenti e della tecnologia di distribuzione senza fili in Windows XP, vedere l'articolo “[Windows XP Wireless Deployment Technology and Component Overview](http://technet.microsoft.com/en-us/library/bb457015.aspx)” all'indirizzo http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/wificomp.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
