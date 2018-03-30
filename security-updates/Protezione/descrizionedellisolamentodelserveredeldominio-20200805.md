---
TOCTitle: 'Descrizione dell''isolamento del server e del dominio'
Title: 'Descrizione dell''isolamento del server e del dominio'
ms:assetid: '2b2b2fd4-fd10-4d3e-a5a1-24ae9569e106'
ms:contentKeyID: 20200805
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536205(v=TechNet.10)'
---

Isolamento del server e del dominio tramite IPsec e criteri di gruppo
=====================================================================

### Capitolo 2: Descrizione dell'isolamento del server e del dominio

Aggiornato: 16 febbraio 2005

Dopo l'affermazione delle reti LAN, i professionisti IT sono stati impegnati nella realizzazione di servizi flessibili e ad elevata disponibilità che consentissero al contempo di mantenere un livello di protezione adeguato. Sono state introdotte diverse tecnologie da associare al protocollo TCP/IP al fine di assicurare una protezione efficace per la rete e a livello di trasporto. Tali tecnologie includono: IPv6, 802.1X, switch di rete, segmentazione LAN virtuale (VLAN), IPSec (Internet Protocol Security), per citarne solo alcune.

Il risultato indiretto dell'introduzione di queste tecnologie è un approccio su più livelli alla protezione di rete. Tali livelli possono venire utilizzati per separare, segmentare o *isolare*** **uno o più host o reti da altri host o reti. L'obiettivo di questo capitolo è organizzare il livello di protezione offerto da IPSec in relazione agli altri livelli, illustrandone le modalità di utilizzo in associazione ai criteri di gruppo nell'ambito di una soluzione che assicuri un isolamento gestibile e scalabile a livello dell'intera azienda.

##### In questa pagina

