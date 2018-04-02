---
TOCTitle: 'Guida alla creazione - Implementazione dell''infrastruttura di protezione per LAN senza fili'
Title: 'Guida alla creazione - Implementazione dell''infrastruttura di protezione per LAN senza fili'
ms:assetid: '381cbd10-e6a4-49f3-9ed8-9cdb60e898cb'
ms:contentKeyID: 20200790
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536190(v=TechNet.10)'
---

Capitolo 9: Implementazione dell'infrastruttura per la protezione di reti LAN senza fili
========================================================================================

Pubblicato: 10 novembre 2004 | Aggiornato: 24 novembre 2004

##### In questa pagina

[](#eiaa)[Introduzione](#eiaa)
[](#ehaa)[Foglio di lavoro per la pianificazione della rete WLAN 802.1X](#ehaa)
[](#egaa)[Preparazione dell'ambiente per una rete WLAN protetta](#egaa)
[](#efaa)[Configurazione e distribuzione di certificati di autenticazione WLAN.](#efaa)
[](#eeaa)[Configurazione dell'infrastruttura di accesso WLAN](#eeaa)
[](#edaa)[Abilitazione dell'accesso di utenti e computer alla rete WLAN](#edaa)
[](#ecaa)[Configurazione di AP senza fili per reti basate sullo standard 802.1X](#ecaa)
[](#ebaa)[Collaudo e verifica](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

Questo capitolo contiene informazioni dettagliate relative all'implementazione della protezione di reti LAN senza fili (WLAN) con il protocollo 802.1X basato su Microsoft® Windows Server™ 2003 e Microsoft Windows® XP Service Pack 1 (SP1). Le indicazioni contenute in questo capitolo includono la configurazione dei gruppi di protezione del servizio directory di Active Directory®, la distribuzione dei certificati X.509 per l'autenticazione WLAN, la modifica delle impostazioni del server del Servizio autenticazione Internet (IAS) di Microsoft, la distribuzione dei criteri di gruppo WLAN e i suggerimenti per la configurazione dei punti di accesso senza fili. Questo capitolo include tutte le impostazioni necessarie per implementare la protezione WLAN mediante lo standard 802.1X e EAP-TLS (Extensible Authentication Protocol-Transport Layer Security).

L'obiettivo di questo capitolo è di fornire una guida all'implementazione della progettazione della rete WLAN protetta descritta nel capitolo 6, “Progettazione della protezione di reti LAN senza fili mediante lo standard 802.1X". Il capitolo non intende illustrare i principi generali di 802.1X, EAP, RADIUS (Remote Authentication Dial-In User Service) o i dettagli sull'implementazione della rete WLAN protetta basata su 802.1X. Per una panoramica di molte di queste tecnologie, vedere l'articolo "Windows XP Wireless Deployment Technology and Component Overview" riportato nella sezione “Ulteriori informazioni” alla fine di questo capitolo.

Questo capitolo è correlato ai capitoli della Guida operativa e della Guida alla pianificazione relativi all'infrastruttura a chiave pubblica (PKI), RADIUS e WLAN. La Guida alla pianificazione spiega le motivazioni delle decisioni relative all'implementazione illustrate in questo capitolo. La Guida operativa descrive le attività e i processi necessari per la gestione dell'infrastruttura 802.1X. Prima di proseguire con gli argomenti del capitolo, si consiglia di leggere i capitoli relativi alla pianificazione. Prima di implementare le linee guida fornite in questo capitolo in un ambiente di produzione, è opportuno inoltre leggere e comprendere le implicazioni dei requisiti di supporto nel capitolo delle istruzioni operative.

#### Prima di iniziare

Questa sezione contiene elenchi di controllo che aiutano a valutare il grado di preparazione di un'azienda in merito all'implementazione della rete WLAN basata sullo standard 802.1X (in questo contesto, il termine "preparazione" si riferisce più all'aspetto logistico che a quello aziendale: le motivazioni aziendali che portano all'implementazione di questa soluzione sono trattate nei primi capitoli della Guida alla pianificazione).

##### Prima di iniziare

È necessario conoscere i concetti dello standard 802.1X e della relativa implementazione nei prodotti Microsoft più importanti, come Windows Server 2003 e Windows XP Service Pack 1. È inoltre consigliabile conoscere Windows Server 2003 o Windows 2000 nelle seguenti aree:

-   Concetti relativi ad Active Directory, tra cui la struttura e gli strumenti di Active Directory; la gestione di utenti, gruppi e altri oggetti Active Directory e l’uso dei criteri di gruppo.

-   Concetti alla base della protezione dei sistemi Windows, quali utenti, gruppi, controllo, elenchi di controllo di accesso (ACL) e utilizzo degli strumenti della riga di comando.

-   Conoscenza degli script dei file batch. Conoscenza di Windows Scripting Host e del linguaggio Microsoft Visual Basic® Scripting Edition (VBScript) per poter trarre il massimo vantaggio dagli script forniti, ma non è essenziale.

Prima di proseguire con gli argomenti del capitolo, è necessario aver letto anche i capitoli sulla pianificazione e avere compreso l’architettura e la progettazione della soluzione.

##### Prerequisiti organizzativi

È consigliabile consultare altri membri della propria azienda che dovrebbero essere coinvolti nell'implementazione di questa soluzione, quali:

-   Finanziatori dell'iniziativa

-   Personale addetto al controllo e alla protezione

-   Personale addetto a progettazione, amministrazione e operazioni di Active Directory

-   Personale addetto a progettazione, amministrazione e operazioni di desktop

-   Personale addetto a DNS (Domain Name System) e progettazione, amministrazione e operazioni di rete

##### Prerequisiti per l'infrastruttura IT

Il capitolo presuppone anche quanto segue:

-   Esiste già un'infrastruttura di dominio di Active Directory Windows Server 2003. Tutti gli utenti della soluzione 802.1X devono essere membri di un dominio all'interno dello stesso insieme di strutture di Active Directory.

    **Nota:** per ulteriori informazioni sulla compatibilità con versioni precedenti di Microsoft Windows, consultare l'appendice A, "Versioni di Windows supportate".

-   Non esiste una soluzione della rete WLAN basata sullo standard 802 .1X. Sebbene questa soluzione non escluda la possibilità di una distribuzione accanto a una soluzione WLAN 802.1X esistente, non fornisce istruzioni per effettuare l'integrazione in un'infrastruttura 802.1X esistente.

-   Un'infrastruttura PKI è stata distribuita come descritto nel capitolo 7, "Implementazione dell'infrastruttura a chiave pubblica" ed è pronta per eseguire la registrazione automatica del certificato.

-   Le infrastrutture di supporto come il protocollo DHC (Dynamic Host Configuration Protocol) e DNS devono essere installate e pronte per fungere da server per i client WLAN.

-   Due o più server con IAS come i server RADIUS descritti nel capitolo 8, "Implementazione dell'infrastruttura RADIUS." Un'ulteriore configurazione di questi server sarà disponibile in questo capitolo.

-   Una rete WLAN con client Windows XP Professional Service Pack 1 e punti di accesso senza fili compatibili con lo standard 802.1X con WPA o WEP (Wired Equivalent Privacy) da 128 bit e schede di interfaccia di rete (NIC) WLAN compatibili con lo standard 802.1X. Un'ulteriore configurazione di questi componenti sarà disponibile in questo capitolo.

#### Panoramica dei capitoli

Questo diagramma mostra il processo di implementazione della protezione WLAN utilizzando 802.1X come descritto in questo capitolo.

![](images/Dd536190.09fig9-1(it-it,TechNet.10).gif "Figura 9.1. Diagramma del processo di implementazione dell'infrastruttura 802.1X")

**Figura 9.1. Diagramma del processo di implementazione dell'infrastruttura 802.1X**

Questi passaggi rispecchiano l'organizzazione del capitolo e sono descritti nell'elenco seguente. Ciascuno di essi è costituito da attività di installazione o configurazione e dispone di procedure di verifica che consentono di controllare le operazioni eseguite prima di continuare con il passaggio successivo.

-   **Foglio di lavoro per la pianificazione della rete WLAN 802.1X** Sono elencate le informazioni di configurazione utilizzate in questo capitolo per configurare i vari componenti della rete WLAN 802.1X. È inclusa una tabella di informazioni che devono essere fornite dall'utente prima di iniziare l'implementazione delle linee guida fornite in questo capitolo.

-   **Preparazione dell'ambiente per una rete WLAN protetta** Viene descritta la preparazione dei gruppi di protezione di Active Directory necessari per configurare e gestire la rete WLAN 802.1X nel tempo. Vengono fornite, inoltre, raccomandazioni importanti per DHCP.

-   **Configurazione e distribuzione di certificati di autenticazione WLAN** Vengono descritte in dettaglio la creazione e la distribuzione di modelli di certificato X.509 richiesti per le autenticazioni WLAN 802.1X. È compresa anche la verifica della distribuzione.

-   **Configurazione dell'infrastruttura di accesso WLAN** Vengono descritte in dettaglio la creazione e la configurazione dei criteri di accesso remoto IAS per reti 802.1X e EAP-TLS. Sono incluse anche le AP come client RADIUS dei server IAS.

-   **Abilitazione dell'accesso di utenti e computer alla rete WLAN** Viene descritta la configurazione di autorizzazioni per utenti e computer tramite Active Directory per consentire l'accesso alla rete WLAN protetta. In questa sezione sono inclusi anche i passaggi per la creazione e la distribuzione di criteri di gruppo di Active Directory per configurare i client WLAN con le impostazioni 802.1X e 802.11 appropriate.

-   **Configurazione dei punti di accesso senza fili per reti 802.1X** Sono elencati gli argomenti che è necessario tenere in considerazione durante la configurazione di AP senza fili per reti basate sullo standard 802.1X.

-   **Collaudo e verifica**. Viene fornita una procedura che consente di testare la funzionalità della rete WLAN basata sullo standard 802.1X.

[](#mainsection)[Inizio pagina](#mainsection)

### Foglio di lavoro per la pianificazione della rete WLAN 802.1X

Nelle tabelle di questa sezione vengono elencati i parametri di configurazione utilizzati in questa soluzione. Devono essere considerati come un elenco di controllo quando si prendono le decisioni relative alla pianificazione.

Molti dei parametri riportati in queste tabelle vengono impostati manualmente come parte delle procedure documentate in questo capitolo. Molti parametri vengono impostati da uno script eseguito come parte di una procedura oppure viene fatto riferimento al parametro da uno script per completare un'altra configurazione o un'attività operativa.

**Nota:** gli script utilizzati nella Guida alla creazione vengono descritti in modo più dettagliato nel file ToolsReadme.txt allegato agli script.

#### Elementi di configurazione definiti dagli utenti

La tabella che segue elenca dei parametri specifici dell'azienda fittizia Woodgrove Bank. Prima di iniziare la procedura di configurazione, occorre accertarsi di aver raccolto o deciso le impostazioni equivalenti per la propria organizzazione di tutti gli elementi indicati nella sottostante tabella. Negli esempi dei comandi citati nell'intero capitolo vengono utilizzati i valori fittizi mostrati qui. È necessario sostituire tali valori fittizi con i valori adeguati alla propria organizzazione. I valori che è necessario sostituire sono indicati in corsivo.

**Tabella 9.1. Elementi di configurazione definiti dagli utenti**

 
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
<td style="border:1px solid black;">Nome di dominio DNS per la radice di strutture Active Directory</td>
<td style="border:1px solid black;"><em>woodgrovebank.com</em></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome NetBIOS del dominio</td>
<td style="border:1px solid black;"><em>WOODGROVEBANK</em></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome del server IAS primario</td>
<td style="border:1px solid black;"><em>HQ- IAS - 01</em></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome del server IAS secondario</td>
<td style="border:1px solid black;"><em>HQ - IAS - 02</em></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome del server IAS opzionale delle filiali</td>
<td style="border:1px solid black;"><em>BO - IAS - 03</em></td>
</tr>
</tbody>
</table>
  
#### Elementi di configurazione indicati dalla soluzione
  
Le impostazioni specificate in questa tabella non devono essere modificate, a meno che non sia necessario utilizzare un'impostazione diversa da quella della progettazione della soluzione. La modifica dei parametri di progettazione forniti è perfettamente accettabile, ma occorre essere consapevoli del fatto che così facendo ci si discosta dalla soluzione collaudata. Prima di modificare eventuali valori nelle procedure di configurazione o negli script forniti, assicurarsi di avere compreso a fondo le implicazioni della modifica che si intende apportare e le dipendenze che tale impostazione potrebbe avere.
  
**Tabella 9.2. Elementi di configurazione indicati dalla soluzione**

 
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
<td style="border:1px solid black;">[Account] Gruppo globale di Active Directory che controlla la distribuzione dei certificati di autenticazione utenti 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica autenticazione client - Certificato utente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] Nome precedente a Windows 2000 del gruppo globale di Active Directory che controlla la distribuzione dei certificati di autenticazione utenti 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica autenticazione client - Certificato utente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] Gruppo globale di Active Directory che controlla la distribuzione dei certificati di autenticazione computer 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica autenticazione client - Certificato computer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] Nome precedente a Windows 2000 del gruppo globale di Active Directory che controlla la distribuzione dei certificati di autenticazione computer 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica autenticazione client - Certificato computer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] Gruppo globale di Active Directory in cui sono inclusi server IAS che richiedono certificati di autenticazione 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica certificato di autenticazione server RAS e IAS</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] Nome precedente a Windows 2000 per il gruppo globale di Active Directory in cui sono inclusi server IAS che richiedono certificati di autenticazione 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica certificato di autenticazione server RAS e IAS</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] Gruppo globale di Active Directory in cui sono inclusi gli utenti a cui è concesso l'accesso alla rete senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Utenti senza fili</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] Nome precedente a Windows 2000 del gruppo globale di Active Directory in cui sono inclusi gli utenti a cui è concesso l'accesso alla rete senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Utenti senza fili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] Gruppo globale di Active Directory in cui sono inclusi i computer a cui è concesso l'accesso alla rete senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Computer senza fili</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] Gruppo globale di Active Directory in cui sono inclusi i computer a cui è concesso l'accesso alla rete senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Computer senza fili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] Gruppo universale di Active Directory in cui sono inclusi il gruppo Utenti senza fili e il gruppo Computer senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Accesso senza fili</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] Gruppo universale di Active Directory in cui sono inclusi il gruppo Utenti senza fili e il gruppo Computer senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Accesso senza fili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] Gruppo globale di Active Directory in cui sono inclusi i computer che richiedono la configurazione di proprietà di rete senza fili</td>
<td style="border:1px solid black;">Criteri di rete senza fili - Computer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] Gruppo globale di Active Directory in cui sono inclusi i computer che richiedono la configurazione di proprietà di rete senza fili</td>
<td style="border:1px solid black;">Criteri di rete senza fili - Computer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Certificati] Modello di certificato utilizzato per generare certificati per l'autenticazione client di utenti</td>
<td style="border:1px solid black;">Autenticazione client - Utente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Certificati] Modello di certificato utilizzato per generare certificati per l'autenticazione client di computer</td>
<td style="border:1px solid black;">Autenticazione client - Computer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Certificati] Modello di certificato utilizzato per generare certificati per l'autenticazione server eseguita da IAS</td>
<td style="border:1px solid black;">Autenticazione server RAS e IAS</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Scripts] Percorso degli script di installazione</td>
<td style="border:1px solid black;">C:\MSSScripts</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Config] Percorso dei file di backup della configurazione</td>
<td style="border:1px solid black;">D:\IASConfig</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Registri richieste] Posizione dei file registro di autenticazione e delle richieste di controllo IAS</td>
<td style="border:1px solid black;">D:\IASLogs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Criteri di accesso remoto] Nome criterio</td>
<td style="border:1px solid black;">Consenti accesso senza fili</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Criteri di gruppo] Nome oggetto Criteri di gruppo (GPO, Group Policy Object) di Active Directory</td>
<td style="border:1px solid black;">Criterio di rete senza fili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Criteri di gruppo] Criteri di rete senza fili all'interno dell'oggetto Criteri di gruppo (GPO, Group Policy Object)</td>
<td style="border:1px solid black;">Configurazione senza fili del computer client</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Preparazione dell'ambiente per una rete WLAN protetta
  
