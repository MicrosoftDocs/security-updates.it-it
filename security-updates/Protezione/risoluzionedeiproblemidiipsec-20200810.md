---
TOCTitle: Risoluzione dei problemi di IPsec
Title: Risoluzione dei problemi di IPsec
ms:assetid: 'd8d73542-5a15-4162-b0c3-5cbf7e1417e3'
ms:contentKeyID: 20200810
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536210(v=TechNet.10)'
---

Isolamento del server e del dominio tramite IPsec e criteri di gruppo
=====================================================================

### Capitolo 7: Risoluzione dei problemi di IPsec

Aggiornato: 16 febbraio 2005

Questo capitolo fornisce informazioni su come risolvere i problemi relativi alla protezione dei protocolli Internet (IPsec, Internet Protocol Security), quali quelli degli scenari di isolamento del server e del dominio, e si basa sull'esperienza e sui processi del team IT di Microsoft. Il presente capitolo fa riferimento, ove possibile, alle procedure esistenti di risoluzione dei problemi di Microsoft e alle relative informazioni.

Il supporto IT di Microsoft si basa su un modello a più livelli, nel quale l'help desk viene definito 1° livello di supporto. Le procedure di assegnazione ai livelli successivi consentono al personale dell'help desk di assegnare i problemi che richiedono l'intervento di specialisti.

Le procedure illustrate in questo capitolo fanno riferimento a tre livelli di supporto: 1°, 2° e 3°. Affinché le istruzioni siano per quanto possibile pratiche e concise, la maggior parte dei contenuti riguardano il 2° livello. Le istruzioni iniziali in merito al 1° livello vengono fornite affinché le organizzazioni possano stabilire rapidamente se il problema è correlato a IPsec e, in questo caso, generare le informazioni necessarie per facilitare il processo di risoluzione da parte del personale di supporto tecnico del 2° livello.

Le informazioni particolarmente dettagliate e complesse necessarie per la risoluzione dei problemi assegnati al 3° livello non rientrano nell'ambito della trattazione del presente capitolo. Nel caso in cui le informazioni fornite non consentano di risolvere i problemi relativi a IPsec, Microsoft consiglia di contattare il servizio di supporto tecnico Microsoft® per ulteriore assistenza.

Nel presente capitolo vengono forniti come riferimento numerosi strumenti, script e procedure di supporto utilizzati da Microsoft. Questi strumenti e raccomandazioni devono però essere adattati in modo da soddisfare le esigenze specifiche dell'organizzazione.

Quando si utilizza IPsec per la protezione del traffico di rete basato su protocolli TCP (Transmission Control Protocol) e UDP (User Datagram Protocol), le procedure e gli strumenti di risoluzione dei problemi tipici delle reti TCP/IP possono dimostrarsi inefficaci. Pertanto, è importante pianificare e mettere a punto tecniche di risoluzione dei problemi specifiche per IPsec che possano essere adottate in caso di problemi di comunicazione fra i computer che utilizzano (o tentano di utilizzare) IPsec.

##### In questa pagina

