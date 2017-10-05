---
TOCTitle: File Leggimi per Windows Server Update Services
Title: File Leggimi per Windows Server Update Services
ms:assetid: '4244109a-395a-4ff8-9989-ea55ab0964a3'
ms:contentKeyID: 18132356
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720505(v=WS.10)'
---

File Leggimi per Windows Server Update Services
===============================================

In questo documento si descrivono i problemi noti riscontrati in Windows Server Update Services (WSUS). Sono inoltre incluse raccomandazioni e requisiti per l'installazione di WSUS.

| ![](images/Cc720505.note(WS.10).gif)Nota                                                                                                                            |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Per il download di una copia di questo documento, visitare l'Area download Microsoft all'indirizzo [http://go.microsoft.com/fwlink/?LinkId=48126](http://go.microsoft.com/fwlink/?linkid=48126). |

Informazioni preliminari
------------------------

#### Punto 1: IIS deve essere installato

Microsoft® Windows Server™ Update Services (WSUS) richiede che sia installato IIS (Internet Information Services). Tuttavia, su Microsoft Windows Server 2003 e Microsoft Windows® 2000 Server, IIS non viene installato per impostazione predefinita, quindi l'installazione di Windows Server Update Services potrebbe non procedere, con un messaggio di errore che informa che IIS non è installato.

Per installare IIS:

1.  Aprire il Pannello di controllo.
2.  Fare doppio clic su **Installazione applicazioni**.
3.  Fare clic su **Installazione componenti di Windows**.
4.  Nell'elenco **Componenti** scegliere **Server applicazioni**.
5.  Scegliere **Dettagli**.
6.  Selezionare la casella di controllo **ASP.NET**. Selezionare **Abilita l'accesso COM+ alla rete**: Internet Information Services (IIS) verrà selezionato automaticamente.
7.  Selezionare **Internet Information Services (IIS)** e scegliere **Dettagli** per visualizzare l'elenco dei componenti facoltativi di IIS.
8.  Selezionare tutti i componenti facoltativi da installare. Il componente facoltativo Servizio World Wide Web include importanti componenti secondari, come ASP (Active Server Pages) e Amministrazione remota (HTML). Per visualizzare e selezionare questi componenti secondari, scegliere Servizio World Wide Web, quindi Dettagli. Scegliere OK fino a tornare all'Aggiunta guidata componenti di Windows.
9.  Scegliere **Avanti** e completare l'Aggiunta guidata componenti di Windows.
10. Dopo avere installato IIS, eseguire l'installazione di Windows Server Update Services.

#### Punto 2: Per i server che eseguono Windows 2000 Server, è necessario che sia presente almeno un sito Web in IIS prima di installare WSUS

Se quando viene eseguita l'installazione non è presente in IIS alcun sito, il programma di installazione di Windows Server Update Services potrebbe non riuscire a creare un sito Web. Questo si verifica, ad esempio, se l'unico sito in IIS è un sito di Software Update Services (SUS) 1.0 eliminato prima di installare WSUS.

In questo caso è necessario creare un nuovo sito Web utilizzando lo snap-in Gestione Internet Information Services (IIS). Una volta creato il sito è possibile selezionarlo o specificare un nuovo sito durante l'installazione di WSUS.

Se si è già tentato di installare WSUS e l'installazione non è riuscita perché non erano presenti siti, aprire lo snap-in Gestione IIS ed eliminare il sito "Sito Web \#1". Quindi, seguire le istruzioni descritte sopra ed eseguire nuovamente il programma di installazione.

#### Punto 3: Installazione dei componenti preliminari richiesti

#### Requisiti software

Nella tabella che segue è riportato il software necessario per ciascun sistema operativo supportato. Accertarsi che il server WSUS soddisfi i requisiti prima di eseguire il programma di installazione di WSUS. Se uno di questi aggiornamenti richiede il riavvio del computer al termine dell'installazione, riavviare prima di installare WSUS.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Sistema operativo</th>
<th style="border:1px solid black;" >Requisiti</th>
<th style="border:1px solid black;" >Download</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Tutti i sistemi operativi</td>
<td style="border:1px solid black;">Microsoft Internet Information Services (IIS) 5.0</td>
<td style="border:1px solid black;">Installare dal sistema operativo.
Vedere Punto 1: IIS deve essere installato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Tutti i sistemi operativi</td>
<td style="border:1px solid black;">Background Intelligent Transfer Service (BITS) 2.0</td>
<td style="border:1px solid black;">Per i sistemi operativi Windows Server 2003, vedere <a href="http://go.microsoft.com/fwlink/?linkid=47251">Aggiornamento per il servizio trasferimento intelligente in background (BITS) 2.0 e WinHTTP 5.1 Windows Server 2003 (KB842773)</a> nell'Area download Microsoft (http://go.microsoft.com/fwlink/?LinkId=47251).
Per i sistemi operativi Windows Server 2000, vedere <a href="http://go.microsoft.com/fwlink/?linkid=46794">Aggiornamento per il servizio trasferimento intelligente in background (BITS) 2.0 e WinHTTP 5.1 Windows 2000 (KB842773)</a> nell'Area download Microsoft (http://go.microsoft.com/fwlink/?LinkId=46794).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2003</td>
<td style="border:1px solid black;">Microsoft .NET Framework 1.1 Service Pack 1 per Windows Server 2003</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=47358">Microsoft .NET Framework 1.1 Service Pack 1 per Windows Server 2003</a>
In alternativa, visitare il sito di <a href="http://go.microsoft.com/fwlink/?linkid=47370">Windows Update</a> ed effettuare la ricerca di aggiornamenti critici e Service Pack; installare Microsoft .NET Framework 1.1 Service Pack 1 per Windows Server 2003.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows Server 2003</td>
<td style="border:1px solid black;">Software di database compatibile al 100% con Microsoft SQL</td>
<td style="border:1px solid black;">N/D</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Software di database compatibile al 100% con Microsoft SQL</td>
<td style="border:1px solid black;">Se non si utilizza Microsoft SQL Server 2000, è possibile installare Microsoft SQL Server 2000 Desktop Engine (MSDE 2000). Questa operazione richiede alcune operazioni. Per ulteriori informazioni, vedere Installazione di MSDE su Windows 2000 più avanti in questo documento.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Microsoft Internet Explorer 6.0 Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=47359">Internet Explorer 6 Service Pack 1</a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Microsoft .NET Framework Version 1.1 Redistributable Package</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=47369">Microsoft .NET Framework Version 1.1 Redistributable Package</a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows 2000 Server</td>
<td style="border:1px solid black;">Microsoft .NET Framework 1.1 Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=47368">Microsoft .NET Framework 1.1 Service Pack 1</a>
In alternativa, visitare il sito di <a href="http://go.microsoft.com/fwlink/?linkid=47370">Windows Update</a> ed effettuare la ricerca di aggiornamenti critici e service pack; installare Microsoft .NET Framework 1.1 Service Pack 1 per Windows Server 2000.</td>
</tr>
</tbody>
</table>
 

Oltre a questi requisiti, se necessario WSUS potrebbe installare o configurare ASP.NET versione 1.1 sul server. Il programma di installazione di WSUS esegue la configurazione di ASP.NET.

#### Installazione di MSDE 2000 su Windows 2000

Se si utilizza Windows 2000 per WSUS e non si ha accesso a Microsoft SQL Server 2000, installare Microsoft SQL Server 2000 Desktop Engine (MSDE) prima di eseguire l'installazione di WSUS. Se MSDE è già installato sul server WSUS, non sarà necessario configurare un'istanza speciale di MSDE per WSUS. Sarà invece sufficiente indicare il nome dell'istanza esistente durante il processo di installazione di WSUS.

L'installazione di MSDE su Windows 2000 Server è un processo in quattro fasi. È prima di tutto necessario scaricare ed espandere l'archivio di MSDE in una cartella sul server WSUS. In secondo luogo, utilizzare un prompt dei comandi e le opzioni della riga di comando per eseguire il programma di installazione di MSDE, impostare la password dell'account sa e assegnare WSUS come nome dell'istanza. Quindi, al termine dell'installazione di MSDE, verificare che l'istanza di WSUS venga eseguita come servizio NT. Infine, aggiungere un aggiornamento della protezione a MSDE per proteggere il server di WSUS.

#### Fase 1: Scaricare ed espandere l'archivio di MSDE

È necessario scaricare ed espandere l'archivio di MSDE in una cartella sul server WSUS. Vedere [Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) versione A](http://go.microsoft.com/fwlink/?linkid=47366).

#### Fase 2: Installare MSDE

Utilizzare un prompt dei comandi e le opzioni della riga di comando per eseguire il programma di installazione di MSDE, impostare la password dell'account sa e assegnare WSUS come nome dell'istanza. Al termine dell'installazione di MSDE, verificare che l'istanza di WSUS venga eseguita come servizio NT.

Per installare MSDE, impostare la password dell'account sa e assegnare un nome all'istanza:

1.  Al prompt dei comandi, passare alla cartella di installazione di MSDE specificata nella "Fase 1: Scaricare ed espandere l'archivio di MSDE".
2.  Digitare quanto segue: **setup sapwd="***password***" nomeistanza=WSUS**
    dove *password* è una password complessa per l'account sa su questa istanza di MSDE e **nomeistanza** è il nome dell'istanza del database. In alternativa è possibile utilizzare il nome dell'istanza predefinito al posto di "WSUS" per il database di WSUS. In questo caso non è necessario digitare **nomeistanza=WSUS** tra i parametri della riga di comando. Il comando avvia il programma di installazione di MSDE, imposta la password dell'account sa e assegna il nome specificato all'istanza di MSDE.

#### Fase 3: Verificare che l'istanza WSUS di MSDE sia installata

Accertarsi che sia possibile visualizzare l'istanza WSUS di MSDE.

1.  Scegliere **Start**, quindi **Esegui**.
2.  Nella casella **Apri**, digitare **services.msc** e scegliere **OK**.

Scorrere nell'elenco di servizi e verificare che esista un servizio chiamato MSSQL$WSUS (se si è utilizzato "WSUS" come nome dell'istanza) o MSSQLSERVER (se si è utilizzato il nome predefinito dell'istanza).

#### Fase 4: Avviare l'istanza di MSDE.

Al termine dell'installazione di MSDE è necessario avviare l'istanza. Se si è utilizzato "WSUS" come nome dell'istanza, avviare "MSSQL$WSUS". Se si è utilizzato il nome predefinito dell'istanza, avviare MSSQLSERVER. Se non si avvia questo servizio, WSUS non sarà in grado di utilizzare l'istanza del database.

#### Fase 5: Aggiornare MSDE

È necessario scaricare e installare l'aggiornamento della protezione descritto nel bollettino [MS03-031: Patch di sicurezza cumulativa per SQL Server](http://go.microsoft.com/fwlink/?linkid=47364).

Per scaricare l'aggiornamento della protezione, vedere [Patch di protezione MS03-031 per SQL Server 2000 (32 bit)](http://go.microsoft.com/fwlink/?linkid=47363).

#### Punto 4: Requisiti minimi di spazio su disco

Di seguito sono riportati i requisiti minimi di spazio su disco per l'installazione di Windows Server Update Services:

-   1 gigabyte (GB) sulla partizione di sistema
-   2 GB per il volume in cui verranno memorizzati i file del database
-   6 GB, in base a proiezioni delle dimensioni del contenuto

#### Punto 5: Prima di installare la versione più recente, è necessario disinstallare le versioni precedenti di WSUS utilizzando Installazione applicazioni

Se si prevede di installare Windows Server Update Services su un server in cui è installato Windows Update Services Beta 1 o Beta 2, è necessario prima di tutto disinstallare la versione precedente utilizzando Installazione applicazioni dal Pannello di controllo.

#### Punto 6: WSUS richiede che sia attivata l'opzione trigger nidificati in SQL Server

Questa opzione è attivata per impostazione predefinita, ma può essere disattivata da un amministratore di SQL Server.

Se si prevede di utilizzare un database SQL Server come archivio dati di Windows Server Update Services, l'amministratore di SQL Server dovrà verificare che l'opzione trigger nidificati del server sia attivata prima che l'amministratore di WSUS proceda con l'installazione di WSUS e la specifica del database durante l'installazione.

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

| ![](images/Cc720505.note(WS.10).gif)Nota                                                                                                                                                                                  |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Il programma di installazione di WSUS non installa questi componenti. È necessario installarli manualmente. Non è necessario installare IIS Lockdown sui computer che eseguono Windows Server 2003, poiché la funzionalità è incorporata nel prodotto. |

#### Punto 2: La modifica della configurazione di WSUS direttamente nel database non è supportata

Windows Server Update Services memorizza i dati relativi alla propria configurazione in un database (MSDE o SQL Server). Tuttavia la modifica dei dati della configurazione mediante l'accesso diretto al database non è supportata. Gli amministratori non devono tentare di modificare la configurazione di WSUS in questo modo. Il metodo supportato per modificare la configurazione di WSUS è mediante la console di WSUS o le chiamate alle API di WSUS.

#### Punto 3: Per accedere al sito amministrativo di WSUS, l'esecuzione di script attivi deve essere abilitata

Sulla workstation dell'amministratore, è necessario configurare Internet Explorer in modo da consentire l'esecuzione di script attivi prima di poterlo utilizzare per accedere al sito amministrativo di WSUS.

#### Punto 4: IIS verrà riavviato durante l'installazione di WSUS

Il programma di installazione di Windows Server Update Services riavvia IIS senza notifiche all'utente. Questo potrebbe influire sui siti Web esistenti nell'organizzazione.

#### Punto 5: Modifica dell'accesso alla directory virtuale dei punti di gestione (MP, Management Points) di WSUS o SMS

Per impostazione predefinita, la directory virtuale del contenuto di Windows Server Update Services è impostata in modo da consentire l'accesso anonimo. Se si modifica questa impostazione in modo da richiedere l'autenticazione, i client riceveranno errori di autenticazione e non potranno accedere allo scaricamento degli aggiornamenti. Questo è un problema noto dovuto al fatto che Winhttp.dll utilizza un contesto di autenticazione scorretto quando è richiesta l'autenticazione implicita, causando un errore nella risposta alla richiesta di autenticazione. Per prevenire il problema, accertarsi che i punti di gestione (MP) del server WSUS e di SMS siano impostati in modo da consentire l'accesso anonimo alle directory virtuali di IIS.

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

Questo è dovuto al fatto che .NET Framework 1.0 è registrato in IIS e WSUS Server richiede .NET Framework 1.1. Per risolvere questo problema, avviare aspnet\_regiis.exe ed eseguire i seguenti comandi, dove *id sito web* è il valore contenuto nella seguente chiave del Registro di sistema:

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
    1.  Prima di eseguire il programma di installazione, aprire un prompt dei comandi e digitare: **change user /install**
    2.  Eseguire il programma di installazione di SQL Server.
    3.  Dopo avere eseguito l'installazione, al prompt dei comandi digitare: **change user /execute**
-   Per installare il database WSUS di SQL Server remoto è necessario appartenere al gruppo di protezione Administrators locale sia sul computer front-end che sul computer back-end.
-   Per ulteriori informazioni sui problemi relativi a SQL remoto, vedere "Appendice C: SQL remoto" in [Distribuzione di Microsoft Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=41777).

#### Punto 13: Un server di replica figlio può avere meno approvazioni del server padre

Un server di replica figlio può avere meno approvazioni del server padre. Questo è dovuto al fatto che le approvazioni di installazione non passano al server figlio finché non è stato scaricato tutto il contenuto nel server padre.

#### Punto 14: Ritentare la sincronizzazione in caso di errore

Se la sincronizzazione non riesce, è possibile che venga visualizzato un messaggio di errore. In tal caso, la prima operazione da eseguire è tentare nuovamente la sincronizzazione.

#### Punto 15: Quando si tenta di accedere alla console amministrativa di WSUS viene visualizzato il messaggio di errore System.IO.FileNotFoundException

Se viene visualizzato il seguente messaggio di errore, potrebbe essere necessario correggere le autorizzazioni sugli account del servizio di rete o ASP.NET:

System.IO.FileNotFoundException: Impossibile trovare il file o l'assembly di nome *xxxxxx*.dll oppure una delle sue dipendenze

Dove *xxxx* è un nome casuale.

Per risolvere questo problema nei sistemi operativi Windows Server 20003, assegnare all'account del servizio di rete accesso di lettura/scrittura a %systemroot%\\Temp. In Windows 2000 Server, assegnare all'account ASP.NET accesso di lettura/scrittura a %systemroot%\\Temp.

#### Punto 16: Aggiornamento per la protezione di SQL MS03-031 (KB815495)

Questo aggiornamento può sembrare installato sul server WSUS anche se l'installazione non è riuscita sul client. Ne può conseguire che il pacchetto venga nuovamente offerto al client. Per ovviare al problema, rimuovere l'approvazione dall'aggiornamento sul server.

#### Punto 17: Le impostazioni di IIS vanno perdute durante l'aggiornamento a RTM.

Se si installa WSUS RTM su un server con una versione precedente di WSUS, ad esempio la versione RC, WSUS RTM disinstalla la versione precedente e poi installa la nuova versione. In questo processo le directory principali virtuali e i file associati a WSUS in IIS vengono eliminati.

Se si è installato WSUS sul sito Web predefinito, si perderanno tutte le impostazioni relative a WSUS effettuate nelle directory principali virtuali. Ad esempio, se si sono configurate le directory principali virtuali di WSUS per SSL allo scopo di proteggere WSUS, sarà necessario riconfigurarle dopo avere installato la versione RTM di WSUS. Nota: una notifica sulla console WSUS informerà che SSL non è abilitato.

Se si era installato WSUS su un sito Web diverso da quello predefinito, tutte le impostazioni aggiuntive a livello del sito Web di WSUS andranno perdute.

#### Punto 18: Utilizzo delle intestazioni host

Se si desidera assegnare valori delle intestazioni host al sito Web predefinito (sito Web WSUS) in IIS, è necessario aggiungere "Tutti non assegnati" o un indirizzo IP assegnato all'elenco degli indirizzi IP senza impostare il valore dell'intestazione host sul sito Web predefinito. Questo dovrebbe essere aggiunto anche al sito Web non predefinito

**Attenzione**: questo potrebbe danneggiare le funzionalità di Windows® SharePoint® Services ed Exchange.

#### Punto 19: L'URL della console WSUS deve essere aggiunto all'elenco Siti attendibili e Intranet locale delle aree di contenuto Web sui computer in cui è abilitata la protezione avanzata di Internet Explorer

Se la protezione avanzata di Internet Explorer (noto anche come componente Protezione avanzata di Internet Explorer di Microsoft Windows Server 2003) è abilitata su un computer e non si aggiunge la console WSUS alle aree di contenuto Web Siti affidabili e Intranet locale, verranno richieste le credenziali ogni volta che si apre una pagina nella console WSUS.

Per aggiungere la console WSUS alle aree di contenuto Web **Intranet locale** e **Siti affidabili**:

1.  Aprire **Opzioni Internet**: ad esempio, scegliere **Start**, **Pannello di controllo**, quindi **Opzioni Internet**.
2.  Nella scheda **Protezione**, scegliere **Intranet locale**, **Siti**, **Avanzate**, aggiungere l'URL http://*nomeserverWSUS*/WSUSAdmin e scegliere **OK**.
3.  Scegliere **Siti affidabili**, quindi **Siti**, aggiungere l'URL della console WSUS, scegliere **OK** e poi scegliere nuovamente **OK** per uscire da **Opzioni Internet**.

#### Punto 20: Errore durante l'aggiornamento dalla versione finale candidata di WSUS

È possibile che l'aggiornamento dalla versione finale candidata di WSUS non riesca a causa di un problema nella struttura di aggiornamento automatico. Questo problema può verificarsi se più client eseguono l'aggiornamento automatico nello stesso momento in cui si tenta di effettuare l'aggiornamento.

Per risolvere il problema:

1.  Disconnettere il server di WSUS dalla rete, assicurando che i client non siano in grado di connettervi.
2.  Al prompt dei comandi digitare: **iisrestart /reset**, quindi premere INVIO.
3.  Eseguire l'aggiornamento.

#### Punto 21: Non è possibile eseguire la migrazione di alcune approvazioni da SUS 1.0 a WSUS

Quando si esegue la migrazione da SUS 1.0 a WSUS, la migrazione di alcune approvazioni dal server SUS 1.0 al server WSUS non riesce. Questo problema si verifica perché alcuni aggiornamenti disponibili per SUS 1.0 non sono più disponibili per WSUS. Inoltre, poiché WSUS supporta un maggior numero di aggiornamenti rispetto a SUS, è possibile che sul server WSUS siano presenti aggiornamenti importanti che non vengono approvati al termine del processo di migrazione.

Microsoft consiglia di controllare l'insieme di aggiornamenti non approvati sul server WSUS dopo la migrazione da SUS 1.0.

Per ulteriori informazioni sulla migrazione da SUS 1.0 a WSUS, vedere la sezione relativa alla [guida dettagliata alla migrazione da Software Update Services a Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=48042) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=48042.

#### Punto 22: se si è effettuata la migrazione da WMSDE a SQL Server, correggere questa voce del Registro di sistema prima di eseguire l'aggiornamento da WSUS 2.0 Service Pack 1

Se si intende eseguire l'aggiornamento da WSUS 2.0 a Service Pack 1 e si è effettuata la migrazione dell'installazione di WMSDE a SQL Server (in modalità remota o locale), accertarsi di modificare la seguente voce del Registro di sistema:

HKLM\\Software\\Microsoft\\Update Services\\Server\\Setup\\WmsdeInstalled

Il valore deve essere modificato da 1 in 0.

#### Punto 23: Migrazione di un'installazione SQL remota a WSUS 2.0 Service Pack 1

Quando si esegue la migrazione a WSUS 2.0 Service Pack 1 con una configurazione SQL remota, attenersi alla seguente procedura:

1) Eseguire il pacchetto di installazione sul front-end senza specificare opzioni e scegliere di eseguire l'aggiornamento

