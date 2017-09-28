---
TOCTitle: 'Implementazione della protezione di reti LAN senza fili mediante lo standard 802.1X'
Title: 'Implementazione della protezione di reti LAN senza fili mediante lo standard 802.1X'
ms:assetid: 'd8b59dab-0d27-41f4-9ede-9471bb36849e'
ms:contentKeyID: 20200850
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536251(v=TechNet.10)'
---

Costruire una rete wireless locale sicura con Windows Server 2003 Certificate Services
======================================================================================

### Implementazione della protezione di reti LAN senza fili mediante lo standard 802.1X

##### In questa pagina

[](#enaa)[Argomenti del modulo](#enaa)
[](#emaa)[Obiettivi](#emaa)
[](#elaa)[Ambito di applicazione](#elaa)
[](#ekaa)[Utilizzo del modulo](#ekaa)
[](#ejaa)[Panoramica](#ejaa)
[](#eiaa)[Foglio di lavoro di pianificazione WLAN 802.1X](#eiaa)
[](#ehaa)[Preparazione dell'ambiente per una rete WLAN protetta](#ehaa)
[](#egaa)[Configurazione e distribuzione di certificati di autenticazione WLAN.](#egaa)
[](#efaa)[Configurazione dell'infrastruttura di accesso WLAN](#efaa)
[](#eeaa)[Attivazione di utenti e computer per reti WLAN protette](#eeaa)
[](#edaa)[Configurazione di AP senza fili per reti basate sullo standard 802.1X](#edaa)
[](#ecaa)[Collaudo e verifica](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Argomenti del modulo

Il presente modulo offre una guida completa per l'implementazione della protezione di reti LAN senza fili (WLAN). Ciò include la configurazione di Microsoft® Active Directory® i gruppi basati su servizi di directory, distribuzione di certificati X.509 per WLAN, modifica delle impostazioni del server Microsoft Internet Authentication Server (IAS), distribuzione dei criteri di gruppo WLAN e suggerimenti per la configurazione dei punti di accesso senza fili (AP). In tal modo vengono fornite tutte le impostazioni necessarie per implementare reti WLAN protette, basate sugli standard 802.1X e EAP-TLS (Extensible Authentication Protocol-Transport Layer Security).

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Il modulo consente di:

-   Implementare una progettazione di rete WLAN protetta.

-   Configurare e distribuire certificati di autenticazione WLAN.

-   Proteggere i dati trasmessi in una rete WLAN.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Questo modulo si applica ai seguenti prodotti e tecnologie:

-   Microsoft Windows® Server™ 2003

-   Microsoft Windows XP Service Pack 1

-   Microsoft Active Directory

-   Servizio di Autenticazione Internet Microsoft (IAS, Internet Authentication Service)

-   Servizi certificati Microsoft

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

Il presente modulo fornisce la metodologia e i passaggi necessari per implementare la protezione di reti LAN senza fili utilizzando lo standard 802.1X. È possibile adattare la metodologia alle esigenze della propria organizzazione. I passaggi sono modulari e dimostrano mostrano come è possibile mettere in pratica la metodologia.

Per sfruttare al massimo il presente modulo:

-   Leggere il modulo "[Progettazione della protezione di reti LAN senza fili mediante lo standard 802.1X](http://technet.microsoft.com/it-it/library/dd536259)" della *Guida operativa*. Ciò consentirà di comprendere i concetti generali dell'implementazione dello standard 802.1X.

-   Leggere il capitolo "[Deploying a Wireless LAN](http://technet.microsoft.com/en-us/library/cc780901.aspx)" (in inglese) del *Microsoft Windows Server 2003 Deployment Kit*, che contiene istruzioni per la distribuzione in un numero di scenari che non rientrano nell'ambito della presente guida alle reti senza fili protette, ma che influenzano le decisioni relative alla progettazione. Il kit completo è disponibile all'indirizzo
    <http://technet.microsoft.com/en-us/library/cc738134.aspx> (in inglese).

-   Utilizzare il 802.1X WLAN Planning Worksheet (foglio di lavoro di pianificazione WLAN 802.1X) all'inizio della guida per fornire un elenco di controllo dei parametri di c configurazione della soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica

La figura 1 mostra una panoramica del processo di implementazione della protezione WLAN utilizzando lo standard 802.1X che sarà illustrato in modo dettagliato in questo modulo.

![](images/Dd536251.SGFG16301(it-it,TechNet.10).jpg)

Figura 1

*Diagramma del processo di creazione dell'infrastruttura 802.1X*

Nell'elenco che segue viene offerta una descrizione generale delle sezioni principali di questo modulo.

-   **802.1X WLAN Planning Worksheet**: elenca le informazioni di configurazione utilizzate in questo modulo per configurare i vari componenti della rete WLAN 802.1X. È inclusa una tabella di informazioni che devono essere fornite dall'utente prima di iniziare l'implementazione del modulo.

-   **Preparazione dell'ambiente per una rete WLAN protetta**: viene descritta la preparazione dei gruppi di protezione di Active Directory necessari per configurare e gestire la rete WLAN 802.1X nel tempo. Inoltre vengono fornite raccomandazioni per il protocollo Dynamic Host Configuration Protocol (DHCP).

-   **Configurazione e distribuzione di certificati di autenticazione WLAN**: vengono descritte la creazione e la distribuzione di modelli di certificato X.509 richiesti per le autenticazioni WLAN 802.1X. È compresa anche la verifica della distribuzione.

-   **Configurazione dell'infrastruttura di accesso WLAN**: vengono descritte in dettaglio la creazione e la configurazione dei criteri di accesso remoto IAS per reti 802.1X basate sugli standard 802.1X e EAP-TLS. Sono incluse anche le AP come client RADIUS (Remote Authentication Dial-In User Service) dei server IAS.

-   **Attivazione di utenti e computer per reti WLAN protette**: viene descritta la configurazione di autorizzazioni per utenti e computer tramite Active Directory per consentire l'accesso alla rete WLAN protetta. In questa sezione sono inclusi anche i passaggi per la creazione e la distribuzione di criteri di gruppo basati su Active Directory per configurare i client WLAN con le impostazioni 802.1X e 802.11 appropriate.

-   **Configurazione di AP senza fili per reti basate sullo standard 802.1X**: sono elencati gli argomenti che è necessario tenere in considerazione durante la configurazione di AP senza fili per reti basate sullo standard 802.1X.

-   **Test e verifica**: viene fornita una procedura che consente di testare la funzionalità della rete WLAN basata sullo standard 802.1X.

[](#mainsection)[Inizio pagina](#mainsection)

### Foglio di lavoro di pianificazione WLAN 802.1X

Nella tabella che segue vengono elencati i parametri di configurazione utilizzati in questa soluzione. Devono essere considerati come un elenco di controllo quando si prendono le decisioni relative alla pianificazione.

Molti dei parametri riportati in queste tabelle vengono impostati manualmente come parte della procedura documentata in questo modulo. Molti vengono impostati da uno script eseguito come parte di una procedura, oppure viene fatto riferimento al parametro da uno script, per completare un'altra configurazione o un'attività operativa.

**Nota:** gli script utilizzati nella Guida realizzativa vengono descritti in più dettagliatamente nel file ToolsReadme.txt allegato agli script. Per ottenere gli script e il file readme.txt file, scaricare [*Securing Wireless LANs - A Microsoft® Windows Server™ 2003 Certificate Services Solution*](http://www.microsoft.com/downloads/details.aspx?familyid=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en) all'indirizzo http://www.microsoft.com/downloads/details.aspx?FamilyID=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en (in inglese).

#### Elementi di configurazione definiti dagli utenti

Prima di iniziare la procedura di installazione, è necessario assicurarsi di avere a disposizione o di avere già scelto le impostazioni per tutti gli elementi inclusi nella tabella che segue. Negli esempi dei comandi citati nell'intero modulo vengono utilizzati i valori fittizi mostrati qui. È necessario sostituire tali valori fittizi con i valori adeguati alla propria organizzazione. I valori che è necessario sostituire sono indicati in corsivo.

**Elementi di configurazione definiti dagli utenti**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento di configurazione</th>
<th>Impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nome DNS (Domain Name System) del dominio principale dell'insieme di strutture di Active Directory</td>
<td style="border:1px solid black;"><em>woodgrovebank.com</em></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome di dominio NetBIOS (network basic input/output system)</td>
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
<td style="border:1px solid black;">Nome del server IAS filiale facoltativo</td>
<td style="border:1px solid black;"><em>BO - IAS - 03</em></td>
</tr>
</tbody>
</table>
  
#### Elementi di configurazione indicati dalla soluzione
  
Nel caso di un'installazione specifica non è necessario modificare le impostazioni indicate in questa tabella, a meno che non sia necessario utilizzare un'impostazione diversa da quella offerta dalla soluzione. La modifica dei parametri di progettazione forniti in questa tabella è perfettamente accettabile, ma occorre essere consapevoli del fatto che così facendo ci si discosta dalla soluzione collaudata. Prima di modificare eventuali valori qui indicati, assicurarsi di aver compreso a fondo le implicazioni della modifica che si intende apportare e le dipendenze che tale impostazione potrebbe avere nelle procedure di configurazione o negli script forniti.
  
**Elementi di configurazione indicati dalla soluzione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento di configurazione</th>
<th>Impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">[Account] gruppo globale di Active Directory contenente utenti che richiedono certificati di autenticazione 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica autenticazione client — Certificato utente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] gruppo globale precedente a Windows 2000 contenente utenti che richiedono certificati di autenticazione 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica autenticazione client — Certificato utente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] gruppo globale di Active Directory contenente computer che richiedono certificati di autenticazione 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica autenticazione client — Certificato computer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] gruppo globale precedente a Windows 2000 contenente computer che richiedono certificati di autenticazione 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica autenticazione client — Certificato computer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] gruppo globale di Active Directory contenente server IAS che richiedono certificati di autenticazione 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica del certificato di autenticazione server RAS e IAS</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] gruppo globale precedente a Windows 2000 per il gruppo globale di Active Directory contenente server IAS che richiedono certificati di autenticazione 802.1X</td>
<td style="border:1px solid black;">Registrazione automatica del certificato di autenticazione server RAS e IAS</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] gruppo globale di Active Directory contenente utenti ai quali è consentito l'accesso alla rete senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Utenti senza fili</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] gruppo globale precedente a Windows per il gruppo globale di Active Directory contenente utenti ai quali è consentito l'accesso alla rete senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Utenti senza fili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] gruppo globale di Active Directory contenente computer ai quali è consentito l'accesso alla rete senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Computer senza fili</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] gruppo globale di Active Directory contenente computer ai quali è consentito l'accesso alla rete senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Computer senza fili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] gruppo universale di Active Directory contenente sia il gruppo di utenti senza fili che il gruppo computer senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Accesso senza fili</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] gruppo universale di Active Directory contenente sia il gruppo di utenti senza fili che il gruppo computer senza fili</td>
<td style="border:1px solid black;">Criteri di accesso remoto - Accesso senza fili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] gruppo globale di Active Directory contenente computer che richiedono la configurazione delle proprietà di rete senza fili</td>
<td style="border:1px solid black;">Criteri di rete senza fili — Computer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] gruppo globale di Active Directory contenente computer che richiedono la configurazione delle proprietà di rete senza fili</td>
<td style="border:1px solid black;">Criteri di rete senza fili — Computer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Certificati] modello di certificato utilizzato per generare certificati per l'autenticazione di utenti client</td>
<td style="border:1px solid black;">Autenticazione client — Utente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Certificati] modello di certificato utilizzato per generare certificati per l'autenticazione di computer client</td>
<td style="border:1px solid black;">Autenticazione client — Computer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Certificati] modello di certificato utilizzato per generare certificati di autenticazione server per l'utilizzo da parte del Servizio di autenticazione Internet (IAS, Internet Authentication Service)</td>
<td style="border:1px solid black;">Autenticazione server RAS e IAS</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Script] Percorso per gli script di installazione</td>
<td style="border:1px solid black;">C:\MSSScripts</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Config] Percorso per i file di backup della configurazione</td>
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
<td style="border:1px solid black;">Criteri di rete senza fili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Criteri di gruppo] Criteri di rete senza fili all'interno dell'oggetto Criteri di gruppo (GPO, Group Policy Object)</td>
<td style="border:1px solid black;">Configurazione computer client senza fili</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Preparazione dell'ambiente per una rete WLAN protetta
  
Prima di implementare la senza fili basata sul protocollo 802.1X, è necessario ottimizzare l'infrastruttura di supporto nell'ambiente. L'infrastruttura di supporto include i server Active Directory e DHCP. Per informazioni dettagliate sulla pianificazione di una rete WLAN, vedere il libro "[Deploying a Wireless LAN](http://technet.microsoft.com/en-us/library/cc780901.aspx)" (in inglese) del *Windows Server 2003 Deployment Kit* e altre risorse elencate nella sezione "[Ulteriori informazioni](#xsltsection134121120120)" alla fine del modulo.
  
#### Creazione di gruppi di Active Directory richiesti per l'accesso alla rete WLAN
  
È necessario eseguire il seguente script come utente che dispone dell'autorizzazione a creare gruppi di protezione Active Directory. Questo script crea i gruppi richiesti per la registrazione di certificati di autenticazione senza fili, criteri di accesso remoto e criteri di gruppo per reti senza fili:  
Cscript //job:CreateWirelessGroups C:\\MSSScripts\\wl\_tools.wsf
  
Lo script crea i seguenti gruppi di protezione basati su Active Directory che vengono utilizzati nell'intera guida:
  
-   Registrazione automatica autenticazione client — Certificato utente
  
-   Registrazione automatica autenticazione client — Certificato computer
  
-   Registrazione automatica del certificato di autenticazione server RAS e IAS
  
-   Criteri di accesso remoto — Utenti senza fili
  
-   Criteri di accesso remoto — Computer senza fili
  
-   Criteri di accesso remoto — Accesso senza fili
  
-   Criteri di rete senza fili — Computer
  
Per un insieme di strutture con più domini, creare questi gruppi nello stesso dominio al quale appartengono gli utenti senza fili. Sebbene non sia essenziale (poiché vengono creati come gruppi globali), nel resto della guida sarà dato per scontato.
  
#### Verifica delle impostazioni DHCP
  
Per utilizzare una rete senza fili, è necessario configurare i server DHCP con ambiti specifici per tecnologie senza fili e tempi di lease degli indirizzi IP (Internet Protocol) più brevi rispetto a quelli per i client con fili. Rivolgersi agli amministratori dei server DHCP per verificare che tali server siano stati configurati correttamente per supportare la soluzione senza fili.
  
Per informazioni approfondite sulla pianificazione DHCP, vedere il libro "[Deploying a Wireless LAN](http://technet.microsoft.com/en-us/library/cc780901.aspx)" (in inglese) del *Windows Server 2003 Deployment Kit.*
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione e distribuzione di certificati di autenticazione WLAN.
  
La soluzione di rete WLAN protetta descritta in questa guida utilizza certificati X.509 per eseguire l'autenticazione di computer e utenti utilizzando EAP-TLS. Nella sezione che segue vengono descritte in dettaglio la creazione e la distribuzione dei seguenti certificati:
  
-   Autenticazione client — Computer
  
-   Autenticazione client — Utente
  
-   Autenticazione server RAS e IAS
  
**Nota:** per ulteriori informazioni su queste operazioni e sui ruoli necessari per eseguirle, vedere il modulo "[Gestione dell'infrastruttura chiavi pubbliche](http://technet.microsoft.com/it-it/library/dd536252)" della *Guida operativa*.
  
#### Creazione di un modello di certificato per l'autenticazione server
  
Un certificato server è necessario sul server IAS per autenticare il computer ai client che eseguono l'handshake del protocollo EAP-TLS. Chiedere all'amministratore dei Servizi certificati di eseguire i seguenti passaggi utilizzando lo snap-in Microsoft Management Console (MMC) Modelli di certificato sul server Servizi certificati per creare un modello di autenticazione server da usare con i server IAS.
  
-   **Per creare un modello di certificato per server senza fili**
  
    1.  Creare un duplicato del modello di certificato server del Servizio di accesso remoto (RAS, Remote Access Service) e server IAS e assegnare al nuovo modello il nome **Autenticazione server RAS e IAS Server** digitando il nome nella casella **Nome visualizzato modello** della scheda **Generale** della pagina delle proprietà del modello.
  
    2.  Nella scheda **Estensioni** assicurarsi che i criteri di applicazione includano solo **Autenticazione server (OID 1.3.6.1.5.5.7.3.1)**.
  
    3.  Inoltre, nella scheda **Estensioni** modificare i criteri di rilascio e aggiungere il criterio **Medium Assurance** .
  
    4.  Nella scheda **Nome soggetto** selezionare **Crea in base alle informazioni di Active Directory**. Assicurarsi inoltre che **Formato del nome soggetto** sia impostato su **Nome comune** e che in **Includere le seguenti informazioni nel nome soggetto alternativo** sia selezionato soltanto **Nome DNS**.
  
    5.  Nella scheda **Gestione richiesta** fare clic sul pulsante **CSP**, assicurarsi che sia selezionato **Requests must use one of the following CSPs** e che sia selezionato solo **Microsoft RSA SChannel Cryptographic Provider**.
  
    6.  Nella scheda **Protezione** aggiungere il gruppo di protezione Registrazione automatica del certificato di autenticazione server RAS e IAS (*WOODGROVEBAN*K\\Registrazione automatica del certificato di autenticazione server RAS e IAS) con autorizzazioni di **Lettura**, **Registrazione** e **Registrazione automatica**.
  
        **Importante:** rimuovere qualsiasi altro gruppo che dispone di autorizzazioni a registrare e/o registrare automaticamente questo modello di certificato. Gli utenti o i gruppi che devono registrare questi certificati devono essere aggiunti al gruppo rilevante di registrazione (o registrazione automatica) del modello di certificato. In tal modo si impedisce agli utenti o ai gruppi di registrare inavvertitamente certificati che essi non dovrebbero essere in grado di rilasciare.
  
Nel modulo "[Progettazione di un'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536257)" della *Guida operativa* viene descritta l'impostazione di questo tipo di certificato per richiedere l'approvazione del gestore dei certificati. Poiché questo è considerato un certificato di valore relativamente alto, potrebbe essere opportuno attivare questa opzione per fornire una verifica aggiuntiva come misura di protezione per il caso in cui venga registrato un server IAS inaffidabile. Ciò significa che per rilasciare il certificato è richiesta un'approvazione manuale (anche se la richiesta viene comunque inviata automaticamente al server IAS e il certificato viene recuperato automaticamente dopo l'approvazione).
  
#### Creazione di un modello di certificato per utenti senza fili
  
Un certificato utente è necessario per l'autenticazione di utenti finali nel server IAS durante l'autenticazione EAP-TLS. Chiedere all'amministratore del Servizio certificati di eseguire i seguenti passaggi utilizzando lo snap-in MMC Modelli di certificato sul server Servizi certificati per creare un modello di certificato di autenticazione utente.
  
-   **Per creare un modello di certificato di autenticazione utente**
  
    1.  Creare un duplicato del modello Sessione autenticata e assegnare al nuovo modello un nome digitando **Autenticazione client — Utente** nella casella **Nome visualizzato del modello** nella scheda **Generale**.
  
    2.  Nella scheda **Gestione richieste** selezionare **CSP** e deselezionare le caselle di controllo **Microsoft Base DSS Cryptographic Provider**.
  
    3.  Nella scheda **Nome soggetto** assicurarsi di selezionare **Crea in base alle informazioni di Active Directory** e sotto **Formato del nome soggetto** selezionare **Nome comune**. Assicurarsi che **Nome principale utente (UPN**) sia l'unica opzione selezionata sotto **Includere le seguenti informazioni nel nome soggetto alternativo**.
  
    4.  Nella scheda **Estensioni** assicurarsi che si incluso solo **Autenticazione client (OID 1.3.6.1.5.5.7.3.2)** in **Criteri di applicazione**.
  
    5.  Inoltre, nella scheda **Estensioni** modificare i criteri di rilascio e aggiungere il criterio **Medium Assurance**.
  
    6.  Nella scheda **Protezione** aggiungere il gruppo di protezione Registrazione automatica del certificato di autenticazione client — Certificato utente (*WOODGROVEBAN*K\\Registrazione automatica del certificato di autenticazione client — Certificato utente) con autorizzazioni di **Lettura**, **Registrazione** e **Registrazione automatica**.
  
        **Importante:** rimuovere qualsiasi altro gruppo che dispone di autorizzazioni a registrare e/o registrare automaticamente questo modello di certificato. Gli utenti o i gruppi che devono registrare questi certificati devono essere aggiunti al gruppo rilevante di registrazione (o registrazione automatica) del modello di certificato. In tal modo si impedisce agli utenti o ai gruppi di registrare inavvertitamente certificati che essi non dovrebbero essere in grado di rilasciare.
  
#### Creazione di un modello di certificato per utenti senza fili
  
Un certificato è necessario per l'autenticazione di computer nel server IAS durante l'autenticazione EAP-TLS. Chiedere all'amministratore del Servizio certificati di eseguire i seguenti passaggi utilizzando lo snap-in MMC Modelli di certificato sul server Servizi certificati per creare un modello di certificato di autenticazione computer.
  
-   **Per creare un modello di certificato di autenticazione computer**
  
    1.  Creare un duplicato del modello Autenticazione workstation e assegnare un nome al nuovo modello digitando **Autenticazione client — Computer** nella casella **Nome visualizzato del modello** nella scheda **Generale**.
  
    2.  Nella scheda **Nome soggetto** assicurarsi di selezionare **Crea in base alle informazioni di Active Directory** e sotto **Formato del nome soggetto** selezionare **Nome comune**. Assicurarsi che **Nome DNS**) sia l'unica opzione selezionata sotto **Includere le seguenti informazioni nel nome soggetto alternativo:**.
  
    3.  Nella scheda **Estensioni** modificare i criteri di applicazione e assicurarsi che sia selezionato solo **Autenticazione server (OID 1.3.6.1.5.5.7.3.2)**.
  
    4.  Inoltre, nella scheda **Estensioni** modificare i criteri di rilascio e aggiungere il criterio **Low Assurance**.
  
    5.  Nella scheda **Protezione** aggiungere il gruppo di protezione Registrazione automatica del certificato di autenticazione computer — Certificato utente (*WOODGROVEBAN*K\\Registrazione automatica del certificato di autenticazione client — Certificato utente) con autorizzazioni di **Lettura**, **Registrazione** e **Registrazione automatica**.
  
        **Importante:** rimuovere qualsiasi altro gruppo che dispone di autorizzazioni a registrare e/o registrare automaticamente questo modello di certificato. Gli utenti o i gruppi che devono registrare questi certificati devono essere aggiunti al gruppo rilevante di registrazione (o registrazione automatica) del modello di certificato. In tal modo si impedisce agli utenti o ai gruppi di registrare inavvertitamente certificati che essi non dovrebbero essere in grado di rilasciare.
  