Prima di implementare la rete senza fili protetta basata sul protocollo 802.1X, è necessario ottimizzare l'infrastruttura di supporto nell'ambiente. L'infrastruttura di supporto include i server Active Directory e DHCP. Per informazioni dettagliate sulla pianificazione di una rete WLAN, vedere il capitolo "Deploying a Wireless LAN" (in inglese) del *Windows Server 2003 Deployment Kit* e altre risorse elencate nella sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
#### Creazione di gruppi di Active Directory richiesti per l'accesso alla rete WLAN
  
È necessario eseguire il seguente script come utente che dispone dell'autorizzazione per creare gruppi di protezione Active Directory. Questo script crea i gruppi richiesti per la registrazione di certificati di autenticazione senza fili, criteri di accesso remoto e criteri di gruppo della rete senza fili:
  
Cscript //job:CreateWirelessGroups C:\\MSSScripts\\wl\_tools.wsf
  
Lo script crea i seguenti gruppi di protezione basati su Active Directory che vengono utilizzati nell'intera guida:
  
-   Registrazione automatica autenticazione client - Certificato utente
  
-   Registrazione automatica autenticazione client - Certificato computer
  
-   Registrazione automatica certificato di autenticazione server RAS e IAS
  
-   Criteri di accesso remoto – Utenti senza fili
  
