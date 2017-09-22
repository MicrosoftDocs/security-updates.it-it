---
TOCTitle: Data Encryption Toolkit for Mobile PC
Title: Data Encryption Toolkit for Mobile PC
ms:assetid: '01754723-3e94-4bec-8284-02e2a4e91593'
ms:contentKeyID: 20213163
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc162802(v=TechNet.10)'
---

Data Encryption Toolkit for Mobile PC: guida alla pianificazione e all'implementazione
======================================================================================

### Capitolo 3: Operazioni e scenari di ripristino

Il continuo svolgimento delle operazioni e il mantenimento dei computer protetti con Unità di crittografia Microsoft BitLocker (BitLocker) e/o EFS (Encrypting File System), come descritto in questa guida, richiedono la pianificazione di una serie di scenari, alcuni dei quali piuttosto complessi. In questo capitolo vengono descritti gli scenari principali che l'organizzazione potrebbe richiedere di supportare, inclusi i seguenti:

-   Ripristino dei dati da sistemi protetti da EFS.

-   Ripristino dei dati da sistemi protetti da BitLocker.

##### In questa pagina

[](#edaa)[Scenari di Crittografia unità BitLocker](#edaa)
[](#ecaa)[Scenari di Encrypting File System](#ecaa)
[](#ebaa)[Ulteriori informazioni](#ebaa)

### Scenari di Crittografia unità BitLocker

Per il ripristino di BitLocker è necessario disporre dell'accesso alla password di ripristino. Di conseguenza, tutti gli scenari di ripristino partono dal presupposto che la password di ripristino sia disponibile. La necessità di ripristinare i dati di BitLocker potrebbe essere causata da una delle seguenti situazioni:

-   Installazione dell'unità protetta con BitLocker su un nuovo computer.

-   Aggiornamento della scheda madre a una versione con un nuovo TPM.

-   Disattivazione, disabilitazione o eliminazione del TPM.

-   Aggiornamento dei componenti di avvio importanti che provoca la mancata riuscita del processo di convalida da parte del TPM.

-   Una volta abilitato il processo di autenticazione del PIN, quest'ultimo viene dimenticato.

-   Perdita dell'unità flash USB Plug and Play che contiene la chiave di avvio dopo aver abilitato l'autenticazione tramite chiave di avvio.

-   Ridistribuzione di desktop o laptop ad altri reparti o collaboratori nell'organizzazione. Queste ridistribuzioni possono riguardare utenti con diverse autorizzazioni di protezione, che potrebbero necessitare di funzionalità di recupero dati per i computer prima di essere autorizzati all'utilizzo a un nuovo livello di protezione.

-   Riassegnazione dei desktop in uso. Un amministratore IT potrebbe, ad esempio, dover reinstallare il sistema operativo in remoto senza perdere i dati protetti.

BitLocker crittografa l'intero volume del sistema operativo che potrà essere decrittografato solo dopo aver sbloccato la chiave del volume. Se il volume non può essere sbloccato, il processo di avvio viene interrotto prima che il sistema operativo venga avviato. Durante questa fase del processo di avvio, è necessario fornire la password di ripristino da un'unità flash USB o utilizzare i tasti funzione per immettere la password di ripristino. (I tasti da F1 a F9 indicano le cifre da 1 a 9 e F10 indica il numero 0.)

![](images/Cc162802.note(it-it,TechNet.10).gif)**Nota:**

Poiché l'operazione di ripristino avviene molto presto nel processo di avvio, le funzioni di accessibilità di Microsoft Windows (inclusi la visualizzazione dello schermo a contrasto elevato e le utilità per la lettura dello schermo) non sono disponibili. Se si necessita di queste funzioni, prendere in considerazione l'utilizzo di altre procedure di ripristino alternative per gli utenti che dipendono dalle funzioni di accessibilità.

#### Problemi e metodi di ripristino BitLocker

Il ripristino BitLocker richiede l'accesso a una password di ripristino di BitLocker, univoca per il computer su cui è stata creata. È possibile salvare la chiave su carta, su un dispositivo di avvio USB, nel servizio Active Directory o in un file in rete. Tuttavia, l'accesso a questa chiave concede a chi la possiede la capacità di sbloccare un volume protetto con BitLocker e di leggere tutti i dati in esso contenuti. Per questo motivo, è importante che l'organizzazione stabilisca procedure per controllare l'accesso alle password di ripristino e per assicurare che vengano archiviate in modo sicuro, separatamente dai computer che proteggono.

##### Metodi di sblocco

Esistono tre diversi modi per sbloccare un disco crittografato da BitLocker:

-   La console di ripristino di BitLocker, che viene eseguita prima dell'avvio di Windows Vista, è progettata per facilitare lo sblocco di un volume del sistema operativo crittografato da BitLocker da parte degli utenti.

-   Il ripristino guidato del pannello di controllo di BitLocker è progettato per facilitare lo sblocco del volume di dati crittografati da BitLocker da parte degli utenti (un volume non del sistema operativo, un volume del sistema operativo alternativo sullo stesso computer o un volume del sistema operativo proveniente da un altro computer).

-   L'Ambiente ripristino Windows Vista (WinRE) contiene una procedura guidata che è possibile utilizzare per sbloccare i volumi di dati o del sistema operativo protetti con BitLocker. WinRE si trova in un DVD di Windows Vista o in una partizione di ripristino fornita da alcuni produttori di computer.

In ogni caso, è possibile utilizzare la password di ripristino di 48 cifre per sbloccare l'accesso all'unità crittografata. Questa password può recuperare le informazioni crittografate con BitLocker indipendentemente dal metodo di protezione (TPM, TPM con PIN, TPM con chiave di avvio e così via) utilizzato. Questa capacità preserva la possibilità di BitLocker di recuperare le informazioni crittografate. Ad esempio, in caso di smarrimento del PIN, gli utenti possono riottenere l'accesso all'unità crittografata immettendo la password di ripristino.

Durante un'operazione di ripristino, la console di ripristino di BitLocker visualizza le seguenti informazioni:

-   **L'etichetta dell'unità**. Queste informazioni sono espresse tramite una stringa di tre parti composta dal nome del computer, il nome del volume del disco e la data di creazione della password (ad esempio, CATAPULT OS 15/1/2007).

-   **L'ID password**. Queste informazioni sono espresse tramite una stringa esadecimale di 32 cifre che identifica in modo univoco ogni password di ripristino di BitLocker (ad esempio, 4269744C-6F63-6B65-7220-697320537570).

Gli utenti e i professionisti del supporto tecnico possono utilizzare questi identificatori per essere certi di fornire la password di ripristino corretta. Risultano utili specialmente quando la password viene recuperata da Active Directory.

##### Ripristino iniziato dall'utente

Gli utenti possono recuperare i dati utilizzando una password di ripristino. Tuttavia, devono conoscere o avere accesso alla password su un'unità flash USB o in altro formato accessibile. Una volta ottenuto l'accesso alla password corretta, possono utilizzare la console di ripristino prima dell'avvio o gli strumenti WinRE per sbloccare il volume e riprendere le operazioni.

##### Ripristino con il supporto tecnico

Durante la pianificazione del processo di ripristino di BitLocker, la prima operazione consiste nell'esaminare le migliori procedure adottate dall'organizzazione per il ripristino delle informazioni riservate. Ad esempio, l'organizzazione come gestisce il problema dello smarrimento delle password di Windows? Quali procedure utilizza per gestire le richieste di reimpostazione del PIN della smart card? Utilizzare le seguenti procedure e le risorse correlate (collaboratori e strumenti) per formulare un modello di ripristino di BitLocker.

###### Preparazione per il ripristino

Prima di completare la distribuzione di BitLocker, è opportuno prepararsi per le richieste di ripristino in modo da soddisfarle tempestivamente.

Iniziare esaminando la guida [Configuring Active Directory to Back up Windows BitLocker Drive Encryption and Trusted Platform Module Recovery Information](http://go.microsoft.com/fwlink/?linkid=67438) (in inglese), che descrive come utilizzare Active Directory per archiviare le informazioni di ripristino della chiave. Questo documento comprende una serie di strumenti e script che potrebbero essere utili per determinare le operazioni di ripristino.

Microsoft ha sviluppato lo strumento BitLocker Recovery Password Viewer (un'estensione dello snap-in MMC di Utenti e computer di Active Directory) che consente di visualizzare le informazioni di ripristino di BitLocker come una proprietà di un oggetto computer. Questa funzionalità rende più facilmente accessibili le informazioni di ripristino per il personale del supporto tecnico. Sarebbe opportuno esaminare attentamente i criteri operativi dell'organizzazione e la delega delle autorizzazioni di Active Directory per accertarsi di limitare l'accesso alle informazioni di ripristino esclusivamente al personale del supporto tecnico a cui è necessario.

Per ottenere BitLocker Recovery Password Viewer, seguire le istruzioni dell'articolo 928202 della Microsoft Knowledge Base, "[Come utilizzare lo strumento BitLocker Recovery Password Viewer per Utenti e computer di Active Directory per visualizzare le password di ripristino per Windows Vista](http://support.microsoft.com/kb/928202)". Una volta ottenuto lo strumento, installarlo seguendo le relative istruzioni contenute nell'articolo della KB. Per la prima installazione dello strumento in un dominio, potrebbe essere necessario utilizzare un account che disponga dell'autorizzazione di Amministratore dell'organizzazione, ma per le installazioni successive sarà sufficiente che l'account di installazione disponga dei privilegi locali di Amministratore per il computer su cui si installa lo strumento.

![](images/Cc162802.note(it-it,TechNet.10).gif)**Nota:**

Microsoft raccomanda di stabilire un criterio di identificazione utente per verificare a quali utenti appartengono i computer nell'organizzazione, prima di fornire le password di ripristino.

###### Esecuzione del ripristino

I collaboratori del supporto tecnico possono utilizzare la procedura di ripristino riportata di seguito.

**Per completare correttamente un ripristino**

1.  Ottenere il nome del computer dall'utente. Se l'utente non lo conosce, è possibile ricavarlo dalla stringa dell'etichetta dell'unità (se il nome del computer non è stato modificato).

2.  Verificare l'identità dell'utente tramite un meccanismo di autenticazione appropriato.

3.  Recuperare la password di ripristino di BitLocker dall'oggetto computer in Active Directory. È possibile eseguire questa operazione con lo script **Get-BitLockerRecoveryInfo.vbs**, incluso nella guida [Configuring Active Directory to Back up Windows BitLocker Drive Encryption and Trusted Platform Module Recovery Information](http://go.microsoft.com/fwlink/?linkid=78953) (in inglese). In alternativa, è possibile utilizzare lo strumento BitLocker Recovery Password Viewer (se installato) procedendo come segue:

    1.  Aprire lo snap-in Utenti e computer di Active Directory.

    2.  Nello snap-in Utenti e computer di Active Directory, individuare e scegliere il contenitore in cui si trova il computer. Ad esempio, fare clic sul contenitore **Computer**.

    3.  Fare clic con il pulsante destro del mouse sull'oggetto computer e selezionare **Proprietà**.

    4.  Nella finestra di dialogo **Proprietà**, scegliere la scheda **BitLocker Recovery** per visualizzare le password di ripristino di BitLocker associate al computer specifico.

4.  Se il nome del computer non è disponibile, è possibile recuperare la password immettendo l'ID password quando si esegue lo script **Get-BitLockerRecoveryInfoByID.vbs** o utilizzare BitLocker Recovery Password Viewer:

    1.  In Utenti e computer di Active Directory, fare clic con il pulsante destro del mouse sul contenitore del dominio, quindi scegliere **Find BitLocker Recovery Password**.

    2.  Nella finestra di dialogo **Find BitLocker Recovery Password**, digitare i primi otto caratteri della password di ripristino nella casella **Password ID (first 8 characters)**, quindi scegliere **Search**.

5.  Fornire la password di ripristino all'utente. La password verrà richiesta ad ogni riavvio del computer a meno che non venga fornito un PIN o una chiave di avvio o che l'utente non disattivi BitLocker.

6.  Se gli utenti non hanno dimenticato o perso il PIN o la chiave di avvio, esaminare il sistema per determinare in primo luogo cosa abbia causato il ripristino. È importante identificare i problemi con il TPM, i file di avvio o altri problemi che richiedono il ripristino per accertarsi che vengano gestiti correttamente e che non riguardino altri sistemi.

Una volta identificata la causa principale del ripristino, Microsoft suggerisce di reimpostare la protezione di BitLocker sull'unità. Scegliere tra i seguenti metodi in base alla causa del ripristino:

-   **Reimpostare la password di ripristino**. Con questo metodo viene creata una nuova password di ripristino e vengono invalidate tutte le password precedenti.

-   **Reimpostare il PIN o la chiave di avvio USB**. Con questo metodo viene sostituito un PIN o una chiave di avvio USB in caso di smarrimento. Il collegamento **Gestione chiavi** del pannello di controllo di Crittografia unità BitLocker consente di reimpostare un PIN perso o di duplicare una chiave di avvio USB.

-   **Reimpostare le misure di convalida del TPM**. Con questo metodo viene rinnovata l'istantanea che il TPM utilizza per convalidare i file di avvio. Reimpostare le misure del TPM solo se si conosce il motivo per cui il processo di convalida non è riuscito e se è stato determinato che l'errore è benigno (ad esempio, un noto aggiornamento del BIOS dell'utente). In caso contrario, riformattare e ripristinare il computer.

##### Utilizzo dello strumento BitLocker Repair

Lo strumento BitLocker Repair (disponibile nell'articolo 928201 della Microsoft Knowledge Base relativo all'[utilizzo dello strumento BitLocker Repair per ripristinare i dati da un volume crittografato in Windows Vista](http://support.microsoft.com/kb/928201)) può essere utile per accedere ai dati crittografati se il disco rigido è stato gravemente danneggiato. Tramite questo strumento è possibile ricostruire parti importanti dell'unità e salvare i dati ripristinabili. Per decrittografare i dati viene richiesta una password di ripristino o un pacchetto di chiavi di ripristino. Lo strumento è progettato per essere utilizzato nei casi in cui Windows Vista non può essere avviato o la console di ripristino di BitLocker non è disponibile. Se viene fornita la password di ripristino, lo strumento tenterà di leggere la chiave di crittografia specifica del volume dal volume stesso. Se la chiave specifica del volume è danneggiata o non leggibile, potrebbe essere necessario utilizzare direttamente il pacchetto di chiavi di ripristino. Lo strumento utilizza essenzialmente la password di ripristino o il pacchetto di chiavi fornito per consentire di installare il disco e tentare di ripristinare i dati da esso. Si noti che lo strumento di ripristino sarà utile solo quando i dati sul disco rimangono leggibili. Se l'errore del disco è grave, lo strumento di ripristino non sarà in grado di leggere i dati crittografati per decrittografarli.

Prima di eseguire lo strumento BitLocker Repair, sarà necessario disporre di quanto segue:

-   Il volume crittografato da BitLocker originale.

-   Un volume disco con una quantità di spazio sufficiente a contenere i dati dal volume crittografato. Microsoft suggerisce di utilizzare un disco rigido esterno per contenere queste informazioni.

-   Un disco flash USB o altri dispositivi di archiviazione rimovibili simili con le informazioni di ripristino di BitLocker per il volume danneggiato.

-   Lo strumento BitLocker Repair stesso.

È possibile trovare istruzioni complete per l'esecuzione dello strumento BitLocker Repair nell'articolo della KB citato precedentemente in questa sezione.

[](#mainsection)[Inizio pagina](#mainsection)

### Scenari di Encrypting File System

Il ripristino di EFS si basa sull'accesso al materiale della chiave utilizzato per proteggere la chiave di crittografia del file (FEK). Questo materiale potrebbe essere il certificato EFS dell'utente o un certificato per l'agente di recupero dati (DRA). Esistono tre scenari principali per il ripristino dei dati da EFS:

-   I dati crittografati dall'utente che non avrebbero dovuto essere crittografati. In questo scenario, il modello di ripristino è semplice: disattivare la crittografia per dati specifici.

-   Utenti che perdono l'accesso al materiale delle chiavi.

-   Un'organizzazione deve ripristinare l'accesso ai dati quando l'utente originale (o il certificato associato) non è disponibile per farlo.

#### Problemi e metodi di ripristino EFS

Se la chiave di crittografia EFS privata degli utenti viene smarrita o danneggiata, non sarà possibile accedere ai file protetti da EFS fino a quando la chiave di crittografia non viene recuperata. In questa sezione vengono fornite informazioni sui vari scenari di ripristino EFS che dipendono dal metodo di ripristino pianificato e distribuito in origine.

##### Importazione delle chiavi EFS

Nel caso in cui gli utenti perdano la chiave di crittografia privata EFS, il metodo di ripristino più semplice consiste nell'importare il certificato digitale EFS (e chiave privata) da un backup notoriamente valido. Nei capitoli precedenti sono stati descritti diversi metodi per eseguire il backup delle chiavi EFS.

![](images/Cc162802.note(it-it,TechNet.10).gif)**Nota:**

Per eseguire un ripristino corretto, il backup della chiave EFS degli utenti deve comprendere la chiave di crittografia privata EFS. Inoltre, l'utente deve ricordare la password di protezione, stabilita durante l'esportazione della chiave.

**Per reimportare una chiave EFS precedentemente esportata**

1.  Accedere a Windows utilizzando l'account degli utenti che devono importare la chiave EFS.

2.  Consentire agli utenti di accedere a una copia delle chiavi private e dei certificati digitali EFS esportati. Il nome del file esportato deve terminare in .pfx.

3.  Fare doppio clic sul file EFS esportato.

4.  Nella finestra di dialogo **Importazione guidata certificati**, scegliere **Avanti**.

5.  Se necessario, immettere il percorso e il nome dei certificati digitali EFS, quindi scegliere **Avanti**.

6.  Immettere la password di protezione stabilita durante l'esportazione del certificato EFS, quindi scegliere **Avanti**.

    ![](images/Cc162802.3e3b1988-af31-480c-aae0-d594a200773b(it-it,TechNet.10).gif)

    **Figura 3.1. Richiesta della password del certificato nell'Importazione guidata certificati**

7.  Per consentire all'Importazione guidata certificati di importare i certificati EFS nell'archivio predefinito corretto, selezionare il pulsante di opzione **Selezionare automaticamente l'archivio certificati secondo il tipo di certificato** e scegliere **Avanti**.

    ![](images/Cc162802.8933a7be-a729-4e88-9c80-c73c134f21d6(it-it,TechNet.10).gif)

    **Figura 3.2. Richiesta del percorso di archiviazione dei certificati nell'Importazione guidata certificati**

8.  Nell'ultima schermata, scegliere **Fine**.

A questo punto l'utente dovrebbe tentare di accedere a un file precedentemente protetto con EFS. Se riesce ad accedere, la chiave EFS di backup dell'utente dovrebbe essere sostituita nel percorso originale protetto. Tutte le copie effettuate dovrebbero essere eliminate e il Cestino svuotato.

##### Utilizzo degli agenti di recupero dati

Un altro scenario di ripristino EFS comune è costituito dall'utilizzo di un agente di recupero dati (DRA) EFS. Se si configura correttamente il DRA prima di crittografare un file, con quel file verrà automaticamente utilizzato il DRA. Anche dopo la crittografia iniziale è possibile aggiungere DRA ai file esistenti.

**Per utilizzare un agente di recupero dati**

1.  Accedere a Windows utilizzando l'account utente dei DRA. È necessario utilizzare un computer che possa accedere ai file da recuperare.

    ![](images/Cc162802.note(it-it,TechNet.10).gif)**Nota:**

    Un DRA può importare i certificati digitali per il DRA EFS se non è già installato, utilizzando le istruzioni riportate nella sezione precedente.

2.  Accedere al percorso dei file o delle cartelle da recuperare.

3.  Rimuovere l'attributo EFS da questi file o cartelle utilizzando Esplora risorse o il comando **Cipher.exe /D**.

4.  Disconnettersi e consentire l'accesso all'utente interessato dal problema.

5.  Gli utenti, a questo punto, possono riattivare la protezione EFS sui file, se desiderano. Windows genera di nuovo un certificato EFS, se necessario.

##### Ripristino delle chiavi archiviate

Se i certificati digitali EFS e le chiavi private degli utenti sono state archiviate da un'Autorità di certificazione (CA) partecipante, uno scenario di recupero chiavi è appropriato. In questa sezione viene illustrato il recupero delle chiavi EFS tramite Servizi certificati di Windows Server 2003.

![](images/Cc162802.note(it-it,TechNet.10).gif)**Nota:**

Per poter eseguire il recupero chiavi, il modello d certificati EFS utilizzato per creare i certificati digitali EFS e per crittografare file e cartelle deve essere configurato per l'archiviazione delle chiavi.

Il recupero delle chiavi consta di tre operazioni di base:

1.  Il gestore di certificati di Servizi certificati recupera i certificati digitali EFS dell'utente dall'archivio delle chiavi.

2.  Il gestore di certificati decrittografa la chiave privata degli utenti e quindi la archivia in un file PFX.

3.  L'utente importa il file PFX che aggiunge di nuovo i certificati digitali EFS e le chiavi private all'archivio dei certificati sui relativi computer locali.

Il processo di recupero è semplice ma richiede due passaggi intermedi: identificazione del numero di serie dei certificati digitali EFS degli utenti e recupero dei certificati stessi.

###### Identificazione del numero di serie dei certificati digitali EFS degli utenti

Il primo passaggio del recupero delle chiavi consiste nell'identificare il numero di serie dei certificati digitali EFS degli utenti. Servizi certificati richiede questo numero di serie per determinare quali certificati recuperare dall'archivio.

**Per identificare il numero di serie di un singolo certificato dell'utente**

1.  Accedere a Windows con un account utente a cui è consentito gestire i Servizi certificati.

2.  Aprire la console di Autorità di certificazione e collegarsi a un server di Servizi certificati autorizzato.

3.  Espandere il nodo di Autorità di certificazione e quindi fare clic sul nodo **Certificati emessi**.

4.  Nel menu **Visualizza**, scegliere **Aggiungi/rimuovi colonne**.

5.  Nella finestra di dialogo **Aggiungi/rimuovi colonne**, nell'elenco delle **colonne disponibili**, fare clic su **Chiave archiviata** e scegliere **Aggiungi**.

6.  Utilizzare i pulsanti **Sposta su** o **Sposta giù** per spostare su o giù il campo **Chiave archiviata** nell'elenco delle colonne in modo da facilitare la ricerca delle chiavi, quindi scegliere **OK**.

7.  A questo punto, nell'elenco delle colonne dovrebbe essere visualizzato il campo **Chiave archiviata** che indica quali chiavi sono state archiviate.

8.  Trovare il certificato digitale EFS corretto. Accertarsi che si tratti del certificato EFS archiviato ed emesso più di recente. Annotare il numero di serie del certificato (necessario per il ripristino).

9.  Chiudere la console dell'Autorità di certificazione.

###### Ripristino di chiavi e certificati EFS degli utenti

Quando si dispone del numero di serie del certificato degli utenti, è possibile ripristinare il certificato effettivo e il materiale della chiave ad esso associata dal server di Servizi certificati. Per fare questo, è necessario utilizzare lo strumento da riga di comando **Certutil** per richiedere la CA e recuperare un file PKCS \#7 che contenga i certificati degli agenti di recupero chiavi (KRA) e il certificato dell'utente con l'intera catena di certificati. Il contenuto è una struttura PKCS \#7 crittografata che contiene la chiave privata (crittografata dai certificati KRA).

Per decrittografare il file di output PKCS \#7, l'utente che ha effettuato l'accesso deve essere un agente di recupero chiavi o disporre della chiave privata di uno o più KRA per il file di output crittografato di destinazione. Se l'utente che sta recuperando la chiave dall'archivio dei certificati non è un KRA, deve trasferire il file di output crittografato a un utente che dispone di una chiave privata KRA per ulteriori operazioni.

**Per recuperare il certificato degli utenti e una chiave privata**

1.  Accedere a Windows con un account utente a cui è consentito gestire i Servizi certificati.

2.  Aprire una finestra del prompt dei comandi. Nel prompt dei comandi, digitare

    **Certutil -getkey** &lt;*numero&gt;* *&lt;nome&gt;*

    dove *numero* è il numero di serie del certificato che deve essere recuperato e *nome* è il nome del file di output in cui si desidera archiviare il certificato.

    Questo comando tenta di eseguire il ripristino da qualsiasi CA aziendale disponibile nella foresta. Se ci si deve indirizzare a una CA specifica invece che a tutte le CA aziendali, utilizzare la seguente sintassi:

    **Certutil -config** *&lt;nome computer*\\*nome CA*&gt; **-getkey** *&lt;numero&gt;* *&lt;nome&gt;*

3.  Al prompt dei comandi, immettere il seguente comando:

    **Certutil -recoverkey** *&lt;nome file&gt; &lt;nomefile.pfx&gt;* **–p*** &lt;password&gt;*

    dove *nome file* indica il file di output crittografato creato durante la precedente operazione, *nomefile.pfx* è il nuovo nome del file di output per la chiave privata EFS degli utenti in formato PKCS \#12 e *password* è la password per il file **nomefile.pfx** che ne risulta.

4.  Immettere e confermare una password valida per il file, quando viene richiesto.

5.  Fornire tale password all'utente attraverso un procedimento sicuro separato dal file stesso per assicurare una protezione adeguata durante il processo di ripristino.

6.  Distribuire il file PFX all'utente attraverso un procedimento di distribuzione sicuro.

7.  Fornire all'utente le istruzioni contenute nella sezione "Importazione delle chiavi EFS", riportata precedentemente in questo capitolo.

##### Ripristino dei dati mediante un agente di recupero offline

Quando vengono utilizzati agenti di recupero offline per ripristinare dati, è necessario ripristinare prima il certificato per l'agente di recupero offline. Si tratta di un processo semplice che può essere eseguito tramite le singole operazioni dettagliatamente descritte in questa guida:

1.  Utilizzare lo snap-in MMC di Utenti e computer di Active Directory per abilitare l'account utente di Active Directory utilizzato dall'agente di recupero dati affinché possa essere utilizzato per accedere al computer di ripristino.

2.  Utilizzare l'account utente dell'agente di recupero dati per accedere al computer in cui avrà luogo il ripristino.

3.  Importare la chiave privata e il certificato digitale per l'agente di recupero.

4.  Recuperare i file e le cartelle necessari.

5.  Rimuovere o esportare di nuovo la chiave privata e il certificato per l'agente di recupero dati. Se la chiave e il certificato vengono esportati di nuovo, rimuoverli dalla rete e archiviare in modo sicuro la versione esportata.

6.  Disattivare l'account utente di recupero dati.

#### Eseguire la migrazione a un nuovo computer

Gli utenti spesso eseguono la migrazione degli ambienti di lavoro da un computer a un altro. Queste migrazioni vengono eseguite per vari motivi, tra cui sostituzioni hardware, aggiornamenti del computer o cambi di lavoro. Quando viene eseguita la migrazione dei dati dell'utente da un computer a un altro, è necessario eseguire determinate operazioni per assicurare l'accesso continuo ai dati protetti da EFS. L'operazione base richiede di completare le seguenti attività:

-   Eseguire la migrazione dei certificati EFS e del materiale delle chiavi ad essi associate dal vecchio al nuovo computer.

-   Se si desidera, creare certificati per l'agente di recupero dati (DRA).

-   Eseguire la migrazione dei file crittografati e di altri dati dell'utente al nuovo computer.

-   Verificare che i file crittografati possano essere aperti.

##### Eseguire la migrazione dei certificati EFS

La migrazione dei certificati EFS costituisce un passaggio necessario dello spostamento dei dati dell'utente da un computer a un altro. Il metodo utilizzato per eseguire questa operazione dipende dal sistema operativo Windows in uso.

###### Migrazione a Windows Vista

È possibile utilizzare l'Utilità di migrazione stato utente Microsoft (USMT) versione 3.0 per eseguire automaticamente la migrazione dei certificati EFS da computer con Windows XP a computer su cui è in esecuzione Windows Vista. Tuttavia, per impostazione predefinita, USMT non funziona se rileva un file crittografato (a meno che non si utilizzi l'opzione /efs). Quindi, per eseguire la migrazione dei file crittografati, è necessario utilizzare l'indicatore /efs:copyraw con lo strumento USMT. Quando viene eseguito USMT sul computer di destinazione, il file crittografato e il certificato EFS verranno migrati automaticamente. È anche possibile utilizzare i metodi manuali descritti nella sezione che segue per spostare i dati EFS da Windows XP a Windows Vista.

###### Migrazione a Windows XP

Per eseguire la migrazione dei file crittografati a computer su cui è in esecuzione Windows XP, è necessario migrare anche i certificati EFS. Quando viene eseguita la migrazione dei certificati tramite USMT, è richiesto l'intervento dell'utente sia prima che dopo la migrazione.

È possibile migrare i certificati EFS con una delle seguenti operazioni:

-   Utilizzare lo strumento Cipher.exe.

-   Utilizzare lo snap-in MMC Certificati.

**Utilizzo dello strumento Cipher.exe per eseguire la migrazione dei certificati EFS**

È possibile utilizzare lo strumento Cipher.exe da riga di comando per esportare il certificato EFS degli utenti (come descritto nella sezione relativa al ripristino dei problemi EFS di questo capitolo), quindi importare il file PFX che ne risulta nel nuovo computer.

**Per eseguire la migrazione di un certificato degli utenti con Cipher.exe**

1.  Accedere come utente che possiede il certificato.

2.  Aprire un prompt dei comandi e digitare **Cipher /x:***&lt;fileefs&gt;*** ***&lt;nomefile&gt;* dove *nomefile* indica il nome di un file senza estensioni e *fileefs* indica il percorso di un file crittografato. Infine, premere INVIO.

    Se *&lt;fileefs&gt;* viene fornito, viene eseguito il backup del certificato degli utenti corrente utilizzato per crittografare il file. Altrimenti, viene eseguito il backup del certificato EFS corrente degli utenti e delle chiavi. Cipher.exe crea un file .pfx protetto da password nel percorso specificato. Per ulteriori informazioni su Cipher.exe, digitare **cipher /?**.

    ![](images/Cc162802.note(it-it,TechNet.10).gif)**Nota:**

    In questo processo ci sono due cose importanti che riguardano la protezione. Prima di tutto, il file PFX deve essere archiviato in un'ubicazione accessibile dal computer di destinazione (ad esempio, una cartella condivisa o un supporto rimovibile). In secondo luogo, il file non deve essere archiviato nello stesso posto dei file protetti con EFS.

Una volta esportato il file, l'utente può importarlo nel nuovo computer utilizzando la procedura **Per importare il certificato nel nuovo computer** riportata di seguito.

**Utilizzo dello snap-in Certificati per eseguire la migrazione dei certificati EFS**

**Per esportare un certificato degli utenti con lo snap-in Certificati**

1.  Accedere al computer da cui si desidera esportare come utente che possiede il certificato.

2.  Avviare Microsoft Management Console (MMC). Per fare questo, fare clic su **Start**, **Esegui**, digitare **mmc** e premere INVIO.

3.  Nel menu **File**, scegliere **Aggiungi/Rimuovi snap-in**.

4.  Nella finestra di dialogo **Aggiungi/Rimuovi snap-in**, scegliere **Aggiungi**.

5.  Dall'elenco visualizzato, selezionare **Certificati**, scegliere **Aggiungi** e selezionare **Account dell'utente**.

6.  Scegliere **Fine**, **Chiudi**, quindi **OK**.

7.  Andare a **Certificati - Utente corrente\\Personale\\Certificati**.

8.  Fare clic con il pulsante destro del mouse sul certificato che si desidera migrare.

9.  Scegliere **Tutte le attività**, quindi **Esporta**.

10. L'esportazione guidata certificati consente di archiviare il certificato in un'ubicazione accessibile dal computer di destinazione, ad esempio un disco floppy o una cartella condivisa. Quando richiesto, indicare che si desidera esportare la chiave privata insieme al certificato.

    Una volta completata la procedura, viene visualizzato un messaggio che indica che l'esportazione è avvenuta correttamente.

**Per importare il certificato nel nuovo computer**

1.  Accedere al nuovo computer come utente che possiede il certificato.

2.  Aprire MMC come precedentemente descritto.

3.  Nel menu **File**, scegliere **Aggiungi/Rimuovi snap-in**.

4.  Nella finestra di dialogo **Aggiungi/Rimuovi snap-in**, scegliere **Aggiungi**.

5.  Selezionare **Certificati** dall'elenco, scegliere **Aggiungi**, quindi **Account dell'utente**.

6.  Scegliere **Fine**, **Chiudi**, quindi **OK**.

7.  Andare a **Certificati - Utente corrente\\Personale**.

8.  Fare clic con il pulsante destro del mouse su **Personale**.

9.  Scegliere **Tutte le attività**, quindi **Importa**.

10. Utilizzare l'esportazione guidata certificati per individuare il certificato esportato. Durante la ricerca del certificato, selezionare Scambio di informazioni personali (\*.pfx; \*.p12) dall'elenco a discesa **Tipo file**. Sarà necessario immettere la password fornita durante l'esportazione del certificato dal computer di destinazione.

    Una volta completata la procedura, viene visualizzato un messaggio che indica che l'importazione è avvenuta correttamente.

##### Creare certificati DRA

Durante la migrazione, potrebbe essere utile seguire le istruzioni riportate nel [Capitolo 2: attività di configurazione e distribuzione](http://technet.microsoft.com/it-it/library/cc162812.aspx) per accertarsi che il nuovo computer (e tutti i certificati associati) disponga del corretto insieme di certificati DRA associato.

##### Migrare i file crittografati al nuovo computer

Una volta esportato il certificato, è possibile procedere con lo spostamento degli altri dati dell'utente, come i file effettivi, sul nuovo computer.

Se si utilizza lo strumento USMT per spostare i dati crittografati da un computer a un altro, è necessario specificare l'indicatore **/efs:copyraw** per consentire a USMT di leggere l'intero flusso di dati crittografati dai file di origine. Nel caso non venga specificato tale indicatore o vengano utilizzati altri strumenti (quali **xcopy** o **robocopy**) per spostare i file, questi verranno decrittografati dal computer di origine prima di essere copiati.

##### Verificare i file migrati

Una volta spostati i certificati e i file sul nuovo computer, è opportuno verificare che la migrazione sia avvenuta correttamente tramite due operazioni:

-   Verificare che l'account utente che possiede i file possa aprirli.

-   Verificare che i file rimangano crittografati controllandone gli attributi in Esplora risorse. Le icone dei file crittografati sono di colore verde; è possibile utilizzare anche la finestra di dialogo **Proprietà file** per verificare che l'attributo **Crittografato** sia abilitato.

#### Aggiornare i certificati DRA

Sarà necessario aggiornare i certificati DRA nei seguenti casi:

-   L'organizzazione sta eseguendo la migrazione dai DRA locali a un'infrastruttura DRA gestita centralmente.

-   È necessario aggiornare un criterio DRA gestito centralmente poiché i certificati DRA esistenti sono scaduti (o scadranno a breve).

-   È necessario aggiornare un criterio DRA gestito centralmente poiché il materiale della chiave DRA esistente è stato smarrito, collocato fuori posto o compromesso.

##### Considerazioni sull'aggiornamento dei certificati DRA

Per aggiornare i certificati DRA, è necessario prima richiedere o creare una o più coppie di chiavi DRA e certificati. In base all'ambiente, è possibile eseguire questa attività in uno dei seguenti modi:

-   Utilizzare lo switch /R con Cipher.exe.

-   Utilizzare le interfacce programmatiche o Web fornite da Servizi certificati Microsoft.

-   Utilizzare il meccanismo di richiesta della CA di terze parti esistente.

La richiesta deve utilizzare un modello di DRA appropriato affinché il certificato emesso sia utilizzabile come un DRA.

Dopo aver richiesto e ottenuto i nuovi certificati DRA, è necessario collegarli a Criteri di gruppo appropriati che vengono applicati a tutti i computer per cui si desidera aggiornare le informazioni del DRA. Accertarsi che l'oggetto Criteri di gruppo utilizzato venga applicato correttamente ai nuovi certificati DRA in più unità organizzative, domini di Active Directory e foreste di Active Directory. Dovrebbe essere possibile utilizzare il GPO Criterio dominio predefinito di Active Directory come base per la distribuzione delle nuove informazioni del DRA.

Dopo aver assegnato i nuovi certificati DRA a un GPO, è possibile eliminare i certificati DRA esistenti. Tuttavia, in questo modo non sarà più possibile recuperare i file creati con i certificati DRA esistenti. Prima di eliminarli, accertarsi di disporre di una copia che consenta di recuperare i file crittografati.

Le modifiche del DRA non verranno applicate sui singoli computer fino a quando questi computer non aggiorneranno le impostazioni di Criteri di gruppo. È possibile attendere il successivo aggiornamento del criterio di protezione (effettuato ogni 90 minuti per impostazione predefinita), eseguire il comando **gpupdate /force** sui computer coinvolti o riavviarli.

Sarebbe opportuno, inoltre, archiviare i certificati e la coppia di chiavi DRA per una maggiore protezione della chiave privata. Successivamente, è necessario eliminare la coppia di chiavi e il certificato dall'archivio di certificati dell'utente di qualsiasi utente che abbia importato il certificato e la coppia di chiavi. Durante questa operazione, accertarsi di selezionare la casella di controllo **Elimina la chiave privata se l'esportazione ha esito positivo** nell'esportazione guidata.

Dopo aver aggiornato le informazioni del DRA, è possibile procedere con l'aggiornamento dei file protetti con EFS sui computer di destinazione, come descritto nella sezione successiva.

#### Aggiornare i file per i nuovi certificati DRA o dell'utente

Dopo aver modificato o aggiornato i DRA utilizzati nell'organizzazione, è necessario aggiornare qualsiasi file protetto dal DRA precedente. È possibile effettuare questa operazione manualmente aprendo e salvando ogni singolo file, ma questo metodo richiede tempo ed è soggetto ad errori. È anche possibile utilizzare lo switch /U con il comando Cipher.exe, che attraversa il disco locale e aggiorna le informazioni del DRA per ogni file crittografato rilevato.

Durante questo processo, è possibile incorporare le seguenti operazioni:

-   Riportare l'output di **Cipher /U** su un registro errori e archiviarlo in un percorso centralizzato (come una condivisione di rete).

-   Prendere in considerazione l'utilizzo dell'indicatore /I per imporre a Cipher.exe di ignorare gli errori. In caso contrario, quando **Cipher /U** rileva file occupati o bloccati, non è in grado di aggiornarli e l'intero processo di aggiornamento non riesce.

-   È possibile creare uno script per eseguire l'aggiornamento invece di utilizzare **Cipher /U** dalla riga di comando. Dato che l'esecuzione dello script può richiedere molto tempo, potrebbe non essere appropriato utilizzarlo durante la procedura di accesso. Tuttavia, è possibile pianificarne l'esecuzione sui computer degli utenti o chiedere loro di richiamarlo manualmente quando lo considerano più opportuno.

[](#mainsection)[Inizio pagina](#mainsection)

### Ulteriori informazioni

-   [Configuring Active Directory to Back up Windows BitLocker Drive Encryption and Trusted Platform Module Recovery Information (in inglese)](http://go.microsoft.com/fwlink/?linkid=67438)

-   [Come utilizzare lo strumento BitLocker Recovery Password Viewer per Utenti e computer di Active Directory per visualizzare le password di ripristino per Windows Vista](http://support.microsoft.com/kb/928202)

-   [Come utilizzare lo strumento BitLocker Repair per ripristinare i dati da un volume crittografato in Windows Vista](http://support.microsoft.com/kb/928201)

**Download**

[Download di Data Encryption Toolkit for Mobile PC (in inglese)](http://go.microsoft.com/fwlink/?linkid=81666)

**Notifiche di aggiornamento**

[Iscriviti per ricevere informazioni su aggiornamenti e nuovi rilasci](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti**

[Inviaci i tuoi commenti o suggerimenti](mailto:secwish@microsoft.com?oggetto=data%20encryption%20toolkit%20for%20mobile%20pc,%20guida%20alla%20pianificazione%20e%20all'implementazione%20di%20data%20encryption%20toolkit)

[](#mainsection)[Inizio pagina](#mainsection)
