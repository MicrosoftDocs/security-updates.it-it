---
TOCTitle: 'Guida alla creazione - Implementazione dell''infrastruttura a chiave pubblica'
Title: 'Guida alla creazione - Implementazione dell''infrastruttura a chiave pubblica'
ms:assetid: '50df104f-0496-4d76-8ef3-0eabf796de2f'
ms:contentKeyID: 20200788
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536188(v=TechNet.10)'
---

Capitolo 7: Implementazione dell’infrastruttura a chiave pubblica
=================================================================

Pubblicato: 11 ottobre 2004 | Aggiornato: 24/11/2004

##### In questa pagina

[](#ekaa)[Introduzione](#ekaa)
[](#ejaa)[Foglio di lavoro per la pianificazione di Servizi certificati](#ejaa)
[](#eiaa)[Creazione dei propri server](#eiaa)
[](#ehaa)[Preparazione di Active Directory per l'infrastruttura PKI](#ehaa)
[](#egaa)[Protezione di Windows Server 2003 per Servizi certificati](#egaa)
[](#efaa)[Altre attività di configurazione di Windows](#efaa)
[](#eeaa)[Installazione e configurazione della CA principale](#eeaa)
[](#edaa)[Installazione e configurazione della CA di emissione](#edaa)
[](#ecaa)[Configurazione post-creazione](#ecaa)
[](#ebaa)[Configurazione dei client](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

#### Introduzione

Questo capitolo contiene informazioni dettagliate relative alla creazione di un'infrastruttura a chiave pubblica (PKI) basata su Servizi certificati di Microsoft® Windows Server™ 2003 e include l'installazione e la configurazione delle autorità di certificazione (CA), la preparazione del servizio directory Active Directory e di Microsoft Internet Information Services (IIS), nonché la configurazione dei criteri di certificazione dei client. Le indicazioni fornite intendono guidare l'utente nella creazione dell'infrastruttura di certificazione che verrà usata nei successivi capitoli per la creazione di una soluzione di protezione per reti LAN senza fili.

Scopo del presente capitolo è fornire istruzioni per la progettazione di un'infrastruttura PKI descritta nel capitolo 4, "Progettazione dell’infrastruttura a chiave pubblica (PKI)." Esula pertanto dagli obiettivi del capitolo l'illustrazione dei concetti generali alla base di un'infrastruttura PKI o la descrizione delle specifiche per l'implementazione di Servizi certificati Microsoft.

Questo capitolo è correlato ai capitoli riguardanti la pianificazione di un'infrastruttura PKI e le relative operazioni, rispettivamente il capitolo 4 e il capitolo 11. Il capitolo Guida alla pianificazione spiega le motivazioni delle decisioni relative all'implementazione illustrate in questo capitolo, mentre il capitolo Guida operativa descrive le attività e i processi necessari per la gestione dell'infrastruttura RADIUS. Prima di proseguire con gli argomenti del capitolo, si consiglia di leggere i capitoli relativi alla pianificazione. Prima di applicare le linee guida fornite in questo capitolo per implementare l'infrastruttura PKI, è opportuno inoltre leggere e comprendere le implicazioni dei requisiti di supporto nella Guida operativa.

### Prima di iniziare

Questa sezione contiene elenchi di controllo che aiutano a valutare il grado di preparazione di un'azienda in merito all'implementazione dell'infrastruttura PKI (in questo contesto, il termine "preparazione" si riferisce più all'aspetto logistico che a quello aziendale: le motivazioni aziendali che portano all'implementazione di questa soluzione sono trattate nei primi capitoli della Guida alla pianificazione).

##### Prima di iniziare

È necessario conoscere i concetti fondamentali relativi all'infrastruttura PKI e a Servizi certificati Microsoft. È inoltre consigliabile acquisire dimestichezza con Windows 2000 Server o Windows Server 2003 nelle seguenti aree:

-   Installazione del sistema operativo di Microsoft Windows®.

-   Concetti relativi ad Active Directory, tra cui la struttura e gli strumenti di Active Directory; la gestione di utenti, gruppi e altri oggetti Active Directory e l’uso dei criteri di gruppo.

-   Concetti alla base della protezione dei sistemi Windows, quali utenti, gruppi, controllo, elenchi di controllo di accesso (ACL), utilizzo dei modelli di protezione e applicazione dei modelli di protezione mediante Criteri di gruppo o utilizzo degli strumenti della riga di comando.

-   Amministrazione di IIS.

-   Anche se non è essenziale, la conoscenza di Windows Scripting Host e del linguaggio Microsoft Visual Basic® Scripting Edition (VBScript) può contribuire a trarre il massimo vantaggio dagli script forniti.

Prima di proseguire con gli argomenti del capitolo, è necessario aver letto anche la Guida alla pianificazione e avere compreso l’architettura e la progettazione della soluzione.

##### Prerequisiti organizzativi

È consigliabile consultare altri membri della propria azienda che dovrebbero essere coinvolti nell'implementazione di questa soluzione, quali:

-   Finanziatori dell'iniziativa

-   Personale addetto al controllo e alla protezione

-   Personale addetto a progettazione, amministrazione e operazioni di Active Directory

-   Personale addetto a DNS (Domain Name System), server Web e progettazione

-   Personale addetto ad amministrazione e operazioni

##### Prerequisiti per l'infrastruttura IT

Per quanto riguarda l'infrastruttura IT esistente, in questo capitolo si presuppone quanto segue:

-   Esiste un'infrastruttura di dominio di Active Directory di Windows 2000 o Windows Server 2003. Tutti gli utenti di Servizi certificati in questa soluzione devono essere membri di un dominio all'interno dello stesso insieme di strutture di Active Directory.

    **Note:**
    sebbene sia pienamente supportato l'uso di Servizi certificati Windows Server 2003 e del Servizio autenticazione Internet (implementazione RADIUS di Microsoft-IAS) con Active Directory di Windows 2000, la soluzione non è stata collaudata in tale configurazione, ma solo con Active Directory di Windows Server 2003. La guida comprende comunque anche istruzioni per l'uso di Active Directory di Windows 2000.
    Nonostante sia possibile distribuire la soluzione a più insiemi di strutture con modifiche minime, ciò esula dagli obiettivi della presente guida. Per ulteriori informazioni sulla distribuzione a più insiemi di strutture, vedere la nota riportata nella sezione "Ulteriori informazioni" alla fine del capitolo.
    Non sono fornite istruzioni per effettuare l'integrazione in un'infrastruttura PKI esistente. Tuttavia ciò non esclude la possibilità di una distribuzione accanto a un'infrastruttura PKI esistente.

-   È disponibile l'hardware del server in grado di supportare l'esecuzione di Servizi certificati di Windows Server 2003. Questa guida contiene una configurazione consigliata.

-   La soluzione non è stata espressamente progettata per l'integrazione con un'infrastruttura PKI esistente. Tuttavia ciò non esclude la possibilità di una distribuzione accanto a un'infrastruttura PKI esistente.

-   Sono disponibili le licenze, i supporti di installazione e i codici "Product Key" di Windows Server 2003 Standard Edition e Enterprise Edition.

#### Panoramica dei capitoli

La figura seguente mostra il processo di creazione dell'infrastruttura PKI che sarà descritto in questo capitolo.

![](images/Dd536188.07fig7-1(it-it,TechNet.10).gif "Figura 7.1 Diagramma del processo di creazione dell'infrastruttura PKI")

**Figura 7.1 Diagramma del processo di creazione dell'infrastruttura PKI**

Questi passaggi rispecchiano l'organizzazione del capitolo e sono descritti nell'elenco seguente. Ciascuno di essi è costituito da attività di installazione o configurazione e dispone di procedure di verifica che consentono di controllare le operazioni eseguite prima di continuare con il passaggio successivo.

-   **Foglio di lavoro per la pianificazione di Servizi certificati** Sono elencate le informazioni di configurazione utilizzate in questo capitolo per installare e configurare Servizi certificati. È inclusa una tabella di informazioni che devono essere fornite dall'utente prima di iniziare l'implementazione.

-   **Creazione dei propri server** Vengono descritte le procedure di selezione e configurazione dell'hardware, l'installazione di Windows Server 2003 e l'installazione di componenti opzionali, quali IIS.

-   **Preparazione di Active Directory per l'infrastruttura PKI** Illustra i prerequisiti relativi al dominio e all'insieme di strutture Active Directory in cui verrà distribuita l'infrastruttura PKI, oltre alle fasi preliminari fondamentali. Inoltre, vengono descritte la creazione di utenti e gruppi di protezione per la gestione e l'impostazione delle autorizzazioni necessarie per la delega delle attività di gestione.

-   **Protezione di Windows Server 2003 per Servizi certificati **Viene illustrata l'implementazione della protezione a livello di sistema operativo mediante l'applicazione di modelli di protezione. I modelli utilizzati sono desunti dalla *Guida per la protezione di Windows Server 2003*. Per i dettagli su come ottenere tale guida, consultare la sezione "Ulteriori informazioni" alla fine di questo capitolo.

-   **Altre attività di configurazione di Windows **Sono elencate alcune attività comuni per completare l'installazione di base dei server.

-   **Installazione e configurazione della CA principale **Descrive i passaggi di preparazione, l'installazione del software e la configurazione di Servizi certificati, oltre alla definizione dei ruoli amministrativi del server. La pubblicazione del certificato della CA principale non in linea e dell'elenco di revoche di certificati (CRL, Certificate Revocation List) in Active Directory e nel server Web rappresenta la fase conclusiva.

-   **Installazione e configurazione della CA di emissione** Analoga alla guida relativa alla CA principale, ma include inoltre la procedura per la richiesta di un certificato alla CA principale. La fase di verifica finale garantisce che sia possibile registrare i certificati della CA di emissione.

-   **Configurazione post-creazione** Illustra la configurazione dei tipi di certificati predefiniti rilasciati dalla CA di emissione, l'impostazione delle autorizzazioni per un insieme di strutture multidominio e l'esecuzione dei backup delle CA prima dell'introduzione nell'ambiente di produzione.

-   **Configurazione dei client **Descrive in che modo attivare la registrazione automatica per tutti gli utenti e i computer del dominio e come configurare i criteri di attendibilità dei certificati principali.

[](#mainsection)[Inizio pagina](#mainsection)

### Foglio di lavoro per la pianificazione di Servizi certificati

Nelle tabelle di questa sezione vengono elencati i parametri di configurazione dell'infrastruttura PKI utilizzati in questa soluzione. Devono essere considerati come un elenco di controllo quando si prendono le decisioni relative alla pianificazione.

Alcuni dei parametri contenuti in queste tabelle sono inseriti manualmente, come prevedono le procedure documentate nel capitolo. Altri vengono impostati da uno script eseguito come parte di una procedura oppure viene fatto riferimento al parametro da uno script, per completare un'altra configurazione o un'attività operativa. In tal caso, il nome del relativo script è incluso nella tabella.

**Nota:** gli script utilizzati in questo capitolo vengono descritti in modo più dettagliato nell'appendice A e nel file ToolsReadme.txt allegato agli script.

#### Elementi di configurazione definiti dagli utenti

La tabella che segue elenca dei parametri specifici dell'azienda fittizia Woodgrove Bank. Prima di iniziare la procedura di configurazione, occorre accertarsi di aver raccolto o deciso le impostazioni equivalenti per la propria organizzazione di tutti gli elementi indicati nella sottostante tabella. Negli esempi dei comandi citati nell'intero capitolo vengono utilizzati i valori fittizi mostrati in questa tabella. È necessario sostituire tali valori fittizi con i valori adeguati alla propria organizzazione. I valori che è necessario sostituire sono indicati in corsivo.

**Tabella 7.1. Elementi di configurazione definiti dagli utenti**

 
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
<th style="border:1px solid black;" >Riferimento script</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nome di dominio DNS per la radice di strutture Active Directory</td>
<td style="border:1px solid black;">woodgrovebank.com</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DN (Distinguished Name) nome distinto della directory principale dell'insieme di strutture</td>
<td style="border:1px solid black;">DC=woodgrovebank,DC=com</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome NetBIOS (Network Basic Input/Output System) del dominio</td>
<td style="border:1px solid black;">WOODGROVEBANK</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome NetBIOS del gruppo di lavoro della CA principale</td>
<td style="border:1px solid black;">WGB-Root</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome server della CA principale</td>
<td style="border:1px solid black;">HQ-CA-01</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome server della CA di emissione</td>
<td style="border:1px solid black;">HQ-CA-02</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">X.500 Nome comune (CN) della CA principale</td>
<td style="border:1px solid black;">WoodGrove Bank Root CA</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">X.500 CN della CA di emissione</td>
<td style="border:1px solid black;">WoodGrove Bank Issuing CA 1</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome host completo del server Web utilizzato per pubblicare il certificato della CA e le informazioni di revoca</td>
<td style="border:1px solid black;">www.woodgrovebank.com</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
</tbody>
</table>
  
#### Elementi di configurazione indicati dalla soluzione
  
Le impostazioni specificate in questa tabella non devono essere modificate, a meno che non sia necessario utilizzare un'impostazione diversa da quella della progettazione della soluzione. La modifica dei parametri di progettazione forniti in questa tabella è perfettamente accettabile, ma occorre essere consapevoli del fatto che così facendo ci si discosta dalla soluzione collaudata. Prima di modificare eventuali valori nelle procedure di configurazione o negli script forniti, assicurarsi di avere compreso a fondo le implicazioni della modifica che si intende apportare e le dipendenze che tale impostazione potrebbe avere.
  
**Tabella 7.2. Elementi di configurazione indicati dalla soluzione**

 
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
<th style="border:1px solid black;" >Riferimento script</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Gruppi di protezione del ruolo amministrativo</td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Amministratori del contenitore della configurazione dei servizi a chiave pubblica.</td>
<td style="border:1px solid black;">Amministratori PKI dell'organizzazione</td>
<td style="border:1px solid black;">ca_setup.wsf</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Gruppo amministrativo a cui è consentito pubblicare elenchi di revoca certificati (CRL, Certificate Revocation List) e certificati CA nel contenitori della configurazione dell'organizzazione.</td>
<td style="border:1px solid black;">Autori PKI dell'organizzazione</td>
<td style="border:1px solid black;">ca_setup.wsf</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gruppo amministrativo che configura e gestisce le CA; controlla inoltre la possibilità di assegnare tutti gli altri ruoli della CA e rinnovare il certificato CA.</td>
<td style="border:1px solid black;">Amministratori CA</td>
<td style="border:1px solid black;">ca_setup.wsf</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Gruppo amministrativo che approva le richieste di registrazione e revoca dei certificati. Questo è un ruolo di Responsabile della CA.</td>
<td style="border:1px solid black;">Responsabili certificazione</td>
<td style="border:1px solid black;">ca_setup.wsf</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gruppo amministrativo che gestisce il controllo CA e i registri di protezione.</td>
<td style="border:1px solid black;">Controllori CA</td>
<td style="border:1px solid black;">ca_setup.wsf</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Gruppo amministrativo che gestisce i backup CA.</td>
<td style="border:1px solid black;">Operatori backup CA</td>
<td style="border:1px solid black;">ca_setup.wsf</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Configurazione IIS</strong></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome della directory virtuale IIS (Internet Information Services) utilizzata per pubblicare le informazioni relative al certificato CA e al CRL.</td>
<td style="border:1px solid black;">pki</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Percorso fisico nella CA di emissione mappato alla directory virtuale IIS.</td>
<td style="border:1px solid black;">C:\CAWWWPub</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Parametri comuni della CA</strong></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Unità e percorso per archiviare i file di richieste di Servizi certificati.</td>
<td style="border:1px solid black;">C:\CAConfig</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Unità e percorso per archiviare i registri del database di Servizi certificati.</td>
<td style="border:1px solid black;">%windir%\System32\CertLog</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Configurazione della CA principale</strong></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Lunghezza della chiave della CA principale
(vedere la nota che segue questa tabella).</td>
<td style="border:1px solid black;">4096</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo di validità del certificato della CA principale.</td>
<td style="border:1px solid black;">16</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Unità per il valore precedente.</td>
<td style="border:1px solid black;">Anni</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo massimo di validità dei certificati rilasciati dalla CA principale.</td>
<td style="border:1px solid black;">8</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Unità del valore precedente.</td>
<td style="border:1px solid black;">Anni</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Intervallo di pubblicazione dei CRL per la CA principale.</td>
<td style="border:1px solid black;">6</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Unità del valore precedente.</td>
<td style="border:1px solid black;">Mesi</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo di sovrapposizione dei CRL (tempo che intercorre tra la pubblicazione del nuovo CRL e la scadenza del vecchio CRL).</td>
<td style="border:1px solid black;">10</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Unità del valore precedente.</td>
<td style="border:1px solid black;">Giorni</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo di pubblicazione di Delta CRL relativi alla CA principale - 0 = disattivazione dei Delta - CRL.</td>
<td style="border:1px solid black;">0</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Unità del valore precedente.</td>
<td style="border:1px solid black;">Ore</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Parametri della CA di emissione</strong></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Unità e percorso per archiviare il database di Servizi certificati.</td>
<td style="border:1px solid black;">D:\CertLog</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Lunghezza della chiave della CA di emissione.</td>
<td style="border:1px solid black;">2048</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo di validità del certificato della CA di emissione.</td>
<td style="border:1px solid black;">8</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Unità del valore precedente.</td>
<td style="border:1px solid black;">Anni</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo massimo di validità dei certificati rilasciati dalla CA di emissione.</td>
<td style="border:1px solid black;">4</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Unità del valore precedente.</td>
<td style="border:1px solid black;">Anni</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Intervallo di pubblicazione dei CRL per la CA di emissione.</td>
<td style="border:1px solid black;">7</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Unità del valore precedente.</td>
<td style="border:1px solid black;">Giorni</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo di sovrapposizione dei CRL (tempo che intercorre tra la pubblicazione del nuovo CRL e la scadenza del vecchio CRL).</td>
<td style="border:1px solid black;">4</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Unità del valore precedente.</td>
<td style="border:1px solid black;">Giorni</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo di pubblicazione di Delta CRL per la CA di emissione - 0 = disattivazione dei Delta - CRL.</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Unità del valore precedente.</td>
<td style="border:1px solid black;">Giorni</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo di sovrapposizione di Delta CRL (tempo che intercorre tra la pubblicazione del nuovo Delta CRL e la scadenza del vecchio Delta CRL).</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Unità del valore precedente.</td>
<td style="border:1px solid black;">Giorni</td>
<td style="border:1px solid black;">Pkiparams.vbs</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Varie</strong></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Percorso degli script di installazione.</td>
<td style="border:1px solid black;">C:\MSSScripts</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
</tbody>
</table>
 

**Importante:** la configurazione di una chiave della lunghezza di 4.096 bit potrebbe causare problemi di compatibilità se i certificati devono essere rilasciati a o utilizzati da alcune periferiche (ad esempio alcuni tipi di router) o versioni precedenti di software di altri fornitori, non in grado di elaborare chiavi di dimensioni superiori a un determinato valore. È necessario testare le applicazioni utilizzando certificati con una chiave del certificato della CA principale di queste dimensioni prima dell'implementazione della PKI. Se la lunghezza della chiave costituisce un problema, ridurre la dimensione della chiave della CA principale a 2048 bit. Questo dato deve essere specificato nel file CAPolicy.inf al momento dell'installazione della CA principale. Vedere la sezione "Installazione e configurazione della CA principale".

[](#mainsection)[Inizio pagina](#mainsection)

### Creazione dei propri server

In questa sezione vengono descritte le attività di base per la preparazione dell'hardware del server e l'installazione del sistema operativo. Sono necessari due server: uno per la CA principale e l'altro per la CA di emissione.

**Importante:** prima di iniziare la creazione delle CA, è necessario leggere la sezione "Gestione della protezione delle CA" nel capitolo 4, "Progettazione dell'infrastruttura a chiave pubblica (PKI)", poiché la creazione delle CA potrebbe influire sull'ambiente di protezione usato per creare i server.

#### Selezione e configurazione dell'hardware dei server

Nelle sezioni seguenti vengono descritte le specifiche di base dei server per entrambi i ruoli CA. Il capitolo 4, "Progettazione dell’infrastruttura a chiave pubblica (PKI)", esamina più dettagliatamente alcuni criteri fondamentali per la selezione dell'hardware.

##### Hardware per il server della CA principale

La seguente tabella mostra le specifiche hardware consigliate per la CA principale, basate sulle raccomandazioni generali relative all'hardware necessario per Windows Server 2003. Tuttavia, potrebbe non essere necessario acquistare nuovo hardware se quello esistente è conforme ai criteri indicati nel capitolo 4 alla pianificazione ma non viene utilizzato per motivi relativi alle prestazioni.

**Tabella 7.3. Specifiche hardware consigliate per il server CA principale**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Elemento</th>
<th style="border:1px solid black;" >Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CPU</td>
<td style="border:1px solid black;">CPU singola a 733 MHz o superiore</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Memoria</td>
<td style="border:1px solid black;">256 MB</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Interfacce di rete</td>
<td style="border:1px solid black;">Nessuna (o disattivate)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Archiviazione disco</td>
<td style="border:1px solid black;">Controller RAID (Redundant Array of Independent Disks) IDE (Integrated Device Electronics) o SCSI (Small Computer System Interface)
2 x 18 GB (SCSI) o 2 x 20 GB (IDE) configurato come volume RAID 1 (unità C)
Archiviazione su supporti rimovibili locali (CD-RW o nastro di backup)
Unità disco floppy da 1,44 MB per il trasferimento dei dati</td>
</tr>
</tbody>
</table>
 

##### Hardware per il server della CA di emissione

Nonostante per le CA di emissione si debbano rispettare determinati requisiti di prestazioni, questi sono alquanto ridotti visto che le attività di tali CA sono decisamente limitate rispetto a molti altri tipi di server. Restano validi anche in questo caso i criteri di qualità e affidabilità per la selezione dell'hardware raccomandati per il server della CA principale. Esistono alcune differenze secondarie rispetto alle specifiche della CA principale relativamente alla connettività di rete e all'archiviazione, come mostrato nella seguente tabella:

**Tabella 7.4. Specifiche hardware consigliate per il server CA di emissione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Elemento</th>
<th style="border:1px solid black;" >Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CPU</td>
<td style="border:1px solid black;">CPU singola a 733 MHz o superiore</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Memoria</td>
<td style="border:1px solid black;">256 MB</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Interfacce di rete</td>
<td style="border:1px solid black;">2 x singole schede di interfaccia di rete (NIC, network interface card) unite per una maggiore adattabilità</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Archiviazione disco</td>
<td style="border:1px solid black;">Controller RAID IDE o SCSI
2 x 18 GB (SCSI) o 2 x 20-GB (IDE) configurato come volumi RAID 1 (unità C e D)
Archiviazione su supporti rimovibili locali (CD-RW o nastro di backup), in assenza di una funzionalità di backup di rete
Unità disco floppy da 1,44 MB per il trasferimento dei dati</td>
</tr>
</tbody>
</table>
 

**Importante:** le specifiche relative al server indicate in questa tabella sono adatte ad un numero di utenti pari a circa 5.000. Se l'utenza è maggiore, occorre almeno raddoppiare la capacità del disco relativa alla seconda unità (in modo da rendere disponibile circa 2 GB per 1000 utenti) e raddoppiare anche le dimensioni della memoria installata. Per linee guida sull'uso del disco, vedere la sezione "Definizione dei requisiti di archiviazione e backup per un'autorità di certificazione emittente" nel capitolo 11, "Gestione dell'infrastruttura a chiave pubblica".

##### Preparazione dell'hardware

Completare tutte le configurazioni hardware in base alle indicazioni del fornitore hardware. Tali indicazioni potrebbero riguardare anche l'applicazione degli aggiornamenti più recenti del BIOS e dei firmware.

Utilizzare il software di gestione del controller disco fornito con l'hardware per creare i volumi RAID 1 come illustrato nella tabella precedente (un volume per la CA principale, due per la CA di emissione).

#### Preparazione del server della CA principale

In questa sezione viene descritta l'installazione di Windows nel server che verrà utilizzato per la CA principale.

##### Installazione di Windows Server 2003 Standard Edition

Molte organizzazioni dispongono già di un processo automatico di installazione server. Se i parametri utilizzati in questa sezione possono essere inclusi nel processo automatico di creazione, è possibile avvalersene per i processi di generazione dei server,

tranne nel caso in cui il processo di generazione sia basato su una connessione di rete. In tal caso, è senz'altro consigliabile eseguire una generazione manuale, almeno per la CA principale. Gran parte della protezione di una CA non in linea dipende dal fatto che non è e non è mai stata connessa a una rete. Ciò riduce drasticamente le possibilità di attacco esterno, in quanto l'eventuale intruso dovrebbe accedere fisicamente al server.

**Per installare Windows Server 2003**

1.  Avviare il sistema inserendo il CD di Windows Server 2003 Standard Edition nell'unità CD-ROM. Assicurarsi che l'unità CD-ROM sia stata impostata come unità avviabile nelle impostazioni BIOS del server.

2.  Creare una partizione nel volume primario, formattarla come NTFS e selezionare l'opzione per installare Windows in tale partizione.

3.  Selezionare le impostazioni internazionali appropriate.

4.  Digitare il nome e le informazioni relative all'azienda per la quale verrà registrato Windows.

5.  Digitare una password sicura per l'account dell'amministratore locale (almeno 10 caratteri misti: maiuscole, minuscole, lettere, numeri e punteggiatura).

6.  Digitare il nome del computer quando richiesto, per esempio ***HQ-CA-01**** *(sostituire questo valore con il nome che si è scelto).

    **Importante:** anche se la CA principale non è in linea, è necessario assegnarle un nome univoco rispetto ai nomi già attribuiti nell'organizzazione.

7.  Quando viene richiesto, aggiungere il computer a un gruppo di lavoro. Digitare il nome del gruppo di lavoro, per esempio ***WGB-Root*** (sostituire questo valore con il nome che si è scelto).

8.  Non installare alcun componente facoltativo quando viene richiesto.

    Al termine del processo di installazione principale il server verrà riavviato. Continuare con i passaggi seguenti.

9.  Installare i Service Pack di Windows correnti (al momento della stesura di questo documento, Windows Server 2003 era stato appena rilasciato, quindi non era disponibile alcun Service Pack) e tutti gli aggiornamenti per la protezione consigliati (utilizzare uno strumento quale Microsoft Baseline Security Analyzer per individuare gli aggiornamenti consigliati). È necessario, inoltre, installare qualsiasi altro aggiornamento rilevante dal punto di vista funzionale (non relativo alla protezione) o gli aggiornamenti rilevati come necessari in base ai controlli eseguiti.

10. Attivare questa copia di Windows. L'attivazione deve essere eseguita in modalità non in linea, in modo da evitare qualsiasi connessione di rete da parte del server.

##### Impostazioni di rete

La CA principale non è connessa alla rete. Per evitare che la CA principale sia accessibile attraverso la rete in caso di erronea connessione, occorre disattivare qualsiasi interfaccia di rete del sistema selezionando **Connessioni di rete** dal Pannello di controllo.

##### Verifica dell'installazione

È necessario verificare che l'installazione del sistema operativo sia stata completata correttamente e che i parametri configurati corrispondano ai risultati previsti.

**Per visualizzare la configurazione corrente del sistema**

1.  Al prompt dei comandi, eseguire il programma systeminfo.

2.  Verificare i seguenti elementi dell'output di systeminfo; alcuni dettagli dell'output sono stati omessi per maggiore concisione, inserendo al loro posto "... " (puntini sospensivi):

    Nome host:    HQ-CA-01

    Nome SO:    Microsoft® Windows® Server 2003, Standard Edition

    ...

    Configurazione SO:    server autonomo

    Proprietario registrato:    *il\_proprio\_nome*

    Organizzazione registrata:    *la\_propria\_organizzazione*

    ...

    Directory Windows:    C:\\WINDOWS

    Directory di sistema:    C:\\WINDOWS\\System32

    Unità di avvio:    \\Device\\HarddiskVolume1

    Impostazioni internazionali sistema:    *le\_proprie\_impostazioni*

    Impostazione internazionale di input:    *la\_propria\_impostazione*

    Fuso orario:    *il\_proprio\_fuso\_orario*

    ...

    Dominio:    WGB-Root

    Server di accesso:    \\\\HQ-CA-01

    Aggiornamenti rapidi:    X Aggiornamenti rapidi installati.

                                   \[01\]: Qxxxxxx

    ...

                                   \[nn\]: Qnnnnnn

    Schede di rete:    N/D

3.  Se queste impostazioni non corrispondono a quelle previste, è necessario riconfigurare il server attraverso il Pannello di controllo oppure riavviare l'installazione.

#### Preparazione del server della CA di emissione

In questa sezione viene descritta l'installazione di Windows nel server che verrà utilizzato per la CA di emissione.

##### Installazione di Windows Server 2003 Enterprise Edition

Attenersi alle procedure per la creazione del server della CA principale, tenendo conto delle eccezioni elencate di seguito.

A differenza del processo seguito per la CA principale, per creare il server della CA di emissione, è possibile, all'occorrenza, avvalersi di un metodo di generazione basato sulla rete. Occorre, tuttavia, adottare opportune misure precauzionali per assicurarsi che la protezione della CA non sia esposta a eventuali minacce. Per esempio, si dovrebbe eseguire l'installazione su una rete isolata con un percorso non instradabile verso Internet o verso la rete principale della propria organizzazione. È necessario ricordare che, se non si è ancora provveduto a installare gli aggiornamenti di protezione più recenti, il sistema potrebbe essere vulnerabile ai rischi a cui è normalmente esposta una rete senza sufficiente protezione.

**Per installare Windows Server 2003 Enterprise Edition**

1.  Per installare il sistema operativo Windows sul server della CA principale, seguire le procedure 1-5, utilizzando tuttavia la Enterprise Edition di Windows Server 2003 invece della Standard Edition.

2.  Digitare il nome del computer quando richiesto, per esempio ***HQ-CA-02**** *(sostituire questo valore con il nome che si è scelto).

3.  Quando richiesto, scegliere l’opzione di unirsi a un dominio. Immettere il nome del dominio Active Directory a cui verranno aggiunti i server, per esempio *WOODGROVEBANK* (sostituire questo valore con il nome del dominio in cui si installa la CA). Quando richiesto, immettere le credenziali di un utente autorizzato ad aggiungere computer a questo dominio.

    **Nota:** in presenza di un insieme di strutture con più domini, i server dei certificati vengono installati di solito nel dominio principale della struttura; sebbene non sia essenziale, questa soluzione si basa su tale configurazione.

4.  Non installare componenti facoltativi.

    Al termine del processo di installazione principale il server verrà riavviato. Continuare con i passaggi seguenti.

5.  Installare i Service Pack correnti e gli aggiornamenti rapidi richiesti, come per la CA principale.

6.  Creare una partizione sul secondo volume del disco rigido, assegnare all'unità di questa partizione la lettera D e formattarla con NTFS.

7.  Creare una cartella sull'unità D denominata D:\\CertLog.

8.  Attivare questa copia di Windows. È necessario eseguire questa operazione in modalità non in linea, per non esporre il server in alcun modo a Internet.

##### Impostazioni di rete

La CA di emissione dispone di una singola interfaccia di rete, sebbene sia possibile accoppiare due schede di interfaccia di rete fisiche per una maggiore capacità di recupero. L'interfaccia di rete deve essere configurata con un indirizzo IP (Internet Protocol) fisso e altri parametri di configurazione IP (gateway predefinito, impostazioni DNS e così via) adeguati alla propria rete.

Per motivi di sicurezza, è necessario inoltre bloccare qualsiasi connettività in ingresso o in uscita tra la CA di emissione e Internet. Persino permettendo l'accesso solo in uscita, si è esposti all'attacco da parte di virus o altri software dannosi. Per esempio, potrebbero essere scaricati codici aggiuntivi da Internet o sottratti e trasportati all'esterno dell'organizzazione materiali riservati importanti relativi alla CA.

##### Verifica dell'installazione

È necessario verificare che l'installazione del sistema operativo sia stata completata correttamente e che i parametri configurati corrispondano ai risultati previsti.

**Per visualizzare la configurazione corrente del sistema**

1.  Al prompt dei comandi, eseguire il programma systeminfo.

2.  Verificare i seguenti elementi dell'output di systeminfo (alcuni dettagli dell'output sono stati omessi per maggiore concisione):

    Nome host:    HQ-CA-02

    Nome SO:    Microsoft® Windows® Server 2003, Enterprise Edition

    ...

    Configurazione SO:    server membro

    Proprietario registrato:    *il\_proprio\_nome*

    Organizzazione registrata:    *la\_propria\_organizzazione*

    ...

    Directory Windows:    C:\\WINDOWS

    Directory di sistema:    C:\\WINDOWS\\System32

    Unità di avvio:    \\Device\\HarddiskVolume1

    Impostazioni internazionali sistema:    le\_proprie\_impostazioni

    Impostazione internazionale di input:    la\_propria\_impostazione

    Fuso orario:    il\_proprio\_fuso\_orario

    ...

    Dominio:    woodgrovebank.com

    Server di accesso:    \\\\Nome\_del\_controller\_di\_dominio

    Aggiornamenti rapidi:    X Aggiornamenti rapidi installati.

                                   \[01\]: Qxxxxxx

    ...

                                   \[nn\]: Qnnnnnn

    Schede di rete:    NIC installate.

    \[01\]:    Modello\_e\_fornitore\_della\_scheda\_di\_rete

        Nome connessione: Connessione alla rete locale

        DHCP abilitato:    No

        Indirizzi IP

        \[01\]: 10.1.1.11

3.  Se queste impostazioni non corrispondono a quelle previste, è necessario riconfigurare il server attraverso il Pannello di controllo oppure eseguire nuovamente l'installazione.

#### Installazione degli script di configurazione nei server

Assieme a questa soluzione vengono forniti script di supporto e file di configurazione per semplificare alcuni aspetti della configurazione e del funzionamento di questa soluzione. È necessario installarli in ciascun server CA. Alcuni di questi script serviranno per eseguire le operazioni descritte nei capitoli della Guida operativa, pertanto non devono essere eliminati al termine dell'installazione della CA.

**Per installare gli script di installazione in ciascun server**

1.  Creare una cartella denominata C:\\MSSScripts.

2.  In questa cartella, copiare gli script dal supporto di distribuzione.

#### Installazione e configurazione di Internet Information Services

Questa sezione illustra le procedure di installazione e configurazione di Internet Information Services (IIS) nella CA di emissione. IIS serve per fornire il certificato della CA e i punti di download dei CRL per i client non basati su Windows. Si consiglia di non installare IIS nella CA principale. Sebbene sia possibile installare IIS nella CA di emissione, per motivi di sicurezza è preferibile che i punti di download Web per il certificato CA e i CRL risiedano in un server diverso dalla CA stessa. Potrebbero esserci numerosi utenti dei certificati (interni ed esterni) che hanno bisogno di recuperare i CRL o i certificati CA a catena, ma ai quali non deve essere necessariamente consentito l'accesso alla CA. Se, tuttavia, i punti di download sono ospitati dalla stessa CA, non è possibile applicare questa restrizione.

**Importante**: per semplificare la soluzione fornita, il server della CA di emissione viene utilizzato per ospitare il server Web, il certificato CA e i punti di download dei CRL. Tuttavia, per migliorare la protezione delle CA, è consigliabile utilizzare un server Web distinto nell'ambiente in cui si opera. Le procedure qui descritte servono per l'installazione e la configurazione di IIS nella CA di emissione o in un server distinto.

IIS può ospitare inoltre le pagine per la registrazione Web dei Servizi certificati, anche se in questa soluzione non ne è richiesto il ricorso. Se si installano le pagine per la registrazione Web in un server diverso da quello della CA, è necessario contrassegnarlo come attendibile per la delega impostando questa proprietà nell'oggetto computer del server di Active Directory.

##### Installazione di Internet Information Services nella CA di emissione

IIS viene installato con Gestione componenti facoltativi di Windows (accessibile dal Pannello di controllo, **Installazione componenti di Windows**). Nella tabella che segue sono elencati i componenti da installare. I rientri dei paragrafi riflettono la relazione tra i componenti così come sono visualizzati nella Gestione guidata dei componenti facoltativi (ad esempio, **Enable network COM+ access** è un sottocomponente di **Server applicazioni**). I componenti che non vengono selezionati non sono inclusi nella tabella.

**Tabella 7.5. Componenti facoltativi da installare**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Componente</th>
<th style="border:1px solid black;" >Stato di installazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Server applicazioni</td>
<td style="border:1px solid black;">Selezionata</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">      Enable network COM+ access</td>
<td style="border:1px solid black;">Selezionata</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">      Internet Information Services (IIS)</td>
<td style="border:1px solid black;">Selezionata</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">            File comuni</td>
<td style="border:1px solid black;">Selezionata</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">            Gestione di Internet Information Services</td>
<td style="border:1px solid black;">Selezionata</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">            Servizio Web</td>
<td style="border:1px solid black;">Selezionata</td>
</tr>
</tbody>
</table>
  
**Per installare IIS**
  
1.  Al prompt dei comandi, eseguire:
  
    sysocmgr /i:sysoc.inf /u:C:\\MSSScripts\\OC\_AddIIS.txt
  
    Tramite questo comando, Gestione componenti facoltativi utilizza le configurazioni dei componenti specificate nel file di installazione automatica C:\\MSSScripts\\OC\_AddIIS.txt:
  
    <codesnippet language displaylanguage containsmarkup="false">\[Components\] complusnetwork = On iis\_common = On iis\_asp = On iis\_inetmgr = On iis\_www = On  
```
  
    **Nota:** in questa configurazione vengono attivate le pagine ASP (con la riga iis\_asp = on). Tale opzione serve a supportare le pagine di registrazione Web di Servizi certificati, ma non serve per la soluzione principale. Se le pagine di registrazione Web non sono richieste, è necessario disattivare ASP (eliminando la riga iis\_asp = on prima di eseguire sysocmgr.exe). All'occorrenza, è possibile attivare questa impostazione in un secondo momento.
  
2.  Eseguire nuovamente Gestione componenti facoltativi e verificare che i componenti installati corrispondano a quelli elencati nella tabella precedente.
  
    sysocmgr /i:sysoc.inf
  
    Non sono richiesti altri sottocomponenti di **Server applicazioni**, quindi non è necessario eseguire altre selezioni.
  
##### Configurazione di IIS per la pubblicazione di AIA (Authority Information Access) e del CDP (CRL Distribution Point) nella CA di emissione
  
È necessario creare una directory virtuale su IIS da utilizzare come percorso del protocollo HTTP (Hypertext Transfer Protocol) per la pubblicazione del certificato della CA (AIA) e dei punti di pubblicazione CRL (CDP).
  
**Per creare una directory virtuale su IIS**
  
1.  Accedere al server IIS (CA di emissione) con i privilegi di Amministratore locale.
  
2.  Creare la cartella C:\\CAWWWPub che conterrà i certificati della CA e i CRL.
  
3.  Mediante Windows Explorer, impostare la protezione nella cartella; la seguente tabella mostra quali sono le autorizzazioni corrispondenti. Le prime quattro dovrebbero essere già presenti.
  
    **Tabella 7.6. Autorizzazioni directory virtuale**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Utente/Gruppo</th>
    <th style="border:1px solid black;" >Autorizzazione</th>
    <th style="border:1px solid black;" >Consenti/Nega</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Amministratori</td>
    <td style="border:1px solid black;">Controllo completo</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">System</td>
    <td style="border:1px solid black;">Controllo completo</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Creator Owners</td>
    <td style="border:1px solid black;">Controllo completo (solo sottocartelle e file)</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Users</td>
    <td style="border:1px solid black;">Lettura
    Visualizzazione contenuto cartella</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">IIS_WPG</td>
    <td style="border:1px solid black;">Lettura
    Visualizzazione contenuto cartella</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Account Internet Guest</td>
    <td style="border:1px solid black;">Scrittura</td>
    <td style="border:1px solid black;">Nega</td>
    </tr>
    </tbody>
    </table>
  
4.  Nella console di gestione di Internet Information Services, creare una nuova directory virtuale nel sito Web predefinito:
  
    -   Assegnare alla directory virtuale il nome *pki*
  
    -   Specificare *C:\\CAWWWPub* come percorso.
  
5.  Eliminare l'opzione **Esecuzione script (ad esempio, ASP)** nelle autorizzazioni di accesso alla directory virtuale.
  
6.  Assicurarsi che l'autenticazione anonima per la directory virtuale sia attivata.
  
##### Selezione di un alias DNS per il punto di pubblicazione HTTP
  
È necessario creare un alias DNS generico (CNAME) che risolve il nome del server IIS in cui risiedono il CDP e AIA, ad esempio, www.woodgrovebank.com. L'alias DNS deve essere utilizzato quando si configurano i percorsi di CDP e AIA per le CA, come descritto nelle sezioni successive. Usando l'alias, è possibile spostare facilmente, in un successivo momento, i punti di pubblicazione della CA in un altro server o posizione della rete, senza dover nuovamente emettere i certificati della CA.
  
##### Verifica dell'installazione di IIS
  
Prima di procedere, è necessario verificare il funzionamento di base di IIS. Se uno dei test descritti di seguito non viene superato, è necessario ricontrollare i passaggi dell'installazione e della configurazione di IIS descritti precedentemente in questa sezione.
  
**Per verificare il corretto funzionamento della directory virtuale IIS**
  
1.  Accedere al server IIS (CA di emissione) come membro del gruppo Amministratori locale e creare un file utilizzando un editor di testo, ad esempio Notepad. Immettere del testo riconoscibile (non è importante il contenuto e non sono richiesti tag HTML). Ad esempio:
  
    Hello world
  
2.  Salvare il file come **test.htm** nella cartella creata per la pubblicazione delle informazioni CDP e AIA utilizzando la procedura sopra descritta - C:\\CAWWWPub. Salvare lo stesso file come **test.asp** nella medesima cartella.
  
3.  Aprire un browser e digitare l'URL (Uniform Resource Locator) per tentare di recuperare le pagine:
  
    http://*www.woodgrovebank.com*/pki/test.htm
  
    **Nota:** se non è ancora stato impostato l'alias nel DNS, è possibile immetterlo temporaneamente nel file host locale (%systemroot%\\system32\\drivers\\etc\\hosts) in base all'indirizzo IP del server IIS. In alternativa, è possibile utilizzare il nome host effettivo del server IIS al posto dell'alias. Tuttavia, in seguito sarà necessario controllare il corretto funzionamento dell'alias DNS.
  
4.  Nel browser, dovrebbe venire visualizzato il testo "Hello world" (o il testo digitato in base alla procedura 1).
  
**Per verificare che l'autorizzazione Esecuzione è stata disattivata**
  
1.  Aprire un browser e digitare il seguente URL per tentare di recuperare le pagine:
  
    http://*www.woodgrovebank.com*/pki/test.asp
  
2.  Nel browser, dovrebbe venire visualizzato il seguente messaggio di errore (o un messaggio analogo):
  
    **Impossibile visualizzare la pagina**
  
    Tentativo di eseguire un'applicazione CGI, ISAPI o altri programmi eseguibili da una directory che non consente l'esecuzione di programmi.
  
    Dovrebbe essere inoltre visualizzato il seguente codice di errore:
  
    Errore HTTP 403.1 - Accesso negato: Accesso in esecuzione negato.
  
    Internet Information Services (IIS)
  
Occorre assicurarsi che sia stato attivato l'accesso anonimo al sito. Microsoft Internet Explorer tenterà automaticamente e in modo invisibile di autenticare un utente per un sito Web; pertanto, a volte risulta difficile determinare se sia stato utilizzato l'accesso anonimo al posto dell'accesso autenticato. Un modo per stabilirlo consiste nel modificare le impostazioni di protezione dell'area di Internet Explorer per imporre l'uso dell'accesso anonimo e ripetere i test precedenti. In alternativa, attenersi alla procedura seguente che utilizza telnet.exe per forzare l'accesso non autenticato. Tale procedura presuppone che si esegua il test del sito Web dal server IIS stesso; non funzionerà se, al contrario, si utilizza un server proxy.
  
**Per verificare se l'accesso anonimo è stato attivato**
  
1.  Eseguire il programma telnet dal prompt dei comandi.
  
2.  Quando viene visualizzato il messaggio telnet, digitare il comando seguente per attivare la visualizzazione locale dei caratteri digitati:
  
    set localecho
  
3.  Digitare il comando per connettersi a IIS utilizzando l'alias DNS definito in precedenza:
  
    open *www.woodgrovebank.com* 80
  
4.  Digitare il testo seguente esattamente come è riportato, rispettando le minuscole e le maiuscole, per recuperare la pagina test.htm:
  
    GET /pki/test.htm
  
    **Nota:** il cursore tornerà a posizionarsi nella parte superiore dello schermo, ciò significa che il testo che viene digitato andrà a sovrascrivere il testo esistente, dando luogo a una visualizzazione leggermente distorta. È possibile ignorare l'avviso.  
    In caso di errore durante la digitazione, premere INVIO e digitare nuovamente il comando **open** (passaggio 3) per riconnettersi e inviare il comando **GET** una seconda volta.
  
5.  Viene visualizzato l'output seguente:
  
    Hello world
  
    Connection to host lost.
  
    Press any key to continue...
  
6.  Digitare **quit** per uscire da telnet.
  
Se tutti e tre i test illustrati nella sezione sono stati superati, eliminare i file test.htm e test.asp dalla cartella del server Web.
  
#### Installazione e configurazione di componenti aggiuntivi del sistema operativo
  
Questa sezione illustra le procedure di installazione e configurazione di altri componenti richiesti nei server. È necessario seguire questa procedura per i server della CA principale e della CA di emissione.
  
##### Rimozione del servizio Aggiorna certificati di origine
  
È necessario rimuovere il servizio Aggiorna certificati di origine. Questo è un componente facoltativo che viene installato per impostazione predefinita. Non è consigliabile che la trust della directory principale delle CA venga aggiornata automaticamente. In ogni caso, il servizio non funzionerà se non potrà accedere a Internet, dando luogo alla registrazione di errori nel Registro eventi. È chiaro che la CA non in linea non avrà accesso a Internet, ma è necessario bloccare anche qualsiasi connessione in ingresso e in uscita tra la CA di emissione e Internet, come illustrato in precedenza.
  
**Per rimuovere il servizio Aggiorna certificati di origine**
  
-   Al prompt dei comandi, eseguire:
  
    sysocmgr /i:sysoc.inf /u:C:\\MSSScripts\\OC\_RemoveRootUpdate.txt
  
Tramite questo comando, Gestione componenti facoltativi utilizza le configurazioni dei componenti specificate nel file C:\\MSSScripts\\OC\_ RemoveRootUpdate.txt
  
<codesnippet language displaylanguage containsmarkup="false">\[Components\] rootautoupdate = Off  
```  
#### Controllo dei Service Pack e degli aggiornamenti di protezione
  
A questo punto, è necessario controllare nuovamente i Service Pack e l'elenco degli aggiornamenti installati, in quanto potrebbero essere stati installati componenti aggiuntivi, quali IIS. Utilizzare uno strumento come Microsoft Baseline Security Analyzer (MBSA) per eseguire il controllo, ottenere gli aggiornamenti necessari e, dopo un'adeguata verifica, installarli nei server.
  
Per istruzioni sull'uso di MBSA, vedere il collegamento indicato nella sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
**Nota:** per poter eseguire MBSA in modalità non in linea, è necessario scaricare separatamente l'elenco corrente degli aggiornamenti della protezione forniti da Microsoft, mssecure.xml. La descrizione è disponibile nella documentazione MBSA, consultabile attraverso il collegamento MBSA.
  
#### Installazione di software aggiuntivo
  
In questa sezione viene descritta l'installazione di applicazioni software aggiuntive necessarie per le CA.
  
##### CAPICOM
  
Per alcuni script di configurazione e di gestione forniti assieme alla soluzione, è necessario disporre di CAPICOM 2.0 (la versione attuale è 2.0.0.3) nella CA principale e nella CA di emissione. Le informazioni su dove trovare la versione più recente di CAPICOM si trovano nella sezione "Ulteriori informazioni" al termine di questo capitolo.
  
Seguire le istruzioni del file eseguibile autoestraente per installare e registrare la DLL (Dynamic-Link Library) di CAPICOM.
  
##### Strumenti di supporto di Windows Server 2003
  
Sebbene non sia essenziale, è utile installare gli strumenti di supporto di Windows 2000 nel server della CA di emissione. Alcuni di questi strumenti sono utili per determinate operazioni della CA, mentre altri possono agevolare la risoluzione dei problemi. È possibile installare gli strumenti di supporto dal CD di installazione di Windows (Suptools.msi in Support\\Tools).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Preparazione di Active Directory per l'infrastruttura PKI
  
Questa sezione illustra come preparare Active Directory per l'installazione di Servizi certificati Windows Server 2003.
  
#### Preparazione dello schema Active Directory
  
Per questa soluzione, sono previsti alcuni requisiti minimi nell'infrastruttura del dominio di Active Directory. Tali requisiti variano a seconda se la soluzione viene installata in un ambiente Active Directory di Windows 2000 o in un ambiente che sia stato aggiornato a (o installato inizialmente come) Active Directory di Windows Server 2003.
  
##### Requisiti per tutte le versioni di Active Directory
  
La soluzione richiede un livello funzionale minimo di dominio nella modalità nativa di Windows 2000, almeno per il dominio in cui sono installati i server dell'autorità di certificazione. Tale requisito è necessario perché la soluzione si avvale dei gruppi universali Active Directory, disponibili appunto nella modalità nativa di Windows 2000. Se il dominio non soddisfa questo requisito, occorre apportarvi modifiche in base alle istruzioni contenute nella documentazione del prodotto (vedere la sezione "Ulteriori informazioni" alla fine di questo capitolo).
  
**Nota:** il livello funzionale di dominio predefinito di Active Directory corrisponde sempre alla modalità mista, anche nel caso in cui l'installazione sia stata eseguita utilizzando solo i controller di dominio Active Directory di Windows 2003. È necessario aumentare il livello prima di continuare. Se non è possibile aumentare il livello di dominio dalla modalità mista perché non sono supportati i controller di dominio della versione 4.0 di Microsoft Windows NT®, sarà necessario creare manualmente gruppi globali di dominio in sostituzione dei gruppi universali.
  
La soluzione presuppone un insieme di strutture di Active Directory con il livello di funzionalità dell'insieme di strutture predefinito di Windows 2000 (o superiore). Non è necessario modificare tale impostazione. Per ulteriori informazioni su tali argomenti, vedere il riferimento alla fine del presente capitolo.
  
##### Installazione in un dominio di Windows 2000
  
**Importante:** sebbene Microsoft supporti l'installazione e l'uso di Servizi certificati Windows Server 2003 in un dominio in cui sono utilizzati controller di dominio Windows, la soluzione non è stata sufficiente testata in questa combinazione.
  
Se la soluzione è stata installata in un insieme di strutture Active Directory di Windows 2000, al fine di garantirne il funzionamento è necessario aggiornare lo schema della directory per l'installazione di Servizi certificati di Windows 2003. È inoltre necessario accertarsi che tutti i controller di dominio Windows 2000 dispongano di Service Pack 3 (o versione successiva). Il service pack è necessario per il corretto funzionamento dello strumento di aggiornamento dello schema e per consentire ai controller di dominio di supportare la firma LDAP (Lightweight Directory Access Protocol). La firma LDAP è un ulteriore perfezionamento della protezione richiesta dalle CA di Windows Server 2003 e dai client Windows XP che utilizzano la registrazione automatica dei certificati.
  
Numerose funzioni di Servizi certificati di Windows 2003 (quali la registrazione automatica dell'utente e i modelli modificabili) richiedono una versione Windows Server 2003 dello schema Active Directory. Tuttavia, tale requisito non implica che alcuni o tutti i controller di dominio debbano eseguire Windows Server 2003, ma che Servizi certificati di Windows Server 2003 richieda estensioni di schema particolari che non sono presenti nello schema Active Directory di Windows 2000. È possibile aggiornare lo schema della directory tramite lo strumento ADPrep.exe (incluso nella cartella i386 del supporto di distribuzione di Windows Server 2003).
  
Per utilizzare Adprep, è necessario applicare il Service Pack 3 ai controller di dominio di Windows 2000 (Adprep funzionerà con il Service Pack 1, più alcuni aggiornamenti successivi, ma poiché il SP3 è richiesto comunque, questa informazione non è rilevante). Non tentare di utilizzare questo strumento senza verificare prima che tutti i controller di dominio si trovino al livello patch corretto.
  
**Attenzione:** usando tale strumento, si modifica in modo irreversibile lo schema della directory. Sebbene tale procedura sia sicura, tuttavia, prima di iniziare, si consiglia di leggere attentamente la documentazione correlata.
  
Nel controller di dominio principale dello schema dell'insieme di strutture, è necessario eseguire il comando seguente:
  
ADPrep /ForestPrep
  
Per eseguire questa operazione, è necessario essere un membro del gruppo Amministratori schema oppure richiedere di eseguirla a un amministratore in possesso delle autorizzazioni appropriate.
  
Per ulteriori informazioni sullo strumento ADPrep, consultare la relativa sezione alla fine di questo capitolo.
  
##### Verifica della disponibilità di Active Directory
  
Per verificare il livello funzionale del dominio e la versione dello schema, attenersi alla seguente procedura.
  
**Per verificare il livello funzionale del dominio**
  
1.  Aprire Utenti e computer di Active Directory.
  
2.  Visualizzare le proprietà dell'oggetto Dominio.
  
3.  Nella scheda **Generale**, viene visualizzato uno dei seguenti **livelli funzionali del dominio**:
  
    -   Windows 2000 nativo
  
    -   Windows Server 2003
  
**Per verificare la versione dello schema corretta**
  
1.  Da un prompt dei comandi, digitare il seguente comando (assicurarsi di sostituire il DN del dominio principale dell'insieme di strutture):
  
    dsquery \* "cn=schema,cn=configuration, *DC=woodgrovebank,DC=com*" -scope base -attr objectversion
  
    (il comando si trova su due righe per esigenze di visualizzazione, ma deve essere digitato su una sola riga).
  
    **Nota:** è necessario eseguire il comando da un server Windows 2003. Dsquery.exe non è disponibile per impostazione predefinita in Windows XP o Windows 2000.
  
2.  Deve essere visualizzata la versione dello schema di 30 (o superiore), come illustrato di seguito:
  
      objectversion
  
      30
  
#### Gruppi e utenti di Active Directory
  
In questa sezione viene illustrata la creazione di gruppi di protezione e di account utenti di Active Directory utilizzati dalle CA.
  
##### Creazione dei gruppi di amministrazione dell'infrastruttura PKI e delle CA
  
I ruoli e le funzionalità amministrative vengono definiti tramite account utenti di dominio e gruppi di protezione.
  
**Nota:** in questa soluzione vengono definiti più gruppi di protezione che corrispondono a ruoli amministrativi distinti. Ciò conferisce un ampio controllo sulle modalità di delega delle responsabilità all'amministrazione delle CA. Tuttavia, *non* è necessario utilizzare tutti o uno qualsiasi di questi ruoli, se essi non corrispondono al modello di amministrazione desiderato. In casi estremi, se esiste un unico amministratore dell'infrastruttura PKI che si occupa di tutti gli aspetti del servizio, è possibile aggiungere questo account a tutti i gruppi di ruoli della CA. Nella pratica, la maggior parte delle organizzazioni adotta di solito una certa separazione dei ruoli, ma solo poche utilizzano tutte le funzionalità di separazione dei ruoli offerte da Servizi certificati.
  
**Per creare gruppi amministrativi della CA nel dominio**
  
1.  Accedere a un computer membro del dominio con un account che dispone di autorizzazioni sufficienti per creare oggetti utente e gruppo nel contenitore Utenti.
  
2.  Per creare i gruppi di gestione CA del dominio, eseguire il comando seguente:
  
    Cscript //job:CertDomainGroups C:\\MSSScripts\\ca\_setup.wsf
  
Questo script crea i gruppi di protezione elencati nella seguente tabella. I gruppi sono creati come gruppi universali nel contenitore Utenti del dominio e devono quindi essere spostati ad una unità organizzativa (UO) più appropriata (in una sezione successiva è illustrata una struttura di UO idonea).
  
**Attenzione:** lo script crea gruppi di protezione a cui verrà assegnato molto potere all'interno dell'insieme di strutture di Active Directory. Nell'attribuzione della qualità di membro di tali gruppi, occorre pertanto prestare molta attenzione. Nello specifico:
  
**Amministratori PKI dell'organizzazione** Si tratta di un gruppo estremamente potente che esercita il completo controllo dell'infrastruttura PKI nell'intero insieme di strutture di Active Directory, oltre ad avere la capacità di installare e sostituire CA principali e dell'organizzazione, modificare trust principali e installare certificati incrociati. Si raccomanda di usare la stessa cautela necessaria per il gruppo Amministratori organizzazione.
  
**Autori PKI dell'organizzazione** Sebbene sembri trattarsi di un gruppo innocuo, anch'esso è dotato di potenti funzionalità, tra cui quella di installazione ed eliminazione di CA principali attendibili e certificati incrociati per l'intero insieme di strutture. Anche se non altrettanto potente quanto il gruppo Amministratori organizzazione, con tale gruppo è comunque necessario mantenere un approccio prudente.
  
**Tabella 7.7. Nomi e scopi dei gruppi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome gruppo</th>
<th style="border:1px solid black;" >Scopo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Amministratori PKI dell'organizzazione</td>
<td style="border:1px solid black;">Amministratori del contenitore della configurazione dei servizi a chiave pubblica.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Autori PKI dell'organizzazione</td>
<td style="border:1px solid black;">Autorizzato a pubblicare CRL e certificati CA nel contenitore della configurazione dell’organizzazione di grandi dimensioni</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Amministratori CA</td>
<td style="border:1px solid black;">Dispone di privilegi amministrativi completi sulla CA, inclusa la determinazione dell'appartenenza di altri ruoli</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Responsabili certificazione</td>
<td style="border:1px solid black;">Gestisce il rilascio e la revoca dei certificati</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controllori CA</td>
<td style="border:1px solid black;">Gestisce i dati di controllo per la CA</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Operatori backup CA</td>
<td style="border:1px solid black;">Dispone delle autorizzazioni a eseguire il backup e il ripristino delle chiavi e dei dati della CA</td>
</tr>
</tbody>
</table>
  
**Note:**  
se si richiedono ruoli Amministratori CA, Responsabili certificazione, Controllori e Operatori backup distinti per ciascuna CA dell'organizzazione, è necessario creare gruppi distinti invece di singoli gruppi a livello di dominio, come illustrato di seguito. Assegnare loro un nome, quale *NomeCA* Amministratori CA o simili.  
La maggior parte di questi gruppi di dominio dispongono di gruppi equivalenti locali creati nelle CA non in linea.  
Anche il gruppo locale Amministratori dei server delle CA riveste un ruolo importante nella gestione di una CA. Questo gruppo esiste nei server Windows per impostazione predefinita.  
In presenza di un insieme di strutture con più domini, è necessario creare tali gruppi nello stesso dominio dei server dei certificati; questo approccio è stato adottato anche in altre sezioni della guida (trattandosi di gruppi universali, è possibile utilizzare tali gruppi per amministrare le CA installate nel dominio di qualsiasi insieme di strutture).
  
##### Creazione degli utenti test di amministrazione dell'infrastruttura PKI e delle CA
  
A scopo di test e dimostrazione, lo script di questa sezione crea account generici che corrispondono a ciascuno dei ruoli definiti dai gruppi di amministrazione creati precedentemente. Tuttavia, se gli account effettivi che verranno utilizzati esistono già in questa fase oppure sono stati già definiti e si è in grado di crearli, ignorare questo passaggio e utilizzare gli account esistenti.
  
**Per creare gli account utenti test di amministrazione della CA**
  
1.  Accedere a un computer membro del dominio con un account che dispone di autorizzazioni sufficienti per creare oggetti utente e gruppo nel contenitore Utenti.
  
2.  Creare account utenti test del dominio per gli individui che amministreranno la CA eseguendo lo script seguente:
  
    Cscript //job:CertDomainTestAccts C:\\MSSScripts\\ca\_setup.wsf
  
    Lo script imposta password casuali su tutti gli account invece di lasciarli con password vuote. Prendere nota delle password dall'output dello script o reimpostare le password assegnate automaticamente con quelle desiderate.
  
    **Attenzione:** l'uso di account generici come questi, con password condivise tra gli amministratori, rende il controllo praticamente impossibile. In ambienti diversi da quello di testing, è necessario utilizzare sempre account individuali.
  
Lo script crea gli account di dominio descritti nella tabella seguente. Lo script crea utenti nel contenitore Utenti che è necessario spostare in un'unità organizzativa più appropriata (in una successiva sezione ne viene fornita un'illustrazione).
  
**Tabella 7.8. Nomi e scopi degli account**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Account utente</th>
<th style="border:1px solid black;" >Scopo dell'account</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">AmminPKIorg</td>
<td style="border:1px solid black;">Amministratore del contenitore della configurazione dei servizi a chiave pubblica</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">AutPKIorg</td>
<td style="border:1px solid black;">Autorizzato a pubblicare CRL e certificati CA nel contenitore della configurazione dell’organizzazione di grandi dimensioni</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">AmminCA</td>
<td style="border:1px solid black;">Dispone di privilegi amministrativi completi sulla CA, inclusa la determinazione dell'appartenenza di altri ruoli</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ResponsCert</td>
<td style="border:1px solid black;">Gestisce il rilascio e la revoca dei certificati</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ControlloreCA</td>
<td style="border:1px solid black;">Gestisce i dati di controllo per la CA</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">BackupCA</td>
<td style="border:1px solid black;">Dispone delle autorizzazioni a eseguire il backup e il ripristino delle chiavi e dei dati della CA</td>
</tr>
</tbody>
</table>
  
**Nota:** gli account test rappresentano la configurazione dei ruoli amministrativi più complessa, nella quale ciascun ruolo della CA corrisponde a un singolo utente (account utente). Tuttavia, disporre di account separati per ogni ruolo non è di solito particolarmente vantaggioso, a meno che ciascun ruolo non sia effettivamente svolto da persone diverse. I singoli account possono essere membri di più gruppi di ruoli, o persino di tutti, se ciò riflette in modo più preciso la struttura amministrativa. Vedere la sezione successiva, "Creazione di un modello di amministrazione semplificato per le CA dell'organizzazione."
  
##### Popolamento dei gruppi di amministrazione della CA
  
È necessario popolare i gruppi di amministrazione della CA con gli account del personale amministrativo appropriato dell'organizzazione. Per una descrizione completa del mapping di questi gruppi ai ruoli amministrativi dell'infrastruttura di Servizi certificati, vedere la sezione "Ruoli di gestione" nel capitolo 4, "Progettazione dell’infrastruttura a chiave pubblica (PKI)." Per una descrizione completa dei ruoli amministrativi di Servizi certificati di Windows Server 2003, vedere l'argomento "Amministrazione basata sui ruoli" della guida in linea oppure il riferimento alla fine del presente capitolo.
  
**Nota:** se sono stati creati account di dominio test, è necessario comunque aggiungerli manualmente come membri dei rispettivi gruppi di protezione. Per motivi precauzionali, ai fini della sicurezza, lo script non esegue questa procedura per impostazione predefinita.
  
La procedura di configurazione descritta nella parte restante di questo documento richiede che alcune delle azioni vengano eseguite utilizzando account membri dei gruppi Amministratori PKI dell'organizzazione, Autori PKI dell'organizzazione e Amministratori CA. In questo modo si evita di utilizzare i privilegi dei gruppi Amministratori organizzazione o Amministratori di dominio se non quando è assolutamente indispensabile.
  
**Nota:** è possibile applicare una separazione rigorosa dei ruoli in Servizi certificati di Windows Server 2003 (solo per l'Enterprise Edition). Ciò significa che qualsiasi account a cui vengano assegnati più ruoli (direttamente o tramite l'appartenenza a un gruppo) viene escluso da tutti i ruoli amministrativi nella CA. Per impostazione predefinita, tale opzione non è attivata nel prodotto né in questa soluzione, pertanto è ammessa l'assegnazione allo stesso account utente di più ruoli amministrativi, se ciò è opportuno per l'organizzazione.
  
##### Creazione di un modello di amministrazione semplificato per le CA dell'organizzazione
  
Gli account test e i gruppi amministrativi rappresentano la configurazione dei ruoli amministrativi più complessa, nella quale ciascun ruolo della CA corrisponde a un singolo utente (account utente). È legittimo, tuttavia, disporre di singoli account in più gruppi di ruolo, o anche in tutti i gruppi di ruolo, se ciò riflette in modo più accurato la struttura amministrativa.
  
Molte organizzazioni useranno solo tre ruoli: Amministratore CA, Controllore e Operatore backup. Questa configurazione viene riportata nella tabella seguente utilizzando un sottoinsieme degli account test creati precedentemente a scopo illustrativo.
  
**Tabella 7.9. Assegnazione dei gruppi del modello amministrativo semplificato**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Account utente con ruolo amministrativo semplificato</th>
<th style="border:1px solid black;" >Appartenenza di gruppo dell'account utente</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">AmminCA</td>
<td style="border:1px solid black;">Amministratori PKI dell'organizzazione
Amministratori CA
Responsabili certificazione
Amministratori (amministratori locali della CA)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ControlloreCA</td>
<td style="border:1px solid black;">Controllori CA
Amministratori (amministratori locali della CA)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">BackupCA</td>
<td style="border:1px solid black;">Operatori backup CA</td>
</tr>
</tbody>
</table>
  
Utilizzando questa configurazione, l'account Amministratore CA sarebbe in grado di eseguire tutte le attività amministrative nelle CA dell'organizzazione (incluse l'approvazione e la revoca dei certificati) e avrebbe il controllo amministrativo di tutte le informazioni di configurazione dell'infrastruttura PKI dell'organizzazione in Active Directory (l'impostazione delle relative autorizzazioni viene illustrata in questo documento più avanti).
  
##### Struttura di unità organizzative del dominio consigliata per la gestione delle CA e dei modelli di certificato
  
Esistono diversi gruppi e account utenti associati alla gestione e al funzionamento di un'infrastruttura PKI. Per consentire una più facile gestione dei gruppi e degli utenti, è preferibile riunirli in unità organizzative (UO). La tabella seguente illustra la struttura consigliata di una UO e ne descrive lo scopo (le voci con rientro sono le UO figlio delle UO di Servizi certificati).
  
È necessario assegnare le autorizzazioni del gruppo Amministratori PKI dell'organizzazione per creare ed eliminare gruppi e utenti nell'unità organizzativa di Servizi certificati e in tutti i contenitori figli.
  
**Tabella 7.10. Struttura di un'unità organizzativa di esempio**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Unità operativa</th>
<th style="border:1px solid black;" >Scopo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Servizi certificati</td>
<td style="border:1px solid black;">Unità organizzativa padre.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">\—Amministrazione Servizi certificati</td>
<td style="border:1px solid black;">Contiene gruppi amministrativi per la gestione della configurazione della CA e dell’infrastruttura PKI di un'organizzazione di grandi dimensioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">\—Gestione modelli certificati</td>
<td style="border:1px solid black;">Contiene i gruppi per la gestione di singoli modelli di certificato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">\—Registrazione modello di certificato</td>
<td style="border:1px solid black;">Contiene i gruppi ai quali è stata concessa l’autorizzazione di Registrazione o Registrazione automatica sui modelli con lo stesso nome. Il controllo di questi gruppi può essere delegato quindi al personale addetto per consentire un regime di registrazione flessibile senza modificare i modelli stessi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">\—Utenti test di Servizi certificati</td>
<td style="border:1px solid black;">Contiene account test temporanei.</td>
</tr>
</tbody>
</table>
  
Per ulteriori informazioni sull'uso di queste UO e dei gruppi in esse contenuti, vedere le rispettive sezioni del capitolo 11, "Gestione dell'infrastruttura a chiave pubblica".
  
**Per creare la gerarchia amministrativa delle unità organizzative di Servizi certificati**
  
1.  Accedere utilizzando un account che disponga delle autorizzazioni per creare UO e delegare le autorizzazioni all'interno di queste stesse UO. Come creatori di nuove UO, sarà sempre possibile assegnare a se stessi l'autorizzazione a delegare il controllo di tali UO.
  
2.  Creare la struttura delle UO illustrata nella tabella precedente in un percorso appropriato del dominio (si presume che si tratti del dominio principale dell'insieme di strutture, ma ciò non è essenziale).
  
3.  Assegnare le autorizzazioni al gruppo Amministratori PKI dell'organizzazione per creare ed eliminare gruppi nell'unità organizzativa di Servizi certificati e in tutti i contenitori figli.
  
    **Nota:** questa struttura di UO viene fornita solo a scopo illustrativo. Non è obbligatorio adottarla.
  
#### Protezione di Servizi chiave pubblica di Active Directory
  
In questa sezione viene descritto come delegare il controllo al contenitore Servizi chiave pubblica per i gruppi di protezione dell'amministrazione della PKI.
  
##### Concessione delle autorizzazioni al contenitore Servizi chiave pubblica
  
Le informazioni relative alla configurazione PKI a livello di insieme di strutture vengono memorizzate nel contenitore Configurazione di Active Directory. Le autorizzazioni per la modifica di questo contenitore, dei relativi sottocontenitori e degli oggetti sono limitate per impostazione predefinita al gruppo di protezione degli Amministratori organizzazione.
  
È necessario modificare la protezione sul contenitore Servizi chiave pubblica per i seguenti motivi:
  
-   Per consentire al gruppo Amministratori PKI dell'organizzazione di installare le CA dell'organizzazione e configurare i modelli di certificato senza dover essere membri del gruppo di protezione Amministratori organizzazione.
  
-   Per consentire al gruppo Autori PKI dell'organizzazione di pubblicare elenchi di revoca certificati e certificati CA senza dover essere membri del gruppo di protezione Amministratori organizzazione.
  
Sarà necessario richiedere a un membro del gruppo Amministratori organizzazione di Active Directory di eseguire la prima procedura, a meno che non l'utente non ne sia membro.
  
**Attenzione:** con tale procedura, si delega una parte di Active Directory contenente dati sensibili relativi sia agli utenti che ai computer compresi nell'insieme delle strutture. Occorre, pertanto, prestare molta attenzione agli utenti ai quali si garantisce il controllo sul contenitore Servizi chiave pubblica. Gli account che sono autorizzati a controllare tale contenitore possono, tra l'altro, aggiungere e rimuovere CA principali attendibili, aggiungere e rimuovere CA dell'organizzazione e creare credenziali valide per qualsiasi utente dell'insieme di strutture.
  
**Per assegnare le autorizzazioni al gruppo Amministratori PKI dell'organizzazione**
  
1.  Accedere come membro del gruppo di protezione Amministratori organizzazione.
  
2.  Nello snap-in di Microsoft Management Console (MMC) di Siti e servizi Active Directory, visualizzare il nodo **Servizi** (dal menu **Visualizza**). Selezionare il sottocontenitore Servizi** **chiave pubblica e visualizzare le relative proprietà.
  
3.  Nella scheda **Protezione**, aggiungere il gruppo di protezione Amministratori PKI dell'organizzazione e concedergli il privilegio **Controllo completo**.
  
4.  Nella vista **Avanzate**, modificare le autorizzazioni del gruppo per garantire che il privilegio **Controllo completo** sia applicato a **Questo oggetto e tutti gli oggetti figlio**.
  
5.  Selezionare il contenitore Servizi e visualizzare le relative proprietà.
  
6.  Nella scheda **Protezione**, aggiungere il gruppo di protezione Amministratori PKI dell'organizzazione e concedergli il privilegio **Controllo completo**.
  
7.  Nella vista **Avanzate**, modificare le autorizzazioni del gruppo per garantire che il privilegio **Controllo completo** sia applicato solo a **Questo oggetto**.
  
**Per assegnare le autorizzazioni al gruppo Autori PKI dell'organizzazione**
  
1.  Accedere come membro del gruppo di protezione Amministratori PKI dell'organizzazione (o Amministratori organizzazione).
  
2.  Nello snap-in MMC di Siti e servizi Active Directory, visualizzare il nodo **Servizi** e aprire le proprietà del contenitore Servizi chiave pubblica\\AIA.
  
3.  Nella scheda **Protezione**, aggiungere il gruppo di protezione Autori PKI dell'organizzazione e concedere al gruppo le seguenti autorizzazioni:
  
    -   Lettura
  
    -   Scrittura
  
    -   Crea tutti gli oggetti figli
  
    -   Elimina tutti gli oggetti figli
  
4.  Nella vista **Avanzate**, modificare le autorizzazioni del gruppo per garantire che le autorizzazioni vengano applicate **all'oggetto specificato e tutti gli oggetti figli**.
  
5.  Ripetere i passaggi 2 - 4 per i contenitori seguenti:
  
    -   Servizi chiave pubblica\\CDP
  
    -   Servizi chiave pubblica\\Autorità di certificazione
  
        **Nota:** dopo aver concesso le autorizzazioni al gruppo Amministratori PKI dell'organizzazione mediante la precedente procedura, un membro di tale gruppo può a sua volta concedere autorizzazioni al gruppo Autori PKI dell'organizzazione.
  
##### Assegnazione delle autorizzazioni al gruppo Autori certificazione
  
Il gruppo di protezione Autori certificazione contiene gli account di computer di tutte le CA dell'organizzazione nel dominio. Questo gruppo viene utilizzato per concedere autorizzazioni agli oggetti utente e computer e agli oggetti inclusi nel contenitore CDP menzionato nella procedura precedente. Quando viene installata una CA, è necessario aggiungere il relativo account di computer a tale gruppo. Per impostazione predefinita, solo i gruppi Amministratori di dominio, Amministratori organizzazione o i gruppi di dominio incorporati Amministratori sono autorizzati a modificare l'appartenenza al gruppo Autori certificazione. Per consentire ai membri del gruppo Amministratori PKI dell'organizzazione di installare le CA dell'organizzazione, è necessario modificare le autorizzazioni di questo gruppo di protezione.
  
**Per assegnare l'autorizzazione per modificare l'appartenenza al gruppo Autori certificazione**
  
1.  Accedere come membro del gruppo Amministratori di dominio relativo al dominio in cui verrà installata la CA di emissione.
  
2.  Aprire lo snap-in MMC Utenti e computer di Active Directory.
  
3.  Dal menu **Visualizza** di MMC, assicurarsi che sia attivata l'opzione **Caratteristiche avanzate**.
  
4.  Individuare il gruppo Autori certificazione (incluso per impostazione predefinita nel contenitore Utenti) e visualizzare le proprietà del gruppo.
  
5.  Dalla scheda **Protezione**, selezionare **Aggiungi** per aggiungere il gruppo **Amministratori PKI dell'organizzazione**, quindi fare clic sul pulsante Avanzate.
  
6.  Selezionare il gruppo **Amministratori PKI dell'organizzazione** dall'elenco e fare clic sul pulsante **Modifica**.
  
7.  Selezionare la scheda **Proprietà** e assicurarsi che sia selezionato **Solo questo oggetto** nella casella **Applica a**.
  
8.  Scorrere verso il basso e fare clic sulla casella **Scrivi membri** nella colonna **Consenti**.
  
9.  Chiudere tutte le finestre di dialogo, salvando le modifiche apportate facendo clic su **OK** per ciascuna.
  
10. Sarà necessario riavviare il server della CA di emissione prima di installare il componente Servizi certificati. In questo modo si consentirà al server di rilevare i membri del nuovo gruppo nel proprio token di accesso.
  
##### Assegnazione delle autorizzazioni di ripristino al gruppo Amministratori PKI dell'organizzazione
  
Per installare le CA dell'organizzazione, è necessario disporre dei diritti di ripristino di file e directory nel dominio in cui si sta installando la CA. Il processo di installazione di Servizi certificati richiede questo diritto per installare i modelli di certificato nel dominio. Più specificamente, questo diritto è richiesto per consentire l'unione dei descrittori di protezione dei modelli e di altri oggetti della directory e, quindi, di assegnare le autorizzazioni corrette agli oggetti PKI del dominio. I gruppi di dominio incorporati Amministratori, Operatori server e Operatori backup dispongono di questo diritto per impostazione predefinita.
  
Poichè si utilizzerà il gruppo Amministratori PKI dell'organizzazione per eseguire l'installazione della CA, è necessario concedere a tale gruppo il diritto Ripristino di file e directory.
  
**Per assegnare i diritti di ripristino al gruppo Amministratori PKI dell'organizzazione:**
  
1.  Accedere come membro di Amministratori di dominio relativo al dominio in cui verrà installata la CA di emissione.
  
2.  Aprire lo snap-in MMC Utenti e computer di Active Directory.
  
3.  Selezionare la UO dei controller di dominio e visualizzare le proprietà della UO.
  
4.  Nella scheda Criteri di gruppo, selezionare il GPO **Criterio controller di dominio predefinito**, quindi fare clic su **Modifica**.
  
5.  Selezionare Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Criteri locali\\Assegnazione diritti utente e fare doppio clic sulla voce **Ripristino di file e directory**.
  
6.  Aggiungere il gruppo Amministratori PKI dell'organizzazione all'elenco visualizzato.
  
7.  Chiudere la finestra di dialogo e la console MMC di modifica del GPO.
  
    **Importante:** se si dispone di altri GPO che impostano il diritto utente **Ripristino di file e directory** nei controller di dominio, è necessario eseguire la procedura sopra descritta sui GPO utilizzando la massima priorità invece di **Criterio controller di dominio predefinito**. Le impostazioni dei diritti utente non sono cumulative e sarà valido solo l'ultimo GPO per il quale sono stati impostati questi diritti, ovvero quello con la priorità più alta.
  
#### Verifica
  
È possibile verificare la creazione di gruppi, utenti e UO sfogliandoli in Utenti e computer di Active Directory della MMC. Gli utenti devono essere membri dei gruppi appropriati (sia gli utenti test che gli effettivi account utente dell'amministrazione PKI).
  
Per verificare l'applicazione corretta delle autorizzazioni al contenitore Servizi chiave pubblica, eseguire i passaggi seguenti. Una copia di Strumenti di supporto di Windows Server 2003 deve essere installata nel sistema in cui si esegue tale procedura. La procedura non deve essere eseguita in una CA.
  
**Nota:** nelle seguenti procedure, invece di accedere con diversi account utente, è possibile usare l'utilità Runas oppure, in Windows Explorer, l'opzione di menu sensibile al contesto **Esegui come** per eseguire MMC ADSIEdit nel contesto degli utenti richiesti.
  
**Per verificare le autorizzazioni di Servizi chiave pubblica**
  
1.  Accedere a un server membro del dominio (ad esempio, il server della CA di emissione) come membro del gruppo Amministratori PKI dell'organizzazione.
  
2.  Eseguire mmc.exe e caricare lo snap-in Modifica ADSI.
  
3.  Fare clic con il pulsante destro del mouse sulla cartella Modifica ADSI, selezionare **Connetti a**, quindi selezionare **Configurazione** dall'elenco a discesa **Seleziona un contesto di nomi noto**.
  
4.  Passare al contenitore Servizi chiave pubblica e selezionarlo con il pulsante destro del mouse, quindi selezionare **Nuovo** e **Oggetto**.
  
5.  Scegliere **Contenitore** dall'elenco e denominarlo (ad esempio, **Test**).
  
    L'oggetto contenitore deve essere creato correttamente nel contenitore Servizi chiave pubblica.
  
6.  Eliminare l'oggetto contenitore appena creato.
  
7.  Non sarà consentito creare un oggetto contenitore all'interno del contenitore Configurazione, tranne che nel contenitore Servizi e nei relativi contenitori figlio.
  
8.  Accedere come membro del gruppo Autori PKI dell'organizzazione.
  
9.  Caricare ADSIEdit e collegarsi al contesto dei nomi (NC) **Configurazione**.
  
10. Provare a creare un oggetto contenitore nel contenitore Servizi chiave pubblica. Il tentativo non dovrebbe riuscire.
  
11. Creare un oggetto di testing (un oggetto contenitore) in ciascun sottocontenitore AIA, CDP e Autorità di certificazione.
  
12. Rimuoverli dopo aver verificato che siano stati creati correttamente.
  
    **Attenzione:** fare attenzione a eliminare solo gli oggetti di testing creati. I membri del gruppo Amministratori PKI dell'organizzazione, in particolare, dispongono di autorizzazioni sufficienti per eliminare il contenitore Servizi a chiave pubblica** **.
  
    **Nota:** se si sceglie di non installare gli Strumenti di supporto di Windows Server 2003, ADSIEdit non sarà disponibile. Queste procedure di verifica possono essere eseguite dalla riga dei comandi, utilizzando le utilità incorporate dsadd.exe e dsrm.exe. Tuttavia, è indispensabile fare attenzione a utilizzare la sintassi e i percorsi dell'oggetto directory corretti con queste utilità. Testare i comandi attentamente in un sistema di testing, prima di utilizzarli nell'insieme delle strutture di produzione di Active Directory.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Protezione di Windows Server 2003 per Servizi certificati
  
In questa sezione viene descritto come applicare i criteri di protezione e altre misure di sicurezza a Windows Server 2003 prima di installare Servizi certificati. Occorre inoltre leggere la sezione relativa alla protezione fisica nel capitolo 4, "Progettazione dell’infrastruttura a chiave pubblica (PKI)".
  
#### Implementazione della protezione nel server della CA principale
  
Nelle sezioni seguenti viene descritta la configurazione di gruppi e account utenti locali e l'applicazione dei criteri di protezione al server della CA.
  
##### Creazione degli account utente e dei gruppi di protezione locali nella CA principale
  
Poiché la CA principale non fa parte di un dominio, i ruoli e le funzionalità amministrative vengono definiti utilizzando gli account utente e i gruppi di protezione locali.
  
**Per creare gli account utenti e i gruppi locali sul server della CA principale**
  
1.  Nella CA principale, eseguire lo script seguente per creare gruppi di gestione della CA locale:
  
    Cscript //job:CertLocalGroups C:\\MSSScripts\\ca\_setup.wsf
  
    Lo script crea i gruppi locali descritti nella tabella seguente.
  
    **Tabella 7.11. Nomi e scopi dei gruppi**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Nome gruppo</th>
    <th style="border:1px solid black;" >Scopo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Amministratori CA</td>
    <td style="border:1px solid black;">Dispone di privilegi amministrativi completi sulla CA, inclusa la determinazione dell'appartenenza di altri ruoli.</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Responsabili certificazione</td>
    <td style="border:1px solid black;">Gestisce il rilascio e la revoca dei certificati.</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Controllori CA</td>
    <td style="border:1px solid black;">Gestisce i dati di controllo per la CA.</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Operatori backup CA</td>
    <td style="border:1px solid black;">Dispone delle autorizzazioni a eseguire il backup e il ripristino delle chiavi e dei dati della CA.</td>
    </tr>
    </tbody>
    </table>
  
2.  Crea account utente locali per il personale che amministrerà la CA. A scopo di test e dimostrazione, gli account locali generici che corrispondono a ciascuno dei ruoli definiti dai gruppi precedenti vengono creati dallo script seguente. Ignorare questo passaggio se si è in grado di creare account effettivi e procedere alla creazione.
  
    Cscript //job:CertLocalTestAccts C:\\MSSScripts\\ca\_setup.wsf
  
    Lo script utilizza CAPICOM per generare password pseudo casuali su tutti gli account invece di lasciarli con password vuote. Prendere nota delle password dall'output dello script o reimpostare le password con quelle desiderate.
  
    **Nota:** l'uso di account generici con password condivise tra gli amministratori rende in teoria privi di significato gli itinerari di controllo. In ambienti di produzione ad alta protezione, è necessario utilizzare sempre account individuali.
  
    Lo script crea gli account locali descritti nella tabella seguente.
  
    **Tabella 7.12. Nomi e scopi degli account**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Nome account</th>
    <th style="border:1px solid black;" >Scopo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">AmminCA</td>
    <td style="border:1px solid black;">Dispone di privilegi amministrativi completi sulla CA, inclusa la determinazione dell'appartenenza di altri ruoli.</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">ResponsCert</td>
    <td style="border:1px solid black;">Gestisce il rilascio e la revoca dei certificati.</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">ControlloreCA</td>
    <td style="border:1px solid black;">Gestisce i dati di controllo per la CA.</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">BackupCA</td>
    <td style="border:1px solid black;">Dispone delle autorizzazioni a eseguire il backup e il ripristino delle chiavi e dei dati della CA.</td>
    </tr>
    </tbody>
    </table>
  
    **Nota:** gli account test rappresentano la configurazione dei ruoli amministrativi più complessa, nella quale ciascun ruolo della CA corrisponde a un singolo utente (account utente). Tuttavia, disporre di account separati per ogni ruolo non è particolarmente vantaggioso, a meno che ciascun ruolo non sia effettivamente svolto da persone diverse. È legittimo, però, disporre di singoli account in più gruppi di ruolo o anche in tutti i gruppi di ruolo, se ciò riflette in modo più accurato la struttura amministrativa.
  
3.  Aggiungere tali account utente ai gruppi di protezione amministrativi nel modo più appropriato. Utilizzare la tabella seguente per gli account test oppure utilizzare i propri account in base ai ruoli e ai criteri di protezione IT definiti dall'organizzazione.
  
    **Tabella 7.13. Nomi account e appartenenze di gruppo**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Nome account</th>
    <th style="border:1px solid black;" >Appartenenza al gruppo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">AmminCA</td>
    <td style="border:1px solid black;">Amministratori CA</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">ResponsCert</td>
    <td style="border:1px solid black;">Responsabili certificazione</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">ControlloreCA</td>
    <td style="border:1px solid black;">–Controllori CA
    –Amministratori</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">BackupCA</td>
    <td style="border:1px solid black;">Operatori backup CA</td>
    </tr>
    </tbody>
    </table>
  
    **Nota:** è anche possibile assegnare ai membri del gruppo Amministratori CA l'appartenenza al gruppo locale Amministratori. Esistono determinate attività che richiedono privilegi amministrativi locali e può essere opportuno associarle al ruolo Amministratori CA.
  
###### Creazione di un modello di amministrazione semplificato per la CA principale
  
La maggior parte delle organizzazioni non richiede una struttura amministrativa complessa come quella illustrata nella procedura precedente Per alcune organizzazioni, potrebbe non essere necessaria la separazione dei ruoli; molte useranno tre ruoli: Amministratore CA, Controllore e Operatore backup. Questa configurazione viene riportata nella tabella seguente utilizzando un sottoinsieme degli account test creati precedentemente.
  
**Tabella 7.14. Assegnazione dei gruppi del modello amministrativo semplificato**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Ruolo amministrativo semplificato</th>
<th style="border:1px solid black;" >Appartenenza al gruppo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">AmminCA</td>
<td style="border:1px solid black;">Amministratori CA
Responsabili certificazione
Amministratori</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllore CA</td>
<td style="border:1px solid black;">Controllori CA
Amministratori</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">BackupCA</td>
<td style="border:1px solid black;">Operatori backup CA</td>
</tr>
</tbody>
</table>
  
###### Verifica dei gruppi e degli account
  
Verificare la creazione di gruppi, utenti e appartenenze ai gruppi esaminando il nodo Utenti e Gruppi dello snap-in MMC Gestione computer.
  
##### Applicazione delle impostazioni di protezione del sistema al server della CA principale
  
I server CA sono protetti tramite il ruolo Servizi certificati del client dell'organizzazione definito nella *Guida per la protezione di Windows Server 2003* (vedere la sezione "Ulteriori informazioni" alla fine di questo capitolo).
  
La CA principale non è membro di un dominio e, pertanto, non può usare i criteri di gruppo di dominio, quindi i modelli e le procedure di protezione devono essere applicati manualmente. Ottenere i modelli di protezione seguenti dalla *Guida per la protezione di Windows Server 2003* e copiarli nella cartella C:\\MSSScripts del server della CA principale:
  
-   Enterprise Client - Domain.inf
  
-   Enterprise Client - Member Server Baseline.inf
  
-   Enterprise Client - Certificate Services.inf
  
Personalizzare i modelli di protezione e applicarli al server in base alla procedura seguente.
  
**Per personalizzare i modelli di protezione**
  
1.  Accedere come un membro del gruppo locale Amministratori e caricare Enterprise Client - Certificate Services.inf in MMC Modelli di protezione.
  
2.  In Criteri locali\\Opzioni di protezione modificare le voci seguenti in base agli standard di protezione dell'organizzazione:
  
    -   Account: Rinomina account amministratore: *nuovo\_nome\_amministratore*
  
    -   Account: Rinomina account guest: *nuovo\_nome\_guest*
  
    -   Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso: *testo\_di\_note\_legali*
  
    -   Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso: *titolo\_note\_legali*
  
        **Nota:** il valore di questi elementi dipende dai criteri correnti dell'organizzazione. Non è necessario configurare questi valori, sebbene sia consigliabile.
  
3.  In Criteri locali\\Assegnazione diritti utenti, aggiungere il gruppo locale Controllori CA al diritto utente **Gestione file registro di controllo e di protezione**.
  
4.  In Criteri locali\\Assegnazione diritti utente, aggiungere il gruppo locale Operatori backup CA ai seguenti diritti utente:
  
    -   Backup di file e directory
  
    -   Ripristino di file e directory
  
5.  In Criteri locali\\Assegnazione diritti utenti, aggiungere i gruppi locali seguenti al diritto utente **Consenti accesso locale**:
  
    -   Amministratori
  
    -   Operatori backup
  
    -   Amministratori CA
  
    -   Responsabili certificazione
  
    -   Controllori CA
  
    -   Operatori backup CA
  
6.  Aprire le proprietà dei servizi elencati di seguito nella cartella Servizi sistema e fare clic su **Definisci questa impostazione nel modello**. Accettare le autorizzazioni predefinite facendo clic su **OK**. Impostare il valore dell'opzione **Selezionare la modalità di avvio servizio** impostandola su **Automatico**.
  
    -   Archivi rimovibili
  
    -   Copia replicata del volume
  
    -   Provider di copie shadow per software MS
  
        **Nota:** questi servizi sono disattivati nel modello di protezione di base per i server membri, ma sono richiesti per l'esecuzione di NTBackup.exe.
  
7.  Con il modello selezionato, salvare le modifiche apportate al modello (facendo clic su **Salva** nel menu **File**), quindi chiudere MMC.
  
8.  Eseguire i comandi seguenti nell'ordine specificato per applicare i modelli di protezione richiesti. Lo strumento Secedit potrebbe indicare che sono stati generati alcuni messaggi di avviso, che possono essere ignorati (tuttavia, è opportuno esaminare gli errori):
  
    secedit /configure /db %temp%\\casec.db /cfg "C:\\MSSScripts\\Enterprise Client - Domain.inf" /overwrite /log "%temp%\\Enterprise Client - Domain.log"
  
    secedit /configure /db %temp%\\casec.db /cfg "C:\\MSSScripts\\Enterprise Client - Member Server Baseline.inf" /log "%temp%\\Enterprise Client - Member Server Baseline.log"
  
    secedit /configure /db %temp%\\casec.db /cfg "C:\\MSSScripts\\Enterprise Client - Certificate Services.inf" /log "%temp%\\Enterprise Client - Certificate Services.log"
  
    Sebbene tali comandi siano visualizzati su più di una riga, immetterli in una unica riga.
  
    **Nota:** la *Guida per la protezione di Windows Server 2003* contiene una spiegazione più dettagliata di queste impostazioni di protezione.
  
###### Verifica delle impostazioni di protezione
  
Per verificare la corretta applicazione delle impostazioni di protezione, procedere come indicato di seguito.
  
**Per verificare le impostazioni di protezione della CA principale**
  
1.  Visualizzare i registri secedit generati nella sezione precedente e verificare che non siano stati registrati errori gravi. È normale che vengano visualizzati diversi messaggi di avviso ed errori minori, ma non tanto gravi da causare un errore di applicazione del modello di protezione.
  
2.  Riavviare il server e verificare che tutti i servizi previsti siano stati avviati e che non siano stati registrati errori nel Registro eventi di sistema.
  
3.  Tentare di accedere utilizzando uno degli account test creati o un account reale. Dopo la visualizzazione del testo dell'avviso legale, deve essere possibile accedere al sistema.
  
#### Implementazione della protezione nel server della CA di emissione
  
Le sezioni seguenti descrivono l'applicazione dei criteri di protezione nel server della CA.
  
##### Applicazione delle impostazioni di protezione del sistema al server CA di emissione
  
I server della CA sono protetti mediante il ruolo Servizi certificati definito nella *Guida per la protezione di Windows Server 2003*. La CA di emissione è un membro di un dominio, pertanto, le impostazioni dei criteri di protezione vengono applicati utilizzando criteri di gruppo basati sul dominio.
  
Sarà necessario creare una struttura di unità organizzative adeguata che possa contenere gli oggetti computer del server CA e una struttura GPO per applicare le impostazioni di protezione. È necessario creare tre oggetti Criteri di gruppo (GPO):
  
-   Enterprise Client - Criteri di base dei server membro
  
-   Enterprise Client - Servizi certificati
  
-   Enterprise Client - Servizi certificati IIS (solo se IIS è installato nel computer CA)
  
    **Nota:** la *Guida per la protezione di Windows Server 2003* include inoltre le impostazioni consigliate per i criteri del dominio (criteri di blocco account e password). Tali impostazioni vengono ereditate da tutti i computer del dominio. Se non si desidera modificare i criteri al livello di dominio, ma si intende utilizzare le impostazioni consigliate per la CA di emissione, è necessario creare inoltre un quarto GPO collegato all'unità organizzativa CA:  
    Enterprise Client - Criteri account per Servizi certificati  
    È necessario attenersi alla procedura seguente per importare il modello Criteri di dominio nel GPO. Tali impostazioni avranno effetto solo sugli account locali della stessa CA.
  
La procedura che segue indica come è possibile creare le UO e i GPO per la propria azienda. I nomi di GPO e UO vengono forniti esclusivamente a scopo esemplificativo. È necessario adeguare la procedura ai propri standard di UO e GPO di dominio..
  
**Per creare unità organizzative e GPO nel server CA**
  
1.  Ottenere i seguenti modelli di protezione dalla *Windows Server 2003 Security Guide*:
  
    -   Enterprise Client - Dominio
  
    -   Enterprise Client - Criteri di base dei server membro
  
    -   Enterprise Client - Servizi certificati
  
    -   Enterprise Client - Server IIS (solo se IIS è installato nel computer CA)
  
2.  Accedere come membro del gruppo degli Amministratori di dominio o come utente che dispone di diritti per la creazione delle UO descritte di seguito. Inoltre, è necessario essere membri di Proprietari autori criteri di gruppo.
  
3.  Aprire lo snap-in MMC Utenti e computer di Active Directory.
  
4.  Creare la seguente struttura dell'unità organizzativa:
  
    woodgrovebank.com (dominio)
  
    Server membri
  
         CA
  
5.  Aprire le proprietà del contenitore di dominio, nella scheda **Criterio gruppo** fare clic su **Nuovo** per creare un nuovo GPO e denominarlo **Criteri dominio.**
  
6.  Modificare il GPO e passare alla cartella Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione. Fare clic con il pulsante destro del mouse sulla cartella Impostazioni protezione, quindi fare clic su **Importa**. Selezionare Enterprise Client-Domain.inf come modello da importare.
  
7.  Chiudere il GPO.
  
8.  Ripetere i tre passaggi precedenti per la combinazione di unità operative, GPO e modelli di protezione mostrata nella tabella seguente.
  
    **Tabella 7.15. Mapping dei GPO ai modelli di protezione e alle UO**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >UO</th>
    <th style="border:1px solid black;" >GPO</th>
    <th style="border:1px solid black;" >Modello di protezione</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Server membri</td>
    <td style="border:1px solid black;">Enterprise Client - Criteri di base dei server membro</td>
    <td style="border:1px solid black;">Enterprise Client - Member Server Baseline.inf</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">CA</td>
    <td style="border:1px solid black;">Enterprise Client - Servizi certificati</td>
    <td style="border:1px solid black;">Enterprise Client - Certificate Services.inf</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">CA</td>
    <td style="border:1px solid black;">(Facoltativo, vedere nota precedente)
    Enterprise Client - Criteri account per Servizi certificati</td>
    <td style="border:1px solid black;">Enterprise Client - Domain.inf</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">CA</td>
    <td style="border:1px solid black;">Facoltativo (se IIS è installato nel computer CA)
    Enterprise Client - Servizi certificati IIS</td>
    <td style="border:1px solid black;">Enterprise Client - IIS Server.inf</td>
    </tr>
    </tbody>
    </table>
  
    **Nota:** se si è scelto di installare IIS nel computer della CA di emissione (come descritto in questo capitolo), sarà necessario creare un GPO IIS distinto solo per le CA. Sebbene sia possibile disporre anche di un GPO IIS per i server IIS Intranet, si consiglia vivamente di creare un GPO diverso che venga utilizzato esclusivamente dalle CA. In questo modo, qualsiasi modifica apportata al GPO IIS non comprometterà la sicurezza delle CA e le impostazioni di protezione delle CA resteranno interamente sotto il controllo degli amministratori dei GPO delle CA.
  
Dopo aver creato i GPO e aver importato i modelli, è necessario personalizzare le impostazioni dei GPO e applicarle ai computer Servizi certificati in base alla procedura seguente.
  
**Per personalizzare e applicare il GPO Servizi certificati**
  
1.  Da Utenti e computer di Active Directory, modificare il GPO Enterprise Client - GPO Servizi certificati. In Configurazione computer\\Impostazioni di Windows\\Impostazioni di protezione\\Criteri locali\\Opzioni di protezione modificare gli elementi indicati di seguito in base agli standard di protezione della propria azienda:
  
    -   Account: Rinomina account amministratore: *nuovo\_nome\_amministratore*
  
    -   Account: Rinomina account guest: *nuovo\_nome\_guest*
  
    -   Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso: *testo\_di\_note\_legali*
  
    -   Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso: *titolo\_note\_legali*
  
2.  In Criteri locali\\Assegnazione diritti utente, aggiungere il gruppo di dominio Controllori CA ai diritti utente **Gestione registri di controllo e protezione**.
  
3.  In Criteri locali\\Assegnazione diritti utente, aggiungere Operatori backup CA ai seguenti diritti utente:
  
    -   Backup di file e directory
  
    -   Ripristino di file e directory
  
4.  In Criteri locali\\Assegnazione diritti utente, aggiungere i seguenti gruppi locali e di dominio al diritto **Consenti** **Accesso locale**:
  
    -   (locale) Amministratori
  
    -   (locale) Operatori backup
  
    -   (dominio) Amministratori PKI dell'organizzazione
  
    -   (dominio) Autori PKI dell'organizzazione
  
    -   (dominio) Amministratori CA  
  
    -   (dominio) Responsabili certificazione
  
    -   (dominio) Controllori CA
  
    -   (dominio) Operatori backup CA
  
5.  In **File System**, aggiungere la cartella D:\\CertLog. Assicurarsi che le autorizzazioni corrispondano a quelle riportate nella tabella seguente.
  
    **Tabella 7.16. Autorizzazioni per le cartelle del database CA**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Utente/Gruppo</th>
    <th style="border:1px solid black;" >Autorizzazione</th>
    <th style="border:1px solid black;" >Consenti/Nega</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Amministratori</td>
    <td style="border:1px solid black;">Controllo completo</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">System</td>
    <td style="border:1px solid black;">Controllo completo</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Operatori backup</td>
    <td style="border:1px solid black;">Controllo completo</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">CREATOR OWNER</td>
    <td style="border:1px solid black;">Controllo completo</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    </tbody>
    </table>
  
6.  Per la stessa cartella, aggiungere le voci di controllo riportate nella tabella seguente per il gruppo Tutti (fare clic sul pulsante **Avanzate** della finestra di dialogo **Protezione**, quindi selezionare la scheda **Controllo**). Digitare **Tutti** quando viene richiesto di indicare un nome per un utente o un gruppo. Aggiungendo il gruppo Tutti, verrà visualizzata una finestra di dialogo con titolo **Voci di controllo per D:\\CertLog**, in cui è possibile immettere le impostazioni dettagliate relative al controllo. Assicurarsi che l'opzione **La cartella selezionata, le sottocartelle e i file** sia selezionata nel campo **Applica a**. Selezionare tutte le voci a cui corrisponde Sì nella tabella.
  
    **Tabella 7.17. Controllo per le cartelle del database CA**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Autorizzazione</th>
    <th style="border:1px solid black;" >Riuscito</th>
    <th style="border:1px solid black;" >Failed</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Controllo completo</td>
    <td style="border:1px solid black;"><br />
    </td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Visita cartelle/Esecuzione file</td>
    <td style="border:1px solid black;"><br />
    </td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Visualizza contenuto cartelle/Lettura dati</td>
    <td style="border:1px solid black;"><br />
    </td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Lettura attributi</td>
    <td style="border:1px solid black;"><br />
    </td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Lettura attributi estesi</td>
    <td style="border:1px solid black;"><br />
    </td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Creazione file/Scrittura dati</td>
    <td style="border:1px solid black;">Sì</td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Creazione cartelle/Aggiunta dati</td>
    <td style="border:1px solid black;">Sì</td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Scrittura attributi</td>
    <td style="border:1px solid black;">Sì</td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Scrittura attributi estesi</td>
    <td style="border:1px solid black;">Sì</td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Eliminazione sottocartelle e file</td>
    <td style="border:1px solid black;">Sì</td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Eliminazione</td>
    <td style="border:1px solid black;">Sì</td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Autorizzazioni di lettura</td>
    <td style="border:1px solid black;"><br />
    </td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Cambia autorizzazioni</td>
    <td style="border:1px solid black;">Sì</td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Diventa proprietario</td>
    <td style="border:1px solid black;">Sì</td>
    <td style="border:1px solid black;">Sì</td>
    </tr>
    </tbody>
    </table>
  
7.  Aprire la pagina delle proprietà dei servizi seguenti nella cartella Servizi di sistema, quindi fare clic su **Definisci questa impostazione dei criteri nel modello**. Accettare le autorizzazioni predefinite facendo clic su **OK**. Impostare il valore dell'opzione **Selezionare la modalità di avvio servizio** impostandola su **Automatico**.
  
    -   Archivi rimovibili
  
    -   Copia replicata del volume
  
    -   Provider di copie shadow per software MS
  
    -   Utilità di pianificazione
  
        **Nota:** questi servizi sono disattivati nel modello di protezione di base per i server membro, ma i primi tre sono necessari per NTBackup.exe. Il servizio Utilità di pianificazione è richiesto da alcuni script operativi.
  
8.  Spostare l'account del computer CA di emissione nell'unità organizzativa Servizi certificati.
  
9.  Nella CA di emissione (il server in cui sarà installata la CA), eseguire il comando seguente per applicare le impostazioni di GPO al computer:
  
    gpupdate
  
    **Nota:** nella *Guida per la protezione di Windows Server 2003,* le impostazioni di protezione sono descritte in modo più dettagliato.
  
###### Verifica delle impostazioni di protezione
  
Per verificare la corretta applicazione delle impostazioni di protezione, procedere come indicato di seguito.
  
**Per verificare le impostazioni di protezione della CA principale**
  
1.  Controllare la presenza di eventi con origine SceCli nel Registro eventi applicazioni. Dovrebbe venire visualizzato un evento con ID 1704 dopo il comando **gpupdate**. Il testo dell'evento dovrebbe essere il seguente:
  
    Applicazione del criterio di protezione agli oggetti del criterio di gruppo riuscita.
  
2.  Riavviare il server e verificare che tutti i servizi previsti siano stati avviati e che non siano stati registrati errori nel registro eventi del sistema.
  
3.  Tentare di accedere utilizzando gli account test creati o gli account reali. Dopo la visualizzazione del testo dell'avviso legale, deve essere possibile accedere al sistema.
  
##### Configurazione della protezione di Servizi terminal nella CA di emissione
  
È necessario disattivare Servizi Terminal nel computer CA di emissione, in quanto potrebbero essere utilizzati da intrusi per attaccare la CA; inoltre, riducono significativamente l'effetto delle misure di protezione fisica applicate al server. Se lo si lascia attivo (ai fini dell'amministrazione remota), occorre configurare le impostazioni descritte nella seguente tabella.
  
**Nota:** lo stato di Servizi terminal nella CA principale è in gran parte irrilevante, in quanto la CA principale non è connessa alla rete.
  
Queste impostazioni devono essere configurate nel GPO di protezione di Servizi certificati o in un altro GPO che si applica alla o alle CA in linea.
  
**Tabella 7.18. Impostazioni da configurare in Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Servizi terminal**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Percorso impostazioni</th>
<th style="border:1px solid black;" >Criteri</th>
<th style="border:1px solid black;" >Impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Nega la disconnessione di un amministratore connesso alla sessione della console</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Non consentire agli amministratori locali di personalizzare le autorizzazioni</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Imposta le regole per il controllo remoto delle sessioni utente di Servizi terminal</td>
<td style="border:1px solid black;">Nessun controllo remoto consentito</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Reindirizzamento dati client/server</td>
<td style="border:1px solid black;">Consenti reindirizzamento fuso orario</td>
<td style="border:1px solid black;">Disabilitata</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Non consentire il reindirizzamento degli Appunti</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Consenti il reindirizzamento audio</td>
<td style="border:1px solid black;">Disabilitata</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Non consentire il reindirizzamento della porta COM</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Non consentire il reindirizzamento della stampante client</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Non consentire il reindirizzamento della porta LPT</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Non consentire il reindirizzamento delle unità</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Non impostare stampante predefinita del client come stampante predefinita per una sessione</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Crittografia e protezione</td>
<td style="border:1px solid black;">Richiedi sempre password del client alla connessione</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Imposta livello di crittografia connessione client</td>
<td style="border:1px solid black;">Alto</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Crittografia e protezione\Protezione RPC</td>
<td style="border:1px solid black;">Server protetto (Richiedi protezione)</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Sessioni</td>
<td style="border:1px solid black;">Imposta limite di tempo per le sessioni disconnesse</td>
<td style="border:1px solid black;">10 minuti</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Consenti la riconnessione solo dal client originale</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
Qualsiasi account di dominio o gruppo di protezione che richiede l'accesso di Servizi terminal alla CA deve essere aggiunto al gruppo Utenti desktop remoto (a meno che non sia già un membro del gruppo Amministratori locale).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Altre attività di configurazione di Windows
  
Sarà necessario quasi sicuramente eseguire altre attività di configurazione sia nella CA di emissione che nella CA principale, a seconda dell'infrastruttura e degli standard della propria organizzazione. Queste attività possono comprendere:
  
-   Attivazione dei backup (descritta nel capitolo11) o installazione di agenti di backup.
  
-   Configurazione del protocollo SNMP (Simple Network Management Protocol) del servizio Strumentazione gestione Windows (WMI).
  
-   Installazione di agenti di gestione, quali i componenti client Microsoft Operations Manager (MOM) o Microsoft Systems Management Server (SMS).
  
-   Installazione di software antivirus.
  
-   Installazione di agenti per il rilevamento delle intrusioni.
  
Verificare queste voci durante l'installazione in base alle istruzioni fornite con il prodotto.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Installazione e configurazione della CA principale
  
In questa sezione viene descritto come installare e configurare Servizi certificati nella CA principale.
  
#### Preparazione del file Capolicy.inf per la CA principale
  
Il file Capolicy.inf deve essere creato prima di impostare un'autorità di certificazione principale in Windows 2003. Tale file specifica le caratteristiche del certificato CA principale autofirmato, ad esempio la lunghezza della chiave, il periodo di validità del certificato, i percorsi di pubblicazione CRL e AIA, i criteri di certificazione e un'istruzione per le prassi di certificazione (CPS), se ne è stata creata una.
  
**Nota:** vedere la sezione "Creazione di una dichiarazione delle procedure di certificazione" nel capitolo 4, "Progettazione dell’infrastruttura a chiave pubblica (PKI)," per ulteriori informazioni sulla CPS e sui casi in cui è opportuno crearne una. La CPS è un documento legale e non un elemento tecnico, pertanto, bisogna essere certi che sia realmente necessaria prima di configurarla nella CA.
  
Le informazioni CRL e AIA non sono necessarie per il certificato della CA principale in sé, pertanto i parametri CRLDistributionPoint e AuthorityInformationAccess sono impostati su **Vuoto** nel file Capolicy.inf.
  
**Per creare il file CAPolicy.inf**
  
1.  Immettere il testo seguente in un editor di testi, ad esempio Blocco note:
  
    <codesnippet language displaylanguage containsmarkup="false">\[Version\] Signature= "$Windows NT$" \[Certsrv\_Server\] RenewalKeyLength=4096  RenewalValidityPeriod=Years  RenewalValidityPeriodUnits=16 \[CRLDistributionPoint\] Empty=true \[AuthorityInformationAccess\] Empty=true  
```
  
    **Attenzione:** l'utilizzo di una chiave della lunghezza di 4.096 bit potrebbe causare problemi di compatibilità. Alcuni dispositivi (per esempio, alcuni router) e alcuni software precedenti di altri fornitori non sono in grado di elaborare chiavi superiori a una data dimensione.
  
2.  Se è stata definita una CPS per la CA, includere quanto segue nel file Capolicy.inf (è necessario sostituire tutte le voci in corsivo con i valori della propria organizzazione):
  
    <codesnippet language displaylanguage containsmarkup="false">\[CAPolicy\] Policies=WoodGrove Bank Root CA CPS \[WoodGrove Bank Root CA CPS\] OID=your.Orgs.OID URL = "http://www.woodgrovebank.com/YourCPSPage.htm"   
```
  
3.  Salvare il file come %windir%\\Capolicy.inf (o sostituire %windir% con il percorso assoluto della cartella in cui Windows è installato, ad esempio C:\\Windows). È necessario essere un amministratore locale o disporre delle autorizzazioni di scrittura nella cartella di Windows per completare questo passaggio.
  
#### Installazione dei componenti software di Servizi certificati
  
Usare Aggiunta guidata componenti di Windows per installare i componenti software della CA. Per completare l'installazione è necessario disporre del CD o del percorso di rete dell'installazione di Windows Server 2003.
  
**Per installare Servizi certificati**
  
1.  Accedere come membro del gruppo Amministratori locale ed eseguire Gestione componenti facoltativi (oppure selezionare **Installazione applicazioni**/**Componenti di Windows** dal Pannello di controllo):
  
    sysocmgr /i:sysoc.inf.
  
2.  Selezionare il componente **Servizi certificati** (fare clic su **Sì** per eliminare il messaggio di avviso relativo alla ridenominazione).
  
3.  Selezionare il tipo di CA come **CA autonoma (standalone) principale**, assicurando di aver selezionato la casella di controllo **Utilizzare impostazione personalizzate**.
  
4.  Nella finestra di dialogo **Coppia di chiavi pubblica e privata,** lasciare le impostazioni predefinite, eccetto la lunghezza della chiave che deve essere impostata su 4096. **Il Tipo CSP** deve essere **Microsoft Strong Cryptographic Provider**.
  
5.  Immettere le informazioni di identificazione dell'autorità di certificazione nel modo seguente:
  
    -   Nome comune CA: *WoodGrove Bank Root CA* 
  
    -   Suffisso del nome distinto: *DC=woodgrovebank,DC=com*  
        DC=woodgrovebank,DC=com (il nome principale dell'insieme di strutture Active Directory dell'organizzazione)
  
    -   Periodo di validità: **8 ann*i***
  
        **Nota:** se una CA è stata installata precedentemente nel computer, viene visualizzato un messaggio di avviso in cui si richiede di confermare se sovrascrivere la chiave privata dell'installazione precedente. Verificare se la chiave può essere eliminata prima di procedere. In caso di dubbi, annullare la procedura di installazione ed eseguire il backup delle informazioni sulla chiave esistente tramite un backup di sistema o un backup del certificato CA e della chiave privata esistenti; vedere le relative procedure nel capitolo 11, "Gestione dell'infrastruttura a chiave pubblica".
  
    Il CSP genera la coppia di chiavi che viene memorizzata nell'archivio delle chiavi del computer locale.
  
6.  Non modificare i percorsi predefiniti del database dei certificati, dei registri del database e della cartella di configurazione.
  
    **Note:**   
    durante la configurazione si potrebbe generare un messaggio di avviso che informa dell'impossibilità di creare una cartella condivisa, a causa della precedente disabilitazione di tutte le interfacce di rete. Ignorare l'avviso e continuare.  
    È necessario posizionare il database dei certificati e il relativo registro nelle unità NTFS locali.
  
    Gestione componenti facoltativi installa quindi i componenti di Servizi certificati. In questa fase del processo, verrà richiesto di inserire il supporto di installazione (CD) di Windows Server 2003.
  
7.  Fare clic su **OK** per eliminare l'avviso relativo a IIS e continuare l'installazione fino al termine.
  
#### Verifica dell'installazione della CA principale
  
È possibile verificare il completamento dell'installazione di Servizi certificati nel modo seguente:
  
**Per verificare la corretta installazione della CA principale**
  
1.  Aprire la console di gestione dell'autorità di certificazione (da **Tutti i programmi**, **Strumenti di amministrazione**). Verificare che sia stato avviato Servizi certificati e che sia possibile visualizzare le proprietà della CA.
  
2.  Nella scheda **Generale**, selezionare il certificato della CA (o **Certificato \#0** dall'elenco, in caso di più certificati), quindi fare clic su **Visualizza certificato**.
  
3.  Verificare nella scheda **Dettagli** del certificato CA che i valori visualizzati corrispondano a quelli descritti nella tabella seguente.
  
    **Tabella 7.19. Proprietà ed estensioni del certificato della CA principale**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Attributo del certificato</th>
    <th style="border:1px solid black;" >Impostazione necessaria</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Campi Autorità emittente e Oggetto</td>
    <td style="border:1px solid black;">I due campi devono essere identici e includere il nome comune completo della CA più il suffisso DN specificato durante l'installazione.</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Non prima - Non dopo</td>
    <td style="border:1px solid black;">16 anni</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Lunghezza della chiave pubblica</td>
    <td style="border:1px solid black;">RSA (4096 bit)</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Utilizzo della chiave</td>
    <td style="border:1px solid black;">Firma digitale, Firma certificato, Firma CRL non in linea, Firma CRL (86).</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Restrizioni di base (critiche)</td>
    <td style="border:1px solid black;">Tipo soggetto=CA
    Limite di lunghezza percorso=Nessuno</td>
    </tr>
    </tbody>
    </table>
 

    La presenza del tipo di oggetto Restrizioni di base è molto importante: questo valore distingue un certificato CA dal certificato di un'entità finale. Inoltre, non deve essere elencata alcuna estensione CDP o AIA.

    Se uno dei valori precedenti non è quello previsto, è consigliabile riavviare l'installazione di Servizi certificati.

    **Nota:** se è necessario eseguire nuovamente l'installazione di Servizi certificati, verrà visualizzato un avviso per informare che la chiave privata esiste già. Nel caso in cui non sia stato rilasciato alcun certificato utilizzando questa chiave, è possibile ignorare l'avviso e generare una nuova chiave. Se la CA ha già rilasciato certificati diversi dai certificati di prova, non reinstallare Servizi certificati fino a quando non è stato eseguito in modo sicuro il backup della chiave e del certificato precedenti (questa procedura è descritta nel capitolo 11, “Gestione dell'infrastruttura a chiave pubblica").

4.  È possibile visualizzare inoltre il registro di installazione di Servizi certificati (%systemroot%\\certocm.log) per eseguire ulteriori verifiche o agevolare la risoluzione dei problemi in caso di errori.

#### Configurazione delle proprietà della CA principale

Per la procedura di configurazione della CA, vengono applicati una serie di parametri specifici per l'ambiente. I valori di tali parametri sono documentati nella precedente sezione "Foglio di lavoro per la pianificazione di Servizi certificati" di questo capitolo. Tale procedura configura le proprietà della CA elencate nella seguente tabella.

**Tabella 7.20. Proprietà della CA da configurare**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Proprietà della CA</th>
<th style="border:1px solid black;" >Descrizione dell'impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">URL dei punti di distribuzione CRL</td>
<td style="border:1px solid black;">Specifica i percorsi HTTP, LDAP e FILE dai quali è possibile ottenere un CRL aggiornato.
Il percorso FILE è una cartella locale ed è utilizzato dalla CA solo per memorizzare i CRL che rilascia; nei certificati rilasciati, sono inclusi solo i percorsi LDAP e HTTP.
L'URL HTTP è elencato in sequenza prima dell'URL LDAP, in modo che i client che utilizzano i certificati della CA principale non siano dipendenti da Active Directory per ottenere CRL.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">URL AIA</td>
<td style="border:1px solid black;">I percorsi dai quali è possibile ottenere i certificati CA
Analogamente ai CDP, il percorso file viene utilizzato solo per la pubblicazione del certificato CA e l'URL LDAP ha la priorità sull'URL HTTP.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo di validità</td>
<td style="border:1px solid black;">Il periodo di validità massimo per i certificati rilasciati (che differisce dal periodo di validità del certificato CA stesso, impostato nel file CAPolicy.inf o dalla CA padre).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo CRL</td>
<td style="border:1px solid black;">Frequenza di pubblicazione del CRL.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Tempo di sovrapposizione CRL</td>
<td style="border:1px solid black;">Il tempo di sovrapposizione tra la pubblicazione di un nuovo CRL e la scadenza del CRL precedente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo Delta-CRL</td>
<td style="border:1px solid black;">Frequenza di pubblicazione del Delta-CRL (nella CA principale i Delta-CRL sono disattivati).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controllo CA</td>
<td style="border:1px solid black;">Impostazioni di controllo della CA. Tutti i controlli sono attivati per impostazione predefinita.</td>
</tr>
</tbody>
</table>
  
**Nota:** le proprietà elencate in questa tabella si riferiscono solo ai certificati emessi dalla CA principale e non al certificato della CA principale stessa.
  
**Per configurare le proprietà della CA principale**
  
1.  Accedere al server CA come membro del gruppo Amministratori locale.
  
2.  Personalizzare lo script seguente (C:\\MSSScripts\\pkiparams.vbs) includendo il DN corretto del dominio principale dell’insieme di strutture di Active Directory e l'URL HTTP che fa riferimento al server Web di pubblicazione CDP e AIA. Modificare il valore dell'impostazione **AD\_ROOT\_DN** in modo che corrisponda al DN del dominio principale dell'insieme di strutture di Active Directory. Modificare l'impostazione **HTTP\_PKI\_VROOT** in base al percorso HTTP della directory virtuale IIS impostata precedentemente.
  
    **Nota:** qui è mostrata solo una parte del file pkiparams.vbs. Non modificare o rimuovere alcun elemento del file, a meno che non si conoscano le conseguenze dell'operazione.
  
    <codesnippet language displaylanguage containsmarkup="false">'\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* '    USER SETTABLE CONSTANTS         ' ' These values MUST be set to reflect actual values used ' by the organization. '\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* ' This is the URL where CRL and CA certs are to be published. CONST CA\_HTTP\_PKI\_VROOT        = " http://www.woodgrovebank.com/pki" ' This needs to be set only if non Active directory clients need to query ' the ldap URL for CRLs. Normally they are OK with HTTP. If you do set this ' (to a specific DC FQDN) ALL clients will use this DC to query. Left blank ' AD clients use their default LDAP server (local DC) to query. CONST CA\_LDAP\_SERVER        = "" ' This needs to be set to the DN of the Active Directory Forest root domain ' This is used to set the Root CA CDP and AIA paths so that clients can ' obtain CRL and CA Certificate information from the Active Directory CONST AD\_ROOT\_DN            = "DC=woodgrovebank,DC=com"  
```
  
3.  Eseguire quindi lo script seguente:
  
    Cscript //job:RootCAConfig C:\\MSSScripts\\ca\_setup.wsf
  
##### Configurazione dei ruoli amministrativi
  
Per utilizzare i ruoli amministrativi nella CA (ad esempio Controllori, Responsabile certificati e così via), è necessario innanzitutto mappare ad essi i gruppi di protezione creati precedentemente.
  
**Nota:** in questa soluzione, vengono utilizzati i gruppi creati precedentemente per definire più ruoli distinti. In questo modo, sussiste la massima flessibilità nel delegare le responsabilità di gestione della CA. Tuttavia, se non è richiesto questo livello di delega, prendere in considerazione l'utilizzo del modello di gruppo di amministrazione semplificato, descritto precedentemente in questo capitolo. Tale modello consente di utilizzare un numero inferiore di account per eseguire le funzioni amministrative della CA.
  
**Per configurare i ruoli amministrati nella CA principale**
  
1.  Dalla console di gestione dell'autorità di certificazione, fare clic su **Proprietà** per modificare le proprietà della CA.
  
2.  Fare clic sulla scheda **Protezione** e aggiungere i gruppi di protezione locali elencati nella tabella seguente. Per ciascun gruppo aggiungere l'autorizzazione elencata.
  
    **Tabella 7.21. Autorizzazioni CA da aggiungere**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Nome gruppo</th>
    <th style="border:1px solid black;" >Autorizzazione</th>
    <th style="border:1px solid black;" >Consenti/Nega</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Amministratori CA</td>
    <td style="border:1px solid black;">Gestione CA</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Responsabili certificazione</td>
    <td style="border:1px solid black;">Rilascio e gestione certificati</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    </tbody>
    </table>
  
    **Nota:** se si desidera una separazione netta dei ruoli, è necessario rimuovere le autorizzazioni di Gestione della CA dal gruppo Amministratori locale. Poiché la CA principale è installata nella Standard Edition di Windows Server, non è possibile imporre la separazione dei ruoli (questa opzione è disponibile solo nella Enterprise Edition).
  
3.  Altri ruoli di protezione per questa CA sono stati già definiti tramite i criteri di protezione applicati precedentemente al server:
  
    -   Ai controllori CA sono stati assegnati i diritti utente Gestione protezione e Registri di controllo.
  
    -   Gli utenti del gruppo Operatori backup dispongono dei diritti necessari di backup e di ripristino della CA.
  
#### Trasferimento del certificato della CA principale e del CRL sul disco floppy
  
È necessario copiare il certificato della CA principale e il CRL dalla CA in modo che possano essere pubblicati in Active Directory e nel server di pubblicazione dei certificati IIS e CRL.
  
**Per copiare il certificato della CA principale e il CRL sul disco floppy**
  
1.  Accedere alla CA principale come membro del gruppo Amministratori CA locale, quindi inserire un disco floppy da utilizzare per il trasferimento nell'unità.
  
2.  Eseguire lo script seguente per copiare il certificato CA sul disco floppy:
  
    Cscript //job:GetCACerts C:\\MSSScripts\\CA\_Operations.wsf
  
3.  Eseguire lo script seguente per copiare i CRL CA sul disco floppy:
  
    Cscript //job:GetCRLs C:\\MSSScripts\\CA\_Operations.wsf
  
4.  Etichettare il disco **Transfer-\[***HQ-CA-01***\]**, datarlo e conservarlo per le fasi successive della procedura.
  
    **Nota:** il disco floppy non contiene informazioni di protezione riservate, ad esempio la chiave privata CA, pertanto non è necessario adottare precauzioni speciali per la custodia.
  
#### Pubblicazione del certificato della CA principale
  
Prima di installare la CA di emissione, è necessario pubblicare il certificato della CA principale nell'archivio principale attendibile di Active Directory e il CRL della CA principale nel contenitore CDP di Active Directory. In questo modo tutti i membri del dominio, inclusa la CA di emissione, importeranno il certificato della CA principale nei propri archivi principali e li attiveranno per verificare lo stato di revoca di eventuali certificati rilasciati dalla CA principale (in questo caso, la CA di emissione dovrà verificare lo stato di revoca del proprio certificato, prima di avviare Servizi certificati).
  
**Nota:** è possibile eseguire la procedura seguente da qualsiasi membro del dominio, sebbene sia necessaria l'installazione di Certutil.exe e delle librerie di supporto certadm.dll e certcli.dll nel sistema; certutil.exe (più le DLL richieste) viene installato insieme a Windows Server 2003. A questo scopo, è possibile utilizzare, ad esempio, il server CA di emissione non configurato.
  
**Per pubblicare il certificato CA principale e il CRL in Active Directory**
  
1.  Accedere a un computer membro del dominio come membro del gruppo Amministratori PKI dell'organizzazione e inserire il disco floppy utilizzato precedentemente per salvare il certificato della CA principale e il CRL (etichettato **Transfer-\[***HQ-CA-01***\]**).
  
2.  Eseguire lo script seguente per pubblicare il certificato CA in Active Directory:
  
    Cscript //job:PublishCertstoAD C:\\MSSScripts\\CA\_Operations.wsf
  
3.  Eseguire lo script seguente per pubblicare il o i CRL CA in Active Directory:
  
    Cscript //job:PublishCRLstoAD C:\\MSSScripts\\CA\_Operations.wsf
  
##### Pubblicazione del certificato della CA principale e del CRL nel server Web
  
Questo passaggio è necessario, in quanto le versioni HTTP degli URL CDP e AIA sono state specificate nelle estensioni dei certificati emessi da questa CA. Se sono presenti tali estensioni, è necessario tenerne conto pubblicando i CRL e i certificati nei percorsi indicati nei certificati.
  
**Nota:** questa procedura è identica, a prescindere se il server Web di pubblicazione CDP e AIA si trovi nella CA di emissione o in un altro server. Si presume che la directory virtuale corrisponda a quella impostata nella procedura di configurazione IIS descritta precedentemente: C:\\CAWWWPub. Se si sceglie di usare un altro percorso, occorrerà aggiornare il valore WWW\_LOCAL\_PUB\_PATH nel file C:\\MSSScripts\\PKIParams.vbs.
  
**Per pubblicare il certificato della CA principale e il CRL in un URL Web**
  
1.  Accedere al server Web come amministratore locale o con un account con autorizzazioni di scrittura nella cartella C:\\CAWWWPub.
  
2.  Assicurarsi che il disco floppy (etichettato **Transfer-\[***HQ-CA-01***\]**) contenente i certificati CA e i CRL sia inserito nell'unità.
  
3.  Eseguire lo script seguente per pubblicare il certificato CA nella cartella server Web:
  
    Cscript //job:PublishRootCertstoIIS
  
    C:\\MSSScripts\\CA\_Operations.wsf
  
    (il comando si trova su due righe per esigenze di visualizzazione, ma deve essere digitato su una sola riga).
  
4.  Eseguire lo script seguente per pubblicare il o i CRL CA nella cartella server Web:
  
    Cscript //job:PublishRootCRLstoIIS
  
    C:\\MSSScripts\\CA\_Operations.wsf
  
    (il comando si trova su due righe per esigenze di visualizzazione, ma deve essere digitato su una sola riga).
  
##### Verifica della pubblicazione del certificato della CA principale
  
È necessario verificare che la pubblicazione del certificato della CA principale sia avvenuta correttamente. Per eseguire tale procedura, è necessario accedere a un computer membro del dominio connesso alla rete utilizzando un account di dominio valido.
  
**Nota:** può essere necessario attendere la replica di Active Directory. Avvalersi del comando certutil -pulse per forzare il download del certificato CA principale, prima di verificarne la pubblicazione.
  
**Per verificare la pubblicazione del certificato della CA principale**
  
1.  Per verificare la pubblicazione del certificato della CA nell'archivio principale attendibile, eseguire il comando seguente:
  
    certutil -viewstore -enterprise Root
  
2.  Il certificato deve essere visualizzato. Verificare che i valori **Autorità emittente** e **Oggetto** corrispondano a quelli configurati per il nome della CA principale e che la data **Valido dal** sia quella odierna.
  
3.  Per verificare la pubblicazione del CRL della CA principale nella directory, eseguire il comando seguente, sostituendo le voci in corsivo con i valori utilizzati per l'installazione (nome comune CA, nome host breve CA e DN del dominio principale dell'insieme di strutture Active Directory):
  
    certutil -store -enterprise "ldap:///cn=WoodGrove Bank Root CA,cn=HQ-CA-01,cn=CDP,CN=Public Key Services,CN=Services,CN=Configuration,DC=woodgrovebank,DC=com?certificateRevocationList?base?objectClass=crlDistributionPoint"
  
    (il comando si trova su due righe per esigenze di visualizzazione, ma deve essere digitato su una sola riga).
  
4.  Il risultato deve essere simile al seguente. Verificare che il valore **Autorità emittente** corrisponda al nome configurato per la CA principale:
  
    ================ CRL 0 ================
  
    Autorità emittente:    CN=WoodGrove Bank Root CA,DC=woodgrovebank,DC=com
  
    Versione CA: V1.0
  
    Numero CRL: Numero CRL=1
  
    CRL Hash(sha1): 73 03 a1 c7 5f a3 c3 f9 8a 09 d0 3c b5 09 00 9c b5 a3 de fe
  
    CertUtil: -store command completed successfully.
  
5.  Per verificare la pubblicazione del certificato CA nel server Web, immettere l'URL seguente in un browser, sostituendo le voci in corsivo con i valori utilizzati nella propria organizzazione:
  
    http://*www.woodgrovebank.com*/pki/*HQ-CA-01\_WoodGrove Bank Root CA*.crt
  
    **Nota:** può essere necessario utilizzare il nome DNS completo del server CA nel nome file del certificato (vale a dire, *HQ-CA-01*.*woodgrovebank.com\_WoodGrove Bank Root CA*.crt invece del nome sopra riportato).
  
6.  Verrà richiesto di aprire o salvare il file. Aprirlo e verificare che venga visualizzato il certificato della CA principale.
  
7.  Per verificare la pubblicazione del CRL della CA principale nel server Web, immettere l'URL seguente in un browser, sostituendo le voci in corsivo con i valori utilizzati nella propria organizzazione:
  
    http://*www.woodgrovebank.com*/pki/*WoodGrove Bank Root CA*.crl
  
8.  Verrà richiesto di aprire o salvare il file. Aprirlo e verificare che venga visualizzato il CRL della CA principale.
  
    **Nota:** se il certificato CA è stato rinnovato o sono stati rilasciati più CRL, è possibile che nell'output di questi comandi vengano visualizzati numeri di versione differenti.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Installazione e configurazione della CA di emissione
  
In questa sezione viene descritto come installare e configurare Servizi certificati nel server CA di emissione. Durante l'installazione, questa CA, la CA principale, Active Directory e il server Web interagiscono in modo complesso. Tali interazioni sono mostrate nel seguente diagramma, a cui può essere utile fare riferimento durante la consultazione di questa sezione.
  
[![](images/Dd536188.07fig7-2(it-it,TechNet.10).gif "Figura 7.2. Interazione tra CA, Active Directory e server Web durante l'installazione della CA di emissione")](https://technet.microsoft.com/it-it/dd536188.07fig7-2_big(it-it,technet.10).gif)
  
**Figura 7.2. Interazione tra CA, Active Directory e server Web durante l'installazione della CA di emissione**
  
Le interazioni principali tra i diversi sistemi durante l'installazione della CA di emissione sono illustrate nel diagramma di flusso Tali interazioni consistono in:
  
1.  Pubblicazione del certificato della CA principale e del CRL in Active Directory.
  
2.  Pubblicazione del certificato della CA principale e del CRL nel server Web.
  
3.  Installazione del software Servizi certificati che genera una richiesta di certificato da inoltrare alla CA principale sul disco. Il certificato relativo a tale richiesta viene rilasciato presso la CA principale.
  
4.  Installazione del certificato della CA di emissione.
  
5.  Pubblicazione del certificato della CA di emissione e del CRL nel server Web.
  
    **Nota:** i passaggi 1 e 2 sono stati illustrati nella sezione precedente, "Pubblicazione del certificato della CA principale". Il passaggio contrassegnato da una X nel diagramma si verifica automaticamente nell'ambito della procedura di configurazione dei valori CRL e AIA nella CA durante l'attività di configurazione delle proprietà della CA di emissione. Gli altri passaggi vengono descritti in questa sezione.
  
#### Preparazione del file Capolicy.inf per la CA di emissione
  
Il file CAPolicy.inf non è indispensabile per la CA di emissione, tuttavia, ne sarà necessario uno se si desidera modificare le dimensioni della chiave utilizzata dalla CA. È necessario creare il file Capolicy.inf prima di impostare la CA di emissione, sebbene sia possibile aggiungerne uno in seguito e rinnovare il certificato CA. Questo file specifica le caratteristiche del certificato CA, ad esempio la lunghezza della chiave e la CPS (se ne è stata creata una).
  
**Per creare il file CAPolicy.inf**
  
1.  Immettere il testo seguente in un editor di testi, ad esempio Blocco note.
  
    <codesnippet language displaylanguage containsmarkup="false">\[Version\] Signature= "$Windows NT$" \[Certsrv\_Server\] RenewalKeyLength=2048   
```
  
2.  Se è stata definita una CPS per la CA, includere quanto segue nel file Capolicy.inf (è necessario sostituire tutte le voci in corsivo con i valori della propria organizzazione):
  
    <codesnippet language displaylanguage containsmarkup="false">\[CAPolicy\] Policies=WoodGrove Bank Issuing CA 1 CPS \[WoodGrove Bank Issuing CA 1 CPS\] OID=your.Orgs.OID URL = "http://www.woodgrovebank.com/YourCPSPage.htm"   
```
  
    **Nota:** vedere la sezione "Creazione di una dichiarazione delle procedure di certificazione" nel capitolo 4, "Progettazione dell’infrastruttura a chiave pubblica (PKI)," per ulteriori informazioni sulla CPS e sui casi in cui è opportuno crearne una. La CPS è un documento legale e non un elemento tecnico, pertanto, bisogna essere certi che sia realmente necessaria prima di configurarla nella CA.
  
3.  Salvare il file come %*windir%*Capolicy.inf (o sostituire %windir% con il percorso assoluto della cartella in cui Windows è installato, ad esempio C:\\Windows). È necessario essere un amministratore locale o disporre delle autorizzazioni di scrittura nella cartella di Windows per completare questo passaggio.
  
#### Installazione dei componenti software di Servizi certificati
  
Usare Aggiunta guidata componenti di Windows per installare i componenti software della CA. È opportuno ricordare che, per completare l'installazione, è necessario disporre del supporto di installazione (CD) di Windows Server 2003.
  
**Per installare Servizi certificati**
  
1.  Accedere al server come membro del gruppo Amministratori organizzazione del dominio ed eseguire Gestione componenti facoltativi (oppure, selezionare **Installazione applicazioni**/**Componenti di Windows** dal Pannello di controllo):
  
    sysocmgr /i:sysoc.inf
  
    **Nota:** per completare la prima parte dell'installazione, è necessario essere membro solo del gruppo Amministratori locale. Nella procedura di seguito descritta per l'installazione del certificato della CA, occorre invece essere membro anche del gruppo Amministratori PKI dell'organizzazione (o Amministratori organizzazione).
  
2.  Selezionare il componente Servizi certificati (fare clic su **OK** per eliminare il messaggio di avviso relativo alla ridenominazione).
  
3.  Selezionare il tipo di CA come **CA globale (enterprise) subordinata**, accertandosi di aver selezionato la casella di controllo **Utilizzare impostazioni personalizzate**.
  
4.  Nella finestra di dialogo **Coppia di chiavi pubblica e privata**, lasciare le impostazioni predefinite, eccetto la lunghezza della chiave, che deve essere impostata su **2048** bit. Il tipo provider deve essere **Microsoft Strong Cryptographic Provider**.
  
5.  Immettere le informazioni di identificazione dell'autorità di certificazione nel modo seguente:
  
    -   Nome comune CA: *WoodGrove Bank Issuing CA 1* 
  
    -   Suffisso del nome distinto: *DC=woodgrovebank,DC=com*  
        (il nome principale dell'insieme di strutture Active Directory dell'organizzazione)
  
    -   Periodo di validità: determinato dalla CA padre
  
        **Nota:** se una CA è stata installata precedentemente nel computer, viene visualizzato un messaggio di avviso in cui si richiede di confermare se sovrascrivere la chiave privata dell'installazione precedente. Verificare se la chiave può essere eliminata prima di procedere. In caso di dubbi, annullare la procedura di installazione ed eseguire il backup delle informazioni sulla chiave esistente tramite un backup di sistema o un backup del certificato CA e della chiave privata esistenti; vedere le relative procedure nel capitolo 11, "Gestione dell'infrastruttura a chiave pubblica".
  
6.  Il CSP genera la coppia di chiavi, che viene memorizzata nell'archivio delle chiavi del computer locale.
  
7.  Immettere i percorsi del database dei certificati, dei registri del database e della cartella di configurazione nel modo seguente.
  
    -   Database dei certificati: **D:\\CertLog**
  
    -   Registro database dei certificati: **%windir%\\System32\\CertLog**
  
    -   Cartella condivisa: Disattivata
  
    Per garantire prestazioni e capacità di recupero, memorizzare sempre il database CA e i registri su volumi fisicamente separati (se il database risulta danneggiato per un qualsiasi motivo, si può usare l'ultimo backup e i relativi registri per ripristinare la CA al momento immediatamente precedente al verificarsi dell'errore). È necessario posizionare il database dei certificati e i relativi registri nelle unità NTFS locali.
  
8.  Copiare il file di richiesta del certificato su disco. La richiesta di certificato viene generata e memorizzata nel percorso della cartella condivisa. Copiare il file *HQ-CA-02.woodgrovebank.com*\_*WoodGrove Bank Issuing CA 1.req* nel disco floppy ed etichettarlo **Transfer-\[***HQ-CA-02***\]**.
  
    Gestione componenti facoltativi installa quindi i componenti di Servizi certificati. Sarà richiesto il supporto di installazione (CD) di Windows Server 2003.
  
9.  Fare clic su **OK** per eliminare l'avviso relativo a IIS e continuare l'installazione fino al termine. La procedura di installazione guidata visualizzerà un avviso in cui si informa l'utente che deve ottenere il certificato dalla CA padre per continuare.
  
    **Note:**   
    verrà visualizzato un avviso durante le ultime fasi dell'installazione, in cui si informa che la CA non può essere aggiunta al **gruppo Accesso compatibile precedente a Windows 2000**. Tenerne conto solo se è necessario utilizzare la funzione di restrizione di gestione certificati di Servizi certificati, altrimenti, richiedere all'amministratore del dominio di aggiungere l'account del computer della CA al gruppo.  
    Servizi certificati non viene avviato fino a quando la richiesta di certificato non viene elaborata dalla CA principale e il certificato non viene rilasciato e installato nella CA.
  
#### Invio della richiesta di certificato alla CA principale
  
È necessario inviare in seguito la richiesta di certificato della CA di emissione alla CA principale in modo che possa essere firmata e il certificato possa essere rilasciato alla CA di emissione.
  
**Per inviare la richiesta di certificato alla CA principale**
  
1.  Accedere alla CA principale come membro del gruppo Responsabili certificazione locale.
  
2.  Dalla console di gestione Autorità di certificazione, nel menu **Attività della CA**, selezionare **Invia nuova richiesta**, quindi inviare la richiesta trasferita dalla CA di emissione (sul disco etichettato **Transfer-\[***HQ-CA-02***\]** ).
  
    **Nota:** se l'installazione di una CA precedente non è riuscita e viene ripetuta, non riutilizzare mai il file di richiesta, in quanto è associato alla chiave precedente e non alla CA corrente che si sta installando.
  
3.  La CA principale richiede che tutte le richieste vengano approvate manualmente. Individuare la richiesta nel contenitore Richieste in sospeso della console MMC dell'autorità di certificazione, verificare che il campo **Nome comune** contenga il nome della CA di emissione, quindi approvare la richiesta facendo clic con il pulsante destro del mouse sulla richiesta e selezionando **Emetti**.
  
4.  Individuare il certificato appena emesso nel contenitore Certificati emessi e aprirlo.
  
5.  Verificare che i dettagli del certificato siano corretti, esportare quindi il certificato in un file facendo clic su **Copia su file** e salvarlo con il nome PKCS\#7 (selezionare l'opzione che consente di includere tutti i certificati possibili nella catena) sul disco floppy etichettato **Transfer-\[***HQ-CA-02***\]** (per il rinvio alla CA di emissione).
  
#### Installazione del certificato della CA di emissione
  
Le attività di questa sezione garantiscono che le informazioni sulla CA principale pubblicate precedentemente in Active Directory possano essere scaricate nella CA di emissione. Il certificato della CA di emissione può essere quindi installato nella CA.
  
##### Aggiornamento del certificato nella CA di emissione
  
Il certificato della CA principale è stato pubblicato precedentemente nell'archivio principale attendibile di Active Directory. È necessario ora assicurare che la CA di emissione abbia scaricato le informazioni e abbia inserito il certificato nel proprio archivio principale.
  
**Per aggiornare le informazioni sulla relazione di trust del certificato nella CA di emissione**
  
1.  Accedere alla CA di emissione come amministratore locale.
  
2.  Al prompt dei comandi, eseguire:
  
    certutil –pulse
  
Questo comando forzerà il download delle informazioni sul nuovo certificato principale attendibile dalla directory e inserirà il certificato nell'archivio principale attendibile locale.
  
**Nota:** questa procedura non è indispensabile, in quanto l'ultima fase di installazione del certificato nella CA inserisce automaticamente il certificato della CA principale nell'archivio principale attendibile locale. Tuttavia, questo passaggio consente di verificare che le precedenti procedure per la pubblicazione in Active Directory siano state eseguite correttamente. La riuscita della pubblicazione è importante perché è in questo modo che tutti i client del dominio ricevono le informazioni sulla relazione di trust relativa alle CA principale ed emittente.
  
**Per verificare che il download delle informazioni sulla relazione di trust della CA principale da Active Directory è riuscito**
  
1.  Eseguire mmc.exe e aggiungere lo snap-in **Certificati**.
  
2.  Selezionare **Account del computer** come archivio certificati da gestire.
  
3.  Verificare che il certificato CA principale si trovi nella cartella Autorità di certificazione principale attendibili (i certificati sono elencati in base al nome breve dell'oggetto CA, l'elemento CN).
  
##### Installazione del certificato
  
La risposta con la firma (il pacchetto PKCS\#7 contenente il certificato) inviata dalla CA principale può essere ora installata nella CA di emissione. Per pubblicare il certificato CA nell'archivio NTAuth di Active Directory (che identifica la CA come CA dell'organizzazione), è necessario installare il certificato CA utilizzando un account che sia membro *sia* del gruppo Amministratori PKI dell'organizzazione, sia del gruppo Amministratori locale. Il primo gruppo dispone dei diritti per pubblicare il certificato nella directory, mentre il secondo dispone dei diritti per installare il certificato sul server della CA. Se si sta utilizzando il modello di amministrazione semplice suggerito in precedenza, il ruolo AmminCA è un membro di questi gruppi.
  
**Per installare il certificato della CA di emissione**
  
1.  Accedere alla CA di emissione utilizzando un account membro sia del gruppo Amministratori PKI dell'organizzazione sia del gruppo Amministratori locale.
  
2.  Inserire il disco (**Transfer-\[***HQ-CA-02***\]**) con il certificato salvato rilasciato dalla CA principale.
  
3.  Dal menu **Attività della CA**, nella console di gestione dell'autorità di certificazione,  selezionare **Installa certificato** e installare il certificato della CA di emissione scaricandolo dal disco.
  
La CA deve ora avviarsi.
  
#### Verifica dell'installazione del certificato della CA di emissione
  
È possibile verificare il completamento dell'installazione di Servizi certificati nel modo seguente:
  
**Per verificare l'installazione del certificato della CA di emissione**
  
1.  Aprire la console di gestione dell'autorità di certificazione. Verificare che sia stato avviato Servizi certificati e che sia possibile visualizzare le proprietà della CA.
  
2.  Nella scheda **Generale**, selezionare il certificato della CA (o **Certificato \#0** se è visualizzato più di un certificato), quindi fare clic su **Visualizza certificato**.
  
3.  Nella scheda **Dettagli** del certificato della CA, verificare che i valori visualizzati corrispondano a quelli descritti nella tabella seguente.
  
    **Tabella 7.22. Proprietà ed estensioni del certificato della CA di emissione**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Attributo del certificato</th>
    <th style="border:1px solid black;" >Impostazione necessaria</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Autorità emittente</td>
    <td style="border:1px solid black;">Nome comune CA principale (più suffisso DN)</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Oggetto</td>
    <td style="border:1px solid black;">Nome comune CA di emissione (più suffisso DN)</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Non prima - Non dopo</td>
    <td style="border:1px solid black;">8 anni</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Lunghezza della chiave pubblica</td>
    <td style="border:1px solid black;">2048 bit</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Utilizzo della chiave</td>
    <td style="border:1px solid black;">Firma digitale, Firma certificato, Firma CRL non in linea, Firma CRL (86)</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Restrizioni di base (critiche)</td>
    <td style="border:1px solid black;">Tipo soggetto=CA
    Limite di lunghezza percorso=Nessuno</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Punti di distribuzione CRL</td>
    <td style="border:1px solid black;">2 voci — URL HTTP ed LDAP</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Accesso alle informazioni dell'autorità</td>
    <td style="border:1px solid black;">2 voci — URL HTTP ed LDAP</td>
    </tr>
    </tbody>
    </table>
  
    La presenza del tipo di oggetto Restrizioni di base è molto importante: questo valore distingue un certificato CA dal certificato di un'entità finale. Inoltre, verrà elencata un'altra estensione, **Identificativo chiave dell'autorità**, che non era inclusa nel certificato della CA principale. Questo valore deve corrispondere a **Identificatore della chiave dell'oggetto** del certificato della CA principale.
  
    Se uno dei valori precedenti non è quello previsto, è consigliabile eseguire nuovamente l'installazione di Servizi certificati.
  
    **Nota:** se è necessario eseguire nuovamente l'installazione di Servizi certificati, verrà visualizzato un avviso per informare che la chiave privata esiste già. Nel caso in cui non sia stato rilasciato alcun certificato utilizzando questa chiave, è possibile ignorare l'avviso e generare una nuova chiave. Se la CA ha già rilasciato certificati diversi dai certificati di prova, non reinstallare Servizi certificati fino a quando non è stato eseguito in modo sicuro il backup della chiave e del certificato precedenti (questa procedura è descritta nel capitolo 11, "Gestione dell'infrastruttura a chiave pubblica").
  
4.  Verificare nella scheda **Percorso certificazione** se il certificato della CA di emissione è collegato correttamente alla CA principale.
  
5.  È possibile visualizzare inoltre il registro di installazione di Servizi certificati (%systemroot%\\certocm.log) per eseguire ulteriori verifiche o agevolare la risoluzione dei problemi in caso di errori di installazione.
  
#### Configurazione delle proprietà della CA di emissione
  
La configurazione della CA applica una serie di parametri specifici dell'ambiente. I valori di tali parametri sono documentati nella precedente sezione "Foglio di lavoro per la pianificazione di Servizi certificati" di questo capitolo. Questa procedura consente di configurare le proprietà della CA descritte nella tabella seguente.
  
**Tabella 7.23. Proprietà della CA da configurare**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Proprietà della CA</th>
<th style="border:1px solid black;" >Descrizione dell'impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">URL dei punti di distribuzione CRL</td>
<td style="border:1px solid black;">Specifica i percorsi HTTP, LDAP e FILE dai quali è possibile ottenere un CRL aggiornato.
Il percorso FILE è una cartella locale ed è utilizzato dalla CA solo per memorizzare i CRL che rilascia; nei certificati rilasciati, sono inclusi solo i percorsi LDAP e HTTP.
L'URL LDAP è elencato in sequenza prima dell'URL HTTP, in modo che i controller di dominio locali siano la destinazione preferita del download dei CRL; vedere, tuttavia, la nota riportata dopo la tabella.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">URL AIA</td>
<td style="border:1px solid black;">I percorsi dai quali è possibile ottenere i certificati CA
Come con i CDP, il percorso file viene utilizzato solo per la pubblicazione del certificato della CA e l'URL LDAP ha la priorità sull'URL HTTP; vedere, tuttavia, la nota riportata dopo la tabella.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo di validità</td>
<td style="border:1px solid black;">Il periodo di validità massimo per i certificati rilasciati (che differisce dal periodo di validità del certificato CA stesso, impostato nel file CAPolicy.inf o dalla CA padre).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo CRL</td>
<td style="border:1px solid black;">Frequenza di pubblicazione del CRL.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Tempo di sovrapposizione CRL</td>
<td style="border:1px solid black;">Il tempo di sovrapposizione tra la pubblicazione di un nuovo CRL e la scadenza del CRL precedente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo Delta-CRL</td>
<td style="border:1px solid black;">Frequenza di pubblicazione Delta-CRL.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Sovrapposizione Delta-CRL</td>
<td style="border:1px solid black;">Il tempo di sovrapposizione tra la pubblicazione di un nuovo CRL e la scadenza del CRL precedente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllo CA</td>
<td style="border:1px solid black;">Impostazioni di controllo della CA. Tutti i controlli sono attivati per impostazione predefinita.</td>
</tr>
</tbody>
</table>
  
**Importante:** se occorre supporto per client non appartenenti al dominio (come illustrato nel capitolo 4, "Progettazione dell’infrastruttura a chiave pubblica"), è necessario modificare l'ordine delle voci CDP e AIA, in modo che la voce HTTP abbia maggiore priorità. Per cambiare tale ordine, occorre modificare lo script di configurazione della CA (ca\_setup.vbs) oppure usare la MMC della CA per modificare manualmente le voci CDP e AIA. Poiché gli URL LDAP funzionano in modo affidabile solo per i client di un dominio, si può decidere di usare solo URL HTTP. In questo caso, occorre accertarsi che i server Web su cui risiedono i punti di pubblicazione HTTP AIA e CDP siano resistenti ad eventuali attacchi.
  
**Per configurare le proprietà della CA di emissione**
  
1.  Accedere al server CA come membro del gruppo Amministratori locale.
  
2.  È necessario personalizzare lo script C:\\MSSScripts\\pkiparams.vbs con le impostazioni specifiche dell'organizzazione quando si configura la CA principale. Replicare inoltre le modifiche apportate nella copia di C:\\MSSScripts\\pkiparams.vbs installata nella CA di emissione.
  
3.  Eseguire quindi lo script seguente:
  
    Cscript //job:IssCAConfig C:\\MSSScripts\\ca\_setup.wsf
  
##### Configurazione dei ruoli amministrativi
  
Per utilizzare i ruoli amministrativi nella CA (ad esempio Controllori, Responsabile certificati e così via) è necessario innanzitutto mappare ad essi i gruppi di protezione creati precedentemente.
  
**Nota:** in questa soluzione, vengono utilizzati i gruppi creati precedentemente per definire più ruoli distinti. In questo modo, sussiste la massima flessibilità nel delegare le responsabilità di gestione della CA. Tuttavia, se non è richiesto questo livello di delega, prendere in considerazione l'utilizzo del modello di gruppo di amministrazione semplificato, descritto precedentemente in questo capitolo. Tale modello consente di utilizzare un numero inferiore di account per eseguire le funzioni amministrative della CA.
  
**Per configurare i ruoli amministrati nella CA di emissione**
  
1.  Dalla console di gestione dell'autorità di certificazione, fare clic su **Proprietà** per modificare le proprietà della CA.
  
2.  Fare clic sulla scheda **Protezione** e aggiungere i gruppi di protezione locali elencati nella tabella seguente. Per ciascun gruppo aggiungere l'autorizzazione elencata.
  
    **Tabella 7.24. Autorizzazioni CA da aggiungere**

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Nome gruppo</th>
    <th style="border:1px solid black;" >Autorizzazione</th>
    <th style="border:1px solid black;" >Consenti/Nega</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Amministratori CA</td>
    <td style="border:1px solid black;">Gestione CA</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">Responsabili certificazione</td>
    <td style="border:1px solid black;">Rilascio e gestione certificati</td>
    <td style="border:1px solid black;">Consenti</td>
    </tr>
    </tbody>
    </table>
  
    **Nota:** se si desidera una separazione netta dei ruoli, è necessario rimuovere le autorizzazioni di Gestione CA dal gruppo Amministratori locale.
  
3.  Altri ruoli di protezione CA richiedono un'ulteriore configurazione, sebbene siano stati già definiti parzialmente tramite i criteri di protezione applicati precedentemente al server:
  
    -   Ai controllori CA sono stati assegnati i diritti utente Gestione protezione e Registri di controllo. Aggiungere questo gruppo al gruppo Amministratori locale.
  
    -   Al gruppo Operatori backup CA sono stati assegnati i diritti di backup e ripristino nella CA. Non sono necessarie altre configurazioni per questo gruppo.
  
#### Pubblicazione del certificato CA di emissione
  
I certificati e i CRL vengono pubblicati automaticamente dalla CA di emissione in Active Directory. La pubblicazione del certificato CA e dei CRL nei percorsi HTTP CDP e AIA, tuttavia, non è automatica; è necessario impostare un processo pianificato per garantirne l'esecuzione.
  
##### Pubblicazione del certificato della CA di emissione e dei CRL nel server Web
  
I certificati e i CRL della CA di emissione devono essere pubblicati rispettivamente nei percorsi HTTP AIA e CDP. È tecnicamente possibile configurare la CA per pubblicare direttamente i certificati e gli elenchi nella cartella server Web; inoltre, se il server Web risiede nella CA di emissione, questo processo è molto semplice. Tuttavia, tale metodo non è sempre possibile per motivi di sicurezza e di connettività di rete. Il metodo illustrato qui utilizza una tecnica semplice di copia del file che può essere estesa a diverse configurazioni.
  
**Nota:** questo metodo non è adatto per la pubblicazione diretta in server Web connessi a Internet, perché richiede connettività diretta alla rete e usa la condivisione di file di rete Windows, di solito bloccata da firewall Internet. Per pubblicare in un server Internet, utilizzare un percorso di pubblicazione intermedio, quindi utilizzare il metodo standard di pubblicazione protetta del contenuto nel server Web. È necessario tenere conto dell'effetto che l’introduzione di questa ulteriore fase potrebbe avere sull’attualità degli elenchi CRL.
  
Il certificato CA viene aggiornato molto raramente, quindi è possibile pubblicare manualmente in AIA ogni volta che il certificato CA viene rinnovato.
  
**Per pubblicare il certificato della CA di emissione**
  
1.  Accedere alla CA di emissione con un account che disponga dell’autorizzazione in scrittura alla cartella pubblicata del server Web.
  
2.  Se il server Web è un server remoto, verificare che la cartella sia condivisa. Registrare il percorso UNC della cartella condivisa.
  
3.  Se il server Web è lo stesso server della CA, registrare il percorso locale della cartella.
  
4.  Aggiornare il parametro WWW\_REMOTE\_PUB\_PATH in C:\\MSSScripts\\PKIParams.vbs in modo che corrisponda al percorso di destinazione della cartella server Web (il valore predefinito è il percorso locale C:\\CAWWWPub).
  
5.  Eseguire il seguente comando per pubblicare il certificato CA nel server Web:
  
    Cscript //job:PublishIssCertsToIIS
  
    C:\\MSSScripts\\CA\_Operations.wsf
  
    (il comando si trova su due righe per esigenze di visualizzazione, ma deve essere digitato su una sola riga).
  
I CRL vengono rilasciati dalla CA di emissione a intervalli molto più regolari, ogni giorno oppure ogni ora nel caso di Delta-CRL, pertanto, è necessario un metodo automatico di replica nel server Web.
  
**Per automatizzare la pubblicazione di CRL**
  
1.  Accedere alla CA di emissione con un account membro del gruppo Amministratori locale.
  
2.  Controllare che la cartella del server Web sia accessibile, come condivisione remota o percorso locale, da questo server.
  
3.  Se il server Web è in una condivisione remota, assegnare alla CA di emissione l'accesso in scrittura alla cartella del file system (accesso **Modifica**) e alla condivisione (accesso **Cambia**). Se il server Web è membro di un insieme di strutture, è possibile utilizzare il gruppo Autori certificazione per assegnare l'accesso.  In questo modo si garantisce che qualsiasi CA dell'organizzazione disponga delle autorizzazioni necessarie per pubblicare i certificati e i CRL in questa cartella. Non è necessario modificare le autorizzazioni nel server Web (vedere la sezione precedente relativa alla configurazione di IIS per la pubblicazione AIA e CDP).
  
4.  Creare un processo programmato di copia dei CRL utilizzando il seguente comando:
  
    schtasks /create /tn "Publish CRLs" /tr "cscript.exe
  
    //job:PublishIssCRLsToIIS C:\\MSSScripts\\CA\_Operations.wsf"
  
    /sc Hourly /ru "System"
  
    (il comando si trova su due righe per esigenze di visualizzazione, ma deve essere digitato su una sola riga).
  
    **Nota:** questa procedura consente di creare un processo programmato, che avverrà ogni ora, per la pubblicazione di CRL dalla CA al server Web. Tale frequenza è sufficiente per una pianificazione che preveda la pubblicazione di Delta-CRL una volta o anche due volte al giorno. Se la pianificazione di pubblicazione CRL è più frequente, è necessario eseguire il processo pianificato a intervalli più brevi. In linea generale, è consigliabile una pianificazione del processo pari al 5-10% circa della pianificazione di Delta-CRL.
  
##### Verifica della pubblicazione del certificato della CA di emissione
  
È necessario verificare che la pubblicazione del certificato della CA di emissione sia avvenuta correttamente. Per eseguire tale procedura è necessario accedere a un computer membro del dominio connesso alla rete utilizzando un account di dominio valido.
  
**Per verificare la pubblicazione del certificato della CA di emissione**
  
1.  Per verificare la pubblicazione del certificato CA nell'archivio della CA intermedia, eseguire il comando seguente:
  
    certutil -viewstore -enterprise CA
  
2.  Vengono visualizzati due certificati: uno per la CA principale e l'altro per la CA di emissione. Fare doppio clic sul certificato della CA di emissione e verificare che il nome **Oggetto** corrisponda a quello configurato per la CA di emissione e che la data **Valido dal** sia quella odierna.
  
3.  Per verificare la pubblicazione del certificato CA nell'archivio CA NTAuth (tutte le CA dell'organizzazione sono pubblicate qui), eseguire il comando seguente:
  
    certutil -viewstore -enterprise NTAuth
  
    Viene visualizzato lo stesso certificato per la CA di emissione.
  
4.  Per verificare la pubblicazione del CRL della CA di emissione nella directory, eseguire il comando seguente, sostituendo le voci in corsivo con i valori utilizzati per l'installazione (nome comune CA, nome host CA breve e DN del dominio principale dell'insieme di strutture Active Directory):
  
    certutil -store -enterprise "ldap:///cn=*Woodgrove Bank Issuing CA 1*,cn=*HQ-CA-02*,cn=CDP,CN=Public Key Services, CN=Services,CN=Configuration,DC=*woodgrovebank*,DC=*com*?certificateRevocationList?base?objectClass= cRlDistributionPoint"
  
    (il comando si trova su due righe per esigenze di visualizzazione, ma deve essere digitato su una sola riga).
  
5.  Il risultato deve essere simile al seguente. Verificare che il valore **Autorità emittente** corrisponda al nome configurato per il certificato della CA di emissione:
  
    ================ CRL 0 ================
  
    Autorità emittente: CN= WoodGrove Bank Issuing CA,DC=woodgrovebank,DC=com
  
    Versione CA: V1.0
  
    Numero CRL: Numero CRL=1
  
    CRL Hash(sha1): 73 03 a1 c7 5f a3 c3 f9 8a 09 d0 3c b5 09 00 9c b5 a3 de fe
  
    CertUtil: -store command completed successfully.
  
6.  Per verificare la pubblicazione del certificato CA nel server Web, immettere l'URL seguente in un browser, sostituendo le voci in corsivo con i valori utilizzati nella propria installazione:
  
    http://*www.woodgrovebank.com*/pki/*HQ-CA-02\_WoodGrove Bank Issuing CA 1*.crt
  
7.  Verrà richiesto di aprire o salvare il file. Aprirlo e verificare che venga visualizzato il certificato CA della CA di emissione.
  
8.  Per verificare la pubblicazione del CRL della CA di emissione nel server Web, immettere l'URL seguente in un browser, sostituendo le voci in corsivo con i valori utilizzati nella propria installazione:
  
    http://*www.woodgrovebank.com*/pki/*WoodGrove Bank Issuing CA 1*.crl
  
9.  Verrà richiesto di aprire o salvare il file. Aprirlo e verificare che venga visualizzato il CRL della CA principale.
  
    **Nota:** se il certificato CA è stato rinnovato o sono stati rilasciati più CRL, è possibile che nell'output di questi comandi vengano visualizzati numeri di versione differenti.
  
#### Verifica della registrazione dei certificati
  
È necessario verificare se è possibile registrare i certificati della CA di emissione.
  
**Per verificare la registrazione dei certificati**
  
1.  Accedere a un computer membro dello stesso dominio della CA di emissione. Utilizzare un account di dominio.
  
2.  Aprire lo snap-in MMC Certificati per l'utente corrente (sarà necessario aggiungere questo snap-in a una console MMC vuota selezionando **Aggiungi/Rimuovi snap-in** poiché non ne è disponibile uno predefinito).
  
3.  Fare clic con il pulsante destro del mouse sulla cartella personale e selezionare **Richiedi nuovo certificato** dal sottomenu **Tutte le attività**.
  
4.  Verrà richiesto di scegliere il tipo di certificato da uno specifico elenco: scegliere il tipo **Utente**. Non selezionare la casella di controllo **Opzioni avanzate**.
  
5.  Assegnare al certificato un nome facile e riconoscibile, ad esempio **Verifica CA di emissione**.
  
6.  Fare clic su **Fine** per registrare il certificato.
  
7.  Passare alla sottocartella Certificati della cartella personale. In questa cartella deve comparire il certificato **Verifica CA di emissione** (può essere necessario aggiornare prima l'archivio: fare clic con il pulsante destro del mouse sull'oggetto principale **Certificati - Utente corrente** nel riquadro destro della console MMC, quindi scegliere **Aggiorna**).
  
Se il test di verifica non ha esito positivo, cioè il certificato non viene visualizzato, è consigliabile ripetere le operazioni illustrate in questo capitolo e risolvere i problemi segnalati. In caso di problemi, consultare la sezione "Risoluzione dei problemi" del capitolo 11, "Gestione dell'infrastruttura a chiave pubblica".
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione post-creazione
  
Dopo aver creato la CA principale ed emittente per la propria organizzazione, è necessario completare ancora alcune attività di configurazione illustrate in questa sezione.
  
#### Configurazione dei modelli di certificato
  
La maggior parte di tali attività consiste nella configurazione dei tipi di certificato che le CA possono rilasciare, delle modalità di controllo del rilascio e dei destinatari dei certificati rilasciati.
  
##### Rimozione dei modelli indesiderati dalla CA di emissione
  
Fino a quando non si presenta l'esigenza di un nuovo certificato, è buona regola rimuovere il corrispondente modello dalla configurazione della CA, in modo da evitare l'involontaria emissione di certificati. I modelli restano comunque sempre disponibili nella rispettiva directory e, all'occorrenza, possono sempre essere nuovamente aggiunti alla configurazione.
  
**Per rimuovere i modelli indesiderati dalla CA di emissione**
  
1.  Accedere come membro del gruppo Amministratori CA del dominio.
  
2.  Dalla console di gestione dell'autorità di certificazione, selezionare il contenitore Modelli di certificato.
  
3.  Rimuovere i tipi di modello seguenti:
  
    -   Agente recupero dati EFS
  
    -   EFS di base
  
    -   Server Web
  
    -   Autenticazione
  
    -   Utente
  
    -   Autorità di certificazione subordinata
  
    -   Amministratore
  
        **Nota:** con questa procedura si rimuovono tutti i modelli dalla CA di emissione, eccetto quelli relativi a Controller di dominio, Autenticazione del controller di dominio e Replica directory via posta elettronica. I controller di dominio di Windows 2000 utilizzano certificati Controller di dominio per abilitare l'accesso con smart card e per la replica SMTP (Simple Mail Transfer Protocol) di Active Directory. I controller di dominio di Windows Server 2003 utilizzano certificati Autenticazione del controller di dominio per supportare l'accesso con smart card e la protezione di LDAP e il certificato Replica directory via posta elettronica per la replica SMTP di Active Directory.  
        Tutti i certificati rimossi possono essere in seguito nuovamente aggiunti all'occorrenza. Nel frattempo, è consigliabile consentire il rilascio solo dei tipi di certificato selezionati.
  
##### Creazione e gestione dei modelli di certificato
  
I modelli di certificato dell'organizzazione possono essere gestiti e utilizzati in modo efficace attraverso i gruppi di protezione. Tali gruppi possono scegliere e controllare gli utenti autorizzati a modificare le proprietà di ciascun modello e gli utenti autorizzati a registrare certificati di quel tipo.
  
**Nota:** i gruppi di amministrazione dei modelli sono utili se esiste la possibilità di delegare ad altri amministratori il controllo sui modelli. Se la struttura di amministrazione della PKI non è sufficientemente ampia o complessa, questa funzionalità probabilmente non sarà necessaria. In questo caso, solo i membri del gruppo incorporato Amministratori organizzazione e del gruppo Amministratori PKI dell'organizzazione (creato nell'ambito di questa soluzione) saranno in grado di gestire i modelli di certificato.
  
Per istruzioni sulla creazione e la gestione dei gruppi di amministrazione dei modelli di certificato, vedere le procedure operative descritte nel capitolo 11, "Gestione dell'infrastruttura a chiave pubblica".
  
Per istruzioni su come creare modelli di certificato specifici per questa soluzione, vedere la sezione "Configurazione e distribuzione di certificati di autenticazione WLAN" del capitolo 9, "Implementazione dell'infrastruttura per la protezione di reti LAN senza fili".
  
Per istruzioni generali su come creare e modificare i modelli di certificato, vedere la sezione della documentazione del prodotto relativa alla gestione dei modelli di certificato e il documento tecnico, *Implementing and Administering Certificate Templates in Windows Server 2003* (vedere i riferimenti alla fine del capitolo).
  
##### Gestione della registrazione dei certificati
  
I gruppi di registrazione del modello semplificano la gestione degli utenti o dei computer che possono registrare un tipo specifico di certificato. A tale scopo, è sufficiente aggiungere o rimuovere gli utenti desiderati da un gruppo di protezione. Il controllo sull'appartenenza al gruppo di registrazione dei modelli può essere concesso anche al personale amministrativo, nel caso in cui non si intenda consentirgli direttamente la possibilità di modificare le proprietà dei modelli di certificato.
  
Per istruzioni sulla creazione e la gestione dei gruppi di registrazione dei modelli di certificato, vedere il capitolo 11, "Gestione dell'infrastruttura a chiave pubblica".
  
#### Impostazione delle autorizzazioni per l'implementazione multidominio
  
Se si sta implementando questa soluzione in un insieme di strutture multidominio, potrebbe essere necessario emettere certificati ad utenti e computer in domini diversi dal dominio della CA stessa. In tal caso, sarà necessario modificare le autorizzazioni predefinite in modo da consentire alle CA di pubblicare i certificati correttamente in altri domini dell'insieme di strutture di Active Directory.
  
Quando si impostano le autorizzazioni di registrazione per gli utenti sulle CA e i modelli di certificato, è necessario includere espressamente gli utenti e i computer di tutti i domini in cui si desidera consentire di registrare i certificati.
  
**Per consentire la pubblicazione di certificati a utenti e computer di altri domini**
  
1.  Accedere a un membro del dominio in cui si desidera consentire la pubblicazione dei certificati. È necessario essere un membro degli amministratori del dominio o di un gruppo con diritti sufficienti a modificare le autorizzazioni sull'oggetto del dominio.
  
2.  Aprire lo snap-in Utenti e computer di Active Directory e fare clic con il pulsante destro del mouse sul nodo del dominio.
  
    **Nota:** questa operazione può essere eseguita da un altro dominio purché il proprio account disponga delle corrette autorizzazioni nel dominio di destinazione. È necessario connettersi al dominio di destinazione da Utenti e computer di Active Directory.
  
3.  Per avviare la procedura guidata di delega, fare clic su **Delega controllo**.
  
4.  Nella procedura guidata, fare clic su **Avanti**, aggiungere il gruppo Autori certificazione dal dominio in cui la CA di emissione è stata installata, quindi scegliere **Avanti**.
  
5.  Selezionare **Crea un'operazione personalizzata per eseguire la delega**, quindi fare clic su **Avanti**.
  
6.  Selezionare **Solo i seguenti oggetti** **contenuti nella cartella**.
  
7.  Scegliere gli **oggetti utente**, quindi fare clic su **Avanti**.
  
8.  Selezionare l'opzione **Proprietà**.
  
9.  Selezionare le opzioni **Read userCertificate** e **Write userCertificate**.
  
10. Fare clic su **Avanti**, quindi su **Fine**.
  
11. Ripetere i passaggi da 3 a 10, ma al passaggio 7, selezionare gli **oggetti computer** invece degli **oggetti utente**.
  
Tale procedura fa in modo che le CA dell'organizzazione abbiano l'autorizzazione a pubblicare correttamente certificati per utenti e computer del dominio.
  
#### Backup delle chiavi e dei server CA
  
Dopo aver creato la CA principale ed emittente, è necessario eseguirne il backup prima possibile, in modo da proteggere i database delle chiavi e dei certificati in caso di errore del server o danneggiamento dei dati.
  
Eseguire completamente le seguenti procedure, come descritto nel capitolo 11, "Gestione dell'infrastruttura a chiave pubblica":
  
-   "Configurazione del backup della CA di emissione"
  
-   "Configurazione ed esecuzione del backup della CA principale"
  
-   "Backup delle chiavi e dei certificati delle CA" (da eseguire per ciascuna CA)
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione dei client
  
Questa sezione descrive alcune importanti attività di configurazione dei client. Se ne illustrano solo alcune, in quanto la maggior parte delle attività relative ai client è specifica dell'applicazione che utilizza Servizi certificati, ad esempio della WLAN o della rete privata virtuale (VPN), e non di tutte le applicazioni di certificazione.
  
#### Attivazione della registrazione automatica dei certificati di utenti e computer
  
I provvedimenti descritti nella precedente sezione sulla gestione della registrazione dei certificati permettono di utilizzare i gruppi di protezione e le autorizzazioni relative ai modelli per controllare la registrazione automatica ad un elevato livello di precisione. Tuttavia, per impostazione predefinita, la funzionalità di registrazione automatica di client Windows XP è disattivata. Per attivarla, è necessario abilitare l'impostazione corretta nei criteri di gruppo. Se si utilizzano i gruppi di protezione per controllare la registrazione automatica, è possibile attivare la registrazione automatica per tutti gli utenti e i computer del dominio, nonché utilizzare il gruppo di protezione relativo alla registrazione per determinare gli utenti ammessi a ricevere ciascun tipo di certificati.
  
**Attenzione:** questa procedura consente la registrazione automatica per *tutti* i computer e gli utenti del dominio. Assicurarsi di aver rimosso i modelli predefiniti dalla CA di emissione prima di avviare questa procedura, in modo da evitare la registrazione dei certificati Computer e utenti predefiniti per ogni computer e utente del dominio. Questa procedura presume che la registrazione automatica verrà controllata automaticamente utilizzando i gruppi di protezione, come descritto nel capitolo 11, "Gestione dell'infrastruttura a chiave pubblica".
  
**Per attivare la registrazione automatica per tutti gli utenti e computer del dominio**
  
1.  Accedere utilizzando un account che disponga delle autorizzazioni a creare GPO (un membro del gruppo Proprietari creatori criteri di gruppo) e a collegarli al dominio. In alternativa, l'utente deve richiedere a un amministratore del dominio di creare e collegare il GPO e di assegnargli i diritti di lettura e scrittura su di esso.
  
2.  In Utenti e computer di Active Directory selezionare l'oggetto dominio, fare clic con il pulsante destro del mouse, quindi scegliere **Proprietà**.
  
3.  Nella scheda **Criteri gruppo,** fare clic su **Nuovo**, quindi digitare un nome per il GPO, ad esempio *Criteri PKI dominio*.
  
4.  Fare clic su **Modifica** per modificare il GPO e passare a Criteri chiave pubblica seguendo il percorso Configurazione computer\\Impostazioni di Windows\\Impostazioni di protezione.
  
5.  Nel riquadro dei dettagli, fare doppio clic su **Impostazioni registrazione automatica**.
  
6.  Assicurarsi che le voci seguenti siano selezionate:
  
    -   **Registra i certificati automaticamente**
  
    -   **Rinnova i certificati scaduti, aggiorna quelli in sospeso e rimuovi i certificati revocati**
  
    -   **Aggiorna i certificati che utilizzano modelli di certificato**
  
7.  Ripetere i passaggi 5 e 6 per le impostazioni di registrazione automatica per l'utente in Configurazione utente\\Impostazioni di Windows\\Impostazioni di protezione\\Criteri chiave pubblica.
  
8.  Chiudere il GPO.
  
9.  Assicurarsi che il GPO abbia una priorità più alta rispetto al GPO Criteri di dominio predefinito.
  
    **Note:**  
    se si dispone di un insieme di strutture Active Directory multidominio, è necessario eseguire questa procedura per ciascun dominio dell'insieme di strutture in cui si desidera attivare la registrazione automatica.  
    Se non si desidera attivare la registrazione automatica per tutti gli utenti o i computer del dominio, è possibile creare GPO collegati alle UO che contengano il sottoinsieme degli utenti e/o dei computer per cui si desidera attivare la registrazione automatica.  
    Se gli utenti non utilizzano profili comuni e si autorizza la registrazione automatica a tutti i livelli, verrà registrato un certificato per tutti gli utenti al momento del loro accesso a qualsiasi computer. Potrebbe, tuttavia, essere opportuno impedire la registrazione automatica di certificati quando amministratori e operatori accedono ai server. A questo scopo, è possibile creare un GPO da applicare a tali server, ad esempio, collegandolo all'OU dei server. Nel GPO creato, disattivare la registrazione automatica per gli utenti selezionando **Non effettuare la registrazione automatica dei certificati**. Nello stesso GPO, consentire l'elaborazione loopback attivando l'impostazione **della modalità loopback Configurazione computer\\Modelli amministrativi\\Sistema\\Criterio gruppo\\Criteri di gruppo dell'utente** e selezionando l'opzione **Sostituisci**.
  
L'attivazione della registrazione automatica del certificato è descritta inoltre dettagliatamente nei documenti elencati nella sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
Solo i client Windows XP e versioni successive supportano la registrazione automatica di entrambi i certificati utente e computer. I client Windows 2000 supportano solo la registrazione automatica di certificati per computer (sebbene alcune applicazioni, come EFS, dispongano di un proprio meccanismo di registrazione automatica per i certificati destinati ad utenti).
  
Se si sta implementando questa soluzione in un ambiente Active Directory di Windows 2000, è necessario modificare le impostazioni di registrazione automatica nei GPO da un computer che esegue Windows Server 2003 o Windows XP Professional in cui sono installati gli strumenti di amministrazione di Windows Server 2003 (Windows XP richiede un livello di Service Pack e di aggiornamenti rapidi specifico per supportare gli strumenti amministrativi di Windows Server 2003).
  
#### Configurazione dei criteri di domino dell'autorità di certificazione principale
  
In questa sezione viene descritto come stabilire quali CA commerciali principali devono essere considerate attendibili dai client dell'organizzazione e se i singoli utenti possono scegliere o meno di modificare tali CA.
  
##### Gestione dei trust di terze parti
  
I client Windows sono configurati per impostazione predefinita in modo che considerino attendibili un vasto numero di CA commerciali principali (note come baked-in-root). Per impedire agli utenti di considerare automaticamente attendibili le CA principali di terzi, consultare la procedura descritta nella sezione della guida in linea "To prevent users from trusting third-party root certification authorities with a Group Policy" o il collegamento a un articolo su questo argomento riportato nella sezione "Ulteriori informazioni".
  
**Nota:** la disattivazione delle CA principali di terzi può causare errori nelle applicazioni client; pertanto, non eseguire questa operazione senza averne prima valutato attentamente le conseguenze. Ad esempio, le connessioni dei client alla maggior parte dei siti Web pubblici protetti determineranno un errore di attendibilità.
  
È possibile eliminare alcuni dei problemi conseguenti la rimozione di tutti i trust di terzi in diversi modi:
  
-   È possibile riaggiungere in modo selettivo singole CA principali all'impostazione del criterio Autorità di certificazione principali attendibili in Criteri di gruppo.
  
-   È possibile aggiungere i certificati principali agli elenchi di certificati attendibili e distribuirli tramite l'impostazione Attendibilità per l'organizzazione di Criteri di gruppo. Questo metodo consente inoltre di controllare l'utilizzo per cui vengono ritenuti attendibili i certificati che le CA principali rilasciano. Tuttavia, poiché il supporto di client è limitato, tale metodo è consigliato solo in assenza di altre alternative.
  
-   Infine, è possibile eseguire una certificazione incrociata (o creare una relazione di trust subordinata qualificata con) delle altre autorità di certificazione. In questo modo si ottiene un controllo ancora maggiore sull'utilizzo e sui parametri dei certificati che verranno considerati attendibili nell'organizzazione.
  
L'utilizzo degli elenchi dei certificati attendibili o di una relazione di trust subordinata qualificata è il modo più sicuro per distribuire le CA principali attendibili di terzi nell'organizzazione. Per ulteriori dettagli su questo argomento, consultare il capitolo 4, "Progettazione dell’infrastruttura a chiave pubblica (PKI)".
  
##### Gestione del controllo utente sulle CA principali attendibili
  
È possibile inoltre utilizzare i criteri di gruppo per impedire agli utenti di selezionare nuove CA principali come attendibili. Questo è particolarmente importante se sono stati creati elenchi di certificati attendibili propri o relazioni di trust subordinate qualificate per controllare l'uso dei certificati di terzi nell'organizzazione. La procedura relativa all'utilizzo dei criteri di gruppo per la gestione del controllo utente sulle CA principali attendibili è disponibile nella sezione "To prevent users from selecting new root certification authorities with a Group Policy" della guida in linea oppure nel collegamento riportato nella sezione "Ulteriori informazioni".
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Se sono state eseguite tutte le procedure illustrate in questo capitolo, sono state completate le attività seguenti:
  
-   Installazione e configurazione di una CA principale non in linea
  
-   Installazione e configurazione di una CA di emissione in linea
  
-   Installazione e configurazione di un server Web per la pubblicazione di CRL e certificati delle CA
  
-   Configurazione di gruppi e utenti amministrativi per la gestione delle CA e delle informazioni di configurazione della PKI di Active Directory
  
-   Configurazione di Active Directory e dei criteri di gruppo per il supporto dell'infrastruttura PKI
  
A questo punto si è pronti per configurare le applicazioni in modo che utilizzino l'infrastruttura PKI. Tale operazione è descritta nei due successivi capitoli della guida: il capitolo 8, "Implementazione dell'infrastruttura RADIUS", e il capitolo 9, "Implementazione dell'infrastruttura per la protezione di reti LAN senza fili".
  
È necessario inoltre leggere le sezioni pertinenti del capitolo 11, "Gestione dell'infrastruttura a chiave pubblica", e assicurarsi che ne sia a conoscenza anche il personale addetto a tali operazioni. In questa guida sono contenute le informazioni essenziali per garantire il funzionamento dell'infrastruttura PKI in un ambiente protetto e affidabile.
  
#### Ulteriori informazioni
  
##### Informazioni di carattere generale sull'infrastruttura PKI e sui Servizi certificati di Windows
  
-   Per un'introduzione esauriente ai concetti di PKI e alle caratteristiche di Servizi certificati di Windows 2000, vedere [*An Introduction to the Windows 2000 Public-Key Infrastructure*](http://www.microsoft.com/technet/archive/windows2000serv/evaluate/featfunc/pkiintro.mspx) all'indirizzo http://www.microsoft.com/technet/archive/windows2000serv/  
    evaluate/featfunc/pkiintro.mspx
  
-   Per una descrizione delle funzionalità avanzate dell'infrastruttura PKI in Windows Server 2003 e Windows XP, vedere [*PKI Enhancements in Windows XP Professional and Windows Server 2003*](http://technet.microsoft.com/en-us/library/bb457034.aspx) all'indirizzo http://technet.microsoft.com/en-us/library/bb457034.aspx
  
-   Per la documentazione di riferimento del prodotto relativa ai concetti fondamentali e alle attività di amministrazione, vedere la sezione "Certificate Services" della guida in linea oppure la sezione [Public Key Infrastructure](http://technet.microsoft.com/en-us/library/cc779826.aspx) della documentazione di Windows Server 2003, disponibile all'indirizzo http://technet.microsoft.com/en-us/library/cc779826.aspx
  
##### Informazioni sugli argomenti specifici
  
-   Per ulteriori informazioni sulla distribuzione di una PKI ad un ambiente Active Directory con più insiemi di strutture, vedere la sezione ["To publish certificates in a foreign Active Directory forest"](http://technet.microsoft.com/en-us/library/cc786746.aspx) della documentazione di Windows Server 2003, disponibile all'indirizzo http://technet.microsoft.com/en-us/library/cc786746.aspx
  
-   CAPICOM può essere scaricato [dall'area di download](http://www.microsoft.com/downloads/details.aspx?displaylang=en&familyid=860ee43a-a843-462f-abb5-ff88ea5896f6) del sito Web Microsoft all'indirizzo http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=860EE43A-A843-462F-ABB5-FF88EA5896F6. In ogni caso, è consigliabile ricercare "CAPICOM" nell'area di download del sito Web Microsoft per accertarsi di individuare la versione più recente:
  
-   Per istruzioni sull'uso di Microsoft Baseline Security Analyzer (MBSA), consultare la pagina [Microsoft Baseline Security Analyzer v1.2](http://www.microsoft.com/technet/security/tools/mbsahome.mspx) all'indirizzo http://www.microsoft.com/technet/security/tools/mbsahome.mspx.
  
-   Per informazioni sui livelli funzionali del dominio Active Directory e istruzioni sul modo in cui passare da un livello all’altro, vedere le seguenti sezioni della documentazione relativa a Windows Server 2003, disponibile negli URL indicati.
  
    -   La sezione [Domain and forest functionality](http://technet.microsoft.com/en-us/library/cc759280.aspx) consultabile all'indirizzo http://technet.microsoft.com/en-us/library/cc759280.aspx descrive i diversi livelli del dominio e dell'insieme di strutture.
  
    -   La pagina dal titolo ["To raise the domain functional level"](http://technet.microsoft.com/en-us/library/cc775826.aspx) consultabile all'indirizzo http://technet.microsoft.com/en-us/library/cc775826.aspx illustra come passare dal livello del dominio a quello dell'insieme di strutture e viceversa.
  
-   Per ulteriori informazioni sullo strumento ADPrep, vedere l'articolo Q325379 della Microsoft Knowledge Base, "[How to upgrade Windows 2000 domain controllers to Windows Server 2003](http://support.microsoft.com/?kbid=325379)", all'indirizzo http://support.microsoft.com/?kbid=325379  
    e la pagina [ADPrep](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/adprep.mspx) all'indirizzo http://www.microsoft.com/technet/prodtechnol/  
    windowsserver2003/proddocs/entserver/adprep.mspx.
  
-   Per ulteriori informazioni sui requisiti del livello di patch ADPrep, vedere l'articolo Q331161 della Knowledge Base, ["Hotfixes to install on Windows 2000 domain controllers before running Adprep /Forestprep"](http://support.microsoft.com/?kbid=331161), disponibile all'indirizzo http://support.microsoft.com/?kbid=331161.
  
-   Per una completa illustrazione dei ruoli amministrativi di Servizi certificati, vedere la sezione "[Managing role-based administration](http://technet.microsoft.com/en-us/library/cc738189.aspx)" della documentazione di Windows Server 2003, disponibile all'indirizzo http://technet.microsoft.com/en-us/library/cc738189.aspx
  
-   Per ulteriori informazioni sulle impostazioni di protezione dei server e sui ruoli dei server usati nella presente guida, consultare la [*Guida per la protezione di Windows Server 2003*](http://technet.microsoft.com/it-it/library/cc163140) all'indirizzo http://technet.microsoft.com/it-it/library/cc163140
  
-   Per istruzioni generali su come creare e modificare i modelli di certificato, consultare il documento tecnico [*Implementing and Administering Certificate Templates in Windows Server 2003*](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/ws03crtm.mspx)all'indirizzo http://www.microsoft.com/technet/prodtechnol/  
    windowsserver2003/echnologies/security/ws03crtm.mspx e la sezione [Manage certificate templates for an enterprise certification authority](http://technet.microsoft.com/en-us/library/cc780765.aspx) della documentazione del prodotto, disponibile all'indirizzo http://technet.microsoft.com/en-us/library/cc780765.aspx
  
-   Per informazioni su come disattivare il trust automatico per le CA di terzi, vedere  
    ["To prevent users from trusting third-party root certification authorities with a Group Policy"](http://technet.microsoft.com/en-us/library/cc780117.aspx) all'indirizzo http://technet.microsoft.com/en-us/library/cc780117.aspx .
  
-   Per informazioni su come gestire il controllo utente sulle CA principali attendibili, vedere l'articolo  
    ["To prevent users from selecting new root certification authorities with a Group Policy"](http://technet.microsoft.com/en-us/library/cc781964.aspx) all'indirizzo http://technet.microsoft.com/en-us/library/cc781964.aspx .
  
-   Per ulteriori informazioni sulla registrazione automatica dei certificati, vedere [*Certificate Autoenrollment in Windows XP*](http://technet.microsoft.com/en-us/library/bb456981.aspx), disponibile all'indirizzo http://technet.microsoft.com/en-us/library/bb456981.aspx , e ["Checklist: Configuring certificate autoenrollment"](http://technet.microsoft.com/en-us/library/cc773385.aspx) , consultabile all'indirizzo http://www.microsoft.com/resources/documentation/  
    WindowsServ/2003/datacenter/proddocs/en-us/certsrv\_checklist\_autoenroll.asp.
  
-   Per ulteriori informazioni sulle procedure avanzate di registrazione dei certificati, vedere [Advanced Certificate Enrollment and Management](http://technet.microsoft.com/en-us/library/cc782583.aspx), consultabile all'indirizzo http://technet.microsoft.com/en-us/library/cc782583.aspx .
  
-   Per ulteriori informazioni su come gestire una PKI Windows (oltre alle informazioni contenute nel capitolo 11, "Gestione della infrastruttura a chiave pubblica"), vedere [*Windows Server 2003 PKI Operations Guide*](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/ws03pkog.mspx) all'indirizzo http://www.microsoft.com/technet/prodtechnol/  
    windowsserver2003/technologies/security/ws03pkog.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
