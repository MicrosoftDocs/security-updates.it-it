---
TOCTitle: 'Data Encryption Toolkit for Mobile PC: Capitolo 2: Crittografia unità BitLocker'
Title: 'Data Encryption Toolkit for Mobile PC: Capitolo 2: Crittografia unità BitLocker'
ms:assetid: '4e6ce820-fcac-495a-9f23-73d65d846638'
ms:contentKeyID: 20213166
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc162804(v=TechNet.10)'
---

Data Encryption Toolkit for Mobile PC - Analisi della protezione
================================================================

### Capitolo 2: Crittografia unità BitLocker

Pubblicato: 4 aprile 2007

Crittografia unità Microsoft® BitLocker™ è una nuova funzionalità di protezione completa delle versioni Enterprise e Ultimate del sistema operativo Windows Vista™ che fornisce una significativa protezione dei dati offline e del sistema operativo stesso per il computer.

BitLocker è una tecnologia di crittografia completa dei volumi che consente di accertarsi che i dati che si trovano in un computer su cui è in esecuzione Windows Vista non vengano rivelati nel caso in cui il computer venga alterato o quando il sistema operativo installato è offline. È progettata per sistemi che abbiano un BIOS e un microchip TPM (Trusted Platform Module) compatibili. Se ci sono questi componenti, BitLocker li utilizza per fornire una migliore protezione ai dati e per assicurare prima l'integrità dei componenti di avvio. Questa funzionalità impedisce che i dati vengano rubati o visti da persone indesiderate crittografando l'intero volume.

Il TPM in genere è installato sulla scheda madre del computer e utilizza un bus hardware per comunicare con il resto del computer. I computer che contengono il TPM sono in grado di creare chiavi crittografiche e di crittografarle in modo che possano essere decrittografate esclusivamente tramite il TPM. Questo processo, spesso denominato *wrapping* o *binding* di una chiave, consente di proteggere la chiave da eventuali divulgazioni. Ogni TPM dispone di una chiave di wrapping principale, denominata chiave radice di archiviazione (SRK), che si trova all'interno del TPM. La parte privata di una coppia di chiavi creata nel TPM non è mai esposta ad altri componenti, software, processi o persone.

BitLocker ha due funzionalità principali:

-   Consente la crittografia per computer crittografando il contenuto del volume del sistema operativo. Chi effettua un attacco e rimuove il volume non potrà leggerlo a meno che non ottenga le chiavi e per ottenerle dovrebbe attaccare l'infrastruttura di ripristino o il TPM sul computer stesso.

-   Consente la crittografia completa dei volumi crittografando l'intero contenuto dei volumi protetti, inclusi i file utilizzati da Windows Vista, il settore di avvio e lo spazio del margine di flessibilità precedentemente assegnato ai file in uso. A chi effettua l'attacco viene pertanto impedito di ripristinare informazioni utili analizzando qualsiasi parte del disco se non dispone della chiave.

I meccanismi di ripristino esistono per utenti autorizzati che possono utilizzarli in condizioni in cui si renda necessario. Ad esempio, se la convalida effettuata dal TPM non avviene correttamente per la necessità di un aggiornamento, perché la scheda madre che contiene il TPM viene sostituita o perché il disco rigido che contiene il volume del sistema operativo viene spostato su un altro computer, il sistema entra in modalità di ripristino e l'utente deve utilizzare una chiave di ripristino che si trova su una periferica USB o nel servizio directory di Active Directory® per poter accedere di nuovo al volume.

Il processo di ripristino è uguale per tutti gli scenari di BitLocker. Se la chiave di ripristino è fisicamente separata dal computer (e pertanto non viene persa insieme al computer) e l'attacco non viene condotto dall'interno da qualcuno come l'amministratore del dominio, gli attacchi contro la chiave di ripristino sono molto difficili.

Dopo che BitLocker autentica l'accesso a un volume del sistema operativo protetto, il driver del filtro del file system BitLocker utilizza una chiave di crittografia completa dei volumi (FVEK) per crittografare e decrittografare in modo trasparente i settori del disco in cui si trovano i dati e leggere dal volume protetto. Quando il computer entra in modalità di ibernazione, un file ibernazione crittografato viene salvato nel volume protetto. In attesa di autenticazione dell'accesso, questo file salvato viene decrittografato quando il computer esce dalla modalità di ibernazione.

BitLocker supporta varie opzioni differenti, in base alla capacità hardware del dispositivo e al livello di protezione desiderato, tra cui:

-   BitLocker con TPM

-   BitLocker con periferica USB (Universal Serial Bus)

-   BitLocker con TPM e codice PIN

-   BitLocker con TPM e USB

##### In questa pagina