#### Aggiunta dei certificati di autenticazione WLAN all'Autorità di certificazione
  
Una volta configurati i modelli di certificato di autenticazione WLAN, è necessario aggiungerli all'Autorità di certificazione (CA) per attivare la registrazione. Chiedere all'amministratore dei Servizi certificati di eseguire i seguenti passaggi per aggiungere modelli di certificato all'Autorità di certificazione.
  
-   **Per aggiungere modelli di certificato alla CA**
  
Dallo snap-in MMC Autorità di certificazione, fare doppio clic sulla cartella **Modelli di certificato**, quindi selezionare **Nuovo** e **Modello di certificato da emettere**. Selezionare i seguenti certificati, quindi fare clic su **OK**:
  
-   Autenticazione client — Computer
  
-   Autenticazione client — Utente
  
-   Autenticazione server RAS e IAS
  
#### Registrazione di un certificato server IAS
  
La distribuzione dei certificati di autenticazione server ai server IAS è una procedura relativamente semplice e automatizzata. Per eseguire questa operazione, completare i passaggi descritti nella sezione che segue.
  
-   **Per registrare un certificato di autenticazione server IAS dalla CA**
  
    1.  Utilizzare lo snap-in MMC Utenti e computer di Active Directory per aggiungere account computer IAS al gruppo di protezione Registrazione automatica certificato di autenticazione server RAS e IAS.
  
    2.  Accedere come membro del gruppo Administrators locali a un server IAS che è stato aggiunto al gruppo di protezione Registrazione automatica certificato di autenticazione server RAS e IAS ed eseguire GPUPDATE /force dal prompt dei comandi.
  
    3.  Aprire la console MMC, quindi aggiungere lo snap-in **Certificati**. Quando viene richiesto, selezionare l'opzione **Account del computer**, quindi selezionare **Computer locale**.
  
        **Suggerimento:** se l'opzione **Account del computer** non viene visualizzata, significa che probabilmente non si dispone di diritti di amministratore sul computer locale.
  
    4.  Selezionare **Certificati (computer locale)** dalla struttura della console, scegliere **Tutte le attività** dal menu **Azione**, quindi fare clic su **Registra automaticamente certificati**.
  
