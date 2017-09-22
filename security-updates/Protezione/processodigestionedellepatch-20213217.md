---
TOCTitle: Processo di gestione delle patch
Title: Processo di gestione delle patch
ms:assetid: 'dc3893d5-6e12-443a-9e7d-f2b999b4bff2'
ms:contentKeyID: 20213217
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc700831(v=TechNet.10)'
---

Processo di gestione delle patch
================================

### Fase 2 - Identificazione

Aggiornato: 1 giugno 2007

##### In questa pagina

[](#ekaa)[Argomenti del modulo](#ekaa)
[](#ejaa)[Obiettivi](#ejaa)
[](#eiaa)[Ambito di applicazione](#eiaa)
[](#ehaa)[Utilizzo del modulo](#ehaa)
[](#egaa)[Panoramica](#egaa)
[](#efaa)[Individuazione di un nuovo aggiornamento software](#efaa)
[](#eeaa)[Controllo della pertinenza degli aggiornamenti software](#eeaa)
[](#edaa)[Reperimento e verifica dei file di origine degli aggiornamenti software](#edaa)
[](#ecaa)[Identificazione della natura dell'aggiornamento software e presentazione della RFC](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Passaggio alla fase di stima e pianificazione](#eaaa)

### Argomenti del modulo

Questo modulo descrive la seconda fase, l'identificazione, del processo di gestione degli aggiornamenti in quattro passaggi. La fase di identificazione riguarda l'individuazione affidabile dei nuovi aggiornamenti software, se sono pertinenti per il proprio ambiente di produzione e se un aggiornamento rappresenta una modifica normale o di emergenza.

Lo scopo di questo modulo consiste nella descrizione dei principi della fase di identificazione del processo di gestione degli aggiornamenti e nell'introduzione dei tipi di attività che consentono di eseguire l'identificazione con Microsoft Windows Server Update Service (WSUS) e Microsoft Systems Management Server (SMS).

**Nota:**la versione di valutazione del successivo rilascio di SMS, chiamata System Center Configuration Manager 2007, è ora disponibile per il download all'indirizzo <http://technet.microsoft.com/configmgr/cc761485.aspx> (in inglese). Grazie ai notevoli investimenti in semplificazione, configurazione, distribuzione e protezione, Configuration Manager 2007 rende radicalmente più facile la distribuzione dei sistemi, l'automazione delle attività, la gestione della conformità e la gestione della protezione basata su criteri, aumentando l'agilità dell'azienda.

Dopo aver letto questo modulo si sarà in grado di pianificare le attività necessarie per:

-   Individuare i nuovi aggiornamenti software.

-   Stabilire se nel proprio ambiente sono richiesti nuovi aggiornamenti.

-   Stabilire se un aggiornamento richiede una distribuzione standard o di emergenza.

Senza un processo di identificazione non si saprà quali sono gli aggiornamenti disponibili, quali sono quelli richiesti, come ottenere aggiornamenti controllati, testati ed esenti da virus e se un aggiornamento deve essere distribuito rapidamente o nel quadro della distribuzione pianificata.

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Il modulo consente di:

-   Individuare i nuovi aggiornamenti software.

-   Stabilire se gli aggiornamenti software sono pertinenti.

-   Ottenere file di origine degli aggiornamenti software sicuri e affidabili.

-   Classificare l'aggiornamento software come modifica normale o di emergenza.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Le informazioni contenute in questo modulo sono valide per i seguenti prodotti e tecnologie:

-   Tutti i prodotti e le tecnologie Microsoft

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

In questo modulo viene descritta la fase di identificazione del processo di gestione in quattro fasi degli aggiornamenti. Vengono illustrate le attività di base richieste per portare a termine l'identificazione utilizzando Microsoft Windows Server Update Service (WSUS) e Microsoft Systems Management Server (SMS). Le istruzioni dettagliate sono fornite nelle Technical Library WSUS e SMS elencate di seguito.

Per trarre il massimo vantaggio dal modulo:

-   Leggere l'introduzione del modulo sul processo di gestione degli aggiornamenti. Si avrà così una panoramica di tutte e quattro le fasi del processo di gestione degli aggiornamenti e un'introduzione agli strumenti disponibili per supportare la gestione degli aggiornamenti negli ambienti con sistema operativo Microsoft Windows.

-   Utilizzare le Technical Library WSUS e SMS per altri materiali di riferimento specifici. Queste librerie si trovano all'indirizzo:

    -   [Windows Server Update Services (WSUS) Technical Library (in inglese)](http://technet.microsoft.com/en-us/library/cc706995.aspx)

    -   [Technical Library for Systems Management Server 2003 (in inglese)](http://technet.microsoft.com/en-us/library/cc181833.aspx)

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica

L'identificazione è la seconda fase del processo di gestione degli aggiornamenti illustrato nella Figura 1.

![](images/Cc700831.secmod195figure1(it-it,TechNet.10).gif)

**Figura 1. Il processo di gestione delle patch**

Gli obiettivi della fase di identificazione sono:

-   Individuare in maniera affidabile i nuovi aggiornamenti software.

-   Stabilire se gli aggiornamenti software sono pertinenti per il proprio ambiente di produzione.

-   Ottenere i file di origine degli aggiornamenti software e controllare la loro sicurezza e che vengano installati correttamente.

-   Stabilire se l'aggiornamento software deve essere considerato una modifica normale o un'emergenza e presentare una richiesta di modifica (RFC, Request For Change) per distribuirlo. La presentazione di una RFC fa scattare la fase successiva di gestione degli aggiornamenti, la stima e la pianificazione.

Questi obiettivi vengono descritti più dettagliatamente nella parte restante di questo modulo. Inoltre, viene spiegato come raggiungerli più rapidamente nel caso in cui ci si trovi a dover affrontare un'emergenza.

[](#mainsection)[Inizio pagina](#mainsection)

### Individuazione di un nuovo aggiornamento software

L'identificazione di un aggiornamento software parte da un'individuazione in maniera sicura e affidabile. L'individuazione consta di due componenti principali:

-   In che modo si riceve la notifica di un nuovo aggiornamento software

-   In che modo si può essere certi dell'affidabilità della fonte e della notifica

#### In che modo si riceve la notifica di un nuovo aggiornamento software

L'individuazione di un nuovo aggiornamento software ha inizio con la notifica. La notifica deve essere fornita tramite l'iscrizione a una fonte affidabile che fornisce attività di analisi e di reporting oppure tramite un altro meccanismo altrettanto affidabile. I meccanismi di notifica più comuni sono:

-   Notifiche tramite posta elettronica.

-   Strumenti di analisi delle vulnerabilità.

-   La pagina relativa all'amministrazione server di WSUS.

-   La funzionalità di gestione degli aggiornamenti software di SMS.

##### Notifiche tramite posta elettronica

La notifica tramite posta elettronica è la forma più comune di notifica degli aggiornamenti. Un'opzione per la notifica tramite posta elettronica consiste nell'abbonamento al servizio Microsoft Security Notification Service all'indirizzo <http://www.microsoft.com/technet/security/bulletin/notify.mspx> (in inglese). Per i rilasci temporanei dei prodotti o gli aggiornamenti software, in genere si riceve un messaggio di posta elettronica con cui si viene informati che sul sito Web Microsoft sono disponibili nuovi aggiornamenti software.

Un esempio di messaggio di posta elettronica che notifica agli amministratori la disponibilità dei nuovi aggiornamenti della protezione è riportato nella Figura 2.

[![](images/Cc700831.secmod195figure2(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700831.secmod195figure2_big(it-it,technet.10).gif)

**Figura 2. Esempio di messaggio di posta elettronica che notifica agli amministratori la disponibilità di nuovi aggiornamenti software**

#### In che modo si può essere certi dell'affidabilità della fonte e della notifica

È importante trattare con attenzione le notifiche tramite posta elettronica. Qui di seguito sono riportate alcune indicazioni utili per convalidare ogni notifica ed essere certi che contenga le ultime informazioni disponibili nel bollettino sulla sicurezza:

-   Eliminare immediatamente qualsiasi notifica tramite posta elettronica di asserita provenienza Microsoft che contiene in allegato file software. Non eseguire mai né installare alcun eseguibile allegato a una notifica tramite posta elettronica.

    **Nota:** la politica Microsoft è di non distribuire mai software tramite allegati di posta elettronica. Esaminare Microsoft Policies on Software Distribution all'indirizzo <http://www.microsoft.com/technet/security/bulletin/info/swdist.mspx> (in inglese).

-   Non fare clic su alcun collegamento direttamente all'interno di una notifica tramite posta elettronica. Incollare gli URL in una finestra del browser per controllare che portino direttamente a un sito Web Microsoft.

-   Visitare regolarmente il sito Web Microsoft TechNet Security Center all'indirizzo <http://www.microsoft.com/technet/security/default.mspx> (in inglese) per leggere i dettagli autorevoli di un bollettino sulla sicurezza. In alternativa, se non si prevede di avere l'accesso Internet quando si ricevono i bollettini, prendere conoscenza degli strumenti di crittografia Pretty Good Privacy (PGP) e utilizzarne uno per verificare l'autenticità della firma PGP inclusa in ogni bollettino sulla sicurezza.

-   È possibile scaricare la chiave del bollettino sulla sicurezza di Microsoft Security Response Center (MSRC) da: <http://www.microsoft.com/technet/security/bulletin/pgp.mspx>

-   Microsoft firma digitalmente tutte le notifiche tramite posta elettronica relative agli aggiornamenti della protezione quando le invia ai clienti. Ulteriori informazioni su come verificare la firma digitale sono disponibili all'indirizzo <http://www.microsoft.com/technet/security/bulletin/notify.mspx> (in inglese).

**Nota:** esistono diversi messaggi hoax di posta elettronica che asseriscono di essere notifiche provenienti da Microsoft. Quando si riceve un bollettino sulla sicurezza Microsoft, controllarlo e verificare tutti i collegamenti ipertestuali agli aggiornamenti software visitando il sito Web Security Bulletin Search Tool all'indirizzo <http://www.microsoft.com/technet/security/current.aspx> (in inglese). Per ulteriori informazioni su questi tipi di hoax, vedere "Come verificare l'autenticità di un messaggio Microsoft sulla protezione" all'indirizzo <http://www.microsoft.com/technet/security/bulletin/info/patch_hoax.mspx>

Se si utilizza WSUS, è possibile iscriversi al servizio di avviso degli aggiornamenti, che informa sui nuovi aggiornamenti tramite messaggi di posta elettronica. Per identificare questi aggiornamenti, è necessario forzare una sincronizzazione tra il server WSUS e il server pubblico di Windows Update ogni volta che si riceve il messaggio di notifica dell'aggiornamento. A tal fine, utilizzare l'opzione Synchronize Now nella pagina relativa all'amministrazione server di WSUS. Per informazioni dettagliate sull'utilizzo di WSUS nella fase di identificazione, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese).

Se si utilizza SMS, ogni volta che si riceve una notifica tramite posta elettronica è necessario stabilire se SMS 2003 sarà in grado di rilevare se l'aggiornamento è applicabile ai sistemi nel proprio ambiente di produzione:

-   Se l'aggiornamento interessa un software che non è supportato o rilevabile da Microsoft Baseline Security Analyzer (MBSA), sarà necessario utilizzare gli agenti client per l'inventario dell'hardware e del software di SMS 2003 al fine di stabilire quali sono i computer che richiedono l'aggiornamento software.

-   Se MBSA è in grado di rilevare l'aggiornamento, è possibile utilizzare gli strumenti di gestione degli aggiornamenti software in SMS 2003 per identificare i computer che richiedono l'aggiornamento.

-   Se l'aggiornamento interessa un'applicazione Microsoft Office e si trova nell'elenco degli aggiornamenti forniti da Microsoft Office Inventory Tool for Updates, è possibile utilizzare gli strumenti di gestione degli aggiornamenti software per identificare i computer che richiedono l'aggiornamento.

Per ulteriori informazioni sull'uso di SMS nella fase di identificazione, vedere [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese).

#### Strumenti di analisi delle vulnerabilità

Come menzionato in precedenza in questo modulo, gli amministratori possono utilizzare MBSA con WSUS per analizzare gli aggiornamenti della protezione mancanti e quelli installati nei computer locali e remoti e per stabilire se il computer è esposto alle comuni vulnerabilità a livello di protezione, ad esempio una password amministratore vuota. Per informazioni dettagliate sull'utilizzo di WSUS nella fase di identificazione, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese).

È anche possibile utilizzare componenti della funzionalità di gestione degli aggiornamenti software in SMS 2003 per analizzare e redigere un report sugli aggiornamenti software mancanti e su quelli applicati nell'ambiente. Per ulteriori informazioni su SMS, vedere [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Controllo della pertinenza degli aggiornamenti software

Molti aggiornamenti software vengono regolarmente rilasciati nella comunità IT. Provengono da numerose fonti e sono stati creati per diverse ragioni, tra cui risolvere i problemi che potrebbero portare a violazioni della protezione. Tutti gli aggiornamenti software devono essere controllati attentamente per stabilire se sono pertinenti per l'infrastruttura IT dell'organizzazione. Il processo di controllo delineato in questa sezione dovrebbe aiutare a rimuovere la maggior parte degli aggiornamenti software irrilevanti, ma probabilmente il loro numero può essere ulteriormente ridotto.

Controllare la pertinenza di ogni aggiornamento software ricevuto. Quando una notifica contiene informazioni su più di un aggiornamento software, è necessario controllare la pertinenza di ognuno di essi per la propria organizzazione.

Stabilire innanzitutto se l'aggiornamento software interessa il sistema operativo o le applicazioni dell'ambiente di produzione.

Una volta stabilita la pertinenza per un elemento dell'ambiente di produzione, verificare se l'applicazione o il sistema interessato presenta la vulnerabilità identificata nell'aggiornamento software. Un aggiornamento software potrebbe, ad esempio, riguardare tutti i sistemi operativi Windows Server™ con Microsoft Internet Information Services (IIS) con attivato Active Server Pages (ASP).

Anche se l'ambiente potrebbe contenere diversi sistemi operativi Windows Server, l'aggiornamento non sarà pertinente se l'organizzazione non ha ASP attivato nei server IIS.

Non tutti gli aggiornamenti della protezione che si applicano a un elemento dell'ambiente saranno pertinenti. Anche se è importante essere a conoscenza e capire adeguatamente gli aggiornamenti della protezione esistenti, è opportuno distribuire solo quelli pertinenti per il proprio ambiente. Si ridurrà così l'impegno necessario per mantenere l'ambiente aggiornato e protetto.

Anche se le informazioni contenute in un aggiornamento software potrebbero essere classificate come irrilevanti, è importante tenere presente che esistono e trasmetterle al personale addetto alla gestione dei problemi. Se, in futuro, saranno richieste perché pertinenti, l'organizzazione potrà accedervi dalla fonte originale.

Esistono diversi metodi per stabilire l'applicabilità di un aggiornamento software per l'infrastruttura IT:

-   Leggere i bollettini sulla sicurezza e gli articoli della Microsoft Knowledge Base (KB).

-   Esaminare i singoli aggiornamenti software.

-   Utilizzare la console di amministrazione di SMS.

-   Utilizzare i report incorporati in SMS.

#### Lettura dei bollettini sulla sicurezza e degli articoli della Knowledge Base (KB)

Le informazioni contenute nei bollettini sulla sicurezza nel sito Web Microsoft sono organizzate in sezioni che aiutano a stabilire la criticità, per il proprio ambiente, delle vulnerabilità descritte. Anche se è opportuno leggere tutte le informazioni contenute in un bollettino sulla sicurezza, al primo esame prestare particolare attenzione alle sezioni riportate nella Tabella 1.

**Tabella 1: Bollettini sulla sicurezza - Informazioni chiave**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Sezione</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Riepilogo</p></td>
<td style="border:1px solid black;"><p>Esaminare immediatamente la sezione Riepilogo di un bollettino sulla sicurezza. Le voci Livello di gravità massimo, Effetti della vulnerabilità, Software interessato e Raccomandazione contengono informazioni che aiutano a stabilire il livello di esposizione dell'ambiente alla vulnerabilità.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dettagli della vulnerabilità</p></td>
<td style="border:1px solid black;"><p>La sezione Dettagli della vulnerabilità contiene una descrizione tecnica approfondita delle vulnerabilità. In essa vengono inoltre illustrati i fattori attenuanti e la gravità della vulnerabilità di tutti i prodotti colpiti.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Soluzioni alternative</p></td>
<td style="border:1px solid black;"><p>La sezione Soluzioni alternative include le informazioni su soluzioni testate da Microsoft per contribuire ad attenuare il pericolo fino all'aggiornamento dell'ambiente. Leggere questa sezione come parte della valutazione del rischio.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Domande frequenti</p></td>
<td style="border:1px solid black;"><p>La sezione Domande frequenti contiene le risposte alle domande frequenti specifiche per la vulnerabilità o la correzione. È consigliabile leggere questa sezione dopo aver preso visione della sezione Riepilogo.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Informazioni sull'aggiornamento per la protezione</p></td>
<td style="border:1px solid black;"><p>In questa sezione sono elencate voci quali i prerequisiti, informazioni di installazione specifiche per la piattaforma, informazioni di distribuzione, informazioni sul riavvio, informazioni sulla disinstallazione, informazioni sui file (compresi i nomi, le dimensioni, le versioni, la cartella di destinazione) e i passaggi di verifica dell'installazione degli aggiornamenti.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Articolo della Knowledge Base</p></td>
<td style="border:1px solid black;"><p>Fare riferimento all'articolo della Knowledge Base (KB) identificato nel titolo di un bollettino sulla sicurezza. Ulteriori informazioni sulle vulnerabilità e gli aggiornamenti prescritti dal bollettino sulla sicurezza sono contenute nell'articolo della Knowledge Base. Il numero tra parentesi a destra del titolo di un bollettino sulla sicurezza indica l'articolo della Knowledge Base corrispondente del bollettino. Utilizzarlo per cercare l'articolo nel sito Web del Supporto tecnico Microsoft all'indirizzo <a href="http://www.support.microsoft.com/" class="uri">http://www.support.microsoft.com/</a> (in inglese).</p></td>
</tr>  
</tbody>  
</table>
  
Per ulteriori informazioni sul processo di rilascio dei bollettini sulla sicurezza, vedere il white paper "Revamping the Security Bulletin Release" all'indirizzo <http://www.microsoft.com/technet/security/bulletin/revsbwp.mspx> (in inglese).
  
Le informazioni raccolte nella notifica iniziale e ulteriori informazioni scoperte leggendo il bollettino sulla sicurezza e il relativo articolo della Knowledge Base aiuteranno a stabilire se l'aggiornamento software è pertinente per la propria organizzazione.
  
Le brevi descrizioni contenute nella sezione Riepilogo di un bollettino sulla sicurezza dovrebbero consentire di valutare rapidamente il potenziale impatto che la vulnerabilità potrebbe avere sull'ambiente senza dover esaminare approfonditamente l'intero contenuto di un bollettino.
  
Nella sezione Riepilogo è evidenziato il tipo di problema, viene riportato un elenco del software interessato e viene consigliata l'azione corretta da intraprendere. Dopo aver letto il Riepilogo, si dovrebbe essere in grado di stabilire se è necessario leggere immediatamente e attentamente le sezioni restanti del bollettino sulla sicurezza.
  
I controlli di pertinenza di livello superiore dovrebbero consentire di isolare i computer dell'ambiente che potrebbero essere interessati dalla vulnerabilità.
  
Oltre alle voci descritte nella Tabella 1, Microsoft Security Response Center (MSRC) ha implementato il Maximum Severity Rating System per aiutare gli utenti a stabilire rapidamente l'importanza di un aggiornamento per un'organizzazione. Queste valutazioni si basano sull'impatto potenziale della vulnerabilità e sono mirate a informare l'utente sull'urgenza di qualsiasi azione richiesta.
  
Stabilire la pertinenza di aggiornamenti software che riguardano specificamente la tecnologia può porre serie difficoltà in qualsiasi ambiente. Tecnologie quali Microsoft Data Engine (MSDE) o IIS, che possono essere installate sui client o sui server, possono rendere difficile stabilire se un aggiornamento software è pertinente per un qualsiasi sottogruppo specifico di computer nell'ambiente. Da ciò emerge ancora più chiaramente l'importanza di mantenere un inventario dell'ambiente il più accurato possibile.
  
#### Esame dei singoli aggiornamenti software
  
Ogni aggiornamento software di cui si dà notizia in una notifica richiede un esame approfondito e dettagliato di tutta la documentazione associata, compresa quella inviata con l'aggiornamento software e le informazioni di supporto che potrebbero trovarsi, ad esempio, nel sito Web di Microsoft TechNet.
  
Dopo aver ricevuto un messaggio di posta elettronica in cui si identificano gli aggiornamenti software applicabili, è necessario incaricare qualcuno del loro esame. Questo membro del team deve assumersi la proprietà dell'aggiornamento software. Deve leggere l'articolo della Knowledge Base pertinente e capire cosa viene corretto dall'aggiornamento software.
  
L'aggiornamento software potrebbe essere specifico per scenari o configurazioni particolari. La persona a cui è stato affidato l'esame deve controllare se lo scenario o la configurazione distribuiti nella produzione corrispondono a quelli coperti dall'articolo della Knowledge Base.
  
Esistono poi delle domande da porsi in termini di dipendenze dell'aggiornamento software:
  
-   Esistono dipendenze legate all'aggiornamento? Ad esempio, perché l'aggiornamento sia efficace è necessario attivare o disattivare determinate funzionalità?
  
-   L'aggiornamento software richiede l'installazione di un determinato service pack? L'aggiornamento software è sostituito da un service pack o da un altro aggiornamento software ed è consigliabile attendere una versione più aggiornata?
  
L'identificazione delle dipendenze sopra riportate è molto importante perché avrà un impatto diretto sul rilascio e sulla pianificazione della distribuzione dell'aggiornamento software. Documentare in quale service pack (SP) apparirà l'aggiornamento software e se è richiesta una versione diversa dell'aggiornamento, in base al service pack attivo. È importante avere queste informazioni nel caso in cui, quando gli utenti effettuano l'aggiornamento da un service pack all'altro, insorgano problemi di conformità.
  
È possibile utilizzare i risultati dell'analisi e i report generati dalle funzionalità di gestione degli aggiornamenti software di SMS 2003 per vedere le informazioni specifiche e applicabili riguardanti un aggiornamento software. Se si utilizza WSUS, questa documentazione è accessibile dalla pagina relativa all'amministrazione server di WSUS. Per ulteriori informazioni su WSUS e SMS, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) e [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Reperimento e verifica dei file di origine degli aggiornamenti software
  
Una volta identificato un aggiornamento software e stabilitane la pertinenza, è necessario ottenere i relativi file di origine e controllare che siano sicuri e che vengano installati correttamente. Il processo di verifica autenticherà gli aggiornamenti della protezione o evidenzierà quelli che non sono convalidati. Nel secondo caso, quando si riceve una notifica non valida, è necessario inviare le informazioni sulla notifica ai responsabili del processo di iscrizione e al team per la protezione affinché conducano ulteriori indagini. Se, ad esempio, una notifica proviene da una fonte normalmente affidabile ma nel caso specifico contiene errori di convalida, potrebbero porsi dei problemi di protezione sulla qualità delle notifiche inviate da quella particolare fonte. È opportuno investigare sulla fonte e risolvere i problemi.
  
La verifica dell'aggiornamento software dovrebbe comprendere almeno le seguenti fasi:
  
-   Identificazione e verifica dell'aggiornamento software.
  
-   Esame di tutta la documentazione relativa:
  
    -   Esame dei file dell'aggiornamento software.
  
    -   Identificazione della dimensione dell'aggiornamento software.
  
    -   Identificazione delle dipendenze dell'aggiornamento software:
  
    -   Identificazione delle azioni richieste prima o dopo l'aggiornamento.
  
    -   Verifica dell'esistenza di procedure di installazione dell'aggiornamento software.
  
    -   Verifica dell'esistenza di procedure di disinstallazione dell'aggiornamento software.
  
-   Controllo della sicurezza dell'aggiornamento software.
  
#### Identificazione e verifica dell'aggiornamento software
  
Microsoft notifica agli amministratori i nuovi aggiornamenti software tramite messaggi di posta elettronica, ma non include mai, né allega, file software ai messaggi. Qui di seguito sono riportate le pratiche Microsoft principali relative alla notifica e alla verifica che l'aggiornamento software sia di proprietà di Microsoft:
  
-   Microsoft invia ogni tanto ai propri clienti un messaggio di posta elettronica con cui li informa sulla disponibilità di aggiornamenti, anche software. Il messaggio contiene tuttavia collegamenti solo ai siti di download. Il software non viene mai allegato. I collegamenti portano sempre al sito Web Microsoft o al sito Microsoft File Transfer Protocol (FTP), mai a un sito di terze parti. Alcuni messaggi di posta elettronica dannosi potrebbero contenere collegamenti Internet che conducono a un indirizzo diverso da quello riportato in un messaggio di posta elettronica in formato HTML. È importante accertarsi che vi sia una persona responsabile del controllo dell'URL (Universal Resource Locator) del sito Web visitato.
  
-   Oltre ai collegamenti forniti in una notifica tramite posta elettronica, Microsoft rende disponibili gli aggiornamenti software su Internet. È possibile accedere ai file da [http://www.microsoft.com](http://www.microsoft.com/italy) (in inglese), tramite il sito FTP all'indirizzo [ftp://ftp.microsoft.com](ftp://ftp.microsoft.com/) oppure tramite il sito Web Microsoft Update all'indirizzo [http://windowsupdate.microsoft.com](http://windowsupdate.microsoft.com/) (in inglese).
  
-   I file dell'aggiornamento software possono essere forniti anche su supporti fisici quali CD-ROM e dischi floppy.
  
-   Microsoft utilizza sempre la tecnologia Authenticode per firmare digitalmente i propri prodotti e permettere agli amministratori di controllare che i file non siano stati alterati, come indicato nella Figura 3.
  
[![](images/Cc700831.secmod195figure3(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc700831.secmod195figure3_big(it-it,technet.10).gif)
  
**Figura 3. Firma digitale Authenticode**
  
Ulteriori informazioni sulle politiche Microsoft relative alla distribuzione software sono disponibili all'indirizzo <http://www.microsoft.com/technet/security/bulletin/info/swdist.mspx> (in inglese).
  
#### Esame di tutta la documentazione relativa
  
Prima di applicare un qualsiasi aggiornamento software, è opportuno leggere e fare esaminare a più persone tutta la documentazione pertinente. La revisione di pari è di importanza cruciale in quanto riduce il rischio che a una persona che valuta l'aggiornamento sfuggano punti pertinenti e missing-critical. Man mano che si legge la documentazione, cercare le risposte alle seguenti domande:
  
-   L'adozione dell'aggiornamento causerà altri problemi che comprometteranno il sistema di produzione?
  
-   È necessario mettere in atto determinate azioni prima della distribuzione dell'aggiornamento?
  
-   È necessario mettere in atto determinate azioni dopo la distribuzione dell'aggiornamento?
  
-   Mentre si procede all'aggiornamento dell'ambiente, sono disponibili soluzioni alternative o procedure di attenuazione?
  
-   Sono disponibili procedure di installazione dell'aggiornamento software?
  
-   Sono disponibili procedure di disinstallazione dell'aggiornamento software?
  
-   Qual è la dimensione del file dell'aggiornamento software? La dimensione del file avrà un impatto sul processo complessivo di rilascio e sulla pianificazione, ad esempio sulla modalità con cui si gestiscono gli utenti mobili.
  
Nel bollettino sulla sicurezza, sotto le sezioni descritte in precedenza nella Tabella 1, è possibile reperire informazioni utili per trovare le risposte a queste domande.
  
#### Controllo della sicurezza dell'aggiornamento software
  
Per evitare che virus o codice dannoso colpiscano l'infrastruttura IT, è opportuno esaminare i file relativi a un aggiornamento software in un ambiente isolato (messo in quarantena). La quarantena deve essere imposta a tutto il software e a tutta la documentazione. È opportuno che l'ambiente in quarantena venga sottoposto a controlli rigorosi e che il processo sia a cura di un gruppo di esperti in seno all'organizzazione.
  
Raramente gli aggiornamenti software richiedono solo modifiche al file di configurazione o del Registro di sistema o delle impostazioni dell'applicazione. La maggior parte degli aggiornamenti software richiede il download dei file. Mettere sempre in quarantena i file scaricati isolandoli dalla rete di produzione mentre li si esamina per individuare la presenza di virus e controllarne l'autenticità digitale.
  
Se si utilizza WSUS, ogni aggiornamento viene firmato; un hash viene impiegato e inviato insieme ai metadati (metadati che descrivono a cosa risulta utile l'aggiornamento). Quando viene scaricato un aggiornamento, WSUS controlla la firma digitale e l'hash. Se l'aggiornamento è stato alterato, non viene installato. Per informazioni dettagliate sull'utilizzo di WSUS nella fase di identificazione, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese).
  
**Nota:** l'Area download Microsoft, Microsoft Update e SMS 2003 con funzionalità di gestione degli aggiornamenti software forniscono solo aggiornamenti software originali Microsoft. Se si riceve un aggiornamento software Microsoft tramite altri canali, controllarne la validità e la firma digitale.
  
#### Verifica dell'esistenza di procedure di installazione dell'aggiornamento software
  
Qui di seguito sono riportate alcune linee guida per controllare le procedure di installazione degli aggiornamenti software:
  
-   Seguire le istruzioni indicate negli articoli della Knowledge Base e nel bollettino sulla sicurezza che accompagnano un aggiornamento software per verificare che l'installazione sia corretta.
  
-   Stabilire se l'aggiornamento software richiede un riavvio. In caso affermativo, sarà necessario valutare diverse considerazioni durante la fase di pianificazione e di distribuzione per i server mission-critical, i server dell'infrastruttura di base e i server con applicazioni line-of-business (LOB). Per ulteriori informazioni su queste tematiche, leggere il modulo "[Fase 3 del processo di gestione degli aggiornamenti - Stima e pianificazione](http://technet.microsoft.com/it-it/library/cc700840.aspx)".
  
-   Valutare qual è lo spazio su disco richiesto dall'aggiornamento software (inclusa una cartella di disinstallazione).
  
-   Controllare se l'aggiornamento fornisce opzioni di configurazione che sono disponibili durante l'installazione.
  
-   Leggere la documentazione di supporto sull'installazione di un aggiornamento software.
  
Malgrado i test, dopo l'installazione del software potrebbero emergere problemi che richiedono la sua disinstallazione. È perciò importante testare la correttezza della procedura di disinstallazione. Dopo la disinstallazione, controllare che il server continui a funzionare come previsto e continuare a controllare i contatori del Registro eventi e del Monitor di sistema.
  
Alcuni aggiornamenti rilasciati da Microsoft forniscono una modalità di disinstallazione, altri no. Stabilire quali aggiornamenti software possono essere disinstallati esaminando i dettagli tecnici forniti nel bollettino sulla sicurezza nella sezione Ulteriori informazioni sulla patch.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Identificazione della natura dell'aggiornamento software e presentazione della RFC
  
Dopo aver identificato l'aggiornamento software, stabilito la sua pertinenza per l'organizzazione, ottenuto i file di origine dell'aggiornamento software e controllato che siano sicuri e vengano installati correttamente, presentare una richiesta di modifica (RFC, Request For Change) per iniziare la fase di valutazione e pianificazione dell'aggiornamento software.
  
L'RFC deve contenere le seguenti informazioni:
  
-   Qual è la modifica?
  
-   A quale vulnerabilità risponde la modifica?
  
-   Su quali servizi si ripercuoterà la modifica?
  
-   È già distribuito un aggiornamento software per quel servizio?
  
-   L'aggiornamento software richiede un riavvio per completare l'installazione?
  
-   L'aggiornamento software può essere disinstallato?
  
-   Quali contromisure esistono, eventualmente, per disporre di più tempo per testare e distribuire l'aggiornamento software?
  
-   Quali sono le strategie di test consigliate per questa modifica?
  
-   Qual è la priorità suggerita dell'RFC?
  
-   Qual è l'impatto (categoria) della modifica?
  
Se un aggiornamento software risolve un problema di protezione critico o un'instabilità del sistema, la priorità dell'RFC deve essere "emergenza". Una RFC di emergenza deve essere creata solo quando la distribuzione di un aggiornamento software o l'implementazione di contromisure di protezione quali la chiusura delle porte di rete deve essere effettuata d'urgenza.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Qui di seguito sono riportati i punti chiave da ricordare in merito alla fase di identificazione:
  
-   Controllare di ricevere notifiche su tutti i nuovi aggiornamenti software.
  
-   Controllare che la notifica di un aggiornamento software provenga da una fonte autorizzata.
  
-   Controllare che l'aggiornamento software sia pertinente per i sistemi nell'ambiente di produzione.
  
-   Ottenere i file di origine dell'aggiornamento software e controllare che non presentino virus.
  
-   Controllare che l'installazione dell'aggiornamento software sia corretta.
  
-   Stabilire se l'aggiornamento software è un'emergenza e presentare una RFC per distribuirlo nella produzione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Passaggio alla fase di stima e pianificazione
  
Sono stati completati i requisiti della fase di identificazione e si è pronti per passare alla fase di stima e pianificazione quando:
  
-   È stato accertato che l'aggiornamento software è pertinente e che può essere distribuito in sicurezza.
  
-   È stata presentata una richiesta di modifica (RFC, Request For Change), che attiva la fase di stima e pianificazione.
  
Per ulteriori informazioni sulla fase di stima e pianificazione, leggere il modulo "[Fase 3 del processo di gestione degli aggiornamenti - Stima e pianificazione](http://technet.microsoft.com/it-it/library/cc700840.aspx)".
  
[](#mainsection)[Inizio pagina](#mainsection)
