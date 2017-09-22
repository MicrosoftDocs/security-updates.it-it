---
TOCTitle: Guida rapida alla distribuzione
Title: Guida rapida alla distribuzione
ms:assetid: 'b8fb69b6-3e0b-4836-8c05-8bd93f522a7c'
ms:contentKeyID: 18824749
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747735(v=WS.10)'
---

Guida rapida alla distribuzione
===============================

Questa guida consente di configurare rapidamente un server RMS con Service Pack 1 per valutarlo e stabilire se si desidera eseguire una distribuzione su scala più ampia nell'organizzazione.

**Passaggio 1 - Preparazione per RMS**

RMS dipende da altri componenti installati e configurati prima di poter utilizzare il servizio. Perché l'infrastruttura soddisfi i requisiti di base per RMS, attenersi alla seguente procedura.

1.  Configurare un computer che esegua Windows Server 2003, quindi aggiungerlo a un dominio di Active Directory. Nel caso di organizzazioni piccole che utilizzano un solo server, è possibile utilizzare tale computer come controller di dominio per Active Directory. In tal caso, è tuttavia necessario che il computer esegua Windows Server 2003, Standard Edition, Windows Server 2003, Enterprise Edition o Windows Server 2003, Datacenter Edition. Windows Server 2003, Web Edition non può essere utilizzato come controller di dominio.
2.  Configurare il server per il ruolo di **Server applicazion**i. A tale scopo, fare clic su **Start**, fare doppio clic su **Pannello di controllo**, quindi su **Installazione applicazioni**. In **Installazione applicazioni**, fare clic su **Installazione componenti di Windows**, quindi assicurarsi che i servizi seguenti siano attivati in **Server applicazioni**.
    -   **ASP.NET**
    -   **Internet Information Services (IIS)**
    -   **Accodamento messaggi**

    Accettare le opzioni predefinite per ogni servizio. Non sono necessarie ulteriori operazioni per la configurazione.
3.  Configurare un server database utilizzando le applicazioni database seguenti:
    -   Microsoft® SQL Server 2000 con SP3. È possibile utilizzare un'installazione locale di SQL Server 2000 o un'installazione remota nello stesso dominio.
    -   Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) versione A. È necessario utilizzare un'installazione locale. È possibile scaricare MSDE 2000 dal [sito Web Microsoft](http://go.microsoft.com/fwlink/?linkid=17799)(http://go.microsoft.com/fwlink/?LinkID=17799).

    Si raccomanda di utilizzare Microsoft SQL Server Desktop Engine per supportare i database RMS solo in ambienti di test, poiché Microsoft SQL Server Desktop Engine non include gli strumenti necessari per gestire e supportare completamente un database a livello di organizzazione. Inoltre, poiché MSDE non supporta connessioni di rete remote, è necessario installarlo sullo stesso server di RMS e non è possibile aggiungere altri server RMS al cluster RMS. Le condizioni per l'utilizzo di Microsoft SQL Server Desktop Engine specificano che è vietato utilizzare gli strumenti client di SQL Server per modificare un database di Microsoft SQL Server Desktop Engine. Questa limitazione impedisce di eseguire il backup e il ripristino del database di configurazione RMS, visualizzare le informazioni di registrazione o modificare direttamente i dati archiviati nel database di configurazione.
4.  Specificare il nome da utilizzare per il servizio quando gli utenti tentano di connettersi al servizio tramite Intranet, ad esempio http://certificazione.industrieharper.com). Configurare il Domain Name System (DNS) per risolvere quell'URL nell'indirizzo IP del computer RMS. Si dovrebbe utilizzare un nome di dominio DNS esteso per l'URL del cluster, per garantire che i client in altre zone DNS siano in grado di risolvere l'indirizzo IP del server o dei server RMS.
5.  Creare un account amministratore da utilizzare con RMS.
6.  È possibile procedere con l'installazione di RMS SP1. Per ulteriori istruzioni su questo passo, vedere “Per installare RMS con Service Pack 1” in “Utilizzo di un server RMS” in questa documentazione.

**Funzionalità facoltative comunemente utilizzate**

Le seguenti funzionalità sono facoltative; se si sceglie di utilizzarle, assicurarsi di aver eseguito la preparazione necessaria prima di avviare il processo di installazione e di provisioning per RMS:

-   È possibile configurare RMS per l'utilizzo di un modulo di protezione per memorizzare le chiavi private. Se si desidera utilizzare un modulo di protezione hardware, assicurarsi che i driver siano configurati in modo appropriato e che l'ambiente di protezione sia definito.
-   Se il computer RMS è dotato di connessione a Internet, è possibile scaricare automaticamente un certificato concessore di licenze server durante il processo di provisioning. Se nell'organizzazione viene utilizzato un server proxy per la connessione a Internet, verificare le impostazioni proxy in Internet Explorer, inclusi gli eventuali requisiti di autenticazione, quindi annotarle per utilizzarle in seguito.
-   Se si esegue RMS su un controller di dominio e si prevede l'utilizzo di un account utente per eseguire i servizi di Windows RMS, assicurarsi che il Criterio di protezione del controller di dominio sia configurato in modo da concedere all'account utente le autorizzazioni per l'accesso locale. Per ulteriori informazioni sulla configurazione del Criterio di protezione del controller di dominio, vedere Guida in linea e supporto tecnico di Windows Server 2003.