**Nota:** se l'opzione per richiedere l'approvazione del gestore dei certificati è stata selezionata per questo tipo di certificato, sarà necessario contattare l'amministratore CA per verificare se si tratta di una richiesta legittima per un server IAS. Una volta eseguita la verifica, l'amministratore CA rilascerà il certificato.
  
#### Verifica della distribuzione dei certificati server IAS
  
La velocità con cui un certificato server IAS registrato viene rilasciato e distribuito all'archivio di certificati server dipende dalle impostazioni relative all'approvazione dei certificati nel modello di certificato. È possibile inoltre che si verifichi un ritardo perché il server interroga la CA a intervalli di qualche ora.
  
-   **Per verificare che il certificato di autenticazione server IAS sia stato distribuito**
  
    1.  Accedere come membro del gruppo Administrators locali al computer locale, aprire la console MMC, quindi aggiungere lo snap-in **Certificati**. Quando viene richiesto, selezionare l'opzione **Account del computer** e selezionare **Computer locale**.
  
        **Suggerimento:** se l'opzione **Account del computer** non viene visualizzata, significa che probabilmente non si dispone di diritti di amministratore sul computer locale.
  
    2.  Aprire l'archivio **Certificati (computer locali)**, **Personale**, **Certificati** e cercare un certificato rilasciato al nome del computer locale dal modello di certificato di autenticazione server RAS e IAS. Il nome del modello è visualizzato nel riquadro di destra. Per visualizzare la colonna appropriata potrebbe essere necessario scorrere la schermata orizzontalmente.
  
    3.  Se il certificato richiesto non è visualizzato nello snap-in **Certificati**, selezionare **Certificati (computer locale)** dalla struttura della console, scegliere **Tutte le attività** dal menu **Azione**, selezionare **Registra automaticamente certificati**. Attendere qualche istante, quindi aggiornare la visualizzazione della cartella Personale, Certificati.
  
        **Suggerimento:** è possibile riavviare il server per imporre la registrazione automatica del certificato. Se la registrazione del certificato è stata eseguita correttamente, nel Registro eventi applicazioni sarà presente un evento con origine Registrazione automatica e un ID evento 19.
  
