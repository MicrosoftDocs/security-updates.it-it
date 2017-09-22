---
TOCTitle: 'Data Encryption Toolkit for Mobile PC: Capitolo 3: crittografia del file system'
Title: 'Data Encryption Toolkit for Mobile PC: Capitolo 3: crittografia del file system'
ms:assetid: 'dc2cde72-a84d-4716-9a30-f62b608efda1'
ms:contentKeyID: 20213183
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc162818(v=TechNet.10)'
---

Data Encryption Toolkit for Mobile PC - Analisi della protezione
================================================================

### Capitolo 3: crittografia del file system

Pubblicato: 4 aprile 2007

Microsoft® Windows® XP e Windows Vista™ consentono la protezione dei dati e il ripristino dei dati protetti tramite EFS (Encrypting File System). EFS è una tecnologia di crittografia dei dati che può essere applicata a singoli file o a tutti i file presenti in una cartella specifica. I file EFS non possono essere decodificati senza il materiale della chiave corrispondente. Inoltre, è importante notare che a differenza di Microsoft BitLocker™ Drive Encryption (BitLocker), EFS non può essere applicato a qualsiasi file necessario per avviare il sistema operativo.

Sebbene BitLocker garantisca la crittografia di tutti i dati sull'intero volume di sistema, EFS ha il vantaggio di essere più preciso e flessibile durante la configurazione della crittografia per uno o più utenti di un solo computer. Ad esempio, è possibile utilizzare EFS per crittografare i file di dati presenti in una rete a cui accedono diversi utenti, uno scenario che va oltre le possibilità di BitLocker.

EFS fornisce una crittografia per utente proteggendo i file con una chiave accessibile solo all'utente e a tutti gli agenti di recupero autorizzati. Un utente malintenzionato che riesce a ottenere delle copie dei file non sarà in grado di leggerle a meno che durante l'accesso come utente che ha crittografato i file non ottenga anche il materiale della chiave o la copia dei file direttamente dalla posizione di origine in un altra posizione.

##### In questa pagina

