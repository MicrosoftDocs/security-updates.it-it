---
TOCTitle: Script e file di supporto
Title: Script e file di supporto
ms:assetid: 'a03d9672-e537-477b-8ec1-d05cda6ea378'
ms:contentKeyID: 20200840
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536241(v=TechNet.10)'
---

Protezione delle reti LAN senza fili con PEAP e password
========================================================

### Appendice D: Script e file di supporto

Aggiornato: 2 aprile 2004

##### In questa pagina

[](#edaa)[Introduzione](#edaa)  
[](#ecaa)[Elenco dei file forniti con la soluzione](#ecaa)  
[](#ebaa)[Struttura degli script](#ebaa)  

### Introduzione

Questa appendice contiene una breve descrizione degli script e degli altri file di supporto forniti con la soluzione. Gli script funzionano e sono stati testati con la soluzione, ma non sono stati sottoposti a un processo completo di controllo della qualità. Scopo di questi script è illustrare le tecniche suggerite e fungere da base per la realizzazione di script di amministrazione personalizzati. Prima di utilizzarli nell'ambiente di produzione è consigliabile sottoporli a test completi.

#### Dichiarazione di non responsabilità

Gli script di esempio non sono supportati da nessun programma o servizio di supporto standard di Microsoft®. Gli script di esempio vengono forniti COSÌ COME SONO, senza garanzia di alcun tipo. Microsoft non riconosce alcuna garanzia implicita, comprese, tra le altre, la garanzia di commerciabilità e/o idoneità per un fine particolare. L'utente utilizza gli script di esempio e la documentazione a suo rischio. Microsoft o i suoi autori o chiunque sia coinvolto nella creazione, produzione o distribuzione degli script non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi, tra gli altri, la perdita di profitti, la perdita di informazioni o altre perdite pecuniarie, derivanti dall'uso o dall'impossibilità di utilizzare gli script di esempio o la documentazione, anche se Microsoft sia stata informata della possibilità del verificarsi di tali danni.

[](#mainsection)[Inizio pagina](#mainsection)

### Elenco dei file forniti con la soluzione

Nella tabella seguente sono elencati tutti i file forniti con la soluzione. Questi file vengono installati dal file MSSWLANTools.msi di Windows® Installer.

**Tabella D.1: Elenco dei file forniti con la soluzione**

<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome file</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>File CMD principali</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSSSetup.cmd
MSSTools.cmd</td>
<td style="border:1px solid black;">Sono i file batch che forniscono l'interfaccia per i file Microsoft Windows Scripting Host (WSH) e semplificano la sintassi. Consentono di eseguire vari processi specificando il nome del processo come unico parametro della riga di comando. La sintassi è la seguente:
<strong>msssetup</strong><em>NomeProcesso</em> [/param:<em>valore</em>]
<strong>msstools</strong> <em>NomeProcesso</em> [/param:<em>valore</em>]
dove <em>NomeProcesso</em> è il nome dell'operazione. Se si esegue questo script senza specificare un nome di processo, verranno elencati tutti i processi disponibili, insieme a una breve descrizione della funzione di ognuno.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>File XML WSH</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">msssetup.wsf
msstools.wsf</td>
<td style="border:1px solid black;">Sono file XML WSH, che specificano i singoli processi disponibili. I processi definiti nei file WSF richiamano procedure definite nei file VBS. La sintassi è la seguente:
<strong>Cscript //job:</strong><em>NomeProcesso</em> msstools.wsf [/param:<em>valore</em>]
Se si esegue questo script senza specificare un nome di processo, viene elencato il contenuto del file WSF insieme a una breve descrizione della funzione di ogni processo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>File VBScript</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ias_setup.vbs</td>
<td style="border:1px solid black;">Routine utilizzate durante l'installazione del Servizio autenticazione Internet (IAS).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ias_tools.vbs</td>
<td style="border:1px solid black;">Routine utilizzate durante l'esercizio e il monitoraggio di IAS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gen_setup.vbs</td>
<td style="border:1px solid black;">Routine non specifiche di IAS o di Servizi certificati, utilizzate durante l'implementazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ca_setup.vbs</td>
<td style="border:1px solid black;">Routine utilizzate durante l'installazione dell'Autorità di certificazione (CA).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ca_monitor.vbs</td>
<td style="border:1px solid black;">Routine utilizzate dalle funzioni di monitoraggio della CA.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">constants.vbs</td>
<td style="border:1px solid black;">Costanti utilizzate dagli altri file VBS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">helper.vbs</td>
<td style="border:1px solid black;">Routine generiche utilizzate dagli altri file VBS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Pkiparams.vbs</td>
<td style="border:1px solid black;">Costanti utilizzate per definire molti dei parametri di installazione della CA.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>File vari</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">InstCAPICOM.cmd</td>
<td style="border:1px solid black;">File CMD che semplifica l'installazione di CAPICOM.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CreateShortCut.cmd</td>
<td style="border:1px solid black;">File CMD che richiama una routine dal file VBS per creare un collegamento sul desktop dell'utente. Il collegamento consente di avviare CMD.EXE con impostata la cartella di installazione degli script come directory corrente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ComputerCerts.msc</td>
<td style="border:1px solid black;">Console di gestione predefinita per la visualizzazione dei certificati nell'archivio del computer.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">AddRADIUSClient.exe</td>
<td style="border:1px solid black;">Utilità che consente di aggiungere client RADIUS a IAS dalla riga di comando. (<strong>Nota:</strong> per poter utilizzare questo strumento deve essere installato .NET Framework.)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Interop.SDOIASLib.dll</td>
<td style="border:1px solid black;">Libreria di supporto richiesta da AddRADIUSClient.exe.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Source</td>
<td style="border:1px solid black;">Cartella contenente il codice sorgente per lo strumento AddRADIUSClient.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>File criteri di gruppo</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSSWLANGPOs</td>
<td style="border:1px solid black;">Questa cartella contiene il file di definizione XML e i file di dati per i due oggetti Criteri di gruppo predefiniti forniti con questa soluzione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Documenti</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Securing Wireless LANs.rtf</td>
<td style="border:1px solid black;">File leggimi contenente lo stesso testo di questa appendice.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Struttura degli script
  
Per comprendere il funzionamento e le interazioni dei file Microsoft Visual Basic® Scripting Edition (VBScript) sono necessarie alcune spiegazioni. A differenza di molti esempi VBScript, i file script forniti con la soluzione contengono più funzioni, spesso indipendenti. Per fornire l'accesso a queste diverse funzioni, negli script viene utilizzata la funzionalità "job" (processo) di WSH. Grazie ad essa, diverse funzioni di programma indipendenti possono essere contenute in uno stesso file e da questo richiamate specificando un nome di processo come parametro dello script.
  
Vi sono due file WSF (Windows Script), che contengono l'interfaccia utente per tutte le diverse operazioni di script. I file WSF richiamano una serie di file VBS, i quali contengono il codice che in realtà svolge il lavoro di un determinato processo.
  
È possibile richiamare il processo utilizzando la seguente sintassi:
  
**cscript //job:***NomeProcessoWScriptFile*.wsf
  
dove *NomeProcesso* è il nome dell'operazione e *WScriptFile* è il nome del file di interfaccia XML per lo script. Di seguito è riportato un estratto di uno dei file WSF, in cui è definito il processo ConfigureCA:
  
```
   <?xml version="1.0" encoding="utf-8" ?> 
   <package xmlns="Windows Script Host"> 
       <job id="ConfigureCA"> 
           <description>Configures the CA registry parameters</description> 
           <script language="VBScript" src="constants.vbs" /> 
           <script language="VBScript" src="pkiparams.vbs" /> 
           <script language="VBScript" src="helper.vbs" /> 
           <script language="VBScript" src="ca_setup.vbs" /> 
           <script language="VBScript"> 
           <![CDATA[         
               Initialize True, True 
               ConfigureCA 
               CloseDown 
           ]]> 
           </script>
``` 
 
In questo estratto, la definizione del processo specifica che i file VBS, cioè constants.vbs, pkiparams.vbs, helper.vbs e ca\_setup.vbs, contengono funzioni, subroutine o dati richiesti da questo processo e, pertanto, devono essere caricati. La sezione finale specifica le funzioni di livello superiore che devono essere eseguite per avviare il processo. In questo caso queste funzioni sono Initialize (che imposta la registrazione), ConfigureCA (che esegue il processo di configurazione della CA) e CloseDown (che chiude il registro).
  
In ognuno dei file WSF, il primo processo elenca i nomi (ID) e le descrizioni di tutti i processi contenuti nel file. Pertanto, se il file WSF viene eseguito senza che sia specificato un processo specifico, viene eseguito questo processo predefinito e viene visualizzata una schermata con i nomi e le descrizioni di tutti i processi disponibili nel file. Nella tabella seguente sono elencati i processi disponibili in ognuno dei file WSF forniti con la soluzione.
  
**Tabella D.2: Elenco dei processi in MSSSetup.wsf**

<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome processo</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ListJobs</td>
<td style="border:1px solid black;">Elenca tutti i processi presenti nel file WSF.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ConfigureCA</td>
<td style="border:1px solid black;">Configura i parametri del Registro di sistema per la CA.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ConfigureTemplates</td>
<td style="border:1px solid black;">Configura i modelli dei certificati della CA.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CheckCAEnvironment</td>
<td style="border:1px solid black;">Controlla l'ambiente prima dell'installazione della CA.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">InstallCA</td>
<td style="border:1px solid black;">Installa Servizi certificati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CreateShortcut</td>
<td style="border:1px solid black;">Crea il collegamento a <strong>MSS WLAN Tools</strong> sul desktop.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ImportSecurityGPO</td>
<td style="border:1px solid black;">Importa nel dominio l'oggetto Criteri di gruppo con le impostazioni per la protezione dei server.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ImportAutoEnrollGPO</td>
<td style="border:1px solid black;">Importa nel dominio l'oggetto Criteri di gruppo con le impostazioni per la registrazione automatica dei certificati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ImportWLANClientGPO*</td>
<td style="border:1px solid black;">Importa l'oggetto Criteri di gruppo con le impostazioni per la rete WLAN</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CheckDomainNativeMode</td>
<td style="border:1px solid black;">Controlla che il dominio sia in modalità nativa.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VerifyCAInstall</td>
<td style="border:1px solid black;">Verifica che la CA sia stata installata in modo corretto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VerifyCAConfig</td>
<td style="border:1px solid black;">Verifica che la CA sia stata configurata in modo corretto.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CheckIASEnvironment</td>
<td style="border:1px solid black;">Controlla l'ambiente prima dell'installazione di IAS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">InstallIAS</td>
<td style="border:1px solid black;">Installa il Servizio autenticazione Internet sul server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CreateWLANGroups</td>
<td style="border:1px solid black;">Crea i gruppi di protezione in Active Directory®.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">AddWLANGroupMembers</td>
<td style="border:1px solid black;">Popola i gruppi di protezione con i membri corretti.</td>
</tr>
</tbody>
</table>
  
**Nota:** i processi contrassegnati con un asterisco (\*) non vengono utilizzati in questa soluzione.
  
**Tabella D.3: Elenco dei processi in MSSTools.wsf**

<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome processo</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ListJobs</td>
<td style="border:1px solid black;">Elenca tutti i processi presenti nel file WSF.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">AddRADIUSClient</td>
<td style="border:1px solid black;">Procedura interattiva per aggiungere un client RADIUS a IAS (parametri: [/path:<em>NomeFileOutput</em>]).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">AddSecRADIUSClients</td>
<td style="border:1px solid black;">Procedura interattiva per aggiungere un client RADIUS a IAS (parametri: [/path:<em>NomeFileInput</em>]).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">GenRADIUSPwd</td>
<td style="border:1px solid black;">Genera voce e password per il client RADIUS (parametri: /client:<em>NomeClient</em> /ip:<em>IndirizzoIPClient</em> [/path:<em>FileOutput</em>]).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ExportIASSettings</td>
<td style="border:1px solid black;">Esporta su file la configurazione del server IAS (parametri: [/path:<em>CartellaDestinazioneFileImpostazioni</em>]).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ImportIASSettings</td>
<td style="border:1px solid black;">Importa dai file la configurazione del server IAS (parametri: [/path:<em>CartellaFileDaImportare</em>]).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ExportIASClients</td>
<td style="border:1px solid black;">Esporta su file i client RADIUS (parametri: [/path:<em>CartellaDestinazioneFileClient</em>]).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ImportIASClients</td>
<td style="border:1px solid black;">Importa dal file i client RADIUS (parametri: [/path:<em>CartellaFileClientDaImportare</em>]).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">BackupIAS</td>
<td style="border:1px solid black;">Esegue il backup su file di tutte le impostazioni di IAS (parametri: [/path:<em>CartellaDestinazioneFileBackup</em>]).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">RestoreIAS</td>
<td style="border:1px solid black;">Ripristina da file tutte le impostazioni di IAS (parametri: [/path:<em>CartellaFileDaRipristinare</em>]).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CheckIAS</td>
<td style="border:1px solid black;">Controlla che il server IAS risponda (parametri: [/verbose]).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CheckCA</td>
<td style="border:1px solid black;">Controlla che il servizio CA risponda e che l'elenco di revoca dei certificati (CRL) sia valido (parametri: [/verbose]).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">EnableIASLockout*</td>
<td style="border:1px solid black;">Attiva il blocco degli account per IAS (parametri: [/maxdenials:<em>10</em>] [/lockouttime:<em>2880</em> (secs)]).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DisableIASLockout*</td>
<td style="border:1px solid black;">Disattiva il blocco degli account per IAS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ShowLockedOutAccounts*</td>
<td style="border:1px solid black;">Mostra gli account bloccati (e gli account con richieste di autorizzazione respinte).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ResetLockedOutAccount*</td>
<td style="border:1px solid black;">Reimposta un account bloccato (parametri: /account:<em>NomeDominio:NomeAccount</em>).</td>
</tr>
</tbody>
</table>
  
**Nota:** i processi contrassegnati con un asterisco (\*) non vengono utilizzati in questa soluzione.
  
#### Output dei processi
  
La maggior parte degli script registrano informazioni sullo stato in una finestra di console e, in molti casi, anche in un file registro. Queste informazioni possono includere informazioni sugli errori, se si sono verificati problemi durante l'esecuzione. Costituiscono un'eccezione gli script di monitoraggio, perché vengono eseguiti come processi pianificati non interattivi e non inviano output a una finestra di console.
  
Per visualizzare l'output degli script viene utilizzata una semplice finestra a scorrimento. Al termine di ogni script viene chiesto di scegliere se lasciare aperta la finestra (per riferimento) o se chiuderla.
  
Per la maggior parte delle procedure di installazione, l'output viene registrato anche in un file denominato %SystemRoot%\\debug\\MSSWLAN-Setup.log. La maggior parte delle normali attività operative non viene registrata. Vengono registrate, comunque, le attività che possono avere conseguenze importanti sulla protezione o sul funzionamento, come, ad esempio, l'importazione della configurazione di IAS. Non vengono registrate neanche le attività che possono comportare la scrittura di informazioni riservate nel registro, come l'aggiunta di client RADIUS e la creazione dei rispettivi segreti.
  
#### Esecuzione dei processi
  
Gli script possono essere eseguiti direttamente, tuttavia sono disponibili due file batch (cmd) della shell comandi che semplificano la sintassi.
  
La sintassi per l'esecuzione diretta dei file WSF è la seguente:
  
**Cscript //job:***NomeProcesso* MssSetup.wsf
  
Al suo posto è possibile utilizzare i file CMD con la seguente sintassi, più semplice:
  
**MssSetup***NomeProcesso*
  
Se si esegue il file CMD senza specificare un processo, viene eseguito il primo processo (ListJobs) del file WSF, che elenca l'ID e la descrizione di ogni processo contenuto nel file WSF.
  
Alcuni processi accettano anche ulteriori parametri. La sintassi per l'esecuzione di tali processi e le informazioni sui parametri aggiuntivi vengono trattate nei capitoli di pertinenza di questa soluzione. La sintassi generica per specificare ulteriori parametri è la seguente:
  
**MssSetup***NomeProcesso* /NomeParam:*ValoreParam*
  
*NomeParam* è il nome del parametro (ad esempio "path" o "client") e *ValoreParam* è l'impostazione per tale parametro (ad esempio "C:\\MioFile.txt" o "MioComputer"). I valori dei parametri che contengono spazi incorporati devono essere racchiusi tra virgolette (").
  
**Scarica la soluzione completa**
  
[Protezione delle reti LAN senza fili con PEAP e password](http://go.microsoft.com/fwlink/?linkid=23481)
  
[](#mainsection)[Inizio pagina](#mainsection)
