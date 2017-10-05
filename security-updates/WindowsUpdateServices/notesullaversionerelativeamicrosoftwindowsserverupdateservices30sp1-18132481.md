---
TOCTitle: 'Note sulla versione relative a Microsoft Windows Server Update Services 3.0 SP1'
Title: 'Note sulla versione relative a Microsoft Windows Server Update Services 3.0 SP1'
ms:assetid: 'a5aa93bf-842b-4ad4-ab0f-fe867843cb02'
ms:contentKeyID: 18132481
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc708525(v=WS.10)'
---

Note sulla versione relative a Microsoft Windows Server Update Services 3.0 SP1
===============================================================================

Nelle presenti note sulla versione vengono illustrati problemi noti relativi a Microsoft® Windows® Server Update Services (WSUS) 3.0 Service Pack 1. Sono inoltre disponibili suggerimenti e informazioni sui requisiti per l'installazione. In questo documento sono presenti le sezioni seguenti:

-   Requisiti di sistema per l'installazione server di WSUS 3.0 SP1
-   Requisiti di configurazione per l'installazione server di WSUS 3.0 SP1
-   Requisiti di sistema per l'installazione della console remota di WSUS 3.0 SP1
-   Requisiti di sistema per l'installazione client
-   Requisiti software per l'installazione server di WSUS SP1
-   Requisiti minimi di spazio su disco per l'installazione server di WSUS 3.0 SP1
-   Requisiti per l'aggiornamento a WSUS 3.0 SP1
-   Parametri della riga di comando del programma di installazione
-   Problemi di installazione
-   Problemi di aggiornamento
-   Problemi noti
-   WSUS 3.0 SP1 su Windows Server® 2008
-   WSUS 3.0 SP1 su Windows Small Business Server 2003

Requisiti di sistema per l'installazione server di WSUS 3.0 SP1
---------------------------------------------------------------

#### Il server WSUS 3.0 SP1 è supportato in Windows Server 2008 e in Windows Server 2003 Service Pack 1

Il server WSUS 3.0 SP1 è supportato in Windows Server 2008 e in Windows Server 2003 Service Pack 1

#### Windows 2000 Server non è supportato per i server WSUS 3.0 SP1

Microsoft Windows® 2000 Server non è un sistema operativo supportato per i server WSUS 3.0 SP1.

#### WSUS 3.0 SP1 non è supportato nei server in cui vengono eseguiti i Servizi terminal