[](#egaa)[EFS in Windows XP](#egaa)
[](#efaa)[EFS in Windows Vista](#efaa)
[](#eeaa)[Opzione EFS: EFS con Archiviazione chiavi software](#eeaa)
[](#edaa)[Opzione EFS: EFS con Smart Card](#edaa)
[](#ecaa)[Riepilogo dell'analisi dei rischi EFS](#ecaa)
[](#ebaa)[Ulteriori informazioni](#ebaa)

### EFS in Windows XP

Nonostante EFS fosse disponibile in Windows 2000, l'implementazione in Windows XP e Windows Server® 2003 offriva importanti funzionalità aggiuntive, tra cui:

-   Maggiori potenzialità di recupero dati.

-   Supporto completo per il controllo della revoca nei certificati utilizzati durante la condivisione dei file crittografati.

-   L'interfaccia utente cambia in Esplora risorse per consentire di individuare e verificare con facilità i file protetti.

-   Supporto per cartelle offline crittografate in Windows XP.

-   Supporto multiutente per i file crittografati.

-   Supporto per Microsoft Enhanced e Strong Cryptographic Service Provider (CSP).

-   Crittografia end-to-end mediante EFS su WebDAV.

Informazioni dettagliate su questi miglioramenti EFS per Windows XP sono disponibili nell'articolo "[Encrypting File System in Windows XP and Windows Server 2003](http://www.microsoft.com/technet/prodtechnol/winxppro/deploy/cryptfs.mspx)" (in inglese).

In tutti gli scenari EFS descritti in questo capitolo, un utente che ha effettuato l'accesso è in grado di abilitare la crittografia nei file e nelle cartelle mediante l'interfaccia **Attributi avanzati** di Esplora risorse.

![](images/Cc162818.c43d3fd1-4a4f-4ad0-8462-5a6eab0bfbb4(it-it,TechNet.10).gif)

**Figura 3.1. Finestra di dialogo Attributi avanzati di Windows XP**

Quando un file viene crittografato per la prima volta in una cartella, all'utente viene chiesto se desidera crittografare solo il file selezionato o l'intera cartella.

Per quelle organizzazioni che richiedono maggiore controllo dei criteri di crittografia EFS, è possibile gestire EFS anche centralmente tramite oggetti Criteri di gruppi (GPO) in modo da distribuire automaticamente gli script che utilizzano l'utilità Cipher.exe per configurare la crittografia nell'intera organizzazione.

![](images/Cc162818.note(it-it,TechNet.10).gif)**Nota:**

Entrambe le modalità EFS basate su software e smart card richiedono la presenza del relativo certificato per ogni operazione. Ad esempio, EFS basato su smart card richiede la presenza della scheda per ogni crittografia o decrittografia. Tale funzionalità impedisce agli utenti di crittografare accidentalmente i file utilizzando un certificato privo della relativa chiave privata. In assenza della chiave privata il certificato non può essere utilizzato per la crittografia.

[](#mainsection)[Inizio pagina](#mainsection)

### EFS in Windows Vista

EFS è disponibile nelle versioni Business, Enterprise e Ultimate di Windows Vista e sarà disponibile nella versione di Windows Server "Longhorn". Windows Vista fornisce importanti miglioramenti aggiuntivi a EFS, che includono quanto riportato di seguito:

-   Uso delle chiavi crittografiche memorizzate direttamente sulle smart card per la crittografia EFS.

-   Creazione e selezione guidata dei certificati utilizzati per EFS.

-   Migrazione guidata dei file da una smart card vecchia in una nuova.

-   Crittografia dei file di paging del sistema durante l'attivazione di EFS.

-   Nuove opzioni di Criteri di gruppo che consentono agli amministratori di definire e implementare i criteri organizzativi di EFS. Tali opzioni consentono di richiedere smart card per EFS, applicare la crittografia del file di paging, stabilire le lunghezze minime delle chiavi per EFS e applicare la crittografia della cartella Documenti dell'utente.

-   La maggiore capacità di gestire con precisione le funzionalità EFS in Windows Vista viene illustrata nella nuova interfaccia utente:

![](images/Cc162818.44c4c3c8-7669-4318-8847-1d5a56121c14(it-it,TechNet.10).gif)

**Figura 3.2. Interfaccia di gestione EFS di Windows Vista**

Nella parte restante di questo capitolo vengono descritte due opzioni EFS, nonché il livello di protezione fornito da ciascuna di esse.

[](#mainsection)[Inizio pagina](#mainsection)

### Opzione EFS: EFS con Archiviazione chiavi software

Questa opzione EFS richiede computer basati solo su Windows XP o Windows Vista.

La sequenza logica del processo di crittografia EFS in questa opzione viene illustrata nella seguente figura:

![](images/Cc162818.67dc08b1-9271-4491-b617-43ccb0020ebc(it-it,TechNet.10).jpg)

**Figura 3.3. Processo di crittografia EFS**

Di seguito sono riportate le procedure della sequenza di crittografia illustrata:

1.  L'utente crea un nuovo file in una cartella crittografata.

2.  Viene generata una chiave di crittografia dei file (FEK) simmetrica in modo casuale.

3.  Il sistema operativo controlla l'archivio certificati dell'utente alla ricerca di un certificato che disponga degli indicatori d'uso della chiave appropriati. In assenza di un certificato appropriato, ne viene generato uno automaticamente.

4.  Viene utilizzato DPAPI (Data Protection Application Programming Interface) per crittografare e memorizzare la chiave privata associata al certificato dell'utente.

5.  La chiave di crittografia dei file (FEK) viene crittografata mediante la chiave pubblica del certificato e memorizzata nei metadati del file.

6.  La chiave FEK viene utilizzata per crittografare ciascun blocco di dati.

7.  I blocchi crittografati vengono scritti sul disco.

La sequenza logica del processo di decrittografia EFS in questa opzione viene illustrata nella seguente figura:

![](images/Cc162818.8e90f3ca-64ed-456e-be71-29bf3388699b(it-it,TechNet.10).jpg)

**Figura 3.4. Processo di decrittografia EFS**

Di seguito sono riportate le procedure nella sequenza di decrittografia illustrata:

1.  L'accesso dell'utente viene convalidato localmente o da un controller di dominio.

2.  L'utente tenta di accedere a un file crittografato.

3.  Viene utilizzato DPAPI per recuperare la chiave privata associata al certificato X.509 dell'utente e per decrittografare tale chiave mediante una chiave derivata dalla credenziale di accesso dell'utente.

4.  La chiave FEK viene recuperata dal file e decrittografata con la chiave privata ottenuta nel passaggio precedente;

5.  inoltre, viene utilizzata per decrittografare ciascun blocco del file man mano che viene richiesto.

6.  I dati decrittografati vengono inoltrati all'applicazione richiedente.

Ulteriori informazioni sul comportamento dell'implementazione di EFS sono disponibili in [Encrypting File System Technical Reference](http://technet.microsoft.com/en-us/library/cc780166.aspx)(in inglese).

#### Rischi attenuati: EFS con Archiviazione chiavi software

Questa opzione EFS attenua i seguenti rischi per i dati:

-   **Dati crittografati leggibili dall'interno**. Un vantaggio specifico di EFS rispetto a BitLocker consiste nel fatto che le chiavi di crittografia vengono memorizzate in un archivio chiavi sicuro, protetto con le credenziali dell'utente. In questa configurazione, la credenziale è una password. Tuttavia, altri utenti autorizzati del computer possono effettuare l'accesso in modo interattivo o in rete, ma non saranno in grado di accedere ai file riservati presenti nel computer protetti da un altro utente con EFS a meno che quell'utente conceda espressamente l'accesso ai file.

-   **Individuazione della chiave tramite attacchi offline**. Supponendo che l'utente malintenzionato miri a una chiave quale FEK o a una chiave master DPAPI piuttosto che alla password dell'utente, la chiave di recupero EFS (ossia, la chiave privata per i certificati utilizzati da EFS) o la chiave master DPAPI potrebbero subire attacchi a forza bruta. Questa minaccia non dovrebbe preoccupare eccessivamente molte organizzazioni a causa della difficoltà di riuscita di questo tipo di attacco contro forti tipi di chiavi utilizzate da EFS.

-   **Perdita di dati non crittografati tramite il file di paging del sistema (solo Windows** **Vista)**. Windows Vista consente di crittografare i contenuti del file di paging del sistema che elimina una possibile fonte di perdita di dati. Questa funzionalità è stata implementata espressamente per proteggere le chiavi EFS di Windows Vista come la chiave DPAPI master (vedere il seguente argomento) durante il relativo utilizzo da parte del computer. Tale funzionalità consente anche di affrontare il rischio implicito in questa opzione EFS di rendere disponibili i dati non crittografati nel file di paging se è in uso da parte di un'applicazione. Le chiavi di crittografia utilizzate per crittografare il file di paging sono effimere e vengono generate nell'LSA (Local Security Authority). Tali chiavi non derivano dalla credenziale di accesso dell'utente o dal certificato X.509. Dopo la chiusura (o arresto) del computer, i dati crittografati del file di paging non possono essere recuperati o letti da qualsiasi metodo noto diverso rispetto a un attacco a forza bruta.

#### Attenuazioni e rischi residui: EFS con Archiviazione chiavi software

Questa opzione EFS non attenua i seguenti rischi senza ulteriori controlli e criteri:

-   **Computer in modalità di ibernazione**. Come nelle opzioni di BitLocker, se il computer non è stato configurato per richiedere la password quando si riattiva dallo stato di ibernazione o di standby, il sistema operativo non può percepire se l'utente corrente è l'utente appropriato. In una situazione di questo tipo l'utente malintenzionato può utilizzare il laptop come se fosse l'utente autorizzato. Un probabile attacco consiste nel copiare i dati di un certo interesse su un'unità rimovibile o in un percorso di rete. Tuttavia, se il computer è configurato in modo da richiedere le credenziali utente nel momento in cui si riattiva dallo stato di ibernazione o di standby, il rischio viene attenuato.

-   **Computer in modalità sospensione (standby)**. Stesse considerazioni evidenziate nella precedente spiegazione sull'attenuazione dei rischi.

-   **Computer lasciato con accesso effettuato e desktop sbloccato**. Dopo l'accesso al computer da parte dell'utente, sono disponibili le credenziali per decrittografare i certificati utilizzati per EFS. Da quel momento in poi i dati non crittografati diventano di facile accesso per chiunque acceda alla tastiera. La prevenzione più utile per questo tipo di rischio è rappresentata dalla formazione nell'ambito della consapevolezza in materia di protezione per gli utenti che potrebbero disporre di informazioni riservate nei propri computer.

-   **Individuazione della password di dominio/locale**. In questa configurazione, le chiavi EFS vengono decrittografate in una sequenza che comincia con una chiave derivata dalla password dell'utente. Tuttavia, se la password dell'utente è compromessa, la crittografia EFS risulta compromessa. Questo rischio può essere attenuato implementando criteri di password complessi per impedire attacchi, ad esempio attacchi con dizionario, e informando gli utenti sull'importanza della protezione delle password.

-   **Attacchi offline contro il sistema operativo**. EFS non fornisce alcuna protezione per il sistema operativo del computer o per i file di configurazione del sistema operativo in uno scenario di attacco offline.

-   **Attacchi online contro il sistema operativo**. Gli attacchi online contro il sistema operativo non vengono attenuati da questa opzione. Un utente malintenzionato in grado di eseguire il codice sul sistema operativo può rubare le chiavi crittografiche.

-   **Perdita di dati non crittografati tramite il file ibernazione**. EFS non fornisce alcuna protezione per il file ibernazione del sistema. Tale rischio può essere attenuato effettuando l'aggiornamento a Windows Vista, utilizzando BitLocker o disattivando l'ibernazione.

    ![](images/Cc162818.important(it-it,TechNet.10).gif)**Importante:**

    La disattivazione della modalità di ibernazione riduce la possibilità di utilizzo dei PC portatili. Tale operazione è particolarmente appropriata per i computer in cui vengono memorizzati dati estremamente preziosi, ma generalmente risultano più appropriati altri tipi di attenuazioni.

-   **Perdita di dati non crittografati tramite il file di paging del sistema (solo Windows** **XP)**. In Windows XP, non è possibile utilizzare EFS per crittografare qualsiasi file di sistema, compreso il file di paging del sistema. Se si accede a dati riservati tramite un'applicazione, i dati possono essere scritti sul disco mediante l'operazione di paging della memoria. Il rischio può essere ridotto effettuando l'aggiornamento a Windows Vista o configurando il computer in modo che non utilizzi il file di paging della memoria.

    ![](images/Cc162818.important(it-it,TechNet.10).gif)**Importante:**

    La disattivazione del file di paging della memoria attenua, in genere, le prestazioni del computer, a volte in modo significativo.

-   **Attacchi alla piattaforma**. Un computer configurato per l'uso di EFS con Archiviazione chiavi software manterrà le chiavi EFS sul disco e in memoria. Un attacco alla piattaforma che utilizza l'accesso diretto alla memoria o altre tecniche di manipolazione hardware potrebbe essere in grado di riconoscere il materiale della chiave.

-   **Fattore di autenticazione richiesto nel computer**. In questa opzione, non esistono altri fattori di autenticazione. L'unico fattore di autenticazione è il computer dell'utente o la password di rete.

-   **Errore dell'utente**. L'utente deve fare attenzione a non salvare i file che contengono dati sensibili in una posizione in cui EFS non è abilitato. Con Windows Vista questo rischio è in parte ridotto poiché dispone di un'opzione di configurazione EFS che consente la crittografia di tutti i file presenti nella cartella Documenti dell'utente. Tale funzionalità consente agli utenti di verificare con più facilità l'avvenuta crittografia di file e directory. Il rischio può essere attenuato anche mediante l'uso dello strumento Microsoft Encrypting File System Assistant (EFS Assistant viene fornito come parte di Solution Accelerator) che consente di automatizzare il processo di protezione dei file dell'utente con EFS.

[](#mainsection)[Inizio pagina](#mainsection)

### Opzione EFS: EFS con Smart Card

Le varie versioni di Windows offrono diverse possibilità per migliorare le caratteristiche di protezione di EFS. Le informazioni su tali possibilità vengono fornite nelle sottosezioni che seguono.

#### Accesso con Windows XP e Smart Card

**Per connettersi alla rete è necessaria una smart card** è un'impostazione dell'utente di dominio configurata tramite il servizio Active Directory. Tale configurazione richiede l'uso di una smart card da parte dell'utente per effettuare l'accesso al relativo account di dominio. Il rischio principale per EFS è che se la password di un utente è compromessa, un utente malintenzionato potrebbe effettuare l'accesso al computer utilizzando tale account e accedere a tutti i dati sul computer, compresi i dati protetti con EFS.

L'impostazione dei criteri di Active Directory che richiede una smart card per l'accesso migliora in modo significativo la sicurezza dell'account e, per estensione, la sicurezza di tutti i dati protetti con EFS. Grazie a questa impostazione è anche possibile proteggere i dati crittografati da eventuali attacchi offline, poiché potenzia la chiave utilizzata da EFS per la crittografia DPAPI. DPAPI agisce derivando una chiave dalle credenziali utente.

L'accesso con smart card può essere richiesto in due modalità differenti: per utente e per computer. In ciascuna modalità può essere attivato o applicato. Esistono delle differenze di protezione importanti tra le modalità, che includono quanto segue:

-   Mediante l'accesso applicato con smart card per utente, la chiave iniziale è sensibilmente più forte rispetto alla password tipica. Anziché effettuare un attacco con dizionario sulla password, è molto probabile che un utente malintenzionato effettui un attacco a forza bruta su una chiave privata resa sufficientemente lunga da risultare praticamente inaccessibile mediante l'uso di tecnologie correnti.

-   L'accesso applicato con smart card per computer fornisce maggiore sicurezza, per certi versi, rispetto all'accesso tramite password perché aggiunge un secondo fattore di autenticazione. Tuttavia, l'accesso con smart card per computer utilizza la smart card solo per l'autenticazione dell'accesso. Un utente malintenzionato in grado di ottenere la chiave master DPAPI crittografata può ancora effettuare un attacco a forza bruta in minor tempo rispetto a un attacco a forza bruta su una chiave master DPAPI protetta da un accesso con smart card per utente.

L'attivazione, ma non l'applicazione, di entrambi i tipi di accessi con smart card non aggiunge reale protezione della sicurezza in quanto consente all'utente di scegliere se utilizzare o meno l'accesso con smart card.

È possibile rintracciare ulteriori informazioni su DPAPI e sulla modalità con cui l'accesso con smart card influisce sulle chiavi DPAPI nell'articolo MSDN "[Windows Data Protection](http://msdn2.microsoft.com/en-us/library/ms995355.aspx)" (in inglese).

![](images/Cc162818.note(it-it,TechNet.10).gif)**Nota:**

Questa discussione sui rischi presuppone che le smart card vengano utilizzate insieme a un PIN non semplice e che la smart card implementi il blocco del PIN come protezione da eventuali intercettazioni del PIN.

La crittografia EFS in Windows XP con l'opzione di accesso con smart card viene illustrata nella seguente figura.

![](images/Cc162818.9106cca5-90c1-49dc-87f0-ec6605d165c9(it-it,TechNet.10).jpg)

**Figura 3.5. Crittografia EFS di Windows XP con accesso con smart card**

Di seguito sono riportate le procedure della sequenza di crittografia illustrata:

1.  L'utente crea un nuovo file in una cartella crittografata.

2.  Una chiave FEK simmetrica viene generata in modo casuale.

3.  Il sistema operativo controlla l'archivio certificati dell'utente alla ricerca di un certificato che disponga degli indicatori d'uso della chiave appropriati. In assenza di un certificato appropriato, ne viene generato uno automaticamente.

4.  DPAPI viene utilizzato per crittografare e memorizzare la chiave privata associata al certificato dell'utente. Questa crittografia risulta più forte rispetto all'opzione precedente a causa di una password più complessa utilizzata quando è richiesto l'accesso con smart card.

5.  La chiave di crittografia dei file (FEK) viene crittografata mediante la chiave pubblica del certificato e memorizzata nei metadati del file.

6.  La chiave FEK viene utilizzata per crittografare ciascun blocco di dati.

7.  I blocchi crittografati vengono scritti sul disco.

L'opzione decrittografia EFS in Windows XP con accesso con smart card viene illustrata nella seguente figura.

![](images/Cc162818.98911cc3-45af-44be-aa3b-ffa37b9e520d(it-it,TechNet.10).jpg)

**Figura 3.6. Sequenza di decrittografia EFS per Windows XP con accesso con smart card**

Di seguito sono riportate le procedure nella sequenza di decrittografia illustrata:

1.  L'accesso con smart card dell'utente viene convalidato localmente o da un controller di dominio.

2.  L'utente tenta di accedere a un file crittografato.

3.  La chiave privata corretta viene recuperata dall'archivio DPAPI dell'utente. DPAPI decrittografa la chiave privata utilizzando una chiave derivata dalla password utente complessa, creata casualmente, che viene applicata all'account utente quando su tale account è attiva l'impostazione **Richiedi accesso con smart card**.

4.  La chiave FEK viene recuperata dal file e decrittografata con la chiave privata recuperata nel passaggio precedente.

5.  Man mano che l'applicazione legge ogni blocco del file, la chiave FEK viene utilizzata per decrittografare il blocco prima di inoltrarlo all'applicazione richiedente.

#### Windows Vista e EFS con Smart Card

Windows Vista offre nuove e potenti funzionalità di protezione che aumentano la sicurezza e l'utilizzabilità di EFS mediante una maggiore integrazione con la tecnologia delle smart card. In Windows XP, l'accesso con smart card viene sfruttato indirettamente per il modo in cui migliora le caratteristiche delle chiavi DPAPI. Tuttavia, in Windows Vista le smart card possono essere utilizzate direttamente per crittografare i file con EFS. Le nuove funzionalità non richiedono l'accesso dell'utente con smart card, sebbene anche questo scenario funzioni. Al contrario, se la configurazione di EFS prevede l'uso di smart card, all'utente viene chiesto di inserire la smart card e fornire un PIN.

L'implementazione ovvia di EFS e smart card consiste nel crittografare direttamente la chiave FEK utilizzando la chiave pubblica, quindi di decrittografare la chiave FEK mediante la chiave privata che corrisponde a un certificato sulla smart card. Sebbene questa opzione sia semplice e sicura, si registra un impatto sulle prestazioni durante la decrittografia di ciascun file a cui è stato effettuato l'accesso in quanto l'operazione di decrittografia della chiave privata implica una comunicazione con la smart card e la CPU della smart card è molto lenta rispetto a quella del computer host.

Un altro problema insito all'implementazione ovvia è che la smart card sia sempre presente perché ogni tentativo di decrittografia di un file richiede che la chiave privata decrittografi correttamente la FEK. Per migliorare le prestazioni e l'utilizzabilità dell'opzione EFS con smart card, EFS viene configurato per impostazione predefinita in modo da derivare una chiave simmetrica dalla chiave privata sulla smart card e utilizzare questa chiave per decrittografare e crittografare le chiavi FEK associate ai file crittografati. Nella configurazione predefinita, la chiave simmetrica derivata viene memorizzata nella cache dal sistema operativo in modo che le successive operazioni di crittografia e decrittografia del file non richiedano l'uso della smart card e delle relative chiavi private o pubbliche.

L'opzione **Crea da smart card una chiave utente in grado di memorizzare nella cache** riportata nella **Figura 3.2. Interfaccia di gestione EFS di Windows Vista** consente di impostare se la chiave simmetrica verrà derivata e memorizzata nella cache. Se questa opzione viene deselezionata, una chiave simmetrica non viene né derivata né memorizzata nella cache e la chiave FEK viene crittografata e decrittografata direttamente mediante le chiavi della smart card. La presente guida utilizza le espressioni *modalità chiave memorizzata nella cache* e *modalità chiave non memorizzata nella cache* per descrivere queste due modalità operative differenti con caratteristiche di sicurezza univoche.

##### Modalità chiave memorizzata nella cache

In modalità chiave memorizzata nella cache, la chiave simmetrica derivata viene memorizzata nella cache nella memoria LSA protetta dal sistema operativo fino alla scadenza del timeout della cache, che può essere configurata. Il timeout predefinito della cache è di otto ore del tempo di inattività del sistema. Qualsiasi operazione che utilizza la chiave derivata ripristinerà il periodo di timeout della cancellazione. In base alla configurazione, la cancellazione della cache della chiave EFS dovrebbe verificarsi quando l'utente blocca il computer o rimuove la smart card. La modalità chiave memorizzata nella cache migliora sensibilmente le prestazioni e consente all'amministratore di configurare EFS in modo che i file crittografati possano essere crittografati e decrittografati senza la presenza della smart card nel lettore.

![](images/Cc162818.note(it-it,TechNet.10).gif)**Nota:**

Per ulteriori dettagli su come viene implementata la modalità cache in Windows Vista, vedere [Guida alla protezione di Windows Vista](http://www.microsoft.com/technet/windowsvista/security/guide.mspx).

La crittografia EFS in modalità chiave memorizzata nella cache viene illustrata nella seguente figura:

![](images/Cc162818.5cf0f6c0-5a9c-4c49-80da-5690297f89bc(it-it,TechNet.10).jpg)

**Figura 3.7. Sequenza di crittografia EFS per Windows Vista con smart card - Modalità chiave memorizzata nella cache**

Di seguito sono riportate le procedure della sequenza di crittografia illustrata:

1.  L'utente crea un nuovo file in una cartella crittografata.

2.  Se nessuna delle seguenti condizioni è vera, all'utente verrà chiesto di inserire la smart card e immettere il PIN:

    -   L'utente non ha effettuato l'accesso al computer con la sua smart card.

    -   Di recente, l'utente non ha utilizzato la propria smart card per accedere a un file EFS.

    -   Il PIN della smart card non è stato memorizzato nella cache da un'operazione EFS recente o la cache del PIN è stata eliminata a causa di inattività.

3.  Una chiave FEK viene generata in modo casuale.

4.  Una chiave simmetrica viene derivata dalla chiave privata della smart card se entrambe le seguenti condizioni sono vere:

    -   Quando viene crittografato il primo file.

    -   Quando la chiave derivata non è presente nella cache.

5.  La chiave FEK viene crittografata mediante la chiave simmetrica del certificato e memorizzata nei metadati del file.

6.  La chiave simmetrica derivata viene memorizzata nella cache nella memoria protetta da LSA.

7.  La chiave FEK viene utilizzata per crittografare ciascun blocco di dati.

8.  I blocchi crittografati vengono scritti sul disco.

La decrittografia EFS in modalità chiave memorizzata nella cache viene illustrata nella seguente figura:

![](images/Cc162818.9239422a-18b2-4d59-a9d4-3d6f7a0ffa8d(it-it,TechNet.10).jpg)

**Figura 3.8. Sequenza di decrittografia EFS per Windows Vista con smart card - Modalità chiave memorizzata nella cache**

Di seguito sono riportate le procedure nella sequenza di decrittografia illustrata:

1.  L'utente tenta di accedere a un file crittografato.

2.  Se nessuna delle seguenti condizioni è vera, all'utente verrà chiesto di inserire la smart card e immettere il PIN:

    -   L'utente non ha effettuato l'accesso al computer con la sua smart card.

    -   Di recente, l'utente non ha utilizzato la propria smart card per accedere a un file EFS.

    -   Il PIN della smart card non è stato memorizzato nella cache da un'operazione EFS recente o la cache del PIN è stata eliminata a causa di inattività.

3.  Una chiave simmetrica viene derivata dalla chiave privata basata sulla smart card se non è già stata memorizzata nella cache. Dopo il primo utilizzo, la chiave derivata viene memorizzata nella cache nella memoria protetta da LSA.

4.  La chiave FEK viene recuperata dal file e decrittografata utilizzando la chiave simmetrica derivata.

5.  Man mano che l'applicazione legge ogni blocco del file, la chiave FEK viene utilizzata per decrittografare il blocco prima di inoltrarlo all'applicazione richiedente.

##### Modalità chiave non memorizzata nella cache

La crittografia EFS in Windows Vista con EFS attiva in modalità chiave non memorizzata nella cache viene illustrata nella seguente figura.

![](images/Cc162818.a1c07b9d-de1a-407a-8ce3-6177d8b91e27(it-it,TechNet.10).jpg)

**Figura 3.9. Sequenza di crittografia EFS per Windows Vista con smart card - Modalità chiave non memorizzata nella cache**

Di seguito sono riportate le procedure della sequenza di crittografia illustrata:

1.  L'utente crea un nuovo file in una cartella crittografata.

2.  Se la smart card dell'utente non è presente, all'utente verrà chiesto di inserirla.

3.  Una chiave FEK simmetrica viene generata in modo casuale.

4.  La chiave di crittografia dei file (FEK) viene crittografata mediante la chiave pubblica del certificato e memorizzata nei metadati del file.

5.  Man mano che l'applicazione scrive ciascun blocco di dati, questo viene crittografato con la chiave FEK.

6.  Il blocco crittografato viene scritto sul disco.

La decrittografia EFS in modalità chiave non memorizzata nella cache viene illustrata nella seguente figura:

![](images/Cc162818.b6906b39-323a-463c-aecc-2252dc8be65e(it-it,TechNet.10).jpg)

**Figura 3.10. Sequenza di decrittografia EFS per Windows Vista con smart card - Modalità chiave non memorizzata nella cache**

Di seguito sono riportate le procedure nella sequenza di decrittografia illustrata:

1.  L'utente tenta di accedere a un file crittografato.

2.  Se la smart card dell'utente non è presente, all'utente verrà chiesto di inserirla. Se nessuna delle seguenti condizioni è vera, all'utente verrà chiesto di inserire il PIN:

    -   L'utente non ha effettuato l'accesso al computer con la sua smart card.

    -   Di recente, l'utente non ha utilizzato la propria smart card per accedere a un file EFS.

    -   Il PIN della smart card non è stato memorizzato nella cache da un'operazione EFS recente o la cache del PIN è stata eliminata a causa di inattività.

3.  I metadati EFS per il file vengono recuperati dal file e la chiave FEK crittografata viene inviata alla smart card.

4.  La smart card decrittografa i metadati per ottenere la chiave FEK che viene a sua volta restituita al sistema operativo.

5.  Man mano che l'applicazione legge ogni blocco del file, la chiave FEK viene utilizzata per decrittografare il blocco prima di inoltrarlo all'applicazione richiedente.

#### Rischi attenuati: EFS con Smart Card

L'opzione EFS con Smart Card attenua i seguenti rischi per i dati:

-   **Computer in modalità di ibernazione (solo modalità chiave non memorizzata nella cache di Windows Vista)**. Windows Vista può richiedere l'autenticazione di una smart card ogni volta che si accede a un file protetto da EFS. Questa modalità di funzionamento attenua in realtà questo rischio, sebbene non avvenga con la modalità smart card predefinita della chiave memorizzata nella cache.

-   **Computer in modalità sospensione (standby) (solo modalità chiave non memorizzata nella cache di Windows Vista)**. Stesse considerazioni evidenziate nella precedente spiegazione sull'attenuazione dei rischi (modalità di ibernazione).

-   **Computer lasciato con accesso effettuato e desktop sbloccato (solo modalità chiave non memorizzata nella cache di Windows Vista)**. Windows Vista può richiedere l'autenticazione della smart card ogni volta che si accede a un file protetto da EFS. Questa funzionalità, nota anche come modalità chiave non memorizzata nella cache, è stata trattata in precedenza nel presente capitolo e attenua, in realtà, tale rischio richiedendo la presenza della smart card per tutti gli accessi al file EFS. Sebbene questo scenario potrebbe presentare potenzialmente gravi problemi di utilizzabilità, rimane una valida opzione per quelle organizzazioni che richiedono una soluzione di crittografia più sicura per i propri dati riservati e di un certo rilievo.

-   **Individuazione della password di dominio/locale**. Come illustrato nella sezione "Rischi di protezione dei dati" del Capitolo 1, un utente malintenzionato sfrutta sempre il collegamento più debole. Sfortunatamente per quelle persone responsabili della protezione dei sistemi IT, il collegamento più debole è rappresentato spesso dall'utente che sceglie password non adeguate o che scrive password valide su un pezzo di carta e le attacca al monitor. Dopo che l'organizzazione implementa l'autenticazione a due fattori basata sulla smart card per la protezione della rete, è necessario aumentare la protezione di EFS tramite l'uso di un criterio "Per l'accesso interattivo è necessaria una smart card". In Windows Vista, è possibile che venga richiesta l'autenticazione a due fattori per accedere ai dati sensibili per le situazioni in cui l'accesso con smart card non può essere attivato mediante l'abilitazione dell'impostazione di **richiesta della smart card per EFS**.

-   **Dati crittografati leggibili dall'interno**. L'opzione EFS con smart card fornisce un'attenuazione reale per questo rischio aggiungendo un fattore di autenticazione aggiuntivo.

-   **Individuazione della chiave tramite attacchi offline**. Supponendo che l'utente malintenzionato miri a una chiave quale FEK o a una chiave master DPAPI piuttosto che alla password dell'utente, la chiave di recupero EFS (ossia, la chiave privata per i certificati utilizzati da EFS) o la chiave master DPAPI potrebbero subire attacchi a forza bruta. Questa minaccia non dovrebbe preoccupare eccessivamente molte organizzazioni a causa della difficoltà di riuscita di questo tipo di attacco contro forti tipi di chiavi utilizzate da EFS.

-   **Perdita di dati non crittografati tramite il file di paging del sistema (solo Windows** **Vista)**. Windows Vista può essere configurato per crittografare il file di paging del sistema che riduce efficacemente questo rischio.

-   **Attacchi alla piattaforma (solo modalità chiave non memorizzata nella cache di Windows Vista)**. In modalità chiave memorizzata nella cache, un computer configurato per l'uso di EFS con archiviazione chiavi smart card manterrà in memoria le chiavi EFS e un attacco alla piattaforma potrebbe riuscire a recuperarle. EFS utilizzato con archiviazione chiavi per smart card non memorizzata nella cache attenua efficacemente questo attacco. Per recuperare il materiale della chiave è necessario un attacco diretto alla smart card.

-   **Fattore di autenticazione richiesto nel computer**. Con questa opzione l'utente deve fornire il PIN e il fattore di autenticazione fisico che garantisce l'attenuazione multifattore vera per tale rischio.

#### Attenuazioni e rischi residui: EFS con Smart Card

L'opzione EFS con smart card non attenua i seguenti rischi senza ulteriori controlli e criteri:

-   **Computer in modalità di ibernazione (solo modalità chiave memorizzata nella cache di Windows XP e Windows Vista)**. Se il computer non è stato configurato per richiedere la password quando si riattiva dallo stato di ibernazione o di standby, il sistema operativo non può percepire se l'utente corrente è l'utente appropriato. In una situazione di questo tipo l'utente malintenzionato può utilizzare il laptop come se fosse l'utente autorizzato. Un probabile attacco consiste nel copiare i dati di un certo interesse su un'unità rimovibile o in un percorso di rete. Tuttavia, se il computer è configurato in modo da richiedere le credenziali utente nel momento in cui si riattiva dallo stato di ibernazione o di standby, il rischio viene attenuato. Nell'opzione EFS con smart card, questo rischio può essere attenuato come descritto in precedenza quando si utilizza Windows Vista.

-   **Computer in modalità sospensione (solo modalità chiave memorizzata nella cache di Windows XP e Windows Vista)**. Stesse considerazioni evidenziate nella precedente spiegazione sui rischi residui (modalità ibernazione).

-   **Computer lasciato con accesso effettuato e desktop sbloccato (solo modalità chiave memorizzata nella cache di Windows XP e Windows Vista)**. Dopo l'accesso al computer da parte dell'utente, sono disponibili le credenziali per decrittografare i certificati utilizzati per EFS. Da quel momento in poi i dati non crittografati diventano di facile accesso per chiunque acceda alla tastiera. La prevenzione più utile per questo tipo di rischio è rappresentata dalla formazione nell'ambito della consapevolezza in materia di protezione per gli utenti che potrebbero disporre di informazioni riservate nei propri computer. Nell'opzione EFS con smart card, questo rischio può essere attenuato come descritto in precedenza quando si utilizza Windows Vista.

-   **Attacchi offline contro il sistema operativo**. EFS non fornisce alcuna protezione per il sistema operativo del computer o per i file di configurazione del sistema operativo in uno scenario di attacco offline.

-   **Attacchi online contro il sistema operativo (solo modalità chiave memorizzata nella cache di Windows XP e Windows Vista)**. Gli attacchi online contro il sistema operativo *non* vengono attenuati da questa opzione. Tuttavia, l'uso di Windows Vista con smart card in modalità chiave non memorizzata nella cache attenua questo rischio rendendo impossibile all'utente malintenzionato il recupero delle chiavi EFS perché non sono accessibili ai programmi in esecuzione sul sistema operativo host.

-   **Perdita di dati non crittografati tramite il file ibernazione**. EFS non fornisce alcuna protezione per il file ibernazione del sistema. Tale rischio può essere attenuato effettuando l'aggiornamento a Windows Vista, utilizzando BitLocker o disattivando l'ibernazione.

    ![](images/Cc162818.important(it-it,TechNet.10).gif)**Importante:**

    La disattivazione della modalità di ibernazione riduce la possibilità di utilizzo dei PC portatili. Tale operazione è particolarmente appropriata per i computer in cui vengono memorizzati dati estremamente preziosi, ma generalmente risultano più appropriati altri tipi di attenuazioni.

-   **Perdita di dati non crittografati tramite il file di paging del sistema (solo Windows** **XP)**. In Windows XP, non è possibile utilizzare EFS per crittografare qualsiasi file di sistema, compreso il file di paging del sistema. Se si accede a dati riservati tramite un'applicazione, i dati possono essere scritti sul disco mediante l'operazione di paging della memoria. Il rischio può essere ridotto effettuando l'aggiornamento a Windows Vista o configurando il computer in modo che non utilizzi il file di paging della memoria.

    ![](images/Cc162818.important(it-it,TechNet.10).gif)**Importante:**

    La disattivazione del file di paging della memoria attenua, in genere, le prestazioni del computer, a volte in modo significativo.

-   **Attacchi alla piattaforma (solo modalità chiave memorizzata nella cache di Windows XP e Windows Vista)**. In modalità chiave memorizzata nella cache, un computer manterrà in memoria le chiavi EFS e un attacco alla piattaforma riuscirà a recuperarle.

-   **Errore dell'utente**. Gli utenti devono fare attenzione a non salvare i file che contengono dati sensibili in una posizione in cui non è abilitato EFS. Con Windows Vista questo rischio è in parte ridotto poiché dispone di un'opzione di configurazione EFS che consente la crittografia di tutti i file presenti nella cartella Documenti dell'utente. Tale funzionalità consente agli utenti di verificare con più facilità l'avvenuta crittografia di file e directory. Il rischio può essere attenuato anche mediante l'uso dello strumento EFS Assistant (fornito come parte di Solution Accelerator) che consente di automatizzare il processo di protezione dei file dell'utente con EFS.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo dell'analisi dei rischi EFS

Nella tabella riportata di seguito vengono elencati i rischi per i dati e viene indicato se le differenti opzioni di EFS sono in grado di attenuare ogni rischio. Per i computer basati su Windows XP, viene attivata l'impostazione utente di dominio **Richiedi accesso con smart card**. Per i computer basati su Windows Vista, sul computer vengono attivate le impostazioni EFS **Richiedi smart card per EFS** e **Abilita crittografia del file di paging**.

I rischi che possono essere attenuati con opzioni specifiche sono indicati con la lettera **Y**. I trattini **-** indicano i rischi per cui l'opzione specifica fornisce un'attenuazione ridotta o inesistente.

**Tabella 3.1. Attenuazione dei rischi di EFS**

![](images/Cc162818.0d76df62-1c23-49d8-beb0-9bd64db9f966(it-it,TechNet.10).gif)
[](#mainsection)[Inizio pagina](#mainsection)

### Ulteriori informazioni

-   [Encrypting File System Technical Reference (in inglese)](http://technet.microsoft.com/en-us/library/cc780166.aspx)

-   [Windows Data Protection (in inglese)](http://msdn2.microsoft.com/en-us/library/ms995355.aspx)

-   [Guida alla protezione di Windows Vista](http://www.microsoft.com/technet/windowsvista/security/guide.mspx)

**Download**

[Get the Data Encryption Toolkit for Mobile PCs (in inglese)](http://go.microsoft.com/fwlink/?linkid=81666)

**Partecipa**

[Iscriviti per partecipare al programma Data Encryption Toolkit Beta](https://connect.microsoft.com/invitationuse.aspx?programid=790&invitationid=desa-r7gd-3f73&siteid=14)

**Notifiche di aggiornamento**

[Iscriviti per ricevere informazioni su aggiornamenti e nuovi rilasci](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti**

[Inviaci i tuoi commenti o suggerimenti](mailto:secwish@microsoft.com?oggetto=analisi%20della%20protezione%20di%20data%20encryption%20toolkit%20for%20mobile%20pc%20su%20technet)

[](#mainsection)[Inizio pagina](#mainsection)
