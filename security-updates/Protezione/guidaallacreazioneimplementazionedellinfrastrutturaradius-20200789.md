---
TOCTitle: 'Guida alla creazione - Implementazione dell''infrastruttura RADIUS'
Title: 'Guida alla creazione - Implementazione dell''infrastruttura RADIUS'
ms:assetid: 'ad283f7c-fd17-4c80-aada-4cdf79856bae'
ms:contentKeyID: 20200789
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536189(v=TechNet.10)'
---

Capitolo 8: Implementazione dell'infrastruttura RADIUS
======================================================

Pubblicato: 11 ottobre 2004 | Aggiornato: 24/11/2004

##### In questa pagina

[](#egaa)[Introduzione](#egaa)  
[](#efaa)[Foglio di lavoro per la pianificazione dell'infrastruttura RADIUS](#efaa)  
[](#eeaa)[Creazione dei propri server](#eeaa)  
[](#edaa)[Installazione e configurazione del Servizio autenticazione Internet](#edaa  
[](#ecaa)[Configurazione del server IAS primario](#ecaa)  
[](#ebaa)[Distribuzione della configurazione a più server IAS](#ebaa)  
[](#eaaa)[Riepilogo](#eaaa)  

### Introduzione

Questo capitolo contiene informazioni dettagliate relative alla creazione di un'infrastruttura RADIUS (Remote Authentication Dial-In User Service) per la protezione di reti LAN senza fili (WLAN) basata sul Servizio autenticazione Internet (IAS, Internet Authentication Service) di Microsoft® Windows Server™ 2003. Sono incluse informazioni sull'installazione e la configurazione dei server RADIUS, la preparazione del servizio directory Active Directory® e la configurazione delle impostazioni del server IAS. L'infrastruttura RADIUS verrà usata nel capitolo successivo per creare una soluzione LAN senza fili completa.

L'obiettivo di questo capitolo è di fornire una guida all'implementazione della progettazione RADIUS descritta nel capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili". Il capitolo non intende illustrare i principi generali di RADIUS o i dettagli sulle modalità di implementazione di IAS del protocollo RADIUS.

Questo capitolo è correlato ai capitoli Guida alla pianificazione di RADIUS e WLAN e Guida operativa. La Guida alla pianificazione spiega le motivazioni delle decisioni relative all'implementazione illustrate in questo capitolo e la Guida operativa descrive le attività e i processi necessari per la gestione dell'infrastruttura RADIUS. Prima di proseguire con gli argomenti del capitolo, si consiglia di leggere i capitoli relativi alla pianificazione. Prima di applicare le linee guida fornite in questo capitolo per implementare l'infrastruttura RADIUS, è opportuno inoltre leggere e comprendere le implicazioni dei requisiti di supporto nel capitolo delle istruzioni operative.

#### Prima di iniziare

Questa sezione contiene elenchi di controllo che aiutano a valutare il grado di preparazione di un'azienda in merito all'implementazione dell'infrastruttura RADIUS (in questo contesto, il termine "preparazione" si riferisce più all'aspetto logistico che a quello aziendale: le motivazioni aziendali che portano all'implementazione di questa soluzione sono trattate nei primi capitoli della Guida alla pianificazione).

##### Prima di iniziare

In particolare, è necessario conoscere i concetti di RADIUS e IAS. È inoltre consigliabile acquisire dimestichezza con Windows 2000 Server o Windows Server 2003 nelle seguenti aree:

-   Installazione del sistema operativo di Microsoft Windows®.

-   Concetti relativi ad Active Directory, tra cui la struttura e gli strumenti di Active Directory; la gestione di utenti, gruppi e altri oggetti Active Directory e l’uso dei criteri di gruppo.

-   Concetti alla base della protezione dei sistemi Windows, quali utenti, gruppi, controllo, elenchi di controllo di accesso (ACL), utilizzo dei modelli di protezione e applicazione dei modelli di protezione mediante Criteri di gruppo o strumenti della riga di comando.

-   Conoscenza degli script dei file batch. Conoscenza di Windows Scripting Host e del linguaggio Microsoft Visual Basic® Scripting Edition (VBScript) per poter trarre il massimo vantaggio dagli script forniti, ma non è essenziale.

Prima di leggere questo capitolo, è preferibile leggere anche il capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili" e comprendere a fondo l’architettura e la progettazione di questa soluzione.

##### Prerequisiti organizzativi

È consigliabile consultare altri membri della propria azienda che dovrebbero essere coinvolti nell'implementazione di questa soluzione, quali:

-   Finanziatori dell'iniziativa

-   Personale addetto al controllo e alla protezione

-   Personale addetto a progettazione, amministrazione e operazioni di Active Directory

-   Personale addetto a DNS (Domain Name System) e progettazione, amministrazione e operazioni di rete

##### Prerequisiti per l'infrastruttura IT

Per quanto riguarda l'infrastruttura IT esistente, in questo capitolo si presuppone quanto segue:

-   Esiste un'infrastruttura di dominio di Active Directory Windows Server 2003. Tutti gli utenti dell'infrastruttura RADIUS in questa soluzione devono essere membri di un dominio all'interno dello stesso insieme di strutture di Active Directory.

    **Nota:** per ulteriori informazioni sulla compatibilità con versioni precedenti di Microsoft Windows, consultare l'appendice A, "Versioni di Windows supportate".

-   Questa soluzione non fornisce istruzioni per effettuare l'integrazione in un'infrastruttura RADIUS esistente, tuttavia ciò non esclude la possibilità di una distribuzione accanto a un'infrastruttura RADIUS esistente.

-   Hardware del server in grado di eseguire il Servizio autenticazione Internet (IAS) di Windows Server 2003. Questa guida contiene una configurazione consigliata.

-   Licenze Windows Server 2003 Standard Edition e Enterprise Edition, supporti di installazione e codici "Product Key".

#### Panoramica dei capitoli

La figura che segue mostra il processo di creazione dell'infrastruttura RADIUS che sarà illustrato in modo dettagliato in questo capitolo.

![](images/Dd536189.08fig8-1(it-it,TechNet.10).gif "Figura 8.1 Diagramma del processo di creazione dell'infrastruttura RADIUS")

**Figura 8.1 Diagramma del processo di creazione dell'infrastruttura RADIUS**

Questi passaggi rispecchiano l'organizzazione del capitolo e sono descritti nell'elenco seguente. Ciascuno di essi è costituito da attività di installazione o configurazione e una o più procedure di verifica che consentono di controllare le operazioni eseguite prima di continuare con il passaggio successivo.

-   **Foglio di lavoro per la pianificazione di IAS** Sono elencate le informazioni di configurazione utilizzate in questo capitolo per installare e configurare il Servizio autenticazione Internet. È inclusa una tabella di informazioni che devono essere fornite dall'utente prima di iniziare l'implementazione.

-   **Creazione dei propri server** Vengono descritte le procedure di selezione e configurazione dell'hardware, l'installazione di Windows Server 2003 e l'installazione di componenti opzionali. Inoltre, vengono descritte la creazione di gruppi di protezione per la gestione di Active Directory, l'impostazione delle autorizzazioni necessarie per la delega delle attività di gestione e l'implementazione della protezione a livello di sistema operativo mediante l'applicazione di modelli di protezione. I modelli utilizzati sono desunti dalla *Guida per la protezione di Windows Server 2003*. Le informazioni su come ottenere questa guida sono riportate alla fine di questo capitolo. Inoltre, in questa sezione sono elencate alcune attività comuni per completare l'installazione di base dei server.

-   **Installazione e configurazione del Servizio autenticazione Internet** Vengono descritti i passaggi di preparazione, l'installazione del software e la configurazione del Servizio autenticazione Internet, incluse la creazione e la protezione delle directory dati IAS.

-   **Configurazione del server IAS primario**  Viene descritto il processo di configurazione del server IAS primario che verrà utilizzato come modello di configurazione per ulteriori server IAS con ruoli simili nell'ambiente. Inoltre, viene descritta la procedura di esportazione della configurazione IAS per l’utilizzo su altri server IAS. Questa procedura verrà riutilizzata nei capitoli successivi dopo l'esecuzione di una configurazione più complessa.

-   **Configurazione del server IAS secondario** Viene descritta la procedura di configurazione del server IAS secondario che verrà unito al server IAS primario in una coppia di server RADIUS per la tolleranza di errore e il bilanciamento del carico. Viene descritta, inoltre, la procedura di importazione della configurazione IAS primaria per la distribuzione automatica. Questa procedura verrà riutilizzata nei capitoli successivi dopo l'esecuzione di una configurazione più complessa.

-   **Configurazione dei server IAS filiale** Viene descritta la procedura di configurazione di un server IAS filiale facoltativo che può essere utilizzato come esempio per ambienti distribuiti e la procedura di importazione della configurazione IAS primaria per la distribuzione automatica. Questa procedura verrà riutilizzata nei capitoli successivi dopo l'esecuzione di una configurazione più complessa.

[](#mainsection)[Inizio pagina](#mainsection)

### Foglio di lavoro per la pianificazione dell'infrastruttura RADIUS

Nella tabella che segue vengono elencati i parametri di configurazione utilizzati in questa soluzione. Devono essere considerati come un elenco di controllo quando si prendono le decisioni relative alla pianificazione.

Molti dei parametri riportati in queste tabelle vengono impostati manualmente come parte delle procedure documentate in questo capitolo. Altri vengono impostati da uno script eseguito come parte di una procedura oppure viene fatto riferimento al parametro da uno script per completare un'altra configurazione o un'attività operativa.

**Nota:** gli script utilizzati nella Guida alla creazione vengono descritti in modo più dettagliato nel file ToolsReadme.txt allegato agli script.

#### Elementi di configurazione definiti dagli utenti

La tabella che segue elenca dei parametri specifici dell'azienda fittizia Woodgrove Bank. Prima di iniziare la procedura di configurazione, occorre accertarsi di aver raccolto o deciso le impostazioni equivalenti per la propria organizzazione di tutti gli elementi indicati nella sottostante tabella. Negli esempi dei comandi citati nell'intero capitolo vengono utilizzati i valori fittizi mostrati qui. È necessario sostituire tali valori fittizi con i valori adeguati della propria azienda. I valori che è necessario sostituire sono indicati in corsivo.

**Tabella 8.1. Elementi di configurazione definiti dagli utenti**

 
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
<td style="border:1px solid black;">Nome NetBIOS (Network Basic Input/Output System) del dominio</td>
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
<td style="border:1px solid black;">Nome del server IAS secondario</td>
<td style="border:1px solid black;"><em>BO - IAS - 03</em></td>
</tr>
</tbody>
</table>
  
#### Elementi di configurazione indicati dalla soluzione
  
Nel caso di un'installazione specifica non è necessario modificare le impostazioni indicate in questa tabella, a meno che non sia necessario utilizzare un'impostazione diversa da quella offerta dalla soluzione. La modifica dei parametri di progettazione forniti in questa tabella è perfettamente accettabile, ma occorre essere consapevoli del fatto che così facendo ci si discosta dalla soluzione collaudata. Prima di modificare eventuali valori nelle procedure di configurazione o negli script forniti, assicurarsi di avere compreso a fondo le implicazioni della modifica che si intende apportare e le dipendenze che tale impostazione potrebbe avere.
  
**Tabella 8.2. Elementi di configurazione indicati dalla soluzione**

 
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
<td style="border:1px solid black;">[Account] Nome completo del gruppo amministrativo che controlla la configurazione del Servizio autenticazione Internet</td>
<td style="border:1px solid black;">IAS Admins</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] Nome precedente a Windows 2000 del gruppo amministrativo che controlla la configurazione del Servizio autenticazione Internet</td>
<td style="border:1px solid black;">IAS Admins</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Account] Nome completo del gruppo che rivede il registro IAS delle richieste di account e di autenticazione per motivi di sicurezza</td>
<td style="border:1px solid black;">IAS Security Auditors</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Account] Nome pre-Windows 2000 del gruppo che esamina i registri delle richieste di autenticazione e accounting IAS a fini di protezione</td>
<td style="border:1px solid black;">IAS Security Auditors</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Scripts] Percorso degli script di installazione</td>
<td style="border:1px solid black;">C:\MSSScripts</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Script] File batch per l'esportazione della configurazione IAS</td>
<td style="border:1px solid black;">IASExport.bat</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Script] File batch per l'importazione della configurazione IAS</td>
<td style="border:1px solid black;">IASImport.bat</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Script] File batch per l'esportazione della configurazione dei client RADIUS IAS</td>
<td style="border:1px solid black;">IASClientExport.bat</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Script] File batch per l'importazione della configurazione dei client RADIUS di IAS</td>
<td style="border:1px solid black;">IASClientImport.bat</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Config] Percorso dei file di backup della configurazione</td>
<td style="border:1px solid black;">D:\IASConfig</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">[Registri richieste] Posizione dei file registro di autenticazione e delle richieste di controllo IAS</td>
<td style="border:1px solid black;">D:\IASLogs</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">[Request Logs] Nome della condivisione dei registri delle richieste RADIUS</td>
<td style="border:1px solid black;">IASLogs</td>
</tr>
</tbody>
</table>
  
