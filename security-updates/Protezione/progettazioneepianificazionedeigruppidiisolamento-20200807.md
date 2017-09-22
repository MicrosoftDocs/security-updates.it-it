---
TOCTitle: Progettazione e pianificazione dei gruppi di isolamento
Title: Progettazione e pianificazione dei gruppi di isolamento
ms:assetid: '03224fec-a5a0-4940-916d-25ae7e827d0d'
ms:contentKeyID: 20200807
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536207(v=TechNet.10)'
---

Isolamento del server e del dominio tramite IPsec e criteri di gruppo
=====================================================================

### Capitolo 4: Progettazione e pianificazione dei gruppi di isolamento

Aggiornato: 16 febbraio 2005

In questo capitolo vengono fornite informazioni dettagliate sulla definizione di gruppi di isolamento che soddisfino i requisiti di protezione discussi nel capitolo 2, "Isolamento del server e del dominio tramite IPsec e criteri di gruppo". La soluzione proposta utilizza una combinazione di identità dei computer nel dominio del servizio Active Directory®, criteri IPSec per autenticare queste identità e criteri di protezione Microsoft® Windows® per definire e applicare i gruppi di isolamento. Gli amministratori IT possono utilizzare il concetto di gruppo di isolamento per gestire il traffico di rete nelle reti interne in modo sicuro e trasparente per le applicazioni. Questa funzionalità può ridurre notevolmente il rischio di danni provocati da infezioni e attacchi che partono dalla rete.

Avvalendosi dello scenario della Woodgrove Bank, questa guida presenta le informazioni essenziali su come un'organizzazione può trasformare i propri requisiti di protezione in gruppi di isolamento. La guida mostra inoltre come IPSec può combinarsi con altre impostazioni di protezione per realizzare una soluzione di isolamento di server e domini completa, gestibile e scalabile.

Ogni azienda avrà requisiti specifici per la propria soluzione e i modelli forniti in questa guida non vanno adottatati senza porsi domande o apportare modifiche. Le organizzazioni che utilizzano questa guida dovranno decidere che cosa è necessario e realizzabile nei propri ambienti e dovranno modificare adeguatamente il modello del progetto dei gruppi di isolamento per far sì che si adatti pienamente ai requisiti aziendali.

##### In questa pagina

