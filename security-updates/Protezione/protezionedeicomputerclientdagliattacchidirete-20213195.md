---
TOCTitle: Protezione dei computer client dagli attacchi di rete
Title: Protezione dei computer client dagli attacchi di rete
ms:assetid: 'f3e96a10-4eb6-4a41-8040-d5af55edf694'
ms:contentKeyID: 20213195
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc875823(v=TechNet.10)'
---

Protezione dei computer client dagli attacchi di rete
=====================================================

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Prima di iniziare](#eeaa)
[](#edaa)[Windows Live OneCare](#edaa)
[](#ecaa)[Windows Defender](#ecaa)
[](#ebaa)[Windows Firewall](#ebaa)
[](#eaaa)[Informazioni correlate](#eaaa)

### Introduzione

Molte organizzazioni si affidano fortemente ai propri firewall di rete per proteggere workstation e server dalle minacce di Internet. Questo approccio presenta una flessibilità interna e una rigidità esterna. Microsoft consiglia l'utilizzo di un firewall di rete e delle funzionalità di protezione delle workstation illustrati nella parte restante del presente documento. L'approccio in questione offre maggiore protezione rispetto a quello in cui la rigidità è applicata sia all'interno che all'esterno. La propagazione dei worm di rete nei firewall delle organizzazioni ha dimostrato come i firewall non siano sufficienti in queste situazioni.

I pirati informatici su Internet creano worm e virus in grado di distruggere le informazioni archiviate nei computer client o di causarne la perdita o il furto. Gli attacchi di questo tipo possono determinare la perdita di informazioni riservate e di segreti aziendali, impedire l'avvio di computer e persino consentire l'avvio di attacchi mirati ad altri computer rappresentando un pericolo estremamente concreto per i computer connessi a Internet.

La maggior parte dei metodi di attacco cerca di trarre vantaggio dai problemi noti di protezione dei computer. L'implementazione delle funzionalità seguenti può garantire una protezione notevole per i computer client che eseguono il sistema operativo Microsoft Windows XP con Service Pack 2 (SP2):

-   Firewall personale (Windows Firewall)

-   Aggiornamento di Service Pack e patch (aggiornamento automatico)

-   Software antivirus con firme aggiornate (Windows Live OneCare)

-   Software antispyware con firme aggiornate (Windows Defender)

#### Obiettivo del documento

Al termine della lettura del presente documento, l'utente avrà acquisito familiarità con gli strumenti e le funzionalità offerte da Microsoft per aumentare la protezione dei computer client che eseguono Windows XP SP2 nel contesto di una rete aziendale di medie dimensioni.

[](#mainsection)[Inizio pagina](#mainsection)

### Prima di iniziare

Prima di seguire i consigli forniti in questo documento, occorre tenere presente le informazioni seguenti.

#### Credenziali necessarie

Per la maggior parte delle attività descritte in questo documento è necessario un account amministrativo. Un utente standard non è infatti in grado di eseguirle.

#### Consigli

Microsoft consiglia di aggiornare tutte le workstation Windows a Windows XP SP2 in quanto contiene le funzionalità di protezione più recenti, molte delle quali sono attivate per impostazione predefinita.

Microsoft consiglia inoltre di aggiornare tutte le versioni delle installazioni esistenti di Internet Explorer alla versione più recente.

#### Impostazioni predefinite

Le impostazioni di protezione predefinite presenti negli strumenti illustrati in questo documento sono le scelte consigliate da Microsoft e sono state definite per bilanciare la funzionalità e la protezione di Windows XP SP2. Molte organizzazioni presentano requisiti di protezione specifici. Tutte le funzionalità di protezione possono essere configurate o disattivate.

[](#mainsection)[Inizio pagina](#mainsection)

### Windows Live OneCare

Microsoft mette a disposizione Windows Live OneCare, un servizio di manutenzione dei PC che si aggiorna automaticamente e viene eseguito in background. Esso fornisce una protezione costante contro virus, pirati informatici e altre minacce, nonché consente di ottimizzare il computer ed effettuare il backup dei documenti importanti. Per ulteriori informazioni, vedere [Windows Live OneCare](http://www.windowsonecare.com/) all'indirizzo www.windowsonecare.com/ (in inglese).

Windows Live OneCare offre un'unica console per controllare lo stato dei diversi servizi legati alla protezione nella workstation Windows XP. Nell'unica schermata vengono indicati lo stato della protezione da virus, i livelli di patch, lo stato del sistema e l'ultimo aggiornamento dei dati.

#### Protezione da virus

I virus informatici sono programmi software ideati deliberatamente per interferire con il funzionamento dei computer. Sono in grado di registrare, danneggiare o eliminare dati e di diffondersi in altri computer e attraverso Internet, spesso rallentando i processi e provocando altri problemi.

Anche i virus informatici, esattamente come quelli che affliggono gli essere umani, da Ebola alla banale influenza, hanno livelli di gravità estremamente diversi; possono creare piccoli problemi o distruggere il sistema. Possono inoltre assumente forme nuove e diverse. Tuttavia, adottando le opportune misure di prevenzione è possibile evitare di cadere vittima di tali pericoli e di ridurne l'impatto.

Grazie a Windows Live OneCare, le firme antivirus e le patch di protezione del sistema operativo vengono aggiornate automaticamente e il computer viene mantenuto aggiornato senza alcun intervento manuale.

Per un [elenco dei fornitori software](http://support.microsoft.com/kb/49500) che offrono programmi antivirus compatibili con Windows XP, visitare il sito Web all'indirizzo http://support.microsoft.com/kb/49500.

#### Monitoraggio del firewall

Windows Firewall funziona in un singolo computer consentendone la protezione dai pirati informatici all'invio o alla ricezione di file. Windows Live OneCare consente il monitoraggio continuo di Windows Firewall.  

#### Windows Defender

Windows Defender può essere scaricato dal sito Web Microsoft e consente di proteggere da attacchi Internet le informazioni riservate presenti nei computer. Windows Live OneCare consente di monitorare lo stato di Windows Defender.

#### Aggiornamenti

Windows Live OneCare viene aggiornato automaticamente per garantire che la protezione da virus, firewall e spyware sia sempre attuale e in grado di affrontare i pericoli più recenti.

#### Backup e ripristino dei file

Con Windows Live OneCare è possibile eseguire copie di file e documenti importanti, nonché archiviarli in un'unità CD, DVD o in un disco rigido esterno in caso di emergenza. Queste operazioni possono essere eseguite manualmente o è possibile impostarne l'esecuzione automatica in modo da evitare di effettuare il backup regolare di file e documenti. In caso di problemi, Windows Live OneCare consente inoltre di ripristinare i file sottoposti a backup nel computer.

[](#mainsection)[Inizio pagina](#mainsection)

### Windows Defender

Lo spyware viene spesso associato al software che visualizza annunci, definito adware, o al software che tiene traccia di informazioni personali o riservate. Ciò non significa che tutti i programmi software pubblicitari o tali da rilevare le attività in linea degli utenti siano dannosi. È ad esempio possibile sottoscrivere un servizio musicale gratuito accettando tuttavia di ricevere annunci pubblicitari mirati. Se le condizioni vengono comprese e accettate, l'accordo è del tutto equo. È inoltre possibile accettare che l'azienda rilevi le attività in linea per individuare gli annunci pubblicitari da visualizzare.

Altri tipi di software indesiderato possono apportare modifiche fastidiose al computer tali da provocarne il rallentamento o l'arresto anomalo. Questi programmi sono in grado di modificare la pagina iniziale o la pagina di ricerca del browser Web o di aggiungere componenti al browser non necessari o non desiderati complicando inoltre il ripristino delle impostazioni originali del computer. Questi tipi di programmi indesiderati sono spesso denominati spyware.

Windows Defender (Beta2) è una tecnologia di protezione che consente di proteggere gli utenti di Windows da spyware e altro software potenzialmente dannoso. È possibile individuare e rimuovere le applicazioni spyware conosciute eventualmente presenti nel computer per ridurne gli effetti negativi, ovvero la diminuzione delle prestazioni, la visualizzazione di fastidiose finestre pubblicitarie popup, le modifiche indesiderate alle impostazioni Internet e l'utilizzo non autorizzato di informazioni riservate. La protezione costante aumenta la sicurezza dell'esplorazione di Internet sorvegliando oltre 50 dei modi in cui lo spyware può accedere ai computer. I membri della community SpyNet, diffusa in tutto il mondo, svolgono un ruolo fondamentale nel determinare quali programmi sospetti vengono classificati come spyware e i ricercatori Microsoft sviluppano rapidamente metodi per contrastare queste minacce; gli aggiornamenti vengono scaricati automaticamente nel PC che, quindi, è sempre aggiornato.

È possibile scaricare [Windows Defender](http://www.microsoft.com/italy/athome/security/spyware/software/default.mspx) all'indirizzo http://www.microsoft.com/italy/athome/security/spyware/software/default.mspx. La versione corrente è la Beta 2. Il nome del file è WindowsDefender.msi e le sue dimensioni sono pari a circa 5,5 MB. Il nome del file e le dimensioni potrebbero variare in seguito al rilascio della versione definitiva.

Per installare Windows Defender (Beta 2) dopo il download, eseguire la procedura seguente.

1.  Al termine del download di Windows Defender (Beta 2), verrà visualizzata la finestra di dialogo seguente. Fare clic su **Esegui**.

    ![](images/Cc875823.PCNA01(it-it,TechNet.10).gif)

2.  Verrà visualizzata la schermata **Welcome to the Installation Wizard for Windows Defender** (Installazione guidata di Windows Defender) seguente. Fare clic su **Avanti**.

    ![](images/Cc875823.PCNA02(it-it,TechNet.10).gif)

3.  Verrà visualizzata la schermata **Windows Defender License Agreement** (Contratto di licenza per Windows Defender), illustrata nella figura seguente. Leggere le condizioni del contratto.

    Per continuare l'installazione, è necessario selezionare **I accept the terms in the license agreement** (Accetto i termini del contratto di licenza) e fare clic su **Avanti**.

    ![](images/Cc875823.PCNA03(it-it,TechNet.10).gif)

4.  Nella schermata **Help protect Windows** (Protezione di Windows), illustrata nella figura seguente, selezionare **Use recommended settings** (Usa impostazioni consigliate). Fare clic sul pulsante **Privacy Statement** (Informativa sulla privacy), se lo si desidera, quindi fare clic su **Avanti**.

    ![](images/Cc875823.PCNA04(it-it,TechNet.10).gif)

5.  Nella schermata **Setup Type** (Tipo di installazione), illustrata nella figura seguente, selezionare **Complete** (Completa) e fare clic su **Avanti**.

    ![](images/Cc875823.PCNA05(it-it,TechNet.10).gif)

6.  Nella schermata **Ready to Install Windows Defender** (Installazione di Windows Defender) che verrà visualizzata, fare clic su **Install** (Installa) per avviare l'installazione.

    ![](images/Cc875823.PCNA06(it-it,TechNet.10).gif)

7.  Al termine dell'installazione, verrà visualizzata la schermata **Windows Defender Installation Complete** (Installazione di Windows Defender completata).

    Verificare che l'opzione **Check for updated definitions and run a quick scan now** (Verifica la disponibilità di definizioni aggiornate ed esegui un'analisi veloce) sia selezionata, quindi fare clic su **Fine**.

    **Nota**   Per l'esecuzione di questo passaggio è necessaria la connessione a Internet.

    ![](images/Cc875823.PCNA07(it-it,TechNet.10).gif)

8.  Nella schermata seguente fare clic sul pulsante **Check for Updates** (Controlla aggiornamenti) per ottenere aggiornamenti recenti.

    [![](images/Cc875823.PCNA08(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875823.pcna08_big(it-it,technet.10).gif)

Per ulteriori dettagli e informazioni sulle funzionalità avanzate di Windows Defender (Beta 2), visitare il sito Web [Windows Defender (Beta 2)](http://www.microsoft.com/italy/athome/security/spyware/software/default.mspx) all'indirizzo http://www.microsoft.com/italy/athome/security/spyware/software/default.mspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Windows Firewall

Un firewall è un sistema di protezione che agisce come una barriera fra una rete e l'esterno. In Windows XP SP2 è incluso Windows Firewall, un software dal funzionamento pressoché analogo in ogni computer client.

Windows Firewall è preinstallato in Windows XP Professional SP2 e presenta numerose possibilità di configurazione. È attivato per impostazione predefinita e facilita la protezione contro attacchi di rete. Windows Live OneCare, inoltre, esegue il monitoraggio di Windows Firewall costituendo un'unica console per il controllo dello stato di protezione globale del computer. Nel prosieguo di questo documento verrà illustrato come modificare le impostazioni di Windows Firewall utilizzando il Centro sicurezza PC Windows, disponibile nel Pannello di controllo.

**Nota**   Windows Firewall non sostituisce le funzionalità di un firewall di rete. La rete Windows è attivata ed è possibile eseguire alcune operazioni nonostante Windows Firewall, ovvero comunicare con altri computer di rete, stampare e accedere a risorse di rete. È tuttavia consigliabile utilizzare un firewall di rete per proteggere le porte aperte nell'esecuzione di queste funzioni.

#### Impostazioni generali

Le impostazioni generali di Windows Firewall consentono di configurare le opzioni seguenti:

-   **Attivato** (impostazione consigliata).

-   **Disattivato** (impostazione non consigliata). La disattivazione di Windows Firewall rende il computer più vulnerabile ai danni provocati da virus, worm o intrusi.

1.  Per aprire il servizio Centro sicurezza PC Windows, fare clic sul pulsante **Start** e quindi scegliere **Pannello di controllo**. Verrà visualizzata la schermata seguente:

    [![](images/Cc875823.PCNA09(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875823.pcna09_big(it-it,technet.10).gif)

2.  Nella sezione **Scegliere una categoria** fare clic su **Centro sicurezza PC**. Verrà visualizzata la schermata **Centro sicurezza PC Windows**, illustrata nella figura seguente.

    [![](images/Cc875823.PCNA10(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875823.pcna10_big(it-it,technet.10).gif)

#### Notifiche di configurazione

Per impostazione predefinita, Windows Firewall visualizza una finestra di dialogo di notifica ogni volta che viene bloccato un tentativo di comunicazione con un altro computer. Questa finestra di dialogo è simile alla schermata illustrata nella figura seguente:

![](images/Cc875823.PCNA11(it-it,TechNet.10).gif)

Nella finestra di dialogo viene indicato il programma bloccato e viene data la possibilità di scegliere se consentirne l'esecuzione. Le opzioni disponibili sono le seguenti:

-   **Continua a bloccare**. Scegliere questa opzione per impedire connessioni non autorizzate al programma da Internet o dalla rete.

-   **Sblocca**. Scegliere questa opzione per inserire il programma nell'elenco di eccezioni di Windows Firewall.

-   **Richiedi in seguito**. Scegliere questa opzione se non è possibile decidere se bloccare o sbloccare il programma. L'opzione mantiene bloccato il programma per maggiore protezione. Il messaggio verrà nuovamente visualizzato al successivo blocco del programma.

#### Esame della modalità con cui le applicazioni utilizzano le porte

Una porta è un punto di connessione utilizzato da un programma per comunicare con altre applicazioni, specialmente con quelle installate in altri computer. Ogni porta viene identificata in base alla combinazione di un trasporto e di un numero. Ad ogni tipo di applicazione o di servizio vengono associate porte specifiche. Ad esempio, la porta standard per un server Web è la porta TCP 80, quella per un server FTP (File Transfer Protocol) è la porta TCP 21 e il servizio Windows Server che assicura la condivisione dei servizi di file e stampa riceve i messaggi tramite quattro porte: le porte UDP 137 e 138 e le porte TCP 139 e 445.

Windows Firewall blocca la ricezione dei messaggi in ingresso non richiesti per tutte le porte. In questo modo si protegge il computer, in quanto vengono bloccati i messaggi utilizzati generalmente dal codice dannoso per ottenere l'accesso. Windows Firewall non interferisce con la maggior parte del software aziendale legittimo poiché, come regola generale, tale software non invia messaggi non richiesti ai computer client.

Poiché i firewall limitano le comunicazioni tra Internet e i computer, può essere necessario modificare le impostazioni per altri programmi che prediligono una connessione aperta. Per fare in modo che tali programmi comunichino attraverso Windows Firewall, è possibile creare eccezioni specifiche.

#### Rischi possibili quando vengono consentite le eccezioni

Ogni volta che viene consentita un'eccezione per fare in modo che un programma comunichi mediante Windows Firewall, il computer viene reso più vulnerabile. Consentire un'eccezione è come creare una falla nel firewall. In presenza di troppe falle, il firewall perde di efficacia. I pirati informatici spesso utilizzano software che analizza Internet alla ricerca di computer con connessioni non protette. Se è presente un numero elevato di eccezioni e di porte aperte, il computer può diventare più vulnerabile.

Per ridurre i rischi di protezione:

-   Consentire un'eccezione solo quando necessario.

-   Non consentire mai un'eccezione per un programma non riconosciuto.

-   Rimuovere un'eccezione quando non è più necessaria.

#### Consentire le eccezioni malgrado i rischi

Talvolta è necessario consentire la connessione a un computer malgrado i rischi di protezione, ad esempio quando è prevista la ricezione di un file inviato mediante un programma di messaggistica immediata su Internet.

Quando si scambiano messaggi immediati con qualcuno che desidera inviare un file, quale un foglio di calcolo, Windows Firewall visualizza un messaggio per richiedere se sbloccare la connessione e consentire il trasferimento del file. In alternativa, è possibile aggiungere il programma di messaggistica immediata come eccezione in modo che Windows Firewall consenta alla connessione di raggiungere il computer.

Per aggiungere un programma all'elenco delle eccezioni, eseguire la procedura seguente.

1.  Fare clic sul pulsante **Start**, quindi scegliere **Pannello di controllo**.

2.  In Pannello di controllo fare clic su **Centro sicurezza PC** e quindi scegliere **Windows Firewall**.

3.  Nella scheda **Eccezioni**, in **Programmi e servizi**, come illustrato nella figura seguente, selezionare la casella di controllo relativa al programma o al servizio da consentire, quindi scegliere **OK**.

    ![](images/Cc875823.PCNA12(it-it,TechNet.10).gif)

Se il programma o il servizio da consentire non è presente nell'elenco:

1.  Scegliere **Aggiungi programma**.

2.  Nella finestra di dialogo **Aggiunta programma** selezionare il programma da aggiungere e scegliere **OK**.

3.  Scegliere **OK**.

**Suggerimento**   Se il programma o il servizio da consentire non è elencato nella finestra di dialogo **Aggiunta programma**, scegliere **Sfoglia**, individuare il programma da aggiungere e fare doppio clic su di esso. Di solito i programmi vengono archiviati nella cartella Programmi del computer. Il programma verrà visualizzato in **Programmi** nella finestra di dialogo **Aggiunta programma**.

#### Ultimo tentativo: apertura di una porta

Se non si riesce a individuare il programma, è possibile aprire una porta nel firewall attraverso la quale consentire il passaggio delle comunicazioni. Per specificare la porta da aprire, nella scheda **Eccezioni** scegliere **Aggiungi porta**. Quando si apre una porta, è necessario chiuderla dopo averla utilizzata.

L'aggiunta di un'eccezione è preferibile all'apertura di una porta per i motivi seguenti:

-   È più semplice da eseguire.

-   Non è necessario conoscere il numero di porta da utilizzare.

-   L'aggiunta di un'eccezione è più sicura dell'apertura di una porta, in quanto il firewall rimane aperto solo durante l'attesa di ricezione di una connessione per il programma.

#### Opzioni avanzate

Gli utenti avanzati possono aprire porte per le singole connessioni e configurarne l'ambito in modo da ridurre le possibilità per eventuali intrusi di connettersi a un computer o una rete. A tale scopo, aprire Windows Firewall, fare clic sulla scheda **Avanzate** e utilizzare le impostazioni presenti in **Impostazioni connessione di rete**.

Per ulteriori informazioni sulle funzionalità avanzate, vedere [Informazioni su Windows Firewall](http://www.microsoft.com/italy/windowsxp/using/security/internet/sp2_wfintro.mspx) all'indirizzo www.microsoft.com/italy/windowsxp/using/security/internet/sp2\_wfintro.mspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Informazioni correlate

Per ulteriori informazioni sull'apertura delle porte, vedere quanto segue:

-   [Network Ports Used by Key Microsoft Server Products](http://www.microsoft.com/smallbusiness/support/articles/ref_net_ports_ms_prod.mspx) nel sito Web Microsoft Small Business Center all'indirizzo www.microsoft.com/smallbusiness/support/articles/ref\_net\_ports\_ms\_prod.mspx (in inglese).

-   [Port Numbers](http://www.iana.org/assignments/port-numbers) disponibile nel sito Web Internet Assigned Numbers Authority all'indirizzo www.iana.org/assignments/port-numbers (in inglese).

Per ulteriori informazioni generali sui firewall, vedere quanto segue:

-   "[Funzionalità modificate in Microsoft Windows XP Service Pack 2 Parte 2: Tecnologie di protezione della rete](http://technet.microsoft.com/en-us/library/bb457156.aspx)" nel sito Web Microsoft TechNet all'indirizzo http://www.microsoft.com/technet/prodtechnol/winxppro/it/maintain/sp2netwk.mspx.

Per ulteriori informazioni sulla protezione di Windows XP SP2, consultare la risorsa seguente:

-   [*Windows XP Security Guide*](http://go.microsoft.com/fwlink/?linkid=35309), disponibile nell'Area download Microsoft all'indirizzo http://go.microsoft.com/fwlink/?linkid=35309 (in inglese).

Per conoscere le definizioni dei termini correlati alla protezione, consultare la risorsa seguente:

-   [Microsoft Security Glossary](http://go.microsoft.com/fwlink/?linkid=35468), disponibile nel sito Web Microsoft all'indirizzo http://go.microsoft.com/fwlink/?LinkId=35468 (in inglese).

**Download**

[Download della guida Protezione dei computer client dagli attacchi di rete](http://go.microsoft.com/fwlink/?linkid=70393)

[](#mainsection)[Inizio pagina](#mainsection)