#### Aggiunta di utenti e computer ai gruppi per la registrazione automatica
  
La distribuzione di certificati di autenticazione WLAN a utenti e computer è relativamente semplice per gli utenti finali. La procedura richiede una connessione a una rete LAN, un account utente basato su dominio e un computer associato a un dominio Active Directory.
  
Gli utenti e i computer che richiederanno l'accesso alla nuova rete WLAN devono disporre di certificati distribuiti prima dell'implementazione della nuova rete, per assicurare che sia possibile eseguire l'autenticazione EAP-TLS. Se si utilizza Windows XP e Windows Server 2003, sia i certificati computer che quelli utente possono essere registrati automaticamente senza l'intervento dell'utente finale. La registrazione e il rinnovo di certificati sono controllati tramite i gruppi di protezione di Active Directory.
  
-   **Per aggiungere utenti e computer ai gruppi di protezione per la registrazione automatica**
  
    1.  Aprire lo snap-in MMC Utenti e computer di Active Directory.
  
    2.  Aggiungere utenti al gruppo Registrazione automatica autenticazione client - Certificato utente.
  
    3.  Aggiungere computer al gruppo Registrazione automatica autenticazione client - Certificato computer.
  
##### Verifica della distribuzione di certificati utente
  
Eseguire i seguenti passaggi dopo aver effettuato l'accesso come utente che è stato aggiunto al gruppo Registrazione automatica autenticazione client - Certificato utente.
  
