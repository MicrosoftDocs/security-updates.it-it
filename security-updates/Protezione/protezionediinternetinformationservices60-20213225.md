---
TOCTitle: 'Protezione di Internet Information Services 6.0'
Title: 'Protezione di Internet Information Services 6.0'
ms:assetid: 'b53beabd-912c-4f53-80fb-acff5d74df20'
ms:contentKeyID: 20213225
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc875829(v=TechNet.10)'
---

Protezione di Internet Information Services 6.0
===============================================

##### In questa pagina

[](#ehaa)[Introduzione](#ehaa)  
[](#egaa)[Prima di iniziare](#egaa)  
[](#efaa)[Riduzione della superficie di attacco del server Web](#efaa)  
[](#eeaa)[Configurazione degli account](#eeaa)  
[](#edaa)[Configurazione della protezione per file e directory](#edaa)  
[](#ecaa)[Protezione di siti Web e directory virtuali](#ecaa)  
[](#ebaa)[Configurazione di Secure Sockets Layer (SSL) nel server Web](#ebaa)  
[](#eaaa)[Informazioni correlate](#eaaa)  

### Introduzione

I server Web sono soggetti spesso a vari tipi di attacchi alla protezione. Alcuni di questi attacchi sono in grado di causare un danno significativo ai beni aziendali, alla produttività e alle relazioni con i clienti e comunque tutti gli attacchi provocano spiacevoli e frustanti disagi. La protezione dei server Web è fondamentale per il successo delle attività aziendali.

In questo documento viene descritto come avviare il processo di protezione di un server Web con Internet Information Services (IIS) 6.0 in esecuzione sul sistema operativo Microsoft Windows Server 2003, Standard Edition. Nella presente sezione sono innanzitutto descritte alcune delle minacce più diffuse che attentano alla protezione dei server Web. Successivamente, vengono fornite istruzioni che consentono di rafforzare la protezione dei server Web contro gli attacchi descritti.

Di seguito sono elencate le modifiche apportate a IIS 6.0 rispetto alle versioni precedenti, che rendono possibile un approccio più fattivo ed efficace contro utenti malintenzionati e aggressori:

-   IIS 6.0 non viene installato per impostazione predefinita quando si installa Windows Server 2003, Standard Edition.

-   Alla prima installazione di IIS 6.0, il server Web utilizza o visualizza solo pagine Web statiche (HTML), caratteristica che riduce i rischi connessi al funzionamento con contenuto dinamico o eseguibile.

-   Il Servizio Pubblicazione sul Web (servizio WWW) è l'unico servizio abilitato per impostazione predefinita quando IIS 6.0 viene installato per la prima volta. Gli altri servizi specifici necessari possono essere abilitati all'occorrenza.

-   ASP e ASP.NET sono disabilitati per impostazione predefinita quando IIS 6.0 viene installato per la prima volta.

Per una protezione aggiuntiva, in IIS 6.0 tutte le impostazioni predefinite per la configurazione della protezione sono conformi o più restrittive rispetto a quelle dello strumento di blocco IIS. Quest'ultimo, denominato IIS Lockdown Tool, è progettato allo scopo di ridurre la superficie di attacco dei server Web disabilitando le funzionalità inutilizzate e può essere eseguito con le versioni precedenti di IIS. Per ulteriori informazioni su questo strumento, consultare il documento sulla protezione di Internet Information Services 5.0 e 5 nel [Security Guidance Kit](http://www.microsoft.com/windowsserver2003/techinfo/overview/iis.mspx), disponibile nell'Area download Microsoft all'indirizzo www.microsoft.com/windowsserver2003/techinfo/overview/iis.mspx (in inglese).

Poiché in base alle impostazioni predefinite di IIS 6.0 numerose funzionalità comunemente utilizzate nei servizi Web sono disabilitate, nel presente documento viene spiegato come configurare funzionalità aggiuntive nel server Web riducendone al tempo stesso l'esposizione a potenziali attacchi.

In questo documento sono riportate le indicazioni seguenti per aumentare la protezione del server Web:

-   Riduzione della superficie di attacco del server Web o del livello di esposizione del server a potenziali pirati informatici.

-   Configurazione di account utente e di gruppo per l'accesso anonimo.

-   Protezione di file e directory da accessi non autorizzati.

-   Protezione di siti Web e directory virtuali da accessi non autorizzati.

-   Configurazione di Secure Sockets Layer (SSL) nel server Web.

**Importante**: tutte le istruzioni dettagliate incluse in questo documento sono state formulate in base al menu predefinito visualizzato quando si fa clic sul pulsante **Start**. Se il menu Start è stato modificato, la procedura potrebbe essere leggermente diversa.

Al completamento delle procedure descritte in questo documento, il server Web sarà in grado di funzionare con contenuto dinamico, nella forma di pagine ASP, ma sarà comunque protetto in modo significativo dai tipi di attacchi elencati di seguito, che a volte minacciano i server Internet:

-   Attacchi di tipo profiling, mirati alla raccolta di informazioni relative al sito Web, che possono essere limitati bloccando le porte inutilizzate e disattivando i protocolli non necessari.

-   Attacchi di tipo "Denial of Service" (DoS) che inondano il server di richieste e che possono essere neutralizzati applicando patch di protezione e aggiornamenti software.

-   Accesso non autorizzato da parte di utenti privi delle corrette autorizzazioni, che spesso può essere sventato configurando le autorizzazioni Web e NTFS.

-   Esecuzione arbitraria di codice dannoso nel server Web, che può essere ridotta al minimo impedendo l'accesso ai comandi e agli strumenti di sistema.

-   Acquisizione di privilegi più elevati, che consente a un utente malintenzionato di utilizzare un account con privilegi elevati per eseguire programmi. È possibile contenere i danni adottando il principio del privilegio minimo per account utente e di servizio.

-   Danni dovuti a virus, worm e trojan horse, che possono essere limitati disabilitando le funzionalità non necessarie, utilizzando account con privilegi minimi e applicando immediatamente le patch di protezione più recenti.

**Nota**: poiché la protezione di un server Web è un processo complesso e continuo, non è possibile garantire una protezione completa.

#### Obiettivo del documento

Nel presente documento vengono fornite informazioni introduttive che consentono di adottare le prime misure necessarie per la configurazione di un server Web più protetto. Tuttavia, per fornire al server Web la massima protezione possibile è indispensabile comprendere il funzionamento delle applicazioni che vi vengono eseguite. In questo documento non verranno fornite informazioni sulla configurazione della protezione specifica delle applicazioni.

[](#mainsection)[Inizio pagina](#mainsection)

### Prima di iniziare

In questa sezione vengono illustrati i prerequisiti del sistema e le caratteristiche del server Web che sono oggetto del presente documento.

#### Requisiti di sistema

I requisiti di sistema del server Web utilizzato come esempio in questo documento sono i seguenti:

-   Nel server è in esecuzione Windows Server 2003, Standard Edition.

-   Il sistema operativo è installato in una partizione NTFS. Per informazioni su NTFS, cercare l'acronimo "NTFS" nella Guida in linea e supporto tecnico di Windows Server 2003.

-   Al server sono state applicate tutte le patch e gli aggiornamenti per Windows Server 2003. Per controllare che nel server Web siano installati gli aggiornamenti di protezione più recenti, è possibile visitare la pagina [Microsoft Update](http://windowsupdate.microsoft.com/) nel sito Web Microsoft all'indirizzo http://windowsupdate.microsoft.com e ricercare gli aggiornamenti disponibili nel server mediante Microsoft Update.

-   Al server sono state applicate le misure di protezione previste in Windows Server 2003. Per ulteriori informazioni sulla protezione di Windows Server 2003, consultare il documento relativo alla [*Guida per la protezione di Windows Server 2003*](http://technet.microsoft.com/it-it/library/cc163140) all'indirizzo http://www.microsoft.com/italy/technet/security/prodtech/windowsserver2003/w2003hg/sgch00.mspx.

#### Caratteristiche del server Web

Le caratteristiche del server Web utilizzato come esempio in questo documento sono le seguenti:

-   Nel server Web è in esecuzione IIS 6.0 in modalità isolamento del processo di lavoro..

-   Il server Web ospita un solo sito Web Internet.

-   Il server Web è protetto da un firewall che consente il passaggio del traffico solo sulla porta HTTP 80 e sulla porta HTTPS 443.

-   Si tratta di un server Web dedicato, che viene utilizzato solo come tale e non per altri scopi, ad esempio come file server, server di stampa o server di database con Microsoft SQL Server.

-   È consentito l'accesso anonimo al sito Web.

-   Il server Web funziona con pagine HTML e ASP.

-   Le estensioni del server di FrontPage 2002 non sono configurate nel server Web.

-   Per le applicazioni del server Web non è richiesta la connettività di database.

-   Il server Web non supporta i protocolli FTP (caricamento e download di file), SMTP (posta elettronica) e NNTP (newsgroup).

-   Il server Web non utilizza ISA (Internet Security and Acceleration Server).

-   Richiede l'accesso locale dell'amministratore per le attività di amministrazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Riduzione della superficie di attacco del server Web

Il primo passo per proteggere il server Web consiste nel ridurne la superficie di attacco, ovvero il livello di esposizione a potenziali pirati informatici. È possibile, ad esempio, abilitare soltanto i componenti, i servizi e le porte che sono strettamente necessari per il corretto funzionamento del server Web.

#### Disabilitazione di SMB e NetBIOS

Negli attacchi di enumerazione host viene esplorata la rete per determinare l'indirizzo IP di potenziali bersagli. Per ridurre il rischio di attacchi di enumerazione host alle porte Internet nel server Web, disabilitare tutti i protocolli di rete ad eccezione di TCP (Transmission Control Protocol). Per i server Web non sono richiesti i protocolli SMB (Server Message Block) o NetBIOS nelle schede di rete Internet.

In questa sezione vengono riportate le istruzioni dettagliate per le attività seguenti che consentiranno di ridurre la superficie di attacco del server Web:

-   Disabilitazione di SMB in una connessione Internet.

-   Disabilitazione di NetBIOS su TCP/IP.

**Nota**: quando si disabilitano SMB e NetBIOS, il server non può funzionare come file server o server di stampa e non è possibile esplorare la rete o gestire il server Web in modo remoto. Nel caso di un server Web dedicato che richiede l'accesso locale degli amministratori, in genere queste limitazioni non influiscono sul funzionamento del server.

SMB utilizza le porte seguenti:

-   Porta TCP 139

-   Porta TCP e UDP 445 (SMB Direct Host)

NetBIOS utilizza le porte seguenti:

-   Porta TCP e UDP (User Datagram Protocol) 137 (servizio nomi NetBIOS)

-   Porta TCP e UDP 138 (servizio datagrammi NetBIOS)

-   Porta TCP e UDP 139 (servizio sessioni NetBIOS)

La sola disabilitazione di NetBIOS non è sufficiente a impedire le comunicazioni SMB perché se non è disponibile una porta NetBIOS standard, SMB utilizza la porta TCP 445, nota come SMB Direct Host. È necessario disabilitare separatamente NetBIOS e SMB.

##### Requisiti

Per completare questa attività è necessario disporre di quanto segue:

-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators

-   **Strumenti:** Risorse del computer, Utilità di sistema e Gestione periferiche.

**Per disabilitare SMB in una connessione Internet**

1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, quindi fare doppio clic su **Connessioni di rete**.

2.  Fare clic con il pulsante destro del mouse sulla connessione Internet, quindi scegliere **Proprietà**.

3.  Deselezionare la casella di controllo **Client per reti Microsoft**.

4.  Deselezionare la casella di controllo **Condivisione file e stampanti per reti Microsoft**, quindi fare clic su **OK**.

**Per disattivare NetBIOS su TCP/IP**

1.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, quindi scegliere **Gestione**.

2.  Fare doppio clic su **Utilità di sistema**, quindi selezionare **Gestione periferiche**.

3.  Fare clic con il pulsante destro del mouse su **Gestione periferiche**, scegliere **Visualizza**, quindi **Mostra periferiche nascoste**.

4.  Fare doppio clic su **Driver non Plug and Play**.

5.  Fare clic con il pulsante destro del mouse su **NetBIOS su TCP/IP**, scegliere **Disattiva** (illustrato nella figura seguente), quindi fare clic su **Sì**.

    ![](images/Cc875829.SIIS601(it-it,TechNet.10).gif "SIIS601.GIF")

    **Nota**: le illustrazioni incluse in questo documento riflettono un ambiente di prova e le informazioni riportate potrebbero essere diverse da quelle visualizzate.

Mediante la procedura descritta vengono disattivati sia il listener SMB gestito direttamente sulle porte TCP 445 e UDP 445 che il driver Nbt.sys. Al termine, è necessario riavviare il computer.

##### Verifica delle nuove impostazioni

Eseguire le procedure seguenti per verificare che al server Web siano state applicate le impostazioni di protezione appropriate.

**Per verificare se SMB è disabilitato**

1.  Fare clic sul pulsante Start, scegliere Impostazioni, quindi Rete e connessioni remote.

2.  Fare clic con il pulsante destro del mouse sulla connessione Internet, quindi scegliere **Proprietà**.

3.  Verificare che le caselle di controllo **Client per reti Microsoft** e **Condivisione file e stampanti per reti Microsoft** siano entrambe deselezionate, quindi fare clic su **OK**.

**Per verificare se NetBIOS è disabilitato**

1.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, quindi scegliere **Gestione**.

2.  Fare doppio clic su **Utilità di sistema**, quindi selezionare **Gestione periferiche**.

3.  Fare clic con il pulsante destro del mouse su **Gestione periferiche**, scegliere **Visualizza**, quindi **Mostra periferiche nascoste**.

4.  Fare doppio clic su **Driver non Plug and Play**, quindi fare clic con il pulsante destro del mouse su **NetBIOS su TCP/IP**. Ora il menu di scelta rapida conterrà l'opzione **Attiva** e questo indica che NetBIOS su TCP/IP è attualmente disattivato.

5.  Fare clic su **OK** per chiudere Gestione periferiche.

#### Selezione di componenti e servizi IIS essenziali

Oltre al servizio WWW, IIS 6.0 include altri sottocomponenti e servizi, ad esempio il servizio FTP e il servizio SMTP. Per ridurre al minimo il rischio di attacchi mirati a specifici servizi e sottocomponenti, è consigliabile selezionare solo quelli indispensabili per il corretto funzionamento dei siti e delle applicazioni Web.

Nella tabella che segue sono illustrate le impostazioni consigliate in Installazione applicazioni per i sottocomponenti e i servizi IIS del server Web utilizzato come esempio in questo documento.

**Tabella 1. Impostazioni consigliate per i sottocomponenti e i servizi IIS**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Sottocomponente o servizio</th>
<th style="border:1px solid black;" >Impostazione predefinita</th>
<th style="border:1px solid black;" >Impostazione del server Web</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Estensione server Servizio trasferimento intelligente in background (BITS)</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Invariato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">File comuni</td>
<td style="border:1px solid black;">Abilitato</td>
<td style="border:1px solid black;">Invariato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Servizio FTP</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Invariato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Estensioni del server di FrontPage 2002</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Invariato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Gestione Internet Information Services</td>
<td style="border:1px solid black;">Abilitato</td>
<td style="border:1px solid black;">Invariato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Stampa Internet</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Invariato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Servizio NNTP</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Invariato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Servizio SMTP</td>
<td style="border:1px solid black;">Abilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Servizio Web</td>
<td style="border:1px solid black;">Abilitato</td>
<td style="border:1px solid black;">Invariato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Estensione server Servizio trasferimento intelligente in background (BITS)</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Invariato</td>
</tr>
</tbody>
</table>
  
##### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Installazione applicazioni
  
**Per configurare componenti e servizi IIS**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, quindi fare clic su **Installazione applicazioni**.
  
2.  Fare clic su **Installazione componenti di Windows**.
  
3.  Nella schermata **Aggiunta guidata componenti di Windows**, in **Componenti** fare clic su **Server applicazioni**, quindi scegliere **Dettagli**.
  
4.  Selezionare **Internet Information Services (IIS)**, quindi scegliere **Dettagli**.
  
5.  Facendo riferimento alla tabella precedente, selezionare o deselezionare i componenti e i servizi IIS appropriati mediante le caselle di controllo.
  
6.  Completare l'Aggiunta guidata componenti di Windows seguendo le istruzioni visualizzate.
  
##### Verifica delle nuove impostazioni
  
Eseguire la procedura seguente per verificare che al server Web siano state applicate le impostazioni di protezione appropriate.
  
**Per verificare che i componenti e i servizi IIS siano selezionati**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, quindi fare clic su **Strumenti di amministrazione**.
  
2.  Il menu di Strumenti di amministrazione ora conterrà **Gestione Internet Information Services (IIS)**.
  
#### Attivazione delle sole estensioni essenziali dei servizi Web
  
Un server Web che funziona con contenuto dinamico richiede estensioni del servizio Web. A ogni tipo di contenuto dinamico corrisponde una specifica estensione. Per motivi di sicurezza, IIS 6.0 consente di abilitare e disabilitare singole estensioni del servizio Web, in modo che siano abilitate solo quelle necessarie in base al contenuto in questione.
  
**Attenzione**: non abilitare tutte le estensioni del servizio Web. Sebbene facendolo si ottenga la massima compatibilità possibile con i siti Web e le applicazioni esistenti, la superficie di attacco del server aumenta considerevolmente. Potrebbe essere necessario verificare individualmente applicazioni e siti Web, per avere la certezza che siano abilitate solo le estensioni del servizio Web necessarie.
  
Si supponga che la configurazione del server Web preveda come pagina predefinita il file Default.asp. Nonostante la pagina predefinita sia configurata, per visualizzare la pagina ASP sarà necessario abilitare l'estensione del servizio Web Pagine ASP.
  
##### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Gestione Internet Information Services (IIS) (iis.msc).
  
**Per abilitare l'estensione del servizio Web Pagine ASP**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
2.  Fare doppio clic sul computer locale, quindi scegliere **Estensioni servizio Web**.
  
3.  Fare clic su **Pagine ASP** e scegliere **Consenti** (come mostrato nella schermata seguente).
  
    ![](images/Cc875829.SIIS602(it-it,TechNet.10).gif "SIIS602.GIF")
  
##### Verifica delle nuove impostazioni
  
Eseguire la procedura seguente per verificare che al server Web siano state applicate le impostazioni di protezione appropriate.
  
**Per verificare che l'estensione del servizio Web Pagine ASP sia abilitata**
  
1.  Aprire un editor di testo, digitare **Pagina ASP di prova** e salvare il file con il nome **Default.asp** nella directory C:\\inetpub\\wwwroot.
  
2.  Nella casella **Indirizzo** di Internet Explorer, digitare l'URL seguente:
  
    http://localhost
  
    Infine, premere INVIO. Nel browser dovrebbe essere visualizzato il testo Pagina ASP di prova.
  
3.  Eliminare il file C:\\inetpub\\wwwroot\\**Default.asp**.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione degli account
  
Microsoft consiglia di rimuovere gli account inutilizzati, perché un utente che effettua un attacco potrebbe individuarli e utilizzarli per accedere ai dati e alle applicazioni Web presenti nel server. È necessario utilizzare sempre password complesse: in caso contrario, aumenta il rischio che un attacco a forza bruta o con dizionario, ovvero il tentativo di un aggressore di identificare le password, possa avere esito positivo. Utilizzare account con privilegi minimi. Questa precauzione consente di evitare che un utente che effettua un attacco possa utilizzare un account dotato di privilegi elevati per accedere a risorse non autorizzate.
  
In questa sezione vengono illustrate le istruzioni dettagliate relative alle attività seguenti:
  
-   Disabilitazione degli account inutilizzati.
  
-   Isolamento delle applicazioni mediante pool di applicazioni.
  
#### Disabilitazione degli account inutilizzati
  
Gli account inutilizzati e i relativi privilegi possono essere utilizzati dai pirati informatici per ottenere l'accesso a un server. È consigliabile controllare periodicamente gli account locali nel server e disabilitare gli eventuali account inutilizzati. Disabilitare gli account in un server di prova prima di disabilitarli in un server di produzione per assicurare che l'operazione non influisca negativamente sul funzionamento dell'applicazione. Se la disabilitazione dell'account non causa problemi nel server di prova, è possibile disabilitare l'account nel server di produzione.
  
**Nota**: se si sceglie di eliminare un account inutilizzato anziché disabilitarlo, tenere presente che non è possibile ripristinare un account eliminato o eliminare gli account Administrator e Guest. È consigliabile inoltre eliminare l'account in un server di prova prima di eliminarlo nel server di produzione.
  
In questa sezione vengono illustrate le istruzioni dettagliate relative alle procedure seguenti:
  
-   Disabilitazione dell'account Guest.
  
-   Ridenominazione dell'account Administrator.
  
-   Ridenominazione dell'account IUSR\_NomeComputer.
  
##### Disabilitazione dell'account Guest
  
L'account Guest viene utilizzato per le connessioni anonime al server Web. In un'installazione predefinita di Windows Server 2003 l'account Guest è disabilitato. Per limitare le connessioni anonime al server è consigliabile che rimanga disabilitato.
  
###### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Gestione computer
  
**Per disabilitare l'account Guest**
  
1.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, quindi scegliere **Gestione**.
  
2.  Fare doppio clic su **Utenti e gruppi locali**, quindi selezionare la cartella **Users**. Sull'icona dell'account Guest dovrebbe essere visualizzata una X rossa, a indicare che l'account è disabilitato (come mostrato nella schermata seguente).
  
    In caso contrario, procedere con il passaggio 3 per disabilitarlo.
  
    ![](images/Cc875829.SIIS603(it-it,TechNet.10).gif "SIIS603.GIF")
  
3.  Fare clic con il pulsante destro del mouse sull'account **Guest**, quindi scegliere **Proprietà**.
  
4.  Nella scheda **Generale**, selezionare la casella di controllo **Account disabilitato**, quindi fare clic su **OK**.
  
Sull'icona dell'account Guest dovrebbe essere visualizzata una X rossa.
  
##### Ridenominazione dell'account Administrator
  
L'account locale predefinito Administrator è un bersaglio per i malintenzionati a causa dei privilegi elevati di cui dispone. Per migliorare la protezione, rinominare l'account Administrator predefinito e assegnargli una password complessa.
  
###### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Risorse del computer.
  
**Per rinominare l'account Administrator e assegnare una password complessa**
  
1.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, quindi scegliere **Gestione**.
  
2.  Fare doppio clic su **Utenti e gruppi locali**, quindi selezionare la cartella **Users**.
  
3.  Fare clic con il pulsante destro del mouse sull'account **Administrator**, quindi scegliere **Rinomina**.
  
4.  Digitare un nome nell'apposita casella e premere INVIO.
  
5.  Nel desktop, premere CTRL+ALT+CANC, quindi fare clic su **Cambia password**.
  
6.  Digitare il nuovo nome per l'account Administrator nella casella **Nome utente**.
  
7.  Digitare la password corrente nella casella **Vecchia password**, digitarne una nuova nella casella **Nuova password**, digitare una seconda volta la nuova password nella casella **Conferma nuova password**, quindi fare clic su **OK**.
  
**Attenzione**: per cambiare la password non utilizzare la voce del menu di scelta rapida Imposta password, a meno di non aver dimenticato la password e di non avere a disposizione un disco di reimpostazione password. Se utilizzato per cambiare la password Administrator, questo metodo potrebbe causare la perdita irreversibile di informazioni protette dalla password in questione.
  
##### Ridenominazione dell'account IUSR
  
L'account utente Internet anonimo predefinito, IUSR\_*&lt;NomeComputer&gt;*, viene creato durante l'installazione di IIS. *&lt;NomeComputer&gt;* corrisponde al nome NetBIOS del server al momento dell'installazione di IIS. Ridenominando questo account si riducono le probabilità di riuscita di alcuni attacchi a forza bruta.
  
###### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Risorse del computer.
  
**Per rinominare l'account IUSR**
  
1.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, quindi scegliere **Gestione**.
  
2.  Fare doppio clic su **Utenti e gruppi locali**, quindi selezionare la cartella **Users**.
  
3.  Fare clic con il pulsante destro del mouse sull'account **IUSR\_&lt;NomeComputer&gt;**, quindi scegliere **Rinomina**.
  
4.  Digitare il nuovo nome account e premere INVIO.
  
**Per modificare il valore per l'account IUSR nella metabase IIS**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
2.  Fare clic con il pulsante destro del mouse sul computer locale, quindi scegliere **Proprietà**.
  
3.  Selezionare la casella di controllo **Abilita modifiche dirette della metabase**, quindi fare clic su **OK**.
  
4.  Selezionare il percorso del file **MetaBase.xml**, che per impostazione predefinita si trova in C:\\Windows\\system32\\inetsrv.
  
5.  Fare clic con il pulsante destro del mouse sul file **MetaBase.xml**, quindi scegliere **Modifica**.
  
6.  Individuare la proprietà **AnonymousUserName** e digitare il nuovo nome dell'account IUSR.
  
7.  Scegliere **Esci** dal menu **File**, quindi fare clic su **Sì**.
  
###### Verifica delle nuove impostazioni
  
Eseguire le procedure seguenti per verificare che al server Web siano state applicate le impostazioni di protezione appropriate.
  
**Per verificare se un account è disabilitato**
  
1.  Premere CTRL+ALT+CANC, quindi fare clic su **Disconnetti** per disconnettere il server Web.
  
2.  Nella casella **Nome utente** della finestra di dialogo **Accesso a Windows**, digitare il nome dell'account disabilitato, digitare la relativa password, quindi fare clic su **OK**.
  
    Verrà visualizzato il messaggio seguente:
  
    **L'account utente è stato disattivato. Rivolgersi all'amministratore del sistema.**
  
**Per verificare se un account è stato rinominato**
  
1.  Premere CTRL+ALT+CANC, quindi fare clic su **Disconnetti** per disconnettere il server Web.
  
2.  Nella casella **Nome utente** della finestra di dialogo **Accesso a Windows**, digitare il nome precedente dell'account rinominato, digitare la relativa password, quindi fare clic su **OK**.
  
    Verrà visualizzato il messaggio seguente:
  
    **Impossibile accedere. Assicurarsi che il nome utente e il dominio siano corretti,** **quindi digitare nuovamente la password rispettando i caratteri maiuscoli o minuscoli.**
  
3.  Fare clic su **OK**, quindi digitare il nuovo nome dell'account rinominato nella casella **Nome utente**.
  
4.  Digitare la password dell'account rinominato, quindi fare clic su **OK**.
  
Dovrebbe essere possibile accedere al computer con l'account rinominato.
  
#### Isolamento delle applicazioni mediante pool di applicazioni
  
È possibile utilizzare IIS 6.0 per isolare le applicazioni in pool di applicazioni. I pool di applicazioni sono gruppi di uno o più URL utilizzati da un processo di lavoro o da un gruppo di processi di lavoro. Consentono di migliorare l'affidabilità e la protezione del server Web, perché ciascuna applicazione funziona indipendentemente dalle altre.
  
A ogni processo eseguito in un sistema operativo Windows corrisponde una identità di processo, che ne determina le modalità di accesso alle risorse presenti nel computer. Anche i pool di applicazioni sono dotati di un'identità di processo, un account che viene eseguito con le autorizzazioni minime richieste dall'applicazione. L'identità di processo può essere utilizzata per consentire l'accesso anonimo alle applicazioni o al sito Web.
  
##### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Risorse del computer.
  
**Per creare un pool di applicazioni**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
2.  Fare doppio clic sul computer locale, fare clic con il pulsante destro del mouse su **Pool di applicazioni**, scegliere **Nuovo**, quindi **Pool di applicazioni**.
  
3.  Nella casella **ID pool di applicazioni**, digitare un nuovo ID per il pool di applicazioni (nella schermata di esempio seguente viene utilizzato ContosoAppPool come ID).
  
    ![](images/Cc875829.SIIS604(it-it,TechNet.10).gif "SIIS604.GIF")
  
4.  In **Impostazioni pool di applicazioni**, selezionare **Usa impostazioni predefinite per il nuovo pool di applicazioni**, quindi fare clic su **OK**.
  
**Per assegnare un'applicazione o un sito Web a un pool di applicazioni**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
2.  Fare clic con il pulsante destro del mouse sull'applicazione o il sito Web che si desidera assegnare a un pool di applicazioni, quindi scegliere **Proprietà**.
  
3.  Fare clic sulla scheda **Home Directory**, **Directory virtuale** o **Directory**, a seconda del tipo di applicazione selezionato.
  
4.  Se si intende assegnare una directory o una directory virtuale a un pool di applicazioni, verificare che la casella **Nome applicazione** contenga il nome corretto dell'applicazione o del sito Web.
  
    Oppure
    
    Se la casella **Nome applicazione** non contiene alcun nome, scegliere **Crea** e digitarne uno.
  
5.  Nella casella di riepilogo **Pool di applicazioni** selezionare il nome del pool di applicazioni a cui si desidera assegnare l'applicazione o il sito Web (come mostrato nella schermata seguente), quindi fare clic su **OK**.
  
    ![](images/Cc875829.SIIS605(it-it,TechNet.10).gif "SIIS605.GIF")
  
##### Verifica delle nuove impostazioni
  
Eseguire le procedure seguenti per verificare che al server Web siano state applicate le impostazioni di protezione appropriate.
  
**Per verificare che il pool di applicazioni sia stato creato**
  
1.  Accedere al server Web tramite l'account Administrator.
  
2.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
3.  Fare doppio clic sul computer locale e quindi su **Pool di applicazioni**. Verificare che il pool di applicazioni creato sia visualizzato nel nodo **Pool di applicazioni**.
  
4.  Fare clic con il pulsante destro del mouse sul pool di applicazioni creato e scegliere **Proprietà**.
  
5.  Selezionare la scheda **Identità**, verificare che l'identità del pool di applicazioni sia impostata su un account di protezione predefinito denominato Servizio di rete, quindi fare clic su **OK**.
  
**Per verificare che un'applicazione o un sito Web sia stato assegnato a uno specifico pool di applicazioni**
  
1.  Accedere al server Web tramite l'account Administrator.
  
2.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
3.  Fare doppio clic sul computer locale e quindi su **Siti Web**, fare clic con il pulsante destro del mouse sul sito Web per cui si desidera verificare l'impostazione del pool di applicazioni, quindi scegliere **Proprietà**.
  
4.  Fare clic sulla scheda **Home Directory**, **Directory virtuale** o **Directory**, a seconda del tipo di applicazione selezionato.
  
5.  Controllare che nella casella di riepilogo **Pool di applicazioni** sia presente il nome del pool di applicazioni a cui si desidera assegnare il sito Web, quindi fare clic su **Annulla**.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione della protezione per file e directory
  
Per proteggere file e directory riservati è necessario utilizzare controlli di accesso avanzati. Nella maggior parte delle situazioni, l'approccio più efficace non consiste nel negare l'accesso a specifici account, ma nel consentirlo solo a specifici account. Se possibile, impostare l'accesso a livello di directory. Poiché i file aggiunti alla cartella ne erediteranno le autorizzazioni, non saranno necessarie ulteriori impostazioni.
  
In questa sezione vengono riportate le istruzioni dettagliate per le attività seguenti, che consentiranno di configurare la protezione per file e directory:
  
-   Rilocazione e impostazione delle autorizzazioni per i file di registro IIS.
  
-   Configurazione delle autorizzazioni della metabase IIS.
  
-   Disabilitazione del componente File System Object.
  
#### Rilocazione e impostazione delle autorizzazioni per i file di registro IIS
  
Per aumentare la protezione dei file di registro IIS è opportuno rilocarli in un'unità non di sistema, formattata per utilizzare il file system NTFS. La nuova posizione deve essere diversa da quella del contenuto del sito Web. Con la rilocazione di questi file è possibile impedire ad alcuni tipi di attacchi di rilevare il contenuto dei file di registro. È inoltre consigliabile proteggere i file di registro in modo da fornire un itinerario di controllo dei possibili attacchi al server. Il posizionamento dei file di registro su un disco non di sistema può anche migliorare le prestazioni del server.
  
##### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Risorse del computer e Gestione Internet Information Services (IIS) (Iis.msc)
  
**Per spostare i file di registro IIS in una partizione non di sistema**
  
1.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, quindi scegliere **Esplora**.
  
2.  Selezionare il percorso in cui si desidera rilocare i file di registro IIS.
  
3.  Fare clic con il pulsante destro del mouse sulla directory superiore di un livello rispetto al percorso in cui si desidera rilocare i file di registro IIS, scegliere **Nuovo** e quindi **Cartella**.
  
4.  Assegnare un nome alla cartella, ad esempio LogIISContoso, e premere INVIO.
  
5.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
6.  Fare clic con il pulsante destro del mouse sul sito Web, quindi scegliere **Proprietà**.
  
7.  Fare clic sulla scheda **Sito Web**, quindi scegliere **Proprietà** nel riquadro **Consenti registrazione attività**.
  
8.  Nella scheda **Proprietà generali**, fare clic su **Sfoglia** e selezionare la cartella appena creata per archiviare i file di registro IIS.
  
9.  Fare clic su **OK** per tre volte.
  
**Nota**: se nel percorso originale Windows\\System32\\Logfiles sono già presenti file di registro IIS, sarà necessario spostarli manualmente nella nuova posizione. IIS non sposta automaticamente tali file.
  
**Per impostare gli ACL nei file di registro IIS**
  
1.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, quindi scegliere **Esplora**.
  
2.  Selezionare la cartella che contiene i file di registro.
  
3.  Fare clic con il pulsante destro del mouse sulla cartella, scegliere **Proprietà**, quindi selezionare la scheda **Protezione**.
  
4.  Nel riquadro in alto fare clic su **Administrators** e controllare che per le autorizzazioni nel riquadro in basso sia impostato **Controllo completo**.
  
5.  Nel riquadro in alto fare clic su **System**, controllare che per le autorizzazioni nel riquadro in basso sia impostato **Controllo completo**, quindi fare clic su **OK**.
  
##### Verifica delle nuove impostazioni
  
Eseguire la procedura seguente per verificare che al server Web siano state applicate le impostazioni di protezione appropriate.
  
**Per verificare che i file di registro siano stati spostati e che le autorizzazioni siano state impostate**
  
1.  Fare clic sul pulsante **Start**, scegliere **Cerca**, quindi **File o cartelle**.
  
2.  Nella casella **Cerca file denominati** digitare un nome file o parte di esso, ad esempio FileLog, selezionare un percorso nella casella **Cerca in**, quindi fare clic su **Cerca ora**.
  
    La ricerca restituirà la nuova posizione dei file di registro.
  
3.  Premere CTRL+ALT+CANC, quindi fare clic su **Disconnetti**.
  
4.  Accedere al server Web tramite un account che non include l'autorizzazione per l'accesso ai file di registro.
  
5.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, scegliere **Esplora**, quindi selezionare la directory FileLog.
  
6.  Fare clic con il pulsante destro del mouse sulla directory FileLog, quindi scegliere **Apri**. Verrà visualizzato il messaggio seguente:
  
    **Accesso negato**.
  
#### Configurazione delle autorizzazioni della metabase IIS
  
La metabase IIS è un file XML che contiene la maggior parte delle informazioni di configurazione IIS.
  
##### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Risorse del computer e il file MetaBase.xml
  
**Per limitare l'accesso al file MetaBase.xml**
  
1.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, quindi scegliere **Esplora**.
  
2.  Selezionare il file **Windows\\System32\\Inetsrv\\MetaBase.xml**, fare clic con il pulsante destro del mouse su di esso, quindi scegliere **Proprietà**.
  
3.  Fare clic sulla scheda **Protezione**, assegnare solo ai membri del gruppo Administrators e all'account LocalSystem l'accesso con Controllo completo alla metabase, rimuovere tutte le altre autorizzazioni file, quindi fare clic su **OK**.
  
##### Verifica delle nuove impostazioni
  
Eseguire la procedura seguente per verificare che al server Web siano state applicate le impostazioni di protezione appropriate.
  
**Per verificare che l'accesso al file MetaBase.xml sia stato limitato**
  
1.  Premere CTRL+ALT+CANC, quindi fare clic su **Disconnetti**.
  
2.  Accedere al server Web con un account che non dispone dell'autorizzazione per l'accesso al file **MetaBase.xml**.
  
3.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, scegliere **Esplora**, quindi selezionare la posizione del file **MetaBase.xml**.
  
4.  Fare clic con il pulsante destro del mouse sul file **MetaBase.xml**, quindi scegliere **Apri**. Verrà visualizzato il messaggio seguente:
  
    **Accesso negato**.
  
#### Disabilitazione del componente File System Object
  
ASP, Windows Script Host e altre applicazioni di scripting utilizzano il componente File System Object (FSO) per creare, eliminare e ottenere le relative informazioni, nonché per modificare unità, cartelle e file. Se si intende disabilitare il componente FSO, tenere tuttavia presente che in tal caso verrà rimosso anche l'oggetto Dictionary. Verificare inoltre che questo componente non sia necessario per altri programmi.
  
##### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: prompt dei comandi.
  
**Per disabilitare il componente File System Object**
  
1.  Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **cmd** nella casella **Apri**, quindi fare clic su **OK**.
  
2.  Digitare **cd c:\\Windows\\system32** e premere INVIO per passare alla directory C:\\Windows\\system32.
  
3.  Al prompt dei comandi, digitare **regsvr32 scrrun.dll /u** e premere INVIO. Verrà visualizzato il messaggio seguente:
  
    **DllUnregisterServer in scrrun.dll riuscito.**
  
4.  Fare clic su **OK**.
  
5.  Al prompt dei comandi, digitare **exit** e premere INVIO per chiudere la finestra del prompt.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Protezione di siti Web e directory virtuali
  
Spostare le directory Web principali e virtuali in una partizione non di sistema è una misura di protezione contro gli attacchi di attraversamento delle directory, che consentono agli utenti che effettuano gli attacchi di eseguire programmi e strumenti del sistema operativo. Poiché non è possibile attraversare le unità, la rilocazione del contenuto del sito Web in un'altra unità offre una protezione aggiuntiva da questi attacchi.
  
In questa sezione vengono riportate le istruzioni dettagliate per le attività seguenti che consentiranno di proteggere i siti Web e le directory virtuali:
  
-   Spostamento del contenuto del sito Web in un'unità non di sistema
  
-   Configurazione delle autorizzazioni del sito Web.
  
#### Spostamento del contenuto del sito Web in un'unità non di sistema
  
Il contenuto del sito Web non deve essere collocato nella directory predefinita \\Inetpub\\Wwwroot. Se ad esempio il sistema operativo è installato nell'unità C:, è possibile spostare il sito e la directory con il relativo contenuto nell'unità D: per ridurre i rischi associati agli attacchi di attraversamento delle directory, in cui un pirata informatico tenta di esplorare la struttura di directory di un server Web. Verificare che tutte le directory virtuali facciano riferimento alla nuova unità.
  
##### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Gestione Internet Information Services (IIS) (Iis.msc), prompt dei comandi
  
**Per spostare il contenuto del sito Web in un'unità non di sistema**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
2.  Fare clic con il pulsante destro del mouse sul sito Web di cui si desidera spostare il contenuto, quindi scegliere **Arresta**.
  
3.  Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **cmd** nella casella **Apri**, quindi fare clic su **OK**.
  
4.  Al prompt dei comandi, digitare:
  
    **xcopy c:\\inetpub\\wwwroot\\*&lt;NomeSito&gt; &lt;Unità&gt;*:\\wwwroot\\&lt;NomeSito&gt; /s /i /o**
  
    dove
  
    -   *&lt;NomeSito&gt;* è il nome del sito Web.
  
    -   *&lt;Unità&gt;* è la lettera corrispondente alla nuova unità, ad esempio D.
  
5.  Tornare allo snap-in Gestione Internet Information Services (IIS), fare clic con il pulsante destro del mouse sul sito Web, quindi scegliere **Proprietà**.
  
6.  Fare clic sulla scheda **Home Directory**, **Directory virtuale** o **Directory**, a seconda del tipo di applicazione selezionato, digitare la nuova posizione della directory nella casella **Percorso locale**, quindi fare clic su **OK**.
  
    Oppure
  
    Selezionare la nuova posizione della directory in cui sono stati appena copiati i file, quindi fare clic su **OK**.
  
7.  Fare clic con il pulsante destro del mouse sul sito Web, quindi scegliere **Avvia**.
  
##### Verifica delle nuove impostazioni
  
Eseguire le procedure seguenti per verificare che al server Web siano state applicate le impostazioni di protezione appropriate.
  
**Per verificare che il contenuto del sito Web sia stato spostato in un'unità non di sistema**
  
1.  Fare clic sul pulsante **Start**, scegliere **Cerca**, quindi **File o cartelle**.
  
2.  Nella casella **Cerca file denominati** digitare un nome file o parte di esso, selezionare una posizione nella casella **Cerca in**, quindi fare clic su **Cerca ora**.
  
    La ricerca restituirà restituirà l'elenco dei file spostati nella nuova posizione e la loro posizione originale.
  
**Per eliminare il contenuto del sito Web dall'unità di sistema**
  
-   Selezionare la directory C:\\Inetpub\\Wwwroot\\&lt;NomeSito&gt; ed eliminare i file che sono stati spostati in un'unità non di sistema.
  
**Per verificare che il contenuto del sito Web sia stato eliminato dall'unità di sistema**
  
1.  Fare clic sul pulsante **Start**, scegliere **Cerca**, quindi **File o cartelle**.
  
2.  Nella casella **Cerca file denominati** digitare un nome file o parte di esso, selezionare una posizione nella casella **Cerca in**, quindi fare clic su **Cerca ora**.
  
    La ricerca restituirà solo l'elenco dei file spostati nella nuova posizione.
  
#### Configurazione delle autorizzazioni del sito Web
  
È possibile configurare le autorizzazioni di accesso al server Web per siti, directory e file specifici. Queste autorizzazioni si applicano a tutti gli utenti, indipendentemente dai relativi diritti di accesso specifici.
  
##### Configurazione delle autorizzazioni nelle directory del file system
  
IIS 6.0 si basa sulle autorizzazioni NTFS per la protezione di singoli file e directory da accessi non autorizzati. Diversamente dalle autorizzazioni per i siti Web, che si applicano a chiunque tenti di accedere al sito Web, le autorizzazioni NTFS possono essere utilizzate per definire con precisione quali utenti possono accedere al contenuto e in che modo sono autorizzati a manipolarlo. Per una maggiore protezione, è consigliabile utilizzare sia le autorizzazioni del sito Web che le autorizzazioni NTFS.
  
Gli elenchi di controllo di accesso (ACL) indicano gli utenti o i gruppi in possesso dell'autorizzazione per l'accesso o la modifica di un file specifico. Anziché impostare ACL per ogni file, è possibile creare nuove directory per ogni tipo di file e per ciascuna di esse impostare gli ACL, consentendo ai file di ereditare le autorizzazioni dalla directory in cui risiedono.
  
###### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Risorse del computer locale e Gestione Internet Information Services (IIS) (iis.msc)
  
**Per spostare il contenuto del sito Web in una cartella separata**
  
1.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, quindi scegliere **Esplora**.
  
2.  Selezionare la cartella in cui si trova il contenuto del sito Web e quindi la relativa cartella principale.
  
3.  Scegliere **Nuovo** dal menu **File** e quindi **Cartella** per creare una nuova cartella nella directory del contenuto del sito Web.
  
4.  Assegnare un nome alla cartella e premere INVIO.
  
5.  Tenendo premuto il tasto CTRL selezionare tutte le pagine che si desidera proteggere.
  
6.  Fare clic con il pulsante destro del mouse sulle pagine, quindi scegliere **Copia**.
  
7.  Fare clic con il pulsante destro del mouse sulla nuova cartella, quindi scegliere **Incolla**.
  
**Nota**: eventuali collegamenti a queste pagine devono essere aggiornati per riflettere la nuova posizione del contenuto del sito.
  
**Per impostare le autorizzazioni per il contenuto Web**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
2.  Fare clic con il pulsante destro del mouse sul file, sito Web, directory, directory virtuale o cartella Siti Web che si desidera configurare, quindi scegliere **Proprietà**.
  
3.  A seconda del tipo di accesso che si intende concedere o negare, selezionare o deselezionare le caselle di controllo seguenti, se disponibili:
  
    -   **Accesso origine script**. Gli utenti possono accedere ai file di origine. Se si seleziona **Lettura**, è possibile leggerli; se si seleziona **Scrittura**, è possibile eseguire operazioni di scrittura. Accesso origine script include il codice sorgente degli script. L'opzione non è disponibile se non sono selezionate autorizzazioni di **Lettura** né di **Scrittura**.
  
    -   **Lettura (selezionata per impostazione predefinita)**. Gli utenti possono visualizzare il contenuto e le proprietà di directory e file.
  
    -   **Scrittura**. Gli utenti possono modificare il contenuto e le proprietà di directory e file.
  
    -   **Esplorazione directory**. Gli utenti possono visualizzare raccolte ed elenchi di file.
  
    -   **Registrazione visite**. Viene creata una voce di registro per ogni visita al sito Web.
  
    -   **Indicizza questa risorsa**. Consente al Servizio di indicizzazione di indicizzare la risorsa, in modo che gli utenti possano eseguirvi ricerche.
  
4.  Nella casella di riepilogo **Autorizzazioni di esecuzione**, selezionare il livello desiderato per l'esecuzione di script:
  
    -   **Nessuna**. Non è possibile eseguire script o file eseguibili nel server, ad esempio file con estensione exe.
  
    -   **Solo script**. È possibile eseguire solo script nel server.
  
    -   **Script e file eseguibili**. È possibile eseguire sia script che file eseguibili nel server.
  
5.  Fare clic su **OK**. Se per i nodi figlio di una directory sono state configurate autorizzazioni del sito Web diverse, viene visualizzata la finestra di dialogo **Proprietà ereditate ignorate**.
  
6.  Se viene visualizzata la finestra di dialogo **Proprietà ereditate ignorate**, nell'elenco **Nodi figlio** selezionare i nodi figlio a cui si desidera applicare le autorizzazioni Web della directory.
  
    Oppure
  
    Fare clic su **Seleziona tutto** per impostare la proprietà in modo da applicare le autorizzazioni Web a tutti i nodi figlio.
  
7.  Se la finestra di dialogo **Proprietà ereditate ignorate** viene visualizzata più volte, selezionare i nodi figlio nell'elenco **Nodi figlio** o fare clic su **Seleziona tutto** e quindi su **OK** per applicare le autorizzazioni Web per la proprietà ai nodi figlio.
  
Se in un nodo figlio appartenente alla directory per cui sono state modificate le autorizzazioni del sito Web sono state impostate anche le autorizzazioni per una specifica opzione, le autorizzazioni impostate per il nodo figlio prevarranno su quelle impostate per la directory. Se si desidera che le autorizzazioni del sito Web a livello di directory siano applicate ai nodi figlio, è necessario selezionare i nodi figlio desiderati nella finestra di dialogo **Proprietà ereditate ignorate**.
  
###### Verifica delle nuove impostazioni
  
Eseguire la procedura seguente per verificare che al server Web siano state applicate le impostazioni di protezione appropriate.
  
**Per verificare che sia negato l'accesso in scrittura alle directory del contenuto del sito Web**
  
1.  Premere CTRL+ALT+CANC, quindi fare clic su **Disconnetti**.
  
2.  Accedere al server Web utilizzando un account dotato dell'autorizzazione Lettura/Esecuzione per la directory fisica o virtuale.
  
3.  Fare clic su **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, scegliere **Esplora** e selezionare la posizione del file che si desidera copiare nella directory fisica o virtuale.
  
4.  Fare clic con il pulsante destro del mouse sul file, quindi scegliere **Copia**.
  
5.  Selezionare la posizione della directory fisica o virtuale e fare clic con il pulsante destro del mouse su di essa. Nel menu di scelta rapida non sarà disponibile l'opzione **Incolla** e ciò significa che non si dispone dell'accesso in scrittura alla directory.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione di Secure Sockets Layer (SSL) nel server Web
  
Configurare la funzionalità di protezione Secure Sockets Layer (SSL) nel server Web per verificare l'integrità del contenuto e l'identità degli utenti, nonché per crittografare le trasmissioni di rete. SSL è in genere un requisito indispensabile qualora si preveda di accettare transazioni con carte di credito sul un sito Web. La protezione SSL è basata su un certificato server che consente agli utenti di autenticare il sito Web prima di trasmettere informazioni personali, ad esempio il numero della carta di credito. Per ogni sito Web è possibile ottenere un solo certificato server.
  
#### Come ottenere e installare un certificato server
  
I certificati vengono rilasciati da organizzazioni non Microsoft denominate Autorità di certificazione (CA). Normalmente il certificato server è associato allo specifico server Web e in particolare al sito Web in cui è stato configurato SSL. È necessario generare una richiesta di certificato, inviarla all'Autorità di certificazione e quindi installare il certificato dopo averlo ricevuto dalla CA.
  
I certificati sono basati su una coppia di chiavi di crittografia, una pubblica e una privata, per garantire la protezione. Generando una richiesta di certificato server viene in effetti generata la chiave privata. Il certificato server ricevuto dalla CA contiene la chiave pubblica.
  
##### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Gestione Internet Information Services (IIS) (iis.msc) e Gestione guidata certificati server Web.
  
**Per generare una richiesta di certificato server**
  
1.  Fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Risorse del computer**, quindi scegliere **Gestione**.
  
2.  Fare doppio clic sulla sezione **Servizi e applicazioni**, quindi di nuovo su **Internet Information Services**.
  
3.  Fare clic con il pulsante destro del mouse sul sito Web in cui si desidera installare un certificato server, quindi scegliere **Proprietà**.
  
4.  Fare clic sulla scheda **Protezione directory**. Nella sezione **Comunicazioni protette**, selezionare **Certificato server** per avviare la Gestione guidata certificati server Web, quindi fare clic su **Avanti**.
  
5.  Selezionare **Crea nuovo certificato**, quindi fare clic su **Avanti**.
  
6.  Selezionare **Preparare la richiesta** **per l'invio posticipato**, quindi fare clic su **Avanti**.
  
7.  Nella casella **Nome** digitare un nome che sia facile da ricordare. Il nome predefinito è quello del sito Web per cui si sta generando la richiesta di certificato, ad esempio http://www.contoso.com.
  
8.  Specificare una lunghezza in bit e fare clic su **Avanti**.
  
    La complessità della crittografia sarà direttamente proporzionale alla lunghezza in bit specificata per la chiave di crittografia. Per la maggior parte delle CA non Microsoft è preferibile scegliere un minimo di 1024 bit.
  
9.  Nella sezione **Organizzazione** digitare le informazioni sull'organizzazione e sull'unità organizzativa. Controllare che le informazioni immesse siano corrette e che i campi Organizzazione non contengano virgole, quindi fare clic su **Avanti**.
  
10. Nella sezione **Nome comune del sito** digitare il nome del computer host con il nome di dominio, quindi fare clic su **Avanti**.
  
11. Digitare i dati geografici, quindi fare clic su **Avanti**.
  
12. Salvare il file con estensione txt. Il nome e il percorso predefiniti per il file sono **C:\\certreq.txt**. Nell'esempio seguente viene mostrato l'aspetto di un file di richiesta certificato.
  
```
   -----BEGIN NEW CERTIFICATE REQUEST-----

MIIDATCCAmoCAQAwbDEOMAwGA1UEAxMFcGxhbjgxDDAKBgNVBAsTA1BTUzESMB
                A1UEChMJTWljcm9zb2Z0MRIwEAYDVQQHEwlDaGFybG90dGUxFzAVBgNVBAgTDk
                cnRoIENhcm9saW5hMQswCQYDVQQGEwJVUzCBnzANBgkqhkiG9w0BAQEFAAOBjQ
                gYkCgYEAtW1koGfdt+EoJbKdxUZ+5vE7TF1ZuT+xaK9jEWHESfw11zoRKrHzHN
                IASnwg3vZ0ACteQy5SiWmFaJeJ4k7YaKUb6chZXG3GqL4YiSKFaLpJX+YRiKMt
                JzFzict5GVVGHsa1lY0BDYDO2XOAlstGlHCtENHOKpzdYdANRg0CAwEAAaCCAV
                GgYKKwYBBAGCNw0CAzEMFgo1LjAuMjE5NS4yMDUGCisGAQQBgjcCAQ4xJzAlMA
                A1UdDwEB/wQEAwIE8DATBgNVHSUEDDAKBggrBgEFBQcDATCB/QYKKwYBBAGCNw
                AjGB7jCB6wIBAR5aAE0AaQBjAHIAbwBzAG8AZgB0ACAAUgBTAEEAIABTAEMAaA
                AG4AbgBlAGwAIABDAHIAeQBwAHQAbwBnAHIAYQBwAGgAaQBjACAAUAByAG8Adg
                AGQAZQByA4GJAGKa0jzBn8fkxScrWsdnU2eUJOMUK5Ms87Q+fjP1/pWN3PJnH7
                MBc5isFCjww6YnIjD8c3OfYfjkmWc048ZuGoH7ZoD6YNfv/SfAvQmr90eGmKOF
                TD+hl1hM08gu2oxFU7mCvfTQ/2IbXP7KYFGEqaJ6wn0Z5yLOByPqblQZAAAAAA
                MhfC7CIvR0McCQ+CBwuLzD+UJxl+kjgb+qwcOUkGX2PCZ7tOWzcXWNmn/4YHQl
                GEXu0w67sVc2R9DlsHDNzeXLIOmjUl935qy1uoIR4V5C48YNsF4ejlgjeCFsbC Jb9/2RM=
                -----END NEW CERTIFICATE REQUEST-----
```

13. Confermare i dettagli della richiesta, fare clic su **Avanti** e quindi su **Fine**.
  
**Per inviare una richiesta di certificato server**
  
1.  Contattare la CA in questione per informarsi sui requisiti previsti per l'inoltro delle richieste.
  
2.  Copiare nel formato richiesto dalla CA il contenuto del file con estensione txt creato nella procedura precedente.
  
3.  Inviare la richiesta alla CA.
  
Quando si riceve il certificato dalla CA, è possibile installarlo nel server Web.
  
**Per installare un certificato server**
  
1.  Copiare il file del certificato (.cer) nella cartella C:\\Windows\\System32\\CertLog.
  
2.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
3.  Fare clic con il pulsante destro del mouse sul sito Web in cui si desidera installare un certificato server, quindi scegliere **Proprietà**.
  
4.  Fare clic sulla scheda **Protezione directory**. Nella sezione **Comunicazioni protette**, selezionare **Certificato server** per avviare la Gestione guidata certificati server Web, quindi fare clic su **Avanti**.
  
5.  Selezionare **Elabora la richiesta in sospeso e installa il certificato**, quindi fare clic su **Avanti**.
  
6.  Selezionare il certificato ricevuto dalla CA. Fare clic su **Avanti** per due volte, quindi su **Fine**.
  
##### Verifica delle nuove impostazioni
  
Eseguire la procedura seguente per verificare che al computer locale siano state applicate le impostazioni di protezione appropriate.
  
**Per verificare se un certificato è installato in un server Web**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare clic su **Gestione Internet Information Services (IIS)**.
  
2.  Fare clic con il pulsante destro del mouse sul sito Web contenente un certificato che si desidera visualizzare, quindi scegliere **Proprietà**.
  
3.  Nella sezione **Comunicazioni protette** della scheda **Protezione directory** selezionare **Visualizza certificato**, controllare il certificato, quindi fare clic su **OK** per due volte.
  
#### Applicazione e abilitazione delle connessioni SSL nel server Web
  
Dopo aver installato il certificato server è necessario attivare le connessioni SSL nel server Web. Successivamente, le connessioni SSL devono essere abilitate.
  
**Nota**: una volta definite connessioni SSL per il server Web, sarà necessario aggiornare i collegamenti al server in modo da utilizzare https anziché http.
  
##### Requisiti
  
Per completare questa attività è necessario disporre di quanto segue:
  
-   **Credenziali**: è necessario accedere al server Web come membro del gruppo Administrators
  
-   **Strumenti**: Gestione Internet Information Services (IIS) (iis.msc).
  
**Per applicare connessioni SSL**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
2.  Fare clic con il pulsante destro del mouse sul sito Web in cui si desidera applicare le connessioni SSL, quindi scegliere **Proprietà**.
  
3.  Fare clic sulla scheda **Protezione directory**. Nella sezione **Comunicazioni protette**, fare clic su **Modifica**.
  
4.  Selezionare **Richiedi un canale protetto (SSL)**, scegliere un livello di crittografia, quindi fare clic su **OK**.
  
    **Nota**: se viene specificata la crittografia a 128 bit, i computer client che utilizzano browser con crittografia a 40 o 56 bit non potranno comunicare con il sito, a meno che tali browser non vengano aggiornati a versioni che supportano la crittografia a 128 bit.
  
**Per abilitare connessioni SSL nel server Web**
  
1.  Fare clic sul pulsante **Start**, scegliere **Pannello di controllo**, **Strumenti di amministrazione**, quindi fare doppio clic su **Gestione Internet Information Services (IIS)**.
  
2.  Fare clic con il pulsante destro del mouse sul sito Web in cui si desidera abilitare le connessioni SSL, quindi scegliere **Proprietà**.
  
3.  Fare clic sulla scheda **Sito Web**. Nella sezione **Identificazione sito Web**, verificare che nella casella **Porta SSL** sia presente il valore numerico **443**.
  
4.  Fare clic su **Avanzate**. In genere, verranno visualizzate due caselle e la porta e l'indirizzo IP del sito Web saranno riportati nella casella **Identità multiple per questo sito Web**. Se la porta 443 non è già elencata nel campo **Identità SSL multiple per questo sito Web** fare clic su **Aggiungi**. Selezionare l'indirizzo IP del server, digitare il valore numerico **443** nella casella **Porta SSL**, quindi fare clic su **OK**.
  
##### Verifica delle nuove impostazioni
  
Eseguire la procedura seguente per verificare che al server Web siano state applicate le impostazioni di protezione appropriate.
  
**Per verificare connessioni SSL nel server Web**
  
1.  Aprire il browser e provare a connettersi al server Web tramite il protocollo http:// standard. Ad esempio, nella casella **Indirizzo** digitare **http://localhost** e premere INVIO.
  
    Se SSL è applicato, verrà visualizzato il seguente messaggio di errore:
  
    **La pagina deve essere visualizzata su un canale protetto. La pagina a cui si sta tentando di accedere è protetta con Secure Sockets Layer (SSL).**
  
2.  Riprovare a connettersi alla pagina che si desidera visualizzare digitando **https://localhost** e premendo INVIO.
  
    Verrà visualizzata la pagina predefinita per il server Web in uso.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Informazioni correlate
  
Per ulteriori informazioni sulla protezione di IIS 6.0, consultare quanto segue:
  
-   "[Security Enhancements in Internet Information Services 6.0](http://www.microsoft.com/windowsserver2003/techinfo/overview/iisenhance.mspx)" nel sito Web Microsoft Windows Server 2003 all'indirizzo www.microsoft.com/windowsserver2003/techinfo/overview/iisenhance.mspx (in inglese).
  
-   "[Configuring Application Isolation on Windows Server 2003 and Internet Information Services (IIS) 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=bb24823c-4299-4437-913a-ea1cc48c1699&displaylang=en)" nel sito Web Microsoft TechNet all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/  
    webapp/iis/appisoa.mspx (in inglese).
  
-   Webcast TechNet "Effectively Using IIS 6.0 Security" nella pagina Web Microsoft [Internet Information Services Webcasts](http://www.microsoft.com/windowsserver2003/iis/support/webcasts.mspx) all'indirizzo www.microsoft.com/windowsserver2003/iis/support/webcasts.mspx (in inglese).
  
Per ulteriori informazioni su IIS 6.0, consultare quanto segue:
  
-   [Internet Information Services (IIS) 6.0 Resource Kit](http://www.microsoft.com/downloads/details.aspx?familyid=80a1b6e6-829e-49b7-8c02-333d9c148e69&displaylang=en), disponibile nell'Area download Microsoft all'indirizzo www.microsoft.com/downloads/details.aspx?familyid=80a1b6e6-829e-49b7-8c02-333d9c148e69&displaylang=en (in inglese).
  
-   "[Technical Overview of Internet Information Services (IIS) 6.0](http://www.microsoft.com/windowsserver2003/techinfo/overview/iis.mspx)" nel sito Web Microsoft Windows Server 2003 all'indirizzo www.microsoft.com/windowsserver2003/techinfo/overview/iis.mspx (in inglese).
  
**Download**
  
[Download della guida Protezione di Internet Information Services 6.0](http://download.microsoft.com/download/7/3/e/73e69052-e497-4b00-b2a6-62e43af6f3f6/securing%20internet%20information%20services%206.0.doc)
  
[](#mainsection)[Inizio pagina](#mainsection)
