---
TOCTitle: 'Capitolo 11: Ruolo del server dei servizi certificati'
Title: 'Capitolo 11: Ruolo del server dei servizi certificati'
ms:assetid: 'a4238f44-28fc-4931-b1d5-a37d2a173284'
ms:contentKeyID: 20213211
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163135(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Capitolo 11: Ruolo del server dei servizi certificati

##### In questa pagina

[](#eiaa)[Panoramica](#eiaa)
[](#ehaa)[Impostazioni del Criterio Controllo](#ehaa)
[](#egaa)[Assegnazione dei diritti utente](#egaa)
[](#efaa)[Opzioni di protezione](#efaa)
[](#eeaa)[Impostazioni del Registro eventi](#eeaa)
[](#edaa)[Voci di registro aggiuntive](#edaa)
[](#ecaa)[Impostazioni di protezione aggiuntive](#ecaa)
[](#ebaa)[Creazione del criterio utilizzando SCW](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

In questo capitolo vengono fornite indicazioni su come aumentare la protezione dei server che eseguono Microsoft Windows Server* *2003 con Service Pack 1 (SP1) e Servizi certificati Microsoft nell'ambiente in uso. Sebbene nel capitolo siano incluse tutte le informazioni necessarie per proteggere questi tipi di server, non vengono fornite informazioni dettagliate in merito alla creazione di un'infrastruttura di Servizi certificati protetta nell'ambiente in uso o alla distribuzione di un'Autorità di certificazione (CA). Questi argomenti sono discussi in dettaglio nella documentazione di Windows* *Server* * 2003. Sono anche trattati nel *Resource Kit di Windows Server 2003* e nei white paper disponibili sul sito Web Microsoft. Per ulteriori informazioni consultare la guida correlata: [*Protezione delle reti LAN senza fili con Servizi certificati*](http://technet.microsoft.com/it-it/library/cc527055), disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14843.

Le impostazioni in questo capitolo sono configurate e applicate tramite l'opzione Criteri di gruppo. È possibile collegare un oggetto Criteri di Gruppo (Group Policy object, GPO) che integri i Criteri di base dei server membro (Member Server Baseline Policy, MSBP) alle unità organizzative appropriate (Organizational Unit, OU) che contengono i server CA al fine di offrire le modifiche delle impostazioni di sicurezza necessarie per tale ruolo server. Questo capitolo tratta solo le impostazioni dei criteri che differiscono da quelle dei criteri MSBP.

Dove possibile, queste impostazioni sono raccolte in un modello Criteri di Gruppo incrementale che sarà applicato all'OU dei server CA. Alcune delle impostazioni in questo capitolo non possono essere applicate tramite il criterio di gruppo. Vengono fornite informazioni dettagliate su come configurare manualmente queste impostazioni.

Il nome del modello di protezione del Server CA per l'ambiente EC è EC-CA Server.inf. È il modello di Server CA incrementale utilizzato per creare un nuovo GPO collegato all'OU dei server CA nell'ambiente appropriato. Le istruzioni dettagliate sono contenute nel Capitolo 2, "Meccanismi di protezione avanzata di Windows Server 2003"   per facilitare la creazione di OU e di criteri di gruppo e quindi di importare il modello di protezione idoneo in ciascun GPO.

Per le informazioni sulle impostazioni nel criterio MSBP, consultare il Capitolo 4, “Criterio di base per un server membro". Per informazioni su tutte le impostazioni di criteri predefinite, consultare la guida correlata, [*Pericoli e contromisure: impostazioni di protezione per Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275)*,*disponibile all'indirizzo http://www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx.

**Nota**: i suggerimenti per le impostazioni dei criteri per il ruolo di server Servizi certificati sono state sottoposte a test solo per l'ambiente client di organizzazione. Per questa ragione, le informazioni sugli attacchi di negazione del servizio (DoS, Denial of Service), specificate per la maggior parte degli altri ruoli del server in questa guida, non sono incluse nel presente capitolo.

È possibile installare Microsoft Internet Information Services (IIS) su alcuni dei server Servizi certificati presenti nell'ambiente in uso, in modo da consentire a tali server la distribuzione dei certificati CA e degli elenchi di revoche di certificati (CLR, Certificate Revocation List). IIS viene utilizzato anche per ospitare le pagine di registrazione Web dei server Servizi certificati, che consentono ai client diversi da Microsoft Windows di registrare i certificati. Le indicazioni fornite in questo capitolo presuppongono le conoscenze sulla corretta installazione di IIS, descritta nel capitolo 9, "Ruolo del server Web", della presente guida. Se si installa IIS sulle Autorità di certificazione in uso, il modello di configurazione della protezione sviluppato per il capitolo 9 dovrà essere applicato ai server Servizi Certificati prima di configurare le impostazioni prescritte illustrate in questo capitolo.

**Nota**: in ambienti semplificati, è possibile utilizzare il server della CA di emissione per ospitare il server Web, il certificato della CA e i punti di download CRL. Tuttavia, per migliorare la protezione delle CA, è consigliabile utilizzare un server Web separato nell'ambiente in cui si opera.

IIS è utilizzato per ospitare le pagine di registrazione del server dei certificati e per distribuire i certificati della CA e i punti di download CRL per i client non Windows. Microsoft consiglia di non installare IIS nella CA principale. Se possibile, evitare di eseguire IIS sulla CA di emissione e su eventuali CA intermedie nell'ambiente in uso. A garanzia di una maggiore protezione, è consigliabile ospitare i punti di download Web per gli elenchi di revoche di certificati e i certificati della CA su un server diverso dal server della CA. È preferibile non concedere l'accesso all'Autorità di certificazione a molti utenti dei certificati (interni ed esterni) che hanno l'esigenza di recuperare le informazioni della catena di certificati CA o degli elenchi di revoche di certificati. Tuttavia, non è possibile isolare gli utenti dalla CA se questa ospita i punti di download.

[](#mainsection)[Inizio pagina](#mainsection)

### Impostazioni del Criterio Controllo

Le impostazioni di Criteri di controllo per i server Servizi certificati nella guida sull'ambiente client di organizzazione vengono configurate mediante i criteri MSBP. Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Criteri di base dei server membro". Le impostazioni del criterio MSBP assicurano che tutte le informazioni di controllo della protezione pertinenti siano registrate su tutti i server Servizi certificati.

[](#mainsection)[Inizio pagina](#mainsection)

### Assegnazione dei diritti utente

Anche le impostazioni per l'assegnazione dei diritti utente per i server Servizi certificati nell'ambiente client di organizzazione sono configurato tramite i criteri MSBP. Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Criterio di base per un server membro". Le impostazioni dei criteri MSBP garantiscono una configurazione uniforme dell'accesso ai server Servizi certificati nell'intera organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Opzioni di protezione

La sezione Opzioni di protezione dei Criteri di gruppo viene utilizzata per attivare o disattivare le impostazioni di protezione per i computer, quali la firma digitale dei dati, i nomi di account Administrator e Guest, l'accesso alle unità disco floppy e CD-ROM, il funzionamento di installazione del driver e i prompt di accesso.

È possibile configurare le impostazioni di Opzioni di protezione in Windows Server 2003 all'interno dell'Editor oggetti Criteri di gruppo nella posizione seguente:

**Configurazione del computer\\Impostazioni di Windows\\Impostazioni di protezione\\Criteri locali\\**
**Opzioni di protezione**

La tabella seguente illustra le impostazioni delle opzioni di protezione consigliate per il ruolo del server Servizi certificati nell'ambiente Client di organizzazione. Informazioni dettagliate sulle impostazioni sono fornite nel testo che segue la tabella.

**Tabella 11.1 Impostazioni delle opzioni di protezione consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Enterprise Client</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash e firma</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
#### Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia, hash e firma
  
Questa impostazione di protezione determina se il provider di protezione TLS/SSL (Transport Layer Security/Secure Sockets Layer) supporta solo il pacchetto di crittografia TLS\_RSA\_WITH\_3DES\_EDE\_CBC\_SHA. In pratica, avere il supporto per il pacchetto di crittografia significa che il provider supporta solo il protocollo TSL come client e server (se applicabile).
  
Il provider di protezione TLS/SSL utilizza i seguenti algoritmi:
  
-   Algoritmo di crittografia 3DES (Triple Data Encryption Standard) per la crittografia del traffico TLS.
  
-   Algoritmo a chiave pubblica RSA (Rivest, Shamir, Adelman) per l'autenticazione e lo scambio delle chiavi TLS. (RSA è una tecnologia di crittografia a chiave pubblica sviluppata da RSA Data Security, Inc.)
  
-   Algoritmo SHA-1 per i requisiti di hashing TLS.
  
Per il servizio Crittografia file system (EFS, Encrypting File System), il provider di protezione TLS/SSL supporta solo l'algoritmo di crittografia Triple DES per crittografare i dati dei file archiviati nei file system Windows NTFS. Per impostazione predefinita, il servizio EFS utilizza l'algoritmo DESX per crittografare i dati dei file.
  
Se si attiva questa impostazione di criterio, i computer che svolgono questo ruolo di server nell'ambiente utilizzeranno i più potenti algoritmi disponibili per la crittografia, l'hash e la firma digitali. L'uso di questi algoritmi riduce al minimo i rischi, poiché limita la possibilità di manomissione di dati con firma o crittografia digitale da parte di utenti non autorizzati.
  
Per queste ragioni, l'impostazione **Crittografia di sistema: utilizza algoritmi FIPS compatibili per crittografia,** **hash,** **e firma** è configurata su **Abilitato** per l'ambiente Client di organizzazione.
  
**Nota**: i computer client in cui questa impostazione di criterio è abilitata non saranno in grado di comunicare mediante protocolli firmati o crittografati digitalmente con i server che non supportano questi algoritmi. I computer client di rete che non supportano questi algoritmi non potranno utilizzare i server che ne richiedono l'impiego per le comunicazioni di rete. Molti server Web basati su Apache, ad esempio, non sono configurati per il supporto di TLS.
  
Se si abilita questa impostazione, sarà necessario configurare anche Internet Explorer per l'utilizzo di TLS. Per farlo, aprire la finestra di dialogo **Opzioni Internet** dal menu **Strumenti** di Internet Explorer, fare clic sulla scheda **Avanzate** nella finestra di dialogo **Opzioni Internet**, scorrere verso la parte inferiore dell'elenco **Impostazioni**, quindi selezionare la casella di controllo **Usa TLS 1.0**. È possibile configurare l'impostazione anche mediante i criteri di gruppo o il kit per amministratori di Internet Explorer.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Registro eventi
  
Le impostazioni di registro eventi per i server Servizi certificati nell'ambiente client di organizzazione vengono configurate mediante i criteri MSBP. Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Criterio di base per un server membro".
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Voci di registro aggiuntive
  
Per il file di modello EC-CA Server.inf sono state create voci di registro aggiuntive. Queste voci non sono definite all'interno dei file dei modelli amministrativi (.adm) per l'ambiente client di organizzazione illustrato in questa guida. I file .adm definiscono le restrizioni e i criteri del sistema per le impostazioni di protezione, del desktop e della shell di Windows* *Server* *2003.
  
Le voci di registro aggiuntive sono configurate all'interno del modello di protezione per automatizzarne l'implementazione. Se i Criteri di gruppo dei Servizi certificati incrementali per questo ambiente vengono rimossi, le relative impostazioni non sono automaticamente rimosse e devono essere modificate manualmente, utilizzando uno strumento di modifica del registro di sistema come Regedt32.exe.
  
È possibile configurare le voci del registro di sistema in Windows Server 2003 all'interno dell'Editor oggetti Criteri di gruppo nella posizione seguente:
  
**MACHINE\\SYSTEM\\CurrentControlSet\\Services\\CertSvc\\Configuration**
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di protezione aggiuntive
  
Sono consigliati i seguenti ACL, che possono essere assegnati mediante i Criteri di gruppo. Tuttavia, questi ACL non sono inclusi nei modelli di protezione forniti con questa guida, poiché il percorso per il database e i registri può differire da server a server. Ad esempio, sul server Servizi certificati in uso potrebbero essere presenti le unità C:\\, D:\\ ed E:\\. Nella sezione che segue vengono fornite informazioni dettagliate sulla modalità di implementazione manuale per le impostazioni di criterio.
  
#### ACL dei file system
  
I file non protetti mediante gli elenchi di controllo di accesso (ACL, Access Control List) possono essere visualizzati, modificati o eliminati facilmente da utenti non autorizzati in grado di accedervi localmente o dalla rete. Sebbene gli elenchi ACL siano utili per proteggere questi file, la crittografia garantisce un livello più elevato di protezione e rappresenta una valida alternativa per la protezione dei file a cui deve poter accedere un solo utente.
  
Nella tabella riportata di seguito sono contenuti gli elenchi ACL dei file system per i server Servizi certificati basati su Windows* * Server* * 2003 presenti nell'ambiente client di organizzazione. In quest'ambiente, i server Servizi certificati utilizzano **D: \\CertSrv** come directory del database dei certificati e i registri del database vengono salvati nella cartella predefinita **%SystemRoot%\\system32\\CertLog.** È inoltre possibile spostare i registri dall'unità di sistema in un'unità con mirroring fisicamente separata, come **E: \\CertLog.** Le impostazioni di protezione non richiedono la separazione di database e registri in unità disco differenti, fisicamente separate, ma tale configurazione è consigliata per garantire una maggiore protezione da eventuali errori del disco e un miglioramento delle prestazioni. Per impostazione predefinita, le cartelle di installazione predefinite di Servizi certificati **%SystemRoot%\\system32\\CertLog** e **%SystemRoot%\\system32\\CertSrv** contengono gli elenchi di controllo di accesso corretti, illustrati nella seguente tabella.
  
**Tabella 11.2 ACL dei file system**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Percorso degli elenchi di controllo di accesso nell'interfaccia utente</th>
<th style="border:1px solid black;" >Enterprise Client</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">%SystemRoot%\system32\CertLog (propagazione a tutte le sottocartelle)</td>
<td style="border:1px solid black;">Amministratori (controllo totale)
SISTEMA (controllo totale)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">%SystemRoot%\system32\CertSrv (propagazione a tutte le sottocartelle)</td>
<td style="border:1px solid black;">Amministratori (controllo totale)
SISTEMA (controllo totale)
Utenti (Lettura/Esecuzione, Visualizzazione contenuto cartella e Lettura)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">D:\CertLog</td>
<td style="border:1px solid black;">Amministratori (controllo totale)
SISTEMA (controllo totale)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">D:\CertSrv</td>
<td style="border:1px solid black;">Amministratori (controllo totale)
SISTEMA (controllo totale)
Utenti (Lettura/Esecuzione, Visualizzazione contenuto cartella e Lettura)</td>
</tr>
</tbody>
</table>
 

Poiché le CA sono basate sulla protezione, per le cartelle di Servizi certificati elencate nella tabella precedente è attivata la funzione di controllo dei file. Le voci di controllo sono configurate come indicato nella tabella seguente:

**Tabella 11.3 Configurazione dei file di Servizi certificati e del controllo del Registro di sistema**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Percorso dei file o del registro di sistema</th>
<th style="border:1px solid black;" >Tipo di controllo</th>
<th style="border:1px solid black;" >Impostazione di controllo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">%SystemRoot%\system32\CertLog</td>
<td style="border:1px solid black;">Operazioni non riuscite</td>
<td style="border:1px solid black;">Everyone (Controllo completo)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">%SystemRoot%\system32\CertSrv</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Everyone (Modifica)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">D:\CertSrv</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Everyone (Modifica)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">D:\CertLog</td>
<td style="border:1px solid black;">Operazione riuscita</td>
<td style="border:1px solid black;">Everyone (Modifica)</td>
</tr>
</tbody>
</table>
  
Queste impostazioni di criterio controlleranno qualsiasi tipo di accesso non riuscito (lettura o modifica) da parte di qualsiasi utente e controllano inoltre tutte le modifiche eventualmente apportate dagli utenti.
  
#### Protezione di account noti
  
In Windows* *Server* *2003 con SP1 sono disponibili alcuni account utente predefiniti che non possono essere eliminati, ma che è possibile rinominare. Due degli account predefiniti più noti di Windows* *Server* *2003 sono Guest e Amministratore.
  
Per impostazione predefinita, l'account Guest è disabilitato nei server membri e nei controller di dominio. Questa impostazione non deve essere modificata. Molte varianti di codice nocivo utilizzano l'account predefinito Administrator nel primo tentativo di attacco a un server. È quindi necessario rinominare l'account Amministratore incorporato e modificarne la descrizione per evitare la compromissione dei server remoti da parte di pirati informatici che cercano di usare questo account noto.
  
Negli ultimi anni il valore della modifica di questa configurazione è diminuito, a seguito della comparsa di strumenti di attacco che cercano di penetrare nel server specificando l'ID di protezione dell'account Amministratore incorporato, per scoprirne il vero nome e quindi penetrare nel server. Il SID è il valore che identifica in modo univoco un utente, un gruppo, un account di computer e una sessione di accesso in una rete. Non è possibile modificare il SID di questo account incorporato. Tuttavia, i gruppi operativi possono controllare facilmente i tentativi di attacco contro questo account Amministratore, se viene rinominato con un nome esclusivo.
  
**Per proteggere gli account noti nei file server**
  
-   Rinominare gli account Amministratore e Guest e modificarne le password impostando valori lunghi e complessi in tutti i domini e server.
  
-   Utilizzare nomi e password diversi su ciascun server. Se si utilizzano gli stessi nomi account e password in tutti i domini e server, un pirata informatico in grado di accedere a un server membro potrà avvalersi dello stesso nome account e password per accedere a tutti gli altri server.
  
-   Modificare le descrizioni predefinite degli account per ostacolarne l'identificazione.
  
-   Registrare le modifiche in un posto protetto.
  
    **Nota**: per rinominare l’account Amministratore incorporato è possibile utilizzare Criteri di gruppo. Questa impostazione di criterio non è stata implementata in nessuno dei modelli di protezione forniti con questa guida, in quanto ogni organizzazione deve scegliere un nome esclusivo per questo account. Tuttavia, è possibile configurare l'impostazione **Account: rinomina account amministratore** per rinominare l'account amministratore nell'ambiente EC. Questa impostazione fa parte delle Opzioni di protezione di un GPO.
  
#### Protezione degli account di servizio
  
Se non è inevitabile, si sconsiglia di configurare un servizio per l'esecuzione in un contesto di protezione di un account di dominio. Se il server è danneggiato, è possibile ottenere facilmente le password degli account di dominio eseguendo il dump dei segreti dell'autorità di protezione locale (LSA, Local Security Authority). Per ulteriori informazioni su come proteggere gli account di servizio, consultare anche la guida [Guida alla pianificazione della protezione degli account dei servizi](http://technet.microsoft.com/it-it/library/cc170953) (in inglese) all'indirizzo www.microsoft.com/technet/security/topics/serversecurity/serviceaccount/default.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Creazione del criterio utilizzando SCW
  
Per distribuire le impostazioni di protezione necessarie è necessario utilizzare sia la Configurazione guidata impostazioni di sicurezza (SCW) sia i modelli di protezione forniti con la versione scaricabile di questa guida per creare un criterio di server.
  
Quando si crea un proprio criterio, ignorare le sezioni "Impostazioni di registro" e “Criterio di controllo”. Queste impostazioni sono fornite dai modelli di protezione per l'ambiente prescelto. Questo approccio garantisce che gli elementi di criterio forniti dai modelli abbiano la precedenza su quelli che verranno configurati da SCW.
  
Per iniziare il lavoro di configurazione, in modo da garantire che non vi siano impostazioni o software legacy di configurazioni precedenti, utilizzare un'installazione nuova del sistema operativo. Per garantire la massima compatibilità, utilizzare un hardware simile a quello usato durante la distribuzione. L'installazione nuova è chiamata *computer di riferimento.*
  
È possibile che durante le fasi di creazione del criterio di server venga eliminato il ruolo di File server dall'elenco di ruoli rilevati. Questo ruolo è comunemente configurato sui server che non lo richiedono e potrebbe essere considerato un rischio di protezione. Per abilitare il ruolo di File server per i server che lo richiedono, è possibile applicare successivamente un secondo criterio nel corso di questo processo.
  
**Per creare i criteri del server Servizi Certificati**
  
1.  Creare una nuova installazione di Windows Server 2003 con SP1 su un computer di riferimento nuovo.
  
2.  Installare il componente di Configurazione guidata impostazioni di sicurezza (SCW) sul computer tramite il Pannello di controllo, Aggiungi/rimuovi programmi, Aggiungi/rimuovi componenti di Windows.
  
3.  Aggiungere il computer al dominio, che applicherà tutte le impostazioni di protezione dalle unità operative genitore.
  
4.  Installare e configurare soltanto le applicazioni obbligatorie che saranno presenti su ogni server che condivide questo ruolo. Gli esempi comprendono servizi specifici, agenti di software e di gestione, agenti di backup su nastro e utilità antivirus o antispyware.
  
5.  Lanciare la SCW GUI, selezionare **Crea il nuovo criterio**, e scegliere il computer di riferimento.
  
6.  Verificare che i ruoli dei server rilevati siano appropriati per l'ambiente in uso, ad esempio, il ruolo Servizi certificati.
  
7.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
8.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso.
  
9.  Assicurarsi che tutti i servizi aggiuntivi richiesti per l'implementazione di base, come agenti di backup o software antivirus, siano rilevati.
  
10. Decidere come gestire i servizi non specificati nell'ambiente in uso. Per una maggior protezione, è possibile configurare questa impostazione di criterio su **Disattiva.** Verificare questa configurazione prima di implementarla nella rete di produzione, in quanto potrebbe causare problemi se i server di produzione eseguono servizi aggiuntivi che non sono duplicati sul computer di riferimento.
  
11. Accertarsi che la casella **Salta questa sezione** non sia selezionata nella sezione "Protezione di rete" e fare clic su **Avanti.** Le porte e le applicazioni identificate in precedenza vengono configurate come eccezioni per Windows Firewall.
  
12. Nella sezione "Impostazioni di registro", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti.** Queste impostazioni di criterio sono importate dal file INF fornito.
  
13. Nella sezione "Criterio di controllo", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti**. Queste impostazioni di criterio sono importate dal file INF fornito.
  
14. Allegare il modello di protezione idoneo (ad esempio, EC-CA Server.inf).
  
15. Salvare il criterio con un nome idoneo (ad esempio, Servizi certificati.xml).
  
#### Verificare il criterio utilizzando SCW
  
Dopo aver creato e salvato il criterio, Microsoft consiglia di usarlo per verificare l'ambiente di prova. Idealmente, i server di prova avranno la medesima configurazione di hardware e software dei server di produzione. Questo approccio consentirà di trovare e riparare potenziali problemi, come la presenza di servizi imprevisti richiesti da specifiche periferiche hardware.
  
Per verificare il criterio sono disponibili due opzioni. È possibile utilizzare le funzionalità di sviluppo SCW native, o implementare i criteri tramite un GPO.
  
Quando si iniziano a creare i criteri, prendere in considerazione l'utilizzo di funzionalità di sviluppo SCW native. È possibile utilizzare SCW per inviare un criterio a un unico server per volta, oppure Scwcmd per inviare il criterio a un gruppo di server. Il metodo di sviluppo nativo consente di rieseguire facilmente i criteri utilizzati da SCW. Questa funzionalità può essere molto utile quando si apportano modifiche multiple ai criteri, durante il processo di prova.
  
Il criterio è verificato per accertarsi che la sua applicazione a server di destinazione non ne comprometta le funzioni critiche. Dopo aver applicato le modifiche alla configurazione, è necessario iniziare a verificare la funzionalità di base del computer. Per esempio, se il server è configurato come un'autorità di certificazione (CA), accertarsi che i client possano richiedere e ottenere dei certificati, scaricare un elenco di revoche di certificati e così via.
  
Quando si è certi delle proprie configurazioni di criterio, è possibile utilizzare Scwcmd come mostrato nella seguente procedura per convertire i criteri in GPO.
  
Per ulteriori dettagli su come verificare i criteri di SCW, consultare la guida [Deployment Guide for the Security Configuration Wizard](http://technet.microsoft.com/en-us/library/cc776871.aspx) (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/  
library/SCWDeploying/5254f8cd-143e-4559-a299-9c723b366946.mspx* * e la guida [Security Configuration Wizard Documentation](http://go.microsoft.com/fwlink/?linkid=43450)(in inglese) all'indirizzo http://go.microsoft.com/fwlink/?linkid=43450.
  
#### Conversione e utilizzo del criterio
  
Dopo aver verificato a fondo il criterio, completare le seguenti fasi, per trasformarlo in un GPO e utilizzarlo:
  
1.  Al prompt dei comandi digitare il seguente comando:
  
    <codesnippet language displaylanguage containsmarkup="false">scwcmd transform /p:&lt;PathToPolicy.xml&gt; /g:&lt;GPODisplayName&gt;  
```
  
    e premere INVIO. Ad esempio:
  
    <codesnippet language displaylanguage containsmarkup="false">scwcmd transform /p:"C:\\Windows\\Security\\msscw\\Policies\\ Certificate Services.xml" /g:"Certificate Services Policy"  
```
  
    **Nota**: le informazioni che devono essere inserite al prompt dei comandi occupano qui più di una riga a causa delle limitazioni del display. Queste informazioni dovrebbero essere inserite tutte su una riga.
  
2.  Utilizzare la Console di gestione Criteri di gruppo per collegare il GPO appena creato all'unità operativa adeguata.
  
Se il file dei criteri di protezione di SCW contiene le impostazioni di Windows Firewall, Windows Firewall dovrà essere attivo sul computer locale, affinché questa procedura possa essere completata con successo. Per verificare che Windows Firewall sia attivo, aprire il Pannello di controllo e fare doppio clic su **Windows Firewall**.
  
Eseguire ora una prova finale per accertarsi che il GPO applichi le impostazioni desiderate. Per completare questa procedura, confermare sia l'esecuzione delle impostazioni appropriate sia l'integrità della funzionalità.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Il presente capitolo ha descritto le impostazioni di criterio che possono essere utilizzate per aumentare il livello di protezione dei server Servizi certificati che eseguono Windows Server 2003 con SP1 nell'Ambiente client di organizzazione come illustrato in questa guida. Le impostazioni sono configurate e applicate mediante un oggetto Criteri di Gruppo (GPO) che integra i criteri MSBP. Per fornire maggiore sicurezza, è possibile collegare i GPO alle unità organizzative (OU) appropriate che contengono i server Servizi certificati.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono informazioni aggiuntive sulla protezione avanzata dei server che eseguono Windows Server 2003 con SP1 e Servizi certificati.
  
-   Per un'introduzione esauriente ai concetti dell'infrastruttura a chiave pubblica (PKI, Public key Infrastructure) e alle funzioni dei servizi di certificazione di Windows 2000* *, consultare "[An Introduction to the Windows 2000 Public-Key Infrastructure](http://www.microsoft.com/technet/archive/windows2000serv/evaluate/featfunc/pkiintro.mspx)" all'indirizzo http://www.microsoft.com/technet/archive/windows2000serv/evaluate/featfunc/pkiintro.mspx (in inglese).
  
-   Per informazioni più dettagliate sulla funzionalità PKI in Windows* * Server* *2003 e Windows* *XP, consultare "[PKI Enhancements in Windows XP Professional and Windows Server 2003](http://www.microsoft.com/technet/prodtechnol/winxppro/plan/pkienh.mspx)" all'indirizzo http://www.microsoft.com/technet/prodtechnol/winxppro/plan/pkienh.mspx (in inglese).
  
-   Per ulteriori informazioni di base sui concetti principali di PKI, consultare la pagina [Public Key Infrastructure](http://technet.microsoft.com/en-us/library/cc757327.aspx) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/  
    ServerHelp/32aacfe8-83af-4676-a45c-75483545a978.mspx (in inglese).
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)
