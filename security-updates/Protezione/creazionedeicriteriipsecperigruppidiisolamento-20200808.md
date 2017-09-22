---
TOCTitle: Creazione dei criteri IPsec per i gruppi di isolamento
Title: Creazione dei criteri IPsec per i gruppi di isolamento
ms:assetid: '432179b2-850e-453e-92cb-017491462bf7'
ms:contentKeyID: 20200808
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536208(v=TechNet.10)'
---

Isolamento del server e del dominio tramite IPsec e criteri di gruppo
=====================================================================

### Capitolo 5: Creazione dei criteri IPsec per i gruppi di isolamento

Aggiornato : febbraio 16, 2005

Il presente capitolo si pone come obiettivo quello di fornire istruzioni per l'implementazione della configurazione di isolamento del server e del dominio. I capitoli precedenti illustrano il processo di progettazione e i concetti su cui si basano le istruzioni contenute in questo capitolo. È pertanto consigliabile leggere questi capitoli prima di procedere alla lettura del presente capitolo.

Questo capitolo fornisce indicazioni per l'implementazione dei requisiti di protezione dell'isolamento del dominio e dei gruppi di isolamento del server, il cui processo di configurazione è illustrato nel capitolo 4, "Progettazione e pianificazione dei gruppi di isolamento". Questi requisiti vengono implementati tramite una combinazione degli elementi seguenti:

-   Requisiti di accesso in ingresso e in uscita per il dominio di isolamento e i gruppi di isolamento:

    -   Criterio di protezione del protocollo Internet (IPsec) sviluppato specificatamente per il gruppo di isolamento, che richiede la negoziazione IKE (Internet Key Exchange) di IPsec per le connessioni in ingresso e in uscita

    -   Gruppi di protezione a livello di dominio, denominati gruppi di accesso alla rete, che consentono o negano l'accesso alla rete quando si utilizza il traffico protetto da IPsec

-   Requisiti di protezione del traffico di rete per il domino di isolamento e i gruppi di isolamento:

    -   Filtri dei criteri IPsec configurati per identificare il traffico che deve essere protetto

    -   Operazioni filtro IPsec che negoziano il livello di autenticazione richiesto e specificano la crittografia per il traffico identificato dal filtro

    -   Impostazioni delle operazioni filtro che controllano le condizioni per la comunicazione non crittografata, quando le connessioni in uscita vengono avviate da host attendibili

Queste istruzioni spiegano come predisporre la soluzione, utilizzando Criteri di gruppo e criteri IPsec nel servizio Active Directory® basato su Microsoft® Windows Server™ 2003 e come configurare i membri del dominio utilizzando Windows Server 2003 e Microsoft Windows® XP. Il presente capitolo illustra inoltre le alternative di configurazione e le opzioni di distribuzione. Alla fine del capitolo, sono inoltre riportati degli elenchi di controllo, che consentono di verificare se la configurazione risponde a tutti i requisiti aziendali e di protezione.

##### In questa pagina