#### Preparazione per il Servizio autenticazione Internet
  
La soluzione include due server IAS in posizione centrale configurati come server RADIUS per il controllo di accesso WLAN. Inoltre, la soluzione include un server IAS filiale facoltativo configurato come un server RADIUS, per ambienti che richiedono un'infrastruttura distribuita. Per ulteriori informazioni sulla posizione dei server IAS, consultare il capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili".
  
Prima dell'installazione del Servizio autenticazione Internet è necessario completare una serie di attività di preparazione, quali:
  
-   configurazione dell'hardware del server.
  
-   Installazione del software del sistema operativo del server.
  
-   Preparazione di Active Directory.
  
-   Esecuzione di alcune attività di consolidamento della protezione del server.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Creazione dei propri server
  
Nelle sezioni seguenti vengono descritti i passaggi per la creazione dei propri server. Sebbene la creazione di ciascun server possa essere eseguita indipendentemente, è importante completare ogni passaggio per tutti i server.
  
#### Specifica dell'hardware del server
  
L'hardware del server per il Servizio autenticazione Internet deve essere selezionato dall'[Windows Server 2003 Hardware Compatibility List (HCL)](http://www.microsoft.com/whdc/hcl/default.mspx) (in inglese). La selezione dell'hardware del server dall'elenco di compatibilità hardware di Windows Server 2003 consente di evitare problemi di affidabilità e compatibilità, che potrebbero verificarsi nel caso di hardware non verificato o driver di periferica mal codificati. Per ulteriori informazioni sulla compatibilità hardware di Windows Server 2003, vedere la sezione “Ulteriori informazioni” alla fine di questo capitolo.
  
##### Specifiche hardware di server verificate
  
Le seguenti specifiche hardware sono state utilizzate per eseguire il test di questa soluzione in un ambiente di laboratorio. Queste specifiche hardware sono solo di riferimento e non sono obbligatorie. Per ulteriori informazioni sui requisiti hardware del server IAS, vedere il capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili".
  
**Tabella 8.3. Specifiche hardware di server verificate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Risorsa</th>
<th style="border:1px solid black;" >Requisito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CPU</td>
<td style="border:1px solid black;">CPU doppia da 850 MHz o superiore</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Memoria</td>
<td style="border:1px solid black;">512 MB</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Interfacce di rete</td>
<td style="border:1px solid black;">2 x singole schede di interfaccia di rete (NIC, Network Interface Card) unite per una maggiore adattabilità</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Archiviazione disco</td>
<td style="border:1px solid black;">Controller RAID (Redundant Array of Independent Disks) IDE (Integrated Device Electronics) o SCSI (Small Computer System Interface)
2 x 9 GB (SCSI o IDE) configurato come volume RAID 1 (unità C)
2 x 18 GB (SCSI o IDE) configurato come volume RAID 1 (unità D)
Archiviazione su supporti rimovibili locali (CD-RW o nastro di backup), in assenza di una funzionalità di backup di rete
Unità disco floppy da 1,44 MB per il trasferimento dei dati</td>
</tr>
</tbody>
</table>
 

##### Preparazione dell'hardware

Completare tutte le configurazioni hardware in base alle indicazioni del fornitore hardware. Queste configurazioni possono includere l'applicazione degli aggiornamenti più recenti del BIOS (Basic Input/Output System) e dei firmware ricevuti dal proprio fornitore.

Utilizzare il software di gestione del controller del disco, fornito con l'hardware, per creare i volumi RAID 1, come indicato nella tabella precedente.

#### Installazione di Windows Server 2003

Questa sezione descrive in dettaglio l'installazione di Windows Server 2003 nei server IAS. Molte organizzazioni dispongono già di un processo automatico di installazione server. Tale processo automatico può essere utilizzato per le build del server, purché sia possibile includere nella build i parametri indicati nella procedura riportata di seguito. Per informazioni sull'utilizzo di Windows Server 2003 Standard Edition o Windows Server 2003 Enterprise Edition, vedere il capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili".

Eseguire i passaggi indicati di seguito per installare Windows Server 2003 su uno dei server IAS.

**Per installare Windows Server 2003**

1.  Assicurarsi che l'unità CD-ROM sia stata impostata come unità avviabile nelle impostazioni BIOS del server. Riavviare il computer con il CD di Windows Server 2003 nell'unità CD-ROM.

2.  Creare una partizione nel volume primario, formattarla come file system NTFS e selezionare l'opzione per installare Windows in tale partizione.

3.  Selezionare le impostazioni internazionali appropriate.

4.  Digitare il nome e le informazioni relative all'azienda per la quale verrà registrato Windows.

5.  Digitare una password sicura per l'account dell'amministratore locale (almeno 10 caratteri misti: maiuscole, minuscole, lettere, numeri e punteggiatura).

6.  Digitare il nome del computer quando richiesto (sostituire questo valore con il nome che si è scelto):

    -   IAS primario: *HQ-IAS-01*

    -   IAS secondario: *HQ-IAS-02*

    -   IAS filiale: BO-IAS-03

7.  Quando richiesto, scegliere l’opzione di unirsi a un dominio. Immettere il nome del dominio Active Directory a cui verranno aggiunti i server: ***WOODGROVEBANK*** (sostituire questo valore con il nome del dominio in cui si installa il server RADIUS). Quando richiesto, immettere le credenziali di un utente autorizzato ad aggiungere computer a questo dominio.

    **Nota:** nel caso di un dominio con più insiemi di strutture, i server IAS vengono solitamente installati nel dominio principale dell'insieme di strutture, per ottimizzare le operazioni di Kerberos. Sebbene non sia essenziale, questa soluzione si basa su tale configurazione.

8.  Non installare componenti facoltativi.

    Al termine del processo di installazione principale, il computer verrà riavviato. Continuare con i passaggi seguenti.

9.  Installare eventuali service pack correnti, aggiornamenti critici e altri aggiornamenti necessari.

10. Riassegnare all'unità CD-ROM/DVD la lettera R.

11. Creare una partizione sul secondo volume del disco rigido, assegnare all'unità di questa partizione la lettera D e formattarla con NTFS.

12. Attivare questa copia di Windows.

##### Impostazioni di rete

I server IAS dispongono di una singola interfaccia di rete, sebbene questa configurazione possa essere implementata accoppiando due schede di interfaccia di rete fisiche per una maggiore capacità di recupero. L'interfaccia di rete deve essere configurata con un indirizzo IP (Internet Protocol) fisso e altri parametri di configurazione IP (quali gateway predefinito e impostazioni DNS) adeguati per la propria rete.

#### Verifica dell'installazione

È necessario verificare che l'installazione del sistema operativo sia stata completata correttamente e che i parametri configurati corrispondano ai risultati previsti.

**Per visualizzare la configurazione corrente del sistema**

1.  Al prompt dei comandi, eseguire il programma systeminfo.

2.  Verificare i seguenti elementi dell'output di systeminfo (alcuni dettagli dell'output sono stati omessi per maggiore concisione):

    Nome host: *HQ-IAS-01*

    Nome SO: Microsoft® Windows® Server 2003, Enterprise Edition

    ...

    Configurazione SO: server membro

    Proprietario registrato: *il\_proprio\_nome*

    Organizzazione registrata: *la\_propria\_organizzazione*

    ...

    Directory Windows: C:\\WINDOWS

    Directory di sistema: C:\\WINDOWS\\System32

    Unità di avvio: \\Device\\HarddiskVolume1

    Impostazioni internazionali sistema: *le\_proprie\_impostazioni*

    Impostazione internazionale di input: *la\_propria\_impostazione*

    Fuso orario: *il\_proprio\_fuso\_orario*

    ...

    Dominio: woodgrovebank.com

    Server di accesso: \\\\*Nome\_del\_controller\_di\_dominio*

    Aggiornamenti rapidi: X aggiornamenti rapidi installati.

      \[01\]: Qxxxxxx

    ...

      \[nn\]: Qnnnnnn

    Schede di rete: 1 NIC installata.

    \[01\]: *modello\_e\_fornitore\_della\_scheda\_di\_rete* 

    Nome connessione: connessione alla rete locale

    DHCP abilitato:    No

    Indirizzi IP

    \[01\]: xxx.xxx.xxx.xxx

