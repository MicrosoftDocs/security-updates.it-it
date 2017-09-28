---
TOCTitle: 'Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi - Capitolo 4'
Title: 'Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi - Capitolo 4'
ms:assetid: 'e6e16691-2280-49fb-95fa-b6ce7da96da1'
ms:contentKeyID: 20200866
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536267(v=TechNet.10)'
---

Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi
==============================================================================================

### Capitolo 4: Progettazione della soluzione

Aggiornato: 23 maggio 2005

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Elementi della soluzione](#eeaa)
[](#edaa)[Rilevazione delle violazioni dei criteri](#edaa)
[](#ecaa)[Individuazione degli attacchi esterni](#ecaa)
[](#ebaa)[Implementazione dell'analisi legale](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

Il passaggio finale nella pianificazione di un sistema di monitoraggio della protezione e di rilevazione degli attacchi consiste nella creazione di una struttura in grado di soddisfare i requisiti della soluzione. Questa struttura deve riuscire a risolvere le problematiche dei seguenti tre scenari:

-   Rilevazione delle violazioni dei criteri

-   Individuazione degli attacchi esterni

-   Implementazione dell'analisi legale

Poiché lo scopo principale della soluzione è di individuare gli attacchi e tracciarne un profilo, la maggior parte di questo capitolo sarà incentrata sulla discussione degli eventi che possono indicare un attacco in corso. Questi profili di attacco sono correlati ai problemi di protezione tipici di ciascuno scenario che sono stati illustrati nel Capitolo 3 "Problemi e requisiti". L'effettiva implementazione della soluzione dipenderà dalla topologia di rete dell'organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Elementi della soluzione

Nella struttura della soluzione vengono utilizzati gli stessi componenti di base per tutti e tre gli scenari. Sebbene l'implementazione dell'analisi legale richieda alcune risorse aggiuntive per l'archiviazione in linea e non in linea, l'architettura della soluzione di questo scenario non presenta particolari differenze rispetto all'implementazione degli altri due scenari.

#### Concetto della soluzione

Un sistema di monitoraggio della protezione e di rilevazione degli attacchi è basato sull'analisi e sulla pianificazione dei livelli appropriati di controlli di protezione per le seguenti aree:

-   Azioni di gestione degli account, ad esempio creazione di utenti e aggiunta di utenti a gruppi

-   Accesso a file protetti

-   Modifiche dei criteri di protezione

-   Creazione ed eliminazione di trust

-   Utilizzo di diritti utente

-   Riavvio del sistema e modifica dell'ora di sistema

-   Modifiche alle impostazioni del Registro di sistema

-   Esecuzione di programmi sconosciuti

Il sistema di monitoraggio della protezione e di rilevazione degli attacchi raccoglie le informazioni dai registri eventi protezione e le archivia in un database centralizzato. L'amministratore può quindi analizzare tali informazioni allo scopo di individuare eventuali attività sospette. In alternativa, le informazioni possono essere archiviate per essere successivamente utilizzate durante l'analisi legale.

Uno dei vantaggi principali di questa soluzione consiste nella possibilità di configurare il livello di controllo in base allo specifico utente. Grazie a questa funzionalità di Microsoft® Windows Server™ 2003 con Service Pack 1 (SP1) e di Microsoft Windows® XP con Service Pack 2 (SP2), è possibile specificare livelli di controllo differenti per determinati account utente, in modo da assegnare un livello più alto alle persone sospette o agli account sensibili.

#### Prerequisiti della soluzione

Di seguito sono riportati i prerequisiti della soluzione per la configurazione di un sistema di monitoraggio della protezione e di rilevazione degli attacchi:

-   I server devono eseguire Windows Server 2003 SP1 o versione successiva e devono appartenere a un dominio del servizio directory Active Directory®.

-   I computer client devono eseguire Windows XP Service Pack 2 o versione successiva e devono appartenere a un dominio Active Directory.

**Nota:** poiché i computer all'interno di una rete perimetrale possono essere membri di un gruppo di lavoro anziché di un dominio, per la configurazione di questi computer non possono essere utilizzate le impostazioni Criteri di gruppo Active Directory. In alternativa, è possibile comunque utilizzare i criteri locali e i file di modello.

Lo scopo di questa guida non è di consigliare una particolare tecnologia per la raccolta centralizzata degli eventi di protezione ma di consentire l'individuazione delle firme tipiche di un attacco. Una volta stabilito un meccanismo di raccolta appropriato, sarà possibile utilizzare gli eventi e le sequenze di eventi descritti in questo capitolo per creare query in grado di individuare gli attacchi.

#### Pianificazione della soluzione

Prima di implementare un sistema di monitoraggio della protezione e di rilevazione degli attacchi, è necessario effettuare le seguenti operazioni:

-   Analisi delle impostazioni correnti dei controlli di protezione

-   Determinazione dei ruoli degli amministratori e delle attività degli utenti

-   Analisi dei criteri e delle procedure dell'organizzazione

-   Individuazione dei computer vulnerabili

-   Indicazione delle risorse critiche

-   Individuazione degli account sensibili o sospetti

-   Indicazione dei programmi autorizzati

Per ulteriori informazioni sui requisiti di archiviazione, vedere la sezione "Implementazione dell'analisi legale" più avanti in questo capitolo.

##### Analisi delle impostazioni correnti dei controlli di protezione

Per determinare i valori di base per le modifiche indicate in questo capitolo, è necessario esaminare le impostazioni correnti relative ai controlli di protezione e ai file registro eventi protezione. Di seguito sono indicati i dati da verificare:

-   Impostazioni correnti relative ai controlli di protezione

-   Livello a cui vengono applicate queste impostazioni (computer locale, sito, dominio o unità organizzativa)

-   Impostazioni correnti dei file di registro (dimensione, comportamento in caso di raggiungimento della dimensione massima)

-   Ulteriori impostazioni dei controlli di protezione applicabili, ad esempio per il controllo dell'utilizzo dei privilegi di backup e ripristino

Per facilitare l'individuazione delle impostazioni da registrare, è possibile fare riferimento all'Appendice B "Implementazione delle impostazioni Criteri di gruppo". Per ulteriori informazioni sulle impostazioni dei controlli di protezione, vedere [Windows Server 2003 Security Guide](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db) all'indirizzo http://www.microsoft.com/downloads/details.aspx?FamilyId=8A2643C1-0685-4D89-B655-521EA6C7B4DB (informazioni in lingua inglese).

##### Determinazione dei ruoli degli amministratori e delle attività degli utenti

Per poter implementare un sistema efficace di monitoraggio della protezione è fondamentale conoscere gli amministratori nonché i ruoli e le responsabilità che essi ricoprono. Ad esempio, la maggior parte delle organizzazioni include gli amministratori nel gruppo Domain Admins. Gli amministratori di dominio hanno la possibilità di creare nuovi account utente nel dominio. È possibile, tuttavia, che nei criteri dell'organizzazione sia specificato che la creazione dei nuovi account può essere eseguita soltanto dal sistema di provisioning. In questo caso, l'eventuale creazione di un account utente da parte di un amministratore dovrebbe attrarre immediatamente l'attenzione.

La valutazione delle attività degli utenti è più semplice, poiché le autorizzazioni per l'accesso alle risorse di rete degli utenti sono molto più limitate rispetto a quelle degli amministratori. Ad esempio, gli utenti in genere non hanno accesso ai file system dei computer nella rete perimetrale. Di conseguenza, non è necessario monitorare questi server per tenere traccia delle attività degli utenti.

##### Analisi dei criteri e delle procedure dell'organizzazione

L'analisi delle procedure dell'organizzazione corrisponde alla valutazione dei ruoli e delle responsabilità degli amministratori. Ad esempio, l'aggiunta degli utenti ai gruppi è un'operazione che richiede la massima attenzione. È opportuno che i reparti stabiliscano apposite procedure per le richieste di modifica e definiscano i metodi per l'implementazione di tali richieste. L'aggiunta di un utente a un gruppo al di fuori del processo approvato richiede un'attenta analisi.

##### Individuazione dei computer vulnerabili

Per computer vulnerabili si intendono i computer nella rete di un'organizzazione che molto probabilmente verranno attaccati per primi da un utente malintenzionato esterno. Nella maggior parte degli scenari di attacco, questi computer fanno parte della rete perimetrale.

È necessario eseguire un'analisi completa e dettagliata di tutti i computer vulnerabili per assicurarsi che siano state completate le seguenti operazioni:

-   Applicazione di tutti i Service Pack e aggiornamenti della protezione

-   Disattivazione dei servizi e degli account utente superflui

-   Se possibile, configurazione dei servizi da eseguire con gli account del servizio locale o del servizio di rete

-   Verifica dei servizi in esecuzione con credenziali di account utente, in particolare quelli con diritti amministrativi, per assicurarsi che questi servizi richiedano effettivamente account utente

-   Applicazione dei modelli dei criteri computer ad alta protezione

**Nota: **questo processo di analisi non riguarda esclusivamente i computer vulnerabili. Si consiglia di applicare questi controlli a tutti i computer nella rete.

Per ulteriori informazioni sull'esecuzione protetta dei servizi, vedere [Guida alla pianificazione della protezione dei servizi e degli account dei servizi](http://go.microsoft.com/fwlink/?linkid=41311) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=41311.

##### Individuazione delle risorse critiche

Anche se l'individuazione delle risorse critiche dell'organizzazione è stata probabilmente già eseguita, in alcuni casi può essere necessario formalizzare queste informazioni in un criterio dell'organizzazione, fornendo una descrizione di queste risorse e indicando il livello di protezione adeguato per ciascuna di esse. Si supponga, ad esempio, che in un'organizzazione vengano utilizzati gli elenchi di controllo di accesso (ACL) e la crittografia per archiviare i record finanziari in modo protetto su partizioni basate su file system NTFS. In questo caso, è necessario definire un criterio dell'organizzazione che individui questi record come file protetti non accessibili agli utenti o agli amministratori non autorizzati. È necessario, inoltre, che gli utenti e gli amministratori siano a conoscenza di questa restrizione.

A questo punto, è necessario analizzare qualsiasi modifica all'elenco ACL relativa a questi file protetti, in particolare le modifiche a livello di proprietà, poiché possono indicare che un utente malintenzionato ha tentato di accedere a un file senza disporre dell'autorizzazione appropriata. Poiché le modifiche di questo tipo sono abbastanza rare, non dovrebbe essere difficile rilevarle.

##### Individuazione degli account sensibili o sospetti

Per individuare gli account che richiedono un livello di controllo più alto è necessario prendere in esame tutti gli account sensibili, tra cui l'account Administrator predefinito, i membri dei gruppi Enterprise, Schema e Domain Admins nonché gli account utilizzati dai servizi per l'accesso al sistema.

Quando si nota un'attività sospetta da parte di un utente, è necessario che i criteri di protezione richiedano un livello di controllo più alto per tale persona. Per ulteriori informazioni sulla modifica dei livelli di controllo per gli account utente, vedere la sezione "Attivazione del controllo selettivo" più avanti in questo capitolo.

##### Indicazione dei programmi autorizzati

Per poter individuare informazioni sulla rete, gli utenti malintenzionati hanno l'esigenza di eseguire programmi. Di conseguenza, la definizione di restrizioni sui programmi che possono essere eseguiti sulla rete consente di ridurre in modo significativo il rischio di attacchi esterni. È necessario eseguire un controllo di tutti i programmi autorizzati e considerare sospetti tutti i programmi sconosciuti. Microsoft Systems Management Server 2003 consente di eseguire controlli sul software in ambienti aziendali di grandi dimensioni.

**Nota: **è possibile che sia necessario escludere dal controllo alcuni computer, ad esempio le workstation dell'ambiente di sviluppo, poiché i file eseguibili creati dagli sviluppatori non sono presenti nell'elenco dei programmi approvati. Per una maggiore protezione, è preferibile che i computer utilizzati per lo sviluppo e il test dei programmi non siano collegati alle rete aziendale.

#### Architettura della soluzione

Nella soluzione per il monitoraggio della protezione e la rilevazione degli attacchi, la gestione degli avvisi di protezione viene eseguita da diversi componenti, tra cui:

-   Controller di dominio Active Directory

-   Infrastruttura di correlazione degli eventi

-   Workstation di monitoraggio e analisi

-   Database per l'archiviazione in linea

-   Supporti di backup

-   Sistema interno di archiviazione a breve termine

-   Sistema esterno di archiviazione a lungo termine

Poiché i controller di dominio Active Directory non sono indispensabili, è possibile configurare i livelli di controllo della protezione utilizzando le impostazioni di protezione locale. Se tuttavia si desidera utilizzare Criteri di gruppo per l'implementazione dei controlli di protezione, è necessario utilizzare Active Directory.

#### Funzionamento della soluzione

Di seguito è riportata la procedura seguita dai componenti dell'architettura della soluzione:

1.  L'amministratore utilizza le impostazioni Criteri di gruppo per applicare le modifiche necessarie ai livelli di controllo. Per l'elenco delle impostazioni Criteri di gruppo consigliate, vedere l'Appendice B "Implementazione delle impostazioni Criteri di gruppo".

2.  Le modifiche vengono propagate ai computer designati.

3.  L'amministratore applica le modifiche ai criteri di protezione locale dei computer che non appartengono al dominio, ad esempio quelli nella rete perimetrale.

4.  Gli eventi vengono raccolti nei registri eventi protezione, in base alle impostazioni definite in Criteri di gruppo.

5.  Il sistema di correlazione degli eventi esamina periodicamente i registri eventi protezione e salva le informazioni in un database appropriato.

6.  Un responsabile della protezione può analizzare le informazioni nel database direttamente o mediante programmi quali SysTrack 3 di Lakeside Software per individuare eventuali attività sospette.

L'implementazione del monitoraggio della protezione per l'analisi legale richiede le seguenti azioni aggiuntive:

1.  Il sistema di correlazione degli eventi estrae periodicamente gli eventi rilevanti e li inserisce nel database in linea.

2.  Il sistema di backup nel database in linea esegue a intervalli predefiniti (in genere giornalmente) l'archiviazione dei dati e la conseguente rimozione dei record obsoleti dal database in linea.

3.  I supporti di backup rimangono nel sistema interno di archiviazione a breve termine per il periodo di tempo specificato.

4.  A intervalli regolari, in genere ogni settimana, i supporti di backup meno recenti vengono trasferiti nel sistema esterno di archiviazione a lungo termine.

5.  L'amministratore responsabile delle operazioni di ripristino esegue mensilmente alcune prove di ripristino per verificare l'integrità delle copie di backup.

#### Attivazione del controllo selettivo

In Windows Server 2003 con Service Pack 1 sono disponibili nuove funzionalità che consentono di impostare livelli di controllo selettivi sugli account utente. Ad esempio, è possibile controllare l'accesso e la disconnessione dal sistema degli utenti nonché tutte le attività di un determinato utente. In alternativa, è possibile controllare tutte le attività degli utenti ad eccezione di uno specifico account utente. Mediante i livelli di controllo selettivi è possibile ridurre il numero degli eventi di routine da filtrare oppure tenere traccia delle persone sospette. Il controllo selettivo può essere applicato soltanto agli account utente e non ai gruppi di protezione o di distribuzione.

Per implementare i livelli di controllo selettivi è possibile utilizzare l'utilità da riga di comando **auditusr.exe**, disponibile sia in Windows Server 2003 con SP1 che in Windows XP con SP2. Per ulteriori informazioni sulla configurazione dei controlli selettivi, eseguire **auditusr.exe /?** al prompt dei comandi.

**Nota: **l'utilizzo dei controlli selettivi non consente di escludere gli eventi relativi ai membri del gruppo Administrators predefinito.

[](#mainsection)[Inizio pagina](#mainsection)

### Rilevazione delle violazioni dei criteri

Nel Capitolo 3 "Problemi e requisiti" è stato dimostrato che le minacce più gravi per una rete provengono dagli utenti interni all'organizzazione. Persino le organizzazioni con procedure di selezione del personale estremamente rigorose non possono permettersi di rinunciare al costante monitoraggio degli utenti interni più fidati. In questo capitolo verranno illustrati alcuni degli scenari di rischio interno più comuni e verrà spiegato come rilevare queste minacce.

In alcuni casi, gli amministratori possono causare involontariamente errori di configurazione della rete o del sistema. Si consideri, ad esempio, un amministratore che ha seguito un processo di approvazione prima dell'implementazione di una modifica di configurazione e che quindi ha utilizzato le credenziali di amministratore corrette per accedere a una workstation visibile ad altri utenti. In questo esempio, l'amministratore non ha tentato di nascondere le proprie azioni. L'eventuale tentativo da parte di un amministratore di nascondere o meno le proprie attività consente di distinguere un tentativo volontario di sabotaggio da un errore accidentale di configurazione.

**Nota: **l'implementazione di un sistema di monitoraggio della protezione risulta molto più efficace se è già stato creato e implementato un processo consolidato di gestione delle modifiche. In caso contrario, sarà molto più difficile verificare che siano state utilizzate le procedure corrette per apportare le modifiche, poiché non è disponibile alcun sistema in base al quale effettuare un confronto.

La creazione di un profilo di attacco per le violazioni dei criteri si basa sull'individuazione di un evento o una sequenza di eventi che può indicare un attacco potenziale. Queste informazioni possono essere utilizzate con il sistema di correlazione degli eventi allo scopo di individuare le firme di attacco.

Di seguito sono riportate le attività associate alla rilevazione delle violazioni dei criteri:

-   Accesso alle risorse mediante la modifica delle autorizzazioni file

-   Accesso alle risorse mediante la reimpostazione delle password

-   Creazione, modifica o eliminazione degli account utente

-   Inserimento degli utenti nei gruppi

-   Utilizzo di account non autorizzati

-   Accesso in modalità interattiva con credenziali degli account dei servizi

-   Esecuzione di programmi non autorizzati

-   Accesso a risorse non autorizzate

-   Danneggiamento di file autorizzati (escluso il danneggiamento causato da errori del disco)

-   Introduzione di sistemi operativi non autorizzati

-   Acquisizione delle credenziali di altri utenti

-   Tentativo di elusione dei controlli

-   Creazione o eliminazione di relazioni di trust

-   Modifiche non autorizzate ai criteri di protezione

#### Accesso alle risorse mediante la modifica delle autorizzazioni file

Gli amministratori hanno la possibilità di visualizzare file per i quali non dispongono delle autorizzazioni di lettura semplicemente modificando i diritti di proprietà del file e quindi aggiungendo se stessi al relativo elenco delle autorizzazioni di lettura. In Windows Server 2003 e versioni successive, per mascherare questa azione è sufficiente ripristinare successivamente lo stato originale dei diritti di proprietà e delle autorizzazioni.

La soluzione di configurare il controllo dell'accesso agli oggetti su tutti i file non è ovviamente praticabile, in quanto l'enorme quantità di eventi generati renderebbe impossibile individuare un'eventuale attività illecita. È tuttavia necessario impostare livelli di controllo della protezione in modo da controllare tutti gli accessi o le modifiche apportate ai file più importanti e alle relative cartelle. L'utilizzo delle semplici voci ACL, infatti, non offre una protezione sufficiente contro l'accesso non autorizzato.

Per contrastare in modo efficace le attività illegali, è necessario ottenere le seguenti informazioni per tutti i file più importanti:

-   Oggetto a cui si è tentato di accedere

-   Utente che ha richiesto l'accesso

-   Eventuale autorizzazione dell'utente per l'accesso all'oggetto

-   Tipo di accesso (lettura, scrittura, visualizzazione e così via) effettuato dall'utente

-   Risultato del controllo dell'evento (operazione riuscita o non riuscita)

-   Computer da cui è stato tentato l'accesso

Poiché in Visualizzatore eventi non sono disponibili impostazioni filtro sufficienti per l'individuazione di queste informazioni, per eseguire questa analisi è necessario utilizzare Event Comb MT o un altro programma di terze parti.

Nella seguente tabella sono elencati gli eventi di controllo che possono indicare una modifica delle autorizzazioni file. La categoria di controllo è Accesso agli oggetti.

**Tabella 4.1. Eventi di modifica delle autorizzazioni file**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">560</td>
<td style="border:1px solid black;">Accesso consentito a un oggetto esistente</td>
<td style="border:1px solid black;">Questo evento indica se un oggetto ha consentito l'accesso a una richiesta, ad esempio di visualizzazione, lettura, creazione o eliminazione. Controllare i campi <strong>ID di accesso primario</strong>, <strong>Nome utente client</strong> e <strong>Nome utente primario</strong> per rilevare eventuali tentativi non autorizzati di modifica delle autorizzazioni file. Controllare il campo <strong>Accessi</strong> per determinare il tipo di operazione. Questo evento indica soltanto che l'accesso è stato richiesto o concesso ma non implica che si sia effettivamente verificato. L'utente che esegue l'azione è l'<strong>utente client</strong>, se presente, altrimenti l'<strong>utente primario</strong>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">567</td>
<td style="border:1px solid black;">Utilizzo di un'autorizzazione associata a un handle</td>
<td style="border:1px solid black;">Questo evento si verifica alla prima istanza di un tipo di accesso (visualizzazione, lettura, creazione e così via) a un oggetto. Per stabilire una correlazione con l'evento 560, confrontare i campi <strong>ID handle</strong> dei due eventi.</td>
</tr>
</tbody>
</table>
  
#### Accesso alle risorse mediante la reimpostazione delle password
  
Le operazioni di reimpostazione delle password devono essere eseguite soltanto nell'ambito di uno schema approvato. Un livello di controllo della protezione correttamente configurato deve prevedere la registrazione delle operazioni di reimpostazione delle password nei registri eventi protezione e l'individuazione delle reimpostazioni che non rispettano le procedure stabilite.
  
Nella seguente tabella sono elencati gli eventi di controllo che possono indicare la reimpostazione della password. La categoria di controllo è Gestione account.
  
**Tabella 4.2. Eventi di reimpostazione delle password**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">627</td>
<td style="border:1px solid black;">Tentativo di cambiamento della password</td>
<td style="border:1px solid black;">Questo evento viene generato da una richiesta di cambiamento della password in cui l'utente fornisce la password originale dell'account. Confrontare i campi <strong>Nome utente primario</strong> e <strong>Nome account di destinazione</strong> per determinare se il tentativo di cambiamento della password è stato eseguito dal proprietario dell'account o da un altro utente. Se il valore in <strong>Nome utente primario</strong> non corrisponde a quello in <strong>Nome account di destinazione</strong>, significa che un utente diverso dal proprietario dell'account ha tentato di cambiare la password. Sui computer che eseguono Microsoft Windows Me o Windows NT®, la richiesta di modifica è in genere associata all'account <em>Anonimo</em>. Questo problema si verifica perché l'utente potrebbe non essere stato autenticato. Ciò non implica, tuttavia, un rischio di protezione particolarmente grave, poiché il richiedente ha dovuto fornire la password precedente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">628</td>
<td style="border:1px solid black;">Impostazione o reimpostazione della password dell'account utente</td>
<td style="border:1px solid black;">Questo evento si verifica quando un utente o un processo reimposta la password di un account mediante un'interfaccia amministrativa quale Utenti e computer di Active Directory anziché mediante una procedura di cambiamento della password. Questa operazione può essere eseguita soltanto da persone o processi autorizzati, ad esempio dal personale del supporto tecnico o dall'utente proprietario della password.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">698</td>
<td style="border:1px solid black;">Cambiamento della password per la modalità di Ripristino servizi directory</td>
<td style="border:1px solid black;">Questo evento si verifica quando un utente tenta di cambiare la password per la modalità di Ripristino servizi directory in un controller di dominio. Controllare i campi <strong>Indirizzo IP workstation</strong> e <strong>Nome account</strong> ed eseguire immediatamente le azioni appropriate.</td>
</tr>
</tbody>
</table>
  
#### Creazione, modifica o eliminazione degli account utente
  
È consigliabile definire un processo consolidato per la creazione di un nuovo account utente. Nelle organizzazioni di grandi dimensioni che prevedono un sistema di provisioning automatico, questo processo può includere processi di regole business, costituiti da più passaggi, in cui gli amministratori devono accedere a un sito Web per approvare la creazione degli account per i nuovi assunti. Anche nelle organizzazioni di piccole dimensioni, la creazione di un account utente in Active Directory dovrebbe essere eseguita soltanto a seguito di una richiesta ufficiale. A ciascun evento che registra la creazione di un account utente deve quindi corrispondere una richiesta di creazione account. Un amministratore disonesto può creare facilmente un account utente falso per un dipendente inesistente e quindi utilizzare tale account per accedere in maniera non autorizzata ed eseguire attività dannose.
  
È necessario inoltre verificare che intercorra solo un breve intervallo di tempo tra la creazione di un nuovo account utente e il momento in cui l'utente esegue l'accesso al sistema per cambiare la password. Se l'accesso al sistema con il nuovo account non si verifica entro un periodo di tempo prestabilito, è necessario disattivare l'account e cercare di determinare la causa del ritardo.
  
Se si desidera utilizzare un sistema di monitoraggio della protezione e di rilevazione degli attacchi per individuare eventuali problemi relativi agli account utente, è necessario configurare query in grado di effettuare le seguenti operazioni:
  
-   Ricerca di attività insolite o irregolari sugli account di rete
  
-   Individuazione degli amministratori che abusano dei privilegi per creare o modificare degli account
  
-   Rilevazione di schemi di attività sugli account che violano i criteri di protezione dell'organizzazione
  
Nella seguente tabella sono elencati gli eventi che possono indicare la modifica di un account utente. Tutti gli eventi appartengono alla categoria di controllo Gestione account.
  
**Tabella 4.3. Eventi di modifica dell'account utente**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">624</td>
<td style="border:1px solid black;">Creazione di un account utente</td>
<td style="border:1px solid black;">Soltanto le persone e i processi autorizzati devono creare account di rete. Esaminare il campo <strong>Nome utente primario</strong> per determinare se l'operazione è stata eseguita da una persona o un processo autorizzato. Questo evento consente inoltre di rilevare se gli amministratori creano account senza rispettare le linee guida dei criteri dell'organizzazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">630</td>
<td style="border:1px solid black;">Eliminazione di un account utente</td>
<td style="border:1px solid black;">Soltanto le persone e i processi autorizzati devono eliminare account di rete. Effettuare una ricerca per individuare questi eventi, quindi esaminare il campo <strong>Nome utente primario</strong> per determinare se l'operazione è stata eseguita da persone non autorizzate.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">642</td>
<td style="border:1px solid black;">Modifica di un account utente</td>
<td style="border:1px solid black;">Questo evento si verifica in caso di modifiche alle proprietà di protezione degli account utente che non sono coperte dagli eventi 627-630.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">685</td>
<td style="border:1px solid black;">Modifica di un nome account</td>
<td style="border:1px solid black;">Assicurarsi che il campo <strong>Nome utente primario</strong> corrisponda a una persona o un processo autorizzato.</td>
</tr>
</tbody>
</table>
  
#### Inserimento degli utenti nei gruppi
  
Una buona strategia di protezione deve basarsi sul principio del privilegio minimo, che prevede l'assegnazione agli utenti del numero minimo di diritti e autorizzazioni necessario per lo svolgimento del proprio lavoro. La maggior parte degli account utente deve appartenere soltanto al gruppo Domain Users, insieme agli eventuali gruppi di protezione specifici dell'organizzazione.
  
Per l'inserimento degli utenti nei gruppi di protezione, in particolare quelli che dispongono di privilegi elevati quali Domain, Schema o Enterprise Admins, è necessario rispettare le linee guida dei criteri dell'organizzazione nonché utilizzare processi o account definiti e approvati. Qualsiasi variazione deve essere considerata sospetta e richiede quindi la massima attenzione.
  
**Nota**: l'appartenenza ai gruppi di distribuzione non fornisce l'accesso alle risorse di rete, poiché questi gruppi non rappresentano identità di protezione. In alcuni casi, tuttavia, l'appartenenza a questi gruppi può generare altri tipi di problemi di protezione. Se ad esempio alcuni account utente vengono inseriti per errore nel gruppo di distribuzione dei vicepresidenti o dei responsabili, è possibile che tali utenti ricevano messaggi di posta elettronica non appropriati per la loro qualifica.
  
Nella seguente tabella sono elencati gli eventi che possono indicare una modifica dell'appartenenza a un gruppo. Tutti gli eventi appartengono alla categoria di controllo Gestione account.
  
**Tabella 4.4. Eventi di modifica dell'appartenenza ai gruppi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Da 631 a 634</td>
<td style="border:1px solid black;">Modifiche a un gruppo globale protetto</td>
<td style="border:1px solid black;">È necessario esaminare i gruppi che dispongono di privilegi di accesso esteso o globale, ad esempio Domain Admins, per verificare che non vi siano modifiche che esulano dai criteri dell'organizzazione. Il nome del gruppo è riportato nel campo <strong>Nome account di destinazione</strong>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Da 635 a 638</td>
<td style="border:1px solid black;">Modifiche a un gruppo locale protetto</td>
<td style="border:1px solid black;">È necessario esaminare i gruppi Administrators, Server Operators e Backup Operators per verificare che non vi siano modifiche che esulano dai criteri dell'organizzazione. Il nome del gruppo è riportato nel campo <strong>Nome account di destinazione</strong>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">639
641
668</td>
<td style="border:1px solid black;">Modifiche a un gruppo protetto</td>
<td style="border:1px solid black;">Questi eventi indicano che sono state apportate altre modifiche a un gruppo, oltre all'eliminazione, la creazione o la modifica dell'appartenenza. È necessario esaminare i gruppi che dispongono di privilegi elevati per verificare che siano stati rispettati tutti i requisiti dei criteri dell'organizzazione. Il nome del gruppo è riportato nel campo <strong>Nome account di destinazione</strong>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Da 659 a 662</td>
<td style="border:1px solid black;">Modifiche a un gruppo universale protetto</td>
<td style="border:1px solid black;">È necessario esaminare i gruppi che dispongono di privilegi elevati, ad esempio Enterprise Admins o Schema Admins, per verificare che non vi siano modifiche che esulano dai criteri dell'organizzazione. Il nome del gruppo è riportato nel campo <strong>Nome account di destinazione</strong>.</td>
</tr>
</tbody>
</table>
  
#### Utilizzo di account non autorizzati
  
L'innalzamento di livello del primo controller di dominio Active Directory in un insieme di strutture crea un account amministratore appartenente ai gruppi Domain Admins e Enterprise Admins. Questo account richiede un'attenzione particolare poiché è l'unico a cui non vengono applicate le impostazioni relative al numero di blocchi dell'account. Di conseguenza, anche se è attivo un criterio di blocco dell'account, questo account è vulnerabile agli attacchi con dizionario.
  
Il monitoraggio della protezione deve individuare qualsiasi tentativo di accesso mediante questo account amministratore, anche se è stato rinominato. Per ulteriori informazioni sull'innalzamento del livello di protezione sugli account amministrativi, vedere [The Administrator Accounts Security Planning Guide](http://go.microsoft.com/fwlink/?linkid=41307) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=41315 (informazioni in lingua inglese).
  
I tentativi di accesso mediante account disattivati o scaduti possono indicare che un ex dipendente, un collaboratore temporaneo o un consulente ha tentato di accedere alla rete senza disporre dell'autorizzazione. Questi eventi richiedono una verifica immediata.
  
Nella seguente tabella sono elencati gli eventi che possono indicare l'utilizzo di un account non autorizzato. Gli eventi appartengono alle categorie di controllo Accesso account e Accesso.
  
**Tabella 4.5. Eventi di accesso non autorizzato**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">528/540</td>
<td style="border:1px solid black;">Accesso riuscito</td>
<td style="border:1px solid black;">Questo evento è sospetto nel caso in cui il valore del campo <strong>Nome account di destinazione</strong> corrisponde all'account amministratore predefinito. L'evento 528, tuttavia, è un evento comune durante il normale utilizzo del sistema.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">529</td>
<td style="border:1px solid black;">Accesso non riuscito: nome utente sconosciuto o password non valida</td>
<td style="border:1px solid black;">Controllare eventuali tentativi in cui il valore del campo <strong>Nome account di destinazione</strong> corrisponde ad Administrator o all'account amministratore predefinito rinominato. Controllare i tentativi multipli di accesso non riusciti che sono inferiori al limite di blocchi dell'account.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">531</td>
<td style="border:1px solid black;">Accesso non riuscito: account disattivato</td>
<td style="border:1px solid black;">Occorre sempre ricercare la causa di questo evento. Controllare il valore di <strong>Nome account di destinazione</strong> e <strong>Nome workstation</strong>. Questo evento può indicare un tentativo di abuso da parte di ex dipendenti interni.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">532</td>
<td style="border:1px solid black;">Accesso non riuscito: account scaduto</td>
<td style="border:1px solid black;">Occorre sempre ricercare la causa di questo evento. Controllare il valore di <strong>Nome account di destinazione</strong> e <strong>Nome workstation</strong>. Questo evento può indicare un abuso da parte di consulenti o dipendenti interni temporanei.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">576</td>
<td style="border:1px solid black;">Privilegi speciali assegnati al nuovo accesso</td>
<td style="border:1px solid black;">Questo evento viene visualizzato ogni volta che una nuova sessione di accesso ottiene privilegi che possono consentire l'accesso di tipo amministratore o la falsificazione dell'itinerario di controllo. Mettere in relazione con l'evento 528 o 540 confrontando il campo <strong>ID di accesso</strong> nei due eventi. L'evento 576 consente di determinare rapidamente se un account ha ottenuto, al momento dell'accesso, privilegi equivalenti a quelli di un amministratore. Questo approccio risulta più semplice rispetto al calcolo dell'appartenenza al gruppo.</td>
</tr>
</tbody>
</table>
  
#### Accesso in modalità interattiva con credenziali degli account dei servizi
  
Quando viene avviato, un servizio deve fornire le credenziali di accesso. In alcuni casi, gli account dei servizi possono richiedere un account di dominio per la connessione e l'esecuzione dei servizi sui computer remoti. Alcuni account dei servizi richiedono l'esecuzione con credenziali di amministratore o l'interazione con il desktop.
  
In Windows Server 2003 e versioni successive è possibile avviare alcuni account dei servizi, ad esempio il servizio Avvisi, con l'opzione **–LocalService**. I servizi che richiedono la connettività di rete possono utilizzare l'account del servizio di rete, ovvero NT AUTHORITY\\NetworkService. È necessario controllare tutti i servizi che richiedono account utente per assicurarsi che questi account utilizzino password complesse. Il sistema di monitoraggio della protezione deve verificare che gli eventi di accesso per tali account si verifichino solo quando viene avviato il relativo servizio. Per ulteriori informazioni sull'innalzamento della protezione sugli account dei servizi, vedere [Guida alla pianificazione della protezione dei servizi e degli account dei servizi](http://go.microsoft.com/fwlink/?linkid=41311) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=41311.
  
La situazione più preoccupante a livello di protezione si verifica quando un account dei servizi accede al sistema in modalità interattiva anziché come servizio. Questo evento può verificarsi solo se un intruso ha individuato la password dell'account dei servizi e accede al sistema utilizzando tale account. Se questo account dispone dei privilegi di amministratore, l'intruso avrà la possibilità di danneggiare i normali servizi di rete.
  
È necessario individuare tutte le risorse a cui può accedere un account dei servizi. Può accadere, ad esempio, che un account dei servizi debba disporre, in alcuni momenti, delle autorizzazioni di scrittura su una directory del file di registro. Questi account non devono disporre di autorizzazioni ingiustificate per l'accesso ai dati importanti. Si consiglia di esaminare con la massima attenzione gli account dei servizi che possono interagire con il desktop, poiché questi account offrono le maggiori opportunità di attacco agli utenti malintenzionati.
  
Nella seguente tabella sono elencati gli eventi che possono indicare l'utilizzo non autorizzato di credenziali degli account dei servizi. Gli eventi appartengono alle categorie di controllo Accesso account e Accesso.
  
**Tabella 4.6. Eventi di accesso con credenziali degli account dei servizi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">528</td>
<td style="border:1px solid black;">Accesso riuscito: attacco console o Servizi terminal</td>
<td style="border:1px solid black;">Se in un registro eventi viene registrato l'evento 528 per un account dei servizi o per un sistema locale con <strong>tipo di accesso 2</strong>, significa che è in corso un attacco, che l'utente malintenzionato ha ottenuto la password dell'account dei servizi e che è riuscito ad accedere alla console. Se invece è stato registrato un <strong>tipo di accesso 10</strong>, significa che un utente malintenzionato ha utilizzato Servizi terminal per accedere al sistema. In entrambi i casi, è necessario eseguire immediatamente un'analisi approfondita.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">534</td>
<td style="border:1px solid black;">Accesso non riuscito: tipo di accesso non consentito</td>
<td style="border:1px solid black;">Controllare i campi <strong>Nome account di destinazione</strong> e <strong>Nome workstation</strong> e il <strong>tipo di accesso</strong>. Questo evento indica un tentativo non riuscito di accesso al sistema in modalità interattiva con credenziali dell'account dei servizi mentre le impostazioni Criteri di gruppo impediscono questo tipo di accesso a tale account.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">600</td>
<td style="border:1px solid black;">Assegnazione di un token primario a un processo</td>
<td style="border:1px solid black;">Questo evento si verifica quando un servizio utilizza un determinato account per accedere a un computer in cui è in esecuzione Windows XP o versione successiva. Mettere in correlazione questo evento con gli eventi 672, 673, 528 e 592.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">601</td>
<td style="border:1px solid black;">Tentativo di installazione di un servizio da parte di un utente</td>
<td style="border:1px solid black;">Questo evento è estremamente raro poiché l'installazione dei servizi non è un'operazione molto frequente. È necessario esaminare con attenzione tutti i tentativi, sia riusciti che non riusciti, relativi a questo evento.</td>
</tr>
</tbody>
</table>
  
#### Esecuzione di programmi non autorizzati
  
Essendo persone fidate, gli amministratori sono autorizzati a installare ed eseguire programmi. È opportuno che le organizzazioni prevedano la creazione di un elenco di programmi approvati (e con licenza) e di un processo per l'approvazione dei nuovi programmi. Gli amministratori dovrebbero eseguire, oltre ai test su nuovi programmi all'interno di segmenti di rete isolati, soltanto programmi inclusi nell'elenco dei programmi approvati.
  
Per individuare i programmi non autorizzati è possibile definire controlli di protezione sul tracciato processo. Quest'ultimo, tuttavia, comporta la generazione di più voci nei registri di protezione. È quindi necessario assicurarsi che il numero degli eventi non crei problemi nel meccanismo di rilevazione.
  
Nella seguente tabella sono elencati gli eventi che possono indicare l'utilizzo di programmi non autorizzati. Gli eventi appartengono alla categoria di controllo Tracciato processo.
  
**Tabella 4.7. Eventi di esecuzione di programmi non autorizzati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">592</td>
<td style="border:1px solid black;">Creazione di un nuovo processo</td>
<td style="border:1px solid black;">Controllare i campi <strong>Nome file immagine</strong> e <strong>Nome utente</strong> per i nuovi processi. Tutti i processi devono essere inclusi nell'elenco dei programmi autorizzati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">602</td>
<td style="border:1px solid black;">Creazione di un processo pianificato</td>
<td style="border:1px solid black;">Controllare il campo <strong>Nome destinazione</strong> per verificare l'autorizzazione a eseguire processi pianificati e il campo <strong>Task Time</strong> per determinare la correlazione dell'evento con le eventuali attività pianificate.</td>
</tr>
</tbody>
</table>
  
#### Accesso a risorse non autorizzate
  
Questa situazione richiede l'individuazione dei controlli non riusciti sull'ID evento 560. Nella seguente tabella sono elencati gli eventi che possono indicare l'accesso a risorse non autorizzate. La categoria di controllo è Accesso agli oggetti.
  
**Tabella 4.8. Eventi di tentativi di accesso a risorse non autorizzate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">560</td>
<td style="border:1px solid black;">Accesso respinto a un oggetto esistente</td>
<td style="border:1px solid black;">Monitorare gli accessi non riusciti. Esaminare il campo <strong>Nome oggetto</strong> per determinare la risorsa a cui si è tentato di accedere. Mettere in relazione con i campi <strong>Nome utente primario</strong> e <strong>Dominio primario</strong> o con i campi <strong>Nome utente client</strong> e <strong>Dominio client</strong>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">568</td>
<td style="border:1px solid black;">Tentativo di creazione di un collegamento fisso a un file controllato</td>
<td style="border:1px solid black;">Questo evento si verifica quando un utente o un programma tenta di creare un collegamento fisso a un file o un oggetto. Una volta creato un collegamento fisso, un utente può modificare un file con i propri diritti utente senza che venga creato un itinerario di controllo.</td>
</tr>
</tbody>
</table>
  
#### Danneggiamento di file autorizzati
  
In questo caso, un utente danneggia volontariamente file a cui è autorizzato ad accedere, senza preoccuparsi delle eventuali conseguenze. Questo tipo di comportamento si verifica in genere quando l'amministratore di un'organizzazione non ha ancora disattivato l'account di un utente licenziato.
  
Per ridurre al minimo le opportunità per questo tipo di sabotaggio è necessario definire strategie di annullamento efficaci e ben documentate che prevedono la disattivazione automatica dell'account e la disconnessione forzata dell'utente.
  
#### Introduzione di sistemi operativi non autorizzati
  
Per introdurre in una rete sistemi operativi non autorizzati, amministratori e utenti potrebbero utilizzare i seguenti meccanismi:
  
-   Computer di casa connessi alla rete
  
-   Sistemi operativi avviabili da CD
  
-   Reinstallazione di Windows XP o di un altro sistema operativo Windows
  
-   Immagini Microsoft Virtual PC
  
L'introduzione di sistemi operativi non autorizzati può causare gravi problemi, ad esempio:
  
-   Riduzione della protezione dalle vulnerabilità a causa della mancata applicazione degli aggiornamenti della protezione
  
-   Duplicazione degli indirizzi IP, in cui il sistema operativo non autorizzato possiede lo stesso indirizzo di un altro computer sulla rete
  
-   Maggiore vulnerabilità ai virus e ad altre applicazioni software dannose
  
-   Maggiore probabilità di danneggiamento dei file
  
-   Numero maggiore di chiamate al personale di supporto tecnico
  
-   Riduzione della produttività
  
Nei criteri di protezione dell'organizzazione è possibile specificare se gli utenti che lavorano da postazioni remote possono collegarsi alla rete aziendale tramite servizi di accesso remoto o reti private virtuali. Per ulteriori informazioni sulla verifica della conformità dei computer remoti ai criteri di protezione dell'organizzazione prima della connessione alla rete, vedere [Implementing Quarantine Services with Microsoft Virtual Private Network Planning Guide](http://go.microsoft.com/fwlink/?linkid=41307) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=41307 (informazioni in lingua inglese).
  
**Nota: **alcune distribuzioni di software open source sono disponibili su CD di avvio. Per avviare uno di questi sistemi operativi, l'utente deve inserire il CD e riavviare il computer. È possibile che il sistema di monitoraggio dei registri eventi non sia in grado di rilevare questa occorrenza, poiché il software open source viene eseguito all'esterno di Windows. Tuttavia, i tentativi di accesso con utente ROOT in un ambiente omogeneo possono indicare la presenza di sistemi operativi non autorizzati. La rimozione delle unità CD dai computer client consente di risolvere questo problema, anche se si tratta di una soluzione non sempre praticabile.
  
Gli utenti potrebbero anche ottenere un CD di installazione di Windows XP e riavviare il computer per reinstallare Windows XP. In questo caso, è possibile che il sistema di monitoraggio dei registri eventi di altri computer rilevi un tentativo di accesso con utente Administrator a cui è associato un nome di gruppo di lavoro sconosciuto o il nome predefinito Gruppo di lavoro.
  
Le immagini Virtual PC consentono di ottenere un'emulazione completa dell'ambiente di un computer host, nella quale è in esecuzione lo stesso sistema operativo del computer host, con i relativi nome del computer, account, programmi e appartenenze al gruppo di lavoro o al dominio. L'immagine Virtual PC può avviare, eseguire e chiudere programmi senza che ciò abbia alcun impatto sul computer host, nonché richiedere un indirizzo IP e accedere alle risorse della rete aziendale. Le immagini Virtual PC rappresentano una minaccia per la protezione del sistema, poiché spesso sono protette con password vuote o facilmente individuabili. Un utente che esegue un'immagine Virtual PC non protetta può effettuare il mapping delle unità alle condivisioni di rete oppure installare componenti, ad esempio Microsoft Internet Information Services (IIS), che contengono vulnerabilità interne che sono state corrette da Service Pack o aggiornamenti della protezione rilasciati successivamente.
  
Il sistema di monitoraggio della protezione consente di rilevare i seguenti problemi:
  
-   Nomi utente, computer, gruppo di lavoro o dominio sconosciuti
  
-   Indirizzi IP duplicati o esterni all'intervallo consentito
  
-   Tentativi di accesso mediante l'account Administrator predefinito
  
Nella seguente tabella sono elencati gli eventi che possono indicare l'utilizzo di sistemi operativi non autorizzati. Gli eventi appartengono alla categoria di controllo Tracciato processo.
  
**Tabella 4.9. Eventi di esecuzione di sistemi operativi non autorizzati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">529</td>
<td style="border:1px solid black;">Accesso non riuscito: nome utente sconosciuto o password non valida</td>
<td style="border:1px solid black;">Controllare i tentativi in cui il campo <strong>Nome account di destinazione</strong> è impostato su Administrator e il valore di <strong>Nome dominio</strong> è sconosciuto oppure il campo <strong>Nome account di destinazione</strong> è impostato su ROOT.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">592</td>
<td style="border:1px solid black;">Creazione di un nuovo processo</td>
<td style="border:1px solid black;">Controllare i campi <strong>Nome file immagine</strong> e <strong>Nome utente</strong> per i nuovi processi. Tutti i processi devono essere programmi autorizzati.<strong> </strong></td>
</tr>
</tbody>
</table>
  
**Nota: **per una rilevazione più affidabile dei rootkit, è possibile utilizzare prodotti di terze parti quali RootkitRevealer di Sysinternals o Blacklight di F-Secure. Per ulteriori informazioni su RootkitRevealer, vedere [RootKitRevealer](http://www.sysinternals.com/utilities/rootkitrevealer.html) all'indirizzo http://www.sysinternals.com/Utilities/RootkitRevealer.html (informazioni in lingua inglese). Per ulteriori informazioni su Blacklight, vedere il comunicato stampa [Revolutionary F-Secure BlackLight Technology](http://www.f-secure.com/news/items/news_2005030701.shtml) all'indirizzo http://www.f-secure.com/news/items/news\_2005030701.shtml (informazioni in lingua inglese).
  
#### Acquisizione delle credenziali di altri utenti
  
Uno degli effetti indesiderati in un corretto sistema di gestione delle password, in cui viene imposto ad esempio il requisito della lunghezza minima e di cambiamento regolare della password, è che gli utenti sono costretti ad annotare le proprie password. Questa situazione è particolarmente evidente negli ambienti eterogenei in cui sono previsti più database di archiviazione delle identità che richiedono agli utenti di eseguire più volte la procedura di accesso.
  
**Nota:** per ulteriori informazioni sulla gestione delle password in ambienti eterogenei, vedere [Identity and Access Management Series](http://www.microsoft.com/technet/security/topics/identity/idmanage/default.mspx) all'indirizzo http://www.microsoft.com/technet/security/topics/identity/idmanage/default.mspx (informazioni in lingua inglese).
  
Una grave minaccia per le organizzazioni è rappresentata dagli utenti che scrivono le proprie password su un foglio di carta che lasciano quindi sulla scrivania. In questo caso, infatti, una persona non autorizzata potrebbe entrare nell'ufficio e scoprire facilmente le credenziali di accesso dell'utente. Il sistema di monitoraggio della protezione dovrebbe rilevare quando un determinato utente tenta di accedere a un computer in genere non utilizzato dall'utente. Per poter rilevare questo tipo di attacco è necessario mettere in relazione gli accessi riusciti con i nomi delle workstation e l'accesso utente o l'autorizzazione per tali workstation.
  
**Nota:** Active Directory consente di controllare le workstation a cui un utente può accedere. Questa funzionalità richiede il supporto del sistema di denominazione NetBIOS (Network Basic Input/Output System), ad esempio tramite Windows Internet Naming Service (WINS).
  
Gli eventi relativi a queste occorrenze sono identici a quelli riportati nella Tabella 4.5 "Eventi di accesso non autorizzato".
  
#### Tentativo di elusione dei controlli
  
Un utente malintenzionato può utilizzare diversi metodi per evitare di essere scoperto. Ad esempio, può modificare i criteri di protezione di un computer o di un dominio in modo che nei registri di eventi non vengano riportate le attività sospette oppure può eliminare volontariamente i registri di protezione per causare la perdita dei dati di controllo. Poiché molti di questi eventi si verificano regolarmente durante la normale esecuzione delle operazioni di rete, l'individuazione dei tentativi di nascondere le tracce può essere estremamente difficile.
  
Nella seguente tabella sono elencati gli eventi in genere causati da utenti malintenzionati che stanno tentando di nascondere le prove delle violazioni della protezione. Gli eventi appartengono a più categorie di controllo.
  
**Tabella 4.10. Eventi di elusione dei controlli**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">512</td>
<td style="border:1px solid black;">Avvio di Windows in corso</td>
<td style="border:1px solid black;">Questo evento viene in genere visualizzato dopo l'evento 513. È necessario esaminare eventuali riavvii imprevisti del sistema.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">513</td>
<td style="border:1px solid black;">Chiusura di Windows in corso</td>
<td style="border:1px solid black;">Questo evento viene in genere visualizzato prima dell'evento 512. Sui computer critici, è necessario che il riavvio dei computer venga eseguito da personale autorizzato in base a criteri prestabiliti. Se si verifica in un server, questo evento richiede un'analisi immediata e approfondita.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">516</td>
<td style="border:1px solid black;">Controllo non riuscito</td>
<td style="border:1px solid black;">Questo evento può verificarsi quando il buffer del registro eventi contiene un numero eccessivo di eventi di protezione. In questo caso, occorre ridurre il numero degli eventi da controllare. Questo evento può inoltre verificarsi se il registro di protezione è configurato in modo da non poter essere sovrascritto. Occorre monitorare attentamente i computer che si trovano in aree in cui è necessario mantenere un numero elevato di controlli nei registri di protezione. In caso di riempimento dei registri, è possibile che le impostazioni di protezione richiedano la chiusura di alcuni computer. Monitorare l'evento 516 su tutti i computer in cui sono previsti requisiti di protezione particolarmente elevati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">517</td>
<td style="border:1px solid black;">Cancellazione dei registri eventi protezione</td>
<td style="border:1px solid black;">Gli amministratori non devono cancellare i registri eventi protezione senza autorizzazione. Controllare i campi <strong>Nome utente client</strong> e <strong>Dominio client</strong>, quindi analizzare le informazioni con personale autorizzato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">520</td>
<td style="border:1px solid black;">Modifica dell'ora di sistema</td>
<td style="border:1px solid black;">Questa azione può ingannare l'analisi legale o fornire un falso pretesto a un utente malintenzionato. Il nome del processo è <strong>%windir %\system32\svchost.exe</strong>. Controllare i campi <strong>Nome utente client</strong> e <strong>Dominio client</strong>, quindi analizzare le informazioni con personale autorizzato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">521</td>
<td style="border:1px solid black;">Impossibile registrare eventi</td>
<td style="border:1px solid black;">Windows non è in grado di scrivere eventi nel registro eventi protezione. Se si verifica in un computer critico, questo evento richiede un'analisi immediata e approfondita.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">608</td>
<td style="border:1px solid black;">Assegnazione di un privilegio a un account utente</td>
<td style="border:1px solid black;">Questa azione concede un nuovo privilegio a un account utente. Nel registro eventi viene registrata questa azione insieme all'identificatore di protezione (SID) dell'account utente ma non il nome dell'account utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">609</td>
<td style="border:1px solid black;">Rimozione di un privilegio da un account utente</td>
<td style="border:1px solid black;">Questa azione rimuove un privilegio da un account utente. Nel registro eventi viene registrata questa azione insieme all'identificatore di protezione (SID) dell'account utente ma non il nome dell'account utente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">612</td>
<td style="border:1px solid black;">Modifica di un criterio di controllo</td>
<td style="border:1px solid black;">Questo evento non indica necessariamente un problema. È possibile, tuttavia, che la modifica del criterio di controllo sia stata eseguita da un utente malintenzionato durante un attacco al computer. Questo evento deve essere monitorato con attenzione sui computer critici e sui controller di dominio.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">621</td>
<td style="border:1px solid black;">Concessione dell'accesso al sistema a un account</td>
<td style="border:1px solid black;">A un utente è stato concesso l'accesso a un sistema. Controllare i campi <strong>Nome utente</strong> e <strong>Account modificato</strong>, in particolare se l'autorizzazione di accesso è interattiva.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">622</td>
<td style="border:1px solid black;">Rimozione dell'accesso al sistema da un account</td>
<td style="border:1px solid black;">Questo evento può indicare che un utente malintenzionato ha eliminato la prova dell'evento 621 o che sta tentando di negare il servizio ad altri account.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">643</td>
<td style="border:1px solid black;">Modifica del criterio di protezione del dominio</td>
<td style="border:1px solid black;">Questo evento indica un tentativo di modifica del criterio password o di altre impostazioni relative ai criteri di protezione del dominio. Controllare il nome utente interessato e metterlo in relazione con l'autorizzazione.</td>
</tr>
</tbody>
</table>
  
#### Creazione o revoca di relazioni di trust
  
Le relazioni di trust consentono agli account utente in un dominio di accedere alle risorse di rete in un altro dominio. Le relazioni di trust transitive bidirezionali automatiche possono estendersi a tutti i domini all'interno dello stesso insieme di strutture Active Directory. Esistono situazioni in cui può essere necessario creare manualmente relazioni di trust, ad esempio:
  
-   Trust che includono domini Windows NT 4.0.
  
-   Trust di collegamento tra domini.
  
-   Trust tra domini appartenenti a insiemi di strutture differenti in Windows 2000 Server.
  
-   Trust tra insiemi di strutture in Windows Server 2003.
  
La creazione delle relazioni di trust non è un'operazione standard e deve essere eseguita soltanto da un amministratore dell'organizzazione mediante un processo ben definito, approvato e consolidato. Questo approccio riguarda anche la revoca delle relazioni di trust, che deve essere eseguita soltanto da un amministratore dell'organizzazione dopo un'attenta analisi degli effetti sulla rete.
  
Nella seguente tabella sono elencati gli eventi che indicano azioni sulle relazioni di trust. Gli eventi appartengono alla categoria di controllo Modifica criterio.
  
**Tabella 4.11. Eventi di modifica delle relazioni di trust**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">610
611
620</td>
<td style="border:1px solid black;">Creazione, eliminazione o modifica di una relazione di trust con un altro dominio</td>
<td style="border:1px solid black;">Questi eventi si verificano sul controller di dominio in cui è stato creato l'oggetto dominio trusted. Questo evento deve generare un avviso e richiede una verifica immediata. Controllare il campo <strong>Nome utente</strong> della persona che ha eseguito l'operazione di trust.</td>
</tr>
</tbody>
</table>
  
#### Modifiche non autorizzate ai criteri di protezione
  
Le modifiche alle configurazioni di protezione approvate devono essere apportate soltanto attraverso un insieme di procedure verificate. Qualsiasi tentativo di apportare modifiche al di fuori di tali procedure deve essere considerato un errore involontario dell'amministratore o un tentativo intenzionale di sabotaggio.
  
Di seguito sono elencate le impostazioni relative alle configurazioni di protezione che richiedono per la modifica l'utilizzo di procedure ben definite:
  
-   Impostazioni Criteri di gruppo
  
    -   Criteri password degli account utente
  
    -   Criteri di blocco degli account utente
  
    -   Criteri di controllo
  
    -   Impostazioni dei registri eventi che devono essere applicate al registro eventi protezione
  
    -   Criteri IPSec
  
    -   Criteri relativi alle reti senza fili (IEEE 802.11)
  
    -   Criteri chiave pubblica, in particolare quelli che devono essere applicati a Crittografia file system (EFS)
  
    -   Criteri di restrizione software
  
-   Impostazioni di protezione
  
    -   Assegnazione diritti utente
  
    -   Criteri password degli account utente
  
    -   Opzioni di protezione
  
In questo elenco sono indicati i requisiti minimi. Nella maggior parte delle organizzazioni è probabile che dovranno essere aggiunte altre impostazioni Criteri di gruppo. È necessario configurare controlli di protezione allo scopo di individuare qualsiasi tentativo, sia riuscito che non riuscito, di modifica di queste impostazioni. Inoltre, tutti i tentativi riusciti devono essere messi in relazione con un account utente che disponga delle autorizzazioni appropriate.
  
Nella seguente tabella sono elencati gli eventi che possono indicare una modifica dei criteri (sia Criteri di gruppo che criteri di sistema locali). Gli eventi appartengono alla categoria di controllo Modifica criterio.
  
**Tabella 4.12. Eventi di modifica dei criteri**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">612</td>
<td style="border:1px solid black;">Modifica di un criterio di controllo</td>
<td style="border:1px solid black;">Questo evento individua una qualsiasi modifica a un criterio di controllo. Mettere in relazione questo evento con le modifiche apportate ai criteri di sistemi dal personale autorizzato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">613
614
615</td>
<td style="border:1px solid black;">Modifica di un criterio IPSec</td>
<td style="border:1px solid black;">Monitorare questi eventi ed esaminare con attenzione eventuali occorrenze che si sono verificate al di fuori delle operazioni di avvio del sistema.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">618</td>
<td style="border:1px solid black;">Criterio di recupero dati crittografati</td>
<td style="border:1px solid black;">Se si utilizza un criterio di recupero dati crittografati, monitorare questo evento ed esaminare con attenzione eventuali occorrenze che si sono verificate al di fuori del criterio specificato.</td>
</tr>
</tbody>
</table>
  
Per ulteriori informazioni sulle impostazioni Criteri di gruppo, vedere [Security Policy Settings](http://www.microsoft.com/resources/documentation/windowsserv/2003/all/techref/en-us/w2k3tr_sepol_set.asp) all'indirizzo http://www.microsoft.com/resources/Documentation/windowsserv/2003/all/techref/en-us/W2K3TR\_sepol\_set.asp (informazioni in lingua inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Individuazione degli attacchi esterni
  
Gli attacchi esterni sono causati dalle azioni di una persona o dagli effetti di programmi dannosi. Questi attacchi possono sovrapporsi. Ad esempio, un trojan horse può ottenere l'accesso a un computer desktop che una persona può quindi sfruttare direttamente.
  
Gli utenti malintenzionati esterni tentano spesso di violare la protezione mediante l'elevazione dei privilegi finché non ottengono l'accesso amministrativo a uno o più computer. Questo approccio in genere inizia con un'intrusione mediante un account utente che dispone di privilegi limitati. A questo punto, l'utente malintenzionato tenta di aumentare i privilegi mediante la creazione di un processo o un servizio che viene eseguito nel contesto del sistema. Viene quindi caricato ed eseguito un programma software allo scopo di esplorare ulteriormente la rete, ad esempio utilizzando strumenti che consentono di intercettare le password o di eseguire la scansione dei pacchetti di rete.
  
Un utente malintenzionato può inoltre tentare di installare in un server un rootkit, ovvero un componente software che assume il controllo completo di un computer nascondendo la propria presenza agli strumenti di diagnostica standard. Poiché operano a un livello hardware molto basso, i rootkit sono in grado di intercettare e modificare le chiamate di sistema. L'individuazione dei rootkit non può essere effettuata mediante la ricerca del relativo eseguibile, poiché il rootkit rimuove se stesso dall'elenco dei risultati restituiti dalla ricerca. La scansione delle porte, inoltre, non consente di determinare che le porte utilizzate dal rootkit sono aperte, poiché il rootkit impedisce al programma di scansione di rilevare la porta aperta. È molto difficile, quindi, essere sicuri che in un computer non sia presente alcun rootkit.
  
I trojan horse sono in genere più semplici da individuare rispetto ai rootkit, anche se possono causare danni maggiori. I programmi di questo tipo possono fornire funzionalità di controllo remoto simili a quelle dei rootkit oppure causare semplicemente la distruzione dei dati, come un normale virus. La caratteristica principale di un trojan horse è che, come implica il nome, tenta con l'inganno di far avviare l'eseguibile dall'utente, facendolo sembrare un programma utile.
  
La maggior parte dei programmi dannosi non sono dotati della stessa flessibilità o capacità di reazione degli attacchi controllati direttamente dalle persone. Tuttavia, è necessario prestare particolare attenzione a possibili meccanismi utilizzati per la distribuzione dei virus, ad esempio la posta elettronica, che sono in grado di eludere la rete perimetrale. Per ridurre gli effetti di questo tipo di attacco è possibile definire alcuni filtri rigorosi sugli allegati di posta elettronica.
  
Di seguito sono elencate le categorie degli attacchi esterni:
  
-   Tentativo di compromissione delle credenziali
  
-   Sfruttamento dei punti di vulnerabilità
  
-   Installazione di un rootkit o di un trojan horse
  
-   Tentativo di far eseguire a un utente un programma dannoso
  
-   Accesso a un computer non autorizzato
  
#### Tentativo di compromissione delle credenziali
  
Gli utenti malintenzionati utilizzano diversi approcci per ottenere le credenziali degli account utente. Il metodo più diffuso consiste nel sottoporre un singolo account utente a un attacco con dizionario. In questo caso, l'utente malintenzionato conosce soltanto il nome di un account utente. Un altro approccio si basa sull'utilizzo dello stesso insieme di password per ogni account utente contenuto nel database del servizio directory. In questo caso, è probabile che l'utente malintenzionato abbia accesso al servizio directory dell'organizzazione. Per rilevare questo tipo di attacco, è necessario monitorare i blocchi degli account e i tentativi ripetuti di accesso non riuscito per una serie di account, anche se il numero totale dei tentativi di accesso è inferiore al limite di blocchi dell'account.
  
I cambiamenti o le reimpostazioni delle password forniscono un'altra opportunità per ottenere le informazioni di accesso di un utente. Poiché per queste operazioni viene generato lo stesso evento sia in caso di operazione riuscita che non riuscita, un utente malintenzionato può evitare la rilevazione aggirando i criteri di blocco dell'account. Una soluzione di monitoraggio della protezione deve individuare i tentativi ripetuti di cambiamento o reimpostazione della password, in particolare quelli che si verificano al di fuori delle apposite procedure previste per tali operazioni all'interno dell'organizzazione.
  
La scansione ciclica delle password non rappresenta un attacco, ma indica l'esecuzione di uno script dell'utente che scorre ciclicamente un numero prestabilito di operazioni di cambiamento password consentendo all'utente di riutilizzare una password precedente. Il numero dei cambiamenti coincide con il limite di riutilizzo delle password. Questo scenario è indicato da una rapida serie di eventi 627 in cui il valore del campo Nome utente primario corrisponde al valore del campo Nome account di destinazione. L'implementazione di un controllo sulla durata minima della password causa il fallimento dei tentativi di cambiamento della password.
  
Nella seguente tabella sono elencati gli eventi generati da attacchi che tentano di individuare le credenziali degli utenti. Questi eventi, tuttavia, possono anche verificarsi durante le normali operazioni di rete o quando utenti legittimi dimenticano le proprie password.
  
**Tabella 4.13. Eventi di attacco delle credenziali di autenticazione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">529</td>
<td style="border:1px solid black;">Accesso non riuscito: nome utente sconosciuto o password non valida</td>
<td style="border:1px solid black;">Controllare eventuali tentativi in cui il valore del campo <strong>Nome account di destinazione</strong> corrisponde ad Administrator o all'account amministratore predefinito rinominato. Controllare i tentativi multipli di accesso non riusciti che sono inferiori al limite di blocchi dell'account. Questo evento può indicare un tentativo da parte di un utente non autorizzato di individuare la password dell'amministratore locale. Mettere in relazione con l'evento 539 per individuare uno schema di blocchi continui dell'account.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">534</td>
<td style="border:1px solid black;">Accesso non riuscito: tipo di accesso non consentito</td>
<td style="border:1px solid black;">Un utente ha tentato di accedere mediante un tipo di accesso non consentito, ad esempio rete, interattivo, batch o servizio. Controllare i campi <strong>Nome account di destinazione</strong> e <strong>Nome workstation</strong> e il <strong>tipo di accesso</strong>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">539</td>
<td style="border:1px solid black;">Account bloccato</td>
<td style="border:1px solid black;">Un utente ha tentato di accedere a un account già bloccato. Mettere in relazione con l'evento 529 per individuare uno schema di blocchi continui.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">553</td>
<td style="border:1px solid black;">Attacco di tipo replay rilevato</td>
<td style="border:1px solid black;">Questo evento si verifica quando il pacchetto di autenticazione, in genere Kerberos, rileva un tentativo di accesso mediante riproduzione delle credenziali di un utente. È necessario eseguire immediatamente un'analisi approfondita. In alternativa, questo evento può indicare una configurazione di rete non corretta.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">627</td>
<td style="border:1px solid black;">Tentativo di cambiamento della password</td>
<td style="border:1px solid black;">Confrontare i campi <strong>Nome utente primario</strong> e <strong>Nome account di destinazione</strong> per determinare se il tentativo di cambiamento della password è stato eseguito dal proprietario dell'account o da un altro utente. Se il valore in <strong>Nome utente primario</strong> non corrisponde a quello in <strong>Nome account di destinazione</strong>, significa che un utente diverso dal proprietario dell'account ha tentato di cambiare la password.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">628</td>
<td style="border:1px solid black;">Impostazione o reimpostazione della password dell'account utente</td>
<td style="border:1px solid black;">Questa operazione può essere eseguita soltanto da persone o processi autorizzati, ad esempio dal personale del supporto tecnico o dall'utente proprietario della password. In caso contrario, è necessario eseguire immediatamente un'analisi approfondita dell'evento.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">644</td>
<td style="border:1px solid black;">Blocco automatico dell'account utente</td>
<td style="border:1px solid black;">Un account utente è stato bloccato poiché il numero dei tentativi di accesso consecutivi non riusciti è maggiore del limite di blocchi dell'account. Mettere in relazione con gli eventi 529, 675, 676 (solo Windows 2000 Server) e 681. Vedere anche le informazioni riportate in questa tabella per l'evento 12294.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">675</td>
<td style="border:1px solid black;">Preautenticazione non riuscita</td>
<td style="border:1px solid black;">Mettere in relazione con l'evento 529 per trovare le altre cause per l'accesso non riuscito, ad esempio la sincronizzazione dell'orario o l'aggiunta non corretta di account computer al dominio.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">12294</td>
<td style="border:1px solid black;">Tentativo di blocco account</td>
<td style="border:1px solid black;">Questo evento indica un possibile attacco a forza bruta nei confronti dell'account Administrator predefinito. Poiché questo account non può essere bloccato, nel registro eventi di sistema viene registrato in alternativa l'evento SAM 12294. È necessario analizzare immediatamente anche una singola occorrenza di questo evento, poiché può anche indicare la presenza di un sistema operativo non autorizzato. Controllare il campo <strong>Nome dominio</strong> per individuare domini sconosciuti.</td>
</tr>
</tbody>
</table>
  
#### Sfruttamento dei punti di vulnerabilità
  
Poiché le vulnerabilità possono essere presenti in qualsiasi computer, gli utenti malintenzionati tentano di sfruttarle per accedere alla rete di un'organizzazione. La migliore protezione contro questo tipo di attacchi consiste nel definire un processo efficace di gestione delle patch basato su Microsoft Systems Management Server 2003 o Microsoft Software Update Services.
  
Per ulteriori informazioni sulla gestione delle patch, vedere [Patch Management Using Systems Management Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=e9eab1bd-13e7-4e25-85c5-ce2d191c3d63) all'indirizzo http://www.microsoft.com/downloads/details.aspx?FamilyID=e9eab1bd-13e7-4e25-85c5-ce2d191c3d63 e [Patch Management Using Software Update Services](http://www.microsoft.com/downloads/details.aspx?familyid=38d7e99b-e780-43e5-aa84-cdf6450d8f99) all'indirizzo http://www.microsoft.com/downloads/details.aspx?familyid=38d7e99b-e780-43e5-aa84-cdf6450d8f99 (informazioni in lingua inglese).
  
Particolarmente importante è il monitoraggio della protezione nei computer appartenenti alla rete perimetrale, poiché sono quelli che subiscono i primi attacchi da parte degli utenti malintenzionati. A meno che non esista un apposito meccanismo in grado di rilevare che è in corso un attacco, è possibile che un'organizzazione venga a conoscenza di eventuali situazioni non corrette soltanto dopo che un utente malintenzionato ha già compromesso la rete aziendale. Il sistema di monitoraggio della protezione nei computer della rete perimetrale deve essere in grado di rilevare una vasta gamma di eventi.
  
Tipiche situazioni di sfruttamento delle vulnerabilità includono i tentativi di accesso non autorizzato e l'utilizzo di identità privilegiate. Nella seguente tabella sono elencati alcuni eventi che possono indicare possibili attacchi nei confronti di computer.
  
**Nota: **per ulteriori eventi che possono indicare questi tipi di attacchi, vedere la Tabella 4.13 "Eventi di attacco delle credenziali di autenticazione".
  
**Tabella 4.14. Eventi di sfruttamento delle vulnerabilità mediante aumento dei privilegi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">528
538</td>
<td style="border:1px solid black;">Accesso locale e disconnessione</td>
<td style="border:1px solid black;">I tentativi di accesso locale dovrebbero essere molto rari nei computer presenti nella rete perimetrale. Mettere in relazione con il campo ID di accesso. Eseguire un'analisi approfondita se sono presenti valori imprevisti nei campi <strong>Nome account utente</strong>, <strong>Ora</strong> o <strong>Nome workstation</strong>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">576</td>
<td style="border:1px solid black;">Accesso privilegiato</td>
<td style="border:1px solid black;">In Windows Server 2003 con SP1 o versione successiva, questo evento indica un accesso amministratore, ovvero un accesso che dispone di privilegi sufficienti per compromettere la protezione o assumere il controllo del computer. Nelle versioni precedenti di Windows, questo evento era di interesse solo se conteneva un privilegio importante quale <strong>SeSecurityPrivilege</strong> o <strong>SeDebugPrivilege</strong>.</td>
</tr>
</tbody>
</table>
  
**Nota:** nelle versioni di Windows precedenti a Windows Server 2003, l'evento 576 viene elencato nella categoria Uso del privilegio. In Windows Server 2003 e versioni successive, questo evento è incluso anche nella categoria Accesso. Di conseguenza, la configurazione delle impostazioni di controllo per una delle due categorie determina la comparsa di questo evento.
  
#### Installazione di un rootkit o di un trojan horse
  
La rilevazione dell'installazione di un rootkit mediante il monitoraggio della protezione è difficile ma non impossibile. L'avvio e l'arresto in rapida successione di un programma sconosciuto può indicare la presenza di un rootkit. Una volta avviato, un rootkit non può essere più rilevato dal sistema operativo. Sembra quindi che il programma venga chiuso senza generare altri eventi.
  
I trojan horse sono in genere più semplici da individuare poiché non sono dotati della stessa capacità di mascheramento dei rootkit. A questa categoria appartengono anche i keystroke logger, ovvero i programmi che tentano di registrare le battute.
  
Nella seguente tabella sono elencati gli eventi che possono indicare l'installazione di un rootkit.
  
**Tabella 4.15. Eventi legati alla presenza di rootkit o trojan horse**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">592</td>
<td style="border:1px solid black;">Creazione di un nuovo processo</td>
<td style="border:1px solid black;">Controllare i campi <strong>Nome file immagine</strong> e <strong>Nome utente</strong> per i nuovi processi. Tutti i processi devono essere programmi autorizzati.</td>
</tr>
</tbody>
</table>
  
#### Tentativo di far eseguire a un utente un programma dannoso
  
In questo approccio, l'utente malintenzionato tenta di eludere il firewall e la rete perimetrale per fornire un allegato eseguibile a un utente, in genere utilizzando la posta elettronica. Esistono tuttavia altri meccanismi, ad esempio un sito Web infetto, che sono in grado di ottenere lo stesso risultato.
  
L'obiettivo principale dell'utente malintenzionato è di far in modo che l'utente esegua il programma. Se il tentativo riesce, il programma viene inizializzato nel contesto di protezione dell'utente. A questo punto, il programma può tentare di aumentare i privilegi, ad esempio allo scopo di acquisire diritti equivalenti a quelli dell'amministratore o di ottenere l'accesso alla rete.
  
Per rilevare i tentativi di avvio dei programmi è possibile configurare il controllo tracciato processo. Se sono definiti criteri di restrizione software per limitare i programmi che possono essere eseguiti da un utente, il tentativo di avviare un programma non autorizzato causa la generazione di un evento di controllo non riuscito. Questa condizione richiede un'analisi approfondita, soprattutto se si verificano i seguenti eventi:
  
-   **Installazione di processi come LocalSystem.** I processi eseguiti come LocalSystem devono essere ben definiti. In genere si tratta di eseguibili del servizio, ad esempio **services.exe**. L'evento 592, che indica la presenza di un altro tipo di immagine eseguibile, richiede un'analisi più approfondita.
  
-   **Installazione di processi in orari insoliti.** Se nel computer non sono previste attività di processi batch pianificate, ad esempio copie di backup, applicazioni CGI o script, i processi creati in orari insoliti, ad esempio nelle ore notturne, richiedono un'analisi più approfondita. Cercare eventuali occorrenze dell'evento 592.
  
Nella Tabella 4.15 "Eventi legati alla presenza di rootkit o trojan horse" vengono elencati gli eventi che possono verificarsi quando un utente malintenzionato tenta di far eseguire a un utente un'applicazione dannosa.
  
#### Accesso a un computer non autorizzato
  
Gli amministratori utilizzano sempre più spesso funzionalità di gestione remota, ad esempio Servizi terminal, per connettersi a determinati computer. È quindi indispensabile monitorare questi computer allo scopo di individuare eventuali tentativi di accesso in modalità interattiva e verificare la validità del tentativo di connessione. Di seguito sono elencati alcuni dei controlli da eseguire:
  
-   Individuazione degli accessi che utilizzano account dei servizi
  
-   Registrazione dei tentativi di accesso ai server con account non autorizzati
  
-   Controllo dei tentativi di accesso ai server da aree geografiche insolite
  
-   Elenco dei tentativi di accesso ai server da un intervallo di indirizzi IP esterni
  
Questo tipo di monitoraggio è particolarmente importante per le risorse critiche, ad esempio i record contenenti i dati dei clienti o informazioni finanziarie riservate. Queste risorse devono essere collocate su un server separato ed occorre impostare criteri rigorosi per l'accesso a queste risorse.
  
Il sistema di monitoraggio della protezione deve indicare chiunque tenti di connettersi a questi computer e tali informazioni devono essere confrontate con l'elenco degli utenti autorizzati. Nella seguente tabella sono elencati gli eventi che possono indicare l'utilizzo di un computer non autorizzato.
  
**Tabella 4.16. Eventi di utilizzo di un computer non autorizzato**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID evento</th>
<th>Occorrenza</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">528</td>
<td style="border:1px solid black;">Accesso riuscito</td>
<td style="border:1px solid black;">Controllare il campo <strong>Nome workstation</strong> e quindi il campo <strong>Nome account utente</strong>. Assicurarsi che il valore del campo <strong>Indirizzo di rete origine</strong> sia compreso nell'intervallo di indirizzi IP dell'organizzazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">530</td>
<td style="border:1px solid black;">Accesso non riuscito: restrizioni sull'orario</td>
<td style="border:1px solid black;">Questo evento indica un tentativo di accesso al di fuori degli orari consentiti. Controllare il valore di <strong>Nome account utente</strong> e <strong>Nome workstation</strong>.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Implementazione dell'analisi legale
  
Nel Capitolo 3 "Problemi e requisiti" sono state illustrate le principali differenze tra l'analisi legale e la rilevazione delle violazioni dei criteri e l'individuazione degli attacchi esterni. Nell'analisi legale vengono utilizzati molti degli elementi già presi in considerazione in questa guida, con particolare attenzione agli aspetti legati all'analisi e all'archiviazione a lungo termine dei dati risultanti. Nella maggior parte delle analisi di questo tipo vengono quindi esaminati gli scenari basati, ad esempio, sulla creazione dell'elenco di tutti gli eventi relativi all'utente A o generati dal computer B.
  
Il monitoraggio della protezione per l'analisi legale richiede le seguenti operazioni:
  
-   Scelta dei tipi di evento da archiviare
  
-   Calcolo del numero di eventi previsti giornalmente
  
-   Individuazione dei limiti temporali per l'archiviazione in linea e non in linea
  
-   Adattamento del database in linea per la gestione del numero di eventi previsti
  
-   Definizione di un sistema di backup in grado di gestire il carico di eventi previsti giornalmente
  
-   Scelta del metodo di gestione del sistema di archiviazione
  
I requisiti di archiviazione dipendono da tre fattori principali:
  
-   Numero di eventi che è necessario registrare
  
-   Frequenza di generazione di questi eventi nei computer di destinazione
  
-   Periodo massimo di mantenimento in linea di queste informazioni
  
**Nota:** un** **controller di dominio con le tutte le categorie di controllo attivate tranne quella per l'accesso agli oggetti può produrre, ogni ora, circa 3000 eventi di protezione. L'archiviazione di queste informazioni come file CSV da Event Comb MT genera un file da 1 MB. L'utilizzo dei controlli per l'accesso agli oggetti e del tracciato processo può aumentare in modo significativo questi valori.
  
Il risultato dell'analisi può portare alla definizione di requisiti di archiviazione non realistici. In questo caso, è necessario trovare un compromesso tra il numero dei computer monitorati, gli eventi da monitorare e il tempo di archiviazione in linea di questi eventi prima dello spostamento nel sistema di archiviazione non in linea.
  
Nell'Appendice A "Esclusione degli eventi superflui" sono elencati gli eventi che non forniscono informazioni utili. In questo modo, è possibile evitare di monitorare eventi che non aggiungono alcuna informazione rilevante per la protezione del sistema.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Per garantire l'integrità di una rete è essenziale disporre di un sistema efficace di monitoraggio della protezione e di rilevazione degli attacchi. La pianificazione di una soluzione basata sui controlli di protezione di Windows richiede una conoscenza completa e dettagliata degli obiettivi del sistema, nonché una corretta valutazione dei rischi e delle minacce a cui è soggetta la rete e delle firme di attacco associate a ciascun tipo di minaccia.
  
In Windows Server 2003 vengono forniti i componenti di base per la creazione di un sistema di monitoraggio della protezione e di rilevazione degli attacchi basato sulla registrazione degli eventi di protezione. Microsoft mette a disposizione componenti basati su server, ad esempio Microsoft Operations Manager, e programmi di utilità, ad esempio Event Comb MT, che consentono di mettere in relazione i registri eventi di più computer e di eseguire un'analisi degli eventi di protezione. I partner Microsoft forniscono utilità e strumenti aggiuntivi che consentono di individuare rapidamente i profili di attacco.
  
##### Download
  
[![](images/Dd536267.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://go.microsoft.com/fwlink/?linkid=41310)
  
[](#mainsection)[Inizio pagina](#mainsection)
