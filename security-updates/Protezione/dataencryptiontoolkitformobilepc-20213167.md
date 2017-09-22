---
TOCTitle: Data Encryption Toolkit for Mobile PC
Title: Data Encryption Toolkit for Mobile PC
ms:assetid: '54de4f8c-d962-4744-b2da-99f7ad7953df'
ms:contentKeyID: 20213167
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc162806(v=TechNet.10)'
---

Data Encryption Toolkit for Mobile PC: guida alla pianificazione e all'implementazione
======================================================================================

### Capitolo 1: Aspetti relativi alla pianificazione

Il processo di distribuzione degli strumenti di crittografia dati per la protezione dei dati nell'organizzazione richiede la conoscenza approfondita delle tecnologie incluse nei sistemi operativi Microsoft e dei problemi di protezione del proprio ambiente specifico. Inoltre, è necessario essere in grado di identificare e risolvere potenziali problemi di distribuzione che implicano la scelta dell'hardware del client e la relativa configurazione, i criteri di protezione della propria organizzazione, nonché le problematiche complesse relative al controllo e alla conformità alle normative.

Questo capitolo della *Guida alla pianificazione e all'implementazione* è incentrato sulle considerazioni relative alla pianificazione coinvolte nella distribuzione di Windows Vista con Microsoft BitLocker Drive Encryption (BitLocker) e il componente Encrypting File System (EFS) di Windows Vista e Microsoft Windows XP.

Le considerazioni sulla pianificazione di BitLocker ed EFS trattate nel presente capitolo includono requisiti hardware e software che determinano quali computer e dati necessitano di protezione, nonché la scelta di configurazioni appropriate. Altre considerazioni includono problemi di distribuzione del servizio directory di Active Directory e di Criteri di gruppo, la gestibilità, l'utilizzabilità e la pianificazione del reale recupero dei dati.

Per EFS, ulteriori considerazioni implicano l'integrazione di EFS con un'infrastruttura a chiave pubblica (PKI, Public Key Infrastructure) esistente, la distribuzione di Microsoft Encrypting File System Assistant (EFS Assistant) nonché la pianificazione dell'effettivo recupero della chiave.

##### In questa pagina