3.  Se queste impostazioni non corrispondono a quelle previste, è necessario riconfigurare il server utilizzando il Pannello di controllo oppure riavviare l'installazione.

##### Installazione di script di configurazione sui server

Assieme a questa soluzione vengono forniti script di supporto e file di configurazione per semplificare alcuni aspetti della configurazione e del funzionamento di questa soluzione. È necessario installarli in ciascun server. Alcuni di questi script saranno richiesti dalle operazioni descritte nel capitolo 12, "Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili", pertanto non dovranno essere eliminati al termine dell'installazione del server RADIUS.

**Per installare gli script di installazione in ciascun server**

1.  Creare una cartella denominata **C:\\MSSScripts**.

2.  Copiare gli script dal supporto di distribuzione alla cartella.

#### Controllo dei service pack e degli aggiornamenti della protezione

A questo punto, è necessario ricontrollare l'elenco dei service pack e degli aggiornamenti della protezione installati. Utilizzare uno strumento, ad esempio Microsoft Baseline Security Analyzer (MBSA), per eseguire il controllo, ottenere tutte le correzioni richieste e installarle nei server dopo un'adeguata procedura di test.

Per ulteriori informazioni su MBSA, vedere la sezione "Ulteriori informazioni" al termine di questo capitolo.

#### Installazione di software aggiuntivo