[](#ejaa)[Prima di iniziare](#ejaa)
[](#eiaa)[Destinatari di questo capitolo](#eiaa)
[](#ehaa)[Requisiti aziendali](#ehaa)
[](#egaa)[Identificazione dei computer attendibili](#egaa)
[](#efaa)[Combinazione dell'isolamento di server e domini con la strategia globale di protezione della rete](#efaa)
[](#eeaa)[Terminologia utilizzata](#eeaa)
[](#edaa)[Realizzazione dell'isolamento di server e domini](#edaa)
[](#ecaa)[Da cosa protegge l'isolamento di server e domini?](#ecaa)
[](#ebaa)[Distribuzione dell'isolamento di server e domini](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Prima di iniziare

Prima di utilizzare le informazioni fornite in questo capitolo, è necessaria una perfetta conoscenza dei concetti e delle tecnologie seguenti. Sebbene i contenuti della guida possano risultare utili anche agli utenti che non possiedono tali requisiti, è più probabile riuscire a pervenire a un'implementazione ottimale se si è in possesso dei prerequisiti indicati di seguito.

#### Prima di iniziare

È inoltre necessaria la conoscenza delle seguenti aree di Microsoft® Windows Server™ 2003:

-   Concetti relativi al servizio di directory Active Directory® (inclusi la struttura e gli strumenti di Active Directory, la gestione di utenti, gruppi e altri oggetti Active Directory e l’utilizzo dei criteri di gruppo).

-   Concetti di autenticazione, incluso l'utilizzo del protocollo Kerberos versione 5 e dell'infrastruttura a chiave pubblica (PKI, Public Key Infrastructure).

-   Concetti di protezione del sistema operativo Microsoft Windows®, quali utenti, gruppi, controllo, elenchi di controllo di accesso (ACL), utilizzo dei modelli di protezione, concetti di autenticazione reciproca, concetti e metodi di risoluzione dei nomi quali DNS (Domain Name System) e WINS (Windows Internet Naming Service), strumenti di diagnosi e concetti di risoluzione dei problemi standard di Windows, utilizzo dei criteri di gruppo o degli strumenti della riga di comando per applicare modelli di protezione.

-   Conoscenza dei concetti TCP/IP, inclusi la disposizione della subnet, la configurazione della network mask e il routing. Conoscenza di funzionalità e protocolli di basso livello, inclusa la relativa terminologia, quali i protocolli ICMP (Internet Control Message Protocol) e ARP (Address Resolution Protocol) e l'unità massima di trasmissione (MTU, Maximum Transmission Unit).

-   Conoscenza dei principi di gestione dei rischi di protezione.

    **Nota:** nel capitolo 6, "Deploying IPSec", del *Windows Server 2003 Deployment Kit* vengono illustrati alcuni scenari relativi alla modalità di trasporto IPSec che al momento della redazione del documento non erano ritenuti consigliabili. Tuttavia, a seguito delle attività di distribuzione interna di IPSec svolte da Microsoft e in ragione della disponibilità di istruzioni supplementari, tale raccomandazione non è più valida.
    Mentre rimane impossibile utilizzare IPSec per il traffico multicast e broadcast, è possibile proteggere tutti i tipi di traffico IP unicast mediante IPSec. Ogni cliente deve valutare i vantaggi della distribuzione di IPSec in uno scenario di isolamento di domini o server considerando fattori quali i costi, l'impatto e altre implicazioni legate a questa scelta. Tuttavia, oggi Microsoft consiglia e supporta un più ampio utilizzo di IPSec nelle reti dei clienti come indicato in questa guida.

#### Prerequisiti organizzativi

È improbabile che la pianificazione dell'ambiente di protezione di un'organizzazione venga affidata a un solo individuo. Le informazioni richieste per determinare gli esatti requisiti di un'organizzazione provengono infatti da numerose fonti interne. Ci si deve inoltre consultare con altre persone dell'organizzazione che possono avere necessità di partecipare alla pianificazione dell'isolamento, incluse le seguenti figure:

-   Finanziatori

-   Rappresentanti dei gruppi di utenti

-   Personale addetto alla protezione e al controllo

-   Gruppo per la gestione dei rischi

-   Personale addetto alla progettazione, amministrazione e gestione di Active Directory

-   Personale addetto alla progettazione, amministrazione e gestione di DNS, server Web e della rete.

    **Nota**: a seconda della struttura dell'organizzazione IT, ognuno di questi ruoli può essere occupato da una persona diversa oppure la stessa persona può rivestire più ruoli.

L'ambito di un progetto di isolamento di server e domini richiede l'esistenza di un team globale con conoscenze approfondite dei requisiti aziendali, dei problemi tecnici, dell'impatto sugli utenti e dell'intero processo a livello di progetto. Spesso può rivelarsi utile affidare a un individuo influente il ruolo di punto di contatto principale nell'ambito del progetto, con l'incarico di ottenere gli input necessari, ad esempio dal personale del supporto o dagli utenti interessati dalla distribuzione. Le due principali cause dell'insuccesso di un progetto complesso sono una pianificazione inadeguata e comunicazioni insufficienti. Il team del progetto deve essere al corrente di questi rischi potenziali e adottare tutte le misure necessarie per la loro riduzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Destinatari di questo capitolo

Questo capitolo è rivolto ai responsabili dei processi decisionali a livello tecnico e agli architetti tecnici che verranno incaricati della progettazione di una soluzione aziendale di isolamento dei server e dei domini personalizzata. Al fine di ottenere i massimi vantaggi dai contenuti presentati in questo capitolo, è necessario possedere conoscenze tecniche di entrambe le tecnologie richieste, nonché dell'attuale infrastruttura dell'organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Requisiti aziendali

È importante tenere presente che la soluzione risultante viene determinata dai requisiti aziendali dell'organizzazione. Per isolamento si intende la separazione logica o fisica di uno o più computer dalla comunicazione di rete con altri computer. L'implementazione di restrizioni di protezione esercita necessariamente un impatto sulle operazioni svolte quotidianamente dai dipendenti di un'organizzazione. Le modifiche introdotte nell'ambito della soluzione alterano il modo in cui i computer del dominio comunicano tra loro e con i computer considerati non attendibili. Ai fini dell'adozione di questa soluzione, è necessario che il team del progetto dedichi tempo alla pianificazione e allo studio della fattibilità; è, inoltre, necessario provvedere alla formazione del personale del supporto IT e, come minimo, all'elaborazione di un programma di base di sensibilizzazione del personale. Gli ulteriori servizi di protezione previsti per il traffico di rete possono richiedere, in alcuni casi, la disponibilità di memoria del server aggiuntiva o altre schede di accelerazione hardware di rete. Possono inoltre essere disponibili soluzioni diverse che consentono di raggiungere obiettivi di isolamento identici o analoghi. È pertanto importante stimare il valore economico che l'azienda intende realizzare con l'adozione della soluzione.

#### Conformità alle normative

Con l'aumento delle informazioni personali archiviate nei sistemi informatici, l'attenzione posta sulla riservatezza dei dati è anch'essa aumentata. Il controllo dell'accesso alle informazioni dei clienti e dei dipendenti non rappresenta più solo una buona prassi aziendale. Un'organizzazione che non è in grado di garantire meccanismi di controllo adeguati è soggetta a significative responsabilità legali e finanziarie, a seconda delle leggi locali dei diversi paesi. Le organizzazioni operanti negli Stati Uniti potrebbero dover soddisfare i requisiti di uno dei seguenti standard normativi:

-   Federal Information Security Management Act (FISMA)

-   Sarbanes-Oxley Public Company Accounting Reform and Investor Protection Act

-   Gramm-Leach-Bliley Financial Services Modernization Act

-   Health Insurance Portability and Accountability Act (HIPAA)

Quest'ultimo standard contiene una regola di protezione che impone il rispetto di rigorose linee guida in merito alla modalità di gestione dei dati sanitari personali in formato elettronico (ePHI) da parte delle organizzazioni operanti nel settore sanitario. Sebbene lo standard normativo HIPAA non prescriva o raccomandi una tecnologia specifica, indica tuttavia le caratteristiche richieste ai fini della conformità e le modalità di riduzione dei rischi per i dati ePHI. È opportuno valutare l'utilizzo della protezione IPSec congiuntamente con l'isolamento dei domini o dei server al fine di assicurare la conformità tecnica alle seguenti sezioni dello standard HIPAA:

-   Access control 164.312(a)(1): proteggere l'accesso di rete in ingresso ai computer attendibili mediante autorizzazioni dei criteri di gruppo e proteggere mediante crittografia i dati ePHI dall'immissione non autorizzata nel traffico di rete.

-   Audit controls 164.312(b): controllare quali computer sono in comunicazione tra loro.

-   Integrity 164.312(c)(1): limitare l'accesso di rete in ingresso ai computer contenenti dati ePHI a un gruppo specifico di computer e utenti autorizzati e considerati attendibili. Prevenire inoltre l'alterazione dei dati ePHI durante la trasmissione di rete assicurando l'integrità e l'autenticità di tutti i pacchetti di rete per le connessioni delle applicazioni.

-   Person or entity authentication 164.312(d): richiedere l'autenticazione e l'autorizzazione dei computer attendibili per l'accesso di rete in ingresso ad altri computer attendibili.

-   Transmission security 164.312(e)(1): assicurare l'autenticità, l'integrità e la crittografia delle trasmissioni.

Questi requisiti vengono spesso soddisfatti utilizzando SSL (Secure Sockets Layer) e TLS (Transport Layer Security). L'utilizzo della tecnologia Microsoft .NET con SSL/TLS consente, ad esempio, di assicurare la conformità delle applicazioni ai requisiti di protezione previsti dalla normativa HIPAA. Per ulteriori informazioni, vedere il white paper "[Healthcare Without Boundaries: Integration
Technology for the New Healthcare Economy](http://www.microsoft.com/resources/healthcare/healthcareeconomy.aspx)" all'indirizzo www.microsoft.com/Resources/Healthcare/
HealthcareEconomy.aspx.

È tuttavia necessario integrare in modo appropriato l'utilizzo di SSL/TLS e gli algoritmi di controllo alle comunicazioni delle applicazioni. I principali vantaggi offerti da una soluzione di isolamento IPSec sono la protezione di tutte le applicazioni e del sistema operativo del computer host, nonché la protezione del traffico di rete per tutte le applicazioni esistenti, senza necessità di apportare modifiche a queste ultime. Per ulteriori dettagli, vedere la sezione "Confronto tra SSL/TLS e IPSec" più avanti in questo capitolo.

##### Conformità della soluzione con le normative del governo degli Stati Uniti

Il 16 dicembre 2003, l'Office of Management and Budget (OMB) degli Stati Uniti ha pubblicato un memorandum intitolato "[E-Authentication Guidance for Federal Agencies](http://www.whitehouse.gov/omb/memoranda/fy04/m04-04.pdf)", disponibile per il download all'indirizzo http://www.whitehouse.gov/omb/memoranda/fy04/
m04-04.pdf. In questo documento si indica che il livello di rischio di una violazione dell'autenticazione corrisponde al livello a cui è richiesta l'autenticazione elettronica (e-authentication).

La pubblicazione speciale 800-63 del National Institute for Standards and Technology (NIST) "Electronic Authentication Guideline: Recommendations of the National Institute of Standards and Technology" identifica i requisiti tecnici dei livelli di autenticazione da 1 a 4. In molti casi, i livelli di autenticazione utente più elevati (3 e 4) richiedono la riscrittura o la sostituzione delle applicazioni. Se i livelli di autenticazione consentono di ridurre i rischi di protezione complessivi, è possibile utilizzare un livello di autenticazione utente meno costoso per l'accesso alle informazioni molto riservate. Nella piattaforma Windows, le soluzioni di isolamento dei server e dei domini consentono di aggiungere un livello iniziale di autenticazione dei computer attendibili, controllo degli accessi, autenticazione del traffico di rete e crittografia prima dell'autenticazione utente al livello dell'applicazione. L'adozione di una soluzione di isolamento dei server e dei domini può ridurre o ritardare la necessità di modificare le applicazioni e agevolare la conformità con le prescrizioni in materia di gestione dei rischi.

Per assicurare la conformità con le normative relative ai prodotti di Information Assurance, Microsoft mette in atto una serie di processi di certificazione. Windows 2000 ha ottenuto la certificazione di conformità con il livello di certificazione 4 (EAL4) e con i requisiti della sezione "ALC\_FLR.3 Systematic Flaw Remediation" dello standard ISO 15408 "Common Criteria for Information Technology Security Evaluation (CCITSE)" . Tale certificazione è valida sia per i sistemi operativi che per la protezione dei dati sensibili.

**Nota**: al momento della stesura di questa guida, era in corso la certificazione di entrambe le piattaforme Windows XP e Windows Server 2003.

È stata inoltre ottenuta la certificazione di conformità con FIPS 140-1 dei componenti di crittografia IPSec di Windows 2000, Windows XP e Windows Server 2003. Le soluzioni di isolamento dei server e dei domini possono pertanto venire utilizzate negli ambienti IT di forze dell'ordine ed enti pubblici. Per ulteriori informazioni, vedere i documenti ai collegamenti seguenti:

-   [Overview: Windows 2000 Common Criteria Certification](http://www.microsoft.com/technet/security/prodtech/windows2000/w2kccwp.mspx), all'indirizzo www.microsoft.com/technet/security/prodtech/Windows2000/
    w2kccwp.mspx

-   [FIPS 140 Evaluation](http://www.microsoft.com/technet/archive/security/topics/issues/fipseval.mspx), all'indirizzo www.microsoft.com/technet/archive/security/topics/
    issues/fipseval.mspx

Le informazioni contenute in questa sezione sono rivolte specificamente alle organizzazioni che operano negli Stati Uniti. Tuttavia, numerosi paesi del mondo stanno introducendo regolamentazioni e legislazioni analoghe, ad esempio la Direttiva del 1998 sulla protezione dei dati personali dell'Unione Europea e il "Personal Information Protection and Electronic Documents Act (PIPEDA)" del Canada, che impongono il rispetto di rigorose linee guida concernenti la gestione dell'identità e la riservatezza dei dati.

#### Verifica dei rischi aziendali dell'infrastruttura IT

Lo scopo della verifica dei rischi aziendali è evidenziare in che modo l'azienda dipende dalla sua infrastruttura IT. L'attività di verifica dei rischi di protezione IT deve individuare i rischi e determinarne le priorità a livello di integrità delle informazioni e stabilità dei servizi. Mediante la verifica dei rischi di protezione, si deve pervenire a una chiara giustificazione dei motivi per cui è opportuno gestire tali rischi e alla stima dei costi in cui si incorrerebbe se i rischi non venissero affrontati. L'attività di stima dei costi è particolarmente importante nell'ambito della valutazione delle diverse soluzioni tecniche disponibili per affrontare i singoli problemi. Poiché nessuna soluzione è in grado di affrontare da sola tutti i rischi esistenti, è importante confrontare tra loro le varie soluzioni e i relativi costi.

I responsabili dei processi decisionali potranno inoltre valutare il costo di una soluzione di isolamento in termini di come contribuisce a ridurre il rischio di prestazioni inferiori o perdita di servizio conseguenti alla propagazione di virus e worm all'interno della rete aziendale. I motivi di preoccupazione principali di alcune organizzazioni sono l'impatto aziendale e i costi di un attacco da parte di un pirata informatico ai dati aziendali ad alto valore.

**Nota**: in alcuni paesi e regioni, la legge obbliga a comunicare agli utenti che potrebbero aver subito danni i casi di avvenute violazioni della protezione. Rivolgersi all'ente pubblico competente in materia o al proprio consulente legale per informazioni sulle normative specifiche vigenti nel paese in cui opera l'organizzazione.

Le categorie seguenti vanno intese come guida di riferimento per la stima del costo totale del problema di protezione:

-   **Costi sostenuti per la perdita di servizio**. Al fine di determinare il costo totale dovuto alla perdita di servizio di un server di rete, sommare i seguenti costi individuali:

    -   Tempo dedicato alla risposta al problema da parte del personale del supporto

    -   Perdita di ricavi dovuta all'interruzione del servizio dell'applicazione

    -   Perdita di produttività interna

-   **Costi sostenuti per il furto di informazioni**. Al fine di determinare il costo totale dovuto al furto delle informazioni da un server di rete interno, sommare i seguenti costi individuali:

    -   Perdita della proprietà intellettuale richiesta per lo sviluppo delle informazioni

    -   Perdita di ricavi futuri per tutti i prodotti a causa della pubblicità negativa presso i clienti, in caso di divulgazione della notizia del furto

    -   Perdita di valore di mercato a causa della pubblicità negativa presso gli investitori, in caso di divulgazione della notizia del furto

    -   Tempo dedicato alla risposta al problema da parte del personale addetto al marketing e allo sviluppo

    -   Perdita di opportunità di ricavi a causa dell'impegno richiesto sul fronte interno per rispondere al problema

    -   Tempo richiesto per la riduzione degli effetti dell'utilizzo illecito delle informazioni ai danni dell'azienda, dei dipendenti o dei clienti

-   **Costi sostenuti per la violazione delle credenziali di amministratore su un server**. Al fine di determinare il costo totale dovuto alla violazione delle credenziali di amministratore su un server, sommare i seguenti costi individuali:

    -   Impegno richiesto sul fronte interno per rispondere all'attacco e sostituire il server

    -   Riduzione dei rischi di attacco ad altri computer come conseguenza della violazione delle credenziali di amministratore sul server

-   **Costi sostenuti per le conseguenti azioni legali o pratiche amministrative**. Al fine di determinare il costo totale dovuto alle azioni legali richieste a seguito di un attacco, sommare i seguenti costi individuali:

    -   Costo dell'azione legale se il pirata informatico viene identificato, ma l'azienda perde la causa

    -   Costo dell'azione legale se il pirata informatico viene identificato e l'azienda vince la causa, ma il colpevole non è in grado di pagare le spese stabilite dal tribunale

    -   Costi sostenuti per imporre multe, effettuare controlli, limitare la divulgazione e altre contromisure intraprese in buona fede al fine di riportare l'ambiente aziendale allo stato attuale

#### Investimento nell'orientamento a lungo termine per la protezione delle informazioni

L'iniziativa NAP (Network Access Protection) di Microsoft definisce l'orientamento a lungo termine necessario per il rigoroso controllo di conformità delle periferiche connesse tra di loro e alla rete. La messa in quarantena dell'accesso remoto e l'isolamento dei server e dei domini sono due aspetti di tale orientamento che è possibile implementare per gli attuali sistemi Windows 2000 e per le piattaforme future. La combinazione di funzionalità di isolamento sia perimetrale che interno consente alle organizzazioni di proteggersi efficacemente dalla diffusione di virus e da altri tipi di attacchi provenienti da computer considerati non attendibili o attuati utilizzando credenziali utente violate.

Per ulteriori informazioni sull'iniziativa NAP, vedere il sito Web [Network Access Protection](http://www.microsoft.com/windowsserver2003/technologies/networking/nap/default.mspx) all'indirizzo www.microsoft.com/nap.

Per ulteriori informazioni sul controllo delle reti private virtuali (VPN, Virtual Private Network) e per la quarantena dell'accesso, vedere il sito Web [Virtual Private Networks for Windows Server 2003](http://www.microsoft.com/windowsserver2003/technologies/networking/vpn/default.mspx) all'indirizzo www.microsoft.com/vpn.

Nelle future versioni di Windows verranno inclusi strumenti di protezione dell'accesso di rete più completi e gestibili. Per ulteriori informazioni, vedere il white paper "[Introduction to Network Access Protection](http://www.microsoft.com/windowsserver2003/techinfo/overview/napoverview.mspx)", all'indirizzo www.microsoft.com/windowsserver2003/techinfo/
overview/napoverview.mspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Identificazione dei computer attendibili

La discussione del concetto di attendibilità, in particolare in riferimento ai computer, è un aspetto importante dell'isolamento dei server e dei domini. L'isolamento è essenzialmente la capacità da parte di uno specifico host ritenuto attendibile di decidere chi può accedervi a livello di rete. Pertanto, indipentemente dalle modalità di connessione dei computer remoti all'estremità remota della connessione (ad esempio tramite rete senza fili, LAN o Internet), un computer remoto può utilizzare il protocollo IPSec per negoziare l'attendibilità e proteggere il traffico TCP/IP end-to-end con il computer di destinazione. A differenza di altri controlli dell'accesso di rete e tecnologie di protezione basati sui collegamenti (ad esempio VPN, 802.1x, WEP 802.11), questo modello di protezione end-to-end assicura un elevato livello di protezione delle comunicazioni di rete. L'attendibilità del computer remoto è particolarmente importante per assicurare la protezione in caso di furto, violazione o utilizzo non appropriato di credenziali.

Ai fini di questa guida, per *attendibilità o trust* si intende la capacità di un'organizzazione di ottenere assicurazioni sufficienti che un determinato computer si trova in uno stato noto e soddisfa i requisiti minimi di protezione stabiliti dall'organizzazione. Tali requisiti possono essere di natura tecnica, aziendale, di protezione o una qualsiasi combinazione di questi aspetti e determinano lo stato in cui un computer si deve trovare prima di stabilire una comunicazione con altri computer. Microsoft consiglia di includere nelle specifiche per i computer attendibili un elenco aggiornato di aggiornamenti per la protezione e service pack che è necessario installare. Idealmente, tali aggiornamenti dovrebbero essere gestiti e applicati mediante un sistema di gestione delle patch, come il servizio Windows Update oppure Microsoft Systems Management Server (SMS). La frequenza dell'installazione degli aggiornamenti varia in funzione del tempo necessario per testare e distribuire i singoli aggiornamenti all'interno dell'organizzazione. Tuttavia, per una protezione ottimale si consiglia di applicare gli aggiornamenti nell'intero ambiente non appena possibile.

I computer considerati non attendibili sono quelli per i quali non è possibile garantire che i requisiti di protezione siano soddisfatti. In generale, un computer viene considerato non attendibile se non è gestito o protetto.

L'obiettivo della soluzione di isolamento dei server e dei domini è ridurre i rischi per le risorse attendibili, implementando strumenti, tecnologie e processi in grado di proteggere i beni dell'organizzazione. La soluzione permette di garantire che:

-   Solo i computer attendibili (ovvero i computer che soddisfano requisiti specifici di protezione) potranno accedere alle risorse considerate attendibili.

-   I computer considerati non attendibili non potranno accedere alle risorse attendibili a meno che il rischio non sia giustificato da una specifica motivazione aziendale.

Per impostazione predefinita, alle risorse attendibili dovrebbe essere consentito l'accesso al livello di rete unicamente da parte di altre risorse attendibili. È inoltre necessario controllare l'accesso al livello di rete mediante autorizzazioni di tipo Autorizza o Nega e ACL per i singoli utenti e computer dell'ambiente considerato attendibile.

La creazione di questo ambiente di trust e la limitazione delle comunicazioni autorizzate all'interno e all'esterno dell'ambiente consentono di ridurre il rischio globale per i dati aziendali. La soluzione può inoltre offrire alle aziende ulteriori vantaggi, quali:

-   Una conoscenza approfondita del flusso di dati tra aree specifiche della rete.

-   Il miglioramento dei programmi di protezione utilizzati per ottenere lo stato di trust.

-   La creazione di un inventario delle periferiche host e di rete aggiornate.

Ad esempio, nello scenario della Woodgrove Bank, sono attendibili tutti i computer che eseguono Windows 2000 Service Pack (SP) 4, Windows XP SP2 o versioni successive e Windows Server 2003 o versioni successive in tutti i domini che la Woodgrove possiede e gestisce. Le risorse attendibili, che includono tutti i computer che eseguono Windows 2000 o versioni successive con la protezione attuata tramite i criteri di gruppo, vengono sottoposte a controlli periodici da parte del personale IT per verificare il mantenimento continuo dei requisiti minimi di protezione. Il reparto IT verifica inoltre le risorse attendibili per garantire che l'installazione e la configurazione di software di protezione specifici (ad esempio il software antivirus) siano controllate a livello centrale in base ai requisiti di protezione esistenti della Woodgrove. Per ulteriori informazioni su quali computer vengono considerati attendibili nel contesto della soluzione, vedere la sezione "Determinazione dell'attendibilità" del capitolo 3, "Determinazione dello stato corrente dell'infrastruttura IT", della presente guida.

#### Computer non gestiti

I computer non gestiti sono computer per i quali le impostazioni di protezione non vengono controllate a livello centrale oppure che non assicurano le capacità di gestione della protezione richieste. I computer non gestiti vengono considerati non attendibili perché non è possibile avere la certezza che rispettino i requisiti previsti per i computer attendibili a cui tentano di accedere.

#### Computer non protetti

I computer non protetti sono computer che eseguono sistemi operativi che non sono stati o non possono venire configurati per assicurare il livello di protezione richiesto. I computer non protetti possono rientrare in una delle quattro categorie seguenti:

-   **Basso livello di protezione del sistema operativo**. Appartengono a questa categoria i computer che eseguono un sistema operativo privo del livello di protezione dell'infrastruttura richiesto, ad esempio Windows 9*x*, Microsoft Windows NT® e Windows CE. In genere le funzioni dell'infrastruttura di protezione richieste sono presenti nei sistemi operativi più recenti, quali Windows XP e Windows Server 2003. Tali funzionalità includono i controlli degli accessi (ad esempio le autorizzazioni per i file), le funzioni di protezione di rete della crittografia dei pacchetti, l'autenticazione e l'autorizzazione avanzata, livelli di privilegio diversi (utente e amministratore), il supporto della gestione centralizzata delle impostazioni di protezione, funzioni che garantiscono la riservatezza e l'integrità dei dati e il supporto di altre tecnologie di protezione (quali il protocollo di autenticazione Kerberos e i Servizi certificati).

-   **Configurazione** **errata**. Anche i sistemi operativi più sicuri possono risultare vulnerabili agli attacchi se non sono stati configurati correttamente. Tali computer vengono pertanto considerati periferiche non protette.

-   **Livello di aggiornamento inadeguato**. Poiché la protezione IT è un'area in continua evoluzione, la maggior parte dei fornitori di software pubblicano aggiornamenti che risolvono le vulnerabilità scoperte più di recente. L'organizzazione può stabilire il livello minimo degli aggiornamenti che devono essere installati in un computer host perché possa essere considerato attendibile. Di conseguenza, tutti i computer ai quali non sono stati applicati gli aggiornamenti richiesti vengono considerati periferiche non protette.

-   **Computer attendibili che potrebbero essere stati oggetto di violazione**. È possibile che un computer attendibile sia stato violato, in genere da parte di un pirata informatico anch'esso considerato attendibile. Dopo che il computer attendibile è stato violato, non viene più considerato attendibile fino all'adozione di specifiche contromisure che lo riportino allo stato di trust. È importante tener presente che se l'utente di un computer viene ritenuto non attendibile, anche il computer non sarà attendibile.

Le periferiche che è possibile ricondurre a una di queste quattro categorie vengono classificate come non attendibili perché l'organizzazione non può avere la certezza che non abbiano subito una qualche forma di violazione. Queste periferiche rappresentano pertanto un rischio significativo per tutti i computer attendibili a cui tentano di accedere.

#### Obiettivi raggiungibili direttamente mediante l'isolamento di server e domini

L'obiettivo generale dell'isolamento dei server e dei domini è quello di ridurre il rischio di accesso non autorizzato ai computer attendibili da parte di computer non attendibili. Con le attuali piattaforme, la capacità di isolare un computer remoto limitando l'accesso di rete in ingresso è basata sulla possibilità di autenticare il computer come membro di dominio mediante il protocollo di negoziazione della protezione IKE (Internet Key Exchange) IPSec. L'autenticazione dell'utente avviene solo dopo l'autenticazione del computer e a condizione che le associazioni di protezione IPSec proteggano i protocolli di livello superiore e le connessioni delle applicazioni tra due computer. Implementando l'isolamento dei server e dei domini, è quindi possibile raggiungere i seguenti obiettivi:

-   Isolare i computer membri di un dominio attendibile dalle periferiche non attendibili a livello di rete.

-   Garantire che l'accesso di rete in ingresso a un membro di un dominio attendibile sulla rete interna avvenga da parte di un altro membro di un dominio attendibile.

-   Consentire ai membri di un dominio attendibile di limitare l'accesso di rete in ingresso a un gruppo specifico di computer membri di dominio.

-   Circoscrivere i rischi di attacco alla rete a un numero ridotto di host, che rappresentano il confine o limite del dominio attendibile, ai quali è possibile applicare con maggiore efficacia le strategie di riduzione dei rischi (quali la registrazione, il monitoraggio e il rilevamento delle intrusioni).

    -   Concentrarsi sul monitoraggio preventivo e l'assicurazione della conformità, definendo le relative priorità, prima di un attacco.

-   Concentrarsi sulle contromisure e le attività di ripristino, accelerandone l'implementazione, prima, durante e dopo l'attacco.

-   Migliorare la protezione aggiungendo caratteristiche di autenticazione avanzata a livello di pacchetto, integrità, misure antireplay e crittografia, senza necessità di modificare le applicazioni e i protocolli del livello superiore, ad esempio mediante i protocolli SMB (Server Message Block) e NetBT (NetBIOS su TCP/IP).

L'isolamento dei server e dei domini è finalizzato alla protezione di *tutti* i servizi di rete sull'host attendibile dalla possibilità di accesso e attacco tramite una rete non attendibile. L'isolamento dei server e dei domini riduce la vulnerabilità degli host ai punti deboli e agli errori di altri tipi di protezione di rete e ai punti deboli della protezione delle credenziali utente. Le soluzioni di isolamento dei server e dei domini affrontano infine pericoli di rete simili a quelli che vengono gestiti da altre tecnologie di protezione di rete, assicurando però un diverso livello di controllo dell'accesso di rete e della protezione del traffico. Ad esempio, la soluzione di isolamento dei server e dei domini consente di autorizzare l'accesso in ingresso verso specifici computer host attendibili sulla base dell'identità di dominio dell'utente e dell'host, assicurando così una protezione end-to-end di determinate comunicazioni autorizzate. Al contrario, la maggior parte delle tecnologie di protezione di rete supporta solo l'identità utente.

#### Rischi affrontati mediante l'isolamento di server e domini

Il rischio principale che è possibile ridurre mediante l'isolamento dei server e dei domini è quello dell'accesso non autorizzato a un computer attendibile da parte di un computer considerato non attendibile. L'adozione di questa soluzione da sola non consente di ridurre efficacemente determinati rischi di protezione. La mancata implementazione di ulteriori processi e tecnologie di protezione potrebbe in definitiva vanificare i vantaggi di protezione ottenuti con la soluzione di isolamento. Alcuni esempi di gravi rischi di protezione che non è possibile ridurre direttamente con questa soluzione includono:

-   **Il rischio che un utente attendibile venda o divulghi dati riservati**. Sebbene la soluzione di isolamento sia in grado di controllare le comunicazioni effettuate dai computer nella rete interna, gli utenti amministrativi possono aggirare tali controlli. Questa soluzione non è in grado di eliminare il rischio di copia o divulgazione non autorizzata di dati riservati da parte di utenti attendibili.

-   **Il rischio di violazione delle credenziali di utente attendibile**. Anche se gli amministratori possono scegliere di crittografare con IPSec la maggior parte del traffico per proteggere le informazioni di accesso alla rete, la protezione IPSec del traffico di accesso degli utenti ai controller di dominio non è supportata. L'isolamento dei server e dei domini può costringere un pirata informatico a utilizzare un host attendibile per attaccare altri host attendibili. Un pirata informatico può inoltre attaccare gli host attendibili mediante credenziali violate da un host esentato dall'utilizzo di IPSec per l'accesso agli host attendibili (ad esempio un controller di dominio o un server DNS) oppure host che accettano connessioni in ingresso da computer considerati non attendibili. Gli amministratori sono in grado di controllare se gli host attendibili effettuano comunicazioni in uscita verso host considerati non attendibili, tuttavia questa soluzione non è in grado di ridurre il rischio che un pirata informatico riesca a ottenere le credenziali da utenti attendibili che abbia indotto a rivelare le proprie password.

-   **Utenti inaffidabili**. Rientrano in questa categoria gli utenti autorizzati che abusano delle proprie credenziali di accesso. Ad esempio, questa soluzione non è in grado di ridurre il rischio che un dipendente insoddisfatto decida di rubare informazioni utilizzando un host attendibile a cui può accedere in virtù delle mansioni ricoperte all'interno dell'azienda. Se un hacker riesce ad accedere fisicamente a un computer host attendibile, potrebbe ottenere l'accesso amministrativo non autorizzato al computer. Poiché gli amministratori possono disattivare la protezione assicurata dall'isolamento dei server e dei domini, è fondamentale limitare l'ambito di accesso e il numero degli amministratori (inclusi gli amministratori dell'organizzazione, di dominio e locali di workstation o server membri).

-   **Il rischio di accesso a computer considerati non attendibili tramite altri computer non attendibili**. Questa soluzione non è in grado di ridurre il rischio che un pirata informatico utilizzi i computer considerati non attendibili per sferrare un attacco ad altri computer non attendibili.

-   **Il rischio di accesso a computer attendibili tramite altri computer non attendibili**. Le soluzioni di isolamento dei server e dei domini sono progettate per proteggere gli host attendibili. Tuttavia, per motivi pratici correlati alla distribuzione, la soluzione consente che esistano membri di un dominio attendibile che per diversi motivi non utilizzano IPSec per negoziare l'accesso trusted ad altri host attendibili. Tali computer attendibili, ma non abilitati per IPSec, sono inclusi in un elenco esenzioni (ad esempio, i controller di dominio). La soluzione identifica inoltre determinati host attendibili a cui accedono i computer ritenuti non attendibili per fornire i servizi del gruppo Limite per il dominio di isolamento. Se un utente malintenzionato acquisisce il controllo di un host esentato o limite, può riuscire ad attaccare tutti gli altri host attendibili all'interno del dominio di isolamento.

-   **Garanzia di conformità ai criteri di protezione degli host attendibili**. Questa soluzione propone una modalità di definizione degli host attendibili e, in particolare, richiede l'appartenenza a un dominio Windows 2000 o Windows Server 2003. La soluzione dipende dall'efficacia dell'autenticazione IPSec IKE basata sul dominio (Kerberos) nel determinare l'attendibilità e quindi nel proteggere la connettività tramite IPSec. Nel corso del tempo e per diversi motivi, gli host attendibili potrebbero non rispettare più tutti i criteri di attendibilità e tuttavia riuscire ancora a completare l'autenticazione come membri di dominio. È compito dei sistemi e dei processi di gestione IT aziendale assicurare la conformità alla definizione di host attendibile da parte di tutti i membri di dominio.

Per affrontare tali problemi, nell'ambiente di prova della Woodgrove sono stati applicati a tutti i sistemi i modelli e le configurazioni di rafforzamento della protezione consigliati. Per ulteriori informazioni sulle tecnologie di protezione e le procedure di gestione per la piattaforma Windows, vedere il sito Web del [Resource Center di TechNet Sicurezza](http://technet.microsoft.com/security/default.aspx) all'indirizzo www.microsoft.com/technet/security/.

[](#mainsection)[Inizio pagina](#mainsection)

### Combinazione dell'isolamento di server e domini con la strategia globale di protezione della rete

L'isolamento dei server e dei domini viene impiegato a integrazione di altri meccanismi di prevenzione o di reazione volti a proteggere la rete e le periferiche connesse ad essa, inclusi i computer. Quello della protezione è un problema molto articolato che richiede diversi livelli di intervento; è pertanto utile prendere in esame il concetto di difesa a più livelli e i concetti di alto livello a essa correlati. Una strategia globale di protezione della rete prevede l'applicazione delle tecnologie appropriate al fine di ridurre i rischi con priorità massima evitando al contempo una dipendenza significativa da singoli punti deboli. Se, ad esempio, viene a mancare la protezione perimetrale a causa di un errore di configurazione o un dipendente malintenzionato, quali altri livelli di difesa sono in grado di contrastare eventuali attacchi alla rete e l'infezione degli host interni attendibili? Cosa consente di bloccare gli attacchi ai danni di tutti i computer host in Europa o in Asia se un pirata informatico riesce a connettersi tramite una porta Ethernet di una sala riunioni di una sede negli Stati Uniti?

#### Difesa su più livelli

La difesa su più livelli consiste in un approccio articolato alla protezione dei computer, anziché nell'adozione di un unico meccanismo per raggiungere il medesimo obiettivo di protezione. Per attuare un sistema di difesa a più livelli è necessario identificare innanzi tutto le possibili origini dell'infezione e gli avversari potenzialmente pronti ad attaccare l'organizzazione, nonché gli eventuali obiettivi di tali attacchi. Un esempio di possibile avversario potrebbe essere una società di spionaggio industriale assunta da un concorrente al fine di sottrarre informazioni relative a un nuovo prodotto o servizio in fase di sviluppo. Dopo aver identificato i potenziali autori e obiettivi degli attacchi, è necessario applicare le procedure di risposta ai problemi ai computer che potrebbero venire violati. Tali metodi includono l'autenticazione, l'autorizzazione, la riservatezza e il non ripudio. Un'organizzazione che adotta le procedure di protezione-rilevamento-reazione consigliate, è consapevole che gli attacchi *si verificheranno*** ** e riconosce l'importanza fondamentale del loro rilevamento tempestivo e del contenimento delle interruzioni del servizio o delle perdite di dati. Le procedure di protezione-rilevamento-reazione consentono di riconoscere che proprio perché è altamente probabile che si verifichi un attacco, è importante dedicare più impegno alla protezione dei dati e beni aziendali piuttosto che alle attività di prevenzione degli attacchi. In generale, è più conveniente proteggersi dagli attacchi piuttosto che ripristinare la situazione precedente dopo che l'attacco si è già verificato.

I meccanismi di Information Assurance sono tutti incentrati sui dipendenti, i processi e le tecnologie. L'isolamento riguarda pertanto tutte e tre queste aree e viene attuato per mezzo di una comprensione approfondita dei rischi, dei requisiti e dei beni che devono essere oggetto delle attività di protezione, tenendo conto inoltre di fattori legati ai dipendenti e ai processi. Al fine di pervenire all'isolamento, è inoltre necessario conoscere lo stato attuale della rete e delle periferiche di rete, quali sono i requisiti di comunicazione che definiscono le modalità di interazione tra i computer e quali sono i requisiti di protezione che impongono delle limitazioni al fine di raggiungere l'equilibrio ottimale tra protezione e comunicazione.

Per una discussione più approfondita di questo argomento, consultare il white paper "[Defense in Depth](http://www.nsa.gov/ia/_files/support/defenseindepth.pdf)" a cura della NSA (National Security Agency), disponibile all'indirizzo http://www.nsa.gov/snac/support/defenseindepth.pdf.

Informazioni ed esempi di progettazione pratici per questo processo sono disponibili nel capitolo [Enterprise Design](http://www.microsoft.com/technet/itsolutions/techguide/wssra/raguide/security_architecture_1.mspx) della guida *Windows Server System Reference Architecture*, disponibile su TechNet all'indirizzo www.microsoft.com/technet/itsolutions/wssra/
raguide/Security\_Architecture\_1.mspx.

La figura seguente illustra come è possibile combinare una soluzione di isolamento logico con l'approccio di difesa su più livelli illustrato nella guida Windows Server System Reference Architecture:

[![](images/Dd536205.SGFG0201(it-it,TechNet.10).gif "Figura 2.1 Difesa su più livelli e isolamento logico")](https://technet.microsoft.com/it-it/dd536205.sgfg0201_big(it-it,technet.10).gif)

**Figura 2.1 Difesa su più livelli e isolamento logico**

In questa figura viene evidenziato un aspetto importante: il livello di protezione dell'isolamento logico è volto a proteggere direttamente il computer host attraverso il controllo delle comunicazioni di rete. Questo ruolo è molto simile a quello di un firewall basato su host. Tuttavia, i servizi di autorizzazione e blocco porte non vengono attuati dal firewall host, bensì tramite IPSec, che negozia inoltre i servizi di accesso alla rete attendibile. Una volta autorizzato l'accesso, IPSec protegge tutti i pacchetti scambiati tra i due computer. Nel contesto di questa soluzione, una soluzione di "isolamento logico" come l'isolamento dei server e dei domini:

-   Non assicura la protezione delle periferiche di rete, ad esempio i router.

-   Non offre il controllo degli accessi fisici alla rete, non permette ad esempio di specificare quali computer sono autorizzati a stabilire una connessione di accesso remoto VPN o di garantire una protezione attuata tramite firewall di rete.

-   Non protegge i collegamenti di rete, ad esempio lo standard 802.1x per il controllo degli accessi e la crittografia WEP 802.11 per i collegamenti senza fili. IPSec assicura tuttavia la protezione end-to-end di tutti i collegamenti di rete nel percorso tra gli indirizzi IP (Internet Protocol) di origine e di destinazione.

-   Non offre la protezione di tutti gli host della rete, ma solo degli host che fanno parte della soluzione di isolamento.

-   Non protegge i percorsi a livello di applicazione, quali il percorso end-to-end del flusso di messaggi di posta elettronica e .NET e le richieste HTTP (Hypertext Transmission Protocol) che il proxy può inviare diverse volte tra il client e il server Web di destinazione.

Un'analisi per la riduzione dei rischi di protezione deve tener conto delle implicazioni di sicurezza a tutti i livelli. Ad esempio, se a un determinato computer viene impedito l'accesso a un server al livello di isolamento logico, non ha importanza quale utente si connette al computer, in quanto l'accesso al server verrà negato a tutti gli utenti, amministratori inclusi.

#### Confronto tra SSL/TLS e IPSec

Il criterio IPSec non è un sostitutivo della protezione a livello di applicazioni, quale ad esempio SSL/TLS. Uno dei vantaggi offerti da IPSec è la possibilità di proteggere il traffico di rete delle applicazioni esistenti senza doverle modificare. L'utilizzo di IPSec in ambienti con applicazioni basate su SSL/TLS può offrire i seguenti vantaggi:

-   Protezione di tutte le applicazioni e del sistema operativo da attacchi di rete attuati tramite computer ritenuti non attendibili e altre periferiche.

-   Approccio di difesa su più livelli contro possibili utilizzi impropri o non conformi di SSL/TLS (ad esempio, se i dati eHPI non sono crittografati e autenticati).

-   Prevenzione dell'immissione di credenziali utente nei computer considerati non attendibili: gli utenti visualizzano la richiesta di accesso a un sito Web interno protetto da SSL/TLS solo dopo che IPSec ha stabilito il trust reciproco tra il client e il server.

-   Protezione nei casi in cui non è possibile utilizzare le impostazioni del Registro di sistema di Windows per selezionare algoritmi SSL/TLS conformi alle normative. In Windows 2000, Windows XP e Windows Server 2003 sono disponibili chiavi del Registro di sistema per il controllo degli algoritmi SSL/TLS, descritte nell'articolo della Microsoft Knowledge Base 245030, "[How to Restrict the Use of Certain Cryptographic Algorithms and Protocols in Schannel.dll](http://support.microsoft.com/?kbid=245030)", all'indirizzo http://support.microsoft.com/?kbid=245030.

-   Protezione nei casi in cui i certificati non siano disponibili.

IPSec protegge il traffico tra gli indirizzi IP di origine e di destinazione. SSL/TLS può proteggere il traffico lungo l'intero percorso dell'applicazione (ad esempio dal browser Web, attraverso il proxy fino al server Web).

Il National Institute for Standards and Technology (NIST) sta sviluppando una guida sull'utilizzo di TLS. La pubblicazione speciale 800-52 "Guidelines on the Selection and Use of Transport Layer Security" è una guida all'implementazione di TLS destinata al governo federale degli Stati Uniti. Per ulteriori informazioni su questo documento, vedere il sito Web [NIST Computer Security Division](http://csrc.nist.gov/publications/index.html), all'indirizzo http://csrc.nist.gov/publications/index.html. Attualmente non sono disponibili guide analoghe sull'utilizzo di IPSec. Tuttavia, la National Security Agency (NSA) degli Stati Uniti ha pubblicato alcune guide per l'utilizzo di IPSec in Windows 2000 . Si consiglia alle organizzazioni che devono ottenere la conformità con le linee guida NSA di valutare i contenuti della documentazione NSA oltre alle indicazioni relative alla presente soluzione.

IPSec in combinazione con l'autenticazione dei certificati offre una protezione simile a quella ottenuta tramite SSL/TLS, con alcune differenze. IPSec per Windows supporta solo una piccola parte degli algoritmi di crittografia supportati da TLS e raccomandati nella pubblicazione NIST 800-52 (ad esempio 3DES, SHA-1 e 1024-bit ephemeral Diffie-Hellman). La soluzione presentata in questa guida è basata sull'autenticazione IKE tra membri di dominio mediante firme del protocollo Kerberos anziché certificati firmati. La negoziazione IPSec IKE per Windows stabilisce il trust reciproco tra i computer che utilizzano il protocollo Kerberos e l'autenticazione basata su certificati. Non essendo integrato nelle applicazioni, IKE non è in grado di verificare che il nome del computer di destinazione sia il nome atteso dall'applicazione per la connessione e non può quindi impedire attacchi di tipo "man-in-the-middle" provenienti da un altro computer host. Poiché SSL/TLS è integrato nell'applicazione, il nome di destinazione non solo viene autenticato (conferma dell'attendibilità), ma può essere anche verificato rispetto al nome atteso.

[](#mainsection)[Inizio pagina](#mainsection)

### Terminologia utilizzata

Prima di proseguire con gli argomenti del capitolo, è utile prendere in esame alcuni termini frequentemente utilizzati nel contesto di questa soluzione. Se i termini descritti sono già noti, è possibile ignorare questa sezione. Tuttavia, se non si possiedono conoscenze adeguate sul significato di tali termini, le spiegazioni presentate all'interno della guida possono risultare di difficile comprensione.

#### Terminologia relativa all'isolamento

La terminologia seguente riguarda specificamente il concetto di isolamento logico. È pertanto essenziale comprenderne appieno il significato prima di procedere con la lettura di questo capitolo.

-   **Isolamento**. Separazione logica di uno o più computer da altri computer.

-   **Isolamento del dominio**. Questa espressione identifica il tipo di isolamento che separa i computer attendibili dai computer considerati non attendibili. Il possesso di credenziali valide e l'esito positivo dell'autenticazione IKE sono gli unici due requisiti necessari per l'isolamento di un computer. Per dominio si intende qualsiasi dominio nel percorso di trust che sia accessibile tramite trust bidirezionale tra i due host che tentano di proteggere le comunicazioni tra loro.

-   **Isolamento del server**. Questa espressione definisce le modalità di limitazione da parte dei server dell'accesso in ingresso attuate tramite IPSec e l'impostazione del diritto utente "Accedi al computer dalla rete" per un gruppo specifico di computer attendibili.

-   **Isolamento logico**. Questo concetto di portata più ampia è riferito a diverse tecnologie di isolamento che includono l'isolamento dei domini e dei server e la piattaforma NAP (Network Access Protection) che consentono l'isolamento dei computer al livello di rete.

-   **Gruppo di isolamento**. Gruppo logico di computer host attendibili che condividono gli stessi criteri di protezione delle comunicazioni, essenzialmente gli stessi requisiti di traffico di rete in ingresso e in uscita. È possibile implementare i controlli degli accessi in ingresso e in uscita per un gruppo di isolamento con i soli criteri IPSec, utilizzando le operazioni di autorizzazione e di blocco oppure la negoziazione della protezione IPSec in combinazione con i diritti di accesso di rete dei criteri di gruppo (ed eventualmente altre configurazioni di rete o impostazioni di connessione). Le applicazioni, i servizi di rete e i protocolli individuali devono avere una configurazione specifica che consenta di soddisfare i requisiti di traffico per il livello a cui appartengono. Ad esempio, per un gruppo di server Exchange è necessario che il computer client o server sia un membro di un dominio attendibile affinché possa essere stabilita una connessione TCP/IP in ingresso. Questo gruppo, a cui è consentito stabilire connessioni TCP/IP in uscita solo con i membri di dominio (con alcune eccezioni), viene definito gruppo di isolamento server Exchange.

-   **Dominio di isolamento**. Gruppo di isolamento i cui membri sono gli stessi del dominio di Windows. Se il dominio comprende domini attendibili bidirezionali, i membri di tali domini fanno parte del dominio di isolamento. I requisiti di comunicazione in ingresso e in uscita di un gruppo di isolamento sono semplici: le connessioni in ingresso sono permesse ai soli host attendibili membri di dominio. Un server membro di un gruppo di isolamento server può avere dei client che fanno parte del dominio isolato.

-   **Gruppo di accesso di rete**. Questa espressione fa riferimento al gruppo di protezione del dominio di Windows utilizzato per controllare l'accesso di rete a un computer, mediante le impostazioni di protezione dei criteri di gruppo per i diritti di accesso di rete. Tali impostazioni vengono create allo scopo di applicare i requisiti di accesso in ingresso per i gruppi di isolamento. Per ogni gruppo di isolamento possono esistere un Gruppo consenti accesso di rete (ANAG) e un Gruppo nega accesso di rete (DNAG).

-   **Affidabilità o trust**. Questo termine viene utilizzato per indicare il fatto che un computer è in grado di accettare la convalida della sua identità attraverso il processo di autenticazione. Il trust di dominio implica che tutti i membri del dominio incaricano il controller di dominio di stabilire l'identità e di fornire informazioni sull'appartenenza al gruppo per tale identità. L'affidabilità è un prerequisito fondamentale della comunicazione con un computer remoto basata su IPSec. Le comunicazioni con un computer o un utente affidabile vengono considerate accettabili e presumibilmente a basso rischio.

-   **Host potenzialmente attendibile**. Con questa espressione si identifica un computer configurabile in modo che soddisfi i requisiti minimi di protezione di un'organizzazione, tuttavia questo computer può non essere un host attendibile in un determinato momento. Durante la determinazione dei membri di un gruppo di isolamento potenzialmente attendibile, è importante sapere quali computer sono attendibili.

-   **Host attendibile**. Indica un computer che esegue Windows 2000, Windows XP o Windows Server 2003 che, come minimo, appartiene a un dominio di protezione Windows 2000 ed è in grado di applicare un criterio IPSec. Gli host attendibili vengono tipicamente definiti in base alla capacità di soddisfare determinati requisiti di gestione e protezione aggiuntivi. La configurazione dell'host viene controllata in modo che l'host sia soggetto a rischi di protezione bassi e gestiti. Le probabilità che un host attendibile sia all'origine di un'infezione o un attacco sono ridotte. Per una trattazione dettagliata di questo argomento, vedere il capitolo 3, "Determinazione dello stato corrente dell'infrastruttura IT".

-   **Host non attendibile**. Computer host considerato non attendibile in quanto la sua configurazione non è nota oppure non è gestita. Esistono garanzie minime o nulle del fatto che l'host (o il suo utente) non sarà all'origine di un'infezione o un attacco se connesso alla rete.

-   **Host limite**. Si tratta di un host attendibile esposto al traffico di rete di host sia attendibili che non attendibili. Pertanto è necessario sottopore questo host a stretto monitoraggio e attuare misure di difesa contro gli attacchi più rigide rispetto agli altri host attendibili. È necessario ridurre al minimo il numero di host limite in quanto essi rappresentano un fattore di rischio per gli altri host attendibili.

-   **Esenzione**. Computer, di dominio oppure no, che non utilizza IPSec. Esistono due tipi di esenzioni. I computer che utilizzano un indirizzo IP statico i cui indirizzi sono inclusi nell'elenco esenzioni per i criteri IPSec affinché gli host attendibili non utilizzino IPSec nei loro confronti. I computer esentati dall'utilizzo dei criteri IPSec per la negoziazione di connessioni protette. Questi ultimi possono comparire o meno nell'elenco esenzioni. Un'esenzione può soddisfare i requisiti di host attendibile e tuttavia non avere comunicazioni protette con IPSec con gli altri host attendibili del dominio di isolamento.

#### Terminologia relativa alla protezione

È importante comprendere a fondo il significato della seguente terminologia correlata con la protezione.

-   **Autorizzazione**. È la procedura che consente a una persona, un computer, un processo o una periferica di accedere a certe informazioni, servizi o funzionalità. L'autorizzazione dipende dall'identità della persona, del computer, del processo o della periferica che richiede l'accesso, la cui identità viene verificata tramite l'autenticazione.

-   **Autenticazione**. È la procedura di convalida delle credenziali di una persona, un computer, un processo o una periferica. Tale procedura prevede che la persona, il processo o la periferica che avanzano la richiesta di autenticazione forniscano delle credenziali che comprovino l'identità del richiedente. Forme comuni di credenziali sono chiavi private per certificati digitali, che vengono configurate segretamente dagli amministratori su due periferiche diverse (chiave già condivisa), password segrete di accesso al dominio da parte di utenti o computer oppure un oggetto biologico come le impronte digitali o la scansione della retina.

-   **Spoofing**. Ai fini di questa guida, per spoofing si intende un'operazione attraverso la quale un pirata informatico falsifica un indirizzo IP autentico nel tentativo di interferire con le comunicazioni o intercettare dati.

-   **Non ripudio**. È la tecnica utilizzata per fare in modo che l'autore di un'azione su un computer non possa negare falsamente di avere eseguito tale azione. Il non ripudio fornisce una prova sufficientemente inconfutabile che una determinata azione, ad esempio il trasferimento di fondi, l'autorizzazione di un acquisto o l'invio di un messaggio, è stata eseguita da un utente o una periferica specifica.

-   **Testo crittografato**. Si tratta di dati codificati. Questo tipo di testo è il risultato di un processo di crittografia e può essere trasformato nuovamente in testo leggibile non crittografato mediante un'apposita chiave di decrittografia.

-   **Testo non crittografato** (a volte detto testo normale). Comunicazioni e dati in formato non crittografato.

-   **Hash**. Il risultato di dimensione fissa che si ottiene applicando una funzione matematica unidirezionale (a volte detta algoritmo) a una quantità arbitraria di dati di input. Se i dati di input cambiano, anche l'hash risulterà modificato. Le funzioni di hash vengono scelte in modo che la probabilità che due input diversi producano lo stesso valore hash risultante sia estremamente bassa. L'hash può essere utilizzato a diversi scopi, incluse l'autenticazione e la firma digitale, ed è altrimenti noto con il nome di message digest.

#### Terminologia relativa alle reti

Di seguito viene indicata la terminologia relativa agli elementi di rete della soluzione.

-   **Iniziatore**. Computer che avvia la comunicazione di rete con un altro computer.

-   **Risponditore**. Computer che risponde a una richiesta di comunicazione di rete.

-   **Percorso di comunicazione**. Il percorso della connessione che viene stabilita per il traffico di rete tra l'iniziatore e il risponditore.

#### Terminologia relativa ai criteri di gruppo.

Di seguito viene indicata la terminologia relativa ai criteri di gruppo di Windows.

-   **GPO**. Le impostazioni dei criteri di gruppo vengono incluse in un oggetto Criteri di gruppo (GPO, Group Policy Object). Associando un GPO a contenitori di sistema di Active Directory selezionati, quali siti, domini e unità organizzative, è possibile applicare le impostazioni GPO agli utenti e ai computer nei contenitori di Active Directory specificati. L'Editor oggetti Criteri di gruppo consente di creare un GPO individuale, mentre la Console Gestione Criteri di gruppo permette la gestione dei GPO a livello aziendale.

-   **Criteri di dominio**. Criteri memorizzati a livello centrale in Active Directory.

-   **Criteri locali**. Criteri memorizzati sui singoli computer.

#### Terminologia IPSec di base

È importante comprendere a fondo il significato della seguente terminologia relativa a IPSec.

-   **Criteri IPSec**. Gruppo di regole di protezione per l'elaborazione del traffico di rete al livello IP. Una regola di protezione contiene filtri di pacchetti associati a un'operazione di autorizzazione, blocco o negoziazione. Quando è necessaria la negoziazione, i criteri IPSec contengono i metodi di autenticazione e protezione da utilizzare per la negoziazione con il computer peer.

-   **Criteri IPSec persistenti**. Tipo di criteri IPSec introdotti con Windows XP e Windows Server 2003 che consentono l'applicazione delle impostazioni dei criteri IPSec in modo persistente. I criteri persistenti vengono inizialmente applicati all'avvio del servizio IPSec in modo che sostituiscano le impostazioni dei criteri IPSec locali o di dominio.

-   **Negoziazione IKE**. Si tratta del processo che avviene all'avvio di una connessione di rete per determinare se un computer che utilizza IPSec autorizzerà la connessione.

-   **Associazioni di protezione (SA)**. Si tratta degli accordi presi tra due host sul metodo di comunicazione IPSec da adottare e i diversi parametri che definiscono tale negoziazione.

    -   SA in modalità principale. Sono le prime associazioni di protezione stabilite durante la negoziazione IKE tra il computer iniziatore e il risponditore.

    -   SA in modalità rapida. Sono le associazioni di protezione che vengono negoziate dopo che è stata stabilita la SA in modalità principale per ognuna delle sessioni di comunicazione tra gli host.

-   **Ritorno alla modalità non crittografata**. Permette a un iniziatore IKE di consentire il normale traffico TCP/IP (non IKE o IPSec) se non viene ricevuta una risposta IKE dal risponditore. Corrisponde all'opzione **Consenti comunicazioni non protette con computer senza IPSec** nella pagina delle proprietà dell'operazione filtro dello strumento di gestione criteri IPSec.

-   **Passthrough in ingresso**. Questa opzione consente a un computer abilitato per IPSec di accettare un normale pacchetto in ingresso TCP/IP (non IKE o IPSec) da un computer remoto. La normale risposta del protocollo di livello superiore è un pacchetto in uscita che aziona un'inizializzazione IKE per il computer remoto. Corrisponde all'opzione **Accetta comunicazioni non protette, ma rispondi sempre usando IPSec** nella pagina delle proprietà dell'operazione filtro dello strumento di gestione criteri IPSec.

    **Nota**. Se è abilitato il passthrough in ingresso, ma non la modalità non crittografata per un risponditore, quest'ultimo non riuscirà a comunicare con un iniziatore senza IPSec.

Esistono altri termini riguardanti elementi di IPSec specifici che è importante comprendere a fondo. Nell'appendice A, "Panoramica dei concetti relativi ai criteri IPSec", di questa guida vengono illustrati tali termini e viene fornita inoltre una panoramica generale del processo IPSec utilizzato dai computer appartenenti ai gruppi di isolamento creati nell'ambito di questa soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Realizzazione dell'isolamento di server e domini

Il concetto di isolamento dei computer rispetto ai possibili rischi non è nuovo. Tecniche quali l'utilizzo di firewall per attuare la segmentazione della rete, l'applicazione del controllo degli accessi e del filtraggio ai router e la segmentazione fisica del traffico di rete consentono tutte di pervenire a un certo grado di isolamento.

La soluzione presentata in questa guida è stata progettata per l'utilizzo insieme alle periferiche e alle tecniche esistenti nell'infrastruttura di rete aziendale. Il punto fondamentale da comprendere è che l'isolamento viene attuato apportando modifiche al software host esistente nelle piattaforme Windows 2000 e successive. Tecnologie e procedure quali la segmentazione di rete, le VLAN, i controlli degli accessi alla rete perimetrale, la quarantena della rete e il rilevamento delle intrusioni di rete vengono attuate mediante l'implementazione o la modifica della configurazione delle periferiche di rete. L'isolamento dei server e dei domini integra tali tecniche e procedure offrendo un nuovo livello di protezione per i membri di domini di Windows gestiti. Gli amministratori IT di Windows possono implementare l'isolamento dei server e dei domini apportando modifiche minime o nulle ai percorsi di rete e ai metodi di connessione esistenti, intervenendo poco o per niente sulle applicazioni e mantenendo l'infrastruttura di dominio Windows 2000 o Windows Server 2003 esistente.

#### Componenti dell'isolamento del server e del dominio

La soluzione di isolamento dei server e dei domini comprende numerosi componenti importanti che, insieme, permettono la realizzazione della soluzione. Questi componenti vengono descritti nelle sottosezioni seguenti.

##### Host attendibili

Gli host attendibili sono computer che l'organizzazione IT può gestire al fine di assicurane la conformità a requisiti di protezione minimi. Molto spesso è possibile raggiungere questo stato di trust solo se il computer esegue un sistema operativo protetto e gestito, un software antivirus e applicazioni e sistemi operativi aggiornati. Dopo la determinazione dell'attendibilità del computer, la fase successiva prevede la conferma di tale stato attraverso l'autenticazione. Per ulteriori informazioni sulla determinazione dello stato, vedere il capitolo 3, "Determinazione dello stato corrente dell'infrastruttura IT".

**Nota**: IPSec da solo non consente di stabilire la conformità di un computer a determinati criteri per gli host. L'utilizzo di una tecnologia di monitoraggio consente di valutare la configurazione di base del computer e segnalare eventuali modifiche richieste.

##### Autenticazione host

Il meccanismo di autenticazione host determina se il computer che tenta di avviare una sessione possiede credenziali di autenticazione valide, quali ticket Kerberos, certificati o eventualmente chiavi già condivise. Attualmente esistono due tecnologie in grado di offrire questo tipo di meccanismo di autenticazione per i computer Windows. Tali tecnologie vengono descritte nella sezione seguente.

###### Protocollo 802.1X

Il protocollo 802.1X è un protocollo basato su standard che consente l'autenticazione degli utenti e delle periferiche affinché possano ottenere l'autorizzazione alla connettività tramite una porta di rete a livello di collegamento, quali un collegamento senza fili 802.11 o una porta Ethernet 802.3. Ciò consente il controllo dell'esperienza degli utenti (ad esempio a scopo di fatturazione), il controllo delle autorizzazioni e altre funzionalità. Questo protocollo richiede uno o più server dedicati, ad esempio RADIUS (Remote Authentication Dial-In User Service), e un'infrastruttura di rete che lo supporti. Il protocollo 802.1X è stato progettato per fornire il controllo degli accessi di rete e le chiavi di crittografia 802.11 WEP (Wired Equivalent Privacy) per il traffico di rete tra il client e il punto di accesso senza fili. Una volta ottenuto l'accesso di rete, la connettività della periferica è solitamente aperta al resto della rete interna. I dati vengono decrittografati nel punto di accesso senza fili e successivamente vengono inoltrati come normale testo non crittografato con il protocollo TCP/IP fino alla destinazione finale ed eventualmente protetti mediante diversi meccanismi a livello di applicazione.

Nell'esempio della Woodgrove, è necessario proteggere tutti gli host attendibili dai computer non attendibili sulla rete interna. Anche se con il protocollo 802.1X, è possibile concedere l'accesso tramite i collegamenti senza fili e alcuni tipi di connettività cablata ai soli computer attendibili, gli switch utilizzati per molte porte interne Ethernet 802.3 non supportano l'autenticazione 802.1X. La sostituzione materiale di tutte le porte per l'accesso LAN in tutti gli uffici del mondo comporterebbe ingenti costi di acquisto e installazione hardware. Per questo motivo, la Woodgrove ha deciso di utilizzare il protocollo 802.1X per la protezione senza fili, ma non per le porte Ethernet cablate.

Un altro requisito di protezione della Woodgrove era assicurare la crittografia del traffico end-to-end tra i client attendibili e i server di crittografia. Il protocollo 802.1X è stato sviluppato per crittografare le connessioni senza fili, ma non quelle cablate. Anche quando le connessioni senza fili sono crittografate, i dati non sono più protetti dopo che i pacchetti sono stati inoltrati sulla rete LAN interna dopo la decrittografia nel punto di accesso senza fili. Di conseguenza, il protocollo 802.1X non è in grado di soddisfare il requisito di crittografia end-to-end.

Sebbene il protocollo 802.1X non possa soddisfare tutti i requisiti di protezione della Woodgrove, viene tuttavia utilizzato per la protezione della connettività senza fili. Microsoft consiglia di utilizzare il protocollo 802.1X per proteggere le reti senza fili e, se possibile, per assicurare il controllo degli accessi per le reti cablate. Per ulteriori informazioni sull'utilizzo del protocollo 802.1X, vedere la pagina [Wi-Fi](http://www.microsoft.com/windowsserver2003/technologies/networking/wifi/default.mspx) nel sito Web Microsoft all'indirizzo http://www.microsoft.com/wifi.

###### IPsec

IPSec è lo standard di protezione IETF (Internet Engineering Taskforce) per il protocollo IP. Assicura un meccanismo di protezione generale a livello IP basato su criteri, ideale per l'autenticazione di un host alla volta. I criteri IPSec comprendono regole di protezione e impostazioni che controllano il flusso del traffico IP in ingresso e in uscita di un host. È possibile gestire i criteri centralmente in Active Directory mediante oggetti Criteri di gruppo per l'assegnazione dei criteri ai membri di dominio. IPSec consente di stabilire comunicazioni sicure tra gli host e utilizza il protocollo di negoziazione IKE (Internet Key Exchange) per negoziare le opzioni di comunicazione protetta tramite IPSec tra due host. Gli accordi presi tra due host sul metodo di comunicazione IPSec che verrà adottato e i diversi parametri che definiscono tale negoziazione sono detti *associazioni di protezione* o SA. La negoziazione IKE stabilisce una SA in modalità principale (ISAKMP SA) e una coppia di SA in modalità rapida (SA IPSec), una per il traffico in ingresso, l'altra per il traffico in uscita. Per stabilire la SA in modalità principale, IKE richiede l'autenticazione reciproca. In Windows, IKE può utilizzare uno dei tre metodi seguenti:

-   Protocollo di autenticazione Kerberos versione 5

-   Certificato digitale X.509 con la corrispondente coppia di chiavi pubblica e privata RSA (Rivest, Shamir and Adleman)

-   Una chiave già condivisa (una frase password, non una semplice password)

Il motivo più diffuso per cui si decide di non implementare IPSec è l'idea errata che questo criterio richieda certificati di infrastruttura a chiave pubblica (PKI, Public Key Infrastructure), spesso difficili da distribuire. Per evitare la necessità di un'infrastruttura a chiave pubblica, l'autenticazione di dominio di Windows 2000 (Kerberos) è stata integrata nel protocollo di negoziazione IKE.

La negoziazione IKE per Windows può essere configurata in modo da consentire le comunicazioni con i computer che non rispondono alla richiesta di negoziazione IKE. Questa funzionalità viene indicata come *modalità non crittografata* ed è una necessità pratica durante la distribuzione graduale di IPSec. Durante il normale funzionamento, è utile per consentire agli host attendibili di comunicare con i computer e le periferiche considerati non attendibili solo quando la richiesta di connessione viene avviata da un host attendibile. L'espressione *associazione di protezione debole* indica una comunicazione che IPSec non è in grado di proteggere con il protocollo AH (Authentication Header) oppure ESP (Encapsulating Security Payload). IPSec verifica l'esito della comunicazione, registrandola in un Registro protezione che contiene l'indirizzo IP di destinazione, ed esegue il monitoraggio del flusso del traffico. Quando dopo un periodo di inattività (5 minuti per impostazione predefinita) il flusso del traffico cessa, è necessario un nuovo tentativo di negoziazione quando vengono effettuate le nuove connessioni in uscita.

IPSec non supporta il filtraggio con informazioni sullo stato del traffico in uscita con le associazioni di protezione AH o ESP o per il traffico non crittografato con SA deboli. Pertanto, quando si utilizzano i criteri IPSec presentati in questa guida per attuare l'isolamento dei server e dei domini, l'host attendibile può ricevere connessioni in ingresso dal computer considerato non attendibile su qualsiasi porta aperta tramite la SA debole. Ciò rappresenta una potenziale finestra di vulnerabilità per gli attacchi. Questo progetto supporta inoltre determinati protocolli che negoziano le porte aperte per il ricevimento di connessioni in ingresso. È possibile aggiungere alla protezione IPSec il filtraggio con informazioni sullo stato delle connessioni in uscita utilizzando un prodotto firewall basato su host come Windows Firewall. Il traffico di rete protetto tramite IPSec AH o ESP senza crittografia non viene considerato come testo in formato normale perché per esso non è prevista l'autenticazione e la protezione contro spoofing e modifiche.

Poiché IPSec incapsula i normali pacchetti IP in un formato protetto, questi non appaiono più come pacchetti TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) durante il transito sulla rete. Nel corso della distribuzione di IPSec presso la Woodgrove Bank, è emerso che la maggior parte degli strumenti di gestione della rete presupponevano la possibilità di rapida identificazione delle applicazioni in base ai relativi numeri delle porte TCP o UDP (ad esempio la porta 25 per la posta elettronica e la porta 80 per il traffico Web). Quando si utilizza IPSec, il traffico diventa opaco e il sistema di rilevamento delle intrusioni di rete non è in grado di distinguere quale applicazione viene utilizzata o eseguire l'ispezione dei dati del pacchetto. Ciò comporta un problema di gestione della rete in quanto riduce il valore degli strumenti attualmente impiegati per il monitoraggio del traffico, il filtraggio di protezione, il WFQ (Weighted Fair Queuing) e la classificazione della qualità del servizio.

Purtroppo, la presupposizione della visibilità del traffico non è totalmente accurata e sta diventando rapidamente obsoleta, anche in assenza di IPSec. La relazione tra i numeri di porta e le applicazioni si sta anch'essa indebolendo. È possibile, ad esempio, gestire un server Web con un numero di porta arbitrario, documentando tale numero di porta nell'URL del sito. È inoltre possibile eludere il filtraggio della posta elettronica attuato da alcuni provider di servizi Internet (ISP) facendo passare il servizio di posta elettronica attraverso un diverso numero di porta. Numerose applicazioni peer-to-peer (P2P) sono dette *port agile,* ovvero utilizzano numeri di porta scelti casualmente allo scopo di evitare il rilevamento. Possiedono questa caratteristica anche le applicazioni basate sui servizi RPC (Remote Procedure Call), poiché questi scelgono a caso le porte nell'intervallo effimero (oltre 1024) per vari servizi.

È probabile che la diffusione dei servizi Web contribuirà all'aumento dei problemi di identificazione del traffico, perché il traffico di tali servizi passa sopra l'HTTP o l'HTTPS, attraverso la porta 80 o la porta 443. I client e i server basano quindi l'identificazione del traffico sull'URL HTTP. Tutte le applicazioni che passano a un'architettura dei servizi Web appaiono ai router come un unico flusso di dati indifferenzati in quanto il traffico di tali servizi Web passa attraverso una o poche porte anziché venire gestito dalle singole applicazioni o servizi su un numero di porta specifico. L'utilizzo di SSL e TLS per le connessioni HTTPS e la crittografia RPC riducono il valore delle ispezioni di rete come meccanismo di difesa dagli attacchi. Poiché le applicazioni di gestione della rete erano comunque in grado di analizzare gli indirizzi dei pacchetti ed erano visibili al resto del traffico non protetto da IPSec, la Woodgrove aveva deciso che la perdita di parte della funzionalità di gestione della rete non era tale da influire significativamente sulla pianificazione del progetto. Inoltre, alcuni fornitori di strumenti di gestione della rete erano disposti a modificare i loro prodotti per renderli in grado di effettuare ispezioni all'interno dei pacchetti IPSec non crittografati.

La maggior parte delle applicazioni basate su host non necessita di alcuna modifica per funzionare correttamente quando tutto il traffico tra gli indirizzi IP viene protetto con IPSec. Questa soluzione non prevede l'utilizzo di IPSec solo per applicazioni o protocolli specifici in ragione del rischio di attacchi ad altri servizi di rete. Se le applicazioni non funzionano correttamente con IPSec, l'amministratore può riuscire a consentire il relativo traffico al di fuori della protezione IPSec sulla base degli indirizzi IP utilizzati per i server. La scelta di consentire le applicazioni che utilizzano una porta nota non è consigliata in quanto ciò aprirebbe una finestra statica in ingresso che permetterebbe a un pirata informatico di stabilire connessioni in ingresso a qualsiasi porta aperta, vanificando quindi le finalità dell'isolamento. Non è possibile consentire le applicazioni che utilizzano porte allocate dinamicamente al di fuori dell'ambito di protezione con IPSec. Le applicazioni che utilizzano l'indirizzamento IP multicast e broadcast potrebbero non funzionare correttamente nell'ambito della protezione con IPSec per l'isolamento dei server e dei domini. IPSec per Windows supporta la possibilità di consentire tutto il traffico multicast e broadcast, con alcune eccezioni. Se esistono problemi di compatibilità delle applicazioni, rivolgersi al fornitore per sapere se e quando verranno rilasciati aggiornamenti o correzioni in grado di risolverli. Se un'applicazione non può essere aggiornata o sostituita con un'applicazione compatibile, è possibile che i computer che utilizzano tale applicazione non possiedano i requisiti necessari per l'inserimento nel dominio o gruppo di isolamento.

Oltre alle funzionalità di autenticazione, IPSec fornisce due utili servizi per le comunicazioni tra gli host: assicura l'integrità degli indirizzi ed esegue la crittografia del traffico di rete.

-   **Integrità degli indirizzi**. IPSec può utilizzare il protocollo AH per assicurare l'integrità di dati e indirizzi di tutti i pacchetti. Gli algoritmi AH per Windows prevedono un meccanismo di hash con chiave nel driver IPSec di Windows. L'utilizzo di AH previene gli attacchi di tipo ripetizione e garantisce un'integrità avanzata confermando che ogni pacchetto ricevuto non ha subito modifiche dal momento dell'invio a quello della ricezione. L'algoritmo AH *non* funziona correttamente durante il passaggio attraverso una periferica che esegue la conversione degli indirizzi di rete (NAT, Network Address Translation) in quanto tale conversione sostituisce l'indirizzo di origine nell'intestazione IP e pertanto viola la protezione assicurata da IPSec AH.

-   **Crittografia del traffico di rete**. IPSec assicura l'integrità e la riservatezza dei dati tramite la crittografia utilizzando l'opzione ESP (Encapsulating Security Payload) per il protocollo IP. Sebbene ESP non garantisca l'integrità degli indirizzi (tranne in caso di utilizzo congiunto con AH), può tuttavia attraversare una periferica NAT utilizzando l'incapsulamento UDP. Se le reti interne sono segmentate con periferiche che utilizzano NAT, ESP rappresenta la scelta logica in quanto non forza la crittografia dei pacchetti. IPSec per Windows supporta l'RFC 2410 che definisce l'utilizzo di ESP con la crittografia null (ESP/null). ESP/null assicura l'autenticità e l'integrità dei dati, nonché misure antireplay senza che sia richiesta la crittografia. Network Monitor per Windows Server 2003 è in grado di analizzare l'ESP non crittografato per esporre i normali protocolli del livello superiore TCP/IP. Se si utilizza la crittografia ESP, il monitoraggio dei pacchetti è possibile solo quando il computer utilizza una scheda di accelerazione hardware di rete per IPSec che esegue innanzi tutto la decrittografia dei pacchetti in ingresso.

    **Nota**: analogamente ad AH, ESP con la crittografia o la crittografia null assicura relazioni di peering IPSec avanzate per l'autenticazione. Offre inoltre la protezione antireplay ed è in grado di attraversare le periferiche NAT. Per questi motivi, la Woodgrove ha scelto di non implementare AH, decidendo di utilizzare solo ESP/null ed ESP con crittografia nella propria rete aziendale.

IPSec è in grado di funzionare in due modi diversi, in modalità di tunnel e in modalità di trasporto.

-   **Modalità di trasporto IPSec**. La modalità di trasporto IPSec è il metodo consigliato per proteggere il traffico tra host end-to-end. Il driver IPSec inserisce semplicemente un'intestazione IPSec dopo l'intestazione IP originale. L'intestazione IP originale viene mantenuta e il resto del pacchetto viene protetto mediante crittografia AH oppure ESP. I filtri IPSec controllano il traffico che viene bloccato, consentito o incapsulato tramite IPSec. I filtri IPSec specificano gli indirizzi IP di origine e di destinazione (o subnet), il protocollo (ad esempio ICMP o TCP) e le porte di origine e di destinazione. I filtri possono pertanto essere applicati a singoli computer oppure a tutti gli indirizzi di destinazione e i protocolli utilizzati. La modalità di trasporto è stata progettata per adattarsi agli indirizzi IP dinamici grazie all'aggiornamento automatico dei filtri configurati con "Indirizzo IP"; riduce il sovraccarico ed è molto più facile da utilizzare rispetto alla modalità di tunnel IPSec. La modalità di trasporto per la negoziazione IKE è quindi un modo efficace per autorizzare le connessioni in ingresso protette con IPSec. L'utilizzo della modalità di trasporto IPSec presenta alcuni problemi, tra i quali:

    -   **Un ritardo iniziale**. L'avvio e il completamento della negoziazione IKE comporta un ritardo di 1-2 secondi. Durante le comunicazioni continue, IKE tenta automaticamente di aggiornare le chiavi di crittografia che proteggono il traffico.

    -   **Ordine di priorità predefinito per i filtri**. I filtri dei criteri IPSec possono sovrapporsi e pertanto avere un ordine di priorità predefinito in base al quale *i filtri più specifici vengono applicati per primi*. Ciò richiede che entrambe le parti di una comunicazione dispongano di un set di filtri per la modalità di trasporto IPSec compatibili con la negoziazione IKE. Ad esempio, questa soluzione prevede un filtro più generico per tutto il traffico che negozia la protezione IPSec in combinazione con un filtro più specifico che consente solo il traffico ICMP, anziché proteggere questo tipo di traffico con IPSec.

    -   **Sovraccarico delle risorse di elaborazione**. La crittografia della modalità di trasporto IPSec ESP può comportare un sovraccarico delle risorse di elaborazione. Durante la copia dei file crittografati, l'utilizzo della CPU può raggiungere picchi dell'80-100 percento. In Windows 2000, Windows XP e Windows Server 2003, sono disponibili interfacce per le schede di rete che consentono l'accelerazione delle operazioni di crittografia IPSec a livello di hardware.

-   **Modalità di tunnel IPSec**. La modalità di tunnel IPSec viene tipicamente utilizzata per i tunnel VPN gateway-to-gateway tra indirizzi IP statici di gateway VPN. Questa modalità crea pertanto una nuova intestazione IP con un'intestazione IPSec. Il pacchetto originale con l'intestazione IP originale viene incapsulato per formare un pacchetto di tunnel. In uno scenario di isolamento dei server e dei domini, la modalità di tunnel può venire utilizzata per proteggere il traffico tra un server IP statico e un router in grado di supportare IPSec. Ciò può essere necessario nei casi in cui l'host di destinazione non supporti IPSec. Lo scenario della Woodgrove non richiedeva la modalità di tunnel.

Per ulteriori informazioni tecniche sulle modalità di trasporto e di tunnel IPSec, vedere la sezione "[Determining Your IPSec Needs](http://www.microsoft.com/resources/documentation/windowsserv/2003/all/deployguide/en-us/dnsbj_ips_wclw.asp)" nel capitolo "Deploying IPSec" del volume "Deploying Network Services" del *Windows Server 2003 Deployment Kit*, all'indirizzo www.microsoft.com/resources/documentation/
WindowsServ/2003/all/deployguide/
en-us/dnsbj\_ips\_wclw.asp.

##### Autorizzazione host

Dopo aver determinato che una comunicazione in ingresso proviene da un'origine verificabile, l'host deve decidere se consentire l'accesso al computer e all'utente di origine. Questo passaggio è importante perché il fatto che una periferica sia in grado di effettuare l'autenticazione non basta a garantire l'accesso a un determinato host.

Microsoft consiglia di progettare la soluzione perché utilizzi i gruppi standard di Windows per limitare le possibilità di accesso da parte di utenti e computer alle risorse presenti su altri computer. Questo metodo genera un nuovo livello di autorizzazione per gli account dei computer e gli account utente che utilizzano la rete e le applicazioni, basato sulle autorizzazioni di assegnazione dei diritti utente nei criteri locali dell'host a cui viene eseguito l'accesso. Utilizzando entrambe le assegnazioni dei diritti utente, "Accedi al computer dalla rete" (ALLOW) e "Nega accesso al computer dalla rete" (DENY), è possibile impedire a un computer o utente di accedere a una risorsa anche se condivide con essa gli stessi parametri dei criteri IPSec e l'utente connesso dispone del diritto di accesso alla risorsa. Questo ulteriore livello di controllo è essenziale per l'approccio all'isolamento descritto nella presente guida.

Tramite i privilegi di gruppo di Active Directory, è possibile organizzare i computer e gli utenti in modo tale da consentire l'assegnazione dei livelli di autorizzazione richiesti in modo gestibile e scalabile. Al fine di agevolare la distinzione tra i gruppi creati appositamente per ottenere l'autorizzazione all’accesso degli host e quelli a cui sono attribuite le autorizzazioni di accesso condiviso standard, in questa guida viene utilizzata l'espressione *gruppi di accesso di rete*.

Nella figura seguente, sono illustrati i principali passaggi del processo globale di autorizzazione di host e utenti previsto dalla soluzione.

[![](images/Dd536205.SGFG0202(it-it,TechNet.10).gif "Figura 2.2. Processo di autorizzazione di utenti e host")](https://technet.microsoft.com/it-it/dd536205.sgfg0202_big(it-it,technet.10).gif)

**Figura 2.2. Processo di autorizzazione di utenti e host**

Nella figura 2, è illustrato il processo descritto di seguito, costituito da cinque passaggi, che viene adottato per tutte le comunicazioni di rete dopo l'implementazione della soluzione di isolamento.

1.  **L'utente tenta di accedere alla condivisione su un server di reparto**. Un utente connesso al computer client tenta di accedere alla condivisione su un host attendibile all'interno della soluzione di isolamento logico. Ciò provoca il tentativo da parte del computer client di accedere all'host attendibile utilizzando il protocollo per la condivisione dei file, di solito SMB (Server Message Block), tramite la porta di destinazione TCP 445. Nell'ambito della soluzione, è stato assegnato al client un criterio IPSec. La richiesta di connessione TCP in uscita aziona una negoziazione IKE verso il server. Il client IKE ottiene un ticket Kerberos per autenticare il server.

2.  **Negoziazione in modalità principale IKE**. Dopo aver ricevuto l'iniziale richiesta di comunicazione IKE dal computer client, il server autentica il ticket Kerberos. Durante il processo di autenticazione, IKE verifica che il computer client disponga dei diritti di accesso host necessari, assegnati con i diritti utente ALLOW o DENY dei criteri di gruppo. Se il computer client dispone delle assegnazioni dei diritti utente necessarie, la negoziazione IKE viene completata e viene stabilita un'associazione di protezione in modalità principale IPSec.

3.  **Negoziazione del metodo di protezione IPSec**. Una volta completata la negoziazione IKE per la SA in modalità principale, vengono verificati i metodi di protezione del criterio IPSec per negoziare una connessione mediante i metodi di protezione per le SA IPSec accettabili da parte di entrambi gli host.

    Nel diagramma di flusso seguente, viene illustrato l'intero processo dai passaggi 2 e 3:

    [![](images/Dd536205.SGFG0203(it-it,TechNet.10).gif "Figura 2.3. Processo di verifica autorizzazioni di accesso ")](https://technet.microsoft.com/it-it/dd536205.sgfg0203_big(it-it,technet.10).gif)

    **Figura 2.3. Processo di verifica autorizzazioni di accesso host computer**

4.  **Verifica autorizzazioni di accesso host utente**. Una volta stabilita la comunicazione protetta con IPSec, il protocollo SMB autentica l'account dell'utente client. Sul server, viene verificata l'esistenza delle necessarie autorizzazioni di accesso host, assegnate con i diritti utente ALLOW o DENY dei criteri di gruppo dell'host attendibile, per l'account utente. Questo processo viene illustrato nel seguente diagramma di flusso:

    [![](images/Dd536205.SGFG0204(it-it,TechNet.10).gif "Figura 2.4. Processo di verifica autorizzazioni di accesso host utente")](https://technet.microsoft.com/it-it/dd536205.sgfg0204_big(it-it,technet.10).gif)

    **Figura 2.4. Processo di verifica autorizzazioni di accesso host utente**

    Se l'account dell'utente dispone delle assegnazioni dei diritti utente richieste, il processo è terminato e viene creato il token di accesso per l'utente. Al termine del processo, la soluzione di isolamento logico ha completato i controlli della protezione.

5.  **Controllo delle autorizzazioni di accesso ai file e condivisione**. Il server controlla infine le autorizzazioni di accesso ai file e condivisione standard di Windows per verificare che l'utente appartenga a un gruppo che possiede le autorizzazioni necessarie per accedere ai dati richiesti.

Utilizzando i gruppi di accesso di rete è possibile pervenire a un livello di controllo della soluzione molto alto.

La situazione seguente è un esempio pratico dei diversi passaggi compresi nella soluzione di isolamento logico.

Durante una riunione, un fornitore esterno collega il proprio computer portatile al punto di connessione di rete di una sala riunioni per copiare alcuni dati nella porzione condivisa del server delle risorse umane di un dipendente. Un'impiegata del reparto risorse umane fornisce al fornitore esterno il percorso della porzione condivisa del server delle risorse umane. Dato che il computer del fornitore esterno non è un host noto o attendibile, non viene gestito dal reparto IT e non si dispone di informazioni su quale sia il livello delle precauzioni di protezione adottate. Teoricamente, i file contenuti nel computer potrebbero contenere software dannoso che potrebbe infettare i computer interni. Quando il computer del fornitore esterno tenta la connessione al server delle risorse umane, il processo viene interrotto in corrispondenza del passaggio 2. I computer non sono in grado di negoziare una SA in modalità principale IKE in quanto il portatile non può fornire il ticket Kerberos richiesto per consentire la verifica delle sue credenziali; la periferica non appartiene a un dominio attendibile. I criteri IPSec per il gruppo di isolamento a cui appartiene il server delle risorse umane non consentono a quest'ultimo di comunicare con un host che non utilizzi a sua volta IPSec, pertanto, tutti i tentativi di comunicazione di questo computer considerato non attendibile vengono bloccati. In sintesi, la soluzione di isolamento logico consente di proteggere l'infrastruttura IT dal pericolo rappresentato da computer non attendibili e non gestiti, anche se tali computer sono in grado di accedere fisicamente alla rete interna.

In questo esempio, viene illustrato come raggiungere l'isolamento di un host alla volta. Un altro importante requisito della soluzione è riuscire a ottenere l'isolamento *con costi amministrativi ridotti*. È possibile raggruppare i computer in modo analogo agli utenti, quindi assegnare a tali gruppi i diritti utente ALLOW o DENY nei criteri locali dei diversi computer. Questo approccio risulta tuttavia di difficile gestione e poco scalabile in assenza delle capacità di centralizzazione offerte dai criteri di gruppo e Active Directory e di una comprensione approfondita dei percorsi di comunicazione richiesti. Inoltre, questo approccio non è in grado di assicurare da solo l'autenticazione avanzata o la crittografia dei dati. Combinando queste autorizzazioni di accesso host con IPSec e organizzando gli host in gruppi di isolamento, la comprensione delle relazioni tra i gruppi e la definizione dei percorsi di comunicazione (dopo una chiara documentazione dei requisiti) risultano semplificate. Per ulteriori informazioni sulla progettazione e il contesto dei gruppi di isolamento, vedere il capitolo 4, "Progettazione e pianificazione dei gruppi di isolamento".

[](#mainsection)[Inizio pagina](#mainsection)

### Da cosa protegge l'isolamento di server e domini?

L'isolamento dei server e dei domini consiste nel limitare le possibilità di comunicazione tra computer e con altre periferiche che tentano di stabilire comunicazioni. Tali limiti vengono utilizzati per descrivere un confine attorno alle comunicazioni in base al livello di trust delle varie periferiche. L'implementazione di limiti quali l'autenticazione, l'autorizzazione e la configurazione della rete attorno a un host mediante i criteri IPSec consente di ridurre efficacemente numerosi rischi. Sebbene IPSec non sia una strategia di protezione completa, viene tuttavia utilizzata come ulteriore livello di difesa nell'ambito di una strategia di protezione globale.

Nella sezione seguente vengono descritti i pericoli più comuni e si descrive brevemente la modellazione dei pericoli. Per ulteriori informazioni sulle periferiche attendibili nello scenario della Woodgrove Bank e sul processo di progettazione utilizzato dalla Woodgrove per identificare e classificare i computer, vedere la sezione "Determinazione dell'attendibilità" nel capitolo 3, "Determinazione dello stato corrente dell'infrastruttura IT".

#### Modellazione e classificazione dei pericoli

Negli ultimi anni, la frequenza e la complessità degli attacchi alle applicazioni e ai server collegati in rete è notevolmente aumentata. È interessante osservare come i tipi e gli stili degli attacchi e i metodi di base utilizzati per farvi fronte siano rimasti relativamente invariati. Tuttavia, alcune caratteristiche e metodi di implementazione di tali difese sono cambiati. Prima di poter procedere con la pianificazione richiesta per attuare l'isolamento dei server e dei domini, l'organizzazione deve condurre un'analisi dettagliata dei rischi relativi ai pericoli esistenti e dei metodi con cui è possibile contrastarli utilizzando diverse tecnologie e processi.

Nel corso degli anni, sono stati sviluppati vari processi in grado di identificare, classificare ed enumerare i pericoli. La documentazione relativa a tali processi spesso presenta una metodologia che è possibile utilizzare per la modellazione dei pericoli di natura aziendale, ambientale e tecnica di un'organizzazione. Microsoft adotta il metodo STRIDE per la modellazione dei pericoli. L'acronimo STRIDE riassume le varie categorie di pericoli, ovvero:

**S**    Spoofing (Spoofing o falsificazione)

**T**    Tampering (Manomissione)

**R**    Repudiation (Ripudio)

**I**    Information disclosure (Diffusione non autorizzata di informazioni)

**D**    Denial of service (Negazione del servizio)

**E**    Elevation of privilege (Aumento del livello dei privilegi)

È essenziale dedicare un impegno adeguato in termini di tempo e risorse alla definizione di un modello di pericolo il più dettagliato possibile al fine di assicurare la protezione di tutti i beni per i quali è richiesta. Per una descrizione dei pericoli e gli attacchi specifici che l'isolamento dei server e dei domini contribuisce a ridurre e contrastare, vedere l'appendice D, "Categorie di pericoli IT", della presente guida. Per una trattazione dettagliata dei modelli di pericolo, vedere il capitolo 2, "Defining the Security Landscape" della guida [*Microsoft Solution for Securing Windows 2000 Server*](http://www.microsoft.com/technet/security/prodtech/windows2000/secwin2k/default.mspx), disponibile per il download all'indirizzo www.microsoft.com/technet/security/prodtech/
win2000/secwin2k/02defsls.mspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Distribuzione dell'isolamento di server e domini

Dopo aver identificato i pericoli per l'organizzazione e in che modo possono venire ridotti adottando questa soluzione, è necessario esaminare la modalità di distribuzione della soluzione. In questa sezione viene descritto il processo di distribuzione proposto.

#### Raccolta di informazioni

La fase iniziale, precedente anche al processo di progettazione, consiste nel verificare di disporre di un quadro aggiornato e accurato dello stato attuale della rete aziendale, comprendente le configurazioni delle workstation e dei server, nonché i percorsi di comunicazione. Non è possibile sviluppare una soluzione di isolamento logico efficace in assenza di informazioni esatte su quali risorse debbano essere oggetto di protezione.

Il capitolo 3, "Determinazione dello stato corrente dell'infrastruttura IT", offre una spiegazione dettagliata sulla raccolta di informazioni circa lo stato attuale della rete e delle periferiche che contiene. Questo processo consente di ottenere tutte le informazioni richieste per procedere con i contenuti dei capitoli seguenti, oltre a fornire strumenti che incrementano il valore di altri progetti intrapresi dall'organizzazione. Il processo consente soprattutto all'organizzazione di analizzare ed esaminare attentamente i percorsi di comunicazione richiesti per i sistemi informatici e di pervenire a scelte informate in merito ad eventuali compromessi tra i rischi, i requisiti di comunicazione e i requisiti aziendali.

#### Panoramica del processo di distribuzione IPSec

Dopo la definizione e l'attuazione del progetto, la priorità successiva consiste nel determinare un processo per l'implementazione del progetto con una modalità gestibile e che comporti anche un impatto minimo sugli utenti. Nel capitolo 4, "Progettazione e pianificazione dei gruppi di isolamento", vengono discussi in dettaglio diversi approcci disponibili per raggiungere tale obiettivo. È tuttavia possibile riepilogare la procedura di base come segue:

1.  **Testare la progettazione e i criteri IPSec in un laboratorio di verifica funzionale**. I criteri IPSec proposti devono essere sottoposti a test in un ambiente non produttivo isolato, al fine di verificare che la soluzione funzioni nel modo previsto, testando eventuali problemi che potrebbero presentarsi a livello di impostazioni dei criteri o meccanismi di distribuzione.

2.  **Effettuare la distribuzione pilota del progetto testato e approvato**. Una volta che i test in laboratorio hanno confermato che il progetto funzionerà come previsto, la fase successiva del processo consiste nell'identificare un numero limitato di computer da includere in una distribuzione pilota della soluzione nell'ambiente di produzione. È necessario inoltre fornire un supporto preventivo ai computer e agli utenti identificati affinché gli eventuali problemi emersi in fase di test abbiano un impatto minimo sulle capacità degli utenti di eseguire i ruoli ad essi assegnati.

3.  **Implementare una distribuzione graduale della soluzione**. La fase finale del processo è pervenire a un piano da utilizzare per la distribuzione della soluzione al resto dell'organizzazione. Questa fase è piuttosto delicata e richiede un'attenta pianificazione dei diversi passaggi. Con un'unica variazione nelle impostazioni dei criteri IPSec, è infatti possibile elaborare un progetto di soluzione in grado di disabilitare l'accesso alle risorse di rete per la maggior parte dei computer. Il piano di distribuzione deve essere testato e organizzato affinché le modifiche introdotte dalla soluzione vengano implementate in modo da consentire un rapido ritorno allo stato corretto conosciuto nel caso in cui non sia stato rilevato un errore di configurazione o progettazione durante la fase di test.

Nel capitolo 4, "Progettazione e pianificazione dei gruppi di isolamento", viene discusso in dettaglio il processo di progettazione dei domini di isolamento e vengono illustrate le diverse opzioni di distribuzione graduale della soluzione.  

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

In questo capitolo sono stati presentati gli obiettivi e i processi alla base della soluzione descritta nella presente guida. Sebbene i vantaggi dell'implementazione di IPSec siano ormai noti ai professionisti IT già da diversi anni, molti di essi hanno evitato di utilizzare questa tecnologia in ragione della sua natura piuttosto complessa. L'implementazione di IPSec può comportare conseguenze gravi in assenza di una progettazione solida e completa, una buona pianificazione della distribuzione e una metodologia di test affidabile.

Le indicazioni fornite in questo capitolo sono state volte a chiarire come l'isolamento logico non sia altro che un ulteriore livello di protezione basato sull'utilizzo delle tecniche di isolamento dei server e dei domini insieme alle funzionalità della piattaforma Windows, di IPSec, dei Criteri di gruppo e di Active Directory, che permette di realizzare una soluzione aziendale, gestibile e scalabile, in grado di limitare al massimo i rischi a cui sono esposti i dati aziendali.

Le informazioni presentate negli altri capitoli sono incentrate sulle diverse fasi di una corretta pianificazione e implementazione della soluzione. Nel capitolo 6, "Gestione di un ambiente di isolamento del server e del dominio", vengono illustrate le procedure che consentono la gestione quotidiana di un ambiente operativo basato sull'isolamento dei server e dei domini. Nel capitolo 7, "Risoluzione dei problemi di IPSec", vengono fornite informazioni utili per il supporto e la risoluzione dei problemi della soluzione.

**Scarica la soluzione completa**

[Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=33947)

[](#mainsection)[Inizio pagina](#mainsection)