-   Criteri di accesso remoto – Computer senza fili
  
-   Criteri di accesso remoto - Accesso senza fili
  
-   Criteri di rete senza fili - Computer
  
Nel caso di un dominio con più insiemi di strutture, è necessario creare questi gruppi nello stesso dominio degli utenti senza fili.
  
**Nota:** la maggior parte dei gruppi creati in questa soluzione sono gruppi globali che, se richiesto, possono essere sostituiti con gruppi universali. Lo script che crea i gruppi di protezione può essere facilmente modificato; copiare la sintassi usata per creare il gruppo universale Criteri di accesso remoto - Accesso senza fili.
  
#### Verifica delle impostazioni di DHCP
  
Per utilizzare una rete senza fili, è necessario configurare i server DHCP con ambiti specifici per tecnologie senza fili e tempi di lease degli indirizzi IP (Internet Protocol) più brevi rispetto a quelli per i client con fili. Rivolgersi agli amministratori dei server DHCP per verificare che tali server siano stati configurati correttamente per supportare la soluzione senza fili.
  
Per informazioni approfondite sulla pianificazione DHCP per la rete senza fili, vedere il capitolo "Deploying a Wireless LAN" (in inglese) del *Windows Server 2003 Deployment Kit.*
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione e distribuzione di certificati di autenticazione WLAN.
  
La soluzione di rete WLAN protetta descritta in questa guida utilizza certificati X.509 per eseguire l'autenticazione di computer e utenti utilizzando EAP-TLS. Nella sezione che segue vengono descritte in dettaglio la creazione e la distribuzione dei seguenti certificati:
  
-   Autenticazione client - Computer
  
-   Autenticazione client - Utente
  
-   Autenticazione server RAS e IAS
  
    **Nota:** vedere il capitolo 11, “Gestione dell'infrastruttura a chiave pubblica”, per ulteriori informazioni su queste operazioni e sui ruoli necessari per eseguirle.
  
#### Creazione di un modello di certificato per l'autenticazione server
  
Un certificato server è necessario sul server IAS per autenticare il computer ai client che eseguono l'handshake del protocollo EAP-TLS. Chiedere all'amministratore dei Servizi certificati di eseguire i seguenti passaggi utilizzando lo snap-in Microsoft Management Console (MMC) Modelli di certificato sul server Servizi certificati per creare un modello di autenticazione server da usare con i server IAS.
  
**Per creare un modello di certificato per server senza fili**
  
1.  Creare un duplicato del modello di certificato dei server RAS e IAS** **. Immettere **l'autenticazione dei server RAS e IAS** nel **campo Nome visualizzato modello** nella scheda **Generale** delle proprietà del nuovo modello.
  
2.  Nella scheda **Estensioni,** assicurarsi che i criteri dell'applicazione includano solo **Autenticazione server** (OID 1.3.6.1.5.5.7.3.1).
  
3.  Inoltre, nella scheda **Estensioni**, modificare i criteri di rilascio e aggiungere il criterio **Medium Assurance**.
  
4.  Nella scheda **Nome soggetto**, selezionare **Crea in base alle informazioni di Active Directory**. Assicurarsi, inoltre, che **Formato del nome soggetto** sia impostato su **Nome comune** e che in **Includere le seguenti informazioni nel nome soggetto alternativo** sia selezionato soltanto **Nome DNS.**
  
5.  **Nella scheda Gestione richiesta**, fare clic sul pulsante **CSP**, assicurarsi che sia selezionata l'opzione per **utilizzare solo uno dei seguenti CSP per le richieste** e che sia selezionato solo **Microsoft RSA SChannel Cryptographic Provider**.
  
6.  Nella scheda **Protezione**, aggiungere il gruppo di protezione Registrazione automatica certificato di autenticazione server RAS e IAS con autorizzazioni **Lettura**, **Registrazione** e **Registrazione automatica**.
  
    **Importante:** rimuovere qualsiasi altro gruppo che dispone di autorizzazioni   a registrare e/o registrare automaticamente questo modello di certificato. Gli utenti o i gruppi che devono registrare questi certificati devono essere aggiunti al gruppo rilevante di registrazione (o registrazione automatica) del modello di certificato. Questa configurazione impedisce agli utenti o ai gruppi di registrare inavvertitamente certificati che essi non dovrebbero essere in grado di rilasciare. Vedere la sezione "Creazione di gruppi di registrazione modelli di certificato" nel capitolo 11, "Gestione dell'infrastruttura a chiave pubblica" per ulteriori dettagli.
  
Il capitolo 4, “Progettazione dell’infrastruttura a chiave pubblica (PKI)”, esamina l'impostazione di questo tipo di certificato per richiedere l'approvazione del gestore dei certificati. Poiché questo è considerato un certificato di valore relativamente alto, potrebbe essere opportuno attivare questa opzione per fornire una verifica aggiuntiva come misura di protezione per il caso in cui venga registrato un server IAS inaffidabile. Questo approccio significa che per rilasciare il certificato è richiesta un'approvazione manuale (anche se la richiesta viene comunque inviata automaticamente al server IAS e il certificato viene recuperato automaticamente dopo l'approvazione).
  
#### Creazione di un modello di certificato per utenti senza fili
  
I certificati utente sono necessari per l'autenticazione di utenti finali nel server IAS durante l'autenticazione EAP-TLS. Chiedere all'amministratore del Servizio certificati di eseguire i seguenti passaggi utilizzando lo snap-in MMC Modelli di certificato sul server Servizi certificati per creare un modello di certificato di autenticazione utente.
  
**Per creare un modello di certificato di autenticazione utente**
  
1.  Creare un duplicato del modello della sessione autenticata. Immettere **Autenticazione client - Utente** nel campo **Nome visualizzato modello** nella scheda **Generale** del nuovo modello.
  
2.  Nella scheda **Gestione richieste** selezionare **CSP** e deselezionare le caselle di controllo **Microsoft Base DSS Cryptographic Provider**.
  