[](#eeaa)[Prima di iniziare](#eeaa)
[](#edaa)[Creazione del progetto di isolamento di server e domini](#edaa)
[](#ecaa)[Metodi di implementazione dei gruppi](#ecaa)
[](#ebaa)[Implementazione dei gruppi per la Woodgrove Bank](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Prima di iniziare

In questa sezione vengono fornite informazioni utili per aiutare l'organizzazione a scegliere il metodo da adottare per l'implementazione della soluzione di isolamento di server e domini. L'esito positivo dell'implementazione di una soluzione di isolamento per l'organizzazione dipende dai prerequisiti identificati in questa sezione.

#### Prima di iniziare

È necessario conoscere i concetti e la terminologia relativi a IPSec, nonché con le seguenti aree di Microsoft Windows Server™ 2003:

-   Criteri IPSec, filtri IPSec, operazioni filtro e elenchi filtri.

-   Concetti relativi ad Active Directory (compresi la struttura e gli strumenti di Active Directory, la gestione di utenti, gruppi e altri oggetti Active Directory, servizi di risoluzione dei nomi e l'uso dei Criteri di gruppo).

-   Concetti di autenticazione compresi il processo di accesso a Windows e il protocollo Kerberos versione 5.

-   Concetti alla base della protezione dei sistemi Windows, quali utenti, gruppi, controllo, elenchi di controllo di accesso (ACL), utilizzo dei modelli di protezione e applicazione dei modelli di protezione mediante Criteri di gruppo o strumenti della riga di comando.

Prima di affrontare questo capitolo, occorre aver letto i capitoli precedenti della presente guida.

#### Prerequisiti organizzativi

È necessario consultarsi con altre persone dell'organizzazione che potrebbero essere coinvolte nell'implementazione della soluzione, fra le quali:

-   Sponsor esecutivi

-   Personale addetto alla protezione e al controllo

-   Personale addetto alla progettazione, amministrazione e gestione di Active Directory

-   Personale addetto a progettazione, amministrazione e gestione di DNS (Domain Name System), server Web e della rete.

    **Nota:** a seconda della struttura dell'organizzazione IT, questi ruoli possono essere ricoperti da più persone oppure un numero ristretto di addetti può ricoprire più ruoli. È però importante individuare una sola persona di contatto che coordini gli sforzi dei team dell'organizzazione nelle varie fasi del progetto.

Prima di affrontare questo capitolo è necessario che siano stati soddisfatti i requisiti elencati nel capitolo 2, "Descrizione dell'isolamento del server e del dominio", e nel capitolo 3, "Determinazione dello stato corrente dell'infrastruttura IT". Ciò significa che occorre aver raccolto le informazioni dagli host, la rete e Active Directory. In questo capitolo viene anche spiegato come individuare i requisiti aziendali e ottenere sponsor aziendali.

Infine, è necessario avere un piano di formazione del personale dell'help desk e del supporto tecnico sui nuovi concetti, terminologia e tecnologie della soluzione. Poiché la soluzione influirà su molte aree dell'organizzazione, il personale del supporto tecnico deve ricevere una formazione adeguata per risolvere i problemi che potrebbero verificarsi durante l'implementazione.

#### Prerequisiti per l'infrastruttura IT

Questo capitolo presuppone l'esistenza della seguente infrastruttura IT:

-   Un dominio Windows Server 2003 con servizio Active Directory in modalità nativa o mista. Questa soluzione utilizza gruppi universali per l'applicazione dell'oggetto Criteri di gruppo (GPO, Group Policy object). Se l'organizzazione non utilizza la modalità nativa o mista, è comunque possibile applicare l'oggetto Criteri di gruppo (GPO) tramite l'uso di configurazioni di gruppo standard globali e locali. Tuttavia, poiché questa opzione è più complessa da gestire, la presente soluzione non la utilizza.

    **Nota**: Windows Server 2003 include numerosi miglioramenti relativi ai criteri IPsec. Nessun aspetto specifico della presente soluzione ne impedisce l'utilizzo con Windows 2000. Tuttavia, la soluzione è stata testata solo su un sistema Windows Server 2003 con servizio Active Directory.
    Per ulteriori informazioni sui miglioramenti apportati a IPsec in Windows Server 2003, consultare la pagina [New features for IPsec](http://technet.microsoft.com/en-us/library/cc739580.aspx) sul sito Web Microsoft all'indirizzo www.microsoft.com/resources/documentation/
    WindowsServ/2003/standard/proddocs/en-us/ipsec\_whatsnew.asp.

[](#mainsection)[Inizio pagina](#mainsection)

### Creazione del progetto di isolamento di server e domini

La progettazione della soluzione dipende in gran parte dai requisiti aziendali e dalle informazioni raccolte nei capitoli precedenti. Nel capitolo 2, "Descrizione dell'isolamento del server e del dominio", e nell'appendice D, "Categorie di pericoli IT", vengono presentati i componenti della soluzione e vengono individuati i rischi che la soluzione può e non può ridurre. Nel capitolo 3, "Determinazione dello stato corrente dell'infrastruttura IT", viene illustrato come raccogliere i dati di pianificazione, ad esempio i dati sull'architettura di rete attuale e sulle risorse degli host della rete. In questo capitolo vengono utilizzati i dati e i requisiti raccolti per la Woodgrove Bank, che sono riportati dettagliatamente nel file **Business\_Requirements.xls** (disponibile nella cartella Strumenti e modelli). È importante consultare questo file durante il processo di progettazione descritto nel presente capitolo per comprendere meglio i motivi che sono alla base del progetto della soluzione. Il processo di progettazione della soluzione comporta le seguenti attività principali:

-   Modellazione dei gruppi di base

-   Pianificazione dei gruppi di computer e dei gruppi di accesso alla rete (NAG)

-   Creazione di gruppi di isolamento aggiuntivi

-   Modellazione dei requisiti del traffico di rete

-   Assegnazione dell'appartenenza ai gruppi di computer e ai gruppi di accesso alla rete (NAG)

Le seguenti sezioni contengono le spiegazioni per ciascuna di queste attività.

#### Modellazione dei gruppi di base

Per la maggior parte delle implementazioni, si consiglia di stabilire un punto di partenza comune per i gruppi di isolamento iniziali. La figura seguente mostra i due gruppi di isolamento iniziali che è opportuno prendere in considerazione.

![](images/Dd536207.SGFG0401(it-it,TechNet.10).gif)

**Figura 4.1 Gruppi di isolamento di base**

I gruppi di isolamento forniscono contenitori logici che costituiscono un ottimo punto di partenza per la progettazione dei gruppi di isolamento.

##### Sistemi non attendibili

Da un punto di vista concettuale, il punto migliore da cui iniziare è costituito dai computer che non sono di proprietà dell'organizzazione, non sono gestiti dal reparto IT o la cui esistenza è addirittura sconosciuta al reparto IT dell'organizzazione. Questi computer sono generalmente host non attendibili o non gestiti e sono i primi sistemi da identificare. Questi computer non faranno parte della soluzione di isolamento perché non potranno utilizzare i criteri IPSec assegnati ai domini.

Esempi di computer che rientrano in questo gruppo:

-   **Computer e dispositivi non Windows**. Le workstation Macintosh e UNIX e le agende elettroniche (PDA) potrebbero non disporre di funzionalità IPSec.

-   **Versioni precedenti del sistema operativo Windows**. I computer che eseguono Microsoft Windows NT® versione 4.0 e Windows 9*x* non possono utilizzare IPSec basato su Criteri di gruppo.

-   **Computer Windows non appartenenti a un dominio attendibile**. I computer autonomi non potranno eseguire l'autenticazione tramite il trust tra domini Kerberos in IKE (Internet Key Exchange). Un computer appartenente a un dominio che non è considerato attendibile dall'insieme di strutture utilizzato come confine della zona protetta per l'autenticazione IKE non potrà entrare a far parte della soluzione di isolamento di domini o server.

-   **Altri client di accesso remoto o VPN non Microsoft**. Se un client di una rete privata virtuale (VPN) non Microsoft IPSec è utilizzato da un'organizzazione in una soluzione di accesso remoto, è probabile che l'installazione abbia disattivato il servizio Windows IPSec nativo. Se non è possibile utilizzare il servizio Windows IPSec nativo, l'host non potrà entrare a far parte della soluzione di isolamento.

    Anche se il servizio Windows IPSec nativo è in esecuzione, il client VPN deve consentire le comunicazioni IKE e IPSec end-to-end attraverso la connessione di tunnelling VPN. Se il servizio IPSec end-to-end non funziona attraverso la connessione VPN, è possibile creare un'esenzione per tutte le subnet IP utilizzate per l'accesso remoto. Quando questo client remoto riconoscerà la rete interna, potrà rientrare a fare parte della soluzione di isolamento.

##### Dominio di isolamento

Un dominio di isolamento costituisce il primo contenitore logico per gli host attendibili. Gli host di questo gruppo utilizzano i criteri IPSec per controllare le comunicazioni consentite in ingresso e in uscita da loro stessi. Il termine *dominio* è utilizzato in questo contesto per illustrare il confine della zona protetta piuttosto che suggerire un dominio Windows. In questa soluzione di isolamento i due costrutti sono molto simili perché l'autenticazione del dominio Windows (Kerberos) è richiesta per accettare connessioni in ingresso provenienti da host attendibili. Tuttavia, molti domini (o insiemi di strutture) Windows possono essere collegati con relazioni di trust per fornire un singolo dominio di isolamento logico. In questo senso, i due costrutti non vanno considerati come una sola e stessa entità.

Lo scopo delle caratteristiche delle comunicazioni del dominio di isolamento è di fornire regole "normali" o standard per la maggior parte dei computer dell'organizzazione. In questo modo, in quasi tutte le implementazioni un dominio di isolamento conterrà il maggior numero possibile di computer. È possibile creare altri gruppi di isolamento per la soluzione se i loro requisiti di comunicazione sono diversi da quelli del dominio di isolamento. Concettualmente, un dominio di isolamento non è altro che un tipo di gruppo di isolamento.

##### Gruppo Limite

In quasi tutte le organizzazioni esistono alcune workstation o server che non possono comunicare avvalendosi di IPSec. Ad esempio, è probabile che le workstation Mac o UNIX non possano comunicare utilizzando IPSec. Spesso vi sono requisiti aziendali che prevedono che questi computer comunichino con host attendibili nel dominio di isolamento. In un ambiente ideale, tutti gli host della rete interna dovrebbero essere considerati attendibili allo stesso livello e utilizzare IPSec, nel qual caso il progetto sarebbe più semplice. Tuttavia, in realtà non tutti i sistemi operativi forniscono lo stesso livello di supporto per IPSec.

Per far fronte a questa situazione, si consiglia di creare un gruppo di isolamento (denominato gruppo Limite in questa guida) contenente gli host che potranno comunicare con i sistemi non attendibili. Questi host sono esposti a maggiori rischi perché possono ricevere comunicazioni in ingresso provenienti direttamente da computer non attendibili.

I computer del gruppo Limite sono host attendibili che possono comunicare sia con altri host attendibili che con host non attendibili. Gli host del gruppo Limite tenteranno di comunicare con IPSec avviando una negoziazione IKE con il computer di origine. Se non viene ricevuta alcuna risposta IKE entro tre secondi, l'host utilizzerà la *modalità non crittografata* e tenterà di stabilire una comunicazione in testo normale senza l'ausilio di IPSec. Gli host del gruppo Limite possono avere un indirizzo IP dinamico perché utilizzano i criteri IPSec analogamente a qualsiasi altro host attendibile presente nel dominio di isolamento. Poiché questi host del gruppo Limite possono comunicare con host attendibili che utilizzano comunicazioni di rete protette da IPSec e con host non attendibili che utilizzano la modalità non crittografata, devono essere comunque altamente protetti in altri modi. Comprendere e ridurre questi rischi aggiuntivi costituisce una parte importante del processo che porterà all'inserimento o meno di un computer nel gruppo Limite. Ad esempio, istituire un processo formale di giustificazione aziendale per ogni computer prima di decidere di inserirlo in questo gruppo può assicurare che tutte le parti interessate capiscano perché vi sono rischi aggiuntivi. La figura seguente mostra un esempio di processo che può aiutare a prendere questa decisione.

[![](images/Dd536207.SGFG0402(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536207.sgfg0402_big(it-it,technet.10).gif)

**Figura 4.2 Diagramma del flusso decisionale del processo di inserimento nel gruppo Limite di esempio**

L'obiettivo di questo processo è determinare se i rischi associati all'inserimento di un host nel gruppo Limite possono essere ridotti a un livello accettabile per l'organizzazione. In definitiva, se si conclude che non è possibile ridurre i rischi, l'inserimento deve essere negato.

##### Creazione di elenchi di esenzioni

I modelli di protezione di server e domini sono soggetti ad alcuni vincoli quando vengono implementati in un ambiente reale. I server principali dell'infrastruttura, quali i controller di dominio, i server DNS e i server DHCP (Dynamic Host Configuration Protocol), sono solitamente disponibili per tutti i sistemi della rete interna. Ovviamente devono essere protetti il più possibile dagli attacchi di rete. Tuttavia, poiché sono disponibili per tutti i sistemi della rete e non solo per i membri di dominio, questi servizi server non possono richiedere IPSec per gli accessi in ingresso, né beneficiare dell'utilizzo della protezione in modalità di trasporto IPSec per tutto il loro traffico. Dato che l'opzione di ritorno alla modalità non crittografata dopo tre secondi per consentire l'accesso a questi servizi, in particolar modo a DNS, inciderebbe notevolmente sulle prestazioni di accesso all'intera rete interna, questi server non possono essere inseriti nel gruppo Limite. Inoltre, gli host attendibili richiedono l'accesso al server DHCP per ottenere un indirizzo IP (Internet Protocol) durante l'avvio del computer o quando un cavo di rete (o una scheda di rete) viene collegato a un computer portatile. Gli host attendibili richiedono anche l'accesso a DNS per individuare i controller di dominio al fine di accedere al dominio e ricevere le credenziali Kerberos. Sarà quindi necessario un elenco di server e servizi (protocolli) che sono esentati dall'utilizzare IPSec per garantire il corretto funzionamento di IPSec e per consentire a tutti gli host interni di condividere l'infrastruttura della rete interna comune. L'elenco dei computer che non possono essere protetti con IPSec è denominato *elenco esenzioni* ed è implementato in ogni criterio IPSec configurato. Nella rete possono esistere anche altri server, a cui gli host attendibili non possono accedere utilizzando IPSec, che devono essere aggiunti all'elenco delle esenzioni. In generale, le seguenti condizioni possono far sì che un host sia inserito nell'elenco delle esenzioni:

-   Se l'host è un computer al quale accedono host attendibili ma non ha un'implementazione compatibile con IPSec.

-   Se l'host fornisce servizi per host non attendibili e attendibili ma non soddisfa i criteri di appartenenza al gruppo di isolamento Limite.

-   Se l'host è utilizzato per un'applicazione che è influenzata negativamente dal ritardo causato dal ritorno alla modalità non crittografata dopo tre secondi o dall'incapsulamento IPSec del traffico delle applicazioni.

-   Se l'host supporta molte migliaia di client contemporaneamente ed è stato rilevato che IPSec non può essere utilizzato a causa dell'impatto sulle prestazioni.

-   Se l'host supporta host attendibili di diversi domini di isolamento che non stabiliscono una relazione di trust tra loro.

-   Se l'host è un controller di dominio, perché IPSec non è supportato tra un controller di dominio e un membro di dominio. Tuttavia, i controller di dominio soddisfano altri criteri in questo elenco e forniscono criteri IPSec ai membri di dominio e l'autenticazione Kerberos su cui si basa il concetto di isolamento.

-   Se l'host supporta host attendibili e non attendibili ma non utilizzerà mai IPSec per proteggere le comunicazioni con gli host attendibili.

L'implementazione di IPSec in Windows supporta solo il filtraggio statico e non quello dinamico (o stateful). Di conseguenza, un'esenzione statica per il traffico in uscita è anche un'esenzione statica per il traffico in ingresso. Gli host esentati hanno quindi accesso in ingresso non autenticato a ogni host, sia esso attendibile o non attendibile. Ciò significa che il numero di host esentati deve essere mantenuto al minimo, e questi host devono essere gestiti molto attentamente e protetti al massimo da attacchi e infezioni. Per ridurre i rischi di attacchi in ingresso provenienti da host presenti nell'elenco delle esenzioni si può utilizzare un firewall per il filtraggio di tipo stateful basato su host, come Windows Firewall. Windows XP Service Pack (SP) 2 dispone di controlli Criteri di gruppo per la configurazione del firewall. Windows Firewall può anche autorizzare solo determinati computer attraverso il firewall (se protetti da IPSec) tramite l'impostazione del criterio "Windows Firewall: consenti messaggi da computer con autenticazione IPSec". Woodgrove Bank ha deciso di non implementare Windows Firewall, ma in altri ambienti potrebbe essere necessario ottenere livelli più elevati di protezione in un dominio o in un gruppo isolato. Per ulteriori informazioni, consultare il white paper “[Deploying Windows Firewall Settings for Microsoft Windows XP with Service Pack 2](http://go.microsoft.com/fwlink/?linkid=23277)”, disponibile nell'area di download del sito Web Microsoft all'indirizzo http://go.microsoft.com/fwlink/?LinkId=23277 (in lingua inglese).

Nelle organizzazioni di grandi dimensioni, l'elenco delle esenzioni può diventare particolarmente lungo se tutte le esenzioni sono implementate da un criterio IPSec per l'intero dominio o per tutti gli insiemi di strutture attendibili. Un elenco lungo produce alcuni effetti indesiderati su ogni computer che riceve il criterio, ad esempio:

-   Riduce l'efficacia complessiva dell'isolamento

-   Richiede maggior impegno di gestione (a causa degli aggiornamenti frequenti)

-   Aumenta le dimensioni del criterio, che utilizza così più memoria e risorse della CPU, rallenta la velocità effettiva della rete e fa aumentare il tempo richiesto per il download e l'applicazione del criterio

Esistono vari metodi per mantenere il numero di esenzioni il più basso possibile:

-   Non utilizzare un'esenzione se le comunicazioni possono sopportare il ritardo di tre secondi causato dal ritorno alla modalità non crittografata. Questa opzione non può essere applicata ai controller di dominio.

-   Considerare attentamente i requisiti delle comunicazioni di ogni gruppo di isolamento, in particolare dei gruppi di soli server. Questi gruppi potrebbero infatti non aver bisogno di comunicare con tutte le esenzioni nei criteri a livello di dominio per i client.

-   Raggruppare le funzioni dei server. Se più servizi di esenzione possono essere ospitati in un indirizzo IP, il numero di filtri verrà ridotto.

-   Raggruppare gli host esentati nella stessa subnet. Se il volume del traffico di rete lo consente, i server potrebbero risiedere in una subnet esentata, piuttosto che utilizzare esenzioni per ogni indirizzo IP.

Analogamente alla definizione del gruppo Limite, dovrebbe esservi un processo formale per l'approvazione degli host da aggiungere all'elenco delle esenzioni. Utilizzare il diagramma decisionale della figura precedente come modello per elaborare le richieste di esenzione.

#### Pianificazione dei gruppi di computer e dei gruppi di accesso alla rete

Il dominio di isolamento e ogni gruppo di isolamento devono avere specifiche chiare e complete riguardanti i requisiti di protezione della rete. Il foglio di lavoro **Business\_Requirements.xls**, disponibile nella cartella Strumenti e modelli, contiene un modello che illustra come documentare tali requisiti. Dopo aver individuato e documentato i requisiti in ingresso e in uscita, è possibile progettare i meccanismi per l'implementazione dei controlli di accesso.

A questo punto del processo deve essere avviata una registrazione dei nuovi gruppi di Active Directory che saranno necessari per supportare i requisiti dei gruppi di isolamento. Per ogni gruppo di isolamento occorrerà creare fino a tre gruppi Active Directory specializzati. Nella seguente sezione viene spiegato il ruolo di ciascuno di questi gruppi.

##### Gruppi di computer

Ogni gruppo di isolamento richiederà la creazione di un gruppo di computer che verrà utilizzato come contenitore dei membri del gruppo di isolamento. Tale operazione è necessaria perché i requisiti di protezione per un gruppo di isolamento sono soddisfatti da diversi tipi di impostazioni di protezione nei GPO assegnati nel dominio. Ad esempio, questa soluzione di isolamento utilizza filtri di protezione nei GPO per fornire un criterio IPSec ai computer di un determinato gruppo di isolamento. Agli account di computer che sono membri del gruppo di computer verrà assegnato il criterio IPSec corrispondente quando il GPO viene elaborato. In questo modo, si evita di dover modificare o creare una nuova struttura dell'unità organizzativa (OU) basata sull'appartenenza al gruppo di isolamento per applicare i GPO appropriati. Se la struttura dell'OU può essere modificata per riflettere l'appartenenza al gruppo di isolamento, questi gruppi di protezione non sono necessari per controllare l'applicazione del criterio di gruppo.

**Tabella 4.1: Gruppi di computer della Woodgrove Bank**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome gruppo di computer</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>CG_IsolationDomain_Computers</p></td>
<td style="border:1px solid black;"><p>Questo gruppo universale conterrà tutti i computer che fanno parte del dominio di isolamento.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>CG_BoundaryIG_Computers</p></td>
<td style="border:1px solid black;"><p>Questo gruppo conterrà tutti i computer che sono autorizzati ad accettare comunicazioni da sistemi non attendibili.</p></td>
</tr>  
</tbody>  
</table>
  
##### Gruppi di accesso alla rete
  
Il solo utilizzo di IPSec e di Kerberos garantisce un limite di autenticazione tra ciò che è attendibile e ciò che non lo è. Per consentire di distinguere questi gruppi da tutti gli altri, nella presente guida li si definisce *gruppi di accesso alla rete (NAG, Network Access Group)*.
  
È possibile creare due tipi di NAG: Consenti e Nega. Questi gruppi controllano la capacità di altri sistemi attendibili di consentire o negare esplicitamente l'accesso. È possibile ottenere questo tipo di controllo utilizzando il diritto utente "Nega accesso al computer dalla rete" (NEGA) o "Accedi dalla rete al computer specificato" (CONSENTI) in Criteri di gruppo.
  
Tecnicamente, questo controllo di accesso tramite diritti utente si applica solo ai servizi di rete che ricevono credenziali di accesso per autenticare l'account di accesso alla rete. L'account può essere un computer, un utente o un account di servizio. Quando il criterio IPSec è configurato per proteggere tutto il traffico, IKE confermerà che il computer remoto ha diritto di accesso alla rete. Il diritto di accesso alla rete controllerà quindi la capacità di un computer remoto di stabilire qualsiasi connessione protetta con IPSec. Dopo aver verificato questo controllo di accesso a livello IP, i normali protocolli di livello superiore (ad esempio, di condivisione dei file) autenticano solitamente l'utente, il che comporta una nuova valutazione dei diritti di accesso alla rete dell'identità utente. Infine, le autorizzazioni specifiche per i servizi (quali gli elenchi di controllo dell'accesso alle condivisioni di file) sono valutate tramite l'identità utente. Per ulteriori informazioni, consultare il diagramma sui livelli dei controlli di accesso alla rete riportato nel capitolo 2, "Descrizione dell'isolamento del server e del dominio".
  
Per impostazione predefinita, il diritto utente CONSENTI contiene il gruppo *Tutti*, che permette a tutti gli utenti *e* ai computer autenticati di accedere al computer. Durante l'implementazione di questa soluzione di isolamento, l'assegnazione dei diritti utente Criteri di gruppo sostituirà il gruppo Tutti con i NAG contenenti computer specifici o utenti e gruppi specifici, a seconda dei requisiti organizzativi. Analogamente, il diritto utente NEGA includerà computer che non devono avere accesso in ingresso protetto da IPSec. Sebbene sia possibile utilizzare un solo gruppo per contenere gli account utente e computer, Microsoft consiglia di utilizzare gruppi distinti, uno per gli utenti e un altro per i computer. Questo metodo migliora la gestione e il supporto di questi criteri e gruppi su base continuativa. La configurazione dell'assegnazione dei diritti utente per CONSENTI e NEGA integra le informazioni contenute nelle guide per la protezione delle versioni precedenti di Windows, che non trattavano specificamente l'autenticazione dei computer richiesta da IPSec.
  
I requisiti che possono essere implementati dai NAG includono:
  
-   Bloccare l'accesso di rete ai server contenenti dati riservati per gli host del gruppo Limite o gli host attendibili dislocati in aree pubbliche.
  
-   Limitare l'accesso ai server dei dirigenti aziendali ai soli computer client utilizzati dai dirigenti stessi.
  
-   Isolare gli host attendibili di un progetto di ricerca e sviluppo da tutti gli altri host attendibili di un dominio.
  
Nello scenario della Woodgrove Bank, un requisito aziendale poneva un limite al numero massimo di nuovi dispositivi hardware da acquistare in un anno ed era necessario un server di stampa per consentire sia agli host attendibili che a quelli non attendibili di stampare. Anche se la Woodgrove Bank avrebbe preferito acquistare un nuovo server di stampa che sarebbe stato utilizzato solo dai computer non attendibili, si è deciso che un solo server poteva soddisfare le esigenze di entrambi i tipi di host. È stato quindi creato un server limite come server di stampa. Dato che questo server di stampa era esposto a rischi maggiori di infezione e attacco dai computer non attendibili, gli altri host attendibili dovevano bloccare gli accessi in ingresso da quel server. In ogni caso, gli host attendibili avrebbero potuto, all'occorrenza, stabilire connessioni in uscita al server di stampa. Woodgrove Bank ha quindi deciso che le serviva un NAG di tipo NEGA per soddisfare questo requisito.
  
In questa fase del processo di progettazione, non è necessario determinare l'appartenenza al NAG, ma occorre individuare e documentare i NAG richiesti dal progetto. I progettisti della Woodgrove Bank hanno ravvisato la necessità dei seguenti NAG:
  
**Tabella 4.2: Gruppi di accesso alla rete della Woodgrove Bank**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome NAG</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>DNAG_IsolationDomain_Computers</p></td>
<td style="border:1px solid black;"><p>Questo gruppo include qualsiasi account computer di dominio a cui è negato stabilire connessioni in ingresso protette da IPSec a tutti gli host attendibili del dominio di isolamento.</p></td>
</tr>  
</tbody>  
</table>
  
#### Creazione di gruppi di isolamento aggiuntivi
  
A questo punto del processo di progettazione esistono due gruppi di isolamento: il gruppo Dominio di isolamento e il gruppo Limite.
  
Se questa configurazione soddisfa i requisiti dell'organizzazione, passare alla sezione successiva del presente capitolo per definire i modelli di traffico per questi due gruppi di isolamento. Tuttavia, se l'organizzazione desidera che alcuni host attendibili abbiano requisiti diversi per i controlli di accesso alla rete in ingresso o in uscita o per la protezione del traffico, saranno necessari gruppi di isolamento per ogni insieme di requisiti.
  
Lo scopo di questa sezione è far comprendere quando sono necessari gruppi aggiuntivi. La prima cosa sa fare è identificare quali computer hanno specifici requisiti di isolamento o protezione del traffico che non sono soddisfatti dalle impostazioni del dominio di isolamento. L'obiettivo è quello di mantenere il più basso possibile il numero di questi host, perché ogni nuovo gruppo aumenterà la complessità del progetto globale e renderà quindi più difficoltosi il supporto e la gestione della soluzione di isolamento.
  
Esempi tipici di requisiti che possono comportare la creazione di un gruppo aggiuntivo:
  
-   Requisiti di crittografia
  
-   Accesso limitato per host o utenti necessario a livello di rete
  
-   Requisiti di flusso del traffico di rete in uscita o in ingresso o di protezione diversi da quelli del dominio di isolamento
  
In molti casi, i requisiti di traffico in ingresso nei server contenenti dati ad alto valore devono prevedere connessioni solo da un sottoinsieme di host attendibili. In altri casi, gli host attendibili possono non essere autorizzati a stabilire connessioni in uscita con computer non attendibili per ridurre i rischi di divulgazione accidentale delle informazioni o applicare le normative in materia di protezione del traffico di rete. Nello scenario della Woodgrove Bank, ad esempio, i progettisti hanno individuato alcuni requisiti che potevano essere soddisfatti solo con la creazione dei due seguenti gruppi di isolamento aggiuntivi:
  
-   Il gruppo *Crittografia* contiene un numero esiguo di server per applicazioni con dati ad alto valore che richiede il più elevato livello di protezione. Solo un sottoinsieme specifico di client attendibili è autorizzato a connettersi in ingresso a questi server. Tutto il traffico di rete con questi server richiede crittografia a 128 bit conformemente alle normative federali statunitensi in materia di riservatezza dei dati finanziari. Infine, si è deciso che questi server non dovevano essere autorizzati a stabilire connessioni in uscita con host non affidabili o a ricevere connessioni in ingresso dagli host del gruppo Limite.
  
-   Il gruppo *Nessun fallback* è necessario per alcuni host attendibili del dominio di isolamento per i quali dovevano essere limitate le comunicazioni di rete con sistemi non attendibili.
  
Anche se il secondo gruppo ha un requisito che non prevede l'utilizzo della modalità non crittografata, non ha l'insieme completo di requisiti dei server per applicazioni. Di conseguenza, questi due diversi insiemi di requisiti indicavano che erano necessari due gruppi di isolamento aggiuntivi. I gruppi della Woodgrove Bank sono quindi divenuti quattro. La figura seguente mostra questi gruppi nella configurazione finale dei gruppi di isolamento della Woodgrove Bank:
  
![](images/Dd536207.SGFG0403(it-it,TechNet.10).gif)
  
**Figura 4.3 Configurazione finale dei gruppi di isolamento della Woodgrove Bank**
  
I seguenti quattro gruppi richiedono l'applicazione di criteri per soddisfare i requisiti del progetto:
  
-   **Dominio di isolamento**. Si tratta del gruppo predefinito per tutti i computer attendibili.
  
-   **Gruppo di isolamento Limite**. Questo gruppo è destinato ai computer a cui possono accedere gli host non attendibili.
  
-   **Gruppo di isolamento Crittografia**. Questo gruppo consente le comunicazioni solo attraverso un percorso di comunicazione attendibile e crittografato.
  
-   **Gruppo di isolamento Nessun fallback**. Questo gruppo contiene i computer con un requisito di protezione maggiore che prevede che non possano avviare direttamente comunicazioni con gli host non attendibili.
  
Dato che la Woodgrove Bank ha individuato altri due gruppi che richiedono criteri IPSec diversi, ha definito gruppi di computer aggiuntivi per controllare l'applicazione di questi nuovi criteri.
  
**Tabella 4.3: Gruppi di computer aggiuntivi della Woodgrove Bank**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome gruppo di computer</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>CG_NoFallbackIG_Computers</p></td>
<td style="border:1px solid black;"><p>Questo gruppo contiene tutti i computer a cui non è consentito il ritorno alla modalità non crittografata.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>CG_EncryptionIG_Computers</p></td>
<td style="border:1px solid black;"><p>Questo gruppo contiene tutti i computer che devono utilizzare comunicazioni crittografate.</p></td>
</tr>  
</tbody>  
</table>
  
La Woodgrove ha stabilito quindi che erano necessari alcuni NAG per autorizzare l'accesso in ingresso al sottoinsieme di host attendibili. I progettisti della Woodgrove Bank hanno creato i seguenti NAG:
  
**Tabella 4.4: Gruppi di accesso alla rete della Woodgrove Bank**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome NAG</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>ANAG_EncryptedResourceAccess_Users</p></td>
<td style="border:1px solid black;"><p>Questo gruppo è per tutti gli utenti che sono autorizzati ad accedere ai server del gruppo di isolamento Crittografia.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>ANAG_EncryptedResourceAccess_Computers</p></td>
<td style="border:1px solid black;"><p>Questo gruppo contiene tutti i computer a cui è consentito l'accesso di rete in ingresso ai server del gruppo di isolamento Crittografia.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>DNAG_EncryptionIG_Computers</p></td>
<td style="border:1px solid black;"><p>Questo gruppo include i gruppi di account computer a cui viene negato l'accesso agli host del gruppo di isolamento Crittografia.</p></td>
</tr>  
</tbody>  
</table>
  
#### Raccolta dei requisiti del traffico di rete
  
A questo punto del processo di progettazione è necessario documentare i requisiti di traffico per le comunicazioni che potranno essere trasmesse tra i gruppi e i requisiti di formato per tali comunicazioni. Esistono molti modi di registrare i requisiti di traffico per i gruppi ma, sulla base delle precedenti esperienze, il team del supporto IT Microsoft ritiene che la creazione di un diagramma sia il metodo migliore per comunicare i requisiti esatti.
  
La seguente figura mostra i percorsi di comunicazione che sono generalmente consentiti tra i gruppi di base, gli host non attendibili e gli elenchi di esenzioni. Per semplificare questo modello, gli elenchi di esenzioni sono raffigurati in un unico gruppo, il che è applicabile ai servizi di infrastruttura, quali i controller di dominio o i server DNS. Tuttavia, i gruppi di isolamento possono avere requisiti aziendali in base ai quali è necessario esentare determinati computer di un gruppo. In questi casi, il gruppo di isolamento conterrà un elenco di esenzioni aggiuntive con i computer esentati oltre alle normali esenzioni. Microsoft consiglia di mantenere al minimo il numero di voci negli elenchi di esenzioni perché queste esentano esplicitamente i sistemi dall'appartenere all'infrastruttura IPSec. Nella figura, tutte le frecce con una linea nera continua rappresentano le comunicazioni che utilizzano IPSec; le frecce con linee tratteggiate si riferiscono invece alle comunicazioni che possono avvenire senza IPSec. Ai computer dei gruppi che sono contrassegnati con una linea tratteggiata in grassetto è stato assegnato un criterio IPSec.
  
[![](images/Dd536207.SGFG0404(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536207.sgfg0404_big(it-it,technet.10).gif)
  
**Figura 4.4 Percorsi di comunicazione normalmente consentiti per i gruppi di isolamento di base**
  
Nella seguente tabella sono riportati i percorsi di comunicazione consentiti per il traffico tra i gruppi di base, i sistemi non protetti e gli elenchi di esenzioni:
  
**Tabella 4.5: Opzioni di comunicazione consentite per i gruppi di isolamento di base**
  
<table style="width:100%;">  
<colgroup>  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Percorso</p></th>  
<th><p>Da</p></th>  
<th><p>Per</p></th>  
<th><p>Bidirezionale</p></th>  
<th><p>Prova IKE/IPSec</p></th>  
<th><p>Fallback</p></th>  
<th><p>Crittografa</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>1</p></td>
<td style="border:1px solid black;"><p>ID</p></td>
<td style="border:1px solid black;"><p>EX</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>2</p></td>
<td style="border:1px solid black;"><p>ID</p></td>
<td style="border:1px solid black;"><p>BO</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>3</p></td>
<td style="border:1px solid black;"><p>ID</p></td>
<td style="border:1px solid black;"><p>UN</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>4</p></td>
<td style="border:1px solid black;"><p>BO</p></td>
<td style="border:1px solid black;"><p>EX</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>5</p></td>
<td style="border:1px solid black;"><p>BO</p></td>
<td style="border:1px solid black;"><p>UN</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>6</p></td>
<td style="border:1px solid black;"><p>UN</p></td>
<td style="border:1px solid black;"><p>BO</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>7</p></td>
<td style="border:1px solid black;"><p>UN</p></td>
<td style="border:1px solid black;"><p>EX</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
</tbody>  
</table>
  
La tabella precedente contiene i requisiti di comunicazione per ogni percorso di comunicazione consentito nella configurazione dei gruppi di isolamento iniziale. Nell'elenco seguente viene spiegata ogni colonna:
  
-   **Percorso**. Il numero assegnato al percorso di comunicazione mostrato nel diagramma dei gruppi.
  
-   **Da**. Il gruppo contenente gli iniziatori del traffico.
  
-   **Da**. Il gruppo contenente i risponditori che saranno contattati attraverso il percorso di comunicazione consentito.
  
-   **Bidirezionale**. Indica se il percorso consente il capovolgimento dei ruoli dell'iniziatore e del risponditore in modo che il traffico possa iniziare sia dal gruppo **Da** che dal gruppo **A**.
  
-   **Prova IKE/IPSec**. Indica se questo percorso tenta di utilizzare IPSec per proteggere le comunicazioni.
  
-   **Fallback**. Indica se le comunicazioni possono tornare a non utilizzare IPSec (modalità non crittografata) nel caso in cui la negoziazione IKE non riesca.
  
-   **Crittografa**. Indica se questo percorso richiede la crittografia delle comunicazioni tramite un algoritmo di crittografia impostato nel criterio IPSec.
  
Nella tabella sono state utilizzate forme abbreviate dei nomi dei gruppi per ragioni di concisione. Se si utilizza questo formato per la documentazione, è possibile creare una rappresentazione molto concisa delle comunicazioni della soluzione di isolamento. Presumendo che tutto il traffico di rete sia disattivato a meno che non sia specificato diversamente, l'identificazione del traffico protetto dalla soluzione diventa un processo molto più semplice. Spiegazione per ciascuno dei percorsi consentiti riportati nell'esempio della figura precedente:
  
-   I percorsi del traffico 1, 4 e 7 mostrano le comunicazioni di rete che sono specificamente consentite a tutti gli host presenti negli elenchi di esenzioni in base ai criteri IPSec. Le esenzioni specifiche possono essere diverse a seconda dei gruppi di isolamento.
  
-   Il percorso del traffico 2 mostra le comunicazioni tra i gruppi Dominio di isolamento e Limite. Questo percorso tenta di utilizzare IPSec per proteggere il traffico. Il traffico può richiedere la crittografia, a seconda dei requisiti di protezione. Se la negoziazione IKE non ha esito positivo, le comunicazioni non potranno avvenire perché non vi è nessuna opzione di ritorno alla modalità non crittografata in caso di negoziazione IKE non riuscita.
  
-   Il percorso 3 mostra che gli host presenti nel dominio di isolamento possono avviare le comunicazioni con gli host non attendibili. Ciò è possibile perché il criterio per questo gruppo consente agli host del dominio di isolamento di utilizzare la modalità non crittografata se non vi è nessuna risposta alla richiesta di negoziazione IKE iniziale. I sistemi non attendibili che tentano di stabilire connessioni non protette da IPSec con gli host attendibili sono bloccate dai filtri in ingresso IPSec.
  
-   I percorsi del traffico 5 e 6 mostrano le comunicazioni consentite tra il gruppo Limite e i sistemi non attendibili. Il percorso 4 mostra che il gruppo Limite è autorizzato a comunicare in uscita con gli host non attendibili. Se la negoziazione IKE non riceve alcuna risposta, l'host comunicherà in modalità non crittografata. Il percorso 5 mostra le comunicazioni che sono state avviate dagli host non attendibili con il gruppo Limite. Benché questa freccia sembri simile a quella del percorso 4, i dettagli della tabella mostrano che gli host non attendibili non tentano una negoziazione IKE con il gruppo Limite. Stabiliscono infatti una comunicazione tramite connessioni TCP/IP in testo non crittografato.
  
Dopo aver documentato le comunicazioni di base, è possibile aggiungere gruppi al piano globale e registrare i relativi requisiti di comunicazione nello stesso modo. Ad esempio, la necessità di altri due gruppi nello scenario della Woodgrove Bank ha dato luogo al diagramma delle comunicazioni più complesso mostrato nella figura seguente.
  
[![](images/Dd536207.SGFG0405(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536207.sgfg0405_big(it-it,technet.10).gif)
  
**Figura 4.5 Percorsi di comunicazione consentiti dalla Woodgrove Bank per i gruppi di isolamento**
  
Nella seguente tabella sono riportati i percorsi di comunicazione consentiti per il traffico che avviene nei gruppi aggiuntivi dello scenario della Woodgrove Bank.
  
**Tabella 4.6: Opzioni di comunicazione consentite per i gruppi di isolamento aggiuntivi**
  
<table style="width:100%;">  
<colgroup>  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Percorso</p></th>  
<th><p>Da</p></th>  
<th><p>Per</p></th>  
<th><p>Bidirezionale</p></th>  
<th><p>Prova IKE/IPSec</p></th>  
<th><p>Fallback</p></th>  
<th><p>Crittografa</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>8</p></td>
<td style="border:1px solid black;"><p>EN</p></td>
<td style="border:1px solid black;"><p>EX</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>9</p></td>
<td style="border:1px solid black;"><p>EN</p></td>
<td style="border:1px solid black;"><p>ID</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>10</p></td>
<td style="border:1px solid black;"><p>EN</p></td>
<td style="border:1px solid black;"><p>NC</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>11</p></td>
<td style="border:1px solid black;"><p>EN</p></td>
<td style="border:1px solid black;"><p>BO</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>12</p></td>
<td style="border:1px solid black;"><p>NF</p></td>
<td style="border:1px solid black;"><p>ID</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>13</p></td>
<td style="border:1px solid black;"><p>NF</p></td>
<td style="border:1px solid black;"><p>EX</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>14</p></td>
<td style="border:1px solid black;"><p>NF</p></td>
<td style="border:1px solid black;"><p>BO</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
</tbody>  
</table>
  
Spiegazione per ciascuno dei percorsi consentiti aggiuntivi riportati nell'esempio della figura precedente e descritti nella tabella precedente:
  
-   I percorsi 8 e 13 rappresentano comunicazioni in testo non crittografato per tutto il traffico esentato.
  
-   I percorsi 9 e 10 mostrano le comunicazioni con crittografia IPSec ESP (Encapsulating Security Payload) richieste tra i gruppi Crittografia, Nessun fallback e Dominio di isolamento. Se la negoziazione IKE non riesce a proteggere la comunicazione tramite crittografia, il tentativo di stabilire tale comunicazione non va a buon fine.
  
-   Il traffico per il percorso 11 è leggermente diverso perché consente che le comunicazioni con il gruppo Limite siano avviate solo dal gruppo Crittografia e non il contrario. Questo perché la Woodgrove Bank ha inserito dati ad alto valore nel gruppo Crittografia e non desidera che tali dati siano esposti ai computer a cui possono accedere direttamente le risorse non attendibili.
  
-   I percorsi del traffico 12 e 14 possono essere implementati dalla modalità di trasporto IPSec AH o IPSec ESP, che è autenticata ma non crittografata (ESP nullo).
  
Come mostrato nell'esempio, l'aggiunta di gruppi può avere un impatto esponenziale sulla complessità della soluzione di isolamento. Per questo motivo, si consiglia di mantenere al minimo il numero di gruppi, specialmente durante le prime fasi dell'implementazione, durante le quali viene introdotta la maggior parte dei cambiamenti.
  
#### Assegnazione dell'appartenenza ai gruppi di computer e ai gruppi di accesso alla rete (NAG)
  
Dopo aver individuato e documentato i requisiti di traffico per il progetto, è necessario stabilire quali host dovranno appartenere a quale gruppo di computer o NAG.
  
Come esplicitato in precedenza, i gruppi di computer sono utilizzati nella soluzione di isolamento per applicare il GPO contenente il criterio IPSec associato. Dopo aver stabilito che un computer deve appartenere a un determinato gruppo di isolamento, l'account del computer viene aggiunto al gruppo di computer per quel gruppo di isolamento. Per il dominio di isolamento questo passaggio non è necessario, perché tutti i computer del dominio appartengono implicitamente al gruppo di computer del dominio di isolamento.
  
L'appartenenza a un NAG si basa sull'autorizzazione in ingresso implementata da quel NAG. Ad esempio, se un NAG esiste per limitare le comunicazioni di un determinato server a un insieme di client noto, gli account computer dei client devono essere inseriti nel NAG appropriato. I NAG sono creati solo quando è necessario e non hanno perciò una configurazione predefinita.
  
##### Appartenenza ai gruppi di computer
  
È importante tenere presente che un host non può essere inserito in più gruppi di computer, perché il gruppo di computer serve a controllare quale GPO va applicato. Benché in teoria sia possibile modificare i criteri per consentire a un host di appartenere a più gruppi di computer, la complessità di tale metodo renderebbe ben presto impossibile supportare la soluzione di isolamento.
  
In genere, la determinazione dell'appartenenza a un gruppo di computer non è un'operazione complicata, ma può richiedere molto tempo. Si consiglia di utilizzare le informazioni ricavate da un controllo come quello effettuato nel capitolo 3, "Determinazione dello stato corrente dell'infrastruttura IT", per inserire ogni host in un gruppo di computer in base al gruppo di isolamento a cui appartiene. È possibile documentare questo inserimento aggiungendo una colonna Gruppo al fine di registrare l'appartenenza a quel gruppo di computer per la configurazione finale, come mostrato nella tabella seguente:
  
**Tabella 4.7: Dati di raccolta sugli host di esempio**
  
<table style="width:100%;">  
<colgroup>  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
<col width="14%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome host</p></th>  
<th><p>Req. hardware soddisfatti?</p></th>  
<th><p>Req. software soddisfatti?</p></th>  
<th><p>Configurazione necessaria</p></th>  
<th><p>Dettagli</p></th>  
<th><p>Costo previsto</p></th>  
<th><p>Gruppo</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>HOST-NYC-001</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Aggiornamento hardware e software</p></td>
<td style="border:1px solid black;"><p>Il sistema operativo corrente è Windows NT 4.0. Hardware obsoleto non compatibile con Windows XP.</p></td>
<td style="border:1px solid black;"><p>€XXX.</p></td>
<td style="border:1px solid black;"><p>ID</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>SERVER-LON-001</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Inserimento in dominio attendibile, aggiornamento da NT 4 a Windows 2000 o versioni successive</p></td>
<td style="border:1px solid black;"><p>Software antivirus assente.</p></td>
<td style="border:1px solid black;"><p>€XXX.</p></td>
<td style="border:1px solid black;"><p>EN</p></td>
</tr>  
</tbody>  
</table>
  
##### Appartenenza ai gruppi di accesso alla rete (NAG)
  
Il passaggio finale di questo processo di progettazione consiste nel definire l'appartenenza ai NAG identificati in precedenza nel presente capitolo. Anche se un host attendibile deve appartenere a un solo gruppo di computer, può far parte di più NAG. Si consiglia però di utilizzare il minor numero possibile di NAG per limitare la complessità della soluzione di isolamento.
  
Quando si assegna l'appartenenza a un NAG per gli account utente, stabilire a che livello si desidera controllare l'accesso. Per garantire il corretto livello di controllo per una risorsa che utilizza già autorizzazioni standard per condivisioni e file, il modo più semplice di definire l'appartenenza è quello di assegnare l'appartenenza dei NAG utente a Utenti dominio per ciascun dominio attendibile dell'insieme di strutture che richiede accesso alla risorsa. Questo metodo ripristina praticamente il comportamento del valore predefinito originale di Utenti autenticati, ma non include gli account utente locali. Se è necessario un servizio o utente locale, l'utilizzo di un GPO basato sul dominio può non essere il modo migliore per configurare i diritti di accesso alla rete CONSENTI e NEGA. L'assegnazione dei diritti utente CONSENTI e NEGA non unisce le impostazioni dei diversi GPO. A questo computer deve pertanto essere impedito di avere un GPO basato sul dominio associato a CONSENTI e NEGA e il computer deve utilizzare un GPO locale personalizzato. Se il GPO basato sul dominio che fornisce l'assegnazione dei criteri IPSec è diverso dal GPO utilizzato per fornire i diritti di accesso alla rete, è comunque possibile utilizzare il GPO basato sul dominio per l'assegnazione dei criteri IPSec.
  
Stabilire inoltre come si desidera implementare i requisiti di accesso in ingresso utilizzando un NAG di tipo CONSENTI o di tipo NEGA o entrambi. La decisione sul tipo di NAG da creare deve basarsi unicamente sul comportamento che si intende ottenere e su ciò che riduce al minimo gli sforzi amministrativi. Può essere utile avere un NAG di tipo NEGA preesistente ma vuoto per gli utenti e un NAG di tipo NEGA per i computer già associati al diritto "Nega accesso al computer dalla rete" nel GPO.
  
Negli scenari ad alta protezione, l'appartenenza ai NAG utente può essere assegnata a utenti o gruppi specifici. Se si sceglie questo metodo, occorre comprendere che gli utenti che non fanno parte di questo gruppo non potranno accedere al computer sulla rete, anche se sono membri del gruppo degli amministratori locali e hanno il controllo completo sulle autorizzazioni per condivisioni e file.
  
Nello scenario della Woodgrove Bank, l'appartenenza a NAG\_EncryptedResourceAccess\_Users è stata assegnata a Utenti dominio e registrata come indicato nella tabella seguente:
  
**Tabella 4.8: Gruppi di accesso alla rete della Woodgrove Bank con appartenenza assegnata**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome NAG</p></th>  
<th><p>Appartenenza</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>ANAG_EncryptedResourceAccess_Users</p></td>
<td style="border:1px solid black;"><p>User7</p></td>
<td style="border:1px solid black;"><p>Questo gruppo è per tutti gli utenti che sono autorizzati a stabilire connessioni in ingresso protette da IPSec con i computer del gruppo di isolamento Crittografia.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>ANAG_EncryptedResourceAccess_Computers</p></td>
<td style="border:1px solid black;"><p>IPS-SQL-DFS-01<br />
IPS-SQL-DFS-02</p>
<p>IPS-ST-XP-05</p></td>
<td style="border:1px solid black;"><p>Questo gruppo contiene tutti i computer che sono autorizzati a stabilire connessioni in ingresso protette da IPSec con i computer del gruppo di isolamento Crittografia.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>DNAG_EncryptionIG_Computers</p></td>
<td style="border:1px solid black;"><p>CG_BoundaryIG_Computers</p></td>
<td style="border:1px solid black;"><p>Questo gruppo contiene tutti i computer che <em>non</em> sono autorizzati a stabilire connessioni in ingresso protette da IPSec con i computer del gruppo di isolamento Crittografia.</p></td>
</tr>  
</tbody>  
</table>
  
**Nota**: l'appartenenza a un NAG non controlla il livello della protezione del traffico con IPSec. Le impostazioni dei criteri IPSec controllano i metodi di protezione utilizzati per proteggere il traffico e sono indipendenti dall'identità autenticata da IKE. La negoziazione IKE rileva solo se l'identità del computer Kerberos ha superato o meno il processo di autenticazione. Non può implementare un criterio di tipo "crittografa se user3 si connette" o "crittografa se host attendibile IPS-SQL-DFS-01 o IPS-SQL-DFS-02". L'amministratore deve ottenere il comportamento desiderato utilizzando un criterio IPSec per i server del gruppo di isolamento Crittografia che richieda la crittografia per qualsiasi connessione in ingresso degli host attendibili e per qualsiasi connessione in uscita verso un host attendibile.
  
Fino ad ora, il processo di progettazione non ha comportato l'esame dettagliato della configurazione dei criteri IPSec. Nel capitolo 5 vengono forniti i dettagli sulla configurazione dei criteri IPSec per la Woodgrove Bank.
  
A questo punto del processo di progettazione, sono state completate le attività necessarie a trasformare i requisiti in una bozza di progetto. In questa sezione sono stati sviluppati sia il progetto che la documentazione che serviranno a creare i criteri IPSec.
  
##### Limiti che possono influire sulla configurazione
  
I seguenti problemi possono influire sulla configurazione e devono quindi essere presi in considerazione prima che la configurazione possa considerarsi completa:
  
-   **Numero massimo di connessioni simultanee tra host univoci e server tramite IPSec**. Il numero di connessioni simultanee è un fattore fondamentale da considerare per stabilire se un'implementazione IPSec su server ad alto utilizzo funzionerà senza problemi o sovraccaricherà la CPU a causa dell'elaborazione di IKE o IPSec. Ogni negoziazione IKE riuscita definisce associazioni di protezione (SA) che occupano circa 5 kilobyte di memoria in modalità utente. Le risorse della CPU sono necessarie per mantenere gli stati correnti delle SA IKE con tutti i peer connessi contemporaneamente. Per ulteriori informazioni sulla scalabilità, consultare il white paper "[Improving Security with Domain Isolation: Microsoft IT implements IP Security (IPsec)](http://www.microsoft.com/technet/itsolutions/msit/security/ipsecdomisolwp.mspx)" all'indirizzo www.microsoft.com/technet/itsolutions/msit/security/ipsecdomisolwp.mspx (in lingua inglese).
  
-   **Limite massimo della dimensione del token Kerberos per gli host che utilizzano IPSec**. Esiste un limite pratico di circa 1.000 gruppi per utente e se questo valore viene superato, l'applicazione dei GPO potrebbe non riuscire. Per ulteriori informazioni in merito, vedere l'articolo della Microsoft Knowledge Base 327825 "[New Resolution for Problems That Occur When Users Belong to Many Groups](http://support.microsoft.com/?kbid=327825)", disponibile all'indirizzo http://support.microsoft.com/?kbid=327825, e l'articolo 306259 "[Members of an Extremely Large Number of Groups Cannot Log On to the Domain](http://support.microsoft.com/?kbid=306259)", disponibile all'indirizzo http://support.microsoft.com/?kbid=306259 (entrambi in lingua inglese).
  
    Benché questi articoli si riferiscano specificamente agli utenti, il problema esiste anche per gli account di computer, perché Kerberos MaxTokenSize viene applicato anche agli account di computer. Anche se raramente, questo limite viene raggiunto nella maggior parte delle implementazioni ed è necessario tenere presente questo problema nel caso in cui si decida di inserire un computer (ad esempio un client) in molti NAG.
  
Se il progetto presenta questi problemi, sarà necessario rivedere il processo di progettazione per risolverli. Ad esempio, si potrebbe risolvere il problema del numero massimo di connessioni simultanee spostando un server estremamente carico negli elenchi delle esenzioni. Si potrebbe risolvere il problema della dimensione massima del token Kerberos riducendo il numero di NAG utilizzati nel progetto.
  
Se questi limiti non influiscono sul progetto, l'operazione successiva consiste nel decidere come implementare il progetto nell'organizzazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Metodi di implementazione dei gruppi
  
Dopo aver creato il progetto iniziale, è necessario esaminare attentamente il processo di implementazione di IPSec. Solo negli ambienti di piccole dimensioni è possibile distribuire i criteri con semplicità in tutti i computer e aspettarsi che IPSec funzioni correttamente con un impatto relativamente ridotto sugli utenti.
  
Nelle grandi organizzazioni, la complessità e i rischi dell'operazione richiedono una strategia di implementazione per fasi graduali. Utilizzando tale metodo, l'organizzazione può ridurre i rischi associati a un cambiamento così radicale nell'ambiente. Senza un'attenta pianificazione, le chiamate all'help desk e una produttività ridotta faranno aumentare rapidamente i costi dell'implementazione.
  
Vi sono molti metodi per implementare IPSec in un'organizzazione. Alcuni degli elementi che consentono di decidere quale metodo di implementazione adottare includono:
  
-   Gli stati di inizio e di fine dell'ambiente.
  
-   La complessità della configurazione dei gruppi.
  
-   La complessità della struttura dei domini.
  
-   La tolleranza ai rischi dell'organizzazione.
  
-   I requisiti di protezione.
  
I seguenti metodi di implementazione non sono completi ma forniscono esempi dei possibili approcci da adottare. È anche possibile utilizzare una combinazione di questi metodi. In generale, le organizzazioni non devono implementare criteri IPSec che limitino o blocchino le comunicazioni all'inizio per garantire che vi sia abbastanza tempo per risolvere i problemi e ridurre il coordinamento della gestione per gli ambienti complessi.
  
Indipendentemente dal metodo utilizzato per implementare IPSec, si consiglia vivamente di testare in modo esauriente lo scenario di implementazione in un ambiente di laboratorio, compresi la sequenza specifica e i tempi dei passaggi di distribuzione graduale e modifica dei criteri. Utilizzare inoltre un'operazione filtro che richieda la funzionalità IPSec ma accetti le comunicazioni in testo non crittografato mediante la modalità non crittografata. Questo metodo consentirà di ridurre al minimo l'impatto della distribuzione iniziale. Al termine della distribuzione graduale, provare a utilizzare modalità di funzionamento più sicure che richiedono la protezione del traffico con IPSec.
  
Per l'implementazione in un ambiente di produzione, si consiglia vivamente l'utilizzo di un progetto pilota per ogni fase significativa della distribuzione graduale. È particolarmente importante analizzare l'impatto delle modifiche dei criteri IPSec, perché queste diventeranno effettive nell'ambiente di produzione a seconda della durata dei ticket Kerberos, degli intervalli di polling dei Criteri di gruppo e degli intervalli di polling dei criteri IPSec. È necessario adottare un processo di controllo formale delle modifiche con strategie e criteri di ripristino graduali per assicurare che tutte le organizzazioni IT interessate siano consapevoli di ogni modifica e del suo impatto e sappiano come coordinare la raccolta dei suggerimenti per i responsabili dei processi decisionali.
  
#### Implementazione per gruppo
  
Il metodo di implementazione per gruppo utilizza criteri IPSec già definiti ma ne controlla l'applicazione mediante l'utilizzo dei gruppi e degli ACL nei GPO che forniscono tali criteri.
  
Nel metodo di implementazione per gruppo, i criteri IPSec sono creati in Active Directory nella loro configurazione definitiva. Ogni criterio IPSec ha tutte le esenzioni e le subnet protette definite, oltre alle operazioni filtro appropriate attivate.
  
Gli amministratori dei criteri IPSec creano quindi i GPO per ogni criterio IPSec. Nel dominio vengono inoltre creati gruppi di computer per gestire e applicare questi nuovi GPO. Gli ACL dei GPO vengono modificati in modo che i membri di Utenti autenticati non abbiano più il diritto "Applica". Anche ai gruppi di utenti/amministratori appropriati vengono concessi i diritti di accesso al GPO per gestire e applicare i criteri.
  
Successivamente, i criteri IPSec appropriati vengono assegnati al GPO corrispondente. Il GPO viene poi collegato con l'oggetto appropriato in Active Directory. A questo punto nessun computer dell'ambiente può ricevere il criterio, perché gli ACL che controllano l'assegnazione del GPO (la capacità di leggere il GPO) sono vuoti.
  
Da ultimo vengono identificati i computer che riceveranno i criteri e i loro account computer vengono inseriti nei gruppi di computer appropriati con accesso in lettura al GPO. Una volta aggiornati i ticket Kerberos del computer con le informazioni di appartenenza al gruppo, il GPO, assieme al criterio IPSec corrispondente, verrà applicato all'intervallo di polling successivo di Criteri di gruppo.
  
**Nota**: gli ACL che impongono ai computer del dominio restrizioni di lettura degli oggetti criteri IPSec o dei contenitori criteri IPSec in Active Directory *non* sono consigliati.
  
Si consideri un'organizzazione che abbia due criteri IPSec già definiti, IPSec Standard e IPSec Crittografia. IPSec Standard è il criterio predefinito che richiede l'utilizzo di IPSec per il traffico in ingresso ma che consente ai sistemi il fallback alla modalità non crittografata se iniziano una comunicazione con un computer senza IPSec. Il criterio IPSec Crittografia richiede che vengano sempre negoziate comunicazioni crittografate con IPSec.
  
In questo esempio, il personale amministrativo dell'organizzazione crea due GPO in Active Directory, un GPO IPSec Standard e un GPO IPSec Crittografia, e identifica inoltre i gruppi riportati nella tabella seguente:
  
**Tabella 4.9: Gruppi di amministrazione IPSec**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome gruppo</p></th>  
<th><p>Tipo di gruppo</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPsecSTD</p></td>
<td style="border:1px solid black;"><p>Universale</p></td>
<td style="border:1px solid black;"><p>Controlla l'applicazione del criterio IPSec Standard</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPsecENC</p></td>
<td style="border:1px solid black;"><p>Universale</p></td>
<td style="border:1px solid black;"><p>Controlla l'applicazione del criterio IPSec Crittografia</p></td>
</tr>  
</tbody>  
</table>
  
Gli ACL dei due nuovi GPO vengono aggiornati in modo che non vengano automaticamente applicati al gruppo Utenti autenticati per far sì che i gruppi di applicazioni e di gestione appropriati ricevano i diritti corretti. Il personale amministrativo ha modificato gli ACL per i due GPO in base alle informazioni riportate nella tabella seguente:
  
**Tabella 4.10: Diritti dei gruppi nei GPO**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Gruppo</p></th>  
<th><p>GPO IPSec Standard</p></th>  
<th><p>GPO IPSec Crittografia</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Utenti autenticati</p></td>
<td style="border:1px solid black;"><p>Lettura</p></td>
<td style="border:1px solid black;"><p>Lettura</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPsecENC</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Lettura</p>
<p>Applica criteri di gruppo</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>IPsecSTD</p></td>
<td style="border:1px solid black;"><p>Lettura</p>
<p>Applica criteri di gruppo</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
</tr>  
</tbody>  
</table>
  
**Nota:** questa tabella mostra solo le autorizzazioni aggiunte o modificate. Esistono probabilmente anche altri gruppi con autorizzazioni.
  
Gli amministratori hanno collegato i due GPO al dominio in Active Directory. Questo metodo fa sì che il criterio verrà applicato a tutti i computer del dominio senza cambiarne la posizione (a meno che il computer non risieda in un'unità organizzativa che blocca i criteri).
  
Man mano che i computer vengono identificati, gli account computer vengono aggiunti al gruppo IPsecSTD o IPsecEnc. Dopo un certo periodo di tempo, il criterio IPSec corrispondente verrà applicato e sarà effettivo.
  
Questo metodo richiede un'attenta pianificazione per evitare l'interruzione delle comunicazioni. Ad esempio, se un server è stato inserito nel gruppo IPsecEnc, ma più client che dipendono da quel server non hanno potuto negoziare IPSec, le comunicazioni tra questi client e server verranno interrotte.
  
#### Implementazione per creazione graduale dei criteri
  
Questo metodo di implementazione utilizza una tecnica in cui i criteri IPSec possono essere creati partendo da zero durante l'implementazione. Il vantaggio di questo metodo è che IPSec viene negoziato solo per una percentuale minima del traffico TCP/IP totale, invece che per tutte le subnet interne come avviene nel metodo di implementazione per gruppo. Questo metodo consente inoltre di testare tutti i percorsi nella rete interna fino alla subnet di destinazione per verificare che la negoziazione IKE e il traffico protetto con IPSec non abbiano problemi di attraversamento della rete. Un altro vantaggio è rappresentato dal fatto che l'intervallo di polling per IPSec può fornire più rapidamente gli aggiornamenti dei criteri IPSec (compreso il ripristino) invece di dover dipendere dalle modifiche all'appartenenza ai gruppi nel ticket di concessione ticket (TGT, Ticket-Granting Ticket) Kerberos o nei ticket di servizio. Lo svantaggio di questo metodo è che viene applicato a tutti i computer del dominio o gruppo di isolamento, non a computer specifici come avviene nel metodo di implementazione per gruppo. Inoltre, tutti i computer avranno un ritardo di tre secondi prima di utilizzare la modalità non crittografata a un certo punto della comunicazione con le subnet specificate.
  
In questo metodo di implementazione, i criteri IPSec includono eccezioni solo all'inizio; non esistono regole di negoziazione della protezione nei criteri IPSec per i computer. Il metodo esegue dapprima dei test e verifica che siano stati eliminati tutti i criteri IPSec locali esistenti in precedenza e ancora in uso. Il team di amministrazione deve essere in grado di identificare in anticipo gli host che utilizzavano criteri IPSec definiti localmente per gestire questi sistemi con un processo speciale. Se un criterio IPSec locale viene ignorato da un criterio di dominio, ciò potrebbe provocare interruzioni nelle comunicazioni e la perdita di protezione per i computer interessati. Diversamente dai criteri locali che vengono sovrascritti dall'applicazione dei criteri di dominio, i criteri persistenti in Windows Server 2003 vengono uniti al risultato dell'applicazione dei criteri di dominio. In questo caso, può sembrare che un sistema contenente un criterio persistente funzioni, ma la configurazione del criterio persistente può modificare il comportamento o addirittura ridurre la protezione fornita dai criteri di dominio oppure può interrompere le comunicazioni in seguito all'inserimento nel criterio di regole per le subnet protette.
  
Successivamente, è possibile creare una regola di protezione con un filtro che agisca su una sola subnet nella rete dell'organizzazione, ad esempio "Da qualsiasi indirizzo IP a subnet A tutto il traffico, negozia". Questa regola deve avere un'operazione filtro per accettare il testo non crittografato in ingresso e avviare le negoziazioni per tutto il traffico in uscita dalla subnet con la modalità non crittografata attivata. Man mano che la distribuzione di questo criterio IPSec in tutti i domini diventa effettiva, le comunicazioni passeranno gradualmente dalle SA trasferibili alle normali associazioni di protezione IPSec per gli host attendibili solo in quella subnet. Tutte le negoziazioni IKE non riuscite verranno esaminate e risolte. Tutte le incompatibilità tra le applicazioni verranno identificate e risolte. IPSec proteggerà le comunicazioni tra gli host attendibili all'interno di quella subnet. Le comunicazioni con gli host attendibili al di fuori della subnet utilizzeranno la modalità non crittografata dopo tre secondi. Verranno poi aggiunte gradualmente altre subnet alla regola di protezione fino a ottenere lo stato definitivo del criterio.
  
Si consideri un'organizzazione che abbia un solo criterio IPSec definito, denominato IPSec Standard, che richiede la negoziazione IPSec ma ricorre al testo non crittografato se questa fallisce. Il criterio viene creato in Active Directory e contiene solo regole di esenzione.
  
Il GPO IPSec Standard viene creato e collegato in modo che venga applicato a tutti i computer dell'ambiente. Il criterio IPSec Standard viene poi assegnato al nuovo GPO.
  
Da ultimo, a tutti i computer verrà assegnato il criterio IPSec. Qualsiasi problema causato dai criteri IPSec locali non passerà inosservato perché questo criterio di dominio sovrascriverà i criteri locali esistenti. I problemi saranno risolti su base continuativa finché tutte le subnet non saranno contenute nell'elenco dei filtri per le subnet protette.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Implementazione dei gruppi per la Woodgrove Bank
  
Woodgrove Bank ha scelto di implementare la distribuzione nell'ambiente di produzione spostando tutti i computer nel gruppo di isolamento Limite secondo il metodo per creazione graduale dei criteri. In questo modo, gli amministratori hanno potuto agire con cautela e risolvere i problemi principali senza che ciò influisse in modo significativo sulla comunicazione tra sistemi. La distribuzione dei criteri senza il ricorso a subnet protette ha consentito al team amministrativo di individuare tutti i sistemi a cui era stato assegnato un criterio IPsec locale e di tenere conto di tale informazione ai fini di valutazioni successive. Con l'aggiunta delle subnet al criterio, gli eventuali conflitti individuati sono stati prontamente risolti.
  
Una volta assicurato il funzionamento dei computer associati al criterio del gruppo Limite, il team ha implementato i gruppi Dominio di isolamento, Nessun fallback e Crittografia. La distribuzione di questi gruppi è avvenuta utilizzando il metodo di implementazione per gruppo. Un insieme di computer è stato selezionato per il progetto pilota e aggiunto ai rispettivi gruppi di controllo dei nuovi criteri. I problemi sono stati risolti man mano che venivano individuati, e sono stati aggiunti altri computer fino al completamento di tutti i gruppi di isolamento.
  
Nella tabella seguente sono elencati i gruppi di computer, i NAG e i relativi membri dopo l'implementazione completa della soluzione di isolamento:
  
**Tabella 4.11: Appartenenza ai gruppi di computer e ai gruppi di accesso alla rete (NAG)**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Gruppo di computer o NAG</p></th>  
<th><p>Membri</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>CG_IsolationDomain_Computers</p></td>
<td style="border:1px solid black;"><p>Computer del dominio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>CG_BoundaryIG_Computers</p></td>
<td style="border:1px solid black;"><p>IPS-PRINTS-01</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>CG_NoFallbackIG_Computers</p></td>
<td style="border:1px solid black;"><p>IPS-LT-XP-01</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>CG_EncryptionIG_Computers</p></td>
<td style="border:1px solid black;"><p>IPS-SQL-DFS-01</p>
<p>IPS-SQL-DFS-02</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>ANAG_EncryptedResourceAccess_Users</p></td>
<td style="border:1px solid black;"><p>User7</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>ANAG_EncryptedResourceAccess_Computers</p></td>
<td style="border:1px solid black;"><p>IPS-SQL-DFS-01<br />
IPS-SQL-DFS-02</p>
<p>IPS-ST-XP-05</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>DNAG_EncryptionIG_Computers</p></td>
<td style="border:1px solid black;"><p>CG_BoundaryIG_Computers</p></td>
</tr>  
</tbody>  
</table>
  
Si osservi che il gruppo ANAG\_EncryptedResourceAccess\_Computers contiene i server che si trovano nel gruppo di isolamento Crittografia. In questo modo, i server potranno comunicare tra di loro e con altri dispositivi in base alle esigenze. Se tali comunicazioni non sono richieste per questi server, non aggiungere i server a questo gruppo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo capitolo è stato descritto il processo di progettazione di una soluzione di isolamento di server e domini. Le attività che sono state trattate in questa sede includono: individuazione dei gruppi di computer e NAG necessari, descrizione dei gruppi di isolamento di base, creazione di gruppi di isolamento aggiuntivi, completamento di un modello di traffico, assegnazione dei membri ai gruppi e pianificazione del metodo di distribuzione graduale dell'implementazione.
  
Nel capitolo è stata anche utilizzata l'implementazione di IPSec presso la Woodgrove Bank, un'organizzazione fittizia, per illustrare il processo di progettazione sul campo e provare la configurazione in ambienti di laboratorio Microsoft.
  
La progettazione dei gruppi è stata basata sui requisiti aziendali e sulle informazioni ottenute nei due precedenti capitoli e documentate nel foglio di lavoro **Business\_Requirements.xls** (disponibile nella cartella Strumenti e modelli). È stata inoltre eseguita una valutazione dell'impatto di IPSec sulla rete, un aspetto che è estremamente importante considerare.
  
Dopo aver letto il capitolo, l'utente dovrebbe avere informazioni sufficienti per iniziare a pianificare i gruppi di isolamento, documentare i requisiti di comunicazione tra questi gruppi e pianificare i criteri IPSec ad alto livello. Queste attività prepareranno l'utente alla lettura del capitolo 5, "Creazione dei criteri IPSec per i gruppi di isolamento".
  
#### Ulteriori informazioni
  
Questa sezione contiene collegamenti a informazioni aggiuntive che possono tornare utili durante l'implementazione della soluzione di isolamento.
  
##### IPsec
  
I collegamenti indicati di seguito offrono un'ampia gamma di informazioni su IPSec specifiche per Windows:
  
-   Il white paper "[Using Microsoft Windows IPSec to Help Secure an Internal Corporate Network Server](http://www.microsoft.com/downloads/details.aspx?familyid=a774012a-ac25-4a1d-8851-b7a09e3f1dc9&displaylang=en)" presenta il primo modello per l'utilizzo di IPSec per proteggere l'accesso di rete ai server interni che elaborano o memorizzano informazioni riservate. Il white paper è disponibile per il download all'indirizzo www.microsoft.com/downloads/  
    details.aspx?FamilyID=a774012a-ac25-4a1d-8851-b7a09e3f1dc9&displaylang=en (in lingua inglese).
  
-   L'implementazione di IPSec realizzata da Microsoft per proteggere tutti i membri di dominio è descritta nel caso di studio "[Improving Security with Domain Isolation: Microsoft IT implements IP Security (IPSec)](http://www.microsoft.com/technet/itsolutions/msit/security/ipsecdomisolwp.mspx)", disponibile all'indirizzo www.microsoft.com/technet/itsolutions/msit/  
    security/ipsecdomisolwp.mspx (in lingua inglese).
  
-   La pagina Microsoft Windows Server 2003 [IPsec](http://www.microsoft.com/windowsserver2003/technologies/networking/ipsec/default.mspx) è disponibile all'indirizzo www.microsoft.com/windowsserver2003/technologies/networking/ipsec/ (in lingua inglese).
  
##### Protezione
  
-   Il metodo di valutazione dei rischi di protezione Microsoft IT è documentato nel white paper "[IT Security at Microsoft Overview](http://www.microsoft.com/technet/itsolutions/msit/security/mssecbp.mspx)", disponibile all'indirizzo www.microsoft.com/technet/itsolutions/msit/security/mssecbp.mspx (in lingua inglese).
  
##### Windows Server 2003 con servizio Active Directory
  
Per ulteriori informazioni su Active Directory, consultare:
  
-   La pagina [Windows Server 2003 Active Directory](http://www.microsoft.com/windowsserver2003/technologies/directory/activedirectory/default.mspx), disponibile all'indirizzo www.microsoft.com/windowsserver2003/technologies/directory/activedirectory/ (in lingua inglese).
  
**Scarica la soluzione completa**
  
[Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=33947)
  
[](#mainsection)[Inizio pagina](#mainsection)