In questa sezione viene descritta la procedura per l'installazione sui server IAS di eventuali programmi software aggiuntivi necessari.

##### CAPICOM

CAPICOM 2.0 è necessario sui server RADIUS per alcuni degli script di installazione e gestione forniti con questa soluzione. Per informazioni su dove reperire l'ultima versione di CAPICOM, consultare la sezione "Ulteriori informazioni" alla fine di questo capitolo.

Prima di continuare con le procedure descritte in questa guida, seguire le istruzioni del file eseguibile autoestraente, per installare e registrare la DLL (Dynamic-Link Library) di CAPICOM.

##### Convalida della connettività di rete e di Active Directory

Il Servizio autenticazione Internet dipende molto dalla corretta configurazione di rete e dalla connettività di Active Directory. Si prenda, pertanto, in considerazione la possibilità di eseguire la diagnostica rete sul server prima di distribuire IAS.

È possibile eseguire Diagnostica rete tramite l'utilità Netdiag.exe degli Strumenti di supporto di Windows Server 2003 inclusi nel CD di Windows Server 2003. Estrarre Netdiag.exe con il comando seguente:

expand r:\\support\\tools\\support.cab –f:netdiag.exe c:\\mssscripts

Al termine, digitare il seguente comando:

C:\\mssscripts\\netdiag.exe

Assicurarsi di controllare eventuali errori o avvisi visualizzati.

##### Verifica del livello di funzionalità del dominio

Il [modello preferito](http://www.microsoft.com/windows2000/techinfo/administration/management/pgremote.asp) per il controllo dell'accesso di rete consiste nello sfruttare l'impostazione **Controlla accesso tramite Criteri di accesso remoto** per gli account utente all'interno di Active Directory. L'impostazione **Controlla accesso tramite Criteri di accesso remoto** è disponibile solo se Active Directory è in esecuzione nella modalità nativa di Windows 2000 o versioni successive. Pertanto, è necessario controllare il livello di funzionalità del dominio prima della distribuzione di criteri di accesso remoto (RAP) in IAS.

È possibile controllare il livello di funzionalità del dominio visualizzando le proprietà del dominio all'interno dello strumento Domini e trust di Active Directory. Se il dominio di destinazione per IAS è configurato nella modalità mista di Windows 2000, rivolgersi agli amministratori di Active Directory appropriati per pianificare la migrazione alla modalità nativa.

Per ulteriori informazioni su questo argomento, vedere la sezione "Ulteriori informazioni" al termine di questo capitolo.

##### Configurazione di gruppi di protezione di Active Directory

Il Servizio autenticazione Internet fa parte dell'infrastruttura per la protezione della rete. Di conseguenza,  l'accesso alla configurazione del Servizio autenticazione Internet e ai file del registro deve essere rigorosamente controllato. Per implementare i controlli degli accessi richiesti, viene utilizzata una combinazione di gruppi globali di Active Directory e gruppi locali di Windows Server 2003.

###### Creazione di gruppi per l'amministrazione del Servizio autenticazione Internet

Eseguire lo script riportato di seguito come amministratore di dominio, per creare gruppi di protezione per l'amministrazione del Servizio autenticazione Internet:

Cscript //job:CreateIASGroups C:\\MSSScripts\\IAS\_Tools.wsf

Questo script crea i seguenti gruppi di protezione come gruppi globali di dominio:

-   IAS Admins

-   IAS Security Auditors

Nel caso di un dominio con più insiemi di strutture, è necessario creare questi gruppi nello stesso dominio dei server IAS.

**Nota:** le aziende con amministratori situati in più domini dovrebbero considerare l'opzione di utilizzare gruppi universali invece dei gruppi globali creati in questa soluzione. Lo script che crea i gruppi di protezione può essere facilmente modificato tramite la sintassi usata per creare il gruppo Criteri di accesso remoto - Accesso senza fili nel capitolo successivo (vedere "Creazione di gruppi di Active Directory richiesti per l'accesso alla rete WLAN" nel capitolo 9).

###### Configurazione del gruppo di amministratori IAS

IAS è un componente fondamentale del sistema operativo Windows Server 2003, pertanto è necessaria l'appartenenza al gruppo di protezione Amministratori locale per eseguire attività di configurazione del Servizio autenticazione Internet.

È necessario aggiungere il gruppo globale di dominio Amministratori IAS nel gruppo Amministratori locale su ciascun server IAS. Se IAS è installato in un controller di dominio, è necessario aggiungere Amministratori IAS al gruppo Amministratori per il dominio utilizzando lo snap-in MMC (Microsoft Management Console) Utenti e computer di Active Directory.

**Avviso:** l'aggiunta di gruppi al gruppo di dominio predefinito Amministratori  può avere serie conseguenze per la protezione. Per ulteriori informazioni, vedere la sezione dedicata al posizionamento di IAS nei controller di dominio del capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili".

È necessario popolare i gruppi Amministratori IAS e Controllori protezione IAS con gli account del personale amministrativo appropriato. Per una descrizione completa del mapping di questi gruppi ai ruoli amministrativi del Servizio autenticazione Internet, consultare la sezione relativa alla pianificazione delle autorizzazioni amministrative nel capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili".

Le procedure di installazione nella parte restante di questo documento richiedono l'uso di account che siano membri del gruppo Amministratori IAS.

##### Protezione di Windows Server 2003 per IAS

È necessario eseguire ulteriori passaggi per proteggere i server IAS dall'accesso non autorizzato. I server IAS sono un componente fondamentale dell'infrastruttura di protezione, pertanto dovrebbero ricevere la stessa considerazione dei firewall e delle altre infrastrutture di protezione dell'accesso.

###### Protezione fisica

È necessario posizionare i server IAS in un luogo dove l'accesso fisico possa essere controllato rigorosamente. Questi server devono essere continuamente in linea, pertanto è necessario posizionarli in un luogo dotato delle strutture adeguate (controllo della temperatura, filtraggio dell'aria, dispositivi antincendio).

La posizione dei server dovrebbe essere scelta in modo che sia il più possibile protetta da rischi esterni che potrebbero danneggiare il server, quali incendi e inondazioni.

Di pari importanza sono il controllo dell'accesso fisico e la garanzia della protezione fisica dei backup, della documentazione e di altri dati di configurazione. Queste informazioni dovrebbero essere conservate in un luogo separato dai server.

##### Applicazione delle impostazioni di protezione del sistema ai server

I server IAS vengono protetti utilizzando il ruolo server IAS definito nella *Guida per la protezione di Windows Server 2003*. Per ulteriori informazioni su questa guida e il sito per il download dei modelli di sicurezza, consultare la sezione "Ulteriori informazioni" alla fine di questo capitolo.

