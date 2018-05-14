---
TOCTitle: 'Appendice B: Script e file di supporto'
Title: 'Appendice B: Script e file di supporto'
ms:assetid: '85c92d5b-9034-48cc-bcf5-5c84d5aae999'
ms:contentKeyID: 21736322
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd772498(v=TechNet.10)'
---

Appendice B: Script e file di supporto
======================================

Pubblicato: 11 ottobre 2004 | Aggiornato: 24/11/2004

##### In questa pagina

[](#edaa)[Introduzione](#edaa)  
[](#ecaa)[Elenco dei file della soluzione](#ecaa)  
[](#ebaa)[Struttura degli script](#ebaa)  
[](#eaaa)[Descrizione degli script e dei file di supporto](#eaaa)  

### Introduzione

Questa appendice contiene una breve descrizione degli script e di altri file di supporto forniti con la soluzione *Protezione delle reti LAN senza fili con Servizi certificati*. Gli script e i file di supporto funzionano e sono stati testati, quindi possono essere utilizzati come riferimento per la realizzazione di script di amministrazione personalizzati. Non sono stati ideati per fungere da codice di produzione di qualità.

#### Condizioni per l'utilizzo

Gli script e i file di supporto forniti con questa soluzione sono soggetti alle CONDIZIONI PER L'UTILIZZO standard di Microsoft. Le condizioni sono disponibili nella pagina [Microsoft - Information on Terms of Use](http://www.microsoft.com/info/cpyright.htm) all'indirizzo http://www.microsoft.com/info/cpyright.htm (in inglese).

**Nota:** assicurarsi di eseguire test esaustivi di questi script e strumenti in un ambiente di test prima di distribuirli in un ambiente di produzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Elenco dei file della soluzione

#### Script comuni

-   constants.vbs

-   helper.vbs  

#### Script di Servizi certificati

-   Pkiparams.vbs

-   ca\_monitor.vbs

-   ca\_monitor.wsf

-   ca\_operations.vbs

-   ca\_operations.wsf

-   ca\_setup.vbs

-   ca\_setup.wsf  

#### Script di IAS e WLAN

-   ias\_tools.vbs

-   ias\_tools.wsf

-   wl\_tools.vbs

-   wl\_tools.wsf

-   IASClientExport.bat

-   IASClientImport.bat

-   IASExport.bat

-   IASImport.bat

-   IAS\_Data.bat  

#### File di supporto per IAS e WLAN

-   IASAccessPrep.txt  

#### File di installazione automatica di componenti facoltativi

-   OC\_AddIAS.txt

-   OC\_AddIIS.txt

-   OC\_RemoveRootUpdate.txt

[](#mainsection)[Inizio pagina](#mainsection)

### Struttura degli script

I file batch sono relativamente semplici da seguire, ma per comprendere il funzionamento e le interazioni dei file VBScript (Microsoft® Visual Basic® Scripting Edition) sono necessarie alcune spiegazioni. A differenza di molti esempi VBScript, questi script contengono più funzioni. Per fornire l'accesso a queste diverse funzioni, tali script sfruttano la funzionalità "job" (processo) di Microsoft Windows® Scripting Host (WSH). Questa consente diverse funzioni di programma indipendenti mediante la specifica di un nome di processo come parametro dello script.

Gli script sono spesso accoppiati: un file .wsf e un file .vbs. Il file WSF contiene l'"interfaccia utente" per diverse operazioni di script. Il file VBS contiene tutto il codice che svolge il lavoro del programma.

Tutti i file di script WSF utilizzano la sintassi dove *NomeProcesso* è il nome dell'operazione richiesta e *WScriptFile* è il nome del file di interfaccia XML per lo script come indicato nel seguente esempio:

cscript //job:*NomeProcesso* *WScriptFile*.wsf

Un estratto di uno dei file WSF include le seguenti informazioni:

```
        <?xml version="1.0" encoding="utf-8" ?>
        <package xmlns="Windows Script Host
            <job id="GetCaCerts ">
                <comment></comment>
                <script language="VBScript" src="constants.vbs" />
                <script language="VBScript" src="pkiparams.vbs" />
                <script language="VBScript" src="helper.vbs" />
                <script language="VBScript" src="ca_operations.vbs" />
                <script language="VBScript
                <![CDATA[
                    GetCaCerts
                ]]>
                </script>
            </job>
            <job id="PublishRootCertstoIIS ">
                <comment></comment>
                <script language="VBScript" src="constants.vbs" />
                <script language="VBScript" src="pkiparams.vbs" />
                <script language="VBScript" src="helper.vbs" />
                <script language="VBScript" src="ca_operations.vbs" />
                <script>
                <![CDATA[
                    PublishCertstoIIS ROOT_CERT_SOURCE, WWW_LOCAL_PUB_PATH
                ]]>
                </script>
            </job>
```

Il primo processo è GetCACerts. La definizione del processo specifica che i file VBS constants.vbs, pkiparams.vbs, helper.vbs, e ca\_operations.vbs verranno caricati e contengono funzioni o subroutine richieste da questo processo. La sezione finale dell'esempio di codice specifica la funzione di livello superiore che viene eseguita per avviare il processo, in questo caso GetCACerts. Questo esempio ha lo stesso nome del processo, ma i nomi non devono essere necessariamente uguali. Si osservi che il secondo processo, PublishRootCertstoIIS, fornisce i parametri della funzione chiamata.

Sono i file VBS che effettivamente svolgono il lavoro e ce ne sono di tre tipi:

-   File di script di specifiche operazioni che contengono funzioni attinenti solo a un particolare tipo di operazione. Ad esempio, ca\_operations.vbs contiene funzioni relative a operazioni di autorità di certificazione (CA).

-   File di script di funzioni generiche, che contengono funzioni più generali utilizzabili dagli script di specifiche operazioni. Helper.vbs è l'unico di questi script e contiene funzioni, quali la creazione di account utente o il controllo degli errori.

-   File di script di parametri che contengono costanti VBScript, le quali definiscono la modalità di esecuzione degli script operativi. Queste sono state raggruppate in modo che sia più facile modificarle in una posizione invece di incorporarle nelle funzioni di script. In questa categoria sono compresi il file constants.vbs, che contiene i parametri globali, e il file pkiparams.vbs, che include i parametri propri della configurazione e delle operazioni dell'infrastruttura a chiave pubblica (PKI).

[](#mainsection)[Inizio pagina](#mainsection)

### Descrizione degli script e dei file di supporto

Questa sezione descrive ciascuno degli script e dei file di supporto elencati in precedenza.

#### Script comuni

Ci sono due tipi di file di script comuni.

##### Constants.vbs

Questo script contiene valori comuni impostabili dagli utenti e usati dagli altri file VBS e WSF. Ad esempio, in questo script è possibile configurare le impostazioni per gli avvisi SMTP e del registro eventi.

##### Helper.vbs

Questo script contiene routine di supporto comuni utilizzate da molti degli altri script VBS (ad esempio, funzioni di creazione di utenti e gruppi, routine di avvisi e utilità varie).

#### Script di Servizi certificati

Questa sezione descrive gli script di Servizi certificati.

##### Pkiparams.vbs

Questo script contiene valori specifici PKI o CA modificabili dall'utente. Prima di poter utilizzare alcuni di questi valori *è necessario* modificarli (per configurare le impostazioni appropriate per l'ambiente in uso), mentre altri non richiedono alcuna modifica, a meno che non si desideri cambiare il funzionamento degli script. Nei capitoli principali della guida (capitolo 7, "Implementazione dell'infrastruttura a chiave pubblica" e il capitolo 11, "Gestione dell'infrastruttura a chiave pubblica") vengono fornite indicazioni sulla necessità o meno di modificare i valori in queste procedure.

Tutti gli altri script includono un riferimento a PKIParams.vbs mediante un prefisso "CA\_".

##### ca\_setup.vbs and ca\_setup.wsf

Questi script contengono funzioni per la configurazione delle impostazioni di base delle CA utilizzate per creare utenti e gruppi di protezione. Ci sono routine di configurazione per le CA principale e di emissione. La maggior parte dei valori impostati sono controllati dal file pkiparams.vbs. Per ulteriori informazioni su questo file, consultare il capitolo 7, "Implementazione dell'infrastruttura a chiave pubblica".

Tra i processi contenuti in questi script sono compresi:

-   CertLocalGroups - Questo processo crea gruppi di protezione locali (utilizzati sulla CA principale) per l'amministrazione delle CA. La funzione di creazione dei gruppi viene chiamata più volte come parte del processo e ogni volta con un nome di gruppo diverso.

-   CertDomainGroups - Questo processo crea gruppi di protezione di dominio per l'amministrazione delle CA e dell’infrastruttura a chiave pubblica. Contiene più chiamate per la creazione di diversi gruppi. Il tipo di gruppo (Locale, Globale o Universale) viene specificato come un parametro nella definizione del processo.

-   CertLocalTestAccts - Questo processo crea account di utenti di prova per l'amministrazione della CA principale.

-   CertDomainTestAccts - Questo processo crea account di dominio di prova per l'amministrazione delle CA in linea.

-   RootCAConfig - Questo processo configura parametri della CA principale utilizzando chiamate a certutil.

-   IssCAConfig — Questo processo configura parametri della CA di emissione utilizzando chiamate a certutil.

##### ca\_monitor.vbs and ca\_monitor.wsf

Questi script contengono funzioni per il controllo dello stato delle CA e dell'infrastruttura a chiave pubblica. Gli script controllano specificatamente che la CA sia reattiva e che i certificati CA e gli elenchi di revoche di certificati (CRL) siano aggiornati. Gli script generano voci del registro eventi o avvisi SMTP (Simple Mail Transfer Protocol) o entrambi. Sono progettati per essere eseguiti da un agente MOM (Simple Mail Transfer Protocol) (o un simile agente di gestione in esecuzione nel server) o dall'Utilità di pianificazione di Windows su una CA in linea. Questa procedura di script è utilizzata solo nel capitolo 11, "Gestione dell’infrastruttura a chiave pubblica".

Tra i processi contenuti in questi script sono compresi:

-   IsCAAlive - Questo processo controlla che le interfacce RPC (Remote Procedure Call) di Servizi certificati stiano rispondendo.

-   CheckCRLs - Questo processo controlla i CRL della CA su cui viene eseguito lo script e i CRL di tutte le CA padre fino alla CA principale. Vengono generati degli avvisi se un CRL è scaduto o se sta per scadere o quando dovrebbe essere stato emesso un nuovo CRL.

-   CheckCACerts - Questo processo controlla il certificato CA sulla CA su cui viene eseguito lo script e i certificati di tutte le CA padre fino alla CA principale. Vengono generati degli avvisi se un certificato è scaduto, se manca un mese alla sua scadenza e se deve essere rinnovato (in genere a metà della sua durata).

-   SetupSMTPAlerts - Questo processo imposta la CA per l'invio di avvisi tramite posta elettronica quando una richiesta di certificati in sospeso (in attesa dell'approvazione del Certificate Manager) è stata inserita in coda sulla CA.

##### ca\_operations.vbs and ca\_operations.wsf

Questi script contengono funzioni attinenti alle operazioni in corso sulla CA, quali la pubblicazione di certificati e CRL e il backup di database e chiavi CA. Questi script sono utilizzati principalmente nel capitolo 11, "Gestione dell'infrastruttura a chiave pubblica", nonché in alcune delle procedure nel capitolo 7, "Implementazione dell'infrastruttura a chiave pubblica".

Tra i processi contenuti in questi script sono compresi:

-   GetCaCerts - Questo processo recupera i certificati CA dalla CA principale e li memorizza su un disco floppy.

-   GetCRLs - Questo processo recupera i CRL dalla CA principale e li memorizza su un disco floppy.

-   PublishCertstoAD - Questo processo pubblica il certificato della CA principale (recuperato tramite GetCaCerts) nel servizio directory Microsoft Active Directory®.

-   PublishCRLstoAD - Questo processo pubblica i CRL della CA principale (recuperati tramite GetCRLs) in Active Directory.

-   PublishRootCertstoIIS - Questo processo pubblica il certificato della CA principale (recuperato tramite GetCaCerts) nel server Web IIS (Internet Information Services).

-   PublishRootCRLstoIIS - Questo processo pubblica i CRL della CA principale (recuperati tramite GetCRLs) nel server Web IIS.

-   PublishIssCertstoIIS - Questo processo pubblica il certificato della CA di emissione (recuperato tramite GetCaCerts) nel server Web IIS.

-   PublishIssCRLstoIIS — Questo processo pubblica i CRL della CA di emissione (recuperati tramite GetCRLs) nel server Web IIS.

-   BackupCaKeys - Questo processo esegue il backup delle chiavi e dei certificati CA su un disco floppy.

-   BackupCaDatabase - Questo processo esegue NTBackup.exe per effettuare un backup dello stato del sistema della CA (inclusi i registri e il database della CA).

#### Script di IAS e WLAN

Questa sezione descrive gli script di IAS e WLAN.

##### ias\_tools.vbs and ias\_tools.wsf

Questi script contengono processi per facilitare l'impostazione dell'utente per il Servizio autenticazione Internet (IAS) di Microsoft. Gli script sono utilizzati nel capitolo 8, "Implementazione dell'infrastruttura RADIUS" e nel capitolo 9, "Implementazione dell'infrastruttura per la protezione di reti LAN senza fili".

Tra i processi contenuti in questi script sono compresi:

-   CreateIasGroups - Questo processo crea i gruppi di protezione di dominio necessari per la soluzione per l'amministrazione di IAS.

-   UpdateUsersRAP - Questo processo modifica le proprietà delle chiamate in ingresso per abilitare l'accesso remoto. Non è stato utilizzato nella presente soluzione, ma è stato incluso nel caso si decida di usarlo. Questo script aggiorna gli oggetti utente *solo* nel contenitore UTENTI; per aggiornare oggetti in un'altra posizione, utilizzare lo script come modello e modificarlo seconde le necessità.

##### wl\_tools.vbs and wl\_tools.wsf

Questi script creano gruppi di protezione necessari per la gestione degli utenti della rete LAN senza fili (WLAN) e contengono una routine per generare segreti di RADIUS/punti di accesso senza fili. Questi script sono utilizzati nel capitolo 9, "Implementazione dell'infrastruttura per la protezione di reti LAN senza fili".

Tra i processi contenuti in questi script sono compresi:

-   CreateWirelessGroups - Questo processo crea gruppi di protezione utilizzati per gestire le autorizzazioni di utenti e computer, la registrazione dei certificati e l'applicazione di criteri di rete senza fili.

-   GenPWD - Questo progetto genera, mediante crittografia, password casuali per i server IAS e i punti di accesso senza fili. Il processo utilizza CAPICOM per generare stringhe casuali.

##### Script di gestione di IAS

In questa sezione vengono descritti gli script di gestione di IAS.

-   IASClientExport.bat e IASClientImport.bat - Questi file batch consentono l'esportazione delle informazioni dei client RADIUS  del server IAS su un disco floppy per un'archiviazione sicura. Lo script di importazione importa le informazioni dei client RADIUS del server IAS da un disco floppy e le ricarica nel server IAS. Questi script sono utilizzati nel capitolo 12, "Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili".

-   IASExport.bat e IASImport.bat - Lo script IASExport esporta lo stato di configurazione IAS comune (eccetto le informazioni del client RADIUS) nei file di testo di configurazione nella directory D:\\IASConfig. Questo script viene eseguito come un evento notturno tramite l'Utilità di pianificazione e viene utilizzato per esportare le impostazioni del server IAS RADIUS primario.

    Il file batch IASImport importa lo stato di configurazione IAS esportato in precedenza dai file di testo di configurazione nella directory D:\\IASConfig. Questo file viene utilizzato per il ripristino di emergenza e per creare i server IAS secondario e terziario illustrati nel capitolo 8, "Implementazione dell'infrastruttura RADIUS” della Guida alla creazione. Questi file batch sono utilizzati anche nel capitolo 12, "Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili".

-   IAS\_Data.bat - Questo file batch crea, imposta autorizzazioni e condivide cartelle IAS. Questo file viene configurato per essere eseguito dallo stesso dominio dei gruppi utilizzati per applicare le autorizzazioni alle cartelle. In caso contrario, modificare lo script per utilizzare il nome dominio esplicito. Questo file è utilizzato nel capitolo 8, "Implementazione dell'infrastruttura RADIUS”.

##### File IAS aggiuntivo

In questa sezione viene illustrato il file IAS aggiuntivo.

-   IASAccessPrep.txt - Questo file di testo contiene i tipi di dati e la riga di intestazione per i dati del Registro richieste di RADIUS, importati in Microsoft Access dai controllori della protezione IAS. Per informazioni sull'utilizzo di questo file, consultare il capitolo 12, "Gestione dell'infrastruttura di protezione RADIUS e LAN senza fili".

#### File di installazione di componenti facoltativi

-   OC\_AddIIS.txt e OC\_RemoveRootUpdate.txt - È possibile utilizzare questi file di testo con Gestione componenti facoltativi di Windows (Gestore OC) per specificare i componenti da installare e disinstallare. Questi file consentono l'installazione automatica di IIS e la disinstallazione del servizio di aggiornamento Microsoft Root Update. Questi file di testo sono utilizzati nel capitolo 7, "Implementazione dell'infrastruttura a chiave pubblica".

-   OC\_AddIAS.txt - È possibile utilizzare questo file di testo con Gestore OC per specificare i componenti da installare per consentire l'installazione automatica di IAS. Questo file di testo è utilizzato nel capitolo 8, "Implementazione dell'infrastruttura RADIUS”.

[](#mainsection)[Inizio pagina](#mainsection)