3.  Nella scheda **Nome soggetto**, assicurarsi di aver selezionato **Crea in base alle informazioni di Active Directory**. Sotto **Formato del nome soggetto**, ** **selezionare **Nome comune**. Assicurarsi che **Nome principale utente (UPN**) sia l'unica opzione selezionata sotto **Includere le seguenti informazioni nel nome soggetto alternativo**.
  
4.  Nella scheda **Estensioni**, assicurarsi che sia incluso solo **Autenticazione client (OID 1.3.6.1.5.5.7.3.2)** in **Criteri di applicazione**.
  
5.  Inoltre, nella scheda **Estensioni** modificare i criteri di rilascio e aggiungere il criterio **Low Assurance**.
  
6.  Nella scheda **Protezione**, aggiungere il gruppo di protezione Registrazione automatica certificato di autenticazione server RAS e IAS con autorizzazioni **Lettura**, **Registrazione** e **Registrazione automatica**.
  
    **Importante:** rimuovere qualsiasi altro gruppo che dispone di autorizzazioni   a registrare e/o registrare automaticamente questo modello di certificato. Gli utenti o i gruppi che devono registrare questi certificati devono essere aggiunti al gruppo rilevante di registrazione (o registrazione automatica) del modello di certificato. Vedere la nota precedente.
  
#### Creazione di un modello di certificato per utenti senza fili
  
Un certificato è necessario per l'autenticazione di computer nel server IAS durante l'autenticazione EAP-TLS. Chiedere all'amministratore del Servizio certificati di eseguire i seguenti passaggi utilizzando lo snap-in MMC Modelli di certificato sul server Servizi certificati per creare un modello di certificato di autenticazione computer.
  
**Per creare un modello di certificato di autenticazione computer**
  
1.  Creare un duplicato del modello Autenticazione Workstation. Immettere **Autenticazione client - computer** nel campo **Nome visualizzato del modello** nella scheda  **Generale** del nuovo modello.
  
2.  Nella scheda **Nome soggetto**, assicurarsi di aver selezionato **Crea in base alle informazioni di Active Directory**. In **Formato del nome soggetto** selezionare **Nome comune.** Assicurarsi che **Nome DNS** sia l'unica opzione selezionata sotto **Includere le seguenti informazioni nel nome soggetto alternativo**.
  
3.  Nella scheda **Estensioni**, modificare i criteri di applicazione e assicurarsi che sia selezionato solo **Autenticazione client (OID 1.3.6.1.5.5.7.3.2)**.
  
4.  Inoltre, nella scheda **Estensioni** modificare i criteri di rilascio e aggiungere il criterio **Low Assurance**.
  
5.  Nella scheda **Protezione**, aggiungere il gruppo di protezione Registrazione automatica certificato di autenticazione client - Computer ** **(WOODGROVEBANK\\Registrazione automatica certificato di autenticazione client - Computer) con autorizzazioni **Lettura**, **Registrazione ** e **Registrazione automatica** .
  
    **Importante:** rimuovere qualsiasi altro gruppo che dispone di autorizzazioni   a registrare e/o registrare automaticamente questo modello di certificato. Gli utenti o i gruppi che devono registrare questi certificati devono essere aggiunti al gruppo rilevante di registrazione (o registrazione automatica) del modello di certificato. Vedere la nota precedente.
  
#### Aggiunta dei certificati di autenticazione WLAN all'Autorità di certificazione
  
Una volta configurati i modelli di certificato di autenticazione WLAN, è necessario aggiungerli all'Autorità di certificazione (CA) per attivare la registrazione. Chiedere all'amministratore dei Servizi certificati di eseguire i seguenti passaggi per aggiungere modelli di certificato all'Autorità di certificazione.
  
**Aggiungere modelli di certificato alla CA**
  
Dallo snap-in MMC Autorità di certificazione, fare clic con il pulsante destro del mouse sulla cartella **Modelli di certificato**, quindi selezionare **Nuovo** e **Modello di certificato da emettere**. Selezionare i seguenti certificati, quindi fare clic su **OK**:
  
-   Autenticazione client - Computer
  
-   Autenticazione client - Utente
  
-   Autenticazione server RAS e IAS
  
#### Registrazione del certificato server IAS
  
La distribuzione dei certificati di autenticazione server ai server IAS è una procedura relativamente semplice e automatizzata. Per eseguire questa operazione, completare i passaggi descritti nella sezione che segue.
  
**Per registrare un certificato di autenticazione server IAS dalla CA**
  
1.  Utilizzare lo snap-in MMC Utenti e computer di Active Directory per aggiungere account computer IAS al gruppo di protezione Registrazione automatica certificato di autenticazione server RAS e IAS.
  
    **Importante:** per rendere effettiva questa nuova appartenenza al gruppo, è necessario riavviare il computer.
  
2.  Accedere al server IAS come membro del gruppo Amministratori locale ed eseguire GPUPDATE /force al prompt dei comandi.
  
3.  Aprire la console MMC,** ** quindi aggiungere lo snap-in **Certificati** . Quando viene richiesto, selezionare l'opzione **Account computer**, quindi selezionare **Computer locale** .
  
4.  Selezionare **Certificati (computer locale)** dalla struttura della console, scegliere **Tutte le attività** dal menu **Azione**, quindi fare clic su **Registra automaticamente certificati**.
  
    **Nota:** se l'opzione per richiedere l'approvazione del gestore dei certificati è stata selezionata per questo tipo di certificato, sarà necessario contattare l'amministratore CA per verificare se si tratta di una richiesta legittima per un server IAS. Una volta eseguita la verifica, l'amministratore CA rilascerà il certificato.
  
#### Verifica della distribuzione dei certificati server IAS
  
La velocità con cui un certificato server IAS registrato viene rilasciato e distribuito all'archivio di certificati server dipende dalle impostazioni relative all'approvazione dei certificati nel modello di certificato. È possibile inoltre che si verifichi un ritardo perché il server interroga la CA a intervalli di qualche ora.
  
**Per verificare che il certificato di autenticazione server IAS sia stato distribuito**
  
1.  Accedere come membro del gruppo Amministratori locale sul computer locale, aprire lo snap-in MMC certificati,** **quindi aggiungere lo snap-in **Certificati**. Quando viene richiesto, selezionare l'opzione **Account computer**, quindi selezionare **Computer locale** .
  
2.  Aprire l'archivio **Certificati (computer locali)**, **Personale**, **Certificati** e cercare un certificato rilasciato al nome del computer locale dal modello di certificato di autenticazione server RAS e IAS. Il nome del modello è visualizzato nel riquadro di destra. Per visualizzare la colonna appropriata potrebbe essere necessario scorrere la schermata orizzontalmente.
  
3.  Se il certificato richiesto non viene visualizzato nello snap-in MMC certificati,** **selezionare **Certificati (computer locale)** dalla struttura della console, scegliere **Tutte le attività** dal menu **Azione**, quindi selezionare **Registra automaticamente certificati**. Attendere qualche istante per l'esecuzione di questa azione, quindi aggiornare la visualizzazione della cartella Personale,** ** Certificati.
  
    **Nota:** se la registrazione automatica del certificato è stata eseguita correttamente, nel Registro eventi applicazioni sarà presente un evento con origine Registrazione automatica e un ID evento 19.
  
#### Aggiunta di utenti e computer ai gruppi per la registrazione automatica
  
La distribuzione di certificati di autenticazione WLAN a utenti e computer è, di solito, trasparente per gli utenti finali. La procedura richiede una connessione a una rete LAN, un account utente basato su dominio e un computer associato a un dominio Active Directory.
  
Gli utenti e i computer che richiederanno l'accesso alla nuova rete WLAN devono disporre di certificati distribuiti in precedenza per assicurare che sia possibile eseguire l'autenticazione EAP-TLS. Se si utilizza Windows XP e Windows Server 2003, sia i certificati computer che quelli utente possono essere registrati automaticamente e rinnovati senza l'intervento dell'utente finale. La registrazione e il rinnovo di certificati sono controllati tramite i gruppi di protezione di Active Directory.
  
