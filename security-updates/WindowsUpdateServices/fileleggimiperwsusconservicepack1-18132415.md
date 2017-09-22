---
TOCTitle: File Leggimi per WSUS con Service Pack 1
Title: File Leggimi per WSUS con Service Pack 1
ms:assetid: '937ecfe9-e8e0-41ac-85f7-4b65956f3d1e'
ms:contentKeyID: 18132415
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc708486(v=WS.10)'
---

File Leggimi per WSUS con Service Pack 1
========================================

Il presente documento descrive i problemi noti riscontrati in Windows Server Update Services con Service Pack 1 (WSUS con SP1). Dopo le informazioni su WSUS con SP1 sono riportate tutte le informazioni già contenute nel file Leggimi originale di WSUS. Queste informazioni includono raccomandazioni e requisiti per l'installazione di WSUS. WSUS con SP1 può essere scaricato dall'[Area download Microsoft](http://go.microsoft.com/fwlink/?linkid=67516).

Novità di WSUS con SP1
----------------------

WSUS con SP1 è una versione service pack che migliora la protezione, la scalabilità, la compatibilità e le prestazioni di WSUS. Offre le seguenti nuove funzionalità e miglioramenti:

-   Supporto per client Windows Vista: I computer che eseguono Windows Vista possono essere aggiornati dal server WSUS con SP1.
-   Supporto per più lingue dei client: Sono supportate tutte le lingue di Office e Windows Vista.
-   Nuova versione di WMSDE: L'istanza di WMSDE verrà aggiornata a WMSDE SP4 da WSUS con SP1 (WSUS RTM utilizza WMSDE SP3).
-   Miglioramenti delle prestazioni: WSUS con SP1 include vari miglioramenti delle prestazioni per accelerare i tempi di risposta dell'interfaccia utente.
-   Tutti gli aggiornamenti rapidi: WSUS con SP1 include tutte le modifiche e gli aggiornamenti rapidi pubblicati dopo WSUS RTM.
-   Supporto per SQL Server 2005.

Prima di iniziare l'aggiornamento a WSUS con SP1
------------------------------------------------

Le seguenti informazioni si applicano specificamente all'aggiornamento a WSUS con SP1. Si noti che i problemi e i requisiti descritti nella sezione “Prima di iniziare” della versione originale di questo argomento non sono ripetuti in questa sezione e rimangono validi. Ad esempio, i requisiti di installazione riportati nella sezione “Prima di iniziare” originale sono ancora validi.

**Nota**   Dopo avere applicato SP1 a WSUS 2.0, non è possibile disinstallare il service pack. La disinstallazione di SP1 rimuoverà l'intero prodotto.

**Importante**   Il presente documento contiene informazioni relative alla modifica del Registro di sistema. Assicurarsi di effettuare un backup del Registro di sistema prima di modificarlo. Assicurarsi di sapere come ripristinare il Registro di sistema se dovesse verificarsi un problema. Per ulteriori informazioni sul backup, il ripristino e la modifica del Registro di sistema, vedere il seguente articolo nella Microsoft Knowledge Base:

[Descrizione del Registro di sistema di Microsoft Windows](http://support.microsoft.com/kb/256986) (http://support.microsoft.com/kb/256986/)

#### Punto 1: Accertarsi di disporre di spazio su disco sufficiente per il backup del database

Quando si aggiorna da WSUS RTM, l'installazione di WSUS con SP1 crea automaticamente un backup del database di WSUS. È necessario accertarsi che vi sia spazio su disco sufficiente nel file system del server WSUS per memorizzare il backup del database di WSUS; in caso contrario l'installazione di WSUS con SP1 non riuscirà.

**Per stabilire se lo spazio è sufficiente**
1.  Aprire Esplora risorse e passare alla cartella in cui è memorizzato il database di WSUS. Per impostazione predefinita, WSUS installa il database nella seguente cartella:

    
        ```
2.  Tenere premuto **CTRL** e selezionare **SUSDB.MDF** e **SUSDB\_log.LDF**, quindi fare clic con il pulsante destro del mouse e selezionare **Proprietà**.

3.  Nella finestra di dialogo **File**, leggere il valore di **Dimensioni su disco**. Questa è la quantità minima di spazio libero necessaria per installare WSUS con SP1.

4.  Dal menu **Start**, scegliere **Risorse del computer**. Verificare che il disco in cui è installato WSUS disponga della quantità necessaria di spazio libero.

Se per qualsiasi motivo l'installazione di WSUS con SP1 non dovesse riuscire, ripristinare manualmente il database di backup. Per istruzioni sul ripristino del database di WSUS, vedere la [Guida operativa di WSUS](http://technet2.microsoft.com/windowsserver/en/library/05f2e884-ae62-4c90-9681-6c9f2f3c9fd91033.mspx).

#### Punto 2: WSUS con SP1 aggiorna solo WSUS RTM

WSUS con SP1 può essere utilizzato solo per aggiornare WSUS RTM. Attualmente l'aggiornamento dalla versione finale candidata di WSUS non è supportato. Se è installata la versione finale candidata o qualsiasi versione precedente di WSUS, è necessario disinstallarle e poi eseguire WSUS con SP1.

#### Punto 3: Il servizio IIS sul server verrà arrestato durante l'aggiornamento a WSUS con SP1

Il programma di installazione di WSUS con SP1 arresta il servizio IIS (Internet Information Services) sul server durante il processo di aggiornamento. Di conseguenza, i siti Web ospitati dall'installazione IIS sul server non saranno disponibili per tutta la durata dell'operazione di aggiornamento. IIS verrà avviato automaticamente al termine dell'aggiornamento.

#### Punto 4: Durante l'aggiornamento, non eseguire applicazioni che inviano chiamate alle API di WSUS

Le chiamate all'API (interfaccia applicazioni) di WSUS entrerebbero in conflitto con il programma di installazione di WSUS con SP1, causando errori nell'aggiornamento (un messaggio richiederà di riavviare il server per completare l'aggiornamento).

#### Punto 5: Per effettuare l'aggiornamento a WSUS con SP1 potrebbe essere necessario disattivare i programmi antivirus

Quando si aggiorna WSUS applicando WSUS con SP1, potrebbe essere necessario disattivare i programmi antivirus prima di poter effettuare correttamente l'aggiornamento o applicare il service pack. Dopo avere disattivato i programmi antivirus, riavviare il computer di Windows Server prima di applicare l'aggiornamento o il service pack. Questa procedura impedisce che vengano bloccati file a cui deve accedere il processo di aggiornamento. Al termine dell'installazione, assicurarsi di riattivare il programma antivirus. Per le procedure esatte per disattivare e riattivare la versione del programma antivirus in uso, vedere il sito Web del fornitore del programma antivirus.

| ![](images/Cc708486.Caution(WS.10).gif)Attenzione                                                                                                                                                                                                                                                                                                                  |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Questo accorgimento può rendere il computer o la rete più vulnerabile agli attacchi di utenti malintenzionati o di software dannoso, ad esempio virus. Non è consigliato applicare questo accorgimento; le informazioni a riguardo sono fornite allo scopo di consentire all'utente di applicarlo a propria discrezione. L'utente si assume ogni rischio legato all'uso di questo accorgimento. |

| ![](images/Cc708486.note(WS.10).gif)Nota                                                                                                                                                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| I programmi antivirus sono progettati per proteggere il computer dai virus. Non scaricare o aprire file da fonti non affidabili, visitare siti Web non affidabili o aprire allegati di posta elettronica quando il programma antivirus è disattivato. |

#### Punto 6: Se si utilizza un server proxy, l'aggiornamento SP1 potrebbe cancellare il nome utente e la password di configurazione della proxy

Se si utilizza un server proxy, in alcuni casi l'aggiornamento SP1 potrebbe cancellare il nome utente e la password della proxy. Questo potrebbe provocare errori di "parametro non valido" durante la sincronizzazione degli aggiornamenti da server Microsoft. Per risolvere questo problema, reimpostare il nome utente e la password di configurazione e ripetere la sincronizzazione del server.

#### Punto 7: Come ripristinare in caso di errore nell'aggiornamento per riportare il server WSUS in uno stato di coerenza e quindi ritentare l'aggiornamento.

Se l'aggiornamento a WSUS con SP1 non riesce, l'installazione di WSUS potrebbe rimanere in uno stato non coerente o inutilizzabile. Per ritentare l'aggiornamento a WSUS con SP1 è necessario riportare l'installazione di WSUS in uno stato di coerenza. A tale scopo si può utilizzare il database di backup creato all'inizio del processo di aggiornamento per ripristinare il server WSUS allo stato precedente all'aggiornamento.

Nell'eventualità di un aggiornamento non riuscito, seguire questa procedura per ritentare l'aggiornamento a WSUS con SP1:

**Per ritentare l'aggiornamento a WSUS con SP1**
1.  Localizzare il database di backup esaminando il contenuto del file WSUSSetup\_%timestamp%.log, che si trova nella seguente cartella:

    -   %programfiles%\\Update Services\\LogFiles

2.  Ripristinare il database di backup sul computer di WSUS utilizzando il seguente comando:

    -   osql.exe -S &lt;IstanzaDatabase&gt; -E -Q "USE master ALTER DATABASE SUSDB SET SINGLE\_USER WITH ROLLBACK IMMEDIATE RESTORE DATABASE SUSDB FROM DISK=N'&lt;PercorsoBackupDatabase&gt;' WITH REPLACE ALTER DATABASE SUSDB SET MULTI\_USER"
    -   Accertarsi di sostituire &lt;IstanzaDatabase&gt; e &lt;PercorsoBackupDatabase&gt; con i valori corrispondenti alla propria installazione.
    -   Per &lt;IstanzaDatabase&gt;, utilizzare il valore della seguente chiave del Registro di sistema:
    -   HKLM\\Software\\Microsoft\\Update Services\\Server\\Setup\\SqlServerName
    -   Per &lt;PercorsoBackupDatabase&gt;, utilizzare il valore identificato al punto 1.

3.  Disinstallare WSUS, ma conservare il database, i file di registro e i file di aggiornamento WSUS quando viene richiesto se si desidera rimuoverli. Verificare che nessuna delle opzioni in **Rimozione di Microsoft Windows Server Update Services** sia selezionata.

4.  Reinstallare WSUS RTM (la versione originale, non WSUS con SP1). Utilizzare il database esistente quando viene offerta l'opzione corrispondente. In questo modo, il sistema WSUS verrà riportato in uno stato di coerenza.

5.  Installare WSUS con SP1.

**Nota**    Non è possibile utilizzare il database di backup creato al punto 1 direttamente in un'installazione pulita di WSUS con SP1. Lo schema del database è stato modificato, quindi tale database non sarà compatibile se non si effettua l'aggiornamento a WSUS con SP1.

#### Punto 8: L'aggiornamento a WSUS con SP1 può non riuscire in alcuni casi in cui è stata effettuata la migrazione del database di WMSDE

La soluzione è variabile a seconda che la migrazione sia stata effettuata su un server SQL locale o remoto.

#### Migrazione del database WMSDE su un server SQL 2000 locale

È necessario modificare il valore di una chiave del Registro di sistema perché il pacchetto di installazione di WSUS con SP1 riconosca l'assenza del database WMSDE da aggiornare.

Se si è effettuata la migrazione di WMSDE su un server SQL 2000 locale, è necessario modificare il Registro di sistema come segue prima di tentare l'aggiornamento a WSUS con SP1:

-   Modificare il valore della seguente chiave del Registro di sistema da "1" a "0":
    -   HKLM\\Software\\Microsoft\\Update Services\\Server\\Setup\\WmsdeInstalled  

#### Migrazione del database WMSDE su un server SQL 2000 remoto

È necessario modificare il valore di due chiavi del Registro di sistema perché il pacchetto di installazione di WSUS con SP1 riconosca l'assenza del database WMSDE da aggiornare. L'aggiornamento deve essere avviato dal server back-end, seguito dal server front-end.  

Se si è effettuata la migrazione di WMSDE su un server SQL 2000 remoto, è necessario modificare il Registro di sistema come segue prima di tentare l'aggiornamento a WSUS con SP1:

1.  Modificare il valore della seguente chiave del Registro di sistema da "1" a "0":
    -   HKLM\\Software\\Microsoft\\Update Services\\Server\\Setup\\WmsdeInstalled 
2.  Modificare il valore della seguente chiave del Registro di sistema da "0x80" a "0x20":
    -   HKLM\\Software\\Microsoft\\Update Services\\Server\\Setup\\InstallType 

Dopo avere aggiornato questi valori, avviare l'aggiornamento sui server back-end e quindi avviarlo sui server front-end.

#### Punto 9: WSUS con SP1 non aggiorna i server WSUS installati tramite distribuzioni SQL remote

È necessario eseguire il pacchetto di installazione di WSUS con SP1 sia sui server front-end che sui server back-end.

**Per aggiornare a WSUS con SP1 quando si utilizza SQL remoto**
1.  Eseguire il pacchetto di installazione sul server front-end senza parametri e scegliere l'opzione di aggiornamento.

2.  Eseguire il pacchetto di installazione sul server back-end senza parametri e scegliere l'opzione di aggiornamento.

#### Punto 10: Se si modifica il nome del computer prima dell'aggiornamento a WSUS con SP1, l'aggiornamento potrebbe non riuscire

Se si modifica il nome del computer dopo avere installato WSUS RTM e prima di aggiornare a WSUS con SP1, l'aggiornamento a WSUS con SP1 potrebbe non riuscire.

Utilizzare il seguente script per rimuovere e aggiungere nuovamente i gruppi Administrator di ASPNET e WSUS, quindi eseguire nuovamente l'aggiornamento.

        ```
| ![](images/Cc708486.note(WS.10).gif)Nota                                                          |
|--------------------------------------------------------------------------------------------------------------------------------|
| Potrebbe essere necessario sostituire&lt;ContentDirectory&gt; nell'ultima riga con il percorso dell'archivio contenuti in uso. |

Segue il contenuto del file Leggimi originale di WSUS
-----------------------------------------------------

Il testo riportato di seguito è il contenuto del file Leggimi originale di WSUS. WSUS con SP1 *non* risolve i seguenti problemi. Il testo è stato incluso per comodità dell'utente.

Informazioni preliminari
------------------------

#### Punto 1: IIS deve essere installato

Microsoft® Windows Server™ Update Services (WSUS) richiede che sia installato IIS (Internet Information Services). Tuttavia, su Microsoft Windows Server 2003 e Microsoft Windows® 2000 Server, IIS non è installato per impostazione predefinita, quindi l'installazione di Windows Server Update Services potrebbe non essere in grado di continuare, con un messaggio di errore che informa che non è installato IIS.

Per installare IIS:

1.  Aprire il Pannello di controllo.
2.  Fare doppio clic su **Installazione applicazioni**.
3.  Fare clic su **Installazione componenti di Windows**.
4.  Nell'elenco **Componenti**, scegliere **Server applicazioni**.
5.  Scegliere **Dettagli**.
6.  Selezionare la casella di controllo **ASP.NET**. Selezionare **Abilita l'accesso COM+ alla rete**: Internet Information Services (IIS) verrà selezionato automaticamente.
7.  Selezionare **Internet Information Services (IIS)** e scegliere **Dettagli** per visualizzare l'elenco dei componenti facoltativi di IIS.
8.  Selezionare tutti i componenti facoltativi che si desidera installare. Il componente facoltativo Servizio World Wide Web include importanti componenti secondari, come ASP (Active Server Pages) e Amministrazione remota (HTML). Per visualizzare e selezionare questi componenti secondari, scegliere Servizio World Wide Web, quindi Dettagli. Scegliere OK fino a tornare all'Aggiunta guidata componenti di Windows.
9.  Scegliere **Avanti** e completare l'Aggiunta guidata componenti di Windows.
10. Dopo avere installato IIS, eseguire l'installazione di Windows Server Update Services.

#### Punto 2: Per i server che eseguono Windows 2000 Server, è necessario che sia presente almeno un sito Web in IIS prima di installare WSUS

Il programma di installazione di Windows Server Update Services potrebbe non riuscire a creare un sito Web se nessun sito è presente in IIS quando viene eseguita l'installazione. Questo potrebbe verificarsi, ad esempio, se l'unico sito in IIS era un sito di Software Update Services (SUS) 1.0 che è stato eliminato prima di installare WSUS.

In questo caso è necessario creare un nuovo sito Web utilizzando lo snap-in Gestione Internet Information Services (IIS). Una volta creato il sito è possibile selezionarlo o specificare un nuovo sito durante l'installazione di WSUS.

Se si è già tentato di installare WSUS e l'installazione non è riuscita perché non erano presenti siti, aprire lo snap-in Gestione IIS ed eliminare il sito "Sito Web \#1". Quindi, seguire le istruzioni descritte sopra ed eseguire nuovamente il programma di installazione.

#### Punto 3: Installazione dei componenti preliminari richiesti

#### Requisiti software

La tabella seguente elenca il software richiesto per ogni sistema operativo supportato. Assicurarsi che il server WSUS soddisfi i requisiti prima di eseguire il programma di installazione di WSUS. Se uno di questi aggiornamenti richiede il riavvio del computer al termine dell'installazione, effettuare il riavvio prima di installare WSUS.

###  

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema operativo</th>
<th>Requisiti</th>
<th>Download</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Tutti i sistemi operativi</p></td>
<td style="border:1px solid black;"><p>Microsoft Internet Information Services (IIS) 5.0</p></td>
<td style="border:1px solid black;"><p>Installare dal sistema operativo.</p>
<p>Vedere Punto 1: IIS deve essere installato.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Tutti i sistemi operativi</p></td>
<td style="border:1px solid black;"><p>Background Intelligent Transfer Service (BITS) 2.0</p></td>
<td style="border:1px solid black;"><p>Per i sistemi operativi Windows Server 2003, vedere Aggiornamento per Background Intelligent Transfer Service (BITS) 2.0 e WinHTTP 5.1 Windows Server 2003 (KB842773) nell'Area download all'indirizzo <a href="http://go.microsoft.com/fwlink/?linkid=47251">http://go.microsoft.com/fwlink/?LinkId=47251</a>.</p>
<p>Per i sistemi operativi Windows Server 2000, vedere Aggiornamento per Background Intelligent Transfer Service (BITS) 2.0 e WinHTTP 5.1 Windows 2000 (KB842773) nell'Area download all'indirizzo <a href="http://go.microsoft.com/fwlink/?linkid=46794">http://go.microsoft.com/fwlink/?LinkId=46794</a>.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
<td style="border:1px solid black;"><p>Microsoft .NET Framework 1.1 Service Pack 1 per Windows Server 2003</p></td>
<td style="border:1px solid black;"><p><a href="http://go.microsoft.com/fwlink/?linkid=47358">Microsoft .NET Framework 1.1 Service Pack 1 per Windows Server 2003</a></p>
<p>In alternativa, andare al sito <a href="http://go.microsoft.com/fwlink/?linkid=47370">Windows Update</a> ed effettuare la ricerca di aggiornamenti critici e service pack; installare Microsoft .NET Framework 1.1 Service Pack 1 per Windows Server 2003.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
<td style="border:1px solid black;"><p>Software di database compatibile al 100% con Microsoft SQL</p></td>
<td style="border:1px solid black;"><p>N/D</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Windows 2000 Server</p></td>
<td style="border:1px solid black;"><p>Software di database compatibile al 100% con Microsoft SQL</p></td>
<td style="border:1px solid black;"><p>Se non si utilizza Microsoft SQL Server 2000, è possibile installare Microsoft SQL Server 2000 Desktop Engine (MSDE 2000). Questa operazione richiede vari passaggi. Per ulteriori informazioni, vedere Installazione di MSDE su Windows 2000 più avanti in questo documento.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Windows 2000 Server</p></td>
<td style="border:1px solid black;"><p>Microsoft Internet Explorer 6.0 Service Pack 1</p></td>
<td style="border:1px solid black;"><p><a href="http://go.microsoft.com/fwlink/?linkid=47359">Internet Explorer 6 Service Pack 1</a></p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Windows 2000 Server</p></td>
<td style="border:1px solid black;"><p>Microsoft .NET Framework Version 1.1 Redistributable Package</p></td>
<td style="border:1px solid black;"><p><a href="http://go.microsoft.com/fwlink/?linkid=47369">Microsoft .NET Framework Version 1.1 Redistributable Package</a></p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Windows 2000 Server</p></td>
<td style="border:1px solid black;"><p>Microsoft .NET Framework 1.1 Service Pack 1</p></td>
<td style="border:1px solid black;"><p><a href="http://go.microsoft.com/fwlink/?linkid=47368">Microsoft .NET Framework 1.1 Service Pack 1</a></p>
<p>In alternativa, andare al sito <a href="http://go.microsoft.com/fwlink/?linkid=47370">Windows Update</a> ed effettuare la ricerca di aggiornamenti critici e service pack; installare Microsoft .NET Framework 1.1 Service Pack 1 per Windows Server 2003.</p></td>
</tr>
</tbody>
</table>
<p> </p>

Oltre a questi requisiti, se necessario WSUS potrebbe installare o configurare ASP.NET versione 1.1 sul server. Il programma di installazione di WSUS esegue la configurazione di ASP.NET.

#### Installazione di MSDE 2000 su Windows 2000

Se si utilizza Windows 2000 per WSUS e non si ha accesso a Microsoft SQL Server 2000, installare Microsoft SQL Server 2000 Desktop Engine (MSDE) prima di eseguire l'installazione di WSUS. Se MSDE è già installato sul server WSUS non è necessario configurare un'istanza speciale di MSDE per WSUS. È sufficiente indicare il nome dell'istanza esistente durante il processo di installazione di WSUS.

L'installazione di MSDE su Windows 2000 Server è un processo in quattro fasi. Per prima cosa è necessario scaricare ed espandere l'archivio di MSDE in una cartella sul server WSUS. In secondo luogo, utilizzare un prompt dei comandi e opzioni della riga di comando per eseguire il programma di installazione di MSDE, impostare la password dell'account sa e assegnare WSUS come nome dell'istanza. Quindi, al termine dell'installazione di MSDE, verificare che l'istanza di WSUS venga eseguita come servizio NT. Infine è necessario aggiungere una patch di sicurezza a MSDE per proteggere il server WSUS.

#### Fase 1: Scaricare ed espandere l'archivio di MSDE

È necessario scaricare ed espandere l'archivio di MSDE in una cartella sul server WSUS. Vedere [Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) versione A](http://go.microsoft.com/fwlink/?linkid=47366).

#### Fase 2: Installare MSDE

Utilizzare un prompt dei comandi e opzioni della riga di comando per eseguire il programma di installazione di MSDE, impostare la password e assegnare WSUS come nome dell'istanza. Al termine dell'installazione di MSDE, verificare che l'istanza di WSUS venga eseguita come servizio NT.

Per installare MSDE, impostare la password dell'account sa e assegnare un nome all'istanza:

1.  Al prompt dei comandi, passare alla cartella di installazione di MSDE specificata nella “Fase 1: Scaricare ed espandere l'archivio di MSDE".
2.  Digitare quanto segue: **setup sapwd="***password***" instancename=WSUS**
    dove *password* è una password complessa per l'account sa su questa istanza di MSDE e **instancename** è il nome dell'istanza del database. In alternativa è possibile utilizzare il nome dell'istanza predefinito al posto di "WSUS" per il database di WSUS. In questo caso non è necessario digitare **instancename=WSUS** tra i parametri della riga di comando. Questo comando avvia il programma di installazione di MSDE, imposta la password dell'account sa e assegna il nome specificato all'istanza di MSDE.

#### Fase 3: Verificare che l'istanza WSUS di MSDE sia installata

1.  Scegliere **Start**, quindi **Esegui**.
2.  Nella casella **Apri**, digitare **services.msc** e scegliere **OK**.

Scorrere nell'elenco di servizi e verificare che esista un servizio chiamato MSSQL$WSUS (se si è utilizzato "WSUS" come nome dell'istanza) o MSSQLSERVER (se si è utilizzato il nome predefinito dell'istanza).

#### Fase 4: Avviare l'istanza di MSDE.

Al termine dell'installazione di MSDE è necessario avviare l'istanza. Se si è utilizzato "WSUS" come nome dell'istanza, avviare "MSSQL$WSUS." Se si è utilizzato il nome predefinito dell'istanza, avviare MSSQLSERVER. Se non si avvia questo servizio, WSUS non sarà in grado di utilizzare l'istanza del database.

#### Fase 5: Aggiornare MSDE

È necessario scaricare e installare la patch di sicurezza descritta nel bollettino [MS03-031: Patch di sicurezza cumulativa per SQL Server](http://go.microsoft.com/fwlink/?linkid=47364).

Per scaricare la patch di sicurezza, vedere [Patch di sicurezza MS03-031 per SQL Server 2000 (32 bit)](http://go.microsoft.com/fwlink/?linkid=47363).

#### Punto 4: Requisiti minimi di spazio su disco

Di seguito sono riportati i requisiti minimi di spazio su disco per l'installazione di Windows Server Update Services:

-   1 gigabyte (GB) sulla partizione di sistema
-   2 GB per il volume in cui verranno memorizzati i file del database
-   6 GB, in base a proiezioni delle dimensioni del contenuto

#### Punto 5: Prima di installare la versione più recente, è necessario disinstallare le versioni precedenti di WSUS utilizzando Installazione applicazioni

Se si prevede di installare Windows Server Update Services su un server in cui è installato Windows Update Services Beta 1 o Beta 2, per prima cosa è necessario disinstallare la versione precedente utilizzando Installazione applicazioni dal Pannello di controllo.

#### Punto 6: WSUS richiede che sia attivata l'opzione trigger nidificati in SQL Server

Questa opzione è attivata per impostazione predefinita, ma può essere disattivata da un amministratore di SQL Server.

Se si prevede di utilizzare un database SQL Server come archivio dati di Windows Server Update Services, l'amministratore di SQL Server dovrà verificare che l'opzione trigger nidificati del server sia attivata prima che l'amministratore di WSUS proceda ad installare WSUS e specificare il database durante l'installazione.

WSUS Setup attiva l'opzione RECURSIVE\_TRIGGERS, che è specifica per il singolo database; non attiva tuttavia l'opzione trigger nidificati, che è un'opzione globale del server.

Per verificare se i trigger nidificati sono attivati, utilizzare il seguente comando:

**sp\_configure 'nested triggers'**

Per attivare l'opzione trigger nidificati in SQL Server, eseguire il seguente comando da un file batch sul computer che esegue SQL Server:

**sp\_configure 'nested triggers', 1**

**GO**

**RECONFIGURE**

**GO**

#### Punto 7: Opzioni della riga di comando per l'installazione di WSUS

È possibile eseguire installazioni automatiche di WSUS. Per ulteriori informazioni e per le opzioni della riga di comando, vedere "Appendice A: Installazione automatica" in [Distribuzione di Microsoft Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=41777).

Problemi noti
-------------

#### Punto 1: Configurazione guidata IIS Lockdown

Se si esegue IIS (Internet Information Services) su un computer che esegue Windows 2000 Server, installare la versione più recente della Configurazione guidata IIS Lockdown, che include URLScan, dalla pagina dello strumento IIS Lockdown nell'area Microsoft TechNet. Microsoft raccomanda di installare questo strumento per garantire la protezione dei server IIS. La Configurazione guidata IIS Lockdown disattiva le funzionalità non richieste di IIS, riducendo in tal modo i rischi di esposizione.

| ![](images/Cc708486.note(WS.10).gif)Nota                                                                                                                                                                                        |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Il programma di installazione di WSUS non installa questi componenti. È necessario installarli manualmente. Non è necessario installare IIS Lockdown sui computer che eseguono Windows Server 2003, poiché la funzionalità è incorporata in questo prodotto. |

#### Punto 2: La modifica della configurazione di WSUS direttamente nel database non è supportata

Windows Server Update Services memorizza i dati relativi alla propria configurazione in un database (MSDE o SQL Server). Tuttavia la modifica dei dati della configurazione mediante l'accesso diretto al database non è supportata. Gli amministratori non devono tentare di modificare la configurazione di WSUS in questo modo. Il metodo supportato per modificare la configurazione di WSUS è mediante la console di WSUS o mediante chiamate alle API di WSUS.

#### Punto 3: L'esecuzione di script attivi deve essere abilitata per accedere al sito amministrativo di WSUS

Sulla workstation dell'amministratore, è necessario configurare Internet Explorer in modo da consentire l'esecuzione di script attivi prima di poterlo utilizzare per accedere al sito amministrativo di WSUS.

#### Punto 4: IIS verrà riavviato durante l'installazione di WSUS

Il programma di installazione di Windows Server Update Services riavvia IIS senza notificare l'utente. Questo potrebbe influire sui siti Web esistenti nell'organizzazione.

#### Punto 5: Modifica dell'accesso alla directory virtuale dei punti di gestione (MP, Management Points) di WSUS o SMS

Per impostazione predefinita, la directory virtuale del contenuto di Windows Server Update Services è impostata in modo da consentire l'accesso anonimo. Se si modifica questa impostazione in modo da richiedere autenticazione, i client riceveranno errori di autenticazione e non potranno accedere allo scaricamento degli aggiornamenti. Questo è un problema noto dovuto al fatto che Winhttp.dll utilizza un contesto di autenticazione scorretto quando è richiesta l'autenticazione implicita, causando un errore nella risposta alla richiesta di autenticazione. Per evitare questo problema, accertarsi che i punti di gestione (MP) del server WSUS e di SMS siano impostati in modo da consentire l'accesso anonimo alle directory virtuali di IIS.

#### Punto 6: Quando si installa WSUS su Windows Small Business Server 2003, le impostazioni di accesso alle directory principali virtuali di WSUS del sito Web predefinito devono essere modificate in modo da consentire ai client WSUS di effettuare automaticamente l'aggiornamento dal server

Il server WSUS installa due directory principali virtuali, SelfUpdate e ClientWebService, e alcuni file nella directory principale del sito Web predefinito (sulla porta 80). Questo consente ai client di effettuare l'aggiornamento automatico tramite il sito Web predefinito. Per impostazione predefinita, in Windows Small Business Server 2003 il sito Web predefinito è configurato in modo da consentire l'accesso esclusivamente agli IP o localhost del server. Di conseguenza viene negato l'accesso alle directory principali virtuali SelfUpdate e ClientWebService e quindi i client non possono effettuare l'aggiornamento automatico. Per consentire l'accesso ai client per l'aggiornamento automatico, effettuare le seguenti operazioni sulle directory principali virtuali SelfUpdate e ClientWebService del sito Web predefinito.

1.  Fare clic sulle **Proprietà** della directory principale virtuale e poi su **Protezione directory**, **Limitazioni sugli indirizzi IP e sui nomi di dominio**, **Modifica**.
2.  Selezionare **Accesso consentito** e scegliere **OK**. Chiudere tutte le pagine delle proprietà.

#### Punto 7: Installazione di WSUS su Small Business Server: problemi relativi all'integrazione

-   Se Windows Small Business Server 2003 utilizza un server proxy ISA per accedere a Internet, è necessario immettere manualmente quanto segue nell'interfaccia utente **Impostazioni**: impostazioni del server proxy, nome del server proxy e porta.
-   Se ISA utilizza l'autenticazione Windows, è necessario immettere le credenziali del server proxy nel formato "DOMINIO\\utente" (l'utente appartiene al gruppo "Utenti Internet").

#### Punto 8: Quando si sposta un computer da un gruppo di computer a un altro, potrebbe passare anche un'ora prima che il computer appaia nel nuovo gruppo quando lo si visualizza dalla console amministrativa

Quando un computer viene assegnato per la prima volta a un gruppo di destinazione, i dati sul computer vengono modificati con le informazioni sul gruppo. I dati vengono aggiornati periodicamente o ogni ora. Di conseguenza, quando si sposta un computer da un gruppo di computer a un altro, potrebbe passare anche un'ora prima che le informazioni vengano aggiornate sul client e la modifica venga visualizzata nella console amministrativa di WSUS.

#### Punto 9: Se si installa WSUS su un server membro e in seguito si desidera promuovere il server membro a controller di dominio è necessario prima disinstallare WSUS

Se si installa WSUS su un server membro e in seguito si desidera promuovere il server membro a controller di dominio, sarà necessario effettuare le seguenti operazioni:

1.  Disinstallare WSUS.
2.  Promuovere il server a controller di dominio.
3.  Reinstallare WSUS.

#### Punto 10: Se si desidera abbassare di livello un server WSUS da controller di dominio a server membro è necessario prima disinstallare WSUS

Se si esegue WSUS Server su un controller di dominio e si desidera abbassarlo di livello da controller di dominio a server membro, sarà necessario effettuare le seguenti operazioni:

1.  Disinstallare WSUS conservando il database.
2.  Creare un account utente chiamato ASPNET.
3.  Al prompt dei comandi, digitare **aspnet\_regiis -i**.
4.  Reinstallare WSUS e utilizzare il database conservato.

#### Punto 11: Se .NET Framework 1.0 o 2.0 viene installato dopo l'installazione di WSUS, la console amministrativa di WSUS non compare

Questo è dovuto al fatto che .NET Framework 1.0 è registrato in IIS e WSUS Server richiede .NET Framework 1.1. Per risolvere questo problema, aprire aspnet\_regiis.exe ed eseguire i seguenti comandi, dove *id sito web* è il valore contenuto nella seguente chiave del Registro di sistema:

HKLM\\Software\\Microsoft\\WindowsUpdateServices\\Server\\Setup\\IISTargetWebsiteIndex

-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*id sito web*&gt;\\ROOT\\ReportingWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*id sito web*&gt;\\ROOT\\ClientWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*id sito web*&gt;\\ROOT\\SimpleAuthWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*id sito web*&gt;\\ROOT\\WSUSAdmin
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*id sito web*&gt;\\ROOT\\AdministrationWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*id sito web*&gt;\\ROOT\\ServrSyncWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*id sito web*&gt;\\ROOT\\DssAuthWebService
-   %windir%\\Microsoft.NET\\Framework\\v1.1.4322\\\\aspnet\_regiis.exe -s W3SVC\\&lt;*id sito web*&gt;\\ROOT\\Content

#### Punto 12: Limitazioni di SQL remoto

WSUS offre supporto limitato per l'esecuzione di software di database su un computer separato da quello che contiene il resto dell'applicazione WSUS.

-   Non è possibile utilizzare Windows 2000 Server come computer front-end in una coppia di SQL remoto.
-   Non è possibile utilizzare un server configurato come controller di dominio come front-end o come back-end della coppia di SQL remoto.
-   Non è possibile utilizzare WMSDE o MSDE come software di database sul computer back-end.
-   L'installazione di SQL Server remoto (da utilizzare come database di WSUS) non riesce se Servizi terminal è installato sul server remoto ed eseguito in modalità applicazione. Quando si installa SQL Server su un server di Servizi terminal, è necessario effettuare le seguenti operazioni:
    1.  Prima di eseguire il programma di installazione, aprire un prompt dei comandi e digitare: "change user /install"
    2.  Eseguire il programma di installazione di SQL Server.
    3.  Dopo avere eseguito l'installazione, al prompt dei comandi digitare: "change user /execute"
-   Per installare il database WSUS di SQL Server remoto è necessario appartenere al gruppo di protezione Administrators locale sia sul computer front-end che sul computer back-end.
-   Per ulteriori informazioni sui problemi relativi a SQL remoto, vedere "Appendice C: SQL remoto" in [Distribuzione di Microsoft Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=41777).

#### Punto 13: Un server di replica figlio può avere meno approvazioni del server padre

Un server di replica figlio può avere meno approvazioni del server padre. Questo è dovuto al fatto che le approvazioni di installazione non passano al server figlio finché non è stato scaricato tutto il contenuto nel server padre.

#### Punto 14: Ritentare la sincronizzazione in caso di errore iniziale

Se la sincronizzazione non riesce, la prima operazione da eseguire per cercare di risolvere il problema è tentare nuovamente di sincronizzare il server. Se la sincronizzazione successiva non riesce, utilizzare le informazioni per la risoluzione dei problemi nella Guida operativa di WSUS.

#### Punto 15: Quando si tenta di accedere alla console amministrativa di WSUS compare il messaggio di errore System.IO.FileNotFoundException

Se compare il seguente messaggio di errore, potrebbe essere necessario correggere le autorizzazioni sugli account del servizio di rete o ASP.NET:

System.IO.FileNotFoundException: Impossibile trovare il file o l'assembly di nome *xxxxxx*.dll oppure una delle sue dipendenze

Dove *xxxx* è un nome casuale.

Per risolvere questo problema nei sistemi operativi Windows Server 20003, assegnare all'account del servizio di rete accesso di lettura/scrittura a %systemroot%\\Temp. In Windows 2000 Server, assegnare all'account ASP.NET accesso di lettura/scrittura a %systemroot%\\Temp.

#### Punto 16: Aggiornamento per la protezione di SQL MS03-031 (KB815495)

Questo aggiornamento può apparire installato sul server WSUS anche se l'installazione non è riuscita sul client. Questo può far sì che il pacchetto venga nuovamente offerto al client. Per ovviare a questo problema, rimuovere l'approvazione dall'aggiornamento sul server.

#### Punto 17: Le impostazioni di IIS vanno perdute durante l'aggiornamento a RTM.

Se si installa WSUS RTM su un server che dispone di una versione precedente di WSUS, come ad esempio la versione RC, WSUS RTM disinstalla la versione precedente e poi installa la nuova versione. In questo processo le directory principali virtuali e i file associati a WSUS in IIS vengono eliminati.

Se si è installato WSUS sul sito Web predefinito, si perderanno tutte le impostazioni relative a WSUS effettuate nelle directory principali virtuali. Ad esempio, se si sono configurate le directory principali virtuali di WSUS per SSL allo scopo di proteggere WSUS, sarà necessario riconfigurarle dopo avere installato la versione RTM di WSUS. Nota: una notifica sulla console WSUS informerà che SSL non è abilitato.

Se si era installato WSUS su un sito Web diverso da quello predefinito, tutte le impostazioni aggiuntive a livello del sito Web di WSUS andranno perdute.

#### Punto 18: Utilizzo delle intestazioni host

Se si desiderano assegnare valori delle intestazioni host al sito Web predefinito (sito Web WSUS) in IIS, è necessario aggiungere “Tutti non assegnati” o un indirizzo IP assegnato all'elenco degli indirizzi IP senza impostare il valore dell'intestazione host sul sito Web predefinito. Questo dovrebbe essere aggiunto anche al sito Web non predefinito

**Attenzione**: Questo potrebbe danneggiare funzionalità di Microsoft SharePoint ed Exchange.

#### Punto 19: L'URL della console WSUS deve essere aggiunta all'elenco Siti attendibili e Intranet locale delle aree di contenuto Web sui computer in cui è abilitata la protezione avanzata di Internet Explorer

Se la protezione avanzata di Internet Explorer (noto anche come componente Protezione avanzata di Internet Explorer di Microsoft Windows Server 2003) è abilitata su un computer e non si aggiunge la console WSUS alle aree di contenuto Web Siti affidabili e Intranet locale, verranno richieste le credenziali ogni volta che si apre una pagina nella console WSUS.

Per aggiungere la console WSUS alle aree di contenuto Web **Intranet locale** e **Siti affidabili**:

1.  Aprire **Opzioni Internet**: ad esempio, scegliere **Start**, **Pannello di controllo**, quindi **Opzioni Internet**.
2.  Nella scheda **Protezione**, scegliere **Intranet locale**, **Siti**, **Avanzate**, aggiungere l'URL (http://*nomeserverWSUS*/WSUSAdmin) e scegliere **OK**.
3.  Scegliere **Siti affidabili**, quindi **Siti**, aggiungere l'URL della console WSUS, scegliere **OK** e poi scegliere nuovamente **OK** per uscire da **Opzioni Internet**.

#### Copyright

Le informazioni contenute in questo documento rappresentano il punto di vista di Microsoft Corporation sui problemi trattati alla data della pubblicazione. Tuttavia, poiché Microsoft deve reagire alle mutevoli condizioni del mercato, questo non deve essere interpretato come un impegno da parte di Microsoft e, dopo la data della pubblicazione, Microsoft non è in grado di garantire l'accuratezza di alcuna delle informazioni presentate.

Questo documento viene fornito con soli intenti informativi. MICROSOFT NON FORNISCE ALCUNA GARANZIA, ESPLICITA, IMPLICITA O DI LEGGE, RIGUARDO ALLE INFORMAZIONI CONTENUTE IN QUESTO DOCUMENTO.

Il rispetto di tutte le leggi applicabili in materia di copyright è esclusivamente a carico dell'utente. Fermi restando tutti i diritti coperti da copyright, nessuna parte di questo documento potrà comunque essere riprodotta o inserita in un sistema di riproduzione o trasmessa in qualsiasi forma e con qualsiasi mezzo (in formato elettronico, meccanico, su fotocopia, come registrazione o altro) per qualsiasi scopo, senza il permesso scritto di Microsoft Corporation.

Microsoft può essere titolare di brevetti, domande di brevetto, marchi, copyright o altri diritti di proprietà intellettuale relativi all'oggetto del presente documento. Salvo quanto espressamente previsto in un contratto scritto di licenza Microsoft, la consegna del presente documento non implica la concessione di alcuna licenza su tali brevetti, marchi, copyright o altra proprietà intellettuale.

Se non specificato diversamente, ogni riferimento a società, nomi, dati e indirizzi utilizzati nel presente documento è puramente casuale e ha il solo scopo di illustrare l'uso del prodotto Microsoft.

© 2006 Microsoft Corporation. Tutti i diritti riservati.

Microsoft, SQL Server, Windows e Windows Server sono marchi registrati o marchi commerciali di Microsoft Corporation negli Stati Uniti e/o in altri paesi.

I nomi di prodotti e società reali citati nel presente documento possono essere marchi dei rispettivi proprietari.
