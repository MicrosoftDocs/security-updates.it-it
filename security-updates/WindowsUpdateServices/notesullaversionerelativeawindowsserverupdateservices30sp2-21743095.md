---
TOCTitle: 'Note sulla versione relative a Windows Server Update Services 3.0 SP2'
Title: 'Note sulla versione relative a Windows Server Update Services 3.0 SP2'
ms:assetid: 'b3723422-489d-47b7-abfa-663353647da0'
ms:contentKeyID: 21743095
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd939886(v=WS.10)'
---

Note sulla versione relative a Windows Server Update Services 3.0 SP2
=====================================================================

Le presenti note sulla versione descrivono la versione di Windows Server Update Services 3.0 Service Pack 2 (WSUS 3.0 SP2). In questo documento sono presenti le sezioni seguenti:

1.  Novità di questa versione
2.  Requisiti di sistema per WSUS 3.0 SP2 Installazione del server
3.  Prerequisiti di configurazione e procedure consigliate per il server WSUS
4.  Prerequisiti per Windows Small Business Server
5.  Requisiti di sistema per l'installazione della console remota di WSUS 3.0 SP2
6.  Requisiti di sistema per l'installazione del client
7.  Requisiti di aggiornamento e suggerimenti
8.  Installazione di WSUS 3.0 SP2
9.  Parametri di installazione dalla riga di comando per le installazioni automatiche di WSUS 3.0 SP2
10. Problemi noti

Novità di questa versione
-------------------------

-   Integrazione con Windows Server 2008 R2.
-   Supporto della funzione BranchCache in Windows Server 2008 R2.
-   Supporto per i client Windows 7.
-   Miglioramenti client Agente di Windows Update (WUA). Il nuovo client Agente di Windows Update offre una serie di miglioramenti delle prestazioni, dell'esperienza utente, oltre a un insieme di correzioni dei bug basate sui suggerimenti dei clienti.
    -   Il tempo di analisi del client è più veloce rispetto alle versioni precedenti.
    -   I computer gestiti dai server WSUS sono in grado di eseguire analisi 'ambito' rispetto gli stessi server WSUS, anziché eseguire un'analisi completa. Il risultato sarà, in ordine di grandezza, analisi più veloci per le applicazioni che utilizzano API Microsoft Update come Windows Defender.
    -   I miglioramenti dell'esperienza utente dell'Agente di Windows Update (WUA) aiutano gli utenti a organizzare meglio gli aggiornamenti e a fornire maggiore chiarezza sul valore e il comportamento dell'aggiornamento.
    -   Le immagini dei computer verranno visualizzate in maniera più chiara nella console WSUS. Per ulteriori informazioni, vedere l'articolo intitolato [Immagine non visualizzata nella console WSUS su un computer basato su Windows 2000, Windows Server 2003, o Windows XP configurato utilizzando Windows 2000, Windows Server 2003, o Windows XP](http://go.microsoft.com/fwlink/?linkid=159749).
-   Nuove funzionalità:
    -   Le regole di approvazione automatica ora permettono di specificare la data e l'ora di scadenza approvazione per tutti i computer o per gruppi preselezionati di computer.
    -   La gestione migliore della selezione della lingua sui server figli include un nuovo messaggio di avviso che compare se si scaricano aggiornamenti solo per le lingue specificate.
    -   I nuovi rapporti sullo stato degli aggiornamenti e del computer consentono di filtrare gli aggiornamenti approvati per l'installazione. Questi aggiornamenti possono essere eseguiti dalla console WSUS, oppure è possibile utilizzare l'API (Application Programming Interface) per integrare questa funzionalità nei propri rapporti.