**Nota:** questa soluzione utilizza gruppi di protezione personalizzati (Registrazione automatica autenticazione client - Certificato utente e Registrazione automatica autenticazione client - Certificato computer) per limitare gli utenti e i computer autorizzati a registrare automaticamente i certificati WLAN. Se si desidera che tutti i computer e gli utenti del dominio ricevano i certificati WLAN, è possibile aggiungere gli utenti del dominio al gruppo Registrazione automatica autenticazione client - Certificato utente e i computer del dominio al gruppo Registrazione automatica autenticazione client - Certificato computer.
  
**Per aggiungere utenti e computer ai gruppi di protezione per la registrazione automatica**
  
1.  Aprire lo snap-in MMC Utenti e computer di Active Directory.
  
2.  Aggiungere gli utenti al gruppo Registrazione automatica autenticazione client - Certificato utente.
  
3.  Aggiungere i computer al gruppo Registrazione automatica autenticazione client - Certificato computer.
  
    **Importante:** per ricevere questa nuova appartenenza al gruppo nei token di accesso, gli utenti devono disconnettersi e riconnettersi e i computer devono essere riavviati. È necessario controllare di aver effettuato entrambe queste operazioni prima di continuare con la procedura di verifica.
  
##### Verifica della distribuzione di certificati utente
  
Eseguire i seguenti passaggi dopo aver effettuato l'accesso come utente che è stato aggiunto al gruppo Registrazione automatica autenticazione client - Certificato utente.
  
**Per verificare la distribuzione di certificati di autenticazione utente**
  
1.  Se non è stata effettuata la disconnessione, disconnettersi e riconnettersi come utente selezionato. Aprire la console MMC** **, quindi aggiungere lo snap-in **Certificati**. Se viene richiesto, selezionare l'opzione **Account dell'utente**.
  
2.  Aprire l'archivio **Certificati - Utente corrente**, **Personale**, **Certificati** e cercare un certificato rilasciato all'utente dal modello di autenticazione client certificato utente. Il nome del modello dovrebbe essere visualizzato nel riquadro di destra. Per visualizzare la colonna appropriata potrebbe essere necessario scorrere la schermata orizzontalmente.
  
3.  Se il certificato richiesto non è visualizzato nello snap-in **Certificati**, eseguire GPUPDATE /force dal prompt dei comandi, attendere qualche minuto, quindi aggiornare la visualizzazione della cartella Personale, ** **Certificati.
  
##### Verifica della distribuzione di certificati computer
  
Eseguire i seguenti passaggi da un computer client che è stato aggiunto al gruppo Registrazione automatica autenticazione client - Certificato computer.
  
**Per verificare la distribuzione di certificati di autenticazione computer**
  
1.  Riavviare il computer se questa operazione non è stata eseguita dopo averlo aggiunto al gruppo di registrazione automatica del certificato.
  
2.  Accedere come membro di un gruppo Amministratori locale sul computer locale, aprire la console MMC,** **quindi aggiungere lo snap-in **Certificati**. Quando viene richiesto, selezionare l'opzione **Account computer**, quindi selezionare **Computer locale** .
  
3.  Aprire l'archivio **Certificati (computer locali)**, **Personale**, **Certificati** e cercare un certificato rilasciato al nome del computer locale dal modello di certificato di autenticazione client - Certificato computer. Il nome del modello dovrebbe essere visualizzato nel riquadro di destra. Per visualizzare la colonna appropriata potrebbe essere necessario scorrere la schermata orizzontalmente.
  
4.  Se il certificato richiesto non è visualizzato nello snap-in **Certificati**, eseguire GPUPDATE /force dal prompt dei comandi, attendere qualche minuto, quindi aggiornare la visualizzazione della cartella Personale, ** **Certificati.
  
    **Suggerimento:** è possibile riavviare il computer per imporre la registrazione automatica del certificato. Se la registrazione automatica del certificato è stata eseguita correttamente, nel Registro eventi applicazioni sarà presente un evento con origine Registrazione automatica e un ID evento 19.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione dell'infrastruttura di accesso WLAN
  
È necessario configurare il server IAS primario con criteri di accesso remoto e impostazioni di richiesta di connessione che determinano l'autenticazione e l'autorizzazione di utenti e computer senza fili alla rete WLAN. È necessario replicare queste impostazioni negli altri server IAS; per eseguire questa operazione, utilizzare la procedura illustrata nella sezione “Distribuzione della configurazione a più server IAS” del capitolo 8, “Implementazione dell'infrastruttura RADIUS”. Inoltre, ciascun server IAS deve essere configurato in maniera univoca per accettare le connessioni da parte di client RADIUS quali, ad esempio, punti di accesso senza fili. I punti di accesso senza fili devono essere configurati per utilizzare server IAS come origine dell'autenticazione e accounting per la rete 802.1X.
  
#### Creazione di un criterio di accesso remoto IAS per reti WLAN
  
Eseguire i seguenti passaggi utilizzando lo snap-in MMC Servizio autenticazione Internet per configurare IAS con un criterio di accesso remoto per reti senza fili.
  
**Per creare un criterio di accesso remoto in IAS**
  
1.  Fare clic con il pulsante destro del mouse sulla cartella Criteri di accesso remoto, quindi selezionare l'opzione per **creare un nuovo criterio di accesso remoto.**
  
2.  Assegnare al criterio il nome **Consenti accesso senza fili** e nella procedura guidata impostare **Procedura guidata per impostare un criterio tipico per scenari**.
  
3.  Selezionare **Senza fili** come metodo di accesso.
  
4.  Consentire l'accesso in base al gruppo e utilizzare il gruppo di protezione Criteri di accesso remoto - Accesso senza fili.
  
5.  Scegliere **Smart Card o altro certificato** per il protocollo Extensible Authentication Protocol (EAP), quindi selezionare il certificato di autenticazione server installato per IAS. Completare la procedura e uscire dalla procedura guidata.
  
    **Nota:** il nuovo criterio Consenti accesso senza fili** **può coesistere con altri criteri di accesso remoto creati dall'utente o con i criteri di accesso remoto predefiniti. Assicurarsi, tuttavia, che i criteri di accesso remoto predefiniti siano stati eliminati o elencati dopo il criterio Consenti accesso senza fili nella cartella Criteri di accesso ** ** remoto.
  
##### Modifica delle impostazioni del profilo dei Criteri di accesso WLAN
  
Le impostazioni predefinite dei criteri di accesso remoto creati in precedenza devono essere modificate per ignorare le impostazioni di connessione remota da Active Directory che possono provocare potenziali problemi con alcuni tipi di AP senza fili. Inoltre, gli attributi RADIUS dovrebbero essere impostati per la nuova autenticazione client a intervalli prestabiliti per assicurare che vengano aggiornate le chiavi di sessione WEP. Per ulteriori informazioni riguardo le impostazioni dei criteri di accesso remoto, vedere il capitolo 6, “Progettazione della protezione di reti LAN senza fili mediante lo standard 802.1X”.
  
**Per modificare le impostazioni del profilo dei criteri di accesso senza fili**
  
1.  Aprire la pagina delle proprietà del criterio Consenti accesso senza fili, quindi fare clic su **Modifica profilo**.
  
2.  Nella scheda **Limitazioni chiamate in ingresso** selezionare l'opzione **Limite massimo di minuti per la connessione del client (timeout sessione)**, quindi immettere come valore **10 minuti**.
  
    **Nota:** è possibile utilizzare un timeout più lungo di 60 minuti senza compromettere in modo significativo la protezione. In tal modo, l'installazione è più resistente alle interruzioni temporanee della rete e impone un carico minore sui server IAS.
  
3.  Nella scheda **Avanzate** aggiungere l'attributo **Ignorare le proprietà della connessione remota dell'utente**, impostarlo su **Vero**, quindi aggiungere l'attributo **Termination-Action** e impostarlo su **RADIUS Request**.
  
##### Verifica del criterio di richiesta di connessione per reti WLAN
  