Sebbene sia comunque possibile eseguire WSUS 3.0 SP1 su server su cui sono in esecuzione i Servizi terminal, questo utilizzo non è supportato né consigliabile. Non è possibile eseguire WSUS 3.0 SP1 su un server su cui sono in esecuzione i Servizi terminal in configurazioni che utilizzano implementazioni di SQL Server remote. Poiché tutte le operazioni personalizzate remote (inclusa l'installazione) in un server licenze Servizi terminal verranno eseguite come account di sistema e l'account di sistema del server potrebbe non disporre delle autorizzazioni sul server SQL remoto, l'installazione potrebbe non riuscire.

Requisiti di configurazione per l'installazione server di WSUS 3.0 SP1
----------------------------------------------------------------------

#### IIS deve essere installato

WSUS 3.0 SP1 richiede Internet Information Services (IIS), il quale non viene installato per impostazione predefinita in Windows Server 2008 o Microsoft Windows Server 2003. Se si tenta di installare WSUS 3.0 SP1 senza IIS, verrà visualizzato un messaggio di errore del programma di installazione di Windows Server Update Services per indicare l'assenza di IIS.

#### Se IIS viene eseguito in modalità di isolamento di IIS 5.0, l'installazione non verrà eseguita

Se si è aggiornato il server da Windows 2000 Server a Windows Server 2003, è possibile che IIS venga eseguito nella modalità di compatibilità di IIS 5.0. È anche possibile attivare la modalità di isolamento di IIS 5.0 in Gestione IIS. Ciò impedirà il completamento dell'installazione. Sarà necessario disabilitare la modalità di isolamento di IIS 5.0 prima di installare WSUS 3.0 SP1.

#### Se uno o più componenti di IIS sono installati in modalità di compatibilità a 32 bit su una piattaforma a 64 bit, l'installazione di WSUS 3.0 SP1 potrebbe avere esito negativo

Tutti i componenti di IIS devono essere installati in modalità nativa su piattaforme a 64 bit. L'installazione potrebbe avere esito negativo, se uno o più componenti di IIS sono in modalità di compatibilità a 32 bit.

#### I server proxy possono supportare solo il protocollo HTTP oppure HTTP e HTTPS

In WSUS 3.0 SP1 un server proxy può supportare solo il protocollo HTTP. È necessario configurare un secondo server proxy che esegue HTTPS tramite la riga di comando (**wsusutil configuresslproxy**) prima di configurare il server WSUS dalla configurazione guidata o dalla console di amministrazione.

#### Se sono presenti due o più siti Web sulla porta 80, eliminarli tutti tranne uno prima di installare WSUS

Se sono presenti due o più siti Web sulla porta 80 (ad esempio Windows® SharePoint® Services), è necessario eliminarli tutti tranne uno prima di installare WSUS, altrimenti non verrà eseguito l'aggiornamento automatico dei client del server.

#### Quando si installa WSUS 3.0 SP1, potrebbe essere necessario disattivare programmi antivirus

Quando si installa WSUS 3.0 SP1, potrebbe essere necessario disattivare programmi antivirus per eseguire correttamente l'installazione. Dopo aver disattivato il programma antivirus, riavviare il computer prima di installare WSUS. Il riavvio del computer impedisce che i file vengano bloccati quando il processo di installazione ha bisogno di accedere ad essi. Al termine dell'installazione assicurarsi di riattivare il programma antivirus. Visitare il sito Web del produttore del programma antivirus per informazioni sulle procedure corrette relative alla disattivazione e riattivazione del programma antivirus.

| ![](images/Cc708525.Caution(WS.10).gif)Attenzione                                                                                                                                                                                                                                                                                                                |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Questa soluzione alternativa potrebbe rendere il computer o la rete più vulnerabile agli attacchi da parte di utenti malintenzionati o di software dannoso, ad esempio virus. Non è consigliabile questa soluzione alternativa, ma tali informazioni vengono fornite in modo che sia possibile implementarla a propria discrezione. Utilizzare questa soluzione a proprio rischio e pericolo. |

| ![](images/Cc708525.note(WS.10).gif)Nota                                                                                                                                                                                                                       |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Un programma antivirus è progettato per aumentare la protezione del computer dai virus. Non si devono scaricare o aprire file provenienti da origini non attendibili, visitare siti Web non attendibili o aprire allegati di posta elettronica quando il programma antivirus è disattivato. |

#### In SQL Server deve essere attivata l'opzione relativa ai trigger nidificati

L'opzione relativa ai trigger nidificati è attivata per impostazione predefinita. Tuttavia, può essere disattivata da un amministratore di SQL Server.

Se si intende utilizzare un database di SQL Server come archivio dati di Windows Server Update Services, l'amministratore di SQL Server dovrà verificare che l'opzione relativa ai trigger nidificati nel server sia attivata prima che l'amministratore di WSUS 3.0 SP1 installi WSUS 3.0 SP1 e specifichi il database durante l'installazione.

Il programma di installazione di WSUS 3.0 SP1 attiva l'opzione RECURSIVE\_TRIGGERS, che è un'opzione specifica del database. Tuttavia, non attiva l'opzione relativa ai trigger nidificati, che è un'opzione globale del server.

Per verificare se i trigger nidificati sono attivati, utilizzare il seguente comando:

**sp\_configure 'nested triggers'**

Per attivare l'opzione relativa ai trigger nidificati in SQL Server, eseguire il seguente comando da un file batch sul computer in cui è in esecuzione SQL Server:

**sp\_configure 'nested triggers', 1**

**GO**

**RECONFIGURE**

**GO**

Se non si dispone di SQL Server Management Studio nel server potrebbe essere necessario eseguire script di SQL dalla riga di comando. È possibile scaricare l'utilità Query della riga di comando di Microsoft SQL Server 2005 dall'[Area download Microsoft](http://go.microsoft.com/fwlink/?linkid=70728) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=70728. Per iniziare, eseguire **sqlcmd**.

Se si desidera eseguire script SQL in Windows Internal Database, è inoltre necessario scaricare SQL Server Native Client dalla stessa pagina di download.

#### Limitazioni e requisiti di SQL remoto

WSUS 3.0 SP1 offre supporto per l'esecuzione di software di database su un computer separato da quello che contiene il resto dell'applicazione WSUS 3.0 SP1. Per configurare un'installazione di SQL remoto sono necessari alcuni requisiti:

-   Un server configurato come controller di dominio non può essere utilizzato come computer back-end nella configurazione di SQL remoto.
-   Non è possibile utilizzare Terminal Server nel computer che sarà il server front-end dell'installazione di SQL remoto.
-   Per il software di database nei computer di back-end, è necessario utilizzare almeno Microsoft SQL Server 2005 Service Pack 1 (disponibile nell'[Area download Microsoft](http://go.microsoft.com/fwlink/?linkid=66143) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=66143) se tali computer utilizzano Windows Server 2003, e SQL Server 2005 Service Pack 2 se i computer back-end utilizzano Windows Server® 2008.
-   Entrambi i computer, front-end e back-end, devono essere uniti a un dominio di Active Directory. se no si trovano nello stesso dominio, è necessario stabilire un'attendibilità tra i domini prima di eseguire l'installazione di WSUS.
-   Se WSUS 2.0 è già installato in una configurazione SQL remota e si desidera eseguire l'aggiornamento a WSUS 3.0 SP1, sarà necessario disinstallare WSUS 2.0 (utilizzando **Installazione applicazioni** nel Pannello di controllo) nel computer back-end assicurandosi che il database esistente rimanga intatto. Sarà quindi necessario installare SQL Server 2005 SP1 o SP2 e aggiornare il database esistente. Sarà infine possibile installare WSUS 3.0 SP1 nel computer front-end.

Requisiti di sistema per l'installazione della console remota di WSUS 3.0 SP1
-----------------------------------------------------------------------------

È possibile installare la console remota di WSUS 3.0 SP1 sulle seguenti piattaforme:

-   Windows Server 2008
-   Windows Vista® o versioni successive
-   Windows Server 2003 SP1 o versioni successive
-   Windows XP SP2 o versioni successive

Requisiti di sistema per l'installazione client
-----------------------------------------------

Aggiornamenti automatici è il software client di WSUS. È possibile utilizzarlo con WSUS nei computer che eseguono uno dei sistemi operativi seguenti:

-   Microsoft Windows Vista o versioni successive
-   Windows Server 2008 o versioni successive
-   Microsoft Windows Server 2003, qualsiasi edizione
-   Microsoft Windows XP Professional SP2 o versioni successive
-   Microsoft Windows 2000 Professional SP4, Windows 2000 Server SP4 o Windows 2000 Advanced Server con SP4

Requisiti software per l'installazione server di WSUS 3.0 SP1
-------------------------------------------------------------

Nella tabella seguente viene illustrato il software necessario per le piattaforme Windows Server 2003 SP1. Le informazioni sul software necessario per Windows Server 2008 sono disponibili nella sezione relativa a WSUS 3.0 SP1 su Windows Server 2008.

Prima di eseguire il programma di installazione WSUS 3.0 SP1 assicurarsi che il server di WSUS 3.0 SP1 soddisfi questo elenco di requisiti. Se uno di questi aggiornamenti richiede il riavvio del computer al termine dell'installazione, sarà necessario eseguire il riavvio prima dell'installazione di WSUS 3.0 SP1.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Requisito</th>
<th style="border:1px solid black;" >Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Internet Information Services (IIS)</td>
<td style="border:1px solid black;">Eseguire l'installazione dal sistema operativo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft .NET Framework versione 2.0 Redistributable Package</td>
<td style="border:1px solid black;">Vedere Microsoft .NET Framework versione 2.0 Redistributable Package (x86) nell'<a href="http://go.microsoft.com/fwlink/?linkid=68935">Area download Microsoft</a> all'indirizzo http://go.microsoft.com/fwlink/?LinkId=68935. Per piattaforme a 64 bit, vedere Microsoft .NET Framework versione 2.0 Redistributable Package (x86) nell'<a href="http://go.microsoft.com/fwlink/?linkid=70637">Area download Microsoft</a> all'indirizzo http://go.microsoft.com/fwlink/?LinkId=70637.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Management Console 3.0 per Windows Server 2003</td>
<td style="border:1px solid black;">Si tratta di un prerequisito per l'utilizzo dell'interfaccia utente di WSUS 3.0 SP1. Vedere Microsoft Management Console 3.0 per Windows Server 2003 (KB907265) nell'<a href="http://go.microsoft.com/fwlink/?linkid=70412">Area download Microsoft</a> all'indirizzo http://go.microsoft.com/fwlink/?LinkId=70412. Per piattaforme a 64 bit, vedere Microsoft Management Console 3.0 per Windows Server 2003 x64 Edition (KB907265) nell'<a href="http://go.microsoft.com/fwlink/?linkid=70638">Area download Microsoft</a> all'indirizzo http://go.microsoft.com/fwlink/?LinkId=70638.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Report Viewer</td>
<td style="border:1px solid black;">Si tratta di un prerequisito per l'utilizzo dell'interfaccia utente di WSUS 3.0 SP1. Vedere Microsoft Report Viewer Redistributable 2005 nell'<a href="http://go.microsoft.com/fwlink/?linkid=70410">Area download Microsoft</a> all'indirizzo http://go.microsoft.com/fwlink/?LinkId=70410.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SQL Server 2005 (opzionale)</td>
<td style="border:1px solid black;">WSUS 3.0 SP1 consente di installare automaticamente Windows Internal Database, se non si dispone di una versione compatibile di SQL Server già installata. Se, tuttavia, si prevede di utilizzare un database di SQL Server completo, è necessario utilizzare almeno SQL Server 2005 SP1 (disponibile nell'<a href="http://go.microsoft.com/fwlink/?linkid=66143">Area download Microsoft</a> all'indirizzo http://go.microsoft.com/fwlink/?LinkId=66143) in computer che eseguono Windows Server 2003 o SQL Server 2005 SP2 (disponibili nell'<a href="http://go.microsoft.com/fwlink/?linkid=84823">Area download Microsoft</a> all'indirizzo http://go.microsoft.com/fwlink/?LinkId=84823) in computer che eseguono Windows Server 2008.</td>
</tr>
</tbody>
</table>
  
| ![](images/Cc708525.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                            |  
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Se è stato precedentemente installato WSUS 2.0 e questa versione utilizza SQL Server 2000, SQL Server Desktop Engine 2000 o qualsiasi database di SQL Server precedente a SQL Server 2005 SP1 (oppure a SQL Server 2005 SP2 su Windows Server 2008), il programma di installazione di WSUS 3.0 SP1 installerà Windows® Internal Database ed eseguirà la migrazione del database. |
  
Requisiti minimi di spazio su disco per l'installazione server di WSUS 3.0 SP1  
------------------------------------------------------------------------------
  
Di seguito vengono indicati i requisiti minimi di spazio su disco per installare Windows Server Update Services:
  
-   1 GB nella partizione di sistema  
-   2 GB per il volume in cui verranno archiviati i file del database  
-   20 GB per il volume in cui verranno archiviati i contenuti
  
| ![](images/Cc708525.Important(WS.10).gif)Importante                             |  
|--------------------------------------------------------------------------------------------------------------|  
| Non è possibile installare WSUS 3.0 SP1 in unità compresse. Verificare che l'unità scelta non sia compressa. |
  
Requisiti per l'aggiornamento a WSUS 3.0 SP1  
--------------------------------------------
  
#### Assicurarsi che l'installazione di WSUS venga eseguita correttamente ed eseguire il backup del database di WSUS prima di eseguire l'aggiornamento
  
Se si esegue l'aggiornamento a WSUS 3.0 SP1 da una versione precedente, è consigliabile accertarsi che l'installazione corrente venga eseguita correttamente ed eseguire il backup del database di WSUS prima dell'aggiornamento.
  
1.  Controllare eventuali errori recenti nel registro eventi, problemi di sincronizzazione tra i server figlio e i server padre o problemi relativi a client che non segnalano errori. Assicurarsi che questi problemi siano stati risolti prima di continuare.  
2.  Potrebbe essere necessario eseguire DBCC CHECKDB per assicurarsi che il database di WSUS sia indicizzato correttamente. Per ulteriori informazioni su DBCC CHECKDB, vedere [DBCC CHECKDB](http://go.microsoft.com/fwlink/?linkid=86948) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=86948.  
3.  Eseguire il backup del database di WSUS.
  
#### Se si è modificato manualmente la porta utilizzata da WSUS, eseguire la disinstallazione prima di eseguire l'aggiornamento
  
Se si modifica la porta per WSUS, utilizzare sempre l'utilità wsusutil invece di tentare di modificare manualmente la porta. Se la porta è stata modificata manualmente ed è stato precedentemente eseguito l'aggiornamento da Software Update Services 1.0 a WSUS 2.0:
  
1.  Se ancora non è stato installato WSUS 3.0, disinstallare WSUS 2.0, mantenendo il database e i contenuti. Se è già stato installato WSUS 3.0, disinstallarlo mantenendo il database e i contenuti.  
2.  Avviare il sito Web predefinito, riattivando temporaneamente SUS 1.0 ma rendendolo accessibile al programma di disinstallazione.  
3.  Disinstallare SUS 1.0.  
4.  Installare WSUS 3.0.
  
#### Software Update Services 1.0 deve essere disinstallato
  
L'installazione di WSUS 3.0 SP1 non verrà eseguita correttamente se Software Update Services 1.0 è installato nello stesso computer. È necessario disinstallare Software Update Services 1.0 prima di installare WSUS 3.0 SP1.
  
#### Non è possibile eseguire l'aggiornamento da WSUS 2.0 a WSUS 3.0 SP1 in un sistema operativo a 64 bit
  
WSUS 2.0 non è supportato in sistemi operativi a 64 bit. Pertanto, non è possibile eseguire l'aggiornamento da WSUS 2.0 a WSUS 3.0 SP1 in tali sistemi.
  
Parametri della riga di comando del programma di installazione  
--------------------------------------------------------------
  
È possibile eseguire installazioni automatiche di WSUS 3.0 SP1 utilizzando i parametri della riga di comando di WSUS. Nella tabella seguente vengono riportati i parametri della riga di comando per l'installazione di WSUS 3.0 SP1.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Opzione</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>/q</strong></td>
<td style="border:1px solid black;">Consente di eseguire l'installazione invisibile all'utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>/u</strong></td>
<td style="border:1px solid black;">Consente di disinstallare il prodotto. Inoltre, consente di disinstallare l'istanza di Windows Internal Database, se è installato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>/p</strong></td>
<td style="border:1px solid black;">Consente solo il controllo dei prerequisiti. Non consente di installare il prodotto, ma consente di eseguire un'ispezione del sistema e riportare eventuali prerequisiti mancanti.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>/?, /h</strong></td>
<td style="border:1px solid black;">Consentono di visualizzare i parametri della riga di comando e le relative descrizioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>/g</strong></td>
<td style="border:1px solid black;">Consente di eseguire l'aggiornamento dalla precedente versione di WSUS. (Non tentare di eseguire l'aggiornamento da SUS 1.0.) L'unico parametro valido con questa opzione è /q (installazione invisibile all'utente). L'unica proprietà valida con questa opzione è DEFAULT_WEBSITE.</td>
</tr>
</tbody>
</table>
  
Nella tabella seguente vengono indicate le proprietà della riga di comando per WSUS 3.0 SP1.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Proprietà</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CONTENT_LOCAL</td>
<td style="border:1px solid black;">0 = contenuto ospitato localmente, 1 = contenuto ospitato su Microsoft Update</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CONTENT_DIR</td>
<td style="border:1px solid black;">Percorso della directory contenuto. L'impostazione predefinita è <em>UnitàDiInstallazioneDiWSUS</em><strong>\WSUS\WSUSContent</strong>, dove <em>UnitàDiInstallazioneDiWSUS</em> è l'unità locale con la maggior quantità di spazio libero.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">WYUKON_DATA_DIR</td>
<td style="border:1px solid black;">Percorso della directory di dati di Windows Internal Database.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SQLINSTANCE_NAME</td>
<td style="border:1px solid black;">Il nome deve essere indicato nel formato <em>Nome Server</em>\<em>NomeIstanzaSQL</em>. Se l'istanza del database si trova nel computer locale, utilizzare la variabile di ambiente %COMPUTERNAME%. Se non è già disponibile un'istanza esistente, il valore predefinito è %COMPUTERNAME%\WSUS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DEFAULT_WEBSITE</td>
<td style="border:1px solid black;">0 = porta 8530, 1 = porta 80</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PREREQ_CHECK_LOG</td>
<td style="border:1px solid black;">Percorso e nome del file registro</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CONSOLE_INSTALL</td>
<td style="border:1px solid black;">0 = installa il server WSUS, 1 = installa solo la console</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ENABLE_INVENTORY</td>
<td style="border:1px solid black;">0 = non installa le funzionalità di inventario, 1 = installa le funzionalità di inventario</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DELETE_DATABASE</td>
<td style="border:1px solid black;">0 = mantiene il database, 1 = rimuove il database</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DELETE_CONTENT</td>
<td style="border:1px solid black;">0 = mantiene il contenuto, 1 = rimuove i file del contenuto</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DELETE_LOGS</td>
<td style="border:1px solid black;">0 = mantiene i file di registro, 1 = rimuove i file di registro (utilizzata con l'opzione di installazione /u).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CREATE_DATABASE</td>
<td style="border:1px solid black;">0 = usa il database corrente, 1 = crea un database</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PROGRESS_WINDOW_HANDLE</td>
<td style="border:1px solid black;">Handle della finestra per restituire i messaggi di avanzamento MSI</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MU_ROLLUP</td>
<td style="border:1px solid black;">1 = partecipa al programma Analisi utilizzo Microsoft Update, 0 = non partecipa al programma Analisi utilizzo Microsoft Update</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">FRONTEND_SETUP</td>
<td style="border:1px solid black;">1 = non scrive il percorso del contenuto nel database, 0 = scrive il percorso del contenuto nel database (per NLB)</td>
</tr>
</tbody>
</table>
  
#### Esempio di sintassi
  
```  
WSUSSetup.exe /q DEFAULT\_WEBSITE=0 (install in quiet mode using port 8530) WSUSSetup.exe /q /u (uninstall WSUS)  
```  
| ![](images/Cc708525.Important(WS.10).gif)Importante                                                                                                                                                       |  
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Se si installa WSUS 3.0 SP1 in modalità non interattiva (/q) e nel computer non sono installati tutti i prerequisiti, il programma di installazione creerà un file denominato WSUSPreReqCheck.xml e lo salverà nella directory %TEMP%. |
  
Problemi di installazione  
-------------------------
  
#### IIS viene riavviato durante l'installazione di WSUS 3.0 SP1
  
Il programma di installazione di WSUS 3.0 SP1 riavvia IIS senza notifica. Ciò potrebbe influire negativamente sui siti Web esistenti nell'organizzazione. Se IIS non è in esecuzione, verrà avviato dal programma di installazione di WSUS 3.0.
  
#### Se sono aperte delle connessioni a un database di WSUS esistente, l'installazione potrebbe avere esito negativo
  
Se si esegue l'aggiornamento a WSUS 3.0 SP1 da un'installazione esistente e risultano ancora aperte delle connessioni al database di WSUS esistente (ad esempio se è aperto SQL Server Management Studio), l'installazione potrebbe avere esito negativo. Chiudere tutte le connessioni e reinstallare WSUS 3.0 SP1.
  
#### Nel programma di installazione di WSUS viene indicata una directory errata per i file di database
  
Nella pagina **Inizio installazione** del programma di installazione di WSUS viene erroneamente indicato come percorso del database la directory padre di quest'ultimo. Ad esempio, se il percorso predefinito è %systemdrive%\\WSUS\\UpdateServicesDbFiles, verrà erroneamente indicato il percorso %systemdrive%\\WSUS.
  
#### Se WSUS viene installato in un computer con Language Pack della funzionalità MUI (Multilingual User Interface, interfaccia utente multilingue) con una lingua predefinita diversa dall'inglese, la Guida in linea verrà visualizzata nella lingua predefinita e non in inglese
  
Se si dispone di un computer con Language Pack della funzionalità MUI (Multilingual User Interface, interfaccia utente multilingue) con una lingua predefinita diversa dall'inglese, sarà ancora possibile installare WSUS se l'impostazione internazionale dell'utente corrente è Inglese. L'interfaccia utente verrà visualizzata in inglese, ma sarà necessario utilizzare una soluzione alternativa per visualizzare la Guida in linea in inglese. Copiare il file con estensione chm della Guida in linea in inglese (*DirectoryDiInstallazioneDiWSUS*\\documentation\\mui\\0409\\WSUS30Help.chm) nella directory principale della documentazione (*DirectoryDiInstallazioneDiWSUS*\\documentation\\WSUS30Help.chm). In questo modo la Guida in linea dovrebbe essere visualizzata correttamente in tutte le lingue.
  
Problemi di aggiornamento  
-------------------------
  
#### Ripristino dopo un aggiornamento non riuscito
  
Se si esegue un aggiornamento da una versione precedente di WSUS (WSUS 3.0, WSUS 2.0 SP1 o WSUS 2.0) a WSUS 3.0 SP1 ma per qualche motivo l'aggiornamento non viene eseguito correttamente:
  
1.  Reinstallare la versione precedente di WSUS.  
2.  Ripristinare il database dal backup eseguito prima dell'aggiornamento. (Nella maggior parte dei casi, anche WSUS crea automaticamente un backup. Vedere il file WSUSSetup.log per il percorso del backup.)  
3.  Esaminare i registri per determinare la causa dell'errore e correggere il problema.  
4.  Tentare nuovamente di aggiornare WSUS.
  
#### Non è possibile eseguire l'aggiornamento da WSUS 2.0 a WSUS 3.0 SP1 se è presente un database di WSUS 3.0 SP1 da un'installazione precedente
  
Se si è precedentemente installato WSUS 3.0 SP1 e successivamente si è reinstallato WSUS 2.0, è necessario eliminare il database di WSUS 3.0 SP1 dal computer prima di tentare di reinstallare WSUS 3.0 SP1.
  
#### Se si modifica il nome del computer prima di eseguire l'aggiornamento a WSUS 3.0 SP1, quest'ultimo potrebbe avere esito negativo
  
Se si modifica il nome del computer dopo l'installazione di WSUS 2.0 e prima di eseguire l'aggiornamento a WSUS 3.0 SP1, quest'ultimo potrebbe avere esito negativo.
  
Utilizzare lo script seguente per rimuovere e aggiungere nuovamente i gruppi ASPNET e WSUS Administrators. Quindi, eseguire nuovamente l'aggiornamento.
  
Sarà necessario sostituire *&lt;PercorsoDB&gt;* con la cartella in cui è installato il database e *&lt;DirectoryContenuto&gt;* con la cartella di archiviazione locale.
  
```  
sqlcmd.exe -S *&lt;DBLocation&gt;* -E -Q "USE SUSDB DECLARE @asplogin varchar(200) SELECT @asplogin=name from sysusers WHERE name like '%ASPNET' EXEC sp\_revokedbaccess @asplogin" sqlcmd.exe -S *&lt;DBLocation&gt;* -E -Q "USE SUSDB DECLARE @wsusadminslogin varchar(200) SELECT @wsusadminslogin=name from sysusers WHERE name like '%WSUS Administrators' EXEC sp\_revokedbaccess @wsusadminslogin"   sqlcmd.exe -S *&lt;DBLocation&gt;* -E -Q "USE SUSDB DECLARE @asplogin varchar(200) SELECT @asplogin=HOST\_NAME()+'\\ASPNET' EXEC sp\_grantlogin @asplogin EXEC sp\_grantdbaccess @asplogin EXEC sp\_addrolemember webService,@asplogin" sqlcmd.exe -S *&lt;DBLocation&gt;* -E -Q "USE SUSDB DECLARE @wsusadminslogin varchar(200) SELECT @wsusadminslogin=HOST\_NAME()+'\\WSUS Administrators' EXEC sp\_grantlogin @wsusadminslogin EXEC sp\_grantdbaccess @wsusadminslogin EXEC sp\_addrolemember webService,@wsusadminslogin"   sqlcmd.exe -S *&lt;DBLocation&gt;* -E -Q "backup database SUSDB to disk=N'*&lt;ContentDirectory&gt;*\\SUSDB.Dat' with init"  
```
  
#### Durante l'installazione verrà sovrascritto un backup di database precedente
  
Il programma di installazione di WSUS 3.0 SP1 aggiunge il database alla directory predefinita, che è *unità*\\WSUS (dove *unità* è l'unità NTFS locale con la maggior quantità di spazio libero). Se in tale directory è presente un backup di database, quest'ultimo verrà sovrascritto. È consigliabile che gli amministratori eseguano il backup del database della versione corrente in un percorso diverso prima di eseguire l'aggiornamento a WSUS 3.0 SP1.
  
#### Se si è eseguita la migrazione da MSDE a SQL Server 2000 o SQL Server 2005 in WSUS 2.0, sarà necessario modificare un valore del Registro di sistema
  
Se nel computer è installato WSUS 2.0 e si è eseguita la migrazione da SQL Server 2000 o SQL Server 2005, sarà necessario modificare il valore **HKLM\\SOFTWARE\\Microsoft\\Update Services\\Server\\Setup\\WmsdeInstalled** da 1 a 0. Se non si esegue questa modifica prima dell'aggiornamento a WSUS 3.0 SP1, quest'ultimo avrà esito negativo.
  
#### Se l'installazione di WSUS 2.0 viene avviata e poi annullata, la chiave del Registro di sistema di WSUS verrà eliminata
  
Se l'installazione di WSUS 2.0 viene avviata e poi annullata, la chiave del Registro di sistema di WSUS verrà eliminata. Ciò può causare problemi se WSUS 3.0 SP1 è già installato. Lo stesso problema si verifica se si avvia la disinstallazione di WSUS 2.0 e quindi si annulla l'operazione per poi tentare di eseguire l'aggiornamento da WSUS 2.0 a WSUS 3.0 SP1.
  
#### Se si disinstalla WSUS 3.0 SP1 e si mantengono tuttavia i file di registro, potrebbero verificarsi problemi di autorizzazione dopo la reinstallazione
  
Quando si disinstalla WSUS 3.0 SP1, è possibile mantenere i file di registro dell'installazione. Quando si reinstalla WSUS 3.0 SP1, i file di registro precedenti perdono le rispettive autorizzazioni (in genere solo per WSUS Administrators). Sarà pertanto necessario ripristinare le autorizzazioni per tali file di registro.
  
#### Se in client WSUS 2.0 sono presenti aggiornamenti con stato "Non applicabile", tali aggiornamenti verranno visualizzati con stato "Sconosciuto" per un breve periodo dopo l'aggiornamento a WSUS 3.0 SP1
  
Se un server WSUS 2.0 dispone di client con aggiornamenti con stato **Non applicabile**, tali aggiornamenti avranno lo stato **Sconosciuto** per un breve periodo dopo che il server viene aggiornato a WSUS 3.0 SP1. Lo stato di aggiornamento tornerà su **Non applicabile** quando il client eseguirà la successiva scansione.
  
Problemi noti  
-------------
  
#### Risoluzione di più errori di download o di ripetuti problemi di sincronizzazione client
  
Se i client di WSUS 3.0 SP1 segnalano più errori di download oppure se i client non eseguono correttamente la sincronizzazione con il server di WSUS 3.0 SP1 per un periodo di tempo prolungato, è possibile che la cache di download del client sia danneggiata. Per risolvere il problema è possibile provare a eliminare la cache di download del client dal file system.
  
Per eliminare la cache di download del client:
  
1.  Eliminare tutti i file e le sottodirectory in questo percorso del computer client: **%windir%\\SoftwareDistribution\\Download**  
2.  Tentare di installare l'aggiornamento sincronizzando di nuovo il computer client con WSUS 3.0 SP1. Questo tentativo di installazione potrebbe non avere esito positivo e potrebbe essere visualizzato un messaggio di errore analogo al seguente: **WU\_E\_DM\_NOTDOWNLOADED, "Impossibile scaricare l'aggiornamento."**  
3.  Dopo questo errore, il computer client riavvia automaticamente il download e sarà possibile procedere con l'installazione.
  
#### Se la sincronizzazione ha esito negativo, ripetere l'operazione
  
Se la sincronizzazione ha esito negativo, il primo passo verso la risoluzione del problema dovrà essere il tentativo di sincronizzare di nuovo il server. Se le sincronizzazioni successive hanno esito negativo, utilizzare le informazioni relative alla risoluzione dei problemi riportate nella [Guida operativa di Windows Server Update Services 3.0](http://go.microsoft.com/fwlink/?linkid=81072) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=81072 (informazioni in inglese).
  
#### La modifica della configurazione di WSUS 3.0 SP1 direttamente dal database non è supportata
  
I dati di configurazione di Windows Server Update Services vengono archiviati in un database di SQL Server. Tali dati non possono tuttavia essere modificati direttamente dal database. Non tentare di modificare la configurazione di WSUS 3.0 SP1 accedendo direttamente al database. È necessario modificare la configurazione di WSUS 3.0 SP1 utilizzando la console di WSUS 3.0 SP1 o chiamando le API di WSUS 3.0 SP1.
  
#### I problemi di download non sono segnalati tempestivamente se le quote disco sono attivate
  
Se le quote disco sono attivate e la quota è stata raggiunta, problemi di download dell'aggiornamento nel server di WSUS potrebbero non essere segnalati tempestivamente. Per evitare questo problema, disattivare le quote disco o aumentare la quota.
  
#### Se WSUS 3.0 SP1 viene distribuito utilizzando SSL, potrebbe verificarsi un errore con codice "0x8024400a" nei computer client
  
Nei computer client possono a volte verificarsi errori con codice "0x8024400a" quando comunicano con un server di WSUS 3.0 SP1 utilizzando SSL. Per un aggiornamento che consente di risolvere questo problema, vedere l'articolo [KB 905422](http://go.microsoft.com/fwlink/?linkid=70593) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=70593.
  
#### L'account di dominio WSUS Administrators non verrà eliminato quando si disinstalla WSUS
  
Il gruppo WSUS Administrators viene creato come un account di dominio, non come un account locale, nei controller di dominio in modo che tutte le installazioni che utilizzano tale account di dominio vengano disattivate qualora l'account venisse eliminato al momento della disinstallazione di WSUS. Di conseguenza, disinstallando WSUS, l'account di dominio WSUS Administrators non verrà eliminato.
  
#### Se un server figlio viene trasformato in server padre, gli aggiornamenti del sito di catalogo devono essere reimportati
  
Quando si innalza un server figlio a server padre è necessario anche reimportare tutti gli aggiornamenti del sito di catalogo. In caso contrario, il sito non sarà in grado di sincronizzare le nuove revisioni dell'aggiornamento del sito di catalogo nell'ambito del server.
  
#### Se si utilizza IIS con SSL, l'accesso non crittografato è ancora possibile a meno che non sia selezionata l'opzione "Richiedi un canale protetto"
  
Se si configura IIS per l'utilizzo di SSL installando un certificato, sarà ancora possibile accedere al sito mediante un protocollo HTTP non crittografato a meno che non sia selezionata l'opzione **Richiedi un canale protetto**. Per ulteriori informazioni, vedere la documentazione relativa a [IIS](http://go.microsoft.com/fwlink/?linkid=98084) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=98084.
  
#### L'importazione del sito del catalogo potrebbe aver un esito negativo senza le autorizzazioni di lettura/scrittura per la cartella %windir%\\TEMP
  
Quando si esegue un'importazione del sito del catalogo, se l'account Servizio di rete non dispone di autorizzazioni di lettura/scrittura per la cartella %windir%\\TEMP, l'importazione potrebbe avere esito negativo e potrebbe essere visualizzato un messaggio di errore analogo al seguente: Impossibile elaborare la richiesta. ---&gt; Impossibile trovare il file "C:\\WINDOWS\\TEMP\\*NomeFileTemp*.dll".
  
#### Le prestazioni potrebbero essere lente durante la sincronizzazione tra WSUS 3.0 SP1 e un server di replica figlio che esegue WSUS 2.0
  
Se si installa WSUS 3.0 SP1 su un server padre e si tenta di sincronizzare un server di replica figlio che esegue WSUS 2.0, potrebbero verificarsi problemi di prestazioni. Per risolvere questo problema, vedere l'articolo [KB 910847](http://go.microsoft.com/fwlink/?linkid=70669) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=70669.
  
#### Se il server di posta non è attivo o non è raggiungibile, la funzionalità di notifica di posta elettronica non funzionerà e l'utente non riceverà alcuna segnalazione del problema
  
Se il server di posta elettronica della rete non è in linea, non verranno inviate notifiche di posta elettronica e il problema non verrà segnalato all'utente. Tuttavia verrà scritto l'evento 10052 (HealthCoreEmailNotificationRed) nel registro eventi.
  
#### Impostazioni modificate sul server padre non vengono trasferite immediatamente al server figlio
  
Quando la configurazione del server padre viene modificata, potrebbe essere necessario attendere del tempo prima che tali modifiche alla configurazione diventino effettive. Se viene modificata un'impostazione nel server padre, ad esempio viene selezionata una nuova lingua, e viene immediatamente avviata una sincronizzazione nel server figlio, la modifica non verrà visualizzata. Verrà invece trasferita al server figlio alla successiva sincronizzazione pianificata. Il tempo di attesa aumenta in base al numero di aggiornamenti presenti nel server padre.
  
#### La disinstallazione di WSUS 3.0 SP1 non rimuove l'istanza del database
  
Se WSUS 3.0 SP1 viene disinstallato, l'istanza del database verrà mantenuta. L'istanza potrebbe essere condivisa da più applicazioni, che potrebbero smettere di funzionare correttamente in seguito alla sua rimozione.
  
Se è necessario disinstallare Windows Internal Database, sarà possibile utilizzare i seguenti comandi per eseguire l'operazione:
  
(su piattaforme a 32 bit)
  
```  
msiexec /x {CEB5780F-1A70-44A9-850F-DE6C4F6AA8FB} callerid=ocsetup.exe  
```  
(su piattaforme a 64 bit)
  
```  
msiexec /x {BDD79957-5801-4A2D-B09E-852E7FA64D01} callerid=ocsetup.exe  
```  
Se si desidera disinstallare Windows Internal Database Service Pack 2 da Windows Server 2008, è possibile utilizzare Gestione server per eseguire l'operazione.
  
Tuttavia, la rimozione dell'applicazione potrebbe non rimuovere i file predefiniti con estensione .mdf e .ldf. Ciò impedirà di completare correttamente una successiva installazione di WSUS 3.0 SP1. Questi file possono essere eliminati dalla directory %windir%\\SYSMSI\\SSEE.
  
#### Se un server figlio modifica il server padre, gli aggiornamenti con stato "Sconosciuto" vengono riportati con stato "Non Applicabile"
  
Se un server figlio inizia la sincronizzazione da un server padre differente, gli aggiornamenti con stato **Sconosciuto** vengono riportati nel nuovo server padre con stato **Non Applicabile**. Questo stato è temporaneo e verrà corretto alla successiva segnalazione dello stato da parte del server figlio, dopo la sincronizzazione con i client.
  
#### Se in un server si verifica il timeout della pulizia guidata server quando viene eseguita su più server da una console remota, la connessione a tutti i server andrà perduta
  
È possibile eseguire la pulizia guidata server su più server da una singola console remota. Tuttavia, se in uno dei server si verifica il timeout della procedura di pulizia, la console perderà le sue connessioni a tutti i server. Nessun dato andrà perso, ma l'amministratore dovrà reimpostare la connessione remota a tutti i server.
  
#### L'avvio e l'interruzione della connessione in rapida successione determinano la visualizzazione del messaggio di errore "Nessun errore di sincronizzazione" nella configurazione guidata
  
Quando si configura WSUS, viene richiesta la connessione al server padre (Microsoft Update oppure il server padre nella intranet) per trasferire informazioni di base relative al server. Se si fa clic su **Avvia connessione** e immediatamente dopo su **Interrompi connessione**, verrà visualizzato il messaggio di errore inesatto "Nessun errore di sincronizzazione".
  
WSUS 3.0 SP1 su Windows Server 2008  
-----------------------------------
  
#### Versioni supportate
  
WSUS 3.0 SP1 supporta Windows Server 2008 nelle versioni a 32 bit e a 64 bit.
  
#### Prerequisiti
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Requisito</th>
<th style="border:1px solid black;" >Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Internet Information Services (IIS)</td>
<td style="border:1px solid black;">Eseguire l'installazione dal sistema operativo. Verificare che i componenti seguenti siano attivati:
<ul>
<li>Autenticazione di Windows<br />
<br />
</li>
<li>Contenuto statico<br />
<br />
</li>
<li>ASP.NET<br />
<br />
</li>
<li>Management Compatibility di IIS 6.0<br />
<br />
</li>
<li>Compatibilità metabase di IIS 6.0<br />
<br />
</li>
</ul></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft .NET Framework versione 2.0 Redistributable Package (x86)</td>
<td style="border:1px solid black;">Non necessario in Windows Server 2008; già installato come componente del sistema operativo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Management Console 3.0</td>
<td style="border:1px solid black;">Non necessario in Windows Server 2008; già installato come componente del sistema operativo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Report Viewer</td>
<td style="border:1px solid black;">Si tratta di un prerequisito per l'utilizzo dell'interfaccia utente di WSUS. Vedere Microsoft Report Viewer Redistributable 2005 nell'<a href="http://go.microsoft.com/fwlink/?linkid=70410">Area download Microsoft</a> all'indirizzo http://go.microsoft.com/fwlink/?LinkId=70410.</td>
</tr>
</tbody>
</table>
  
#### Utilizzo della Configurazione guidata impostazioni di sicurezza
  
Quando in Windows Server 2008 si esegue la Configurazione guidata impostazioni di sicurezza, è possibile selezionare il ruolo di WSUS ed abilitare le relative dipendenze. Per eseguire la Configurazione guidata impostazioni di sicurezza, fare clic su **Start**, scegliere **Strumenti di amministrazione** e fare clic su **Configurazione guidata impostazioni di sicurezza**.
  
I problemi noti riportati di seguito si verificano durante l'utilizzo della Configurazione guidata impostazioni di sicurezza assieme al ruolo di WSUS:
  
-   **Il servizio Database interno di Windows è abilitato anche se non può essere utilizzato da WSUS.** WSUS viene configurato per utilizzare un database, il database interno di Windows o il database di SQL Server. Se WSUS viene installato con SQL Server e si seleziona il ruolo di WSUS nella Configurazione guidata impostazioni di sicurezza, il servizio Database interno di Windows è abilitato se è installato nel computer, ma non viene utilizzato da WSUS. È necessario disabilitare il servizio Database interno di Windows, se si utilizza il database di SQL Server al posto del database interno di Windows.  
-   **Le regole firewall per WSUS in un sito Web personalizzato non vengono selezionate per impostazione predefinita.** Se si installa WSUS in un sito Web personalizzato (porta 8530 o 8531), le regole firewall richieste non vengono selezionate automaticamente anche se si seleziona il ruolo di WSUS nella Configurazione guidata impostazioni di sicurezza. Sarà necessario abilitare le regole firewall appropriate per WSUS in base all'eventuale configurazione di SSL (Secure Sockets Layer) per il server WSUS.
  
WSUS 3.0 SP1 su Windows Small Business Server 2003  
--------------------------------------------------
  
#### Se la radice virtuale IIS è limitata ad alcuni indirizzi IP o nomi dominio, il server di WSUS 3.0 SPI non sarà in grado di aggiornarsi automaticamente
  
È possibile che in alcune installazioni di Windows Small Business Server il sito Web IIS predefinito sia configurato in base all'impostazione **Limitazioni sull'indirizzo IP e sul nome di dominio**. In questo caso, il client di Windows Update nel server potrebbe non essere in grado di aggiornarsi automaticamente.
  
#### Problemi di integrazione relativi all'installazione di WSUS 3.0 SP1 in Small Business Server
  
-   Se in Windows Small Business Server 2003 viene utilizzato un server proxy ISA per l'accesso a Internet, sarà necessario digitare le informazioni seguenti nell'interfaccia utente **Impostazioni**: **impostazioni del server proxy, nome del server proxy e porta**.  
-   Se ISA utilizza l'Autenticazione Windows, le credenziali del server proxy dovranno essere digitate nel formato *DOMINIO*/*utente*. L'utente deve appartenere al gruppo degli utenti di Internet.
  
#### Se alla rete in uso è stata aggiunta una sottorete senza utilizzare le procedure guidate di Windows Small Business Server, sarà necessario attenersi alla procedura seguente
  
Il processo di installazione del server WSUS installa due directory principali virtuali IIS nel server: SelfUpdate e ClientWebService. Il processo di installazione salva, inoltre, alcuni file nella home directory del sito Web predefinito (sulla porta 80), che consente ai computer client di eseguire automaticamente l'aggiornamento attraverso il sito Web predefinito. Per impostazione predefinita, il sito Web predefinito è configurato in modo da negare l'accesso a tutti gli indirizzi IP diversi da localhost o da sottoreti specifiche associate al server. Di conseguenza, i computer client che non sono in host locali o in quelle sottoreti specifiche non possono eseguire l'aggiornamento automatico. Se alla propria rete è stata aggiunta una sottorete senza utilizzare le procedure guidate di Microsoft Windows Small Business Server, sarà necessario attenersi alla seguente procedura:
  
1.  In Gestione server espandere **Gestione Avanzata**, **Internet Information Services**, **Siti web**, **Sito Web predefinito**, fare clic con il pulsante destro del mouse sulla directory virtuale **Selfupdate**, quindi scegliere **Proprietà**.  
2.  Fare clic su **Protezione Directory**.  
3.  In **Limitazioni sull'indirizzo IP e sul nome di dominio** fare clic su **Modifica**, quindi selezionare **consentito**.  
4.  Fare clic su **OK**, fare clic con il pulsante destro del mouse sulla directory virtuale **ClientWebService** e scegliere **Proprietà**.  
5.  Fare clic su **Protezione Directory**.  
6.  In **Limitazioni sull'indirizzo IP e sul nome di dominio** fare clic su **Modifica**, quindi selezionare **consentito**.
  
Copyright  
---------
  
Le informazioni contenute nel presente documento, inclusi gli URL e altri riferimenti a siti Web, sono soggette a modifiche senza preavviso. Se non specificato diversamente, ogni riferimento a società, organizzazioni, prodotti, nomi di dominio, indirizzi di posta elettronica, loghi, persone, località ed eventi utilizzato negli esempi è puramente casuale e ha il solo scopo di illustrare l'uso del prodotto Microsoft. Il rispetto di tutte le applicabili leggi in materia di copyright è esclusivamente a carico dell'utente. Fermi restando tutti i diritti coperti da copyright, nessuna parte di questo documento potrà comunque essere riprodotta o inserita in un sistema di riproduzione o trasmessa in qualsiasi forma e con qualsiasi mezzo (in formato elettronico, meccanico, fotocopia, tramite registrazione o latro) per qualsiasi scopo, senza il permesso scritto di Microsoft Corporation.
  
Microsoft può essere titolare di brevetti, domande di brevetto, marchi, copyright, o altri diritti di proprietà intellettuale relativi all'oggetto del presente documento. Salvo quanto espressamente previsto in un contratto scritto di licenza Microsoft, la consegna del presente documento non implica la concessione di alcuna licenza su tali brevetti, marchi, copyright, o altra proprietà intellettuale.
  
© 2007 Microsoft Corporation. Tutti i diritti riservati.
  
Microsoft, SQL Server, Windows, e Windows Server sono marchi o marchi registrati di Microsoft Corporation negli Stati Uniti e/o negli altri paesi.
  
Tutti gli altri marchi appartengono ai rispettivi proprietari.
