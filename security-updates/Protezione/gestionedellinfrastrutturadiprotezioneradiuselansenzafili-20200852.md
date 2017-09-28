---
TOCTitle: 'Gestione dell''infrastruttura di protezione RADIUS e LAN senza fili'
Title: 'Gestione dell''infrastruttura di protezione RADIUS e LAN senza fili'
ms:assetid: 'ca27de71-ea36-44ec-b832-461cfb05bd0b'
ms:contentKeyID: 20200852
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536253(v=TechNet.10)'
---

Lavorare con una rete locale wireless sicura grazie a Windows Server 2003 Certificate Services
==============================================================================================

### Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili

##### In questa pagina

[](#elaa)[Argomenti del modulo](#elaa)
[](#ekaa)[Obiettivi](#ekaa)
[](#ejaa)[Ambito di applicazione](#ejaa)
[](#eiaa)[Utilizzo del modulo](#eiaa)
[](#ehaa)[Attività fondamentali di manutenzione](#ehaa)
[](#egaa)[Ruoli amministrativi di RADIUS e della protezione WLAN](#egaa)
[](#efaa)[Attività della fase operativa](#efaa)
[](#eeaa)[Attività della fase di supporto](#eeaa)
[](#edaa)[Attività della fase di ottimizzazione](#edaa)
[](#ecaa)[Attività della fase di modifica](#ecaa)
[](#ebaa)[Tabelle di configurazione](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Argomenti del modulo

In questo modulo vengono descritte le procedure operative necessarie per la gestione dell'infrastruttura RADIUS (Remote Authentication Dial-In User Service) e della protezione WLAN implementate nel contesto della soluzione [*Securing Wireless LAN - Microsoft® Windows® Server™ 2003 Certificate Services Solution*](http://www.microsoft.com/downloads/details.aspx?familyid=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en) (in inglese). La struttura si basa sulle categorie MOF (Microsoft Operational Framework) e sui concetti discussi nel primo modulo della *Guida operativa*.

Lo scopo di questo modulo è di consentire l'implementazione di un sistema di gestione completo per l'infrastruttura RADIUS e la protezione WLAN. Tale sistema include tutte le attività di impostazione necessarie per avviare il monitoraggio e la manutenzione del sistema. Vengono inoltre descritte le attività operative da eseguire con regolarità per mantenere il corretto funzionamento del sistema, le procedure per consentire all'utente di gestire problemi di supporto, modifiche all'ambiente, nonché di ottimizzare le prestazioni del sistema.

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Il modulo consente di:

-   Comprendere le attività da eseguire per la gestione protetta del sistema.

-   Assegnare i ruoli amministrativi necessari per l'amministrazione del sistema.

-   Fornire un documento di riferimento per la gestione dell'infrastruttura RADIUS.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Questo modulo si applica ai seguenti prodotti e tecnologie:

-   Microsoft Windows Server 2003

-   Servizi di Autenticazione Internet di Microsoft (IAS)

-   Servizio Microsoft Active Directory®

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

In questo modulo sono descritte le fasi necessarie a mantenere un ambiente gestito correttamente per l'infrastruttura RADIUS. La parte restante del modulo deve essere considerata come materiale di riferimento.

Per sfruttare al massimo il presente modulo:

-   Leggere il modulo "[Guida operativa alla protezione delle LAN senza fili: introduzione](http://technet.microsoft.com/it-it/cc645531.aspx)", in cui viene illustrato Microsoft Operations Framework, dal momento che il presente modulo è strutturato come una guida operativa di MOF.

[](#mainsection)[Inizio pagina](#mainsection)

### Attività fondamentali di manutenzione

In questa sezione sono elencate le attività principali da eseguire per un corretto funzionamento dell'infrastruttura RADIUS e della protezione WLAN. Le attività sono elencate in due tabelle: attività iniziali di configurazione e attività operative continue. I nomi delle attività elencate nelle tabelle sono descritti dettagliatamente più avanti nel documento. Le attività sono raggruppate in base alla fase MOF, mentre la funzione di gestione dei servizi (SMF, Service Management Function) cui appartiene l'attività è indicata accanto a questa, in modo che sia più semplice trovarla.

In questa sezione è incluso anche un elenco degli strumenti e delle tecnologie utilizzate nelle procedure di questo modulo.

#### Attività iniziali di configurazione

In questa tabella sono illustrate le attività che occorre eseguire per rendere operative l'infrastruttura RADIUS e la protezione WLAN. A seconda dello standard operativo e delle procedure utilizzate potrebbe non essere necessario eseguire tutte le attività. Esaminare in dettaglio le attività per decidere se eseguirle o meno. È anche possibile che alcune di queste attività debbano essere eseguite nuovamente. Ad esempio, se viene installato un nuovo server IAS, sarà necessario configurare le operazioni di backup e di monitoraggio per questo server.

**Tabella 1. Attività iniziali di configurazione**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome attività</p></th>
<th><p>Cluster di ruoli</p></th>
<th><p>Funzione SMF MOF</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Fase di operatività</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Aggiunta di client RADIUS ai server IAS</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Amministrazione di rete</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Aggiunta di computer ai gruppi di criteri delle reti senza fili</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Amministrazione dei servizi directory</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Aggiunta di computer e utenti ai gruppi di criteri di accesso remoto</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Amministrazione dei servizi directory</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Classificazione degli avvisi di monitoraggio</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Monitoraggio e controllo dei servizi</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Monitoraggio dei vincoli di capacità di IAS</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Monitoraggio e controllo dei servizi</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Configurazione dell'esportazione della configurazione IAS</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Esportazione della configurazione dei client RADIUS</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Configurazione del backup delle directory di dati IAS</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Test del backup IAS</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Fase di ottimizzazione</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Determinazione del carico massimo sul server IAS</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Gestione della capacità</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Determinazione dei requisiti di archiviazione e di backup per un server IAS</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Gestione della capacità</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Fase di modifica</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Gestione delle patch del sistema operativo</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Gestione delle modifiche e gestione dei rilasci</p></td>
</tr>
</tbody>
</table>
  
Sebbene non esista un'attività documentata per impostare un sistema di gestione della configurazione per l'infrastruttura RADIUS e la protezione WLAN, occorre verificare le procedure nella sezione relativa alla gestione della configurazione, in cui sono descritti i tipi di informazioni che è necessario raccogliere e conservare nella gestione della configurazione.
  
#### Attività di manutenzione
  
In questa tabella sono illustrate le attività che occorre eseguire regolarmente per mantenere in perfetto stato di funzionamento l'infrastruttura RADIUS e la protezione WLAN. La tabella può essere utilizzata nella pianificazione delle risorse necessarie e nella pianificazione operativa dell'amministrazione del sistema.
  
È possibile che esistano alcune attività che non occorre eseguire; tuttavia, prima di decidere è opportuno verificarne i dettagli. È anche possibile che alcune di queste attività debbano essere eseguite occasionalmente oltre ad essere pianificate. Ad esempio, se viene aggiunto un client RADIUS a un server IAS, sarà necessario eseguire un'esportazione/backup della configurazione del server anche se questa non è pianificata. In questo caso, viene fornita una nota nella colonna della frequenza. Dipendenze di questo tipo vengono anche annotate nei dettagli stessi dell'attività.
  
**Tabella 2. Attività di manutenzione continue**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome attività</p></th>
<th><p>Cluster di ruoli</p></th>
<th><p>Frequenza</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Aggiunta di client RADIUS ai server IAS</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Ogni volta che vengono aggiunti alla rete dei punti di accesso senza fili (AP, Access Points)</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Rimozione di client RADIUS dal server IAS</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Ogni volta che dei punti di accesso senza fili vengono rimossi dalla rete</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Aggiunta di computer ai gruppi di criteri delle reti senza fili</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Ogni volta che vengono aggiunti dei computer alla rete</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Aggiunta di computer e utenti ai gruppi di criteri di accesso remoto</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Ogni volta che ai dipendenti viene concesso l'accesso alla rete WLAN</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Esportazione della configurazione dei client RADIUS</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Ogni volta che alla rete vengono aggiunti punti di accesso senza fili</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Test del backup IAS</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Ogni mese</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Accesso ai registri delle richieste RADIUS IAS</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Ogni giorno oppure ogni settimana (a seconda dei requisiti di protezione)</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Verifica delle voci del Registro eventi di autenticazione RADIUS IAS</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Ogni giorno oppure ogni settimana (a seconda dei requisiti di protezione)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Archiviazione ed eliminazione delle voci del registro RADIUS IAS</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Ogni mese</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Gestione delle patch del sistema operativo</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Ogni giorno</p></td>
</tr>
</tbody>
</table>
  
#### Tecnologia richiesta nella Guida operativa
  
Nella tabella riportata di seguito sono elencati gli strumenti o le tecnologie utilizzati nelle procedure descritte in questa guida.
  
**Tabella 3. Tecnologia richiesta**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome elemento</p></th>
<th><p>Origine</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Console di gestione Utenti e computer di Active Directory</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Script MSS</p></td>
<td style="border:1px solid black;"><p>Questa soluzione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Editor di testo</p></td>
<td style="border:1px solid black;"><p>Blocco note — Windows Server 2003</p></td>
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
<td style="border:1px solid black;"><p>Backup di Windows</p></td>
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
<td style="border:1px solid black;"><p>Servizio di backup aziendale o<br />
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
  
**Tabella 4. Tecnologia consigliata**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome elemento</p></th>
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
<td style="border:1px solid black;"><p>Server e client SMTP/POP3/IMAP, ad esempio Microsoft Exchange Server e il client di messaggistica e collaborazione Microsoft Outlook®</p></td>
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
<td style="border:1px solid black;"><p>Sistema di distribuzione delle patch</p></td>
<td style="border:1px solid black;"><p>Microsoft Systems Management Server o Microsoft Software Update Services</p></td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ruoli amministrativi di RADIUS e della protezione WLAN
  
I ruoli coinvolti nella gestione di un'infrastruttura RADIUS e della protezione WLAN sono molteplici. Nelle due sezioni che seguono sono stati suddivisi in ruoli fondamentali e ruoli di supporto.
  
#### Ruoli RADIUS e WLAN fondamentali
  
Si tratta di ruoli centrali nella gestione di un'infrastruttura RADIUS e della protezione WLAN. Tali ruoli corrispondono a vari cluster di ruoli MOF descritti nel modulo "[Guida alla pianificazione della protezione di reti LAN senza fili: introduzione](http://technet.microsoft.com/it-it/library/dd536254)".
  
**Tabella 5. Ruoli fondamentali per l'infrastruttura RADIUS e la protezione WLAN**

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
<th><p>Cluster di ruoli MOF</p></th>
<th><p>Ambito</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore del Servizio di autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile dell'amministrazione e della configurazione generale di IAS per l'organizzazione di grandi dimensioni</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Controllore del Servizio di autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile della verifica, dell'archiviazione e dell'eliminazione dei registri RADIUS nei computer server IAS</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Operatore di backup del Servizio di autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>Operatività</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile del backup e del ripristino dello stato di configurazione IAS e dei dati cronologici</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Personale del supporto tecnico WLAN</p></td>
<td style="border:1px solid black;"><p>Supporto</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile principale del personale del supporto tecnico per la risoluzione dei problemi WLAN</p></td>
</tr>
</tbody>
</table>
  
#### Ruoli di supporto per l'infrastruttura RADIUS e la protezione WLAN
  
Si tratta di ruoli operativi, che non sono centrali nella gestione dell'infrastruttura RADIUS e della protezione WLAN ma che forniscono funzioni di supporto ai ruoli fondamentali.
  
**Tabella 6. Ruoli di supporto per l'infrastruttura RADIUS e la protezione WLAN**

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
<th><p>Cluster di ruoli MOF</p></th>
<th><p>Ambito</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Operatore di monitoraggio</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile del monitoraggio degli eventi</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Pianificatore della capacità</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile dell'analisi delle prestazioni e del carico per la previsione dei requisiti di capacità futuri</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore di Active Directory</p></td>
<td style="border:1px solid black;"><p>Infrastruttura e supporto</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile della configurazione e del supporto dell'infrastruttura Active Directory</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Gestione delle operazioni di Active Directory</p></td>
<td style="border:1px solid black;"><p>Operatore</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile della manutenzione quotidiana della directory, ad esempio della manutenzione dei gruppi di protezione, della creazione degli account e così via</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore desktop</p></td>
<td style="border:1px solid black;"><p>Infrastruttura e supporto</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile della configurazione e del supporto dei computer desktop</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Consiglio di approvazione delle modifiche</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Rappresentanti aziendali e tecnici ai quali viene richiesto di approvare le modifiche all'infrastruttura</p></td>
</tr>
</tbody>
</table>
  
#### Mapping dei ruoli con i gruppi di protezione
  
Nella tabella seguente sono elencati i gruppi di protezione definiti per questa soluzione e vengono brevemente descritte le funzionalità o le autorizzazioni di ogni gruppo.
  
Per i server IAS, i gruppi di protezione di dominio e locali vengono utilizzati per applicare le autorizzazioni specifiche di ciascun ruolo. Gli account di dominio sono utilizzati per popolare i gruppi di ruoli. Anche in questo caso, i singoli account possono essere membri di più gruppi di ruoli se previsto dai criteri di protezione e IT dell'organizzazione.
  
**Tabella 7. Mapping dei ruoli RADIUS e di protezione WLAN con i gruppi di protezione**

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
<td style="border:1px solid black;"><p>Controllori del Servizio di autenticazione Internet</p></td>
<td style="border:1px solid black;"><p>IAS Security Auditors</p></td>
<td style="border:1px solid black;"><p>N/D</p></td>
<td style="border:1px solid black;"><p>Capacità di leggere ed eliminare i file registro delle richieste RADIUS nel volume di registrazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Operatori di backup IAS</p></td>
<td style="border:1px solid black;"><p>N/D</p></td>
<td style="border:1px solid black;"><p>Backup Operators</p></td>
<td style="border:1px solid black;"><p>Backup e ripristino completi dello stato del sistema operativo e dei dati di configurazione IAS</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Personale del supporto tecnico WLAN</p></td>
<td style="border:1px solid black;"><p>N/D</p></td>
<td style="border:1px solid black;"><p>N/D</p></td>
<td style="border:1px solid black;"><p>Collabora con il gruppo IAS Administrators per risolvere i problemi di autenticazione IAS (in alcuni casi può disporre delle autorizzazioni di lettura per le stesse risorse dei controllori della protezione IAS)</p></td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase operativa
  
Nella fase operativa sono inclusi gli standard operativi IT, i processi e le procedure che vengono applicati regolarmente alle soluzioni di servizi per raggiungere e mantenere livelli di servizio entro parametri predeterminati. L'obiettivo della fase operativa è un'esecuzione altamente prevedibile delle attività quotidiane, sia manuali sia automatiche.
  
In questa sezione vengono fornite le informazioni relative alle seguenti funzioni di gestione dei servizi:
  
-   Amministrazione di rete
  
-   Amministrazione dei servizi directory
  
-   Amministrazione della protezione
  
-   Gestione dell'archiviazione
  
-   Monitoraggio e controllo dei servizi
  
-   Pianificazione dei processi
  
Non esistono attività per le restanti funzioni di gestione dei servizi:
  
-   Gestione dei sistemi
  
-   Gestione della rete
  
-   Gestione della stampa e degli output
  
#### Amministrazione di rete
  
Il ruolo di amministrazione di rete è responsabile della progettazione e della manutenzione dei componenti fisici che costituiscono la rete dell'organizzazione, ad esempio i server, i router, gli switch e i firewall. Nel caso delle reti senza fili sono inclusi anche i punti di accesso senza fili e i server di configurazione RADIUS per supportarli.
  
##### Aggiunta di client RADIUS ai server IAS
  
Per eseguire l'autenticazione e l'accounting con i server IAS occorre che i punti di accesso senza fili siano autorizzati. L'attivazione di nuovi punti di accesso senza fili come client RADIUS è una delle poche modifiche da apportare a un server IAS di produzione distribuito. Questa attività consente al punto di accesso senza fili di partecipare all'autenticazione RADIUS e all'accounting con il server IAS. Eseguire questa attività ogni volta che nuovi punti di accesso senza fili vengono distribuiti e configurati per la partecipazione all'autenticazione di rete.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni volta che alla rete vengono aggiunti nuovi punti di accesso senza fili</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Appartenenza al gruppo di protezione IAS Admins</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Informazioni relative ai punti di accesso senza fili Accesso al disco dei client RADIUS di ciascun server (ubicato in un archivio protetto)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>Snap-in MMC (Microsoft Management Console) IAS<br />
Script MSS (per GenPwd) Unità disco floppy o altro unità per supporti rimovibili e scrivibili<br />
Disco floppy o altri supporti rimovibili e scrivibili</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Per la massima protezione occorre aggiungere ogni punto di accesso senza fili a ciascun server IAS utilizzando una password pseudo-casuale (segreto) unica per la coppia. La condivisione di segreti RADIUS tra i punti di accesso senza fili e i server RADIUS aumenta il rischio che il segreto condiviso non resti tale a lungo.

Windows Server 2003 Enterprise Edition consente agli amministratori l'aggiunta globale di punti di accesso a IAS aggiungendo la subnet client RADIUS dedicata e utilizzando il segreto condiviso. Tuttavia, questa strategia presenta un rischio di protezione e deve essere considerata con attenzione.

Questa soluzione implementa, mediante la crittografia, segreti casuali generati dallo script GenPwd incluso in queste guide.

-   **Per aggiungere singoli client RADIUS a IAS**

    1.  Dallo snap-in MMC IAS, fare clic con il pulsante destro del mouse sulla cartella **Client RADIUS**, quindi su **Nuovo client RADIUS**.

    2.  Immettere il nome descrittivo nel campo **Nome** e l'indirizzo del client nel campo **Indirizzo client (IP o DNS)** per il punto di accesso senza fili. Selezionare l'indirizzo IP piuttosto che il nome DNS se possibile, dal momento che IAS cercherà di risolvere ciascun client RADIUS all'avvio del server e questa operazione, in ambienti di grandi dimensioni con un gran numero di punti di accesso senza fili, può influire sui parametri della capacità del server. Scegliere **Avanti**.

    3.  Selezionare **Standard RADIUS** come attributo client-fornitore e immettere il segreto condiviso per questo particolare punto di accesso senza fili.

        **Nota:** per le fasi che seguono si utilizzerà un disco floppy o un altro supporto rimovibile e scrivibile. Individuare un disco formattato ed etichettarlo "Client RADIUS per MSS server - IAS - 01". Sostituire, nell'etichetta, "MSS - IAS - 01" con il nome del server IAS in uso.

    4.  È possibile utilizzare lo script GenPwd incluso in queste guide per generare un segreto sicuro pseudo-casuale per l'utilizzo singolo da parte di ciascun WAP configurato come client RADIUS. GenPwd genererà un segreto e lo archivierà in un file Clients.txt insieme a un nome descrittivo per ciascun client RADIUS. GenPwd aggiunge automaticamente le informazioni a un file Clients.txt nella directory corrente sotto forma di valori separati da virgola. Tuttavia, se si dispone di un metodo per generare e archiviare segreti RADIUS sicuri, è possibile utilizzarlo al posto dei passaggi di GenPwd indicati di seguito.

    5.  Aprire il prompt dei comandi e rendere la directory A:\\ la directory corrente. Il percorso della directory nel file system è importante, in quanto le nuove informazioni verranno aggiunte al file Clients.txt della directory corrente. Se non esiste un file Clients.txt, ne verrà creato uno.

    6.  Eseguire il seguente comando. Accertarsi di sostituire il **\[nome client\]** con il nome descrittivo del punto di accesso senza fili. Questo potrebbe essere un nome DNS, un indirizzo IP o un'altra stringa:

        cscript //job:GenPwd C:\\MSSScripts\\wl\_tools.wsf /client:\[nome client\]

        Una volta creato, il file separato da virgole può essere facilmente importato in un foglio di calcolo o in un'applicazione di database come riferimento e per le modifiche.

        **Nota:** è opportuno cambiare i segreti RADIUS per ciascun server IAS e punto di accesso senza fili periodicamente. Accertarsi di utilizzare GenPwd o un'altra utilità per generare segreti sicuri e archiviare il nuovo segreto e il nome del punto di accesso senza fili nel file Clients.txt.

    7.  Immettere il segreto condiviso RADIUS nei campi **Segreto condiviso** e **Conferma segreto condiviso**. Selezionare il campo **La richiesta deve contenere l'attributo autenticatore del messaggio** e fare clic su **Fine**:

    **Nota:** alcuni client RADIUS potrebbero richiedere attributi di configurazione specifici del fornitore per funzionare correttamente. Per informazioni sui requisiti degli attributi specifici del fornitore, consultare la documentazione del fornitore.

##### Rimozione di client RADIUS dai server IAS

La rimozione di punti di accesso senza fili di versioni precedenti utilizzati come client RADIUS è una delle poche modifiche da apportare a un server IAS di produzione distribuito. Mediante questa attività i punto di accessi senza fili perdono la capacità di partecipare all'autenticazione RADIUS e all'accounting con il server IAS. Eseguire questa attività ogni volta che i punti di accesso senza fili vengono ritirati, in modo da disattivare la capacità di eseguire l'autenticazione RADIUS e l'accounting con IAS.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni volta che dei punti di accesso senza fili vengono rimossi dalla rete</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Membro del gruppo IAS Administrators</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Informazioni sul client RADIUS, quali indirizzo IP o nome</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>- Snap-in MMC IAS<br />
- Editor di file di testo Notepad.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Ciascun punto di accesso senza fili deve essere rimosso in modo indipendente e occorre eliminare la voce corrispondente nel file Clients.txt del disco floppy del client RADIUS memorizzato in un archivio protetto. Il file Clients.txt viene creato mediante la procedura riportata nell'attività **Esportazione della configurazione dei client RADIUS**.

-   **Per rimuovere i client RADIUS dal server IAS**

    1.  Dallo snap-in MMC IAS, selezionare la cartella **Client RADIUS**.

    2.  Dal riquadro di destra, selezionare la voce che rappresenta il client RADIUS da rimuovere e premere **Canc**.

    3.  Alla richiesta di conferma, scegliere **Sì**.

        **Nota:** nei passaggi che seguono è previsto l'utilizzo di un disco floppy o di altro supporto rimovibile e scrivibile con l'etichetta "Client RADIUS per MSS server - IAS - 01", creato nella sezione precedente. Sostituire, nell'etichetta, "MSS - IAS - 01" con il nome del server IAS in uso. Accertarsi di utilizzare il disco corretto con il server appropriato per evitare la perdita di dati.

    4.  Individuare il disco floppy del client RADIUS per questo server e aprire il file A:\\Clients.txt utilizzando Blocco note.

    5.  Trovare ed eliminare la voce associata al client RADIUS da ritirare.

#### Amministrazione dei servizi directory

I servizi directory consentono agli utenti e alle applicazioni di trovare risorse di rete quali utenti, server, applicazioni, strumenti, servizi e altre informazioni nella rete. L'amministrazione dei servizi directory si occupa delle operazioni quotidiane, della manutenzione e del supporto della directory di un'organizzazione di grandi dimensioni. L'obiettivo dell'amministrazione dei servizi directory è assicurare che le informazioni nella rete siano accessibili tramite un processo semplice e organizzato, da parte di coloro che le richiedono e che dispongono delle autorizzazioni appropriate.

##### Aggiunta di computer ai gruppi di criteri per le reti senza fili

L'aggiunta di computer ai gruppi di protezione Criteri di gruppo basati su Active Directory della rete senza fili consente la configurazione automatica delle impostazioni della rete senza fili nei computer client. È necessario eseguire questa attività ogni volta che nell'ambiente viene introdotto un nuovo computer che dovrà utilizzare la rete senza fili.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni volta che alla rete vengono aggiunti computer portatili</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>- Amministratore di dominio o autorizzazione all'aggiunta di utenti al gruppo di protezione Criterio rete senza fili<br />
- Computer in Active Directory</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>- Creazione dell'oggetto Criteri di gruppo Wireless Network<br />
- Creazione del gruppo di protezione Wireless Network Policy<br />
- Computer</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Utenti e computer di Active Directory</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
Se i criteri della rete senza fili sono configurati e funzionali, l'aggiunta di altri computer ai gruppi di protezione che controllano l'applicazione del criterio è abbastanza semplice.
  
-   **Per aggiungere computer al gruppo di protezione dei criteri di gruppo della rete senza fili**
  
    1.  In Utenti e computer di Active Directory individuare il gruppo di protezione Criterio rete senza fili  
        - Computer che corrisponde al criterio della rete senza fili da applicare. È necessario accedere come utente che dispone delle autorizzazioni di modifica dell'appartenenza per il gruppo.
  
    2.  Aggiungere il computer al gruppo di protezione selezionato.
  
##### Aggiunta di computer e utenti ai gruppi di criteri di accesso remoto
  
L'aggiunta di computer e utenti al gruppo di criteri di accesso remoto consente l'accesso autorizzato alla rete WLAN. IAS utilizza l'appartenenza di questo gruppo ai criteri di accesso remoto come condizione per l'accesso. Per ottenere l'autorizzazione di accesso alla rete WLAN è necessario aggiungere computer e utenti ai gruppi di criteri di accesso remoto.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni volta che agli utenti viene concesso l'accesso alla WLAN</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratore di dominio o autorizzazione alla modifica dell'appartenenza dei gruppi di protezione Remote Access Policy<br />
- Wireless Users e Remote Access Policy<br />
- Wireless Computers in Active Directory</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze</p></td>
<td style="border:1px solid black;"><p>Creazione di gruppi di protezione dei criteri di accesso remoto Esistenza di computer e account utente in Active Directory</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta</p></td>
<td style="border:1px solid black;"><p>Console di gestione di Utenti e computer di Active Directory</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
Se sono stati creati i gruppi di protezione dei criteri di accesso remoto, l'aggiunta di ulteriori computer ai gruppi di protezione che controllano l'applicazione del criterio è abbastanza semplice.
  
-   **Per aggiungere utenti al gruppo di protezione dei criteri di accesso remoto**
  
    1.  Accedere a un computer amministrativo come amministratore di dominio o come utente con autorizzazione di protezione a modificare l'appartenenza del gruppo di protezione Remote Access Policy - Wireless Users.
  
    2.  In Utenti e computer di Active Directory individuare il gruppo di protezione **Remote Access Policy - Wireless Users** corrispondente al criterio di accesso remoto che controlla l'accesso alla rete WLAN.
  
    3.  Aggiungere l'utente al gruppo di protezione selezionato.
  
<!-- -->
  
-   **Per aggiungere computer al gruppo di protezione dei criteri di accesso remoto**
  
    1.  Accedere a un computer amministrativo come amministratore di dominio o come utente con autorizzazione di protezione a modificare l'appartenenza del gruppo di protezione Remote Access Policy - Wireless Computers.
  
    2.  In Utenti e computer di Active Directory individuare il gruppo di protezione **Remote Access Policy - Wireless Computers** corrispondente al criterio di accesso remoto che controlla l'accesso alla rete WLAN.
  
    3.  Aggiungere il computer al gruppo di protezione selezionato.
  
#### Monitoraggio e controllo dei servizi
  
Il monitoraggio dei servizi consente al personale operativo di osservare la condizione di un servizio IT in tempo reale.
  
Nei punti di questa sezione in cui si fa riferimento a MOM si presume che la distribuzione di MOM segua le indicazioni della *Guida operativa a MOM*.
  
Tuttavia, MOM non è necessario; è utilizzato semplicemente a scopo illustrativo. Per informazioni sulla *Guida operativa a MOM*, consultare la sezione "[Ulteriori informazioni](#xsltsection132121120120)" alla fine di questo modulo.
  
##### Classificazione degli avvisi di monitoraggio
  
Il sistema di monitoraggio dovrebbe segnalare solo gli avvisi più significativi al personale operativo. Se tutti gli errori secondari vengono passati al livello superiore per produrre avvisi di emergenze, il personale operativo farà confusione tra gli avvisi che sono urgenti e quelli che non lo sono ma che richiedono un'indagine a più lungo termine.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Attività di configurazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>- Esistenza di un processo di pianificazione della capacità nell'organizzazione<br />
- Strumenti di analisi per supportare il processo</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console avvisi operativi (ad esempio MOM)</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
In questo documento vengono utilizzate le seguenti categorie di avvisi. Di queste, solo le prime tre producono avvisi sulla console dell'operatore. A queste categorie verrà fatto riferimento nelle descrizioni delle attività successive.
  
**Tabella 8. Categorie di avvisi**

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
<td style="border:1px solid black;"><p>Avviso</p></td>
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

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>- Infrastruttura</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>- Attività di configurazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Autorizzazione necessaria come indicato dalla soluzione di monitoraggio</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Output alla funzione SMF della Gestione della capacità</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Performance Monitor<br />
- Consolidatore dei contatori delle prestazioni (ad esempio MOM)<br />
- Console avvisi operativi (ad esempio MOM)<br />
- Strumenti di pianificazione della capacità</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

I seguenti contatori delle prestazioni sono i più utili per l'identificazione dei vincoli di capacità in IAS. Il processore e il disco sono le due risorse utilizzate in modo più intensivo da IAS, pertanto è probabile che indicheranno dei vincoli prima della rete o della memoria.

**Tabella 9. Elementi per i quali monitorare i vincoli di capacità IAS**

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
<th><p>Istanza</p></th>
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
<td style="border:1px solid black;"><p>D: (IAS - DATA)</p></td>
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
  
Per ulteriori informazioni generali sui vincoli di capacità e sui relativi contatori delle prestazioni, consultare l'articolo Q146005 della Microsoft Knowledge Base, "Optimizing Windows NT for Performance," all'indirizzo <http://support.microsoft.com/default.aspx?scid=146005> (in inglese).
  
È anche importante monitorare gli indicatori di capacità delle infrastrutture di supporto. Gli elementi chiave sono:
  
-   Comunicazioni tra IAS e Active Directory. IAS utilizza ampiamente Active Directory per l'autenticazione e per alcuni servizi di autorizzazione.
  
-   I client RADIUS, ad esempio il punto di accesso senza fili, comunicano con i client e con IAS mediante i protocolli EAP (Extensible Authentication Protocol) e RADIUS.
  
-   Comunicazioni correlate ai client verso Active Directory. I client della rete LAN senza fili utilizzano i controller di dominio Active Directory per l'autenticazione mediante Criteri di gruppo e per quella tramite il dominio nativo.
  
#### Gestione dell'archiviazione
  
La gestione dell'archiviazione si occupa dell'archiviazione dei dati sia interna che esterna per il ripristino dei dati e l'archiviazione cronologica. Il team di gestione dell'archiviazione dovrà garantire la protezione fisica dei backup e degli archivi. Obiettivo della gestione dell'archiviazione è definire, tenere traccia e mantenere dati e risorse di dati nell'ambiente di produzione IT.
  
##### Configurazione dell'esportazione della configurazione IAS
  
Scopo di questa attività è pianificare un'attività notturna che esporti lo stato di configurazione parziale IAS per semplificare il ripristino di un sistema dopo un errore irreversibile. Lo stato di configurazione IAS completo include la configurazione dei client RADIUS che rappresenta informazioni potenzialmente riservate da proteggere. Pertanto, le istruzioni dettagliate per l'esportazione della parte dello stato di configurazione relativa ai client RADIUS sono fornite separatamente. Per eseguire il ripristino completo di ciascun server IAS alla piena produzione, saranno necessari entrambi i tipi di backup.
  
In un backup completo del server IAS sono incluse tutte le informazioni di configurazione del sistema operativo e tutte le altre informazioni di stato da cui dipende il server IAS. Questa attività è stata sviluppata in modo da consentire la reinstallazione di un server, la reinstallazione dei componenti facoltativi di IAS e il ripristino dello stato di configurazione. In questo modo il ripristino del servizio di un server che non si trova più in uno stato di configurazione noto (inaffidabile) o la cui protezione è compromessa si rivela più semplice.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Attività di configurazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Membro del gruppo di protezione Administrators locale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Presenza delle funzionalità o dei processi seguenti:<br />
- Backup dei dischi/file dei server aziendali<br />
- Percorsi di archiviazione protetti<br />
- Sistema di escalation e di monitoraggio degli avvisi (ad esempio MOM)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>- Script MSS<br />
- Servizio Utilità di pianificazione di Windows<br />
- SchTasks.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Questa attività consente di configurare un'attività pianificata con cui eseguire un backup notturno dello stato di configurazione del server IAS. Il backup di IAS presume l'esistenza di un sistema di backup dei server aziendali; l'output del backup di questa procedura sarà un file di backup che, a sua volta, può essere sottoposto a backup da parte del sistema di backup aziendale. Potrebbe trattarsi di un backup in rete oppure di un backup su periferica locale. La soluzione presume anche che il sistema di backup dei server aziendali esegua ogni notte il backup dei dischi del server IAS.

-   **Per configurare il backup della configurazione IAS**

    1.  Pianificare il processo di backup in modo che venga eseguito di notte mediante il seguente comando, mediante il quale il processo viene impostato per essere eseguito alle 02.00 di notte.

        SCHTASKS /Create /RU system /SC Daily /TN "IAS Backup" /TR C:\\MSSScripts\\IASExport.bat /ST 02:00

        **Nota:** il comando viene mostrato su due righe per motivi di stampa; immetterlo come riga singola.

    2.  Configurare il sistema di backup dei server aziendali in modo da eseguire il backup del contenuto della directory D:\\IASConfig ogni notte su supporti rimovibili. Se possibile, impostare uno script preliminare per verificare che la data e l'ora dei file di testo della configurazione IAS creati a partire dal file IASExport.bat non risalgano a oltre 24 ore prima. Se la data e l'indicatore orario dei file superano le 24 ore, il backup precedente non è riuscito oppure è ancora in esecuzione.

**Nota:** lo script IASExport.bat fornito può essere utilizzato come punto di partenza per questa attività. È necessario modificare la logica dello script IASExport.bat in modo che gli eventi di errore dello strumento **netsh** all'interno dello script generino eventi o notifiche che saranno rilevate dal personale operativo.

È opportuno considerare l'attivazione del controllo dei file di Windows nella directory D:\\IASConfig e indicare ai controllori della protezione dei server di verificare periodicamente l'eventuale presenza di attività insolite nei dati di controllo (accesso non riuscito, ad esempio). Le informazioni contenute nella directory D:\\IASConfig potrebbero consentire a un intruso di conoscere il modo di compromettere il controllo dell'accesso alla rete.

##### Esportazione della configurazione dei client RADIUS

Per assicurare la possibilità di ripristino in caso di errore irreversibile del server, è necessario esportare la configurazione dei client RADIUS dal server IAS. Le informazioni sui client RADIUS sono riservate e vanno protette, dal momento che contengono i segreti RADIUS univoci tra ciascun server e il relativo punto di accesso senza fili. Pertanto, le esportazioni dei client RADIUS vengono archiviate su supporti rimovibili che occorre sistemare in un luogo sicuro. Ogni backup di configurazione dei client RADIUS è univoco per ciascun server IAS.

Per consentire un ripristino completo dello stato di configurazione IAS, le configurazioni dei client RADIUS create mediante questa attività devono essere associate alla configurazione del sistema IAS creata utilizzando lo script IASClientExport.bat, illustrato dettagliatamente in un altro punto di questo modulo.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Attività di configurazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Membro del gruppo di protezione IAS Admins</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Presenza delle funzionalità o dei processi seguenti:<br />
- Backup dei dischi/file del server aziendale<br />
- Percorsi di archiviazione protetti</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>- Script MSS<br />
- Disco floppy o altri supporti rimovibili e scrivibili</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Le informazioni relative ai client RADIUS vengono esportate mediante il comando **netsh**. In questa soluzione è incluso un file batch mediante il quale le informazioni sui client RADIUS verranno esportate in un disco floppy o su altri supporti scrivibili e rimovibili.

-   **Per esportare la configurazione dei client RADIUS**

    1.  Dal prompt dei comandi del server IAS che sta esportando lo stato dei client RADIUS, eseguire il comando seguente:

        C:\\MSSScripts\\IASClientExport.bat

    2.  Esaminare la presenza di eventuali errori o avvisi rilevati e correggerli. Dopo aver risolto la situazione, eseguire nuovamente lo script.

    3.  Archiviare i supporti di backup in modo appropriato. I dati di questo backup sono riservati in quanto contengono segreti che potrebbero essere utilizzati per accedere alla rete WLAN dell'azienda. Per questo motivo occorre trasportarli e archiviarli con la stessa attenzione e protezione utilizzate per il server IAS. È opportuno archiviare i dati di backup in un luogo fisico diverso dal server IAS stesso. In questo modo sarà possibile ripristinare il server IAS nel caso in cui tutti i computer del sito venissero distrutti o diventassero inaccessibili.

##### Configurazione del backup delle directory di dati IAS

Scopo di questa attività è fornire indicazioni sulle directory del server IAS che richiedono il backup per assicurare un ripristino completo dello stato di configurazione IAS e dei dati del registro RADIUS dopo un errore irreversibile del server. In un backup completo del server IAS sono incluse tutte le informazioni di configurazione del sistema operativo e tutte le altre informazioni di stato da cui dipende il server IAS.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Attività di configurazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Membro del gruppo di protezione locale Backup Operators</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Presenza delle funzionalità o dei processi seguenti:<br />
- Backup dei dischi/file dei server aziendali<br />
- Percorsi di archiviazione protetti<br />
- Sistema di escalation e di monitoraggio degli avvisi (ad esempio MOM)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>- Backup di Windows o sistema di backup aziendale<br />
- Servizio Utilità di pianificazione di Windows<br />
- SchTasks.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

In questa attività vengono indicate dettagliatamente tutte le directory di cui eseguire il backup per assicurare il ripristino completo dello stato di configurazione IAS e dei dati dei file registro. L'attività presume la presenza di un sistema di backup dei server aziendali. Potrebbe trattarsi di un backup in rete oppure di un backup su periferica locale. La soluzione presume anche che il sistema di backup dei server aziendali venga eseguito di notte, dopo il backup dello stato di configurazione IAS (02.00), per eseguire il backup dei dischi del server IAS.

-   **Per configurare il backup delle directory di dati IAS**

    1.  Verificare che il backup dello stato di configurazione IAS sia pianificato correttamente e che venga eseguito con esito positivo. L'attività pianificata dello stato di configurazione IAS genera file dello stato della configurazione IAS sul disco rigido.

    2.  Utilizzare Blocco note per creare un file denominato backuptest.txt nella directory D:\\IASLogs. All'interno del file, digitare **Utilizzato per la verifica del backup e del ripristino**. Salvare il file e chiudere Blocco note. Questo file sarà utilizzato in seguito nelle procedure di verifica del ripristino.

    3.  Configurare il sistema di backup dei server aziendali in modo da eseguire un backup completo, incrementale o differenziale delle seguenti directory:

        -   D:\\IASConfig

        -   D:\\IASLogs

    4.  Visualizzare i file registro del sistema di backup dei server aziendali per assicurarsi che non si siano verificati errori o avvisi. In caso di rilevamento di errori o avvisi, prendere in considerazione l'esecuzione manuale degli script di esportazione della configurazione IAS e l'esecuzione di un altro backup completo di entrambe le directory.

    5.  Archiviare i supporti di backup in modo appropriato. I dati di questo backup sono riservati in quanto contengono la configurazione del software del server che consente di accedere alla rete WLAN dell'azienda. Per questo motivo occorre trasportarli e archiviarli con la stessa attenzione e protezione utilizzate per il server IAS. È opportuno archiviare i dati di backup in un luogo fisico diverso dal server IAS stesso. In questo modo sarà possibile ripristinare il server IAS nel caso in cui tutti i computer del sito venissero distrutti o diventassero inaccessibili.

##### Test del backup di IAS

Scopo di questa attività è verificare, mediante un ripristino di prova, che il processo e la tecnologia di backup funzionino correttamente. L'esecuzione di un ripristino completo dei backup su hardware server di riserva assicura con la massima affidabilità che le procedure di backup funzionino correttamente. Tuttavia, tale procedura è stata creata in modo da consentire ai clienti che non dispongono dell'accesso ad hardware server di riserva di collaudare le procedure di ripristino sull'hardware di produzione con un certo grado di rischio. Il test delle procedure di ripristino sui server di produzione implica il rischio che un ripristino parziale possa rendere il server inutilizzabile. Inoltre, assicura una buona conoscenza delle fasi di ripristino e l'assenza di errori di procedura o tecnici che potrebbero impedirne il completamento in caso di errore irreversibile del server.

I dati di ripristino del server IAS includono:

-   Dati di esportazione dello stato di configurazione IAS, che si trovano nella directory D:\\IASConfig. Se ripristinate da un nastro, queste informazioni vengono utilizzate per importare nuovamente la configurazione sul server IAS.

-   Dati di esportazione dei client RADIUS, che si trovano sul disco floppy o su altri supporti rimovibili scrivibili con l'etichetta "Client RADIUS per il server MSS - IAS - 01". "MSS - IAS - 01" sull'etichetta sarà sostituito con il nome del server IAS in uso. Queste informazioni sono utilizzate per il ripristino, sul server IAS, della configurazione dei client RADIUS.

-   Dati dei registri delle richieste RADIUS, che si trovano nella directory D:\\IASLogs. Se ripristinate da un nastro, queste informazioni contengono i dati cronologici utilizzati dai controllori della protezione IAS.

Prima di eseguire un ripristino di prova, è necessario esportare manualmente i dati di esportazione della configurazione IAS e i dati di esportazione dei client RADIUS. Successivamente eseguire un backup non pianificato dei dati del server e metterlo da parte per utilizzarlo solo in caso di problemi del ripristino di prova. In questo modo si riduce il rischio che nastri difettosi ed errori che potrebbero non essere notati durante i backup normali causino un ripristino parziale di un server di produzione.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>- Prima che il server IAS diventi operativo<br />
- Ogni mese<br />
- Collaudare nuovamente quando si apportano modifiche alla tecnologia o al processo di backup</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Privilegi di Local Administrators o di Backup Operators sul computer di prova</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Backup dei dischi/file dei server aziendali</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>- Backup di Windows o sistema di backup aziendale<br />
- Script MSS</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

In questa attività sono descritti dettagliatamente il ripristino e la verifica dei dati IAS. Saranno ripristinati tutti e tre i tipi di dati e utilizzate procedure speciali per la convalida del ripristino. Se non si esegue la verifica avanzata del ripristino, accertarsi di utilizzare un backup completo recente (quello della notte precedente) completato con esito positivo. Accertarsi anche che durante la verifica non siano state effettuate attività amministrative sul server di destinazione dall'ultimo backup.

Se questa attività viene eseguita per verificare il ripristino di un server dall'installazione iniziale di Windows Server 2003 al ripristino della configurazione IAS, è necessario eseguire i passaggi preliminari di creazione del server descritti nel modulo "[Implementazione dell'infrastruttura RADIUS per la protezione di reti LAN senza fili](http://technet.microsoft.com/it-it/library/dd536250)", per assicurare che l'hardware e il software del server siano configurati correttamente per IAS. L'ordine suggerito per il ripristino di un server a seguito di una reinstallazione è il seguente:

-   Installare e configurare il server seguendo le indicazioni fornite nel modulo "[Implementazione dell'infrastruttura RADIUS per la protezione di reti LAN senza fili](http://technet.microsoft.com/it-it/library/dd536250)" nella *Guida realizzativa*.

-   Eseguire il ripristino seguendo i passaggi indicati in questa attività.

**Nota:** è possibile che occorra selezionare nuovamente il certificato di autenticazione dei server RAS e IAS appena installato all'interno del criterio di accesso remoto per le reti WLAN ripristinato.

-   **Per verificare il backup di IAS**

**Nota:** il primo passaggio della procedura è facoltativo ed è utilizzato in un ambiente di laboratorio di prova su hardware server non di produzione. Tuttavia assicura il ripristino di un server con uno stato instabile o la cui protezione è compromessa.

1.  Per ripristinare un server che è diventato instabile o nel quale la protezione è stata violata, reinstallare Windows Server 2003 come indicato nel modulo "[Implementazione dell'infrastruttura RADIUS per la protezione di reti LAN senza fili](http://technet.microsoft.com/it-it/library/dd536250)" della *Guida realizzativa* e accertarsi di copiare gli script MSS dai supporti di distribuzione alla directory C:\\MSSScripts del server.

2.  Individuare la directory D:\\IASLogs e cercare il file bakuptest.txt. Se non esistono file, andare al passaggio successivo. Se si trova il file backuptest.txt, eliminarlo. Il file backuptest.txt è stato creato durante l'attività di configurazione del backup delle directory di dati IAS per simulare il ripristino di un file registro delle richieste RADIUS IAS per la convalida dei supporti e della procedura di backup. Se si preferisce, è possibile ripristinare i dati effettivi del registro delle richieste da D:\\IASLogs. Si noti tuttavia che la sovrascrittura dei dati del file registro potrebbe causare la perdita di dati in caso di ripristino parziale.

3.  Aprire lo snap-in MMC IAS, selezionare le proprietà dell'oggetto **Servizio di Autenticazione Internet (locale)** e controllare la scheda **Generale**. Aggiungere **(Test di ripristino)** al campo **Descrizione server**. Scegliere **OK** per chiudere la finestra di dialogo delle proprietà di IAS. La modifica della stringa di descrizione del server consente di verificare il ripristino delle impostazioni di configurazione IAS. Al termine del ripristino delle impostazioni di configurazione IAS, la stringa di descrizione del server non dovrà essere presente.

4.  Utilizzando lo snap-in MMC **IAS**, fare clic con il pulsante destro del mouse sulla cartella **Client RADIUS** e selezionare **Nuovo client RADIUS**. Immettere **Test di ripristino** come nome descrittivoe digitare **127.0.0.1** nel campo **Indirizzo client (IP o DNS)**. Immettere una password nei campi **Segreto condiviso** e **Conferma segreto condiviso** relativi a questo client RADIUS, quindi scegliere **Fine**. La creazione del nuovo client RADIUS viene utilizzata per il test dei supporti e della procedura di ripristino dei client RADIUS. Dopo il ripristino, il client RADIUS Test di ripristino non dovrebbe essere presente.

5.  Individuare i supporti di backup che si desidera verificare(ad esempio il backup della notte precedente) in base a una pianificazione e utilizzarli per il ripristino dei seguenti dati sul disco rigido del server:

    -   D:\\IASConfig\\\*.\*

    -   D:\\IASLogs\\BACKUPTEST.TXT

    **Avviso:** il ripristino parziale dell'intera cartella D:\\IASLogs in un server di produzione potrebbe sovrascrivere i dati di produzione dei file registro RADIUS.

6.  Dal prompt dei comandi, eseguire il comando riportato di seguito per ripristinare, nel database IAS, la configurazione IAS salvata in precedenza come file di testo. Accertarsi di controllare l'eventuale visualizzazione di errori o avvisi durante l'esecuzione dello script:

    **C:\\MSSScripts\\IASImport.bat**

    **Nota:** nei passaggi che seguono è previsto l'utilizzo di un disco floppy o di altri supporti rimovibili e scrivibili con l'etichetta "Client RADIUS per server MSS - IAS - 01", creato nel passaggio precedente. Sostituire, nell'etichetta, "MSS - IAS - 01" con il nome del server IAS in uso. Accertarsi di utilizzare il disco corretto con il server appropriato per evitare la perdita di dati.

7.  Individuare il disco floppy (o gli altri supporti rimovibili e scrivibili) di configurazione dei client RADIUS per questo server, e inserirli nell'unità del server. Dal prompt dei comandi, eseguire il comando riportato di seguito. Accertarsi di controllare l'eventuale visualizzazione di errori o avvisi durante l'esecuzione dello script:

    **C:\\MSSScripts\\IASClientImport.bat**

8.  Chiudere e riaprire lo snap-in MMC **IAS**, selezionare le proprietà dell'oggetto **Servizio Autenticazione Internet (locale)** e controllare la scheda **Generale** per accertarsi che il testo **(Test di ripristino)** non sia più visualizzato nel campo **Descrizione server**. Scegliere **OK** per chiudere la finestra di dialogo delle proprietà di IAS.

9.  Selezionare la cartella **Client RADIUS** e accertarsi che il client RADIUS **Test di ripristino** non sia più visualizzato nel campo a destra.

10. Nella parte restante della configurazione all'interno dello snap-in MMC **IAS** dovranno essere visualizzate le impostazioni precedenti il backup utilizzato durante la verifica.

11. Individuare la directory D:\\IASLogs e accertarsi della presenza del file backuptest.txt. Se i passaggi di questa procedura erano relativi a un server di produzione, fare in modo che un controllore della protezione IAS controlli i file registro per assicurare che siano intatti e che siano aggiornati almeno al momento in cui è stato eseguito il backup.

12. È opportuno mettere nuovamente i supporti di backup e il disco floppy in un archivio protetto.

#### Amministrazione della protezione

L'amministrazione della protezione è responsabile del mantenimento di un ambiente informatico protetto. La protezione è una parte importante dell'infrastruttura di un'organizzazione di grandi dimensioni. In un sistema informatico con una protezione debole è probabile che si verifichino violazioni della protezione.

##### Accesso ai registri delle richieste RADIUS IAS

Il server IAS è in grado di registrare, a scelta, diversi eventi derivanti dalle richieste RADIUS dei punti di accesso senza fili nei registri delle richieste RADIUS che si trovano sul disco rigido del server. I registri RADIUS sono utili per un gran numero di motivi, tra cui l'identificazione di eventuali attacchi al sistema e di accesso non autorizzato alla rete aziendale. Sebbene la discussione dettagliata dell'analisi dei registri delle richieste RADIUS non rientri nell'ambito di questa guida, in questa attività saranno illustrati i metodi per controllare i registri delle richieste RADIUS.

Per analizzare i registri delle richieste RADIUS archiviati come testo in formato IAS oppure nel formato di importazione per database, possono essere utilizzati diversi metodi. In questa soluzione è stato scelto il formato di importazione per database, in quanto l'importazione di questo tipo di file in applicazioni che riconoscono il testo delimitato da virgole è relativamente semplice. Tra i metodi per l'analisi dei registri delle richieste RADIUS IAS sono inclusi i seguenti:

**Individuazione diretta dei file registro mediante l'utilità IASPARSE** dagli strumenti di supporto di Windows Server 2003. Questo strumento in genere viene installato ed eseguito sul server IAS stesso, per cui è necessaria una sessione remota di Telnet o di Servizi terminal. Per impostazione predefinita questa soluzione non è configurata per supportare questo metodo di visualizzazione dei file registro.

**Importazione dei file registro in Microsoft Access 2002 da un computer di amministrazione remoto**. Questo metodo consente a un amministratore di importare i registri in una tabella di Microsoft Access per query occasionali o nell'ambito di uno schema più ampio di reporting e archiviazione. Si tratta del metodo scelto in questa soluzione per la visualizzazione dei file registro. È opportuno che le organizzazioni di grandi dimensioni prendano in considerazione la registrazione basata su Microsoft SQL Server™ 2000 descritta di seguito.

**Accesso alle informazioni dei registri tramite un cluster centrale di SQL Server 2000** di cui sono stati replicati i dati sul server IAS mediante la registrazione basata su MSDE 2000. Sebbene la configurazione di questo scenario sia piuttosto complessa, è stato pubblicato un white paper con relativo codice per supportare questo processo. Per assistenza durante il processo di configurazione di questo tipo di registrazione SQL, consultare il partner Microsoft di riferimento oppure contattare l'addetto ai clienti Microsoft che è in grado di mettere l'utente in contatto con il partner appropriato oppure con il personale dei Servizi di consulenza Microsoft.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni giorno oppure ogni settimana, a seconda dei requisiti di protezione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Membro del gruppo di protezione IAS Security Auditors</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Archiviazione su disco per l'archiviazione temporanea dei registri delle richieste RADIUS</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>IASPARSE<br />
Microsoft Access<br />
Microsoft Excel</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

I registri delle richieste RADIUS vengono generati su ciascun server di questa soluzione e archiviati in un volume disco dedicato ai file registro. I passaggi da compiere per accedere a questi file registro includono la creazione di una connessione di rete a ciascun server IAS, nonché l'analisi e l'eliminazione dei file registro non più necessari. I server IAS di questa soluzione sono configurati per la creazione di un nuovo file registro delle richieste RADIUS ogni mese. Gli amministratori IAS possono modificare questo intervallo e adattarlo alle proprie esigenze specifiche.

La tabella creata con Access verrà formattata in base al tipo di dati contenuti in ciascun campo. Sebbene in questo esempio vengano illustrate le modalità di creazione di una nuova tabella, è anche possibile importare un registro in una tabella esistente.

-   **Per importare i file registro delle richieste RADIUS in Microsoft Access**

    1.  Accedere a una workstation di amministrazione come membro del gruppo di protezione IAS Security Auditors di Active Directory ed eseguire la connessione di un'unità a un server da analizzare mediante il seguente comando digitato dal prompt dei comandi. Accertarsi di sostituire MSS - IAS - 01 con il nome del server IAS in uso:

        **NET USE X: \\\\MSS - IAS - 01\\IASLogs**

    2.  Individuare il file registro che rappresenta il mese che si desidera esaminare utilizzando il nome del file registro, la data e l'indicatore orario. Il nome del file registro conterrà un formato di denominazione che indica la data di creazione del file. Creare una copia del database che si desidera importare e aggiungere l'estensione **.**txt.

    3.  Prima di creare la tabella, aggiungere all'inizio del file registro creato da IAS le due righe complete fornite nel file di testo "C:\\MSSScripts\\IASAccessPrep.txt". La prima riga contiene i nomi degli attributi di ciascun campo del registro, utilizzati da Access per creare i nomi dei campi della tabella. L'utilizzo di questi nomi rende più semplice l'interpretazione delle voci del registro. La seconda riga viene utilizzata da Access per configurare il tipo di dati appropriato a ciascuna colonna della tabella. Dopo aver importato il file registro, è necessario eliminare queste voci dalla tabella di Access.

    4.  In Access 2002 scegliere **Database vuoto**. In **Salva nuovo database** specificare un nome file, quindi scegliere **Crea una tabella mediante l'immissione di dati**. Scegliere **File**, quindi **Carica dati esterni** e poi **Importa**.

    5.  Scegliere **Importa**, **Tipo file**, quindi **File di testo**, individuare il file registro IAS, selezionarlo e scegliere **Importa**. In **Importazione guidata testo** scegliere **Avanzate**.

    6.  Scegliere **Specifica di importazione**:

    7.  In **Formato file** scegliere **Delimitato**.

    8.  In **Delimitatore di campo** scegliere **,** (virgola).

    9.  In **Qualificatore testo** scegliere " (virgolette).

    10. Nei campi **Date, Ore e Numeri** selezionare **Formato anno esteso** e **Date con zero iniziale**, quindi digitare il **Formato data** (ad esempio MGA), il **Separatore data** (ad esempio **/** o **barra**), il **Separatore ora** (ad esempio **:** o due punti) e il **Separatore decimale** (ad esempio **,** o virgola) appropriati.

    11. Nella finestra di dialogo **Importazione guidata testo** scegliere **Avanti**, selezionare **Nomi di campo nella prima riga**, quindi scegliere **Avanti**. Scegliere **Tabella nuova**, quindi **Avanti**.

    12. Lasciare le impostazioni predefinite in **Opzioni per i campi**, quindi scegliere **Avanti**. Scegliere **Chiave primaria aggiunta automaticamente**, quindi **Avanti**. In **Importa nella tabella** digitare il nome della nuova tabella. Scegliere **Fine**.

    13. Nella finestra di dialogo **Nome file:Database** selezionare il nome del database in uso, quindi scegliere **Apri** per visualizzare la tabella.

##### Verifica delle voci del Registro eventi di autenticazione RADIUS IAS

I controllori della protezione possono utilizzare quest'attività periodicamente per controllare i tentativi di accesso non autorizzato alla rete senza fili. È possibile che i criteri di protezione interni impongano di verificare periodicamente gli eventi di autenticazione RADIUS nel Registro eventi per rilevare i tentativi di autenticazione oppure l'utilizzo di credenziali di certificati rubati.

Questa attività è facoltativa ed è segnalata solo per le piccole organizzazioni che dispongono di personale IT ridotto e che hanno scelto di disattivare gli eventi IAS di riuscita e rifiuto nei registri eventi di sistema. L'attività richiede l'appartenenza al gruppo IAS Admins oppure l'appartenenza diretta al gruppo Administrators locale. Le attività destinate a questa soluzione consentono ai controllori della protezione IAS di leggere gli eventi di autenticazione sulla condivisione IASLogs senza richiedere l'accesso al server con privilegi di amministratore completi.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni giorno oppure ogni settimana, a seconda dei requisiti di protezione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Appartenenza al gruppo IAS Admins o al gruppo Administrators locale/incorporato</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Questa attività è facoltativa e dipende dal privilegio di amministratore locale per il ruolo di controllore della protezione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>Visualizzatore eventi o, a scelta, EventCombMT incluso in Windows Server 2003 Resource Kit</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
Questa attività viene segnalata per gli ambienti di piccole dimensioni in cui i controllori della protezione IAS si occupano anche dell'amministrazione del sistema IAS. Questa soluzione è configurata per impostazione predefinita in modo da non fornire privilegi di amministratore locale ai controllori della protezione. Pertanto, prima di cominciare ad eseguirla, è necessario aggiungere il controllore al gruppo di protezione IAS Admins di Active Directory.
  
-   **Per controllare la presenza di tentativi di autenticazione non riusciti nel Registro eventi**
  
    1.  Accedere a uno dei server IAS come membro del gruppo di protezione Internet Authentication Service Administrators.
  
    2.  Aprire il Visualizzatore eventi facendo clic sul pulsante **Start**, scegliendo **Tutti i programmi** e quindi **Strumenti di amministrazione**.
  
    3.  Scegliere **Registro eventi sistema**.
  
    4.  Dal menu **Visualizza** scegliere **Filtro**.
  
    5.  Selezionare **IAS** come **Origine evento** e **2** come **ID evento**.
  
    6.  Esaminare tutti gli eventuali errori di autenticazione frequenti.
  
##### Archiviazione ed eliminazione dei file registro RADIUS IAS
  
I controllori della protezione IAS dovranno archiviare ed eliminare periodicamente i file registro delle richieste IAS RADIUS per assicurare che lo spazio su disco del server IAS non si esaurisca causando l'interruzione del servizio per le richieste di autenticazione e accounting provenienti dai punti di accesso senza fili. Si tratta di un processo manuale, a meno di non ricorrere alla creazione di uno script per la soluzione o utilizzare la strategia di replica automatica SQL Server 2000 descritta nell'attività "Accesso ai registri delle richieste RADIUS IAS" presentata in questo modulo.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni mese</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Appartenenza al gruppo di protezione IAS Security Auditors di Active Directory</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Supporti rimovibili per memorizzare i file registro RADIUS archiviati</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>Comandi nativi di Windows</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
I registri delle richieste di autenticazione e accounting RADIUS non contengono informazioni sulla protezione particolarmente riservate. Pertanto esiste un gran numero di metodi di archiviazione e di eliminazione. Ad esempio, uno script di backup basato su server è in grado di informare i controllori della protezione IAS, mediante un messaggio di posta elettronica, del completamento del backup dei file registro. I controllori della protezione possono quindi collegarsi al server IAS ed eliminare i file registro meno recenti che non sono necessari.
  
Un controllore della protezione IAS è in grado di eseguire il backup dei file registro RADIUS su un'unità nastro o CD-RW collegata al proprio computer di amministrazione. I controllori possono quindi collegarsi al server IAS ed eliminare i file registro meno recenti che non sono necessari. Il server IAS di questa soluzione è configurato per la creazione di un nuovo file registro ogni mese, pertanto occorre scegliere una strategia che consenta di mantenere in linea una quantità di dati sufficiente a ricostruire le informazioni di accesso alla rete per i diversi scenari. Ad esempio, se si dispone di dati in linea relativi a tre mesi in tre file registro diversi, potrebbero essere necessari gli ultimi due file registro per ricostruire le informazioni di accesso alla rete e tenere traccia degli eventi di protezione o rieseguire i conti. Pertanto, è opportuno archiviare ed eliminare il meno recente dei tre file registro e lasciare i due più recenti.
  
Per maggiori informazioni sul backup dei registri delle richieste RADIUS e di altri dati IAS, vedere l'attività "Configurazione del backup delle directory di dati IAS" illustrata dettagliatamente in questo modulo. In questa attività sono fornite le indicazioni per l'archiviazione e l'eliminazione di registri RADIUS da una workstation amministrativa.
  
-   **Per archiviare ed eliminare i file registro delle richieste RADIUS**
  
    1.  Accedere a una workstation amministrativa come membro del gruppo di protezione IAS Security Auditors.
  
    2.  Mappare un'unità al server IAS in cui si eseguiranno l'archiviazione e l'eliminazione dei file di registro digitando il seguente comando al prompt dei comandi. Accertarsi di sostituire "MSS - IAS - 01" con il nome del server IAS in uso:
  
        **NET USE X: \\\\MSS - IAS - 01\\IASLogs**
  
    3.  Identificare i file registro meno recenti sul server IAS, che saranno archiviati ed eliminati dal server. Utilizzare NTBACKUP, il comando **copy** o un'altra utilità per archiviare i file registro selezionati dalla condivisione in linea ai supporti secondari.
  
    4.  Utilizzare il comando **del** per eliminare i file registro dalla condivisione in linea.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di supporto
  
Le funzioni SMF di questa fase supportano questo obiettivo assicurando l'utilizzo di funzionalità reattive e preventive nella gestione dei livelli di servizio. Le funzioni reattive dipendono dalla capacità dell'organizzazione di reagire e risolvere rapidamente le emergenze e i problemi. Le funzionalità più auspicabili, quelle preventive, cercano di evitare interruzioni dei servizi mediante l'identificazione e la risoluzione dei problemi prima che si verifichino ripercussioni sui livelli di servizio. Tale obiettivo viene raggiunto attraverso un buon monitoraggio della soluzione di servizi, a fronte di soglie predefinite e dando al personale operativo il tempo di reagire a eventuali problemi prima che si manifestino con interruzioni dei servizi.
  
In questa sezione vengono fornite le informazioni relative alle seguenti funzioni SMF:
  
-   Gestione delle emergenze
  
Non esistono attività per le restanti funzioni SMF:
  
-   Gestione dei problemi
  
-   Servizio di assistenza
  
#### Gestione delle emergenze
  
La gestione delle emergenze è il processo che consente di gestire e controllare errori e interruzioni nell'utilizzo o nell'implementazione dei servizi IT riferiti dai clienti o dai partner IT. L'obiettivo principale della gestione delle emergenze è ripristinare il normale funzionamento del servizio nel modo più rapido possibile e ridurre al minimo le ripercussioni negative sull'attività aziendale, assicurando il mantenimento della migliore qualità e disponibilità dei livelli di servizio. Con l'espressione normale funzionamento del servizio si intende un funzionamento entro i limiti del contratto del livello di servizio (SLA, Service Level Agreement).
  
**Nota:** per la risoluzione generale dei problemi dei client senza fili Windows XP, consultare l'articolo Q313242 della Knowledge Base, "How to Troubleshoot Wireless Network Connections in Windows XP," all'indirizzo <http://support.microsoft.com/default.aspx?scid=313242> (in inglese).
  
##### Verifica dello stato della cartella Connessioni di rete dei client
  
La cartella Connessioni di rete e le icone di notifica di Windows XP forniscono informazioni sullo stato dell'autenticazione. Questa attività consente all'utente finale o ai membri del personale del servizio di assistenza di verificare lo stato della connessione senza fili sul computer client. Se un'autenticazione richiede informazioni aggiuntive da parte dell'utente, ad esempio la scelta di uno o più certificati utente, viene visualizzato un promemoria con le istruzioni per l'utente. Questa attività viene utilizzata durante la risoluzione dei problemi.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Supporto</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Durante la risoluzione dei problemi di un utente</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Appartenenza al gruppo di protezione Administrators locale per apportare modifiche alle impostazioni della rete WLAN</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Potrebbe richiedere la connessione LAN per l'assistenza remota durante la risoluzione dei problemi</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>Windows XP Professional</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
Lo stato dell'autenticazione è descritto nel testo sotto il nome della connessione corrispondente alla scheda di rete senza fili, all'interno della cartella Connessioni di rete.
  
Una volta visualizzato lo stato della connessione, è anche possibile visualizzare l'intensità del segnale nella scheda **Generale** e la configurazione dell'indirizzo IP nella scheda **Supporto**. Se la scheda senza fili dispone di un indirizzo APIPA (Automatic Private IP Addressing), ad esempio 169.254.0.0/16, o se è configurata con l'indirizzo IP alternativo, l'autenticazione non è riuscita e il client senza fili Windows XP è ancora associato al punto di accesso senza fili. In questo caso viene attivata la scheda senza fili e il protocollo TCP/IP esegue il processo di configurazione normale. Se non viene rilevato un server DHCP, viene configurato automaticamente un indirizzo APIPA o un indirizzo alternativo.
  
-   **Per verificare lo stato della cartella Connessioni di rete**
  
    1.  Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **ncpa.cpl**, quindi scegliere **OK**.
  
##### Attivazione e disattivazione dell'analisi sui computer client
  
Windows supporta informazioni di analisi dettagliate per agevolare il personale del servizio di assistenza e gli sviluppatori nella risoluzione dei problemi dei componenti software. L'analisi fornisce un livello di dettaglio superiore a quello dei Registri eventi e archivia queste informazioni in file registro di testo.
  
Per ottenere informazioni dettagliate sul processo di autenticazione EAP, occorre attivare l'analisi di EAP sui componenti LAN (EAPOL) e RATLS (Remote Access Service - Transport Layer Security).

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Supporto</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Se necessario, durante la risoluzione dei problemi di rete WLAN di un client</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Appartenenza al gruppo di protezione Administrators locale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Potrebbe richiedere la connessione LAN per l'assistenza remota durante la risoluzione dei problemi</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>- Windows XP Professional<br />
- Notepad.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Una volta emessi i comandi riportati di seguito, tentare nuovamente il processo di autenticazione e visualizzare i file Eapol.log e Rastls.log della cartella %SystemRoot%\\Tracing.

-   **Per attivare l'analisi sui computer client**

    1.  Eseguire i comandi seguenti:

        -   **netsh ras set tracing eapol enabled**

        -   **netsh ras set tracing rastls enabled**

<!-- -->

-   **Per disattivare l'analisi sui computer client**

    1.  Eseguire i comandi seguenti:

        -   **netsh ras set tracing eapol disabled**

        -   **netsh ras set tracing rastls disabled**

**Nota:** l'analisi richiede una grande quantità di risorse del sistema e crea file registro che aumentano di dimensioni nel corso del tempo. Accertarsi di disattivare l'analisi nuovamente una volta completata la risoluzione dei problemi.

##### Verifica della stringa del nome di dominio sui computer client

Durante l'autenticazione reciproca EAP - TLSI i computer client non possono eseguire il controllo dei certificati revocati, in quanto i percorsi degli elenchi CRL (Certificate Revocation List) in genere non sono accessibili se prima non si è ottenuto l'accesso. Pertanto, i client Windows sono in grado di convalidare tutto o parte del nome del server nel certificato presentato dal server IAS.

L'autenticazione non riesce se il client senza fili sta effettuando la convalida del certificato del server (attivata per impostazione predefinita) ed è stato immesso un valore errato per il dominio del server IAS nel campo che indica di eseguire la connessione qualora il nome del server termini con un determinato elemento. Se si è scelto di attivare l'opzione **Connetti ai server seguenti**, è necessario eseguire questa attività durante la risoluzione dei problemi di autenticazione dei client. Questa soluzione non attiva l'impostazione appena descritta in quanto può visualizzare finestre di dialogo WLAN agli utenti finali. Windows XP Professional SP1 è configurato con questa opzione disattivata per impostazione predefinita.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Supporto</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Configurazione oppure durante la risoluzione dei problemi WLAN degli utenti</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Appartenenza al gruppo di protezione Administrators locale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Conoscenza del percorso di dominio di IAS</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>Windows XP Professional</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
Verificare l'esattezza di questa stringa aprendo la finestra di dialogo **Proprietà** della connessione di rete corrispondente alla scheda di rete WLAN. Visualizzare l'impostazione selezionando le proprietà del tipo EAP **Smart Card and Other Certificate** nella scheda **Authentication**.
  
-   **Per verificare la stringa del nome di dominio sui computer client**
  
    1.  Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **ncpa.cpl**, quindi scegliere **OK**.
  
    2.  Visualizzare le proprietà della connessione di rete senza fili.
  
    3.  Nella scheda **Reti senza fili** selezionare l'identificatore SSID (Service Set Identifier) della rete di destinazione dalle reti preferite e visualizzarne le proprietà.
  
    4.  Nella scheda **Authentication** visualizzare le proprietà e assicurarsi che la stringa del campo **Connect if the server name ends with** sia uguale al nome di dominio dei server IAS.
  
##### Visualizzazione degli eventi di autenticazione IAS nel Registro eventi
  
La riuscita e la mancata riuscita dell'autenticazione client vengono registrate, per impostazione predefinita, nel Registro eventi di sistema e possono dimostrarsi utili nella risoluzione dei problemi. La registrazione degli eventi è attivata per tutti i tipi di eventi IAS (eventi di rifiuto, di eliminazione o eventi riusciti) per impostazione predefinita nella scheda **Servizio** delle proprietà del server IAS nello snap-in IAS.
  
Questa attività consente agli amministratori IAS di agevolare il personale del servizio di assistenza nella risoluzione dei problemi di autenticazione di computer e utenti visualizzando gli eventi di autenticazione inclusi nei Registri eventi del server IAS.
  
È opportuno notare che se il personale del servizio di assistenza IT richiede l'accesso alle informazioni di autenticazione dei client senza fili incluse nei Registri eventi di sistema IAS, esistono diverse opzioni da considerare:
  
-   Prevedere il supporto di un amministratore IAS, membro del gruppo di protezione IAS Admins e quindi dotato dell'accesso ai messaggi dei Registri eventi di sistema IAS. In questa attività sono forniti i dettagli relativi a questa opzione.
  
-   Utilizzare un sistema di gestione dei Registri eventi dell'organizzazione di grandi dimensioni, ad esempio MOM, per esportare i registri in un percorso accessibile al personale del servizio di assistenza.
  
-   Assegnare al personale del servizio di assistenza l'autorizzazione in lettura per la condivisione IASLogs e per la relativa directory NTFS D:\\IASLogs. Indicare al personale del servizio di assistenza le modalità di individuazione dei file registro mediante strumenti come IASPARSE, descritto nell'attività "Accesso ai registri delle richieste RADIUS IAS" di questo modulo. La maggior parte dei clienti probabilmente prenderà in considerazione questa opzione, in quanto richiede l'infrastruttura minima e non espone a rischi di protezione eccessivi.
  
L'assegnazione a utenti senza privilegi di amministrazione dell'accesso non necessario ai Registri eventi di sistema pone rischi di protezione e pertanto dovrebbe essere evitato, se possibile. Ciò è vero in particolare per i server che combinano ruoli di server IAS e ruoli di server di controller di dominio.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Supporto</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Durante la risoluzione dei problemi di autenticazione dei client</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Appartenenza al gruppo di protezione IAS Administrators locale oppure a un gruppo che dispone dell'accesso in lettura/salvataggio al Registro eventi di sistema</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Approvazione da parte degli amministratori del servizio directory e del personale della protezione per l'appartenenza al gruppo di protezione appropriato</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>Snap-in MMC Visualizzatore eventi o EventCombMT incluso in Windows Server 2003 Resource Kit</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
La visualizzazione dei tentativi di autenticazione in questo registro è utile per risolvere i problemi relativi ai tentativi di autenticazione rifiutati da IAS. Se sono configurati più criteri di accesso remoto, è possibile utilizzare il Registro eventi di sistema per determinare il nome del criterio di accesso remoto che ha accettato o rifiutato il tentativo di connessione (vedere Criterio - Nome nella descrizione dell'evento). Inoltre, l'evento di autenticazione (Source: IAS, Event ID 1 for accept and 2 for reject) segnala i codici motivo che dispongono di descrizioni corrispondenti e sono menzionati in *Guida in linea e supporto tecnico per Windows Server 2003*.
  
L'attivazione della registrazione degli eventi IAS e la lettura del testo degli eventi di autenticazione IAS nel Registro eventi di sistema sono lo strumento più utile nella risoluzione dei problemi di autenticazione IAS non riuscita.
  
-   **Per visualizzare gli eventi di autenticazione del Registro eventi di sistema**
  
    1.  Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **Eventvwr**, quindi scegliere **OK**.
  
    2.  Selezionare **Registro eventi sistema**.
  
    3.  Dal menu **Visualizza** scegliere **Filtro**, **IAS** come **Origine evento** quindi fare clic su **OK**.
  
##### Attivazione e disattivazione dell'analisi sul server IAS
  
Windows supporta informazioni di analisi dettagliate per agevolare il personale del servizio di assistenza e gli sviluppatori nella risoluzione dei problemi dei componenti software. L'analisi fornisce un livello di dettaglio superiore a quello dei Registri eventi e archivia queste informazioni in file registro di testo.
  
Windows Server 2003 dispone di una funzionalità di analisi estesa che può essere utilizzata per la risoluzione di problemi complessi relativi a componenti specifici. In Windows Server 2003 è possibile consentire ai componenti di registrare le informazioni di analisi all'interno di file utilizzando il comando **netsh**.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Supporto</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Se necessario, durante la risoluzione dei problemi di connessione alla rete WLAN dei client</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Appartenenza al gruppo di protezione Administrators locale del server IAS</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>È necessaria la generazione di traffico di rete durante la risoluzione dei problemi</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>Comando <strong>netsh</strong> Blocco note</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
Per attivare e disattivare l'analisi per componenti specifici, è possibile utilizzare il comando **netsh**. Di seguito sono elencati i componenti per i quali è più utile attivare l'analisi dei problemi di autenticazione 802.1X basata su EAP - TLS:
  
-   IASSAM (il file Iassam.log della cartella *SystemRoot*\\tracing) — Si tratta del file di analisi dei problemi IAS utilizzato più comunemente, in quanto descrive le funzioni relative alla violazione dei nomi utente, al collegamento a un controller di dominio, alla verifica delle credenziali e così via. È il più importante dei file di analisi IAS e in genere è richiesto per il debug di tutti i problemi di autenticazione.
  
-   RASTLS (il file Rastls.log della cartella *SystemRoot*\\tracing) — Per tutte le autenticazioni relative a EAP e PEAP (Protected EAP), questo registro contiene le informazioni di debug più importanti; tuttavia è di difficile lettura. Microsoft si sta attivando per produrre informazioni che potrebbero semplificarne l'interpretazione.
  
Le informazioni di analisi riportate di seguito per IAS di solito non sono necessarie nella risoluzione dei problemi di autenticazione 802.1X con EAP - TLS; tuttavia potrebbero rivelarsi utili nella risoluzione dei problemi di altre attività:
  
-   IASRAD (il file Iasrad.log della cartella *SystemRoot*\\tracing) — Descrive tutte le operazioni relative al protocollo RADIUS. Il file descrive le porte del server che sono in attesa e così via. È utilizzato raramente nel debug dei problemi del server IAS.
  
-   IASSDO (il file Iassdo.log della cartella *SystemRoot*\\tracing) — Il registro IASSDO si occupa delle transazioni dall'interfaccia utente ai file MDB che contengono la configurazione e il dizionario del server. Si tratta del registro utilizzato per il debug di tutti i problemi relativi ai servizi o all'interfaccia utente.
  
<!-- -->
  
-   **Per attivare l'analisi sul server IAS**
  
    1.  Eseguire i seguenti comandi **netsh** che corrispondono alla informazioni di analisi richieste. Nella risoluzione dei problemi EAP - TLS con l'autenticazione 802.1X, si consiglia l'utilizzo dei registri IASSAM e RASTLS:
  
    2.  I comandi **netsh** corrispondenti sono:
  
        -   **netsh ras set tracing iassam enabled**
  
        -   **netsh ras set tracing rastls enabled**
  
        -   **netsh ras set tracing iasrad enabled**
  
        -   **netsh ras set tracing iassdo enabled**
  
<!-- -->
  
-   **Per disattivare l'analisi sul server IAS**
  
    1.  Eseguire i seguenti comandi **netsh** che corrispondono alla informazioni di analisi che si desidera disattivare.
  
    2.  I comandi **netsh** corrispondenti sono:
  
        -   **netsh ras set tracing iassam disabled**
  
        -   **netsh ras set tracing rastls disabled**
  
        -   **netsh ras set tracing iasrad disabled**
  
        -   **netsh ras set tracing iassdo disabled**
  
**Nota:** l'analisi richiede una notevole quantità di risorse del sistema, per cui è opportuno utilizzarla con parsimonia per agevolare l'identificazione dei problemi di rete. Una volta acquisita l'analisi o identificato il problema, è opportuno disattivare subito l'analisi.
  
##### Attivazione della registrazione SChannel sul server IAS
  
SChannel (Secure Channel) è un provider SSP (Security Support Provider) che supporta una serie di protocolli di protezione Internet, ad esempio SSL e TLS.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Responsabile del cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Supporto</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Se necessario, durante la risoluzione dei problemi di connessione client sul server IAS</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Appartenenza al gruppo di protezione Administrators locale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Capacità di carico sul server sufficiente a sostenere la registrazione aggiuntiva<br />
Requisiti di spazio su disco inferiori sul volume del sistema operativo</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Tecnologia richiesta:</p></td>
<td style="border:1px solid black;"><p>REGEDIT<br />
Blocco note</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

La registrazione degli errori di convalida dei certificati dei client è un evento SChannel e non è attiva sul server IAS per impostazione predefinita.

-   **Attivazione della registrazione SChannel sul server IAS**

È possibile attivare eventi aggiuntivi SChannel modificando il valore della seguente chiave del Registro di sistema da **1** (tipo **REG\_DWORD**, dati **0x00000001**) a **3** (tipo **REG\_DWORD**, dati **0x00000003**):

**HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL\\EventLogging**

**Avviso:** modifiche non corrette al Registro di sistema potrebbero danneggiare gravemente il sistema. Prima di apportare modifiche al Registro di sistema, è consigliabile eseguire il backup di tutti i dati importanti presenti nel computer.

Accertarsi di disattivare la registrazione SChannel durante l'attività di risoluzione dei problemi.

[](#mainsection)[Inizio pagina](#mainsection)

### Attività della fase di ottimizzazione

Nella fase di ottimizzazione sono incluse le funzioni SMF con cui gestire i costi mantenendo o migliorando i livelli di servizio. Tra queste rientrano l'analisi delle interruzioni o delle emergenze, l'esame delle strutture di costo, le valutazioni del personale, la disponibilità, l'analisi delle prestazioni e la previsione della capacità.

In questa sezione vengono fornite le informazioni relative alle seguenti funzioni SMF:

-   Gestione della capacità

Non esistono attività per le restanti funzioni di gestione dei servizi:

-   Gestione dei livelli di servizio

-   Gestione finanziaria

-   Gestione della disponibilità

-   Gestione della continuità dei servizi IT

-   Gestione della forza lavoro

#### Gestione della capacità

La gestione della capacità è il processo di pianificazione, dimensionamento e controllo della capacità della soluzione di servizi in modo che soddisfi la richiesta degli utenti entro i livelli di prestazioni stabiliti nel contratto del livello di servizio. Il processo richiede informazioni relative agli scenari di utilizzo, agli schemi e alle caratteristiche di carico massimo della soluzione di servizi, nonché requisiti di prestazione definiti.

##### Determinazione del carico massimo sul server IAS

In questa sezione vengono fornite alcune informazioni sul carico massimo probabile del server IAS.

Raramente le prestazioni costituiscono un problema per i server RADIUS IAS che sono dimensionati e configurati correttamente. I server RADIUS IAS subiscono un carico maggiore durante le ore di punta, ad esempio al mattino, quando un gran numero di utenti accede contemporaneamente, subito dopo un'interruzione di rete importante o durante un errore del server RADIUS nel failover dei punti di accesso senza fili al server di backup.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
L'attività di test interna di Microsoft ha mostrato che IAS può raggiungere un carico massimo, su hardware modesto, in grado di servire la maggior parte delle esigenze dei clienti. La stima del numero di autenticazioni che IAS è in grado di gestire deve essere espressa in autenticazioni al secondo. IAS è in grado di raggiungere le seguenti prestazioni con un server Intel Pentium 4 a 2 GHz su cui viene eseguito Windows Server 2003 con Active Directory su un altro server Intel Pentium 4 a 2 GHz. Queste informazioni vengono fornite senza alcuna garanzia e devono essere intese come mere linee guida ai fini della pianificazione della capacità e non ai fini di un confronto fra prestazioni:
  
**Tabella 10. Determinazione del carico sul server IAS**

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
  
IAS può essere configurato in modo che generi registri di testo basati su disco contenenti quantità variabili di informazioni sulle richieste RADIUS. Occorre considerare attentamente il sovraccarico che le attività di registrazione RADIUS comportano per i server RADIUS, in quanto i sottosistemi disco lenti possono ritardare le risposte RADIUS IAS ai dispositivi WAP, con conseguenti timeout dei protocolli e inutili operazioni di failover dei dispositivi WAP ai server RADIUS secondari.
  
Inoltre, l'attivazione delle funzionalità di analisi software di Windows Server 2003 causerà carico aggiuntivo sui server IAS, sebbene possa essere necessaria per risolvere i problemi di accesso alla rete. I server IAS, pertanto, dovrebbero avere la capacità di funzionare e gestire il carico di produzione anche quando le funzionalità di analisi risultano attive per brevi periodi di tempo.
  
##### Determinazione dei requisiti di archiviazione e di backup per un server IAS
  
In questa sezione vengono forniti i dettagli sulla capacità per i parametri di archiviazione IAS. Tali dettagli consentiranno ai pianificatori della capacità di calcolare i requisiti futuri per l'archiviazione di backup su disco e non in linea.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>
</tbody>
</table>
  
**Dettagli relativi all'attività**
  
I file registro RADIUS IAS sono l'unico componente dei server IAS per il quale è necessaria la pianificazione dell'archiviazione. I registri delle richieste RADIUS per questa soluzione sono configurati in modo da creare un registro nuovo ogni mese, mentre l'hardware sottoposto a test durante lo sviluppo di questa soluzione includeva un volume disco rigido di 18 GB dedicato ai file registro.
  
Per simulare il processo di autenticazione dei client senza fili al server IAS e la conseguente generazione di dati di registro, è necessario calcolare il carico stimato sui server IAS dell'ambiente, quindi scegliere le opzioni di registrazione ed eseguire i test in un ambiente di laboratorio. Per le stime, è possibile utilizzare una logica simile a quella riportata di seguito:
  
Il numero massimo di utenti per punto di accesso senza fili è di circa 25 utenti con 25 computer che effettuano un'autenticazione iniziale e quindi una nuova autenticazione ogni 10 minuti. Ogni autenticazione genera 1 kilobyte di informazioni di registrazione su disco (vengono registrate le richieste di autenticazione e le richieste di controllo, non le richieste provvisorie). Le dimensioni del file variano a seconda delle opzioni di registrazione. Calcolare la quantità di spazio di registrazione su disco generata per punto di accesso senza fili ogni ora per supportare 25 utenti e 25 computer, vale a dire 50 client. A questo punto eseguire la stima del massimo numero di punti di accesso senza fili che il server IAS principale supporterà nelle ore di carico della rete o di failover del server.
  
I registri delle richieste RADIUS IAS contengono dati altamente comprimibili. Sebbene non sia consigliabile utilizzarla normalmente, in caso di necessità è possibile attivare la compressione della cartella dei file registro delle richieste RADIUS. Ricordare che un server IAS a cui viene richiesta la compressione istantanea dei dati sarà sottoposto a un carico aggiuntivo.
  
**Intervallo di backup per i file registro RADIUS IAS**
  
Considerando un backup di rete che funziona in condizioni ideali su uno switch dedicato da 100 Mbps e collegato al server di backup, il backup di un database da 3 GB e di uno stato del sistema di 500 MB richiederà circa 15-20 minuti.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di modifica
  
Nella fase di modifica sono inclusi i processi e le procedure necessari a identificare, analizzare, approvare e incorporare le modifiche in un ambiente IT gestito. Le modifiche includono le risorse hardware e software nonché le modifiche di processi e procedure specifici.
  
Obiettivo del processo di modifica è introdurre rapidamente nell'ambiente IT, con disagi minimi al servizio, nuove tecnologie, sistemi, applicazioni, hardware, strumenti e processi, nonché modifiche dei ruoli e delle responsabilità.
  
#### Gestione delle modifiche
  
La funzione SMF di gestione delle modifiche è responsabile della gestione delle modifiche in un ambiente IT. Obiettivo principale del processo di gestione delle modifiche è assicurare che tutte le parti interessate da una determinata modifica siano consapevoli dell'impatto dell'imminente modifica. Poiché la maggior parte dei sistemi è strettamente correlata, le modifiche apportate a una parte del sistema potrebbero avere ripercussioni su un'altra parte. La gestione delle modifiche cerca di identificare tutti i sistemi e i processi interessati prima che la modifica sia distribuita, in modo da ridurre o eliminare qualsiasi effetto negativo. In genere, l'ambiente di destinazione, o ambiente gestito, è l'ambiente di produzione; tuttavia sarebbe opportuno includere gli ambienti di integrazione, test e temporanei principali.
  
Tutte le modifiche all'infrastruttura RADIUS e alla protezione WLAN dovranno seguire il processo di gestione delle modifiche MOF standard illustrato di seguito:
  
1.  **Richiesta di modifica** — avvio formale di una modifica mediante l'invio di una richiesta di modifica (RFC, Request For Change).
  
2.  **Classificazione della modifica** — assegnazione di una priorità e di una categoria alla modifica, mediante i criteri di urgenza e di impatto sull'infrastruttura o sugli utenti. Tale assegnazione influisce sulla velocità e sul percorso dell'implementazione.
  
3.  **Autorizzazione alla modifica** — la considerazione e l'approvazione o il rifiuto della modifica da parte del responsabile delle modifiche e del consiglio consultivo per le modifiche(Change Advisory Board), che include i rappresentanti del reparto IT e i rappresentanti dell'azienda.
  
4.  **Sviluppo della modifica** — la pianificazione e lo sviluppo della modifica, un processo di ambito estremamente variabile che include analisi nelle fasi principali intermedie.
  
5.  **Rilascio della modifica** — il rilascio e la distribuzione della modifica nell'ambiente di produzione.
  
6.  **Esame della modifica** — il processo successivo all'implementazione che verifica se la modifica ha raggiunto gli obiettivi stabiliti e stabilisce se conservarla oppure ritirarla.
  
Le procedure di questa sezione illustrano come sviluppare alcune delle modifiche principali che probabilmente saranno necessarie regolarmente nell'ambiente in uso. Ciascuna procedura di sviluppo delle modifiche è affiancata da una procedura di rilascio in cui sono descritte le modalità di distribuzione della modifica nella produzione.
  
##### Gestione delle patch del sistema operativo
  
La gestione delle patch per i componenti 802.1X di IAS e di Windows XP è illustrata in due guide operative di Microsoft Solutions for Management, dal momento che tali componenti sono trattati nella gestione generale delle patch di Windows. Per i collegamenti a questi documenti, vedere la sezione "Ulteriori informazioni" alla fine di questo modulo.
  
La gestione delle patch include componenti di gestione del rilascio e componenti di gestione della configurazione, nonché un componente di gestione delle modifiche. Tuttavia, tutte e tre le funzioni SMF sono trattate nei documenti a cui è stato fatto riferimento in precedenza.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Tabelle di configurazione
  
Nelle tabelle che seguono sono contenute le informazioni di configurazione specifiche del sito e della soluzione a cui si fa riferimento nelle procedure di questo modulo.
  
#### Parametri di configurazione per sito
  
**Tabella 11. Elementi di configurazione definiti dall'utente**

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
<th><p>Nome variabile</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Nome DNS del dominio principale dell'insieme di strutture di Microsoft Active Directory</p></td>
<td style="border:1px solid black;"><p>woodgrovebank.com</p></td>
<td style="border:1px solid black;"><p>ForestRootDomain</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Nome NetBIOS (Network Basic Input/Output System) del dominio</p></td>
<td style="border:1px solid black;"><p>WOODGROVEBANK</p></td>
<td style="border:1px solid black;"><p>NBDomainName</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Nome server del server IAS principale</p></td>
<td style="border:1px solid black;"><p>MSS - IAS - 01</p></td>
<td style="border:1px solid black;"><p>PrimaryIAShostname</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Nome server del server IAS secondario</p></td>
<td style="border:1px solid black;"><p>MSS - IAS - 02</p></td>
<td style="border:1px solid black;"><p>SecondaryIAShostname</p></td>
</tr>
</tbody>
</table>
  
#### Parametri di configurazione della soluzione
  
**Tabella 12. Elementi di configurazione prescritti nella soluzione**

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
<th><p>Nome variabile</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Nome completo del gruppo amministrativo che controlla la configurazione di IAS</p></td>
<td style="border:1px solid black;"><p>IAS Admins</p></td>
<td style="border:1px solid black;"><p><em>IASAdminsGroup</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Nome pre-Windows 2000 del gruppo amministrativo che controlla la configurazione di IAS</p></td>
<td style="border:1px solid black;"><p>IAS Admins</p></td>
<td style="border:1px solid black;"><p><em>IASAdminsNTGroup</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Nome completo del gruppo che esamina i registri delle richieste di autenticazione e accounting IAS a fini di protezione</p></td>
<td style="border:1px solid black;"><p>IAS Security Auditors</p></td>
<td style="border:1px solid black;"><p><em>IASSecAuditGroup</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Nome pre-Windows 2000 del gruppo che esamina i registri delle richieste di autenticazione e accounting IAS a fini di protezione</p></td>
<td style="border:1px solid black;"><p>IAS Security Auditors</p></td>
<td style="border:1px solid black;"><p><em>IASSecAuditNTGroup</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Gruppo globale Active Directory contenente gli utenti che richiedono certificati di autenticazione 802.1x</p></td>
<td style="border:1px solid black;"><p>AutoEnroll Client Authentication - User Certificate</p></td>
<td style="border:1px solid black;"><p><em>EnrollUserCertGroup</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Gruppo globale Active Directory contenente i computer che richiedono certificati di autenticazione 802.1x</p></td>
<td style="border:1px solid black;"><p>AutoEnroll Client Authentication - Computer Certificate</p></td>
<td style="border:1px solid black;"><p><em>EnrollComputerCertGroup</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Gruppo globale Active Directory contenente i server IAS che richiedono certificati di autenticazione 802.1X</p></td>
<td style="border:1px solid black;"><p>AutoEnroll RAS and IAS Server Authentication Certificate</p></td>
<td style="border:1px solid black;"><p>EnrollIASCertGroup</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Nome pre-Windows 2000 del gruppo globale Microsoft Active Directory contenente i server IAS che richiedono certificati di autenticazione 802.1X</p></td>
<td style="border:1px solid black;"><p>AutoEnroll RAS and IAS Server Authentication Certificate</p></td>
<td style="border:1px solid black;"><p><em>EnrollIASCertNTGroup</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Gruppo globale Active Directory contenente gli utenti a cui è consentito l'accesso alla rete senza fili</p></td>
<td style="border:1px solid black;"><p>Remote Access Policy - Wireless Users</p></td>
<td style="border:1px solid black;"><p><em>WLANUsersGroup</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Gruppo globale Active Directory contenente i computer a cui è consentito l'accesso alla rete senza fili</p></td>
<td style="border:1px solid black;"><p>Remote Access Policy - Wireless Computers</p></td>
<td style="border:1px solid black;"><p><em>WLANComputersGroup</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Account] Gruppo universale Active Directory contenente il gruppo Wireless Users e il gruppo Wireless Computers</p></td>
<td style="border:1px solid black;"><p>Remote Access Policy - Wireless Access</p></td>
<td style="border:1px solid black;"><p><em>WLANAccessGroup</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Account] Gruppo globale Active Directory contenente i computer che richiedono la configurazione delle proprietà della rete senza fili mediante Criteri di gruppo di Active Directory</p></td>
<td style="border:1px solid black;"><p>Wireless Network Policy - Computer</p></td>
<td style="border:1px solid black;"><p><em>WLANConfigPolicyGroup</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Certificati] Modello di certificato utilizzato per generare i certificati per l'autenticazione client degli utenti</p></td>
<td style="border:1px solid black;"><p>Client Authentication - User</p></td>
<td style="border:1px solid black;"><p><em>UserClientAuthTemplate</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Certificati] Modello di certificato utilizzato per generare i certificati per l'autenticazione client dei computer</p></td>
<td style="border:1px solid black;"><p>Client Authentication - Computer</p></td>
<td style="border:1px solid black;"><p><em>ComputerClientAuthTemplate</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Certificati] Modello di certificato utilizzato per generare i certificati di autenticazione server che dovranno essere utilizzati da IAS</p></td>
<td style="border:1px solid black;"><p>RAS and IAS Server Authentication</p></td>
<td style="border:1px solid black;"><p><em>IASServerCertificate</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Script] Percorso degli script di installazione</p></td>
<td style="border:1px solid black;"><p>C:\MSSScripts</p></td>
<td style="border:1px solid black;"><p><em>ScriptPath</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Script] File batch di esportazione della configurazione IAS</p></td>
<td style="border:1px solid black;"><p>IASExport.bat</p></td>
<td style="border:1px solid black;"><p><em>IASExportBatch</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Script] File batch di importazione della configurazione IAS</p></td>
<td style="border:1px solid black;"><p>IASImport.bat</p></td>
<td style="border:1px solid black;"><p><em>IASImportBatch</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Script] File batch di esportazione della configurazione dei client IAS</p></td>
<td style="border:1px solid black;"><p>IASClientExport.bat</p></td>
<td style="border:1px solid black;"><p><em>IASClientExportBatch</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Script] File batch di importazione della configurazione dei client IAS</p></td>
<td style="border:1px solid black;"><p>IASClientImport.bat</p></td>
<td style="border:1px solid black;"><p><em>IASClientImportBatch</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Config] Percorso dei file di backup della configurazione</p></td>
<td style="border:1px solid black;"><p>D:\IASConfig</p></td>
<td style="border:1px solid black;"><p><em>ConfigPath</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Registri richieste] Percorso dei registri delle richieste di autenticazione e controllo IAS</p></td>
<td style="border:1px solid black;"><p>D:\IASLogs</p></td>
<td style="border:1px solid black;"><p><em>IASRequestLogLocation</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Registri richieste] Nome della condivisione dei registri delle richieste RADIUS</p></td>
<td style="border:1px solid black;"><p>IASLogs</p></td>
<td style="border:1px solid black;"><p><em>IASLogShare</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Criterio di accesso remoto] Nome del criterio</p></td>
<td style="border:1px solid black;"><p>Allow Wireless Access</p></td>
<td style="border:1px solid black;"><p><em>IASRAPName</em></p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>[Criteri di gruppo] Nome dell'oggetto Criteri di gruppo (GPO) di Active Directory</p></td>
<td style="border:1px solid black;"><p>Wireless Network Policy</p></td>
<td style="border:1px solid black;"><p><em>GPONameForWLAN</em></p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>[Criteri di gruppo] Criterio della rete senza fili all'interno dell'oggetto Criteri di gruppo</p></td>
<td style="border:1px solid black;"><p>Client Computer Wireless Configuration</p></td>
<td style="border:1px solid black;"><p><em>ClientWLANPolicy</em></p></td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
Per ulteriori informazioni sul monitoraggio dei vincoli di capacità IAS e sulla misurazione delle prestazioni dei dischi, consultare l'articolo Q146005 della Microsoft Knowledge Base, "Optimizing Windows NT for Performance", all'indirizzo <http://support.microsoft.com/default.aspx?scid=146005> (in inglese).
  
Per ulteriori informazioni sul modello dei processo e sul modello di team Microsoft Operations Framework, consultare la *Guida operativa*.
  
-   Per informazioni sulla distribuzione di MOM, consultare la guida *Microsoft Operations Manager 2000 Operations Guide*, all'indirizzo <http://technet.microsoft.com/en-us/library/cc181143.aspx>(in inglese).
  
-   Per informazioni sulla gestione delle patch mediante Microsoft Systems Management Server, vedere l'indirizzo [http://www.microsoft.com/italy/technet/risorse/info\_tech/servers/pmsmsag](http://technet.microsoft.com/en-us/library/cc182024.aspx) (in inglese).
  
-   Per informazioni sulla gestione delle patch mediante Microsoft Software Update Services, vedere l'indirizzo [http://www.microsoft.com/italy/technet/risorse/info\_tech/servers/pmsusag](http://technet.microsoft.com/en-us/library/cc708609.aspx) (in inglese).
  
-   Per ulteriori informazioni sulla Console di gestione Criteri di gruppo (GPMC, Group Policy Management Console), vedere l'indirizzo <http://www.microsoft.com/windowsserver2003/gpmc/default.mspx> (in inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
