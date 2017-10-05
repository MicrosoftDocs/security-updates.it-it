---
TOCTitle: 'Capitolo 12: Ruolo degli host Bastion'
Title: 'Capitolo 12: Ruolo degli host Bastion'
ms:assetid: 'c663fb69-d017-4f65-b812-01882f39a34b'
ms:contentKeyID: 20213212
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163137(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Capitolo 12: Ruolo degli host Bastion

##### In questa pagina

[](#ehaa)[Panoramica](#ehaa)
[](#egaa)[Impostazioni del Criterio Controllo](#egaa)
[](#efaa)[Assegnazione dei diritti utente](#efaa)
[](#eeaa)[Opzioni di protezione](#eeaa)
[](#edaa)[Impostazioni del Registro eventi](#edaa)
[](#ecaa)[Impostazioni di protezione aggiuntive](#ecaa)
[](#ebaa)[Creazione del criterio utilizzando SCW](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

Questo capitolo descrive come garantire una protezione avanzata agli host Bastion che eseguono Microsoft Windows* *Server* *2003* *con Service Pack 1 (SP1) nell'ambiente in uso. Gli host Bastion sono computer protetti, ma accessibili pubblicamente, che risiedono sul lato pubblico della rete perimetrale di una organizzazione (nota anche come DMZ, zona demilitarizzata e subnet protetta). Poiché non sono protetti da un firewall o router per l'applicazione di filtri, gli host Bastion sono completamente esposti a ogni possibile attacco. Per minimizzare la possibilità di compromissione, è necessario progettare e configurare gli host Bastion con attenzione.

Gli host Bastion vengono spesso utilizzati come server Web, server DNS (Domain Name System), server FTP (File Transfer Protocol), server SMTP (Simple Mail Transport Protocol) e server NNTP (Network News Transfer Protocol). In teoria, gli host Bastion sono dedicati all'esecuzione di una di queste funzioni, poiché più numerose sono le funzioni svolte da ciascun server, maggiore sarà la possibilità che eventuali punti di vulnerabilità vengano trascurati. È più semplice proteggere un singolo servizio su un singolo host Bastion che proteggere servizi multipli. Le organizzazioni in grado di permettersi host Bastion multipli potranno trarre significativi vantaggi da questo tipo di architettura di rete.

Gli host Bastion protetti vengono configurati in modo differente rispetto ai comuni host. Tutti i servizi, i protocolli, i programmi e le interfacce di rete non necessari vengono disattivati o rimossi e, successivamente, ciascun host Bastion viene configurato per svolgere uno specifico ruolo. Utilizzando questo sistema per la protezione avanzata degli host Bastion, è possibile limitare l'impiego di potenziali metodi di attacco.

Nelle sezioni seguenti di questo capitolo vengono descritte varie impostazioni di protezione che consentono di proteggere gli host Bastion in qualunque ambiente. I passaggi descritti in questo capitolo consentono di creare un host Bastion SMTP. Per aggiungere ulteriori funzionalità, sarà necessario modificare i file di configurazione inclusi nella guida.

#### Criteri locali degli host Bastion

I ruoli di server descritti in precedenza nella presente guida utilizzavano Criteri di gruppo per la configurazione dei server. I Criteri di gruppo non possono essere applicati ai server che fungono da host Bastion, in quanto questi ultimi sono configurati come host autonomi non appartenenti a un dominio del servizio directory Active* *Directory. Essendo esposti e non protetti dalle altre periferiche, per i server host Bastion presenti nei tre ambienti definiti in questa guida viene prescritto un solo livello di indicazioni. Le impostazioni di protezione descritte in questo capitolo si basano sui Criteri di base dei server membro (MSBP, Member Server Baseline Policy) per l'ambiente SSLF, definiti nel Capitolo 4, "Il Criterio base del server membro." Le impostazioni sono contenute in un modello di protezione che è necessario applicare ai Criteri locali degli host Bastion (BHLP, Bastion Host Local Policy) di ogni host Bastion.

**Tabella 12.1 Modelli di protezione dei server host Bastion**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">SSLF-Bastion Host.inf</td>
<td style="border:1px solid black;">SSLF-Bastion Host.inf</td>
<td style="border:1px solid black;">SSLF-Bastion Host.inf</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Criterio Controllo
  
Le impostazioni dei Criteri di controllo BHLP per gli host Bastion sono contenute nel file SSLF-Bastion Host.inf. Tali impostazioni sono identiche a quelle specificate nel file** **SSLF-Member Server Baseline.inf Per ulteriori informazioni sul criterio MSBP, consultare il Capitolo 4, "Il Criterio base del server membro". Le impostazioni BHLP assicurano che su tutti i server host Bastion siano registrate tutte le relative informazioni di controllo della protezione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Assegnazione dei diritti utente
  
Il file SSLF-Bastion Host.inf include le assegnazioni dei diritti utente BHPL per gli host Bastion. Queste impostazioni dei criteri si basano su quelle specificate nel file SSLF-Member Server Baseline.inf nel Capitolo 4, "Il Criterio base del server membro." Le informazioni contenute nella seguente tabella riassumono le differenze tra i criteri BHLP e i criteri MSBP. Nel testo che segue la tabella sono fornite informazioni dettagliate.
  
**Tabella 12.2 Impostazioni per l'assegnazione dei diritti utente consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Assegnazione diritti utente</th>
<th style="border:1px solid black;" >Impostazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nega accesso al computer dalla rete</td>
<td style="border:1px solid black;">ACCESSO ANONIMO; Amministratore incorporato; Support_388945a0; Guest; tutti gli account di servizio NON utilizzati dal sistema operativo</td>
</tr>
</tbody>
</table>
  
#### Nega accesso al computer dalla rete
  
**Nota**: ACCESSO ANONIMO, Amministratore incorporato, Support\_388945a0, Guest, e tutti gli account di servizio NON utilizzati dal sistema operativo non sono inclusi nel modello di protezione. A questi account e gruppi sono assegnati ID di protezione (SID, Security Identifier) univoci. Quindi, è necessario aggiungerli manualmente al BHLP.
  
Questa impostazione di criterio determina a quali utenti è impedito l'accesso a un computer attraverso la rete. Impedisce l'accesso a numerosi protocolli di rete, tra cui i protocolli basati su SMB, NetBIOS, CIFS (Common Internet File System), HTTP e COM+ (Component Object Model Plus). Questa impostazione di criterio prevale sull'impostazione **Accesso al computer dalla rete** nei casi in cui a un account utente siano applicati entrambi i criteri. Se si configura questo diritto utente per altri gruppi, le possibilità degli utenti di eseguire attività amministrative delegate nell'ambiente in uso potrebbero risultare limitate.
  
Nel Capitolo 4, "Il Criterio base del server membro", viene consigliato di includere il gruppo **Guests** nell'elenco degli utenti e dei gruppi che detengono questo diritto utente, allo scopo di garantire il massimo livello di protezione possibile. Tuttavia, per impostazione predefinita, l'account IUSR utilizzato per l'accesso anonimo a IIS è membro del gruppo **Guests**.
  
L'impostazione **Nega accesso al computer dalla rete** è configurata per includere ACCESSO ANONIMO, Amministratore incorporato, Support\_388945a0, Guest e tutti gli account di servizio NON utilizzati dal sistema operativo per gli host Bastion nell'ambiente SSLF definito in questa guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Opzioni di protezione
  
Le impostazioni di Opzioni di protezione BHLP per gli host Bastion sono identiche alle impostazioni specificate nel file SSLF-Member Server Baseline.inf nel Capitolo 4, "Criterio di base del server membro". Le impostazioni BHLP garantiscono una configurazione uniforme di tutte le impostazioni di Opzioni di protezione rilevanti su tutti i server host Bastion.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni del Registro eventi
  
Le impostazioni del Registro eventi BHLP per gli host Bastion sono identiche alle impostazioni specificate nel file SSLF-Member Server Baseline.inf nel Capitolo 4, "Criterio di base del server membro". Le impostazioni BHLP garantiscono una configurazione uniforme di tutte le impostazioni rilevanti del Registro eventi su tutti i server host Bastion.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di protezione aggiuntive
  
Le impostazioni di protezione applicate dal criterio BHLP migliorano significativamente la protezione dei server host Bastion. Tuttavia, esistono alcune impostazioni aggiuntive che è necessario considerare. Queste impostazioni non possono essere applicate tramite i criteri locali e devono quindi essere completate manualmente su tutti i server host Bastion.
  
#### Aggiunta manuale di gruppi di protezione univoci ad Assegnazioni diritti utente
  
Per la maggior parte delle assegnazioni di diritti utente applicate tramite i criteri MSBP, i gruppi di protezione sono specificati nei modelli di protezione allegati a questa guida. Tuttavia, vi sono alcuni account e gruppi di protezione che non possono essere inclusi nei modelli, perché i relativi ID di protezione (SID) sono specifici di singoli domini Windows* *Server* *2003. Le impostazioni per l'assegnazione dei diritti utente contenute nella seguente tabella devono essere configurate manualmente.
  
Avvertenza: nella tabella che segue sono contenuti i valori per l'account **Amministratore** incorporato. Questo account non deve essere confuso con il gruppo di protezione **Amministratori** incorporato. Se il gruppo di protezione **Administratori** viene aggiunto allo specifico diritto utente di "Accesso negato", sarà necessario connettersi localmente per correggere l'errore.
  
Inoltre, l'account Amministratore incorporato potrebbe essere stato rinominato, come consigliato nel Capitolo 4, "Il Criterio di base del server membro". Quando si aggiunge l'account Amministratore a uno qualunque dei diritti utente, assicurarsi di specificare l'account rinominato.
  
**Tabella 12.3 Assegnazioni diritti utente aggiunte manualmente**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nega accesso al computer dalla rete</td>
<td style="border:1px solid black;">Amministratore incorporato; Support_388945a0;
Guest; Tutti gli account di servizio NON utilizzati dal sistema operativo</td>
<td style="border:1px solid black;">Amministratore incorporato; Support_388945a0;
Guest; Tutti gli account di servizio NON utilizzati dal sistema operativo</td>
<td style="border:1px solid black;">Amministratore incorporato; Support_388945a0;
Guest; Tutti gli account di servizio NON utilizzati dal sistema operativo</td>
</tr>
</tbody>
</table>
 

**Importante:** l'opzione "Tutti gli account di servizio non utilizzati dal sistema operativo" comprende gli account di servizio usati per applicazioni specifiche all'interno di un'organizzazione, ma NON comprende gli account SISTEMA LOCALE, SERVIZIO LOCALE o quelli del SERVIZIO DI RETE (gli account predefiniti usati dal sistema operativo).

#### Protezione di account noti

In Windows Server 2003 sono disponibili alcuni account utente predefiniti, che non possono essere eliminati, ma che è possibile rinominare. Due degli account predefiniti più noti di Windows Server 2003 sono Guest e Amministratore.

Per impostazione predefinita, l'account Guest è disabilitato nei server membri e nei controller di dominio. Questa impostazione non deve essere modificata. Molte varianti di codice nocivo utilizzano l'account predefinito Administrator nel primo tentativo di attacco a un server. È quindi necessario rinominare l'account Amministratore incorporato e modificarne la descrizione per evitare la compromissione dei server remoti da parte di pirati informatici che cercano di usare questo account noto.

Negli ultimi anni il valore della modifica di questa configurazione è diminuito, a seguito della comparsa di strumenti di attacco che cercano di penetrare nel server specificando l'ID di protezione dell'account Amministratore incorporato, per scoprirne il vero nome e quindi penetrare nel server. Il SID è il valore che identifica in modo univoco un utente, un gruppo, un account di computer e una sessione di accesso in una rete. Non è possibile modificare il SID di questo account incorporato. Tuttavia, i gruppi operativi possono controllare facilmente i tentativi di attacco contro questo account Amministratore, se viene rinominato con un nome esclusivo.

**Per proteggere gli account noti sui server host Bastion**

-   Rinominare gli account Amministratore e Guest e modificarne le password, impostando valori lunghi e complessi in ogni server.

-   Utilizzare nomi e password diversi su ciascun server. Se si utilizzano gli stessi nomi account e password in tutti i server, un pirata informatico in grado di accedere a uno dei server potrà accedere anche a tutti gli altri.

-   Modificare le descrizioni predefinite degli account per ostacolarne l'identificazione.

-   Salvare qualsiasi modifica effettuata in un luogo sicuro.

#### Segnalazione errori

**Tabella 12.4 Impostazioni di segnalazione errori consigliate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Impostazione</th>
<th style="border:1px solid black;" >Legacy Client</th>
<th style="border:1px solid black;" >Enterprise Client</th>
<th style="border:1px solid black;" >Specialized Security – Limited Functionality</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Disabilitare la segnalazione errori di Windows</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
Questo servizio aiuta Microsoft a rintracciare e a correggere eventuali errori. È possibile configurare questo servizio in modo che vengano segnalati gli errori del sistema operativo, gli errori dei componenti di Windows o gli errori dei programmi. È disponibile soltanto in Windows XP Professional e Windows Server 2003.
  
Il **Servizio di segnalazione errori** può segnalare tali errori a Microsoft tramite Internet o una condivisione di file interni. Sebbene le relazioni di errore possono potenzialmente contenere dei dati sensibili o anche riservati, l'informativa sulla privacy di Microsoft garantisce che, nell'ambito della segnalazione di tali errori, Microsoft non utilizzerà tali dati in modo inappropriato. I dati vengono però trasmessi non crittografati su HTTP e possono essere intercettati su Internet e visualizzati da terzi.
  
L'impostazione di **disattivazione della segnalazione degli errori di Windows** regola la trasmissione di dati da parte del servizio **Segnalazione errori**.
  
È possibile configurare questa impostazione del criterio in Windows Server 2003 alla posizione seguente nell'ambito, dell'Editor oggetti Criteri di gruppo:
  
**Configurazione computer\\Modelli amministrativi\\Sistema\\Gestione comunicazioni Internet\\impostazioni di comunicazione Internet**
  
Configurare l'impostazione di disabilitazione della segnalazione degli errori di Windows su Abilitato nel BHLP per tutti e tre gli ambienti definiti in questa guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Creazione del criterio utilizzando SCW
  
Per distribuire le impostazioni di protezione necessarie è necessario utilizzare sia la Configurazione guidata impostazioni di sicurezza (SCW) sia i modelli di protezione forniti con la versione scaricabile di questa guida per creare un criterio di server.
  
Quando si crea un proprio criterio, ignorare le sezioni "Impostazioni di registro" e “Criterio di controllo”. Queste impostazioni sono fornite dai modelli di protezione per l'ambiente prescelto. Questo approccio garantisce che gli elementi di criterio forniti dai modelli abbiano la precedenza su quelli che verranno configurati da SCW.
  
Per iniziare il lavoro di configurazione, in modo da garantire che non vi siano impostazioni o software legacy di configurazioni precedenti, utilizzare un'installazione nuova del sistema operativo. Per garantire la massima compatibilità, utilizzare un hardware simile a quello usato durante la distribuzione. L'installazione nuova è chiamata *computer di riferimento.*
  
È possibile che durante le fasi di creazione del criterio di server venga eliminato il ruolo di File server dall'elenco di ruoli rilevati. Questo ruolo è comunemente configurato sui server che non lo richiedono e potrebbe essere considerato un rischio di protezione. Per abilitare il ruolo di File server per i server che lo richiedono, è possibile applicare successivamente un secondo criterio nel corso di questo processo.
  
**Per creare i criteri di un host Bastion**
  
1.  Creare una nuova installazione di Windows Server 2003 con SP1 su un computer di riferimento nuovo.
  
2.  Installare il componente di Configurazione guidata impostazioni di sicurezza (SCW) sul computer tramite il Pannello di controllo, Aggiungi/rimuovi programmi, Aggiungi/rimuovi componenti di Windows.
  
3.  Installare e configurare soltanto le applicazioni obbligatorie che saranno presenti su ogni host Bastion. Gli esempi includono le utilità antivirus o antispyware.
  
4.  Lanciare la SCW GUI, selezionare **Crea il nuovo criterio**, e scegliere il computer di riferimento.
  
5.  Verificare che i ruoli dei server rilevati siano appropriati per l'host Bastion (ad esempio, il server Web). Rimuovere tutti gli altri ruoli dei server.
  
6.  Accertarsi che le funzionalità client rilevate siano adatte all'ambiente in uso. Rimuovere tutte le funzionalità client non necessarie. Per esempio, per ridurre la superficie di attacco del server, è necessario rimuovere le funzionalità **Client di rete Microsoft** e **Client DHCP**.
  
7.  Per garantire una protezione ottimale, rimuovere tutte le funzionalità amministrative eccetto Windows Firewall. Con le opzioni aggiuntive aumenterà la gestibilità di host Bastion, ma aumenterà anche la sua superficie di attacco. Valutare attentamente i vantaggi delle opzioni che non sono essenziali per il corretto funzionamento dell'host Bastion e i potenziali rischi di protezione che queste potrebbero comportare.
  
8.  Assicurarsi che tutti i servizi aggiuntivi richiesti per l'implementazione di base, come agenti di backup o software antivirus, siano rilevati.
  
9.  Decidere come gestire i servizi non specificati nell'ambiente in uso. Per una maggior protezione, è possibile configurare questa impostazione di criterio su **Disattiva.** Verificare questa configurazione prima di implementarla nella rete di produzione, in quanto potrebbe causare problemi se i server di produzione eseguono servizi aggiuntivi che non sono duplicati sul computer di riferimento.
  
10. Accertarsi che la casella **Salta questa sezione** non sia selezionata nella sezione "Protezione di rete", quindi fare clic su **Avanti.** Le porte e le applicazioni identificate in precedenza vengono configurate come eccezioni per Windows Firewall. Deselezionare tutte le porte, eccetto quelle necessarie per il funzionamento di host Bastion.
  
11. Nella sezione "Impostazioni di registro", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti.** Queste impostazioni di criterio sono importate dal file INF fornito.
  
12. Nella sezione "Criterio di controllo", fare clic sulla casella di controllo **Salta questa sezione** e quindi su **Avanti**. Queste impostazioni di criterio sono importate dal file INF fornito.
  
13. Allegare il modello di protezione idoneo (ad esempio, SSLF-Bastion Host.inf).
  
14. Salvare il criterio con un nome idoneo (ad esempio, Bastion Host.xml).
  
#### Verificare il criterio utilizzando SCW
  
Dopo aver creato e salvato il criterio, Microsoft consiglia di usarlo per verificare l'ambiente di prova. Idealmente, i server di prova avranno la medesima configurazione di hardware e software dei server di produzione. Questo approccio consentirà di trovare e riparare potenziali problemi, come la presenza di servizi imprevisti richiesti da specifiche periferiche hardware.
  
Perché i computer nel ruolo di host Bastion non sono connessi a un dominio, è necessario applicare le impostazioni con SCW. È impossibile utilizzare l'oggetto Criteri di gruppo senza un dominio.
  
Il criterio è verificato per accertarsi che la sua applicazione a server di destinazione non ne comprometta le funzioni critiche. Dopo aver applicato le modifiche alla configurazione, è necessario iniziare a verificare la funzionalità di base del computer. Per esempio, se il server è configurato come un'autorità di certificazione (CA), accertarsi che i client possano richiedere e ottenere dei certificati, scaricare un elenco di revoche di certificati e così via.
  
Quando si è certi delle proprie configurazioni di criterio, è possibile utilizzare Scwcmd come mostrato nella seguente procedura per convertire i criteri in GPO.
  
Per ulteriori dettagli su come verificare i criteri di SCW, consultare la guida [Deployment Guide for the Security Configuration Wizard](http://technet.microsoft.com/en-us/library/cc776871.aspx) (in inglese) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/  
library/SCWDeploying/5254f8cd-143e-4559-a299-9c723b366946.mspx* * e la guida [Security Configuration Wizard Documentation](http://go.microsoft.com/fwlink/?linkid=43450)(in inglese) all'indirizzo http://go.microsoft.com/fwlink/?linkid=43450.
  
#### Implementare il criterio
  
Dopo aver verificato a fondo il criterio, completare le seguenti fasi per implementarlo:
  
1.  Lanciare la SCW GUI.
  
2.  Selezionare **Applica un criterio di protezione esistente**.
  
3.  Scegliere il file XML creato in precedenza. Ad esempio, Bastion Host.xml.
  
4.  Completare la configurazione guidata SCW per applicare le impostazioni.
  
Se il file dei criteri di protezione di SCW contiene le impostazioni di Windows Firewall, Windows Firewall dovrà essere attivo sul computer locale, affinché questa procedura possa essere completata con successo. Per verificare che Windows Firewall sia attivo, aprire il Pannello di controllo e fare doppio clic su **Windows Firewall**.
  
Eseguire ora una prova finale per accertarsi che SCW applichi le impostazioni desiderate. Per completare questa procedura, confermare sia l'esecuzione delle impostazioni appropriate sia l'integrità della funzionalità.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Poiché i server host Bastion che eseguono Windows* *Server* *2003 con SP1 non sono protetti da altre periferiche quali i firewall, sono esposti ad attacchi esterni. Per ottimizzarne la disponibilità e ridurre al minimo i rischi di violazioni, è necessario garantirne il più elevato livello di protezione possibile. I server host Bastion con un livello di protezione molto elevato limitano l'accesso solo agli account cui è stata concessa la massima fiducia e consentono solo ai servizi necessari di svolgere completamente le relative funzioni.
  
Questo capitolo ha illustrato le impostazioni e le procedure utilizzabili per garantire una protezione avanzata ai server host Bastion, rendendoli più sicuri. È possibile applicare la maggior parte delle impostazioni mediante i Criteri di gruppo locali. Inoltre, sono state fornite le linee guida per configurare e applicare le impostazioni manuali.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono informazioni aggiuntive sulla protezione avanzata dei server host Bastion che eseguono Windows Server 2003 con SP1.
  
-   Per ulteriori informazioni sulla creazione di reti private, consultare "[Firewalls and Virtual Private Networks](http://www.wiley.com/legacy/compbooks/press/0471348201_09.pdf) " di Elizabeth D. Zwicky, Simon Cooper, e Brent D. Chapman all'indirizzo www.wiley.com/legacy/compbooks/press/0471348201\_09.pdf.
  
-   Per ulteriori informazioni su firewall e protezione, consultare "[Internet Firewalls and Security – A Technology Overview](http://www.itmweb.com/essay534.htm)" di Chuck Semeria all'indirizzo www.itmweb.com/essay534.htm.
  
-   Per informazioni sul modello di difesa a più livelli, consultare la pagina "[About defense in depth](http://usmilitary.about.com/careers/usmilitary/library/glossary/d/bldef01834.htm)" all'indirizzo http://usmilitary.about.com/careers/usmilitary/library/glossary/d/bldef01834.htm.
  
-   Per informazioni sulle misure di protezione contro gli intrusi, consultare "[Intruder Detection Checklist](http://www.cert.org/tech_tips/intruder_detection_checklist.html)" di Jay Beale all'indirizzo: www.cert.org/tech\_tips/intruder\_detection\_checklist.html.
  
-   Per ulteriori informazioni su come rafforzare gli host Bastion, consultare l'articolo della SANS Info Sec Reading Room "[Hardening Bastion Hosts](http://www.sans.org/rr/whitepapers/basics/420.php)" all'indirizzo: www.sans.org/rr/whitepapers/basics/420.php.
  
-   Per informazioni sulla risoluzione dei problemi relativi allo strumento Analisi e configurazione della protezione, vedere l'articolo di Microsoft Knowledge Base "[Problems After You Import Multiple Templates Into the Security Configuration and Analysis Too](http://support.microsoft.com/?kbid=279125)" all'indirizzo http://support.microsoft.com/?kbid=279125.
  
-   Per informazioni sulla protezione dei siti, consultare il "[Site Security Handbook](http://www.faqs.org/rfcs/rfc2196.html) " all'indirizzo www.faqs.org/rfcs/rfc2196.html.
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)