-   L'interfaccia utente è compatibile con Service Pack 1 e Service Pack 2 per WSUS 3.0 sia su client che su server.
-   Aggiornamenti software.
-   In questa versione sono stati risolti alcuni Problemi noti dell'Agente di Windows Update:
    1.  WSUS 3.0 SP2 e Windows 7 includono una nuova versione dell'Agente di Windows Update (per Windows XP, Windows Vista, Windows Server 2000, Windows Server 2003 e Windows Server 2008). Questa versione risolve i seguenti problemi: Fallimento della chiamata di API da chiamanti su sistemi non locali in una sessione non interattiva.
    2.  Problema risolto dalla versione 7.2.6001.788 dell'Agente di Windows Update. Questo aggiornamento risolve i seguenti problemi: Se si provano a installare 80 o più aggiornamenti contemporaneamente dalla pagina Windows Update o dalla pagina Web di Microsoft Update potrebbe presentarsi un codice di errore 0x80070057.
    3.  Miglioramenti implementati e problemi risolti dalla versione 7.2.6001.784 dell'Agente di Windows Update. Questo aggiornamento include quanto segue: Migliorati tempi di scansione di Windows Update, velocità di consegna degli aggiornamenti della firma, abilitato il supporto per la funzionalità di reinstallazione di Windows Installer e migliorata la messaggistica di errore.

<span id="BKMK_SysReqWSUS30SP2"></span>
Requisiti di sistema per WSUS 3.0 SP2 Installazione del server
--------------------------------------------------------------

Il presente paragrafo descrive i requisiti software e hardware necessari per l'installazione di WSUS 3.0 SP2.

### Prerequisiti software server WSUS

-   È necessario avere installato uno dei seguenti sistemi operativi supportati:
    -   Windows Server 2008 R2
    -   Windows Server 2008 SP1 o versioni successive
<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="100%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><img src="images/Dd939886.Warning(WS.10).gif" />Figyelmeztetés</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;">Se WSUS 3.0 SP2 è installato su Windows Server 2008 prima di eseguire l'aggiornamento a Windows Server 2008 R2, l'aggiornamento a Windows Server 2008 R2 non verrà eseguito correttamente. Vedere la sezione <a href="#bkmk_knownissues">Problemi noti</a> per ulteriori informazioni.
        <p></p></td>
        </tr>
        </tbody>
        </table>
<p> </p>

    -   Windows Server 2003 SP1 o versioni successive
    -   Windows Small Business Server 2008
    -   Windows Small Business Server 2003

    Per Windows Small Business Server si applicano prerequisiti supplementari. Per ulteriori informazioni, vedere il paragrafo “Prerequisiti per Windows Small Business Server”.
-   Internet Information Services (IIS) 6.0 o versioni successive
-   Microsoft .NET Framework 2.0 o versioni successive
-   È necessario avere installato uno dei seguenti database supportati:
    -   Microsoft SQL Server 2008 Standard o Enterprise Edition
    -   Microsoft SQL Server 2005 SP3 o versioni successive
    -   Database interno di Windows

    Se non è installata nessuna delle versioni supportate di SQL Server, l'Installazione guidata di WSUS 3.0 SP2 installerà il Database interno di Windows.
-   Microsoft Management Console 3.0
-   Microsoft Report Viewer Redistributable 2008

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><img src="images/Dd939886.Important(WS.10).gif" />Fontos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2008 R2 richiede WSUS 3.0 SP2. Se si installa Windows Server 2008 R2 allora bisogna installare WSUS 3.0 SP2. Non installare WSUS 3.0 SP1 su Windows Server 2008 R2.
<p></p>
WSUS 3.0 SP2 non è supportato per l'utilizzo con Servizi terminal nel front-end server in una configurazione di SQL remoto.
<p></p></td>
</tr>
</tbody>
</table>
<p> </p>

### Prerequisiti software Console di amministrazione WSUS

-   Uno dei seguenti sistemi operativi supportati: Windows Server 2008 R2, Windows Server 2008, Windows Server 2003 SP2 o versioni successive, Windows Small Business Server 2008 o Windows Small Business Server 2003, Windows Vista oppure Windows XP SP2
-   Microsoft .NET Framework 2.0 o versioni successive
-   Microsoft Management Console 3.0
-   Microsoft Report Viewer Redistributable 2008

### Requisiti hardware minimi del server WSUS

Il seguente elenco contiene i requisiti hardware minimi necessari per un'installazione base del server. Consultare la guida alla distribuzione di WSUS 3.0 SP2 alla pagina [http://go.microsoft.com/fwlink/?LinkId=139832](http://go.microsoft.com/fwlink/?linkid=139832) per un elenco completo delle configurazioni hardware supportate.

