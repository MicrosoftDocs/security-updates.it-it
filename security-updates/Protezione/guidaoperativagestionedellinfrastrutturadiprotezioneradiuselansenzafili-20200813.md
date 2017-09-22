---
TOCTitle: 'Guida operativa - Gestione dell''infrastruttura di protezione RADIUS e LAN senza fili'
Title: 'Guida operativa - Gestione dell''infrastruttura di protezione RADIUS e LAN senza fili'
ms:assetid: '590b5abd-a42a-49a7-a467-657389b29673'
ms:contentKeyID: 20200813
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536213(v=TechNet.10)'
---

Capitolo 12: Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili
===============================================================================

Pubblicato: 11 ottobre 2004 | Aggiornato: 24/11/2004

##### In questa pagina

[](#ejaa)[Introduzione](#ejaa)
[](#eiaa)[Attività fondamentali di manutenzione](#eiaa)
[](#ehaa)[Tecnologia richiesta nella Guida operativa](#ehaa)
[](#egaa)[Ruoli amministrativi di RADIUS e della protezione WLAN](#egaa)
[](#efaa)[Attività della fase operativa](#efaa)
[](#eeaa)[Attività della fase di supporto](#eeaa)
[](#edaa)[Attività della fase di ottimizzazione](#edaa)
[](#ecaa)[Attività della fase di modifica](#ecaa)
[](#ebaa)[Tabelle di configurazione](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Introduzione

In questo capitolo, vengono descritte le procedure operative necessarie per la gestione dell'infrastruttura RADIUS (Remote Authentication Dial-In User Service) e della protezione WLAN implementate nel contesto della soluzione *Protezione delle reti LAN senza fili*. La struttura si basa sulle categorie MOF (Microsoft Operations Framework) e sui concetti discussi nel capitolo 10, “Introduzione alla Guida operativa”.

Lo scopo di questo capitolo è di consentire l'implementazione di un sistema di gestione completo per l'infrastruttura RADIUS e la protezione WLAN, incluse tutte le attività di configurazione necessarie per avviare il monitoraggio e la manutenzione del sistema. In questo capitolo, vengono inoltre descritte le attività operative periodiche per mantenere l'infrastruttura in buono stato di funzionamento, nonché le procedure per affrontare i problemi di supporto, gestire le modifiche all'ambiente e ottimizzare le prestazioni del sistema.

Il capitolo comprende due parti principali. La prima parte è composta da due sezioni: "Attività fondamentali di manutenzione" e "Ruoli amministrativi di RADIUS e della protezione WLAN". Sono brevi sezioni e devono essere lette per intero, in quanto forniscono informazioni essenziali sulla configurazione necessaria a ottimizzare la gestione dell’ambiente per il sistema in uso. La restante parte del capitolo è costituita principalmente da materiale di riferimento. Dopo la distribuzione del sistema, sarà necessario implementare alcune delle attività descritte nelle sezioni di riferimento. Per ottenere informazioni dettagliate su queste attività, consultare la sezione "Attività fondamentali di manutenzione".

Sebbene non sia necessario sapere tutti i dettagli descritti nelle sezioni di riferimento, è preferibile esaminare queste sezioni brevemente per conoscerne il contenuto a grandi linee e poter localizzare rapidamente gli argomenti in futuro.

#### Prima di iniziare

È consigliabile acquisire familiarità con i concetti MOF descritti nel capitolo 10, "Introduzione alla Guida operativa", anche se non è necessaria una conoscenza approfondita di MOF.

In particolare, è preferibile conoscere i concetti di RADIUS e del Servizio autenticazione Internet (IAS) Microsoft®, nonché quelli di 802.11, 802.1X e EAP-TLS. Per ulteriori informazioni su questi argomenti tecnici, vedere i riferimenti nei capitoli della Guida alla pianificazione.

È inoltre consigliabile conoscere Microsoft Windows® 2000 Server (o versioni successive) nelle seguenti aree:

-   Operazioni di base e manutenzione di Microsoft Windows Server™ 2003, compreso l’utilizzo di strumenti quali Visualizzatore eventi, Gestione computer e NTBackup.

-   Attività e concetti relativi al servizio directory Active Directory®, inclusi struttura di Active Directory, strumenti, gestione degli utenti, dei gruppi e degli altri oggetti di Active Directory e utilizzo dei Criteri di gruppo.

-   Concetti alla base della protezione dei sistemi Windows, quali utenti, gruppi, controllo, elenchi di controllo di accesso, utilizzo dei modelli di protezione e applicazione dei modelli di protezione mediante Criteri di gruppo o strumenti della riga di comando.

-   Amministrazione del Servizio autenticazione Internet.

-   Windows Scripting Host e il linguaggio Microsoft Visual Basic® Scripting Edition (VBScript). Anche se non è essenziale, la conoscenza della sintassi di programmazione batch  può contribuire a trarre il massimo vantaggio dagli script forniti.

Inoltre, prima di prendere in esame questo capitolo, è preferibile leggere i capitoli della Guida alla pianificazione e della Guida alla creazione e comprendere a fondo l’architettura e la progettazione della soluzione.

#### Panoramica dei capitoli

L'elenco seguente descrive le sezioni principali di questo capitolo.

-   **Attività fondamentali di manutenzione** Contiene due tabelle che elencano le attività necessarie per impostare il sistema di gestione e per svolgere la regolare manutenzione.

-   **Ruoli amministrativi** Vengono descritti i ruoli amministrativi utilizzati nella soluzione, i privilegi di ciascun ruolo, le modalità di associazione dei ruoli ai cluster di ruoli MOF e i gruppi di protezione amministrativa definiti per la soluzione.

-   **Attività della fase operativa** Questa sezione comprende tutte le attività relative alla normale manutenzione dell'infrastruttura RADIUS e della protezione WLAN, nonché le operazioni relative a monitoraggio, backup, directory e protezione.

-   **Attività della fase di supporto** Include tutte le procedure relative al ripristino in seguito a problemi di sistema. Questa sezione contiene informazioni relative al ripristino da backup e alle operazioni necessarie in caso di errori del server IAS.

-   **Attività della fase di ottimizzazione** Comprende alcune procedure di pianificazione della gestione della capacità.

-   **Attività della fase di modifica** Comprende attività comuni relative all'apporto di modifiche alla configurazione del server IAS e alla loro distribuzione nella produzione in maniera controllata. Sono inoltre incluse le procedure di raccolta e gestione di essenziali informazioni di configurazione sul server IAS.

-   **Risoluzione dei problemi** Questa sezione comprende procedure utili per risolvere i problemi comuni che possono verificarsi nelle infrastrutture RADIUS e nella protezione WLAN. Contiene, inoltre, descrizioni di strumenti e procedure utili per tenere traccia delle attività dei vari componenti e risolvere eventuali problemi.

-   **Tabelle di configurazione** Contiene un sottoinsieme di parametri di configurazione utilizzati nei capitoli della Guida alla creazione. Questi valori sono utilizzati come esempi nelle procedure.

-   **Ulteriori informazioni** Elenca fonti di informazioni aggiuntive a cui si fa riferimento nel testo.

[](#mainsection)[Inizio pagina](#mainsection)

### Attività fondamentali di manutenzione

In questa sezione sono elencate le attività principali da eseguire per un corretto funzionamento dell'infrastruttura RADIUS e della protezione WLAN. Le attività sono elencate in due tabelle: attività iniziali di configurazione e attività operative ordinarie. I nomi delle attività elencate nelle tabelle sono descritti dettagliatamente più avanti nel documento. Le attività sono raggruppate in base alla fase MOF, mentre la funzione di gestione dei servizi (SMF, Service Management Function) cui appartiene l'attività è indicata accanto a questa, in modo che sia più semplice trovarla.

In questa sezione, è incluso anche un elenco degli strumenti e delle tecnologie utilizzate nelle procedure di questo capitolo.

#### Attività iniziali di configurazione

Nella tabella seguente sono elencate le attività da eseguire per rendere operative l'infrastruttura RADIUS e la protezione WLAN. Le attività da eseguire possono variare a seconda degli standard e delle procedure operative di un'azienda. Esaminare le attività per decidere se eseguirle o meno. Potrebbe essere necessario ripetere alcune attività in un secondo momento. Ad esempio, se viene installato un nuovo server IAS, sarà necessario configurare le operazioni di backup e di monitoraggio per questo server.

**Tabella 12.1. Attività iniziali di configurazione**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome attività</p></th>
<th><p>Funzione di gestione dei servizi (SMF)</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p><strong>Fase di operatività</strong></p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Aggiunta di client RADIUS ai server IAS</p></td>
<td style="border:1px solid black;"><p>Amministrazione di rete</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Abilitazione delle impostazioni di rete senza fili sui computer</p></td>
<td style="border:1px solid black;"><p>Amministrazione dei servizi directory</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Aggiunta di computer e utenti ai gruppi di criteri di accesso remoto</p></td>
<td style="border:1px solid black;"><p>Amministrazione dei servizi directory</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Classificazione degli avvisi di monitoraggio</p></td>
<td style="border:1px solid black;"><p>Monitoraggio e controllo dei servizi</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Monitoraggio dei vincoli di capacità di IAS</p></td>
<td style="border:1px solid black;"><p>Monitoraggio e controllo dei servizi</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Configurazione dell'esportazione della configurazione IAS</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Esportazione della configurazione dei client RADIUS</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Configurazione del backup delle directory di dati IAS</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Test del backup di IAS</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><strong>Fase di ottimizzazione</strong></p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Determinazione del carico massimo sul server IAS</p></td>
<td style="border:1px solid black;"><p>Gestione della capacità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Determinazione dei requisiti di archiviazione e di backup per un server IAS</p></td>
<td style="border:1px solid black;"><p>Gestione della capacità</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><strong>Fase di modifica</strong></p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Gestione degli aggiornamenti del sistema operativo</p></td>
<td style="border:1px solid black;"><p>Gestione delle modifiche<br />
Gestione del rilascio</p></td>
</tr>
</tbody>
</table>
<p> </p>

#### Attività di manutenzione

Nella tabella seguente sono elencate le attività da eseguire regolarmente per mantenere in perfetto stato di funzionamento l'infrastruttura RADIUS e la protezione WLAN. La tabella può essere utilizzata nella pianificazione delle risorse necessarie e nella pianificazione operativa dell'amministrazione del sistema.

È possibile che esistano alcune attività che non occorre eseguire; tuttavia, prima di decidere è opportuno verificarne i dettagli. Inoltre, per alcune attività sarà necessaria l'esecuzione occasionale, mentre per altre è bene pianificarne l'esecuzione. Ad esempio, se viene aggiunto un client RADIUS a un server IAS, sarà necessario eseguire un'esportazione/backup della configurazione del server anche se questa non è pianificata. Tali attività vengono elencate nella colonna Frequenza. Dipendenze di questo tipo vengono anche annotate nei dettagli stessi dell'attività.

**Tabella 12.2. Attività ordinarie di manutenzione**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome attività</p></th>
<th><p>Frequenza</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Aggiunta di client RADIUS ai server IAS</p></td>
<td style="border:1px solid black;"><p>Ogni volta che alla rete vengono aggiunti punti di accesso senza fili</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Rimozione di client RADIUS dai server IAS</p></td>
<td style="border:1px solid black;"><p>Ogni volta che dei punti di accesso senza fili vengono rimossi dalla rete</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Abilitazione delle impostazioni di rete senza fili sui computer</p></td>
<td style="border:1px solid black;"><p>Ogni volta che vengono aggiunti dei computer alla rete</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Aggiunta di computer e utenti ai gruppi di criteri di accesso remoto</p></td>
<td style="border:1px solid black;"><p>Ogni volta che ai dipendenti viene concesso l'accesso alla rete WLAN</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Esportazione della configurazione dei client RADIUS</p></td>
<td style="border:1px solid black;"><p>Ogni volta che alla rete vengono aggiunti punti di accesso senza fili</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Test del backup di IAS</p></td>
<td style="border:1px solid black;"><p>Ogni mese</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Accesso ai registri delle richieste RADIUS IAS</p></td>
<td style="border:1px solid black;"><p>Ogni giorno oppure ogni settimana<br />
(a seconda dei requisiti di protezione)</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Verifica delle voci del Registro eventi di autenticazione RADIUS IAS</p></td>
<td style="border:1px solid black;"><p>Ogni giorno oppure ogni settimana<br />
(a seconda dei requisiti di protezione)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Archiviazione ed eliminazione delle voci del registro RADIUS IAS</p></td>
<td style="border:1px solid black;"><p>Ogni mese</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Gestione degli aggiornamenti del sistema operativo</p></td>
<td style="border:1px solid black;"><p>Ogni giorno</p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Tecnologia richiesta nella Guida operativa
  
Nelle tabelle riportate di seguito sono elencati gli strumenti o le tecnologie utilizzati per le procedure descritte in questo capitolo.
  
**Tabella 12.3. Tecnologia richiesta**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome</p></th>  
<th><p>Origine</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Snap-in MMC Utenti e computer di Active Directory</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Script MSS</p></td>
<td style="border:1px solid black;"><p>Questa soluzione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Editor di testo</p></td>
<td style="border:1px solid black;"><p>Blocco note - Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Servizio Utilità di pianificazione di Windows</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>SchTasks.exe</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Utilità di backup di Windows</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Visualizzatore eventi</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Performance Monitor</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Net.exe</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Console avvisi operativi</p></td>
<td style="border:1px solid black;"><p>Microsoft Operations Manager (MOM)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Supporti rimovibili per l'archiviazione esterna ai computer</p></td>
<td style="border:1px solid black;"><p>Disco floppy, CD riscrivibile o nastro</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Backup server IAS</p></td>
<td style="border:1px solid black;"><p>Servizio di backup di rete<br />
oppure<br />
Periferica di backup locale</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Console di gestione Criteri di gruppo</p></td>
<td style="border:1px solid black;"><p>Download Web da Microsoft.com</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>IASParse</p></td>
<td style="border:1px solid black;"><p>Strumenti di supporto di Windows Server 2003</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Microsoft Access 2002</p></td>
<td style="border:1px solid black;"><p>Microsoft Office XP</p></td>
</tr>  
</tbody>  
</table>
  
**Tabella 12.4. Tecnologia consigliata**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome</p></th>  
<th><p>Origine</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Console avvisi operativi</p></td>
<td style="border:1px solid black;"><p>Microsoft Operations Manager o altro sistema di monitoraggio dei servizi</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Infrastruttura di posta elettronica per gli avvisi operativi (in alternativa a MOM)</p></td>
<td style="border:1px solid black;"><p>Server e client SMTP/POP3/IMAP, ad esempio Microsoft Exchange Server e Microsoft Outlook®</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Eventquery.vbs</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Strumenti per la pianificazione della capacità</p></td>
<td style="border:1px solid black;"><p>Microsoft Operations Manager o altri strumenti per la pianificazione della capacità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sistema di distribuzione degli aggiornamenti per la protezione</p></td>
<td style="border:1px solid black;"><p>Microsoft Systems Management Server<br />
oppure<br />
Microsoft Software Update Services</p></td>
</tr>
</tbody>
</table>
<p> </p>

[](#mainsection)[Inizio pagina](#mainsection)

### Ruoli amministrativi di RADIUS e della protezione WLAN

I ruoli coinvolti nella gestione di un'infrastruttura RADIUS e della protezione WLAN sono molteplici. Nelle due sezioni che seguono tali ruoli sono suddivisi in due categorie: principali e di supporto.

#### Ruoli RADIUS e WLAN fondamentali

I ruoli riportati nella seguente tabella sono centrali nella gestione di un'infrastruttura RADIUS e della protezione WLAN.

**Tabella 12.5. Ruoli fondamentali per l'infrastruttura RADIUS e la protezione WLAN**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome del ruolo</p></th>
<th><p>Ambito</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore del Servizio di autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile dell'amministrazione e della configurazione generale di IAS per l'organizzazione di grandi dimensioni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Controllore del Servizio di autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile della verifica, dell'archiviazione e dell'eliminazione dei registri RADIUS nei computer server IAS</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Operatori di backup del Servizio autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile del backup e del ripristino dello stato di configurazione IAS e dei dati cronologici</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Personale del supporto tecnico WLAN</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile principale del personale del supporto tecnico per la risoluzione dei problemi WLAN</p></td>
</tr>  
</tbody>  
</table>
  
#### Ruoli di supporto per l'infrastruttura RADIUS e la protezione WLAN
  
I ruoli operativi riportati nella seguente tabella non sono centrali nella gestione dell'infrastruttura RADIUS e della protezione WLAN, ma forniscono funzioni di supporto ai ruoli fondamentali.
  
**Tabella 12.6. Ruoli di supporto per l'infrastruttura RADIUS e la protezione WLAN**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Nome del ruolo</p></th>  
<th><p>Ambito</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Operatore di monitoraggio</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile del monitoraggio degli eventi</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Pianificatore della capacità</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile dell'analisi delle prestazioni e del carico per la previsione dei requisiti di capacità futuri</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore di Active Directory</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile della configurazione e del supporto dell'infrastruttura Active Directory</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Gestione delle operazioni di Active Directory</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile della manutenzione quotidiana della directory, ad esempio della manutenzione dei gruppi di protezione, della creazione degli account e così via</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore desktop</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile della configurazione e del supporto dei computer desktop</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Consiglio di approvazione delle modifiche</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Rappresentanti aziendali e tecnici ai quali viene richiesto di approvare le modifiche all'infrastruttura</p></td>
</tr>  
</tbody>  
</table>
  
#### Mapping dei ruoli con i gruppi di protezione
  
Nella tabella seguente sono elencati i gruppi di protezione definiti per questa soluzione e vengono brevemente descritte le funzionalità o le autorizzazioni di ogni gruppo.
  
Per i server IAS, i gruppi di protezione di dominio e locali vengono utilizzati per applicare le autorizzazioni specifiche di ciascun ruolo. Gli account di dominio sono utilizzati per popolare i gruppi di ruoli. I singoli account possono essere membri di più gruppi di ruoli se questa condizione è supportata dai criteri IT e di protezione dell'organizzazione.
  
**Tabella 12.7. Mapping dei ruoli RADIUS e della protezione WLAN con i gruppi di protezione**

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
<th><p>Nome del ruolo</p></th>  
<th><p>Gruppo di protezione di dominio</p></th>  
<th><p>Gruppo di protezione locale</p></th>  
<th><p>Privilegi</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore del Servizio di autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>IAS Admins</p></td>
<td style="border:1px solid black;"><p>Administrators</p></td>
<td style="border:1px solid black;"><p>Funzionalità di amministrazione complete sul server IAS, inclusi l'avvio e l'arresto del servizio IAS e la modifica della configurazione di tale servizio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Controllori del Servizio autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>IAS Security Auditors</p></td>
<td style="border:1px solid black;"><p>N/D</p></td>
<td style="border:1px solid black;"><p>Capacità di leggere ed eliminare i file registro delle richieste RADIUS nel volume di registrazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>IAS Backup Operators</p></td>
<td style="border:1px solid black;"><p>N/D</p></td>
<td style="border:1px solid black;"><p>Backup Operators</p></td>
<td style="border:1px solid black;"><p>Backup e ripristino completi dello stato del sistema operativo e dei dati di configurazione IAS</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Personale del supporto tecnico WLAN</p></td>
<td style="border:1px solid black;"><p>N/D</p></td>
<td style="border:1px solid black;"><p>N/D</p></td>
<td style="border:1px solid black;"><p>Collabora con il gruppo di amministratori di IAS per risolvere i problemi di autenticazione IAS (in alcuni casi può disporre delle autorizzazioni di lettura per le stesse risorse dei controllori della protezione IAS).</p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase operativa
  
Nella fase operativa sono inclusi gli standard operativi IT, i processi e le procedure che vengono applicati regolarmente alle soluzioni di servizi per raggiungere e mantenere i livelli di servizio entro parametri predeterminati. L'obiettivo della fase operativa è la previsione con grande anticipo dell'esecuzione di attività quotidiane, con o senza l'intervento di utenti.
  
In questa sezione vengono fornite le informazioni relative alle seguenti funzioni SMF:
  
-   Amministrazione di rete
  
-   Amministrazione dei servizi directory
  
-   Amministrazione della protezione
  
-   Gestione dell'archiviazione
  
-   Monitoraggio e controllo dei servizi
  
-   Pianificazione dei processi
  
Non esistono attività per le restanti funzioni SMF:
  
-   Gestione dei sistemi
  
-   Gestione della rete
  
-   Gestione della stampa e degli output
  
    **Nota:** la descrizione dell'attività comprende le seguenti informazioni riassuntive: requisiti di protezione, frequenza e requisiti di tecnologia.
  
#### Amministrazione di rete
  
Il ruolo di amministrazione di rete riguarda la progettazione e la manutenzione dei componenti fisici che costituiscono la rete dell'organizzazione, ad esempio i server, i router, gli switch e i firewall. Nel caso delle reti senza fili, sono inclusi anche i punti di accesso senza fili e i server RADIUS per supportarli.
  
##### Aggiunta di client RADIUS ai server IAS
  
Per eseguire l'autenticazione e l'accounting con i server IAS occorre che i punti di accesso senza fili siano autorizzati. L’attivazione di nuovi punti di accesso senza fili come client RADIUS è una delle poche modifiche incrementali che è necessario apportare in un server di produzione IAS distribuito. Questa attività autorizza i punti di accesso senza fili a partecipare alle operazioni di autenticazione e accounting RADIUS con il server IAS. Eseguire questa attività ogni volta che nuovi punti di accesso senza fili vengono distribuiti e configurati per la partecipazione all'autenticazione di rete.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Amministratori IAS.
  
-   **Frequenza**: ogni volta che alla rete vengono aggiunti nuovi punti di accesso senza fili.
  
-   **Requisiti di tecnologia**:
  
    -   Snap-in MMC IAS
  
    -   Script MSS (per il comando di script GenPwd)
  
    -   Unità disco floppy o altra unità per supporti rimovibili e scrivibili
  
    -   Disco floppy o altri supporti rimovibili e scrivibili
  
###### Dettagli relativi all'attività
  
Usare una password casuale (segreto) univoca per ogni punto di accesso senza fili durante l'aggiunta del punto di accesso a ciascun server IAS. L'utilizzo degli stessi segreti RADIUS per più punti di accesso senza fili aumenta il rischio che il segreto condiviso non resti tale a lungo.
  
Windows Server 2003 Enterprise Edition consente agli amministratori l'aggiunta globale di punti di accesso senza fili a IAS aggiungendo una subnet client RADIUS dedicata e utilizzando un segreto condiviso per tutti i punti di accesso di questa subnet. Tuttavia, sebbene semplifichi la gestione di questi segreti, tale metodo offre una minore protezione rispetto a quella fornita dall'utilizzo di segreti univoci.
  
Questa soluzione implementa, mediante la crittografia, segreti casuali generati dallo script GenPwd incluso in queste guide.
  
**Per aggiungere singoli client RADIUS al server IAS**
  
1.  Dallo snap-in MMC IAS, fare clic con il pulsante destro del mouse sulla cartella **Client RADIUS**, quindi su **Nuovo client RADIUS**.
  
2.  Immettere il **Nome descrittivo** e l**’**indirizzo client (IP o DNS) del punto di accesso senza fili. È consigliabile utilizzare gli indirizzi IP al posto dei nomi DNS, poiché il servizio IAS tenterà di risolvere l’indirizzo di ogni client RADIUS all’avvio del server. Negli ambienti con numerosi punti di accesso senza fili, la risoluzione di client tramite i nomi DNS può pregiudicare il tempo di avvio. Fare clic su **Avanti**.
  
3.  Selezionare **Standard RADIUS** come attributo client-fornitore e immettere il segreto condiviso per questo particolare punto di accesso senza fili.
  
    **Nota:** nei passaggi che seguono è previsto l'utilizzo di un disco floppy o di altri supporti rimovibili e scrivibili. Individuare un disco floppy formattato ed etichettarlo con "Client RADIUS per *&lt;nome server&gt;*".
  
4.  È possibile utilizzare lo script GenPwd qui incluso per generare un segreto casuale sicuro da utilizzare una sola volta per ogni punto di accesso configurato come client RADIUS. GenPwd genererà un segreto e lo archivierà in un file Clients.txt insieme a un nome descrittivo per ciascun client RADIUS. GenPwd aggiunge automaticamente le informazioni a un file Clients.txt nella directory corrente sotto forma di valori separati da virgola. Tuttavia, se si dispone di un metodo per generare segreti RADIUS sicuri, è possibile utilizzarlo al posto di GenPwd nei passaggi indicati di seguito.
  
    **Nota:** GenPwd utilizza una funzione CryptoAPI per generare una stringa crittografica generata in maniera casuale con codifica Base64. Non utilizza la funzionalità di generazione di numeri casuali VBScript.
  
5.  Aprire il prompt dei comandi e passare alla directory A:\\. Il percorso della directory nel file system è importante, in quanto le nuove informazioni verranno aggiunte automaticamente al file Clients.txt della directory corrente. Se non esiste un file Clients.txt, ne verrà creato uno.
  
6.  Eseguire il comando seguente. Verificare di sostituire il parametro &lt;*nome\_client&gt;* con il nome descrittivo del punto di accesso senza fili. Può trattarsi di un nome DNS, di un indirizzo IP o di un’altra stringa.
  
    cscript //job:GenPwd C:\\MSSScripts\\wl\_tools.wsf /client:nome\_client
  
    Una volta creato, importare il file delimitato da virgole in un foglio di calcolo o in un’applicazione di database, per consultazioni o modifiche future.
  
    **Importante:** è consigliabile modificare regolarmente i segreti RADIUS di ogni server IAS. Accertarsi di utilizzare GenPwd o un'altra utilità per generare segreti sicuri e archiviare il nuovo segreto e il nome del punto di accesso senza fili nel file Clients.txt. I dati nel file Clients.txt sono estremamente riservati. Non copiare questo file sul server e conservarlo in un luogo sicuro, come ad esempio una cassaforte.
  
7.  Nello snap-in MMC IAS, immettere il segreto condiviso RADIUS nei campi **Segreto condiviso** e **Conferma segreto condiviso**. Selezionare l'**attributo La richiesta deve contenere l'autenticatore del messaggio**, quindi scegliere **Fine**.
  
    **Nota:** alcuni client RADIUS potrebbero richiedere attributi di configurazione specifici del fornitore per funzionare correttamente. Per informazioni sui requisiti degli attributi specifici del fornitore, consultare la documentazione del fornitore.
  
##### Rimozione di client RADIUS dai server IAS
  
La rimozione di punti di accesso senza fili indesiderati utilizzati come client RADIUS è una delle poche modifiche incrementali da apportare a un server IAS di produzione distribuito. Questa attività impedisce al punto di accesso senza fili di partecipare alle operazioni di autenticazione e accounting RADIUS con il server IAS. Eseguire questa attività ogni volta che i punti di accesso senza fili vengono ritirati, in modo da disattivare la capacità di utilizzare i servizi di accounting e autenticazione RADIUS.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo Amministratori IAS.
  
-   **Frequenza**: ogni volta che dei punti di accesso senza fili vengono rimossi dalla rete.
  
-   **Requisiti di tecnologia**:
  
    -   Snap-in MMC IAS
  
    -   Notepad.exe o altro editor di file di testo
  
###### Dettagli relativi all'attività
  
Rimuovere ciascun punto di accesso senza fili in modo indipendente. È necessario eliminare anche la voce corrispondente nel file Clients.txt del disco floppy del client RADIUS memorizzato in un archivio protetto. Il file Clients.txt viene creato mediante la procedura riportata nell'attività "Aggiunta di client RADIUS ai server IAS".
  
**Per rimuovere client RADIUS dal server IAS**
  
1.  Dallo snap-in MMC IAS, selezionare la cartella Client RADIUS.
  
2.  Dal riquadro di destra, selezionare la voce che rappresenta il client RADIUS da rimuovere e premere **Canc**.
  
3.  Quando viene richiesta la conferma, scegliere **Sì**.
  
    **Nota:** nei passaggi che seguono è previsto l'utilizzo di un disco floppy o di altri supporti rimovibili e scrivibili con l'etichetta "Client RADIUS per il server *&lt;nome server&gt;*", creati in una delle sezioni precedenti. Accertarsi di utilizzare il disco corretto, con il server appropriato, per evitare la perdita di dati.
  
4.  Individuare il disco floppy del client RADIUS per questo server e aprire il file A:\\Clients.txt utilizzando Blocco note.
  
5.  Individuare ed eliminare la voce del client RADIUS che si desidera eliminare.
  
#### Amministrazione dei servizi directory
  
I servizi directory consentono a utenti e applicazioni di trovare risorse di rete quali utenti, server, applicazioni, strumenti, servizi e altre informazioni in rete. L'amministrazione dei servizi directory comprende operazioni quotidiane, manutenzione e supporto per la directory di un'organizzazione di grandi dimensioni. L'amministrazione dei servizi directory garantisce a tutti gli utenti autorizzati, mediante procedure semplici e organizzate, l'accesso alle informazioni in rete.
  
##### Abilitazione dell'accesso di utenti e computer alla rete WLAN
  
Per consentire l'accesso alla rete WLAN, è necessario effettuare tre attività separate. Queste attività possono essere controllate tramite l'appartenenza a gruppi di protezione e automatizzate facilmente utilizzando uno script di file di comando (batch), VBScript o Jscript. Tali attività sono documentate separatamente poiché molte organizzazioni le eseguono in fasi diverse della distribuzione WLAN.
  
**Importante:** questa soluzione utilizza gruppi di protezione personalizzati per controllare quali utenti e computer ricevono impostazioni dei criteri e certificati WLAN e per controllare quali utenti e computer sono autorizzati ad accedere alla rete WLAN tramite IAS. Per consentire una distribuzione graduale di certificati, impostazioni dei criteri e accesso alla rete WLAN, per questi tre elementi vengono usati dei gruppi separati. Per evitare questo controllo diretto, è possibile attivare tutti gli utenti e i computer per alcuni o tutti questi elementi. Il modo più facile per attivare tutti gli utenti e i computer è aggiungere Utenti dominio e Computer del dominio al relativo gruppo di registrazione dei certificati, gruppo dei criteri di gruppo WLAN (solo computer) e gruppo di accesso alla rete WLAN.
  
**Per consentire l'accesso alla rete LAN senza fili a un computer**
  
1.  Seguire la procedura "Attivazione della registrazione (o registrazione automatica) di un tipo di certificato per un utente o un computer" nel capitolo 11, aggiungendo l'account del computer al gruppo di registrazione dei certificati **Registrazione automatica autenticazione client - Certificato computer**.
  
2.  Per distribuire le corrette impostazioni di rete al computer, attenersi alla procedura "Abilitazione delle impostazioni di rete senza fili sui computer" più avanti in questa sezione. Aggiungere l'account del computer al gruppo di criteri **Criteri di rete senza fili - Computer**.
  
3.  Per consentire al computer di connettersi alla rete WLAN, seguire la procedura "Aggiunta di computer e utenti ai gruppi di criteri di accesso remoto" più avanti in questa sezione. Aggiungere l'account del computer al gruppo di protezione di accesso remoto **Criteri di accesso remoto - Computer senza fili**.
  
    **Importante:** questi passaggi possono essere eseguiti in qualsiasi ordine. Durante una distribuzione di grandi dimensioni, questi passaggi possono essere effettuati molto prima dell'attivazione dell'hardware WLAN. Il computer *deve* essere riavviato almeno una volta al fine di consentire il ricevimento delle appartenenze ai gruppi assegnate nel corso di queste procedure. Dopo un determinato periodo di tempo, si verifica il timeout del token di accesso del computer, che causa l'aggiornamento delle appartenenze al gruppo; tuttavia, questo processo può richiedere fino a una settimana.  
    Per ricevere le impostazioni di rete senza fili iniziali e il certificato iniziale, il computer *deve* essere connesso a una rete cablata. Il rinnovo dei certificati e le future modifiche alle impostazioni di rete senza fili vengono ricevute tramite la rete WLAN.
  
**Per consentire l'accesso alla rete LAN senza fili a un utente**
  
1.  Seguire la procedura "Attivazione della registrazione (o registrazione automatica) di un tipo di certificato per un utente o un computer" del capitolo 11 aggiungendo l'account dell'utente al gruppo di registrazione dei certificati **Registrazione automatica autenticazione client - Certificato utente**.
  
2.  Assicurarsi che l'utente effettui l'accesso utilizzando un computer autorizzato e configurato per le reti WLAN (come descritto nella procedura precedente). In particolare, il computer deve essere stato configurato con le corrette impostazioni dei criteri WLAN.
  
3.  Per consentire al computer di connettersi alla rete WLAN, seguire la procedura "Aggiunta di computer e utenti ai gruppi di criteri di accesso remoto" più avanti in questa sezione. Aggiungere l'account del computer al gruppo di protezione di accesso remoto **Criteri di accesso remoto - Utenti senza fili**.
  
    **Importante:** questi passaggi possono essere eseguiti in qualsiasi ordine e anche prima di distribuire e attivare l'hardware WLAN. Per ricevere le appartenenze ai gruppi assegnate nel corso di queste procedure, gli utenti *devono* disconnettersi e riconnettersi almeno una volta. Dopo un determinato periodo di tempo, si verifica il timeout del token di accesso dell'utente, che causa l'aggiornamento delle appartenenze al gruppo; tuttavia, questo processo può richiedere fino a una settimana.  
    Affinché gli utenti possano ricevere i certificati iniziali, il computer *deve* essere connesso a una rete cablata. Il rinnovo dei certificati viene ricevuto tramite la rete WLAN.
  
##### Abilitazione delle impostazioni di rete senza fili sui computer
  
La configurazione delle impostazioni di rete senza fili (come le impostazioni 802.11 e 802.1X) nei computer client viene automatizzata mediante Criteri di gruppo di Active Directory. Per controllare quali computer ricevono queste impostazioni di rete senza fili, è necessario aggiungerli ai gruppi di protezione. I gruppi di protezione sono utilizzati per filtrare l'oggetto Criteri di gruppo (GPO) in modo che solo i membri del gruppo ricevano le impostazioni dei criteri. Eseguire questa attività ogni volta che nell'ambiente viene introdotto un nuovo computer che dovrà utilizzare la rete senza fili.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo Amministratori di dominio o autorizzazione all'aggiunta di utenti al gruppo di protezione Criteri di rete senza fili - Computer in Active Directory.
  
-   **Frequenza**: ogni volta che alla rete vengono aggiunti computer portatili.
  
-   **Requisiti di tecnologia**: snap-in MMC Utenti e computer di Active Directory.
  
###### Dettagli relativi all'attività
  
Dopo aver configurato e attivato la rete senza fili, l’aggiunta di computer ai gruppi di protezione che controllano l’applicazione dei criteri è semplice.
  
**Per aggiungere computer al gruppo di protezione Criteri di gruppo della rete senza fili**
  
1.  Nello snap-in MMC Utenti e computer di Active Directory, individuare il gruppo di protezione Criteri di rete senza fili - Computer che corrisponde al criterio della rete senza fili da applicare. È necessario accedere come utente che dispone delle autorizzazioni di modifica dell'appartenenza per il gruppo.
  
2.  Aggiungere il computer al gruppo di protezione selezionato.
  
    **Nota:** per rendere effettiva questa nuova appartenenza al gruppo e applicare i criteri di rete senza fili, è necessario riavviare il computer. La prima volta che un criterio di rete senza fili viene applicato, per ricevere le impostazioni di rete senza fili, il computer *deve* essere connesso a una rete cablata. Le successive modifiche possono essere applicate tramite la rete WLAN.
  
##### Aggiunta di computer e utenti ai gruppi di criteri di accesso remoto
  
L'aggiunta di computer e utenti al gruppo di protezione dei criteri di accesso remoto autorizza l'accesso alla rete WLAN. IAS utilizza l'appartenenza di questo gruppo ai criteri di accesso remoto come condizione per l'accesso. Per ottenere l'autorizzazione di accesso alla rete WLAN è necessario aggiungere computer e utenti ai gruppi di criteri di accesso remoto.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo Amministratori di dominio o autorizzazione alla modifica dell'appartenenza dei gruppi di protezione Criteri di accesso remoto - Utenti senza fili e Criteri di accesso remoto - Computer senza fili in Active Directory.
  
-   **Frequenza**: ogni volta che agli utenti viene concesso l'accesso alla WLAN.
  
-   **Requisiti di tecnologia**: snap-in MMC Utenti e computer di Active Directory.
  
###### Dettagli relativi all'attività
  
Dopo che sono stati creati i gruppi di protezione dei criteri di accesso remoto, l'aggiunta di ulteriori computer e utenti ai gruppi di protezione che controllano l'accesso alla rete WLAN è abbastanza semplice.
  
**Per aggiungere utenti al gruppo di protezione Criteri di accesso di remoto**
  
1.  Accedere a un computer amministrativo come membro del gruppo Amministratori di dominio o come utente con autorizzazione a modificare l'appartenenza del gruppo di protezione Criteri di accesso remoto - Utenti senza fili.
  
2.  Nello snap-in MMC Utenti e computer di Active Directory, individuare il gruppo di protezione Criteri di accesso remoto - Utenti senza fili che corrisponde al criterio di accesso remoto che controlla l'accesso alla rete LAN senza fili.
  
3.  Aggiungere l’utente al gruppo di protezione selezionato.
  
    **Nota:** per ricevere la nuova appartenenza al gruppo e accedere alla rete WLAN, l'utente deve disconnettersi e riconnettersi.
  
**Per aggiungere computer al gruppo di protezione Criteri di accesso di remoto**
  
1.  Accedere a un computer amministrativo come membro del gruppo Amministratori di dominio o come utente con autorizzazione di protezione a modificare l'appartenenza del gruppo di protezione Criteri di accesso remoto - Computer senza fili.
  
2.  Nello snap-in MMC Utenti e computer di Active Directory, individuare il gruppo di protezione Criteri di accesso remoto - Computer senza fili che corrisponde al criterio di accesso remoto che controlla l'accesso alla rete LAN senza fili.
  
3.  Aggiungere il computer al gruppo di protezione selezionato.
  
    **Nota:** per consentire il ricevimento della nuova appartenenza al gruppo e l'accesso alla rete WLAN, è necessario avviare il computer.
  
#### Monitoraggio e controllo dei servizi
  
Il monitoraggio dei servizi consente al personale operativo di osservare la condizione di un servizio IT in tempo reale.
  
Nei punti di questa sezione in cui si fa riferimento a MOM (Microsoft Operations Manager) si presume che la distribuzione di MOM segua le indicazioni della Guida operativa a MOM. Tuttavia, MOM non è necessario ed è utilizzato semplicemente come esempio. Per ulteriori informazioni sulla Guida operativa a MOM, consultare la sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
##### Classificazione degli avvisi di monitoraggio
  
Il sistema di monitoraggio dovrebbe segnalare solo gli avvisi più significativi al personale operativo. Se tutti gli errori secondari vengono passati al livello superiore per produrre avvisi di emergenze, il personale operativo farà confusione tra gli avvisi che sono urgenti e quelli che non lo sono, ma che richiedono un'indagine a più lungo termine.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: nessuno
  
-   **Frequenza**: attività di configurazione
  
-   **Requisiti di tecnologia**: console avvisi operativi (ad esempio MOM).
  
###### Dettagli relativi all'attività
  
In questo documento vengono utilizzate le seguenti categorie di avvisi. Di queste, solo le prime tre (Servizio non disponibile, Violazione della protezione ed Errore critico) producono avvisi sulla console dell'operatore per richiedere un intervento immediato. Gli errori e gli avvisi non sono considerati urgenti e dovrebbero essere comunicati al personale addetto al supporto tecnico della rete WLAN e RADIUS. Queste categorie di eventi sono le opzioni predefinite utilizzate da MOM e le successive descrizioni delle attività in questa sezione vi fanno riferimento.
  
**Tabella 12.8. Categorie di avvisi**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Categoria di avvisi</p></th>  
<th><p>Descrizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Servizio non disponibile</p></td>
<td style="border:1px solid black;"><p>Quando l'applicazione o il componente sono completamente non disponibili.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Violazione della protezione</p></td>
<td style="border:1px solid black;"><p>Quando l'applicazione viene violata oppure è stata compromessa.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Errore critico</p></td>
<td style="border:1px solid black;"><p>Quando nell'applicazione si è verificato un errore critico che richiede un'azione amministrativa rapida (ma non necessariamente immediata). L'applicazione o il componente funziona a un livello di prestazioni al di sotto della norma ma è ancora in grado di eseguire le operazioni più critiche.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Errore</p></td>
<td style="border:1px solid black;"><p>Quando nell'applicazione si verifica un problema temporaneo che non richiede un'azione amministrativa o una risoluzione immediata o che addirittura non richiede alcuna azione. L'applicazione o il componente funziona a un livello di prestazioni accettabile ed è ancora in grado di eseguire tutte le operazioni critiche.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>Quando l'applicazione genera un messaggio di avviso che non richiede un'azione amministrativa o una risoluzione immediata o che addirittura non richiede alcuna azione. L'applicazione o il componente funziona a un livello di prestazioni accettabile ed è ancora in grado di eseguire tutte le operazioni critiche. Tuttavia, se il problema persiste, questa situazione potrebbe generare avvisi quali Errore, Errore critico oppure Servizio non disponibile.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Quando l'applicazione genera un evento informativo. L'applicazione o il componente funziona a un livello di prestazioni accettabile ed esegue tutte le operazioni critiche e non critiche.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Operazione riuscita</p></td>
<td style="border:1px solid black;"><p>Quando l'applicazione genera un evento riuscito. L'applicazione o il componente funziona a un livello di prestazioni accettabile ed esegue tutte le operazioni critiche e non critiche.</p></td>
</tr>  
</tbody>  
</table>
  
##### Monitoraggio dei vincoli di capacità di IAS
  
Il rilevamento di eventuali vincoli di capacità è essenziale per mantenere il servizio a un livello ottimale. Quando i sottosistemi si avvicinano al limite delle capacità operative, le prestazioni si riducono drasticamente (di solito non in modo lineare). Pertanto, è importante monitorare gli andamenti della capacità e identificare e risolvere in anticipo le tendenze verso vincoli futuri.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: autorizzazioni necessarie come indicato dalla soluzione di monitoraggio.
  
-   **Frequenza**: attività di configurazione
  
-   **Requisiti di tecnologia**:
  
    -   Performance Monitor
  
    -   Consolidatore dei contatori delle prestazioni (ad esempio MOM)
  
    -   Console avvisi operativi (ad esempio MOM)
  
    -   Strumenti per la pianificazione della capacità
  
###### Dettagli relativi all'attività
  
I seguenti contatori delle prestazioni sono i più utili per l'identificazione dei vincoli di capacità in IAS. Il processore e il disco sono le due risorse utilizzate in modo più intensivo da IAS, pertanto è probabile che indicheranno dei vincoli prima della rete o della memoria.
  
**Tabella 12.9. Elementi per i quali monitorare i vincoli di capacità IAS**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Oggetto prestazioni</p></th>  
<th><p>Contatore prestazioni</p></th>  
<th><p>Instance</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Processore</p></td>
<td style="border:1px solid black;"><p>% Tempo processore</p></td>
<td style="border:1px solid black;"><p>_Total</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Disco fisico</p></td>
<td style="border:1px solid black;"><p>% Tempo disco</p></td>
<td style="border:1px solid black;"><p>_Total</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Disco fisico</p></td>
<td style="border:1px solid black;"><p>Lunghezza media lettura coda del disco</p></td>
<td style="border:1px solid black;"><p>_Total</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Disco fisico</p></td>
<td style="border:1px solid black;"><p>Lunghezza media scrittura coda del disco</p></td>
<td style="border:1px solid black;"><p>D: (IAS-DATA)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Interfaccia di rete</p></td>
<td style="border:1px solid black;"><p>Byte totali/sec</p></td>
<td style="border:1px solid black;"><p>Scheda di rete</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Memoria</p></td>
<td style="border:1px solid black;"><p>% Byte vincolati in uso</p></td>
<td style="border:1px solid black;"><p>---</p></td>
</tr>  
</tbody>  
</table>
  
Per ulteriori informazioni generali sui vincoli di capacità e sui relativi contatori delle prestazioni, vedere la sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
È anche importante monitorare gli indicatori di capacità delle infrastrutture di supporto. Gli elementi chiave sono:
  
-   **Comunicazioni tra IAS e Active Directory** IAS utilizza ampiamente Active Directory per l'autenticazione e per alcuni servizi di autorizzazione.
  
-   **Client RADIUS quali punti di accesso senza fili** Questi client comunicano con i client e con IAS mediante i protocolli EAP (Extensible Authentication Protocol) e RADIUS.
  
-   **Comunicazioni correlate ai client verso Active Directory** I client della rete LAN senza fili utilizzano i controller di dominio Active Directory per l'autenticazione mediante Criteri di gruppo e per quella tramite il dominio nativo.
  
#### Gestione dell'archiviazione
  
La gestione dell'archiviazione si occupa dell'archiviazione dei dati sia interna che esterna per il ripristino dei dati e l'archiviazione cronologica. Il team di gestione dell'archiviazione dovrà garantire la protezione fisica dei backup e degli archivi. La gestione dell'archiviazione consente di definire, tenere traccia e mantenere dati e risorse di dati nell'ambiente di produzione IT.
  
##### Configurazione dell'esportazione della configurazione IAS
  
Questa attività consente di pianificare un'attività notturna che esporti lo stato di configurazione parziale IAS per semplificare il ripristino di un sistema dopo un errore irreversibile. Lo stato di configurazione IAS completo include la configurazione dei client RADIUS che rappresenta informazioni riservate da proteggere. Pertanto, le istruzioni dettagliate per l'esportazione della parte dello stato di configurazione relativa ai client RADIUS sono fornite separatamente. Per eseguire il ripristino completo di ciascun server IAS alla piena produzione, saranno necessari entrambi i tipi di backup.
  
In un backup completo del server IAS sono incluse tutte le informazioni di configurazione del sistema operativo e tutte le altre informazioni di stato da cui dipende il server IAS. Questa attività è stata sviluppata in modo da consentire la reinstallazione di un server, la reinstallazione dei componenti facoltativi di IAS e il ripristino dello stato di configurazione. In questo modo, il ripristino del servizio di un server, che non si trova più in uno stato di configurazione noto (inaffidabile) o la cui protezione è compromessa, si rivela più semplice.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Amministratori locale.
  
-   **Frequenza**: attività di configurazione
  
-   **Requisiti di tecnologia**:
  
    -   Script MSS
  
    -   Servizio Utilità di pianificazione di Windows
  
    -   SchTasks.exe
  
###### Dettagli relativi all'attività
  
Questa attività imposta un’attività programmata per l’esecuzione del backup notturno dello stato della configurazione del server IAS. Il backup di IAS presume l'esistenza di un sistema di backup dei server aziendali; l'output del backup di questa procedura sarà un file di backup che, a sua volta, può essere sottoposto a backup da parte del sistema di backup. Il sistema di backup principale può essere un backup di rete, backup di rete SAN o backup su dispositivo locale. La soluzione presuppone inoltre che il sistema di backup del server venga avviato durante la notte ed esegua il backup dei dischi del server IAS.
  
**Per configurare il backup della configurazione IAS**
  
1.  Creare un processo pianificato che venga eseguito di notte immettendo il seguente comando. Il comando imposta l’esecuzione dell’attività alle 2.00 di ogni notte.
  
    SCHTASKS /Create /RU system /SC Daily /TN "IAS Backup" /TR \\"C:\\MSSScripts\\IASExport.bat\\" /ST 02:00
  
    Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe.
  
    **Nota:** le barre e le virgolette visualizzate ai lati del nome dello script C:\\MSSScripts\\IASExport.bat sono necessarie solo nel caso di spazi all'interno del nome del percorso o del file. La barra rovesciata è usata per "isolare" le virgolette ai lati del nome dello script in modo che vengano memorizzate come parte della riga di comando del processo schtasks. Questi caratteri possono essere omessi se nel nome del percorso non sono presenti spazi.
  
2.  Configurare il sistema di backup dei server in modo da eseguire il backup del contenuto della directory D:\\IASConfig ogni notte su supporti rimovibili. Se possibile, impostare uno script preliminare per verificare che la data e l'ora dei file di testo della configurazione IAS creati a partire dal file IASExport.bat non risalgano a oltre 24 ore prima. Se i file presentano un indicatore orario e della data superiore alle 24 ore, ciò significa che il backup precedente non è riuscito o è ancora in esecuzione.
  
    **Nota:** lo script IASExport.bat può essere utilizzato come punto di partenza per questa attività. È possibile modificare la logica dello script IASExport.bat in modo che le condizioni di errore dello strumento **netsh** utilizzate all'interno dello script generino eventi o notifiche che saranno rilevate dal personale operativo.
  
È opportuno considerare l'attivazione del controllo dei file di Windows nella directory D:\\IASConfig e indicare ai controllori della protezione dei server di verificare periodicamente l'eventuale presenza di attività insolite nei dati di controllo (accesso non riuscito, ad esempio). Le informazioni contenute nella directory D:\\IASConfig potrebbero consentire a un intruso di conoscere il modo di compromettere il controllo dell'accesso alla rete.
  
##### Esportazione della configurazione dei client RADIUS
  
Per assicurare la possibilità di ripristino di queste informazioni in caso di errore irreversibile del server, è necessario esportare la configurazione dei client RADIUS dal server IAS. Le informazioni sui client RADIUS sono riservate e vanno protette, dal momento che contengono i segreti RADIUS utilizzati dai server e dai punti di accesso senza fili. I dati dei client RADIUS esportati vengono quindi trasferiti su supporti rimovibili che devono essere conservati in un luogo sicuro. I dati di configurazione dei client RADIUS sono in genere univoci per ciascun server IAS.
  
Per eseguire il ripristino completo della configurazione di un server IAS, è necessario ripristinare i dati di configurazione dei client RADIUS, che vengono creati nel corso di questa attività, e i dati di configurazione del sistema IAS creati con lo script IASExport.bat nella procedura precedente.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Amministratori IAS.
  
-   **Frequenza**: attività di configurazione
  
-   **Requisiti di tecnologia**:
  
    -   Script MSS
  
    -   Disco floppy o altri supporti rimovibili e scrivibili
  
###### Dettagli relativi all'attività
  
Le informazioni sui client RADIUS vengono esportate utilizzando il comando **netsh**. Questa guida prevede la creazione di un file batch mediante il quale i dati dei client RADIUS vengono esportati su un disco floppy o su altro supporto rimovibile e scrivibile.
  
**Per esportare la configurazione dei client RADIUS**
  
1.  Accedere al server IAS in cui si desidera salvare i dati dei client RADIUS ed eseguire il comando seguente dal prompt dei comandi:
  
    C:\\MSSScripts\\IASClientExport.bat
  
2.  Individuare eventuali errori o avvisi e correggerli. Dopo aver rettificato la situazione, eseguire di nuovo lo script.
  
3.  Conservare il supporto di backup in maniera adeguata. I dati di questo backup sono estremamente riservati in quanto contengono segreti che potrebbero essere utilizzati per accedere alla rete WLAN aziendale. Questi dati devono essere gestiti con lo stesso livello di protezione usato per il server IAS. È preferibile conservare i dati di backup in una posizione fisica diversa da quella del server IAS, in modo che sia possibile ripristinare il server IAS nel caso in cui tutte le apparecchiature informatiche subiscano danni irreversibili o diventino inaccessibili.
  
##### Configurazione del backup delle directory di dati IAS
  
Scopo di questa attività è fornire indicazioni sulle directory del server IAS che richiedono il backup per consentire un ripristino completo dello stato di configurazione IAS e dei dati del registro RADIUS dopo un errore irreversibile del server. In un backup completo del server IAS sono incluse tutte le informazioni di configurazione del sistema operativo e tutti gli altri dati di stato del sistema da cui dipende il server IAS.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Operatori di backup locale.
  
-   **Frequenza**: attività di configurazione
  
-   **Requisiti di tecnologia**:
  
    -   Utilità di backup di Windows o sistema di backup aziendale
  
    -   Servizio Utilità di pianificazione di Windows
  
    -   SchTasks.exe
  
###### Dettagli relativi all'attività
  
In questa attività, vengono elencate tutte le directory di cui eseguire il backup per assicurare il ripristino completo dello stato di configurazione IAS e dei dati dei file registro. L'attività presume la presenza di un sistema di backup dei server aziendali. Questo sistema può essere un backup di rete, backup di rete SAN o backup su dispositivo locale. La soluzione presume anche che il sistema di backup dei server aziendali venga eseguito di notte, dopo il backup dello stato di configurazione IAS (02.00) per eseguire il backup dei dischi del server IAS.
  
**Per configurare il backup delle directory di dati IAS**
  
1.  Verificare che il backup dello stato di configurazione IAS sia pianificato correttamente e che venga eseguito con esito positivo. L'attività pianificata dello stato di configurazione IAS genera file dello stato della configurazione IAS sul disco rigido.
  
2.  Utilizzare Blocco note per creare un file denominato backuptest.txt nella directory D:\\IASLogs. All'interno del file, digitare **Utilizzato per la verifica del backup e del ripristino**. Salvare il file e chiudere Blocco note. Questo file sarà utilizzato in seguito nelle procedure di verifica del ripristino.
  
    Configurare il sistema di backup dei server aziendali in modo da eseguire un backup completo, incrementale o differenziale delle seguenti directory:
  
    -   D:\\IASConfig
  
    -   D:\\IASLogs
  
3.  Visualizzare i file registro del sistema di backup dei server aziendali per assicurarsi che non si siano verificati errori o avvisi. In caso di rilevamento di errori o avvisi, prendere in considerazione l'esecuzione manuale degli script di esportazione della configurazione IAS e l'esecuzione di un altro backup completo di entrambe le directory.
  
4.  Conservare il supporto di backup in maniera adeguata. I dati di questo backup sono riservati in quanto contengono la configurazione del software del server che consente di accedere alla rete WLAN dell'azienda. Questi dati devono essere gestiti con lo stesso livello di protezione usato per il server IAS. È preferibile conservare i dati di backup in una posizione fisica diversa da quella del server IAS, in modo che sia possibile ripristinare il server IAS nel caso in cui tutte le apparecchiature informatiche subiscano danni irreversibili o diventino inaccessibili.
  
##### Test del backup di IAS
  
Scopo di questa attività è verificare, mediante un ripristino di prova, che il processo e la tecnologia di backup funzionino correttamente. L'esecuzione di un ripristino completo dei backup su hardware server di riserva assicura con la massima affidabilità che le procedure di backup funzionino correttamente. Tuttavia, tale procedura è stata creata in modo da consentire ai clienti, che non dispongono dell'accesso ad hardware server di riserva, di collaudare le procedure di ripristino sull'hardware di produzione con un certo grado di rischio. Il test delle procedure di ripristino sui server di produzione implica il rischio che un ripristino parziale possa rendere il server inutilizzabile.
  
Inoltre, assicura una buona conoscenza delle fasi di ripristino e l'assenza di errori di procedura o tecnici che potrebbero impedirne il completamento in caso di errore irreversibile.
  
I dati di ripristino del server IAS includono:
  
-   **Dati di esportazione dello stato di configurazione IAS** Situati nella directory D:\\IASConfig. Se ripristinate da un nastro, queste informazioni vengono utilizzate per importare nuovamente la configurazione sul server IAS e sono create eseguendo i passaggi riportati nell'attività "Configurazione dell'esportazione della configurazione IAS" in questo capitolo.
  
-   **Dati di esportazione dei client RADIUS** Situati sul disco floppy o su altri supporti rimovibili scrivibili con l'etichetta "Client RADIUS per il server *&lt;nome server&gt;*". Queste informazioni sono utilizzate per il ripristino della configurazione dei client RADIUS sul server IAS e sono create eseguendo i passaggi riportati nell'attività "Esportazione della configurazione dei client RADIUS" in questo capitolo.
  
-   **Dati dei registri delle richieste RADIUS** Situati nella directory D:\\IASLogs. Se ripristinate da un nastro, queste informazioni contengono i dati cronologici utilizzati dai controllori della protezione IAS. Questi dati vengono creati man mano che il servizio IAS registra informazioni RADIUS sul disco.
  
Prima di eseguire un ripristino di prova, è necessario esportare manualmente i dati di esportazione della configurazione IAS e i dati di esportazione dei client RADIUS. Successivamente, eseguire un backup non pianificato dei dati del server su nastri speciali e metterli da parte per utilizzarli solo in caso di problemi nel corso del ripristino di prova. In questo modo si riduce il rischio che nastri difettosi ed errori che potrebbero non essere notati durante i backup normali causino un ripristino parziale di un server di produzione.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: privilegi di Amministratori locali o Operatori di backup sul computer di prova.
  
-   **Frequenza**:
  
    -   Prima che il server IAS diventi operativo
  
    -   Ogni mese
  
    -   Collaudare nuovamente quando si apportano modifiche alla tecnologia o al processo di backup
  
-   **Requisiti di tecnologia**:
  
    -   Utilità di backup di Windows o sistema di backup aziendale
  
    -   Script MSS
  
###### Dettagli relativi all'attività
  
In questa attività sono descritti dettagliatamente il ripristino e la verifica dei dati IAS. Saranno ripristinati tutti e tre i tipi di dati e utilizzate procedure speciali per la convalida del ripristino. Accertarsi di utilizzare un backup completo recente (quello della notte precedente) completato con esito positivo. Accertarsi anche che durante la verifica non siano state effettuate attività amministrative (ad esempio, qualsiasi tipo di configurazione) sul server di destinazione dall'ultimo backup.
  
Se si desidera verificare il ripristino su una copia di Windows Server 2003 appena installata, è necessario eseguire i passaggi preliminari di creazione del server descritti nel capitolo 8, "Implementazione dell'infrastruttura RADIUS per la protezione di reti LAN senza fili", per assicurare che l'hardware e il software del server siano configurati correttamente per IAS.
  
**Nota:** è possibile che occorra selezionare nuovamente il certificato di autenticazione dei server RAS e IAS appena installato all'interno del criterio di accesso remoto per le reti WLAN ripristinato.
  
**Per verificare il backup di IAS**
  
**Nota:** il primo passaggio della procedura è facoltativo ed è utilizzato in un ambiente di laboratorio di prova su hardware server non di produzione. Tuttavia assicura il ripristino di un server con uno stato instabile o la cui protezione è compromessa.
  
1.  Per ripristinare un server in caso di errore irreversibile dell'hardware o del software o di violazione della protezione (a causa di un virus), reinstallare Windows Server 2003 come indicato nel capitolo 8, "Implementazione dell'infrastruttura RADIUS", e accertarsi di copiare gli script MSS dai supporti di distribuzione alla directory C:\\MSSScripts del server.
  
2.  Accedere alla directory D:\\IASLogs e individuare il file backuptest.txt. Se non esiste, continuare con il passaggio successivo. Se si trova il file backuptest.txt, eliminarlo. Il file backuptest.txt è stato creato durante la procedura "Configurazione del backup delle directory di dati IAS". Viene sottoposto a backup insieme ai registri delle richieste RADIUS IAS e consente di controllare che sia possibile ripristinare i dati dal backup senza dover ripristinare i registri RADIUS. Se si preferisce, è possibile ripristinare i dati effettivi del registro delle richieste da D:\\IASLogs. Tuttavia, la sovrascrittura dei dati del file registro potrebbe causare la perdita di dati se l'operazione di ripristino non viene completata.
  
3.  3. Aprire lo snap-in MMC IAS, selezionare le proprietà dell'oggetto **Servizio autenticazione Internet (locale)** e controllare la scheda **Generale**. Aggiungere "**(Test di ripristino)"** al campo **Descrizione server**. Scegliere **OK** per chiudere la finestra di dialogo delle proprietà di IAS. La modifica della stringa di descrizione del server consente di verificare che il backup delle impostazioni di configurazione IAS sia stato ripristinato. Dopo aver ripristinato le precedenti impostazioni di configurazione IAS, la stringa di **descrizione del server** viene sovrascritta dal valore precedente e il testo "**(Test di ripristino)"** viene rimosso.
  
4.  Utilizzando lo snap-in MMC **IAS**, fare clic con il pulsante destro del mouse sulla cartella **Client RADIUS** e selezionare **Nuovo client RADIUS**. Immettere **Test di ripristino** come **nome descrittivo** e digitare **127.0.0.1** nel campo **Indirizzo client (IP o DNS)**. Immettere una password nei campi **Segreto condiviso** e **Conferma segreto condiviso** relativi a questo client RADIUS, quindi scegliere **Fine**. Se il ripristino è riuscito, le informazioni dei client RADIUS sono state sovrascritte e questo nuovo RADIUS non viene visualizzato.
  
5.  Individuare i supporti di backup che si desidera verificare (ad esempio il backup programmato della notte precedente) e utilizzarli per il ripristino dei seguenti dati sul disco rigido del server:
  
    -   D:\\IASConfig\\\*.\*
  
    -   D:\\IASLogs\\BACKUPTEST.TXT
  
6.  Dal prompt dei comandi, eseguire il comando riportato di seguito per ripristinare, nel database IAS, la configurazione IAS salvata in precedenza come file di testo. Accertarsi di controllare l'eventuale visualizzazione di errori o avvisi durante l'esecuzione dello script:
  
    C:\\MSSScripts\\IASImport.bat
  
    **Nota:** nei passaggi che seguono è previsto l'utilizzo di un disco floppy o di altri supporti rimovibili e scrivibili con l'etichetta "Client RADIUS per il server *&lt;nome server&gt;*." Accertarsi di utilizzare il disco corretto, con il server appropriato, per evitare la perdita di dati.
  
7.  Individuare il disco floppy (o gli altri supporti rimovibili e scrivibili) di configurazione dei client RADIUS per questo server e inserirli nell'unità del server. Dal prompt dei comandi, eseguire il comando riportato di seguito. Accertarsi di controllare l'eventuale visualizzazione di errori o avvisi durante l'esecuzione dello script:
  
    C:\\MSSScripts\\IASClientImport.bat
  
8.  Chiudere e riaprire lo snap-in MMC **IAS**, selezionare le proprietà dell'oggetto **Servizio autenticazione Internet (locale)** e controllare la scheda **Generale** per accertarsi che il testo **(Test di ripristino)** non sia più visualizzato nel campo **Descrizione server**. Scegliere **OK** per chiudere la finestra di dialogo **Proprietà IAS**.
  
9.  Selezionare la cartella Client RADIUSe accertarsi che il client RADIUS **Test di ripristino** non sia più visualizzato nell'elenco di client nel riquadro a destra.
  
10. Nella parte restante della configurazione all'interno dello snap-in MMC **IAS** dovranno essere visualizzate le impostazioni precedenti alla verifica del ripristino.
  
11. Individuare la directory D:\\IASLogs e accertarsi della presenza del file backuptest.txt. Se i passaggi di questa procedura di ripristino sono stati eseguiti su un server di produzione, fare in modo che un controllore della protezione IAS controlli i file registro per assicurare che siano intatti e che siano aggiornati almeno al momento in cui è stato eseguito il backup.
  
12. È opportuno mettere nuovamente i supporti di backup e il disco floppy in un archivio protetto.
  
#### Amministrazione della protezione
  
L'amministrazione della protezione è responsabile del mantenimento di un ambiente informatico protetto. La protezione è una parte importante dell'infrastruttura di un'azienda. In un sistema informatico con una protezione debole è probabile che si verifichino violazioni della protezione.
  
##### Accesso ai registri delle richieste RADIUS IAS
  
Il server IAS è in grado di registrare, a scelta, diversi eventi derivanti dalle richieste RADIUS dei punti di accesso senza fili nei registri delle richieste RADIUS che si trovano sul disco rigido del server. I registri RADIUS sono utili per un gran numero di motivi, tra cui l'identificazione di eventuali attacchi al sistema e di accesso non autorizzato alla rete aziendale. Sebbene la discussione dettagliata dell'analisi dei registri delle richieste RADIUS non rientri nell'ambito di questa guida, in questa attività sono illustrati i metodi per controllare i registri delle richieste RADIUS.
  
Per analizzare i registri delle richieste RADIUS archiviati come testo in formato IAS oppure nel formato di importazione per database, possono essere utilizzati diversi metodi. In questa soluzione, è stato scelto il formato di importazione per database per i file registro, in quanto l'importazione di questo tipo di file in applicazioni che riconoscono il testo delimitato da virgole è relativamente semplice. Tra i metodi per l'analisi dei registri delle richieste RADIUS IAS sono inclusi i seguenti:
  
-   **Individuazione diretta dei file registro mediante l'utilità IASPARSE** Questo strumento fa parte degli Strumenti di supporto di Windows Server 2003 e, per motivi di prestazioni, viene in genere installato ed eseguito sul server IAS stesso. È necessaria quindi una sessione di Connessione desktop remoto (o un altro sistema di esecuzione remota). Per impostazione predefinita, questa soluzione non è configurata per supportare questo metodo di visualizzazione dei file registro.
  
-   **Importazione dei file registro in Microsoft Access 2002 da un computer di amministrazione remoto**. Questo metodo consente a un amministratore di importare i registri in una tabella di Microsoft Access per query improvvisate o nell'ambito di uno schema strutturato di reporting e archiviazione. Questo metodo di visualizzazione dei file registro è stato scelto per questa soluzione in quanto offre un giusto grado di semplicità e flessibilità. È opportuno che le aziende prendano in considerazione la registrazione basata su Microsoft SQL Server™ 2000 descritta di seguito.
  
-   **Accesso alle informazioni dei registri tramite un cluster centrale di SQL Server 2000** a cui sono stati replicati i dati da MSDE 2000 su ciascun server IAS. Ciascun server IAS accede alla propria istanza locale di MSDE. Sebbene la configurazione di questa disposizione sia piuttosto complessa, è stato pubblicato un white paper con relativo codice per supportare questo processo. Per assistenza durante il processo di configurazione di questo tipo di registrazione SQL, consultare un partner Microsoft o rivolgersi al responsabile clienti Microsoft che potrà segnalare il partner o un esperto di Microsoft Consulting Services da contattare.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Controllori protezione IAS.
  
-   **Frequenza**: ogni giorno oppure ogni settimana, a seconda dei requisiti di protezione.
  
-   **Requisiti di tecnologia**:
  
    -   IASPARSE
  
    -   Microsoft Access
  
    -   Microsoft Excel
  
###### Dettagli relativi all'attività
  
I registri delle richieste RADIUS vengono generati su ciascun server di questa soluzione e archiviati in un volume disco dedicato. I passaggi da compiere per accedere a questi file registro includono la creazione di una connessione di rete a ciascun server IAS, nonché l'analisi e l'eliminazione dei file registro non più necessari. I server IAS di questa soluzione sono configurati per la creazione di un nuovo file registro delle richieste RADIUS ogni mese, ma è possibile modificare questo intervallo per adattarlo alle esigenze specifiche.
  
La tabella creata con Access verrà formattata in base al tipo di dati contenuti in ciascun campo. Sebbene in questo esempio vengano illustrate le modalità di creazione di una nuova tabella, è anche possibile importare un registro in una tabella esistente.
  
**Per importare i file registro delle richieste RADIUS in Microsoft Access**
  
1.  Accedere a una workstation amministrativa come membro del gruppo di protezione Controllori protezione IAS di Active Directory e mappare una connessione di un'unità al server IAS che contiene i registri da analizzare. Al prompt dei comandi, digitare il comando seguente, sostituendo HQ-IAS-01 con il nome del server IAS:
  
    NET USE X: \\\\HQ-IAS-01\\IASLogs
  
2.  Individuare il file registro che rappresenta il mese che si desidera esaminare. Il nome del file registro utilizza un formato che indica la data di creazione del file. Creare una copia del file registro e rinominarla con l'estensione .txt.
  
3.  Aggiungere all'inizio del file registro copiato le due righe complete fornite nel file di testo C:\\MSSScripts\\IASAccessPrep.txt. La prima riga contiene i nomi degli attributi di ciascun campo del registro, utilizzati da Access per creare i nomi dei campi della tabella. L'utilizzo di questi nomi rende più semplice l'interpretazione delle voci del registro. Access utilizza la seconda riga per configurare il tipo di dati appropriato a ciascuna colonna della tabella. Dopo aver importato il file registro, è necessario eliminare queste voci dalla tabella di Access.
  
4.  In Access 2002 scegliere **Database vuoto**. In **Salva nuovo database** specificare un nome file, quindi scegliere **Crea una tabella mediante l'immissione di dati**. Scegliere **File**, quindi **Carica dati esterni** e poi **Importa**.
  
5.  Scegliere **Importa**, **Tipo file**, quindi **File di testo**, individuare il file registro IAS, selezionarlo e scegliere **Importa**. In **Importazione guidata testo** scegliere **Avanzate**.
  
6.  Scegliere **Specifica di importazione**:
  
7.  In **Formato file** scegliere **Delimitato**.
  
8.  In **Delimitatore di campo,** scegliere **,** (virgola).
  
9.  In **Qualificatore testo** scegliere " (virgolette).
  
10. Nei campi **Date, Ore e Numeri,** selezionare **Formato anno esteso** e **Date con zero iniziale**, quindi digitare il **formato data** (ad esempio MGA), il **separatore data** (ad esempio **/** o **barra**), il **separatore ora** (ad esempio **:** o due punti) e il **separatore decimale** (ad esempio . o punto) appropriati.
  
11. Nella finestra di dialogo **Importazione guidata testo,** scegliere **Avanti**, selezionare **Nomi di campo nella prima riga**, quindi scegliere **Avanti**. Scegliere **Tabella nuova**, quindi **Avanti**.
  
12. Lasciare le impostazioni predefinite in **Opzioni per i campi**, quindi scegliere **Avanti**. Scegliere **Chiave primaria aggiunta automaticamente**, quindi **Avanti**. In **Importa nella tabella** digitare il nome della nuova tabella. Scegliere **Fine**.
  
13. Nella finestra di dialogo **Nome file:Database,** immettere il nome del database in uso, quindi scegliere **Apri** per visualizzare la tabella.
  
##### Verifica delle voci del Registro eventi di autenticazione RADIUS IAS
  
I controllori della protezione possono utilizzare quest'attività periodicamente per controllare i tentativi di accesso non autorizzato alla rete senza fili. È possibile che i criteri di protezione interni impongano di verificare periodicamente gli eventi di autenticazione RADIUS nel Registro eventi per rilevare i tentativi di autenticazione oppure l'utilizzo di credenziali di certificati rubati. Per creare avvisi quando vengono registrati eventi sospetti, è possibile usare anche uno strumento di gestione come MOM.
  
Questa attività è facoltativa e può essere un'alternativa alla registrazione RADIUS di IAS descritta in precedenza. L'attività richiede l'appartenenza al gruppo Amministratori IAS o Amministratori locale del server.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo Amministratori IAS o al gruppo Amministratori locale/incorporato.
  
-   **Frequenza**: ogni giorno oppure ogni settimana, a seconda dei requisiti di protezione.
  
-   **Requisiti di tecnologia**:
  
    -   Visualizzatore eventi
  
    -   A scelta, EventCombMT o EventFilter inclusi in Windows Server 2003 Resource Kit.
  
###### Dettagli relativi all'attività
  
Questa attività è adatta agli ambienti IT in cui i controllori della protezione IAS si occupano anche dell'amministrazione del sistema IAS. Al contrario, i registri RADIUS possono essere visualizzati dagli operatori che non dispongono dei diritti amministrativi locali del server. Questa soluzione non fornisce privilegi di amministratore locale ai controllori della protezione. Pertanto, prima di cominciare ad eseguire questa attività, è necessario aggiungere il controllore al gruppo di protezione Amministratori IAS di Active Directory.
  
**Per controllare la presenza di tentativi di autenticazione non riusciti nel Registro eventi tramite Visualizzatore eventi**
  
1.  Accedere a uno dei server IAS come membro del gruppo di protezione Amministratori IAS.
  
2.  Aprire il Visualizzatore eventi facendo clic sul pulsante **Start**, scegliendo **Tutti i programmi** e quindi **Strumenti di amministrazione**.
  
3.  Scegliere **Registro eventi sistema**.
  
4.  Dal menu **Visualizza,** scegliere **Filtro**.
  
5.  Selezionare **IAS** come **Origine evento** e **2** come **ID evento**.
  
6.  Esaminare tutti gli eventuali errori di autenticazione frequenti o altri elementi sospetti.
  
    **Nota:** per visualizzare gli eventi di IAS, è possibile utilizzare anche lo strumento Eventquery (in Windows XP e Windows Server 2003) e EventFilter o EventCombMT di Windows Server 2003 Resource Kit.
  
##### Archiviazione ed eliminazione dei file registro RADIUS IAS
  
IAS include una funzione per eliminare il file registro RADIUS IAS meno recente quando il disco di registrazione è pieno. Se non si utilizza questa funzione, è necessario archiviare ed eliminare manualmente i file registro delle richieste IAS RADIUS per assicurare che lo spazio su disco del server IAS non si esaurisca. Se si esaurisce lo spazio su disco, IAS interrompe il servizio per le richieste di autenticazione e accounting provenienti dai punti di accesso senza fili. È possibile automatizzare l'archiviazione dei registri anche mediante uno script o una strategia di replica automatica SQL Server 2000 (come descritto nell'attività "Accesso ai registri delle richieste RADIUS IAS" presentata in precedenza in questo capitolo).
  
**Nota:** questa soluzione utilizza la funzione IAS per eliminare automaticamente il file registro meno recente quando il disco è pieno.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Controllori protezione IAS di Active Directory.
  
-   **Frequenza**: ogni mese.
  
-   **Requisiti di tecnologia**: comandi nativi di Windows.
  
###### Dettagli relativi all'attività
  
Ci sono diversi metodi di archiviazione ed eliminazione per i registri delle richieste di autenticazione e accounting RADIUS. Ad esempio, uno script di backup basato su server è in grado di informare i controllori della protezione IAS, mediante un messaggio di posta elettronica, del completamento del backup dei file registro. I controllori della protezione possono quindi collegarsi al server IAS ed eliminare i file registro meno recenti. Un controllore della protezione IAS è in grado di eseguire il backup dei file registro RADIUS su un'unità nastro o CD-RW collegata al proprio computer di amministrazione e collegarsi al server IAS ed eliminare i file registro meno recenti che non sono necessari.
  
Il server IAS di questa soluzione è configurato per la creazione di un nuovo file registro ogni mese.
  
È preferibile scegliere una strategia che consenta di mantenere in linea una quantità di dati sufficiente a ricostruire le informazioni di accesso alla rete per i diversi scenari. Ad esempio, se si dispone di dati in linea relativi a tre mesi in tre file registro diversi, potrebbero essere necessari gli ultimi due file registro per ricostruire le informazioni di accesso alla rete e tenere traccia degli eventi di protezione. Pertanto, è possibile archiviare ed eliminare il meno recente dei tre file registro e lasciare i due più recenti.
  
Per maggiori informazioni sul backup dei registri delle richieste RADIUS e di altri dati IAS, vedere l'attività "Configurazione del backup delle directory di dati IAS" illustrata dettagliatamente in questo capitolo. In questa attività sono fornite le indicazioni per l'archiviazione e l'eliminazione di registri RADIUS da una workstation amministrativa.
  
**Per archiviare ed eliminare i file registro delle richieste RADIUS**
  
1.  Accedere a una workstation amministrativa come membro del gruppo di protezione IAS Security Auditors.
  
2.  Mappare un'unità al server IAS in cui si eseguiranno l'archiviazione dei file di registro digitando il seguente comando al prompt dei comandi, sostituendo HQ-IAS-01 con il nome del server IAS:
  
    NET USE X: \\\\HQ-IAS-01\\IASLogs
  
3.  Identificare i file registro meno recenti sul server IAS, che saranno archiviati ed eliminati dal server. Utilizzare NTBACKUP, il comando **copy** o un'altra utilità per archiviare i file registro selezionati dalla condivisione in linea ai supporti secondari.
  
4.  Eliminare i file registro indesiderati dalla condivisione in linea.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di supporto
  
Le funzioni SMF della fase di supporto forniscono attività reattive e proattive al fine di mantenere i livelli di servizio richiesti. Le funzioni reattive dipendono dalla capacità dell'azienda di reagire e risolvere rapidamente le emergenze e i problemi. Le funzioni preventive tentano di evitare eventuali interruzioni del servizio identificando e risolvendo i problemi prima che influiscano su qualsiasi livello del servizio. Queste funzioni utilizzano un buon monitoraggio della soluzione di servizi a fronte di soglie predefinite e danno al personale operativo il tempo sufficiente per reagire a eventuali problemi prima che si manifestino con interruzioni dei servizi. La fase di supporto è strettamente correlata alla funzione SMF di monitoraggio e controllo dei servizi descritta nella fase operativa. Il monitoraggio e controllo dei servizi fornisce informazioni essenziali che consentono al personale operativo e a quello addetto al supporto tecnico di individuare i problemi. In questa sezione, sono descritte le procedure per affrontare e risolvere i problemi più comuni.
  
In questa sezione vengono fornite le informazioni relative alle seguenti funzioni SMF:
  
-   Gestione delle emergenze
  
Non esistono attività per le restanti funzioni SMF:
  
-   Gestione dei problemi
  
-   Servizio di assistenza
  
    **Nota:** la descrizione dell'attività comprende le seguenti informazioni riassuntive: requisiti di protezione, frequenza e requisiti di tecnologia.
  
#### Gestione delle emergenze
  
La gestione delle emergenze è il processo che consente di gestire e controllare errori e interruzioni nell'utilizzo o nell'implementazione dei servizi IT riferiti dai clienti o dai partner IT. La gestione delle emergenze mira a ripristinare il normale funzionamento del servizio nel modo più rapido possibile e a ridurre al minimo le ripercussioni negative sull'attività aziendale, assicurando il mantenimento della migliore qualità e disponibilità dei livelli di servizio. Con l'espressione normale funzionamento del servizio si intende un funzionamento entro i limiti del contratto del livello di servizio (SLA, Service Level Agreement).
  
**Nota:** per la risoluzione generale dei problemi dei client senza fili Windows XP, consultare la sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
##### Verifica dello stato della cartella Connessioni di rete dei client
  
La cartella Connessioni di rete e le icone di notifica di Windows XP forniscono informazioni sullo stato dell'autenticazione WLAN. Questa attività consente all'utente finale o ai membri del personale del servizio di assistenza di verificare lo stato della connessione senza fili sul computer client. Se un'autenticazione richiede informazioni aggiuntive da parte dell'utente, ad esempio la scelta di uno o più certificati utente, viene visualizzato un promemoria con le istruzioni per l'utente. Questa attività viene utilizzata durante la risoluzione dei problemi.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Amministratori locale per apportare modifiche alle impostazioni della rete WLAN.
  
-   **Frequenza**: durante la risoluzione dei problemi di un utente.
  
-   **Requisiti di tecnologia**: Windows XP Professional.
  
###### Dettagli relativi all'attività
  
Lo stato dell'autenticazione è descritto nel testo sotto il nome della connessione corrispondente alla scheda di rete senza fili, all'interno della cartella Connessioni di rete.
  
Una volta visualizzato lo stato della connessione, è possibile visualizzare l'intensità del segnale nella scheda **Generale** e la configurazione dell'indirizzo IP nella scheda **Supporto**. Se la scheda senza fili dispone di un indirizzo APIPA (Automatic Private IP Addressing), ad esempio 169.254.0.0/16, o se è stata configurata con l'indirizzo IP alternativo nelle proprietà del protocollo TCP/IP (Transmission Control Protocol/Internet Protocol) della scheda, l'autenticazione non è riuscita, ma il client senza fili Windows XP è ancora associato al punto di accesso senza fili. Se l'autenticazione non va a buon fine e l'associazione è ancora valida, Windows attiva la scheda senza fili e il protocollo TCP/IP esegue il processo di configurazione normale. In questo esempio, poiché il client non viene autenticato nella rete WLAN e non è possibile rilevare un server DHCP (Dynamic Host Configuration Protocol), TCP/IP configura automaticamente un indirizzo APIPA o un indirizzo alternativo. In questi casi, si consiglia di ricontrollare l'errore di autenticazione WLAN sul server IAS o attivare ed effettuare l'analisi del computer client.
  
**Per verificare lo stato della cartella Connessioni di rete**
  
-   Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **ncpa.cpl**, quindi scegliere **OK**.
  
##### Attivazione e disattivazione dell'analisi sui computer client
  
Windows supporta la raccolta di informazioni dettagliate sull’analisi, che consentono di facilitare il personale degli helpdesk e gli sviluppatori nella risoluzione di problematiche rilevate in componenti software. L’analisi offre un livello di dettaglio superiore a quello dei registri eventi. Tali informazioni sono archiviate in file registro di testo.
  
Per ottenere informazioni dettagliate sul processo di autenticazione EAP, occorre attivare l'analisi di EAP sui componenti LAN (EAPOL) e RASTLS (Remote Access Service - Transport Layer Security).
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Amministratore locale.
  
-   **Frequenza**: se necessario, durante la risoluzione dei problemi di rete WLAN di un client.
  
-   **Requisiti di tecnologia**:
  
    -   Windows XP Professional
  
    -   Notepad.exe
  
###### Dettagli relativi all'attività
  
Una volta emessi i comandi riportati di seguito, tentare nuovamente il processo di autenticazione e visualizzare i file Eapol.log e Rastls.log della cartella %systemroot%\\Tracing.
  
**Per attivare l’analisi sui computer client**
  
-   Eseguire i comandi seguenti:
  
    -   **netsh ras set tracing eapol enabled**
  
    -   **netsh ras set tracing rastls enabled**
  
**Per disattivare l’analisi sui computer client**
  
-   Eseguire i comandi seguenti:
  
    -   **netsh ras set tracing eapol disabled**
  
    -   **netsh ras set tracing rastls disabled**
  
    **Nota:** l’analisi richiede un consumo di risorse di sistema e crea file registro le cui dimensioni possono aumentare rapidamente. Verificare di disattivare l’analisi una volta completata la risoluzione dei problemi.
  
##### Verifica della stringa del nome di dominio sui computer client
  
L'attività seguente è utile se si è scelto di attivare il controllo dei nomi di dominio dei certificati sui computer client. Questa impostazione non è attivata in questa soluzione perché può generare delle finestre di dialogo WLAN che possono confondere l'utente. Windows XP Professional SP1 è configurato con questa opzione disattivata per impostazione predefinita.
  
Durante l'autenticazione reciproca EAP-TLSI, i computer client non possono eseguire il controllo dei certificati revocati, in quanto i percorsi degli elenchi CRL (Certificate Revocation List) in genere non sono accessibili se prima non si è ottenuto l'accesso alla rete WLAN. I client Windows possono, tuttavia, convalidare tutto o parte del nome del server nel certificato presentato dal server IAS. Questa funzione è configurata nelle impostazioni dei criteri di rete senza fili nell'oggetto Criteri di gruppo dei client senza fili. Le impostazioni hanno un'interfaccia utente simile a quella delle proprietà Reti senza fili nelle proprietà della scheda di rete senza fili del computer client.
  
L'autenticazione non riesce se il client senza fili tenta di convalidare il certificato del server ed è stato immesso un valore errato per il dominio del server IAS nel campo che indica di **eseguire la connessione qualora il nome del server termini con un determinato elemento**. Se si è scelto di attivare l'opzione **Connetti ai server seguenti**, può essere necessario eseguire questa attività durante la risoluzione dei problemi di autenticazione dei client.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Amministratore locale.
  
-   **Frequenza**: configurazione oppure durante la risoluzione dei problemi WLAN degli utenti.
  
-   **Requisiti di tecnologia**: Windows XP Professional.
  
###### Dettagli relativi all'attività
  
Questa attività consente di controllare la correttezza della stringa del nome di dominio nella finestra di dialogo **Proprietà**della connessione di rete della scheda di rete WLAN sul client o nell'oggetto Criteri di gruppo delle reti senza fili.
  
**Per verificare la stringa del nome di dominio sui computer client**
  
1.  Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **ncpa.cpl**, quindi scegliere **OK**.
  
2.  Visualizzare le proprietà della connessione di rete senza fili.
  
3.  Nella scheda **Reti senza fili,** selezionare l'identificatore SSID (Service Set Identifier) della rete di destinazione dalle reti preferite e visualizzarne le proprietà.
  
4.  Nella scheda **Autenticazione,** visualizzare le proprietà e assicurarsi che la stringa del campo **che indica di eseguire la connessione qualora il nome del server termini con un determinato elemento** sia uguale al nome di dominio dei server IAS.
  
##### Visualizzazione degli eventi di autenticazione IAS nel Registro eventi
  
Gli eventi relativi alla riuscita e alla mancata riuscita dell'autenticazione client vengono registrati nel Registro eventi di sistema nei server IAS e possono dimostrarsi utili per la risoluzione dei problemi. La registrazione degli eventi è attivata per tutti i tipi di eventi IAS (eventi di rifiuto, di eliminazione o eventi riusciti) per impostazione predefinita nella scheda **Servizio** delle proprietà del server IAS nello snap-in MMC IAS.
  
Questa attività consente agli amministratori IAS di agevolare il personale del servizio di assistenza nella risoluzione dei problemi di autenticazione di computer e utenti visualizzando gli eventi di autenticazione inclusi nei Registri eventi del server IAS.
  
Se il personale del servizio di assistenza IT richiede l'accesso alle informazioni di autenticazione dei client senza fili incluse nei Registri eventi di sistema IAS, esistono diverse opzioni:
  
-   Prevedere il supporto di un amministratore IAS, membro del gruppo di protezione IAS Admins e quindi dotato dell'accesso ai messaggi dei Registri eventi di sistema IAS. Questa attività utilizza questa opzione.
  
-   Utilizzare un sistema di gestione dei Registri eventi dell'organizzazione, ad esempio MOM, per esportare i registri in un percorso accessibile al personale del servizio di assistenza.
  
-   Assegnare al personale del servizio di assistenza l'autorizzazione in lettura per la condivisione IASLogs e per la relativa directory NTFS D:\\IASLogs. Indicare al personale del servizio di assistenza le modalità di individuazione dei file registro mediante strumenti come IASPARSE descritti nell'attività "Accesso ai registri delle richieste RADIUS IAS" di questo capitolo. La maggior parte dei clienti probabilmente prenderà in considerazione questa opzione che richiede l'infrastruttura minima e non espone a rischi di protezione eccessivi.
  
Concedere l'accesso ai Registri eventi di sistema IAS ad utenti che non dispongono di privilegi di amministratori può comportare un rischio di protezione, specialmente per i server che combinano ruoli di server IAS e ruoli di server di controller di dominio.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Amministratori IAS locale oppure a un gruppo che dispone dell'accesso in lettura/salvataggio al Registro eventi di sistema.
  
-   **Frequenza**: durante la risoluzione dei problemi di autenticazione dei client.
  
-   **Requisiti di tecnologia**: snap-in MMC Visualizzatore eventi o EventCombMT incluso in Windows Server 2003 Resource Kit.
  
###### Dettagli relativi all'attività
  
La visualizzazione dei tentativi di autenticazione nel Registro eventi di sistema è utile per risolvere i problemi relativi ai tentativi di autenticazione rifiutati da IAS. Se sono configurati più criteri di accesso remoto, è possibile utilizzare il registro per determinare il nome del criterio di accesso remoto che ha accettato o rifiutato il tentativo di connessione (vedere Criterio - Nome nella descrizione dell'evento). Inoltre, l'evento di autenticazione (Source: IAS, Event ID 1 for accept and 2 for reject) segnala i codici motivo che dispongono di descrizioni corrispondenti e sono menzionati in Guida in linea e supporto tecnico per Windows Server 2003.
  
L'attivazione della registrazione degli eventi IAS e la lettura del testo degli eventi di autenticazione IAS nel Registro eventi di sistema sono lo strumento più utile nella risoluzione dei problemi di autenticazione IAS non riuscita.
  
**Per visualizzare gli eventi di autenticazione del Registro eventi di sistema**
  
1.  Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **Eventvwr**, quindi scegliere **OK**.
  
2.  Selezionare **Registro eventi sistema**.
  
3.  Dal menu **Visualizza,** scegliere **Filtro**, **IAS** come **Origine evento**, quindi fare clic su **OK**.
  
##### Attivazione e disattivazione dell'analisi sul server IAS
  
Windows supporta la raccolta di informazioni dettagliate sull’analisi, che consentono di facilitare il personale degli helpdesk e gli sviluppatori nella risoluzione di problematiche rilevate in componenti software. L’analisi offre un livello di dettaglio superiore a quello dei Registri eventi. Tali informazioni sono archiviate in file registro di testo.
  
Microsoft Windows Server 2003 dispone di una funzionalità di analisi estesa che può essere utilizzata per la risoluzione di problemi complessi relativi a componenti specifici. In Windows Server 2003 è possibile consentire ai componenti di registrare le informazioni di analisi all'interno di file utilizzando il comando **netsh**.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Amministratori locale del server IAS.
  
-   **Frequenza**: se necessario, durante la risoluzione dei problemi di connessione alla rete WLAN dei client.
  
-   **Requisiti di tecnologia**:
  
    -   Netsh
  
    -   Blocco note
  
    -   Regedit
  
###### Dettagli relativi all'attività
  
Per attivare o disattivare l’analisi di componenti specifici o di tutti i componenti, utilizzare il comando **netsh**. I componenti più efficaci nei quali attivare l’analisi delle problematiche di autenticazione 802.1X tramite EAP-TLS sono indicati di seguito:
  
-   **IASSAM** (**file Iassam.log nella cartella %*systemroot%*\\tracing**) Questo registro è il file di analisi più utilizzato per i problemi di IAS, in quanto descrive le funzioni relative alla violazione di nomi utente, al collegamento a un controller di dominio e alla verifica delle credenziali. È il punto nodale dei file di analisi di IAS e in genere è necessario per eseguire il debug degli errori correlati all’autenticazione.
  
-   **RASTLS (file Rastls.log nella cartella %*systemroot%*\\tracing**) In tutti i casi di autenticazioni EAP e PEAP, questo registro contiene la maggior parte delle informazioni essenziali sul debug. Tuttavia, è un file difficile da leggere. Microsoft è impegnata nell’elaborazione di un sistema che consenta una più agevole lettura di questi dati.
  
Le seguenti informazioni di analisi per IAS in genere non sono necessarie per la risoluzione di problematiche di autenticazione 802.1X utilizzando il protocollo EAP-TLS ma possono essere utili per risolvere altri problemi.
  
-   **IASRAD (file Iasrad.log nella cartella** ***%systemroot%*\\tracing**) Questo registro descrive tutte le operazioni relative al protocollo RADIUS, ad esempio le porte sulle quali il server è in ascolto e così via. Anche queste informazioni sono usate raramente nelle problematiche di debug del server IAS.
  
-   **IASSDO (file Iassdo.log nella cartella** ***%systemroot%*\\tracing**) Nel registro IASSDO vengono registrate le transazioni dall'interfaccia utente ai file MDB che contengono la configurazione e il dizionario del server. Si tratta del registro utilizzato per eseguire il debug delle problematiche del servizio o di quelle correlate all’interfaccia utente.
  
**Per attivare l’analisi sul server IAS**
  
-   Eseguire i comandi **netsh**, che corrispondono alle informazioni di analisi richieste. È consigliabile l’utilizzo dei registri IASSAM e RASTLS in caso di problemi con l’autenticazione 802.1X tramite EAP-TLS.
  
    I comandi **netsh** corrispondenti sono:
  
    -   **netsh ras set tracing iassam enabled**
  
    -   **netsh ras set tracing rastls enabled**
  
    -   **netsh ras set tracing iasrad enabled**
  
    -   **netsh ras set tracing iassdo enabled**
  
**Per disattivare l’analisi sul server IAS**
  
-   Eseguire i comandi **netsh**, che corrispondono alle informazioni di analisi che si desidera disattivare.
  
    I comandi **netsh** corrispondenti sono:
  
    -   **netsh ras set tracing iassam disabled**
  
    -   **netsh ras set tracing rastls disabled**
  
    -   **netsh ras set tracing iasrad disabled**
  
    -   **netsh ras set tracing iassdo disabled**
  
        **Nota:** poiché l'analisi richiede una certa quantità di risorse del sistema, è opportuno utilizzarla con parsimonia, quando occorre individuare i problemi della rete. Una volta acquisita l'analisi o identificato il problema, è opportuno disattivare subito l'analisi.
  
I registri di analisi IASSAM sono impostati su un solo megabyte (MB) e questo può causare la sovrascrittura di informazioni importanti nei file registro in presenza di un carico pesante. Per impostare il registro di analisi IASSAM su 15 MB, seguire le operazioni riportate di seguito. Quando le dimensioni del registro raggiungono i 15 MB, il file viene rinominato IASSAM.old e viene creato un nuovo file IASSAM.log. Questa procedura consente di disporre di 30 MB di dati sul server.
  
**Per impostare il file registro di analisi IASSAM su 15 MB**
  
1.  Avviare Regedit.exe.
  
2.  Passare alla seguente chiave del Registro di sistema: **\\HKLM\\Software\\Microsoft\\Tracing\\**.
  
3.  Aggiornare la chiave **IASSAM** con un valore di **MaxFileSize**, un tipo **REG\_DWORD** e un valore di dati di **0xF00000**.
  
##### Attivazione della registrazione SChannel sul server IAS
  
SChannel (Secure Channel) è un provider SSP (Security Support Provider) che supporta una serie di protocolli di protezione Internet, ad esempio SSL e TLS.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: appartenenza al gruppo di protezione Amministratore locale.
  
-   **Frequenza**: se necessario, durante la risoluzione dei problemi di connessione client sul server IAS.
  
-   **Requisiti di tecnologia**:
  
    -   Regedit
  
    -   Blocco note
  
###### Dettagli relativi all'attività
  
La registrazione degli errori di convalida dei certificati dei client è un evento SChannel e non è attiva sul server IAS per impostazione predefinita.
  
**Per attivare la registrazione SChannel sul server IAS**
  
È possibile attivare eventi aggiuntivi SChannel modificando il valore della seguente chiave del Registro di sistema da **1** (tipo **REG\_DWORD**, dati **0x00000001**) a **3** (tipo **REG\_DWORD**, dati **0x00000003**):
  
**HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders**  
**\\SCHANNEL\\EventLogging**
  
**Avviso:** modifiche non corrette al Registro di sistema potrebbero danneggiare gravemente il sistema. Prima di apportare modifiche al Registro di sistema, è consigliabile eseguire il backup di tutti i dati importanti presenti nel computer.
  
Accertarsi di disattivare la registrazione SChannel durante l'attività di risoluzione dei problemi, perché questa operazione richiede una quantità notevole di risorse del sistema e registra moltissime voci nel Registro eventi.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di ottimizzazione
  
Nella fase di ottimizzazione, sono incluse le funzioni SMF con cui gestire i costi mantenendo o migliorando i livelli di servizio. Questa fase comprende l'analisi delle interruzioni o delle emergenze, l'esame delle strutture di costo, le valutazioni del personale, la disponibilità, l'analisi delle prestazioni e la previsione della capacità.
  
In questa sezione vengono fornite le informazioni relative alle seguenti funzioni SMF:
  
-   Gestione della capacità
  
Non esistono attività per le restanti funzioni SMF:
  
-   Gestione dei livelli di servizio
  
-   Gestione finanziaria
  
-   Gestione della disponibilità
  
-   Gestione della continuità dei servizi IT
  
-   Gestione della forza lavoro
  
    **Nota:** la descrizione dell'attività comprende le seguenti informazioni riassuntive: requisiti di protezione, frequenza e requisiti di tecnologia.
  
#### Gestione della capacità
  
La gestione della capacità è il processo di pianificazione, dimensionamento e controllo della capacità della soluzione di servizi in modo che soddisfi la richiesta degli utenti entro i livelli di prestazioni stabiliti nel contratto del livello di servizio. Il processo richiede informazioni relative agli scenari di utilizzo, agli schemi e alle caratteristiche di carico massimo della soluzione di servizi, nonché requisiti di prestazione definiti.
  
##### Determinazione del carico massimo sul server IAS
  
In questa sezione vengono fornite alcune informazioni sul carico massimo probabile del server IAS.
  
Raramente le prestazioni costituiscono un problema per i server RADIUS IAS che sono dimensionati e configurati correttamente. I server RADIUS IAS subiscono un carico maggiore durante le ore di punta, ad esempio al mattino, quando un numero molto alto di utenti accede contemporaneamente, subito dopo un'interruzione di rete importante o durante un errore del server RADIUS nel failover dei punti di accesso senza fili al server di backup.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: nessuno
  
-   **Frequenza**: attività di configurazione
  
-   **Requisiti di tecnologia**: nessuno
  
###### Dettagli relativi all'attività
  
L'attività di test interna di Microsoft ha mostrato che IAS può raggiungere un carico massimo, su hardware modesto, in grado di servire la maggior parte delle esigenze dei clienti. La stima del numero di autenticazioni che IAS è in grado di gestire deve essere espressa in autenticazioni al secondo. IAS è in grado di raggiungere le seguenti prestazioni con un server Intel Pentium 4 a 2 GHz su cui viene eseguito Windows Server 2003 con Active Directory su un altro server Intel Pentium 4 a 2 GHz.
  
**Tabella 12.10. Determinazione del carico sul server IAS**

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
<td style="border:1px solid black;"><p>Nuove autenticazioni EAP-TLS con scheda di supporto per la ripartizione del carico</p></td>
<td style="border:1px solid black;"><p>50</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazioni con Riconnessione rapida</p></td>
<td style="border:1px solid black;"><p>166</p></td>
</tr>  
</tbody>  
</table>
  
**Nota:** queste informazioni vengono fornite senza alcuna garanzia e devono essere intese come mere linee guida ai fini della pianificazione della capacità e non ai fini di un confronto fra prestazioni.
  
IAS può essere configurato in modo che generi registri di testo basati su disco contenenti quantità variabili di informazioni sulle richieste RADIUS. È preferibile pianificare l'utilizzo di un disco ad alte prestazioni per l'archiviazione di registri RADIUS a causa del sovraccarico che le attività di registrazione RADIUS comportano per i server RADIUS. I sottosistemi disco a bassa velocità possono ritardare le risposte RADIUS IAS ai punti di accesso senza fili, con conseguenti timeout dei protocolli e inutili operazioni di failover dei punti di accesso senza fili ai server RADIUS secondari. Per ulteriori informazioni sulle opzioni di registrazione di RADIUS, vedere il capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili".
  
Inoltre, se si attivano le funzionalità di analisi software di Windows Server 2003 (come descritto nella precedente sezione "Attivazione e disattivazione dell'analisi sul server IAS"), verrà imposto un ulteriore carico sui server IAS. Occasionalmente, tuttavia, può essere necessario attivare le funzionalità di analisi per risolvere problemi di accesso alla rete. I server IAS dovrebbero avere la capacità di funzionare e gestire il carico di produzione anche quando le funzionalità di analisi sono attive per brevi periodi di tempo.
  
##### Determinazione dei requisiti di archiviazione e di backup per un server IAS
  
In questa sezione vengono forniti i dettagli sulla capacità per i parametri di archiviazione IAS. Tali dettagli consentono ai pianificatori della capacità di calcolare i requisiti futuri per l'archiviazione di backup su disco in linea e non in linea.
  
###### Riepilogo delle informazioni
  
-   **Requisiti di protezione**: nessuno
  
-   **Frequenza**: quando necessario
  
-   **Requisiti di tecnologia**: nessuno
  
###### Dettagli relativi all'attività
  
I file registro RADIUS IAS sono l'unico componente dei server IAS per il quale è necessaria la pianificazione dell'archiviazione. I registri delle richieste RADIUS per questa soluzione sono configurati in modo da creare un registro nuovo ogni mese, mentre l'hardware sottoposto a test durante lo sviluppo di questa soluzione includeva un volume disco di 18 GB dedicato ai file registro.
  
Per simulare il processo di autenticazione dei client senza fili al server IAS e la generazione di dati di registro, è necessario fare una stima del carico sui server IAS dell'ambiente, quindi scegliere le opzioni di registrazione ed eseguire i test in un ambiente di laboratorio. Per le stime, è possibile utilizzare una logica simile a quella riportata di seguito:
  
Il numero medio di utenti per ogni punto di accesso senza fili è 25 (utenti o computer). Ogni utente o computer esegue un'autenticazione iniziale ed effettua la riautenticazione ogni 10 - 60 minuti (in base ai requisiti di protezione). Ogni autenticazione genera 1 kilobyte (KB) di informazioni di registrazione su disco (vengono registrate le richieste di autenticazione e le richieste di controllo, non le richieste provvisorie). Le dimensioni del file variano a seconda delle opzioni di registrazione. È preferibile calcolare la quantità di spazio di registrazione su disco generata per punto di accesso senza fili ogni ora per supportare 25 client. A questo punto, eseguire la stima del massimo numero di punti di accesso senza fili che il server IAS principale supporterà nelle ore di carico della rete o di failover del server.
  
I registri delle richieste RADIUS IAS contengono dati altamente comprimibili. Sebbene non sia consigliabile utilizzarla normalmente, in caso di necessità è possibile attivare la compressione della cartella dei file registro delle richieste RADIUS. Tenere presente che un server IAS a cui viene richiesta la compressione dei dati sarà sottoposto a un carico aggiuntivo.
  
###### Intervallo di backup per i file registro RADIUS IAS
  
Considerando un backup di rete che funziona in condizioni ideali su uno switch dedicato da 100 Mbps e collegato al server di backup, il backup di un database da 3 GB e di uno stato del sistema di 500 MB richiederà circa 15 - 20 minuti.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di modifica
  
Nella fase di modifica, sono inclusi i processi e le procedure necessari a identificare, analizzare, approvare e incorporare le modifiche in un ambiente IT gestito. Le modifiche includono le risorse hardware e software nonché le modifiche di processi e procedure specifici.
  
Obiettivo del processo di modifica è introdurre rapidamente nell'ambiente IT, con disagi minimi al servizio, nuove tecnologie, sistemi, applicazioni, hardware, strumenti e processi, nonché modifiche dei ruoli e delle responsabilità.
  
#### Gestione delle modifiche
  
La funzione SMF di gestione delle modifiche è responsabile della gestione delle modifiche in un ambiente IT. Obiettivo principale del processo di gestione delle modifiche è assicurare che tutte le parti interessate da una determinata modifica siano consapevoli dell'impatto dell'imminente modifica. Poiché la maggior parte dei sistemi è strettamente correlata, le modifiche apportate a una parte del sistema potrebbero avere notevoli ripercussioni su un'altra parte. La gestione delle modifiche cerca di identificare tutti i sistemi e i processi interessati prima che la modifica sia distribuita, in modo da ridurre o eliminare qualsiasi effetto negativo. In genere, l'ambiente di destinazione, o ambiente gestito, è l'ambiente di produzione; tuttavia, sarebbe opportuno includere gli ambienti di integrazione, test e temporanei principali.
  
Tutte le modifiche all'infrastruttura RADIUS e alla protezione WLAN dovranno seguire il processo di gestione delle modifiche MOF standard illustrato di seguito.
  
1.  **Richiesta di modifica** L’inizializzazione formale di una modifica mediante l’invio di una richiesta di modifica (RFC).
  
2.  **Classificazione della modifica** L’assegnazione di una priorità e di una categoria alla modifica, considerando come criterio l’urgenza ed il relativo impatto sull’infrastruttura o sugli utenti. Tale assegnazione influisce sulla velocità e sul percorso dell'implementazione.
  
3.  **Autorizzazione della modifica** La considerazione e approvazione o disapprovazione della modifica da parte del gestore delle modifiche e del consiglio di analisi delle modifiche costituito dai rappresentanti aziendali e IT.
  
4.  **Sviluppo della modifica** La pianificazione e lo sviluppo della modifica, un processo che può variare molto a seconda degli obiettivi ed include le analisi degli obiettivi chiave.
  
5.  **Rilascio della modifica** Il rilascio e la distribuzione della modifica nell’ambiente di produzione.
  
6.  **Analisi della modifica** Il processo successivo all'implementazione che verifica se la modifica ha raggiunto gli obiettivi stabiliti e stabilisce se conservarla oppure ritirarla.
  
Le procedure di questa sezione illustrano come sviluppare alcune delle modifiche principali che probabilmente saranno necessarie regolarmente nell'ambiente in uso. Ciascuna procedura di sviluppo delle modifiche è affiancata da una procedura di rilascio in cui sono descritte le modalità di distribuzione della modifica nella produzione.
  
##### Gestione degli aggiornamenti del sistema operativo
  
La gestione degli aggiornamenti di sicurezza per i componenti software RADIUS e WLAN fa parte della gestione generale delle patch di Windows. Questo argomento è trattato in due guide delle soluzioni di Microsoft che descrivono gli aggiornamenti del sistema operativo Windows mediante Microsoft Systems Management Server (SMS) o Microsoft Software Update Services (SUS). Per i dettagli su come ottenerle, consultare la sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
La gestione delle patch include componenti di gestione del rilascio e componenti di gestione della configurazione, nonché un componente di gestione delle modifiche. Tuttavia, tutte e tre le funzioni SMF sono trattate nei documenti a cui è stato fatto riferimento nei paragrafi precedenti.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Tabelle di configurazione
  
Le tabelle seguenti contengono le informazioni di configurazione specifiche del sito e della soluzione utilizzate nelle procedure di questo capitolo. Queste tabelle sono un sottogruppo delle tabelle di configurazione della pianificazione riportata nel capitolo 8, "Implementazione dell'infrastruttura RADIUS", e nel capitolo 9, "Implementazione dell'infrastruttura per la protezione di reti LAN senza fili", e sono solo di riferimento.
  
#### Parametri di configurazione per sito
  
**Tabella 12.11. Elementi di configurazione definiti dall'utente**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Elemento di configurazione</p></th>  
<th><p>Impostazione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome DNS del dominio principale dell'insieme di strutture di Microsoft Active Directory</p></td>
<td style="border:1px solid black;"><p>woodgrovebank.com</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Nome NetBIOS del dominio</p></td>
<td style="border:1px solid black;"><p>WOODGROVEBANK</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome del server IAS primario</p></td>
<td style="border:1px solid black;"><p>HQ- IAS - 01</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Nome del server IAS secondario</p></td>
<td style="border:1px solid black;"><p>HQ - IAS - 02</p></td>
</tr>  
</tbody>  
</table>
  
#### Parametri di configurazione della soluzione
  
**Tabella 12.12. Elementi di configurazione definiti dalla soluzione**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Elemento di configurazione</p></th>  
<th><p>Impostazione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Nome completo del gruppo amministrativo che controlla la configurazione del Servizio autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>IAS Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Nome precedente a Windows 2000 del gruppo amministrativo che controlla la configurazione del Servizio autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>IAS Admins</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Nome completo del gruppo che rivede il registro IAS delle richieste di account e di autenticazione per motivi di sicurezza</p></td>
<td style="border:1px solid black;"><p>IAS Security Auditors</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Nome pre-Windows 2000 del gruppo che esamina i registri delle richieste di autenticazione e accounting IAS a fini di protezione</p></td>
<td style="border:1px solid black;"><p>IAS Security Auditors</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Gruppo globale Active Directory contenente gli utenti che richiedono certificati di autenticazione 802.1x</p></td>
<td style="border:1px solid black;"><p>Registrazione automatica autenticazione client - Certificato utente</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Gruppo globale Active Directory contenente i computer che richiedono certificati di autenticazione 802.1x</p></td>
<td style="border:1px solid black;"><p>Registrazione automatica autenticazione client - Certificato computer</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Gruppo globale Active Directory contenente i server IAS che richiedono certificati di autenticazione 802.1X</p></td>
<td style="border:1px solid black;"><p>Registrazione automatica certificato di autenticazione server RAS e IAS</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Nome pre-Windows 2000 del gruppo globale Microsoft Active Directory contenente i server IAS che richiedono certificati di autenticazione 802.1X</p></td>
<td style="border:1px solid black;"><p>Registrazione automatica certificato di autenticazione server RAS e IAS</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Gruppo globale di Active Directory in cui sono inclusi gli utenti a cui è concesso l'accesso alla rete senza fili</p></td>
<td style="border:1px solid black;"><p>Criteri di accesso remoto - Utenti senza fili</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Gruppo globale di Active Directory in cui sono inclusi i computer a cui è concesso l'accesso alla rete senza fili</p></td>
<td style="border:1px solid black;"><p>Criteri di accesso remoto - Computer senza fili</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Gruppo universale di Active Directory in cui sono inclusi il gruppo Utenti senza fili e il gruppo Computer senza fili</p></td>
<td style="border:1px solid black;"><p>Criteri di accesso remoto - Accesso senza fili</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Gruppo globale Active Directory contenente i computer che richiedono la configurazione delle proprietà della rete senza fili mediante Criteri di gruppo di Active Directory</p></td>
<td style="border:1px solid black;"><p>Criteri di rete senza fili - Computer</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Certificati] Modello di certificato utilizzato per generare certificati per l'autenticazione client di utenti</p></td>
<td style="border:1px solid black;"><p>Autenticazione client - Utente</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Certificati] Modello di certificato utilizzato per generare certificati per l'autenticazione client di computer</p></td>
<td style="border:1px solid black;"><p>Autenticazione client - Computer</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Certificati] Modello di certificato utilizzato per generare certificati per l'autenticazione server eseguita da IAS</p></td>
<td style="border:1px solid black;"><p>Autenticazione server RAS e IAS</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Scripts] Percorso degli script di installazione</p></td>
<td style="border:1px solid black;"><p>C:\MSSScripts</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Script] File batch per l'esportazione della configurazione IAS</p></td>
<td style="border:1px solid black;"><p>IASExport.bat</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Script] File batch per l'importazione della configurazione IAS</p></td>
<td style="border:1px solid black;"><p>IASImport.bat</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Script] File batch per l'esportazione della configurazione client RADIUS IAS</p></td>
<td style="border:1px solid black;"><p>IASClientExport.bat</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Script] File batch per l'importazione della configurazione client RADIUS IAS</p></td>
<td style="border:1px solid black;"><p>IASClientImport.bat</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Config] Percorso dei file di backup della configurazione</p></td>
<td style="border:1px solid black;"><p>D:\IASConfig</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Registri richieste] Posizione dei file registro di autenticazione e delle richieste di controllo IAS</p></td>
<td style="border:1px solid black;"><p>D:\IASLogs</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Request Logs] Nome della condivisione dei registri delle richieste RADIUS</p></td>
<td style="border:1px solid black;"><p>IASLogs</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Criteri di accesso remoto] Nome criterio</p></td>
<td style="border:1px solid black;"><p>Consenti accesso senza fili</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>[Criteri di gruppo] Nome dell'oggetto Criteri di gruppo di Microsoft Active Directory</p></td>
<td style="border:1px solid black;"><p>Criterio di rete senza fili</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>[Criterio di gruppo] Criterio di rete senza fili nell'oggetto Criteri di gruppo</p></td>
<td style="border:1px solid black;"><p>Configurazione senza fili del computer client</p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
-   Per ulteriori informazioni sul modello di processo e sul modello di team MOF, consultare [Microsoft Operations Framework](http://www.microsoft.com/mof) all'indirizzo www.microsoft.com/technet/itsolutions/techguide/mof/default.mspx (in inglese).
  
-   Per ulteriori informazioni sui vincoli di capacità e sui relativi contatori delle prestazioni, consultare l'articolo Q146005 della Microsoft Knowledge Base, "[Optimizing Windows NT for Performance](http://support.microsoft.com/default.aspx?kbid=146005)", all'indirizzo http://support.microsoft.com/default.aspx?scid=146005 (in inglese).
  
-   Per informazioni sulla risoluzione dei problemi delle reti senza fili, vedere:
  
    -   L'articolo Q313242 della Microsoft Knowledge Base, "[How to troubleshoot wireless network connections in Windows XP](http://support.microsoft.com/?kbid=313242)", all'indirizzo http://support.microsoft.com/?scid=313242 (in inglese).
  
    -   Il white paper ["Troubleshooting Windows XP IEEE 802.11 Wireless Access](http://technet.microsoft.com/en-us/library/bb457017.aspx)" all'indirizzo www.microsoft.com/windowsxp/pro/techinfo/administration/  
        networking/troubleshooting.asp (in inglese).
  
-   Per informazioni sulla distribuzione di MOM, consultare [*MOM 2000 SP1 Operations Guide*](http://www.microsoft.com/resources/documentation/mom/2000sp1/all/opsguide/en-us/1_in781g.mspx) all'indirizzo www.microsoft.com/resources/documentation/mom/2000sp1/all/opsguide/en-us/1\_in781g.mspx (in inglese).
  
-   Per informazioni sulla gestione delle patch con Microsoft SMS 2003, consultare il documento "[Patch Management Using Microsoft Systems Management Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=959ee7d6-7ddf-409a-9522-7d270bdcf12a&displaylang=en)" all'indirizzo www.microsoft.com/technet/itsolutions/techguide/msm/swdist/pmsms/2003/pmsms031.mspx (in inglese).
  
-   Per informazioni sulla gestione delle patch con Microsoft Software Update Services, vedere "[Patch Management Using Microsoft Software Update Services](http://technet.microsoft.com/wsus/default.aspx)" all'indirizzo www.microsoft.com/technet/itsolutions/techguide/msm/swdist/pmsus/pmsus251.mspx (in inglese).
  
-   Per informazioni su come ottenere ed utilizzare la Console di gestione Criteri di gruppo (GPMC, Group Policy Management Console), vedere "[Enterprise Management with the Group Policy Management Console](http://www.microsoft.com/windowsserver2003/gpmc/default.mspx)" all'indirizzo www.microsoft.com/windowsserver2003/gpmc/default.mspx (in inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