-   **Per verificare la distribuzione di certificati di autenticazione utente**
  
    1.  Aprire la console MMC, quindi aggiungere lo snap-in **Certificati**. Se viene richiesto, selezionare l'opzione **Account dell'utente**.
  
    2.  Aprire l'archivio **Certificati - Utente corrente**, **Personale**, **Certificati** e cercare un certificato rilasciato all'utente dal modello di certificato di autenticazione server RAS e IAS. Il nome del modello dovrebbe essere visualizzato nel riquadro di destra. Per visualizzare la colonna appropriata potrebbe essere necessario scorrere la schermata orizzontalmente.
  
    3.  Se il certificato richiesto non è visualizzato nello snap-in **Certificati**, eseguire GPUPDATE /force dal prompt dei comandi, attendere qualche minuto, quindi aggiornare la visualizzazione della cartella Personale, Certificati.
  
##### Verifica della distribuzione di certificati computer
  
Eseguire i seguenti passaggi da un computer client che è stato aggiunto al gruppo Registrazione automatica autenticazione client — Certificato computer.
  
-   **Per verificare la distribuzione di certificati di autenticazione computer**
  
    1.  Accedere come membro del gruppo Administrators locali al computer locale, aprire la console MMC, quindi aggiungere lo snap-in **Certificati**. Quando viene richiesto, selezionare l'opzione **Account del computer** e selezionare **Computer locale**.
  
        **Suggerimento:** Se l'opzione **Account del computer** non viene visualizzata, significa che probabilmente non si dispone di diritti di amministratore sul computer locale.
  
    2.  Aprire l'archivio **Certificati (computer locali)**, **Personale**, **Certificati** e cercare un certificato rilasciato al nome del computer locale dal modello di certificato di autenticazione client — Certificato computer. Il nome del modello dovrebbe essere visualizzato nel riquadro di destra. Per visualizzare la colonna appropriata potrebbe essere necessario scorrere la schermata orizzontalmente.
  
    3.  Se il certificato richiesto non è visualizzato nello snap-in **Certificati**, eseguire GPUPDATE /force dal prompt dei comandi, attendere qualche minuto, quindi aggiornare la visualizzazione della cartella Personale, Certificati.
  
        **Suggerimento:** è possibile riavviare il computer per imporre la registrazione automatica del certificato. Se la registrazione del certificato è stata eseguita correttamente, nel Registro eventi applicazioni sarà presente un evento con origine Registrazione automatica e un ID evento 19.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione dell'infrastruttura di accesso WLAN
  
È necessario configurare il server IAS primario con criteri di accesso remoto e impostazioni di richiesta di connessione che determinano l'autenticazione e l'autorizzazione di utenti e computer senza fili alla rete WLAN. Queste impostazioni devono essere quindi replicate ai server IAS aggiuntivi con ruolo simile utilizzando il comando **netsh** descritto nella *Guida realizzativa RADIUS* o nella *Guida operativa*. Inoltre, ciascun server IAS deve essere configurato in maniera univoca per accettare le connessioni da parte di client RADIUS quali, ad esempio, AP senza fili. Gli AP senza fili devono essere configurati per utilizzare server IAS come origine dell'autenticazione e accounting per la rete 802.1X.
  
#### Creazione di un criterio di accesso remoto IAS per reti WLAN
  
Eseguire i seguenti passaggi utilizzando lo snap-in MMC Servizio di autenticazione Internet (IAS, Internet Authentication Service) per configurare IAS con un criterio di accesso remoto per reti senza fili.
  
-   **Per Creare un criterio di accesso remoto in IAS**
  
    1.  Fare clic con il pulsante destro del mouse sulla cartella Criteri di accesso remoto, quindi selezionare **Create New Remote Access Policy**.
  
    2.  Assegnare al criterio il nome **Consenti accesso senza fili** e nella procedura guidata impostare **Procedura guidata per impostare un criterio tipico per scenari**.
  
    3.  Scegliere **Senza fili** come metodo di accesso.
  
    4.  Consentire l'accesso in base al gruppo e utilizzare il gruppo **Criteri di accesso remoto - Accesso senza fili (WOODGROVEBANK\\Criteri di accesso remoto - Accesso senza fili)**.
  
    5.  Scegliere **Smart Card o altro certificato** per il protocollo Extensible Authentication Protocol (EAP), quindi selezionare il certificato di autenticazione server installato per IAS. Completare la procedura e uscire dalla procedura guidata.
  
        **Nota:** il nuovo criterio Consenti accesso senza fili può coesistere con altri criteri di accesso remoto creati dall'utente o con i criteri di accesso remoto predefiniti. Assicurarsi, tuttavia, che i criteri di accesso remoto predefiniti siano stati eliminati o elencati dopo il criterio Consenti accesso senza fili nella cartella Criteri di accesso remoto.
  
##### Modifica delle impostazioni del profilo dei Criteri di accesso WLAN
  
Il criterio di accesso remoto creato in precedenza dovrebbe essere configurato utilizzando impostazioni predefinite, includendo l'impostazione che consente di ignorare le impostazioni di connessione remota da Active Directory che possono provocare potenziali problemi con alcuni tipi di AP senza fili. Inoltre, gli attributi RADIUS dovrebbero essere impostati per la nuova autenticazione client a intervalli prestabiliti per assicurare che vengano aggiornate le chiavi di sessione Wired Equivalent Privacy (WEP). Per ulteriori informazioni sulle impostazioni dei criteri di accesso remoto, vedere il modulo "[Progettazione della protezione di reti LAN senza fili mediante lo standard 802.1X](http://technet.microsoft.com/it-it/library/dd536259)" della *Guida operativa*.
  
-   **Per modificare le impostazioni del profilo dei criteri di accesso senza fili**
  
    1.  Aprire la pagina delle proprietà del criterio Consenti accesso senza fili, quindi fare clic su **Modifica profilo**.
  
    2.  Nella scheda **Limitazioni chiamate in ingresso** selezionare l'opzione **Limite massimo di minuti per la connessione del client (timeout sessione)**, quindi immettere come valore **10 minuti**.
  
    3.  Nella scheda **Avanzate** aggiungere l'attributo **Ignorare le proprietà della connessione remota dell'utente**, impostarlo su **Vero**, quindi aggiungere l'attributo **Termination-Action** e impostarlo su **RADIUS Request**.
  
##### Verifica del criterio di richiesta di connessione per reti WLAN
  
