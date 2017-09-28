---
TOCTitle: 'Capitolo 5: Criterio di base per il controller di dominio'
Title: 'Capitolo 5: Criterio di base per il controller di dominio'
ms:assetid: '4247b4ee-4805-4ac4-8962-9f73c91bb80f'
ms:contentKeyID: 20213205
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163123(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Capitolo 5: Criterio di base per il controller di dominio

##### In questa pagina

[](#eiaa)[Panoramica](#eiaa)
[](#ehaa)[Impostazioni del Criterio Controllo](#ehaa)
[](#egaa)[Impostazioni di Assegnazione diritti utente](#egaa)
[](#efaa)[Opzioni di protezione](#efaa)
[](#eeaa)[Impostazioni del Registro eventi](#eeaa)
[](#edaa)[Gruppi con restrizioni](#edaa)
[](#ecaa)[Impostazioni di protezione aggiuntive](#ecaa)
[](#ebaa)[Creazione del criterio utilizzando SCW](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

La risoluzione dei problemi di protezione nel ruolo del server controller di dominio è uno dei più importanti aspetti in qualsiasi ambiente in cui siano presenti computer che eseguono Windows Server 2003 con Service Pack 1 (SP1) e utilizzano il servizio directory Active Directory. La perdita o la compromissione di un controller di dominio in un ambiente di questo tipo potrebbe danneggiare seriamente i computer client, i server e le applicazioni che si affidano ai controller di dominio per l’autenticazione, i criteri di gruppo e una directory LDAP (Lightweight Directory Access Protocol) centralizzata.

Data l’importanza che rivestono, i controller di dominio devono sempre essere custoditi in luoghi fisici protetti, accessibili esclusivamente a personale amministrativo qualificato. Quando i controller di dominio devono essere archiviati in luoghi non protetti, ad esempio filiali, è possibile effettuare alcune impostazioni di protezione per limitare i potenziali danni derivanti da pericoli fisici.

#### Criterio di base dei controller di dominio

A differenza degli altri criteri per il ruolo dei server, descritti di seguito in questa guida, i criteri di gruppo per i controller di dominio sono criteri di base come i criteri MSBP, definiti nel Capitolo 4 "Criteri di base dei server membro". Il Criterio di base dei controller di dominio (DCBP) è collegato all’unità organizzativa (OU) dei controller di dominio e ha la precedenza rispetto al Criterio controller di dominio predefinito. Le impostazioni incluse nei criteri DCBP aumentano la protezione globale di tutti i controller di dominio in qualsiasi ambiente.

Gran parte dei criteri DCBP sono una copia dei criteri MSBP. È quindi necessario consultare con attenzione il Capitolo 4, "Criteri di base dei server membro" per capire a fondo le numerose impostazioni di protezione incluse nei criteri DCBP. In questo capitolo sono documentate solo le impostazioni dei criteri DCBP che differiscono da quelle dei criteri MSBP.

I modelli di controller di dominio sono progettati esclusivamente per soddisfare le esigenze di protezione dei tre ambienti definiti in questa guida. La seguente tabella illustra i file .inf del controller di dominio allegati a questa guida per gli ambienti Legacy Client (LC), Enterprise Client (EC) e Specialized Security – Limited Functionality (SSLF). Ad esempio, il file Enterprise Client - Domain Controller.inf è un modello di protezione per l’ambiente Enterprise Client.

**Tabella 5.1 Modelli di protezione di base per i controller di dominio**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Legacy Client</p></th>
<th><p>Enterprise Client</p></th>
<th><p>Specialized Security – Limited Functionality</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>LC-Domain Controller.inf</p></td>
<td style="border:1px solid black;"><p>EC-Domain Controller.inf</p></td>
<td style="border:1px solid black;"><p>SSLF-Domain Controller.inf</p></td>
</tr>
</tbody>
</table>
  
**Nota**: le operazioni di dominio potrebbero essere notevolmente ostacolate se un oggetto Criteri di gruppo (GPO) configurato erroneamente è collegato all'unità organizzativa dei controller di dominio. Quando si importano questi modelli di protezione, è necessario prestare la massima attenzione e verificare che tutte le impostazioni di criteri importate siano corrette prima di collegare un oggetto Criteri di gruppo all’unità organizzativa dei controller di dominio.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Criterio Controllo
  
Le impostazioni dei Criteri di controllo per i controller di dominio sono le stesse specificate nei criteri MSBP. Per ulteriori informazioni, consultare il Capitolo 4, "Criteri di base dei server membro". Le impostazioni del criterio DCBP assicurano che tutte le informazioni di controllo della protezione pertinenti siano registrate sui controller di dominio.
  
**Tabella 5.2 Impostazioni consigliate dei criteri di controllo**

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
<th><p>Impostazione</p></th>
<th><p>Legacy Client</p></th>
<th><p>Enterprise Client</p></th>
<th><p>Specialized Security – Limited Functionality</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Controlla accesso al servizio directory</p></td>
<td style="border:1px solid black;"><p>Nessun controllo</p></td>
<td style="border:1px solid black;"><p>Nessun controllo</p></td>
<td style="border:1px solid black;"><p>Operazioni non riuscite</p></td>
</tr>
</tbody>
</table>
  
#### Controlla accesso al servizio directory
  
Questa impostazione del criterio determina se controllare l'accesso utente a un oggetto Active Directory al quale è associato un elenco di controllo accesso di sistema (SACL). Se si configura l'impostazione **Controlla accesso al servizio directory**, è possibile specificare se controllare gli eventi riusciti e non riusciti oppure non controllare alcun tipo di evento. Quando un utente riesce ad accedere a un oggetto Active Directory per cui è stato specificato un elenco di controllo di accesso di sistema (SACL), viene creata una voce di controllo per l'evento riuscito. Quando un utente non riesce ad accedere a un oggetto Active Directory per cui è stato specificato un elenco di controllo di accesso di sistema (SACL), viene creata una voce di controllo per l'evento non riuscito.
  
Se si abilita l'impostazione del criterio **Controlla accesso agli oggetti** e si configurano i SACL sugli oggetti della directory, verrà generato un volume elevato di voci nei registri di protezione sui controller di dominio. Si consiglia di attivare questa impostazione solo se si intendono utilizzare le informazioni generate.
  
L'impostazione **Controlla accesso al servizio directory** è configurata su **Nessun controllo** negli ambienti LC ed EC. Nell'ambiente SSLF è invece configurata per registrare gli eventi **Operazioni non riuscite**.
  
La seguente tabella contiene importanti eventi di protezione che l'impostazione **Controlla accesso al servizio directory** registra nel registro di protezione.
  
**Tabella 5.3 Eventi di accesso al servizio directory**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>ID evento</p></th>
<th><p>Descrizione evento</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>ID</p></td>
<td style="border:1px solid black;"><p>Descrizione</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>566</p></td>
<td style="border:1px solid black;"><p>Esecuzione di un'operazione su un oggetto generico.</p></td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di Assegnazione diritti utente
  
Nei criteri DCBP sono specificate diverse assegnazioni dei diritti utente per i controller di dominio. Oltre alla configurazione predefinita, sono state modificate parecchie altre impostazioni di diritti di utente per aumentare la protezione dei controller di dominio nei tre ambienti definiti in questa guida.
  
In questa sezione sono contenuti dettagli relativi alle impostazioni richieste per i criteri DCBP relative ai diritti utente, diverse da quelle presenti nei criteri MSBP. Per un riepilogo delle impostazioni richieste illustrate in questa sezione, vedere la cartella di lavoro di Excel con le impostazioni della "Windows Server 2003 Security Guide Settings" allegata alla versione scaricabile di questa guida.
  
La seguente tabella riassume le impostazioni per l'assegnazione dei diritti utente consigliate per i criteri DCBP. Nelle sezioni che seguono la tabella sono contenute ulteriori informazioni per ciascuna impostazione.
  
**Tabella 5.4 Impostazioni assegnazioni diritti utente consigliate**

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
<th><p>Impostazione</p></th>
<th><p>Legacy Client</p></th>
<th><p>Enterprise Client</p></th>
<th><p>Specialized Security – Limited Functionality</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Accesso al computer dalla rete</p></td>
<td style="border:1px solid black;"><p>Non definito</p></td>
<td style="border:1px solid black;"><p>Non definito</p></td>
<td style="border:1px solid black;"><p>Amministratori, Authenticated Users, CONTROLLER DI DOMINIO ORGANIZZAZIONE</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Aggiunta del computer al dominio</p></td>
<td style="border:1px solid black;"><p>Non definito</p></td>
<td style="border:1px solid black;"><p>Non definito</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Consenti accesso locale</p></td>
<td style="border:1px solid black;"><p>Administrators, Server Operators, Backup Operators</p></td>
<td style="border:1px solid black;"><p>Administrators, Server Operators, Backup Operators</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Consenti accesso tramite Servizi terminal</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Modifica dell'orario di sistema</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Impostazione account computer ed utente a tipo trusted per la delega</p></td>
<td style="border:1px solid black;"><p>Non definito</p></td>
<td style="border:1px solid black;"><p>Non definito</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Installa e disinstalla driver periferica</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Ripristina file e directory</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Arresto del sistema</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
<td style="border:1px solid black;"><p>Amministratori</p></td>
</tr>
</tbody>
</table>
  
#### Accesso al computer dalla rete
  
Questa impostazione determina quali utenti e gruppi sono autorizzati a connettersi al controller di dominio tramite la rete. È richiesta da tutta una serie di operazioni di rete, inclusa la replica di Active Directory tra i controller di dominio, le richieste di autenticazione ai controller di dominio dagli utenti e dai computer e per l'accesso alle cartelle condivise e alle stampanti.
  
Sebbene le autorizzazioni che sono assegnate al gruppo di protezione **Tutti** non forniscono più l'accesso agli utenti anonimi in Windows Server 2003 con SP1, i gruppi e gli account guest possono tuttavia avere l'accesso tramite il gruppo di protezione **Tutti.**
  
Per questa ragione, il gruppo di protezione **Tutti** viene rimosso dal diritto utente **Accesso al computer dalla rete** nel criterio DCBP per l'ambiente SSLF. La rimozione di questo gruppo offre una maggior protezione dagli attacchi mirati all'accesso guest al dominio. Questa impostazione del criterio è configurata su **Non definito** per gli ambienti LC ed EC.
  
#### Aggiunta del computer al dominio
  
Questa impostazione del criterio determina quali utenti possono aggiungere workstation a un determinato dominio. Per rendere effettivo questo diritto, è necessario assegnarlo all'utente quale parte del Criterio controller di dominio predefinito relativo al dominio. Un utente al quale è stato concesso questo diritto può aggiungere un massimo di 10 workstation al dominio. Gli utenti ai quali è stata assegnata l'autorizzazione per la **creazione di oggetti computer** per un'unità organizzativa o per il contenitore di computer in Active Directory, possono aggiungere un numero illimitato di computer al dominio, indipendentemente dal fatto che sia stato assegnato loro il diritto utente **Aggiunta di computer al dominio.**
  
In base all'impostazione predefinita, tutti gli utenti del gruppo **Authenticated Users** possono aggiungere fino a 10 account di computer a un dominio Active Directory. Questi nuovi account di computer vengono creati nel Contenitore computer.
  
Nelle reti di Windows, il termine *Identità di protezione* è definito come utente, gruppo o computer al quale è stato automaticamente assegnato un identificatore di protezione per controllare l'accesso alle risorse. In un dominio di Active Directory, ogni account di computer rappresenta un'identità di protezione completa con l'autorizzazione per l'autenticazione e l'accesso alle risorse del dominio. Alcune organizzazioni desiderano però limitare il numero di computer in un ambiente di Active Directory in modo che sia possibile registrarli, eseguire build e gestirli in modo coerente. Se agli utenti è consentito aggiungere computer al dominio, si ostacolerebbero le operazioni di registrazione e gestione. Gli utenti potrebbero inoltre eseguire attività più difficili da registrare in quanto possono creare altri computer di dominio non autorizzati.
  
Per questi motivi, il diritto utente **Aggiunta del computer al dominio** viene concesso solo al gruppo **Amministratori** nel criterio DCBP per l'ambiente SSLF. Questa impostazione del criterio è configurata su **Non definito** per gli ambienti LC ed EC.
  
#### Consenti accesso locale
  
Questa impostazione del criterio determina quali utenti possono avviare sessioni interattive nel controller di dominio. Gli utenti che non dispongono di questo diritto possono comunque avviare una sessione interattiva remota dal computer se è stato loro concesso il diritto utente **Consenti accesso tramite Servizi terminal**.
  
Si deve limitare il numero di account che possono accedere alle console del controller di dominio per impedire l'accesso non autorizzato ai file system e ai servizi di sistema dei controller di dominio. Un utente in grado di accedere alla console di un controller di dominio potrebbe sfruttare il sistema a fini illeciti e potenzialmente compromettere la protezione dell’intero dominio o dell'insieme di strutture.
  
Per impostazione predefinita, ai gruppi **Account Operators**, **Backup Operators**, **Print Operators** e **Server Operators** è concesso il diritto utente **Consenti accesso locale** ai controller di dominio. Per gli utenti che fanno parte di questi gruppi non dovrebbe sussistere la necessità di accedere a un controller di dominio per eseguire le proprie attività di gestione da altre workstation. I soli utenti autorizzati a svolgere attività di manutenzione sui controller di dominio dovrebbero essere gli appartenenti al gruppo **Amministratori**.
  
Se si assegna il diritto utente **Consenti accesso locale** solo al gruppo **Amministratori**, l’accesso fisico e interattivo ai controller di dominio è limitato ai soli utenti altamente attendibili, migliorando così la protezione. Per questi motivi, il diritto utente **Consenti accesso locale** è assegnato solo al gruppo **Amministratori** nel criterio DCBP per l'ambiente SSLF. Questa impostazione di criterio è configurata in modo da includere i gruppi **Server Operators** e **Backup Operators** per gli ambienti LC ed EC.
  
#### Consenti accesso tramite Servizi terminal
  
Questa impostazione di criterio determina quali utenti possono accedere al controller di dominio tramite una connessione desktop remoto.
  
Si deve limitare il numero di account che possono accedere alle console del controller di dominio per impedire l'accesso non autorizzato ai file system e ai servizi di sistema dei controller di dominio. Un utente in grado di accedere alla console di un controller di dominio mediante Servizi terminal potrebbe sfruttare il computer e potenzialmente compromettere la protezione di un intero dominio o di un insieme di strutture.
  
Se si assegna il diritto utente **Consenti accesso tramite Servizi terminal** solo al gruppo **Amministratori**, l’accesso interattivo ai controller di dominio è limitato ai soli utenti altamente attendibili, migliorando così la protezione. Per questo motivo, il diritto utente **Consenti accesso tramite Servizi terminal** viene consesso solo al gruppo **Amministratori** nel criterio DCBP per tutti e tre gli ambienti definiti in questa guida. Sebbene per accedere a un controller di dominio mediante Servizi terminal siano per impostazione predefinita necessari i diritti amministrativi, configurando questa impostazione di criterio si contribuisce a proteggere il sistema da azioni dannose o effettuate inavvertitamente che potrebbero compromettere la rete.
  
Come ulteriore misura di protezione, nei criteri DCBP il diritto utente **Consenti accesso tramite Servizi terminal** è negato all’account Amministratore predefinito. Questa configurazione impedisce inoltre a utenti malintenzionati di tentare di penetrare remotamente nel controller di dominio utilizzando l’account Amministratore predefinito. Per ulteriori dettagli su questa impostazione di criterio, vedere il Capitolo 4: "Criteri di base dei server membro".
  
#### Modifica dell'orario di sistema
  
Questa impostazione del criterio determina quali utenti possono regolare l'orario dell'orologio interno del computer. Non è però necessario disporre di questo diritto per modificare il fuso orario o altre caratteristiche di visualizzazione dell’orario di sistema.
  
La sincronizzazione dell’orario di sistema è molto importante per il funzionamento di Active Directory. I processi di generazione di ticket di autenticazione e replica di Active Directory, utilizzati dal protocollo di autenticazione Kerberos, fanno affidamento sulla sincronizzazione dell’orario fra tutti gli ambienti.
  
Un orologio del controller di dominio non sincronizzato con l'orario di sistema di altri controller di dominio che fanno parte dell’ambiente può interferire con il funzionamento dei servizi del dominio. Consentendo di modificare l’orario di sistema esclusivamente agli amministratori, si riduce al minimo la possibilità che un controller di dominio venga configurato con un orario di sistema non corretto.
  
Il diritto di modificare l’orario di sistema sui controller di dominio è concesso al gruppo **Server Operators** per impostazione predefinita. A causa dei problemi che potrebbero essere causati dalla modifica errata di un orologio del controller di dominio dai membri di questo gruppo, il diritto utente **Modifica dell'orario di sistema** è assegnato nel criterio DCBP solo al gruppo **Amministratori** per tutti e tre gli ambienti definiti in questa guida.
  
Per ulteriori informazioni sul servizio di sistema Ora di Microsoft Windows , vedere la [documentazione tecnica del servizio Ora di Windows](http://technet.microsoft.com/en-us/library/cc773061.aspx)all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/TechRef/  
a0fcd250-e5f7-41b3-b0e8-240f8236e210.mspx.
  
#### Impostazione account computer ed utente a tipo trusted per la delega
  
Questa impostazione del criterio determina quali utenti possono modificare l'impostazione **Trusted per la delega** su un oggetto utente o computer in Active Directory. La delega dell’autenticazione è una funzionalità utilizzata dalle applicazioni client/server a più livelli. Essa consente a un servizio front-end, tipo un'applicazione, di utilizzare le credenziali di un client per l’autenticazione a un servizio back-end, come un database. Per permettere questa autenticazione, sia il client sia il server devono essere eseguiti con account considerati trusted per la delega.
  
Un abuso di questo diritto utente potrebbe consentire ad utenti non autorizzati di impersonare altri utenti in rete. Un pirata informatico potrebbe sfruttare questo diritto utente per accedere alle risorse di rete spacciandosi per un utente diverso, il che potrebbe rendere più difficile ricostruire cosa sia accaduto dopo un’infrazione della protezione.
  
Assegnare il privilegio utente **Impostazione account computer ed utente a tipo trusted per la delega** solo al gruppo **Amministratori** sui controller di dominio per l'ambiente SSLF. Questa impostazione del criterio è configurata su **Non definito** per gli ambienti LC ed EC.
  
**Nota**: nonostante il Criterio controller di dominio predefinito assegni questo diritto al gruppo **Amministratori**, in base ai criteri DCBP questo diritto utente viene applicato esclusivamente nell’ambiente SSLF, solo perché era in origine basato sui criteri MSBP. I criteri MSBP assegnano a questo diritto il valore Null.
  
#### Installa e disinstalla driver periferica
  
Questa impostazione del criterio determina quali utenti possono caricare e scaricare driver di periferiche ed è necessaria per caricare e scaricare le periferiche Plug and Play.
  
La gestione negligente di driver della periferica sui controller di dominio espone a errori o a codici dannosi che possono avere un impatto negativo sui controller di dominio. Se il criterio DCBP limita gli account che possono caricare e scaricare i driver di periferica solo agli utenti più attendibili, si riducono al minimo le possibilità che i driver di periferica siano utilizzati per compromettere i controller del dominio.
  
Per impostazione predefinita, il diritto utente **Installa e disinstalla driver periferica** è assegnato al gruppo **Print Operators.** Come indicato in precedenza, non si consiglia la creazione di condivisioni di stampa sui controller di dominio, dato che elimina la necessità di concedere ai **Print Operators** la capacità di caricare e scaricare i driver di periferica. Di conseguenza, il diritto utente **Installa e disinstalla driver periferica** è assegnato solo al gruppo **Amministratori** nel criterio DCBP per tutti e tre gli ambienti definiti in questa guida.
  
#### Ripristina file e directory
  
Questa impostazione di criterio determina se gli utenti possono aggirare le autorizzazioni per file e directory durante il processo di ripristino. Qualsiasi identità di protezione valida potrebbe essere impostata come proprietario di un oggetto.
  
Un account in grado di ripristinare file e directory nel file system di un controller di dominio può facilmente modificare i file eseguibili. Utenti malintenzionati potrebbero sfruttare questa funzionalità non solo per rendere inutilizzabile un controller di dominio, ma anche per compromettere la protezione di un dominio o di un intero insieme di strutture.
  
Per impostazione predefinita, il diritto utente **Ripristino di file e directory** è assegnato a gruppi di **Server Operators** e **Backup Operators**. Negando questo diritto utente a tali gruppi e concedendolo esclusivamente al gruppo **Amministratori**, si riducono le probabilità che un controller di dominio venga compromesso da modifiche non corrette del file system. Di conseguenza, il diritto utente **Ripristino di file e directory** è assegnato solo al gruppo **Amministratori** nel criterio DCBP per tutti e tre gli ambienti definiti in questa guida.
  
#### Arresto del sistema
  
Questa impostazione del criterio determina quali utenti possono arrestare il computer locale
  
Utenti malintenzionati aventi la facoltà di arrestare i controller di dominio potrebbero facilmente iniziare un attacco di tipo DoS (Denial of Service) che potrebbe avere un grave impatto sull’intero dominio o insieme di strutture. Un pirata informatico potrebbe sfruttare questo diritto utente per sferrare un attacco con elevazione dei privilegi su un account di controller di dominio al riavvio dei servizi. Qualora l’attacco con elevazione dei privilegi a un controller di dominio abbia successo può compromettere la protezione del dominio o dell’intera struttura.
  
Per impostazione predefinita, il diritto utente **Arresto del sistema** è assegnato ai gruppi **Administrators**, **Server Operators**, **Print Operators** e **Backup Operators**. Negli ambienti protetti, nessuno di questi gruppi, ad eccezione del gruppo **Amministratori**, necessita di questo diritto per eseguire attività di amministrazione. Per questo motivo, il diritto utente **Arresto del sistema** viene concesso solo al gruppo **Amministratori** nel criterio DCBP per tutti e tre gli ambienti definiti in questa guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Opzioni di protezione
  
Molte delle impostazioni di opzioni di protezione per i controller di dominio sono le stesse specificate nei criteri MSBP. Per ulteriori informazioni, vedere il Capitolo 4, "Criteri di base dei server membro". Nella sezione seguente vengono descritte le differenze tra i criteri MSBP e DCBP.
  
#### Impostazioni dei controller di dominio
  
**Tabella 5.5 Opzioni di protezione: consigli per l'impostazione dei controller di dominio**

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
<th><p>Impostazione</p></th>
<th><p>Legacy Client</p></th>
<th><p>Enterprise Client</p></th>
<th><p>Specialized Security – Limited Functionality</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>consenti agli operatori dei server di pianificare le operazioni</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>requisiti di accesso al server LDAP</p></td>
<td style="border:1px solid black;"><p>Non definito</p></td>
<td style="border:1px solid black;"><p>Non definito</p></td>
<td style="border:1px solid black;"><p>Richiedi firma</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>rifiuta cambio password account computer</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>
</tbody>
</table>
  
##### Controller di dominio: consente agli operatori dei server di pianificare le operazioni
  
Questa impostazione di criterio determina se ai membri dei gruppi **Server Operators** è consentito inviare processi mediante la funzione di pianificazione AT.
  
L'impostazione **Controller di dominio: consente agli operatori dei server di pianificare le operazioni** è configurata su **Disabilitata** nel criterio DCBP per tutti e tre gli ambienti definiti in questa guida. Gli effetti della configurazione di questa impostazione di criterio dovrebbero essere minimi per la maggior parte delle organizzazioni. Gli utenti, compresi quelli del gruppo **Server Operators**, potranno comunque creare processi tramite l’Utilità di pianificazione, ma tali processi verranno eseguiti nel contesto dell’account con cui l'utente è stato autenticato quando ha impostato il processo.
  
**Nota**: è possibile modificare l’account del servizio AT selezionando un account diverso dall’account SISTEMA LOCALE. Per modificare l'account, aprire Utilità di sistema, fare clic su **Operazioni pianificate** e quindi fare clic sulla cartella **Accessori**. Scegliere **Account servizio AT** dal menu **Avanzate**.
  
##### Controller di dominio: requisiti di accesso al server LDAP
  
Questa impostazione di criterio determina se il server LDAP richiede una firma prima di negoziare con i client LDAP. In assenza di firma digitale o crittografia, il traffico di rete è soggetto ad attacchi di tipo "man-in-the-middle", vale a dire attacchi in cui un intruso prende possesso dei pacchetti inviati dal server al client e li modifica prima di inoltrarli al client. Di conseguenza, nel caso di un server LDAP, un pirata informatico potrebbe indurre un client a prendere decisioni sulla base di record falsi della directory LDAP.
  
Se tutti i controller di dominio eseguono Windows 2000 o Windows Server 2003, configurare l'impostazione **Controller di dominio: requisiti di accesso al server LDAP** su **Richiedi firma.** Altrimenti lasciare le impostazioni di questo criterio configurate su **Non definito**, configurazione del criterio DCBP per gli ambienti LC ed EC. Questa impostazione del criterio è configurata su **Richiedi firma** nel criterio DCBP per l'ambiente SSLF dato che tutti i computer in questo ambiente eseguono o Windows 2000 o Windows Server 2003.
  
##### Controller di dominio: rifiuta cambio password account computer
  
Questa impostazione del criterio determina se i controller di dominio rifiuteranno o meno delle richieste dai computer membri di modificare le password dell'account del computer. Se si attiva questa impostazione di criterio su tutti i controller di dominio di un dominio, non sarà possibile modificare le password degli account del computer sui membri del dominio che saranno così più suscettibili agli attacchi.
  
Di conseguenza l'impostazione **Controller di dominio: rifiuta cambio password account computer** è configurata su **Disabilitata** nel criterio DCBP per tutti e tre gli ambienti definiti in questa guida.
  
#### Impostazioni di protezione di rete
  
**Tabella 5.6 Opzioni di protezione: consigli per le impostazioni di protezione di rete**

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
<th><p>Impostazione</p></th>
<th><p>Legacy Client</p></th>
<th><p>Enterprise Client</p></th>
<th><p>Specialized Security – Limited Functionality</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>non memorizzare il valore hash di LAN Manager al prossimo cambio di password</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>
</tbody>
</table>
  
#### Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password
  
Questa impostazione di protezione determina se il valore hash di LAN Manager (LM) per la nuova password verrà memorizzato al successivo cambio di password. L'hash di LAN Manager è relativamente debole e vulnerabile agli attacchi, rispetto all'hash di Windows NT crittograficamente più forte.
  
Per questa ragione, il criterio DCBP abilita l'impostazione **Protezione di rete: non memorizzare il valore hash di LAN Manager al prossimo cambio di password** in tutti e tre gli ambienti definiti in questa guida.
  
**Nota**: quando questa impostazione è abilitata, i sistemi operativi più vecchi e alcune applicazioni di terzi potrebbero non funzionare. Per esempio, Windows 95 e Windows 98 non funzioneranno se non è stato installato il componente Active Directory Client Extension. Inoltre, se si abilita questa impostazione del criterio, tutti gli account dovranno modificare la password.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Registro eventi
  
Le impostazioni del registro eventi dei controller di dominio sono uguali a quelle specificate nei criteri MSBP. Per ulteriori informazioni, consultare il Capitolo 4, "Criteri di base dei server membro". Le impostazioni del criterio DCBP assicurano che tutte le informazioni di controllo della protezione pertinenti siano registrate sui controller di dominio.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Gruppi con restrizioni
  
Come descritto nel capitolo precedente, le impostazioni **Gruppi con restrizioni** consentono di gestire l'appartenenza dei gruppi in Windows Server 2003 con SP1 mediante il criterio di gruppo Active Directory. Esaminare prima di tutto le esigenze dell'organizzazione per determinare quali gruppi devono essere limitati. Per i controller di dominio, i gruppi **Server Operators** e **Backup Operators** sono limitati in tutti e tre gli ambienti definiti in questa guida. Anche se i membri dei gruppi **Server Operators** e **Operatori backup** godono di un accesso più limitato rispetto ai membri del gruppo **Amministratori**, dispongono pur tuttavia di funzionalità potenti.
  
**Nota:** se l'organizzazione utilizza uno qualsiasi di questi gruppi, controllare attentamente la loro appartenenza e non implementare le istruzioni relative all'impostazione dei **Gruppi con restrizioni**. Se l'organizzazione aggiunge utenti al gruppo Utenti server, potrebbe essere utile implementare le autorizzazioni opzionali del file system, descritte nella sezione “Protezione del File System" al capitolo precedente.
  
**Tabella 5.7 Consigli per gruppi con restrizioni**

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
<th><p>Gruppo locale</p></th>
<th><p>Legacy Client</p></th>
<th><p>Enterprise Client</p></th>
<th><p>Specialized Security – Limited Functionality</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Backup Operators</p></td>
<td style="border:1px solid black;"><p>Nessun membro</p></td>
<td style="border:1px solid black;"><p>Nessun membro</p></td>
<td style="border:1px solid black;"><p>Nessun membro</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Server Operators</p></td>
<td style="border:1px solid black;"><p>Nessun membro</p></td>
<td style="border:1px solid black;"><p>Nessun membro</p></td>
<td style="border:1px solid black;"><p>Nessun membro</p></td>
</tr>
</tbody>
</table>
  
L'impostazione **Gruppi con restrizioni** può essere configurata in Windows Server 2003 con SP1 nel seguente percorso tramite l'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione\\Gruppi con restrizioni\\**
  
Gli amministratori possono configurare i gruppi con restrizioni per un oggetto Criteri di gruppo (GPO) aggiungendo il gruppo desiderato direttamente al nodo **Gruppi con restrizioni** dello spazio dei nomi del GPO.
  
Quando viene posta la restrizione su un gruppo, è possibile definirne i membri e altri gruppi a cui esso appartiene. Se non si definiscono questi membri del gruppo, esso mantiene tutte le restrizioni. Solo utilizzando i modelli di protezione è possibile imporre restrizioni ai gruppi.
  
**Per visualizzare o modificare l'impostazione Gruppi con restrizioni**
  
1.  Aprire la console Modelli di protezione.
  
    **Nota**: la console Modelli di protezione non è inclusa per impostazione predefinita nel menu Strumenti di amministrazione. Per aggiungerla, avviare la Microsoft Management Console (mmc.exe) e aggiungere il componente aggiuntivo Modelli di protezione.
  
2.  Fare doppio clic sulla directory del file di configurazione, quindi sul file di configurazione.
  
3.  Fare doppio clic sulla voce **Gruppi con restrizioni**.
  
4.  Fare clic con il pulsante destro del mouse su **Gruppi con restrizioni**.
  
5.  Selezionare **Aggiungi gruppo**.
  
6.  Fare clic sul pulsante **Sfoglia,** quindi su **Percorsi,** scegliere i percorsi che si desiderano sfogliare e quindi fare clic su **OK.**
  
    **Nota**: in genere questa procedura pone al primo posto della lista un computer locale.
  
7.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare** digitare il nome del gruppo e fare clic sul pulsante **Controlla nomi**.
  
    – oppure –
  
    Fare clic sul pulsante **Avanzate**, quindi su **Trova** per elencare tutti i gruppi disponibili.
  
8.  Selezionare il gruppo a cui imporre le restrizioni, quindi scegliere **OK**.
  
9.  Scegliere **OK** per chiudere la finestra di dialogo **Aggiungi gruppi**.
  
In questa guida sono stati eliminati tutti i membri, utenti e gruppi, dei **Server Operators** e **Backup Operators**, per limitarli completamente in entrambi gli ambienti. Per l'ambiente SSLF sono stati inoltre eliminati tutti i membri del gruppo **Utenti desktop remoto**. Microsoft consiglia la restrizione per tutti i gruppi incorporati che l'organizzazione non ha intenzione di utilizzare.
  
**Nota**: Risulta molto semplice la configurazione dei Gruppi con restrizioni descritta in questa sezione. Le versioni di Windows XP con SP1 e SP2 come pure Windows Server 2003 supportano progetti più complessi. Per ulteriori informazioni consultare l'articolo della Microsoft Knowledge Base, “[Updates to Restricted Groups ("Member of") Behavior of User-Defined Local Groups](http://support.microsoft.com/kb/810076/it)” all'indirizzo http://support.microsoft.com/kb/810076/it.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di protezione aggiuntive
  
In questa sezione sono descritte le modifiche manuali da apportare ai criteri DCBP e le impostazioni e contromisure aggiuntive che non è possibile implementare mediante i criteri di gruppo.
  
#### Aggiunta manuale di gruppi di protezione univoci ad Assegnazioni diritti utente
  
La maggior parte delle assegnazioni di diritti utente applicate tramite i criteri DCBP, sono specificate in modo esauriente nei modelli di protezione allegati a questa guida. Tuttavia, vi sono alcuni account e gruppi di protezione che non possono essere inclusi nei modelli, perché i relativi ID di protezione (SID) sono specifici di singoli domini Windows Server 2003. Le assegnazioni dei diritti utente che devono essere configurati manualmente sono specificate nella seguente tabella.
  
Avvertenza: nella tabella che segue sono contenuti i valori per l'account **Amministratore** incorporato. Questo account non deve essere confuso con il gruppo di protezione **Amministratori** incorporato. Se si aggiunge il gruppo di protezione **Amministratori** a uno qualunque dei diritti di accesso utente negati, indicati di seguito, sarà necessario accedere a livello locale per correggere l'errore.
  
Inoltre, se è stato rinominato l'account Amministratore incorporato in base ai consigli del Capitolo 4, "Criteri di base dei server membro", verificare di scegliere l'account amministratore appena rinominato quando si aggiunge l'account a uno qualunque dei diritti di accesso utente negati.
  
**Tabella 5.8 Assegnazioni diritti utente aggiunte manualmente**

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
<th><p>Impostazione</p></th>
<th><p>Legacy Client</p></th>
<th><p>Enterprise Client</p></th>
<th><p>Specialized Security – Limited Functionality</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Nega accesso al computer dalla rete</p></td>
<td style="border:1px solid black;"><p>Amministratore incorporato; Support_388945a0;</p>
<p>Guest; Tutti gli account di servizio NON utilizzati dal sistema operativo</p></td>
<td style="border:1px solid black;"><p>Amministratore incorporato; Support_388945a0;</p>
<p>Guest; Tutti gli account di servizio NON utilizzati dal sistema operativo</p></td>
<td style="border:1px solid black;"><p>Amministratore incorporato; Support_388945a0;</p>
<p>Guest; Tutti gli account di servizio NON utilizzati dal sistema operativo</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Nega accesso come processo batch</p></td>
<td style="border:1px solid black;"><p>Support_388945a0 e Guest</p></td>
<td style="border:1px solid black;"><p>Support_388945a0 e Guest</p></td>
<td style="border:1px solid black;"><p>Support_388945a0 e Guest</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Nega accesso tramite Servizi terminal</p></td>
<td style="border:1px solid black;"><p>Amministratore incorporato; tutti gli account di servizio NON utilizzati dal sistema operativo</p></td>
<td style="border:1px solid black;"><p>Amministratore incorporato; tutti gli account di servizio NON utilizzati dal sistema operativo</p></td>
<td style="border:1px solid black;"><p>Amministratore incorporato; tutti gli account di servizio NON utilizzati dal sistema operativo</p></td>
</tr>
</tbody>
</table>
  
**Importante**: l'opzione “Tutti gli account di servizio NON utilizzati dal sistema operativo" comprende gli account di servizio usati per applicazioni specifiche all'interno di un'organizzazione, ma NON comprende gli account SISTEMA LOCALE, SERVIZIO LOCALE o quelli del SERVIZIO DI RETE (gli account predefiniti usati dal sistema operativo).
  
#### Servizi directory
  
I controller di dominio che eseguono Windows Server 2003 con SP1 archiviano i dati della directory e gestiscono le interazioni fra utente e dominio, compresi i processi di accesso, l'autenticazione e la ricerca nelle directory.
  
##### Spostamento dei dati: database e file di registro di Active Directory
  
Per mantenere l'integrità e l'attendibilità della directory, è essenziale proteggere il database Active Directory e i rispettivi file di registro.
  
Lo spostamento dei file ntds.dit, edb.log e temp.edb dalla loro posizione predefinita può essere d’aiuto per nasconderli da potenziali pirati informatici, qualora venga compromesso un controller di dominio. Spostando i file dal volume di sistema a un disco fisico separato si otterrà un ulteriore vantaggio, dato che si miglioreranno le prestazioni del controller di dominio.
  
Per queste ragioni, la presente guida raccomanda di spostare il database e i file di registro Active Directory dai controller di dominio a un volume di disco con striping o con striping/mirroring che non contenga il sistema operativo. Questi file dovrebbero essere spostati per tutti e tre gli ambienti definiti in questa guida.
  
##### Ridimensionamento dei file di registro di Active Directory
  
Registrare un quantitativo idoneo di informazioni per controllare in modo efficace e mantenere l'integrità, attendibilità e disponibilità di Active Directory. Sono necessarie informazioni provenienti da tutti i controller di dominio all'interno dello stesso ambiente.
  
Per sostenere questo sforzo è possibile aumentare la dimensione massima dei file di registro. Ulteriori informazioni sul registro consentiranno agli amministratori di eseguire controlli utili nel caso di attacchi da parte di pirati informatici.
  
In questa guida si consiglia di aumentare la dimensione massima del Servizio directory e del Servizio replica file passando dai 512 KB predefiniti a 16 MB per i controller di dominio nei tre ambienti qui definiti.
  
##### Utilizzo di Syskey
  
Nei controller di dominio, le informazioni sulla password sono memorizzate in Active Directory. Non è insolito che un programma software per la violazione delle password venga diretto contro il database di Gestione account di protezione (SAM) o i servizi directory per accedere alle password degli account utente.
  
L’utilità chiave di sistema (Syskey) fornisce un’ulteriore difesa contro i programmi software per la violazione delle password non in linea. Syskey utilizza tecniche di crittografia avanzata per proteggere le informazioni sulla password di account, archiviate nel database SAM o nel controller di dominio.
  
**Tabella 5.9 Modalità Syskey**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Opzione Chiave di sistema</p></th>
<th><p>Livello di protezione</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Modalità 1: Password generata dal sistema, Archivia chiave di avvio a livello locale</p></td>
<td style="border:1px solid black;"><p>Protezione</p></td>
<td style="border:1px solid black;"><p>Come chiave del sistema viene utilizzata una chiave casuale generata dal computer e nel computer locale viene archiviata una versione crittografata della chiave. Questa opzione offre una crittografia avanzata delle informazioni relative alle password contenute nel Registro di sistema e consente di riavviare il computer senza che l’amministratore debba immettere una password o inserire un disco.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Modalità 2: Password generata amministratore, Avvia mediante password</p></td>
<td style="border:1px solid black;"><p>Media protezione</p></td>
<td style="border:1px solid black;"><p>Come chiave del sistema viene utilizzata una chiave casuale generata dal computer e nel computer locale viene archiviata una versione crittografata della chiave. La chiave è ulteriormente protetta da una password scelta dall’amministratore. Quando il computer esegue la sequenza di avvio iniziale, agli utenti viene richiesta la password per la chiave di sistema. La password per la chiave di sistema non viene memorizzata in una posizione qualsiasi del computer.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Modalità 3: Password generata dal sistema, Archivia chiave di avvio su disco floppy</p></td>
<td style="border:1px solid black;"><p>Massima protezione</p></td>
<td style="border:1px solid black;"><p>Viene utilizzata una chiave casuale generata dal computer che viene quindi memorizzata su un disco floppy. Per avviare il sistema è necessario il disco floppy contenente la chiave di sistema, da inserire durante la sequenza di avvio quando viene visualizzato il relativo prompt. La chiave di sistema non viene memorizzata in una posizione qualsiasi del computer.</p></td>
</tr>
</tbody>
</table>
  
Syskey è abilitato in tutti i server con Windows Server 2003 con SP1 in Modalità 1 (chiave offuscata). Dal punto di vista della protezione, questa configurazione potrebbe sembrare utile. Ma Syskey in Modalità 1 consente a un pirata informatico di leggere e alterare il contenuto della directory, rendendo il controller di dominio più vulnerabile ad attacchi da parte di un pirata informatico con accesso fisico.
  
Esistono molte ragioni per raccomandare di utilizzare Syskey in Modalità 2 (password della console) o Modalità 3 (memorizzazione su floppy della password Syskey) per qualunque controller di dominio esposto a pericoli di protezione fisica. I requisiti operativi di riavvio dei controller di dominio tendono tuttavia a rendere di difficile utilizzo le Modalità 2 e 3 di Syskey. Per avvantaggiarsi dalla maggiore protezione fornita da queste modalità Syskey, nell’ambiente devono essere implementati processi operativi corretti, per far fronte ai requisiti specifici di disponibilità dei controller di dominio.
  
La logistica della password Syskey o la gestione del disco floppy possono risultare alquanto complesse, soprattutto nelle succursali di uffici. Per esempio, potrebbe essere costoso dover chiedere a uno dei direttori di filiale o al personale amministrativo locale di recarsi in ufficio alle 3 del mattino, per immettere le password o inserire un disco floppy in modo da consentire ad altri utenti di accedere al sistema. Delle soluzioni così costose possono rendere molto difficoltosa la stipulazione di accordi SLA (Service Level Agreements) ad alta disponibilità.
  
Alternativamente, se si decide di consentire al personale IT centralizzato di fornire remotamente la password Syskey, è necessario altro hardware. Alcuni fornitori di hardware dispongono di soluzioni aggiuntive per accedere remotamente alle console dei server.
  
E per finire, la perdita della password Syskey o del disco floppy renderebbero impossibile il riavvio del controller di dominio. Non esistono metodi per ripristinare un controller di dominio se va persa la password Syskey o il disco floppy. Qualora ciò succedesse, sarebbe necessario ricostruire il controller di dominio.
  
Attuando procedure operative corrette, Syskey è in grado di offrire un maggiore livello di protezione, particolarmente efficace per le informazioni di directory riservate, presenti nei controller di dominio. Per questi motivi si raccomanda di utilizzare la Modalità 2 o 3 di Syskey per i controller di dominio che si trovano in luoghi sprovvisti di una protezione fisica adeguata dell’archiviazione. Questa configurazione si applica anche ai controller di dominio in tutti e tre gli ambienti descritti in questa guida.
  
**Creazione o aggiornamento di una chiave di sistema:**
  
1.  Fare clic su **Start**, scegliere **Esegui**, digitare **syskey** e quindi scegliere **OK**.
  
2.  Fare clic su **Crittografia abilitata**, quindi scegliere **Aggiorna**.
  
3.  Selezionare l**’opzione desiderata, quindi scegliere** OK.
  
#### DNS integrati in Active Directory
  
Microsoft consiglia l'uso di DNS integrati in Active Directory nei tre ambienti definiti in questa guida. Questo consiglio è in parte dettato dal fatto che l'integrazione della zona Active Directory semplifica la protezione di un'infrastruttura DNS in un ambiente che utilizza DNS integrati in Active Directory piuttosto che in uno che non ne fa uso.
  
##### Protezione dei server DNS
  
È essenziale per proteggere i server DNS in qualsiasi ambiente Active Directory. Nelle sezioni riportate di seguito sono contenuti vari consigli e spiegazioni su come proteggere i server DNS.
  
Quando un server DNS viene attaccato, uno dei possibili scopi del pirata informatico è controllare le informazioni DNS inviate in risposta alle query dei client DNS. Se un pirata informatico controlla queste informazioni, i client possono essere inconsapevolmente reindirizzati a computer non autorizzati. Lo spoof IP e la manipolazione della cache poisoning DNS sono esempi di questo tipo di attacco.
  
Nello spoof IP, all’indirizzo IP di un utente autorizzato viene inviata una trasmissione allo scopo di ottenere l’accesso a un computer o rete. La manipolazione della cache è un attacco in cui un host non autorizzato trasmette nella cache di un server DNS informazioni false riguardanti un altro host. Ne risulta il reindirizzamento dei client a computer non autorizzati.
  
Se ai computer client è concesso di comunicare con i computer non autorizzati, i computer non autorizzati possono tentare di accedere alle informazioni sui computer client.
  
Non tutti gli attacchi si concentrano sullo spoof dei server DNS. Alcuni attacchi DoS possono alterare i record DNS in server DNS legittimi per fornire indirizzi non validi in risposta alle query dei client. Facendo in modo che il server risponda con indirizzi non validi, i client e i server non possono individuare le risorse necessarie al loro funzionamento, ad esempio controller di dominio, server Web o condivisioni di file.
  
Per questi motivi, i router usati nei tre ambienti definiti in questa guida sono configurati in modo da ignorare i pacchetti IP sui quali è stato eseguito lo spoof per garantire che gli indirizzi IP dei server DNS non possano essere oggetto di spoof da parte di altri computer.
  
##### Configurazione degli aggiornamenti dinamici protetti
  
Il servizio **client DNS** di Windows Server 2003 con SP1 supporta gli aggiornamenti DNS dinamici, che consentono ai computer client di aggiungere record DNS direttamente nel database. Se un server DNS dinamico è configurato per accettare gli aggiornamenti non protetti, un pirata informatico potrebbe trasmettere aggiornamenti dannosi o non autorizzati da un computer client che supporta il protocollo di aggiornamento dinamico DNS.
  
Come minimo, un pirata informatico potrebbe aggiungere voci false al database DNS. Nella peggiore delle ipotesi, un pirata informatico può sovrascrivere o eliminare le voci legittime nel database DNS. Un pirata informatico che si comporti in questo modo potrebbe far sorgere una delle seguenti condizioni:
  
-   **Indirizzamento dei client a controller di dominio non autorizzati**. un server DNS compromesso potrebbe essere stato alterato in modo da restituire l’indirizzo di un server non autorizzato quando un client inoltra una query DNS alla ricerca dell’indirizzo di un controller di dominio. In seguito, mediante l’utilizzo di altri attacchi non correlati ai DNS, il client potrebbe essere “ingannato” in modo da passare informazioni protette al server non autorizzato.
  
-   **Risposta con indirizzi non validi a query DNS**. Client e server sono incapaci di individuarsi a vicenda. Se i client non individuano i server, non possono accedere alla directory. Se i controller di dominio non sono in grado di individuare altri controller di dominio, la replica delle directory si arresta, creando una condizione DoS che potrebbe influire sugli utenti di un insieme di strutture.
  
-   **Creazione di una condizione DoS**. Lo spazio sul disco di un server può essere esaurito da un enorme file di zona riempito con record fittizi o con un gran numero di voci che rallentano la replica.
  
L’utilizzo di aggiornamenti DNS protetti garantisce che le richieste di registrazione vengano elaborate solo se sono inviate da client validi che fanno parte dell'insieme di strutture di Active Directory. In tal modo si limita notevolmente la possibilità che un pirata informatico possa compromettere l’integrità di un server DNS.
  
Per questi motivi, i server DNS di Active Directory nei tre ambienti definiti in questa guida sono configurati in modo da accettare solo aggiornamenti dinamici protetti.
  
##### Limitazione dei trasferimenti di zona a sistemi autorizzati
  
Data l’importanza del ruolo rivestito dalle zone nei DNS, queste dovrebbero essere disponibili da più di un server DNS della rete per offrire una disponibilità adeguata e la tolleranza agli errori durante la risoluzione delle query riguardanti i nomi. Perché ulteriori server possano ospitare una zona sono necessari i trasferimenti di zona per replicare e sincronizzare tutte le copie della zona utilizzate da ogni server configurato per ospitare la zona.
  
Un server DNS non configurato in modo da limitare i richiedenti dei trasferimenti di zona è inoltre vulnerabile alle richieste di trasferimento dell’intera zona DNS a chiunque lo richieda. Questo trasferimento può essere realizzato facilmente con strumenti quali Nslookup.exe. Questi strumenti sono in grado di esporre l’intero set di dati DNS del dominio, inclusi elementi come gli host che fungono da controller di dominio, i server Web integrati nella directory o i database di Microsoft SQL Server.
  
Per questi motivi, i server DNS integrati in Active Directory nei tre ambienti definiti in questa guida sono configurati in modo da consentire i trasferimenti di zona, limitando però i computer che possono fare le richieste di trasferimento.
  
##### Ridimensionamento del registro eventi e del registro del servizio DNS
  
Registrare un quantitativo idoneo di informazioni per controllare in modo efficace e mantenere il servizio DNS. Sono necessarie informazioni provenienti da tutti i controller di dominio all'interno dello stesso ambiente.
  
Si possono aumentare le dimensioni massime del file di registro del servizio DNS, che consentirà gli amministratori di eseguire le revisioni importanti in caso di un attacco.
  
In questa guida si consiglia di aumentare la dimensione massima del file di registro del servizio DNS ad almeno 16 MB sui controller di dominio nei tre ambienti qui definiti. Inoltre, verificare che l'opzione **Sovrascrivi eventi se necessario** del servizio DNS sia selezionata per aumentare al massimo la quantità delle voci di registro conservate.
  
#### Protezione di account noti
  
In Windows Server 2003 sono disponibili alcuni account utente predefiniti, che non possono essere eliminati, ma che è possibile rinominare. Due degli account predefiniti più noti di Windows Server 2003 sono Guest e Amministratore.
  
Per impostazione predefinita, l'account Guest è disabilitato nei server membro e nei controller di dominio. Questa impostazione non deve essere modificata. Molte varianti di codice nocivo utilizzano l'account predefinito Administrator nel primo tentativo di attacco a un server. È quindi necessario rinominare l'account Amministratore incorporato e modificarne la descrizione per evitare la compromissione dei server remoti da parte di pirati informatici che cercano di usare questo account noto.
  
Negli ultimi anni il valore della modifica di questa configurazione è diminuito, a seguito della comparsa di strumenti di attacco che cercano di penetrare nel server specificando l'ID di protezione dell'account Amministratore incorporato, per scoprirne il vero nome e quindi penetrare nel server. Il SID è il valore che identifica in modo univoco un utente, un gruppo, un account di computer e una sessione di accesso in una rete. Non è possibile modificare il SID di questo account predefinito. Tuttavia, i gruppi operativi possono controllare facilmente i tentativi di attacco contro questo account Amministratore, se viene rinominato con un nome esclusivo.
  
Per proteggere gli account noti su domini e server, completare la procedura seguente:
  
-   Rinominare gli account Amministratore e Guest e modificarne le password impostando valori lunghi e complessi in tutti i domini e server.
  
-   Utilizzare nomi e password diversi su ciascun server. Se si utilizzano gli stessi nomi account e password in tutti i domini e server, un pirata informatico che riuscisse ad accedere a un server membro potrebbe avvalersi dello stesso nome account e password per accedere a tutti gli altri server.
  
-   Modificare le descrizioni predefinite degli account per ostacolarne l'identificazione.
  
-   Salvare qualsiasi modifica effettuata in un luogo sicuro.
  
    **Nota**: per rinominare l'account Amministratore incorporato è possibile utilizzare i Criteri di gruppo. Questa impostazione di criterio non è stata implementata in nessuno dei modelli di protezione forniti con questa guida, in quanto ogni organizzazione deve scegliere un nome esclusivo per questo account. Tuttavia, è possibile configurare le impostazioni di **Account: Rinomina l'impostazione di account amministratore** per rinominare gli account amministratore in tutti e tre gli ambienti che sono definiti in questa guida. Questa impostazione fa parte delle Opzioni di protezione di un GPO.
  
#### Protezione degli account di servizio
  
Se non è inevitabile, si sconsiglia di configurare un servizio per l'esecuzione in un contesto di protezione di un account di dominio. Se il server è danneggiato, è possibile ottenere facilmente le password degli account di dominio eseguendo il dump dei segreti dell'autorità di protezione locale (LSA, Local Security Authority). Per ulteriori informazioni su come proteggere gli account di servizio, consultare anche [la Guida alla pianificazione della protezione degli account dei servizi](http://www.microsoft.com/technet/security/topics/serversecurity/serviceaccount/default.mspx) all'indirizzo www.microsoft.com/technet/security/topics/serversecurity/serviceaccount/default.mspx.
  
#### Impostazioni di Servizi terminal
  
**Tabella 5.10 Impostazioni di Servizi terminal consigliate**

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
<th><p>Impostazione predefinita</p></th>
<th><p>Legacy Client</p></th>
<th><p>Enterprise Client</p></th>
<th><p>Specialized Security – Limited Functionality</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Imposta livello di crittografia connessione client</p></td>
<td style="border:1px solid black;"><p>Alto</p></td>
<td style="border:1px solid black;"><p>Alto</p></td>
<td style="border:1px solid black;"><p>Alto</p></td>
</tr>
</tbody>
</table>
  
L'impostazione **Imposta livello di crittografia connessione client** determina il livello di crittografia applicato alle connessioni client dei Servizi terminal nell'ambiente in uso. L'opzione di livello **Alto**, che utilizza la crittografia a 128 bit, impedisce a un pirata informatico di infiltrarsi nelle sessioni di Servizi terminal utilizzando un analizzatore di pacchetti. Alcune versioni precedenti dei client di Servizi terminal non supportano questo livello di crittografia elevato. Se nella rete sono presenti client di questo tipo, impostare il livello di crittografia della connessione in modo da inviare e ricevere dati al livello di crittografia più elevato tra quelli supportati dal client.
  
Per i tre ambienti di protezione qui definiti configurare l'impostazione **Imposta livello di crittografia connessione client** su **Abilitato** e selezionare la crittografia di **Livello alto** nel criterio DCBP.
  
È possibile configurare questa impostazione del criterio in Windows Server 2003 alla posizione seguente nell'ambito, dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Componenti di Windows\\**  
**Servizi terminal \\Crittografia e protezione**
  
I tre livelli di crittografia disponibili sono descritti nella tabella seguente:
  
**Tabella 5.11 Livelli di crittografia di Servizi terminal**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Livello di crittografia</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Alto</p></td>
<td style="border:1px solid black;"><p>Codifica i dati inviati dal client al server e dal server al client con crittografia avanzata a 128 bit. Utilizzare questo livello quando il Terminal Server è in esecuzione in un ambiente dove si trovano solo client a 128 bit (ad esempio client di Connessione desktop remoto). I client che non supportano questo livello di crittografia non possono stabilire la connessione.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Compatibile con client</p></td>
<td style="border:1px solid black;"><p>Codifica i dati inviati fra client e server basandosi sulla forza massima della chiave supportata dal client. Utilizzare questo livello se il Terminal Server è in esecuzione in un ambiente con client misti o legacy.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Basso</p></td>
<td style="border:1px solid black;"><p>Codifica i dati inviati fra client e server con crittografia a 56 bit.</p>
<p><strong>Importante</strong>: i dati inviati dal server al client non sono crittografati.</p></td>
</tr>
</tbody>
</table>
<p> </p>

#### Segnalazione errori

**Tabella 5.12 Impostazioni di segnalazione errori consigliate**

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
<th><p>Impostazione</p></th>
<th><p>Legacy Client</p></th>
<th><p>Enterprise Client</p></th>
<th><p>Specialized Security – Limited Functionality</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Disabilitare la segnalazione errori di Windows</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>
</tbody>
</table>
  
Questo servizio aiuta Microsoft a rintracciare e a correggere eventuali errori. È possibile configurare questo servizio in modo che vengano segnalati gli errori del sistema operativo, gli errori dei componenti di Windows o gli errori dei programmi. È disponibile soltanto in Windows XP Professional e Windows Server 2003.
  
Il **Servizio di segnalazione errori** può segnalare tali errori a Microsoft tramite Internet o una condivisione di file interni. Sebbene le relazioni di errore possono potenzialmente contenere dei dati sensibili o anche riservati, l'informativa sulla privacy di Microsoft garantisce che, nell'ambito della segnalazione di tali errori, Microsoft non utilizzerà tali dati in modo inappropriato. I dati vengono però trasmessi non crittografati su HTTP e possono essere intercettati su Internet e visualizzati da terzi.
  
L'impostazione di disattivazione della segnalazione degli errori di Windows regola la trasmissione di dati da parte del servizio **Segnalazione errori**.
  
È possibile configurare questa impostazione del criterio in Windows Server 2003 alla posizione seguente nell'ambito, dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Sistema\\Gestione comunicazioni Internet\\impostazioni di comunicazione Internet**
  
Abilitare l'impostazione di disattivazione della segnalazione degli errori di Windows nel DCBP per tutti e tre gli ambienti definiti in questa guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Creazione del criterio utilizzando SCW
  
Per distribuire le impostazioni di protezione necessarie bisogna utilizzare sia la Configurazione guidata impostazioni di sicurezza (SCW) sia i modelli di protezione forniti con la versione scaricabile di questa guida per creare un criterio di base del controller di dominio.
  
Quando si crea un proprio criterio, ignorare le sezioni "Impostazioni di registro" e “Criterio di controllo”. Le impostazioni di questi criteri sono definite dai modelli di protezione per l'ambiente prescelto. Questo metodo serve a garantire che gli elementi di criterio forniti dai modelli abbiano la precedenza su quelli che verranno configurati da SCW.
  
Per iniziare il lavoro di configurazione, in modo da garantire che non vi siano impostazioni o software legacy di configurazioni precedenti, utilizzare un'installazione nuova del sistema operativo. Per garantire la massima compatibilità, installare il sistema operativo su un computer simile a quello usato durante lo sviluppo. L'installazione nuova è chiamata *computer di riferimento.*
  
**Creazione dei Criteri di base del controller di dominio**
  
Per creare i Criteri di base del controller di dominio è necessario usare un computer configurato quale controller di dominio. È possibile utilizzare un controller di dominio esistente o creare un computer di riferimento e utilizzare lo strumento Dcpromo per trasformare il computer in un controller di dominio. Tuttavia, la maggior parte delle organizzazioni non vuole aggiungere un controller di dominio al proprio ambiente di produzione perché può violare i loro criteri di protezione. Se si utilizza un controller di dominio esistente, fare attenzione a non applicarvi nessuna impostazione con SCW o a non modificarne la configurazione.
  
1.  Installare il componente di Configurazione guidata impostazioni di sicurezza (SCW) sul computer tramite il Pannello di controllo, Aggiungi/rimuovi programmi, Aggiungi/rimuovi componenti di Windows.
  
2.  Lanciare la SCW GUI, selezionare **Crea il nuovo criterio**, e scegliere il computer di riferimento.
  
3.  Accertarsi che i ruoli rilevati siano adatti all'ambiente in uso. Non rimuovere il ruolo di File server, dato che è necessario per il corretto funzionamento dei controller di dominio.
  
4.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
5.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
    **Nota**: se l'ambiente in uso contiene dei controller di dominio in siti multipli, verificare che sia selezionata l'opzione **Replica di Active Directory con posta**.
  
6.  Assicurarsi che tutti i servizi aggiuntivi richiesti per l'implementazione di base, come agenti di backup o software antivirus, siano rilevati.
  
7.  Decidere come gestire i servizi non specificati nell'ambiente in uso. Per una maggior protezione, è possibile configurare questa impostazione di criterio su **Disattiva.** Verificare questa configurazione prima di utilizzarla nella rete di produzione, in quanto potrebbe causare problemi se i server di produzione eseguono servizi aggiuntivi che non sono duplicati sul computer di riferimento.
  
8.  Accertarsi che la casella **Salta questa sezione** non sia selezionata nella sezione "Protezione di rete" e fare clic su **Avanti.** Le porte e le applicazioni identificate in precedenza vengono configurate come eccezioni per Windows Firewall.
  
    **Nota:** verificare che l'opzione **Ports for System RPC Applications** sia selezionata.
  
9.  Nella sezione "Impostazioni di registro", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti.** Queste impostazioni di criterio sono importate dal file INF fornito.
  
10. Nella sezione "Criterio di controllo", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti**. Queste impostazioni di criterio sono importate dal file INF fornito.
  
11. Allegare il modello di protezione idoneo (ad esempio, EC-Domain Controller.inf).
  
12. Salvare il criterio con un nome idoneo (ad esempio, Domain Controller.xml**)**.
  
#### Verificare il criterio utilizzando SCW
  
Dopo aver creato e salvato il criterio, Microsoft consiglia di usarlo per verificare l'ambiente di prova. Idealmente, i server di prova avranno la medesima configurazione di hardware e software dei server di produzione. Questo approccio consentirà di trovare e riparare potenziali problemi, come la presenza di servizi imprevisti richiesti da specifiche periferiche hardware.
  
Per verificare il criterio sono disponibili due opzioni. È possibile utilizzare le funzionalità di sviluppo SCW native, o usare i criteri tramite un GPO.
  
Quando si iniziano a creare i criteri, prendere in considerazione l'utilizzo di funzionalità di sviluppo SCW native. È possibile utilizzare SCW per inviare un criterio a un unico server per volta, oppure Scwcmd per inviare il criterio a un gruppo di server. Il metodo di sviluppo nativo offre la possibilità di rieseguire facilmente i criteri utilizzati dallo SCW. Questa funzionalità può essere molto utile quando si apportano modifiche multiple ai criteri, durante il processo di prova.
  
Il criterio è verificato per accertarsi che la sua applicazione a server di destinazione non ne comprometta le funzioni critiche. Dopo aver applicato le modifiche alla configurazione, è necessario iniziare a verificare la funzionalità di base del computer. Per esempio, se il server è configurato come un'autorità di certificazione (CA), verificare che i client possano richiedere e ottenere certificati, scaricare un elenco di revoche di certificati e così via.
  
Quando si è certi delle proprie configurazioni di criterio, è possibile utilizzare Scwcmd come mostrato nella seguente procedura per convertire i criteri in GPO.
  
Per ulteriori dettagli su come verificare i criteri di SCW, consultare la [Guida di sviluppo per la configurazione guidata delle impostazioni di sicurezza](http://technet.microsoft.com/en-us/library/cc776871.aspx) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/  
library/SCWDeploying/5254f8cd-143e-4559-a299-9c723b366946.mspx* * e la [Documentazione di configurazione guidata impostazioni di sicurezza](http://go.microsoft.com/fwlink/?linkid=43450)all'indirizzo http://go.microsoft.com/fwlink/?linkid=43450.
  
#### Conversione e utilizzo del criterio
  
Dopo aver verificato a fondo il criterio, completare le seguenti fasi, per trasformarlo in un GPO e utilizzarlo:
  
1.  Al prompt dei comandi digitare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">scwcmd transform /p:&lt;PathToPolicy.xml&gt; /g:&lt;GPODisplayName&gt;  
```
  
    e premere INVIO. Ad esempio:
  
    <codesnippet language displaylanguage containsmarkup="false">scwcmd transform /p:"C:\\Windows\\Security\\msscw\\Policies\\Domain Controller.xml" /g:"Domain Controller Policy"  
```
  
    **Nota**: le informazioni che devono essere inserite al prompt dei comandi occupano qui più di una riga a causa delle limitazioni del display. Queste informazioni dovrebbero essere inserite tutte su una riga.
  
2.  Utilizzare la Console di gestione Criteri di gruppo per collegare il GPO appena creato all'unità operativa Controller di dominio e verificare di spostarlo sopra al Criterio controller di dominio predefinito in modo che riceva la massima priorità.
  
Se il file dei criteri di protezione di SCW contiene le impostazioni di Windows Firewall, Windows Firewall dovrà essere attivo sul computer locale, affinché questa procedura possa essere completata con successo. Per verificare che Windows Firewall sia attivo, aprire il Pannello di controllo e fare doppio clic su **Windows Firewall**.
  
Ricordare che la replica del GPO appena creato in tutti i controller di dominio potrebbe richiedere un certo periodo di tempo, soprattutto negli ambienti con controller di dominio in siti multipli. Dopo aver verificato che il GPO è stato replicato in modo corretto, eseguire una prova finale per accertarsi che il GPO applichi le impostazioni desiderate. Per completare questa procedura, confermare sia l'esecuzione delle impostazioni appropriate sia l'integrità della funzionalità.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questo capitolo spiega come aumentare la protezione dei server dei controller di dominio che eseguono Windows Server 2003 con SP1 in ciascuno dei tre ambienti definiti in questa guida. La maggior parte delle impostazioni di criterio trattate sono state configurate e applicate mediante Criteri di gruppo. I Criteri di base controller di dominio (DCBP) correlati al Criterio controller di dominio predefinito erano collegati all'OU del Controller di dominio.
  
Le impostazioni del criterio DCBP aumenteranno la protezione complessiva dei controller di dominio in qualsiasi ambiente. Utilizzando due oggetti Criteri di gruppo per proteggere i controller di dominio è possibile conservare l’ambiente predefinito e semplificare la risoluzione dei problemi.
  
Alcune delle impostazioni trattate non possono essere applicate mediante i Criteri di gruppo. Per queste impostazioni, sono stati forniti dei dettagli per la configurazione manuale.
  
Dopo aver configurato il livello di protezione dei controller di dominio, è possibile aumentare anche quello di altri ruoli di server. I successivi capitoli di questa guida si concentrano su come ottenere parecchi altri ruoli di server specifici.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono informazioni aggiuntive sulla protezione avanzata dei server che eseguono Windows Server 2003 con SP1.
  
-   Per informazioni sulle Prescriptive Architecture Guides di Microsoft Systems Architecture: Enterprise Data Center vedere la pagina [MSA EDC Prescriptive Architecture Guide](http://www.microsoft.com/resources/documentation/msa/edc/all/solution/en-us/pak/pag/default.mspx) all'indirizzo www.microsoft.com/resources/documentation/msa/edc/all/solution/  
    en-us/pak/pag/default.mspx.
  
-   Per le informazioni su come attivare l'accesso anonimo a Active Directory, vedere l'articolo di Microsoft Knowledge Base "[Descrizione di scelte di autorizzazioni Dcpromo](http://support.microsoft.com/kb/257988/it)" all'indirizzo http://support.microsoft.com/kb/257988/it.
  
-   Per ulteriori informazioni sulle restrizioni per Active Directory, vedere l'articolo di Microsoft Knowledge Base "[Restricting Active Directory replication traffic to a specific por](http://support.microsoft.com/kb/224196/it)t" all'indirizzo http://support.microsoft.com/kb/224196/it.
  
-   Per ulteriori informazioni sulla limitazione del traffico di replica FRS, vedere l'articolo di Microsoft Knowledge Base "[How to restrict FRS replication traffic to a specific static port](http://support.microsoft.com/kb/319553/it)" all'indirizzo http://support.microsoft.com/kb/319553/it.
  
-   Per ulteriori informazioni sul servizio Ora di Microsoft Windows , vedere la [documentazione tecnica del servizio Ora di Windows](http://technet.microsoft.com/en-us/library/cc773061.aspx)all'indirizzo http://www.microsoft.com/technet/prodtechnol/windowsserver2003/library/TechRef  
    a0fcd250-e5f7-41b3-b0e8-240f8236e210.mspx.
  
-   Per ulteriori informazioni sullo spoofing IP vedere l'articolo “[Introduction to IP Spoofing](http://www.giac.org/practical/gsec/victor_velasco_gsec.pdf)” all'indirizzo www.giac.org/practical/gsec/Victor\_Velasco\_GSEC.pdf.
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)