Il criterio di richiesta di connessione IAS predefinito è configurato in modo tale da consentire a IAS di autenticare utenti e computer direttamente mediante un confronto con Active Directory. Eseguire i seguenti passaggi per verificare la configurazione del criterio di richiesta di connessione predefinito.
  
**Per verificare la configurazione del criterio di richiesta di connessione predefinito**
  
1.  Aprire lo snap-in MMC Servizio autenticazione Internet e visualizzare le proprietà del criterio di richiesta di connessione **Utilizzare autenticazione Windows per tutti gli utenti** ** **.
  
2.  Verificare che le condizioni del criterio contengano **Date-And-Time-Restrictions matches** **“Sun 00:00-24:00; Mon 00:00-24:00; Tue 00:00-24:00; Wed 00:00-24:00; Thu 00:00-24:00; Fri 00:00-24:00; Sat 00:00-24:00”**
  
3.  Scegliere il pulsante **Modifica profilo**. Accertarsi che nella scheda **Autenticazione** sia selezionata l'opzione **Autentica le richieste su questo server**.
  
4.  Assicurarsi che siano presenti regole nella scheda **Attributi**.
  
    **Nota:** per questa soluzione non sono richieste impostazioni aggiuntive per il criterio di richiesta di connessione. Tuttavia, è possibile che la propria organizzazione preveda impostazioni aggiuntive adatte per esigenze diverse.
  
Dopo aver configurato l'accesso alla rete WLAN, tutte le modifiche di configurazione effettuate sul server IAS primario devono essere replicate negli altri server IAS. È necessario replicare queste impostazioni negli altri server IAS; per eseguire questa operazione, utilizzare la procedura illustrata nella sezione “Distribuzione della configurazione a più server IAS” del capitolo 8, “Implementazione dell'infrastruttura RADIUS”.
  
##### Aggiunta di client RADIUS a IAS
  
È necessario aggiungere proxy RADIUS e punti di accesso senza fili come client RADIUS a IAS prima di consentire che usufruiscano dei servizi di autenticazione e accounting tramite il protocollo RADIUS. Per aggiungere AP senza fili a IAS, eseguire i seguenti passaggi dallo snap-in MMC Servizio autenticazione Internet (IAS, Internet Authentication Server).
  
**Per aggiungere client RADIUS a IAS**
  
1.  Fare clic con il pulsante destro del mouse sulla cartella Client Radius ** **, quindi selezionare **Nuovo client RADIUS**.
  
2.  Immettere un nome descrittivo e l'indirizzo IP dell'AP senza fili.
  
3.  Selezionare **RADIUS Standard** come attributo Client-Fornitore, quindi immettere il segreto condiviso per l'AP senza fili (è possibile utilizzare lo script GenPwd, descritto nella procedura seguente, per generare un segreto sicuro), quindi selezionare l'attributo **La richiesta deve contenere l'autenticatore del messaggio.**
  
    **Nota:** alcuni client RADIUS possono richiedere la configurazione di attributi specifici del produttore (VSA) per funzionare correttamente. Consultare la documentazione fornita dal produttore per informazioni relative a questo tipo di requisiti.
  
È possibile utilizzare lo script GenPwd incluso in questa guida per generare segreti casuali avanzati a 23 caratteri per l'uso individuale da parte di ciascun punto di accesso senza fili configurato come client RADIUS. GenPwd genererà un segreto casuale in maniera crittografica e lo archivierà in un file Clients.txt insieme a un nome descrittivo per ciascun client RADIUS. GenPwd aggiunge automaticamente le informazioni a un file Clients.txt nella directory corrente sotto forma di valori separati da virgola.
  
N*on* copiare questo file nel disco rigido del server. Salvare il file su disco floppy o su altro supporto rimovibile con l'etichetta “Client RADIUS per server ***HQ-IAS-01***“ (utilizzare il nome del server invece di *HQ-IAS-01*) e conservarlo in un luogo sicuro. Lo stesso disco, specifico del server, viene utilizzato per eseguire l'esportazione e l'importazione di client RADIUS nel capitolo 12, “Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili”.
  
**Per generare segreti RADIUS in un file Clients.txt utilizzando lo script GenPwd**
  
1.  Accedere al prompt dei comandi e impostare A come directory corrente (se si utilizza un tipo di supporto diverso dal disco floppy, usare la lettera di unità appropriata). La posizione della directory di file system è importante in quanto nel file Clients.txt presente nella directory predefinita verranno automaticamente aggiunte le nuove informazioni. Se non esiste un file Clients.txt, ne verrà creato uno.
  
2.  Eseguire il comando seguente. Accertarsi di sostituire il *nome client* con il nome descrittivo del punto di accesso senza fili, ad esempio un nome DNS o un'altra stringa:
  
    Cscript //job:GenPWD C:\\MSSScripts\\wl\_tools.wsf /client:*nome client*
  
    **Importante:** conservare il disco di archiviazione client RADIUS in un luogo sicuro e accessibile nel caso in cui si renda necessario un ripristino di emergenza. Una volta creato, importare il file delimitato da virgole in un foglio di calcolo o in un’applicazione di database, per consultazioni o modifiche future.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Abilitazione dell'accesso di utenti e computer alla rete WLAN
  
I passaggi finali per l'attivazione di utenti e computer per l'accesso a una rete WLAN protetta sono costituiti da operazioni che devono essere eseguite su oggetti Active Directory. Tra queste operazioni sono incluse la verifica di autorizzazioni account, la modifica dell'appartenenza ai gruppi e l'implementazione delle impostazioni dei criteri di gruppo. È possibile eseguire queste azioni in maniera controllata seguendo un programma di distribuzione graduale in modo da ridurre i rischi inerenti a una modifica significativa dell'ambiente.
  
#### Verifica delle autorizzazioni di accesso remoto Active Directory
  
Per poter utilizzare i criteri di accesso remoto, gli account di utenti e computer di Active Directory devono disporre delle corrette autorizzazioni di accesso remoto. Per impostazione predefinita, le autorizzazioni di accesso remoto su account in un dominio Active Directory in modalità originale sono impostate su **Controlla accesso tramite Criteri di accesso remoto**;** **pertanto una modifica, in genere, non è necessaria.
  
Tuttavia, è possibile verificare se gli utenti e i computer di destinazione siano configurati correttamente con lo snap-in MMC Utenti e computer di Active Directory. Verificare che l'opzione **Controlla accesso tramite Criteri di accesso remoto** sia selezionata per l'impostazione **Autorizzazione di accesso remoto (chiamata in ingresso o VPN)** nella scheda **Chiamate in ingresso** delle proprietà dell'account.
  
#### Aggiunta di utenti a gruppi di Criteri di accesso remoto
  
I criteri di accesso remoto IAS utilizzano gruppi di protezione basati su Active Directory per determinare se gli utenti e i computer sono autorizzati ad accedere alla rete WLAN. I gruppi di protezione creati in precedenza in questo capitolo includono quelli descritti nella seguente tabella.
  
**Tabella 9.3. Gruppi di protezione di Active Directory**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Gruppo di protezione</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Criteri di accesso remoto - Utenti senza fili</td>
<td style="border:1px solid black;">Gruppo globale per utenti che richiedono l'accesso alla rete WLAN.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri di accesso remoto - Computer senza fili</td>
<td style="border:1px solid black;">Gruppo globale per computer che richiedono l'accesso alla rete WLAN.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri di accesso remoto - Accesso senza fili</td>
<td style="border:1px solid black;">Gruppo universale che dovrebbe contenere i due gruppi globali precedenti.</td>
</tr>
</tbody>
</table>
  
Utilizzare lo snap-in MMC Utenti e computer di Active Directory per aggiungere il gruppo Criteri di accesso remoto - Utenti senza fili e Criteri di accesso remoto - Computer senza fili al gruppo Criteri di accesso remoto - Accesso senza fili.
  
