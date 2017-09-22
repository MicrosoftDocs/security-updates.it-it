---
TOCTitle: 'Guida operativa - Gestione dell''infrastruttura a chiave pubblica'
Title: 'Guida operativa - Gestione dell''infrastruttura a chiave pubblica'
ms:assetid: 'e6c7636a-d366-4fe7-a3b6-280107085269'
ms:contentKeyID: 20200812
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536212(v=TechNet.10)'
---

Capitolo 11: Gestione dell'infrastruttura a chiave pubblica
===========================================================

Pubblicato: 10 novembre 2004 | Aggiornato: 24 novembre 2004

##### In questa pagina

[](#ejaa)[Introduzione](#ejaa)
[](#eiaa)[Attività fondamentali di manutenzione](#eiaa)
[](#ehaa)[Ruoli amministrativi di Servizi certificati](#ehaa)
[](#egaa)[Attività della fase operativa](#egaa)
[](#efaa)[Attività della fase di supporto](#efaa)
[](#eeaa)[Attività della fase di ottimizzazione](#eeaa)
[](#edaa)[Attività della fase di modifica](#edaa)
[](#ecaa)[Risoluzione dei problemi](#ecaa)
[](#ebaa)[Tabelle di configurazione](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Introduzione

In questo capitolo vengono descritte le procedure operative necessarie per la gestione dell'infrastruttura a chiave pubblica (PKI, Public Key Infrastructure) implementata come parte della soluzione *Protezione delle reti LAN senza fili*. La struttura si basa sulle categorie MOF (Microsoft Operational Framework) e sui concetti discussi nel primo capitolo della Guida operativa (capitolo 10).

Lo scopo di questo modulo è di consentire l'implementazione di un sistema di gestione completo dell'infrastruttura PKI. Negli argomenti trattati sono incluse tutte le attività di configurazione necessarie per iniziare il monitoraggio e la gestione del sistema e le normali attività operative occorrenti per mantenere il sistema in buono stato di funzionamento. Inoltre, vengono descritte le procedure per affrontare i problemi di supporto, gestire le modifiche all'ambiente e ottimizzare le prestazioni del sistema.

Il capitolo comprende due parti principali. La prima parte è composta da due sezioni: "Attività fondamentali di manutenzione" e "Assegnazione dei ruoli amministrativi". Sono brevi sezioni e devono essere lette per intero, in quanto forniscono informazioni essenziali sulla configurazione necessaria a ottimizzare la gestione dell’ambiente per il sistema in uso. La parte restante del capitolo deve essere considerata come materiale di riferimento. Alcune attività descritte nelle sezioni di riferimento devono essere implementate durante la distribuzione del sistema e sono chiaramente indicate nella sezione "Attività fondamentali di manutenzione".

Sebbene non sia necessario apprendere tutti i dettagli descritti nella sezione di riferimento, si consiglia di consultarli per ottenere informazioni sui contenuti e individuare gli elementi che potrebbero essere utili in futuro.

#### Prima di iniziare

È consigliabile acquisire familiarità con i concetti MOF descritti nel capitolo 10, "Introduzione alla Guida operativa", anche se non è necessaria una conoscenza approfondita di MOF.

È necessario conoscere inoltre alcuni concetti relativi all'infrastruttura PKI e, in particolare, a Servizi certificati Microsoft®. È inoltre consigliabile conoscere Microsoft Windows® 2000 Server (o versioni successive) nelle seguenti aree:

-   Operazioni di base e manutenzione di Microsoft Windows Server™ 2003, compreso l’utilizzo di strumenti quali Visualizzatore eventi, Gestione computer e NTBackup.

-   Servizio directory Active Directory®, tra cui la struttura e gli strumenti di Active Directory; la gestione di utenti, gruppi e altri oggetti Active Directory e l’uso dei criteri di gruppo.

-   Concetti alla base della protezione dei sistemi Windows, quali utenti, gruppi, controllo, elenchi di controllo di accesso, utilizzo dei modelli di protezione e applicazione dei modelli di protezione mediante i criteri di gruppo o utilizzo degli strumenti della riga di comando.

-   Amministrazione di IIS (Internet Information Services).

-   Anche se non è essenziale, la conoscenza di Windows Scripting Host e del linguaggio Microsoft Visual Basic® Scripting Edition (VBScript) può contribuire a trarre il massimo vantaggio dagli script forniti.

Prima di proseguire con gli argomenti del capitolo, è necessario aver letto anche i capitoli correlati alla Guida alla pianificazione e alla Guida alla creazione (capitoli 4 e 6) e avere compreso l’architettura e la progettazione della soluzione.

#### Panoramica dei capitoli

L'elenco seguente descrive le sezioni principali di questo capitolo.

-   **Attività fondamentali di manutenzione** Contiene due tabelle in cui vengono elencate le attività da impostare, il sistema di gestione e l'elenco normale di attività da eseguire per garantire il costante funzionamento del sistema.

-   **Ruoli amministrativi** Descrive i ruoli amministrativi utilizzati nella soluzione, le capacità di ciascun ruolo, le modalità di corrispondenza di tali ruoli ai cluster di ruoli MOF e i gruppi amministrativi di protezione definiti per la soluzione.

-   **Attività della fase operativa** Include tutte le attività collegate alla normale manutenzione dell'infrastruttura PKI. Le attività includono monitoraggio, backup e operazioni per le directory e la protezione.

-   **Attività della fase di supporto** Include tutte le procedure associate al ripristino in seguito a problemi di sistema. Queste procedure includono la revoca dei certificati e delle autorità di certificazione (CA), il ripristino da backup e le operazioni per la gestione di una CA non riuscita.

-   **Attività della fase di ottimizzazione.** Include alcune procedure di pianificazione della gestione della capacità.

-   **Attività della fase di modifica** Include attività comuni relative alla modifica della configurazione CA e al rilascio di CA in produzione in maniera controllata. Inoltre, comprende procedure per consentire la raccolta e la gestione di informazioni di configurazione fondamentali relative all'infrastruttura PKI.

-   **Risoluzione dei problemi** Contiene procedure utili per risolvere i problemi comuni che possono verificarsi nell'infrastruttura PKI. Contiene, inoltre, descrizioni di strumenti e procedure utili per tenere traccia delle attività dei vari componenti e risolvere eventuali problemi.

-   **Tabelle di configurazione** Contiene un sottoinsieme di parametri di configurazione utilizzati nella guida alla creazione. Tali valori sono utilizzati come esempi per illustrare il testo delle procedure.

-   **Ulteriori informazioni** Elenca una serie di fonti di informazioni aggiuntive a cui si è fatto riferimento nel testo.

[](#mainsection)[Inizio pagina](#mainsection)

### Attività fondamentali di manutenzione

In questa sezione sono elencate le attività principali da eseguire per un corretto funzionamento dell'infrastruttura PKI. Le attività iniziali di configurazione e le attività operative ordinarie sono elencate in due tabelle. Le attività elencate nelle tabelle sono descritte dettagliatamente più avanti nel documento. Le attività sono raggruppate in base alla fase MOF, mentre la funzione di gestione dei servizi (SMF, Service Management Function) cui appartiene l'attività è indicata accanto a questa, in modo che sia più semplice trovarla.

In questa sezione è incluso anche un elenco degli strumenti e delle tecnologie utilizzate nelle procedure di questo capitolo.

#### Attività iniziali di configurazione

In questa tabella sono elencate le attività da eseguire per avviare la produzione operativa dell'infrastruttura PKI. Le attività da eseguire possono variare a seconda degli standard e delle procedure operative di un'azienda. Esaminare in dettaglio le attività per decidere se eseguirle o meno. È anche possibile che alcune di queste attività debbano essere eseguite nuovamente. Ad esempio, se viene installata una nuova CA, sarà necessario configurare le relative operazioni di backup e di monitoraggio.

**Tabella 11.1. Attività iniziali di configurazione**

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
<th><p>SMF</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p><strong>Fase di operatività</strong></p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Preparazione di una struttura di unità organizzativa di dominio per la gestione di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Amministrazione dei servizi directory</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Pubblicazione degli elenchi CRL della CA di emissione nel server Web</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Amministrazione della protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Configurazione di un backup del database dell'autorità di certificazione emittente</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Configurazione del backup del database autorità di certificazione principale</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Test dei backup per database autorità di certificazione</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Test dei backup per chiave autorità di certificazione</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Classificazione degli avvisi di monitoraggio</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Monitoraggio e controllo dei servizi</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Monitoraggio restrizioni capacità Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Monitoraggio e controllo dei servizi</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Monitoraggio integrità e disponibilità Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Monitoraggio e controllo dei servizi</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Impostazione degli avvisi SMTP per le richieste di certificati in sospeso</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Monitoraggio e controllo dei servizi</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Pianificazione processi autorità di certificazione emittente</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Pianificazione dei processi</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><strong>Fase di ottimizzazione</strong></p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Definizione del carico massimo per l'autorità di certificazione emittente</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Gestione della capacità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Definizione dei requisiti di archiviazione e backup per un'autorità di certificazione emittente</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Gestione della capacità</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><strong>Fase di modifica</strong></p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Gestione degli aggiornamenti del sistema operativo</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Gestione delle modifiche<br />
Gestione del rilascio</p></td>
</tr>
</tbody>
</table>
<p> </p>

Sebbene non esista un'attività documentata per l'impostazione di un sistema di gestione della configurazione per l'infrastruttura PKI, esaminare le procedure descritte nella sezione "Gestione della configurazione", in cui sono descritti i tipi di informazioni da raccogliere e conservare in un sistema di gestione della configurazione.

#### Attività di manutenzione

In questa tabella sono elencate le attività da eseguire regolarmente per mantenere in perfetto stato di funzionamento l'infrastruttura PKI. La tabella può essere utilizzata nella pianificazione delle risorse necessarie e nella pianificazione operativa dell'amministrazione del sistema.

È possibile che esistano alcune attività che non occorre eseguire; tuttavia, prima di decidere è opportuno verificarne i dettagli. Per alcune attività sarà necessaria l'esecuzione occasionale, mentre per altre è bene pianificarne l'esecuzione. Ad esempio, se un certificato della CA principale viene rinnovato, sarà necessario eseguire un backup della CA principale anche se l'attività non è pianificata. In questi casi viene inserita una nota nella colonna Frequenza. Dipendenze di questo tipo vengono anche annotate nei dettagli stessi dell'attività.

**Tabella 11.2. Attività di manutenzione**

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
<th><p>Frequenza</p></th>
<th><p>SMF</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p><strong>Fase di operatività</strong></p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Controllo richieste in sospeso</p></td>
<td style="border:1px solid black;"><p>Ogni giorno</p></td>
<td style="border:1px solid black;"><p>Amministrazione della protezione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Rinnovo certificato CA principale</p></td>
<td style="border:1px solid black;"><p>Ogni otto anni</p></td>
<td style="border:1px solid black;"><p>Amministrazione della protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Rinnovo certificato CA di emissione</p></td>
<td style="border:1px solid black;"><p>Ogni quattro anni</p></td>
<td style="border:1px solid black;"><p>Amministrazione della protezione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Pubblicazione elenco CRL non in linea e certificato CA</p></td>
<td style="border:1px solid black;"><p>Ogni sei mesi</p></td>
<td style="border:1px solid black;"><p>Amministrazione della protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Backup di chiavi e certificati CA</p></td>
<td style="border:1px solid black;"><p>Annuale oppure ogni volta che il certificato CA viene rinnovato (in base a quale evento si verifica per primo)</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Test dei backup per database autorità di certificazione</p></td>
<td style="border:1px solid black;"><p>Ogni mese</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Test dei backup per chiave autorità di certificazione</p></td>
<td style="border:1px solid black;"><p>Ogni sei mesi</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Archiviazione di dati di controllo della protezione da una CA</p></td>
<td style="border:1px solid black;"><p>Mensile (CA di emissione)</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Archiviazione di dati di controllo della protezione da una CA</p></td>
<td style="border:1px solid black;"><p>Ogni sei mesi (CA principale)</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
</tbody>  
</table>
  
#### Tecnologia richiesta nella Guida operativa
  
Nella tabella riportata di seguito sono elencati gli strumenti o le tecnologie utilizzati nelle procedure descritte in questo capitolo.
  
**Tabella 11.3. Tecnologia richiesta**

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
<td style="border:1px solid black;"><p>Console di gestione (snap-in MMC) Utenti e computer di Active Directory</p></td>
<td style="border:1px solid black;"><p>Microsoft Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Snap-in MMC Autorità di certificazione</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Snap-in MMC Modelli di certificato</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Certutil.exe</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Certreq.exe</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Script MSS</p></td>
<td style="border:1px solid black;"><p>Questa soluzione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Editor di testo</p></td>
<td style="border:1px solid black;"><p>Blocco note, Windows Server 2003</p></td>
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
<td style="border:1px solid black;"><p>Cipher.exe</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Visualizzatore eventi</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Performance Monitor</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Net.exe</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>DSquery.exe</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Ldifde.exe</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>DCDiag.exe</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Console avvisi operativi</p></td>
<td style="border:1px solid black;"><p>Microsoft Operations Manager (MOM)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Supporti rimovibili per il backup della CA principale</p></td>
<td style="border:1px solid black;"><p>CD-RW o nastro</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Backup server CA di emissione</p></td>
<td style="border:1px solid black;"><p>Servizio di backup aziendale o<br />
Periferica di backup locale</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Snap-in MMC Criteri di gruppo</p></td>
<td style="border:1px solid black;"><p>Download Web da Microsoft.com</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Integrità PKI</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003 Resource Kit</p></td>
</tr>  
</tbody>  
</table>
  
**Tabella 11.4. Tecnologia consigliata**

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
<td style="border:1px solid black;"><p>Sistema di distribuzione degli aggiornamenti della protezione</p></td>
<td style="border:1px solid black;"><p>Microsoft Systems Management Server o Microsoft Software Update Services</p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ruoli amministrativi di Servizi certificati
  
Numerosi ruoli sono coinvolti nella gestione di un'infrastruttura PKI. Nelle due sezioni che seguono tali ruoli sono suddivisi in due categorie: principali e di supporto.
  
#### Ruoli principali di Servizi certificati
  
Questa categoria di ruoli è fondamentale per la gestione di un'infrastruttura a chiave pubblica. Molti di questi corrispondono ai ruoli di protezione di criteri comuni definiti per Servizi certificati. In questi casi viene inserita una nota tra parentesi  dopo il nome del ruolo.
  
**Tabella 11.5. Ruoli principali di Servizi certificati**

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
<td style="border:1px solid black;"><p>Enterprise PKI Administrator</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile dell'intera infrastruttura PKI; definisce tipi di certificati, criteri di applicazioni, percorsi di trust e così via per un'organizzazione di grandi dimensioni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Enterprise PKI Publisher</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile della pubblicazione di certificati affidabili principali, certificati CA secondari e di elenchi CRL nella directory.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore CA<br />
(ruolo Amministratore CA)</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Amministratore CA; responsabile della configurazione CA e dell'assegnazione dei ruoli sulla CA. Di solito coincide con il ruolo Amministratori PKI dell'organizzazione.<br />
È possibile assegnare più amministratori CA a CA differenti se ciò è richiesto dall’utilizzo dei certificati.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Amministratore<br />
(ruolo Amministratore CA)</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Amministratore del sistema operativo del server CA; responsabile della configurazione a livello di server (ad esempio, installazione CA). Di solito coincide con il ruolo Amministratori CA.<br />
È possibile assegnare più amministratori a CA differenti se ciò è richiesto dall’utilizzo dei certificati.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Controllore CA<br />
(ruolo Controllore CA)</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Gestisce eventi di controllo, criteri e tutto ciò che riguarda gli eventi CA controllabili.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Responsabile certificati<br />
(ruolo Responsabile CC)</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Approva le richieste di certificati per cui è richiesta approvazione manuale e revoca certificati.<br />
Possono coesistere più responsabili certificati che si occupano dell'approvazione per CA differenti se l'utilizzo dei certificati lo richiede.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Autorità di registrazione</p></td>
<td style="border:1px solid black;"><p>Profilo del certificato</p></td>
<td style="border:1px solid black;"><p>Estensione del ruolo del responsabile certificati, che si occupa dell'approvazione e della firma di richieste di certificati in seguito a una verifica ID del soggetto certificato.<br />
Il ruolo può essere ricoperto da una persona, da un processo IT o da un dispositivo (ad esempio, scanner di impronte digitali e database).<br />
È possibile specificare autorità di registrazione differenti per profili di certificati diversi (modelli) e interessare più CA.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Key Recovery Agent</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Detiene le chiavi per la decrittografia di chiavi private, archiviate nel database CA.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Operatore di backup CA<br />
(ruolo Operatore CC)</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Responsabile di backup e ripristino di server CA e di conservare in modo sicuro i supporti di backup.</p></td>
</tr>  
</tbody>  
</table>
  
#### Ruoli di supporto di Servizi certificati
  
I ruoli operativi descritti nella tabella riportata di seguito non sono centrali nella gestione dell'infrastruttura a chiave pubblica, ma forniscono funzioni di supporto ai ruoli fondamentali.
  
**Tabella 11.6. Ruoli di supporto di Servizi certificati**

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
<td style="border:1px solid black;"><p>Responsabile del monitoraggio di eventi.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Pianificatore della capacità</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile dell'analisi di prestazioni e carico per la previsione di requisiti futuri di capacità.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore di Active Directory</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile di configurazione e supporto dell'infrastruttura Active Directory.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Gestione delle operazioni di Active Directory</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Responsabile della manutenzione quotidiana della directory (ad esempio, gestione dei gruppi di protezione, creazione di account e così via).</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consiglio di approvazione delle modifiche</p></td>
<td style="border:1px solid black;"><p>Organizzazione</p></td>
<td style="border:1px solid black;"><p>Rappresentanti del settore tecnico e aziendale necessari per l'approvazione di modifiche all'infrastruttura.</p></td>
</tr>  
</tbody>  
</table>
  
#### Mapping di ruoli di Servizi certificati con gruppi di protezione
  
Nella tabella seguente sono elencati i gruppi di protezione definiti per questa soluzione e vengono brevemente descritte le funzionalità o le autorizzazioni di ogni gruppo.
  
Per le CA non in linea esistono solo gruppi di protezione locali. In questo caso, vengono creati singoli account locali nella CA, utilizzati in seguito per popolare i gruppi locali. È possibile rendere i singoli account membri di più o anche di tutti i gruppi di ruoli locali, se questa condizione è supportata dai criteri IT e di protezione dell'organizzazione.
  
I gruppi di protezione di dominio delle CA in linea vengono utilizzati per applicare le autorizzazioni destinate a ogni ruolo. Gli account di dominio sono utilizzati per popolare i gruppi di ruoli. È sempre possibile rendere i singoli account membri di più gruppi di ruoli se la configurazione supporta i criteri IT e di protezione dell'organizzazione.
  
**Tabella 11.7. Mapping di ruoli di Servizi certificati con gruppi di protezione**

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
<th><p>Gruppo di protezione di dominio (CA in linea)</p></th>  
<th><p>Gruppo di protezione locale (CA non in linea)</p></th>  
<th><p>Privilegi</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Enterprise PKI Administrator</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
<td style="border:1px solid black;"><p>–</p></td>
<td style="border:1px solid black;"><p>Controllo sul contenitore di servizi a chiave pubblica di Active Directory, quindi su modelli, pubblicazione trust e altri elementi di configurazione estesi a tutta l'organizzazione di grandi dimensioni (insieme di strutture).</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Enterprise PKI Publisher</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Publishers</p></td>
<td style="border:1px solid black;"><p>–</p></td>
<td style="border:1px solid black;"><p>Consente la pubblicazione di certificati affidabili principali, certificati CA secondari e di elenchi CRL nella directory.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore CA</p></td>
<td style="border:1px solid black;"><p>Amministratori CA</p></td>
<td style="border:1px solid black;"><p>Amministratori CA (solo CA principale)</p></td>
<td style="border:1px solid black;"><p>Dispone delle autorizzazioni di &quot;Gestione CA&quot; sull'autorità di certificazione. Controlla l'assegnazione di ruoli nella CA e può modificare le proprietà dell'autorità di certificazione.<br />
Di solito è associato al ruolo di amministratore locale del server CA, a meno che non sia richiesta una separazione di ruoli.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Amministratore</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratore locale del server CA.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Controllore CA</p></td>
<td style="border:1px solid black;"><p>Controllori CA</p></td>
<td style="border:1px solid black;"><p>Controllori CA (solo CA principale)</p></td>
<td style="border:1px solid black;"><p>Dispone del diritto utente per i registri di controllo e gestione protezione di una CA.<br />
Deve inoltre essere membro del gruppo Administrators locale per la CA (necessario per accedere ai registri di controllo).</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Responsabile certificati</p></td>
<td style="border:1px solid black;"><p>Responsabili certificazione</p></td>
<td style="border:1px solid black;"><p>Responsabili certificazione<br />
(solo CA principale)</p></td>
<td style="border:1px solid black;"><p>Dispone dell'autorizzazione &quot;Rilascio e Gestione certificati&quot; per la CA.<br />
È possibile configurare più responsabili certificati per ogni CA, ciascuno responsabile della gestione dei certificati per un sottoinsieme di utenti o altre entità.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Autorità di registrazione</p></td>
<td style="border:1px solid black;"><p>–</p></td>
<td style="border:1px solid black;"><p>–</p></td>
<td style="border:1px solid black;"><p>Detiene chiavi e certificati necessari per la firma delle richieste di certificati prima dell'approvazione.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Key Recovery Agent</p></td>
<td style="border:1px solid black;"><p>–</p></td>
<td style="border:1px solid black;"><p>–</p></td>
<td style="border:1px solid black;"><p>Detiene chiavi e certificati necessari per la decrittografia di chiavi private memorizzate nel database certificati.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Operatore di backup CA</p></td>
<td style="border:1px solid black;"><p>Operatori di backup CA</p></td>
<td style="border:1px solid black;"><p>Operatori di backup CA (solo CA principale)</p></td>
<td style="border:1px solid black;"><p>Dispone di diritti di backup e ripristino per il server CA.</p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase operativa
  
In questa sezione vengono fornite informazioni dettagliate sulle attività di manutenzione inerenti alla fase operativa MOF.
  
Tale fase include standard operativi, processi e procedure dell'infrastruttura IT applicate con regolarità alle soluzioni di servizi per raggiungere e mantenere livelli del servizio predeterminati. L'obiettivo della fase operativa è la previsione con grande anticipo dell'esecuzione di attività quotidiane, con o senza l'intervento di utenti.
  
In questa fase sono contenute le seguenti funzioni SMF:
  
-   Amministrazione dei servizi directory
  
-   Amministrazione della protezione
  
-   Gestione dell'archiviazione
  
-   Monitoraggio e controllo dei servizi
  
-   Pianificazione dei processi
  
Non esistono attività per le restanti funzioni SMF:
  
-   Gestione di sistema
  
-   Gestione della rete
  
-   Gestione della stampa e degli output
  
    **Nota:** ogni descrizione dell'attività contiene le seguenti informazioni di riepilogo: requisiti di protezione, frequenza e requisiti tecnologici.
  
#### Amministrazione dei servizi directory
  
I servizi directory consentono a utenti e applicazioni di trovare risorse di rete quali utenti, server, applicazioni, strumenti, servizi e altre informazioni in rete. L'amministrazione di tali servizi riguarda operazioni quotidiane, manutenzione e supporto per la directory di un'organizzazione di grandi dimensioni. L'obiettivo dell'amministrazione di questi servizi è garantire a tutti gli utenti autorizzati, mediante procedure semplici e organizzate, l'accesso alle informazioni in rete.
  
##### Preparazione di una struttura di unità organizzativa (OU) di dominio per la gestione di Servizi certificati
  
Scopo di questa attività è creare una struttura di unità organizzativa adatta a gestire account utente e gruppi di protezione per i Servizi certificati.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Account con diritti di creazione di unità organizzative in una parte di Active Directory specifica
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici:** Snap-in MMC Utenti e computer di Active Directory
  
###### Dettagli relativi all'attività
  
Questa attività non è rigida, infatti dipende molto dalla struttura dell'unità organizzativa esistente, nonché dai criteri e dalle procedure di gestione adottate. La seguente tabella fornisce un esempio di semplice sottostruttura di unità organizzativa che può essere utilizzata per semplificare l'organizzazione dei gruppi di protezione creati e descritti nella presente guida.
  
**Tabella 11.8. Collocazione dei gruppi di protezione all'interno della struttura dell'unità organizzativa**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Unità operativa</p></th>  
<th><p>Gruppi</p></th>  
<th><p>Scopo</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Servizi certificati</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Amministrazione Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins<br />
Enterprise PKI Publishers<br />  
CA Admins<br />  
CA Auditors<br />  
Certificate Managers<br />
CA Backup Operators</p></td>
<td style="border:1px solid black;"><p>Contiene gruppi amministrativi per la gestione della configurazione della CA e dell’infrastruttura PKI di un'organizzazione di grandi dimensioni.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Gestione modelli certificati</p></td>
<td style="border:1px solid black;"><p>Esempi:<br />
Gestione modello utente<br />
Gestione modello di accesso di smart card</p></td>
<td style="border:1px solid black;"><p>Contiene i gruppi ai quali è concesso il controllo completo del modello con lo stesso nome. Consente la delega del controllo in base al tipo di modello.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Registrazione modello di certificato</p></td>
<td style="border:1px solid black;"><p>Esempi:<br />
Registrazione certificato utente<br />  
Registrazione automatica certificato utente<br />
Registrazione certificato di firma per posta elettronica</p></td>
<td style="border:1px solid black;"><p>Contiene i gruppi ai quali è stata concessa l’autorizzazione di Registrazione o Registrazione automatica sui modelli con lo stesso nome. Il controllo dei gruppi può quindi essere delegato al personale preposto in modo da consentire un regime di registrazione flessibile senza dover coinvolgere i modelli stessi.</p></td>
</tr>  
</tbody>  
</table>
  
##### Creazione di gruppi di gestione di modelli di certificato
  
I gruppi di gestione di modelli consentono di delegare ad amministratori diversi il controllo sui modelli e sulle relative impostazioni. Solo i ruoli Amministratori organizzazione e Amministratori PKI dell'organizzazione hanno l’autorizzazione per modificare i modelli. Se l’organizzazione IT non è di grandi dimensioni, questo tipo di delega dettagliata potrebbe non essere necessario. In questo caso, solo i membri del gruppo incorporato Amministratori organizzazione e del gruppo Amministratori PKI dell'organizzazione (creato nell'ambito di questa soluzione) saranno in grado di gestire i modelli di certificato.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori PKI dell'organizzazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Snap-in MMC Utenti e computer di Active Directory
  
    -   Snap-in MMC Modello di certificato
  
        **Avviso**: prestare estrema attenzione quando si utilizza questa funzionalità. La delega del controllo su un tipo di modello implica il fatto che si ritenga pienamente attendibile la persona alla quale si sta assegnando la delega. Gli utenti che dispongono delle autorizzazioni di scrittura possono modificare tutti i parametri di un modello per creare qualsiasi tipo di certificato desiderato. È consigliabile creare il modello per loro conto, in modo tale che il controllo sui tipi di certificato venga mantenuto esclusivamente all’interno del gruppo Amministratori PKI dell'organizzazione.
  
###### Dettagli relativi all'attività
  
Per ciascun modello di certificato che viene creato o che si desidera attivare nel proprio ambiente, attenersi alle seguenti procedure.
  
**Per creare gruppi di gestione di modelli di certificato**
  
1.  Accedere come membro del gruppo Amministratori PKI dell'organizzazione.
  
2.  Nell’unità organizzativa Gestione modelli certificati, creare un gruppo di protezione globale di dominio chiamato **Gestionemodello*CertTemplateName*** (dove *CertTemplateName* è il nome del modello di certificato da gestire).
  
3.  Caricare lo snap-in **Modelli di certificato** in MMC.
  
4.  Aprire le proprietà del modello richiesto e fare clic sulla scheda **Protezione**.
  
5.  Aggiungere il gruppo Gestione modello *CertTemplateName* con l'autorizzazione di **scrittura**.
  
##### Creazione di gruppi di registrazione modelli di certificato
  
I gruppi di registrazione del modello semplificano la registrazione o la registrazione automatica da parte di utenti o computer per un tipo specifico di certificato, aggiungendoli a un gruppo di protezione o rimuovendoli. È inoltre possibile concedere il controllo sull’appartenenza a questi gruppi al personale addetto all’amministrazione che non dispone dell’autorizzazione per modificare le proprietà dei modelli di certificato.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori PKI dell'organizzazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Snap-in MMC Utenti e computer di Active Directory
  
    -   Snap-in MMC Modello di certificato
  
###### Dettagli relativi all'attività
  
È opportuno creare un gruppo di registrazione per ogni tipo di modello di certificato o, almeno, per tutti quelli che prevedono l'approvazione automatica del certificato. Se si utilizza un processo di registrazione più complesso o manuale per un determinato tipo di certificato, l'uso di gruppi di registrazione del modello potrebbe non essere particolarmente vantaggioso. Laddove si possa usufruire della registrazione automatica, è possibile creare un gruppo distinto che controlli gli utenti e le periferiche che possono eseguire la registrazione automatica del certificato.
  
**Per creare un gruppo di registrazione del modello di certificato**
  
1.  Accedere come membro del gruppo Amministratori PKI dell'organizzazione e aprire lo snap-in MMC Utenti e computer di Active Directory.
  
2.  Nell'unità organizzativa (UO) Registrazione modello di certificato, creare dei gruppi di protezione globali per il dominio denominati:
  
    -   **Registrazionecertificato*CertTemplateName***
  
    -   **Registrazione automaticacertificato*CertTemplateName*** (se richiesto)
  
3.  Caricare lo snap-in Modelli di certificato in MMC.
  
4.  Aprire le proprietà del modello per modificare la protezione.
  
5.  Aggiungere il gruppo Registrazione certificato *CertTemplateName* e concedergli le autorizzazioni di **lettura** e **registrazione**.
  
6.  Aggiungere il gruppo Registrazione automatica certificato *CertTemplateName* e concedergli le autorizzazioni di **lettura**, **registrazione** e **registrazione automatica**.
  
    **Nota:** è possibile delegare il controllo dei gruppi di protezione per consentire al proprietario dell'applicazione di indicare chi è autorizzato alla registrazione del tipo di certificato in oggetto.
  
##### Attivazione della registrazione (o registrazione automatica) di un tipo di certificato per un utente o un computer
  
Questa attività utilizza i gruppi di registrazione per consentire la registrazione manuale oppure per avviare la registrazione automatica di un determinato tipo di certificato per un utente, un computer o un gruppo di protezione comprendente utenti e/o computer.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Autorizzazioni Modifica appartenenza per il gruppo di registrazione dei certificati
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:** Snap-in MMC Utenti e computer di Active Directory
  
    **Nota:** la registrazione automatica deve essere attivata anche nel criterio di dominio per gli utenti o i computer di destinazione. Per altre informazioni, consultare la sezione relativa alla registrazione automatica nel criterio di gruppo nel capitolo 7, "Implementazione dell'infrastruttura a chiave pubblica".
  
###### Dettagli relativi all'attività
  
**Per attivare la registrazione o la registrazione automatica per un utente o un computer**
  
1.  In Utenti e computer di Active Directory, individuare il gruppo di protezione per la registrazione del modello di certificato oppure il gruppo di registrazione automatica corrispondente al tipo di certificato da registrare. È necessario avere eseguito l'accesso come utente con le autorizzazioni **Modifica appartenenza** per il gruppo.
  
2.  Aggiungere l'utente, il computer o il gruppo di protezione al gruppo di protezione del modello selezionato.
  
##### Disattivazione della registrazione (o registrazione automatica) di un tipo di certificato per un utente o computer
  
L’emissione di un certificato a un utente o computer generalmente abilita alcune delle funzionalità del possessore del certificato; potrebbe essere necessario revocare tale funzionalità in un secondo momento.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Autorizzazioni Modifica appartenenza per il gruppo di registrazione dei certificati
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Snap-in MMC Utenti e computer di Active Directory
  
    -   Snap-in MMC Autorità di certificazione
  
###### Dettagli relativi all'attività
  
**Per disattivare la registrazione manuale o automatica per un utente o un computer**
  
1.  In Utenti e computer di Active Directory, individuare il gruppo di protezione per la registrazione del modello di certificato oppure il gruppo di registrazione automatica corrispondente al tipo di certificato da disattivare. È necessario avere eseguito l'accesso come utente con le autorizzazioni **Modifica** **appartenenza** per il gruppo.
  
2.  Rimuovere l’utente, il computer o il gruppo di protezione dal gruppo di protezione del modello selezionato.
  
    **Nota**: per ogni utente certificato da disattivare, è necessario revocare anche il relativo certificato utente.
  
3.  Accedere come membro del gruppo Responsabili certificazione e individuare il certificato esistente dell’utente nel database della CA (console MMC Autorità di certificazione). Per individuare il certificato, nella cartella Certificati emessi della CA, scegliere il menu **Visualizza** e l’opzione **Filtro**.
  
4.  Fare clic sul certificato per selezionarlo e scegliere **Revoca** dal menu **Attività**.
  
5.  Selezionare il codice di motivo appropriato per la revoca. Se il motivo della revoca non è compreso tra quelli predefiniti, selezionare **Non specificato**.
  
    **Importante:** solo il motivo **Sospensione certificato** consente di ripristinare il certificato in seguito. Tutti gli altri motivi determinano la disattivazione permanente del certificato. Tuttavia, non utilizzare il motivo **Sospensione certificato** solo perché consente il ripristino del certificato in un secondo momento. Utilizzare questo codice solo se è effettivamente necessaria una sospensione temporanea del certificato.
  
#### Amministrazione della protezione
  
L'amministrazione della protezione è responsabile del mantenimento di un ambiente informatico protetto. La protezione costituisce una parte importante dell’infrastruttura di un’organizzazione. In un sistema informatico con una protezione debole è probabile che si verifichino violazioni della protezione.
  
##### Controllo richieste in sospeso
  
Le richieste di certificati possono essere inviate alle autorità di certificazione emittenti in qualsiasi momento. La maggior parte dei certificati viene emessa automaticamente sia mediante l’utilizzo di Active Directory come autorità di registrazione (RA) sia mediante l’utilizzo di un gruppo predefinito di firme dell’autorità di registrazione nominata. Se per qualsiasi tipo di certificato è stata impostata l’approvazione manuale da parte del gestore certificati, tali richieste verranno messe in coda fino a quando non verranno approvate o rifiutate.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Responsabili certificazione
  
-   **Frequenza**: Quotidiana
  
-   **Requisiti tecnologici**: Snap-in MMC Autorità di certificazione
  
###### Dettagli relativi all'attività
  
Controllare giornalmente la cartella Richieste per verificare la presenza di richieste in coda. Prima di emettere un certificato, controllare attentamente la richiesta per verificare il richiedente e il contenuto della richiesta. Controllare che contenga il nome del soggetto, il nome del soggetto alternativo, gli utilizzi delle chiavi, i criteri e le estensioni previste. In caso di dubbi, non approvare la richiesta.
  
È inoltre possibile configurare l’autorità di certificazione per l’invio di avvisi di posta elettronica per i diversi eventi, ad esempio l'arrivo di una richiesta in sospeso. Vedere la procedura "Impostazione degli avvisi SMTP per le richieste di certificati in sospeso".
  
**Per controllare le richieste in sospeso**
  
1.  Accedere all’autorità di certificazione emittente come membro del gruppo Responsabili certificazione (è possibile eseguire questa attività in remoto attivando nuovamente la console MMC Autorità di certificazione sulla CA).
  
2.  Aprire la console MMC Autorità di certificazione e aprire la cartella **Richieste**.
  
3.  Per visualizzare i dettagli di qualsiasi richiesta della cartella, fare clic con il pulsante destro del mouse sulla richiesta e scegliere **Visualizza attributi/estensioni** dal sottomenu **Visualizza**.
  
    **Nota**: nella scheda **Attributi** appaiono gli attributi della richiesta ricevuti come parte della richiesta, mentre nella scheda **Estensioni** appaiono le estensioni del certificato che verranno utilizzate nel certificato. Ogni voce di estensione indica se si tratta di un’estensione inclusa nella richiesta, di un valore fornito dal server oppure se è stata definita dal modulo dei criteri dell’autorità di certificazione (quest’ultima origine generalmente indica che si tratta di un’estensione definita nel modello di certificato).
  
    A seconda dei criteri adottati dall’organizzazione, è inoltre possibile che siano presenti altre informazioni relative alla richiesta, ad esempio informazioni date di persona, per telefono, tramite posta elettronica o con altri mezzi.
  
4.  Una volta verificata la validità della richiesta, è possibile approvarla facendo clic con il pulsante destro del mouse sulla richiesta e scegliendo **Emetti** dal sottomenu **Attività**. In caso contrario, è possibile rifiutare la richiesta scegliendo **Nega** dallo stesso sottomenu.
  
##### Rinnovo certificato CA principale
  
È necessario rinnovare regolarmente il certificato CA per consentire alle CA subordinate e ad altre entità finali di registrare i certificati con questa CA. I certificati emessi da questa CA e dalle sue subordinate non possono avere una data di scadenza successiva a quella di questo certificato CA. Altri motivi validi per il rinnovo del certificato della CA sono indicati di seguito.
  
-   Modifica della chiave utilizzata dalla CA in caso di manomissione, reale o presunta
  
-   Aggiunta di criteri dei certificati alla CA (subordinazione qualificata)
  
-   Modifica di percorsi dei punti di distribuzione dell’elenco di certificati revocati (CRL) o di percorsi di accesso alle informazioni dell'autorità (AIA)
  
-   Partizione dell'elenco di revoche di certificati (CRL)
  
È *sempre* necessario modificare la chiave di una CA a ogni rinnovo della CA. Se si desidera effettuare il rinnovo con la stessa chiave, fare riferimento alla procedura "Rinnovo del certificato CA principale con la stessa chiave".
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: Ogni 8 anni
  
-   **Requisiti tecnologici:**
  
    -   Certutil.exe
  
    -   Script MSS
  
    -   Snap-in MMC Autorità di certificazione
  
    -   Editor di testo
  
        **Avviso**: il rinnovo del certificato di una CA principale è un evento significativo. Accertarsi che tutti i proprietari dell’applicazione interessati vengano informati sul nuovo certificato principale nel caso in cui debbano configurare questo nuovo certificato principale nella loro applicazione.
  
###### Dettagli relativi all'attività
  
**Per rinnovare il certificato della CA principale**
  
1.  Accedere alla CA principale come membro del gruppo Administrators locale.
  
2.  Se è necessario cambiare la dimensione della chiave, modificare il file CAPolicy.inf, posizionato nella directory %systemroot%. Modificare il valore del parametro RenewalKeyLength inserendo la dimensione in bit desiderata. La dimensione della chiave deve essere supportata dal CPS (Crypto Service Provider) utilizzato dalla CA. Nell’esempio seguente il valore è 2048.
  
    <codesnippet language displaylanguage containsmarkup="false">\[Certsrv\_Server\] RenewalKeyLength=2048  
```
  
    **Nota:** se è necessario modificare il periodo di validità o i criteri del certificato CA, prima di iniziare questa procedura è necessario specificarlo nel file CAPolicy.inf (in %systemroot%).
  
3.  Aprire lo snap-in MMC Autorità di certificazione. Scegliere **Rinnova certificato CA** dal menu **Attività** dell’oggetto CA. Viene visualizzato un avviso di Servizi certificati che indica che è necessario chiudere la CA per rinnovare il certificato.
  
4.  Selezionare l'opzione **Nuova chiave**. Servizi certificati viene riavviato.
  
5.  Visualizzare il certificato dalla finestra delle proprietà della CA e verificare che la data **Valido dal** corrisponda alla data corrente.
  
6.  Emettere un elenco CRL, quindi copiare il CRL e il nuovo certificato della CA su disco utilizzando i seguenti comandi:
  
    Cscript //job:getcacerts c:\\MSSScripts\\ca\_operations.wsf
  
    Cscript //job:getcrls c:\\MSSScripts\\ca\_operations.wsf
  
7.  Portare il disco nella posizione della CA di emissione. È possibile utilizzare un membro del dominio che abbia il file certutil.exe e gli script forniti con questa soluzione installati. Il server non deve necessariamente essere la CA di emissione.
  
8.  Accedere come membro del gruppo Enterprise PKI Admins ed eseguire gli script seguenti:
  
    Cscript //job: PublishCertstoAD c:\\MSSScripts\\ca\_operations.wsf
  
    Cscript //job: PublishCRLstoAD c:\\MSSScripts\\ca\_operations.wsf
  
    Cscript //job: PublishRootCertstoIIS c:\\MSSScripts\\ca\_operations.wsf
  
    Cscript //job: PublishRootCRLstoIIS c:\\MSSScripts\\ca\_operations.wsf
  
    **Nota:** è consigliabile rinnovare tutte le CA subordinate nello stesso momento, sebbene tale operazione non sia obbligatoria. Vedere "Rinnovo certificato CA di emissione".
  
9.  Eseguire il backup del certificato e della chiave della CA principale. Vedere "Backup di chiavi e certificati CA".
  
10. Eseguire il backup del database dei certificati e dello stato di sistema della CA principale. Vedere "Backup del database autorità di certificazione principale".
  
##### Rinnovo certificato CA di emissione
  
È necessario rinnovare regolarmente il certificato CA per consentire alle entità finali (e alle CA subordinate, se presenti) di registrare i certificati con questa CA. I certificati emessi dalla CA di emissione non possono avere una data di scadenza successiva alla data di scadenza del certificato CA. Altri motivi validi per il rinnovo del certificato della CA sono indicati di seguito.
  
-   Modifica della chiave utilizzata dalla CA in caso di manomissione, reale o presunta
  
-   Aggiunta di criteri dei certificati alla CA (subordinazione qualificata)
  
-   Modifica dei percorsi CDP o AIA
  
-   Partizione del CRL
  
È *sempre* necessario modificare la chiave di una CA a ogni rinnovo della CA. Se si desidera effettuare il rinnovo con la stessa chiave, fare riferimento alla procedura "Rinnovo del certificato CA di emissione con la stessa chiave".
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione:**
  
    -   Amministratori locali sulla CA di emissione
  
    -   Responsabili certificazione sulla CA principale
  
    -   Enterprise PKI Admins
  
-   **Frequenza**: Ogni 4 anni
  
-   **Requisiti tecnologici:**
  
    -   Certutil.exe
  
    -   Script MSS
  
    -   Snap-in MMC Autorità di certificazione
  
    -   Editor di testo
  
        **Importante:** per effettuare con successo il rinnovo del certificato CA e pubblicarlo nell’archivio NTAuth di Active Directory (che identifica la CA come CA dell’organizzazione di grandi dimensioni), è necessario eseguire l’installazione del certificato CA utilizzando un account che sia membro *sia* del gruppo Amministratori PKI dell'organizzazione, sia del gruppo Amministratori. Il primo gruppo dispone dei diritti per pubblicare il certificato nella directory mentre il secondo dispone dei diritti per installare il certificato CA sull’autorità di certificazione.
  
###### Dettagli relativi all'attività
  
**Per rinnovare il certificato della CA di emissione**
  
1.  Accedere alla CA di emissione come membro del gruppo Amministratori locale.
  
2.  Se è necessario cambiare la dimensione della chiave, modificare il file CAPolicy.inf, posizionato nella directory %systemroot%. Modificare il valore del parametro RenewalKeyLength inserendo la dimensione in bit desiderata (la dimensione della chiave deve essere supportata dal CPS utilizzato dalla CA).
  
    <codesnippet language displaylanguage containsmarkup="false">\[Certsrv\_Server\] RenewalKeyLength=2048  
```
  
    **Importante:** se è necessario modificare il periodo di validità o i criteri del certificato CA, prima di iniziare questa procedura è necessario specificarlo nel file CAPolicy.inf (in %systemroot%).
  
3.  Aprire lo snap-in MMC Autorità di certificazione e, nel menu **Attività** dell’oggetto CA, fare clic su **Rinnova certificato CA**.
  
4.  Selezionare l'opzione **Nuova chiave**.
  
5.  Verrà visualizzato un messaggio che chiede di indicare la CA alla quale inviare il rinnovo. Fare clic su **Annulla** per salvare il file di richiesta su disco. Servizi certificati viene riavviato.
  
6.  Copiare il file di richiesta del certificato su disco. La richiesta di certificato viene generata e archiviata nel percorso della cartella condivisa (C:\\CAConfig). Copiare il file *HQ-CA-02.woodgrovebank.com\_Woodgrove Bank Issuing CA 1*.req sul disco (sostituire il testo in corsivo con i dettagli CA appropriati).
  
7.  Mantenere il disco sulla CA principale e accedere come membro del gruppo Responsabili certificazione locale.
  
8.  Nello snap-in MMC Autorità di certificazione, scegliere **Invia nuova richiesta** dal menu **Attività** della CA, quindi inviare la richiesta trasferita dalla CA di emissione (sul disco della richiesta alla CA subordinata).
  
9.  La CA principale richiede l’approvazione manuale di tutte le richieste. Individuare la richiesta nel contenitore **Richieste in sospeso**, verificare che il campo **Nome comune** contenga il nome della CA di emissione e quindi approvare la richiesta.
  
10. Individuare il certificato appena emesso nel contenitore **Certificati emessi** e aprirlo.
  
11. Verificare che le informazioni contenute nel certificato siano corrette, quindi fare clic su **Copia su file** per esportare il certificato in un file. Salvarlo su disco nel formato PKCS\#7, per poterlo ritrasferire alla CA di emissione.
  
12. Accedere alla CA di emissione utilizzando un account membro *sia* del gruppo Amministratori PKI dell'organizzazione, *sia* del gruppo Amministratori locale, quindi inserire il disco.
  
13. Nello snap-in MMC Autorità di certificazione, nel menu **Attività** della CA, fare clic su **Installa certificato**. Installare il certificato della CA di emissione dal disco. La CA verrà riavviata.
  
14. Visualizzare il certificato dalla finestra delle proprietà della CA e verificare che la data **Valido dal** corrisponda alla data corrente.
  
15. Pubblicare il nuovo certificato della CA nella posizione di pubblicazione del punto di distribuzione Web. Vedere la procedura "Pubblicazione del certificato della CA di emissione nel server Web".
  
16. Eseguire il backup del certificato e della chiave della CA di emissione. Vedere la procedura "Backup di chiavi e certificati CA".
  
17. Eseguire il backup del database dei certificati e dello stato di sistema della CA principale. Vedere la procedura "Backup del database autorità di certificazione principale".
  
18. Eseguire il backup del database dei certificati e dello stato di sistema della CA di emissione. Vedere la procedura "Configurazione del backup del database dell'autorità di certificazione emittente". È necessario compiere queste operazioni durante il normale backup quotidiano.
  
##### Rinnovo del certificato CA principale con la stessa chiave
  
È necessario modificare la chiave della CA principale a *ogni* rinnovo del certificato CA pianificato (fare riferimento alla procedura "Rinnovo certificato CA principale"). Potrebbe rivelarsi necessario rinnovare il certificato CA senza cambiare la chiave CA se si desidera cambiare i criteri CA o estendere la durata del certificato conservando però la stessa coppia di chiavi.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Certutil.exe
  
    -   Script MSS
  
    -   Editor di testo
  
###### Dettagli relativi all'attività
  
**Per rinnovare il certificato CA principale senza modificare la chiave CA**
  
-   Seguire la procedura "Rinnovo certificato CA principale", ma quando viene richiesto di effettuare il rinnovo con una nuova chiave, fare clic su **No**. Eventuali modifiche del valore di RenewalKeyLength nel file CAPolicy.inf non hanno alcun effetto.
  
Oltre a **non** effettuare la selezione per generare una nuova chiave, la procedura è la stessa del "Rinnovo certificato CA principale".
  
**Avviso**: il rinnovo del certificato di una CA principale è un evento significativo. Accertarsi che tutti i proprietari dell’applicazione interessati vengano informati sul nuovo certificato principale nel caso in cui debbano configurare questo nuovo certificato principale nelle proprie applicazioni.
  
##### Rinnovo del certificato CA di emissione con la stessa chiave
  
È necessario cambiare la chiave di una CA a *ogni* rinnovo programmato del certificato CA (vedere "Rinnovo certificato CA di emissione". Tuttavia, potrebbe rivelarsi necessario rinnovare il certificato CA senza cambiare la chiave CA, ad esempio se si desidera cambiare i criteri CA o estendere la durata del certificato conservando però la stessa coppia di chiavi.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Certutil.exe
  
    -   Script MSS
  
    -   Snap-in MMC Autorità di certificazione
  
    -   Editor di testo
  
###### Dettagli relativi all'attività
  
**Per rinnovare il certificato della CA di emissione senza modificare la chiave CA**
  
-   Seguire la procedura per il rinnovo del certificato della CA principale, ma quando viene richiesto di effettuare il rinnovo con una nuova chiave, fare clic su **No**. Eventuali modifiche del valore di RenewalKeyLength nel file CAPolicy.inf non hanno alcun effetto.
  
Oltre a **non** effettuare la selezione per generare una nuova chiave, la procedura è la stessa del "Rinnovo certificato CA di emissione".
  
##### Pubblicazione elenco CRL non in linea e certificato CA
  
È necessario pubblicare l’elenco di revoche di certificati (CRL) di una CA non in linea in un percorso in linea in modo tale che gli utenti dei certificati possano controllare lo stato di revoca dell’intera catena CA.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione:**
  
    -   Amministratori locali sulla CA
  
    -   Enterprise PKI Publishers
  
-   **Frequenza**: Ogni sei mesi o come richiesto
  
-   **Requisiti tecnologici:**
  
    -   Certutil.exe
  
    -   Script MSS
  
###### Dettagli relativi all'attività
  
**Per pubblicare l'elenco CRL principale non in linea in Active Directory e nell'URL Web**
  
1.  Eseguire l'accesso alla CA principale in qualità di membro del gruppo Amministratori CA.
  
2.  Emettere un elenco CRL, quindi copiare il CRL e il nuovo certificato della CA su disco utilizzando i seguenti comandi:
  
    Cscript //job:getcacerts c:\\MSSScripts\\ca\_operations.wsf
  
    Cscript //job:getcrls c:\\MSSScripts\\ca\_operations.wsf
  
3.  Portare il disco nella posizione della CA di emissione. Non è necessario che il server sia la CA di emissione, è sufficiente che sia un membro del dominio e che siano installati certutil.exe e gli script MSS.
  
4.  Accedere come membro del gruppo Autori PKI dell'organizzazione ed eseguire gli script seguenti:
  
    Cscript //job: PublishCertstoAD c:\\MSSScripts\\ca\_operations.wsf
  
    Cscript //job: PublishCRLstoAD c:\\MSSScripts\\ca\_operations.wsf
  
    Cscript //job: PublishRootCertstoIIS c:\\MSSScripts\\ca\_operations.wsf
  
    Cscript //job: PublishRootCRLstoIIS c:\\MSSScripts\\ca\_operations.wsf
  
##### Imposizione dell’emissione di un elenco CRL in linea
  
Gli elenchi CRL di una CA dell’organizzazione di grandi dimensioni vengono emessi e pubblicati automaticamente; normalmente l’imposizione dell’emissione di un elenco CRL in linea non è richiesta. Tuttavia, l'imposizione dell’emissione di un elenco CRL in linea può essere necessaria in alcuni casi critici, ad esempio quando tutti i certificati emessi dalla CA vengono revocati ed è necessario pubblicare un nuovo elenco CRL nel più breve tempo possibile.
  
**Nota:** non è possibile trasferire l'elenco CRL ai client. Questi ultimi conservano le copie memorizzate nella cache fino alla scadenza. Dal momento della pubblicazione del nuovo elenco CRL, tuttavia, i client che richiedono l'elenco CRL riceveranno quello più aggiornato, ritardi di distribuzione permettendo.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: Snap-in MMC Autorità di certificazione
  
###### Dettagli relativi all'attività
  
**Per emettere e pubblicare l’elenco CRL della CA non in linea nella Active Directory**
  
1.  Accedere alla CA come membro del gruppo Amministratori CA e caricare lo snap-in MMC Autorità di certificazione.
  
2.  Fare clic su **Pubblica** per emettere il nuovo elenco CRL dal menu **Attività** della cartella Certificati revocati.
  
3.  Selezionare **Nuovo CRL** per emettere un elenco CRL di base oppure **Delta CRL** **solo** nel caso di un nuovo elenco Delta CRL.
  
##### Pubblicazione del certificato della CA di emissione sul server Web
  
Il certificato della CA di emissione deve essere pubblicato nel percorso HTTP AIA.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Autori PKI dell'organizzazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Script MSS
  
    -   Certutil.exe
  
###### Dettagli relativi all'attività
  
Tecnicamente, è possibile configurare la CA affinché la pubblicazione avvenga direttamente nella cartella del server Web. Tuttavia, questo metodo non sempre si rivela attuabile, per ragioni di protezione e di connettività di rete. Il metodo descritto di seguito utilizza una semplice tecnica di copia del file ma può essere adattato alla maggior parte delle configurazioni.
  
**Nota:** questo metodo non è adatto per pubblicare direttamente in un server Web connesso a Internet in quanto utilizza una connettività di rete diretta e la condivisione di file SMB (Server Message Block), generalmente bloccata dai firewall. Per pubblicare in un server Internet, utilizzare un percorso di pubblicazione intermedio, quindi utilizzare il metodo standard di pubblicazione protetta del contenuto nel server Web. È necessario tenere conto della latenza aggiuntiva implicita in questo metodo.
  
Il certificato CA viene aggiornato molto raramente, quindi è possibile pubblicare manualmente in AIA ogni volta che il certificato CA viene rinnovato.
  
**Per pubblicare il certificato della CA di emissione**
  
1.  Accedere alla CA di emissione con un account che disponga dell’autorizzazione in scrittura alla cartella pubblicata del server Web.
  
2.  Se il server Web è un server remoto, verificare che la cartella sia condivisa. Registrare il percorso UNC (Universal Naming Convention) della cartella condivisa.
  
3.  Se il server Web è lo stesso server della CA, registrare il percorso locale della cartella.
  
4.  Aggiornare il parametro WWW\_REMOTE\_PUB\_PATH in C:\\MSSScripts\\PKIParams.vbs in modo che corrisponda al percorso di destinazione della cartella server Web (l'impostazione predefinita è il percorso locale C:\\CAWWWPub).
  
5.  Eseguire il seguente comando per pubblicare il certificato CA nel server Web:
  
    Cscript //job:PublishIssCertsToIIS C:\\MSSScripts\\CA\_Operations.wsf
  
##### Pubblicazione degli elenchi CRL della CA di emissione nel server Web
  
È necessario pubblicare gli elenchi CRL della CA di emissione nel percorso del punto di distribuzione CRL HTTP.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici:**
  
    -   Script MSS
  
    -   Certutil.exe
  
    -   Servizio Utilità di pianificazione di Windows
  
    -   SchTasks.exe
  
###### Dettagli relativi all'attività
  
Tecnicamente, è possibile configurare la CA affinché la pubblicazione avvenga direttamente nella cartella del server Web. Tuttavia, questo metodo non sempre si rivela attuabile, per ragioni di protezione e di connettività di rete. Il metodo descritto di seguito utilizza una semplice tecnica di copia del file ma può essere adattato alla maggior parte delle configurazioni.
  
**Nota:** questo metodo non è adatto per pubblicare direttamente in un server Web connesso a Internet in quanto utilizza una connettività di rete diretta e la condivisione di file SMB (Server Message Block), generalmente bloccata dai firewall. Per pubblicare in un server Internet, utilizzare un percorso di pubblicazione intermedio, quindi utilizzare il metodo standard di pubblicazione protetta del contenuto nel server Web. È necessario tenere conto della latenza aggiuntiva implicita in questo metodo e del possibile impatto sull'attualità degli elenchi CRL.
  
La CA di emissione rilascia frequentemente (quotidianamente o ogni ora nel caso di Delta CRL) elenchi CRL. Quindi, è necessario adottare un metodo automatico di replica degli elenchi CRL sul server Web.
  
**Per automatizzare la pubblicazione di CRL**
  
1.  Accedere alla CA di emissione con un account membro del gruppo Administrators locale.
  
2.  Controllare che la cartella del server Web sia accessibile, come condivisione remota o percorso locale, da questo server.
  
3.  Se il server Web è remoto, concedere all’account del computer della CA di emissione l’accesso in scrittura alla cartella del file system (accesso **Modifica**) e alla condivisione (accesso **Cambia**) corrispondente alla cartella pubblicata del server Web. Se il server Web è membro di un insieme di strutture, è possibile utilizzare il gruppo Autori certificazione per assegnare l'accesso e garantire che qualsiasi CA dell'organizzazione disponga delle autorizzazioni necessarie per pubblicare i certificati e i CRL in questa cartella. Non è necessario modificare le autorizzazioni del server Web. Vedere la sezione relativa alla configurazione di IIS per la pubblicazione AIA e CDP nel capitolo 6.
  
4.  Creare un processo programmato di copia degli elenchi CRL mediante il seguente comando:
  
    schtasks /create /tn "Publish CRLs" /tr "cscript.exe  
    //job:PublishIssCRLsToIIS \\"C:\\MSSScripts\\CA\_Operations.wsf\\""  
    /sc Hourly /ru "System"
  
    Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe.
  
    **Nota:** questa procedura consente di creare un processo programmato, che avverrà ogni ora, per la pubblicazione di CRL dalla CA al server Web. Tale intervallo è sufficiente per una pianificazione che preveda la pubblicazione di Delta CRL giornalmente o anche due volte al giorno. Se la pianificazione della pubblicazione CRL avviene con maggiore frequenza, è possibile eseguire il processo di copia a intervalli più brevi. Indicativamente, la pianificazione del processo di copia dovrebbe rappresentare un valore compreso tra il cinque e il dieci percento della pianificazione dei Delta CRL.
  
#### Gestione dell'archiviazione
  
La gestione dell'archiviazione si occupa dell'archiviazione dei dati sia interna che esterna per il ripristino dei dati e l'archiviazione cronologica. Il team di gestione dell'archiviazione dovrà garantire la protezione fisica dei backup e degli archivi. Obiettivo della gestione dell'archiviazione è definire, tenere traccia e mantenere dati e risorse di dati nell'ambiente di produzione IT.
  
##### Configurazione del backup del database dell’autorità certificazione emittente
  
L'obiettivo consiste nell'eseguire una copia di backup delle chiavi private e dei certificati della CA, del database dei certificati e delle informazioni di configurazione di Servizi certificati. Queste ultime includono dati sulla configurazione del sistema operativo e altre informazioni sullo stato sulle quali si basa la CA.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici:**
  
    -   Utilità di backup di Windows
  
    -   Sistema di backup organizzativo
  
    -   Servizio Utilità di pianificazione di Windows
  
    -   SchTasks.exe
  
###### Dettagli relativi all'attività
  
Questa attività configura un processo pianificato per eseguire un backup notturno dello stato del sistema del server CA. Per questa procedura, si presume l'esistenza di un sistema di backup dei server; il processo di backup produce un file di backup che può essere sottoposto a backup da parte del relativo sistema dell'organizzazione. Può trattarsi di un dispositivo di backup in rete o locale. Questa soluzione prevede, inoltre, che il sistema di backup del server dell'organizzazione esegua la copia dei dischi del server della CA di notte.
  
**Nota:** se si utilizza un modulo HSM (Hardware Security Module), questa procedura è in grado di copiare il materiale della chiave crittografata, a seconda del funzionamento del modulo, ma tale backup risulterebbe inutilizzabile in un computer ripristinato privo di un identico modulo HSM e delle relative chiavi di accesso. Seguire le istruzioni del produttore del modulo HSM per le operazioni di backup e protezione dei dati delle chiavi e delle chiavi di accesso.
  
**Per configurare il backup della CA**
  
1.  Creare una directory nella quale archiviare i file di backup temporanei (ad esempio, C:\\CABackup) e proteggere tale directory con il comando seguente:
  
    cacls c:\\CABackup /G system:F administrators:F "Backup Operators":C "CA Backup Operators":C
  
    Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe.
  
2.  Se per memorizzare il file di backup si sceglie un'altra cartella, è necessario aggiornare le relative impostazioni in pkiparams.vbs. Modificare nel modo desiderato il percorso visualizzato nella riga successiva.
  
    <codesnippet language displaylanguage containsmarkup="false">CONST SYSSTATE\_BACKUP\_PATH = "C:\\CABackup"   'path used by NTBackup  
```
  
    **Nota:** dal momento che la stessa funzione di script viene utilizzata per eseguire il backup delle CA non in linea e in linea, se si utilizzano percorsi differenti per le diverse CA è necessario effettuare copie separate degli script.
  
3.  Creare un processo pianificato che venga eseguito di notte immettendo il seguente comando. Il comando imposta l’esecuzione dell’attività alle 2.00 di ogni notte.
  
    SCHTASKS /Create /RU system /SC Daily /TN "CA Backup" /TR "cscript.exe //job:BackupCADatabase \\"C:\\MSSScripts\\ca\_operations.wsf\\"" /ST 02:00
  
    Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe.
  
    **Nota:** la barra rovesciata seguita da virgolette (\\") visualizzata ai lati del nome dello script "C:\\MSSScripts\\ca\_operations.wsf"è necessaria solo nel caso di spazi all'interno del nome del file o del percorso dello script. La barra rovesciata viene utilizzata per evitare le virgolette ai lati del nome dello script in modo che il nome e il percorso dello script vengano memorizzati come unico parametro della riga di comando del processo schtasks e non vengano divisi in più parti. Questi caratteri possono essere omessi se nel nome del percorso non sono presenti spazi.
  
4.  Configurare il sistema di backup del server dell'organizzazione in modo che ogni notte copi il contenuto della cartella di backup temporanea (C:\\CABackup) in un supporto rimovibile. Se possibile, impostare uno script di controllo condizionale preventivo per verificare l'esistenza del file di blocco BackupRunning.lck, memorizzato nella cartella di backup temporanea, che viene creato dal file dello script di backup durante l'esecuzione. Se questo file esiste, significa che il backup precedente non è riuscito oppure è ancora in corso. In alternativa, fare in modo che il sistema dell'organizzazione esegua lo script di backup della CA prima del backup vero e proprio.
  
    **Nota:** quando viene eseguito, lo script di backup BackupCADatabase cerca il file di blocco. Se questo esiste, inserisce l'errore seguente nel registro applicazioni:
  
    Source: CA Operations
  
    ID evento: 30
  
    Tipo evento: Errore
  
    Il backup CA potrebbe non essere avviato se è ancora presente il file di blocco C:\\CABackup\\BackupRunning.lck di un processo precedente. Il backup precedente potrebbe essere ancora in corso.
  
    Se il sistema di backup dei server dell'organizzazione non può eseguire controlli preliminari oppure non può eseguire gli script, pianificare l’inizio del backup in un orario adatto dopo l’avvio del backup dello stato del sistema. Per stimare il tempo necessario, eseguire il backup dello stato del sistema (con la **verifica** abilitata) sul server con Servizi certificati chiuso. La disattivazione della CA impedisce che i registri della CA vengano troncati a causa del backup di prova. In tal modo, si dovrebbe ottenere la copia di circa 500 MB dei dati relativi allo stato del sistema. Prendere nota del tempo necessario per il processo, quindi utilizzare la seguente equazione per calcolare approssimativamente il tempo previsto per il backup di un database CA e dello stato del sistema:
  
    Ttotal = TSysState x (500 + (Nusers x NCerts x 20KB x 2)) ÷ 500
  
    Con questa equazione si considerano cinque certificati per ogni utente e computer, per ogni anno, memorizzati per cinque anni nel database prima dell'archiviazione. Se si assegnano 20 kilobyte (KB) per certificato, il risultato del calcolo è di 1 MB di archiviazione per ogni utente. Se il tempo necessario per il solo backup dello stato del sistema è di 10 minuti, assegnare 70 minuti per una CA con 3.000 utenti. Queste cifre sono, tuttavia, approssimative; in alternativa, assegnare 1 GB ogni 50.000 certificati.
  
    **Nota:** se si utilizza l'archiviazione delle chiavi, i requisiti per l'archiviazione dei certificati sono maggiori per i certificati con chiavi archiviate. In questo caso, assegnare altri 10 KB per certificato (anche se potrebbe essere necessaria un'archiviazione aggiuntiva se si dispone di molti agenti di ripristino chiavi configurati sulla CA).
  
5.  Conservare il supporto di backup in maniera adeguata.
  
    **Avviso:** questi dati di backup sono estremamente riservati, poiché contengono i dati della chiave privata della CA. È necessario trasferire e archiviare i dati con la stessa attenzione e protezione riservata alla CA. Archiviare i dati del backup in una sede fisica diversa da quella della CA. In questo modo sarà possibile ripristinare la CA nel caso in cui tutte le attrezzature informatiche subiscano danni irreversibili o diventino inaccessibili.
  
##### Configurazione del backup del database autorità di certificazione principale
  
Scopo di questa attività è disporre il backup delle chiavi private e dei certificati della CA, del database dei certificati e delle informazioni di configurazione di Servizi certificati. Queste ultime includono dati sulla configurazione del sistema operativo e altre informazioni sullo stato sulle quali si basa la CA.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici:**
  
    -   Utilità di backup di Windows
  
    -   Supporti rimovibili (quale CD-RW o nastro)
  
###### Dettagli relativi all'attività
  
I certificati emessi dalla CA principale non sono mai numerosi e pertanto anche la dimensione dei dati che contengono non è eccessiva. I dati non cambiano frequentemente, a volte solo a distanza di anni. La procedura è identica per qualsiasi altra CA non in linea, ad esempio nel caso in cui sia stata scelta una CA intermediaria non in linea.
  
La CA principale non è in linea, quindi richiede determinati tipi di dispositivi locali di backup (quale unità a nastro o CD scrivibile) sui quali archiviare il file di backup.
  
**Avviso:** se si utilizza un HSM, questa procedura può eseguire il backup dei dati relativi alle chiavi crittografate (a seconda del funzionamento di HSM) ma, generalmente, non è utilizzabile su un computer ripristinato senza un HSM identico e le stesse chiavi di accesso. Seguire le istruzioni del produttore del modulo HSM per le operazioni di backup e protezione dei dati delle chiavi e delle chiavi di accesso.
  
**Per configurare il backup della CA**
  
1.  Creare una directory nella quale archiviare i file di backup (C:\\CABackup) e proteggere la directory con il comando seguente:
  
    cacls c:\\CABackup /G system:F administrators:F "Backup Operators":C "CA Backup Operators":C
  
    Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe.
  
2.  Se per memorizzare il file di backup si sceglie un'altra cartella, è necessario aggiornare le relative impostazioni nello script pkiparams.vbs. Modificare nel modo desiderato il percorso visualizzato nella riga successiva.
  
    <codesnippet language displaylanguage containsmarkup="false">CONST SYSSTATE\_BACKUP\_PATH = "C:\\CABackup"   'path used by NTBackup   
```
  
##### Backup del database autorità di certificazione principale
  
Lo scopo di questa attività consiste nel creare copie di backup dei certificati e delle chiavi private della CA, del database dei certificati e delle informazioni sulla configurazione di Servizi certificati. Queste ultime includono dati sulla configurazione del sistema operativo e altre informazioni sullo stato sulle quali si basa la CA.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Operatori di backup CA
  
-   **Frequenza:** Ogni volta che viene emesso o revocato un nuovo certificato
  
-   **Requisiti tecnologici:**
  
    -   Utilità di backup di Windows
  
    -   Supporti rimovibili (quale CD-RW o nastro)
  
###### Dettagli relativi all'attività
  
I certificati emessi dalla CA principale non sono mai numerosi e pertanto anche la dimensione dei dati che contengono non è eccessiva. I dati non cambiano frequentemente, a volte solo a distanza di anni. La procedura è identica per qualsiasi altra CA non in linea, ad esempio nel caso in cui sia stata scelta una CA intermediaria non in linea.
  
La CA principale non è in linea, quindi richiede determinati tipi di dispositivi locali di backup (quale unità nastro o CD scrivibile).
  
**Avviso:** se si utilizza un HSM, questa procedura può eseguire il backup dei dati relativi alle chiavi crittografate (a seconda del funzionamento di HSM) ma, generalmente, non è utilizzabile su un computer ripristinato senza un HSM identico e le stesse chiavi di accesso. Seguire le istruzioni del produttore del modulo HSM per le operazioni di backup e protezione dei dati delle chiavi e delle chiavi di accesso.
  
**Per effettuare il backup della CA principale**
  
1.  Utilizzare il seguente comando per eseguire il backup dei dati della CA in un file temporaneo:
  
    cscript //job:BackupCADatabase C:\\MSSScripts\\ca\_operations.wsf
  
2.  Questo comando crea un file di backup, CABackup.bkf, nel percorso scelto in precedenza (il percorso predefinito è C:\\CABackup). Copiare il file su un supporto rimovibile e conservare tale supporto in modo adeguato.
  
    **Avviso:** questi dati di backup sono estremamente riservati, poiché contengono i dati della chiave privata della CA. È necessario trasferire e archiviare i dati con la stessa attenzione e protezione riservata alla CA. Archiviare i dati del backup in una sede fisica diversa da quella della CA. In questo modo sarà possibile ripristinare la CA nel caso in cui tutte le attrezzature informatiche subiscano danni irreversibili o diventino inaccessibili.
  
##### Backup di chiavi e certificati CA
  
Il backup delle chiavi e dei certificati CA dovrebbe essere eseguito indipendentemente dal database dei certificati. È possibile che ai certificati e alle chiavi private CA venga richiesto di firmare un elenco CRL o un certificato nel caso in cui il server CA non funzioni e non possa essere ripristinato in tempi sufficienti.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Operatori di backup CA
  
-   **Frequenza**: Annuale oppure ogni volta che il certificato CA viene rinnovato (in base a quale evento si verifica per primo)
  
-   **Requisiti tecnologici:**
  
    -   Certutil.exe
  
    -   Script MSS
  
###### Dettagli relativi all'attività
  
I certificati e le chiavi CA occupano solo pochi kilobyte di archiviazione e quindi possono essere salvati su un disco. Questa attività si riferisce alla CA principale e a tutte le CA intermedie ed emittenti dell'organizzazione. Se si esegue un backup delle chiavi con archiviazione a lungo termine, ad esempio su CD o DVD, non è necessario eseguire il backup ogni anno. Se si utilizzano supporti magnetici quali dischi floppy o nastri, è necessario eseguire il backup delle chiavi e dei certificati ogni anno e ad ogni rinnovo di un certificato della CA. Il segnale registrato sui supporti magnetici si deteriora con il tempo, in particolare se questi sono esposti a campi elettrici. Sebbene il processo di deterioramento dei supporti magnetici richieda anni perché si arrivi alla totale impossibilità di leggere i dati contenuti, è comunque consigliabile cautelarsi il più possibile.
  
**Avviso:** se si utilizza un HSM, questa procedura non funziona come indicato. Seguire le istruzioni del produttore del modulo HSM per le operazioni di backup e protezione dei dati delle chiavi e delle chiavi di accesso.
  
**Per esportare su disco i certificati e le chiavi**
  
1.  Eseguire il comando:
  
    cscript //job:BackupCAKeys c:\\MMSScripts\\ca\_operations.wsf
  
    Eseguire almeno due backup separati su dischi diversi (i dischi non sono sempre affidabili al cento per cento). Etichettare e datare in modo chiaro i dischi, considerando quanto tempo può trascorrere prima che debbano essere utilizzati.
  
    Questo script utilizza certutil.exe per esportare i certificati e le chiavi CA su un file PKCS\#12 (P12) nel percorso seguente:
  
    A:\\CAKeyBackup\\*CAComputerName*\\*yymmdd\_hhmm*\\CA Common Name.p12
  
    *CAComputerName* è il nome host della CA, mentre *yymmdd\_hhmm* rappresenta la data e l'ora del backup.
  
2.  Quando viene richiesto, inserire una password.
  
    **Importante:** registrare e conservare la password in luogo diverso, ma ugualmente sicuro, rispetto alle copie di backup delle chiavi. La registrazione della password deve indicare chiaramente il backup (etichetta del disco, data e nome della CA) al quale si riferisce. Possono trascorrere mesi o anni prima di dover riutilizzare le chiavi ed è improbabile che qualcuno possa ricordare la password utilizzata. Assicurarsi di distruggere tutte le altre registrazioni della password. Non utilizzare una password conosciuta dallo staff dell’amministrazione.
  
3.  Conservare il disco in modo appropriato. Analogamente a quanto avviene con i backup del database della CA, è necessario garantire la massima protezione anche per i backup delle chiavi. Conservare almeno due copie di backup dei certificati e delle chiavi in due luoghi protetti e diversi, ad esempio due casseforti.
  
##### Test dei backup per database autorità di certificazione
  
Controllare i backup della CA per essere sicuri che la tecnologia ed il processo di siano stati eseguiti in modo corretto.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Privilegi di Amministratori locali o di Operatori backup sul computer di prova
  
-   **Frequenza:**
  
    -   Prima che la CA diventi operativa
  
    -   Ogni mese
  
    -   Collaudare nuovamente quando si apportano modifiche alla tecnologia o al processo di backup
  
-   **Requisiti tecnologici:**
  
    -   Utilità di backup di Windows
  
    -   Sistema di backup organizzativo
  
    -   Certutil.exe
  
    -   Cipher.exe
  
###### Dettagli relativi all'attività
  
È necessario ripristinare il backup dello stato del sistema su un sistema con la stessa configurazione del disco. Ad esempio, Windows deve essere installato nello stesso percorso di directory del sistema di cui è stato effettuato il backup e la configurazione dell’unità per l’archiviazione dei file di Windows (quali file di paging), i registri e il database della CA devono essere uguali a quelli della CA di cui è stato eseguito il backup.
  
**Importante:** il server di test ripristinato non deve essere mantenuto in linea dal punto in cui il file di backup dello stato del sistema è stato ripristinato dal supporto di backup e certamente prima dell’avvio del ripristino dello stato del sistema. Questa separazione serve a impedire che le chiavi CA ripristinate vengano esposte senza motivo, ma anche che si verifichino conflitti di indirizzi IP e nomi duplicati tra il server originale e quello di test.
  
**Avviso:** se si utilizza un HSM, questa procedura non è sufficiente per ripristinare completamente la CA. A seconda del funzionamento del modulo HSM, il computer ripristinato non è utilizzabile senza lo stesso HSM e le stesse chiavi di accesso HSM. Questa situazione può essere sufficiente per un test normale, ma è consigliabile eseguire regolarmente un ripristino completo con il ripristino HSM per essere sicuri che le procedure e la tecnologia di backup funzionino correttamente. Per eseguire il backup e le procedure di recupero e protezione dei dati delle chiavi e delle chiavi di accesso, seguire le istruzioni del fornitore.
  
**Per ripristinare la CA**
  
1.  Ripristinare il file di backup dello stato del sistema dal supporto di backup nella cartella C:\\CABackup.
  
2.  Eseguire l’utilità di backup di Windows e selezionare il file di backup ripristinato in C:\\CABackup. È necessario essere un membro di un gruppo che dispone delle autorizzazioni di backup e ripristino sulla macchina (ad esempio Operatori di backup CA, Operatori di backup o Amministratori).
  
3.  Fare clic su **Ripristina**.
  
4.  Riavviare il sistema.
  
5.  Verificare che tutte le operazioni vengano eseguite come previsto.
  
6.  Alla fine del test, eliminare in maniera sicura tutti i dati del server di prova (o almeno le chiavi).
  
Se si sceglie di eliminare solo le chiavi, rimuovere innanzitutto i contenitori della chiave CA, quindi cancellare in modo sicuro le parti del disco non allocate. Per eseguire questa operazione, è necessario essere un membro del gruppo Amministratori locale.
  
**Per eliminare in modo sicuro le chiavi CA ripristinate**
  
1.  Elencare i contenitori della chiave sul server di prova con il comando riportato di seguito:
  
    Certutil –chiave
  
2.  Annotare tutti i contenitori corrispondenti al nome della CA (inclusi quelli con un suffisso di indice), ad esempio, "Woodgrove Bank Issuing CA 1(1)".
  
3.  Eliminare tutti i contenitori della chiave dal server di prova con il comando riportato di seguito, sostituendo KeyContainerName con i valori ottenuti nella procedura precedente:
  
    Certutil –delkey *KeyContainerName*
  
4.  Cancellare in maniera sicura lo spazio dell'unità non allocato per garantire la completa eliminazione dei dati della chiave dal disco. Nel comando riportato di seguito, il percorso %allusersprofile% viene utilizzato in modo tale che il comando cipher possa operare sull’unità nella quale sono presenti i dati relativi alle chiavi.
  
    Cipher /W:%AllUsersProfile%
  
##### Test dei backup per chiave autorità di certificazione
  
Controllare i backup delle chiavi CA regolarmente per essere sicuri che siano validi, nel caso dovessero servire.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali su computer di prova
  
-   **Frequenza:**
  
    -   Attività di impostazione (prima che la CA diventi operativa)
  
    -   Ogni sei mesi
  
-   **Requisiti tecnologici:**
  
    -   Certutil.exe
  
    -   Cipher.exe
  
###### Dettagli relativi all'attività
  
È possibile installare le chiavi e i certificati CA in qualsiasi sistema. Tuttavia, considerata la natura altamente sensibile di queste chiavi, è consigliabile che il sistema sia affidabile e non in linea, soprattutto nel caso di chiavi della CA principale non in linea. Per garantire che tutte le tracce dei dati delle chiavi vengano rimosse dal computer, creare un account utente locale separato e temporaneo dedicato a questa operazione (è possibile utilizzare qualsiasi nome per questo account).
  
**Avviso:** se si utilizza un HSM, questa procedura non funziona come indicato. Seguire le istruzioni del produttore del modulo HSM per le operazioni di backup, ripristino e protezione dei dati della chiave e delle chiavi di accesso.
  
**Per ripristinare le chiavi CA**
  
1.  Controllare che il computer sia disconnesso dalla rete. Accedere come membro del gruppo Amministratori locale, quindi creare l’account utente locale TestCAKeys.
  
2.  Accedere utilizzando l’account TestCAKeys.
  
3.  Inserire il disco contenente il backup delle chiavi CA da controllare.
  
4.  Utilizzare Esplora risorse per individuare il file della chiave P12, quindi fare doppio clic sul file. Verrà avviata l'Importazione guidata certificati.
  
5.  Quando viene richiesto, inserire la password. Non selezionare le caselle di controllo per aggiungere maggiore protezione alle chiavi o per renderle esportabili.
  
6.  Fare clic su **Mettere tutti i certificati nel seguente archivio**, quindi scegliere **Sfoglia** e infine **Archivio** **personale** come posizione nella quale ripristinare le chiavi CA.
  
7.  Aprire lo snap-in MMC Certificati e scegliere l’archivio personale. Individuare il certificato CA della CA ripristinata, quindi aprirlo per verificare di possedere la chiave privata corrispondente. L'indicazione dovrebbe essere visualizzata nella parte inferiore della scheda **Generale**.
  
**Per verificare le chiavi ripristinate**
  
1.  Ottenere un elenco CRL o un certificato emesso dalla CA che si sta verificando.
  
2.  A seconda della scelta di un CRL o di un certificato nel passaggio precedente, eseguire uno dei comandi seguenti, sostituendo *CRLFileName* o *CertFileName* con il nome del file ottenuto nel passaggio 1:
  
    Certutil -sign *CRLFileName.crl NewCRL.crl*
  
    Certutil -sign *CertFileName.cer NewCertFile.cer*
  
3.  Quando viene richiesto, selezionare il certificato CA importato nel passaggio precedente come certificato con firma.
  
4.  Eseguire il comando certutil riportato di seguito per verificare che l'operazione di firma sia riuscita e che il risultato sia simile al seguente:
  
    C:\\CA&gt;Configcertutil -sign "Woodgrove Bank Issuing CA 1.crl" "Woodgrove Bank Issuing CA 1xxs.crl"
  
    ThisUpdate: 10/02/03 22:52
  
    NextUpdate: 25/02/03 15:11
  
    CRL Entries: 0
  
    Signing certificate Subject:
  
        CN=Woodgrove Bank Issuing CA 1
  
        DC=woodgrovebank,DC=com
  
    Output Length = 970
  
    CertUtil: -sign command completed successfully.
  
È necessario eliminare le chiavi dal sistema di test.
  
**Per eliminare le chiavi dal sistema**
  
1.  Accedere come membro del gruppo Amministratori locale ed eliminare il profilo utente dell’account TestCAKeys, utilizzando **Proprietà avanzate** in Risorse del computer.
  
2.  Eliminare l’account TestCAKeys.
  
3.  Cancellare in maniera sicura le aree del disco non allocate per rimuovere permanentemente le tracce delle chiavi utilizzando il seguente comando:
  
    Cipher /W:%AllUsersProfile%
  
    **Nota:** specificando %allusersprofile% come percorso si garantisce che Cipher.exe operi sull’unità contenente i profili utente. Verrà cancellata qualsiasi informazione presente nell’intera unità e non solo il percorso indicato.
  
##### Archiviazione di dati di controllo della protezione da una CA
  
Archiviare e memorizzare i registri di controllo in base ai requisiti legali o normativi o ai criteri di protezione interni.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione:**
  
    -   CA Auditors
  
    -   Amministratori locali sulla CA
  
-   **Frequenza:**
  
    -   Mensile (CA di emissione)
  
    -   Ogni sei mesi (CA principale)
  
-   **Requisiti tecnologici:**
  
    -   Visualizzatore eventi
  
    -   Supporti rimovibili (quale CD-RW o nastro)
  
###### Dettagli relativi all'attività
  
**Per archiviare il registro eventi di protezione**
  
1.  Accedere al server come membro del gruppo Controllori CA e del gruppo Amministratori locale (creare un account membro di entrambi i gruppi).
  
2.  Aprire Visualizzatore eventi facendo clic su **Start**, **Tutti i programmi** e **Strumenti di amministrazione**.
  
3.  Fare clic sulla cartella del registro di protezione per selezionarla.
  
4.  Fare clic con il pulsante destro del mouse sulla cartella e selezionare **Salva registro con nome** dal menu a discesa.
  
5.  Salvare il registro in un file temporaneo.
  
6.  Copiare su un supporto rimovibile (CD-RW), quindi eliminare il file temporaneo.
  
##### Esportazione di un modello di certificato da Active Directory
  
È possibile salvare le definizioni del modello di certificato della directory in modo che possano essere ripristinate in futuro senza dover eseguire un ripristino completo della directory.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Utenti di dominio
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Idifde.exe
  
    -   Snap-in MMC Modelli di certificato
  
###### Dettagli relativi all'attività
  
Questa procedura descrive un modo semplice per esportare su file un oggetto Active Directory di modello di certificato. L'oggetto può essere importato di nuovo nella directory, se necessario. Questo metodo salva solo le informazioni LDAP dell’oggetto modello. Altre informazioni, ad esempio le informazioni sulla protezione (quali proprietà e autorizzazioni) non vengono mantenute utilizzando questo processo.
  
**Nota:** l'unico modo completamente supportato per eseguire il backup e il ripristino degli oggetti Active Directory consiste nell’utilizzare un metodo di backup di directory dedicato come il backup dello stato del sistema di Windows. Tuttavia, il ripristino di una versione precedente di un oggetto modificato richiede un ripristino autorevole di Active Directory che è una procedura complessa. Questa procedura descrive un modo semplice per eseguire il backup e il ripristino di un’istantanea di un oggetto modello di certificato.
  
**Per esportare un oggetto modello di certificato**
  
1.  Determinare il nome del modello di cui si desidera eseguire il backup. Non deve trattarsi necessariamente dello stesso nome di modello visualizzato. Esaminare le proprietà del modello nella scheda **Generale** del modello (utilizzando lo snap-in MMC Modelli di certificato) per vedere il **nome del modello** e il **nome visualizzato del modello**.
  
2.  Accedere ad un server membro di dominio o controller di dominio utilizzando un account utente di dominio.
  
3.  Eseguire il comando seguente per salvare i dettagli del modello nel file *templatename.*ldif, sostituendo *templatename* con il nome del modello di certificato e *DC=woodgrovebank,DC=com* con il nome del dominio (DN) dell’insieme di strutture:
  
    ldifde -f *templatename*.ldif -d "cn=*templatename*, cn=Certificate Templates,cn=Public Key Services,cn=Services,cn=Configuration,*DC=woodgrovebank,DC=com*"
  
    Questo comando deve essere immesso su una sola riga, anche se qui può comparire su più righe.
  
4.  Il file *templatename*.ldif verrà salvato nella directory corrente. Archiviare il file *templatename*.ldif in modo sicuro.
  
##### Importazione di un modello di certificato in Active Directory
  
Nel caso in cui si desideri ripristinare un modello dal backup, ad esempio, per ripristinare una modifica apportata ad un modello, è possibile importare di nuovo in Active Directory la definizione del modello di certificato salvata in precedenza.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori PKI dell'organizzazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: Idifde.exe
  
###### Dettagli relativi all'attività
  
Questa procedura descrive come ripristinare la definizione di un modello di certificato da un file. Il file deve essere stato creato in precedenza mediante la procedura "Esportazione di un modello di certificato da Active Directory". Questo metodo ripristina solo le informazioni LDAP dell’oggetto modello. Altre informazioni, ad esempio le informazioni sulla protezione(proprietà, autorizzazioni e così via) non vengono mantenute utilizzando questo processo.
  
**Nota:** l'unico modo completamente supportato per eseguire il backup e il ripristino degli oggetti Active Directory consiste nell’utilizzare un metodo di backup di directory dedicato come il backup dello stato del sistema di Windows. Tuttavia, il ripristino di una versione precedente di un oggetto modificato richiede un ripristino autorevole di Active Directory che è una procedura complessa. Questa procedura descrive un modo semplice per eseguire il backup e il ripristino di un’istantanea di un oggetto modello di certificato.
  
Questa procedura non sostituisce quella di backup e ripristino di Active Directory e deve essere utilizzata solo nelle specifiche circostanze descritte.
  
**Per importare un oggetto modello di certificato**
  
1.  Recuperare il file della definizione del modello esportato creato mediante la procedura "Esportazione di un modello di certificato da Active Directory".
  
2.  Accedere ad un server membro di dominio o ad un controller di dominio come membro del gruppo Enterprise PKI Admins.
  
3.  Se si sostituisce un modello esistente, eseguire il backup del modello da sostituire (utilizzando la procedura descritta in precedenza), prendere nota delle autorizzazioni del modello ed eliminarlo.
  
4.  Aprire il file con Blocco note o un editor di testo simile e ricercare la riga che inizia con "objectGUID:". La riga dovrebbe essere simile alla seguente (sebbene i caratteri dopo la virgola siano differenti):
  
    objectGUID:: b/pVt//+I0i9hp8aJ7IWRg==
  
5.  Eliminare la riga, prestando attenzione a non apportare altre modifiche al file e salvarlo.
  
6.  Eseguire il comando seguente per importare il modello in Active Directory dal file *templatename*.ldif, sostituendo *templatename* con il nome del modello di certificato:
  
    ldifde -f *templatename*.ldif -i
  
7.  Verificare che la procedura funzioni aprendo MMC Modelli di certificato e visualizzando il modello ripristinato.
  
8.  Applicare al modello ripristinato le autorizzazioni di cui si è preso nota nel passaggio 3 oppure applicare quelle appropriate per questo modello.
  
#### Monitoraggio e controllo dei servizi
  
Il monitoraggio dei servizi consente al personale operativo di osservare la condizione di un servizio IT in tempo reale.
  
Nei punti di questa sezione in cui si fa riferimento a MOM si presume che la distribuzione di MOM segua le indicazioni della Guida operativa a MOM. MOM non è richiesto, viene utilizzato semplicemente a scopo illustrativo. Consultare la sezione "Ulteriori informazioni" alla fine di questo capitolo per ulteriori informazioni sulla Guida operativa a MOM.
  
##### Classificazione degli avvisi di monitoraggio
  
Il sistema di monitoraggio dovrebbe segnalare solo gli avvisi più significativi al personale operativo. Se tutti gli errori di minore entità venissero classificati in modo da generare avvisi di richiesta di supporto, il personale operativo in breve non riuscirebbe più a definire l’urgenza delle operazioni.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Nessuno
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici**: Console avvisi operativi (ad esempio MOM)
  
###### Dettagli relativi all'attività
  
In questo capitolo vengono utilizzate le seguenti categorie di avvisi. Di queste, solo le prime tre (Servizio non disponibile, Violazione della protezione, Errore critico) producono avvisi sulla console dell'operatore che richiedono attenzione immediata. Gli errori e gli avvisi non sono considerati urgenti, quindi la loro risoluzione viene demandata al supporto tecnico operativo PKI. Queste categorie di eventi rappresentano le impostazioni predefinite utilizzate da MOM, alle quali verrà fatto riferimento nelle descrizioni delle attività successive nella presente sezione.
  
**Tabella 11.9. Categorie di avvisi**

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
<td style="border:1px solid black;"><p>Quando l'applicazione genera un evento informativo. L’applicazione o il componente è operativo ad un livello di prestazioni accettabile ed esegue tutte le operazioni critiche e non critiche.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Operazione riuscita</p></td>
<td style="border:1px solid black;"><p>Quando l'applicazione genera un evento riuscito. L'applicazione o il componente funziona a un livello di prestazioni accettabile ed esegue tutte le operazioni critiche e non critiche.</p></td>
</tr>  
</tbody>  
</table>
  
##### Monitoraggio restrizioni capacità Servizi certificati
  
Il rilevamento di eventuali vincoli di capacità è essenziale per mantenere il servizio a un livello ottimale. Quando i sottosistemi si avvicinano al limite delle capacità operative, le prestazioni si riducono drasticamente (di solito non in modo lineare). Pertanto, è importante monitorare gli andamenti della capacità e identificare e risolvere in anticipo le tendenze verso vincoli futuri.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: L'autorizzazione necessaria richiesta dalla soluzione di monitoraggio
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici:**
  
    -   Performance Monitor
  
    -   Consolidatore dei contatori delle prestazioni (ad esempio MOM)
  
    -   Console avvisi operativi (ad esempio MOM)
  
    -   Strumenti per la pianificazione della capacità
  
###### Dettagli relativi all'attività
  
I seguenti contatori di prestazioni sono i più utili per identificare le restrizioni delle capacità in Servizi certificati. Processore e disco fisico sono le due risorse maggiormente utilizzate da Servizi certificati e indicano quindi restrizioni a un livello precedente rispetto a quelle dell'interfaccia di rete o della memoria.
  
**Tabella 11.10. Principali contatori di monitoraggio capacità per Servizi certificati**

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
<td style="border:1px solid black;"><p>Lunghezza Media lettura coda del disco</p></td>
<td style="border:1px solid black;"><p>_Total</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Disco fisico</p></td>
<td style="border:1px solid black;"><p>Lunghezza Media scrittura coda del disco</p></td>
<td style="border:1px solid black;"><p>D: (CA–DB)<br />
C: (CA–Log)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Interfaccia di rete</p></td>
<td style="border:1px solid black;"><p>Byte totali/sec</p></td>
<td style="border:1px solid black;"><p>Scheda di rete</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Memoria</p></td>
<td style="border:1px solid black;"><p>% Byte vincolati in uso</p></td>
<td style="border:1px solid black;"><p>–––</p></td>
</tr>  
</tbody>  
</table>
  
Per ulteriori informazioni generali sulle restrizioni della capacità e i contatori delle prestazioni correlati, vedere il riferimento contenuto nella sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
È inoltre essenziale monitorare gli indicatori di capacità su qualsiasi infrastruttura di supporto. Gli elementi chiave sono:
  
-   **Le comunicazioni di Servizi certificati con Active Directory** Le CA dell’organizzazione di grandi dimensioni utilizzano Active Directory per i servizi di autenticazione e autorizzazione, per leggere e archiviare le informazioni sulla configurazione dell’autorità di certificazione dell’infrastruttura PKI e, a seconda del tipo di certificato, per pubblicare i certificati emessi sulla directory.
  
-   **Le comunicazioni correlate ai certificati client con Active Directory** I client leggono le informazioni sull’autorità di certificazione e sull’infrastruttura PKI da Active Directory. Questa attività implica il download di CRL di diversi MB, per client e per settimana.
  
-   **Le comunicazioni correlate ai certificati client con il server Web** I client possono recuperare i certificati CA e gli elenchi CRL dal server Web, sebbene sia improbabile che questa attività produca un carico tale da causare restrizioni di capacità, a meno che il server non sia già estremamente carico.
  
##### Monitoraggio integrità e disponibilità Servizi certificati
  
Le autorità di certificazione generalmente non forniscono servizi in linea o in tempo reale (mentre servizi quali Active Directory o Microsoft SQL Server™, ad esempio, devono essere costantemente in linea per poter fornire un servizio utile). Tuttavia, molti aspetti dell’operatività della CA sono critici e richiedono risposte in linea del servizio:
  
-   **Disponibilità delle informazioni di revoca** Un CRL corrente deve essere disponibile per qualsiasi utente che desideri controllare lo stato di revoca di un certificato.
  
-   **Validità del certificato CA** Una CA deve avere un certificato attualmente valido. Un certificato CA non valido impedisce la convalida di qualsiasi certificato emesso dalla CA o dalle sue subordinate. Impedisce inoltre l’emissione di nuovi certificati.
  
-   **Disponibilità del servizio di registrazione certificati** Nessuno può registrare o rinnovare un certificato se il servizio CA non è disponibile.
  
La mancata disponibilità dei primi due aspetti ha generalmente un impatto maggiore rispetto alla non disponibilità dell’ultimo.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratore MOM (o sistema di monitoraggio)
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici:**
  
    -   Script MSS
  
    -   Console avvisi operativi (quale MOM o infrastruttura di posta elettronica)
  
    -   Agenti MOM o Servizio Utilità di pianificazione di Windows per l’esecuzione
  
###### Dettagli relativi all'attività
  
Gli eventi riportati nella tabella seguente sono i più significativi per Servizi certificati. La tabella descrive il significato dei tipi di evento e il grado di criticità dell'avviso (per la console operativa) da assegnare all'evento. Nella seconda tabella vengono descritti i metodi di rilevamento di tali problemi, molti dei quali vengono rilevati mediante gli script operativi forniti con questa soluzione.
  
La colonna Criticità si riferisce alle Categorie di avvisi definite nella procedura "Classificazione degli avvisi di monitoraggio" descritta in precedenza.
  
**Tabella 11.11. Criticità dei principali eventi Servizi certificati**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Stato Servizi certificati</p></th>  
<th><p>Significato</p></th>  
<th><p>Criticità</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>CRL scaduto</p></td>
<td style="border:1px solid black;"><p>Un CRL valido non è accessibile; tale situazione sta attualmente causando una perdita di servizio.</p></td>
<td style="border:1px solid black;"><p>Servizio non disponibile</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>CRL pronto</p></td>
<td style="border:1px solid black;"><p>L’elenco CRL è ancora valido ma un nuovo elenco CRL è pronto e dovrebbe essere stato pubblicato.</p></td>
<td style="border:1px solid black;"><p>Critica</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Elenco CRL non disponibile<br />
Eventi secondari:<br />  
Il CRL non può essere recuperato da  Active Directory<br />
Il CRL non può essere recuperato dal server Web</p></td>
<td style="border:1px solid black;"><p>Non è disponibile alcun elenco CRL nel punto di distribuzione CRL pubblicato. Questa situazione potrebbe causare perdita di servizio.</p></td>
<td style="border:1px solid black;"><p>Critica</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Server CA non riuscito</p></td>
<td style="border:1px solid black;"><p>Il server non è visibile sulla rete.</p></td>
<td style="border:1px solid black;"><p>Servizio non disponibile</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Integrità del sistema operativo CA in stato critico</p></td>
<td style="border:1px solid black;"><p>Presenza di un problema di entità maggiore con Windows o l’hardware del server.</p></td>
<td style="border:1px solid black;"><p>Critica</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Integrità del sistema operativo CA in stato di errore/avviso</p></td>
<td style="border:1px solid black;"><p>Presenza di problemi non critici con Windows o l’hardware del server.</p></td>
<td style="border:1px solid black;"><p>Errore o Avviso (come definito dalle regole MOM)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Servizi certificati non in linea<br />
Eventi secondari:<br />  
   Interfaccia client non in linea<br />
   Interfaccia di amministrazione non in linea</p></td>
<td style="border:1px solid black;"><p>L’interfaccia RPC (Remote Procedure Call) di Servizi certificati non è in linea; i certificati non possono essere emessi.</p></td>
<td style="border:1px solid black;"><p>Critica</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Certificato CA scaduto<br />
Eventi secondari:<br />  
   Questo certificato CA è scaduto<br />
   Il certificato CA padre è scaduto</p></td>
<td style="border:1px solid black;"><p>Il certificato della CA è scaduto. Questa situazione sta attualmente causando una perdita di servizio.</p></td>
<td style="border:1px solid black;"><p>Servizio non disponibile</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>La validità rimanente del certificato CA è inferiore a 1 mese</p></td>
<td style="border:1px solid black;"><p>Il certificato CA scadrà presto e, se non corretto, causerà la perdita del servizio. Attualmente vengono emessi solo certificati con durata molto breve.</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>La validità del certificato CA è inferiore alla metà del suo periodo di validità</p></td>
<td style="border:1px solid black;"><p>Un certificato CA deve essere rinnovato quando raggiunge la metà del suo periodo di validità. Ciò significa che vengono emessi certificati con validità inferiore alla durata prevista.</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Backup CA non riuscito</p></td>
<td style="border:1px solid black;"><p>Backup dello stato del sistema della CA non riuscito; possibile perdita di informazioni.</p></td>
<td style="border:1px solid black;"><p>Critico o Errore</p></td>
</tr>  
</tbody>  
</table>
  
Per controllare questi eventi, è possibile utilizzare lo script ca\_monitor.wsf fornito nella tabella seguente. Quando viene rilevato un errore, la logica degli script include la scrittura degli eventi nel registro delle applicazioni di Windows. Questi eventi possono quindi essere rilevati dagli agenti MOM o da un’altra soluzione di monitoraggio. È necessario impostare delle regole per l'applicazione dei filtri per verificare l'origine e le ID dell'evento prodotte dagli script elencati nella tabella riportata di seguito.
  
Gli script possono inoltre inviare un messaggio di posta elettronica in risposta alle condizioni di avviso. Quando viene utilizzato il sistema MOM (o un altro sistema di monitoraggio basato su agenti), gli script devono essere eseguiti dall’agente client MOM. Se non è presente alcun agente di gestione in grado di effettuare questa operazione, utilizzare il servizio Utilità di pianificazione di Windows per eseguire questi controlli almeno ogni ora. Gli avvisi possono essere inviati mediante posta elettronica o con uno strumento di monitoraggio del Registro eventi.
  
Gli script sono stati progettati per essere eseguiti sulla CA di emissione in linea, sebbene eseguano anche controlli sullo stato dei certificati pubblicati e sui CRL a partire dalle CA padre non in linea fino alla CA principale. Gli ID evento generati dallo script di monitoraggio sono mostrati nella tabella seguente. La sintassi dello script viene mostrata dopo la tabella.
  
**Tabella 11.12. Script di monitoraggio di Servizi certificati**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Event</p></th>  
<th><p>Script o metodo di rilevamento</p></th>  
<th><p>Origine e</p>  
<p>ID evento</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>CRL scaduto</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCRLs</p></td>
<td style="border:1px solid black;"><p>Operazioni CA 20</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>CRL pronto</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCRLs</p></td>
<td style="border:1px solid black;"><p>Operazioni CA 21</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Elenco CRL non disponibile<br />
Eventi secondari:<br />  
   Impossibile recuperare l’elenco CRL da Active Directory<br />
Il CRL non può essere recuperato dal server Web</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCRLs</p></td>
<td style="border:1px solid black;"><p>Operazioni CA 22<br />
23</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Server CA non riuscito</p></td>
<td style="border:1px solid black;"><p>Rilevamento errore server MOM nativo</p></td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Integrità del sistema operativo CA in stato critico</p></td>
<td style="border:1px solid black;"><p>Monitoraggio integrità server MOM nativo</p></td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Integrità del sistema operativo CA in stato di errore/avviso</p></td>
<td style="border:1px solid black;"><p>Monitoraggio integrità server MOM nativo</p></td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Servizi certificati in linea<br />
Eventi secondari:<br />  
   Interfaccia client non in linea<br />
   Interfaccia di amministrazione non in linea</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: IsCAAlives</p></td>
<td style="border:1px solid black;"><p>Operazioni CA 1<br />
2</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Certificato CA scaduto<br />
Eventi secondari:<br />  
   Questo certificato CA è scaduto<br />
   Il certificato CA padre è scaduto</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCACerts</p></td>
<td style="border:1px solid black;"><p>Operazioni CA 10</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>La validità rimanente del certificato CA è inferiore a 1 mese</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCACerts</p></td>
<td style="border:1px solid black;"><p>Operazioni CA 11</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>La validità del certificato CA è inferiore alla metà del suo periodo di validità</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCACerts</p></td>
<td style="border:1px solid black;"><p>Operazioni CA 12</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Backup CA bloccato (non è stato possibile eseguire lo script di backup in quanto era ancora presente un file di blocco del backup precedente)</p></td>
<td style="border:1px solid black;"><p>Script: Ca_operations.wsf<br />
Job: BackupCADatabase</p></td>
<td style="border:1px solid black;"><p>Operazioni CA 30</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Backup CA non riuscito</p></td>
<td style="border:1px solid black;"><p>Il codice di errore per NTBackup.exe viene fornito in questa situazione, sebbene si basi sulle capacità di MOM o di un altro sistema di monitoraggio per avvisare sui problemi di backup. Tenere presente che è necessario controllare sia il sistema di backup dello stato del sistema che quello organizzativo.</p></td>
<td style="border:1px solid black;"><p>Ntbackup<br />
8019</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Altro evento</p></td>
<td style="border:1px solid black;"><p>Errore di esecuzione di Ca_monitor.wsf</p></td>
<td style="border:1px solid black;"><p>Operazioni CA 100</p></td>
</tr>  
</tbody>  
</table>
  
Prima della distribuzione degli script, aggiornare il file constants.vbs con i parametri di avviso corretti. Di seguito sono riportate le sezioni pertinenti del file. Le voci da modificare sono evidenziate in corsivo:
  
<codesnippet language displaylanguage containsmarkup="false">'Alerting parameters CONST ALERT\_EMAIL\_ENABLED = FALSE'set to true/false to enable/disable email CONST ALERT\_EVTLOG\_ENABLED= TRUE'set to true/false to enable/disable event 'log entries ' set to comma-separated list of recipients to get email alerts CONST ALERT\_EMAIL\_RECIPIENTS= "Admin@woodgrovebank.com,Ops@woodgrovebank.com" 'SMTP host to use CONST ALERT\_EMAIL\_SMTP= "mail.woodgrovebank.com" 'String used as the Source in event log events CONST EVENT\_SOURCE= "MSS Tools" CONST CA\_EVENT\_SOURCE= "CA Operations" 'CA Event IDs CONST CA\_EVENT\_CS\_RPC\_OFFLINE=1 CONST CA\_EVENT\_CS\_RPC\_ADMIN\_OFFLINE=2 CONST CA\_EVENT\_CA\_CERT\_EXPIRED=10 CONST CA\_EVENT\_CA\_CERT\_NEARLY\_EXPIRED=11 CONST CA\_EVENT\_CA\_CERT\_RENEWAL\_DUE=12 CONST CA\_EVENT\_CRL\_EXPIRED=20 CONST CA\_EVENT\_CRL\_OVERDUE=21 CONST CA\_EVENT\_CRL\_NOT\_AVAILABLE\_LDAP=22 CONST CA\_EVENT\_CRL\_NOT\_AVAILABLE\_HTTP=23 CONST CA\_EVENT\_BACKUP\_LOCKED=30 CONST CA\_EVENT\_CA\_OTHER=100  
```  
È necessario specificare se si desidera che gli errori producano avvisi di posta elettronica o voci del Registro eventi o entrambi. L'impostazione predefinita comprende solo voci del Registro eventi. Se si desidera produrre avvisi di posta elettronica, è *necessario* fornire un elenco di destinatari di posta elettronica valido (separati dalla virgola) e il nome host del server SMTP o l’indirizzo IP. Entrambe queste stringhe devono essere racchiuse tra virgolette.
  
Se si specifica l’avviso del Registro eventi, è necessario modificare il parametro CA\_EVENT\_SOURCE (usato per tutti gli eventi CA correlati) o EVENT\_SOURCE (usato per tutti gli eventi non correlati alla CA).
  
La sintassi e l’uso degli script di monitoraggio sono descritti nella sezione seguente.
  
**Per controllare la scadenza del certificato CA**
  
Eseguire il comando qui riportato per verificare il certificato della CA di emissione (dove viene eseguito lo script) e i certificati pubblicati di tutte le CA padre fino alla CA principale.
  
Cscript //job:CheckCACerts C:\\MSSScripts\\ca\_monitor.wsf
  
L’esecuzione di questo comando avvisa sulle seguenti condizioni:
  
-   Il certificato CA è scaduto (ID evento 12)
  
-   La validità alla scadenza del certificato CA è inferiore ad un mese (ID evento 11)
  
-   Il certificato CA ha superato la metà della durata del suo periodo di validità (ID evento 12)
  
**Per controllare la scadenza dell’elenco CRL**
  
Eseguire il comando qui riportato per verificare l'elenco CRL della CA di emissione e gli elenchi CRL pubblicati di tutte le CA padre fino alla CA principale inclusa.
  
Cscript //job:CheckCRLs C:\\MSSScripts\\ca\_monitor.wsf
  
L’esecuzione di questo comando avvisa sulle seguenti condizioni:
  
-   Il CRL è scaduto (ID evento 20)
  
-   Il CRL ha superato la data specificata in "Pubblicazione successiva CRL" ed è scaduto (ID evento 21)
  
-   Il CRL non può essere recuperato da CDP LDAP (ID evento 22)
  
-   Il CRL non può essere recuperato da CDP HTTP (ID evento 23)
  
Attualmente, FTP e FILE CDP non vengono controllati nello script.
  
**Per verificare che il servizio CA sia in esecuzione**
  
Eseguire il comando qui riportato per verificare la CA su cui viene eseguito lo script.
  
Cscript //job:IsCAAlive C:\\MSSScripts\\ca\_monitor.wsf
  
L’esecuzione di questo comando avvisa sulle seguenti condizioni:
  
-   L’interfaccia client RPC della CA non risponde (ID evento 1)
  
-   L’interfaccia di amministrazione RPC della CA non risponde (ID evento 2)
  
##### Monitoraggio della protezione dell’autorità di certificazione
  
Servizi certificati produce una varietà di voci di registro di controllo in risposta ai diversi eventi di protezione. La maggior parte di queste voci è il risultato di attività operative quotidiane. Tuttavia, alcuni eventi indicano le principali modifiche di configurazione che è inoltre necessario controllare.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione:**
  
    -   Controllori CA (per analizzare il registro di protezione)
  
    -   Account di monitoraggio della protezione designato per il monitoraggio mediante MOM (o sistema simile)
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici:**
  
    -   Console avvisi operativi (ad esempio MOM)
  
    -   Visualizzatore eventi
  
    -   Eventquery.vbs (strumento della riga di comando di Windows)
  
###### Dettagli relativi all'attività
  
Nella tabella seguente sono elencati gli eventi di controllo prodotti di Servizi certificati insieme alla categoria di avviso consigliata. Configurare il sistema di monitoraggio per la ricerca di questi eventi e specificare il livello di avviso appropriato. In alternativa, se non si dispone di un sistema di monitoraggio eventi centralizzato, esaminare i registri di protezione del server CA regolarmente (possibilmente giornalmente) per controllare questi elementi.  
La categoria di avviso predefinita per gli eventi riusciti è **Informazioni**. Qualsiasi evento di operazione riuscita risultante da possibili modifiche apportate alla configurazione della protezione della CA viene trattato come **Avviso.** Tutti gli eventi a livello di **Avviso** indicano eventi significativi normalmente non previsti nelle operazioni quotidiane. Tutti gli eventi di **Avviso** devono essere correlati ad una richiesta di modifica approvata. Se tale correlazione non è presente, trattare l’evento come possibile violazione di protezione e controllarlo immediatamente.
  
Gli eventi di **operazioni non riuscite** non sono normalmente previsti durante le operazioni quotidiane o durante le modifiche standard alla CA. Quasi tutti questi eventi di operazioni non riuscite sono significativi e devono essere controllati (sebbene possano indicare solo un’assegnazione di autorizzazione non corretta piuttosto che un attacco intenzionale).
  
**Nota:** vi sono alcune eccezioni, ad esempio l’Evento 792 in cui **Servizi certificati ha negato la richiesta di certificato**. Questa condizione produce gli eventi di operazione riuscita e non riuscita per una richiesta che è stata legittimamente negata dal responsabile certificati. L’evento di operazione non riuscita viene generato solo quando la negazione di una richiesta è richiesta da un utente che non dispone dell’autorizzazione necessaria.
  
Un’ulteriore serie di eccezioni all'elenco riportato di seguito è dovuta alle diverse modalità con le quali vengono apportate le modifiche di configurazione alla CA. Gli eventi 789 (modifica del filtro di controllo) e 795 e 796 (modifica delle proprietà o della configurazione della CA) vengono registrati solo se le modifiche vengono apportate utilizzando lo snap-in MMC Autorità di certificazione. La registrazione non avviene se qualcuno tenta di modificare direttamente il registro CA oppure utilizza il comando certutil -setreg per modificare i valori di configurazione della CA. Al contrario, questi eventi vengono registrati come semplici errori di controllo di accesso oggetto, Evento 560 (vedere l’ultima voce della tabella seguente). Il controllo è abilitato per le sottochiavi di configurazione del registro CA e registra le modifiche riuscite e tutti gli accessi non riusciti. Per tenere traccia delle modifiche apportate alle chiavi del Registro della CA, utilizzare il parametro **Nome oggetto** dell'evento di controllo insieme a **ID evento** e **Tipo evento** per creare un filtro per produrre gli avvisi corretti.
  
Oltre a controllare gli eventi Servizi certificati, è anche necessario monitorare e generare avvisi su eventi standard di protezione del sistema operativo, quali eventi di accesso, utilizzo di privilegi e accesso agli oggetti. Il database ed il registro CA e le directory dei registri sono state configurati per generare avvisi per tutti gli accessi non riusciti e per tutte le modifiche riuscite. Considerare inoltre il controllo delle impostazioni sul contenitore di servizi a chiave pubblica (in Configurazione\\Servizi) e sui gruppi di amministrazione dell'infrastruttura PKI. Tali impostazioni non sono inserite in questa soluzione a causa delle difficoltà di monitoraggio degli eventi di controllo distribuiti sui controller di dominio. Se si dispone di un sistema (quale MOM) in grado di consolidare e filtrare questi registri, abilitare il controllo su tutti i contenitori e gli oggetti della configurazione e dell’amministrazione dell’infrastruttura PKI di Active Directory.
  
**Nota:** il monitoraggio della protezione del sistema operativo della CA esula dagli argomenti trattati in questa guida e può includere la gestione degli eventi di protezione da parte di agenti specializzati nel rilevamento di intrusioni. Nel caso si verifichi una condizione che indichi la violazione della protezione, controllare interamente gli eventi di controllo dell’autorità di certificazione insieme all’output derivante da tali condizioni.
  
Le categorie degli avvisi di operazione riuscita e operazione non riuscita della tabella seguente si riferiscono alle categorie di avvisi definite nella procedura "Classificazione degli avvisi di monitoraggio" descritta in precedenza.
  
**Tabella 11.13. Eventi di controllo di Servizi certificati**

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
<th><p>ID evento</p></th>  
<th><p>Descrizione evento</p></th>  
<th><p>Categoria avviso di operazione riuscita</p></th>  
<th><p>Categoria avviso di operazione non riuscita</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>772</p></td>
<td style="border:1px solid black;"><p>Il responsabile certificati ha negato una richiesta di certificati in sospeso</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>773</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha ricevuto una richiesta di certificati nuovamente inoltrata</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>774</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha revocato un certificato</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>775</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha ricevuto una richiesta di pubblicazione dell’elenco di revoche di certificati (CRL)</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>776</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha pubblicato l'elenco di revoche di certificati (CRL)</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>777</p></td>
<td style="border:1px solid black;"><p>L’estensione di una richiesta di certificati è stata modificata</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>778</p></td>
<td style="border:1px solid black;"><p>Uno o più attributi di richieste di certificati sono stati modificati</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>779</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha ricevuto una richiesta di arresto</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>780</p></td>
<td style="border:1px solid black;"><p>È stato avviato il backup di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>–</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>781</p></td>
<td style="border:1px solid black;"><p>È stato completato il backup di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>–</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>782</p></td>
<td style="border:1px solid black;"><p>È stato avviato il ripristino di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>–</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>783</p></td>
<td style="border:1px solid black;"><p>È stato completato il ripristino di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>–</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>784</p></td>
<td style="border:1px solid black;"><p>Servizi certificati avviato</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>–</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>785</p></td>
<td style="border:1px solid black;"><p>Servizi certificati arrestato</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>–</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>786</p></td>
<td style="border:1px solid black;"><p>Le autorizzazioni di protezione di Servizi certificati sono state modificate</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>787</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha recuperato una chiave archiviata</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>788</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha importato un certificato nel proprio database</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>789</p></td>
<td style="border:1px solid black;"><p>Il filtro di controllo per Servizi certificati è stato modificato</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>790</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha ricevuto una richiesta di certificato</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>791</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha approvato una richiesta di certificato e ha rilasciato un certificato</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>792</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha negato una richiesta di certificato</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>793</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha negato una richiesta di certificato</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>794</p></td>
<td style="border:1px solid black;"><p>Le impostazioni del responsabile certificati per Servizi certificati sono state modificate</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>795</p></td>
<td style="border:1px solid black;"><p>Una voce della configurazione in Servizi certificati è stata modificata</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Nodo:<br />
Voce: CRLPeriod o CRLPeriodUnits o CRLDeltaPeriod o CRLDeltaPeriodUnits<br />
Descrive le modifiche nella pianificazione della pubblicazione del CRL. Il valore 0 per CRLDeltaPeriodUnits significa che la pubblicazione di Delta CRL è disattivata.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Nodo: PolicyModules\CertificateAuthority_Microsoft<br />
Default.Policy<br />  
Voce: RequestDisposition<br />  
Valore: 1<br />
Imposta la CA per l’emissione di richieste in ingresso, se non diversamente specificato.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Nodo: PolicyModules\CertificateAuthority_Microsoft<br />
Default.Policy<br />  
Voce: RequestDisposition<br />  
Valore: 257<br />
Imposta la CA in modo che mantenga le richieste in ingresso in sospeso.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Nodo: ExitModules\CertificateAuthority_Microsoft<br />
Default.Exit<br />  
Voce: PublishCertFlags<br />  
Valore: 1<br />
Consente ai certificati di essere pubblicati nel file system.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Nodo: ExitModules\CertificateAuthority_Microsoft<br />
Default.Exit<br />  
Voce: PublishCertFlags<br />  
Valore: 0<br />
Non consente ai certificati di essere pubblicati nel file system.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Nodo: ExitModules<br />
Voce: Active<br />
Passa al modulo uscita attivo. Valore specifica il nome del nuovo modulo. Se vuoto significa nessuno.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Nodo: PolicyModules<br />
Voce: Active<br />
Passa al modulo criterio attivo. Valore specifica il nome del nuovo modulo.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Nodo:<br />
Voce: CRLPublicationURLs<br />
Passa a CDP o AIA. Valore specifica il gruppo di CDP risultanti</p></td>
<td style="border:1px solid black;"><p>Nodo:<br />
Voce: CACertPublicationURLs<br />
Passa a AIA o CDP. Valore specifica il gruppo di AIA risultanti.</p></td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>796</p></td>
<td style="border:1px solid black;"><p>Una proprietà di Servizi certificati è stata modificata (vedere i sottotipi riportati di seguito).</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Tipo: 4<br />
Aggiunta/rimozione di un modello a/da CA. Valore è l’elenco dei modelli risultanti ordinato per nome e OID.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Tipo: 3<br />
Aggiunta di certificati KRA a CA. Valore è la rappresentazione Base64 del certificato.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Tipo: 1<br />
Rimozione certificato KRA da CA. Valore è il conteggio totale dei certificati KRA.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"><p>Tipo: 1<br />
Aggiunta/rimozione numero di certificati KRA da utilizzare per l’archiviazione delle chiavi. Valore è il numero risultante di certificati da utilizzare.</p></td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>797</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha archiviato una chiave.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>–</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>798</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha importato e archiviato una chiave.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>–</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>799</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha pubblicato il certificato della CA in Active Directory.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"> </td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>800</p></td>
<td style="border:1px solid black;"><p>Una o più righe sono state eliminate dal database dei certificati.</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>801</p></td>
<td style="border:1px solid black;"><p>Separazione ruoli abilitata.</p></td>
<td style="border:1px solid black;"><p>Attenzione</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>560</p></td>
<td style="border:1px solid black;"><p>Accesso agli oggetti<br />
Dove:<br />  
Tipo oggetto: <strong>Chiave</strong><br />
Nome oggetto: <strong>\REGISTRY\MACHINE\SYSTEM\ ControlSet001\Services\CertSvc\Configuration</strong></p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
</tbody>  
</table>
  
##### Impostazione degli avvisi SMTP per le richieste di certificati in sospeso
  
Se si dispone di alcuni tipi di certificato configurati per richiedere l’approvazione del responsabile certificati, tali certificati rimangono in coda nella cartella delle richieste in sospeso (dello snap-in MMC Autorità di certificazione) fino a quando la richiesta non viene approvata o respinta. È possibile configurare l’invio di avvisi di posta elettronica ogni volta che una richiesta viene messa in coda. Le richieste approvate automaticamente non inviano avvisi di posta elettronica.
  
Gli avvisi di posta elettronica possono essere configurati anche per altri eventi CA. Nella Guida in linea di Servizi certificati, è possibile trovare informazioni su come configurare tali avvisi.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori CA
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici:**
  
    -   Editor di testo
  
    -   Server SMTP e cassetta postale del destinatario
  
###### Dettagli relativi all'attività
  
I valori del server SMTP e l'elenco dei destinatari SMTP configurati nel file constants.vbs e utilizzati in questa procedura sono condivisi anche dal sevizio di avvisi SMTP descritto nella procedura "Monitoraggio integrità e disponibilità Servizi certificati". Se sono richieste due diverse impostazioni per il server SMTP e i destinatari per le due procedure, è possibile modificare temporaneamente i valori nel file constants.vbs, quindi eseguire la presente procedura. Lo script utilizzato in questa procedura consente di salvare le impostazioni nel registro CA. Dopo l'esecuzione, il file constants.vbs può essere riportato ai valori precedenti da utilizzare con lo script per il monitoraggio nella procedura "Monitoraggio integrità e disponibilità Servizi certificati" (in questa procedura, l’impostazione per l’attivazione e la disattivazione degli avvisi di posta elettronica, ALERT\_EMAIL\_ENABLED, non ha alcun effetto sui relativi avvisi).
  
**Per attivare gli avvisi di posta elettronica per le richieste in sospeso**
  
1.  Configurare i valori corretti per i destinatari della posta elettronica e il server SMTP nel file di script C:\\MSSScripts\\constants.vbs:
  
    <codesnippet language displaylanguage containsmarkup="false">'Alerting parameters ' set to comma-separated list of recipients to get email alerts CONST ALERT\_EMAIL\_RECIPIENTS= "Admin@woodgrovebank.com, PKIOps@woodgrovebank.com" CONST ALERT\_EMAIL\_SMTP= "mail.woodgrovebank.com" 'SMTP host to use  
```
  
    **Nota:** la riga con rientro visualizzata nel file rappresenta la prosecuzione della riga precedente che viene continuata nella riga successiva per questioni di visualizzazione, anche se si tratta di un'unica riga del file.
  
2.  Per attivare gli avvisi di posta elettronica per le richieste in sospeso inserite in coda, eseguire il comando:
  
    cscript //job:SetupSMTPAlerts C:\\MSSScripts\\ca\_monitor.wsf
  
#### Pianificazione dei processi
  
La pianificazione dei processi include la continua organizzazione dei processi nella sequenza più efficiente, aumentando la velocità di trasmissione dati e l’utilizzo del sistema per soddisfare i requisiti SLA (Service Level Agreement). La pianificazione dei processi è strettamente legata al monitoraggio e al controllo dei servizi e alla gestione della capacità.
  
##### Pianificazione dei processi sulla CA di emissione
  
Un certo numero di attività ripetitive deve essere eseguita sulle CA per mantenere l’esecuzione continua dell’infrastruttura di Servizi certificati. Tali attività sono automatiche in modo da ridurre il carico operativo.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici:**
  
    -   Utilità di pianificazione di Windows
  
    -   MOM (se appropriato)
  
###### Dettagli relativi all'attività
  
Nella tabella seguente sono elencati i processi automatizzati che vengono eseguiti nelle CA di emissione. Tali processi vengono definiti in attività descritte in altre sezioni del presente capitolo (visualizzate nella colonna **Attività di riferimento**); la tabella seguente viene visualizzata solo come riferimento.
  
Solo sulla CA di emissione possono essere eseguiti processi automatici. La CA principale potrebbe essere disattivata per periodi lunghi, di conseguenza non è possibile mantenere sul computer una pianificazione attendibile.
  
**Tabella 11.14. Elenco di processi pianificati sulla CA di emissione**

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
<th><p>Descrizione della mansione</p></th>  
<th><p>Schedule</p></th>  
<th><p>Eseguito da</p></th>  
<th><p>Attività di riferimento</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Backup dello stato del sistema della CA su file</p></td>
<td style="border:1px solid black;"><p>Ogni giorno</p></td>
<td style="border:1px solid black;"><p>Utilità di pianificazione di Windows</p></td>
<td style="border:1px solid black;"><p>Configurazione ed esecuzione del backup del database della CA di emissione<br />
Configurazione ed esecuzione del backup del database della CA principale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Backup del file della CA per archiviazione di backup</p></td>
<td style="border:1px solid black;"><p>Quotidiana (dopo il backup dello stato del sistema)</p></td>
<td style="border:1px solid black;"><p>Utilità di pianificazione backup organizzativa</p></td>
<td style="border:1px solid black;"><p>Nessuna (definita dall’organizzazione)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Pubblicazione di CRL su IIS</p></td>
<td style="border:1px solid black;"><p>Oraria</p></td>
<td style="border:1px solid black;"><p>Utilità di pianificazione di Windows</p></td>
<td style="border:1px solid black;"><p>Pubblicazione certificati e CA di emissione su IIS</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Controllo dell’integrità della CA in linea</p></td>
<td style="border:1px solid black;"><p>Oraria</p></td>
<td style="border:1px solid black;"><p>MOM o Utilità di pianificazione di Windows</p></td>
<td style="border:1px solid black;"><p>Monitoraggio integrità e disponibilità Servizi certificati</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Monitoraggio dello stato di pubblicazione ed emissione CRL</p></td>
<td style="border:1px solid black;"><p>Oraria</p></td>
<td style="border:1px solid black;"><p>MOM o Utilità di pianificazione di Windows</p></td>
<td style="border:1px solid black;"><p>Monitoraggio integrità e disponibilità Servizi certificati</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Monitoraggio della validità dei certificati CA</p></td>
<td style="border:1px solid black;"><p>Ogni giorno</p></td>
<td style="border:1px solid black;"><p>MOM o Utilità di pianificazione di Windows</p></td>
<td style="border:1px solid black;"><p>Monitoraggio integrità e disponibilità Servizi certificati</p></td>
</tr>  
</tbody>  
</table>
  
#### Altre attività operative
  
Esistono altre attività operative relative alla manutenzione di un’infrastruttura PKI che generalmente non sono necessarie ma che potrebbero servire occasionalmente oppure riguardano problemi di supporto.
  
La documentazione di Servizi certificati di Windows Server 2003 descrive alcune di queste attività e fornisce informazioni relative all’amministrazione che non vengono trattate né in questo capitolo né nel capitolo "Implementazione di un'infrastruttura a chiave pubblica" della Guida alla creazione. Anche quando l'attività è trattata nella presente guida, è sempre consigliabile fare riferimento alla documentazione relativa al prodotto per ottenere ulteriori informazioni.
  
Vedere la sezione "Ulteriori informazioni" alla fine di questo capitolo per il collegamento a questo documento nel quale è possibile trovare istruzioni sull’esecuzione delle seguenti attività amministrative:
  
-   Avvio o arresto del servizio Autorità di certificazione.
  
-   Impostazione delle autorizzazioni di protezione e delega del controllo di un’autorità di certificazione.
  
-   Visualizzazione del certificato dell’autorità di certificazione.
  
-   Impostazione della protezione per l’accesso alle pagine Web dell’autorità di certificazione.
  
-   Configurazione delle restrizioni del gestore dei certificati.
  
-   Pubblicazione dei certificati in un insieme di strutture Active Directory esterno
  
-   Invio di posta elettronica quando si verifica un evento di certificato.
  
-   Utilizzo dello snap-in Autorità di certificazione.
  
-   Gestione revoca del certificato.
  
-   Gestione delle richieste di certificati su un’autorità di certificazione autonoma.
  
-   Gestione dei modelli di certificato per un’autorità di certificazione di un’organizzazione di grandi dimensioni.
  
-   Gestione dell’archiviazione e del ripristino delle chiavi.
  
-   Modifica delle impostazioni dei criteri per un’autorità di certificazione.
  
-   Modifica dei moduli dei criteri o di uscita di un’autorità di certificazione.
  
-   Gestione dell’amministrazione basata sui ruoli.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di supporto
  
Le funzioni SMF della Fase di supporto includono sia attività reattive che preventive per garantire i livelli di servizio richiesti. Le funzioni reattive dipendono dalla capacità dell'organizzazione di reagire e risolvere rapidamente le emergenze e i problemi. Le funzionalità più auspicabili, quelle preventive, cercano di evitare le interruzioni dei servizi. Attraverso un buon monitoraggio della soluzione di servizi a fronte di soglie predefinite, tali funzioni consentono di identificare i problemi prima che influiscano sui livelli dei servizi. In questo modo, il personale operativo dispone di tempo sufficiente per reagire e risolvere i potenziali problemi.
  
La fase di supporto è strettamente correlata alla funzione SMF di monitoraggio e controllo dei servizi descritta nella fase operativa. Tale funzione fornisce le informazioni fondamentali grazie alle quali il personale operativo e di assistenza è in grado di rilevare i problemi. Le procedure descritte nella presente sezione riguardano i problemi più diffusi che potrebbero verificarsi e consentono di affrontarli.
  
Questa sezione contiene informazioni relative alla seguente funzione di gestione dei servizi:
  
-   Gestione delle emergenze
  
Non esistono attività per le restanti funzioni SMF:
  
-   Gestione dei problemi (la diagnosi dei problemi viene descritta nella sezione "Risoluzione dei problemi" più avanti in questo capitolo)
  
-   Servizio di assistenza
  
    **Nota:** ogni descrizione dell'attività contiene le seguenti informazioni di riepilogo: requisiti di protezione, frequenza e requisiti tecnologici.
  
#### Gestione delle emergenze
  
La gestione delle emergenze è il processo che consente di gestire e controllare errori e interruzioni nell'utilizzo o nell'implementazione dei servizi IT riferiti dai clienti o dai partner IT. L'obiettivo principale della gestione delle emergenze è ripristinare il normale funzionamento del servizio nel modo più rapido possibile e ridurre al minimo le ripercussioni negative sull'attività aziendale, assicurando il mantenimento della migliore qualità e disponibilità dei livelli di servizio. Con l'espressione normale funzionamento del servizio si intende un funzionamento entro i limiti del contratto del livello di servizio (SLA, Service Level Agreement).
  
Questa sezione è strettamente correlata alla sezione "Risoluzione dei problemi". Mentre la sezione "Risoluzione dei problemi" tratta l’identificazione e la diagnosi dei problemi, questa sezione contiene le attività più comuni utilizzate per risolvere tali problemi.
  
Le emergenze trattate nella sezione "Risoluzione dei problemi" sono:
  
-   Server non risponde
  
-   Pubblicazione CRL non riuscita
  
-   CRL non emesso
  
-   Il client non può registrare
  
-   Aggiornamento della protezione installato richiede riavvio
  
-   Errore server permanente
  
-   Certificato orfano deve essere revocato
  
-   Il server non può essere ripristinato in tempo per l’emissione del certificato o del CRL
  
-   Il certificato dell’entità finale è compromesso
  
-   Il certificato della CA di emissione è compromesso
  
-   Il certificato della CA principale è compromesso
  
La maggior parte di questi problemi sono correlati direttamente ad una o più delle procedure riportate in dettaglio nelle sezioni seguenti. In altri casi, ad esempio in caso di errore di registrazione del client, il processo di risposta al problema richiesto è più complesso e viene discusso nella sezione "Risoluzione dei problemi".
  
##### Riavvio di Servizi certificati
  
È necessario riavviare Servizi certificati per molti motivi operativi, ad esempio, dopo la riconfigurazione di molte proprietà della CA, è necessario riavviare Servizi certificati per rendere effettive le modifiche. In alcuni casi, potrebbe essere necessario riavviare Servizi certificati se il servizio non risponde oppure funziona in modo non previsto.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Snap-in MMC Autorità di certificazione
  
    -   Net.exe
  
###### Dettagli relativi all'attività
  
Vi sono molti metodi per riavviare il servizio, tutti accettabili per questa attività.
  
**Per riavviare il servizio CA**
  
1.  Verificare che nessun utente sia attualmente coinvolto in alcuna transazione con la CA. Inviare un avviso agli utenti che potrebbero essere coinvolti, se il tempo lo consente.
  
2.  Nella console MMC Autorità di certificazione, selezionare l’oggetto CA.
  
3.  Nel menu **Attività,** fare clic su **Arresta servizio** oppure al prompt dei comandi digitare:
  
    net stop "Servizi certificati"
  
4.  Nel menu **Attività,** fare clic su **Avvia servizio** oppure al prompt dei comandi digitare:
  
    net start "Servizi certificati"
  
    **Nota:** con il controllo abilitato, Servizi certificati potrebbe impiegare molto tempo per la chiusura e il riavvio; queste operazioni potrebbero richiedere oltre 10 minuti nel caso di database grandi. L'uso della funzione di controllo estende il processo di chiusura e avvio dell’intero server, poiché Servizi certificati deve calcolare l’hashing dell’intero database per creare le voci di controllo dell’avvio e dell’arresto del sistema. Questo ritardo non si verifica se le procedure di avvio e chiusura non vengono controllate.
  
##### Riavvio del server CA
  
È possibile dover riavviare il server CA per molti motivi operativi, ad esempio per applicare un aggiornamento del sistema operativo. Potrebbe essere necessario riavviare il server se il servizio non risponde o se funziona in modo non previsto e non si riavvia normalmente mediante la procedura di riavvio del servizio.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: Net.exe
  
###### Dettagli relativi all'attività
  
**Per riavviare il servizio CA**
  
1.  Verificare che nessun utente sia attualmente coinvolto in alcuna transazione con la CA. Inviare un avviso agli utenti che potrebbero essere coinvolti, se il tempo lo consente.
  
2.  Se possibile, eseguire il comando riportato di seguito per arrestare Servizi certificati in modo da impedire agli utenti di collegarsi alla CA durante l'arresto del sistema:
  
    net stop "Servizi certificati"
  
3.  Seguire le normali procedure del sistema operativo per riavviare il computer. A meno che non sia chiaro che il processo Servizi certificati non risponde, non tentare di eliminare il processo o arrestare il server. L’interruzione del processo Servizi certificati potrebbe danneggiare il database di Servizi certificati e richiedere un ripristino dal backup.
  
    **Nota:** come indicato nell'attività precedente, il controllo dei processi di avvio e di arresto può causare un ritardo nell'arresto e nel riavvio di Servizi certificati. Tale ritardo non si verifica se le procedure di avvio e chiusura non vengono controllate.
  
##### Ripristino della CA da un backup
  
Se non è possibile avviare una CA a causa di un grave danno software o hardware, è necessario ripristinare il server e i dati delle chiavi dal backup.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione:**
  
    -   Amministratori locali sulla CA
  
    -   Operatori di backup CA (solo per eseguire il ripristino)
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Utilità di backup di Windows
  
    -   Sistema di backup organizzativo
  
###### Dettagli relativi all'attività
  
Eseguire le operazioni seguenti per ripristinare una CA dal backup.
  
**Avviso:** se si utilizza un HSM, questa procedura non funziona come indicato. Seguire le istruzioni del produttore del modulo HSM per le operazioni di backup, ripristino e protezione dei dati della chiave e delle chiavi di accesso.
  
**Per ripristinare una CA dal backup**
  
1.  Il sistema operativo deve essere ripristinato fino al punto in cui risultava affidabile per eseguire nuovamente Servizi certificati; ciò potrebbe richiedere la reinstallazione di Windows. In questo caso, seguire le istruzioni nella Guida alla creazione per installare il sistema operativo e i componenti del sistema di base. Non è necessario applicare alcuna misura di protezione o altre misure di configurazione.
  
    **Avviso:** se è necessario reinstallare Windows sulla CA di emissione, non creare nuove partizioni e riformattare la seconda unità. Questa unità contiene il database della CA, che potrebbe essere intatto.
  
2.  Se possibile, conservare il database della CA (in %systemroot%\\System32\\CertLog sulla CA principale oppure in D:\\CertLog sulla CA di emissione) e i registri della CA (in %systemroot%\\System32\\CertLog). Prima di ripristinare la CA, eseguire il backup del file di queste cartelle. Il database ed i registri potrebbero non essere stati influenzati dal malfunzionamento del sistema. I registri contengono le informazioni necessarie per eseguire nuovamente tutte le transazioni sulla CA che sono state eseguite tra l’ultimo backup ed il malfunzionamento del server. Il ripristino del backup dello stato del sistema sovrascrive il database e i registri esistenti, quindi è consigliabile conservarli prima di iniziare il ripristino del sistema.
  
3.  Inserire il supporto di backup contenente il backup più recente della CA e ripristinare il file di backup dello stato del sistema in un’area del disco idonea (è consigliabile utilizzare una seconda unità, se disponibile).
  
4.  Avviare il programma di backup di Windows. Nella scheda **Ripristina**, fare clic con il pulsante destro del mouse su **File** nel riquadro di sinistra, quindi fare clic su **Cataloga file**.
  
5.  Accertarsi che l’opzione **Percorso originale** sia selezionata come destinazione di ripristino dei file, quindi fare clic su **Avvia ripristino** per ripristinare lo stato del sistema. Dopo il completamento dell'operazione, riavviare il server e interrompere Servizi certificati dopo il riavvio del sistema.
  
6.  Se i registri della CA sono stati conservati nel passaggio 2, copiarli nella cartella dei registri di Servizi certificati (%systemroot%\\System32\\CertLog). A questo punto, i registri possono essere eseguiti di nuovo in relazione al database ripristinato per inserire le eventuali transazioni eseguite dopo l’ultimo backup.
  
    **Nota:** se nel passaggio 2 il database della CA e i registri sono stati salvati intatti, è possibile ripristinarli nel server invece di eseguire la procedura descritta nel presente passaggio (passaggio 6). È necessario arrestare Servizi certificati prima di poter copiare nuovamente il database della CA e i registri sul server.
  
7.  Avviare Servizi certificati.
  
##### Ripristino del certificato CA e della coppia di chiavi su un computer temporaneo
  
Se una CA che non funziona non può essere ripristinata in tempo affinché la CA emetta un nuovo CRL (o certificato critico), è necessario installare il certificato CA e le chiavi su un computer temporaneo in modo da poterli utilizzare per firmare nuovamente ed estendere il periodo di validità del certificato o del CRL esistente.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali su un computer temporaneo
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Certutil.exe
  
    -   Cipher.exe
  
###### Dettagli relativi all'attività
  
Questa attività descrive come ripristinare il certificato CA e la chiave privata su un computer temporaneo. Se la CA è stata rinnovata, si disporrà dei backup di più certificati e coppie di chiavi. Per questa procedura, è necessario ripristinare la chiave e il file del certificato più recente.
  
**Importante:** se su questo computer è installata la chiave CA, adottare sempre le stesse precauzioni di protezione come se si trattasse della CA. Se si sta ripristinando la chiave di una CA non in linea, accertarsi che il computer non sia in linea. Una volta terminate le operazioni con la chiave, prendere in considerazione la riformattazione dei dischi del computer.
  
**Avviso:** se si utilizza un HSM, questa procedura non funziona come indicato. Seguire le istruzioni del produttore del modulo HSM per le operazioni di backup, ripristino e protezione dei dati della chiave e delle chiavi di accesso.
  
**Per ripristinare il certificato e la chiave CA su un computer temporaneo**
  
1.  Controllare che il computer sia disconnesso dalla rete. Accedere come membro del gruppo Amministratori locale, quindi creare l’account utente locale CAKeySigner.
  
2.  Eseguire l'accesso tramite questo nuovo account.
  
3.  Inserire un disco contenente il backup delle chiavi CA da controllare.
  
4.  Utilizzare Esplora risorse per individuare i file della chiave P12, selezionare il file più recente, quindi fare doppio clic per avviare l'Importazione guidata certificati.
  
5.  Quando viene richiesto, inserire la password. Non selezionare le caselle di controllo per aggiungere maggiore protezione alle chiavi o per renderle esportabili.
  
6.  Selezionare **Archivio** **personale** come posizione nella quale ripristinare le chiavi CA.
  
7.  Aprire lo snap-in MMC Certificati e scegliere l’archivio personale. Individuare il certificato CA della CA ripristinata, quindi aprirlo per verificare di possedere la chiave privata corrispondente.
  
A questo punto, è possibile eseguire qualsiasi attività di nuova firma richiesta con le chiavi CA ripristinate. Vedere la procedura seguente "Nuova firma di un certificato o di un CRL per estenderne il periodo di validità". Una volta completata l’operazione, eliminare le chiavi dal computer utilizzando la procedura seguente.
  
**Per eliminare le chiavi dal sistema**
  
1.  Accedere come membro del gruppo Amministratori locale ed eliminare il profilo utente dell’account CAKeySigner, utilizzando **Proprietà avanzate** in Risorse del computer.
  
2.  Eliminare l’account CAKeySigner.
  
3.  Cancellare in maniera sicura le aree del disco non allocate per rimuovere permanentemente le tracce delle chiavi utilizzando il seguente comando:
  
    Cipher /W:%AllUsersProfile%
  
    **Nota:** specificando %allusersprofile% come percorso si garantisce che Cipher.exe operi sull’unità contenente i profili utente. Verrà cancellata qualsiasi informazione presente nell’intera unità e non solo il percorso indicato.
  
##### Nuova firma di un certificato o di un CRL per estenderne il periodo di validità
  
Se una CA non è disponibile a causa di un errore del server, è possibile estendere la durata degli elenchi CRL o dei certificati firmando nuovamente il file del certificato o il CRL. Questa azione può essere fondamentale per mantenere il servizio.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Account temporaneo creato durante il ripristino della chiave CA
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:** Certutil.exe
  
###### Dettagli relativi all'attività
  
La nuova firma di un certificato o di un CRL ne estende il periodo di validità. Per impostazione predefinita, viene utilizzato il periodo di validità esistente che viene quindi specificato a partire dalla data della nuova firma, ad esempio, se il periodo di validità del CRL era di un mese, il nuovo periodo di validità sarà di un mese a partire dalla data di apposizione della nuova firma. Se necessario, è possibile specificare un periodo di validità diverso nella riga di comando Certutil.
  
**Per firmare nuovamente un CRL o un certificato**
  
1.  Ottenere una copia del CRL o del certificato che deve essere firmato di nuovo.
  
2.  Accedere ad un computer sul quale è stata precedentemente ripristinata la chiave della CA e il certificato utilizzati per firmare originariamente il certificato o il CRL (vedere la procedura precedente "Ripristino del certificato CA e della coppia di chiavi su un computer temporaneo"). Accedere utilizzando l’account creato in questa procedura.
  
3.  Eseguire il comando seguente, sostituendo *OldFile.ext* con il nome del file del CRL o del certificato e *NewFile.ext* con il nome di output richiesto.
  
    Certutil -sign *OldFile.ext NewFile.ext*
  
4.  Quando viene richiesto il certificato da utilizzare, selezionare il certificato CA.
  
5.  Se si firma nuovamente un CRL, questo adesso dovrebbe essere pubblicato su CDP come richiesto (vedere le procedure per la pubblicazione dei CRL nella sezione "Attività della fase operativa").
  
##### Revoca del certificato di un’entità finale
  
Un certificato può essere revocato per diversi motivi, quali:
  
-   Le funzionalità o i privilegi associati al certificato sono stati revocati dal possessore del certificato.
  
-   La chiave del certificato è stata compromessa.
  
-   La CA che ha emesso il certificato è stata compromessa.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Responsabili certificazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: Snap-in MMC Autorità di certificazione
  
###### Dettagli relativi all'attività
  
Questa procedura descrive le operazioni di revoca del certificato di un’entità finale (ad esempio, un certificato emesso per un’entità diversa da una CA). Seguire le procedure descritte per la revoca di un certificato CA.
  
**Per revocare un certificato**
  
1.  Accedere come membro del gruppo Responsabili certificazione e individuare il certificato da revocare nel database dell’autorità di certificazione (nella console MMC Autorità di certificazione). Utilizzare l’opzione **Filtro** nel menu **Visualizza** della cartella **Certificati emessi** per individuare il certificato.
  
2.  Selezionare il certificato e, nel menu **Attività**, scegliere **Revoca**.
  
3.  Selezionare il codice di motivo appropriato per la revoca. Se il motivo della revoca non è compreso tra i codici motivo predefiniti, selezionare **Non specificato**.
  
    **Importante:** solo il codice motivo **Sospensione certificato** consente di ripristinare il certificato in seguito. Tutti gli altri motivi determinano la disattivazione permanente del certificato. Tuttavia, non utilizzare il motivo **Sospensione certificato** solo perché consente il ripristino del certificato in un secondo momento. Utilizzare questo codice solo se è effettivamente necessaria una sospensione temporanea del certificato.
  
##### Revoca di un certificato orfano
  
Quando si ripristina una CA da un backup a seguito di un errore del server, i certificati emessi tra l’ultimo backup e la condizione di errore potrebbero non essere nel database dei certificati. Questi certificati vengono definiti orfani. Situazioni di questo genere possono verificarsi se i registri della CA vengono distrutti e, dopo il ripristino del backup, non vengono eseguiti nuovamente in relazione al database CA. Se si verifica questa condizione, è impossibile revocare certificati orfani con la normale procedura.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Responsabili certificazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:** Certutil.exe
  
###### Dettagli relativi all'attività
  
Per revocare un certificato orfano, è necessario ottenere una copia del certificato da revocare o il numero di serie di tale certificato.
  
**Per revocare un certificato orfano**
  
1.  Accedere alla CA che ha emesso il certificato da revocare come membro del gruppo Responsabili certificazione.
  
2.  Se non è possibile ottenere una copia del certificato, eseguire il comando seguente per creare un certificato fittizio e salvarlo come CertToRevoke.cer. Sostituire *SerialNumber* con il numero di serie del certificato da revocare.
  
    Certutil -sign *SerialNumber* CertToRevoke.cer
  
3.  Quando richiesto, selezionare il certificato CA corrente per firmare il certificato fittizio.
  
4.  Una volta creato un certificato fittizio (o aver ottenuto una copia del vero certificato da revocare), importarlo nel database della CA. Eseguire il comando seguente per importare il certificato nel database dei certificati. CertToRevoke è una copia del certificato effettivo da revocare oppure un certificato fittizio creato nei passaggi precedenti.
  
    Certutil -importcert CertToRevoke.cer
  
5.  Seguire la procedura standard per revocare un certificato (descritta nella procedura precedente "Revoca del certificato di un’entità finale").
  
    **Importante:** è presente un problema con le versioni di Certutil precedenti a SP1 di Windows Server 2003 che genera un errore di creazione del certificato fittizio su Windows Server 2003. Se si utilizza una versione precedente e non si riesce a individuare la copia del certificato originale, è possibile prendere un certificato esistente e, con un editor binario, sostituire il numero di serie con il numero di serie del certificato da revocare. Questo certificato modificato può essere firmato nuovamente utilizzando il seguente comando:
  
    Certutil -sign ModifiedCert.cer CertToRevoke.cer  
    Il certificato appena creato può essere importato nel database seguendo il passaggio 4 della presente procedura.
  
##### Revoca e sostituzione di un certificato della CA di emissione
  
Se la chiave privata di una CA risulta compromessa (o se si pensa che lo sia), revocare il certificato CA ed emetterne uno nuovo utilizzando una nuova coppia di chiavi.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Responsabili certificazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: Snap-in MMC Autorità di certificazione
  
###### Dettagli relativi all'attività
  
Poiché la CA principale prevede un periodo piuttosto lungo di pubblicazione degli elenchi CRL, la semplice revoca del certificato CA e la pubblicazione di un nuovo CRL darebbe luogo a un ritardo tra l’esecuzione della revoca e la ricezione, da parte degli utenti del certificato, della notifica della revoca. Per garantire che tutti i certificati emessi dalla CA compromessa vengano rifiutati nel più breve tempo possibile, vengono revocati singolarmente anche tutti i certificati emessi da tale CA.
  
**Importante:** tutti gli utenti certificati dovranno registrarsi di nuovo per ottenere i nuovi certificati.
  
**Per revocare il certificato della CA di emissione**
  
1.  Accedere alla CA di emissione come membro del gruppo Responsabili certificazione e aprire lo snap-in MMC Autorità di certificazione.
  
2.  Selezionare tutti i certificati nella cartella Certificati emessi, quindi nel menu **Tutte le attività** fare clic su **Revoca certificato**. Selezionare **Compromesso di CA** per il codice motivo.
  
3.  Aumentare il valore nel campo Intervallo pubblicazione CRL affinché corrisponda alla durata rimanente del certificato CA. In questo modo, si garantisce una maggiore durata rispetto a tutti i certificati emessi dalla CA.
  
4.  Deselezionare la casella di controllo **Pubblica Delta CRL**, se selezionata.
  
5.  Nel menu **Tutte le attività** della cartella Certificati revocati, fare clic su **Pubblica**, quindi fare clic su **Nuovo CRL**.
  
6.  Accedere alla CA principale come membro del gruppo Responsabili certificazione e aprire MMC Autorità di certificazione.
  
7.  Individuare il certificato CA da revocare nella cartella Certificati emessi, quindi nel menu **Tutte le attività** fare clic su clic su **Revoca certificato**. Selezionare **Compromesso chiave** per il codice motivo.
  
8.  Seguire la procedura "Pubblicazione elenco CRL non in linea e certificato CA" nella sezione "Attività della fase operativa" (è possibile ignorare le parti della procedura relative alla pubblicazione del certificato CA).
  
9.  Tornare alla CA di emissione e seguire la procedura "Rinnovo certificato CA di emissione" nella sezione "Attività della fase operativa".
  
Gli utenti certificati possono ora registrarsi nuovamente con la nuova CA. I certificati con registrazione automatica vengono registrati automaticamente.
  
##### Revoca e sostituzione di un certificato della CA principale
  
Se la chiave privata di una CA principale risulta compromessa (o se si pensa che lo sia), è necessario rimuovere il certificato CA e revocare tutti i certificati emessi da tale CA e dalle relative CA subordinate. È necessario rinnovare il certificato della CA principale ed i certificati di tutte le relative CA subordinate con le nuove chiavi, e quindi pubblicarli nuovamente in Active Directory. Generalmente, non è possibile revocare un certificato della CA principale. Spesso, il certificato della CA non include un CDP dal quale controllare lo stato di revoca e, comunque, non è strettamente legale da parte di una CA attestare la propria revoca (infatti, dovrebbe utilizzare il certificato compromesso per firmare il CRL contenente il proprio certificato revocato).
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione:**
  
    -   Responsabili certificazione
  
    -   Amministratori locali sulle CA (per attività secondarie di rinnovo CA)
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: Snap-in MMC Autorità di certificazione
  
###### Dettagli relativi all'attività
  
**Nota:** al termine di questa procedura, tutti gli utenti di certificati devono registrare nuovamente i nuovi certificati.
  
**Per revocare un certificato della CA principale**
  
1.  Accedere alla CA di emissione come membro del gruppo Responsabili certificazione e aprire lo snap-in MMC Autorità di certificazione.
  
2.  Selezionare tutti i certificati nella cartella Certificati emessi, quindi nel menu **Tutte le attività** fare clic su **Revoca certificato**. Selezionare **Compromesso di CA** per il codice motivo.
  
3.  Aumentare il valore nel campo Intervallo pubblicazione CRL affinché corrisponda alla durata rimanente del certificato CA. In questo modo, si garantisce una maggiore durata rispetto a tutti i certificati emessi dalla CA.
  
4.  Deselezionare la casella di controllo **Pubblica Delta CRL** se è selezionata.
  
5.  Nel menu **Tutte le attività** della cartella Certificati revocati, fare clic su **Pubblica**, quindi fare clic su **Nuovo CRL**. Ripetere i passaggi da 1 a 5 per tutte le CA subordinate.
  
6.  Accedere alla CA principale come membro del gruppo Responsabili certificazione e aprire lo snap-in MMC Autorità di certificazione.
  
7.  Selezionare tutti i certificati nella cartella Certificati emessi, quindi nel menu **Tutte le attività** fare clic su **Revoca certificato**. Selezionare **Compromesso di CA** per il codice motivo.
  
8.  Aumentare il valore nel campo Intervallo pubblicazione CRL affinché corrisponda alla durata rimanente del certificato CA. In questo modo, si garantisce una maggiore durata rispetto a tutti i certificati emessi dalla CA.
  
9.  Deselezionare la casella di controllo **Pubblica Delta CRL**, se selezionata.
  
10. Seguire la procedura "Rinnovo certificato CA principale".
  
11. Tornare alla CA di emissione e seguire la procedura "Rinnovo certificato CA di emissione".
  
    Gli utenti certificati possono ora registrarsi nuovamente con la nuova CA. I certificati con registrazione automatica vengono registrati automaticamente.
  
    **Importante:** il rinnovo di un certificato della CA principale è un evento molto importante specialmente nel caso in cui coinvolga la revoca delle CA figlio e dei certificati emessi. Accertarsi che tutti i proprietari dell’applicazione interessati vengano informati sul nuovo certificato principale nel caso in cui debbano configurare questo nuovo certificato principale nella loro applicazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di ottimizzazione
  
Nella fase di ottimizzazione sono incluse le funzioni SMF con cui gestire i costi mantenendo o migliorando i livelli di servizio. Tra tali attività, figura l’analisi delle interruzioni/emergenze, l’esame delle strutture di costo, le verifiche del personale e l’analisi delle prestazioni, così come le previsioni delle capacità.
  
In questa sezione vengono fornite le informazioni relative alle seguenti funzioni SMF:
  
-   Gestione capacità
  
Non esistono attività per le restanti funzioni SMF:
  
-   Gestione del livello del servizio
  
-   Gestione finanziaria
  
-   Gestione disponibilità
  
-   Gestione della continuità del servizio IT
  
-   Gestione forza lavoro
  
    **Nota:** ogni descrizione dell'attività contiene le seguenti informazioni di riepilogo: requisiti di protezione, frequenza e requisiti tecnologici.
  
#### Gestione della capacità
  
La gestione della capacità è il processo di pianificazione, dimensionamento e controllo della capacità della soluzione di servizi in modo da soddisfare la richiesta degli utenti entro i livelli di prestazioni stabiliti nel contratto del livello di servizio. Per soddisfare tale richiesta sono necessarie informazioni relative agli scenari di utilizzo, agli schemi e alle caratteristiche di carico massimo della soluzione di servizi, nonché requisiti di prestazione definiti.
  
##### Definizione del carico massimo per l'autorità di certificazione emittente
  
In questa sezione vengono fornite alcune informazioni sul carico massimo per la CA di emissione.
  
Sebbene normalmente le CA non prevedano un carico molto alto, potrebbero comunque verificarsi condizioni di carico improvviso. Il carico maggiore su una CA avviene generalmente in fase di collegamento o avvio durante la generazione di un nuovo tipo di certificato. Allo stesso modo, sebbene più raramente, se è avvenuta una revoca di massa di certificati o di certificati CA, la nuova registrazione di utenti e computer causa un carico massimo anomalo.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Nessuno
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici**: Nessuno
  
###### Dettagli relativi all'attività
  
Le procedure di test interne di Microsoft hanno mostrato che, per una CA tipica di un’organizzazione di grandi dimensioni, il collo di bottiglia delle prestazioni in condizioni di alto carico è dovuto all’interazione con Active Directory. L’attività di firma ed emissione dei certificati è relativamente leggera rispetto al sovraccarico dell’esecuzione di una ricerca nelle directory per recuperare le informazioni del certificato e quindi della ripubblicazione del certificato su Active Directory.  
Considerare ad esempio le cifre generate in uno scenario tipico di carico massimo, in cui è stato attivato un nuovo tipo di certificato e tutti gli utenti e computer devono registrare i certificati:
  
-   Numero di utenti: 3000
  
-   Numero di computer: 3000
  
-   La velocità di emissione massima approssimativa di una CA di un’organizzazione di grandi dimensioni è di 30 certificati al secondo (o 1800 certificati al minuto).
  
In base a queste cifre, il tempo di registrazione minimo totale è di 3,3 minuti. Per la registrazione contemporanea di 15.000 utenti e dello stesso numero di computer, il tempo necessario sarebbe di 16,6 minuti.
  
È necessario determinare quale potrebbe essere il carico massimo di registrazioni dell'organizzazione e calcolare la durata totale del processo di registrazione. Se tale durata risulta eccessivamente lunga e non è possibile rendere la registrazione più graduale, si consiglia di utilizzare più CA di emissione da distribuire su più siti di Active Directory in modo da associarle a controller di dominio distinti.
  
##### Definizione dei requisiti di archiviazione e backup per un'autorità di certificazione emittente
  
Questa sezione fornisce i dettagli della capacità per i parametri di archiviazione della CA. Tali dettagli consentiranno ai pianificatori della capacità di calcolare i requisiti futuri per l'archiviazione di backup su disco e non in linea.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Nessuno
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: Nessuno
  
###### Dettagli relativi all'attività
  
Le sezioni seguenti riportano i presupposti e i risultati dei calcoli delle dimensioni relativamente a: dimensioni del database CA, dimensioni del registro del database CA, dimensioni del CRL e intervallo di backup (tempo richiesto per il backup del database CA).
  
I calcoli seguenti si basano su questi presupposti:
  
-   3000 utenti, 3000 computer e 100-300 server.
  
-   Ogni entità finale viene emessa con cinque certificati per anno, ciascuno con un periodo di validità di un anno.
  
-   I certificati vengono mantenuti nel database per cinque anni.
  
-   Il backup del database viene eseguito quotidianamente (troncando i registri del database).
  
**Dimensione del database dei certificati**
  
Ciascuna voce del certificato occupa circa 20 KB nel database (per i tipi di certificato in cui la chiave privata viene archiviata con il certificato, calcolare 10 KB aggiuntivi di archiviazione per certificato). Con un rapido calcolo, si arriva ai seguenti risultati:
  
-   Nel database sono sempre presenti 150000 certificati archiviati.
  
-   La dimensione totale del database è di 3 GB.
  
In un'organizzazione con 15000 utenti, la dimensione del database dei certificati è di 15 GB.
  
**Dimensione media del registro del database dei certificati**
  
-   Sono presenti 750 certificati al giorno.
  
-   La dimensione media del registro è di 5 MB.
  
In un'organizzazione con 15000 utenti, vengono emessi 3750 certificati al giorno, con una dimensione massima del registro di 25 MB.
  
**Dimensione del CRL**
  
Una voce CRL è di circa 30 byte e circa il dieci per cento dei certificati emessi viene revocato. I certificati revocati che non rientrano nel relativo periodo di validità non sono inclusi nel CRL.
  
-   Se in qualsiasi momento 30000 certificati rientrano nel periodo di validità,
  
-   nel CRL sono presenti 3000 certificati.
  
-   La dimensione del CRL è di 90 KB.
  
In un'organizzazione di 15000 utenti, 15000 certificati sono presenti nel CRL, la cui dimensione raggiunge i 440 KB.
  
**Intervallo di backup per il database dei certificati**
  
Se si suppone che un backup di rete in funzione in condizioni ideali su 100 Mbps (megabit al secondo) passi al server di backup, il backup di un database di 3 GB più lo stato del sistema di 500 MB può essere eseguito in circa 15-20 minuti. In un'organizzazione con 15000 utenti, il backup di un database dei certificati di 15 GB può essere quindi eseguito in meno di due ore.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di modifica
  
Nella fase di modifica sono inclusi i processi e le procedure necessari a identificare, analizzare, approvare e incorporare le modifiche in un ambiente IT gestito. Le modifiche includono le risorse hardware e software nonché le modifiche di processi e procedure specifici.
  
L’obiettivo del processo di modifica consiste nell’introdurre nuove tecnologie, sistemi, applicazioni, hardware, strumenti, processi e modifiche a ruoli e responsabilità nell’ambiente IT in tempi rapidi e con un’interruzione minima del servizio.
  
In questa sezione vengono fornite le informazioni relative alle seguenti funzioni SMF:
  
-   Gestione delle modifiche
  
-   Gestione della configurazione
  
-   Gestione del rilascio
  
    **Nota:** ogni descrizione dell'attività contiene le seguenti informazioni di riepilogo: requisiti di protezione, frequenza e requisiti tecnologici.
  
#### Gestione delle modifiche
  
La funzione SMF di gestione delle modifiche è responsabile della gestione delle modifiche in un ambiente IT. Obiettivo principale del processo di gestione delle modifiche è assicurare che tutte le parti interessate da una determinata modifica siano consapevoli dell'impatto dell'imminente modifica. Poiché la maggior parte dei sistemi è strettamente correlata, le modifiche apportate a una parte del sistema potrebbero avere ripercussioni su un'altra parte. Per ridurre o eliminare eventuali effetti negativi, il processo di gestione delle modifiche tenta di identificare tutti i sistemi ed i processi interessati prima di rendere effettive le modifiche. In genere, l'ambiente di destinazione, o ambiente gestito, è l'ambiente di produzione; tuttavia, sarebbe opportuno includere gli ambienti di integrazione, test e temporanei principali.
  
Tutte le modifiche apportate all’infrastruttura PKI devono seguire il processo standard di gestione delle modifiche MOF mostrato di seguito:
  
1.  **Richiesta di modifica**. L’inizializzazione formale di una modifica mediante l’invio di una richiesta di modifica (RFC).
  
2.  **Classificazione della modifica**. L’assegnazione di una priorità e di una categoria alla modifica, considerando come criterio l’urgenza e il relativo impatto sull’infrastruttura o sugli utenti. Tale assegnazione influisce sulla velocità e sul percorso dell'implementazione.
  
3.  **Autorizzazione della modifica**. La considerazione e approvazione o disapprovazione della modifica da parte del responsabile delle modifiche e del consiglio di approvazione delle modifiche costituito dai rappresentanti aziendali e IT.
  
4.  **Sviluppo della modifica**. La pianificazione e lo sviluppo della modifica, un processo che può variare molto a seconda degli obiettivi ed include le analisi degli obiettivi chiave.
  
5.  **Rilascio della modifica**. Il rilascio e la distribuzione della modifica nell’ambiente di produzione.
  
6.  **Analisi della modifica**. Un processo successivo all'implementazione che verifica se la modifica ha raggiunto gli obiettivi stabiliti e stabilisce se conservarla oppure ritirarla.
  
In questa sezione viene illustrato come sviluppare alcune delle modifiche principali che probabilmente saranno necessarie regolarmente nell'ambiente in uso. Ciascuna procedura di sviluppo delle modifiche è affiancata da una procedura di rilascio in cui sono descritte le modalità di distribuzione della modifica nella produzione.
  
##### Gestione degli aggiornamenti del sistema operativo
  
La gestione degli aggiornamenti di protezione per Servizi certificati viene trattata all'interno della gestione generale delle patch di Windows. Questo argomento viene trattato da Microsoft in due guide delle soluzioni, che illustrano la distribuzione di aggiornamenti del sistema operativo Windows mediante Microsoft Systems Management Server (SMS) o Microsoft Software Update Services (SUS). Per ulteriori dettagli su come ottenere le guide, vedere la sezione "Ulteriori informazioni" alla fine del capitolo.
  
La gestione delle patch include componenti di gestione del rilascio e componenti di gestione della configurazione, nonché un componente di gestione delle modifiche. Tuttavia, tutte e tre le funzioni SMF sono trattate nei documenti a cui è stato fatto riferimento nel paragrafo precedente.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: Attività di configurazione
  
-   **Requisiti tecnologici**: Infrastruttura di distribuzione degli aggiornamenti di protezione (quale SMS o SUS)
  
##### Aggiunta di un modello di certificato
  
Un nuovo modello di certificato viene aggiunto per consentire l’emissione di un nuovo tipo di certificato, che potrebbe essere richiesto in quanto una nuova applicazione sta per essere distribuita oppure un’applicazione esistente richiede nuove funzionalità. Questa attività può inoltre far parte di un processo di aggiornamento di un tipo di certificato esistente.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori PKI dell'organizzazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: snap-in MMC Modelli di certificato
  
Prima di inviare la relativa richiesta, testare il nuovo tipo di certificato in un ambiente di test che rappresenti l’ambiente di produzione.
  
Documentare la richiesta di un nuovo tipo di certificato e includere:
  
-   I motivi di generazione del nuovo modello
  
-   Una verifica dell’impatto sugli utenti e l’infrastruttura
  
-   Una verifica di eventuali impatti se la modifica non viene eseguita
  
-   I risultati del test della modifica
  
La documentazione deve includere gli aggiornamenti rilevanti ai criteri del certificato e le istruzioni CPS. Deve inoltre essere verificato in termini di priorità ed impatto. Una volta che la modifica è stata approvata può essere implementata (anche se non ancora rilasciata).
  
###### Dettagli relativi all'attività
  
La procedura seguente deve essere eseguita esclusivamente in un ambiente di test. Il processo per l’esecuzione di questa modifica nell’ambiente di produzione è descritta nella procedura "Rilascio di un nuovo modello di certificato".
  
**Per implementare un nuovo modello di certificato**
  
1.  Accedere come membro del gruppo Amministratori PKI dell'organizzazione e aprire lo snap-in MMC Modelli di certificato.
  
2.  I nuovi modelli di certificato vengono creati copiando un modello esistente. Selezionare un modello appropriato sul quale basare il nuovo modello, che sia il più simile possibile al modello che si desidera creare.
  
    **Importante:** accertarsi che il tipo di modello di base (utente o computer) del modello originale corrisponda al tipo soggetto del nuovo modello; questo non può essere modificato con l’editor di modelli.
  
3.  Modificare i dettagli del modello come richiesto. Per informazioni dettagliate, consultare la documentazione del prodotto nel sistema di guida locale oppure in linea all’indirizzo del riferimento presente nella sezione "Ulteriori informazioni".
  
4.  Se questo modello sostituisce un modello esistente, è necessario aggiungere i modelli sostitutivi all’elenco dei **modelli sostituiti** nelle proprietà del nuovo modello. È necessario accertarsi che il modello sostitutivo fornisca le stesse funzionalità del modello sostituito. Ridurre le funzionalità solo se si è certi che nessuna applicazione utilizzi le funzionalità rimosse.
  
5.  Controllare che le modifiche funzionino come previsto e non influiscano negativamente sulle applicazioni esistenti.
  
6.  Apportare le modifiche appropriate al documento dei criteri del certificato e ai CPS.
  
7.  Seguire i passaggi descritti nelle procedure "Rilascio di un nuovo modello di certificato" e "Rilascio di un nuovo CPS" (se si pubblicano i CPS).
  
##### Aggiornamento di un modello di certificato
  
Questa attività descrive come apportare modifiche secondarie ai modelli di certificato. Le modifiche principali devono essere apportate duplicando il modello e imponendo il nuovo modello in modo da sostituire il modello esistente (come descritto nell'attività precedente "Aggiunta di un modello di certificato").
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori PKI dell'organizzazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: snap-in MMC Modelli di certificato
  
###### Dettagli relativi all'attività
  
Apportare modifiche ad un modello di certificato solo se si tratta di modifiche secondarie che non hanno un impatto significativo sugli utenti dei certificati. È più difficile controllare l’impatto delle modifiche del modello ed è estremamente più complesso ripristinarle.
  
Esempi di modifiche secondarie:
  
-   Modifica del periodo di validità o di rinnovo
  
-   Aggiunta (ma non rimozione) di un tipo di CSP consentito
  
Implementare qualsiasi modifica che influisce sulla funzionalità dei certificati (ad esempio, la modifica dei criteri dei certificati, la rimozione di tipi di CSP e la modifica dei criteri di emissione) creando un nuovo tipo di modello e sostituendo il modello precedente.
  
Valutare ed approvare la richiesta di modifica come descritto nella procedura "Aggiunta di un modello di certificato".
  
È possibile implementare e testare la modifica di modello proposta passando la modifica per il rilascio in produzione. Vedere la procedura "Rilascio di un aggiornamento del modello".
  
**Per aggiornare un modello di certificato**
  
1.  Accedere come membro del gruppo Amministratori PKI dell'organizzazione e caricare lo snap-in Modelli di certificato in una console MMC.
  
2.  Aprire il modello da modificare ed apportare le modifiche richieste. Per informazioni dettagliate, consultare la documentazione del prodotto nel sistema di guida locale oppure in linea all’indirizzo del riferimento presente nella sezione "Ulteriori informazioni".
  
3.  Testare l’aggiornamento per essere sicuri che produca la funzionalità richiesta.
  
4.  Seguire i passaggi descritti nelle procedure "Rilascio di un nuovo modello di certificato" e "Rilascio di un nuovo CPS" (se appropriato).
  
##### Rimozione di un modello di certificato
  
Quando un modello di certificato non è più necessario, può essere rimosso dallo stato attivo oppure può essere rimosso completamente dalla directory.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori CA
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Snap-in MMC Modelli di certificato
  
    -   Snap-in MMC Autorità di certificazione
  
###### Dettagli relativi all'attività
  
Rimuovere un modello solo quando si è certi che nessuna applicazione utilizzi certificati di quel tipo. Valutare ed approvare la richiesta di rimozione del modello seguendo le modalità descritte nella procedura "Aggiunta di un modello di certificato". Seguire sempre la prima procedura per rimuovere un modello dallo stato di uso attivo e testarne gli effetti prima di eliminare completamente un modello dalla directory.
  
È possibile quindi implementare e testare la rimozione della modifica del modello prima di passare la modifica per il rilascio in produzione. Vedere la procedura "Rilascio della rimozione di un modello".
  
**Per rimuovere un modello di certificato dall’uso attivo**
  
1.  Accedere come membro del gruppo Amministratori CA e caricare lo snap-in Autorità di certificazione in una console MMC.
  
2.  Nella cartella Modelli di certificato, fare clic con il pulsante destro del mouse sul modello da rimuovere e selezionare **Elimina**.
  
3.  Ripetere i passaggi 1 e 2 per tutte le CA di emissione che attualmente emettono questo tipo di certificato.
  
4.  Testare tutte le applicazioni che utilizzavano in precedenza questo modello per accertarsi che non dipendano più da questo tipo di certificato.
  
5.  Seguire i passaggi descritti nelle procedure "Rilascio della rimozione di un modello" e "Rilascio di un nuovo CPS" (se appropriato).
  
**Per rimuovere completamente un modello di certificato dalla directory**
  
1.  Accedere come membro del gruppo Amministratori PKI dell'organizzazione e caricare lo snap-in Modelli di certificato in una console MMC.
  
2.  Fare clic con il pulsante destro del mouse sul modello da rimuovere e selezionare **Elimina**.
  
#### Gestione della configurazione
  
La funzione SMF di gestione della configurazione è responsabile dell’identificazione, della registrazione e delle attività di analisi e reporting dei componenti o delle risorse chiave IT chiamati elementi di configurazione. Le informazioni acquisite e di cui viene tenuta traccia dipendono dall’elemento di configurazione specifico, ma spesso includono una descrizione dall’elemento di configurazione, la versione, i componenti costituenti, le relazioni con gli altri elementi di configurazione, la posizione/assegnazione e lo stato corrente.
  
La gestione della configurazione di un’infrastruttura PKI può essere suddivisa in diverse aree principali:
  
-   **Configurazione dell'infrastruttura PKI di un'organizzazione di grandi dimensioni**. Informazioni comuni archiviate in Active Directory.
  
-   **Configurazione del modello di certificato**. Dettagli della configurazione di tutti i modelli attivi.
  
-   **Configurazione della CA.** Dettagli della configurazione specifici della CA.
  
-   **Gruppi di gestione della CA e dell’infrastruttura PKI**. Dettagli dei gruppi e degli utenti di gestione dell’infrastruttura PKI e relative autorizzazioni.
  
-   **Configurazione dei client.** Configurazione delle impostazioni utente e computer mediante criteri di gruppo (o altri metodi).
  
Ognuna delle seguenti sezioni descrive questi elementi in maggior dettaglio e include metodi per l’automazione della raccolta di queste informazioni, dove possibile.
  
Per ulteriori informazioni sulla gestione della configurazione, vedere la sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
##### Raccolta informazioni sulla configurazione dell'infrastruttura PKI dell'organizzazione di grandi dimensioni
  
Le informazioni sulla configurazione a livello di organizzazione di grandi dimensioni sono archiviate in Active Directory e includono informazioni attendibili sulla CA principale, sulla configurazione CA dell’organizzazione e sugli annunci. Includono inoltre i modelli di certificato che verranno trattati in una procedura successiva.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Utenti di dominio
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Certutil.exe
  
    -   DSQuery.exe
  
###### Dettagli relativi all'attività
  
Registrare le seguenti informazioni archiviate in Active Directory:
  
-   Autorità di certificazione principali attendibili
  
-   Archivio NTAuth
  
-   Servizi di registrazione (CA dell’organizzazione di grandi dimensioni)
  
-   Certificati incrociati
  
-   CRL pubblicati
  
I comandi per raccogliere queste informazioni vengono forniti nelle procedure seguenti.
  
**Importante:** nei comandi seguenti è necessario sostituire il nome distinto (DN, Distinguished Name) del dominio principale, *DC=woodgrovebank,DC=com*, con il DN del dominio principale del *proprio* insieme di strutture.
  
**Nota:** alcuni comandi appaiono su più righe per questioni di leggibilità ma devono essere immessi come singola riga.
  
**Per visualizzare le autorità di certificazione principali attendibili**
  
certutil -store -enterprise Root
  
**Per visualizzare gli archivi NT Auth**
  
certutil -store -enterprise NTAuth
  
**Per visualizzare i certificati delle CA dell’organizzazione di grandi dimensioni corrente**
  
certutil -store -enterprise "ldap:///cn=Enrollment Services,CN=Public Key Services,CN=Services,CN=Configuration,  
*DC=woodgrovebank,DC=com*?cACertificate?one?  
objectClass=pkiEnrollmentService"
  
**Per visualizzare i certificati incrociati e intermedi**
  
certutil -store -enterprise CA
  
**Per visualizzare i certificati della CA intermedia**
  
certutil -store -enterprise "ldap:///cn=AIA,CN=Public Key Services,CN=Services,CN=Configuration, *DC=woodgrovebank,DC=com*?cACertificate?one?  
objectClass=certificationAuthority"
  
**Per visualizzare certificati incrociati**
  
certutil -store -enterprise "ldap:///cn=AIA,CN=Public Key Services,CN=Services,CN=Configuration, *DC=woodgrovebank,DC=com*?cRossCertificatePair?one?  
objectClass=certificationAuthority"
  
**Per visualizzare i CRL attualmente pubblicati**
  
1.  Questo comando visualizza i **nomi dei server** di tutte le CA che hanno pubblicato i CDP nel contenitore CDP di Active Directory:
  
    dsquery \* "cn=CDP,cn=Public Key Services,cn=Services, cn=Configuration,*DC=woodgrovebank,DC=com*" -attr cn -scope onelevel
  
2.  Questo comando visualizza i CDP di tutte le CA che hanno pubblicato CRL nel contenitore CDP di Active Directory. I CDP rappresentano gli oggetti figlio degli oggetti server visualizzati nell'elenco precedente. Per assegnare un nome a ciascun oggetto CDP, la CA utilizza il nome comune. Tenere presente che una CA creerà un nuovo CDP per ogni versione della CA (incrementato ogni volta che la CA viene rinnovata); tali nomi vengono archiviati come "CACommonName(X)" dove X è il numero di versione della CA:
  
    dsquery \* "cn=CDP,cn=Public Key Services,cn=Services, cn=Configuration, *DC=woodgrovebank,DC=com*" -attr cn -filter (objectclass=crlDistributionPoint)
  
3.  3. Con le informazioni fornite in precedenza, è possibile visualizzare il CRL di un determinato CDP (utilizzando i nomi comuni della CA descritti nel passaggio 2 e i nomi server ottenuti nel passaggio 1):
  
    certutil -store -enterprise "ldap:///cn=*Woodgrove Bank Root CA*,cn=*HQ-CA-01*,cn=CDP,CN=Public Key Services,CN=Services,CN=Configuration, *DC=woodgrovebank,DC=com*?certificateRevocationList?base?objectClass=cRlDistributionPoint"
  
    **Importante:** sostituire "Woodgrove Bank Root CA" con il nome comune della CA, "HQ-CA-01" con il nome dell’host della CA e "DC=woodgrovebank,DC=com" con il DN del dominio principale dell’insieme di strutture.
  
    **Nota**: per automatizzare questo comando nel caso in cui fosse necessario eseguirlo regolarmente, è possibile scrivere un semplice script di file di comando (batch).
  
##### Raccolta informazioni sulla configurazione del modello di certificato
  
I modelli di certificato sono archiviati in Active Directory. Registrare la configurazione di ciascun modello e registrare le autorizzazioni per la registrazione dei certificati utilizzate per ciascun modello.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Utenti di dominio
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:** Certutil.exe
  
###### Dettagli relativi all'attività
  
Utilizzare i seguenti comandi per raccogliere le informazioni di configurazione specificate:
  
**Per produrre un elenco dei modelli configurati in Active Directory**
  
Certutil -template
  
**Per eseguire il dump della configurazione di questi modelli**
  
Certutil -dsTemplate
  
**Per eseguire il dump delle autorizzazioni di un modello**
  
Dsacls "cn=TemplateName,cn=Certificate Templates,cn=Public Key Services,cn=Services,cn=Configuration,*DC=woodgrovebank,DC=com*"
  
Non esistono strumenti che consentano di esportare le autorizzazioni complete dei modelli in un formato facilmente leggibile. Dsacls.exe consente di visualizzare le autorizzazioni di un modello. Tuttavia, la versione corrente non consente di visualizzare le autorizzazioni di registrazione automatica con diritti estesi (sebbene consenta la visualizzazione di autorizzazioni di registrazione e di altri tipi di autorizzazione con diritti estesi). Ciò comporta la necessità di registrare manualmente le autorizzazioni di registrazione automatica. In alternativa, è possibile creare uno script o uno strumento utilizzando Active Directory Services Interface (ADSI) per leggere e visualizzare correttamente tutte le autorizzazioni.
  
##### Raccolta informazioni sulla configurazione CA
  
Questa sezione descrive come recuperare le informazioni di configurazione archiviate localmente su ciascuna CA e, nel caso di CA dell’organizzazione di grandi dimensioni, alcune informazioni archiviate in Active Directory.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori locali sulla CA
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:** Certutil.exe
  
###### Dettagli relativi all'attività
  
Registrare le seguenti informazioni:
  
-   Informazioni sul registro CA
  
-   Informazioni sul certificato CA
  
-   Autorizzazioni CA
  
-   Modelli CA assegnati
  
-   CPS della CA
  
-   Utilizzare i seguenti comandi per raccogliere le informazioni di configurazione specificate:
  
**Per visualizzare la configurazione del registro CA**
  
Certutil -getreg
  
Certutil -getreg CA
  
**Per visualizzare il certificato CA corrente**
  
certutil -f -ca.cert %temp%\\CAcert.cer &gt; nul && certutil -dump %temp%\\CACert.cer
  
**Nota:** alcuni comandi appaiono su più righe per questioni di leggibilità ma devono essere immessi come singola riga.
  
Non esistono strumenti che consentano di esportare le autorizzazioni della CA in un formato utilizzabile, sebbene sia possibile creare uno script ADSI per leggere e visualizzare correttamente tali autorizzazioni. In alternativa, registrare manualmente queste informazioni.
  
**Per visualizzare i modelli attualmente assegnati a questa CA**
  
Certutil -CATemplates
  
Il file CPS della CA deve essere mantenuto con un controllo di versione adeguato in modo tale che sia semplice identificare e recuperare il CPS attivo in un determinato momento.
  
##### Raccolta informazioni sui gruppi di gestione dell'infrastruttura PKI e dell'autorità di certificazione
  
L’appartenenza ai gruppi di gestione dell’infrastruttura PKI è una parte molto importante delle informazioni di configurazione in quanto questi gruppi hanno il controllo su tutti gli aspetti delle informazioni sull’infrastruttura PKI dell’organizzazione e sulle CA.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Utenti di dominio
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: Net.exe
  
###### Dettagli relativi all'attività
  
Per ognuno dei gruppi dell’amministrazione dell’infrastruttura PKI e dell’autorità di certificazione, elencare e registrare l’appartenenza corrente. Se uno qualsiasi dei membri è un gruppo (indicato da un asterisco prima del nome), elencare l’appartenenza di questi gruppi fino a quando non si ottiene l’elenco completo degli utenti membri dei gruppi dell’infrastruttura PKI.
  
I gruppi predefiniti sono:
  
-   Enterprise PKI Admins
  
-   Enterprise PKI Publishers
  
-   CA Admins
  
-   Certificate Managers
  
-   CA Auditors
  
-   CA Backup Operators
  
Se sono stati creati, includere anche eventuali altri gruppi di gestione.
  
**Per elencare l’appartenenza di ciascun gruppo**
  
Net groups *groupname* /domain
  
##### Raccolta informazioni sulla configurazione del client di certificato
  
Questa attività si riferisce alle informazioni di configurazione del client distribuite mediante il processo Criteri di gruppo. Se si utilizza un altro meccanismo, ad esempio SMS o script di accesso, per distribuire le impostazioni del client correlate all’infrastruttura PKI, documentare anche queste procedure.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratore con le autorizzazioni per la gestione degli oggetti di criteri di gruppo
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: Console di gestione Criteri di gruppo
  
###### Dettagli relativi all'attività
  
Utilizzare la console di gestione di criteri di gruppo (GPMC) per raccogliere ed elencare le informazioni sulla configurazione del client PKI. Per informazioni su come ottenere e utilizzare la console di gestione Criteri di gruppo, vedere il riferimento contenuto nella sezione "Ulteriori informazioni".
  
#### Gestione del rilascio
  
L’obiettivo della gestione del rilascio consiste nel facilitare l’introduzione di rilasci software e hardware negli ambienti IT gestiti. Generalmente include l’ambiente di produzione e gli ambienti di preproduzione gestiti. La gestione del rilascio è il punto di coordinamento tra i gruppi di sviluppo/progetto del rilascio ed i gruppi operativi responsabili della distribuzione del rilascio in produzione.
  
In questa sezione vengono trattate le modifiche più comuni, quali aggiunta, modifica e rimozione di tipi di certificato (usando i modelli di certificato). Altri tipi di modifiche devono, inoltre, essere rilasciate nello stesso modo sistematico:
  
-   **Modifiche alla configurazione dell’infrastruttura PKI** Alcuni esempi di modifiche includono i modelli e gli oggetti OID.
  
-   **Modifiche alla configurazione della CA** Registro di sistema locale più le impostazioni di Active Directory in oggetti di registrazione.
  
-   **Modifiche alla configurazione del client** Modifiche GPO
  
Tutte le procedure di rilascio seguono il processo generale descritto di seguito:
  
1.  Preparazione del rilascio delle modifiche; backup della configurazione esistente.
  
2.  Test delle modifiche in modo controllato.
  
3.  Distribuzione delle modifiche in modo controllato per numeri limitati di utenti e computer.
  
4.  Ripristino delle modifiche in caso di errore: configurazione di Active Directory e CA.
  
##### Rilascio di un nuovo modello di certificato
  
L’introduzione di un nuovo modello di certificato rappresenta un cambiamento importante per l’ambiente IT, quindi il rilascio deve essere gestito in modo controllato e reversibile.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione:**
  
    -   Enterprise PKI Admins
  
    -   CA Admins
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Snap-in MMC Autorità di certificazione
  
    -   Snap-in MMC Modelli di certificato
  
    -   Altri strumenti in base a quanto richiesto dalle attività dipendenti
  
###### Dettagli relativi all'attività
  
Il rilascio di un nuovo modello di certificato nell’ambiente di produzione viene descritto nella procedura seguente.
  
**Per rilasciare un nuovo modello di certificato**
  
1.  Eseguire il backup della configurazione del modello di certificato esistente. Questa operazione può essere eseguita come parte del backup regolare di Active Directory o mediante la tecnica descritta nella procedura "Esportazione di un modello di certificato da Active Directory".
  
2.  Creare il nuovo modello come descritto nella procedura "Aggiunta di un modello di certificato".
  
3.  Rimuovere tutte le autorizzazioni di registrazione e registrazione automatica per i gruppi (cercare oggetti quali utenti autenticati e utenti di dominio). Creare il gruppo di registrazione dei certificati (e/o gruppo di registrazione automatica) per il modello come descritto nella procedura "Creazione di gruppi di registrazione modelli di certificato".
  
4.  Aggiungere il nuovo modello di certificato alla CA di emissione. Se non si è anche membro del gruppo Amministratori CA, è necessario accedere (o utilizzare il comando runas) come membro di questo gruppo ed eseguire MMC Autorità di certificazione. Fare clic con il pulsante destro del mouse sulla cartella Modelli di certificato e selezionare **Nuovo**, quindi **Modello di certificato da emettere**. Aggiungere il modello dall’elenco.
  
5.  Aggiungere gli utenti o computer pilota o di test al gruppo di registrazione dei certificati come descritto nella procedura "Attivazione della registrazione (o registrazione automatica) di un tipo di certificato per un utente o un computer".
  
6.  Verificare che la registrazione del nuovo tipo di certificato funzioni come previsto.
  
7.  Verificare che le funzionalità del certificato siano come previsto.
  
8.  Una volta terminato il test, aggiungere gli utenti, i computer o i gruppi di protezione di produzione finale al gruppo di registrazione dei certificati come descritto nella procedura "Attivazione della registrazione (o registrazione automatica) di un tipo di certificato per un utente o un computer".
  
9.  Se questo modello sostituisce uno o più modelli esistenti, è possibile rimuovere i modelli sostituiti dalla CA di emissione (mediate lo snap-in MMC Autorità di certificazione) per evitare la registrazione di questi tipi di certificato sostituiti. Non eliminare questo modello dalla directory fino a quando non si è certi che tutti utilizzino il nuovo tipo di modello.
  
10. Se necessario, aggiornare il CPS per riflettere la funzionalità del nuovo certificato.
  
Il ripristino di un nuovo tipo di modello è relativamente semplice solo se i modelli sostituiti non sono stati eliminati. Se il modello sostituito è stato eliminato, è necessario ripristinarne una copia dal backup, utilizzando un ripristino autorevole di Active Directory o le procedure di esportazione e importazione dei modelli descritte nella sezione "Gestione dell’archiviazione" ("Esportazione di un modello di certificato da Active Directory" e "Importazione di un modello di certificato in Active Directory").
  
**Per ripristinare l’aggiunta di un nuovo modello**
  
1.  Se non sono stati sostituiti altri modelli con questo modello, è possibile semplicemente eliminarlo.
  
2.  Se è stato rimosso qualsiasi modello sostituito da questo modello, ripristinarlo seguendo i passaggi descritti nella procedura "Importazione di un modello di certificato in Active Directory". È necessario ripristinare le autorizzazioni del modello come descritto nella procedura.
  
##### Rilascio di un nuovo CPS
  
Se si pubblica il CPS, è necessario aggiornarlo per riflettere le modifiche delle procedure operative e dei criteri del certificato nell’organizzazione.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratore con le autorizzazioni per modificare il file CPS sul server Web
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici**: Editor di testo o HTML a seconda del formato del file CPS
  
###### Dettagli relativi all'attività
  
Il file CPS è generalmente archiviato come semplice file di testo o HTML su un server di file o Web. Se questo CPS è condiviso tra più CA, nello stesso file sono presenti i riferimenti di tutte le CA.
  
**Per rilasciare un nuovo file CPS**
  
1.  Eseguire il backup del file CPS esistente.
  
2.  Apportare le modifiche richieste su una copia non in linea.
  
3.  Sostituire il CPS.
  
4.  Verificare che il nuovo file CPS sia leggibile da client che emulano i tipi di piattaforma e le posizioni normalmente gestite.
  
##### Rilascio di un aggiornamento del modello
  
Questa attività descrive come apportare le modifiche di rilascio a modelli di certificato esistenti in modo controllato e reversibile.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori PKI dell'organizzazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Snap-in MMC Modelli di certificato
  
    -   Altre tecnologie a seconda delle procedure
  
###### Dettagli relativi all'attività
  
Apportare modifiche a modelli di certificato solo se si tratta di modifiche secondarie che non hanno un impatto significativo sugli utenti dei certificati. È più difficile controllare l’impatto delle modifiche del modello ed è estremamente più complesso ripristinarle.
  
**Per rilasciare l’aggiornamento di un modello di certificato**
  
1.  Esportare il modello corrente su un file mediante la procedura "Esportazione di un modello di certificato da Active Directory".
  
2.  Accedere come membro del gruppo Amministratori PKI dell'organizzazione e caricare lo snap-in Modelli di certificato in una console MMC. Apportare le modifiche al modello come descritto in "Aggiornamento di un modello di certificato".
  
3.  Aggiornare il file CPS e seguire i passaggi della procedura "Rilascio di un nuovo CPS" (se appropriato)
  
**Per ripristinare l’aggiornamento di un modello di certificato**
  
-   Seguire i passaggi della procedura "Importazione di un modello di certificato in Active Directory" nella sezione "Gestione dell’archiviazione".
  
##### Rilascio della rimozione di un modello
  
Quando un modello di certificato non è più necessario, può essere rimosso dall’uso attivo oppure può essere rimosso completamente dalla directory.
  
###### Informazioni di riepilogo
  
-   **Requisiti di protezione**: Amministratori PKI dell'organizzazione
  
-   **Frequenza**: In base alle esigenze
  
-   **Requisiti tecnologici:**
  
    -   Snap-in MMC Autorità di certificazione
  
    -   Altre tecnologie a seconda delle attività
  
###### Dettagli relativi all'attività
  
La procedura di rilascio per la rimozione di un modello dall’uso attivo è relativamente facile in quanto è semplice da ripristinare. La rimozione del modello dalla directory è più problematica in quanto richiede che il modello venga reimportato per invertire la modifica.
  
**Per rimuovere un modello di certificato dall’uso attivo**
  
1.  Rimuovere il modello dalle CA di emissione correnti come descritto nella procedura "Rimozione di un modello di certificato".
  
2.  Aggiornare il file CPS e seguire i passaggi della procedura "Rilascio di un nuovo CPS" (se appropriato).
  
**Per ripristinare la rimozione di un modello dall’uso attivo**
  
1.  Accedere come membro del gruppo Amministratori CA e utilizzare lo snap-in MMC Autorità di certificazione per aggiungere nuovamente i modelli alle CA di emissione.
  
2.  Aggiornare il file CPS e seguire i passaggi della procedura "Rilascio di un nuovo CPS" (se appropriato).
  
**Per rimuovere completamente un modello di certificato dalla directory**
  
1.  Eseguire questa procedura solo dopo che il modello di certificato è stato rimosso dall’uso attivo e tutte le applicazioni dipendenti siano state testate in modo da garantire che non vi siano impatti negativi su di esse.
  
2.  Esportare il modello corrente in un file mediante la procedura "Esportazione di un modello di certificato da Active Directory".
  
3.  Seguire la procedura "Rimozione di un modello di certificato" per rimuovere completamente un modello di certificato dalla directory.
  
**Per ripristinare la rimozione di un modello dalla directory**
  
-   Seguire la procedura di reimportazione del modello eliminato in "Importazione di un modello di certificato in Active Directory".
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Risoluzione dei problemi
  
La risoluzione dei problemi fa riferimento sia agli SMF di gestione delle emergenze che agli SMF di gestione dei problemi. La gestione delle emergenze riguarda il ripristino del servizio il prima possibile. La gestione dei problemi riguarda l’identificazione delle cause principali dei problemi e tenta di garantire che non si verifichino nuovamente.
  
Questa sezione è strettamente correlata alla sezione "Attività della fase di supporto". Molte delle procedure di risoluzione dei problemi riportate in questo documento fanno riferimento alle attività trattate in questa sezione.
  
Le emergenze più comuni che potrebbero verificarsi sono trattate in questa sezione, insieme alle procedure e alle strategie da adottare per risolverle. L’obiettivo principale è quello di ripristinare il servizio il prima possibile. In alcuni casi, la procedura di risoluzione dei problemi costituisce un semplice riferimento ad una procedura di supporto ma, in altri casi, comprende una procedura diagnostica più complessa.
  
Nella tabella seguente sono elencati i principali problemi di supporto e le relative modalità di risoluzione. Nella colonna **Processo supporto,** sono elencate le procedure da seguire. Queste procedure sono descritte in dettaglio nella sezione "Attività della fase di supporto". Se non è riportato alcun processo, fare riferimento alla procedura diagnostica appropriata per il problema descritta nella sezione successiva.
  
**Tabella 11.15. Principali problemi di supporto**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Problema</p></th>  
<th><p>Descrizione</p></th>  
<th><p>Processo supporto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Server non risponde</p></td>
<td style="border:1px solid black;"><p>Il processo software non risponde alle richieste dei client o agli strumenti di amministrazione.</p></td>
<td style="border:1px solid black;"><p>Riavvio di Servizi certificati<br />
oppure<br />
Riavvio del server CA</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Pubblicazione CRL non riuscita</p></td>
<td style="border:1px solid black;"><p>Il CRL è stato emesso dalla CA, ma l’ultimo CRL non è stato pubblicato in Active Directory e/o nel Web.</p></td>
<td style="border:1px solid black;"><p>Vedere la procedura per la risoluzione dei problemi descritta di seguito.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>CRL non emesso</p></td>
<td style="border:1px solid black;"><p>Il CRL aggiornato non è stato emesso dalla CA.</p></td>
<td style="border:1px solid black;"><p>Vedere la procedura completa per la risoluzione dei problemi descritta di seguito.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Il client non può registrare</p></td>
<td style="border:1px solid black;"><p>La richiesta di registrazione del client non è riuscita.</p></td>
<td style="border:1px solid black;"><p>Vedere la procedura completa per la risoluzione dei problemi descritta di seguito.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Il client non può registrare automaticamente il certificato</p></td>
<td style="border:1px solid black;"><p>La richiesta di registrazione automatica del client non è riuscita.</p></td>
<td style="border:1px solid black;"><p>Vedere la procedura completa per la risoluzione dei problemi descritta di seguito.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Aggiornamento della protezione installato richiede riavvio</p></td>
<td style="border:1px solid black;"><p>L'aggiornamento della protezione è installato ma richiede il riavvio di Windows.</p></td>
<td style="border:1px solid black;"><p>Riavvio del server CA</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Errore server permanente</p></td>
<td style="border:1px solid black;"><p>Errore hardware o danneggiamento che richiede il ripristino.</p></td>
<td style="border:1px solid black;"><p>Ripristino CA da backup</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Certificato orfano deve essere revocato</p></td>
<td style="border:1px solid black;"><p>Dopo il ripristino della CA, tutti i certificati emessi dopo l’ultimo backup non sono presenti nel database. Questi certificati non possono essere revocati secondo la normale procedura.</p></td>
<td style="border:1px solid black;"><p>Revoca di un certificato orfano</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Il server non può essere ripristinato in tempo per l’emissione del certificato o del CRL</p></td>
<td style="border:1px solid black;"><p>È necessario firmare nuovamente il CRL o il certificato con la chiave CA per prolungare il periodo di validità.</p></td>
<td style="border:1px solid black;"><p>Sequenza di attività:<br />
1. Ripristino del certificato CA su un computer temporaneo<br />
2. Nuova firma di un certificato o di un CRL per estenderne la validità</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Il certificato dell’entità finale è compromesso</p></td>
<td style="border:1px solid black;"><p>La chiave privata del certificato è stata persa, divulgata o comunque compromessa.</p></td>
<td style="border:1px solid black;"><p>Revoca del certificato di un’entità finale</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Il certificato della CA di emissione è compromesso</p></td>
<td style="border:1px solid black;"><p>La chiave privata del certificato CA è stata persa, divulgata o comunque compromessa.</p></td>
<td style="border:1px solid black;"><p>Revoca e sostituzione di una CA di emissione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Il certificato della CA principale è compromesso</p></td>
<td style="border:1px solid black;"><p>La chiave privata del certificato CA è stata persa, divulgata o comunque compromessa.</p></td>
<td style="border:1px solid black;"><p>Revoca e sostituzione di una CA principale</p></td>
</tr>  
</tbody>  
</table>
  
#### Procedure complete di risoluzione dei problemi
  
In questa sezione sono descritte alcune procedure di risoluzione dei problemi che potrebbero risultare utili per la diagnosi e la risoluzione dei alcuni dei problemi riportati nella tabella precedente. Le procedure riguardano la risoluzione dei problemi comuni seguenti:
  
-   Problemi di pubblicazione del CRL
  
-   CRL non emesso
  
-   Il client non può registrare
  
-   Il client non può registrare automaticamente un certificato
  
##### Problemi di pubblicazione del CRL
  
I problemi di pubblicazione del CRL verranno indicati da un avviso prodotto dallo script CheckCRLs descritto nella sezione "Monitoraggio e controllo servizi". Questo avviso viene emesso tempestivamente quando si verifica un errore nella pubblicazione di un CRL in Active Directory e/o nel server Web. Se il problema non viene risolto, le applicazioni che richiedono i controlli delle revoche inizieranno a non funzionare correttamente.
  
Esaminare la voce del Registro eventi delle applicazioni prodotta da CheckCRLs. Tale voce dovrebbe indicare in modo più preciso la natura del problema e a quale CA appartiene il problema CDP o CRL. Il problema sarà uno dei seguenti:
  
-   Un CRL aggiornato è stato emesso dalla CA. Questo errore indica qualche problema legato alla CA stessa.
  
-   Il CRL è stato emesso ma non è stato pubblicato correttamente in uno o più dei CDP. Ciò può indicare un problema con la CA, con le comunicazioni tra la CA e il CDP o con il servizio CDP stesso (Active Directory o IIS).
  
-   Il CRL è stato prodotto e pubblicato ma non è recuperabile da una o più ubicazioni CDP. Questo errore indica un problema con il servizio CDP.
  
**Per risolvere i problemi di pubblicazione CRL**
  
1.  Accedere alla CA dove sono stati rilevati i problemi e verificare che il CRL della CA di emissione sia aggiornato. Immettere i seguenti comandi per visualizzare il CRL delle CA (per eseguire il primo di questi due comandi, è necessario essere un membro del gruppo Amministratori CA).
  
    Certutil -getCRL %temp%\\CA.crl
  
    Certutil -dump %temp%\\CA.crl
  
2.  Se il CRL non è aggiornato, vedere la procedura successiva "CRL non emesso".
  
3.  Aprire lo strumento Integrità PKI e controllare le voci CDP per la CA in errore. Questo strumento indica qualsiasi CDP non accessibile e CRL scaduti (sebbene non avvisi su CRL non ancora scaduti ma pronti per il rinnovo; ovvero, quando la data specificata in **Pubblicazione successiva CRL** è trascorsa).
  
    **Nota:** è possibile ottenere lo strumento Integrità PKI disponibile in Windows Server 2003 Resource Kit. I riferimenti relativi a tale strumento sono forniti alla fine del presente capitolo.
  
4.  Se qualsiasi CDP viene mostrato come non accessibile, controllare il servizio di pubblicazione di tale CDP.
  
5.  Se dal Registro eventi viene mostrato un errore con CDP LDAP, controllare il collegamento al controller di dominio di Active Directory dalla CA che utilizza lo strumento DCDiag compreso negli Strumenti di supporto di Windows 2003. In questo modo, è possibile verificare la presenza di problemi con il controller di dominio o legati alla connettività CA con il controller di dominio. Controllare tutti gli errori.
  
6.  Controllare le autorizzazioni sul contenitore CDP per la CA utilizzando i siti di Active Directory e lo snap-in MMC Servizi. In "cn=CDP,cn=Public Key Services,cn=Services, cn=Configuration,*DC=woodgrovebank,DC=com"* sostituire le voci in corsivo con il DN per il dominio principale dell’insieme di strutture.
  
7.  Creare un account temporaneo e aggiungerlo al gruppo Autori certificazione. Accedere con tale account e tentare di pubblicare manualmente il CRL recuperato nel passaggio 1 nella directory. Utilizzare il comando seguente:
  
    certutil -dspublish CA.crl *CAHostname* *CASubjectName*.
  
    Questo comando indica se le CA dispongono di autorizzazioni sufficienti a pubblicare in Active Directory.
  
8.  Se viene mostrato un errore (nella voce del Registro eventi) con CDP HTTP, controllare se è coinvolto il server IIS. Controllare connettività e autorizzazioni. Eseguire manualmente lo script per pubblicare i CRL nel server IIS (vedere "Pubblicazione degli elenchi CRL della CA di emissione nel server Web" nella sezione "Attività della fase operativa") e controllare gli errori. Quando si esegue questa attività, provare ad utilizzare la stessa appartenenza di gruppo/account della CA stessa.
  
9.  Se i CRL vengono pubblicati nei servizi CDP ma lo strumento Integrità PKI indica un errore, significa che è presente un problema con il servizio CDP (Active Directory o IIS). La risoluzione dei problemi di questi servizi esula dagli argomenti trattati in questo documento.
  
##### CRL non emesso
  
Questa situazione è una condizione improbabile nel normale funzionamento. Di solito, una CA può pubblicare sempre un CRL localmente a meno che non sia stata riconfigurata per non pubblicare CRL dalla propria cartella di sistema locale (%windir%\\system32\\certsrv\\certenroll). Se il percorso di pubblicazione locale non è stato riconfigurato potrebbe verificarsi un problema grave con la CA. Utilizzare la seguente procedura per la risoluzione dei problemi per determinare la causa del problema. Sebbene questa procedura è rivolta ai problemi CRL, la maggior parte delle operazioni è generica e può essere utilizzata per qualsiasi problema secondario con Servizi certificati.
  
**Per risolvere i problemi di emissione del CRL**
  
1.  Esaminare il registro eventi per qualsiasi errore registrato da Servizi certificati.
  
2.  Tentare di imporre manualmente l’emissione di un CRL (accedere come membro del gruppo Amministratori CA) con il seguente comando:
  
    Certutil -CRL
  
3.  Se il passaggio non riesce, esaminare di nuovo il Registro eventi per eventuali nuovi errori.
  
4.  Esaminare il certificato CA e tutti i certificati della catena per la CA principale per vedere se sono presenti problemi con i certificati, ad esempio se i certificati sono scaduti o sono stati revocati.
  
5.  Verificare che sia possibile firmare di nuovo una certificato o un CRL con la chiave CA (vedere la procedura "Nuova firma di un certificato o di un CRL per estenderne il periodo di validità" nella sezione "Attività della fase di supporto").
  
6.  Riavviare la CA ed eseguire di nuovo questi controlli.
  
7.  Se il CRL non viene ancora emesso, attivare la registrazione di debug (vedere "Registrazione Servizi certificati" più avanti in questo capitolo). Quindi, tentare di emettere il CRL ed esaminare la registrazione per gli errori.
  
##### Il client non può registrare un certificato
  
Seguire la procedura per diagnosticare i problemi relativi alla registrazione dei certificati.
  
**Per diagnosticare un problema di registrazione dei certificati**
  
1.  Verificare che il modello di certificato sia stato assegnato ad una CA.
  
2.  Verificare che l’utente o computer disponga delle autorizzazioni per registrare sulla CA alla quale è stato assegnato il modello.
  
3.  Verificare che il modello corrisponda al tipo soggetto. I modelli utente possono essere registrati solo da utenti, mentre i modelli computer possono essere registrati solo da computer.
  
4.  Verificare che la CA possa accedere ai propri CRL pubblicati e a quelli delle relative CA padre. La CA esegue sempre un controllo delle revoche prima di emettere un certificato.
  
5.  Verificare che il modello di certificato non imponga l’uso di CSP non disponibili per la registrazione, ad esempio, CSP di smart card per un computer (o quando l’utente non dispone di una smart card) o CSP di canale protetto (SChannel) RSA (Rivest-Shamir-Adleman) per utenti.
  
6.  Verificare che il modello di certificato non richieda informazioni da inserire nel campo **Soggetto** o **Soggetto alternativo** che non esiste in Active Directory. Un problema comune consiste nello specificare che l’indirizzo di posta elettronica debba essere incluso nel nome soggetto, ma non il fatto che il campo della posta elettronica debba essere specificato nell’oggetto Active Directory dell’utente.
  
##### Il client non può registrare automaticamente un certificato
  
Informazioni esaurienti per la comprensione e la risoluzione dei problemi relativi alla registrazione automatica sono disponibili nell’articolo "Certificate Autoenrollment in Windows XP" (vedere il riferimento alla fine del presente capitolo).
  
Verificare che un client possa registrare manualmente il certificato che si sta tentando di registrare automaticamente. Caricare lo snap-in MMC Certificati e richiedere un nuovo certificato. Se il tipo di certificato non appare oppure se appare ma viene prodotto un errore quando si tenta di effettuarne la registrazione, seguire la procedura della sezione precedente "Il client non può registrare un certificato".
  
Se la registrazione manuale è possibile, continuare con i passaggi seguenti.
  
1.  Verificare che la piattaforma in uso sia corretta. Solo Windows 2000 e le versioni successive supportano la registrazione automatica dei certificati computer. Solo Windows XP e Windows Server 2003 supportano la registrazione automatica dei certificati utente.
  
2.  Verificare che l’utente o il computer disponga delle autorizzazioni di registrazione automatica sul modello di certificato per il tipo di certificato richiesto.
  
3.  Verificare che l’impostazione dei criteri di gruppo per la registrazione automatica sia stata specificata correttamente. Per funzionare correttamente, la registrazione automatica deve essere configurata sull'oggetto Criteri di gruppo (GPO) che ha la precedenza rispetto a tutti gli altri GPO. Ad esempio, se il GPO per la registrazione automatica viene creato a livello di dominio deve avere una priorità più alta rispetto ai criteri di dominio predefiniti. È possibile controllare la precedenza dei GPO con lo snap-in MCC Gruppo di criteri risultante.
  
4.  Verificare che il modello di certificato non richieda l’approvazione manuale o le firme dell’autorità di registrazione. Le richieste di certificati che richiedono l’approvazione del responsabile certificati verranno inviate per l’approvazione ma il certificato non verrà emesso all’utente fino a quando non sarà approvato manualmente. Le richieste che richiedono le firme dell’autorità di registrazione verranno rifiutate in quanto non esiste una procedura per l’aggiunta di ulteriori firme ad una richiesta di registrazione automatica.
  
5.  Verificare che il modello di certificato non sia impostato in modo tale da prevedere che nella richiesta debbano essere fornite le informazioni relative al soggetto. Per i certificati a registrazione automatica, il relativo soggetto (e soggetto alternativo) deve essere impostato dalla CA.
  
#### Tecniche e strumenti di risoluzione dei problemi
  
In questa sezione vengono descritti alcuni strumenti utili per la diagnosi e la soluzione dei problemi relativi all’infrastruttura PKI. Vengono inoltre descritte le registrazioni di Servizi certificati e le modalità di attivazione di registrazioni più dettagliate per Servizi certificati e la registrazione automatica del client.
  
##### Integrità PKI
  
Integrità PKI è principalmente uno strumento diagnostico CDP e AIA che tenta di creare una vista di tutte le CA dell’organizzazione di grandi dimensioni. È molto utile per la diagnosi della connettività e dei problemi di pubblicazione CDP e AIA; inoltre, consente di eseguire il download e di visualizzare i CRL o i certificati ai quali fanno riferimento CDP o AIA. È disponibile come parte di Windows Server 2003 Resource Kit.
  
##### Certutil
  
Certutil è il singolo strumento più importante per la gestione e la risoluzione dei problemi delle CA Windows. Per informazioni su alcuni degli usi principali di questo strumento, vedere il white paper "Using Certutil.exe to Manage and Troubleshoot Certificate Services". I relativi riferimenti sono forniti alla fine del presente capitolo.
  
Tuttavia, sono disponibili molte altre opzioni relative alle procedure diagnostiche e di gestione (non discusse nel white paper). È possibile visualizzare l’elenco completo delle attività (o dei verbi) Certutil disponibili immettendo il comando con un parametro "-?". Immettendo un verbo che descrive l'attività per la quale viene richiesta assistenza, viene visualizzata la sintassi dettagliata relativa a tale attività. Ad esempio:
  
Certutil -dsPublish -?
  
##### Altri strumenti diagnostici
  
Altri strumenti diagnostici e di gestione utili sono:
  
-   **Certreq.exe**. Consente di creare, inviare e recuperare le richieste di certificati dalla riga di comando.
  
-   **DCDiag.exe**. Utile per la diagnosi di problemi con Active Directory che possono influire sulle CA.
  
##### Registrazione Servizi certificati
  
Servizi certificati ed i relativi strumenti associati producono diversi tipi di registrazioni molto utili per la risoluzione dei problemi.
  
-   Registrazioni Servizi certificati (il processo di CA stesso) per %systemroot%\\certsrv.log (quando la registrazione di debug è abilitata).
  
-   Registrazioni Certutil.exe per %systemroot%\\certutil.log
  
-   Registrazioni MMC Autorità di certificazione per %windir%\\certmmc.log
  
**Per attivare la registrazione di debug su Servizi certificati**
  
-   Eseguire il comando:
  
    certutil -setreg CA\\Debug 0xffffffe3
  
Le voci della registrazione vengono salvate in %windir%\\certsrv.log
  
**Per disattivare la registrazione di debug**
  
-   Eseguire il comando:
  
    certutil -delreg CA\\Debug
  
##### Registrazione eventi di registrazione automatica
  
Per attivare la registrazione degli eventi di registrazione automatica, è necessario aggiungere un valore di registro. La registrazione avanzata viene attivata separatamente per la registrazione automatica dei certificati di utenti e computer.
  
**Per attivare la registrazione di eventi di registrazione automatica utente**
  
1.  Creare un nuovo valore di registro DWORD chiamato **AEEventLogLevel** nella chiave HKEY\_CURRENT\_USER\\Software\\Microsoft\\Cryptography\\Autoenrollment.
  
2.  Impostare il valore su **0**.
  
**Per attivare la registrazione di eventi di registrazione automatica computer**
  
1.  Creare un nuovo valore di registro DWORD chiamato **AEEventLogLevel** nella chiave HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Cryptography\\Autoenrollment.
  
2.  Impostare il valore su **0**.
  
    **Nota:** tutti gli errori vengono registrati automaticamente. Non è necessario attivare la chiave di registro per abilitare la registrazione degli errori.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Tabelle di configurazione
  
Nelle tabelle che seguono sono contenuti i valori di configurazione specifici del sito e della soluzione utilizzati nelle procedure di questo capitolo. Queste tabelle sono un sottogruppo delle tabelle di configurazione della pianificazione riportate nel capitolo 7 "Implementazione dell'infrastruttura a chiave pubblica" e sono mostrate solo a scopo illustrativo.
  
**Tabella 11.16. Elementi di configurazione definiti dall'utente**

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
<td style="border:1px solid black;"><p>Nome di dominio DNS per la radice di strutture Active Directory</p></td>
<td style="border:1px solid black;"><p>woodgrovebank.com</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>DN del dominio principale dell’insieme di strutture</p></td>
<td style="border:1px solid black;"><p>DC=woodgrovebank,DC=com</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome del server della CA principale</p></td>
<td style="border:1px solid black;"><p>HQ-CA-01</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Nome del server della CA di emissione</p></td>
<td style="border:1px solid black;"><p>HQ-CA-02</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>X.500 CN della CA principale</p></td>
<td style="border:1px solid black;"><p>Woodgrove Bank Root CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>X.500 CN della CA di emissione</p></td>
<td style="border:1px solid black;"><p>Woodgrove Bank Issuing CA 1</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome host completo del server Web utilizzato per pubblicare le informazioni relative alla revoca e al certificato CA</p></td>
<td style="border:1px solid black;"><p>www.woodgrovebank.com</p></td>
</tr>  
</tbody>  
</table>
  
**Tabella 11.17. Elementi di configurazione definiti dalla soluzione**

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
<td style="border:1px solid black;"><p>Amministratori del contenitore della configurazione dei servizi a chiave pubblica</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Autorizzato a pubblicare CRL e certificati CA nel contenitore della configurazione dell’organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Publishers</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Gruppo amministrativo che configura e gestisce le CA; controlla inoltre la possibilità di assegnare tutti gli altri ruoli della CA e rinnova il certificato CA</p></td>
<td style="border:1px solid black;"><p>CA Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Gruppo amministrativo che approva la registrazione dei certificati e le richieste di revoca; ruolo CA Officer</p></td>
<td style="border:1px solid black;"><p>Certificate Managers</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Gruppo amministrativo che gestisce il controllo CA e i registri protezione</p></td>
<td style="border:1px solid black;"><p>CA Auditors</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Gruppo amministrativo che gestisce i backup CA</p></td>
<td style="border:1px solid black;"><p>CA Backup Operators</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome della directory virtuale IIS utilizzata per pubblicare le informazioni relative al certificato CA e al CRL</p></td>
<td style="border:1px solid black;"><p>pki</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Percorso fisico sulla CA di emissione che esegue il mapping alla directory virtuale IIS</p></td>
<td style="border:1px solid black;"><p>C:\CAWWWPub</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Unità e percorso per archiviare i file di richieste di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>C:\CAConfig</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Unità e percorso per archiviare il database di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>%systemroot%\System32\CertLog</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Unità e percorso per archiviare i registri del database di Servizi certificati</p></td>
<td style="border:1px solid black;"><p>D:\CertLog</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Percorso per script di installazione</p></td>
<td style="border:1px solid black;"><p>C:\MSSScripts</p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
-   Per ulteriori informazioni sul modello di processo e sul modello di team MOF, vedere la pagina [Microsoft Operations Framework](http://www.microsoft.com/mof) all'indirizzo www.microsoft.com/technet/itsolutions/techguide/mof/default.mspx.
  
-   Per ulteriori informazioni sui vincoli di capacità e sui relativi contatori delle prestazioni, consultare l'articolo Q146005 della Microsoft Knowledge Base "[Optimizing Windows NT for Performance](http://support.microsoft.com/default.aspx?kbid=146005)" all'indirizzo http://support.microsoft.com/default.aspx?kbid=146005.
  
-   Per informazioni sulla distribuzione MOM, scaricare [*Microsoft Operations Manager 2000 (MOM) Service Pack 1 (SP1) Operations Guide*](http://www.microsoft.com/downloads/details.aspx?familyid=556a7746-75df-4acd-8cde-26cb12148161&displaylang=en) all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyID=556A7746-75DF-4ACD-8CDE-26CB12148161&displaylang=en.
  
-   Per ulteriori informazioni su attività operative supplementari, vedere la pagina [Administer a certification authority](http://technet.microsoft.com/en-us/library/cc738069.aspx) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/sag\_CS\_procs\_admin.mspx.
  
-   Per informazioni sulla gestione delle patch con Microsoft SMS 2003, vedere "[Patch Management Using Microsoft Systems Management Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=959ee7d6-7ddf-409a-9522-7d270bdcf12a&displaylang=en)" all'indirizzo www.microsoft.com/technet/itsolutions/techguide/msm/swdist/pmsms/2003/pmsms031.mspx.
  
-   Per informazioni sulla gestione delle patch con Microsoft Software Update Services, vedere "[Patch Management Using Microsoft Software Update](http://technet.microsoft.com/wsus/default.aspx)" all'indirizzo www.microsoft.com/technet/itsolutions/techguide/msm/swdist/pmsus/pmsus251.mspx.
  
-   Per informazioni dettagliate sulle proprietà del modello di certificato, vedere "[Understanding Certificate Templates](http://technet.microsoft.com/en-us/library/cc781718.aspx)" nella guida in linea del prodotto all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/ctcon\_concepts\_under.mspx.
  
-   Per ulteriori informazioni su come ottenere e utilizzare la Console di gestione Criteri di gruppo, vedere "[Enterprise Management with the Group Policy Management Console](http://www.microsoft.com/windowsserver2003/gpmc/default.mspx)" all'indirizzo www.microsoft.com/windowsserver2003/gpmc/default.mspx.
  
-   Per ulteriori informazioni sui problemi di pubblicazione degli elenchi CRL, vedere [Troubleshooting Certificate Status and Revocation](http://technet.microsoft.com/en-us/library/cc700843.aspx) all'indirizzo www.microsoft.com/technet/prodtechnol/WinXPPro/support/tshtcrl.mspx.
  
-   Per ottenere lo strumento Integrità PKI (PKIView.msc), scaricare gli [strumenti di Microsoft Windows Server 2003 Resource Kit](http://www.microsoft.com/downloads/details.aspx?familyid=9d467a69-57ff-4ae7-96ee-b18c4790cffd&displaylang=en) all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyID=9d467a69-57ff-4ae7-96ee-b18c4790cffd&DisplayLang=en.
  
-   Per informazioni esaurienti per la comprensione e la risoluzione dei problemi relativi alla registrazione automatica, vedere l’articolo "[Certificate Autoenrollment in Windows XP](http://technet.microsoft.com/en-us/library/bb456981.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/winxppro/maintain/certenrl.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