[](#edaa)[Pianificazione di Crittografia unità BitLocker](#edaa)
[](#ecaa)[Pianificazione della crittografia del file system](#ecaa)
[](#ebaa)[Ulteriori informazioni](#ebaa)

### Pianificazione di Crittografia unità BitLocker

Per completare un piano di distribuzione BitLocker è necessario effettuare quanto segue:

1.  Conoscere le opzioni per la distribuzione di BitLocker

2.  Valutare la disponibilità di BitLocker

3.  Stabilire l'ambito di distribuzione di BitLocker

4.  Scegliere la configurazione di BitLocker

5.  Pianificare il recupero dei dati

6.  Pianificare la gestibilità

7.  Pianificare l'utilizzabilità

8.  Pianificare l'implementazione di Active Directory e Criteri di gruppo

Nelle sottosezioni che seguono vengono analizzate in dettaglio le problematiche relative alla pianificazione di BitLocker.

#### Opzioni per la distribuzione di BitLocker

BitLocker è un'efficace strumento che consente di attenuare la maggior parte delle minacce alla protezione. Per capire quali sono le minacce che BitLocker riesce ad attenuare e quali invece le minacce che è possibile attenuare combinando BitLocker con EFS, è necessario conoscere il modello di protezione di BitLocker e le opzioni di distribuzione da esso supportate. Il documento *Analisi della protezione* fornito con questo Toolkit descrive una vasta gamma di minacce e le modalità con cui BitLocker le attenua. Prima di passare alla fase di pianificazione è necessario acquisire familiarità con i contenuti di tale documento.

#### Valutazione della disponibilità di BitLocker

Per utilizzare BitLocker, è necessario che il computer disponga dei seguenti componenti:

-   Versione Enterprise o Ultimate di Windows Vista.

-   Se si intende utilizzare BitLocker con un TPM, una scheda madre compatibile con TPM (chip BIOS e TPM con TPM v.1.2 o successive definito dal Trusted Computing Group).

-   Disco rigido con due partizioni formattate NTFS. La partizione in cui verranno memorizzate le informazioni sul componente di avvio di BitLocker deve essere una partizione vuota con almeno 1,5 GB di spazio disponibile. Questa partizione deve essere quella attiva.

I requisiti possono essere confermati manualmente utilizzando uno script Windows Management Instrumentation (WMI) o PowerShell per interrogare ciascun computer client e raccogliere informazioni sulle relative funzionalità. La maggior parte delle organizzazioni preferisce utilizzare uno strumento di gestione come Microsoft Systems Management Server (SMS) o un equivalente di terzi, poiché questi strumenti forniscono servizi di inventario e reporting.

##### Requisiti hardware di BitLocker

BitLocker può essere eseguito su qualsiasi computer conforme ai requisiti di sistema di Windows Vista. Per ulteriori informazioni su specifici requisiti di CPU, memoria e disco, vedere [Windows Vista Enterprise Hardware Planning Guidance](http://go.microsoft.com/fwlink/?linkid=79962) (in inglese). Sebbene Microsoft abbia stabilito categorie separate di "Windows Vista Capable" e "Windows Vista Premium Ready" per l'hardware che supporta diverse funzionalità di Windows Vista, BitLocker funzionerà su qualsiasi computer che supporta Windows Vista.

Per sfruttare il supporto di BitLocker per l'hardware TPM, è necessario che i computer includano un hardware TPM 1.2 o versioni successive. Molti produttori forniscono il TPM insieme ai loro prodotti standard, mentre altri lo forniscono in sottoinsiemi limitati delle loro linee di computer portatili o non lo forniscono affatto. Non è possibile aggiungere in alcun modo il supporto TPM ai computer che ne sono privi. Per ovviare a questo problema, è possibile utilizzare una chiave USB per memorizzare le chiavi di crittografia BitLocker.

I computer che invece includono l'hardware TPM devono disporre anche di una versione BIOS che consenta a Windows Vista di utilizzare la serie completa delle funzionalità del TPM. Alcuni computer che contengono l'hardware TPM 1.2 potrebbero richiedere ancora aggiornamenti del BIOS se sono stati spediti prima del gennaio 2007. Se si desidera utilizzare BitLocker con una chiave USB, il BIOS deve essere in grado di leggere tale chiave durante il processo di avvio.

![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**

Alcune implementazioni BIOS supportano USB per avviare il computer, ma disattivano tale funzionalità se il computer viene avviato dal disco rigido o da un altro dispositivo. Queste implementazioni non sono compatibili con BitLocker in quanto quest'ultimo legge la chiave USB più avanti nel processo di avvio.

Ogni computer protetto da BitLocker deve disporre di due partizioni del disco: una per il sistema operativo e i dati, e un'altra più piccola utilizzata solo all'avvio del computer o durante gli aggiornamenti del sistema operativo. (Non è necessario utilizzare questa partizione di avvio per l'archiviazione di altri dati). Microsoft consiglia che la partizione di avvio disponga di almeno 1,5 GB di spazio disponibile su disco. Entrambe le partizioni devono essere formattate con il file system NTFS (NTFS).

Gli utenti di Windows Vista Ultimate possono utilizzare lo strumento Preparazione unità BitLocker di Windows per creare in modo dinamico la partizione dell'utilità e consentire l'uso di BitLocker. Gli utenti della versione Enterprise possono ottenere lo strumento Drive Preparation Tool come descritto nell'articolo 930063 della Microsoft Knowledge Base, "[Descrizione dello strumento Preparazione unità BitLocker](http://support.microsoft.com/kb/930063)." Per richiedere lo strumento è necessario chiamare il Servizio Clienti Microsoft. Sia la chiamata sia lo strumento sono gratuiti. Microsoft non supporta la creazione o lo spostamento manuale delle partizioni per creare la configurazione della partizione di BitLocker. A tal fine è necessario eseguire un'installazione di Windows Vista (che crea partizioni come parte del processo di avvio) o utilizzare Drive Preparation Tool.

Se durante la distribuzione di BitLocker si intende utilizzare unità flash USB, i modelli utilizzati devono implementare la specifica [USB Mass Storage Class Bulk-Only Transport](http://www.usb.org/developers/devclass_docs/usbmassbulk_10.pdf) sul sito Web Universal Serial Bus.

###### Conoscere il TPM

La maggior parte delle organizzazioni che distribuiscono BitLocker vorrà usufruire dei vantaggi sulla protezione offerti dai computer che includono l'hardware TPM. La conoscenza di questo hardware e delle funzionalità da esso fornite è fondamentale per la scelta della configurazione di BitLocker appropriata per la propria organizzazione. (Un esame approfondito del TPM non rientra nell'ambito della presente guida. Per ulteriori informazioni sul TPM e sul Trusted Computing Group, vedere la pagina [Trusted Platform Module (TPM) Specifications](https://www.trustedcomputinggroup.org/specs/tpm) sul sito Web Trusted Computing Group).

È importante conoscere la natura del TPM, si tratta fondamentalmente di un microprocessore specifico con un sistema I/O e una memoria propri. Il TPM dispone di una chiave di verifica dell'autenticità (EK) utilizzata per firmare e crittografare i dati che arrivano direttamente dal TPM o che vengono inoltrati al TPM per la firma o la crittografia. La chiave EK deve essere caricata nel TPM dal produttore del computer o automaticamente come parte del processo di inizializzazione di BitLocker.

È anche importante sapere che in un determinato periodo di tempo il TPM può trovarsi in uno dei diversi stati indicati di seguito:

-   **Abilitato o disabilitato**. Durante la fase di avvio il TPM può essere abilitato e disabilitato più volte. Quando viene abilitato sono disponibili tutte le relative funzioni. Quando viene disabilitato le operazioni sono limitate fatta eccezione per la possibilità di segnalare le funzionalità del TPM e accettare gli aggiornamenti.

-   **Attivato o disattivato**. Quando il TPM è attivato sono disponibili tutte le relative funzioni. Lo stato disattivato è simile allo stato disabilitato, si differenzia per la possibilità di apportare modifiche allo stato operativo (ad esempio, modificare il proprietario o l'attivazione con la presenza fisica).

-   **Con proprietario o senza proprietario**. Quando il sistema operativo assume la proprietà del TPM, questo genera una chiave radice di archiviazione (SRK), ossia una coppia di chiavi utilizzata per eseguire il sealing delle operazioni sui volumi protetti. Il proprietario di un TPM può eseguire tutte le operazioni, incluse le modifiche allo stato operativo. BitLocker non può utilizzare il TPM a meno che non si trovi nello stato con proprietario.

Questi stati possono essere combinati. Ad esempio, alcuni fornitori spediscono computer abilitati al TPM il cui stato predefinito è impostato su disabilitato, disattivato e senza proprietario. Per utilizzare BitLocker su computer di questo tipo, è necessario stabilire la proprietà del TPM, attivarla e abilitarla. Queste operazioni vengono eseguite automaticamente quando si utilizza l'interfaccia utente standard di BitLocker. Dopo la sua attivazione, BitLocker abiliterà, attiverà e assumerà automaticamente la proprietà del TPM, se presente.

È anche necessario conoscere i requisiti per la presenza fisica di alcune operazioni del TPM. Per l'esecuzione di alcuni comandi, le specifiche TPM definite dal Trusted Computing Group richiedono l'interazione diretta tra una persona e il computer fisico e questa persona non può essere né sostituita né imitata tramite uno script. La presenza fisica indica che un utente assume la proprietà ed è fisicamente presente vicino al computer per eseguire le attività amministrative basilari del TPM, come:

-   Abilitare il TPM senza informazioni sul proprietario.

-   Attivare il TPM.

-   Eliminare un proprietario esistente dal TPM.

-   Disattivare o disabilitare temporaneamente il TPM.

##### Requisiti software di BitLocker

Windows Vista è disponibile in diverse versioni, ma solo le versioni Enterprise e Ultimate supportano BitLocker. Microsoft include la funzionalità Windows Anytime Upgrade (descritta nella guida online di Windows Vista), che può essere utilizzata per aggiornare computer singoli. Ad esempio, con la funzionalità Anytime Upgrade è possibile passare dalla versione Business alla versione Ultimate. Alcuni tipi di aggiornamenti potrebbero richiedere la reinstallazione. Ad esempio, gli aggiornamenti da 32 a 64 bit richiedono la reinstallazione della versione a 64 bit di Windows Vista.

![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**

Le indicazioni e gli strumenti presenti in Data Encryption Toolkit for Mobile PC si applicano a EFS (disponibile in Windows XP Professional SP 2 e in tutte le versioni di Windows Vista) e a BitLocker (disponibile in Windows Vista Enterprise e Windows Vista Ultimate). Tuttavia, Windows Vista Ultimate non è stato sottoposto a test rigorosi per verificare se supporta tutte le funzionalità delle indicazioni e degli strumenti. Il Toolkit è inteso principalmente per l'uso con Windows XP Professional SP 2 e le versioni Enterprise e Business di Windows Vista.

###### Distribuzione di Windows Vista

[Solution Accelerator for Business Desktop Deployment](http://go.microsoft.com/fwlink/?linkid=91187) fornisce istruzioni e strumenti completi per la distribuzione di Windows Vista ai computer client della propria organizzazione. In fase di pianificazione della strategia di distribuzione di Windows Vista, tenere presente che l'abilitazione di BitLocker richiederà, molto probabilmente, il contatto fisico con ogni computer, in quanto il TPM non può essere né inizializzato né riprogrammato fatta eccezione per la console del computer interessato. Inoltre, per sfruttare al massimo le funzionalità di BitLocker potrebbe essere necessario aggiornare il BIOS dei computer.

Un aspetto fondamentale consiste nel decidere se aggiornare i computer esistenti da Windows XP a Windows Vista o se eseguire un'installazione corretta del nuovo sistema operativo. Se non si installa Windows Vista, non è possibile abilitare BitLocker. Tuttavia, tenere presente che BitLocker richiede una configurazione particolare della partizione del disco, come descritto nella [Guida dettagliata a Crittografia unità BitLocker di Windows](http://go.microsoft.com/fwlink/?linkid=83223). Se è necessario effettuare l'aggiornamento dei computer esistenti su cui è in esecuzione Windows XP, il piano di distribuzione deve garantire la creazione della struttura della partizione necessaria prima di poter attivare BitLocker su tali computer.

Il toolkit Business Desktop Deployment (BDD) di Windows Vista supporta l'attivazione automatica di BitLocker in determinate circostanze. Per i dettagli su come utilizzare gli strumenti BDD per attivare BitLocker come parte del processo di distribuzione del sistema operativo, vedere la [Lite Touch Installation Guide](http://go.microsoft.com/fwlink/?linkid=78607).

#### Ambito di distribuzione di BitLocker

Dopo aver valutato quali reparti della propria organizzazione dispongono di hardware e software che supportano di una o più modalità di BitLocker, il passo successivo consiste nel determinare esattamente dove distribuire BitLocker. Per tale operazione è necessario rispondere alle seguenti domande e stabilire l'ambito finale per la distribuzione di BitLocker:

-   Quali sono i computer all'interno dell'organizzazione che necessitano di protezione? È possibile scegliere di proteggere alcuni o tutti i computer portatili e desktop, a seconda delle necessità di protezione e del ciclo di implementazione della distribuzione.

-   Quali sono i dati presenti nell'organizzazione che necessitano di protezione? Alcune organizzazioni potrebbero voler proteggere tutti i dati disponibili, mentre altre potrebbero avere esigenze più specifiche.

##### Quali computer necessitano di protezione?

Le decisioni relative alla protezione implicano generalmente un compromesso tra protezione e costi e l'implementazione di BitLocker non fa eccezione. Distribuire Windows Vista su tutti i computer client presenti in un'azienda e abilitare BitLocker su di essi potrebbe apparire la migliore strategia di protezione. Tuttavia, la maggior parte delle organizzazioni dovrà sincronizzare l'implementazione diffusa di Windows Vista (e, pertanto, di BitLocker) con il piano di distribuzione IT complessivo. E ancora, ogni organizzazione può trarre vantaggio dall'implementazione mirata di Windows Vista e BitLocker sui computer che sono maggiormente a rischio. Questi computer includono:

-   Computer utilizzati da dirigenti, avvocati o altri collaboratori che utilizzano quotidianamente dati finanziari, legali o strategici.

-   Computer utilizzati da sviluppatori software, tester, progettisti di siti Web o altri utenti che potrebbero avere accesso a dati personali o finanziari su clienti, collaboratori o partner commerciali.

-   Computer utilizzati dal settore delle risorse umane, dal settore assicurativo, dal settore medico o da altri che gestiscono quotidianamente informazioni personali riservate su clienti e collaboratori.

-   Computer utilizzati in aree in cui risultano vulnerabili ad attacchi fisici (compreso il furto dei dischi rigidi o dell'intero computer).

-   Computer laptop o portatili utilizzati dai collaboratori per accedere o utilizzare le informazioni aziendali anche quando lavorano fuori ufficio.

-   Computer domestici o personali dei dipendenti chiave, se tali computer vengono utilizzati per lavorare sulle informazioni aziendali o accedere alla rete dell'organizzazione.

Per determinare quali sono i computer all'interno della propria azienda che necessitano di protezione, utilizzare un inventario automatizzato (se possibile) per identificare i computer che corrispondono a uno di quelli su indicati. È possibile integrare un inventario automatizzato con un controllo incrociato manuale che metta in corrispondenza i collaboratori che lavorano su dati riservati e i computer di proprietà dell'azienda utilizzati quotidianamente. Se l'organizzazione utilizza un pool di computer portatili assegnati a postazioni specifiche o disponibili per la verifica da parte dei collaboratori, prendere in considerazione la loro inclusione come categoria separata di computer che richiedono protezione.

##### Quali sono i dati che necessitano di protezione?

Uno dei maggiori vantaggi di BitLocker è che protegge tutti i contenuti del volume del sistema. Questa funzionalità consente di eliminare gran parte dell'incertezza sui dati che devono o non devono essere crittografati. Ogni file creato o utilizzato dall'utente verrà crittografato se viene memorizzato nel volume del sistema operativo.

Tuttavia, è importante identificare categorie o classi specifiche di dati che potrebbero richiedere la protezione di BitLocker in modo da poter identificare meglio gli utenti e i computer a cui è consentito elaborare tali tipi di dati. I tipi di dati candidati per la protezione includono:

-   Informazioni commerciali riservate, compresi dati finanziari, piani del prodotto, informazioni su conto bancario o carta di credito, nonché piani e comunicazioni strategiche.

-   Informazioni e dati relativi a controversie in sospeso, passate o future, in particolare se soggette a privilegi legali o client.

-   Dati personali di collaboratori, ex dipendenti, pensionati o clienti.

-   Codice sorgente, database, informazioni sul progetto proprietario, segreti commerciali e altre proprietà intellettuali.

-   Materiale con licenza o di proprietà di partner commerciali o altri concessori di licenze che potrebbero richiedere la riservatezza di tali informazioni.

#### Scelta della configurazione di BitLocker

In questa fase di pianificazione si stabilisce quali configurazioni sono appropriate per la propria organizzazione e viene delineato il processo di configurazione e di distribuzione.

La guida *Analisi della protezione* presente in questo Solution Accelerator contiene una descrizione completa dei metodi di protezione da utilizzare con BitLocker per proteggere le chiavi di crittografia del volume. Utilizzare le informazioni della guida *Analisi della protezione* per scegliere le modalità di BitLocker che risultano appropriate per la propria organizzazione. La scelta delle modalità di BitLocker può dipendere dalla disponibilità di hardware e software, come indicato in precedenza, o dai requisiti di protezione differenti in varie parti dell'organizzazione. Le modalità disponibili sono:

-   BitLocker con TPM

-   BitLocker con TPM e PIN

-   BitLocker con dispositivo USB

-   BitLocker con TPM e dispositivo USB

Nella seguente figura viene illustrata una struttura decisionale da utilizzare per valutare le opzioni di configurazione di BitLocker per il proprio ambiente.

![](images/Cc162806.ca97aaca-c63e-43bb-948c-67d3ae965c2e(it-it,TechNet.10).gif)

**Figura 1.1. Struttura decisionale delle opzioni di configurazione di BitLocker**

L'output del processo decisionale potrebbe essere simile a quanto illustrato nella seguente tabella. Le informazioni devono includere ruoli hardware, tipi di hardware supportati, nonché la configurazione e i criteri associati di BitLocker.

**Tabella 1.1. Linee guida su criteri e configurazione di BitLocker**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tipo di sistema</p></th>
<th><p>Criteri e configurazione di BitLocker</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Desktop standard</p></td>
<td style="border:1px solid black;"><p>I computer utilizzeranno la crittografia di BitLocker con una chiave di avvio TPM o USB, a seconda della capacità dell'hardware. Questa configurazione verrà utilizzata per controllare l'esposizione dei dati e gestire il ritiro delle risorse.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Laptop standard</p></td>
<td style="border:1px solid black;"><p>Tutti i nuovi computer utilizzeranno un TPM e un PIN. I computer privi di TPM utilizzeranno chiavi di avvio sulle unità USB, ma tutti i nuovi computer verranno acquistati con dispositivi TPM integrati. Questa configurazione verrà utilizzata per controllare l'esposizione dei dati e gestire il ritiro delle risorse.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Laptop dei dirigenti</p></td>
<td style="border:1px solid black;"><p>Tutti i computer utilizzeranno un TPM con un PIN. I computer esistenti non provvisti di supporto TPM verranno sostituiti.</p></td>
</tr>  
</tbody>  
</table>
  
##### Considerazioni su BitLocker con TPM
  
La modalità BitLocker con TPM fornisce protezione senza la necessità di alcun intervento da parte dell'utente; inoltre la crittografia del volume, l'avvio e il funzionamento sono tutte operazioni trasparenti per l'utente. Questa modalità di BitLocker *non* è, in genere, appropriata per un'implementazione base di BitLocker, ma deve essere considerata solo nelle seguenti situazioni:
  
-   Quando non è necessaria l'autenticazione multifattoriale di BitLocker.
  
-   Quando il valore dei dati non giustifica la spesa aggiuntiva e/o la complessità della configurazione multifattoriale di BitLocker.
  
##### Pianificazione di BitLocker con TPM
  
Le operazioni di pianificazione per la modalità BitLocker con TPM includono quanto segue:
  
-   Un inventario dei computer all'interno dell'organizzazione che dispongono del TPM.
  
-   Ciclo di aggiornamento e sostituzione dell'hardware.
  
-   Modalità di funzionamento dei processi di aggiornamento dei software esistenti e di gestione delle patch.
  
-   Motivi aziendali o operativi che consentono o meno l'avvio automatico dei computer. BitLocker con TPM consente l'avvio automatico, ma le modalità di BitLocker che utilizzano un PIN o una chiave USB richiedono che il PIN o la chiave USB venga fornito durante l'avvio.
  
-   Modalità di funzionamento dei processi esistenti del supporto tecnico (che includono la riparazione, la sostituzione e la rimozione delle autorizzazioni dell'hardware) con i sistemi protetti da TPM, considerato che il disco protetto da BitLocker potrebbe non essere utilizzato direttamente in un computer di sostituzione.
  
##### Considerazioni su BitLocker con TPM e PIN
  
BitLocker con un TPM e un PIN consente di impedire agli utenti di dominio che non conoscono il PIN di leggere i dati del computer protetto. Protegge da attacchi al computer che potrebbero riuscire se questo è stato avviato dalla schermata di accesso.
  
La fase di pianificazione deve stabilire se gli utenti oppongono resistenza a imparare e a ricordare un PIN aggiuntivo e se eseguono delle operazioni che consentono di superare tale resistenza. La necessità di un ulteriore fattore di autenticazione come protezione aggiuntiva rende ideale questa soluzione per proteggere le risorse preziose.
  
##### Pianificazione di BitLocker con TPM e PIN
  
Per pianificare la modalità BitLocker con TPM e PIN è necessario seguire tutte le procedure di pianificazione per la modalità BitLocker con TPM. È inoltre necessario creare un piano per:
  
1.  Creare una documentazione per la formazione dell'utente che consentirà a quest'ultimo di creare un PIN adeguato in grado di soddisfare i requisiti di protezione dell'organizzazione, nonché le operazioni da effettuare in caso venisse dimenticato il PIN.
  
2.  Creare la documentazione per la formazione del personale del supporto tecnico sulle procedure di ripristino del PIN.
  
##### Considerazioni su BitLocker con USB
  
BitLocker con un dispositivo USB fornisce protezione ai computer che non contengono un TPM. Questa modalità fornisce una funzionalità di base ma non consente il controllo dell'integrità all'avvio e non impedisce agli utenti di dominio di effettuare l'accesso al computer e di leggere i dati dopo l'avvio del sistema tramite il dispositivo USB.
  
##### Pianificazione di BitLocker con USB
  
Se si intende utilizzare BitLocker con una chiave di avvio USB, sarà necessario eseguire le operazioni di pianificazione riportate di seguito:
  
1.  Testare i computer per verificare che siano in grado di riconoscere il modello preferito di chiavi USB all'avvio. I test di Microsoft indicano che alcuni marchi di chiavi USB presentano percentuali di errore superiori al 50%, pertanto il test dovrebbe includere la verifica dell'affidabilità. Occorre prendere in considerazione l'uso di un solo tipo di chiave per garantire l'accesso affidabile alle password di avvio e di ripristino.
  
2.  Pianificare la modalità con cui gli utenti che utilizzano solo BitLocker con una chiave USB passeranno alla modalità BitLocker con TPM e PIN. Il piano deve includere la modalità di migrazione dei dati e delle applicazioni su computer con supporto TPM o, se i computer esistenti supportano il TPM, l'attivazione del TPM e la riattivazione di BitLocker.
  
##### Considerazioni su BitLocker con TPM e USB
  
In questa modalità, BitLocker consente il controllo e la crittografia all'avvio ed è necessario che il token USB sia presente per consentire l'avvio del computer. Le considerazioni sulla pianificazione per questa modalità sono un ibrido di quelle richieste per le modalità solo TPM e solo USB, in quanto è necessario verificare che i computer possano utilizzare BitLocker con un TPM e supportare l'archiviazione della chiave USB.
  
##### Pianificazione di BitLocker con TPM e USB
  
Se si intende utilizzare questa modalità, è necessario eseguire le stesse procedure di pianificazione descritte nella sezione "Pianificazione di BitLocker con TPM" riportata in precedenza in questo capitolo, nonché le procedure descritte nella sezione "Pianificazione di BitLocker con USB".
  
#### Pianificazione del recupero dati
  
BitLocker consente una crittografia completa dei dati. Se non si dispone della password di ripristino corretta, non esistono "backdoor" o altri metodi per ripristinare i dati da un disco protetto da BitLocker. La pianificazione del ripristino diventa così di fondamentale importanza in quanto senza una copia corretta della password di ripristino non sarà possibile ripristinare *i* dati da un volume protetto.
  
Durante l'avvio del computer, BitLocker è in grado di rilevare una condizione che gli impedisce di sbloccare l'unità su cui è installato Windows. Esempi di queste condizioni includono errori del disco o modifiche apportate ai file di avvio del computer. Se si verifica una qualsiasi di queste condizioni, non sarà possibile accedere ai file non protetti fino a quando non si sblocca il volume tramite la password di ripristino di BitLocker. Se si tenta di caricare il disco rigido in un computer differente, sarà ancora necessaria la password di ripristino di BitLocker.
  
Sono disponibili quattro strategie principali per l'archiviazione delle password di ripristino:
  
-   Stampare la password.
  
-   Archiviare la password su supporti rimovibili.
  
-   Archiviare la password in un percorso di archiviazione di rete.
  
-   Archiviare la password in Active Directory.
  
Microsoft consiglia di scegliere una combinazione di metodi di ripristino. Poiché i volumi BitLocker non possono essere ripristinati senza la password, l'archiviazione delle password di ripristino mediante un singolo metodo di ripristino introduce un singolo punto di errore nel processo di ripristino dati. Ogni metodo di ripristino presenta dei vantaggi e degli svantaggi; pertanto, quando si sceglie un metodo, occorre accertarsi di essere a conoscenza di queste problematiche.
  
##### 
  
###### Active Directory
  
Microsoft consiglia vivamente di pianificare e distribuire l'archivio Active Directory delle password di ripristino per i computer protetti da BitLocker. Grazie a questo metodo, le informazioni sul ripristino vengono memorizzate come attributi sull'oggetto computer in Active Directory. Le informazioni sul ripristino includono la password di ripristino per ciascun volume abilitato da BitLocker, la password del proprietario del TPM e le informazioni necessarie per identificare a quali computer e volumi si applicano tali informazioni. Facoltativamente, è possibile salvare un pacchetto che contiene le chiavi utilizzate per crittografare i dati e la password di ripristino necessari per accedere a tali chiavi. Questo metodo di archiviazione della password di ripristino, confrontato con altri metodi di archiviazione, presenta i seguenti vantaggi:
  
-   Il processo di archiviazione è automatizzato e non implica pertanto il coinvolgimento dell'utente.
  
-   L'utente non può in alcun modo perdere o danneggiare le informazioni sul ripristino.
  
-   Active Directory fornisce il controllo centralizzato dell'archiviazione e dell'utilizzo delle informazioni sul ripristino.
  
-   Le informazioni vengono sottoposte a backup e protette insieme ad altri dati valutabili di Active Directory.
  
-   Tali informazioni sono accessibili in remoto e rendono possibile il ripristino in un altro luogo e con assistenza da parte del supporto tecnico.
  
L'utilizzo di Active Directory per la memorizzazione delle password di ripristino di BitLocker prevede i seguenti requisiti:
  
-   L'organizzazione deve disporre di un'infrastruttura Active Directory affidabile e ben gestita.
  
-   Lo schema Active Directory di Windows Server 2003 deve essere esteso in modo da includere attributi e oggetti di BitLocker. La pianificazione dell'estensione dello schema Active Directory è un aspetto importante. Per ulteriori informazioni sull'estensione dello schema Active Directory, vedere [Extending Your Active Directory Schema in Windows Server 2003 R2](http://technet.microsoft.com/en-us/library/cc772804.aspx) (in inglese).
  
-   L'amministratore deve essere in grado di abilitare le impostazioni di Criteri di gruppo per consentire il backup della password di ripristino di BitLocker.
  
-   I criteri e il personale devono essere sufficientemente protetti per garantire l'archiviazione sicura e l'accesso controllato al materiale di ripristino memorizzato in Active Directory.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
I computer che entrano in modalità di ripristino potrebbero essere soggetti ad attacchi improvvisi da parte di malware. Prima che l'utente esegua un ripristino è opportuno verificare che tutti i computer che entrano in tale modalità senza una causa nota vengano esaminati dal personale di supporto.
  
###### Metodo che prevede l'uso di file o stampante
  
La stampa della password di ripristino o la relativa archiviazione in un file è un semplice processo che presenta alcuni vantaggi importanti:
  
-   Facile da impostare.
  
-   È richiesta una piccola infrastruttura.
  
-   Facile da gestire per gli utenti non tecnici.
  
Tuttavia, presenta anche degli svantaggi:
  
-   È l'utente che deve gestire la password di ripristino e proteggerla da eventuali perdite o danneggiamenti.
  
-   Questo tipo di archiviazione delle password non fornisce alcun controllo centralizzato.
  
-   Non esiste una protezione talmente efficace da evitare la perdita o il danneggiamento di file salvati o di documenti stampati.
  
###### Metodo che prevede l'uso del dispositivo USB
  
L'archiviazione della password di ripristino su un dispositivo USB presenta i seguenti vantaggi:
  
-   È possibile memorizzare più password di ripristino su un singolo dispositivo USB in quanto tali password sono file di testo semplici.
  
-   È più semplice aggiungere protezione fisica e barriere per proteggere le password.
  
-   La separazione della chiave USB dal computer consente di tenere divise le mansioni.
  
Tuttavia, questo metodo presenta anche degli svantaggi:
  
-   Non tutti i computer supportano il caricamento dei dispositivi USB durante i processi prima dell'avvio e durante l'avvio.
  
-   La raccolta e l'archiviazione delle password di ripristino è un processo manuale che deve essere eseguito su ogni singolo computer.
  
-   Per questo metodo non è previsto alcun controllo centralizzato.
  
-   Il dispositivo USB può essere perso, danneggiato o può presentare errori.
  
###### Definizione dei criteri di recupero
  
È importante definire un criterio che indichi in maniera specifica la persona responsabile del ripristino dei dati da un computer protetto con BitLocker. Il ripristino di BitLocker richiede l'accesso fisico al computer in modo da poter immettere la password di ripristino. Questo requisito influenza in modo significativo il processo di definizione di un criterio di recupero, in quanto potrebbero verificarsi scenari in cui un utente remoto o che lavora fuori ufficio abbia la necessità di accedere a un volume protetto da BitLocker.
  
Per impostazione predefinita, tutti gli amministratori di dominio possono leggere le password di ripristino di BitLocker memorizzate in Servizi di dominio Active Directory (AD DS). Gli amministratori di dominio possono delegare questa funzionalità ad altri utenti assegnando loro le autorizzazioni per il controllo dell'accesso e la lettura della proprietà. Allo stesso modo, gli amministratori possono delegare la funzionalità che consente la lettura delle informazioni memorizzate sul proprietario del TPM. Ad esempio, è possibile concedere al personale del supporto tecnico o del supporto telefonico il diritto di accedere alle password di ripristino dell'utente. Tuttavia, prima di effettuare questa operazione è opportuno accertarsi che la concessione di tale accesso sia in linea con i criteri di protezione dell'organizzazione, poiché ogni utente che può accedere alla password di ripristino di un volume è in grado di leggere i dati presenti sul volume senza alcuna restrizione.
  
Prima di specificare un metodo di ripristino obbligatorio, accertarsi di soddisfare i prerequisiti necessari per quel particolare metodo. Questi prerequisiti includono:
  
-   Per le chiavi USB, verificare che il sistema di destinazione consenta di leggere i dispositivi USB all'avvio. Inoltre, effettuare un test su un computer rappresentativo per verificare che il marchio standard della chiave USB funzioni in maniera appropriata con BitLocker prima della relativa distribuzione. Accertarsi che la chiave USB sia disponibile quando si abilita BitLocker per la prima volta.
  
-   Per percorsi di archiviazione alternativi, la prima volta che gli utenti hanno la necessità di eseguire un ripristino, verificare che la password di ripristino sia disponibile. Non utilizzare un percorso di archiviazione alternativo sullo stesso computer, in quanto potrebbe non essere accessibile durante un ripristino del computer. Evitare l'uso di condivisioni di rete che potrebbero non essere protette adeguatamente da accessi da parte di utenti indesiderati o non attendibili.
  
-   Se si desidera stampare la password di ripristino, quando si attiva BitLocker verificare che sia disponibile una stampante locale o di rete connessa. Inoltre, accertarsi di aver pianificato cosa fare con la password stampata poiché i documenti cartacei sono soggetti a rischi e minacce.
  
-   L'archivio Active Directory delle password di ripristino richiede una serie di operazioni preparatorie (come descritto nel capitolo successivo).
  
#### Pianificazione della gestibilità
  
Un passaggio importante nel processo di pianificazione di BitLocker consiste nel decidere la modalità con cui BitLocker influisce sui processi di gestione IT dell'organizzazione. BitLocker influisce sui seguenti processi in corso individuati in ogni organizzazione:
  
-   Gestione degli aggiornamenti software
  
-   Aggiornamenti e sostituzione dell'hardware
  
-   Integrazione con software di imaging, di backup e antimalware
  
-   Gestione della configurazione di BitLocker
  
-   Rimozione delle autorizzazioni dei computer
  
##### Gestione degli aggiornamenti software
  
Sono disponibili tre scenari di gestione degli aggiornamenti software che influiscono sulla pianificazione della distribuzione di BitLocker.
  
Il primo scenario implica gli aggiornamenti del BIOS. BitLocker controlla le modifiche a una serie di componenti, tra cui alcuni aspetti della configurazione del BIOS. Se alcuni di questi parametri cambiano inaspettatamente, BitLocker forzerà un ripristino a ogni riavvio. Per evitare questo problema, prima di aggiornare il sistema BIOS occorre disattivare BitLocker, quindi aggiornare il BIOS e riattivare BitLocker.
  
Il secondo scenario implica aggiornamenti o patch per Windows Vista. Se BitLocker è disattivato con un TPM, sono disponibili due scenari secondari:
  
-   Aggiornamenti che influiscono sul boot manager, sul programma di caricamento del sistema operativo, sull'applicazione utilizzata per il ripristino dallo stato di ibernazione o sull'applicazione di diagnostica della memoria. Nel momento in cui BitLocker rileva l'alterazione di uno o più componenti da parte di Windows Update, aggiorna le informazioni sulla configurazione in modo che riflettano le nuove versioni.
  
-   Gli aggiornamenti che influiscono su altri componenti Windows vengono applicati in base ai meccanismi di aggiornamento tipici di Windows, che non influiscono sui parametri misurati da BitLocker.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
Se BitLocker è stato attivato senza utilizzare il TPM, non è disponibile un percorso attendibile per l'integrità dell'avvio e gli aggiornamenti del sistema non possono forzare un ripristino o un aggiornamento della configurazione.
  
Il terzo scenario prevede gli aggiornamenti della versione o edizione (ad esempio, passare da Windows Vista Enterprise a Windows Vista Ultimate). In uno scenario di questo tipo, è necessario decrittografare l'unità e disattivare BitLocker prima di applicare l'aggiornamento. Al termine dell'aggiornamento, è possibile abilitare BitLocker e crittografare nuovamente l'unità.
  
##### Aggiornamenti e sostituzione dell'hardware
  
Non è possibile caricare e leggere in un altro computer un volume del disco crittografato con BitLocker a meno che non si disponga dell'accesso alla password di ripristino. All'avvio di Windows Vista, è possibile ripristinare il volume immettendo la password di ripristino in modo da consentire il proseguimento del processo di avvio. Questa funzionalità potrebbe richiedere modifiche ai criteri di riparazione e aggiornamento dell'hardware. Le modifiche specifiche variano a seconda di come e quando vengono sostituiti i computer, se si utilizza il software di imaging del disco o di backup per spostare i dati da un computer a un altro e come consentire l'accesso ai dati di ripristino di BitLocker.
  
##### Integrazione con software di imaging, di backup e antimalware
  
BitLocker crittografa i dati a livello del volume del disco. I programmi o le utilità che accedono direttamente al disco mentre Windows è in esecuzione saranno in grado di leggere i dati dal disco, ma i dati verranno crittografati. Ad esempio, gli strumenti di imaging saranno in grado di catturare i contenuti crittografati di un disco protetto da BitLocker, ma non i contenuti dei dati non crittografati.
  
La maggior parte degli strumenti di backup, di ripristino e antimalware in esecuzione durante l'esecuzione di Windows funzioneranno come previsto su un computer che utilizza BitLocker.
  
Inoltre, gli strumenti che modificano i file system Windows o i parametri di configurazione del sistema potrebbero indurre BitLocker a richiedere una password di ripristino al successivo avvio. Anche le modifiche ai criteri, come passare dalla modalità solo TPM a TPM con PIN, potrebbero avviare il processo di ripristino. Per ulteriori informazioni sull'impatto della crittografia di BitLocker sulla gestione degli aggiornamenti software, vedere il [Capitolo 3: Operazioni e scenari di ripristino](http://technet.microsoft.com/it-it/library/cc162802.aspx) della presente guida.
  
##### Gestione della configurazione di BitLocker
  
Insieme a Criteri di gruppo, BitLocker supporta l'uso dello script per controllare e gestire il principale funzionamento della tecnologia. Per ulteriori informazioni sulle interfacce di script quali ProtectKeyWithTPM, vedere il documento [BitLocker Drive Encryption Technical Overview](http://go.microsoft.com/fwlink/?linkid=77977) (in inglese). Alcune organizzazioni potrebbero decidere di utilizzare lo script per applicare i criteri di BitLocker, mentre altre sceglieranno Criteri di gruppo. Questa decisione deve essere presa relativamente presto nel processo di pianificazione.
  
Le opzioni di controllo di BitLocker disponibili nella console Gestione Criteri di gruppo di Windows Vista (o su altri computer su cui sono installati i modelli amministrativi di Windows Vista) consentono di controllare quanto segue:
  
-   Se il backup delle chiavi di BitLocker viene eseguito automaticamente o meno in Active Directory.
  
-   Il percorso predefinito utilizzato per memorizzare le chiavi di ripristino.
  
-   Se gli utenti possono modificare le opzioni di ripristino e di avvio.
  
-   Quale metodo di crittografia viene utilizzato da BitLocker.
  
-   Come viene eseguita la convalida della piattaforma TPM.
  
La parte restante di questa sezione descrive ciascuna delle impostazioni nel modello. È possibile accedere a queste impostazioni da **\\Configurazione computer\\Impostazioni amministrative\\Crittografia unità BitLocker**.
  
###### Attivare il backup di BitLocker sui servizi di dominio Active Directory
  
L'impostazione di questo criterio consente di gestire il backup dei Servizi di dominio di Active Directory (AD DS) delle informazioni sul ripristino di Crittografia unità BitLocker. Per impostazione predefinita, questa impostazione è contrassegnata come **Non configurata**. Se si attiva questa impostazione relativa al criterio, viene eseguito il backup automatico delle informazioni sul ripristino di BitLocker in AD DS dopo l'attivazione di BitLocker per un computer.
  
Le informazioni sul ripristino di BitLocker includono la password di ripristino e alcuni dati di identificazione univoci. È anche possibile specificare che Windows deve eseguire il backup di un pacchetto di chiavi di ripristino contenente una chiave di ripristino del volume protetta da BitLocker, insieme alla password di ripristino. Questo pacchetto di chiavi viene protetto dalla password di ripristino e consente il ripristino nel momento in cui il disco viene danneggiato o corrotto.
  
Se si seleziona l'opzione **Richiedi backup BitLocker su Servizi di dominio** **Active Directory**, non è possibile attivare BitLocker a meno che il computer non sia connesso al dominio e il backup dei servizi di dominio Active Directory venga eseguito correttamente. Questa opzione è selezionata per impostazione predefinita per garantire che sia possibile ripristinare BitLocker. Se questa opzione viene disattivata, BitLocker tenta ancora di registrare le chiavi di ripristino in Active Directory, ma se la registrazione non riesce è possibile proseguire la configurazione di BitLocker. Il backup non viene ritentato automaticamente ed è molto probabile che la password di ripristino non sia stata memorizzata in Servizi di dominio AD durante l'impostazione di BitLocker.
  
![](images/Cc162806.important(it-it,TechNet.10).gif)**Importante:**
  
Per impedire la perdita dei dati occorre disporre di un metodo che consenta il ripristino di BitLocker. Se questa impostazione dei criteri viene disattivata o non viene configurata, il backup delle informazioni sul ripristino di BitLocker non viene eseguito in Servizi di dominio AD.
  
###### Impostazione del Pannello di controllo: configurazione cartella di ripristino
  
L'impostazione di questo criterio consente di specificare il percorso predefinito visualizzato quando Installazione guidata di Crittografia unità BitLocker richiede all'utente di immettere il percorso di una cartella in cui salvare la password di ripristino.
  
Se si attiva questa impostazione relativa al criterio, è possibile specificare il percorso utilizzato come percorso cartella predefinito quando l'utente sceglie l'opzione che consente di salvare la password di ripristino in una cartella. È possibile specificare un percorso completo o includere nel percorso le variabili d'ambiente del computer di destinazione. Se il percorso non è valido, la configurazione guidata BitLocker visualizzerà la cartella principale del computer.
  
Se questa impostazione criteri viene disattivata o non viene configurata, la configurazione guidata BitLocker visualizza la cartella principale del computer quando l'utente sceglie l'opzione che consente di salvare la password di ripristino in una cartella.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
L'utente sarà in grado di selezionare altre cartelle in cui salvare la password di ripristino.
  
###### Impostazione del Pannello di controllo: configurazione cartella di ripristino
  
L'impostazione di questo criterio consente di configurare se la configurazione guidata di Crittografia unità BitLocker richiede all'utente di salvare le opzioni di ripristino di BitLocker.
  
Gli utenti hanno a disposizione due opzioni di ripristino per sbloccare l'accesso ai dati crittografati con BitLocker:
  
-   Immettere una password di ripristino numerica composta da 48 cifre generata in modo casuale.
  
-   Inserire un'unità flash USB che contiene una chiave di ripristino a 256 bit generata in modo casuale.
  
Le chiavi o le password di ripristino vengono generate al momento della configurazione di BitLocker. Se si attiva questa impostazione relativa al criterio, è possibile configurare le opzioni che la configurazione guidata espone agli utenti per il ripristino di BitLocker. Ad esempio, se si disattiva la password di ripristino di 48 cifre agli utenti non potranno stampare o salvare le informazioni di ripristino in una cartella.
  
Se si disattiva o non si configura questa impostazione, la configurazione guidata BitLocker presenterà agli utenti diversi modi per archiviare le opzioni di ripristino. Il salvataggio in un'unità memoria flash USB archivierà la password di ripristino di 48 cifre come file di testo e la chiave di ripristino a 256 bit come file nascosto. Il salvataggio in una cartella archivierà la password di ripristino di 48 cifre come file di testo. La stampa fornirà la password di ripristino di 48 cifre.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
Se è necessaria l'inizializzazione del TPM durante l'installazione di BitLocker, le informazioni sul proprietario del TPM verranno salvate o stampate con le informazioni di ripristino di BitLocker.
  
###### Impostazione del Pannello di controllo: attivazione opzioni di avvio avanzate
  
L'impostazione di questo criterio consente di configurare se la configurazione guidata Crittografia unità BitLocker richiede all'utente di impostare un'autenticazione aggiuntiva necessaria a ogni avvio del computer. In questa impostazione dei criteri, è possibile controllare i seguenti aspetti dell'avvio di BitLocker:
  
-   L'impostazione **Consenti BitLocker senza un TPM compatibile** controlla se è possibile utilizzare BitLocker su computer senza un TPM supportato. Sui computer senza TPM, è necessario utilizzare un dispositivo USB per la chiave di avvio, il che significa che il computer deve essere in grado di leggere un dispositivo USB all'avvio. Senza un TPM, i dati crittografati con BitLocker sono protetti unicamente dal materiale della chiave presente sull'unità flash USB.
  
-   Su un computer con un TPM compatibile, è possibile scegliere quali sono i metodi di avvio disponibili per gli utenti. All'avvio del computer, agli utenti viene richiesto di inserire un'unità flash USB che contiene una chiave di avvio. Potrebbe anche essere necessario inserire un PIN di avvio da 4 a 20 cifre.
  
Se si abilita questa impostazione dei criteri, la procedura guidata visualizza una pagina che consente all'utente di configurare le opzioni di avvio avanzate per BitLocker. È anche possibile configurare le opzioni di impostazione per i computer con e senza un TPM.
  
Se questa impostazione dei criteri viene disattivata o non viene configurata, la configurazione guidata BitLocker visualizza i passaggi fondamentali che consentono agli utenti di attivare BitLocker sui computer con un TPM. In questa procedura guidata di base, non è possibile configurare un ulteriore chiave o PIN di avvio.
  
Se si intende utilizzare BitLocker senza un TPM o con un TPM più un PIN o una chiave di avvio, verificare che i criteri del computer locale (Criteri di gruppo efficaci) siano configurati per le opzioni di avvio avanzate (vedere la seguente figura). Questa configurazione deve essere impostata prima di attivare BitLocker e può essere individuata nel percorso **Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Crittografia unità BitLocker\\Impostazione del pannello di controllo: attivazione opzioni di avvio avanzate**.
  
![](images/Cc162806.01e06e8d-fc15-49cd-a09c-ed805d2c1655(it-it,TechNet.10).gif)
  
**Figura 1.2. Finestra di dialogo Attivazione opzioni di avvio avanzate**
  
###### Configurazione metodo di crittografia
  
Questa impostazione consente di configurare le dimensioni della chiave e dell'algoritmo utilizzati da BitLocker. L'impostazione di questo criterio si applica a un disco completamente decrittografato. La modifica del metodo di crittografia non ha alcun effetto se il disco è già crittografato o se la crittografia è in corso. L'impostazione del criterio dispone di quattro opzioni:
  
-   AES 128 bit e AES 256 bit utilizzano l'algoritmo AES (Advanced Encryption Standard) standard FIPS con la forza della chiave specificata.
  
-   AES 128 bit con diffusione e AES 256 bit con diffusione aggiungono l'algoritmo di diffusione descritto nella guida *Analisi della protezione*. Il livello di diffusione aggiunge alcune proprietà di protezione auspicabili nell'impostazione della crittografia del disco ma che non vengono fornite direttamente da AES nella modalità CBC (Cipher Block Chaining).
  
Se si attiva questa impostazione, è possibile configurare il metodo di crittografia utilizzato in un volume non crittografato. Se si disattiva o non si configura questa impostazione, BitLocker utilizzerà il metodo di crittografia predefinito AES 128 bit con diffusione o il metodo di crittografia specificato dallo script di configurazione dell'amministratore locale.
  
###### Non sovrascrivere la memoria al riavvio
  
Questa impostazione dei criteri controlla le prestazioni di riavvio del computer rispetto al rischio di esposizione dei segreti BitLocker. I segreti BitLocker includono il materiale della chiave utilizzata per la crittografia dei dati. Questa impostazione dei criteri si applica solo quando la protezione BitLocker è attivata.
  
Se si attiva questa impostazione, la memoria del computer non viene sovrascritta al riavvio. Questo consente migliori prestazioni al riavvio ma aumenta il rischio di esposizione dei segreti BitLocker.
  
Se questa impostazione è disattivata o non è configurata, i segreti BitLocker vengono rimossi dalla memoria al riavvio del computer. Per impostazione predefinita, questo criterio non è configurato.
  
###### Configurazione profilo di convalida della piattaforma TPM
  
Questa impostazione consente di configurare il modo in cui l'hardware di protezione TPM protegge la chiave di crittografia di BitLocker. Questa impostazione non si applica se il computer non dispone di un TPM compatibile o se BitLocker è già stato attivato con protezione del TPM.
  
Se si attiva questa impostazione prima dell'attivazione di BitLocker, è possibile configurare i componenti di avvio che saranno convalidati dal TPM prima di sbloccare l'accesso al volume del sistema operativo crittografato con BitLocker. Se uno qualsiasi di questi componenti viene modificato mentre è attiva la protezione BitLocker, il TPM non rilascerà la chiave di crittografia per sbloccare il volume e il computer passerà in modalità di ripristino durante l'avvio.
  
Se si disattiva o non si configura questa impostazione, il TPM utilizzerà il profilo di convalida della piattaforma predefinito o il profilo di convalida della piattaforma specificato dallo script di configurazione dell'amministratore locale. Il profilo di convalida della piattaforma predefinito protegge la chiave di crittografia dalle modifiche al CRTM (Core Root of Trust Measurement), al BIOS, alle estensioni della piattaforma (PCR 0), al codice Option ROM (PCR 2), al codice MBR (Record di avvio principale, Master Boot Record) (PCR 4), al settore di avvio NTFS (PCR 8), al blocco di avvio NTFS (PCR 9), a Boot Manager (PCR 10) e al controllo di accesso BitLocker (PCR 11).
  
![](images/Cc162806.important(it-it,TechNet.10).gif)**Importante:**
  
Le modifiche al profilo predefinito hanno effetto sulla protezione e sulla gestione del computer. La sensibilità di BitLocker alle modifiche (autorizzate o non autorizzate) della piattaforma può aumentare o diminuire, rispettivamente, in base all'inclusione o all'esclusione dei PCR.
  
##### Rimozione delle autorizzazioni dei computer
  
La rimozione delle autorizzazioni dei computer deve essere inclusa come parte della pianificazione. Ad esempio, quali sono le operazioni da eseguire nel caso in cui un computer protetto da BitLocker debba essere riassegnato, spostato al di fuori dell'organizzazione o eliminato a causa di un errore hardware? A causa del livello dell'algoritmo AES utilizzato da BitLocker, l'eliminazione della password di ripristino impedisce in realtà l'accesso a un volume protetto. È opportuno prendere in considerazione criteri e procedure che consentono di verificare che tutte le protezioni vengano rimosse da Active Directory o altri percorsi durante la rimozione delle autorizzazioni di un computer. Per ulteriori informazioni su come rimuovere le protezioni delle autorizzazioni di un computer, vedere [BitLocker Drive Encryption and Disk Sanitation](http://go.microsoft.com/fwlink/?linkid=80648) (in inglese).
  
#### Pianificazione dell'utilizzabilità
  
BitLocker è stato progettato per fornire sistemi di protezione efficaci pur rimanendo trasparenti per gli utenti durante le operazioni tipiche. Tuttavia, gli utenti devono conoscere diversi aspetti per utilizzare BitLocker in maniera efficace e sicura. È necessario sviluppare un criterio di crittografia scritto che descriva l'uso, i requisiti e i problemi operativi che riguardano la crittografia. Prima di procedere con la distribuzione è necessario che gli utenti e il personale di supporto siano informati sull'uso appropriato della crittografia.
  
Un criterio di crittografia dovrebbe risolvere problemi relativi all'uso della crittografia per la protezione dei dati riservati, tra cui:
  
-   I tipi di informazioni da crittografare.
  
-   I tipi di computer che devono utilizzare la crittografia (ad esempio, computer desktop, laptop e così via).
  
-   Soluzioni supportate per la crittografia dei dati (ad esempio, EFS e BitLocker).
  
-   Quali sono i problemi risolvibili o meno dalla crittografia.
  
-   Modalità con cui è possibile archiviare o meno le chiavi e le password di ripristino.
  
-   Chi custodisce le chiavi e le password di ripristino ed è in grado di accedervi.
  
-   Quali sono le operazioni che gli utenti possono e devono effettuare per garantire l'uso appropriato della crittografia.
  
-   Quali sono le responsabilità degli utenti nella gestione delle password di ripristino per i loro computer.
  
-   Problemi potenziali (ad esempio, perdita di dati) correlati alla crittografia.
  
-   Quali procedure seguire per crittografare i file.
  
-   Chi è responsabile del ripristino dei dati crittografati e in che modo gli utenti possono avviare un ripristino.
  
-   In che modo gli utenti possono ottenere supporto per i problemi relativi alla crittografia.
  
Per condividere le informazioni sulla crittografia con gli utenti, utilizzare canali informativi tipici, tra cui fonti online e scritte, incontri online e sessioni hands-on. Questo sforzo può essere eseguito in parallelo al processo di distribuzione.
  
#### Pianificazione dell'implementazione di Active Directory e Criteri di gruppo
  
L'output delle precedenti procedure di pianificazione descrive l'ambito in cui verrà utilizzato Active Directory per consentire la gestione dell'ambiente BitLocker. Le opzioni disponibili sono:
  
-   Utilizzare Active Directory per memorizzare il TPM e le password di ripristino.
  
-   Gestire le impostazioni e le configurazioni per BitLocker con Criteri di gruppo.
  
##### Pianificare l'archiviazione delle password di ripristino in Active Directory
  
Come indicato in precedenza nella sezione "Pianificazione del ripristino dei dati", l'uso di Active Directory per l'archiviazione delle password di ripristino necessita dell'estensione dello schema Active Directory. L'implementazione di questa estensione è un'impresa significativa e deve essere pianificata prima della distribuzione di BitLocker per garantire che l'estensione dello schema avvenga correttamente e che l'ambiente si stabilizzi in maniera appropriata.
  
Il processo di pianificazione delle operazioni di Active Directory con BitLocker deve includere anche l'analisi e la scelta della persona che avrà il compito di eseguire le operazioni di ripristino della chiave e dei dati. Un punto fondamentale da prendere in considerazione è se tenere separata la funzione dell'operatore di ripristino dai ruoli di Amministratore di dominio e Amministratore dell'organizzazione. In alcune organizzazioni esiste una netta separazione dei ruoli, mentre in altre (probabilmente più piccole) sarà possibile demandare agli Amministratori di dominio il compito di eseguire il ripristino dei dati e delle chiavi per il semplice motivo che queste persone hanno già seguito corsi sulle complesse attività tecniche di gestione di Active Directory.
  
##### Controllo crittografia dati BitLocker con Criteri di gruppo
  
Verranno utilizzate le precedenti procedure di pianificazione stabilite con le opzioni di Criteri di gruppo correlate a BitLocker. Le opzioni di Criteri di gruppo da pianificare includono:
  
-   Modalità di archiviazione del TPM e delle password di ripristino in Active Directory.
  
-   Meccanismi di ripristino attivati e disattivati.
  
-   Impostazioni predefinite di BitLocker per la lunghezza e il livello di codifica.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Pianificazione della crittografia del file system
  
Per completare un piano di distribuzione EFS è necessario effettuare quanto segue:
  
1.  Conoscere le opzioni per la distribuzione di EFS
  
2.  Valutare la disponibilità di EFS
  
3.  Stabilire l'ambito di distribuzione di EFS
  
4.  Scegliere la configurazione di EFS
  
5.  Pianificare il ripristino di chiavi e dati
  
6.  Pianificare la gestibilità
  
7.  Pianificare l'utilizzabilità
  
8.  Pianificare l'implementazione di Active Directory e Criteri di gruppo
  
#### Opzioni per la distribuzione di EFS
  
EFS è un'efficace strumento che consente di attenuare diverse minacce alla protezione. Per capire quali sono le minacce che EFS riesce ad attenuare e quali sono invece le minacce che è possibile attenuare combinando EFS con BitLocker, è necessario conoscere il modello di protezione di EFS e le opzioni di distribuzione da esso supportate. Il documento *Analisi della protezione* fornito con questo Toolkit descrive una vasta gamma di minacce e le modalità di attenuazione tramite EFS. Prima di passare alla fase di pianificazione è necessario acquisire familiarità con i contenuti di tale documento.
  
#### Valutazione della disponibilità di EFS
  
Prima di creare un piano di distribuzione di EFS, è necessario valutare la disponibilità dell'organizzazione a distribuire e utilizzare EFS.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
Se si utilizza la funzionalità di roaming delle credenziali di Active Directory, è possibile semplificare notevolmente i piani di distribuzione di EFS. Per ulteriori informazioni, vedere la pagina [Understanding credential roaming](http://technet.microsoft.com/en-us/library/cc783542.aspx) (in inglese) di Microsoft TechNet.
  
##### Requisiti hardware e software
  
EFS non richiede un hardware speciale se non un computer in grado di eseguire una versione del sistema operativo Windows che supporti EFS. Le informazioni specifiche sull'uso di EFS su qualsiasi sistema operativo oltre a Windows XP Professional o le versioni Business, Enterprise o Ultimate di Windows Vista non rientrano nell'ambito di questa guida.
  
##### Requisiti aggiuntivi
  
Oltre ai requisiti hardware e software elencati in precedenza, EFS richiede che:
  
-   Tutti i computer partecipanti eseguano Windows XP o Windows Vista.
  
-   I file e le cartelle da crittografare vengano memorizzati nei volumi formattati NTFS.
  
-   Gli utenti che eseguono la crittografia dei file dispongano delle autorizzazioni NTFS per consentire o modificare il file o la cartella che si sta crittografando.
  
-   Le applicazioni che aprono e modificano i file protetti da EFS siano compatibili con EFS. In genere, qualsiasi applicazione Microsoft Win32 sarà compatibile con EFS. La maggior parte dei problemi di compatibilità si verifica con le applicazioni legacy a 16 bit, sebbene le applicazioni che accedono al file system in modi speciali (che includono pacchetti antivirus, applicazioni di backup e utilità di deframmentazione) meritino un'attenzione speciale.
  
#### Determinazione dell'ambito di distribuzione di EFS
  
La pianificazione della distribuzione di EFS implica decisioni relative alla designazione dei computer e degli utenti che utilizzeranno EFS, nonché dei dati specifici presenti su ciascun computer che necessitano di protezione con EFS. Poiché EFS può essere utilizzato sulla maggior parte dei computer basati su Windows, un processo analitico comincia con la determinazione dei dati da proteggere e identifica gli utenti che dispongono di copie di quei dati e su quali computer è possibile definire completamente l'ambito di una distribuzione di EFS.
  
Per stabilire quali sono i dati che necessitano di protezione, prendere in considerazione le seguenti domande:
  
-   Se i dati sono stati danneggiati o alterati, intenzionalmente o accidentalmente, quali sono le operazioni da eseguire per ripristinarli o ricrearli?
  
-   Nel caso in cui non fosse possibile ripristinare o ricreare i dati, quali sono le implicazioni finanziarie per l'organizzazione?
  
-   Se i dati vengono esposti o divulgati in modo errato, causeranno imbarazzi per l'organizzazione?
  
-   Quale potrebbe essere il costo dell'esposizione pubblica di questi dati?
  
-   Tale esposizione potrebbe risultate dannosa o imbarazzante quanto l'esposizione effettiva del contenuto?
  
-   Se i dati sono stati acquistati da un utente esterno ostile, in che modo possono essere utilizzati per sconvolgere, imbarazzare, ingannare, defraudare o intaccare in qualche modo l'azienda?
  
-   Quale potrebbe essere il costo di questi scenari per l'organizzazione?
  
Gli esempi di dati da crittografare includono quanto segue:
  
-   Contratti, negoziazioni, RFP, RFQ e preventivi, se generati da clienti o per i fornitori.
  
-   Listini prezzi, programmi di sconti o altre informazioni correlate ai prezzi.
  
-   Informazioni sui contatti di collaboratori, clienti e potenziali clienti.
  
-   Note e presentazioni riunioni.
  
-   Promemoria e manuali sui criteri.
  
-   Progettazioni e configurazioni.
  
-   Ricerca e analisi competitiva.
  
-   Dati protetti legalmente (ad esempio, informazioni personali sui clienti).
  
L'intento di questo elenco è quello di stimolare la consapevolezza in materia di protezione.
  
##### File e cartelle che non possono essere crittografati tramite EFS
  
Molti file e cartelle non possono essere crittografati tramite EFS a prescindere dalle autorizzazioni dell'utente. Per impedire che l'utente rimanga in uno stato inattivo, Windows impedisce in modo specifico la crittografia dei dati critici che necessitano di protezione. Questi file e cartelle includono:
  
-   File di avvio critici del sistema all'interno della cartella principale
  
-   %Windir% e tutti gli oggetti figlio
  
-   File che riguardano i profili utente (ossia, Ntuser.\*)
  
-   %APPDATA%
  
-   \\Boot (in Windows Vista)
  
-   \\$Recycle.Bin
  
-   Qualsiasi file o cartella contrassegnato con l'attributo del sistema
  
-   File ibernazione
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
Alcune di queste cartelle consentiranno la crittografia di alcuni dati in esse contenuti, non solo file critici.
  
Alla maggior parte dei file e delle cartelle che non possono essere crittografati da EFS viene negata esplicitamente la crittografia per proteggere l'utente e il computer partecipante. Ad esempio, le chiavi di decrittografia EFS private dell'utente vengono memorizzate nel profilo dell'utente. Se l'utente è in grado di crittografare il proprio profilo, Windows non può in alcun modo ottenere la chiave di decrittografia per decrittografare il profilo utente. Tuttavia, Windows blocca la crittografia dei file da parte degli utenti.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
È possibile utilizzare BitLocker per crittografare i file di sistema prima dell'avvio.
  
Windows Vista consente di crittografare alcuni file e cartelle critici non attivati nelle versioni precedenti di Windows, che comprendono il file di paging del sistema (**pagefile.sys**).
  
##### File e cartelle da non crittografare
  
Esistono altri tipi di file e cartelle che, in genere, non vengono crittografati dagli utenti, anche se il sistema operativo lo consente. Di seguito vengono elencati alcuni esempi:
  
-   File da condividere (a meno che non sia stata attivata la condivisione EFS).
  
-   La cartella \\Programmi e le relative sottocartelle.
  
-   Database condivisi, che comprendono i database di Microsoft Exchange Server.
  
-   File generati su un computer per l'utilizzo o l'elaborazione su un altro (a meno che non sia stata attivata la condivisione di EFS).
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
I file del database condiviso non devono essere crittografati in modo da consentire l'accesso a tutti gli utenti come avviene con il programma database. I file del database vengono protetti meglio mediante la crittografia specifica del campo/attributo.
  
##### Identificazione dei dati e delle posizioni dei dati
  
Uno scenario EFS comune implica la protezione di testo, grafici, fogli di calcolo e presentazioni creati da prodotti quali la suite di Microsoft Office. È necessario eseguire un sondaggio per stabilire se tutti gli utenti all'interno dell'organizzazione utilizzano il percorso predefinito per questo tipo di documenti. Se così fosse, pianificare la crittografia dell'intera cartella su ciascun computer da proteggere.
  
Inoltre, è necessario crittografare la cartella %TEMP% per proteggere tutti i file temporanei dell'applicazione che è possibile creare in questa cartella.
  
Per stabilire dove vengono memorizzati i dati creati, è necessario esaminare le altre applicazioni che interagiscono con i dati riservati.
  
Dopo aver identificato tutti i dati riservati e i percorsi dei dati dell'applicazione, è necessario indicare un criterio scritto per informare gli utenti sulla modalità con cui attivare la crittografia su tali cartelle. È necessario sviluppare anche un piano per configurare e distribuire l'automazione dei criteri al fine di consentire la crittografia automatica.
  
##### Strutture comuni di directory crittografate
  
L'individuazione dei punti in cui gli utenti inseriscono le loro informazioni sensibili riserva alcune sorprese. È fondamentale non specificare, ad esempio, che gli utenti devono conservare i propri documenti nel percorso Documenti\\Riservati, ma verificare che questi non li memorizzino in directory che non devono o non possono essere crittografate, come C:\\ o C:\\WINDOWS.
  
La creazione di una struttura di directory comune per tutti i laptop protetti semplificherà la manutenzione. L'approccio più semplice, ovviamente, consiste nell'impostare un criterio che consente di conservare tutti i documenti nella struttura Documenti. Sebbene questo approccio sia sufficiente per molte organizzazioni, alcune di essere lo troveranno troppo restrittivo e definiranno criteri più complessi e più flessibili.
  
Alcune applicazioni creano file temporanei o di cache che potrebbero contenere dati riservati. Per proteggere le directory contenenti i file dovrebbe essere possibile utilizzare EFS e lo strumento EFS Assistant fornito con questa guida. Tuttavia, nel momento in cui vengono crittografate le directory temporanee o cache, sarà necessario testare le applicazioni per garantire che funzionino adeguatamente.
  
#### Scelta delle opzioni di configurazione di EFS
  
Una volta stabilito l'ambito della distribuzione di EFS, il passo successivo del processo di pianificazione di EFS consiste nello scegliere le opzioni e le configurazioni EFS per i computer dell'organizzazione. Le opzioni da prendere in considerazione e da pianificare includono quanto segue:
  
-   Scegliere se utilizzare certificati autofirmati o emessi dalla CA.
  
-   Scegliere se utilizzare smart card per l'archiviazione dei certificati EFS e delle chiavi.
  
-   Scegliere la crittografia e le dimensioni delle chiavi.
  
-   La possibilità di impedire a EFS di utilizzare certificati autofirmati nel caso non sia presente alcuna autorità di certificazione (CA).
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
Questa funzionalità è inclusa in Windows Vista. Per utilizzarla in Windows XP, vedere l'articolo 912761 della Microsoft Knowledge Base, "[Encrypting File System (EFS) generates a self-signed certificate when you try to encrypt an EFS file on a Windows XP-based computer](http://support.microsoft.com/kb/912761) (in inglese)".
  
I computer basati su Windows Vista offrono diverse opzioni aggiuntive che comprendono le seguenti funzionalità:
  
-   Crittografa il contenuto della cartella Documenti dell'utente
  
-   Richiedi l'uso di una smart card per EFS
  
-   Utilizza la smart card direttamente per tutte le operazioni crittografiche
  
-   Abilita crittografia del file di paging
  
-   Visualizza notifiche del backup della chiave alla creazione o alla modifica della chiave utente
  
Poiché alcune opzioni di configurazione sono possibili solo su Windows Vista, potrebbe essere necessario pianificare un aggiornamento del sistema operativo su determinati computer basati sui requisiti di protezione per una parte dell'organizzazione.
  
##### Scelta di una strategia di certificato digitale
  
I certificati digitali EFS possono essere autofirmati o emessi da una CA attendibile. La prima volta che un utente tenta di crittografare un file o una cartella tramite EFS, Windows verifica se esiste già un certificato o una chiave da poter utilizzare. Nel caso in cui non esista alcuna chiave o certificato, Windows tenta di contattare una CA di emissione. Se la CA di emissione non fornisce una chiave o un certificato, Windows genera un certificato autofirmato per l'utente. Un certificato autofirmato è un certificato digitale che non dispone di un'autorità di firma attendibile di livello superiore per la propria autenticità. In genere, i certificati digitali autofirmati non devono basarsi su terze parti. Tuttavia, i certificati digitali autofirmati sono spesso appropriati per le applicazioni interne come EFS.
  
Generalmente, i certificati digitali EFS autofirmati sono più semplici da implementare inizialmente e più difficili da gestire a livello operativo. Se i servizi PKI appropriati sono già stati implementati, è necessario scegliere i certificati generati dalla CA.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
Le aziende prive di una piattaforma PKI devono prendere in seria considerazione l'implementazione di Servizi certificati prima di attivare e utilizzare EFS. Servizi certificati è disponibile in Microsoft Windows 2000 Server e prodotti server successivi. I vantaggi derivanti dalla gestione del ciclo di vita del certificato digitale EFS e dall'automazione di una soluzione di ripristino comporterà una riduzione complessiva di sforzi e spese.
  
In assenza di una CA partecipante è possibile utilizzare Criteri di gruppo o Criteri del computer locale per consentire o meno a un computer di generare un certificato EFS autofirmato. Questa opzione è trattata nella seguente sezione.
  
Gli amministratori devono valutare i vantaggi e gli svantaggi di ciascun metodo relativo al certificato digitale e prendere una decisione risoluta se utilizzare una soluzione o un'altra. La modifica del metodo basato sulla catena di certificati digitali EFS dopo l'iniziale implementazione di EFS potrebbe risultare scomoda.
  
###### Vantaggi e svantaggi dei certificati autofirmati EFS
  
I certificati autofirmati rappresentano il metodo più semplice per stabilire un'infrastruttura EFS funzionale. Se non viene rilevata alcuna CA PKI partecipante e compatibile, i certificati autofirmati vengono emessi automaticamente ai client EFS. Le operazioni di generazione e installazione di certificati digitali autofirmati sono rapide e trasparenti per l'utente partecipante. Per impostazione predefinita, i certificati autofirmati hanno una validità di 100 anni.
  
Tuttavia, i certificati autofirmati presentano alcuni svantaggi importanti che comprendono quanto indicato di seguito:
  
-   Il lungo periodo di validità dei certificati autofirmati potrebbe rendere il compromesso più verosimile durante il periodo di validità.
  
-   Sono necessari più sforzi per revocare i certificati digitali autofirmati, in quanto è necessario revocare i certificati su ciascun computer singolo piuttosto che su una CA centrale.
  
-   La condivisione dei file crittografati è più difficile. Poiché i certificati autofirmati non vengono pubblicati in Active Directory, non sono accessibili ad altri computer a meno che non vengano spostati manualmente.
  
-   L'automatizzazione dell'archiviazione delle chiavi richiede maggiori sforzi poiché non esiste una posizione centrale in cui archiviare le chiavi.
  
###### Vantaggi e svantaggi dei certificati EFS emessi da un'autorità di certificazione
  
L'emissione di certificati EFS da una CA centralizzata presenta alcuni vantaggi. Questo metodo consente la gestione centralizzata dei certificati digitali e riduce il rischio per la sicurezza in quanto i certificati digitali generati hanno una durata più breve. Il rinnovo, la revoca, la nuova creazione di chiavi e l'archiviazione sono operazioni più semplici da automatizzare poiché il materiale della chiave e del certificato rimane accessibile tramite la CA. Modificando il modello del certificato è anche possibile regolare diversi parametri del certificato. Inoltre, è possibile pubblicare i certificati su Active Directory per semplificare l'individuazione dei certificati da parte degli utenti per la condivisione dei file crittografati EFS.
  
Tuttavia, i certificati EFS emessi dalla CA presentano degli svantaggi. Innanzitutto, è necessario implementare una CA compatibile con EFS prima di distribuirlo. In secondo luogo, il periodo di validità più breve dei certificati emessi dalla CA potrebbe richiedere la creazione più frequente delle chiavi dei certificati. Se i computer basati su Windows non possono contattare una CA partecipante, emettono certificati EFS autofirmati propri. Ne consegue un ambiente misto composto da certificati firmati dalla CA e da certificati autofirmati che complicano la gestione del certificato digitale EFS. Questo problema potenziale può essere risolto configurando Criteri di gruppo per disattivare l'uso dei certificati autofirmati per EFS o disattivando completamente EFS fino a quando non vengono implementati servizi CA necessari.
  
Se si intende utilizzare la registrazione automatica per emettere certificati client da utilizzare con EFS, esaminare attentamente la sezione "Pianificazione di Active Directory e Criteri di gruppo" più avanti in questo capitolo per garantire che l'infrastruttura di Active Directory supporterà la registrazione automatica (la quale richiede almeno un controller di dominio Windows Server 2003 nella foresta).
  
##### EFS e Smart Card
  
Windows XP e Windows Vista supportano entrambi l'uso di smart card con EFS. Come descritto in *Analisi della protezione*, se si utilizzano smart card con EFS, è possibile attenuare il rischio che un utente malintenzionato possa entrare in possesso della password di un utente e utilizzarla per connettersi a un computer e recuperare i file protetti da EFS, uno dei principali fattori di rischio per EFS. La richiesta dell'uso di smart card con EFS consente di aggiungere protezione, ma i metodi per richiedere l'uso di smart card EFS variano da Windows XP a Windows Vista.
  
In Windows XP, è possibile richiedere la smart card per l'accesso. Facoltativamente, potrebbe essere necessario per sbloccare un desktop inattivo o bloccato. In uno scenario di questo tipo, la protezione aggiuntiva per le chiavi EFS deriva dalla presenza necessaria della smart card, ossia l'unico metodo per sbloccare le chiavi EFS e utilizzarle nei file.
  
In Windows XP, è possibile richiedere la smart card per l'accesso e lo sblocco. Tuttavia, è anche possibile richiedere la presenza della smart card ogni volta che un file protetto da EFS viene crittografato o decrittografato. Per impostazione predefinita, Windows Vista deriva una chiave crittografica e la memorizza nella cache per l'uso nelle operazioni EFS. Per una maggiore protezione, Windows Vista può utilizzare direttamente la smart card per ogni operazione crittografica. Tuttavia, questo approccio è meno conveniente per gli utenti ed è molto più lento rispetto alla modalità chiave memorizzata nella cache; di conseguenza, potrebbe non essere adatto in alcuni ambienti.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
Per ulteriori dettagli sulle modalità EFS supportate in Windows Vista e Windows XP, vedere il "Capitolo 3: Crittografia del file system" in *Analisi della protezione*.
  
###### Vantaggi delle smart card
  
Le smart card sono state ideate per offrire una protezione crittografica efficace in un pacchetto portatile, fisicamente protetto. Inoltre, aggiungono protezione alla smart card in quanto scaricano la firma, la verifica, la crittografia e la decrittografia dal computer host. Le chiavi crittografiche vengono memorizzate in modo sicuro nella smart card e vengono considerate protette, in genere, dalla maggior parte degli utenti malintenzionati più sofisticati e consolidati. I certificati associati a una smart card possono essere utilizzati per una serie di miglioramenti alla protezione, che includono la protezione S/MIME per l'autenticazione dell'e-mail basata sul certificato, per le applicazioni Web, l'accesso remoto e l'accesso più sicuro al desktop. La necessità di utilizzare le smart card forza essenzialmente l'uso dell'autenticazione a due fattori, poiché qualsiasi utente che desidera effettuare l'autenticazione deve disporre dalla smart card e della passphrase o PIN associato. Inoltre, non è necessario impostare i sistemi di roaming della credenziale, in quanto le credenziali di ciascun utente vengono memorizzate sulla scheda.
  
###### Svantaggi delle smart card
  
Le smart card dispongono di diversi drawback rilevanti. Innanzitutto, richiedono la distribuzione delle schede stesse insieme ai lettori, il che potrebbe risultare alquanto oneroso per alcune organizzazioni. Il meccanismo di emissione e di controllo del certificato delle smart card deve essere integrato con un PKI causando un aumento dei costi e della complessità delle distribuzioni delle smart card. Le organizzazioni che richiedono smart card devono anche implementare le procedure per emettere e tenere traccia delle schede, un'attività correlata alla sicurezza che deve essere gestita attentamente per evitare eventuali vulnerabilità. Per semplificare il processo di distribuzione della smart card, è possibile distribuire Microsoft [Identity Lifecycle Manager 2007](http://www.microsoft.com/windowsserver/ilm2007) (ILM 2007).
  
##### Scelta di una crittografia
  
EFS può essere implementato con diverse crittografie e forze della chiave. È essenziale essere consapevoli che il tipo di crittografia e di forza della chiave può essere scelto su due oggetti EFS *differenti*: la chiave asimmetrica EFS personale dell'utente e una chiave di crittografia dei file (FEK) simmetrica condivisa del file. Ogni file protetto da EFS dispone di una sola chiave FEK simmetrica. I dati di ciascun file protetto da EFS vengono crittografati con la chiave FEK del file.
  
A ciascun utente autorizzato (o agente di recupero) viene assegnata una copia della chiave FEK del file, che viene crittografata con la chiave pubblica nel certificato EFS dell'utente (e può essere decrittografata solo dalla chiave privata corrispondente dell'utente). Nel momento in cui l'utente deve accedere a un file protetto da EFS, la chiave di crittografia EFS asimmetrica privata personale dell'utente viene utilizzata per decrittografare la copia crittografata dell'utente della chiave FEK del file. La chiave FEK simmetrica appena decrittografata viene utilizzata per decrittografare il file protetto da EFS. Per decidere il tipo di crittografia e la forza della chiave, è essenziale conoscere la differenza tra i due tipi di chiavi EFS.
  
###### Crittografie supportate
  
Le crittografie dell'algoritmo di crittografia per la chiave FEK sono le seguenti, nell'ordine dalla meno sicura alla più sicura:
  
-   Data Encryption Standard (DES)
  
-   Data Encryption Standard Expanded (DESX)
  
-   Triple Data Encryption Standard (3DES)
  
-   Advanced Encryption Standard (AES)
  
Per impostazione predefinita Windows Vista, Windows XP Professional (SP1 e versioni successive) e Windows Server 2003 utilizzano la crittografia AES complessa. Le versioni precedenti di Windows XP Professional utilizzavano DESX per impostazione predefinita, ma è possibile passare alla crittografia 3DES più complessa. A tal fine, è necessario attivare il criterio di protezione **Utilizza algoritmi FIPS compatibili per crittografia, hash e firma** in Criteri di gruppo, Criteri del computer locale oppure modificare direttamente il Registro di sistema. Windows 2000 utilizza le crittografie DES o DESX per EFS. DESX viene utilizzato automaticamente per qualsiasi versione di Windows 2000 SP1 o successiva.
  
Se in Windows XP Professional SP1 (o versioni successive) o in Windows Server 2003 è stata attivata l'opzione FIPS, la protezione crittografica passa di fatto da AES a 3DES. Tuttavia, se l'opzione FIPS è attivata, sono necessari i server IIS (Internet Information Service) e i client Microsoft Internet Explorer per l'uso di TLS (Transport Layer Security) invece dell'SSL (Secure Sockets Layer), più debole per le transazioni Web sicure. La richiesta di un TLS più forte può essere eseguita anche a livello del server, senza attivare la sicurezza FIPS e ridurre la sicurezza della chiave simmetrica sui client basati su Windows XP.
  
L'algoritmo di crittografia asimmetrica predefinito utilizzato per crittografare le chiavi FEK è RSA sia per le chiavi autofirmate che per quelle emesse da un'autorità di certificazione basata su Microsoft.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
L'algoritmo predefinito utilizzato è sempre la crittografia più sicura disponibile al momento. Ogni versione di Windows è in grado di gestire tutte le crittografie supportate della versioni precedenti. Microsoft consiglia di non modificare le impostazioni di crittografia per EFS salvo quando richiesto per esigenze di conformità alle normative.
  
###### Dimensioni della chiave EFS
  
Windows XP e Windows Vista consentono flessibilità nelle dimensioni della chiave asimmetrica dell'utente e la chiave di crittografia FEK del file, sebbene vi sia meno flessibilità nella dimensione della chiave FEK. La scelta dell'algoritmo crittografico FEK determina la forza della chiave simmetrica di FEK. L'utilizzo di dimensioni chiave più grandi può incrementare la protezione EFS, ma potrebbe provocare un maggiore calo delle prestazioni, a seconda dell'algoritmo in uso.
  
**Dimensioni della chiave asimmetrica dell'utente**
  
In genere, le dimensioni della chiave asimmetrica EFS possono variare da 1.024 a 16.384 bit. Le dimensioni tipiche della chiave sono: 1.024, 2.048, 4.096, 8.192 e 16.384 bit. In Windows Vista, la dimensione predefinita della chiave è di 2.048 bit, sufficientemente sicura per quasi tutte le applicazioni EFS. Microsoft raccomanda di mantenere questa dimensione predefinita per le nuove distribuzioni di EFS. Nelle versioni precedenti di Windows veniva utilizzata la dimensione della chiave predefinita di 1.024 bit.
  
**Dimensioni della chiave FEK simmetrica**
  
Le crittografie della chiave FEK simmetrica di EFS vanno da 56 bit nelle versioni precedenti di Windows a 256 bit AES in Windows Vista. Windows 2000 utilizza chiavi DESK a 128 bit se è installato il pacchetto crittografia elevata o SP1 o versione successiva; altrimenti, viene utilizzata una chiave a 56 bit. Windows XP SP 1 (o successiva) e Windows Server 2003 utilizzano AES a 256 bit per impostazione predefinita. Prima del SP1, Windows XP utilizzava DESX ma poteva essere impostato per utilizzare DES a 168 bit.
  
In genere, la maggior parte degli utenti viene soddisfatta consentendo l'utilizzo delle chiavi FEK EFS predefinite. Tuttavia, alcune organizzazioni richiedono l'uso di chiavi di crittografia precedenti o dimensioni della chiave personalizzate.
  
##### EFS e Windows Vista
  
Windows Vista offre alcuni miglioramenti significativi in EFS. È opportuno prendere in considerazione dove e come distribuire Windows Vista per l'uso appropriato di questi miglioramenti, che includono:
  
-   La possibilità di richiedere l'uso di una smart card per EFS. Questa funzionalità fornisce vantaggi significativi in termini di protezione e gestibilità, in quanto EFS può essere gestito con un processo già utilizzato per la gestione delle smart card.
  
-   La possibilità di utilizzare la smart card direttamente per tutte le operazioni crittografiche (nota come modalità non cache) o di consentire a Windows di memorizzare una chiave crittografica derivata (nota come modalità cache). Queste modalità, descritte in dettaglio nel "Capitolo 3: crittografia del file system" in *Analisi della protezione*, consentono di bilanciare protezione, prestazioni e vantaggi per l'utente.
  
-   La possibilità di crittografare il file di paging del sistema. Questa funzionalità consente di evitare la divulgazione accidentale delle informazioni riservate impedendo a un utente malintenzionato di analizzare il file di paging quando Windows non è in esecuzione.
  
-   La possibilità di ricordare agli utenti di eseguire il backup delle chiavi durante l'aggiornamento delle chiavi esistenti o la creazione di nuove chiavi.
  
-   La possibilità di impedire agli utenti di creare certificati autofirmati propri da usare con EFS quando non è disponibile alcuna CA. Questa funzionalità consente di limitare l'uso di EFS al di fuori dell'infrastruttura della chiave pubblica.
  
Se queste funzionalità sono importanti per l'organizzazione, è necessario prendere in considerazione la modalità con cui coordinare la distribuzione di EFS e di Windows Vista. Distribuzione guidata Windows consente di attivare BitLocker come parte di una distribuzione Lite Touch. EFS equivale alla registrazione automatica dei certificati utente, pertanto all'installazione di EFS Assistant (come parte dell'immagine Windows Vista o tramite altri metodi) in modo che i file riservati possano essere automaticamente protetti.
  
##### EFS e condivisione di file
  
A partire da Windows XP Professional, i file e le cartelle protette da EFS possono essere condivisi con altri utenti. Il primo utente (o un agente di recupero dati EFS) che deve crittografare un file o una cartella deve aggiungere ulteriori utenti al file o alla cartella. Gli altri utenti devono già disporre di certificati digitali EFS validi.
  
Gli utenti che dispongono delle autorizzazioni per la scrittura, la cancellazione o la modifica sono in grado di modificare o eliminare i file e le cartelle protette da EFS anche se non possono crittografare o decrittografare quegli stessi file o cartelle. EFS protegge la riservatezza, vale a dire che gli utenti non autorizzati non possono leggere, visualizzare o stampare file protetti, ma sono in grado di gestire il file senza visualizzare o leggere i contenuti. Se la possibilità di condividere i file tra più utenti è importante, è necessario garantire che i propri criteri organizzativi siano chiari per quanto concerne la persona responsabile della crittografia dei file, la quale avrà la possibilità di leggerli e l'autorità di aggiungere o rimuovere utenti condivisi per i file crittografati.
  
#### Pianificazione del ripristino di chiavi e dati
  
Le organizzazioni che scelgono di distribuire EFS dovranno pianificare attentamente la modalità di ripristino dei dati in determinate situazioni, ad esempio quando un utente lascia l'organizzazione, la propria workstation è bloccata o il certificato EFS e le chiavi sono corrotte. Le più importanti attività di pianificazione per il ripristino dei dati EFS sono documentate nella sezione "Data Protection and Recovery in Windows XP/[Data Recovery Overview](http://technet.microsoft.com/en-us/library/bb457020.aspx)" della documentazione di Windows XP. Questa sezione fornisce ulteriori istruzioni sui problemi da tenere in considerazione durante la pianificazione.
  
EFS è una soluzione di crittografia file sicura. Se le chiavi di crittografia utilizzate per decrittografare i file protetti non sono più disponibili, è possibile che anche i file protetti diventino non disponibili. Se non esiste un backup dei dati non crittografato o se non viene distribuito un metodo di ripristino della crittografia, i file protetti potrebbero rimanere non disponibili in modo permanente.
  
Come trattato in precedenza in questa guida, per proteggere i dati EFS utilizza una combinazione di algoritmi della chiave simmetrica e asimmetrica (pubblica/privata). Nello scenario predefinito, viene generata una chiave di crittografia dei file (FEK) simmetrica, la quale viene poi crittografata mediante la chiave pubblica da un certificato X.509. Per una strategia di backup dei dati crittografati da EFS sono disponibili due tipi di approcci differenti:
  
-   Creare backup delle chiavi private associate al certificato X.509. Questo approccio viene indicato, generalmente, come recupero chiavi poiché enfatizza la protezione del materiale della chiave come metodo per impedire l'accesso ai file protetti.
  
-   Creare ulteriori copie crittografate della chiave FEK copiata con certificati differenti. Questo approccio viene definito come recupero dati in quanto consente di recuperare i dati anche dopo la perdita della chiave o del certificato originale.
  
##### Recupero chiavi
  
Recupero chiavi implica che la parte della chiave privata di una coppia di chiavi pubblica/privata possa essere archiviata e ripristinata, se necessario. Se la copia dell'utente della chiave privata viene persa o danneggiata, a prescindere se sia stata memorizzata su una smart card o in un computer locale, è possibile recuperare la chiave dal percorso di backup. Dopo il recupero di una chiave privata, è possibile decrittografare tutti i dati (o più precisamente, tutte le chiavi simmetriche crittografate come FEK). In Windows, questa funzionalità viene fornita in due modi: mediante l'uso degli agenti di recupero chiavi o l'archiviazione manuale delle chiavi.
  
###### Uso dell'agente di recupero chiavi
  
Se si utilizza Servizi certificati o un'altra CA compatibile, per consentire il recupero dei file è possibile utilizzare un agente di recupero chiavi (KRA). La CA di emissione può archiviare automaticamente i certificati digitali EFS man mano che vengono emessi; tale archivio viene poi utilizzato da KRA per recuperare le chiavi EFS perse. La principale differenza operativa tra un DRA di EFS e un KRA è che i DRA di EFS hanno accesso esplicito a tutti i file protetti da EFS partecipanti, mentre gli agenti di recupero chiavi (KRA) possono recuperare solo le copie memorizzate delle chiavi di altre persone. I KRA possono partecipare anche agli eventi di recupero chiavi del certificato digitale oltre a EFS.
  
Se i modelli del certificato vengono configurati per richiedere l'archiviazione della chiave, l'archiviazione automatica viene effettuata come parte del processo di registrazione dei certificati. Se configurata in questo modo, la chiave privata verrà inviata alla CA come parte della procedura di richiesta certificati e la chiave privata verrà archiviata automaticamente dalla CA.
  
Per ulteriori informazioni sulla pianificazione e l'implementazione del meccanismo di archiviazione e recupero chiavi, vedere [Key Archival and Management in Windows Server 2003](http://technet.microsoft.com/en-us/library/cc755395.aspx) (in inglese).
  
###### Archiviazione manuale delle chiavi
  
Se la distribuzione di EFS si basa sui certificati autofirmati, l'archiviazione manuale delle chiavi è l'unico modo per eseguire il backup della chiave privata necessaria per decrittografare FEK. Per impostazione predefinita, tutti gli utenti di EFS possono eseguire un backup dei relativi certificati digitali EFS e la chiave di decrittografia EFS privata. Windows Vista richiede agli utenti di eseguire il backup delle chiavi ogni volta che vengono create o modificate. Tutte le versioni di Windows successive a Windows 2000 consentono agli utenti di eseguire manualmente il backup delle chiavi EFS, mediante due o più metodi. Se consentito dal criterio di protezione, gli utenti devono eseguire il backup delle chiavi EFS e archiviarle in due o più luoghi protetti utilizzando dispositivi di archiviazione attendibili.
  
Con l'archiviazione manuale della chiave, gli utenti esportano manualmente le chiavi private e le inviano a un amministratore della CA il quale, a sua volta, le importa nel database protetto della CA.
  
Questo approccio consente agli utenti di assumersi la responsabilità delle chiavi di recupero. Tuttavia, è difficile da monitorare e regolare nelle organizzazioni di grandi dimensioni e non esiste alcun metodo attendibile per stabilire se un utente ha archiviato o meno una chiave EFS, entrambi i casi importanti per la compatibilità con i criteri.
  
##### Recupero dati
  
Recupero dati è un processo leggermente differente che non implica l'archiviazione delle chiavi associate a un certificato X.509 qualsiasi. Al contrario, questo processo crea percorsi ridondanti per l'accesso a un file crittografato creando altre chiavi FEK crittografate, ognuna crittografata con la chiave pubblica di un certificato X.509 differente. Le chiavi aggiuntive create da questo processo vengono definite agenti di recupero dati.
  
Quando viene crittografato un file, Windows effettua automaticamente una copia della chiave FEK del file e la crittografa con la chiave EFS pubblica del DRA. Questa funzionalità indica che un DRA può decrittografare qualsiasi file protetto da EFS.
  
Il principale vantaggio di un DRA è che ogni file protetto da EFS dispone automaticamente di una copia della chiave FEK del file creata per impostazione predefinita. Non è necessario che un utente crei manualmente chiavi di backup. Il maggiore svantaggio è che se l'account utente del DRA risulta compromesso sono possibili intrusioni ai file protetti da EFS.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
Per proteggere qualsiasi account utente del DRA è necessario utilizzare ulteriori metodi di protezione. Inoltre, è possibile esportare e memorizzare esternamente la chiave di recupero EFS dell'agente di recupero per impedire che l'EFS venga compromesso in seguito alla compromissione dell'account dell'agente. La chiave di recupero EFS può essere importata successivamente, se necessario.
  
Implementando il recupero dati e gli agenti di recupero dati, ogni chiave di crittografia del file crittografato viene crittografata mediante la chiave pubblica del DRA oltre alla chiave pubblica dell'utente. Utilizzando la chiave privata associata, qualsiasi DRA designato è in grado di decrittografare e crittografare il file nell'ambito del criterio di ripristino EFS.
  
##### Definizione di un criterio di recupero
  
Il criterio di recupero definisce la persona a cui è consentito il recupero dei dati, le circostanze in cui possono essere eseguiti tali recuperi; inoltre, rappresenta una parte importante della pianificazione EFS. Il criterio deve definire:
  
-   Gli utenti o i ruoli a cui è consentito il recupero dei dati.
  
-   Gli utenti o i ruoli a cui è consentito il recupero dei dati di altri utenti.
  
-   I controlli commerciali o normativi da applicare al recupero dei dati.
  
-   La modalità con cui verrà controllato l'uso degli strumenti di recupero dati per garantire che non vengano utilizzati in modo scorretto.
  
-   La modalità con cui verranno raccolti, memorizzati e salvaguardati i materiali della password di ripristino.
  
-   Le workstation o le risorse che è possibile utilizzare per eseguire le operazioni di ripristino.
  
Se possibile, Microsoft consiglia di scegliere una delle due procedure consigliate per il criterio di recupero. Il metodo di recupero preferito consiste nell'emettere un certificato DRA su una smart card, quindi proteggere separatamente la smart card e il relativo PIN. Un computer basato su Windows Vista può utilizzare questa smart card e il certificato associato per ripristinare i dati da qualsiasi client nel dominio. Questa combinazione fornisce una protezione complessa a due fattori per le credenziali DRA ed è possibile forzare l'accesso separato alla smart card e al PIN in modo da garantire la separazione dei compiti di ripristino.
  
Negli ambienti in cui ciò non è fattibile, Microsoft consiglia di definire e configurare computer separati che vengono utilizzati solo per il recupero dei dati. Queste workstation di ripristino devono essere protette fisicamente e devono disporre di ulteriori misure di controllo e di protezione, proporzionali al valore dei dati da ripristinare.
  
###### Pianificazione della scadenza del DRA
  
Gli agenti di recupero dati EFS utilizzano certificati che hanno una scadenza, come tutti gli altri certificati. Tuttavia, i certificati convenzionali vengono utilizzati di solito per fornire maggiore segretezza: proteggono il materiale che deve rimanere crittografato per un determinato periodo di tempo in futuro. Per preservare la segretezza è necessario che la chiave associata al certificato scada in un periodo di tempo futuro non precisato in modo che sia possibile creare una nuova chiave.
  
I DRA non forniscono la segretezza: consentono il ripristino dei dati. Questa funzionalità indica che un certificato DRA scaduto è ancora utile per ripristinare i dati crittografati durante il periodo di validità del certificato DRA. Per preservare la possibilità di ripristinare i dati a prescindere dalla data di creazione, occorre pianificare l'archiviazione dei certificati DRA in un dispositivo di archiviazione sicuro in modo che siano disponibili per eventuali consulti futuri, se necessario.
  
Alla scadenza di un certificato DRA, è possibile emetterlo nuovamente o creare una nuova chiave. Dopo aver eseguito queste operazioni, è possibile utilizzare il DRA per ripristinare i dati appena creati. Tuttavia, è opportuno conservare una copia del certificato DRA precedente per ripristinare i dati protetti dal DRA precedente. Quando vengono sviluppate procedure e criteri per gestire (o prevenire) la scadenza del DRA, considerare quanto segue:
  
-   Se un certificato DRA attivo è scaduto (anche se il client ha configurato più certificati DRA), Windows non consentirà la crittografia di alcun nuovo file. Questa funzionalità indica che un'organizzazione deve garantire l'emissione di nuovi certificati DRA e la sostituzione di certificati a breve scadenza sufficientemente in anticipo per evitare che Criteri di gruppo disponga di un certificato DRA scaduto.
  
-   La sostituzione di certificati DRA (e le successive procedure, anche se facoltative, necessarie per aggiornare i file client) è un processo semplice a più fasi.
  
-   Qualsiasi oggetto Criteri  di gruppo (GPO) che configura i DRA deve contenere più di un DRA. Questo approccio fornisce una protezione ridondante contro la perdita dei dati causata dalla perdita dell'accesso a una sola chiave privata DRA.
  
###### Determinazione del livello del criterio di recupero dati
  
Nel momento in cui l'amministratore accede per la prima volta al controller di dominio, in tale dominio viene introdotto automaticamente un criterio di recupero predefinito, il che rende l'amministratore l'agente di recupero del dominio. Windows XP, Windows Vista e Windows Server 2003 non richiedono più un criterio di recupero attivo per crittografare i file.
  
Per i computer autonomi il criterio di recupero predefinito viene configurato localmente, Per i computer che fanno parte di un dominio basato su Active Directory, il criterio di recupero viene configurato sul sito, sul dominio, sull'unità organizzativa (OU) o al livello di singolo computer e si applica a tutti i computer basati su Windows 2000, Windows Server 2003, Windows XP e Windows Vista nell'ambito di influenza definito. I certificati di ripristino vengono emessi da un'autorità di certificazione (CA) e gestiti mediante lo snap-in Certificati di Microsoft Management Console (MMC).
  
In un ambiente di rete, l'amministratore del dominio determina la modalità di implementazione di EFS nei criteri di ripristino applicati a tutti gli utenti e ai computer nell'ambito di influenza specifico. In un'installazione predefinita di Active Directory, durante la configurazione del primo controller di dominio, l'amministratore del dominio viene impostato come agente di recupero per il dominio. L'implementazione di EFS nei computer locali degli utenti dipende dalla modalità con cui l'amministratore del dominio configura il criterio di recupero. Per modificare il criterio di recupero del dominio, l'amministratore del dominio utilizza l'editor Criteri di gruppo da qualsiasi computer client o server connesso al dominio. Per un computer autonomo (non connesso a un dominio), il periodo di scadenza di un certificato DRA dell'account amministratore è di 100 anni. Per un computer aggiunto al dominio, il certificato DRA predefinito emesso dall'amministratore del dominio ha un periodo di scadenza di tre anni.
  
L'amministratore può scegliere fra tre possibilità:
  
-   **Criterio dell'agente di recupero**. Questo tipo di criterio viene applicato quando l'amministratore aggiunge uno o più agenti di recupero, che hanno il compito di ripristinare tutti i dati crittografati contenuti nei rispettivi ambiti di amministrazione. Un criterio dell'agente di recupero è il tipo più comune di criterio di recupero. I criteri dell'agente di recupero possono essere utilizzati per distribuire il carico di lavoro amministrativo all'interno dell'organizzazione; inoltre, è possibile indicare account di recupero EFS alternativi per le categorie di computer raggruppati dalle unità organizzative. Potrebbe anche essere possibile configurare le impostazioni degli agenti di recupero dati crittografati per i computer portatili in modo che utilizzino gli stessi certificati dell'agente di recupero sia quando sono connessi al dominio sia quando funzionano come computer autonomi.
  
-   **Criterio di recupero vuoto**. Questo tipo di criterio viene applicato quando l'amministratore elimina tutti gli agenti di recupero e i rispettivi certificati a chiave pubblica. Quando è in vigore un criterio di questo tipo, non è disponibile alcun agente di recupero e, se il sistema operativo client è Windows 2000, il sistema EFS viene disattivato. Il client Windows XP consente a EFS di funzionare con un criterio DRA vuoto.
  
-   **Nessun criterio di recupero**. Questo criterio viene applicato quando un amministratore elimina le chiavi private associate a un criterio di recupero specifico. Poiché non è disponibile alcuna chiave privata, non è possibile utilizzare alcun agente di recupero e, quindi, ripristinare i dati. Questo tipo di criterio dovrebbe essere utile per le organizzazioni con un ambiente misto di client Windows 2000 e Windows XP che non richiedono il recupero dei dati.
  
Sebbene in un ambiente Active Directory l'agente DRA predefinito sia costituito dall'amministratore del dominio, questa responsabilità può essere delegata o assegnata anche a uno o più utenti.
  
##### Scelta del meccanismo corretto
  
Le strategie di recupero chiavi e dati possono essere utilizzate separatamente o insieme. Occorre, tuttavia, considerare molti problemi operativi o di protezione. È possibile trovare ulteriori informazioni in [Key Archival and Management in Windows Server 2003](http://technet.microsoft.com/en-us/library/cc755395.aspx) (in inglese). Si consiglia di rivedere queste informazioni prima di decidere quale strategia, o combinazioni di strategie, utilizzare.
  
#### Pianificazione della gestibilità
  
Un passaggio importante nel processo di pianificazione di EFS consiste nel decidere la modalità con cui EFS influisce sui processi di gestione IT dell'organizzazione. EFS influisce sui seguenti processi in corso individuati in ogni organizzazione:
  
-   Integrazione con software di imaging, di backup e antimalware
  
-   Pianificazione di EFS e della condivisione di file
  
-   Rimozione delle autorizzazioni dei computer
  
##### Integrazione con software di imaging, di backup e antimalware
  
La maggior parte delle applicazioni di imaging, di backup e antimalware di terze parti sono state ideate e testate per funzionare con EFS. Una delle procedure necessarie della pianificazione al fine di garantire la piena soddisfazione dei contratti di assistenza IT consiste nel conoscere gli strumenti utilizzati da un'organizzazione e testarli insieme a EFS. I criteri di test devono stabilire se le applicazioni funzionano correttamente con i dati crittografati e se gli strumenti rimangono nello stato crittografato o meno, a seconda dei requisiti dell'organizzazione.
  
###### Copia e spostamento dei file
  
La copia o lo spostamento dei file protetti da EFS potrebbe causare modifiche allo stato di crittografia del file. Le regole generali su come la copia o lo spostamento dei file influenza la crittografia sono:
  
-   Se si copia un file o una cartella *nello stesso computer* da una partizione NTFS in un'altra partizione NTFS, il file verrà crittografato nella destinazione.
  
-   Se si copia un file o una cartella da una partizione NTFS su un computer in un'altro tipo di partizione, a prescindere dal fatto che le partizioni si trovino nello stesso computer, la copia non viene crittografata perché il file di destinazione non supporta la crittografia.
  
-   Se si copia un file o una cartella tra le partizioni NTFS su due computer, il file di destinazione verrà crittografato se il computer remoto consente la crittografia dei file; in caso contrario, non verrà crittografato. Tenere presente che il computer remoto deve essere affidabile per la delega. In un ambiente di dominio, la crittografia remota non viene attivata per impostazione predefinita.
  
La gestione delle utilità in grado di copiare i file nella loro totalità senza leggere i file di dati dovrebbe funzionare come previsto. Ad esempio, l'utilità Windows Backup (e la maggior parte degli altri programmi di backup) legge l'intera serie di tutti i dati NTFS dei file di cui viene eseguito il backup, pertanto il backup può procedere senza dover accedere al materiale della chiave dell'utente. I file sottoposti a backup tramite questo metodo rimarranno crittografati nel dispositivo di backup.
  
![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
L'utilità di backup inclusa con Windows Vista non può eseguire il backup dei file crittografati da EFS. Se non si utilizza uno strumento di backup di terze parti, è possibile utilizzare ancora lo strumento Robocopy con l'opzione /efsraw per automatizzare il backup dei file protetti da EFS sui computer che eseguono Windows Vista.
  
###### Strumenti di imaging del disco
  
Analogamente, gli strumenti di imaging del disco che catturano i contenuti dell'intero file system preserveranno lo stato di EFS dei file protetti, in quanto leggono singoli blocchi del disco. La creazione dell'immagine di un computer che contiene dati protetti da EFS includerà i dati crittografati da EFS come parte dell'immagine. Alcuni strumenti di imaging consentono di aprire un'immagine e visualizzare o modificare singoli file nell'immagine senza ripristinare l'immagine in un computer di destinazione. Questi strumenti, in genere, non funzionano in maniera adeguata con i file crittografati da EFS e l'utente non sarà in grado di aprire o modificare i file crittografati catturati in un'immagine a meno che il computer su cui vengono aperti i file non disponga del materiale della chiave corretto.
  
###### Strumenti antimalware
  
I programmi antimalware (che includono software antivirus e antispyware) funzionano generalmente in due modi:
  
-   Intercettano le richieste di apertura file ed eseguono la scansione per eventuali malware prima che l'utente possa accedere al file. I programmi che utilizzano questi meccanismi funzioneranno generalmente con EFS perché la scansione viene eseguita dopo che l'applicazione richiede i dati da un file e la richiesta viene effettuata nell'ambito del contesto di protezione dell'utente.
  
-   Questi programmi utilizzano un account di sistema (ad esempio SISTEMA LOCALE o SERVIZIO DI RETE) per effettuare la scansione dei file su un computer a prescindere dal proprietario. Gli strumenti che utilizzano questo meccanismo non saranno in grado, generalmente, di analizzare i file protetti da EFS, perché quando tentano di aprire il file viene generato un errore di accesso negato.
  
Singoli programmi antimalware potrebbero combinare questi due approcci. Rivedere la documentazione relativa alle soluzioni antimalware e testarle per garantire che funzionino adeguatamente con i file protetti da EFS nell'ambiente.
  
##### Pianificazione di EFS e della condivisione di file
  
Se l'organizzazione ha la necessità di condividere i dati riservati tra più utenti lo può fare in due modi: mediante l'archiviazione delle cartelle condivise su server di file o l'utilizzo delle cartelle Web. Entrambi i metodi richiedono la configurazione per supportare EFS, inoltre è necessario conoscere eventuali problemi, vantaggi e rischi.
  
-   Se i file crittografati vengono memorizzati su un server file remoto, è possibile scegliere se consentire al server di mantenere copie non crittografate dei file o se questi devono rimanere crittografati sul server. Se si intende fornire l'accesso condiviso ai file crittografati continuando a proteggerne i contenuti sui PC portatili, è possibile mantenere copie di file non crittografati sul server. Se i file protetti devono rimanere crittografati a prescindere dal percorso di archiviazione, sarà opportuno configurare il server in maniera appropriata (il che richiede che il server sia affidabile per la delega in Active Directory).
  
-   Se si utilizza Windows XP o Windows Server 2003, è possibile memorizzare file crittografati nelle cartelle Web. Questo approccio rende disponibili i file per le applicazioni che possono utilizzare DAV per accedere a cartelle Web (che includono Microsoft Office 2000 e versioni successive); inoltre, consente di renderli disponibili per gli utenti tramite le applicazioni basate sul Web.
  
##### Pianificazione della rimozione delle autorizzazioni
  
EFS esegue solo la crittografia dei file selezionati, mentre il materiale della chiave può essere conservato sul volume del sistema nelle modalità operative. Quando vengono rimosse le autorizzazioni di un computer che contiene contenuti protetti da EFS, occorre seguire le normali procedure di eliminazione autorizzazioni per garantire che tutti i file riservati vengano spostati.
  
#### Pianificazione dell'utilizzabilità
  
EFS è un metodo sicuro per la crittografia di file e cartelle sui volumi NTFS. È necessario che venga distribuito un criterio di crittografia scritto che descrive l'uso, i requisiti e i problemi operativi impliciti alla crittografia. Prima di procedere con la distribuzione è necessario che gli utenti e il personale di supporto siano informati sull'uso appropriato della crittografia.
  
Un criterio di crittografia deve descrivere i problemi correlati alla crittografia dei dati riservati, che includono:
  
-   I tipi di informazioni da crittografare.
  
-   I tipi di computer che devono utilizzare la crittografia (ad esempio, computer desktop, laptop e così via).
  
-   Soluzioni supportate per la crittografia dei dati (ad esempio, EFS e BitLocker).
  
-   Problemi risolvibili e non della crittografia.
  
-   Quali algoritmi crittografici e dimensioni minime della chiave sono accettabili per la protezione dei dati dell'organizzazione.
  
-   Quali sono le operazioni che gli utenti possono e devono effettuare per garantire l'uso appropriato della crittografia.
  
-   Problemi potenziali (ad esempio, perdita di dati) correlati alla crittografia.
  
-   Quali procedure seguire per crittografare i file.
  
-   Modalità con cui gli utenti possono confermare la crittografia dei dati (ad esempio, il file evidenziato con caratteri verdi in Esplora risorse, Cipher.exe e così via).
  
-   Persona responsabile del ripristino dei dati crittografati e modalità di avvio di un ripristino da parte degli utenti.
  
-   In che modo gli utenti possono ottenere supporto per i problemi relativi alla crittografia.
  
Per condividere le informazioni sulla crittografia con gli utenti, utilizzare canali informativi tipici, tra cui fonti online e scritte, incontri online e sessioni hands-on. Questo sforzo può essere eseguito in parallelo al processo di distribuzione.
  
#### Pianificazione dell'implementazione di Active Directory e Criteri di gruppo
  
Active Directory e Criteri di gruppo forniscono il metodo più efficace per la gestione della configurazione e del criterio EFS. Il funzionamento di EFS può essere influenzato dalle seguenti impostazioni dell'oggetto Criteri di gruppo.
  
-   In **Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri locali\\Opzioni di protezione**
  
    -   **Arresto del sistema: cancella il file di paging della memoria virtuale**. Con questa impostazione, al momento dell'arresto del sistema, il sistema operativo elimina i contenuti del file di paging. Questa configurazione riduce il rischio di perdita di dati non crittografati tramite il file di paging.
  
    -   **Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash e firma**. Per impostazione predefinita, EFS utilizza l'algoritmo AES (Advanced Encryption Standard) con una chiave a 256 bit su computer basati su Windows XP Service Pack 1 (SP1) e Windows Server 2003. Tuttavia, se si attiva l'impostazione **Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash e firma** su questi computer, il sistema operativo utilizzerà 3DES con una chiave a 168 bit. Sui computer Windows Vista questa impostazione provocherà l'uso di AES da parte di EFS.
  
    ![](images/Cc162806.note(it-it,TechNet.10).gif)**Nota:**
  
    L'utilizzo del criterio FIPS non è il metodo consigliato per la gestione degli algoritmi di crittografia utilizzati da EFS a meno che la compatibilità con FIPS non sia un requisito. Il metodo consigliato per modificare gli algoritmi utilizzati da EFS consiste nell'impostare il valore appropriato in **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\EFS.**
  
-   In **Configurazione computer\\Impostazioni Windows\\Impostazioni protezione\\Criteri chiave pubblica**
  
    -   **Crittografia del file system**. Attiva EFS per i computer all'interno dell'ambito del criterio.
  
    -   **Crittografia del file system**. Aggiungere o rimuovere gli agenti di recupero dati per modificare il criterio di recupero dell'organizzazione. Il processo di gestione degli agenti di recupero dati è descritto in modo dettagliato nel [Capitolo 2: Attività di configurazione e distribuzione](http://technet.microsoft.com/it-it/library/cc162812.aspx) di questa guida.
  
##### Pianificazione della migrazione sugli account di dominio
  
Per i motivi trattati nella guida *Analisi della protezione* di Solution Accelerator, EFS offre una protezione ottimale solo per gli utenti con account di dominio di Active Directory. È possibile utilizzare Syskey per raggiungere livelli di protezione equivalenti, ma l'impatto dei livelli avanzati di Syskey è alquanto negativo. Per questo motivo, è necessario che gli utenti di EFS siano utenti di dominio. Parte del processo di pianificazione di EFS deve includere una ricerca dei potenziali utenti al fine di garantire che questi dispongano di account di dominio e che utilizzino solo tali account quando si collegano a un computer e accedono ai dati riservati protetti da EFS.
  
##### Pianificazione dei criteri di password di Active Directory
  
A meno che le smart card non siano utilizzate con EFS, le chiavi di crittografia file EFS sono protette dalla password dell'utente. Chiunque sia in grado di ottenere un ID utente e una password può accedere con l'identità di quell'utente e decrittografare i file. Tuttavia, per garantire la protezione dei file crittografati da EFS è essenziale che le norme di protezione dell'organizzazione prevedano un criterio per password complesse e un'ottima formazione dell'utente.
  
##### Pianificazione della migrazione da certificati autofirmati a certificati emessi dalla CA
  
È probabile che alcuni utenti abbiano iniziato a utilizzare EFS prima della sua distribuzione formale. Se un utente tenta di crittografare un file su un computer privo di certificati EFS, il sottosistema EFS genererà un nuovo certificato autofirmato. Quando EFS viene distribuito ai computer dell'organizzazione, occorre pianificare la sostituzione di questi certificati autofirmati con certificati emessi da un'autorità di certificazione. Questo processo di sostituzione standardizza la durata e la forza della chiave dei certificati utilizzati per EFS sui computer con certificati autofirmati e su altri computer su cui è stato distribuito EFS.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
-   [Windows Vista Enterprise Hardware Planning Guidance (in inglese)](http://go.microsoft.com/fwlink/?linkid=79962)
  
-   La specifica [USB Mass Storage Class Bulk-Only Transport](http://www.usb.org/developers/devclass_docs/usbmassbulk_10.pdf) sul sito Web Universal Serial Bus
  
-   La pagina [Trusted Platform Module (TPM) Specifications](https://www.trustedcomputinggroup.org/specs/tpm) sul sito Web di Trusted Computing Group
  
-   [Solution Accelerator for Business Desktop Deployment](http://go.microsoft.com/fwlink/?linkid=91187)
  
-   Business Desktop Deployment [Lite Touch Installation Guide](http://go.microsoft.com/fwlink/?linkid=78607) (in inglese)
  
-   [BitLocker Drive Encryption Technical Overview (in inglese)](http://go.microsoft.com/fwlink/?linkid=77977)
  
-   [BitLocker Drive Encryption and Disk Sanitation (in inglese)](http://go.microsoft.com/fwlink/?linkid=80648)
  
-   [Understanding Credential Roaming (in inglese)](http://technet.microsoft.com/en-us/library/cc783542.aspx)
  
-   [Quando si tenta di crittografare un file EFS su un computer basato su Windows XP, Encrypting File System (EFS) genera un certificato autofirmato](http://support.microsoft.com/kb/912761)
  
-   Microsoft [Identity Lifecycle Manager 2007](http://www.microsoft.com/windowsserver/ilm2007) (ILM 2007)
  
-   La sezione "Data Protection and Recovery in Windows XP/[Data Recovery Overview](http://technet.microsoft.com/en-us/library/bb457020.aspx)" della documentazione di Windows XP
  
-   [Guida dettagliata a Crittografia unità BitLocker di Windows](http://go.microsoft.com/fwlink/?linkid=83223)
  
-   [Key Archival and Management in Windows Server 2003 (in inglese)](http://technet.microsoft.com/en-us/library/cc755395.aspx)
  
-   [Descrizione dello strumento Preparazione unità BitLocker](http://support.microsoft.com/kb/930063)
  
-   [Extending Your Active Directory Schema in Windows Server 2003 R2 (in inglese)](http://technet.microsoft.com/en-us/library/cc772804.aspx)
  
**Download**
  
[Download di Data Encryption Toolkit for Mobile PC (in inglese)](http://go.microsoft.com/fwlink/?linkid=81666)
  
**Notifiche di aggiornamento**
  
[Iscriviti per ricevere informazioni su aggiornamenti e nuovi rilasci](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti**
  
[Inviaci i tuoi commenti o suggerimenti](mailto:secwish@microsoft.com?oggetto=data%20encryption%20toolkit%20for%20mobile%20pc,%20guida%20alla%20pianificazione%20e%20all'implementazione%20di%20data%20encryption%20toolkit)
  
[](#mainsection)[Inizio pagina](#mainsection)
