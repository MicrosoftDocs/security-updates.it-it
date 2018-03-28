---
TOCTitle: 'Come supportare l''accesso con smart card per connessioni di accesso remoto VPN'
Title: 'Come supportare l''accesso con smart card per connessioni di accesso remoto VPN'
ms:assetid: '8a7bcb4b-3c92-4c44-a9aa-be5bb20e7c62'
ms:contentKeyID: 20213230
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc875840(v=TechNet.10)'
---

Come supportare l'accesso con smart card per connessioni di accesso remoto VPN
==============================================================================

##### In questa pagina

[](#edaa)[Introduzione](#edaa)
[](#ecaa)[Tecnologie delle smart card](#ecaa)
[](#ebaa)[Scenario di accesso con smart card per connessioni di accesso remoto VPN](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

I progressi compiuti nell'ambito della tecnologia per le telecomunicazioni, mossi dalla necessità di mantenere bassi i costi e rimanere allo stesso tempo competitivi in un mercato in continua espansione, richiedono alle organizzazioni non solo di mantenere attivi i canali di comunicazione 24 ore al giorno, sette giorni su sette ma anche di fornire la connettività ai dati aziendali e ai servizi da postazioni remote.

Internet offre alle organizzazioni e ai singoli utenti la possibilità di utilizzare i computer per comunicare e condividere i dati a livello mondiale. In questo modo sono garantiti una serie di vantaggi in ambito di accessibilità, scalabilità, prestazioni e riduzione dei costi aziendali. Tuttavia, Internet può rappresentare un ambiente non del tutto sicuro e potenzialmente ostile per le organizzazioni. L'obiettivo delle organizzazioni è quello di sfruttare al meglio tutti i vantaggi che offre Internet, mantenendo allo stesso tempo i necessari livelli di protezione sia per i dati che per le comunicazioni.

Le reti VPN (Virtual Private Network) consentono alle organizzazioni di utilizzare Internet e allo stesso tempo di limitare l'esposizione dei dati e dei canali di comunicazione. A tale scopo è disponibile una serie di funzioni di protezione, tra cui meccanismi di autenticazione e di crittografia affidabili.

#### Destinatari della guida

Tra i destinatari di questa sono inclusi i professionisti IT (Information Technology) che sono responsabili della distribuzione dei servizi VPN nei relativi ambienti di rete.

Le informazioni contenute in questa guida sono valide per le organizzazioni di piccole e medie dimensioni che devono garantire un accesso remoto affidabile alle proprie reti.

#### Panoramica

Quando si configura l'accesso remoto VPN alle risorse di rete, è possibile utilizzare lo stesso set di credenziali utilizzato per accedere alla rete quando ci si trova nel proprio posto di lavoro, ovvero un nome utente e una password. Tuttavia, questa potrebbe non essere la soluzione più sicura. Ad esempio, i biglietti da visita o la documentazione aziendale spesso contiene i nomi utente. Le credenziali potrebbero essere soggette ad attacchi di tipo "trial and error". Se terze parti dovessero entrare in possesso del nome utente, la password rimarrebbe l'unico meccanismo di protezione della rete aziendale.

Le password possono rappresentare controlli di protezione efficaci. Una password di grandi dimensioni, contenente lettere e numeri casuali oltre a caratteri speciali può essere molto difficile da riprodurre. Inoltre, le passphrase garantiscono una maggiore protezione rispetto alle singole password.

Sfortunatamente, gli utenti non possono sempre ricordare password complesse e pertanto dovranno essere annotate da qualche parte. Quando non vi sono limiti alla complessità delle password, gli utenti tendono a creare password facili da ricordare e pertanto facili da indovinare.

Le soluzioni nome utente e password vengono chiamate a fattore singolo poiché per accedere alla rete l'utente utilizza un solo elemento noto solo all'utente stesso. I sistemi di autenticazione a più fattori risolvono i problemi relativi all'autenticazione a fattore singolo poiché in essi viene utilizzata una combinazione di requisiti, tra cui:

-   Qualcosa noto solo all'utente, ad esempio una password o un PIN (Personal Identification Number).

-   Qualcosa in possesso dell'utente possiede, ad esempio un token hardware o una smart card.

-   Qualcosa di assolutamente univoco per l'utente, ad esempio un'impronta digitale o la scansione della retina.

Le smart card e i relativi PIN associati rappresentano la forma più diffusa, affidabile ed economica di autenticazione a due fattori. Gli utenti devono infatti disporre delle proprie smart card e conoscere i relativi PIN per accedere alle risorse di rete. L'autenticazione a due fattori riduce in modo significativo la probabilità di accessi non autorizzati alla rete aziendale.

#### Vantaggi delle VPN

Quando l'organizzazione deve connettersi a reti contenenti informazioni riservate ed esclusive dell'azienda, i livelli di connettività raggiunti espongono a un rischio di protezione notevole.

Nell'ambiente potenzialmente ostile di Internet, le soluzioni VPN assumono un ruolo fondamentale poiché consentono tra l'altro di mantenere la protezione relativamente a un'infrastruttura di rete privata. Le soluzioni VPN garantiscono la protezione poiché utilizzano connessioni a tunnel protetto, la crittografia dei dati e consentono l'accesso alla rete aziendale solo agli utenti autenticati.

Le reti VPN supportano un'ampia gamma di metodi di autenticazione, protocolli di tunneling e tecnologie di crittografia per garantire la protezione dei dati aziendali.

I metodi di autenticazione VPN includono:

-   Protocollo PAP (Password Authentication Protocol).

-   Protocollo CHAP (Challenge Handshake Authentication Protocol).

-   Protocollo MS-CHAP (Microsoft Challenge Handshake Authentication Protocol).

-   MS-CHAP versione 2 (MS-CHAP v2).

-   Protocollo EAP (Extensible Authentication Protocol).

I protocolli di tunneling VPN includono:

-   Protocollo PPTP (Point-to-Point Tunneling Protocol).

-   Protocollo L2TP (Layer 2 Tunneling Protocol).

I protocolli di crittografia VPN includono:

-   MPPE (Microsoft Point-to-Point Encryption).

-   IPsec (IP Security).

Per supportare l'ampia gamma di sistemi operativi Microsoft, utilizzare una versione dei protocolli MS-CHAP, PPTP e MPPE.

Se si utilizza Microsoft Windows 2000 o versioni successive, è possibile garantire maggiori livelli di protezione utilizzando i protocolli EAP, L2TP e IPsec.

Per ulteriori informazioni sull'autenticazione VPN, il tunneling e la crittografia, vedere il white paper [Virtual Private Networking: An Overview](http://www.microsoft.com/technet/prodtechnol/windows2000serv/plan/vpnoverview.mspx) (in inglese) sul sito Web Microsoft TechNet all'indirizzo www.microsoft.com/technet/prodtechnol/windows2000serv/plan/vpnoverview.mspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Tecnologie delle smart card

Le smart card consentono l'autenticazione a due fattori. L'autenticazione a due fattori va oltre la semplice combinazione di nome utente e password e richiede all'utente di presentare un token univoco abbinato a un PIN.

Le smart card sono tessere in materiale plastico (simili a carte di credito) che contengono un microcomputer e una piccola quantità di memoria. Sono in grado di memorizzare chiavi private e certificati di protezione X.509 al riparo da possibili intrusioni.

Per eseguire l'autenticazione a un computer o su una connessione ad accesso remoto, l'utente deve inserire la smart card in un apposito lettore e immettere il proprio PIN. L'utente non può ottenere l'accesso utilizzando solo il PIN o solo la smart card. Gli attacchi di tipo "brute-force" nei confronti dei PIN delle smart card non sono possibili poiché è previsto il blocco delle smart card dopo ripetuti tentativi di accesso inserendo PIN errati.

Con le smart card è possibile eseguire sistemi operativi incorporati e un tipo di file system nel quale è possibile archiviare i dati. Il sistema operativo delle smart card deve essere in grado di eseguire quanto segue:

-   Archiviare le chiavi pubbliche e private dell'utente

-   Archiviare un certificato con chiave pubblica

-   Recuperare il certificato con chiave pubblica

-   Eseguire operazioni con chiave privata per conto dell'utente

Per ulteriori informazioni sulle smart card e per un elenco dei lettori di smart card supportati da Microsoft, vedere l'argomento [Smart Cards](http://www.microsoft.com/technet/security/topics/identitymanagement/scard.mspx) (in inglese) sul sito Web Microsoft TechNet all'indirizzo www.microsoft.com/technet/security/topics/identitymanagement/scard.mspx.

#### Requisiti di distribuzione delle smart card

Per supportare l'accesso con smart card per reti VPN ad accesso remoto, sono necessari specifici componenti hardware e software sul computer.

Per ulteriori informazioni sulle specifiche e sui requisiti per la distribuzione delle smart card, vedere l'argomento [*Secure Access Using Smart Cards Planning Guide*](http://www.microsoft.com/technet/security/topics/networksecurity/securesmartcards/default.mspx) (in inglese) sul sito Web Microsoft TechNet all'indirizzo www.microsoft.com/technet/security/topics/networksecurity/securesmartcards/
default.mspx.

##### Requisiti hardware del client per le smart card

Per supportare la soluzione VPN per smart card, gli utenti devono essere in possesso di un computer client in grado di eseguire Windows XP.

Inoltre, gli utenti hanno bisogno di un lettore per smart card associato a un'interfaccia standard per periferiche, ad esempio un'interfaccia seriale RS-232, PS/2, PC Card o USB (Universal Serial Bus).

##### Requisiti software del client per le smart card

I client di accesso remoto richiedono il sistema operativo Windows XP per supportare la soluzione VPN per smart card. Inoltre, si consiglia l'installazione del Service Pack 2 (SP2).

Ogni computer client richiederà l'installazione di un CSP (Cryptographic Service Provider) in grado di supportare la smart card scelta. Windows XP include un CSP che supporta una serie di soluzioni per smart card. In alternativa, sarà il fornitore della soluzione per smart a fornire un CSP. Il CSP svolge le seguenti funzioni:

-   Funzioni di crittografia, inclusa la firma digitale

-   Gestione della chiave privata

-   Comunicazioni protette tra il lettore di smart card del computer client e la smart card

In ogni computer client è necessario installare lo specifico driver di periferica del lettore di smart card. I driver di periferica associano la funzionalità del lettore di smart card ai servizi nativi forniti da Windows XP e all'infrastruttura delle smart card. Il driver di periferica del lettore comunica gli eventi di inserimento e rimozione della smart card e offre funzionalità per la comunicazione dei dati verso e dalla smart card.

Connection Manager è una funzionalità standard di Windows XP che facilita e gestisce le connessioni di rete, la connessione remota e le connessioni VPN. Inoltre, è possibile utilizzare il CMAK (Connection Manager Administration Kit) per personalizzare i profili di Connection Manager e creare un file di installazione che configura automaticamente la connessione VPN, di cui avviene la distribuzione ai client.

La distribuzione delle smart card può includere il software di gestione delle smart card sul client. Il software include strumenti di gestione delle smart card, di connettività e di protezione che consentono di vedere il contenuto delle smart card, reimpostare i PIN e aggiungere certificati.

##### Requisiti hardware del server VPN

Le connessioni VPN aggiungono un ulteriore carico di lavoro al processore del server di accesso remoto. L'accesso protetto con smart card non aggrava ulteriormente tale carico. I server di accesso remoto VPN che si occupano di volumi elevati di connessioni in ingresso, richiedono processori veloci, preferibilmente con una configurazione di tipo multiprocessore, oltre al supporto per elevate velocità di rete. Le organizzazioni che utilizzano le VPN protette con IPsec possono implementare le schede di rete che eseguono l'offload del processo di crittografia IPsec su un processore separato presente sulla scheda di rete.

##### Requisiti software del server VPN

I requisiti software del server VPN per l'accesso con smart card sono relativamente chiari. I server di accesso remoto devono eseguire Windows 2000 Server o versioni successive, devono avere il servizio Routing e Accesso remoto abilitato e devono supportare il protocollo EAP-TLS (Extensible Authentication Protocol-Transport Layer Security).

Il protocollo EAP-TLS è un meccanismo di autenticazione reciproca sviluppato per essere utilizzato insieme ai dispositivi di protezione, ad esempio le smart card e i token hardware. EAP-TLS supporta i protocolli PPP (Point-to-Point Protocol) e le connessioni VPN e consente lo scambio di chiavi segrete condivise per la crittografia MPPE, oltre al protocollo IPsec.

Il vantaggio principale nell'utilizzo del protocollo EAP-TLS è rappresentato dalla sua resistenza agli attacchi di tipo "brute-force" e il supporto per l'autenticazione reciproca. Con l'autenticazione reciproca, il client e il server sono tenuti a dimostrare la loro identità. Se il client o il server non invia un certificato per la convalida dell'identità, la connessione viene interrotta.

Microsoft Windows Server 2003 supporta il protocollo EAP-TLS per le connessioni remote e VPN, che consente l'utilizzo delle smart card agli utenti remoti. Per ulteriori informazioni sul protocollo EAP-TLS, vedere l'argomento [Extensible Authentication Protocol (EAP)](http://technet.microsoft.com/en-us/network/bb643147.aspx) (in inglese) all'indirizzo http://technet.microsoft.com/en-us/network/bb643147.aspx.

Per ulteriori informazioni sui requisiti del certificato EAP, vedere l'articolo della Microsoft Knowledge Base "[Certificate Requirements when you use EAP-TLS or PEAP with EAP-TLS](http://support.microsoft.com/default.aspx?scid=814394)" (in inglese) all'indirizzo http://support.microsoft.com/default.aspx?scid=814394.

#### Prerequisiti dell'infrastruttura di rete per la distribuzione delle smart card

Le smart card richiedono un'infrastruttura adatta supportata dal sistema operativo e dagli elementi di rete. Prima di iniziare il processo di distribuzione delle smart card, è necessario che per i seguenti componenti vengano soddisfatti specifici requisiti:

-   Requisiti dell'utente

-   PKI (Public Key Infrastructure)

-   Modelli di certificato

-   Servizio Active Directory

-   Gruppi di protezione

-   Stazioni e agenti di registrazione

##### Requisiti dell'utente

L'identificazione degli utenti e dei gruppi che richiedono l'accesso VPN rappresenta una parte importante del processo di distribuzione delle smart card. Identificare subito questi account nel processo per definire l'ambito del progetto e controllare i costi.

##### PKI (Public Key Infrastructure)

Le soluzioni per smart card richiedono un'infrastruttura PKI per associare ai certificati le coppie di chiavi pubbliche/private che consentono il mapping dell'account in Active Directory. L'infrastruttura PKI può essere implementata utilizzando uno dei due metodi riportati di seguito: fornendo l'infrastruttura interna dei certificati a un'organizzazione esterna oppure utilizzando i Servizi certificati in Windows Server 2003. Per utilizzare i Servizi certificati in Windows Server 2003 per la soluzione per smart card, l'Autorità di certificazione (CA) deve essere di tipo aziendale, che richiede l'utilizzo di Active Directory.

Per ulteriori informazioni sui Servizi certificati in Windows Server 2003, visitare il sito Web [Public Key Infrastructure for Windows Server 2003](http://www.microsoft.com/windowsserver2003/technologies/pki/default.mspx) (in inglese) all'indirizzo www.microsoft.com/windowsserver2003/technologies/pki/default.mspx.

L'infrastruttura PKI deve avere un meccanismo che si occupa della revoca dei certificati. La revoca è necessaria alla scadenza del certificato oppure quando un utente malintenzionato può averne compromessa l'affidabilità. Con la revoca di un certificato, un amministratore nega l'accesso a chiunque utilizzi il certificato. Ogni certificato include l'ubicazione del proprio elenco di revoche di certificati, denominato CRL (Certificate Revocation List).

Per ulteriori informazioni su come gestire la revoca dei certificati, vedere l'argomento [Manage Certificate Revocation](http://technet2.microsoft.com/windowsserver/en/library/92a5e655-3eb2-4843-b9cb-58c84c0a91d61033.mspx?mfr=true) (in inglese) sul sito Web Microsoft TechNet all'indirizzo http://technet2.microsoft.com/WindowsServer/en/library/92a5e655-3eb2-4843-b9cb-58c84c0a91d61033.mspx?mfr=true.

Utilizzare la PKI per assegnare un certificato a ogni smart card nella propria soluzione VPN. Il certificato deve essere emesso da un'Autorità di certificazione che il server VPN ritiene affidabile. Se si utilizza Servizi certificati in Windows Server 2003, installare il certificato radice PKI sul server VPN.

Per l'autenticazione reciproca, è necessario assegnare un certificato al server VPN da un'Autorità di certificazione che il client ritiene affidabile. Se si utilizza Servizi certificati in Windows Server 2003, installare il certificato radice PKI sul client VPN.

##### Modelli di certificato

Windows Server 2003 fornisce modelli di certificato specifici per l'emissione di certificati digitali da utilizzare nelle smart card. I tre modelli di certificati per le smart card sono elencati di seguito:

-   Agente di registrazione, che consente la richiesta di certificati per altri utenti da parte di un utente autorizzato.

-   Utente con smart card, che consente all'utente di connettersi mediante una smart card e di firmare la posta elettronica. Fornisce anche l'autenticazione del client.

-   Accesso con smart card, che permette all'utente di accedere mediante una smart card e fornisce l'autenticazione del client, ma non consente la firma della posta elettronica.

**Nota**   Microsoft raccomanda di aggiornare le PKI attuali di Windows Server 2003 a Windows Server 2003 con Service Pack 1 (SP1) in modo da sfruttare le nuove e migliorate funzionalità di protezione.

La soluzione VPN richiederà almeno un amministratore con un certificato dell'agente di registrazione che assegna i certificati alle smart card. Inoltre, i client richiederanno i certificati per l'accesso con smart card sulle relative smart card.

Per ulteriori informazioni sui modelli di certificato, vedere l'argomento [Certificate Templates](http://technet2.microsoft.com/windowsserver/en/library/7d82b420-10ef-4f20-a56f-17ee7ee352d21033.mspx?mfr=true) (in inglese) sul sito Web Microsoft TechNet all'indirizzo http://technet2.microsoft.com/WindowsServer/en/Library/7d82b420-10ef-4f20-a56f-17ee7ee352d21033.mspx?mfr=true.

##### Active Directory

Active Directory consente di gestire le identità e le relazioni che costituiscono gli ambienti di rete e rappresenta un componente chiave per l'implementazione delle soluzioni per le smart card. Active Directory in Windows Server 2003 dispone del supporto incorporato per rendere effettivo l'accesso interattivo con smart card ed è in grado di eseguire il mapping degli account ai certificati. Questa funzionalità di mapping degli account utente ai certificati collega la chiave privata presente sulla smart card con il certificato presente in Active Directory.

Quando l'agente di registrazione assegna un certificato a una smart card per uno specifico utente, il processo esegue il mapping del certificato relativamente all'account utente in Active Directory. La presentazione delle credenziali di smart card durante l'accesso richiede che Active Directory stabilisca una corrispondenza tra una smart card specifica e un unico account utente, cosa che fornisce all'utente le necessarie autorizzazioni e capacità sulla rete.

Per ulteriori informazioni sul mapping dei certificati, vedere l'argomento [Map certificates to user accounts](http://technet.microsoft.com/en-us/library/cc736706.aspx) (in inglese) sul sito Web Microsoft TechNet all'indirizzo www.microsoft.com/resources/documentation/WindowsServ/2003/all/deployguide/en-us/dssch\_pki\_cyek.asp.

Per ulteriori informazioni su Active Directory, vedere la pagina [Windows Server 2003 Active Directory](http://www.microsoft.com/windowsserver2003/technologies/directory/activedirectory/default.mspx) (in inglese) all'indirizzo www.microsoft.com/windowsserver2003/technologies/directory/activedirectory/
default.mspx.

##### Gruppi di protezione

Il processo di distribuzione e gestione delle smart card risulta molto più semplice se gli utenti vengono organizzati in gruppi di protezione in Active Directory. Ad esempio, una tipica distribuzione di smart card può richiedere la creazione dei seguenti gruppi di protezione:

-   **Agenti di registrazione smart card**. Questo gruppo è responsabile della distribuzione delle smart card agli utenti.

-   **Gestione temporanea di smart card**. Questo gruppo contiene tutti gli utenti autorizzati a ricevere una smart card, ma le cui smart card non sono ancora state registrate e attivate da un agente di registrazione.

-   **Utenti con smart card**. Questo gruppo contiene tutti gli utenti che hanno completato il processo di registrazione e che dispongono di una smart card attiva. L'agente di registrazione provvede a spostare gli utenti dal gruppo di gestione temporanea delle smart card al gruppo di utenti con smart card.

-   **Eccezioni temporanee delle smart card**. Questo gruppo contiene gli utenti che necessitano di eccezioni temporanee ai requisiti delle smart card, ad esempio in caso di smarrimento o dimenticanza della propria smart card.

-   **Eccezioni permanenti delle smart card**. Questo gruppo include gli account che necessitano di eccezioni permanenti ai requisiti di accesso con smart card.

Quanto meno, la soluzione VPN richiederà gruppi per agenti di registrazione e per utenti con smart card. La creazione di questi gruppi consente di gestire e configurare più utenti in modo più semplice.

##### Stazioni e agenti di registrazione

Per emettere le smart card o registrare gli utenti, è possibile utilizzare un'interfaccia basata sul Web, tuttavia questo non è il metodo consigliato. Poiché gli utenti devono immettere il proprio nome utente e la password per ottenere le smart card, questa soluzione riduce sensibilmente il livello di protezione offerto dalle smart card in quanto questo è pari al livello di protezione delle credenziali immesse nell'interfaccia Web. La soluzione consigliata è quella di creare stazioni di registrazione e di definire uno o più amministratori come agenti di registrazione.

Una stazione di registrazione tipica è costituita da un computer cui sono collegati un lettore e uno scrittore di smart card. Il lettore consente l'accesso dell'agente di registrazione e lo scrittore rilascia nuove smart card per l'utente. La stazione di registrazione ha un'impostazione dei criteri di gruppo che forza la disconnessione non appena l'agente di registrazione rimuove la propria smart card dal lettore.

L'amministratore designato svolge il ruolo di agente di registrazione e utilizza la propria smart card per accedere alla stazione di registrazione. Successivamente, apre la pagina Web dei Servizi certificati, verifica l'identità dell'utente, lo registra e rilascia la smart card registrata. Gli agenti di registrazione richiedono un certificato dell'agente di registrazione e devono disporre delle autorizzazioni per accedere ai modelli di certificato.

#### Considerazioni operative

La soluzione VPN per smart card deve permettere il monitoraggio del funzionamento della soluzione. Gli strumenti di monitoraggio devono mostrare le informazioni necessarie da fornire al supporto operativo. Se la soluzione non soddisfa questo requisito, il personale addetto alla protezione non può determinare se la soluzione sia effettivamente in grado di garantire la protezione delle connessioni di accesso remoto.

Le considerazioni operative includono:

-   **Verificare l'autenticazione nelle applicazioni interne**. Una smart card dovrebbe agire unicamente sull'accesso iniziale. Il programma pilota dovrebbe testare e verificare il funzionamento dell'autenticazione nelle applicazioni interne.

-   **Risolvere i problemi dei client remoti**. Per risolvere i problemi dei client potrebbe essere necessaria la stretta collaborazione di più team che potrebbero essere situati in zone con fusi orari diversi. Test rigorosi e un'implementazione adeguata dei progetti pilota contribuiscono a ridurre le richieste di supporto.

-   **Comprendere gli scenari e le minacce associati all'accesso remoto all'organizzazione**. È necessario comprendere gli scenari di accesso remoto e le minacce alla protezione dell'organizzazione e trovare un equilibrio. È opportuno assegnare la priorità ai beni che richiedono la protezione maggiore. La decisione che riguarda il giusto equilibrio tra i costi e i rischi è strategica e deve essere presa dai dirigenti di più alto livello.

-   **Anticipare le difficoltà tecniche**. È opportuno anticipare le difficoltà tecniche, come le routine di installazione e la distribuzione degli strumenti di gestione delle smart card. Potrebbe essere necessario integrare la soluzione basata sulle smart card negli strumenti di gestione dell'azienda esistenti.

-   **Monitorare e gestire i problemi delle prestazioni**. È necessario monitorare e gestire i problemi delle prestazioni e stabilire in anticipo le aspettative degli utenti sulla distribuzione.

-   **Considerare la presenza dei beni personali**. Ricordare che i computer di casa dei dipendenti sono di loro proprietà e non vengono gestiti dal reparto IT dell'azienda. Se un dipendente non desidera o non è in grado di installare l'hardware e il software necessari per supportare l'accesso remoto protetto con le smart card è possibile vagliare altre possibilità. Ad esempio, Microsoft Outlook Web Access fornisce ai dipendenti l'accesso protetto alla propria cassetta postale di Microsoft Exchange Server tramite connessioni crittografate SSL (Secure Socket Layer).

    Per ulteriori informazioni sulla protezione della posta elettronica, vedere "[Come proteggere la riservatezza della posta elettronica nei settori soggetti a normative](http://technet.microsoft.com/it-it/library/cc875813.aspx)" all'indirizzo http://technet.microsoft.com/it-it/library/cc875813.aspx.

-   **Gestire le modifiche alla soluzione**. È necessario gestire le eventuali modifiche e gli sviluppi alla soluzione ricorrendo a processi simili a quelli necessari per la distribuzione iniziale.

-   **Ottimizzare la soluzione**. Tutti gli aspetti della soluzione basata sulle smart card richiedono un esame e un'ottimizzazione periodici. A scadenza regolare, è necessario esaminare i processi di registrazione e le esigenze di eccezioni degli account con l'obiettivo di incrementare la sicurezza e l'integrità.

[](#mainsection)[Inizio pagina](#mainsection)

### Scenario di accesso con smart card per connessioni di accesso remoto VPN

Il processo illustrato in questa sezione per la configurazione dell'accesso con smart card per connessioni di accesso remoto VPN fa riferimento a scenari che riguardano piccole o medie imprese. La figura seguente mostra una rete aziendale di medie dimensioni. Nel proprio ambiente è possibile disporre solo di alcuni o di tutti i servizi mostrati.

![](images/Cc875840.SCLVPN01(it-it,TechNet.10).gif "Figura 1. Accesso remoto nell'ambiente IT di medie dimensioni")

**Figura 1. Accesso remoto nell'ambiente IT di medie dimensioni**

In modo specifico, questo processo riguarda scenari in cui gli utenti remoti richiedono l'accesso ai dati e ai servizi aziendali da ubicazioni esterne. Per ottenere questo tipo di accesso, gli utenti remoti creano una connessione VPN a un server VPN di Windows Server 2003 e per l'autenticazione vengono utilizzate le smart card.

Le procedure seguenti consentono di preparare, sviluppare e configurare il supporto per smart card per le VPN di accesso remoto.

#### Come preparare un'Autorità di certificazione per l'emissione dei certificati smart card

Innanzitutto, è necessario preparare l'Autorità di certificazione all'assegnazione dei certificati necessari, ovvero il certificato dell'agente di registrazione e il certificato per l'accesso con smart card.

**Per preparare l'Autorità di certificazione all'emissione dei certificati smart card**

1.  Accedere con i diritti di amministratore.

2.  Aprire la schermata **Siti e servizi di Active Directory**.

3.  Scegliere il menu **Visualizza**, quindi selezionare **Mostra nodo servizi**.

4.  Espandere **Servizi**, scegliere **Servizi chiave pubblica**, quindi **Modelli di certificato** (mostrato nella schermata seguente).

    [![](images/Cc875840.SCLVPN02(it-it,TechNet.10).gif "Siti e servizi di Active Directory")](https://technet.microsoft.com/it-it/cc875840.sclvpn02_big(it-it,technet.10).gif)

5.  Fare clic con il pulsante destro del mouse sul modello di certificato **EnrollmentAgent**, quindi selezionare **Proprietà**.

6.  Aggiungere il gruppo di protezione per gli agenti di registrazione creati come parte dei prerequisiti di distribuzione e assegnare le autorizzazioni di **lettura** e **registrazione** (mostrato nella schermata seguente). Quindi, fare clic su **OK**.

    [![](images/Cc875840.SCLVPN03(it-it,TechNet.10).gif "Siti e servizi di Active Directory")](https://technet.microsoft.com/it-it/cc875840.sclvpn03_big(it-it,technet.10).gif)&gt;

7.  Chiudere la schermata **Siti e servizi di Active Directory**.

8.  Aprire la schermata **Autorità di certificazione**.

9.  Espandere il nome del server e selezionare **Modelli di certificato**. Nel riquadro destro, è possibile vedere l'elenco dei certificati che l'Autorità di certificazione può assegnare (mostrato nella schermata seguente).

    [![](images/Cc875840.SCLVPN04(it-it,TechNet.10).gif "Autorità di certificazione")](https://technet.microsoft.com/it-it/cc875840.sclvpn04_big(it-it,technet.10).gif)

10. Fare clic con il pulsante destro del mouse su **Modelli di certificato**, scegliere **Nuovo**, quindi selezionare **Modello di certificato da emettere**.

11. Tenere premuto il tasto CTRL e, nell'elenco **Attivazione modelli di certificato**, selezionare **Agente di registrazione** e **Accesso con smartcard** (mostrato nella schermata seguente). Quindi, fare clic su **OK**.

    [![](images/Cc875840.SCLVPN05(it-it,TechNet.10).gif "Attivazione modelli di certificato")](https://technet.microsoft.com/it-it/cc875840.sclvpn05_big(it-it,technet.10).gif)

12. Chiudere la schermata **Autorità di certificazione**.

#### Come distribuire i certificati alle smart card

È ora possibile assegnare i certificati alle smart card per gli utenti remoti. Accedere come agente di registrazione per il dominio in cui si trova l'account dell'utente.

**Per distribuire i certificati alle smart card**

1.  Aprire Microsoft Internet Explorer.

2.  Nella barra degli indirizzi digitare l'indirizzo dell'Autorità di certificazione che emette i certificati per l'accesso con smart card e premere INVIO.

3.  Scegliere **Richiedi un certificato**, quindi selezionare **Richiesta avanzata di certificati**. Viene visualizzata una schermata simile alla seguente.

    [![](images/Cc875840.SCLVPN06(it-it,TechNet.10).gif "Servizi certificati Microsoft")](https://technet.microsoft.com/it-it/cc875840.sclvpn06_big(it-it,technet.10).gif)

4.  Scegliere **Richiedere un certificato per una smart card per conto di un altro utente utilizzando la stazione di registrazione certificato smart card**. Se viene richiesto di accettare un controllo Microsoft ActiveX, scegliere **Sì**. È necessario abilitare l'uso dei controlli ActiveX in Internet Explorer.

5.  Nella schermata **Stazione di registrazione certificati smart card** (mostrata nella schermata seguente), selezionare **Accesso con smartcard**. Inoltre, è possibile vedere i nomi dell'**Autorità di certificazione**, del **provider del servizio di crittografia** e del **certificato di firma dell'amministratore**. Se non è possibile selezionare un certificato di firma dell'amministratore, significa che all'utente che ha eseguito l'accesso non è stato assegnato un certificato dell'agente di registrazione.

    [![](images/Cc875840.SCLVPN07(it-it,TechNet.10).gif "Stazione di registrazione di Smart Card Microsoft")](https://technet.microsoft.com/it-it/cc875840.sclvpn07_big(it-it,technet.10).gif)

6.  Dall'elenco a discesa **Autorità di certificazione**, selezionare il nome dell'Autorità di certificazione che si desidera emetta il certificato smart card.

7.  Dall'elenco a discesa **Provider del servizio di crittografia**, selezionare il produttore della smart card.

8.  In **Certificato di firma dell'amministratore**, digitare il nome del certificato dell'agente di registrazione che firmerà la richiesta di registrazione oppure scegliere **Selezione certificato** per selezionare un nome.

9.  Scegliere **Seleziona utente**, quindi selezionare l'account utente appropriato. Scegliere **Registrazione**.

10. Quando richiesto, inserire la smart card nel lettore del computer e fare clic su **OK**. Quando richiesto, digitare il PIN per la smart card.

#### Come configurare i server VPN per l'autenticazione con smart card

È ora possibile configurare il server VPN.

**Per configurare il servizio Routing e Accesso remoto per accettare l'autenticazione EAP**

1.  Avviare lo snap-in Routing e Accesso remoto.

2.  Fare clic con il pulsante destro del mouse su ***&lt;nomeserver&gt;***, scegliere **Proprietà**, quindi selezionare la scheda **Protezione**.

3.  Scegliere **Metodi di autenticazione**.

4.  Selezionare la casella di controllo **EAP (Extensible authentication protocol)** (mostrata nella schermata seguente), quindi fare clic su **OK**.

    [![](images/Cc875840.SCLVPN08(it-it,TechNet.10).gif "Proprietà DCI (locale)")](https://technet.microsoft.com/it-it/cc875840.sclvpn08_big(it-it,technet.10).gif)

5.  Fare clic su **OK**.

#### Come configurare i criteri di accesso remoto per l'autenticazione con smart card

È ora possibile abilitare EAP nei criteri di accesso remoto. Per impostazione predefinita il componente Criteri di accesso remoto è incluso nello snap-in Routing e Accesso remoto. Tuttavia, se è installato il servizio IAS (Internet Authentication Service), conosciuto anche come RADIUS (Remote Authentication Dial-in User Service), il componente Criteri di accesso remoto è incluso con lo snap-in IAS.

**Per abilitare EAP con i criteri di accesso remoto**

1.  Nel riquadro sinistro di Routing e Accesso remoto, scegliere **Criteri di accesso remoto**.

2.  Nel riquadro destro, fare doppio clic su **Connessioni al server Routing e Accesso remoto Microsoft**. Viene visualizzata una schermata simile alla seguente.

    [![](images/Cc875840.SCLVPN09(it-it,TechNet.10).gif "Connessione al server Routing e Accesso remoto Microsoft")](https://technet.microsoft.com/it-it/cc875840.sclvpn09_big(it-it,technet.10).gif)

3.  Scegliere **Modifica profilo**, la scheda **Autenticazione**, quindi selezionare **Metodi EAP** (mostrato nella schermata seguente).

    [![](images/Cc875840.SCLVPN10(it-it,TechNet.10).gif "Modifica profilo chiamate in ingresso")](https://technet.microsoft.com/it-it/cc875840.sclvpn10_big(it-it,technet.10).gif)

4.  Se **Smart Card o altro certificato** non è presente nell'elenco **Tipi di EAP**, come mostrato nella schermata seguente, scegliere **Aggiungi**, selezionare **Smart Card o altro certificato**, quindi fare clic su **OK**.

    [![](images/Cc875840.SCLVPN11(it-it,TechNet.10).gif "Selezione provider EAP")](https://technet.microsoft.com/it-it/cc875840.sclvpn11_big(it-it,technet.10).gif)

5.  Selezionare **Smart Card o altro certificato**, quindi scegliere **Modifica**. Viene visualizzata una schermata simile alla seguente.

    [![](images/Cc875840.SCLVPN12(it-it,TechNet.10).gif "Proprietà smart card o altro certificato")](https://technet.microsoft.com/it-it/cc875840.sclvpn12_big(it-it,technet.10).gif)

6.  Dall'elenco a discesa, selezionare il certificato da utilizzare per l'autenticazione EAP, quindi fare clic tre volte su **OK**.

7.  Verificare che l'opzione **Consenti l'accesso remoto** sia selezionata, fare clic su **OK** e chiudere la schermata Routing e Accesso remoto.

#### Come configurare i client VPN per l'autenticazione con smart card

A questo punto, configurare il client per l'uso dell'autenticazione EAP per supportare le smart card.

**Per creare una voce della rubrica**

1.  Fare clic su **Start**, scegliere **Connetti a**, **Mostra tutte le connessioni**, quindi nell'elenco **Operazioni di rete**, scegliere **Crea una nuova connessione**. Scegliere **Avanti** nella schermata iniziale di **Creazione guidata nuova connessione**. Viene visualizzata la schermata seguente.

    [![](images/Cc875840.SCLVPN13(it-it,TechNet.10).gif "Creazione guidata nuova connessione")](https://technet.microsoft.com/it-it/cc875840.sclvpn13_big(it-it,technet.10).gif)

2.  Selezionare **Connessione alla rete aziendale**, quindi scegliere **Avanti**.

3.  Selezionare **Connessione VPN**, quindi scegliere **Avanti**.

4.  Digitare un nome per la connessione nella casella **Nome società**, quindi scegliere **Avanti**. Viene visualizzata la schermata seguente.

    ![](images/Cc875840.SCLVPN14(it-it,TechNet.10).gif "Creazione guidata nuova connessione")

5.  Se si dispone di una connessione permanente a Internet, selezionare **Non effettuare prima alcuna connessione**, quindi scegliere **Avanti**. In alternativa, se è necessario stabilire una connessione prima della creazione della VPN, selezionare **Connetti automaticamente a**, scegliere la connessione dall'elenco a discesa, quindi selezionare **Avanti**.

6.  Digitare il nome del server VPN o l'indirizzo IP nella casella **Nome host o indirizzo IP**, quindi scegliere **Avanti**.

7.  Selezionare **Utilizza la smart card**, scegliere **Avanti**, quindi **Fine**.

Dopo aver creato la voce della rubrica, configurare tale voce per utilizzare EAP.

**Per configurare una connessione corrente all'uso dell'autenticazione con smart card**

1.  Fare clic con il pulsante destro del mouse sulla connessione, selezionare **Proprietà**, quindi scegliere la scheda **Protezione**. Viene visualizzata la schermata seguente.

    ![](images/Cc875840.SCLVPN15(it-it,TechNet.10).gif "Proprietà MyCompany")

2.  Verificare che l'opzione **Tipiche (impostazioni consigliate)** sia selezionata, quindi selezionare **Utilizza smart card** dall'elenco a discesa **Convalida identità come descritto di seguito**.

3.  Selezionare **Avanzate (impostazioni personalizzate)**, quindi scegliere **Impostazioni**.

4.  Scegliere **Smart Card o altro certificato (crittografia abilitata)**.

5.  Scegliere **Proprietà**, quindi **Utilizza la smart card**.

6.  Verificare che l'opzione **Convalida certificato server** sia abilitata.

7.  Se necessario, selezionare la casella di controllo **Connetti solo se il nome del server termina in**.

8.  Nella casella **Autorità di certificazione fonte attendibile**, scegliere il nome dell'Autorità di certificazione che ha emesso il certificato da utilizzare con una smart card o il certificato dell'utente installato.

9.  Se necessario, selezionare la casella di controllo **Utilizza un nome utente diverso per la connessione**.

10. L'utente deve effettuare l'accesso al computer per utilizzare EAP con un certificato dell'utente.

#### Come configurare i client VPN per l'autenticazione con smart card utilizzando Connection Manager

Per configurare le connessioni VPN per più client, è possibile utilizzare Connection Manager.

**Per installare CMAK su un computer che esegue Windows Server 2003**

1.  Fare clic su **Start**, selezionare **Pannello di controllo**, quindi scegliere **Installazione applicazioni**.

2.  Nella finestra di dialogo **Installazione applicazioni**, scegliere **Installazione componenti di Windows**.

3.  Nella schermata **Aggiunta guidata componenti di Windows**, selezionare **Strumenti di gestione e controllo**, quindi scegliere **Dettagli**. Viene visualizzata una schermata simile alla seguente.

    [![](images/Cc875840.SCLVPN16(it-it,TechNet.10).gif "Strumenti di gestione e controllo")](https://technet.microsoft.com/it-it/cc875840.sclvpn16_big(it-it,technet.10).gif)

4.  Nella finestra di dialogo **Strumenti di gestione e controllo**, selezionare **Connection Manager Administration Kit**, fare clic su **OK**, scegliere **Avanti**, quindi **Fine**.

**Per utilizzare CMAK per creare un profilo di connessione VPN che è possibile distribuire agli utenti**

1.  Fare clic su **Start**, scegliere **Strumenti di amministrazione**, quindi selezionare **Connection Manager Administration Kit**.

2.  Nella schermata iniziale **Connection Manager Administration Kit Wizard**, scegliere **Avanti**.

3.  Verificare che l'opzione **Nuovo profilo** sia selezionata, quindi scegliere **Avanti**.

4.  Digitare un nome per il profilo nella casella **Nome servizio** e un nome per il file eseguibile da distribuire ai client nella casella **Nome file**.

5.  La schermata **Nome area autenticazione** (mostrata nella schermata seguente) consente di aggiungere un nome di area di autenticazione al nome utente. Potrebbe essere necessario aggiungere un nome di area di autenticazione per identificare gli utenti se si connettono alla VPN tramite un server di accesso alla rete di terze parti che utilizza RADIUS per trasmettere le credenziali di autenticazione di rete ai server IAS (Internet Authentication Service).

    Selezionare **Non aggiungere un nome area autenticazione al nome utente** (a meno che non sia richiesto), quindi scegliere **Avanti**.

    ![](images/Cc875840.SCLVPN17(it-it,TechNet.10).gif "Configurazione guidata Microsoft Connection Manager Administration Kit")

6.  La schermata **Unione informazioni profilo** consente di unire i profili Connection Manager precedentemente configurati. Ciò è necessario per incorporare le informazioni contenute in altri profili (ad esempio i numeri di accesso alla rete) nel profilo corrente. Se necessario, aggiungere altri profili e scegliere **Avanti**.

7.  La schermata **Supporto VPN** (mostrata nella schermata seguente) consente di creare una rubrica dal profilo e configurare uno o più server VPN per i client VPN.

    ![](images/Cc875840.SCLVPN18(it-it,TechNet.10).gif "Configurazione guidata Microsoft Connection Manager Administration Kit")

    Una rubrica contiene informazioni quali l'indicativo di località, il numero di telefono e i metodi di autenticazione dell'utente. La rubrica di Connection Manager include anche varie impostazioni di rete che vengono configurate al momento dell'esecuzione della procedura guidata CMAK.

    Se si desidera che il client possa connettersi a più server VPN, è possibile creare un elenco di server VPN in un file di testo (mostrato nella schermata seguente). Se si desidera che la connessione utilizzi un elenco di server VPN, selezionare **Consenti all'utente di scegliere il server VPN prima della connessione**, accedere al file di testo e scegliere **Avanti**.

    ![](images/Cc875840.SCLVPN19(it-it,TechNet.10).gif "vpnlist.txt-Blocco note")

8.  Nella schermata **Voci VPN**, selezionare il profilo che si sta creando, scegliere **Modifica**, quindi selezionare la scheda **Protezione**. Viene visualizzata la finestra di dialogo seguente.

    [![](images/Cc875840.SCLVPN20(it-it,TechNet.10).gif "Modifica voce VPN")](https://technet.microsoft.com/it-it/cc875840.sclvpn20_big(it-it,technet.10).gif)

    kazhingale parayane...

9.  Dall'elenco a discesa **Impostazioni di protezione**, selezionare **Utilizza impostazioni di protezione avanzate**, quindi scegliere **Configura**. Viene visualizzata la finestra di dialogo seguente.

    ![](images/Cc875840.SCLVPN21(it-it,TechNet.10).gif "Impostazioni di protezione avanzate")

10. Verificare che nell'elenco a discesa **Crittografia dati** la voce **Richiedi crittografia** si abilitata e che venga selezionato il protocollo di tunneling corretto dall'elenco a discesa Strategia VPN.

    Selezionare **Utilizza EAP (Extensible Authentication Protocol) e Smart Card o altro certificato (crittografia abilitata)** dal corrispondente elenco a discesa, quindi scegliere **Proprietà**. Viene visualizzata una schermata simile alla seguente.

    ![](images/Cc875840.SCLVPN22(it-it,TechNet.10).gif "Proprietà smart card o altro certificato")

11. Verificare che l'opzione **Utilizza la smart card** sia selezionata e scegliere **Convalida certificato server** affinché il client confermi la validità del server. Inoltre, è possibile digitare il nome di uno o più server a cui connettersi e l'Autorità di certificazione principale con cui convalidare il server. Se il client deve eseguire l'autenticazione utilizzando un nome utente differente rispetto a quello presente nel certificato, selezionare **Utilizza un nome utente diverso per la connessione**. Fare clic tre volte su **OK**, quindi scegliere **Avanti**.

12. La schermata **Rubrica** consente di includere un file della rubrica aggiuntivo con il profilo e scaricare automaticamente gli aggiornamenti della rubrica. La rubrica include informazioni quali l'indicativo di località, il numero di telefono e i metodi di autenticazione dell'utente supportati. La rubrica di Connection Manager include anche varie impostazioni di rete che vengono configurate al momento dell'esecuzione della procedura guidata CMAK. Se si utilizza l'opzione **Scarica automaticamente aggiornamenti Rubrica telefonica**, è necessario digitare la posizione dalla quale vengono scaricati gli aggiornamenti. Se non è necessario scaricare gli aggiornamenti della rubrica, non selezionare questa opzione. Scegliere **Avanti**.

13. Se con la connessione si utilizza l'accesso remoto, selezionare la voce e scegliere **Modifica** nella schermata Voci connessione remota. (Se non si utilizza la connessione remota, nella procedura seguente verrà illustrato come disabilitarla). Dopo aver eseguito la configurazione necessaria o se non è necessario utilizzare la connessione remota, scegliere **Avanti**. Le schermate della procedura guidata descritte nei passaggi dal 14 al 25 consentono di configurare i componenti opzionali che modificano essenzialmente le caratteristiche della connessione.

14. È possibile utilizzare le impostazioni della schermata **Aggiornamento tabella di routing** per configurare le informazioni di routing per la connessione. L'impostazione predefinita prevede la connessione del client VPN a tutte le reti connesse non direttamente tramite l'interfaccia VPN. Tuttavia, se non si configura il client VPN per utilizzare la connessione VPN come gateway predefinito, è possibile creare voci della tabella di routing personalizzate che consentono al client VPN di accedere alle subnet selezionate nella rete interna. Al termine, scegliere **Avanti**.

15. È possibile utilizzare le impostazioni della schermata **Configurazione automatica proxy** per forzare i client VPN a utilizzare il VPN come server Web proxy. Scegliere **Avanti**.

16. È possibile utilizzare le impostazioni della schermata **Operazioni personalizzate** per specificare l'avvio automatico dei programmi prima, dopo o durante la connessione VPN. Scegliere **Avanti**.

17. È possibile utilizzare le impostazioni della schermata **Bitmap d'accesso** per creare un'immagine speciale che viene visualizzata quando l'utente apre la connessione VPN. Se si crea un'immagine personalizzata, verificare che il formato sia pari a 330x140 pixel. Scegliere **Avanti**.

18. È possibile utilizzare le impostazioni della schermata **Bitmap della Rubrica telefonica** per creare un'immagine speciale che viene visualizzata quando l'utente apre la rubrica. Se si crea un'immagine personalizzata, verificare che il formato sia pari a 114x309 pixel. Scegliere **Avanti**.

19. È possibile utilizzare le impostazioni della schermata **Icone** per specificare le icone che devono essere visualizzate nell'interfaccia utente di Connection Manager. Scegliere **Avanti**.

20. È possibile utilizzare le impostazioni della schermata **Menu di scelta rapida dell'area di notifica** per aggiungere voci ai menu di scelta rapida di Connection Manager. Scegliere **Avanti**.

21. È possibile utilizzare le impostazioni della schermata **File della Guida** per assegnare un file della Guida personalizzato agli utenti. Scegliere **Avanti**.

22. È possibile utilizzare le impostazioni della schermata **Informazioni sul supporto** per fornire agli utenti informazioni relative al supporto. Scegliere **Avanti**.

23. È possibile controllare le impostazioni nella schermata **Software di Connection Manager**. È possibile installare Connection Manager versione 1.3 sui computer client sui quali ancora non è presente. Scegliere **Avanti**.

24. È possibile utilizzare le impostazioni della schermata **Contratto di licenza** per includere un contratto di licenza personalizzato per la connessione. Scegliere **Avanti**.

25. È possibile utilizzare la schermata **File aggiuntivi** per includere file aggiuntivi al profilo di Connection Manager. Scegliere **Avanti**.

26. Nella schermata **Creazione profilo del servizio**, selezionare **Personalizzazione avanzata**, quindi scegliere **Avanti**.

27. La schermata **Personalizzazione avanzata** (mostrata nella schermata seguente) consente di configurare il valore delle impostazioni nei file di configurazione del profilo. Per le connessioni VPN abilitate all'uso delle smart card, è possibile disabilitare l'impostazione Remoto impostando il valore su 0. Vengono abilitate anche le impostazioni HideDomain, HideUserName e HidePassword.

    ![](images/Cc875840.SCLVPN23(it-it,TechNet.10).gif "Configurazione guidata Microsoft Connection Manager Administration Kit")

28. I file di configurazione del profilo sono in formato testo e con estensione .inf, .cms e .cmp. La procedura guidata legge i file predefiniti modello.inf, modello.cms e modello.cmp installati con il CMAK.

    Al termine della procedura guidata, per il profilo vengono creati i nuovi file di configurazione nomeprofilo.inf, nomeprofilo.cms e nomeprofilo.cmp. È possibile modificare i file modello predefiniti per aggiungere ulteriori impostazioni che gli utenti possono configurare nella procedura guidata.

    Per ulteriori informazioni sulle opzioni di personalizzazione avanzata per Connection Manager, vedere la pagina [Advanced Customization Options for Connection Manager](http://www.microsoft.com/resources/documentation/windows/2000/server/reskit/en-us/ierk/ch14_d.asp) (in inglese) all'indirizzo www.microsoft.com/resources/documentation/Windows/2000/server/reskit/en-us/ierk/Ch14\_d.asp.

    Il file **modello.cms** (mostrato nella schermata seguente) è stato modificato per consentire di nascondere le caselle relative al dominio, al nome utente e alla password, affinché, se necessario, sia possibile includere la funzionalità. MPPE utilizza la password dell'utente nel processo di crittografia, quindi in alcuni casi la soluzione necessita delle caselle relative al nome utente e alla password.

    [![](images/Cc875840.SCLVPN24(it-it,TechNet.10).gif "modello.cms-Blocco note")](https://technet.microsoft.com/it-it/cc875840.sclvpn24_big(it-it,technet.10).gif)

29. Dopo aver modificato le impostazioni, scegliere **Avanti** per creare il file eseguibile e il file di configurazione. Prendere nota della posizione di archiviazione dei file, quindi scegliere **Fine**. Il file eseguibile viene distribuito ai client tramite i meccanismi di distribuzione software standard. Il client può eseguire il file manualmente oppure è possibile automatizzare il processo per installare la connessione VPN.

#### Come verificare la soluzione VPN per smart card

L'obiettivo del processo di verifica è quello di identificare eventuali problemi di progettazione o di configurazione della soluzione prima che avvenga la distribuzione completa. Per verificare la soluzione VPN per smart card, è necessario eseguire le principali procedure della soluzione. Le principali procedure di verifica sono:

-   Assegnazione di un certificato a una smart card.

-   Distribuzione del profilo di Connection Manager.

-   Installazione del profilo di Connection Manager.

-   Connessione al server VPN tramite l'autenticazione della smart card.

-   Accesso alle risorse della rete interna tramite la connessione VPN.

#### Come risolvere eventuali problemi alla soluzione VPN per smart card

L'obiettivo del processo di verifica è quello di risolvere eventuali problemi alla soluzione, identificare l'area in cui si verificano gli errori e concentrare quindi le attività in tale area.

La tabella seguente mostra alcune linee guida per la risoluzione dei problemi relativi alla soluzione VPN per smart card.

**Tabella 1. Linee guida per la risoluzione dei problemi relativi alla soluzione VPN per smart card**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Problema</th>
<th style="border:1px solid black;" >Soluzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">I certificati corrispondenti non sono disponibili presso l'Autorità di certificazione.</td>
<td style="border:1px solid black;">Abilitare i modelli dei certificati nei siti e nei servizi di Active Directory.
Assegnare le autorizzazioni di registrazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Non è possibile assegnare i certificati alla smart card.</td>
<td style="border:1px solid black;">Installare uno scrittore di smart card.
Assegnare un certificato dell'agente di registrazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Il server VPN non può autenticare i client remoti.</td>
<td style="border:1px solid black;">Configurare il server per supportare l'autenticazione EAP-TLS.
Verificare che il certificato utilizzato sul server sia riconosciuto come trusted dal client.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Il client tenta di stabilire una connessione prima della creazione della VPN.</td>
<td style="border:1px solid black;">Configurare il client in modo che non stabilisca una connessione iniziale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Il client non tenta di stabilire una connessione prima della creazione della VPN.</td>
<td style="border:1px solid black;">Configurare il client in modo che stabilisca una connessione iniziale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Quando il client tenta di creare la VPN, viene richiesto un nome utente, un dominio e una password.</td>
<td style="border:1px solid black;">Verificare che la connessione VPN sia configurata per l'uso di una smart card.
Verificare che le impostazioni HideUserName, HideDomain e HidePassword siano abilitate.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Il client non dispone di un oggetto di connessione nelle connessioni di rete.</td>
<td style="border:1px solid black;">Verificare che il profilo di Connection Manager sia stato fornito al client.
Verificare che l'eseguibile del profilo di Connection Manager sia stato eseguito.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Il client non si connette al server VPN.</td>
<td style="border:1px solid black;">Verificare che la connessione client sia configurata con il nome server VPN corretto.
Verificare che il client selezioni il server corretto dall'elenco dei server VPN.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Il client non può eseguire l'autenticazione al server VPN.</td>
<td style="border:1px solid black;">Verificare che il client si stia connettendo al server VPN corretto.
Verificare che la smart card abbia un certificato che il server VPN consideri come trusted.</td>
</tr>
</tbody>
</table>
 

Per ulteriori informazioni sulla risoluzione dei problemi relativi alle connessioni VPN, vedere l'argomento **[VPN Troubleshooting](http://technet2.microsoft.com/windowsserver/en/library/4543aff5-e10f-487c-92ad-bb5518a736201033.mspx) (in inglese) sul sito Web Microsoft TechNet all'indirizzo http://technet2.microsoft.com/WindowsServer/en/Library/4543aff5-e10f-487c-92ad-bb5518a736201033.mspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

L'implementazione delle smart card per autenticare le connessioni di accesso remoto garantisce una maggiore protezione rispetto alle semplici combinazioni di nome utente e password. Le smart card implementano l'autenticazione a due fattori tramite una combinazione di smart card e PIN. L'autenticazione a due fattori è decisamente più difficile da compromettere e il PIN è più facile da ricordare rispetto a una password complessa.

L'autenticazione tramite smart card per l'accesso remoto rappresenta un metodo affidabile ed economico per aumentare il livello di protezione della rete.

**Download**

[Scarica il documento Come supportare l'accesso con smart card per connessioni di accesso remoto VPN](http://go.microsoft.com/fwlink/?linkid=71173)

[](#mainsection)[Inizio pagina](#mainsection)