-   La partizione di sistema e la partizione su cui WSUS 3.0 SP2 è installato devono essere formattate con il file system NTFS.
-   1 GB minimo di spazio libero sulla partizione di sistema.
-   2 GB minimo di spazio libero per il volume in cui verranno archiviati i file del database.
-   20 GB minimo di spazio libero per il volume in cui verrà archiviato il contenuto, si consigliano 30 GB.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><img src="images/Dd939886.Important(WS.10).gif" />Fontos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Non è possibile installare WSUS 3.0 su unità compresse.
<p></p></td>
</tr>
</tbody>
</table>
<p> </p>

Prerequisiti di configurazione e procedure consigliate per il server WSUS
-------------------------------------------------------------------------

Prima di installare WSUS 3.0 SP2, completare tutte le operazioni applicabili di questo paragrafo.

### IIS

-   Nella pagina Web Server (IIS) Role Services di Gestione server, installare ogni funzionalità richiesta, tutti i servizi dei ruoli IIS predefiniti e i seguenti servizi dei ruoli: **ASP.NET**, **Autenticazione di Windows**, **Compressione dinamica del contenuto** e **Management Compatibility di IIS 6**.
-   Se IIS viene eseguito in modalità di isolamento di IIS 5.0, l'installazione non avrà esito positivo. Disattivare la modalità di isolamento IIS 5.0 prima di installare WSUS 3.0 SP2.
-   Se uno o più componenti di IIS sono installati in modalità di compatibilità a 32 bit su una piattaforma a 64 bit, l'installazione di WSUS 3.0 SP2 potrebbe avere esito negativo. Tutti i componenti IIS devono essere installati in modalità nativa su piattaforme a 64 bit.

### Server proxy

WSUS 3.0 SP2 permette ai server proxy di supportare solo l'HTTP. La procedura migliore consiste nel configurare un secondo server proxy che supporti l'HTTPS utilizzando la riga di comando (**wsusutil configuresslproxy**) prima di configurare il server WSUS dalla Configurazione guidata o dalla Console di amministrazione.

### Siti Web in funzione sulla porta 80

Se sono presenti due o più siti Web in funzione sulla porta 80 (per esempio Windows SharePoint Services), prima di installare WSUS cancellarli tutti tranne uno. Se non si esegue questa operazione, i client del server potrebbero non aggiornarsi automaticamente.

### Programmi antivirus

Quando si installa WSUS 3.0 potrebbe essere necessario disattivare i programmi antivirus prima di riuscire a eseguire l'installazione. Dopo aver disattivato i software antivirus, riavviare il computer prima di installare WSUS. Il riavvio del computer impedisce che i file vengano bloccati quando il processo di installazione deve accedervi. Al termine dell'installazione, assicurarsi di riattivare il software antivirus. Visitare il sito Web del produttore del software antivirus per informazioni sulle procedure corrette relative alla disattivazione e riattivazione del software antivirus e sulla versione.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><img src="images/Dd939886.Caution(WS.10).gif" />Vigyázat!</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Questa soluzione alternativa potrebbe rendere il computer o la rete in uso più vulnerabile agli attacchi da parte di utenti malintenzionati o di software dannoso, ad esempio virus. Non è consigliabile questa soluzione alternativa ma tali informazioni vengono fornite in modo che sia possibile implementarla a propria discrezione. Utilizzare questa soluzione alternativa a proprio rischio e pericolo.
<p></p>
Il software antivirus aiuta a proteggere il computer dai virus. Non scaricare o aprire file provenienti da origini non attendibili, visitare siti Web non attendibili o aprire allegati di posta elettronica quando il programma antivirus è disattivato.
<p></p></td>
</tr>
</tbody>
</table>
<p> </p>

### Opzione Nested Triggers su SQL Server

Se si desidera utilizzare un database di SQL Server come archivio dati di Windows Server Update Services, l'amministratore SQL Server dovrà verificare che l'opzione relativa ai nested triggers venga attivata sul server prima che l'amministratore di WSUS installi WSUS 3.0 SP2. Questa opzione è attivata per impostazione predefinita ma può essere disattivata da un amministratore di SQL Server. L'installazione di WSUS 3.0 SP2 attiva l'opzione RECURSIVE\_TRIGGERS, opzione specifica di un database. Comunque, l'installazione di WSUS 3.0 SP2 non attiva l'opzione nested triggers, che è un'opzione globale del server.

### Limiti e requisiti per SQL remoto