**Importante:** questa soluzione utilizza gruppi di protezione personalizzati (Criteri di accesso remoto - Utenti senza fili e Criteri di accesso remoto - Computer senza fili) per limitare gli utenti e i computer autorizzati ad accedere alla rete WLAN. Se si desidera che tutti i computer e gli utenti del dominio abbiano accesso alla rete WLAN, è possibile aggiungere i gruppi Utenti dominio e Computer del dominio a questi gruppi di protezione personalizzati per semplificare l'amministrazione.
  
Ora la struttura di gruppo è pronta per essere popolata con utenti e computer che saranno autorizzati ad accedere alla rete WLAN.
  
**per aggiungere utenti e computer ai gruppi di accesso alla rete WLAN**
  
1.  Aprire lo snap-in MMC Utenti e computer di Active Directory.
  
2.  Aggiungere gli utenti che disporranno dell'autorizzazione di accesso alla rete WLAN al gruppo Criteri di accesso remoto - utenti senza fili (WOODGROVEBANK\\Criteri di accesso remoto - utenti senza fili).
  
3.  Aggiungere i computer che disporranno dell'autorizzazione di accesso alla rete WLAN al gruppo Criteri di accesso remoto - computer senza fili (WOODGROVEBANK\\Criteri di accesso remoto - computer senza fili).
  
    **Nota:** per ulteriori informazioni sui motivi alla base dell'attivazione dell'autenticazione degli utenti e dei computer per l'accesso alla rete WLAN, vedere il capitolo 6, “Progettazione della protezione di reti LAN senza fili mediante lo standard 802.1X”.
  
#### Creazione di criteri di gruppo WLAN di Active Directory
  
È possibile automatizzare e imporre la configurazione WLAN di computer client utilizzando i Criteri di gruppo Windows. Lo snap-in MMC Criteri di gruppo in Windows Server 2003 consente di configurare le impostazioni dei **criteri di rete senza fili**, incluse le impostazioni relative alla protezione basata sullo standard 802.1X e al comportamento delle reti WLAN 802.11.
  
Per creare un profilo di criterio di gruppo per reti senza fili per i computer client della nuova rete WLAN basata sullo standard 802.1X, eseguire i seguenti passaggi utilizzando lo snap-in MMC Utenti e computer di Active Directory.
  
**Note:**  
la creazione di GPO a livello di dominio potrebbe non essere adatta per tutte le organizzazioni. Pertanto, per determinare la posizione ottimale per i GPO, è necessario esaminare la strategia dei criteri di gruppo della propria organizzazione.  
Se l'oggetto Criteri di gruppo viene modificato in un sistema Windows 2000 o Windows XP, le impostazioni dell'oggetto Criteri di gruppo senza fili non verranno visualizzate nella relativa console MMC. È quindi necessario modificare le impostazioni in un sistema Windows Server 2003 o in un sistema in cui siano installati gli strumenti di amministrazione di Windows Server 2003. È possibile utilizzare queste impostazioni GPO in Active Directory di Windows 2000 o Windows Server 2003.
  
**Per creare un criterio di gruppo per la rete senza fili**
  
1.  Selezionare le proprietà dell'oggetto dominio (ad esempio woodgrovebank.com) e nella scheda **Criteri di gruppo** fare clic su **Nuovo** e assegnare al GPO il nome **Criteri di rete senza fili.**
  
2.  Fare clic sul pulsante **Proprietà** e nella scheda **Protezione,** concedere al gruppo di protezione Criteri di rete senza fili - Computer le autorizzazioni **Lettura** e **Applica criteri di gruppo**. Rimuovere, inoltre, l'autorizzazione **Applica criteri di gruppo** da Utenti autenticati nell'oggetto Criteri di gruppo.
  
3.  Nella scheda **Generale,** selezionare **Disattiva impostazioni configurazione utente** sull'oggetto criteri e selezionare **Sì** quando vengono visualizzati messaggi di avviso. Applicare le modifiche e chiudere la finestra delle **proprietà** GPO.
  
4.  Fare clic sul pulsante **Modifica** per modificare il criterio e passare a \\Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri di rete senza fili (IEEE 802.11).
  
5.  Selezionare l'oggetto **Criteri di rete senza fili (IEEE 802.11)** dal riquadro di spostamento, quindi selezionare **Crea criterio rete senza fili** dal menu **Azione**. Utilizzare la procedura guidata per assegnare al criterio il nome **Configurazione senza fili computer client**. Lasciare selezionata l'opzione **Modifica proprietà**, quindi scegliere **Fine** per chiudere la procedura guidata.
  
6.  Selezionare **Aggiungi** dalla scheda **Reti preferite** del criterio Configurazione senza fili del computer client** **, quindi immettere il nome della rete o l'identificatore del set di servizi (SSID, Service Set Identifier) della rete senza fili.
  
    **Nota:** se i client utilizzano una rete WLAN esistente, è necessario scegliere un SSID diverso per la nuova rete LAN senza fili 802.1X. Immettere l'SSID nel profilo della rete senza fili 802.1X.
  
