---
TOCTitle: 'Gestione dell''infrastruttura a chiave pubblica'
Title: 'Gestione dell''infrastruttura a chiave pubblica'
ms:assetid: 'b31bbe10-b1dd-41cd-a875-96818c366ea6'
ms:contentKeyID: 20200851
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536252(v=TechNet.10)'
---

Lavorare con una rete locale wireless sicura grazie a Windows Server 2003 Certificate Services
==============================================================================================

### Gestione dell'infrastruttura a chiave pubblica

##### In questa pagina

[](#emaa)[Argomenti del modulo](#emaa)
[](#elaa)[Obiettivi](#elaa)
[](#ekaa)[Ambito di applicazione](#ekaa)
[](#ejaa)[Utilizzo del modulo](#ejaa)
[](#eiaa)[Attività fondamentali di manutenzione](#eiaa)
[](#ehaa)[Ruoli amministrativi di Servizi certificati](#ehaa)
[](#egaa)[Attività della fase operativa](#egaa)
[](#efaa)[Attività della fase di supporto](#efaa)
[](#eeaa)[Attività della fase di ottimizzazione](#eeaa)
[](#edaa)[Attività della fase di modifica](#edaa)
[](#ecaa)[Risoluzione dei problemi](#ecaa)
[](#ebaa)[Tabelle di configurazione](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Argomenti del modulo

In questo modulo sono descritte le procedure operative per gestire l'infrastruttura a chiave pubblica (PKI, Public Key Infrastructure) implementata come parte della soluzione di *protezione per reti LAN senza fili*. La struttura si basa su categorie e concetti descritti nel primo modulo della Guida operativa di Microsoft® Operations Framework (MOF).

Sono inoltre fornite indicazioni sull'implementazione di un sistema completo per la gestione dell'infrastruttura PKI, in cui sono incluse tutte le attività di configurazione necessarie per avviare monitoraggio e mantenimento del sistema. Vengono inoltre descritte le attività operative da eseguire con regolarità per mantenere il corretto funzionamento del sistema, le procedure per consentire all'utente di gestire problemi di supporto, modifiche all'ambiente, nonché di ottimizzare le prestazioni del sistema.

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Il modulo consente di:

-   Comprendere le attività da eseguire per gestire il sistema.

-   Assegnare i ruoli amministrativi necessari per l'amministrazione del sistema.

-   Fornire un documento di riferimento per la gestione dell'infrastruttura PKI.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Questo modulo si applica ai seguenti prodotti e tecnologie:

-   Microsoft Windows® Server™ 2003

-   Servizi certificati Microsoft

-   Servizio Microsoft Active Directory®

-   Microsoft Internet Information Server (IIS)

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

In questo modulo vengono descritte le procedure necessarie a gestire e mantenere in modo appropriato l'ambiente per l'infrastruttura PKI. La parte restante del modulo deve essere considerata come materiale di riferimento.

Per sfruttare al massimo il presente modulo:

-   Leggere il modulo "[Guida operativa alla protezione delle LAN senza fili: introduzione](http://technet.microsoft.com/it-it/cc645531.aspx)", in cui viene illustrato Microsoft Operations Framework, dal momento che il presente modulo è strutturato come una guida operativa di MOF.

[](#mainsection)[Inizio pagina](#mainsection)

### Attività fondamentali di manutenzione

In questa sezione vengono elencate le attività principali da eseguire per far funzionare in modo corretto l'infrastruttura PKI. Le attività sono elencate in due tabelle: attività iniziali di configurazione e attività operative continue. I nomi delle attività elencate nelle tabelle sono descritti dettagliatamente più avanti nel documento. Le attività sono raggruppate in base alla fase MOF, mentre la funzione di gestione dei servizi (SMF, Service Management Function) a cui appartiene l'attività è indicata accanto a questa, in modo che sia più semplice individuarla.

In questa sezione è incluso anche un elenco degli strumenti e delle tecnologie utilizzati nelle procedure di questo modulo.

#### Attività iniziali di configurazione

Nella tabella 1 sono elencate le attività da eseguire per avviare la produzione operativa dell'infrastruttura PKI. Le attività da eseguire possono variare a seconda degli standard e delle procedure operative di un'azienda. Esaminare in dettaglio le attività per decidere se eseguirle o meno. Potrebbe essere necessario ripetere alcune attività in un secondo momento. Ad esempio, se si installa una nuova autorità di certificazione (CA, Certificate Authority), sarà necessario configurare appositamente processi di monitoraggio e backup.

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
<td style="border:1px solid black;"><p>Preparazione di una struttura di unità organizzativa di dominio per la gestione dei Servizi certificati</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Amministrazione dei servizi directory</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Pubblicazione nel server Web degli elenchi di revoca certificati (CRL, Certificate Revocation List) dell'autorità di certificazione emittente</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Amministrazione della protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Configurazione di un backup del database dell'autorità di certificazione emittente</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Configurazione del backup del database dell'autorità di certificazione principale</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Test dei backup dei database delle autorità di certificazione</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Test dei backup delle chiavi delle autorità di certificazione</p></td>
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
<td style="border:1px solid black;"><p>Configurazione di avvisi SMTP (Simple Mail Transfer Protocol) per richieste di certificati in sospeso</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Monitoraggio e controllo dei servizi</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Pianificazione processi autorità di certificazione emittente</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Pianificazione dei processi</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Fase di ottimizzazione</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
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
<td style="border:1px solid black;"><p>Fase di modifica</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Gestione delle patch del sistema operativo</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>- Gestione delle modifiche<br />
- Gestione del rilascio</p></td>
</tr>
</tbody>
</table>
<p> </p>

Sebbene non esista un'attività documentata per l'impostazione di un sistema di gestione della configurazione per l'infrastruttura PKI, esaminare le procedure descritte nella sezione "Gestione della configurazione", in cui sono descritti i tipi di informazioni da raccogliere e conservare in un sistema di gestione della configurazione.

#### Attività di manutenzione

Nella tabella 2 sono riportate le attività da eseguire regolarmente per mantenere l'infrastruttura PKI in condizioni di funzionamento ottimali. Utilizzare questa tabella per prevedere le risorse necessarie e pianificare le fasi operative per l'amministrazione del sistema.

Non tutte le attività della tabella sono sempre necessarie. Esaminare in dettaglio le attività per decidere se eseguirle o meno. Per alcune attività sarà necessaria l'esecuzione occasionale, mentre per altre è bene pianificarne l'esecuzione. Ad esempio, se un certificato della CA principale viene rinnovato, sarà necessario eseguire un backup della CA principale anche se l'attività non è pianificata. In questi casi viene inserita una nota nella colonna Frequenza. Dipendenze di questo tipo vengono anche annotate nei dettagli stessi dell'attività.

**Tabella 2. Attività di manutenzione**

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
<th><p>Nome attività</p></th>
<th><p>Cluster di ruoli</p></th>
<th><p>Frequenza</p></th>
<th><p>SMF</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Fase di operatività</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Controllo richieste in sospeso</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Ogni giorno</p></td>
<td style="border:1px solid black;"><p>Amministrazione della protezione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Rinnovo certificato CA principale</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Ogni otto anni</p></td>
<td style="border:1px solid black;"><p>Amministrazione della protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Rinnovo certificato CA di emissione</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Ogni quattro anni</p></td>
<td style="border:1px solid black;"><p>Amministrazione della protezione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Pubblicazione elenco CRL non in linea e certificato CA</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Ogni sei mesi</p></td>
<td style="border:1px solid black;"><p>Amministrazione della protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Backup di chiavi e certificati CA</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>- Annuale<br />
- Ogni volta che il certificato CA viene rinnovato (a seconda dell'evento che si verifica per primo)</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Test dei backup del database dell'autorità di certificazione</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Ogni mese</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Test dei backup delle chiavi dell'autorità di certificazione</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Ogni sei mesi</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Archiviazione e rimozione di dati meno recenti dal database dei certificati</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Annuale</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Archiviazione di dati di controllo della protezione di una CA</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Mensile (CA di emissione)</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Archiviazione di dati di controllo della protezione di una CA</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>Ogni sei mesi (CA principale)</p></td>
<td style="border:1px solid black;"><p>Gestione dell'archiviazione</p></td>
</tr>  
</tbody>  
</table>
  
#### Tecnologia richiesta nella Guida operativa
  
Nelle tabelle 3 e 4 sono elencati gli strumenti o le tecnologie utilizzati per le procedure descritte nella presente guida.
  
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
<td style="border:1px solid black;"><p>Console di gestione Utenti e computer del servizio Active Directory</p></td>
<td style="border:1px solid black;"><p>Microsoft Windows Server 2003</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Console di gestione Autorità di certificazione</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Console di gestione Modelli di certificato</p></td>
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
<td style="border:1px solid black;"><p>Servizio di backup aziendale o periferica di backup locale</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Console di gestione Criteri di gruppo</p></td>
<td style="border:1px solid black;"><p>Download Web da Microsoft.com</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Integrità PKI</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003 Resource Kit</p></td>
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
<td style="border:1px solid black;"><p>Server e client SMTP/Post Office Protocol 3 (POP3)/Internet Message Access Protocol (IMAP), ad esempio, Microsoft Exchange Server e Microsoft Outlook®</p></td>
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
<td style="border:1px solid black;"><p>Microsoft Systems Management Server (SMS) o<br />
Microsoft Software Update Services (SUS)</p></td>
</tr>
</tbody>
</table>
<p> </p>

[](#mainsection)[Inizio pagina](#mainsection)

### Ruoli amministrativi di Servizi certificati

Nella gestione di un'infrastruttura PKI sono coinvolti molti ruoli differenti. Nelle due sezioni che seguono tali ruoli sono suddivisi in due categorie: principali e di supporto.

#### Ruoli principali di Servizi certificati

Questa categoria di ruoli è fondamentale per la gestione di un'infrastruttura PKI. Quasi tutti corrispondono al cluster dei ruoli di protezione MOF. Molti di questi corrispondono ai ruoli di protezione di criteri comuni definiti per i Servizi certificati. In questi casi viene inserita una nota tra parentesi dopo il nome del ruolo.

**Tabella 5. Ruoli principali di Servizi certificati**

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
<td style="border:1px solid black;"><p>Amministratore PKI organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile dell'intera infrastruttura PKI — definisce tipi di certificati, criteri di applicazioni, percorsi di trust e così via per un'organizzazione di grandi dimensioni.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Enterprise PKI Publisher</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile della pubblicazione di certificati trust principali, certificati CA secondari e di elenchi CRL nella directory.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>CA Administrator (ruolo CC)</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Amministratore CA — responsabile della configurazione a livello di server (ad esempio, installazione CA). Di solito coincide con il ruolo Enterprise PKI Admins.<br />
È possibile assegnare amministratori diversi a CA differenti se ciò è richiesto dall'utilizzo dei certificati.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Administrator (ruolo CC)</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Amministratore del sistema operativo del server CA — responsabile della configurazione a livello di server (ad esempio, installazione CA). Di solito coincide con il ruolo CA Admins.<br />
È possibile assegnare amministratori diversi a CA differenti se ciò è richiesto dall'utilizzo dei certificati.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>CA Auditor (ruolo CC)</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Gestisce eventi di controllo, criteri e tutto ciò che riguarda gli eventi CA controllabili.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Certificate Manager(ruolo CC)</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Approva le richieste di certificati per cui è richiesta l'approvazione manuale e revoca certificati.<br />
Possono coesistere più gestori dei certificati che si occupano dell'approvazione per CA differenti se l'utilizzo dei certificato lo richiede.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Autorità di registrazione</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Profilo del certificato</p></td>
<td style="border:1px solid black;"><p>È un'estensione del ruolo Certificate Manager, che si occupa dell'approvazione e delle firma di richieste di certificati in seguito a una verifica dell'identificatore (ID) fuori banda.<br />
Il ruolo può essere ricoperto da una persona o da un dispositivo di elaborazione IT (ad esempio, scanner di impronte digitali e database).<br />
È possibile specificare autorità di registrazione differenti per profili di certificati diversi (modelli) e interessare più CA.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Agente recupero chiavi</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Detiene le chiavi per la decrittografia di chiavi private, archiviate nel database CA.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Backup Operator (ruolo CC)</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Responsabile di backup e ripristino di server CA e della conservazione in modo sicuro dei supporti di backup.</p></td>
</tr>  
</tbody>  
</table>
  
#### Ruoli di supporto di Servizi certificati
  
I ruoli di supporto sono di tipo operativo e non risultano fondamentali per la gestione dell'infrastruttura PKI, ma forniscono funzioni di supporto ai ruoli principali.
  
**Tabella 6. Ruoli di supporto di Servizi certificati**

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
<td style="border:1px solid black;"><p>Responsabile del monitoraggio di eventi.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Pianificatore della capacità</p></td>
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile dell'analisi di prestazioni e carico per la previsione di requisiti futuri di capacità.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Amministratore di Active Directory</p></td>
<td style="border:1px solid black;"><p>Infrastruttura e supporto</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile di configurazione e supporto dell'infrastruttura Active Directory.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Gestione delle operazioni di Active Directory</p></td>
<td style="border:1px solid black;"><p>Operatore</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Responsabile della manutenzione quotidiana di directory (ad esempio, gestione dei gruppi di protezione, creazione di account e così via).</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Consiglio di approvazione delle modifiche</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
<td style="border:1px solid black;"><p>Organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Rappresentanti del settore tecnico e aziendale necessari per l'approvazione di modifiche all'infrastruttura.</p></td>
</tr>  
</tbody>  
</table>
  
#### Mapping di ruoli di Servizi certificati con gruppi di protezione
  
Nella tabella 7 sono elencati i gruppi di protezione definiti per questa soluzione. Vengono inoltre descritte sommariamente le capacità o le autorizzazioni di ciascun gruppo.
  
Per le CA non in linea esistono solo gruppi di protezione locali. In questo caso, vengono creati singoli account locali nella CA, utilizzati in seguito per popolare i gruppi locali. È possibile accettare che singoli account siano membri di più o anche di tutti i gruppi di ruoli locali, se questa condizione è supportata dai criteri IT e di protezione dell'organizzazione.
  
I gruppi di protezione di dominio delle CA in linea vengono utilizzati per applicare le autorizzazioni destinate a ogni ruolo. Gli account di dominio sono utilizzati per popolare i gruppi di ruoli. È sempre possibile accettare che singoli account siano membri di più gruppi di ruoli se questa condizione è supportata dai criteri IT e di protezione dell'organizzazione.
  
**Tabella 7. Mapping di ruoli di Servizi certificati con gruppi di protezione**

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
<td style="border:1px solid black;"><p>Amministratore PKI di un'organizzazione di grandi dimensioni</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
<td style="border:1px solid black;"><p>-</p></td>
<td style="border:1px solid black;"><p>Controllo sul contenitore di servizi a chiave pubblica di Active Directory, quindi su modelli, pubblicazione trust e altri elementi di configurazione estesi a tutta l'organizzazione di grandi dimensioni (insieme di strutture).</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Amministratore CA</p></td>
<td style="border:1px solid black;"><p>CA Admins</p></td>
<td style="border:1px solid black;"><p>CA Admins (solo CA principale)</p></td>
<td style="border:1px solid black;"><p>Dispone delle autorizzazioni di Gestione CA sull'autorità di certificazione. Controlla l'assegnazione di ruoli nella CA e può modificare le proprietà dell'autorità di certificazione. Di solito è un amministratore locale del server CA, a meno che non sia richiesta una separazione di ruoli.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Controllore CA</p></td>
<td style="border:1px solid black;"><p>CA Auditors</p></td>
<td style="border:1px solid black;"><p>CA Auditors (solo CA principale)</p></td>
<td style="border:1px solid black;"><p>Dispone di diritti utente dei registri di controllo e gestione protezione per un'autorità di certificazione. Deve inoltre essere membro del gruppo Administrators locale per la CA (necessario per accedere ai registri di controllo).</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Certificate Manager</p></td>
<td style="border:1px solid black;"><p>Certificate Managers</p></td>
<td style="border:1px solid black;"><p>Certificate Managers</p></td>
<td style="border:1px solid black;"><p>Dispone dell'autorizzazione Rilascio e Gestione certificati per la CA.<br />
È possibile configurare più Certificate Manager per ogni CA — ognuno responsabile della gestione certificati per un sottoinsieme di utenti o altre entità.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Autorità di registrazione</p></td>
<td style="border:1px solid black;"><p>-</p></td>
<td style="border:1px solid black;"><p>-</p></td>
<td style="border:1px solid black;"><p>Detiene chiavi e certificati necessari per la firma delle richieste di certificati prima dell'approvazione.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Agente recupero chiavi</p></td>
<td style="border:1px solid black;"><p>-</p></td>
<td style="border:1px solid black;"><p>-</p></td>
<td style="border:1px solid black;"><p>Detiene chiavi e certificati necessari per la decrittografia di chiavi private memorizzate nel database certificati.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Operatore di backup CA</p></td>
<td style="border:1px solid black;"><p>CA Backup Operators</p></td>
<td style="border:1px solid black;"><p>CA Backup Operators (solo CA principale)</p></td>
<td style="border:1px solid black;"><p>Dispone di diritti di backup e ripristino per il server CA.</p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase operativa
  
In questa sezione vengono fornite informazioni dettagliate sulle attività di manutenzione correlate alla fase operativa MOF.
  
Tale fase include standard operativi, processi e procedure dell'infrastruttura IT applicate con regolarità alle soluzioni di servizi per raggiungere e mantenere i livelli del servizio a livelli determinati. L'obiettivo della fase operativa è la previsione con grande anticipo dell'esecuzione di attività quotidiane, con o senza l'intervento di utenti.
  
In questa fase sono contenute le funzioni seguenti per la gestione di servizi:
  
-   Amministrazione dei servizi directory
  
-   Amministrazione della protezione
  
-   Gestione dell'archiviazione
  
-   Monitoraggio e controllo dei servizi
  
-   Pianificazione dei processi
  
Non esistono attività per le restanti funzioni di gestione dei servizi:
  
-   Gestione di sistema
  
-   Gestione della rete
  
-   Gestione della stampa e degli output
  
#### Amministrazione dei servizi directory
  
I servizi directory consentono a utenti e applicazioni di trovare risorse di rete quali utenti, server, applicazioni, strumenti, servizi e altre informazioni in rete. L'amministrazione di tali servizi riguarda operazioni quotidiane, manutenzione e supporto per la directory di un'organizzazione di grandi dimensioni. L'obiettivo dell'amministrazione di questi servizi è garantire a tutti gli utenti autorizzati, mediante procedure semplici e organizzate, l'accesso alle informazioni in rete.
  
##### Preparazione di una struttura di unità organizzativa (OU) di dominio per la gestione di Servizi certificati
  
Scopo di questa attività è creare una struttura di unità organizzativa adatta a gestire account utente e gruppi di protezione per i Servizi certificati.

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
<td style="border:1px solid black;"><p>Account con diritti di creazione di unità organizzative in una parte di Active Directory specifica</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Utenti e computer di Active Directory</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Questa attività non è rigida, infatti dipende molto dalla struttura dell'unità organizzativa esistente, nonché dai criteri e dalle procedure di gestione adottate. La seguente tabella fornisce un esempio di semplice sottostruttura di unità organizzativa che può essere utilizzata per semplificare l'organizzazione dei gruppi di protezione creati e descritti nella presente guida.
  
**Tabella 8. Collocazione dei gruppi di protezione all'interno della struttura dell'unità organizzativa**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Unità organizzativa</p></th>  
<th><p>Gruppi</p></th>  
<th><p>Scopo</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Servizi certificati</p></td>
<td style="border:1px solid black;"><br />
</td>
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
<td style="border:1px solid black;"><p>Contiene gruppi amministrativi per la gestione<br />
della configurazione della CA e dell'infrastruttura PKI di un'organizzazione di grandi dimensioni.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Gestione modelli certificati</p></td>
<td style="border:1px solid black;"><p>Esempi:<br />
Gestione modello utente<br />
Gestione modello di accesso di smart card</p></td>
<td style="border:1px solid black;"><p>Contiene i gruppi ai quali è concesso il controllo completo del modello<br />
con lo stesso nome. Consente la delega del<br />
controllo in base al tipo di modello.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Registrazione modello di certificato</p></td>
<td style="border:1px solid black;"><p>Esempi:<br />
Registrazione certificato utente<br />  
Registrazione automatica certificato utente<br />
Registrazione certificato di firma per posta elettronica</p></td>
<td style="border:1px solid black;"><p>Contiene i gruppi ai quali è stata concessa l'autorizzazione di Registrazione<br />
o Registrazione automatica sui modelli con lo<br />  
stesso nome. Il controllo dei gruppi<br />  
può quindi essere delegato al personale preposto<br />  
in modo da consentire un regime di registrazione flessibile senza<br />  
dover coinvolgere i<br />
modelli stessi.</p></td>
</tr>
</tbody>
</table>
<p> </p>

##### Creazione di gruppi di gestione di modelli di certificato

I gruppi di gestione di modelli consentono di delegare ad amministratori diversi il controllo sui modelli e sulle relative impostazioni. In caso contrario, solo i ruoli Enterprise Administrators ed Enterprise PKI Admins hanno l'autorizzazione per modificare i modelli. Se l'organizzazione IT non è di grandi dimensioni, questo tipo di delega granulare potrebbe non essere necessario. In questo caso, solo i membri del gruppo Enterprise Admins (gruppo incorporato) e del gruppo Enterprise PKI Admins (creato nell'ambito di questa soluzione) possono amministrare i modelli di certificato.

**Avviso:** prestare estrema attenzione quando si utilizza questa funzionalità. La delega del controllo su un tipo di modello implica il fatto che si ritenga pienamente attendibile l'utente al quale si sta assegnando la delega. Gli utenti che dispongono delle autorizzazioni di scrittura possono modificare tutti i parametri di un modello per creare qualsiasi tipo di certificato desiderato. È consigliabile creare il modello per loro conto, in modo tale che il controllo sui tipi di certificato venga mantenuto esclusivamente all'interno del gruppo Enterprise PKI Admins.

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
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>La struttura dell'unità organizzativa dei gruppi di gestione dei certificati deve esistere.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Console di gestione Utenti e computer di Active Directory<br />
- Console di gestione Modelli di certificato</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Per ciascun modello di certificato che viene creato o che si desidera attivare nel proprio ambiente, eseguire le procedure seguenti.

-   **Per creare gruppi di gestione di modelli di certificato**

    1.  Accedere come membro del gruppo Enterprise PKI Admins.

    2.  Nell'unità organizzativa Gestione modelli certificati creare un gruppo di protezione globale di dominio chiamato Manage *CertTemplateName* Template (dove *CertTemplateName* è il nome del modello di certificato da gestire).

    3.  Caricare lo snap-in **Modelli di certificato** in MMC (Microsoft Management Console).

    4.  Aprire le proprietà del modello richiesto e fare clic sulla scheda **Protezione**.

    5.  Aggiungere il gruppo Manage *CertTemplateName* Template e concedergli l'autorizzazione di **scrittura**.

##### Creazione di gruppi di registrazione modelli di certificato

I gruppi di registrazione di modelli semplificano la gestione degli utenti autorizzati alla registrazione o degli utenti autorizzati alla registrazione automatica per un determinato tipo di certificato aggiungendo e rimovendo utenti o computer a o da un gruppo di protezione. È inoltre possibile concedere il controllo sull'appartenenza a questi gruppi al personale addetto all'amministrazione che non dispone dell'autorizzazione per modificare direttamente le proprietà dei modelli di certificato.

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
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>La struttura dell'unità organizzativa dei gruppi di gestione dei certificati deve esistere.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Console di gestione Utenti e computer di Active Directory<br />
- Console di gestione Modelli di certificato</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Creare un gruppo di registrazione per ciascun tipo di modello di certificato o almeno tutti quelli per i quali l'approvazione del certificato è automatica (nel caso in cui fosse presente un processo di registrazione diverso per un determinato tipo di certificato, questa procedura potrebbe non essere utile). Se il tipo di certificato è abilitato alla registrazione automatica, è possibile creare un gruppo separato che controlla gli utenti e le periferiche per la registrazione automatica del certificato.

-   **Per creare un gruppo di registrazione dei modelli di certificato:**

    1.  Accedere come membro del gruppo Enterprise PKI Admins e aprire la console di gestione Utenti e computer di Active Directory.

    2.  Nell'unità organizzativa di registrazione del modello di certificato creare i gruppi di protezione globale di dominio chiamati:

        Registrazione certificato *CertTemplateName*

        Registrazione automatica certificato *CertTemplateName*(se richiesto)

    3.  Caricare lo snap-in **Modelli di certificato** in MMC.

    4.  Aprire le proprietà del modello per modificare la protezione.

    5.  Aggiungere il gruppo Enroll *CertTemplateName* Certificate e concedergli le autorizzazioni di **lettura** e **registrazione**.

    6.  Aggiungere il gruppo Autoenroll *CertTemplateName* Certificate e concedergli le autorizzazioni di **lettura**, **registrazione** e **registrazione automatica**.

**Nota:** è possibile delegare il controllo su questi gruppi di protezione per consentire al proprietario dell'applicazione di specificare gli utenti abilitati o meno alla registrazione di questo tipo di certificato.

##### Attivazione della registrazione (o registrazione automatica) di un tipo di certificato per un utente o un computer

Questa attività configura la directory per consentire la registrazione manuale o avviare la registrazione automatica di un tipo di certificato per un utente, un computer o un gruppo di protezione contenente utenti e/o computer.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Modificare le autorizzazioni di appartenenza per il gruppo di registrazione dei certificati.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Il gruppo di registrazione dei modelli di certificato deve esistere.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Utenti e computer di Active Directory</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
-   **Per attivare la registrazione o la registrazione automatica per un utente o computer**
  
    1.  Nella console di gestione Utenti e computer di Active Directory individuare il gruppo di protezione Certificate Template Enrollment(o gruppo AutoEnrollment per la registrazione automatica del certificato) corrispondente al tipo di certificato da registrare. È necessario accedere come utente con le autorizzazioni per la **modifica dell'appartenenza** per questo gruppo.
  
    2.  Aggiungere l'utente, il computer o il gruppo di protezione al gruppo di protezione del modello selezionato.
  
##### Disattivazione della registrazione (o registrazione automatica) di un tipo di certificato per un utente o computer
  
L'emissione di un certificato a un utente o computer generalmente abilita alcune delle funzionalità del possessore del certificato. In seguito potrebbe essere necessario disattivare questa funzionalità.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Modificare le autorizzazioni di appartenenza per il gruppo di registrazione dei certificati.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Il gruppo di registrazione dei modelli di certificato deve esistere.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Console di gestione Utenti e computer di Active Directory<br />
- Console di gestione Autorità di certificazione</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

-   **Per disattivare la registrazione o la registrazione automatica per un utente o computer**

    1.  Nella console di gestione Utenti e computer di Active Directory individuare il gruppo di protezione Certificate Template Enrollment (o Autoenrollment) corrispondente al tipo di certificato da disattivare. È necessario accedere come utente con le autorizzazioni per la **modifica** dell'appartenenza per questo gruppo.

    2.  Rimuovere l'utente, il computer o il gruppo di protezione dal gruppo di protezione del modello selezionato.

        **Nota:** per ciascun utente che si desidera disattivare è inoltre necessario revocare il certificato di tale utente.

    3.  Accedere come membro del gruppo Certificate Managers ed individuare il certificato esistente dell'utente nel database dell'autorità di certificazione (console MMC Autorità di certificazione). Per individuare il certificato, nella cartella **Certificati emessi** dell'Autorità di certificazione scegliere il menu **Visualizza** e l'opzione **Filtro**.

    4.  Fare clic sul certificato e dal menu **Attività** scegliere **Revoca**.

    5.  Selezionare un codice motivo appropriato per la revoca. Se il motivo della revoca non è compreso tra i codici motivo predefiniti, selezionare **Non specificato**.

        **Nota:** solo il codice motivo **Sospensione certificato** consente di ripristinare il certificato in seguito. Tutti gli altri codici motivo disattivano in modo permanente il certificato. Tuttavia, non utilizzare il codice motivo **Sospensione certificato** solo perché consente il ripristino del certificato. Utilizzare questo codice quando è effettivamente necessaria la sospensione temporanea del certificato.

#### Amministrazione della protezione

L'amministrazione della protezione è responsabile del mantenimento di un ambiente informatico protetto. La protezione costituisce una parte importante dell'infrastruttura di un'organizzazione. In un sistema informatico con una protezione debole è probabile che si verifichino violazioni della protezione.

##### Controllo richieste in sospeso

Le richieste di certificati possono essere inviate alle autorità di certificazione emittenti in qualsiasi momento. La maggior parte dei certificati viene emessa automaticamente sia mediante l'utilizzo di Active Directory come autorità di registrazione (RA) sia mediante l'utilizzo di un gruppo predefinito di firme dell'autorità di registrazione nominata. Se per qualsiasi tipo di certificato è stata impostata l'approvazione manuale da parte del gestore certificati, tali richieste verranno messe in coda fino a quando non verranno approvate o rifiutate.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni giorno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Certificate Managers</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Autorità di certificazione</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Controllare quotidianamente la cartella **Richieste** per verificare le richieste in coda. Prima di emettere un certificato, controllare attentamente la richiesta per verificare il richiedente e il contenuto della richiesta. Controllare che contenga il nome del soggetto, il nome del soggetto alternativo, gli utilizzi delle chiavi, i criteri e le estensioni previste. In caso di dubbi, non approvare la richiesta.
  
È inoltre possibile configurare l'autorità di certificazione per l'invio di avvisi di posta elettronica per i diversi eventi. Uno di questi eventi è l'arrivo di una richiesta in sospeso. Vedere la procedura "[Impostazione degli avvisi SMTP per le richieste di certificati in sospeso](#a1)".
  
-   **Per controllare le richieste in sospeso**
  
    1.  Accedere all'autorità di certificazione emittente come membro del gruppo Certificate Managers (è possibile eseguire questa attività in remoto attivando nuovamente la console MMC Autorità di certificazione).
  
    2.  Aprire la console MMC Autorità di certificazione e aprire la cartella **Richieste**.
  
    3.  Per visualizzare i dettagli di qualsiasi richiesta della cartella, fare clic con il pulsante destro del mouse sulla richiesta e scegliere **Visualizza attributi/estensioni** dal sottomenu **Visualizza**.
  
        **Nota:** nella scheda **Attributi** appaiono gli attributi della richiesta ricevuti come parte della richiesta mentre nella scheda **Estensioni** appaiono le estensioni del certificato che verranno utilizzate nel certificato. Ogni voce di estensione indica se si tratta di un'estensione inclusa nella richiesta, di un valore fornito dal server oppure se è stata definita dal modulo dei criteri dell'autorità di certificazione (quest'ultima origine generalmente indica che si tratta di un'estensione definita nel modello di certificato).
  
    4.  A seconda dei criteri adottati dall'organizzazione, è inoltre possibile che siano presenti altre informazioni relative alla richiesta, ad esempio informazioni date di persona, per telefono, tramite posta elettronica o altre informazioni simili.
  
    5.  Una volta verificata la validità della richiesta, è possibile approvarla facendo clic con il pulsante destro del mouse sulla richiesta e scegliendo **Emetti** dal sottomenu **Attività**. In caso contrario, è possibile rifiutare la richiesta scegliendo **Nega** dallo stesso sottomenu.
  
##### Rinnovo certificato CA principale
  
È necessario rinnovare regolarmente il certificato CA per consentire alle CA subordinate e ad altre entità finali di registrare i certificati con questa CA. I certificati emessi da questa CA e dalle sue subordinate non possono avere una data di scadenza successiva a quella di questo certificato CA. Altri motivi per il rinnovo del certificato CA sono:
  
-   Modifica della chiave utilizzata dalla CA (in caso di compromissione effettiva o sospetta).
  
-   Aggiunta di criteri del certificato alla CA (subordinazione qualificata).
  
-   Modifica del percorso CDP o AIA (Authority Information Access).
  
-   Partizionamento dell'elenco CRL.
  
È consigliabile modificare la chiave CA a ogni rinnovo. Se si desidera effettuare il rinnovo con la stessa chiave, fare riferimento alla seguente procedura "[Rinnovo del certificato CA principale con la stessa chiave](#a2)."

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni otto anni</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Certutil.exe<br />
- Script MSS<br />  
- Console di gestione Autorità di certificazione<br />
- Editor di testo</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Avviso:** il rinnovo di un certificato CA principale è un evento molto importante. Accertarsi che tutti i proprietari dell'applicazione interessati vengano informati sul nuovo certificato principale nel caso in cui debbano configurare questo nuovo certificato principale nella loro applicazione.

**Dettagli relativi all'attività**

-   **Per rinnovare il certificato CA principale**

    1.  Accedere alla CA principale come membro del gruppo Administrators locale.

    2.  Per modificare la dimensione della chiave, è necessario modificare il file CAPolicy.inf che si trova nella directory *%systemroot%*. Modificare il valore di **RenewalKeyLength** con la dimensione di bit desiderata. Nell'esempio seguente, questo valore è 8192.
        ```

        **Avviso:** la dimensione della chiave di 8192 bit viene mostrata solo per illustrare come modificare la dimensione della chiave. Prestare estrema attenzione se si utilizza una chiave di questa dimensione. Sebbene Servizi certificati supporti dimensioni di chiave fino a 16384 bit, vi sono applicazioni e sistemi che non supportano dimensioni di chiave maggiori di 2048 bit in alcun certificato dalla catena di certificati che giunge fino alla CA principale.

        Se è necessario modificare il periodo di validità o i criteri del certificato dell'autorità di certificazione, prima di iniziare questa procedura è necessario specificarlo nel file CAPolicy.inf in *%systemroot%*).

    3.  Aprire la console di gestione Autorità di certificazione e, nel menu **Attività** dell'oggetto CA, fare clic su **Rinnova certificato CA**. Servizi certificati avvisa che, per effettuare questa operazione, è necessario arrestare l'autorità di certificazione.

    4.  Selezionare la nuova opzione chiave. Servizi certificati viene riavviato.

    5.  Visualizzare il certificato dalle proprietà CA e verificare che la data del certificato CA più recente specificata in **Valido dal** corrisponda alla data corrente.

    6.  Emettere un elenco CRL e copiare il CRL ed il nuovo certificato CA sul disco mediante il comando di script:
        ```

    7.  Portare il disco alla CA di emissione (il server deve essere solo un membro di dominio con certutil.exe e gli script forniti con questa soluzione installata — non è necessario che sia la CA di emissione).

    8.  Accedere come membro del gruppo Enterprise PKI Admins ed eseguire gli script seguenti:
        ```

        **Nota:** sebbene non sia necessario effettuare queste operazioni contemporaneamente, è consigliabile rinnovare tutte le CA subordinate nello stesso momento (vedere la sezione successiva "[Rinnovo certificato CA di emissione](#a3)").

    9.  Eseguire il backup della chiave e del certificato della CA principale (vedere Backup di chiavi e certificati CA).

    10. Eseguire il backup dello stato del sistema e del database dei certificati della CA principale (vedere la procedura "[Backup del database autorità di certificazione principale](#a4)").

##### Rinnovo certificato CA di emissione

È necessario rinnovare regolarmente il certificato CA per consentire alle CA subordinate e ad altre entità finali di continuare a registrare i certificati con questa CA. I certificati emessi da questa CA non possono avere una data di scadenza successiva a quella di questo certificato CA. Altri motivi per il rinnovo del certificato CA sono:

-   Modifica della chiave utilizzata dalla CA (in caso di compromissione effettiva o sospetta).

-   Aggiunta di criteri del certificato alla CA (subordinazione qualificata).

-   Modifica dei percorsi CDP o AIA.

-   Partizionamento del CRL.

È consigliabile modificare la chiave CA ad ogni rinnovo. Se si desidera effettuare il rinnovo con la stessa chiave, fare riferimento alla procedura "[Rinnovo del certificato CA principale con la stessa chiave](#a2)".

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni quattro anni</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Local Administrators su CA di emissione<br />
Certificate Managers su CA principale<br />
Enterprise PKI Admins</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Certutil.exe<br />
- Script MSS<br />  
- Console di gestione Autorità di certificazione<br />
- Editor di testo</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Importante:** Per effettuare con successo il rinnovo del certificato CA e pubblicarlo nell'archivio NTAuth di Active Directory (che identifica la CA come CA dell'organizzazione di grandi dimensioni), è necessario eseguire l'installazione del certificato CA utilizzando un account che sia *sia*membro del gruppo Enterprise PKI Admins sia del gruppo Administrators locale. Il primo gruppo dispone dei diritti per pubblicare il certificato nella directory mentre il secondo dispone dei diritti per installare il certificato CA sull'autorità di certificazione.

**Dettagli relativi all'attività**

-   **Per rinnovare il certificato della CA di emissione**

    1.  Accedere alla CA di emissione come membro del gruppo Administrators locale.

    2.  Per modificare la dimensione della chiave, è necessario modificare il file CAPolicy.inf che si trova nella directory *%systemroot%*. Modificare il valore di **RenewalKeyLength** con la dimensione in bit desiderata.
        ```

        **Importante:** se è necessario modificare il periodo di validità o i criteri del certificato CA, prima di iniziare questa procedura è necessario specificarlo nel file CAPolicy.inf in *%systemroot%*).

    3.  Aprire la console di gestione Autorità di certificazione e, nel menu **Attività** dell'oggetto CA, fare clic su **Rinnova certificato CA**.

    4.  Selezionare la nuova opzione chiave.

    5.  Quando viene richiesta la CA alla quale inviare il rinnovo, fare clic su **Annulla** per salvare il file della richiesta sul disco. Servizi certificati viene riavviato.

    6.  Copiare il file della richiesta di certificato sul disco. La richiesta di certificato viene generata e archiviata nel percorso della cartella condivisa (C:\\CAConfig). Copiare il file ***HQ-CA-02.woodgrovebank.com\_Woodgrove Bank Issuing CA 1***.req sul disco (sostituire il testo in corsivo con i dettagli CA appropriati).

    7.  Portare il disco alla CA principale e accedere come membro del gruppo Certificate Managers locale.

    8.  Nella console di gestione Autorità di certificazione, nel menu **Attività** della CA, fare clic su **Invia nuova richiesta**, quindi inviare la richiesta trasferita dalla CA di emissione (sul disco della richiesta della CA subordinata).

    9.  La CA principale richiede che tutte le richieste vengano approvate manualmente. Individuare la richiesta nel contenitore **Richieste in sospeso**, verificare che nel campo **Nome comune** sia presente il nome della CA di emissione, quindi approvare (emettere) la richiesta.

    10. Individuare il certificato appena emesso nel contenitore **Certificati emessi** ed aprirlo.

    11. Verificare che i dettagli del certificato siano corretti, quindi fare clic su **Copia su file** per esportare il certificato in un file, salvandolo come file PKCS\#7 sul disco (per trasferirlo di nuovo alla CA di emissione).

    12. Accedere di nuovo alla CA di emissione con un account membro sia del gruppo **Enterprise PKI Admins*che* del gruppo Administrators locale, quindi inserire il disco.

    13. Nella console di gestione Autorità di certificazione, nel menu **Attività** della CA, fare clic su **Installa certificato**. Installare il certificato della CA di emissione dal disco. L'autorità di certificazione viene riavviata.

    14. Visualizzare il certificato dalle proprietà CA e verificare che la data del certificato CA più recente specificata in **Valido dal** corrisponda alla data corrente.

    15. Pubblicare il nuovo certificato CA nel percorso Web CDP (vedere la procedura "[Pubblicazione del certificato della CA di emissione nel server Web](#a5)").

    16. Eseguire il backup della chiave e del certificato della CA di emissione (vedere la procedura "[Backup di chiavi e certificati CA](#a6)").

    17. Eseguire il backup dello stato del sistema e del database dei certificati della CA principale (vedere la procedura "[Backup del database autorità di certificazione principale](#a4)").

    18. Eseguire il backup dello stato del sistema e del database dei certificati della CA di emissione (vedere la procedura "[Configurazione del backup del database dell'autorità di certificazione emittente](#a7)"). Questa operazione può essere eseguita in qualsiasi momento durante il normale backup giornaliero.

##### Rinnovo del certificato CA principale con la stessa chiave

Modificare la chiave della CA principale ad ogni rinnovo del certificato CA pianificato (fare riferimento all'attività "Rinnovo certificato CA principale"). Se è necessario modificare i criteri CA, estendere la durata del certificato, e così via, mantenendo la stessa coppia di chiavi, potrebbe essere necessario rinnovare il certificato CA senza dover rinnovare la chiave CA.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Rinnovo certificato CA principale</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Certutil.exe<br />
- Script MSS<br />
- Editor di testo</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

-   **Per rinnovare il certificato CA principale senza modificare la chiave CA**

    -   Seguire la procedura "[Rinnovo certificato CA principale](#a8)", ma quando viene richiesto di effettuare il rinnovo con una nuova chiave, fare clic su **No**. Eventuali modifiche del valore di **RenewalKeyLength** nel file CAPolicy.inf non hanno alcun effetto.

Oltre a non effettuare la selezione per generare una nuova chiave, la procedura è la stessa del "[Rinnovo certificato CA principale](#a8)."

##### Rinnovo del certificato CA di emissione con la stessa chiave

Modificare la chiave di una CA a ogni rinnovo del certificato CA pianificato (vedere la procedura "Rinnovo certificato CA di emissione"). Se è necessario modificare i criteri CA, estendere la durata del certificato, e così via, mantenendo la stessa coppia di chiavi, potrebbe essere necessario rinnovare il certificato CA senza dover rinnovare la chiave CA.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Rinnovo certificato CA di emissione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Cert util.exe<br />
- Script MSS<br />  
- Console di gestione Autorità di certificazione<br />
- Editor di testo</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

-   **Per rinnovare il certificato della CA di emissione senza modificare la chiave CA**

    -   Seguire la procedura "[Rinnovo certificato CA principale](#a8)", ma quando viene richiesto di effettuare il rinnovo con una nuova chiave, fare clic su **No**. Eventuali modifiche del valore di **RenewalKeyLength** nel file CAPolicy.inf non hanno alcun effetto.

Oltre a non effettuare la selezione per generare una nuova chiave, la procedura è la stessa del "Rinnovo certificato CA di emissione".

**Avviso:** il rinnovo di un certificato CA principale è un evento molto importante. Accertarsi che tutti i proprietari dell'applicazione interessati vengano informati sul nuovo certificato principale nel caso in cui debbano configurare questo nuovo certificato principale nella loro applicazione.

##### Pubblicazione elenco CRL non in linea e certificato CA

È necessario pubblicare l'elenco CRL di una CA non in linea in un percorso in linea in modo tale che gli utenti dei certificati possano controllare lo stato di revoca dell'intera catena CA.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni sei mesi o come richiesto</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>- Gruppo Administrators locale sulla CA<br />
- Enterprise PKI Publishers</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>- I responsabili della pubblicazione PKI per l'organizzazione di grandi dimensioni devono essere autorizzati a modificare i file della cartella IIS pubblicata.<br />
- Correggere la configurazione delle autorizzazioni nel contenitore di servizi a chiave pubblica in Active Directory (vedere <em>Guida all'implementazione</em>)<br />
- Correggere la configurazione della directory di pubblicazione IIS (vedere <em>Guida all'implementazione</em>).</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Certutil.exe<br />
- Script MSS</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

-   **Per pubblicare l'elenco CRL principale non in linea in Active Directory e nell'URL Web**

    1.  Accedere alla CA principale come membro del gruppo CA Admins.

    2.  Emettere un elenco CRL e copiare il CRL ed il nuovo certificato CA sul disco mediante il comando di script:

        **Cscript //job:getcacerts c:\\MSSScripts\\ca\_operations.wsf**

        **Cscript //job:getcrls c:\\MSSScripts\\ca\_operations.wsf**

    3.  Portare il disco alla CA di emissione (non è necessario che il server sia la CA di emissione — deve essere solo un membro del dominio con certutil.exe e gli script MSS installati).

    4.  Accedere come membro del gruppo Enterprise PKI Publishers ed eseguire gli script seguenti:
        ```

##### Imposizione dell'emissione di un elenco CRL in linea

Gli elenchi CRL di una CA dell'organizzazione di grandi dimensioni vengono emessi e pubblicati automaticamente; normalmente l'imposizione dell'emissione di un elenco CRL in linea non è richiesta. Tuttavia, tale imposizione potrebbe essere necessaria quando si verifica una revoca critica (ad esempio, tutti i certificati emessi dalla CA) e deve essere pubblicato un nuovo elenco CRL in tempi brevissimi.

**Nota:** non è possibile imporre un elenco CRL ai client, che manterranno memorizzate nella cache le copie fino alla loro scadenza. Tuttavia, da quando il nuovo elenco CRL viene pubblicato, qualsiasi client che richiede un elenco CRL riceverà quello nuovo, a parte i ritardi di propagazione.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>La struttura dell'unità organizzativa dei gruppi di gestione è stata creata.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Autorità di certificazione</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
-   **Per emettere e pubblicare l'elenco CRL della CA non in linea nella Active Directory**
  
    1.  Accedere alla CA come membro del gruppo CA Admins e caricare la console di gestione Autorità di certificazione.
  
    2.  Emettere un nuovo elenco CRL dal menu **Attività** della cartella **Certificati revocati** facendo clic su **Pubblica**.
  
    3.  Selezionare **Nuovo CRL** per emettere un Base CRL o Delta CRL solo per un Delta CRL nuovo.
  
##### Pubblicazione del certificato della CA di emissione sul server Web
  
Il certificato della CA di emissione deve essere pubblicato nel percorso HTTP AIA.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Publishers</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>- I responsabili della pubblicazione PKI per l'organizzazione di grandi dimensioni devono essere autorizzati a modificare i file della cartella IIS pubblicata.<br />
- Correggere la configurazione della directory di pubblicazione IIS (vedere <em>Guida all'implementazione</em>)<br />
- Il file PKIParams.vbs deve essere aggiornato in modo da riflettere il percorso di destinazione corretto degli elenchi CRL.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Script MSS<br />
- Certutil.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Tecnicamente è possibile configurare la CA in modo che la pubblicazione venga eseguita direttamente nella cartella **Server Web**. Tuttavia, questa operazione non è sempre pratica per motivi di protezione e connettività della rete. Il metodo mostrato in questo documento si avvale di una semplice tecnica di copia dei file ma può essere esteso per adattarsi alla maggior parte delle configurazioni.

**Nota:** questo metodo non è adatto per pubblicare direttamente in un server Web connesso a Internet in quanto esso utilizza la condivisione di file SMB (Server Message Block). Per pubblicare in un server Internet, utilizzare un percorso di pubblicazione intermedio, quindi utilizzare il metodo standard di pubblicazione protetta del contenuto nel server Web. È necessario tenere in considerazione l'ulteriore latenza connessa a questo approccio.

Il certificato CA viene aggiornato molto raramente, quindi è possibile pubblicare manualmente in AIA ogni volta che il certificato CA viene rinnovato.

-   **Per pubblicare il certificato della CA di emissione**

    1.  Accedere alla CA di emissione come membro del gruppo Enterprise PKI Publishers oppure come account con le autorizzazioni di scrittura sulla cartella **Server Web** pubblicata.

    2.  Se il server Web si trova su un server remoto, accertarsi che la cartella **Server Web** sia condivisa. Registrare il percorso UNC (Universal Naming Convention) della cartella condivisa.

    3.  Se il server Web si trova sullo stesso server della CA, registrare il percorso locale della cartella.

    4.  Aggiornare il parametro **WWW\_REMOTE\_PUB\_PATH** nel file
        C:\\MSSScripts\\PKIParams.vbs in modo che corrisponda al percorso di destinazione della cartella del server Web (l'impostazione predefinita è il percorso locale C:\\CAWWWPub).

    5.  Eseguire il comando seguente per pubblicare il certificato CA nel server Web:
        ```

        **Nota:** questo comando viene mostrato su due righe; immetterlo come singola riga.

##### Pubblicazione degli elenchi CRL della CA di emissione nel server Web

È necessario pubblicare gli elenchi CRL della CA di emissione nel percorso del punto di distribuzione CRL HTTP.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Attività di configurazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>- Correggere la configurazione della directory di pubblicazione IIS (vedere <em>Guida all'implementazione</em>)<br />
- Il file PKIParams.vbs deve essere aggiornato in modo da riflettere il percorso di destinazione corretto degli elenchi CRL.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Script MSS<br />
- Certutil.exe<br />  
- Servizio Utilità di pianificazione di Windows<br />
- SchTasks.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Tecnicamente è possibile configurare la CA in modo che la pubblicazione venga eseguita direttamente nella cartella del server Web. Tuttavia, questa operazione non è sempre pratica per motivi di protezione e connettività della rete. Il metodo mostrato in questo documento si avvale di una semplice tecnica di copia dei file ma può essere esteso per adattarsi alla maggior parte delle configurazioni.

**Nota:** questo metodo non è adatto per pubblicare direttamente in un server Web connesso a Internet in quanto esso utilizza la condivisione di file SMB. Per pubblicare in un server Internet, utilizzare la seguente tecnica per pubblicare in un percorso intermedio, quindi procedere con le normali operazioni che garantiscono la pubblicazione sicura dei contenuti nel server Web. È necessario considerare l'effetto che la latenza dell'introduzione di questo ulteriore passaggio potrebbe avere sugli elenchi CRL.

La CA di emissione rilascia frequentemente (quotidianamente o ogni ora nel caso di Delta CRL) elenchi CRL. Quindi, è necessario adottare un metodo automatico di replica degli elenchi CRL sul server Web.

-   **Per automatizzare la pubblicazione di CRL**

    1.  Accedere alla CA di emissione con un account membro del gruppo Administrators locale.

    2.  Accertarsi che la cartella **Server Web** sia accessibile (come condivisione remota o percorso locale) da questo server.

    3.  Se il server Web è remoto, concedere all'account del computer della CA di emissione l'accesso in **scrittura** alla cartella del file system (accesso in **modifica**) e alla condivisione (accesso **Change**) corrispondente alla cartella **Server Web** pubblicata. Se il server Web è un membro dell'insieme di strutture, è possibile utilizzare il gruppo Cert Publishers per concedere l'accesso; ciò assicura che qualsiasi CA dell'organizzazione di grandi dimensioni disponga delle autorizzazioni necessarie per pubblicare i certificati e gli elenchi CRL in questa cartella. Non è necessario cambiare le autorizzazioni del server Web.

    4.  Creare un processo pianificato per copiare gli elenchi CRL eseguendo il comando seguente:
        ```

        Questo comando viene mostrato su tre righe; immetterlo come singola riga.

**Nota:** questo comando crea un processo pianificato ogni ora per pubblicare i CRL dalla CA nel server Web. Ciò è sufficiente per far fronte a una pianificazione che prevede la pubblicazione quotidiana o semi quotidiana di Delta CRL. Se la pianificazione CRL è più frequente, eseguire con maggiore frequenza il processo di copia. Un buon metodo consiste nel fare in modo che la pianificazione del processo di copia sia circa dal cinque al dieci percento della pianificazione delta CRL.

#### Gestione dell'archiviazione

La gestione dell'archiviazione si occupa dell'archiviazione dei dati sia interna che esterna per il ripristino dei dati e l'archiviazione cronologica. Il team di gestione dell'archiviazione dovrà garantire la protezione fisica dei backup e degli archivi. Obiettivo della gestione dell'archiviazione è definire, tenere traccia e mantenere dati e risorse di dati nell'ambiente di produzione IT.

##### Configurazione del backup del database dell'autorità certificazione emittente

Lo scopo di questa attività consiste nell'eseguire il backup di una copia dei certificati e delle chiavi private della CA, del database dei certificati e delle informazioni sulla configurazione di Servizi certificati. Le informazioni sulla configurazione di Servizi certificati includono tutte le informazioni sulla configurazione del sistema operativo ed altre informazioni sullo stato dalle quali dipende la CA.

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
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Le seguenti funzioni o processi devono essere attivi:<br />
- Backup su file/disco del server aziendale<br />  
- Percorsi di archiviazione protetti<br />
- Sistema di monitoraggio ed escalation degli avvisi (ad esempio, MOM)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Backup di Windows<br />
- Sistema di backup aziendale<br />  
- Servizio Utilità di pianificazione di Windows<br />
- SchTasks.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Questa attività configura un'attività pianificata per eseguire un backup notturno dello stato del sistema del server CA. Il backup della CA presuppone che il sistema di backup dei server aziendali sia attualmente disponibile. Il backup di questa procedura genera un file di backup di cui, a propria volta, il sistema aziendale eseguirà il backup. Potrebbe trattarsi di un backup in rete oppure di un backup su periferica locale. Questa soluzione presuppone inoltre che il sistema di backup dei server aziendali venga eseguito di notte in modo da eseguire il backup dei dischi del server CA.

**Nota:** se si utilizza un HSM, questa procedura può eseguire il backup dei dati relativi alle chiavi crittografate (a seconda del funzionamento di HSM) ma, generalmente, non è utilizzabile su un computer ripristinato senza un HSM identico e le stesse chiavi di accesso HSM. Per eseguire il backup e le procedure di protezione dei dati delle chiavi e delle chiavi di accesso, seguire le istruzioni del fornitore.

-   **Per configurare il backup di una CA**

    1.  Creare una directory nella quale archiviare i file di backup temporanei (C:\\CABackup) e proteggere tale directory eseguendo il comando seguente:
        ```

        (tenere presente che si tratta di un singolo comando che, per questioni di leggibilità, qui viene riportato su righe separate)

    2.  Se si sceglie un'altra cartella nella quale archiviare il backup, è necessario aggiornare l'impostazione correlata nel file pkiparams.vbs. Modificare il percorso specificando quello mostrato nella riga seguente, se necessario.
        ```

        **Nota:** dal momento che la stessa funzione di script viene utilizzata per eseguire il backup delle CA non in linea e in linea, se si utilizzano percorsi differenti per le diverse CA è necessario effettuare copie separate degli script.

    3.  Pianificare il processo di backup in modo che venga eseguito di notte mediante il seguente comando. Questo comando imposta l'esecuzione del processo ogni notte alle 02.00.
        ```

        **Nota:** questo comando viene mostrato su più righe; immetterlo come singola riga.

        Inoltre, le barre rovesciate che racchiudono il nome dello script C:\\MSSScripts\\ca\_operations.wsf sono necessarie solo se nel nome del percorso sono presenti degli spazi. Possono essere omesse se nel nome del percorso non sono presenti spazi.

    4.  Configurare il sistema di backup dei server aziendali in modo da eseguire il backup del contenuto della cartella temporanea di backup (C:\\CABackup) ogni notte su supporti rimovibili. Se possibile, impostare uno script preliminare per il controllo del file di blocco (il file BackupRunning.lck archiviato nella cartella temporanea di backup) creato durante l'esecuzione del file di script di backup. Se questo file esiste, significa che il backup precedente non è riuscito oppure è ancora in esecuzione. In alternativa, fare in modo che il sistema aziendale di backup esegua lo script di backup della CA sotto forma di processo di pre-esecuzione.

        **Nota:**
        lo script di backup BackupCADatabase controlla il file di blocco e, se presente, scrive un evento di errore nel registro dell'applicazione:

        Origine: Operazioni CA

        ID evento: 30

        Tipo evento: Errore

        Il backup CA potrebbe non essere avviato se è ancora presente il file di blocco C:\\CABackup\\BackupRunning.lck di un processo precedente. Ciò potrebbe significare che il backup precedente è ancora in esecuzione.

        Se il sistema di backup dei server aziendali non può eseguire controlli preliminari oppure non può eseguire gli script, pianificare l'inizio del backup in un orario adatto dopo l'avvio del backup dello stato del sistema. Per stimare il tempo necessario, eseguire il backup dello stato del sistema (con la **verifica** abilitata) sul server con Servizi certificati chiuso (la chiusura della CA impedisce che i registri della CA vengano troncati per questo backup di prova). Questa operazione dovrebbe eseguire il backup di circa 500 MB di dati dello stato del sistema. Calcolare il tempo impiegato per questa operazione e calcolare approssimativamente il tempo previsto per il backup di un database CA e dello stato del sistema:
        ```

        Se il tempo impiegato solo per l'esecuzione del backup dello stato del sistema è di 10 minuti, impostare 70 minuti per una CA con 3000 utenti (si presuppone che siano presenti cinque certificati per ciascun utente e computer, per anno, archiviati per cinque anni). Si tratta solo di un'indicazione sommaria; aggiungere la previsione per il database dei certificati — 1 GB per ogni 50000 certificati.

    5.  Archiviare i supporti di backup in modo appropriato.

**Avviso:** i dati di questo backup sono estremamente importanti in quanto contengono i dati delle chiavi private per la CA. È necessario trasferire ed archiviare il backup prestando la stessa attenzione e garantendo la stessa protezione adottate per la CA. Archiviare i dati del backup in una sede fisica diversa da quella della CA. Ciò consentirà di ripristinare la CA nell'eventualità in cui tutti i computer dovessero subire dei danni oppure diventino inaccessibili.

##### Configurazione del backup del database autorità di certificazione principale

Lo scopo di questa attività consiste nel preparare per il backup i certificati e le chiavi private della CA, il database dei certificati e le informazioni di configurazione di Servizi certificati. Le informazioni sulla configurazione di Servizi certificati includono tutte le informazioni sulla configurazione del sistema operativo ed altre informazioni sullo stato dalle quali dipende la CA.

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
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>- Periferica di backup locale con una capacità superiore a 500 MB<br />
- Percorsi di archiviazione protetti</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Backup di Windows<br />
- Supporti rimovibili (quale CD-RW o nastro)</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Generalmente la CA principale emette solo pochi certificati, quindi la dimensione dei dati non è mai elevata. I dati cambiano raramente, generalmente una volta ogni qualche anno. La procedura dovrebbe inoltre essere la stessa per qualsiasi altra CA non in linea, ad esempio una CA intermedia non in linea, se si è scelto di utilizzare CA intermedie.

La CA principale non è in linea, quindi richiede determinati tipi di dispositivi locali di backup (quale unità a nastro o CD scrivibile) sui quali archiviare il file di backup.

**Avviso:** se si utilizza un HSM, questa procedura può eseguire il backup dei dati relativi alle chiavi crittografate (a seconda del funzionamento di HSM) ma, generalmente, non è utilizzabile su un computer ripristinato senza un HSM identico e le stesse chiavi di accesso. Per eseguire il backup e le procedure di protezione dei dati delle chiavi e delle chiavi di accesso, seguire le istruzioni del fornitore.

-   **Per configurare il backup di una CA**

    1.  Creare una directory nella quale archiviare i file di backup (C:\\CABackup) e proteggere la directory eseguendo il comando seguente:
        ```

        **Nota:** questo comando viene mostrato su due righe; immetterlo come singola riga.

    2.  Se si sceglie un'altra cartella nella quale archiviare il backup, è necessario aggiornare l'impostazione correlata nel file pkiparams.vbs. Modificare il percorso specificando quello mostrato nella riga seguente, se necessario.
        ```

##### Backup del database autorità di certificazione principale

Lo scopo di questa attività consiste nel creare copie di backup dei certificati e delle chiavi private della CA, del database dei certificati e delle informazioni sulla configurazione di Servizi certificati. Le informazioni sulla configurazione di Servizi certificati includono tutte le informazioni sulla configurazione del sistema operativo ed altre informazioni sullo stato dalle quali dipende la CA.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Ogni volta che un nuovo certificato viene emesso o revocato.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>CA Backup Operators</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>- Periferica di backup locale con una capacità superiore a 500 MB<br />
- Percorsi di archiviazione protetti</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Backup di Windows<br />
- Supporti rimovibili (quale CD-RW o nastro)</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Generalmente la CA principale emette solo pochi certificati, quindi la dimensione dei dati non è mai elevata. I dati cambiano raramente, generalmente una volta ogni qualche anno. La procedura dovrebbe inoltre essere la stessa per qualsiasi altra CA non in linea, ad esempio una CA intermedia non in linea , se si è scelto di utilizzare CA intermedie.

La CA principale non è in linea, quindi richiede determinati tipi di dispositivi locali di backup (quale unità nastro o CD scrivibile).

**Avviso:** se si utilizza un HSM, questa procedura può eseguire il backup dei dati relativi alle chiavi crittografate (a seconda del funzionamento di HSM) ma, generalmente, non è utilizzabile su un computer ripristinato senza un HSM identico e le stesse chiavi di accesso. Per eseguire il backup e le procedure di protezione dei dati delle chiavi e delle chiavi di accesso, seguire le istruzioni del fornitore.

-   **Per eseguire il backup della CA principale**

    1.  Eseguire il comando seguente per effettuare il backup dei dati della CA in un file temporaneo:
        ```

    2.  Questo comando crea un file di backup (CABackup.bkf) nel percorso scelto in precedenza (percorso predefinito C:\\CABackup). Copiare questo file su un supporto rimovibile e archiviare il supporto di backup in modo appropriato.

**Avviso:** i dati di questo backup sono estremamente importanti in quanto contengono i dati delle chiavi private per la CA. È necessario trasferire ed archiviare il backup prestando la stessa attenzione e garantendo la stessa protezione adottate per la CA. Archiviare i dati del backup in una sede fisica diversa da quella della CA. Ciò consentirà di ripristinare la CA nell'eventualità in cui tutti i computer dovessero subire dei danni oppure diventino inaccessibili.

##### Backup di chiavi e certificati CA

Il backup delle chiavi e dei certificati CA dovrebbe essere eseguito indipendentemente dal database dei certificati. È possibile che ai certificati e alle chiavi private CA venga richiesto di firmare un elenco delle revoche dei certificati (CRL)o un certificato nel caso in cui il server CA non funzioni e non possa essere ripristinato in tempi sufficienti.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>- Annuale<br />
- Ogni volta che il certificato CA viene rinnovato (in base a quale evento si verifica per primo)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>CA Backup Operators</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>- Backup dei dischi/file del server aziendale<br />
- Percorsi di archiviazione protetti</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Certutil.exe<br />
- Script MSS</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

I certificati e le chiavi CA occupano solo pochi KB (kilobyte) di archiviazione e quindi possono essere salvati su un disco. Questa attività viene applicata alla CA principale e a tutte le CA di emissione e intermedie dell'organizzazione.

**Avviso:** se si utilizza un HSM, questa procedura non funziona come indicato. Per eseguire il backup e le procedure di protezione dei dati delle chiavi e delle chiavi di accesso, seguire le istruzioni del fornitore.

-   **Per esportare le chiavi e i certificati sul disco**

    1.  Eseguire il comando seguente:
        ```

        Eseguire almeno due backup separati su dischi diversi (i dischi non sono sempre affidabili al cento per cento). Etichettare e datare in modo chiaro i dischi, considerando quanto tempo può trascorrere prima che debbano essere utilizzati.

        Lo script precedente utilizza certutil.exe per esportare i certificati e le chiavi CA su un file PKCS\#12 (P12):

        **A**:\\CAKeyBackup\\CAComputerName\\yymmdd\_hhmm\\CA Common Name.p12

    2.  Immettere una password, quando richiesto.

        **Importante:** registrare ed archiviare questa password in un altro percorso, ugualmente protetto, diverso da quello dei backup delle chiavi. La registrazione della password deve indicare in modo chiaro il backup al quale si riferisce (etichetta del disco, data e nome della CA). Potrebbero trascorrere molti mesi oppure anni prima che queste chiavi siano necessarie ed è molto probabile che nessuno si ricordi la password utilizzata in precedenza. Accertarsi di eliminare tutte le altre registrazioni della password. Non utilizzare una password conosciuta dallo staff dell'amministrazione.

    3.  Archiviare il disco in modo appropriato. Come per i backup dei database della CA, trattare i backup delle chiavi con la massima sicurezza. Archiviare almeno due backup delle chiavi e dei certificati in due posizioni protette separate.

##### Test dei backup per database autorità di certificazione

Controllare i backup della CA per essere sicuri che la tecnologia ed il processo di siano stati eseguiti in modo corretto.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>- Prima che la CA sia operativa<br />
- Mensilmente<br />
- Eseguire di nuovo il test ogni volta che il processo o la tecnologia di backup viene aggiornata</p></td>
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
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Backup di Windows<br />
- Sistema aziendale di backup<br />  
- Certutil.exe<br />
- Cipher.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

È necessario ripristinare il backup dello stato del sistema su un sistema con la stessa configurazione del disco. Ad esempio, Windows deve essere installato nello stesso percorso di directory del sistema di cui è stato effettuato il backup e la configurazione dell'unità per l'archiviazione dei file di Windows (quali file di paging), i registri e il database della CA devono essere uguali a quelli della CA di cui è stato eseguito il backup.

**Importante:** il server di test ripristinato non deve essere mantenuto in linea dal punto in cui il file di backup dello stato del sistema è stato ripristinato dal supporto di backup e certamente prima dell'avvio del ripristino dello stato del sistema. Questo per impedire che le chiavi CA ripristinate vengano esposte senza motivo, ma anche per impedire il verificarsi di conflitti di indirizzi IP e nomi duplicati tra il server originale e quello di test.

**Avviso:** se si utilizza un HSM, questa procedura non è sufficiente per ripristinare completamente la CA. A seconda del funzionamento del modulo HSM, il computer ripristinato non è utilizzabile senza lo stesso HSM e le stesse chiavi di accesso HSM. Queste operazioni possono essere sufficienti per un test normale ma è consigliabile eseguire regolarmente un ripristino completo con il ripristino HSM per essere sicuri che le procedure e la tecnologia di backup funzionino correttamente. Per eseguire il backup e le procedure di recupero e protezione dei dati delle chiavi e delle chiavi di accesso, seguire le istruzioni del fornitore.

-   **Per ripristinare la CA**

    1.  Ripristinare il file di backup dello stato del sistema dal supporto di backup nella cartella C:\\CABackup.

    2.  Eseguire l'utilità di backup di Windows e selezionare il file di backup ripristinato in C:\\CABackup. È necessario essere un membro di un gruppo che dispone delle autorizzazioni di backup e ripristino sulla macchina (ad esempio CA Backup Operators, Backup Operators o Administrators).

    3.  Fare clic su **Ripristina**.

    4.  Riavviare il sistema.

    5.  Verificare che tutte le operazioni vengano eseguite come previsto.

    6.  Alla fine del test, eliminare i dati del server di prova (o almeno le chiavi).

**Importante:** se si decide di eliminare solo le chiavi, eseguire il comando cipher per cancellare le parti del disco non allocate:

**Cipher /W*:%AllUsersProfile%***

Per eseguire questa operazione, è necessario essere un membro del gruppo Administrators locale. Il percorso %allusersprofile% viene utilizzato in modo tale che il comando cipher possa operare sull'unità nella quale sono presenti i dati relativi alle chiavi.

##### Test dei backup per chiave autorità di certificazione

Controllare i backup delle chiavi CA regolarmente per essere sicuri che siano validi, nel caso dovessero servire.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>- Attività di impostazione (prima che la CA sia operativa)<br />
- Ogni sei mesi</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratori locali su computer di prova</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Backup precedente delle chiavi CA</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Certutil.exe<br />
- Cipher.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

È possibile installare i certificati e le chiavi CA su qualsiasi sistema (sebbene, a causa della loro natura estremamente sensibile, dovrebbe essere un sistema non in linea e attendibile, soprattutto nel caso di chiavi della CA principale non in linea). Per garantire che tutte le tracce dei dati delle chiavi vengano rimosse dal computer, creare un account separato e temporaneo dedicato a questa operazione.

**Avviso:** se si utilizza un HSM, questa procedura non funziona come indicato. Per eseguire il backup, il ripristino e le procedure di protezione dei dati delle chiavi e delle chiavi di accesso, seguire le istruzioni del fornitore.

-   **Per ripristinare le chiavi CA**

    1.  Verificare che il computer sia stato disconnesso dalla rete ed accedere come membro del gruppo Administrators locale, quindi creare l'account utente locale **TestCAKeys**.

    2.  Accedere utilizzando questo account.

    3.  Inserire un disco contenente il backup delle chiavi CA da testare.

    4.  Utilizzare Esplora risorse per selezionare i file delle chiavi P12 fare doppio clic su **Importazione guidata**.

    5.  Immettere la password quando richiesto e non selezionare le caselle di controllo per fornire alta protezione alle chiavi o per renderle esportabili.

    6.  Fare clic su **Mettere tutti i certificati nel seguente archivio**, quindi **Sfoglia** e selezionare **Archivio personale** come posizione nella quale ripristinare le chiavi CA.

    7.  Aprire la console di gestione dei certificati e scegliere l'archivio personale. Individuare il certificato CA per la CA ripristinata, quindi aprire il certificato per verificare di disporre della chiave privata corrispondente.

<!-- -->

-   **Per testare le chiavi ripristinate**

    1.  Ottenere un CRL o un certificato emesso dalla CA da testare.

    2.  A seconda della scelta di un CRL o di un certificato nel passaggio precedente, eseguire uno dei comandi seguenti, sostituendo *CRLFileName* o *CertFileName* con il nome del file ottenuto in precedenza:
        ```

    3.  Quando richiesto, selezionare il certificato CA (importato nella procedura precedente) come certificato di firma.

    4.  Verificare che l'operazione di firma venga eseguita correttamente e che l'output sia simile al seguente:

        C:\\CAConfig&gt;certutil -sign "Woodgrove Bank Issuing CA 1.crl"
        "Woodgrove Bank Issuing CA 1xxs.crl"

        ThisUpdate: 2/10/2003 10:52 PM

        NextUpdate: 2/25/2003 3:11 PM

        CRL Entries: 0

        Signing certificate Subject:

        CN=Woodgrove Bank Issuing CA 1

        DC=woodgrovebank,DC=com

        Output Length = 970

        CertUtil: -sign command completed successfully.

È necessario eliminare le chiavi dal sistema di test.

-   **Per eliminare le chiavi dal sistema**

    1.  Accedere come membro del gruppo Administrators locale ed eliminare il profilo utente dell'account **TestCAKeys** (utilizzando **Proprietà avanzate** in Computer locale).

    2.  Eliminare l'account **TestCAKeys**.

    3.  Cancellare le aree non allocate del disco per rimuovere in modo permanente le tracce delle chiavi eseguendo il comando seguente:
        ```

**Nota:** specificando *%allusersprofile%* come percorso si garantisce che Cipher.exe operi sull'unità contenente i profili utente. L'esecuzione di questo comando elimina il contenuto dell'intera unità, non solo il percorso specificato.

##### Archiviazione e rimozione di dati vecchi dal database dei certificati della CA di emissione

Il database della CA aumenta in modo uniforme ad ogni certificato emesso e le sue dimensioni non diminuiscono mai. Tuttavia, i certificati scaduti non sono più necessari all'interno del database e possono essere eliminati. Maggiori sono le dimensioni del database e maggiore è la durata delle operazioni quali l'avvio e la chiusura della CA e la ricerca di un certificato nel database. Quindi, è consigliabile eliminare regolarmente i dati vecchi dal database.

Non eliminare gli elenchi CRL dal database in quanto potrebbero essere necessari per verificare la validità delle firme create in passato. Ad esempio, potrebbe essere necessario utilizzarli per verificare che un certificato non sia stato revocato quando è stato utilizzato per firmare un documento *x* anni prima.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Annuale</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>CA Backup Operators<br />
Amministratori locali sulla CA</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Certutil.exe<br />
- Supporti rimovibili (quale CD-RW o nastro)<br />  
or<br />
- Sistema aziendale di backup</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Questa procedura è applicabile solo alla CA di emissione; dal momento che la CA principale emette solo pochi certificati, non avrà mai problemi di archiviazione del database dei certificati.

1.  Accedere alla CA come membro del gruppo CA Backup Operators.

2.  Archiviare il database CA esistente utilizzando il comando seguente:
        ```

    **Avviso:** Se deve essere ripristinato un normale backup, non seguire la procedura inclusa nella sezione "[Configurazione di un backup per database dell'autorità di certificazione emittente](#a9)" in quanto tronca i registri e potrebbe provocare perdita di informazioni.

3.  Copiare il contenuto del database *BackupFolder*/su un supporto rimovibile e memorizzarlo in un archivio protetto.

4.  Disconnettersi e accedere di nuovo come membro del gruppo Administrators locale.

5.  Eliminare le richieste di certificati antecedenti alla data *mm/dd/yyyy* mediante l'esecuzione del comando seguente:
        ```

6.  Eliminare i certificati scaduti prima della data *gg/mm/yyyy* eseguendo il comando seguente (la validità massima dei certificati emessi da questa CA è di due anni, quindi tre anni è un periodo sicuro ma si potrebbe voler lasciare cinque anni o più):
        ```

##### Archiviazione di dati di controllo della protezione da una CA

Archiviare e memorizzare i registri di controllo in base ai requisiti legali o regolatori o ai criteri di protezione interni.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>- Mensile (CA di emissione)<br />
- Ogni sei mesi (CA principale)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>- CA Auditors<br />
Amministratori locali sulla CA</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Supporti rimovibili per copiare il registro eventi</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Visualizzatore eventi<br />
- Supporti rimovibili (quale CD-RW o nastro)</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

-   **Per archiviare il registro eventi di protezione**

    1.  Accedere al server come membro del gruppo CA Auditors e del gruppo Administrators locale (creare un account membro di entrambi i gruppi).

    2.  Aprire Visualizzatore eventi facendo clic su **Start**, **Tutti i programmi** e **Strumenti di amministrazione**.

    3.  Fare clic sulla cartella registro Protezione.

    4.  Fare clic con il pulsante destro del mouse su di essa, quindi fare clic su **Salva registro con nome**.

    5.  Salvare il registro in un file temporaneo.

    6.  Copiare su un supporto rimovibile (CD-RW), quindi eliminare il file temporaneo.

##### Esportazione di un modello di certificato da Active Directory

È possibile salvare le definizioni del modello di certificato della directory in modo che possano essere ripristinate in futuro senza dover eseguire un ripristino completo della directory.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Utenti di dominio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- ldifde.exe<br />
- MMC Modelli di certificato</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Questa procedura descrive un modo semplice per esportare su file un oggetto Active Directory di modello di certificato. Questo può essere importato di nuovo nella directory, se necessario. Questo metodo salva solo le informazioni LDAP (Lightweight Directory Access Protocol) dell'oggetto modello. Altre informazioni, ad esempio le informazioni sulla protezione(proprietà, autorizzazioni e così via) non vengono mantenute utilizzando questo processo.

**Nota:** il modo migliore per eseguire il backup ed il ripristino di oggetti Active Directory consiste nell'utilizzare un metodo di backup di directory dedicato come il backup dello stato del sistema di Windows. Tuttavia, il ripristino di una versione precedente di un oggetto modificato richiede un ripristino autorevole di Active Directory che è una procedura complessa. Questa procedura descrive un modo semplice per eseguire il backup ed il ripristino di un'istantanea di un oggetto modello di certificato.

-   **Per esportare un oggetto modello di certificato**

    1.  Determinare il nome del modello di cui si desidera eseguire il backup. Non deve trattarsi necessariamente dello stesso nome di modello visualizzato. Esaminare le proprietà del modello nella scheda **Generale** del modello (utilizzando MMC Modelli di certificato) per vedere il **Nome modello** e il **Nome visualizzato modello**.

    2.  Accedere ad un server membro di dominio o controller di dominio utilizzando un account utente di dominio.

    3.  Eseguire il comando seguente per salvare i dettagli del modello nel file templatename.ldif, sostituendo *templatename* con il nome del modello di certificato e *DC=woodgrovebank,DC=com* con il nome del dominio dell'insieme di strutture:
        ```

        Questo comando viene mostrato su più righe; immetterlo come singola riga.

    4.  Il file *templatename*.ldif verrà salvato nella directory corrente. Archiviare il file *templatename*.ldif in modo sicuro.

##### Importazione di un modello di certificato in Active Directory

Nel caso in cui si desideri ripristinare un modello dal backup, ad esempio, per ripristinare una modifica apportata ad un modello, è possibile importare di nuovo in Active Directory la definizione del modello di certificato salvata in precedenza.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>È possibile che si renda necessario ripristinare un modello dal backup per annullare modifiche non desiderate apportate al modello.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>ldifde.exe</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Questa procedura descrive come ripristinare la definizione di un modello di certificato da un file. Il file deve essere stato creato in precedenza mediante la procedura "[Esportazione di un modello di certificato da Active Directory](#a10)". Questo metodo ripristina solo le informazioni LDAP dell'oggetto modello. Altre informazioni, ad esempio le informazioni sulla protezione(proprietà, autorizzazioni e così via) non vengono mantenute utilizzando questo processo.
  
**Nota:** il modo migliore per eseguire il backup ed il ripristino degli oggetti Active Directory consiste nell'utilizzare un metodo di backup di directory dedicato come il backup dello stato del sistema di Windows. Tuttavia, il ripristino di una versione precedente di un oggetto modificato richiede un ripristino autorevole di Active Directory che è una procedura complessa. Questa procedura descrive un modo semplice per eseguire il backup ed il ripristino di un'istantanea di un oggetto modello di certificato.
  
Questa procedura non sostituisce quella di backup e ripristino di Active Directory e deve essere utilizzata solo nelle specifiche circostanze descritte.
  
-   **Per importare un oggetto modello di certificato**
  
    1.  Recuperare il file della definizione del modello esportato creato mediante la procedura "[Esportazione di un modello di certificato da Active Directory](#a10)".
  
    2.  Accedere ad un server membro di dominio o ad un controller di dominio come membro del gruppo Enterprise PKI Admins.
  
    3.  Se si sostituisce un modello esistente, eseguire il backup del modello da sostituire (utilizzando la procedura descritta in precedenza). Prendere nota delle autorizzazioni del modello ed eliminarlo.
  
    4.  Aprire il file con Blocco note o un editor di testo simile e ricercare la riga che inizia con "objectGUID:" la riga dovrebbe essere simile alla seguente (sebbene i caratteri dopo la virgola sono differenti):
  
        objectGUID:: b/pVt//+I0i9hp8aJ7IWRg==
  
    5.  Eliminare la riga, prestando attenzione a non apportare altre modifiche al file e salvarlo.
  
    6.  Eseguire il comando seguente per importare il modello in Active Directory dal file *templatename*.ldif, sostituendo *templatename* con il nome del modello di certificato:
  
        <codesnippet language displaylanguage containsmarkup="false"> ldifde -f templatename.ldif -i  
```
  
    7.  Verificare che la procedura funzioni aprendo lo snap-in Modelli di certificato e visualizzando il modello ripristinato.
  
    8.  Applicare al modello ripristinato le autorizzazioni di cui si è preso nota nel passaggio 3 oppure applicare quelle appropriate per questo modello.
  
#### Monitoraggio e controllo dei servizi
  
Il monitoraggio dei servizi consente al personale operativo di osservare la condizione di un servizio IT in tempo reale.
  
Nei punti di questa sezione in cui si fa riferimento a MOM si presume che la distribuzione di MOM segua le indicazioni della *Guida operativa a MOM*.
  
MOM non è richiesto; viene utilizzato semplicemente a scopo illustrativo. Consultare la sezione "[Ulteriori informazioni](#xsltsection133121120120)" alla fine di questo modulo per ulteriori informazioni su *MOM Operations Guide*.
  
##### Classificazione degli avvisi di monitoraggio
  
Il sistema di monitoraggio dovrebbe segnalare solo gli avvisi più significativi al personale operativo. Se tutti gli errori di minore entità venissero classificati in modo da generare avvisi di richiesta di supporto, il personale operativo in breve non riuscirebbe più a definire l'urgenza delle operazioni.

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
  
**Tabella 10. Categorie di avviso**

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
<td style="border:1px solid black;"><p>Quando l'applicazione genera un messaggio di avviso che non richiede un'azione amministrativa o una risoluzione immediata o che addirittura non richiede alcuna azione. L'applicazione o il componente funziona a un livello di prestazioni accettabile ed è ancora in grado di eseguire tutte le operazioni critiche. Tuttavia, se il problema persiste, questa situazione potrebbe diventare una situazione di Errore, Errore critico o Servizio non disponibile.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Quando l'applicazione genera un evento informativo. L'applicazione o il componente funziona a un livello di prestazioni accettabile ed esegue tutte le operazioni critiche e non critiche.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Operazione riuscita</p></td>
<td style="border:1px solid black;"><p>Quando l'applicazione genera un evento riuscito. L'applicazione o il componente è operativo ad un livello di prestazioni accettabile ed esegue tutte le operazioni critiche e non critiche.</p></td>
</tr>  
</tbody>  
</table>
  
##### Monitoraggio restrizioni capacità Servizi certificati
  
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
<td style="border:1px solid black;"><p>Infrastruttura</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Attività di configurazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Autorizzazione obbligatoria richiesta dalla soluzione di monitoraggio.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>L'output viene inserito nella funzione SMF Gestione capacità.</p></td>
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

I seguenti contatori di prestazioni sono i più utili per identificare le restrizioni delle capacità in Servizi certificati. Processore e disco sono le due risorse maggiormente utilizzate da Servizi certificati e quindi le restrizioni indicate saranno ad un livello precedente a quelle di rete o di memoria.

**Tabella 11. Principali contatori di monitoraggio capacità per Servizi certificati**

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
<td style="border:1px solid black;"><p>D: (CA - DB)<br />
C: (CA - Log)</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Interfaccia di rete</p></td>
<td style="border:1px solid black;"><p>Byte totali/sec</p></td>
<td style="border:1px solid black;"><p>Scheda di rete</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Memoria</p></td>
<td style="border:1px solid black;"><p>% Byte vincolati in uso</p></td>
<td style="border:1px solid black;"><p>- - -</p></td>
</tr>  
</tbody>  
</table>
  
Per ulteriori informazioni generali sulle restrizioni della capacità ed i contatori delle prestazioni correlati, vedere Microsoft Knowledge Base Q146005, "Optimizing Windows NT for Performance" all'indirizzo: <http://support.microsoft.com/default.aspx?scid=146005>.
  
È inoltre essenziale monitorare gli indicatori di capacità su qualsiasi infrastruttura di supporto. Gli elementi chiave sono:
  
-   Le comunicazioni di Servizi certificati con Active Directory (le CA dell'organizzazione di grandi dimensioni utilizzano Active Directory per i servizi di autenticazione ed autorizzazione, per leggere ed archiviare le informazioni sulla configurazione dell'autorità di certificazione dell'infrastruttura PKI e, a seconda del tipo di certificato, per pubblicare i certificati emessi sulla directory).
  
-   Le comunicazioni correlate ai certificati client con Active Directory (i client leggono le informazioni sull'autorità di certificazione e sull'infrastruttura PKI da Active Directory; ciò implica il download di CRL di diversi MB, per client, per settimana).
  
-   Le comunicazioni correlate ai certificati client con il server Web (i client possono recuperare i certificati CA e gli elenchi CRL dal server Web, sebbene sia improbabile che questa operazione produca un carico tale da causare restrizioni di capacità a meno che il server non sia già estremamente carico).
  
##### Monitoraggio integrità e disponibilità Servizi certificati
  
Le autorità di certificazione generalmente non forniscono servizi in linea o in tempo reale (mentre servizi quali Active Directory o Microsoft SQL Server™, ad esempio, devono essere costantemente in linea per poter fornire un servizio utile). Tuttavia, vi sono molti aspetti dell'operatività della CA che sono critici e che richiedono risposte in linea:
  
-   Disponibilità delle informazioni di revoca — un CRL corrente deve essere disponibile per qualsiasi utente che desideri controllare lo stato di revoca di un certificato.
  
-   Validità del certificato CA — una CA deve avere un certificato attualmente valido. Un certificato CA non valido impedisce la convalida di qualsiasi certificato emesso dalla CA o dalle sue subordinate. Impedisce inoltre l'emissione di nuovi certificati.
  
-   Disponibilità del servizio di registrazione certificati — nessuno può registrare o rinnovare un certificato se il servizio CA non è disponibile.
  
La non disponibilità dei primi due ha generalmente un impatto maggiore rispetto alla non disponibilità dell'ultimo.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Gestione delle operazioni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Attività di configurazione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratore MOM (o sistema di monitoraggio)</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Registro gestione modifica e rilascio</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Script MSS<br />
- Console avvisi operativi (quale MOM o infrastruttura di posta elettronica)<br />
- Agenti MOM o Servizio Utilità di pianificazione di Windows per l'esecuzione</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Gli eventi riportati nella tabella seguente sono i più significativi per Servizi certificati. Controllarli ed assicurarsi che, nel caso in cui si verificassero, vengano prodotti gli avvisi appropriati.

**Tabella 12. Criticità dei principali eventi Servizi certificati**

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
<td style="border:1px solid black;"><p>Un CRL valido non è accessibile — ciò sta attualmente causando una perdita di servizio.</p></td>
<td style="border:1px solid black;"><p>Servizio non disponibile</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>CRL pronto</p></td>
<td style="border:1px solid black;"><p>L'elenco CRL è ancora valido ma un nuovo elenco CRL è pronto e dovrebbe essere stato pubblicato.</p></td>
<td style="border:1px solid black;"><p>Critica</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>CRL non disponibile<br />
Eventi secondari:<br />  
- Il CRL non può essere recuperato da Active Directory<br />
- Il CRL non può essere recuperato dal server Web</p></td>
<td style="border:1px solid black;"><p>Un CRL non è disponibile nel punto di distribuzione CRL pubblicato. Ciò potrebbe causare perdita di servizio.</p></td>
<td style="border:1px solid black;"><p>Critica</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Server CA non riuscito</p></td>
<td style="border:1px solid black;"><p>Il server non è visibile sulla rete</p></td>
<td style="border:1px solid black;"><p>Servizio non disponibile</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Integrità del sistema operativo CA in stato critico</p></td>
<td style="border:1px solid black;"><p>Presenza di un problema di entità maggiore con Windows o l'hardware del server</p></td>
<td style="border:1px solid black;"><p>Critica</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Integrità del sistema operativo CA in stato di errore/avviso</p></td>
<td style="border:1px solid black;"><p>Presenza di problemi non critici con Windows o l'hardware del server</p></td>
<td style="border:1px solid black;"><p>Errore o Avviso (come definito dalle regole MOM)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Servizi certificati non in linea<br />
Eventi secondari:<br />  
Interfaccia client non in linea<br />
Interfaccia di amministrazione non in linea</p></td>
<td style="border:1px solid black;"><p>L'interfaccia RPC (Remote Procedure Call) di Servizi certificati non è in linea — i certificati non possono essere emessi.</p></td>
<td style="border:1px solid black;"><p>Critica</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Certificato CA scaduto<br />
Eventi secondari:<br />  
Questo certificato CA è scaduto<br />
Il certificato CA padre è scaduto</p></td>
<td style="border:1px solid black;"><p>Il certificato della CA è scaduto — ciò attualmente causa una perdita di servizio.</p></td>
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
<td style="border:1px solid black;"><p>Avviso</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Backup CA non riuscito</p></td>
<td style="border:1px solid black;"><p>Backup dello stato del sistema della CA non riuscito — possibile perdita di informazioni.</p></td>
<td style="border:1px solid black;"><p>Critico o Errore</p></td>
</tr>  
</tbody>  
</table>
  
Per controllare questi eventi, è possibile utilizzare gli script forniti nella Tabella 13. Quando viene rilevato un errore, la logica degli script consiste nello scrivere gli eventi nel registro delle applicazioni di Windows. Questi eventi possono essere rilevati dagli agenti MOM o da un'altra soluzione di monitoraggio. Gli script inoltre inviano un messaggio di posta elettronica in risposta alle condizioni di avviso. Quando viene utilizzato il sistema MOM (o un altro sistema di monitoraggio basato su agenti), gli script riportati di seguito devono essere eseguiti dall'agente client MOM. Se non è presente alcun agente di gestione in grado di effettuare questa operazione, utilizzare il servizio Utilità di pianificazione di Windows per eseguire questi controlli almeno ogni ora. Gli script sono stati progettati per essere eseguiti sulla CA di emissione in linea, sebbene eseguano anche controlli sui certificati e sui CRL a partire dalle CA padre non in linea fino alla CA principale. Gli ID evento generati dagli script di monitoraggio sono mostrati nella Tabella 13.
  
**Tabella 13. Script di monitoraggio di Servizi certificati**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Evento</p></th>  
<th><p>Script o metodo di rilevamento</p></th>  
<th><p>Origine e ID evento</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>CRL scaduto</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCRLs</p></td>
<td style="border:1px solid black;"><p>Operazioni CA<br />
20</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>CRL pronto</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCRLs</p></td>
<td style="border:1px solid black;"><p>Operazioni CA<br />
21</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>CRL non disponibile<br />
Eventi secondari:<br />  
- Il CRL non può essere recuperato da Active Directory<br />
- Il CRL non può essere recuperato dal server Web</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCRLs</p></td>
<td style="border:1px solid black;"><p>Operazioni CA<br />
22<br />
23</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Server CA non riuscito</p></td>
<td style="border:1px solid black;"><p>Rilevamento errore server MOM nativo</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Integrità del sistema operativo CA in stato critico</p></td>
<td style="border:1px solid black;"><p>Monitoraggio integrità server MOM nativo</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Integrità del sistema operativo CA in stato di errore/avviso</p></td>
<td style="border:1px solid black;"><p>Monitoraggio integrità server MOM nativo</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Servizi certificati in linea<br />
Eventi secondari:<br />  
Interfaccia client non in linea<br />
Interfaccia di amministrazione non in linea</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: IsCAAlives</p></td>
<td style="border:1px solid black;"><p>Operazioni CA<br />
1<br />
2</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Certificato CA scaduto<br />
Eventi secondari:<br />  
Questo certificato CA è scaduto<br />
Il certificato CA padre è scaduto</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCACerts</p></td>
<td style="border:1px solid black;"><p>Operazioni CA<br />
10</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>La validità rimanente del certificato CA è inferiore a 1 mese</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCACerts</p></td>
<td style="border:1px solid black;"><p>Operazioni CA<br />
11</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>La validità del certificato CA è inferiore alla metà del suo periodo di validità</p></td>
<td style="border:1px solid black;"><p>Script: Ca_monitor.wsf<br />
Job: CheckCACerts</p></td>
<td style="border:1px solid black;"><p>Operazioni CA<br />
12</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Backup CA bloccato (non è stato possibile eseguire lo script di backup in quanto era ancora presente un comando di blocco file del backup precedente)</p></td>
<td style="border:1px solid black;"><p>Script: Ca_operations.wsf<br />
Job: BackupCADatabase</p></td>
<td style="border:1px solid black;"><p>Operazioni CA<br />
30</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Backup CA non riuscito</p></td>
<td style="border:1px solid black;"><p>Il codice di errore per NTBackup.exe viene fornito in questa situazione, sebbene si basi sulle capacità di MOM o di un altro sistema di monitoraggio per avvisare sui problemi di backup (tenere presente che è necessario controllare sia il sistema di backup dello stato del sistema che quello aziendale).</p></td>
<td style="border:1px solid black;"><p>Ntbackup<br />
8019</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Altro evento</p></td>
<td style="border:1px solid black;"><p>Errore di esecuzione di Ca_monitor.wsf</p></td>
<td style="border:1px solid black;"><p>Operazioni CA<br />
100</p></td>
</tr>
</tbody>
</table>
<p> </p>

Prima della distribuzione degli script, aggiornare il file constants.vbs con i parametri di avviso corretti. Le sezioni rilevanti del file sono mostrate di seguito:
        ```
È necessario specificare se si desidera che gli errori producano avvisi di posta elettronica o avvisi registro eventi o entrambi. Se sono stati specificati avvisi di posta elettronica, è necessario fornire un elenco di destinatari di posta elettronica valido (separati dalla virgola) e il nome host del server SMTP o l'indirizzo IP. Entrambe queste stringhe devono essere racchiuse tra virgolette.

Se è stato specificato l'avviso registro eventi, è necessario modificare il parametro **CA\_EVENT\_SOURCE** (usato per tutti gli eventi CA correlati) o **EVENT\_SOURCE** (usato per tutti gli eventi non correlati alla CA).

La sintassi e l'uso degli script di monitoraggio sono descritti nella sezione seguente:

-   **Per controllare la scadenza del certificato CA**

    Questo script controlla i certificati della CA di emissione (dove viene eseguito lo script) e della CA padre fino alla CA principale inclusa.
        ```

    L'esecuzione di questo script avvisa sulle seguenti condizioni:

    -   Il certifica CA è scaduto (ID evento 12).

    -   La validità alla scadenza del certificato CA è inferiore ad un mese (ID evento 11).

    -   Il certificato CA ha superato la metà della durata del suo periodo di validità (ID evento 12).

-   **Per controllare la scadenza dell'elenco CRL**

    Questo script controlla il CRL della CA di emissione e i CRL di tutte le CA padre fino alla CA principale inclusa.
        ```

    L'esecuzione di questo script avvisa sulle seguenti condizioni:

    -   Il CRL è scaduto (ID evento 20).

    -   Il CRL ha superato la data specificata in "Pubblicazione CRL successiva" ed è scaduto (ID evento 21).

    -   Il CRL non può essere recuperato da CDP LDAP (ID evento 22).

    -   Il CRL non può essere recuperato da CDP HTTP (ID evento 23).

        (CDP FTP e FILE attualmente non vengono controllati nello script).

-   **Per controllare un servizio CA non in linea**

    Questo script controlla solo la CA sulla quale è in esecuzione.
        ```

    L'esecuzione di questo script avvisa sulle seguenti condizioni:

    -   L'interfaccia client RPC della CA non risponde (ID evento 1).

    -   L'interfaccia di amministrazione RPC della CA non risponde (ID evento 2).

##### Monitoraggio della protezione dell'autorità di certificazione

Servizi certificati produce una varietà di voci di registro di controllo in risposta ai diversi eventi di protezione. La maggior parte di queste voci è il risultato di attività operative quotidiane. Tuttavia, alcuni eventi indicano le principali modifiche di configurazione che è inoltre necessario controllare.

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
<td style="border:1px solid black;"><p>- CA Auditors (per analizzare il registro di protezione)<br />
- Account di monitoraggio della protezione designato per il monitoraggio mediante MOM (o similare).</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>- Registro gestione modifica e rilascio<br />
- Impostazioni di controllo eseguite attualmente durante la generazione.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Console avvisi operativi (quale MOM)<br />
- Visualizzatore eventi<br />
- Eventquery.vbs (strumento della riga di comando di Windows)</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Nella tabella seguente sono elencati gli eventi di controllo prodotti di Servizi certificati insieme alla categoria di avviso consigliata. Configurare il sistema di monitoraggio per la ricerca di questi eventi e specificare il livello di avviso appropriato. In alternativa, se non si dispone di un sistema di monitoraggio eventi centralizzato, esaminare i registri di protezione del server CA regolarmente (possibilmente giornalmente) per controllare questi elementi.

La categoria di avviso predefinita per gli eventi riusciti è Informativo. Qualsiasi evento di operazione riuscita risultante da possibili modifiche apportate alla configurazione della protezione della CA viene trattato come Avviso. Tutti gli eventi a livello di Avviso indicano eventi significativi normalmente non previsti nelle operazioni quotidiane. Tutti gli eventi di avviso devono essere correlati ad una richiesta di modifica approvata. Se tale correlazione non è presente, trattare l'evento come possibile violazione di protezione e controllarlo immediatamente.

Gli eventi di operazioni non riuscite non sono normalmente previsti durante le operazioni quotidiane o durante le modifiche standard alla CA. Quasi tutti questi eventi sono significativi e devono essere controllati (sebbene ciò potrebbe indicare solo un'assegnazione di autorizzazione non corretta piuttosto che un attacco intenzionale).

**Nota:** vi sono alcune eccezioni, ad esempio l'Evento 792 in cui Servizi certificati ha negato la richiesta di certificato. Ciò produce sia l'evento Operazione riuscita che Operazione non riuscita per una richiesta che è stata legittimamente negata dal gestore dei certificati. L'evento Operazione non riuscita viene generato solo quando la negazione di una richiesta è richiesta da un utente che non dispone dell'autorizzazione necessaria.

Un'ulteriore serie di eccezioni al seguente elenco è correlato alle diverse modalità con le quali vengono apportate le modifiche di configurazione alla CA. Gli eventi 789 (modifica del filtro di controllo) e 795 e 796 (modifica delle proprietà o della configurazione della CA) non registrano un errore di controllo se qualcuno tenta si modificare direttamente il registro CA oppure utilizza il comando **certutil -setreg** per modificare i valori di configurazione della CA. Questi vengono registrati come semplici errori di controllo di accesso oggetto, Evento560 (vedere l'ultima voce della tabella seguente). Il controllo è abilitato per le sottochiavi di configurazione del registro CA e registra le modifiche riuscite e tutti gli accessi non riusciti. Utilizzare il parametro **Nome oggetto** insieme a ID evento e Tipo evento come filtro per produrre gli avvisi corretti.

Naturalmente, monitorare e generare avvisi su eventi standard di protezione del sistema operativo. Il database ed il registro CA e le directory dei registri sono state configurati per generare avvisi per tutti gli accessi non riusciti e per tutte le modifiche riuscite. Considerare inoltre il controllo delle impostazioni sul contenitore di servizi a chiave pubblica (in Configurazione\\Servizi) e sui gruppi di amministrazione. Tali controlli non sono inseriti in questa soluzione a causa delle difficoltà di monitoraggio degli eventi di controllo distribuiti sui controller di dominio. Se si dispone di una strumento (quale MOM) per il consolidamento ed il filtraggio di questi registri, abilitare il controllo su tutti i contenitori e gli oggetti della configurazione e dell'amministrazione dell'infrastruttura PKI.

**Nota:** il monitoraggio della protezione del sistema operativo della CA esula dagli argomenti trattati in questo documento e può includere la gestione degli eventi di protezione da parte di agenti specializzati nel rilevamento di intrusioni. Nel caso si verifichi una condizione che indichi la violazione della protezione, controllare interamente gli eventi di controllo dell'autorità di certificazione insieme all'output derivante da tali condizioni.

**Tabella 14. Eventi di controllo Servizi certificati**

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
<th><p>Categoria avviso Operazione riuscita</p></th>
<th><p>Categoria avviso Operazione non riuscita</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>772</p></td>
<td style="border:1px solid black;"><p>Il gestore dei certificati ha negato una richiesta di certificati in sospeso.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>773</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha ricevuto una richiesta di certificati nuovamente inoltrata.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>774</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha revocato un certificato.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>775</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha ricevuto una richiesta di pubblicazione dell'elenco di revoche di certificati (CRL).</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>776</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha pubblicato l'elenco di revoche di certificati (CRL).</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>777</p></td>
<td style="border:1px solid black;"><p>L'estensione di una richiesta di certificati è stata modificata.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>778</p></td>
<td style="border:1px solid black;"><p>Uno o più attributi di richieste di certificati sono stati modificati.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>779</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha ricevuto una richiesta di arresto.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>780</p></td>
<td style="border:1px solid black;"><p>È stato avviato il backup di Servizi certificati.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>-</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>781</p></td>
<td style="border:1px solid black;"><p>È stato completato il backup di Servizi certificati.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>-</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>782</p></td>
<td style="border:1px solid black;"><p>È stato avviato il ripristino di Servizi certificati.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>-</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>783</p></td>
<td style="border:1px solid black;"><p>È stato completato il ripristino di Servizi certificati.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>-</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>784</p></td>
<td style="border:1px solid black;"><p>Servizi certificati avviato.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>-</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>785</p></td>
<td style="border:1px solid black;"><p>Servizi certificati arrestato.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>-</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>786</p></td>
<td style="border:1px solid black;"><p>Le autorizzazioni di protezione di Servizi certificati sono state modificate.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>787</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha recuperato una chiave archiviata.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>788</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha importato un certificato nel proprio database.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>789</p></td>
<td style="border:1px solid black;"><p>Il filtro di controllo per Servizi certificati è stato modificato.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>790</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha ricevuto una richiesta di certificato.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>791</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha approvato una richiesta di certificato e ha rilasciato un certificato.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>792</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha negato una richiesta di certificato.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>793</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha negato una richiesta di certificato.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>794</p></td>
<td style="border:1px solid black;"><p>Le impostazioni del gestore certificati per Servizi certificati sono state modificate.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>795</p></td>
<td style="border:1px solid black;"><p>Una voce della configurazione in Servizi certificati è stata modificata.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Nodo:<br />
Voce: CRLPeriod o CRLPeriodUnits o CRLDeltaPeriod o CRLDeltaPeriodUnits<br />  
Descrive le modifiche nella pianificazione della pubblicazione del CRL.<br />
Il valore 0 per CRLDeltaPeriodUnits significa che la pubblicazione di Delta CRL è disattivata.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Nodo:<br />
PolicyModules\CertificateAuthority_MicrosoftDefault.Policy<br />  
Voce: RequestDisposition<br />  
Valore: 1<br />
Imposta la CA per l'emissione di richieste in ingresso, se non diversamente specificato.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Nodo:<br />
PolicyModules\CertificateAuthority_MicrosoftDefault.Policy<br />  
Voce: RequestDisposition<br />  
Valore: 257<br />
Imposta la CA in modo che mantenga le richieste in ingresso in sospeso.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Nodo:<br />
ExitModules\CertificateAuthority_MicrosoftDefault.Exit<br />  
Voce: PublishCertFlags<br />  
Valore: 1<br />
Consente ai certificati di essere pubblicati nel file system.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Nodo:<br />
ExitModules\CertificateAuthority_MicrosoftDefault.Exit<br />  
Voce: PublishCertFlags<br />  
Valore: 0<br />
Non consente ai certificati di essere pubblicati nel file system.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Nodo: Nodo:<br />
Voce: Active<br />
Passa a modulo uscita attivo. Valore specifica il nome del nuovo modulo. Se vuoto significa nessuno.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Nodo: PolicyModules<br />
Voce: Active<br />
Passa a modulo criterio attivo. Valore specifica il nome del nuovo modulo.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Nodo:<br />
Voce: CRLPublicationURLs<br />
Passa a CDP o AIA. Valore specifica il gruppo di CDP risultanti</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Nodo:<br />
Voce: CACertPublicationURLs<br />
Passa a AIA o CDP. Valore specifica il gruppo di AIA risultanti.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>796</p></td>
<td style="border:1px solid black;"><p>Una proprietà di Servizi certificati è stata modificata (vedere i sottotipi riportati di seguito).</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Tipo: 4<br />
Aggiunta/rimozione di un modello a/da CA. Valore è l'elenco dei modelli risultanti ordinato per nome e OID.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Tipo: 3<br />
Aggiunta di certificati KRA a CA. Valore è la rappresentazione Base64 del certificato.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Tipo: 1<br />
Rimozione certificato KRA da CA. Valore è il conteggio totale dei certificati KRA.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Tipo: 1<br />
Aggiunta/rimozione numero di certificati KRA da utilizzare per l'archiviazione delle chiavi. Valore è il numero risultante di certificati da utilizzare.</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>797</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha archiviato una chiave.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>-</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>798</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha importato e archiviato una chiave.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>-</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>799</p></td>
<td style="border:1px solid black;"><p>Servizi certificati ha pubblicato il certificato della CA in Active Directory.</p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>800</p></td>
<td style="border:1px solid black;"><p>Una o più righe sono state eliminate dal database dei certificati.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>801</p></td>
<td style="border:1px solid black;"><p>Separazione ruoli abilitata.</p></td>
<td style="border:1px solid black;"><p>Avviso</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>560</p></td>
<td style="border:1px solid black;"><p>Accesso oggetto<br />
Dove:<br />  
Tipo oggetto: <strong>Key</strong><br />
Nome oggetto: <strong>\REGISTRY\MACHINE\SYSTEM\ ControlSet001\Services\CertSvc\Configuration</strong></p></td>
<td style="border:1px solid black;"><p>Informazioni</p></td>
<td style="border:1px solid black;"><p>Errore</p></td>
</tr>  
</tbody>  
</table>
  
##### Impostazione degli avvisi SMTP per le richieste di certificati in sospeso
  
Se si dispone di alcuni tipi di certificato configurati per richiedere l'approvazione del gestore dei certificati, tali certificati rimangono in coda nella cartella **Richieste in sospeso** fino a quando la richiesta non viene approvata. È possibile configurare l'invio di avvisi di posta elettronica ogni volta che una richiesta viene messa in coda. Le richieste approvate automaticamente non inviano avvisi di posta elettronica.
  
Gli avvisi di posta elettronica possono essere configurati anche per altri eventi CA. Per la configurazione, consultare la guida in linea di Servizi certificati.

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
<td style="border:1px solid black;"><p>CA Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Le attività alle quali fanno riferimento sono definite nella tabella precedente.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Editor di testo<br />
- Server SMTP e cassetta postale del destinatario</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Il server SMTP e l'elenco dei destinatari configurati nel file sono condivisi anche dal sevizio di avvisi SMTP descritto nella procedura "[Monitoraggio integrità e disponibilità Servizi certificati](#a11)". Se è necessario utilizzare valori diversi per questa procedura, è possibile modificare temporaneamente i valori nel file constants.vbs. Quindi, eseguire questa procedura e poi ripristinare i valori utilizzati in precedenza. L'impostazione per l'attivazione degli avvisi di posta elettronica in quella procedura (**ALERT\_EMAIL\_ENABLED**) non ha alcun effetto sugli avvisi di questa procedura.

-   **Per attivare gli avvisi di posta elettronica per le richieste in sospeso**

    1.  Accertarsi che nel file di script C:\\MSSScripts\\constants.vbs siano stati configurati i valori corretti per i destinatari della posta elettronica ed il server SMTP:
        ```

        **Nota:** le righe rientrate mostrate nel file sono continuazioni della riga precedente che continua alla riga successiva per questioni di leggibilità — nel file devono essere su una singola riga.

    2.  Eseguire il comando seguente per attivare gli avvisi di posta elettronica relativi alle richieste in sospeso in coda:
        ```

#### Pianificazione dei processi

La pianificazione dei processi include la continua organizzazione dei processi nella sequenza più efficiente, aumentando la velocità di trasmissione dati e l'utilizzo del sistema per soddisfare i requisiti SLA (Service Level Agreement). La pianificazione dei processi è strettamente legata al controllo e monitoraggio del servizio e alla gestione della capacità.

##### Pianificazione dei processi sulla CA di emissione

Un certo numero di attività ripetitive deve essere eseguita sulle CA per mantenere l'esecuzione continua dell'infrastruttura di Servizi certificati. Tali attività sono automatiche in modo da ridurre il carico operativo.

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
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Le attività alle quali fanno riferimento sono definite nella tabella precedente.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Utilità di pianificazione di Windows<br />
- MOM (se appropriato)</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Nella tabella seguente sono elencate le attività automatizzate che vengono eseguite CA di emissione.

Solo sulla CA di emissione possono essere eseguire attività automatiche. La CA principale potrebbe essere disattivata per periodi lunghi, di conseguenza non è possibile mantenere sul computer una pianificazione attendibile.

**Tabella 15. Elenco di processi pianificati sulla CA di emissione**

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
<th><p>Descrizione processo</p></th>
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
<td style="border:1px solid black;"><p>Utilità di pianificazione backup aziendale</p></td>
<td style="border:1px solid black;"><p>Nessuna (definita dall'organizzazione)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Pubblicazione di CRL su IIS</p></td>
<td style="border:1px solid black;"><p>Oraria</p></td>
<td style="border:1px solid black;"><p>Utilità di pianificazione di Windows</p></td>
<td style="border:1px solid black;"><p>Pubblicazione certificati e CA di emissione su IIS</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Controllo dell'integrità della CA in linea</p></td>
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
  
Vi sono altre attività operative relative alla manutenzione di un'infrastruttura PKI che generalmente non sono necessarie ma che potrebbero servire occasionalmente oppure riguardano problemi di supporto.
  
La documentazione di Servizi certificati di Windows Server 2003 descrive alcune di queste attività e fornisce informazioni relative all'amministrazione che non vengono trattate né in questo documento né nella *Guida all'implementazione* (modulo "Implementazione di un'infrastruttura a chiave pubblica") o informazioni supplementari utili.
  
Vedere la sezione "[Ulteriori informazioni](#xsltsection133121120120)" alla fine di questo modulo per il collegamento a questo documento nel quale è possibile trovare istruzioni sull'esecuzione delle seguenti attività amministrative:
  
-   Avvio o arresto del servizio Autorità di certificazione.
  
-   Impostazione delle autorizzazioni di protezione e delega del controllo di un'autorità di certificazione.
  
-   Visualizzazione del certificato dell'autorità di certificazione.
  
-   Impostazione della protezione per l'accesso alle pagine Web dell'autorità di certificazione.
  
-   Configurazione delle restrizioni del gestore dei certificati.
  
-   Pubblicazione dei certificati in un insieme di strutture Active Directory esterno
  
-   Invio di posta elettronica quando si verifica un evento di certificato.
  
-   Utilizzo dello snap-in Autorità di certificazione.
  
-   Gestione revoca del certificato.
  
-   Gestione delle richieste di certificati su un'autorità di certificazione autonoma.
  
-   Gestione dei modelli di certificato per un'autorità di certificazione di un'organizzazione di grandi dimensioni.
  
-   Gestione dell'archiviazione e del ripristino delle chiavi.
  
-   Modifica delle impostazioni dei criteri per un'autorità di certificazione.
  
-   Modifica dei moduli dei criteri o di uscita di un'autorità di certificazione.
  
-   Gestione dell'amministrazione basata sui ruoli.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di supporto
  
Le funzioni SMF di questa fase supportano questo obiettivo assicurando l'utilizzo di funzionalità reattive e preventive nella gestione dei livelli di servizio. Le funzioni reattive dipendono dalla capacità dell'organizzazione di reagire e risolvere rapidamente le emergenze e i problemi. Le funzioni preventive tentano di evitare eventuali interruzioni del servizio identificando e risolvendo i problemi prima che influiscano su qualsiasi livello del servizio. Tale obiettivo viene raggiunto attraverso un buon monitoraggio della soluzione di servizi, a fronte di soglie predefinite e dando al personale operativo il tempo di reagire a eventuali problemi prima che si manifestino con interruzioni dei servizi.
  
Questa sezione contiene informazioni relative alle seguenti funzioni di gestione del servizio:
  
-   Gestione delle emergenze
  
Non esistono attività per le restanti funzioni di gestione dei servizi:
  
-   Gestione dei problemi
  
-   Servizio di assistenza
  
#### Gestione delle emergenze
  
La gestione delle emergenze è il processo che consente di gestire e controllare errori e interruzioni nell'utilizzo o nell'implementazione dei servizi IT riferiti dai clienti o dai partner IT. L'obiettivo principale della gestione delle emergenze è ripristinare il normale funzionamento del servizio nel modo più rapido possibile e ridurre al minimo le ripercussioni negative sull'attività aziendale, assicurando il mantenimento della migliore qualità e disponibilità dei livelli di servizio. Con l'espressione normale funzionamento del servizio si intende un funzionamento entro i limiti del contratto del livello di servizio (SLA, Service Level Agreement).
  
Questa sezione è strettamente correlata alla sezione "[Risoluzione dei problemi](#xsltsection131121120120)". Mentre la sezione "Risoluzione dei problemi" tratta l'identificazione e la diagnosi dei problemi, questa sezione contiene le attività più comuni utilizzate per risolvere tali problemi.
  
Le emergenze trattate nella sezione "Risoluzione dei problemi" sono:
  
-   Server non risponde
  
-   Pubblicazione CRL non riuscita
  
-   CRL non emesso
  
-   Il client non può registrare
  
-   Patch installata richiede riavvio
  
-   Errore server permanente
  
-   Certificato orfano deve essere revocato
  
-   Il server non può essere ripristinato in tempo per l'emissione del certificato o del CRL
  
-   Il certificato dell'entità finale è compromesso
  
-   Il certificato della CA di emissione è compromesso
  
-   Il certificato della CA principale è compromesso
  
La maggior parte di questi problemi sono correlati direttamente ad una o più delle procedure riportate in dettaglio nelle sezioni seguenti. In altri casi, ad esempio in caso di errore di registrazione del client, il processo di risposta al problema richiesto è più complesso. Queste risposte ai problemi sono trattate nella sezione "Risoluzione dei problemi".
  
##### Riavvio di Servizi certificati
  
È necessario riavviare Servizi certificati per molti motivi operativi. Ad esempio, dopo la riconfigurazione di molte proprietà della CA è necessario riavviare Servizi certificati per rendere effettive le modifiche. In alcuni casi, potrebbe essere necessario riavviare Servizi certificati se il servizio non risponde oppure funziona in modo non previsto.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Supporto</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Console di gestione Autorità di certificazione<br />
- Net.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Vi sono molti metodi per riavviare il servizio, tutti accettabili per questa attività.

-   **Per riavviare il servizio CA**

    1.  Verificare che nessun utente sia attualmente coinvolto in alcuna transazione con la CA. Inviare un avviso agli utenti che potrebbero esser coinvolti, se il tempo lo consente.

    2.  Nella console MMC Autorità di certificazione, selezionare l'oggetto **CA**.

    3.  Nel menu **Attività** fare clic su **Arresta servizio** oppure da una finestra di comando digitare:
        ```

    4.  Nel menu **Attività** fare clic su **Avvia servizio** oppure da una finestra di comando digitare:
        ```

**Nota:** con il controllo abilitato, Servizi certificati potrebbe impiegare molto tempo per la chiusura ed il riavvio — questa operazione potrebbe richiedere oltre 10 minuti nel caso di database grandi. Questa operazione estende il processo di chiusura e avvio dell'intero server. Questo ritardo è dovuto al fatto che Servizi certificati calcola l'hashing dell'intero database per creare le voci di controllo dell'avvio e dell'arresto del sistema; questo ritardo non si verifica se le procedure di avvio e chiusura non vengono controllate.

##### Riavvio del server CA

È possibile dover riavviare il server CA per molti motivi operativi, principalmente per includere le patch del sistema operativo e se il servizio non risponde o se funziona in modo non previsto e non si riavvia normalmente mediante la procedura di riavvio del servizio.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Supporto</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Net.exe</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
-   **Per riavviare il servizio CA**
  
    1.  Verificare che nessun utente sia attualmente coinvolto in alcuna transazione con la CA. Inviare un avviso agli utenti che potrebbero esser coinvolti, se il tempo lo consente.
  
    2.  Se possibile, eseguire il comando seguente per arrestare Servizi certificati in modo da impedire agli utenti di collegarsi alla CA:
  
        <codesnippet language displaylanguage containsmarkup="false"> net stop "Servizi certificati"  
```
  
    3.  Seguire le normali procedure del sistema operativo per riavviare il computer. A meno che non sia chiaro che il processo Servizi certificati non risponde, non tentare di arrestare il processo o disattivare il server. L'interruzione del processo Servizi certificati potrebbe danneggiare il database di Servizi certificati e richiedere un ripristino dal backup.
  
**Nota:** con il controllo abilitato, Servizi certificati potrebbe impiegare molto tempo per la chiusura ed il riavvio — questa operazione potrebbe richiedere oltre 10 minuti nel caso di database grandi. Questa operazione estende il processo di chiusura e avvio dell'intero server. Questo ritardo è dovuto al fatto che Servizi certificati calcola l'hashing dell'intero database per creare le voci di controllo dell'avvio e dell'arresto del sistema; questo ritardo non si verifica se le procedure di avvio e chiusura non vengono controllate.
  
##### Ripristino della CA da un backup
  
Se non è possibile avviare una CA a causa di un grave danno software o hardware, è necessario ripristinare il server e i dati delle chiavi dal backup.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>- Amministratori locali sulla CA<br />
- CA Backup Operators (solo per eseguire il ripristino)</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>- Il processo di backup è stato precedentemente configurato ed eseguito correttamente.<br />
- Il supporto di backup è disponibile</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Backup di Windows<br />
- Sistema di backup aziendale</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Eseguire le operazioni seguenti per ripristinare una CA dal backup.

**Avviso:** se si utilizza un HSM, questa procedura non funziona come indicato. Per eseguire il backup, il ripristino e le procedure di protezione dei dati delle chiavi e delle chiavi di accesso, seguire le istruzioni del fornitore.

-   **Per ripristinare una CA dal backup**

    1.  Il sistema operativo deve essere ripristinato fino al punto in cui risultava affidabile per eseguire nuovamente Servizi certificati. Ciò potrebbe significare reinstallare Windows. Se necessario, seguire le istruzioni nella *Guida all'implementazione* per installare il sistema operativo ed i componenti del sistema di base. Non è necessario applicare alcuna misura di protezione o altre misure di configurazione.

        **Avviso:** se è necessario reinstallare Windows, non creare nuove partizioni e riformattare la seconda unità (applicabile solo per la CA di emissione). Questa unità contiene il database della CA, che potrebbe essere intatto.

    2.  Se possibile, conservare il database della CA (in *%systemroot%\\System32\\CertLog* sulla CA principale oppure in D:\\CertLog sulla CA di emissione) ed i registri della CA (in *%systemroot%\\System32\\CertLog*). Prima di ripristinare la CA, eseguire il backup del file di queste cartelle. Il database ed i registri potrebbero non essere stati influenzati dal malfunzionamento del sistema. I registri contengono le informazioni necessarie per eseguire nuovamente tutte le transazioni sulla CA che sono state eseguite tra l'ultimo backup ed il malfunzionamento del server. Il ripristino del backup dello stato del sistema sovrascrive il database ed i registri esistenti, quindi conservarli prima di iniziare il ripristino del sistema.

    3.  Inserire il supporto di backup contenente il backup più recente della CA e ripristinare il file di backup dello stato del sistema in un'area del disco idonea (è consigliabile utilizzare la seconda unità, se disponibile).

    4.  Avviare il programma di backup di Windows. Nella scheda **Ripristina**, fare clic con il pulsante destro del mouse su **File** nel riquadro di sinistra, quindi fare clic su **Cataloga file**.

    5.  Accertarsi che l'opzione **Percorso originale** sia selezionata come destinazione di ripristino dei file, quindi fare clic su **Avvia ripristino** per ripristinare lo stato del sistema.

    6.  Se i registri della CA sono stati conservati (passaggio 2), a questo punto verranno eseguiti di nuovo in relazione al database ripristinato per inserire le eventuali transazioni eseguite dopo l'ultimo backup.

        **Nota:** se il database della CA era intatto, è possibile ripristinarlo di nuovo nel sistema (prima arrestare Servizi certificati) se l'esecuzione delle operazioni del passaggio 7 non ripristina tutti i dati previsti.

    7.  Avviare **Servizi certificati**.

##### Ripristino del certificato CA e della coppia di chiavi su un computer temporaneo

Se una CA che non funziona non può essere ripristinata in tempo affinché la CA emetta un nuovo CRL (o certificato critico), è necessario installare il certificato CA e le chiavi su un computer temporaneo in modo da poter utilizzare le chiavi CA per estendere il periodo di validità del certificato o del CRL esistente.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratori locali su un computer temporaneo</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Backup precedente delle chiavi CA</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Certutil.exe<br />
- Cipher.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Questa attività descrive come ripristinare il certificato CA e la chiave privata su un computer temporaneo.

**Importante:** se su questo computer è installata la chiave CA, adottare sempre le stesse precauzioni di protezione come se si trattasse della CA. Se si sta ripristinando la chiave di una CA non in linea, accertarsi che il computer non sia in linea. Una volta terminate le operazioni con la chiave, prendere in considerazione la riformattazione dei dischi del computer.

**Avviso:** se si utilizza un HSM, questa procedura non funziona come indicato. Per eseguire il backup, il ripristino e le procedure di protezione dei dati delle chiavi e delle chiavi di accesso, seguire le istruzioni del fornitore.

-   **Per ripristinare il certificato e la chiave CA su un computer temporaneo**

    1.  Verificare che il computer sia stato disconnesso dalla rete e che sia collegato come membro del gruppo Administrators locale, quindi creare l'account utente — **CAKeySigner**.

    2.  Accedere utilizzando questo account.

    3.  Inserire un disco contenente il backup delle chiavi CA da testare.

    4.  Utilizzare Esplora risorse per selezionare i file delle chiavi P12 e fare doppio clic su **Importazione guidata**.

    5.  Quando richiesto, immettere la password e non selezionare le caselle di controllo per fornire alta protezione alle chiavi o per renderle esportabili.

    6.  Selezionare **Archivio personale** come posizione nella quale ripristinare le chiavi CA.

    7.  Aprire la console di gestione dei certificati e scegliere l'archivio personale. Individuare il certificato CA per la CA ripristinata, quindi aprire il certificato per verificare di disporre della chiave privata corrispondente.

A questo punto, è possibile eseguire qualsiasi attività di nuova firma richiesta con le chiavi CA ripristinate. Una volta completata l'operazione, eliminare le chiavi dal computer utilizzando la procedura seguente.

-   **Per eliminare le chiavi dal sistema**

    1.  Accedere come membro del gruppo Administrators locale ed eliminare il profilo utente dell'account **CAKeySigner** (utilizzando **Proprietà avanzate** in Computer locale).

    2.  Eliminare l'account **CAKeySigner**.

    3.  Cancellare le aree non allocate del disco per rimuovere in modo permanente le tracce delle chiavi eseguendo il comando seguente:
        ```

**Nota:** specificando *%allusersprofile%* come percorso si garantisce che Cipher.exe operi sull'unità contenente i profili utente. L'esecuzione di questo comando elimina il contenuto dell'intera unità, non solo il percorso specificato.

##### Nuova firma di un certificato o di un CRL per estenderne la validità

Se una CA non è disponibile a causa di un errore del server, è possibile estendere la durata degli elenchi CRL o dei certificati firmando nuovamente il file del certificato o il CRL. Questa operazione può essere fondamentale per mantenere il servizio.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Account temporaneo creato durante il ripristino della chiave CA.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>La chiave CA è disponibile (vedere l'attività &quot;Ripristino del certificato CA e della coppia di chiavi su un computer temporaneo&quot;)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Certutil.exe</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
La nuova firma di un certificato o di un CRL ne estende il periodo di validità. Per impostazione predefinita, viene utilizzato il periodo di validità esistente che viene quindi specificato a partire dalla data della nuova firma (ad esempio, se il periodo di validità del CRL era di un mese, il nuovo periodo di validità sarà di un mese a partire dalla data di apposizione della nuova firma). Se è richiesto un periodo di validità diverso, deve essere specificato nella riga di comando certutil.
  
-   **Per firmare nuovamente un CRL o un certificato**
  
    1.  Ottenere una copia del CRL o del certificato che deve essere firmato di nuovo.
  
    2.  Accedere ad un computer sul quale è stata precedentemente ripristinata una copia della chiave CA e del certificato utilizzati per firmare originariamente il certificato o il CRL (vedere la procedura precedente "Ripristino del certificato CA e della coppia di chiavi su un computer temporaneo"). Accedere utilizzando l'account creato in quella procedura.
  
    3.  Eseguire il comando seguente, sostituendo *OldFile.ext* con il nome del file del CRL o del certificato e *NewFile.ext* con il nome di output richiesto.
  
        <codesnippet language displaylanguage containsmarkup="false"> Certutil -sign OldFile.ext NewFile.ext  
```
  
    4.  Quando viene richiesto il certificato da utilizzare, selezionare il certificato CA.
  
    5.  Nel caso di un CRL, questo adesso dovrebbe essere pubblicato su CDP come richiesto (vedere le procedure per la pubblicazione dei CRL nella sezione delle procedure operative).
  
##### Revoca del certificato di un'entità finale
  
Un certificato può essere revocato per diversi motivi, quali:
  
-   Le funzionalità o i privilegi associati al certificato sono stati revocati dal possessore del certificato.
  
-   La chiave del certificato è stata compromessa.
  
-   La CA che ha emesso il certificato è stata compromessa.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Certificate Managers</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Autorità di certificazione</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Questa procedura descrive le operazioni di revoca del certificato di un'entità finale (ad esempio, un certificato emesso per un'entità diversa da una CA). Seguire le procedure descritte per la revoca di un certificato CA.
  
-   **Per revocare un certificato**
  
    1.  Accedere come membro del gruppo **Certificate Managers** ed individuare il certificato da revocare nel database dell'autorità di certificazione (nella console MMC Autorità di certificazione). Utilizzare l'opzione **Filtro** nel menu **Visualizza** della cartella **Certificati emessi** per individuare il certificato.
  
    2.  Selezionare il certificato, quindi nel menu **Attività** fare clic su **Revoca**.
  
    3.  Selezionare un codice motivo appropriato per la revoca. Se il motivo della revoca non è compreso tra i codici motivo predefiniti, selezionare **Non specificato**.
  
        **Importante:** solo il codice motivo **Sospensione certificato** consente di ripristinare il certificato in seguito. Tutti gli altri codici motivo disattivano in modo permanente il certificato. Tuttavia, non utilizzare il codice motivo **Sospensione certificato** solo perché consente il ripristino del certificato in un secondo momento. Utilizzare questo codice solo quando è effettivamente necessaria la sospensione temporanea del certificato.
  
##### Revoca di un certificato orfano
  
Quando si ripristina una CA da un backup a seguito di un errore del server, i certificati emessi tra l'ultimo backup e la condizione di errore potrebbero non essere nel database dei certificati. Questi certificati vengono definiti orfani. Un caso di certificato orfano potrebbe verificarsi se i registri della CA sono stati distrutti e, dopo il ripristino del backup, non sono stati eseguiti nuovamente in relazione al database CA. Se si verifica questa condizione, mediante la normale procedura non è possibile revocare nessuno di questi certificato orfani.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Certificate Managers</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Certutil.exe</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Per revocare un certificato orfano, è necessario ottenere una copia del certificato da revocare o il numero di serie di tale certificato.
  
-   **Per revocare un certificato orfano**
  
    1.  Accedere alla CA che ha emesso il certificato da revocare come membro del gruppo **Certifcate Managers**.
  
    2.  Se non è possibile ottenere una copia del certificato, eseguire il comando seguente per creare un certificato fittizio e salvarlo come CertToRevoke.cer. Sostituire *SerialNumber* con il numero di serie del certificato da revocare.
  
        <codesnippet language displaylanguage containsmarkup="false"> Certutil -sign SerialNumber CertToRevoke.cer  
```
  
    3.  Quando richiesto, selezionare il certificato CA corrente per firmare il certificato fittizio.
  
    4.  Eseguire il comando seguente per importare il certificato nel database dei certificati. **CertToRevoke** è sia una copia del certificato effettivo da revocare che il certificato fittizio creato nei passi precedenti.
  
        <codesnippet language displaylanguage containsmarkup="false"> Certutil -importcert CertToRevoke.cer  
```
  
    5.  Seguire la procedura standard per revocare un certificato.
  
**Importante:** è presente un problema con certutil che genera un errore di creazione del certificato fittizio su Windows Server 2003. Prima che questa funzionalità venisse corretta, questa procedura è stata lasciata nel modulo. Nel frattempo, un approccio alternativo consiste nel prendere un certificato esistente e con un editor binario si sostituisce il numero di serie con il numero di serie del certificato da revocare. Questo certificato modificato può essere firmato nuovamente utilizzando la sintassi:
  
<codesnippet language displaylanguage containsmarkup="false"> Certutil -sign ModifiedCert.cer CertToRevoke.cer  
```  
Il certificato appena creato può essere importato nel database seguendo il passaggio 4.
  
##### Revoca e sostituzione di un certificato della CA di emissione
  
Se la chiave privata di una CA risulta compromessa (o se si pensa che lo sia), revocare il certificato CA ed emetterne uno nuovo utilizzando una nuova coppia di chiavi.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Certificate Managers</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Attività di riferimento</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Autorità di certificazione</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Poiché il tempo di pubblicazione del CRL di un'autorità di certificazione è molto lungo, revocando semplicemente il certificato CA e pubblicando un nuovo CRL trascorrerà molto tempo tra la revoca e la ricezione della notifica di tale revoca. Per garantire che tutti i certificati emessi dalla CA compromessa vengano rifiutati il prima possibile, anche tutti i certificati emessi da questa CA vengono revocati singolarmente.
  
**Importante:** tutti gli utenti di certificati devono registrare nuovamente i nuovi certificati.
  
-   **Per revocare un certificato della CA di emissione**
  
    1.  Accedere alla CA di emissione come membro del gruppo Certifcate Managers ed aprire la console MMC Autorità di certificazione.
  
    2.  Selezionare tutti i certificati nella cartella **Certificati emessi**, quindi nel menu **Tutte le attività** fare clic su **Revoca certificato**. Selezionare **Compromesso CA** per il codice motivo.
  
    3.  Aumentare il valore di **Intervallo pubblicazione CRL** per far corrispondere la durata rimanente del certificato CA. In questo modo si garantisce che la sua durata sarà maggiore di quella rimanente di tutti i certificati emessi dalla CA.
  
    4.  Deselezionare la casella di controllo **Pubblica Delta CRL**, se selezionata.
  
    5.  Nel menu **Tutte le attività** della cartella Certificati revocati fare clic su **Pubblica**, quindi fare clic su **Nuovo CRL**.
  
    6.  Accedere alla CA principale come membro del gruppo Certifcate Manager ed aprire la console MMC Autorità di certificazione.
  
    7.  Individuare il certificato CA da revocare nella cartella **Certificati emessi**, quindi nel menu **Tutte le attività** fare clic su clic su **Revoca certificato**. Selezionare **Compromesso chiave** per il codice motivo.
  
    8.  Seguire la procedura di operazioni di "Pubblicazione elenco CRL non in linea e certificato CA" (è possibile ignorare le parti della procedura relative alla pubblicazione del certificato CA).
  
    9.  Tornare alla CA di emissione e seguire la procedura "Rinnovo certificato CA di emissione".
  
Gli utenti dei certificati adesso possono registrare di nuovo la nuova CA. I certificati a registrazione automatica devono essere registrati automaticamente.
  
##### Revoca e sostituzione di un certificato della CA principale
  
Se la chiave privata di una CA principale risulta compromessa (o se si pensa che lo sia), è necessario rimuovere il certificato CA e revocare tutti i certificati emessi da tale CA e dalle relative CA subordinate. È necessario rinnovare il certificato della CA principale ed i certificati di tutte le relative CA subordinate con le nuove chiavi, e quindi pubblicarli nuovamente in Active Directory. Generalmente, non è possibile revocare un certificato della CA principale. Spesso, come in questo caso, il certificato della CA non include un CDP dal quale controllare lo stato di revoca e, comunque, non è strettamente legale da parte di una CA attestare la propria revoca firmando il CRL con il proprio certificato.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>- Certificate Managers<br />
- Amministratori locali sulle CA (per attività secondarie di rinnovo CA)</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Autorità di certificazione</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
**Nota:** al termine di questa procedura, tutti gli utenti di certificati devono registrare nuovamente i nuovi certificati.
  
-   **Per revocare un certificato della CA di emissione**
  
    1.  Accedere alla CA di emissione come membro del gruppo Certifcate Managers ed aprire la console MMC Autorità di certificazione.
  
    2.  Selezionare tutti i certificati nella cartella **Certificati emessi**, quindi nel menu **Tutte le attività** fare clic su **Revoca certificato**. Selezionare **Compromesso CA** per il codice motivo.
  
    3.  Aumentare il valore di **Intervallo pubblicazione CRL**per far corrispondere la durata rimanente del certificato CA. In questo modo si garantisce che la sua durata sarà maggiore di quella rimanente di tutti i certificati emessi dalla CA.
  
    4.  Deselezionare la casella di controllo **Pubblica Delta CRL**, se selezionata.
  
    5.  Nel menu **Tutte le attività** della cartella **Certificati revocati** fare clic su **Pubblica** , quindi fare clic su **Nuovo CRL**.
  
    6.  Accedere alla CA principale come membro del gruppo Certifcate Manager ed aprire la console MMC Autorità di certificazione.
  
    7.  Selezionare tutti i certificati nella cartella **Certificati emessi**, quindi nel menu **Tutte le attività** fare clic su **Revoca certificato**. Selezionare **Compromesso CA** per il codice motivo.
  
    8.  Aumentare il valore di **Intervallo pubblicazione CRL**per far corrispondere la durata rimanente del certificato CA. In questo modo si garantisce che la sua durata sarà maggiore di quella rimanente di tutti i certificati emessi dalla CA.
  
    9.  Deselezionare la casella di controllo **Pubblica Delta CRL**, se selezionata.
  
    10. Seguire la procedura "Rinnovo certificato CA principale".
  
    11. Tornare alla CA di emissione e seguire la procedura "Rinnovo certificato CA di emissione".
  
Gli utenti dei certificati adesso possono registrare di nuovo la nuova CA. I certificati a registrazione automatica devono essere registrati automaticamente.
  
**Importante:** il rinnovo di un certificato della CA principale è un evento molto importante specialmente nel caso in cui coinvolga la revoca delle CA figlie e dei certificati emessi. Accertarsi che tutti i proprietari dell'applicazione interessati vengano informati sul nuovo certificato principale nel caso in cui debbano configurare questo nuovo certificato principale nella loro applicazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di ottimizzazione
  
Nella fase di ottimizzazione sono incluse le funzioni SMF con cui gestire i costi mantenendo o migliorando i livelli di servizio. Ciò include l'analisi delle interruzioni/emergenze, l'esame delle strutture di costo, le verifiche del personale e l'analisi delle prestazioni, così come le previsioni delle capacità.
  
In questa sezione vengono fornite le informazioni relative alle seguenti funzioni SMF:
  
-   Gestione capacità
  
Non esistono attività per le restanti funzioni di gestione dei servizi:
  
-   Gestione del livello del servizio
  
-   Gestione finanziaria
  
-   Gestione disponibilità
  
-   Gestione della continuità del servizio IT
  
-   Gestione forza lavoro
  
#### Gestione della capacità
  
La gestione della capacità è il processo di pianificazione, dimensionamento e controllo della capacità della soluzione di servizi in modo che soddisfi la richiesta degli utenti entro i livelli di prestazioni stabiliti nel contratto del livello di servizio. Il processo richiede informazioni relative agli scenari di utilizzo, agli schemi e alle caratteristiche di carico massimo della soluzione di servizi, nonché requisiti di prestazione definiti.
  
##### Definizione del carico massimo per l'autorità di certificazione emittente
  
In questa sezione vengono fornite alcune informazioni sul carico massimo per la CA di emissione.
  
Sebbene normalmente le CA non hanno un carico molto alto, potrebbero comunque verificarsi condizioni di carico improvviso. Il carico più alto su una CA avviene generalmente in fase di collegamento o avvio durante la generazione di un nuovo tipo di certificato. Allo stesso modo, sebbene più raro, se è avvenuta una revoca di massa di certificati o di certificati CA, la nuova registrazione di utenti e computer causa un carico massimo anomalo.

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
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Le procedure di test interne di Microsoft hanno mostrato che, per una CA tipica di un'organizzazione di grandi dimensioni, il collo di bottiglia delle prestazioni sotto alto carico è dovuto all'interazione con Active Directory. L'attività di firma ed emissione dei certificati è relativamente leggera rispetto al sovraccarico dell'esecuzione di una ricerca nelle directory per recuperare le informazioni del certificato e quindi della ripubblicazione del certificato su Active Directory.
  
Considerare uno scenario di carico massimo tipico in cui è stato attivato un nuovo tipo di certificato e tutti gli utenti e computer devono registrare i certificati:
  
-   Numero di utenti:3000
  
-   Numero di computer:3000
  
-   La velocità di emissione massima approssimativa di una CA di un'organizzazione di grandi dimensioni è di tre certificati al secondo (o 180 certificati al minuto).
  
##### Definizione dei requisiti di archiviazione e backup per un'autorità di certificazione emittente
  
Questa sezione fornisce i dettagli della capacità per i parametri di archiviazione della CA. Tali dettagli consentiranno ai pianificatori della capacità di calcolare i requisiti futuri per l'archiviazione di backup su disco e non in linea.

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
  
Le sezioni seguenti riportano i presupporti ed i risultati dei calcoli delle dimensioni relativamente a: dimensioni del database CA, dimensioni del registro del database CA, dimensioni del CRL e intervallo di backup richiesto (ad esempio, il tempo per il backup del database CA).
  
I calcoli seguenti si basano su questi presupposti:
  
-   3000 utenti, 3000 computer e 100-300 server.
  
-   Ogni entità finale viene emessa con cinque certificati per anno, ciascuno con un periodo di validità di un anno.
  
-   I certificati vengono mantenuti nel database per cinque anni.
  
-   Il backup del database viene eseguito quotidianamente (troncando i registri del database).
  
**Dimensione del database dei certificati**
  
Ciascuna voce del certificato occupa circa 20 KB nel database.
  
Questa condizione produce i seguenti risultati:
  
-   Nel database sono sempre presenti 150000 certificati archiviati.
  
-   La dimensione totale del database è di 3 GB.
  
**Dimensione media del registro del database dei certificati**
  
-   Sono presenti 750 certificati al giorno.
  
-   La dimensione media del registro è di 5 MB.
  
**Dimensione del CRL**
  
Una voce CRL è di circa 30 byte e, circa il dieci per cento dei certificati emessi viene revocato. I certificati revocati che non rientrano nel relativo periodo di validità non sono inclusi nel CRL.
  
-   In qualsiasi momento 30000 certificati rientrano attualmente nel periodo di validità.
  
-   3000 certificati saranno presenti nel CRL.
  
-   La dimensione del CRL è di 90 KB.
  
**Intervallo di backup per il database dei certificati**
  
Se si assume che un backup di rete in funzione in condizioni ideali su 100 Mbps (megabit al secondo) passi al server di backup, in circa 15-20 minuti può essere eseguito il backup di un database di 3 GB più lo stato del sistema di 500 MB.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Attività della fase di modifica
  
Nella fase di modifica sono inclusi i processi e le procedure necessari a identificare, analizzare, approvare e incorporare le modifiche in un ambiente IT gestito. Le modifiche includono le risorse hardware e software nonché le modifiche di processi e procedure specifici.
  
L'obiettivo del processo di modifica consiste nell'introdurre nuove tecnologie, sistemi, applicazioni, hardware, strumenti e processi e modifiche a ruoli e responsabilità nell'ambiente IT in tempi rapidi e con un'interruzione minima del servizio.
  
#### Gestione delle modifiche
  
La funzione SMF di gestione delle modifiche è responsabile della gestione delle modifiche in un ambiente IT. Obiettivo principale del processo di gestione delle modifiche è assicurare che tutte le parti interessate da una determinata modifica siano consapevoli dell'impatto dell'imminente modifica. Poiché la maggior parte dei sistemi è strettamente correlata, le modifiche apportate a una parte del sistema potrebbero avere ripercussioni su un'altra parte. Per ridurre o eliminare eventuali effetti negativi, il processo di gestione delle modifiche tenta di identificare tutti i sistemi ed i processi interessati prima di rendere effettive le modifiche. Generalmente, l'ambiente di destinazione è l'ambiente di produzione, ma potrebbe includere anche gli ambienti di integrazione delle chiavi, di test e di distribuzione.
  
Tutte le modifiche apportate all'infrastruttura PKI devono seguire il processo standard di gestione delle modifiche MOF mostrato di seguito:
  
1.  **Richiesta di modifica**. L'inizializzazione formale di una modifica mediante l'invio di una richiesta di modifica (RFC).
  
2.  **Classificazione della modifica**. L'assegnazione di una priorità e di una categoria alla modifica, considerando come criterio l'urgenza ed il relativo impatto sull'infrastruttura o sugli utenti. Tale assegnazione influisce sulla velocità e sul percorso dell'implementazione.
  
3.  **Autorizzazione della modifica**. La considerazione e approvazione o disapprovazione della modifica da parte del gestore delle modifiche e del consiglio di analisi delle modifiche costituito dai rappresentanti aziendali e IT.
  
4.  **Sviluppo della modifica**. La pianificazione e lo sviluppo della modifica, un processo che può variare molto a seconda degli obiettivi ed include le analisi degli obiettivi chiave.
  
5.  **Rilascio della modifica**. Il rilascio e la distribuzione della modifica nell'ambiente di produzione.
  
6.  **Analisi della modifica**. Un processo post implementazione che esamina se la modifica ha raggiunto l'obiettivo stabilito e determina se mantenerla o meno effettiva.
  
Le procedure di questa sezione illustrano come sviluppare alcune delle modifiche principali che probabilmente saranno necessarie regolarmente nell'ambiente in uso. Ciascuna procedura di sviluppo delle modifiche è affiancata da una procedura di rilascio in cui sono descritte le modalità di distribuzione della modifica nella produzione.
  
##### Gestione delle patch del sistema operativo
  
La gestione delle patch per Servizi certificati (Servizi certificati viene trattato dalla gestione generale delle patch di Windows) viene trattata in due guide operative Microsoft *Solutions for Management*. Per i collegamenti alla documentazione, vedere la sezione "Ulteriori informazioni" alla fine di questo modulo.
  
La gestione delle patch include componenti di gestione del rilascio e componenti di gestione della configurazione, nonché un componente di gestione delle modifiche. Tuttavia, tutti e tre gli SMF sono descritti nelle documentazioni citate in precedenza.

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
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Infrastruttura di distribuzione delle patch (quale SMS o SUS)</p></td>
</tr>  
</tbody>  
</table>
  
##### Aggiunta di un modello di certificato
  
Un nuovo modello di certificato viene aggiunto per consentire l'emissione di un nuovo tipo di certificato. Ciò potrebbe verificarsi in quanto una nuova applicazione sta per essere distribuita oppure un'applicazione esistente richiede nuove funzionalità. Questo può inoltre far parte di un processo di aggiornamento di un tipo di certificato esistente.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Processo di gestione delle modifiche definito e altre procedure<br />
- Rilascio di un nuovo modello di certificato<br />
- Rilascio di un nuovo CPS</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Modelli di certificato</p></td>
</tr>  
</tbody>  
</table>
  
Prima di inviare un richiesta di un nuovo tipo di certificato, testarlo in un ambiente di test che rappresenti l'ambiente di produzione.
  
Documentare la richiesta di un nuovo tipo di certificato e includere:
  
-   I motivi di generazione del nuovo modello
  
-   Una verifica dell'impatto sugli utenti e l'infrastruttura
  
-   Una verifica di eventuali impatti se la modifica non viene eseguita
  
-   I risultati del test della modifica
  
La documentazione deve includere gli aggiornamenti rilevanti ai criteri del certificato e le istruzioni CPS. Deve inoltre essere verificato in termini di priorità ed impatto. Una volta che la modifica è stata approvata può essere implementata (anche se non ancora rilasciata).
  
**Dettagli relativi all'attività**
  
La procedura seguente deve essere eseguita esclusivamente in un ambiente di test. Il processo per l'esecuzione di questa modifica nell'ambiente di produzione è descritta nella procedura "Rilascio di un nuovo modello di certificato".
  
-   **Per implementare un nuovo modello di certificato**
  
    1.  Accedere come membro del gruppo Enterprise PKI Admins ed aprire la console MMC Modelli di certificato.
  
    2.  Selezionare un modello appropriato sul quale basare il nuovo modello.
  
        **Importante:** accertarsi che il tipo di modello di base (utente o computer) del modello copiato corrisponda al tipo soggetto del nuovo modello; questo non può essere modificato con l'editor di modelli.
  
    3.  Modificare i dettagli del modello come richiesto. Per informazioni dettagliate, consultare la documentazione del prodotto nel sistema di guida locale oppure in linea all'indirizzo: <http://technet.microsoft.com/en-us/library/cc755996.aspx> (in inglese).
  
    4.  Se questo modello sostituisce un modello esistente, è necessario aggiungere i modelli sostitutivi all'elenco dei modelli sostituiti. È necessario accertarsi che il modello sostituivo fornisca le stesse funzionalità del modello sostituito. Ridurre le funzionalità solo se si è certi che nessuna applicazione utilizza le funzionalità rimosse.
  
    5.  Controllare che le modifiche funzionino come previsto e non influiscano negativamente sulle applicazioni esistenti.
  
    6.  Apportare le modifiche appropriate al documento dei criteri del certificato e ai CPS.
  
    7.  Seguire le procedure "Rilascio di un nuovo modello di certificato e Rilascio di un nuovo CPS" (se si pubblicano i CPS).
  
##### Aggiornamento di un modello di certificato
  
Questa attività descrive come apportare modifiche secondarie ai modelli di certificato. Apportare le modifiche principali duplicando il modello e imponendo il nuovo modello in modo che sostituisca il modello esistente.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Modelli di certificato</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Apportare modifiche ad un modello di certificato solo se si tratta di modifiche secondarie che non hanno un impatto significativo sugli utenti dei certificati. Questo perché è più difficile controllare l'impatto delle modifiche del modello ed è estremamente più complesso ripristinarle.
  
Esempi di modifiche secondarie:
  
-   Modifica del periodo di validità o di rinnovo
  
-   Aggiunta (ma non rimozione) di un tipo di CSP consentito
  
Implementare qualsiasi modifica che influisce sulla funzionalità dei certificati, ad esempio la modifica dei criteri dei certificati, la rimozione di tipi di CSP, la modifica dei criteri di emissione e così via, creando un nuovo tipo di modello e sostituendo il modello vecchio.
  
Valutare ed approvare la richiesta di modifica come descritto nella procedura "Aggiunta di un modello di certificato".
  
È possibile implementare e testare la modifica di modello proposta passando la modifica per il rilascio in produzione. Vedere la procedura "Rilascio di un aggiornamento del modello".
  
-   **Per aggiornare un modello di certificato**
  
    1.  Accedere come membro del gruppo Enterprise PKI Admins e caricare lo snap-in Modelli di certificato in una console MMC.
  
    2.  Aprire il modello da modificare ed apportare le modifiche richieste. Per informazioni dettagliate, consultare la documentazione del prodotto nel sistema di guida locale oppure in linea all'indirizzo: <http://technet.microsoft.com/en-us/library/cc755996.aspx> (in inglese).
  
    3.  Testare l'aggiornamento per essere sicuri che produca la funzionalità richiesta.
  
    4.  Seguire le procedure "Rilascio di un nuovo modello di certificato e Rilascio di un nuovo CPS" (se appropriato).
  
##### Rimozione di un modello di certificato
  
Quando un modello di certificato non è più necessario, può essere rimosso dallo stato attivo oppure può essere rimosso completamente dalla directory.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- Console di gestione Modelli di certificato<br />
- Console di gestione Autorità di certificazione</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Rimuovere un modello solo quando si è certi che nessuna applicazione utilizzi certificati di quel tipo. Valutare ed approvare la richiesta di rimozione del modello seguendo le modalità descritte nella procedura "Aggiunta di un modello di certificato". Seguire sempre la prima procedura per rimuovere un modello dallo stato di uso attivo e testarne gli effetti prima di eliminare completamente un modello dalla directory.

È possibile quindi implementare e testare la rimozione della modifica del modello prima di passare la modifica per il rilascio in produzione. Vedere la procedura "Rilascio della rimozione di un modello".

-   **Per rimuovere un modello di certificato dall'uso attivo**

    1.  Accedere come membro del gruppo Enterprise PKI Admins e caricare lo snap-in Autorità di certificazione in una console MMC.

    2.  Nella cartella **Modelli di certificato**, fare clic con il pulsante destro del mouse sul modello da rimuovere e selezionare **Elimina**.

    3.  Ripetere i passi 1 e 2 per tutte le CA di emissione che attualmente emettono questo tipo di certificato.

    4.  Testare tutte le applicazioni che utilizzavano in precedenza questo modello per accertarsi che non dipendano più da questo tipo di certificato.

    5.  Seguire le procedure "Rilascio di un nuovo modello di certificato e Rilascio di un nuovo CPS" (se appropriato).

<!-- -->

-   **Per rimuovere completamente un modello di certificato dalla directory**

    1.  Accedere come membro del gruppo Enterprise PKI Admins e caricare lo snap-in Modelli di certificato in una console MMC.

    2.  Fare clic con il pulsante destro del mouse sul modello da rimuovere e selezionare **Elimina**.

#### Gestione della configurazione

La funzione SMF di gestione della configurazione è responsabile dell'identificazione, della registrazione e delle attività di analisi e reporting dei componenti o delle risorse chiave IT chiamati elementi di configurazione. Le informazioni acquisite e di cui viene tenuta traccia dipendono dall'elemento di configurazione specifico, ma spesso includono una descrizione dall'elemento di configurazione, la versione, i componenti costituenti, le relazioni con gli altri elementi di configurazione, la posizione/assegnazione e lo stato corrente.

La gestione della configurazione di un'infrastruttura PKI riguarda molte aree principali:

-   Configurazione dell'infrastruttura PKI dell'organizzazione di grandi dimensioni — informazioni comuni archiviate in Active Directory

-   Configurazione del modello di certificato — dettagli della configurazione di tutti i modelli attivi

-   Configurazione dell'autorità di certificazione — dettagli specifici della configurazione dell'autorità di configurazione

-   Gruppi di gestione dell'infrastruttura PKI e dell'autorità di certificazione — dettagli dei gruppi di gestione dell'infrastruttura PKI e degli utenti e le relative autorizzazioni

-   Configurazione client — configurazione delle impostazioni utente e computer mediante criteri di gruppo (o altro metodo)

Ognuna delle seguenti sezioni descrive questi elementi in maggior dettaglio e include metodi per l'automazione della raccolta di queste informazioni, dove possibile.

Per ulteriori informazioni sulla gestione della configurazione, vedere la sezione "Ulteriori informazioni" alla fine di questo modulo.

##### Raccolta informazioni sulla configurazione dell'infrastruttura PKI dell'organizzazione di grandi dimensioni

Le informazioni sulla configurazione a livello di organizzazione di grandi dimensioni sono archiviate in Active Directory. Questo include informazioni attendibili sulla CA principale, sulla configurazione CA dell'organizzazione di grandi dimensioni e sugli annunci. Include inoltre i modelli di certificato trattati nella procedura seguente.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Utenti di dominio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Certutil.exe<br />
DSQuery.exe</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Registrare le seguenti informazioni archiviate in Active Directory:

-   Autorità di certificazione principali attendibili

-   Archivio NTAuth

-   Servizi di registrazione (CA dell'organizzazione di grandi dimensioni)

-   Certificati incrociati

-   CRL pubblicati

I comandi per raccogliere queste informazioni vengono forniti nelle procedure seguenti.

**Importante:** nei comandi seguenti è necessario sostituire il DN del dominio principale con il DN del dominio principale dell'insieme di strutture.

**Nota:** alcuni comandi appaiono su più righe per questioni di leggibilità ma devono essere immessi come singola riga.

-   **Per visualizzare le autorità di certificazione principali attendibili:**
        ```

<!-- -->

-   **Per visualizzare gli archivi NT Auth:**
        ```

<!-- -->

-   **Per visualizzare i certificati delle CA dell'organizzazione di grandi dimensioni corrente:**
        ```

<!-- -->

-   **Per visualizzare certificati incrociati e intermedi:**
        ```

<!-- -->

-   **Per visualizzare certificati della CA intermedia:**
        ```

<!-- -->

-   **Per visualizzare certificati incrociati:**
        ```

<!-- -->

-   **Per visualizzare i CRL attualmente pubblicati:**

    1.  Questo comando visualizza i **nomi dei server** di tutte le CA che hanno pubblicato i CDP nel contenitore CDP di Active Directory:
        ```

    2.  Questo comando visualizza i **nomi comuni** di tutte le CA che hanno pubblicato i CDP nel contenitore CDP di Active Directory (questi saranno oggetti figli dell'elenco precedente). Tenere presente che una CA creerà un nuovo CDP per ogni versione della CA (incrementato ogni volta che la CA viene rinnovata). Questi vengono archiviati come "CACommonName(*X*)" dove *X* è il numero di versione della CA:
        ```

    3.  Utilizzando le informazioni precedenti è possibile visualizzare il CRL di un determinato CDP:
        ```

        **Importante:** sostituire "**Woodgrove Bank Root CA**" con il nome comune della CA, "**HQ-CA-01**" con il nome dell'host della CA e "**DC=woodgrovebank,DC=com**" con il DN del dominio principale dell'insieme di strutture.

        **Nota:** per automatizzare questa operazione nel caso in cui fosse necessario eseguirla regolarmente, è possibile scrivere un semplice script di file di comando (batch).

##### Raccolta informazioni sulla configurazione del modello di certificato

I modelli di certificato sono archiviati in Active Directory. Registrare la configurazione di ciascun modello e registrare i modelli di registrazione dei certificati utilizzati per ciascun modello.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Utenti di dominio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Certutil.exe</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
I comandi per raccogliere queste informazioni sono forniti di seguito.
  
-   **Per produrre un elenco dei modelli configurati in Active Directory**
  
    <codesnippet language displaylanguage containsmarkup="false"> Certutil -template  
```
  
<!-- -->
  
-   **Per eseguire il dump della configurazione di questi modelli**
  
    <codesnippet language displaylanguage containsmarkup="false"> Certutil -dsTemplate  
```
  
Non esiste alcuno strumento che consenta di esportare le autorizzazioni dei modelli in un formato utilizzabile anche se è possibile creare un script ADSI (Active Directory Service Interface) che esegua questa operazione. Mantenere una registrazione manuale.
  
##### Raccolta informazioni sulla configurazione CA
  
In questa sezione sono descritte le informazioni di configurazione archiviate localmente su ciascuna CA e, nel caso di CA dell'organizzazione di grandi dimensioni, alcune informazioni archiviate in Active Directory.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratori locali sulla CA</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Certutil.exe</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Registrare le seguenti informazioni:
  
-   Informazioni sul registro CA
  
-   Informazioni sul certificato CA
  
-   Autorizzazioni CA
  
-   Modelli CA assegnati
  
-   CPS della CA
  
I comandi per raccogliere queste informazioni sono forniti di seguito:
  
-   **Per visualizzare la configurazione del registro CA**
  
    <codesnippet language displaylanguage containsmarkup="false"> Certutil -getreg Certutil -getreg CA  
```
  
<!-- -->
  
-   **Per visualizzare il certificato CA corrente**
  
    <codesnippet language displaylanguage containsmarkup="false"> certutil -f -ca.cert %temp%\\CAcert.cer &gt; nul &amp;&amp; certutil -dump %temp%\\CACert.cer  
```
  
**Nota:** alcuni comandi appaiono su più righe per questioni di leggibilità ma devono essere immessi come singola riga.
  
Non esiste alcuno strumento che consenta di eseguire il dump della autorizzazioni CA in un formato utilizzabile. Mantenere una registrazione manuale.
  
-   **Per visualizzare i modelli attualmente assegnati a questa CA**
  
    <codesnippet language displaylanguage containsmarkup="false"> Certutil -CATemplates  
```
  
Il file CPS della CA deve essere mantenuto con un controllo di versione adeguato in modo tale che sia semplice identificare e recuperare il CPS attivo in un determinato momento.
  
##### Raccolta informazioni sui gruppi di gestione dell'infrastruttura PKI e dell'autorità di certificazione
  
L'appartenenza ai gruppi di gestione dell'infrastruttura PKI è una parte molto importante delle informazioni di configurazione in quanto questi gruppi hanno il controllo su tutti gli aspetti delle informazioni sull'infrastruttura PKI dell'organizzazione di grandi dimensioni e sulle CA.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Utenti di dominio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Net.exe</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Per ognuno dei gruppi dell'amministrazione dell'infrastruttura PKI e dell'autorità di certificazione, elencare e registrare l'appartenenza corrente. Se uno qualsiasi dei membri è un gruppo (indicato da un asterisco prima del nome) elencare l'appartenenza di questi gruppi uno alla volta fino a quando non si ottiene l'elenco completo degli utenti di tutti i gruppi dell'infrastruttura PKI.
  
I gruppi predefiniti sono:
  
-   Enterprise PKI Admins
  
-   Enterprise PKI Publishers
  
-   CA Admins
  
-   Certificate Managers
  
-   CA Auditors
  
-   CA Backup Operators
  
Se sono stati creati ulteriori gruppi di gestione, includere anche quelli.
  
-   **Per elencare l'appartenenza di ciascun gruppo**
  
    <codesnippet language displaylanguage containsmarkup="false"> Net groups groupname /domain  
```
  
##### Raccolta informazioni sulla configurazione del client di certificato
  
Questo si riferisce alle informazioni di configurazione del client generalmente distribuite mediante il processo Criterio gruppo. Se si utilizza un altro meccanismo, ad esempio SMS o script di accesso, per distribuire le impostazioni del client correlate all'infrastruttura PKI, documentare anche queste.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratore con le autorizzazioni per la gestione degli oggetti di criteri di gruppo</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Console di gestione Criteri di gruppo</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Utilizzare la console di gestione di criteri di gruppo (GPMC) per raccogliere ed elencare le informazioni sulla configurazione del client PKI.
  
#### Gestione del rilascio
  
L'obiettivo della gestione del rilascio consiste nel facilitare l'introduzione di rilasci software e hardware negli ambienti IT gestiti. Generalmente include l'ambiente di produzione e gli ambienti di preproduzione gestiti. La gestione del rilascio è il punto di coordinamento tra i gruppi di sviluppo/progetto del rilascio ed i gruppi operativi responsabili della distribuzione del rilascio in produzione.
  
In questa sezione vengono trattate le modifiche più comuni — aggiunta, modifica e rimozione di tipi di certificato (usando i modelli di certificato). Vi sono altri tipi di modifiche che è inoltre necessario rilasciare nello stesso modo sistematico:
  
-   Modifiche alla configurazione dell'infrastruttura PKI (modelli, ID oggetto (OID) e così via).
  
-   Modifiche alla configurazione dell'autorità di certificazione — Registro di sistema locale più le impostazioni di Active Directory in oggetti di registrazione
  
-   Modifiche alla configurazione del client — modifiche GPO
  
Tutte le procedure di rilascio seguono il processo generale descritto di seguito:
  
1.  Preparazione del rilascio delle modifiche — backup della configurazione esistente.
  
2.  Test delle modifiche in modo controllato.
  
3.  Distribuzione delle modifiche in modo controllato — per numeri limitati.
  
4.  Ripristino delle modifiche — configurazione di Active Directory e CA.
  
##### Rilascio di un nuovo modello di certificato
  
L'introduzione di un nuovo modello di certificato rappresenta un cambiamento importante per l'ambiente IT, quindi il rilascio deve essere gestito in modo controllato e reversibile.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>- Enterprise PKI Admins<br />
- CA Admins</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Altre procedure a cui si fa riferimento:<br />
- Aggiunta di un modello di certificato<br />  
- Esportazione di un modello di certificato da Active Directory<br />
- Importazione di un modello di certificato in Active Directory.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- MMC Autorità di certificazione<br />
- MMC Modelli di certificato<br />
- Altri strumenti in base a quanto richiesto dalle attività dipendenti</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Il rilascio di un nuovo modello di certificato nell'ambiente di produzione viene descritto nella procedura seguente.

-   **Per rilasciare un nuovo modello di certificato**

    1.  Eseguire il backup della configurazione del modello di certificato esistente — Questa operazione può essere eseguita come parte del backup regolare di Active Directory.

    2.  Creare il nuovo modello come descritto in "Aggiunta di un modello di certificato".

    3.  Rimuovere tutte le autorizzazioni esistenti di registrazione e registrazione automatica concesse ad altri gruppi (utenti autenticati, utenti di dominio e così via). Creare il gruppo di registrazione dei certificati (e/o gruppo di registrazione automatica) per il modello come descritto in "Creazione di gruppi di registrazione modelli di certificato".

    4.  Aggiungere il nuovo modello di certificato alla CA di emissione. Se non si è anche membro del gruppo CA Admins, è necessario accedere (o utilizzare il comando **runas**) come membro di questo gruppo ed eseguire MMC Autorità di certificazione. Fare clic con il pulsante destro del mouse sulla cartella **Modelli di certificato** e selezionare **Nuovo**, quindi **Modello di certificato da emettere**. Aggiungere il modello dall'elenco.

    5.  Aggiungere gli utenti o computer pilota o di test al gruppo di registrazione dei certificati come descritto in "Attivazione della registrazione (o registrazione automatica) di un tipo di certificato per un utente o un computer".

    6.  Verificare che la registrazione del nuovo tipo di certificato funzioni come previsto.

    7.  Verificare che le funzionalità del certificato siano come previsto.

    8.  Una volta terminato il test, aggiungere gli utenti, i computer o i gruppi di protezione di produzione finale al gruppo di registrazione dei certificati come descritto in "Attivazione della registrazione (o registrazione automatica) di un tipo di certificato per un utente o un computer".

    9.  Se questo modello sostituisce uno o più modelli esistenti, è possibile rimuovere i modelli sostituiti dalla CA di emissione (mediate MMC Autorità di certificazione) per evitare che nessuno registri questi tipi di certificato sostituiti. Non eliminare questo modello dalla directory fino a quando non si è certi che tutti utilizzino il nuovo tipo di modello.

    10. Se necessario, aggiornare il CPS per riflettere la funzionalità del nuovo certificato.

Il ripristino di un nuovo tipo di modello è relativamente semplice solo se i modelli sostituiti non sono stati eliminati. Se il modello sostituito è stato eliminato, è necessario ripristinarne una copia dal backup, utilizzando un ripristino autorevole di Active Directory o le procedure di esportazione e importazione dei modelli descritte nella sezione "Gestione dell'archiviazione".

-   **Per ripristinare l'aggiunta di una nuovo modello**

    1.  Se non sono stati sostituiti altri modelli con questo modello, è possibile semplicemente eliminarlo.

    2.  Se è stato rimosso qualsiasi modello sostituito da questo modello, ripristinare prima quelli utilizzando la procedura descritta in "Importazione di un modello di certificato in Active Directory". È necessario ripristinare le autorizzazioni del modello come descritto in questa procedura.

##### Rilascio di un nuovo CPS

Se si pubblica il CPS, è necessario aggiornarlo per riflettere le modifiche delle procedure operative e dei criteri del certificato nell'organizzazione.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Amministratore con le autorizzazioni per modificare il file CPS sul server Web</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Nessuno</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>Editor di testo o HTML a seconda del formato del file CPS</p></td>
</tr>  
</tbody>  
</table>
  
**Dettagli relativi all'attività**
  
Il file CPS è generalmente archiviato come semplice file di testo o HTML su un server di file o Web. Se questo CPS è condiviso tra più CA, nello stesso file sono presenti i riferimenti di tutte le CA.
  
-   **Per rilasciare un nuovo file CPS:**
  
    1.  Eseguire il backup del file CPS esistente.
  
    2.  Apportare le modifiche richieste su una copia non in linea.
  
    3.  Sostituire il CPS.
  
    4.  Verificare che il nuovo file CPS sia leggibile da una posizione remota.
  
##### Rilascio di un aggiornamento del modello
  
Questa attività descrive come apportare le modifiche di rilascio a modelli di certificato esistenti in modo controllato e reversibile.
  
**Nota:** apportare le modifiche principali duplicando il modello e imponendo il nuovo modello in modo che sostituisca il modello esistente, non utilizzando questa procedura.

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Altre procedure a cui si fa riferimento:<br />
- Esportazione di un modello di certificato da Active Directory<br />  
- Importazione di un modello di certificato in Active Directory<br />  
- Aggiornamento di un modello di certificato<br />
- Rilascio di una nuova dichiarazione CPS</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- MMC Modelli di certificato<br />
- Altre tecnologie a seconda delle procedure</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

Apportare modifiche ad un modello di certificato solo se si tratta di modifiche secondarie che non hanno un impatto significativo sugli utenti dei certificati. Questo perché è più difficile controllare l'impatto delle modifiche del modello ed è estremamente più complesso ripristinarle.

-   **Per rilasciare l'aggiornamento di un modello di certificato**

    1.  Esportare il modello corrente su file mediante la procedura "Esportazione di un modello di certificato da Active Directory".

    2.  Accedere come membro del gruppo Enterprise PKI Admins e caricare lo snap-in Modelli di certificato in una console MMC. Apportare le modifiche al modello come descritto in "Aggiornamento di un modello di certificato".

    3.  Aggiornare il CPS e seguire le procedure per il rilascio di un nuovo CPS (se appropriato)

<!-- -->

-   **Per ripristinare l'aggiornamento di un modello di certificato**

    -   Seguire la procedura "Importazione di un modello di certificato in Active Directory" nella sezione "Gestione dell'archiviazione".

##### Rilascio della rimozione di un modello

Quando un modello di certificato non è più necessario, può essere rimosso dall'uso attivo oppure può essere rimosso completamente dalla directory.

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Cluster di ruoli:</p></td>
<td style="border:1px solid black;"><p>Rilascio</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Frequenza:</p></td>
<td style="border:1px solid black;"><p>Secondo necessità</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di protezione:</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Dipendenze:</p></td>
<td style="border:1px solid black;"><p>Altre procedure a cui si fa riferimento:<br />
- Rimozione di un modello di certificato<br />  
- Rilascio di un nuovo CPS<br />  
- Esportazione di un modello di certificato da Active Directory<br />
- Importazione di un modello di certificato in Active Directory</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Requisiti di tecnologia:</p></td>
<td style="border:1px solid black;"><p>- MMC Autorità di certificazione<br />
- Altre tecnologie a seconda delle attività</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Dettagli relativi all'attività**

La procedura di rilascio per la rimozione di un modello dall'uso attivo è relativamente semplice in quanto è semplice da ripristinare. La rimozione del modello dalla directory è più problematica in quanto richiede che il modello venga reimportato per invertire la modifica.

-   **Per rimuovere un modello di certificato dall'uso attivo**

    1.  Rimuovere il modello dalle CA di emissione correnti come descritto nella procedura "Rimozione di un modello di certificato".

    2.  Aggiornare il file CPS e seguire la procedura "Rilascio di un nuovo CPS" (se appropriato).

<!-- -->

-   **Per ripristinare la rimozione di un modello dall'uso attivo**

    1.  Accedere come membro del gruppo CA Admins ed utilizzare MMC Autorità di certificazione per aggiungere nuovamente i modelli alle CA di emissione.

    2.  Aggiornare il file CPS e seguire la procedura "Rilascio di un nuovo CPS" (se appropriato).

<!-- -->

-   **Per rimuovere completamente un modello di certificato dalla directory**

    1.  Eseguire questa procedura solo dopo che il modello di certificato è stato rimosso con successo dall'uso attivo e qualsiasi applicazione dipendente è stata testata in modo da garantire che non vi siano impatti negativi su di esse.

    2.  Esportare il modello corrente su file mediante la procedura "Esportazione di un modello di certificato da Active Directory".

    3.  Seguire la procedura "Rimozione di un modello di certificato" per rimuovere completamente un modello di certificato dalla directory.

<!-- -->

-   **Per ripristinare la rimozione di un modello dalla directory**

    -   Seguire la procedura di reimportazione del modello eliminato in "Importazione di un modello di certificato in Active Directory".

[](#mainsection)[Inizio pagina](#mainsection)

### Risoluzione dei problemi

La risoluzione dei problemi fa riferimento sia agli SMF di gestione delle emergenze che agli SMF di gestione dei problemi. La gestione delle emergenze riguarda il ripristino del servizio il prima possibile. La gestione dei problemi riguarda l'identificazione delle cause principali dei problemi e tenta di garantire che non si verifichino nuovamente.

Questa sezione è strettamente correlata alla sezione "Attività della fase di supporto". Molte delle procedure di risoluzione dei problemi riportate in questo documento fanno riferimento alle attività trattate in questa sezione.

Le emergenze più comuni che potrebbero verificarsi sono trattate in questa sezione, insieme alle procedure ed alle strategie da adottare per risolverle. L'obiettivo principale è quello di ripristinare il servizio il prima possibile. In alcuni casi, la procedura di risoluzione dei problemi costituisce un semplice riferimento ad una procedura di supporto ma, in altri casi, comprende una procedura diagnostica più complessa.

Nella tabella seguente sono elencati i principali problemi di supporto e le relative modalità di risoluzione. Nella colonna Processo supporto sono elencate le procedure da seguire. Queste procedure sono descritte in dettaglio nella sezione "Attività della fase di supporto". Dove non è riportato alcun processo, nella sezione successiva viene descritta la procedura diagnostica appropriata per il problema.

**Tabella 16. Principali problemi di supporto**

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
<td style="border:1px solid black;"><p>- Riavvio di Servizi certificati<br />
o<br />
- Riavvio del server CA</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Pubblicazione CRL non riuscita</p></td>
<td style="border:1px solid black;"><p>Il CRL è stato emesso dalla CA, ma l'ultimo CRL non è stato pubblicato in Active Directory e/o nel Web.</p></td>
<td style="border:1px solid black;"><p>Vedere la procedura di risoluzione dei problemi completa riportata di seguito.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>CRL non emesso</p></td>
<td style="border:1px solid black;"><p>Il CRL aggiornato non è stato emesso dalla CA.</p></td>
<td style="border:1px solid black;"><p>Vedere la procedura di risoluzione dei problemi completa riportata di seguito.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Il client non può registrare</p></td>
<td style="border:1px solid black;"><p>La richiesta di registrazione del client non è riuscita.</p></td>
<td style="border:1px solid black;"><p>Vedere la procedura di risoluzione dei problemi completa riportata di seguito.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Il client non può registrare automaticamente il certificato</p></td>
<td style="border:1px solid black;"><p>La richiesta di registrazione automatica del client non è riuscita.</p></td>
<td style="border:1px solid black;"><p>Vedere la procedura di risoluzione dei problemi completa riportata di seguito.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Patch installata richiede riavvio</p></td>
<td style="border:1px solid black;"><p>La patch è installata ma richiede il riavvio di Windows.</p></td>
<td style="border:1px solid black;"><p>Riavvio del server CA</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Errore server permanente</p></td>
<td style="border:1px solid black;"><p>Errore hardware o danneggiamento che richiede il ripristino.</p></td>
<td style="border:1px solid black;"><p>Ripristino CA da backup</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Certificato orfano deve essere revocato</p></td>
<td style="border:1px solid black;"><p>Dopo il ripristino della CA, tutti i certificati emessi dopo l'ultimo backup non sono presenti nel database. Questi certificati non possono essere revocati secondo la normale procedura.</p></td>
<td style="border:1px solid black;"><p>Revoca di un certificato orfano</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Il server non può essere ripristinato in tempo per l'emissione del certificato o del CRL</p></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Sequenza di attività:</p>
<ol>  
<li><p>Ripristino del certificato CA su un computer temporaneo</p></li>  
<li><p>Nuova firma di un certificato o di un CRL per estenderne la validità</p></li>
</ol></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Il certificato dell'entità finale è compromesso</p></td>
<td style="border:1px solid black;"><p>La chiave privata del certificato è stata persa, divulgata o comunque compromessa.</p></td>
<td style="border:1px solid black;"><p>Revoca del certificato di un'entità finale</p></td>
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
  
I problemi di pubblicazione del CRL verranno indicati da un avviso prodotto dallo script CheckCRLs descritto nella sezione "Monitoraggio e controllo servizi". Un CRL è stato emesso dalla CA, ma l'ultimo CRL non è stato pubblicato in Active Directory e/o nel Web. Se il problema non viene risolto, le applicazioni che richiedono i controlli delle revoche inizieranno a non funzionare correttamente.
  
Esaminare il registro degli eventi prodotto da CheckCRLs. Questo dovrebbe indicare in modo più preciso la natura del problema. Indica inoltre a quale CA appartiene il problema CDP o CRL. Il problema sarà uno dei seguenti:
  
-   Un CRL aggiornato è stato emesso dalla CA — indica qualche problema legato alla CA stessa.
  
-   Il CRL è stato prodotto ma non è stato pubblicato correttamente in uno o più dei CDP — ciò può indicare un problema con la CA, con le comunicazioni tra la CA e il CDP o con il servizio CDP stesso (Active Directory o IIS).
  
-   Il CRL è stato prodotto e pubblicato ma non è recuperabile da una o più ubicazioni CDP. Questo indica un problema con il servizio CDP stesso.
  
<!-- -->
  
-   **Per risolvere i problemi di pubblicazione CRL**
  
    1.  Accedere alla CA dove sono stati rilevati i problemi e verificare che il CRL della CA di emissione sia aggiornato. Immettere i seguenti comandi per visualizzare il CRL delle CA (per eseguire il primo di questi due comandi, è necessario essere un membro degli amministratori della CA):
  
        <codesnippet language displaylanguage containsmarkup="false"> Certutil -getCRL %temp%\\CA.crl Certutil -dump %temp%\\CA.crl  
```
  
    2.  Se il CRL non è aggiornato, vedere la procedura "CRL non emesso".
  
    3.  Aprire lo strumento Integrità PKI e controllare le voci CDP per la CA in errore. Questo strumento indica qualsiasi CDP non accessibile e CRL scaduti (sebbene non avvisa su CRL non ancora scaduti ma pronti per il rinnovo; ovvero, quando la data di **Pubblicazione CRL successiva** è trascorsa).
  
    4.  Se qualsiasi CDP viene mostrato come non accessibile, controllare il servizio di pubblicazione di tale CDP.
  
    5.  Se (da registro eventi) viene mostrato un errore con CDP LDAP, controllare il collegamento al controller di dominio di Active Directory dalla CA che utilizza DCDiag mediante gli strumenti di supporto di Windows Server 2003. Questo mostra se vi sono problemi con DC o legati alla connettività della CA con DC. Controllare tutti gli errori.
  
    6.  Controllare le autorizzazioni sul contenitore CDP per la CA utilizzando i siti di Active Directory ed i servizi MMC (in: "**cn=CDP,cn=Public Key Services,cn=Services, cn=Configuration,*DC=woodgrovebank,DC=com****"* — sostituire le voci in corsivo con il DN per il dominio principale dell'insieme di strutture).
  
    7.  Creare un account temporaneo e aggiungerlo al gruppo Cert Publishers. Accedere con tale account, prendere il CRL recuperato nel passaggio 1 e tentare di pubblicarlo manualmente nella directory utilizzando il comando seguente:
  
        <codesnippet language displaylanguage containsmarkup="false"> certutil -dspublish CA.crl CAHostname CASubjectName  
```
  
    8.  Se viene mostrato un errore (dal registro eventi) con CDP HTTP, controllare se è coinvolto il server IIS. Controllare connettività e autorizzazioni. Eseguire manualmente lo script per pubblicare i CRL nel server IIS (vedere l'attività "Pubblicazione degli elenchi CRL della CA di emissione nel server Web" nella sezione "Attività della fase operativa") e controllare gli errori. Quando si esegue questa attività, provare ad utilizzare la stessa appartenenza di gruppo/account della CA stessa.
  
    9.  Se i CRL vengono pubblicati nei servizi CDP con successo ma è presente un problema indicato da Integrità PKI, significa che è presente un problema con il servizio CDP (Active Directory o IIS). La risoluzione dei problemi di questi servizi esula dagli argomenti trattati in questo documento.
  
##### CRL non emesso
  
Questa è una condizione improbabile nel normale funzionamento. Una CA può generalmente pubblicare sempre un CRL localmente a meno che non sia stata riconfigurata per non pubblicare i CRL dalla sua cartella di sistema locale (*%windir%*\\system32\\certsrv\\certenroll). Se il percorso di pubblicazione locale non è stato riconfigurato potrebbe indicare un problema grave con la CA. Seguire le procedure di risoluzione dei problemi generiche per determinare la causa del problema come indicato di seguito. Sebbene questa procedura è rivolta ai problemi CRL, la maggior parte delle operazioni è generica e può essere utilizzata per qualsiasi problema secondario con Servizi certificati.
  
-   **Per risolvere i problemi di emissione del CRL**
  
    1.  Esaminare il registro eventi per qualsiasi errore registrato da Servizi certificati.
  
    2.  Tentare di imporre manualmente l'emissione di un CRL (accedere come membro del gruppo CA Admins):
  
        <codesnippet language displaylanguage containsmarkup="false"> Certutil -CRL  
```
  
    3.  Se l'operazione non riesce, esaminare di nuovo il registro eventi per eventuali nuovi errori.
  
    4.  Esaminare il certificato CA e tutti i certificati della catena per la CA principale per vedere se sono presenti problemi con i certificati (certificati scaduti, revocati e così via).
  
    5.  Verificare che sia possibile firmare di nuovo una certificato o un CRL con la chiave CA (vedere la procedura "Nuova firma di un certificato o di un CRL per estenderne la validità" nella sezione "Attività della fase di supporto").
  
    6.  Riavviare la CA ed eseguire di nuovo questi controlli.
  
    7.  Se il CRL non viene ancora prodotto, attivare la registrazione di debug (vedere Registrazione Servizi certificati). Quindi, tentare di emettere il CRL ed esaminare la registrazione per gli errori.
  
##### Il client non può registrare un certificato
  
Eseguire i passi seguenti per diagnosticare i problemi relativi alla registrazione dei certificati.
  
1.  Verificare che il modello di certificato sia stato assegnato ad una CA.
  
2.  Verificare che l'utente o computer disponga delle autorizzazioni per registrare sulla CA alla quale è stato assegnato il modello.
  
3.  Verificare che il modello corrisponda al tipo soggetto — i modelli utente possono essere registrati solo da utenti mentre i modelli computer possono essere registrati solo da computer.
  
4.  Verificare che la CA possa accedere ai propri CRL pubblicati e a quelli delle relative CA padre. La CA esegue sempre un controllo delle revoche prima di emettere un certificato.
  
5.  Verificare che il modello di certificato non imponga l'uso di CSP non disponibili per la registrazione. Ad esempio, CSP di smart card per un computer; o quando l'utente non dispone di una smart card, CSP di canale protetto (SChannel) RSA (Rivest-Shamir-Adleman) per utenti.
  
6.  Verificare che il modello di certificato non richieda informazioni da inserire nel campo **Soggetto** o **Soggetto alternativo** che non esiste in Active Directory. Un problema comune consiste nello specificare che l'indirizzo di posta elettronica debba essere incluso nel nome soggetto ma non il fatto che il campo della posta elettronica debba essere specificato nell'oggetto Active Directory dell'utente.
  
##### Il client non può registrare automaticamente un certificato
  
Informazioni esaurienti per la comprensione e la risoluzione dei problemi relativi alla registrazioni automatica sono disponibili nell'articolo "Certificate Autoenrollment in Windows XP" all'indirizzo: [http://www.microsoft.com/WindowsXP/pro/techinfo/administration/autoenroll/default.asp](http://www.microsoft.com/windowsxp/pro/techinfo/administration/autoenroll/default.asp) (in inglese).
  
Verificare che un client possa registrare manualmente il certificato che si sta tentando di registrare automaticamente. Caricare MMC certificati e richiedere un nuovo certificato. Se il tipo di certificato non appare oppure se appare ma viene prodotto un errore quando si tenta di effettuarne la registrazione, seguire la procedura della sezione precedente "Il client non può registrare un certificato".
  
Se la registrazione manuale è possibile, continuare con i passi seguenti.
  
1.  Verificare che la piattaforma in uso sia corretta. Solo Windows 2000 e le versioni successive supportano la registrazione automatica di computer. Solo Windows XP e Windows Server 2003 supportano la registrazione automatica di utenti.
  
2.  Verificare che l'utente o computer disponga delle autorizzazioni di **Registrazione automatica** sul modello di certificato per il tipo di certificato richiesto.
  
3.  Verificare che l'impostazione dei criteri del gruppo di registrazione automatica sia stata specificata correttamente. Affinché la registrazione automatica funzioni correttamente, il GPO sul quale è stata configurata la registrazione automatica deve avere maggiore precedenza rispetto a tutti gli altri GPO. Ad esempio, se questo GPO viene creato a livello di dominio, deve avere una priorità più alta rispetto ai criteri di dominio predefiniti. È possibile controllare la precedenza dei GPO con MCC Gruppo di criteri risultanti.
  
4.  Verificare che il modello di certificato non richieda l'approvazione manuale o le firme dell'autorità di registrazione. Le richieste di certificati che richiedono l'approvazione del gestore dei certificati verranno inviate per l'approvazione ma il certificato non verrà emesso all'utente fino a quando non viene approvato manualmente. Le richieste che richiedono le firme dell'autorità di registrazione verranno rifiutate in quando non esiste una procedura per l'aggiunta di ulteriori firme ad una richiesta di registrazione automatica.
  
5.  Verificare che il modello di certificato non sia impostato in modo tale da prevedere che nella richiesta debbano essere fornite le informazioni relative al soggetto. Per i certificati a registrazione automatica il relativo soggetto (e soggetto alternativo) deve essere impostato dalla CA.
  
#### Tecniche e strumenti di risoluzione dei problemi
  
In questa sezione vengono descritti alcuni strumenti utili per la diagnosi e la soluzione dei problemi relativi all'infrastruttura PKI. Vengono inoltre descritte le registrazioni di Servizi certificati e le modalità di attivazione di registrazioni più dettagliate per Servizi certificati e la registrazione automatica del client.
  
##### Integrità PKI
  
Integrità PKI è principalmente uno strumento diagnostico CDP e AIA che tenta di creare una vista di tutte le CA dell'organizzazione di grandi dimensioni. È molto utile per la diagnosi della connettività e dei problemi di pubblicazione CDP e AIA. È possibile eseguire il download dei CRL o dei certificati ai quali fanno riferimento CDP o AIA. È disponibile come parte del Resource Kit di Windows.
  
##### Certutil
  
Certutil è il singolo strumento più importante per la gestione e la risoluzione dei problemi delle CA Windows. Per informazioni su alcuni degli usi principali di questo strumento, vedere "Using Certutil.exe to Manage and Troubleshoot Certificate Services" all'indirizzo:
  
<http://technet.microsoft.com/en-us/library/cc962081.aspx> (in inglese).
  
Tuttavia, sono disponibili molte altre opzioni relative alle procedure diagnostiche e di gestione. È possibile visualizzare l'elenco completo delle opzioni disponibili immettendo:
  
<codesnippet language displaylanguage containsmarkup="false"> Certutil -uSAGE   
```  
##### Altri strumenti diagnostici
  
Altri strumenti diagnostici e di gestione utili sono:
  
-   Certreq.exe — consente di creare, inviare e recuperare le richieste di certificati dalla riga di comando.
  
-   DCDiag.exe — utile per la diagnosi di problemi con Active Directory che possono influire sulle CA.
  
##### Registrazione Servizi certificati
  
Servizi certificati ed i relativi strumenti associati producono diverse registrazioni molto utili per la risoluzione dei problemi.
  
-   Registrazioni Servizi certificati per *%systemroot%\\*certsrv.log (quando la registrazione di debug è abilitata).
  
-   Registrazioni Certutil.exe per *%systemroot%\\*certutil.log.
  
-   Registrazioni MMC Autorità di certificazione per *%windir%*\\certmmc.log.
  
<!-- -->
  
-   **Per attivare la registrazione di debug su Servizi certificati**
  
    1.  Eseguire il comando seguente:
  
        <codesnippet language displaylanguage containsmarkup="false"> certutil -setreg CA\\Debug 0xffffffe3  
```
  
Le voci della registrazione vengono salvate in *%windir%*\\certsrv.log
  
-   **Per disattivare la registrazione di debug**
  
    1.  Eseguire il comando seguente:
  
        <codesnippet language displaylanguage containsmarkup="false"> certutil -delreg CA\\Debug  
```
  
##### Registrazione eventi di registrazione automatica
  
Per attivare la registrazione degli eventi di registrazione automatica, è necessario aggiungere un valore di registro. La registrazione avanzata viene attivata separatamente per la registrazione automatica di utenti e di computer.
  
-   **Per attivare la registrazione di eventi di registrazione automatica utente**
  
    1.  Creare un nuovo valore di registro **DWORD** chiamato **AEEventLogLevel** nella chiave **HKEY\_CURRENT\_USER\\Software\\Microsoft\\Cryptography\\Autoenrollment**.
  
    2.  Impostare il valore su **0**.
  
<!-- -->
  
-   **Per attivare la registrazione di eventi di registrazione automatica computer**
  
    1.  Creare un nuovo valore di registro **DWORD** chiamato **AEEventLogLevel** nella chiave **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Cryptography\\Autoenrollment**.
  
    2.  Impostare il valore su **0**.
  
**Nota:** tutti gli errori vengono registrati automaticamente. Non è necessario attivare la chiave di registro per abilitare la registrazione degli errori.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Tabelle di configurazione
  
Le tabelle seguenti contengono le informazioni di configurazione specifiche del sito e della soluzione alle quali fanno riferimento le procedure di questo modulo. Queste tabelle sono un sottogruppo delle tabelle di configurazione della pianificazione riportata nella sezione "Building Certificate Services" della*Build Guide* disponibile per il download all'indirizzo: [http://www.microsoft.com/downloads/details.aspx?FamilyID=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en](http://www.microsoft.com/downloads/details.aspx?familyid=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en) (in inglese).
  
**Tabella 17. Elementi di configurazione definiti dall'utente**

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
<td style="border:1px solid black;"><p>Nome DNS del dominio principale dell'insieme di strutture di Active Directory</p></td>
<td style="border:1px solid black;"><p>woodgrovebank.com</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>DN del dominio principale dell'insieme di strutture</p></td>
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
  
**Tabella 18. Elementi di configurazione definiti dalla soluzione**

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
<td style="border:1px solid black;"><p>Autorizzato a pubblicare CRL e certificati CA nel contenitore della configurazione dell'organizzazione di grandi dimensioni</p></td>
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
<td style="border:1px solid black;"><p><em>%systemroot%</em>\System32\CertLog</p></td>
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
  
Per ulteriori informazioni su qualsiasi modello di processo e modello di team Microsoft Operations Framework, vedere i riferimenti nel primo modulo di *Operations Guide* disponibile per il download all'indirizzo: [http://www.microsoft.com/downloads/details.aspx?FamilyID=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en](http://www.microsoft.com/downloads/details.aspx?familyid=cdb639b3-010b-47e7-b234-a27cda291dad&displaylang=en) (in inglese).
  
-   Per informazioni sulla distribuzione MOM, vedere MOM Operations Guide, all'indirizzo: <http://technet.microsoft.com/en-us/library/cc181143.aspx> (in inglese).
  
-   Per informazioni sulla gestione delle patch che utilizza Microsoft Systems Management Server, vedere: <http://technet.microsoft.com/en-us/library/cc182024.aspx> (in inglese).
  
-   Per informazioni sulla gestione delle patch che utilizza Microsoft Software Update Services, vedere: <http://technet.microsoft.com/en-us/library/cc708609.aspx> (in inglese).
  
-   Per informazioni su come ottenere ed utilizzare GPMC, vedere: <http://www.microsoft.com/windowsserver2003/gpmc/default.mspx> (in inglese).
  
-   Per ulteriori informazioni sui problemi di pubblicazione degli elenchi CRL, vedere: <http://support.microsoft.com/kb/289749> (in inglese).
  
-   Per ulteriori informazioni sulle restrizioni della capacità di Servizi certificati ed i contatori delle prestazioni correlati, vedere Microsoft Knowledge Base Q146005, "Optimizing Windows NT for Performance", all'indirizzo: <http://support.microsoft.com/default.aspx?scid=146005>.
  
-   Per ulteriori informazioni su attività operative supplementari, vedere la documentazione del prodotto Servizi certificati di Windows Server 2003, all'indirizzo: [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/sag\_CS\_procs\_admin.asp](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/sag_cs_procs_admin.asp) (in inglese).
  
-   Per gli strumenti di risoluzione dei problemi Certutil, vedere il white paper "Using Certutil.exe to Manage and Troubleshoot Certificate Services" all'indirizzo: <http://technet.microsoft.com/en-us/library/cc962081.aspx> (in inglese).
  
-   Per informazioni esaurienti per la comprensione e la risoluzione dei problemi relativi alla registrazioni automatica, vedere l'articolo "Certificate Autoenrollment in Windows XP" all'indirizzo: [http://www.microsoft.com/WindowsXP/pro/techinfo/administration/autoenroll/default.asp](http://www.microsoft.com/windowsxp/pro/techinfo/administration/autoenroll/default.asp) (in inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