2) Eseguire il pacchetto di installazione sul back-end senza specificare opzioni e scegliere di eseguire l'aggiornamento.

#### Copyright

Le informazioni contenute in questo documento rappresentano il punto di vista di Microsoft Corporation sui problemi trattati alla data della pubblicazione. Tuttavia, poiché Microsoft deve reagire alle mutevoli condizioni del mercato, questo non deve essere interpretato come un impegno da parte di Microsoft e, dopo la data della pubblicazione, Microsoft non è in grado di garantire l'accuratezza di alcuna delle informazioni presentate.

Questo documento viene fornito con soli intenti informativi. MICROSOFT NON FORNISCE ALCUNA GARANZIA, ESPLICITA, IMPLICITA O DI LEGGE, RIGUARDO ALLE INFORMAZIONI CONTENUTE IN QUESTO DOCUMENTO.

Il rispetto di tutte le leggi applicabili in materia di copyright è esclusivamente a carico dell'utente. Fermi restando tutti i diritti coperti da copyright, nessuna parte di questo documento potrà comunque essere riprodotta o inserita in un sistema di riproduzione o trasmessa in qualsiasi forma e con qualsiasi mezzo (in formato elettronico, meccanico, su fotocopia, come registrazione o altro) per qualsiasi scopo, senza il permesso scritto di Microsoft Corporation.

Microsoft può essere titolare di brevetti, domande di brevetto, marchi, copyright o altri diritti di proprietà intellettuale relativi all'oggetto del presente documento. Salvo quanto espressamente previsto in un contratto scritto di licenza Microsoft, la consegna del presente documento non implica la concessione di alcuna licenza su tali brevetti, marchi, copyright o altra proprietà intellettuale.

Se non specificato diversamente, ogni riferimento a società, nomi, dati e indirizzi utilizzati nel presente documento è puramente casuale e ha il solo scopo di illustrare l'uso del prodotto Microsoft.

© 2005 Microsoft Corporation. Tutti i diritti riservati.

Microsoft, SQL Server, Windows e Windows Server sono marchi registrati o marchi commerciali di Microsoft Corporation negli Stati Uniti e/o in altri paesi.

I nomi di prodotti e società reali citati nel presente documento possono essere marchi dei rispettivi proprietari.