Il criterio di richiesta di connessione IAS predefinito è configurato in modo tale che IAS autentica utenti e computer direttamente effettuando un confronto con Active Directory. Eseguire i seguenti passaggi per verificare la configurazione del criterio di richiesta di connessione predefinito.
  
-   **Per verificare la configurazione del criterio di richiesta di connessione predefinito**
  
    1.  Aprire lo snap-in MMC Servizio autenticazione Internet (IAS, Internet Authentication Service) e visualizzare le proprietà del criterio di richiesta di connessione **Utilizzare autenticazione Windows per tutti gli utenti**.
  
    2.  Verificare che le condizioni del criterio contengano **Date-And-Time-Restrictions matches "Sun 00:00-24:00; Mon 00:00-24:00; Tue 00:00-24:00; Thu 00:00-24:00; Fri 00:00-24:00; Sat 00:00-24:00"**.
  
    3.  Fare clic sul pulsante **Modifica profilo**, quindi sulla scheda **Autenticazione** e assicurarsi che sia selezionata l'opzione **Autentica le richieste su questo server**.
  
    4.  Assicurarsi che siano presenti regole nella scheda **Attributi**.
  
        **Nota:** per questa soluzione non sono richieste impostazioni aggiuntive per il criterio di richiesta di connessione. Tuttavia, è possibile che la propria organizzazione preveda impostazioni aggiuntive adatte per esigenze diverse.
  
##### Aggiunta di client RADIUS a IAS
  
È necessario aggiungere proxy AP senza fili e RADIUS come client RADIUS a IAS prima di consentire che usufruiscano dei servizi di autenticazione e accounting tramite il protocollo RADIUS. Per aggiungere AP senza fili a IAS, eseguire i seguenti passaggi dallo snap-in MMC Servizio autenticazione Internet (IAS, Internet Authentication Server).
  
-   **Per aggiungere client RADIUS a IAS**
  
    1.  Fare clic con il pulsante destro del mouse sulla cartella **RADIUS Clients**, quindi selezionare **New RADIUS Client**.
  
    2.  Immettere un nome descrittivo e l'indirizzo IP dell'AP senza fili.
  
    3.  Selezionare **RADIUS Standard** come attributo Client-Fornitore, quindi immettere il segreto condiviso per l'AP senza fili (per generare il segreto, è possibile utilizzare lo script GenPwd descritto di seguito). Quindi selezionare l'attributo **Request must contain the Message Authenticator**.
  
**Nota:** è possibile che per funzionare correttamente, alcuni client RADIUS richiedano attributi specifici del fornitore (VSA, Vendor-Specific Attributes). Per informazioni relative ai requisiti VSA, consultare la documentazione specifica del fornitore.
  
È possibile utilizzare lo script GenPwd incluso in questa guida per generare segreti pseudo-casuali avanzati a 23 caratteri per l'uso individuale da parte di ciascun AP senza fili configurato come client RADIUS. Lo script GenPwd genererà un segreto e lo archivierà insieme a un nome descrittivo per ciascun client RADIUS in un file denominato Clients.txt. GenPwd aggiunge automaticamente le informazioni al file Clients.txt nella directory corrente sotto forma di valori separati da virgola.
  
Si consiglia di conservare questo file su disco floppy o su altro supporto rimovibile con l'etichetta "Client RADIUS per server H*Q-IAS-0*1" sostituendo H*Q-IAS-0*1 con il nome del proprio server. Lo stesso disco, specifico del server, viene utilizzato per eseguire l'esportazione e l'importazione di client RADIUS nel modulo "[Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili](http://technet.microsoft.com/it-it/library/dd536253)" della *Guida operativa*.
  
-   **Per generare segreti RADIUS in un file Clients.txt utilizzando lo script GenPwd**
  
    1.  Accedere al prompt dei comandi e impostare A come directory corrente. Se si utilizza un tipo di supporto diverso dal disco floppy, usare la lettera di unità relativa a tale supporto. La posizione della directory di file system è importante in quanto nel file Clients.txt presente nella directory predefinita verranno automaticamente aggiunte le nuove informazioni. Se non esiste, il file Clients.txt verrà creato.
  
    2.  Eseguire il seguente comando. Assicurarsi di sostituire \[nome client\] con un nome descrittivo dell'AP senza fili, ad esempio un nome DNS o un'altra stringa:  
        **Cscript //job:GenPWD C:\\MSSScripts\\wl\_tools.wsf /client:\[nome client\]**
  
Conservare il disco di archiviazione client RADIUS in un luogo sicuro e accessibile nel caso in cui si renda necessario un ripristino di emergenza. Una volta creato, il file con valori separati da virgola può essere importato facilmente in un foglio di calcolo o in un'applicazione database e utilizzato come riferimento oppure modificato.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attivazione di utenti e computer per reti WLAN protette
  
I passaggi finali per l'attivazione di utenti e computer per l'accesso a una rete WLAN protetta sono costituiti da operazioni che devono essere eseguite su oggetti Active Directory. Tra queste operazioni sono incluse la verifica di autorizzazioni account, la modifica dell'appartenenza ai gruppi e l'implementazione di criteri di gruppo. È possibile eseguire questi passaggi in maniera controllata seguendo un programma di distribuzione graduale in modo da ridurre i rischi inerenti a una modifica significativa dell'ambiente.
  
#### Verifica delle autorizzazioni di accesso remoto Active Directory
  
Per poter utilizzare i criteri di accesso remoto, gli account di utenti e computer di Active Directory devono disporre delle corrette autorizzazioni di accesso remoto. Per impostazione predefinita, le autorizzazioni di accesso remoto su account in un dominio Active Directory in modalità originale sono impostate su **Controlla accesso tramite Criteri di accesso remoto**, pertanto una modifica in genere non è necessaria.
  
Tuttavia, è possibile verificare che gli utenti e i computer di destinazione siano configurati correttamente utilizzando lo snap-in MMC Utenti e computer di Active Directory. Verificare che l'opzione **Controlla accesso tramite Criteri di accesso remoto** sia selezionata per l'impostazione **Autorizzazione di accesso remoto (chiamata in ingresso o VPN)** nella scheda **Chiamate in ingresso** delle proprietà dell'account.
  
#### Aggiunta di utenti a gruppi di Criteri di accesso remoto
  
I criteri di accesso remoto basati su IAS utilizzano gruppi di protezione basati su Active Directory per determinare se gli utenti e i computer sono autorizzati ad accedere alla rete WLAN. I gruppi di protezione creati in precedenza in questo modulo includono quelli descritti nella seguente tabella.
  
**Tabella 3. Gruppi di protezione di Active Directory**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo di protezione</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Criteri di accesso remoto - Utenti senza fili</td>
<td style="border:1px solid black;">Gruppo globale per utenti che richiedono l'accesso alla rete WLAN</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri di accesso remoto - Computer senza fili</td>
<td style="border:1px solid black;">Gruppo globale di computer che richiedono l'accesso alla rete WLAN</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri di accesso remoto - Accesso senza fili</td>
<td style="border:1px solid black;">Gruppo universale che dovrebbe contenere i due gruppi globali precedenti</td>
</tr>
</tbody>
</table>
  