WSUS 3.0 SP2 supporta l'esecuzione di software di una versione compatibile di SQL Server su un computer separato da quello su cui è in esecuzione l'applicazione WSUS 3.0 SP2. I seguenti requisiti si applicano all'installazione di SQL remoto.

-   Un server configurato come controller di dominio non può essere utilizzato come back-end del corrispettivo SQL remoto.
-   Impossibile eseguire i Servizi terminal sul computer indicato come front-end server di un'installazione di SQL remoto.
-   Entrambi computer front-end e computer back-end devono essere sotto al dominio di Active Directory. Se i computer front-end e back-end sono sotto domini diversi, prima dell'esecuzione dell'installazione di WSUS stabilire un certificato di attendibilità interdominio.
-   Se WSUS 2.0 è già installato in configurazione SQL remoto e si desidera aggiornarsi a WSUS 3.0 SP2, prima di installare WSUS:
    1.  Disinstallare WSUS 2.0 (tramite **Installazione applicazioni** sul Pannello di controllo), accertandosi comunque che il database esistente rimanga intatto.
    2.  Installare SQL Server 2005 SP2 o SQL Server 2008 e aggiornare il database esistente.

### IIS viene riavviato durante l'installazione di WSUS 3.0 SP2

Il programma di installazione di WSUS 3.0 SP2 riavvia IIS senza notifica, ciò potrebbe influire negativamente sui siti Web esistenti nell'ambito dell'organizzazione. La procedura migliore sarebbe avvisare in anticipo dell'installazione le parti coinvolte. Se IIS non è in esecuzione, verrà avviato dal programma di installazione di WSUS 3.0 SP2.

Prerequisiti per Windows Small Business Server
----------------------------------------------

Se si installa WSUS 3.0 SP2 su Windows Small Business Server, si applicano i seguenti prerequisiti.

### Se la Directory principale virtuale IIS è limitata ad alcuni indirizzi IP o nomi di dominio

È possibile che in alcune installazioni di Windows Small Business Server il sito Web IIS predefinito sia configurato in base all'impostazione **Limitazioni sull'indirizzo IP e sul nome di dominio**. In questo caso, il Client di Windows Update sul server potrebbe non riuscire ad aggiornarsi. Prima di installare WSUS 3.0 SP2, eliminare tale limitazione.

### Se si utilizza un server proxy ISA

-   Se Windows Small Business Server utilizza un server proxy ISA per l'accesso a Internet, digitare **impostazioni server proxy, nome server proxy e porta** nell'interfaccia utente **Impostazioni**.
-   Se ISA sta utilizzando l'Autenticazione Windows, inserire le credenziali del server proxy nel modulo *DOMINIO*\\*nome utente*. L'utente deve essere un membro del gruppo Utenti di Internet.

### Se è stata aggiunta una sottorete alla rete senza seguire le procedure guidate di Windows Small Business Server

Il processo di installazione del server di WSUS installa due directory principali virtuali IIS nel server: SelfUpdate e ClientWebService. Il programma di installazione colloca inoltre alcuni file nella directory principale del sito Web predefinito (sulla porta 80), che consentono ai computer client di eseguire automaticamente l'aggiornamento attraverso il sito Web predefinito. Per impostazione predefinita, il sito Web predefinito è configurato in modo da negare l'accesso a tutti gli indirizzi IP diversi da localhost o da sottoreti specifiche associate al server. Di conseguenza, i computer client che non sono sul localhost o in quelle sottoreti specifiche non possono eseguire l'aggiornamento automatico. Se alla rete in uso è stata aggiunta una sottorete senza seguire le procedure guidate di Small Business Server, sarà necessario attenersi alla procedura seguente:

1.  In Gestione server, espandere **Gestione avanzata**, **Internet Information Services**, **Siti Web** e **Sito Web predefinito**, fare clic con il pulsante destro del mouse sulla directory virtuale **Selfupdate** e quindi fare clic su **Proprietà**.
2.  Fare clic su **Protezione directory**.
3.  In **Limitazioni sugli indirizzi IP e sui nomi di dominio** fare clic su **Modifica** e quindi su **Accesso concesso**.
4.  Fare clic su **OK**, fare clic con il pulsante destro del mouse sulla directory virtuale **ClientWebService** e quindi fare clic su **Proprietà**.
5.  Fare clic su **Protezione directory**.
6.  In **Limitazioni sugli indirizzi IP e sui nomi di dominio** fare clic su **Modifica** e quindi su **Accesso concesso**.