[](#eeaa)[Prima di iniziare](#eeaa)
[](#edaa)[Creazione dei criteri IPsec in Active Directory](#edaa)
[](#ecaa)[Autorizzazione dell'accesso in ingresso a un gruppo di isolamento](#ecaa)
[](#ebaa)[Considerazioni aggiuntive su IPsec](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Prima di iniziare

Questa sezione contiene informazioni utili per valutare il grado di idoneità dell'organizzazione all'implementazione della soluzione IPsec. Il termine "idoneità" è inteso in senso logico più che organizzativo, in quanto le motivazioni aziendali che spingono un'azienda a implementare la presente soluzione sono illustrate nel capitolo 1, "Introduzione all'isolamento del server e del dominio", di questa guida.

#### Prima di iniziare

È necessario conoscere i concetti fondamentali del protocollo IPsec e in particolare dell'implementazione Microsoft di IPsec. È inoltre necessaria la conoscenza delle seguenti aree di Windows Server 2003:

-   Concetti relativi ad Active Directory, tra cui la struttura e gli strumenti di Active Directory, la gestione di utenti, gruppi e altri oggetti Active Directory e l’uso dei criteri di gruppo

-   La protezione dei sistemi Windows, inclusi concetti quali utenti, gruppi, controllo, elenchi di controllo dell'accesso (ACL, Access Control List), utilizzo dei modelli di protezione e applicazione dei modelli di protezione mediante Criteri di gruppo o strumenti della riga di comando.

-   Principi chiave delle connessioni in rete e del protocollo IPsec

Prima di proseguire con gli argomenti di questo capitolo, è necessario aver letto anche le istruzioni di pianificazione riportate nei capitoli precedenti della presente guida e conoscere a fondo l'architettura e la configurazione della soluzione. È inoltre necessario aver definito e documentato i requisiti aziendali della soluzione all'interno di una matrice dei requisiti della soluzione.

#### Prerequisiti organizzativi

È necessario consultarsi con altre persone dell'organizzazione che potrebbero essere coinvolte nell'implementazione della soluzione, fra le quali:

-   Finanziatori

-   Personale addetto alla protezione e al controllo

-   Personale addetto alla progettazione, amministrazione e gestione di Active Directory

-   Personale addetto alla progettazione, amministrazione e gestione di DNS (Domain Name System), server Web e della rete.

    **Nota:** a seconda della struttura dell'organizzazione IT, questi ruoli possono essere ricoperti da più persone oppure un numero ristretto di addetti può ricoprire più ruoli.

#### Prerequisiti per l'infrastruttura IT

Il presente capitolo presuppone inoltre l'esistenza della seguente infrastruttura IT:

-   Un dominio Active Directory basato su Microsoft Windows Server™ 2003 in modalità nativa o mista. Questa soluzione utilizza gruppi universali per l'applicazione dell'oggetto Criteri di gruppo (GPO, Group Policy Object). Se l'organizzazione non utilizza la modalità nativa o mista, è comunque possibile applicare l'oggetto Criteri di gruppo tramite l'uso di configurazioni di gruppo standard globali e locali. Tuttavia, poiché questa opzione è più complessa da gestire, la presente soluzione non la utilizza.

    **Nota**: Windows Server 2003 include numerosi miglioramenti relativi ai criteri IPsec. Nessun aspetto specifico della presente soluzione ne impedisce l'utilizzo con Windows 2000. Tuttavia, la soluzione è stata testata solo su un sistema Windows Server 2003 con servizio Active Directory.
    Per ulteriori informazioni sui miglioramenti apportati a IPsec in Windows Server 2003, consultare la pagina [New features for IPsec](http://technet.microsoft.com/en-us/library/cc739580.aspx) sul sito Web Microsoft all'indirizzo www.microsoft.com/resources/documentation/
    WindowsServ/2003/standard/proddocs/en-us/ipsec\_whatsnew.asp.

-   Licenze supporti di installazione e codici "Product Key" di Windows 2000 Server, Windows Server 2003 Standard Edition e Windows Server 2003 Enterprise Edition.

Il presente capitolo richiede inoltre una perfetta conoscenza dell'infrastruttura IT esistente, necessaria per garantire la corretta distribuzione dei criteri agli host desiderati dell'ambiente. Il capitolo 3, "Determinazione dello stato corrente dell'infrastruttura IT", illustra le informazioni necessarie e come acquisirle. I passaggi riportati in questo capitolo devono essere eseguiti soltanto se si dispone almeno delle informazioni seguenti:

-   Definizione dei gruppi di isolamento per la progettazione. Ciascuno dei gruppi di isolamento necessari deve includere una chiara descrizione, che indichi i requisiti di sicurezza e identifichi le risorse a cui si applicano questi requisiti (vale a dire, appartenenza al gruppo di isolamento).

-   Una descrizione generale delle modalità di utilizzo dei criteri IPsec per l'implementazione dei gruppi di isolamento, compreso un elenco dei diversi criteri IPsec necessari con i relativi metodi di assegnazione.

-   Un riepilogo generale dell'impatto derivante dall'applicazione di IPsec per l'implementazione dei gruppi di isolamento. Questo riepilogo potrebbe essere accompagnato da un elenco di problematiche e soluzioni.

-   Una descrizione generale del processo di modifica dei criteri IPsec nel tempo e un elenco delle procedure che richiedono la modifica dei criteri IPsec. Questo elenco deve includere procedure quali le risposte ai problemi di protezione, l'aggiunta di componenti di rete e l'aggiunta di client o server nel gruppo di isolamento.

-   Comprensione della topologia di rete dell'organizzazione e dello schema d'indirizzamento IP.

[](#mainsection)[Inizio pagina](#mainsection)

### Creazione dei criteri IPsec in Active Directory

Il processo di creazione dei criteri necessari per supportare i gruppi di isolamento previsti include le seguenti attività principali:

-   Creazione di elenchi filtri

-   Creazione di operazioni filtro

-   Creazione di criteri IPsec per l'implementazione dei gruppi di isolamento

Prima di procedere alla creazione di questi componenti, è importante ottenere i diagrammi dei modelli di traffico e le tabelle indicate nel capitolo 4 "Progettazione e pianificazione dei gruppi di isolamento", nonché le tabelle di mapping degli host e della rete. Queste tabelle forniscono le informazioni necessarie per creare criteri che eseguano le funzionalità previste e che vengano assegnati ai gruppi di isolamento corretti.

La figura seguente illustra la configurazione di rete utilizzata per simulare lo scenario della Woodgrove Bank.

[![](images/Dd536208.SGFG0501(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536208.sgfg0501_big(it-it,technet.10).gif)

**Figura 5.1. Configurazione di rete della Woodgrove Bank**

La configurazione del laboratorio di test della Woodgrove Bank dimostra le seguenti funzionalità chiave della soluzione:

-   Isolamento del dominio tramite gruppi di accesso alla rete che, quando si utilizza IPsec, impediscono la comunicazione con alcuni host specifici ad elevato rischio ma attendibili membri del dominio

-   Isolamento del server tramite gruppi di accesso alla rete, che consente di definire quali client degli host attendibili sono autorizzati a connettersi utilizzando IPsec

Inoltre, questo ambiente di prova dimostra le seguenti funzionalità di IPsec per Windows e testa la compatibilità con altre tecnologie di protezione che potrebbero essere adottate negli ambienti reali:

-   Compatibilità dei computer che eseguono Windows 2000 Service Pack (SP) 4 (con l'aggiornamento del NAT-T (Network Address Translation Traversal), Windows XP SP2 e Windows Server 2003 in qualità di controller di dominio.

-   Compatibilità di queste piattaforme, se protette utilizzando le forme di protezione avanzata consigliate nelle guide per la protezione di Microsoft Windows. Le mappe che indicano il traffico autorizzato e bloccato tramite i filtri IPsec non sono state inserite in questa soluzione perché i requisiti di protezione per l'isolamento sono diversi. Ulteriori ragioni motivano questa scelta, fra le quali quella di ridurre la complessità dei criteri IPsec per l'isolamento del server, oltre al fatto che in molti casi è più opportuno utilizzare Windows Firewall per i filtri di autorizzazione e blocco (indipendentemente dalla protezione end-to-end garantita da IPsec per ciascun pacchetto).

-   Capacità di proteggere server e traffico Web (HTTP), server SQL, file system distribuiti (DFS, Distributed File System), condivisioni di file e stampa, Microsoft Operations Manager (MOM) e Microsoft Systems Management Server (SMS).

-   Compatibilità del NAT-T ESP di IPsec mediante l'incapsulamento UDP-ESP per entrambe le condizioni seguenti:

    -   Accesso in uscita dai membri del dominio posizionati dietro al NAT mediante l'autenticazione Kerberos di IKE

    -   Accesso in ingresso a un membro del dominio posizionato dietro al NAT mediante l'autenticazione Kerberos di IKE

Lo scenario di prova illustrato nella figura 5.1 è stato utilizzato per testare il corretto funzionamento di tutti i gruppi di isolamento della soluzione. In totale, sono stati creati quattro criteri IPsec, successivamente assegnati ai gruppi di isolamento rappresentati con una linea tratteggiata in figura (vale a dire, il dominio di isolamento e i gruppi di isolamento Crittografia, Nessun fallback e Limite). Le sezioni seguenti illustrano il processo di creazione di questi criteri.

#### Panoramica dei componenti dei criteri IPsec

I criteri IPsec sono costituiti da vari componenti, che consentono di applicare i requisiti di protezione IPsec scelti dall'organizzazione. La figura seguente illustra i vari componenti di un criterio IPsec e le loro associazioni.

[![](images/Dd536208.SGFG0502(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536208.sgfg0502_big(it-it,technet.10).gif)

**Figura 5.2. Componenti dei criteri IPsec**

Un criterio IPsec funge da contenitore di una serie di regole, che specificano quale tipo di traffico di rete è consentito e in quali modalità. Ciascuna regola è costituita da un elenco di filtri e da un'operazione a esso associata. L'elenco dei filtri contiene un raggruppamento di filtri. Quando il traffico corrisponde a un filtro specifico, l'operazione filtro corrispondente viene avviata. Le regole definiscono inoltre quali metodi di autenticazione devono essere utilizzati fra gli host.

Il diagramma rappresenta i componenti in una struttura gerarchica, ma il modo più efficace per creare i criteri consiste nell'iniziare dai filtri e dagli elenchi filtri, poiché essi rappresentano i tasselli fondamentali che determinano quale traffico verrà protetto.

#### Elenchi filtri IPsec

Gli elenchi filtri IPsec sono gruppi di uno o più filtri, che vengono utilizzati per creare corrispondenze con il traffico di rete, sulla base dei criteri specificati per ciascun filtro. Ciascun filtro dell'elenco definisce:

-   Reti o indirizzi di origine e di destinazione

-   Protocolli

-   Porte TCP (Transmission Control Protocol) o UDP di origine e di destinazione

Gli elenchi filtri e le operazioni filtro sono stati concepiti per essere condivisi da vari criteri IPsec. Questo approccio consente di gestire un elenco di filtri per un certo tipo di esenzione e di utilizzarlo nel singolo criterio IPsec di ciascun gruppo di isolamento. Tuttavia, i filtri che costituiscono gli elenchi non possono essere condivisi con altri elenchi. Se due elenchi devono includere filtri identici, sarà necessario creare i filtri due volte, una per ciascun elenco.

L'amministratore IPsec dovrà evitare accuratamente di duplicare i filtri all'interno di un criterio poiché essi potrebbero essere associati a operazioni diverse. Il servizio IPsec potrebbe, infatti, modificare l'ordinamento dei filtri duplicati nell'elaborazione dei pacchetti e generare quindi risultati non coerenti. Se necessario, è possibile utilizzare filtri duplicati quando essi sono associati alla medesima operazione, ad esempio di autorizzazione o di blocco, e le prestazioni non vengono compromesse.

Le informazioni sulla rete acquisite nelle fasi precedenti sono utili per identificare i vari modelli di traffico che l'amministratore desidera proteggere. Inoltre, queste informazioni possono essere utilizzate per identificare il traffico che deve essere esentato dalle limitazioni di IPsec.

La tabella seguente riporta alcuni elenchi di base, potenzialmente utili per un'organizzazione tipo. A seconda dei requisiti aziendali dell'organizzazione e della configurazione della rete, potrebbero essere necessari altri elenchi filtri.

**Tabella 5.1. Elenchi filtri contenuti nella soluzione**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Elenco filtri</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Elenco subnet protette</p></td>
<td style="border:1px solid black;"><p>Include tutte le subnet dell'organizzazione che verranno protette tramite IPsec</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Elenco di esenzioni DNS</p></td>
<td style="border:1px solid black;"><p>Include gli indirizzi IP dei server DNS che saranno autorizzati a comunicare senza la protezione di IPsec</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Elenco di esenzioni controller di dominio</p></td>
<td style="border:1px solid black;"><p>Include gli indirizzi IP dei controller di dominio che saranno autorizzati a comunicare senza la protezione di IPsec</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Elenco di esenzioni WINS</p></td>
<td style="border:1px solid black;"><p>Include gli indirizzi IP dei server WINS (Windows Internet Naming Service) che saranno autorizzati a comunicare senza la protezione di IPsec</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>DHCP, traffico di negoziazione</p></td>
<td style="border:1px solid black;"><p>Include il filtro che autorizza il traffico di negoziazione DHCP (Dynamic Host Configuration Protocol) sulla porta UDP 68</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>ICMP, Tutto il traffico</p></td>
<td style="border:1px solid black;"><p>Include il filtro che consente il funzionamento del protocollo ICMP (Internet Control Message Protocol) all'interno dell'organizzazione per la risoluzione dei problemi</p></td>
</tr>  
</tbody>  
</table>
  
L'elenco delle subnet protette include tutte le subnet della rete interna dell'organizzazione. Questo elenco di filtri è associato a un'operazione filtro, che esegue le azioni previste per un gruppo di isolamento specifico. Questa operazione è quella più ampia per la protezione di tutto il traffico di rete della subnet specifica (ad esempio, la negoziazione IPsec), perché gli altri filtri, quali ad esempio quello per ICMP, sono più specifici e richiedono una diversa operazione (ad esempio, di autorizzazione). È importante ricordare che questo approccio implica che sulle subnet non devono essere presenti host non attendibili o non protetti da IPsec.
  
I filtri devono implementare i requisiti di protezione sia in ingresso che in uscita e, in fase di definizione, è necessario configurarli specularmente. La specularità assicura infatti la corrispondenza con il traffico quando vengono utilizzati indirizzi di origine e di destinazione esattamente opposti. Nella descrizione dei filtri, il simbolo "&lt;-&gt;" sta a indicare che il filtro è speculare. I filtri speculari devono essere utilizzati tutte le volte che l'operazione filtro negozia metodi di protezione per l'incapsulamento IPsec.
  
##### Indirizzi di origine e di destinazione
  
Ciascun filtro include le impostazioni sia per gli indirizzi di origine che per quelli di destinazione. Windows XP e Windows Server 2003 offrono maggiori opzioni per gli indirizzi rispetto a Windows 2000. Quando la piattaforma Windows 2000 fa parte del dominio, è quindi necessario utilizzare soltanto le impostazioni di Windows 2000. Le impostazioni di Windows 2000 sono le seguenti:
  
-   **Indirizzo IP**. Questa opzione è stata concepita affinché un criterio IPsec comune in Active Directory possa essere applicato a molti o a tutti i computer, indipendentemente dal fatto che utilizzino un indirizzo IP statico o assegnato da DHCP. Per l'assegnazione centralizzata dei criteri dal dominio, IPsec non supporta la configurazione di filtri per interfacce di rete fisiche, ma soltanto per il tipo di interfaccia (ad esempio, LAN o WAN), quali le interfacce di connessione remota o di rete privata virtuale (VPN). Utilizzando **Indirizzo IP**, i filtri generici dei criteri IPsec vengono copiati in un filtro specifico che contiene ciascun indirizzo IP utilizzato dal computer nel momento in cui il servizio IPsec si prepara ad applicare il criterio. Inoltre, il servizio IPsec rileva i cambiamenti di indirizzo o le nuove interfacce di rete, al fine di consentire la gestione del numero corretto di filtri. Se un computer è dotato di una scheda di rete con due indirizzi IP configurati, verranno creati due diversi filtri IPsec specifici che utilizzano i due diversi indirizzi IP.
  
-   **Qualsiasi indirizzo IP**. Questa opzione consente di stabilire corrispondenze fra i filtri IPsec e qualsiasi indirizzo IP.
  
-   **Nome DNS specifico**. Questa opzione fa sì che IPsec valuti l'indirizzo IP del nome DNS specificato e quindi crei i filtri utilizzando l'indirizzo o gli indirizzi IP specifici. Il risultato corrisponde a quello che si otterrebbe se l'amministratore immettesse gli indirizzi IP nei filtri. Durante la creazione del filtro iniziale, il nome DNS viene risolto e gli indirizzi IP corrispondenti inseriti nel filtro. Se nel server DNS è specificato un record errato della risorsa per il nome DNS incluso nel filtro, nel filtro verrà aggiunto l'indirizzo IP errato.
  
    **Nota**: il nome DNS non viene più valutato dopo la creazione iniziale dei filtri all'interno del criterio.
  
    L'opzione del nome DNS è utile quando è necessario creare numerosi filtri poiché il nome DNS corrisponde a molti indirizzi IP, quali, ad esempio, quelli di ciascun controller incluso nel dominio. Non esistono metodi automatici per creare filtri che vengano mantenuti aggiornati rispetto all'elenco degli indirizzi IP per un nome DNS specifico.
  
-   **Indirizzo IP specifico**. Questa opzione consente di creare corrispondenze fra il traffico e l'indirizzo IP incluso nel filtro.
  
-   **Subnet IP specifica**. Questa opzione consente di configurare una subnet specifica. Tutti gli indirizzi IP inclusi nella subnet specificata creeranno corrispondenze con il filtro. Questa opzione va gestita con cautela, in particolare se viene creata un'esenzione per una subnet poiché verranno così esentati anche gli utenti non affidabili che eseguono lo spoofing su un indirizzo IP dalla subnet.
  
    **Nota:** Windows XP e Windows Server 2003 sono stati migliorati e mettono a disposizione ulteriori opzioni per gli indirizzi, nonché altre opzioni supplementari. Se il medesimo criterio IPsec deve essere applicato a diverse piattaforme, l'amministratore dovrà accertarsi che nella configurazione dei criteri siano state utilizzate soltanto le opzioni di Windows 2000.
  
##### Protocolli
  
Oltre alla configurazione degli indirizzi di origine e di destinazione, ciascun filtro può essere configurato affinché crei una corrispondenza con un protocollo o una porta specifici. Per impostazione predefinita, il filtro crea una corrispondenza con tutti i protocolli e tutte le porte. Se fra i criteri del filtro viene selezionato un protocollo che supporti le porte, l'amministratore ha inoltre la possibilità di configurare le porte di origine e di destinazione.
  
##### Porte di origine e di destinazione
  
Nonostante sia possibile configurare i filtri per creare corrispondenze con porte TCP e UDP, in questa soluzione si sconsiglia di creare filtri specifici per le porte. Il filtraggio a livello di porta aumenta notevolmente il carico di lavoro e il livello di complessità della configurazione dei filtri IPsec e potrebbe richiedere un complesso coordinamento fra i criteri dei client e quelli dei server per il completamento della negoziazione di protezione IKE. Poiché questa soluzione presuppone che la comunicazione fra computer attendibili sia effettivamente di tipo trust, i filtri consentono che tutto il traffico (eccetto quello ICMP) venga protetto da IPsec. Se sull'host attendibile è necessario il filtraggio a livello di porta, consultare il file **Business\_Requirements.xls** in merito ai requisiti di protezione che vengono soddisfatti dalla combinazione di IPsec e firewall basato su host (ad esempio, Windows Firewall) posizionato sopra il livello IPsec.
  
Per risolvere numerosi dei problemi menzionati nell'appendice A riguardo al comportamento dei filtri quando si utilizza "Indirizzo IP", questa soluzione utilizza per lo scenario della Woodgrove Bank i filtri Qualsiasi &lt;-&gt; Subnet. Viene così creato un elenco filtri che include numerosi filtri di tipo Qualsiasi indirizzo IP &lt;-&gt; Subnet IP specifica, in cui sono esplicitamente elencate tutte le subnet dell'organizzazione. Questo approccio consente all'amministratore di definire le subnet specifiche che devono essere protette. Eventuale traffico non incluso nelle subnet specifiche non corrisponderà ad alcun filtro IPsec e verrà inviato come normale testo non crittografato all'host di destinazione.
  
Per ulteriori procedure consigliate per la configurazione dei filtri, consultare la sezione "Best Practices" del white paper "[Improving Security with Domain Isolation: Microsoft IT implements IP Security (IPsec)](http://www.microsoft.com/technet/itsolutions/msit/security/ipsecdomisolwp.mspx)" incluso in IT Showcase e disponibile su Microsoft TechNet all'indirizzo www.microsoft.com/technet/itsolutions/msit/  
security/ipsecdomisolwp.mspx (in lingua inglese).
  
##### Considerazioni sull'elenco di esenzioni
  
Una parte del traffico non può essere protetta da IPsec per ragioni aziendali, tecniche o di supporto. Inoltre, i computer che non eseguono sistemi operativi Windows potrebbero non supportare IPsec o rendere difficile la distribuzione di questo servizio. I computer che eseguono versioni precedenti di Windows, quali Microsoft Windows NT® versione 4.0, Windows 95 e Windows 98, non sono in grado di elaborare criteri IPsec basati su criteri di gruppo. Infine, i computer non gestiti che eseguono Windows 2000 o versioni successive possono partecipare alla negoziazione IPsec soltanto se il criterio viene distribuito manualmente ai singoli computer e se si utilizza un'autenticazione diversa dal protocollo Kerberos versione 5 (ad esempio, chiavi già condivise o certificati).
  
Inoltre, un computer che esegue Windows 2000 (o versioni successive) deve disporre della connettività di rete per ottenere i criteri IPsec dal dominio e quindi utilizzare IPsec. Attualmente, la connessione alla rete, l'individuazione di controller di dominio e il recupero dei criteri impone l'esenzione dei servizi di infrastruttura dalla protezione IPsec. Questi servizi includono quelli relativi ai nomi, quali DNS e WINS, e i controller di dominio stessi.
  
Oltre a questi servizi di infrastruttura, all'interno dell'organizzazione potrebbero esistere altri servizi che non supportano IPsec. Ad esempio, i thin client o altri client di bootstrap che devono scaricare immagini da Advanced Deployment Services (ADS) o da Remote Installation Services (RIS), non supportano IPsec. Se sulla rete sono presenti server che erogano questi servizi, è necessario analizzarli ed eventualmente inserirli nell'elenco di esenzioni o nel gruppo di isolamento Limite, affinché possano accettare le comunicazioni in rete da host che non sono in grado di utilizzare IPsec.
  
**Nota:** la decisione di includere i server che erogano servizi ADS, RIS o di altro tipo negli elenchi di esenzioni o nel gruppo di isolamento Limite si basa su fattori di rischio e facilità di gestione. In entrambi i casi, si dovrà testare accuratamente l'approccio scelto.
  
Se un client non può essere inserito nell'infrastruttura IPsec, ma per ragioni aziendali deve poter accedere a un server che utilizza IPsec, è necessario adottare un metodo che consenta di stabilire un percorso di comunicazione. Per controllare questi requisiti di traffico mediante delle autorizzazioni, la soluzione proposta in questa guida utilizza gli elenchi di esenzioni dei filtri. Gli elenchi di esenzioni sono stati inclusi nell'infrastruttura IPsec per consentire tutte le comunicazioni necessarie con gli host, anche se non è possibile utilizzare le negoziazioni IPsec.
  
Questi elenchi vengono utilizzati per escludere selettivamente il traffico che non deve rientrare nell'infrastruttura IPsec, consentendo quello che corrisponde ai filtri degli elenchi di esenzioni. Questi elenchi devono essere configurati con estrema cautela poiché scavalcano i meccanismi di protezione implementati da IPsec. Se, ad esempio, si inserisce un server protetto tramite crittografia (per la protezione di informazioni proprietarie) in un elenco di esenzioni, si consentirà ai computer guest di comunicare direttamente con il server stesso senza utilizzare IPsec.
  
Così come gli elenchi filtri, anche gli elenchi di esenzioni consentono di contenere le dimensioni dell'elenco e di facilitare la configurazione dell'interfaccia utente (IU). È possibile, ad esempio, creare un elenco che contenga i filtri per tutti i controller di dominio o per i controller di dominio di ciascun dominio. Un secondo vantaggio derivante dall'utilizzo di numerosi elenchi filtri è dato dal fatto che la regola di autorizzazione può essere attivata e disattivata facilmente nel criterio IPsec per ciascun elenco di filtri.
  
Quando si configura una regola per implementare l'esenzione nel criterio IPsec, si deve fare in modo che il traffico autorizzato e non protetto da IPsec sia minimo. Si dovranno però accettare compromessi in termini di complessità e dimensioni del criterio IPsec rispetto alla protezione che si ottiene utilizzando filtri più specifici. Si noti che *tutti* gli indirizzi IP dei controller di dominio inclusi in tutti gli insiemi di strutture attendibili devono essere esentati affinché i client del dominio o dell'insieme di strutture possano ottenere i ticket Kerberos per i server di un altro dominio o insieme di strutture non attendibili. Il client Windows Kerberos utilizza il traffico ICMP, Lightweight Directory Access Protocol (LDAP) UDP 389 e Kerberos UDP 88 e TCP 88 sia verso i propri controller di dominio che i controller di altri domini. I membri del dominio utilizzano altri tipi di traffico con i relativi controller del dominio a cui appartengono, quali ad esempio SMB (Server Message Block) TCP 445, RPC (Remote Procedure Call) e LDAP TCP 389. Nel caso in cui i requisiti di sicurezza non siano particolarmente severi, l'esenzione viene implementata per "tutto il traffico" sugli indirizzi IP dei controller di dominio al fine di semplificare la configurazione e ridurre il numero di filtri.
  
Si potrebbe essere tentati dall'esentare il traffico di un'applicazione specifica tramite la porta invece che tramite l'indirizzo di destinazione, evitando così di dover gestire un elenco di indirizzi, ad esempio Telnet in uscita che utilizza la porta TCP 23 per accedere ai sistemi UNIX. Si consideri, ad esempio, la seguente esenzione in uscita:
  
    Da Indirizzo IP a Qualsiasi indirizzo IP, TCP, da qualsiasi porta alla porta di destinazione 23, speculare
  
Il corrispondente filtro in ingresso sarà:
  
    Da Qualsiasi indirizzo IP a Indirizzo IP, TCP, dalla porta di origine 23 a qualsiasi porta di destinazione
  
Questo filtro in ingresso consentirà di rispondere alle richieste di connessione da Telnet, ma consentirà anche a un pirata informatico di scavalcare i requisiti dell'autenticazione IPsec e di accedere a qualsiasi porta aperta dell'host. Prima di utilizzare questa configurazione del filtro, le organizzazioni dovranno quindi valutare attentamente il rischio di questi potenziali attacchi. Tale rischio viene certamente ridotto al minimo se si specifica l'indirizzo IP di destinazione. Questa stessa situazione può presentarsi se non si disattiva l'esenzione predefinita per il protocollo di autenticazione Kerberos. Per una trattazione dettagliata della configurazione e dell'impatto sulla protezione delle esenzioni predefinite, consultare gli articoli della Microsoft Knowledge Base [811832](http://support.microsoft.com/?kbid=811832) all'indirizzo http://support.microsoft.com/?kbid=811832 (in lingua inglese) e [810207](http://support.microsoft.com/?kbid=810207) all'indirizzo http://support.microsoft.com/?kbid=810207. I criteri IPsec devono essere configurati presupponendo che non sia attivata alcuna esenzione predefinita.
  
Inserendo gli indirizzi dei sistemi in un elenco di esenzioni, si evita efficacemente che questi sistemi partecipino come host IPsec per tutti i criteri IPsec che implementano l'elenco di esenzioni. Poiché la maggior parte dei client dell'organizzazione (inclusi i client guest) deve accedere a servizi di infrastruttura, quali DHCP, DNS o WINS, i server che erogano tali servizi vengono solitamente implementati in questo modo.
  
##### Elenchi filtri per la Woodgrove Bank
  
Dopo aver analizzato l'output dei requisiti del traffico ottenuto in base alle istruzioni del capitolo 4, gli amministratori della Woodgrove Bank hanno mappato l'elenco dei filtri nella tabella seguente:
  
**Tabella 5.2. Esempi degli elenchi filtri utilizzati dalla Woodgrove Bank**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Elenco filtri</p></th>  
<th><p>Filtri definiti</p></th>  
<th><p>Protocollo o porta</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Subnet protette</p></td>
<td style="border:1px solid black;"><p>Qualsiasi &lt;-&gt; 192.168.1.0/24</p>
<p>Qualsiasi &lt;-&gt; 172.10.1.0/24</p></td>
<td style="border:1px solid black;"><p>Tutte</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Elenco di esenzioni DNS</p></td>
<td style="border:1px solid black;"><p>Qualsiasi &lt;-&gt; 192.168.1.21</p>
<p>Qualsiasi &lt;-&gt; 192.168.1.22</p></td>
<td style="border:1px solid black;"><p>Tutte</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Elenco di esenzioni controller di dominio</p></td>
<td style="border:1px solid black;"><p>Qualsiasi &lt;-&gt; 192.168.1.21</p>
<p>Qualsiasi &lt;-&gt; 192.168.1.22</p></td>
<td style="border:1px solid black;"><p>Tutte</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Elenco di esenzioni server applicazioni LOB</p></td>
<td style="border:1px solid black;"><p>Qualsiasi &lt;-&gt; 192.168.1.10</p></td>
<td style="border:1px solid black;"><p>Tutte</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Elenco di esenzioni WINS</p></td>
<td style="border:1px solid black;"><p>Qualsiasi &lt;-&gt; 192.168.1.22</p></td>
<td style="border:1px solid black;"><p>Tutte</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>DHCP, traffico di negoziazione</p></td>
<td style="border:1px solid black;"><p>Indirizzo IP &lt;-&gt; Qualsiasi</p></td>
<td style="border:1px solid black;"><p>UDP 68 di origine, 67 di destinazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>ICMP, Tutto il traffico</p></td>
<td style="border:1px solid black;"><p>Indirizzo IP &lt;-&gt; Qualsiasi</p></td>
<td style="border:1px solid black;"><p>Solo ICMP</p></td>
</tr>  
</tbody>  
</table>
  
Per creare questi elenchi filtri, i progettisti della Woodgrove Bank hanno seguito le istruzioni riportate in questo capitolo. Il primo elenco (Subnet protette) include due filtri:
  
-   Qualsiasi &lt;-&gt; 192.168.1.0/24
  
-   Qualsiasi &lt;-&gt; 172.10.1.0/24
  
Questi filtri delle subnet sono speculari affinché corrispondano sia al traffico in ingresso che a quello in uscita e sono configurati per essere attivati da qualsiasi protocollo. Questo elenco, quando associato all'operazione filtro appropriata, implementerà i gruppi di isolamento.
  
I progettisti della Woodgrove Bank hanno quindi scelto di implementare un elenco di esenzioni per il traffico di rete ICMP. Questo elenco di filtri include un solo filtro speculare (Indirizzo IP &lt;-&gt; Qualsiasi) configurato soltanto per il traffico di rete ICMP. Questo approccio consente agli amministratori di utilizzare l'utilità Ping come strumento per la risoluzione dei problemi di questo ambiente, indipendentemente dalla negoziazione di un'associazione di protezione (SA, Security Association) IPsec. Tale approccio era inoltre necessario perché il rilevamento dell'unità massima di trasmissione (MTU, Maximum Transmission Unit) è imprescindibile per il corretto funzionamento di questa soluzione. Per il traffico DHCP, i progettisti della Woodgrove Bank hanno creato un nuovo filtro per la porta UDP 68 al fine di consentire ai client DHCP di ricevere il traffico dal server DHCP.
  
Inoltre, la Woodgrove Bank disponeva di alcune applicazioni aziendali (LOB, line-of-business) che venivano eseguite su server non inseribili nell'infrastruttura IPsec. Per consentire questi servizi, i progettisti hanno quindi creato un nuovo elenco di esenzioni, denominato Elenco di esenzioni server applicazioni LOB, e aggiunto un filtro Qualsiasi &lt;-&gt; 192.168.1.10 per il sistema di hosting dell'applicazione LOB.
  
Infine, il team di progettazione della Woodgrove Bank ha individuato i servizi di infrastruttura e creato gli elenchi di esenzioni corrispondenti per consentire a tutti i client di comunicare direttamente con i server che erogano questi servizi, indipendentemente dalle impostazioni di IPsec per i gruppi di isolamento. Sono stati creati elenchi di esenzioni specifici per i seguenti servizi:
  
-   **DNS**. Questo elenco esenta i server DNS affinché tutti i client della rete possano eseguire le ricerche DNS.
  
-   **Controller di dominio**. Questo elenco consente ai sistemi uniti al dominio di eseguire l'autenticazione con un controller di dominio.
  
-   **WINS**. Questo elenco consente specificatamente alle periferiche host di eseguire le ricerche dei nomi NetBIOS su un server WINS.
  
Questi elenchi includono filtri speculari, specificati come Qualsiasi &lt;-&gt; Indirizzo IP specifico, e sono configurati per attivarsi con qualsiasi protocollo. Il numero di computer negli elenchi di esenzioni deve essere minimo, perché tutto il traffico verso questi computer viene esentato e tutti i computer dell'elenco di esenzioni hanno un accesso TCP/IP totale a tutti gli host attendibili del dominio di isolamento. Conseguentemente, questo approccio potrebbe offrire ai pirati informatici una superficie di attacco più ampia di quella altrimenti disponibile. Per dettagli sui requisiti che possono ridurre il rischio del traffico in ingresso da indirizzi IP esentati, consultare il foglio di calcolo **Business\_Requirements.xls**, incluso nella cartella Strumenti e modelli.
  
La Woodgrove Bank ha scelto di gestire due elenchi separati per i server DNS e i controller di dominio, nonostante gli indirizzi IP siano i medesimi. È stato scelto questo approccio perché entrambi gli elenchi filtri sono associati alla medesima operazione di autorizzazione. Inoltre, la rete di produzione della Woodgrove Bank utilizza i server DNS in alcune aree che non fungono anche da controller di dominio.
  
Invece di utilizzare indirizzi IP di destinazione specifici, il filtro per DHCP è stato configurato in modo da creare corrispondenze con tutto il traffico in uscita dai client DHCP. La specularità di questo filtro consente le risposte dai server DHCP. Come menzionato, ciò potrebbe anche consentire attacchi in ingresso da qualsiasi indirizzo IP mediante la porta di origine 67. Tuttavia, l'attacco in ingresso è limitato alla porta di destinazione 68 del client, utilizzata dal client DHCP. La Woodgrove Bank ha optato per questa configurazione al fine di evitare la configurazione di filtri per ciascun server DHCP e perché la valutazione dei rischi non classifica ad alto livello i rischi di attacchi in ingresso sulla porta dei client DHCP, così come il rischio di server DHCP non autorizzati.
  
Questa sezione non include la descrizione completa di tutti i filtri. Si consiglia comunque di utilizzare il campo di descrizione per definire con precisione ciascun filtro, perché il monitor IPsec e gli strumenti della riga di comando visualizzano la descrizione dei filtri e non le informazioni dell'elenco filtri.
  
#### Operazioni filtro IPsec
  
Le operazioni filtro definiscono come vengono gestiti i pacchetti IP in caso di corrispondenza con un filtro dell'elenco. Le operazioni filtro sono alla base dell'implementazione dei vari gruppi di isolamento. Nonostante il sistema operativo Windows includa tre operazioni filtro predefinite, si consiglia di eliminarle e di creare nuove operazioni filtro. Questo approccio consente di accertarsi che solo le operazioni create facciano parte della configurazione utilizzata. Ciascuna operazione filtro include un nome, una descrizione e un metodo di protezione.
  
##### Nome
  
Assegnare all'operazione un nome esplicativo che rifletta l'azione che svolge.
  
##### Descrizione
  
Immettere in questo campo una descrizione dettagliata del comportamento dell'operazione.
  
##### Metodi di protezione
  
I metodi di protezione implementati all'interno dell'operazione filtro dipendono dai requisiti di elaborazione dei pacchetti che corrispondono ai filtri associati dell'elenco. Sono disponibili le seguenti tre opzioni:
  
-   **Blocca**. I pacchetti IP che corrispondono al filtro associato vengono bloccati. In altre parole, il pacchetto viene scartato o ignorato.
  
-   **Autorizza**. I pacchetti IP che corrispondono al filtro associato vengono autorizzati ad attraversare il livello IPsec, senza ulteriori elaborazioni da parte di IPsec.
  
-   **Negozia protezione**. Se i pacchetti in uscita corrispondono ai criteri del filtro, IPsec tenterà di negoziare uno dei metodi di protezione inclusi nell'operazione filtro, sulla base del relativo ordine. Più elevata è la posizione del metodo di protezione nell'elenco, maggiore è il grado di precedenza. Per ciascun metodo di protezione, è possibile specificare se utilizzare l'integrità, attivare la crittografia e scegliere gli algoritmi di crittografia. La gestione dei pacchetti in ingresso che corrispondono a un filtro con un'operazione di negoziazione associata è determinata dall'impostazione di **Accetta comunicazioni non protette, ma rispondi sempre usando IPSEC.**
  
La tabella seguente elenca le possibili opzioni di crittografia per ciascun metodo di protezione:
  
**Tabella 5.3. Opzioni di protezione e crittografia**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Metodo di protezione</p></th>  
<th><p>Opzioni di crittografia</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>AH (Authentication Header)</p></td>
<td style="border:1px solid black;"><p>MD5</p>
<p>SHA-1</p></td>
<td style="border:1px solid black;"><p>Assicura l'integrità e l'autenticità sia del payload IP (dati) che dell'intestazione IP (indirizzo) senza crittografia. AH non consente l'attraversamento di periferiche NAT</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Integrità ESP</p></td>
<td style="border:1px solid black;"><p>&lt;Nessuna&gt;</p>
<p>MD5</p>
<p>SHA-1</p></td>
<td style="border:1px solid black;"><p>Assicura l'integrità e l'autenticità soltanto del payload IP (dati). Può essere utilizzata sia con che senza crittografia. L'utilizzo di ESP senza autenticazione non è consigliato.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Crittografia</p></td>
<td style="border:1px solid black;"><p>&lt;Nessuna&gt;</p>
<p>3DES</p>
<p>DES</p></td>
<td style="border:1px solid black;"><p>Con DES o 3DES, esegue la crittografia del payload IP (dati). Può essere utilizzato senza algoritmo di crittografia quando la crittografia non è necessaria.</p></td>
</tr>  
</tbody>  
</table>
  
Le implementazioni IPsec di Windows 2000 SP4, Windows XP SP2 e Windows Server 2003 supportano le tecniche NAT-T per l'ESP della modalità di trasporto IPsec, oltre a supportare il NAT-T per i tunnel dei client VPN L2TP/IPsec. Per Windows 2000 SP4, è necessario l'aggiornamento per il NAT-T. Il supporto di Windows 2000 e Windows XP per il NAT-T della modalità di trasporto di IPsec è limitato nelle versioni Windows 2000 e Windows XP precedenti a SP2 perché il rilevamento dell'MTU del percorso (PMTU) non è supportato per il traffico protetto da IPsec. Windows Server 2003 include questo supporto. Per l'incapsulamento dell'ESP, le tecniche NAT-T utilizzano un'intestazione UDP posta dopo l'intestazione IP. IKE rileva automaticamente la presenza del NAT sul percorso e utilizza UDP-ESP se ESP è incluso nell'elenco dei metodi di protezione. È inoltre importante notare che le attuali implementazioni Windows di IPsec non supportano lo standard AES (Advanced Encryption Standard) del governo federale statunitense. Nelle versioni future di Windows sarà supportato.
  
Per AH ed ESP, sono disponibili le seguenti opzioni di crittografia:
  
-   **MD5**. Questo algoritmo hash utilizza una chiave di crittografia a 128 bit per generare un digest del contenuto dei pacchetti. MD5 non è un algoritmo approvato per gli scenari di protezione del governo federale statunitense.
  
-   **SHA-1**. Questo algoritmo hash utilizza una chiave di crittografia più avanzata a 160 bit per generare un digest del contenuto dei pacchetti. La lunghezza superiore della chiave di SHA-1 assicura una maggiore protezione, nonostante non comporti un carico di elaborazione superiore. SHA-1 è un algoritmo approvato per gli scenari di protezione del governo federale statunitense.
  
È possibile configurare ESP affinché non utilizzi alcun algoritmo di crittografia, con conseguente applicazione soltanto dell'integrità e autenticità dei dati. Questa configurazione viene solitamente denominata ESP senza crittografia e consente di autenticare gli host prima di stabilire una connessione di comunicazione e di effettuare un controllo di integrità sul segmento dati del pacchetto IP trasportato nel pacchetto ESP.
  
ESP consente anche di crittografare la sezione dati del pacchetto IP. Sono disponibili le seguenti due opzioni di crittografia:
  
-   **DES**. Questa opzione utilizza una sola chiave a 56 bit ed elabora ciascun blocco uno alla volta. DES è un requisito della conformità alla specifica RFC (Request for Comment). Viste le sempre maggiori abilità dei pirati informatici nel compromettere la crittografia DES, non è consigliabile utilizzarla.
  
-   **3DES**. Questa opzione elabora tre volte ciascun blocco utilizzando tre chiavi univoche a 56 bit. Nonostante la crittografia DES sia supportata, si consiglia di utilizzare 3DES per la maggiore protezione che garantisce. L'opzione 3DES è, tuttavia, leggermente più lenta e genera un carico di elaborazione superiore rispetto alla crittografia DES.
  
Per soddisfare requisiti di protezione particolarmente elevati, è possibile combinare i protocolli AH ed ESP con una delle due crittografie. Se, ad esempio, esiste una chiara esigenza di integrità dell'intestazione IP oltre a quella di crittografia dei dati, è possibile configurare il metodo di protezione per l'utilizzo di AH con l'integrità SHA-1 ed ESP con la crittografia 3DES. Se è necessaria soltanto l'integrità dei dati, è possibile utilizzare ESP senza crittografia con SHA-1.
  
Nonostante sia possibile selezionare qualsiasi combinazione di opzioni di protezione, è importante considerare che AH assicura l'integrità sia dei dati che dell'intestazione. L'utilizzo combinato di AH ed ESP per l'integrità dei dati non assicura alcuna protezione supplementare per l'integrità dei dati del pacchetto, ma aumenta soltanto il carico di lavoro necessario per elaborare il pacchetto. Inoltre, ESP combinato ad AH non consente di eliminare i problemi delle barriere NAT che AH deve superare. È quindi opportuno utilizzare AH ed ESP insieme solo per gli ambienti che richiedono il massimo livello di protezione.
  
Quando si configurano i metodi di protezione delle operazioni filtro, è necessario adottare un'accurata pianificazione. Affinché due computer completino la negoziazione, le rispettive operazioni filtro devono avere in comune almeno uno dei metodi di protezione. Ciascuna operazione filtro potrebbe contenere più di un metodo di negoziazione per consentire diversi tipi di negoziazioni. Un sistema potrebbe, ad esempio, negoziare solamente con ESP senza crittografia, ma l'operazione filtro potrebbe anche contenere un metodo di negoziazione per ESP-3DES. Questo approccio consentirà al sistema di negoziare, se necessario, una connessione con crittografia 3DES.
  
Oltre a selezionare i metodi di protezione, è possibile specificare le impostazioni della chiave di sessione per ciascun metodo di protezione. Per impostazione predefinita, le durate delle SA IPsec sono configurate a 100 megabyte (MB) di dati trasferiti o un'ora di tempo. Queste impostazioni controllano quando la modalità rapida IKE rinegozia una nuova coppia di associazioni di protezione IPsec. Il processo in modalità rapida IKE viene definito "reimpostazione delle chiavi", ma in effetti non si limita ad aggiornare le chiavi per la coppia di SA IPsec esistenti. Se scade la durata, IPsec deve scartare i pacchetti; tenta quindi di completare la rinegoziazione prima della scadenza della durata in byte o secondi. Se la durata è insufficiente, i pacchetti potrebbero andare perduti. Analogamente, l'utilizzo della CPU potrebbe incrementare per i server che gestiscono le SA IPsec con numerosi client. Il rinnovo delle SA IPsec evita che i pirati informatici possano decifrare l'intera comunicazione, pur scoprendo una delle chiavi di sessione. Aumentando la durata, i pirati informatici hanno a disposizione maggiori informazioni sulla chiave di sessione. Si deve quindi evitare di modificare le durate, a meno che esigenze operative specifiche non lo impongano, ed è possibile scrivere specifici requisiti di protezione che definiscano un livello appropriato di protezione contro attacchi sofisticati alla crittografia.
  
##### Opzioni della negoziazione di protezione
  
Per i criteri IPsec, è possibile impostare le seguenti opzioni per la negoziazione di protezione:
  
-   Passthrough in ingresso
  
-   Modalità non crittografata
  
-   Utilizza chiave di sessione PFS (Perfect Forward Secrecy)
  
###### Passthrough in ingresso
  
L'opzione Passthrough in ingresso è stata sviluppata per i criteri dei server interni affinché i criteri dei client possano utilizzare la regola non intrusiva di risposta predefinita. Quando questa opzione è attivata, verranno accettate le richieste di connessione in testo normale che corrispondono al filtro in ingresso. La risposta di connessione dal server corrisponde al filtro in uscita che attiva una richiesta di negoziazione in modalità principale IKE verso il client.
  
Questa opzione non va attivata sui computer connessi a Internet poiché consente il passaggio degli attacchi in ingresso attraverso il livello IPsec. Inoltre, obbliga il server a tentare una negoziazione di SA IPsec verso l'IP di origine del pacchetto in ingresso. Effettuando lo spoofing degli indirizzi IP di origine, i pirati informatici possono pertanto causare un problema di negazione del servizio sul server poiché IKE tenta di negoziare centinaia o migliaia di indirizzi IP non validi.
  
Per attivare il passthrough in ingresso, selezionare **Accetta comunicazioni non protette, ma rispondi sempre usando IPSEC** nella finestra di dialogo **Gestione operazioni filtro**.
  
**Nota:** se i criteri assegnati ai client non attivano la regola di risposta predefinita, è necessario disattivare questa opzione, perché non ci sarà alcuna risposta per la comunicazione IPsec. Può inoltre essere utilizzata come vettore di un attacco di negazione del servizio.
  
###### Modalità non crittografata
  
L'opzione della modalità non crittografata controlla la funzionalità del computer di origine che consente l'invio di traffico senza la protezione IPsec, a condizione che la negoziazione iniziale in modalità principale IKE non ottenga risposta da un computer di destinazione. Gli host che non supportano IPsec non saranno in grado di rispondere (utilizzando IKE) alla richiesta di negoziazione IKE. Questi host sono definiti computer che non riconoscono IPsec. Tuttavia, la mancanza di una risposta in modalità principale IKE non significa necessariamente che il computer non è in grado di utilizzare IPsec; potrebbe, infatti, trattarsi di un computer che consente comunicazioni protette da IPsec, ma che non dispone di un criterio IPsec attivo. Oppure il criterio IPsec potrebbe non includere operazioni di autorizzazione e blocco o non essere stato concepito per negoziare con l'indirizzo IP del computer di origine. Nella terminologia IPsec, il traffico di rete che non utilizza IPsec viene definito *non crittografato*. In caso di mancata risposta da un computer di destinazione entro tre secondi, viene creata un'associazione di protezione trasferibile (SA trasferibile) e la comunicazione avviene in modalità non crittografata. Per le distribuzioni iniziali, si consiglia di attivare questa opzione affinché i client possano comunicare con gli host su cui IPsec non è attivato. Inoltre, utilizzando questa opzione, risulta più facile ristabilire temporaneamente la connettività in modalità non crittografata quando il servizio IPsec viene arrestato per la risoluzione dei problemi. Se il computer di destinazione invia una risposta IKE e per una qualsiasi ragione si verifica un problema durante la negoziazione IKE, il servizio IPsec sul computer di origine scarterà i pacchetti in uscita, bloccando così la comunicazione.
  
Per attivare la modalità non crittografata, selezionare **Consenti comunicazioni non protette con computer senza IPsec** nella finestra di dialogo **Gestione operazioni filtro**.
  
**Nota:** la modalità di funzionamento di questa opzione è diversa sui computer che eseguono Windows 2000 SP3 o versioni successive, Windows XP SP1 e Windows Server 2003. Quando è attivata solo questa opzione, il sistema sarà in grado di avviare la comunicazione in modalità non crittografata, ma non accetterà richieste di comunicazione da sistemi senza IPsec. Se è necessario che il sistema risponda alle richieste e che avvii la comunicazione con sistemi senza IPsec, selezionare le opzioni **Accetta comunicazioni non protette, ma rispondi sempre usando IPSEC** e **Consenti comunicazioni non protette con computer senza IPsec**.  
Se il sistema esegue Windows 2000 o Windows XP senza gli appropriati service pack, il client accetterà richieste di comunicazione non protette quando è selezionata l'opzione **Consenti comunicazioni non protette con computer senza IPsec,** anche se l'opzione **Accetta comunicazioni non protette, ma rispondi sempre usando IPSec** non è selezionata. Questa condizione si verifica perché quando l'opzione **Consenti comunicazioni non protette con computer senza IPsec** è selezionata, IPsec elabora il filtro in ingresso associato come un filtro di passthrough in ingresso (lo stesso comportamento si presenta quando è selezionata l'opzione **Accetta comunicazioni non protette, ma rispondi sempre usando IPSec**).
  
###### Utilizza chiave di sessione PFS (Perfect Forward Secrecy)
  
L'opzione Utilizza chiave di sessione PFS (Perfect Forward Secrecy) determina se è possibile utilizzare il materiale della chiave principale per generare tutte le chiavi di sessione o soltanto la prima chiave di sessione. Quando questa opzione è attivata, la chiave principale può essere utilizzata una sola volta e per ciascuna nuova negoziazione delle chiavi di sessione sarà necessario un nuovo scambio di chiavi, che genera una nuova chiave principale prima della chiave di sessione. Questa impostazione assicura che, in caso di compromissione della chiave principale, il pirata informatico non potrà generare chiavi di sessione supplementari per decrittografare il flusso di traffico. L'attivazione di questa opzione non è consigliata a causa del maggiore carico generato dallo scambio di chiavi a ciascun intervallo di rinnovo delle chiavi di sessione.
  
Per ulteriori informazioni sulle opzioni di passthrough in ingresso, modalità non crittografata e uso della chiave di sessione PFS (Perfect Forward Secrecy) e PFS (Perfect Forward Secrecy) chiave master, consultare la sezione "Security Negotiation Options" del white paper [Using Microsoft Windows IPSec to Help Secure an Internal Corporate Network Server](http://www.microsoft.com/downloads/details.aspx?familyid=a774012a-ac25-4a1d-8851-b7a09e3f1dc9&displaylang=en), disponibile nell'area di download del sito Web Microsoft all'indirizzo www.microsoft.com/downloads/details.aspx?  
familyid=a774012a-ac25-4a1d-8851-b7a09e3f1dc9&displaylang=en.
  
##### Operazioni filtro IPsec della Woodgrove Bank
  
La tabella seguente riporta i nomi delle operazioni filtro e le descrizioni utilizzate per implementare i vari gruppi di isolamento nello scenario della Woodgrove Bank:
  
**Tabella 5.4. Operazioni filtro IPsec e descrizioni**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Operazione filtro</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPsec - Blocca</p></td>
<td style="border:1px solid black;"><p>Blocca il traffico che corrisponde al filtro.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPsec - Autorizza</p></td>
<td style="border:1px solid black;"><p>Consente il traffico che corrisponde al filtro.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta</p>
<p>(Accetta in ingresso, Consenti in uscita)</p></td>
<td style="border:1px solid black;"><p>L'host accetta in ingresso i pacchetti di IPsec o non crittografati. Per il traffico in uscita, avvia una negoziazione IKE e consente l'utilizzo della modalità non crittografata in caso di mancata risposta. Questa operazione filtro viene utilizzata per configurare il gruppo di isolamento Limite.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta protetta (Ignora in ingresso, Consenti in uscita)</p></td>
<td style="border:1px solid black;"><p>L'host consente l'accesso TCP/IP in ingresso soltanto quando i pacchetti sono protetti da IPsec e ignora i pacchetti in ingresso non protetti da IPsec. Per il traffico in uscita, avvia una negoziazione IKE e consente la modalità non crittografata in caso di mancata risposta. Questa operazione filtro viene utilizzata per implementare il dominio di isolamento, in cui sono consentite le connessioni in uscita a host non attendibili.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta completa (Ignora in ingresso, Impedisci in uscita)</p></td>
<td style="border:1px solid black;"><p>L'host richiede comunicazioni protette da IPsec sia per i pacchetti in ingresso che in uscita. Questa operazione filtro viene utilizzata per implementare il gruppo di isolamento Nessun fallback, in cui tutte le comunicazioni sono protette da IPsec.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta di crittografia (Ignora in ingresso, Impedisci in uscita)</p></td>
<td style="border:1px solid black;"><p>L'host consente l'accesso TCP/IP in ingresso soltanto quando i pacchetti sono protetti dalla crittografia IPsec ESP-3DES e ignora i pacchetti in ingresso non protetti da IPsec. Per il traffico in uscita, avvia una negoziazione IKE che richiede la crittografia IPsec ESP-3DES. Questa operazione filtro viene utilizzata per implementare il gruppo di isolamento Crittografia.</p></td>
</tr>  
</tbody>  
</table>
  
Le prime due operazioni filtro sono di immediata comprensione. L'operazione filtro di blocco scarta tutto il traffico che corrisponde a uno dei filtri inclusi nell'elenco associato. L'operazione filtro di autorizzazione consente il traffico che corrisponde a uno dei filtri inclusi nell'elenco. Le ultime quattro operazioni filtro della tabella 5.4 vengono utilizzate per implementare i gruppi di isolamento nello scenario della Woodgrove Bank.
  
Gli amministratori della Woodgrove Bank devono implementare quattro gruppi di isolamento per la protezione. Per distribuire questa configurazione, è necessario definire almeno tre operazioni filtro con metodi personalizzati di negoziazione della protezione, oltre alle operazioni filtro di blocco e autorizzazione.
  
La Woodgrove Bank non ha esigenze supplementari per la comunicazione bilaterale fra i computer di uno specifico gruppo di isolamento protetto. La banca ha quindi stabilito che le quattro operazioni filtro con negoziazione riportate nella tabella seguente sono sufficienti per l'implementazione del proprio ambiente:
  
**Tabella 5.5. Metodi di protezione supportati**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Operazione filtro</p></th>  
<th><p>Metodi di protezione supportati</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta (Accetta in ingresso, Consenti in uscita)</p></td>
<td style="border:1px solid black;"><p>ESP – SHA-1, &lt;Nessuna&gt;</p>
<p>ESP – SHA-1, 3DES</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta protetta (Ignora in ingresso, Consenti in uscita)</p></td>
<td style="border:1px solid black;"><p>ESP – SHA-1, &lt;Nessuna&gt;</p>
<p>ESP – SHA-1, 3DES</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta completa (Ignora in ingresso, Impedisci in uscita)</p></td>
<td style="border:1px solid black;"><p>ESP – SHA-1, &lt;Nessuna&gt;</p>
<p>ESP – SHA-1, 3DES</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta di crittografia (Ignora in ingresso, Impedisci in uscita)</p></td>
<td style="border:1px solid black;"><p>ESP – SHA-1, 3DES</p></td>
</tr>  
</tbody>  
</table>
  
La Woodgrove utilizza ESP IPsec invece di AH a causa della presenza all'interno dell'organizzazione di periferiche di rete che utilizzano il servizio NAT.
  
La Woodgrove Bank ha inoltre l'esigenza di implementare la crittografia per alcuni server dell'organizzazione. Di conseguenza, tutti i criteri devono includere l'opzione per l'utilizzo della crittografia. La Woodgrove Bank ha quindi scelto di implementare un tipo di protezione basata esclusivamente su ESP IPsec.
  
Per l'integrità ESP, la Woodgrove Bank ha scelto di utilizzare SHA-1, invece di MD5, per la maggiore protezione che assicura, ma anche perché le normative del governo statunitense ne impongono l'utilizzo per l'elaborazione di informazioni finanziarie richiedendo algoritmi approvati.
  
La Woodgrove Bank ha stabilito di non utilizzare PFS sulle operazioni filtro poiché non sussistono pericoli specifici per la protezione che ne richiedano l'utilizzo. Questa decisione è stata adottata anche per evitare impatti prestazionali sui computer, causati dalla rinegoziazione delle chiavi.
  
##### Operazione filtro per il dominio di isolamento
  
Per implementare il dominio di isolamento, gli amministratori della Woodgrove Bank hanno creato l'operazione filtro IPSEC - Modalità di richiesta protetta (Ignora in ingresso, Consenti in uscita).
  
La Woodgrove Bank deve soddisfare numerosi requisiti aziendali per la comunicazione fra gli host del dominio di isolamento e di altri gruppi di isolamento. Conseguentemente, i client del dominio di isolamento effettuano le operazioni seguenti, descritte nelle tabelle 4.5 e 4.6 del capitolo 4 di questa guida:
  
-   Avvio delle comunicazioni con gli host del gruppo di isolamento Nessun fallback
  
-   Accettazione delle comunicazioni dagli host del gruppo di isolamento Nessun fallback
  
-   Avvio delle comunicazioni con gli host del gruppo di isolamento Crittografia
  
-   Accettazione delle comunicazioni dagli host del gruppo di isolamento Crittografia
  
-   Avvio delle comunicazioni con gli host del gruppo di isolamento Limite
  
-   Accettazione delle comunicazioni dagli host del gruppo di isolamento Limite
  
-   Avvio della comunicazione con sistemi non attendibili
  
I client del dominio di isolamento non possono accettare comunicazioni da sistemi non attendibili.
  
Si noti che il criterio IPsec utilizza filtri e operazioni filtro per intercettare e controllare i pacchetti IP in ingresso e in uscita. Nonostante IKE autentichi entrambi i computer, l'appartenenza a un gruppo di un computer che utilizza un certo indirizzo IP non è nota nel momento in cui viene inviata la richiesta iniziale di connessione in uscita. Di conseguenza, non è possibile configurare specificatamente IPsec e IKE per l'avvio delle comunicazioni in una modalità specifica con un particolare gruppo di isolamento o identità. Inoltre, i computer che sono membri di questi gruppi di isolamento possono essere ubicati in qualsiasi posizione sulla rete interna. Non è quindi possibile utilizzare gli indirizzi IP per definire o approssimare i gruppi di isolamento.
  
Al fine di implementare questi requisiti in un criterio IPsec, è necessario configurare l'operazione filtro affinché venga attivata dall'elenco di filtri che include tutte le subnet interne. È possibile sintetizzare i requisiti precedenti in due comportamenti di base:
  
-   In uscita, per i pacchetti che corrispondono ai relativi filtri (tutte le subnet interne), avvio delle richieste di negoziazione IKE che tentano di proteggere il traffico con ESP IPsec, con preferenza per ESP senza crittografia e inclusi ESP–SHA-1–3DES. Autorizzazione alla modalità non crittografata, se un host di destinazione non risponde con IKE.
  
-   In ingresso, per pacchetti che corrispondono ai relativi filtri (tutte le subnet interne), ignorare il traffico non protetto all'interno di pacchetti ESP IPsec validi.
  
Per consentire le comunicazioni con il gruppo di isolamento Crittografia, i metodi di protezione includono quelli definiti nel gruppo di isolamento Crittografia (algoritmi ESP–SHA-1–3DES). Per ulteriori informazioni sui metodi di negoziazione della protezione crittografata, vedere la sezione "Operazione filtro per il gruppo di isolamento Crittografia" del presente capitolo.
  
Per il traffico interno del dominio di isolamento e con i gruppi di isolamento Limite e Nessun fallback, la Woodgrove Bank utilizza ESP senza crittografia con SHA-1.
  
È necessario disattivare l'opzione **Accetta comunicazioni non protette, ma rispondi sempre usando IPSEC**dell'operazione filtro affinché il testo non crittografato in ingresso venga ignorato. Questa configurazione assicura che gli host del dominio di isolamento non accetteranno il traffico da computer che non rientrano nell'ambiente IPsec.
  
L'operazione filtro IPSEC - Modalità di richiesta protetta (Ignora in ingresso, Consenti in uscita) è stata configurata per consentire ai membri del dominio di isolamento di avviare la comunicazione con sistemi non attendibili. Questo comportamento si implementa attivando l'opzione **Consenti comunicazioni non protette con computer senza IPsec** dell'operazione filtro. Se un host attendibile del dominio di isolamento avvia una connessione in uscita verso un host non attendibile (o un altro sistema non protetto da IPsec), viene stabilita una SA IPsec trasferibile, che rimane attiva per cinque minuti dall'interruzione del flusso di traffico. Conseguentemente, durante questo intervallo di tempo il sistema non affidabile potrà avviare nuove connessioni con l'host affidabile in modalità non crittografata. Quando la SA trasferibile scade, l'host affidabile non accetterà più il traffico da questo sistema in modalità non crittografata. Il supporto del filtraggio IPsec e della SA trasferibile non è stato concepito per fornire protezione su connessioni specifiche, quale il filtraggio di stato effettuato, ad esempio, da numerosi firewall. Le SA trasferibili autorizzano tutto i traffico che corrisponde al filtro associato. Per ulteriori informazioni in merito a questo processo, consultare la sezione relativa a SA in modalità principale IKE e SA IPsec nell'appendice A, "Panoramica dei concetti relativi ai criteri IPSec".
  
##### Operazione filtro per il gruppo di isolamento Limite
  
Per implementare il gruppo di isolamento Limite, gli amministratori della Woodgrove Bank hanno creato l'operazione filtro IPSEC - Modalità di richiesta (Accetta in ingresso, Consenti in uscita).
  
La Woodgrove Bank deve soddisfare numerosi requisiti aziendali per la comunicazione fra gli host del gruppo di isolamento Limite e di altri gruppi di isolamento. Conseguentemente, i client del gruppo di isolamento Limite effettuano le operazioni seguenti, descritte nelle tabelle 4.5 e 4.6 del capitolo 4 di questa guida:
  
-   Avvio delle comunicazioni con gli host del gruppo di isolamento Nessun fallback
  
-   Accettazione delle comunicazioni dagli host del gruppo di isolamento Nessun fallback
  
-   Avvio delle comunicazioni con gli host del dominio di isolamento
  
-   Accettazione delle comunicazioni dagli host del dominio di isolamento
  
-   Accettazione delle comunicazioni dagli host del gruppo di isolamento Crittografia
  
-   Avvio delle comunicazioni con sistemi non attendibili
  
-   Accettazione delle comunicazioni da sistemi non attendibili
  
Al fine di implementare questi requisiti in un criterio IPsec, è necessario configurare l'operazione filtro affinché venga attivata dall'elenco di filtri che include tutte le subnet interne. È possibile sintetizzare i requisiti elencati in due comportamenti di base:
  
-   In uscita, per i pacchetti che corrispondono ai relativi filtri (tutte le subnet interne), avvio delle richieste di negoziazione IKE che tentano di proteggere il traffico con ESP IPsec, con preferenza per ESP senza crittografia e inclusi ESP–SHA-1–3DES. Autorizzazione alla modalità non crittografata, se un host di destinazione non risponde con IKE.
  
-   In ingresso, accettazione dei pacchetti non crittografati che corrispondono ai relativi filtri (tutte le subnet interne).
  
Per soddisfare questi requisiti necessari per avviare e accettare il traffico verso o da il dominio di isolamento e il gruppo di isolamento Nessun fallback, la Woodgrove Bank ha inserito i metodi di protezione delle negoziazioni utilizzati per il dominio di isolamento e il gruppo di isolamento Nessun fallback nell'operazione filtro. Il metodo di protezione comune per la negoziazione scelto dalla Woodgrove Bank è ESP con SHA-1 per l'integrità.
  
Agli host del gruppo di isolamento Limite è consentita la comunicazione con sistemi non attendibili. Per consentire questa funzionalità, gli amministratori della Woodgrove Bank hanno selezionato, per questa operazione filtro, entrambe le opzioni **Consenti comunicazioni non protette con computer senza IPsec** e **Accetta comunicazioni non protette, ma rispondi sempre usando IPSEC**. Attivando entrambe le opzioni, Woodgrove Bank ha la certezza che gli host accetteranno il traffico non protetto in ingresso e che saranno in grado di utilizzare la modalità non crittografata per il traffico non protetto in uscita.
  
##### Operazione filtro per il gruppo di isolamento Nessun fallback
  
Per implementare il gruppo di isolamento Nessun fallback, gli amministratori della Woodgrove Bank hanno creato l'operazione filtro IPSEC - Modalità di richiesta completa (Ignora in ingresso, Impedisci in uscita).
  
La Woodgrove Bank deve soddisfare numerosi requisiti aziendali per la comunicazione fra gli host del gruppo di isolamento Nessun fallback e di altri gruppi di isolamento. Conseguentemente, i client del gruppo di isolamento Nessun fallback possono effettuare le operazioni seguenti:
  
-   Avvio delle comunicazioni con gli host del dominio di isolamento
  
-   Accettazione delle comunicazioni dagli host del dominio di isolamento
  
-   Avvio delle comunicazioni con gli host del gruppo di isolamento Crittografia
  
-   Accettazione delle comunicazioni dagli host del gruppo di isolamento Crittografia
  
-   Avvio delle comunicazioni con gli host del gruppo di isolamento Limite
  
-   Accettazione delle comunicazioni dagli host del gruppo di isolamento Limite
  
I client inclusi nel gruppo di isolamento Nessun fallback non possono avviare né accettare le comunicazioni da sistemi non attendibili.
  
Al fine di implementare questi requisiti in un criterio IPsec, è necessario configurare l'operazione filtro affinché venga attivata dall'elenco di filtri che include tutte le subnet interne. È possibile sintetizzare i requisiti elencati in due comportamenti di base:
  
-   In uscita, per i pacchetti che corrispondono ai relativi filtri (tutte le subnet interne), avvio delle richieste di negoziazione IKE che tentano di proteggere il traffico con ESP IPsec, con preferenza per ESP senza crittografia e inclusi ESP–SHA-1–3DES. Modalità non crittografata *non* consentita, se un host di destinazione non risponde con IKE.
  
-   In ingresso, per i pacchetti non crittografati che corrispondono ai relativi filtri (tutte le subnet interne), ignorarli.
  
Per consentire le comunicazioni con il gruppo di isolamento Crittografia, i metodi di protezione includono quelli definiti nel gruppo di isolamento Crittografia. Per ulteriori informazioni sui metodi di negoziazione della protezione crittografata, vedere la sezione "Operazione filtro per il gruppo di isolamento Crittografia" del presente capitolo.
  
Per il traffico verso i gruppi di isolamento Limite e Nessun fallback, la Woodgrove Bank utilizza l'ESP con SHA-1 come metodo di protezione dell'integrità.
  
Per creare il gruppo di isolamento Nessun fallback, la casella di controllo **Accetta comunicazioni non protette, ma rispondi sempre usando IPSEC** dell'operazione filtro è deselezionata. Questo approccio assicura che gli host del gruppo di isolamento Nessun fallback proteggano tutto il traffico in ingresso e in uscita utilizzando IPsec e non accettino il traffico da computer che non rientrano nell'ambiente IPsec.
  
L'operazione filtro IPSEC - Modalità di richiesta completa (Ignora in ingresso, Impedisci in uscita) non consente ai computer che la utilizzano di avviare la comunicazione verso computer che non rientrano nell'infrastruttura IPsec. Per soddisfare questo requisito, l'opzione **Consenti comunicazioni non protette con computer senza IPsec** è stata disattivata.
  
##### Operazione filtro per il gruppo di isolamento Crittografia
  
La Woodgrove Bank ha scelto ESP come protocollo di base per l'integrità e SHA-1 come opzione di crittografia. Inoltre, gli host del gruppo di isolamento Crittografia devono poter comunicare con gli host del dominio di isolamento e del gruppo di isolamento Nessun fallback. L'operazione filtro è quindi stata configurata includendo i metodi di protezione della negoziazione che crittografano le informazioni.
  
La Woodgrove Bank deve soddisfare numerosi requisiti aziendali per la comunicazione fra gli host del gruppo di isolamento Crittografia e di altri gruppi di isolamento. Conseguentemente, i client del gruppo di isolamento Crittografia possono effettuare le operazioni seguenti, descritte nella tabella 4.6:
  
-   Avvio delle comunicazioni con gli host del dominio di isolamento
  
-   Accettazione delle comunicazioni dagli host del dominio di isolamento
  
-   Avvio delle comunicazioni con gli host del gruppo di isolamento Nessun fallback
  
-   Accettazione delle comunicazioni dagli host del gruppo di isolamento Nessun fallback
  
-   Avvio delle comunicazioni con gli host del gruppo di isolamento Limite
  
I computer del gruppo di isolamento Crittografia non possono accettare le comunicazioni dagli host del gruppo di isolamento Limite.
  
Al fine di implementare questi requisiti in un criterio IPsec, è necessario configurare l'operazione filtro affinché venga attivata dall'elenco di filtri che include tutte le subnet interne. È possibile sintetizzare i requisiti elencati in due comportamenti di base:
  
-   In uscita, per i pacchetti che corrispondono ai relativi filtri (tutte le subnet interne), avvio delle richieste di negoziazione IKE che tentano di proteggere il traffico solo con ESP–SHA-1–3DES di IPsec. Modalità non crittografata *non* consentita, se un host di destinazione non risponde con IKE.
  
-   In ingresso, per i pacchetti non crittografati che corrispondono ai relativi filtri (tutte le subnet interne), ignorarli. Accettazione solo delle richieste di negoziazione IKE da host attendibili che consentono ESP–SHA-1–3DES di IPsec.
  
I client inclusi nel gruppo di isolamento Crittografia non possono accettare comunicazioni dal gruppo di isolamento Limite e non possono avviare né accettare le comunicazioni da sistemi non attendibili.
  
Per consentire la comunicazione con il dominio di isolamento, i metodi di protezione della negoziazione utilizzati nell'operazione filtro IPSEC - Modalità di richiesta di crittografia (Ignora in ingresso, Impedisci in uscita) sono inclusi anche nelle operazioni IPSEC - Modalità di richiesta protetta (Ignora in ingresso, Consenti in uscita) e IPSEC - Modalità di richiesta completa (Ignora in ingresso, Impedisci in uscita). La Woodgrove Bank utilizza il metodo di crittografia 3DES, che assicura una maggiore protezione rispetto a DES, ma che implica un carico di lavoro supplementare.
  
Vista l'esigenza di non accettare né avviare la comunicazione con sistemi non attendibili, la Woodgrove Bank non ha attivato l'opzione **Accetta comunicazioni non protette, ma rispondi sempre usando IPSEC**. Questa configurazione assicura che gli host del gruppo di isolamento Crittografia non accettino il traffico da computer che non rientrano nell'ambiente IPsec. Anche l'opzione **Consenti comunicazioni non protette con computer senza IPsec** è stata disattivata al fine di impedire ai computer di tentare di avviare le comunicazioni con computer che non fanno parte dell'ambiente IPsec.
  
Il blocco delle comunicazioni IPsec da parte dei computer del gruppo di isolamento Limite ha reso necessaria un'ulteriore configurazione. Gli amministratori della Woodgrove Bank hanno configurato il GPO che recapita il criterio IPsec per i computer del gruppo di isolamento Crittografia includendo il diritto "Nega accesso al computer dalla rete". Questo diritto è stato applicato a un gruppo che includeva tutti gli account computer per i sistemi che rientrano nel gruppo di isolamento Limite. Se uno di questi computer tenta di avviare la comunicazione con un sistema del gruppo di isolamento Crittografia, l'autenticazione IKE non concederà l'autorizzazione e le comunicazioni verranno bloccate.
  
#### Criteri IPsec
  
I criteri IPsec configurano i computer basati su Windows per operare all'interno di un ambiente IPsec. Un criterio IPsec è un insieme di regole alle quali il traffico deve corrispondere. In Windows 2000 esistono tre diversi tipi di criteri IPsec:
  
-   Criteri locali
  
-   Criteri di dominio di Active Directory
  
-   Criteri dinamici
  
Windows XP e Windows Server 2003 supportano inoltre i seguenti tipi di criteri:
  
-   **Criteri IPsec di avvio**. Sono archiviati e gestiti al livello del Registro di sistema locale e supportati soltanto da Windows XP SP2 o versioni successive. Vengono applicati non appena il computer ottiene l'indirizzo IP, condizione che potrebbe verificarsi prima che il servizio IPsec venga avviato. Vengono sostituiti quando il servizio applica i criteri permanenti.
  
-   **Criteri IPsec permanenti**. Sono archiviati e gestiti al livello del Registro di sistema locale e possono essere configurati tramite uno strumento della riga di comando. Vengono applicati non appena il servizio IPsec si avvia e sostituiscono i criteri di avvio.
  
-   **Criteri IPsec locali**. Sono archiviati e gestiti a livello di computer locale. Si configurano tramite lo snap-in MMC (Microsoft Management Console) Gestione criteri di protezione IP o uno strumento della riga di comando. Vengono applicati insieme ai criteri permanenti, se non viene assegnato alcun criterio di dominio.
  
-   **Criteri IPsec di dominio di Active Directory**. Sono archiviati in Active Directory. Si gestiscono tramite lo snap-in MMC Gestione criteri di protezione IP o uno strumento della riga di comando. Sovrascrivono i criteri locali eventualmente assegnati. Per assegnare i criteri IPsec di Active Directory a un GPO, utilizzare lo snap-in MMC Editor criteri di gruppo o la console di gestione Criteri di gruppo di **Impostazioni di Windows**, **Impostazioni protezione**, **Criteri IPsec**.
  
-   **Criteri IPsec dinamici**. Sono archiviati soltanto nella memoria e possono essere configurati tramite uno strumento della riga di comando. Sono utilizzati come integrazione dinamica dei criteri esistenti e vengono eliminati quando il servizio IPsec viene arrestato.
  
Per semplificare la comprensione, le presenti istruzioni sono relative all'utilizzo dei criteri IPsec di dominio di Active Directory.
  
In fase di definizione dei criteri IPsec, è preferibile configurare un criterio generico che funga da base per l'infrastruttura IPsec di tutti i computer. Successivamente, si potranno creare criteri supplementari che applichino impostazioni più rigide sui sistemi che richiedono una maggiore protezione. Tutti i criteri supplementari devono essere configurati in modo da poter essere applicati al maggior numero possibile di computer che devono soddisfare specifici requisiti organizzativi o tecnici. Riducendo al minimo il numero totale di criteri, sarà infatti più semplice risolvere eventuali problemi e gestire i criteri.
  
I criteri IPsec includono un nome, una descrizione, una serie di regole e impostazioni di configurazione per gli intervalli di polling, lo scambio delle chiavi e i relativi metodi di scambio, trattati nei dettagli nella sezione seguente.
  
##### Nome
  
Ai criteri, così come alle operazioni filtro, devono essere assegnati nomi esplicativi, che ne facilitino la gestione e la risoluzione dei problemi sia durante l'implementazione che l'attuazione del progetto.
  
##### Descrizione
  
Utilizzando una descrizione dettagliata dei criteri, si facilita l'identificazione dell'azione del criterio, evitando di dover aprire e analizzare le singole regole.
  
##### Regole
  
Le regole IPsec contengono un solo elenco di filtri, un'operazione filtro associata, i metodi di autenticazione utilizzati per stabilire la relazione di trust fra i computer, il tipo di connessione e un eventuale impostazione di tunneling.
  
Ciascuna regola specifica uno o più metodi di autenticazione da utilizzare per stabilire la relazione di trust fra gli host. Le opzioni sono: protocollo Kerberos versione 5, certificati da un'autorità di certificazione specifica e chiavi già condivise.
  
Il tipo di connessione specifica le connessioni a cui viene applicato il criterio IPsec. È possibile configurare il criterio affinché venga applicato a tutte le connessioni, alle connessioni della rete locale o a quelle basate su un accesso remoto.
  
Il tipo di tunneling indica se il criterio IPsec specifica un tunnel IPsec. Se il tipo di tunneling è disattivato, IPsec utilizza la modalità di trasporto.
  
Per supportare i gruppi di isolamento protetti precedentemente illustrati in questa guida, la Woodgrove Bank ha implementato quattro criteri IPsec. Tutti i quattro criteri sono stati configurati impostando il protocollo di autenticazione Kerberos versione 5, sono stati applicati a tutte le connessioni e non specificano un tunnel IPsec.
  
La tabella seguente riporta i criteri utilizzati nello scenario della Woodgrove Bank:
  
**Tabella 5.6. Criteri IPsec della Woodgrove Bank**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome criterio</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPSEC - Criterio IPsec dominio di isolamento (1.0.041001.1600)</p></td>
<td style="border:1px solid black;"><p>Questo criterio implementa il dominio di isolamento. Gli host di questo gruppo di isolamento sono in grado di utilizzare la modalità non crittografata quando avviano le comunicazioni con host non protetti da IPsec. La configurazione prevede che gli host utilizzino la comunicazione IPsec. Se la negoziazione fra client protetti da IPsec non viene completata, la comunicazione non viene stabilita.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPSEC - Criterio IPsec gruppo di isolamento Limite (1.0.041001.1600)</p></td>
<td style="border:1px solid black;"><p>Questo criterio implementa il gruppo di isolamento Limite. La configurazione prevede che gli host utilizzino la comunicazione IPsec, ma consente la modalità non crittografata in caso di comunicazioni con un host senza IPsec.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPSEC - Criterio IPsec gruppo di isolamento Nessun fallback (1.0.041001.1600)</p></td>
<td style="border:1px solid black;"><p>Questo criterio implementa il gruppo di isolamento Nessun fallback. La configurazione prevede che gli host utilizzino la comunicazione IPsec. Se la negoziazione non viene completata e l'host tenta di comunicare con un client che non utilizza IPsec, la comunicazione si interrompe.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPSEC - Criterio IPsec gruppo di isolamento Crittografia (1.0.041001.1600)</p></td>
<td style="border:1px solid black;"><p>Questo criterio implementa il gruppo di isolamento Crittografia. La configurazione prevede che gli host utilizzino la comunicazione IPsec e la crittografia. Se la negoziazione non viene completata e l'host tenta di comunicare con un client che non utilizza IPsec, la comunicazione si interrompe.</p></td>
</tr>  
</tbody>  
</table>
  
Il numero associato al nome del criterio indica la versione e viene illustrato successivamente nella sezione "Versioni dei criteri".
  
Tutti i criteri della Woodgrove Bank contengono i medesimi elenchi di esenzioni poiché non esistono esigenze di esenzione di gruppi specifici di computer per un particolare gruppo di isolamento. La tabella seguente riporta le regole utilizzate da tutti i quattro criteri menzionati nella precedente tabella:
  
**Tabella 5.7. Regole comuni specificate nei criteri IPsec della Woodgrove Bank**

<p> </p>
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
<th><p>Elenco filtri</p></th>  
<th><p>Operazione filtro</p></th>  
<th><p>Metodi di autenticazione</p></th>  
<th><p>Endpoint del tunnel</p></th>  
<th><p>Tipo di connessione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Elenco di esenzioni DNS</p></td>
<td style="border:1px solid black;"><p>IPSEC - Autorizza</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Tutte</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Elenco di esenzioni controller di dominio</p></td>
<td style="border:1px solid black;"><p>IPSEC - Autorizza</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Tutte</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Elenco di esenzioni WINS</p></td>
<td style="border:1px solid black;"><p>IPSEC - Autorizza</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Tutte</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>DHCP, traffico di negoziazione</p></td>
<td style="border:1px solid black;"><p>IPSEC - Autorizza</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Tutte</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>ICMP, Tutto il traffico</p></td>
<td style="border:1px solid black;"><p>IPSEC - Autorizza</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Nessuna</p></td>
<td style="border:1px solid black;"><p>Tutte</p></td>
</tr>  
</tbody>  
</table>
  
Oltre alle regole elencate in questa tabella, è stata disattivata per ciascun criterio la regola di risposta predefinita del client.
  
I quattro criteri definiti dalla Woodgrove Bank differiscono soltanto nella modalità di gestione del traffico che non corrisponde agli elenchi di esenzioni. Per ciascuna di queste regole, il metodo di autenticazione impostato è il protocollo Kerberos versione 5, l'endpoint del tunnel è impostato su Nessuno, il tipo di connessione è impostato su Tutte.
  
La tabella seguente riporta le regole della Woodgrove per l'implementazione dei quattro gruppi di isolamento:
  
**Tabella 5.8. Regole di base della Woodgrove Bank per l'implementazione dei gruppi di isolamento**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome criterio</p></th>  
<th><p>Elenco filtri</p></th>  
<th><p>Operazione filtro</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPSEC - Criterio IPsec dominio di isolamento (1.0.041001.1600)</p></td>
<td style="border:1px solid black;"><p>Subnet protette della Woodgrove Bank</p></td>
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta protetta (Ignora in ingresso, Consenti in uscita)</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPSEC - Criterio IPsec gruppo di isolamento Limite (1.0.041001.1600)</p></td>
<td style="border:1px solid black;"><p>Subnet protette della Woodgrove Bank</p></td>
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta (Accetta in ingresso, Consenti in uscita)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPSEC - Criterio IPsec gruppo di isolamento Nessun fallback (1.0.041001.1600)</p></td>
<td style="border:1px solid black;"><p>Subnet protette della Woodgrove Bank</p></td>
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta completa (Ignora in ingresso, Impedisci in uscita)</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPSEC - Criterio IPsec gruppo di isolamento Crittografia (1.0.041001.1600)</p></td>
<td style="border:1px solid black;"><p>Subnet protette della Woodgrove Bank</p></td>
<td style="border:1px solid black;"><p>IPsec - Modalità di richiesta di crittografia (Ignora in ingresso, Impedisci in uscita)</p></td>
</tr>  
</tbody>  
</table>
  
La Woodgrove Bank ha scelto di utilizzare il protocollo Kerberos versione 5 come unico protocollo di autenticazione. Inoltre, non utilizza chiavi già condivise perché il valore della chiave di autenticazione può essere letto dagli amministratori locali nel Registro di sistema e da qualsiasi utente e computer autenticato del dominio. Infine, non ha scelto i certificati perché la banca non ha un'infrastruttura a chiave pubblica (PKI) distribuita.
  
Utilizzando il protocollo Kerberos versione 5, tutti i computer uniti al dominio sono in grado di partecipare all'infrastruttura IPsec perché possono eseguire l'autenticazione e ottenere il criterio. I computer non uniti al dominio non possono partecipare facilmente all'ambiente IPsec poiché non sono disponibili meccanismi di autenticazione né sistemi di distribuzione dei criteri. Se questi computer soddisfano i criteri degli host attendibili, è possibile configurare un criterio IPsec locale utilizzando l'autenticazione del certificato e consentire così la comunicazione di questi computer con altri host attendibili. Al momento, la Woodgrove Bank gestisce i computer che non rientrano nel dominio come non attendibili.
  
**Nota:** utilizzando il protocollo Kerberos versione 5 per l'autenticazione IKE, non si impedisce ai computer che non rientrano nel dominio di partecipare all'ambiente IPsec. Se, ad esempio, un sistema UNIX viene configurato adeguatamente per l'utilizzo di Active Directory come area di autenticazione Kerberos e l'implementazione di IKE supporta l'autenticazione Kerberos, potrebbe essere inserito nel dominio di isolamento. Questa configurazione non rientra però nell'ambito della trattazione del presente documento e non è stata testata da Microsoft.
  
##### Intervalli di polling
  
Gli intervalli di polling da considerare sono due: quello di Criteri di gruppo e quello del servizio IPsec. L'impostazione predefinita dell'intervallo di polling per le modifiche dei criteri del servizio IPsec è di 180 minuti fra due polling consecutivi per le modifiche dei criteri IPsec basati su Active Directory. Questi controlli tramite polling solo per le modifiche dei criteri IPsec non rilevano le modifiche delle appartenenze a domini o a unità organizzative (UO) né l'assegnazione o l'annullamento dell'assegnazione di un criterio IPsec in un GPO. Le modifiche delle appartenenze alle UO e delle assegnazioni dei GPO vengono rilevate tramite il polling del servizio Criteri di gruppo che, per impostazione predefinita, viene effettuato ogni 90 minuti.
  
La Woodgrove Bank ha scelto di impostare entrambi gli intervalli di polling su 60 minuti affinché, in caso di esigenze di protezione, sia possibile aggiornare e distribuire i criteri in un'ora, limitando i rischi. Questo incremento della frequenza di polling ha generato un traffico di polling supplementare sotto forma di query LDAP dal client per il controllo dei timestamp dei criteri IPsec. Nonostante questa impostazione non abbia introdotto un carico di lavoro significativo nello scenario della Woodgrove Bank, nelle distribuzioni con un elevato numero di client, questo incremento potrebbe diventare significativo.
  
##### Impostazioni dello scambio di chiavi
  
Le impostazioni seguenti per lo scambio di chiavi specificano la modalità di ottenimento delle nuove chiavi e la frequenza di rinnovo. Il termine "chiave principale" indica il materiale relativo alla chiave segreta condivisa Diffie-Hellman generato in modalità principale IKE. Il termine "chiave di sessione" si riferisce invece alle chiavi generate in modalità rapida IKE e utilizzate negli algoritmi di integrità e crittografia di IPsec. Le chiavi di sessione sono derivate dalla chiave principale.
  
-   **PFS (Perfect Forward Secrecy).** In IKE esistono due tipi di PFS: chiave principale (che significa PFS in modalità principale) e chiave di sessione (che significa PFS in modalità rapida). Si sconsiglia di utilizzare PFS in modalità principale perché questa funzionalità è duplicata da altre impostazioni supportate di scambio delle chiavi. PFS in modalità principale comporta una ripetizione dell'autenticazione da parte di IKE e la negoziazione di una nuova chiave principale tutte le volte che viene eseguita la modalità rapida per aggiornare le chiavi di sessione. Questa impostazione assicura che tutte le volte che è necessario aggiornare una chiave di crittografia, i due computer ripetano la procedura dall'inizio con una nuova negoziazione IKE in modalità principale e in modalità rapida. Questa protezione aggiuntiva incrementa il carico di lavoro. La chiave di sessione PFS genera una nuova chiave principale in modalità rapida (senza l'autenticazione in modalità principale) e genera le nuove chiavi di sessione da questa chiave principale. Tale funzionalità assicura che una grande quantità o tutti i dati della comunicazione non siano protetti soltanto dal valore della chiave principale, a fronte di una piccola quantità di dati crittografati che potrebbe essere rilevata nel caso in cui un pirata informatico riuscisse a scoprire la chiave principale. La chiave di sessione PFS è supportata tramite una casella di controllo nei metodi di protezione dell'operazione filtro. È consigliabile utilizzare la chiave di sessione PFS solo se il traffico protetto da IPsec è esposto al rischio di attacchi sofisticati alla crittografia sulla chiave principale Diffie-Hellman.
  
-   **Autentica e genera una nuova chiave ogni: &lt;*numero&gt;*** **minuti.** Questo valore imposta la durata della SA in modalità principale IKE che, per impostazione predefinita, è di 480 minuti. Controlla il tempo di utilizzo della chiave principale e della relazione di trust che deve trascorrere prima di avviare una nuova negoziazione. Alla prima connessione TCP/IP da un client univoco verso l'host, viene stabilita una SA in modalità principale IKE. A differenza delle SA trasferibili, le SA della modalità principale non vengono eliminate dall'host dopo 5 minuti di inattività. Le SA della modalità principale occupano circa 5 kilobyte di memoria ciascuna. Modificando questo valore, è possibile ottimizzare il carico della CPU e l'utilizzo della memoria da parte di IKE. Riducendo la durata, si diminuisce il numero di SA attive in modalità principale sul server. Ciò comporta una riduzione dell'utilizzo della memoria e un contenimento del tempo di elaborazione di IKE, grazie a un numero inferiore di SA da gestire. Si incrementa però il carico della CPU necessario per la ripetizione delle negoziazioni delle SA in modalità principale per i client che comunicano frequentemente.
  
-   **Autentica e genera una nuova chiave ogni: &lt;*numero&gt;*** **sessione/i.** Questa impostazione controlla il numero massimo di modalità rapide IKE consentito per l'intervallo di durata di una SA in modalità principale, limitando così il numero di chiavi di sessione che vengono generate dalla stessa chiave principale. Quando si raggiunge questo limite, viene negoziata una nuova SA in modalità principale che genera una nuova chiave principale. L'impostazione predefinita è 0 che corrisponde all'assenza di limitazioni. Ciò significa che la chiave principale viene aggiornata soltanto alla scadenza della durata della SA in modalità principale IKE, a meno che non si utilizzi PFS in modalità rapida. Per ottenere il medesimo comportamento dell'impostazione della chiave principale PFS, questa opzione deve essere impostata su 1.
  
La Woodgrove Bank ha scelto di non utilizzare la chiave principale PFS perché non ha specifiche esigenze di protezione che la rendano necessaria. Analogamente, nelle operazioni filtro non viene utilizzata PFS in modalità rapida IKE. La durata delle SA in modalità rapida IKE è stata modificata da 480 minuti a 180 minuti al fine di eliminare più rapidamente le SA in modalità principale sui server di tutti i gruppi, fatta eccezione per il gruppo di isolamento Limite. Per il gruppo di isolamento Limite, gli amministratori della Woodgrove Bank hanno ridotto la durata delle SA in modalità principale IKE a 20 minuti, al fine di limitare l'esposizione agli attacchi offerta dalle SA residenti in modalità principale che vengono negoziate con il gruppo di isolamento Crittografia. Nonostante gli host del gruppo di isolamento Limite non possano avviare nuove negoziazioni IKE con gli host del gruppo di isolamento Crittografia, può però avvenire il contrario. Dopo aver stabilito la SA in modalità principale, un host del gruppo di isolamento Limite ha infatti la possibilità di utilizzare questa associazione per negoziare SA in modalità rapida per la protezione del traffico in ingresso verso il sistema corrispondente del gruppo di isolamento Crittografia e fino a quando la SA in modalità principale non viene eliminata. Questo rischio è stato ridotto imponendo un'eliminazione più frequente delle SA in modalità principale sui server del gruppo di isolamento Limite. Il numero di sessioni in cui è possibile utilizzare la chiave principale per generare una chiave di sessione è stato lasciato sull'impostazione predefinita di 0.
  
##### Metodi di scambio delle chiavi
  
I metodi di scambio delle chiavi controllano i metodi di protezione utilizzanti durante la negoziazione in modalità principale IKE. Le opzioni di configurazione sono relative all'integrità (SHA-1 e MD5), alla confidenzialità o alla crittografia (3DES e DES) e alla lunghezza dei numeri primi della base utilizzati durante il processo di scambio delle chiavi.
  
**Nota:** per utilizzare 3DES, sui computer che eseguono Windows 2000, è necessario installare High Encryption Pack oppure SP2 (o versioni successive).
  
Il livello di crittografia delle chiavi utilizzato per l'integrità e la crittografia della negoziazione IKE stessa e per la protezione IPsec dei dati dipende dal livello del gruppo Diffie-Hellman su cui si basano i numeri primi. Per il gruppo Diffie-Hellman sono disponibili tre opzioni:
  
-   **Alta (3)** - Livello di crittografia a 2048 bit. Questa opzione corrisponde alla specifica RFC 3526 di IETF per il Gruppo Diffie-Hellman 14. Questo livello di crittografia è necessario affinché 3DES raggiunga il livello massimo di crittografia. Per ulteriori informazioni, consultare la specifica RFC 3526 di IETF.
  
-   **Media (2)** - Livello di crittografia a 1024 bit.
  
-   **Min (1)** - Livello di crittografia a 768 bit.
  
L'impostazione Alta può essere utilizzata soltanto con sistemi basati su Windows XP SP2 e Windows Server 2003. L'impostazione Media consente l'interoperabilità con Windows 2000 e Windows XP SP1. L'impostazione Min assicura la compatibilità con le versioni precedenti e non deve essere utilizzata a causa della sua relativa debolezza.
  
La tabella seguente elenca in ordine di preferenza i metodi di protezione dello scambio delle chiavi scelti dalla Woodgrove Bank:
  
**Tabella 5.9. Metodi di protezione predefiniti per lo scambio delle chiavi**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Crittografia</p></th>  
<th><p>Integrità</p></th>  
<th><p>Gruppo Diffie-Hellman</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>3DES</p></td>
<td style="border:1px solid black;"><p>SHA-1</p></td>
<td style="border:1px solid black;"><p>Alta (3) 2048 bit</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>3DES</p></td>
<td style="border:1px solid black;"><p>SHA-1</p></td>
<td style="border:1px solid black;"><p>Media (2) 1024 bit</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>3DES</p></td>
<td style="border:1px solid black;"><p>MD5</p></td>
<td style="border:1px solid black;"><p>Media (2) 1024 bit</p></td>
</tr>  
</tbody>  
</table>
  
**Nota:** per utilizzare il gruppo a 2048 bit in un criterio IPsec, è necessario configurarlo utilizzando gli strumenti di gestione di Windows Server 2003, quali ad esempio lo snap-in MMC Gestione dei criteri di protezione IP o l'utilità Netsh della riga di comando. Questo criterio può essere assegnato a piattaforme Windows 2000 all'interno del dominio, ma queste piattaforme ignoreranno l'opzione relativa ai 2048 bit.
  
##### Versioni dei criteri
  
Durante la pianificazione iniziale, le prove di laboratorio, le distribuzioni pilota e anche durante la fase operativa, è probabile che le configurazioni dei criteri IPsec vengano modificate varie volte. Se, per creare i criteri IPsec, si utilizzano script, fogli di calcolo e altri documenti, è necessario gestire questi file con un sistema di controllo delle versioni simile a Microsoft Visual SourceSafe®.
  
L'identificazione delle versioni dei criteri IPsec tramite l'analisi dei relativi attributi risulta difficoltosa in Active Directory. I passaggi delle procedure di risoluzione dei problemi rendono necessaria l'identificazione della versione del criterio IPsec attivo sul computer ed è quindi consigliabile inserire le informazioni relative alle versioni sia nel nome del criterio che nelle relative regole.
  
Un metodo che semplifica l'identificazione della versione consiste nel creare un ID della versione basato sulla formula seguente:
  
<codesnippet language displaylanguage containsmarkup="false">&lt;Major Change&gt;.&lt;Minor Change&gt;.&lt;Date:yymmdd&gt;.&lt;Time:24 Hour&gt;  
```  
Ad esempio, 1.0.041001.1600 corrisponderà alla versione 1.0 creata il 10/01/04 alle 16:00.
  
Questo ID della versione deve essere posto alla fine del nome del criterio, ad esempio, IPSEC - Criterio IPsec limite (1.0.041001.1600). Può inoltre essere aggiunto al nome o alla descrizione degli elenchi filtri, che cambiano frequentemente.
  
Criteri di gruppo recupera il nome del criterio IPsec e lo archivia nel registro locale in  
**HKEY\_LOCAL\_MACHINE \\SOFTWARE\\**  
**Policies\\Microsoft\\Windows\\IPsec\\GPTIPSECPolicy** dove viene memorizzato come valore stringa nella chiave **DSIPSECNomeCriterio**.
  
Nonostante il polling del servizio IPsec verifichi la presenza di modifiche apportate a tutti gli oggetti dei criteri assegnati, non aggiorna il nome del criterio assegnato che Criteri di gruppo ha archiviato. Criteri di gruppo non aggiorna il nome nel Registro di sistema locale fino a quando l'assegnazione del GPO non viene modificata. Microsoft IT ha rilevato che un mezzo efficace per archiviare le informazioni sulla versione del criterio potrebbe essere una regola non utilizzata del criterio IPsec. È possibile creare un elenco che includa un filtro con indirizzi non validi e associarlo a un'operazione di autorizzazione, come ad esempio:
  
Nome elenco filtri: Ver. criterio IPsec 1.0.041001.1600
  
Descrizione elenco filtri: Ver. criterio IPsec 1.0.041001.1600
  
1.1.1.1 &lt;-&gt; 1.1.1.2, ICMP, descrizione = "ID ver. criterio IPsec 1.0.041001.1600"
  
Dopo aver creato questo elenco di filtri in Active Directory, sarà possibile identificare il nome distinto (DN) dell'oggetto versione assegnato all'elenco filtri mediante la console MMC Utenti e computer di Active Directory eseguita in modalità avanzata. L'oggetto dell'elenco filtri si troverà in &lt;Nome dominio&gt;\\System\\IP Security e sarà identificabile in base alla descrizione.
  
Quando il DN dell'oggetto versione è noto, è possibile confrontarlo a livello di programmazione con gli oggetti IPsec archiviati nel Registro di sistema in **HKEY\_LOCAL\_MACHINE \\SOFTWARE**  
**\\Policies\\Microsoft\\Windows\\IPSec\\Policy\\Cache** per stabilire in quale posizione della cache si trova. Se si individua il DN dell'oggetto versione nella cache, è possibile confrontare i nomi dell'oggetto archiviato in Active Directory e dell'oggetto archiviato nel computer locale. Se i nomi sono uguali, il criterio locale e quello di dominio sono sincronizzati. I nomi e le descrizioni di ciascun elenco di filtri IPsec sono archiviati anche nella cache all'interno del criterio IPsec, il che facilita l'identificazione delle versioni degli oggetti assegnate. Il servizio IPsec conserva in memoria la descrizione di ciascun filtro (e non dell'elenco filtri) affinché lo snap-in del monitor IPsec e gli strumenti della riga di comando possano visualizzare questa informazione.
  
Il controllo della versione del criterio può essere automatizzato utilizzando uno script, quale **Detect\_IPsec\_Policy.vbs** fornito come esempio e incluso nella cartella Strumenti e modelli della presente soluzione.
  
Visto che nel corso del tempo i criteri vengono modificati, è necessario aggiornare i nomi dei filtri relativi affinché riflettano queste modifiche.
  
#### Modalità di applicazione dei criteri IPsec ai singoli computer
  
Il passaggio finale per attivare IPsec consiste nel distribuire i criteri agli host. Per la distribuzione dei criteri sono disponibili due metodi. Il primo consiste nell'applicarli direttamente ai singoli computer host, mentre il secondo prevede l'utilizzo dei GPO e di Active Directory. L'applicazione dei criteri tramite Active Directory è illustrata nella sezione "Modalità di applicazione dei criteri IPsec tramite GPO" del presente capitolo.
  
L'applicazione dei criteri IPsec ai singoli computer può essere effettuata in uno dei due modi seguenti: tramite lo snap-in MMC Gestione criteri di protezione IP o tramite la riga di comando utilizzando Netsh (per Windows Server 2003), **Ipseccmd.exe** (per Windows XP) o **Ipsecpol.exe** (per Windows 2000).
  
Lo snap-in MMC offre un'interfaccia grafica che consente di applicare manualmente i criteri o di importare criteri precedentemente configurati ed esportati da un altro computer. Oltre alla gestione dei criteri sul computer locale, lo snap-in consente agli amministratori di gestire i criteri sui computer remoti.
  
Le informazioni dettagliate sugli strumenti della riga di comando sono disponibili nei documenti seguenti:
  
-   Guida in linea e supporto tecnico per Netsh in Windows Server 2003
  
-   Documentazione sugli strumenti di supporto di Windows XP per **Ipseccmd.exe**
  
-   Windows 2000 Server Resource Kit per **Ipsecpol.exe**
  
La versione più recente del Resource Kit e degli strumenti di supporto è disponibile nell'[area di download del sito Web Microsoft](http://www.microsoft.com/downloads/search.aspx?) all'indirizzo www.microsoft.com/downloads/search.aspx?
  
Con Windows XP SP2, Microsoft ha reso disponibile un aggiornamento di **Ipseccmd** e altri strumenti di supporto. L'articolo numero 838079 "[Strumenti di supporto di Windows XP Service Pack 2](http://support.microsoft.com/?kbid=838079)" della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/?kbid=838079.
  
Le informazioni dettagliate sull'utilizzo di questi strumenti non rientrano nell'ambito della trattazione di questa guida. Gli esempi riportati sono relativi all'utilizzo di Netsh su server che eseguono Windows Server 2003.
  
#### Modalità di applicazione dei criteri IPsec tramite GPO
  
Criteri di gruppo di Active Directory viene utilizzato come meccanismo per l'assegnazione e la distribuzione dei criteri ai computer aggiunti a un dominio. Prima di distribuire i criteri in Active Directory tramite il meccanismo di distribuzione Criteri di gruppo, è necessario configurare i GPO che verranno utilizzati per applicare i criteri IPsec ai computer host.
  
**Nota:** nonostante la sezione seguente illustri il caricamento dei criteri IPsec direttamente in Active Directory, si presuppone che tali criteri siano stati creati e testati su un sistema locale, in un laboratorio di prova e in progetti pilota su scala ridotta, prima di procedere alla distribuzione nell'ambiente di produzione.
  
##### Modalità di caricamento dei criteri IPsec in Active Directory
  
La prima attività da completare per implementare i criteri IPsec tramite Active Directory consiste nel creare gli elenchi filtri, le operazioni filtro e i criteri IPsec nel servizio di directory. È possibile effettuare questa attività mediante lo snap-in MMC Gestione criteri di protezione IP o uno strumento della riga di comando, come ad esempio Netsh. Indipendentemente dallo strumento scelto, per implementare i criteri IPsec è necessario completare le seguenti tre attività secondarie:
  
1.  Creare gli elenchi e i filtri indicati nella sezione "Elenchi filtri IPsec" del presente capitolo.
  
2.  Creare le operazioni filtro indicate nella sezione "Operazioni filtro IPsec" del presente capitolo.
  
3.  Creare i criteri IPsec indicati nella sezione "Criteri IPsec" del presente capitolo.
  
###### Utilizzo dello snap-in MMC Gestione criteri di protezione IP
  
Lo snap-in Gestione criteri di protezione IP è uno strumento basato su un'interfaccia grafica che consente di creare, configurare e modificare i criteri IPsec su computer locali, remoti e domini. La configurazione dei componenti di IPsec è un processo manuale che include la modifica degli oggetti creati, assistito da procedure guidate.
  
Dopo aver configurato i criteri IPsec localmente o in Active Directory, è possibile esportarli (inclusi tutti gli elenchi filtri e le operazioni filtro) per modificarli creando un file con estensione .ipsec. Questo file può essere copiato su altri supporti per consentire il backup.
  
Se esiste una copia di backup dei criteri IPsec, è possibile utilizzare questo strumento anche per importare i criteri in Active Directory. Questo approccio consente di ripristinare e spostare i file dei criteri IPsec da un insieme di strutture di test a uno di produzione, senza dover ricreare manualmente tutti gli elenchi filtri, le operazioni filtro e i criteri. Verificare attentamente la configurazione dei criteri che vengono ripristinati dal backup. Si consiglia di effettuare un test, per verificare l'impatto dell'applicazione di impostazioni precedenti sull'ambiente. Un file di backup di date precedenti potrebbe, infatti, contenere impostazioni dei criteri, quali elenchi filtri oppure operazioni filtro, che non sono più valide e che potrebbero causare un'interruzione delle comunicazioni se assegnate agli attuali membri del dominio.
  
Per ulteriori informazioni sull'utilizzo dello snap-in MMC Gestione criteri di protezione IP, consultare l'argomento "Definizione dei criteri IPsec" nella Guida in linea e supporto tecnico di Windows Server 2003.
  
###### Utilizzo di Netsh
  
In alternativa allo snap-in MMC Gestione criteri di protezione IP, è possibile utilizzare Netsh per la configurazione dei criteri IPsec in un servizio Active Directory basato su Windows Server 2003. Questo strumento della riga di comando può essere eseguito in modalità interattiva o batch. Se viene utilizzato in modalità interattiva, l'amministratore dovrà digitare i singoli comandi nella shell dei comandi di Netsh. Prima di creare gli elenchi filtri, le operazioni filtro e i criteri IPsec, è necessario configurare lo strumento affinché punti su Active Directory.
  
Per puntare Netsh su Active Directory, digitare il comando seguente al prompt di **Netsh**:
  
<codesnippet language displaylanguage containsmarkup="false">ipsec static set store location=domain  
```  
Sarà quindi possibile immettere manualmente gli elenchi filtri, le operazioni filtro e i criteri IPsec utilizzando la shell dei comandi di Netsh. Analogamente allo strumento dotato di interfaccia grafica, Netsh supporta l'esportazione e l'importazione dei file dei criteri IPsec per il backup e il ripristino.
  
L'esecuzione di Netsh in modalità batch implica la creazione di un file di script dei comandi Netsh. Questo file di script deve includere il comando necessario per impostare come attivo il dominio, nonché tutti i comandi di configurazione per gli elenchi filtri, i filtri, le operazioni filtro e i criteri IPsec.
  
È possibile creare le informazioni sui criteri IPsec in Active Directory avviando Netsh ed eseguendo il file di script. La sintassi della riga di comando per lanciare Netsh ed eseguire un file di script è la seguente:
  
<codesnippet language displaylanguage containsmarkup="false">netsh –f &lt;scriptfile&gt;  
```  
Per ulteriori informazioni sull'utilizzo di Netsh, consultare l'argomento "Netsh" nella sezione "Strumenti di amministrazione e script" della Guida in linea e supporto tecnico di Windows Server 2003.
  
**Nota:** Netsh funziona solo con i criteri IPsec dei computer che eseguono Windows Server 2003. Per manipolare i criteri IPsec tramite la riga di comando sui computer che eseguono Windows 2000 o Windows XP, è necessario utilizzare **Ipsecpol.exe** e **Ipseccmd.exe,** rispettivamente. Inoltre, Netsh elenca un comando **dump** nel contesto IPsec dello strumento. Questa funzione non viene implementata, nonostante sia elencata nel testo di descrizione. A differenza dello strumento dotato di interfaccia grafica, Netsh non supporta le connessioni remote.
  
##### Creazione di oggetti di Criteri di gruppo per la distribuzione di criteri IPsec
  
I GPO sono oggetti archiviati in Active Directory che definiscono una serie di impostazioni da applicare a un computer. I criteri IPsec non vengono archiviati direttamente nei GPO, che conservano invece un collegamento al nome distinto LDAP del criterio IPsec. I criteri IPsec vengono archiviati nella posizione cn=IP Security, cn=System, dc=&lt;dominio&gt; di Active Directory.
  
I GPO vengono assegnati a siti, domini o UO all'interno di Active Directory. I computer che si trovano in questi contenitori o posizioni ricevono il criterio specificato nel GPO, se non impedito in altro modo. Il team di progettazione di IPsec dovrà consultarsi con quello di Active Directory per discutere l'opportunità di utilizzare i GPO esistenti per recapitare i criteri IPsec. Se questo approccio non è attuabile o richiede notevoli modifiche delle procedure di gestione, è possibile creare nuovi GPO per ciascuna serie di criteri IPsec che verrà distribuita. La soluzione descritta in queste istruzioni utilizza GPO nuovi per la distribuzione dei criteri IPsec.
  
Nonostante sia possibile creare i GPO mediante gli snap-in Utenti e computer di Active Directory o Siti e servizi di Active Directory, si consiglia di crearli utilizzando la console di gestione Criteri di gruppo (GPMC). La creazione dei criteri tramite gli strumenti di Active Directory collega automaticamente i GPO all'oggetto che viene esplorato. Se invece si utilizza la console GPMC per creare i GPO, è possibile accertarsi che vengano creati in Active Directory ma non applicati ai computer fino a quando ciascuno di essi non verrà esplicitamente collegato a un sito, un dominio o una UO.
  
La console di gestione Criteri di gruppo è un'utilità aggiuntiva per i computer che eseguono Windows XP Service Pack 1 (o versioni successive) o Windows Server 2003. È uno strumento che consente di gestire criteri di gruppo per più domini e siti in uno o più insiemi di strutture mediante un'interfaccia utente semplice, in cui è possibile trascinare e rilasciare gli elementi selezionati. Fra le caratteristiche principali, figurano funzionalità di backup, ripristino, importazione, copia e creazione di report per i GPO. Queste operazioni possono essere eseguite tramite script e, quindi, gli amministratori possono personalizzare e automatizzare le attività di gestione. Si noti che queste tecniche di gestione dei GPO si applicano alla gestione degli oggetti dei criteri IPsec stessi. È necessario elaborare una strategia di gestione dei criteri IPsec coordinata con quella dei GPO che li recapitano.
  
Per ulteriori informazioni sull'utilizzo della console GPMC, consultare il white paper "[Administering Group Policy with the GPMC](http://www.microsoft.com/windowsserver2003/gpmc/gpmcwp.mspx)", disponibile sul sito Web Microsoft all'indirizzo www.microsoft.com/windowsserver2003/gpmc/  
gpmcwp.mspx.
  
La [Console di gestione Criteri di gruppo con Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0a6d4c24-8cbd-4b35-9272-dd3cbfc81887&displaylang=en) è disponibile per il download all'indirizzo www.microsoft.com/downloads/details.aspx?  
FamilyId=0A6D4C24-8CBD-4B35-9272-DD3CBFC81887&displaylang=en (in lingua inglese).
  
Utilizzando la console GPMC, è possibile creare un GPO per ciascun criterio IPsec effettuando i passaggi seguenti:
  
**Per creare un nuovo GPO**
  
1.  Espandere la struttura del dominio, fare clic con il pulsante destro del mouse sul contenitore **Oggetti Criteri di gruppo** e scegliere **Nuovo**.
  
2.  Digitare il nome di un nuovo GPO, quindi fare clic su **OK**.
  
Come nel caso delle operazioni filtro e dei criteri IPsec, è necessario definire uno standard di denominazione per i GPO, che includa un numero di versione del criterio all'interno del nome, visto che le informazioni sulle versioni degli oggetti di Active Directory non sono facilmente ottenibili. Includendo un numero di versione nel nome del criterio, è quindi possibile identificare rapidamente quale criterio è attivo. Microsoft consiglia di utilizzare la medesima convezione di denominazione descritta precedentemente in questo capitolo per le operazioni filtro e i criteri IPsec. Ad esempio, l'oggetto GPO denominato "GPO dominio di isolamento IPsec ver 1.0.040601.1600" indicherà la versione 1.0 creata il giorno 06/01/04 alle 16:00.
  
Dopo aver creato il GPO, sarà necessario configurarlo affinché utilizzi il criterio IPsec appropriato.
  
**Assegnazione del criterio IPsec in un GPO**
  
1.  Avviare l'editor dei criteri di gruppo facendo clic con il pulsante destro del mouse sul nome del GPO e scegliendo **Modifica**.
  
2.  I criteri IPsec che possono essere assegnati sono disponibili in Configurazione computer\\\\Impostazioni di Windows\\\\Impostazioni protezione\\Criteri di protezione IP in Active Directory.
  
3.  Per assegnare un criterio IPsec, fare clic con il pulsante destro del mouse nel riquadro destro e scegliere **Assegna**.
  
    -   È possibile assegnare un solo criterio IPsec a un GPO.
  
4.  Per salvare le modifiche apportate al GPO, chiudere l'editor dei criteri di gruppo.
  
Il criterio IPsec viene applicato ai computer host tramite le impostazioni di configurazione del computer nel GPO. Se il GPO viene utilizzato soltanto per applicare i criteri IPsec, si consiglia di configurarlo in modo che disattivi le impostazioni di configurazione dell'utente. Disattivando queste impostazioni, è infatti possibile ridurre il tempo di elaborazione del GPO, evitando la valutazione delle opzioni di configurazione dell'utente.
  
**Disattivazione della configurazione dell'utente nel GPO**
  
1.  Aprire la console di gestione Criteri di gruppo.
  
2.  Fare clic con il pulsante destro del mouse sul nome del GPO all'interno della console GPMC.
  
3.  Selezionare **Stato criteri di gruppo**, quindi scegliere **Impostazioni configurazione utente attivate**.
  
Se nel GPO vengono successivamente specificate le impostazioni di configurazione utente, l'amministratore dovrà riattivare l'elaborazione delle impostazioni di configurazione utente per riapplicarle.
  
##### Gruppi di protezione del dominio
  
I gruppi di protezione del dominio hanno due funzioni. La prima consiste nell'identificare gli account computer del dominio che sono membri di un gruppo di isolamento, mentre la seconda consiste nell'identificare gli account computer del dominio che sono membri di un gruppo di accesso alla rete.
  
Tutti i membri di un gruppo di isolamento devono ricevere il medesimo criterio IPsec ed è quindi possibile creare gruppi di protezione del dominio che consentano di applicare e gestire i criteri IPsec, invece di controllare l'assegnazione utilizzando i contenitori UO. I gruppi universali sono l'opzione migliore per controllare l'assegnazione dei criteri poiché possono essere applicati all'intero insieme di strutture e quindi riducono il numero di gruppi da gestire. Se, però, i gruppi universali non sono disponibili, è possibile utilizzare i gruppi globali di dominio. I gruppi globali di dominio vengono utilizzati per i gruppi di accesso alla rete, illustrati nelle sezioni successive.
  
La tabella seguente elenca i gruppi creati per lo scenario della Woodgrove Bank che consentono di gestire l'ambiente IPsec e controllare l'applicazione dei criteri:
  
**Tabella 5.10. Nomi dei gruppi IPsec**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome gruppo</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>No IPsec</p></td>
<td style="border:1px solid black;"><p>Gruppo universale di account computer che non rientrano nell'ambiente IPsec. Solitamente, include gli account computer di infrastruttura.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>CG_IsolationDomain_computers</p></td>
<td style="border:1px solid black;"><p>Gruppo universale di account computer membri del dominio di isolamento.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>CG_BoundaryIG_computers</p></td>
<td style="border:1px solid black;"><p>Gruppo universale di account computer membri del gruppo di isolamento Limite e quindi autorizzati a comunicare con sistemi non attendibili.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>CG_NoFallbackIG_computers</p></td>
<td style="border:1px solid black;"><p>Gruppo universale di account computer membri del gruppo di isolamento Nessun fallback e quindi <em>non</em> autorizzati ad effettuare comunicazioni in uscita non autenticate.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>CG_EncryptionIG_computers</p></td>
<td style="border:1px solid black;"><p>Gruppo universale di account computer membri del gruppo di isolamento Crittografia, le cui comunicazioni devono essere crittografate.</p></td>
</tr>  
</tbody>  
</table>
  
Oltre ai gruppi elencati, è possibile creare gruppi supplementari e utilizzarli per limitare l'applicazione dei criteri durante la distribuzione iniziale. In fase di distribuzione di IPsec, non è consigliabile limitarsi a creare i GPO e i criteri IPsec e assegnarli simultaneamente a tutti i computer del dominio. È possibile utilizzare un gruppo di protezione del dominio che consenta di controllare puntualmente quali computer sono autorizzati a leggere i GPO e quindi a ricevere il corrispondente criterio IPsec. È possibile assegnare all'intero dominio i GPO che recapitano i criteri IPsec. Durante il processo di distribuzione, è necessario valutare attentamente se il criterio IPsec è stato correttamente configurato, assegnato e recuperato su tutti i nodi che devono eseguire la negoziazione IPsec. La configurazione del criterio del gruppo limite viene tipicamente utilizzata per consentire le comunicazioni non protette da IPsec sia in ingresso che in uscita con computer che non hanno ancora ricevuto il rispettivo criterio IPsec.
  
##### Distribuzione dei criteri IPsec tramite Active Directory
  
È possibile controllare quali GPO vengono assegnati ai computer in Active Directory utilizzando i tre metodi seguenti:
  
-   UO con GPO collegati
  
-   Inserimento degli account computer in gruppi di protezione, a cui si faccia riferimento in ACL applicati ai GPO.
  
-   Utilizzo di filtri di Strumentazione gestione Windows (WMI) sui GPO.
  
La forma più comune di applicazione dei criteri in Active Directory consiste nel controllare l'applicazione dei GPO tramite le UO con GPO collegati. Questo metodo crea delle UO in Active Directory e collega i GPO a siti, domini oppure UO. I computer ricevono i criteri sulla base della loro posizione in Active Directory. Se un computer viene spostato in una diversa UO, il criterio collegato alla seconda UO verrà applicato quando Criteri di gruppo rileva il cambiamento durante il polling.
  
Il secondo metodo utilizza le impostazioni di protezione sui GPO stessi. Viene aggiunto un gruppo all'ACL del GPO in Active Directory. A questo gruppo vengono poi assegnati i diritti di lettura e applicazione dei criteri di gruppo sul criterio che deve essere applicato ai computer del gruppo. Inoltre, al gruppo vengono specificatamente negate le autorizzazioni sui criteri che non devono essere applicati ai computer del gruppo. Il criterio viene quindi collegato al livello di dominio.
  
Il terzo metodo utilizza i filtri VMI sul criterio al fine di controllare dinamicamente l'ambito di applicazione del criterio. Prevede la creazione di un filtro SQL WMI che viene collegato al criterio. Se la condizione della query è vera, il criterio viene applicato; in caso contrario, viene invece ignorato. I computer che eseguono Windows 2000 ignorano il filtraggio WMI e applicano il criterio. Le query WMI possono rallentare l'elaborazione dei GPO e devono essere utilizzate soltanto quando necessario.
  
La Woodgrove Bank ha scelto di utilizzare i gruppi di protezione per controllare l'applicazione dei criteri, invece di collegarli direttamente a una UO. Ha optato per questo approccio al fine di introdurre i criteri IPsec senza difficoltà nell'ambiente e senza dover forzare i criteri in più posizioni o imporre uno spostamento di computer da una UO a un'altra affinché i computer ricevano il criterio appropriato. A meno che gli ACL dei GPO non siano estremamente ampi, non si genera alcun carico supplementare con questo metodo rispetto al primo, perché in entrambi i casi gli ACL devono essere valutati. La Woodgrove ha scartato il filtraggio WMI perché nell'ambiente sono presenti dei sistemi Windows 2000.
  
La tabella seguente riporta la configurazione finale degli ACL di Criteri di gruppo. Si noti che gli ACL degli oggetti dei criteri IPsec stessi non vengono utilizzati e sono sconsigliati.
  
**Tabella 5.11. Autorizzazioni dei GPO dei criteri della Woodgrove Bank**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome GPO</p></th>  
<th><p>Nome gruppo di protezione</p></th>  
<th><p>Diritti assegnati</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPSEC - Criterio dominio di isolamento</p></td>
<td style="border:1px solid black;"><p>No IPsec</p></td>
<td style="border:1px solid black;"><p>Nega applicazione Criteri di gruppo</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPSEC - Criterio dominio di isolamento</p></td>
<td style="border:1px solid black;"><p>CG_IsolationDomain_computers</p></td>
<td style="border:1px solid black;"><p>Consenti lettura e applicazione dei criteri di gruppo</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPSEC - Criterio gruppo limite</p></td>
<td style="border:1px solid black;"><p>No IPsec</p></td>
<td style="border:1px solid black;"><p>Nega applicazione Criteri di gruppo</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPSEC - Criterio gruppo limite</p></td>
<td style="border:1px solid black;"><p>CG_BoundaryIG_computers</p></td>
<td style="border:1px solid black;"><p>Consenti lettura e applicazione dei criteri di gruppo</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPSEC - Criterio gruppo di isolamento Nessun fallback</p></td>
<td style="border:1px solid black;"><p>No IPsec</p></td>
<td style="border:1px solid black;"><p>Nega applicazione Criteri di gruppo</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPSEC - Criterio gruppo di isolamento Nessun fallback</p></td>
<td style="border:1px solid black;"><p>CG_NoFallbackIG_computers</p></td>
<td style="border:1px solid black;"><p>Consenti lettura e applicazione dei criteri di gruppo</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>IPSEC - Criterio gruppo di isolamento Crittografia</p></td>
<td style="border:1px solid black;"><p>No IPsec</p></td>
<td style="border:1px solid black;"><p>Nega applicazione Criteri di gruppo</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IPSEC - Criterio gruppo di isolamento Crittografia</p></td>
<td style="border:1px solid black;"><p>CG_EncryptionIG_computers</p></td>
<td style="border:1px solid black;"><p>Consenti lettura e applicazione dei criteri di gruppo</p></td>
</tr>  
</tbody>  
</table>
  
###### Dominio di isolamento
  
La Woodgrove Bank ha scelto di collegare il criterio del dominio di isolamento a livello di dominio per ciascun dominio dell'organizzazione. Questo criterio utilizza un ACL che impedisce ai computer che non appartengono al gruppo CG\_IsolationDomain\_computers di applicare il criterio. I diritti di applicazione di Criteri di gruppo per il gruppo Utenti autenticati sono stati eliminati dall'ACL del criterio.
  
Il criterio del dominio di isolamento è il criterio predefinito utilizzato da tutti i computer dell'organizzazione come criterio di protezione IPsec. Conseguentemente, il gruppo Computer del dominio dispone dei diritti di lettura del criterio. I diritti di applicazione di Criteri di gruppo per il gruppo Utenti autenticati sono stati eliminati dall'ACL del criterio. Durante la distribuzione iniziale, il gruppo Computer del dominio è stato eliminato dall'ACL ed è stato temporaneamente utilizzato un altro gruppo di protezione per controllare la distribuzione del criterio. Questo approccio ha consentito una distribuzione in fasi del criterio.
  
###### Gruppo di isolamento Limite
  
La Woodgrove Bank ha scelto di collegare il criterio del gruppo di isolamento Limite a livello di dominio per ciascun dominio dell'organizzazione. Questo criterio utilizza un ACL che impedisce ai computer che non appartengono al gruppo CG\_BoundaryIG\_computers di applicare il criterio. I diritti di applicazione di Criteri di gruppo per il gruppo Utenti autenticati sono stati eliminati dall'ACL del criterio.
  
Se, per ragioni aziendali, è necessario che un sistema accetti le comunicazioni da un sistema non attendibile, è possibile aggiungere l'account computer del sistema al gruppo di protezione CG\_BoundaryIG\_computers.
  
###### Gruppo di isolamento Nessun fallback
  
La Woodgrove Bank ha scelto di collegare il criterio del gruppo di isolamento Nessun fallback a livello di dominio per ciascun dominio dell'organizzazione. Questo criterio utilizza un ACL che impedisce ai computer che non appartengono al gruppo CG\_NoFallbackIG\_computers di applicare il criterio. I diritti di applicazione di Criteri di gruppo per il gruppo Utenti autenticati sono stati eliminati dall'ACL del criterio.
  
Se, per ragioni aziendali, è necessario negare a un sistema la facoltà di avviare le comunicazioni con sistemi non attendibili, è possibile aggiungere l'account computer del sistema al gruppo di CG\_NoFallbackIG\_computers.
  
###### Gruppo di isolamento Crittografia
  
La Woodgrove Bank ha scelto di collegare il criterio del gruppo di isolamento Crittografia a livello di dominio per ciascun dominio dell'organizzazione. Questo criterio utilizza un ACL che impedisce ai computer che non appartengono al gruppo CG\_EncryptionIG\_computers di applicare il criterio. I diritti di applicazione di Criteri di gruppo per il gruppo Utenti autenticati sono stati eliminati dall'ACL del criterio.
  
Se, per ragioni aziendali, è necessario che un sistema comunichi soltanto utilizzando il traffico crittografato, è possibile aggiungere l'account computer del sistema al gruppo CG\_EncryptionIG\_computers.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Autorizzazione dell'accesso in ingresso a un gruppo di isolamento
  
I requisiti della Woodgrove Bank includevano l'esigenza di autorizzare soltanto una subnet di host attendibili ad accedere alla rete in ingresso verso i server del gruppo di isolamento Crittografia. Nella tabella 4.8 del capitolo 4 sono riportati i seguenti gruppi di accesso alla rete (NAG, Network Access Group) per l'implementazione dei requisiti descritti di seguito:
  
-   ANAG\_EncryptedResourceAccess\_Users
  
-   ANAG\_EncryptedResourceAccess\_Computers
  
-   DNAG\_EncryptedResourceAccess\_Computers
  
Quando un client avvia IKE verso un server del gruppo crittografia, IKE deve ottenere un ticket di servizio Kerberos che contenga l'identificativo del gruppo di protezione del dominio, il quale indica se il computer client appartiene al gruppo ANAG e/o possibilmente al gruppo DNAG. Se tutti i computer del gruppo di isolamento Crittografia sono membri del medesimo dominio, è possibile creare questi NAG come gruppi di protezione locali del dominio. Se i computer del gruppo di isolamento Crittografia sono invece membri di domini attendibili diversi, è possibile utilizzare una serie di gruppi globali di dominio per i NAG oppure creare gruppi locali di dominio in ciascun dominio. Lo scenario della Woodgrove Bank include un solo dominio e quindi utilizza gruppi locali di dominio per questi NAG.
  
Al fine di configurare i diritti **Accedi al computer dalla rete** che implementano l'autorizzazione in ingresso, è stato creato il seguente GPO aggiuntivo:
  
-   GPO Autorizzazione rete in ingresso EncryptionIG
  
Al gruppo CG\_EncryptionIG\_Computers sono stati assegnati i diritti di lettura e applicazione per questo GPO. Il gruppo Utenti autenticati è stato eliminato dal diritto di lettura e conseguentemente questo GPO viene applicato soltanto ai computer che sono membri del gruppo di isolamento Crittografia.
  
Come riportato nella Tabella 4.8 del capitolo 4, l'account computer IPS-ST-XP-05 del client di dominio è stato aggiunto al gruppo di accesso alla rete ANAG\_EncryptedResourceAccess\_Computers. Anche gli account IPS-SQL-DFS-01 e IPS-SQL-DFS-02 del server del gruppo di crittografia sono stati aggiunti. Era comunque possibile ottenere il medesimo risultato in modo più semplice, utilizzando il gruppo CG\_EncryptionIG\_computers per gestire un elenco più lungo. In tal caso, agli account deve essere assegnato il diritto **Accedi al computer dalla rete**, sia tramite l'appartenenza a un gruppo ANAG, che tramite l'inclusione diretta del gruppo CG\_EncryptionIG\_computers oppure mediante un'elencazione esplicita di account computer nel diritto. In caso contrario, gli account non potranno stabilire connessioni protette da IPsec fra di loro, necessarie per le applicazioni che eseguono. Per simulare un ambiente con un dominio esteso, i gruppi ANAG sono i soli che autorizzano l'accesso in ingresso nello scenario della Woodgrove Bank.
  
Poiché il gruppo Utenti autenticati include tutti i computer del dominio, deve essere eliminato dal diritto **Accedi al computer dalla rete**. Gli utenti autorizzati del dominio devono essere esplicitamente autorizzati, ad esempio mediante il gruppo incorporato Utenti dominio. La Woodgrove Bank ha però preferito sfruttare la possibilità di definire limitazioni di accesso alla rete in ingresso per gli utenti così come per i computer. Ha quindi creato un gruppo di protezione locale nel dominio, denominato ANAG\_EncryptedResourceAccess\_Users e lo ha popolato con gli account utente delle applicazioni autorizzate (ad esempio, l'utente 7) e con il gruppo degli amministratori locali e i gruppi degli amministratori di dominio. Queste limitazioni di accesso alla rete a livello di utente vengono applicate durante le richieste di autenticazione di protocolli di livello superiore (quali RPC, SMB ed SQL), quando la connettività IPsec ESP-3DES è già stata stabilita.
  
Per i diritti di accesso alla rete dei server di crittografia, sono stati creati i seguenti gruppi di protezione del dominio. Risiedono nel GPO all'interno del diritto **Accedi al computer dalla rete** in Configurazione computer, Impostazioni di Windows, Impostazioni protezione, Criteri locali, Assegnazione diritti utente:
  
-   ANAG\_EncryptedResourceAccess\_Computers
  
-   ANAG\_EncryptedResourceAccess\_Users
  
Per il medesimo GPO **Nega accesso al computer dalla rete,** è stato configurato il gruppo seguente:
  
-   DNAG\_EncryptedResourceAccess\_Computers
  
Presupponendo che l'utente 7 non possa accedere direttamente ai server di crittografia, dovrà utilizzare il computer client IPS-ST-XP-05 per accedere ai server IPS-SQL-DFS-01 o IPS-SQL-DFS-02. Il computer IPS-ST-XP-05 deve disporre di un account computer valido del dominio e di un criterio IPsec attivo che avvii la negoziazione IKE verso gli indirizzi IP dei server di crittografia.
  
Si noti che ai restanti utenti e computer del dominio viene in effetti negato l'accesso perché questi sono stati intenzionalmente omessi dal diritto **Accedi al computer dalla rete**. L'accesso è stato esplicitamente negato soltanto ai computer del gruppo Limite, mediante l'impiego del DNAG, che funge da efficace misura di difesa in caso di future modifiche delle appartenenze ai gruppi che potrebbero includere un account computer del gruppo Limite in un ANAG. Un parametro esplicito di negazione prevale su tutte le forme di autorizzazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Considerazioni aggiuntive su IPsec
  
Oltre alla definizione dei criteri, per un'efficace implementazione di IPsec vanno valutate altre considerazioni. Il foglio di calcolo **Business\_Requirements.xls** della cartella Strumenti e modelli fornisce i dettagli delle limitazioni del servizio IPsec.
  
#### Esenzioni predefinite
  
In Windows 2000 e Windows XP, i seguenti tipi di traffico sono esentati per impostazione predefinita:
  
-   Broadcast
  
-   Multicast
  
-   Protocollo di autenticazione Kerberos
  
-   IKE
  
-   Protocollo RSVP (Resource Reservation Protocol)
  
Nei sistemi operativi della famiglia Windows Server 2003, il traffico proveniente dai protocolli broadcast, multicast, RSVP e Kerberos non è esentato per impostazione predefinita e può creare corrispondenze con i filtri (solo il traffico IKE è esentato). I pacchetti broadcast e multicast vengono scartati se corrispondono a un filtro con un'operazione che negozia la protezione. Per impostazione predefinita, i prodotti della famiglia Windows Server 2003 offrono un supporto limitato per il filtraggio del traffico broadcast e multicast. Un filtro con un indirizzo di origine del tipo Qualsiasi indirizzo IP creerà corrispondenze con gli indirizzi multicast e broadcast. Un filtro con un indirizzo di origine Qualsiasi indirizzo IP e un indirizzo di destinazione Qualsiasi indirizzo IP creerà corrispondenze con gli indirizzi multicast in ingresso e in uscita. Questo filtro può essere utilizzato per bloccare tutto il traffico. I filtri unidirezionali che consentono di bloccare o autorizzare traffico multicast o broadcast specifico non sono supportati.
  
A seguito di una modifica apportata all'implementazione di IPsec nel comportamento di esenzione predefinito dei prodotti della famiglia Windows Server 2003, è necessario verificare il comportamento dei criteri IPsec configurati per Windows 2000 o Windows XP e stabilire se è necessario configurare filtri di autorizzazione espliciti per consentire il passaggio di tipi specifici di traffico. Per ripristinare il comportamento predefinito di Windows 2000 e Windows XP per i criteri IPsec, è possibile utilizzare il comando Netsh o modificare il Registro di sistema.
  
**Ripristino del driver IPsec alla condizione di filtraggio predefinita di Windows 2000 e Windows XP utilizzando Netsh**
  
1.  Al prompt di **Netsh**, digitare il comando seguente e premere **INVIO**:
  
    <codesnippet language displaylanguage containsmarkup="false">netsh ipsec dynamic set config ipsecexempt 0   
```
  
2.  Riavviare il computer.
  
**Esenzione di tutto il traffico broadcast, multicast e IKE dal filtraggio IPsec modificando il Registro di sistema**
  
1.  Impostare la voce **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\**  
    **Services\\IPSEC\\NoDefaultExempt DWORD** del registro sul valore **1**. La chiave **NoDefaultExempt** non esiste per impostazione predefinita e deve essere creata.
  
2.  Riavviare il computer.
  
#### Attraversamento del NAT
  
La modalità di funzionamento dei traduttori di indirizzi di rete (NAT, Network Address Translator) talvolta genera risultati inaspettati sui client che comunicano con i server che eseguono Windows 2000 Server o Windows Server 2003 dietro a un traduttore di indirizzi di rete che utilizza l'attraversamento IPsec del NAT. Per impostazione predefinita, Windows XP SP2 non supporta più le associazioni di protezione di attraversamento IPsec del NAT verso questi server.
  
Questa modifica è stata apportata per evitare un rischio di protezione percepito nelle situazioni in cui si verifica la seguente sequenza di eventi:
  
1.  traduttore di indirizzi di rete configurato per mappare il traffico di attraversamento IKE e IPsec del NAT verso un server su una rete configurata con NAT (server 1).
  
2.  client esterni alla rete configurata con NAT (client 1) che utilizzano l'attraversamento IPsec del NAT per stabilire associazioni di protezione bidirezionali con il server 1.
  
3.  client sulla rete configurata con NAT (client 2) che utilizzano l'attraversamento IPsec del NAT per stabilire associazioni di protezione bidirezionali con il client 1.
  
4.  si verifica una condizione che impone al client 1 di ristabilire le associazioni di protezione con il client 2, a causa dei mapping statici del traduttore di indirizzi di rete che mappano il traffico di attraversamento IKE e IPsec del NAT verso il server 1. Questa condizione potrebbe deviare verso il server 1 il traffico di negoziazione dell'associazione di protezione IPsec inviato dal client 1 e destinato al client 2.
  
Nonostante si tratti di una condizione poco probabile, il comportamento predefinito nei computer basati su Windows XP SP2 impedisce di stabilire associazioni di protezione per l'attraversamento IPsec del NAT con server ubicati dietro un traduttore di indirizzi di rete, al fine di garantire che non si verifichi mai.
  
Se è necessario consentire la comunicazione IPsec attraverso il NAT, si consiglia di utilizzare indirizzi IP pubblici per tutti i server che possono connettersi direttamente da Internet. Se questa configurazione non è attuabile, è possibile modificare il comportamento predefinito di Windows XP SP2 attivando le associazioni di protezione dell'attraversamento IPsec del NAT verso i server ubicati dietro un traduttore di indirizzi di rete.
  
**Per creare e configurare il valore AssumeUDPEncapsulationContextOnSendRule del Registro di sistema**
  
1.  Fare clic su **Start**, scegliere **Esegui**, digitare **regedit**, quindi fare clic su **OK**.
  
2.  Individuare e fare clic sulla seguente sottochiave del Registro di sistema:
  
    <codesnippet language displaylanguage containsmarkup="false">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\ Services\\IPSec  
```
  
3.  Scegliere **Nuovo** dal menu **Modifica**, quindi fare clic su **Valore DWORD**.
  
4.  Nella casella **Nuovo valore \#1,** immettere **AssumeUDPEncapsulationContextOnSendRule** e premere INVIO.
  
    **Nota:** il nome del valore distingue fra maiuscole e minuscole.
  
5.  Fare clic con il pulsante destro del mouse su **AssumeUDPEncapsulationContextOnSendRule**, quindi fare clic su **Modifica**.
  
6.  Nella casella **Dati valore**, digitare uno dei seguenti valori:
  
    -   **0** (impostazioni predefinita). Il valore 0 (zero) configura Windows in modo che il sistema non possa stabilire associazioni di protezione con server ubicati dietro i traduttori di indirizzi di rete.
  
    -   **1**. Il valore 1 configura Windows in modo che il sistema possa stabilire associazioni di protezione con server ubicati dietro i traduttori di indirizzi di rete.
  
    -   **2**. Il valore 2 configura Windows in modo che il sistema possa stabilire associazioni di protezione quando sia il server che il computer client basato su Windows XP SP2 sono ubicati dietro i traduttori di indirizzi di rete.
  
        **Nota:** la configurazione rappresentata dal valore 2 viene utilizzata nella versione originale di Windows XP e in Windows XP Service Pack 1 (SP1).
  
7.  Fare clic su **OK**, quindi chiudere l'Editor del Registro di sistema.
  
8.  Riavviare il computer.
  
Dopo aver configurato **AssumeUDPEncapsulationContextOnSendRule** impostando il valore 1 o 2, Windows XP SP2 è in grado di connettersi a un server ubicato dietro un traduttore di indirizzi di rete.
  
I server basati su Windows Server 2003 necessitano di un aggiornamento per funzionare correttamente con IPsec se ubicati dietro a una periferica NAT. Per informazioni su come ottenere [Windows Server 2003 Service Pack 1](http://go.microsoft.com/fwlink/?linkid=41652), visitare l'URL seguente:
  
http://go.microsoft.com/fwlink/?LinkId=41652 (in lingua inglese)
  
**Nota:** per ulteriori informazioni, consultare l'articolo numero 885348 "[IPSec NAT-T is not recommended for Windows Server 2003 computers that are behind network address translators](http://support.microsoft.com/default.aspx?scid=kb;en-us;885348)" della Microsoft Knowledge Base, disponibile all'indirizzo http://support.microsoft.com/default.aspx?  
scid=kb;en-us;885348. Questo articolo descrive i rischi di protezione derivanti dall'implementazione di questo scenario. Ciascun cliente deve valutare i vantaggi che può offrire IPsec in questo scenario, rispetto ai rischi correlati per la protezione. Nonostante Microsoft sconsigli di implementare questo scenario per i rischi ad esso associati, ne garantisce comunque il supporto se si utilizza la configurazione documentata nella presente soluzione.
  
Affinché sia possibile stabilire le connessioni NAT in ingresso, il rilevamento PMTU deve essere attivato e funzionante. Alcune fonti, quali la *Guida per la protezione di Windows XP* e la *Guida per la protezione di Windows Server 2003*, consigliano di disattivare il rilevamento PMTU e in alcuni casi forniscono modelli di criteri che disattivano questa funzionalità.
  
**    Per attivare il rilevamento del PMTU**
  
1.  Fare clic su **Start**, scegliere **Esegui**, digitare **regedit**, quindi fare clic su **OK**.
  
2.  Individuare e fare clic sulla seguente sottochiave del Registro di sistema:
  
    <codesnippet language displaylanguage containsmarkup="false">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\ Services\\tcpip\\parameters  
```
  
3.  Scegliere **Nuovo** dal menu **Modifica**, quindi fare clic su **Valore DWORD**.
  
4.  Nella casella **Nuovo valore \#1,** immettere **EnablePMTUDiscovery** e premere INVIO.
  
5.  Fare clic con il pulsante destro del mouse su **EnablePMTUDiscovery**, quindi fare clic su **Modifica**.
  
6.  Nella casella **Dati valore**, digitare 1
  
7.  Fare clic su **OK**, quindi chiudere l'Editor del Registro di sistema.
  
8.  Riavviare il computer.
  
Inoltre, per un corretto funzionamento sugli host che eseguono Windows 2000 e partecipano a uno scenario di attraversamento del NAT, è necessario installare l'aggiornamento rapido incluso nell'articolo numero 818043 "[Aggiornamento L2TP/IPSec NAT-T per Windows XP e per Windows 2000](http://support.microsoft.com/kb/818043)" della Microsoft Knowledge Base.
  
Per ulteriori informazioni, consultare gli articoli seguenti della Knowledge Base:
  
-   885407 "[The default behavior of IPSec NAT traversal (NAT-T) is changed in Windows XP Service Pack 2](http://support.microsoft.com/kb/885407)" nel sito del Servizio Supporto Clienti Microsoft all'indirizzo http://support.microsoft.com/kb/885407 (in lingua inglese).
  
-   818043 "[Aggiornamento L2TP/IPSec NAT-T per Windows XP e per Windows 2000](http://support.microsoft.com/kb/818043)" nel sito del Servizio Supporto Clienti Microsoft all'indirizzo http://support.microsoft.com/kb/818043.
  
#### IPsec e Windows Firewall
  
Sui computer che eseguono Windows XP SP2, Windows Firewall offre una protezione aggiuntiva contro gli attacchi, bloccando il traffico non richiesto in ingresso. In Windows XP SP2, IPsec riconosce Windows Firewall. In presenza di un criterio IPsec attivo, i componenti IPsec di Windows XP SP2 indicano a Windows Firewall di aprire le porte UDP 500 e 4500 per consentire il traffico IKE.
  
Una funzionalità supplementare del supporto IPsec consente di specificare mediante Criteri di gruppo se ignorare l'elaborazione di Windows Firewall per il traffico protetto da IPsec. Per ulteriori informazioni, consultare l'appendice A del white paper "[Deploying Windows Firewall Settings for Microsoft Windows XP with Service Pack 2](http://download.microsoft.com/download/6/8/a/68a81446-cd73-4a61-8665-8a67781ac4e8/wf_xpsp2.doc)", disponibile all'indirizzo http://download.microsoft.com/download/  
6/8/a/68a81446-cd73-4a61-8665-8a67781ac4e8/wf\_xpsp2.doc (in lingua inglese).
  
#### IPsec e Firewall connessione Internet (ICF)
  
Per i computer basati su Windows XP su cui non è installato SP2, Firewall connessione Internet (ICF, Internet Connection Firewall) potrebbe soddisfare più efficacemente le esigenze di filtraggio del traffico. ICF esegue il filtraggio ed è in grado di bloccare il traffico multicast e broadcast in ingresso in Windows XP SP1. ICF non riconosce però il traffico protetto da AH o ESP IPsec in modalità di trasporto o tunnel. Visto che IPsec opera su un livello di rete inferiore a quello di ICF, è necessario impostare un'autorizzazione statica per IKE (porta UDP 500) per il traffico in ingresso. Se IPsec blocca il traffico, il registro dei pacchetti scartati del firewall ICF non includerà i pacchetti scartati da IPsec.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Il presente capitolo ha fornito informazioni in merito alla creazione e alla distribuzione dei criteri IPsec basati sulla configurazione dei gruppi di isolamento illustrati nel capitolo 4. Le informazioni sono state suddivise nelle seguenti sette attività di base:
  
-   Identificazione e creazione di elenchi filtri
  
-   Identificazione e creazione di operazioni filtro
  
-   Identificazione e creazione di regole
  
-   Identificazione e creazione di criteri IPsec
  
-   Scelta di un meccanismo di distribuzione per i criteri IPsec
  
-   Scelta di un metodo di distribuzione per i criteri IPsec
  
-   Definizione delle autorizzazioni per il controllo degli accessi in ingresso utilizzando la configurazione dei diritti di accesso alla rete di Criteri di gruppo
  
Queste attività completano le fasi di configurazione e pianificazione della soluzione di isolamento del server e del dominio. La fase successiva del progetto prevede la distribuzione in un ambiente di test o pilota che consenta di verificare la configurazione. Microsoft ha effettuato questa verifica nei propri laboratori di prova e ha utilizzato lo scenario della Woodgrove Bank come progetto pilota. Se si desidera ricreare questo ambiente o analizzare le fasi di distribuzione, l'appendice C di questa guida contiene le istruzioni dettagliate del processo di distribuzione che Microsoft ha utilizzato nei propri laboratori di prova per convalidare la configurazione di questo scenario.
  
#### Ulteriori informazioni
  
Questa sezione fornisce collegamenti a informazioni aggiuntive sulle tecnologie menzionate nel presente capitolo.
  
##### Informazioni di carattere generale su IPsec
  
-   La [home page di IPsec](http://www.microsoft.com/ipsec) del sito Web Microsoft:
  
    www.microsoft.com/ipsec (in lingua inglese)
  
-   La pagina dedicata a [IPsec](http://www.microsoft.com/windowsserver2003/technologies/networking/ipsec/default.mspx) della sezione di Windows Server 2003 nel sito Web Microsoft offre una vasta gamma di documenti specifici riguardanti IPsec per Windows Server 2003: www.microsoft.com/windowsserver2003/technologies/  
    networking/ipsec/  
    default.mspx (in lingua inglese).
  
-   Il capitolo [Deploying IPsec](http://technet.microsoft.com/en-us/library/cc737024.aspx) nel *Windows Server 2003 Deployment* *Kit*: www.microsoft.com/resources/documentation/  
    WindowsServ/2003/all/deployguide/en-us/DNSBJ\_IPS\_OVERVIEW.asp.
  
##### Informazioni aggiuntive
  
-   La pagina [http://technet.microsoft.com/en-us/library/cc758751.aspx](http://www.microsoft.com/windowsserver2003/technologies/management/grouppolicy/default.mspx) del sito Web Microsoft fornisce un'ampia gamma di informazioni sulla gestione dei sistemi Windows con Criteri di gruppo di Active Directory: www.microsoft.com/windowsserver2003/technologies/  
    management/grouppolicy/  
    default.mspx (in lingua inglese).
  
-   L'articolo di *The Cable Guy* "[Problems with Using Network Address Translators](http://www.microsoft.com/technet/community/columns/cableguy/cg1004.mspx)" (ottobre 2004) fornisce ulteriori informazioni sui problemi specifici del servizio NAT e di IPsec. Questo articolo è disponibile sul sito Web di Microsoft.
  
    www.microsoft.com/technet/community/columns/  
    cableguy/cg1004.mspx.
  
**Scarica la soluzione completa**
  
[Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=33947)
  
[](#mainsection)[Inizio pagina](#mainsection)