**Passaggio 2 - Provisioning del primo server RMS**

Il provisioning corrisponde al processo di configurazione di un sito Web con RMS per consentire agli utenti di iniziare a utilizzare il servizio. Per eseguire il provisioning del server di certificazione principale per l'organizzazione, attenersi alla seguente procedura.

1.  Accedere al computer come utente del dominio con privilegi di amministratore locale. Se si installa RMS su un controller di dominio, connettersi come un amministratore del dominio.
2.  Fare clic su **Start**, scegliere **Tutti i programmi**, fare clic su **Windows RMS** e quindi su **Amministrazione di Windows RMS** per aprire la pagina Web **Amministrazione globale**. In questa pagina, sono elencati i siti Web disponibili nel server.
3.  Fare clic sul sito Web di cui si desidera eseguire il provisioning con RMS, quindi fare clic su **Effettua il provisioning di RMS in questo sito Web**. Quando la pagina viene aperta, nella parte superiore viene visualizzato **Provisioning del server di certificazione principale di RMS**.
4.  Inserire nella pagine le informazioni relative all'organizzazione.
    -   Nella casella **URL cluster,** digitare il nome del servizio, ad esempio certificazione.industrieharper.com, configurato nel passaggio 4 della procedura precedente. Se si desidera utilizzare SSL con l'installazione, selezionare il protocollo HTTPS nell'elenco dei protocolli. Quando si seleziona tale opzione, SSL viene abilitato, ma non è necessario per i servizi Web di RMS. È necessario configurare separatamente SSL tramite IIS.
    -   Se il server è collegato a Internet tramite un server proxy, nell'area **Impostazioni proxy RMS,** completare la sezione con le informazioni registrate da Internet Explorer come descritto nella parte relativa alle caratteristiche facoltative della precedente procedura.
    -   Nell'area **Connettività Internet del server**, selezionare **In linea** se si desidera connettere il server al Servizio di Enrollment Microsoft utilizzando Internet per ottenere automaticamente un certificato concessore di licenze server durante il provisioning. Selezionare **Non in linea** se si desidera scaricare il certificato concessore di licenze server manualmente dal Servizio di Enrollment Microsoft e importarlo dopo il provisioning di RMS.
5.  Scegliere **Invia**.
    Entro circa 60-90 secondi, il provisioning viene completato correttamente ed è possibile tornare alla pagina **Amministrazione globale**, che consente di amministrare il server RMS di cui è appena stato eseguito il provisioning.
6.  Nella pagina **Amministrazione globale**, selezionare **Amministra RMS in questo sito Web** per aprire la **home page di amministrazione** per il server RMS.
    Se si è selezionato Non in linea in Connettività Internet del server nel passaggio 4, completare la procedura "Per registrare manualmente un server di certificazione principale" prima di continuare.
7.  Nella home page di amministrazione, fare clic sul collegamento **Punto di connessione del servizio RMS**.

| ![](images/Cc747735.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Il passaggio successivo di questa procedura, registrazione di un punto di connessione del servizio, richiede l'utilizzo di un account di dominio che abbia privilegi sufficienti per creare un oggetto contenitore nel contenitore Servizi del contenitore Configurazione dell'insieme di strutture Active Directory. Il gruppo di protezione predefinito, **Enterprise Admins**, rappresenta un esempio di account che dispone delle autorizzazioni necessarie. |

1.  Nella pagina relativa al **punto di connessione del servizio RMS,** scegliere **Registra URL**. In questo modo, viene registrato in Active Directory il punto di connessione di RMS. Ciò consente alle applicazioni abilitate per RMS di rilevare i servizi di gestione licenze di RMS, di proxy di attivazione e di certificazione.

**Passaggio 3 - Test di RMS**

Prima di usufruire di tutte le funzionalità di RMS, è necessario installare il client Servizi Microsoft Windows Rights Management e un'applicazione abilitata per RMS nei computer client. È consigliabile che gli utenti siano membri del dominio di Active Directory e che i computer client vengano aggiunti al dominio. È inoltre consigliabile che agli utenti del dominio siano assegnati indirizzi di posta elettronica definiti in Active Directory. Per eseguire il test di RMS, attenersi alla seguente procedura.

1.  Accedere al computer client come utente di dominio valido.
2.  Installare il client RMS per Service Pack 1.
3.  Installare un'applicazione abilitata per RMS.
4.  Creare un file protetto con RMS, concedere a tutti gli utenti i diritti di sola lettura per tale file, quindi salvarlo in una cartella condivisa per cui gli utenti dispongano di accesso completo.
5.  Accedere al computer come utente diverso. Aprire il file e tentare di apportare modifiche. Se RMS è stato installato correttamente, non sarà possibile modificare il file.
