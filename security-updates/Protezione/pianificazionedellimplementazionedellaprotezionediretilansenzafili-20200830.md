---
TOCTitle: 'Pianificazione dell''implementazione della protezione di reti LAN senza fili'
Title: 'Pianificazione dell''implementazione della protezione di reti LAN senza fili'
ms:assetid: 'e5223e67-b466-411e-b866-8655901fdf74'
ms:contentKeyID: 20200830
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536231(v=TechNet.10)'
---

Protezione delle reti LAN senza fili con PEAP e password
========================================================

### Capitolo 2: Pianificazione dell'implementazione della protezione di reti LAN senza fili

Aggiornato: 3 aprile 2004

##### In questa pagina

[](#ejaa)[Cenni preliminari](#ejaa)
[](#eiaa)[Prima di iniziare](#eiaa)
[](#ehaa)[Funzionamento della protezione di reti LAN senza fili](#ehaa)
[](#egaa)[Profilo dell'organizzazione di destinazione](#egaa)
[](#efaa)[Criteri di progettazione](#efaa)
[](#eeaa)[Architettura WLAN](#eeaa)
[](#edaa)[Scalabilità per organizzazioni di maggiori dimensioni](#edaa)
[](#ecaa)[Variazioni nell'architettura della soluzione](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Riferimenti](#eaaa)

### Cenni preliminari

In questo capitolo viene descritta la progettazione complessiva della soluzione per reti WLAN (Wireless Local Area Network) protette. Lo scopo è quello di offrire una descrizione approfondita relativa alla progettazione della soluzione, illustrando i motivi delle scelte effettuate. Vengono inoltre riportate le informazioni necessarie per adattare la progettazione alle esigenze specifiche della propria organizzazione.

Il capitolo inizia con una descrizione della modalità di funzionamento dell'autenticazione 802.1X e del protocollo PEAP (Protected Extensible Authentication Protocol) per la protezione dell'accesso alla rete, seguita dalla descrizione dell'organizzazione di destinazione della soluzione e dai relativi requisiti fondamentali.

Nella parte centrale del capitolo viene descritta la progettazione della soluzione per reti WLAN, che include: la struttura della rete; il posizionamento del server IAS (Internet Authentication Service, Servizio di autenticazione Internet); la scelta di hardware e software; la procedura per ottenere i certificati; la configurazione dei client. Viene inoltre illustrato come eseguire la migrazione da una rete WLAN non protetta all'autenticazione 802.1X e al protocollo PEAP.

Nelle sezioni finali del capitolo vengono presentate possibili variazioni alla progettazione di base della soluzione. La più importante di tali variazioni riguarda la scalabilità della soluzione per l'utilizzo in organizzazioni di maggiori dimensioni, che viene illustrata in dettaglio. Tra le altre opzioni di progettazione indicate rientrano:

-   Riutilizzo dell'infrastruttura IAS per la protezione di reti LAN cablate

-   Utilizzo di IAS per l'autenticazione dell'accesso remoto

-   Distribuzione di reti WLAN in ambienti SOHO

[](#mainsection)[Inizio pagina](#mainsection)

### Prima di iniziare

Durante la pianificazione dell'implementazione di reti WLAN protette è necessario verificare che nell'organizzazione siano disponibili le competenze appropriate e che le decisioni relative alla distribuzione vengano affidate a persone qualificate.

Per trarre il massimo vantaggio da questo capitolo, è consigliabile approfondire i seguenti argomenti:

-   Concetti relativi alla rete, in particolare a reti LAN senza fili

-   Microsoft® Windows® 2000 o Windows Server™ 2003

-   Concetti relativi al servizio Microsoft Active Directory®, inclusi i domini e gli insiemi di strutture di Active Directory, gli strumenti di gestione, l'utilizzo dei criteri di gruppo e la manipolazione di utenti, di gruppi e di altri oggetti di Active Directory

-   Concetti relativi a Servizi certificati e all'infrastruttura a chiave pubblica (PKI)

-   Concetti relativi alla protezione generale, quali l'autenticazione, l'autorizzazione e la crittografia

-   Funzionalità di protezione di Windows, quali utenti, gruppi, controllo ed elenchi di controllo di accesso (ACL)

-   Applicazione delle impostazioni di protezione mediante i criteri di gruppo.

    **Nota:** sebbene sia possibile implementare questa soluzione senza una conoscenza tecnica approfondita, è consigliabile acquisire una certificazione Microsoft Certified Systems Engineer (MSCE) o una conoscenza e un'esperienza equivalenti.

[](#mainsection)[Inizio pagina](#mainsection)

### Funzionamento della protezione di reti LAN senza fili

Nel documento introduttivo "Scelta di una strategia per la protezione di reti LAN senza fili" sono stati descritti in dettaglio diversi metodi per la protezione di reti WLAN. In particolare è stato illustrato l'utilizzo dell'autenticazione avanzata di reti WLAN tramite lo standard 802.1X e la crittografia del traffico di rete basata sul WEP (Wired Equivalent Privacy) dinamico o su WPA (WiFi Protected Access). I punti principali di tale descrizione sono i seguenti:

-   Lo schema di protezione originale per reti WLAN basate sulla tecnologia 802.11, noto come WEP (Wired Equivalent Privacy), presenta gravi lacune che consentono a un pirata informatico di decifrare la chiave di rete e quindi di violare la rete. Questo schema è conosciuto come "WEP statico", in quanto utilizza una chiave fissa di accesso alla rete e di crittografia condivisa tra tutti i membri della rete WLAN.

-   L'utilizzo dell'autenticazione IEEE 802.1X garantisce un meccanismo di controllo dell'accesso avanzato per la rete WLAN. Tale meccanismo deve essere combinato con un metodo EAP (Extensible Authentication Protocol) protetto. La scelta del metodo EAP determina il tipo di credenziali che è possibile utilizzare per l'autenticazione di utenti e computer nella rete WLAN.

-   Microsoft supporta e consiglia l'utilizzo di PEAP con MS-CHAP v2 per l'autenticazione tramite password e EAP-TLS per l'autenticazione con certificato.

-   PEAP consente di proteggere un altro metodo EAP, ad esempio MS-CHAP v2, all'interno di un canale protetto. L'utilizzo di PEAP è indispensabile per impedire attacchi ai metodi EAP basati su password.

-   È possibile garantire la protezione avanzata dei dati del traffico di rete WLAN tramite WEP dinamico o WPA. Le chiavi di crittografia principali per la protezione dei dati vengono generate durante il processo di autenticazione 802.1X, anche se il WEP dinamico e WPA utilizzano in modo diverso questo chiavi.

-   La differenza tra WEP statico e WEP dinamico è fondamentale. Il WEP dinamico utilizza gli stessi algoritmi di crittografia del WEP statico ma aggiorna continuamente le chiavi di crittografia, impedendo pertanto gli attacchi noti al WEP statico. Il WEP dinamico include soltanto il meccanismo di protezione dei dati di rete, in quanto l'autenticazione di rete viene gestita separatamente dalla tecnologia 802.1X.

#### Funzionamento dell'autenticazione 802.1X con PEAP e password

Per l'autenticazione di reti WLAN basata su password, Microsoft supporta l'utilizzo di PEAP con MS-CHAP v2. Nella figura 2.2 è illustrato il funzionamento dell'autenticazione 802.1X con PEAP e MS-CHAP v2.

[![](images/Dd536231.PEAP_201(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536231.peap_201_big(it-it,technet.10).gif)

**Figura 2.1 Autenticazione 802.1X e PEAP per la rete LAN senza fili**

Nella figura sono illustrati i seguenti quattro componenti principali:

-   **Client senza fili:** si tratta di un computer o di un dispositivo in cui viene eseguita un'applicazione che richiede l'accesso alle risorse di rete. Il proprietario delle credenziali utilizzate per l'autenticazione del client nella rete può essere un utente o un computer. Il client deve disporre di una scheda di rete WLAN in grado di supportare l'autenticazione 802.1X e il WEP dinamico o la crittografia WPA. In vari documenti relativi agli standard di rete si fa riferimento al client con il termine "stazione" (STA).

    Prima che al client venga consentito l'accesso alla rete WLAN, il client deve concordare fuori banda un insieme di credenziali con il servizio di autenticazione (il server RADIUS e la directory). In questo caso, gli account di dominio dell'utente e del computer vengono creati prima della connessione alla rete WLAN. Il client conosce la password e il controller di dominio (la directory) è in grado di verificarla. È necessario inoltre preconfigurare il client con le impostazioni corrette della rete WLAN, inclusi il nome della rete WLAN e il metodo di autenticazione da utilizzare.

    **Nota:** a rigore, è necessario concordare fuori banda un unico insieme di credenziali, ovvero quelle dell'utente o quelle del computer. Ad esempio, è possibile connettersi alla rete WLAN utilizzando le credenziali utente e quindi aggiungere il computer al dominio. Tuttavia questa soluzione presuppone che gli account dell'utente e del computer siano già disponibili prima dell'accesso alla rete WLAN.

-   **Punto di accesso senza fili:** il punto di accesso senza fili è responsabile del controllo dell'accesso alla rete WLAN e del bridging di una connessione client alla rete LAN interna. Deve supportare l'autenticazione 802.1X e il WEP dinamico o la crittografia WPA. In termini di standard di rete, il punto di accesso svolge il ruolo del servizio NAS (Network Access Service).

    Il punto di accesso senza fili e il server RADIUS dispongono inoltre di un segreto condiviso per identificarsi reciprocamente in modo sicuro.

-   **Server RADIUS e directory:** il server RADIUS utilizza la directory per verificare le credenziali dei client WLAN. Prende decisioni sulle autorizzazioni in base a un criterio di accesso alla rete. Inoltre consente di raccogliere le informazioni di accounting e di controllo sull'accesso client alla rete. Nella terminologia degli standard di rete si fa riferimento a questo server con l'espressione "servizio di autenticazione" (AS, Authentication Service).

-   **Rete interna:** rete protetta necessaria per l'applicazione client senza fili al fine di ottenere l'accesso.

Nella procedura seguente vengono descritte le modalità con cui il client effettua una richiesta, ottenendo l'accesso alla rete WLAN e quindi alla rete interna. Il numero dei passaggi corrisponde ai numeri indicati nella figura 2.1.

1.  Se il computer client è compreso nell'intervallo del punto di accesso senza fili, tenta di connettersi alla rete WLAN attiva su tale punto di accesso e individuata in base al relativo identificatore del set di servizi (SSID). Il SSID rappresenta il nome della rete WLAN e viene utilizzato dal client per identificare le impostazioni corrette e il tipo di credenziali appropriato per questa rete.

2.  Il punto di accesso senza fili viene configurato in modo da consentire solo connessioni protette con l'autenticazione 802.1X. Quando il client tenta di connettersi al punto di accesso senza fili, quest'ultimo invia una richiesta al client, quindi imposta un canale con restrizioni che consente al client di comunicare solo con il server RADIUS, bloccando l'accesso al resto della rete. Il server RADIUS accetterà una connessione solo da un punto di accesso senza fili attendibile, ovvero configurato come client RADIUS nel server IAS e in grado di fornire il segreto condiviso per tale client RADIUS.

    Il client tenta di eseguire l'autenticazione nel server RADIUS tramite il canale con restrizioni utilizzando l'autenticazione 802.1X. Durante la negoziazione PEAP, il client stabilisce una sessione TLS (Transport Layer Security) con il server RADIUS. L'utilizzo di una sessione TLS durante la negoziazione PEAP è finalizzato a diversi scopi:

    -   Consente al client di eseguire l'autenticazione del server RADIUS; pertanto il client stabilirà la sessione esclusivamente con un server in possesso di un certificato ritenuto attendibile dal client stesso.

    -   Protegge il protocollo di autenticazione MS-CHAP v2 dall'analisi del pacchetto.

    -   La negoziazione della sessione TLS genera una chiave che può essere utilizzata dal client e dal server RADIUS per stabilire chiavi principali comuni, le quali consentono di ricavare le chiavi utilizzate per la crittografia del traffico di rete WLAN.

    Il client, protetto all'interno del canale PEAP, esegue l'autenticazione nel server RADIUS tramite il protocollo MS-CHAP v2 EAP. Durante questo scambio, il traffico all'interno del tunnel TLS è visibile solo al client e al server RADIUS e non viene mai esposto al punto di accesso senza fili.

3.  Il server RADIUS controlla le credenziali del client in base alla directory. Se il client viene autenticato, il server RADIUS raccoglie le informazioni che gli consentono di decidere se autorizzare o meno il client a utilizzare la rete WLAN. Il server utilizza le informazioni della directory (ad esempio, l'appartenenza ai gruppi) e le limitazioni definite nel relativo criterio di accesso (ad esempio, l'orario in cui è consentito l'accesso alla rete WLAN) per consentire o negare l'accesso al client. Il server RADIUS inoltra tale decisione al punto di accesso.

    Se è stato consentito l'accesso al client, il server RADIUS trasmette la chiave principale del client al punto di accesso senza fili. A questo punto, il client e il punto di accesso condividono i dati della chiave comune, che possono utilizzare per crittografare e decrittografare il traffico WLAN che si scambiano.

    Se si utilizza il WEP dinamico per crittografare il traffico, le chiavi principali vengono utilizzate direttamente come chiavi di crittografia. È necessario modificare periodicamente tali chiavi per impedire attacchi di recupero delle chiavi WEP. Questa operazione viene eseguita dal server RADIUS forzando regolarmente il client a eseguire una nuova autenticazione e a generare un nuovo set di chiavi.

    Se le comunicazioni vengono protette tramite WPA, i dati della chiave principale vengono utilizzati per ricavare le chiavi di crittografia dei dati, che vengono modificate per ogni pacchetto trasmesso. Per garantire la protezione delle chiavi, non è necessario che WPA forzi una nuova autenticazione periodica.

4.  Il punto di accesso esegue quindi il bridging della connessione WLAN client alla rete LAN interna, consentendo al client di comunicare liberamente con i sistemi della rete interna. A questo punto, il traffico inviato tra il client e il punto di accesso viene crittografato.

5.  Se è necessario un indirizzo IP per il client, quest'ultimo può richiedere un lease DHCP (Dynamic Host Configuration Protocol) a un server della rete LAN. Dopo l'assegnazione dell'indirizzo IP, il client può iniziare a comunicare normalmente con i sistemi presenti sul resto della rete.

##### Autenticazione di computer e utenti nella rete WLAN

Il processo appena descritto illustra le modalità con cui un client (un utente o un computer) si connette alla rete WLAN. Windows XP autentica separatamente sia l'utente che il computer. All'avvio del computer, vengono utilizzati il relativo account di dominio e la password per eseguire l'autenticazione alla rete WLAN. Dopo tutte le operazioni descritte nella sezione precedente, segue l'autorizzazione del computer nella rete WLAN. Poiché il computer si connette alla rete WLAN tramite le relative credenziali, è possibile effettuare operazioni di gestione anche quando non è collegato alcun utente. Ad esempio, è possibile applicare le impostazioni dei criteri di gruppo e distribuire il software e le patch al computer.

Quando un utente accede al computer, viene ripetuto lo stesso processo di autenticazione e autorizzazione ma in questo caso vengono utilizzati il nome e la password dell'utente. La sessione dell'utente sostituisce la sessione WLAN del computer; pertanto le due sessioni non possono essere attive contemporaneamente e un utente non autorizzato non può utilizzare un computer autorizzato per accedere alla rete WLAN.

**Nota:** Windows XP consente di ignorare questo funzionamento e di specificare che vengano utilizzate solo le credenziali del computer oppure solo le credenziali dell'utente. Queste configurazioni non sono quelle consigliate. Le prime consentono agli utenti di connettersi alla rete WLAN senza autorizzazione, mentre le seconde impediscono al computer di connettersi alla rete WLAN fino a quando esiste un utente collegato, che interferisce con varie funzioni di gestione del computer.

[](#mainsection)[Inizio pagina](#mainsection)

### Profilo dell'organizzazione di destinazione

Questa soluzione è stata progettata per piccole imprese con un numero di dipendenti variabile da 100 a 200 dipendenti. Anche se l'organizzazione di riferimento è fittizia, le caratteristiche e i requisiti corrispondenti sono il frutto di una ricerca approfondita nel mondo reale. Lo stile e lo scopo di questa guida, insieme alla scelte relative alla progettazione, sono stati definiti in base a tali requisiti.

È importante comprendere che questa soluzione non è valida solo per le organizzazioni di piccole dimensioni. La semplicità della progettazione e la scalabilità dei componenti utilizzati consentono infatti di adattare facilmente la stessa soluzione per reti WLAN basata su PEAP per organizzazioni di dimensioni maggiori (con migliaia di utenti) o minori. In base alle caratteristiche dell'organizzazione di destinazione fittizia, sarà possibile comprendere i presupposti di base della progettazione e adattarli alla propria organizzazione.

L'utilizzo della soluzione in organizzazioni più grandi è illustrato nella sezione "Scalabilità per organizzazioni di maggiori dimensioni" di questo capitolo. Per organizzazioni di minori dimensioni, è possibile installare tutti i componenti necessari in un singolo server disponibile.

#### Layout dell'organizzazione

Il layout fisico e IT dell'organizzazione è illustrato nella figura seguente.

[![](images/Dd536231.PEAP_202(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536231.peap_202_big(it-it,technet.10).gif)

**Figura 2.2 Layout fisico e IT dell'organizzazione di destinazione**

Esiste un'unica sede centrale di grandi dimensioni, che ospita la maggior parte dei sistemi IT e degli utenti. Tutti i controller di dominio di Active Directory si trovano in tale sede. Nella sede centrale è disponibile una connessione a Internet tramite un server firewall. Alcuni client WLAN e punti di accesso senza fili sono connessi alla rete interna.

Esistono inoltre uno o più uffici periferici con un numero estremamente ridotto di servizi IT locali oltre alla connettività di rete alla sede centrale. In questi uffici è disponibile un numero limitato di client, possibilmente tutti senza fili, e spesso vengono ospitati visitatori provenienti dalla sede centrale che portano i propri clienti WLAN per connettersi ai dati e alle applicazioni residenti in tale sede.

La connettività WAN (Wide Area Network) tra gli uffici viene garantita tramite linee private(ad esempio, una linea T1 da 1,5 Mbps) o mediante connessioni Internet DSL e un collegamento VPN da router a router attraverso Internet. In genere, la connessione WAN non prevede capacità di recupero dagli errori.

**Nota:** se la connessione WAN tra gli uffici viene assicurata mediante una connessione VPN attraverso Internet, ogni ufficio disporrà generalmente di un firewall per la protezione dai pericoli presenti su Internet. Poiché il firewall eventualmente esistente non è rilevante per la descrizione della rete WLAN, è stato omesso in modo da semplificare l'argomento.

#### Ambiente IT

In questa organizzazione, Active Directory consiste in un singolo insieme di strutture di dominio con almeno due controller di dominio. Esegue l'autenticazione degli utenti nel dominio e offre servizi directory e di autenticazione per varie applicazioni, ad esempio Microsoft Exchange Server e Outlook® per la posta elettronica. I controller di dominio sono stati aggiornati recentemente da Windows 2000 Server a Windows Server 2003, Standard Edition. I controller di dominio eseguono anche servizi aggiuntivi, quali il sistema DNS (Domain Name System), DHCP e WINS (Windows Internet Name Service), per alcune applicazioni ereditate.

I sistemi IT sono rappresentati prevalentemente da tecnologie Microsoft, con Windows XP nei computer client e Windows Server 2003 nei sistemi server. Inoltre sono disponibili alcuni server Windows 2000, che la società intende aggiornare in base a quanto consentito dal testing delle applicazioni e dal supporto. L'organizzazione ha iniziato a investire in sistemi portatili quali Windows XP, Tablet Edition e Pocket PC 2003, specialmente per il personale addetto alle vendite, alla distribuzione e al magazzino.

Tra le principali applicazioni server sono inclusi Microsoft Exchange Server, SQL Server (che esegue diverse applicazioni line-of-business), Internet Information Services (IIS) e Windows SharePoint™ Team Services.

Le applicazioni vengono distribuite nei computer client mediante i criteri di gruppo di Active Directory. Le patch dei sistemi operativi vengono distribuite mediante Microsoft Software Update Service (SUS) e il servizio di aggiornamento automatico di Windows.

Il monitoraggio del sistema viene eseguito direttamente nei sistemi server esaminando ogni giorno i registri eventi di Windows, i registri prestazioni e i registri applicazioni. Gli avvisi critici relativi ad hardware e software vengono inviati all'amministratore IT tramite messaggi di posta elettronica e avvisi sulle console di sistema.

L'organizzazione dispone di due esperti IT a tempo pieno che si occupano della pianificazione IT, della fornitura dei servizi e del supporto tecnico quotidiano. Sia il responsabile IT che l'addetto al supporto tecnico IT hanno acquisito le certificazioni MCSE più recenti e alcuni anni di esperienza nel settore IT.

[](#mainsection)[Inizio pagina](#mainsection)

### Criteri di progettazione

L'organizzazione descritta nella sezione precedente applicherà generalmente a una soluzione per reti WLAN i tipi di criteri riportati di seguito. Tali criteri sono stati estesi a una vasta categoria di organizzazioni. La progettazione presentata nel resto del capitolo è basata esplicitamente su tali criteri.

**Tabella 2.1: Criteri di progettazione della soluzione per reti WLAN**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Fattore di progettazione</th>
<th style="border:1px solid black;" >Criteri</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Requisiti di protezione</td>
<td style="border:1px solid black;">- Autenticazione e autorizzazione affidabile dei client senza fili
- Controllo dell'accesso affidabile per consentire l'accesso di rete ai client autorizzati e negare l'accesso non autorizzato
- Crittografia di alto livello (128 bit) del traffico di rete senza fili
- Gestione protetta delle chiavi di crittografia</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Scalabilità - Numero min/max di utenti supportati</td>
<td style="border:1px solid black;">Da 25 a 5.000 utenti WLAN e oltre
Per reti WLAN di dimensioni differenti, vedere la tabella 2.2.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Scalabilità - Numero di sedi supportate</td>
<td style="border:1px solid black;"><strong>Base:</strong> sede singola di grandi dimensioni con controller di dominio e servizi IT locali; uno o più uffici di minori dimensioni senza controller di dominio. È richiesto un numero minimo di 25 utenti.
<strong>Fascia alta:</strong> singola sede centrale con più controller di dominio; grandi uffici con un singolo controller di dominio e/o connettività WAN con capacità di recupero alla sede centrale; più uffici di piccole dimensioni senza controller di dominio, probabilmente senza capacità di recupero della rete WAN. Il numero massimo di utenti consentito è 5000.
Per organizzazioni di maggiori dimensioni, fare riferimento all'appendice A, &quot;Utilizzo di PEAP nell'impresa&quot;.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Requisiti di disponibilità</td>
<td style="border:1px solid black;">L'utilizzo di più punti di accesso senza fili, server IAS o controller di dominio determina capacità di recupero della rete WLAN in caso di errori dei singoli componenti negli uffici di maggiori dimensioni. Le reti WLAN degli uffici di piccole dimensioni sono soggette a guasti, a meno che venga installata una connettività ridondante.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto di piattaforme</td>
<td style="border:1px solid black;"><strong>Piattaforme server:</strong> Windows Server 2003, Standard Edition o Enterprise Edition (per l'installazione di IAS e di autorità di certificazione). Standard Edition supporta un massimo di 50 punti di accesso senza fili (client RADIUS) per ogni server.
<strong>Piattaforme client:</strong> Windows XP Professional o Tablet Edition; Pocket PC 2003.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Estensibilità (riutilizzo dei componenti della soluzione per altre applicazioni)</td>
<td style="border:1px solid black;">Altre applicazioni di accesso alla rete (VPN di accesso remoto, accesso alla rete cablata 802.1X e autenticazione firewall) possono essere supportate dalla stessa infrastruttura di autenticazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Requisiti dell'organizzazione IT</td>
<td style="border:1px solid black;">Per l'installazione e la gestione della soluzione sono necessari professionisti IT con la certificazione MSCE più recente o una conoscenza equivalente e da 2 a 3 anni di esperienza nel settore IT.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Requisiti di gestibilità</td>
<td style="border:1px solid black;">Per mantenere il corretto funzionamento della soluzione sono necessarie operazioni minime di gestione.
Gli avvisi vengono inviati tramite posta elettronica e/o il registro eventi di Windows oppure vengono modificati per segnalare altri tipi di alterazioni.
È possibile controllare il componente IAS mediante la soluzione di monitoraggio di Windows utilizzando registri eventi e contatori delle prestazioni, mediante la registrazione RADIUS e tramite il sistema di gestione SNMP (Simple Network Management Protocol).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Conformità agli standard</td>
<td style="border:1px solid black;">La soluzione supporta i seguenti standard:
- Standard di rete IEEE 802.11 (a, b, o g)
- Autenticazione IEEE 802.1X con PEAP e MS-CHAP v2 (può essere utilizzata con altri metodi EAP, ad esempio il protocollo EAP-TLS basato su certificati e PEAP-EAP-TLS).
- Protezione della rete WLAN con WEP a chiave dinamica e WPA
- Funzionalità e standard futuri (ad esempio, 802.11i).
- Supporto RADIUS per RFC 2865 e 2866.</td>
</tr>
</tbody>
</table>
 

Nella tabella seguente sono riportati i requisiti per l'autenticazione WLAN in organizzazioni di varie dimensioni. Nella colonna "Nuove autenticazioni al secondo" viene indicata una parte del carico costante in base a una media delle quattro nuove autenticazioni quotidiane per ogni utente mobile che si sposta tra punti di accesso senza fili. Nella colonna "Numero massimo nuove autenticazioni al secondo" viene indicato il tipo di carico previsto quando tutti gli utenti eseguono l'autenticazione in un periodo di 30 minuti, ad esempio all'inizio della giornata. Nella colonna "Riautenticazioni al secondo" viene indicato il numero di riautenticazioni periodiche per forzare il rinnovo delle chiavi WEP dinamiche.

**Tabella 2.2: Requisiti per l'autenticazione WLAN**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Numero di utenti WLAN</th>
<th style="border:1px solid black;" >Nuove autenticazioni al secondo</th>
<th style="border:1px solid black;" >Numero massimo nuove autenticazioni al secondo</th>
<th style="border:1px solid black;" >Riautenticazioni al secondo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">100</td>
<td style="border:1px solid black;">&gt; 0,1</td>
<td style="border:1px solid black;">0,1</td>
<td style="border:1px solid black;">0,1</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">1000</td>
<td style="border:1px solid black;">0,1</td>
<td style="border:1px solid black;">0,6</td>
<td style="border:1px solid black;">1,1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">10.000</td>
<td style="border:1px solid black;">1,4</td>
<td style="border:1px solid black;">5,6</td>
<td style="border:1px solid black;">11,1</td>
</tr>
</tbody>
</table>
  
Questi dati si riferiscono alla descrizione delle dimensioni del server IAS riportata più avanti nel capitolo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Architettura WLAN
  
In questa sezione viene presentata l'architettura della soluzione.
  
#### Struttura della rete
  
Nella figura seguente viene illustrato il layout della rete di base per la sede centrale.
  
[![](images/Dd536231.PEAP_203(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536231.peap_203_big(it-it,technet.10).gif)
  
**Figura 2.3 Layout della rete per la sede centrale**
  
La figura mostra i client senza fili, due o più punti di accesso senza fili, due server IAS in esecuzione nei controller di dominio di Active Directory, un server DHCP e altri server, client e dispositivi connessi alla rete. Ad eccezione dei client WLAN, tutti gli elementi sono connessi a una rete LAN singola tramite uno o più switch di livello 2. Per l'intera rete interna di questa sede viene utilizzata un'unica subnet. Sono disponibili connessioni di routing (non indicate nella figura) a Internet e ad altri uffici tramite firewall.
  
Nelle organizzazioni di maggiori dimensioni è più probabile che esista un ambiente di routing all'interno di una singola sede. Sebbene tale differenza non influisca affatto sull'infrastruttura di autenticazione, potrebbe avere un impatto sulla modalità di connessione dei punti di accesso senza fili al resto della rete. Per facilitare lo spostamento degli utenti tra più punti di accesso all'interno di una sede, in genere tutti i punti di accesso senza fili e i client WLAN vengono posizionati nella stessa subnet IP. In questo modo gli utenti possono spostarsi tra i punti di accesso senza fili mantenendo tuttavia lo stesso indirizzo IP. La descrizione dettagliata esula dagli argomenti trattati in questa guida. Per ulteriori informazioni, vedere il capitolo "Deploying a Wireless LAN" (in inglese) del *Windows Server 2003 Deployment Kit*.
  
Nella struttura della rete, è necessario verificare quanto segue:
  
-   I punti di accesso senza fili devono disporre della connettività sia al server IAS primario che a quello secondario. Se i punti di accesso si trovano su una rete WLAN o una subnet diversa rispetto ai server IAS, il traffico deve essere instradabile tra queste subnet.
  
-   I client WLAN devono disporre della connettività ai server DHCP. Se i server non si trovano nella stessa subnet, è necessario disporre di agenti di inoltro DHCP/BOOTP per inoltrare la richiesta DHCP dei client a un DHCP con un ambito definito per tale subnet. Per i client sarà necessaria ovviamente anche la connettività ai normali servizi di rete corrispondenti, ad esempio ai controller di dominio, ai file server e così via.
  
##### Scelta dell'hardware di rete senza fili
  
È consigliabile verificare che i punti di accesso e le schede di rete senza fili supportino quanto segue:
  
-   Crittografia WEP a 128 bit se si utilizza il WEP dinamico oppure crittografia TKIP (RC4) o AES se si utilizza WPA
  
-   Autenticazione 802.1X
  
-   Aggiornamento delle chiavi dinamiche (solo crittografia WEP)
  
-   Supporto WPA (anche se si utilizza il WEP dinamico, è consigliabile ottenere dal fornitore l'impegno esplicito a fornire l'aggiornamento firmware per assicurare il supporto WPA).
  
È necessario disporre di un numero sufficiente di punti di accesso senza fili al fine di garantire la copertura dei client WLAN nelle posizioni fisiche che è necessario supportare. È inoltre consigliabile pianificare il posizionamento dei punti di accesso senza fili in modo da ottenere la copertura di backup appropriata in tutte le posizioni in caso di problemi in uno di tali punti di accesso. Il posizionamento dei punti di accesso senza fili è illustrato in dettaglio nel capitolo "Deploying a Wireless LAN" (in inglese) del *Windows Server 2003 Deployment Kit*, elencato anche nella sezione "Riferimenti" alla fine di questo capitolo. È opportuno leggere anche l'articolo "Recommendations for IEEE 802.11 Access Points" (in inglese), indicato nei riferimenti riportati alla fine di questo capitolo.
  
#### Posizionamento del server IAS
  
Lo scopo del posizionamento del server IAS è quello di ottenere un servizio WLAN con capacità di recupero limitando contemporaneamente i costi di implementazione e di gestione. Un servizio WLAN con capacità di recupero in caso di guasto di un singolo componente presenta le seguenti caratteristiche:
  
-   Tutte le aree fisiche per cui è necessaria la copertura WLAN devono disporre di due o più punti di accesso senza fili compresi nell'intervallo.
  
-   Ogni punto di accesso senza fili deve essere in grado di comunicare con un server IAS di backup nel caso in cui si verifichi un errore nel server IAS primario corrispondente o nella connessione di rete a questo server.
  
-   Anche i servizi da cui dipendono IAS e i client WLAN, ad esempio Active Directory, DHCP e DNS, devono includere capacità di recupero.
  
Il secondo di questi è il più importante ai fini della pianificazione del posizionamento del server IAS. In questa soluzione, IAS si trova nei controller di dominio esistenti. In questo modo si garantiscono una configurazione con le massime prestazioni e costi di implementazione e di gestione ridotti. Come raccomandazione generale per le organizzazioni di tutte le dimensioni, si consiglia di distribuire IAS in ogni sede che dispone di un controller di dominio, anche se in alcuni casi non è necessario installare IAS in ogni controller di dominio.
  
Nella figura seguente viene illustrato il posizionamento dei server IAS nell'organizzazione. IAS viene distribuito nei due controller di dominio della sede centrale. In uno di questi controller di dominio è installata anche la CA di rete (fare riferimento alla sezione "Come ottenere i certificati per i server IAS" più avanti in questo capitolo). Tutti i punti di accesso della sede centrale vengono configurati per l'utilizzo di questi server IAS.
  
[![](images/Dd536231.PEAP_204(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536231.peap_204_big(it-it,technet.10).gif)
  
**Figura 2.4 Infrastruttura della sede centrale e della filiale**
  
L'organizzazione include una piccola filiale senza alcun controller di dominio locale. I punti di accesso senza fili della filiale utilizzano i due server IAS della sede centrale per tutte le richieste di autenticazione. Pertanto gli utenti non potranno eseguire l'autenticazione nella rete WLAN in caso di errore nella connessione WAN alla sede centrale. Per molte organizzazioni, questo rischio potrebbe non essere accettabile.
  
Per risolvere tale problema, è consigliabile installare una connettività WAN ridondante oppure un server IAS e un controller di dominio locali. Sebbene tale strategia possa comportare apparentemente un costo eccessivo per questo tipo di ufficio, i guasti alla rete WAN causerebbero problemi in altri servizi di rete (ad esempio, ai file server locali) senza accesso a un controller di dominio. Di conseguenza, la risoluzione del problema sopra indicata presenta il vantaggio di garantire l'affidabilità sia di tali servizi che della rete WLAN locale. La distribuzione dei controller di dominio nelle filiali è descritta nella sezione "Scalabilità per organizzazioni di maggiori dimensioni", riportata più avanti nel capitolo.
  
Per piccoli uffici in cui la connettività WAN è estremamente inaffidabile e non è conveniente distribuire un controller di dominio locale, è possibile installare una rete WLAN autonoma. Per ulteriori informazioni su questo argomento, leggere la sezione "Ambienti SOHO" riportata più avanti nel capitolo.
  
##### Assegnazione di punti di accesso ai server RADIUS
  
È necessario assegnare tutti i punti di accesso senza fili ai server IAS. Ogni punto di accesso senza fili richiede un server RADIUS primario e uno secondario. In questo modo, il punto di accesso senza fili può utilizzare il server RADIUS secondario nel caso in cui il server primario sia guasto o non contattabile. Questa configurazione è illustrata nella figura seguente.
  
![](images/Dd536231.PEAP_205(it-it,TechNet.10).gif)
  
**Figura 2.5 Bilanciamento del punto di accesso tra server IAS primario e secondario**
  
La figura mostra la configurazione di ogni punto di accesso senza fili con server RADIUS primario e secondario differenti. Tale strategia consente il bilanciamento del carico tra i server. I punti di accesso senza fili negli uffici senza server IAS locale seguono lo stesso schema, utilizzando i server IAS della sede centrale rispettivamente come server RADIUS primario e secondario.
  
Per i punti di accesso senza fili negli uffici con un unico server IAS locale, quest'ultimo deve svolgere sempre la funzione di server primario mentre il server nella sede centrale (o in un altra posizione appropriata in cui sia disponibile una connettività affidabile al server IAS) deve svolgere la funzione di server secondario. Questa configurazione è illustrata nella figura seguente.
  
[![](images/Dd536231.PEAP_206(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536231.peap_206_big(it-it,technet.10).gif)
  
**Figura 2.6 Configurazione dei punti di accesso per l'utilizzo di server IAS locali e remoti**
  
Se si dispone di numerosi punti di accesso, è consigliabile documentarne accuratamente l'assegnazione ai server IAS. È possibile utilizzare questa registrazione per assicurare che ogni punto di accesso sia stato assegnato a un server primario e secondario e che il carico dei punti di accesso sia bilanciato equamente tra i server disponibili.
  
**Nota:** se il server IAS primario non è disponibile, per tutti i punti di accesso senza fili si verificherà il failover nel server IAS secondario. Tuttavia la maggior parte dei punti di accesso non tornerà automaticamente a utilizzare il server primario quando questo diventerà di nuovo disponibile, ma soltanto in caso di guasto successivo del server secondario. Il problema non è grave se entrambi i server IAS si trovano nella stessa posizione, in quanto determinerà semplicemente un carico disomogeneo nei server. Se invece il server IAS secondario è remoto, un guasto temporaneo del server primario potrebbe comportare l'autenticazione di tutti i punti di accesso nel server secondario su un collegamento WAN non ottimale.
  
Nel caso in cui i punti di accesso non tornino automaticamente al server primario designato, potrebbe essere necessario reimpostarli in modo che inizino a utilizzare il server IAS locale ripristinato dopo un guasto. Condizioni di rete temporanee possono inoltre causare il failover dei punti di accesso nei server RADIUS secondari; pertanto potrebbe essere necessario controllare occasionalmente gli eventi di richiesta di autenticazione nei registri applicazioni dei server IAS al fine di individuare eventuali punti di accesso che utilizzano il server IAS errato.
  
##### Posizionamento di IAS nei controller di dominio
  
In questa soluzione, IAS è installato nei controller di dominio esistenti. In questo modo si limitano i costi di implementazione e si ottiene un miglioramento delle prestazioni relative all'utilizzo di IAS in due server membri distinti. L'aumento delle prestazioni è dovuto al fatto che IAS può comunicare con Active Directory nello stesso computer senza ritardi a livello di rete.
  
Per l'installazione di IAS nei controller di dominio è necessario tenere presenti alcuni avvertimenti. Anche se per molte organizzazioni può essere superfluo, prima di proseguire è consigliabile considerare quanto segue:
  
-   Non sarà possibile disporre di un'unica configurazione per tutti i controller di dominio a meno che, ovviamente, si scelga di installare IAS in tutti i controller di dominio.
  
-   Non sarà possibile applicare la distinzione tra amministrazione di IAS e amministrazione del dominio. Se si installa IAS nei controller di dominio, è necessario che gli amministratori di IAS siano anche membri del gruppo Domain Administrators predefinito.
  
-   Un carico elevato sulle funzioni dei controller di dominio influirà negativamente sulle prestazioni di IAS e viceversa. È possibile posizionare IAS e tali funzioni in server distinti in modo da disporre di un maggiore controllo sulle prestazioni e sul funzionamento dei singoli servizi.
  
#### Requisiti software e hardware per IAS
  
Nel caso di un'organizzazione di destinazione che comprende da 100 a 200 utenti è improbabile che il carico di IAS sui server causi problemi, a condizione che venga utilizzata la specifica hardware consigliata per Windows Server 2003. Per organizzazioni di maggiori dimensioni, tuttavia, tale carico può rappresentare un problema, specialmente se IAS è in esecuzione nei controller di dominio esistenti.
  
Il carico di IAS verrà influenzato dai seguenti fattori:
  
-   Numero di utenti e dispositivi per cui è necessaria l'autenticazione RADIUS
  
-   Scelta delle opzioni di autenticazione, quali il tipo di EAP e la frequenza di riautenticazione
  
-   Eventuale attivazione della registrazione RADIUS.
  
È possibile utilizzare i dati riportati nella tabella 2.2 della sezione precedente "Criteri di progettazione" per effettuare una stima del numero di autenticazioni al secondo previste per una determinata popolazione di utenti. È consigliabile considerare lo stato di carico costante che si verifica quando gli utenti eseguono normalmente l'autenticazione e il carico che si registra nel peggiore dei casi durante le ore di punta. Se si estrapolano i dati di questa tabella, si ottiene che 200 utenti generano un carico costante corrispondente a meno di un'autenticazione completa ogni 50 secondi e a una riautenticazione rapida ogni dieci secondi. Tali cifre sono talmente irrilevanti che l'unico dato realmente significativo è il tempo impiegato per l'autenticazione di tutti gli utenti in seguito a un'interruzione, quando tutti gli utenti devono riconnettersi immediatamente alla rete WLAN. Si tratta di un picco estremo di gran lunga superiore all'accesso all'inizio della giornata, per il quale sono necessari circa 30 minuti o un periodo di tempo maggiore.
  
Le opzioni di autenticazione influiscono in modo significativo sul carico dei server IAS. All'accesso iniziale, protocolli come PEAP eseguono un'operazione a chiave pubblica che richiede un uso intensivo della CPU; invece per le riautenticazioni successive vengono utilizzate le informazioni della sessione memorizzate nella cache, consentendo il processo noto come "riconnessione rapida". Se si utilizza il WEP dinamico, i client eseguiranno la riautenticazione ogni 15-60 minuti per generare nuove chiavi di crittografia. Con WPA, tuttavia, è necessario applicare la riautenticazione con minore frequenza, in genere ogni 8 ore.
  
Nella tabella seguente è indicato il numero approssimativo di autenticazioni al secondo per IAS in un server con processore Intel Pentium 4 a 2 GHz che esegue Windows Server 2003 con Active Directory in un server distinto.
  
**Nota:** le informazioni riportate nella tabella seguente sono state ricavate in base ai test eseguiti da Microsoft Solutions for Security. Queste informazioni vengono fornite senza alcuna garanzia e devono essere intese come mere linee guida ai fini della pianificazione della capacità e non ai fini di un confronto tra prestazioni.
  
**Tabella 2.3: Autenticazioni al secondo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Tipo di autenticazione</th>
<th style="border:1px solid black;" >Nuove autenticazioni</th>
<th style="border:1px solid black;" >Autenticazioni con riconnessione rapida</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Autenticazioni PEAP al secondo</td>
<td style="border:1px solid black;">36</td>
<td style="border:1px solid black;">166</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Tempo per l'autenticazione di 200 utenti</td>
<td style="border:1px solid black;">6 sec</td>
<td style="border:1px solid black;">2 sec</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Tempo per l'autenticazione di 1000 utenti</td>
<td style="border:1px solid black;">30 sec</td>
<td style="border:1px solid black;">7 sec</td>
</tr>
</tbody>
</table>
  
Questi dati sono stati calcolati attivando la registrazione RADIUS ed eseguendo Active Directory in un server distinto; poiché entrambi questi fattori riducono le prestazioni di IAS, tali dati devono essere considerati come una stima valida nel peggiore dei casi.
  
Come indicato dai dati, questo tipo di server consentirà a 200 utenti WLAN di eseguire l'autenticazione in rete in sei secondi e a 1000 utenti di effettuare tale processo in 30 secondi.
  
##### Utilizzo di Windows Server Standard Edition o Enterprise Edition
  
Questa soluzione utilizza Windows Server 2003, Standard Edition per tutti i server IAS; in questo modo si limita il costo delle licenze server ed è possibile eseguire la distribuzione nei server esistenti indipendentemente dal fatto che si tratti di server Standard Edition o Enterprise Edition.
  
In Windows Server 2003, Standard Edition, per IAS esistono limitazioni in base alle quali ogni server può supportare solo 50 client RADIUS e due gruppi di routing del server RADIUS.
  
**Nota:** i client RADIUS non sono identici ai client WLAN. Il client RADIUS fa riferimento ai punti di accesso senza fili e anche ad altri server di accesso alla rete, ad esempio server VPN e firewall che utilizzano i servizi di autenticazione RADIUS.
  
Per l'organizzazione di destinazione che comprende da 1 a 200 utenti, un massimo di 50 punti di accesso per server è più che sufficiente. Per organizzazioni di maggiori dimensioni, questo limite può essere significativo in particolar modo per grandi uffici oppure per uffici periferici basati su uno o due server IAS hub.
  
Se si suppone che esistano 15 utenti per ogni punto di accesso senza fili, un singolo server IAS con Windows Server 2003, Standard Edition potrebbe supportare circa 750 utenti. In questo calcolo si è tenuto conto del numero totale di punti di accesso che utilizzeranno un server come server RADIUS primario o secondario; pertanto, due server supporteranno 50 punti di accesso e non 100. Se uno dei server IAS deve supportare più di 50 punti di accesso, è necessario utilizzare Windows Server 2003, Enterprise Edition. Ovviamente è anche possibile unire e associare le due edizioni utilizzando Windows Server 2003, Enterprise Edition per uffici di grandi dimensioni e uffici hub e Windows Server 2003, Standard Edition per uffici di minori dimensioni.
  
#### Configurazione IAS
  
È possibile suddividere le impostazioni IAS in quattro categorie principali:
  
-   Impostazioni del server IAS
  
-   Configurazione della registrazione RADIUS
  
-   Criteri di accesso remoto
  
-   Criteri richiesta di connessione
  
Queste categorie sono descritte in dettaglio nelle sottosezioni seguenti. Tutte le impostazioni sono comuni a tutti i server IAS utilizzati in questa soluzione, in modo che sia possibile configurarle in un singolo server IAS e copiarle negli altri server. Questa tecnica viene utilizzata nel capitolo 5, "Creazione dell'infrastruttura di protezione per LAN senza fili", al fine di garantire che le impostazioni IAS siano coerenti in tutti i server dell'organizzazione.
  
Ogni server IAS disporrà inoltre di uno o più punti di accesso senza fili configurati come client RADIUS. I client RADIUS sono stati descritti nella sezione precedente "Assegnazione di punti di accesso ai server RADIUS". In genere, l'insieme di client RADIUS è diverso per ogni server e pertanto non viene replicato tra i server come le altre impostazioni.
  
##### Impostazioni del server IAS
  
Questa categoria include:
  
-   Registrazione delle richieste di autenticazione nel registro eventi di Windows. In questa soluzione è attivata la registrazione delle operazioni riuscite e non riuscite.
  
    **Nota:** la registrazione delle richieste è descritta nella sezione "Registrazione RADIUS" più avanti in questo capitolo.
  
-   Le porte UDP (User Datagram Protocol) su cui il server IAS ascolta le richieste di accounting e di autenticazione RADIUS. Questa soluzione utilizza le porte RADIUS predefinite 1812 e 1813 rispettivamente per l'autenticazione e l'accounting.
  
##### Criteri RADIUS
  
I criteri IAS controllano l'autenticazione e l'autorizzazione degli account nella rete. Esistono due tipi di criteri:
  
-   Criteri di accesso remoto
  
-   Criteri richiesta di connessione.
  
I criteri di accesso controllano la modalità con cui una connessione viene eventualmente autorizzata in rete. Un criterio di accesso remoto contiene un insieme di condizioni filtro che determinano se applicare o meno tale criterio a una determinata richiesta di connessione. Alcuni esempio di condizioni filtro sono: specificare il gruppo di protezione di Windows a cui deve appartenere un client; specificare il tipo di connessione del client richiedente, ad esempio Senza fili o VPN; specificare l'ora del giorno in cui il client tenta di eseguire la connessione. Ogni criterio di accesso remoto prevede un'azione corrispondente, impostata sull'opzione per *consentire* o *rifiutare* una richiesta di connessione. Alle richieste di connessione corrispondenti al filtro della condizione del criterio di accesso remoto verrà concesso o negato l'accesso alla rete in base all'impostazione dell'azione relativa al criterio.
  
Un criterio di accesso remoto contiene inoltre un insieme di parametri applicati a una connessione consentita, noto come profilo dei criteri di accesso remoto. Questi parametri includono i metodi di autenticazione accettabili per la connessione, la modalità di assegnazione di un indirizzo IP al client e l'intervallo di tempo durante il quale il client può rimanere connesso prima che venga richiesta l'autenticazione. In un server IAS possono esistere più criteri di accesso remoto; ogni richiesta di connessione viene valutata in base a tali criteri, in ordine di priorità, fino a quando un criterio di accesso remoto corrispondente consente o rifiuta la richiesta.
  
In questa soluzione, i criteri di accesso remoto sono configurati come illustrato nella tabella seguente.
  
**Tabella 2.4: Configurazione dei criteri di accesso remoto**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Elemento di configurazione</th>
<th style="border:1px solid black;" >Impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nome criterio</td>
<td style="border:1px solid black;">Consenti accesso LAN senza fili</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Tipo di criterio</td>
<td style="border:1px solid black;">Consenti</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Condizioni criteri di accesso remoto</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Tipo - porta - NAS corrispondente</td>
<td style="border:1px solid black;">Senza fili - IEEE 802.11
Senza fili - Altro</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Gruppo di Windows corrispondente</td>
<td style="border:1px solid black;">Accesso LAN senza fili</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Profilo criteri di accesso remoto</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Limitazioni chiamate in ingresso - Timeout client</td>
<td style="border:1px solid black;">60 minuti (WEP dinamico)
8 ore (WPA)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Assegnazione indirizzo IP</td>
<td style="border:1px solid black;">L'assegnazione dell'indirizzo IP è determinata dalle impostazioni del server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Filtro IP</td>
<td style="border:1px solid black;">Nessuno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Autenticazione</td>
<td style="border:1px solid black;">Tutto disattivato ad eccezione di EAP</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione - Tipo di EAP utilizzato</td>
<td style="border:1px solid black;">PEAP (Protected EAP)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Autenticazione - Tipo di EAP PEAP utilizzato</td>
<td style="border:1px solid black;">EAP MS-CHAP v2</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione - Riconnessione rapida</td>
<td style="border:1px solid black;">Abilitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Attributi RADIUS</td>
<td style="border:1px solid black;">Ignore-User-Dialin-Properties = &quot;True&quot;
Termination Action = &quot;RADIUS-Request&quot;</td>
</tr>
</tbody>
</table>
 

Il filtro della condizione corrisponde a tutti i client senza fili e a tutti i membri del gruppo di dominio Accesso LAN senza fili. I parametri che non sono rilevanti per l'accesso WLAN, quali le impostazioni di crittografia Connessione multipla e Microsoft Point-to-Point Encryption (MPPE), non sono inclusi nella tabella. Per ulteriori dettagli sull'utilizzo dei gruppi di protezione con i criteri di accesso remoto, fare riferimento alla sezione "Modello di amministrazione per utenti e computer di reti WLAN" più avanti in questo capitolo.

L'impostazione Limitazioni chiamate in ingresso - Timeout client può influire sulla protezione e sull'affidabilità della soluzione. Le ragioni per cui talvolta è necessario utilizzare valori diversi da quelli indicati nella tabella sono illustrate nella sezione "Opzioni di protezione per il WEP dinamico" più avanti nel capitolo.

L'attributo RADIUS "Ignore-User-Dialin-Properties" viene utilizzato per ignorare il controllo per utente delle autorizzazioni di accesso alla rete. Per la descrizione del controllo dell'accesso per utente e per gruppo, vedere la sezione "Modello di amministrazione per utenti e computer di reti WLAN".

Un criterio di richiesta di connessione controlla se elaborare la richiesta in un server RADIUS specifico oppure inviarla a un altro server RADIUS, denominato proxy RADIUS. In genere, i proxy RADIUS vengono utilizzati nei casi in cui il server RADIUS non dispone delle informazioni per elaborare direttamente la richiesta e deve quindi inoltrarla a un server RADIUS autorevole, ad esempio a un server di un altro insieme di strutture di Active Directory. I proxy RADIUS non vengono utilizzati in questa soluzione ed esulano dagli argomenti trattati in questa guida.

Per ulteriori informazioni sui criteri di accesso remoto e di richiesta di connessione e sull'utilizzo dei proxy RADIUS, vedere la sezione "Riferimenti" alla fine del capitolo.

##### Registrazione RADIUS

È possibile configurare i server IAS in modo che registrino due tipi di informazioni facoltative:

-   Eventi di autenticazione riusciti e rifiutati

-   Informazioni di autenticazione e di accounting RADIUS.

Gli eventi di autenticazione riusciti e rifiutati generati da dispositivi e utenti WLAN possono essere memorizzati nel registro eventi di sistema di Windows Server 2003 sul server IAS. Le informazioni del registro eventi di autenticazione sono particolarmente utili per la risoluzione dei problemi di autenticazione, sebbene possano essere utilizzate anche per il controllo della protezione e la segnalazione di avvisi.

Inizialmente è consigliabile lasciare attivata la registrazione degli eventi riusciti e rifiutati, ma è possibile disattivarla una volta che il sistema è diventato stabile. Gli eventi di accesso alla rete WLAN riusciti riempiranno il registro eventi di sistema ma potrebbero essere necessari per attività di controllo.

Se si utilizza uno strumento di monitoraggio e segnalazione di avvisi quale Microsoft Operations Manager (MOM), è consigliabile valutare l'opportunità di aggiungere una regola per segnalare gli eventi non riusciti di autenticazione IAS nel registro eventi di sistema. In alternativa, è possibile utilizzare uno strumento per le query al registro eventi, ad esempio eventquery.vbs, per controllare in tale registro la presenza di errori di autenticazione (vedere la voce "Eventquery.vbs" nella Guida in linea). In genere, gli eventi singoli non sono significativi ma una serie di eventi può indicare un tentativo di violazione.

IAS consente inoltre di registrare le informazioni sulle sessioni di autenticazione e di accesso alla rete sotto forma di registri delle richieste RADIUS. Normalmente si utilizza la registrazione RADIUS quando è necessario addebitare l'utilizzo della rete (ad esempio, un provider di servizi Internet deve addebitare la tariffa in base al tempo di connessione) oppure occorrono informazioni speciali di controllo della protezione, anche se nella maggior parte dei casi tali informazioni vengono ricavate dagli eventi di autenticazione memorizzati nel registro eventi.

Per ulteriori informazioni sulla registrazione RADIUS, vedere la sezione "Riferimenti" alla fine del capitolo.

##### Protezione di IAS

È consigliabile applicare a IAS precauzioni di protezione analoghe a quelle utilizzate per un controller di dominio. Il controllo sicuro della rete dipende dalla protezione dell'infrastruttura IAS. Esistono alcune semplici misure che è possibile implementare al fine di migliorare la protezione di IAS:

-   Utilizzare password complesse per i client RADIUS (punti di accesso senza fili). La soluzione include script per generare vere e proprie password casuali in modo da ostacolare gli attacchi del dizionario.

-   Attivare l'autenticatore del messaggio RADIUS per tutti i client RADIUS al fine di impedire lo spoofing degli indirizzi IP dei punti di accesso senza fili. In questa soluzione, l'autenticatore è attivato.

-   Verificare che le impostazioni di protezione del server siano appropriate. Tale procedura è descritta nel capitolo 3, "Predisposizione dell'ambiente".

-   Verificare che i server siano stati corretti con gli ultimi aggiornamenti rapidi per la protezione e che le patch siano mantenute regolarmente aggiornate. Anche questa procedura è descritta nel capitolo 3, "Predisposizione dell'ambiente".

-   Verificare che vengano utilizzate impostazioni avanzate per l'account di dominio. In particolare, è consigliabile controllare che vengano applicate password complesse e che le password vengano modificate regolarmente. È inoltre possibile valutare l'opportunità di attivare il blocco degli account di dominio per impedire gli attacchi di determinazione della password. Tuttavia è consigliabile attivare il blocco degli account solo se si dispone di risorse di supporto per sbloccare in tempo utile gli account degli utenti.

-   È possibile valutare l'opportunità di utilizzare IPSec per proteggere il traffico RADIUS e rafforzare l'autenticazione reciproca tra i punti di accesso senza fili e i server IAS. Tuttavia, non tutti i punti di accesso senza fili supportano l'utilizzo di IPSec per tale scopo.

Per ulteriori informazioni sulle misure di protezione relative a IAS, vedere la sezione "Riferimenti" alla fine di questo capitolo.

##### Modello di amministrazione per utenti e computer di reti WLAN

In questa soluzione, l'accesso alla rete WLAN viene controllato tramite i gruppi di protezione del dominio. Sebbene sia possibile utilizzare le proprietà delle chiamate in ingresso degli oggetti utente del dominio per consentire e negare l'accesso a singoli utenti, l'amministrazione di molti utenti con questo metodo richiede tempo.

Questa soluzione utilizza uno schema estremamente semplice, in base al quale si consente a tutti gli utenti e i computer del dominio di accedere alla rete WLAN. Per molte organizzazioni, il controllo dell'accesso tramite l'appartenenza al dominio è sufficientemente sicuro e riduce al minimo il sovraccarico di gestione aggiuntivo associato alla rete WLAN. Per garantire un maggiore controllo alle organizzazioni che lo richiedono, tuttavia, è possibile utilizzare i gruppi di protezione al fine di definire gli utenti e i computer a cui è consentito l'accesso alla rete WLAN.

Come descritto nella sezione "Criteri RADIUS", i criteri di accesso remoto IAS utilizzano una condizione filtro che concede l'accesso alla rete WLAN a tutti i membri del gruppo Accesso LAN senza fili. Nella tabella seguente è illustrata l'appartenenza al gruppo Accesso LAN senza fili.

**Tabella 2.5: Gruppi di accesso senza fili per consentire l'accesso a tutti gli utenti e i computer**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Gruppo universale di livello superiore (accesso concesso nel criterio di accesso remoto)</th>
<th style="border:1px solid black;" >Membri di primo livello
(Gruppi globali di dominio)</th>
<th style="border:1px solid black;" >Membri di secondo livello
(Gruppi globali di dominio)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Accesso LAN senza fili</td>
<td style="border:1px solid black;">Utenti LAN senza fili</td>
<td style="border:1px solid black;">Domain Users</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso LAN senza fili</td>
<td style="border:1px solid black;">Computer LAN senza fili</td>
<td style="border:1px solid black;">Computer del dominio</td>
</tr>
</tbody>
</table>
  
Il gruppo nella prima colonna, Accesso LAN senza fili, include due membri elencati nella seconda colonna, ovvero Utenti LAN senza fili e Computer LAN senza fili. Questi stessi gruppi di "primo livello" includono i membri indicati nella terza colonna "Membri di secondo livello", rispettivamente i gruppi Domain Users e Computer del dominio. Questa disposizione di gruppi nidificati consente a tutti gli utenti e computer del dominio di connettersi alla rete WLAN.
  
Se questo tipo di concessione risulta eccessivamente permissivo per la propria organizzazione, è possibile rimuovere uno o entrambi i membri Domain Users e Computer del dominio da tali gruppi. In seguito sarà necessario aggiungere account o gruppi di utenti e computer specifici ai gruppi della rete LAN senza fili. Nella tabella seguente è illustrata tale modalità di utilizzo della struttura di gruppo Accesso LAN senza fili.
  
**Tabella 2.6: Gruppi di accesso senza fili per consentire l'accesso agli utenti e ai computer selezionati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Gruppo universale di livello superiore (accesso concesso nel criterio di accesso remoto)</th>
<th style="border:1px solid black;" >Membri di primo livello (Gruppi globali di dominio)</th>
<th style="border:1px solid black;" >Membri di secondo livello
(Gruppi globali di dominio)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Accesso LAN senza fili</td>
<td style="border:1px solid black;">Utenti LAN senza fili</td>
<td style="border:1px solid black;">Utente1<br />
Utente2
Utente3</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso LAN senza fili</td>
<td style="border:1px solid black;">Computer LAN senza fili</td>
<td style="border:1px solid black;">Computer1<br />
Computer2<br />
Computer3</td>
</tr>
</tbody>
</table>
 

Per ulteriori informazioni sull'utilizzo di questi gruppi di protezione in un insieme di strutture multidominio, fare riferimento alla sezione "Scalabilità per organizzazioni di maggiori dimensioni" più avanti in questo capitolo.

#### Come ottenere i certificati per i server IAS

I server IAS devono disporre di certificati per l'autenticazione dei client WLAN. I certificati server sono necessari per creare il tunnel crittografato TLS tra i server IAS e i client. TLS consente di proteggere lo scambio di autenticazione tra il server e i client.

**Nota:** TLS è uno standard RFC basato sullo standard analogo Secure Sockets Layer versione 3.0 (SSL 3.0). Entrambi vengono utilizzati generalmente per proteggere il traffico Web come parte di HTTPS (Hypertext Transfer Protocol Secure).

##### Differenze tra CA incorporata e CA commerciale

Per ottenere questi certificati, è possibile scegliere se installare direttamente una CA o acquistare i certificati da un'autorità di certificazione commerciale. Entrambe le opzioni sono valide e la scelta di una rispetto all'altra non comporta alcuna differenza tecnica per la soluzione per reti WLAN.

I vantaggi e gli svantaggi principali dell'utilizzo di una CA interna rispetto all'acquisto di certificati da un'autorità di certificazione commerciale sono riepilogati nella tabella seguente.

**Tabella 2.7: Vantaggi e svantaggi dell'utilizzo di una CA interna rispetto ai certificati commerciali**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >CA interna</th>
<th style="border:1px solid black;" >CA commerciale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nessun costo per certificato</td>
<td style="border:1px solid black;">Costo per certificato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Software CA da installare e gestire</td>
<td style="border:1px solid black;">Nessun software server</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Registrazione e rinnovo automatici</td>
<td style="border:1px solid black;">Processo di registrazione più complesso, installazione manuale di certificati</td>
</tr>
</tbody>
</table>
  
La scelta finale dipende dalla complessità e dai costi di gestione della CA interna. Se il costo di installazione di una CA locale è limitato e la gestione risulta semplice, in genere questa strategia è più vantaggiosa rispetto all'acquisto di certificati esterni.
  
Questa soluzione utilizza una semplice CA interna per fornire i certificati. In questa guida sono stati utilizzati spesso i termini "CA incorporata" e "CA di rete" per indicare una CA per scopi speciali, sostanzialmente invisibile agli utenti e agli amministratori e in grado di rilasciare certificati di un solo tipo. La funzionalità limitata della CA di questa soluzione comporta il vantaggio che è possibile installare e utilizzare l'autorità di certificazione con operazioni di gestione o interventi dell'utente limitati o nulli. Ad esempio, la CA di questa soluzione può rilasciare un certificato con una durata di 25 anni; pertanto non sarà necessario rinnovarlo durante il ciclo di vita della soluzione. Grazie alla registrazione e al rinnovo automatici dei certificati del server IAS, non è necessario eseguire alcuna distribuzione manuale dei certificati.
  
A questo riguardo, confrontiamo la CA interna con l'utilizzo di certificati esterni. È necessario ricordarsi di rinnovare i certificati di tutti i server IAS ogni anno oppure ogni due anni. Ogni volta è necessario creare manualmente la richiesta di certificato in ciascun server IAS, inviarla alla CA commerciale e quindi recuperare e installare manualmente il certificato rilasciato. Se non si esegue questa procedura, gli utenti non potranno connettersi alla rete WLAN. Per molte organizzazioni, il sovraccarico di gestione dovuto a tale procedura è maggiore rispetto all'utilizzo della semplice CA interna impiegata in questa soluzione.
  
##### Limitazioni della CA della soluzione
  
Per il rilascio di certificati necessari ai server IAS, questa soluzione utilizza una configurazione speciale della CA. Tale configurazione è stata progettata esclusivamente per soddisfare questa esigenza specifica e non è adatta per autorità di certificazione con scopi generici.
  
I certificati digitali vengono utilizzati in molte applicazioni, ad esempio posta elettronica e browser Web, Protezione IP (IPSec), reti private virtuali (VPN), Crittografia file system (EFS) e altre ancora. Per ognuna di queste applicazioni esistono requisiti di protezione specifici. L'organizzazione disporrà di requisiti di protezione univoci per quanto riguarda queste applicazioni. Per tali motivi, Microsoft consiglia di non utilizzare la CA della soluzione per altri scopi.
  
Se si intende utilizzare queste o altre applicazioni dei certificati, è necessario progettare l'infrastruttura di certificazione in base ai requisiti corrispondenti. È necessario tenere in considerazione quanto segue:
  
-   Poiché la CA della soluzione è un'autorità di certificazione principale autofirmata, non è possibile revocarla. In caso di compromissione della CA, è necessario revocare i certificati rilasciati.
  
-   Le disposizioni specifiche di settore o locali potrebbero richiedere l'utilizzo di una gerarchia CA a più livelli per alcuni tipi di certificato o per tutti.
  
-   Microsoft sconsiglia l'installazione di una CA in un controller di dominio per certificati con livello di protezione elevato.
  
Per ulteriori informazioni sulla pianificazione dettagliata necessaria per progettare un'architettura PKI più generica, vedere il capitolo 4 "Designing the Public Key Infrastructure" (in inglese) nella guida alla soluzione correlata, *Securing Wireless LANs — A Certificate Services Solution*.
  
Tenere inoltre presente che esistono alcune limitazioni dovute all'installazione della CA in Windows Server 2003, Standard Edition che, sebbene sia appropriato per questa soluzione, supporta una serie limitata di funzionalità rispetto a Windows Server 2003, Enterprise Edition. Tra le funzionalità principali che non sono disponibili in Windows Server 2003, Enterprise Edition sono incluse:
  
-   **Registrazione automatica di certificati sia per i computer che per gli utenti:** il servizio Richiesta automatica certificati utilizzato in Windows 2000 Server e in Windows Server 2003, Standard Edition supporta solo la registrazione automatica di certificati del computer. Non è possibile registrare automaticamente i certificati dell'utente.
  
-   **Modelli di certificato versione 2:** molti tipi di certificati utilizzati da Windows Server 2003 e Windows XP utilizzano le funzionalità avanzate dei modelli versione 2. Tuttavia, una CA basata su Windows Server 2003, Standard Edition non può rilasciare certificati con i modelli versione 2.
  
-   **Modelli di certificato modificabili:** non è possibile modificare o creare modelli versione 1 per produrre nuovi tipi di certificati.
  
-   **L'archiviazione delle chiavi non è supportata**.
  
Se è richiesta una di queste funzionalità, è necessaria una CA basata sulle funzionalità più avanzate di Windows Server 2003, Enterprise Edition. Per una descrizione dettagliata delle differenze tra Enterprise e Standard Edition, vedere il documento "PKI Enhancements in Windows XP Professional and Windows Server 2003" (in inglese) elencato nella sezione "Riferimenti" alla fine del capitolo.
  
Se attualmente non esistono tuttavia requisiti chiari per altri tipi di certificati, è possibile distribuire la CA descritta in questa soluzione senza escludere ulteriori possibilità in futuro. In una fase successiva, se si identificano altri requisiti relativi ai certificati, è possibile distribuire un'infrastruttura PKI contemporaneamente a questa soluzione. In tal caso è possibile combinarle oppure eseguire la migrazione per rilasciare tutti i certificati dalla nuova infrastruttura PKI.
  
#### Client WLAN
  
La soluzione per reti WLAN supporta implicitamente o esplicitamente vari tipi diversi di client WLAN, ovvero client Windows XP, Professional Edition, Windows XP, Tablet Edition e Pocket PC 2003. Per indicazioni specifiche sulla configurazione e sull'utilizzo di questi client con la soluzione, fare riferimento al capitolo 6 "Configurazione dei client delle reti LAN senza fili". Nella guida non viene illustrato l'utilizzo di altri tipi di client che supportano l'autenticazione 802.1X con PEAP-MS-CHAP v2. Sebbene sia possibile utilizzare altri tipi di client, ad esempio Windows 2000 Professional, la guida non contiene istruzioni per la relativa configurazione e il team Microsoft Solutions for Security non li ha testati con questa soluzione.
  
##### Windows XP
  
Windows XP, Professional Edition e Windows XP, Tablet Edition vengono supportati perfettamente da questa soluzione. È necessario aggiornare tutti i client Windows XP con Service Pack 1 o versioni successive. I computer devono appartenere allo stesso dominio dei server IAS o a un altro dominio all'interno dello stesso insieme di strutture. L'appartenenza al dominio è necessaria per consentire ai computer di eseguire l'autenticazione nella rete WLAN e il download delle impostazioni della rete WLAN specificate nei criteri di gruppo.
  
L'autenticazione dei computer nella rete WLAN viene utilizzata quando nessun utente è connesso al computer. In questo modo, il computer può ottenere le impostazioni degli oggetti Criteri di gruppo (GPO), eseguire gli script di avvio e scaricare le patch. L'autenticazione del computer è necessaria anche durante le fasi iniziali dell'accesso dell'utente. L'utente può avviare l'autenticazione nella rete WLAN solo dopo il caricamento del profilo utente; pertanto non sarà possibile eseguire script di accesso, altre impostazioni degli oggetti Criteri di gruppo e profili comuni se il computer non dispone di una connessione alla rete prima dell'accesso dell'utente.
  
I computer Windows XP che non sono membri di dominio possono comunque essere utilizzati con la soluzione, ma è necessario tenere presenti i seguenti avvertimenti:
  
-   Sarà necessario configurare manualmente le impostazioni dei client WLAN.
  
-   È difficile ottenere l'autenticazione del computer nella rete WLAN.
  
-   Per l'autenticazione dell'utente nella rete WLAN è necessaria una richiesta distinta per nome utente e password, in corrispondenza della quale l'utente deve digitare le relative credenziali WLAN di dominio.
  
Microsoft consiglia inoltre di attivare il firewall personale in tutti i computer client senza fili.
  
##### Pocket PC 2003
  
Pocket PC 2003 supporta l'autenticazione 802.1X e PEAP; tuttavia è possibile ottenere aggiornamenti dal fornitore del dispositivo e da Microsoft per utilizzare funzionalità WLAN complete. È possibile utilizzare anche versioni di Pocket PC precedenti alla 2003 ma in questo caso Microsoft non fornisce il supporto incorporato per l'autenticazione 802.1X. È possibile ottenere supporto specifico dal fornitore del dispositivo Pocket PC o utilizzare software client WLAN di terze parti.
  
I sistemi Pocket PC non prevedono l'utilizzo di account di dominio del computer e vengono sempre autenticati nella rete WLAN utilizzando le credenziali utente. Normalmente, una connessione alla rete WLAN richiede all'utente di digitare ogni volta il relativo nome utente e la password. È possibile salvare le credenziali in modo che il dispositivo si connetta automaticamente ma questa opzione non è consigliata, a meno che nel dispositivo Pocket PC siano disponibili funzionalità di protezione estremamente avanzate.
  
I dispositivi Pocket PC, inoltre, non riconoscono i criteri di gruppo e pertanto non è possibile impostare automaticamente le relative impostazioni della rete WLAN mediante tali criteri. È necessario impostare manualmente la configurazione WLAN.
  
##### Altri client 802.1X
  
I client diversi da Windows XP e Pocket PC 2003 sono compatibili con questa soluzione se supportano l'autenticazione 802.1X e PEAP-MS-CHAP v2. I client Windows 2000 vengono supportati utilizzando Microsoft 802.1X Authentication Client per Windows 2000. I dettagli su come ottenere Microsoft 802.1X Authentication Client per Windows 2000 sono inclusi nei riferimenti alla fine di questo capitolo. I client Windows diversi da Windows 2000, ad esempio Windows NT 4.0, Windows 9*x* e Windows Me, vengono supportati con un client disponibile tramite Microsoft Supporto Premier. È possibile ottenere un client per queste ed altre piattaforme anche da fornitori di software di rete non Microsoft.
  
È consigliabile consultare anche l'appendice C, "Versioni del sistema operativo supportate".
  
##### Supporto WPA
  
La soluzione per reti WLAN descritta in questa guida supporta l'utilizzo della protezione di rete WLAN WPA in sostituzione del WEP dinamico. WPA è sempre preferibile al WEP in quanto consente una migliore gestione delle chiavi e implementa un algoritmo di crittografia di rete più avanzato. WPA supporta anche l'utilizzo della crittografia AES, a condizione che l'hardware (punti di accesso senza fili e schede di rete) offra il supporto necessario.
  
Sebbene WPA presenti alcuni vantaggi rispetto al WEP a chiave dinamica, per il relativo utilizzo è necessario tenere presenti alcuni avvertimenti. Ad esempio:
  
-   Il supporto degli oggetti Criteri di gruppo per la configurazione delle impostazioni WPA nei client WLAN sarà disponibile solo in Windows Server 2003 Service Pack 1.
  
-   Il supporto client per sistemi diversi da Windows XP potrebbe non essere disponibile. Sebbene Microsoft fornirà probabilmente il supporto WPA per Pocket PC 2003, è possibile che Windows 2000 e altri client Microsoft non vengano supportati. Il supporto WPA per questi client potrebbe essere prodotto da fornitori non Microsoft.
  
-   In alcuni casi non è possibile aggiornare le apparecchiature WLAN esistenti, ovvero punti di accesso senza fili e schede di rete client, per supportare WPA. Anche il costo di acquisto e di installazione di nuovo hardware potrebbe essere proibitivo.
  
Il supporto degli oggetti Criteri di gruppo e di Pocket PC 2003 per WPA verrà rilasciato a breve, lasciando la possibilità di scegliere o meno WPA. Fino ad allora, il WEP dinamico combinato con l'autenticazione 802.1X continuerà a garantire un livello di protezione estremamente elevato per le reti WLAN e costituirà la scelta predefinita per questa soluzione. Per ulteriori informazioni su WPA, vedere la sezione "Riferimenti" alla fine di questo capitolo.
  
#### Migrazione da una rete WLAN esistente
  
Se nell'organizzazione è già attiva una rete senza fili, è consigliabile scegliere una strategia di migrazione per ridurre al minimo i problemi per gli utenti e l'ambiente.
  
In molte organizzazioni sono disponibili reti WLAN basate sullo standard 802.11 che funzionano senza crittografia o autenticazione di rete. Altre organizzazioni hanno implementato il WEP statico mediante crittografia con chiavi condivise, spesso associata al filtraggio degli indirizzi MAC (Media Access Control).
  
Il processo di migrazione da uno di questi scenari a una rete WLAN protetta basata sullo standard 802.1X include le seguenti operazioni:
  
1.  **Distribuzione di certificati nei server IAS:** per i dettagli relativi alla distribuzione di certificati in un server IAS,fare riferimento al capitolo 4, "Creazione dell'autorità di certificazione della rete", di questa guida.
  
2.  **Configurazione dei criteri di accesso remoto della rete senza fili nei server IAS:** la procedura di configurazione dei criteri di accesso remoto della rete senza fili è descritta nel capitolo 5, "Creazione dell'infrastruttura di protezione per LAN senza fili", di questa guida.
  
3.  **Distribuzione di una configurazione WLAN per la nuova rete WLAN nei computer client:** per la nuova rete basata sullo standard 802.1X è necessario un nuovo identificatore del set di servizi (SSID). Le impostazioni per la nuova rete WLAN possono essere distribuite dall'oggetto Criteri di gruppo di Active Directory. I criteri di gruppo WLAN devono essere distribuiti prima della riconfigurazione dei punti di accesso senza fili per garantire che i computer portatili con accesso esclusivamente occasionale alla rete LAN ricevano la configurazione. Questa procedura è descritta nel capitolo 6, "Configurazione dei client delle reti LAN senza fili".
  
4.  **Configurazione di punti di accesso senza fili per la protezione 802.1X:** questa operazione viene eseguita in maniera ottimale procedendo per aree specifiche, ad esempio all'interno di un edificio o di un gruppo di edifici, e viene effettuata al di fuori dell'orario di lavoro o avvisando con il dovuto anticipo gli utenti riguardo a una possibile interruzione della rete WLAN. È consigliabile creare voci client RADIUS per IAS relative a tutti i punti di accesso della sede, configurare i punti di accesso con gli indirizzi dei server IAS per le voci RADIUS di tali punti e disattivare infine i punti di accesso per consentire solo client autenticati in base allo standard 802.1X. Per facilitare il ripristino, è possibile eseguire il backup delle impostazioni dei punti di accesso senza fili prima di iniziare la procedura, in modo che sia possibile ripristinarle in caso di emergenza.
  
Questo tipo di distribuzione riduce al minimo i danni per gli utenti e consente di ripristinare facilmente una sede se si verificano problemi. Durante la transizione, gli utenti incontreranno inevitabilmente alcuni problemi; pertanto è consigliabile tenerli informati riguardo alla migrazione e prepararsi a gestire un numero di chiamate al supporto tecnico superiore al normale.
  
Come per tutte le strategie di migrazione, è essenziale un'accurata attività di pianificazione e di testing. Senza un'accurata attività di testing a scopo di prevenzione, le operazioni di configurazione dei computer client e dei punti di accesso senza fili possono causare problemi all'ambiente.
  
La pianificazione dettagliata della migrazione da reti WLAN non protette e con WEP statico o da schemi di protezione per reti WLAN proprietarie non è inclusa in questa guida. Il principio di base di queste reti è analogo e viene seguito lo schema sopra indicato. Se tuttavia è necessaria ulteriore assistenza per la pianificazione della migrazione, rivolgersi al partner Microsoft o contattare la filiale Microsoft locale affinché agisca da intermediaria con il partner Microsoft di zona o con Microsoft Consulting Services.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Scalabilità per organizzazioni di maggiori dimensioni
  
In questa sezione vengono riportate alcune considerazioni fondamentali relative all'utilizzo di questa soluzione in organizzazioni di grandi dimensioni, ad esempio una società con varie migliaia di utenti. L'utilizzo di PEAP e dell'autenticazione tramite password nell'organizzazione è descritta in dettaglio nell'appendice A, "Utilizzo di PEAP nell'impresa".
  
#### Posizionamento del server IAS
  
Se aumenta il numero di posizioni che supportano le reti WLAN, è necessario decidere le modalità con cui i servizi per punti di accesso senza fili verranno forniti dai server IAS. Esistono sostanzialmente due approcci:
  
-   **Utilizzo di un numero limitato di server IAS centrali:** utilizzare un numero limitato di server IAS centrali per gestire tutto il traffico di autenticazione WLAN (è probabile che due server siano sufficienti). È necessario verificare che le connessioni WAN tra gli uffici periferici e i server IAS includano capacità di recupero.
  
-   **Distribuzione dei server IAS in ogni ufficio:** esiste un limite minimo per le dimensioni di un ufficio oltre al quale questo approccio risulta economicamente vantaggioso ma, in generale, qualsiasi ufficio sufficientemente grande da includere un controller di dominio interno può disporre localmente di IAS, che in genere viene installato appunto nel controller di dominio.
  
Sebbene l'investimento per le capacità di recupero della rete possa sembrare una scelta che comporta costi eccessivi, è necessario confrontarlo con il costo di amministrazione dovuto alla gestione dei vari server IAS distribuiti. Anche se IAS è installato nello stesso server fisico di un controller di dominio esistente, sarà necessario affrontare alcuni costi di gestione per ogni istanza di IAS. In pratica, la maggior parte delle organizzazioni di grandi dimensioni utilizza un ibrido tra i due approcci nei seguenti modi:
  
-   Centralizzazione dei server IAS e investimento nelle capacità di recupero della rete WAN, se possibile
  
-   Distribuzione di IAS negli uffici in cui non è possibile ottenere capacità di recupero della rete WAN o i relativi costi sono proibitivi
  
-   Utilizzo di reti WLAN con WPA a chiave già condivisa (PSK) per uffici estremamente piccoli con connettività scadente o per le abitazioni dei dipendenti.
  
La strategia basata su server IAS centralizzati è stata illustrata in precedenza nella sezione "Posizionamento del server IAS" di questo capitolo. L'utilizzo di un controller di dominio locale e di IAS in una filiale è illustrato nella figura seguente, che mostra un ufficio periferico di maggiori dimensioni collegato tramite una rete WAN alla sede centrale illustrata in precedenza nella figura 2.4.
  
[![](images/Dd536231.PEAP_207(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536231.peap_207_big(it-it,technet.10).gif)
  
**Figura 2.7 Filiale di dimensioni maggiori con controller di dominio e server IAS**
  
In questa filiale, i punti di accesso sono configurati per l'utilizzo del server IAS locale come server RADIUS primario e di uno dei server IAS della sede centrale come server RADIUS secondario. Di conseguenza è possibile autenticare i client WLAN anche in caso di problemi al server IAS o alla connettività WAN.
  
Se tuttavia si dispone di una connettività WAN con capacità di recupero (ad esempio, più collegamenti WAN con provider differenti), non è vantaggioso distribuire server aggiuntivi nelle filiali, in quanto in tal modo si ottiene solo una maggiore complessità e un ulteriore sovraccarico di gestione.
  
#### Domini multipli
  
La progettazione di base della soluzione assicura una scalabilità trasparente per insiemi di strutture multidominio. I punti fondamentali da considerare in caso di utilizzo della soluzione con più domini sono i seguenti:
  
-   I server IAS devono essere registrati in ogni dominio che include utenti o computer che accederanno alla rete WLAN. Per i dettagli, fare riferimento al capitolo 5 "Creazione dell'infrastruttura di protezione per LAN senza fili".
  
-   Gli oggetti Criteri di gruppo per le impostazioni del server e della richiesta di certificato automatica devono essere importati in ogni dominio in cui sono installati i server IAS. La relativa procedura è descritta in dettaglio nel capitolo 3, "Predisposizione dell'ambiente", e nel capitolo 4, "Creazione dell'autorità di certificazione della rete".
  
-   L'oggetto Criteri di gruppo che controlla le impostazioni della rete WLAN nei computer client deve essere creato in ogni dominio che include computer client che avranno accesso alla rete WLAN. Per ulteriori dettagli su questo argomento, fare riferimento al capitolo 6, "Configurazione dei client delle reti LAN senza fili".
  
-   I gruppi di protezione utilizzati da IAS per filtrare i criteri di accesso remoto devono essere configurati in modo da supportare più domini.
  
I primi tre elementi non richiedono spiegazioni e la relativa procedura di configurazione per più domini è descritta negli ultimi capitoli. L'utilizzo dei gruppi di protezione è leggermente più complesso ed è descritto in dettaglio nella sezione seguente.
  
##### Utilizzo dei gruppi di protezione in più domini
  
Nella tabella seguente viene illustrata l'organizzazione dei gruppi di protezione in un insieme di strutture multidominio, descritta nella sezione "Modello di amministrazione per utenti e computer di reti WLAN".
  
**Tabella 2.8: Gruppi di accesso senza fili per consentire l'accesso a tutti gli utenti e i computer**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Gruppo universale di livello superiore (accesso concesso nel criterio di accesso remoto)</th>
<th style="border:1px solid black;" >Membri di primo livello
(Gruppi globali di dominio)</th>
<th style="border:1px solid black;" >Membri di secondo livello
(Gruppi globali di dominio)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">DomPrinc\Accesso LAN senza fili</td>
<td style="border:1px solid black;">DomUtente1\Utenti LAN senza fili</td>
<td style="border:1px solid black;">DomUtente1\Domain Users</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DomPrinc\Accesso LAN senza fili</td>
<td style="border:1px solid black;">DomUtente2\Utenti LAN senza fili</td>
<td style="border:1px solid black;">DomUtente2\Domain Users</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DomPrinc\Accesso LAN senza fili</td>
<td style="border:1px solid black;">DomUtente3\Utenti LAN senza fili</td>
<td style="border:1px solid black;">DomUtente3\Utente1<br />
DomUtente3\Utente2<br />
DomUtente3\Utente2</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DomPrinc\Accesso LAN senza fili</td>
<td style="border:1px solid black;">DomUtente1\Computer LAN senza fili</td>
<td style="border:1px solid black;">DomUtente1\Computer del dominio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DomPrinc\Accesso LAN senza fili</td>
<td style="border:1px solid black;">DomUtente2\Computer LAN senza fili</td>
<td style="border:1px solid black;">DomUtente2\Computer del dominio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DomPrinc\Accesso LAN senza fili</td>
<td style="border:1px solid black;">DomUtente3\Computer LAN senza fili</td>
<td style="border:1px solid black;">DomUtente3\Computer HR<br />
DomUtente3\Computer reparto finanziario</td>
</tr>
</tbody>
</table>
 

Nella tabella è illustrata la stessa disposizione con nidificazione dei gruppi riportata nelle tabelle della sezione "Modello di amministrazione per utenti e computer di reti WLAN". I membri del gruppo elencato nella prima colonna sono riportati nella seconda colonna; i membri dei gruppi elencati nella seconda colonna sono riportati nella terza colonna.

Nell'esempio della tabella vengono utilizzati nomi fittizi. Ad esempio, DomPrinc è il nome del dominio in cui sono installati i server IAS, mentre DomUtente1 e DomUtente2 sono altri domini contenenti utenti e computer a cui è consentito l'accesso alla rete WLAN.

Nell'esempio indicato, l'accesso alla rete WLAN è consentito implicitamente a tutti gli utenti e i computer di DomUtente1 e DomUtente2, in quanto i gruppi Domain Users e Computer del dominio di tali domini sono membri dei gruppi Utenti LAN senza fili e Computer LAN senza fili dello stesso dominio. Tuttavia, gli utenti di DomUtente3 vengono aggiunti singolarmente al gruppo Utenti LAN senza fili di DomUtente3. L'accesso viene consentito ai computer tramite i gruppi di protezione delle unità aziendali, ad esempio tutti i computer del reparto risorse umane.

I gruppi globali di ogni dominio, ovvero Utenti LAN senza fili e Computer LAN senza fili, vengono quindi aggiunti come membri del gruppo universale Accesso LAN senza fili. A tutti i membri di quest'ultimo gruppo viene consentito l'accesso alla rete WLAN nei criteri di accesso remoto IAS.

#### Architettura PKI

Come indicato nella precedente sezione "Come ottenere i certificati per i server IAS", molte applicazioni possono utilizzare i certificati. È importante tenere presente che, sebbene risulti appropriata per questa soluzione, una CA autonoma difficilmente è in grado di soddisfare le varie esigenze delle organizzazioni di maggiori dimensioni. Prima di implementare la CA descritta in questa guida, valutare attentamente altri possibili utilizzi futuri dei certificati, nonché architetture PKI alternative più adatte a tali scenari.

Per ulteriori informazioni sulla pianificazione dell'architettura PKI, fare riferimento al capitolo 4 "Designing the Public Key Infrastructure" (in inglese) nella guida alla soluzione correlata *Securing Wireless LANs — A Certificate Services Solution*. Sebbene sia più avanzata rispetto alla CA di questa guida, l'architettura PKI descritta in tale soluzione è comunque relativamente semplice: ad esempio, utilizza solo due CA. Tuttavia è stata progettata come modello di base per una gamma molto più ampia di esigenze relative ai certificati.

Se si decide di implementare un'architettura PKI più avanzata di questo tipo, è comunque possibile utilizzare le linee guida riportate nel capitolo 4 di questa guida, "Creazione dell'autorità di certificazione della rete". Tuttavia, è consigliabile apportare le seguenti modifiche alle istruzioni indicate in tale capitolo:

-   Installare la CA nel relativo server interno anziché in un controller di dominio.

-   Utilizzare Windows Server 2003, Enterprise Edition per garantire una maggiore flessibilità in futuro.

-   Utilizzare la registrazione automatica di Windows Server 2003 anziché il servizio Richiesta automatica certificati. Per istruzioni relative all'utilizzo della registrazione automatica, vedere la documentazione del prodotto Windows Server 2003, Enterprise Edition.

-   Utilizzare il modello di certificato "Server RAS e IAS" o creare un tipo di certificato utente per i certificati del server IAS anziché utilizzare il modello "Computer".

    **Nota:** nel nome del modello di certificato, "RAS" è l'acronimo di Remote Access Service, Servizio di Accesso remoto.

Le istruzioni per eseguire tali operazioni sono contenute nella sezione "Public Key Infrastructure" (in inglese) della documentazione del prodotto Windows Server 2003 e nel capitolo 4 "Designing the Public Key Infrastructure", nel capitolo 7 "Building the Public Key Infrastructure" e nel capitolo 9 "Implementing Wireless LAN Security" (in inglese) della guida alla soluzione correlata *Securing Wireless LANs — A Certificate Services Solution*.

[](#mainsection)[Inizio pagina](#mainsection)

### Variazioni nell'architettura della soluzione

In questa sezione vengono descritte alcune variazioni rispetto alla progettazione di base. Nelle sottosezioni seguenti vengono riportate le possibili alternative per le impostazioni di protezione predefinite della soluzione, utilizzando i server IAS per l'autenticazione dell'accesso cablato e remoto, creando reti WLAN guest per i visitatori e distribuendo reti WLAN in ambienti di dimensioni estremamente ridotte quali le abitazioni.

#### Opzioni di protezione per il WEP dinamico

Nella precedente sezione "Funzionamento dell'autenticazione 802.1X con PEAP e password" di questo capitolo è stato descritto l'utilizzo della crittografia basata sul WEP dinamico nella soluzione. La protezione del WEP dinamico si basa sul rinnovo delle chiavi di crittografia a intervalli regolari per ostacolare gli attacchi noti al protocollo WEP. IAS assicura che le chiavi di ogni client senza fili vengano rinnovate a intervalli impostati utilizzando un timeout di sessione client, che forza il client ad eseguire la riautenticazione nella rete WLAN.

Se si riduce il valore del timeout di sessione, la protezione aumenta ma è possibile che l'affidabilità e le prestazioni vengano ridotte. Un timeout di 60 minuti offre una protezione adeguata per la maggior parte dei casi e sicuramente indicata per reti basate sullo standard 802.11b a 11 Mbps. Di norma, in 60 minuti i client senza fili non trasmettono mai una quantità di dati sufficiente per consentire a un pirata informatico di recuperare una chiave WEP.

Le ricerche più recenti dimostrano che le chiavi WEP statiche possono essere recuperate tramite l'acquisizione di un numero di pacchetti di rete con la stessa chiave compreso tra 1 e 5 milioni. Tali ricerche sono documentate nel white paper tecnico "Using the Fluhrer, Mantin, and Shamir Attack to Break WEP" (in inglese) di Adam Stubblefield, John Ioannidis e Aviel D. Rubin che operano presso AT&T Labs (vedere il riferimento alla fine di questo capitolo).

**Nota:** il numero di 1 milione di pacchetti è stato ottenuto sottoponendo a test le reti WLAN con WEP statico mediante l'utilizzo di chiavi relativamente deboli (una "frase password memorizzabile dall'utente") e non è applicabile direttamente alle reti WLAN con WEP dinamico. A differenza delle tipiche reti WLAN con WEP statico, il WEP dinamico utilizza chiavi di crittografia casuali avanzate e limita l'efficacia di una delle ottimizzazioni delle chiavi utilizzata dagli autori. In termini di protezione, tuttavia, è preferibile applicare misure preventive in eccesso e utilizzare il dato relativo al peggiore degli scenari, ovvero 1 milione di pacchetti, per valutare i rischi relativi alla protezione di reti WLAN con WEP dinamico.

In genere, ipotizzando che le dimensioni di un pacchetto medio corrispondano a 500 byte, un milione di pacchetti equivale a circa 500 MB di dati. Per la protezione dei dati crittografati, è necessario impostare il timeout di sessione in modo da forzare il rinnovo della chiave di ogni client prima che questo invii una quantità di dati superiore.

Per l'utilizzo tipico della rete client, ad esempio per posta elettronica, browser Web e condivisione di file, la velocità media di trasferimento dei dati è di 160 Kbps o inferiore. Con questa velocità di trasferimento e supponendo che le dimensioni di ogni pacchetto corrispondano a 500 byte, un pirata informatico impiegherebbe circa 7 ore per acquisire una quantità di dati sufficiente per il recupero della chiave di crittografia corrente del client.

**Nota:** in condizioni di laboratorio, è possibile trasmettere 500 Mb in meno di 7 ore, ovvero in 10 minuti in una rete WLAN a 11 Mbps o meno di 3 minuti in un rete WLAN a 54 Mbps. In tal caso, tuttavia, si suppone che un singolo client utilizzi in modo esclusivo la rete WLAN e invii un flusso di pacchetti UPD non riconosciuti in un'unica direzione. Questo scenario o qualsiasi scenario analogo è estremamente improbabile per una rete WLAN reale.

Un timeout di sessione di 60 minuti è più che sufficiente per la maggior parte delle organizzazioni. Di conseguenza, un client medio è in grado di trasmettere circa 150.000 pacchetti prima dell'aggiornamento di ogni chiave, ovvero una quantità nettamente inferiore rispetto al limite di 1 milione di pacchetti necessario per la violazione della chiave WEP. Tuttavia potrebbe essere necessario utilizzare un valore di timeout inferiore per uno o più dei seguenti motivi:

-   Se si dispone di client senza fili che inviano o ricevono grandi quantità di dati sulla rete WLAN in periodi di tempo relativamente brevi, è consigliabile impostare il timeout su una durata inferiore al tempo impiegato da un singolo client per inviare e ricevere 75 MB (che corrispondono a meno del 20 percento della quantità di dati necessaria per il recupero di una chiave WEP, lasciando quindi un margine di sicurezza maggiore).

-   Se si utilizzano reti WLAN basate sullo standard 802.11a o 802.11g a 54 Mbps, risulta più facile trasmettere un maggior numero di pacchetti in un tempo specifico. In queste reti WLAN più veloci, potrebbe essere necessario ridurre il timeout di sessione a 15 minuti.

-   Se le capacità delle tecniche di violazione delle chiavi WEP migliorano in modo significativo, sarà necessaria una minore quantità di dati per recuperare tali chiavi. Se ad esempio viene scoperta una nuova tecnica crittoanalitica che consente di recuperare le chiavi con soli 100.000 pacchetti, sarà necessario ridurre il timeout di sessione per impedire che i client senza fili raggiungano questo limite prima del rinnovo delle chiavi di crittografia.

-   Per esigenze di protezione specifiche, si potrebbe decidere di ridurre il timeout oltre il limite che consente anche la riuscita di attacchi teorici al WEP (10 minuti o 3 minuti, come descritto nella nota precedente). Tuttavia è necessario valutare questa decisione in base agli avvertimenti riportati più avanti in questa sezione. Se la riservatezza dei dati è tale da richiedere questo livello di precauzione, è consigliabile valutare seriamente l'opportunità di utilizzare solo la protezione dei dati WPA nella rete WLAN e di utilizzare la protezione IP per proteggere i dati durante il trasferimento su reti LAN cablate.

Gli svantaggi principali della riduzione del timeout di sessione sono due:

-   **Minore affidabilità della rete WLAN** **:** timeout di sessione WLAN estremamente brevi possono compromettere la riautenticazione dei client e determinarne la disconnessione dalla rete WLAN qualora la comunicazione con un controller di dominio o un server IAS sia stata temporaneamente interrotta.

-   **Aumento del carico dei server IAS:** più breve è il timeout e maggiore è la frequenza con cui il client deve eseguire la riautenticazione in un server IAS o in un controller di dominio. Di conseguenza, il carico dei server IAS e dei controller di dominio aumenta. Poiché IAS memorizza nella cache le sessioni di autenticazione client, di norma l'aumento del carico sarà significativo solo per le organizzazioni con un numero elevato di client senza fili o in caso di utilizzo di valori estremamente bassi per il timeout di sessione.

#### Altri servizi di accesso alla rete

La progettazione RADIUS utilizzata in questa soluzione può fornire servizi di autenticazione, autorizzazione e accounting per altri server di accesso alla rete, quali l'autenticazione di rete cablata basata sullo standard 802.1X e l'autenticazione di accesso remoto e VPN.

##### Autenticazione di rete cablata basata sullo standard 802.1X

L'autenticazione di rete cablata basata sullo standard 802.1X è la più semplice, in quanto non richiede alcuna modifica della progettazione RADIUS di base. Le organizzazioni dotate di un'infrastruttura di rete cablata ad ampia distribuzione potrebbero incontrare difficoltà nel controllare l'utilizzo non autorizzato della rete aziendale. Ad esempio, spesso è difficile impedire che i visitatori colleghino i computer portatili o che i dipendenti aggiungano computer non autorizzati alla rete. Alcune parti della rete, ad esempio i centri dati, possono essere designate come aree ad alta protezione e in queste reti è consigliabile consentire solo i dispositivi autorizzati, determinando anche l'esclusione dei dipendenti con computer aziendali.

La modalità di integrazione della soluzione di accesso a una rete cablata con la progettazione è illustrata nella figura seguente.

[![](images/Dd536231.PEAP_208(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536231.peap_208_big(it-it,technet.10).gif)

**Figura 2.8 Utilizzo dell'autenticazione cablata 802.1X**

Nella casella con i margini in grassetto sono rappresentati i componenti cablati basati sullo standard 802.1X, mentre le altre caselle contengono i servizi rilevanti. Confrontare questa figura con la figura 2.4. In questa figura è illustrata solo la sede centrale.

Gli switch di rete in grado di supportare la tecnologia 802.1X svolgono un ruolo identico a quello dei punti di accesso senza fili all'interno della soluzione di base e possono sfruttare la stessa infrastruttura RADIUS per autenticare i client e autorizzare in modo selettivo l'accesso al segmento di rete appropriato. Questo include i tipici vantaggi della centralizzazione della gestione degli account nella directory aziendale, lasciando tuttavia i criteri di accesso alla rete sotto il controllo dell'amministratore della protezione di rete.

##### Autenticazione della connessione remota e VPN

Un altro servizio di accesso alla rete che potrebbe utilizzare i componenti RADIUS è la connessione remota e VPN. Specialmente nelle organizzazioni di grandi dimensioni, è probabile che sia necessario apportare alcune aggiunte alla progettazione, ad esempio l'aggiunta di proxy RADIUS. La soluzione estesa è illustrata nella figura seguente.

[![](images/Dd536231.PEAP_209(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536231.peap_209_big(it-it,technet.10).gif)

**Figura 2.9 Estensione del componente RADIUS per il supporto della connessione VPN**

In questa variante, i server VPN svolgono lo stesso ruolo funzionale dei punti di accesso senza fili all'interno della progettazione di base. Questi passano le richieste di autenticazione dei client all'infrastruttura RADIUS. È possibile ottenere che le richieste RADIUS vengano passate direttamente ai server IAS interni. Tuttavia, molte organizzazioni desiderano aggiungere un ulteriore livello di proxy RADIUS fornendo un livello di protezione aggiuntivo e instradando le richieste ai server IAS interni.

Analogamente alla protezione di rete cablata, questa soluzione presenta gli stessi vantaggi offerti dal riutilizzo dell'infrastruttura esistente e dalla centralizzazione della gestione degli account. È possibile apportare ulteriori miglioramenti, ad esempio l'utilizzo dell'autenticazione degli utenti basata su smart card. La soluzione VPN interna di accesso remoto fornita da Microsoft per il personale della propria società utilizza virtualmente la stessa architettura VPN e RADIUS con smart card per l'autenticazione degli utenti.

L'accesso remoto funziona in modo analogo, utilizzando la funzionalità server di connessione remota anziché le funzioni VPN di Routing e Accesso remoto disponibili in Windows Server.

Il vantaggio principale dell'utilizzo di IAS per connessioni sia VPN che remote consiste nella possibilità di utilizzare il controllo per la quarantena dell'accesso remoto di Windows Server 2003. Tale controllo utilizza le funzionalità del server di Routing e Accesso remoto (RAS) e quelle avanzate del client di accesso remoto di Windows (Connection Manager) per consentire o negare l'accesso in base allo stato di protezione del computer client. Vengono eseguiti controlli sul client nella fase di connessione, ad esempio verificando che il client disponga di software antivirus aggiornato o esegua una versione del sistema operativo approvata dall'azienda. Se il client non riesce a eseguire questi controlli, il server RADIUS nega l'accesso del client alla rete. Pertanto è possibile che l'accesso venga negato anche a un utente o a un computer regolarmente autenticato nel caso in cui rappresenti un possibile pericolo per la protezione della rete aziendale.

Per ulteriori informazioni sulla funzionalità di quarantena di Windows Server 2003, vedere i riferimenti alla fine del capitolo.

#### Bootstrap dei computer client

La maggior parte dei computer senza fili dispone anche di un'interfaccia di rete cablata, che facilita relativamente l'aggiunta dei client al dominio e il download delle impostazioni WLAN prima della connessione alla rete WLAN. Tuttavia, questo non avviene in tutti i casi. I dispositivi portatili sono già senza fili e non dispongono di schede di rete cablate. Questo pone il problema di eseguire il bootstrap di un client prima della connessione alla rete WLAN, in quanto questo computer non dispone delle impostazioni e delle credenziali necessarie per tale connessione.

Il problema si complica ulteriormente se un'organizzazione decide di utilizzare la protezione 802.1X sia cablata che senza fili, poiché un client non può connettersi a una rete LAN cablata senza disporre prima delle credenziali e delle impostazioni corrette.

Se non è possibile utilizzare una rete LAN cablata per recuperare le impostazioni e le credenziali, per eseguire il bootstrap di un computer client esistono due approcci principali:

-   Utilizzare una rete LAN guest e una connessione autenticata alternativa, ad esempio una connessione VPN, per ottenere le credenziali e le impostazioni.

-   Configurare manualmente i client.

Attualmente, Microsoft supporta solo la seconda opzione. Microsoft rilascerà un servizio di fornitura adatto per l'utilizzo di una rete WLAN "guest" al fine di eseguire il bootstrap della configurazione WLAN del computer client. Fino ad allora, la configurazione manuale rappresenta il metodo più semplice per questo scopo. Per configurare le impostazioni del computer client e aggiungerlo al dominio, è necessario che l'addetto alla configurazione sia un membro del gruppo Admistrators locale del computer.

**Per eseguire il bootstrap di un computer tramite la configurazione manuale:**

1.  Configurare manualmente le impostazioni della rete WLAN per l'identificatore SSID corretto.

2.  Connettersi alla rete WLAN tramite credenziali di dominio dell'utente valide. Non sarà possibile connettersi con l'account del computer fino a quando questo non verrà aggiunto al dominio.

3.  Aggiungere il computer al dominio e quindi riavviarlo.

4.  Dopo il riavvio, il client potrà connettersi alla rete WLAN utilizzando l'account del computer e scaricare le impostazioni dell'oggetto Criteri di gruppo WLAN. Queste impostazioni si limiteranno a sovrascrivere quelle configurate manualmente.

5.  A questo punto, sia l'utente che il computer possono connettersi alla rete WLAN.

#### Ambienti SOHO

Potrebbe essere necessario distribuire le reti WLAN in aree in cui non è possibile o conveniente autenticare gli utenti tramite l'infrastruttura IAS, ad esempio le postazioni degli utenti che lavorano regolarmente a casa o in piccoli uffici con connessioni estremamente inaffidabili o connessioni lente a banda larga alla rete aziendale principale.

In precedenza, l'unica soluzione a questo problema consisteva nel configurare la protezione con WEP statico sperando che nessun pirata informatico fosse seriamente intenzionato ad eseguire attacchi alla rete WLAN. Attualmente è preferibile utilizzare WPA in modalità PSK. Tutti i punti di accesso senza fili certificati Wi-Fi sono dotati della protezione WPA, anche se è possibile che questa non venga supportata dai punti di accesso precedenti. È consigliabile verificare che i punti di accesso supportino la modalità PSK per WPA, dato il valore di protezione aggiuntivo che offre. A differenza del WEP statico, la chiave di autenticazione WPA non è recuperabile dal traffico crittografato; pertanto, per un pirata informatico è molto più difficile violare la rete. È consigliabile verificare inoltre che gli utenti siano preparati a utilizzare chiavi WPA avanzate e a modificarle regolarmente e che siano a conoscenza delle implicazioni di protezione derivanti dalla mancata osservanza di questo requisito. Per implementare la modalità PSK di WPA, sono necessari un punto di accesso senza fili, schede di rete senza fili e un sistema operativo client che supporta WPA, ad esempio Windows XP. Non sono necessari server RADIUS o un'altra infrastruttura server.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

All'inizio del capitolo è stata presentata una descrizione relativa alla protezione delle reti LAN senza fili basate sullo standard 802.1X. Per illustrare in dettaglio la progettazione, è stata fornita una panoramica dell'organizzazione di destinazione della soluzione insieme ai criteri di progettazione fondamentali relativi alla soluzione per reti WLAN dell'organizzazione. In seguito, sono stati descritti gli aspetti principali della progettazione scelta per la rete WLAN. Nella progettazione sono stati inclusi la rete, il posizionamento e la configurazione dei server IAS, l'utilizzo dei certificati e i diversi tipi di client senza fili. Sono stati indicati anche i punti principali della migrazione da una rete WLAN esistente.

Nelle due sezioni alla fine del capitolo sono state descritte variazioni importanti rispetto alla progettazione di base. In primo luogo, è stata descritta la procedura di scalabilità della soluzione per organizzazioni di maggiori dimensioni, fornendo inoltre le istruzioni relative alla gestione delle differenze principali rispetto alla soluzione di base. In seguito, è stato illustrato l'utilizzo della stessa infrastruttura di autenticazione di base al fine di supportare altri servizi di rete quali l'accesso remoto, la connessione VPN e la protezione di rete cablata; sono state inoltre indicate le soluzioni possibili per i problemi di bootstrap dei client e la distribuzione delle reti WLAN in ambienti SOHO.

Nel capitolo successivo ha inizio l'implementazione della soluzione, consentendo di preparare la rete, Active Directory e la protezione dei server per la distribuzione dei componenti WLAN.

[](#mainsection)[Inizio pagina](#mainsection)

### Riferimenti

Questa sezione contiene rimandi a informazioni supplementari importanti e ad altro materiale di riferimento attinente al contenuto di questo capitolo.

-   Per ulteriori dettagli sull'autenticazione 802.1X, vedere "IEEE 802.1X Authentication for Wireless Connections" (in inglese) all'indirizzo:

    <http://technet.microsoft.com/en-us/library/bb878016.aspx>

-   Per ulteriori informazioni sull'utilizzo di PEAP con le password, vedere "PEAP with MS-CHAP Version 2 for Secure Password-based Wireless Access" (in inglese) al seguente indirizzo:

    <http://technet.microsoft.com/library/bb878077.aspx>

-   Per ulteriori dettagli sull'autenticazione 802.1X, l'interazione tra client, i punti di accesso senza fili e i server RADIUS, nonché per i consigli relativi alle funzionalità supportate dai punti di accesso senza fili, vedere "Recommendations for IEEE 802.11 Access Points" (in inglese) al seguente indirizzo:

    [http://www.microsoft.com/whdc/archive/AccessPts.mspx](http://www.microsoft.com/whdc/archive/accesspts.mspx)

-   Per ulteriori informazioni sulla progettazione di reti LAN senza fili, inclusi i servizi DHCP e i layout dei punti di accesso senza fili, vedere il capitolo "Deploying a Wireless LAN" (in inglese) nel *Windows Server 2003 Deployment Kit* al seguente indirizzo:

    <http://technet.microsoft.com/en-us/library/cc780901.aspx>

-   Per ulteriori informazioni sulla protezione di IAS, vedere la documentazione del prodotto Windows Server 2003 al seguente indirizzo:

    <http://technet.microsoft.com/en-us/library/cc783725.aspx>

-   Per ulteriori informazioni sulle funzionalità di Servizi certificati disponibili in Windows Server 2003, Enterprise Edition, vedere il white paper "PKI Enhancements in Windows XP Professional and Windows Server 2003" (in inglese) al seguente indirizzo:

    <http://technet.microsoft.com/en-us/library/bb457034.aspx>

    **Nota:** questo articolo è stato scritto prima del rilascio di Windows Server 2003 e pertanto i termini Windows .Net Server, Advanced Server e Standard Server vengono utilizzati rispettivamente in riferimento a Windows Server 2003, Enterprise Edition e Standard Edition.

-   Per ulteriori informazioni su Microsoft 802.1X Authentication Client per Windows 2000, vedere l'articolo della Knowledge Base "Using 802.1x Authentication on Computers Running Windows 2000" (in inglese) al seguente indirizzo:

    <http://support.microsoft.com/default.aspx?scid=313664>

-   Per ulteriori informazioni su WPA e sull'aggiornamento per la protezione WPA senza fili in Windows XP, vedere "Wi-Fi Protected Access (WPA) Overview" e "WPA Wireless Security Update" (in inglese) ai seguenti indirizzi:

    <http://technet.microsoft.com/library/bb878054.aspx>

    <http://support.microsoft.com/default.aspx?kbid=815485>

-   Per una descrizione dei problemi di protezione relativi al WEP, vedere il white paper tecnico "Weaknesses in the Key Scheduling Algorithm of RC4" (in inglese) di Scott Fluhrer, Itsik Mantin e Adi Shamir e il white paper tecnico "Using the Fluhrer, Mantin, and Shamir Attack to Break WEP" (in inglese) di Adam Stubblefield, John Ioannidis e Aviel D. Rubin. Tenere presente che in questi white paper viene illustrata la protezione del WEP statico e che, pertanto, le conclusioni riportate non sono direttamente applicabili alla reti WLAN con WEP dinamico. Il documento "Weaknesses in the Key Scheduling Algorithm of RC4" è disponibile al seguente indirizzo:

    <http://www.crypto.com/papers/others/rc4_ksaproc.pdf>

-   Il documento "Using the Fluhrer, Mantin, and Shamir Attack to Break WEP" (AT&T Technical Report) è disponibile al seguente indirizzo:

    <http://www.isoc.org/isoc/conferences/ndss/02/papers/stubbl.pdf>

-   Per ulteriori informazioni sul controllo per la quarantena dell'accesso alla rete, vedere “Guida alla pianificazione dell'implementazione di servizi di quarantena con la rete privata virtuale” all’indirizzo

    <http://technet.microsoft.com/it-it/library/dd548379.aspx>

-   Per informazioni sull'utilizzo di WPA per la protezione di reti WLAN SOHO, vedere "WPA Wireless Security for Home Networks" (in inglese) al seguente indirizzo:

    [http://download.microsoft.com/download/b/b/b/bbbb5a3c-1518-4c0a-910b-15a92902fe6d/XP80211Security.doc](http://download.microsoft.com/download/b/b/b/bbbb5a3c-1518-4c0a-910b-15a92902fe6d/xp80211security.doc)

**Scarica la soluzione completa**

[Protezione delle reti LAN senza fili con PEAP e password](http://go.microsoft.com/fwlink/?linkid=23481)

[](#mainsection)[Inizio pagina](#mainsection)
