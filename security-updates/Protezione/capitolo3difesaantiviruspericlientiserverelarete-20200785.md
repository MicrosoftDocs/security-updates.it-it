---
TOCTitle: 'Capitolo 3: Difesa antivirus per i client, i server e la rete'
Title: 'Capitolo 3: Difesa antivirus per i client, i server e la rete'
ms:assetid: '5ea5c9e7-96d5-4c58-8d27-e44d80e609ea'
ms:contentKeyID: 20200785
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536185(v=TechNet.10)'
---

Guida alla difesa antivirus a più livelli
=========================================

### Capitolo 3: Difesa antivirus a più livelli

Pubblicato: 20 maggio 2004

##### In questa pagina

[](#eiaa)[Introduzione](#eiaa)  
[](#ehaa)[Vettori di pericoli correlati a software dannoso](#ehaa)  
[](#egaa)[Strategia di difesa da attacchi di software dannoso](#egaa)  
[](#efaa)[Protezione client](#efaa)  
[](#eeaa)[Protezione server](#eeaa)  
[](#edaa)[Livello di difesa della rete](#edaa)  
[](#ecaa)[Protezione fisica](#ecaa)  
[](#ebaa)[Criteri, procedure e consapevolezza](#ebaa)  
[](#eaaa)[Riepilogo](#eaaa)  

### Introduzione

È opportuno che tutte le organizzazioni sviluppino una soluzione antivirus che fornisca un elevato livello di protezione. Tuttavia, la propagazione di infezioni nella maggior parte delle organizzazioni è una situazione piuttosto comune, anche dopo che queste abbiano provveduto all'installazione di software antivirus. In questa Guida viene proposto un approccio differente alla protezione contro applicazioni software dannose o *malware*. Come per la progettazione della protezione di rete, anche per la progettazione di soluzioni antivirus Microsoft consiglia l'adozione di una strategia di difesa a più livelli in modo da garantire una gestione affidabile delle misure di protezione implementate dall'organizzazione.

Un approccio di questo tipo è fondamentale per la protezione dei computer dell'organizzazione, in quanto purtroppo, indipendentemente dal numero di funzionalità o servizi utili forniti da un sistema informatico, esiste sempre il rischio che qualcuno, per diversi motivi, tenti di individuare una vulnerabilità da sfruttare al fine di provocare danni reali.

La collaborazione di consulenti e tecnici di sistema che hanno implementato Microsoft® Windows Server™ 2003, Windows® XP Professional e Windows® 2000 in un'ampia gamma di ambienti ha consentito di stabilire le procedure consigliate più aggiornate per la protezione da software dannoso dei client e dei server su cui vengono eseguiti questi sistemi operativi. Tutte queste informazioni vengono illustrate nel presente capitolo.

In questo capitolo vengono fornite inoltre indicazioni per l'utilizzo di una strategia di difesa a più livelli durante la progettazione di una soluzione di protezione antivirus per la propria organizzazione. Lo scopo di questa strategia consiste nell'assicurare che l'utente comprenda in modo chiaro ciascun livello del modello e i pericoli specifici correlati a ciascun livello in modo da utilizzare queste informazioni durante l'implementazione di difese antivirus.

**Nota**: Microsoft consiglia di includere alcune operazioni descritte in questa Guida nei criteri e nelle procedure di protezione generali dell'organizzazione. Queste operazioni vengono identificate in questa Guida come requisiti che dovranno essere definiti in maggiore dettaglio dal team di protezione all'interno dell'organizzazione.

**Importante**: se si sospetta che la propria organizzazione stia attualmente subendo un attacco, prima di leggere il presente documento, fare riferimento al Capitolo 4 "Controllo delle violazioni e ripristino" in questa Guida.

Se si legge questa guida dopo aver subito un attacco di software dannoso e ripristinato il sistema, le informazioni illustrate nel presente capitolo avranno lo scopo di impedire la ricorrenza di eventuali attacchi e di fornire una maggiore comprensione della modalità di esecuzione dell'attacco precedente.

[](#mainsection)[Inizio pagina](#mainsection)

### Vettori di pericoli correlati a software dannoso

Esistono diversi metodi con cui un'applicazione software dannosa può compromettere un'organizzazione. Questi metodi vengono talvolta definiti come *vettori di pericoli* e rappresentano le aree all'interno dell'ambiente in uso che richiedono particolare attenzione durante la progettazione di una soluzione antivirus efficace. Nel seguente elenco sono riportate le aree maggiormente esposte al rischio di attacchi di software dannoso all'interno di organizzazioni tipiche:

-   **Reti esterne**: qualsiasi rete che non sia sotto il controllo diretto di un'organizzazione deve essere considerata come origine potenziale di attacchi di software dannoso. Tuttavia, Internet costituisce di gran lunga il maggiore pericolo correlato al software dannoso. L'anonimato e la connettività forniti da Internet consente a utenti malintenzionati di ottenere un accesso rapido ed efficace a molte destinazioni allo scopo di sferrare attacchi mediante l'uso di codice dannoso.

-   **Client guest**: con il continuo espandersi dell'uso di computer portatili e dispositivi mobili all'interno delle aziende, i dispositivi vengono spostati regolarmente all'interno e all'esterno delle infrastrutture dell'organizzazione. Se non dispongono di difese antivirus efficaci, i client guest rappresenteranno per l'organizzazione agenti di pericoli correlati a software dannoso.

-   **File eseguibili**: qualsiasi codice eseguibile è in grado di svolgere la funzione di software dannoso. Esempi di software dannoso comprendono non solo programmi, ma anche script, file batch e oggetti attivi, quali i controlli Microsoft ActiveX®.

-   **Documenti**: poiché sono diventate sempre più potenti, le applicazioni di fogli di calcolo ed elaborazione testi rappresentano oggi i principali obiettivi degli autori di software dannoso. Infatti, il supporto fornito per i linguaggi macro rende molte applicazioni potenziali bersagli di attacchi di software dannoso.

-   **Posta elettronica**: gli autori di software dannoso possono sfruttare come metodi di attacco sia gli allegati di posta elettronica che il codice HTML (Hypertext Markup Language) attivo all'interno dei messaggi di posta elettronica.

-   **Supporti rimovibili**: il trasferimento di file tramite supporti rimovibili rappresenta un problema che le organizzazioni devono affrontare durante lo sviluppo delle relative difese antivirus. Tra i supporti rimovibili più comunemente utilizzati figurano:

    -   **Unità CD-ROM o DVD-ROM**: l'avvento di dispositivi di registrazione CD e DVD economici ha reso questi supporti accessibili a tutti gli utenti di computer, compresi i creatori di software dannoso.

    -   **Unità floppy e Zip**: Questi supporti vengono utilizzati sempre meno di frequente a causa della capacità e della velocità limitate di cui dispongono, ma rappresentano comunque dei rischi potenziali per la protezione, nel caso in cui il software dannoso sia in grado di accedervi fisicamente.

    -   **Unità USB**: questi dispositivi assumono molte forme che variano dal classico dispositivo a forma di portachiavi all'orologio da polso. Tutti questi dispositivi, se inseriti nella porta USB (Universal Serial Bus) di un host, possono essere utilizzati per introdurre del software dannoso.

    -   **Schede di memoria**: le telecamere digitali e i dispositivi mobili, quali PDA e telefoni cellulari, hanno consentito di creare schede di memoria digitali. I lettori di schede, essendo diventati ormai periferiche standard dei computer, stanno acquisendo un'importanza sempre maggiore, in quanto consentono di semplificare il trasferimento di dati sulle schede di memoria. Poiché questi dati sono basati su file, le schede di memoria sono anche in grado di trasferire software dannoso su un sistema host.

[](#mainsection)[Inizio pagina](#mainsection)

### Strategia di difesa da attacchi di software dannoso

Prima di tentare di organizzare una difesa efficace contro attacchi di software dannoso, è essenziale comprendere le varie parti dell'infrastruttura dell'organizzazione potenzialmente a rischio e la portata del rischio per ciascuna parte. Microsoft consiglia di eseguire una verifica completa dei rischi di protezione prima di avviare la progettazione di una soluzione antivirus. È possibile ottenere le informazioni necessarie per l'ottimizzazione della progettazione della soluzione solo eseguendo una verifica completa dei rischi di protezione.

Per informazioni e istruzioni sull'esecuzione di una verifica dei rischi di protezione, vedere la Guida *Microsoft Solution for Securing Windows 2000 Server* all'indirizzo:
<http://www.microsoft.com/technet/security/prodtech/win2000/secwin2k/default.mspx> (in inglese). In questa Guida viene fornita un'introduzione alla disciplina della gestione dei rischi di protezione (SRMD, Security Risk Management Discipline), che è possibile utilizzare per comprendere la natura dell'esposizione dell'organizzazione a potenziali rischi.

#### Modello di protezione per la difesa a più livelli

Una volta individuate e documentate le situazioni di rischio che l'organizzazione deve affrontare, il passo successivo prevede l'analisi e l'organizzazione delle difese che si utilizzeranno per la realizzazione della soluzione antivirus. Il modello di protezione per la difesa a più livelli rappresenta un eccellente punto di partenza per questo processo. Questo modello consente di identificare sette livelli di difese di protezione progettati per assicurare che i tentativi di violazione della protezione di un'organizzazione vengano gestiti mediante un efficace set di difese. Ciascun set è in grado di respingere attacchi a diversi livelli. Se non si ha familiarità con il modello di protezione per la difesa a più livelli, Microsoft consiglia di esaminare la pagina Security Content Overview sul sito Web Microsoft TechNet all'indirizzo:
<http://www.microsoft.com/technet/security/bestprac/overview.mspx> (in inglese).

Ulteriori informazioni ed esempi di progettazione pratici per questo processo sono disponibili inoltre in *MSA Reference Architecture Kit* sul sito Web TechNet all'indirizzo:
<http://www.microsoft.com/resources/documentation/msa/2/all/solution/en-us/msa20rak/vmhtm1.mspx> (in inglese).

Nella seguente figura vengono illustrati i livelli definiti per il modello di protezione per la difesa a più livelli:

[![](images/Dd536185.AVFG0301(it-it,TechNet.10).gif "Figura 3.1 Livelli del modello di protezione per la difesa a più livelli")](https://technet.microsoft.com/it-it/dd536185.avfg0301_big(it-it,technet.10).gif)

**Figura 3.1 Livelli del modello di protezione per la difesa a più livelli**

I livelli illustrati nella figura forniscono una visualizzazione di ciascuna area dell'ambiente in uso che è consigliabile prendere in considerazione durante la progettazione delle difese di protezione per la rete.

È possibile modificare le definizioni dettagliate di ciascun livello in base alle priorità e ai requisiti di protezione dell'organizzazione. Nell'ambito di questa Guida, i livelli del modello vengono definiti mediante le semplici definizioni riportate di seguito:

-   **Dati**: i rischi a livello di dati provengono da vulnerabilità che un utente malintenzionato potrebbe sfruttare per ottenere l'accesso ai dati di configurazione, ai dati dell'organizzazione o ai dati specifici dei dispositivi utilizzati dall'organizzazione. Dati riservati, come dati aziendali confidenziali, dati degli utenti e archivi dei dati dei clienti privati, devono essere tutti considerati parte di questo livello. La preoccupazione principale per l'organizzazione a questo livello del modello è rappresentata dai problemi aziendali e legali che possono insorgere in conseguenza della perdita o del furto di dati, nonché dai problemi operativi che potrebbero derivare da vulnerabilità a livello di host o di applicazione.

-   **Applicazione**: i rischi a livello di applicazione provengono da vulnerabilità che un utente malintenzionato potrebbe sfruttare per accedere alle applicazioni in esecuzione. Qualsiasi tipo di codice eseguibile che un creatore di software dannoso è in grado di trasferire all'esterno di un sistema operativo potrebbe essere utilizzato per sferrare un attacco contro un sistema. La principale preoccupazione per l'organizzazione a questo livello è rappresentata dall'accesso ai file binari che costituiscono le applicazioni, dall'accesso all'host tramite le vulnerabilità nei servizi in ascolto dell'applicazione o dalla raccolta inadeguata dal sistema di dati specifici da passare a un utente in modo che possa utilizzarli per i propri scopi.

-   **Host:** questo livello viene in genere utilizzato dai fornitori che offrono service pack e aggiornamenti rapidi al fine di affrontare i pericoli correlati a software dannoso. I rischi a questo livello provengono da utenti malintenzionati che sfruttano le vulnerabilità all'interno dei servizi offerti dall'host o dal dispositivo. I pirati informatici sfruttano queste vulnerabilità in diversi modi per sferrare attacchi contro il sistema. Un valido esempio di vulnerabilità di questo tipo è rappresentato dal sovraccarico del buffer, una condizione che si verifica quando a un buffer viene aggiunta una quantità di informazioni maggiore rispetto alla quantità prevista in fase di progettazione. La principale preoccupazione di un'organizzazione a questo livello è impedire l'accesso ai file binari che costituiscono il sistema operativo e dall'accesso all'host tramite le vulnerabilità presenti nei servizi in ascolto del sistema operativo.

-   **Rete interna**: i rischi per le reti interne delle organizzazioni riguardano in larga parte i dati riservati trasmessi tramite reti di questo tipo. Numerosi rischi sono anche associati ai requisiti di connettività per le workstation client su queste reti interne.

-   **Rete perimetrale**: i rischi associati al livello della rete perimetrale (noto anche come DMZ, zona demilitarizzata o subnet protetta) provengono da un utente malintenzionato che ottiene l'accesso a una rete WAN (Wide Area Network) e ai livelli della rete a cui si connettono. I principali rischi a questo livello del modello sono incentrati sulle porte TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) disponibili utilizzate dalla rete.

-   **Protezione fisica**: i rischi a livello fisico provengono da utenti malintenzionati che riescono a ottenere l'accesso fisico a un bene fisico. Questo livello include tutti i livelli precedenti, in quanto l'accesso fisico a un bene può a sua volta consentire l'accesso a tutti gli altri livelli del modello di difesa a più livelli. La principale preoccupazione a questo livello del modello per le organizzazioni che utilizzano sistemi antivirus è impedire ai file infetti di aggirare le difese delle reti interne e perimetrali. Questa operazione può essere eseguita dagli autori di attacchi semplicemente copiando un file infetto direttamente sul computer host tramite alcuni supporti rimovibili fisici, quale una periferica disco USB.

-   **Criteri, procedure e consapevolezza**: a tutti i livelli del modello di protezione sono associati i criteri e le procedure che l'organizzazione deve implementare per soddisfare e supportare i requisiti relativi a ciascun livello. Infine, è importante promuovere tra tutte le parti interessate un certo livello di consapevolezza in materia di protezione all'interno dell'organizzazione. In molti casi, la mancata consapevolezza dell'esistenza di uno specifico rischio può favorire una violazione della protezione. Per questo motivo, anche la formazione deve essere una parte integrante di qualsiasi modello di protezione.

L'utilizzo dei livelli di protezione del modello come base per l'approccio di difesa antivirus a più livelli consente di ottimizzare tali livelli tramite la relativa inclusione in gruppi per le difese antivirus da implementare all'interno dell'organizzazione. La modalità di esecuzione di questa ottimizzazione dipende interamente dalle priorità dell'organizzazione e dalle specifiche applicazioni di difesa utilizzate al suo interno. Il punto importante consiste nell'evitare la progettazione di una soluzione antivirus incompleta e debole assicurando che nessuno dei livelli di protezione venga escluso dall'infrastruttura di protezione. Nella seguente figura viene mostrata una visualizzazione più particolareggiata del modello di difesa antivirus a più livelli:

[![](images/Dd536185.AVFG0302(it-it,TechNet.10).gif "Figura 3.2 Visualizzazione particolareggiata del modello di difesa antivirus a più livelli")](https://technet.microsoft.com/it-it/dd536185.avfg0302_big(it-it,technet.10).gif)

**Figura 3.2 Visualizzazione particolareggiata del modello di difesa antivirus a più livelli**

Per garantire la protezione dei client e dei server dell'organizzazione, è possibile combinare i livelli dei dati, dell'applicazione e dell'host in due strategie di difesa. Sebbene queste difese condividano numerose strategie comuni, le differenze a livello di implementazione delle difese dei client e dei server sono sufficienti per garantire un approccio di difesa univoco per ciascuno.

I livelli delle reti interne e perimetrali possono essere combinati in una strategia di protezione della rete comune, in quanto le tecnologie coinvolte sono identiche per entrambi i livelli. I dettagli di implementazione sono differenti in ciascun livello, a seconda della posizione delle periferiche e delle tecnologie nell'infrastruttura dell'organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Protezione client

Quando un'applicazione software dannosa raggiunge un computer host, i sistemi di difesa devono essere mirati a proteggere il sistema host e i relativi dati e a impedire la diffusione dell'infezione. Queste difese non sono meno importanti delle difese a livello di protezione fisica e di rete del proprio ambiente. È consigliabile progettare le difese del sistema basandosi sul presupposto che il software dannoso sia riuscito a penetrare in tutti i precedenti livelli di difesa. Questo approccio rappresenta il modo migliore per ottenere il più elevato livello di protezione.

#### Procedura per la protezione antivirus dei client

Esistono numerosi approcci e tecnologie che è possibile utilizzare per le configurazioni antivirus dei client. Nelle sezioni riportate di seguito vengono forniti i dettagli che Microsoft consiglia di prendere in considerazione.

##### Passaggio 1: ridurre la superficie di attacco

La prima linea di difesa a livello di applicazione prevede la riduzione della superficie di attacco del computer. Per ridurre al minimo i numerosi modi con cui un autore di attacchi potrebbe sfruttare il sistema, è consigliabile rimuovere o disattivare sul computer tutte le applicazioni o i servizi non necessari.

Le impostazioni predefinite per i servizi di Windows XP Professional sono disponibili nella pagina Default settings for services nella documentazione di Windows XP Professional sul sito Web Microsoft.com all'indirizzo: <http://www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/sys_srv_default_settings.mspx> (in inglese).

Una volta ridotta al minimo la superficie di attacco senza influire sulle funzionalità necessarie del sistema, la principale difesa da utilizzare a questo livello è rappresentata da uno strumento di scansione antivirus. Il ruolo principale dello strumento di scansione consiste nel rilevare e impedire un attacco e nell'informare l'utente e probabilmente gli amministratori del sistema all'interno dell'organizzazione di un'eventuale violazione della protezione.

##### Passaggio 2: applicare gli aggiornamenti della protezione

La possibilità di connettere un'ampia gamma di computer client alle reti di un'organizzazione può rendere difficoltosa la fornitura di un servizio di gestione degli aggiornamenti di protezione veloce e affidabile. Microsoft e altre società produttrici di software hanno sviluppato numerosi strumenti che è possibile utilizzare per gestire questo problema. Attualmente, Microsoft fornisce i seguenti strumenti di aggiornamento della protezione e gestione delle patch:

-   **Windows Update**: per le organizzazioni di piccole dimensioni o i singoli utenti, il servizio Windows Update fornisce un processo automatico e manuale per il rilevamento e il download delle modifiche più recenti della protezione e delle funzionalità per la piattaforma Windows. I problemi correlati a questo approccio che alcune organizzazioni si trovano ad affrontare includono la mancanza di supporto per le procedure di test prima della distribuzione degli aggiornamenti offerti da questo servizio e la quantità di larghezza di banda della rete che i client possono utilizzare nell'organizzazione quando scaricano contemporaneamente lo stesso pacchetto. Le informazioni sull'uso di questo servizio sono disponibili nella home page di Windows Update all'indirizzo:
    [www.windowsupdate.com](http://www.windowsupdate.com/) (in inglese).

-   **Software Update Service**: questo servizio è stato progettato per fornire una soluzione di aggiornamento della protezione per i client Windows all'interno dell'azienda. Il servizio risolve i difetti del servizio Windows Update per le organizzazioni di grandi dimensioni consentendo sia il test interno che la gestione degli aggiornamenti della protezione distribuiti. Le informazioni sull'utilizzo di questo servizio per lo sviluppo di una soluzione per la propria organizzazione sono disponibili nella home page di Software Update Service sul sito Web Microsoft.com all'indirizzo:
    [http://www.microsoft.com/windowsserversystem/sus/](http://technet.microsoft.com/en-us/wsus/bb466186.aspx) (in inglese).

-   **Systems Management Server 2003**: Microsoft Systems Management Server 2003 è una soluzione di gestione aziendale completa in grado di fornire, tra le altre funzionalità, servizi di aggiornamento della protezione completi. Per ulteriori informazioni su questa soluzione, vedere la home page di Systems Management Server sul sito Web Microsoft.com all'indirizzo:
    <http://www.microsoft.com/smserver/default.asp> (in inglese).

Ciascuno di questi strumenti di aggiornamento della protezione offerti da Microsoft possiede specifici punti di forza e obiettivi. L'approccio ottimale prevede probabilmente l'utilizzo di uno o più di questi strumenti. Per informazioni sulle soluzioni di aggiornamento della protezione più appropriate per la propria organizzazione, vedere il confronto delle funzionalità fornito nella pagina Choosing a Security Update Management Solution sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/windowsserversystem/sus/suschoosing.mspx> (in inglese).

##### Passaggio 3: attivare un firewall basato su host

Il firewall personale o basato su host rappresenta un importante livello di difesa dei client che è consigliabile attivare, in particolare sui computer portatili che potrebbe essere portati dagli utenti all'esterno degli usuali sistemi di difesa fisica e della rete. Questi firewall filtrano tutti i dati che si tenta di immettere o di prelevare da uno specifico computer host.

Windows XP include un semplice firewall personale denominato ICF (Internet Connection Firewall). Una volta attivato, il firewall ICF monitora tutti gli aspetti della comunicazione dei dati che lo attraversano. Il firewall ICF è in grado inoltre di controllare l'indirizzo di origine e di destinazione di ciascun pacchetto di dati che gestisce per assicurare che siano consentite tutte le comunicazioni. Per ulteriori informazioni sul firewall ICF, vedere la Guida in linea di Windows XP e la pagina Use the Internet Connection Firewall sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/windowsxp/pro/using/howto/networking/icf.asp> (in inglese).

Windows XP Service Pack 2 introduce un'ampia gamma di miglioramenti significativi del firewall ICF (ora denominato *Windows Firewall*) e altri miglioramenti orientati alla protezione. Un service pack è un insieme cumulativo testato di tutti gli aggiornamenti rapidi, gli aggiornamenti della protezione, gli aggiornamenti critici e gli aggiornamenti creati per i difetti rilevati all'interno di un prodotto dopo il rilascio. I service pack possono contenere anche un numero limitato di modifiche o funzionalità richieste dal cliente. Per informazioni su questo aggiornamento per Windows XP, vedere la pagina Windows XP Service Pack 2 sul sito Web Microsoft TechNet all'indirizzo:
<http://www.microsoft.com/technet/prodtechnol/winxppro/sp2preview.mspx> (in inglese).

Le versioni di Windows precedenti a Windows XP non sono state fornite con un firewall incorporato. Sono disponibili soluzioni firewall basate su host di terze parti che è possibile installare per fornire servizi firewall nelle versioni precedenti di Windows e migliorare i servizi firewall nei client Windows XP. Per informazioni su questi prodotti firewall, vedere la pagina relativa alle domande frequenti sui firewall interni sul sito Web Microsoft Proteggi il tuo PC all'indirizzo:
[http://www.microsoft.com/italy/security/protect/firewall.asp](http://www.microsoft.com/security/protect/firewall.asp).

##### Passaggio 4: installare il software antivirus

Molte società producono applicazioni antivirus, ciascuna delle quali tenta di proteggere il computer host creando pochi disagi e richiedendo un livello di interazione minimo con gli utenti finali. La maggior parte di queste applicazioni fornisce funzionalità di protezione di grande efficacia, ma tutte richiedono aggiornamenti frequenti per stare al passo con il software dannoso più recente. Qualsiasi soluzione antivirus dovrebbe fornire un meccanismo rapido e semplice per assicurare che gli aggiornamenti ai *file delle firme* richiesti per la gestione di nuovi software dannosi o varianti vengano rilasciati il più presto possibile. Un file di firma contiene informazioni utilizzate dai programmi antivirus per rilevare software dannosi durante un'operazione di scansione. I file delle firme sono progettati per essere aggiornati regolarmente dai fornitori di applicazioni antivirus e scaricati sul computer client.

**Nota**: questi aggiornamenti presentano rischi di protezione intrinseci, in quanto i file delle firme vengono inviati dal sito di supporto dell'applicazione all'applicazione host (in genere via Internet). Se ad esempio il meccanismo di trasferimento prevede l'utilizzo del protocollo FTP (File Transfer Protocol) per ottenere il file, i firewall perimetrali dell'organizzazione dovranno consentire questo tipo di accesso al server FTP richiesto su Internet. Assicurarsi che durante il processo di verifica dei rischi antivirus venga esaminato il meccanismo di aggiornamento per l'organizzazione e che questo processo sia sufficientemente sicuro per soddisfare i requisiti di protezione dell'organizzazione.

A causa della rapida evoluzione degli schemi e delle tecniche di attacco di software dannosi, alcune organizzazioni hanno adottato un approccio che prevede la necessità che gli utenti esposti a rischi elevati eseguano più pacchetti antivirus sullo stesso computer al fine di ridurre al minimo il rischio che software dannosi non vengano rilevati. In questa categoria rientrano in genere i seguenti tipi di utenti:

-   Webmaster o chiunque amministri contenuto su Internet o una rete Intranet.

-   Addetti ai laboratori di rilascio o chiunque produca supporti elettronici, quali CD-ROM.

-   Membri dei team di sviluppo che creano o compilano file compressi o altri prodotti software.

Tenere presente che l'esecuzione di applicazioni antivirus di fornitori differenti sullo stesso computer potrebbe causare problemi a causa della mancanza di interoperabilità tra le applicazioni antivirus. I problemi del sistema che possono verificarsi in conseguenza dell'esecuzione contemporanea di più applicazioni antivirus nell'ambiente in uso comprendono:

-   **Sovraccarico della memoria:** molte applicazioni antivirus utilizzano agenti attivi che risiedono in memoria riducendo la quantità di memoria di sistema disponibile.

-   **Arresti anomali del sistema o errori di interruzione**: gli arresti anomali e gli errori di interruzione possono essere causati da applicazioni antivirus che tentano di eseguire contemporaneamente la scansione dello stesso file.

-   **Deterioramento delle prestazioni**: durante l'analisi dei file tramite le applicazioni antivirus per individuare codice dannoso, le prestazioni del sistema potrebbero subire un deterioramento. Quando si utilizzano più applicazioni, le scansioni vengono eseguite ripetutamente, il che potrebbe ridurre le prestazioni del sistema a un livello inaccettabile.

-   **Perdita dell'accesso al sistema**: l'esecuzione contemporanea di più applicazioni antivirus potrebbe causare un arresto del sistema durante l'avvio. Questo problema è più comune nelle versioni precedenti di Windows, quali Microsoft Windows® NT e Windows 9*x*.

Per questi motivi, l'utilizzo di più applicazioni antivirus sullo stesso computer non è una strategia consigliata e dovrebbe essere evitato, se possibile.

Un approccio alternativo da prendere in considerazione è l'utilizzo di software antivirus di fornitori differenti per la protezione dei client, dei server e della rete all'interno dell'organizzazione. Questo approccio consente una scansione coerente di queste diverse aree dell'infrastruttura mediante l'uso di diversi motori di scansione, che consentono di ridurre il rischio di una potenziale violazione delle difese antivirus globali dell'organizzazione nel caso in cui il prodotto di un singolo fornitore non sia in grado di rilevare un attacco.

Per ulteriori informazioni sui fornitori di software antivirus, vedere la pagina relativa ai partner antivirus Microsoft sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/security/partners/antivirus.asp> (in inglese).

Per ulteriori informazioni sui software antivirus progettati per Windows XP, vedere la pagina Microsoft Windows Catalog Antivirus sul sito Web Microsoft.com all'indirizzo: [http://go.microsoft.com/fwlink/?LinkId=28506](http://go.microsoft.com/fwlink/?linkid=28506) (in inglese).

##### Passaggio 5: eseguire il test con strumenti di scansione delle vulnerabilità

Una volta configurato un sistema, è consigliabile controllarlo periodicamente per assicurarsi che siano stati eliminati tutti i punti deboli della protezione. Per semplificare l'esecuzione di questo processo, è possibile utilizzare numerose applicazioni che fungono da strumenti di scansione al fine di individuare eventuali punti deboli che software dannosi e pirati informatici potrebbero tentare di sfruttare. Gli strumenti migliori sono in grado di aggiornare le relative routine di scansione per difendere il sistema dai punti deboli più recenti.

Microsoft Baseline Security Analyzer (MBSA) è un esempio di strumento di scansione delle vulnerabilità in grado di verificare la presenza dei problemi di configurazione della protezione più comuni. Questo strumento è in grado inoltre di eseguire una serie di controlli per verificare che l'host sia configurato con gli aggiornamenti di protezione più recenti.

Per ulteriori informazioni su questo strumento di configurazione gratuito, vedere la pagina Microsoft Baseline Security Analyzer V1.2 sul sito Web TechNet all'indirizzo: <http://www.microsoft.com/technet/security/tools/mbsahome.mspx> (in inglese).

##### Passaggio 6: utilizzare criteri con privilegi minimi

Un'altra area da non trascurare tra i sistemi di protezione dei client è rappresentata dai privilegi assegnati agli utenti in situazioni di normale operatività. Microsoft consiglia di adottare un criterio che fornisca il minor numero di privilegi possibile per consentire di ridurre al minimo l'impatto di software dannosi che si basano sullo sfruttamento dei privilegi utente durante l'esecuzione. Questo criterio è particolarmente importante per gli utenti che in genere dispongono di privilegi amministrativi locali. Prendere in considerazione la rimozione di questi privilegi per l'esecuzione delle operazioni quotidiane e l'utilizzo del comando **RunAs** per avviare gli strumenti di amministrazione necessari.

Un utente che ha l'esigenza di installare un'applicazione che richiede i privilegi di amministratore potrebbe ad esempio eseguire il seguente comando di installazione al prompt dei comandi per avviare il programma di installazione con i privilegi appropriati:

```
runas /user:mydomain\admin "setup.exe"
```

È possibile inoltre accedere a questa funzione direttamente da Esplora risorse di Microsoft effettuando le seguenti operazioni:


**Per eseguire un programma con privilegi amministrativi**

1.  In Esplora risorse selezionare il programma o lo strumento che si desidera aprire, ad esempio lo snap-in Microsoft Management Console (MMC) o il Pannello di controllo.

2.  Fare clic con il pulsante destro del mouse sul programma o sullo strumento aperto e selezionare l'opzione **Esegui come**.

    **Nota**: se l'opzione **Esegui come** non viene visualizzata, mentre si fa clic con il pulsante destro del mouse sullo strumento tenere contemporaneamente premuto il tasto **MAIUSC**.

3.  Nella finestra di dialogo **Esegui come** selezionare l'opzione **Utente seguente:**.

4.  Nelle caselle **Nome utente** e **Password** digitare il nome utente e la password per l'account di amministratore che si desidera utilizzare.

##### Passaggio 7: limitare l'accesso da parte di applicazioni non autorizzate

Se un'applicazione fornisce un servizio alla rete, quale Microsoft Instant Messenger o un servizio Web, potrebbe, in teoria, diventare il bersaglio di un attacco di software dannoso. Come parte della soluzione antivirus, è opportuno prendere in considerazione la creazione di un elenco di applicazioni autorizzate nell'organizzazione. I tentativi di installare un'applicazione non autorizzata in uno dei computer client in uso potrebbe esporre tutti i client e i dati in essi contenuti a un più elevato elevato rischio di attacchi di software dannosi.

Se l'organizzazione desidera limitare l'accesso da parte di applicazioni non autorizzate, sarà possibile utilizzare i criteri di gruppo di Windows per limitare la capacità degli utenti di eseguire software non autorizzato. La modalità di utilizzo dei criteri di gruppo è già stata ampiamente documentata e informazioni dettagliate in merito sono disponibili in [Windows Server 2003 Group Policy Technology Center](http://www.microsoft.com/windowsserver2003/technologies/management/grouppolicy/default.mspx) sul sito Web Microsoft.com all'indirizzo:
www.microsoft.com/windowsserver2003/technologies/management/grouppolicy/ (in inglese).

L'area specifica dei criteri di gruppo che gestisce questa funzione è denominata Criteri di restrizione software, a cui è possibile accedere tramite lo snap-in MMC Criteri di gruppo standard. Nella seguente figura viene visualizzata una schermata MMC Criteri di gruppo in cui viene illustrato il percorso in cui è possibile impostare i criteri di restrizione software per i computer e gli utenti:

[![](images/Dd536185.AVFG0303(it-it,TechNet.10).gif "Figura 3.3 Percorso delle cartelle dei criteri di restrizione software nello snap-in MMC Criteri di gruppo")](https://technet.microsoft.com/it-it/dd536185.avfg0303_big(it-it,technet.10).gif)

**Figura 3.3 Percorso delle cartelle dei criteri di restrizione software nello snap-in MMC Criteri di gruppo**

Per accedere a questo snap-in direttamente da un client Windows XP, completare le seguenti operazioni:

1.  Fare clic su **Start** e scegliere **Esegui**.

2.  Digitare secpol.msc, quindi scegliere **OK**.

Una descrizione dettagliata di tutte le impostazioni possibili non rientra nell'ambito della presente guida. Tuttavia, nell'articolo "Utilizzo dei criteri di restrizione software per la protezione contro il software non autorizzato" sul sito Web TechNet all'indirizzo:
<http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/rstrplcy.mspx> (in inglese) vengono fornite istruzioni dettagliate per l'utilizzo di questa potente funzionalità del sistema operativo Windows XP Professional.

**Avviso**: i criteri di gruppo sono una tecnologia estremamente potente la cui implementazione richiede un'attenta configurazione e una conoscenza approfondita. Non tentare di modificare queste impostazioni direttamente fino a quando non si è sicuri di conoscere le impostazioni dei criteri e non si sono testati i risultati su un sistema non di produzione.

#### Impostazioni antivirus per applicazioni client

Nelle sezioni riportate di seguito vengono fornite istruzioni per la configurazione di specifiche applicazioni client che potrebbero essere prese di mira da attacchi di software dannoso.

##### Client di posta elettronica

Se il software dannoso riesce a superare le difese antivirus a livello di rete e di server di posta elettronica, sarà possibile configurare alcune impostazioni per garantire un livello di protezione aggiuntivo per il client di posta elettronica.

In genere, la capacità di un utente di aprire allegati di posta elettronica direttamente da un messaggio di posta elettronica fornisce uno dei principali metodi per la propagazione sul client di software dannoso. Se possibile, prendere in considerazione l'ipotesi di limitare questa capacità nei sistemi di posta elettronica dell'organizzazione. Se non è possibile eseguire questa operazione, alcuni client di posta elettronica consentiranno di configurare ulteriori operazioni che gli utenti dovranno eseguire prima di aprire un allegato. In Microsoft Outlook® e Outlook Express è possibile ad esempio effettuare le seguenti operazioni:

-   Utilizzare le aree di protezione di Internet Explorer per disattivare il contenuto attivo nei messaggi di posta elettronica HTML.

-   Attivare un'impostazione che consenta agli utenti di visualizzare solo i messaggi di posta elettronica in testo normale.

-   Impedire ai programmi di inviare messaggi di posta elettronica senza la specifica approvazione dell'utente.

-   Bloccare gli allegati di messaggi di posta elettronica non protetti.

Per informazioni sulla modalità di configurazione di queste funzionalità, vedere l'articolo della Microsoft Knowledge Base "291387 - OLEXP: Using Virus Protection features in Outlook Express 6" all'indirizzo:
<http://support.microsoft.com/?kbid=291387> (in inglese).

Microsoft Outlook 2003 fornisce funzionalità aggiuntive per la protezione da software dannosi e messaggi di posta indesiderata. Informazioni sulla configurazione di queste funzionalità sono disponibili nella pagina [Customizing Outlook 2003 to Help Prevent Viruses](http://www.microsoft.com/office/ork/2003/three/ch12/default.htm) sul sito Web Microsoft.com all'indirizzo:
www.microsoft.com/office/ork/2003/three/ch12/ (in inglese).

##### Applicazioni per desktop

Essendo sempre più potenti, le applicazioni per desktop sono diventate oggi i principali bersagli di attacchi di software dannoso. Per replicarsi, i virus macro utilizzano i file creati da applicazioni di elaborazione testi, fogli di calcolo o altre applicazioni abilitate per le macro.

È opportuno intraprendere le misure necessarie ove possibile per far sì che le impostazioni di protezione più appropriate vengano attivate in tutte le applicazioni nell'ambiente in uso che gestiscono questi file. Per informazioni sulla protezione delle applicazioni di Microsoft Office 2003, vedere la pagina Best practices for protection from viruses sul sito Web Microsoft.com all'indirizzo:
[http://go.microsoft.com/fwlink/?LinkId=28509](http://go.microsoft.com/fwlink/?linkid=28509) (in inglese).

##### Applicazioni di messaggistica immediata

Sebbene abbia consentito di migliorare le comunicazioni degli utenti in tutto il mondo, tuttavia, il meccanismo di messaggistica immediata ha anche fornito un'altra applicazione che è potenzialmente in grado di consentire al software dannoso di insediarsi nel sistema. Sebbene i messaggi di testo non costituiscano un pericolo di software dannoso diretto, la maggior parte dei client di messaggistica immediata forniscono ulteriori funzionalità di trasferimento dei file per migliorare le capacità di comunicazione degli utenti. Il supporto dei trasferimenti di file fornisce un mezzo diretto alla rete di un'organizzazione per potenziali attacchi di software dannoso.

I firewall di rete possono bloccare i trasferimenti di file semplicemente filtrando le porte utilizzate per questa comunicazione. I client Microsoft Windows e MSN® Messenger utilizzano ad esempio per il trasferimento dei file un intervallo di porte TCP compreso tra 6891 e 6900. Pertanto, se il firewall perimetrale blocca queste porte, non sarà possibile eseguire il trasferimento dei file tramite un'applicazione di messaggistica immediata. Tuttavia, i computer client portatili vengono protetti solo quando risiedono nella rete dell'organizzazione. Per questo motivo, è opportuno configurare il firewall basato su host nei client in uso per il blocco di queste porte e proteggere i client portatili nell'organizzazione quando sono al di fuori delle difese della rete.

Se l'organizzazione non è in grado di bloccare queste porte perché utilizzate da altre applicazioni richieste o perché il trasferimento dei file è necessario, si consiglia di analizzare tutti i file per verificare la presenza di eventuale software dannoso prima di eseguirne il trasferimento. Se le workstation client non utilizzano uno strumento di scansione antivirus in tempo reale, si consiglia di configurare l'applicazione di messaggistica immediata per il passaggio automatico dei file trasferiti a un'applicazione antivirus in modo da eseguirne la scansione non appena vengono ricevuti. È possibile ad esempio configurare MSN Messenger per la scansione automatica dei file trasferiti. Nella seguente procedura viene illustrato come attivare questa funzionalità di protezione:

**Nota**: l'applicazione Windows Messenger fornita con Windows XP non supporta questa funzionalità. Per questa applicazione, è consigliabile utilizzare uno strumento di scansione antivirus in tempo reale.

**Per eseguire la scansione dei file trasferiti tramite MSN Messenger**

1.  Nella finestra principale di MSN Messenger scegliere **Opzioni** dal menu **Strumenti**.

2.  Fare clic sulla scheda **Messaggi**.

3.  In **Trasferimento di file** selezionare la casella di controllo **Scan for viruses using**.

4.  Fare clic su **Sfoglia**, selezionare il software di scansione antivirus in uso, quindi scegliere **OK**.

    **Nota**: la ricerca del file eseguibile corretto da utilizzare e del parametro di comando da includere in questo file potrebbe richiedere un input aggiuntivo dal parte del fornitore del software di scansione antivirus.

Una volta completati questi passaggi, il software antivirus eseguirà automaticamente la scansione di tutti i file ricevuti sul client tramite MSN Messenger.

**Nota**: lo strumento di scansione antivirus potrebbe richiedere operazioni di installazione aggiuntive. Per ulteriori informazioni, fare riferimento alle istruzioni fornite con il software di scansione antivirus.

##### Browser

Prima di scaricare o eseguire codice da Internet, assicurarsi che provenga da un'origine conosciuta e affidabile. È opportuno che gli utenti non facciano affidamento semplicemente sull'aspetto o sull'indirizzo del sito, in quanto gli indirizzi e le pagine Web possono essere contraffatti.

Sono state sviluppate numerose tecniche e tecnologie che consentono all'applicazione browser di un utente di determinare l'affidabilità del sito Web che si sta esplorando. Per verificare l'identità del codice scaricato, in Microsoft Internet Explorer viene utilizzata ad esempio la tecnologia Microsoft Authenticode®. La tecnologia Authenticode consente di verificare che il codice contenga un certificato valido, che l'identità dell'autore del software corrisponda al certificato e che il certificato sia ancora valido. Se tutti questi test vengono superati, il rischio che un utente malintenzionato trasferisca codice dannoso nel sistema risulterà ridotto.

La maggior parte delle principali applicazioni browser supporta la capacità di limitare il livello di accesso automatico disponibile al codice eseguito da un server Web. Per impedire al contenuto Web di eseguire operazioni potenzialmente dannose sul client, in Internet Explorer vengono utilizzate le aree di protezione. Le aree di protezione sono basate sulla posizione (zona) del contenuto Web.

Se ad esempio si è sicuri che tutto il contenuto scaricato all'interno della rete Intranet dell'organizzazione sia sicuro, sarà possibile configurare le impostazioni di protezione dei client per l'area Intranet locale su un livello basso in modo da consentire agli utenti di scaricare il contenuto dalla rete Intranet con poche o nessuna restrizione. Se tuttavia l'origine del download si trova nell'area Internet o nell'area Siti con restrizioni, è opportuno configurare le impostazioni di protezione dei client su un livello medio o elevato. Se si configurano queste impostazioni, nei browser client verrà chiesto agli utenti di immettere informazioni sul certificato del contenuto prima del download o si impedirà loro di scaricare il certificato.

Per ulteriori informazioni sui problemi correlati alla protezione per Internet Explorer, vedere la pagina [Internet Explorer Security Center](http://www.microsoft.com/technet/security/prodtech/ie/default.mspx) sul sito Web Microsoft.com all'indirizzo:
www.microsoft.com/technet/security/prodtech/ie/ (in inglese).

##### Applicazioni peer-to-peer

L'avvento delle applicazioni peer-to-peer (P2P) per Internet ha semplificato più che mai la ricerca e lo scambio di file con altri utenti. Sfortunatamente, questa situazione ha favorito numerosi attacchi di software dannoso che tentano di utilizzare queste applicazioni per replicare i file sui computer di altri utenti. Per replicarsi, i worm, come W32.HLLW.Sanker, hanno utilizzato applicazioni P2P, quale Kazaa. Esistono molti altri esempi di software dannosi che tentano di utilizzare altre applicazioni peer-to-peer, quali Morpheus e Grokster.

I problemi di protezione correlati alle applicazioni P2P hanno poco a che vedere con gli stessi programmi client. Questi problemi sono invece strettamente correlati alla capacità di queste applicazioni di fornire un routing diretto da un computer all'altro attraverso cui è possibile trasmettere il contenuto eludendo i controlli di protezione appropriati.

Se possibile, Microsoft consiglia di limitare il numero di client all'interno dell'organizzazione che utilizzano queste applicazioni. Per impedire agli utenti di eseguire applicazioni peer-to-peer, è possibile utilizzare i criteri di restrizione software di Windows illustrati in precedenza in questo capitolo. Se non è possibile eseguire questa operazione nel proprio ambiente, assicurarsi che i criteri antivirus prendano in considerazione il maggiore rischio a cui i client dell'organizzazione sono esposti a causa di queste applicazioni.

[](#mainsection)[Inizio pagina](#mainsection)

### Protezione server

L'infrastruttura di protezione dei server ha molto in comune con l'infrastruttura di protezione dei client, in quanto entrambe mirano a proteggere lo stesso ambiente di computer di base. La principale differenza tra i due tipi di difese sta nel fatto che, in genere, sulla protezione dei server viene posto un maggiore livello di aspettativa per quanto riguarda l'affidabilità e le prestazioni. Inoltre, i ruoli dedicati che molti server svolgono all'interno dell'infrastruttura di un'organizzazione in genere favoriscono la creazione di una soluzione di difesa specializzata. Le informazioni nelle sezioni riportate di seguito sono incentrate sulle principali differenze tra la protezione dei server e la protezione dei client illustrata in precedenza.

#### Procedura per la protezione antivirus dei server

Le configurazioni antivirus dei server variano notevolmente a seconda del ruolo dello specifico server e dei servizi forniti. Il processo di riduzione al minimo della superficie di attacco di un server viene in genere definito *protezione avanzata*. Sono disponibili informazioni particolarmente utili sulla protezione avanzata di Windows Server 2003 quando viene utilizzato in diversi ruoli tipici all'interno di un'organizzazione. Per ulteriori informazioni su questo argomento, vedere la pagina di indice Protezione dei server sul sito Web Microsoft.com all'indirizzo:
[http://www.microsoft.com/italy/security/guidance/topics/ServerSecurity.mspx](http://www.microsoft.com/italy/technet/security/guidance/topics/serversecurity.mspx).

Quattro dei passaggi antivirus di base per la difesa dei server nell'organizzazione sono identici a quelli eseguiti per i client.

1.  **Ridurre la superficie di attacco**. rimuovere i servizi e le applicazioni indesiderati dai server per ridurre al minimo la relativa superficie di attacco.

2.  **Applicare gli aggiornamenti di protezione**. Assicurarsi che su tutti i computer server vengano eseguiti gli aggiornamenti di protezione più recenti, se possibile. Eseguire ulteriori procedure di test in base alle esigenze per assicurarsi che i server mission-critical non vengano influenzati negativamente dai nuovi aggiornamenti.

3.  **Attivare il firewall basato su host**. Windows Server 2003 include un firewall basato su host che è possibile utilizzare per ridurre la superficie di attacco dei server e rimuovere applicazioni e servizi non desiderati.

4.  **Eseguire i test mediante gli strumenti di scansione delle vulnerabilità**. Utilizzare MBSA su Windows Server 2003 per identificare potenziali vulnerabilità in una configurazione server. Microsoft consiglia di utilizzare questo strumento e altri strumenti di scansione delle vulnerabilità specializzati per garantire una configurazione il più efficace possibile.

Oltre a queste comuni procedure antivirus, prendere in considerazione l'utilizzo del seguente software specifico per i server come parte delle difese antivirus dei server globali.

##### Software antivirus dei server generale

La principale differenza tra le applicazioni antivirus progettate per gli ambienti client, quale Windows XP, e quelle progettate per gli ambienti server, quale Windows Server 2003, è rappresentata dal livello di integrazione tra lo strumento di scansione basato su server e i servizi basati su server, come i servizi di messaggistica o di database. Anche molte applicazioni antivirus basate su server offrono funzionalità di gestione remota per ridurre al minimo la necessità dell'accesso fisico alla console del server.

Tra gli altri importanti problemi da prendere in considerazione durante la valutazione del software antivirus per l'ambiente server figurano:

-   **Utilizzo della CPU durante la scansione**: in un ambiente server, l'utilizzo della CPU è una componente essenziale della capacità del server di svolgere il rispettivo ruolo principale per l'organizzazione.

-   **Affidabilità dell'applicazione**: un arresto anomalo del sistema su un importante server del centro dati ha un impatto maggiore rispetto all'arresto anomalo di una singola workstation. Pertanto, per verificare l'affidabilità del sistema, Microsoft consiglia di testare completamente tutte le applicazioni antivirus basate su server.

-   **Sovraccarico di gestione**: la capacità di autogestione delle applicazioni antivirus potrebbe ridurre il sovraccarico amministrativo per i team di gestione dei server all'interno dell'organizzazione.

-   **Interoperabilità delle applicazioni**: per verificare che non esistano problemi di interoperabilità, è consigliabile testare le applicazioni antivirus con gli stessi servizi e applicazioni basati su server che verranno eseguiti sul server di produzione.

##### Software e configurazioni antivirus specifici per i ruoli

Attualmente è disponibile una serie di configurazioni, strumenti e applicazioni antivirus specializzati per specifici ruoli server all'interno dell'azienda. Esempi di ruoli server che possono trarre vantaggio da questo tipo di difesa antivirus specializzata:

-   **Server Web**, quali i server di Microsoft Internet Information Services (IIS).

-   **Server di messaggistica**, quali i server di Microsoft Exchange 2003.

-   **Server di database**, quali i server che eseguono Microsoft SQL Server™ 2000.

-   **Server di collaborazione**, quali i server che eseguono Microsoft Windows SharePoint™ Services e Microsoft Office SharePoint Portal Server™ 2003.

Le soluzioni antivirus specifiche delle applicazioni in genere forniscono livelli di protezione e prestazioni migliori, in quanto sono progettate per l'integrazione con uno specifico servizio anziché per l'utilizzo in un livello inferiore rispetto al servizio a livello di file system. Tutti i ruoli server illustrati in questa sezione sono responsabili dell'accesso a informazioni che non sarebbero accessibili a uno strumento di scansione antivirus utilizzato a livello di file system. Sono inoltre disponibili informazioni su ciascuno di questi ruoli server e sulle procedure consigliate da Microsoft per l'utilizzo di specifici configurazioni, strumenti e applicazioni antivirus.

##### Server Web

I server Web in tutti i tipi di organizzazioni sono stati per molto tempo il bersaglio di attacchi alla protezione. Sia che un attacco provenga da software dannoso, quale CodeRed, o da un pirata informatico che tenta di alterare il sito Web di un'organizzazione, è importante che le impostazioni di protezione sui server Web siano adeguatamente configurate per l'ottimizzazione delle difese contro questi attacchi. Microsoft ha sviluppato indicazioni specifiche per gli amministratori del sistema responsabili per la protezione dei server che eseguono IIS sulla rete in "Chapter 8 - Hardening IIS Servers" della *Guida per la protezione di Windows Server 2003* sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/technet/security/prodtech/win2003/w2003hg/sgch08.mspx> (in inglese).

Oltre a questa Guida, è possibile scaricare alcuni strumenti gratuiti in grado di eseguire automaticamente un'ampia gamma di configurazioni di protezione su IIS. Lo strumento di blocco IIS ad esempio è disponibile sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/technet/security/tools/locktool.mspx> (in inglese).

Questo strumento viene utilizzato per configurare il server Web in modo che fornisca solo i servizi necessari per il relativo ruolo, riducendo in tal modo l'area della superficie del server esposta ad attacchi di software dannoso.

UrlScan è un altro strumento di protezione che limita i tipi di richieste HTTP che verranno elaborate su IIS. Bloccando specifiche richieste HTTP, URLScan impedisce che richieste potenzialmente dannose raggiungano il server. Ora è possibile eseguire un'installazione completa di UrlScan 2.5 sui server che eseguono IIS 4.0 o versione successiva. Per ulteriori informazioni su UrlScan, vedere la pagina UrlScan Security Tool sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/technet/security/tools/urlscan.mspx> (in inglese).

##### Server di messaggistica

Durante la progettazione di una soluzione antivirus efficace per i server di posta elettronica all'interno dell'organizzazione, è importante prendere in considerazione due obiettivi principali. Il primo obiettivo consiste nel proteggere i server da attacchi di software dannoso. Il secondo obiettivo consiste nell'impedire a eventuali software dannosi di insediarsi attraverso il sistema di posta elettronica nelle cassette postali degli utenti all'interno dell'organizzazione. È importante assicurarsi che la soluzione antivirus installata sui server di posta elettronica sia in grado di raggiungere entrambi gli obiettivi.

In generale, le soluzioni antivirus standard per la scansione dei file non sono in grado di impedire a un server di posta elettronica di passare software dannoso sotto forma di allegati ai client. Tutti i servizi di posta elettronica, eccetto quelli più semplici, consentono di memorizzare i messaggi di posta elettronica in uno specifico tipo di database, a cui si fa talvolta riferimento con l'espressione *archivio messaggi*. Una tipica soluzione antivirus per la scansione dei file non è in grado di accedere al contenuto di un database di questo tipo. In realtà, una soluzione antivirus per la scansione dei file potrebbe danneggiare un archivio messaggi nel caso in cui tenti la scansione tramite il mapping di un'unità, ad esempio l'unità M: su Exchange Server 5.5 ed Exchange Server 2000.

È importante far corrispondere la soluzione antivirus alla soluzione di posta elettronica in uso. Molti fornitori di programmi antivirus ora offrono versioni dedicate del relativo software per specifici server di posta elettronica che sono progettati per eseguire la scansione dei messaggi che passano attraverso il sistema di posta elettronica per individuare la presenza di software dannoso. Sono in genere disponibili due tipi principali di soluzioni antivirus di posta elettronica:

-   **Strumenti di scansione per gateway SMTP**: queste soluzioni di scansione di posta elettronica basate su SMTP (Simple Mail Transfer Protocol) vengono in genere definite "soluzioni gateway antivirus" e hanno il vantaggio di poter essere utilizzate con tutti i servizi di posta elettronica SMTP anziché essere associate a uno specifico server di posta elettronica. Tuttavia, a causa della dipendenza dal protocollo di posta elettronica SMTP, queste soluzioni presentano delle limitazioni nell'ambito delle funzionalità più avanzate che sono in grado di offrire.

-   **Strumenti di scansione per server integrati**: queste applicazioni antivirus specializzate funzionano direttamente con uno specifico server di posta elettronica e offrono numerosi vantaggi. Sono ad esempio in grado di integrarsi direttamente con le funzionalità server avanzate e sono progettate per utilizzare lo stesso hardware impiegato dal server di posta elettronica.

Microsoft Exchange fornisce una specifica API (Application Programming Interface) antivirus, denominata Virus API (VAPI), a cui si fa riferimento anche con l'espressione Antivirus API (AVAPI) o Virus Scanning API (VSAPI). Questa API viene utilizzata da applicazioni antivirus specializzate per Exchange Server al fine di garantire la protezione completa della messaggistica in modo sicuro e affidabile sui server di posta elettronica Exchange. Per ulteriori informazioni su questa API, vedere l'articolo della Microsoft Knowledge Base "328841 – XADM: Exchange and Antivirus Software" sul sito Web Microsoft.com all'indirizzo:
<http://support.microsoft.com/?kbid=328841> (in inglese).

##### Server di database

Durante la valutazione dell'infrastruttura di protezione da realizzare per un server di database, esistono quattro elementi principali da proteggere:

-   **Host**: il server o i server su cui è in esecuzione il database.

-   **Servizi di database**: le diverse applicazioni in esecuzione sull'host che forniscono il servizio di database alla rete.

-   **Archivio dati**: i dati memorizzati nel database.

-   **Comunicazioni di dati**: le connessioni e i protocolli che vengono utilizzati tra l'host del database e gli altri host sulla rete.

Poiché i dati all'interno dell'archivio dati non sono direttamente eseguibili, si ritiene in genere che gli stessi archivi dati non richiedano la scansione. Attualmente, non sono disponibili applicazioni antivirus progettate specificamente per gli archivi dati. Tuttavia, per le configurazioni antivirus, è opportuno prendere attentamente in considerazione gli altri elementi del server di database, ovvero l'host, i servizi di database e le comunicazioni di dati.

Il posizionamento e la configurazione dell'host devono essere esaminati specificamente per verificare la presenza di pericoli correlati a software dannoso. In generale, Microsoft consiglia di non collocare i server di database nella rete perimetrale dell'infrastruttura di un'organizzazione, soprattutto se nei server vengono memorizzati dati riservati. Tuttavia, se è necessario posizionare un server di database nella rete perimetrale, assicurarsi che sia configurato per la riduzione al minimo del rischio di un'infezione da software dannoso.

Nel caso in cui l'organizzazione utilizzi SQL Server, per ulteriori informazioni sulle linee guida specifiche per la configurazione della protezione da attacchi di software dannoso, vedere i seguenti riferimenti:

-   Articolo della Microsoft Knowledge Base "309422 – INF: Consideration for a Virus Scanner On a Computer That Is Running SQL Server" sul sito Web Microsoft.com all'indirizzo:
    <http://support.microsoft.com/?kbid=309422> (in inglese).

-   Pagina [Security Resources](http://www.microsoft.com/sqlserver/2005/en/us/security.aspx) per Microsoft SQL Server sul sito Web Microsoft.com all'indirizzo:
    www.microsoft.com/sql/techinfo/administration/2000/security/ (in inglese).

Il recente attacco del worm "Slammer" ha colpito direttamente SQL Server. Questo attacco ha mostrato quanto sia importante proteggere i computer dei database di SQL Server, indipendentemente da se risiedano nella rete perimetrale o nella rete interna.

Per informazioni e per i software disponibili in grado di fornire il supporto necessario per assicurarsi che i sistemi SQL Server siano protetti dal worm Slammer, vedere la pagina Finding and Fixing Slammer Vulnerabilities sul sito Web Microsoft.com all'indirizzo:
[http://www.microsoft.com/security/slammer.asp](http://www.microsoft.com/sql/prodinfo/previousversions/slammer.mspx) (in inglese).

##### Server di collaborazione

Per la loro natura intrinseca, i server di collaborazione sono vulnerabili ad attacchi di software dannoso. Quando gli utenti copiano i file in e dai server, potrebbero esporre i server e gli altri utenti in rete ad attacchi di software dannoso. Microsoft consiglia di proteggere i server di collaborazione nell'ambiente in uso, quali i server su cui sono in esecuzione SharePoint Services e SharePoint Portal Server 2003, con un'applicazione antivirus in grado di eseguire la scansione di tutti i file copiati nel e dall'archivio di collaborazione. Per informazioni dettagliate sulla protezione di questi servizi, vedere la pagina Configuring Antivirus Protection in *Administrators Guide for Windows SharePoint Services* sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/resources/documentation/wss/2/all/adminguide/en-us/stse11.mspx> (in inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Livello di difesa della rete

Gli attacchi che in genere vengono sferrati contro la rete rappresentano il maggior numero di problemi di protezione registrati correlati a software dannoso. In genere, gli attacchi di software dannoso vengono lanciati per sfruttare i punti deboli presenti nelle difese della rete perimetrale per consentire al software dannoso di accedere alle periferiche host all'interno dell'infrastruttura IT dell'organizzazione. Queste periferiche potrebbero essere client, server, router o firewall. Uno dei problemi più difficili affrontati dalle difese antivirus a questo livello è rappresentato dalla necessità di trovare un giusto equilibrio tra i requisiti delle funzionalità degli utenti dei sistemi IT e le limitazioni necessarie per creare un'infrastruttura di protezione efficace. Analogamente alla maggior parte degli attacchi recenti, per replicarsi, il worm MyDoom ha utilizzato ad esempio un allegato di posta elettronica. Dalla prospettiva dell'infrastruttura IT, la soluzione più semplice e sicura è quella di bloccare tutti gli allegati in ingresso. Tuttavia, i requisiti degli utenti di posta elettronica dell'organizzazione potrebbero rendere impraticabile un'opzione di questo tipo. È necessario raggiungere un compromesso che consenta di ottenere un giusto equilibrio tra i requisiti di un'organizzazione e il livello di rischio che è disposta ad accettare.

Molte organizzazioni hanno adottato un approccio multilivello alla progettazione delle relative reti che prevede l'utilizzo di strutture di rete interne ed esterne. Microsoft consiglia l'utilizzo di questo approccio in quanto conforme al modello di protezione per la difesa a più livelli.

**Nota**: negli ultimi anni si è sviluppata una crescente tendenza a suddividere la rete interna in aree di protezione per stabilire un perimetro per ciascuna. Microsoft consiglia di utilizzare questo approccio in quanto consente di ridurre il livello di esposizione globale a un attacco di software dannoso che tenta di ottenere l'accesso alla rete interna. Tuttavia, nell'ambito di questa Guida viene descritta una singola difesa della rete. Se si intende utilizzare una rete perimetrale e più reti interne, sarà possibile applicare queste istruzioni direttamente a ciascuna di queste reti.

Le prime difese delle reti dell'organizzazione sono definite come difese della rete perimetrale. Queste difese sono progettate per impedire al software dannoso di penetrare all'interno dell'organizzazione da un punto di attacco esterno. Come illustrato in precedenza in questo capitolo, un tipico attacco di software dannoso prevede la copia di file in un computer di destinazione. Di conseguenza, è consigliabile integrare le difese antivirus con le misure di protezione generali dell'organizzazione per assicurare che l'accesso ai dati dell'organizzazione sia disponibile solo dal personale autorizzato in modalità protetta, ad esempio tramite una connessione VPN (Virtual Private Network) crittografata. Per ulteriori informazioni sulla creazione di una struttura di rete perimetrale protetta, vedere la guida di Microsoft Systems Architecture 2.0 su TechNet all'indirizzo:
<http://www.microsoft.com/resources/documentation/msa/2/all/solution/en-us/default.mspx> (in inglese).

**Nota**: è opportuno inoltre considerare qualsiasi rete LAN e VPN come rete perimetrale. Se l'organizzazione ha implementato queste tecnologie, è importante garantirne la protezione. L'incapacità di garantire un livello di protezione adeguato potrebbe consentire a un pirata informatico di ottenere l'accesso diretto alla rete interna (aggirando le difese standard della rete perimetrale) per sferrare un attacco.

Per ulteriori informazioni sulla protezione delle reti WLAN, vedere i seguenti articoli su TechNet:

-   "Pianifica la protezione di una LAN wireless con Windows Server 2003 Certificate Services" all'indirizzo:
    [http://www.microsoft.com/italy/technet/security/guidance/secmod167.mspx.](http://www.microsoft.com/italy/technet/security/guidance/secmod171.mspx)

-   "Securing Wireless LANs - A Windows Server 2003 Certificate Services Solution" all'indirizzo:
    <http://www.microsoft.com/technet/security/prodtech/win2003/pkiwire/swlan.mspx> (in inglese).

Per informazioni sulla protezione delle reti VPN, vedere il seguente articolo sul sito Web Microsoft.com:

-   MSA Enterprise Design for Remote Access all'indirizzo:
    <http://www.microsoft.com/resources/documentation/msa/2/all/solution/en-us/msa20rak/vmhtm128.mspx>.

In questa Guida si presume che la progettazione della protezione della rete fornisca all'organizzazione il livello necessario di identificazione, autorizzazione, crittografia e protezione per la costituzione di una difesa contro l'intrusione diretta di un utente non autorizzato. Tuttavia, in questa fase le difese antivirus non sono complete. Il passaggio successivo consiste nel configurare le difese a livello di rete per rilevare e filtrare gli attacchi di software dannoso che utilizzano le comunicazioni di rete consentite, quali messaggi di posta elettronica, esplorazione del Web e messaggistica immediata.

#### Configurazione antivirus della rete

Esistono molte configurazioni e tecnologie progettate specificamente per garantire la protezione delle reti delle organizzazioni. Sebbene queste tecniche siano componenti essenziali della progettazione della protezione di un'organizzazione, in questa sezione verranno trattate solo le aree che hanno una relazione diretta con la difesa antivirus. È opportuno che i team responsabili per la progettazione e la protezione della rete determinino la modalità di utilizzo all'interno dell'organizzazione di ciascuna delle tecniche riportate di seguito.

##### Sistema di rilevamento delle intrusioni di rete

Poiché la rete perimetrale è una parte della rete notevolmente esposta a potenziali attacchi, è estremamente importante che i sistemi di gestione della rete siano in grado di rilevare e segnalare un attacco il prima possibile. Il ruolo di un sistema di rilevamento delle intrusioni di rete (NID, Network Intrusion Detection) consiste nel garantire un rapido rilevamento e una rapida segnalazione di attacchi esterni. Sebbene un sistema NID sia parte integrante della progettazione complessiva della protezione del sistema e non uno specifico strumento antivirus, molti dei primi segni sono comuni sia agli attacchi al sistema che agli attacchi di software dannoso. In alcuni software dannosi viene ad esempio utilizzata la scansione IP per individuare i sistemi disponibili da infettare. Per questo motivo, è opportuno configurare il sistema NID per il funzionamento con i sistemi di gestione della rete dell'organizzazione in modo che sia in grado di fornire messaggi di avviso relativi a eventuali comportamenti inusuali della rete direttamente al personale addetto alla protezione dell'organizzazione.

Un aspetto fondamentale da comprendere è rappresentato dal fatto che, con l'implementazione di qualsiasi sistema NID, la misura della validità della relativa protezione è basata sul processo che viene seguito una volta rilevata un'intrusione. È necessario che questo processo attivi difese che è possibile utilizzare per bloccare un attacco e che le difese vengano costantemente monitorate in tempo reale. Solo in questo caso, il processo potrà essere considerato parte di una strategia di difesa. In caso contrario, il sistema NID sarà soltanto uno strumento in grado di fornire un itinerario di controllo dopo che sia stato sferrato un attacco.

I progettisti di rete hanno a disposizione numerosi sistemi di rilevamento delle intrusioni di rete a livello aziendale. Questi sistemi possono essere dispositivi autonomi o altri sistemi in grado di integrarsi in altri servizi di rete, quali i servizi firewall dell'organizzazione. I prodotti Microsoft Internet Security and Acceleration (ISA) Server 2000 e 2004 contengono ad esempio le funzionalità del sistema NID e i servizi firewall e proxy.

Per un elenco dei partner di Microsoft ISA Server che offrono servizi NID aggiuntivi per ISA Server, vedere la pagina Intrusion Detection sul sito Web Microsoft.com all'indirizzo:
[http://www.microsoft.com/isaserver/partners/intrusiondetection.asp](http://technet.microsoft.com/library/cc722757.aspx) (in inglese).

##### Filtraggio a livello di applicazione

L'utilizzo delle tecnologie di filtraggio per Internet per il monitoraggio e lo screening delle comunicazioni di rete per individuare contenuto dannoso, quali i virus, risulta non solo utile ma anche necessario per le organizzazioni. In passato, il filtraggio veniva eseguito tramite il filtraggio a livello di pacchetto fornito dai servizi firewall, che consente di filtrare il traffico di rete solo in base a un indirizzo IP di origine o di destinazione o una specifica porta di rete TCP o UDP. Il filtraggio a livello di applicazione (ALF, Application Layer Filtering) opera al livello di applicazione del modello di rete OSI. Pertanto, consente l'analisi e il filtraggio dei dati in base al relativo contenuto. L'uso combinato della tecnologia ALF con il filtraggio a livello di pacchetto standard consentirà di raggiungere un più elevato livello di protezione. L'utilizzo del filtraggio di pacchetti potrebbe ad esempio consentire il filtraggio del traffico di rete della porta 80 attraverso il firewall dell'organizzazione in modo da consentirne l'indirizzamento solo verso i server Web. Tuttavia, questo approccio potrebbe non fornire un livello di protezione sufficiente. L'aggiunta della tecnologia ALF alla soluzione consentirebbe di controllare il passaggio di tutti i dati ai server Web sulla porta 80 per assicurarsi che siano validi e non contengano codice sospetto.

ISA Server consente di eseguire il filtraggio a livello di applicazione sui pacchetti di dati durante il passaggio attraverso il firewall di un'organizzazione. È possibile eseguire la scansione del browser e della posta elettronica per assicurarsi che il contenuto specifico di ciascuno non contenga dati sospetti, ad esempio posta indesiderata o software dannoso. La funzionalità di filtraggio a livello di applicazione in ISA Server consente un'analisi approfondita del contenuto, inclusa la possibilità di rilevare, controllare e convalidare il traffico utilizzando qualsiasi porta e protocollo. Per un elenco dei fornitori che producono filtri per migliorare la protezione e l'interoperabilità per protocolli differenti e il traffico Web, vedere la pagina Partner Application Filters sul sito Web Microsoft.com .

Per una descrizione dettagliata della modalità di utilizzo del filtraggio a livello di applicazione in ISA Server 2000, vedere la pagina Introducing the ISA Server 2000 Application Layer Filtering Kit all'indirizzo:
[www.isaserver.org/articles/spamalfkit.html](http://www.isaserver.org/articles/spamalfkit.html) (in inglese).

##### Scansione del contenuto

La scansione del contenuto è disponibile come funzionalità in soluzioni firewall più avanzate o come componente di un servizio separato, ad esempio il servizio di posta elettronica. La scansione del contenuto consente di interrogare i dati a cui è consentito entrare o uscire dalla rete di un'organizzazione tramite canali di dati validi. Se viene eseguita sui messaggi di posta elettronica, la scansione del contenuto opererà con i server di posta elettronica per verificare la presenza nei messaggi di posta elettronica di caratteristiche particolari, ad esempio allegati. Questa tecnica consente di analizzare e identificare il contenuto di software dannoso in tempo reale durante il passaggio dei dati attraverso il servizio. Numerosi partner collaborano con Microsoft per fornire funzionalità di protezione avanzate a Microsoft Exchange Server e ISA Server, quale la scansione di contento antivirus in tempo reale.

Per ulteriori dettagli sui prodotti antivirus dei partner disponibili per Microsoft Exchange Server 2003, vedere l'articolo della Microsoft Knowledge Base "823166 "Overview of Exchange Server 2003 and Antivirus Software" sul sito Web Microsoft.com all'indirizzo:
<http://support.microsoft.com/?kbid=823166> (in inglese).

Per un elenco dei partner Microsoft che hanno sviluppato prodotti di scansione del contenuto per ISA Server, vedere la pagina Partners sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/isaserver/partners/> (in inglese).

##### Filtraggio URL

Un'altra opzione disponibile agli amministratori di rete è rappresentata dal filtraggio URL, che è possibile utilizzare per bloccare siti Web che presentano problemi. È possibile ad esempio utilizzare il filtraggio URL per bloccare siti Web, server di download e servizi di posta elettronica HTTP personali di pirati informatici noti.

**Nota**: i principali siti di servizi di posta elettronica HTTP, quali Hotmail e Yahoo, forniscono servizi di scansione antivirus, ma sono disponibili molti siti più piccoli che non forniscono alcuno strumento di scansione antivirus. Questa situazione costituisce un problema serio per le difese di un'organizzazione, in quanto tali servizi forniscono una route diretta da Internet ai client.

Gli amministratori di rete possono utilizzare due approcci di base per il filtraggio URL:

-   **Liste di blocco**: prima di consentire la connessione, il firewall controlla un elenco predefinito di siti che presentano problemi. Agli utenti è consentito connettersi ai siti che non sono presenti nella lista di blocco.

-   **Liste di ammissibilità**: questo approccio consente di stabilire comunicazioni solo con i siti presenti in un elenco predefinito di siti Web che sono stati approvati dall'organizzazione.

Il primo approccio si basa su un processo attivo di identificazione dei siti Web problematici e l'aggiunta di tali siti all'elenco. A causa delle dimensioni e della natura variabile di Internet, questo approccio richiede una soluzione automatica o un significativo sovraccarico di gestione e, in genere, risulta utile solo per bloccare un numero minimo di siti problematici noti anziché fornire una soluzione di protezione completa. Il secondo approccio fornisce un più elevato livello di protezione in quanto la relativa natura restrittiva consente di controllare i siti disponibili agli utenti del sistema. Tuttavia, a meno che non venga eseguita una ricerca corretta per identificare tutti i siti richiesti dagli utenti, questo approccio potrebbe rivelarsi eccessivamente restrittivo per la maggior parte delle organizzazioni.

Microsoft ISA Server supporta la creazione manuale di entrambe le liste utilizzando le rispettive regole relative a contenuto e siti. Tuttavia, i partner Microsoft offrono soluzioni automatiche e avanzate che funzionano direttamente con ISA Server per assicurarsi che gli URL possano essere bloccati o consentiti in base alle esigenze con un sovraccarico di gestione minimo.

Entrambi questi approcci forniranno la protezione solo quando un client si trova all'interno delle difese dell'organizzazione. Questa protezione non è disponibile quando un client portatile è in grado di connettersi direttamente a Internet quando si è fuori dall'ufficio, il che implica che la rete sarà esposta a potenziali attacchi. Se per i client portatili all'interno dell'organizzazione è necessaria una soluzione di filtraggio URL, è opportuno prendere in considerazione l'utilizzo di un sistema di difesa basato su client. Tuttavia, l'adozione di questo approccio può comportare un significativo sovraccarico di gestione, soprattutto in ambienti con un elevato numero di client portatili.

##### Reti di quarantena

Un'altra tecnica che è possibile utilizzare per proteggere le reti consiste nello stabilire una rete per la quarantena dei computer che non soddisfano i requisiti di protezione minimi dell'organizzazione.

**Nota**: questa tecnica non deve essere confusa con la funzionalità di quarantena disponibile in alcune applicazioni antivirus, che prevede lo spostamento di un file infetto in un'area sicura del computer prima che si provveda alla relativa eliminazione.

Una rete di quarantena deve limitare o anche bloccare l'accesso interno alle risorse dell'organizzazione, ma fornire un livello di connettività, incluso Internet, che consenta ai computer di visitatori temporanei di lavorare in modo produttivo senza mettere a rischio la protezione della rete interna. Se un computer portatile di un visitatore viene infettato da software dannoso e si connette alla rete, la relativa capacità di infettare gli altri computer sulla rete interna verrà limitata dalla rete di quarantena.

Un approccio simile è stato applicato per un determinato periodo di tempo alle connessioni remote di tipo VPN. I client VPN vengono deviati verso una rete di quarantena temporanea durante l'esecuzione dei test del sistema. Se il client supera i test, perché dispone ad esempio degli aggiornamenti di protezione e dei file delle firme antivirus necessari, otterrà l'accesso alla rete interna dell'organizzazione. Se il client soddisfa questi requisiti, verrà disconnesso o gli sarà consentito di accedere alla rete di quarantena, che può essere utilizzata per ottenere gli aggiornamenti necessari per superare i test. I progettisti di rete stanno attualmente prendendo in considerazione l'uso di questa tecnologia per migliorare il livello di protezione per le reti interne.

Per ulteriori informazioni su questa tecnica, vedere la pagina Planning for Network Access Quarantine Control in *Microsoft Windows Server 2003 Deployment Kit* sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/resources/documentation/windowsserv/2003/all/deployguide/en-us/dnsbf_vpn_aosh.asp> (in inglese).

##### ISA Server Feature Pack

Se l'organizzazione utilizza ISA Server 2000, Microsoft consiglia di utilizzare anche le funzionalità aggiuntive fornite in ISA Server Feature Pack 1. Questo componente aggiuntivo gratuito include ulteriori funzionalità di protezione che è possibile utilizzare per migliorare la protezione delle comunicazioni (inclusa la posta elettronica) attraverso i firewall all'interno delle difese della rete. Tra le funzionalità che è possibile utilizzare per migliorare le difese della rete antivirus figurano:

-   **Filtro** **SMTP avanzato**. Questa funzionalità consente di filtrare i messaggi di posta elettronica con caratteristiche di affidabilità e protezione avanzate. Il filtraggio è basato sul nome, sulle dimensioni o sull'estensione di un allegato, nonché sul mittente, sul dominio, sulla parola chiave e su qualsiasi comando SMTP e la relativa lunghezza.

-   **Filtro** **RPC (Remote Procedure Call, chiamata a procedura remota) di Exchange avanzato**. Questa funzionalità consente di proteggere la comunicazione tra il sistema di posta elettronica Outlook e i computer Exchange Server su reti non considerate attendibili senza la necessità di impostare una rete VPN. A tal fine, in ISA Server Feature Pack 1 sono incluse le seguenti funzionalità aggiuntive:

    -   Possibilità per gli amministratori di attivare la crittografia RPC tra Outlook ed Exchange Server.

    -   Possibilità per le comunicazioni RPC in uscita di passare in modo protetto attraverso ISA Server, che a sua volta consente ai client Outlook connessi a un computer ISA Server di accedere ai computer Exchange Server esterni.

-   **UrlScan 2.5**. Questo strumento consente di arrestare richieste Web dannose sul computer ISA Server prima che possano entrare nella rete e accedere a un server Web.

-   **Outlook Web Access (OWA) Wizard**. È possibile utilizzare questa procedura guidata per configurare in modo rapido e semplice ISA Server per la protezione di una distribuzione OWA.

-   **RPC Filter Configuration Wizard**. È possibile utilizzare questa procedura guidata solo per consentire un livello di accesso preciso ai servizi RPC sulla rete interna anziché tutto il traffico RPC.

Per ulteriori informazioni sull'utilizzo di queste funzionalità per proteggere un firewall ISA Server perimetrale, vedere la pagina ISA Server Feature Pack 1 sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/isaserver/featurepack1/> (in inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Protezione fisica

Sebbene la protezione fisica rappresenti più un problema di protezione generale piuttosto che uno specifico problema correlato a software dannoso, non è possibile garantire la protezione da software dannoso senza predisporre un piano di difesa fisica efficace per tutte le periferiche client, server e di rete all'interno dell'infrastruttura dell'organizzazione. Un piano di protezione fisica efficace prevede numerosi elementi critici, tra cui:

-   Creazione di un sistema di protezione.

-   Protezione del personale.

-   Punti di accesso alla rete.

-   Computer server.

-   Workstation.

-   Dispositivi e computer portatili.

Ciascuno di questi elementi deve essere valutato in un piano di verifica dei rischi di protezione per l'organizzazione. Se un utente malintenzionato compromette uno di questi elementi, esiste un maggiore livello di rischio che del software dannoso possa superare i confini delle difese delle reti interna ed esterna per infettare un host sulla rete.

La protezione dell'accesso agli edifici della società e ai sistemi di elaborazione deve essere un elemento fondamentale della strategia di protezione globale dell'organizzazione. Una descrizione dettagliata di queste considerazioni non rientra nell'ambito di questa soluzione. Tuttavia, informazioni sugli elementi di base di un piano di protezione fisica efficace è disponibile nell'articolo "5-Minute Security Advisor - Basic Physical Security" nel sito Microsoft TechNet all'indirizzo:
<http://www.microsoft.com/technet/community/columns/5min/5min-203.mspx> (in inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Criteri, procedure e consapevolezza

Le procedure e i criteri operativi per i client, i server e la rete sono aspetti essenziali dei livelli di difesa antivirus all'interno dell'organizzazione. Microsoft consiglia di prendere in considerare l'utilizzo dei seguenti criteri operativi e procedure come parte della soluzione di difesa antivirus a più livelli adottata dall'organizzazione:

-   **Routine di scansione antivirus**: in teoria, è necessario che l'applicazione antivirus in uso supporti la scansione automatica o in tempo reale. Tuttavia, in caso contrario, è consigliabile implementare un processo che fornisca indicazioni sul momento più appropriato in cui gli utenti dell'organizzazione devono eseguire una scansione completa del sistema.

-   **Routine di aggiornamento delle definizioni dei virus**: poiché la maggior parte delle applicazioni antivirus attuali supporta un metodo automatico per il download degli aggiornamenti delle definizioni dei virus, è consigliabile implementare un metodo di questo tipo regolarmente. Tuttavia, se l'organizzazione richiede il test di questi aggiornamenti prima di distribuirli, in generale non si sarà in grado di utilizzare questi metodi. In tal caso, assicurarsi che il personale addetto al supporto tecnico identifichi, scarichi, testi e aggiorni i file delle firme il prima possibile.

-   **Criteri in applicazioni e servizi consentiti**: è necessario che sia disponibile un criterio comunicato in modo chiaro in grado di spiegare quali applicazioni sono consentite sui computer dell'organizzazione e sugli altri computer che accedono alle risorse dell'organizzazione. Esempi di applicazioni che possono causare problemi comprendono applicazioni di rete peer-to-peer e applicazioni che gli utenti possono scaricare direttamente da siti Web inaffidabili.

Microsoft consiglia di utilizzare almeno i criteri e le procedure riportate di seguito per tutte le periferiche nel livello di difesa della rete dell'organizzazione.

-   **Controllo delle modifiche**: un processo di protezione chiave per le periferiche di rete prevede il controllo delle modifiche che hanno effetto su tali periferiche. In teoria, tutte le modifiche devono essere proposte, testate e implementate in modo controllato e documentato. È probabile che modifiche non sottoposte a un accurato controllo alle periferiche nella rete perimetrale introducano errori di configurazione o vulnerabilità che un attacco potrebbe sfruttare.

-   **Monitoraggio della** **rete**: configurare correttamente le periferiche di rete in modo da ottimizzarle per la protezione non implica la possibilità di trascurare altre procedure antivirus. Un monitoraggio continuo di tutte le periferiche nella rete è essenziale per rilevare il prima possibile attacchi di software dannoso. Il monitoraggio è un processo complesso che richiede la raccolta di informazioni da numerose origini, quali firewall, router e switch, per la definizione di una linea di base che rappresenti il normale funzionamento che è possibile utilizzare per identificare comportamenti anomali.

-   **Processo di rilevamento degli attacchi**: se viene rilevato un attacco di software dannoso sospetto, è opportuno che la propria organizzazione disponga di una serie di procedure chiaramente definite e documentate che consentano di assicurarsi che l'attacco venga confermato, controllato ed eliminato limitando al minimo i disagi per gli utenti finali. Per ulteriori informazioni su questo argomento, vedere il Capitolo 4 "Controllo delle violazioni e ripristino".

-   **Criteri di accesso alla rete del computer domestico**: è consigliabile stabilire e soddisfare un set di requisiti minimi prima che un dipendente possa connettere una rete o un computer domestico alla rete dell'organizzazione tramite una connessione VPN.

-   **Criteri di accesso alla rete dei visitatori**: per poter connettersi alla rete dell'organizzazione, è opportuno che i visitatori stabiliscano e soddisfino un set di requisiti minimi. Questi requisiti devono essere applicabili sia alla connettività senza fili che a quella cablata.

-   **Criteri di rete senza fili**: per poter stabilire una connessione, è necessario che tutte le periferiche senza fili che si connettono alla rete interna soddisfino i requisiti di configurazione della protezione minimi. Questi criteri devono specificare la configurazione minima necessaria per l'organizzazione.

Esistono molti altri criteri e procedure che è possibile implementare per migliorare la protezione delle periferiche di rete. I criteri e le procedure riportati in questa sezione rappresentano un valido punto di partenza. Tuttavia, poiché questi criteri e procedure aggiuntivi forniscono impostazioni di protezione generali anziché specifiche impostazioni antivirus, la relativa descrizione esula dall'ambito della presente Guida.

#### Criteri di aggiornamento della protezione

È opportuno che tutte le difese dei client, dei server e della rete dispongano di un sistema di gestione degli aggiornamenti della protezione. Tale sistema potrebbe essere fornito come parte di una più ampia soluzione di gestione delle patch a livello aziendale. È opportuno verificare periodicamente sui sistemi operativi di host e periferiche la disponibilità di aggiornamenti forniti dai produttori. È opportuno inoltre che i criteri di aggiornamento della protezione forniscano i criteri operativi per il processo utilizzato per distribuire gli aggiornamenti della protezione sui sistemi dell'organizzazione. Questo processo prevede le seguenti fasi:

1.  **Verifica della disponibilità di aggiornamenti**: per informare gli utenti sui tipi di aggiornamenti disponibili, occorre disporre di un processo di notifica automatica.

2.  **Download degli aggiornamenti**: è necessario che il sistema sia in grado di scaricare gli aggiornamenti con un impatto minimo sugli utenti e sulla rete.

3.  **Test degli aggiornamenti**: se gli aggiornamenti sono relativi a host mission-critical, è opportuno assicurarsi che ciascun aggiornamento venga testato su un sistema non di produzione appropriato prima che venga distribuito nell'ambiente di produzione.

4.  **Distribuzione degli aggiornamenti**: una volta testato e verificato un aggiornamento, per distribuirlo, è necessario disporre di un semplice meccanismo di distribuzione.

Se i sistemi aggiornati nel proprio ambiente non richiedono la fase di test, è opportuno che l'organizzazione prenda in considerazione l'automazione dell'intero processo per i relativi sistemi. Se ad esempio si attiva l'opzione **Aggiornamenti automatici** nel sito Web di Microsoft Windows Update, sarà possibile notificare e aggiornare i computer client senza alcun intervento da parte dell'utente. L'utilizzo di questa opzione consente di assicurarsi che sui sistemi vengano eseguiti il prima possibile gli aggiornamenti della protezione più recenti. Tuttavia, questo approccio non prevede il test dell'aggiornamento prima dell'installazione. Se la fase di test rappresenta un requisito stabilito dall'organizzazione, questa opzione non è consigliata.

È opportuno che la verifica che i sistemi dell'organizzazione siano gestiti con gli aggiornamenti di protezione più recenti diventi parte delle attività di gestione ordinarie dei sistemi aziendali.

#### Criteri basati sui rischi

Dato l'elevato numero di client, server e periferiche di rete connessi ai livelli della rete perimetrica e della rete interna del modello di difesa antivirus a più livelli, la creazione di un singolo criterio di protezione efficace per la gestione di tutti i requisiti e le configurazioni all'interno dell'organizzazione può rivelarsi difficoltosa. Un approccio che è possibile utilizzare per organizzare i criteri consiste nel raggruppare gli host dell'organizzazione in categorie in base al tipo e al livello di esposizione al rischio.

Per determinare il livello di rischio da assegnare a un host o una periferica, eseguire una verifica dei rischi per ciascuno di essi. Un insieme dettagliato di indicazioni sull'esecuzione delle verifiche dei rischi è disponibile nel "Chapter 3 - Understanding the Security Risk Management Discipline" in *Microsoft Solution for Securing Windows 2000 Server* sul sito TechNet all'indirizzo:
<http://www.microsoft.com/technet/security/prodtech/win2000/secwin2k/03secrsk.mspx> (in inglese).

Microsoft consiglia di prendere in considerazione le seguenti categorie di configurazione per i criteri di verifica dei rischi incentrati sui client dell'organizzazione:

-   **Configurazione client standard**: questa categoria di configurazione in genere è applicabile ai computer desktop aziendali che risiedono fisicamente negli uffici all'interno dell'edificio dell'organizzazione. Questi client desktop vengono costantemente protetti dalle difese delle reti interna ed esterna esistenti e all'interno degli edifici di un'organizzazione.

-   **Configurazione client ad alto rischio**: questa categoria di configurazione è progettata per soddisfare le esigenze degli utenti dei computer portatili e dei dispositivi mobili, quali PDA e telefoni cellulari. Questi dispositivi vengono in genere spostati all'esterno della protezione delle difese della rete dell'organizzazione e sono pertanto esposti a un più elevato livello di rischio.

-   **Configurazione client guest**: questa categoria di configurazione è progettata per i computer client non posseduti o supportati dall'organizzazione. Potrebbe non essere possibile eseguire la gestione della configurazione di questi computer, in quanto è improbabile che si sia in grado di esercitare controllo sulla relativa configurazione. Tuttavia, è possibile impostare criteri che limitino la capacità di questi computer di connettersi alle reti dell'organizzazione. Sono disponibili in genere i seguenti tipi di computer client guest:

    -   Computer domestici dei dipendenti.

    -   Computer dei partner o dei fornitori.

    -   Computer guest.

Microsoft consiglia inoltre di stabilire categorie di rischio per i ruoli server e di utilizzare la stessa verifica dei rischi per i server e i client. È possibile utilizzare come punto di partenza per i criteri dei server le seguenti categorie di configurazione:

-   **Configurazione server standard**: questa categoria di configurazione è progettata per fornire un livello di protezione comune per la maggior parte delle configurazioni dei server nel proprio ambiente. Sebbene fornisca un livello minimo di protezione, tuttavia non limita i servizi più comunemente utilizzati. Per soddisfare tutti i requisiti dei criteri a un livello appropriato, è possibile quindi modificare i criteri delle categorie di configurazione specifiche per i ruoli e ad alto rischio.

-   **Configurazione server ad alto rischio**: è opportuno prendere in considerazione in questa categoria di configurazione i server che risiedono sulla rete perimetrale o esposti direttamente a connessioni e file esterni. Questa categoria potrebbe comprendere ad esempio i server Web, i server firewall e i server di messaggistica perimetrali. Questa configurazione potrebbe essere garantita anche da un server che contiene dati riservati, quale un server di database per le risorse umane, indipendentemente dal relativo percorso di rete.

-   **Configurazioni specifiche per i ruoli**: è possibile inoltre che l'organizzazione scelga di suddividere specifici ruoli server in categorie di configurazione differenti per soddisfare il più possibile i requisiti delle applicazioni server. È possibile ad esempio scegliere di utilizzare le configurazioni specifiche per i ruoli per i server di messaggistica, i server di database o i firewall e decidere di utilizzare questo approccio in aggiunta alla categoria di configurazione standard o ad alto rischio, in base alle esigenze.

L'utilizzo dei criteri basati sui rischi rappresenta la scelta preferita dai team addetti alla pianificazione all'interno dell'organizzazione ed è possibile utilizzare le classificazioni delle configurazioni cui si è fatto riferimento come base per un ulteriore sviluppo. L'obiettivo finale è quello di ridurre il numero di configurazioni che i sistemi di gestione devono supportare. In generale, è più probabile che una configurazione protetta venga garantita da un approccio standardizzato anziché dall'esecuzione in modo indipendente della configurazione della protezione di ciascun host all'interno dell'ambiente in uso.

#### Criteri di segnalazione e monitoraggio automatici

Se l'organizzazione utilizza un sistema di monitoraggio automatico o un'applicazione antivirus in grado di segnalare potenziali infezioni da software dannoso alla sede centrale, sarà possibile automatizzare questo processo in modo che tutti gli utenti nell'infrastruttura IT dell'organizzazione vengano informati automaticamente mediante l'invio di avvisi. Un sistema di avviso automatico consentirà di ridurre al minimo il ritardo che intercorre tra un avviso iniziale e la notifica agli utenti del potenziale pericolo correlato a software dannoso. Tuttavia, lo svantaggio di questo approccio è dato dal fatto che può generare molti falsi allarmi. Se non si esegue lo screening degli avvisi e si esamina un elenco di controllo per il reporting di attività insolite, è probabile che gli utenti vengano avvisati dell'esistenza di software dannoso, anche nel caso in cui non sia presente. Questa situazione può dare adito a una certa autosufficienza da parte degli utenti, che saranno quindi "desensibilizzati" rispetto ad avvisi che vengono generati troppo di frequente.

Microsoft consiglia di assegnare ai membri del team di amministrazione della rete la responsabilità di ricevere tutti gli avvisi automatici relativi a software dannoso da tutti i pacchetti di applicazioni antivirus o di monitoraggio del sistema utilizzati all'interno dell'organizzazione. Il team può quindi filtrare i falsi allarmi generati dai sistemi automatici prima di inviare gli avvisi agli utenti. Per la corretta implementazione di questo approccio, è necessario che il team esegua il monitoraggio degli avvisi 24 ore al giorno, sette giorni su sette, per assicurarsi che tutti gli avvisi vengano controllati e, se necessario, inviati agli utenti della rete.

#### Consapevolezza del team addetto al supporto tecnico e degli utenti

È opportuno che le attività di formazione e la promozione della consapevolezza in tema di protezione siano rivolte particolarmente ai team addetti al supporto tecnico e all'amministrazione all'interno dell'organizzazione. La formazione dei principali professionisti IT rappresenta un requisito fondamentale in tutte le aree dell'infrastruttura IT, ma per la difesa antivirus è particolarmente importante perché la natura degli attacchi di software dannoso e delle difese potrebbe cambiare periodicamente. Un nuovo attacco di software dannoso può compromettere un sistema di difesa efficace quasi in una notte, mettendo a rischio le difese dell'organizzazione. Se al personale addetto al supporto tecnico per queste difese non viene fornita una formazione adeguata sulle modalità di individuazione e reazione a nuovi pericoli correlati a software dannoso, è solo una questione di tempo prima che si verifichi una seria violazione del sistema di difesa antivirus.

##### Consapevolezza degli utenti

La formazione degli utenti rappresenta in genere una delle ultime questioni prese in considerazione da un'organizzazione durante la progettazione di un sistema di difesa antivirus. Agevolare la comprensione da parte degli utenti di alcuni dei rischi associati agli attacchi di software dannoso è una parte importante del processo di riduzione dei rischi, in quanto tutti gli utenti nell'organizzazione che utilizzano le risorse IT svolgono un ruolo fondamentale per la protezione della rete. Per questo motivo, è importante istruire gli utenti sui rischi più comuni mitigabili con le appropriate contromisure, tra cui:

-   Apertura di allegati di posta elettronica.

-   Utilizzo di password vulnerabili.

-   Download di applicazioni e controlli ActiveX da siti Web inattendibili.

-   Esecuzioni di applicazioni da supporti rimovibili non autorizzati.

-   Autorizzazione dell'accesso ai dati e alle reti dell'organizzazione.

Poiché le tecniche di attacco del software dannoso cambiano continuamente, è necessario aggiornare regolarmente le difese antivirus. Indipendentemente dal fatto se sia necessario aggiornare il file di firma di un programma antivirus o il programma stesso, la creazione e la distribuzione degli aggiornamenti richiedono lungo tempo. Tuttavia, la quantità di tempo necessaria per creare gli aggiornamenti è stata notevolmente ridotta negli ultimi anni e, pertanto, oggi è possibile ottenere questi aggiornamenti anche nel giro di poche ore. Tuttavia, sebbene in rari casi, l'implementazione di un sistema di difesa efficace può richiedere alcuni giorni a partire dal momento in cui viene rilasciato un nuovo attacco di software dannoso.

Durante questo periodo, la difesa più efficace per un'organizzazione è rappresentata dalla consapevolezza da parte degli utenti dei pericoli correlati a software dannoso e dei relativi rischi. Fornire agli utenti le linee guida di base per la creazione di difese antivirus e una formazione adeguata può consentire di impedire a un nuovo attacco di software dannoso che riesce a superare le difese l'infrastruttura di protezione IT di propagarsi nell'ambiente in uso.

La formazione degli utenti non deve essere un processo complesso. Le linee guida antivirus di base sono in gran parte basate su principi di buon senso. Un compito arduo è invece assicurare che queste linee guida vengano applicate e comunicate in modo chiaro. Gli elenchi di controllo per la protezione di base di Windows XP disponibili sul sito Web Microsoft TechNet all'indirizzo:
[http://www.microsoft.com/technet/Security/chklist/xpcl.mspx](http://www.microsoft.com/technet/security/chklist/xpcl.mspx) (in inglese) consentono di identificare i problemi più comuni correlati alla protezione e ai programmi antivirus da comunicare agli utenti.

È probabile che gli utenti responsabili dei dispositivi mobili richiedano corsi di formazione aggiuntivi che consentano loro di comprendere i rischi associati allo spostamento di un dispositivo all'esterno delle difese a livello fisico e di rete dell'organizzazione. È possibile che siano necessarie difese aggiuntive mirate specificamente a proteggere questi dispositivi mobili. Per questo motivo, potrebbe essere necessario richiedere configurazioni e corsi di formazione aggiuntivi per gli utenti che gestiscono questi dispositivi.

**Nota**: alcune utili informazioni sulla configurazione per gli utenti finali sono disponibili nella Guida [Proteggi il tuo PC](http://www.microsoft.com/security/protect/default.asp) sul sito Web Microsoft.com all'indirizzo:
www.microsoft.com/italy/security/protect/. Questo sito rappresenta una valida fonte di informazioni in grado di fornire agli utenti le istruzioni appropriate sulla modalità di protezione dei relativi computer domestici e reti.

##### Consapevolezza del team addetto al supporto tecnico

È necessario fornire ai professionisti IT responsabili della configurazione e dell'assistenza a server, client e periferiche di rete dell'organizzazione una formazione antivirus che consenta loro di assicurarsi che i relativi sistemi siano configurati e gestiti in modo ottimale per evitare attacchi di software dannoso. Eventuali errori nella configurazione di uno di questi computer o periferiche possono comportare l'apertura di una route per un attacco di software dannoso. Se ad esempio un amministratore di firewall non adeguatamente qualificato apre tutte le porte della rete su un dispositivo firewall perimetrale, potrebbero essere introdotti seri rischi di protezione correlati a software dannoso. È opportuno che gli amministratori responsabili dei dispositivi che si connettono alla rete perimetrale dell'organizzazione ricevano una formazione specifica in materia di protezione che consenta loro di comprendere la serie di attacchi che possono avere un notevole impatto sulle periferiche di rete.

Microsoft mette a disposizione molti eventi, laboratori pratici e webcast su argomenti relativi alla protezione. Per ulteriori informazioni su questi argomenti, vedere Your Security Program Guide sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/seminar/events/security.mspx> (in inglese).

Libri e corsi di formazione sulla protezione sono inoltre resi disponibili da Microsoft Learning. Per ulteriori informazioni su queste pubblicazioni, vedere la pagina Microsoft Learning Security Resources sul sito Web Microsoft.com all'indirizzo:
<http://www.microsoft.com/learning/centers/security.asp> (in inglese).

##### Commenti e suggerimenti degli utenti

Gli utenti consapevoli di potenziali attacchi di software dannoso potranno fornire un eccellente sistema di avviso anticipato nel caso in cui dispongano di un meccanismo semplice ed efficace per segnalare comportamenti anomali dei sistemi che utilizzano. Tale meccanismo può essere rappresentato da un numero verde, alias di posta elettronica o un rapido processo di escalation reso disponibile dal servizio di supporto tecnico dell'organizzazione.

##### Comunicazioni interne proattive

Se possibile, è opportuno che i membri del reparto IT creino un team di risposta antivirus proattivo che sia responsabile per il monitoraggio di siti di avviso esterni in modo che possano ricevere avvisi anticipati di eventuali attacchi di software dannoso. Di seguito sono riportati alcuni esempi di tali siti:

-   Siti Web di fornitori di applicazioni antivirus.

-   Sito Web Anti-Virus Information Exchange Network (AVIEN) all'indirizzo: [www.avien.org](http://www.avien.org/) (in inglese).

-   Servizi di avviso antivirus, tra cui il servizio Antivirus Information Early Warning System (AVI-EWS) fornito da AVIEN (è possibile effettuare la sottoscrizione a questi servizi).

-   Sito Web Microsoft Security Antivirus Information su Microsoft.com all'indirizzo: <http://www.microsoft.com/security/antivirus/> (in inglese).

Il controllo regolare di questi siti dovrebbe consentire al personale addetto al supporto tecnico di avvisare gli amministratori di sistema e gli utenti dei pericoli correnti correlati a software dannosi prima che questi penetrino nella rete dell'organizzazione. La tempistica di questi controlli riveste un'importanza cruciale. Assicurare che gli utenti del sistema ricevano un avviso proattivo prima di eseguire il controllo mattutino della relativa posta elettronica può fare la differenza tra la gestione della rimozione di alcuni messaggi sospetti e il tentativo di limitare i danni provocati da una violazione di software dannoso. Se la maggior parte degli utenti del sistema si connette alle 9.00, è consigliabile stabilire un metodo per comunicare nuovi pericoli correlati a software dannoso prima di questa ora.

##### Avvisi di attacchi di software dannoso interni

La ricerca del meccanismo più efficace per informare tutti gli utenti di un potenziale attacco di software dannoso in modo tempestivo ed esaustivo è cruciale. I sistemi di comunicazione disponibili variano notevolmente a seconda dell'infrastruttura dell'organizzazione ed è impossibile fornire un sistema di avviso di software dannoso adatto per tutte le organizzazioni. Tuttavia, in questa sezione sono riportati alcuni esempi di meccanismi di avviso che è opportuno che ogni organizzazione prenda in considerazione:

-   **Bacheche**: un approccio semplice, da non dimenticare, consiste nell'utilizzo delle porte interne degli uffici, di bacheche o di punti di informazioni su documenti cartacei, tutti strumenti ovvi per i dipendenti. Sebbene questo processo imponga un certo sovraccarico, offre il vantaggio significativo di comunicare informazioni fondamentali agli utenti quando alcune aree della rete non sono disponibili a causa di un attacco.

-   **Sistemi di posta vocale**: se consentito dal sistema di posta vocale dell'organizzazione, la possibilità di lasciare un singolo messaggio per tutti gli utenti può rivelarsi un efficace meccanismo di comunicazione di potenziali attacchi di software dannoso. Tuttavia, è bene tenere presente che questo metodo, per avvisare gli utenti di un pericolo potenziale correlato alla posta elettronica, prevede che gli utenti accedano alla posta vocale prima di accedere alla posta elettronica.

-   **Messaggi di accesso**: è possibile configurare il sistema operativo Windows per l'invio di un messaggio direttamente alle schermate degli utenti durante il processo di accesso. Questo meccanismo risulta molto utile per attirare l'attenzione degli utenti sugli avvisi di potenziali attacchi di software dannoso.

-   **Portali di rete Intranet**: per fornire avvisi relativi a potenziali attacchi di software dannoso, è possibile utilizzare un comune portale di rete Intranet che gli utenti hanno impostato come relativa home page. Perché questo meccanismo di avviso sia efficace, è necessario che gli utenti visualizzino questo portale prima di accedere alla posta elettronica.

-   **Sistemi di posta elettronica**: è necessario prestare particolare attenzione quando si utilizza un sistema di posta elettronica per comunicare avvisi di attacchi di software dannoso agli utenti. Poiché un attacco è in grado di influire sui server di posta elettronica, questo meccanismo potrebbe non essere efficace in tutti i casi. Inoltre, a causa della natura del processo di accodamento dei messaggi nella cartella Posta in arrivo, è possibile che un avviso di attacco di software dannoso venga inviato dopo che gli utenti abbiano già ricevuto un messaggio di posta elettronica contenente software dannoso. Per questo motivo, potrebbe essere necessario avvisare gli utenti della necessità di verificare la presenza di eventuali avvisi ad alta priorità relativi a software dannoso prima di esaminare i messaggi di posta elettronica.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

Ormai, la difesa antivirus non implica più l'installazione di un'applicazione. Gli attacchi di software dannoso più recenti hanno dimostrato che è necessario un approccio difensivo più completo. In questo capitolo è stata esaminata la modalità di applicazione di un modello di protezione in profondità che costituisca la base di un approccio di difesa a più livelli per creare una soluzione antivirus efficace per la propria organizzazione. È importante comprendere che gli autori di software dannoso aggiornano continuamente i metodi utilizzati per attaccare le nuove tecnologie IT eventualmente utilizzate all'interno delle organizzazioni e che le tecnologie antivirus si evolvono continuamente al fine di limitare questi nuovi pericoli.

È necessario che l'approccio di difesa antivirus a più livelli assicuri che l'infrastruttura IT sia in grado di gestire tutti i possibili vettori di attacco di software dannoso. L'utilizzo di questo approccio a livelli consente di semplificare il riconoscimento di eventuali punti deboli nell'intero sistema, dalla rete perimetrale ai singoli utenti che utilizzano i computer all'interno dell'organizzazione. L'incapacità di gestire i livelli descritti nell'approccio di difesa antivirus a più livelli potrebbe lasciare il sistema esposto a potenziali attacchi.

È consigliabile esaminare costantemente la soluzione antivirus in modo che sia possibile aggiornarla quando necessario. Tutti gli aspetti della protezione sono importanti, dal semplice download automatico delle definizioni dei virus alle modifiche globali apportate ai criteri operativi.

Analogamente, poiché le informazioni fornite in questa guida sono soggette ad aggiornamenti, per ricevere le ultime informazioni e indicazioni relative alle soluzioni antivirus, è importante monitorare continuamente il sito Web Microsoft Security Antivirus Information su Microsoft.com all'indirizzo <http://www.microsoft.com/security/antivirus/> (in inglese).

Microsoft riconosce quanto pericolosi e costosi possano essere i software dannosi e ha compiuto uno sforzo significativo per rendere più difficili la creazione e la distribuzione di software di questo tipo. Microsoft si sta attivando inoltre per semplificare la configurazione dei sistemi da parte dei progettisti di rete, dei professionisti IT e degli utenti finali al fine di soddisfare i relativi requisiti di protezione con un impatto minimo sulle attività aziendali.

Sebbene non sia possibile sradicare completamente il codice dannoso, una costante attenzione alle aree evidenziate in questo approccio di difesa antivirus a più livelli consentirà di ridurre al minimo gli effetti che un attacco di software dannoso può avere sull'operatività dell'organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)
