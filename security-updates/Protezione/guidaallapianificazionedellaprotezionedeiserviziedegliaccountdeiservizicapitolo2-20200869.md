---
TOCTitle: 'Guida alla pianificazione della protezione dei servizi e degli account dei servizi - Capitolo 2'
Title: 'Guida alla pianificazione della protezione dei servizi e degli account dei servizi - Capitolo 2'
ms:assetid: 'c5262521-a6a5-499c-89bb-4fa3f333e886'
ms:contentKeyID: 20200869
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536270(v=TechNet.10)'
---

Guida alla pianificazione della protezione dei servizi e degli account dei servizi
==================================================================================

### Capitolo 2 - Strategie per l'esecuzione protetta dei servizi

Aggiornato: 31 maggio 2005

In questo capitolo vengono fornite informazioni dettagliate sui rischi interni derivanti dall'esecuzione dei servizi e vengono illustrati i tipi di account utilizzati per l'esecuzione dei servizi. Vengono inoltre descritti i principi e le strategie da applicare per consentire l'esecuzione protetta dei servizi.

##### In questa pagina

[](#eeaa)[Vulnerabilità dei servizi](#eeaa)
[](#edaa)[Account di sistema](#edaa)
[](#ecaa)[Account utente](#ecaa)
[](#ebaa)[Modifiche alle impostazioni di protezione predefinite dei servizi in Windows Server 2003](#ebaa)
[](#eaaa)[Principi per l'esecuzione protetta dei servizi](#eaaa)

### Vulnerabilità dei servizi

Poiché vengono eseguiti automaticamente all'avvio, i servizi risultano particolarmente adatti per le applicazioni di tipo server, ad esempio i servizi Web. Questa caratteristica comporta tuttavia alcuni svantaggi, poiché l'utente potrebbe non essere consapevole dell'esecuzione di un determinato servizio. Sebbene per alcuni servizi venga visualizzata una finestra di dialogo, in genere non è prevista alcuna interazione con l'utente. È quindi possibile che alcuni servizi predefiniti vengano eseguiti senza che l'utente sia a conoscenza degli eventuali rischi di protezione. I più recenti worm, ad esempio Nimda, sfruttano il fatto che sia possibile eseguire server Web sulle workstation degli utenti senza che questi ne siano a conoscenza. Le workstation infette diffondono quindi il worm a migliaia di computer attraverso Internet.

Alcuni servizi, in particolare quelli utilizzati da strumenti di gestione aziendali quali Microsoft® Systems Management Server, Microsoft Operations Manager e Tivoli, richiedono che per l'accesso al sistema venga utilizzato un account utente di dominio. Questi servizi, infatti, in genere richiedono l'accesso all'intero dominio ed eventualmente anche ad altri domini trusted. In altri scenari, l'utilizzo di un account utente di dominio per l'esecuzione dei servizi era visto come una pratica normale. Di recente, tuttavia, le organizzazioni hanno iniziato a considerarla come un rischio per la protezione.

Le informazioni relative al nome utente e alla password di ciascun servizio che utilizza un account utente locale o di dominio vengono memorizzate nel Registro di sistema e possono quindi essere utilizzate da un utente malintenzionato che riesce a ottenere l'accesso amministrativo al computer. Di conseguenza, la configurazione di un servizio per l'accesso come utente determina sempre un'esposizione del sistema a possibili rischi di protezione.

Poiché si crea un'esposizione ogni volta che un servizio viene configurato per l'accesso al sistema mediante un account utente di dominio, la probabilità di sfruttamento di questa vulnerabilità dipende da numerosi fattori, tra cui:

-   **Numero di server su cui un determinato account utente di dominio è configurato per l'esecuzione dei servizi**. In un ambiente server gestito correttamente, tutti i server dovrebbero essere protetti allo stesso modo. In caso contrario, il rischio di vulnerabilità aumenterà proporzionalmente al numero di server scarsamente protetti. Maggiore è il numero di server sui quali è in esecuzione il servizio con dominio autenticato, maggiori saranno le possibilità per gli utenti malintenzionati di sfruttare la vulnerabilità di protezione. Si supponga, ad esempio, che un servizio utilizzi lo stesso account di dominio per autenticare se stesso su centinaia o migliaia di server all'interno di un'organizzazione. In questo caso, se riesce a compromettere uno di questi server e a ottenere il nome utente e la password utilizzati dal servizio, un utente malintenzionato avrà anche accesso a tutti gli altri server sui quali è in esecuzione il servizio.

-   **Ambito dei privilegi di rete per qualsiasi account utente di dominio configurato per l'esecuzione di un servizio**. L'estensione dell'ambito dei privilegi è direttamente proporzionale al numero delle risorse soggette a rischi di protezione. Gli account Administrator del dominio sono esposti a un rischio elevato, poiché l'ambito della vulnerabilità per la rete è rappresentato da tutti i computer che risiedono nel dominio, inclusi i controller di dominio. Se inoltre l'account utente di dominio dispone dei privilegi di amministratore locale su uno o più server, esiste il rischio che la vulnerabilità di protezione venga sfruttata più volte.

    È essenziale proteggere soprattutto le risorse di rete a cui accedono gli account a livello di amministratore, poiché le credenziali di amministratore di dominio creano vulnerabilità transitive e possibilità di escalation nell'ambito dell'intero dominio. Queste credenziali vengono in genere utilizzate per l'accesso remoto o interattivo su tutti i computer del dominio. L'eventuale compromissione di queste credenziali rende quindi tutti i computer del dominio vulnerabili agli attacchi.

#### Scenari di vulnerabilità dei servizi

Nella figura e nella tabella riportate di seguito vengono illustrati alcuni scenari differenti di vulnerabilità dei servizi, ciascuno caratterizzato da un diverso livello di rischio per la protezione. Si presuppone che tutti gli account riportati nella figura siano account di dominio e che ciascun account stia eseguendo almeno un servizio su uno dei server.

Di seguito viene riportata la descrizione degli account di dominio nel diagramma:

-   Account A dispone dei privilegi di amministratore su uno o più controller di dominio.

-   Gli account A, B, C e D dispongono dei privilegi di amministratore su più server membri.

-   Account E dispone dei privilegi di amministratore su un unico server membro.

    [![](images/Dd536270.PGFG0201(it-it,TechNet.10).jpg)](https://technet.microsoft.com/it-it/dd536270.pgfg0201_big(it-it,technet.10).gif)

    **Figura 2.1. Privilegi degli account amministratore su server e controller di dominio**

##### Livelli di priorità delle vulnerabilità di protezione

Di seguito sono elencati i livelli di priorità utilizzati nella seguente tabella:

-   **Livello di rischio Critico**. Questo scenario indica un pericolo immediato per la protezione dell'organizzazione.

-   **Livello di rischio Alto**. Questo scenario compromette la protezione dell'organizzazione ma non indica un pericolo immediato.

-   **Livello di rischio Medio**. Questo scenario riveste una certa importanza, ma l'esposizione non coinvolge un server con livello di protezione alto.

-   **Livello di rischio Basso**. L'eliminazione di questo scenario ha un impatto minimo sugli obiettivi di protezione.

Nella seguente tabella viene fornita una descrizione dettagliata degli scenari di vulnerabilità dei servizi, con i relativi livelli di priorità.

**Tabella 2.1. Scenari di vulnerabilità della protezione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario</th>
<th>Descrizione</th>
<th>Livello di rischio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>1</strong></td>
<td style="border:1px solid black;">Account A sta eseguendo un servizio su Server 1. Una volta individuata la password di Account A su Server 1, l'utente ha accesso a DC 1, che diventa quindi vulnerabile. Questo è uno scenario con priorità<em>critica</em> . Non utilizzare account di dominio con privilegi di amministratore su un controller di dominio per l'esecuzione dei servizi su un server membro.</td>
<td style="border:1px solid black;"><strong>Critico</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>2</strong></td>
<td style="border:1px solid black;">Account B sta eseguendo un servizio su Server 2 e ha inoltre accesso a Server 1, dove Account A sta eseguendo un servizio. Una volta individuata la password di Account B su Server 2, l'utente raggiunge la stessa situazione iniziale dello scenario 1, quindi DC 1 diventa vulnerabile. È possibile estendere questa logica al caso in cui Account C sta eseguendo un servizio su Server 3, che a sua volta può accedere a Server 2, dove Account B sta eseguendo un servizio, e così via. Questo è uno scenario con priorità<em>alta</em> ma non critica. Una volta risolto il problema dello scenario 1, infatti, quello dello scenario 2 viene circoscritto ai soli server membri.</td>
<td style="border:1px solid black;"><strong>Alto</strong></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>3</strong></td>
<td style="border:1px solid black;">Account D sta eseguendo un servizio su Server 4 o Server 5. Una volta individuata la password di Account D sul server, l'utente ha accesso a tutti i server membri di cui Account D dispone dei privilegi. Questo è uno scenario con priorità<em>media</em> (non esiste la caratteristica di transitività dello scenario 2).</td>
<td style="border:1px solid black;"><strong>Medio</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>4</strong></td>
<td style="border:1px solid black;">Account E sta eseguendo un servizio su Server 5 e ha accesso soltanto a tale server.</td>
<td style="border:1px solid black;"><strong>Basso</strong></td>
</tr>
</tbody>
</table>
  
#### Riepilogo delle vulnerabilità dei servizi
  
I servizi costituiscono i principali punti di vulnerabilità per gli utenti malintenzionati che tentano di accedere al server locale o agli altri server della rete. Se non è necessario utilizzare un determinato servizio, si consiglia di disattivarlo. In questo modo, è possibile restringere in modo semplice e rapido la superficie di attacco nonché ottenere vantaggi significativi a livello di prestazioni.
  
Per proteggere in modo adeguato l'esecuzione di un servizio, è necessario conoscere le vulnerabilità del servizio e cercare di ridurre al minimo la relativa esposizione agli attacchi.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Account di sistema
  
Per poter accedere alle risorse e agli oggetti del sistema operativo, un servizio deve accedere al sistema come account. Se si assegna a un servizio un account che non dispone delle autorizzazioni appropriate per l'accesso, lo snap-in Servizi di Microsoft Management Console (MMC) concede automaticamente a tale account il diritto utente di accesso come servizio al computer gestito. In Microsoft Windows Server™ 2003 sono inclusi tre account locali predefinit, che vengono utilizzati come account di accesso per alcuni servizi di sistema:
  
-   **Account di sistema locale**
  
    Si tratta dell'account locale predefinito che consente di avviare un servizio e fornire il contesto di protezione per tale servizio. Questo account dispone dell'accesso completo al computer, incluso il servizio directory quando viene utilizzato per i servizi in esecuzione sui controller di dominio. Funge da account computer host sulla rete e ha quindi accesso alle risorse di rete come qualsiasi altro account di dominio. Sulla rete questo account è indicato come DOMAIN\\&lt;*nome computer*&gt;$. Se un servizio accede al sistema utilizzando l'account di sistema locale in un controller di dominio, il servizio disporrà dell'accesso di sistema locale sul controller di dominio stesso. In caso di compromissione del controller di dominio, un utente malintenzionato avrà quindi la possibilità di apportare qualsiasi modifica all'interno del dominio. Per impostazione predefinita, in Windows Server 2003 alcuni servizi sono configurati per l'accesso con l'account di sistema locale. Il nome effettivo dell'account è NT AUTHORITY\\System e a tale account non è associata alcuna password che deve essere gestita da un amministratore.
  
-   **Account del servizio locale**
  
    Si tratta di un account predefinito speciale che dispone di privilegi ridotti, simile a un account utente locale autenticato. Questo tipo di accesso limitato consente di proteggere il computer in caso di compromissione di singoli servizi o processi da parte di un utente malintenzionato. Un servizio eseguito con l'account del servizio locale accede alle risorse di rete come sessione Null, ovvero utilizzando credenziali anonime. Il nome effettivo dell'account è NT AUTHORITY\\LocalService e a tale account non è associata alcuna password che deve essere gestita da un amministratore.
  
-   **Account del servizio di rete**
  
    Si tratta di un account predefinito speciale che dispone di privilegi ridotti, simile a un account utente autenticato. Questo tipo di accesso limitato consente di proteggere il computer in caso di compromissione di singoli servizi o processi da parte di un utente malintenzionato. Un servizio eseguito con l'account del servizio di rete accede alle risorse di rete utilizzando le credenziali dell'account computer, in modo analogo al servizio di sistema locale. Il nome effettivo dell'account è NT AUTHORITY\\NetworkService e a tale account non è associata alcuna password che deve essere gestita da un amministratore.
  
    **Importante:** la modifica delle impostazioni predefinite potrebbe impedire il corretto funzionamento di alcuni servizi importanti. È necessario prestare particolare attenzione quando si modificano le impostazioni **Tipo di avvio** e **Connessione** dei servizi configurati per l'avvio automatico per impostazione predefinita.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Account utente
  
Alcune categorie di account utente possono accedere come servizio. Ciascuna categoria dispone di funzionalità e privilegi specifici:
  
-   **Account utente locali**
  
    Questa categoria include gli account creati su un computer locale, ad esempio attraverso la console di gestione Utenti e gruppi locali. Questi account dispongono di privilegi molto limitati sul computer locale, a meno che non ricevano specificatamente privilegi più elevati o non vengano aggiunti a gruppi che dispongono già di tali privilegi.
  
-   **Account amministratore locale**
  
    Questa categoria include l'account Administrator predefinito che viene creato e utilizzato al momento della prima installazione di Windows Server 2003 o Microsoft Windows® XP nel computer, nonché eventuali altri account utente creati successivamente e aggiunti al gruppo Administrators predefinito. I membri di questo gruppo hanno accesso completo e senza restrizioni al computer locale.
  
-   **Account utente di dominio**
  
    Questa categoria include gli account che vengono creati nel dominio, ad esempio utilizzando la console di gestione Utenti e computer di Active Directory®. Questi account dispongono di privilegi limitati nel dominio, a meno che non ricevano specificatamente privilegi più elevati o non vengano aggiunti a gruppi che dispongono già di tali privilegi.
  
-   **Account Administrator del dominio**
  
    Questa categoria include l'account Administrator del dominio predefinito, che viene creato e utilizzato al momento della prima installazione di Active Directory, nonché eventuali altri account utente creati successivamente e aggiunti al gruppo Administrators locale predefinito oppure ai gruppi Domain Admins o Enterprise Admins. I membri di questi gruppi hanno accesso completo e senza restrizioni al dominio e, nel caso del gruppo Enterprise Admins, all'intero insieme di strutture.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Modifiche alle impostazioni di protezione predefinite dei servizi in Windows Server 2003
  
Per impostazione predefinita, nelle versioni di Windows precedenti a Windows XP e Windows Server 2003 quasi tutti i servizi forniti con il sistema operativo utilizzano l'account di sistema locale. I programmi eseguiti in questo contesto hanno privilegi illimitati sul computer locale, con conseguenti rischi di protezione. Con il rilascio di Windows Server 2003, gli sviluppatori hanno modificato le impostazioni predefinite allo scopo di aumentare la protezione dell'ambiente. Una delle modifiche introdotte riguarda la riduzione del numero dei servizi che vengono eseguiti con l'account di sistema locale per impostazione predefinita. Anziché utilizzare questo account, molti servizi comuni adesso utilizzano l'account del servizio locale o del servizio di rete. Questi account hanno un livello di privilegio molto più basso rispetto all'account di sistema locale e rappresentano quindi una minaccia meno grave per la protezione del sistema.
  
Molti servizi, tra cui Aggiornamenti automatici, Browser di computer, Messenger e Windows Installer, continuano ad accedere come account del sistema locale, mentre altri utilizzano account differenti. Il servizio Avvisi, ad esempio, utilizza l'account di sistema locale in Windows 2000 e l'account del servizio locale in Windows Server 2003. Il servizio Client DNS utilizza l'account di sistema locale in Windows 2000 e l'account del servizio di rete in Windows Server 2003. Nella seguente tabella sono elencati i servizi che non utilizzano più l'account di sistema locale in Windows Server 2003 e viene inoltre indicato l'account del servizio attualmente utilizzato.
  
**Attenzione:** non tentare di modificare gli account utilizzati dai servizi forniti con Windows Server 2003. Questa operazione potrebbe infatti causare gravi problemi e compromettere potenzialmente la corretta esecuzione di servizi importanti. Il servizio Client DNS, ad esempio, utilizza l'account del servizio di rete poiché deve accedere ad alcune risorse di rete, tra cui i server DNS. Questo servizio non funziona correttamente con l'account del servizio locale né con qualsiasi altro account che non è in grado di effettuare l'autenticazione nell'ambito delle risorse di rete.
  
**Tabella 2.2. Nuove impostazioni degli account dei servizi in Windows Server 2003**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome del servizio</th>
<th>Connessione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Avvisi</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Servizio Gateway di livello applicazione</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Registro di sistema remoto</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Smart card</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Helper NetBIOS di TCP/IP</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Telnet</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Gruppo di continuità</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">WebClient</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Acquisizione di immagini di Windows (WIA)</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Ora di Windows</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Servizio rilevamento automatico proxy WinHTTP</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Client DHCP</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Distributed Transaction Coordinator</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Client DNS</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Registrazione licenze</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Avvisi e registri di prestazioni</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">RPC Locator</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Principi per l'esecuzione protetta dei servizi
  
Per creare una strategia adeguata in grado di garantire la protezione dei servizi, è necessario comprendere la natura dei servizi disponibili nell'ambiente di rete e stabilire procedure adeguate per proteggere l'utilizzo di tali servizi. In questa sezione vengono illustrati i tre principi fondamentali per una corretta pianificazione dell'esecuzione protetta dei servizi.
  
-   Conoscenza del sistema
  
-   Utilizzo del principio del privilegio minimo
  
-   Utilizzo del principio del servizio minimo
  
L'integrazione di questi principi all'interno delle procedure di protezione IT consente di ottenere un livello appropriato di protezione dei servizi.
  
#### Conoscenza del sistema
  
Sebbene possa sembrare una raccomandazione ovvia, molte organizzazioni non hanno la visione completa dei ruoli e dei servizi eseguiti su tutti i computer dell'organizzazione.
  
Per sapere se i computer sono protetti o meno, è necessario conoscere i servizi in esecuzione sui computer e le relative proprietà. Per disporre di queste informazioni, fondamentali per la protezione dei server, può essere utile creare una tabella in cui sono elencati i servizi in esecuzione sui computer e le impostazioni delle relative proprietà, in modo da poter valutare immediatamente i possibili rischi. Sebbene possa richiedere inizialmente un notevole impegno, la creazione di questa tabella è estremamente importante per comprendere le proprietà di una *configurazione valida* per i diversi ruoli server.
  
Di seguito sono indicate alcune utilità che possono essere utilizzate per creare un elenco dei servizi in esecuzione con le relative proprietà:
  
-   **Controller servizi (sc.exe)**. Questa utilità da riga di comando, inclusa in Windows Server 2003 e Windows XP, consente di comunicare con il componente Gestione controllo servizi dalla riga di comando per individuare e impostare le proprietà dei servizi.
  
-   **Strumentazione gestione Windows (WMI)**. Questo componente preinstallato in Windows Server 2003 e Windows XP fornisce informazioni di gestione e funzionalità di controllo per gli ambienti aziendali. Grazie all'utilizzo degli standard del settore, gli amministratori dei sistemi possono utilizzare WMI per individuare e impostare le informazioni su computer desktop, applicazioni, reti e altri componenti dell'organizzazione. Numerosi strumenti di gestione, ad esempio System Information e il componente Relazioni di dipendenza della console Servizi, sono compatibili con la tecnologia WMI. Le dipendenze servizio individuano i servizi da cui dipende il servizio corrente e quelli che dipendono dal servizio corrente. Gli amministratori di sistema possono inoltre utilizzare script WMI per automatizzare le attività di amministrazione.
  
-   **Strumentazione gestione Windows da riga di comando (WMIC)**. In WMI è inclusa l'utilità da riga di comando WMIC, che fornisce una semplice interfaccia da riga di comando per WMI che può essere utilizzata per l'esecuzione di query e la gestione remota dei computer su cui sono in esecuzione sistemi operativi Windows. Per richiamare WMIC è sufficiente digitare **wmic** al prompt dei comandi. Ad esempio, per visualizzare informazioni sui servizi per un server denominato Server1, digitare quanto segue:
  
    **wmic /output:c:\\servizi.htm /node:server1 service list full / format:htable**
  
    Utilizzare Microsoft Internet Explorer per visualizzare il file c:\\servizi.htm risultante, in formato di tabella HTML (Hypertext Markup Language). Se il nome del server contiene spazi o caratteri speciali, racchiudere il nome tra virgolette quando si esegue il comando **wmic** .
  
    **Nota:** è disponibile anche un'altra utilità da riga di comando, **sclist.exe**, inclusa in Windows 2000 Server Resource Kit. Questo strumento consente di visualizzare i servizi attualmente in esecuzione, quelli sospesi oppure tutti i servizi, sia su computer locali che remoti. Sclist.exe è in grado di individuare i servizi in esecuzione su un computer remoto o su un computer senza monitor, ad esempio installato in un rack di server.
  
#### Utilizzo del principio del privilegio minimo
  
Nella maggior parte della documentazione e dei corsi di formazione sulla protezione viene illustrata l'importanza dell'applicazione del principio del privilegio minimo. Si tratta di un principio semplice la cui implementazione consente tuttavia di aumentare significativamente la protezione del sistema, riducendo al tempo stesso i possibili rischi di attacco. Secondo questo principio, a un'entità deve essere assegnato il livello minimo di accesso necessario per lo svolgimento della propria funzione. In Windows Server 2003 questo principio si applica sia agli account utente che agli account computer, poiché in Active Directory entrambi questi account rappresentano identità di protezione, ovvero account a cui è possibile assegnare autorizzazioni e privilegi.
  
Questo principio risulta particolarmente utile poiché obbliga l'utente a eseguire una valutazione delle risorse di rete e dei potenziali rischi di protezione. L'utente deve conoscere i privilegi di accesso effettivamente necessari per un determinato computer o utente e quindi verificare che vengano applicati soltanto i privilegi necessari.
  
L'esecuzione protetta dei servizi richiede che la distribuzione dei servizi nelle organizzazioni sia effettuata utilizzando un approccio basato sul privilegio minimo. Se possibile, è preferibile eseguire i servizi con l'account del servizio locale. In questo modo, l'account potrà ottenere l'accesso soltanto a un singolo computer e non all'intero dominio. I servizi che richiedono un accesso autenticato alla rete potrebbero dover utilizzare l'account del servizio di rete, mentre l'account di sistema locale deve essere utilizzato per la distribuzione dei servizi che richiedono un'implementazione più ampia. Se per la distribuzione di un servizio è necessario un account amministratore a livello di dominio, il server utilizzato per la distribuzione deve essere considerato un *server con livello di protezione alto* e deve essere protetto con le stesse misure utilizzate per le altre risorse di rete critiche, ad esempio i controller di dominio. Per ulteriori informazioni su questo argomento, vedere la sezione "Creazione di un gruppo di server con livello di protezione alto per le eccezioni di amministratore del dominio" nel Capitolo 3: "Esecuzione protetta dei servizi".
  
Microsoft ha sottoposto Windows Server 2003 a una serie di test approfonditi per assicurare che i servizi fondamentali del sistema operativo vengano eseguiti già con l'account con privilegi minimi. In genere, quindi, non dovrebbe essere necessario modificare questi servizi. Occorre invece concentrare la propria attenzione sulla protezione dei servizi che non sono inclusi nel sistema operativo, ad esempio quelli forniti come componenti di altri prodotti server, tra cui Microsoft SQL Server™, Microsoft Operations Manager e i servizi forniti da produttori di software di terze parti.
  
In Windows Server 2003 è possibile utilizzare Criteri di gruppo per controllare determinati servizi che possono essere eseguiti su uno o più computer. A questo scopo, aprire l'oggetto Criteri di gruppo per l'unità organizzativa contenente il computer che si desidera configurare, selezionare il nodo **Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Servizi sistema** e aprire la pagina **Proprietà** relativa al servizio che si desidera controllare. Nella finestra di dialogo **Proprietà** definire la modalità di avvio servizio (**Automatica**, **Manuale**o **Disabilitata**), quindi impostare le autorizzazioni di protezione che controllano gli account utente che possono eseguire determinate operazioni su tale servizio, ad esempio l'avvio o l'arresto.
  
Per ulteriori informazioni sugli aspetti da prendere in considerazione per l'individuazione del tipo di account più appropriato per l'esecuzione di un servizio, vedere la Figura 3.1 "Distribuzione dei servizi mediante la gerarchia basata sul privilegio minimo" nel Capitolo 3: "Esecuzione protetta dei servizi".
  
Una volta implementato sui vari computer, il principio del privilegio minimo viene utilizzato insieme alla regola di *conoscenza del sistema*. Per determinare se sui computer è in esecuzione il numero minimo di servizi è infatti necessario conoscere quali sono i servizi effettivamente in esecuzione. Combinando questi due principi, il personale amministrativo è in grado di individuare i servizi in esecuzione su un determinato computer, il relativo stato e le credenziali in uso per ciascun server. A questo punto, sarà possibile definire una procedura di modifica sistematica per assegnare a ciascun servizio il livello di privilegio minimo necessario. È inoltre necessario monitorare i computer per assicurarsi che non sia possibile aggiungere nuovi servizi senza utilizzare le procedure appropriate di controllo delle modifiche.
  
#### Utilizzo del principio del servizio minimo
  
In base al principio del servizio minimo, il sistema operativo e i protocolli di rete disponibili su una qualsiasi periferica di rete devono eseguire soltanto i servizi e i protocolli strettamente necessari per il raggiungimento degli obiettivi dell'organizzazione. Se ad esempio un server non deve ospitare eventuali applicazioni Web, è necessario rimuovere o disattivare il servizio Web. Nella configurazione predefinita, la maggior parte dei sistemi operativi e dei programmi prevede l'installazione di un numero di servizi e protocolli molto maggiore rispetto a quello effettivamente richiesto per i normali scenari di utilizzo.
  
In una procedura ottimale per la configurazione di un nuovo server deve essere incluso un passaggio in cui l'amministratore di sistema arresta tutti servizi non indispensabili per il corretto funzionamento del sistema operativo. Nei sistemi operativi Windows precedenti a Windows Server 2003, ad esempio, in genere è preferibile arrestare i servizi Avvisi e Messenger. È inoltre necessario verificare la corretta posizione dei servizi sulla rete. Ad esempio, si dovrebbe evitare di posizionare Routing e Accesso remoto o Internet Information Services (IIS) in un controller di dominio poiché questi componenti eseguono servizi in background che possono aumentare la vulnerabilità sul controller di dominio. Si consiglia di eseguire su un controller di dominio soltanto i servizi necessari per il corretto funzionamento del controller di dominio.
  
Per ulteriori informazioni sulla protezione dei servizi in Windows Server 2003 e Windows XP, vedere le seguenti guide:
  
-   [*Introduzione alla protezione di Windows 2003*](http://technet.microsoft.com/it-it/library/cc163140.aspx) all'indirizzo http://go.microsoft.com/fwlink/?linkid=14845
  
-   [*Guida per la protezione di Windows XP*](http://technet.microsoft.com/it-it/library/cc163061.aspx) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14839
  
-   [*Guida su Pericoli e contromisure*](http://technet.microsoft.com/it-it/library/dd162275.aspx) all'indirizzo http://go.microsoft.com/fwlink/?linkid=15159
  
##### Download
  
[![](images/Dd536270.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione della protezione dei servizi e degli account dei servizi](http://go.microsoft.com/fwlink/?linkid=41312)
  
[](#mainsection)[Inizio pagina](#mainsection)