Utilizzando lo snap-in MMC Utenti e computer di Active Directory aggiungere il gruppo **Criteri di accesso remoto - Utenti senza fili (WOODGROVEBANK\\Criteri di accesso remoto - Utenti senza fili**) e il gruppo **Criteri di accesso remoto - Computer senza fili (WOODGROVEBANK\\Criteri di accesso remoto - Computer senza fili)** al gruppo **Criteri di accesso remoto - Accesso senza fili (WOODGROVEBANK\\Criteri di accesso remoto - Accesso senza fili)**.
  
Ora la struttura di gruppo è pronta per essere popolata con utenti e computer che saranno autorizzati ad accedere alla rete WLAN.
  
-   **per aggiungere utenti e computer ai gruppi di accesso alla rete WLAN**
  
    1.  Aprire lo snap-in MMC Utenti e computer di Active Directory.
  
    2.  Aggiungere gli utenti che disporranno dell'autorizzazione di accesso alla rete WLAN al gruppo **Criteri di accesso remoto - utenti senza fili (WOODGROVEBANK\\Criteri di accesso remoto - utenti senza fili)**.
  
    3.  Aggiungere i computer che disporranno dell'autorizzazione di accesso alla rete WLAN al gruppo **Criteri di accesso remoto - computer senza fili (WOODGROVEBANK\\Criteri di accesso remoto - computer senza fili)**.
  
**Nota:** per ulteriori informazioni sul perché devono essere attivata sia l'autenticazione degli utenti che dei computer per l'accesso alla rete WLAN, vedere il modulo "[Progettazione della protezione di reti LAN senza fili mediante lo standard 802.1X](http://technet.microsoft.com/it-it/library/dd536259)" nella *Guida operativa*.
  
#### Creazione di criteri di gruppo WLAN di Active Directory
  
È possibile automatizzare e imporre la configurazione WLAN di computer client utilizzando gli strumenti di Criteri di gruppo basati su Windows 2003. Questi strumenti consentono di configurare le impostazioni dei **Criteri di rete senza fili** , incluse le impostazioni relative alla protezione basata sullo standard 802.1X e al comportamento delle reti WLAN 802.11.
  
Per creare un profilo di criterio di gruppo per reti senza fili per i computer client della nuova rete WLAN basata sullo standard 802.1X, eseguire i seguenti passaggi utilizzando lo snap-in MMC Utenti e computer di Active Directory.
  
**Nota:** La creazione di GPO a livello di dominio potrebbe non essere adatta per tutte le organizzazioni. Pertanto, per determinare la posizione ottimale per i GPO, è necessario esaminare la strategia dei criteri di gruppo specifica della propria organizzazione.
  
-   **Per creare un criterio di gruppo per la rete senza fili**
  
    1.  Selezionare le proprietà dell'oggetto dominio (ad esempio w*oodgrovebank.co*m) e nella scheda **Criteri di gruppo** fare clic su **Nuovo** e assegnare al GPO il nome **Criteri di rete senza fili**.
  
    2.  Fare clic sul pulsante **Proprietà** e nella scheda **Protezione** assicurarsi che per il gruppo di protezione **Criteri di rete senza fili — Computer (WOODGROVEBANK\\Criteri di rete senza fili — Computer)** le autorizzazioni di **Lettura** e **Applica criteri di gruppo** siano impostate su **Consenti**. Inoltre, rimuovere Authenticated Users dal GPO. Nella scheda **Generale** selezionare **Disattiva impostazioni configurazione utente** sull'oggetto criteri e selezionare **Sì** quando vengono visualizzati messaggi di avviso. Applicare le modifiche e chiudere la finestra delle proprietà GPO.
  
    3.  Fare clic sul pulsante **Modifica** per modificare il criterio e andare a \\Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Wireless Network (Institute of Electrical and Electronic Engineers, or IEEE 802.11) Policies.
  
    4.  Selezionare l'oggetto **Wireless Network (IEEE 802.11) Policies** dal riquadro di spostamento, quindi selezionare **Create Wireless Network Policy** dal menu **Azione**. Utilizzare la procedura guidata per assegnare al criterio il nome **Configurazione senza fili computer client**. Lasciare selezionata l'opzione **Modifica proprietà** e fare clic su **Fine** per chiudere la procedura guidata.
  
    5.  Selezionare **Aggiungi** dalla scheda **Reti preferite** del criterio Configurazione senza fili computer client, quindi immettere il nome della rete o l'identificatore del set di servizi (SSID, Service Set Identifier) della rete senza fili.
  
        **Nota:** se i client utilizzano una rete WLAN esistente, è necessario scegliere un SSID diverso per la nuova rete LAN senza fili 802.1X. Immettere quindi il nuovo SSID nel profilo della rete senza fili 802.1X.
  
    6.  Fare clic sulla scheda **IEEE 802.1x**, quindi aprire le impostazioni per il tipo EAP **Smart Card o altro certificato**. Sotto **Autorità di certificazione fonte attendibile** selezionare le autorità di certificazione principali per i certificati del server IAS.
  
    7.  Chiudere la finestra delle proprietà per la Configurazione senza fili computer client e l'editor degli oggetti Criteri di gruppo.
  
#### Aggiunta di computer a gruppi di protezione per i criteri di gruppo WLAN
  
I gruppi di protezione basati su Active Directory vengono utilizzati per determinare i computer ai quali sono applicati criteri di rete senza fili e per i quali, pertanto, sono automaticamente configurate le impostazioni di rete senza fili 802.1X.
  
La distribuzione delle impostazioni dei criteri di gruppo per reti senza fili per la nuova rete basata sullo standard 802.1X devono essere configurate con grande anticipo rispetto alle impostazioni 802.1X sugli AP senza fili e all'attivazione della nuova WLAN. In tal modo si assicura che i computer client dispongano della possibilità di scaricare e applicare il criterio di gruppo basato sul computer, anche se si connettono alla rete LAN soltanto occasionalmente.
  
Inoltre, le impostazioni dei Criteri di gruppo possono essere applicate al computer prima che la scheda di rete WLAN (NIC, Network Interface Card) venga installata e configurata tramite Windows. Una volta installata una scheda di rete LAN senza fili, verranno automaticamente applicati a tale scheda i criteri di gruppo per la rete senza fili.
  
-   **Per aggiungere computer o gruppi ai criteri di gruppo per reti senza fili**
  
    -   Utilizzare lo snap-in MMC Utenti e computer di Active Directory per aggiungere computer al gruppo **Criteri di rete senza fili — Computer (WOODGROVEBANK\\Criteri di rete senza fili — Computer)**.
  
Notare che le impostazioni della rete senza fili verranno aggiornate sui computer client durante il successivo intervallo di aggiornamento dei Criteri di gruppo. È possibile utilizzare il comando **GPUPDATE /force** per imporre un aggiornamento dei criteri.
  
#### Verifica dell'applicazione dei criteri di gruppo WLAN
  
Eseguire i seguenti passaggi da un computer client che è stato aggiunto al gruppo di protezione Configurazione senza fili computer client in Active Directory.
  