Poiché i server IAS sono membri di un dominio, le impostazioni dei criteri di protezione vengono applicate utilizzando Criteri di gruppo basati sul dominio. È necessario creare un'adeguata struttura di unità organizzativa (UO) che conservi gli oggetti computer del server IAS e una struttura di Oggetto Criteri di gruppo (GPO) per applicare le impostazioni di sicurezza. È necessario creare due GPO per server IAS eseguiti su server dedicati (ossia installati in un controller di dominio).

-   Enterprise Client - Server membro di base

-   Enterprise Client - Servizio autenticazione Internet

Dopo aver letto il capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili", si potrebbe decidere di eseguire alcuni o tutti i servizi IAS nei controller di dominio. A causa della complessità della protezione avanzata dei controller di domino, in questo documento non vengono fornite istruzioni per l'applicazione di modelli Controller di dominio. La *Guida per la protezione di Windows Server 2003* include un modello di protezione per i controller di dominio che eseguono un blocco simile a quello del criterio di base per i server membri. È necessario applicare il modello di protezione Controller di dominio ai controller di dominio esistenti solo dopo aver letto attentamente la *Guida per la protezione di Windows Server 2003* e aver valutato i potenziali impatti sulle applicazioni e sui client di dominio.

Se si utilizza il modello di protezione Enterprise Client - Controller di dominio su server di controller di dominio e IAS combinati, su tali computer è necessario applicare il modello di protezione Enterprise Client - Server IAS. Questo modello applica impostazioni aggiuntive che attivano il servizio IAS (il servizio IAS è disattivato nel modello Enterprise Client - Controller di dominio). Per applicare questo modello, è necessario creare un GPO aggiuntivo da applicare in una nuova unità organizzativa figlio posizionata al di sotto dell'unità organizzativa Controller di dominio:

-   Enterprise Client - IAS su Controller di dominio

È necessario attenersi alla procedura seguente per importare il modello Enterprise Client - Server IAS in questo GPO. Questa procedura descrive come creare unità organizzative (UO) e oggetti Criteri gruppo richiesti (GPO). I nomi di GPO e UO vengono forniti esclusivamente a scopo esemplificativo. È necessario adeguare la procedura ai propri standard di UO e GPO di dominio.

**Per creare le UO e i GPO dei server IAS**

1.  Ottenere i seguenti modelli di protezione dalla *Windows Server 2003 Security Guide*:

    -   Enterprise Client - Dominio

    -   Enterprise Client - Server membro di base

    -   Enterprise Client - Server IAS

    -   Enterprise Client - Controller di dominio

2.  Accedere come membro del gruppo degli Amministratori di dominio o come utente che dispone di diritti per la creazione delle UO descritte nel passaggio 4. Per creare GPO, è necessario essere un membro del gruppo Amministratori di dominio o di quello Proprietari autori criteri di gruppo.

3.  Aprire lo snap-in MMC Utenti e computer di Active Directory.

4.  Creare la seguente struttura dell'unità organizzativa:

    woodgrovebank.com

    - Server membri

    - IAS

    - Controller di dominio

    - Controller di dominio con IAS

    **Avviso:** i passaggi da 5 a 7 applicano criteri di dominio che configurano i criteri di account locali su tutti i computer nel dominio. È preferibile prendere in esame il modello Enterprise Client - Protezione del dominio. Anziché applicarlo a tutto il dominio, può essere necessario creare questo GPO collegato all'unità operativa IAS in maniera che il suo ambito sia limitato solo ai server IAS.

5.  Aprire le proprietà del contenitore del dominio. Dalla scheda **Criterio gruppo**, fare clic su **Nuovo** per creare un nuovo GPO e denominarlo **Criteri dominio**.

6.  Modificare il GPO e selezionare la cartella Configurazione computer\\Impostazioni di Windows\\Impostazioni di protezione. Fare clic con il pulsante destro del mouse sulla cartella **Impostazioni di protezione**, quindi fare clic su **Importa**. Individuare il file Enterprise Client - Domain.inf e selezionarlo come modello da importare.

7.  Chiudere il GPO.

8.  Ripetere i tre passaggi precedenti per la combinazione di unità operative, GPO e modelli di protezione mostrata nella tabella seguente. Questi tre GPO agiscono solo sui server IAS, quindi l'avviso precedente in questo caso non è rilevante.

    **Tabella 8.4. Oggetti Criteri di gruppo e posizione**
   
   <table style="border:1px solid black;">
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" >Unità operativa</th>
    <th style="border:1px solid black;" >GPO</th>
    <th style="border:1px solid black;" >Modello di protezione</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Server membri</td>
    <td style="border:1px solid black;">Enterprise Client - Server membro di base</td>
    <td style="border:1px solid black;">Enterprise Client - Server membro Baseline.inf</td>
    </tr>
    <tr class="even">
    <td style="border:1px solid black;">IAS</td>
    <td style="border:1px solid black;">Enterprise Client - Servizio autenticazione Internet</td>
    <td style="border:1px solid black;">Enterprise Client - IAS Server.inf</td>
    </tr>
    <tr class="odd">
    <td style="border:1px solid black;">Controller di dominio con IAS</td>
    <td style="border:1px solid black;">Enterprise Client - IAS su Controller di dominio
    (facoltativo se IAS si trova su un controller di dominio)</td>
    <td style="border:1px solid black;">Enterprise Client - IAS Server.inf</td>
    </tr>
    </tbody>
    </table>
  
Dopo aver creato i GPO e importato i modelli, è necessario personalizzare le impostazioni nei GPO e applicarli ai computer del server IAS in base alla seguente procedura.
  
**Per personalizzare e applicare il GPO Enterprise Client - Servizio autenticazione Internet**
  
1.  Da Utenti e computer di Active Directory, modificare il GPO Enterprise Client - Servizio autenticazione Internet. In Configurazione computer\\Impostazioni di Windows\\Impostazioni di protezione\\Criteri locali\\Opzioni di protezione modificare gli elementi indicati di seguito in base agli standard di protezione della propria azienda:
  
    -   Account: rinomina account guest: *nuovo\_nome\_amministratore*
  
    -   Account: rinomina account guest: *nuovo\_nome\_guest*
  
    -   Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso: *titolo\_note\_legali*
  
    -   Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso: *titolo\_note\_legali*
  
2.  In Criteri locali\\Assegnazione diritti utente, aggiungere i seguenti gruppi locali e di dominio ai diritti utente **Consenti** **accesso locale**:
  
    -   (locale) *Administrators*
  
    -   (locale) *Backup Operators*
  
    -   (dominio) IAS Security Auditors
  
3.  Aprire le proprietà dei servizi elencati di seguito nella cartella Servizi sistema e fare clic su **Definisci questa impostazione nel modello**. Accettare le autorizzazioni predefinite facendo clic su **OK**. Impostare il valore dell'opzione **Selezionare la modalità di avvio servizio** impostandola su **Automatico**.
  
    -   Archivi rimovibili
  
    -   Copia replicata del volume
  
    -   Provider di copie shadow per software MS
  
    -   Utilità di pianificazione
  
    **Nota:** questi servizi sono disattivati nel modello di protezione di base per i server membro, ma i primi tre sono necessari per NTBackup.exe. Il servizio Utilità di pianificazione è richiesto da alcuni script operativi.
  
