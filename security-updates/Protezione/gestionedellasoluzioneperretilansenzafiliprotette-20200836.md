---
TOCTitle: Gestione della soluzione per reti LAN senza fili protette
Title: Gestione della soluzione per reti LAN senza fili protette
ms:assetid: '9490af9a-fd41-45c7-9876-f5ac2c80b770'
ms:contentKeyID: 20200836
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536237(v=TechNet.10)'
---

Protezione delle reti LAN senza fili con PEAP e password
========================================================

### Capitolo 8: Gestione della soluzione per reti LAN senza fili protette

Aggiornato: 2 aprile 2004

##### In questa pagina

[](#ehaa)[Introduzione](#ehaa)
[](#egaa)[Cenni preliminari](#egaa)
[](#efaa)[Prima di iniziare](#efaa)
[](#eeaa)[Attività fondamentali di manutenzione](#eeaa)
[](#edaa)[Esercizio dell'infrastruttura WLAN](#edaa)
[](#ecaa)[Risoluzione dei problemi](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Riferimenti](#eaaa)

### Introduzione

In questo capitolo vengono descritte le procedure operative per la gestione della soluzione *Protezione delle reti LAN senza fili con PEAP e password*. Viene spiegato come eseguire le attività operative e di supporto essenziali per una corretta gestione dell'infrastruttura per la protezione delle reti LAN senza fili e in particolare dei server di Servizi autenticazione Internet (IAS), dell'Autorità di certificazione (CA), dei punti di accesso (AP) senza fili e dei client della rete LAN senza fili (WLAN). Non vengono fornite indicazioni per la gestione delle reti in generale o per la gestione di aspetti diversi dai servizi per la protezione, ad esempio per l'analisi e l'ottimizzazione del traffico della rete.

[](#mainsection)[Inizio pagina](#mainsection)

### Cenni preliminari

Il capitolo è suddiviso nelle seguenti sezioni:

-   **Attività fondamentali di manutenzione** In questa sezione vengono descritte le attività fondamentali che è necessario eseguire per impostare il sistema di gestione (ad esempio, configurare i processi di backup) e per svolgere la regolare manutenzione (ad esempio, attività di manutenzione settimanali).

-   **Esercizio dell'infrastruttura WLAN** Si tratta prevalentemente di una sezione di riferimento, in cui sono descritti i vari tipi di attività che occorre svolgere per una corretta manutenzione dell'infrastruttura per la protezione delle reti LAN senza fili. Le sottosezioni contengono informazioni sulle attività operative standard, sull'applicazione di modifiche, sulle attività di supporto e sulle attività di ottimizzazione.

-   **Risoluzione dei problemi** Questa sezione contiene procedure e diagrammi di flusso utili per risolvere i problemi comuni che possono verificarsi nell'infrastruttura WLAN. Contiene, inoltre, descrizioni di strumenti e procedure utili per tenere traccia delle attività dei vari componenti e risolvere eventuali problemi.

-   **Riferimenti** In questa sezione vengono elencate le fonti di informazioni supplementari a cui viene fatto riferimento nel testo.

[](#mainsection)[Inizio pagina](#mainsection)

### Prima di iniziare

È necessario avere dimestichezza con l'amministrazione di Microsoft® Windows® Server™ 2003 o Windows® 2000 Server, in particolare per le seguenti aree:

-   Operazioni di base e manutenzione di Microsoft Windows Server 2003, compreso l'utilizzo di strumenti quali Visualizzatore eventi, Gestione computer e NTBackup.

-   IAS.

-   Servizi certificati.

-   Servizio directory Microsoft Active Directory® (inclusi struttura e strumenti di Active Directory), gestione degli utenti, dei gruppi e degli altri oggetti di Active Directory e utilizzo dei Criteri di gruppo.

-   Concetti alla base della protezione dei sistemi Windows, quali utenti, gruppi, controllo, elenchi di controllo di accesso (ACL), utilizzo dei modelli di protezione e applicazione dei modelli di protezione mediante Criteri di gruppo o strumenti della riga di comando.

-   Concetti alla base delle reti in generale e delle reti LAN senza fili.

-   Conoscenza di Windows Script Host e di Microsoft Visual Basic® Scripting Edition (VBScript). Questa conoscenza serve per capire e utilizzare gli script forniti con la soluzione.

Inoltre, è necessario aver letto i seguenti capitoli e avere compreso l'architettura e la progettazione della soluzione:

-   Capitolo 2 "Pianificazione dell'implementazione della protezione di reti LAN senza fili"

-   Capitolo 3 "Predisposizione dell'ambiente"

-   Capitolo 4 "Creazione dell'Autorità di certificazione della rete"

-   Capitolo 5 "Creazione dell'infrastruttura di protezione per LAN senza fili"

-   Capitolo 6 "Configurazione dei client delle reti LAN senza fili"

[](#mainsection)[Inizio pagina](#mainsection)

### Attività fondamentali di manutenzione

In questa sezione vengono descritte le attività che è necessario eseguire per far funzionare in modo corretto l'infrastruttura della rete LAN senza fili. Queste attività possono essere suddivise in due categorie:

-   Attività iniziali di configurazione

-   Attività ordinarie di manutenzione

In questa sezione, inoltre, vengono elencati gli strumenti e le tecnologie utilizzati nelle procedure descritte in questo capitolo.

#### Attività iniziali di configurazione

Nella tabella seguente sono elencate le attività da eseguire per rendere operativa l'infrastruttura per la protezione della rete LAN senza fili.

**Tabella 8.1: Attività iniziali di configurazione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome attività</th>
<th style="border:1px solid black;" >Sezione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Configurazione del backup di IAS</td>
<td style="border:1px solid black;">Attività operative</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configurazione dei tipi di avviso</td>
<td style="border:1px solid black;">Monitoraggio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Attivazione del monitoraggio di IAS</td>
<td style="border:1px solid black;">Monitoraggio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Attivazione del monitoraggio della CA</td>
<td style="border:1px solid black;">Monitoraggio</td>
</tr>
</tbody>
</table>
  
#### Attività di manutenzione
  
Nella tabella seguente sono elencate le attività che devono essere eseguite regolarmente per garantire il corretto funzionamento dell'infrastruttura per la protezione della rete LAN senza fili. Questa tabella può essere utilizzata per prevedere le risorse necessarie e pianificare le attività operative per l'amministrazione del sistema.
  
**Tabella 8.2: Attività di manutenzione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome attività</th>
<th style="border:1px solid black;" >Frequenza</th>
<th style="border:1px solid black;" >Sezione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Testing dei backup</td>
<td style="border:1px solid black;">6 mesi</td>
<td style="border:1px solid black;">Attività operative</td>
</tr>
</tbody>
</table>
  
#### Strumenti e tecnologie necessari
  
Nella tabella seguente sono elencati gli strumenti e le tecnologie utilizzati nelle procedure descritte in questo capitolo.
  
**Tabella 8.3: Tecnologia necessaria**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome</th>
<th style="border:1px solid black;" >Origine</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Console di gestione (MMC) Utenti e computer di Active Directory</td>
<td style="border:1px solid black;">Windows Server 2003</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MMC Autorità di certificazione</td>
<td style="border:1px solid black;">Windows Server 2003</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Certutil.exe</td>
<td style="border:1px solid black;">Windows Server 2003</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DCDiag.exe</td>
<td style="border:1px solid black;">Strumenti di supporto di Windows Server 2003</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DSquery.exe</td>
<td style="border:1px solid black;">Windows Server 2003</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Visualizzatore eventi</td>
<td style="border:1px solid black;">Windows Server 2003</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Console Gestione criteri di gruppo (GPMC, Group Policy Management Console)</td>
<td style="border:1px solid black;">Download Web da Microsoft.com</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSS WLAN Tools</td>
<td style="border:1px solid black;">Script installati con questa soluzione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Netdiag.exe</td>
<td style="border:1px solid black;">Strumenti di supporto di Windows Server 2003</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Performance Monitor</td>
<td style="border:1px solid black;">Windows Server 2003</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Integrità PKI</td>
<td style="border:1px solid black;">Windows Server 2003 Resource Kit</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporti rimovibili per il backup della CA principale</td>
<td style="border:1px solid black;">CD-RW o nastro</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SchTasks.exe</td>
<td style="border:1px solid black;">Windows Server 2003</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Editor di testo</td>
<td style="border:1px solid black;">Blocco note, Windows Server 2003</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Utilità di backup di Windows</td>
<td style="border:1px solid black;">Windows Server 2003</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Servizio Utilità di pianificazione di Windows</td>
<td style="border:1px solid black;">Windows Server 2003</td>
</tr>
</tbody>
</table>
  
**Tabella 8.4: Tecnologia consigliata**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome</th>
<th style="border:1px solid black;" >Origine</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Infrastruttura per la posta elettronica per gli avvisi operativi</td>
<td style="border:1px solid black;">Server e client SMTP/POP3/IMAP, ad esempio Microsoft Exchange Server e Microsoft Outlook®</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Console avvisi operativi</td>
<td style="border:1px solid black;">Microsoft Operations Manager o altro sistema di monitoraggio dei servizi</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Distribuzione degli aggiornamenti del sistema operativo</td>
<td style="border:1px solid black;">Microsoft Systems Management Server (SMS) o Microsoft Software Update Services (SUS)</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Esercizio dell'infrastruttura WLAN
  
In questa sezione vengono descritte le attività principali che occorre eseguire per una corretta manutenzione dell'infrastruttura per la protezione delle reti WLAN.
  
#### Attività operative
  
Nelle attività operative rientrano quelle attività che devono essere svolte con regolarità per garantire il corretto funzionamento dell'infrastruttura WLAN.
  
##### Backup di IAS e dell'Autorità di certificazione
  
È necessario eseguire backup regolari dei server IAS, compreso il server IAS in cui è in esecuzione l'Autorità di certificazione. Per quanto riguarda IAS, è necessario eseguire una procedura speciale per esportare le impostazioni di IAS in un file, quindi eseguire un normale backup di tale file. Per quanto riguarda Servizi certificati, è possibile avvalersi del backup dello stato del sistema Windows, disponibile nell'Utilità di backup di Windows. È necessario predisporre procedure di backup adeguate per tutti i server in cui è in esecuzione IAS.
  
Le due procedure descritte di seguito non si escludono a vicenda. È necessario configurare sia il backup di IAS, sia il backup del server.
  
###### Configurazione del backup di IAS
  
È necessario creare una cartella con autorizzazioni limitate in cui ogni notte verrà esportata la configurazione di IAS. È necessario, inoltre, creare un processo pianificato che eseguirà il backup della configurazione di IAS ogni notte (lo script di backup non richiede che IAS venga arrestato durante l'operazione di backup). Se il backup va a buon fine, viene registrato un evento nel registro applicazioni di Windows. Se il backup non va a buon fine, viene registrato un errore.
  
**Avviso:** i file di backup di IAS contengono tutti i segreti dei client RADIUS. Si tratta di informazioni molto riservate, quindi è importante conservare i file di backup in un luogo sicuro.
  
**Per configurare il backup di IAS**
  
1.  Aprire una shell comandi nel server utilizzando il collegamento **MSS WLAN Tools** e specificare il comando seguente per creare una cartella in cui salvare le impostazioni di IAS:
  
    **mdc:\\IASBackup**
  
    (Di norma il file con la configurazione di IAS non supera i 100 KB e può essere salvato nell'unità di sistema, come qui indicato.)
  
2.  Specificare il seguente comando per impostare le autorizzazioni per la cartella, in modo che solo gli amministratori e i membri del gruppo Backup Operators possano leggere e modificare il contenuto della cartella:
  
    **cacls c:\\IASBackup /G system:F administrators:F "Backup Operators":C**
  
    (Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe.)
  
3.  Verificare il backup mediante il seguente comando:
  
    **"C:\\Programmi\\Microsoft\\Microsoft WLAN-PEAP Tools\\msstools.cmd" BackupIAS /path:C:\\IASBackup**
  
    (Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe. "**Microsoft WLAN-PEAP Tools**" contiene due spazi incorporati, uno dopo "Microsoft" e l'altro dopo "WLAN-PEAP".)
  
    **Nota:** se il backup va a buon fine, viene scritto un evento nel registro applicazioni di Windows e sullo schermo, altrimenti viene registrato un errore.
  
4.  Creare un'attività pianificata che esegua l'esportazione della configurazione di IAS ogni notte. Ad esempio, il seguente comando consente di pianificare l'esecuzione del processo ogni notte alle 22.00:
  
    **SCHTASKS /Create /RU system /SC Daily /TN "IAS Backup"/TR "\\"C:\\Programmi\\Microsoft\\Microsoft WLAN-PEAP Tools\\msstools.cmd\\" BackupIAS /path:C:\\IASBackup" /ST 22.00**
  
    (Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe. "**Microsoft WLAN-PEAP Tools**" contiene due spazi incorporati, uno dopo "Microsoft" e l'altro dopo "WLAN-PEAP".)
  
    **Nota:** se si racchiude il percorso del file script msstools.cmd tra barre rovesciate (\\), le virgolette doppie (") non vengono interpretate e rimosse dal comando dalla shell comandi di Windows. Il comando che viene passato e archiviato dall'Utilità di pianificazione è come quello presentato nel passaggio 3.
  
###### Esecuzione dei backup del server
  
Dopo aver pianificato un'attività per il backup della configurazione di IAS su disco, è necessario configurare anche un backup regolare su un supporto rimovibile o in un percorso della rete dello stato del sistema del server e dei file esportati contenenti la configurazione di IAS. Il modo più semplice consiste nell'utilizzare l'Utilità di backup di Windows. Se si utilizza un sistema di backup diverso, è necessario verificare che contenga la funzionalità equivalente a quella del backup dello stato del sistema Windows. Questa informazione dovrebbe essere contenuta nella documentazione del sistema di backup. Il backup dello stato del sistema è essenziale per poter eseguire un backup corretto dei database delle chiavi e dei certificati di Servizi certificati e Active Directory.
  
Se nel programma di backup in uso non è disponibile la funzionalità per il backup dello stato del sistema Windows, è possibile procedere come segue:
  
-   Configurare l'Utilità di backup di Windows in modo che venga eseguito un backup dello stato del sistema in un file nel server (controllare che lo spazio disponibile su disco sia sufficiente, perché un backup dello stato del sistema occupa 500 MB o più). Per informazioni in merito, vedere la Guida in linea dell'Utilità di backup di Windows.
  
-   Configurare il software di backup in modo che vengano copiati sia il file di backup dello stato del sistema, sia il file di backup di IAS descritto nella precedente procedura.
  
Per ottenere backup coerenti e protetti, procedere come descritto di seguito:
  
-   Pianificare le diverse operazioni di backup in modo che non si sovrappongano, altrimenti si corre il rischio di danneggiare i dati dei backup.
  
-   Avviare il backup del server e dello stato del sistema almeno 10 minuti dopo l'avvio del backup di IAS.
  
-   Se si eseguono file distinti per lo stato del sistema e il server, avviare il backup del server almeno un'ora dopo il backup dello stato del sistema.
  
-   Conservare sempre una copia recente dei dati del backup in un posto fisico diverso dal server sottoposto a backup. In questo modo sarà possibile ripristinare il server nel caso in cui tutte le apparecchiature informatiche subiscano danni irreversibili o diventino inaccessibili.
  
    **Avviso:** questi dati di backup sono molto riservati, perché contengono i segreti RADIUS di tutti i punti di accesso del server, tutte le informazioni sulle chiavi private per la CA e il database di Active Directory. È necessario trasferire e archiviare i supporti di backup in modo protetto, perché la loro acquisizione da parte di persone non autorizzate potrebbe compromettere la protezione dell'intera organizzazione.
  
##### Testing dei backup
  
È possibile verificare in modo adeguato il backup del sistema solo ripristinandolo in un server di prova e controllando che il server ripristinato funzioni come previsto. Il backup dello stato del sistema deve essere ripristinato in un sistema con configurazione del disco uguale a quella del server sottoposto a backup. Ad esempio, Windows deve essere installato, nel server di prova, in un percorso uguale a quello del server sottoposto a backup e la configurazione dell'unità di archiviazione per i file di Windows (ad esempio, per i file di paging) deve essere uguale nei due server.
  
**Importante:** per evitare conflitti a livello di nomi e indirizzi IP tra il server di prova e il server originale, il server di prova deve essere tenuto in modalità non in linea dal momento in cui viene avviato il ripristino del sistema.
  
**Per ripristinare il server**
  
1.  Predisporre un server di ripristino in cui ripristinare i dati del backup. Nel server di ripristino deve venire utilizzata la stessa edizione di Windows Server 2003 utilizzata nel server sottoposto a backup. (È necessario, inoltre, installare in questo server gli script forniti con la soluzione. Per ulteriori informazioni, vedere la sezione "Installazione degli strumenti della soluzione" del capitolo 3 "Predisposizione dell'ambiente".)
  
2.  Se si utilizzano un backup dello stato del sistema e un backup dei file, utilizzare il software di backup per ripristinare dal supporto del backup nel server il file di backup dello stato del sistema e il file di backup delle impostazioni di IAS. Le impostazioni di IAS devono essere ripristinate nello stesso percorso: C:\\IASBackup.
  
3.  Eseguire l'utilità di backup di Windows e selezionare il file di backup dello stato del sistema ripristinato. È necessario essere un membro di un gruppo che dispone delle autorizzazioni di backup e ripristino sul computer (ad esempio Backup Operators o Administrators).
  
4.  Fare clic su **Ripristina**.
  
5.  Riavviare il sistema.
  
6.  Verificare che tutto funzioni come previsto dopo il riavvio e che Active Directory e Servizi certificati vengano avviati senza errori. (I registri eventi conterranno errori causati dal fatto che il server non è connesso alla rete.)
  
7.  Utilizzare il collegamento **MSS WLAN Tools** per aprire una shell comandi. Ripristinare la configurazione di IAS specificando il seguente comando:
  
    **MSSTools RestoreIAS /path:C:\\IASBackup**
  
8.  Per verificare che le impostazioni di IAS siano state ripristinate, aprire la console di gestione di IAS e controllare le cartelle Client RADIUS e Criteri di accesso remoto.
  
#### Monitoraggio
  
In questa sezione viene descritto come monitorare i componenti IAS e CA dell'infrastruttura di protezione della rete WLAN. Non viene descritto come monitorare i punti di accesso o altre periferiche di rete senza fili, né vengono fornite indicazioni di carattere generale sul monitoraggio dei server Windows. Per informazioni sul monitoraggio dei server Windows, vedere la sezione "Riferimenti" alla fine del capitolo.
  
Nella maggior parte delle procedure di questa sezione vengono utilizzati gli script di monitoraggio forniti con la soluzione. In presenza di un problema, questi script generano un avviso e, in alcuni casi, tentano di risolverlo.
  
##### Configurazione dei tipi di avviso
  
Gli avvisi generati dagli script di monitoraggio possono essere inviati al registro eventi applicazioni di Windows e/o a uno o più indirizzi di posta elettronica. Prima di attivare gli strumenti di monitoraggio, è necessario specificare i tipi di avviso desiderati. Se, inoltre, si opta per l'invio degli avvisi a indirizzi di posta elettronica, è necessario specificare gli indirizzi di posta elettronica dei destinatari e il nome del server della posta elettronica a cui inviare i messaggi.
  
Per specificare questi parametri, è necessario modificare il file constants.vbs. Di seguito sono riportate le sezioni pertinenti del file. Le voci da modificare sono evidenziate in *corsivo*:
  
<codesnippet language displaylanguage containsmarkup="false">' Alerting parameters CONST ALERT\_EMAIL\_ENABLED = FALSE 'set to enable/disable e-mail CONST ALERT\_EVTLOG\_ENABLED = TRUE 'set to enable/disable eventlog entries ' set to comma-separated list of recipients to get e-mail alerts CONST ALERT\_EMAIL\_RECIPIENTS = "Admin@woodgrovebank.com,Ops@woodgrovebank.com" 'SMTP server to use (use DNS name or IP address) CONST ALERT\_EMAIL\_SMTP = "mail.woodgrovebank.com"   
```  
##### Monitoraggio di IAS
  
IAS registra molti eventi di diverso tipo nel registro di sistema di Windows. Fra questi vi sono le notifiche di avvio e interruzione dei servizi (ed eventuali errori o avvisi in merito) e le notifiche delle richieste di autenticazione. (Le voci del registro relative alle richieste di autenticazione sono descritte in dettaglio nella sezione "Risoluzione dei problemi", più avanti in questo capitolo.)
  
###### Attivazione del monitoraggio di IAS
  
Nella soluzione è disponibile un semplice script che consente di monitorare la reattività di IAS. Lo script controlla se il processo IAS è in esecuzione. In caso affermativo, cerca di interrogare IAS utilizzando l'interfaccia **Oggetti dati server**. Se una delle due verifiche ha esito negativo, viene generato un avviso.
  
**Nota:** lo script per il monitoraggio non verifica l'autenticazione RADIUS, ma solo la reattività generica del processo IAS. Per verificare le operazioni RADIUS end-to-end, è necessario un client RADIUS per emulare i punti di accesso senza fili che inoltrano le richieste dei client della rete WLAN.
  
La seguente procedura descrive come configurare lo script di monitoraggio in modo che venga eseguito come operazione pianificata e avvisi automaticamente l'utente in caso di arresto di IAS. Tuttavia, dal momento che lo script viene eseguito nel server, non potrà avvisare l'utente in caso di arresto del server. Pertanto è necessario monitorare anche i server, per essere sempre certi che funzionino. Per configurare lo script in modo che venga eseguito come operazione pianificata, procedere come descritto di seguito.
  
Ogni volta che viene rilevato un errore, viene inviato un avviso per posta elettronica (se è stato configurato l'invio di avvisi tramite posta elettronica) e viene registrato un evento nel registro applicazioni (per informazioni sui tipi di eventi registrati, vedere la tabella nella prossima sezione). A differenza di quanto avviene con lo script per il monitoraggio della CA, non viene effettuato alcun tentativo di risolvere i problemi riavviando IAS. Dal momento che IAS, a differenza di una CA, deve essere sempre in esecuzione per l'autenticazione dei client della rete WLAN, consentire allo script di riavviare IAS automaticamente potrebbe causare problemi, anziché risolverli. È necessario prestare attenzione a ogni avviso generato dallo script ed effettuare una diagnosi corretta della sua causa prima di provare a risolvere il problema.
  
**Per configurare il monitoraggio di IAS**
  
1.  Aprire una shell comandi utilizzando il collegamento **MSS WLAN Tools**.
  
2.  Eseguire il seguente comando per pianificare l'esecuzione dello script ogni ora a partire dall'1.30. Lo script viene eseguito 30 minuti dopo l'ora per evitare sovrapposizioni con il processo di backup di IAS.
  
    **SCHTASKS /Create /RU system /SC Hourly /TN "IAS Check"/TR "\\"C:\\Programmi\\Microsoft\\Microsoft WLAN-PEAP Tools\\msstools.cmd\\" CheckIAS" /ST 01.30**
  
    (Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe. "**Microsoft WLAN-PEAP Tools**" contiene due spazi incorporati, uno dopo "Microsoft" e l'altro dopo "WLAN-PEAP".)
  
    **Nota:** se si racchiude il percorso del file script msstools.cmd tra barre rovesciate (\\), le virgolette doppie (") non vengono interpretate e rimosse dal comando dalla shell comandi di Windows. L'utilizzo della barra rovesciata (\\) prima delle virgolette (") fa sì che il comando passato e archiviato dall'Utilità di pianificazione sia come quello presentato nel passaggio 2.
  
###### Eventi di IAS registrati dagli script MSS
  
Lo script per il monitoraggio e lo script per il backup di IAS registrano i seguenti tipi di avviso nel registro eventi.
  
**Tabella 8.5: Eventi di IAS restituiti dagli script per IAS forniti con questa soluzione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Evento IAS</th>
<th style="border:1px solid black;" >Significato</th>
<th style="border:1px solid black;" >Categoria evento</th>
<th style="border:1px solid black;" >Origine evento</th>
<th style="border:1px solid black;" >ID evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IAS Backup OK</td>
<td style="border:1px solid black;">Il backup su file della configurazione di IAS è riuscito.</td>
<td style="border:1px solid black;">Informazioni</td>
<td style="border:1px solid black;">Operazioni IAS</td>
<td style="border:1px solid black;">210</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IAS Invalid Backup Path</td>
<td style="border:1px solid black;">Il backup non è andato a buon fine, perché il percorso di destinazione specificato non era valido.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni IAS</td>
<td style="border:1px solid black;">211</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IAS No Access to Backup Path</td>
<td style="border:1px solid black;">Il backup non è andato a buon fine, perché non è stato possibile salvare i file di backup nel percorso di destinazione specificato.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni IAS</td>
<td style="border:1px solid black;">212</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IAS Restore OK</td>
<td style="border:1px solid black;">Le impostazioni IAS sono state ripristinate dalla configurazione salvata.</td>
<td style="border:1px solid black;">Informazioni</td>
<td style="border:1px solid black;">Operazioni IAS</td>
<td style="border:1px solid black;">220</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IAS Restore Failed</td>
<td style="border:1px solid black;">Il ripristino delle impostazioni di IAS non è riuscito.</td>
<td style="border:1px solid black;">Attenzione</td>
<td style="border:1px solid black;">Operazioni IAS</td>
<td style="border:1px solid black;">221</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IAS Policy Query Failed</td>
<td style="border:1px solid black;">Non è stato possibile contattare IAS mediante l'interfaccia Oggetti dati server. È possibile che IAS non sia in esecuzione.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni IAS</td>
<td style="border:1px solid black;">230</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IAS No Policies Detected</td>
<td style="border:1px solid black;">IAS non contiene criteri per l'accesso remoto.
Questa situazione non dovrebbe mai verificarsi in un server IAS con una configurazione normale e può indicare un problema a livello di IAS o di rete.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni IAS</td>
<td style="border:1px solid black;">231</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IAS Not Installed</td>
<td style="border:1px solid black;">IAS non è installato nel computer.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni IAS</td>
<td style="border:1px solid black;">232</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IAS Had Stopped</td>
<td style="border:1px solid black;">Il servizio IAS non era in esecuzione, ma è stato avviato senza problemi.</td>
<td style="border:1px solid black;">Attenzione</td>
<td style="border:1px solid black;">Operazioni IAS</td>
<td style="border:1px solid black;">233</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IAS Not Running</td>
<td style="border:1px solid black;">Non è stato possibile avviare il servizio IAS.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni IAS</td>
<td style="border:1px solid black;">234</td>
</tr>
</tbody>
</table>
  
##### Monitoraggio dell'Autorità di certificazione
  
L'Autorità di certificazione non richiede particolari attenzioni, a parte il monitoraggio delle condizioni generali del server e l'esecuzione di backup adeguati. In questa soluzione l'Autorità di certificazione, o CA, viene impiegata esclusivamente per l'attività, relativamente poco frequente, di rilascio di certificati a nuovi server IAS e per il rinnovo dei certificati esistenti una volta all'anno. Pertanto, la CA di norma non è un servizio cruciale.
  
La CA, inoltre, pubblica l'elenco dei certificati che sono stati revocati dall'amministratore. Questo elenco, detto Elenco di revoche di certificati (CRL, Certificate Revocation List), viene pubblicato settimanalmente in Active Directory. Questa CA rilascerà solo un numero ridotto di certificati, quindi l'elenco CRL sarà di dimensioni ridotte e di norma vuoto. Nonostante questo, è fondamentale che l'elenco CRL venga pubblicato in Active Directory in modo tempestivo, così che le applicazioni possano verificare se i certificati rilasciati dalla CA sono stati revocati. La CA stessa, ad esempio, deve controllare lo stato di revoca di ogni certificato rilasciato prima di inviarlo al richiedente.
  
Lo script per il monitoraggio della CA verifica che la CA risponda alle richieste e che in Active Directory sia disponibile un elenco CRL valido. Se una delle due verifiche ha esito negativo, lo script tenta di riavviare la CA. In caso di un problema all'elenco CRL, cerca anche di pubblicare un nuovo elenco CRL. Se viene rilevato un problema anche dopo questi tentativi di ripristino, viene generato un avviso che viene inviato come messaggio di posta elettronica all'account di posta elettronica configurato e registrato nel registro eventi.
  
###### Attivazione del monitoraggio dell'Autorità di certificazione
  
La seguente procedura descrive come configurare lo script di monitoraggio in modo che venga eseguito come operazione pianificata e, in presenza di un errore, avvisi automaticamente l'utente e tenti il ripristino. Questo script deve essere eseguito solo nel server della CA.
  
**Per configurare lo script per il monitoraggio della CA**
  
1.  Aprire una shell comandi utilizzando il collegamento **MSS WLAN Tools**.
  
2.  Eseguire il seguente comando per pianificare l'esecuzione dello script ogni ora a partire dall'1.20. Lo script viene eseguito 20 minuti dopo l'ora per evitare sovrapposizioni con altre operazioni pianificate.
  
    **SCHTASKS /Create /RU system /SC Hourly /TN "CA Check" /TR "\\"C:\\Programmi\\Microsoft\\Microsoft WLAN-PEAP Tools\\msstools.cmd\\" CheckCA" /ST 01.20**
  
    (Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe.)
  
    **Nota:** se si racchiude il percorso completo del file script msstools.cmd tra barre rovesciate (\\), le virgolette doppie (") non vengono interpretate e rimosse dalla shell comandi di Windows. Il percorso memorizzato dall'Utilità di pianificazione deve essere racchiuso fra virgolette se contiene spazi incorporati. Se si specifica una barra rovesciata (\\) prima delle virgolette ("), il percorso memorizzato dall'Utilità di pianificazione viene racchiuso tra virgolette doppie.
  
###### Eventi dell'Autorità di certificazione registrati dagli script MSS
  
Lo script per il monitoraggio della CA registra i seguenti eventi nel registro eventi.
  
**Tabella 8.6: Eventi della CA restituiti dallo script per il monitoraggio della CA fornito con questa soluzione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Evento CA</th>
<th style="border:1px solid black;" >Significato</th>
<th style="border:1px solid black;" >Categoria evento</th>
<th style="border:1px solid black;" >Origine evento</th>
<th style="border:1px solid black;" >ID evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CRL scaduto</td>
<td style="border:1px solid black;">Non è possibile accedere a un elenco CRL e questo sta causando una perdita a livello di servizio.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni CA</td>
<td style="border:1px solid black;">20</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CRL pronto</td>
<td style="border:1px solid black;">L'elenco CRL è ancora valido ma un nuovo elenco CRL è pronto e dovrebbe essere stato pubblicato.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni CA</td>
<td style="border:1px solid black;">21</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Impossibile recuperare l'elenco CRL da Active Directory</td>
<td style="border:1px solid black;">Non è disponibile alcun elenco CRL nel punto di distribuzione CRL pubblicato. Ciò potrebbe causare perdita di servizio.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni CA</td>
<td style="border:1px solid black;">22</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Servizi certificati non risponde:
ID evento 1: Interfaccia client non in linea
ID evento 2: Interfaccia di amministrazione non in linea</td>
<td style="border:1px solid black;">L'interfaccia RPC (Remote Procedure Call) di Servizi certificati non è in linea e non è possibile rilasciare certificati. Può essere necessario riavviare il servizio.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni CA</td>
<td style="border:1px solid black;">1 e
2</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Altro evento</td>
<td style="border:1px solid black;">Errore di esecuzione dello script di monitoraggio della CA.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">Operazioni CA</td>
<td style="border:1px solid black;">100</td>
</tr>
</tbody>
</table>
  
#### Gestione delle modifiche
  
Le attività descritte in questa sezione riguardano le modifiche che può essere necessario apportare alla configurazione dell'infrastruttura per la protezione della rete LAN senza fili.
  
##### Gestione degli aggiornamenti per la protezione di Windows
  
I Service Pack e le patch di base per Windows Server 2003 contengono aggiornamenti sia per IAS che per Servizi certificati e, quindi, non è necessario aggiornare questi componenti separatamente.
  
Leggere le indicazioni contenute nella sezione "Aggiornamento della protezione dei server" del capitolo 3 "Predisposizione dell'ambiente" e consultare la documentazione citata.
  
##### Gestione delle modifiche nei server IAS
  
Nel capitolo 5 "Creazione dell'infrastruttura di protezione per LAN senza fili" viene consigliato di designare uno dei server IAS come server "master", ovvero il server in cui apportare tutte le modifiche necessarie alla configurazione di IAS (vedere la sezione "Distribuzione delle impostazioni a più server IAS" del capitolo 5). Queste modifiche verranno replicate negli altri server dell'organizzazione, utilizzando l'esportazione e l'importazione automatiche del database di configurazione di IAS per garantire l'omogeneità delle impostazioni nell'intera infrastruttura IAS.
  
Tuttavia, di norma il gruppo di client RADIUS (i punti di accesso senza fili) configurati in ogni server IAS non viene replicato. I punti di accesso senza fili supportati da ogni server possono variare sostanzialmente e di rado in due server IAS è presente esattamente lo stesso gruppo di client. (Questo può avvenire se, ad esempio, si hanno due server IAS centrali che servono tutti i punti di accesso senza fili dell'organizzazione.)
  
###### Backup delle impostazioni di IAS prima di apportare modifiche
  
Anche se si pianificano backup dei server ogni notte, è buona norma eseguire un backup manuale di IAS prima di apportare le modifiche ai server. In questo modo sarà possibile, se necessario, eseguire il rollback delle modifiche e ripristinare lo stato del server immediatamente precedente le modifiche. Nella procedura seguente viene utilizzato lo script di backup per esportare la configurazione, i criteri, le impostazioni del registro e i client RADIUS.
  
**Per eseguire il backup della configurazione di IAS**
  
1.  Aprire una shell comandi nel server utilizzando il collegamento **MSS WLAN Tools** e specificare il comando seguente per creare una cartella in cui salvare il file di esportazione di IAS:
  
    **md c:\\IASSaveState**
  
    (Di norma il file con la configurazione di IAS non supera i 100 KB e può essere salvato nell'unità di sistema, come mostrato nell'esempio. Tuttavia, è possibile specificare qualsiasi percorso, purché vi sia coerenza tra questo comando e i successivi.)
  
2.  Specificare il seguente comando per impostare le autorizzazioni per la cartella, in modo che solo gli amministratori e i membri del gruppo Backup Operators possano leggere e modificare il contenuto della cartella:
  
    **cacls c:\\IASSaveState /G system:F administrators:F "Backup Operators":C**
  
    (Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe.)
  
3.  Per eseguire lo script di backup ed esportare le impostazioni di IAS, specificare il seguente comando:
  
    **MSSTools BackupIAS /path:C:\\IASSaveState**
  
###### Replica delle impostazioni in altri server IAS
  
È opportuno definire una procedura ripetibile per la replica delle impostazioni dal server master in tutti gli altri server IAS dell'organizzazione. In alcuni casi sarà necessario spiegare al personale del supporto come importare le impostazioni. Più spesso, tuttavia, questa operazione verrà svolta in remoto, copiando i file di configurazione e utilizzando una sessione di Desktop remoto per eseguire lo script per l'importazione della configurazione.
  
Per replicare le impostazioni in altri server IAS, eseguire le procedure descritte nella sezione "Replica delle impostazioni dal primo server IAS" del capitolo 5 "Creazione dell'infrastruttura di protezione per LAN senza fili".
  
**Nota:** può essere utile incorporare un numero di versione nel nome del criterio di accesso remoto, in modo che sia più semplice controllare che tutti i server IAS abbiano la stessa versione delle impostazioni.
  
##### Aggiunta di server IAS nell'ambiente
  
Prima di installare un nuovo server IAS, è necessario individuare i punti di accesso senza fili che verranno configurati come client del server, seguendo le indicazioni fornite nel capitolo 2 "Pianificazione dell'implementazione della protezione di reti LAN senza fili". Sarà necessario anche un altro server IAS configurato come server RADIUS secondario, in modo da conferire capacità di recupero ai punti di accesso in caso di problemi del server. Se si decide di riconfigurare i punti di accesso esistenti in modo che utilizzino il nuovo server, è necessario pianificare con attenzione la migrazione, per evitare interruzioni del servizio per gli utenti durante la migrazione dei punti di accesso. Di norma, finché per un punto di accesso è disponibile almeno un server RADIUS di autenticazione attivo, non si verifica alcuna interruzione del servizio.
  
**Per installare IAS in un nuovo server**
  
1.  Seguire le indicazioni fornite nel capitolo 3 "Predisposizione dell'ambiente" per preparare il server.
  
2.  Seguire le istruzioni contenute nelle sezioni "Installazione di IAS" e "Registrazione di IAS in Active Directory" del capitolo 5 "Creazione dell'infrastruttura di protezione di LAN senza fili".
  
3.  Per replicare le modifiche dal server IAS master nel nuovo server, seguire la procedura "Replica delle impostazioni dal primo server IAS" del capitolo 5 "Creazione dell'infrastruttura di protezione per LAN senza fili".
  
4.  Infine, aggiungere a IAS le voci dei client RADIUS per i punti di accesso senza fili e configurare i punti di accesso senza fili in modo che utilizzino il nuovo server IAS.
  
##### Aggiunta di un punto di accesso senza fili alla rete
  
Per aggiungere un nuovo punto di accesso senza fili, è necessario svolgere le seguenti attività:
  
1.  Aggiungere il punto di accesso come client RADIUS a un server IAS primario e a uno secondario.
  
2.  Configurare il punto di accesso in modo che utilizzi i server IAS come server RADIUS primario e secondario.
  
La scelta dei server IAS da utilizzare come server RADIUS primario e secondario dipenderà dalla collocazione del punto di accesso nella rete. La soluzione ideale consiste nello scegliere un server IAS primario che si trovi nella stessa LAN in cui si trova il punto di accesso, o almeno che disponga di una connettività affidabile al punto di accesso, e scegliere un server IAS secondario con una connettività affidabile al punto di accesso. Per ulteriori informazioni, vedere la sezione "Assegnazione di punti di accesso ai server RADIUS" del capitolo 2 "Pianificazione dell'implementazione della protezione di reti LAN senza fili".
  
Dopo aver individuato i server IAS adatti per il punto di accesso, svolgere le seguenti procedure. Sono le stesse procedure descritte per l'aggiunta di un punto di accesso a IAS del capitolo 5 "Creazione dell'infrastruttura di protezione per LAN senza fili".
  
**Per aggiungere un punto di accesso alla rete**
  
1.  Per aggiungere il punto di accesso come client RADIUS al server IAS primario, eseguire la procedura descritta nella sezione "Aggiunta di punti di accesso al primo server IAS" del capitolo 5 "Creazione dell'infrastruttura di protezione per LAN senza fili".
  
2.  Per aggiungere il punto di accesso come client RADIUS al server IAS secondario, eseguire la procedura descritta nella sezione "Importazione dei punti di accesso nel secondo server IAS" del capitolo 5 "Creazione dell'infrastruttura di protezione per LAN senza fili".
  
3.  Configurare il punto di accesso in base alle indicazioni fornite nella sezione "Configurazione dei punti di accesso senza fili" del capitolo 5 "Creazione dell'infrastruttura di protezione per LAN senza fili".
  
##### Rimozione di un punto di accesso senza fili
  
In caso di trasferimento o riorganizzazione della rete, può essere necessario rimuovere un punto di accesso senza fili dalla rete. È indispensabile rimuovere sempre da IAS le voci dei client RADIUS che non vengono più utilizzati.
  
**Per rimuovere un punto di accesso senza fili dalla rete**
  
1.  Individuare i server IAS primario e secondario del punto di accesso da rimuovere.
  
2.  Utilizzare la console MMC **Servizio autenticazione Internet** per eliminare la voce del client RADIUS relativo al punto di accesso. (Verificare che l'indirizzo IP del client RADIUS corrisponda all'indirizzo IP del punto di accesso da rimuovere. Evitare di basarsi sul nome del client RADIUS.)
  
3.  Ripetere il passaggio 2 per il server IAS secondario.
  
##### Concedere l'accesso alla rete LAN senza fili a un utente o a un computer
  
Se per questa soluzione è stata eseguita la procedura di installazione predefinita, tutti gli utenti e i computer del dominio in cui sono stati installati i server IAS hanno automaticamente accesso alla rete WLAN, perché i gruppi Domain Users e Domain Computers sono membri rispettivamente del gruppo Utenti LAN senza fili e del gruppo Computer LAN senza fili. Questi gruppi sono, a loro volta, membri del gruppo Accesso LAN senza fili, che viene utilizzato dal criterio di accesso remoto di IAS per concedere l'accesso alla rete WLAN.
  
###### Controllo dell'accesso per membri dello stesso dominio
  
Se si desidera definire in modo esplicito quali utenti e computer possono connettersi alla rete WLAN, è necessario servirsi dei gruppi di protezione. Rimuovere i gruppi Domain Users e Domain Computers rispettivamente dal gruppo Utenti LAN senza fili e dal gruppo Computer LAN senza fili. Al loro posto aggiungere gli utenti e i computer che devono poter accedere alla rete WLAN.
  
In questo modo si modifica la configurazione predefinita della soluzione e alla rete WLAN potranno accedere solo coloro a cui viene concesso l'accesso esplicitamente aggiungendoli a un gruppo di protezione. Questa strategia è più prudente rispetto a quella che consente l'accesso per impostazione predefinita, e di norma è preferibile per le organizzazioni che hanno bisogno di livelli di protezione alti. Potrebbe essere utile anche nelle situazioni in cui l'accesso alla rete WLAN deve essere consentito solo a un numero limitato di persone, ad esempio durante la fase pilota di un progetto di implementazione.
  
**Per consentire l'accesso alla rete LAN senza fili a un utente o a un computer dello stesso dominio**
  
1.  Mediante **Utenti e computer di Active Directory**, aggiungere l'account dell'utente o del computer al gruppo Utenti LAN senza fili o Computer LAN senza fili.
  
2.  Se si deve aggiungere un utente, chiedere all'utente di disconnettersi e riconnettersi. Se si deve aggiungere un computer, riavviare il computer.
  
3.  Verificare che l'utente o il computer possa accedere alla rete WLAN.
  
###### Controllo dell'accesso per membri di un altro dominio
  
In presenza di un insieme di strutture con più domini, può essere necessario consentire a utenti e computer degli altri domini di utilizzare la rete WLAN. A questo proposito è necessario accedere utilizzando un account che sia:
  
-   Un amministratore di entrambi i domini oppure
  
-   Un account che abbia le autorizzazioni necessarie per creare gruppi negli altri domini e per modificare i membri del gruppo Accesso LAN senza fili nel dominio di origine, cioè nel dominio in cui sono installati i server IAS.
  
**Per consentire l'accesso alla rete LAN senza fili a utenti e computer di altri domini**
  
1.  Accedere con un account che abbia le autorizzazioni per creare gruppi nel dominio degli utenti e dei computer che devono poter accedere alla rete WLAN (dominio di destinazione).
  
2.  Aprire **Utenti e computer di Active Directory** e individuare un controller di dominio per il dominio di destinazione.
  
3.  Creare un gruppo globale di dominio denominato Utenti LAN senza fili nel dominio di destinazione.
  
4.  Creare un gruppo globale di dominio denominato Computer LAN senza fili nel dominio di destinazione.
  
5.  Accedere con un account che abbia le autorizzazioni per modificare i membri del gruppo Accesso LAN senza fili nel dominio di origine. Mediante **Utenti e computer di Active Directory**, individuare il gruppo Accesso LAN senza fili e aprirlo per modificarne le proprietà. Nella scheda **Appartenenza** della finestra delle proprietà del gruppo, aggiungere a questo gruppo i gruppi Utenti LAN senza fili e Computer LAN senza fili del dominio di destinazione.
  
6.  Individuare gli utenti del dominio di destinazione che devono poter accedere alla rete WLAN. Aggiungere i rispettivi account al gruppo Utenti LAN senza fili in tale dominio. Analogamente aggiungere al gruppo Computer LAN senza fili gli account computer desiderati del dominio di destinazione. In alternativa, per consentire a tutti i membri del dominio di destinazione di accedere alla rete WLAN, aggiungere i gruppi Domain Users e Domain Computers a questi gruppi.
  
##### Impedire l'accesso alla rete LAN senza fili a un utente o a un computer
  
Per impostazione predefinita, in questa soluzione viene concesso l'accesso alla rete WLAN a tutti gli utenti e a tutti i computer del dominio in cui sono stati installati i server IAS. L'accesso viene concesso loro automaticamente, perché sono membri rispettivamente del gruppo Domain Users e del gruppo Domain Computers. Questo può rappresentare un problema se occorre impedire a singoli utenti o computer di accedere alla rete WLAN. In questo caso, bisogna evitare di rimuovere utenti o computer dai gruppi predefiniti Domain Users e Domain Computers e occorre procedere in uno dei seguenti modi:
  
-   Se l'utente ha lasciato l'organizzazione (oppure, nel caso di un computer, se questo è stato perso o rubato), è possibile disattivare il relativo account in Active Directory.
  
-   Consentire o impedire l'accesso avvalendosi delle autorizzazioni di accesso remoto per l'oggetto account utente o computer. Questa procedura è descritta brevemente nella sezione "Allowing Users and Computers to Access the WLAN" del capitolo 6 "Configurazione dei client delle reti LAN senza fili".
  
-   Se si desidera impedire a un utente o a un computer di accedere alla rete WLAN, lasciando tuttavia che l'account possa essere utilizzato per il normale accesso al dominio e per altri tipi di accesso alla rete, è necessario utilizzare un modello di accesso alla rete LAN senza fili selettivo oppure implementare un criterio per negare l'accesso remoto. Per decidere è necessario valutare se si desidera consentire l'accesso alla rete WLAN per impostazione predefinita oppure se si desidera negare tale accesso per impostazione predefinita e consentirlo solo a utenti specifici.
  
    -   L'impiego dell'appartenenza a gruppi specifici per implementare un criterio di accesso selettivo è stato descritto più indietro in questo capitolo, nella sezione "Concedere l'accesso alla rete LAN senza fili a un utente o a un computer". È possibile negare l'accesso alla rete WLAN semplicemente rimuovendo un utente o un computer dal rispettivo gruppo di protezione.
  
    -   La procedura per creare un criterio di accesso remoto IAS per negare l'accesso ai gruppi selezionati è descritta nella prossima sezione "Controllo dell'accesso alla rete LAN senza fili mediante un criterio di tipo Nega".
  
        **Importante:** evitare di rimuovere utenti e computer rispettivamente dai gruppi Domain Users e Domain Computers. Sebbene sia tecnicamente possibile farlo, si comprometterebbe il normale utilizzo dell'account utente o computer nel dominio.
  
###### Controllo dell'accesso alla rete LAN senza fili mediante un criterio di tipo Nega
  
Se si desidera consentire l'accesso per impostazione predefinita ma al tempo stesso poterlo negare a singoli utenti e computer, è necessario creare un criterio di accesso remoto di tipo "Nega" in IAS.
  
**Per creare un criterio di accesso remoto di tipo Nega**
  
1.  In **Utenti e computer di Active Directory**, creare un gruppo universale denominato Nega accesso LAN senza fili.
  
2.  Creare i gruppi globali di dominio Utenti Nega accesso LAN senza fili e Computer Nega accesso LAN senza fili, quindi aggiungerli come membri del gruppo Nega accesso LAN senza fili.
  
3.  Accedere al server IAS master utilizzato per modificare le impostazioni IAS globali (queste impostazioni verranno replicate negli altri server IAS).
  
4.  Nella console MMC **Servizio autenticazione Internet** fare clic con il pulsante destro del mouse sulla cartella **Criteri di accesso remoto** e scegliere **Nuovi Criteri di accesso remoto**.
  
5.  Selezionare **Imposta un criterio personalizzato** e digitare **Nega accesso LAN senza fili** come nome del criterio. Scegliere **Avanti** per continuare.
  
6.  Fare clic su **Aggiungi** per aggiungere una condizione per il criterio, selezionare **Gruppi di Windows** dall'elenco e fare clic su **Aggiungi**.
  
7.  Fare clic su **Aggiungi** per aggiungere un gruppo di protezione. Digitare o selezionare il gruppo Nega accesso LAN senza fili e scegliere **OK**.
  
8.  Fare clic su **Aggiungi** per aggiungere un'altra condizione per il criterio, selezionare **Tipo-porta-NAS** dall'elenco e fare clic su **Aggiungi**.
  
9.  Dall'elenco **Tipi disponibili** selezionare **Senza fili - IEEE 802.11** e fare clic su **Aggiungi**. Selezionare, quindi, **Wireless - Altro** e fare clic su **Aggiungi** per aggiungerli all'elenco **Tipi selezionati**. Scegliere **OK**, quindi scegliere **Avanti** per continuare.
  
10. Selezionare **Non consentire l'accesso remoto** e scegliere **Avanti** per continuare.
  
11. Nella finestra **Profilo** scegliere **Avanti**, quindi scegliere **Fine**.
  
12. Il criterio **Nega accesso LAN senza fili** verrà a trovarsi all'inizio dell'elenco dei criteri(priorità maggiore) o per lo meno prima del criterio Consenti accesso LAN senza fili. Se non è così, fare clic con il pulsante destro del mouse sul nome del criterio, quindi scegliere **Sposta su** finché il criterio non viene a trovarsi prima del criterio **Consenti accesso LAN senza fili**.
  
13. Mediante le procedure descritte in precedenza, replicare le nuove impostazioni negli altri server IAS dell'organizzazione.
  
Agli utenti o ai computer aggiunti ai gruppi Utenti Nega accesso LAN senza fili o Computer Nega accesso LAN senza fili non verrà consentito di accedere alla rete WLAN. Questa impostazione, tuttavia, ha effetto solo dopo il successivo accesso dell'utente o solo dopo il riavvio del computer.
  
#### Attività di supporto
  
In questa sezione vengono descritte le attività da eseguire per la risoluzione dei problemi comuni dell'infrastruttura per la protezione della rete LAN senza fili. Molte di queste attività verranno citate nella sezione "Risoluzione dei problemi" di questo capitolo.
  
##### Ripristino da backup della configurazione di un server IAS
  
I criteri e le impostazioni di IAS sono memorizzati nel database di configurazione di IAS e possono essere ripristinati in modo indipendente dal resto delle impostazioni del sistema. È opportuno pianificare l'operazione di backup di IAS in modo che il backup delle impostazioni di IAS venga eseguito nella cartella C:\\IASBackup ogni notte. Per ulteriori informazioni, vedere la procedura "Configurazione del backup di IAS" nella sezione "Attività operative" di questo capitolo. Se occorre annullare le modifiche effettuate durante la giornata, è possibile ripristinare le impostazioni dai file di backup (in C:\\IASBackup) creati la notte precedente o dal backup di "rollback" effettuato prima di apportare le modifiche. Per ulteriori informazioni, vedere la procedura "Backup delle impostazioni di IAS prima di apportare modifiche" nella sezione "Gestione delle modifiche".
  
Se occorre ripristinare una versione precedente delle impostazioni, è necessario recuperare le impostazioni di IAS esportate dal backup del server.
  
**Avviso:** con questa procedura vengono ripristinate tutte le impostazioni di IAS, compresi i client RADIUS, e vengono sovrascritte tutte le impostazioni esistenti nel server. Il backup da utilizzare per il ripristino deve essere un backup effettuato sullo stesso server.
  
**Per ripristinare le impostazioni di IAS**
  
1.  Se i file di backup delle impostazioni di IAS che si desidera utilizzare non sono presenti nel server, è necessario ripristinarli dai supporti di backup. Selezionare solo i file della cartella IASBackup da ripristinare. Non ripristinare lo stato del sistema, a meno che non si desideri ripristinare anche precedenti impostazioni di sistema.
  
2.  Utilizzare il collegamento **MSS WLAN Tools** per aprire una shell comandi. Ripristinare la configurazione di IAS specificando il seguente comando:
  
    **msstools RestoreIAS /path:C:\\IASBackup**
  
3.  Per verificare che le impostazioni di IAS siano state ripristinate, aprire la console di gestione di IAS e controllare le cartelle Client RADIUS e Criteri di accesso remoto.
  
Se, per qualche motivo, non è disponibile un backup del sistema utilizzabile, è possibile esportare le impostazioni da un altro server IAS e importarle nel server in questione. Di norma, i server IAS con lo stesso ruolo hanno impostazioni di configurazione uguali ma una serie di client RADIUS diversi, quindi questa procedura non deve essere utilizzata per ripristinare le impostazioni da un altro server. Utilizzare, invece, la procedura "Replica delle impostazioni dal primo server IAS" descritta nel capitolo 5 "Creazione dell'infrastruttura di protezione per LAN senza fili".
  
**Importante:** è necessario verificare che al sistema ripristinato siano applicate le patch più recenti. A seguito del ripristino da un backup, infatti, potrebbero venire rimosse eventuali patch che erano state precedentemente applicate.
  
##### Ripristino da backup della configurazione completa del server
  
Le procedure per il ripristino del server variano a seconda del tipo di sistema di backup in uso. Per la procedura descritta di seguito si presuppone che sia stato effettuato un backup su file dello stato del sistema Windows, seguito da un backup su file di questo file e di altri file necessari.
  
**Per ripristinare il server**
  
1.  A seconda dello stato del server, può essere necessario predisporre il server partendo da zero, ad esempio nel caso in cui un problema hardware abbia distrutto i dischi del sistema. Altrimenti è possibile effettuare il ripristino direttamente nel server, senza dover reinstallare il sistema operativo.
  
2.  Se si utilizzano due backup diversi, uno dello stato del sistema e uno dei file, utilizzare il software di backup per ripristinare nel server il file di backup dello stato del sistema e il file di backup delle impostazioni di IAS. Le impostazioni di IAS devono essere ripristinate nello stesso percorso, cioè C:\\IASBackup.
  
3.  Eseguire l'utilità di backup di Windows e selezionare il file di backup dello stato del sistema ripristinato. È necessario essere membro di un gruppo che dispone delle autorizzazioni di backup e ripristino sul server (ad esempio Backup Operators o Administrators).
  
4.  Fare clic su **Ripristina**.
  
5.  Riavviare il sistema.
  
6.  Verificare che tutto funzioni come previsto e che Active Directory e Servizi certificati, se installati, siano stati avviati senza errori.
  
7.  Utilizzare il collegamento **MSS WLAN Tools**per aprire una shell comandi. Ripristinare la configurazione di IAS specificando il seguente comando:
  
    **MSSTools RestoreIAS /path:C:\\IASBackup**
  
8.  Per verificare che le impostazioni di IAS siano state ripristinate, aprire la console di gestione di IAS e controllare le cartelle Client RADIUS e Criteri di accesso remoto.
  
    **Importante:** se IAS è in esecuzione in un controller di dominio, ripristinando un backup dello stato del sistema si ripristina in tale server anche la versione sottoposta a backup del database di Active Directory. Tuttavia, le modifiche eventualmente apportate ad Active Directory dopo il backup verranno replicate nel server ripristinato al successivo ciclo di replica di Active Directory.
  
#### Attività di ottimizzazione
  
In questa sezione vengono descritte le attività da svolgere per ottimizzare l'esecuzione dell'infrastruttura IAS.
  
##### Determinazione del carico massimo sul server IAS
  
In questa sezione vengono fornite informazioni sul carico massimo probabile del server IAS.
  
Raramente le prestazioni costituiscono un problema per i server IAS che sono stati dimensionati e configurati correttamente. I server IAS sono soggetti a un carico maggiore durante le ore di punta, ad esempio al mattino, quando un numero molto alto di utenti accede contemporaneamente, subito dopo un'interruzione di rete importante o durante un errore del server RADIUS nel failover dei punti di accesso senza fili al server di backup.
  
Nella tabella seguente sono riportati i requisiti per l'autenticazione WLAN in organizzazioni di varie dimensioni.
  
**Tabella 8.7: Requisiti per l'autenticazione WLAN**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Numero utenti WLAN</th>
<th style="border:1px solid black;" >Nuove autenticazioni al secondo</th>
<th style="border:1px solid black;" >Numero massimo nuove autenticazioni al secondo</th>
<th style="border:1px solid black;" >Riautenticazioni al secondo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">100</td>
<td style="border:1px solid black;">&gt; 0,1</td>
<td style="border:1px solid black;">0,1</td>
<td style="border:1px solid black;">0,1</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">1000</td>
<td style="border:1px solid black;">0,1</td>
<td style="border:1px solid black;">0,6</td>
<td style="border:1px solid black;">1,1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">10.000</td>
<td style="border:1px solid black;">1,4</td>
<td style="border:1px solid black;">5,6</td>
<td style="border:1px solid black;">11,1</td>
</tr>
</tbody>
</table>
  
La colonna Nuove autenticazioni al secondo mostra il carico abituale. È possibile presupporre una media di quattro nuove autenticazioni complete a fronte degli spostamenti degli utenti tra i punti di accesso senza fili. La colonna Numero massimo nuove autenticazioni al secondo indica il tipo di carico atteso quando tutti gli utenti richiedono l'autenticazione in un periodo di 30 minuti (ad esempio all'inizio della giornata lavorativa). La colonna Riautenticazioni al secondo mostra il numero di autenticazioni con riconnessione rapida causate dal fatto che IAS impone un timeout della sessione dopo 15 minuti. (Il valore di timeout predefinito per la soluzione è di 60 minuti, tuttavia qui viene utilizzato il valore di 15 minuti per presentare il caso limite.) È opportuno valutare questi dati a fronte dei requisiti della propria organizzazione per determinare il tipo di carico che occorre supportare.
  
Test interni svolti da Microsoft mostrano che IAS è in grado di gestire un carico alto su hardware server con prestazioni modeste. Il carico gestito da IAS è espresso dal numero di autenticazioni EAP (Extensible Authentication Protocol) al secondo. La tabella seguente mostra i risultati di un server IAS in esecuzione su un server Intel Pentium 4 2GHz con Windows Server 2003.
  
I test sono stati condotti con la registrazione RADIUS attivata (in un disco diverso) e con IAS in un server diverso dal controller di dominio di Active Directory. Pertanto questi valori devono essere considerati relativi a un caso limite. La configurazione predefinita per questa soluzione prevede che la registrazione sia disattivata e che IAS si trovi nello stesso server del controller di dominio. Entrambi questi fattori determinano un miglioramento della velocità effettiva di autenticazione.
  
**Nota:** queste informazioni vengono fornite senza alcuna garanzia e devono essere intese come mere linee guida ai fini della pianificazione della capacità e non ai fini di un confronto fra prestazioni.
  
**Tabella 8.8: Valori campione della capacità del server IAS**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Tipo autenticazione</th>
<th style="border:1px solid black;" >Autenticazioni al secondo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nuove autenticazioni PEAP (Protected Extensible Authentication Protocol)</td>
<td style="border:1px solid black;">36</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nuove autenticazioni PEAP con scheda di supporto per la ripartizione del carico TLS/SSL</td>
<td style="border:1px solid black;">50</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autenticazioni con Riconnessione rapida</td>
<td style="border:1px solid black;">166</td>
</tr>
</tbody>
</table>
  
È possibile configurare IAS in modo che generi registri RADIUS basati su disco contenenti quantità variabili di informazioni sulle richieste RADIUS. Se si decide di attivare la registrazione RADIUS, non bisogna sottovalutare il carico di lavoro che ne deriverà per i server, in particolare nei sottosistemi dei dischi. Una bassa velocità effettiva del disco agisce come collo di bottiglia per le prestazioni di IAS e rallenta le risposte RADIUS ai punti di accesso, causando timeout di protocollo e failover non necessario dei punti di accesso su server RADIUS secondari. Se si prevede un carico alto (è possibile fare riferimento ai valori delle tabelle precedenti per elaborare una stima) e si decide di attivare la registrazione RADIUS, è necessario controllare che IAS sia configurato in modo che i registri RADIUS vengano memorizzati in un disco ad alte prestazioni diverso dall'unità di sistema di Windows e dall'unità del file di paging.
  
Un ulteriore carico per i server IAS viene generato se si attivano le funzionalità di analisi di IAS di Windows Server 2003 (come descritto nella sezione "Attivazione e disattivazione dell'analisi nel server IAS" in questo capitolo). Occasionalmente può essere necessario attivare le funzionalità di analisi per risolvere problemi di accesso alla rete, ma è importante disattivarle appena possibile. In ogni caso è consigliabile verificare che nei server IAS siano disponibili risorse extra sufficienti per utilizzare l'analisi per periodi di tempo limitati, senza effetti indesiderati sul carico di produzione.
  
##### Altre misure di ottimizzazione
  
Per ulteriori informazioni sull'ottimizzazione di IAS, vedere la sezione "Designing an Optimized IAS Solution" del capitolo "Deploying IAS" di *Windows Server 2003 Deployment Kit* (in inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Risoluzione dei problemi
  
In questa sezione vengono descritte procedure e tecniche per la diagnosi e la risoluzione di eventuali problemi della soluzione LAN senza fili.
  
#### Procedure per la risoluzione dei problemi
  
Le seguenti procedure consentono di individuare le cause possibili di un problema e di intraprendere le misure correttive opportune. Questa sezione è organizzata in modo gerarchico. La prima procedura, "Individuazione del tipo di problema", indirizza il lettore a una procedura fra quelle disponibili. Ognuna di queste procedure consente di affrontare il problema in modo più specifico. A loro volta, queste procedure possono rimandare a ulteriori procedure, specifiche per i componenti della soluzione.
  
Tutte le procedure verranno descritte in dettaglio più avanti in questo capitolo, alcune in forma grafica, altre mediante tabelle o descrizioni. Per alcune procedure viene fatto riferimento alla sezione "Tecniche e strumenti di risoluzione dei problemi" di questo capitolo. Per poter applicare in modo efficace le procedure per la risoluzione dei problemi, è necessario conoscere il contenuto di tale sezione.
  
**Importante:** queste procedure diagnostiche non coprono tutte le eventualità. Se la procedura consigliata non permette di individuare l'origine del problema, è opportuno tornare sui propri passi e seguire le altre procedure diagnostiche citate. Nei casi in cui la natura o la portata dei sintomi non sia chiara, si corre il rischio di seguire una direzione sbagliata. Ad esempio, può accadere che un solo utente segnali un problema che, in realtà, interessa l'intero ufficio. In questo caso la tabella rimanda a procedure diagnostiche relative a problemi di pertinenza di un solo client, mentre in realtà potrebbero essere più indicate altre procedure.
  
Consultare, inoltre, i documenti per la risoluzione dei problemi delle reti LAN senza fili e di IAS indicati alla fine del capitolo.
  
##### Individuare il tipo di problema
  
In primo luogo, classificare il tipo di problema facendo riferimento al seguente diagramma di flusso. I rombi contengono le domande che l'utente deve porsi e i rettangoli contengono la diagnosi del problema e indicano il nome della procedura da seguire.
  
![](images/Dd536237.PEAP_801(it-it,TechNet.10).gif)
  
**Figura 8.1 Individuare il tipo di problema**
  
##### Diagnostica dei problemi di connessione dei client
  
Nella tabella seguente sono riportati i diversi tipi di problemi di connessione, raggruppati in base al numero e alla posizione dei client interessati. La colonna Possibili problemi indica le cause più probabili dei sintomi. Nella colonna Procedure diagnostiche da eseguire, sono elencate le procedure da provare per prime per diagnosticare il problema. Ognuna di queste procedure è descritta in dettaglio più avanti in questo capitolo.
  
**Tabella 8.9: Chi non riesce a connettersi alla rete LAN senza fili?**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Sintomo</th>
<th style="border:1px solid black;" >Possibili problemi</th>
<th style="border:1px solid black;" >Procedure diagnostiche da seguire</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Un solo client</td>
<td style="border:1px solid black;">Configurazione del computer o account utente/computer.</td>
<td style="border:1px solid black;">Verificare l'account utente/computer
Verificare il computer client</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Diversi client di un sito</td>
<td style="border:1px solid black;">Configurazione errata di uno o più punti di accesso.</td>
<td style="border:1px solid black;">Controllare la configurazione dei punti di accesso senza fili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Intero sito (IAS locale)</td>
<td style="border:1px solid black;">Errata configurazione o malfunzionamento del server IAS in loco; problemi di replica di Active Directory che impediscono al controller di dominio di ricevere le informazioni corrette; malfunzionamento del server IAS più problema a livello di connettività della rete WLAN.</td>
<td style="border:1px solid black;">Controllare Active Directory e i servizi di rete
Controllare IAS
Controllare la connettività WAN</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Intero sito (IAS non in loco)</td>
<td style="border:1px solid black;">Problema di connettività della WLAN; problemi di replica di Active Directory (in presenza di controller di dominio locale).</td>
<td style="border:1px solid black;">Controllare la connettività WAN</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Tutti i client di tutti i siti</td>
<td style="border:1px solid black;">Configurazione a livello di organizzazione (oggetto Criteri di gruppo per le impostazioni dei client), gruppi dei criteri di accesso remoto, problemi di rinnovo dei certificati.</td>
<td style="border:1px solid black;">Controllare Active Directory e i servizi di rete (controlli &quot;Controllare l'oggetto Criteri di gruppo per le impostazioni della rete WLAN&quot; e &quot;Controllare i gruppi di Active Directory&quot;)
Controllare la CA
Controllare IAS</td>
</tr>
</tbody>
</table>
 

##### Diagnostica dei problemi di prestazioni

In questa sezione vengono trattati i problemi di prestazioni associati all'infrastruttura per la protezione della rete LAN senza fili. In questo capitolo non vengono affrontati i problemi generali di prestazioni delle reti senza fili e cablate.

**Tabella 8.10: Problemi di prestazioni**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Sintomo</th>
<th style="border:1px solid black;" >Soluzione possibile</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Ritardo di autenticazione che interessa molti utenti</td>
<td style="border:1px solid black;">Carico pesante del server IAS, controllare Performance Monitor.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Autenticazione su un collegamento WLAN lento (anche se è presente un server IAS locale, controllare che non sia stato eseguito il failover dei punti di accesso sul server IAS remoto).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">I ritardi di un server DHCP (Dynamic Host Configuration Protocol) nel rilascio di un indirizzo IP possono ripercuotersi sul tempo di connessione totale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Ritardo di riautenticazione in caso di roaming tra punti di accesso</td>
<td style="border:1px solid black;">Un ritardo di pochi secondi è normale in caso di spostamento tra punti di accesso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Se un client esce dalla portata di un punto di accesso (e questa condizione dura più di 10 secondi), possono trascorrere fino a 60 secondi prima che venga avviata la riautenticazione dopo che il client viene a trovarsi di nuovo a portata di un punto di accesso. Questo succede perché il client WLAN Windows, quando è disconnesso da una WLAN, esegue il polling delle WLAN ogni 60 secondi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Velocità effettiva della rete WLAN bassa</td>
<td style="border:1px solid black;">Questo sintomo può essere causato dal fatto che troppi client usano un numero eccessivamente ridotto di punti di accesso, dalla posizione non corretta dei punti di accesso, da un segnale radio debole a causa di ostruzioni o dalla distanza eccessiva.
Tutti questi sono aspetti della progettazione della rete WLAN ed esulano dall'ambito di questa documentazione. Per informazioni, rivolgersi al proprio fornitore.
Per ulteriori informazioni, vedere il capitolo &quot;Deploying a Wireless LAN&quot; di <em>Windows Server 2003 Deployment Kit</em> (in inglese).</td>
</tr>
</tbody>
</table>
 

##### Autenticazione dell'utente ed errore di autenticazione del computer

In questa soluzione vengono utilizzate sia l'autenticazione dell'utente che l'autenticazione del computer per la rete WLAN. Per effettuare l'autenticazione per la rete WLAN quando nessun utente è connesso al computer, vengono utilizzate le credenziali di dominio del computer. Quando un utente esegue l'accesso, vengono utilizzate le credenziali dell'utente per la riautenticazione per la rete WLAN. In questo modo il computer può comunicare con la rete WLAN quando nessun utente è connesso e può essere gestito in remoto, per scaricare le impostazioni dell'oggetto Criteri di gruppo del server e così via.

Quando un utente accede a un computer della rete WLAN, si verifica un lieve ritardo causato dall'autenticazione dell'utente nella rete WLAN. Finché l'utente non riceve l'autorizzazione per la connessione, la sessione WLAN autenticata del computer rimane attiva. Se, tuttavia, il computer non era stato autenticato nella WLAN, questo ritardo significa che non vi è connettività di rete all'inizio della sessione di accesso dell'utente.

Questo può causare una serie di problemi non immediatamente palesi. Ad esempio, non vengono caricati i profili utente comuni, non vengono applicate alcuni impostazioni dell'oggetto Criteri di gruppo del computer e non vengono eseguiti gli script di accesso degli utenti e le distribuzioni software basate su oggetti Criteri di gruppo (che vengono eseguite molto presto nel processo di accesso).

Per determinare la causa della mancata autenticazione del computer, eseguire la procedura "Verificare l'account utente/computer" più avanti in questa guida.

##### Autenticazione del computer ed errore di autenticazione dell'utente

A differenza del caso precedente, questo problema è ovvio e viene segnalato subito dagli utenti interessati. Per determinare la causa della mancata autenticazione dell'utente, eseguire la procedura "Verificare l'account utente/computer".

##### Procedure diagnostiche

Nella sezione seguente vengono descritte in dettaglio le procedure per la risoluzione dei problemi citate nelle sezioni precedenti.

###### Verificare l'account utente/computer

Il seguente diagramma di flusso consente di diagnosticare la causa di un errore di autenticazione di un utente o di un computer.

**Nota:** la casella a forma di freccia nel diagramma di flusso indica che bisogna fare riferimento alla procedura "Verificare il computer client", come specificato nella casella.

[![](images/Dd536237.PEAP_802(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536237.peap_802_big(it-it,technet.10).gif)

**Figura 8.2 Verifica dell'account utente o computer**

###### Verificare il computer client

Il seguente diagramma di flusso consente di diagnosticare i problemi del computer client.

[![](images/Dd536237.PEAP_803(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536237.peap_803_big(it-it,technet.10).gif)

**Figura 8.3 Verifica del computer client**

**Nota:** la casella a forma di freccia nel diagramma di flusso indica che si prosegue dalla procedura "Verificare l'account utente/computer".

Lo stato della scheda WLAN (richiesto nel passaggio "Disattivare e attivare la scheda WLAN e osservare lo stato" illustrato nel diagramma di flusso) può essere visualizzato nel riquadro **Dettagli** della cartella Connessioni di rete (nel **Pannello di controllo**). Durante l'attivazione della scheda vengono visualizzati i seguenti stati:

-   Connessione in corso

-   Autenticazione in corso

-   Acquisizione dell'indirizzo IP (a meno che non venga assegnato automaticamente)

Una delle procedure diagnostiche più efficaci consiste nel monitorare il punto in cui si verifica il problema.

###### Controllare IAS

Nella seguente tabelle è elencata una serie di controlli da eseguire qualora si sospetti che un server IAS stia causando problemi.

**Tabella 8.11: Controlli diagnostici per IAS**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Controllo</th>
<th style="border:1px solid black;" >Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IAS è in esecuzione</td>
<td style="border:1px solid black;">Aprire la MMC <strong>Gestione computer</strong> e passare a <strong>Servizi</strong>. Verificare che IAS sia in esecuzione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configurazione di rete di base di IAS</td>
<td style="border:1px solid black;">Eseguire il comando <strong>netdiag</strong> per controllare se vi sono errori nella configurazione di rete del server IAS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Al server IAS è associato un certificato server corrente</td>
<td style="border:1px solid black;">Aprire la console MMC <strong>Certificati</strong> e osservare la cartella \Certificati (computer locale)\Personali\Certificati. Questa cartella dovrebbe contenere un certificato per il server con le seguenti caratteristiche:
-La data corrente rientra nel periodo di validità del certificato.
-Il nome alternativo soggetto corrisponde al nome DNS (Domain Name System) del server.
-L'utilizzo avanzato chiavi deve contemplare l'autenticazione server
-L'autorità emittente è attendibile (nella scheda <strong>Trust Path</strong>).
-Il certificato non è stato revocato.
Visualizzare le impostazioni del profilo del criterio di accesso remoto IAS, fare clic sulla scheda <strong>Autenticazione</strong> e visualizzare le impostazioni per 802.1X. Dovrebbe essere selezionato il certificato server sopra descritto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IAS appartiene al gruppo Server RAS e IAS nel dominio</td>
<td style="border:1px solid black;">Il server deve appartenere a questo gruppo (normalmente vi viene aggiunto quando IAS viene registrato in Active Directory).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criterio di accesso remoto IAS o criterio di richiesta di connessione non corretto</td>
<td style="border:1px solid black;">Verificare che le impostazioni del criterio (e il numero di versione, se è stato incluso) siano quelle attese. In caso di dubbi, distribuire di nuovo la configurazione dal server IAS &quot;master&quot;.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Visualizzare gli eventi di IAS nel registro eventi del sistema</td>
<td style="border:1px solid black;">Cercare gli eventi relativi a errori o avvisi di IAS nel registro eventi del sistema. Agli errori di autenticazione è associato un codice che indica la causa del problema.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Attivazione dell'analisi sul server IAS</td>
<td style="border:1px solid black;">Vedere la procedura &quot;Attivazione e disattivazione dell'analisi sul server IAS&quot; nella sezione &quot;Tecniche e strumenti di risoluzione dei problemi&quot; più avanti in questo capitolo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Attivazione dell'analisi sul client</td>
<td style="border:1px solid black;">Vedere la procedura &quot;Attivazione e disattivazione dell'analisi sui computer client&quot; nella sezione &quot;Tecniche e strumenti di risoluzione dei problemi&quot; più avanti in questo capitolo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Attivazione della registrazione SChannel</td>
<td style="border:1px solid black;">Per diagnosticare i problemi relativi ai certificati e TLS, attivare la registrazione SChannel. Per ulteriori informazioni, vedere la procedura &quot;Attivazione della registrazione SChannel sul server IAS&quot; nella sezione &quot;Tecniche e strumenti di risoluzione dei problemi&quot; più avanti in questo capitolo. È possibile, inoltre, attivare la registrazione SChannel sul client per acquisire ulteriori informazioni diagnostiche sul lato client.</td>
</tr>
</tbody>
</table>
  
###### Controllare l'Autorità di certificazione
  
Nella tabella seguente sono indicati i controlli che è possibile eseguire per determinare se la CA funziona in modo corretto.
  
**Tabella 8.12: Controlli diagnostici per la CA**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Controllo</th>
<th style="border:1px solid black;" >Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Servizi certificati è in esecuzione</td>
<td style="border:1px solid black;">Aprire la MMC <strong>Gestione computer</strong> e passare a <strong>Servizi</strong>. Verificare che Servizi certificati sia in esecuzione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">In presenza di errori di TLS (evidenziati nel registro di analisi di RASTLS o dalla registrazione SChannel) oppure se la CA non emette certificati, controllare l'elenco CRL.</td>
<td style="border:1px solid black;">Eseguire il comando <strong>msstools CheckCA</strong> sulla CA per controllare che sia pubblicato e accessibile un elenco CRL corrente.
In caso di problemi in server IAS particolari (o in siti particolari), procurarsi lo strumento Integrità PKI (disponibile nel <em>Windows Server 2003 Resource Kit</em>). Si tratta di uno strumento MMC che mostra se il server ha problemi ad accedere a un elenco CRL o a un certificato della CA corrente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Se non sono stati registrati o rinnovati certificati, controllare l'oggetto Criteri di gruppo per la registrazione automatica dei certificati.</td>
<td style="border:1px solid black;">-Controllare che l'oggetto Criteri di gruppo per la registrazione automatica sia collegato alla posizione corretta (di norma il dominio).
-Controllare che per l'oggetto Criteri di gruppo sia impostato il modello &quot;Computer&quot; come tipo di certificato da registrare (in Configurazione computer\Impostazioni di Windows\Impostazioni protezione\Criteri chiave pubblica\Impostazioni richiesta automatica certificati<strong>)</strong>.
-Controllare che il gruppo Server RAS e IAS abbia le autorizzazioni per l'<strong>applicazione dei criteri e la lettura</strong> per l'oggetto Criteri di gruppo e controllare che non vengano annullate da eventuali autorizzazioni di tipo Nega (ad esempio Utenti autenticati-Nega lettura).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modelli di certificato</td>
<td style="border:1px solid black;">Il modello Computer deve essere assegnato alla CA (osservare la cartella Modelli nella console MMC <strong>Autorità di certificazione</strong>).
Il modello Computer deve avere l'<strong>autorizzazione Registra per il gruppo Server RAS e IAS</strong> (controllare che questa autorizzazione non venga annullata da autorizzazioni di tipo Nega).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Interfaccia DCOM CA in remoto</td>
<td style="border:1px solid black;">Eseguire il seguente comando da un server IAS remoto per controllare che DCOM/RPC funzioni tra il server e la CA:
<strong>certutil -ping-config</strong> <em>NomeHostCA</em><strong>\</strong><em>NomeCA</em>
dove <em>NomeHostCA</em> è il nome computer del server della CA e
<em>NomeCA</em> è il nome descrittivo assegnato alla CA in fase di installazione (è il nome che compare accanto a <strong>Rilasciato da</strong> nella scheda <strong>Generale</strong> dei certificati rilasciati da questa CA).</td>
</tr>
</tbody>
</table>
 

###### Controllare Active Directory e i servizi di rete

Nella tabella seguente sono elencati i controlli da eseguire su Active Directory e altri componenti della rete per verificare se funzionano in modo corretto.

**Tabella 8.13: Controlli diagnostici per Active Directory**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Controllo</th>
<th style="border:1px solid black;" >Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Controllare le comunicazioni con Active Directory da IAS</td>
<td style="border:1px solid black;">Eseguire il comando <strong>netdiag /test:ldap /test:trust</strong> nel server IAS. Questo comando consente anche di verificare se vi sono problemi a livello di DNS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllare i gruppi di protezione della rete WLAN</td>
<td style="border:1px solid black;">Controllare i membri dei gruppi di protezione utilizzati in questa soluzione per controllare l'accesso alla rete WLAN. I membri predefiniti sono indicati nella sezione &quot;Creazione di gruppi di protezione&quot; del capitolo 3 &quot;Predisposizione dell'ambiente&quot;.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controllare l'oggetto Criteri di gruppo delle impostazioni WLAN per i client</td>
<td style="border:1px solid black;">Controllare che le impostazioni dell'oggetto Criteri di gruppo per le impostazioni WLAN siano corrette, che l'oggetto sia collegato all'unità operativa o al dominio corretto e che vi siano state applicate le autorizzazioni corrette. (Vedere la sezione &quot;Creating the WLAN Settings GPO&quot; del capitolo 6 &quot;Configurazione dei client delle reti LAN senza fili&quot;.)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllare che la replica di Active Directory funzioni in modo corretto</td>
<td style="border:1px solid black;">Eseguire il comando <strong>dcdiag /test:replications</strong> dal server IAS in cui si verificano i problemi. (Anche se IAS non viene eseguito in un controller di dominio, lo strumento dcdiag è in grado di controllare il controller di dominio utilizzato da tale istanza di IAS.)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controllare il server DHCP</td>
<td style="border:1px solid black;">Controllare che il server DHCP sia in esecuzione, che per i client della rete WLAN sia stato creato un ambito valido e che sia attivo e che vi sia connettività tra i punti di accesso senza fili e il server DHCP (più precisamente, deve esserci connettività tra la rete locale virtuale (VLAN) predefinita dei punti di accesso e il server DHCP, in modo che i client della rete WLAN possano acquisire un lease IP).</td>
</tr>
</tbody>
</table>
  
###### Controllare la configurazione dei punti di accesso senza fili
  
Nella tabella seguente sono elencati i controlli da eseguire sui punti di accesso senza fili per verificare se funzionano in modo corretto.
  
**Tabella 8.14: Controlli diagnostici per i punti di accesso senza fili**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Controllo</th>
<th style="border:1px solid black;" >Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Controllare la configurazione IP dei punti di accesso e la connettività con IAS</td>
<td style="border:1px solid black;">Molti punti di accesso dispongono di una funzionalità per il testing della connettività (ad esempio ping). Provare a effettuare il ping dei server IAS primario e secondario (oppure effettuare il ping del punto di accesso dai server IAS primario e secondario).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllare le impostazioni RADIUS del punto di accesso</td>
<td style="border:1px solid black;">Controllare l'indirizzo IP e le impostazioni delle porte configurate nel punto di accesso per i server RADIUS primario e secondario. Verificare che corrispondano alla configurazione nei server IAS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controllare la voce del client RADIUS nel server o nei server IAS</td>
<td style="border:1px solid black;">Verificare che per il punto di accesso in questione esista una voce client RADIUS nei server IAS primario e secondario. IAS registra un errore nel registro di sistema se riceve una richiesta RADIUS da un dispositivo che non è configurato come client.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllare il segreto del client RADIUS</td>
<td style="border:1px solid black;">Può essere difficile verificare a vista il segreto del client RADIUS, perché talvolta non è possibile visualizzarlo dopo che è stato immesso nel punto di accesso. Se il valore configurato nella voce del client RADIUS nel server IAS è diverso da quello configurato nel punto di accesso, IAS registra un errore nel registro eventi di sistema.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controllare la revisione firmware del punto di accesso</td>
<td style="border:1px solid black;">Verificare che il firmware del punto di accesso sia aggiornato. Controllare se sono disponibili aggiornamenti nel sito Web.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllare il server DHCP</td>
<td style="border:1px solid black;">Controllare che il server DHCP sia in esecuzione, che per i client della rete WLAN sia stato creato un ambito valido e che sia attivo e che vi sia connettività tra i punti di accesso senza fili e il server DHCP (più precisamente, deve esserci connettività tra la VLAN predefinita dei punti di accesso e il server DHCP in modo che i client della rete WLAN possano acquisire un lease IP).</td>
</tr>
</tbody>
</table>
  
###### Controllare la connettività WAN
  
I problemi delle reti WLAN possono essere causati da problemi di connettività tra componenti diversi. Nella tabella seguente sono elencati gli elementi che potrebbero dare origine a problemi.
  
**Tabella 8.15: Controlli diagnostici per la rete WAN**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Controllo</th>
<th style="border:1px solid black;" >Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione dei punti di accesso senza fili su server IAS remoti</td>
<td style="border:1px solid black;">Testare la connettività tra il punto di accesso e i server IAS primario e secondario. Nella maggior parte dei punti di accesso è disponibile un semplice comando <strong>ping</strong> o <strong>traceroute</strong>.
In presenza di firewall o router che filtrano il traffico tra i siti in questione, è necessario verificare che il traffico per l'accounting e l'autenticazione RADIUS sia autorizzato (richieste più risposte sulle porte UDP (User Datagram Protocol) 1812 e 1813).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controller di dominio che replicano su una rete WAN</td>
<td style="border:1px solid black;">Possono verificarsi problemi di replica tra i controller di dominio anche in presenza della connettività IP di base. Una latenza eccessiva può causare problemi a livello di comunicazioni RPC tra i controller di dominio. Verificare questa ipotesi utilizzando lo strumento dcdiag come descritto nella sezione &quot;Controllare Active Directory e i servizi di rete&quot; più indietro in questo capitolo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Client della rete WLAN e server DHCP</td>
<td style="border:1px solid black;">Se il server DHCP non si trova nella stessa rete LAN dei punti di accesso e dei client della WLAN autenticati, è necessario configurare un agente di inoltro BOOTP/DHCP per l'inoltro delle richieste al server DHCP corretto sulla rete remota.</td>
</tr>
</tbody>
</table>
  
#### Tecniche e strumenti di risoluzione dei problemi
  
In questa sezione vengono descritte alcune tecniche e alcuni strumenti utili per la risoluzione dei problemi.
  
##### Verifica dello stato della cartella Connessioni di rete dei client
  
La cartella Connessioni di rete e le icone nell'area di notifica di Windows XP forniscono informazioni sullo stato dell'autenticazione nella rete WLAN.
  
Nella cartella Connessioni di rete (del **Pannello di controllo**), il testo sotto la scheda di rete senza fili descrive lo stato corrente della connessione. Se si evidenzia la scheda, vengono visualizzate ulteriori informazioni sulla connessione nel riquadro **Dettagli** della cartella Connessioni di rete. Se si disattiva e riattiva la scheda, viene visualizzato lo stato della scheda mentre viene eseguito il processo di connessione alla WLAN e di autenticazione. Queste informazioni possono essere utili per la risoluzione dei problemi di connessione dei client.
  
Fare clic con il pulsante destro del mouse sull'icona della scheda e scegliere **Stato** per vedere l'intensità del segnale della rete WLAN (nella scheda **Generale**) e i dettagli sull'indirizzo IP (nella scheda **Supporto**).
  
##### Visualizzazione degli eventi di autenticazione IAS nel Registro eventi
  
Gli eventi relativi all'avvenuta o mancata autenticazione dei client vengono registrati nel registro eventi di sistema nei server IAS e possono dimostrarsi utili per la risoluzione dei problemi. Per impostazione predefinita, è attivata la registrazione per le richieste di autenticazione riuscite e non riuscite. Questa impostazione può essere modificata nella scheda **Servizio** della finestra delle proprietà del server IAS nella console MMC **Servizio autenticazione Internet**.
  
Osservare questi eventi può essere utile per risolvere i problemi di autenticazione. I tipi di evento generati da IAS sono elencati nella tabella seguente.
  
**Tabella 8.16: Eventi IAS per le richieste di autenticazione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Evento IAS</th>
<th style="border:1px solid black;" >Significato</th>
<th style="border:1px solid black;" >Categoria evento</th>
<th style="border:1px solid black;" >Origine evento</th>
<th style="border:1px solid black;" >ID evento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Accesso concesso</td>
<td style="border:1px solid black;">Un utente o un computer è stato autenticato ed è stato concesso l'accesso alla rete WLAN.</td>
<td style="border:1px solid black;">Informazioni</td>
<td style="border:1px solid black;">IAS</td>
<td style="border:1px solid black;">1</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso negato</td>
<td style="border:1px solid black;">Un tentativo di accesso è stato respinto (il motivo è indicato nel testo dell'evento).</td>
<td style="border:1px solid black;">Attenzione</td>
<td style="border:1px solid black;">IAS</td>
<td style="border:1px solid black;">2</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Rifiutata</td>
<td style="border:1px solid black;">La richiesta di accesso è stata rifiutata perché scaduta.</td>
<td style="border:1px solid black;">Errore</td>
<td style="border:1px solid black;">IAS</td>
<td style="border:1px solid black;">3</td>
</tr>
</tbody>
</table>
  
Ogni evento contiene informazioni dettagliate sulla richiesta di autenticazione, fra cui:
  
-   Nome del client
  
-   Indirizzo IP e identificatore del punto di accesso
  
-   Tipo di client (deve essere "Wireless-IEEE 802.11")
  
-   Nome del criterio di accesso remoto
  
-   Tipo EAP e autenticazione
  
-   Codice e descrizione del motivo
  
Se l'autenticazione non va a buon fine, spesso è possibile risalire al problema grazie al codice e alla descrizione del motivo (sebbene il motivo indicato possa essere, talvolta, fuorviante o ambiguo). Nella tabella seguente sono indicati i codici dei motivi.
  
**Tabella 8.17: Codici dei motivi negli eventi IAS relativi alle richieste di autenticazione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Codice motivo</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">00</td>
<td style="border:1px solid black;">Operazione riuscita</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">01</td>
<td style="border:1px solid black;">Errore interno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">02</td>
<td style="border:1px solid black;">Accesso negato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">03</td>
<td style="border:1px solid black;">Richiesta non corretta</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">04</td>
<td style="border:1px solid black;">Catalogo globale non disponibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">05</td>
<td style="border:1px solid black;">Dominio non disponibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">06</td>
<td style="border:1px solid black;">Server non disponibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">07</td>
<td style="border:1px solid black;">Dominio specificato inesistente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">08</td>
<td style="border:1px solid black;">Utente specificato inesistente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">16</td>
<td style="border:1px solid black;">Errore di autenticazione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">17</td>
<td style="border:1px solid black;">Errore di modifica della password</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">18</td>
<td style="border:1px solid black;">Tipo di autenticazione non supportato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">32</td>
<td style="border:1px solid black;">Solo utenti locali</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">33</td>
<td style="border:1px solid black;">La password deve essere cambiata</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">34</td>
<td style="border:1px solid black;">Account disattivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">35</td>
<td style="border:1px solid black;">Account scaduto</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">36</td>
<td style="border:1px solid black;">Account bloccato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">37</td>
<td style="border:1px solid black;">Orari di accesso non validi</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">38</td>
<td style="border:1px solid black;">Restrizione account</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">48</td>
<td style="border:1px solid black;">Mancata corrispondenza con il criterio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">64</td>
<td style="border:1px solid black;">Chiamate in ingresso bloccate</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">65</td>
<td style="border:1px solid black;">Chiamate in ingresso disattivate</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">66</td>
<td style="border:1px solid black;">Tipo di autenticazione non valido</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">67</td>
<td style="border:1px solid black;">Stazione chiamante non valida</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">68</td>
<td style="border:1px solid black;">Orari chiamate in ingresso non validi</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">69</td>
<td style="border:1px solid black;">Stazione chiamata non valida</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">70</td>
<td style="border:1px solid black;">Tipo di porta non valido</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">71</td>
<td style="border:1px solid black;">Restrizione non valida</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">Nessun record</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">96</td>
<td style="border:1px solid black;">Timeout sessione</td>
</tr>
</tbody>
</table>
  
Nei casi in cui le informazioni ricavate dal registro eventi non siano sufficienti per risalire alla causa del problema, può essere utile attivare l'analisi sul client IAS e sul server IAS. Le procedure sono descritte di seguito.
  
##### Attivazione e disattivazione dell'analisi sui computer client
  
In Windows sono disponibili informazioni di analisi dettagliate per la maggior parte dei componenti, proprio per semplificare la diagnosi di eventuali problemi. Se si attiva l'analisi per un componente, viene creato un file di testo contenente informazioni diagnostiche più dettagliate di quelle disponibili nei registri eventi.
  
Per ottenere informazioni dettagliate sul processo di autenticazione della rete WLAN, occorre attivare l'analisi per i componenti EAPOL (EAP over LAN) e RASTLS (Remote Access Service - Transport Layer Security). Dopo aver attivato l'analisi, riprovare il processo di autenticazione e controllare se i file Eapol.log e Rastls.log contengono informazioni utili per la diagnosi dei problemi (questi file vengono creati nella cartella %Systemroot%\\Tracing).
  
**Per attivare l'analisi sui computer client**
  
-   Eseguire i comandi seguenti:
  
    **netsh ras set tracing eapol enabled**
  
    **netsh ras set tracing rastls enabled**
  
**Per disattivare l'analisi sui computer client**
  
-   Eseguire i comandi seguenti:
  
    **netsh ras set tracing eapol disabled**
  
    **netsh ras set tracing rastls disabled**
  
    **Nota:**l'analisi richiede un notevole consumo di risorse di sistema e crea file registro le cui dimensioni possono aumentare rapidamente. Ricordarsi di disattivare l'analisi una volta completata la risoluzione dei problemi.
  
##### Attivazione e disattivazione dell'analisi sul server IAS
  
Per attivare l'analisi sul server IAS si procede esattamente come per i client.
  
È possibile utilizzare il comando **netsh** per attivare e disattivare l'analisi per vari componenti coinvolti nell'autenticazione nella rete. È particolarmente utile attivare l'analisi per problemi di autenticazione 802.1X con PEAP nei seguenti componenti:
  
-   **IASSAM (file Iassam.log nella cartella %Systemroot%\\tracing):** è il file di analisi più utilizzato per i problemi di IAS, in quanto descrive le funzioni relative alla violazione (conversione tra formati diversi) di nomi utente, al collegamento a un controller di dominio e alla verifica delle credenziali. È il punto nodale dei file di analisi di IAS e in genere è necessario per eseguire il debug degli errori correlati all'autenticazione.
  
-   **RASTLS (file Rastls.log nella cartella %Systemroot%\\tracing):** questo file di analisi viene utilizzato per tutte le autenticazioni EAP e PEAP. Contiene la maggior parte delle informazioni essenziali per il debug, ma è difficile da leggere e comprendere. Microsoft prevede di divulgare una documentazione che renda più semplice l'interpretazione di queste informazioni.
  
-   **RASCHAP (file Raschap.log nella cartella %Systemroot%\\tracing):** questo file di analisi viene utilizzato per tutte le operazioni di autenticazione di password MS-CHAP v2 e basate su CHAP.
  
L'attivazione dell'analisi sui seguenti componenti di IAS di norma non è necessaria per la risoluzione dei problemi di autenticazione 802.1X, ma può essere utile per risolvere altri problemi.
  
-   **IASRAD (file Iasrad.log nella cartella %Systemroot%\\tracing):** in questo file vengono registrate tutte le operazioni relative al protocollo RADIUS, ad esempio le porte sulle quali il server è in ascolto e così via. Può essere utile per risolvere i problemi di compatibilità dei punti di accesso senza fili.
  
-   **IASSDO (file Iassdo.log nella cartella %Systemroot%\\tracing):** nel file IASSDO vengono registrate le transazioni dall'interfaccia utente ai file MDB contenenti la configurazione e il dizionario del server. Questo registro è utile per risolvere i problemi relativi ai servizi o all'interfaccia utente.
  
**Per attivare l'analisi sul server IAS**
  
1.  Eseguire il comando **netsh** corrispondente al tipo di informazioni di analisi necessarie. Quando si risolvono i problemi di autenticazione 802.1X, i registri IASSAM, RASTLS e RASCHAP contengono le informazioni più utili.
  
    **netsh ras set tracing iassam enabled**
  
    **netsh ras set tracing rastls enabled**
  
    **netsh ras set tracing raschap enabled**
  
    **netsh ras set tracing iasrad enabled**
  
    **netsh ras set tracing iassdo enabled**
  
    In alternativa, per attivare l'analisi per tutte le categorie di componenti di rete, eseguire il comando seguente:
  
    **netshras set tracing \* enabled**
  
**Per disattivare l'analisi sul server IAS**
  
1.  Eseguire uno o più dei seguenti comandi **netsh** per disattivare l'analisi per le categorie attivate nella procedura precedente:
  
    **netsh ras set tracing iassam disabled**
  
    **netsh ras set tracing rastls disabled**
  
    **netsh ras set tracing raschap disabled**
  
    **netsh ras set tracing iasrad disabled**
  
    **netsh ras set tracing iassdo disabled**
  
    In alternativa, per disattivare l'analisi per tutte le categorie di componenti di rete, eseguire il comando seguente:
  
    **netshras set tracing \* disabled**
  
    **Nota:** poiché l'analisi richiede una notevole quantità di risorse del sistema, è opportuno utilizzarla con parsimonia, quando occorre individuare i problemi della rete. Dopo aver eseguito l'analisi o individuato il problema, è consigliabile disattivare l'analisi.
  
Per impostazione predefinita, i registri di analisi IASSAM e RASTLS sono impostati su solo 1 MB e questo può causare la sovrascrittura di informazioni importanti nei file registro in presenza di un carico pesante. La seguente procedura consente di impostare i registri di analisi su 10 MB. Quando viene raggiunto il limite di 10 MB, il file registro viene rinominato (IASSAM.old e RASTLS.old) e viene creato un nuovo file registro. In questo modo è possibile avere fino a 20 MB di dati nel server per ogni tipo di analisi. È possibile ripetere questa procedura per ogni tipo di analisi, specificando il nome della categoria di analisi (ad esempio RASTLS e RASCHAP) al posto del nome "IASSAM" indicato nella procedura.
  
**Per impostare il file registro di analisi IASSAM su 10 MB**
  
1.  Avviare Regedit.exe.
  
2.  Passare alla seguente chiave del Registro di sistema:
  
    **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Tracing**
  
3.  Trovare la sottochiave **IASSAM**, che dovrebbe avere il valore **MaxFileSize** (tipo **REG\_DWORD**). Modificare questo valore e impostare il valore **0xA00000** (è la rappresentazione esadecimale di 10MB; il valore predefinito è 0x100000). Se lo si desidera, è possibile impostare un valore diverso da 10 MB. Tuttavia, i registri di dimensioni maggiori di 10 MB diventano molto difficili da gestire.
  
    **Avviso:**modifiche non corrette al Registro di sistema potrebbero danneggiare gravemente il sistema. Prima di apportare modifiche al Registro di sistema, è consigliabile eseguire il backup di tutti i dati importanti presenti nel computer.
  
##### Attivazione della registrazione SChannel sul server IAS
  
SChannel è un provider SSP (Security Support Provider) che supporta una serie di protocolli di protezione Internet, ad esempio SSL (Secure Sockets Layer) e TLS (Transport Level Security). Se si sospettano problemi relativi al certificato del server IAS, oppure se dal registro RASTLS risulta che vi sono problemi nella creazione della sessione TLS, è opportuno attivare la registrazione sia sul client che sul server. Gli eventi vengono registrati nel registro di protezione.
  
Seguire la stessa procedura per il client e il server.
  
**Per attivare la registrazione SChannel**
  
1.  Avviare Regedit.exe.
  
2.  Passare alla seguente chiave del Registro di sistema:
  
    **HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL\\**
  
3.  Per attivare la registrazione di eventi Schannel dettagliati, modificare il valore di **EventLogging** da **1** (tipo **REG\_DWORD**, dati **0x00000001**) a **3** (tipo **REG\_DWORD**, dati **0x00000003**).
  
    **Avviso:**modifiche non corrette al Registro di sistema potrebbero danneggiare gravemente il sistema. Prima di apportare modifiche al Registro di sistema, è consigliabile eseguire il backup di tutti i dati importanti presenti nel computer.
  
Dopo aver risolto il problema, ricordarsi di disattivare la registrazione Schannel, perché richiede un quantità notevole di risorse del sistema e registra moltissime voci nel registro eventi.
  
##### Strumenti diagnostici per Pocket PC
  
In Windows XP sono disponibili numerosi strumenti per la diagnosi dei problemi della rete. I Pocket PC, al contrario, contengono relativamente pochi strumenti diagnostici. I rivenditori di Pocket PC, Microsoft e altre società forniscono vari tipi di strumenti per la diagnosi dei problemi dei Pocket PC. Alcuni di questi sono:
  
-   **Strumenti diagnostici e per la configurazione IP:** strumenti quali VXUtil o VXIPConfig di Cambridge Software.
  
-   Strumenti diagnostici per reti LAN senza fili forniti da rivenditori di Pocket PC.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo capitolo sono stati affrontati i seguenti punti, essenziali per garantire il corretto funzionamento dell'infrastruttura per la protezione delle reti LAN senza fili:
  
-   Individuazione delle attività di manutenzione essenziali.
  
-   Descrizione delle attività operative, di monitoraggio, di supporto, di modifica e di ottimizzazione necessarie per questo ambiente.
  
-   Descrizione delle procedure e delle tecniche più importanti per la risoluzione dei problemi.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riferimenti
  
In questa sezione vengono suggerite altre fonti di informazioni, a completamento delle indicazioni fornite in questo capitolo.
  
-   Per ulteriori informazioni sul backup e il ripristino dei server Windows, vedere la pagina Windows Server 2003 "Backing up and restoring data" nel sito Web Microsoft, all'indirizzo:
  
    <http://technet.microsoft.com/en-us/library/cc775934.aspx> (in inglese)
  
-   Per ulteriori informazioni sul monitoraggio e sulla gestione, vedere la pagina "Microsoft Solutions for Management" nel sito Web Microsoft, all'indirizzo:
  
    <http://technet.microsoft.com/systemcenter/default.aspx> (in inglese)
  
-   Per ulteriori informazioni sull'ottimizzazione di IAS, vedere:
  
    <http://technet.microsoft.com/en-us/library/cc780027.aspx> (in inglese)
  
-   Per informazioni sulla risoluzione dei problemi dei componenti delle reti senza fili, vedere:
  
    <http://support.microsoft.com/default.aspx?scid=313242> (in inglese)
  
    [http://www.microsoft.com/technet/prodtechnol/winxppro/  
    maintain/wifitrbl.mspx](http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/wifitrbl.mspx) (in inglese)
  
-   Per ulteriori informazioni sulla risoluzione dei problemi di IAS, vedere:
  
    <http://technet.microsoft.com/en-us/library/cc875820.aspx> (in inglese)
  
-   Per ulteriori informazioni sugli strumenti per la diagnostica e la configurazione IP, quali VXUtil e VXIPConfig, vedere:
  
    <http://www.cam.com/windowsce.html> (in inglese)
  
**Scarica la soluzione completa**
  
[Protezione delle reti LAN senza fili con PEAP e password](http://go.microsoft.com/fwlink/?linkid=23481)
  
[](#mainsection)[Inizio pagina](#mainsection)
