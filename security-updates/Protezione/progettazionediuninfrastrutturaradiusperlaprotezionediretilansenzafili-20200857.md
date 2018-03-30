---
TOCTitle: 'Progettazione di un''infrastruttura RADIUS per la protezione di reti LAN senza fili'
Title: 'Progettazione di un''infrastruttura RADIUS per la protezione di reti LAN senza fili'
ms:assetid: '6b78f346-f0e1-4094-b8c5-6604b25c1eaf'
ms:contentKeyID: 20200857
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536258(v=TechNet.10)'
---

Pianifica la protezione di una LAN wireless con Windows Server 2003 Certificate Services
========================================================================================

### Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili

##### In questa pagina

[](#ejaa)[Argomenti del modulo](#ejaa)
[](#eiaa)[Obiettivi](#eiaa)
[](#ehaa)[Ambito di applicazione](#ehaa)
[](#egaa)[Utilizzo del modulo](#egaa)
[](#efaa)[Utilizzo di IAS per la gestione dell'accesso alla rete](#efaa)
[](#eeaa)[Identificazione dei requisiti per la soluzione](#eeaa)
[](#edaa)[Progettazione dell'infrastruttura RADIUS](#edaa)
[](#ecaa)[Creazione di un piano di gestione](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Argomenti del modulo

L'obiettivo principale di questo modulo consiste nel descrivere l'architettura e la progettazione dell'infrastruttura IAS (Servizio di Autenticazione Internet Microsoft®, Internet Authentication Service) utilizzata in questa soluzione. La prima funzione del modulo è di presentare le decisioni di progettazione relative all'infrastruttura IAS per la soluzione e il ragionamento sotteso a tali decisioni. Il secondo scopo di questo modulo è di facilitare la determinazione dell'adeguatezza della progettazione per l'organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Il modulo consente di:

-   Definire l'utilizzo di IAS per fornire una soluzione di gestione dell'accesso alla rete.

-   Identificare i requisiti per la progettazione di un'infrastruttura RADIUS.

-   Comprendere le decisioni di progettazione al momento di ideare l'architettura dell'infrastruttura RADIUS basata su IAS.

-   Esplorare le possibili strategie di gestione dell'infrastruttura del server IAS.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Questo modulo si applica ai seguenti prodotti e tecnologie:

-   Microsoft Windows® Server™ 2003

-   Servizio di Autenticazione Internet (IAS)

-   RADIUS (Remote Authentication Dial-in User Service)

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

In questo modulo viene fornita una panoramica della modalità di utilizzo di IAS per fornire una soluzione di accesso a una rete LAN senza fili (WLAN, Wireless LAN). È possibile adattare la metodologia utilizzata nella propria organizzazione e utilizzare le linee guida presentate in questo modulo con una infrastruttura RADIUS già esistente.

Per sfruttare al massimo il presente modulo:

-   Leggere il manuale "Internet Authentication Service" che fa parte del Microsoft Windows Server 2003 Resource Kit. In questo modo si acquisirà una conoscenza dei concetti dell'infrastruttura RADIUS e delle opzioni di distribuzione di IAS.

    <http://www.microsoft.com/windowsserver2003/techinfo/reskit/resourcekit.mspx> (in inglese).

-   Leggere il manuale "Deploying IAS" che fa parte del Microsoft Windows Server 2003 Deployment Kit. Si disporrà in tal modo di linee guida sulla distribuzione per utilizzare IAS in svariate situazioni non rientranti nell'ambito della protezione di un rete senza fili.

    <http://www.microsoft.com/windowsserver2003/techinfo/reskit/deploykit.mspx> (in inglese).

-   Utilizzare Internet Authentication Service Technology Center, che rappresenta un ottimo punto di partenza per informazioni esaustive e aggiornate su IAS.

    <http://www.microsoft.com/windowsserver2003/technologies/ias/default.mspx> (in inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo di IAS per la gestione dell'accesso alla rete

Il Servizio di Autenticazione Internet (IAS) incluso in Windows Server 2003 rappresenta l'implementazione Microsoft di un server e un proxy RADIUS. In qualità di server RADIUS, IAS esegue l'autenticazione, l'autorizzazione e l'accounting centralizzati di vari tipi di connessioni di rete. In qualità di proxy RADIUS, IAS è in grado di inoltrare le richieste RADIUS a un altro server RADIUS per l'esecuzione delle su indicate funzioni. IAS può essere utilizzato insieme con i server VPN (Rete privata virtuale, Virtual Private Network), ad esempio il servizio Routing e Accesso remoto (RRAS, Routing and Remote Access Service) basato su Microsoft Windows, o con un'altra infrastruttura di accesso alla rete, ad esempio i punti di accesso senza fili e i dispositivi Ethernet di autenticazione.

Per ottenere il massimo da un'infrastruttura RADIUS basata su IAS, occorre prendere una decisione mirata allo sfruttamento dei servizi centralizzati per la gestione dell'accesso alla rete che interessi l'intera azienda. Ciò include l'utilizzo di un database di account centralizzato, quale il servizio directory Microsoft Active Directory®, e la centralizzazione della gestione dei criteri di accesso alla rete su server IAS. Mediante la gestione centralizzata è possibile ridurre drasticamente i costi associati alla gestione delle informazioni per il controllo dell'accesso alla rete memorizzate su dispositivi distribuiti. Inoltre, il ricorso ad account e a criteri di accesso alla rete centralizzati consente di ridurre i rischi di sicurezza associati alla configurazione e alla gestione dei dispositivi distribuiti.

La pianificazione e la distribuzione di un'infrastruttura IAS rispondente alle esigenze presenti e future dell'organizzazione richiedono un'attenta considerazione. IAS non è stato ideato per fornire l'accesso a una rete isolata, quanto piuttosto per consentire una gestione strategica dell'accesso alla rete in diversi contesti.

#### Identificazione dei requisiti dell'organizzazione in termini di gestione dell'accesso alla rete

Il Servizio di Autenticazione Internet (IAS) incluso in Windows Server 2003 supporta vari scenari di accesso alla rete, tra cui i seguenti:

-   **Accesso senza fili**. È possibile configurare punti di accesso senza fili compatibili con lo standard 802.1X affinché utilizzino i servizi di autenticazione, autorizzazione e accounting di IAS per il controllo dell'accesso WLAN basato sullo standard 802.11, nonché per la gestione delle chiavi.

-   **Accesso cablato**. È possibile configurare i dispositivi Ethernet conformi allo standard 802.1X affinché utilizzino i servizi di autenticazione, autorizzazione e accounting di IAS per il controllo dell'accesso per porta e li forniscano alle reti locali cablate (LAN).

-   **Accesso VPN**. È possibile configurare i server VPN, ad esempio RRAS basato su Windows, affinché utilizzino i servizi di autenticazione, autorizzazione e accounting di IAS per il controllo dell'accesso alla rete aziendale, nonché per la gestione delle chiavi.

-   **Connessione remota**. È possibile configurare i server di connessione remota, ad esempio RRAS basato su Windows, affinché utilizzino i servizi di autenticazione, autorizzazione e accounting di IAS per il controllo dell'accesso alla rete aziendale.

-   **Accesso Extranet**. I server di accesso Extranet possono utilizzare i servizi di autenticazione, autorizzazione e accounting di IAS quando forniscono ai partner aziendali l'accesso limitato alle risorse condivise.

-   **Gestione esterna dell'accesso alla rete aziendale**. I fornitori di soluzioni di rete possono utilizzare i servizi di autenticazione, autorizzazione e accounting di IAS per integrare l'infrastruttura di rete gestita esternamente con i database degli account e i criteri di controllo dell'accesso in uso presso i clienti. IAS è in grado di fornire le informazioni di accounting necessarie per fatturare questo servizio ai clienti.

-   **Accesso Internet**. I provider di servizi Internet (ISP, Internet Service Provider) possono utilizzare i servizi di autenticazione, autorizzazione e accounting di IAS per fornire l'accesso a Internet in connessione remota e ad alta velocità sfruttando al contempo i database degli account e i criteri di controllo dell'accesso in uso presso le singole organizzazioni. IAS è in grado di fornire le informazioni di accounting necessarie per fatturare questo servizio ai clienti.

Per ottimizzare l'investimento in un'infrastruttura IAS e ridurre al minimo le modifiche future, è opportuno valutare ciascuno degli scenari in rapporto alla propria organizzazione. Sebbene IAS venga utilizzato in questa soluzione solo per l'accesso alla rete senza fili, il suo impiego potrebbe essere esteso a supporto di ciascuno di tali scenari. Per informazioni sull'estensione dell'infrastruttura RADIUS a supporto di altri scenari, fare riferimento al modulo "[Architettura della soluzione di rete LAN senza fili protetta](http://technet.microsoft.com/it-it/library/dd536256)".

#### Utilizzo di IAS per la gestione dell'accesso alla rete senza fili

In seguito all'adozione di standard di settore quali IEEE (Institute of Electrical and Electronics Engineers) 802.11 e 802.11b, le reti WLAN stanno diventando sempre più diffuse. Questo tipo di rete consente agli utenti di spostarsi all'interno di un edificio o di un gruppo di edifici e, allo stesso tempo, avere la possibilità di collegarsi automaticamente alla rete mediante un punto di accesso senza fili (AP, Access Point).

Pur essendo estremamente pratiche, le reti WLAN presentano i seguenti rischi per la sicurezza:

-   Chiunque disponga di una scheda WLAN compatibile può ottenere l'accesso alla rete.

-   I segnali delle reti senza fili utilizzano le onde radio per inviare e ricevere informazioni. Chiunque si trovi nel raggio d'azione di un punto di accesso senza fili può individuare e ricevere tutti i dati inviati da e verso tale punto di accesso.

Per ovviare al primo rischio, è possibile impostare i punti di accesso senza fili come client RADIUS e, quindi, configurarli per inviare le richieste di accesso e i messaggi di accounting a un server RADIUS centrale in cui viene eseguito IAS. Per far fronte al secondo rischio, è possibile crittografare i dati scambiati tra i dispositivi senza fili e i punti di accesso senza fili.

IAS fornisce una protezione avanzata per le reti WLAN fungendo da server RADIUS per i punti di accesso senza fili e per i dispositivi client IEEE 802.1X, nonché fornendo chiavi di crittografia dinamiche mediante protocolli di autenticazione basati su certificati, ad esempio il protocollo EAP-TLS (Extensible Authentication Protocol-Transport Layer Security).

**Nota:** in questa guida, per descrivere i punti di accesso senza fili si ricorre anche all'espressione client RADIUS. Sebbene i punti di accesso senza fili non siano il solo tipo possibile di client RADIUS, sono gli unici trattati in questa guida e, pertanto, le due espressioni vengono utilizzate come se fossero dei sinonimi.

[](#mainsection)[Inizio pagina](#mainsection)

### Identificazione dei requisiti per la soluzione

Prima di iniziare a progettare una soluzione di gestione dell'accesso senza fili mediante IAS, occorre essere certi di aver compreso i requisiti esistenti necessari relativi all'ambiente.

#### Considerazioni su Active Directory

Questa soluzione si rivolge alle organizzazioni che adottano Active Directory e utilizzano Microsoft Windows 2000 Server o versioni successive nei controller di dominio. Questa condizione è essenziale in quanto in materia di progettazione dell'infrastruttura RADIUS sono state prese diverse decisioni che implicano l'utilizzo di funzionalità disponibili solo in domini Windows 2000 (o versioni successive) in modalità nativa. Nella tabella seguente vengono illustrate alcune funzionalità utilizzate in questa soluzione e il relativo supporto nei vari livelli di funzionalità di un dominio.

**Tabella 1. Funzionalità di Windows 2000 utilizzate nella soluzione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Funzionalità</th>
<th style="border:1px solid black;" >Windows Server 2003 in modalità nativa</th>
<th style="border:1px solid black;" >Windows 2000 in modalità nativa</th>
<th style="border:1px solid black;" >Modalità mista o Microsoft Windows NT® versione 4.0</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Gruppi universali e nidificati</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome principale utente (UPN, User Principal Name)</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controllo dell'accesso tramite autorizzazione Criteri di accesso remoto disponibile nell'account utente</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporto per il protocollo EAP-TLS</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
</tr>
</tbody>
</table>
  
**Nota:** anche l'implementazione di Servizi certificati inclusa in questa soluzione richiede Active Directory. Per ulteriori informazioni, vedere il modulo "[Progettazione di un'infrastruttura a chiave pubblica](http://www.microsoft.com/italy/technet/security/guidance/secmod170.mspx)".
  
Sebbene non indispensabile, dopo aver letto il presente modulo si potrebbe decidere di distribuire IAS nei controller di dominio. Questa soluzione si basa sul Servizio di Autenticazione Internet (IAS) incluso in Windows Server 2003 e pertanto richiede l'aggiornamento dei controller di dominio di destinazione a questa versione del sistema operativo. Tale aggiornamento presuppone un'attenta pianificazione dei requisiti sia per i computer client sia per gli altri controller di dominio dell'ambiente. Nel corso del presente modulo verranno fornite ulteriori informazioni sulla distribuzione di IAS nei controller di dominio.
  
#### Infrastruttura RADIUS esistente
  
Questa soluzione non presuppone un'infrastruttura RADIUS esistente. Sebbene i server esistenti basati su IAS e di terze parti *possano* coesistere senza problemi con questa soluzione, nella maggior parte dei casi è consigliabile utilizzare il Servizio di Autenticazione Internet (IAS) di Windows Server 2003 per le funzionalità correlate all'accesso alla rete WLAN.
  
I server RADIUS esistenti basati su Windows possono essere aggiornati a Windows Server 2003, così da poter essere utilizzati in questa soluzione come server RADIUS principali. In alternativa è possibile modificare i server RADIUS esistenti in modo che fungano da proxy e inoltrino il traffico RADIUS ai nuovi server RADIUS basati su Windows Server 2003.
  
Per istruzioni dettagliate sulla pianificazione della migrazione dell'infrastruttura RADIUS esistente al Servizio di Autenticazione Internet (IAS) di Windows Server 2003, contattare il partner Microsoft oppure il responsabile clienti Microsoft, che è in grado di indirizzare verso il partner appropriato o ai professionisti Microsoft Consulting Services.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Progettazione dell'infrastruttura RADIUS
  
Quando si utilizza IAS per supportare l'accesso WLAN basato sullo standard 802.1X, occorre prendere numerose decisioni relative alla progettazione. In questa sezione vengono illustrate alcune di tali decisioni, nonché le opzioni scelte per questa soluzione. È necessario valutare ciascuna di tali decisioni per verificarne l'applicabilità al proprio ambiente.
  
#### Determinazione del ruolo di IAS come server RADIUS
  
I server IAS possono essere distribuiti in modo che funzionino in uno dei tre seguenti ruoli concettuali RADIUS:
  
-   Server RADIUS
  
-   Proxy RADIUS
  
-   Server e proxy RADIUS
  
**Nota:** nella presente guida le espressioni server RADIUS e proxy RADIUS vengono utilizzate per descrivere un server IAS configurato in modo tale da svolgere questi ruoli.
  
Nella tabella seguente vengono descritte alcune delle capacità dei server configurati per svolgere questi ruoli e la relativa utilità in scenari reali.
  
**Tabella 2. Ruoli RADIUS di un server IAS**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Ruolo RADIUS del server IAS</th>
<th style="border:1px solid black;" >Capacità</th>
<th style="border:1px solid black;" >Scenario</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Server RADIUS</td>
<td style="border:1px solid black;">—- Controlla le credenziali direttamente in Active Directory.<br />
—- Utilizza Criteri di accesso remoto per determinare l'accesso alla rete.</td>
<td style="border:1px solid black;">Necessario per tutti gli scenari di gestione dell'accesso alla rete.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Proxy RADIUS</td>
<td style="border:1px solid black;">—- Indirizza la richiesta in base alle sue proprietà.<br />
-— È in grado di modificare le proprietà RADIUS delle richieste in transito.<br />
—- Fornisce il bilanciamento del carico delle richieste RADIUS per i gruppi di server RADIUS.</td>
<td style="border:1px solid black;">-— Utile in scenari con più insiemi di strutture in cui i dispositivi di accesso alla rete sono condivisi.<br />
—- Utile per la distribuzione di architetture di rete di vasta scala di tipo front-end/back-end con servizi di autenticazione, autorizzazione e accounting.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Server e proxy RADIUS</td>
<td style="border:1px solid black;">Combinazione delle due precedenti capacità.</td>
<td style="border:1px solid black;">Combinazione dei due scenari.</td>
</tr>
</tbody>
</table>
  
Non tutti i ruoli RADIUS sono necessari per gli scenari di gestione dell'accesso alla rete. Per molte organizzazioni, ad esempio, la gestione dell'accesso WLAN richiede solo il ruolo di server RADIUS. Se tuttavia l'organizzazione prevede di utilizzare l'infrastruttura di rete senza fili per utenti e dispositivi di più insiemi di strutture Active Directory, è necessario anche il ruolo di proxy RADIUS, onde indirizzare le richieste ai diversi server RADIUS di ciascun insieme di strutture.
  
Questa soluzione include server IAS configurati unicamente come server RADIUS e non come proxy RADIUS.
  
#### Informazioni sul failover dei server e sul bilanciamento del carico
  
Il servizio RADIUS è un componente essenziale di qualsiasi soluzione di gestione dell'accesso WLAN basata sullo standard 802.1X. La disponibilità di server IAS a servizio di punti di accesso senza fili determina la disponibilità della rete WLAN per gli utenti finali. Pertanto, quando si progetta un'infrastruttura RADIUS, è necessario garantire che due o più server IAS siano sempre al servizio dei punti di accesso senza fili. Nella maggior parte dei punti di accesso senza fili di ultima generazione è possibile configurare due server RADIUS per l'autenticazione e due server RADIUS per l'accounting. In tal modo viene assicurato che la perdita di contatto con un server RADIUS non incida sul servizio fornito ai client WLAN.
  
Quando si implementano più server per garantire la capacità di recupero dagli errori, molte organizzazioni scelgono uno schema in base al quale eseguire il bilanciamento del carico delle richieste provenienti dai punti di accesso senza fili configurati come client RADIUS su tutti i server RADIUS, così da assicurare che non vengano limitate le risorse di alcun server.
  
Prima di scegliere una strategia di bilanciamento del carico, è importante sapere che lo standard 802.1X prevede l'implementazione del protocollo EAP nell'ambito del servizio RADIUS (EAP-RADIUS) tra i punti di accesso senza fili e i server RADIUS. Sebbene il servizio RADIUS utilizzi il protocollo UDP (User Datagram Protocol) senza connessione, il protocollo EAP è orientato alla sessione e ne viene effettuato il tunneling all'interno del servizio RADIUS. Ciò comporta la necessità di garantire che, in caso di mancata autenticazione, vengano restituiti allo stesso server RADIUS più pacchetti EAP-RADIUS comprendenti una sola operazione di autenticazione.
  
Nella tabella seguente vengono illustrate le varie opzioni che consentono di assicurare che i client RADIUS possano utilizzare più server RADIUS per il recupero dagli errori ed eseguire il bilanciamento del carico delle richieste RADIUS.
  
**Tabella 3. Opzioni per il failover e il bilanciamento del carico EAP-RADIUS**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Metodo di failover e bilanciamento del carico</th>
<th style="border:1px solid black;" >Vantaggi</th>
<th style="border:1px solid black;" >Svantaggi</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Proxy IAS con gruppi di server RADIUS</td>
<td style="border:1px solid black;">- — Rilevamento del mancato funzionamento del servizio RADIUS con failover e failback.<br />
—- Distribuzione del carico di traffico in base alle proprietà del traffico stesso.<br />
-— Gestione dello stato della sessione EAP durante l'esecuzione del bilanciamento del carico.<br />
-— Distribuzione delle richieste sui server in base alle impostazioni di priorità e peso.</td>
<td style="border:1px solid black;">Server IAS aggiuntivi necessari.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Impostazione dei server RADIUS principale e secondario nei punti di accesso senza fili</td>
<td style="border:1px solid black;">- — Configurazione semplificata per ambienti di ridotte dimensioni.<br />
—- Il punto di accesso senza fili rileva l'assenza di traffico ed esegue il failover. Utilizza la funzionalità nativa del punto di accesso senza fili.</td>
<td style="border:1px solid black;">— Richiede una pianificazione e un monitoraggio accurati della selezione dei server RADIUS principale e secondario.<br />
— Molti punti di accesso senza fili non supportano la funzionalità di failback, causando lo sbilanciamento del carico sui server.</td>
</tr>
</tbody>
</table>
 

È consigliabile che le organizzazioni di notevoli dimensioni e i grandi provider di servizi di rete prendano in considerazione l'utilizzo dei proxy RADIUS per l'accettazione delle richieste provenienti dai client RADIUS e la distribuzione del carico tra i server RADIUS, che possono essere configurati in gruppi di server RADIUS. La distribuzione del carico di traffico tra i server RADIUS configurati come gruppi di server RADIUS può basarsi su vari parametri configurabili, ad esempio il tipo di traffico RADIUS e gli attributi RADIUS, oltre che sui valori relativi a priorità e peso. I server RADIUS di ogni gruppo di server RADIUS possono quindi eseguire l'autenticazione e l'autorizzazione di base per gli utenti e i dispositivi di un dominio o di un intero insieme di strutture. In tal modo si crea un'efficiente architettura front-end/back-end a servizio delle richieste RADIUS e si fornisce la maggior flessibilità possibile per le opzioni di bilanciamento del carico e di scalabilità.

![](images/Dd536258.SGFG17101(it-it,TechNet.10).jpg "Failover e bilanciamento del carico mediante i proxy RADIUS")

*Figura 1*
*Failover e bilanciamento del carico mediante i proxy RADIUS*

Tuttavia, le capacità native di failover ai server RADIUS incluse nei punti di accesso senza fili di ultima generazione forniscono il livello minimo di funzionalità necessaria per la maggior parte delle organizzazioni, così da garantire agli utenti finali un accesso WLAN continuo. Inoltre, il percorso di migrazione da una strategia di failover e bilanciamento del carico RADIUS basata su punti di accesso senza fili a una strategia di failover e bilanciamento del carico RADIUS basata su server proxy RADIUS è relativamente semplice. Uno svantaggio della strategia di failover e bilanciamento del carico RADIUS basata su punti di accesso senza fili è rappresentato dal sovraccarico di gestione dovuto all'abbinamento dei punti di accesso senza fili ai server RADIUS, al monitoraggio dei server RADIUS finalizzato all'equa distribuzione del carico e alle modifiche da apportare laddove necessario. Un altro svantaggio è costituito dal fatto che numerosi punti di accesso senza fili non supportano il failback. Ciò può condurre a situazioni in cui tutti i punti di accesso senza fili rimangono esclusi da un server RADIUS, con conseguente necessità di un intervento da parte dell'amministratore.

Per ottenere il bilanciamento del carico mediante una strategia di failover basata su punti di accesso senza fili qualora siano disponibili localmente più server RADIUS:

-   Configurare metà dei punti di accesso senza fili di ogni sede affinché utilizzino innanzitutto il server RADIUS principale e, quindi, il server RADIUS secondario in caso di mancato funzionamento del server RADIUS principale.

-   Configurare l'altra metà dei punti di accesso senza fili di ogni sede affinché utilizzino innanzitutto il server RADIUS secondario e, quindi, il server RADIUS principale in caso di mancato funzionamento del server RADIUS secondario.

![](images/Dd536258.SGFG17102(it-it,TechNet.10).jpg "Failover e bilanciamento del carico basati su punti di accesso senza fili")

*Figura 2*
*Failover e bilanciamento del carico basati su punti di accesso senza fili*

Per realizzare il bilanciamento del carico mediante una strategia di failover basata su punti di accesso senza fili nelle filiali in cui è disponibile un solo server RADIUS locale, oltre a un server RADIUS remoto, è necessario configurare tutti i punti di accesso senza fili della filiale in modo che utilizzino il server RADIUS locale come server principale. Quindi configurare il server RADIUS remoto come server secondario da utilizzare qualora quello principale non funzioni.

![](images/Dd536258.SGFG17103(it-it,TechNet.10).jpg "Failover e bilanciamento del carico basati su punti di accesso senza fili con server RADIUS remoti")

*Figura 3*
*Failover e bilanciamento del carico basati su punti di accesso senza fili con server RADIUS remoti*

Nei casi di filiali, assicurarsi che i punti di accesso senza fili siano in grado di eseguire il failback al server RADIUS principale quando quest'ultimo torna a funzionare, altrimenti occorrerà riconfigurare manualmente i punti di accesso senza fili per evitare che il servizio RADIUS attraversi inutilmente la rete WAN.

I server RADIUS presso le filiali sono facoltativi e si possono evitare utilizzando server RADIUS centralizzati in una rete WAN. Tuttavia, l'assenza di un server RADIUS locale comporta che l'accesso alla rete WLAN locale dipende dalla disponibilità della rete WAN.

Questa soluzione è stata ideata con l'intento di utilizzare il failover tra server basato su punti di accesso senza fili e la configurazione manuale per il bilanciamento del carico. Per ulteriori informazioni sulla pianificazione di un'infrastruttura RADIUS in grado di utilizzare i proxy RADIUS per il failover e il bilanciamento del carico tra server, consultare il manuale "Deploying IAS" incluso in *Microsoft Windows Server 2003 Deployment Kit* all'indirizzo [http://go.microsoft.com/fwlink/?LinkId=4716](http://go.microsoft.com/fwlink/?linkid=4716) (in iglese).

#### Definizione dei requisiti di registrazione

È possibile configurare i server IAS in modo che registrino due tipi di informazioni facoltative:

-   Eventi di autenticazione riusciti e rifiutati

-   Informazioni di autenticazione e accounting RADIUS

Gli eventi di autenticazione riusciti e rifiutati che vengono generati a partire da dispositivi e utenti che tentano di accedere alla rete WLAN vengono registrati per impostazione predefinita in IAS nel Registro eventi sistema di Windows Server 2003. Le informazioni incluse nel registro degli eventi di autenticazione si dimostrano assai utili per la risoluzione dei problemi di autenticazione, sebbene possano essere utilizzate anche per attività di controllo della protezione e segnalazione di avvisi.

All'inizio è opportuno che la registrazione degli eventi di autenticazione riusciti e rifiutati rimanga attiva, tuttavia è possibile disattivarla una volta che il sistema risulti stabile. Gli eventi di accesso riuscito alla rete WLAN tendono a saturare rapidamente il Registro eventi sistema e potrebbero risultare inutili ai fini della protezione qualora sia attiva la registrazione delle richieste di autenticazione RADIUS.

È consigliabile che le aziende utilizzino strumenti di monitoraggio, ad esempio Microsoft Operations Manager (MOM), per trattare mediante script personalizzati gli eventi IAS inclusi nel Registro eventi sistema. Uno script personalizzato MOM potrebbe ad esempio rilevare un aumento del numero di eventi IAS correlati a tentativi rifiutati di autenticazione e informarne l'amministratore affinché agisca conseguentemente.

IAS consente inoltre di salvare le informazioni sulle sessioni di autenticazione e accesso alla rete sotto forma di registri di richieste RADIUS. È possibile attivare e disattivare le informazioni seguenti incluse nei registri delle richieste RADIUS:

-   Richieste di accounting, ad esempio messaggi di inizio e fine accounting che segnalano l'avvio e la chiusura di una sessione di accesso alla rete.

-   Richieste di autenticazione, ad esempio messaggi di accettazione o rifiuto di accesso che indicano la riuscita o meno dei tentativi di autenticazione.

-   Stato periodico, ad esempio richieste di accounting temporaneo inviate da alcuni dispositivi di accesso alla rete. Tali informazioni in genere non sono necessarie.

I registri delle richieste RADIUS si dimostrano assai utili per organizzazioni quali i provider di servizi di rete che addebitano ai clienti il servizio in base all'utilizzo della rete. Tuttavia, i registri delle richieste RADIUS possono essere utilizzati anche per scopi di protezione. In particolare, i registri di autenticazione e accounting RADIUS consentono a coloro che si occupano di monitorare la protezione di determinare quanto segue:

-   Dettagli dei tentativi non autorizzati di autenticazione nella rete WLAN.

-   Durata delle connessioni accettate alla rete WLAN.

In IAS la registrazione in formato testo delle informazioni di autenticazione e accounting RADIUS è disattivata per impostazione predefinita. Prima di attivarla è necessario:

-   Parlare con il personale addetto alla protezione per venire a conoscenza dei requisiti occorrenti e tenere traccia delle informazioni sull'accesso alla rete WLAN, nonché di quali dettagli sono necessari.

-   Eseguire test di laboratorio della registrazione RADIUS in formato testo, per conoscere i requisiti hardware dei server (unità disco e CPU) in presenza di carico dovuto agli utenti della rete WLAN. L'accesso alla rete WLAN genera molte più informazioni rispetto ad altri tipi di accesso alla rete.

-   Valutare quali informazioni sulle richieste RADIUS (autenticazione, accounting e stato periodico) sono necessarie e quali non lo sono. L'accesso alla rete WLAN può generare quantità notevoli di informazioni che possono occupare rapidamente lo spazio su disco.

-   Stabilire una strategia per l'accesso, la memorizzazione e l'archiviazione delle informazioni dei registri delle richieste RADIUS. Tali informazioni possono essere salvate come file di testo sul disco rigido di ogni server IAS o in un database Microsoft SQL Server®.

Le aziende che hanno deciso di utilizzare i registri di accounting RADIUS devono prendere in considerazione la possibilità di avvalersi delle funzionalità di registrazione SQL Server di IAS. Le informazioni di accounting RADIUS possono essere registrate in SQL Server Desktop Engine (MSDE 2000) su ogni server IAS e, quindi, replicate in un cluster centrale Microsoft SQL Server 2000. L'adozione di questa strategia consente di realizzare un sistema di memorizzazione centralizzato e strutturato dei dati di accounting RADIUS, così da rendere più semplici l'esecuzione di query, la creazione di report e le attività di archiviazione. La registrazione SQL Server in un database MSDE locale elimina inoltre l'eventualità che i problemi della rete impediscano a IAS di registrare le informazioni e, quindi, di respingere le richieste di accesso alla rete.

Le organizzazioni prive di SQL Server 2000 o a corto di personale in grado di eseguire query, creare report e archiviare periodicamente i registri delle richieste RADIUS possono comunque prendere in considerazione la possibilità di eseguire la registrazione di queste informazioni per facilitare le indagini in caso di problemi di protezione. Come indicato nella tabella seguente, in questa soluzione sono state prese varie decisioni di progettazione che occorre esaminare per stabilirne l'adeguatezza all'ambiente.

**Tabella 4. Decisioni di progettazione in relazione alla registrazione IAS**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Decisione di progettazione in relazione alla registrazione IAS</th>
<th style="border:1px solid black;" >Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">La dimensione del Registro eventi sistema indicata nel modello dei criteri di gruppo IAS della documentazione <em>Windows Server 2003 Security Guide</em> è stata incrementata rispetto al valore predefinito, al fine di poter registrare i numerosi eventi IAS.</td>
<td style="border:1px solid black;">Se si sceglie di non attivare la registrazione delle richieste di autenticazione RADIUS, il Registro eventi sistema rappresenta la registrazione principale degli eventi di protezione connessi all'accesso alla rete WLAN. Considerare con attenzione le impostazioni, ad esempio l'impostazione predefinita per <strong>Sovrascrivi eventi se necessario</strong>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">È stata attivata la registrazione delle richieste di accounting e autenticazione RADIUS in file di testo.</td>
<td style="border:1px solid black;">Questa decisione comporta un aumento del carico sulla CPU e dei requisiti di spazio su disco dei server IAS.<br />
IAS interromperà l'accettazione delle richieste di autenticazione e accounting se non è possibile eseguire la registrazione. Pertanto, occorre prestare attenzione a possibili attacchi DoS (Negazione di servizio, Denial of Service) basati sul riempimento del disco dei file di registro.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Le specifiche hardware dei server IAS indicate nella presente guida prevedono un volume disco distinto per i file di registro su dischi fisici separati.</td>
<td style="border:1px solid black;">Questa decisione assicura che le prestazioni in scrittura dei file di registro delle richieste RADIUS incidano il meno possibile sulla gestione dell'accesso alla rete RADIUS. Questa decisione garantisce inoltre che gli eventi che provocano il riempimento di un volume disco non incidano sulla recuperabilità dei server.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Le voci relative all'autenticazione e all'accounting RADIUS sono state selezionate, mentre non lo sono quelle relative allo stato periodico.</td>
<td style="border:1px solid black;">Questa decisione è stata presa per assicurare che vengano registrate solo le informazioni essenziali necessarie per determinare lo stato delle autenticazioni e la durata delle sessioni. Lo stato periodico è stato omesso per ridurre i requisiti dei file di registro.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Per i file di registro dell'autenticazione e accounting RADIUS è stato scelto il formato di database compatibile con ODBC (Open Database Connectivity).</td>
<td style="border:1px solid black;">Questa scelta consente agli amministratori di importare con facilità i file di registro in database compatibili con ODBC, così da semplificarne l'analisi, e può considerarsi una procedura consigliata. Inoltre, per esplorare i file è possibile utilizzare ASPARSE.EXE, incluso negli strumenti di supporto di Windows Server 2003.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">L'intervallo per la creazione di nuovi file di registro è stato impostato su <strong>Mensile</strong>.</td>
<td style="border:1px solid black;">La scelta di un intervallo che generi meno file di registro ne facilita l'importazione nei database o l'esplorazione mediante IASPARSE.EXE se la registrazione SQL Server non viene utilizzata. Questa opzione dovrebbe essere considerata a fronte del rischio di riempire un disco rigido con un solo file di registro.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">La registrazione delle richieste RADIUS è stata impostata in modo tale da eliminare il file di registro meno recente quando il disco è pieno.</td>
<td style="border:1px solid black;">Il rischio di questa impostazione predefinita è rappresentato dal fatto che le informazioni di protezione possono andare perse qualora il disco di un file di registro divenga pieno. Questa impostazione è stata scelta per ridurre al minimo il rischio che i server IAS smettano di funzionare in ambienti gestititi in maniera approssimativa. Se per la disponibilità dei servizi è fondamentale disporre di un maggior livello di protezione, è opportuno prendere in considerazione la disattivazione di questa opzione.</td>
</tr>
</tbody>
</table>
  
#### Scelta di centralizzare o distribuire i server
  
La decisione di utilizzare server IAS centralizzati o distribuiti si basa in parte sulla distribuzione geografica dell'organizzazione e sulla strategia di distribuzione dell'infrastruttura IT dell'organizzazione. Occorre considerare quale dei tre seguenti tipi di strategia per l'infrastruttura IT è più vicino a quello dell'organizzazione:
  
-   Infrastruttura IT centralizzata
  
-   Infrastruttura IT distribuita
  
-   Infrastruttura IT mista centralizzata e distribuita
  
L'obiettivo principale delle moderne organizzazioni IT aziendali è di utilizzare un'infrastruttura IT sempre più di ridotta, basata su componenti centralizzati e con maggiore capacità di recupero dagli errori. Il raggiungimento di questo obiettivo richiede un notevole investimento in componenti infrastrutturali WAN ad alta velocità e con maggiore capacità di recupero dagli errori, così da garantire che gli utenti nelle filiali godano dello stesso livello di servizio IT degli utenti che si trovano nella sede centrale. Un vantaggio di questa strategia è rappresentato dal fatto che il costo dell'infrastruttura a server distribuiti può essere dirottato verso l'infrastruttura di rete e la larghezza di banda. Inoltre, l'infrastruttura dei server si trova a poca distanza dal personale tecnico specializzato e dal personale addetto all'esercizio del data center. Pertanto è possibile ottenere un maggiore livello di disponibilità.
  
In organizzazioni con reti WAN ad alta velocità e con grande capacità di recupero dagli errori è da preferire la centralizzazione dei server IAS, la quale deve pertanto essere considerata come il punto di partenza per la progettazione dei server RADIUS aziendali. Il protocollo RADIUS non sfrutta in modo eccessivo la larghezza di banda e funziona bene sui collegamenti WAN. Tuttavia, è essenziale disporre di una connessione ad alte prestazioni tra i server IAS e i controller di dominio che contengono gli utenti e i gruppi utilizzati per determinare l'accesso alla rete. Molti potenziali problemi con lo standard di rete 802.1X possono essere evitati garantendo che le comunicazioni tra i server IAS e Active Directory avvengano ad alta velocità.
  
La realtà per molte organizzazioni non aziendali è che il costo della larghezza di banda, di sofisticati dispositivi di rete e di connessioni WAN ridondanti impedisce l'adozione di un modello di infrastruttura IT centralizzata. Tali organizzazioni scelgono un modello di infrastruttura IT decentralizzata con server distribuiti nelle filiali, così da garantire la continuità del servizio IT in caso di guasto della rete WAN.
  
Un terzo tipo di strategia per l'infrastruttura IT si ha quando le organizzazioni scelgono di centralizzare l'infrastruttura IT dove possibile e di distribuirla dove necessario. Questa strategia consente di raggruppare la maggior parte dell'infrastruttura IT in sedi hub a servizio degli utenti di tali sedi e di quelli delle filiali collegate all'hub. Questo modello consente al contempo di distribuire l'infrastruttura dei server nelle filiali con un maggior numero di utenti finali. Nel diagramma seguente viene illustrato un esempio di una simile organizzazione.
  
![](images/Dd536258.SGFG17104(it-it,TechNet.10).jpg "Organizzazione con infrastruttura IT sia centralizzata sia distribuita")
  
*Figura 4*  
*Organizzazione con infrastruttura IT sia centralizzata sia distribuita*
  
Questa soluzione, progettata in vista di modelli di distribuzione dell'infrastruttura server centralizzata, decentralizzata e mista, fornisce quanto segue:
  
-   Configurazione di sedi hub di grandi dimensioni con due server RADIUS in grado di gestire le richieste locali e quelli di uffici privi di infrastruttura server.
  
-   Configurazione di filiali di grandi dimensioni con un server RADIUS facoltativo di filiale.
  
**Nota:** in filiali di piccole dimensioni prive di infrastruttura server, l'accesso alle reti WLAN dipende dalla disponibilità della rete WAN.
  
#### Determinazione del numero e della posizione dei server
  
Ogni insieme indipendente di strutture Active Directory dovrebbe includere almeno due server IAS che fungano da server RADIUS per gli utenti e i dispositivi dell'insieme di strutture. Ciò assicura che le richieste di accesso alla rete continuino a essere gestite qualora uno dei server RADIUS diventi indisponibile.
  
Le sedi centrali delle aziende, al cui interno lavorano molti utenti, rappresentano i candidati ideali per un'infrastruttura basata su due o più server RADIUS. Se tra più sedi hub con server RADIUS è disponibile larghezza di banda ad alta velocità, è possibile configurare i punti di accesso senza fili in modo che eseguano il failover ai server RADIUS di una rete WAN. Tuttavia, prima di utilizzare i server RADIUS di una rete WAN, è opportuno considerare la vicinanza di tali server ai controller di dominio contenenti le informazioni su utenti e gruppi con cui viene controllato l'accesso alla rete. Inoltre, è importante testare i valori di timeout dei punti di accesso senza fili e dei computer client, apportando le eventuali modifiche necessarie.
  
Le filiali abbastanza grandi da garantire controller di dominio e che sono prive di connessioni WAN alle sedi hub con capacità di recupero dagli errori sono candidati probabili a ospitare un server RADIUS locale. Se l'organizzazione non ha implementato funzionalità WAN di recupero dagli errori, occorre valutare il costo iniziale e di esercizio di un server IAS di filiale rispetto al costo in cui si incorre nel caso in cui la rete WAN ha problemi e gli utenti della rete WLAN non possono accedere a quest'ultima.
  
#### Installazione di IAS insieme con altri servizi
  
A motivo del grande volume di interazioni con i controller di dominio Active Directory, i server IAS presentano un incremento delle prestazioni se installati sullo stesso hardware dei controller di dominio, evitando l'attraversamento della rete. Occorre tuttavia considerare attentamente le implicazioni connesse all'installazione di IAS nei controller di dominio. Nella tabella seguente vengono riportati i dettagli relativi a tali considerazioni.
  
**Tabella 5. Considerazioni sull'installazione di IAS e dei controller di dominio sullo stesso hardware**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Posizione di IAS</th>
<th style="border:1px solid black;" >Vantaggi</th>
<th style="border:1px solid black;" >Svantaggi</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Installato nei controller di dominio</td>
<td style="border:1px solid black;">- — Incremento delle prestazioni per l'autenticazione e l'autorizzazione di utenti e computer.<br />
—- Richiede meno componenti hardware per server.</td>
<td style="border:1px solid black;">Nessuna separazione tra amministratori di IAS e amministratori di dominio.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Separatamente dai controller di dominio</td>
<td style="border:1px solid black;">- — Separazione tra amministratori di IAS e amministratori di dominio.<br />
—- Il carico e il funzionamento di IAS non incidono sul servizio Active Directory.</td>
<td style="border:1px solid black;">Richiede hardware aggiuntivo per server.</td>
</tr>
</tbody>
</table>
  
I controller di dominio Active Directory sono elementi essenziali dell'infrastruttura IT e devono essere gestiti con estrema cura. Molte organizzazioni aziendali adottano una politica che prevede di ridurre al minimo i programmi software o i servizi installati nei controller di dominio, per garantire la loro massima affidabilità e la continuità del servizio.
  
Inoltre, gli amministratori delle infrastrutture RADIUS di molte aziende sono distinti dagli amministratori delle infrastrutture Active Directory. IAS è un componente facoltativo di Windows, pertanto non esiste alcuna separazione intrinseca tra l'amministrazione di IAS e gli amministratori locali di Windows. Ciò comporta che se IAS viene installato nei controller di dominio, gli amministratori di dominio devono aggiungere gli amministratori di IAS al gruppo di protezione Administrators condiviso da tutti i controller del dominio.
  
Occorre prestare attenzione al fatto che questa soluzione richiede la versione di IAS inclusa in Windows Server 2003. Pertanto, se si intende installare IAS sullo stesso hardware dei controller di dominio Windows 2000 Server, è necessario eseguirne l'aggiornamento a Windows Server 2003 prima di installare e configurare IAS. Inoltre, prima di eseguire l'aggiornamento dei controller di dominio Windows 2000 Server a Windows Server 2003, è opportuno considerare i requisiti riportati di seguito.
  
**Tabella 6. Requisiti per i controller di dominio Windows Server 2003**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Fattore da valutare</th>
<th style="border:1px solid black;" >Requisito</th>
<th style="border:1px solid black;" >Commento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">I controller di dominio Windows Server 2003 richiedono per impostazione predefinita la firma dei pacchetti SMB (Server Message Block) e ciò causa problemi con alcune versioni precedenti di client Windows.</td>
<td style="border:1px solid black;">Aggiornare tutti i computer client almeno al sistema operativo Microsoft Windows 95 con il client Active Directory oppure al sistema operativo Microsoft Windows NT 4.0 con Service Pack 4 (SP4) o versione successiva.</td>
<td style="border:1px solid black;">Per ulteriori informazioni, vedere Windows Server 2003 Support Center.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">I controller di dominio Windows Server 2003 richiedono per impostazione predefinita la firma e la crittografia SChannel, e ciò causa problemi con alcune versioni precedenti di client Windows.</td>
<td style="border:1px solid black;">Aggiornare tutti i computer client almeno a Windows 95 con il client Active Directory oppure a Windows NT 4.0 con SP4 o versione successiva.</td>
<td style="border:1px solid black;">Per ulteriori informazioni, vedere Windows Server 2003 Support Center all'indirizzo <a href="http://support.microsoft.com/default.aspx?scid=fh;it;winsvr2003">http://support.microsoft.com/default.aspx?scid=fh;IT;winsvr2003</a>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">I controller di dominio Windows Server 2003 richiedono per impostazione predefinita la firma e la crittografia SChannel, e ciò incide sulle relazioni di trust con i domini che includono server Windows NT 4.0 pre-SP4.</td>
<td style="border:1px solid black;">Aggiornare tutti i server del dominio a Windows NT Server 4.0 con SP4 o versione successiva.</td>
<td style="border:1px solid black;">Per ulteriori informazioni, vedere Windows Server 2003 Support Center all'indirizzo <a href="http://support.microsoft.com/default.aspx?scid=fh;it;winsvr2003">http://support.microsoft.com/default.aspx?scid=fh;IT;winsvr2003</a>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">I controller di dominio Windows Server 2003 richiedono, prima dell'installazione, la preparazione dell'insieme di strutture Active Directory e del dominio.</td>
<td style="border:1px solid black;">Preparare il nuovo insieme di strutture utilizzando l'utilità ADPrep prima di eseguire l'aggiornamento dei controller di dominio a Windows Server 2003.</td>
<td style="border:1px solid black;">Ciò non incide sul set di attributi parziali e pertanto non causa una ricostituzione del server di catalogo globale.</td>
</tr>
</tbody>
</table>
  
Questa soluzione è stata ideata per consentire l'installazione di IAS sullo stesso hardware dei controller di dominio, se lo si desidera. La soluzione è stata collaudata con IAS separato dai controller di dominio Windows Server 2003 in sedi hub e installato insieme con Windows Server 2003 nei controller di dominio di filiali.
  
#### Stima del carico dei server RADIUS
  
IAS funziona bene anche su server con prestazioni modeste e può essere scalato verticalmente mediante hardware aggiuntivo o orizzontalmente ricorrendo ai gruppi di server RADIUS. Tuttavia è preferibile stimare in anticipo il carico che i client WLAN causeranno sull'hardware dei server IAS, così da evitare alle risorse dei server limitazioni che potrebbero incidere sulla disponibilità del servizio.
  
Una progettazione ottimale dovrebbe includere un numero minimo di server necessari per garantire la capacità di recupero dagli errori, pur lasciando spazio per una futura crescita. Ciò è particolarmente importante quando si sceglie di dimensionare l'hardware dei server per l'utilizzo in un modello di bilanciamento del carico basato su punti di accesso senza fili. Nel passare dal bilanciamento del carico basato su punti di accesso senza fili al bilanciamento del carico basato su proxy RADIUS, i requisiti dell'hardware possono passare da due a cinque server qualora i server RADIUS esistenti abbiano già raggiunto la capacità massima.
  
Le considerazioni sul carico dei server IAS includono quanto segue:
  
-   Il numero di utenti e dispositivi che necessitano di autenticazione e accounting.
  
-   Le opzioni di autenticazione, ad esempio tipo EAP e frequenza di riautenticazione.
  
-   Le opzioni RADIUS, ad esempio la registrazione dell'attività e l'analisi software IAS.
  
Il numero di utenti e dispositivi che necessitano dell'accesso alla rete WLAN è indispensabile per la stima del carico dei server IAS. Alcune organizzazioni limitano l'utilizzo della rete WLAN a un ristretto gruppo di utenti quali i dirigenti, mentre altre organizzazioni scelgono di offrire l'accesso WLAN a tutti gli utenti. A prescindere dalla strategia scelta dall'organizzazione, è necessario prevedere lo scenario peggiore, nel quale tutti gli utenti e dispositivi in grado di accedere alla rete WLAN richiedono l'autenticazione e l'autorizzazione nell'arco di un breve periodo di tempo. Così facendo si garantisce che i server IAS saranno dimensionati in modo da gestire periodi di stress elevato, ad esempio gli orari di punta del lavoro e il periodo immediatamente successivo a un'interruzione cospicua della rete.
  
Inoltre, le opzioni di autenticazione hanno un notevole effetto sul carico dei server IAS. I protocolli basati su certificati, ad esempio EAP-TLS, eseguono in occasione dell'accesso iniziale un'operazione con chiave pubblica che sfrutta intensamente le risorse della CPU, ma poi, per tutti i successivi accessi, utilizzano una strategia basata su credenziali memorizzate nella cache detta Riconnessione rapida, fino alla scadenza della cache (otto ore, per impostazione predefinita).
  
La riautenticazione completa può avere luogo quando i client senza fili si associano a punti di accesso che sfruttano un server IAS diverso da quello precedentemente utilizzato. Questa riautenticazione mobile avviene solo una volta tra client e server IAS ed è invisibile all'utente finale qualora sia in uso il protocollo EAP-TLS.
  
Inoltre, è possibile adottare il metodo di aggiornamento delle chiavi di crittografia delle sessioni WEP 802.11 che consiste nell'imporre ai client senza fili di riautenticarsi con i server RADIUS. Alcuni modelli di punto di accesso senza fili includono funzionalità con cui eseguire l'aggiornamento temporizzato delle chiavi di sessione WEP senza dover imporre ai client l'esecuzione frequente della riautenticazione con il server RADIUS a intervalli prestabiliti. Queste funzionalità sono specifiche dei singoli produttori e devono essere valutate a fronte dei requisiti delle risorse dei server, della strategia di amministrazione centralizzata e degli standard di settore. Oltre a ciò, l'imminente standard WPA (WiFi Protected Access) include funzionalità di crittografia avanzata che possono ridurre la necessità di una riautenticazione frequente.
  
Pertanto, nel creare un modello per un determinato numero di autenticazioni che ogni server IAS dovrà gestire, è opportuno considerare la frequenza dei tipi di autenticazione indicati nella tabella riportata di seguito.
  
**Tabella 7. Tipi di autenticazione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Tipo di autenticazione</th>
<th style="border:1px solid black;" >Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione iniziale del computer</td>
<td style="border:1px solid black;">Il client esegue un'autenticazione completa con IAS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Autenticazione iniziale dell'utente</td>
<td style="border:1px solid black;">Il client esegue un'autenticazione completa con IAS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Riautenticazione dell'utente quando passa da un punto di accesso senza fili a un altro</td>
<td style="border:1px solid black;">Il client esegue un'autenticazione completa con ogni server IAS, quindi utilizza la funzione di Riconnessione rapida per le ulteriori autenticazioni.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Riautenticazione del dispositivo quando passa da un punto di accesso senza fili a un altro</td>
<td style="border:1px solid black;">Il client esegue un'autenticazione completa con ogni server IAS, quindi utilizza la funzione di Riconnessione rapida per le ulteriori autenticazioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Riautenticazione temporizzata del computer</td>
<td style="border:1px solid black;">Il client utilizza un'autenticazione memorizzata nella cache con IAS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Riautenticazione temporizzata dell'utente</td>
<td style="border:1px solid black;">Il client utilizza un'autenticazione memorizzata nella cache con IAS.</td>
</tr>
</tbody>
</table>
  
La stima del numero di autenticazioni che IAS è in grado di gestire deve essere espressa in autenticazioni al secondo. È stato dimostrato che IAS è in grado di raggiungere le seguenti prestazioni con un server Intel Pentium 4 a 2 GHz su cui viene eseguito Windows Server 2003 e Active Directory installato su un altro server Intel Pentium 4 a 2 GHz. Le informazioni contenute nella tabella che segue vengono fornite senza alcuna garanzia e devono essere intese come mere linee guida ai fini della pianificazione della capacità e non ai fini di un confronto fra prestazioni.
  
**Tabella 8. Autenticazioni al secondo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Tipo di autenticazione</th>
<th style="border:1px solid black;" >Autenticazioni al secondo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nuove autenticazioni EAP-TLS</td>
<td style="border:1px solid black;">36</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nuove autenticazioni EAP-TLS con scheda di supporto per la ripartizione del carico</td>
<td style="border:1px solid black;">50</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autenticazioni con Riconnessione rapida</td>
<td style="border:1px solid black;">166</td>
</tr>
</tbody>
</table>
  
IAS può essere configurato in modo che generi registri di testo basati su disco contenenti quantità variabili di informazioni sulle richieste RADIUS. Occorre considerare attentamente il sovraccarico che le attività di registrazione RADIUS comportano per i server RADIUS, in quanto i sottosistemi disco a bassa velocità possono ritardare le risposte RADIUS IAS ai punti di accesso senza fili, con conseguenti timeout dei protocolli e inutili operazioni di failover dei punti di accesso senza fili ai server RADIUS secondari.
  
Inoltre, se si attivano le funzionalità di analisi software di Windows Server 2003, verrà imposto un ulteriore carico sui server IAS, sebbene ciò possa dimostrarsi necessario di tanto in tanto per risolvere i problemi di accesso alla rete. I server IAS, pertanto, dovrebbero avere la capacità di funzionare e gestire il carico di produzione anche quando le funzionalità di analisi risultano attive per brevi periodi di tempo.
  
#### Stima dei requisiti hardware dei server
  
È necessario scegliere l'hardware dei server su cui eseguire IAS basandosi sull'[elenco di compatibilità hardware per Windows Server 2003](http://www.windowsservercatalog.com/). Scegliendo i componenti hardware dei server da questo elenco è possibile evitare i problemi di affidabilità e compatibilità che potrebbero sorgere con hardware non collaudato e driver di periferica malfunzionanti.
  
I server IAS devono rispettare i requisiti hardware consigliati per Windows Server 2003. Occorre poi prendere in considerazione altri servizi in esecuzione nel sistema, ad esempio Active Directory. Sarebbe opportuno dedicare a IAS componenti hardware in grado di sostenere il doppio del previsto carico di autenticazione per server, così da garantire la disponibilità di sufficienti risorse server con cui affrontare le situazioni di failover tra server e le condizioni insolite della rete.
  
Nel diagramma seguente viene illustrato un esempio di progettazione di server RADIUS basata su IAS in cui vengono indicati la posizione e il numero di server in base alla distribuzione degli utenti e al carico previsto. Sebbene tale progettazione si riferisca a un'organizzazione di grandi dimensioni, questa soluzione è stata collaudata con un sottoinsieme di questa infrastruttura basato sulla sede londinese qui mostrata.
  
**Nota:** la Woodgrove Bank è un'azienda fittizia rappresentativa di organizzazioni di medie e grandi dimensioni. L'architettura e le caratteristiche della sua rete sono state utilizzate come base per diverse decisioni di progettazione nell'implementazione della build di riferimento di questa soluzione.
  
![](images/Dd536258.SGFG17105(it-it,TechNet.10).jpg "Distribuzione di utenti, punti di accesso senza fili e server IAS della Woodgrove Bank")
  
*Figura 5*  
*Distribuzione di utenti, punti di accesso senza fili e server IAS della Woodgrove Bank*
  
Questa soluzione è stata progettata con due server RADIUS che si trovano nella sede centrale al servizio di 6.742 utenti. Solo il 50 percento degli utenti può accedere alla rete senza fili, pertanto 3.371 utenti e i rispettivi 3.371 dispositivi eseguono l'autenticazione con i due server RADIUS mediante il protocollo EAP-TLS negli orari di massimo carico. Ogni server è dimensionato in modo da gestire 3.371 autenticazioni distribuite in un periodo di picco di accessi di 30 minuti, che corrisponde all'incirca a due nuove autenticazioni EAP-TLS al secondo con capacità di quattro nuove autenticazioni al secondo nei periodi di failover tra server.
  
Sul server è inoltre attiva la registrazione delle richieste di autenticazione e accounting RADIUS in file di testo. Il server è dedicato all'esecuzione della funzione di server RADIUS, con Active Directory su un diverso computer. Inoltre, i server sono intenzionalmente sovradimensionati per poter far fronte ai requisiti futuri, ad esempio il controllo dell'accesso alla rete di tipo VPN, via cavo e con connessione remota.
  
Nella tabella seguente viene indicato l'hardware dei server IAS utilizzato per il collaudo di questa soluzione.
  
**Tabella 9. Hardware dei server collaudato**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Risorsa</th>
<th style="border:1px solid black;" >Configurazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CPU</td>
<td style="border:1px solid black;">Pentium III a 850 MHz con doppia CPU</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">RAM</td>
<td style="border:1px solid black;">512 MB</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Scheda di rete</td>
<td style="border:1px solid black;">Due schede di rete abbinate per funzionalità di recupero dagli errori</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Disco rigido</td>
<td style="border:1px solid black;">- — Due dischi rigidi da 9 GB in configurazione RAID 1 (volume C$) per il sistema operativo<br />
- — Due dischi rigidi da 18 GB in configurazione RAID 1 (volume D$) per i file di registro e i dati di configurazione</td>
</tr>
</tbody>
</table>
 

I requisiti hardware per i propri server IAS possono essere diversi e devono essere valutati sulla base delle variabili specifiche dell'organizzazione.

#### Determinazione dei requisiti software dei server

Occorre stabilire se per i server IAS del proprio ambiente è necessario Windows Server 2003 Standard Edition o Enterprise Edition. Windows Server 2003 Standard Edition supporta solo 50 client RADIUS e due gruppi di routing server.

Questa soluzione è stata collaudata con Windows Server 2003 Enterprise Edition per server RADIUS di sedi hub e con Windows Server 2003 Standard Edition per ulteriori server RADIUS di filiali. La soluzione tuttavia funziona altrettanto bene con una versione che presenta le limitazioni indicate in precedenza. È opportuno scegliere la versione di Windows Server 2003 che risponde ai propri requisiti RADIUS specifici.

Sono necessari altri componenti software, a seconda degli standard dell'organizzazione. Ad esempio:

-   Agenti di backup.

-   Agenti di gestione, quali MOM o i componenti client Microsoft Systems Management Server (SMS).

-   Software antivirus.

-   Agenti per il rilevamento di intrusioni.

[](#mainsection)[Inizio pagina](#mainsection)

### Creazione di un piano di gestione

I server RADIUS basati su IAS richiedono relativamente poca manutenzione ordinaria per garantire la disponibilità continua del servizio e la protezione della rete. Tuttavia, è necessario determinare in anticipo la strategia di gestione IAS, così da addestrare il personale necessario per gestire l'infrastruttura RADIUS in base ai requisiti aziendali.

#### Gestione delle modifiche e della configurazione

La conoscenza dello stato dei server IAS e la sua conservazione sono essenziali per assicurare la disponibilità del servizio e la protezione della rete. IAS facilita nativamente le modifiche transazionali di vari elementi di configurazione dei server mediante il comando **netsh** e pertanto consente un semplice rollback qualora una modifica causi problemi imprevisti.

Il comando **netsh** consente di esportare e importare per intero o in parte la configurazione IAS in file di testo di configurazione per il trasferimento delle impostazioni tra server IAS che svolgono lo stesso ruolo. Questa funzionalità può velocizzare la distribuzione delle modifiche della configurazione in ambienti di grandi dimensioni.

Le attività che occorre svolgere per realizzare una gestione appropriata delle modifiche e della configurazione vengono indicate nel modulo "[Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili](http://technet.microsoft.com/it-it/library/dd536253)" nella *Guida operativa*.

#### Pianificazione in vista di un ripristino di emergenza

Per garantire un ripristino veloce del servizio RADIUS in situazioni di emergenza è necessaria un'appropriata pianificazione da realizzare prima del verificarsi dell'evento. L'installazione e la configurazione di IAS possono essere semplificate mediante gli script di installazione forniti con la presente guida, mentre le attività da svolgere per ripristinare rapidamente lo stato della configurazione di IAS possono essere desunte dagli script **netsh**. Ulteriori informazioni sulle attività di ripristino di emergenza si trovano nel modulo "[Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili](http://technet.microsoft.com/it-it/library/dd536253)" della *Guida operativa*.

#### Pianificazione delle autorizzazioni amministrative

IAS è un componente facoltativo del sistema operativo Windows Server 2003 e pertanto non richiede un modello di protezione amministrativa diverso da quello del server locale. La separazione dell'amministrazione di IAS da quella svolta dagli amministratori del server locale non è possibile se non mediante attività di sviluppo personalizzato, ad esempio la creazione di una pagina Web protetta che consenta di eseguire modifiche della configurazione di IAS mediante un account fisso con autorizzazioni amministrative per il server locale.

È tuttavia importante pianificare i tipi di amministrazione necessari e i requisiti di accesso alle varie risorse IAS per ottenere un modello con privilegi minimi. Nella tabella seguente vengono forniti alcuni esempi di ruoli e attività correlati ai server IAS.

**Tabella 10. Descrizioni e attività dei ruoli IAS**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Ruolo del personale</th>
<th style="border:1px solid black;" >Descrizione del ruolo</th>
<th style="border:1px solid black;" >Attività</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">IAS Administrators</td>
<td style="border:1px solid black;">Ruolo necessario per eseguire le attività amministrative quotidiane di IAS, ad esempio il controllo del servizio IAS e della configurazione di IAS</td>
<td style="border:1px solid black;">Avviare/arrestare/eseguire query/configurare il servizio IAS e apportare modifiche al database di configurazione di IAS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IAS Security Auditors</td>
<td style="border:1px solid black;">Ruolo necessario per consentire l'accesso alle informazioni sulla protezione da parte dei membri del gruppo IAS Security Auditors con autorizzazioni non amministrative</td>
<td style="border:1px solid black;">Esaminare i file di registro di accounting e autenticazione RADIUS per individuare gli eventi di protezione.<br />
Se i registri delle richieste di autenticazione RADIUS sono disattivati, i membri del gruppo IAS Security Auditors potrebbero avere bisogno di esaminare e salvare le voci del Registro eventi sistema relative agli eventi di protezione rilevanti per IAS. Ciò può richiedere autorizzazioni aggiuntive.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IAS Backup Operators</td>
<td style="border:1px solid black;">Operatori responsabili dei backup regolari dei server IAS, nei quali sono inclusi lo stato della configurazione e i dati cronologici IAS</td>
<td style="border:1px solid black;">Gestire i backup quotidiani/settimanali/mensili dei server IAS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">WLAN Help Desk Staff</td>
<td style="border:1px solid black;">Personale responsabile dell'assistenza agli utenti nella soluzione di problemi correlati all'accesso alla rete WLAN</td>
<td style="border:1px solid black;">Esaminare gli eventi IAS inclusi nel Registro eventi sistema correlati all'autenticazione di utenti e dispositivi.</td>
</tr>
</tbody>
</table>
  
Nella tabella seguente sono illustrate le autorizzazioni per le risorse che occorre avere per eseguire le varie attività sui server IAS.
  
**Tabella 11. Autorizzazioni necessarie per le attività sui server IAS**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Attività</th>
<th style="border:1px solid black;" >Appartenenza al gruppo</th>
<th style="border:1px solid black;" >Autorizzazione o diritti necessari</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Arrestare/avviare/<br />
eseguire query/<br />
configurare il servizio<br />
IAS</td>
<td style="border:1px solid black;">Gruppo globale IAS Admins di Active Directory, incluso nel gruppo Administrators locale/incorporato sui server IAS</td>
<td style="border:1px solid black;">Le modifiche delle autorizzazioni per i servizi di Windows Server 2003 possono essere apportate mediante il comando <strong>SC</strong>. Consultare il personale dell'assistenza Microsoft prima di modificare le autorizzazioni predefinite per i componenti del sistema operativo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modificare la configurazione di IAS</td>
<td style="border:1px solid black;">Gruppo globale IAS Admins di Active Directory, incluso nel gruppo Administrators locale/incorporato sui server IAS</td>
<td style="border:1px solid black;">Sono necessarie le autorizzazioni per i file di database IAS che si trovano nella directory C:\WINDOWS\system32\ias, nonché per le varie chiavi del Registro di sistema incluse in <strong>HKLM\System\CurrentControlSet\Services</strong>. Per impostazione predefinita, tali autorizzazioni vengono accordate ai membri del gruppo di protezione Administrators locale/incorporato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accedere ai registri delle richieste RADIUS<br />
che si trovano nei<br />
server IAS</td>
<td style="border:1px solid black;">Gruppo globale IAS Security Auditors di Active Directory</td>
<td style="border:1px solid black;">I membri del gruppo IAS Security Auditors devono essere in grado di leggere ed eliminare i file di registro delle richieste RADIUS che si trovano nella directory D:\IASLogs. Le linee guida per l'implementazione incluse nella presente soluzione accordano l'autorizzazione Modifica del file system NTFS al gruppo di protezione IAS Security Auditors per questa directory e creano una condivisione chiamata IASLogs con l'autorizzazione di modifica accordata al gruppo di protezione IAS Security Auditors.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Leggere e salvare<br />
gli eventi di protezione IAS<br />
inclusi nel<br />
Registro eventi<br />
sistema</td>
<td style="border:1px solid black;">Administrators locale/incorporato<br />
oppure Backup Operators</td>
<td style="border:1px solid black;">Questa soluzione include linee guida con cui attivare la registrazione dell'autenticazione RADIUS in file di testo su disco. Pertanto i membri del gruppo di protezione IAS Security Auditors in genere non hanno bisogno di accedere al Registro eventi sistema per esaminare gli eventi di protezione correlati all'autenticazione RADIUS.<br />
Se però si decide di disattivare la registrazione dell'autenticazione RADIUS, i membri del gruppo IAS Security Auditors devono poter leggere e salvare gli eventi IAS inclusi nel Registro eventi sistema. Per poter archiviare un Registro eventi sistema è necessario appartenere al gruppo Administrators o Backup Operators.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Eseguire backup quotidiani/settimanali<br />
/mensili<br />
dei server IAS</td>
<td style="border:1px solid black;">Backup Operators</td>
<td style="border:1px solid black;">Il backup di IAS include lo stato della configurazione e i dati cronologici di IAS, ad esempio i registri delle richieste RADIUS. L'appartenenza al gruppo di protezione Backup Operators consente l'accesso ai file di database IAS situati nella directory C:\WINDOWS\system32\ias, alle varie chiavi del Registro di sistema in <strong>HKLM\System\CurrentControlSet\Services</strong>, ai file di registro delle richieste RADIUS in D:\IASLogs e ai file di testo di configurazione di IAS <strong>NETSH</strong> che si trovano in D:\IASConfig.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Esaminare gli eventi di autenticazione IAS inclusi nel Registro eventi sistema per risolvere i problemi</td>
<td style="border:1px solid black;">Appartenenza a un gruppo con autorizzazioni alla lettura del Registro eventi sistema</td>
<td style="border:1px solid black;">Al personale esperto di risoluzione dei problemi deve essere accordata<br />
l'autorizzazione alla lettura del Registro eventi sistema di Windows Server<br />
2003, per visualizzare e interpretare<br />
gli eventi di rifiuto dell'autenticazione IAS.</td>
</tr>
</tbody>
</table>
 

#### Monitoraggio e controllo della protezione

IAS è un componente dell'infrastruttura di protezione del quale occorre eseguire il monitoraggio in maniera preventiva. Alcune ricerche nell'ambito della protezione hanno mostrato che gli attacchi riusciti sono in genere preceduti da svariati attacchi non riusciti. Il monitoraggio preventivo della protezione dei server IAS e dei relativi registri finalizzato all'individuazione di elementi sospetti si dimostra necessario per sapere quando la rete è sotto attacco.

Nella tabella seguente vengono elencati i possibili pericoli per l'infrastruttura dei server che possono essere monitorati in maniera preventiva.

**Tabella 12. Pericoli per l'infrastruttura dei server IAS**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Pericolo</th>
<th style="border:1px solid black;" >Sintomo</th>
<th style="border:1px solid black;" >Strumento di monitoraggio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Tentativo di autenticazione mediante credenziali rubate (ad esempio, quelle trovate su un computer portatile perso o rubato)</td>
<td style="border:1px solid black;">Eventi di autenticazione riuscita/rifiutata (origine: IAS, ID 1 e 2) nel Registro eventi sistema o nei registri delle richieste di autenticazione RADIUS indicanti l'utilizzo di certificati revocati.</td>
<td style="border:1px solid black;">— MOM con uno script personalizzato mirato all'analisi delle voci del registro eventi alla ricerca di indicazioni sull'utilizzo di certificati revocati.<br />
— Script di analisi di file o SQL Server che cercano l'utilizzo di certificati revocati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Tentativo di attacco di tipo 'man-in-the-middle' eseguito mediante un punto di accesso senza fili manomesso</td>
<td style="border:1px solid black;">Monitor di sistema contrasta qualsiasi server IAS che presenta un numero eccessivo di istanze di autenticatori errati (attributo Bad Message Authenticator) o richieste non valide (ricevute da client o server RADIUS ignoti).</td>
<td style="border:1px solid black;">MOM con uno script personalizzato per rilevare le contromosse di Monitor di sistema e creare un avviso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Tentativi di attacco di tipo DoS o overflow del buffer contro il servizio dei server IAS</td>
<td style="border:1px solid black;">Monitor di sistema contrasta qualsiasi server IAS che presenta un numero eccessivo di istanze di pacchetti errati (pacchetti contenenti dati errati), tipo ignoto (ricezione di pacchetti non RADIUS) o pacchetti ignorati (diversi da quelli MAC errati/errati/ignoti).</td>
<td style="border:1px solid black;">MOM con uno script personalizzato per rilevare le contromosse di Monitor di sistema e creare un avviso.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Tentativo di autenticazione non autorizzato</td>
<td style="border:1px solid black;">Eventi ripetuti di autenticazione non riuscita (origine: IAS, ID 2) nel Registro eventi sistema.</td>
<td style="border:1px solid black;">— MOM con uno script personalizzato mirato all'analisi delle voci del registro eventi per individuarvi un eventuale numero eccessivo di autenticazioni rifiutate.<br />
— Script di analisi di file o SQL Server per identificare un numero eccessivo di autenticazioni rifiutate.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione riuscita non autorizzata con credenziali rubate</td>
<td style="border:1px solid black;">I registri di accounting RADIUS indicano un'attività sospetta della rete</td>
<td style="border:1px solid black;">— Microsoft Access per importare registri basati su file ed eseguire query personalizzate.<br />
— Creazione di report per identificare informazioni su accessi inusuali alla rete memorizzate in un database SQL Server.</td>
</tr>
</tbody>
</table>
 

Oltre al monitoraggio di base della protezione, è consigliabile eseguire il controllo preventivo della protezione dei server IAS e utilizzare i componenti tecnologici correlati, onde capire quando la rete è in pericolo.

Nella tabella che segue sono elencati i potenziali pericoli per l'infrastruttura di server IAS e i relativi componenti tecnologici che è possibile utilizzare per eseguire un controllo preventivo.

**Tabella 13. Pericoli per l'infrastruttura dei server IAS da controllare preventivamente**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Pericolo</th>
<th style="border:1px solid black;" >Sintomo</th>
<th style="border:1px solid black;" >Strumento di controllo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Autorizzazione eccessiva per i dati cronologici e di configurazione di IAS</td>
<td style="border:1px solid black;">Membro non autorizzato dei gruppi IAS Admins, IAS Security Auditors o del gruppo locale Administrators.</td>
<td style="border:1px solid black;">Strumenti di controllo di Active Directory e dei gruppi di protezione locale, ad esempio DumpSec di SomarSoft.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Tentativi di nascondere l'autenticazione non autorizzata</td>
<td style="border:1px solid black;">Il Registro eventi sistema è inaspettatamente vuoto.</td>
<td style="border:1px solid black;">— Controllo del registro eventi di Windows mediante strumenti come EventcombMT, incluso in <em>Windows Server 2003 Resource Kit.</em><br />
— Strumento di monitoraggio del registro eventi e di segnalazione di avvisi, ad esempio MOM.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso non autorizzato al file dei segreti condivisi dei client RADIUS</td>
<td style="border:1px solid black;">ID utente ignoto con accesso all'oggetto file aperto nei registri di controllo delle cartelle.</td>
<td style="border:1px solid black;">Strumento di controllo e monitoraggio dei file di Windows, ad esempio MOM.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modifica non autorizzata dei registri di accounting e autenticazione RADIUS</td>
<td style="border:1px solid black;">ID utente inatteso con accesso in scrittura nei registri di controllo delle cartelle.</td>
<td style="border:1px solid black;">Strumento di controllo e monitoraggio dei file di Windows, ad esempio MOM.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo modulo è stata illustrata la progettazione di un'infrastruttura RADIUS per la protezione di una rete senza fili basata sullo standard 802.1X. Dato il probabile utilizzo futuro dell'infrastruttura RADIUS per altri tipi di gestione dell'accesso alla rete, tale infrastruttura è stata progettata con questa finalità. La progettazione qui presentata è abbastanza flessibile da consentirne l'estensione in base a numerosi requisiti futuri.
  
Le considerazioni illustrate in questo modulo verranno utilizzate nella *Guida all'implementazione* e nella *Guida operativa* per implementare l'infrastruttura RADIUS.
  
Nei restanti moduli di questa *Guida alla pianificazione* verrà trattata la progettazione di altri componenti essenziali di questa soluzione: le impostazioni 802.1X e l'infrastruttura necessarie per ottenere un rete WLAN protetta.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
Per ulteriori informazioni su IAS, vedere quanto segue:
  
-   Il sito Windows Server 2003 Support Center all'indirizzo [http://support.microsoft.com/default.aspx?scid=fh;IT;winsvr2003](http://support.microsoft.com/default.aspx?scid=fh;it;winsvr2003). La documentazione del prodotto include una panoramica delle funzionalità di IAS, istruzioni essenziali per la configurazione e procedure consigliate per la distribuzione.
  
-   Il manuale "Internet Authentication Service" incluso in *Microsoft Windows Server 2003 Resource Kit*, disponibile all'indirizzo <http://www.microsoft.com/windowsserver2003/techinfo/reskit/resourcekit.mspx> (in inglese). Questo manuale fornisce informazioni tecniche su IAS più dettagliate di quelle incluse nella documentazione del prodotto. Tali informazioni possono essere utilizzate come punto di riferimento qualora si abbia bisogno di maggiori dati.
  
-   Il manuale "Deploying IAS" incluso in *Microsoft Windows Server 2003 Deployment Kit*, disponibile all'indirizzo <http://www.microsoft.com/windowsserver2003/techinfo/reskit/deploykit.mspx> (in inglese). Questo manuale contiene linee guida sulla distribuzione utili per utilizzare IAS in svariate situazioni non trattate nell'ambito della presente guida alla realizzazione di una rete senza fili protetta ma che incidono sulle decisioni di progettazione.
  
Per ulteriori informazioni sulle tecnologie WLAN 802.1X, vedere:
  
-   Il white paper "Windows XP Wireless Deployment Technology and Component Overview" all'indirizzo <http://technet.microsoft.com/en-us/library/bb457015.aspx> (in lingua inglese).
  
#### Elementi di configurazione definiti dall'utente
  
Prima di iniziare la procedura di configurazione, occorre accertarsi di aver raccolto o deciso le impostazioni di tutti gli elementi indicati nella sottostante tabella.
  
**Tabella 14. Elementi di configurazione definiti dall'utente**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Elemento di configurazione</th>
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Nome variabile</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nome DNS (Domain Name System) del dominio principale dell'insieme di strutture Active Directory</td>
<td style="border:1px solid black;">woodgrovebank.com</td>
<td style="border:1px solid black;"><em>ForestRootDomain</em></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome NetBIOS (Network Basic Input/Output System) del dominio</td>
<td style="border:1px solid black;">WOODGROVEBANK</td>
<td style="border:1px solid black;"><em>NBDomainName</em></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome del server IAS principale</td>
<td style="border:1px solid black;">HQ— IAS — 01</td>
<td style="border:1px solid black;"><em>PrimaryIAShostname</em></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome del server IAS secondario</td>
<td style="border:1px solid black;">HQ— IAS — 02</td>
<td style="border:1px solid black;"><em>SecondaryIAShostname</em></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome del server IAS secondario</td>
<td style="border:1px solid black;">BO— IAS — 03</td>
<td style="border:1px solid black;"><em>TertiaryIAShostname</em></td>
</tr>
</tbody>
</table>
  
#### Elementi di configurazione prescritti nella soluzione
  
Le impostazioni specificate in questa tabella non devono essere modificate se non se ne ha una particolare necessità.
  
**Tabella 15. Elementi di configurazione prescritti nella soluzione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Elemento di configurazione</th>
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Nome variabile</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">[Accounts] Nome completo del gruppo amministrativo che controlla la configurazione di IAS</td>
<td style="border:1px solid black;">IAS Admins</td>
<td style="border:1px solid black;"><em>IASAdminsGroup</em></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Accounts] Nome pre-Windows 2000 del gruppo amministrativo che controlla la configurazione di IAS</td>
<td style="border:1px solid black;">IAS Admins</td>
<td style="border:1px solid black;"><em>IASAdminsNTGroup</em></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Accounts] Nome completo del gruppo che esamina i registri delle richieste di autenticazione e accounting IAS a fini di protezione</td>
<td style="border:1px solid black;">IAS Security Auditors</td>
<td style="border:1px solid black;"><em>IASSecAuditGroup</em></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Accounts] Nome pre-Windows 2000 del gruppo che esamina i registri delle richieste di autenticazione e accounting IAS a fini di protezione</td>
<td style="border:1px solid black;">IAS Security Auditors</td>
<td style="border:1px solid black;"><em>IASSecAuditNTGroup</em></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Scripts] Percorso degli script di installazione</td>
<td style="border:1px solid black;">C:\MSSScripts</td>
<td style="border:1px solid black;"><em>ScriptPath</em></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Config] Percorso dei file di backup della configurazione</td>
<td style="border:1px solid black;">D:\IASConfig</td>
<td style="border:1px solid black;"><em>ConfigPath</em></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Request Logs] Percorso dei registri delle richieste di autenticazione e controllo IAS</td>
<td style="border:1px solid black;">D:\IASLogs</td>
<td style="border:1px solid black;"><em>IASLogLocation</em></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Request Logs] Nome della condivisione dei registri delle richieste RADIUS</td>
<td style="border:1px solid black;">IASLogs</td>
<td style="border:1px solid black;"><em>IASLogShare</em></td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
