---
TOCTitle: 'Guida alla pianificazione - Progettazione di un''infrastruttura RADIUS per la protezione di reti LAN senza fili'
Title: 'Guida alla pianificazione - Progettazione di un''infrastruttura RADIUS per la protezione di reti LAN senza fili'
ms:assetid: '73625ab0-734a-4e59-be7d-0ad89ca1b39f'
ms:contentKeyID: 20200845
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536246(v=TechNet.10)'
---

Capitolo 5: Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili
==============================================================================================

Pubblicato: 11 ottobre 2004 | Aggiornato: 24/11/2004

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Utilizzo di IAS per la gestione dell'accesso alla rete](#eeaa)
[](#edaa)[Identificazione dei requisiti per la soluzione](#edaa)
[](#ecaa)[Progettazione di un'infrastruttura RADIUS](#ecaa)
[](#ebaa)[Creazione di un piano di gestione](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

In questo capitolo vengono descritte l'architettura e la progettazione dell'infrastruttura RADIUS (Remote Authentication Dial-In User Service) utilizzata in questa soluzione per reti WLAN (Wireless Local Area Network). L'infrastruttura RADIUS utilizza l'implementazione RADIUS di Microsoft - Servizio autenticazione Internet (IAS) di Microsoft®.

La prima finalità del capitolo è di illustrare le decisioni di progettazione relative all'infrastruttura IAS per la soluzione e le motivazioni di tali scelte.

Frasi quali “Questa soluzione utilizza l'opzione...” o “Questa progettazione utilizza...” presenti nel capitolo si riferiscono a decisioni che fanno parte della progettazione della soluzione, implementate nei capitoli relativi alla Guida alla creazione o alla Guida operativa della soluzione.

Un secondo obiettivo del capitolo è aiutare a valutare l'adeguatezza della progettazione per le necessità specifiche della propria organizzazione. Frasi quali “È necessario decidere...” indicano invece elementi per i quali è necessario prendere decisioni in base alle proprie esigenze. In genere, questi casi si trovano in parti di testo nelle quali viene discusso come estendere la soluzione per soddisfare le maggiori esigenze di protezione della propria organizzazione. Alcuni argomenti offrono quindi informazioni più dettagliate che consentono di comprendere tutte le implicazioni delle scelte a disposizione, rendendo superfluo il ricorso a ulteriori risorse.

#### Prima di iniziare

Prima di iniziare a leggere questo capitolo, è preferibile conoscere i concetti di RADIUS e delle opzioni di distribuzione IAS. La sezione “Ulteriori informazioni” alla fine di questo capitolo contiene risorse utili per approfondire questi argomenti. Inoltre, i capitoli relativi al Servizio autenticazione Internet del *Microsoft Windows Server*™ *2003 Resource Kit* e del *Microsoft Windows Server*™ *2003 Deployment Kit* contengono informazioni  utili  .

#### Panoramica del capitolo

Il capitolo è suddiviso in argomenti che trattano la progettazione di un'infrastruttura RADIUS. Le finalità del capitolo sono:

-   Definire l'utilizzo di IAS per fornire un'ampia soluzione di gestione dell'accesso alla rete e come si applichi in particolare alle reti WLAN.

-   Identificare i requisiti ambientali per la soluzione e analizzare l'infrastruttura esistente.

-   Discutere in dettaglio le decisioni relative all'architettura di un’infrastruttura RADIUS basata su IAS e specificatamente le scelte attinenti a una rete senza fili basata sul protocollo 802.1X.

-   Esplorare le possibili strategie di gestione dell'infrastruttura del server IAS.

-   Fornire fonti di informazioni per approfondire concetti, dettagli del prodotto e pianificazione della distribuzione.

Il diagramma di flusso riportato di seguito illustra la struttura del capitolo.

![](images/Dd536246.05fig5-1(it-it,TechNet.10).gif)

**Figura 5.1 Pianificazione di un'infrastruttura IAS**

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo di IAS per la gestione dell'accesso alla rete

Il Servizio autenticazione Internet (IAS) incluso in Windows Server™ 2003 di Microsoft rappresenta l'implementazione Microsoft di un server e un proxy RADIUS. In qualità di server RADIUS, IAS esegue l'autenticazione, l'autorizzazione e l'accounting centralizzati di vari tipi di connessioni di rete. In qualità di server proxy RADIUS, IAS è in grado di inoltrare le richieste RADIUS a un altro server RADIUS per l'esecuzione delle su indicate funzioni. IAS può essere utilizzato insieme con i server VPN (Rete privata virtuale, Virtual Private Network), ad esempio il servizio Routing e Accesso remoto (RRAS, Routing and Remote Access Service) basato su Microsoft Windows®, o con un'altra infrastruttura di accesso alla rete, quali i punti di accesso senza fili e i dispositivi Ethernet di autenticazione.

Per ottenere il massimo da un'infrastruttura RADIUS basata su IAS, occorre prendere una decisione mirata allo sfruttamento dei servizi centralizzati per la gestione dell'accesso alla rete che interessi l'intera azienda. Ciò include l'utilizzo di un database di account centralizzato, quale il servizio directory Microsoft Active Directory®, e la centralizzazione della gestione dei criteri di accesso alla rete su server IAS. Mediante la gestione centralizzata è possibile ridurre drasticamente i costi della gestione delle informazioni per il controllo dell'accesso alla rete memorizzate su dispositivi distribuiti. Inoltre, il ricorso ad account e a criteri di accesso alla rete centralizzati contribuisce a ridurre i rischi di protezione associati alla configurazione e alla gestione dei dispositivi distribuiti.

La pianificazione e la distribuzione di un'infrastruttura IAS rispondente alle esigenze presenti e future dell'organizzazione richiedono un'attenta considerazione. IAS non è stato ideato per fornire l'accesso a una rete isolata, quanto piuttosto per consentire una gestione strategica dell'accesso alla rete in diversi contesti.

#### Identificazione dei requisiti dell'organizzazione in termini di gestione dell'accesso alla rete

Il Servizio autenticazione Internet (IAS) incluso in Windows Serve 2003 supporta vari scenari di accesso alla rete, tra cui i seguenti:

-   **Accesso senza fili** È possibile configurare punti di accesso senza fili compatibili con lo standard 802.1X affinché utilizzino i servizi di autenticazione, autorizzazione e accounting di IAS per il controllo dell'accesso alla rete WLAN basato sullo standard 802.11, nonché per la gestione delle chiavi.

-   **Accesso cablato** I dispositivi Ethernet conformi allo standard 802.1X possono utilizzare i servizi di autenticazione, autorizzazione e accounting di IAS per il controllo dell'accesso per porta alle reti LAN cablate.

-   **Accesso VPN** I server VPN, ad esempio RRAS basato su Windows, possono utilizzare i servizi di autenticazione, autorizzazione e accounting di IAS per il controllo dell'accesso alla rete aziendale, nonché per la gestione delle chiavi.

-   **Connessione remota** I server di connessione remota, quali i server di Routing e Accesso remoto (RRAS) basati su Windows possono utilizzare i servizi di autenticazione, autorizzazione e accounting di IAS per il controllo dell'accesso alla rete aziendale.

-   **Accesso Extranet** I server di accesso Extranet possono utilizzare i servizi di autenticazione, autorizzazione e accounting di IAS quando forniscono ai partner aziendali l'accesso limitato alle risorse condivise.

-   **Gestione esterna dell'accesso alla rete aziendale** I fornitori di soluzioni di rete possono utilizzare i servizi di autenticazione, autorizzazione e accounting di IAS per integrare l'infrastruttura di rete gestita esternamente con i database degli account e i criteri di controllo dell'accesso in uso presso i clienti. Inoltre, IAS è in grado di fornire le informazioni di accounting necessarie per fatturare questo servizio ai clienti.

-   **Accesso Internet** I provider di servizi Internet (ISP, Internet Service Provider) possono sfruttare i servizi di autenticazione, autorizzazione e accounting di IAS per fornire l'accesso a Internet in connessione remota e ad alta velocità utilizzando al contempo i database degli account e i criteri di controllo dell'accesso in uso presso le singole organizzazioni. IAS è in grado di fornire le informazioni di accounting necessarie per fatturare questo servizio ai clienti.

Per ottimizzare l'investimento in un'infrastruttura IAS e ridurre al minimo le modifiche future, è opportuno valutare ciascuno degli scenari in rapporto alla propria organizzazione. Sebbene IAS venga utilizzato in questa soluzione solo per l'accesso alla rete senza fili, il suo impiego potrebbe essere esteso a supporto di ciascuno di tali scenari. Per informazioni sull'estensione dell'infrastruttura RADIUS a supporto di altri scenari, fare riferimento al capitolo "Architettura della soluzione di rete LAN senza fili protetta".

#### Utilizzo di IAS per la gestione dell'accesso alla rete senza fili

In seguito all'adozione di standard di settore quali IEEE (Institute of Electrical and Electronics Engineers) 802.11, le reti WLAN stanno diventando sempre più diffuse. Questo tipo di rete consente agli utenti di spostarsi all'interno di un edificio o di un gruppo di edifici e, allo stesso tempo, avere la possibilità di collegarsi automaticamente alla rete mediante un punto di accesso senza fili (AP, Access Point).

Pur essendo estremamente pratiche, le reti WLAN presentano i seguenti rischi per la protezione:

-   Chiunque disponga di una scheda di rete WLAN compatibile può ottenere l'accesso alla rete.

-   I segnali delle reti senza fili utilizzano le onde radio per inviare e ricevere informazioni. Chiunque si trovi nel raggio d'azione di un punto di accesso senza fili può individuare e ricevere tutti i dati inviati da e verso tale punto di accesso.

Per ovviare al primo rischio, è possibile impostare i punti di accesso senza fili come client RADIUS e, quindi, configurarli per inviare le richieste di accesso e i messaggi di accounting a un server RADIUS centrale in cui viene eseguito IAS. Per far fronte al secondo rischio, è possibile crittografare i dati scambiati tra i dispositivi senza fili e i punti di accesso senza fili.

IAS fornisce una protezione avanzata per le reti WLAN in due modi: fungendo da server RADIUS per i punti di accesso senza fili e per i dispositivi client IEEE 802.1X, nonché fornendo chiavi di crittografia dinamiche mediante protocolli di autenticazione basati su certificati, quale il protocollo EAP-TLS (Extensible Authentication Protocol-Transport Layer Security).

**Nota:** in questa guida, per descrivere i punti di accesso senza fili si ricorre anche all'espressione client RADIUS. Sebbene i punti di accesso senza fili non siano il solo tipo possibile di client RADIUS, sono gli unici trattati in questa guida e, pertanto, le due espressioni vengono utilizzate come se fossero dei sinonimi.

[](#mainsection)[Inizio pagina](#mainsection)

### Identificazione dei requisiti per la soluzione

Prima di iniziare a progettare una soluzione di gestione dell'accesso senza fili mediante IAS, occorre essere certi di aver compreso i requisiti esistenti necessari relativi all'ambiente.

#### Considerazioni su Active Directory

Questa soluzione si rivolge alle organizzazioni che adottano Active Directory e utilizzano Windows 2000 Server o versioni successive nei controller di dominio. Questi requisiti sono essenziali in questa soluzione in quanto in materia di progettazione dell'infrastruttura RADIUS sono state prese decisioni che implicano l'utilizzo di funzionalità disponibili solo in domini Windows 2000 (o versioni successive) in modalità nativa. Nella tabella seguente vengono illustrate alcune funzionalità utilizzate in questa soluzione e il relativo supporto nei vari livelli di funzionalità di un dominio.

**Tavola 5.1. Funzionalità del dominio di Windows utilizzate nella soluzione**

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
<th><p>Funzionalità</p></th>
<th><p>Windows Server 2003 in modalità nativa</p></th>
<th><p>Windows 2000 in modalità nativa</p></th>
<th><p>Modalità mista</p>
<p>o</p>
<p>Microsoft Windows NT® 4.0</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Gruppi universali e nidificati</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Nome principale utente (UPN, User Principal Name)</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Controllo dell'accesso tramite autorizzazione Criteri di accesso remoto disponibile nell'account utente</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Supporto per il protocollo EAP-TLS</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>Sì</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>
</tbody>
</table>
  
**Nota:** l'implementazione di Servizi certificati inclusa in questa soluzione presenta anche dei requisiti specifici di Active Directory. Per ulteriori informazioni, consultare il capitolo 4, “Progettazione dell’infrastruttura a chiave pubblica (PKI)”.
  
Sebbene non indispensabile, dopo aver letto il presente capitolo si potrebbe decidere di distribuire IAS nei controller di dominio. Questa soluzione si basa sul Servizio autenticazione Internet (IAS) incluso in Windows Server 2003 e pertanto richiede l'aggiornamento dei controller di dominio di destinazione a questa versione del sistema operativo. Nel corso del presente capitolo verranno fornite ulteriori informazioni sulla distribuzione di IAS nei controller di dominio.
  
#### Infrastruttura RADIUS esistente
  
Questa soluzione non prevede l'integrazione con server RADIUS esistenti nell'ambiente in uso. Tuttavia, è possibile integrare i server esistenti basati su IAS e di terze parti con la presente soluzione. Nella maggior parte dei casi è consigliabile utilizzare il Servizio autenticazione Internet (IAS) di Windows Server 2003 per le funzionalità correlate all'accesso alla rete WLAN.
  
I server RADIUS meno recenti basati su Windows possono essere aggiornati a Windows Server 2003, così da poter essere utilizzati in questa soluzione come server RADIUS principali. In alternativa è possibile modificare i server RADIUS esistenti in modo che fungano da proxy e inoltrino il traffico RADIUS ai nuovi server RADIUS basati su Windows Server 2003.
  
Per istruzioni dettagliate sulla pianificazione della migrazione dell'infrastruttura RADIUS esistente al Servizio autenticazione Internet (IAS) di Windows Server 2003, contattare il partner Microsoft oppure il responsabile clienti Microsoft, che è in grado di indirizzare verso il partner appropriato o ai professionisti di Microsoft Consulting Services.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Progettazione di un'infrastruttura RADIUS
  
Quando si utilizza IAS per supportare l'accesso WLAN basato sullo standard 802.1X, occorre prendere numerose decisioni relative alla progettazione. In questa sezione vengono illustrate alcune di tali decisioni, nonché le opzioni scelte per questa soluzione. È necessario valutare ciascuna di tali decisioni per verificarne l'applicabilità al proprio ambiente.
  
#### Determinazione del ruolo di IAS come server RADIUS
  
I server IAS possono essere distribuiti in modo che funzionino in uno dei tre seguenti ruoli concettuali RADIUS:
  
-   Server RADIUS
  
-   Server proxy RADIUS
  
-   Server proxy e server RADIUS
  
    **Nota:** nella presente guida le espressioni server RADIUS e server proxy RADIUS vengono utilizzate per descrivere un server IAS configurato in modo tale da svolgere questi ruoli.
  
Nella tabella seguente vengono descritte alcune delle funzionalità dei server configurati per svolgere questi ruoli e la relativa utilità in scenari reali.
  
**Tavola 5.2. Ruoli RADIUS del server IAS**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Ruolo RADIUS del server IAS</p></th>
<th><p>Funzionalità</p></th>
<th><p>Scenario</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Server RADIUS</p></td>
<td style="border:1px solid black;"><p>- Controlla le credenziali direttamente in Active Directory o altre origini dati autorevoli.<br />
- Utilizza Criteri di accesso remoto per determinare l'accesso alla rete.</p></td>
<td style="border:1px solid black;"><p>Necessario per tutti gli scenari di gestione dell'accesso alla rete.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Server proxy RADIUS</p></td>
<td style="border:1px solid black;"><p>- Indirizza la richiesta in base alle sue proprietà.<br />
- È in grado di modificare le proprietà RADIUS delle richieste in transito.<br />
- Fornisce il bilanciamento del carico delle richieste RADIUS per i gruppi di server RADIUS.</p></td>
<td style="border:1px solid black;"><p>- Utile in scenari con più insiemi di strutture in cui i dispositivi di accesso alla rete sono condivisi.<br />
- Utile per la distribuzione di architetture di rete di vasta scala di tipo front-end/back-end con servizi di autenticazione, autorizzazione e accounting.<br />
- Utile per raggruppare autenticazioni a organizzazioni esterne.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Server proxy e server RADIUS</p></td>
<td style="border:1px solid black;"><p>Combinazione delle due precedenti funzionalità.</p></td>
<td style="border:1px solid black;"><p>Combinazione dei due scenari.</p></td>
</tr>
</tbody>
</table>
  
Non tutti i ruoli RADIUS sono necessari per gli scenari di gestione dell'accesso alla rete. Per molte organizzazioni, ad esempio, la gestione dell'accesso WLAN richiede solo il ruolo di server RADIUS. Se tuttavia l'organizzazione prevede di utilizzare l'infrastruttura di rete senza fili per utenti e dispositivi di più insiemi di strutture Active Directory, è necessario anche il ruolo di server proxy RADIUS onde indirizzare le richieste ai diversi server RADIUS di ciascun insieme di strutture.
  
Per maggiore semplicità e contenere i costi, questa soluzione include server IAS configurati unicamente come server RADIUS e non come server proxy RADIUS.
  
#### Informazioni sul failover dei server e sul bilanciamento del carico
  
Il servizio RADIUS è un componente essenziale di qualsiasi soluzione di gestione dell'accesso alla rete WLAN basata sullo standard 802.1X. La disponibilità di server IAS a servizio di punti di accesso senza fili determina la disponibilità della rete WLAN per gli utenti finali. Pertanto, è necessario garantire che due o più server IAS siano sempre al servizio dei punti di accesso senza fili. Nella maggior parte dei punti di accesso senza fili di ultima generazione è possibile configurare due server RADIUS per l'autenticazione e due server RADIUS per l'accounting. In tal modo, viene assicurato che la perdita di contatto con un server RADIUS non incida sul servizio fornito ai client WLAN.
  
Per implementare più server per garantire la capacità di recupero dagli errori, molte organizzazioni scelgono uno schema in base al quale eseguire il bilanciamento del carico delle richieste provenienti dai punti di accesso senza fili configurati come client RADIUS su tutti i server RADIUS, così da assicurare che non vengano limitate le risorse di alcun server.
  
Prima di scegliere una strategia di bilanciamento del carico, è importante sapere che lo standard 802.1X prevede l'implementazione del protocollo EAP nell'ambito del servizio RADIUS (EAP-RADIUS) tra i punti di accesso senza fili e i server RADIUS. Sebbene il servizio RADIUS utilizzi il protocollo UDP (User Datagram Protocol) senza connessione, il protocollo EAP è orientato alla sessione e ne viene effettuato il tunneling all'interno del servizio RADIUS. Ciò comporta che più pacchetti EAP-RADIUS comprendenti una sola operazione di autenticazione vengano restituiti allo stesso server RADIUS altrimenti i tentativi di autenticazione avranno esito negativo
  
Nella tabella seguente vengono illustrate le varie opzioni che consentono di assicurare che i client RADIUS possano utilizzare più server RADIUS per il recupero dagli errori ed eseguire il bilanciamento del carico delle richieste RADIUS.
  
**Tavola 5.3. Opzioni per il failover e il bilanciamento del carico EAP-RADIUS**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Metodo di failover e bilanciamento del carico</p></th>
<th><p>Vantaggi</p></th>
<th><p>Svantaggi</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Proxy IAS con gruppi di server RADIUS</p></td>
<td style="border:1px solid black;"><p>- Rilevamento del mancato funzionamento del servizio RADIUS con failover e failback.<br />
- Distribuzione del carico di traffico in base alle proprietà del traffico stesso.<br />
- Gestione dello stato della sessione EAP durante l'esecuzione del bilanciamento del carico.<br />
- Distribuzione delle richieste sui server in base alle impostazioni di priorità e peso.</p></td>
<td style="border:1px solid black;"><p>- Server IAS aggiuntivi necessari.<br />
- Richiede comunque che i punti di accesso siano configurati con gli indirizzi IP dei proxy RADIUS principale e secondario.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Impostazione dei server RADIUS principale e secondario nei punti di accesso senza fili</p></td>
<td style="border:1px solid black;"><p>- Configurazione semplificata per ambienti di ridotte dimensioni.<br />
- Il punto di accesso senza fili rileva l'assenza di traffico ed esegue il failover.<br />
- Utilizza la funzionalità nativa del punto di accesso senza fili.</p></td>
<td style="border:1px solid black;"><p>- Richiede una pianificazione e un monitoraggio accurati della selezione dei server RADIUS principale e secondario.<br />
- Molti punti di accesso senza fili non supportano la funzionalità di failback, causando lo sbilanciamento del carico sui server.</p></td>
</tr>
</tbody>
</table>
<p> </p>

È consigliabile che le organizzazioni di notevoli dimensioni e i grandi provider di servizi di rete prendano in considerazione l'utilizzo dei proxy RADIUS per l'accettazione delle richieste provenienti dai client RADIUS e la distribuzione del carico tra i server RADIUS, che possono essere configurati in gruppi di server RADIUS. La distribuzione del traffico di rete tra i server RADIUS nei gruppi di server RADIUS può basarsi su vari parametri configurabili, ad esempio il tipo di traffico RADIUS e gli attributi RADIUS, oltre che sui valori relativi a priorità e peso. I server RADIUS di ogni gruppo di server RADIUS possono quindi eseguire l'autenticazione e l'autorizzazione di base per gli utenti e i dispositivi di un dominio o di un intero insieme di strutture. In tal modo si crea un'architettura front-end/back-end a servizio delle richieste RADIUS e si fornisce la maggior flessibilità possibile per le opzioni di bilanciamento del carico e di scalabilità.

![](images/Dd536246.05fig5-2(it-it,TechNet.10).gif)

**Figura 5.2 Failover e bilanciamento del carico mediante i proxy RADIUS**

Tuttavia, le capacità native di failover ai server RADIUS incluse nei punti di accesso senza fili di ultima generazione forniscono una capacità di recupero sufficiente per la maggior parte delle organizzazioni. Se questo non è abbastanza sofisticato, il percorso di migrazione a una strategia di bilanciamento del carico e failover basata su server proxy RADIUS è relativamente semplice. Uno svantaggio della strategia di bilanciamento del carico e failover basata su punti di accesso senza fili è rappresentato dal sovraccarico di gestione richiesto per l'abbinamento dei punti di accesso senza fili ai server RADIUS, al monitoraggio dei server RADIUS finalizzato all'equa distribuzione del carico e alle modifiche da apportare laddove necessario. Un altro svantaggio è costituito dal fatto che alcuni modelli di punti di accesso senza fili non supportano il failback. Il failback si verifica quando un punto di accesso, che ha eseguito un failover per utilizzare un server RADIUS secondario, torna automaticamente al server RADIUS primario designato appena il server primario viene ripristinato. Senza il failback, tutti i punti di accesso senza fili potrebbero eseguire il failover nel server RADIUS secondario e richiederebbero l'intervento di un amministratore per essere reindirizzati al server primario corretto.

Per ottenere il bilanciamento del carico mediante una strategia di failover basata su punti di accesso senza fili qualora siano disponibili localmente più server RADIUS:

-   Configurare metà dei punti di accesso senza fili di ogni sede affinché utilizzino innanzitutto il server RADIUS principale e il server RADIUS secondario in caso di mancato funzionamento del server RADIUS principale.

-   Configurare l'altra metà dei punti di accesso senza fili di ogni sede affinché utilizzino innanzitutto il server RADIUS secondario e il server RADIUS principale in caso di mancato funzionamento del server RADIUS secondario.

    **Nota:** i termini "primario" e "secondario" non indicano alcuna differenza di funzionalità tra i server che sono di pari livello. Tali termini sono utilizzati in questo contesto per distinguere i vari server ai fini dell'analisi del failover.

    ![](images/Dd536246.05fig5-3(it-it,TechNet.10).gif)

    **Figura 5.3 Failover e bilanciamento del carico basati su punti di accesso senza fili**

Per realizzare il bilanciamento del carico mediante una strategia di failover basata su punti di accesso senza fili nelle filiali in cui è disponibile un solo server RADIUS locale, oltre a un server RADIUS remoto, è necessario configurare tutti i punti di accesso senza fili della filiale in modo che utilizzino il server RADIUS locale come server principale. Quindi configurare il server RADIUS remoto come server secondario da utilizzare qualora quello principale non funzioni.

[![](images/Dd536246.05fig5-4(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536246.05fig5-4_big(it-it,technet.10).gif)

**Figura 5.4 Failover e bilanciamento del carico basati su punti di accesso senza fili con server RADIUS locali e remoti**

Nei casi di filiali, assicurarsi che i punti di accesso senza fili siano in grado di eseguire il failback al server RADIUS principale quando quest'ultimo torna a funzionare, altrimenti occorrerà riconfigurare manualmente i punti di accesso senza fili per evitare che il servizio RADIUS attraversi inutilmente la rete WAN.

**Nota:** per informazioni sul supporto della funzionalità di failback dei vari prodotti, consultare il proprio fornitore hardware.

I server RADIUS della filiale sono opzionali, in alternativa, è possibile utilizzare server RADIUS su una rete WAN. Senza un server RADIUS e un controller di dominio locali, tuttavia, gli utenti di un ufficio remoto non possono accedere alla rete WLAN locale in caso di interruzioni del servizio.

Questa soluzione è stata ideata con l'intento di utilizzare il failover tra server basato su punti di accesso senza fili e la configurazione manuale per il bilanciamento del carico. Per ulteriori informazioni sulla pianificazione di un'infrastruttura RADIUS in grado di utilizzare i proxy RADIUS per il failover e il bilanciamento del carico tra server, consultare il capitolo "Deploying* *IAS”* *incluso in *Microsoft Windows Server* *2003 Deployment Kit* (in inglese). I riferimenti relativi a questa risorsa sono forniti alla fine del presente capitolo.

#### Definizione dei requisiti di registrazione

È possibile configurare i server IAS in modo che registrino due tipi di informazioni facoltative:

-   Eventi di autenticazione riusciti e rifiutati.

-   Informazioni di autenticazione e di accounting RADIUS.

Gli eventi di autenticazione riusciti e rifiutati che vengono generati a partire da dispositivi e utenti che tentano di accedere alla rete WLAN vengono registrati per impostazione predefinita in IAS nel Registro eventi di sistema di Windows Server 2003. Le informazioni del Registro eventi di autenticazione sono particolarmente utili per la risoluzione dei problemi di autenticazione, sebbene possano essere utilizzate anche per il controllo della protezione e la segnalazione di avvisi.

Inizialmente è consigliabile lasciare attivate le opzioni per la registrazione degli eventi **riusciti** e **rifiutati**, ma è possibile disattivare l'opzione per la registrazione degli eventi **riusciti** una volta che il sistema è diventato stabile. Questo perché gli eventi di accesso riuscito alla rete WLAN tendono a saturare rapidamente il Registro eventi di sistema e l'uso di questa opzione potrebbe risultare inutile ai fini della protezione qualora sia attiva la registrazione delle richieste di autenticazione RADIUS.

È consigliabile che le organizzazioni utilizzino strumenti di monitoraggio, ad esempio Microsoft Operations Manager (MOM), per trattare mediante script personalizzati gli eventi IAS inclusi nel Registro eventi di sistema. Uno script personalizzato MOM potrebbe ad esempio rilevare un aumento del numero di eventi IAS correlati a tentativi rifiutati di autenticazione e informarne l'amministratore affinché agisca conseguentemente.

IAS consente inoltre di salvare le informazioni sulle sessioni di autenticazione e accesso alla rete sotto forma di registri di richieste RADIUS. È possibile attivare e disattivare le informazioni seguenti incluse nei registri delle richieste RADIUS:

-   Richieste di accounting, ad esempio messaggi di inizio e fine accounting che segnalano l'avvio e la chiusura di una sessione di accesso alla rete.

-   Richieste di autenticazione, ad esempio messaggi di accettazione o rifiuto di accesso che indicano la riuscita o meno dei tentativi di autenticazione.

-   Stato periodico, ad esempio richieste di accounting temporaneo inviate da alcuni dispositivi di accesso alla rete.

I registri delle richieste RADIUS si dimostrano assai utili per organizzazioni quali i provider di servizi di rete che addebitano ai clienti il servizio in base all'utilizzo della rete. È possibile, tuttavia, utilizzare i registri delle richieste RADIUS per il monitoraggio e il controllo della protezione. In particolare, i registri di autenticazione e accounting RADIUS consentono a coloro che si occupano di monitorare la protezione di determinare quanto segue:

-   Dettagli dei tentativi non autorizzati di autenticazione nella rete WLAN.

-   Durata delle connessioni accettate alla rete WLAN.

IAS può accedere ai registri di testo o ai database Microsoft SQL Server™ 2000. In IAS la registrazione in formato testo delle informazioni di autenticazione e accounting RADIUS è disattivata per impostazione predefinita. Prima di attivarla è necessario:

-   Parlare con il personale addetto alla protezione per venire a conoscenza dei requisiti occorrenti e tenere traccia delle informazioni sull'accesso alla rete WLAN, nonché di quali dettagli sono necessari.

-   Eseguire test di laboratorio della registrazione RADIUS in formato testo, per conoscere i requisiti hardware dei server (unità disco e CPU) in presenza di carico dovuto agli utenti della rete WLAN. L'accesso alla rete WLAN può generare molte più informazioni rispetto ad altri tipi di accesso alla rete.

-   Valutare quali informazioni sulle richieste RADIUS (autenticazione, accounting e stato periodico) sono necessarie e quali non lo sono. L'accesso alla rete WLAN può generare quantità notevoli di informazioni che possono occupare rapidamente lo spazio su disco.

-   Stabilire una strategia per l'accesso, la memorizzazione e l'archiviazione delle informazioni dei registri delle richieste RADIUS. È possibile salvare queste informazioni come file di testo sul disco rigido di ciascun server IAS o in un database SQL Server.

Le organizzazioni che devono utilizzare i registri di accounting RADIUS dovrebbero considerare l'uso delle funzioni di registrazione SQL Server di IAS. È possibile accedere alle informazioni di accounting RADIUS in SQL Server Desktop Engine (MSDE) su ogni server IAS e, quindi, replicarle in un cluster centrale SQL Server. L'adozione di questa strategia consente di realizzare un sistema di memorizzazione centralizzato e strutturato dei dati di accounting RADIUS, così da rendere più semplici l'esecuzione di query, la creazione di report e le attività di archiviazione. L'accesso di SQL Server ai database MSDE locali elimina, inoltre, la possibilità di incorrere in problemi di rete impedendo al server IAS di accedere a queste informazioni e consentendo di rifiutare le richieste di accesso alla rete che si basano sulle informazioni sull'account.

Le organizzazioni prive di SQL Server 2000 o a corto di personale in grado di eseguire query, creare report e archiviare i registri delle richieste RADIUS possono comunque prendere in considerazione la possibilità di eseguire la registrazione di queste informazioni per facilitare le indagini in caso di problemi di protezione. Molte delle decisioni di progettazione correlate alla registrazione RADIUS in questa soluzione sono state prese come indicato nella seguente tabella. Riesaminare queste informazioni per determinare quali soddisfano i requisiti del proprio ambiente.

**Tabella 5.4. Decisioni di progettazione in relazione alla registrazione IAS**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Decisione di progettazione in relazione alla registrazione IAS</p></th>
<th><p>Commenti</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>La dimensione del Registro eventi di sistema indicata nel modello dei criteri di gruppo IAS della documentazione <em>Windows Server</em> <em>2003 Security Guide</em> è stata incrementata rispetto al valore predefinito, al fine di poter registrare i numerosi eventi IAS.</p></td>
<td style="border:1px solid black;"><p>Se si sceglie di non attivare la registrazione delle richieste di autenticazione RADIUS, il Registro eventi di sistema rappresenta la registrazione principale degli eventi di protezione connessi all'accesso alla rete WLAN per impostazione predefinita. Considerare con attenzione le impostazioni, ad esempio l'impostazione predefinita per <strong>Sovrascrivi eventi se necessario,</strong> poiché in tal modo, i dati di controllo potrebbero venire sovrascritti quando il registro è pieno.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>È stata attivata la registrazione delle richieste di accounting e autenticazione RADIUS in file di testo.</p></td>
<td style="border:1px solid black;"><p>Questa decisione comporta un aumento del carico sulla CPU e dei requisiti di spazio su disco dei server IAS.<br />
IAS interromperà l'accettazione delle richieste di autenticazione e accounting se non è possibile eseguire la registrazione. Pertanto, occorre prestare attenzione a possibili attacchi DoS (Negazione di servizio, Denial of Service) volti al riempimento del disco dei file di registro.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Le specifiche hardware dei server IAS indicate nella presente guida prevedono un volume disco distinto per i file di registro su dischi fisici separati.</p></td>
<td style="border:1px solid black;"><p>Questa decisione assicura che le prestazioni in scrittura dei file di registro delle richieste RADIUS incidano il meno possibile sulla gestione dell'accesso alla rete RADIUS. Questa decisione garantisce inoltre che gli eventi che provocano il riempimento di un volume disco non incidano sulla recuperabilità dei server.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Le opzioni corrispondenti alle voci relative all'autenticazione e all'accounting RADIUS sono state attivate, mentre non sono state attivate quelle relative allo stato periodico.</p></td>
<td style="border:1px solid black;"><p>In tal modo, si può assicurare che vengano registrate solo le informazioni essenziali necessarie per determinare lo stato delle autenticazioni e la durata delle sessioni. L'opzione relativa allo stato periodico è stata omessa per ridurre i requisiti dei file di registro. È consigliabile valutare la possibilità di attivare la registrazione periodica dello stato qualora sia importante registrare la durata delle sessioni dell'utente nel proprio ambiente.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Per i file di registro dell'autenticazione e accounting RADIUS è stato scelto il formato di database compatibile con ODBC (Open Database Connectivity).</p></td>
<td style="border:1px solid black;"><p>Questa scelta consente agli amministratori di importare con facilità i file di registro in database compatibili con ODBC, così da semplificarne l'analisi, e può considerarsi una procedura consigliata. Inoltre, per esplorare i file è possibile utilizzare IASPARSE.exe, incluso negli strumenti di supporto di Windows Server 2003.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>L'intervallo per la creazione di nuovi file di registro è stato impostato su <strong>Mensile</strong>.</p></td>
<td style="border:1px solid black;"><p>La scelta di un intervallo che generi un numero inferiore di file di registro ne facilita l'importazione nei database o l'esplorazione mediante IASPARSE.exe se la registrazione SQL Server non viene utilizzata. Questa opzione dovrebbe essere considerata a fronte del rischio di riempire un disco rigido con un solo file di registro.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>È stata impostata un'opzione per la registrazione delle richieste RADIUS in modo tale da eliminare il file di registro meno recente quando il disco è pieno.</p></td>
<td style="border:1px solid black;"><p>Il rischio di questa impostazione predefinita è rappresentato dal fatto che le informazioni di protezione possono andare perse qualora il disco di un file di registro divenga pieno. Questa impostazione è stata selezionata per evitare di interrompere i server IAS quando il file di registro diventa pieno.<br />
Se si ritiene più importante conservare i registri di protezione rispetto al fatto di garantire la disponibilità del servizio, è consigliabile disattivare questa impostazione.</p></td>
</tr>
</tbody>
</table>
<p> </p>

#### Scelta di centralizzare o distribuire i server

La decisione di utilizzare server IAS centralizzati o distribuiti si basa in parte sulla distribuzione geografica dell'organizzazione e sulla strategia di distribuzione dell'infrastruttura IT dell'organizzazione. Occorre considerare quale dei tre seguenti tipi di strategia per l'infrastruttura IT è più vicino a quello dell'organizzazione:

-   Infrastruttura IT centralizzata

-   Infrastruttura IT distribuita

-   Infrastruttura IT mista

L'obiettivo principale di numerose organizzazioni IT moderne è di utilizzare un'infrastruttura IT sempre più ridotta, basata su componenti centralizzati e con maggiore capacità di recupero dagli errori. Il raggiungimento di questo obiettivo richiede un notevole investimento in componenti infrastrutturali WAN ad alta velocità e con maggiore capacità di recupero dagli errori, così da garantire che gli utenti nelle filiali godano dello stesso livello di servizio IT degli utenti che si trovano nella sede centrale. Un vantaggio di questa strategia è rappresentato dal fatto che il costo dell'infrastruttura a server distribuiti può essere dirottato verso l'infrastruttura di rete e la larghezza di banda. Inoltre, l'infrastruttura dei server si trova a poca distanza dal personale tecnico specializzato e dal personale addetto all'esercizio del data center. Pertanto è possibile ottenere un maggiore livello di disponibilità.

La centralizzazione dei server IAS in organizzazioni con infrastrutture WAN ad alta velocità e con maggiore capacità di recupero dagli errori contribuisce a ridurre i costi di una soluzione WLAN 802.1X. Questo tipo di strategia dell'infrastruttura IT dovrebbe essere considerato il punto di partenza per la progettazione di server RADIUS nelle organizzazioni aziendali. Il protocollo RADIUS non sfrutta in modo eccessivo la larghezza di banda e funziona bene sui collegamenti WAN. Occorre tenere presente, inoltre, che potrebbe non essere più possibile utilizzare i protocolli DHCP (Dynamic Host Configuration Protocol) in attesa che venga completata l'autenticazione 802.1X. È essenziale anche disporre di una connessione ad alte prestazioni tra i server IAS e i controller di dominio che contengono gli utenti e i gruppi utilizzati per determinare l'accesso alla rete. Molti potenziali problemi con lo standard di rete 802.1X possono essere evitati garantendo che le comunicazioni tra i server IAS e Active Directory avvengano ad alta velocità.

Tuttavia, per molte organizzazioni il costo della larghezza di banda, di sofisticati dispositivi di rete e di connessioni WAN ridondanti impedisce l'adozione di un modello di infrastruttura IT centralizzata. Queste organizzazioni, infatti, preferiscono adottare un modello di infrastruttura IT decentralizzata con un'infrastruttura server distribuita nelle filiali per garantire, in tal modo, la continuità del servizio IT in caso di caso di guasti alla rete WAN.

Un terzo tipo di strategia per l'infrastruttura IT consente alle organizzazioni di centralizzare l'infrastruttura IT dove possibile e di distribuirla dove necessario. Questa strategia consente di raggruppare la maggior parte dell'infrastruttura IT in sedi hub a servizio degli utenti di tali sedi e di quelli delle filiali collegate all'hub. Allo stesso tempo, questo modello consente di distribuire l'infrastruttura server in filiali con molti utenti finali. Il diagramma seguente illustra un esempio di infrastruttura IT mista.

[![](images/Dd536246.05fig5-5(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536246.05fig5-5_big(it-it,technet.10).gif)

**Figure 5.5 Un'organizzazione con un'infrastruttura IT mista centralizzata e distribuita**

Questa soluzione, progettata in vista di modelli di distribuzione dell'infrastruttura server centralizzata, decentralizzata e mista, fornisce quanto segue:

-   Configurazione di sedi hub di grandi dimensioni con due server RADIUS in grado di gestire le richieste locali e quelle di uffici privi di infrastruttura server.

-   Configurazione di filiali di grandi dimensioni con un server RADIUS facoltativo di filiale.

    **Nota:** in uffici di piccole dimensioni privi di infrastruttura server, l'accesso alle reti WLAN dipende dalla disponibilità della rete WAN.

#### Determinazione del numero e della posizione dei server

Ogni insieme indipendente di strutture Active Directory dovrebbe includere almeno due server IAS che fungano da server RADIUS per gli utenti e i dispositivi dell'insieme di strutture. Ciò assicura che le richieste di accesso alla rete continuino a essere gestite qualora uno dei server RADIUS non sia disponibile.

Le sedi centrali delle aziende, al cui interno lavorano molti utenti, rappresentano i candidati ideali per un'infrastruttura basata su due o più server RADIUS. Se tra più sedi hub con server RADIUS è disponibile una larghezza di banda ad alta velocità, è possibile configurare i punti di accesso senza fili in modo che eseguano il failover ai server RADIUS di una rete WAN. Quando si pianifica l'uso di server RADIUS su una rete WAN, tuttavia, è necessario stabilire se il collegamento di rete tra i server RADIUS e i controller di dominio nel proprio ambiente sia adeguato. È consigliabile inoltre verificare i valori di timeout per punti di accesso senza fili e computer client e modificare i parametri dei punti di accesso, se necessario. Occorre, infine, individuare i server RADIUS presenti nel dominio principale dell'insieme di strutture per ottimizzare le operazioni Kerberos.

Le filiali abbastanza grandi da garantire controller di dominio e che sono prive di connessioni WAN alle sedi hub con capacità di recupero dagli errori sono candidati probabili a ospitare un server RADIUS locale. Se l'organizzazione non ha implementato funzionalità WAN di recupero dagli errori, occorre valutare il costo iniziale e di esercizio di un server IAS di filiale rispetto al costo in cui si incorre nel caso in cui si verifichino guasti alla rete WAN e gli utenti della rete WLAN non possano accedervi.

#### Installazione di IAS insieme con altri servizi

Vista la notevole quantità di comunicazioni stabilite tra il server IAS e i controller di dominio Active Directory, è possibile migliorare le prestazioni eseguendo il server IAS sullo stesso server dei controller di dominio, in modo da evitare problemi di latenza correlati alle comunicazioni sulla rete. Occorre, tuttavia, considerare con attenzione le implicazioni derivanti dall'installazione del server IAS sui controller di dominio. Nella tabella seguente vengono riportati i dettagli relativi a tali considerazioni.

**Tabella 5.5. Considerazioni sull'installazione di IAS e dei controller di dominio sullo stesso hardware**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Posizione di IAS</p></th>
<th><p>Vantaggi</p></th>
<th><p>Svantaggi</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Installato nei controller di dominio</p></td>
<td style="border:1px solid black;"><p>- Incremento delle prestazioni per l'autenticazione e l'autorizzazione di utenti e computer.</p>
<p>- Richiede meno componenti hardware per server.</p></td>
<td style="border:1px solid black;"><p>- Nessuna separazione tra amministratori di IAS e amministratori di dominio.</p>
<p>- Nessuna separazione intrinseca tra problemi di prestazioni o guasti dei servizi installati.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Separatamente dai controller di dominio</p></td>
<td style="border:1px solid black;"><p>- Separazione tra amministratori di IAS e amministratori di dominio.</p>
<p>- II carico e il funzionamento di IAS non incidono sul servizio Active Directory.</p></td>
<td style="border:1px solid black;"><p>Richiede hardware aggiuntivo per server.</p></td>
</tr>
</tbody>
</table>
  
I controller di dominio Active Directory sono elementi essenziali dell'infrastruttura IT e devono essere gestiti con estrema cura. Molte organizzazioni aziendali adottano una politica che prevede di ridurre al minimo i programmi software o i servizi installati nei controller di dominio, per garantire la loro massima affidabilità del servizio.
  
In molte organizzazioni aziendali, i ruoli degli amministratori RADIUS sono separati da quelli degli amministratori di Active Directory. IAS è un componente facoltativo del sistema operativo Windows, pertanto non esiste alcuna separazione intrinseca tra le responsabilità dell'amministrazione di IAS e gli amministratori locali di Windows. Per questo motivo, una volta installato il server IAS nei controller di dominio, gli amministratori IAS diventano membri del gruppo di protezione Amministratori di dominio.
  
Questa soluzione richiede la versione di IAS inclusa in Windows Server 2003. È necessario, pertanto, aggiornare i controller di dominio a Windows Server 2003 (se questa operazione non è stata già eseguita). Inoltre, prima di eseguire l'aggiornamento dei controller di dominio Windows 2000 Server a Windows Server 2003, è opportuno considerare i requisiti riportati di seguito.
  
**Tabella 5.6. Requisiti per i controller di dominio Windows Server 2003**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Fattore da valutare</p></th>
<th><p>Requisito</p></th>
<th><p>Commento</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>I controller di dominio Windows Server 2003 richiedono la firma delle comunicazioni basate su un canale protetto o la firma e la crittografia di Server Message Block (SMB) per impostazione predefinita. Questo requisito può causare conflitti con alcune versioni precedenti di client basati su Windows.</p></td>
<td style="border:1px solid black;"><p>Aggiornare tutti i computer client nel proprio ambiente almeno al sistema operativo Microsoft Windows® 95 con il client Active Directory oppure al sistema operativo Windows NT 4.0 con Service Pack 4 (SP4) o versione successiva.</p></td>
<td style="border:1px solid black;"><p>Consultare la Guida in linea e supporto tecnico per <em>Windows</em> <em>Server</em> <em>2003</em> per ulteriori informazioni indicate nella sezione &quot;Ulteriori informazioni&quot; alla fine di questo capitolo.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>I controller di dominio Windows Server 2003 richiedono la firma e la crittografia di un canale protetto per impostazione predefinita. Questo requisito può incidere sulle relazioni di trust con i domini che includono server Windows NT 4.0 senza SP4.</p></td>
<td style="border:1px solid black;"><p>Aggiornare tutti i controller di dominio a Windows NT Server 4.0 con SP4 o versione successiva.</p></td>
<td style="border:1px solid black;"><p>Consultare la Guida in linea e supporto tecnico per <em>Windows Server</em> <em>2003</em> per ulteriori informazioni indicate nella sezione &quot;Ulteriori informazioni&quot; alla fine di questo capitolo.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>I controller di dominio Windows Server 2003 richiedono, prima dell'installazione, la preparazione dell'insieme di strutture Active Directory e del dominio.</p></td>
<td style="border:1px solid black;"><p>Preparare il nuovo insieme di strutture utilizzando l'utilità ADPrep prima di eseguire l'aggiornamento dei controller di dominio nell'ambiente a Windows Server 2003.</p></td>
<td style="border:1px solid black;"><p>Ciò non incide sul set di attributi parziali e pertanto non causa una ricostituzione del server di catalogo globale.</p></td>
</tr>
</tbody>
</table>
  
Questa soluzione è stata ideata per consentire l'installazione di IAS e Active Directory sullo stesso hardware dei controller di dominio, se lo si desidera. La soluzione è stata collaudata con IAS separato dai controller di dominio Windows Server 2003 in sedi hub e installato insieme con Windows Server 2003 nei controller di dominio di filiali.
  
#### Stima del carico dei server RADIUS
  
IAS funziona bene anche su server con prestazioni modeste e può essere scalato verticalmente mediante hardware aggiuntivo o orizzontalmente ricorrendo ai gruppi di server RADIUS. Tuttavia, è preferibile stimare in anticipo il carico che i client WLAN causeranno sull'hardware dei server IAS, così da evitare alle risorse dei server limitazioni che potrebbero incidere sulla disponibilità del servizio.
  
Una progettazione ottimale dovrebbe includere un numero minimo di server necessari per garantire la capacità di recupero dagli errori, pur lasciando spazio per una futura crescita. Ciò è particolarmente importante quando si sceglie di dimensionare l'hardware dei server per l'utilizzo in un modello di bilanciamento del carico basato su punti di accesso senza fili. In seguito allo spostamento del bilanciamento del carico basato su punti di accesso senza fili a un bilanciamento del carico basato su server proxy RADIUS, il numero di server richiesto può passare da due a cinque (supponendo che i server RADIUS esistenti abbiano raggiunto la capacità massima).
  
Le considerazioni sul carico dei server IAS includono quanto segue:
  
-   Il numero di utenti e dispositivi che necessitano di autenticazione e accounting.
  
-   Le opzioni di autenticazione, ad esempio tipo EAP e frequenza di riautenticazione.
  
-   Le opzioni RADIUS, ad esempio la registrazione dell'attività e l'analisi software IAS.
  
Il numero di utenti e dispositivi che necessitano dell'accesso alla rete WLAN è indispensabile per la stima del carico dei server IAS. Alcune organizzazioni limitano l'utilizzo della rete WLAN a un ristretto gruppo di utenti quali i dirigenti, mentre altre organizzazioni scelgono di offrire l'accesso WLAN a tutti gli utenti. A prescindere dalla strategia scelta dall'organizzazione, è necessario prevedere lo scenario peggiore, nel quale tutti gli utenti e i dispositivi in grado di accedere alla rete WLAN richiedono l'autenticazione e l'autorizzazione nell'arco di un breve periodo di tempo. Così facendo si garantisce che i server IAS saranno dimensionati in modo da gestire periodi di stress elevato, ad esempio gli orari di punta del lavoro e il periodo immediatamente successivo a un'interruzione cospicua della rete.
  
Inoltre, le opzioni di autenticazione hanno un notevole effetto sul carico dei server IAS. I protocolli basati su certificati, ad esempio EAP, eseguono in occasione dell'accesso iniziale un'operazione con chiave pubblica che sfrutta intensamente le risorse della CPU, ma poi, per tutti i successivi accessi, utilizzano una strategia basata su credenziali memorizzate nella cache detta Riconnessione rapida, fino alla scadenza della cache (otto ore, per impostazione predefinita). La riautenticazione completa si verifica sempre quando i client senza fili passano a punti di accesso che si riautenticano con un server IAS diverso da quello precedentemente utilizzato (ad esempio, quando il client viene spostato all'interno di un edificio). Questa riautenticazione mobile avviene solo una volta tra client e server IAS ed è invisibile all'utente finale qualora sia in uso il protocollo EAP-TLS.
  
Inoltre, è possibile adottare il metodo di aggiornamento delle chiavi di crittografia delle sessioni WEP 802.11 che consiste nell'imporre ai client senza fili di riautenticarsi con i server RADIUS. Alcuni modelli di punto di accesso senza fili includono funzionalità con cui eseguire l'aggiornamento temporizzato delle chiavi di sessione WEP senza dover imporre ai client l'esecuzione periodica della riautenticazione con il server RADIUS. Questo tipo di funzionalità è specifico per il fornitore. Lo standard WPA (WiFi Protected Access) include funzionalità di crittografia e gestione delle chiavi avanzate che possono ridurre la necessità di una riautenticazione forzata per aggiornare le chiavi di sessione.
  
Pertanto, nel creare un modello per un determinato numero di autenticazioni che ogni server IAS dovrà gestire, è opportuno considerare i vari tipi di autenticazione indicati nella tabella riportata di seguito.
  
**Tabella 5.7: Opzioni di autenticazione EAP-TLS**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tipo di autenticazione</p></th>
<th><p>Commenti</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazione iniziale del computer</p></td>
<td style="border:1px solid black;"><p>Il client esegue un'autenticazione completa con IAS.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Autenticazione iniziale dell'utente</p></td>
<td style="border:1px solid black;"><p>Il client esegue un'autenticazione completa con IAS.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Riautenticazione dell'utente quando passa da un punto di accesso senza fili a un altro</p></td>
<td style="border:1px solid black;"><p>Il client esegue un'autenticazione completa con ogni server IAS, quindi utilizza la funzione Riconnessione rapida per le ulteriori autenticazioni.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Riautenticazione del dispositivo quando passa da un punto di accesso senza fili a un altro</p></td>
<td style="border:1px solid black;"><p>Il client esegue un'autenticazione completa con ogni server IAS, quindi utilizza la funzione Riconnessione rapida per le ulteriori autenticazioni.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Riautenticazione temporizzata del computer</p></td>
<td style="border:1px solid black;"><p>Il client utilizza un'autenticazione memorizzata nella cache con IAS.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Riautenticazione temporizzata dell'utente</p></td>
<td style="border:1px solid black;"><p>Il client utilizza un'autenticazione memorizzata nella cache con IAS.</p></td>
</tr>
</tbody>
</table>
  
La stima del numero di autenticazioni che IAS è in grado di gestire deve essere espressa in autenticazioni al secondo. È stato dimostrato che IAS è in grado di raggiungere le seguenti prestazioni con un computer su cui viene eseguito Windows Server 2003 e Active Directory installato su un altro computer Intel Pentium 4 a 2 GHz.
  
**Importante:** le informazioni contenute nella tabella che segue vengono fornite senza alcuna garanzia e devono essere intese come mere linee guida ai fini della pianificazione della capacità e non ai fini di un confronto fra prestazioni.
  
**Tabella 5.8. Autenticazioni al secondo**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Tipo di autenticazione</p></th>
<th><p>Autenticazioni al secondo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Nuove autenticazioni EAP-TLS</p></td>
<td style="border:1px solid black;"><p>36</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Nuove autenticazioni EAP con scheda di supporto per la ripartizione del carico</p></td>
<td style="border:1px solid black;"><p>50</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazioni con Riconnessione rapida</p></td>
<td style="border:1px solid black;"><p>166</p></td>
</tr>
</tbody>
</table>
  
IAS può essere configurato in modo che generi registri di testo basati su disco contenenti quantità variabili di informazioni sulle richieste RADIUS. È preferibile pianificare l'utilizzo di un disco ad alte prestazioni per l'archiviazione di registri RADIUS a causa del sovraccarico che le attività di registrazione RADIUS comportano per i server RADIUS. I sottosistemi disco a bassa velocità possono ritardare le risposte RADIUS IAS ai punti di accesso senza fili, con conseguenti timeout dei protocolli e inutili operazioni di failover dei punti di accesso senza fili ai server RADIUS secondari.
  
Inoltre, se si attivano le funzionalità di analisi software di Windows Server 2003, verrà imposto un ulteriore carico sui server IAS. Occasionalmente, tuttavia, può essere necessario attivare le funzionalità di analisi per risolvere i problemi di accesso alla rete. Per questi motivi, è necessario garantire ai server IAS la capacità di funzionare e gestire il carico di produzione anche quando le funzionalità di analisi sono attive per brevi periodi di tempo.
  
#### Stima dei requisiti hardware dei server
  
È necessario scegliere l'hardware dei server su cui eseguire IAS basandosi sull'<http://www.microsoft.com/whdc/hcl/default.mspx>. Scegliendo i componenti hardware dei server da questo elenco, è possibile evitare i problemi di affidabilità e compatibilità che potrebbero sorgere con hardware non collaudato e driver di periferica malfunzionanti.
  
Verificare che i server IAS soddisfino i requisiti di hardware consigliati per Windows Server 2003 e tenere conto degli altri servizi che vengono eseguiti sul sistema, come Active Directory. È opportuno utilizzare componenti hardware del server IAS in grado di sostenere il doppio del previsto carico di autenticazione per server, così da garantire la disponibilità di sufficienti risorse server con cui affrontare le situazioni di failover tra server e le condizioni insolite della rete.
  
Tramite l'uso del layout di server della Woodgrove Bank, un'azienda fittizia, la figura seguente mostra un esempio di progettazione di un server RADIUS basato su IAS in cui vengono indicati la posizione e il numero di server IAS richiesti dalla distribuzione degli utenti e dal carico previsto. Solo un sottoinsieme di questa infrastruttura, tuttavia, è stato collaudato per la presente guida (utilizzando la sede centrale di Londra e le filiali di Johannesburg).
  
**Nota:** la Woodgrove Bank è un'azienda fittizia rappresentativa di organizzazioni di medie e grandi dimensioni. L'architettura e le caratteristiche della sua rete sono state utilizzate come base per diverse decisioni di progettazione nell'implementazione di questa soluzione.
  
[![](images/Dd536246.05fig5-6(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536246.05fig5-6_big(it-it,technet.10).gif)
  
**Figura 5.6 Distribuzione di utenti, punti di accesso senza fili e server IAS della Woodgrove Bank**
  
Questa soluzione è stata progettata con due server RADIUS che si trovano nella sede centrale al servizio di 6.742 utenti. Solo il 50 percento degli utenti può accedere alla rete senza fili, pertanto 3.371 utenti e i rispettivi 3.371 dispositivi eseguono l'autenticazione con i due server RADIUS mediante il protocollo EAP-TLS negli orari di massimo carico. Ogni server può gestire 3.371 autenticazioni in un periodo di picco di accessi di 30 minuti, che corrisponde all'incirca a due nuove autenticazioni EAP-TLS al secondo con capacità di quattro nuove autenticazioni al secondo nei periodi di failover tra server.
  
Il server è stato configurato per registrare le richieste di autenticazione e di accounting RADIUS in file di testo. Il server è un server RADIUS dedicato, mentre i servizi dei controller di dominio sono stati posizionati su altri server.  Inoltre, i componenti hardware del server RADIUS sono intenzionalmente sovradimensionati per poter far fronte ai requisiti futuri, ad esempio il controllo dell'accesso alla rete di tipo VPN, cablata e con connessione remota.
  
Nella tabella che segue sono descritti in dettaglio i componenti hardware del server RADIUS utilizzati durante le attività di test della soluzione.
  
**Tabella 5.9. Hardware dei server collaudato**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Risorsa</p></th>
<th><p>Configurazione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>CPU</p></td>
<td style="border:1px solid black;"><p>Pentium III da 850 MHz con doppia CPU</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>RAM</p></td>
<td style="border:1px solid black;"><p>512 MB</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Scheda di rete</p></td>
<td style="border:1px solid black;"><p>Due schede di rete abbinate per funzionalità di recupero dagli errori</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Disco rigido</p></td>
<td style="border:1px solid black;"><p>- Due dischi rigidi da 9 GB in configurazione RAID (volume C) per il sistema operativo<br />
- Due dischi rigidi da 18 GB in configurazione RAID 1 (volume D) per i file di registro e i dati di configurazione</p></td>
</tr>
</tbody>
</table>
<p> </p>

I requisiti hardware per i propri server IAS possono essere diversi e devono essere valutati sulla base delle variabili specifiche dell'organizzazione.

#### Determinazione dei requisiti software dei server

Occorre stabilire se per i server IAS del proprio ambiente, è necessario Windows Server 2003 Standard Edition o Enterprise Edition. Windows Server 2003 Standard Edition supporta solo 50 client RADIUS e due gruppi di routing server.

Questa soluzione è stata collaudata con Windows Server 2003 Enterprise Edition per server RADIUS di sedi centrali e con Windows Server 2003 Standard Edition per server RADIUS di filiali. La soluzione, tuttavia, funziona altrettanto bene con una versione che presenta le limitazioni indicate in precedenza.

Sono necessari altri componenti software per l'ambiente, a seconda degli standard dell'organizzazione, come i seguenti:

-   Agenti di backup.

-   Agenti di gestione, quali MOM o i componenti client Microsoft Systems Management Server (SMS).

-   Software antivirus.

-   Agenti per il rilevamento di intrusioni.

[](#mainsection)[Inizio pagina](#mainsection)

### Creazione di un piano di gestione

I server RADIUS basati su IAS richiedono relativamente poca manutenzione ordinaria per garantire la disponibilità continua del servizio e la protezione della rete. Tuttavia, è necessario determinare la strategia di gestione IAS all'inizio del progetto WLAN, così da addestrare il personale necessario per gestire l'infrastruttura RADIUS.

#### Gestione delle modifiche e della configurazione

La conoscenza dello stato dei server IAS e la sua conservazione sono essenziali per assicurare la disponibilità del servizio e la protezione della rete. IAS facilita nativamente le modifiche transazionali di vari elementi di configurazione dei server mediante il comando **netsh** e pertanto consente un semplice rollback qualora una modifica causi problemi imprevisti.

Il comando **netsh** consente di esportare e importare l'intera configurazione IAS (o parti di essa) in file di testo che è possibile utilizzare per replicare le impostazioni tra i server IAS. Questa funzionalità può velocizzare la distribuzione delle modifiche della configurazione in ambienti di grandi dimensioni.

Le attività che occorre svolgere per realizzare una gestione appropriata delle modifiche e della configurazione vengono indicate nel capitolo 12, "Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili".

#### Pianificazione in vista di un ripristino di emergenza

Per garantire un ripristino veloce del servizio RADIUS in situazioni di emergenza, è necessaria un'appropriata pianificazione da realizzare prima del verificarsi dell'evento. Gli script di installazione forniti con questa guida consentono di semplificare l'installazione e la configurazione del server IAS; è possibile, inoltre, automatizzare facilmente le operazioni richieste per ripristinare in tempi rapidi lo stato della configurazione IAS mediante gli script **netsh**. Per ulteriori informazioni sulle operazioni di ripristino dei servizi, consultare il capitolo 12, “Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili”.

#### Pianificazione delle autorizzazioni amministrative

IAS è un componente facoltativo del sistema operativo Windows Server 2003 e pertanto non richiede un modello di protezione amministrativa diverso da quello del server locale. La separazione dell'amministrazione di IAS da quella svolta dagli amministratori del server locale non è possibile se non mediante attività di sviluppo personalizzato, ad esempio la creazione di una pagina Web protetta che consenta di eseguire modifiche della configurazione di IAS mediante un account con privilegi minimi con autorizzazioni amministrative per il server locale.

È tuttavia importante pianificare i tipi di amministrazione necessari e i requisiti di accesso alle varie risorse IAS per ottenere un modello basato su privilegi minimi. Nella tabella seguente vengono forniti alcuni esempi di ruoli e attività correlati ai server IAS.

**Tabella 5.10. Descrizioni e attività dei ruoli IAS**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Ruolo del personale</p></th>
<th><p>Descrizione del ruolo</p></th>
<th><p>Attività</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratori IAS</p></td>
<td style="border:1px solid black;"><p>Ruolo necessario per eseguire le attività amministrative quotidiane di IAS, ad esempio il controllo del servizio IAS e della configurazione di IAS</p></td>
<td style="border:1px solid black;"><p>Avviare/arrestare/eseguire query/configurare il servizio IAS e apportare modifiche al database di configurazione di IAS.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Controllori protezione IAS</p></td>
<td style="border:1px solid black;"><p>Questo ruolo consente ai controllori della protezione senza autorizzazioni amministrative di accedere alle informazioni di protezione.</p></td>
<td style="border:1px solid black;"><p>Esaminare i file di registro di accounting e autenticazione RADIUS per individuare gli eventi di protezione.</p>
<p>Se i registri delle richieste di autenticazione RADIUS sono disattivati, i membri del gruppo Controllori protezione IAS potrebbero avere bisogno di esaminare e salvare le voci del Registro eventi di sistema relative agli eventi di protezione rilevanti per IAS. Ciò può richiedere autorizzazioni aggiuntive.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Operatori backup IAS</p></td>
<td style="border:1px solid black;"><p>Questo ruolo consente agli operatori di backup di eseguire backup regolari dei server IAS che includono lo stato della configurazione e i dati cronologici di IAS.</p></td>
<td style="border:1px solid black;"><p>Gestire i backup quotidiani/settimanali/mensili dei server IAS.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Personale del supporto tecnico WLAN</p></td>
<td style="border:1px solid black;"><p>Personale responsabile dell'assistenza agli utenti nella soluzione di problemi correlati all'accesso alla rete WLAN.</p></td>
<td style="border:1px solid black;"><p>Esaminare gli eventi IAS inclusi nel Registro eventi di sistema correlati all'autenticazione di utenti e dispositivi o visualizzare gli eventi man mano che vengono replicati in un altro sistema.</p></td>
</tr>
</tbody>
</table>
  
Nella tabella seguente sono descritte le autorizzazioni per le risorse che occorre avere per eseguire le varie attività sui server IAS.
  
**Tabella 5.11. Autorizzazioni necessarie per le attività sui server IAS**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Operazione</p></th>
<th><p>Appartenenza al gruppo</p></th>
<th><p>Autorizzazione o diritti necessari</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Arrestare/avviare/eseguire query/configurare il servizio IAS</p></td>
<td style="border:1px solid black;"><p>Gruppo globale di dominio Amministratori IAS, che è un membro del gruppo Amministratori locale sui server IAS.</p></td>
<td style="border:1px solid black;"><p>È possibile modificare le autorizzazioni del servizio  in Windows Server 2003 mediante il comando SC. Consultare il personale dell'assistenza Microsoft prima di modificare le autorizzazioni predefinite per i componenti del sistema operativo.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Modificare la configurazione di IAS</p></td>
<td style="border:1px solid black;"><p>Gruppo globale di dominio Amministratori IAS, che è un membro del gruppo Amministratori locale sui server IAS.</p></td>
<td style="border:1px solid black;"><p>Sono necessarie le autorizzazioni per i file di database IAS che si trovano nella directory C:\WINDOWS\system32\ias, nonché per le varie chiavi del Registro di sistema incluse in <strong>HKLM\System\CurrentControlSet\Services</strong>.</p>
<p>Per impostazione predefinita, tali autorizzazioni vengono accordate ai membri del gruppo di protezione Amministratori locale/incorporato.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Accedere ai registri delle richieste RADIUS che si trovano nei server IAS</p></td>
<td style="border:1px solid black;"><p>Gruppo globale di dominio Controllori protezione IAS.</p></td>
<td style="border:1px solid black;"><p>I membri del gruppo Controllori protezione IAS devono essere in grado di leggere ed eliminare i file di registro delle richieste RADIUS che si trovano nella directory D:\IASLogs. Le linee guida per l'implementazione incluse nella presente soluzione accordano l'autorizzazione Modifica del file system NTFS al gruppo di protezione Controllori protezione IAS per questa directory e creano una condivisione chiamata IASLogs con l'autorizzazione di modifica accordata al gruppo di protezione Controllori protezione IAS.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Leggere e salvare gli eventi di protezione IAS inclusi nel Registro eventi di sistema</p></td>
<td style="border:1px solid black;"><p>Amministratori locali<br />
-o-<br />
Operatori di backup sui server IAS.</p></td>
<td style="border:1px solid black;"><p>Questa soluzione include linee guida con cui attivare la registrazione dell'autenticazione RADIUS in file di testo su disco. Pertanto i membri del gruppo di protezione Controllori protezione IAS in genere non hanno bisogno di accedere al Registro eventi di sistema per esaminare gli eventi di protezione correlati all'autenticazione RADIUS.<br />
Se però si decide di disattivare la registrazione dell'autenticazione RADIUS, i membri del gruppo Controllori protezione IAS devono poter leggere e salvare gli eventi IAS inclusi nel Registro eventi di sistema. Per poter archiviare un Registro eventi di sistema, è necessario appartenere al gruppo Amministratori o Operatori backup.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Gestire i backup quotidiani/settimanali/mensili dei server IAS.</p></td>
<td style="border:1px solid black;"><p>Operatori di backup sui server IAS.</p></td>
<td style="border:1px solid black;"><p>Il backup dei server IAS include lo stato della configurazione e i dati cronologici di IAS, ad esempio i registri delle richieste RADIUS. L'appartenenza al gruppo di protezione Operatori backup consente l'accesso ai file di database IAS situati nella directory %systemroot%\system32\ias, alle varie chiavi del Registro di sistema in <strong>HKLM\System\CurrentControlSet\Services</strong>, ai file di registro delle richieste RADIUS in D:\IASLogs e ai file di testo di configurazione di IAS <strong>NETSH</strong> che si trovano in D:\IASConfig.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Esaminare gli eventi di autenticazione IAS inclusi nel Registro eventi di sistema per risolvere i problemi.</p></td>
<td style="border:1px solid black;"><p>Appartenenza a un gruppo con autorizzazioni alla lettura del Registro eventi di sistema.</p></td>
<td style="border:1px solid black;"><p>Al personale esperto di risoluzione dei problemi deve essere accordata l'autorizzazione alla lettura del Registro eventi di sistema di Windows Server 2003, per visualizzare e interpretare gli eventi di rifiuto dell'autenticazione IAS.</p></td>
</tr>
</tbody>
</table>
  
#### Monitoraggio e controllo della protezione
  
IAS è un componente dell'infrastruttura di protezione del quale occorre eseguire il monitoraggio in maniera preventiva. Alcune ricerche nell'ambito della protezione hanno mostrato che gli attacchi riusciti sono in genere preceduti da svariati attacchi non riusciti. Il monitoraggio preventivo della protezione dei server IAS e dei relativi registri finalizzato all'individuazione di elementi sospetti si dimostra necessario per sapere quando la rete è sotto attacco.
  
Nella tabella seguente vengono elencati i possibili pericoli da monitorare per l'infrastruttura dei server.
  
**Tabella 5.12. Pericoli per l'infrastruttura dei server IAS**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Pericolo/Vulnerabilità</p></th>
<th><p>Sintomo</p></th>
<th><p>Strumento di monitoraggio</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Tentativo di autenticazione mediante credenziali rubate (ad esempio, quelle trovate su un computer portatile perso o rubato)</p></td>
<td style="border:1px solid black;"><p>Eventi di autenticazione riuscita/rifiutata (origine: IAS, ID 1 e 2) nel Registro eventi di sistema o nei registri delle richieste di autenticazione RADIUS indicanti l'utilizzo di certificati revocati.</p></td>
<td style="border:1px solid black;"><p>- MOM con uno script personalizzato mirato all'analisi delle voci del registro eventi alla ricerca di indicazioni sull'utilizzo di certificati revocati.<br />
- Script di analisi di file o strumenti di SQL Server che cercano l'utilizzo di certificati revocati.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Tentativo di attacco di tipo 'man-in-the-middle' eseguito mediante un punto di accesso senza fili manomesso</p></td>
<td style="border:1px solid black;"><p>I contatori del monitor di sistema sui server IAS presentano un numero eccessivo di istanze di: autenticatori errati (attributo Bad Message Authenticator) o richieste non valide (ricevute da client o server RADIUS ignoti).</p></td>
<td style="border:1px solid black;"><p>MOM con uno script personalizzato per rilevare le contromosse del monitor di sistema e creare un avviso.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tentativi di attacco di tipo DoS o overflow del buffer contro il servizio dei server IAS</p></td>
<td style="border:1px solid black;"><p>I contatori del monitor di sistema sui server IAS presentano un numero eccessivo di istanze di: pacchetti errati (pacchetti contenenti dati errati), tipo ignoto (ricezione di pacchetti non RADIUS) o pacchetti ignorati (diversi da quelli MAC errati/errati/ignoti).</p></td>
<td style="border:1px solid black;"><p>MOM con uno script personalizzato per rilevare le contromosse del monitor di sistema e creare un avviso.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Tentativo di autenticazione non autorizzato</p></td>
<td style="border:1px solid black;"><p>Eventi ripetuti di autenticazione non riuscita (origine: IAS, ID 2) nel Registro eventi di sistema.</p></td>
<td style="border:1px solid black;"><p>- MOM con uno script personalizzato mirato all'analisi delle voci del registro eventi per individuarvi un eventuale numero eccessivo di autenticazioni rifiutate.<br />
- Script di analisi di file o strumenti di SQL Server per identificare un numero eccessivo di autenticazioni rifiutate.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazione riuscita con credenziali rubate</p></td>
<td style="border:1px solid black;"><p>I registri di accounting RADIUS indicano un'attività sospetta della rete.</p></td>
<td style="border:1px solid black;"><p>- Microsoft Access per importare registri basati su file ed eseguire query personalizzate.<br />
- Creazione di report per identificare informazioni su accessi inusuali alla rete memorizzate in un database SQL Server.</p></td>
</tr>
</tbody>
</table>
<p> </p>

Oltre al monitoraggio di base della protezione, è consigliabile eseguire il controllo preventivo della protezione dei server IAS e utilizzare i componenti tecnologici correlati, onde definire e attenuare le vulnerabilità individuate nell'infrastruttura di rete.

Nella tabella che segue sono elencati i potenziali pericoli per l'infrastruttura di server IAS e i relativi componenti tecnologici che è possibile utilizzare per eseguire un controllo preventivo.

**Tabella 5.13. Pericoli per l'infrastruttura dei server IAS da controllare preventivamente**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Pericolo/Vulnerabilità</p></th>
<th><p>Sintomo</p></th>
<th><p>Strumento di controllo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Autorizzazione eccessiva per i dati cronologici e di configurazione di IAS.</p></td>
<td style="border:1px solid black;"><p>Membro non autorizzato dei gruppi Amministratori IAS e Controllori protezione IAS o del gruppo Amministratori locale.</p></td>
<td style="border:1px solid black;"><p>Strumenti di controllo di Active Directory e dei gruppi di protezione locale, ad esempio DumpSec di SomarSoft.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Tentativi di nascondere l'autenticazione non autorizzata.</p></td>
<td style="border:1px solid black;"><p>Il Registro eventi di sistema è inaspettatamente vuoto.</p></td>
<td style="border:1px solid black;"><p>- Controllo del Registro eventi di Windows mediante strumenti come EventcombMT, incluso in <em>Windows Server</em> <em>2003 Resource Kit</em>.</p>
<p>- Strumento di monitoraggio del registro eventi e di segnalazione di avvisi, ad esempio MOM.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Modifica non autorizzata dei registri di accounting e autenticazione RADIUS</p></td>
<td style="border:1px solid black;"><p>ID utente inatteso con accesso in scrittura nei registri di controllo delle cartelle.</p></td>
<td style="border:1px solid black;"><p>Strumento di controllo e monitoraggio dei file di Windows, ad esempio MOM. Per rilevare una modifica di file non autorizzata, è necessario attivare il controllo dei file.</p></td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo modulo è stata illustrata la progettazione di un'infrastruttura RADIUS per la protezione di una rete senza fili basata sullo standard 802.1X. La progettazione dell'infrastruttura RADIUS descritta nel presente capitolo è abbastanza flessibile da consentirne l'estensione per numerosi requisiti futuri. È possibile anche utilizzare la progettazione dell'infrastruttura di altri tipi di gestione dell'accesso alla rete.
  
La progettazione descritta nel presente capitolo verrà utilizzata nei capitoli successivi per implementare l'infrastruttura RADIUS. Nel capitolo successivo, viene illustrata la progettazione RADIUS generica che consente di descrivere le impostazioni 802.1X e l'infrastruttura WLAN richieste per implementare i componenti rimanenti dell’infrastruttura di protezione della rete WLAN.
  
#### Ulteriori informazioni
  
Per ulteriori informazioni su IAS, vedere le risorse seguenti:
  
-   Il [sito Web del supporto tecnico di Windows Server 2003 Support Center](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/default.mspx), disponibile all'indirizzo http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/  
    entserver/default.mspx.
  
-   La documentazione del prodotto include una panoramica delle funzionalità di IAS, istruzioni essenziali per la configurazione e procedure consigliate per la distribuzione.
  
-   La [*documentazione tecnica su Windows Server 2003*](http://www.microsoft.com/windows/reskits/default.asp) e il [*Microsoft Windows Server 2003 Deployment Kit*](http://www.microsoft.com/windows/reskits/default.asp) sono disponibili all'indirizzo http://www.microsoft.com/windows/reskits/default.asp (in inglese).
  
-   Il capitolo “[IAS Technical Reference](http://technet.microsoft.com/en-us/library/cc759100.aspx)“ della documentazione tecnica su *Microsoft Windows Server* *2003* è disponibile all'indirizzo http://technet.microsoft.com/en-us/library/cc759100.aspx
  
-   Nel capitolo IAS Technical Reference sono incluse informazioni tecniche su IAS più dettagliate di quelle contenute nella documentazione del prodotto, che possono essere utilizzate come riferimento per approfondire argomenti specifici.
  
-   Il capitolo “Deploying IAS” della guida *Deploying Network Services* (in inglese) incluso nel [*Microsoft Windows Server 2003 Deployment Kit*](http://www.microsoft.com/windowsserver2003/techinfo/reskit/deploykit.mspx) è disponibile all'indirizzo http://www.microsoft.com/windowsserver2003/techinfo/reskit/deploykit.mspx (in inglese).
  
-   Questo capitolo del Deployment Kit contiene una guida alla distribuzione per l'utilizzo del servizio IAS in vari scenari che non rientrano nell'ambito della presente guida alla protezione delle reti senza fili, ma che influiscono sulle scelte di progettazione.
  
Per ulteriori informazioni sulle tecnologie WLAN 802.1X, vedere:
  
-   Il white paper “[Windows XP Wireless Deployment Technology and Component Overview](http://technet.microsoft.com/en-us/library/bb457015.aspx)” (in inglese) su Microsoft TechNet all'indirizzo http://technet.microsoft.com/en-us/library/bb457015.aspx
  
[](#mainsection)[Inizio pagina](#mainsection)
