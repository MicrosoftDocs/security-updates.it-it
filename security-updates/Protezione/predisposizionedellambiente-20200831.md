---
TOCTitle: 'Predisposizione dell''ambiente'
Title: 'Predisposizione dell''ambiente'
ms:assetid: 'dcffe076-8f32-4bc3-93fc-e64c47b6ef9e'
ms:contentKeyID: 20200831
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536232(v=TechNet.10)'
---

Protezione delle reti LAN senza fili con PEAP e password
========================================================

### Capitolo 3: Predisposizione dell'ambiente

Aggiornato: 3 aprile 2004

##### In questa pagina

[](#eiaa)[Cenni preliminari](#eiaa)
[](#ehaa)[Prima di iniziare](#ehaa)
[](#egaa)[Prerequisiti e presupporti dell'infrastruttura IT](#egaa)
[](#efaa)[Operazioni preliminari per l'implementazione](#efaa)
[](#eeaa)[Installazione degli strumenti della soluzione](#eeaa)
[](#edaa)[Impostazione della rete e dell'infrastruttura di directory](#edaa)
[](#ecaa)[Preparazione dei server](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Riferimenti](#eaaa)

### Cenni preliminari

In questo capitolo viene descritto come predisporre l'ambiente IT per la distribuzione dell'infrastruttura di protezione per la rete LAN senza fili. Le principali operazioni necessarie per preparare l'ambiente includono:

-   Preparazione del dominio del servizio Microsoft® Active Directory® mediante la creazione dei gruppi di protezione richiesti.

-   Preparazione dei server per l'installazione di IAS (Internet Authentication Service) e Servizi certificati. Questa operazione richiede il completamento di tre attività secondarie:

    -   Applicazione delle impostazioni di protezione ai server.

    -   Installazione degli strumenti richiesti sui server.

    -   Aggiornamento dei server al fine di garantire l'assenza di vulnerabilità di protezione conosciute.

[](#mainsection)[Inizio pagina](#mainsection)

### Prima di iniziare

Prima di proseguire con gli argomenti del capitolo, è necessario comprendere a fondo l'architettura e la progettazione di questa soluzione, descritta nel capitolo 2, "Pianificazione dell'implementazione della protezione di reti LAN senza fili". È necessario conoscere inoltre le procedure di installazione e amministrazione di Microsoft Windows® 2000 Server o Microsoft Windows Server™ 2003. Può anche essere utile avere dimestichezza con i seguenti argomenti:

-   Concetti relativi ad Active Directory tra cui la struttura e gli strumenti di gestione di Active Directory; la gestione di utenti, gruppi e altri oggetti Active Directory; e l'uso dei criteri di gruppo.

-   Argomenti correlati alla protezione di sistemi Windows, inclusi concetti di protezione quali l'impostazione di utenti e gruppi, la gestione di elenchi di controllo di accesso e l'applicazione di impostazioni di protezione mediante criteri di gruppo.

-   Windows Scripting Host e il linguaggio Microsoft Visual Basic®, Scripting Edition (VBScript).

[](#mainsection)[Inizio pagina](#mainsection)

### Prerequisiti e presupporti dell'infrastruttura IT

Questo capitolo e tutti gli altri della guida sono basati sui seguenti presupposti relativi all'infrastruttura IT, anche se alcuni aspetti potrebbero essere implementati nell'ambito della soluzione. In molti casi questi presupposti non rappresentano dei requisiti imprescindibili; se sono disponibili configurazione alternative, verranno indicate nella guida.

-   Un insieme di strutture Active Directory che utilizza controller di dominio Windows 2000 Server o Windows Server 2003, con tutti gli utenti della rete LAN senza fili configurati come membri di un dominio appartenente allo stesso insieme di strutture.

    **Nota:** i controller di dominio su cui sono installati IAS e Servizi certificati devono eseguire Windows Server 2003.

-   Due o più server che eseguono Windows Server 2003, Standard Edition (è anche supportato Windows Server 2003, Enterprise Edition) su cui installare componenti della soluzione.

-   Questi server non sono in grado di eseguire IAS e Servizi certificati in aggiunta ad altri servizi e applicazioni esistenti. Servizi certificati è installato solo sul primo server.

-   IAS verrà installato sui controller di dominio esistenti. Questo è un aspetto facoltativo, in quanto è possibile installare IAS su un server membro del dominio.

-   Servizi certificati verrà installato su un controller di dominio. In alternativa, è possibile installare Servizi certificati su un server membro del dominio.

-   Si ha accesso al supporto di installazione di Windows Server 2003.

-   Il dominio in cui verrà installato IAS è in esecuzione nella modalità nativa di Windows 2000. Questo aspetto è facoltativo.

-   L'installazione o pianificazione di un'infrastruttura LAN senza fili costituita da più punti di accesso senza fili. La progettazione dell'infrastruttura LAN senza fili e altri aspetti correlati, come la disposizione dei punti di accesso senza fili e la selezione del canale, esulano dall'ambito di questa guida.

-   L'intera organizzazione deve disporre al massimo di 50 punti di accesso senza fili.

-   Uno o più uffici periferici senza controller di dominio locali (e senza server IAS), ma con client che richiedono la connessione alla rete LAN senza fili.

Sebbene la soluzione sia stata creata per questo profilo specifico, la progettazione base può essere adattata a molte altre configurazioni, ad esempio, filiali con controller di dominio locali o l'installazione in insiemi di strutture a più domini. L'impatto delle configurazioni alternative valide, se disponibili, è segnalato nella guida.

[](#mainsection)[Inizio pagina](#mainsection)

### Operazioni preliminari per l'implementazione

#### Autorizzazioni necessarie

Per svolgere le procedure descritte in questo capitolo è necessario utilizzare un account membro del gruppo Administrators per il dominio in cui sono inclusi i server. Per impostazione predefinita, l'account incorporato Administrator del dominio è membro del gruppo Administrators. È tuttavia possibile utilizzare qualsiasi altro account membro di questo gruppo.

**Nota:** questa guida è basata sul presupposto che si stia installando Servizi certificati e IAS su un controller di dominio. Se si esegue l'installazione di questi servizi su server diversi dai controller di dominio, sarà sufficiente che l'account sia membro del gruppo Administrators locale dei singoli server.

#### Strumenti necessari

Per completare le procedure descritte in questo capitolo, sono necessari i seguenti strumenti:

**Tabella 3.1: Strumenti necessari**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Strumento</p></th>
<th><p>Descrizione</p></th>
<th><p>Origine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Script della soluzione per reti LAN senza fili</p></td>
<td style="border:1px solid black;"><p>Set di script e strumenti fornito con questa soluzione.</p></td>
<td style="border:1px solid black;"><p>I dettagli relativi all'installazione sono forniti in questo capitolo.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Console di gestione Criteri di gruppo</p></td>
<td style="border:1px solid black;"><p>Strumento di gestione avanzata per oggetti Criteri di gruppo, che consente di importarli ed esportarli.</p></td>
<td style="border:1px solid black;"><p>Può essere scaricato dal sito Microsoft.com.<br />
I dettagli relativi all'installazione sono forniti in questo capitolo.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>CAPICOM</p></td>
<td style="border:1px solid black;"><p>Libreria di sistema che consente l'utilizzo di script per operazioni relative ai certificati e alla protezione.</p></td>
<td style="border:1px solid black;"><p>Può essere scaricato dal sito Microsoft.com.<br />
I dettagli relativi all'installazione sono forniti in questo capitolo.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p><em>DSACLs.exe</em></p></td>
<td style="border:1px solid black;"><p>Strumento della riga di comando che consente l'impostazione delle autorizzazioni in oggetti Active Directory.</p></td>
<td style="border:1px solid black;"><p>CD di installazione di Windows Server 2003.<br />
I dettagli relativi all'installazione sono forniti in questo capitolo.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Utenti e computer di Active Directory</p></td>
<td style="border:1px solid black;"><p>Strumento MMC (Microsoft Management Console) utilizzato per gestire utenti, gruppi, computer e altri oggetti Active Directory.</p></td>
<td style="border:1px solid black;"><p>Installato con Windows Server 2003.</p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Installazione degli strumenti della soluzione
  
Con la presente guida sono forniti alcuni script e strumenti che consentono di semplificare la configurazione e l'utilizzo di questa soluzione. Tali script e strumenti devono essere installati in ogni server IAS. Alcuni script sono richiesti durante le normali operazioni (come descritto nel capitolo 8, "Gestione della soluzione per reti LAN senza fili"), di conseguenza, non devono essere eliminati al termine dell'installazione. Per impostazione predefinita, gli script vengono installati nella cartella C:\\Programmi\\Microsoft\\Microsoft WLAN-PEAP Tools.
  
**Per installare gli script e gli strumenti in ogni server**
  
1.  Copiare nel server il file **PEAPWLAN.msi** fornito con la soluzione.
  
2.  Da **Esplora risorse** fare doppio clic sul file **PEAPWLAN.msi** per avviare l'installazione, quindi fare clic su **Avanti** per iniziare il processo.
  
3.  Se si desidera installare gli script in una posizione diversa dalla cartella predefinita C:\\Programmi\\Microsoft\\Microsoft WLAN-PEAP Tools, specificarne il percorso.  
    Verrà richiesto se installare gli script solo per l'account in uso o per tutti gli utenti. Fare clic su **Tutti gli utenti**, scegliere **Avanti** per proseguire e quindi nuovamente **Avanti** per confermare.
  
4.  Dopo aver completato l'installazione, verrà visualizzato il file **Tools Readme**. Questo file contiene una importante dichiarazione di non responsabilità e una breve descrizione degli script installati. È necessario leggere tutto il contenuto prima di proseguire. Fare clic su **Avanti** per proseguire, quindi su **Fine** per completare l'installazione.
  
Per semplificare l'accesso a questi script, è possibile creare un collegamento per l'apertura di una shell dei comandi nella cartella in cui sono archiviati gli script.
  
**Per creare un collegamento alla cartella MSS WLAN Tools**
  
1.  In **Esplora risorse** visualizzare la cartella **MSS WLAN Tools**, il cui percorso predefinito è C:\\Programmi\\Microsoft\\Microsoft WLAN-PEAP Tools.
  
2.  Fare doppio clic sul file batch di script **CreateShortcut.cmd**. In questo modo viene creato sul desktop un collegamento denominato MSS WLAN Tools.
  
3.  È possibile spostare o copiare questo collegamento nel menu di avvio.
  
#### Utilizzo degli script
  
Gli script sono creati in Windows Scripting Host mediante il linguaggio VBScript e funzionano tutti in maniera analoga. Devono essere eseguiti mediante i due file batch (MSSSetup.cmd e MSSTools.cmd) anziché eseguirli direttamente. I file batch semplificano la sintassi degli script.
  
La maggior parte degli script accetta un solo parametro, che specifica la funzione da eseguire. In alcuni casi possono accettare parametri aggiuntivi (illustrati nella guida quando è necessario). Gli script vengono eseguiti dalla cartella in cui vengono installati, ovvero da una shell dei comandi con la directory di lavoro corrente impostata sulla cartella di installazione degli strumenti.
  
L'esecuzione degli script determina i seguenti tipi di risultati:
  
-   Finestre di messaggio in cui sono visualizzate informazioni o avvisi, richieste di scelta tra più opzioni o di immissione di valori.
  
-   Informazioni dettagliate sullo stato del processo inviate progressivamente a una finestra durante l'esecuzione dello script. Se lo script rileva un errore, nella finestra vengono visualizzate informazioni sull'errore. Al termine dell'esecuzione dello script, viene chiesto se si desidera chiudere la finestra o lasciarla aperta per ulteriori controlli (ad esempio, può essere lasciata aperta per valutare gli errori).
  
-   In molti casi le informazioni dettagliate sullo stato del processo vengono scritte anche in un file di registro (%systemroot%\\debug\\ MSSWLAN-Setup.log). Questo file è destinato a operazioni di risoluzione dei problemi e di controllo dell'installazione. Tutte le attività di installazione e configurazione, insieme alle operazioni di esportazione e importazione delle impostazioni IAS vengono registrate in questo file di registro. Per motivi di sicurezza, le attività che generano segreti RADIUS (password) per i punti di accesso senza fili non vengono registrate.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazione della rete e dell'infrastruttura di directory
  
#### Configurazione della rete
  
È necessario connettere i componenti alla rete come illustrato nella figura seguente o in base ai requisiti specifici della rete.
  
[![](images/Dd536232.PEAP_301(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536232.peap_301_big(it-it,technet.10).gif)
  
**Figura 3.1 Semplice configurazione di rete WLAN**
  
Questa figura mostra il livello più semplice di configurazione in cui i server IAS, i punti di accesso e gli altri elementi della rete interna sono connessi alla stessa LAN. Nelle installazioni più estese, la rete solitamente è suddivisa in più LAN virtuali LAN (VLAN) connesse tramite router o commutazione di livello 3. I dettagli della configurazione variano enormemente in base ai requisiti dell'organizzazione, ma una trattazione dettagliata di questo argomento esula dall'ambito di questa guida.
  
Per ulteriori informazioni sulla configurazione della rete per un'infrastruttura di rete LAN senza fili, vedere il capitolo "Deploying Wireless LANs" di *Windows Server 2003 Deployment Kit* (in inglese).
  
##### Configurazione della rete IP
  
La soluzione è nettamente indipendente della rete VLAN e dalla organizzazione di subnet. Come è stato illustrato nel capitolo 2, "Pianificazione dell'implementazione della protezione di reti LAN senza fili", è possibile collocare i client senza fili in una VLAN diversa rispetto al resto della rete. Tuttavia, questa soluzione è stata verificata solo per lo scenario più semplice, ovvero i client senza fili sono inclusi nella stessa LAN del resto della rete e condividono la stessa subnet IP.
  
Se si sceglie di collocare i client senza fili in una VLAN separata, è necessario allocare una subnet IP specifica per tali client e collegare la rete VLAN senza fili al resto della rete mediante un router o una commutazione di livello 3. Nel caso di ambienti più complessi esistono alcuni vantaggi nella configurazione di subnet separate per i client di reti LAN senza fili in ogni sede fisica. Tali vantaggi includono i seguenti aspetti:
  
-   È possibile tenere separati gli ambiti DHCP (Dynamic Host Configuration Protocol) per i client cablati e quelli senza fili; in questo modo i tempi di lease per i client di reti LAN senza fili si riducono in maniera significativa.
  
-   Se si dispone di un ambiente con routing che presenta più subnet nello stesso sito, l'allocazione di una singola subnet per tutti i client di reti LAN senza fili in tale sito consente a tali client di spostarsi tra i punti di accesso utilizzando lo stesso indirizzo IP.
  
-   È possibile utilizzare la subnet della rete LAN senza fili per definire un sito Active Directory e associare impostazioni specifiche di criteri di gruppo a tale sito. Tuttavia, non è possibile utilizzare questo meccanismo per applicare le impostazioni del client di rete LAN senza fili descritte nel capitolo 6, "Configurazione dei client delle reti LAN senza fili", poiché tali impostazioni devono essere applicate ai client prima della connessione alla rete LAN senza fili.
  
#### DHCP
  
Gli indirizzi IP e le informazioni della rete IP devono essere assegnati ai client delle reti LAN senza fili. Nella soluzione proposta viene utilizzato il servizio Windows DHCP per questo scopo. Di conseguenza, è necessario che un servizio DHCP sia disponibile per i client della rete LAN senza fili.
  
È necessario assegnare un ambito DHCP separato per ogni subnet in cui verranno distribuiti i client. Ad esempio, se sono presenti due siti differenti collegati tramite una connessione WAN di routing, è necessario creare un ambito DHCP per ogni subnet. Se si assegnano subnet separate per i client di reti LAN senza fili e per quelli di LAN cablate, è necessario configurare un ambito separato per ogni subnet della rete LAN senza fili. Inoltre, se esistono connessioni di routing tra i punti di accesso e i server DHCP, è necessario configurare gli agenti di inoltro DHCP sui router o installare l'agente di inoltro DHCP Windows su un server nella stessa subnet dei punti di accesso.
  
Per garantire una maggiore disponibilità, è opportuno valutare l'uso di una configurazione DHCP con capacità di recupero mediante ambiti divisi, DHCP in cluster o configurazioni DHCP di standby. Per ulteriori informazioni, vedere il capitolo "Deploying DHCP" di *Windows Server 2003 Deployment Kit* (in inglese).
  
#### DNS
  
Il servizio Active Directory dipende dal corretto funzionamento di un servizio DNS (Domain Name System). La soluzione proposta è basata sul presupposto che tale servizio sia disponibile e attivo. Il servizio DNS sarà stato installato nell'ambito del processo di installazione di Active Directory o configurato separatamente.
  
#### Active Directory
  
Questa soluzione è stata progettata e collaudata utilizzando la seguente configurazione di Active Directory:
  
-   Un insieme di strutture Active Directory a singolo dominio.
  
-   Controller di dominio Windows Server 2003 (nuova installazione, non aggiornati da controller di dominio Windows 2000).
  
-   Un livello funzionale di dominio della modalità originale di Windows 2000.
  
In molti casi è possibile utilizzare altre configurazioni di Active Directory, ad esempio, utilizzando più domini o controller di dominio Windows 2000. Nei casi in cui queste configurazioni sono supportate da Microsoft, nella guida sono fornite istruzioni supplementari sull'utilizzo. Tuttavia, queste configurazioni alternative non fanno parte della soluzione principale sottoposta a test.
  
##### Requisiti per tutte le versioni di Active Directory
  
Un dominio in modalità nativa consente di creare gruppi universali di protezione Active Directory. L'utilizzo di questi gruppi semplifica la gestione dei criteri di accesso in una rete con più domini. Tuttavia, questa impostazione è superflua per le distribuzioni a un singolo dominio. Gli script di installazione verificano se il dominio è o meno in modalità nativa. Se è attiva la modalità nativa, lo script utilizzerà i gruppi universali, in caso contrario verranno utilizzati solo i gruppi globali.
  
Active Directory deve disporre di uno schema Windows Server 2003, necessario per supportare le impostazioni degli oggetti Criteri di gruppo delle reti senza fili. Non è richiesto uno specifico livello di funzionalità dell'insieme di strutture Active Directory. Questa soluzione presuppone il livello predefinito di funzionalità dell'insieme di strutture Windows 2000.
  
Per ulteriori informazioni sulla modalità di dominio e dell'insieme di strutture, vedere i riferimenti alla fine del presente capitolo.
  
##### Utilizzo dei controller di dominio per Windows 2000
  
In questa soluzione IAS e Servizi certificati sono installati su sistemi Windows Server 2003. Non verranno fornite istruzioni per l'utilizzo delle versioni Windows 2000 di questi componenti. Se si utilizzano controller di dominio Windows 2000 e non si intende eseguirne l'aggiornamento a Windows Server 2003, è necessario aggiornare lo schema al livello Windows 2003. Per ulteriori informazioni sull'aggiornamento dello schema, vedere i riferimenti alla fine del presente capitolo.
  
Se questa soluzione verrà utilizzata in un dominio o insieme di strutture basato su controller di dominio Windows 2000, è necessario verificare che a tali controller di dominio sia applicato il Service Pack 3 (SP3) o versione successiva. Il service pack è necessario per garantire che i controller di dominio supportino la firma LDAP (Lightweight Directory Access Protocol). Si tratta di un'ulteriore misura di protezione richiesta dalle autorità di certificazione di Windows Server 2003 e dai client Windows XP che utilizzano la registrazione automatica dei certificati.
  
##### Verifica della protezione dei criteri di account di dominio
  
Questa soluzione si basa sulle password di utenti e computer per l'autenticazione degli stessi nella rete LAN senza fili. È quindi estremamente importante non utilizzare password semplici o vuote. Le password facilmente intuibili consentono ai pirati informatici di accedere facilmente alla rete LAN senza fili. Poiché le stesse password vengono utilizzate per autenticare l'utente o il computer nel dominio, il pirata informatico potrebbe accedere anche a tutte le risorse della rete.
  
Il modo più semplice di evitare l'utilizzo di password semplici consiste nell'impostare criteri per password complesse nell'oggetto Criteri di gruppo del dominio predefinito. È inoltre consigliabile applicare scadenze periodiche delle password, validità minima della password e controllo della cronologia delle password (per verificare che gli utenti non riutilizzino la stessa password).
  
**Avviso:** prima di modificare i criteri per le password del dominio, è necessario avvisare gli utenti e gli amministratori. Per evitare disagi e confusione tra gli utenti, è consigliabile informarli in anticipo dei nuovi criteri per le password che si intende adottare, fornendo tutte le istruzioni necessarie per scegliere password valide.
  
Per consigli sulle procedure ottimali relative ai criteri per le password del dominio, vedere la *Guida per la protezione di Windows Server 2003*. I riferimenti relativi a questa pubblicazione sono forniti alla fine del presente capitolo.
  
##### Creazione di gruppi di protezione
  
Seguire la procedura fornita più avanti in questa sezione per creare gruppi di protezione in Active Directory da utilizzare in questa soluzione. I gruppi creati sono elencati nella tabella che segue e, se specificato, sono definiti anche i membri. Per impostazione predefinita, questi gruppi vengono creati nel contenitore Users.
  
**Tabella 3.2: Gruppi di protezione e membri**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="25%" />  
<col width="25%" />  
<col width="25%" />  
<col width="25%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Gruppo di protezione</p></th>  
<th><p>Scopo</p></th>  
<th><p>Tipo di gruppo</p></th>  
<th><p>Membri</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Wireless LAN Users</p></td>
<td style="border:1px solid black;"><p>Specifica quali utenti possono eseguire l'autenticazione per la rete LAN senza fili.</p></td>
<td style="border:1px solid black;"><p>Globale</p></td>
<td style="border:1px solid black;"><p>Domain Users</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Wireless LAN Computers</p></td>
<td style="border:1px solid black;"><p>Specifica quali computer possono eseguire l'autenticazione per la rete LAN senza fili.</p></td>
<td style="border:1px solid black;"><p>Globale</p></td>
<td style="border:1px solid black;"><p>Computer del dominio</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Wireless LAN Access</p></td>
<td style="border:1px solid black;"><p>Questo gruppo è utilizzato nel criterio di accesso RADIUS per controllare l'accesso alla rete LAN senza fili.</p></td>
<td style="border:1px solid black;"><p>Universale</p></td>
<td style="border:1px solid black;"><p>Wireless LAN Users<br />
Wireless LAN Computers.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Wireless LAN Computer Settings</p></td>
<td style="border:1px solid black;"><p>Specifica quali computer ricevono impostazioni della rete LAN senza fili dai criteri di gruppo.</p></td>
<td style="border:1px solid black;"><p>Domain Local</p></td>
<td style="border:1px solid black;"><p>Wireless LAN Computers.</p></td>
</tr>  
</tbody>  
</table>
  
**Per creare gruppi di protezione e definire membri di tali gruppi**
  
1.  Aprire una shell comandi utilizzando il collegamento **MSS WLAN Tools**.
  
2.  Al prompt dei comandi digitare *MSSSetup CreateWLANGroups*, quindi premere **INVIO**.
  
    **Importante:** se i gruppi Domain Users e Domain Computers sono stati spostati dalla posizione predefinita al contenitore Users, essi non verranno aggiunti rispettivamente ai gruppi Wireless LAN Users e Wireless LAN Computers. In tal caso, è necessario aggiungerli manualmente a tali gruppi.
  
    **Nota:** se si installa questa soluzione in un dominio a modalità mista, il gruppo Wireless LAN Access verrà creato come gruppo globale di dominioanziché come gruppo universale. Di conseguenza, se si intende installare questa soluzione in un insieme di strutture con più domini, sarà necessario creare uno di tali gruppi in ogni dominio (questa attività è descritta nel capitolo 2, "Pianificazione dell'implementazione della protezione di reti LAN senza fili").
  
    Se si installa questa soluzione in più domini, è necessario creare i gruppi globali Wireless LAN Users e Wireless LAN Computers in ogni dominio e aggiungerli al gruppo Wireless LAN Access. È inoltre necessario creare un gruppo locale di dominio Wireless LAN Computer Settings in ogni dominio in cui sono presenti client di rete LAN senza fili e aggiungere il gruppo universale Wireless LAN Computers come membro.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Preparazione dei server
  
Questa sezione è dedicata alla configurazione specifica per i server. La maggior parte delle procedure che seguono devono essere eseguite per ogni server che si intende installare come server IAS. La procedura decritta nella sezione "Configurazione della protezione del server" costituisce l'unica eccezione in quanto, anche se le impostazioni di protezione vengono applicate a ogni server, questa procedura deve essere eseguita una sola volta per ogni dominio. Le impostazioni vengono quindi applicate automaticamente ad altri server del dominio.
  
#### Sistemi operativi supportati
  
Questa soluzione è stata creata e sottoposta a test utilizzando Windows Server 2003, Standard Edition per tutti i componenti server. In ogni modo, la guida e gli script di installazione sono gli stessi anche per Windows Server 2003, Enterprise Edition.
  
Prima di stabilire se è necessario o meno utilizzare Windows Server 2003, leggere la sezione relativa all'utilizzo di Windows Server Standard o Enterprise Edition del capitolo 2, "Pianificazione dell'implementazione della protezione di reti LAN senza fili". L'uso di Windows Server 2003, Standard Edition pone dei limiti alle funzionalità di Servizi certificati e al numero di punti di accesso senza fili che possono essere supportati da IAS. Tali limitazioni possono risultare inaccettabili per le organizzazioni di grandi dimensioni.
  
Questa soluzione non è stata progettata per supportare le versioni precedenti di Windows Server, né è stata sottoposta a test con tali sistemi. Le versioni Windows 2000 Server di IAS e Servizi certificati possono funzionare per alcuni o tutti i ruoli server previsti in questa soluzione, ma la descrizione della configurazione necessaria per utilizzare tali versioni non rientra nell'ambito di questa documentazione.
  
#### Linee guida per l'hardware
  
Il primo server installato eseguirà Servizi certificati e IAS. Sebbene Servizi certificati richieda risorse minime in questa soluzione, è necessario verificare che il carico generato da IAS sul server non incida negativamente sulle prestazioni del controller di dominio del server. Questa condizione si verifica raramente e solo nelle implementazioni più estese di IAS. Se necessario, aggiungere un controller di dominio aggiuntivo allo stesso sito di Active Directory per compensare questo sovraccarico.
  
Se si intende abilitare la registrazione RADIUS, è necessario allocare un disco fisico separato per i registri.
  
**Tabella 3.3: Hardware minimo consigliato per il server IAS**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Elemento</p></th>  
<th><p>Requisito</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>CPU</p></td>
<td style="border:1px solid black;"><p>CPU singola a 733 MHz o superiore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Memoria</p></td>
<td style="border:1px solid black;"><p>256 MB</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Interfacce di rete</p></td>
<td style="border:1px solid black;"><p>Scheda di rete singola</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Archiviazione disco</p></td>
<td style="border:1px solid black;"><p>Controller RAID IDE o SCSI</p>
<p>2 x 18 GB (SCSI) o 2 x 20 GB (IDE) configurati come volume RAID 1</p>  
<p>Archiviazione su supporti rimovibili (CD-RW o nastro di backup), in assenza di una funzionalità di backup di rete</p>
<p>Unità disco floppy da 1,44 MB per il trasferimento dei dati.</p></td>
</tr>
</tbody>
</table>
<p> </p>

Per ulteriori informazioni sui requisiti di prestazioni dell'hardware, leggere la sezione dedicata a questo argomento nel capitolo 2, "Pianificazione dell'implementazione della protezione di reti LAN senza fili".

#### Come ottenere e installare il software di supporto

In questa sezione è elencato il software aggiuntivo richiesto sui server e il modo in cui ottenerlo e installarlo.

##### Console di gestione Criteri di gruppo

GPMC (Group Policy Management Console) consente di installare e configurare gli oggetti Criteri di gruppo (GPO) utilizzati dalla soluzione. La console GPMC deve essere installata solo sul primo server su cui viene installato IAS; l'installazione sugli altri server IAS è facoltativa.

**Nota:** l'installazione di GPMC modifica leggermente l'interfaccia utente di Utenti e computer di Active Directory sul server in cui è installato GPMC. Per ulteriori informazioni sull'utilizzo e il download di GPMC, vedere il riferimento alla fine del presente capitolo.

**Per installare Group Policy Management Console**

1.  Scaricare il file di installazione **Gpmc.msi** dall'area di download del sito Web Microsoft.

2.  Accertarsi di aver eseguito l'accesso con un account membro del gruppo Administrators del dominio (o del gruppo locale Administrators del computer su cui si installa GPMC, se l'installazione non avviene su un controller di dominio).

3.  In **Esplora risorse** fare doppio clic sul file di installazione **Gpmc.msi**.

4.  Per installare GPMC, seguire le richieste della procedura di installazione guidata e accettare tutte le impostazioni predefinite.

    **Importante:** è necessario installare GPMC nella cartella Programmi (di qualsiasi unità). È consigliabile inoltre utilizzare la cartella di installazione predefinita, GPMC, all'interno della cartella Programmi (se si modifica il nome della cartella sarà necessario aggiornare nel file Constants.txt il nome della cartella utilizzata per installare GPMC). Nelle procedure che seguono vengono utilizzati alcuni strumenti installati da GPMC e, se la console viene installata in una posizione diversa, tali strumenti non potranno essere individuati.

##### Strumenti di supporto di Windows Server 2003

Alcuni strumenti di supporto di Windows sono utilizzati dagli script e dalle procedure di configurazione descritti in questa soluzione. L'installazione di tali strumenti deve essere eseguita dal supporto di installazione di Windows Server 2003. Poiché sono richiesti dagli script di installazione e configurazione della CA, è necessario installarli sul server in cui si intende installare Servizi certificati. Sebbene non siano necessari sugli altri server, è possibile installarli in altri server se lo si desidera.

**Per installare gli strumenti di supporto di Windows Server 2003**

1.  Accertarsi di aver eseguito l'accesso con un account membro del gruppo Administrators del dominio (o del gruppo locale Administrators del computer su cui si installano gli strumenti di supporto, se l'installazione non avviene su un controller di dominio).

2.  Inserire il **CD di installazione** di **Windows Server 2003** (o collegare l'origine dell'installazione se si esegue il processo in rete o da altro supporto).

3.  In **Esplora risorse** individuare il supporto di installazione (unità CD o floppy) e il file **\\support\\tools\\supptools.msi**. Fare doppio clic sul file per iniziare l'installazione.

4.  Seguire le richieste della procedura guidata per installare gli strumenti di supporto e accettare il Contratto di Licenza e la cartella di installazione predefinita.

##### CAPICOM

CAPICOM è un interfaccia utilizzabile tramite script per un insieme di funzioni di protezione Windows definito CryptoAPI (CAPI). L'interfaccia CAPICOM è richiesta dagli script di controllo dell'integrità di Servizi certificati e per generare i segreti RADIUS utilizzati per l'autenticazione dei punti di accesso senza fili. È necessario installare CAPICOM versione 2.0 o successiva su tutti i server IAS dell'organizzazione.

La versione più recente di CAPICOM 2.0 è disponibile nell'area di download del sito Web Microsoft (vedere la sezione "Riferimenti" alla fine del presente capitolo).

Il file di distribuzione di CAPICOM non contiene un processo di installazione automatica, quindi è necessario utilizzare lo script batch, InstCAPICOM.cmd (fornito con la soluzione). Se si desidera eseguire manualmente questi passaggi, è possibile copiare i comandi dallo script batch.

**Per installare CAPICOM**

1.  Scaricare il file di distribuzione di **CAPICOM**, **CCR2INST.exe**, dall'area di download del sito Web Microsoft e copiarlo in una cartella temporanea del server.

2.  Accertarsi di aver eseguito l'accesso con un account membro del gruppo Administrators del dominio (o del gruppo locale Administrators del computer su cui si installa l'interfaccia CAPICOM, se l'installazione non avviene su un controller di dominio).

3.  Aprire una shell comandi utilizzando il collegamento **MSS WLAN Tools**.

4.  Al prompt dei comandi digitare:

    *InstCAPICOM \[d:\]PercorsoFileDistCC*\\CCR2INST.EXE, quindi premere **INVIO**.

    **Nota:** Sostituire a *\[d:\]PercorsoFileDistCC* il percorso completo (inclusa la lettera di unità, se diversa da quella indicata) della cartella in cui è stato copiato il file di distribuzione di CAPICOM.

##### Microsoft Baseline Security Analyzer (MBSA)

Questo strumento consente di verificare che la protezione del sistema operativo sia costantemente aggiornata e di rilevare eventuali problemi relativi alla configurazione della protezione dei server. Per analizzare i sistemi Windows Server 2003, è necessario utilizzare la versione 1.1.1 o una versione successiva di MBSA. La versione più recente di MBSA è disponibile nell'area di download del sito Web Microsoft.

**Per installare MBSA**

1.  Scaricare il file di installazione **mbsasetup.msi** dall'area di download del sito Web Microsoft.

2.  Accertarsi di aver eseguito l'accesso con un account membro del gruppo Administrators del dominio (o del gruppo locale Administrators del computer su cui si installa MBSA, se l'installazione non avviene su un controller di dominio).

3.  In **Esplora risorse** individuare il file **mbsasetup.msi** e fare doppio clic su di esso.

4.  Per installare MBSA, seguire le richieste della procedura di installazione guidata e accettare tutte le impostazioni predefinite.

#### Configurazione della protezione dei server

In questa sezione viene descritto come applicare i criteri di protezione e altre misure di sicurezza a Windows Server 2003 prima di installare IAS e Servizi certificati.

Questa soluzione è progettata per essere installata sui server esistenti (in genere controller di dominio). Le impostazioni di protezione utilizzate in questa sezione tendono intenzionalmente a lasciare inalterati i valori esistenti per evitare il rischio di conflitti con le impostazioni di protezione delle applicazioni e dei servizi installati, che potrebbero già essere attivi sul server.

##### Utilizzo della Guida per la protezione di Windows Server 2003

Le impostazioni di protezione predefinite di Windows Server 2003 garantiscono un livello di protezione avanzato. Per la maggior parte delle organizzazioni queste impostazioni assicurano una protezione adeguata per i sistemi se combinate con un processo di aggiornamento efficace (per ulteriori informazioni sull'aggiornamento, vedere la sezione "Aggiornamento della protezione dei server" più avanti in questo capitolo). Tuttavia, è necessario valutare anche i suggerimenti forniti nella *Guida per la protezione di Windows Server 2003*. Questa guida definisce le impostazioni di protezione appropriate per i diversi ruoli server.

I server utilizzati in questa soluzione svolgono diversi ruoli tra quelli definiti nella *Guida per la protezione*: i ruoli "Controller di dominio" e "Server RADIUS" per la maggior parte dei server e, per il primo server, anche il ruolo "Autorità di certificazione". Per ogni ruolo nella guida è definito un modello di protezione con tutte le impostazioni di protezione appropriate a tale ruolo. Nel caso di un server con più ruoli, è necessario applicare una combinazione dei modelli di protezione corrispondenti a ognuno dei diversi ruoli del server. Nei server potrebbero inoltre essere presenti altri servizi di infrastruttura come DNS, DHCP e WINS (Windows Internet Naming Service), in tal caso sarebbe necessario includere anche i modelli di protezione appropriati a tali ruoli. Per istruzioni su questo argomento, vedere la *Guida per la protezione di Windows Server 2003*.

**Avviso:** i modelli delle impostazioni di protezione nella *Guida per la protezione di Windows Server 2003* disabilitano alcuni servizi non richiesti dai ruoli server definiti. Se sono presenti altre applicazioni o servizi in esecuzione sui server, è necessario sottoporli a un test per verificare che i modelli di protezione non li disabilitino o modifichino impostazioni di protezione su cui sono basate tali applicazioni o servizi. Le istruzioni relative alla combinazione dei ruoli e alla modifica delle impostazioni per adattare altre applicazioni sono incluse nella *Guida per la protezione di Windows Server 2003*.

##### Applicazione delle impostazioni di protezione

Diversamente dalla maggior parte delle altre procedure descritte nella sezione "Preparazione dei server" di questo capitolo, in questo caso non è necessario eseguire la procedura su ogni server. Le impostazione vengono invece importate in un oggetto Criteri di gruppo in Active Directory e quindi applicate globalmente a tutti i server.

Le impostazioni di protezione applicate in questa soluzione sono di due tipi. Il primo tipo viene applicato per configurare l'avvio automatico di tutti i servizi richiesti (nel caso vengano interrotti o disabilitati da altri criteri di protezione applicati al computer). Il secondo tipo viene applicato per modificare il criterio di controllo in modo che vengano catturati nel registro anche i controlli non riusciti per gli eventi comuni, come l'accesso.

Nella tabella che segue sono elencati i servizi impostati per l'avvio automatico.

**Tabella 3.4: Servizi Windows abilitati tramite i criteri**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Servizio</p></th>
<th><p>Impostazione del criterio</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Automatico</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Servizio autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>Automatico</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Provider di copie replicate software Microsoft</p></td>
<td style="border:1px solid black;"><p>Automatico</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Archivi rimovibili</p></td>
<td style="border:1px solid black;"><p>Automatico</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Utilità di pianificazione</p></td>
<td style="border:1px solid black;"><p>Automatico</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Copia shadow del volume</p></td>
<td style="border:1px solid black;"><p>Automatico</p></td>
</tr>  
</tbody>  
</table>
  
Nella tabella che segue sono elencate le categorie di controllo per cui è abilitato il controllo delle operazioni non riuscite oltre a quello delle operazioni riuscite.
  
**Tabella 3.5: Impostazioni del Criterio Controllo**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Criteri di controllo</p></th>  
<th><p>Impostazione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Controlla eventi accesso account</p></td>
<td style="border:1px solid black;"><p>Operazioni riuscite/Operazioni non riuscite (l'impostazione predefinita è Operazioni riuscite)</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Controlla eventi di gestione degli account</p></td>
<td style="border:1px solid black;"><p>Operazioni riuscite/Operazioni non riuscite (l'impostazione predefinita è Operazioni riuscite)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Controlla eventi di accesso</p></td>
<td style="border:1px solid black;"><p>Operazioni riuscite/Operazioni non riuscite (l'impostazione predefinita è Operazioni riuscite)</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Eventi di modifica del criterio di controllo</p></td>
<td style="border:1px solid black;"><p>Operazioni riuscite/Operazioni non riuscite (l'impostazione predefinita è Operazioni riuscite)</p></td>
</tr>  
</tbody>  
</table>
  
L'abilitazione delle impostazioni di controllo riportate nella tabella determina un incremento dei requisiti di archiviazione per il registro di protezione. È necessario verificare che i registri eventi siano impostati con dimensioni adeguate nei controller di dominio. Le dimensioni predefinite del registro eventi per Windows Server 2003 sono appropriate, mentre in Windows 2000 erano utilizzate dimensioni eccessivamente ridotte (queste impostazioni potrebbero ancora essere attive se è stato eseguito l'aggiornamento da Windows 2000). Nel capitolo 5, "Creazione dell'infrastruttura di protezione per LAN senza fili", è illustrato il modo in cui configurare i server IAS per la registrazione nel registro eventi di sistema Windows di tutte le connessioni riuscite e non riuscite alla rete LAN senza fili. È necessario verificare che i registri protezione e degli eventi di sistema siano impostati con dimensioni adeguate in tutti i controller di dominio. In Windows Server 2003 vengono utilizzati 16 MB per i registri di sistema e delle applicazioni, e 128 MB per il registro protezione: entrambi i valori sono appropriati a questa soluzione.
  
###### Importazione dell'oggetto Criteri di gruppo delle impostazioni di protezione
  
La procedura che segue consente di importare nel dominio le impostazioni descritte nella sezione precedente, ma non di applicarle ai server.
  
**Per installare il GPO delle impostazioni di protezione nel dominio**
  
1.  Aprire una shell comandi utilizzando il collegamento **MSS WLAN Tools**.
  
2.  Al prompt dei comandi, digitare il seguente comando per importare nel dominio il GPO denominato IAS Server Security Policies:
  
    *MSSSetup ImportSecurityGPO,* quindi premere **INVIO**.
  
###### Applicazione delle impostazioni di protezione a tutti i controller di dominio
  
In questa procedura le impostazioni di protezione vengono applicate e tutti i controller di dominio, indipendentemente dalla presenza di IAS. Non dovrebbero verificarsi effetti negativi sulle funzioni del controller di dominio o su qualsiasi altra applicazione o servizio in esecuzione poiché nell'oggetto Criteri di gruppo non sono presenti impostazioni che disabilitano funzionalità di qualsiasi tipo. Se non si desidera applicare queste impostazioni a tutti i controller di dominio, consultare la procedura successiva.
  
Per applicare le impostazioni a tutti i controller di dominio, è necessario collegare l'oggetto Criteri di gruppo all'unità organizzativa (OU) dei controller di dominio. L'oggetto Criteri di gruppo viene collegato manualmente per evitare il pericolo di sovrascrivere impostazioni già configurate nel dominio.
  
**Per applicare le impostazioni di protezione a tutti i controller di dominio**
  
1.  Dalmenu di avvio scegliere **Tutti iprogrammi**, quindi **Strumenti di amministrazione** e infine **Gestione criteri di gruppo** per avviare la **console Gestione criteri di gruppo** (GPMC, Group Policy Management Console).
  
2.  Passare all'UO **Controller di dominio** nel riquadro a sinistra e fare clic su di essa.
  
    L'unità organizzativa verrà visualizzata sotto l'oggetto di dominio.
  
3.  Fare clic con il pulsante destro del mouse sul nome dell'unità organizzativa e quindi scegliere **Link a una GPO esistente...**.
  
4.  Nell'elenco degli oggetti Criteri di gruppo fare clic su **IAS Server Security Policies**, quindi scegliere **OK** per tornare alla finestra principale di GPMC.
  
5.  Nel riquadro destro verificare che la scheda **Linked Group Policy Objects** sia selezionata, quindi fare clic sull'oggetto Criteri di gruppo **IAS Server Security Policies**.
  
6.  Fare clic sul simbolo della freccia doppia verso l'alto a sinistra dell'elenco per assegnare a questo oggetto Criteri di gruppo la massima priorità.
  
    In questo modo i servizi richiesti resteranno attivi indipendentemente dagli altri criteri di protezione applicati ai controller di dominio.
  
7.  Chiudere la **console Gestione criteri di gruppo**.
  
    Le impostazioni di protezione verranno applicate ai server in corrispondenza del successivo intervallo di aggiornamento dell'oggetto Criteri di gruppo (l'intervallo predefinito è di 5 minuti per i controller di dominio).
  
###### Applicazione delle impostazioni di protezione solo ai server IAS
  
Se non si desidera applicare le impostazioni di protezione a tutti i controller di dominio o se si è scelto di non installare IAS nei controller di dominio, è possibile creare un'unità organizzativa separata per i server IAS e quindi applicare l'oggetto Criteri di gruppo a tale unità. Se non si installa IAS sui controller di dominio, è necessario creare l'unità organizzativa dei server IAS in altre parti del dominio.
  
**Per applicare le impostazioni di protezione solo ai server IAS**
  
1.  Dalmenu di avvio scegliere **Tutti iprogrammi**, quindi **Strumenti di amministrazione** e infine **Gestione criteri di gruppo** per avviare la **console Gestione criteri di gruppo** (GPMC, Group Policy Management Console).
  
2.  Passare all'UO **Controller di dominio** nel riquadro a sinistra e fare clic su di essa.
  
    Questa unità organizzativa è posizionata al di sotto della directory principale del dominio.
  
3.  Creare una nuova OU figlio al di sotto di questa OU facendo clic con il pulsante destro del mouse sul nome **Controller di dominio** e quindi selezionando **New Organizational Unit** dal menu a comparsa.
  
4.  Quando richiesto digitare un nome per l'unità organizzativa, ad esempio, *Server IAS*.
  
5.  Fare clic con il pulsante destro del mouse sull'unità organizzativa e quindi scegliere **Link a una GPO esistente...**.
  
6.  Nell'elenco degli oggetti Criteri di gruppo selezionare **IAS Server Security Policies**, quindi scegliere **OK** per tornare alla finestra principale di GPMC.
  
7.  Chiudere la **console Gestione criteri di gruppo**.
  
8.  Spostare l'oggetto computer di ogni controller di dominio combinato e server IAS dall'unità organizzativa **Controller di dominio** alla nuova unità organizzativa figlio.
  
    Le impostazioni di protezione verranno applicate ai server in corrispondenza del successivo intervallo di aggiornamento dell'oggetto Criteri di gruppo (l'intervallo predefinito è di 5 minuti per i controller di dominio e di 90 minuti per gli altri computer).
  
    **Nota:** se si installano i server IAS in più domini, è necessario ripetere l'installazione e collegare gli oggetti Criteri di gruppo per ogni dominio nell'insieme di strutture.
  
###### Verifica delle impostazioni di protezione
  
**Per verificare che le impostazioni di protezione siano state applicate**
  
1.  Da una shell dei comandi, al prompt dei comandi digitare:
  
    *gpupdate /force*, quindi premere **INVIO**.
  
2.  Esaminare il registro eventi delle applicazioni per individuare eventi dell'origine **SceCli** (potrebbero essere necessari alcuni secondi per visualizzarlo). Dovrebbe essere registrato un evento con ID 1704. Il testo dell'evento dovrebbe essere il seguente:
  
    Applicazione del criterio di protezione agli oggetti del criterio di gruppo riuscita.
  
#### Aggiornamento della protezione dei server
  
Diversamente dalle impostazioni di protezione dell'oggetto Criteri di gruppo, è necessario controllare e applicare gli aggiornamenti della protezione su ogni server. Se il numero di server da gestire è relativamente esiguo, è possibile utilizzare procedure manuali. Se si dispone di molti server e il sistema di gestione degli aggiornamenti non è stato automatizzato, il controllo e l'applicazione manuale degli aggiornamenti su tutti i server può risultare un'operazione poco efficace. È quindi opportuno automatizzare l'applicazione degli aggiornamenti di protezione mediante Microsoft Software Update Service (SUS) o Microsoft Systems Management Server (SMS) 2003. Per ulteriori informazioni sull'uso di questi programmi per la gestione degli aggiornamenti della protezione, vedere *Microsoft Guide to Security Patch Management* (in inglese).
  
##### Verifica dell'aggiornamento costante della protezione
  
Per verificare che la protezione del server sia sempre aggiornata è possibile utilizzare due soluzioni: Windows Update e MBSA. Sono inoltre disponibili alcuni strumenti di altri fornitori che svolgono funzioni simili.
  
###### Windows Update
  
Windows Update è un servizio in linea progettato principalmente per le piccole imprese e i privati, anche se non esistono limitazioni all'uso di questo servizio. Poiché Windows Update richiede una connessione attiva a Internet, non è consigliabile utilizzare questo servizio senza aver protetto il server con un firewall.
  
Per ulteriori informazioni su Windows Update, vedere i riferimenti alla file di questo capitolo.
  
###### Microsoft Baseline Security Analyzer
  
MBSA è uno strumento di valutazione della protezione che esamina i sistemi per verificare numerosi aspetti legati alla protezione, tra cui la mancanza di alcuni aggiornamenti. Per ulteriori informazioni su MBSA, vedere i riferimenti alla file di questo capitolo.
  
**Per controllare gli aggiornamenti della protezione installati mediante MBSA**
  
1.  Se il server in uso non è connesso a Internet, è necessario ottenere ogni volta la versione corrente del database di protezione MBSA prima di eseguire il controllo. Si tratta di un file XML, **msecure.xml**, che può essere scaricato dall'URL fornito alla fine del presente capitolo. Copiare questo file nella cartella in cui è stato installato MBSA (la cartella predefinita è C:\\Programmi\\Microsoft Baseline Security Analyzer).
  
2.  Per verificare lo stato corrente di aggiornamento del server, al prompt dei comandi digitare:
  
    *Mbsacli /hf -v*, quindi premere **INVIO**.
  
3.  Annotare gli aggiornamenti della protezione mancanti, che verranno visualizzati come segue:
  
    \* WINDOWS SERVER 2003, STANDARD EDITION GOLD
  
    Nota MS03-030 819696
  
    Per una descrizione dettagliata, vedere l'articolo Q306460.
  
4.  È possibile ottenere ogni aggiornamento di protezione mancante utilizzando il browser per accedere all'articolo attinente della Microsoft Knowledge Base. Digitare il seguente URL nel browser:
  
    *http://support.microsoft.com/default.aspx?kbid=XXXXXX*
  
    **Nota:** è necessario sostituire XXXXXX con il numero dell'articolo della Knowledge Base elencato nei risultati di MBSA, ad esempio 819696 nel caso proposto.
  
5.  Installare ogni aggiornamento in base alle istruzioni fornite nell'articolo della Knowledge Base.
  
##### Utilizzo di MBSA per controllare altri problemi di protezione
  
Oltre a verificare la presenza degli aggiornamenti di protezione più recenti, MBSA può essere utilizzato per controllare altri potenziali problemi legati alla protezione sul server. Per questo scopo, eseguire la versione grafica dal menu di avvio, eseguire un'analisi del server e prendere provvedimenti per ogni avviso.
  
In particolare, è necessario prestare la massima attenzione se vengono rilevati eventuali account utente con password vuote, semplici o senza scadenza. In ogni caso, non modificare le impostazioni di qualunque account incorporato, come krbtgt.
  
A meno che non siano state modificate le impostazioni predefinite dell'area di protezione di Internet Explorer sui server, è possibile ignorare gli avvisi di MBSA relativi a impostazioni non standard. Le impostazioni predefinite per Windows Server 2003 sono più avanzate rispetto a quelle delle aree di Internet Explorer utilizzate da MBSA come base per il controllo.
  
La procedura descritta in questo capitolo prevede solo l'esecuzione di MBSA per l'analisi del computer locale, poiché la procedura per l'analisi dei computer in rete non rientra nell'ambito di questa guida. Per informazioni dettagliate sull'uso di MBSA, vedere il riferimento alla fine del presente capitolo.
  
##### Gestione e installazione degli aggiornamenti sui server
  
Una descrizione completa della gestione automatica costante degli aggiornamenti esula dall'ambito di questa guida. Tuttavia, è necessario sapere che esistono tre soluzioni principali per gestire gli aggiornamenti di sistema in maniera continuativa mediante la tecnologia Microsoft.
  
###### Aggiornamenti automatici
  
Aggiornamenti automatici è un servizio incorporato nei server e client Windows che consente a ogni computer di ricercare e scaricare eventuali aggiornamenti rapidi della protezione rilasciati da Microsoft. È possibile scegliere di installare automaticamente tali aggiornamenti, ma in tal caso ogni computer deve avere accesso al Web (HTTP). L'avviso formulato nella sezione relativa a Windows Update a proposito della necessità di avere un firewall di protezione per ogni dispositivo, è valido anche in questo caso.
  
Per ulteriori informazioni su Aggiornamenti automatici, vedere il riferimento alla file del presente capitolo.
  
###### Software Update Service
  
Grazie a Software Update Service (SUS), basato sul servizio Aggiornamenti automatici, non è più necessario che ogni computer sia connesso a Internet in quanto le funzionalità di controllo e download sono unite in uno o più computer centrali. L'amministratore può quindi approvare o respingere gli aggiornamenti scaricati nei server SUS. Tutti gli aggiornamenti approvati vengono recuperati da tutti gli altri computer dell'organizzazione. Tali computer utilizzano il servizio Aggiornamenti automatici per controllare e scaricare eventuali aggiornamenti dai server SUS anziché dal sito Windows Update.
  
Per informazioni sul modo in cui distribuire SUS, vedere *Gestione di patch mediante Microsoft Software Update Services (SUS)*. L'URL per ottenere questo documento è fornito alla fine del presente capitolo.
  
###### Gestione degli aggiornamenti con Microsoft Systems Management Server
  
Microsoft SMS 2003 consente di automatizzare completamente la distribuzione dei service pack, degli aggiornamenti della protezione e degli aggiornamenti software. Se si utilizza SMS 2000 con Software Update Services Feature Pack, le funzionalità di SUS vengono integrate con le maggiori capacità di SMS. Sia SMS 2000 che SMS 2003 includono la possibilità di pianificare le analisi tramite MBSA dei computer dell'organizzazione. Per ulteriori informazioni sull'utilizzo di SMS, vedere i seguenti documenti:
  
-   *Gestione delle patch mediante Microsoft Systems Management Server 2003*
  
-   *Gestione delle patch mediante Microsoft Systems Management Server 2.0*
  
Gli URL per ottenere questi documenti sono forniti alla fine del presente capitolo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo capitolo viene descritto come predisporre la rete, Active Directory, i controller di dominio e altri elementi dell'ambiente in uso per l'installazione di un'infrastruttura LAN senza fili protetta. Gli script utilizzati per configurare questa soluzione sono stati installati con numerosi strumenti di supporto. I gruppi di protezione utilizzati da questa soluzione sono stati creati nel dominio e le impostazioni di protezione sono state importate e applicate ai server. Infine, l'attualità degli aggiornamenti di protezione sui server è stata esaminata e, se necessario, rivista.
  
Il capitolo successivo è dedicato all'installazione di Servizi certificati sul primo server installato per creare la CA di rete.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riferimenti
  
Questa sezione contiene rimandi a informazioni supplementari importanti e ad altro materiale attinente al contenuto di questo capitolo.
  
-   Il capitolo "Deploying Wireless LANs" di Windows Server 2003 Deployment Kit, è disponibile al seguente URL:
  
    [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    proddocs/deployguide/DNSBM\_WIR\_OVERVIEW.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/deployguide/dnsbm_wir_overview.mspx) (in inglese).
  
-   Per informazioni sui livelli funzionali del dominio Active Directory e istruzioni sul modo in cui passare da un livello all'altro, vedere le seguenti sezioni della documentazione relativa a Windows Server 2003 disponibile negli URL indicati.
  
    -   In questa sezione sono descritti i diversi livelli del dominio e dell'insieme di strutture:
  
        [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
        proddocs/standard/sag\_levels.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/standard/sag_levels.mspx) (in inglese)
  
    -   In questa sezione sono descritte le modalità di modifica del livello del dominio e dell'insieme di strutture:
  
        [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
        proddocs/standard/sag\_changedomlevel.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/standard/sag_changedomlevel.mspx) (in inglese)
  
-   Per informazioni dettagliate sull'aggiornamento di uno schema Active Directory da Windows 2000 a Windows Server 2003, vedere la pagina della documentazione ADPrep disponibile al seguente URL:
  
    [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    proddocs/standard/adprep.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/standard/adprep.mspx) (in inglese)
  
-   Per informazioni dettagliate sul download e l'utilizzo di Group Policy Management Console, vedere il seguente URL:
  
    [http://go.microsoft.com/fwlink/?LinkId=8630](http://go.microsoft.com/fwlink/?linkid=8630) (in inglese).
  
-   Per scaricare la versione 2.0.0.3 di CAPICOM, vedere il seguente URL:
  
    [http://www.microsoft.com/downloads/details.aspx?  
    displaylang=en&FamilyID=860EE43A-A843-462F-ABB5-FF88EA5896F6](http://www.microsoft.com/downloads/details.aspx?displaylang=en&familyid=860ee43a-a843-462f-abb5-ff88ea5896f6) (in inglese).
  
    In ogni caso, è consigliabile ricercare "CAPICOM" nel seguente URL per accertarsi di individuare la versione più recente:
  
    <http://www.microsoft.com/downloads> (in inglese).
  
-   Per istruzioni sul download e l'utilizzo di MBSA (Microsoft Baseline Security Analyzer), vedere il seguente URL:
  
    <http://www.microsoft.com/technet/security/tools/tools/mbsahome.mspx> (in inglese).
  
-   La Guida per la protezione di Windows Server 2003 è disponibile al seguente URL:
  
    [http://go.microsoft.com/fwlink/?LinkId=14845](http://go.microsoft.com/fwlink/?linkid=14845)
  
-   Per Windows Update, vedere il seguente URL:
  
    <http://v4.windowsupdate.microsoft.com/it/default.asp>
  
-   Per ulteriori informazioni sull'utilizzo di Aggiornamenti automatici, leggere l'articolo disponibile al seguente URL:
  
    [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    proddocs/standard/autoupdate\_top.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/standard/autoupdate_top.mspx) (in inglese).
  
-   Per le pagine relative alla gestione delle patch, agli aggiornamenti della protezione e ai download, vedere il seguente URL:
  
    <http://technet.microsoft.com/it-it/library/dd547309.aspx>.
  
-   L'URL segnalato sopra fornisce collegamenti alle seguenti documentazioni e ad altre guide attinenti:
  
    -   Gestione di patch mediante Microsoft Software Update Services (SUS)
  
    -   Gestione delle patch mediante Microsoft Systems Management Server 2003
  
    -   Gestione delle patch mediante Microsoft Systems Management Server 2.0
  
**Scarica la soluzione completa**
  
[Protezione delle reti LAN senza fili con PEAP e password](http://go.microsoft.com/fwlink/?linkid=23481)
  
[](#mainsection)[Inizio pagina](#mainsection)