Requisiti di sistema per l'installazione della console remota di WSUS 3.0 SP2
-----------------------------------------------------------------------------

La Console remota di WSUS 3.0 SP2 può essere installata su uno dei seguenti sistemi operativi:

-   Windows Server 2008 R2, Windows Server 2008 SP1 o versioni successive, Windows Server 2003 SP2 o versioni successive, Windows Small Business Server 2003, Windows Small Business Server 2005 o Windows Small Business Server 2008, Windows Vista o Windows XP Professional SP3 o versioni successive.

Requisiti di sistema per l'installazione del client di WSUS
-----------------------------------------------------------

Aggiornamenti automatici, il software del client di WSUS può essere installato su uno dei seguenti sistemi operativi:

-   Windows Server 2008 R2, Windows Server 2008 SP1 o versioni successive, Windows Server 2003 SP2 o versioni successive, Windows Small Business Server 2003, Windows Small Business Server 2005 o Windows Small Business Server 2008, Windows Vista, Windows XP Professional RTM, Windows XP Professional SP1, Windows XP Professional SP2, Windows XP Professional SP3 o versioni successive, Windows 2000 SP4 o client Windows 7.

Requisiti di aggiornamento e suggerimenti
-----------------------------------------

Le seguenti versioni di WSUS possono essere aggiornate a WSUS 3.0 SP2 e non richiedono la disinstallazione della versione precedente:

-   WSUS 2.0, 2.0 SP1, 3.0 e 3.0 SP1.

Gli aggiornamenti dalla versione WSUS 1.0 alla 3.0 SP2 non sono supportati. Prima di installare WSUS 3.0 SP2, disinstallare Software Update Services (SUS) 1.0.

Windows Server 2008 R2 richiede WSUS 3.0 SP2. Se si installa Windows Server 2008 R2 allora bisogna installare WSUS 3.0 SP2. Non installare WSUS 3.0 SP1 su Windows Server 2008 R2.

#### Prima di aggiornare a WSUS 3.0 SP2

1.  Controllare gli errori recenti nei registri eventi, i problemi di sincronizzazione tra i server figli e i server padre e i problemi inerenti ai rapporti del client. Prima dell'aggiornamento, risolvere questi problemi.

2.  Se lo si desidera, si può eseguire DBCC CHECKDB per accertarsi che il database di WSUS sia indicizzato correttamente. Per ulteriori informazioni su DBCC CHECKDB, fare riferimento a [DBCC CHECKDB](http://go.microsoft.com/fwlink/?linkid=86948).

3.  Backup del database di WSUS L'installazione di WSUS 3.0 SP2 aggiungerà il nuovo database alla directory predefinita, ossia *unità*\\WSUS (*unità* è l'unità locale NTFS con più spazio libero). Se in tale directory è presente un backup di database precedente, quest'ultimo verrà sovrascritto. La procedura migliore consiste nel salvare un backup del database della versione corrente di WSUS in una posizione diversa prima di aggiornare a WSUS 3.0 SP2.