7.  Fare clic sulla scheda **IEEE 802.1x**, quindi aprire le impostazioni per il tipo EAP **Smart Card o altro certificato**. Sotto **Autorità di certificazione principale attendibili**, selezionare il certificato CA principale per infrastruttura PKI che ha emesso i certificati del server IAS (ossia, infrastruttura PKI installata nel capitolo 7, “Implementazione dell'infrastruttura a chiave pubblica”).
  
8.  Chiudere la finestra delle proprietà per la **Configurazione senza fili computer client** e l'editor degli oggetti Criteri di gruppo.
  
#### Aggiunta di computer a gruppi di protezione per i criteri di gruppo WLAN
  
I gruppi di protezione basati su Active Directory vengono utilizzati per determinare i computer ai quali sono applicati criteri di rete senza fili per configurare automaticamente le impostazioni 802.11 e 802.1X.
  
La distribuzione delle impostazioni dei criteri di gruppo per reti senza fili per la nuova rete basata sullo standard 802.1X devono essere configurate con grande anticipo rispetto alle impostazioni 802.1X sugli AP senza fili e all'attivazione della nuova WLAN. In tal modo si assicura che i computer client dispongano della possibilità di scaricare e applicare il criterio di gruppo basato sul computer, anche se si connettono alla rete LAN soltanto occasionalmente.
  
Le impostazioni dei criteri di gruppo possono essere applicate al computer prima che la scheda dell'interfaccia di rete (NIC) WLAN venga installata e configurata tramite Windows. Una volta installata una scheda di rete LAN senza fili, verranno automaticamente recuperati e applicati a tale scheda i criteri di gruppo per la rete senza fili appropriati.
  
**Importante:** questa soluzione utilizza un gruppo di protezione personalizzato (Criterio di rete senza fili - Computer) per determinare quali computer ricevono la configurazione per la rete WLAN. Per consentire a tutti i computer di ricevere le impostazioni di configurazione della rete WLAN, è possibile semplificare l’amministrazione aggiungendo il gruppo Computer del dominio o quello Utenti autenticati a questo gruppo. È necessario tenere presente che questa operazione applica le impostazioni dei criteri a tutti i server e i client presenti nel dominio (se si utilizza l'opzione Computer del dominio) o nell'insieme di strutture (se si utilizza l'opzione Utenti autenticati).
  
**Per aggiungere computer o gruppi ai criteri di gruppo per reti senza fili**
  
1.  Utilizzare lo snap-in MMC Utenti e computer di Active Directory per aggiungere computer al gruppo Criterio di rete senza fili - Computer.
  
2.  Prima di provare ad utilizzare la rete WLAN, accertarsi che i sistemi vengano riavviati (questa operazione è richiesta per consentire al computer di ricevere la nuova appartenenza al gruppo configurata nel passaggio precedente).
  
    **Nota:** le impostazioni dell'oggetto Criteri di gruppo della rete senza fili verranno aggiornate sui computer client durante il successivo intervallo di aggiornamento dei Criteri di gruppo. In alternativa è possibile utilizzare il comando  GPUPDATE /force dal prompt dei comandi per imporre un aggiornamento dei criteri.
  
#### Verifica dell'applicazione dei criteri di gruppo WLAN
  
Eseguire i seguenti passaggi da un computer client che è stato aggiunto al gruppo di protezione **Configurazione senza fili del computer client** in Active Directory.
  
**Nota:** affinché i criteri di rete senza fili siano visibili, è necessario che nei computer sia installata e riconosciuta da Windows una scheda di rete senza fili.
  
**Per verificare la distribuzione della configurazione di rete senza fili**
  
1.  Accedere come Administrator al computer locale, fare clic su **Start**, **Esegui** e digitare il seguente comando per aprire la cartella Connessioni di rete:
  
    ncpa.cpl
  
2.  Visualizzare le proprietà dell'icona **Connessione rete senza fili** corrispondente alla scheda senza fili. Nella scheda **Reti senza fili,** verrà visualizzato il nuovo nome SSID della rete senza fili sotto **Reti preferite**. Selezionare la nuova configurazione di rete senza fili e fare clic su **Proprietà** per esplorare le impostazioni e verificare che corrispondano a quelle scelte nel gruppo Criteri di gruppo della rete senza fili.
  
3.  Se il nome SSID non è visualizzato sotto **Reti preferite** o le impostazioni di rete non corrispondono a quelle configurate in Criteri di gruppo della rete senza fili, chiudere tutte le finestre di dialogo Reti senza fili ed eseguire GPUPDATE /force dal prompt dei comandi. Attendere qualche minuto, quindi ricontrollare le impostazioni.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione di AP senza fili per reti basate sullo standard 802.1X
  
La procedura per configurare i punti di accesso senza fili varia drasticamente in base alla marca e al modello della periferica. Tuttavia, i fornitori di AP senza fili in genere forniscono le informazioni per la configurazione della periferica con:
  
-   Impostazioni di rete 802.1X.
  
-   Indirizzo IP del server di autenticazione RADIUS primario.
  
-   Indirizzo IP del server di accounting RADIUS primario.
  
-   Segreto RADIUS condiviso con il server RADIUS primario.
  
-   Indirizzo IP del server di autenticazione RADIUS secondario.
  
-   Indirizzo IP del server di accounting RADIUS secondario.
  
-   Segreto RADIUS condiviso con il server RADIUS secondario.
  
Per informazioni sulla configurazione dei punti di accesso senza fili per 802.1X, vedere la documentazione del fornitore.
  
Se nell'ambiente sono presenti utenti che stanno utilizzando AP senza fili configurati senza impostazioni di protezione o solo con protezione di WEP statica, sarà necessario sviluppare un piano di migrazione. Per ulteriori informazioni sulla migrazione da una rete senza fili esistente, vedere il capitolo 6, “Progettazione della protezione di reti LAN senza fili mediante lo standard 802.1X”. Sebbene fornire istruzioni sulla configurazione degli AP senza fili dei vari fornitori non rientri negli obiettivi di questa guida, nel capitolo 6 vengono trattati anche alcuni argomenti relativi alla protezione degli AP senza fili.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Collaudo e verifica
  
È necessario collaudare la funzionalità della rete WLAN basata sullo standard 802.1X utilizzando un computer client configurato con un certificato computer, un certificato utente, criteri di gruppo di reti senza fili e una scheda di rete WLAN.
  
**Per collaudare la funzionalità della rete senza fili**
  
1.  Riavviare il computer client membro del gruppo di protezione Criteri di accesso remoto - Computer senza fili.
  
2.  Accedere al computer come utente membro del gruppo Criteri di accesso remoto - Utenti senza fili.
  
3.  Dal prompt dei comandi, utilizzare il comando **ping** per verificare la connettività a un altro computer della rete.
  
Per altre procedure di test dettagliate, vedere il capitolo 13, “Test della soluzione”.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Se sono state eseguite tutte le procedure illustrate in questo capitolo, dovrebbero essere state completate le attività seguenti:
  
-   Creazione e configurazione di gruppi di protezione di Active Directory utilizzati per gestire i componenti della protezione WLAN.
  
-   Creazione di modelli di certificato richiesti e distribuzione dei certificati senza fili ai server IAS, selezione dei computer e degli utenti finali.
  
-   Creazione e configurazione di criteri di accesso remoto basati su IAS e criteri di richiesta di connessione per la rete senza fili.
  
-   Configurazione di AP senza fili per lo standard 802.1X.
  
-   Creazione di Criteri di gruppo per reti senza fili e distribuzione di tali criteri ai computer client.
  
Una volta completate questa operazioni, l'infrastruttura di protezione della rete WLAN basata su 802.1X dovrebbe essere completamente funzionante e pronta per migliorare la protezione della rete della propria organizzazione.
  
#### Ulteriori informazioni
  
-   La [documentazione di Windows Server 2003](http://www.microsoft.com/windowsserver2003/proddoc/default.mspx) è disponibile all'indirizzo www.microsoft.com/windowsserver2003/proddoc/default.mspx. La documentazione del prodotto include una panoramica delle funzionalità di IAS, istruzioni essenziali per la configurazione e procedure consigliate per la distribuzione.
  
-   Nel capitolo [IAS Technical Reference](http://technet.microsoft.com/en-us/library/cc759100.aspx) sono incluse informazioni tecniche su IAS che possono essere utilizzate come riferimento per approfondire argomenti specifici. È disponibile all'indirizzo:http://technet.microsoft.com/en-us/library/cc759100.aspx .
  
-   Il capitolo [“Deploying a Wireless LAN”](http://technet.microsoft.com/en-us/library/cc780901.aspx) del *Microsoft Windows Server 2003 Deployment Kit* è disponibile all'indirizzo http://technet.microsoft.com/en-us/library/cc780901.aspx .  
    Questo capitolo del Deployment Kit contiene una guida alla distribuzione per l'utilizzo del servizio IAS in vari scenari che non rientrano nell'ambito della presente guida alla protezione delle reti senza fili, ma che influiscono sulle scelte di progettazione.
  
-   Per una trattazione completa delle reti WLAN 802.1X, dei problemi di protezione delle reti WLAN e degli standard correlati, vedere [la pagina Web non ufficiale della protezione basata sullo standard 802.11](http://www.drizzle.com/~aboba/ieee/) all'indirizzo www.drizzle.com/~aboba/IEEE/ (in inglese).
  
-   Per informazioni sulle soluzioni WLAN e informazioni sul settore, visitare il sito Web di Wi-Fi Alliance all'indirizzo [www.wi-fialliance.org](http://www.wi-fialliance.org) (in inglese).
  
-   Per informazioni sulla tecnologia WLAN, comprese le informazioni di background, ricerche di mercato, white paper e programmi di formazione, visitare il centro formazione di Wireless LAN Association (WLANA) all'indirizzo <http://www.wlana.org/learning_center.html> (in inglese).
  
-   Per informazioni su EAP-TLS, EAP over LAN (EAPOL), EAP-RADIUS, RADIUS e altri standard Internet utilizzati con 802.1X, vedere il sito Web di Internet Engineering Task Force (IETF) all'indirizzo <http://www.ietf.org/> (in inglese).
  
-   Gli standard WLAN specifici includono: 802.11, 802.11b, 802.11a, 802.11g, 802.1X, 802.11i, ecc. Per informazioni su questo argomento, visitare l'area relativa agli [standard senza fili del sito Web IEEE (Institute of Electrical and Electronics Engineers),](http://standards.ieee.org/wireless/%20%20.) disponibile all'indirizzo: http://standards.ieee.org/wireless/.
  
-   Per ulteriori informazioni sulle tecnologie WLAN 802.1X, vedere l'articolo ["Windows XP Wireless Deployment Technology and Component Overview"](http://technet.microsoft.com/en-us/library/bb457015.aspx) all'indirizzo http://technet.microsoft.com/en-us/library/bb457015.aspx .
  
[](#mainsection)[Inizio pagina](#mainsection)