**Nota:** affinché o criteri di rete senza fili siano visibili, è necessario che nei computer sia installata e riconosciuta da Windows una scheda di rete senza fili.
  
-   **Per verificare la distribuzione della configurazione di rete senza fili**
  
    1.  Accedere come Administrator al computer locale e aprire la cartella Connessioni di rete scegliendo **Esegui** del menu **Start** e digitando il seguente comando:  
        ncpa.cpl
  
    2.  Visualizzare le proprietà dell'icona **Connessione rete senza fili** che corrisponde alla scheda senza fili. Nella scheda **Reti senza fili** dovrebbe essere visualizzato sotto **Reti preferite** il nome SSID della nuova rete senza fili. Selezionare la nuova configurazione di rete senza fili e fare clic su **Proprietà** per esplorare le impostazioni e verificare che corrispondano a quelle scelte nei Criteri di gruppo per reti senza fili.
  
    3.  Se il nome SSID non è visualizzato sotto **Reti preferite** o le impostazioni di rete non corrispondono a quelle configurate in Criteri di gruppo per reti senza fili, chiudere tutte le finestre di dialogo Reti senza fili ed eseguire **GPUPDATE /force** dal prompt dei comandi. Verificare le impostazioni dopo qualche minuto.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione di AP senza fili per reti basate sullo standard 802.1X
  
La procedura per configurare AP senza fili varia drasticamente in base alla marca e al modello della periferica. Tuttavia, i fornitori di AP senza fili in genere forniscono le informazioni per la configurazione della periferica con:
  
-   Impostazioni di rete 802.1X.
  
-   Indirizzo IP del server di autenticazione RADIUS primario.
  
-   Indirizzo IP del server di accounting RADIUS primario.
  
-   Segreto RADIUS condiviso con il server RADIUS primario.
  
-   Indirizzo IP del server di autenticazione RADIUS secondario.
  
-   Indirizzo IP del server di accounting RADIUS secondario.
  
-   Segreto RADIUS condiviso con il server RADIUS secondario.
  
Per informazioni sulla configurazione di AP senza fili per lo standard 802.1X, vedere la documentazione specifica del fornitore.
  
Se nell'ambiente sono presenti utenti che stanno utilizzando AP senza fili senza impostazioni di protezione o impostazioni di WEP statica, sarà necessario sviluppare un piano di migrazione. Per ulteriori informazioni sulla migrazione da una rete senza fili esistente, vedere il modulo "[Progettazione della protezione di reti LAN senza fili mediante lo standard 802.1X](http://technet.microsoft.com/it-it/library/dd536259)" della *Guida operativa*. Sebbene fornire istruzioni sulla configurazione degli AP senza fili dei vari fornitori non rientri negli obiettivi di questa guida, nel presente modulo vengono trattati alcuni argomenti relativi alla protezione degli AP senza fili.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Collaudo e verifica
  
A questo punto è necessario collaudare la funzionalità della rete WLAN basata sullo standard 802.1X utilizzando un computer client configurato con un certificato computer, un certificato utente, Criteri di gruppo per reti senza fili e una scheda di rete WLAN.
  
-   **Per collaudare la funzionalità della rete senza fili**
  
    1.  Riavviare il computer client membro del gruppo Criteri di accesso remoto - Protezione computer senza fili (*WOODGROVEBAN*K\\Criteri di accesso remoto - Protezione computer senza fili).
  
    2.  Accedere al computer come utente membro del gruppo Criteri di accesso remoto - Utenti senza fili (*WOODGROVEBAN*K\\Criteri di accesso remoto - Utenti senza fili).
  
    3.  Dal prompt dei comandi utilizzare il comando **ping** per verificare la connettività a un altro computer della rete.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Dopo aver completato i passaggi descritti in questo modulo, si saranno eseguite le seguenti operazioni:
  
-   Creazione e configurazione di gruppi di protezione di Active Directory utilizzati per gestire i componenti della protezione WLAN.
  
-   Creazione di modelli di certificato richiesti e distribuzione dei certificati senza fili ai server IAS, selezione dei computer e degli utenti finali.
  
-   Creazione e configurazione di criteri di accesso remoto basati su IAS e criteri di richiesta di connessione per la rete senza fili.
  
-   Configurazione di AP senza fili per lo standard 802.1X.
  
-   Creazione di Criteri di gruppo per reti senza fili e distribuzione di tali criteri ai computer client.
  
A questo punto si dovrebbe disporre di una rete WLAN basata sullo standard 802.1X funzionante e protetta.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
-   Vedere "Managing Remote Access on a Per-Group Basis Using Windows 2000 Remote Access Policies" all'indirizzo [http://www.microsoft.com/windows2000/techinfo/administration/management/pgremote.asp](http://technet.microsoft.com/it-it/library/dd536251.aspx) (in inglese).
  
-   Per la documentazione dei prodotti contenente una panoramica delle funzioni IAS, le istruzioni di base per la configurazione e le procedure consigliate per la distribuzione, vedere il supporto tecnico per Windows Server 2003 all'indirizzo <http://support.microsoft.com/kb/324747> (informazioni in inglese).
  
-   Il "Supporting Mobile Users" *Microsoft Windows Server 2003 Resource Kit*, disponibile all'indirizzo: <http://technet.microsoft.com/en-us/library/cc782392.aspx> (in inglese). Il libro *Resource Kit* fornisce informazioni tecniche su IAS più dettagliate rispetto alla documentazione del prodotto e può essere utilizzato come riferimento nei casi in cui è necessario disporre di ulteriori informazioni.
  
-   Per informazioni dettagliate sui problemi di protezione WLAN relativi alle reti WLAN basate sullo standard 802.1X e su standard correlati, vedere [http://www.drizzle.com/~aboba/IEEE/](http://www.drizzle.com/~aboba/ieee/) (in inglese).
  
-   Per informazioni sulle soluzioni WLAN e informazioni sul settore, visitare il sito Web di Wi-Fi alliance all'indirizzo [http://www.wi-fialliance.org](http://www.wi-fialliance.org/) (in inglese).
  
-   Per informazioni sulle reti WLAN, comprese le informazioni di background, ricerche di mercato, white paper e programmi di formazione, visitare il centro formazione di Wireless LAN Association (WLANA) all'indirizzo <http://www.wlana.org/learning_center.html> (in inglese).
  
-   Per informazioni su EAP-TLS, EAP over LAN (EAPOL), EAP-RADIUS, RADIUS e altri standard Internet utilizzati con 802.1X, vedere il sito Web di Internet Engineering Task Force (IETF) all'indirizzo <http://www.ietf.org/> (in inglese).
  
-   Gli standard WLAN rilevanti includono: 802.11, 802.11b, 802.11a, 802.11g, 802.1X, 802.11i e altri. Informazioni su questi standard sono disponibili sul sito dell'Institute of Electrical and Electronics Engineers (IEEE) wireless standards all'indirizzo <http://standards.ieee.org/wireless/> (in inglese).
  
-   Per ulteriori informazioni sulle tecnologie WLAN 802.1X, vedere il white paper "Windows XP Wireless Deployment Technology and Component Overview," all'indirizzo <http://technet.microsoft.com/en-us/library/bb457015.aspx> (in inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