[](#efaa)[Livelli di supporto e assegnazione dei problemi](#efaa)
[](#eeaa)[Risoluzione dei problemi di 1° livello](#eeaa)
[](#edaa)[Preparazione alla risoluzione dei problemi di 2° livello](#edaa)
[](#ecaa)[Processo di risoluzione dei problemi relativi a IPsec](#ecaa)
[](#ebaa)[Risoluzione dei problemi di 3° livello](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Livelli di supporto e assegnazione dei problemi

All'interno di Microsoft, il supporto per l'isolamento del server e del dominio rientra nell'offerta standard e viene specificato nei contratti standard del livello di servizio (SLA, Service Level Agreement). Il supporto per l'isolamento viene fornito dai livelli seguenti:

-   **1° livello: help desk**. L'help desk è il livello iniziale che si occupa dei problemi relativi ai client aggiunti e non aggiunti a un dominio. Ha inoltre il compito di fornire il supporto necessario per i server gestiti dall'organizzazione IT centrale (altri server potrebbero essere gestiti da team dedicati alle applicazioni aziendali o a gruppi di prodotti). Il personale dell'help desk è stato addestrato a utilizzare una tassonomia e numerosi diagrammi di flusso che consentono di classificare i problemi relativi all'isolamento del server e del dominio.

    Durante la fase pilota della soluzione di isolamento di Microsoft, i problemi dei client sono stati assegnati al reparto Corporate IT Security. Tuttavia, dopo aver distribuito la soluzione nell'ambiente di produzione, i problemi relativi ai client sono stati gestiti dal team di supporto del 2° livello.

-   **2° livello: gestione dei data center, centri operativi per la rete globale, supporto per le applicazioni aziendali e supporto per messaggistica e collaborazione**. Questi gruppi sono team operativi che monitorano e gestiscono quotidianamente i servizi IT e le risorse correlate. Durante i progetti pilota di isolamento del server e del dominio, questi team hanno svolto il ruolo di primo livello dell'escalation per l'help desk e per il reparto Corporate IT Security per la risoluzione dei problemi e gli aspetti correlati ai server. In ogni gruppo è presente un esperto in materia di isolamento del server e del dominio e vengono fornite procedure dettagliate per la risoluzione dei problemi.

-   **3° livello: servizi per reti e infrastrutture Windows.** Nei progetti pilota di isolamento del server e del dominio, questo gruppo ha individuato un team di persone da specializzare nella risoluzione dei problemi dei componenti dell'architettura correlati alla soluzione, quali ad esempio IPsec, elaborazione dei pacchetti TCP/IP, account dei computer e diritti di accesso alla rete. All'interno di Microsoft, se è necessaria un'ulteriore escalation, il 2° livello lavora direttamente con i team di Windows Development fino alla risoluzione completa. Al di fuori di Microsoft, questo livello dovrebbe coinvolgere il servizio di supporto tecnico Microsoft, ove necessario.

La sezione seguente riassume le tecniche di risoluzione dei problemi che può utilizzare il personale dell'help desk.

[](#mainsection)[Inizio pagina](#mainsection)

### Risoluzione dei problemi di 1° livello

Questa sezione illustra il processo generale di risoluzione dei problemi relativi a IPsec utilizzato dal personale dell'help desk che fornisce il supporto di 1° livello. Solitamente, questo personale fornisce assistenza telefonica e tenta di diagnosticare i problemi in modalità remota.

#### Il problema è causato da IPsec?

L'help desk riceve presumibilmente chiamate del tipo: "Riuscivo a connettermi al server x fino a quando non è stato attivato IPsec" oppure "Ieri funzionava tutto, mentre oggi non riesco a stabilire la connessione". In base all'esperienza acquisita da Microsoft IT, la distribuzione di IPsec aumenta il numero di chiamate per tutti i tipi di problemi di connettività di rete e per incidenti di "accesso negato" perché gli utenti prestano maggiore attenzione ai comportamenti delle applicazioni e della rete. Di conseguenza, alcuni utenti pensano che il problema possa essere causato da IPsec e chiamano l'help desk. Il piano di implementazione dell'isolamento del server e del dominio deve pertanto includere un sistema di classificazione delle chiamate affinché il personale dell'help desk possa fornire report chiari in merito al volume e alla natura dei problemi correlati a IPsec.

Dopo aver ottenuto dal chiamante le informazioni di natura amministrativa del caso, il personale dell'help desk deve seguire un processo ben definito di risoluzione dei problemi. Poiché le configurazioni del criterio IPsec possono avere impatti diversi sulle comunicazioni e poiché il processo di distribuzione può richiedere numerosi giorni o settimane, è necessario elaborare un diagramma di flusso e mantenerlo aggiornato per ciascuna serie di modifiche implementate. È pertanto necessario che il processo di pianificazione coinvolga il personale responsabile dell'help desk.

L'obiettivo dell'help desk deve essere quello di categorizzare i problemi al fine di poter tentare soluzioni note. Se questi tentativi non dovessero risolvere il problema, il personale dell'help desk deve garantire il reperimento delle informazioni appropriate per poi assegnare il problema al supporto di 2° livello. L'help desk deve, ad esempio, essere in grado di identificare vari tipi di problemi nei modi seguenti:

-   **Connettività di rete**. Per testare i percorsi di rete, utilizzare i messaggi **ping** e **tracert** di ICMP (Internet Control Message Protocol).

-   **Risoluzione dei nomi**. Utilizzare **ping** *&lt;nome destinazione&gt;* e **nslookup**.

-   **Applicazioni**. Quando comunicano con la medesima destinazione, alcune applicazioni, quali **NetView**, funzionano, mentre altre no.

-   **Servizi**. Stabilire, ad esempio, se sul server è in esecuzione il servizio Routing e Accesso remoto (RRAS, Routing and Remote Access Service), che crea un criterio IPsec automatico in conflitto per L2TP.

-   **Computer del chiamante**. Stabilire se è in grado di accedere a un host o a specifici computer host di destinazione attendibili che vengono utilizzati dall'help desk per il testing e la diagnostica.

-   **Computer di destinazione**. Stabilire se il computer del chiamante è in grado di accedere a tutti i computer dell'help desk utilizzati per i test, ma non riesce ad accedere a uno specifico computer di destinazione.

A seconda dell'organizzazione, l'help desk può utilizzare Assistenza remota o Desktop remoto per connettersi al computer del chiamante. Le linee guida fornite nel presente capitolo non richiedono l'accesso remoto, ma potrebbero essere utili strumenti per il personale dell'help desk, da utilizzare in alternativa ai passaggi necessari per guidare il chiamante all'uso dello snap-in MMC (Microsoft Management Console) del monitor IPsec o di Visualizzatore eventi.

Negli scenari in cui si utilizza l'isolamento del server senza quello del dominio, il personale dell'help desk deve essere a conoscenza di quali server appartengono al gruppo di isolamento.

##### Assegnazione di competenze e livelli di gravità

Una delle prime domande a cui deve rispondere il supporto di 1° livello è: chi è coinvolto nel problema? Il personale di supporto deve essere in grado di stabilire se il problema è condiviso da altri utenti e, in questo caso, da quanti e in quali ubicazioni. Dovrà quindi verificare la portata del problema stesso. Ad esempio, compromette la connettività a un singolo server o causa problemi più ampi, quali accessi o autenticazioni non riusciti in segmenti più ampi della rete?

I problemi di connettività possono riguardare tecnologie diverse e numerosi livelli utilizzati per le comunicazioni in rete. Il personale del supporto tecnico deve conoscere i principi generali della comunicazione sulle reti Windows TCP/IP, nonché gli aspetti specifici riguardanti la presente soluzione. In questa sezione vengono esaminati i diversi tipi di problemi e gli aspetti tipici di ognuno di essi, che devono essere gestiti dal supporto di 1° livello.

-   **Problemi specifici del computer**. Le comunicazioni protette da IPsec si basano sulla mutua autenticazione dei computer tramite lo scambio di chiavi Internet (IKE, Internet Key Exchange). I computer che avviano la comunicazione e quelli che rispondono devono disporre di account di dominio validi e accedere ai controller di dominio per il dominio di appartenenza. Inoltre, per l'assegnazione dei criteri IPsec e i controlli di accesso alla rete è necessario che gli account dei computer siano inseriti nei gruppi appropriati del dominio. Altri aspetti specifici relativi ai computer possono interferire sul funzionamento di IPsec, fra i quali:

    -   Sistemi operativi con service pack, patch o configurazione della chiave del Registro errati

    -   Computer con alcuni software installati o particolari servizi in esecuzione

    -   Connessioni di rete che utilizzano un indirizzo IP specifico o comunicano utilizzando un particolare percorso di rete

    A seguito di queste particolari condizioni, alcuni computer potrebbero causare problemi di connettività.

    **Nota:** tutti gli strumenti di risoluzione dei problemi relativi a IPsec trattati nel presente capitolo richiedono i privilegi del gruppo degli amministratori locali.

-   **Problemi specifici del percorso di rete**. In una soluzione di isolamento del server e del dominio o in altre distribuzioni allargate di IPsec, è probabile che tutto il traffico TCP e UDP sia incapsulato. Conseguentemente, le periferiche di rete presenti sul percorso vedranno soltanto i protocolli IKE, IPsec e ICMP. Se si verificano problemi di rete nella trasmissione di questi tre protocolli fra l'origine e la destinazione, la comunicazione fra i due computer potrebbe interrompersi.

-   **Problemi specifici dell'utente**. La distribuzione di IPsec, ad esempio in uno scenario di isolamento del server e del dominio, può interferire con i diritti di accesso alla rete degli utenti del dominio. Il problema potrebbe ad esempio interessare soltanto gli utenti che non appartengono a un gruppo autorizzato ad accedere alla rete oppure un utente autorizzato potrebbe non riuscire a ottenere le credenziali di autenticazione Kerberos che contengono l'appartenenza al gruppo appropriato. Si potrebbero riscontrare delle differenze di comportamento fra utenti locali e del dominio o account di servizio.

Altre due caratteristiche della soluzione di isolamento del server e del dominio che tipicamente si riscontrano nelle distribuzioni aziendali di IPsec sono l'utilizzo di filtri di subnet, per definire gli intervalli di indirizzi utilizzati sulla rete interna, e l'applicazione di criteri IPsec basati sull'appartenenza a un dominio e a un gruppo, indipendentemente dalla posizione del computer sulla rete interna. Pertanto, se si verifica un problema legato alla configurazione dei filtri di subnet o al percorso di rete utilizzato dal computer specifico per connettersi ad altri computer, i problemi di connettività possono verificarsi solo su segmenti specifici della rete, quando si utilizza un certo indirizzo IP (ad esempio, un indirizzo wireless e non un indirizzo LAN) oppure soltanto su alcuni computer.

#### Diagrammi di flusso per la risoluzione dei problemi

I diagrammi di flusso per la gestione delle chiamate riportati nella presente sezione sono stati elaborati da Microsoft IT per facilitare la classificazione dei problemi di supporto IPsec di 1° livello. Oltre agli strumenti standard, due dei diagrammi di flusso fanno riferimento a uno script per l'aggiornamento del criterio IPsec, la cui descrizione è riportata nella sezione "Esempi di script di supporto" nelle pagine seguenti di questo capitolo.

La figura 7.1 è utile per la diagnosi iniziale e per individuare il tipo di problema:

-   **È un problema relativo alla connettività di rete?** In questo caso, tentare le procedure di base per la risoluzione dei problemi di rete. Se l'operazione non ha esito positivo, assegnare il problema al supporto di 2° livello.

-   **È un problema relativo alla risoluzione dei nomi?** In questo caso, tentare le procedure di base per la risoluzione dei problemi relativi alla risoluzione dei nomi. Se l'operazione non ha esito positivo, assegnare il problema al supporto di 2° livello.

-   **È un problema relativo all'applicazione?** In questo caso, assegnare il problema al supporto di 2° livello.

-   **È un problema relativo a IPsec sul computer del chiamante?** In questo caso, vedere la figura 7.2.

-   **È un problema relativo a IPsec sul computer di destinazione a cui il chiamante tenta di connettersi?** In questo caso, vedere la figura 7.3.  

    [![](images/Dd536210.SGFG0701(it-it,TechNet.10).gif "Dd536210.SGFG0701(it-it,TechNet.10).gif")](https://technet.microsoft.com/it-it/dd536210.sgfg0701_big(it-it,technet.10).gif)

    **Figura 7.1. Procedura di risoluzione dei problemi in caso di assenza di comunicazione con un computer di destinazione**

**Nota**: questo diagramma di flusso presuppone che IPsec sia in esecuzione sul computer del chiamante e che le zone di ricerca inversa del DNS siano configurate in modo da consentire il corretto funzionamento del comando ping.

La figura 7.2 ha lo scopo di facilitare l'identificazione dei problemi del computer del chiamante. Si noti che, oltre alla diagnostica, questo diagramma di flusso fa riferimento all'utilizzo dello script per l'aggiornamento dei criteri IPsec (vedere "Esempi di script di supporto" nelle pagine seguenti del presente capitolo), che potrebbe risolvere il problema senza necessariamente identificarlo. I passaggi della figura 7.2 facilitano l'individuazione dei seguenti problemi potenziali del computer del chiamante:

-   **È un problema relativo al servizio RRAS?** In questo caso, interrompere il servizio RRAS (se non è necessario) o assegnare il problema al supporto di 2° livello.

-   **È un problema relativo ai criteri?** In questo caso, provare ad aggiornare i criteri di gruppo e i criteri IPsec.

-   **È un problema relativo all'account di dominio?** In questo caso, creare un account di dominio per il computer del chiamante.

-   **Nessuno dei casi precedenti?** Se l'aggiornamento dei criteri IPsec e/o la creazione di un account di dominio non risolvono il problema, assegnarlo al supporto di 2° livello.

    [![](images/Dd536210.SGFG0702(it-it,TechNet.10).gif "Dd536210.SGFG0702(it-it,TechNet.10).gif")](https://technet.microsoft.com/it-it/dd536210.sgfg0702_big(it-it,technet.10).gif)

    **Figura 7.2. Risoluzione dei problemi relativi a IPsec del computer del chiamante - Problemi correlati**

La figura 7.3 ha lo scopo di facilitare l'identificazione dei problemi con uno specifico computer di destinazione. Si noti che anche questo diagramma di flusso fa riferimento all'utilizzo di uno script per l'aggiornamento dei criteri IPsec che potrebbe risolvere il problema senza necessariamente identificarlo. La figura 7.3 facilita l'individuazione dei seguenti problemi potenziali con il computer di destinazione (o il suo percorso):

-   **È un problema relativo al servizio RRAS?** In questo caso, assegnare il problema al supporto di 2° livello.

-   **È un problema relativo ai criteri IPsec?** In questo caso, provare ad aggiornare i criteri di gruppo e i criteri IPsec. Verificare quindi la connettività della rete.

-   **È un problema relativo alla connettività di rete?** In questo caso, assegnare il problema al supporto di 2° livello.

-   **È un problema relativo ai diritti di accesso?** In questo caso, assegnare il problema al supporto di 2° livello.

    [![](images/Dd536210.SGFG0703(it-it,TechNet.10).gif "Dd536210.SGFG0703(it-it,TechNet.10).gif")](https://technet.microsoft.com/it-it/dd536210.sgfg0703_big(it-it,technet.10).gif)

    **Figura 7.3. Risoluzione dei problemi relativi a IPsec del computer di destinazione – Problemi correlati**

Quando il personale di supporto del 1° livello ha completato i passaggi dei diagrammi di flusso, lo stato del problema sarà uno dei seguenti:

-   **Risoluzione compresa**. Questo stato indica che il problema è stato risolto e che la relativa causa può essere stata stabilita.

-   **Risoluzione non chiara.** Questo stato indica che il problema è stato risolto, ma che la sua causa non è stata completamente compresa. L'aggiornamento dei criteri IPsec potrebbe, ad esempio, risolvere il problema senza però necessariamente spiegare perché era stato applicato un criterio errato o non era stato applicato alcun criterio.

-   **Nessuna risoluzione**. Questo stato indica che il problema è ancora presente, ma che ne sono stati individuati i probabili aspetti per poi assegnarlo al supporto di 2° livello.  

#### Prevenzione degli attacchi ai soggetti vulnerabili

In una soluzione di isolamento, il personale dell'help desk potrebbe individuare aree specifiche dell'ambiente IT non protette da IPsec, ad esempio i computer che rientrano nell'elenco di esenzioni. Queste aree potrebbero non essere utilizzate per proteggere informazioni sensibili poiché in altre soluzioni di protezione queste informazioni critiche sono solitamente accessibili solo a personale di supporto di livello superiore. Per questa ragione, il personale dell'help desk deve essere addestrato a rilevare e a resistere agli attacchi rivolti a persone vulnerabili.

In questo tipo di attacchi, una persona non attendibile tenta di acquisire informazioni sulla protezione implementata e sui punti deboli, spesso sfruttando semplicemente la propensione alla fiducia dell'essere umano. Il personale dell'help desk deve controllare attentamente le seguenti informazioni:

-   **Membri dell'elenco di esenzioni**. L'elenco degli indirizzi IP inclusi nell'elenco di esenzioni dei filtri è probabilmente a disposizione degli amministratori locali su tutti gli host attendibili tramite lo snap-in MMC del monitor IPsec oppure tramite la visualizzazione del criterio IPsec archiviato nella cache del Registro di sistema locale. Inoltre, le impostazioni di protezione utilizzate dall'organizzazione possono consentire l'accesso in lettura della cache agli utenti non amministrativi. Quando l'implementazione dell'isolamento del dominio è completata, i pirati informatici devono effettuare una scansione della rete per individuare i computer esentati in grado di rispondere alle richieste di connessione TCP e UDP. Si noti che i server DNS, DHCP e WINS sono facilmente identificabili in base alla configurazione DHCP e che i controller di dominio sono facili da individuare tramite una query DNS o LDAP (Light Directory Access Protocol) UDP.

-   **Computer dell'organizzazione che non partecipano alla soluzione di isolamento**. Alcuni domini o tipi di server possono, ad esempio, non essere inclusi nella soluzione.

-   **Computer che utilizzano l'isolamento del server o che richiedono un controllo dell'accesso a livello di computer**. I server su cui risiedono le informazioni più sensibili sono solitamente quelli su cui vengono adottate le misure di protezione più rigide.

-   **Utenti amministratori o che svolgono ruoli speciali nell'organizzazione IT**. In alcuni casi, gli indirizzi di posta elettronica vengono utilizzati come nomi di computer o parti dei nomi di computer, rivelando quindi nomi di accesso o indirizzi di posta elettronica.

-   **Subnet utilizzate per scopi specifici o da alcune organizzazioni**. Se questa informazione è nota, un pirata informatico può concentrare il proprio attacco sulle parti più sensibili e importanti della rete.

-   **Altre misure di protezione a livello di rete**. Per i pirati informatici è, ad esempio, molto utile sapere se esistono firewall, se i filtri dei router permettono un certo tipo di traffico o se si utilizzano sistemi di rilevamento delle intrusioni.

Il personale dell'help desk deve, inoltre, essere addestrato a operare con la massima cautela quando il chiamante chiede di collegarsi all'indirizzo IP del loro computer per analizzare un problema, ad esempio, se un pirata informatico chiede di connettersi al loro computer mediante condivisione file, Desktop remoto, Telnet o altri protocolli di rete. Se un addetto dell'help desk stabilisce una connessione non protetta da IPsec, il computer del pirata informatico potrà acquisire informazioni sulla password o (in alcuni casi, con Telnet) appropriarsi della password. Questa situazione può verificarsi perché alcuni protocolli di rete dei client non eseguono prima l'autenticazione e non stabiliscono una relazione di trust avanzata con il computer di destinazione oppure non richiedono protezioni avanzate della password prima di rivelare l'identità dell'utente o informazioni relative alla password.

#### Esempi di script di supporto

Nella maggior parte degli scenari di risoluzione dei problemi, è possibile determinare rapidamente la soluzione dopo aver acquisito le informazioni corrette. Queste informazioni sono reperibili tramite vari strumenti di Windows, quali ad esempio quelli riportati nei diagrammi di flusso. Nella soluzione della Woodgrove Bank, sono stati sviluppati numerosi script che forniscono informazioni chiave e non richiedono una conoscenza dettagliata del loro funzionamento e della sintassi da parte del personale di supporto del 1° livello. Questi script sono disponibili scaricando questa guida nella cartella Strumenti e modelli.

##### Script disponibili per il supporto di 1° livello

Se l'utente è un amministratore locale, il personale dell'help desk può richiedere l'esecuzione di uno dei tre script forniti con questa soluzione. Questi script sono esempi delle versioni personalizzate utilizzate per l'ambiente della Woodgrove Bank illustrato in questa guida. Vengono descritti nel presente capitolo per illustrare come utilizzare gli script per facilitare il processo di risoluzione dei problemi.

**Nota**: questi script sono esempi testati, ma non sono supportati da Microsoft. Devono essere utilizzati come base per sviluppare una soluzione personalizzata per l'organizzazione specifica.

###### IPsec\_Debug.vbs

Oltre a fornire informazioni di debug, questo script può risolvere alcuni problemi. Arresta e riavvia il servizio IPsec (eliminando tutte le associazioni di protezione di IKE e IPsec correnti), esegue un aggiornamento forzato dei criteri di gruppo per ricaricare il criterio IPsec corrente assegnato al dominio dal servizio Active Directory® e aggiorna la cache dei criteri. Al fine di evitare la perdita di connettività per le sessioni di Desktop remoto, è necessario scaricare lo script sul computer del chiamante ed eseguirlo localmente tramite un account con privilegi amministrativi. Per eseguire lo script dal prompt dei comandi, utilizzare la sintassi seguente:

```
cscript IPsec_Debug.vbs
```  

Lo script esegue le funzioni seguenti:

-   Identificazione della versione del sistema operativo

-   Richiamo di **Detect\_IPsec\_Policy.vbs**

-   Incremento del livello di registrazione dei criteri di gruppo

-   Incremento del livello di registrazione del protocollo di autenticazione Kerberos versione 5

-   Rimozione dei ticket del protocollo Kerberos correnti

-   Aggiornamento dei criteri di gruppo

-   Attivazione della registrazione IPsec

-   Esecuzione dei test PING e SMB (NetView)

-   Rilevamento delle versioni dei file IPsec

-   Esecuzione di test di diagnostica dei criteri e della rete

-   Copia degli eventi IPsec 547 in un file di testo

-   Disattivazione della registrazione IPsec

-   Ripristino della registrazione del protocollo Kerberos

-   Ripristino della registrazione dei criteri di gruppo

Questo script abilita, inoltre, tutti i registri correlati a IPsec per la risoluzione dei problemi del 2° livello di supporto.

###### Detect\_IPsec\_Policy.vbs

Questo script determina se il computer sta eseguendo il criterio IPsec corretto, verificando nella cache del Registro di sistema locale le informazioni sulla versione del criterio IP di dominio. Per eseguire lo script dal prompt dei comandi, utilizzare la sintassi seguente:

```
cscript Detect_IPsec_Policy.vbs
```  

**Nota:** questo script viene richiamato anche da **IPsec\_Debug.vbs** e quindi non deve essere eseguito se quest'ultimo è già stato completato.

###### Refresh\_IPsec\_Policy.vbs

È lo script di aggiornamento dei criteri IPsec, già menzionato nei diagrammi di flusso per la risoluzione dei problemi. Aggiorna i ticket del protocollo di autenticazione Kerberos e i criteri di gruppo e potrebbe risolvere il problema, se questo è causato da un'assegnazione errata dei criteri IPsec o da un errore di download dei criteri di gruppo. Per eseguire lo script dal prompt dei comandi, utilizzare la sintassi seguente:

```
cscript Refresh_IPsec_Policy.vbs

```  

#### Assegnazione ai livelli successivi

Quando il personale dell'help desk deve assegnare un potenziale problema di IPsec a un livello successivo, insieme alla richiesta di assistenza, deve acquisire e trasferire le informazioni seguenti:

-   File di registro generati con lo script **IPsec\_Debug.vbs**.

-   Nome del computer del chiamante affinché il livello di supporto successivo possa identificare il file di registro generato dallo script.

-   Computer di destinazione a cui viene negato l'accesso affinché il problema possa essere assegnato al gruppo di supporto appropriato.

Gli scenari di isolamento del server spesso dispongono del proprio team di supporto addetto alla verifica delle appartenenze ai gruppi di accesso alla rete.  

[](#mainsection)[Inizio pagina](#mainsection)

### Preparazione alla risoluzione dei problemi di 2° livello

Al supporto di 2° livello, sono assegnati due ruoli principali. In primo luogo, quale destinatario delle assegnazioni del 1° livello, il 2° livello deve convalidare le informazioni e verificare i passaggi eseguiti dal 1° livello, accertandosi che nessun passaggio della procedura di risoluzione dei problemi sia stato saltato. A questo riguardo, il 2° livello deve verificare che il problema assegnatogli sia effettivamente causato da IPsec e che non sia stato commesso un errore di diagnosi. In secondo luogo, in qualità di tecnici specializzati nelle reti, il personale del 2° livello deve essere in grado di utilizzare le proprie competenze ed esperienze (elencate nella sezione seguente) per risolvere positivamente il problema, tramite l'analisi dei registri e senza acquisire il controllo amministrativo del computer. I registri acquisiscono però soltanto informazioni, mentre gli interventi correttivi richiedono l'accesso con privilegi amministrativi. Non è necessario che l'addetto al supporto del 2° livello sia un amministratore di dominio né che sia in grado di modificare il criterio IPsec di dominio o le appartenenze ai gruppi dei computer.

#### Competenze del supporto di 2° livello

Il personale che fornisce il supporto IPsec di 2° livello deve possedere competenze ed esperienza nelle seguenti aree:

-   **Criteri di gruppo**. Conoscenza di quali criteri devono essere assegnati e delle modalità di assegnazione, nonché competenze sufficienti per svolgere le seguenti attività:

    -   Controllo degli elenchi di controllo di accesso (ACL, Access Control List) sugli oggetti Criteri di gruppo (GPO, Group Policy Object)

    -   Controllo delle impostazioni dei GPO

    -   Controllo delle appartenenze a gruppi di computer e utenti

-   **Software di terze parti utilizzato dall'organizzazione**.

-   **Identificazione degli errori di autenticazione**.

    -   Capacità di verificare gli account di dominio dei computer utilizzando le utilità **netdiag** e **nltest**.

-   **Configurazione di IPsec**. Competenze sufficienti per svolgere le seguenti attività:

    -   Verifica delle configurazioni dei filtri IPsec

    -   Ricaricamento del criterio di dominio IPsec

    -   Disattivazione totale di IPsec o soltanto del criterio di dominio per utilizzare il criterio locale a scopo di test

    -   Risoluzione dei problemi del processo di negoziazione IKE di IPsec e dei protocolli di protezione

-   **Reti**. Competenze sufficienti per svolgere le seguenti attività:

    -   Risoluzione dei problemi relativi allo stack del protocollo di rete su un computer host

    -   Comprensione e analisi delle informazioni acquisite mediante le tracce di rete

    -   Risoluzione dei problemi dei percorsi di rete, inclusi il rilevamento dell'MTU nel percorso TCP e le soluzioni di accesso remoto alla rete privata virtuale (VPN, Virtual Private Network).

#### Aspetti inerenti all'utilizzo di IPsec

Come indicato nella sezione precedente, il personale di supporto del 2° livello per le soluzioni di isolamento del server e del dominio deve essere a conoscenza di tutti i dettagli inerenti le comunicazioni protette da IPsec, ma deve anche saper individuare problemi correlati ad altre tecnologie.

Affinché fra due computer si stabilisca una comunicazione protetta da IPsec, entrambi i computer devono utilizzare un criterio IPsec compatibile. Un criterio IPsec potrebbe, ad esempio, bloccare la comunicazione se il computer remoto non dispone di un criterio IPsec appropriato. Nonostante questo aspetto possa essere comprensibile e accettabile durante la distribuzione di una modifica dei criteri, potrebbe non risultare immediatamente evidente se interrompe la connettività di rete con uno o più computer o genera avvisi o errori delle applicazioni. Nel peggiore dei casi, l'amministratore potrebbe assegnare per errore a tutti i membri del dominio un criterio IPsec che blocca *tutto* il traffico. Se l'errore non viene immediatamente compreso e corretto con un'assegnazione appropriata che si replichi rapidamente dopo quella originaria, non sarà facile interrompere la replica del criterio errato. Questo tipo di errore crea un situazione in cui, per utilizzare il servizio IPsec, è necessaria la comunicazione fra un client e un controller di dominio. Poiché, però, l'autenticazione utilizzata in questa soluzione si basa sul protocollo Kerberos, tutti i client che ereditano il criterio errato non saranno in grado di completare la procedura di accesso poiché non potranno ottenere il ticket Kerberos necessario per proteggere le comunicazioni. Gli amministratori dovranno, quindi, pianificare con attenzione le modifiche dei criteri e accertarsi di predisporre le misure di sicurezza procedurali che possano evitare questo tipo di situazione.

Le informazioni di base sulla risoluzione dei problemi relativi a TCP/IP sono riportate nelle guide alla risoluzione dei problemi elencate nella sezione "Ulteriori informazioni" alla fine del presente capitolo. Molte delle procedure a cui si fa riferimento in queste guide funzionano però soltanto se IPsec assicura la connettività. Se IKE o IPsec non funzionano, la maggior parte delle procedure e degli strumenti risulterà probabilmente inefficace. In uno scenario di isolamento del server e del dominio, alcune delle procedure documentate nelle guide di supporto potrebbero addirittura non funzionare affatto, anche se IPsec assicura la connettività. Per garantire un'azione sempre efficace negli ambienti di isolamento del server e del dominio, l'organizzazione di supporto deve pianificare l'aggiornamento e la personalizzazione degli strumenti e delle procedure di risoluzione dei problemi. Poiché le modalità di distribuzione dei criteri IPsec per controllare e migliorare la protezione del traffico sono numerose, è improbabile che le organizzazioni possano fare affidamento esclusivamente sulle procedure esistenti e su un toolkit generico.

È molto importante che il personale di supporto possa fare riferimento a esempi documentati dei risultati che possono produrre gli strumenti di risoluzione dei problemi di rete sviluppati in un ambiente di prova in cui l'isolamento del server e del dominio o altre distribuzioni di IPsec funzionano correttamente. In molti casi, gli strumenti di diagnostica della rete non rispettano i ritardi di tre secondi necessari per il passaggio alla modalità non crittografata né i brevi ritardi necessari per la negoziazione IKE iniziale delle associazioni di protezione (SA, Security Association) di IPsec. Per questa ragione, tali strumenti potrebbero visualizzare un risultato durante l'esecuzione iniziale e un risultato diverso se eseguiti alcuni secondi dopo. Inoltre, nei casi in cui l'accesso alla rete viene deliberatamente negato da IPsec, questi strumenti segnaleranno degli errori. Il tipo di errore dipenderà dallo strumento e dall'ambiente IPsec.

**Nota**: nella sezione dedicata al 1° livello, sono stati utilizzati i termini *chiamante* e *destinazione* per facilitare la risoluzione dei problemi più comuni da parte del personale di supporto. Nella sezione riguardante il 2° livello, è preferibile utilizzare i termini IPsec *iniziatore* e *risponditore* per rendere più chiari i processi avanzati di risoluzione dei problemi. Nelle sezioni seguenti di questo capitolo verranno utilizzati questi termini di IPsec.

##### Criteri di gruppo e appartenenze ai gruppi

Il criterio IPsec basato sul dominio dipende dai criteri di gruppo e dal download dei GPO. In caso di errori del sistema Criteri di gruppo del client nel rilevamento delle modifiche dei GPO o nel relativo processo di downloading, la connettività IPsec potrebbe risultarne compromessa. Se l'assegnazione dei criteri di gruppo è controllata in base all'appartenenza a un'unità organizzativa (OU, Organizational Unit) e gli account dei computer vengono inavvertitamente spostati su una diversa UO, eliminati o ricreati in una UO errata, potrebbe venire assegnato un criterio IPsec inadeguato.

Questa soluzione utilizza gruppi di protezione del dominio per controllare l'assegnazione dei criteri e l'accesso alla rete. L'appartenenza al gruppo è contenuta nei ticket di autenticazione del protocollo Kerberos versione 5 (sia TGT che di servizio) che hanno durate moderatamente lunghe. Gli amministratori dovranno, quindi, calcolare il tempo necessario ai computer per ricevere le nuove credenziali dei ticket Kerberos TGT e di servizio che contengono gli aggiornamenti delle appartenenze ai gruppi. Il protocollo Kerberos rende estremamente difficile stabilire se i ticket Kerberos per un computer contengono le appartenenze ai gruppi appropriati. Questa difficoltà è "voluta" poiché tutte le informazioni sulle appartenenze ai gruppi sono memorizzate in forma crittografata all'interno del ticket. L'appartenenza al gruppo deve, quindi, essere determinata utilizzando le informazioni del servizio directory e non quelle dei ticket stessi.

##### Autenticazione Kerberos

La configurazione di isolamento del server e del dominio utilizza il protocollo Kerberos versione 5 per l'autenticazione IKE. Poiché questo protocollo richiede che la connettività di rete sia presente e che il servizio DNS e dei controller di dominio sia disponibile, la mancanza di connettività rende impossibile l'autenticazione Kerberos e arresta IKE (IKE cessa di funzionare in caso di interruzione di Kerberos). Conseguentemente, i problemi di connettività fra un computer A e un computer B potrebbero essere causati da blocchi della connettività di rete fra il computer A e un computer C, derivanti dal fatto che il protocollo Kerberos non è in grado di completare l'autenticazione con un controller di dominio. In situazioni come queste, le informazioni registrate negli eventi 547 dei registri di controllo e protezione di Windows solitamente sono le migliori indicazioni per individuare l'origine del problema.

##### Traffico in ingresso protetto da IPsec

Questa soluzione di isolamento del server e del dominio prevede comunicazioni protette da IPsec per l'accesso in ingresso. Questo requisito fa si che gli strumenti di monitoraggio remoto, eseguiti su computer non attendibili o su periferiche di monitoraggio della rete dedicate, rilevino che il computer non è contattabile. Se non è possibile aggiungere questi computer o periferiche a un ambiente "attendibile", essi non potranno svolgere la loro funzione di monitoraggio, a meno che alla configurazione non vengano aggiunte esenzioni specifiche. La risoluzione dei problemi è complicata dal fatto che potrebbe essere necessario che IPsec si connetta a un host attendibile, il che significa che un amministratore potrebbe non essere in grado di connettersi a un host attendibile e di interrompere il servizio IPsec senza perdere la connettività. Se il criterio IPsec dell'amministratore consente il passaggio alla modalità non crittografata, l'interruzione del servizio sul computer remoto avverrà dopo un ritardo di tre o quattro secondi. Tuttavia, l'interruzione del servizio IPsec su un computer remoto comporta l'eliminazione di tutte le SA IPsec utilizzate da tutti gli altri computer connessi. Se questi computer non sono in grado di passare alla modalità non crittografa, la comunicazione si interromperà e le connessioni TCP andranno in timeout. Poiché le interruzioni improvvise delle comunicazioni TCP possono corrompere i dati delle applicazioni, l'interruzione del servizio IPsec deve essere utilizzata soltanto come ultima opzione del processo di risoluzione dei problemi. Prima di interrompere il servizio IPsec, preparare il computer all'arresto affinché tutti gli utenti e le applicazioni possano terminare correttamente le comunicazioni.

##### Aspetti relativi alla direzione delle comunicazioni

Un tipico scenario di risoluzione dei problemi è quello di comunicazione corretta in una direzione e non in quella inversa. L'autenticazione IKE tipicamente richiede la mutua autenticazione fra i computer. Se un computer non riesce a ottenere un ticket Kerberos, quando avvia la modalità principale IKE per un computer remoto, IKE si arresta. Questa situazione può verificarsi se il client Kerberos del computer che ha avviato la comunicazione non è riuscito ad accedere a un controller di dominio nel dominio del computer di destinazione. Se i computer sono membri di domini non reciprocamente attendibili (trust bidirezionale), le negoziazioni in modalità principale IKE verranno completate quando è uno dei due computer ad avviare la comunicazione e falliranno quando invece avvia la comunicazione l'altro computer. Analogamente, i diritti di accesso alla rete in ingresso potrebbero essere diversi fra un computer e l'altro. È possibile che la negoziazione IKE in modalità principale e rapida fallisca in una direzione non solo per queste ragioni, ma anche se le configurazioni dei criteri IPsec non sono compatibili per entrambe le parti.

I firewall basati su host che intercettano il traffico sopra il livello IPsec possono applicare la direzionalità alle connessioni. Alcuni firewall basati su host intercettano invece il traffico sotto il livello IPsec. Dopo aver stabilito la comunicazione, il traffico protetto da IPsec potrebbe essere consentito in entrambe le direzioni per un certo periodo di tempo.

Se il router o il firewall svolgono un'efficace azione di filtro basata sullo stato, la reimpostazione delle chiavi di IKE o il flusso del traffico IPsec potrebbero risultare bloccati senza alterare altri protocolli di diagnostica, quali ad esempio ICMP. Le porte TCP e UDP potrebbero non essere accessibili su un computer perché un servizio non è in funzione o perché una periferica che opera sopra il livello IPsec (ad esempio, Windows Firewall o un router di rete) blocca l'accesso.

##### Risoluzione dei problemi tramite tracce di rete e percorsi di rete avanzati

Gli errori della negoziazione IKE spesso fanno sì che il computer su cui si è verificato il problema cessi di rispondere alla negoziazione oppure, in alcuni casi, che ripeta l'invio dell'ultimo messaggio "buono" fino a quando non viene esaurito il limite di tentativi. IKE deve essere in grado di inviare datagrammi UDP frammentati che contengano i ticket Kerberos poiché questi pacchetti spesso sono di dimensioni superiori all'unità massima di trasmissione nel percorso (PMTU, Path Maximum Transmission Unit) per l'indirizzo IP di destinazione. Se la frammentazione non è adeguatamente supportata, questi frammenti possono venire scartati dalle periferiche di rete lungo un percorso specifico. Inoltre, la rete potrebbe non trasferire correttamente i pacchetti del protocollo IPsec o i frammenti dei pacchetti. L'integrazione di IPsec con TCP consente a quest'ultimo di ridurre le dimensioni dei pacchetti per contenere le intestazioni IPsec. Tuttavia, la negoziazione TCP delle dimensioni massime del segmento (MSS, Maximum Segment Size) durante l'handshake TCP non prende in considerazione il sovraccarico imposto da IPsec. Di conseguenza, esiste l'ulteriore necessità di rilevare la PMTU di ICMP sulla rete al fine di assicurare una corretta comunicazione TCP protetta da IPsec. Per questa ragione, la risoluzione dei problemi di connettività potrebbe rendere necessaria l'acquisizione di tracce di rete da una o entrambe le parti della comunicazione, nonché dei relativi registri.

Il personale addetto al supporto tecnico deve sapere come interpretare le tracce di rete e, inoltre, comprendere la negoziazione IKE. Sui server dovrà essere installato il software Windows Network Monitor. Windows 2000 Network Monitor esegue l'analisi di AH e IKE di IPsec. Windows Server 2003 include il supporto per l'analisi di ESP senza crittografia di IPsec, l'analisi ESP quando la crittografia viene delegata e l'analisi dell'incapsulamento UDP-ESP utilizzato per l'attraversamento del NAT.

#### Toolkit per la risoluzione dei problemi

Prima di avviare il processo di risoluzione dei problemi, è importante individuare le utilità che consentono di estrarre le informazioni di supporto per il processo stesso. Questa sezione non si pone come obiettivo quello di duplicare le informazioni contenute nella Guida di Windows 2000, Windows XP o Windows Server 2003 o quelle riportate nella pagina [Troubleshooting tools](http://www.microsoft.com/resources/documentation/windowsserv/2003/standard/proddocs/en-us/sag_ipsec_tools.asp) del sito Web Microsoft Windows Server™ 2003 all'indirizzo www.microsoft.com/resources/documentation/
.WindowsServ/2003/standard/proddocs/en-us/
sag\_IPSec\_tools.asp.

Le informazioni dettagliate sugli strumenti sono riportate in questa sezione soltanto se non sono facilmente reperibili nella pagina degli strumenti sopra indicata o quando è utile avere a disposizione riepiloghi delle varie versioni dei sistemi operativi.

##### Snap-in MMC Gestione criteri di protezione IP

Lo snap-in MMC Gestione criteri di protezione IP consente di creare e gestire criteri IPsec locali o archiviati in Active Directory. Può essere utilizzato anche per modificare i criteri IPsec sui computer remoti. Lo snap-in MMC Gestione criteri di protezione IP è incluso nei sistemi operativi Windows Server 2003, Windows XP, Windows 2000 Server e Windows 2000 Professional e può essere utilizzato per visualizzare e modificare i dettagli dei criteri IPsec, i filtri, gli elenchi filtri e le operazioni filtro, nonché per assegnare e annullare le assegnazioni di criteri IPsec.

##### Snap-in MMC Monitor di protezione IP

Lo snap-in MMC Monitor di protezione IP mostra le statistiche IPsec e le SA attive. Viene inoltre utilizzato per visualizzare informazioni sui seguenti componenti di IPsec:

-   Modalità principale e rapida IKE

-   Criteri IPsec a livello locale o di dominio

-   Filtri IPsec applicati al computer  

Nonostante questo snap-in sia incluso in Windows XP e in Windows Server 2003, esistono differenze a livello di funzionalità e interfaccia fra i due sistemi operativi. Inoltre, la versione per Windows Server 2003 offre le seguenti funzionalità aggiuntive:

-   Fornisce dettagli sul criterio IPsec attivo, inclusi il nome, la descrizione, la data di ultima modifica, l'archivio, il percorso, la UO e il nome dell'oggetto Criteri di gruppo. Per ottenere le stesse informazioni in Windows XP, è necessario utilizzare lo strumento Ipseccmd della riga di comando (descritto in questa sezione).

-   Fornisce statistiche separate per le modalità principale e rapida in cartelle ubicate sotto ciascuna modalità invece che in una sola visualizzazione.

    **Nota:** in Windows 2000, Monitor di protezione IP è un programma eseguibile in modalità autonoma (IPsecmon.exe) dotato della propria interfaccia grafica. Le descrizioni dello strumento e delle modalità di utilizzo sono riportate nell'articolo numero 257225 "[Procedura di base per la risoluzione di problemi IPSec in Windows 2000](http://support.microsoft.com/kb/257225)" della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/kb/257225.

Per questo snap-in, è disponibile un aggiornamento per Windows XP che fa parte dell'aggiornamento descritto nell'articolo numero 818043 "[Aggiornamento L2TP/IPSec NAT-T per Windows XP e per Windows 2000](http://support.microsoft.com/?kbid=818043)" della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/?kbid=818043. Questo aggiornamento consente di visualizzare i computer che eseguono Windows Server 2003 in Windows XP. Lo snap-in MMC Monitor di protezione IP aggiornato consente anche di leggere le funzionalità avanzate create in Windows Server 2003 (ad esempio, informazioni sul gruppo Diffie-Hellman 2048, il mapping dei certificati e i filtri dinamici), ma non di modificarle. Per ulteriori informazioni, consultare il suddetto articolo della Microsoft Knowledge Base.

##### Netsh

Netsh è un'utilità di script della riga di comando che consente di visualizzare o modificare la configurazione di rete, sia in locale che in remoto. Netsh è disponibile per Windows 2000, Windows XP e Windows Server 2003. Tuttavia, in Windows Server 2003 questa utilità è stata migliorata al fine di fornire funzionalità di diagnostica e di gestione IPsec. I comandi di Netsh per IPsec sono disponibili solo per Windows Server 2003 e sostituiscono Ipseccmd in Windows XP e Netdiag nella versione utilizzata in Windows 2000.

##### Ipseccmd

Ipseccmd è una riga di comando alternativa allo snap-in MMC Monitor di protezione IP. È disponibile solo per Windows XP, mentre in Windows XP Service Pack 2 sono disponibili ulteriori funzionalità per questo strumento.

L'utilità Ipseccmd deve essere installata dalla cartella Support/Tools del CD di Windows XP. Con Windows XP SP2, è disponibile una versione aggiornata, che deve essere installata dalla cartella Support/Tools del CD di Windows XP SP2. Le versioni precedenti a SP2 non funzionano sui computer aggiornati e la versione aggiornata non funziona sui computer in cui non è installato SP2.

L'utilità Ipseccmd aggiornata include le seguenti funzionalità:

-   Attivazione e disattivazione dinamica della registrazione IKE

-   Visualizzazione di informazioni sul criterio assegnato

-   Possibilità di creare un criterio IPsec permanente

-   Possibilità di visualizzare il criterio IPsec assegnato e attivo

Per ulteriori informazioni sull'utilità Ipseccmd aggiornata, consultare l'articolo numero 818043 della Microsoft Knowledge Base citato in precedenza.

Per visualizzare tutte le impostazioni dei criteri IPsec e le statistiche della diagnostica, utilizzare la sintassi seguente:

```
ipseccmd show all
```  

Per visualizzare i criteri IPsec assegnati e attivi (locali o di Active Directory), utilizzare la sintassi seguente:

```
ipseccmd show gpo
```  

**Nota:** questo comando funziona solo con la versione per SP2.

Per attivare la registrazione di debug in Windows XP SP2, utilizzare la sintassi seguente:

    ipseccmd set logike  (non è necessario riavviare il servizio IPsec)

Per disattivare la registrazione di debug, utilizzare la sintassi seguente:

    ipseccmd set dontlogike  (anche in questo caso, non è necessario riavviare il servizio IPsec)

**Nota:** per attivare la registrazione Oakley in Windows XP SP2, è possibile utilizzare soltanto Ipseccmd; i comandi precedenti non funzionano con le versioni precedenti a SP2.

##### Netdiag

Netdiag è uno strumento di diagnostica della riga di comando che consente di testare la connettività e la configurazione di rete, comprese le informazioni IPsec. Netdiag è disponibile in Windows 2000, Windows XP e Windows Server 2003, ma offre funzionalità diverse a seconda della versione del sistema operativo. In Windows Server 2003, Netdiag non include più la funzionalità IPsec; è invece possibile utilizzare il contesto netsh ipsec e anche i test di base della rete possono essere eseguiti tramite Netsh. Per tutti i sistemi operativi, è importante verificare che si stia utilizzando la versione più recente, controllando nell'area di download del sito Web Microsoft. Netdiag deve essere installato dalla cartella Support\\Tools del CD di installazione di qualsiasi sistema operativo Windows.

**Nota**: Netdiag non viene aggiornato quando si installa Windows XP SP2.

Il ruolo di Netdiag nella risoluzione dei problemi relativi a IPsec varia a seconda della versione del sistema operativo. Le differenze sono riportate nella tabella seguente.

**Tabella 7.1. Funzionalità IPsec di Netdiag nei diversi sistemi operativi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Comando</th>
<th style="border:1px solid black;" >Descrizione</th>
<th style="border:1px solid black;" >Windows
2000?</th>
<th style="border:1px solid black;" >Windows
XP?</th>
<th style="border:1px solid black;" >Windows
2003?</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">netdiag<br />
/test:ipsec</td>
<td style="border:1px solid black;">Visualizza il criterio IPsec assegnato</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No**</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">netdiag<br />
/test:ipsec<br />
/debug</td>
<td style="border:1px solid black;">Visualizza il criterio IPsec attivo, i filtri e le statistiche di modalità rapida</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì*</td>
<td style="border:1px solid black;">No**</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">netdiag<br />
/test:ipsec<br />
/v</td>
<td style="border:1px solid black;">Visualizza il criterio IPsec attivo, i filtri e le statistiche di modalità principale</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì*</td>
<td style="border:1px solid black;">No**</td>
</tr>
</tbody>
</table>
  
\* Fornisce la diagnostica di rete, ma visualizza soltanto il nome del criterio IPsec. Ulteriori informazioni su IPsec possono essere acquisite tramite Ipseccmd.
  
\*\* Fornisce la diagnostica di rete, ma non visualizza alcuna informazione relativa a IPsec. Utilizzare invece la sintassi seguente: netsh ipsec dynamic show all.
  
##### Altri utili strumenti per il supporto di IPsec
  
Oltre agli strumenti specifici per IPsec precedentemente elencati, la tabella seguente riporta altri strumenti che possono essere utili nella risoluzione dei problemi e che devono essere inseriti nel toolkit del 2° livello.
  
**Tabella 7.2. Strumenti vari utili per la risoluzione dei problemi relativi a IPsec**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Strumento</th>
<th style="border:1px solid black;" >Sistemi operativi supportati</th>
<th style="border:1px solid black;" >Dove reperirlo</th>
<th style="border:1px solid black;" >Funzione</th>
<th style="border:1px solid black;" >Ulteriori informazioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Ipsecpol.exe</td>
<td style="border:1px solid black;">Solo Windows 2000</td>
<td style="border:1px solid black;">Windows 2000 Resource Kit</td>
<td style="border:1px solid black;">Configura i criteri IPsec nella directory o in un registro</td>
<td style="border:1px solid black;">Guida in linea degli strumenti inclusi in Windows 2000 Resource Kit</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gpresult</td>
<td style="border:1px solid black;">Windows 2000, Windows Server <br />
2003, Windows XP</td>
<td style="border:1px solid black;">Windows 2000– Resource Kit; per Windows XP e Windows Server <br />
2003, incluso nel sistema operativo</td>
<td style="border:1px solid black;">Controlla l'ultima applicazione di Criteri di gruppo</td>
<td style="border:1px solid black;">Guida in linea degli strumenti inclusi in Windows 2000 Resource Kit, Guida in linea di Windows XP e Guida in linea di Windows Server <br />
2003</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Snap-in MMC Gruppo di criteri risultante<br />
(RSoP)</td>
<td style="border:1px solid black;">Windows Server <br />
2003, Windows XP</td>
<td style="border:1px solid black;">Incluso nel sistema operativo</td>
<td style="border:1px solid black;">Visualizza il criterio IPsec per un computer o per i membri di un contenitore di Criteri di gruppo</td>
<td style="border:1px solid black;">Windows Server <br />
2003</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Srvinfo</td>
<td style="border:1px solid black;">Windows 2000, Windows Server <br />
2003, Windows XP</td>
<td style="border:1px solid black;">Windows 2000  e Windows Server <br />
2003 Resource Kit</td>
<td style="border:1px solid black;">Informazioni su servizi, driver di periferiche e protocolli</td>
<td style="border:1px solid black;">Guida in linea degli strumenti inclusi in Windows Server <br />
2003 Resource Kit</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PortQry</td>
<td style="border:1px solid black;">Windows 2000, Windows Server <br />
2003, Windows XP</td>
<td style="border:1px solid black;">Windows Server <br />
2003 Resource Kit</td>
<td style="border:1px solid black;">Segnala lo stato delle porte di rete</td>
<td style="border:1px solid black;"><a href="http://support.microsoft.com/kb/310099">http://support.<br />
microsoft.com/<br />
kb/310099</a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">NLTest</td>
<td style="border:1px solid black;">Windows 2000, Windows Server <br />
2003, Windows XP</td>
<td style="border:1px solid black;">Strumenti di supporto</td>
<td style="border:1px solid black;">Test delle relazioni di trust e dei canali protetti Netlogon</td>
<td style="border:1px solid black;">Guida in linea degli strumenti inclusi in Windows Server <br />
2003</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Klist</td>
<td style="border:1px solid black;">Windows 2000, Windows Server <br />
2003, Windows XP</td>
<td style="border:1px solid black;">Windows 2000 e Windows Server <br />
2003 Resource Kit</td>
<td style="border:1px solid black;">Crea report dei ticket Kerberos</td>
<td style="border:1px solid black;">Guida in linea degli strumenti inclusi in Windows Server <br />
2003 Resource Kit</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pathping</td>
<td style="border:1px solid black;">Windows 2000, Windows Server <br />
2003, Windows XP</td>
<td style="border:1px solid black;">Incluso nel sistema operativo</td>
<td style="border:1px solid black;">Testa la connettività di rete e del percorso</td>
<td style="border:1px solid black;">Guida di Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">LDP</td>
<td style="border:1px solid black;">Windows 2000, Windows Server <br />
2003, Windows XP</td>
<td style="border:1px solid black;">Strumenti di supporto</td>
<td style="border:1px solid black;">Client LDAP per il test di Active Directory</td>
<td style="border:1px solid black;">Guida in linea degli strumenti inclusi in Windows Server <br />
2003</td>
</tr>
</tbody>
</table>
 

##### Utilizzo di strumenti basati su ICMP con IPsec

Ping, Pathping e Tracert di Windows XP e Windows Server 2003 sono integrati con IPsec, ma potrebbero non funzionare correttamente fino a quando non vengono stabilite SA trasferibili (se la modalità non crittografata è consentita). Se le negoziazioni delle SA IPsec vengono completate per l'incapsulamento del traffico ICMP utilizzato da queste utilità, esse potrebbero non essere in grado di rilevare eventuali punti di passaggio intermedi (router) fra il client e la destinazione. I calcoli delle perdite di pacchetti per Ping potrebbero mostrare pacchetti persi durante il tempo necessario a IKE per completare la negoziazione di una coppia di SA IPsec con la destinazione. I calcoli delle perdite di pacchetti per ciascun punto di passaggio intermedio non sono disponibili quando il traffico ICMP viene incapsulato da IPsec.

Queste utilità di ICMP sono state concepite per rilevare se il driver IPsec ha creato una corrispondenza fra un filtro IPsec e il pacchetto di richiesta echo ICMP in uscita e se ha richiesto la negoziazione della protezione da parte di IKE. Quando si verifica questa condizione, l'utilità visualizza il messaggio "Negoziazione protezione IP in corso". Un errore noto di Windows 2000 fa sì che l'utilità Ping non attenda per l'intervallo di tempo corretto prima di ripetere la richiesta echo, il che significa che il comando potrebbe essere immediatamente completato senza attendere i tre secondi necessari per stabilire la SA trasferibile. L'utilità Ping di Windows XP e Windows Server 2003 attende invece per il numero di secondi previsti prima di inviare la successiva richiesta echo.

Il messaggio "Negoziazione protezione IP in corso" non viene visualizzato nelle seguenti condizioni:

-   Se il driver IPsec scarta il pacchetto ICMP in uscita a causa di un filtro di blocco

-   Se il driver IPsec consente il passaggio non protetto del pacchetto ICMP a causa di un filtro di autorizzazione o di una SA trasferibile

-   Se il driver IPsec non rileva il pacchetto in uscita (ad esempio, se il pacchetto viene scartato da livelli superiori al driver IPsec).

    **Nota:** alcuni strumenti che utilizzano ICMP potrebbero non essere in grado di rilevare che IPsec sta negoziando la protezione e potrebbero generare risultati non coerenti o errati.

[](#mainsection)[Inizio pagina](#mainsection)

### Processo di risoluzione dei problemi relativi a IPsec

Se il supporto di 1° livello ha identificato chiaramente il problema, il 2° livello sarà in grado di individuare rapidamente la procedura di risoluzione adeguata consultando le sezioni seguenti. In questo modello, il supporto di 1° livello gestisce prevalentemente i problemi correlati all'accesso dei client. Si presuppone che i proprietari e gli amministratori dei server siano in grado di eseguire la diagnostica di base della connettività di rete e possano saltare il supporto di 1° livello. Tuttavia, ciascuna organizzazione dovrà adeguare il modello al proprio specifico ambiente di supporto. Il supporto di 2° livello deve concentrarsi sull'identificazione dell'origine del problema di comunicazione, quindi analizzare le possibilità correlate all'interno dell'architettura del sistema.

Se l'organizzazione specifica utilizza gli script inclusi nel presente processo di risoluzione dei problemi, sarà necessario accedere a vari file di registro in formato testo, che possono essere utilizzati per facilitare la diagnosi del problema. Le descrizioni dei file che vengono generati dagli script sono riportate nella tabella seguente.

**Tabella 7.3. File creati dallo script IPsec\_Debug.vbs**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome file</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">&lt;Nome computer&gt;_FileVer.txt</td>
<td style="border:1px solid black;">Elenca le versioni dei file di varie DLL correlate a IPsec.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">&lt;Nome computer&gt;_gpresult.txt</td>
<td style="border:1px solid black;">Output del comando gpresult.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">&lt;Nome computer&gt;_ipsec_547_events.txt</td>
<td style="border:1px solid black;">Output di tutti gli errori IPSEC 547 nel registro eventi di protezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">&lt;Nome computer&gt;_ipsec_policy_version.txt</td>
<td style="border:1px solid black;">Output dello script Detect_IPsec_Policy.vbs. Mostra nella finestra la versione corrente del criterio e se la versione corrisponde al criterio di Active Directory.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">&lt;Nome computer&gt;_ipseccmd_show_all.txt</td>
<td style="border:1px solid black;">Solo per Windows XP. Questo file acquisisce l'output del comando ipseccmd.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">&lt;Nome computer&gt;_kerberos_events.txt</td>
<td style="border:1px solid black;">Output di tutti gli eventi Kerberos nel Registro eventi di sistema.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">&lt;Nome computer&gt;_klist_purge_mt.txt</td>
<td style="border:1px solid black;">Output di KList durante la rimozione dei ticket del computer.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">&lt;Nome computer&gt;_lsass.log</td>
<td style="border:1px solid black;">Copia del file lsass.log, se presente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">&lt;Nome computer&gt;_netdiag.txt</td>
<td style="border:1px solid black;">Output dell'esecuzione di netdiag.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">&lt;Nome computer&gt;_netsh_show_all.txt</td>
<td style="border:1px solid black;">Solo su piattaforme server. Output del comando show all in Netsh.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">&lt;Nome computer&gt;_netsh_show_gpo.txt</td>
<td style="border:1px solid black;">Solo su piattaforme server. Output del comando show gpo in Netsh.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">&lt;Nome computer&gt;_oakley.log</td>
<td style="border:1px solid black;">Copia del file Oakley.log, se presente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">&lt;Nome computer&gt;_OSInfo.txt</td>
<td style="border:1px solid black;">Output delle informazioni correnti sul sistema operativo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">&lt;Nome computer&gt;_RegDefault.txt</td>
<td style="border:1px solid black;">Output dei valori originali della chiave del Registro di sistema prima delle modifiche. Può essere utilizzato per ripristinare manualmente il Registro di sistema ai valori precedenti, se per qualche motivo lo script non ha funzionato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">&lt;Nome computer&gt;_userenv.log</td>
<td style="border:1px solid black;">Copia del file userenv.log, se presente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">&lt;Nome computer&gt;_&lt;Nome server&gt;_netview.txt</td>
<td style="border:1px solid black;">Output del comando net view su &lt;Nome server&gt;.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">&lt;Nome computer&gt;_&lt;Nome server&gt;_ping.txt</td>
<td style="border:1px solid black;">Output del comando ping su &lt;Nome server&gt;.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">&lt;Nome computer&gt;_winlogon.log</td>
<td style="border:1px solid black;">Copia del file winlogon.log, se presente.</td>
</tr>
</tbody>
</table>
  
Poiché le potenziali origini dei problemi sono numerose, questa sezione tratta ciascun componente dell'architettura uno dopo l'altro, iniziando con la connettività di rete. Le procedure illustrate di seguito facilitano il completamento delle attività seguenti:
  
-   Verifica della configurazione della rete IP, della connettività di rete e del servizio sui controller di dominio e della connettività sul percorso client-server per i protocolli correlati a IPsec
  
-   Verifica dell'applicazione corretta dei criteri di gruppo e del criterio IPsec sui client e sui server
  
-   Analisi delle problematiche della negoziazione IKE e delle comunicazioni protette da IPsec
  
-   Identificazione della causa del problema per l'eventuale assegnazione al 3° livello  
  
Si presupponga lo scenario seguente: un client crea un report segnalando che ha effettuato il ping al server, ma che non è riuscito a connettersi a una condivisione di file su questo server. Questo è il solo server a cui il client non riesce ad accedere. Una rapida analisi del Registro protezione per l'evento 547 (errore della negoziazione IKE), che contiene l'indirizzo IP del server, indica che al client è stato assegnato un criterio IPsec e che IKE viene avviato. Se l'evento 547 del client segnala che la negoziazione IKE è scaduta, il protocollo IKE del server non ha presumibilmente completato la negoziazione. Il supporto di 2° livello esaminerà quindi gli eventi 547 nel database MOM degli eventi acquisiti dal server specificato, contenenti l'indirizzo IP corrente del client.
  
#### Avviso: avvio e interruzione del servizio IPsec
  
Il documento sulla risoluzione dei problemi relativi a TCP/IP di Windows Server 2003 e altri documenti di riferimento spiegano come stabilire se IPsec sta generando problemi di connettività interrompendo il servizio IPsec. Nonostante questa procedura interrompa l'azione di filtraggio di IPsec sul computer, disattiva anche la protezione che IPsec garantisce, esponendo il computer ad accessi non attendibili e disattivando la protezione dei pacchetti. Inoltre, in un ambiente di isolamento del dominio, il traffico TCP e UDP non protetto da IPsec verrà scartato da altri membri del dominio di isolamento. Se IPsec viene disattivato su un computer, si verificheranno quindi interruzioni della connettività con i computer remoti che hanno stabilito associazioni di protezione IPsec. Quando il servizio IPsec viene arrestato, IKE invia delle notifiche di eliminazione per tutte le SA IPsec e per la SA IKE a tutti i computer connessi e attivi. I computer remoti a cui è stato assegnato un criterio IPsec che consente la modalità non crittografata ristabiliranno la connessione dopo un ritardo di tre secondi. I computer remoti a cui invece è stato assegnato un criterio IPsec che non consente la modalità non crittografata non saranno in grado di comunicare.
  
È quindi importante utilizzare le tecniche illustrate nelle sezioni seguenti per risolvere i problemi degli scenari di isolamento senza interrompere il servizio IPsec. Il servizio IPsec deve essere disattivato solo come ultima risorsa per la risoluzione dei problemi di IPsec e nelle situazioni seguenti:
  
-   Ambienti con traffico broadcast e multicast
  
-   Connessioni a computer remoti che non richiedono IPsec per l'accesso in ingresso (ad esempio, computer che rientrano nell'elenco di esenzioni)  
  
In Windows 2000, arrestando il servizio IPsec si interrompe il binding fra il driver IPsec e TCP/IP e si scarica il driver IPsec dalla memoria.
  
In Windows XP e Windows Server 2003, l'interruzione del servizio IPsec elimina tutti i filtri dal driver IPsec e imposta la modalità di autorizzazione sul driver. Il driver IPsec rimane però caricato nella memoria. Per evitare che il driver IPsec venga caricato, è necessario disattivare il servizio IPsec e riavviare il computer.
  
In Windows 2000 e Windows XP SP1, per attivare la registrazione IKE sul file **Oakley.log** è necessario riavviare il servizio IPsec. In Windows XP SP2 e Windows Server 2003, non è invece necessario interrompere il servizio per attivare e disattivare la registrazione IKE sul file **Oakley.log**. L'ultimo aggiornamento di Ipseccmd per Windows XP SP2 consente di utilizzare la sintassi  
ipseccmd set logike e ipseccmd set dontlogike per attivare e disattivare dinamicamente la registrazione IKE sul file **Oakley.log**. La registrazione IKE in Windows Server 2003 può essere attivata dinamicamente utilizzando i comandi Netsh illustrati nella Guida in linea.
  
#### Verifica della connettività di rete
  
Se il supporto di 1° livello identifica potenziali problemi di connettività di rete, la prima fase consisterà nel verificare se è presente la connettività di rete di base. Questa analisi include la verifica della configurazione IP utilizzata, della presenza di un percorso di rete valido fra iniziatore e risponditore e del funzionamento dei servizi di risoluzione dei nomi.
  
##### Problemi di configurazione degli indirizzi IP di rete
  
Se la configurazione IP dinamica non viene completata o se le comunicazioni si bloccano dopo il riavvio del computer (oppure durante il normale funzionamento), la causa potrebbe essere IPsec. In Windows Server 2003, questi problemi potrebbero essere correlati al comportamento in modalità provvisoria di IPsec (ad esempio, se il computer viene avviato in modalità provvisoria o in modalità di ripristino di Active Directory).
  
**Nota:** per informazioni sul comportamento di Windows Server 2003 in modalità provvisoria, consultare la sezione "[Understanding IPSec Protection During Computer Startup](http://technet.microsoft.com/en-us/library/cc756853.aspx)" del modulo "Deploying IPsec" nel Windows Server 2003 Deployment Kit all'indirizzo www.microsoft.com/resources/  
documentation/WindowsServ/2003/all/deployguide/  
en-us/dnsbj\_ips.asp.
  
Windows Server 2003 ricorre alla modalità provvisoria se il servizio IPsec non si avvia o se non è possibile applicare il criterio assegnato. Questa modalità viene applicata soltanto in caso di assegnazione di un criterio IPsec al computer e se il servizio IPsec non è disattivato. Di conseguenza, la connettività verso o da un computer potrebbe interrompersi durante il normale funzionamento perché il driver IPsec non applica il criterio IPsec di dominio. Dopo aver stabilito quale traffico è consentito e quale viene bloccato dalle configurazioni di avvio e permanenti, potrebbe essere facile spiegare il problema di comunicazione. Per ottenere informazioni alternative o aggiuntive, è possibile eseguire una query dello stato corrente dalla riga di comando utilizzando la sintassi seguente:

```  
netsh ipsec dynamic show config  
```  

In Windows Server 2003, il driver IPsec viene caricato all'avvio del computer insieme al driver TCP/IP. Per evitare, pertanto, che il driver IPsec vada in modalità provvisoria, è necessario disattivare il servizio IPsec e riavviare il computer. Il modulo dedicato alla distribuzione di IPsec a cui si faceva precedentemente riferimento contiene una configurazione consigliata delle esenzioni di avvio per esentare le connessioni RDP (Remote Desktop Protocol) e garantire così che l'accesso remoto al server sia possibile quando l'altro traffico viene bloccato.
  
In una soluzione di isolamento del server e del dominio, il traffico broadcast e quello verso i server DHCP viene esentato per garantire il corretto funzionamento della configurazione IP dinamica. Tuttavia, l'elenco di esenzioni deve essere gestito manualmente e potrebbe non essere aggiornato. Se un computer non riesce a ottenere una configurazione DHCP appropriata (ad esempio, se utilizza un indirizzo IP 169.254.x.x di configurazione automatica) o ha problemi a rinnovare il lease, è necessario verificare che il criterio IPsec contenga le esenzioni corrette. Con il servizio IPsec in esecuzione, utilizzare Ipconfig per verificare eventuali problemi di configurazione degli indirizzi:
  
-   Per i client DHCP, aprire una finestra di comando ed eseguire ipconfig /release seguito da ipconfig /renew.
  
Se in Windows XP SP2 e Windows Server 2003 i problemi di configurazione degli indirizzi si verificano soltanto all'avvio del computer, è necessario verificare la configurazione delle esenzioni (esenzioni predefinite e di avvio).
  
##### Problemi di risoluzione dei nomi
  
La configurazione dei criteri IPsec negli scenari di isolamento del server e del dominio non deve interferire con le procedure comunemente utilizzate per verificare se la risoluzione dei nomi funziona. Nello scenario della Woodgrove Bank, ad esempio, la configurazione dei criteri IPsec esenta tutto il traffico verso i server DNS e WINS. È comunque possibile configurare i server DNS e WINS affinché non rispondano alle richieste di ping. Per verificare che la risoluzione dei nomi funzioni correttamente quando il servizio IPsec è in esecuzione, rispondere alle seguenti domande:
  
-   "Il client riesce a eseguire il ping dell'indirizzo IP del server DNS elencato nella configurazione IP?",
  
-   "nslookup riesce a trovare un server DNS?",
  
-   "Il client riesce a eseguire il ping del nome DNS completo della destinazione?",
  
-   "Il client riesce a eseguire il ping della versione abbreviata del nome DNS o NetBIOS della destinazione?".
  
Le potenziali origini dei problemi di risoluzione dei nomi includono: file HOSTS attivo e non correttamente configurato, voce del server DNS configurata in modo errato nelle proprietà IP, registrazioni errate del record DNS, problemi di aggiornamento dei file di zona, problemi di replica di Active Directory, modalità non crittografata utilizzata per i server DNS e problemi di aggiornamento automatico di DHCP.
  
Le possibili cause dei problemi di risoluzione dei nomi NetBIOS includono: file LMHOSTS attivo e non correttamente configurato, voce del server WINS configurata in modo errato nelle proprietà IP, mancata disponibilità del server WINS, record WINS errato, problemi di replica WINS, problemi di proxy WINS e timeout di rete che raggiungono il server WINS.
  
Per le procedure di supporto alla risoluzione dei problemi di DNS integrati in Active Directory, consultare la pagina [Troubleshooting Active Directory - Related DNS Problems](http://www.microsoft.com/technet/prodtechnol/windows2000serv/technologies/activedirectory/maintain/opsguide/part1/adogd10.mspx) sul sito Web Microsoft.com all'indirizzo www.microsoft.com/technet/prodtechnol/  
windows2000serv/technologies/activedirectory/  
maintain/opsguide/part1/adogd10.mspx.
  
Alcuni ambienti con livello di protezione elevato potrebbero richiedere la protezione IPsec per i server DNS e WINS con conseguenti possibili problemi di risoluzione dei nomi. Se, ad esempio, DNS è integrato in Active Directory ed esistono filtri duplicati per il medesimo indirizzo IP all'interno del criterio IPsec, uno dei filtri potrebbe negoziare la protezione verso il server DNS e l'altro filtro potrebbe esentare i controller di dominio. Per ulteriori informazioni, vedere la sezione "Risoluzione dei problemi del servizio IPsec" più avanti nel presente capitolo.
  
Se i problemi di risoluzione dei nomi permangono, è possibile acquisire l'elenco filtri dall'iniziatore e controllare che non siano presenti duplicati. Per visualizzare gli elenchi filtri, è possibile utilizzare le seguenti opzioni della riga di comando:
  
```  
Ipseccmd show filters  
Netsh ipsec static show all   
```  

Se anche in questo caso i problemi di risoluzione dei nomi permangono, sarà necessario interrompere brevemente il servizio IPsec (se possibile) e ripetere i test di risoluzione dei nomi. Se i test di risoluzione dei nomi danno esito negativo solo quando il servizio IPsec è in funzione, si dovrà proseguire l'analisi per stabilire quale criterio IPsec viene applicato, come precedentemente illustrato in questa sezione.
  
##### Verifica della connettività e dell'autenticazione con i controller di dominio
  
Poiché la distribuzione dei criteri IPsec, l'autenticazione IKE e la maggior parte dei protocolli di livello superiore dipendono dall'accesso ai controller di dominio, è necessario eseguire i test di connettività di rete e di funzionamento dei servizi di autenticazione, prima di effettuare i passaggi specifici di risoluzione dei problemi IPsec (descritti nella sezione seguente). In uno scenario come quello della Woodgrove Bank, la configurazione dei criteri IPsec esenta tutto il traffico verso tutti i controller di dominio, quindi i test di connettività di rete verso i controller di dominio non subiscono interferenze da parte di IPsec. L'elenco degli indirizzi IP dei controller di dominio deve tuttavia essere gestito manualmente. Se si rileva la negoziazione IKE verso un indirizzo IP di un controller di dominio, il criterio IPsec potrebbe essere stato assegnato in modo errato o non essere aggiornato.
  
**Risoluzione dei problemi dei servizi di accesso alla rete in Active Directory**
  
-   Verificare che il client possa eseguire il ping di tutti gli indirizzi IP dei controller di dominio. In caso contrario, vedere i precedenti passaggi riguardanti la connettività di rete.
  
-   Identificare quali indirizzi IP vengono utilizzati per i controller di dominio membri del dominio. Utilizzare nslookup *&lt;nome dominio&gt;* per ottenere l'elenco completo degli indirizzi IP. In uno scenario di isolamento del server e del dominio, deve essere presente un filtro specifico per la modalità rapida con un criterio di negoziazione (operazione filtro) di *autorizzazione* per ciascuno di questi indirizzi.
  
-   Per testare l'accesso alle porte UDP, LDAP e RPC del controller di dominio, utilizzare la versione 2.0 o successive dello strumento **portqry.exe** o lo strumento PortQueryUI. I messaggi del protocollo UDP utilizzati da portqry solitamente non richiedono l'autenticazione del protocollo di livello superiore e quindi possono verificare la disponibilità del servizio anche se l'autenticazione non è disponibile. Questi passaggi sono spiegati nell'articolo [HOW TO: Use Portqry to Troubleshoot Active Directory Connectivity Issues](http://support.microsoft.com/?kbid=816103), disponibile all'indirizzo http://support.microsoft.com/?kbid=816103 (in lingua inglese).
  
-   In caso di connessione a una rete interna, utilizzare netdiag /v &gt;outputfile.txt per eseguire vari test di connettività correlati ai DNS e ai controller di dominio. Netdiag utilizza numerose connessioni di rete e protocolli per eseguire i test; se una di queste connessioni avvia le negoziazioni IKE e l'autenticazione non viene completata perché il protocollo non è in grado di individuare un controller di dominio per l'autenticazione Kerberos, è possibile che nel Registro protezione venga registrato l'evento di errore 547.
  
Per verificare che l'accesso e l'autenticazione Kerberos vengano completati, è possibile utilizzare lo strumento di supporto **klist.exe** di Windows. Klist deve essere eseguito nel contesto del sistema locale per visualizzare i ticket Kerberos per il computer.
  
**Visualizzazione dei ticket di servizio Kerberos per l'utente di dominio connesso**
  
-   Aprire un prompt dei comandi e digitare:
  
```
klist tickets  
```  
  
**Visualizzazione dei ticket dei computer di dominio**
  
1.  Verificare che il servizio Utilità di pianificazione sia in esecuzione e che l'utente connesso sia membro del gruppo Amministratori locale.
  
2.  Al prompt della riga di comando, scegliere un orario antecedente all'orario corrente del sistema (ad esempio, 16:38) di 1 minuto e digitare:
  
```
at 4:38pm /interactive cmd /k klist tickets  
```  

Si noti che la barra del titolo della finestra di comando visualizza **C:\\Windows\\System32\\svchost.exe**.
  
Nonostante i ticket Kerberos contengano informazioni sui gruppi dell'utente o del computer, queste informazioni sono crittografate e quindi i gruppi non sono visibili. Ne consegue che l'appartenenza a un gruppo deve essere verificata manualmente in Active Directory. Affinché i computer ricevano le informazioni più aggiornate sull'appartenenza ai gruppi nei ticket Kerberos, utilizzare klist per rimuovere i ticket Kerberos correnti. Quando viene ripetuto il tentativo di negoziazione IKE, i nuovi ticket Kerberos vengono ottenuti automaticamente.
  
**Rimozione dei ticket Kerberos dal computer**
  
(i passaggi da 1 a 4 devono essere eseguiti nel contesto del sistema locale)
  
1.  Verificare che il servizio Utilità di pianificazione sia in esecuzione e che l'utente connesso sia membro del gruppo Amministratori locale.
  
2.  Al prompt della riga di comando, scegliere un orario successivo all'orario corrente del sistema (ad esempio 16:38) di 1 minuto e digitare:
  
```
at 4:38pm /interactive cmd  
```  
  
3.  Digitare klist purge e premere Y per ciascun tipo di ticket, eliminando tutti i ticket Kerberos.
  
4.  Digitare klist tickets per verificare che non esista più alcun tipo di ticket.
  
5.  Se questa procedura rientra nel processo di risoluzione dei problemi di negoziazione IKE, attendere un minuto affinché scada la negoziazione IKE e tentare nuovamente di accedere al server di destinazione usando l'applicazione. Le negoziazioni in modalità principale IKE richiederanno nuovi ticket Kerberos TGT e di servizio per il computer di destinazione contenenti le informazioni più recenti sul gruppo. Fare attenzione a non eseguire l'applicazione dalla finestra di comando in esecuzione nel contesto del sistema locale.  
  
Ulteriori procedure dettagliate per la risoluzione dei problemi relativi a Kerberos sono pubblicate nei white paper seguenti:
  
-   [Troubleshooting Kerberos Errors](http://www.microsoft.com/downloads/details.aspx?familyid=7dfeb015-6043-47db-8238-dc7af89c93f1&displaylang=en) disponibile all'indirizzo www.microsoft.com/downloads/details.aspx?  
    FamilyID=7dfeb015-6043-47db-8238-dc7af89c93f1&displaylang=en
  
-   [Troubleshooting Kerberos Delegation](http://www.microsoft.com/downloads/details.aspx?familyid=99b0f94f-e28a-4726-bffe-2f64ae2f59a2&displaylang=en) disponibile all'indirizzo www.microsoft.com/downloads/details.aspx?  
    FamilyID=99b0f94f-e28a-4726-bffe-2f64ae2f59a2&displaylang=en
  
##### Verifica di autorizzazioni e integrità del criterio IPsec in Active Directory
  
Potrebbe essere necessario verificare le informazioni sul contenitore dei criteri IPsec in Active Directory. La procedura seguente utilizza lo strumento di supporto **ldp.exe**.
  
**Per verificare le informazioni sul contenitore dei criteri IPsec**
  
1.  Fare clic su **Start**, **Esegui**, digitare **ldp.exe** e premere INVIO.
  
2.  Scegliere **Connection**, quindi **Connect**. Specificare il nome del dominio di destinazione.
  
3.  Scegliere **Connection**, quindi **Bind**. Specificare le credenziali di accesso per il dominio di destinazione.
  
4.  Scegliere **View**, quindi **Tree**. È possibile non specificare alcun nome distinto di base e navigare fino al contenitore dei criteri IPsec oppure specificare il nome distinto di LDAP per il contenitore dei criteri IPsec come ubicazione di base.
  
5.  Fare clic su **+** (segno più) accanto al nodo del contenitore nella struttura. Se si dispone delle autorizzazioni di lettura per il contenitore, verranno visualizzati tutti gli oggetti dei criteri IPsec presenti nel contenitore.
  
    **Nota**: alcuni utenti di dominio potrebbero non disporre delle autorizzazioni di lettura per il contenitore a causa della modalità di configurazione delle autorizzazioni. Per ulteriori informazioni, consultare l'articolo numero 329194 "[IPSec Policy Permissions in Windows 2000 and Windows Server 2003](http://support.microsoft.com/?kbid=329194)", disponibile all'indirizzo http://support.microsoft.com/?kbid=329194 (in lingua inglese).
  
Per i processi avanzati di risoluzione dei problemi di recupero e danneggiamento dei criteri, è possibile utilizzare **ldp.exe** per analizzare manualmente il contenuto del contenitore Protezione IP e la relazione che lega gli oggetti dei criteri IP. Windows 2000, Windows XP e Windows Server 2003 utilizzano per i criteri IPsec il medesimo schema di base della directory illustrato nel diagramma della struttura dei criteri IPsec riportato nel documento tecnico [How IPsec Works](http://technet.microsoft.com/en-us/library/cc759130.aspx) di Windows Server 2003, disponibile all'indirizzo www.microsoft.com/resources/documentation/  
WindowsServ/2003/all/techref/en-us/w2k3tr\_ipsec\_how.asp.
  
La tabella seguente mostra la relazione fra i nomi degli oggetti di Active Directory e i nomi dei componenti dei criteri IPsec configurati nello snap-in MMC Gestione criteri di protezione IP:
  
**Tabella 7.4. Mappatura dei componenti dei criteri IPsec rispetto al nome dell'oggetto di Active Directory**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome del componente del criterio IPsec</th>
<th style="border:1px solid black;" >Nome dell'oggetto di Active Directory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Criterio IPsec</td>
<td style="border:1px solid black;">CriterioIpsec{GUID}</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Metodi di protezione per scambio chiavi IKE</td>
<td style="border:1px solid black;">CriterioISAKMPipsec{GUID}</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Regola IPsec</td>
<td style="border:1px solid black;">NFAipsec{GUID}</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Elenco filtri IPsec</td>
<td style="border:1px solid black;">FiltroIpsec{GUID}</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Operazione filtro IPsec</td>
<td style="border:1px solid black;">CriterioNegoziazioneIpsec{GUID}</td>
</tr>
</tbody>
</table>
  
**Ldp.exe** consente di individuare l'ultima modifica apportata agli oggetti dei criteri IPsec, facilitando quindi la risoluzione dei problemi correlati alla replica e alla versione degli oggetti. Può essere lanciato da una finestra di comando nel contesto del sistema locale per risolvere i problemi di autorizzazione alla lettura per il servizio IPsec.
  
**Attenzione**: è consigliabile che tutti gli oggetti del contenitore Protezione IP dispongano delle medesime autorizzazioni. Microsoft sconsiglia di impostare autorizzazioni specifiche su ciascuno degli oggetti dei criteri IPsec. Per controllare l'accesso in lettura e modifica dei criteri IPsec, le autorizzazioni devono essere gestite a livello del contenitore Protezione IP stesso, come spiegato nell'articolo 329194 "[IPSec Policy Permissions in Windows 2000 and Windows Server 2003](http://support.microsoft.com/default.aspx?scid=kb;en-us;329194)" della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/?kbid=329194 (in lingua inglese).
  
Il danneggiamento del criterio IPsec è la causa più comune delle situazioni in cui l'oggetto IPsec contiene un riferimento nome distinto a un oggetto che non esiste più. Tuttavia, il danneggiamento può verificarsi anche nel caso in cui i caratteri di controllo diventino parte del nome di un oggetto, se i singoli oggetti non sono leggibili a causa di problemi di autorizzazioni o se nomi identici degli oggetti generano configurazioni errate del criterio IPsec (ad esempio, due versioni del medesimo elenco filtri). Per ulteriori informazioni su come correggere i criteri IPsec danneggiati, vedere la sezione "Risoluzione dei problemi del servizio IPsec" descritta di seguito.
  
**Nota**: i dettagli di configurazione di questi oggetti sono considerati come struttura di dati privata e interna e non vengono pubblicati da Microsoft. Esistono differenze fra i formati di questi oggetti nelle diverse versioni di Windows e Microsoft si riserva il diritto di apportare modifiche a questi formati in qualsiasi momento. Tali oggetti devono, pertanto, essere gestiti utilizzando lo snap-in MMC Gestione criteri di protezione IP e gli strumenti della riga di comando disponibili per ciascuna piattaforma. Gli oggetti devono essere eliminati soltanto utilizzando LDP e come ultima opzione quando i danneggiamenti impediscono l'utilizzo dello snap-in MMC Gestione criteri di protezione IP e degli strumenti della riga di comando.
  
##### Connettività sul percorso di rete
  
Microsoft consiglia di esentare il protocollo ICMP nelle soluzioni con isolamento del server e del dominio. Le ragioni di questa raccomandazione sono numerose, fra le quali l'esigenza di alcune utilità, quali Ping, Pathping e Tracert, di utilizzare ICMP per i test del percorso di rete. Queste utilità devono quindi funzionare correttamente e non visualizzare il messaggio "Negoziazione protezione IP in corso". Se questo messaggio viene visualizzato, potrebbe essere stato assegnato un criterio IPsec non appropriato.
  
**Distinzione fra problemi correlati alla configurazione di base della rete e problemi di connettività sul percorso**
  
-   Il client riesce a eseguire il ping del proprio indirizzo IP o dell'indirizzo 127.0.0.1 del loopback locale? In caso contrario, potrebbe trattarsi di un problema di configurazione TCP/IP, potrebbe essere installato un firewall di terze parti, l'utilità Ping potrebbe essere assente o la configurazione IP potrebbe non essere valida. Per individuare la causa, utilizzare altre procedure di risoluzione dei problemi relativi alla configurazione TCP/IP.
  
-   Il client riesce ad eseguire il ping del gateway predefinito indicato nella configurazione IP? In caso contrario, la configurazione IP residente sul client potrebbe costituire un problema, l'interfaccia locale potrebbe non essere connessa o potrebbe avere una connettività limitata, i filtri locali e di rete potrebbero bloccare il traffico o il percorso di rete verso il gateway predefinito potrebbe essere interrotto. Per individuare la causa, utilizzare altre procedure di risoluzione dei problemi relativi a TCP/IP.
  
-   Il client riesce ad eseguire il ping dei server DNS indicati nella configurazione IP? In caso contrario, i server DNS potrebbero non consentire la ricezione dei messaggi di richiesta echo ICMP, il criterio IPsec potrebbe non esentare gli indirizzi IP dei server DNS corretti oppure potrebbe trattarsi di uno dei problemi sopra menzionati. Per individuare la causa, utilizzare altre procedure di risoluzione dei problemi relativi a TCP/IP.
  
-   Il client riesce ad eseguire il ping di un indirizzo IP presente nell'elenco di esenzioni, ad esempio di un controller di dominio? In caso contrario, IPsec non è la causa del problema oppure non dispone di un filtro per questo indirizzo IP esentato. La seconda opzione può essere verificata controllando la configurazione del filtro. Vedere la sezione dedicata ai criteri IPsec più avanti nel presente capitolo.
  
-   Il client riesce a eseguire il ping dell'indirizzo IP della destinazione? In caso affermativo, è presente la connettività di base fra il client e la destinazione senza IPsec. In caso contrario, per stabilire fino a che punto il percorso di rete è valido, tentare con Tracert verso la destinazione e verso altri indirizzi IP di destinazione. Per individuare la causa, utilizzare altre procedure di risoluzione dei problemi relativi a TCP/IP e alla rete.
  
I test della connettività sul percorso possono dare esito positivo per ICMP e negativo quando si utilizzano i protocolli IKE o IPsec. In particolare, il carico imposto da IPsec sui pacchetti di autenticazione in modalità principale IKE, che contengono i ticket Kerberos, è spesso superiore alla PMTU dell'indirizzo IP di destinazione e rende necessaria la frammentazione. Di conseguenza, i firewall basati su host, il filtraggio dei router, i firewall di rete e i filtri presenti sull'host di destinazione devono essere aperti ai seguenti protocolli e porte e supportare la frammentazione:
  
-   **IKE**. Porta UDP di origine 500, porta di destinazione 500 e frammenti
  
-   **NAT-T di IKE/IPsec**. Porta UDP di origine 4500, porta di destinazione 4500
  
-   **ESP di IPsec**. Protocollo IP 50 e frammenti
  
-   **AH di IPsec**. Protocollo IP 51 e frammenti
  
###### Filtri di stato sul percorso (sconsigliati)
  
I filtri di stato potrebbero causare problemi di connettività per IKE, AH ed ESP in quanto lo stato si basa tipicamente sui timeout delle attività. Le periferiche non riescono a monitorare il traffico IKE per stabilire quando vengono eliminate le SA IPsec perché questi messaggi vengono crittografati da IKE. Per definizione, IKE deve essere in grado di reimpostare le chiavi in entrambe le direzioni, il che significa che i messaggi di eliminazione possono essere inviati in entrambe le direzioni. Se una parte non riceve un messaggio di eliminazione, potrebbe considerare ancora valida una coppia di SA IPsec quando il peer invece non la riconosce più e scarta i pacchetti che la utilizzano. La direzione di reimpostazione delle chiavi IKE si basa sulla direzione del flusso di traffico in cui la durata in byte scade più rapidamente, sui piccoli offset per la reimpostazione quando scade la durata basata sul tempo e sulla direzione di flusso dei pacchetti dopo l'eliminazione delle SA IPsec inattive. Il filtraggio di stato del traffico IKE basato su host e applicato ai client che avviano le connessioni (e quindi le negoziazioni IKE) attraverso Windows Firewall solitamente non causa problemi. Windows Firewall non filtra i pacchetti IPsec perché il driver IPsec li elabora a un livello inferiore rispetto a quello in cui viene eseguito il filtraggio del firewall. Tuttavia, nei firewall basati su host, la configurazione delle porte IKE deve essere aperta per ricevere le negoziazioni IKE in ingresso per le connessioni dei protocolli di livello superiore consentite dal firewall (ad esempio, per la condivisione file mediante il protocollo SMB sulla porta TCP 445).
  
###### Supporto per la PMTU ICMP (necessario per TCP)
  
L'impostazione predefinita in Windows 2000 e nelle versioni successive prevede che il bit **Don't Fragment** sia impostato nell'intestazione IP di ciascun pacchetto TCP. Questa impostazione viene mantenuta anche quando si utilizzano le modalità di trasporto AH o ESP di IPsec per la protezione del pacchetto. Conseguentemente, i pacchetti di dimensioni eccessive vengono scartati a livello di router, che dovrà restituire il messaggio **Destinazione ICMP non raggiungibile** per specificare le dimensioni massime consentite. Questo comportamento viene definito "rilevamento dell'MTU del percorso TCP". Sia il computer client che quello di destinazione devono essere in grado di ricevere i messaggi PMTU ICMP per i pacchetti IPsec di dimensione eccessiva. È particolarmente importante evitare che il traffico protetto da IPsec venga frammentato perché le schede di accelerazione hardware, di solito, non elaborano i pacchetti frammentati. I pacchetti IPsec frammentati devono essere elaborati a livello di software dal driver IPsec.
  
Windows 2000 e Windows XP non supportano l'elaborazione del rilevamento PMTU di ICMP per i pacchetti trasportati in modalità IPsec che utilizzano l'incapsulamento per l'attraversamento del NAT (porta UDP 4500). Windows Server 2003 non supporta l'elaborazione di questo rilevamento. Per le opzioni e gli strumenti da utilizzare in assenza di rilevamento della PMTU, consultare la pagina "Troubleshooting Translational Bridging" della sezione "[TCP/IP Troubleshooting](http://www.microsoft.com/resources/documentation/windows/2000/server/reskit/en-us/cnet/cnbd_trb_gdhe.asp)" nella documentazione in linea di Windows Server 2003, disponibile all'indirizzo www.microsoft.com/resources/documentation/Windows/  
2000/server/reskit/en-us/cnet/cnbd\_trb\_gdhe.asp
  
**Nota:** un problema noto richiede l'attivazione del rilevamento della PMTU di TCP affinché IPsec possa proteggere il traffico in uno scenario di attraversamento del NAT in cui le connessioni UDP-ESP di IPsec vengono avviate da un host esterno al NAT verso un host ubicato dietro al NAT. Se è necessario utilizzare questo scenario, verificare che il rilevamento della PMTU di TPC sia attivato, controllando che la seguente chiave del Registro di sistema non sia definita o impostandola su 1 per entrambe le parti:  
**    HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\Tcpip\\**  
**    Parameters\\EnablePMTUDiscovery=1**  
    (questa chiave potrebbe essere visualizzata su più di una riga; nel Registro di sistema è su una sola riga).  
Il modello di protezione di base per server membro di Microsoft Windows Server 2003 e altre configurazioni di terze parti potrebbero configurare questa chiave del Registro di sistema per disattivare la PMTU di TCP.
  
###### Supporto per la frammentazione
  
I percorsi e i filtri di rete devono supportare il passaggio dei frammenti per i protocolli IKE, IPsec, AH ed ESP. IKE utilizza i pacchetti UDP e ne consente la frammentazione quando necessario. L'implementazione dell'attraversamento del NAT in IPsec include il supporto necessario per evitare la frammentazione IKE soltanto quando questo protocollo esegue l'autenticazione con certificati (ad esempio, negli scenari L2TP/IPsec VPN). L'autenticazione IKE che utilizza Kerberos non supporta la possibilità di evitare la frammentazione e deve essere in grado di inviare e ricevere pacchetti UDP frammentati che contengano il ticket Kerberos.
  
Il percorso di rete deve supportare il passaggio dei frammenti per AH ed ESP poiché IPsec protegge l'intero pacchetto originale prima della frammentazione in uscita a livello IP. Grazie all'integrazione fra IPsec e TCP, quando nei pacchetti TCP il flag DF (Don’t Fragment) non è impostato (impostazione predefinita), TCP ne riduce le dimensioni per consentire l'inserimento dei byte supplementari dell'incapsulamento IPsec.
  
IPsec non è però integrato con UDP e le applicazioni UDP non dispongono di un metodo per rilevare se IPsec sta proteggendo il loro traffico. Conseguentemente, quando si applica il formato AH o ESP di IPsec, i pacchetti UDP che utilizzano le dimensioni MTU massime vengono frammentati dall'host al momento della trasmissione. Analogamente, se i filtri del criterio IPsec non esentano ICMP, l'utilizzo dell'utilità Ping può generare pacchetti ICMP che appaiono sulla rete come pacchetti AH o ESP di IPsec frammentati.
  
Per ulteriori informazioni, consultare l'articolo numero 233256 "[How to Enable IPSec Traffic Through a Firewall](http://support.microsoft.com/?kbid=233256)" della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/?kbid=233256 (in lingua inglese).
  
###### Supporto per il traffico broadcast e multicast
  
La configurazione dei criteri IPsec per l'isolamento del server e del dominio utilizza filtri da Qualsiasi &lt;-&gt; Subnet. Il filtro in uscita Subnet -&gt; Qualsiasi corrisponderà quindi al traffico broadcast e multicast in uscita inviato dagli host utilizzando un indirizzo IP di una subnet interna. Tuttavia, visto che IPsec non è in grado di proteggere il traffico multicast e broadcast, deve scartare questo traffico se corrispondente al filtro. Il traffico multicast e la maggior parte dei tipi di traffico broadcast in ingresso non corrisponderanno al filtro Qualsiasi -&gt; Subnet. Se il traffico multicast o broadcast è necessario, è possibile impostare la chiave del Registro di sistema su **NoDefaultExempt=1** per consentire al traffico multicast e broadcast di eludere i filtri IPsec in Windows XP e Windows Server 2003. Questa configurazione evita i problemi noti con i client RTC (Real Time Communications) e Windows Media Server che utilizzano entrambi il traffico multicast. Per informazioni sull'utilizzo e sulle implicazioni di protezione della chiave **NoDefaultExempt** del Registro di sistema, consultare i seguenti articoli della Knowledge Base:
  
-   810207 - [Rimozione delle esenzioni predefinite per IPSec in Windows Server 2003](http://support.microsoft.com/default.aspx?scid=kb;en-us;810207), disponibile all'indirizzo http://support.microsoft.com/?kbid=810207
  
-   811832 - [IPSec Default Exemptions Can Be Used to Bypass IPsec Protection in Some Scenarios](http://support.microsoft.com/default.aspx?scid=kb;en-us;811832), disponibile all'indirizzo http://support.microsoft.com/?kbid=811832 (in lingua inglese)
  
    **Nota:** Windows XP SP2 utilizza le medesime esenzioni predefinite di Windows Server 2003.
  
La chiave del Registro di sistema può essere impostata per controllare, se necessario, tutte le esenzioni predefinite per tutte le piattaforme. Il filtraggio IPsec non supporta la configurazione di indirizzi di destinazione per indirizzi specifici di broadcast o multicast.
  
###### Possibile inefficacia della diagnostica delle periferiche di rete
  
Uno degli impatti derivanti dall'utilizzo dell'incapsulamento IPsec consiste nel fatto che le applicazioni che presumono che il traffico TCP/IP non sia crittografato non sono più in grado di controllare il traffico sulla rete. Gli strumenti di diagnostica della rete che controllano o generano report basati sulle porte TCP e UDP difficilmente possono interpretare i pacchetti con incapsulamento IPsec, anche se non si utilizza la crittografia AH o ESP. Per analizzare i pacchetti IPsec con crittografia AH o ESP senza crittografia, potrebbe essere necessario aggiornare questi strumenti.
  
##### Aspetti correlati ai driver e alle schede di interfaccia di rete
  
La perdita di pacchetti IPsec, in alcuni casi, può essere causata dalle schede di interfaccia di rete (NIC) che eseguono funzioni speciali. Le schede che eseguono il clustering o "raggruppamento" devono essere testate per verificarne la compatibilità con IPsec. I driver NIC che accelerano le funzioni non IPsec potrebbero generare problemi con il traffico protetto da IPsec. Le schede NIC che accelerano le funzioni TCP potrebbero supportare il calcolo del checksum TCP e la convalida (offload di checksum) e potrebbero essere in grado di inviare in modo efficiente buffer di dati TCP di grandi dimensioni (offload invio di grandi dimensioni). Windows 2000 e le versioni successive disattivano automaticamente queste funzioni di offload TCP nello stack TCP/IP quando il driver IPsec contiene dei filtri, anche se IPsec sta eseguendo soltanto funzioni di autorizzazione e blocco. I driver delle schede di rete privi di certificazione e firma WHQL (Windows Hardware Quality Lab) possono causare problemi quando si utilizza IPsec per la protezione del traffico. Per la certificazione dei driver NIC sviluppati per supportare l'offloading IPsec, WHQL utilizza una serie completa di test. Al fine di facilitare la risoluzione dei problemi, lo stack TCP/IP di Windows 2000, Windows XP e Windows Server 2003 supporta un'opzione della chiave del Registro di sistema che consente di disattivare tutte le forme di offloading TCP/IP. Inoltre, alcuni driver NIC supportano la possibilità di disattivare l'offloading utilizzando le proprietà avanzate della connessione alla rete. Per rendere attive le modifiche di configurazione a livello di driver, potrebbe essere necessario riavviare il computer.
  
##### Risoluzione dei problemi di perdita dei pacchetti nei protocolli IPsec
  
Può accadere che i pacchetti vengano scartati o vadano persi interferendo così sulla connettività dell'applicazione. Questa sezione prende in esame i casi più comuni in cui i pacchetti vengono scartati da IPsec. Come già menzionato, alcune periferiche di rete potrebbero non consentire il passaggio dei protocolli IP 50 o 51 o delle porte UDP 500 e 4500. Analogamente, i pacchetti IPsec incapsulati possono comportare la frammentazione di alcuni pacchetti impedendone l'attraversamento della rete. In questi casi, per individuare e comprendere quali pacchetti vengono inviati e quali ricevuti, è solitamente necessaria una traccia di monitoraggio della rete da entrambe le parti della comunicazione. Cercare eventuali ritrasmissioni distinguibili grazie alle medesime dimensioni del pacchetto che appaiano ripetutamente. Potrebbe essere necessario acquisire una traccia del comportamento tipico del protocollo in assenza di IPsec per poi confrontarla con il comportamento del protocollo in caso di traffico protetto da IPsec.
  
###### Evento di errore 4284
  
**Titolo dell'evento: errore di autenticazione Hash**
  
IKE e IPsec assicurano la protezione contro la modifica dei pacchetti durante il transito lungo la rete. Se una periferica modifica parte di un pacchetto protetto da un hash di integrità, il driver IKE o IPsec che lo riceve lo scarterà e genererà un errore di autenticazione hash che viene registrato nel Registro eventi di sistema con il numero 4285. L'esperienza dimostra che alcuni driver di rete, periferiche e dispositivi di elaborazione di terze parti talvolta danneggiano i pacchetti di una dimensione specifica, quelli con un numero specifico di frammenti, quelli di alcuni protocolli o in determinate condizioni (quali congestione della periferica, monitoraggio del traffico o riavvii). Questo errore potrebbe inoltre segnalare un attacco al pacchetto sferrato da un'applicazione dannosa o da un'applicazione che non ne ha rilevato la protezione. Potrebbe infine indicare un attacco di negazione del servizio.
  
Per rilevare i pacchetti danneggiati che vengono scartati da IPsec, è possibile utilizzare le tecniche seguenti. È tuttavia importante rapportare queste osservazioni a una traccia di monitoraggio della rete affinché sia possibile individuare l'origine del danneggiamento.
  
-   Tenere sotto controllo il contatore **Pacchetti IPsec non autenticati**. Per controllare questo contatore in Windows Server 2003, utilizzare il contatore IPsec in Performance Monitor mediante il comando `netsh ipsec dynamic show stats `oppure analizzare le statistiche nello snap-in MMC Monitor di protezione IP. In Windows XP, è possibile verificare questo contatore mediante il `ipseccmd show stats`** **comando** **oppure analizzando le statistiche nello snap-in MMC Monitor di protezione IP. Windows 2000 visualizza questo contatore nel display grafico di **ipsecmon.exe** oppure utilizzando il comando  
    `netdiag /test:ipsec /v` .
  
-   Attivare la registrazione del driver IPsec e cercare l'evento 4285 nel Registro eventi di sistema dell'IPsec di origine. Per informazioni su come attivare la registrazione del driver IPsec, vedere la sezione relativa ai toolkit del presente capitolo. Il testo dell'evento è simile al seguente:
  
    Impossibile autenticare l'hash per 5 pacchetti ricevuti da 192.168.0.10. Potrebbe essere un problema temporaneo, se il problema persiste, arrestare e riavviare il servizio Agente criteri IPSEC sul computer.  
  
Nonostante il testo dell'evento suggerisca che riavviando il servizio IPsec si potrebbe risolvere il problema, l'origine della maggior parte dei problemi di perdita di pacchetti non è IPsec. Il riavvio del servizio non risolve il problema e potrebbe invece creare altri problemi. Il servizio IPsec deve essere arrestato solo se non è possibile individuare in altro modo se un problema è correlato a IPsec o meno.
  
La risoluzione richiede pertanto un'analisi che identifichi uno schema degli indirizzi IP sorgente, gli orari della giornata, le schede o le condizioni in cui l'errore si verifica. Se il numero di pacchetti è contenuto, questo errore potrebbe non meritare un'analisi. È essenziale iniziare tentando di escludere possibili origini del danneggiamento nel sistema locale. Disattivare l'offloading IPsec, provare a disattivare le funzioni avanzate o relative alle prestazioni del driver usando la configurazione indicata in Proprietà avanzate e utilizzare i driver NIC più recenti disponibili presso il fornitore, preferibilmente quelli con certificazioni e firme WHQL (Windows Hardware Quality Lab). Analizzare quindi le caratteristiche dei percorsi di rete lungo i quali devono essere trasmessi i pacchetti. Cercare ulteriori prove di danneggiamento dei pacchetti nelle statistiche di scarto di TCP/IP e su altri computer che utilizzano la stessa configurazione. Il contatore IP **Datagrammi ricevuti scartati** incrementa tutte le volte che IPsec scarta un pacchetto.
  
**Nota:** per disattivare la funzionalità di offloading TCP/IP, utilizzare la seguente chiave del Registro di sistema per i computer che eseguono Windows 2000, Windows XP o Windows Server 2003:  
**    HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\IPSEC\\**  
**    EnableOffload DWORD impostandola su 0**  
    (questa chiave potrebbe essere visualizzata su più di una riga; nel Registro di sistema è su una sola riga),  
quindi riavviare il computer.
  
###### Evento di errore 4268
  
**Titolo dell'evento: pacchetti ricevuti con un indice parametri di protezione errato (SPI)**
  
L'implementazione di IKE in Windows 2000 e Windows XP (incluso SP1) presenta un problema noto che comporta la perdita di pacchetti in alcune condizioni specifiche. Questo problema è stato risolto in Windows Server 2003 e Windows XP SP2. L'impatto sulle comunicazioni nel protocollo di livello superiore è solitamente trascurabile perché i protocolli si aspettano comunque una perdita di pacchetti per altre ragioni. La presenza di questo problema può essere indicata dalle seguenti condizioni:
  
-   Lento ma sensibile aumento dell'incremento del contatore Pacchetti SPI errati.
  
-   Messaggi dell'evento 4268 nel Registro eventi di sistema (se attivato). Per impostazione predefinita, Windows 2000 registra questi messaggi come evento 4268 nel Registro eventi di sistema. Windows XP invece non registra questo evento per impostazione predefinita; è necessario attivare la registrazione a livello di driver. Il testo dell'evento è simile al seguente:
  
    "Ricevuti da &lt;indirizzo IP&gt; &lt;numero&gt; pacchetti con un indice parametri di protezione errato. Potrebbe essere un problema temporaneo, se il problema persiste, arrestare e riavviare il servizio Agente criteri IPSEC sul computer."  
  
Nonostante il testo dell'evento suggerisca che riavviando il servizio IPsec si potrebbe risolvere il problema, l'origine di questo tipo di perdita di pacchetti è da farsi risalire alla configurazione del sistema IPsec. Il riavvio del servizio non risolve il problema e potrebbe invece creare altri problemi. Come sopra menzionato, il servizio IPsec deve essere arrestato soltanto se non è possibile individuare in altro modo se un problema è correlato a IPsec o meno.
  
L'indice dei parametri di protezione (SPI, Security Parameter Index) di IPsec è un'etichetta del pacchetto che comunica al risponditore quale associazione di protezione deve essere utilizzata per l'elaborazione. Se un SPI non viene riconosciuto, il sistema lo definisce "SPI errato". Questo errore indica che il computer ha ricevuto dei pacchetti formattati IPsec, ma non dispone della SA IPsec necessaria per elaborarli e, di conseguenza, li scarta.
  
Nonostante i pacchetti vengano scartati, questi messaggi di errore sono benigni. Il numero di eventi generati per SPI errati dipende dal carico di lavoro dei computer nel momento specifico e dalla velocità di trasmissione dei dati protetti da IPsec al momento della reimpostazione delle chiavi. Le condizioni seguenti possono generare altri eventi di questo tipo:
  
-   Trasferimento di volumi elevati di traffico IPsec su connessioni a 1 Gigabit o più veloci.
  
-   Server con elevati carichi di lavoro (lenti) e client veloci.
  
-   Client che comunicano a bassa velocità con server veloci.
  
-   Numerosi client attivi per un solo server con reimpostazione costante delle chiavi da parte di IKE per vari client simultaneamente.  
  
Ne consegue che la connessione TCP protetta da IPsec rallenta per alcuni secondi al fine di ritrasmettere i dati perduti. In caso di perdita di numerosi pacchetti, il protocollo TCP potrebbe attivare la modalità anti-congestione sulla connessione specifica. Entro alcuni secondi, la connessione dovrebbe quindi tornare alla piena velocità. File copy, Telnet, Terminal Server e altre applicazioni basate su TCP non dovrebbero notare la perdita di questo numero esiguo di pacchetti. Tuttavia, si sono verificati alcuni casi in cui TCP ha perduto numerosi pacchetti su un collegamento veloce e ha dovuto ripristinare la connessione. Ripristinando la connessione, il socket viene chiuso e le applicazioni ricevono una notifica di interruzione della connessione che potrebbe interrompere i trasferimenti di file.
  
La causa più comune di questo errore è un problema noto di Windows 2000 relativo alla modalità di sincronizzazione adottata da IKE per la crittografia delle SA IPsec. Se in modalità rapida IKE l'iniziatore è più rapido del risponditore, l'iniziatore sarà in grado di inviare nuovi pacchetti IPsec protetti dalle SA più rapidamente di quando il risponditore non riesca a riceverli. Come riportato nella specifica Request for Comment (RFC) di IETF (Internet Engineering Task Force), quando IKE stabilisce una nuova coppia di associazioni di protezione IPsec, l'iniziatore deve utilizzare la nuova SA IPsec in uscita per trasmettere i dati, ma il risponditore lento riceverà un traffico protetto da IPsec che non è ancora in grado di riconoscere. Poiché la reimpostazione delle chiavi IKE dipende sia dal tempo trascorso che dalla quantità di dati inviati utilizzando una SA IPsec, gli eventi di tipo SPI errato possono verificarsi periodicamente (anche se non a intervalli specifici).
  
Negli scenari di interoperabilità con client di terze parti, un errore di tipo SPI errato potrebbe indicare che un peer IPsec non ha accettato ed elaborato un messaggio di eliminazione o che non è riuscito a completare l'ultima fase della negoziazione in modalità rapida IKE. L'errore potrebbe inoltre indicare che un pirata informatico sta sovraccaricando un computer inserendo o falsificando pacchetti IPsec. Il driver IPsec conteggia questi eventi e li registra al fine di conservare un registro delle attività con SPI errati.
  
Per analizzare e ridurre il numero di questi eventi, è possibile utilizzare la chiave **LogInterval** del Registro di sistema. Durante il processo di risoluzione dei problemi, impostare questa chiave sul valore minimo (ogni 60 secondi) affinché gli eventi vengano registrati rapidamente. Per ricaricare il driver IPsec in Windows 2000, è possibile interrompere e riavviare il servizio Agente criteri IPSEC. In Windows XP e Windows Server 2003, è invece necessario riavviare il computer per ricaricare i driver TCP/IP e IPsec.
  
In Windows 2000, non è possibile eliminare questi eventi tramite patch o impostazioni della chiave del Registro di sistema. Per impostazione predefinita, Windows XP e Windows Server 2003 non generano report su questi eventi. È possibile attivare la creazione di report relativi a questi eventi impostando la configurazione IPsecDiagnostics tramite l'opzione netsh ipsec della riga di comando o direttamente mediante la chiave del Registro di sistema.
  
Le tecniche seguenti consentono di ridurre al minimo questi errori:
  
-   Adattare le impostazioni dei criteri IPsec. Aumentare le durate della modalità rapida (se i requisiti di protezione lo consentono) fino a 21 o 24 ore (le SA IPsec inattive vengono eliminate entro 5 minuti, se non utilizzate). Per evitare potenziali punti deboli della protezione introdotti dall'utilizzo della medesima chiave per la crittografia di un volume elevato di dati, non impostare una durata superiore a 100 MB in caso di crittografia ESP.
  
-   Utilizzare l'impostazione PFS (Perfect Forward Secrecy) delle modalità principale e rapida così da evitare il problema per la SA IPsec specifica in fase di negoziazione. Tuttavia, entrambe le impostazioni precedenti aumentano sensibilmente il carico dei computer che servono numerosi client e quindi potrebbero contribuire a ritardare la risposta in altre negoziazioni.
  
-   Potenziare la CPU o altri componenti hardware per migliorare le prestazioni oppure ridurre i carichi delle applicazioni.
  
-   Se non è già presente, installare una scheda NIC per l'accelerazione hardware di IPsec. Queste schede riducono in modo sostanziale l'utilizzo della CPU da parte di IPsec per il trasferimento di dati ad alta velocità.
  
-   Se l'utilizzo della CPU rimane elevato, considerare la possibilità di ricorrere a prodotti di accelerazione hardware che possano velocizzare i calcoli Diffie-Hellman. Questi prodotti sono solitamente delle schede PCI con funzionalità di ripartizione esponenziale del carico che accelerano i calcoli Diffie-Hellman. Questo tipo di accelerazione ha effetti positivi anche sulla gestione delle chiavi pubbliche e private per i certificati che utilizzano il protocollo SSL (Secure Sockets Layer). Verificare con il fornitore che la scheda supporti specificatamente l'interfaccia ModExpoOffload in CAPI per i calcoli Diffie-Hellman.
  
-   Creare, se possibile, un filtro che autorizzi un certo volume di traffico ad alta velocità che non necessiti della protezione IPsec (ad esempio, il traffico di backup del server su una LAN dedicata).
  
Se queste soluzioni non danno esito positivo e non è possibile eseguire l'aggiornamento a Windows XP SP2 o Windows Server 2003, contattare il servizio di supporto tecnico Microsoft per verificare se sono disponibili altre opzioni.
  
###### Evento di errore 4284
  
**Titolo dell'evento: pacchetti in chiaro che avrebbero dovuto essere protetti**
  
Questo evento indica che è stata stabilita un'associazione di protezione IPsec in un momento in cui i pacchetti ricevuti non erano crittografati, mentre dovevano essere protetti all'interno di un'associazione di protezione IPsec. Questi pacchetti vengono scartati per impedire gli attacchi basati sull'inserimento di pacchetti nelle connessioni protette da IPsec. Nonostante il contatore IP **Datagrammi ricevuti scartati** venga incrementato, IPsec non dispone di un valore di conteggio specifico che registri i pacchetti scartati per questa ragione. Questo problema può essere individuato soltanto mediante l'errore 4284 nel Registro eventi di sistema, che visualizza il messaggio:
  
Ricevuti da &lt;indirizzo IP&gt; &lt;numero&gt; pacchetti in chiaro che avrebbero dovuto essere protetti.
  
Potrebbe essere un problema temporaneo, se il problema persiste, arrestare e riavviare il servizio Agente criteri IPSEC sul computer."
  
Come per gli errori precedenti, non si devono seguire i suggerimenti dell'evento. È improbabile che il riavvio del servizio IPsec risolva il problema.
  
La causa più probabile dell'errore è un problema di configurazione del criterio che fa sì che una parte invii dati in modalità non crittografata a causa di un filtro di autorizzazione in uscita più specifico. Se, ad esempio, un client utilizza un filtro per proteggere tutto il traffico con un server e il criterio del server include un filtro più specifico che autorizza tutte le risposte HTTP non crittografate, il server proteggerà tutto il traffico verso il client, fatta eccezione per i pacchetti HTTP in uscita. Il client riceverà questi pacchetti e li scarterà per problemi di protezione poiché si aspetta che tutto il traffico da e verso il server sia protetto all'interno di una coppia di SA IPsec.
  
Questo evento può verificarsi anche durante il normale funzionamento e nei casi di interoperabilità con client di terze parti quando un peer elimina un'associazione di protezione IPsec o un filtro del driver IPsec mentre il traffico scorre fra i due computer. Ad esempio, una delle due parti potrebbe annullare l'assegnazione del criterio IPsec o essere sottoposta a un aggiornamento dei criteri che elimina le SA e i filtri IPsec. Poiché una delle due parti ha eliminato il filtro mentre è in corso la comunicazione su un protocollo di livello superiore, il messaggio di eliminazione di IKE potrebbe non essere recapitato ed elaborato dall'altro peer prima che arrivino i pacchetti in chiaro e quindi si potrebbe generare l'errore. Si consideri che il tempo necessario a elaborare il messaggio di eliminazione dipende dal carico corrente del computer peer.
  
Il messaggio di errore potrebbe presentarsi anche quando viene caricato un criterio di grandi dimensioni poiché le associazioni di protezione IPsec potrebbero diventare attive prima che al driver IPsec venga applicata la serie completa di filtri. Se si verifica questa condizione, potrebbero aver luogo negoziazioni di SA IPsec relative a un traffico che sarà esentato quando il caricamento del criterio verrà completato.
  
Il messaggio di errore può inoltre indicare un attacco con inserimento di traffico non crittografato che corrisponde (volutamente o casualmente) ai selettori di traffico di una particolare associazione di protezione attiva in ingresso.
  
Questo problema deve essere assegnato al responsabile della configurazione dei criteri IPsec.
  
###### Timeout NAT-T IPsec in caso di connessione con le reti wireless
  
È stato recentemente individuato un problema che causa il timeout delle connessioni quando computer client basati su Windows Server 2003 o Windows XP tentano di connettersi a un server tramite una rete wireless che utilizza NAT-T IPsec. Per ulteriori informazioni, consultare l'articolo numero [885267](http://support.microsoft.com/?kbid=885267) della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/?kbid=885267 (in lingua inglese).
  
#### Verifica della correttezza dei criteri IPsec
  
Questa sezione illustra i passaggi da eseguire per rilevare i problemi di assegnazione e interpretazione dei criteri IPsec. Affinché IPsec autorizzi e blocchi i pacchetti e avvii le negoziazioni IKE delle SA IPsec con gli indirizzi IP remoti per proteggere il traffico, nel driver IPsec devono essere presenti i filtri di criteri IPsec correttamente interpretati. Per guidare l'azione di IKE come risponditore, è inoltre necessario utilizzare filtri appropriati. In questa soluzione, la configurazione dei criteri IPsec prevede la protezione di tutto il traffico (eccetto quello ICMP) tramite IPsec. Il criterio contiene inoltre dei filtri per ciascun indirizzo IP incluso nell'elenco di esenzioni.
  
**Nota:** in Windows 2000, il servizio IPsec è denominato Agente criteri IPsec; in Windows XP e Windows Server 2003 è invece denominato Servizio IPsec.
  
Il personale del supporto tecnico deve conoscere come IPsec utilizza Criteri di gruppo, la precedenza dei criteri IPsec e la loro interpretazione. Ulteriori informazioni su questi argomenti sono reperibili nella sezione "Ulteriori informazioni" alla fine del presente capitolo.  
  
##### Risoluzione dei problemi di Criteri di gruppo per IPsec
  
Criteri di gruppo è un meccanismo che consente di assegnare ai membri di un dominio criteri IPsec basati sul dominio. Per assegnare un criterio IPsec a un computer host, è necessario che il membro del dominio recuperi gli oggetti Criteri di gruppo (GPO) assegnati. Eventuali problemi di recupero dei GPO impediranno, pertanto, al computer di applicare il criterio IPsec appropriato. I problemi più comuni di Criteri di gruppo per la gestione dei criteri IPsec includono:
  
-   Ritardi di replica da parte di vari componenti di configurazione di Active Directory
  
-   Problemi del processo di polling e download di Criteri di gruppo
  
-   Confusione in merito alla versione del criterio IPsec assegnato
  
-   Servizio IPsec non in esecuzione
  
-   Impossibilità di recuperare il criterio IPsec in Active Directory con conseguente utilizzo di una copia archiviata nella cache
  
-   Ritardi derivanti dal polling dei criteri IPsec per il recupero del criterio IPsec assegnato
  
La replica potrebbe essere ritardata a causa della presenza di numerosi oggetti correlati a IPsec in Active Directory, quali ad esempio criteri IPsec, GPO, modifiche degli attributi nelle assegnazioni dei GPO e nei criteri IPsec e informazioni sull'appartenenza a un gruppo di protezione. Sarà quindi necessario eseguire una pianificazione accurata che consenta di valutare l'impatto delle modifiche di configurazione, mentre vengono gradualmente applicate ai membri del dominio.
  
Per le procedure di risoluzione dei problemi di Criteri di gruppo, consultare i seguenti white paper:
  
-   [Troubleshooting Group Policy in Windows 2000](http://support.microsoft.com/?kbid=810739) , disponibile all'indirizzo http://support.microsoft.com/?kbid=810739 (in lingua inglese).
  
-   [Troubleshooting Group Policy in Microsoft Windows Server](http://www.microsoft.com/downloads/details.aspx?familyid=b24bf2d5-0d7a-4fc5-a14d-e91d211c21b2&displaylang=en) disponibile all'indirizzo www.microsoft.com/downloads/details.aspx?  
    FamilyId=B24BF2D5-0D7A-4FC5-A14D-E91D211C21B2&displaylang=en.  
  
L'assegnazione dei criteri IPsec basati sul dominio avviene mediante due componenti:
  
-   Lo snap-in MMC Gestione criteri di protezione IP (un'estensione dello snap-in MMC Criteri di protezione locali) per l'assegnazione di un criterio IPsec nell'oggetto GPO
  
-   L'Estensione criteri gruppo lato client (CSE, Client Side Extension) per IPsec (implementata in **gptext.dll**), che elabora le informazioni IPsec nel GPO  
  
Lo snap-in MMC Gestione criteri di protezione IP assegna il criterio a un GPO archiviando le informazioni del criterio IPsec selezionato nel componente IPsec del GPO, definito nome distinto (DN) LDAP:
  
**CN=IPSEC,CN=Windows,CN=Microsoft,CN=Computer,CN={GPOGUID},**  
**CN=Criteri,CN=Sistema,DC=dominio,DC=Woodgrove,DC=com**
  
Il DN LDAP del criterio IPsec assegnato viene archiviato nell'attributo ipsecOwnersReference del GPO.
  
Quando Criteri di gruppo recupera l'elenco dei GPO da applicare al computer, i GPO che contengono le assegnazioni dei criteri IPsec vengono archiviati nel GUID del Registro di sistema per l'estensione lato client IPsec nella seguente posizione:
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft**  
**\\Windows\\CurrentVersion\\Group Policy**  
**\\History\\{e437bc1c-aa7d-11d2-a382-00c04f991e27}**
  
La CSE IPsec viene attivata dalla CSE del criterio di sicurezza quando nel GPO è presente un'assegnazione di un criterio IPsec. In caso di problemi nell'elaborazione del criterio di sicurezza, potrebbero verificarsi anche errori di elaborazione del criterio IPsec. Per individuare il GUID per ciascuna estensione criteri di gruppo, cercare nella posizione seguente del Registro di sistema:
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft**  
**\\WindowsNT\\CurrentVersion\\WinLogon\\GPExtensions**
  
I GUID correlati alla distribuzione IPsec per le CSE criteri gruppo lato client sono i seguenti:
  
-   Protezione. {827D319E-6EAC-11D2-A4EA-00C04F79F83A}
  
-   Protezione IP.{E437BC1C-AA7D-11D2-A382-00C04F991E27}
  
-   Script. {42B5FAAE-6536-11D2-AE5A-0000F87571E3}
  
Le CSE IPsec copiano il nome distinto LDAP e le informazioni sull'assegnazione del criterio IPsec nella seguente chiave del Registro di sistema:
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\**  
**IPSec\\GPTIPSECPolicy**
  
Se le assegnazioni dei criteri IPsec sono contenute in vari GPO, la CSE IPsec viene richiamata per ciascun GPO. Le regole di precedenza dei GPO si applicano all'ordine in cui la CSE IPsec riceve i GPO da elaborare. Questo ordine può essere modificato tramite impostazioni all'interno dei GPO stessi e tramite ACL di lettura che impediscono il recupero di alcuni GPO assegnati. Tutte le volte che la CSE IPsec viene richiamata, le informazioni relative a IPsec presenti nel GPO (incluso il DN) vengono sovrascritte in questa chiave del Registro di sistema. Quando l'elaborazione di tutti i GPO viene completata, la CSE segnala al servizio IPsec che è stato assegnato un criterio IPsec basato sul dominio. Il servizio IPsec legge quindi il valore **GPTIPsecPolicy\\DSIPSECPolicyPath** per recuperare il criterio IPsec corretto.
  
Il servizio IPsec continua a eseguire il polling per rilevare eventuali modifiche del criterio IPsec assegnato, basandosi sull'ultimo orario di aggiornamento di uno qualsiasi degli oggetti di directory del criterio IPsec assegnato. Il servizio gestisce il criterio IPsec archiviato nella cache come criterio di dominio più recente.
  
Esiste un problema noto che comporta la perdita di sincronizzazione fra il nome del criterio IPsec assegnato e il nome del criterio IPsec effettivamente in uso (e archiviato nella cache). Il servizio IPsec non aggiorna le informazioni nella chiave **GPTIPsecPolicy** del Registro di sistema, quali ad esempio **DSIPSECPolicyName**, e il nome del criterio IPsec viene modificato soltanto quando la CSE IPsec viene richiamata. La CSE IPsec viene però richiamata solo in caso di modifica dell'attributo DN di assegnazione del criterio IPsec nel GPO. Questo valore del Registro di sistema viene utilizzato dallo snap-in MMC del monitor IPsec e dagli strumenti della riga di comando per creare report del nome del criterio IPsec assegnato. Gli strumenti IPsec potrebbero quindi indicare il nome dell'ultimo criterio IPsec elaborato dalla CSE e non quello in uso. Esistono numerose soluzioni a questo problema; per ulteriori informazioni, consultare la sezione "Versioni dei criteri" nel capitolo 5, "Creazione dei criteri IPsec per gruppi di isolamento", di questa guida.
  
**Nota:** Microsoft consiglia di utilizzare per i criteri IPsec delle convenzioni di denominazione che includano un numero di versione affinché sia possibile risalire facilmente alla versione applicata. Se, invece, il nome del criterio rimane invariato, non sarà possibile rilevare facilmente le modifiche correlate alle versioni.
  
Quando non viene assegnato il criterio IPsec appropriato, anche dopo un aggiornamento forzato dei criteri di gruppo, gli errori del Registro applicazioni dalle origini **Userenv** o **SceCli** segnalano problemi di elaborazione di Criteri di gruppo. Per analizzare a fondo questo problema, è necessario attivare la registrazione di Criteri di gruppo. Esistono numerosi diversi tipi di livelli di registrazione e registri per Criteri di gruppi. I registri per la CSE di protezione sono necessari per verificare eventuali errori di elaborazione dei criteri di protezione, nonché eventuali errori rilevati dalla CSE IPSec. Non esiste alcun registro specifico per la CSE IPsec. Le tracce di monitoraggio della rete potrebbero essere utili per acquisire il traffico al momento dell'aggiornamento dei criteri di gruppo al fine di verificare quale indirizzo IP dei controller di dominio viene utilizzato per il recupero di ciascun oggetto. I problemi possono includere:
  
-   Problemi di replica o ritardi che rendono impossibile il reperimento degli oggetti
  
-   Logica di bilanciamento del carico del servizio di individuazione dei controller di dominio, che potrebbe comportare il recupero di un oggetto GPO da un controller di dominio, mentre la query LDAP per il criterio IPsec assegnato viene recuperata da un controller diverso nello stesso sito.
  
Per creare un file di registro dettagliato per la CSE di protezione, utilizzare la seguente chiave del Registro di sistema:
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft**  
**\\WindowsNT\\CurrentVersion\\CurrentVersion\\Winlogon**  
**\\GpExtensions\\{827d319e-6eac-11d2-a4ea-00c04f79f83a}\\**
  
Impostare la voce **ExtensionDebugLevel** su un valore **REG\_DWORD** di 0x2.
  
Il file di registro verrà creato in **%windir%\\Security\\Logs\\Winlogon.log**.
  
**Nota:** una voce DNS non valida potrebbe indicare che i criteri di gruppo non vengono scaricati da Active Directory, anche se l'accesso del computer e dell'utente sono stati completati. Per ulteriori informazioni sui problemi relativi a DNS, consultare la sezione "Problemi di risoluzione dei nomi" descritta in precedenza.
  
##### Risoluzione dei problemi del servizio IPsec
  
Il servizio IPsec non deve necessariamente essere in funzione per utilizzare lo snap-in MMC Gestione criteri di protezione IP. Tuttavia, se un amministratore assegna un criterio locale, la colonna **Criterio assegnato** visualizzerà un errore.
  
Il servizio IPsec potrebbe essere interrotto durante l'avvio se si verificano i seguenti problemi comuni:
  
-   **Computer avviato in modalità provvisoria o di ripristino di Active Directory**. In questi casi, il driver IPsec fornirà per impostazione predefinita una comunicazione in uscita in modalità di stato, se è stato assegnato un criterio IPsec. La connettività in ingresso viene bloccata, a meno che non sia configurata un'esenzione di tipo bootexemption.
  
-   **IKE non ha acquisito il controllo esclusivo delle porte UDP 500 e 4500**. Utilizzare netstat –bov per visualizzare i processi e i moduli di codice per ciascuna porta. Il comando portqry –local –v fornisce un maggior numero di dettagli. Potrebbero essere installati alcuni provider LSP (Layered Service Providers) Winsock che interferiscono con IPsec. Per ulteriori informazioni sugli LSP e IPsec, consultare la sezione* *"Risoluzione dei problemi correlati alle applicazioni" più avanti nel presente capitolo.
  
-   **Criterio IPsec danneggiato**. Non è stato possibile leggere o applicare interamente il criterio IPsec assegnato con conseguente segnalazione di numerosi errori da parte del servizio IPsec. Questi errori non interrompono il servizio, ma possono causare interruzioni delle comunicazioni in vari modi, ad esempio, bloccando Criteri di gruppo e impedendo al servizio IPsec di recuperare i criteri corretti. In Windows XP e Windows Server 2003, è necessario configurare con la massima attenzione criteri permanenti o locali "sicuri" da applicare in caso di errori nell'applicazione di criteri basati sul dominio. Sia i criteri permanenti che quelli di avvio del computer (esenzioni di tipo bootmode) devono rientrare nell'analisi del processo di risoluzione. Questi criteri devono consentire l'accesso remoto al computer tramite altri mezzi, nel caso in cui siano i soli criteri applicati a causa di altre condizioni di errore.
  
L'implementazione di Windows 2000 IPsec utilizza un modulo denominato Archivio criteri IPsec (**polstore.dll**), che consente all'Agente criteri IPsec e allo snap-in MMC Gestione criteri di protezione IP di utilizzare un modulo per accedere a tutte le tre posizioni di archiviazione dei criteri supportate: locale, computer remoto e Active Directory. Questa configurazione è stata modificata e migliorata in Windows XP e Windows Server 2003 tramite l'aggiunta di nuovi tipi di criteri IPsec (criterio di avvio e criterio permanente) e del componente database dei criteri di protezione (SPD, Security Policy Database) che gestisce lo stato di runtime del criterio IPsec per le query di monitoraggio di IPsec e le query IKE. Questa modifica dell'architettura comporta una variazione del testo degli eventi IPsec registrati in Windows XP e Windows Server 2003 rispetto a Windows 2000. Tale modifica a livello di architettura ha reso necessarie modifiche significative anche alle interfacce RPC utilizzate per la gestione remota. In Windows Server 2003, le interfacce RPC sono state ulteriormente aggiornate. Di conseguenza, lo snap-in MMC Gestione criteri di protezione IP non è in grado di connettersi a computer remoti su cui non è installata la medesima versione del sistema operativo. Inoltre, il modello di protezione per Windows XP SP2 e Windows Server 2003 SP1 è stato sostanzialmente modificato per limitare le connessioni RPC remote e per l'attivazione predefinita di Windows Firewall. Per ulteriori informazioni, consultare [Changes to Functionality in Microsoft Windows XP Service Pack 2 - Part 2: Network Protection Technologies](http://technet.microsoft.com/en-us/library/bb457156.aspx), disponibile all'indirizzo www.microsoft.com/technet/prodtechnol/winxppro/  
maintain/sp2netwk.mspx.
  
A causa di queste modifiche, le interfacce RPC remote per il servizio IPsec sono state disattivate come misura di sicurezza. Gli snap-in MMC del monitor IPsec e Gestione criteri di protezione IP non sono quindi in grado di effettuare il monitoraggio remoto su questi computer. La gestione remota di IPsec deve essere effettuata utilizzando le connessioni desktop remoto (Terminal Server) che eseguono gli snap-in MMC di IPsec come processi locali.
  
In Windows 2000, il driver IPsec viene caricato per impostazione predefinita al termine del processo di avvio dal servizio Agente criteri. Il driver IPsec non partecipa quindi all'elaborazione dei pacchetti IP fino a quando l'Agente criteri non lo informa per la prima volta che esiste un criterio attivo. In assenza di un criterio IPsec attivo, il driver IPsec non viene incluso nell'elaborazione del traffico IP in ingresso e in uscita. In Windows XP e Windows Server 2003, questa configurazione è stata migliorata in modo che il driver IPsec venga caricato dal driver TCP/IP durante il processo di avvio. In questo caso, il driver non elabora i pacchetti fino a quando il servizio IPsec non completa il caricamento dei filtri.
  
In Windows 2000, l'Agente criteri IPsec potrebbe registrare degli errori di avvio del servizio. Questi errori includono:
  
-   **Impossibile avviare l'Agente criteri di protezione IP. Non verrà imposto alcun criterio di protezione IP**. Questo errore è presumibilmente causato da problemi riscontrati dall'Agente criteri IPsec durante la propria registrazione nel sottosistema RPC. Può inoltre essere causato dalla mancata inizializzazione di IKE a causa di provider LSP Winsock di terze parti.
  
-   **Il server RPC dell'Agente criteri non è stato in grado di...**
  
    -   **registrare la sequenza di protocollo**
  
    -   **registrare l'interfaccia**
  
    -   **registrare i binding dell'interfaccia**
  
    -   **registrare l'endpoint dell'interfaccia**
  
    -   **registrare i meccanismi di autenticazione**
  
    -   **eseguire l'ascolto**
  
    Questi errori possono essere causati da modifiche a impostazioni di protezione avanzate o da problemi interni del servizio RPC che impediscono all'Agente criteri IPsec di completare l'inizializzazione all'avvio del servizio. L'Agente criteri IPsec non funzionerà correttamente, potrebbe bloccarsi o chiudersi.
  
-   **Impossibile avviare l'Agente criteri. Impossibile connettersi al database SCM. Errore: &lt;numero&gt;**. Il servizio IPsec non è riuscito ad aprire il database di Gestione controllo servizio, presumibilmente perché il servizio IPsec è stato configurato per l'esecuzione come account di servizio non privilegiato. Deve essere eseguito come sistema locale. In caso contrario, analizzare i problemi di Gestione controllo servizio.
  
-   **L'Agente criteri non ha potuto connettersi al driver IPSEC**. Non è stato possibile caricare il driver IPsec e interfacciarlo con lo stack TCP/IP. Windows 2000 è configurato per eseguire questa operazione all'avvio del servizio IPsec. Potrebbero essere presenti software di terze parti che impediscono la connessione oppure potrebbero risultare mancanti dei moduli di codice del sistema operativo necessari per questa funzionalità.
  
-   **L'Agente criteri non ha potuto caricare i criteri IPSEC**. Si è verificato un errore mentre l'Agente criteri IPsec stava caricando tutti i filtri sul driver IPsec. Questo errore può essere causato da memoria del kernel insufficiente o da un utilizzo non corretto del driver IPsec. Se il problema persiste, contattare il servizio di supporto tecnico Microsoft.
  
-   **L'Agente criteri non ha potuto avviare il servizio ISAKMP**. Questo errore solitamente si verifica perché IKE non riesce ad acquisire il controllo esclusivo delle porte UDP 500 o 4500 in quanto queste porte vengono già utilizzate da un altro servizio. Può essere causato anche da un software di protezione di terze parti, che impedisce l'allocazione delle porte della rete, o dal fatto che il servizio IPsec non viene eseguito nel contesto del sistema locale.
  
-   **Impossibile rilevare il nome principale SSPI per il servizio ISAKMP/Oakley**. Windows 2000 registra questo messaggio quando non è possibile eseguire la chiamata di funzione QueryCredentialsAttributes dell'interfaccia SSPI (Security Support Provider Interface). Questo errore potrebbe indicare che il computer non è in grado di completare l'accesso al dominio.
  
-   **Impossibile ottenere le credenziali del server Kerberos per il servizio ISAKMP/Oakley**. Questo messaggio di errore di Windows 2000 si verifica tipicamente quando si avvia il servizio IPsec (presumibilmente, all'avvio del computer) su una rete remota a cui viene assegnato un criterio IPsec (presumibilmente, dalla cache del Registro di sistema di un criterio di dominio) che richiede l'autenticazione Kerberos e non è disponibile un controller di dominio. Conseguentemente, l'autenticazione Kerberos non funziona. Sulla rete interna, questo evento verrà caricato su un computer che non è membro del dominio o che non riesce a raggiungere i controller di dominio utilizzando il protocollo Kerberos durante l'inizializzazione del servizio IPsec.
  
-   **Impossibile imporre un criterio di comunicazioni protette a causa dell'impossibilità di avviare il driver di protezione IP. Rivolgersi immediatamente all'amministratore di sistema**. Questo errore è causato da un problema di caricamento del driver IPsec, di binding allo stack TCP/IP o di inizializzazione prima di tentare l'aggiunta del criterio. La causa può essere un danneggiamento del file o problemi di autorizzazione. Cercare di individuare le impostazioni di protezione e software di protezione di terze parti che possono impedire il caricamento del driver. Se durante l'inizializzazione non è possibile verificare le firme **FIPS.sys** interne, il software non verrà caricato così come il driver IPsec. L'errore di firma **FIPS.sys** rende necessaria la sostituzione con il file binario originale firmato o con un nuovo file binario fornito da Microsoft. Riavviare il computer. Se il problema persiste, contattare il servizio di supporto tecnico Microsoft.  
  
In Windows XP e Windows Server 2003, i seguenti eventi di errore del servizio IPsec indicano che non è possibile avviare il servizio:
  
-   **I servizi IPSec non hanno inizializzato il driver IPSec; codice di errore: &lt;numero&gt;. Impossibile avviare i servizi IPSec**. Il driver IPsec non ha completato il caricamento. Se il problema persiste, contattare il servizio di supporto tecnico Microsoft.
  
-   **I servizi IPSec non hanno inizializzato il modulo IKE; codice di errore: &lt;numero&gt;. Impossibile avviare i servizi IPSec**. Le cause più comuni di questo problema sono i provider LSP Winsock di terze parti che impediscono a IKE di utilizzare alcune opzioni del socket. Questo errore si verifica anche quando IKE non riesce ad acquisire il controllo esclusivo delle porte UDP 500 e 4500.
  
-   **I servizi IPSec non hanno inizializzato il server RPC; codice di errore: &lt;numero&gt;. Impossibile avviare i servizi IPSec**. Il servizio IPsec dipende dal sottosistema RPC per la comunicazione interprocesso fra IKE, SPD e l'Agente criteri. Per verificare che RPC stia funzionando correttamente, utilizzare le tecniche specifiche di risoluzione dei problemi. Dopo aver riavviato il computer, se i problemi permangono, contattare il servizio di supporto tecnico Microsoft.
  
-   **È stato rilevato un errore critico da parte dei servizi IPSec e sono stati interrotti; codice di errore: &lt;numero&gt;. L'interruzione dei servizi IPSec può rappresentare un potenziale pericolo per il sistema. Contattare l'amministratore del sistema per riavviare il servizio**. Nel servizio IPsec si è verificato l'errore, indicato dal numero nel testo dell'evento, e il servizio ha cessato di funzionare. Il driver IPsec è ancora caricato e si trova in modalità normale (applicazione dei filtri dei criteri IPsec) o di blocco. Un evento separato indicherà se è stata attivata la modalità di blocco sul driver. Se il driver si trova invece in modalità normale, le operazioni filtro di autorizzazione e blocco funzioneranno ancora come previsto. I filtri con un'operazione di negoziazione si limitano a scartare il traffico a causa della non disponibilità di IKE.
  
-   **I servizi IPSec hanno attivato la modalità di blocco per il driver IPSec a causa di errori precedenti; codice errore &lt;numero&gt;**. Questo messaggio segnala che è stata attivata la modalità di blocco per il driver IPsec come misura di sicurezza a seguito di errori rilevati nell'elaborazione dei criteri IPsec. Questo comportamento è disponibile solo in Windows Server 2003. Nella modalità di blocco rimangono comunque attive le esenzioni in ingresso configurate utilizzando il comando netsh ipsec.  
  
##### Risoluzione dei problemi di recupero dei criteri IPsec
  
Per il download dei criteri IPsec assegnati per tutte le piattaforme, il servizio IPsec utilizza una query LDAP TCP autenticata e crittografata. Sono disponibili opzioni per la firma e il sigillo LDAP mediante la chiave di sessione Kerberos. Il servizio IPsec in esecuzione come sistema locale deve quindi essere in grado di ottenere un ticket di servizio Kerberos per il servizio LDAP sul server di Active Directory. Se la CSE IPsec conferma l'archiviazione del criterio IPsec assegnato nella chiave **GPTIPsecPolicy** del Registro di sistema e il servizio IPsec è in esecuzione, i problemi seguenti potrebbero non consentire al servizio stesso di recuperare il criterio da Active Directory:
  
-   Problemi di comunicazione con i controller di dominio
  
-   Problemi di accesso all'account computer di controller di dominio
  
-   Problemi di emissione dei ticket Kerberos
  
-   Problemi di disponibilità del servizio LDAP
  
-   Problemi di individuazione di uno specifico criterio IPsec o di oggetti richiesti dalla query LDAP
  
-   Problemi di autorizzazioni di lettura per uno qualsiasi degli oggetti richiesti del criterio IPsec
  
-   Danneggiamenti causati da problemi durante il salvataggio degli oggetti in archivio o da eliminazioni accidentali o intenzionali degli oggetti archiviati  
  
    **Nota**: se i criteri IPsec creati in Windows XP o Windows Server 2003 utilizzano nuove funzionalità rese disponibili in queste versioni e vengono successivamente modificati e salvati con lo snap-in MMC Gestione criteri di protezione di Windows 2000, le nuove funzionalità potrebbero venire eliminate senza segnalazione. Se, invece, un sistema Windows 2000 recupera un criterio IPsec con funzionalità aggiuntive, si limiterà a ignorarle con conseguente possibile variazione del comportamento del criterio stesso quando viene applicato sul sistema Windows 2000.
  
Un problema noto dello snap-in MMC Gestione criteri di protezione IP si verifica quando si gestiscono i criteri IPsec in Active Directory o su un computer remoto. Quando lo snap-in MMC viene eseguito su un collegamento lento, potrebbe essere necessario un tempo relativamente lungo per salvare tutte le modifiche di un criterio di grandi dimensioni. Se la finestra dello snap-in MMC si chiude, eventuali oggetti o modifiche che non sono ancora stati salvati andranno perduti. Questa condizione potrebbe danneggiare il criterio IPsec. Se si esegue lo snap-in MMC Gestione criteri di protezione IP su un collegamento lento, utilizzare una sessione Desktop remoto per eseguirlo come processo locale.
  
In generale, è necessario testare qualsiasi script per strumenti della riga di comando che crea un criterio IPsec. Per eseguire il test, creare un criterio nell'archivio locale e verificarne l'integrità visualizzandolo con lo snap-in MMC Gestione criteri di protezione IP. I computer di test dovranno essere utilizzati per applicare il criterio IPsec locale e analizzare i dettagli nello snap-in MMC del monitor IPsec al fine di verificare che l'ordinamento dei filtri operi come previsto.
  
Le procedure di risoluzione ed eliminazione degli errori di lettura e danneggiamento dei criteri IPsec dipendono dalla posizione di archiviazione. Questa soluzione utilizza soltanto criteri IPsec basati sul dominio, ma è possibile che altri tipi di criteri IPsec vengano configurati in modo da causare problemi.
  
Nella parte restante di questa sezione vengono analizzate le procedure di risoluzione dei problemi per ciascun tipo di criterio. Solitamente, il supporto di 2° livello deve essere in grado di utilizzare gli strumenti della riga di comando e quelli dell'interfaccia grafica per verificare che sia stato recuperato il criterio IPsec appropriato e che questo criterio venga correttamente interpretato. Di seguito vengono illustrati i passaggi necessari per eliminare ciascun tipo di criterio al fine di consentire l'installazione di criteri corretti tramite l'aggiornamento. Se gli script non sembrano recuperare o installare i criteri corretti, il problema deve essere assegnato al 3° livello.
  
###### Criteri IPsec di avvio
  
L'utilità Netsh consente la configurazione delle opzioni bootmode e bootexemption, supportate soltanto da Windows Server 2003. La configurazione viene archiviata nelle seguenti chiavi del Registro di sistema con i valori riportati:
  
-   **HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\IPSec\\**  
    **OperationMode=3 (di stato)**
  
-   **HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\IPSec\\**  
    **BootExemptList = (esenzione per DHCP in ingresso, vedere più avanti)**
  
Il valore predefinito di **OperationMode** prevede che il driver IPsec esegua il filtraggio di stato del traffico in uscita. Se il servizio IPsec è in esecuzione, utilizzare il comando  
`Netsh ipsec dynamic show config` per visualizzare la configurazione di avvio. Se il servizio IPsec non è in esecuzione (ad esempio, in caso di avvio in modalità provvisoria), è possibile utilizzare gli strumenti del Registro di sistema per analizzare e modificare il valore della chiave.
  
Per risolvere i problemi di traffico potenzialmente causati da filtri di stato IPsec all'avvio, impostare il driver IPsec affinché autorizzi il traffico all'avvio invece di eseguire il filtraggio di stato. Se il servizio IPsec è in esecuzione, impostare  
`netsh ipsec dynamic set config bootmode value=permit`** **la modalità di avvio per l'autorizzazione del traffico. Se il servizio IPsec non è in esecuzione, utilizzare uno strumento del Registro di sistema per impostare **OperationsMode=1** per l'autorizzazione. In alternativa, il driver IPsec non applica la modalità di protezione all'avvio se il servizio IPsec è configurato per l'avvio manuale o se è disattivato. Dopo aver configurato l'avvio manuale o la disattivazione del servizio, riavviare il computer per consentire il caricamento del driver IPsec in modalità di autorizzazione.
  
###### Criteri IPsec permanenti
  
I criteri permanenti sono supportati da Windows XP e Windows Server 2003. Una situazione comune di errore si verifica quando un criterio permanente non viene eliminato prima di definirne uno nuovo e quindi il nuovo criterio entra in conflitto con altre impostazioni che sono già state assegnate. La soluzione descritta in questa guida non utilizza criteri permanenti. Poiché questi criteri potrebbero essere utilizzati in alcuni ambienti, nel presente capitolo si riportano le relative istruzioni di risoluzione.
  
La chiave del Registro di sistema per il criterio permanente esiste per impostazione predefinita ed è vuota:
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\**  
**IPSec\\Policy\\Persistent**
  
In Windows XP, il modo migliore per rilevare criteri permanenti consiste nel verificare che la chiave del Registro di sistema non sia vuota. Il comando ipseccmd show segnala i criteri attivi del servizio IPsec e non indica se un'impostazione specifica deriva da criteri permanenti. Il servizio IPsec elimina i nomi delle regole dei criteri permanenti quando li interpreta nelle impostazioni attive. Poiché ipseccmd non fornisce nomi di filtri e operazioni filtro, non è possibile utilizzare le convenzioni di denominazione per contraddistinguere filtri e operazioni filtro derivati da criteri permanenti. Quando i filtri che includono voci di un criterio permanente vengono creati con **ipsecpol.exe** o **ipseccmd.exe,** i nomi assegnati utilizzano lo stile "text2pol{GUID}". Anche i criteri locali o di dominio creati mediante gli script possono però utilizzare questi nomi.
  
Quando i criteri permanenti vengono assegnati, si uniscono ai criteri IPsec locali o del dominio. È quindi necessario annullare l'applicazione dei criteri locali e del dominio per visualizzare soltanto le impostazioni dei criteri permanenti. Quando si avvia il servizio IPsec, utilizzare `ipseccmd show all` per visualizzare tutti i criteri attivi, comprese eventuali impostazioni permanenti.
  
Per eliminare tutti gli oggetti (regole, elenchi filtri e operazioni filtro) associati a un criterio permanente specifico, specificare il nome del criterio permanente nel seguente comando:
  
```
ipseccmd.exe -w PERS -p "policy name" –o  
```  
Il modo più semplice per ottenere l'eliminazione completa di un criterio permanente consiste nell'eliminare tutte le sottochiavi della chiave **Persistent**. Tuttavia, se si elimina la chiave **Persistent**, eventuali futuri comandi ipseccmd non verranno completati quando si tenta di creare un criterio permanente. Per risolvere i problemi di danneggiamento del criterio permanente e i conflitti fra i criteri, eliminare tutti gli oggetti nell'archivio dei criteri permanenti ed eseguire nuovamente lo script ipseccmd per ricrearli.
  
In Windows Server 2003, il criterio permanente ha piene funzionalità di gestione, simili a quelle dei criteri IPsec locali e del dominio. Il criterio permanente viene archiviato nella medesima posizione del Registro di sistema sopra menzionata. Il seguente script di comandi Netsh visualizzerà il criterio permanente configurato utilizzando i comandi del file **show\_persistent.netsh**:

```  
Netsh –f show\_persistent.netsh   
```  

Il file **show\_persistent.netsh** è un file di testo che contiene le righe seguenti:

```  
Pushd ipsec static Set store persistent show all exit  
```  

Per eliminare completamente il criterio permanente, è possibile utilizzare il seguente script di comandi Netsh:
  
```  
pushd ipsec static set store persistent delete all exit  
```  

###### Criterio IPSec locale
  
Windows 2000, Windows XP e Windows Server 2003 supportano i criteri IPsec locali che vengono archiviati nella seguente chiave del Registro di sistema:
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\**  
**IPSec\\Policy\\Local**
  
In caso di assegnazione di un criterio locale, esso verrà archiviato nella chiave come segue:
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\**  
**IPSec\\Policy\\Local\\ActivePolicy**
  
Se il criterio di dominio non viene assegnato, il criterio locale assegnato verrà aggiunto a tutti i criteri permanenti configurati e diventerà il criterio attivo. Per una risoluzione dei problemi notevolmente semplificata, i criteri IPsec creati dagli script ipsecpol o ipseccmd devono essere modificati con lo snap-in MMC Gestione criteri di protezione IP al fine di definire i nomi di ciascun filtro prima di utilizzarli negli ambienti di produzione. In alternativa è possibile utilizzare il comando `netsh ipsec` per creare il criterio su un computer basato su Windows Server 2003 e quindi esportarlo in un file che possa essere importato nei computer con sistema operativo Windows 2000 e Windows XP o in un dominio, dopo averlo testato.
  
In Windows 2000, utilizzare il comando `netdiag /test:ipsec /debug `per visualizzare i dettagli dell'assegnazione e del criterio attivo. Per eliminare gli oggetti dei criteri IPsec nell'archivio locale, utilizzare lo snap-in MMC Gestione criteri di protezione IP o gli strumenti del Registro di sistema. Per forzare la procedura di caricamento del criterio IPsec assegnato, interrompere e riavviare il servizio.
  
In Windows XP, utilizzare i comandi `ipseccmd show gpo` o `netdiag /test:ipsec `per visualizzare l'assegnazione e i dettagli del criterio attivo. Utilizzare lo snap-in MMC Gestione criteri di protezione IP, gli strumenti del Registro di sistema o il comando  
`ipseccmd.exe -w REG -p "<policy_name>" –o `per eliminare il criterio IPsec specificato. Per rimuovere completamente il criterio locale, eliminare tutte le sottochiavi nella posizione di archivio precedentemente menzionata.
  
Per forzare il servizio IPsec a ricaricare il criterio, arrestarlo e riavviarlo o eliminare l'assegnazione e ripeterla utilizzando lo snap-in MMC Gestione criteri di protezione IP. Per ricaricare il criterio, è inoltre possibile utilizzare il comando `sc policyagent control 130 `. Quando il criterio viene ricaricato, tutte le SA IPsec e IKE vengono eliminate con conseguenti possibili ritardi di connettività o interruzioni con i computer che utilizzano attivamente le SA IPsec per trasmettere e ricevere il traffico.
  
In Windows Server 2003, utilizzare il comando  
`netsh ipsec static show gpoassignedpolicy `, lo snap-in MMC Gestione criteri di protezione IP o il nodo del criterio attivo del monitor IPsec per visualizzare il criterio locale assegnato.
  
Utilizzare il comando `netsh ipsec dynamic show all `per visualizzare la configurazione attiva del criterio. In alternativa è possibile utilizzare il monitor IPsec per analizzare le diverse parti del criterio attivo.
  
Per eliminare e ricaricare il criterio locale in Windows Server 2003, utilizzare i medesimi comandi menzionati per Windows XP. Il comando `netsh ipsec `può essere utilizzato per annullare l'assegnazione oppure riassegnare o eliminare il criterio.
  
###### Criterio IPSec di Active Directory
  
Questo criterio è supportato da Windows 2000, Windows XP e Windows Server 2003. Il criterio IPsec di dominio assegnato viene archiviato nel Registro di sistema locale nella posizione seguente:
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\**  
**IPSec\\GPTIPSECPolicy**
  
La cache di archiviazione del Registro di sistema locale del criterio di dominio è memorizzata in:
  
**HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\**  
**IPSec\\Policy\\Cache**
  
L'archivio della directory deve essere gestito con lo snap-in Gestione criteri di protezione IP o con il comando netsh ipsec eseguito come processo locale su Active Directory. Non esistono strumenti che consentano di visualizzare direttamente il contenuto della cache. Per stabilire se la cache esiste e contiene dati corretti, è necessario utilizzare uno strumento del Registro di sistema. Analogamente, per eliminare le chiavi **GPTIPsecPolicy** e **Cache** è necessario utilizzare gli strumenti del Registro di sistema. Si dovrà quindi riavviare il servizio IPsec o utilizzare il comando di controllo del servizio per forzare un nuovo caricamento del criterio IPsec senza il criterio di dominio.
  
Per aggiornare l'assegnazione del criterio IPsec basato sul dominio e ricaricare il criterio IPsec aggiornando il contenuto della cache, utilizzare **gpudpate /force**.
  
Per impedire temporaneamente l'applicazione di un criterio di dominio a un computer locale, è possibile configurare le autorizzazioni nelle chiavi **GPTIPsecPolicy** e **Cache** del Registro di sistema al fine di negare l'accesso in lettura all'account del sistema locale. Lo snap-in MMC Monitor di protezione IP e gli strumenti della riga di comando mostreranno ancora il criterio di dominio come assegnato perché leggono le informazioni di GPTIPsecPolicy eseguite nel contesto dell'utente amministratore locale. Per blocchi a lungo termine del criterio IPsec basato sul dominio, è necessario evitare che il computer legga il GPO appropriato in Active Directory.
  
In caso di problemi con il criterio, in Windows 2000 possono verificarsi gli errori seguenti:
  
-   **Impossibile eseguire il binding allo schema della directory**. L'Agente criteri IPsec non ha eseguito il binding LDAP autenticato con il contenitore dei criteri di protezione IP Active Directory. Questo errore è probabilmente causato dall'impossibilità di completare l'accesso all'account computer e di ricevere le credenziali Kerberos. Può inoltre dipendere da un errore del protocollo Kerberos nell'emissione del ticket di servizio LDAP al servizio Agente criteri IPsec.
  
-   **Impossibile eseguire il binding all'oggetto di archiviazione del criterio IPSEC**. Nel criterio IPsec è stato definito un oggetto (quale, ad esempio, una regola o un elenco filtri) che non esiste. Il criterio IPsec o il criterio di archiviazione di Active Directory potrebbe essere danneggiato oppure l'oggetto è stato eliminato (nonostante i criteri IPsec esistenti vi facciano ancora riferimento). Analizzare il criterio IPsec utilizzando lo snap-in MMC Gestione criteri di protezione IP per verificare che tutte le regole di protezione non siano danneggiate e che le proprietà di **Scambio chiave** (nella scheda **Generale**) possano essere visualizzate correttamente.
  
-   **Impossibile individuare il controller di dominio. Accertarsi che il computer sia membro del dominio e verificare la connessione di rete**. Il modulo di archiviazione del criterio IPsec non è riuscito a individuare una directory LDAP dalla quale recuperare il criterio IPsec basato sul dominio.
  
-   **Impossibile comunicare con il servizio directory sul controller di dominio. Contattare l'amministratore di sistema**. Il modulo dell'archivio IPsec non è riuscito a utilizzare la firma e il sigillo LDAP per scaricare il criterio IPsec assegnato.
  
-   **Impossibile individuare l'oggetto in memoria**. Questo errore è solitamente grave perché segnala che non è stato possibile recuperare completamente il criterio IPsec che quindi non verrà eseguito correttamente. Il modulo di archiviazione del criterio IPsec non ha trovato il GUID dell'oggetto (regola, elenco filtri, operazione filtro o impostazioni ISAKMP) contenuto nel criterio IPsec o una delle regole, sia utilizzando una chiamata LDAP che una chiamata di registro remoto. Questo errore può essere causato da una delle condizioni seguenti:
  
    -   Ritardi di replica in cui l'oggetto di riferimento arriva prima di quello a cui si fa riferimento o in cui le query vengono indirizzate a due diversi controller di dominio
  
    -   Oggetto eliminato mentre è ancora in uso nel criterio IPsec
  
    -   Oggetto con autorizzazioni che impediscono la sua enumerazione o lettura oppure archivio del criterio IPsec ripristinato a un momento precedente in cui l'oggetto non esisteva
  
    -   Criterio IPsec danneggiato che può generare un GUID non valido nella query
  
    -   Connettività di rete non disponibile per l'indirizzo IP di destinazione
  
    -   Servizio LDAP o Registro di sistema remoto non disponibile
  
-   **Impossibile completare l'operazione. L'archivio criteri non è aperto**. Non è stato possibile aprire l'archivio di Active Directory, del computer remoto o del computer locale. Questo errore è solitamente causato da un problema di autorizzazione o autenticazione.
  
-   **Si sta utilizzando il criterio attivo contenuto nel Registro di sistema locale, poiché (a) non esiste alcun criterio di archiviazione di Active Directory o (b) non è stato possibile applicare il criterio di archiviazione di Active Directory e la cache non ha alcun criterio in archivio**. Questo evento indica che il criterio IPsec è definito localmente sul computer e che non è stato possibile applicare il criterio basato sul dominio per sovrascriverlo.
  
-   **Non si sta utilizzando alcun criterio IPSEC, poiché (a) non esiste alcun criterio di archiviazione di Active Directory o alcun criterio attivo nel Registro di sistema locale oppure (b) non è stato possibile applicare il criterio di archiviazione di Active Directory e la cache non ha alcun criterio in archivio o non esiste alcun criterio attivo nel Registro di sistema locale**. Questo evento indica uno stato predefinito in cui al computer non è assegnato alcun criterio.
  
In Windows XP e Windows Server 2003, i seguenti eventi indicano che il servizio IPsec non è stato in grado di recuperare un tipo specifico di criterio. Se in Windows Server 2003 e Windows XP SP2 non è possibile leggere correttamente un criterio locale, il criterio viene ignorato per passare alla lettura del successivo criterio assegnato in ordine di precedenza.
  
-   **PAStore Engine non è riuscito a caricare il criterio IPSec di archivio permanente sul computer per "*&lt;nome criterio&gt;*"; codice errore** ***&lt;numero&gt;***. Il servizio IPsec ha rilevato che il criterio permanente è stato assegnato e archiviato nel Registro di sistema locale, ma non è riuscito a leggere il contenuto di almeno uno degli oggetti del criterio permanente. Controllare le autorizzazioni su tutte le chiavi del Registro di sistema. Il criterio potrebbe essere danneggiato. Tentare di eliminare completamente il criterio permanente e ricrearlo.
  
-   **PAStore Engine non è riuscito a caricare il criterio IPSec di archiviazione locale sul computer per "*&lt;nome criterio&gt;*"; codice errore:** ***&lt;numero&gt;***. Il servizio IPsec ha rilevato l'assegnazione di un criterio locale e ha tentato di leggerlo, ma si è verificato un errore durante la lettura di almeno uno degli oggetti associati al criterio assegnato. Controllare le autorizzazioni su tutte le chiavi del Registro di sistema. Il criterio potrebbe essere danneggiato e deve quindi essere eliminato e ricreato.
  
-   **PAStore Engine non è riuscito a caricare il criterio IPSec di archiviazione delle directory sul computer per "*&lt;nome criterio&gt;*"; codice errore:** ***&lt;numero&gt;***. Il servizio IPsec ha riscontrato almeno un errore durante la lettura del criterio IPsec assegnato da Active Directory. Questo errore può essere causato da un problema di connettività di rete verificatosi prima che tutti gli oggetti del criterio fossero recuperati oppure da oggetti mancanti nel criterio IPsec o da oggetti che non dispongono di autorizzazioni di lettura.
  
-   **PAStore Engine ha eseguito il polling delle modifiche al criterio IPSec di Active Directory, ha rilevato che Active Directory non è raggiungibile e ha eseguito la migrazione utilizzando la copia memorizzata del criterio IPSec di Active Directory. Non tutte le modifiche apportate al criterio IPSec di Active Directory potrebbero essere applicate**. Questo messaggio indica semplicemente che all'intervallo regolare di polling il servizio IPsec non è riuscito a connettersi ad Active Directory (ad esempio, a causa di un'interruzione del servizio DNS) e che non sono state apportate modifiche al criterio IPsec attivo. Quando il criterio attivo è stato originariamente applicato, la connettività ad Active Directory era disponibile e il servizio IPsec ha quindi recuperato e archiviato la versione più recente nella cache. Il servizio IPsec, pertanto considera la cache del Registro di sistema del criterio di dominio IPsec come l'origine primaria del criterio. Il polling continuerà a tentare di raggiungere la directory.  
  
##### Risoluzione dei problemi di interpretazione dei criteri IPsec
  
Il criterio IPsec viene interpretato quando il recupero dalla posizione di archiviazione viene completato. Gli indirizzi IP correnti delle interfacce di rete vengono utilizzati per estendere i filtri generici del criterio in filtri specifici. L'elenco filtri specifici in ingresso e in uscita viene quindi caricato nel driver IPsec per l'elaborazione dei pacchetti. Gli eventi di modifica delle interfacce vengono segnalati al servizio IPsec che adatta la configurazione dei filtri IPsec nel driver IPsec il più rapidamente possibile (ad esempio, per i filtri di Indirizzo IP).
  
In Windows 2000, i messaggi seguenti possono indicare un problema di interpretazione o di configurazione dei componenti IPsec per l'applicazione del criterio:
  
-   **L'attributo Tipo dati indica un formato di dati non riconosciuto**. Una parte del criterio IPsec contiene un formato di dati che il motore di archiviazione non riconosce. Questo errore indica un danneggiamento del criterio oppure un potenziale futuro problema di versione. Le caratteristiche del criterio IPsec in Windows XP e Windows Server 2003 sono state concepite per risultare trasparenti all'Agente criteri IPsec di Windows 2000.
  
-   **Impossibile leggere dati da un blob**. Il formato dei dati dell'attributo IPsecData in un oggetto del criterio IPsec è diverso da quello previsto. Questo errore indica quasi sempre un problema di danneggiamento del criterio o della versione. Per la corretta applicazione di tutte le impostazioni del criterio IPsec, è necessario risolvere il problema.
  
-   **L'Agente criteri non dispone dell'elenco delle interfacce**. L'Agente criteri IPsec non ha trovato interfacce di rete IP da filtrare. Si noti che l'errore nel testo di questo messaggio proviene direttamente dal codice sorgente di Windows e apparirà come qui riportato.
  
-   **Impossibile ottenere la tabella dell'interfaccia. I filtri basati sulle interfacce non verranno estesi e canalizzati nel driver IPSEC**.** **Si è verificato un errore quando l'Agente criteri IPsec ha tentato di enumerare l'elenco di interfacce sul computer. Potrebbero non essere disponibili interfacce di rete o potrebbe essersi verificato un errore interno nella gestione delle interfacce di rete. Le periferiche non completamente compatibili con PnP, i file danneggiati o i problemi delle schede NIC o di altri componenti di rete Windows possono esserne la causa. Altre possibili cause sono i filtri IPsec basati sul tipo di interfaccia, ad esempio, quelli configurati in una regola per un particolare tipo di connessione (accesso remoto, ad esempio) invece che per tutte le connessioni. Se il problema persiste dopo il riavvio, contattare il servizio di supporto tecnico Microsoft.
  
-   **Impossibile ottenere la tabella degli indirizzi IP. I filtri basati sulle interfacce non verranno estesi e canalizzati nel driver IPSEC**. Si è verificato un errore mentre l'Agente criteri IPsec tentava di enumerare tutti gli indirizzi IP sul computer utilizzando una chiamata di funzione nell'API helper IP. Potrebbe non essere stato configurato alcun indirizzo IP o potrebbero essere presenti problemi simili al precedente.
  
-   **Impossibile trovare l'indice delle voci degli indirizzi IP nella tabella dell'interfaccia. L'indirizzo IP verrà scartato**. L'Agente criteri IPsec verifica che tutti gli indirizzi IP compaiano nell'elenco delle interfacce di rete. Questo problema può essere causato da condizioni transitorie, ad esempio, quando si aggiunge o si rimuove un'interfaccia di rete. Il messaggio indica che il servizio IPsec non creerà filtri specifici per questo indirizzo IP scartato per i filtri generici di tipo Indirizzo IP nel criterio. Questa condizione potrebbe generare temporaneamente comportamenti non previsti a livello di connettività quando si utilizza questo indirizzo IP. L'errore potrebbe inoltre indicare un problema dello stato interno di configurazione dell'interfaccia IP che il servizio di supporto tecnico Microsoft dovrà ulteriormente analizzare. Poiché l'indirizzo IP viene scartato dall'Agente criteri IPsec (non dallo stack TCP/IP), non verranno creati filtri IPsec per questo indirizzo IP. Conseguentemente, non verranno effettuate operazioni di protezione (quali autorizzazione o blocco) né negoziazioni delle SA IPsec per il traffico che utilizza questo indirizzo IP.
  
-   **Un filtro mirror corrispondente è già esistente nell'elenco dei filtri**. Questo errore indica la presenza di un filtro duplicato nel criterio IPsec. È necessario analizzare la configurazione del criterio IPsec per verificare che non siano duplicati i filtri specifici della modalità rapida per le direzioni di ingresso e uscita.
  
-   **Non sono stati aggiunti filtri all'elenco dei filtri principale**. L'Agente criteri IPsec non ha trovato filtri nel criterio IPsec recuperato dall'archivio. Il criterio IPsec potrebbe contenere soltanto la regola di risposta predefinita oppure si sono verificati degli errori durante la lettura delle regole o dei filtri.
  
-   **Zero offerte per la fase 1. Il criterio ISAKMP verrà scartato**. Se non sono stati trovati metodi di protezione in modalità principale IKE (oggetti del criterio ISAKMP), il criterio IPsec è presumibilmente danneggiato.
  
-   **Zero offerte per la fase 2. Il criterio di negoziazione verrà scartato**. In assenza di metodi di protezione per l'operazione filtro (offerte per la fase 2 in modalità rapida IKE), IKE non eseguirà le negoziazioni in modalità rapida per il traffico che corrisponde ai relativi filtri. Il criterio IPsec è probabilmente danneggiato.
  
-   **Il criterio non contiene offerte valide**. Il criterio IPsec non contiene metodi di protezione validi nell'operazione filtro di una regola oppure non contiene impostazioni per la modalità principale IKE (impostazioni di scambio delle chiave configurate nella scheda Generale).
  
-   **L'Agente criteri ha tentato di inserire un filtro esistente all'interno di IPSEC**. Il driver IPsec rileva la presenza di un filtro duplicato e lo scarta. Questa situazione può essere benigna se il filtro duplicato contiene la medesima operazione di quello già elaborato nel driver IPsec. Se invece le operazioni filtro sono diverse, questa configurazione del criterio IPsec non è supportata. I risultati possono essere diversi dopo un certo intervallo di tempo e dipendono dall'ordine in cui la modifica del criterio viene elaborata. Il criterio IPsec deve essere configurato in modo da evitare filtri duplicati.
  
-   **Impossibile aggiungere una voce alla tabella dei criteri di IPSEC**. Non è stato possibile aggiungere un nuovo filtro al driver IPsec tramite l'Agenti criteri IPsec. Questo errore indica che il traffico che corrisponde al filtro specificato non verrà protetto. Questo errore può essere causato dall'insufficienza di memoria del kernel. Se il problema persiste, contattare il servizio di supporto tecnico Microsoft.
  
-   **L'Agente criteri non è stato in grado di inserire o aggiornare un filtro in IPSEC**. Come il precedente messaggio sull'aggiunta di un filtro, l'elenco dei filtri nel driver IPsec non corrisponde a quanto prevede il criterio IPsec assegnato. Non viene quindi garantita la protezione richiesta.
  
-   **Si sta utilizzando il criterio archiviato nella cache, poiché non è stato possibile applicare il criterio di archiviazione di Active Directory a causa di errori quali: rete non raggiungibile, integrità del criterio non valida o altro**. Quando viene assegnato un criterio IPsec basato sul dominio, l'Agente criteri IPSEC tenta prima di tutto di leggere il criterio più recente da Active Directory. Questo messaggio segnala che l'Agente criteri non è stato in grado di recuperare il criterio dalla directory e che sta applicando l'ultimo criterio di dominio archiviato nel Registro di sistema.  
  
In Windows Server 2003, gli eventi seguenti indicano che si è presumibilmente verificato un problema di interpretazione del criterio IPsec. Nella maggior parte dei casi, in Windows XP il testo degli eventi è il medesimo. Per un corretto funzionamento del criterio IPsec, è necessario risolvere questi problemi.
  
-   **PAStore Engine non è riuscito ad applicare il criterio IPSec di archivio permanente al computer per "*&lt;nome criterio&gt;*"; codice errore:*&lt;numero&gt;***. Il servizio IPsec ha rilevato un criterio permanente configurato nel Registro di sistema, ma non è riuscito ad applicarlo completamente. Eventuali criteri permanenti già applicati vengono eliminati e il driver IPsec entra in modalità di blocco a livello di programmazione (con le esenzioni di avvio), come indicato in un messaggio separato.
  
-   **PAStore Engine non è riuscito ad applicare il criterio IPSec di archiviazione del registro locale al computer per DN "*&lt;nome criterio&gt;*"*;*** **codice di errore:** ***&lt;numero&gt;***. Questo messaggio indica che il servizio ha rilevato almeno un errore nell'applicazione del criterio IPsec locale dal Registro di sistema locale. Questo messaggio potrebbe anche indicare che il criterio è danneggiato o che le autorizzazioni sono errate.
  
-   **PAStore Engine non è riuscito ad applicare il criterio IPSec di archiviazione di Active Directory al computer per DN "*&lt;CN=CriterioIpsec{GUID}*"; codice di errore:** ***&lt;numero&gt;***. Il servizio IPsec ha trovato il criterio di dominio specificato dal DN nella chiave **GPTIPsecPolicy** del Registro di sistema, ma non è riuscito ad applicarlo. Questo messaggio è di tipo informativo e spesso segnala che il controller di dominio non è raggiungibile dai client mobili; deve essere seguito dalla corretta applicazione del criterio archiviato nella cache (se presente). Potrebbe tuttavia indicare che un oggetto GPO sta consegnando un criterio IPsec che non esiste, non può essere letto o è danneggiato.
  
-   **PAStore Engine non è riuscito ad applicare una copia locale del criterio IPSec di archiviazione di Active Directory al computer per "*&lt;nome criterio&gt;"*; codice di errore:** ***&lt;numero&gt;***. Questo messaggio indica che il servizio IPsec è consapevole del fatto che è necessario assegnare un criterio di dominio e che non è stato possibile applicare il criterio recuperato da Active Directory. Il servizio IPsec ha quindi rilevato almeno un errore durante l'applicazione della copia locale in archivio del criterio di dominio assegnato. Questo messaggio potrebbe indicare che la cache è danneggiata o che le autorizzazioni sono errate. Si tratta di una condizione grave poiché non è stato possibile applicare alcun criterio basato sul dominio con conseguenti possibili problemi di connettività con altri membri del dominio di isolamento. Il criterio locale (se definito) avrà un ordine di precedenza inferiore.
  
-   **PAStore Engine non è riuscito ad applicare alcune regole del criterio IPSec attivo "*&lt;nome criterio&gt;*" al computer; codice di errore:** ***&lt;numero&gt;*. Eseguire lo snap-in del monitor IPSec per meglio identificare il problema.** Questo problema solitamente si manifesta insieme ad altri problemi qui illustrati, ad esempio, se non sono disponibili metodi di protezione per la modalità rapida (offerte).
  
-   **I servizi IPSec non sono riusciti a ottenere l'elenco completo delle interfacce di rete sul sistema. Ciò può rappresentare un potenziale pericolo per il sistema poiché alcune interfacce di rete potrebbero non essere protette nel modo opportuno dai filtri IPSec applicati. Eseguire lo snap-in del monitor IPSec per meglio identificare il problema.** Questo messaggio sostituisce i numerosi messaggi dell'API helper IP utilizzati in Windows 2000. Si tratta di un errore benigno se si verifica quando si aggiungono o rimuovono interfacce o quando variano gli stati di connessione, ad esempio, quando una rete senza fili non si trova più entro il raggio. È benigno anche quando si verifica durante la riattivazione dalle modalità di standby o sospensione ed esiste una diversa configurazione di rete che viene rilevata durante la riattivazione.  
  
##### Aspetti relativi alla configurazione dei criteri con VPN dotate di servizio RRAS
  
Come indicato nella sezione relativa al supporto di 1° livello del presente capitolo, in alcune organizzazioni il servizio RRAS è una comune fonte di conflitti con i criteri IPsec. Questa sezione illustra perché il criterio IPsec integrato per i server L2TP/IPsec VPN crea un conflitto con il criterio di dominio utilizzato in questa soluzione. Questa situazione è un esempio di problema di duplicazione dei filtri.
  
Nella seguente trattazione, per illustrare i problemi si ricorrerà alla configurazione del criterio IPsec utilizzata nello scenario della Woodgrove Bank. I principi sono comunque validi per numerose distribuzioni di IPsec a livello aziendale.
  
Il criterio IPsec per i server L2TP/IPsec viene generato automaticamente dal servizio RAS Manager (RASMAN) e include i filtri seguenti:
  
-   Da Qualsiasi Indirizzo IP a Indirizzo IP, UDP, origine 1701, dest Qualsiasi (in ingresso)
  
-   Da Indirizzo IP a Qualsiasi Indirizzo IP, UDP, origine Qualsiasi, dest 1701 (in uscita)
  
    **Nota:** per ulteriori informazioni su questo criterio, consultare l'articolo numero 248750  "[Description of the IPSec policy created for L2TP/IPsec](http://support.microsoft.com/?kbid=248750)" della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/?kbid=248750 (in lingua inglese).
  
Conseguentemente, il filtro specifico della modalità principale che controlla la risposta della negoziazione IKE a questo server è la parte relativa all'indirizzo del filtro in ingresso:
  
-   Da Qualsiasi Indirizzo IP a Indirizzo IP -&gt; Autenticazione certificato
  
Si noti che l'utilizzo di "Indirizzo IP" fa sì che il filtro in ingresso venga esteso a ciascun indirizzo IP sul server VPN. Presupponendo che il server VPN abbia un indirizzo IP di interfaccia esterna per la connettività Internet e un'interfaccia interna per la connettività LAN, i filtri in ingresso specifici per la modalità principale IKE saranno:
  
-   Da Qualsiasi Indirizzo IP a &lt;indirizzo IP interfaccia esterna&gt; -&gt; Autenticazione certificati
  
-   Da Qualsiasi Indirizzo IP a &lt;indirizzo IP interfaccia LAN interna&gt; -&gt; Autenticazione certificati
  
Il secondo filtro per l'interfaccia della rete LAN interna è più specifico rispetto al filtro in ingresso della modalità principale IKE nell'isolamento del server e del dominio e corrisponde a:
  
-   Da Qualsiasi IP a Subnet -&gt; Autenticazione Kerberos
  
Conseguentemente, quando un amministratore utilizza un client affidabile per gestire il server VPN, avvierà IKE sull'indirizzo IP interno del server VPN. La ricerca del criterio IKE in ingresso creerà una corrispondenza con il filtro della modalità principale più specifico e risponderà con le impostazioni della modalità principale IKE per L2TP. Invece dell'autenticazione Kerberos utilizzata per questa soluzione, verrà adottata l'autenticazione dei certificati.
  
Un secondo caso di conflitto potrebbe verificarsi se il client Internet VPN utilizza le funzionalità di quarantena del client di Connection Manager. Per terminare la quarantena e ottenere l'accesso VPN completo alla rete, il client in quarantena deve passare la "chiave di quarantena" all'indirizzo IP della LAN interna del server VPN. In questo scenario, quando il computer portatile viene avviato, il criterio IPsec di dominio del client VPN viene recuperato dalla cache. Quando si stabilisce una connessione VPN in quarantena, al client VPN viene assegnato un indirizzo IP interno. L'indirizzo IP interno può essere incluso in uno dei filtri di subnet (Qualsiasi &lt;-&gt; Subnet interna) definiti nel criterio IPsec di isolamento del dominio. Questo filtro è necessario affinché i client VPN possano utilizzare un accesso autenticato da IPsec da un'estremità all'altra del tunnel VPN verso i server interni e altre workstation a cui potrebbero accedere.
  
Tuttavia, i filtri di subnet utilizzati in questa soluzione avviano la negoziazione IKE dall'indirizzo IP interno dell'interfaccia virtuale del client VPN del tunnel verso l'interfaccia della rete LAN interna del server VPN. Si verificherà un errore in modalità principale IKE perché il server risponderà di accettare *soltanto* l'autenticazione tramite certificati, il che non è compatibile con il criterio utilizzato per l'isolamento del dominio e del server. Anche se il criterio non ha consentito l'autenticazione tramite certificato, la modalità rapida IKE proporrà dal client il filtro per tutto il traffico e il server VPN non completerà la negoziazione perché il filtro proposto è troppo generico. Il server VPN accetterà i filtri della modalità rapida soltanto a condizione che essi siano specifici per L2TP: origine UDP 1701, destinazione Qualsiasi od origine UDP 1701, destinazione 1701.
  
Per risolvere il conflitto fra il criterio L2TP/IPsec del server RRAS e il criterio di isolamento, è possibile utilizzare le opzioni seguenti:
  
-   Inserire nell'elenco di esenzioni gli indirizzi IP del server RRAS sulla LAN interna
  
-   Disattivare le porte L2TP sui server VPN Utilizzare soltanto PPTP
  
-   Disattivare il criterio automatico IPsec per L2TP utilizzando la chiave **ProhibitIPsec** del Registro di sistema per RASMAN. Personalizzare manualmente la configurazione del criterio IPsec per L2TP affinché utilizzi soltanto l'indirizzo IP esterno per l'autenticazione tramite certificati per il traffico UDP 1701 e soltanto l'autenticazione Kerberos per tutto il traffico per l'isolamento del dominio mediante l'indirizzo IP interno.
  
    **Nota:** Per ulteriori informazioni su questa configurazione, consultare l'articolo numero 240262 "[How to Configure a L2TP/IPSec Connection Using Pre-shared Key Authentication](http://support.microsoft.com/kb/240262)" della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/kb/240262 (in lingua inglese).
  
La soluzione più semplice di questo elenco è la prima che evita che la scheda NIC interna del server RRAS utilizzi IPsec.
  
#### Risoluzione dei problemi relativi a IKE
  
IKE e IPsec solitamente generano errori alla prima distribuzione perché il filtraggio di rete non consente il passaggio dei pacchetti dei protocolli UDP 500 o IPsec. Per questa ragione, è consigliabile utilizzare una workstation IPsec statica o un server di test a cui assegnare un criterio semplice, ad esempio, il criterio predefinito Server (Richiesta) che utilizza una chiave già condivisa. Per acquisire gli eventi di controllo di IKE, il controllo deve essere attivato. A tutti i membri del dominio che eseguono l'autenticazione con la medesima chiave già condivisa viene distribuito un criterio IPsec di dominio che contiene una regola con un filtro per tutto il traffico (compreso quello ICMP) verso l'indirizzo IP del computer di test.
  
Distribuire uno script di accesso al dominio per eseguire il ping `<testserver>` o  
`nbtstat –n <testserver>`, che avvierà la negoziazione IKE da tutti i membri del dominio verso il server di test. Analizzando e riepilogando gli indirizzi IP nei controlli riusciti della modalità principale IKE, è possibile stabilire se tutti i computer ricevono il criterio e verificare che tutte le aree della rete possano raggiungere il computer di test utilizzando i protocolli IKE e IPsec.
  
per verificare che l'incapsulamento IPsec funzioni con la frammentazione in ciascuna area della rete, è possibile eseguire un test più avanzato utilizzando `ping –l 5000 <IP address>` dal server di test ai computer ubicati in ciascuna area. L'opzione –l 5000 fa sì che Ping crei un payload di pacchetti ICMP da 5000 byte. Questo pacchetto IP completo viene incapsulato dal protocollo IPsec e quindi frammentato dal livello IP prima di essere inviato sulla rete. La destinazione dovrà ricevere tutti i frammenti e inviare una risposta che includa un numero uguale di frammenti. L'esperienza ha dimostrato che le periferiche congestionate o che fungono da confini fra reti a diversa velocità (ad esempio, Ethernet a 1 gigabit e 100 megabit) possono avere problemi di trasferimento dei frammenti. Analogamente, gli host che risiedono su collegamenti con diverse MTU, quali ATM (Asynchronous Transfer Mode), FDDI (Fiber Distributed Data Interface) e Token Ring, richiedono che i messaggi PMTU ICMP rilevino correttamente l'MTU del percorso di rete per i pacchetti TCP protetti da IPsec. Per informazioni sui diversi valori predefiniti di MTU della rete, consultare l'articolo numero 314496 "[Default MTU Size for Different Network Topology](http://support.microsoft.com/kb/314496)" della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/kb/314496 (in lingua inglese).
  
##### Risoluzione dei problemi di negoziazione IKE
  
La risoluzione dei problemi relativi a IKE può risultare complessa perché gli errori si possono verificare in condizioni specifiche, ad esempio, quando viene avviata la modalità rapida IKE soltanto da un computer che solitamente è il risponditore. Gli errori possono essere causati anche da problemi del sistema di autenticazione, ad esempio, errori del protocollo Kerberos, o verificarsi quando un criterio di dominio viene unito a configurazioni non compatibili o a un criterio pre-esistente. Gli errori di IKE comportano un'interruzione della negoziazione IKE da parte del computer su cui si è verificato l'errore, mentre l'altro computer che partecipa alla negoziazione solitamente esaurisce il limite di tentativi e va in timeout. In caso di errori di IKE, provare ad analizzare il problema e ad acquisire i registri senza apportare modifiche. È possibile attivare automaticamente i controlli standard senza modificare la configurazione di IPsec o lo stato di esecuzione del servizio. Tuttavia, in Windows 2000 è necessario riavviare il servizio IPsec per attivare la registrazione dettagliata di IKE nel file **Oakley.log**. In Windows XP SP2 e Windows Server 2003, è invece possibile attivare e disattivare la registrazione di IKE, quando necessario, mediante una riga di comando.
  
In alcune situazioni, potrebbe essere necessario arrestare e riavviare il servizio IPsec per analizzare il traffico di rete ed acquisire i risultati nel file **Oakley.log** da uno stato in cui il sistema è integro. Quando il servizio IPsec viene arrestato manualmente o tramite una procedura di riavvio o arresto del computer, IKE tenta di inviare messaggi di eliminazione per ripulire lo stato delle SA IPsec su tutti i peer attivamente connessi. In alcuni casi, il sistema operativo disattiva questa funzionalità di invio dei pacchetti prima che IKE completi l'invio dei messaggi di eliminazione a tutti i peer attivi, facendo sì che lo stato delle SA IPsec sul peer rimanga invariato. Quando ciò si verifica, il peer potrebbe ritenere di essere protetto e connesso al computer che si sta riavviando. A riavvio completato, se il computer non avvia una nuova negoziazione IKE con il relativo peer, il peer stesso dovrà attendere che le SA IPsec scadano (5 minuti) prima di tentare di ristabilirle. Per ristabilire le SA, viene prima tentata una negoziazione in modalità rapida per un minuto, quindi IKE avvia la modalità principale.
  
A partire da Windows 2000, la registrazione di IKE è stata costantemente migliorata. Gli eventi illustrati in questa sezione sono validi per Windows XP e Windows Server 2003, nonostante anche gli eventi di Windows 2000 siano di natura simile.
  
Il Registro protezione di Windows è il punto di partenza consigliato per tentare di individuare le cause di un errore di negoziazione IKE. Per visualizzare gli eventi IKE e verificare che l'impostazione dei criteri di protezione del gruppo "Controlla eventi di accesso" venga completata, è necessario attivare il controllo prima che il servizio IKE possa creare le voci di controllo e fornire una spiegazione del fallimento della negoziazione. La spiegazione degli errori di negoziazione IKE viene riportata, nella maggior parte dei casi, come Evento 547 e le cause possibili del medesimo messaggio di errore possono essere numerose. L'elenco degli errori dell'evento 547 e le potenziali cause sono riportati nei dettagli nelle sezioni seguenti.
  
In Windows XP SP2 e Windows Server 2003, è possibile disattivare tutti i controlli IKE con una chiave **DisableIKEAudits** del Registro di sistema. È quindi essenziale accertare lo stato di questo valore sui computer che vengono analizzati. I controlli IKE possono essere disattivati nei casi in cui il controllo generi un numero così elevato di operazioni riuscite e non riuscite da rendere impossibile un efficace monitoraggio degli altri eventi di accesso/disconnessione.
  
I valori dei codici di errore sono spesso riportati negli eventi di controllo IKE e nei dettagli del registro. Le descrizioni di questi valori sono disponibili presso Microsoft MSDN® nella pagina [System Code Errors (12000-15999)](http://msdn.microsoft.com/en-us/library/ms681384(vs.85).aspx) all'indirizzo http://msdn.microsoft.com/library/en-us/debug/base/  
system\_error\_codes\_\_12000-15999\_.asp (in lingua inglese).
  
La risoluzione dei problemi relativi a IKE richiede una conoscenza approfondita del comportamento previsto della configurazione dei criteri IPsec, del processo di negoziazione IKE e degli eventi di errore IKE. Questa sezione tenta di spiegare gli eventi più comuni relativi allo scenario di isolamento del dominio della Woodgrove Bank. Non tratta tutti gli eventi di controllo IKE né tutte le condizioni di errore.
  
Dopo aver compreso il processo di negoziazione IKE, è necessario acquisire una traccia di rete da almeno una delle parti della comunicazione (se possibile) al fine di individuare i problemi relativi a IKE prima di tentare di acquisire un file **Oakley.log**. I server distribuiti negli scenari di isolamento del server e del dominio devono poter acquisire una traccia tramite Network Monitor.
  
Il file **Oakley.log** fornisce le registrazioni più dettagliate possibili e potrebbe essere necessario acquisire questo file da entrambe le parti della negoziazione (con orari sincronizzati). Tuttavia, se si attiva questo registro, la negoziazione IKE potrebbe rallentare alterando i tempi e causando una perdita dello stato corrente se il servizio viene riavviato per ripetere la lettura della chiave del Registro di sistema (necessaria in Windows 2000 e Windows XP SP1). Attualmente, non sono state pubblicate istruzioni per l'interpretazione del file **Oakley.log**. Per la soluzione illustrata in questa guida, questa interpretazione rientra nelle competenze del 3° livello. Per ragioni di spazio, vengono riportati brevi estratti dei dettagli inclusi nel registro solo per un numero limitato di errori. Per assistenza sull'interpretazione del file **Oakley.log**, contattare il servizio di supporto tecnico Microsoft.
  
IKE registra i seguenti file di registrazione dettagliati:
  
-   **Oakley.log**. Registro corrente per IKE, limitato a 50.000 righe.
  
-   **Oakley.log.bak**. Questo file viene creato una volta esaurite le 50.000 righe di **Oakley.log** e viene aperto un nuovo file **Oakley.log** vuoto. Questo file viene sovrascritto dal nuovo file **Oakley.log, se necessario,** fino a quando il servizio IPsec rimane in funzione.
  
-   **Oakley.log.sav**. Quando si avvia il servizio IPsec, il precedente file **Oakley.log** viene salvato con questo nome.
  
-   **Oakley.log.bak.sav**. Quando si avvia il servizio IPsec, il precedente file **Oakley.log.bak** viene salvato con questo nome.
  
Un errore che si commette spesso durante il processo di risoluzione dei problemi consiste nella mancata sincronizzazione degli orari dei due computer da cui si acquisiscono le registrazioni e le tracce di rete. Ciò complica la correlazione fra i registri, pur non rendendola impossibile. La correlazione fra i messaggi IKE e i pacchetti della traccia di rete deve essere verificata utilizzando i cookie delle intestazioni ISAKMP e i campi ID dei messaggi della modalità rapida.
  
##### Comportamenti previsti di IKE
  
Se la rete impedisce che l'avvio della modalità principale raggiunga l'indirizzo IP di destinazione desiderato, non è possibile eseguire la negoziazione della comunicazione protetta da IPsec. Se l'iniziatore non è configurato per la modalità non crittografata, l'impossibilità di contattare la destinazione viene segnalata come evento di controllo 547 nel Registro protezione con una delle seguenti voci:
  
-   Nessuna risposta da peer
  
-   Timeout negoziazione
  
-   SA IKE eliminato prima che la connessione fosse stabilita  
  
D'altro canto, per i client dell'isolamento del dominio questa condizione potrebbe non apparire come un errore se il relativo criterio consente la modalità non crittografata. Quando viene stabilita una SA trasferibile, viene generato un evento 541 della modalità principale IKE. L'indicazione di una SA trasferibile nell'evento 541 è data dalla visualizzazione dell'SPI in uscita a zero e di tutti gli algoritmi come None. L'esempio seguente mostra come appaiono questi parametri nell'evento 541:

```  
ESP Algorithm None
HMAC Algorithm None
AH Algorithm None
Encapsulation None
InboundSpi 31311481 (0x1ddc679)
OutBoundSpi 0 (0x0)
Lifetime (sec) <whatever is configured for QM lifetime>
Lifetime (kb) 0
```  
**Nota**: gli eventi relativi alle SA trasferibili per lo stesso indirizzo IP di destinazione presenteranno diversi timestamp e valori SPI in ingresso.
  
Ritardi di connettività di un minuto si verificano quando due computer perdono la sincronizzazione relativamente all'esistenza di una modalità principale IKE attiva tra di loro. Si possono verificare ritardi di cinque minuti se un computer ritiene che esista una coppia di SA IPsec attiva fra se stesso e un altro computer (ad esempio, un server) e se elimina queste SA senza iniziare la reimpostazione delle chiavi in modalità rapida. IKE di Windows 2000 supportava messaggi di eliminazione singoli che in alcuni casi andavano perduti. In Windows XP e Windows Server 2003, è stato aggiunto il supporto per una funzionalità di eliminazione "affidabile" sotto forma di messaggi di eliminazione multipli, come misura di sicurezza contro i pacchetti scartati.
  
Lo scenario più comune per questa situazione è quello in cui un utente di un portatile appartenente all'isolamento del dominio rimuove il portatile dall'alloggiamento di espansione per recarsi a una riunione. L'alloggiamento di espansione è dotato di una connessione Ethernet cablata e la rimozione di questa interfaccia di rete rende necessaria l'eliminazione di tutti i filtri associati (in caso di filtri estesi da Indirizzo IP).
  
Tuttavia, nessuno dei filtri con un'operazione di negoziazione utilizza Indirizzo IP nella soluzione di isolamento del dominio poiché tutti i filtri sono di tipo Qualsiasi &lt;-&gt; Subnet. Conseguentemente, gli stati delle SA IPsec e IKE rimangono attivi sul portatile perché questi filtri non vengono eliminati a ciascun cambiamento di indirizzo. Se esistono filtri estesi da "Indirizzo IP", essi dovrebbero essere stati eliminati quando l'indirizzo IP è scomparso.
  
Quando viene eliminato un filtro di qualsiasi tipo nel driver IPsec, il driver informa IKE che tutte le SA IKE e IPsec che utilizzano tale indirizzo IP devono essere eliminate. IKE tenterà di inviare messaggi di eliminazione per queste SA e le eliminerà internamente. Tali messaggi di eliminazione utilizzeranno lo stesso IP di origine usato per l'SA IKE, nonostante possa essere presente un diverso IP di origine sull'interfaccia connessa nel momento in cui è stata inviata la richiesta di eliminazione. L'indirizzo IP di origine non viene preso in considerazione dal computer remoto, se la coppia di cookie dell'intestazione ISAKMP viene riconosciuta e se i controlli di crittografia sul pacchetto sono validi. D'altro canto, però, i messaggi di eliminazione spesso non vengono inviati per mancanza di connettività della rete nei secondi successivi alla rimozione (del portatile dall'alloggiamento di espansione).
  
In questo caso specifico di filtri Qualsiasi &lt;-&gt; Subnet, i filtri non vengono mai eliminati, il che significa che le SA IKE e IPsec non vengono eliminate immediatamente. Nel frattempo, il timeout delle SA IPsec sui computer remoti che erano precedentemente connessi e le eliminazioni della modalità rapida IKE vengono inviate all'indirizzo precedente del portatile. Le SA della modalità rapida IKE rimangono attive per un tempo predefinito di 8 ore su questi computer remoti, ma possono essere eliminate prima per ragioni interne a IKE. Naturalmente, i messaggi di eliminazione delle SA IKE non vengono ricevuti dal portatile al precedente indirizzo IP. Quando il portatile viene riconnesso nell'alloggiamento di espansione, riceverà nuovamente il medesimo indirizzo IP. Le condivisioni di file, i client di posta elettronica e le altre applicazioni solitamente si riconnettono alle stesse destinazioni. Lo stato del protocollo IKE sul portatile potrebbe però essere diverso da quello di dette destinazioni remote. Se il portatile utilizza ancora la modalità principale IKE, tenterà la negoziazione in modalità rapida IKE. La modalità rapida utilizza uno stato crittografico che il peer remoto ha eliminato e quindi non riconosce i messaggi e non risponde. Dopo un minuto, sul portatile scade il limite di tentativi IKE e viene tentata una nuova negoziazione in modalità principale IKE, che ha ora esito positivo. L'utente del portatile potrebbe pertanto notare un minuto di ritardo quando si connette nuovamente alle risorse remote. Microsoft prevede di poter migliorare questo comportamento negli aggiornamenti futuri di tutte le versioni di Windows che supportano IPsec.
  
La negoziazione IKE potrebbe segnalare un timeout per numerose ragioni. L'evento "Timeout negoziazione" si verifica quando una qualsiasi fase della negoziazione IKE (fatta eccezione per la modalità non crittografata) fallisce perché il limite di tentativi è stato raggiunto, fatta eccezione per i casi in cui IKE interrompe la negoziazione con un evento "SA IKE eliminato prima che la connessione fosse stabilita". Questi due eventi sono sostanzialmente identici. Sono spesso comuni, benigni e previsti durante il normale funzionamento per i client mobili, che frequentemente modificano gli stati di connettività sulla rete quando si verificano gli eventi seguenti:
  
-   Utenti che inseriscono e rimuovono i computer portatili da alloggiamenti di espansione
  
-   Utenti che si scollegano da una connessione cablata
  
-   Computer portatili che entrano in modalità di sospensione o standby
  
-   Computer che si trovano oltre il raggio della connessione wireless
  
-   Interruzione di una connessione VPN
  
-   Espulsione di una scheda di rete PCMCIA durante la connessione
  
Per un computer remoto, uno di questi eventi viene interpretato come se il computer peer si fosse disconnesso dalla rete. Il computer remoto tenterà così di reimpostare le chiavi o di ripetere la negoziazione fino a quando la fase di negoziazione IKE non scade.
  
Gli errori di timeout della negoziazione sono stati migliorati in Windows Server 2003 al fine di facilitare l'identificazione del momento in cui si è verificato il timeout durante la negoziazione IKE, individuando l'ultima fase completata. Questi eventi possono essere causati anche dalla presenza di una NAT (Network Address Translation) quando IKE esegue la negoziazione senza funzionalità NAT-T. Il timeout della negoziazione IKE si verifica anche se il peer remoto rileva una causa che impedisce di completare la negoziazione IKE.
  
Ne consegue che, in tutti i casi di eventi di timeout e "SA IKE eliminato prima che la connessione fosse stabilita", il supporto di 2° livello deve individuare il computer remoto che non ha completato la negoziazione, verificando gli eventi di controllo 547 non riusciti sul computer in questione e fino a un minuto prima che IKE registri il timeout.
  
###### Eventi di negoziazione IKE riuscita
  
Se la negoziazione IKE viene completata, le SA della modalità principale IKE possono essere visualizzate nello snap-in MMC del monitor IPSec e mediante gli strumenti di query della riga di comando.
  
**Visualizzazione di un elenco delle SA correnti nella modalità principale IKE**
  
-   Per Windows 2000:
  
```
ipsecmon.exe, netdiag /test:ipsec /v   
```  
  
    **Nota**: questo comando visualizza soltanto le SA IPsec e non le SA IKE in modalità principale
  
-   Per Windows XP:

```  
IPsec monitor snapin, ipseccmd show sas   
```  
  
-   Per Windows Server 2003**:**
  
    **Nota:** la riga è stata suddivisa per facilitarne la lettura. Tuttavia, quando la si prova su un sistema, è necessario immettere il testo su una sola riga senza interruzioni.
  
```
IPsec monitor snapin, netsh ipsec dynamic  
show \[mmsas | qmsas\]  
```  
  
Se il controllo è attivato, le SA completate in modalità principale e rapida genereranno i seguenti eventi nel file del Registro protezione.
  
-   **541**. Stabilita modalità principale IKE o modalità rapida
  
-   **542**. Modalità rapida IKE eliminata
  
-   **543**. Modalità principale IKE eliminata
  
##### Voci informative dei file di registro in modalità principale IKE
  
Per stabilire se si è verificato un problema di scambio nella modalità principale, verificare se sono stati registrati i seguenti eventi nei registri del computer:
  
**Tabella 7.5. Messaggi di informazioni del file di registro in modalità principale IKE**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Testo del file di registro</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Il nuovo criterio invalida SA formati con il vecchio criterio</td>
<td style="border:1px solid black;">Messaggio di Windows 2000 che indica che la modifica del criterio IP ha causato l'eliminazione delle SA IKE o IPsec correnti. Si tratta di un errore benigno. Vengono stabilite nuove SA IPsec basate sul flusso corrente di traffico che utilizzano il nuovo criterio IPsec.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IKE ha numerose richieste di Associazione di protezione in sospeso e sta entrando nella modalità di prevenzione di attacchi di tipo &quot;Denial of service&quot;</td>
<td style="border:1px solid black;">Ciò potrebbe essere normale e provocato da un elevato carico del computer e/o da un gran numero di tentativi di connessione client. Potrebbe essere anche la conseguenza di un attacco di tipo Denial of Service nei confronti di IKE. Se si tratta di un attacco Denial of Service, saranno presenti numerosi record di controllo con negoziazioni IKE non riuscite sugli indirizzi IP attaccati. In caso contrario, il carico del computer è semplicemente troppo elevato.<br />
Indica che IKE ritiene di essere stato sovraccaricato con richieste di SA IKE in modalità principale e quindi scarterà numerose di queste richieste adottando una strategia di risposta agli attacchi di tipo Denial of service.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IKE ha terminato la modalità di prevenzione di attacchi di tipo &quot;Denial of service&quot; ed è ritornato all'operatività normale</td>
<td style="border:1px solid black;">IKE ha terminato la risposta a quello che ha giudicato essere un attacco di tipo Denial of Service ed è ritornato alle normali condizioni di funzionamento.</td>
</tr>
</tbody>
</table>
  
La presenza di queste voci non indica un errore di comunicazione. Sono infatti voci informative e possono essere utilizzate per fornire ulteriori dettagli e facilitare l'individuazione della reale causa del problema.
  
###### Eventi di errore 547 della negoziazione IKE in modalità principale
  
I seguenti eventi di errore relativi a IKE possono verificarsi quando la negoziazione IKE in modalità principale non ha esito positivo:
  
-   **Nessuna risposta da peer**. È probabile che questo evento si verifichi per le connessioni in uscita verso computer che non utilizzano IPsec e che non rientrano nell'elenco di esenzioni. Il supporto di 2° livello deve però essere attento ai problemi di connettività che bloccano la negoziazione IKE e che potrebbero generare questo evento.
  
-   **Nessun criterio configurato**. Questo evento indica la presenza di un problema nel caso in cui l'indirizzo IP dell'origine sia inserito in subnet interne oppure potrebbe indicare una mancata corrispondenza con una serie di filtri. Si potrebbe altrimenti presumere che i computer non utilizzano alcuna regola per la negoziazione con certi gruppi di indirizzi o subnet. I computer su queste subnet potrebbero tentare di avviare IKE, ma non riceveranno risposte perché non è configurato alcun criterio.
  
-   **Attributi di protezione IKE inaccettabili**. Questo evento non dovrebbe verificarsi sui sistemi configurati correttamente. Per analizzare la situazione, eseguire i passaggi della sezione "Verifica della correttezza dei criteri IPsec".
  
Come conseguenza delle condizioni sopra illustrate, potrebbe apparire uno dei seguenti messaggi di "Timeout negoziazione". Questi messaggi possono inoltre indicare che il computer remoto non è riuscito a completare la negoziazione IKE. Solitamente, il supporto di 2° livello si concentra sull'analisi degli errori relativi a IKE sul computer remoto piuttosto che sui timeout di negoziazione, che sono molto comuni per i computer disconnessi, e sull'incompatibilità di configurazione dei criteri, in cui il risponditore a una negoziazione IKE in modalità principale o rapida non trova un filtro specifico corrispondente alla richiesta in ingresso.
  
-   Timeout negoziazione
  
-   Timeout negoziazione-Primo payload (SA) elaborato Rispondente. Durata intervallo 63
  
-   Timeout negoziazione-Secondo payload (KE) elaborato Iniziatore. Durata intervallo 63
  
-   Timeout negoziazione-Secondo payload (KE) elaborato Rispondente.
  
###### Controlli non riusciti in modalità rapida IKE (547)
  
I seguenti eventi di errore relativi a IKE possono verificarsi quando la negoziazione IKE in modalità rapida non viene completata:
  
-   Nessun criterio configurato-Terzo payload (ID) elaborato Iniziatore
  
-   Impossibile completare la negoziazione dell'associazione di protezione a causa di una mancata corrispondenza attributi
  
-   Errore generale di elaborazione
  
-   Impossibile ottenere nuovo SPI per SA in ingresso dal driver IPsec
  
-   Negoziazione oakley non riuscita, a causa della mancanza di filtri
  
-   Impossibile aggiungere l'Associazione di protezione al driver IPSec
  
-   Timeout negoziazione
  
In caso di criteri IPsec correttamente configurati, non dovrebbero verificarsi errori della modalità rapida IKE con carichi operativi normali. Se si riceve uno di questi errori, il supporto di 2° livello deve prima di tutto eseguire i passaggi indicati nella sezione "Verifica della correttezza dei criteri IPsec", quindi dovrà tentare di correlare questi eventi a condizioni prestazionali insolite, quali ad esempio un utilizzo del 100% della CPU o condizioni di insufficienza di memoria del kernel.
  
Si noti che gli errori della modalità rapida IKE per timeout della negoziazione sono prevedibili se il computer non utilizza più il precedente indirizzo IP per una qualsiasi delle ragioni precedentemente illustrate.
  
##### Risoluzione dei problemi relativi a IKE causati dall'autenticazione
  
I messaggi seguenti sono relativi agli errori di autenticazione IKE:
  
-   Destinazione specificata sconosciuta / Impossibile contattare un'autorità per l'autenticazione
  
-   Destinazione specificata sconosciuta o irraggiungibile-Primo payload (SA) elaborato Iniziatore. Durata intervallo 0
  
-   Credenziali di autenticazione IKE inaccettabili
  
-   Tentativo di accesso non riuscito
  
-   Impossibile autenticare mediante Kerberos
  
-   IKE non è riuscito a trovare un certificato di computer valido
  
I primi due messaggi indicano che non è possibile utilizzare l'identità Kerberos del computer remoto per ottenere un ticket di servizio per il computer remoto. Questa situazione potrebbe verificarsi in mancanza di una relazione di trust con il dominio oppure perché non è possibile accedere ai controller di dominio.
  
Se la negoziazione IKE in ingresso non viene completata a causa delle impostazioni di "Accesso al computer dalla rete", la negoziazione IKE all'estremità che applica i diritti di accesso segnalerà un evento 547 "Impossibile autenticare mediante Kerberos" come descritto in precedenza. Questo evento non indica specificatamente che il problema si verifica durante il controllo dei diritti di "Accesso al computer dalla rete" ed è quindi necessario acquisire un file **Oakley.log** dal server per verificare l'errore specifico generato. È inoltre necessario verificare l'appartenenza al gruppo dell'iniziatore di IKE, controllando che esso appartenga a un gruppo autorizzato. Se il computer è membro di un gruppo che dispone di autorizzazioni di accesso, potrebbe non disporre dei ticket Kerberos che attestano la nuova appartenenza. In alternativa, il computer potrebbe non essere in grado di ottenere i ticket Kerberos appropriati. Eseguire le procedure illustrate nella sezione "Verifica della connettività e dell'autenticazione con i controller di dominio" riportata in precedenza nel presente capitolo.
  
#### Risoluzione dei problemi correlati alle applicazioni
  
Questa sezione descrive come la configurazione delle applicazioni potrebbe interagire con l'utilizzo di IPsec in Microsoft Windows. Il progettista dei criteri IPsec deve saper comprendere queste interazioni e il personale di supporto deve esserne a conoscenza per poter velocizzare la classificazione e l'identificazione dei problemi. L'applicazione dei criteri IPsec deve essere perfettamente trasparente per le applicazioni. Si verificano però circostanze in cui l'assegnazione di criteri IPsec o la protezione del traffico può comportare un diverso comportamento delle applicazioni. Le sezioni seguenti illustrano queste circostanze nel contesto della soluzione di isolamento del dominio della Woodgrove Bank.
  
##### ICMP autorizzato - Protezione IPsec per TCP e UDP
  
Alcune applicazioni utilizzano il messaggio di richiesta echo ICMP (Ping) per stabilire se un indirizzo di destinazione è raggiungibile. In questa soluzione, ad esempio, IPsec non protegge il traffico ICMP, quindi un'applicazione potrebbe ricevere una risposta ICMP da una destinazione. L'applicazione potrebbe però non essere in grado di connettersi alla destinazione utilizzando il traffico TCP e UDP protetto da IPsec quando la negoziazione IKE non viene completata.
  
##### Ritardi iniziali di connessione
  
La negoziazione IKE implica sostanzialmente una maggiore elaborazione e tempi più lunghi rispetto a un handshake TCP tridirezionale o a una query Nbtstat non autenticata a un solo pacchetto con risposta. Le applicazioni che attendono una risposta rapida della connessione TCP o UDP da una destinazione potrebbero stabilire che la destinazione non risponde e avviare altre operazioni, ad esempio la segnalazione di un errore o il tentativo di connessione a una destinazione alternativa. Le negoziazioni IKE che utilizzano l'autenticazione Kerberos solitamente vengono completate in 1-2 secondi. Questo intervallo di tempo dipende però da numerosi fattori, in particolare dall'utilizzo della CPU su entrambi i computer e dalla perdita di pacchetti lungo la rete. La modalità non crittografata attende sempre tre secondi prima di consentire l'invio del primo pacchetto non protetto dell'handshake TCP.
  
##### Blocco dell'applicazione in attesa di risposta dalla rete
  
Alcune applicazioni sono state sviluppate presupponendo che il tempo necessario per la connessione o la ricezione di un messaggio di errore sia molto rapido. Queste applicazioni attendono che la connessione venga stabilita (completamento dell'operazione di binding al socket) prima di visualizzare le modifiche nell'interfaccia utente. Quando il traffico di queste applicazioni è protetto da IPsec, potrebbe sembrare che le applicazioni si blocchino temporaneamente mentre viene completata la connessione. Se la connessione non viene stabilita a causa di un errore di negoziazione IKE o di un filtro IPsec di blocco, l'applicazione potrebbe rimanere bloccata fino a quando non viene chiusa o si verificano altri errori insoliti. Il livello socket della rete non è integrato con i filtri IPsec né riconosce quando IKE sta negoziando la protezione del traffico. L'applicazione solitamente interpreta queste condizioni come problemi causati da un host remoto non funzionante o da un guasto della rete. Tuttavia, le applicazioni possono anche interpretare l'impossibilità di accedere ai controller di dominio come indisponibilità del computer di destinazione o come connessione respinta.
  
##### Problemi di elaborazione dei pacchetti sulla rete in modalità kernel
  
Le applicazioni che richiedono l'elaborazione dei pacchetti da parte dei driver di rete o altre elaborazioni a livello di kernel potrebbero non funzionare correttamente quando IPsec protegge il traffico. Queste applicazioni potrebbero infatti apportare modifiche ai pacchetti che fanno sì che IPsec li scarti oppure non comprendere le modifiche apportate da IPsec con un conseguente errore di sistema (schermo blu).
  
##### Scansione della rete da parte degli host nei domini di isolamento
  
Gli strumenti basati sugli host che tentano di sondare rapidamente gli indirizzi IP remoti o di aprire porte sulla rete possono funzionare molto più lentamente se IPsec tenta di proteggere il relativo traffico. Il traffico di sondaggio può causare un problema di tipo "Denial of Service" sull'host locale a seguito dell'avvio delle negoziazioni IKE su centinaia di indirizzi IP in pochi secondi o minuti. Alcuni strumenti basati su SNMP dipendono dall'invio di eventi SNMP d'intercettazione a host non attendibili che fungono da contenitori di eventi. Anche se IPsec può passare alla modalità non crittografata, i pacchetti SNMP intercettati in uscita possono essere scartati dal driver IPsec prima che venga stabilita la SA trasferibile. Analogamente, alcune applicazioni basate su UDP (quali, ad esempio, NTP e il servizio di individuazione dei controller di dominio di Windows) attendono la risposta soltanto per tre secondi con conseguente errore dell'applicazione o creazione di report falsi sull'impossibilità di raggiungere una destinazione.
  
##### Problemi relativi ai provider LSP Winsock
  
Alcune applicazioni legittime (come, ad esempio, i firewall personali) e alcune applicazioni dannose (quali gli spyware) possono causare problemi inserendo le loro specifiche funzioni di controllo del traffico sulla rete, denominate provider LSP (Layered Service Provider) Winsock. Nel componente IKE dell'implementazione Microsoft di IPSec, viene utilizzata una funzione API Winsock estesa, il cui puntatore di funzione è determinato mediante una chiamata WSAIoctl(). Se non viene consentito il passaggio di questa chiamata attraverso uno o più provider LSP installati, IKE non potrà monitorare le porte UDP specificate. In Windows Server 2003, IPsec interpreta questa condizione come un problema di applicazione del criterio di protezione richiesto nel componente e reagisce difendendosi. Viene richiamato il passaggio alla modalità protetta e il driver IPsec si porta in condizione di blocco. Per arrestare il servizio IPsec e ripristinare la connettività, l'amministratore dovrà accedere utilizzando l'accesso del desktop. Se il servizio IPsec non risponde alla richiesta di interruzione, sarà necessario configurarlo come disattivato e riavviare il computer.
  
Nonostante possa sembrare che IKE abbia completato l'inizializzazione, il computer potrebbe non riuscire a inviare e ricevere protocolli IKE e IPsec a causa dell'LSP o di altri programmi di terze parti.
  
Per il supporto di 2° livello, il processo di risoluzione dei problemi dei provider LSP Winsock consiste nel verificare che gli LSP stessi esistano. Il supporto di 3° livello dovrà eseguire ulteriori analisi per identificare l'applicazione che ha installato gli LSP e per riordinarli o rimuoverli al fine di verificare che i servizi IPsec e IKE non abbiano più problemi. Gli strumenti per la rilevazione di provider LSP Winsock includono:
  
-   **Sporder.exe**. Applet disponibile per la visualizzazione di provider LSP in Winsock 2.0 di SDK (Software Development Kit) per la piattaforma Windows.
  
-   **Netdiag /debug**.
  
##### Client IPsec VPN di terze parti
  
Possono verificarsi numerosi problemi quando si implementa un protocollo IPsec di terze parti su un client VPN di accesso remoto. Tipicamente, questi client disattivano il servizio IPsec e non sono in conflitto con l'IPsec nativo di Windows. Tuttavia, per i membri del dominio attendibile di questa soluzione, il servizio IPsec è necessario. Ne consegue che le implementazioni di IPsec di terze parti possono entrare in conflitto per le ragioni seguenti:
  
-   Entrambe le implementazioni di IKE potrebbero utilizzare la porta UDP 500
  
-   L'elaborazione dei pacchetti IPsec a livello di kernel potrebbe richiedere il protocollo ESP per entrambe le implementazioni
  
-   Funzioni dei provider LSP Winsock installate come parte del client
  
-   Funzionalità firewall fornita dal client VPN
  
-   Sovrapposizione di livelli che impedisce il passaggio di pacchetti IKE nativi e con incapsulamento IPsec attraverso il tunnel IPsec di terze parti
  
Per verificare se i client VPN supportano il servizio IPsec di Windows e il traffico in modalità di trasporto protetto da IPsec da un'estremità all'altra delle relative connessioni di accesso remoto, è consigliabile richiedere informazioni ai fornitori. In alcuni casi, il gateway del fornitore VPN supporta il PPTP di Windows 2000 e Windows XP e i client L2TP/IPsec VPN. I client VPN nativi di Windows sono compatibili con la modalità di trasporto IPsec da un'estremità all'altra del tunnel VPN.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Risoluzione dei problemi di 3° livello
  
Se il processo di risoluzione dei problemi di 2° livello non ha esito positivo, sarà necessario ricorrere ad altre competenze che analizzino il problema e individuino una soluzione. Questa competenza viene definita supporto di 3° livello. In numerosi casi, questo supporto viene fornito da consulenti esterni o da organizzazioni specializzate, quali il servizio di supporto tecnico Microsoft.
  
Il supporto di 3° livello per IPsec deve poter contare su conoscenze approfondite del funzionamento di IPsec e dello stack TCP/IP di Microsoft. Il personale del supporto di 3° livello deve essere adeguatamente formato sul protocollo IPsec e sull'utilizzo di IPsec negli scenari di isolamento del server e del dominio. Le competenze del personale di 3° livello consentono di affidare a questo team la formazione degli addetti al supporto dei livelli inferiori e l'elaborazione della documentazione di supporto, inclusi documenti tecnici, white paper, guide di supporto, elenchi di domande frequenti e informazioni sull'architettura e la tassonomia di IPsec. Il supporto di 3° livello può inoltre essere responsabile dello sviluppo e della documentazione dei piani di ripristino.
  
#### Coinvolgimento del servizio di supporto tecnico Microsoft
  
Se le procedure di risoluzione dei problemi illustrate nel presente capitolo non si dimostrassero efficaci o se l'organizzazione non dovesse disporre delle competenze sufficienti per utilizzare tecniche di risoluzione dei problemi avanzate, potrebbe essere necessario assegnare il problema al servizio di supporto tecnico Microsoft. Prima di coinvolgere il servizio di supporto tecnico Microsoft, è essenziale acquisire il maggior numero possibile di informazioni di diagnostica, ad esempio, dai registri e dal monitoraggio di rete. Utilizzare l'elenco seguente per raccogliere le informazioni necessarie al personale del supporto di 3° livello o al servizio di supporto tecnico Microsoft per analizzare il problema:
  
-   Requisiti di protezione per l'autenticazione e l'autorizzazione in ingresso e in uscita per ciascun computer. Una breve descrizione che illustri come la configurazione di Criteri di gruppo e di IPsec soddisfi questi requisiti.
  
-   Uno schema esplicativo dello scenario, che riporti i nomi dei computer di origine e di destinazione, i loro indirizzi IP al momento dell'acquisizione dei file di registro e le versioni dei sistemi operativi (incluse le informazioni sui Service Pack). Indicare anche gli indirizzi IP dei server DNS e WINS e dei controller di dominio.
  
-   Tracce del monitoraggio di rete acquisite da entrambe le parti con il criterio IPsec attivo, preferibilmente in simultanea, affinché sia possibile mettere in relazione i pacchetti dei due file di traccia. Le tracce di rete devono includere tutto il traffico in ingresso e in uscita su ciascun computer (se possibile), affinché si possano identificare le richieste di autenticazione, le ricerche DNS e il traffico correlato. Inoltre, se la comunicazione si interrompe mentre il criterio IPsec è attivo e invece funziona quando il criterio IPsec è disattivato o il servizio viene arrestato, fornire anche una traccia di rete del traffico con servizio IPsec non attivo. È di fondamentale importanza che l'orario dei sistemi venga sincronizzato affinché i file di registro e di traccia possano essere messi a confronto.
  
-   Per Windows 2000, Windows XP e Windows Server 2003 eseguire  
    `netdiag /debug >netdiag-debug-computername.txt` subito prima o subito dopo l'acquisizione della traccia di rete (netdiag genera un elevato volume di traffico sulla rete che non è necessario acquisire nella traccia di rete). Per Windows XP e Windows Server 2003, eseguire anche  
    `portqry -v -local >portqry-v-computername.txt.`
  
-   File **Oakley.log** di IKE acquisito dalle due parti nel momento in cui si verifica il problema e orario in cui sono state registrate le tracce di monitoraggio della rete. I nomi di questi file devono fare riferimento al nome del computer. Se è coinvolto un client Windows RAS o VPN, utilizzare lo strumento RASDIAG per acquisire informazioni.
  
-   I registri applicazioni, protezione ed eventi completi di sistema e di ciascun computer al momento dell'acquisizione dei file **Oakley.log** e delle tracce di rete.
  
-   Tutti i file di registro specifici di Criteri di gruppo creati nello stesso momento in cui vengono acquisiti i file **Oakley.log** e le tracce di rete.
  
-   I dettagli dei criteri IPsec per ciascun computer. Se è possibile salvare senza difficoltà i criteri IPsec applicati a ciascun computer, includere anche questi ultimi. D'altro canto, il criterio IPsec attivo del computer è spesso una combinazione di numerosi tipi di configurazioni dei criteri IPsec, non soltanto del criterio locale o di dominio. Il formato migliore per analizzare il criterio attivo su un computer consiste nell'elencare i filtri specifici della modalità principale IKE e i filtri specifici della modalità rapida IKE dallo snap-in MMC del monitor IPsec.
  
**Creazione di un file di testo formattato dei filtri**
  
1.  Fare clic con il pulsante destro del mouse sul nodo **Filtri specifici della modalità rapida IKE** nel riquadro sinistro della struttura.
  
2.  Scegliere **Esporta elenco**.
  
3.  Salvare il file di testo delimitato da tabulatori come **IKE-qm-*&lt;nome specifico computer&gt;*.txt** o con una convenzione di denominazione simile che includa il nome del computer.
  
Il file di testo delimitato da tabulatori con tutti i dettagli sui filtri può essere importato in un foglio di calcolo o in un documento di elaborazione testo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Nel presente capitolo sono state fornite informazioni dettagliate sui processi che facilitano la comprensione e la risoluzione dei problemi di comunicazione più comuni relativi a IPsec per il supporto di 1° livello (personale dell'help desk) e del 2° livello (personale di supporto IT specializzato nelle reti). Non è possibile fornire informazioni su tutti i potenziali errori poiché IPsec e la protezione della rete sono aspetti talmente complessi da non consentire un'elencazione di tutte le possibili variabili. I redattori di questo capitolo hanno, ove possibile, standardizzato le opzioni per concentrarsi sulle istruzioni nelle aree solitamente più problematiche nell'ambiente di isolamento del server e del dominio illustrato in questa guida.
  
Gli script di esempio forniti nella presente guida sono stati testati nel laboratorio di prova dello scenario della Woodgrove Bank per verificarne l'efficacia. Gli script sono stati però concepiti per la personalizzazione che dovrà soddisfare le esigenze specifiche dell'organizzazione e pertanto non sono supportati da Microsoft.
  
È evidente che le procedure di risoluzione dei problemi relativi a IPsec sono tecnicamente complesse e, oltre alla conoscenza del protocollo IPsec, richiedono competenze in numerosi campi della tecnologia, fra i quali le reti, Active Directory e Criteri di gruppo. Le informazioni contenute nel presente capitolo dovrebbero comunque consentire al lettore di eseguire le procedure di risoluzione dei problemi più complessi che possono presentarsi in una soluzione di isolamento del server e del dominio.
  
Per coloro che desiderano approfondire le loro conoscenze nel campo del supporto di 2° livello, il materiale di riferimento aggiuntivo riportato nella sezione seguente dovrebbe essere sufficiente per un approfondimento più che dettagliato.
  
#### Ulteriori informazioni
  
-   Per informazioni di base dettagliate su IPsec, consultare il documento tecnico su Windows Server 2003 - [How IPsec Works](http://technet.microsoft.com/en-us/library/cc759130.aspx) all'indirizzo www.microsoft.com/resources/documentation/  
    WindowsServ/2003/all/techref/en-us/w2k3tr\_IPsec\_how.asp
  
-   Per informazioni dettagliate sulla risoluzione dei problemi relativi a TCP/I, vedere i seguenti documenti tecnici:
  
    -   Il capitolo [TCP/IP Troubleshooting](http://www.microsoft.com/resources/documentation/windows/xp/all/reskit/en-us/prcc_tcp_gfhp.asp) del Resource Kit di Microsoft Windows XP all'indirizzo www.microsoft.com/resources/documentation/Windows/  
        XP/all/reskit/en-us/prcc\_tcp\_gfhp.asp
  
    -   "[Risoluzione dei problemi relativi alla connettività TCP/IP in Windows XP](http://support.microsoft.com/?kbid=314067)" all'indirizzo http://support.microsoft.com/?kbid=314067
  
    -   [Windows Server 2003 TCP/IP Troubleshooting](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/operations/system/tcpiptrb.mspx) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/  
        operations/system/tcpiptrb.mspx (in lingua inglese)
  
-   Per le guide in linea e la documentazione dei Resource Kit che trattano specificatamente la risoluzione dei problemi relativi a IPsec in Windows 2000, Windows XP e Windows Server 2003, consultare i riferimenti seguenti:
  
    -   "[Procedura di base per la risoluzione di problemi IPSec in Windows 2000](http://support.microsoft.com/?kbid=257225)" all'indirizzo  
        http://support.microsoft.com/?kbid=257225
  
    -   [Documentazione su Windows 2000 Server](http://www.microsoft.com/windows2000/en/advanced/help/sag_ipsectrouble.htm?id=3352) all'indirizzo  
        www.microsoft.com/windows2000/en/advanced/help/  
        sag\_ipsectrouble.htm?id=3352
  
    -   "[Procedure di base per la risoluzione dei problemi relativi a L2TP/IPSec in Windows XP](http://support.microsoft.com/?kbid=314831)" all'indirizzo  
        http://support.microsoft.com/?kbid=314831
  
    -   Guida in linea di Windows Server 2003 - IPsec [Troubleshooting tools](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/standard/sag_ipsec_tools.asp?frame=true) all'indirizzo  
        www.microsoft.com/technet//prodtechnol/  
        windowsserver2003/proddocs/standard/  
        sag\_ipsec\_tools.asp?frame=true\#iketrace\_enable
  
    -   Il diagramma Architecture Overview nel white paper "[Windows 2000 TCP/IP Implementation Details](http://www.microsoft.com/windows2000/techinfo/howitworks/communications/networkbasics/tcpip_implement.asp)" all'indirizzo  
        www.microsoft.com/windows2000/  
        techinfo/howitworks/communications/networkbasics/  
        tcpip\_implement.asp
  
    -   [Windows 2000 Network Architecture](http://www.microsoft.com/resources/documentation/windows/2000/server/reskit/en-us/cnet/cnad_arc_jypf.asp) (figura B.1) all'indirizzo  
        www.microsoft.com/resources/documentation/windows/  
        2000/server/reskit/en-us/cnet/cnad\_arc\_jypf.asp
  
    -   [How TCP/IP Works](http://technet.microsoft.com/en-us/library/cc786128.aspx) all'indirizzo www.microsoft.com/resources/documentation/  
        WindowsServ/2003/all/techref/en-us/w2k3tr\_tcpip\_how.asp
  
    -   [How IPSec Works](http://technet.microsoft.com/en-us/library/cc759130.aspx) all'indirizzo www.microsoft.com/resources/documentation/  
        WindowsServ/2003/all/techref/en-us/w2k3tr\_ipsec\_how.asp
  
**Scarica la soluzione completa**
  
[Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=33947)
  
[](#mainsection)[Inizio pagina](#mainsection)