4.  Spostare l'account del computer del server IAS nell'unità operativa IAS.
  
5.  Sul server IAS, eseguire il comando gpupdate per applicare le impostazioni di GPO al computer.
  
    **Nota:** la *Guida per la protezione di Windows Server 2003* contiene una spiegazione più dettagliata di queste impostazioni di protezione. Per ulteriori dettagli su come ottenere la guida, vedere la sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
**Per personalizzare e applicare il GPO Enterprise Client - IAS su Controller di dominio**
  
1.  Da Utenti e computer di Active Directory, modificare il GPO Enterprise Client - IAS su Controller di dominio. In Configurazione computer\\Impostazioni di Windows\\Impostazioni di protezione\\Criteri locali\\Opzioni di protezione modificare gli elementi indicati di seguito in base agli standard di protezione della propria azienda:
  
    -   Account: rinomina account guest: *nuovo\_nome\_amministratore*
  
    -   Account: rinomina account guest: *nuovo\_nome\_guest*
  
    -   Accesso interattivo: testo del messaggio per gli utenti che tentano l'accesso: *titolo\_note\_legali*
  
    -   Accesso interattivo: titolo del messaggio per gli utenti che tentano l'accesso: *titolo\_note\_legali*
  
2.  In Criteri locali\\Assegnazione diritti utente, aggiungere i seguenti gruppi locali e di dominio ai diritti utente **Consenti** **accesso locale**:
  
    -   (locale) *Administrators*
  
    -   (locale) *Backup Operators*
  
    -   (dominio) IAS Security Auditors
  
3.  Aprire le proprietà dei servizi elencati di seguito nella cartella Servizi sistema e fare clic su **Definisci questa impostazione nel modello**. Accettare le autorizzazioni predefinite facendo clic su **OK**. Impostare il valore dell'opzione **Selezionare la modalità di avvio servizio** impostandola su **Automatico**.
  
    -   Archivi rimovibili
  
    -   Copia replicata del volume
  
    -   Provider di copie shadow per software MS
  
    -   Utilità di pianificazione
  
        **Nota:** questi servizi sono disattivati nel modello di protezione di base dei server membro, ma i primi tre sono necessari per consentire l'esecuzione di NTBackup.exe. Il servizio Utilità di pianificazione è richiesto da alcuni script operativi.
  
4.  Spostare l'account del computer del server IAS nei controller di dominio con unità operativa IAS.
  
5.  Sul server IAS, eseguire il comando gpupdate per applicare le impostazioni di GPO al computer.
  
    **Nota:** la *Guida per la protezione di Windows Server 2003* contiene una spiegazione più dettagliata di queste impostazioni di protezione. Per ulteriori dettagli su come ottenere la guida, vedere la sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
##### Verifica delle impostazioni di protezione
  
Per verificare la corretta applicazione delle impostazioni di protezione, procedere come indicato di seguito.
  
**Per verificare le impostazioni di protezione del server IAS**
  
1.  Controllare la presenza di eventi con origine SceCli nel Registro eventi applicazioni. Dovrebbe venire visualizzato un evento con ID 1704 dopo il comando **gpupdate**. Il testo dell'evento dovrebbe essere il seguente:
  
    Applicazione del criterio di protezione agli oggetti del criterio di gruppo riuscita.
  
2.  Riavviare il server, verificare che tutti i servizi previsti vengano avviati e che non vengano inseriti errori nel registro eventi di sistema.
  
3.  Dovrebbe essere consentito l'accesso e dovrebbe essere visualizzato il testo della nota legale.
  
##### Configurazione della protezione di Servizi terminal
  
È necessario utilizzare Servizi terminal per la modifica pianificata delle password (segreti di RADIUS) utilizzate dai client RADIUS. La crittografia del traffico di Servizi terminal protegge i segreti di RADIUS quando transitano in rete.
  
**Importante:** se viene utilizzato un altro metodo per impostare o modificare i segreti dei client RADIUS in rete (ad esempio, tramite telnet o un altro semplice strumento di esecuzione remota), assicurarsi di utilizzare IPSec (Internet Protocol Security) o un'altra tecnologia appropriata per proteggere le informazioni in transito.
  
Le seguenti impostazioni di Servizi terminal dovrebbero essere configurate nel GPO Enterprise Client - IAS su Controller di dominio e nel GPO Enterprise Client - Servizio autenticazione Internet che si applicano ai server IAS.
  
**Tabella 8.5. Impostazioni da configurare in Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\Servizi terminal**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Percorso</th>
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
<td style="border:1px solid black;">Imposta livello di crittografia connessione client</td>
<td style="border:1px solid black;">Alto</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Richiedi sempre password del client alla connessione</td>
<td style="border:1px solid black;">Attivato</td>
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
  
Ogni account di dominio o gruppo di protezione che richiede l'accesso dei Servizi terminal ai server IAS dovrà essere aggiunto al gruppo locale Utenti desktop remoto (a meno che non sia già membro del gruppo Administrators locale).
  
##### Restanti attività di configurazione di Windows
  
Sarà necessario eseguire ulteriori attività di configurazione, a seconda dell'infrastruttura e degli standard della propria azienda. Ad esempio:
  
-   Attivazione dei backup o installazione di agenti di backup.
  
-   Configurazione del protocollo SNMP (Simple Network Management Protocol) del servizio Strumentazione gestione Windows (WMI).
  
-   Installazione di agenti di gestione, quali i componenti client Microsoft Operations Manager (MOM) o Microsoft Systems Management Server (SMS).
  
-   Installazione di software antivirus.
  
-   Installazione di agenti per il rilevamento delle intrusioni.
  
È necessario verificare questi elementi quando vengono installati.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Installazione e configurazione del Servizio autenticazione Internet
  
Questa soluzione include due server IAS in posizione centrale che funzionano da server RADIUS per l'autenticazione degli utenti e l'autorizzazione dell'accesso alla rete. Inoltre, la soluzione include un server IAS filiale facoltativo per gli ambienti che richiedono un'autenticazione degli utenti e un'autorizzazione dell'accesso alla rete distribuite. Per ulteriori informazioni sulla posizione dei server IAS, consultare il capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili".
  
Nella sezione che segue vengono descritte le procedure per installare IAS sui server. È importante eseguire tutte le procedure di installazione e configurazione su ciascun server IAS.
  
#### Installazione dei componenti software di IAS
  