[](#egaa)[Opzione di BitLocker: BitLocker con TPM](#egaa)
[](#efaa)[Opzione di BitLocker: BitLocker con USB](#efaa)
[](#eeaa)[Opzione di BitLocker: BitLocker con TPM e PIN](#eeaa)
[](#edaa)[Opzione di BitLocker: BitLocker con TPM e periferica USB](#edaa)
[](#ecaa)[Riepilogo analisi dei rischi di BitLocker](#ecaa)
[](#ebaa)[Ulteriori informazioni](#ebaa)

### Opzione di BitLocker: BitLocker con TPM

BitLocker con TPM necessita di un computer con TPM versione hardware 1.2. Questa opzione è chiara per l'utente perché il processo di avvio non viene alterato in alcun modo e non sono necessari password o hardware aggiuntivi.

La modalità di autenticazione effettuata esclusivamente con TPM costituisce l'esperienza più trasparente per l'utente nelle organizzazioni che necessitano di un livello base di protezione dei dati per soddisfare i criteri di protezione. La modalità con TPM è semplice da distribuire, gestire e utilizzare. Inoltre, la modalità TPM può risultare più appropriata per computer incustoditi, quando altrimenti sarebbe opportuno riavviarli.

Tuttavia, questa opzione fornisce la protezione minima dei dati. Protegge contro gli attacchi che modificano solo i componenti di avvio, ma il livello di protezione può presentare punti deboli per quanto riguarda l'hardware o i componenti di avvio. Le modalità di autenticazione multifattore di BitLocker possono prevenire molti di questi attacchi.

Se alcuni settori dell'organizzazione dispongono di dati considerati estremamente riservati su computer portatili, è opportuno prendere in considerazione la possibilità di distribuire BitLocker con autenticazione multifattore su questi computer. Richiedere agli utenti di immettere un codice PIN o di inserire una chiave di avvio USB diminuisce significativamente la facilità di attaccare i dati sensibili.

L'immagine che segue mostra il procedimento logico del processo di decrittografia in questa opzione.

![](images/Cc162804.d118f78b-f599-4be8-a53e-f1d62b9cad8c(it-it,TechNet.10).jpg "Crittografia unità BitLocker con TPM")

**Figura 2.1. Processo di decrittografia BitLocker con TPM**

Le operazioni nella sequenza mostrata sono le seguenti:

1.  Il BIOS avvia e inizializza il TPM. I componenti misurati/attendibili interagiscono con il TPM per archiviare le misurazioni dei componenti nei registri di configurazione di piattaforma (PCR) del TPM.

2.  Se i valori di PCR corrispondono ai valori previsti, il TPM utilizza la chiave radice di archiviazione (SRK) per decrittografare la chiave master del volume (VMK).

3.  La FVEK crittografata viene letta dal volume e la VMK decrittografata viene utilizzata per decrittografarla.

4.  I settori del disco vengono decrittografati con la FVEK non appena vi è effettuato l'accesso.

5.  I dati in testo normale vengono forniti alle applicazioni e ai processi.

La protezione della VMK è un modo indiretto di proteggere i dati che si trovano sul volume del disco. L'aggiunta della VMK consente al sistema di ricreare facilmente una chiave quando le chiavi madre nella catena di certificati vengono perse o compromesse, perché decrittografare e ricrittografare l'intero volume del disco sarebbe costoso.

Come descritto nel processo precedente, BitLocker impedisce che il volume venga decrittografato e che il sistema operativo venga caricato se rileva modifiche al codice record di avvio principale (MBR), al settore di avvio NTFS, al blocco di avvio NTFS, al Boot Manager e ad altri componenti importanti.

#### Rischi attenuati: BitLocker con TPM

L'opzione BitLocker con TPM attenua i seguenti rischi per i dati:

-   **Individuazione della chiave tramite attacchi offline**. La VMK viene crittografata utilizzando la SRK, una chiave contenuta nell'hardware del TPM. La VMK viene quindi utilizzata per crittografare la FVEK. Per decrittografare i dati nel volume crittografato, sarebbe necessario effettuare un attacco a forza bruta per determinare il valore della FVEK.

    ![](images/Cc162804.note(it-it,TechNet.10).gif)**Nota:**

    Per impostazione predefinita, BitLocker utilizza l'algoritmo Advanced Encryption Standard AES-128 più la potenza a 128 bit di Elephant diffuser. Per ulteriori informazioni sul ruolo della diffusione per aggiungere protezione a BitLocker, consultare il white paper BitLocker Drive Encryption [AES-CBC + Elephant diffuser](http://www.microsoft.com/downloads/details.aspx?familyid=131dae03-39ae-48be-a8d6-8b0034c92555&displaylang=en). Facoltativamente, è possibile configurare BitLocker in modo che utilizzi AES-256 più la versione a 256 bit di Elephant, AES-128 semplice o AES-256 semplice. Consultare la documentazione di Windows Vista per ulteriori informazioni su come selezionare la resistenza di questo testo crittografato per BitLocker.

-   **Attacchi offline contro il sistema operativo**. Gli attacchi offline contro il sistema operativo sono prevenuti dal fatto che chi effettua l'attacco deve recuperare correttamente la SRK dal TPM e poi utilizzarla per decrittografare la VMK oppure effettuare un attacco a forza bruta sulla FVEK. Inoltre, BitLocker configurato con la relativa tecnologia di diffusione (attivata per impostazione predefinita) attenua attacchi mirati di questa natura, poiché le piccole modifiche apportate al testo crittografato si propagheranno su un'area più grande.

-   **Perdita di dati non crittografati tramite il file ibernazione**. Uno degli obiettivi principali di BitLocker è di proteggere i dati nel volume del sistema operativo del disco rigido quando il computer viene spento o entra in modalità di ibernazione. Quando BitLocker è attivo, il file ibernazione viene crittografato.

-   **Perdita di dati non crittografati tramite il file di paging del sistema**. Quando BitLocker è attivo, il file di paging del sistema viene crittografato.

-   **Errore dell'utente**. Poiché BitLocker è una tecnologia di crittografia completa dei volumi, esegue la crittografia di tutti i file che si trovano nel volume del sistema operativo Windows Vista. Questa funzionalità consente di impedire che l'utente prenda decisioni sbagliate riguardo l'applicazione della crittografia.

#### Rischi residui e attenuazione: BitLocker con TPM

L'opzione BitLocker con TPM non attenua i seguenti rischi senza criteri e controlli aggiuntivi:

-   **Computer in modalità di ibernazione**. Lo stato del portatile e le chiavi di crittografia di BitLocker non vengono modificati quando il portatile entra in ibernazione. Questo rischio può essere attenuato attivando l'impostazione **Chiedi la password al termine della modalità standby**.

-   **Computer in modalità sospensione (standby)**. Come per l'ibernazione, lo stato del portatile e le chiavi di crittografia di BitLocker non vengono modificati quando il portatile entra in modalità sospensione. Alla ripresa dalla modalità sospensione, la FVEK rimane accessibile sul computer. Questo rischio può essere attenuato attivando l'impostazione **Chiedi la password al termine della modalità standby**.

-   **Computer con accesso effettuato e desktop sbloccato**. Una volta avviato il computer e rimosso il sealing alla VMK, chiunque può accedere ai dati decrittografati con l'accesso alla tastiera. L'attenuazione più utile per questo rischio è la formazione nell'ambito della consapevolezza in materia di protezione per gli utenti che potrebbero disporre di informazioni riservate nei propri computer.

-   **Individuazione della password di dominio/locale**. Poiché il TPM è collegato in modo permanente al computer degli utenti, non viene presa in considerazione una seconda credenziale per l'autenticazione o l'accesso ai file crittografati. Se la password dell'utente viene compromessa, anche la soluzione di crittografia risulta compromessa. Questo rischio può essere attenuato facendo in modo che gli utenti creino password valide e non le condividano con nessuno né le scrivano in posti ovvi. Validi criteri di password di rete possono impedire efficacemente che un attacco con dizionario su una password, effettuato da qualcuno che utilizzi strumenti facilmente reperibili, riesca.

-   **Dati crittografati leggibili dall'interno**. BitLocker con TPM non richiede altre credenziali oltre a una password account utente valida per accedere a tutti i dati crittografati nel computer. Quindi, qualsiasi account utente in grado di accedere al computer può accedere ad alcuni o a tutti i file crittografati con BitLocker, come se BitLocker fosse disattivato. L'attenuazione più utile per questo rischio è richiedere un fattore di autenticazione aggiuntivo per utilizzare il computer (possibile con altre opzioni BitLocker) o tenere sotto stretto controllo il criterio di ogni computer che riguarda coloro a cui è consentito accedere. Inoltre, la distribuzione appropriata di EFS può attenuare significativamente questo rischio.

-   **Attacchi online contro il sistema operativo**. Gli attacchi online contro il sistema operativo *non* vengono attenuati da questa opzione. Se chi effettua l'attacco è in grado di rimuovere il sealing al volume ed eseguire un normale avvio, il sistema operativo potrebbe essere esposto a una serie di attacchi, tra cui l'acquisizione di privilegi e l'esecuzione del codice remoto.

-   **Attacchi alla piattaforma**. Un computer configurato con BitLocker in modalità base (solo TPM) avvia e carica il sistema operativo fino alla visualizzazione dell'interfaccia delle credenziali utente Microsoft Windows® (il servizio Winlogon), senza richiedere ulteriori elementi di autenticazione BitLocker. Per caricare il sistema operativo dal volume crittografato, il computer deve accedere con privilegi alle chiavi di decrittografia. Questa operazione viene effettuata in modo sicuro perché avviene in un TCB (Trusted Computing Base) convalidato tramite TPM. Qualsiasi attacco alla piattaforma, come l'accesso diretto alla memoria (DMA) nel bus PCI, potrebbe causare il rilevamento del materiale della chiave.

-   **Fattore di autenticazione richiesto nel computer**. Il TPM fornisce un ulteriore livello di protezione perché non è possibile decrittografare un volume sealed senza utilizzarlo. Questa funzionalità protegge da attacchi che spostano il volume crittografato da un computer a un altro. Tuttavia, poiché il TPM non può essere rimosso dal computer, è sempre presente e non è forte quanto un fattore di autenticazione completamente indipendente. Il TPM non fornisce protezione se chi effettua un attacco rileva autenticatori aggiuntivi, come la password dell'account del computer dell'utente (solo per BitLocker con TPM), il token USB dell'utente o il PIN BitLocker.

[](#mainsection)[Inizio pagina](#mainsection)

### Opzione di BitLocker: BitLocker con USB

BitLocker fornisce supporto per la crittografia completa dei volumi su computer che non dispongono di chip TPM versione 1.2. Sebbene la protezione aggiuntiva fornita dal TPM non sia presente con questa opzione, molte organizzazioni che necessitano di una soluzione di crittografia base, possono trovare soddisfacente l'opzione BitLocker con USB quando combinata con criteri come valide password account utente e l'impostazione **Chiedi la password al termine della modalità standby o di ibernazione**.

Poiché in questa opzione non c'è TPM, non vengono effettuate operazioni di sealing o rimozione del sealing sulla VMK. Invece, la VMK viene crittografata e decrittografata attraverso meccanismi software tradizionali che utilizzano una chiave simmetrica che si trova sulla periferica USB. Dopo aver inserito la periferica USB nel computer, BitLocker recupera la chiave e decifra la VMK. La VMK viene quindi utilizzata per decifrare la FVEK, come mostrato nella figura seguente.

![](images/Cc162804.5cc88486-b6fc-4393-9159-596ad2187ec5(it-it,TechNet.10).jpg "Figura 2.2. Processo di decrittografia BitLocker con USB")

**Figura 2.2. Processo di decrittografia BitLocker con USB**

Le operazioni nella sequenza mostrata sono le seguenti:

1.  Il sistema operativo viene avviato e richiede all'utente di inserire una periferica USB che contenga la chiave USB.

2.  La VMK viene decifrata con la chiave che si trova sulla periferica USB.

3.  La FVEK crittografata viene letta dal volume e la VMK decrittografata viene utilizzata per decrittografarla.

4.  I settori del disco vengono decrittografati con la FVEK non appena vi è effettuato l'accesso.

5.  I dati in testo normale vengono forniti alle applicazioni e ai processi.

#### Rischi attenuati: BitLocker con USB

L'opzione BitLocker con USB attenua i seguenti rischi per i dati:

-   **Computer in modalità di ibernazione**. Dopo l'ibernazione, BitLocker richiederà di nuovo l'autenticazione con la periferica USB.

-   **Individuazione della password di dominio/locale**. BitLocker con una periferica USB richiede un fattore di autenticazione diverso da una password account computer valida per accedere ai dati crittografati nel computer.

-   **Dati crittografati leggibili dall'interno**. Stesse considerazioni evidenziate nella precedente spiegazione sull'attenuazione dei rischi.

-   **Individuazione della chiave tramite attacchi offline**. La VMK viene crittografata tramite una chiave che si trova sulla periferica USB. Se la periferica USB non è disponibile, per chi effettua l'attacco sarà molto difficoltoso determinare il valore della FVEK.

-   **Attacchi offline contro il sistema operativo**. La VMK viene crittografata tramite una chiave che si trova sulla periferica USB. Se la periferica USB non è disponibile, chi effettua l'attacco dovrà gestire correttamente migliaia di settori che contengono moduli del sistema operativo (cioè effettuare un attacco a forza bruta) per determinare il valore della FVEK. Inoltre, BitLocker configurato con la relativa tecnologia di diffusione (attivata per impostazione predefinita) attenua attacchi mirati di questa natura, poiché le piccole modifiche apportate al testo crittografato si propagheranno su un'area più grande.

-   **Perdita di dati non crittografati tramite il file ibernazione**. Uno degli obiettivi principali di BitLocker è di proteggere i dati nel volume del sistema operativo del disco rigido quando il computer viene spento o entra in modalità di ibernazione. Quando BitLocker è attivo, il file ibernazione viene crittografato.

-   **Perdita di dati non crittografati tramite il file di paging del sistema**. Quando BitLocker è attivo, il file di paging del sistema viene crittografato.

-   **Errore dell'utente**. Poiché BitLocker è una tecnologia di crittografia completa dei volumi, crittografa tutti i file che si trovano nel volume del sistema operativo Windows Vista. Questa funzionalità consente di impedire che l'utente prenda decisioni sbagliate riguardo l'applicazione della crittografia.

#### Rischi residui e attenuazione: BitLocker con USB

L'opzione BitLocker con USB non attenua i rischi che seguono senza criteri e controlli aggiuntivi:

-   **Computer in modalità sospensione (standby)**. Lo stato del portatile e le chiavi di crittografia di BitLocker non vengono modificati quando il portatile entra in modalità sospensione. Alla ripresa dalla modalità sospensione, la FVEK rimane accessibile sul computer. Questo rischio può essere attenuato attivando l'impostazione **Chiedi la password al termine della modalità standby**.

-   **Computer con accesso effettuato e desktop sbloccato**. Una volta avviato il computer e rimosso il sealing alla VMK, chiunque può accedere ai dati decrittografati con l'accesso alla tastiera. L'attenuazione più utile per questo rischio è la formazione nell'ambito della consapevolezza in materia di protezione per gli utenti che potrebbero disporre di informazioni riservate nei propri computer.

-   **Attacchi online contro il sistema operativo**. Gli attacchi online contro il sistema operativo *non* vengono attenuati da questa opzione. Se chi effettua l'attacco è in grado di eseguire un normale avvio fornendo la periferica USB al momento dell'avvio, il sistema operativo potrebbe essere esposto a una serie di attacchi, tra cui l'acquisizione di privilegi e l'esecuzione del codice remoto.

-   **Attacchi alla piattaforma**. Un computer configurato con BitLocker e una periferica USB avvia e carica il sistema operativo fino alla visualizzazione dell'interfaccia delle credenziali utente Windows (Winlogon) utilizzando la chiave contenuta nella periferica USB. Qualsiasi attacco alla piattaforma, come DMA nel bus PCI o attraverso le interfacce IEEE 1394, potrebbe causare il rilevamento del materiale della chiave.

-   **Fattore di autenticazione richiesto nel computer**. La periferica USB costituisce un unico fattore di autenticazione fisico e la soluzione di crittografia dipende da esso. È possibile che utenti poco preparati o con poca attenzione tengano la periferica USB nella stessa borsa in cui tengono il PC portatile, mettendo in questo modo la periferica a disposizione dei ladri. Il rischio di perdere il computer e la periferica USB allo stesso tempo può essere attenuato utilizzando un approccio di attenuazione dei rischi che richieda un secondo fattore di autenticazione non fisico come un numero di identificazione personale (PIN) o una password.

[](#mainsection)[Inizio pagina](#mainsection)

### Opzione di BitLocker: BitLocker con TPM e PIN

Un computer con chip TPM versione 1.2 e un BIOS che supporti BitLocker può essere configurato in modo che richieda due fattori per decrittografare i dati crittografati con BitLocker. Il primo fattore è il TPM e il secondo è il codice PIN.

![](images/Cc162804.note(it-it,TechNet.10).gif)**Nota:**

Alle organizzazioni che pensano alla protezione, Microsoft suggerisce di utilizzare BitLocker con TPM e codice PIN come opzione preferita perché non ci sono token esterni che possono essere persi o attaccati.

L'aggiunta di un requisito PIN a un computer che supporta BitLocker migliora significativamente la protezione della tecnologia BitLocker in termini di usabilità e gestibilità. In questa opzione, all'utente vengono richieste due password per utilizzare il computer, una per BitLocker (al momento dell'avvio) e una per il computer o il dominio al momento dell'accesso. Le due password dovrebbero essere e probabilmente saranno diverse perché il codice PIN deve contenere caratteri numerici immessi attraverso i tasti funzione e la maggior parte dei criteri password dominio rifiuterebbe una password composta esclusivamente da caratteri numerici.

Sebbene il codice PIN fornisca una protezione aggiuntiva, può essere attaccato con particolare motivazione e perseveranza. BitLocker elabora il codice PIN prima che sia disponibile un supporto localizzato per tastiere, pertanto è possibile utilizzare solo i tasti funzione (F0 - F9). Questa funzionalità limita l'entropia della chiave e rende possibili gli attacchi a forza bruta, sebbene non particolarmente rapidi. Fortunatamente, il meccanismo TPM PIN è progettato per resistere agli attacchi con dizionario. I dettagli variano a seconda del fornitore; tuttavia, una volta immesso un codice PIN non corretto, ciascuno aggiunge un aumento esponenziale del ritardo prima di consentire l'immissione di un nuovo numero. L'effetto di questo ritardo è quello di ritardare un possibile attacco a forza bruta, che rende l'attacco inefficace. Questo ritardo per l'immissione è noto come protezione *da attacchi di tipo hammering*. Gli utenti possono prevenire gli attacchi a forza bruta contro il PIN scegliendo codici PIN relativamente forti con sette cifre e almeno quattro valori unici. È possibile trovare ulteriori informazioni sulla scelta di codici PIN adeguati in [System Integrity Team Blog](http://blogs.msdn.com/si_team/archive/2006/04/10/572888.aspx) di MSDN.

La versione corrente di BitLocker non fornisce supporto diretto per eseguire il backup del codice PIN. Poiché l'utente deve ricordare due password, è ancora più importante creare una chiave di ripristino di BitLocker che possa essere utilizzata nel caso in cui l'utente dimentichi il codice PIN di BitLocker.

La figura che segue mostra il procedimento logico del processo di decrittografia nell'opzione BitLocker con TPM e PIN.

![](images/Cc162804.11056951-8e9f-4482-9ac4-bc7dac6e48a6(it-it,TechNet.10).jpg "Crittografia unità BitLocker con TPM e codice PIN")

**Figura 2.3. Processo di decrittografia BitLocker con TPM e codice PIN**

Le operazioni nella sequenza mostrata sono le seguenti:

1.  Il BIOS avvia e inizializza il TPM. I componenti misurati/attendibili interagiscono con il TPM per archiviare le misurazioni dei componenti nei registri di configurazione di piattaforma (PCR) del TPM. All'utente viene richiesto di immettere un codice PIN.

2.  La VMK viene decrittografata dal TPM tramite la SRK se i valori di PCR corrispondono ai valori previsti *e* il PIN è corretto.

3.  La FVEK crittografata viene letta dal volume e la VMK decrittografata viene utilizzata per decrittografarla.

4.  I settori del disco vengono decrittografati con la FVEK non appena vi è effettuato l'accesso.

5.  I dati in testo normale vengono forniti alle applicazioni e ai processi.

Un'interessante differenza tra questa opzione e l'opzione base BitLocker con TPM è costituita dal fatto che il PIN è combinato con la chiave TPM per rimuovere il sealing di VMK. Dopo aver eseguito correttamente la rimozione del sealing, BitLocker viene eseguito come nell'opzione base.

#### Rischi attenuati: BitLocker con TPM e PIN

L'opzione BitLocker con TPM e codice PIN attenua i seguenti rischi per i dati:

-   **Computer in modalità di ibernazione**. BitLocker con TPM e codice PIN attenua questo rischio perché all'utente viene richiesto di fornire il codice PIN alla ripresa del computer dalla modalità di ibernazione.

-   **Individuazione della password di dominio/locale**. Uno dei vantaggi principali dell'opzione BitLocker con TPM e codice PIN è costituito dal fatto che la soluzione introduce un altro fattore o credenziale, necessario per avviare il computer o per la ripresa dalla modalità di ibernazione. Questo vantaggio è importante per utenti a rischio di attacchi di social engineering o che sono soliti utilizzare password non adeguate, come le password Windows su computer non attendibili.

-   **Dati crittografati leggibili dall'interno**. Un utente che dispone di un account dominio autorizzato deve accedere al computer ma per fare questo deve riavviarlo. Un utente con un account dominio autorizzato che non dispone del fattore di autenticazione aggiuntivo non potrà avviare il computer per accedere. Gli utenti che non conoscono il codice PIN, compresi gli utenti a cui altrimenti sarebbe consentito accedere al computer, non possono accedere ad alcun dato nel portatile a causa del criterio di dominio.

-   **Individuazione della chiave tramite attacchi offline**. La VMK viene crittografata utilizzando una chiave che si trova nell'hardware del TPM insieme a un codice PIN. Se non si è a conoscenza del codice PIN, per chi effettua l'attacco sarà molto difficoltoso determinare il valore della FVEK.

-   **Attacchi offline contro il sistema operativo**. La VMK viene crittografata utilizzando una chiave che si trova nell'hardware del TPM insieme a un codice PIN. Se non si è a conoscenza del codice PIN, sarà necessario effettuare un attacco offline a forza bruta per determinare il valore della FVEK e utilizzarlo per decrittografare il volume per attaccare i file del sistema operativo.

-   **Perdita di dati non crittografati tramite il file ibernazione**. Uno degli obiettivi principali di BitLocker è di proteggere i dati che si trovano nel volume del sistema operativo del disco rigido quando il computer viene spento o entra in modalità di ibernazione. Quando BitLocker è attivo, il file ibernazione viene crittografato.

-   **Perdita di dati non crittografati tramite il file di paging del sistema**. Quando BitLocker è attivo, il file di paging del sistema viene crittografato.

-   **Fattore di autenticazione richiesto nel computer**. Il codice PIN è un secondo fattore di autenticazione non fisico che non può essere perso insieme al computer a meno che non sia scritto da qualche parte, ad esempio su carta.

-   **Errore dell'utente**. Poiché BitLocker è una tecnologia di crittografia completa dei volumi, esegue la crittografia di tutti i file che si trovano nel volume del sistema operativo Windows Vista. Questa funzionalità consente di impedire errori dell'utente nel prendere decisioni sbagliate riguardo l'applicazione della crittografia.

#### Rischi residui e attenuazione: BitLocker con TPM e PIN

L'opzione BitLocker con TPM e codice PIN non attenua i seguenti rischi senza criteri e controlli aggiuntivi:

-   **Computer in modalità sospensione (standby)**. Lo stato del portatile e le chiavi di crittografia di BitLocker non vengono modificati quando il portatile entra in modalità sospensione. Alla ripresa dalla modalità sospensione, la FVEK rimane accessibile sul computer. Questo rischio può essere attenuato attivando l'impostazione **Chiedi la password al termine della modalità standby**.

-   **Computer con accesso effettuato e desktop sbloccato**. Una volta avviato il computer e rimosso il sealing alla VMK, chiunque può accedere ai dati decrittografati con l'accesso alla tastiera. L'attenuazione più utile per questo rischio è la formazione nell'ambito della consapevolezza in materia di protezione per gli utenti che potrebbero disporre di informazioni riservate nei propri computer.

-   **Attacchi online contro il sistema operativo**. Gli attacchi online contro il sistema operativo *non* vengono attenuati da questa opzione.

-   **Attacchi alla piattaforma**. Un computer configurato con BitLocker, un TPM e un codice PIN utente avvia e carica il sistema operativo fino alla visualizzazione dell'interfaccia delle credenziali utente Windows (Winlogon) dopo aver immesso il codice PIN utente. Fino a quando l'utente non immette il codice PIN, gli attacchi alla piattaforma non sono in grado di recuperare il materiale della chiave. Dopo aver immesso il codice PIN, tali attacchi potrebbero causare il rilevamento del materiale della chiave.

[](#mainsection)[Inizio pagina](#mainsection)

### Opzione di BitLocker: BitLocker con TPM e periferica USB

Nell'opzione precedente, BitLocker era stato configurato affinché utilizzasse un codice PIN come secondo fattore di autenticazione con TPM. È anche possibile utilizzare una periferica USB come alternativa al codice PIN. In questa opzione, all'utente viene richiesto di inserire la periferica USB al momento dell'avvio o alla ripresa dalla modalità di ibernazione.

La figura che segue mostra il procedimento logico del processo di decrittografia nell'opzione BitLocker con TPM e USB.

![](images/Cc162804.da7b15a1-1d74-4a40-86b4-adb3720183c5(it-it,TechNet.10).jpg "Crittografia unità BitLocker con TPM e periferica USB")

**Figura 2.4. Processo di decrittografia BitLocker con TPM e periferica USB**

Le operazioni nella sequenza mostrata sono le seguenti:

1.  Il BIOS avvia e inizializza il TPM. I componenti misurati/attendibili interagiscono con il TPM per archiviare le misurazioni dei componenti nei registri di configurazione di piattaforma (PCR) del TPM.

2.  All'utente viene richiesta la periferica USB che contiene la chiave BitLocker.

3.  Se i valori di PCR corrispondono ai valori previsti, una chiave intermedia viene decrittografata dal TPM tramite la SRK. Questa chiave intermedia viene combinata con la chiave che si trova sulla periferica USB per produrre un'altra chiave intermedia utilizzata per decrittografare la VMK.

4.  La FVEK crittografata viene letta dal volume e la VMK decrittografata viene utilizzata per decrittografarla.

5.  I settori del disco vengono decrittografati con la FVEK non appena vi è effettuato l'accesso.

6.  I dati in testo normale vengono forniti alle applicazioni e ai processi.

Questa opzione è diversa dalle opzioni BitLocker con TPM base o BitLocker con TPM e codice PIN perché il materiale della chiave che si trova sulla periferica USB viene combinato con la chiave TPM per decrittografare la VMK. Dopo aver completato correttamente la rimozione del sealing, BitLocker viene eseguito come nell'opzione base.

#### Rischi attenuati: BitLocker con TPM e periferica USB

L'opzione BitLocker con TPM e periferica USB attenua i seguenti rischi per i dati:

-   **Computer in modalità di ibernazione**. Dopo l'ibernazione, BitLocker richiederà di nuovo l'autenticazione con la periferica USB.

-   **Individuazione della password di dominio/locale**. Come per la precedente opzione, il vantaggio principale dell'opzione BitLocker con TPM e USB è che la soluzione introduce un altro fattore o credenziale, necessario per avviare il computer o per la ripresa dalla modalità di ibernazione.

-   **Dati crittografati leggibili dall'interno**. Poiché questa opzione aggiunge un fattore di autenticazione, riduce il rischio che un utente non autorizzato con un account valido possa avviare il computer, accedere e leggere i dati crittografati.

-   **Individuazione della chiave tramite attacchi offline**. Se non è presente una periferica USB, è necessario un attacco a forza bruta alla chiave che si trova sulla periferica USB per determinare il valore della FVEK.

-   **Attacchi offline contro il sistema operativo**. Se non è presente una periferica USB, è necessario un attacco a forza bruta alla chiave che si trova sulla periferica USB per attaccare efficacemente il sistema operativo.

-   **Perdita di dati non crittografati tramite il file ibernazione**. Uno degli obiettivi principali di BitLocker è di proteggere i dati che si trovano nel volume del sistema operativo del disco rigido quando il computer viene spento o entra in modalità di ibernazione. Quando BitLocker è attivo, il file ibernazione viene crittografato.

-   **Perdita di dati non crittografati tramite il file di paging del sistema**. In Windows Vista, il file di paging viene crittografato utilizzando una chiave simmetrica temporanea generata al momento dell'avvio, ma mai scritta sul disco. All'arresto del sistema, questa chiave viene eliminata affinché sia necessario un attacco a forza bruta per trovare la chiave simmetrica utilizzata per crittografare il file di paging per recuperare i dati dal file di paging.

-   **Errore dell'utente**. Poiché BitLocker è una tecnologia di crittografia completa dei volumi, crittografa tutti i file che si trovano nel volume del sistema operativo Windows Vista. Questa funzionalità consente di impedire che l'utente prenda decisioni sbagliate riguardo l'applicazione della crittografia.

#### Rischi residui e attenuazione: BitLocker con TPM e periferica USB

L'opzione BitLocker con TPM e periferica USB non attenua i seguenti rischi senza criteri e controlli aggiuntivi:

-   **Computer in modalità sospensione (standby)**. Lo stato del portatile e le chiavi di crittografia di BitLocker non vengono modificati quando il portatile entra in modalità sospensione. Alla ripresa dalla modalità sospensione, la FVEK rimane accessibile sul computer. Questo rischio può essere attenuato attivando l'impostazione **Chiedi la password al termine della modalità standby**.

-   **Computer con accesso effettuato e desktop sbloccato**. Una volta avviato il computer e decrittografata la VMK, chiunque può accedere ai dati decrittografati tramite l'accesso alla tastiera. L'attenuazione più utile per questo rischio è la formazione nell'ambito della consapevolezza in materia di protezione per gli utenti che potrebbero disporre di informazioni riservate nei propri computer.

-   **Attacchi online contro il sistema operativo**. Chiunque effettui un attacco e sia in grado di eseguire un normale avvio fornendo la periferica USB come parte del processo di avvio, può effettuare una serie di attacchi, tra cui l'acquisizione di privilegi e attacchi che possono essere sfruttati in remoto.

-   **Attacchi alla piattaforma**. Un computer configurato con BitLocker, TPM e una periferica USB avvia e carica il sistema operativo fino alla visualizzazione dell'interfaccia delle credenziali utente Windows (Winlogon). Gli attacchi alla piattaforma potrebbero causare il rilevamento del materiale della chiave.

-   **Fattore di autenticazione richiesto nel computer**. La periferica USB costituisce un unico fattore di autenticazione fisico e la soluzione di crittografia dipende da esso. Il rischio corso dagli utenti che perdono il computer insieme alla periferica USB può essere attenuato richiedendo un secondo fattore di autenticazione non fisico come un codice PIN o una password.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo analisi dei rischi di BitLocker

Nella tabella riportata di seguito vengono elencati i rischi per i dati e viene indicato se le differenti opzioni di BitLocker sono in grado di attenuare ogni rischio. I rischi che possono essere attenuati con opzioni specifiche sono indicati con la lettera **Y**. I trattini **-** indicano i rischi per cui l'opzione specifica fornisce un'attenuazione ridotta o inesistente.

**Tabella 2.1. Attenuazione dei rischi di BitLocker**

![](images/Cc162804.fd057821-a2d0-48df-a0b1-5b07eaa7c90a(it-it,TechNet.10).gif "Attenuazione dei rischi di BitLocker")
[](#mainsection)[Inizio pagina](#mainsection)

### Ulteriori informazioni

-   [System Integrity Team Blog (in inglese)](http://blogs.msdn.com/si_team/archive/2006/04/10/572888.aspx)

-   BitLocker Drive Encryption [AES-CBC + Elephant diffuser](http://www.microsoft.com/downloads/details.aspx?familyid=131dae03-39ae-48be-a8d6-8b0034c92555&displaylang=en) white paper (in inglese)

**Download**

[Get the Data Encryption Toolkit for Mobile PCs (in inglese)](http://go.microsoft.com/fwlink/?linkid=81666)

**Partecipa**

[Iscriviti per partecipare al programma Data Encryption Toolkit Beta](https://connect.microsoft.com/invitationuse.aspx?programid=790&invitationid=desa-r7gd-3f73&siteid=14)

**Notifiche di aggiornamento**

[Iscriviti per ricevere informazioni su aggiornamenti e nuovi rilasci](http://go.microsoft.com/fwlink/?linkid=54982)

**Commenti**

[Inviaci i tuoi commenti o suggerimenti](mailto:secwish@microsoft.com?oggetto=analisi%20della%20protezione%20di%20data%20encryption%20toolkit%20for%20mobile%20pc%20su%20technet)

[](#mainsection)[Inizio pagina](#mainsection)
