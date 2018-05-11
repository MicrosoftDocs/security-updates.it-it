---
TOCTitle: 'Capitolo 11: Ulteriori contromisure'
Title: 'Capitolo 11: Ulteriori contromisure'
ms:assetid: '4d1e0402-944f-4b97-a885-5d6c503f09a8'
ms:contentKeyID: 20200882
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536283(v=TechNet.10)'
---

Pericoli e contromisure
=======================

### Capitolo 11: Ulteriori contromisure

Questo capitolo descrive come implementare alcune contromisure aggiuntive, come la protezione degli account. Questo capitolo fornisce, inoltre informazioni di carattere generale, riferimenti e una guida per la configurazione all'uso dei filtri IPsec (IP Security) come contromisura efficace contro gli attacchi alla rete.

##### In questa pagina

[](#ecaa)[Procedure per la protezione avanzata dei server membri](#ecaa)  
[](#ebaa)[Configurazione di Windows Firewall](#ebaa)  
[](#eaaa)[Ulteriori informazioni](#eaaa)  

### Procedure per la protezione avanzata dei server membri

Sebbene sia possibile applicare la maggior parte delle contromisure trattate in questa guida mediante Criteri di gruppo, sono disponibili altre impostazioni la cui applicazione tramite Criteri di gruppo è molto difficile, se non impossibile. Le sezioni successive offrono istruzioni su come implementare queste impostazioni per i server membri del dominio.

#### Protezione degli account

Microsoft Windows Server 2003 con Service Pack 1 (SP1) dispone di una serie di account utente incorporati che non possono essere eliminati, ma che possono essere rinominati. Due degli account predefiniti più noti di Windows Server 2003 sono Guest e Amministratore.

##### Vulnerabilità

Per impostazione predefinita, l'account Guest è disabilitato nei server membri e nei controller di dominio. Questa impostazione non deve essere modificata. Molte varianti di codice nocivo utilizzano l'account predefinito Administrator nel primo tentativo di attacco a un server. È necessario rinominare l'account Administrator incorporato e modificarne la descrizione per evitare la compromissione dei server remoti da parte di pirati informatici che cercano di usare questo account molto noto.

Negli ultimi anni il valore della modifica di questa configurazione è diminuito, a seguito della comparsa di strumenti di attacco che cercano di penetrare nel server specificando l'ID di protezione dell'account Amministratore incorporato, per scoprirne il vero nome e quindi penetrare nel server. Il SID è il valore che identifica in modo univoco un utente, un gruppo, un account di computer e una sessione di accesso in una rete. Non è possibile modificare il SID di questo account incorporato.

##### Contromisura

Rinominare l’account Administrator e modificare la relativa password impostando un valore lungo e complesso in tutti i server.

**Nota**: per rinominare l’account Amministratore incorporato è possibile utilizzare Criteri di gruppo. I criteri di base descritti nella *Guida per la protezione di* *Windows* *Server* 2003 non implementano questa impostazione, perché ogni organizzazione dovrebbe scegliere un nome univoco per questo account. Per rinominare l'account, configurare l'impostazione **Rinomina account amministratore** di Criteri di gruppo in:
**Configurazione computer\\Impostazioni Windows\\Impostazioni di protezione\\Criteri locali\\**
**Protezione\\Opzioni**
In teoria, le organizzazioni dovrebbero utilizzare password diverse per ciascun server, tuttavia, una configurazione di questo tipo comporta un significativo carico gestionale. Tuttavia, si sottolinea che se si utilizzano gli stessi nomi account e password in tutti i server, un pirata informatico che riuscisse ad accedere a un server membro potrebbe accedere a tutti gli altri. Annotare qualsiasi modifica effettuata in un luogo sicuro.

##### Impatto potenziale

Gli utenti che gestiscono i computer, devono tenere traccia del nome account assegnato a ogni computer. Gli utenti che devono accedere a un determinato server con l’account Administrator locale, devono fare riferimento a questa documentazione protetta per determinare il nome utente e la password per il server.

#### NTFS

Le partizioni NTFS supportano gli elenchi di controllo di accesso (ACL) e, a scelta, la crittografia, tramite EFS (Encrypting File System), a livello di file e cartelle. Questo supporto non è disponibile nel file system FAT, FAT32 o FAT32x. FAT32 è una versione del file system FAT che è stata aggiornata per rendere possibili dimensioni di cluster predefinite molto più piccole e per supportare dischi rigidi di dimensioni fino a due terabyte. FAT32 è disponibile in Microsoft Windows 95 OSR2, Windows 98, Windows Me, Windows Server 2003 e Windows XP.

##### Vulnerabilità

I file che non è possibile proteggere mediante gli elenchi di controllo di accesso (ACL) possono essere visualizzati, modificati o eliminati facilmente da utenti non autorizzati che riescano ad accedervi localmente o dalla rete. Altri file possono essere protetti con gli elenchi ACL, ma la crittografia garantisce un livello più elevato di protezione e rappresenta una valida alternativa per la protezione dei file a cui deve poter accedere un solo utente.

##### Contromisura

Formattare tutte le partizioni di tutti i server utilizzando NTFS. Utilizzare il programma di utilità convert per eseguire la conversione non distruttiva delle partizioni FAT in NTFS, tenendo presente, tuttavia, che questa utilità configurerà gli ACL dell’unità convertita su Everyone: Controllo completo.

Per i computer Windows Server 2003 e Windows XP, applicare i seguenti modelli di protezione a livello locale per configurare gli elenchi ACL predefiniti del file system:

-   **Per le workstation**. %windir%\\inf\\defltwk.inf

-   **Per i server**. %windir%\\inf\\defltsv.inf

-   **Per i controller di dominio**. %windir%\\inf\\defltdc.inf

Per ottenere le istruzioni su come applicare i modelli di protezione a livello locale, consultare il Capitolo 12, "Ruolo degli host Bastion" nella *Guida per la protezione di* *Windows* *Server* 2003.

**Nota**: le impostazioni di protezione predefinite dei controller di dominio si applicano quando un server viene innalzato al livello di controller di dominio.

##### Impatto potenziale

Nessun impatto negativo.

**Importante**: la configurazione corretta delle autorizzazioni NTFS contribuisce a proteggere i dati dell'organizzazione da divulgazione o da modifiche non autorizzate, ma è comunque molto importante non trascurare la protezione fisica. Un pirata informatico che riesca ad accedere a un computer può avviarlo con un sistema operativo diverso utilizzando un CD-ROM o un disco floppy di avvio. Un pirata informatico che riesca a rimuovere un disco rigido da un computer dell’organizzazione può spostarlo in un altro computer non gestito. Se il pirata informatico si impadronisce dei supporti di archiviazione, diventa estremamente difficile tutelare i dati.

Questo problema sostanziale inerente la protezione dei computer esiste anche per i file system di altri sistemi operativi. Una volta che un pirata informatico ottiene l'accesso fisico al disco, le autorizzazioni NTFS, nonché molte misure di protezione, possono facilmente essere aggirate. Le misure di protezione fisiche più comuni che un'organizzazione può implementare sono la restrizione dell'accesso agli edifici, l'installazione di serrature ad azionamento magnetico nelle sale dei server, l'uso di blocchi sui rack dei server e l'adozione di blocchi per gli alloggiamenti di espansione dei computer portatili. Oltre a queste misure di protezione, Microsoft consiglia i seguenti rimedi tecnologici che possono contribuire a ridurre l'impatto di attacchi di questo tipo:

-   Utilizzare Syskey con una password non in linea per impedire che individui non autorizzati possano avviare il sistema operativo Windows.

-   Utilizzare il sistema EFS per crittografare i dati degli utenti. Avvisare gli utenti di utilizzare i propri account di dominio ed evitare di configurare un agente recupero dati oppure configurarlo per gli account degli amministratori del dominio e non per l'account dell'amministratore locale.

-   Utilizzare password BIOS per impedire l'avvio dei computer da parte di utenti non autorizzati.

-   Configurare il BIOS del sistema in modo da disattivare l'avvio dei computer da CD-ROM e da unità disco floppy. Questa configurazione impedirà l'avvio di computer con il sistema operativo di utenti non autorizzati.

#### Segmentazione di dati e applicazioni

Da tempo è considerata buona norma archiviare dati, applicazioni e file del sistema operativo su periferiche di archiviazione diversi, per migliorare le prestazioni del sistema. Se si isolano questi tipi di file sui server si contribuisce a proteggere anche le applicazioni, i dati e i sistemi operativi da attacchi di attraversamento delle directory.

##### Vulnerabilità

La presenza di applicazioni, dati e file di registro sullo stesso volume di archiviazione del sistema operativo presenta due tipi di vulnerabilità. Una vulnerabilità è il rischio che uno o più utenti, in maniera accidentale o deliberatamente, possano riempire il file di registro applicazione oppure caricare file sul server riempiendo di dati il volume di archiviazione.

La seconda vulnerabilità è nota come sfruttamento dell'attraversamento delle directory, in cui un pirata informatico sfrutta un bug in un servizio di rete per risalire la struttura della directory fino alla directory principale del volume di sistema. A questo punto il pirata informatico può eseguire una ricerca nelle cartelle di file del sistema operativo ed eseguire utilità da remoto.

Sono migliaia le varianti degli attacchi basati sull’attraversamento delle directory che sfruttano applicazioni e sistemi operativi vulnerabili. L'IIS è risultato vulnerabile a vari attacchi di questo tipo negli ultimi anni. Ad esempio, i worm NIMDA e Code Red sfruttavano una vulnerabilità a livello di overflow del buffer per attraversare le strutture di directory dei siti Web e, quindi, eseguivano in modo remoto Cmd.exe per accedere a una shell remota ed eseguire altri comandi.

##### Contromisura

Ove possibile, spostare il contenuto Web, le applicazioni, i dati e i file di registro delle applicazioni in una partizione diversa dal volume di sistema.

##### Impatto potenziale

Per le organizzazioni che configurano e gestiscono i server in modo coerente, l’impatto dovrebbe essere minimo. Per le organizzazione che invece non gestiscono queste informazioni, l’impatto sarà maggiore, perché gli amministratori dovranno analizzare la configurazione di ogni computer.

#### Configurare il nome di comunità SNMP

Il protocollo SNMP (Simple Network Management Protocol) è uno standard per la gestione delle reti che trova ampio impiego nelle reti TCP/IP. SNMP consente di gestire i nodi della rete, vale a dire server, workstation, router, bridge e hub, da un host centrale. SNMP esegue i servizi di gestione tramite un'architettura distribuita di sistemi e agenti appositi. I computer che eseguono il software per la gestione della rete vengono detti sistemi di gestione SNMP o gestori SNMP. I nodi della rete gestiti vengono detti agenti SNMP.

Il servizio SNMP fornisce una forma rudimentale di protezione mediante i nomi di comunità e le trap di autenticazione. È possibile limitare le comunicazioni SNMP degli agenti al solo elenco definito di sistemi di gestione SNMP e utilizzare i nomi di comunità per autenticare i messaggi SNMP. È vero che un host può appartenere a più comunità contemporaneamente, ma un agente SNMP non accetta richieste da un sistema di gestione appartenente a una comunità non presente nel suo elenco di nomi di comunità accettabili. Non esiste alcuna relazione tra i nomi di comunità e i nomi di dominio o di gruppi di lavoro. Un nome di comunità può considerata come una password condivisa dalle console di gestione SNMP e dai computer gestiti. È compito dell'amministratore di sistema impostare nomi di comunità difficili da indovinare quando installa il servizio SNMP.

##### Vulnerabilità

In termini di protezione, il protocollo SNMP è per natura debole. La principale vulnerabilità di SNMP è che quasi tutti i fornitori impostano nomi di comunità predefiniti molto diffusi. Ad esempio, Microsoft utilizza il termine Public.

Una seconda vulnerabilità è più difficile da risolvere. Dal momento che il traffico SNMP viene inviato in formato non crittografato, anche il nome di comunità viene trasmesso lungo la rete a un client SNMP senza essere crittografato o sottoposto ad hashing. Per risolvere questa vulnerabilità, è possibile crittografare tutto il traffico tra i server. Questa contromisura non è, tuttavia, contemplata tra gli argomenti trattati in questa guida.

##### Contromisura

Impostare un valore alfanumerico casuale per il nome di comunità SNMP per l’accesso in lettura a tutti i computer.

**Configurazione del nome di comunità SNMP**

1.  Nella console Servizi, fare doppio clic su **Servizio SNMP**.

2.  Fare clic sulla scheda **Protezione** della finestra di dialogo **Proprietà del servizio SNMP**.

3.  Selezionare **public** dall'elenco **Nomi comunità accettati**.

4.  Fare clic sul pulsante **Modifica**, quindi digitare il nuovo nome di comunità nella finestra di dialogo **SNMP Service Community Name** (Nome del servizio di comunità SNMP).

5.  Scegliere **OK** per chiudere tutte le finestre di dialogo.

Lasciare disabilitato l’accesso in scrittura tramite SNMP.

**Nota**: il nome di comunità viene archiviato nel Registro di sistema con il valore DWORD di 4, è pertanto possibile automatizzare questa modifica creando uno script o aggiungendo una riga a un modello di protezione e importando il modello in un criterio di gruppo basato sul dominio. Il valore viene archiviato in: **HKLM\\SYSTEM\\CurrentControlSet\\Services\\SNMP\\Parameters\\ValidCommunities**.

##### Impatto potenziale

È necessario riconfigurare il nome di comunità anche in tutti gli strumenti di gestione che utilizzano il protocollo SNMP.

#### Disabilitare NetBIOS e SMB nelle interfacce esposte pubblicamente

Questa sezione esamina alcune indicazioni destinate ai server situati in reti che non possono essere controllate a pieno, come server Web accessibili dal pubblico e gateway di posta elettronica. Questi tipi di server vengono spesso detti host Bastion. Con server di questo tipo, conviene prendere in considerazione le procedure consigliate in questa contromisura. Tuttavia, conviene fare una prova meticolosa delle modifiche apportate ed è importante essere consci che è difficile gestire computer in cui è stato disattivato NetBIOS.

##### Vulnerabilità

Per contribuire alla protezione dell'host Bastion, disattivare i protocolli SMS (Server Message Block) e NetBIOS su TCP/IP, che riducono in maniera sostanziale la superficie di attacco. Server che operano in una configurazione di questo tipo sono difficili da gestire e non sono in grado di accedere alle cartelle condivise in rete. Tuttavia, così facendo i server vengono protetti efficacemente da violazione tramite i protocolli SMB e NetBIOS. Pertanto, disattivare SMB e NetBIOS su TCP/IP per le connessioni di rete sui server accessibili da Internet.

##### Contromisura

La disattivazione di NetBIOS non impedisce le comunicazioni SMB. In assenza delle porte standard NetBIOS, SMB si servirà della porta TCP 445, detta porta SMB Direct Host o CIFS (Common Internet File System). È quindi necessario eseguire delle operazioni specifiche per disattivare separatamente NetBIOS e SMB.

NetBIOS utilizza le porte seguenti:

-   UDP/137 (servizio nomi NetBIOS)

-   UDP/138 (servizio datagrammi NetBIOS)

-   TCP/139 (servizio di sessione NetBIOS)

SMB utilizza le porte seguenti:

-   TCP/139

-   TCP/445

Completare le seguenti procedure per rimuovere Condivisione file e stampanti per reti Microsoft e Client per reti Microsoft sui server accessibili da Internet.

**Per disattivare SMB**

1.  Nel Pannello di controllo, fare doppio clic su **Connessioni di rete**.

2.  Fare clic con il pulsante destro del mouse su una connessione a Internet, quindi scegliere **Proprietà**.

3.  Nella finestra di dialogo **Proprietà**, selezionare **Client per reti Microsoft**, quindi fare clic su **Disinstalla**.

4.  Seguire la procedura di disinstallazione.

5.  Selezionare **Condivisione file e stampanti per reti Microsoft** e fare clic su **Disinstalla**.

6.  Seguire la procedura di disinstallazione.

**Per disattivare NetBIOS su TCP/IP**

1.  Nel Pannello di controllo fare doppio clic su **Sistema**, selezionare la scheda **Hardware** e quindi fare clic sul pulsante **Gestione periferiche**.

2.  Nel menu **Visualizza**, selezionare **Mostra periferiche nascoste**.

3.  Espandere **Driver non Plug and Play**.

4.  Fare clic con il pulsante destro del mouse su **NetBIOS su Tcpip**, quindi fare clic su **Disabilita**.

Questa procedura consente di disattivare il listener per SMB direct host su TCP/445 e UDP 445.

**Nota**: questa procedura disattiva il driver Nbt.sys. Sebbene la procedura consenta di disattivare il servizio sessione NetBIOS, in ascolto sulla porta TCP 139, non consente di disattivare completamente SMB. A questo scopo, eseguire la procedura "Per disattivare SMB", descritta in precedenza.

##### Impatto potenziale

Nessun sistema sarà in grado di collegarsi al server tramite SMB. I server non potranno accedere alle cartelle condivise sulla rete. Gli strumenti di gestione che dipendono dai protocolli NetBIOS o SMB per la connettività non saranno in grado di collegarsi ai server.

#### Configurare la porta per Servizi terminal

Servizi terminal è uno strumento molto utile per gli amministratori della rete, perché consente la gestione remota dei server e dei computer degli utenti finali. Il client Desktop remoto viene installato per impostazione predefinita in tutti i computer Windows Server 2003 e Windows XP ed è disponibile come componente facoltativo nei supporti di installazione di Windows 2000 Server. È disponibile una versione scaricabile del Microsoft ActiveX, eseguibile in Internet Explorer o nel modulo MMC (Microsoft Management Console). Nel complesso, i client Desktop remoto e ActiveX sono detti client TSAC (Terminal Services Advanced Client).

##### Vulnerabilità

Per impostazione predefinita, Servizi terminal utilizza la porta TCP 3389, e tutte le versioni dei client Desktop remoto cercano di connettersi a questa porta. L’intera sessione è crittografata, compresa l’autenticazione dell’utente, ma i client di Servizi terminal non effettuano l’autenticazione del server. Un pirata informatico che riuscisse a portare a termine un attacco di spoofing contro un server di Servizi terminal potrebbe ingannare gli utenti e convincerli a connettersi a un server diverso da quello legittimo. A tal fine, il pirata informatico può tentare di alterare i record DNS per ridirigere gli utenti a un server non autorizzato oppure utilizzare altri mezzi per ottenere lo stesso risultato.

##### Contromisura

Cambiare la porta TCP utilizzata da Servizi terminal o implementare un criterio IPsec per richiedere l’attendibilità e negoziare il protocollo AH (Authentication Header) o ESP (Encapsulation Security Payload) utilizzando la modalità di trasporto IPsec (non la modalità tunnel IPsec). In alcuni casi, può essere opportuno isolare il sistema Server terminal dietro un gateway VPN, in modo che per accedere al Server terminal siano necessari tunnel VPN protetti con PPTP (Point-to-Point Tunneling Protocol) o L2TP/IPSec.

Per informazioni su come cambiare la porta utilizzata dai Servizi terminal e dal client Desktop remoto, consultare l'articolo della Microsoft Knowledge Base "[Modifica della porta di attesa del server terminal](http://support.microsoft.com/kb/187623/it)" all'indirizzo http://support.microsoft.com/kb/187623/it. Questo articolo illustra come cambiare la porta di ascolto per i client desktop normali. A tal fine, il client Web TSAC (Terminal Services Advanced Client), è necessario aggiungere il seguente script nella pagina Web:

MsRdpClient.RDPport = xxx

(xxx rappresenta il numero di porta TCP prescelto). Per ulteriori informazioni su come utilizzare e personalizzare la Connessione Web di Desktop remoto per eseguire sessioni di Servizi terminal in Microsoft Internet Explorer, consultare " [Providing for RDP Client Security](http://msdn.microsoft.com/en-us/library/aa382994.aspx)" (in inglese) all'indirizzo http://msdn.microsoft.com/library/default.asp?url=/library/en-us/termserv/termserv/
providing\_for\_rdp\_client\_security.asp.

##### Impatto potenziale

L'implementazione di IPsec con AH avrà un impatto trascurabile sulle prestazioni del computer, sebbene la configurazione IPsec di client e server comporti nuovi carichi gestionali. Per gestire un metodo di trust reciproco tra i computer client e server utilizzati dalla negoziazione di protezione IKE (Internet Key Exchange) prima che vengano stabilite le associazioni di protezione IPsec viene aggiunto altro carico. Configurare il criterio IPsec per proteggere tutto il traffico verso il server oppure per richiedere IPsec solo per le connessioni alla porta TCP 3389. Se si richiede IPsec lato server, si impedisce l’accesso ai computer client che non dispongono di trust e configurazione compatibili con IPsec. Per ulteriori informazioni su come utilizzare i criteri IPsec per le negoziazioni della protezione del traffico TCP/IP, consultare la sezione “Configurare criteri IPsec” in questo capitolo.

Se si cambiano le porte predefinite nei server e nei client di Servizi terminal, tutti gli utenti autorizzati che non hanno configurato il software client in modo che utilizzi la nuova porta non saranno in grado di collegarsi ai computer le cui assegnazioni di porta sono state cambiate. Inoltre, non è possibile cambiare la porta TCP nella versione corrente di TSAC.

#### Disattivare Dr. Watson: Disattivare l'esecuzione automatica del debugger di sistema Dr. Watson

I debugger di sistema agevolano la risoluzione dei problemi di computer e applicazioni. Con il computer in funzione, questi programmi raccolgono dati e li presentano all'amministratore di sistema o allo sviluppatore di applicazioni. Lo strumento Dr. Watson, componente di Windows Server 2003 e Windows XP, è un debugger di sistema automatico che registra le informazioni sullo stato del sistema e sulle applicazioni attive al momento in cui si verifica un errore di programma.

##### Vulnerabilità

Alcune organizzazioni possono decidere di non installare alcun debugger di sistema sui computer di produzione. Tuttavia, non esistono violazioni correlate all'uso di Dr. Watson che possano essere effettuate da utenti privi di privilegi di amministratore. Vale a dire, che un pirata informatico deve appartenere al gruppo **Administrators** locale per poter utilizzare Dr. Watson come strumento di attacco nei confronti di altri utenti o processi. Un pirata informatico che ha ottenuto privilegi amministrativi ha il controllo completo del computer, pertanto è in grado di perseguire altre strade per disattivare Dr. Watson.

##### Contromisura

Per istruzioni su come disattivare il debugger di sistema Dr. Watson, consultare l'articolo "[Disabilitazione di Dr. Watson per Windows](http://support.microsoft.com/kb/188296/it)" all'indirizzo http://support.microsoft.com/kb/188296/it.

##### Impatto potenziale

Se si verifica un arresto anomalo dei programmi, non verrà eseguito alcun debugger di sistema e non verrà generato automaticamente alcun rapporto. Gli amministratori di sistema e gli sviluppatori avranno meno informazioni a disposizione per diagnosticare la causa di problemi di questo tipo. Anche, la funzionalità di segnalazione errori non funzionerà.

#### Disattivare SSDP/UPNP: Disattivare SSDP/UPNP

Se si disattiva il servizio host UPnP (Universal Plug and Play), le altre applicazioni quali Windows Messenger saranno ancora in grado di utilizzare il servizio di rilevamento SSDP (Simple Service Discovery Protocol), un processo di rilevamento atto a identificare i gateway o altre periferiche di rete.

Per ulteriori informazioni, consultare l'articolo della Microsoft Knowledge Base "[L'invio di traffico dopo aver rilevato il servizio, Plug and Play universale e l'host di periferica di riproduzione](http://support.microsoft.com/kb/317843/it)" all'indirizzo http://support.microsoft.com/kb/317843/it.

##### Vulnerabilità

Le funzionalità UPnP incluse in Windows  XP e Windows Server 2003 risultano molto utili per utenti privati e piccole aziende, poiché consentono di automatizzare le procedure di installazione e configurazione delle periferiche UPnP collegate alla rete locale. Alcune organizzazioni devono verificare che non vi sia alcun traffico UPnP o SSDP sulla propria rete. Sebbene, a tutt'oggi, non esistano vulnerabilità note correlate a queste funzionalità, un paio d'anni fa è stato identificato un problema grave in Windows XP che ha richiesto un aggiornamento rapido.

##### Contromisura

Per assicurare che nessuna applicazione utilizzi le funzionalità SSDP ed UPnP contenute in Windows  XP, aggiungere il valore del registro REG\_DWORD, UPnPMode, alle seguenti chiavi del Registro di sistema:

**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\DirectPlayNATHelp\\DPNHUPnP\\**

e configurare il valore su 2.

##### Impatto potenziale

Le funzionalità UPnP e SSDP saranno completamente disattivate. Quando si collegano periferiche UPnP alla rete, sarà necessario configurarle e gestirle manualmente.

#### Configurare criteri IPsec

IPsec, disponibile nei sistemi operativi Windows 2000, Windows XP e Microsoft Windows Server 2003, è uno strumento che consente agli amministratori della protezione della rete di autorizzare, bloccare o negoziare la protezione del traffico TCP/IP. IPsec è indipendente da applicazioni ed è anche trasparente per le stesse. Per Windows 2000 l’obiettivo era fornire un meccanismo per proteggere il traffico della rete utilizzando il formato AH o il formato ESP del protocollo IPsec. Il criterio IPsec fornisce filtri statici per il traffico TCP/IP (detti anche "*selettori*") necessari per negoziare la protezione utilizzando IKE, detto anche protocollo ISAKMP.

Il Capitolo 6, "Deploying IPsec" nel [*Windows Server 2003 Deployment Kit: Deploying Network Services*](http://www.microsoft.com/downloads/details.aspx?familyid=aaf0a7a4-71c1-4ee9-b974-66214651a23b&displaylang=en) (in inglese) fornisce un approfondimento sugli aggiornamenti delle funzionalità di IPsec. Nella sezione intitolata "Determining Your IPSec Needs" vengono delineati gli utilizzi di IPsec: Questa pubblicazione può essere scaricata all'indirizzo www.microsoft.com/downloads/details.aspx?
FamilyID=d91065ee-e618-4810-a036-de633f79872e&DisplayLang=en.

Il componente Windows Firewall è in grado di fornire alla maggior parte delle applicazioni protezione adeguata a livello di host contro traffico dannoso in ingresso. La Configurazione guidata impostazioni di sicurezza (SCW) di Windows Server 2003 con SP1 semplifica di molto l'organizzazione e la gestione delle impostazioni di Windows Firewall per le operazioni di distribuzione di grandi dimensioni. Dove opportuno, utilizzare IPsec per proteggere il traffico host-to-host e host-client e distribuire quanto più possibile Windows Firewall, che, di norma, dovrebbe essere impiegato nella maggior parte delle organizzazioni come livello aggiuntivo di protezione.

##### Vulnerabilità

La maggior parte delle strategie di protezione delle reti sono rivolte a evitare attacchi provenienti dall'esterno della rete. Tuttavia, le informazioni riservate di un’organizzazione possono essere oggetto di attacchi interni, che interpretano i dati della rete o che sfruttano punti deboli a livello di progettazione o implementazione dei protocolli del livello superiore per accedere al computer. I pirati informatici potrebbero utilizzare le sessioni null NetBT per recuperare informazioni utili per compromettere le password degli amministratori (se non si adottano o si disattivano accidentalmente altre impostazioni di protezione).

È sufficiente per i pirati informatici individuare una vulnerabilità in una porta dell'applicazione per poter accedere e potenzialmente acquisire il controllo completo del computer. Come osservato, poiché molti tipi di dati attraversano la rete non protetti impiegati, membri del personale di assistenza o visitatori possono essere in grado di copiare dati da analizzare in un momento successivo. I firewall posti tra la rete interna e Internet non offrono alcuna protezione contro questi pericoli interni. Spesso, inoltre, i firewall interni non sono in grado di effettuare i controlli necessari sugli accessi autenticati per proteggere client e server, né possono garantire una protezione end-to-end del traffico di rete tra i computer.

##### Contromisura

I filtri IPsec riconoscono il traffico TCP/IP in base agli indirizzi IP di origine e di destinazione, in base al tipo di protocollo IP e in base alle porte TCP e UDP. Grazie alle loro capacità di bloccare il traffico di worm e virus, i filtri IPsec contribuiscono a contenere e controllare la diffusione di codice dannoso. Inoltre, IPsec può rendere molto difficile il ricorso a shell remote o altre utilità per accedere al computer da un’applicazione compromessa. Per ulteriori dettagli su come applicare il criterio IPsec in Windows 2000 per bloccare le porte, consultare l'articolo della Microsoft Knowledge Base “[Blocco di specifici protocolli di rete e porte utilizzando IPSec](http://support.microsoft.com/kb/813878/it)” all'indirizzo http://support.microsoft.com/kb/813878/it. Inoltre, procedure dettagliate per la configurazione del filtraggio autorizzazione/blocco di IPsec in Windows Server 2003, simili a quanto offerto in questa guida, sono disponibili nel white paper "[Using IPSec to Lock Down a Server](http://www.microsoft.com/technet/itsolutions/network/security/ipsecld.mspx)" (in inglese) all'indirizzo www.microsoft.com/technet/itsolutions/network/security/ipsecld.mspx. Per Windows 2000 è tuttavia necessario aggiungere le impostazioni del registro NoDefaultExempt consigliate nell'articolo della Knowledge Base.

In Windows Server 2003 è presente lo snap-in MMC Gestione dei criteri di protezione IP, un’interfaccia grafica utente (GUI) per la gestione del criterio IPsec. Questo strumento è molto simile a quello per Windows 2000 e Windows XP. In Windows Server 2003 sono disponibili lo snap-in MMC Monitor di protezione IP e l’utilità della riga di comando NETSH IPsec che consente di controllare l’applicazione dei filtri del criterio IPsec al computer. Il filtri di autorizzazione e blocco sono presenti nella configurazione della modalità rapida IKE; i filtri generici della modalità rapida IKE sono definiti nel criterio IPsec assegnato. I filtri specifici in modalità rapida IKE derivano dal criterio applicato alla configurazione IP specifica del computer. Si osservi che la funzione dei filtri specifici in modalità rapida IKE, Trova filtri corrispondenti, non può essere utilizzata per trovare filtri di autorizzazione/blocco, ma solo filtri cui sia associata un’azione di negoziazione.

Il resto di questa sezione illustra i seguenti termini:

-   **Elenco filtri**. Include porte, protocolli e indicazioni. Gli elenchi filtro attivano una decisione quando il traffico corrisponde a un criterio specificato nell'elenco. Un elenco può contenere più filtri.

-   **Operazione filtro**\\ Risposta richiesta quando esiste una corrispondenza tra il traffico e un elenco filtro. Tra le azioni possibili vi sono il blocco o l’autorizzazione di un determinato traffico.

-   **Regola** Correlazione di un elenco filtro e di un’azione filtro.

-   **Criteri IPsec**. Raccolta di regole. In un dato momento può essere attivo un solo criterio.

Una soluzione semplice per registrare queste informazioni è offerta da una tabella, detta mappa del traffico della rete. La mappa del traffico della rete contiene informazioni di base sul ruolo del server, sulla direzione del traffico della rete, sulla destinazione del traffico, sull’indirizzo IP dell’interfaccia, sul protocollo IP, sulla porta TCP e sulla porta UDP interessata. Nella seguente tabella è riportata una mappa esemplificativa.

Una mappa del traffico della rete contribuisce a determinare i tipi di traffico di rete in ingresso e in uscita su determinati server. Prima di creare criteri IPsec, è importante aver determinato con chiarezza il traffico necessario al server per garantirne il funzionamento. In caso contrario, si rischia di creare filtri troppo rigidi, che possono compromettere il funzionamento delle applicazioni.

**Per creare la mappa del traffico:**

1.  Individuare i servizi di base della rete necessari per il ruolo del server.

2.  Individuare i protocolli e le porte necessari per ogni servizio. Questo processo può prevedere l'uso di Network Monitor per catturare ed analizzare il traffico della rete al fine di individuare gli indirizzi di destinazione, i protocolli e le porte. Inoltre, è possibile utilizzare strumenti quali il comando Netstat.exe per visualizzare le porte aperte e le connessioni attive.

3.  Documentare le regole per l’applicazione dei filtri IPsec necessarie per autorizzare solo il traffico identificato.

Partendo da filtri IPsec più restrittivi e aprendo le porte solo all’occorrenza, si riesce a ottenere il livello più elevato possibile di protezione per queste impostazioni. Questa procedura risulta molto più semplice se si suddividono i servizi in servizi client e servizi server. Definire come servizi server tutti i servizi che il computer offre ad altri host.

**Tabella 11.1 Esempio di mappa del traffico della rete**

 
<table style="border:1px solid black;">
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Servizio</th>
<th style="border:1px solid black;" >Protocollo</th>
<th style="border:1px solid black;" >Porta di origine</th>
<th style="border:1px solid black;" >Porta di destinazione</th>
<th style="border:1px solid black;" >Indirizzo di origine</th>
<th style="border:1px solid black;" >Indirizzo di destinazione</th>
<th style="border:1px solid black;" >Azione</th>
<th style="border:1px solid black;" >Mirror</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">HTTP Server (Server HTTP)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Server HTTPS</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">443</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Client DNS</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">53</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">DNS</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Block everything (Blocco generale)</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">BLOCCA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
</tbody>
</table>
  
In questa mappa del traffico esemplificativa, il server Web offre servizi HTTP e HTTPS ai computer con qualsiasi indirizzo IP di origine, così da autorizzare il traffico appropriato. Per la destinazione ME (Questo computer) il servizio IPsec crea un filtro per ognuno degli indirizzi IP del computer. Ognuno di questi filtri è di tipo speculare, per consentire che il traffico ritorni al computer di origine. Questo approccio significa che in pratica la regola “HTTP Server” (server HTTP) autorizzerà il collegamento del traffico proveniente da qualsiasi host o porta di origine alla porta 80 dell'IIS. La regola speculare permette al traffico TCP proveniente dalla porta 80 del server IIS di connettersi a qualsiasi porta di qualsiasi host.
  
Un servizio client è un qualsiasi servizio che il computer esegue in cui i criteri utilizzano un altro host. Ad esempio, nella mappa del traffico esemplificativa, il server potrebbe aver bisogno del servizio client DNS per eseguire ricerche di nomi per un’applicazione Web. In questo esempio, il filtro è stato creato per autorizzare il traffico da e verso il server o i server DNS. In Windows Server 2003 sono stati apportati miglioramenti rispetto a Windows 2000 Server per quanto riguarda questo tipo di configurazione per autorizzare il traffico verso i server DNS e altri server dell’infrastruttura. In Windows 2000 il criterio IPsec deve contenere tutti gli indirizzi IP dei server DNS. In Windows Server 2003 il criterio può utilizzare il nome logico DNS, che viene espanso in un filtro per ogni indirizzo IP del server DNS in base alla configurazione IP locale del server.
  
**Nota**: evitare di assegnare a computer Windows 2000 o Windows XP criteri IPsec che utilizzano funzionalità di Windows Server 2003 come questa.
  
Il filtro di blocco speculare “da qualsiasi indirizzo IP all’indirizzo IP di questo computer” blocca tutto il traffico IP unicast da o verso un indirizzo IP del computer. Questo filtro è più generico rispetto ai filtri specifici per protocollo e porte definiti per DNS, HTTP e HTTPS. Dal momento che in Windows Server 2003 sono state rimosse le esenzioni predefinite, questo filtro blocca i pacchetti multicast e broadcast in uscita, perché l’indirizzo IP di origine corrisponde a Indirizzo IP (ME) e l’indirizzo di destinazione corrisponde a Qualsiasi indirizzo IP (ANY). Tuttavia, questo filtro non interviene sul traffico multicast e broadcast in ingresso. L’indirizzo di origine sarebbe qualsiasi indirizzo IP (ANY), ma l’indirizzo di destinazione di un pacchetto multicast o broadcast non è un indirizzo IP specifico del computer, è piuttosto un indirizzo IP multicast o broadcast. Pertanto, questa regola non blocca il traffico broadcast o multicast in ingresso in Windows Server 2003. Questa definizione di filtro è supportata anche in Windows 2000 e Windows XP,. ma rileva solo il traffico IP unicast. Queste piattaforme, infatti, non sono state progettate per consentire il rilevamento dei pacchetti broadcast e multicast da parte dei filtri IPsec. Pertanto, se questo filtro viene applicato in computer Windows 2000 e Windows XP, i pacchetti multicast e broadcast in uscita e in ingresso vengono comunque autorizzati.
  
L'ultima regola, Block Everything (Blocco generale), mostra un altro potenziamento subito dai filtri in Windows Server 2003. Questa regola non è supportata da Windows 2000 o Windows XP e blocca il traffico multicast e broadcast in ingresso e in uscita, nonché tutto il traffico unicast che non soddisfa i requisiti di un filtro più specifico. Se si utilizza questa regola, la regola precedente "Any IP to Me" (da qualsiasi indirizzo IP a questo computer) non è necessaria.
  
È importante tenere presente che se si adotta questo criterio, il computer non può comunicare con il suo server DHCP per rinnovare un lease, con i controller di dominio, con i server WINS, con i siti di revoca CRL o con le stazioni di monitoraggio dei server. Inoltre, questo criterio non consente la gestione remota da parte di amministratori che utilizzano lo snap-in MMC basato su RPC o mediante una connessione client Desktop remoto. Si osservi, inoltre, che se il server IIS dell’esempio fosse dotato di due schede di interfaccia di rete (una per l’accesso a Internet e una per l’accesso interno), tutto il traffico su entrambe le interfacce verrebbe filtrato nello stesso modo. Pertanto, questo criterio deve essere necessariamente personalizzato in base all'ambiente di produzione in cui viene impiegato. Il traffico di rete deve essere filtrato in modo diverso per l’indirizzo IP interno o la subnet. In tutti i casi possibili, utilizzare anche regole di filtraggio che richiedono la gestione remota crittografata con IPsec da stazioni di gestione specifiche, per evitare che server compromessi possano accedere al server tramite l’interfaccia interna oppure possano catturare il traffico di rete generato dall’accesso amministrativo per sferrare attacchi non in linea.
  
Se è necessario utilizzare un servizio client le cui connessioni non si limitano esclusivamente a uno o più server di destinazione specifici, il livello di protezione fornito dai filtri IPsec potrebbe risultare decisamente ridotto. Nel successivo esempio di mappa del traffico della rete, viene aggiunta una regola che consente a un amministratore di utilizzare un browser per accedere a un sito Internet in cui reperire informazioni e patch da scaricare. Questa funzionalità richiede un filtro statico di autorizzazione in uscita speculare per il traffico della porta di destinazione TCP 80.
  
**Tabella 11.2 Esempio di Mappa del traffico della rete per l'esplorazione Web in uscita**

 
<table style="border:1px solid black;">
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Servizio</th>
<th style="border:1px solid black;" >Protocollo</th>
<th style="border:1px solid black;" >Porta di origine</th>
<th style="border:1px solid black;" >Porta di destinazione</th>
<th style="border:1px solid black;" >Indirizzo di origine</th>
<th style="border:1px solid black;" >Indirizzo di destinazione</th>
<th style="border:1px solid black;" >Azione</th>
<th style="border:1px solid black;" >Mirror</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Inbound ICMP for TCP PMTU (ICMP in ingresso per PMTU TCP)</td>
<td style="border:1px solid black;">ICMP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">NO</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Inbound IIS Server HTTP:80 (HTTP:80 server IIS in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Inbound IIS Server FTP:21 (FTP:21 server IIS in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">21</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Inbound Terminal Server (Server terminal in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">3389</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Me to Domain DCs all traffic (Tutto il traffico dall'utente ai controller di dominio)</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">Nome dominio</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Outbound DNS UDP/TCP (UDP/TCP DNS in uscita)</td>
<td style="border:1px solid black;">UDP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">53</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">DNS</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Outbound DNS UDP/TCP (UDP/TCP DNS in uscita)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">53</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">DNS</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Outbound WINS (WINS in uscita)</td>
<td style="border:1px solid black;">UDP</td>
<td style="border:1px solid black;">137</td>
<td style="border:1px solid black;">137</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">WINS</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Outbound DHCP (DHCP in uscita)</td>
<td style="border:1px solid black;">UDP</td>
<td style="border:1px solid black;">68</td>
<td style="border:1px solid black;">67</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">DHCP</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Outbound HTTP:80 (HTTP:80 in uscita)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Block everything (Blocco generale)</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">BLOCCA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
</tbody>
</table>
  
Sebbene questa mappa di traffico esemplificativa sembri riportare una configurazione corretta, il risultato è che tutto il criterio adesso non fornisce alcuna protezione contro un pirata informatico che avvia una connessione in ingresso da un indirizzo IP qualsiasi tramite la porta di origine TCP 80. Questo pirata informatico può accedere a qualsiasi porta TCP aperta tramite il filtro di autorizzazione in ingresso e, inoltre, viene autorizzata la risposta tramite il filtro di autorizzazione in uscita verso la porta di destinazione TCP 80.
  
Per bloccare un attacco in ingresso è possibile ricorrere alle seguenti soluzioni:
  
-   Utilizzare ulteriori regole di filtraggio IPsec per impedire che un pirata informatico utilizzi la porta 80 per accedere alle porte aperte.
  
-   Utilizzare un router o un firewall di filtraggio con informazioni sullo stato nel front-end per bloccare il traffico in ingresso proveniente dalla porta 80 a meno che non corrisponda a una connessione in uscita.
  
-   Oltre a questo criterio IPsec, configurare Windows Firewall nella scheda di rete esterna del server per garantire il filtraggio con informazioni sullo stato di tutto il traffico in uscita autorizzato dai filtri IPsec. Dal momento che il livello di Windows Firewall è superiore rispetto a IPsec, è necessario configurarlo anche per autorizzare le porte TCP 80 e 443 in ingresso, sebbene questa sia la configurazione predefinita.
  
La mappa del traffico esemplificativa riportata nella seguente tabella, utilizza filtri IPsec aggiuntivi per bloccare qualunque tentativo di accesso alle porte aperte dalla porta 80. Innanzitutto, si utilizza il comando Netstat –ano per determinare le porte TCP da aprire sul server cui si potrebbe collegare un pirata informatico. L'uscita di questo comando è simile a quanto segue:
  
```
    C:\Documents and Settings\testuser.domain.000>netstat -ano 
    Active Connections

    Proto  Local Address       Foreign Address     State         PID
    TCP    0.0.0.0:135         0.0.0.0:0           LISTENING     740
    TCP    0.0.0.0:445         0.0.0.0:0           LISTENING     4
    TCP    0.0.0.0:1025        0.0.0.0:0           LISTENING     884
    TCP    0.0.0.0:1046        0.0.0.0:0           LISTENING     508
    TCP    192.168.0.5:139     0.0.0.0:0           LISTENING     4
    UDP    0.0.0.0:445         *:*                               4
    UDP    0.0.0.0:500         *:*                               508
    UDP    0.0.0.0:1026        *:*                               816
    UDP    0.0.0.0:1029        *:*                               508
    UDP    0.0.0.0:1051        *:*                               452
    UDP    0.0.0.0:4500        *:*                               508
    UDP    127.0.0.1:123       *:*                               884
    UDP    192.168.0.5:123     *:*                               884
    UDP    192.168.0.5:137     *:*                               4
    
```

Viene quindi definita la regola per bloccare l’attacco specifico dalla porta di origine TCP 25 a ciascuna porta TCP aperta, come illustrato nella seguente tabella:
  
**Tabella 11.3 Esempio riveduto di Mappa del traffico della rete per l'esplorazione Web in uscita**

<table style="border:1px solid black;">
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Servizio</th>
<th style="border:1px solid black;" >Protocollo</th>
<th style="border:1px solid black;" >Porta di origine</th>
<th style="border:1px solid black;" >Porta di destinazione</th>
<th style="border:1px solid black;" >Indirizzo di origine</th>
<th style="border:1px solid black;" >Indirizzo di destinazione</th>
<th style="border:1px solid black;" >Azione</th>
<th style="border:1px solid black;" >Mirror</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Inbound ICMP for TCP PMTU (ICMP in ingresso per PMTU TCP)</td>
<td style="border:1px solid black;">ICMP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">NO</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Inbound IIS Server HTTP:80 (HTTP:80 server IIS in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Inbound IIS Server FTP:21 (FTP:21 server IIS in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">21</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Inbound Terminal Server (Server terminal in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">3389</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Me to Domain DCs all traffic (Tutto il traffico dall'utente ai controller di dominio)</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">Nome dominio</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Outbound DNS UDP/TCP (UDP/TCP DNS in uscita)</td>
<td style="border:1px solid black;">UDP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">53</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">DNS</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Outbound DNS UDP/TCP (UDP/TCP DNS in uscita)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">53</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">DNS</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Outbound WINS (WINS in uscita)</td>
<td style="border:1px solid black;">UDP</td>
<td style="border:1px solid black;">137</td>
<td style="border:1px solid black;">137</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">WINS</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Outbound DHCP (DHCP in uscita)</td>
<td style="border:1px solid black;">UDP</td>
<td style="border:1px solid black;">68</td>
<td style="border:1px solid black;">67</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">DHCP</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Outbound HTTP:80 (HTTP:80 in uscita)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">AUTORIZZA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Mitigation from inbound src 80 attack (Riduzione attacco da porta di origine 80 in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">135</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">BLOCCA</td>
<td style="border:1px solid black;">NO</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Mitigation from inbound src 80 attack (Riduzione attacco da porta di origine 80 in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">139</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">BLOCCA</td>
<td style="border:1px solid black;">NO</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Mitigation from inbound src 80 attack (Riduzione attacco da porta di origine 80 in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">445</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">BLOCCA</td>
<td style="border:1px solid black;">NO</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Mitigation from inbound src 80 attack (Riduzione attacco da porta di origine 80 in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">1025</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">BLOCCA</td>
<td style="border:1px solid black;">NO</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Mitigation from inbound src 80 attack (Riduzione attacco da porta di origine 80 in ingresso)</td>
<td style="border:1px solid black;">TCP</td>
<td style="border:1px solid black;">80</td>
<td style="border:1px solid black;">1046</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUESTO COMPUTER</td>
<td style="border:1px solid black;">BLOCCA</td>
<td style="border:1px solid black;">NO</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Block everything (Blocco generale)</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">QUALSIASI</td>
<td style="border:1px solid black;">BLOCCA</td>
<td style="border:1px solid black;">SÌ</td>
</tr>
</tbody>
</table>

Questo esempio dimostra come creare filtri unidirezionali per bloccare il traffico con la porta di origine 80 per qualunque porta attiva sul computer, che potrebbe bloccare un attacco in ingresso. L'esempio impedisce di effettuare lo spoofing di una porta di origine 80 per connettersi alle porte utilizzate da RPC, NetBT, SMB (CIFS).
  
È possibile applicare i criteri IPsec in modi diversi:
  
-   Applicandoli a un computer singolo.
  
-   Allegandoli all'unità organizzativa o al dominio utilizzando Criteri di gruppo.
  
-   Scrivendo uno script per il comando netsh ipsec e quindi applicando lo script su computer scelti.
  
È possibile distribuire i criteri IPsec in base a Criteri di gruppo. Tuttavia, nei casi in cui è necessario personalizzare i criteri IPsec per computer specifici, è consigliabile utilizzare criteri locali. In alternativa, la soluzione più semplice da gestire è l’uso di criteri locali o di dominio abbinato a un criterio persistente impostato con NETSH IPsec con script. In particolare, è necessario utilizzare NETSH per impostare un criterio persistente che fornisca la protezione durante l’avvio del computer. Per ulteriori dettagli, consultare la sezione "Assigning Domain-based, OU-Level, and Local IPSec Policies" del Capitolo 6, "Deploying IPSec" in *Windows* *Server* *2003 Deployment Kit: Deploying Network Services (in inglese).*
  
###### Negoziazione della protezione IPsec per il traffico
  
L’integrazione del protocollo IKE con le funzionalità di filtro IPsec consente di negoziare in modo automatico e sulla base di criteri la protezione con crittografia IPsec per il traffico IP unicast che soddisfa i criteri dei filtri IPsec. I pacchetti protetti con IPsec possono utilizzare il formato AH o il formato ESP con opzioni di protezione determinate dalla configurazione del criterio. L’impiego di criteri IPsec per negoziare il trasporto protetto con IPsec per le applicazioni e i protocolli del livello superiore presenta i seguenti vantaggi:
  
-   Difesa da attacchi alla rete. IPsec è un protocollo di protezione sviluppato dall'IETF ( Internet Engineering Task Force), maturo e all'avanguardia, che consente agli amministratori di aggiungere un livello di difesa robusto, sotto tutte le comunicazioni IP unicast per aumentare la protezione basata su applicazioni. In questo modo IPsec difende dalle vulnerabilità della protezione dei protocolli del livello superiore e può contribuire in modo significativo a potenziare la protezione delle comunicazioni. Ad esempio, il protocollo per la condivisione di file SMB trova vasto impiego per la replica, il trasferimento di file, la stampa e il download di Criteri di gruppo del servizio directory Active Directory. Tuttavia, SMB non fornisce funzionalità per la tutela della privacy. Tutti i dati inviati in SMB sono visibili a un osservatore della rete passivo. SMB contiene la funzionalità per la firma digitale, ma in alcuni casi non è possibile utilizzarla, perché interessa tutti i percorsi di comunicazione SMB. Per proteggere uno o più percorsi di rete specifici è possibile applicare IPsec. In Windows 2000 e Windows XP sono stati riscontrati due problemi di protezione di SMB. Sebbene le correzioni per questi problemi siano ormai disponibili da Microsoft, è comunque possibile aumentare il grado di protezione utilizzando IPsec come primo livello di difesa contro eventuali attacchi su SMB o altri protocolli. Per ulteriori informazioni su queste due vulnerabilità della protezione di SMB e sulle correzioni disponibili per Windows 2000 e Windows XP, vedere i seguenti articoli della Microsoft Knowledge Base:
  
    -   “[MS02-070: Un difetto nella firma SMB può consentire la modifica dei Criteri di gruppo](http://support.microsoft.com/kb/329170/it)” all'indirizzo http://support.microsoft.com/kb/329170/it.
  
    -   “[MS02-045: Il buffer non controllato nel provider della condivisione di rete può causare un attacco denial of service](http://support.microsoft.com/kb/326830/it)” all'indirizzo http://support.microsoft.com/kb/326830/it.
  
-   La crittografia e l’autenticazione basata su host per tutto il traffico tra due o più computer, sono destinate a garantire che il proprietario amministrativo dei dati ne mantenga il controllo completo anche quando questi attraversano la rete. I dati del traffico della rete contengono un patrimonio informativo estremamente importante e di proprietà dei rispettivi titolari. Il furto di queste informazioni mentre esse percorrono la rete potrebbe causare danni inimmaginabili a un'azienda. Se le relazioni di trust legali e di business che gestiscono il trust e l'integrità del percorso di rete non vengono imposte perfettamente o vengono compromesse, le comunicazioni crittografate con IPsec rimangono protette.
  
-   Attraversamento del firewall semplice e protetto. I molti protocolli utilizzati nelle comunicazioni tra controller di dominio, tra server o tra client e server, vengono interpretati dai firewall solo come traffico ESP (protocollo 50) o traffico AH (protocollo 51) IPsec. I firewall possono essere configurati in modo da autorizzare solo il traffico per questi protocolli (e il traffico IKE), e questi protocolli risultano più protetti contro eventuali attacchi.
  
-   L'IPsec che utilizza l'algoritmo di crittografia 3DES e l'algoritmo di integrità SHA1 è certificato ai sensi di Common Criteria e FIPS 140-1. Gli algoritmi certificati Common Criteria o FIPS 140-1 sono utilizzati per proteggere il traffico di tutta una serie di istituzioni governative, militari, finanziarie e sanitarie. Per impostazione predefinita, la crittografia del traffico della maggior parte dei protocolli Windows, ad esempio RPC, il protocollo di autenticazione Kerberos e LDAP (Lightweight Directory Access Protocol), viene effettuato dall’algoritmo di crittografia dei flussi di dati RC4. RC4 non è uno degli algoritmi certificati ai sensi di Common Criteria o FIPS 140-1.
  
-   In quanto soluzione software per Windows, IPsec risulta più conveniente delle soluzioni hardware per la protezione delle comunicazioni host-to-host. Le soluzioni di protezione hardware, come una rete privata virtuale (VPN) o un linea in noleggio privata, possono risultare più onerose rispetto all'utilizzo di IPsec per Windows.
  
-   IPsec può comportare un utilizzo della CPU inferiore rispetto a misure di protezione specifiche dei protocolli, quali la firma SMB. Le schede di rete che attuano l'offloading dell'elaborazione IPsec, velocizzano le operazioni di crittografia con cui si proteggono i pacchetti IPsec, riducendo al minimo i costi della crittografia a livello di prestazioni. Ne consegue che le connessioni TCP/IP protette con IPsec possono raggiungere la stessa velocità effettiva delle connessioni TCP/IP che non vengono protette con IPsec, con la differenza che queste schede possono comportare costi aggiuntivi in termini di apparecchiature. Se non è possibile utilizzare schede di questo tipo, la crittografia IPsec può aumentare il carico della CPU sul controller di dominio. Ciò potrebbe rendere necessario un aumento di capacità della CPU, a seconda della CPU disponibile e della quantità di traffico nella rete. In alcune circostanze, sarà necessario effettuare test per valutare l’impatto sulle prestazioni dei controller di dominio.
  
##### Impatto potenziale
  
IPsec è uno strumento atto a proteggere i server contro attacchi alla rete, ma non deve essere considerato l’unico strumento possibile, né una soluzione completa. Le funzionalità di filtro IPsec non sono concepite per sostituire filtri firewall o router a protezione perimetrale, completi di tutte le funzionalità. Sono consigliabili, infatti, solo per esigenze di filtraggio dei pacchetti non complessi, per rafforzare la protezione dei client e dei server dove i filtri statici possono rivelarsi efficaci. Inoltre, il filtraggio IPsec è stato progettato per criteri basati su directory da applicare a più computer. Pertanto, durante la configurazione lo snap-in MMC Gestione criteri di protezione IP non è in grado di fornire informazioni dettagliate su come un criterio verrà applicato a un computer specifico. Le limitazioni del filtraggio IPsec sono:
  
-   I filtri IPsec non possono essere applicati a un'applicazione specifica. Possono essere definiti solo per i protocolli e le porte utilizzati dall'applicazione.
  
-   I filtri IPsec sono statici. Non consentono di filtrare traffico in uscita "con informazioni sullo stato". Per autorizzare il traffico in uscita in genere è necessario un filtro di autorizzazione in uscita e in ingresso statico. Pertanto, IPsec non può costituire una difesa contro pirati informatici che utilizzano il filtro di autorizzazione in ingresso statico per accedere a una qualsiasi porta aperta. Ne consegue che i filtri di autorizzazione in uscita devono essere specifici dell'indirizzo o dell'intervallo di indirizzi IP necessari.
  
-   I filtri IPsec non distinguono tra tipi diversi di messaggi ICMP.
  
-   I filtri IPsec non esaminano il contenuto dei pacchetti IP per rilevare tentativi di intrusione.
  
-   I filtri IPsec possono sovrapporsi, ma non possono essere ordinati manualmente. Il servizio IPsec esegue il calcolo interno del peso che determina l’ordine automatico dei filtri. La parte dell’indirizzo del filtro ha la precedenza, seguita dal protocollo, quindi dalle porte di origine e di destinazione.
  
-   I filtri IPsec non sono specifici dell’interfaccia. Possono tuttavia essere configurati per essere specifici per un indirizzo IP, anche se tutto il traffico su ciascuna interfaccia verrà messo a confronto con l'elenco filtri.
  
-   I filtri IPsec non possono essere configurati esplicitamente come filtri in ingresso o in uscita. La direzione (in ingresso o in uscita) viene determinata automaticamente in base agli indirizzi specifici presenti nel filtro. In alcuni casi vengono generati automaticamente sia i filtri in ingresso che i filtri in uscita.
  
-   Il criterio IPsec non supporta filtri doppi.
  
-   In Windows Server 2003 le prestazioni dei filtri IPsec hanno subito un miglioramento sostanziale, anche se l'uso di filtri basati su host può comportare un aumento del carico della CPU in presenza di grandi volumi di traffico. Un firewall o un router front-end ottimizzati possono garantire una maggiore velocità per il filtraggio del traffico.
  
Il blocco del traffico della rete da parte dei filtri IPsec (o di un’altra periferica di rete) può provocare anomalie nel funzionamento delle applicazioni e messaggi di eventi. I filtri IPsec non producono un registro di facile lettura del traffico eliminato in ingresso e in uscita. Le acquisizione del traffico di rete di Network Monitor (Netmon) non visualizzano il traffico in uscita che è stato bloccato. Sebbene sia possibile visualizzare il traffico bloccato in ingresso, il file di acquisizione non contiene alcuna indicazione sull'eliminazione di un particolare pacchetto. Pertanto, la precisione della diagnosi dipende dall'effettiva conoscenza del funzionamento normale di un'applicazione, degli eventi e dei flussi di traffico nella rete in assenza del criterio IPsec.
  
Inoltre, per progettare in modo corretto i filtri IPsec per il traffico delle applicazioni può essere necessaria un’analisi dettagliata dei flussi di traffico nella rete, in modo da determinare come l'applicazione utilizza la rete. Ad esempio, il protocollo SMB utilizza la porta TCP 139 per il trasferimento dei file, la condivisione dei file e la condivisione delle stampanti. Se IPsec blocca questa porta, SMB può anche utilizzare la porta TCP 445. Un altro esempio è rappresentato dal caso in cui un’applicazione richiede più flussi di traffico della rete verso destinazioni diverse. Di norma SMB e altri protocolli autenticano l’utente e questo può far sì, in modo trasparente, che il computer trovi e scambi traffico Kerberos con il controller di dominio. Il protocollo Kerberos utilizza DNS UDP 53 o TCP 53 per individuare l’elenco di indirizzi IP dei controller di dominio, quindi utilizza LDAP UDP 389 e il traffico della porta UDP e TCP 88 verso potenzialmente qualsiasi indirizzo IP di controller di dominio. Pertanto, un errore di stampa potrebbe in realtà essere provocato da un pacchetto bloccato a livello di controller di dominio. Alcuni protocolli, quali RPC, utilizzano un'ampia serie di porte TCP che vengono determinate in modo dinamico all’avvio del computer o al momento dell’esecuzione di un'applicazione, vale a dire che non è possibile controllare in modo efficace le applicazioni RPC mediante filtri statici sulle porte, tranne nei casi in cui la configurazione dell’applicazione RPC richiede l’uso di una porta statica.
  
Windows 2000 e Windows XP prevedono esenzioni predefinite per i filtri specificati nella configurazione del criterio per i tipi di traffico di rete IP che non possono essere protetti con IKE (pacchetti IP broadcast e multicast) o che devono essere esentati per garantire la qualità del servizio per il traffico IPsec (protocollo RSVP) o che funzionano solo se richiesti dal sistema IPsec (IKE stesso e Kerberos come metodo di autenticazione IKE). Sebbene sia disponibile una chiave del Registro di sistema con cui rimuoverle, spesso queste esenzioni non vengono disabilitate quando vengono utilizzati i filtri IPsec per firewall di autorizzazione e blocco. Pertanto Windows Server 2003 contiene una sola esenzione per il traffico IKE. Microsoft consiglia di rimuovere le esenzioni predefinite per tutti gli scenari IPsec in cui vengono utilizzati Windows 2000 e Windows XP. Per ulteriori informazioni sulle esenzioni predefinite, consultare l'articolo della Microsoft Knowledge Base relativo all'utilizzo delle esenzioni IPsec Default per ignorare la protezione IPSec in alcuni scenari, all'indirizzo http://support.microsoft.com/?kbid=811832 e l'articolo della Microsoft Knowledge Base "[Rimozione delle esenzioni predefinite per IPSec in Windows Server 2003](http://support.microsoft.com/kb/810207/it)" all'indirizzo http://support.microsoft.com/kb/810207/it.
  
Quando un computer Windows 2000 è connesso a Internet, un filtro di autorizzazione in uscita speculare (come nel caso della porta 80, illustrata dianzi nel capitolo) consente a un pirata informatico di accedere a qualsiasi porta TCP aperta nel server da Internet utilizzando la porta di origine. Pertanto, un errore nella configurazione di IPsec può rendere nulla la protezione prevista. È necessario, quindi, provare le configurazioni per verificare che forniscano effettivamente la protezione desiderata.
  
Se, a causa di un problema a livello di protezione, un pirata informatico riuscisse ad accedere come amministratore locale o sistema locale, potrebbe disabilitare o modificare il criterio IPsec.
  
In Windows 2000, IPsec non fornisce funzionalità complete di filtraggio durante l’avvio del computer. C’è una piccola finestra di tempo in cui lo stack TCP/IP è reattivo. Un attacco automatizzato potrebbe accedere alle porte dell'applicazione che altrimenti sarebbero bloccate dal criterio IPsec. Nella maggior parte dei casi, le applicazioni non sono state in grado di avviare l'elaborazione delle connessioni prima dell’applicazione dei filtri IPsec. Per ottenere il massimo livello possibile di protezione con i filtri IPsec, scollegare il computer dalla rete durante il riavvio.
  
In Windows Server 2003 è presente un criterio per l’avvio iniziale, che viene utilizzato dal driver IPsec quando viene caricato da TCP/IP durante l’avvio del computer. Non appena il servizio IPsec viene avviato, applica subito il criterio persistente. Successivamente, quando rileva un’assegnazione del criterio IPsec a livello locale o di dominio, la applica in aggiunta al criterio persistente. Pertanto, uno script NETSH IPsec che configuri un criterio persistente predefinito protetto (ad esempio, che blocchi tutto il traffico tranne il traffico di gestione) può fornire una protezione completa durante la transizione dal criterio di avvio al criterio IPsec assegnato a livello locale o di dominio. Ulteriori informazioni sono disponibili nella Guida in linea di Windows Server 2003 e nel Deployment Kit.
  
In ogni caso, Windows 2000 e Windows Server 2003 non consentono di configurare dipendenze di servizi per l’avvio del servizio Agente criteri IPsec. La configurazione di una dipendenza non è una garanzia assoluta che il servizio in questione venga avviato solo dopo l’applicazione dei filtri.
  
In Windows Server 2003 e Windows XP è disponibile Windows Firewall, che effettua un filtraggio con informazioni sullo stato del traffico in uscita e garantisce un controllo di base degli accessi in ingresso a porte e tipi di messaggi ICMP. Windows Firewall genera, inoltre, un registro leggibile dei pacchetti bloccati in ingresso e in uscita. Gli amministratori devono studiare le funzionalità di Windows Firewall e decidere se può essere più adatto per il filtraggio del traffico. La funzionalità di filtro con informazioni sullo stato di Wiindows Firewall può essere utilizzata insieme alla funzionalità di filtro IPsec per fornire la protezione in scenari in cui sia necessario configurare IPsec per l'utilizzo di filtri in uscita speculari per autorizzare il traffico. Qualora sia possibile, è consigliabile applicare i filtri all’altezza di firewall o router del front-end come prima linea di difesa.
  
È consigliabile, inoltre, valutare l'opportunità di adottare un sistema di rilevamento delle intrusioni basato su host e altri sistemi antivirus per rilevare e possibilmente contrastare infezioni e attacchi nel traffico di rete autorizzato e nelle applicazioni. Un firewall di terze parti basato su host o di tipo edge potrebbe rappresentare la soluzione migliore per esigenze di filtraggio complesse.
  
###### Negoziazione della protezione IPsec per il traffico
  
La protezione IPsec end-to-end può potenziare molto la protezione, tuttavia è necessario sapere che la distribuzione di comunicazioni protette con IPsec nella rete richiede formazione e comporta costi amministrativi. Può comportare, inoltre, un incremento dei costi hardware, ove fosse necessario acquistare hardware IPsec, schede di rete con offloading o aumentare la capacità della CPU. Pertanto, prima di distribuire IPsec è importante studiare e documentare con precisione i pericoli che IPsec dovrebbe contrastare, i requisiti di protezione, il costo della distribuzione di IPsec e i vantaggi attesi per l’organizzazione.
  
L’implementazione di IPsec con AH comporta un carico maggiore per la gestione di una configurazione IPsec client/server e per la gestione di un metodo di trust reciproco tra computer client/server. Se i due computer si trovano sempre nello stesso dominio o in domini con relazione di trust reciproco, Criteri di gruppo può fornire le impostazioni necessarie per il criterio IPsec e l’autenticazione Kerberos può definire le relazioni di trust per le associazioni di protezione IPsec. Se i computer non possono utilizzare l'autenticazione Kerberos, è possibile ricorrere ai certificati del computer o a una chiave di autenticazione precondivisa. In questa guida, tuttavia, le chiavi di autenticazione precondivise non vengono consigliate, perché il valore della chiave viene archiviato, senza protezione, nella configurazione del criterio IPsec.
  
È vero che il criterio IPsec locale può essere letto solo dagli amministratori che lo hanno definito, ma al criterio archiviato in Active Directory devono poter accedere tutti i computer del dominio. Pertanto, è difficile mantenere segreto il valore della chiave precondivisa. Microsoft consiglia di servirsi dei certificati digitali, se non è possibile utilizzare il protocollo Kerberos per l’autenticazione IKE. Il criterio IPsec deve essere progettato in modo da proteggere tutto il traffico o in modo da negoziare IPsec per le porte TCP o UDP specifiche. Il criterio IPsec lato client deve essere configurato con l’indirizzo IP statico del server. Se si richiede IPsec lato server, viene negato l’accesso ai computer client che non hanno una configurazione del criterio IPsec compatibile e un metodo di trust reciproco.
  
Per ulteriori informazioni sull’implementazione di IPsec di Windows, consultare la pagina Web relativa a [IPSec per Windows](http://technet.microsoft.com/en-us/network/bb531150.aspx) (in inglese) all'indirizzo http://www.microsoft.com/windows2000/technologies/communications/ipsec/default.asp.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione di Windows Firewall
  
Un firewall Internet contribuisce ad evitare l'accesso dall'esterno al computer tramite Internet. Windows XP con SP2 e Windows Server 2003 con SP1 sono dotati di Windows Firewall, un firewall incorporato in grado di fornire un livello di protezione aggiuntivo che molte organizzazioni possono utilizzare contro attacchi in rete, del tipo worm o DoS (Denial of Service).
  
1.  Fare clic su **Start**, quindi scegliere **Pannello di controllo**.
  
2.  Fare clic su **Windows Firewall**.    
  
3.  Selezionare il pulsante di opzione **Attivato (impostazione consigliata)**.
  
4.  Se necessario, selezionare la scheda **Eccezioni** e configurare le eccezioni per i protocolli autorizzati ad attraversare il firewall.
  
5.  Fare clic su **OK** per attivare Windows Firewall.
  
Windows Firewall dispone solo di una funzionalità di base, atta a prevenire le intrusioni e non è dotato della serie completa di funzionalità offerte dai prodotti di terze parti. Windows Firewall non consente la raccolta dei dati del PC e blocca i tentativi di connessione non richiesti. Tuttavia, Windows Firewall non esegue un filtraggio esteso del traffico in uscita.
  
Windows Firewall propone numerosi miglioramenti importanti rispetto a Firewall connessione Internet (ICF) incluso nelle versioni precedenti di Windows. In particolare, Windows Firewall può essere gestito centralmente tramite Criteri di gruppo. Per ulteriori informazioni sugli strumenti di gestione e sulle impostazioni disponibili, consultare il white paper "[Deploying Windows Firewall Settings for Microsoft Windows XP with Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4454e0e1-61fa-447a-bdcd-499f73a637d1&displaylang=en)" (in inglese) all'indirizzo www.microsoft.com/downloads/details.aspx?  
FamilyID=4454e0e1-61fa-447a-bdcd-499f73a637d1&DisplayLang=en.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
I seguenti collegamenti forniscono ulteriori informazioni sulle misure di protezione aggiuntive per Windows Server 2003 e Windows XP.
  
-   La [*Guida per la protezione di Windows Server 2003*](http://technet.microsoft.com/it-it/library/cc163140.aspx) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14845 fornisce le istruzioni complete per la configurazione e l'amministrazione delle funzionalità di protezione di Windows Server 2003.
  
-   La [*Exchange Server Security Hardening Guide*](http://go.microsoft.com/fwlink/?linkid=37804) (in inglese) scaricabile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=37804 descrive le procedure per attivare la protezione di computer Exchange Server in un dominio Active Directory.
  
-   La [*Microsoft Internet Security and Acceleration (ISA) Server 2004 Hardening Guide*](http://download.microsoft.com/download/c/e/c/cecc8742-2102-42d4-9fc7-6b641bebbf56/isasecurityguide.doc) (in inglese) scaricabile all'indirizzo http://download.microsoft.com/download/c/e/c/cecc8742-2102-42d4-9fc7-6b641bebbf56/ISASecurityGuide.doc descrive i passaggi necessari per proteggere un computer ISA Server 2004, a prescindere dalla sua appartenenza a un dominio.
  
-   Il wihite paper "[Deploying Windows Firewall Settings for Microsoft Windows XP with Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4454e0e1-61fa-447a-bdcd-499f73a637d1&displaylang=en)" (in inglese) all'indirizzo www.microsoft.com/downloads/  
    details.aspx?FamilyID=4454e0e1-61fa-447a-bdcd-499f73a637d1 delinea un processo che contribuisce a determinare le impostazioni appropriate per Windows Firewall e come distribuirle.
  
**Download**
  
[Scaricare la Guida a pericoli e contromisure](http://go.microsoft.com/fwlink/?linkid=15160)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:secwish@microsoft.com?subject=guida%20a%20pericoli%20e%20contromisure)
  
[](#mainsection)[Inizio pagina](#mainsection)