Il Servizio autenticazione Internet viene installato tramite Windows Optional Components Manager (a cui si accede selezionando **Installazione componenti di Windows** dal Pannello di controllo. Nella tabella che segue sono elencati i componenti da installare. I rientri dei paragrafi riflettono la relazione tra i componenti così come sono visualizzati nella Gestione guidata dei componenti facoltativi. I componenti che non vengono selezionati non sono inclusi nella tabella.
  
**Tabella 8.6. Componenti IAS per l'installazione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Componente facoltativo da installare</th>
<th style="border:1px solid black;" >Stato di installazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Servizi di rete</td>
<td style="border:1px solid black;">Selezionata</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">          Servizio autenticazione Internet</td>
<td style="border:1px solid black;">Selezionata</td>
</tr>
</tbody>
</table>
  
**Nota:** il supporto di installazione di Windows Server 2003 sarà necessario per completare l'installazione.
  
**Per installare i componenti IAS**
  
-   Eseguire nuovamente Gestione componenti facoltativi su ciascun server IAS per automatizzare l'installazione del Servizio autenticazione Internet; il seguente comando esegue questa operazione:
  
    sysocmgr /i:sysoc.inf /u:C:\\MSSScripts\\OC\_AddIAS.txt
  
##### Registrazione di IAS in Active Directory
  
I server IAS devono essere registrati in ogni dominio. In questo modo, l'account di computer del server IAS diventa un membro del gruppo di protezione Server RAS e IAS in ciascun dominio per il quale si dovrà eseguire l'autenticazione. L'appartenenza a questo gruppo garantisce che i server IAS dispongano dell'autorizzazione per leggere le proprietà di accesso remoto degli account utente e computer nel dominio.
  
Gli oggetti account computer dei server IAS possono essere posizionati in questo gruppo utilizzando lo snap-in MMC Utenti e computer di Active Directory o il comando di Netshell (**netsh**).
  
**Per registrare il Servizio autenticazione Internet sui server nel dominio predefinito con il comando netsh**
  
1.  Accedere a ciascun server IAS con un account che dispone dei privilegi di Domain Admins per il dominio.
  
2.  Aprire un prompt dei comandi e digitare:
  
    netsh ras add registeredserver
  
**Per registrare il Servizio autenticazione Internet in domini diversi da quello predefinito utilizzando il comando netsh**
  
1.  Accedere a ciascun server IAS con un account che dispone dei privilegi di Domain Admins per il dominio di destinazione.
  
2.  Aprire un prompt dei comandi e digitare quanto segue sostituendo *DomainName* con il nome del dominio in cui deve essere registrato il server IAS:
  
    netsh ras add registeredserver domain = *DomainName*
  
    **Nota:** in alternativa, è possibile aggiungere l'oggetto computer del server IAS nel gruppo di protezione Server RAS e IAS utilizzando lo snap-in MMC Utenti e computer di Active Directory.
  
##### Creazione e protezione delle directory dati IAS
  
È necessario creare directory di dati nelle unità dei server IAS per archiviare i dati di configurazione e del file di registro IAS. Eseguire le procedure descritte di seguito al prompt dei comandi su ciascun server IAS per creare e proteggere le directory dati IAS. In alternativa, è possibile utilizzare lo script batch fornito per automatizzare questa procedura.
  
**Per creare e proteggere le directory dati IAS**
  
-   Eseguire i comandi indicati di seguito, sostituendo WODGROVEBANK con il nome NetBIOS del proprio dominio:
  
    -   md D:\\IASConfig
  
    -   md D:\\IASLogs
  
    -   cacls D:\\IASConfig /G system:F administrators:F "Backup Operators":C
  
    -   cacls D:\\IASLogs /G system:F administrators:F "Backup Operators":C "WOODGROVEBANK\\IAS Security Auditors":C
  
Inoltre, è necessario condividere la directory D:\\IASLogs con IAS Security Auditors, in modo che sia possibile accedere ai dati del Registro richieste di RADIUS in modalità remota.
  
**Per condividere in modo protetto la directory IAS log**
  
-   Eseguire il comando indicato di seguito, sostituendo WODGROVEBANK con il nome NetBIOS del proprio dominio:
  
    net share IASLogs=D:\\IASLogs /GRANT:"WOODGROVEBANK\\IAS Security Auditors",CHANGE
  
È stato creato un file batch facoltativo contenente i comandi precedenti, ma sarà necessario modificarlo affinché includa il nome NetBIOS corretto del proprio dominio.
  
**Per modificare ed eseguire il file batch per la creazione, la protezione e la condivisione delle directory dati IAS**
  
1.  Utilizzare Blocco note per modificare il file C:\\MSSScripts\\IAS\_Data.BAT e sostituire WOODGROVEBANK con il nome NetBIOS del proprio dominio.
  
2.  Eseguire il file batch eseguendo il seguente comando al prompt dei comandi:
  
    C:\\MSSScripts\\IAS\_Data.BAT
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione del server IAS primario
  
È necessario selezionare uno dei server IAS nel proprio ambiente come server primario. Configurare questo server prima degli altri server IAS e utilizzarlo come modello per configurare le impostazioni sugli altri server IAS.
  
#### Configurazione della registrazione delle richieste di account e di autenticazione
  
Per impostazione predefinita il Servizio autenticazione Internet non registra le richieste di account e di autenticazione RADIUS. Se possibile, abilitare entrambi i tipi di registro richieste, per assicurare che gli eventi di protezione vengano registrati per essere analizzati in un secondo momento. Inoltre, la propria azienda può avere l'esigenza di utilizzare i dati di contabilità per scopi di fatturazione.
  
**Nota:** la registrazione delle richieste di RADIUS influenza le prestazioni del server, pertanto sono necessarie alcune procedure per assicurare che i registri non riempiano i dischi dei dati. Per ulteriori informazioni sulla pianificazione della capacità, vedere il capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili", per le procedure di archiviazione ed eliminazione dei file di registro consultare il capitolo 3, "Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili".
  
**Configurazione della registrazione di richiesta accounting e di autenticazione sui server IAS**
  
1.  Utilizzare lo snap-in MMC Servizio autenticazione Internet per selezionare **Registrazione Accesso remoto**, quindi visualizzare le proprietà del metodo di registrazione **File locale**.
  
2.  Selezionare le richieste di **Accounting** (ad esempio, inizio e fine accounting) e le richieste di **autenticazione** (ad esempio, concessione di accesso o rifiuto di accesso).
  
    **Nota:** questa guida non abilita la registrazione di richieste di stato periodico. Tuttavia, questo tipo di registrazione può essere necessario per tenere traccia delle informazioni sulla sessione di rete dell'utente. Per ulteriori informazioni, consultare il capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili".
  
3.  Assicurarsi che la directory del file di registro sia D:\\IASLogs e che sia selezionato il formato file **Formato file compatibile con database**.
  
Utilizzando il formato file **Formato file compatibile con database,** è possibile importare i registri delle richieste direttamente nei database, quali Microsoft Access e Microsoft SQL Server™ 2000, semplificando l'esecuzione di query e la creazione di report.
  
#### Configurazione di IAS per l'accesso alle reti LAN senza fili e altre applicazioni di rete
  
Nella prima parte del capitolo, sono state configurate le impostazioni di base di IAS. Nella seconda parte viene descritta la modalità di replicazione delle impostazioni dal primo server IAS agli altri server. Prima di replicare queste impostazioni, è necessario configurare i criteri di accesso remoto e altre impostazioni proprie delle applicazioni in uso. Il capitolo 9, "Implementazione della protezione di reti LAN senza fili" descrive come configurare IAS per le reti LAN. Dopo aver configurato il primo server, è possibile tornare a questo capitolo e seguire le procedure per replicare le impostazioni IAS in altri server.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Distribuzione della configurazione a più server IAS
  
È possibile utilizzare il comando **netsh** per esportare parti della configurazione di IAS in file di testo. È possibile esportare individualmente le seguenti aree di configurazione:
  
-   Impostazioni del server
  
-   Configurazione di registrazione
  
-   Criteri di accesso remoto
  
-   Criteri richiesta di connessione
  
-   Client RADIUS
  
-   Configurazione completa
  
È possibile utilizzare questi file di testo per trasferire impostazioni di configurazione comuni in più server IAS, in modo da garantire una configurazione coerente e una maggiore velocità di distribuzione. Le seguenti sezioni di configurazione possono essere comuni a server con ruoli simili:
  
-   Configurazione server
  
-   Impostazioni di registrazione
  
-   Criteri di accesso remoto
  
-   Criteri di richiesta di connessione
  
È necessario configurare gli elementi precedenti solo sul server IAS primario, quindi utilizzare il comando **netsh** per esportare tali elementi in file di testo, che potranno essere importati in server IAS aggiuntivi con ruoli simili. In tal modo, si assicura che i file di testo di configurazione per impostazioni di configurazione simili siano sincronizzati in tutti i server.
  
Ciascun server IAS contiene informazioni di configurazione dei client RADIUS con segreti condivisi che in genere sono univoci per ciascun server. Pertanto, è necessario eseguire la configurazione e il backup di tali informazioni separatamente su ciascun server.
  
**Avviso:** l'utilizzo di **netsh** per eseguire un'immagine completa della memoria crea un file di testo di configurazione con informazioni relative a segreti condivisi di RADIUS potenzialmente riservate. In questa guida vengono illustrate le modalità di distribuzione delle impostazioni e di esecuzione di backup senza utilizzare un'immagine completa della memoria delle impostazioni IAS. Se si decide di utilizzare file di testo di configurazione dell'immagine completa della memoria, assicurarsi di gestirli e memorizzarli secondo le procedure previste per i dati riservati, poiché questi file contengono informazioni che consentono a chiunque di accedere alla rete.
  
Le sezioni seguenti descrivono la procedura per il trasferimento della configurazione dal server IAS primario ai server IAS aggiuntivi con ruoli simili. In questa fase è possibile replicare le impostazioni, ma fino ad ora sono state apportate solo modifiche minime alla configurazione dei server IAS. È preferibile ripetere la procedura di replica dopo che saranno state apportate maggiori modifiche alla configurazione IAS seguendo le istruzioni del capitolo successivo, quali la creazione di criteri di accesso alla rete e l'aggiunta di clienti RADIUS.
  
#### Esportazione della configurazione del server IAS primario
  
L'esportazione della configurazione del server IAS primario è necessaria per trasferire le impostazioni a server IAS aggiuntivi utilizzati in questa soluzione.
  
I file batch possono automatizzare l'esportazione delle aree comuni di configurazione IAS per il backup e per aiutare la distribuzione delle impostazioni IAS su più server IAS con lo stesso ruolo. Quando si creano file batch per la distribuzione delle impostazioni, includere solo i seguenti tipi di impostazioni che possono essere trasferiti attraverso server IAS:
  
-   Configurazione server
  
-   Impostazioni di registrazione
  
-   Criteri di accesso remoto
  
-   Criteri di richiesta di connessione
  
**Per esportare la configurazione comune nel server IAS primario**
  
-   Al prompt dei comandi digitare il comando seguente:
  
    C:\\MSSScripts\\IASExport.bat
  
Questo file batch contiene una serie di comandi **netsh** che consentono di esportare le informazioni comuni relative alla configurazione in file di testo di configurazione nella directory D:\\IASConfig.
  
#### Caricamento del backup della configurazione dal server primario
  
IAS utilizza il comando **netsh** per trasferire lo stato di configurazione da un server all'altro. In tal modo, viene accelerata la distribuzione e si riducono le possibilità di errore durante una distribuzione multiserver. I file di testo della configurazione del server IAS primario creati precedentemente ora possono essere utilizzati per caricare la configurazione sul server IAS secondario e qualsiasi altro  server IAS filiale.
  
Per caricare il file di testo della configurazione esportata dal server IAS primario ad altri server IAS, procedere come segue.
  
**Per caricare la configurazione comune dal server IAS primario ad altri server IAS**
  
1.  Copiare tutti i file di configurazione dalla directory D:\\IASConfig sul server IAS primario alla directory D:\\IASConfig sugli altri server IAS.
  
2.  Utilizzare il file batch riportato di seguito per caricare la configurazione dai file di testo di configurazione del server IAS primario:
  
    C:\\MSSScripts\\IASImport.bat
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Se sono state eseguite tutte le procedure illustrate in questo capitolo, dovrebbero essere state completate le attività seguenti:
  
-   Le impostazioni di base per un server IAS primario installate e configurate.
  
-   Un server IAS secondario installato e configurato.
  
-   Un server IAS filale facoltativo installato e configurato.
  
-   Gruppi amministrativi configurati utilizzati per la gestione dei server IAS.
  
A questo punto, si è pronti per configurare le impostazioni specifiche per reti WLAN descritte nel capitolo 9, "Implementazione della protezione di reti LAN senza fili". Quindi, potrà essere necessario ritornare alla parte finale di questo capitolo per replicare le impostazioni IAS che verranno configurate nel prossimo capitolo.
  
A questo punto, è anche consigliabile leggere le parti rilevanti del capitolo 12, "Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili", che contiene informazioni fondamentali per mantenere funzionante l'infrastruttura RADIUS in modo sicuro e affidabile.
  
#### Ulteriori informazioni
  
-   CAPICOM può essere scaricato dall'[area di download del sito Web Microsoft](http://www.microsoft.com/downloads/details.aspx?displaylang=en&familyid=860ee43a-a843-462f-abb5-ff88ea5896f6) all'indirizzo www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=860EE43A-A843-462F-ABB5-FF88EA5896F6. In ogni caso, è consigliabile ricercare "CAPICOM" nell'area di download del sito Web Microsoft per accertarsi di individuare la versione più recente:
  
-   La [*Guida per la protezione di Windows Server 2003*](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en) può essere scaricata all'indirizzo http://www.microsoft.com/downloads/details.aspx?FamilyID=8a2643c1-0685-4d89-b655-521ea6c7b4db&DisplayLang;=en (in inglese).
  
-   Il capitolo "Internet Authentication Service" della [*documentazione tecnica su Windows Server 2003*](http://technet.microsoft.com/en-us/library/cc759100.aspx). Questa guida è reperibile all'indirizzo http://technet.microsoft.com/en-us/library/cc759100.aspx (in inglese).
  
-   Il capitolo "[Deploying IAS](http://technet.microsoft.com/en-us/library/cc738717.aspx)" incluso in *Windows Server 2003 Deployment Kit* è disponibile all'indirizzo: http://technet.microsoft.com/en-us/library/cc738717.aspx (in inglese).
  
-   I requisiti hardware per il programma di logo di Windows sono descritti nella pagina "[FAQ for Windows Logo Program for Hardware](http://www.microsoft.com/whdc/winlogo/logofaq.mspx)" all'indirizzo www.microsoft.com/whdc/winlogo/logofaq.mspx (in inglese).
  
-   L'articolo ["Microsoft Baseline Security Analyzer V1.2"](http://www.microsoft.com/technet/security/tools/mbsahome.mspx) è reperibile all'indirizzo www.microsoft.com/technet/security/tools/mbsahome.mspx (in inglese).
  
-   Le tecnologie WLAN 802.1X sono descritte nell'articolo ["Windows XP Wireless Deployment Technology and Component Overview"](http://technet.microsoft.com/en-us/library/bb457015.aspx) all'indirizzo http://technet.microsoft.com/en-us/library/bb457015.aspx (in inglese)
  
[](#mainsection)[Inizio pagina](#mainsection)