4.  Se la porta utilizzata da WSUS (ossia, se non si utilizza l'utilità Wsusutil) è stata cambiata manualmente e attualmente è in esecuzione SUS 1.0 o WSUS 2.0. avviare il sito Web predefinito prima di disinstallare SUS 1.0 o WSUS 2.0 a 64 bit.

5.  Se sono aperte delle connessioni a un database di WSUS esistente (per esempio, se SQL Server Management Studio è aperto), l'installazione potrebbe avere esito negativo. Prima di installare WSUS 3.0 SP2, chiudere tutte le connessioni.

### Ripristino dopo l'esito negativo di un aggiornamento

Se si aggiorna da una versione precedente di WSUS a WSUS 3.0 SP2 e l'aggiornamento ha esito negativo (per qualsiasi motivazione diversa da un aggiornamento non supportato da SUS 1.0), eseguire le seguenti operazioni.

1.  Reinstallare la versione precedente di WSUS.
2.  Ripristinare il database dal backup eseguito prima di provare l'aggiornamento. Non è possibile portare a termine un aggiornamento se è ancora presente un database di WSUS 3.0 SP2 da una precedente installazione. Nella maggior parte dei casi, WSUS crea automaticamente un backup. Vedere il file WSUSSetup.log per trovarlo.
3.  Rivedere i log per determinare la causa dell'esito negativo dell'installazione e risolvere il problema.
4.  Installare WSUS 3.0 SP2

### Se si modifica il nome del computer prima di eseguire l'aggiornamento a WSUS 3.0 SP2, quest'ultimo potrebbe avere esito negativo

Se si modifica il nome del computer dopo l'installazione di WSUS 2.0 e prima di eseguire l'aggiornamento a WSUS 3.0 SP2, quest'ultimo può avere esito negativo.

Utilizzare lo script seguente per rimuovere e aggiungere nuovamente i gruppi ASPNET e Amministratori WSUS. Eseguire quindi nuovamente l'aggiornamento.

        ```

### Se è stata effettuata la migrazione da MSDE a SQL Server 2008 o SQL Server 2005 su WSUS 2.0, bisognerà modificare un valore del registro

Se è presente l'installazione di WSUS 2.0, con migrazione a SQL Server 2008 o SQL Server 2005, bisogna cambiare il valore di **HKLM\\SOFTWARE\\Microsoft\\Update Services\\Server\\Setup\\WmsdeInstalled** da 1 a 0. Se tale operazione non viene eseguita, l'aggiornamento a WSUS 3.0 SP2 non avrà esito positivo.

### Se si disinstalla WSUS 3.0 SP2 e si mantengono tuttavia i file di log, potrebbero verificarsi problemi di autorizzazione dopo la reinstallazione

Quando si disinstalla WSUS 3.0 SP2, è possibile mantenere i file di log dell'installazione. Quando si reinstalla WSUS 3.0 SP2, i file di log precedenti perdono le rispettive autorizzazioni (in genere solo per gli Amministratori WSUS). La procedura migliore sarebbe confermare le autorizzazioni su questi file di log dopo l'installazione.

### Se i client WSUS 2.0 presentano aggiornamenti in stato "Non applicabile", per un breve istante gli aggiornamenti compariranno come "Sconosciuto" dopo l'aggiornamento a WSUS 3.0 SP2

Se il server WSUS 2.0 esistente ha client con aggiornamenti in stato **Non applicabile**, per un breve istante gli aggiornamenti compariranno come **Sconosciuto** dopo l'aggiornamento a WSUS 3.0 SP2. Lo stato dell'aggiornamento tornerà a **Non applicabile** alla prossima scansione del client.

Installazione di WSUS 3.0 SP2
-----------------------------

La guida di installazione passo-passo per WSUS alla pagina [http://go.microsoft.com/fwlink/?LinkId=139836](http://go.microsoft.com/fwlink/?linkid=139836) fornisce le istruzioni per l'installazione di WSUS 3.0 SP2 utilizzando Server Manager di Windows o il file WSUSSetup.exe.

Per ulteriori informazioni su come installare e utilizzare WSUS, vedere:

Guida alla distribuzione di WSUS alla pagina [http://go.microsoft.com/fwlink/?LinkId=139832](http://go.microsoft.com/fwlink/?linkid=139832).

Guida operativa di WSUS alla pagina [http://go.microsoft.com/fwlink/?LinkId=139838](http://go.microsoft.com/fwlink/?linkid=139838).

Parametri di installazione da linea di comando per le installazioni automatiche di WSUS 3.0 SP2
-----------------------------------------------------------------------------------------------

È possibile eseguire installazioni automatiche di WSUS 3.0 SP2 utilizzando il programma di installazione della riga di comando di WSUS. Nella tabella seguente vengono riportati i parametri della riga di comando per l'installazione di WSUS 3.0 SP2.

###  

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opzione</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p><strong>/q</strong></p></td>
<td style="border:1px solid black;"><p>Esegui installazione silenziosa.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p><strong>/u</strong></p></td>
<td style="border:1px solid black;"><p>Disinstalla.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p><strong>/p</strong></p></td>
<td style="border:1px solid black;"><p>Controllo dei prerequisiti. Controllare il sistema e segnalare i prerequisiti mancanti.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p><strong>/?, /h</strong></p></td>
<td style="border:1px solid black;"><p>Visualizza i parametri da linea di comando e la loro descrizione.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p><strong>/g</strong></p></td>
<td style="border:1px solid black;"><p>Aggiorna da una versione precedente di WSUS. (Gli aggiornamenti dalla versione 1.0 non sono supportati). L'unico parametro valido per questa opzione è /q (installazione silenziosa). L'unica proprietà valida per questa opzione è DEFAULT_WEBSITE.</p></td>
</tr>
</tbody>
</table>
  
Nella tabella seguente vengono indicate le proprietà della riga di comando per WSUS 3.0 SP2.
  
###  

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Proprietà</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>CONTENT_LOCAL</p></td>
<td style="border:1px solid black;"><p>0=contenuto ospitato localmente, 1=contenuto ospitato su Microsoft Update</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>CONTENT_DIR</p></td>
<td style="border:1px solid black;"><p>Percorso della directory contenuto. Quello predefinito è <em>WSUSInstallationDrive\WSUS\WSUSContent</em>, dove <em>WSUSInstallationDrive</em> è l'unità locale con più spazio libero su disco.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>WYUKON_DATA_DIR</p></td>
<td style="border:1px solid black;"><p>Percorso della directory dati del Database interno di Windows.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>SQLINSTANCE_NAME</p></td>
<td style="border:1px solid black;"><p>Il nome deve essere indicato nel formato <em>NomeServer</em>\<em>NomeIstanzaSQL</em>. Se l'istanza del database si trova nel computer locale, utilizzare la variabile di ambiente %COMPUTERNAME%. Se non è già disponibile un'istanza esistente, il valore predefinito è %COMPUTERNAME%\WSUS.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>DEFAULT_WEBSITE</p></td>
<td style="border:1px solid black;"><p>0=porta 8530, 1=porta 80</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>PREREQ_CHECK_LOG</p></td>
<td style="border:1px solid black;"><p>Percorso e nome del file di log</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>CONSOLE_INSTALL</p></td>
<td style="border:1px solid black;"><p>0=installare il server WSUS, 1=installare solo la console</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>ENABLE_INVENTORY</p></td>
<td style="border:1px solid black;"><p>0=non installa, 1=installa funzionalità inventario</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>DELETE_DATABASE</p></td>
<td style="border:1px solid black;"><p>0=mantieni database, 1=rimuovi i file del database</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>DELETE_CONTENT</p></td>
<td style="border:1px solid black;"><p>0=mantieni contenuto, 1=rimuovi file di contenuto</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>DELETE_LOGS</p></td>
<td style="border:1px solid black;"><p>0=mantieni log, 1=rimuovi file di log (utilizzati con lo switch di installazione /u)</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>CREATE_DATABASE</p></td>
<td style="border:1px solid black;"><p>0=usa database corrente, 1=crea database</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>PROGRESS_WINDOW_HANDLE</p></td>
<td style="border:1px solid black;"><p>Handle della finestra per restituire i messaggi di stato di Windows Installer</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>MU_ROLLUP</p></td>
<td style="border:1px solid black;"><p>1=partecipa al programma Analisi utilizzo Microsoft Update, 0=non partecipa programma di miglioramento di Microsoft Update</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>FRONTEND_SETUP</p></td>
<td style="border:1px solid black;"><p>1=non scrive il precorso del contenuto nel database, 0=scrive il percorso del contenuto nel database (per NLB)</p></td>
</tr>
</tbody>
</table>
  
### Esempio di sintassi
  
```  
WSUSSetup.exe /q DEFAULT\_WEBSITE=0 (installa in modalità non interattiva utilizzando la porta 8530) WSUSSetup.exe /q /u (disinstalla WSUS)  
```
<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><img src="images/Dd939886.Important(WS.10).gif" />Fontos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Se si installa WSUS 3.0 SP2 in modalità non interattiva (/q) e il computer non dispone di tutti i prerequisiti installati, l'installazione genererà un file denominato WSUSPreReqCheck.xml che verrà salvato nella directory %TEMP%.
<p></p></td>
</tr>
</tbody>
</table>
<p> </p>

<span id="BKMK_KnownIssues"></span>
Problemi noti
-------------

-   Dopo il completamento dell'installazione guidata di WSUS, all'utente viene richiesto di fare clic su **Fine**. In rari casi, compare una finestra di dialogo di errore che contiene il seguente messaggio: "**Errore durante la comunicazione con il server. La procedura guidata deve essere chiusa. È possibile riavviare la Configurazione guidata server WSUS dalla pagina Opzioni della console WSUS**". Per accertarsi che le opzioni di installazione siano state salvate, aprire la pagina **Opzioni** sulla console di amministrazione di WSUS e confermare le impostazioni di ogni sezione.
-   **Le versioni localizzate del client dell'Agente di Windows Update (WUA) saranno rilasciate successivamente rispetto alla versione di WSUS 3.0 SP2**. La causa risiede in una dipendenza dalla pianificazione della localizzazione di Windows 7. Nell'intervallo di tempo tra la versione di WSUS 3.0 SP2 e la versione localizzata del client WUA, il client WUA supporta solo cinque lingue (inglese, tedesco, francese, spagnolo e giapponese).
-   **I nuovi rapporti sullo stato degli aggiornamenti e del computer, introdotti in questa versione SP2, non sono funzionali in un ambiente dove i server figlio WSUS 3.0 SP1 sono gestiti da un server WSUS 3.0 SP2**. Se i nuovi rapporti vengono eseguiti per un server SP1, viene visualizzato il seguente messaggio di errore, "Errore durante la creazione del rapporto. Provare a eseguire nuovamente il rapporto. Se il problema persiste, contattare l'amministratore di rete". Se eseguendo nuovamente il rapporto il problema non viene risolto, il problema potrebbe non essere relativo alla rete. I nuovi rapporti dipendono dalla funzionalità API che non esiste in SP1; tuttavia, la console di amministrazione SP2 non blocca i nuovi rapporti durante la gestione di un server SP1.
-   **L'aggiornamento a WSUS 3.0 SP2 ha esito negativo quando SSL viene configurato senza un nome certificato**. Se si configura SSL viene richiesto un nome certificato.
-   **L'esecuzione di WSUS 3.0 SP2 Belső Windows-adatbázis installato su Windows Server 2008 impedisce l'aggiornamento a Windows Server 2008 R2**. Prima di continuare l'aggiornamento a Windows Server 2008 R2, viene visualizzato un messaggio di errore del rapporto compatibilità che richiede di disattivare il Belső Windows-adatbázis. È necessario eseguire l'aggiornamento di Belső Windows-adatbázis prima che l'aggiornamento a Windows Server 2008 R2 possa continuare. Vedere [Come ottenere l'ultimo Service Pack per il database interno di Windows](http://go.microsoft.com/fwlink/?linkid=162104) (http://go.microsoft.com/fwlink/?LinkId=162104) per istruzioni e ulteriori informazioni sull'aggiornamentoBelső Windows-adatbázis.

Informazioni sul copyright
--------------------------

Le informazioni contenute nel presente documento, inclusi gli URL o altri riferimenti a siti Web, sono soggette a modifiche senza preavviso. Se non specificato diversamente, ogni riferimento a società, organizzazioni, prodotti, nomi di dominio, indirizzi di posta elettronica, logo, persone, località ed eventi utilizzati negli esempi è puramente causale e ha il solo scopo di illustrare l'uso del prodotto Microsoft. Il rispetto di tutte le applicabili leggi in materia di copyright è esclusivamente a carico dell'utente. Fermi restando tutti i diritti coperti da copyright, nessuna parte di questo documento potrà comunque essere riprodotta o inserita in un sistema di riproduzione o trasmessa in qualsiasi forma e con qualsiasi mezzo (in formato elettronico, meccanico, su fotocopia, come registrazione o altro) per qualsiasi scopo, senza il permesso scritto di Microsoft Corporation.

Microsoft può essere titolare di brevetti, domande di brevetto, marchi, copyright o altri diritti di proprietà intellettuale relativi all'oggetto del presente documento. Salvo quanto espressamente previsto in un contratto scritto di licenza Microsoft, la consegna del presente documento non implica la concessione di alcuna licenza su tali brevetti, marchi, copyright o altra proprietà intellettuale.

© 2009 Microsoft Corporation. Tutti i diritti riservati.

Microsoft, Active Directory, ActiveX, Authenticode, Excel, InfoPath, Internet Explorer, MSDN, Outlook, Visual Studio, Win32, Windows, Windows Server e Windows Vista sono marchi delle società del gruppo Microsoft.

Altri nomi di prodotti e società citati nel presente documento possono essere marchi dei rispettivi proprietari.
