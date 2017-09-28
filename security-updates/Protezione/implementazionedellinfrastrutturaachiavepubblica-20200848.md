---
TOCTitle: 'Implementazione dell''infrastruttura a chiave pubblica'
Title: 'Implementazione dell''infrastruttura a chiave pubblica'
ms:assetid: '6e3898b3-0edc-4d1e-884d-c50d4c5cd608'
ms:contentKeyID: 20200848
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536249(v=TechNet.10)'
---

Costruire una rete wireless locale sicura con Windows Server 2003 Certificate Services
======================================================================================

### Implementazione dell'infrastruttura a chiave pubblica

##### In questa pagina

[](#eoaa)[Argomenti del modulo](#eoaa)
[](#enaa)[Obiettivi](#enaa)
[](#emaa)[Ambito di applicazione](#emaa)
[](#elaa)[Utilizzo del modulo](#elaa)
[](#ekaa)[Panoramica](#ekaa)
[](#ejaa)[Specifiche di pianificazione di Servizi certificati](#ejaa)
[](#eiaa)[Creazione dei server](#eiaa)
[](#ehaa)[Preparazione di Active Directory per l'infrastruttura PKI](#ehaa)
[](#egaa)[Protezione di Windows Server 2003 per Servizi certificati](#egaa)
[](#efaa)[Altre attività di configurazione di Windows](#efaa)
[](#eeaa)[Installazione e configurazione della CA principale](#eeaa)
[](#edaa)[Installazione e configurazione della CA di emissione](#edaa)
[](#ecaa)[Configurazione post-creazione](#ecaa)
[](#ebaa)[Configurazione dei client](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Argomenti del modulo

Questo modulo fornisce le istruzioni complete per la creazione di un'infrastruttura a chiave pubblica (PKI) basata su Servizi certificati Microsoft® Windows® Server™ 2003. Questa procedura include l'installazione e la configurazione delle autorità di certificazione (CA, Certification Authority), la preparazione del servizio di directory Microsoft Active Directory® e di Microsoft Internet Information Services (IIS), infine la configurazione dei criteri di certificazione dei client. In questo modo si predispone l'infrastruttura di certificazione che verrà utilizzata nei moduli successivi di questa guida per la creazione della soluzione completa di protezione delle reti LAN senza fili (WLAN, Wireless LAN).

L'obiettivo di questo modulo è di fornire una guida all'implementazione dell'infrastruttura PKI descritta nel modulo "[Progettazione di un'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536257)" della *Guida alla pianificazione*. Questo modulo non intende illustrare i principi generali dell'infrastruttura PKI o i dettagli dell'implementazione di Servizi certificati Microsoft.

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Il modulo consente di:

-   Preparare Active Directory per l'infrastruttura PKI.

-   Proteggere i server Windows per Servizi certificati.

-   Installare e configurare una CA principale.

-   Installare e configurare una CA di emissione.

-   Attivare la registrazione automatica per i client.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Questo modulo si applica ai seguenti prodotti e tecnologie:

-   Microsoft Windows Server 2003

-   Servizi certificati Microsoft

-   Microsoft Active Directory

-   Microsoft Internet Information Services

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

Questo modulo offre una guida dettagliata che consente di creare un'infrastruttura PKI basata su Servizi certificati Microsoft Windows Server 2003.

Per sfruttare al massimo il presente modulo:

-   Leggere il modulo "[Progettazione di un'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536257)" della *Guida alla pianificazione* per comprendere i principi generali dell'infrastruttura PKI.

-   Utilizzare il foglio di lavoro "Certificate Services Planning Worksheet" disponibile in [*Microsoft Solution for Securing Wireless LANs*](http://www.microsoft.com/downloads/details.aspx?familyid=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en) (in inglese) come elenco di controllo dei parametri di configurazione dell'infrastruttura PKI utilizzati in questa soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica

La Figura 1 illustra in modo dettagliato il processo di creazione dell'infrastruttura PKI oggetto del presente modulo.

![](images/Dd536249.SGFG16101(it-it,TechNet.10).jpg)

**Figura 1**
*Diagramma del processo di creazione dell'infrastruttura PKI*

Nell'elenco seguente vengono descritte dettagliatamente le sezioni principali del modulo. Dopo ciascun passaggio di installazione o di configurazione significativo, viene incluso un passaggio di verifica che consente di controllare se le operazioni sono state eseguite correttamente prima di continuare con il passaggio successivo.

-   **Specifiche di pianificazione di Servizi certificati** — elenca le informazioni di configurazione utilizzate in questo modulo per installare e configurare Servizi certificati e include una tabella di informazioni che è necessario fornire prima di iniziare l'implementazione del modulo.

-   **Creazione dei server** — descrive la selezione e la configurazione dell'hardware, l'installazione di Windows Server 2003 e l'installazione dei componenti facoltativi, quali IIS.

-   **Preparazione di Active Directory per l'infrastruttura PKI** — descrive i requisiti della foresta e del dominio di Active Directory in cui l'infrastruttura PKI verrà implementata, insieme alla procedura di preparazione di base. Descrive inoltre la creazione di gruppi e di utenti di protezione e l'impostazione delle autorizzazioni corrette per la delega delle attività di gestione.

-   **Protezione di Windows Server 2003 per Servizi certificati** — descrive l'implementazione della protezione al livello di sistema operativo tramite l'applicazione dei modelli di protezione. I modelli utilizzati sono desunti dalla guida Windows Server 2003 Security Guide, disponibile all'indirizzo: [http://go.microsoft.com/fwlink/?LinkId=14845](http://go.microsoft.com/fwlink/?linkid=14845).

-   **Altre attività di configurazione di Windows** — elenca alcune attività comuni per il completamento dell'installazione di base dei server.

-   **Installazione e configurazione della CA principale** — descrive la procedura di preparazione, l'installazione del software e la configurazione di Servizi certificati, inclusa la definizione dei ruoli amministrativi del server. La pubblicazione del certificato della CA principale non in linea e dell'elenco di revoche di certificati (CRL, Certificate Revocation List) in Active Directory e nel server Web rappresenta la fase conclusiva.

-   **Installazione e configurazione della CA di emissione** — illustra una procedura analoga a quella prevista per la CA principale, ma include inoltre la richiesta di un certificato alla CA principale. La fase di verifica finale garantisce che sia possibile registrare i certificati della CA di emissione.

-   **Configurazione post-creazione** — descrive la configurazione dei tipi di certificati predefiniti rilasciati dalla CA di emissione, l'impostazione delle autorizzazioni per un insieme di strutture multidominio e l'esecuzione dei backup delle CA prima dell'introduzione nell'ambiente di produzione.

-   **Configurazione dei client** — descrive in che modo attivare la registrazione automatica per tutti gli utenti e i computer del dominio e come configurare i criteri di attendibilità dei certificati principali.

[](#mainsection)[Inizio pagina](#mainsection)

### Specifiche di pianificazione di Servizi certificati

Nelle tabelle seguenti sono elencati tutti i parametri di configurazione dell'infrastruttura PKI utilizzati in questa soluzione. Utilizzarle come elenco di controllo per le decisioni relative alla pianificazione.

Molti dei parametri contenuti in queste tabelle vengono impostati manualmente nel corso della procedura documentata in questo modulo. Altri vengono impostati tramite uno script eseguito nel corso di una delle procedure oppure eseguito per completare altre attività operative o di configurazione. In questo caso, il nome dello script è incluso nella tabella.

**Nota:** gli script utilizzati nella *Guida all'implementazione* sono descritti più dettagliatamente nel file readme.txt che accompagna gli script (disponibile con la guida completa [*Microsoft Solution for Securing Wireless LANS*](http://www.microsoft.com/downloads/details.aspx?familyid=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en) all'indirizzo http://www.microsoft.com/downloads/details.aspx?FamilyID=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en) (in inglese).

#### Elementi di configurazione definiti dall'utente

Prima di iniziare la procedura di installazione è necessario assicurarsi che siano state raccolte o definite le impostazioni per tutti gli elementi contenuti nella tabella seguente. I valori fittizi indicati nel modulo vengono utilizzati nei comandi di esempio forniti, ma devono essere sostituiti con i valori relativi alla propria organizzazione. Le voci in cui è necessario sostituire i valori sono riportate in corsivo.

**Tabella 1. Elementi di configurazione definiti dall'utente**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Elemento di configurazione</p></th>
<th><p>Impostazione</p></th>
<th><p>Riferimento script</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>DNS (Domain Name System) nome del dominio principale dell'insieme di strutture di Active Directory</p></td>
<td style="border:1px solid black;"><p>woodgrovebank.com</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>DN (Distinguished Name) nome distinto della directory principale dell'insieme di strutture</p></td>
<td style="border:1px solid black;"><p>DC=woodgrovebank,DC=com</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Nome NetBIOS (Network Basic Input/Output System) del dominio</p></td>
<td style="border:1px solid black;"><p>WOODGROVEBANK</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Nome NetBIOS del gruppo di lavoro della CA principale</p></td>
<td style="border:1px solid black;"><p>WGB-Root</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Nome server della CA principale</p></td>
<td style="border:1px solid black;"><p>HQ-CA-01</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Nome server della CA di emissione</p></td>
<td style="border:1px solid black;"><p>HQ-CA-02</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>X.500 Nome comune (CN) della CA principale</p></td>
<td style="border:1px solid black;"><p>WoodGrove Bank Root CA</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>X.500 CN della CA di emissione</p></td>
<td style="border:1px solid black;"><p>WoodGrove Bank Issuing CA 1</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Nome host completo del server Web utilizzato per pubblicare il certificato della CA e le informazioni di revoca</p></td>
<td style="border:1px solid black;"><p>www.woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
</tbody>
</table>
  
#### Elementi di configurazione prescritti dalla soluzione
  
Non è necessario modificare le impostazioni elencate in questa tabella per un'installazione particolare, a meno che non sia richiesto specificatamente l'utilizzo un'impostazione diversa dalla quella prevista dalla soluzione. È possibile modificare i parametri specificati, tuttavia, è necessario comprendere che in questo modo si apportano variazioni alla soluzione testata. Prima di modificare i valori riportati nelle procedure di configurazione o negli script forniti, assicurarsi di aver compreso pienamente le implicazioni della modifica e le dipendenze dell'impostazione modificata.
  
**Tabella 2. Elementi di configurazione prescritti dalla soluzione**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Elemento di configurazione</p></th>
<th><p>Impostazione</p></th>
<th><p>Riferimento script</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Gruppi di protezione del ruolo amministrativo</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Amministratori del contenitore di configurazione Servizi chiave pubblica</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
<td style="border:1px solid black;"><p>ca_setup.wsf</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Gruppo autorizzato a pubblicare elenchi CRL e certificati CA nei contenitori della configurazione dell'organizzazione</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Publishers</p></td>
<td style="border:1px solid black;"><p>ca_setup.wsf</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Gruppo amministrativo che configura e aggiorna le CA; controlla inoltre la capacità di assegnare tutti gli altri ruoli della CA e di rinnovare il certificato CA.</p></td>
<td style="border:1px solid black;"><p>CA Admins</p></td>
<td style="border:1px solid black;"><p>ca_setup.wsf</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Gruppo amministrativo che approva le richieste di registrazione e revoca dei certificati. Questo è un ruolo di Responsabile della CA.</p></td>
<td style="border:1px solid black;"><p>Certificate Managers</p></td>
<td style="border:1px solid black;"><p>ca_setup.wsf</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Gruppo amministrativo che gestisce i registri di controllo e protezione della CA</p></td>
<td style="border:1px solid black;"><p>CA Auditors</p></td>
<td style="border:1px solid black;"><p>ca_setup.wsf</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Gruppo amministrativo che gestisce i backup della CA</p></td>
<td style="border:1px solid black;"><p>CA Backup Operators</p></td>
<td style="border:1px solid black;"><p>ca_setup.wsf</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Configurazione IIS</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Il nome della directory virtuale IIS utilizzato per pubblicare il certificato e i CRL della CA</p></td>
<td style="border:1px solid black;"><p>pki</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Percorso fisico nella CA di emissione mappato alla directory virtuale IIS</p></td>
<td style="border:1px solid black;"><p>C:\CAWWWPub</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Parametri comuni della CA</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Unità e percorso di memorizzazione dei file di richiesta di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>C:\CAConfig</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Unità e percorso di memorizzazione dei registri del database di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>%windir%\System32\CertLog</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Configurazione della CA principale</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Lunghezza della chiave della CA principale (vedere la nota che segue questa tabella)</p></td>
<td style="border:1px solid black;"><p>4096</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Periodo di validità del certificato della CA principale</p></td>
<td style="border:1px solid black;"><p>16</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Anni</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Periodo massimo di validità dei certificati rilasciati dalla CA principale</p></td>
<td style="border:1px solid black;"><p>8</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Anni</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Intervallo di pubblicazione dei CRL per la CA principale</p></td>
<td style="border:1px solid black;"><p>6</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Mesi</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Periodo di sovrapposizione dei CRL (tempo che intercorre tra la pubblicazione del nuovo CRL e la scadenza del vecchio CRL)</p></td>
<td style="border:1px solid black;"><p>10</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Giorni</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Periodo di pubblicazione di Delta-CRL per la CA principale-0 = disattivazione dei Delta-CRL</p></td>
<td style="border:1px solid black;"><p>0</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Ore</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Parametri della CA di emissione</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Unità e percorso di memorizzazione del database di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>D:\CertLog</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Lunghezza della chiave della CA di emissione</p></td>
<td style="border:1px solid black;"><p>2048</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Periodo di validità del certificato della CA di emissione</p></td>
<td style="border:1px solid black;"><p>8</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Anni</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Periodo massimo di validità dei certificati rilasciati dalla CA di emissione</p></td>
<td style="border:1px solid black;"><p>4</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Anni</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Intervallo di pubblicazione dei CRL per la CA di emissione</p></td>
<td style="border:1px solid black;"><p>7</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Giorni</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Periodo di sovrapposizione dei CRL (tempo che intercorre tra la pubblicazione del nuovo CRL e la scadenza del vecchio CRL)</p></td>
<td style="border:1px solid black;"><p>4</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Giorni</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Periodo di pubblicazione di Delta-CRL per la CA di emissione-0 = disattivazione dei delta-CRL</p></td>
<td style="border:1px solid black;"><p>1</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Giorni</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Periodo di sovrapposizione dei Delta- CRL (tempo che intercorre tra la pubblicazione del nuovo Delta-CRL e la scadenza del vecchio Delta-CRL)</p></td>
<td style="border:1px solid black;"><p>1</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Unità del valore precedente</p></td>
<td style="border:1px solid black;"><p>Giorni</p></td>
<td style="border:1px solid black;"><p>Pkiparams.vbs</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Varie</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Percorso degli script di installazione</p></td>
<td style="border:1px solid black;"><p>C:\MSSScripts</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
</tbody>
</table>
<p> </p>

**Nota:** l'utilizzo di una chiave della lunghezza di 4.096 bit potrebbe causare problemi di compatibilità, se i certificati devono essere rilasciati a o utilizzati da alcune periferiche, ad esempio, alcuni tipi di router, o versioni precedenti di software di alcuni fornitori, in quanto non sono in grado di elaborare chiavi superiori a dimensioni specifiche. È necessario testare le applicazioni utilizzando certificati con una chiave del certificato della CA principale di queste dimensioni prima dell'implementazione della PKI.

[](#mainsection)[Inizio pagina](#mainsection)

### Creazione dei server

In questa sezione vengono descritte le attività di base per la preparazione dell'hardware del server e l'installazione del sistema operativo. Sono necessari due server: uno per la CA principale e uno per la CA di emissione.

**Importante:** prima di iniziare la creazione delle CA, è necessario leggere la sezione "Gestione della protezione delle CA" nel modulo "[Progettazione di un'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536257)" della *Guida alla pianificazione*.

#### Selezione e configurazione dell'hardware dei server

Nelle sezioni seguenti vengono descritte le specifiche di base dei server per entrambi i ruoli CA. Il modulo "[Progettazione di un'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536257)" della *Guida alla pianificazione* esamina più dettagliatamente alcuni criteri fondamentali per la selezione dell'hardware.

##### Hardware per il server della CA principale

Nella tabella seguente vengono fornite le specifiche hardware consigliate in base alle raccomandazioni di Windows Server 2003. Tuttavia, potrebbe non essere necessario acquistare nuovo hardware se quello esistente è conforme ai criteri indicati nella *Guida alla pianificazione* ma non viene utilizzato per motivi relativi alle prestazioni.

**Tabella 3. Specifiche hardware consigliate per il server CA principale**

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
<td style="border:1px solid black;"><p>Nessuna (o disattivate)</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Archiviazione disco</p></td>
<td style="border:1px solid black;"><p>— Controller RAID (Redundant Array of Independent Disks) IDE (Integrated Device Electronics) o SCSI (Small Computer System Interface)<br />
— 2 x 18 GB (SCSI) o 2 x 20 GB (IDE) configurato come volume RAID 1 (unità C)<br />
— Archiviazione su supporti rimovibili locali (CD-RW o nastro per backup)<br />
— Unità disco da 1,44 MB per il trasferimento dei dati</p></td>
</tr>
</tbody>
</table>
<p> </p>

##### Hardware per il server della CA di emissione

Il livello di prestazioni richiesto per la CA di emissione è relativamente basso, in quanto il carico di lavoro è piuttosto ridotto. Vengono applicati qui gli stessi criteri di selezione dell'hardware validi per la CA principale. Esistono alcune differenze secondarie relative alla connettività di rete e all'archiviazione:

**Tabella 4. Specifiche hardware consigliate per il server CA di emissione**

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
<td style="border:1px solid black;"><p>2 x singola scheda di interfaccia di rete (NIC) accoppiate per garantire il recupero</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Archiviazione disco</p></td>
<td style="border:1px solid black;"><p>— Controller RAID IDE o SCSI<br />
— 2 x 18 GB (SCSI) o 2 x 20-GB (IDE) configurato come volume RAID 1 (unità C e D)<br />
— Archiviazione su supporti rimovibili locali (CD-RW o nastro per backup) se non è presente la funzione di backup di rete<br />
— Unità disco da 1,44 MB per il trasferimento dei dati.</p></td>
</tr>
</tbody>
</table>
<p> </p>

##### Preparazione dell'hardware

Eseguire la configurazione dell'hardware seguendo le istruzioni del fornitore. Può essere necessario applicare gli ultimi aggiornamenti BIOS e firmware indicati dal fornitore.

Utilizzando il software di gestione del controller disco fornito con l'hardware, creare i volumi RAID 1 come illustrato nella tabella precedente (un volume per la CA principale, due per la CA di emissione).

#### Preparazione del server della CA principale

In questa sezione viene descritta l'installazione di Windows Server 2003 nel server che verrà utilizzato per la CA principale.

##### Installazione di Windows Server 2003, Standard Edition

Molte organizzazioni dispongono già del processo di installazione automatico del server. È possibile utilizzarlo per la creazione dei server, purché possano essere inclusi i parametri riportati di seguito.

Tuttavia, se la creazione dipende da una connessione di rete, si consiglia vivamente di eseguire un'installazione manuale, almeno per la CA principale. Gran parte della protezione di una CA non in linea dipende dal fatto che non è e non è mai stata connessa a una rete. Ciò riduce drasticamente le possibilità di attacco esterno, in quanto l'eventuale intruso dovrebbe accedere fisicamente al server.

-   **Per installare Windows Server 2003**

    1.  Avviare il sistema inserendo il CD di Windows Server 2003, Standard Edition nell'unità CD-ROM. Assicurarsi che il CD-ROM sia stato impostato come periferica di avvio nelle impostazioni BIOS del server.

    2.  Creare una partizione sul volume principale, formattarla come NTFS e selezionarla come partizione di installazione di Windows.

    3.  Selezionare le impostazioni internazionali corrette.

    4.  Digitare le informazioni sul nome e l'organizzazione con cui Windows Server 2003 verrà registrato.

    5.  Digitare una password sicura per l'account dell'Amministratore locale (almeno 10 caratteri e una combinazione di lettere maiuscole e minuscole, caratteri numerici e punteggiatura).

    6.  Digitare il nome del computer quando viene richiesto: **HQ-CA-01** (sostituire questo valore con il nome prescelto).

        **Importante:** anche se la CA principale non è in linea, è essenziale che il nome sia univoco nell'organizzazione.

    7.  Quando viene richiesto, aggiungere il computer a un gruppo di lavoro. Digitare il nome del gruppo di lavoro: **WGB-Root** (sostituire questo valore con il nome del gruppo di lavoro prescelto).

    8.  Non installare alcun componente facoltativo quando viene richiesto.
        Al termine del processo di installazione principale il server verrà riavviato. Continuare con i passaggi seguenti:

    9.  Installare i Service Pack di Windows correnti (al momento della stesura di questo documento, Windows Server 2003 era stato appena rilasciato, quindi non era disponibile alcun Service Pack) e tutti gli aggiornamenti rapidi per la protezione consigliati (utilizzare uno strumento quale hfnetchk.exe per individuare l'elenco consigliato). A questo punto, è necessario installare anche gli eventuali aggiornamenti rapidi funzionali, non di protezione, consigliati da Microsoft o che si rivelano necessari in base ai risultati dei test svolti.

    10. Attivare questa copia di Windows. È necessario eseguire questa operazione in modalità non in linea, in modo che il server non debba essere sempre connesso alla rete.

##### Impostazioni di rete

La CA principale non è mai connessa alla rete. È necessario disattivare qualsiasi interfaccia di rete presente nel sistema utilizzando la scheda **Connessioni di rete** del Pannello di controllo. In questo modo si evita che la CA principale diventi accessibile dalla rete, nel caso in cui venga condivisa accidentalmente.

##### Verifica dell'installazione

È necessario verificare che l'installazione del sistema operativo sia stata completata correttamente e che i parametri di configurazione siano conformi a quelli previsti.

-   **Per visualizzare la configurazione del sistema corrente**

    1.  Eseguire il comando:

        **systeminfo**

    2.  Verificare i seguenti elementi dell'output del comando systeminfo; altri dettagli sono stati omessi per brevità e sono indicati da " " (puntini sospensivi):
        ```

    3.  Se queste impostazioni non corrispondono a quelle previste, sarà necessario riconfigurare il server utilizzando il Pannello di controllo oppure rieseguire l'installazione.

#### Preparazione del server della CA di emissione

In questa sezione viene descritta l'installazione di Windows Server 2003 nel server che verrà utilizzato per la CA di emissione.

##### Installazione di Windows Server 2003, Enterprise Edition

Eseguire il processo di creazione del server della CA principale tenendo conto delle eccezioni elencate di seguito.

A differenza della CA principale, è possibile creare il server della CA di emissione utilizzando un metodo di creazione automatico basato sulla rete. Tuttavia, è necessario adottare misure adeguate per garantire che la CA non venga esposta ad alcun rischio di protezione; ad esempio, è necessario installarla in una rete isolata con un percorso non instradabile verso Internet o la rete aziendale principale.

-   **Per installare Windows Server 2003, Enterprise Edition**

    1.  Eseguire i passaggi da 1 a 5 sopra descritti (per il server della CA principale) utilizzando la Enterprise Edition di Windows Server 2003 al posto della Standard Edition.

    2.  Digitare il nome del computer quando viene richiesto: ***HQ-CA-02*** (sostituire questo valore con il nome prescelto).

    3.  Quando viene richiesto, aggiungere il computer a un dominio. Immettere il nome del dominio di Active Directory a cui saranno aggiunti i server: ***WOODGROVEBANK*** (sostituire questo valore con il nome del dominio in cui si sta installando la CA). Quando viene richiesto, immettere le credenziali di un utente autorizzato ad aggiungere computer a questo dominio.

        **Nota:** per i domini con più insiemi di strutture, i server dei certificati vengono installati di solito nel dominio principale della struttura. Ciò non è essenziale, ma è un presupposto di questa soluzione.

    4.  Non installare alcun componente facoltativo.
        Dopo il riavvio al termine del processo di installazione principale:

    5.  Installare i Service Pack correnti e gli aggiornamenti rapidi richiesti, come per la CA principale.

    6.  Creare una partizione sul secondo volume del disco rigido, assegnare alla partizione la lettera di unità D e formattarla con NTFS.

    7.  Creare una cartella sull'unità D denominata ***D:\\CertLog***.

    8.  Attivare questa copia di Windows Server 2003 in modalità non in linea per non esporre il server in alcun modo a Internet.

##### Impostazioni di rete

La CA di emissione dispone di una singola interfaccia di rete, sebbene sia possibile accoppiare due schede di interfaccia di rete fisiche per una maggiore capacità di recupero. L'interfaccia di rete deve essere configurata con un indirizzo IP (Internet Protocol) fisso e altri parametri di configurazione IP (gateway predefinito, impostazioni DNS e così via) appropriati dell'organizzazione.

Per motivi di sicurezza è necessario inoltre bloccare qualsiasi connettività in ingresso o in uscita tra la CA di emissione e Internet. Anche il solo accesso in uscita può consentire ai virus e ad altri software dannosi ("malware") di diventare ancora più pericolosi scaricando ulteriore codice da Internet o, nei casi peggiori, sottraendo e trasferendo la chiave privata della CA al di fuori dell'organizzazione.

##### Verifica dell'installazione

È necessario verificare che l'installazione del sistema operativo sia stata completata correttamente e che i parametri di configurazione siano conformi a quelli previsti.

-   **Per visualizzare la configurazione del sistema corrente**

    1.  Eseguire il comando:

        **systeminfo**

    2.  Verificare i seguenti elementi dell'output del comando systeminfo (altri dettagli sono stati omessi per brevità):
        ```

    3.  Se queste impostazioni non corrispondono a quelle previste, è necessario riconfigurare il server utilizzando il Pannello di controllo o rieseguire l'installazione.

#### Installazione degli script di configurazione nei server

Per semplificare alcuni aspetti della configurazione e del funzionamento di questa soluzione, vengono forniti diversi script di supporto e file di configurazione che dovranno essere installati in ciascun server. Alcuni di questi script sono richiesti dalle operazioni descritte nella *Operations Guide*, quindi, non eliminarli al termine dell'installazione della CA.

-   **Per installare gli script di installazione in ciascun server**

    1.  Creare una cartella denominata **C:\\MSSScripts.**

    2.  Copiare gli script dal supporto di distribuzione nella cartella.

#### Installazione e configurazione di Internet Information Services

In questa sezione viene descritta l'installazione e la configurazione di IIS nella CA di emissione. Si consiglia di non installare IIS nella CA principale.

**Avviso:** per semplificare la soluzione fornita, il server della CA di emissione viene utilizzato per ospitare il server Web, il certificato CA e i punti di download dei CRL. Tuttavia, si consiglia nella pratica l'uso di un server Web distinto per migliorare la protezione delle CA. La procedura descritta è applicabile sia per l'installazione di IIS nella CA di emissione che in un server distinto.

IIS è utilizzato per ospitare le pagine di registrazione del server dei certificati e per fornire il certificato della CA e i punti di download dei CRL per i client non Windows. Per motivi di sicurezza, è consigliabile che i punti di download Web per il certificato CA e i CRL risiedano in un server diverso dalla CA stessa. Potrebbero esserci numerosi utenti dei certificati (interni ed esterni) che hanno bisogno di recuperare i CRL o i certificati CA a catena, ma ai quali non deve essere necessariamente consentito l'accesso alla CA. Se i punti di download risiedono nella CA stessa, tali utenti non potranno eseguire il recupero.

##### Installazione di Internet Information Services nella CA di emissione

IIS viene installato con Gestione componenti facoltativi di Windows (accessibile dal Pannello di controllo, **Installazione componenti di Windows**). La tabella seguente illustra i componenti da installare. I rientri dei paragrafi riflettono la relazione tra i componenti così come sono visualizzati nella Gestione guidata dei componenti facoltativi. (**Enable network COM+ access** è ad esempio un sottocomponente del server delle applicazioni Microsoft.) I componenti che non vengono selezionati non sono inclusi nella tabella.

**Tabella 5. Componenti facoltativi da installare**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Componente</p></th>
<th><p>Stato installazione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Modalità server applicazioni</p></td>
<td style="border:1px solid black;"><p>Selezionato</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Enable network COM+ access</p></td>
<td style="border:1px solid black;"><p>Selezionato</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Internet Information Services</p></td>
<td style="border:1px solid black;"><p>Selezionato</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>File comuni</p></td>
<td style="border:1px solid black;"><p>Selezionato</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Gestione di Internet Information Services</p></td>
<td style="border:1px solid black;"><p>Selezionato</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Servizio Web</p></td>
<td style="border:1px solid black;"><p>Selezionato</p></td>
</tr>
</tbody>
</table>
  
-   **Per installare IIS**
  
    1.  Eseguire il comando seguente
  
        **sysocmgr /i:sysoc.inf /u:C:\\MSSScripts\\OC\_AddIIS.txt**  
        Eseguendo questo comando Gestione dei componenti facoltativi utilizza le configurazioni dei componenti specificate nel file di installazione automatica **C:\\MSSScripts** \\OC\_AddIIS.txt (riportato di seguito):
  
        <codesnippet language displaylanguage containsmarkup="false"> \[Components\] complusnetwork = On iis\_common = On iis\_asp = On iis\_inetmgr = On iis\_www = On   
```
  
        **Nota:** in questa configurazione vengono attivate le pagine ASP (con la riga iis\_asp = on). Ciò è necessario per supportare le pagine di registrazione Web di Servizi certificati ma non per la soluzione principale. Se le pagine di registrazione Web non sono richieste, è necessario disattivare ASP (eliminando la riga iis\_asp = on prima di eseguire sysocmgr.exe). Se necessario, è sempre possibile riattivarle in seguito.
  
    2.  Eseguire nuovamente Gestione componenti facoltativi e verificare che i componenti installati corrispondano a quelli elencati nella tabella precedente. Non sono richiesti altri sottocomponenti del **Server applicazioni**, quindi non è necessario eseguire altre selezioni.
  
        **sysocmgr /i:sysoc.inf**
  
##### Configurazione di IIS per la pubblicazione di AIA (Authority Information Access) e del CDP (CRL Distribution Point) nella CA di emissione
  
È necessario creare una directory virtuale su IIS da utilizzare come percorso del protocollo HTTP (Hypertext Transfer Protocol) per la pubblicazione del certificato della CA (AIA) e dei CRL.
  
-   **Per creare una directory virtuale su IIS**
  
    1.  Accedere al server IIS (CA di emissione) con i privilegi di Amministratore locale.
  
    2.  Creare la cartella **C:\\CAWWWPub** che conterrà i certificati della CA e i CRL.
  
    3.  Impostare la protezione della cartella utilizzando Esplora risorse; di seguito sono elencate le autorizzazioni da applicare. Le primi quattro devono già essere presenti
  
        **Tabella 6. Autorizzazioni directory virtuale**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>Utente/Gruppo</p></th>
        <th><p>Autorizzazione</p></th>
        <th><p>Consenti/Nega</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Administrators</p></td>
        <td style="border:1px solid black;"><p>Controllo completo</p></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>System</p></td>
        <td style="border:1px solid black;"><p>Controllo completo</p></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Creator Owners</p></td>
        <td style="border:1px solid black;"><p>Controllo completo (solo sottocartelle e file)</p></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>Users</p></td>
        <td style="border:1px solid black;"><p>— Lettura<br />
        — Visualizzazione contenuto cartelle</p></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>IIS_WPG</p></td>
        <td style="border:1px solid black;"><p>— Lettura<br />
        — Visualizzazione contenuto cartelle</p></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>Account Internet Guest</p></td>
        <td style="border:1px solid black;"><p>Scrittura</p></td>
        <td style="border:1px solid black;"><p>Nega</p></td>
        </tr>
        </tbody>
        </table>
  
    4.  In Gestione IIS creare una nuova directory virtuale nel sito Web predefinito:
  
        -   Denominare la directory virtuale ***pki***
  
        -   Specificare ***C:\\CAWWWPub*** come percorso.
  
    5.  Eliminare l'opzione **Esecuzione script (ad esempio, ASP)** nelle autorizzazioni di accesso alla directory virtuale.
  
    6.  Assicurarsi che l'autenticazione anonima per la directory virtuale sia attivata.
  
##### Selezione di un alias DNS per il punto di pubblicazione HTTP
  
È necessario creare un alias DNS generico (CNAME) che risolve il nome del server IIS in cui risiedono il CDP e AIA, ad esempio, www.woodgrovebank.com. L'alias DNS deve essere utilizzato quando si configurano i percorsi di CDP e AIA per le CA, come descritto nelle sezioni successive. L'uso dell'alias consente di modificare facilmente il percorso dei certificati CA in futuro senza doverli rilasciare nuovamente.
  
##### Verifica dell'installazione di IIS
  
Prima di procedere, è necessario verificare il funzionamento di base di IIS. Se uno dei test descritti di seguito non viene superato, è necessario tornare indietro e ricontrollare i passaggi dell'installazione e della configurazione di IIS descritti precedentemente in questa sezione.
  
-   **Per verificare il corretto funzionamento della directory virtuale IIS**
  
    1.  Accedere al server IIS (CA di emissione) come membro del gruppo Administrators locale e creare un file utilizzando un editor di testo, ad esempio Notepad. Immettere del testo riconoscibile (non è importante il contenuto e non sono richiesti tag HTML):
  
        <codesnippet language displaylanguage containsmarkup="false">Ciao a tutti  
```
  
    2.  Salvare il file come **test.htm** nella cartella creata per la pubblicazione delle informazioni CDP e AIA utilizzando la procedura sopra descritta—**C:\\CAWWWPub**. Salvare lo stesso file come **Test.asp** nella stessa cartella.
  
    3.  Aprire un browser e digitare l'URL per tentare di recuperare le pagine:  
        **http://*www.woodgrovebank.com*/pki/test.htm**
  
        **Nota:** se non è ancora stato impostato l'alias nel DNS, è possibile immetterlo temporaneamente nel file host locale (%systemroot%\\system32\\drivers\\etc\\hosts) in base all'indirizzo IP del server IIS. In alternativa, è possibile utilizzare il nome host del server IIS al posto dell'alias. Tuttavia, sarà necessario in seguito controllare il corretto funzionamento dell'alias DNS.
  
    4.  Il testo "Ciao a tutti" verrà visualizzato nel browser.
  
<!-- -->
  
-   **Per verificare che le autorizzazioni di esecuzione siano state disattivate**
  
    1.  Aprire un browser e digitare l'URL per tentare di recuperare le pagine:  
        **http://*www.woodgrovebank.com*/pki/test.asp**
  
    2.  Nel browser viene visualizzato il messaggio di errore seguente o simile:  
        **Impossibile visualizzare la pagina**  
        **Tentativo di eseguire un'applicazione CGI, ISAPI o altri programmi eseguibili da una directory che non consente l'esecuzione di programmi.**
  
        insieme al seguente codice di errore:  
        **Errore HTTP 403.1 - Accesso negato: Accesso in esecuzione negato.**  
        **Internet Information Services (IIS)**
  
Microsoft Internet Explorer tenterà automaticamente e in modo invisibile di autenticare un utente per un sito Web, pertanto, è difficile determinare se è stato utilizzato l'accesso anonimo. Un modo per stabilirlo è di modificare le impostazioni di protezione dell'area di Internet Explorer per forzare l'uso dell'accesso anonimo e ripetere i test precedenti. In alternativa alla modifica della configurazione di Internet Explorer, è possibile seguire questa procedura che utilizza telnet.exe per forzare l'accesso non autenticato. Questa procedura presuppone che il test del sito Web venga eseguito dal server IIS stesso. Il test riportato di seguito non funzionerà se si utilizza un server proxy.
  
-   **Per verificare se l'accesso anonimo è stato attivato**
  
    1.  Da un prompt dei comandi, eseguire il comando:  
        **telnet**
  
    2.  Quando viene visualizzato il messaggio telnet, digitare il comando seguente per attivare la visualizzazione locale dei caratteri digitati:  
        **set localecho**
  
    3.  Quindi digitare il comando per connettersi a IIS utilizzando l'alias DNS definito precedentemente:  
        **open** ***www.woodgrovebank.com*** **80**
  
    4.  Digitare il testo seguente esattamente come è riportato, rispettando le minuscole e le maiuscole, per recuperare la pagina test.htm:  
        **GET /pki/test.htm**
  
        **Nota:** il cursore sarà ritornato nella parte superiore dello schermo, ciò significa che il testo che viene digitato sovrascrive il testo esistente dando luogo a una visualizzazione leggermente distorta che può essere ignorata.
  
        In caso di errore durante la digitazione, premere **INVIO** e digitare nuovamente il comando **open** (passaggio 3) per riconnettersi e inviare il comando **GET** una seconda volta.
  
    5.  Viene visualizzato l'output seguente:
  
        <codesnippet language displaylanguage containsmarkup="false">Hello world Connection to host lost. Press any key to continue...  
```
  
    6.  Digitare **quit** per uscire da telnet.
  
    7.  Se tutti e tre i test sono stati superati, eliminare i file test.htm e test.asp dalla cartella del server Web.
  
#### Installazione e configurazione di componenti aggiuntivi del sistema operativo
  
In questa sezione vengono descritte l'installazione e la configurazione di altri componenti richiesti nei server. È necessario seguire questa procedura per i server della CA principale e della CA di emissione.
  
##### Rimozione del servizio Aggiorna certificati di origine
  
È necessario rimuovere il servizio Aggiorna certificati di origine. Questo è un componente facoltativo che viene installato per impostazione predefinita. Non è consigliabile che la trust della directory principale delle CA venga aggiornata automaticamente e, in ogni caso, il servizio non funzionerà se non può accedere a Internet dando luogo alla registrazione di errori nel registro eventi. È chiaro che la CA non in linea non avrà accesso a Internet, ma è necessario bloccare inoltre qualsiasi connessione in ingresso e in uscita tra la CA di emissione e Internet.
  
-   **Per rimuovere il servizio Aggiorna certificati di origine**
  
    -   Eseguire il comando seguente:
  
        **sysocmgr /i:sysoc.inf /u:C:\\MSSScripts\\OC\_RemoveRootUpdate.txt**
  
        Tramite questo comando Gestione componenti facoltativi utilizza le configurazioni dei componenti specificate nel file di installazione automatica **C:\\MSSScript**s**\\OC\_ RemoveRootUpdate.txt** riportato di seguito:
  
        <codesnippet language displaylanguage containsmarkup="false">\[Components\] rootautoupdate = Off   
```
  
#### Controllo dei Service Pack e degli aggiornamenti e delle correzioni di protezione
  
A questo punto è necessario controllare nuovamente i Service Pack e l'elenco degli aggiornamenti rapidi installati, in quanto potrebbero essere stati installati componenti aggiuntivi, quali IIS. Utilizzare uno strumento, ad esempio Hfnetchk, per eseguire il controllo, ottenere tutte le correzioni richieste e installarle nei server dopo un'adeguata procedura di test.
  
Per istruzioni sull'uso di Hfnetchk, vedere il collegamento indicato nella sezione "[Ulteriori informazioni](#xsltsection136121120120)" alla fine di questo modulo.
  
**Nota:** sarà necessario scaricare separatamente l'elenco di aggiornamenti rapidi XML (Extensible Markup Language) corrente in modo da poter eseguire Hfnetchk non in linea.
  
#### Installazione di software aggiuntivo
  
In questa sezione viene descritta l'installazione di applicazioni software aggiuntive, necessarie per le CA.
  
##### CAPICOM
  
CAPICOM 2.0 è richiesto nella CA principale e nella CA di emissione per molti degli script di impostazione e di gestione forniti con questa soluzione. Per informazioni su dove reperire l'ultima versione di CAPICOM, consultare la sezione "[Ulteriori informazioni](#xsltsection136121120120)" alla fine di questo modulo.
  
Per installare e registrare la DLL di CAPICOM, seguire le istruzioni contenute nell'eseguibile autoestraente.
  
##### Strumenti di supporto di Windows Server 2003
  
Sebbene non sia essenziale, è utile installare gli strumenti di supporto di Windows 2000 nel server della CA di emissione. Alcuni di questi strumenti sono utili per determinate operazioni della CA, mentre altri possono agevolare la risoluzione dei problemi. È possibile installare gli strumenti di supporto dal CD di installazione di Windows (Suptools.msi in Support\\Tools).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Preparazione di Active Directory per l'infrastruttura PKI
  
In questa sezione viene descritto come assicurare che Active Directory sia predisposto correttamente per l'installazione di Servizi certificati.
  
#### Preparazione dello schema Active Directory
  
Sono previsti alcuni requisiti minimi nell'infrastruttura del dominio di Active Directory. Tali requisiti variano a seconda se la soluzione viene stata installata in un ambiente Active Directory di Windows 2000 o in un ambiente che sia stato aggiornato a (o installato inizialmente come) Active Directory di Windows Server 2003.
  
##### Requisiti per tutte le versioni di Active Directory
  
La soluzione richiede un livello funzionale dei domini della modalità originale di Windows 2000 o superiore, almeno per il dominio in cui sono installati i server dell'autorità di certificazione. Se il dominio non si trova a questo livello o a un livello superiore, è necessario innalzarlo seguendo le istruzioni riportate nell'articolo di Microsoft TechNet seguente: [Raise the Domain Functional Level to Windows Server 2003](http://technet.microsoft.com/en-us/library/cc775826.aspx)
  
**Nota:** il livello funzionale dei domini predefinito di Active Directory è sempre in modalità mista, anche se è stato installato un dominio di Active Directory di Windows 2003 originale. È necessario aumentare il livello prima di continuare.
  
La soluzione presuppone un insieme di strutture di Active Directory con il livello di funzionalità dell'insieme di strutture predefinito di Windows 2000 (o superiore). Non è necessario modificare tale impostazione. Per ulteriori informazioni su questi concetti, vedere l'articolo di TechNet seguente:[Enabling Windows Server 2003 Active Directory Functional Levels.](http://technet.microsoft.com/en-us/library/cc759280.aspx)
  
##### Installazione in un dominio di Windows 2000
  
Se la soluzione è stata installata in un insieme di strutture Active Directory di Windows 2000, per garantirne il funzionamento è necessario aggiornare lo schema della directory per l'installazione di Servizi certificati di Windows 2003. È necessario inoltre assicurarsi che Service Pack 3 di Windows 2000 sia applicato a tutti i controller di dominio (DC). Il Service Pack 3 è necessario per lo strumento di aggiornamento dello schema e affinché i DC supportino la firma LDAP (Lightweight Directory Access Protocol). La firma LDAP è un'ulteriore perfezionamento della protezione richiesta dalle CA di Windows Server 2003 e dai client del sistema operativo Microsoft Windows XP che utilizzano la registrazione automatica dei certificati.
  
Numerose funzioni di Servizi certificati di Windows 2003 (quali la registrazione automatica dell'utente e i modelli modificabili) richiedono una versione Windows Server 2003 dello schema Active Directory. Ciò non significa che alcuni o tutti i controller di dominio devono eseguire Windows Server 2003, ma che Servizi certificati di Windows Server 2003 richiede estensioni di schema particolari che non sono presenti nello schema Active Directory di Windows 2000. È possibile aggiornare lo schema della directory tramite lo strumento ADPrep.exe (incluso nella cartella i386 del supporto di distribuzione di Windows Server 2003).
  
Per utilizzare Adprep, è necessario applicare il Service Pack 3 (SP3) ai controller di dominio di Windows 2000 (Adprep funzionerà con il Service Pack 1, più alcuni aggiornamenti rapidi, ma poiché il SP3 è richiesto comunque, questa informazione non è rilevante). Non tentare di utilizzare questo strumento senza verificare prima che tutti i controller di dominio si trovino al livello patch corretto.
  
**Avviso:** questa procedura modifica in modo irreversibile lo schema della directory. Sebbene si tratti di una procedura sicura, prima di iniziare è necessario assicurarsi di aver letto attentamente la documentazione correlata.
  
Nel controller di dominio principale dello schema dell'insieme di strutture, è necessario eseguire il comando seguente:  
**ADPrep /ForestPrep**
  
Per eseguire questa operazione è necessario essere un membro del gruppo Schema Admins oppure richiedere di eseguirla a un amministratore in possesso delle autorizzazioni appropriate.
  
Per ulteriori informazioni sullo strumento ADPrep, vedere la sezione "[Ulteriori informazioni](#xsltsection136121120120)" alla fine di questo modulo.
  
##### Verifica della disponibilità di Active Directory
  
È possibile verificare il livello funzionale del dominio e la versione dello schema eseguendo la procedura seguente.
  
-   **Per verificare il livello funzionale del dominio**
  
    1.  Aprire Utenti e computer di Active Directory.
  
    2.  Visualizzare le proprietà dell'oggetto Dominio.
  
    3.  Nella scheda **Generale**, viene visualizzato uno dei **livelli funzionali del dominio** seguenti:
  
        -   Windows 2000 nativo
  
        -   Windows Server 2003
  
<!-- -->
  
-   **Per verificare la versione dello schema corretta**
  
    1.  Da un prompt dei comandi digitare i comandi seguenti (assicurarsi di sostituire il DN del dominio principale dell'insieme di strutture nel comando dsquery.exe):  
        **dsquery \* "cn=schema,cn=configuration,** ***DC=woodgrovebank,DC=com*" -scope base -attr objectversion**
  
        **Note:** questo comando è suddiviso in più righe per la stampa, ma è necessario immetterlo su un'unica riga.  
        Sarà necessario eseguire il comando da un server Windows 2003. Dsquery.exe non è disponibile per impostazione predefinita in Windows XP o Windows 2000.
  
    2.  Viene visualizzata la versione dello schema di 30 (o superiore) come illustrato di seguito:
  
        <codesnippet language displaylanguage containsmarkup="false"> objectversion 30  
```
  
#### Gruppi e utenti di Active Directory
  
In questa sezione viene illustrata la creazione di gruppi di protezione e di account utenti di Active Directory utilizzati dalle CA.
  
##### Creazione dei gruppi di amministrazione dell'infrastruttura PKI e delle CA
  
I ruoli e le funzionalità amministrative vengono definiti tramite account utenti di dominio e gruppi di protezione.
  
**Nota:** in questa soluzione vengono definiti più gruppi di protezione che corrispondono a ruoli amministrativi distinti. Ciò conferisce un ampio controllo sulle modalità di delega delle responsabilità all'Amministrazione delle CA. Tuttavia, *non* è necessario utilizzare tutti o uno qualsiasi di questi ruoli, se non corrispondono al modello di amministrazione desiderato. In casi estremi, se esiste un unico amministratore dell'infrastruttura PKI che si occupa di tutti gli aspetti del servizio, è possibile aggiungere questo account a tutti i gruppi di ruoli della CA. Nella pratica la maggior parte delle organizzazioni adotta di solito una certa separazione dei ruoli, ma solo poche utilizzano tutte le funzionalità di separazione dei ruoli di Servizi certificati di Windows.
  
-   **Per creare gruppi amministrativi della CA nel dominio**
  
    1.  Accedere a un membro del dominio con un account che dispone di autorizzazioni sufficienti per creare oggetti utente e gruppo nel contenitore Utenti.
  
    2.  Per creare i gruppi di gestione CA del dominio, eseguire il comando seguente:  
        **Cscript //job:CertDomainGroups C:\\MSSScripts\\ca\_setup.wsf**
  
Questo script crea i gruppi di protezione elencati nella tabella seguente come gruppi universali. I gruppi vengono creati nel contenitore Utenti e devono essere spostati in un'unità organizzativa (OU, Organizational Unit) più appropriata. (Vedere la sezione successiva per informazioni più dettagliate.)
  
**Tabella 7. Nomi e scopi dei gruppi**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome gruppo</p></th>
<th><p>Scopo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
<td style="border:1px solid black;"><p>Amministratori del contenitore di configurazione Servizi chiave pubblica</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Enterprise PKI Publishers</p></td>
<td style="border:1px solid black;"><p>Autorizzato a pubblicare CRL e certificati CA nei contenitori della configurazione dell'organizzazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>CA Admins</p></td>
<td style="border:1px solid black;"><p>Dispone di privilegi amministrativi completi sulla CA, inclusa la determinazione dell'appartenenza di altri ruoli</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Certificate Managers</p></td>
<td style="border:1px solid black;"><p>Gestisce il rilascio e la revoca dei certificati</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>CA Auditors</p></td>
<td style="border:1px solid black;"><p>Gestisce i dati di controllo per la CA</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>CA Backup Operators</p></td>
<td style="border:1px solid black;"><p>Dispone delle autorizzazioni a eseguire il backup e il ripristino delle chiavi e dei dati della CA</p></td>
</tr>
</tbody>
</table>
  
**Note:** se si richiedono ruoli CA Admins, Certificate Managers, CA Auditors e CA Backup Operators distinti per ciascuna CA dell'organizzazione, è necessario creare gruppi distinti invece di singoli gruppi a livello di dominio, come illustrato di seguito. Denominarli *CA Admin* ***NomeCA*****o in modo simile.
  
Questi gruppi di dominio dispongono di gruppi equivalenti locali creati nelle CA non in linea.
  
Il gruppo Administrators locale della CA ha inoltre un ruolo importante nella gestione di una CA. Questo gruppo esiste nei server Windows per impostazione predefinita, pertanto, questa soluzione non ne prevede la creazione.
  
Per un insieme di strutture multidominio, è necessario creare questi gruppi nello stesso dominio dei server dei certificati. Ciò non è essenziale, ma è un presupposto della parte rimanente di questa guida. Poiché i gruppi vengono creati come universali, è possibile utilizzarli per amministrare le CA installate nel dominio di qualsiasi insieme di strutture.
  
##### Creazione degli utenti test di amministrazione dell'infrastruttura PKI e delle CA
  
A scopo di test e dimostrazione, lo script seguente crea account generici che corrispondono a ciascuno dei ruoli definiti dai gruppi sopra elencati. Tuttavia, se gli account effettivi che verranno utilizzati già esistono in questa fase, oppure si è in grado di crearli, ignorare questo passaggio e utilizzare gli account esistenti.
  
-   **Per creare gli account utenti test di amministrazione della CA**
  
    1.  Accedere a un membro del dominio con un account che dispone di autorizzazioni sufficienti per creare oggetti utente e gruppo nel contenitore Utenti.
  
    2.  Creare account utenti test del dominio per gli individui che amministreranno la CA eseguendo lo script seguente:  
        **Cscript //job:CertDomainTestAccts C:\\MSSScripts\\ca\_setup.wsf**
  
        Lo script imposta password pseudo casuali su tutti gli account invece di lasciarli con password vuote. Prendere nota delle password dall'output dello script o reimpostare le password assegnate automaticamente con quelle desiderate.
  
**Avviso:** l'uso di account generici come questi, con password condivise tra gli amministratori, rende il controllo praticamente impossibile. In ambienti diversi da quello di testing, è necessario utilizzare sempre account individuali.
  
Lo script crea gli account di dominio descritti nella tabella seguente. Lo script crea utenti nel contenitore Utenti che è necessario spostare in una unità organizzativa più appropriata. (Vedere la sezione successiva per informazioni più dettagliate.)
  
**Tabella 8. Nomi e scopi degli account**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Account utente</p></th>
<th><p>Scopo dell'account</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>EntPKIAdmin</p></td>
<td style="border:1px solid black;"><p>Amministratori del contenitore di configurazione Servizi chiave pubblica</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>EntPKIPub</p></td>
<td style="border:1px solid black;"><p>Autorizzato a pubblicare CRL e certificati CA nei contenitori della configurazione dell'organizzazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>CAAdmin</p></td>
<td style="border:1px solid black;"><p>Dispone di privilegi amministrativi completi sulla CA, inclusa la determinazione dell'appartenenza di altri ruoli</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>CertManager</p></td>
<td style="border:1px solid black;"><p>Gestisce il rilascio e la revoca dei certificati</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>CAAuditor</p></td>
<td style="border:1px solid black;"><p>Gestisce i dati di controllo per la CA</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>CABackup</p></td>
<td style="border:1px solid black;"><p>Dispone delle autorizzazioni a eseguire il backup e il ripristino delle chiavi e dei dati della CA</p></td>
</tr>
</tbody>
</table>
  
**Nota:** gli account test rappresentano la configurazione dei ruoli amministrativi più complessa, nella quale ciascun ruolo della CA corrisponde a un singolo utente (account utente). Tuttavia, disporre di account separati per ogni ruolo non è particolarmente vantaggioso, a meno che ciascun ruolo non sia effettivamente svolto da persone diverse. È legittimo disporre di singoli account in più gruppi di ruolo, o anche in tutti i gruppi di ruolo, se ciò riflette in modo più accurato la struttura amministrativa.
  
##### Popolamento dei gruppi di amministrazione della CA
  
È necessario popolare i gruppi di amministrazione della CA con gli account del personale amministrativo appropriato dell'organizzazione. Per una descrizione completa del mapping di questi gruppi ai ruoli amministrativi dell'infrastruttura di Servizi certificati, vedere la sezione "Ruoli di gestione" nel modulo "[Progettazione di un'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536257)" della *Guida alla pianificazione*. Per una descrizione completa dei ruoli amministrativi di Servizi certificati di Windows Server 2003, vedere l'argomento "Amministrazione basata sui ruoli" della guida in linea o l'articolo di TechNet seguente: [Windows Server 2003 PKI and Role-Based Administration](http://technet.microsoft.com/en-us/library/cc739182.aspx) (in inglese).
  
**Nota:** se sono stati creati account di dominio test, è necessario comunque aggiungerli manualmente come membri dei rispettivi gruppi di protezione. Come misura di protezione, questi account non vengono aggiunti per impostazione predefinita.
  
La procedura di installazione descritta nella parte restante di questo documento richiede che alcune delle azioni di impostazione vengano eseguite utilizzando account membri dei gruppi Enterprise PKI Admins, Enterprise PKI Publishers e CA Admins. In questo modo si evita di utilizzare i privilegi dei gruppi Enterprise Admins o Domain Admins se non quando è assolutamente indispensabile.
  
**Nota:** è possibile applicare una separazione rigorosa dei ruoli nei Servizi certificati di Windows Server 2003. Ciò significa che qualsiasi account a cui vengono assegnati più ruoli (direttamente o tramite l'appartenenza a un gruppo) viene escluso da tutti i ruoli amministrativi nella CA. Questa funzione non è attivata per impostazione predefinita o in questa soluzione, pertanto, è accettabile che allo stesso account utente siano assegnati più ruoli amministrativi, se ciò è richiesto dall'organizzazione.
  
##### Creazione di un modello di amministrazione semplificato per le CA dell'organizzazione
  
gli account test e i gruppi amministrativi rappresentano la configurazione dei ruoli amministrativi più complessa, nella quale ciascun ruolo della CA corrisponde a un singolo utente (account utente). Tuttavia, disporre di account separati per ogni ruolo non è particolarmente vantaggioso, a meno che ciascun ruolo non sia effettivamente svolto da persone diverse. È legittimo disporre di singoli account in più gruppi di ruolo, o anche in tutti i gruppi di ruolo, se ciò riflette in modo accurato la struttura amministrativa.
  
Numerose organizzazioni utilizzeranno tre ruoli: CA Administrator, Auditor e Backup Operator. Questa configurazione viene riportata nella tabella seguente utilizzando un sottoinsieme degli account test creati precedentemente a scopo illustrativo.
  
**Tabella 9. Assegnazione dei gruppi del modello amministrativo semplificato**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Ruolo amministrativo semplificato</p></th>
<th><p>Appartenenza al gruppo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>CAAdmin</p></td>
<td style="border:1px solid black;"><p>— Enterprise PKI Admins<br />
— <strong>CA Admins</strong><br />
— <strong>Certificate Managers</strong><br />
— Administrators (amministratori locali della CA)</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>CAAuditor</p></td>
<td style="border:1px solid black;"><p>— <strong>CA Auditors</strong><br />
— Administrators (amministratori locali della CA)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>CABackup</p></td>
<td style="border:1px solid black;"><p>CA Backup Operators</p></td>
</tr>
</tbody>
</table>
  
Utilizzando questa configurazione, l'account CA Admin sarà in grado di eseguire tutte le attività amministrative nelle CA dell'organizzazione (incluse l'approvazione e la revoca dei certificati) e avrà il controllo amministrativo di tutte le informazioni di configurazione dell'infrastruttura PKI dell'organizzazione in Active Directory (l'impostazione delle relative autorizzazioni viene illustrata di seguito in questo documento).
  
##### Struttura di unità organizzative del dominio consigliata per la gestione delle CA e dei modelli di certificato
  
Esistono diversi tipi di gruppi e account utenti associati alla gestione e al funzionamento di un'infrastruttura PKI. Per consentire una più facile gestione dei gruppi e degli utenti, è possibile riunirli in unità organizzative. La tabella seguente illustra la struttura consigliata di un'unità organizzativa e ne descrive lo scopo (le voci con rientro sono le OU figlie delle OU di Servizi certificati).
  
È necessario assegnare le autorizzazioni del gruppo Enterprise PKI Admins per creare ed eliminare gruppi e utenti nell'unità organizzativa di Servizi certificati e in tutti i contenitori figli.
  
**Tabella 10. Struttura di un'unità organizzativa di esempio**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Unità organizzativa</p></th>
<th><p>Scopo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Servizi certificati</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Amministrazione di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Contiene i gruppi amministrativi per la gestione delle CA e la configurazione dell'infrastruttura PKI dell'organizzazione.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Gestione dei modelli di certificato</p></td>
<td style="border:1px solid black;"><p>Contiene i gruppi per la gestione di singoli modelli di certificato</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Registrazione dei modelli di certificato</p></td>
<td style="border:1px solid black;"><p>Contiene gruppi a cui sono state concesse le autorizzazioni di registrazione o registrazione automatica sui modelli dello stesso nome. Il controllo di questi gruppi può essere delegato quindi al personale appropriato per consentire un regime di registrazione flessibile senza modificare i modelli stessi</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Utenti test di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Contiene account test temporanei</p></td>
</tr>
</tbody>
</table>
  
Per ulteriori informazioni sull'uso di queste unità organizzative e dei gruppi contenuti in esse, vedere le sezioni pertinenti di "Managing the Public Key Infrastructure" disponibile in [*Microsoft Solution for Securing Wireless LANS: Operations Guide*](http://www.microsoft.com/downloads/details.aspx?familyid=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en) (in inglese).
  
-   **Per creare la gerarchia amministrativa delle unità organizzative di Servizi certificati**
  
    1.  Accedere come Amministratore con un livello di autorizzazioni adeguato per creare le OU e delegare le autorizzazioni all'interno delle OU. Come creatori di nuove OU, sarà sempre possibile assegnare a se stessi l'autorizzazione a delegare il controllo di tali OU.
  
    2.  Creare la struttura delle unità organizzativa illustrata nella tabella precedente in un percorso appropriato del dominio. (Si presume che si tratti del dominio principale dell'insieme di strutture, ma non è essenziale).
  
    3.  Assegnare le autorizzazioni al gruppo E**nterprise PKI Admin**s per creare ed eliminare gruppi nell'unità organizzativa di Servizi certificati e in tutti i contenitori figli.  
        **Nota:** questa struttura di unità organizzativa viene fornita solo a scopo illustrativo. Non è obbligatorio adottarla.
  
#### Protezione di Servizi chiave pubblica di Active Directory
  
In questa sezione viene descritto come delegare il controllo al contenitore Servizi chiave pubblica per i gruppi di protezione dell'amministrazione della PKI.
  
##### Concessione delle autorizzazioni al contenitore Servizi chiave pubblica
  
Le informazioni relative alla configurazione PKI a livello di insieme di strutture vengono aggiornate nel contenitore Configurazione di Active Directory. Le autorizzazioni di scrittura per questo contenitore, per i relativi sottocontenitori e per gli oggetti sono limitate per impostazione predefinita al gruppo di protezione degli Amministratori dell'organizzazione.
  
Per consentire al gruppo Enterprise PKI Admins di installare le CA e configurare i modelli di certificato e per consentire al gruppo Enterprise PKI Publishers di pubblicare gli elenchi di revoca dei certificati e i certificati CA senza dover essere membri del gruppo di protezione degli Amministratori dell'organizzazione, è necessario modificare la protezione sul contenitore Servizi chiave pubblica.
  
**Nota:** sarà necessario richiedere a un membro del gruppo Enterprise Admins di Active Directory di eseguire la prima procedura, a meno che non l'utente non ne sia membro.
  
-   **Per assegnare le autorizzazioni a Enterprise PKI Admins**
  
    1.  Accedere come membro del gruppo di protezione **Enterprise Admins** .
  
    2.  Nello snap-in MMC di Siti e servizi di Active Directory visualizzare il nodo **Servizi** (dal menu **Visualizza**). Selezionare il sottocontenitore Servizi chiave pubblica e visualizzare le relative proprietà.
  
    3.  Nella scheda **Protezione**, aggiungere il gruppo di protezione **Enterprise PKI Admin**s e concedere al gruppo il **Controllo completo**.
  
    4.  Nella vista **Avanzate** , modificare le autorizzazioni del gruppo per garantire che il **Controllo completo** sia applicato **all'oggetto specificato e tutti gli oggetti figli**.
  
    5.  Selezionare il contenitore **Servizi** e visualizzare le relative proprietà.
  
    6.  Nella scheda **Protezione**, aggiungere il gruppo di protezione **Enterprise PKI Admin**s e concedere al gruppo il **Controllo completo**.
  
    7.  Nella vista **Avanzate** , modificare le autorizzazioni del gruppo per garantire che il **Controllo completo** sia applicato solo a **questo oggetto**.
  
<!-- -->
  
-   **Per assegnare le autorizzazioni a Enterprise PKI Publishers**
  
    1.  Accedere come membro del gruppo di protezione E**nterprise PKI Admin**s (o Enterprise Admins).
  
    2.  Nello snap-in MMC di Siti e servizi di Active Directory visualizzare il nodo **Servizi** e aprire le proprietà del contenitore **Servizi chiave pubblica\\AIA**.
  
    3.  Nella scheda **Protezione**, aggiungere il gruppo di protezione **Enterprise PKI Publishers** e concedere le autorizzazioni seguenti al gruppo:
  
        -   Lettura
  
        -   Scrittura
  
        -   Crea tutti gli oggetti figli
  
        -   Elimina tutti gli oggetti figli
  
    4.  Nella vista **Avanzate**, modificare le autorizzazioni del gruppo per garantire che le autorizzazioni vengano applicate **all'oggetto specificato e tutti gli oggetti figli**.
  
    5.  Ripetere i passaggi da 2 a 4 per i contenitori seguenti:
  
        -   Servizi chiave pubblica\\CDP
  
        -   Servizi chiave pubblica\\Autorità di certificazione
  
        **Nota:** dopo aver concesso le autorizzazioni al gruppo Enterprise PKI Admins, un membro di questo gruppo può concedere le autorizzazioni al gruppo Enterprise PKI Publishers.
  
##### Assegnazione delle autorizzazioni al gruppo Cert Publishers
  
Il gruppo di protezione Cert Publishers contiene gli account di computer di tutte le CA dell'organizzazione nel dominio. Questo gruppo viene utilizzato per concedere autorizzazioni agli oggetti utente e computer e agli oggetti inclusi nel contenitore CDP menzionato nella procedura precedente. Quando viene installata una CA, è necessario aggiungere il relativo account di computer a tale gruppo. Per impostazione predefinita, solo i gruppi Domain Admins, Enterprise Admins o i gruppi Administrators incorporati del dominio sono autorizzati a modificare l'appartenenza al gruppo Cert Publishers. Per consentire ai membri di Enterprise PKI Admins di installare le CA dell'organizzazione, è necessario modificare le autorizzazioni di questo gruppo di protezione
  
-   **Per assegnare l'autorizzazione per modificare l'appartenenza al gruppo Cert Publishers**
  
    1.  Accedere come membro di **Domain Admins** (del dominio in cui viene installata la CA di emissione).
  
    2.  Aprire MMC di **Utenti e computer di Active Directory**.
  
    3.  Dal menu **Visualizza** di MMC, assicurarsi che **Caratteristiche avanzate** sia attivato.
  
    4.  Individuare il gruppo **Cert Publishers** (incluso per impostazione predefinita nel contenitore **Utenti**) e visualizzare le proprietà del gruppo.
  
    5.  Dalla scheda **Protezione**, aggiungere il gruppo **Enterprise PKI Admins** e fare clic sul pulsante **Avanzate**.
  
    6.  Selezionare il gruppo **Enterprise PKI Admins** dall'elenco e fare clic sul pulsante **Modifica**.
  
    7.  Selezionare la scheda **Proprietà** e assicurarsi che sia selezionato **Solo l'oggetto specificato** nella casella **Applica a:**.
  
    8.  Scorrere verso il basso e fare clic sulla casella **Write Members** nella colonna **Consenti**.
  
    9.  Chiudere tutte le finestre di dialogo e salvare le modifiche facendo clic su **OK** in ogni finestra.
  
    10. Sarà necessario riavviare il server della CA di emissione prima di installare il componente Servizi certificati. In questo modo si consentirà al server di rilevare i membri del nuovo gruppo nel proprio token di accesso.
  
##### Assegnazione delle autorizzazioni di ripristino a Enterprise PKI Admins
  
Per installare le CA dell'organizzazione è necessario disporre dei diritti di ripristino di file e directory nel dominio in cui si sta installando la CA. Il processo di installazione di Servizi certificati richiede questo diritto per installare i modelli di certificato nel dominio. Più specificamente, questo diritto è richiesto per consentire l'unione dei descrittori di protezione dei modelli e di altri oggetti della directory e, quindi, di assegnare le autorizzazioni corrette agli oggetti PKI del dominio. I gruppi di dominio incorporati Administrators, Server Operators e Backup Operators dispongono di questo diritto per impostazione predefinita.
  
Poiché si utilizzerà un gruppo delegato per eseguire l'installazione della CA, è necessario assegnare questo diritto al gruppo Enterprise PKI Admins utilizzato per installare la CA.
  
-   **Per assegnare i diritti di ripristino a Enterprise PKI Admins:**
  
    1.  Accedere come membro di **Domain Admins** (del dominio in cui verrà installata la CA di emissione).
  
    2.  Aprire MMC di **Utenti e computer di Active Directory**.
  
    3.  Selezionare la **OU dei controller di dominio**e visualizzare le proprietà della OU.
  
    4.  Nella scheda **Criterio gruppo** selezionare l'oggetto Criteri di gruppo (GPO, Group Policy Object) del **Criterio controller di dominio predefinito**, quindi fare clic su **Modifica**.
  
    5.  Selezionare Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri locali\\Assegnazione diritti utente e fare doppio clic sulla voce **Ripristino di file e directory**.
  
    6.  Aggiungere il gruppo **Enterprise PKI Admins** all'elenco visualizzato.
  
    7.  Chiudere la finestra di dialogo e la console MMC di modifica del GPO.
  
**Importante:** se si dispone di altri GPO che impostano il diritto utente **Ripristino di file e directory** nei controller di dominio, è necessario eseguire la procedura sopra descritta sui GPO utilizzando la massima priorità invece del **Criterio controller di dominio predefinito**. Le impostazioni dei diritti utente non sono cumulative e sarà valido solo l'ultimo GPO per il quale sono stati impostati questi diritti, ovvero quello con la priorità più alta.
  
#### Verifica
  
È possibile verificare la creazione di gruppi, utenti e OU sfogliandoli in Utenti e computer di Active Directory. Gli utenti devono essere membri dei gruppi appropriati (sia gli utenti test che gli utenti effettivi).
  
Per verificare l'applicazione corretta delle autorizzazioni al contenitore Servizi chiave pubblica, eseguire i passaggi seguenti. Una copia di Strumenti di supporto di Windows Server 2003 deve essere installata nel sistema in cui si esegue tale procedura. La procedura non deve essere eseguita in una CA.
  
-   **Per verificare le autorizzazioni di Servizi chiave pubblica**
  
    1.  Accedere a un server membro del dominio (ad esempio, il server della CA di emissione) come membro di Enterprise PKI Admins.
  
    2.  Eseguire mmc.exe e caricare lo snap-in Modifica ADSI.
  
    3.  Fare clic con il pulsante destro del mouse sulla cartella Modifica ADSI, selezionare **Connetti a**, quindi selezionare **Configurazione** dall'elenco a discesa **Select a Well Known Naming Context**.
  
    4.  Passare al contenitore Servizi chiave pubblica e selezionarlo con il pulsante destro del mouse. Selezionare **Nuovo**, quindi scegliere **Oggetto**.
  
    5.  Scegliere **Contenitore** dall'elenco e denominarlo (ad esempio, **Test**).
  
        L'oggetto contenitore deve essere creato correttamente nel contenitore Servizi chiave pubblica.
  
    6.  Eliminare l'oggetto contenitore appena creato.
  
    7.  Non deve essere possibile creare un oggetto contenitore in un punto qualsiasi del contenitore Configurazione diverso dal contenitore Servizi.
  
    8.  Accedere come membro di **Enterprise PKI Publishers**.
  
    9.  Caricare ADSIEdit e connettersi al contenitore della configurazione.
  
    10. Tentare di creare un oggetto contenitore nel contenitore Servizi chiave pubblica; questo tentativo non deve riuscire.
  
    11. Creare un contenitore test in ciascun sottocontenitore AIA, CDP e Autorità di certificazione.
  
    12. Rimuoverli dopo aver verificato che siano stati creati correttamente.
  
**Avviso:** fare attenzione a eliminare solo gli oggetti di testing creati. In particolare, Enterprise PKI Admins dispone di autorizzazioni sufficienti per eliminare l'intero contenitore Servizi chiave pubblica.
  
**Nota:** se si sceglie di non installare gli Strumenti di supporto di Windows Server 2003, ADSIEdit non sarà disponibile. È possibile eseguire questa procedura di verifica dalla riga di comando utilizzando le utilità incorporate dsadd.exe e dsrm.exe. Tuttavia, è indispensabile utilizzare la sintassi e i percorsi dell'oggetto directory corretti con queste utilità. Testare i comandi attentamente in un sistema di testing, prima di utilizzarli nell'ambiente di produzione di Active Directory.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Protezione di Windows Server 2003 per Servizi certificati
  
In questa sezione viene descritto come applicare i criteri di protezione e altre misure di sicurezza a Windows Server 2003 prima di installare Servizi certificati. È necessario inoltre leggere la sezione sulla "Protezione fisica " nel modulo "[Progettazione di un'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536257)" della *Guida alla pianificazione*.
  
#### Implementazione della protezione nel server della CA principale
  
Nelle sezioni seguenti viene descritta la configurazione di gruppi e account utenti locali e l'applicazione dei criteri di protezione al server della CA.
  
##### Creazione degli account utente e dei gruppi di protezione locali nella CA principale
  
Poiché la CA principale non fa parte di un dominio, i ruoli e le funzionalità amministrative vengono definiti utilizzando gli account utente e i gruppi di protezione locali.
  
-   **Per creare gli account utenti e i gruppi locali sul server della CA principale**
  
    1.  Nella CA principale, eseguire lo script seguente per creare gruppi di gestione della CA locale:
  
        **Cscript //job:CertLocalGroups C:\\MSSScripts\\ca\_setup.wsf**
  
        Lo script crea i gruppi locali descritti nella tabella seguente.
  
        **Tabella 11. Nomi e scopi dei gruppi**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>Nome gruppo</p></th>
        <th><p>Scopo</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p>CA Admins</p></td>
        <td style="border:1px solid black;"><p>Dispone di privilegi amministrativi completi sulla CA, inclusa la determinazione dell'appartenenza di altri ruoli</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>Certificate Managers</p></td>
        <td style="border:1px solid black;"><p>Gestisce il rilascio e la revoca dei certificati</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>CA Auditors</p></td>
        <td style="border:1px solid black;"><p>Gestisce i dati di controllo per la CA</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>CA Backup Operators</p></td>
        <td style="border:1px solid black;"><p>Dispone delle autorizzazioni a eseguire il backup e il ripristino delle chiavi e dei dati della CA</p></td>
        </tr>
        </tbody>
        </table>
  
    2.  Creare account utente locali per gli individui che amministreranno la CA. A scopo di test e dimostrazione, gli account locali generici che corrispondono a ciascuno dei ruoli definiti dai gruppi precedenti vengono creati dallo script seguente. Ignorare questo passaggio se si è in grado di creare account effettivi e procedere alla creazione.  
        **Cscript //job:CertLocalTestAccts C:\\MSSScripts\\ca\_setup.wsf**
  
        Lo script utilizza CAPICOM per generare password pseudo casuali su tutti gli account invece di lasciarli con password vuote. Prendere nota delle password dall'output dello script o reimpostare le password con quelle desiderate.
  
        **Nota:** l'uso di account generici con password condivise tra gli Amministratori rende il controllo praticamente impossibile. In ambienti di produzione ad alta protezione, è necessario utilizzare sempre account individuali.
  
        Lo script crea gli account locali descritti nella tabella seguente.
  
        **Tabella 12. Nomi e scopi degli account**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>Nome account</p></th>
        <th><p>Scopo</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p>CAAdmin</p></td>
        <td style="border:1px solid black;"><p>Dispone di privilegi amministrativi completi sulla CA, inclusa la determinazione dell'appartenenza di altri ruoli</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>CertManager</p></td>
        <td style="border:1px solid black;"><p>Gestisce il rilascio e la revoca dei certificati</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>CAAuditor</p></td>
        <td style="border:1px solid black;"><p>Gestisce i dati di controllo per la CA</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>CABackup</p></td>
        <td style="border:1px solid black;"><p>Dispone delle autorizzazioni a eseguire il backup e il ripristino delle chiavi e dei dati della CA</p></td>
        </tr>
        </tbody>
        </table>
  
        **Nota:** gli account test rappresentano la configurazione dei ruoli amministrativi più complessa, nella quale ciascun ruolo della CA corrisponde a un singolo utente (account utente). Tuttavia, disporre di account separati per ogni ruolo non è particolarmente vantaggioso, a meno che ciascun ruolo non sia effettivamente svolto da persone diverse. È legittimo disporre di singoli account in più gruppi di ruolo, o anche in tutti i gruppi di ruolo, se ciò riflette in modo più accurato la struttura amministrativa.
  
    3.  Aggiungere questi account utente ai gruppi nel modo appropriato. Utilizzare la tabella seguente per gli account test oppure utilizzare i propri account in base ai ruoli e ai criteri di protezione IT definiti dall'organizzazione.
  
        **Tabella 13. Nomi account e appartenenze di gruppo**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>Nome account</p></th>
        <th><p>Appartenenza al gruppo</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p>CAAdmin</p></td>
        <td style="border:1px solid black;"><p><strong>CA Admin</strong>s</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>CertManager</p></td>
        <td style="border:1px solid black;"><p><strong>Certificate Manager</strong>s</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>CAAuditor</p></td>
        <td style="border:1px solid black;"><p>— <strong>CA Auditors</strong><br />
        — Administrators</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>CABackup</p></td>
        <td style="border:1px solid black;"><p><strong>CA Backup Operator</strong>s</p></td>
        </tr>
        </tbody>
        </table>
  
**Nota:** i membri del gruppo CA Admins possono essere nominati inoltre membri del gruppo Administrators locale. Esistono determinate attività che richiedono privilegi amministrativi locali e può essere opportuno associarle al ruolo CA Admins. Tuttavia, ciò renderebbe impossibile l'attivazione della separazione dei ruoli, illustrata in seguito, tra i compiti dell'amministrazione server e quelli dell'amministrazione CA.
  
**Creazione di un modello di amministrazione semplificato per la CA principale**
  
La maggior parte delle organizzazioni non richiede una struttura amministrativa complessa come quella illustrata nella procedura precedente e potrebbero non aver bisogno della separazione dei ruoli. Numerose organizzazioni utilizzano tre ruoli: CA Administrator, Auditor e Backup Operator. Questa configurazione viene riportata nella tabella seguente utilizzando un sottoinsieme degli account test creati precedentemente.
  
**Tabella 14. Assegnazione dei gruppi del modello amministrativo semplificato**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Ruolo amministrativo semplificato</p></th>
<th><p>Appartenenza al gruppo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>CAAdmin</p></td>
<td style="border:1px solid black;"><p>— <strong>CA Admins</strong><br />
— <strong>Certificate Managers</strong><br />
— Administrators</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>CA Auditor</p></td>
<td style="border:1px solid black;"><p>— <strong>CA Auditors</strong><br />
— Administrators</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>CABackup</p></td>
<td style="border:1px solid black;"><p>— <strong>CA Backup Operators</strong></p></td>
</tr>
</tbody>
</table>
  
**Verifica dei gruppi e degli account**
  
Verificare la creazione di gruppi, utenti e appartenenze ai gruppi esaminando il nodo Utenti e Gruppi dello snap-in Gestione computer.
  
##### Applicazione delle impostazioni di protezione del sistema al server della CA principale
  
I server dei certificati vengono protetti tramite il ruolo Servizi certificati del client dell'organizzazione definito nella guida *Windows Server 2003 Security Guide*, disponibile all'indirizzo: [http://go.microsoft.com/fwlink/?LinkId=14845](http://go.microsoft.com/fwlink/?linkid=14845).
  
La CA principale non è membro di un dominio, quindi i modelli e le procedure di protezione devono essere applicati manualmente. Ottenere i modelli di protezione seguenti dalla guida *Windows Server 2003 Security Guide* e copiarli nella cartella C:\\MSSScripts del server della CA principale:
  
-   Enterprise Client — Domain.inf
  
-   Enterprise Client — Member Server Baseline.inf
  
-   Enterprise Client — Certificate Services.inf
  
Personalizzare i modelli di protezione e applicarli al server in base alla procedura seguente.
  
-   **Per personalizzare i modelli di protezione**
  
    1.  Accedere come un membro del gruppo Administrators locale e caricare Enterprise Client—Certificate Services.inf in MMC Modelli di protezione.
  
    2.  In Criteri locali\\Opzioni di protezione modificare le voci seguenti in base agli standard di protezione dell'organizzazione:
  
        -   Account: rinomina account amministratore: *NuovoNuoveAmmin*
  
        -   Account: rinomina account guest: *NuovoNomeGuest*
  
        -   Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso: *TestoAvvisoLegale*
  
        -   Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso: *TitoloAvvisoLegale*
  
        **Nota:** il valore di questi elementi dipende dai criteri correnti dell'organizzazione. Non è necessario configurare questi valori, sebbene sia consigliabile.
  
    3.  In Criteri locali\\Assegnazioni diritti utenti, aggiungere il gruppo locale *****CA Auditors*** ai diritti utente **Gestione registri di controllo e protezione**.
  
    4.  In Criteri locali\\Assegnazioni diritti utenti aggiungere il gruppo locale ***CA Backup Operators*** **ai diritti utente:
  
        -   **Backup di file e directory**
  
        -   **Ripristino di file e directory**
  
    5.  In Criteri locali\\Assegnazioni diritti utenti, aggiungere i gruppi locali seguenti ai diritti utente **Consenti accesso locale**:
  
        -   Administrators
  
        -   Backup Operators
  
        -   **CA Admins**
  
        -   **Certificate Managers**
  
        -   **CA Auditors**
  
        -   **CA Backup Operators**
  
    6.  Aprire la pagina delle proprietà dei servizi seguenti nella cartella Servizi di sistema, quindi fare clic su **Definisci questa impostazionee nel modello**. Confermare le autorizzazioni predefinite facendo clic su **OK**. Impostare il valore di **Selezionare la modalità di avvio servizio** su **Automatico**.
  
        -   Archivi rimovibili
  
        -   Copia replicata del volume
  
        -   Provider di copie replicate Microsoft
  
        **Nota:** questi servizi sono disattivati nel modello di protezione di base per i server membri, ma sono richiesti per l'esecuzione di NTBackup.exe.
  
    7.  Con il modello selezionato, salvare le modifiche al modello (facendo clic su **Salva** nel menu **File**), quindi chiudere MMC.
  
    8.  Eseguire i comandi seguenti nell'ordine specificato per applicare i modelli di protezione richiesti. Secedit potrebbe indicare che sono stati generati alcuni messaggi di avviso che possono essere ignorati (tuttavia, è opportuno investigare gli errori):
  
        **secedit /configure /db %temp%\\casec.db /cfg "C:\\MSSScripts\\Enterprise Client - Domain.inf" /overwrite /log "%temp%\\Enterprise Client - Domain.log"**
  
        **secedit /configure /db %temp%\\casec.db /cfg "C:\\MSSScripts\\Enterprise Client - Member Server Baseline.inf" /log "%temp%\\Enterprise Client - Member Server Baseline.log"**
  
        **secedit /configure /db %temp%\\casec.db /cfg "C:\\MSSScripts\\Enterprise Client - Certificate Services.inf" /log "%temp%\\Enterprise Client - Certificate Services.log"**
  
        Questi comandi sono suddivisi su più righe per la stampa. Immetterli come un'unica riga.
  
**Nota:** nella guida *Windows Server 2003 Security Guide* le impostazioni di protezione sono descritte in modo più dettagliato.
  
**Verifica delle impostazioni di protezione**
  
Per verificare l'applicazione corretta delle impostazioni di protezione, eseguire la procedura seguente.
  
-   **Per verificare le impostazioni di protezione della CA principale**
  
    1.  Visualizzare i registri secedit generati nella sezione precedente e verificare che non siano stati registrati errori gravi. È normale che vengano visualizzati diversi messaggi di avviso ed errori minori, ma non tanto gravi da causare un errore di applicazione del modello di protezione.
  
    2.  Riavviare il server e verificare che tutti i servizi previsti siano stati avviati e che non siano stati registrati errori nel registro eventi del sistema.
  
    3.  Tentare di accedere utilizzando uno degli account test creati o un account reale. Dopo la visualizzazione del testo dell'avviso legale, deve essere possibile accedere al sistema.
  
#### Implementazione della protezione nel server della CA di emissione
  
Le sezioni seguenti descrivono l'applicazione dei criteri di protezione nel server della CA.
  
##### Applicazione delle impostazioni di protezione del sistema al server CA di emissione
  
I server dei certificati vengono protetti tramite il ruolo Servizi certificati definito nella guida *Windows Server 2003 Security Guide*. La CA di emissione è un membro di un dominio, pertanto, le impostazioni dei criteri di protezione vengono applicati utilizzando criteri di gruppo basati sul dominio.
  
Sarà necessario creare una struttura di unità organizzative adeguata che possa contenere gli oggetti computer del server CA e una struttura GPO per applicare le impostazioni di protezione. È necessario creare tre oggetti Criteri di gruppo (GPO):
  
-   Client di organizzazione — Criteri di base per i server membri
  
-   Client di organizzazione — Servizi certificati
  
-   Client di organizzazione — Servizi certificati IIS (solo se IIS è installato nel computer CA)
  
**Nota:** la guida *Windows Server 2003 Security Guide* include inoltre le impostazioni consigliate per i criteri del dominio (criteri di blocco account e password). Tali impostazioni vengono ereditate da tutti i computer del dominio. Se non si desidera modificare i criteri al livello di dominio, ma si intende utilizzare le impostazioni consigliate per la CA di emissione, è necessario creare inoltre un quarto GPO collegato all'unità organizzativa CA:
  
Client di organizzazione - Criteri account per Servizi certificati
  
È necessario attenersi la procedura seguente per impostare il modello dei Criteri di dominio nel GPO.
  
La procedura seguente descrive come creare le unità organizzative e i GPO per la propria organizzazione. Le denominazioni dei GPO e delle unità organizzative sono solo a scopo illustrativo ed è necessario adattare la procedura agli standard dei GPO e delle unità organizzative del proprio dominio.
  
-   **Per creare unità organizzative e GPO nel server CA**
  
    1.  Individuare i modelli di protezione seguenti nella guida *Windows Server 2003 Security Guide*:
  
        -   Client di organizzazione — Dominio
  
        -   Client di organizzazione — Criteri di base per i server membri
  
        -   Client di organizzazione — Servizi certificati
  
        -   Client di organizzazione — Server IIS (solo se IIS è installato nel computer CA)
  
    2.  Accedere come membro del gruppo Administrators del dominio o come utente in possesso dei privilegi per la creazione delle unità organizzative descritte di seguito. Sarà necessario inoltre essere un membro del gruppo Creator Owners Criteri di gruppo.
  
    3.  Aprire MMC di Utenti e computer di Active Directory.
  
    4.  Creare la struttura OU seguente:
  
        **woodgrovebank.com (dominio)**
  
        -   **Server membri**
  
            -   **CA**
  
    5.  Aprire le proprietà del contenitore del dominio e, nella scheda **Criterio gruppo**, fare clic su **Nuovo** per creare un nuovo GPO e denominarlo **Criteri dominio**.
  
    6.  Modificare il GPO e passare alla cartella Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione. Fare clic con il pulsante destro del mouse sulla cartella Impostazioni protezione, quindi fare clic su **Importa**. Selezionare Enterprise Client-Domain.inf come modello da importare.
  
    7.  Chiudere il GPO.
  
    8.  Ripetere i tre passaggi precedenti per le combinazioni di unità organizzative, GPO e modelli di protezione elencati nella tabella seguente.
  
        **Tabella 15. Mapping dei GPO ai modelli di protezione e alle unità organizzative**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>OU</p></th>
        <th><p>GPO</p></th>
        <th><p>Modello di protezione</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Server membri</p></td>
        <td style="border:1px solid black;"><p>Client di organizzazione — Criteri di base per i server membri</p></td>
        <td style="border:1px solid black;"><p>Enterprise Client — Member Server Baseline.inf</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>CA</p></td>
        <td style="border:1px solid black;"><p>Client di organizzazione — Servizi certificati</p></td>
        <td style="border:1px solid black;"><p>Enterprise Client — Certificate Services.inf</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>CA</p></td>
        <td style="border:1px solid black;"><p>(Opzionale — vedere nota precedente) Client di organizzazione — Criteri account per Servizi certificati</p></td>
        <td style="border:1px solid black;"><p>Enterprise Client — Domain.inf</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>CA</p></td>
        <td style="border:1px solid black;"><p>(Opzionale — se IIS è installato nel computer CA) Client di organizzazione — Servizi certificati IIS</p></td>
        <td style="border:1px solid black;"><p>Enterprise Client — IIS Server.inf</p></td>
        </tr>
        </tbody>
        </table>
  
**Nota:** se IIS è stato installato nel computer CA di emissione (l'impostazione predefinita per questa soluzione), sarà necessario creare un GPO IIS distinto solo per le CA. Sebbene sia possibile disporre anche di un GPO IIS per i server IIS Intranet, si consiglia vivamente di creare un GPO diverso che venga utilizzato esclusivamente dalle CA. In questo modo, qualsiasi modifica apportata al GPO IIS non comprometterà la sicurezza delle CA.
  
Dopo aver creato i GPO e aver importato i modelli, è necessario personalizzare le impostazioni dei GPO e applicarle ai computer Servizi certificati in base alla procedura seguente.
  
-   **Per personalizzare e applicare il GPO Servizi certificati**
  
    1.  Da Utenti e computer di Active Directory, modificare il GPO Client di organizzazione — Servizi certificati. In Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri locali\\Opzioni di protezione, modificare le voci seguenti in conformità agli standard di protezione dell'organizzazione:
  
        -   Account: rinomina account amministratore: *NuovoNuoveAmmin*
  
        -   Account: rinomina account guest: *NuovoNomeGuest*
  
        -   Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso: *TestoAvvisoLegale*
  
        -   Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso: *TitoloAvvisoLegale*
  
    2.  In Criteri locali\\Assegnazione diritti utente, aggiungere il gruppo dominio *****Controllori CA*** **ai diritti utente **Gestione registri di controllo e protezione**.
  
    3.  In Criteri locali\\Assegnazione diritti utente, aggiungere *****CA Backup Operators*****ai diritti utente:
  
        -   Backup di file e directory
  
        -   Ripristino di file e directory
  
    4.  In Criteri locali\\Assegnazione diritti utente, aggiungere i gruppi locali e di dominio ai diritti utente **Consenti accesso locale**:
  
        -   (locale) **Administrators**
  
        -   (locale) **Backup Operators**
  
        -   (dominio) **Enterprise PKI Admins**
  
        -   (dominio) **Enterprise PKI Publishers**
  
        -   (dominio) **CA Admins**
  
        -   (dominio) **Certificate Managers**
  
        -   (dominio) **CA Auditors**
  
        -   (dominio) **CA Backup Operators**
  
    5.  In **File System**, aggiungere la cartella D:\\CertLog. Assicurarsi che le autorizzazioni corrispondano a quelle riportate nella tabella seguente.
  
        **Tabella 16. Autorizzazioni per le cartelle del database CA**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>Utente/Gruppo</p></th>
        <th><p>Autorizzazione</p></th>
        <th><p>Consenti/Nega</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Administrators</p></td>
        <td style="border:1px solid black;"><ul>
        <li><p>Controllo completo</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>System</p></td>
        <td style="border:1px solid black;"><ul>
        <li><p>Controllo completo</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Backup Operators</p></td>
        <td style="border:1px solid black;"><ul>
        <li><p>Controllo completo</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>CREATOR OWNER</p></td>
        <td style="border:1px solid black;"><ul>
        <li><p>Controllo completo</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        </tbody>
        </table>
  
    6.  Per la stessa cartella, aggiungere le voci di controllo riportate nella tabella seguente per il gruppo Everyone (fare clic sul pulsante **Avanzate** della finestra di dialogo **Protezione**, quindi selezionare la scheda **Controllo**). Digitare **Everyone** quando viene richiesto per il nome di un utente o di un gruppo. Quando si aggiunge il gruppo Everyone, verrà visualizzata la finestra di dialogo con le informazioni dettagliate **Voci di controllo per** D:\\CertLog. Assicurarsi che l'opzione **La cartella selezionata, le sottocartelle e i file** sia selezionata nel campo **Applica a**. Selezionare tutte le voci a cui corrisponde Sì nella tabella.
  
        **Tabella 17. Controllo per le cartelle del database CA**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>Autorizzazione</p></th>
        <th><p>Riuscito</p></th>
        <th><p>Non riuscito</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><ul>
        <li><p>Controllo completo</p></li>
        </ul></td>
        <td style="border:1px solid black;"><br />
        </td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><ul>
        <li><p>Visita cartelle/Esecuzione file</p></li>
        </ul></td>
        <td style="border:1px solid black;"><br />
        </td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><ul>
        <li><p>Visualizza contenuto cartelle/Lettura dati</p></li>
        </ul></td>
        <td style="border:1px solid black;"><br />
        </td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><ul>
        <li><p>Lettura attributi</p></li>
        </ul></td>
        <td style="border:1px solid black;"><br />
        </td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><ul>
        <li><p>Lettura attributi estesi</p></li>
        </ul></td>
        <td style="border:1px solid black;"><br />
        </td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><ul>
        <li><p>Creazione file/Scrittura dati</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><ul>
        <li><p>Creazione cartelle/Aggiunta dati</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><ul>
        <li><p>Scrittura attributi</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><ul>
        <li><p>Scrittura attributi estesi</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><ul>
        <li><p>Eliminazione sottocartelle e file</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><ul>
        <li><p>Eliminazione</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><ul>
        <li><p>Autorizzazioni di lettura</p></li>
        </ul></td>
        <td style="border:1px solid black;"><br />
        </td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><ul>
        <li><p>Cambia autorizzazioni</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><ul>
        <li><p>Diventa proprietario</p></li>
        </ul></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        <td style="border:1px solid black;"><p>Sì</p></td>
        </tr>
        </tbody>
        </table>
  
    7.  Aprire la pagina delle proprietà dei servizi seguenti nella cartella Servizi di sistema, quindi fare clic su **Definisci questa impostazione nel modello**. Confermare le autorizzazioni predefinite facendo clic su **OK**. Impostare il valore di **Selezionare la modalità di avvio servizio** su **Automatico**.
  
        -   Archivi rimovibili
  
        -   Copia replicata del volume
  
        -   Provider di copie replicate Microsoft
  
        -   Utilità di pianificazione
  
            **Nota:** questi servizi sono disattivati nel modello di protezione di base per i server membri, ma i primi due sono necessari per consentire l'esecuzione di NTBackup.exe, mentre l'Utilità di pianificazione è richiesta da alcuni script operativi.
  
    8.  Spostare l'account del computer CA di emissione nell'unità organizzativa Servizi certificati.
  
    9.  Nel computer CA di emissione, eseguire il comando seguente per applicare le impostazioni del GPO al computer:
  
        **gpupdate**
  
**Nota:** nella guida *Windows Server 2003 Security Guide* le impostazioni di protezione sono descritte in modo più dettagliato.
  
**Verifica delle impostazioni di protezione**
  
Per verificare l'applicazione corretta delle impostazioni di protezione, eseguire la procedura seguente.
  
-   **Per verificare le impostazioni di protezione della CA principale**
  
    1.  Verificare la presenza di eventi di origine SceCli nel registro eventi applicazioni. Deve esistere un ID evento 1704 che fa seguito al comando **gpupdate**. Il testo dell'evento deve essere il seguente:
  
        **Applicazione del criterio di protezione agli oggetti del criterio di gruppo riuscita.**
  
    2.  Riavviare il server e verificare che tutti i servizi previsti siano stati avviati e che non siano stati registrati errori nel registro eventi del sistema.
  
    3.  Tentare di accedere utilizzando uno degli account test creati o un account reale. Dopo la visualizzazione del testo dell'avviso legale, deve essere possibile accedere al sistema.
  
##### Configurazione della protezione di Servizi terminal nella CA di emissione
  
È necessario disattivare Servizi Terminal nel computer CA di emissione, in quanto potrebbero essere utilizzati da intrusi per attaccare la CA; inoltre, riducono significativamente l'effetto delle misure di protezione fisica applicate al server. Se non è possibile disattivare Servizi Terminal, in quanto sono richiesti per scopi di amministrazione remota, è necessario configurare le impostazioni come descritto nella tabella seguente.
  
**Nota:** lo stato di Servizi Terminal nella CA principale è in gran parte irrilevante, in quanto non è connessa alla rete.
  
Queste impostazioni devono essere configurate nel GPO di protezione di Servizi certificati o in un altro GPO che si applica alla o alle CA in linea.
  
**Tabella 18. Impostazioni da configurare in Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Servizi terminal**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Percorso</p></th>
<th><p>Criterio</p></th>
<th><p>Impostazione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Nega la connessione di un amministratore connesso alla sessione della console</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Non consentire agli amministratori locali di personalizzare le autorizzazioni</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Imposta regole per il controllo remoto delle sessioni di Servizi Terminal</p></td>
<td style="border:1px solid black;"><p>Nessun controllo remoto consentito</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Reindirizzamento dati client\server</p></td>
<td style="border:1px solid black;"><p>Consenti reindirizzamento fuso orario</p></td>
<td style="border:1px solid black;"><p>Disattivato</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Non consentire il reindirizzamento degli Appunti</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Consenti il reindirizzamento audio</p></td>
<td style="border:1px solid black;"><p>Disattivato</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Non consentire il reindirizzamento della porta COM</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Non consentire il reindirizzamento della stampante client</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Non consentire il reindirizzamento della porta LPT</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Non consentire il reindirizzamento delle unità</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Non impostare stampante predefinita del client come stampante predefinita per una sessione</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Crittografia e protezione</p></td>
<td style="border:1px solid black;"><p>Richiedi sempre password del client alla connessione</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Imposta livello di crittografia connessione client</p></td>
<td style="border:1px solid black;"><p>Alta</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Crittografia e protezione\Protezione RPC</p></td>
<td style="border:1px solid black;"><p>Server protetto (richiede protezione)</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Sessioni</p></td>
<td style="border:1px solid black;"><p>Imposta limite di tempo per le sessioni disconnesse</p></td>
<td style="border:1px solid black;"><p>10 minuti</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Consenti la riconnessione solo dal client originale</p></td>
<td style="border:1px solid black;"><p>Attivo</p></td>
</tr>
</tbody>
</table>
  
Qualsiasi account di dominio o gruppo di protezione che richiede l'accesso di Servizi terminal alla CA deve essere aggiunto al gruppo Utenti desktop remoto (a meno che non sia già un membro del gruppo Administrators locale).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Altre attività di configurazione di Windows
  
Sarà necessario quasi sicuramente eseguire altre attività di configurazione sia nella CA di emissione che nella CA principale, a seconda dell'infrastruttura e degli standard della propria organizzazione. Tali attività possono includere:
  
-   Abilitazione dei backup o installazione degli agenti di backup.
  
-   Configurazione del protocollo SNMP (Simple Network Management Protocol) o delle opzioni di Strumentazione gestione Windows (WMI).
  
-   Installazione degli agenti di gestione, quali i componenti client Microsoft Operations Manager (MOM) o Microsoft Systems Management Server (SMS).
  
-   Installazione di software antivirus.
  
-   Installazione degli agenti di rilevamento delle intrusioni.
  
Verificare queste voci durante l'installazione in base alle istruzioni fornite con il prodotto.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Installazione e configurazione della CA principale
  
In questa sezione viene descritto come installare e configurare Servizi certificati nella CA principale.
  
#### Preparazione del file CApolicy.inf per la CA principale
  
Il file CApolicy.inf deve essere creato prima di impostare un'autorità di certificazione principale in Windows 2003. Tale file specifica le caratteristiche del certificato CA principale autofirmato, ad esempio la lunghezza della chiave, il periodo di validità del certificato, i percorsi di pubblicazione CRL e AIA, i criteri di certificazione e un'istruzione di pratica di certificazione (CPS), se ne è stata creata una.
  
**Nota:** per ulteriori informazioni sulla CPS e sui casi in cui è opportuno crearne una, vedere la sezione "Creazione di un'istruzione di pratica di certificazione" nel modulo "[Progettazione di un'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536257)" della *Guida alla pianificazione*. La CPS è un documento legale e non un elemento tecnico, pertanto, bisogna essere certi che sia realmente necessaria prima di configurarla nella CA.
  
Le informazioni CRL e AIA non sono necessarie per il certificato CA principale in sé, pertanto, i parametri *CRLDistributionPoint* e *AuthorityInformationAccess* sono impostati su **Empty** nel file CApolicy.inf.
  
-   **Per creare il file CAPolicy.inf**
  
    1.  Immettere il testo seguente in un editor di testi, ad esempio Blocco note:
  
        <codesnippet language displaylanguage containsmarkup="false">\[Versione\] Signature= "$Windows NT$" \[Certsrv\_Server\] RenewalKeyLength=4096 RenewalValidityPeriod=Years RenewalValidityPeriodUnits=16 \[CRLDistributionPoint\] Empty=true \[AuthorityInformationAccess\] Empty=true   
```
  
        **Nota:** la configurazione di una chiave della lunghezza di 4.096 bit potrebbe causare problemi di compatibilità se i certificati devono essere rilasciati a o utilizzati da alcune periferiche, ad esempio alcuni tipi di router, o versioni precedenti di software di alcuni fornitori, non in grado di elaborare chiavi di dimensioni superiori a un valore specifico.
  
    2.  Se è stata definita una CPS per la CA, includere quanto segue nel file CApolicy.inf (è necessario sostituire tutte le voci in corsivo con i valori della propria organizzazione):
  
        <codesnippet language displaylanguage containsmarkup="false">\[CAPolicy\] Policies=WoodGrove Bank Root CA CPS \[WoodGrove Bank Root CA CPS\] OID=OID.org. URL = "http://www.woodgrovebank.com/YourCPSPage.htm" URL = "ftp://www.woodgrovebank.com/YourCPSPage.txt" Notice = "Istruzioni di pratica di certificazione CA principale WoodGrove Bank"   
```
  
        **Nota:** il testo dell'avviso può contenere un massimo di 200 caratteri. Utilizzare questo campo solo per una breve descrizione della CPS e non per il testo completo della CPS.
  
    3.  Salvare il file come *windir*\\CApolicy.inf (sostituire *windir* con il percorso assoluto della cartella in cui Windows è installato, ad esempio C:\\Windows). È necessario essere un amministratore locale o disporre delle autorizzazioni di scrittura nella cartella di Windows per completare questo passaggio.
  
#### Installazione dei componenti software di Servizi certificati
  
Installare i componenti software CA utilizzando la procedura Aggiunta guidata componenti di Windows. Per completare l'installazione è necessario disporre del CD o del percorso di rete dell'installazione di Windows Server 2003.
  
-   **Per installare Servizi certificati**
  
    1.  Accedere come membro del gruppo Administrators locale ed eseguire Gestione componenti facoltativi (oppure, selezionare **Installazione applicazioni/Componenti di Windows dal Pannello di controllo)**:
  
        sysocmgr /i:sysoc.inf
  
    2.  Selezionare il componenti Servizi certificati (fare clic su **Sì** per eliminare il messaggio di avviso relativo alla ridenominazione).
  
    3.  Selezionare il tipo di CA come **CA autonoma (standalone) principale**, assicurando di aver selezionato la casella di controllo **Utilizzare impostazione personalizzate**.
  
    4.  Nella finestra di dialogo **Coppia di chiavi pubblica e privata** lasciare le impostazioni predefinite, eccetto la lunghezza della chiave che deve essere impostata su 4096. **Tipo provider** deve essere **Microsoft Strong Cryptographic Provider**.
  
    5.  Immettere le informazioni di identificazione dell'autorità di certificazione nel modo seguente:
  
        -   Nome comune CA — *WoodGrove Bank Root CA*
  
        -   Suffisso del nome distinto — DC=woodgrovebank,DC=com (il nome principale dell'insieme di struttura Active Directory dell'organizzazione)
  
        -   Periodo di validità — **8** ***anni***
  
            **Nota:** se una CA era stata installata precedentemente nel computer, verrà visualizzato un messaggio di avviso in cui si richiede se si desidera sovrascrivere la chiave privata dell'installazione precedente. Verificare se la chiave può essere eliminata prima di procedere. In caso di dubbi, annullare la procedura di installazione ed eseguire il backup delle informazioni sulla chiave esistente tramite un backup di sistema o un backup del certificato CA e della chiave privata esistentivedere le relative procedure nel modulo["Gestione dell'infrastruttura a chiave pubblica"](http://technet.microsoft.com/it-it/library/dd536252.aspx) della Guida alla pianificazione.
  
            Il CSP genera la coppia di chiavi che viene memorizzata nell'archivio delle chiavi del computer locale.
  
    6.  Non modificare i percorsi predefiniti del database dei certificati, dei registri del database e della cartella di configurazione.
  
        **Nota:** la configurazione potrebbe generare un avviso in cui si informa che non è possibile creare una cartella condivisa. Tale avviso è prevedibile, in quanto tutte le interfacce di rete sono state disattivate precedentemente. Ignorare l'avviso e continuare.  
        È necessario posizionare il database dei certificati e il relativo registro nelle unità NTFS locali.
  
        Gestione componenti facoltativi installa quindi i componenti di Servizi certificati. Sarà necessario il supporto di installazione di Windows Server 2003 (CD).
  
    7.  Fare clic su **OK** per eliminare l'avviso relativo a IIS e continuare l'installazione.
  
#### Verifica dell'installazione della CA principale
  
È possibile verificare il completamento dell'installazione di Servizi certificati nel modo seguente:
  
-   **Per verificare la corretta installazione della CA principale**
  
    1.  Aprire la console di gestione dell'autorità di certificazione. Verificare che sia stato avviato Servizi certificati e che sia possibile visualizzare le proprietà della CA.
  
    2.  Nella scheda **Generale**, selezionare **Certificato \#0** nell'elenco Certificati CA, quindi fare clic su **Visualizza certificato**.
  
    3.  Verificare nella scheda **Dettagli** del certificato CA che i valori visualizzati corrispondano a quelli descritti nella tabella seguente.
  
        **Tabella 19. Proprietà ed estensioni del certificato della CA principale**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>Attributo del certificato</p></th>
        <th><p>Impostazione richiesta</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Campi Autorità emittente e Oggetto</p></td>
        <td style="border:1px solid black;"><p>Devono essere identici e includere il nome comune completo della CA più il suffisso del nome distinto specificato durante l'installazione.</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>Non prima - Non dopo</p></td>
        <td style="border:1px solid black;"><p>16 anni</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Lunghezza della chiave pubblica</p></td>
        <td style="border:1px solid black;"><p>RSA (4096 bit)</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>Utilizzo chiave</p></td>
        <td style="border:1px solid black;"><p>Firma digitale, Firma certificato, Firma CRL non in linea, Firma CRL (86)</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Restrizioni di base (critiche)</p></td>
        <td style="border:1px solid black;"><p>Tipo oggetto=CA<br />
        Limite lunghezza percorso=Nessuno</p></td>
        </tr>
        </tbody>
        </table>
<p> </p>

        La presenza del tipo di oggetto Restrizioni di base è molto importante: questo valore distingue un certificato CA da un certificato entità di fine. Inoltre, non deve essere elencata alcuna estensione CDP o AIA.

        Se uno dei valori precedenti non è quello previsto, è consigliabile riavviare l'installazione di Servizi certificati.

        **Nota:** se è necessario eseguire nuovamente l'installazione di Servizi certificati, verrà visualizzato un avviso per indicare che la chiave privata esiste già. Nel caso in cui non sia stato rilasciato alcun certificato utilizzando questa chiave, è possibile ignorare l'avviso e generare una nuova chiave. Se la CA ha già rilasciato i certificati (diversi dai certificati di prova), non reinstallare Servizi certificati senza aver prima eseguito una copia di backup della chiave e del certificato precedente (la relativa procedura è descritta nel modulo["Gestione dell'infrastruttura a chiave pubblica"](http://technet.microsoft.com/it-it/library/dd536252.aspx)della *Guida alla pianificazione.*

    4.  È possibile visualizzare inoltre il registro di installazione di Servizi certificati, **%systemroot%\\certocm.log**, per eseguire ulteriori verifiche o agevolare la risoluzione dei problemi in caso di errori.

#### Configurazione delle proprietà della CA principale

La configurazione della CA applica una serie di parametri specifici dell'ambiente. I valori di tali parametri sono documentati nella sezione precedente "Specifiche di pianificazione di Servizi certificati" del presente modulo. Questa procedura consente di configurare le proprietà della CA descritte nella tabella seguente.

**Tabella 20. Proprietà della CA da configurare**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Proprietà CA</p></th>
<th><p>Descrizione dell'impostazione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>URL dei punti di distribuzione CRL</p></td>
<td style="border:1px solid black;"><p>Specifica i percorsi HTTP, LDAP e FILE dai quali è possibile ottenere un CRL aggiornato.<br />
Il percorso FILE è una cartella locale ed è utilizzato dalla CA solo per memorizzare i CRL che rilascia; nei certificati rilasciati sono inclusi solo i percorsi LDAP e HTTP.<br />
L'URL HTTP è elencato in sequenza prima dell'URL LDAP, in modo che i client che utilizzano i certificati CA principali non siano dipendenti da Active Directory.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>URL AIA</p></td>
<td style="border:1px solid black;"><p>I percorsi dai quali è possibile ottenere i certificati CA. Analogamente ai CDP, il percorso file viene utilizzato solo per la pubblicazione del certificato CA e l'URL HTTP ha la priorità sull'URL LDAP.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Periodo di validità</p></td>
<td style="border:1px solid black;"><p>Il periodo di validità massimo per i certificati rilasciati (differisce dal periodo di validità del certificato CA stesso che è impostato nel file CAPolicy.inf o dalla CA padre).</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Periodo CRL</p></td>
<td style="border:1px solid black;"><p>Frequenza di pubblicazione del CRL.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tempo di sovrapposizione CRL</p></td>
<td style="border:1px solid black;"><p>Il tempo di sovrapposizione tra la pubblicazione di un nuovo CRL e la scadenza del CRL precedente.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Periodo Delta - CRL</p></td>
<td style="border:1px solid black;"><p>Frequenza di pubblicazione del Delta-CRL (nella CA principale i Delta-CRL sono disattivati).</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Controllo CA</p></td>
<td style="border:1px solid black;"><p>Impostazioni di controllo CA—tutte le opzioni di controllo sono attivate per impostazione predefinita.</p></td>
</tr>
</tbody>
</table>
  
-   **Per configurare le proprietà della CA principale**
  
    1.  Accedere al server CA come membro del gruppo Administrators locale.
  
    2.  Personalizzare lo script seguente (C:\\MSSScripts\\pkiparams.vbs) in modo da includere il DN corretto del nome principale dell'insieme di strutture di Active Directory (modificare il valore dell'impostazione **AD\_ROOT\_DN**) e l'URL HTTP (modificare l'impostazione **HTTP\_PKI\_VROOT** in base al percorso HTTP della directory virtuale IIS impostata precedentemente) in modo che faccia riferimento al server Web di pubblicazione CDP e AIA.
  
        **Nota:** qui è riportata solo una parte del file. Non modificare o rimuovere alcun elemento del file, a meno che non si conoscano le conseguenze dell'operazione.
  
        <codesnippet language displaylanguage containsmarkup="false">'\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* ' USER SETTABLE CONSTANTS ' ' These values MUST be set to reflect actual values used ' by the organization. '\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* ' This is the URL where CRL and CA certs are to be published. CONST CA\_HTTP\_PKI\_VROOT = " http://www.woodgrovebank.com/pki" ' This needs to be set only if non-Active directory clients need to query ' the ldap URL for CRLs. Normally they are OK with HTTP. If you do set this ' (to a specific DC FQDN) ALL clients will use this DC to query. Left blank ' AD clients use their default LDAP server (local DC) to query. CONST CA\_LDAP\_SERVER = "" ' This needs to be set to the DN of the Active Directory Forest root domain ' This is used to set the Root CA CDP and AIA paths so that clients can ' obtain CRL and CA Certificate information from the Active Directory CONST AD\_ROOT\_DN = "DC=woodgrovebank,DC=com"   
```
  
    3.  Then run the following script:
  
        **Cscript //job:RootCAConfig C:\\MSSScripts\\ca\_setup.wsf**
  
##### Configurazione dei ruoli amministrativi
  
Per utilizzare i ruoli amministrativi nella CA, ad esempio controllori, gestione certificati e così via, è necessario innanzitutto mappare ad essi i gruppi di protezione creati precedentemente.
  
**Nota:** in questa soluzione vengono utilizzati i gruppi creati precedentemente per definire più ruoli distinti. In questo modo sussiste la massima flessibilità nel delegare le responsabilità di gestione della CA. Tuttavia, se non è richiesto questo livello di delega, prendere in considerazione l'utilizzo del modello di gruppo di amministrazione semplificato, specificato precedentemente in questo modulo. Tale modello consente di utilizzare un numero inferiore di account per eseguire le funzioni amministrative CA.
  
-   **Per configurare i ruoli amministrati nella CA principale**
  
    1.  Dalla console di gestione dell'autorità di certificazione, fare clic su **Proprietà** per modificare le proprietà della CA.
  
    2.  Fare clic sulla scheda **Protezione** e aggiungere i gruppi di protezione locali elencati nella tabella seguente. Per ciascun gruppo aggiungere l'autorizzazione elencata.
  
        **Tabella 21. Autorizzazioni CA da aggiungere**

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
        <th><p>Autorizzazione</p></th>
        <th><p>Consenti/Nega</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>CA Admins</strong></p></td>
        <td style="border:1px solid black;"><p>Gestione CA</p></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Certificate Managers</strong></p></td>
        <td style="border:1px solid black;"><p>Rilascio e gestione certificati</p></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        </tbody>
        </table>
  
        **Nota**: se si desidera una separazione netta dei ruoli, è necessario rimuovere le autorizzazioni di Gestione CA dal gruppo Administrators locale.
  
    3.  Altri ruoli di protezione per questa CA sono stati già definiti tramite i criteri di protezione applicati precedentemente al server:
  
        -   Ai controllori CA sono stati assegnati i diritti utente Gestione protezione e Registri di controllo.
  
        -   Gli utenti del gruppo Backup Operators dispongono dei diritti necessari di backup e di ripristino della CA.
  
#### Trasferimento del certificato della CA principale e del CRL sul disco floppy
  
È necessario copiare il certificato della CA principale e il CRL dalla CA in modo che possano essere pubblicati in Active Directory e nel server di pubblicazione dei certificati IIS e CRL.
  
-   **Per copiare il certificato della CA principale e il CRL sul disco floppy**
  
    1.  Accedere alla CA principale come membro del gruppo CA Admins locale, quindi inserire un disco floppy da utilizzare per il trasferimento nell'unità.
  
    2.  Eseguire lo script seguente per copiare il certificato CA sul disco floppy:  
        **Cscript //job:GetCACerts C:\\MSSScripts\\CA\_Operations.wsf**
  
    3.  Eseguire lo script seguente per copiare i CRL CA sul disco floppy:  
        **Cscript //job:GetCRLs C:\\MSSScripts\\CA\_Operations.wsf**
  
    4.  Etichettare il disco floppy ***Transfer-\[HQ-CA-01\]***, datarlo e conservarlo per le fasi successive della procedura.
  
**Nota:** il disco floppy non contiene informazioni di protezione riservate, ad esempio la chiave privata CA, pertanto non è necessario adottare precauzioni speciali per la custodia.
  
#### Pubblicazione del certificato della CA principale
  
Prima di installare la CA di emissione, è necessario pubblicare il certificato della CA principale nell'archivio principale attendibile di Active Directory e il CRL della CA principale nel contenitore CDP di Active Directory. In questo modo tutti i membri del dominio, inclusa la CA di emissione, importeranno il certificato della CA principale nei propri archivi principali e li attiveranno per verificare lo stato di revoca di eventuali certificati rilasciati dalla CA principale (in questo caso, la CA di emissione dovrà verificare lo stato di revoca del proprio certificato, prima di avviare Servizi certificati).
  
**Nota:** è possibile eseguire la procedura seguente da qualsiasi membro del dominio, sebbene sia necessaria l'installazione di Certutil.exe e delle librerie di supporto certadm.dll e certcli.dll nel sistema; certutil.exe (più le DLL richieste) viene installato insieme a Windows Server 2003. A questo scopo, è possibile utilizzare ad esempio il server CA di emissione non configurato.
  
-   **Per pubblicare il certificato CA principale e il CRL in Active Directory**
  
    1.  Accedere a un computer membro del dominio come membro del gruppo ***Enterprise PKI Admin****s* e inserire il disco floppy utilizzato precedentemente per salvare il certificato CA principale e il CRL (etichettato **Transfer-\[HQ-CA-01\]**).
  
    2.  Eseguire lo script seguente per pubblicare il certificato CA in Active Directory:  
        **Cscript //job:PublishCertstoAD C:\\MSSScripts\\CA\_Operations.wsf**
  
    3.  Eseguire lo script seguente per pubblicare il o i CRL CA in Active Directory:  
        **Cscript //job:PublishCRLstoAD C:\\MSSScripts\\CA\_Operations.wsf**
  
##### Pubblicazione del certificato della CA principale e del CRL nel server Web
  
Questo passaggio è necessario, in quanto le versioni HTTP degli URL CDP e AIA sono state specificate nelle estensioni dei certificati CA. Se sono presenti tali estensioni, è necessario tenerne conto pubblicando i CRL e i certificati nei percorsi indicati.
  
**Nota:** questa procedura è identica, a prescindere se il server Web di pubblicazione CDP e AIA si trovi nella CA di emissione o in un altro server. Si presume che la directory virtuale corrisponda a quella impostata nella procedura di configurazione IIS descritta precedentemente: C:\\CAWWWPub. Se il percorso è diverso, sarà necessario aggiornare il valore WWW\_LOCAL\_PUB\_PATH nel file C:\\MSSScripts\\PKIParams.vbs.
  
-   **Per pubblicare il certificato della CA principale e il CRL in un URL Web**
  
    1.  Accedere al server Web come amministratore locale o con un account con autorizzazioni di scrittura nella cartella C:\\CAWWWPub.
  
    2.  Assicurarsi che il disco floppy (etichettato **Transfer-\[HQ-CA-01\]**) contenente i certificati CA e i CRL sia inserito nell'unità.
  
    3.  Eseguire lo script seguente per pubblicare il certificato CA nella cartella server Web:  
        **Cscript //job:PublishRootCertstoIIS**  
        **C:\\MSSScripts\\CA\_Operations.wsf**
  
        (il comando è visualizzato su due righe per la stampa; immetterlo su un'unica riga).
  
    4.  Eseguire lo script seguente per pubblicare il o i CRL CA nella cartella server Web:  
        **Cscript //job:PublishRootCRLstoIIS**  
        **C:\\MSSScripts\\CA\_Operations.wsf**
  
        (il comando è visualizzato su due righe per la stampa; immetterlo su un'unica riga).
  
##### Verifica della pubblicazione del certificato della CA principale
  
È necessario verificare che la pubblicazione del certificato della CA principale sia avvenuta correttamente. Per eseguire tale procedura è necessario accedere a un computer membro del dominio connesso alla rete utilizzando un account di dominio valido.
  
**Nota:** può essere necessario attendere la replica di Active Directory e utilizzare il comando GPUPDATE per forzare il download del certificato CA principale, prima di verificarne la pubblicazione.
  
-   **Per verificare la pubblicazione del certificato della CA principale**
  
    1.  Per verificare la pubblicazione del certificato della CA nell'archivio principale attendibile, eseguire il comando seguente:  
        **certutil -viewstore -enterprise Root**
  
    2.  Il certificato deve essere visualizzato. Verificare che i valori **Issuer** e **Subject** corrispondano a quelli configurati per il nome della CA principale e che la data **Valido dal** sia quella odierna.
  
    3.  Per verificare la pubblicazione del CRL della CA principale nella directory, eseguire il comando seguente, sostituendo le voci in corsivo con i valori utilizzati per l'installazione (nome comune CA, nome host breve CA e DN del dominio principale dell'insieme di strutture Active Directory):  
        **certutil -store -enterprise "ldap:///cn=WoodGrove Bank Root CA,cn=HQ-CA-01,cn=CDP,CN=Public Key Services,CN=Services,CN=Configuration,DC=woodgrovebank,DC=com?certificateRevocationList?base?objectClass=crlDistributionPoint"**
  
    4.  Il risultato deve essere simile al seguente. Verificare che il valore **Issuer** corrisponda al nome configurato per il certificato della CA principale:
  
        <codesnippet language displaylanguage containsmarkup="false"> ================ CRL 0 ================ Issuer: CN=WoodGrove Bank Root CA,DC=woodgrovebank,DC=com CA Version: V1.0 CRL Number: CRL Number=1 CRL Hash(sha1): 73 03 a1 c7 5f a3 c3 f9 8a 09 d0 3c b5 09 00 9c b5 a3 de fe CertUtil: -store command completed successfully.   
```
  
    5.  Per verificare la pubblicazione del certificato CA nel server Web, immettere l'URL seguente in un browser, sostituendo le voci in corsivo con i valori utilizzati nella propria organizzazione:  
        **http://*www.woodgrovebank.com*/pki/*HQ-CA-01\_WoodGrove Bank Root CA*.crt**
  
        **Nota:** può essere necessario utilizzare il nome DNS completo del server CA nel nome file del certificato.
  
    6.  Verrà richiesto di aprire o salvare il file. Aprirlo e verificare che venga visualizzato il CRL della CA principale.
  
    7.  Per verificare la pubblicazione del CRL della CA principale nel server Web, immettere l'URL seguente in un browser, sostituendo le voci in corsivo con i valori utilizzati nella propria organizzazione:  
        **http://*www.woodgrovebank.com*/pki/*WoodGrove Bank Root CA*.crl**
  
    8.  Verrà richiesto di aprire o salvare il file. Aprirlo e verificare che venga visualizzato il CRL della CA principale.
  
**Nota:** se il certificato CA è stato rinnovato o sono stati rilasciati più CRL, è possibile che vengano visualizzati diversi numeri di versione nell'output di questi comandi.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Installazione e configurazione della CA di emissione
  
In questa sezione viene descritto come installare e configurare Servizi certificati nel server CA di emissione. Durante l'installazione questa CA, la CA principale, Active Directory e il server Web interagiscono in modo complesso. Tali interazioni sono illustrate nel diagramma di flusso seguente a cui può essere utile fare riferimento durante l'analisi della sezione.
  
![](images/Dd536249.SGFG16102(it-it,TechNet.10).jpg)
  
*Figura 2*  
*Interazione tra CA, Active Directory e server Web durante l'installazione della CA di emissione*
  
Le interazioni principali tra i diversi sistemi durante l'installazione della CA di emissione sono illustrate nel diagramma di flusso e sono:
  
1.  Pubbicazione del certificato della CA principale e del CRL in Active Directory.
  
2.  Pubblicazione del certificato della CA principale e del CRL nel server Web.
  
3.  Installazione del software Servizi certificati che genera una richiesta di certificato da inoltrare alla CA principale sul disco. Il certificato viene rilasciato dalla CA principale.
  
4.  Installazione del certificato della CA di emissione.
  
5.  Pubblicazione del certificato della CA di emissione e del CRL nel server Web.
  
**Nota:** i passaggi 1 e 2 sono stati descritti nella sezione precedente, "Pubblicazione del certificato della CA principale". Il passaggio contrassegnato da una X nel diagramma si verifica automaticamente nell'ambito della procedura di configurazione dei valori CRL e AIA nella CA durante la fase di configurazione delle proprietà della CA di emissione. Gli altri passaggi vengono descritti in questa sezione.
  
#### Preparazione del file CApolicy.inf per la CA di emissione
  
Il file CAPolicy.inf non è indispensabile per la CA di emissione, tuttavia, ne sarà necessario uno se si desidera modificare le dimensioni della chiave utilizzata dalla CA. È necessario creare il file CApolicy.inf prima di impostare la CA di emissione, sebbene sia possibile aggiungerne uno in seguito e rinnovare il certificato CA. Questo file specifica le caratteristiche del certificato CA, ad esempio la lunghezza della chiave e la CPS (se ne è stata creata una).
  
-   **Per creare il file CAPolicy.inf**
  
    1.  Immettere il testo seguente in un editor di testi, ad esempio Blocco note.
  
        <codesnippet language displaylanguage containsmarkup="false"> \[Versione\] Signature= "$Windows NT$" \[Certsrv\_Server\] RenewalKeyLength=2048   
```
  
    2.  Se è stata definita una CPS per la CA, includere quanto segue nel file CApolicy.inf  
        (è necessario sostituire tutte le voci in corsivo con i valori della propria organizzazione):
  
        <codesnippet language displaylanguage containsmarkup="false">\[CAPolicy\] Policies=WoodGrove Bank Issuing CA 1 CPS \[WoodGrove Bank Issuing CA 1 CPS\] OID=OID.org. URL = "http://www.woodgrovebank.com/YourCPSPage.htm" URL = "ftp://www.woodgrovebank.com/YourCPSPage.txt" Notice = "Istruzioni di pratica di certificazione CA di emissione 1 WoodGrove Bank"   
```
  
        **Note:**
  
        Il testo dell'avviso può contenere un massimo di 200 caratteri. Utilizzare questo campo solo per una breve descrizione della CPS e non per il testo completo della CPS.
  
        Per ulteriori informazioni sulla CPS e sui casi in cui è opportuno crearne una, vedere la sezione "Creazione di un'istruzione di pratica di certificazione" nel modulo "[Progettazione di un'infrastruttura a chiave pubblica](http://www.microsoft.com/downloads/details.aspx?familyid=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en)" della *Guida alla pianificazione*. La CPS è un documento legale e non un elemento tecnico, pertanto, bisogna essere certi che sia realmente necessaria prima di configurarla nella CA.
  
    3.  Salvare il file come %*windir%*\\CApolicy.inf (o sostituire %*windir%* con il percorso assoluto della cartella in cui Windows è installato, ad esempio C:\\Windows). È necessario essere un amministratore locale o disporre delle autorizzazioni di scrittura nella cartella di Windows per completare questo passaggio.
  
#### Installazione dei componenti software di Servizi certificati
  
Installare i componenti software CA utilizzando la procedura Aggiunta guidata componenti di Windows. Per completare l'installazione è necessario disporre del supporto di installazione (CD) di Windows Server 2003.
  
-   **Per installare Servizi certificati**
  
    1.  Accedere al server come membro del gruppo Enterprise Admins del dominio ed eseguire Gestione componenti facoltativi (oppure, selezionare **Installazione applicazioni**/**Componenti di Windows** dal Pannello di controllo):
  
        sysocmgr /i:sysoc.inf
  
        **Nota:** in alternativa all'account Enterprise Admins, è possibile utilizzare un account membro sia del gruppo Enterprise PKI Admins che Domain Admins del dominio a cui la CA appartiene.
  
    2.  Selezionare il componente Servizi certificati (fare clic su **OK** per eliminare il messaggio di avviso relativo alla ridenominazione).
  
    3.  Selezionare il tipo di CA come **CA globale (enterprise) subordinata**, assicurando di aver selezionato la casella di controllo **Utilizzare impostazioni personalizzate**.
  
    4.  Nella finestra di dialogo **Coppia di chiavi pubblica e privata** lasciare le impostazioni predefinite, eccetto la lunghezza della chiave che deve essere impostata su 2*048*. Il tipo provider deve essere **Microsoft Strong Cryptographic Provider**.
  
    5.  Immettere le informazioni di identificazione dell'autorità di certificazione nel modo seguente:
  
        -   Nome comune CA - *WoodGrove Bank Issuing CA 1*
  
        -   Suffisso del nome distinto - *DC=woodgrovebank,DC=com*  
            (il nome principale dell'insieme di strutture Active Directory dell'organizzazione)
  
        -   Periodo di validità — Determinato dalla CA padre
  
        **Nota:** se una CA era stata installata precedentemente nel computer, verrà visualizzato un messaggio di avviso in cui si richiede se si desidera sovrascrivere la chiave privata dell'installazione precedente. Verificare se la chiave può essere eliminata prima di procedere. In caso di dubbi, annullare la procedura di installazione ed eseguire il backup delle informazioni sulla chiave esistente tramite un backup di sistema o un backup del certificato CA e della chiave privata esistenti; vedere le relative procedure nel modulo["Gestione dell'infrastruttura a chiave pubblica"](http://technet.microsoft.com/it-it/library/dd536252.aspx)della *Guida alla pianificazione.*
  
    6.  Il CSP genera la coppia di chiavi che viene memorizzata nell'archivio delle chiavi del computer locale.
  
    7.  Immettere i percorsi del database dei certificati, dei registri del database e della cartella di configurazione nel modo seguente.
  
        -   Database dei certificati—D**:\\CertLo**g
  
        -   Registro database dei certificati— %**windir%\\System32\\CertLo**g
  
        -   Cartella condivisa— **Disattivata**
  
        Per garantire prestazioni e capacità di recupero, memorizzare sempre il database CA e i registri su volumi fisicamente separati (se il database si danneggia per qualche motivo, è possibile utilizzare l'ultima copia di backup insieme ai registri per ripristinare la CA al momento in cui si è verificato l'errore). È necessario posizionare il database dei certificati e i relativi registri nelle unità NTFS locali.
  
    8.  Copiare il file di richiesta del certificato sul disco. La richiesta di certificato viene generata e memorizzata nel percorso della cartella condivisa. Copiare il file *HQ-CA-02.woodgrovebank.com*\_*WoodGrove Bank Issuing CA 1.req* sul disco floppy ed etichettarlo **Transfer-\[HQ-CA-02\]**.
  
    9.  Fare clic su **OK** per eliminare l'avviso relativo a IIS e continuare l'installazione. La procedura di installazione guidata visualizzerà un avviso in cui si informa l'utente che deve ottenere il certificato dalla CA padre per continuare.
  
**Note:**
  
Verrà visualizzato un avviso durante le ultime fasi dell'installazione in cui si informa che la CA non può essere aggiunta al **gruppo Accesso compatibile precedente a Windows 2000**. Tenerne conto solo se è necessario utilizzare la funzione di restrizione di gestione certificati di Servizi certificati, altrimenti, richiedere all'amministratore del dominio di aggiungere l'account del computer della CA al gruppo.
  
Servizi certificati non verrà avviato fino a quando la richiesta di certificato non viene elaborato dalla CA principale e il certificato non viene rilasciato e installato nella CA.
  
#### Invio della richiesta di certificato alla CA principale
  
È necessario inviare in seguito la richiesta di certificato della CA di emissione alla CA principale in modo che possa essere firmata e il certificato possa essere rilasciato alla CA di emissione.
  
-   **Per inviare la richiesta di certificato alla CA principale**
  
    1.  Accedere alla CA principale come membro del gruppo Certificate Managers locale.
  
    2.  Dalla console di gestione dell'autorità di certificazione, nel menu **Attività**, selezionare **Invia nuova richiesta**, quindi inviare la richiesta trasferita dalla CA di emissione (sul disco etichettato **Transfer-\[HQ-CA-02\]**).
  
        **Nota:** se l'installazione di una CA precedente non è riuscita e viene ripetuta, non riutilizzare mai il file di richiesta, in quanto è associato alla chiave precedente e non alla CA corrente che si sta installando.
  
    3.  La CA principale richiede che tutte le richieste vengano approvate manualmente. Individuare la richiesta nel contenitore Richieste in sospeso, verificare che il campo **Nome comune** contenga il nome della CA di emissione, quindi approvare la richiesta facendo clic con il pulsante destro del mouse sulla richiesta e selezionando **Emetti**.
  
    4.  Individuare il certificato appena rilasciato nel contenitore Certificati emessi e aprirlo.
  
    5.  Verificare che i dettagli del certificato siano corretti, esportare quindi il certificato in un file facendo clic su **Copia su file** e salvarlo con il nome PKCS\#7 (selezionare l'opzione che consente di includere tutti i certificati possibili nella catena) sul disco floppy etichettato **Transfer-\[HQ-CA-02\]** (per il rinvio alla CA di emissione).
  
#### Installazione del certificato della CA di emissione
  
Questa sezione illustra come scaricare il certificato CA principale pubblicato precedentemente in Active Directory nella CA di emissione e quindi installarlo nella CA.
  
##### Aggiornamento del certificato nella CA di emissione
  
Il certificato CA principale è stato pubblicato precedentemente nell'archivio principale attendibile di Active Directory. È necessario ora assicurare che la CA di emissione abbia scaricato le informazioni e abbia inserito il certificato nel proprio archivio principale.
  
-   **Per aggiornare le informazioni sulla relazione di trust del certificato nella CA di emissione**
  
    1.  Accedere alla CA di emissione come amministratore locale.
  
    2.  Eseguire il comando seguente:
  
        **certutil -pulse**
  
Questo comando forzerà il download delle informazioni sul nuovo certificato principale attendibile dalla directory e inserirà il certificato nell'archivio principale attendibile locale.
  
**Nota:** questa procedura non è indispensabile, in quanto l'ultima fase di installazione del certificato nella CA inserisce automaticamente il certificato della CA principale nell'archivio principale attendibile locale. Tuttavia, questo passaggio consente di verificare che la procedura di pubblicazioni in Active Directory sia stata eseguita correttamente. La riuscita della procedura è importante perché è in questo modo che tutti i client del dominio ricevono le informazioni sulla relazione di trust relativa alle CA principale ed emittente.
  
-   **Per verificare che il download delle informazioni sulla relazione di trust della CA principale da Active Directory è riuscito**
  
    1.  Eseguire mmc.exe e aggiungere lo snap-in **Certificati**.
  
    2.  Selezionare **Account del computer** come archivio certificati da gestire.
  
    3.  Verificare che il certificato CA principale si trovi nella cartella Autorità di certificazione dell'origine attendibile (i certificati sono elencati in base al nome breve dell'oggetto CA, l'elemento CN).
  
##### Installazione del certificato
  
La risposta con la firma inviata dalla CA principale può essere ora installata nella CA di emissione. Per pubblicare il certificato CA nell'archivio NTAuth di Active Directory (che identifica la CA come CA dell'organizzazione), è necessario installare il certificato CA utilizzando un account che sia membro *sia* del gruppo Enterprise PKI Admins, sia del gruppo Administrators locale. Il primo gruppo dispone dei diritti di pubblicare il certificato nella directory, mentre il secondo dispone dei diritti di installare il certificato nella CA. Se si sta utilizzando il modello di amministrazione semplice suggerito in precedenza, il ruolo CAAdmin è un membro di questi gruppi.
  
-   **Per installare il certificato della CA di emissione**
  
    1.  Accedere alla CA di emissione utilizzando un account membro sia del gruppo Enterprise PKI Admins, sia del gruppo Administrators locale.
  
    2.  Inserire il disco (**Transfer-\[HQ-CA-02\]**) con il certificato salvato rilasciato dalla CA principale.
  
    3.  Dalla console di gestione Autorità di certificazione, nel menu CA **Tasks**, selezionare **Installa certificato**, quindi installare il certificato della CA di emissione dal disco floppy.
  
La CA deve ora avviarsi.
  
#### Verifica dell'installazione del certificato della CA di emissione
  
È possibile verificare il completamento dell'installazione di Servizi certificati nel modo seguente:
  
-   **Per verificare l'installazione del certificato della CA di emissione**
  
    1.  Aprire la console di gestione dell'autorità di certificazione. Verificare che sia stato avviato Servizi certificati e che sia possibile visualizzare le proprietà della CA.
  
    2.  Nella scheda **Generale**, selezionare **Certificato \#0** nell'elenco Certificati CA, quindi fare clic su **Visualizza certificato**.
  
    3.  Verificare nella scheda **Dettagli** del certificato CA che i valori visualizzati corrispondano a quelli descritti nella tabella seguente.
  
        **Tabella 22. Proprietà ed estensioni del certificato della CA di emissione**

<p> </p>
        <table style="border:1px solid black;">
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th><p>Attributo del certificato</p></th>
        <th><p>Impostazione richiesta</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Autorità emittente</p></td>
        <td style="border:1px solid black;"><p>Nome comune CA principale (più suffisso DN)</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>Oggetto</p></td>
        <td style="border:1px solid black;"><p>Nome comune CA di emissione (più suffisso DN)</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Non prima - Non dopo</p></td>
        <td style="border:1px solid black;"><p>8 anni</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>Lunghezza della chiave pubblica</p></td>
        <td style="border:1px solid black;"><p>2048 bit</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Utilizzo chiave</p></td>
        <td style="border:1px solid black;"><p>Firma digitale, Firma certificato, Firma CRL non in linea, Firma CRL (86)</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>Restrizioni di base (critiche)</p></td>
        <td style="border:1px solid black;"><p>Tipo oggetto=CAPath<br />
        Limite lunghezza percorso=Nessuno</p></td>
        </tr>
        <tr class="odd">
        <td style="border:1px solid black;"><p>Punti di distribuzione CRL</p></td>
        <td style="border:1px solid black;"><p>2 voci - URL HTTP ed LDAP</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p>Accesso alle informazioni dell'autorità</p></td>
        <td style="border:1px solid black;"><p>2 voci - URL HTTP ed LDAP</p></td>
        </tr>
        </tbody>
        </table>
  
        La presenza del tipo di oggetto Restrizioni di base è molto importante: questo valore distingue un certificato CA da un certificato entità di fine. Inoltre, verrà elencata un'altra estensione, **Identificativo chiave dell'autorità**, che non era inclusa nel certificato della CA principale. Questo valore deve corrispondere a **Identificatore della chiave dell'oggetto** del certificato della CA principale.
  
        Se uno dei valori precedenti non è quello previsto, è consigliabile riavviare l'installazione di Servizi certificati.
  
        **Nota:** se è necessario eseguire nuovamente l'installazione di Servizi certificati, verrà visualizzato un avviso per indicare che la chiave privata esiste già. Nel caso in cui non sia stato rilasciato alcun certificato utilizzando questa chiave, è possibile ignorare l'avviso e generare una nuova chiave. Se la CA ha già rilasciato i certificati (diversi dai certificati di prova), non reinstallare Servizi certificati senza aver prima eseguito una copia di backup della chiave e del certificato precedente (la relativa procedura è descritta in "Gestione dell'infrastruttura a chiave pubblica", disponibile nella [Microsoft Solution for Securing Wireless LANS: Operations Guide](http://www.microsoft.com/downloads/details.aspx?familyid=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en).
  
    4.  Verificare nella scheda **Percorso certificazione** se il certificato della CA di emissione è collegato correttamente alla CA principale.
  
    5.  È possibile visualizzare inoltre il registro di installazione di Servizi certificati, **%systemroot%\\certocm.log**, per eseguire ulteriori verifiche o agevolare la risoluzione dei problemi in caso di errori di installazione.
  
#### Configurazione delle proprietà della CA di emissione
  
La configurazione della CA applica una serie di parametri specifici dell'ambiente. I valori di tali parametri sono documentati nella sezione precedente "Specifiche di pianificazione di Servizi certificati" del presente modulo. Questa procedura consente di configurare le proprietà della CA descritte nella tabella seguente.
  
**Tabella 23. Proprietà della CA da configurare**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Proprietà CA</p></th>
<th><p>Descrizione dell'impostazione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>URL dei punti di distribuzione CRL</p></td>
<td style="border:1px solid black;"><p>Specifica i percorsi HTTP, LDAP e FILE dai quali è possibile ottenere un CRL aggiornato. Il percorso FILE è una cartella locale ed è utilizzato dalla CA solo per memorizzare i CRL che rilascia; nei certificati rilasciati sono inclusi solo i percorsi LDAP e HTTP. L'URL LDAP è elencato in sequenza prima dell'URL HTTP, in modo che i controller di dominio locali siano la destinazione preferita del download dei CRL nella maggioranza dei client.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>URL AIA</p></td>
<td style="border:1px solid black;"><p>I percorsi dai quali è possibile ottenere i certificati CA. Analogamente ai CDP, il percorso file viene utilizzato solo per la pubblicazione del certificato CA e l'URL LDAP ha la priorità sull'URL HTTP.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Periodo di validità</p></td>
<td style="border:1px solid black;"><p>Il periodo di validità massimo per i certificati rilasciati (differisce dal periodo di validità del certificato CA stesso che è impostato nel file CAPolicy.inf o dalla CA padre).</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Periodo CRL</p></td>
<td style="border:1px solid black;"><p>Frequenza di pubblicazione del CRL.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tempo di sovrapposizione CRL</p></td>
<td style="border:1px solid black;"><p>Il tempo di sovrapposizione tra la pubblicazione di un nuovo CRL e la scadenza del CRL precedente.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Periodo Delta - CRL</p></td>
<td style="border:1px solid black;"><p>Frequenza di pubblicazione Delta-CRL.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Sovapposizione Delta - CRL</p></td>
<td style="border:1px solid black;"><p>Il tempo di sovrapposizione tra la pubblicazione di un nuovo CRL e la scadenza del CRL precedente.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Controllo CA</p></td>
<td style="border:1px solid black;"><p>Impostazioni di controllo CA—tutte le opzioni di controllo sono attivate per impostazione predefinita.</p></td>
</tr>
</tbody>
</table>
  
-   **Per configurare le proprietà della CA di emissione**
  
    1.  Accedere al server CA come membro del gruppo Administrators locale.
  
    2.  È necessario personalizzare lo script **C:\\MSSScripts**\\pkiparams.vbs con le impostazioni specifiche dell'organizzazione quando si imposta la CA principale. Replicare inoltre le modifiche apportate nella copia di C**:\\MSSScript**s\\pkiparams.vbs installata nella CA di emissione.
  
    3.  Eseguire quindi lo script seguente:
  
        **Cscript //job:IssCAConfig C:\\MSSScripts\\ca\_setup.wsf**
  
##### Configurazione dei ruoli amministrativi
  
Per utilizzare i ruoli amministrativi nella CA, ad esempio controllori, gestione certificati e così via, è necessario innanzitutto mappare ad essi i gruppi di protezione creati precedentemente.
  
**Nota:** in questa soluzione vengono utilizzati i gruppi creati precedentemente per definire più ruoli distinti. In questo modo sussiste la massima flessibilità nel delegare le responsabilità di gestione della CA. Tuttavia, se non è richiesto questo livello di delega, prendere in considerazione l'utilizzo del modello di gruppo di amministrazione semplificato, descritto precedentemente in questo modulo. Tale modello consente di utilizzare un numero inferiore di account per eseguire le funzioni amministrative CA.
  
-   **Per configurare i ruoli amministrati nella CA di emissione**
  
    1.  Dalla console di gestione dell'autorità di certificazione, fare clic su **Proprietà** per modificare le proprietà della CA.
  
    2.  Fare clic sulla scheda **Protezione** e aggiungere i gruppi di protezione del dominio elencati nella tabella seguente. Per ciascun gruppo aggiungere l'autorizzazione elencata.
  
        **Tabella 24. Autorizzazioni CA da aggiungere**

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
        <th><p>Autorizzazione</p></th>
        <th><p>Consenti/Nega</p></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td style="border:1px solid black;"><p><strong>CA Admins</strong></p></td>
        <td style="border:1px solid black;"><p>Gestione CA</p></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        <tr class="even">
        <td style="border:1px solid black;"><p><strong>Certificate Managers</strong></p></td>
        <td style="border:1px solid black;"><p>Rilascio e gestione certificati</p></td>
        <td style="border:1px solid black;"><p>Consenti</p></td>
        </tr>
        </tbody>
        </table>
  
        **Nota:** se si desidera una separazione netta dei ruoli, è necessario rimuovere le autorizzazioni di Gestione CA dal gruppo Administrators locale.
  
    3.  Altri ruoli di protezione CA richiedono un'ulteriore configurazione, sebbene siano stati già definiti parzialmente tramite i criteri di protezione applicati precedentemente al server:
  
        -   Ai controllori CA sono stati assegnati i diritti utente Gestione protezione e Registri di controllo. Aggiungere questo gruppo al gruppo Administrators locale.
  
        -   Ai CA Backup Operators sono stati assegnati i diritti di backup e ripristino nella CA. Non sono necessarie altre configurazioni per questo gruppo.
  
#### Pubblicazione del certificato CA di emissione
  
I certificati e i CRL vengono pubblicati automaticamente dalla CA di emissione in Active Directory. La pubblicazione del certificato CA e dei CRL nei percorsi HTTP CDP e AIA, tuttavia, non è automatica; è necessario impostare un processo pianificato per garantirne l'esecuzione.
  
##### Pubblicazione del certificato della CA di emissione e dei CRL nel server Web
  
I certificati e i CRL della CA di emissione devono essere pubblicati rispettivamente nei percorsi HTTP AIA e CDP. È tecnicamente possibile configurare la CA per pubblicare direttamente i certificati e gli elenchi nella cartella server Web; inoltre, se il server Web risiede nella CA di emissione questo processo è molto semplice, tuttavia, non è sempre possibile per motivi di sicurezza e di connettività di rete. Il metodo illustrato qui utilizza una tecnica semplice di copia del file che può essere esteso a diverse configurazioni.
  
**Nota:** questo metodo non è adatto per la pubblicazione diretta in server Web connessi a Internet, in quanto si basa sull'utilizzo della condivisione file SMB (Server Message Block). Per pubblicare in un server Internet, utilizzare un percorso di pubblicazione intermedio, quindi utilizzare il metodo standard di pubblicazione protetta del contenuto nel server Web. È necessario tenere conto dell'effetto che la latenza aggiuntiva, dovuta all'introduzione di questo passaggio, può avere sull'aggiornamento dei CRL.
  
Il certificato CA viene aggiornato molto raramente, pertanto, è possibile pubblicarlo manualmente nel percorso AIA ogni volta che viene rinnovato.
  
-   **Per pubblicare il certificato della CA di emissione**
  
    1.  Accedere alla CA di emissione utilizzando un account in possesso delle autorizzazioni di scrittura nella cartella server Web pubblicata.
  
    2.  Se il server Web si trova in un server remoto, assicurarsi che la relativa cartella sia condivisa. Registrare il percorso UNC (Universal Naming Convention) nella cartella condivisa.
  
    3.  Se il server Web si trova nello stesso server della CA, registrare il percorso locale nella cartella.
  
    4.  Aggiornare il parametro WWW\_REMOTE\_PUB\_PATH in C:\\MSSScripts\\PKIParams.vbs in modo che corrisponda al percorso di destinazione della cartella server Web (il valore predefinito è il percorso locale C:\\CAWWWPub).
  
    5.  Eseguire il comando seguente per pubblicare il certificato CA nel server Web:
  
        **Cscript //job:PublishIssCertsToIISC:\\MSSScripts\\CA\_Operations.wsf**
  
        (il comando è visualizzato su due righe per la stampa; immetterlo su un'unica riga).
  
I CRL vengono rilasciati dalla CA di emissione a intervalli più regolari, ogni giorno oppure ogni ora nel caso dei Delta-CRL, pertanto, è necessario un metodo automatico di replica nel server Web.
  
-   **Per rendere automatica la pubblicazione dei CRL**
  
    1.  Accedere alla CA di emissione con un account membro del gruppo Administrators locale.
  
    2.  Assicurarsi che la cartella server Web sia accessibile (come condivisione remota o percorso locale) da questo server.
  
    3.  Se il server Web è in una condivisione remota, assegnare alla CA di emissione l'accesso in scrittura nella cartella del file system (facendo clic su **Modify access**) e nella condivisione (facendo clic su **Change access**). Se il server Web è membro di un insieme di strutture, è possibile utilizzare il gruppo Cert Publishers per assegnare l'accesso; in questo modo si garantisce che qualsiasi CA dell'organizzazione disponga delle autorizzazioni necessarie per pubblicare i certificati e i CRL in questa cartella. Non è necessario modificare le autorizzazioni nel server Web (vedere la sezione precedente relativa alla configurazione di IIS per la pubblicazione AIA e CDP).
  
    4.  Creare un processo pianificato per copiare i CRL eseguendo il comando seguente:
  
        **schtasks /create /tn "Publish CRLs" /tr "cscript.exe**
  
        **//job:PublishIssCRLsToIIS C:\\MSSScripts\\CA\_Operations.wsf"**
  
        **/sc Hourly /ru "System"**
  
        (Il comando è visualizzato su tre righe per la stampa; immetterlo su un'unica riga.)
  
**Nota:** il comando crea un processo pianificato di pubblicazione dei CRL dalla CA al server che viene eseguito ogni ora. Questo programma è sufficiente per una pianificazione di pubblicazione di Delta-CRL giornaliero o semi-giornaliero. Se la pianificazione di pubblicazione CRL è più frequente, è necessario eseguire il processo pianificato a intervalli più brevi. Il linea generale, è consigliabile una pianificazione del processo pari al circa 5 — 10% della pianificazione di Delta-CRL.
  
##### Verifica della pubblicazione del certificato della CA di emissione
  
È necessario verificare che la pubblicazione del certificato della CA di emissione sia avvenuta correttamente. Per eseguire tale procedura è necessario accedere a un computer membro del dominio connesso alla rete utilizzando un account di dominio valido.
  
-   **Per verificare la pubblicazione del certificato della CA di emissione**
  
    1.  Per verificare la pubblicazione del certificato CA nell'archivio della CA intermedia, eseguire il comando seguente:  
        **certutil -viewstore -enterprise CA**
  
    2.  Vengono visualizzati due certificati: uno per la CA principale e l'altro per la CA di emissione. Fare doppio clic sul certificato della CA di emissione e verificare che il nome **Oggetto** corrisponda a quello configurato per la CA di emissione e che la data **Valido dal** sia quella odierna.
  
    3.  Per verificare la pubblicazione del certificato CA nell'archivio CA NTAuth (tutte le CA dell'organizzazione sono pubblicate qui), eseguire il comando seguente:  
        **certutil -viewstore -enterprise NTAuth**
  
        Viene visualizzato lo stesso certificato per la CA di emissione.
  
    4.  Per verificare la pubblicazione del CRL della CA di emissione nella directory, eseguire il comando seguente, sostituendo le voci in corsivo con i valori utilizzati per l'installazione (nome comune CA, nome host CA breve e DN del dominio principale dell'insieme di strutture Active Directory):
  
        **certutil -store -enterprise "ldap:///cn=WoodGrove Bank Issuing CA 1,"**
  
        **cn=HQ-CA-02,cn=CDP,CN=Servizi chiave pubblica,**
  
        **CN=Servizi,CN=Configurazione,DC=woodgrovebank,DC=com?**
  
        **certificateRevocationList?base?objectClass= cRlDistributionPoint**
  
        (il comando è visualizzato su più righe per la stampa; immetterlo su un'unica riga).
  
    5.  Il risultato deve essere simile al seguente. Verificare che il valore **Issuer** corrisponda al nome configurato per il certificato della CA di emissione:
  
        **================ CRL 0 ================**
  
        **Issuer: CN= WoodGrove Bank Issuing CA,DC=woodgrovebank,DC=com**
  
        **CA Version: V1.0**
  
        **CRL Number: CRL Number=1**
  
        **CRL Hash(sha1): 73 03 a1 c7 5f a3 c3 f9 8a 09 d0 3c b5 09 00 9c b5 a3 de fe**
  
        **CertUtil: -store command completed successfully.**
  
    6.  Per verificare la pubblicazione del certificato CA nel server Web, immettere l'URL seguente in un browser, sostituendo le voci in corsivo con i valori utilizzati nella propria organizzazione:  
        **http://*www.woodgrovebank.com*/pki/*HQ-CA-02\_WoodGrove Bank Issuing CA 1*.crt**
  
    7.  Verrà richiesto di aprire o salvare il file. Aprirlo e verificare che venga visualizzato il certificato CA della CA di emissione.
  
    8.  Per verificare la pubblicazione del CRL della CA di emissione nel server Web, immettere l'URL seguente in un browser, sostituendo le voci in corsivo con i valori utilizzati nella propria organizzazione:  
        **http://*www.woodgrovebank.com*/pki/*WoodGrove Bank Issuing CA 1*.crl**
  
    9.  Verrà richiesto di aprire o salvare il file. Aprirlo e verificare che venga visualizzato il CRL della CA principale.
  
**Nota:** se il certificato CA è stato rinnovato o sono stati rilasciati più CRL, è possibile che vengano visualizzati diversi numeri di versione nell'output di questi comandi.
  
#### Verifica della registrazione dei certificati
  
È necessario verificare se è possibile registrare i certificati della CA di emissione.
  
-   **Per verificare la registrazione dei certificati**
  
    1.  Accedere a un computer membro dello stesso dominio della CA di emissione. Utilizzare un account di dominio.
  
    2.  Aprire la console MMC Certificati per l'utente corrente (sarà necessario aggiungerla a una console MMC vuota utilizzando **Aggiungi/Rimuovi snap-in**).
  
    3.  Fare clic con il pulsante destro del mouse sulla cartella personale e selezionare **Richiedi nuovo certificato** dal sottomenu **Tutte le attività**.
  
    4.  Verrà richiesto di scegliere da un elenco il tipo di certificato: scegliere il tipo **Utente**. Non selezionare la casella di controllo **Opzioni avanzate**.
  
    5.  Assegnare al certificato un nome breve, riconoscibile, ad esempio **Verifica CA di emissione**.
  
    6.  Fare clic su **Fine** per registrare il certificato.
  
    7.  Passare alla sottocartella Certificati della cartella personale. In questa cartella deve comparire **Verifica CA di emissione** (può essere necessario aggiornare prima l'archivio: fare clic con il pulsante destro del mouse sull'oggetto principale **Certificati — Utente corrente** nel riquadro destro della console MMC, quindi scegliere **Aggiorna**).
  
Se il certificato non viene visualizzato, riesaminare la procedura descritta in questo modulo e correggere gli eventuali problemi identificati. Se il problema non viene risolto, consultare la sezione relativa alla risoluzione dei problemi nel modulo["Gestione dell'infrastruttura a chiave pubblica"](http://technet.microsoft.com/it-it/library/dd536252.aspx)della *Guida alla pianificazione.*
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione post-creazione
  
Dopo aver creato la CA principale ed emittente per la propria organizzazione, è necessario completare ancora alcune attività di configurazione illustrate in questa sezione.
  
#### Configurazione dei modelli di certificato
  
La maggior parte di tali attività consiste nella configurazione dei tipi di certificato che le CA possono rilasciare, delle modalità di controllo del rilascio e dei destinatari dei certificati rilasciati.
  
##### Rimozione dei modelli indesiderati dalla CA di emissione
  
Se non sono richiesti, è consigliabile rimuovere tipi specifici di certificati dalla configurazione CA, in modo che non vengano rilasciati accidentalmente. I modelli potranno sempre essere aggiunti in seguito, se necessario.
  
-   **Per rimuovere i modelli indesiderati dalla CA di emissione**
  
    1.  Accedere come membro del gruppo CA Admins del dominio.
  
    2.  Dalla console di gestione dell'autorità di certificazione, selezionare il contenitore Modelli di certificato.
  
    3.  Rimuovere i tipi di modello seguenti:
  
        -   Agente recupero dati EFS
  
        -   EFS di base
  
        -   Server Web
  
        -   Computer
  
        -   Utente
  
        -   Autorità di certificazione subordinata
  
        -   Amministratore
  
        **Nota:** con questa procedura si rimuovono tutti i modelli dalla CA di emissione, eccetto Controller di dominio, Autenticazione controller di dominio e Replica directory via posta elettronica. I certificati Controller di dominio vengono utilizzati dai controller di dominio (DC) di Windows 2000, mentre i certificati Autenticazione controller di dominio e Replica directory via posta elettronica vengono utilizzati sia dai DC di Windows Server 2003 che di Windows 2000. Entrambi sono necessari per supportare l'accesso con smart card. Solo il secondo tipo è necessario per supportare la firma LDAP protetta. Il certificato Replica directory via posta elettronica viene utilizzato per la replica SMTP (Simple Mail Transfer Protocol) di Active Directory.
  
        Tutti i modelli rimossi possono essere aggiunti nuovamente in seguito, se necessario. Nel frattempo, è consigliabile consentire il rilascio solo dei tipi di certificato selezionati.
  
##### Creazione e gestione dei modelli di certificato
  
Oltre ai gruppi di gestione CA e PKI dell'organizzazione, è possibile gestire e utilizzare i modelli di certificato dell'organizzazione in modo più efficace creando gruppi che controllino quali utenti possono modificare le proprietà di ciascun modello e quali utenti possono registrare i certificati di quel tipo.
  
**Nota:** i gruppi Template Admin sono utili se esiste la possibilità di delegare a diversi amministratori il controllo sui modelli. Se la propria organizzazione IT è di piccole o medie dimensioni, questa funzione potrebbe non essere necessaria. In questo caso, solo i membri del gruppo incorporato Enterprise Admins e del gruppo Enterprise PKI Admins (creato dalla presente soluzione) saranno in grado di gestire i modelli di certificato.
  
Per istruzioni sulla creazione e la gestione dei gruppi di amministrazione dei modelli di certificato, vedere le procedure operative nel modulo["Gestione dell'infrastruttura a chiave pubblica"](http://technet.microsoft.com/it-it/library/dd536252.aspx) della *Guida alla pianificazione.*
  
Per istruzioni su come creare modelli di certificato specifici per questa soluzione, vedere la sezione "Configurazione e distribuzione di certificati di autenticazione WLAN" del modulo "Implementazione della protezione di reti LAN senza fili mediante lo standard 802.1X" della presente guida.
  
Per istruzioni generali su come creare e modificare i modelli di certificato, vedere la sezione della documentazione del prodotto relativa alla gestione dei modelli di certificato all'indirizzo: [Certificate Templates How To…](http://technet.microsoft.com/en-us/library/cc786998.aspx) (in inglese).
  
##### Gestione della registrazione dei certificati
  
I gruppi di registrazione del modello semplificano la gestione degli utenti o dei computer che possono registrare un tipo specifico di certificato o sono registrati automaticamente aggiungendoli a un gruppo di protezione o rimuovendoli. Il controllo dell'appartenenza a un gruppo può essere assegnato inoltre al personale amministrativo senza consentirgli di modificare direttamente le proprietà dei modelli di certificato.
  
Per istruzioni sulla creazione e la gestione dei gruppi di registrazione dei modelli di certificato, vedere il modulo ["Gestione dell'infrastruttura a chiave pubblica"](http://technet.microsoft.com/it-it/library/dd536252.aspx) della *Guida alla pianificazione.*
  
#### Impostazione delle autorizzazioni per l'implementazione multidominio
  
Se si sta implementando questa soluzione in un insieme di strutture multidominio e si stanno rilasciando certificati per utenti e computer in domini diversi dalla CA, sarà necessario modificare le autorizzazioni predefinite in modo da consentire alle CA di pubblicare i certificati correttamente in Active Directory.
  
Quando si impostano le autorizzazioni di registrazione per gli utenti sulle CA e i modelli di certificato, è necessario includere espressamente gli utenti e i computer di tutti i domini in cui si desidera consentire di registrare i certificati.
  
-   **Per consentire la pubblicazione di certificati a utenti e computer di altri domini**
  
    1.  Accedere a un controller di dominio del dominio in cui si desidera consentire la pubblicazione dei certificati. È necessario essere un membro degli amministratori del dominio o di un gruppo con diritti sufficienti a modificare le autorizzazioni sull'oggetto del dominio.
  
    2.  Aprire lo snap-in Utenti e computer di Active Directory e fare clic con il pulsante destro del mouse sul nodo del dominio.
  
    3.  Fare clic su **Delega controllo** per avviare la procedura Aggiunta guidata nuova delega.
  
    4.  Nella procedura guidata fare clic su **Avanti**, quindi aggiungere il gruppo Cert Publishers del dominio in cui la CA di emissione è stata installata. Quindi fare clic su **Avanti**.
  
    5.  Selezionare **Crea un'operazione personalizzata per eseguire la delega**, quindi fare clic su **Avanti**.
  
    6.  Selezionare **Solo i seguenti oggetti contenuti** nella cartella.
  
    7.  Scegliere **Oggetti USER**, quindi fare clic su **Avanti**.
  
    8.  Selezionare l'opzione **Proprietà**.
  
    9.  Selezionare le opzioni **Read userCertificate** e **Write userCertificate**.
  
    10. Fare clic su **Avanti**, quindi su **Fine**.
  
    11. Ripetere i passaggi da 3 a 10, ma al passaggio 7, selezionare **Oggetti Computer** invece di **Oggetti User**.
  
In questo modo si assicura che le CA dell'organizzazione dispongano dell'autorizzazione a pubblicare correttamente i certificati per gli utenti degli altri domini.
  
#### Backup delle chiavi e dei server CA
  
Dopo aver creato la CA principale ed emittente, è necessario eseguirne il backup prima possibile, in modo da proteggere i database delle chiavi e dei certificati in caso di errore del server o danneggiamento dei dati.
  
A questo scopo, seguire le procedure descritte nel modulo["Gestione dell'infrastruttura a chiave pubblica"](http://technet.microsoft.com/it-it/library/dd536252.aspx) della *Guida alla pianificazione.*
  
-   Configurazione del backup della CA di emissione
  
-   Configurazione ed esecuzione del backup della CA principale
  
-   Backup delle chiavi e dei certificati delle CA (da eseguire per ciascuna CA)
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione dei client
  
In questa sezione vengono descritte alcune delle attività di configurazione dei client più importanti. La maggior parte delle attività relative ai client non è oggetto tuttavia di questa sezione, in quanto è specifica dell'applicazione che utilizza Servizi certificati, ad esempio della WLAN o la rete privata virtuale (VPN) e non di tutte le applicazioni di certificazione.
  
#### Attivazione della registrazione automatica dei certificati di utenti e computer
  
Utilizzando le procedure descritte precedentemente è possibile utilizzare i gruppi di protezione e le autorizzazioni sui modelli per controllare la registrazione automatica a un livello molto specifico. Tuttavia, la funzionalità di registrazione automatica è disattivata nei client per impostazione predefinita. Per attivarla, è necessario abilitare l'impostazione corretta nei criteri di gruppo. Se si utilizzano i gruppi di protezione per controllare la registrazione automatica, è possibile attivare la registrazione automatica per tutti gli utenti del dominio.
  
**Avviso:** questa procedura consente la registrazione automatica per *tutti* i computer e gli utenti del dominio. Assicurarsi di aver rimosso i modelli predefiniti dalla CA di emissione prima di avviare questa procedura, in modo da evitare la registrazione dei certificati Computer e utenti predefiniti per ogni computer e utente del dominio. Questa procedura presume che la registrazione automatica verrà controllata automaticamente utilizzando i gruppi di protezione, come descritto nel modulo["Gestione dell'infrastruttura a chiave pubblica"](http://technet.microsoft.com/it-it/library/dd536252.aspx)della *Guida alla pianificazione.*
  
-   **Per attivare la registrazione automatica per tutti gli utenti e computer del dominio**
  
    1.  Accedere utilizzando un account che disponga delle autorizzazioni per creare GPO (un membro del gruppo Proprietari autori criteri di gruppo) e collegarli al dominio. In alternativa, l'utente deve richiedere a un amministratore del dominio di creare e collegare il GPO e di assegnargli i diritti di lettura e scrittura su di esso.
  
    2.  In Utenti e computer di Active Directory selezionare l'oggetto dominio, fare clic con il pulsante destro del mouse, quindi scegliere **Proprietà**.
  
    3.  Nella scheda **Criteri gruppo** fare clic su **Nuovo**, quindi digitare un nome per il GPO, ad esempio *Criteri PKI dominio*.
  
    4.  Fare clic su **Modifica** per modificare il GPO e passare a Criteri chiave pubblica sotto Configurazione computer\\Impostazioni di Windows\\Impostazioni di protezione.
  
    5.  Nel riquadro dei dettagli, fare doppio clic su **Impostazioni registrazione automatica**.
  
    6.  Assicurarsi che le voci seguenti siano selezionate:
  
        -   **Registra i certificati automaticamente**
  
        -   **Rinnova i certificati scaduti, aggiorna quelli in sospeso e rimuovi i certificati revocati**
  
        -   **Aggiorna i certificati che utilizzano modelli di certificato**
  
    7.  Ripetere i passaggi 5 e 6 per le impostazioni di registrazione automatica per l'utente in Configurazione utente\\Impostazioni di Windows\\Impostazioni di protezione\\Criteri chiave pubblica.
  
    8.  Chiudere il GPO.
  
    9.  Assicurarsi che il GPO abbia una priorità più alta rispetto al GPO Criteri di dominio predefinito.
  
**Note:** se si dispone di un insieme di strutture Active Directory multidominio, è necessario eseguire questa procedura per ciascun dominio dell'insieme di strutture in cui si desidera attivare la registrazione automatica.
  
Se non si desidera attivare la registrazione automatica per tutti gli utenti o i computer del dominio, è possibile creare GPO collegati alle OU che contengano gli utenti e/o i computer per cui si desidera attivare la registrazione automatica.
  
Se gli utenti non utilizzano profili comuni, ne può conseguire la registrazione di un certificato per un utente in qualsiasi computer da cui esegue l'accesso. È possibile evitare la registrazione automatica dei certificati utente per gli amministratori e gli operatori che accedono ai server. A questo scopo, è possibile creare un GPO da applicare a tali server, ad esempio, collegandolo all'OU dei server. Nel GPO creato, disattivare la registrazione automatica per gli utenti selezionando **Non effettuare la registrazione automatica dei certificati**. Nello stesso GPO, consentire l'elaborazione loopback attivando l'impostazione **della modalità loopback di Configurazione computer\\Modelli amministrativi\\Sistema\\Criterio gruppo\\Criteri di gruppo dell'utente** e selezionando l'opzione **Sostituisci**.
  
L'attivazione della registrazione automatica del certificato è descritta inoltre dettagliatamente nei documenti elencati nella sezione "[Ulteriori informazioni](http://www.microsoft.com/downloads/details.aspx?familyid=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en)" alla fine di questo modulo.
  
Solo i client Windows XP e versioni successive supportano la registrazione automatica di entrambi i certificati utente e computer. I client Windows 2000 supportano solo la registrazione automatica dei certificati computer.
  
Se si sta implementando questa soluzione in un ambiente Active Directory di Windows 2000, è necessario modificare i GPO da un computer che esegue Windows Server 2003 o Windows XP Professional in cui sono installati gli strumenti di amministrazione di Windows Server 2003 (Windows XP richiede un livello di Service Pack e di aggiornamenti rapidi specifico per supportare gli strumenti amministrativi di Windows Server 2003).
  
#### Configurazione dei criteri di domino dell'autorità di certificazione principale
  
In questa sezione viene descritto come stabilire quali CA commerciali principali devono essere considerate attendibili dai client dell'organizzazione e se i singoli utenti possono scegliere o meno di modificare tali CA.
  
##### Gestione dei trust di terzi
  
I client Windows sono configurati per impostazione predefinita in modo che considerino attendibili un vasto numero di CA commerciali principali (note come baked-in-root). Per impedire agli utenti di considerare automaticamente attendibili le CA principali di terzi, consultare la procedura descritta nell'argomento "To prevent users from trusting third-party root certification authorities with a Group Policy" nella Guida in linea o il collegamento elencato nella sezione "[Ulteriori informazioni](http://www.microsoft.com/italy/technet/security/guidance/microsoft_guide_for_securing_wlans/secmod161.mspx)" alla fine di questo modulo.
  
**Nota:** la disattivazione delle CA principali di terzi può causare errori nelle applicazioni client, quindi, non eseguire questa operazione senza valutarne attentamente le conseguenze. Ad esempio, le connessioni dei client alla maggior parte dei siti Web pubblici protetti determineranno un errore di attendibilità.
  
È possibile eliminare alcuni dei problemi conseguenti la rimozione di tutti i trust di terzi in diversi modi:
  
-   È possibile aggiungere in modo selettivo singole CA principali all'impostazione del criterio Autorità di certificazione principale attendibili in Criteri di gruppo.
  
-   È possibile aggiungere i certificati principali agli elenchi di certificati attendibili e distribuirli tramite l'impostazione Attendibilità per l'organizzazione di Criteri di gruppo. Questo metodo consente inoltre di controllare l'utilizzo per cui vengono ritenuti attendibili i certificati che le CA principali rilasciano.
  
-   Infine, è possibile eseguire una certificazione incrociata (o creare una relazione di trust subordinata qualificata con) delle altre autorità di certificazione. In questo modo si ottiene un controllo ancora maggiore sull'utilizzo e sui parametri dei certificati che verranno considerati attendibili nell'organizzazione.
  
L'utilizzo degli elenchi dei certificati attendibili o di una relazione di trust subordinata qualificata è il modo più sicuro per distribuire le CA principali attendibili di terzi nell'organizzazione. Questo argomento è descritto più dettagliatamente nel modulo, "[Progettazione di un'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536257)" della *Guida alla pianificazione*.
  
##### Gestione del controllo utente sulle CA principali attendibili
  
È possibile inoltre utilizzare i criteri di gruppo per impedire agli utenti di selezionare nuove CA principali come attendibili. Questo è particolarmente importante se sono stati creati elenchi di certificati attendibili propri o relazioni di trust subordinate qualificate per controllare l'uso dei certificati di terzi nell'organizzazione. La procedura relativa all'utilizzo dei criteri di gruppo per la gestione del controllo utente sulle CA principali attendibili è disponibile nell'argomento "To prevent users from selecting new root certification authorities with a Group Policy" nella Guida in linea oppure nel collegamento elencato nella sezione "[Ulteriori informazioni](http://www.microsoft.com/italy/technet/security/guidance/secmod170.mspx)", alla fine di questo modulo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Sono state completate le attività seguenti:
  
-   Installazione e configurazione di una CA principale non in linea
  
-   Installazione e configurazione di una CA di emissione in linea
  
-   Installazione e configurazione di un server Web per la pubblicazione di CRL e certificati delle CA
  
-   Configurazione di gruppi e utenti amministrativi per la gestione delle CA e delle informazioni di configurazione della PKI di Active Directory
  
-   Configurazione di Active Directory e dei Criteri di gruppo per il supporto dell'infrastruttura PKI
  
A questo punto si è pronti per configurare le applicazioni in modo che utilizzino l'infrastruttura PKI. Tale configurazione è descritta nei moduli "[Implementazione dell'infrastruttura RADIUS per la protezione di reti LAN senza fili](#xsltsection136121120120)" e "[Implementazione della protezione di reti LAN senza fili mediante lo standard 802.1X](http://technet.microsoft.com/it-it/library/dd536251)" di questa guida
  
È necessario inoltre leggere le sezioni pertinenti del modulo["Gestione dell'infrastruttura a chiave pubblica"](http://technet.microsoft.com/it-it/library/dd536252.aspx) della *Guida alla pianificazione.* In questa guida sono contenute le informazioni essenziali per garantire il funzionamento dell'infrastruttura in un ambiente protetto e affidabile.
  
#### Ulteriori informazioni
  
Ulteriori informazioni sono disponibili nei documenti seguenti.
  
**Informazioni di carattere generale sull'infrastruttura PKI e sui Servizi certificati di Windows**
  
-   Per un'introduzione esauriente ai concetti di PKI e alle caratteristiche di Servizi certificati di Windows 2000, vedere "An Introduction to the Windows 2000 Public-Key Infrastructure" all'indirizzo <http://technet.microsoft.com/en-us/library/cc768063.aspx> (in inglese).
  
-   Per una descrizione delle funzionalità avanzate dell'infrastruttura PKI in Windows Server 2003 e Windows XP, vedere "PKI Enhancements in Windows XP Professional and Windows Server 2003" all'indirizzo <http://technet.microsoft.com/en-us/library/bb457034.aspx> (in inglese).
  
-   Per la documentazione generale sul prodotto in cui sono descritti i concetti chiave e le attività amministrative, vedere la Guida in linea di Servizi certificati o la versione disponibile nel sito Web di Microsoft all'indirizzo <http://technet.microsoft.com/en-us/library/cc700832.aspx> (in inglese).
  
**Informazioni sugli argomenti specifici**
  
-   Per ulteriori informazioni sull'implementazione di una PKI in un ambiente Active Directory a più insiemi di strutture, vedere [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/sag\_CS\_procs\_xforest\_cert\_pub.asp](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/sag_cs_procs_xforest_cert_pub.asp) (in inglese).
  
-   È possibile scaricare l'ultima versione di CAPICOM da: [http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=860EE43A-A843-462F-ABB5-FF88EA5896F6](http://www.microsoft.com/downloads/details.aspx?displaylang=en&familyid=860ee43a-a843-462f-abb5-ff88ea5896f6) (in inglese).
  
-   Per ulteriori informazioni sullo strumento ADPrep, vedere l'articolo Q325379 della Knowledge Base disponibile all'indirizzo [http://support.microsoft.com/default.aspx?scid=kb;en-us;Q325379](http://support.microsoft.com/default.aspx?scid=kb;en-us;q325379) (in inglese) e la pagina della documentazione ADPrep disponibile all'indirizzo <http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/adprep.asp> (in inglese).
  
-   Per ulteriori informazioni sui requisiti del livello di patch ADPrep, vedere l'articolo Q331161 della Knowledge Base disponibile all'indirizzo [http://support.microsoft.com/default.aspx?scid=kb;en-us;Q331161](http://support.microsoft.com/default.aspx?scid=kb;en-us;q331161) (in inglese).
  
-   Per ulteriori informazioni sui ruoli di protezione del server utilizzati in questa guida, vedere la guida *Windows Server 2003 Security Guide*, disponibile all'indirizzo [http://go.microsoft.com/fwlink/?LinkId=14845](http://go.microsoft.com/fwlink/?linkid=14845) (in inglese).
  
-   Per informazioni su come disattivare il trust automatico per le CA di terzi, vedere l'articolo "To prevent users from trusting third-party root certification authorities with a Group Policy*" di TechNet* all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/sag\_PKPprocsConfig 3rdpartyRootCA.asp](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/sag_pkpprocsconfig3rdpartyrootca.asp) (in inglese).
  
-   Per informazioni su come gestire il controllo utente sulle CA principali attendibili, vedere l'articolo "To prevent users from selecting new root certification authorities with a Group Policy *di TechNet,* " all'indirizzo [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/sag\_PKPprocs ConfigTrustedRootCA.asp](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/sag_pkpprocsconfigtrustedrootca.asp) (in inglese).
  
-   Per ulteriori informazioni sulla registrazione automatica dei certificati, fare riferimento al white paper "Certificate Autoenrollment in Windows XP" disponibile all'indirizzo [http://www.microsoft.com/WindowsXP/pro/techinfo/administration/autoenroll/default.asp](http://www.microsoft.com/windowsxp/pro/techinfo/administration/autoenroll/default.asp) (in inglese) e l'articolo nella documentazione di Windows Server 2003 disponibile all'indirizzo <http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/certsrv_checklist_autoenroll.asp> (in inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
