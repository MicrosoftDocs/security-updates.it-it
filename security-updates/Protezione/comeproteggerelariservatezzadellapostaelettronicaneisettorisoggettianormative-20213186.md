---
TOCTitle: Come proteggere la riservatezza della posta elettronica nei settori soggetti a normative
Title: Come proteggere la riservatezza della posta elettronica nei settori soggetti a normative
ms:assetid: '1c41144a-813b-4a0d-b982-4060269eacfb'
ms:contentKeyID: 20213186
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc875813(v=TechNet.10)'
---

Come proteggere la riservatezza della posta elettronica nei settori soggetti a normative
========================================================================================

##### In questa pagina

[](#ecaa)[Introduzione](#ecaa)
[](#ebaa)[Scenario su come agevolare la protezione della riservatezza della posta elettronica](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

Tutte le organizzazioni devono attualmente affrontare importanti problemi legali e normativi nei settori riguardanti la protezione, la privacy e l'affidabilità delle informazioni. Questi problemi possono richiedere modifiche significative ai sistemi e ai processi di un'organizzazione. Le aziende devono reagire e pianificare la struttura e le normative crescenti riguardanti le responsabilità e il controllo, allo scopo di soddisfare i molti obiettivi legali ed etici. Per conformità si intende il rispetto di tutti i requisiti legali e aziendali che un'organizzazione deve affrontare e dimostrare nello svolgimento delle proprie operazioni e dei propri affari. Si intende, inoltre, la comprensione della struttura legale in cui sono validi i suddetti requisiti legali e aziendali. Il rispetto della conformità coinvolge tutti i reparti aziendali e ogni singolo dipendente. Non è possibile ottenere la conformità mediante l'implementazione di una singola soluzione o di un singolo processo, essa deve essere incorporata in ogni segmento aziendale di un'organizzazione.

L'ambiente normativo diventa sempre più complesso. Spesso la conformità non è un processo semplice e le normative variano in base alla specificità dei singoli requisiti. Di conseguenza, un'organizzazione deve effettuare una valutazione completa dei rischi e dell'impatto.

Lo scopo di questo white paper è descrivere alcuni dei processi e delle tecnologie di cui le aziende si possono avvalere per agevolare la standardizzazione e la velocizzazione delle attività relative alla conformità normativa per quanto riguarda la riservatezza della posta elettronica. Vengono illustrate anche le risorse e le opzioni che molte aziende di piccole e medie dimensioni possono incontrare nel percorso verso la conformità alle leggi e alle normative. Il presente white paper non è una roadmap della conformità normativa, né è volto a fornire consigli legali sulle suddette questioni. I lettori devono rivolgersi ai propri consulenti e avvocati prima di avviare qualsiasi eventuale programma o processo di conformità.

#### Destinatari della guida

Il pubblico a cui si rivolge la presente guida include i professionisti dell'IT responsabili dell'installazione, della manutenzione e della gestione di un servizio di posta elettronica, all'interno degli ambienti di rete, basato su Microsoft® Exchange Server 2003.

Le informazioni contenute in questa guida sono applicabili alle aziende di piccole e medie dimensioni che devono consegnare messaggi di posta elettronica riservati in rete.

#### panoramica

Sebbene le funzioni di protezione dei messaggi siano presenti in Microsoft Exchange Server fin dalla prima versione del prodotto, solitamente queste funzioni sono state utilizzate soltanto dai clienti con requisiti di protezione specifici e dal personale addetto alla protezione. Soltanto gli specialisti della protezione e le persone con un background di crittografia avevano la necessità di comprendere i concetti relativi alla protezione dei messaggi di posta elettronica. Con il supporto aumentato per S/MIME (Secure/Multipurpose Internet Mail Extensions) in Exchange Server 2003 e le necessità relative alla conformità normativa, anche gli amministratori hanno cominciato a sentire la necessità di comprendere tali principi e concetti.

Il Feature Pack per la messaggistica e la protezione per Windows Mobile 5.0 offre il supporto per i certificati S/MIME sugli smartphone. Inoltre, il Service Pack per Microsoft Exchange Server 2003 2 (SP2) offre il supporto per S/MIME in Microsoft Outlook® Web Access (OWA).

Il presente white paper contiene un'introduzione a S/MIME e ai concetti correlati e fornisce una guida normativa su come implementare S/MIME. Non è richiesta esperienza nell'ambito della protezione. In questo documento vengono illustrati i concetti generali di S/MIME affinché sia possibile applicarli in maniera specifica a Exchange Server.

##### Vantaggi di S/MIME

Prima che esistesse S/MIME, gli amministratori utilizzavano, per il trasferimento dei messaggi, un protocollo di posta elettronica largamente accettato, ovvero SMTP (Simple Mail Transfer Protocol), che era intrinsecamente meno sicuro. Altrimenti potevano utilizzare soluzioni più sicure ma proprietarie. In sostanza, erano obbligati a scegliere una soluzione che enfatizzasse la sicurezza o la connettività. Adesso, grazie a S/MIME, gli amministratori dispongono di un'opzione di posta elettronica che aiuta a fornire una maggiore protezione rispetto a quella offerta da SMTP, abilitando così una connettività per posta elettronica diffusa e sicura.

S/MIME fornisce due servizi di protezione:

-   Firme digitali

-   Crittografia dei messaggi

Questi due servizi rappresentano il fulcro della protezione dei messaggi basata su S/MIME. Tutti gli altri concetti relativi alla protezione dei messaggi supportano questi due servizi. Sebbene l'ambito della protezione dei messaggi possa sembrare complesso nel suo insieme, questi due servizi rappresentano la base di questa attività.

Le firme digitali e la crittografia dei messaggi non sono servizi che si escludono reciprocamente. Ciascun servizio è mirato a risolvere problemi di protezione specifici. Le firme digitali risolvono i problemi di autenticazione e ripudio, mentre la crittografia dei messaggi risolve i problemi di riservatezza. Poiché ogni servizio si occupa di problemi diversi, una strategia di protezione dei messaggi richiede l'ausilio di entrambi, spesso contemporaneamente. Questi due servizi sono stati concepiti per essere utilizzati insieme, perché ciascuno di essi risolve, separatamente, un aspetto del rapporto mittente-destinatario. Le firme digitali risolvono i problemi di protezione relativi ai mittenti, mentre la crittografia si occupa principalmente dei problemi di protezione relativi ai destinatari.

Se le firme digitali e la crittografia dei messaggi vengono utilizzati insieme, gli utenti beneficiano di entrambi i servizi. L'impiego di entrambi i servizi nei messaggi non comporta modifiche alla gestione o all'elaborazione di nessuno dei due servizi.

###### Firme digitali

Le firme digitali sono il servizio più comunemente utilizzato di S/MIME. Come suggerisce il nome, le firme digitali sono l'equivalente digitale della tradizionale firma legale su un documento cartaceo. Come la firma legale, le firme digitali offrono le seguenti capacità di protezione:

-   **Autenticazione**. Una firma serve a convalidare un'identità. Fornisce la risposta alla domanda: "chi sei?", offrendo un mezzo per differenziare un'entità da tutte le altre e affermando che proviene da un fonte considerata reciprocamente attendibile. Poiché in un messaggio di posta elettronica SMTP non esiste autenticazione, non è possibile sapere chi abbia effettivamente inviato il messaggio. L'autenticazione di una firma digitale aiuta a risolvere questo problema permettendo al destinatario di sapere che un messaggio è stato inviato dalla persona o dall'organizzazione che afferma di averlo inviato.

-   **Non ripudio**. L'univocità di una firma aiuta a impedire che il proprietario della firma disconosca la propria firma. Questa capacità viene definita non ripudio. Quindi, l'autenticazione che una firma è in grado di fornire permette di applicare il non ripudio. Il concetto di non ripudio è maggiormente noto nel contesto dei contratti cartacei. Un contratto firmato è legalmente vincolante ed è più difficile disconoscere una firma autenticata. Le firme digitali hanno la stessa funzione e, in alcuni settori sempre in maniera crescente, vengono riconosciute legalmente vincolanti proprio come la firma apposta su un documento cartaceo. Poiché la posta elettronica SMTP non fornisce metodi di autenticazione, non può offrire capacità di non ripudio. Per un mittente è semplice disconoscere la proprietà di un messaggio di posta elettronica inviato con SMTP.

-   **Integrità dei dati**. Un servizio aggiuntivo di protezione offerto dalle firme digitali è l'integrità dei dati. L'integrità dei dati è il risultato delle operazioni specifiche che rendono possibili le firme digitali. Grazie ai servizi di integrità dei dati, quando il destinatario di un messaggio di posta elettronica con firma digitale convalida tale firma, il destinatario aiuta a garantire che il messaggio ricevuto è esattamente lo stesso messaggio firmato e inviato e che non è stato alterato durante il trasferimento. Qualsiasi alterazione del messaggio durante il trasferimento, dopo che è stato firmato invalida la firma stessa. In questo modo, le firme digitali possono aiutare a fornire una garanzia che le firme su carta non possono offrire, poiché è possibile alterare un documento cartaceo anche dopo che è stato firmato.

###### Crittografia dei messaggi

La crittografia dei messaggi offre una soluzione al problema della divulgazione delle informazioni. La posta elettronica inviata su Internet tramite SMTP non protegge i messaggi. Un messaggio di posta elettronica inviato su Internet tramite SMTP può essere letto da chiunque lo veda durante il trasferimento o lo visualizzi dalla posizione di archiviazione. Grazie S/MIME è possibile risolvere questi problemi utilizzando la crittografia.

La crittografia è un modo per modificare le informazioni in modo tale che non siano leggibili o comprensibili finché non vengono nuovamente convertite in formato leggibile e comprensibile.

Sebbene la crittografia dei messaggi non sia così largamente usata come le firme digitali, essa risolve il problema che molte persone percepiscono come il punto più debole della posta elettronica su Internet. La crittografia dei messaggi offre due servizi di protezione specifici:

-   **Riservatezza**. La crittografia dei messaggi aiuta a proteggere i contenuti di un messaggio di posta elettronica. Solo il destinatario a cui è indirizzato può visualizzarne i contenuti, che rimangono riservati e vengono resi noti esclusivamente a chi riceve o visualizza il messaggio. Grazie alla crittografia la riservatezza dei messaggi viene protetta sia durante il trasferimento che in archivio.

-   **Integrità dei dati**. Come accade con le firme digitali, la crittografia dei messaggi offre servizi di integrità dei dati come conseguenza dalle operazioni che rendono possibile la crittografia.

##### Requisiti S/MIME

Allo scopo di assicurare la riservatezza della posta elettronica, l'ambiente aziendale necessita di particolari componenti software. In questa sezione vengono descritti tali componenti.

###### PKI (Public Key Infrastructure)

Le soluzioni S/MIME richiedono che una PKI fornisca certificati digitali con coppie di chiavi pubbliche/private e abiliti il mapping dei certificati nel servizio directory Active Directory®. Lo standard S/MIME specifica che i certificati digitali utilizzati per S/MIME siano conformi allo standard ITU (International Telecommunications Union) X.509. La versione 3 di S/MIME richiede in maniera specifica che i certificati digitali siano conformi alla versione 3 dello standard X.509. Poiché S/MIME si basa su uno standard stabilito e riconosciuto per la struttura dei certificati digitali, lo standard S/MIME si basa sulla crescita di tale standard e, in questo modo, estende la sua accettazione.

Una PKI per il supporto di S/MIME può essere implementata in uno dei due modi seguenti: fornitura dell'infrastruttura interna per certificati in un'organizzazione esterna o uso di Certificate Services in Microsoft Windows Server™ 2003.

Per ulteriori informazioni sui Certificate Services in Windows Server 2003, visitare il sito Web [Public Key Infrastructure for Windows Server 2003](http://www.microsoft.com/windowsserver2003/technologies/pki/default.mspx) (in inglese) all'indirizzo www.microsoft.com/windowsserver2003/technologies/pki/default.mspx.

La PKI deve disporre di un meccanismo che si occupi della revoca dei certificati. La revoca è necessaria alla scadenza del certificato oppure quando un utente malintenzionato può averne compromessa l'affidabilità. Con la revoca di un certificato, un amministratore nega l'accesso a chiunque utilizzi il certificato. Ogni certificato comprende l'ubicazione del proprio elenco di revoche di certificati, denominato CRL (Certificate Revocation List).

Per ulteriori informazioni su come gestire la revoca dei certificati, leggere l'argomento [Manage Certificate Revocation](http://technet2.microsoft.com/windowsserver/en/library/de0ae267-14e6-46f8-bcc7-8ac480889b951033.mspx?mfr=true) (in inglese) all'indirizzo http://technet2.microsoft.com/WindowsServer/en/Library/de0ae267-14e6-46f8-bcc7-8ac480889b951033.mspx

###### Modelli di certificati

Windows Server 2003 fornisce dei modelli di certificati specifici per emettere i certificati digitali da utilizzare con S/MIME. Per emettere certificati per la posta elettronica protetta è possibile utilizzare tre modelli di certificati utente multifunzione.

-   **Amministratore**. Permette a un amministratore di utilizzare un certificato per l'autenticazione, la crittografia EFS (Encrypted File System), la posta elettronica protetta e la firma dell'elenco scopi consentiti dei certificati.

-   **Utente**. Permette a un utente di utilizzare un certificato per l'autenticazione, la crittografia EFS e la posta elettronica protetta.

-   **Utente smart card**. Permette a un utente di accedere con una smart card e firmare la posta elettronica. Inoltre, questo certificato consente l'autenticazione client.

**Nota**   Microsoft consiglia vivamente di eseguire l'aggiornamento di una PKI Windows Server 2003 corrente a Windows Server 2003 con il Service Pack 1 (SP1) PKI per beneficiare delle funzioni di protezione migliorate.

Per ulteriori informazioni sui modelli dei certificati, vedere l'argomento [Certificate Templates](http://technet2.microsoft.com/windowsserver/en/library/7d82b420-10ef-4f20-a56f-17ee7ee352d21033.mspx) (in inglese) su Microsoft TechNet, all'indirizzo http://technet2.microsoft.com/windowsserver/en/library/7D82B420-10EF-4F20-A56F-17EE7EE352D21033.mspx.

###### Active Directory

Active Directory è un componente fondamentale per l'implementazione dei certificati S/MIME. Per distribuire agli utenti i certificati da utilizzare con i servizi di posta elettronica, un amministratore può avvalersi della funzione di registrazione automatica Criteri di gruppo di Active Directory. Inoltre, Active Directory di Windows Server 2003 contiene il supporto incorporato come directory PKI per molti client di posta elettronica Microsoft, inclusi Outlook, Outlook Express e OWA (Outlook Web Access) con S/MIME e la capacità di associare gli account utente ai certificati.

Per ulteriori informazioni sul mapping dei certificati, vedere l'argomento [Map certificates to user accounts](http://technet2.microsoft.com/windowsserver/en/library/0539dcf5-82c5-48e6-be8a-57bca16c7e171033.mspx?mfr=true) (in inglese) all'indirizzo http://technet2.microsoft.com/WindowsServer/en/library/0539dcf5-82c5-48e6-be8a-57bca16c7e171033.mspx?mfr=true.

###### Exchange Server 2003

Grazie al supporto per una serie di client di posta elettronica fornito da Exchange Server 2003, gli amministratori possono personalizzare la distribuzione in modo da soddisfare le esigenze specifiche. Il supporto S/MIME per i client di Exchange Server 2003 è simile al supporto client generico, poiché gli utenti possono utilizzare simultaneamente qualsiasi client supportato. Quindi, una soluzione Exchange Server 2003 basata su S/MIME può supportare simultaneamente i client Outlook, OWA e Outlook Express, utilizzando POP3. Tuttavia, poiché il client di posta elettronica deve supportare la versione 3 di S/MIME e deve essere un client supportato da Exchange Server, non tutti i client di posta elettronica possono essere S/MIME.

S/MIME viene fornito anche con Exchange Server 2000 ed Exchange Server 2007.

##### Client di posta elettronica

Exchange Server 2003 supporta i client S/MIME mediante il supporto esistente per i protocolli client. Se un client supportato dispone del supporto per S/MIME, tale client può essere utilizzato con Exchange Server 2003. Se il client non supporta la versione 3 di S/MIME, tale client può comunque essere utilizzato per leggere i messaggi con firma non crittografati.

###### Microsoft Outlook 2003

Outlook supporta la connettività MAPI (Messaging Application Programming Interface) per Exchange Server 2003. Inoltre, Outlook può collegarsi utilizzando POP3 e IMAP4. Exchange Server 2003 S/MIME può essere utilizzato con qualsiasi versione di Outlook che supporti i certificati digitali X.509 V.3. Il supporto completo di Outlook per i certificati digitali X.509 V.3 è stato introdotto per la prima volta con Outlook 2000 Service Release 1 (SR-1).

###### Client POP3 e IMAP4

Exchange Server 2003 offre il supporto completo per i client S/MIME tramite i protocolli standard di posta elettronica per Internet POP3 e IMAP4 se il client di posta elettronica supporta S/MIME versione 2 o versione 3. Qualsiasi client di posta elettronica che supporti S/MIME versione 2 o versione 3, oppure POP3 o IMAP4, può essere utilizzato come client di posta elettronica in un sistema di protezione dei messaggi di Exchange Server 2003. Poiché qualsiasi client di posta elettronica che supporti lo standard S/MIME fornisce il supporto completo per tutti i servizi di protezione dei messaggi, questi client possono essere utilizzati come client di posta elettronica con funzioni complete. Microsoft fornisce il supporto della versione 3 di S/MIME nei client POP3 e IMAP4 sia con Outlook Express 5.5 e versioni successive che con Outlook 2000 SR-1a e versioni successive.

**Nota**   I diversi standard Internet e client di posta elettronica hanno i propri requisiti e metodi di gestione dei certificati X.509 V.3. È importante conoscere questi requisiti e i problemi di compatibilità quando si deve decidere quali client di posta elettronica saranno supportati.

##### Considerazioni operative

Dopo avere implementato e verificato gli elementi di questa soluzione, si suggerisce di considerare una serie di attività costanti per garantire che la soluzione continui a funzionare correttamente per proteggere la riservatezza della posta elettronica.

Tra le considerazioni operative sono incluse:

-   **Applicazione dei service pack**. Tra i miglioramenti di Exchange Server SP2 sono incluse le funzioni di filtro posta indesiderata. Per ulteriori informazioni, vedere l'argomento [Anti-Spam Enhancements in Exchange Server 2003 Service Pack 2](http://go.microsoft.com/fwlink/?linkid=55849) (in inglese) su TechNet, all'indirizzo http://go.microsoft.com/fwlink/?linkid=55849.

-   **Applicazione degli aggiornamenti di protezione più recenti**. Tutti i server vengono protetti grazie agli aggiornamenti del Microsoft Download Center.

-   **Prevenzione dei problemi tecnici**. Visitando regolarmente [Microsoft Update](http://update.microsoft.com/) all'indirizzo http://update.microsoft.com/ è possibile scaricare e installare altri aggiornamenti di protezione per Exchange Server e Windows Server.

-   **Esecuzione di MBSA (Microsoft Baseline Security Analyzer)**. Scaricando MBSA è possibile eseguire la scansione degli aggiornamenti di protezione mancanti su Exchange Server 2003.

-   **Uso del Filtro messaggi intelligente di Microsoft Exchange Server**. Combinando il Filtro messaggi intelligente di Exchange Server con Outlook 2003 si ottiene un filtraggio dei messaggi euristico avanzato del lato server e si agevola la riduzione del flusso di posta indesiderata in entrata. Per ulteriori informazioni su come tenere aggiornato il Filtro messaggi intelligente, leggere l'articolo [Disponibilità della Guida alla distribuzione del Filtro messaggi intelligente di Microsoft Exchange](http://support.microsoft.com/?kbid=907747) all'indirizzo http://support.microsoft.com/?kbid=907747.

-   **Esecuzione di Microsoft Exchange Server Best Practices Analyzer**. Questo strumento, disponibile come download gratuito, raccoglie in remoto i dati di configurazione da ciascun server presente nella topologia, quindi analizza automaticamente i dati. Il report che ne risulta illustra in dettaglio i problemi di configurazione critici, i potenziali problemi e le impostazioni non predefinite del prodotto. Seguendo queste raccomandazioni è possibile ottenere prestazioni, scalabilità, affidabilità e tempo di attività migliori.

-   **Verifica regolare delle eventuali informazioni di protezione aggiornate**. Per le indicazioni tecniche sulla protezione, visitare la pagina [Exchange Server 2003 Technical Documentation Library](http://technet.microsoft.com/library/bb123630(exchg.65).aspx) (in inglese) sul sito Web Security and Protection (in inglese) all'indirizzo http://technet.microsoft.com/library/bb123630(EXCHG.65).aspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Scenario su come agevolare la protezione della riservatezza della posta elettronica

La procedura seguente sulla protezione della riservatezza della posta elettronica si riferisce a scenari di aziende di piccole e medie dimensioni simili a quella indicata nella figura.

[![](images/Cc875813.PECRI01(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri01_big(it-it,technet.10).gif)

**Figura 1. Servizi di posta elettronica nell'ambiente IT di un'azienda di medie dimensioni**

Gli utenti di posta elettronica necessitano di riservatezza per l'invio di messaggi verso le ubicazioni interne ed esterne. Per raggiungere questo obiettivo, è possibile implementare Exchange Server 2003 e i client di posta elettronica per il supporto di S/MIME.

#### Agevolare la protezione della riservatezza della posta elettronica

I passaggi seguenti identificano le procedure di configurazione necessarie per proteggere la riservatezza della posta elettronica.

##### Operazioni preliminari

Prima di implementare S/MIME in un ambiente Exchange Server 2003, è necessario comprendere cosa accade ai messaggi se uno qualsiasi degli elementi seguenti è stato implementato.

-   Event sink

-   Software antivirus

###### Event sink e messaggi con firma digitale

Gli event sink possono eseguire azioni sui messaggi di posta elettronica quando Exchange Server li gestisce. Ad esempio, alcuni event sink alterano il contenuto e le intestazioni di un messaggio di posta elettronica al fine di filtrare il messaggio. Una firma digitale valida indica che un messaggio non è stato alterato durante il trasferimento. Un event sink che altera il messaggio di posta elettronica invalida le firme digitali. Quando il destinatario riceve il messaggio ed elabora la firma digitale, quest'ultima risulta non valida, infatti l'event sink ha modificato il messaggio dopo che il mittente lo ha firmato.

###### Software antivirus e messaggi S/MIME

Se si utilizza una soluzione antivirus basata su server, la crittografia che aiuta a proteggere la riservatezza del corpo del messaggio e di qualsiasi allegato da eventuali utenti non autorizzati, previene anche la possibilità che il software antivirus basato su server esegua la scansione virus dei messaggi e degli allegati. Poiché il software antivirus non può ispezionare il messaggio, un messaggio crittografato potrebbe includere un virus come allegato. È fondamentale stabilire come affrontare questo rischio, in conformità con i criteri di protezione aziendali.

Inoltre, se un programma antivirus rileva un virus in un messaggio di posta elettronica con firma digitale e lo elimina, tale azione può invalidare la firma digitale, poiché il programma antivirus ha modificato il messaggio durante il trasferimento. Sebbene la modifica non sia dannosa per la firma digitale, il messaggio è stato modificato e verrà identificato come messaggio alterato.

##### Come configurare Exchange Server 2003 per aiutare a garantire la riservatezza della posta elettronica

Quando Exchange Server archivia dei messaggi di posta elettronica S/MIME, l'unico requisito è che l'archivio messaggi sia stato configurato per la gestione delle firme S/MIME. Poiché i messaggi S/MIME possono essere tenuti in cassette postali utente e in cartelle pubbliche, sia gli archivi pubblici che gli archivi delle cassette di posta possono essere configurati per l'archiviazione di messaggi con firme S/MIME.

1.  Accedere tramite un account che sia membro di entrambi i gruppi seguenti.

    -   Gruppo Amministratori sul computer locale

    -   Un gruppo a cui sia stato applicato almeno il ruolo di Amministratore di sola visualizzazione di Exchange a livello di gruppo amministrativo

2.  Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft Exchange** e fare clic su **Gestore di sistema**. Verrà visualizzato il Gestore di sistema di Exchange (indicato nella schermata seguente).

    [![](images/Cc875813.PECRI02(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri02_big(it-it,technet.10).gif)

3.  Fare clic su **Server**, quindi su ***&lt;nomeserver&gt;***, scegliere **Gruppo di archiviazione** e fare clic con il tasto destro del mouse su **Archivio cassette postali**, quindi fare clic su **Proprietà**.

    Nella pagina delle **Proprietà**, selezionare **Supporto client per firme S/MIME** come indicato nella schermata seguente.

    ![](images/Cc875813.PECRI03(it-it,TechNet.10).gif)

##### Come distribuire i certificati digitali per S/MIME con la registrazione automatica

La registrazione automatica permette ai client di presentare automaticamente una richiesta di certificato a un'autorità di certificazione e di recuperare e archiviare i certificati emessi. I client Microsoft Windows® XP e Windows Server™ 2003 possono partecipare alla registrazione automatica per i certificati di utenti e computer. Grazie alla registrazione automatica il costo di proprietà totale viene ridotto poiché consente di ridurre i costi associati alla registrazione dei certificati e al processo di rinnovo.

**Attivazione delle impostazioni di registrazione automatica**

1.  Accedere con i diritti di amministratore.

2.  Da Strumenti di amministrazione, avviare lo strumento Utenti e computer di Active Directory.

3.  Nella struttura della console, fare clic con il tasto destro del mouse sul dominio in cui si desidera implementare le impostazioni di registrazione automatica, quindi fare clic su Proprietà.

    Per la registrazione automatica, l'oggetto Criteri di gruppo deve essere collegato al dominio o all'unità organizzativa in cui si trova l'account dell'utente o del computer.

    ![](images/Cc875813.PECRI04(it-it,TechNet.10).gif)

4.  Nella finestra di dialogo **Proprietà Nome dominio**, scegliere la scheda **Criteri di gruppo**, quindi fare clic su **Apri** per aprire la Console Gestione Criteri di gruppo.

5.  Creare un oggetto Criteri di gruppo collegato al dominio.

6.  Nell'Editor oggetti Criteri di gruppo, nella struttura della console, espandere **Configurazione utente**.

7.  Nella struttura della console, espandere **Impostazioni di Windows**, espandere **Impostazioni protezione**, quindi fare clic su **Criteri chiave pubblica**, come indicato nella schermata seguente.

    [![](images/Cc875813.PECRI05(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri05_big(it-it,technet.10).gif)

8.  Nel riquadro dettagli, fare doppio clic su **Impostazioni registrazione automatica**. Nella finestra di dialogo **Impostazioni registrazione automatica**, assicurarsi che le impostazioni seguenti siano state selezionate, come indicato nella schermata seguente.

    -   **Registra i certificati automaticamente**. Questa impostazione permette la registrazione automatica dei certificati dell'unità organizzativa dove è collegato l'oggetto Criteri di gruppo.

    -   Casella di controllo **Rinnova i certificati scaduti, aggiorna quelli in sospeso e rimuovi i certificati revocati**. Questa impostazione abilita la registrazione automatica dei certificati per il rinnovo, l'emissione di certificati in sospeso e la rimozione dei certificati revocati dall'archivio dei certificati del soggetto.

    -   Casella di controllo **Aggiorna i certificati che utilizzano modelli di certificati**. Questa impostazione abilita la registrazione automatica per i modelli di certificati sostituiti.

    ![](images/Cc875813.PECRI06(it-it,TechNet.10).gif)

9.  Fare clic su **OK**.

Adesso la registrazione automatica è attiva per l'unità organizzativa a cui è collegato l'oggetto Criteri di gruppo.

Le impostazioni di registrazione automatica vengono applicate la volta successiva che l'oggetto Criteri di gruppo viene applicato all'utente. La registrazione automatica dell'utente viene attivata quando l'utente esegue un accesso interattivo e agli intervalli di aggiornamento dei Criteri di gruppo.

Le impostazioni dell'oggetto Criteri di gruppo possono essere aggiornate anche manualmente su un client che esegue Windows XP o Windows Server 2003 imponendo l'aggiornamento dei Criteri di gruppo. Le impostazioni dell'oggetto Criteri di gruppo possono essere aggiornate eseguendo **GPUpdate /Imponi** al prompt dei comandi sulla workstation di destinazione.

##### Come configurare Outlook 2003 per aiutare a garantire la riservatezza della posta elettronica

Per inviare correttamente un messaggio di posta elettronica crittografato, il destinatario deve già essere in possesso di un certificato digitale. Se si tenta di inviare un messaggio di posta elettronica crittografato a un utente che non possiede un certificato digitale, si riceve un messaggio di errore. Assicurarsi di avere seguito le istruzioni contenute nell'argomento "Come distribuire i certificati digitali per S/MIME con la registrazione automatica", descritto in precedenza, per tutti gli utenti di prova, prima di inviare loro dei messaggi di posta elettronica.

**Configurazione di Outlook per la riservatezza della posta elettronica**

1.  Accedere al proprio dominio come membro del gruppo Domain Users.

2.  Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft Office**, quindi fare clic su **Microsoft** **Office Outlook 2003**.

3.  Fare clic su **Strumenti**, quindi scegliere **Opzioni**. Verrà visualizzata la seguente finestra di dialogo.

    ![](images/Cc875813.PECRI07(it-it,TechNet.10).gif)

4.  Fare clic sulla scheda **Protezione**, quindi scegliere **Impostazioni**.

5.  Outlook popola la finestra di dialogo **Cambia impostazioni di protezione** con le informazioni predefinite. Fare clic su **OK** per accettare i valori predefiniti indicati nella schermata seguente.

    ![](images/Cc875813.PECRI08(it-it,TechNet.10).gif)

6.  Fare clic su **OK** per chiudere la finestra di dialogo **Opzioni**.

A questo punto Outlook è stato configurato per garantire la riservatezza della posta elettronica.

**Invio di un messaggio con firma digitale con Outlook**

1.  Accedere al proprio dominio come membro del gruppo Domain Users.

2.  Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft Office**, quindi fare clic su **Microsoft** **Office Outlook 2003**.

3.  Per comporre un nuovo messaggio, fare clic su **Nuovo**.

4.  Aggiungere un destinatario al messaggio di prova e riempire i campi del messaggio.

5.  Assicurarsi di avere selezionato il pulsante **Aggiungi firma digitale al messaggio**. Poiché la verifica riguarda soltanto la firma digitale, controllare che il pulsante **Crittografa contenuti e allegati del messaggio** non sia stato selezionato.

    [![](images/Cc875813.PECRI09(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri09_big(it-it,technet.10).gif)

6.  Fare clic su **Invia**.

A questo punto il messaggio con firma digitale è stato inviato al destinatario, il quale può verificare la firma digitale.

**Invio di un messaggio crittografato con Outlook**

1.  Accedere al proprio dominio come membro del gruppo Domain Users.

2.  Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft Office**, quindi fare clic su **Microsoft** **Office Outlook 2003**.

3.  Per comporre un nuovo messaggio, fare clic su **Nuovo**.

4.  Aggiungere un destinatario al messaggio di prova e riempire i campi del messaggio.

5.  Verificare che sulla barra degli strumenti il pulsante **Crittografa contenuti e allegati del messaggio** sia stato selezionato. Poiché la verifica riguarda soltanto la crittografia, controllare che il pulsante **Aggiungi firma digitale al messaggio** non sia stato selezionato.

    [![](images/Cc875813.PECRI10(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri10_big(it-it,technet.10).gif)

A questo punto, il messaggio crittografato è stato inviato al destinatario, il quale può aprirlo e leggerlo.

##### Come configurare Outlook Express per aiutare a garantire la riservatezza della posta elettronica

Per inviare correttamente un messaggio di posta elettronica crittografato, il destinatario deve già essere in possesso di un certificato digitale. Se si tenta di inviare un messaggio di posta elettronica crittografato a un utente che non possiede un certificato digitale, si riceve un messaggio di errore. Assicurarsi di avere seguito le istruzioni contenute nell'argomento "Come distribuire i certificati digitali per S/MIME con la registrazione automatica", descritto in precedenza, per tutti gli utenti di prova, prima di inviare loro dei messaggi di posta elettronica.

**Invio di un messaggio con firma digitale con Outlook Express**

1.  Accedere al proprio dominio come membro del gruppo Domain Users.

2.  Scegliere **Start**, **Tutti i programmi**, quindi **Outlook Express**.

3.  Se richiesto, digitare la password utente.

4.  Per comporre un nuovo messaggio, fare clic su **Crea messaggio**.

5.  Per aggiungere un destinatario da Active Directory, fare clic su **A:**.

6.  Sotto **Specificare o selezionare un nome dall'elenco:**, fare clic su **Trova**. Verrà visualizzata la seguente finestra di dialogo.

    ![](images/Cc875813.PECRI11(it-it,TechNet.10).gif)

7.  Nell'elenco **Cerca in:**, fare clic su **Active Directory**, digitare il nome del destinatario nella casella **Nome**, quindi fare clic su **Trova**.

8.  Selezionare il nome, quindi fare clic su **A:**.

9.  Fare clic su **OK** per chiudere la finestra **Seleziona destinatari**.

10. Sulla barra degli strumenti sono visualizzate due nuove icone: una per crittografare i messaggi e una per firmarli. Assicurarsi che il pulsante **Firma** sia stato selezionato, come indicato nella schermata seguente. Poiché la verifica riguarda soltanto la firma digitale, controllare che il pulsante **Crittografa** non sia stato selezionato.

    [![](images/Cc875813.PECRI12(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri12_big(it-it,technet.10).gif)

11. Fare clic su **Invia**.

A questo punto il messaggio con firma digitale è stato inviato al destinatario, il quale può verificare la firma digitale.

**Invio di un messaggio crittografato con Outlook Express**

1.  Accedere al proprio dominio come membro del gruppo Domain Users.

2.  Scegliere **Start**, **Tutti i programmi**, quindi **Outlook Express**.

3.  Se richiesto, digitare la password utente.

4.  Per comporre un nuovo messaggio, fare clic su **Crea messaggio**.

5.  Per aggiungere un destinatario da Active Directory, fare clic su **A:**.

6.  Sotto **Specificare o selezionare un nome dall'elenco:**, fare clic su **Trova**.

7.  Nell'elenco **Cerca in:**, fare clic su **Active Directory**, digitare il nome del destinatario nella casella **Nome**, quindi fare clic su **Trova**.

8.  Selezionare il nome, quindi fare clic su **A:**.

9.  Fare clic su **OK** per chiudere la finestra **Seleziona destinatari**.

10. Assicurarsi che il pulsante **Crittografa** sia stato selezionato, come indicato nella schermata seguente. Poiché la verifica riguarda soltanto la crittografia, controllare che il pulsante **Firma** non sia stato selezionato.

    [![](images/Cc875813.PECRI13(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri13_big(it-it,technet.10).gif)

11. Fare clic su **Invia**.

A questo punto, il messaggio crittografato è stato inviato al destinatario, il quale può aprirlo e leggerlo.

##### Come verificare che un utente sia in possesso di un certificato digitale per S/MIME in Active Directory

Tramite Utenti e computer di Active Directory è possibile verificare se un account utente di Active Directory dispone di un certificato digitale per S/MIME.

**Verifica dell'aggiunta del certificato all'account di un utente di Active Directory**

1.  Accedere al proprio dominio come membro del gruppo Amministratori CA.

2.  Fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory.**

3.  Fare clic su **Visualizza**, quindi su **Funzioni avanzate** come indicato nella schermata seguente.

    [![](images/Cc875813.PECRI14(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri14_big(it-it,technet.10).gif)

4.  Nel riquadro di sinistra, fare clic sulla cartella **Utenti**.

5.  Nel riquadro di destra, fare doppio clic su uno degli utenti di prova.

6.  Scegliere la scheda **Certificati pubblicati**.

7.  In **Elenco di certificati X509 pubblicati per l'account utente** (nella schermata seguente), verrà visualizzato il certificato digitale dell'utente dell'autorità di certificazione Windows insieme a tutti gli altri certificati archiviati per questo utente in Active Directory.

    ![](images/Cc875813.PECRI15(it-it,TechNet.10).gif)

A questo punto, è stato verificato che il certificato è stato aggiunto all'account utente di Active Directory.

##### Come verificare che Exchange Server sia stato configurato per aiutare a garantire la riservatezza della posta elettronica

Per verificare Exchange Server sia stato configurato per supportare i client che utilizzano S/MIME è possibile utilizzare il Gestore di sistema di Exchange.

1.  Accedere utilizzando un account che sia membro di entrambi i gruppi seguenti:

    -   Gruppo Amministratori sul computer locale

    -   Un gruppo a cui sia stato applicato almeno il ruolo di Amministratore di sola visualizzazione di Exchange a livello di gruppo amministrativo

2.  Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft Exchange** e fare clic su **Gestore di sistema**.

3.  Fare clic su **Server**, selezionare ***&lt;nomeserver&gt;***, quindi **Gruppo di archiviazione**, fare clic con il tasto destro del mouse su **Archivio cassette** **postali** o su **Archivio cartelle pubbliche**, quindi scegliere **Proprietà**.

4.  Nella pagina **Proprietà**, verificare che la casella di controllo **Supporto client per firme S/MIME** nella scheda **Generale** sia stata selezionata, come indicato nella schermata seguente.

    ![](images/Cc875813.PECRI16(it-it,TechNet.10).gif)

A questo punto, la verifica che la configurazione di Exchange Server sia in grado di supportare la riservatezza della posta elettronica è stata completata.

##### Come verificare che Outlook 2003 sia stato configurato per ricevere posta elettronica assicurandone la riservatezza

Per verificare che si ricevano messaggi di posta elettronica configurati per le firme digitali e la crittografia è possibile utilizzare Outlook 2003.

**Visualizzazione di un messaggio con firma digitale con Outlook**

1.  Accedere al proprio dominio come membro del gruppo Domain Users.

2.  Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft Office**, quindi fare clic su **Microsoft** **Office Outlook 2003**.

3.  Individuare il messaggio di prova con firma digitale nella Posta in arrivo, quindi fare doppio clic su di esso.

4.  Quando il messaggio si apre, fare clic sul pulsante **Verifica firma** (indicato nella seguente schermata) per verificare la firma.

    [![](images/Cc875813.PECRI17(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri17_big(it-it,technet.10).gif)

    Dopo avere fatto clic sul pulsante **Verifica firma**, viene visualizzata la finestra di dialogo **Firma digitale** (nella schermata seguente), che indica che la firma digitale è valida.

    ![](images/Cc875813.PECRI18(it-it,TechNet.10).gif)

A questo punto, la firma digitale del messaggio è stata verificata.

**Visualizzazione di un messaggio crittografato con Outlook**

1.  Accedere al proprio dominio come membro del gruppo Domain Users.

2.  Fare clic su **Start**, scegliere **Tutti i programmi**, **Microsoft Office**, quindi fare clic su **Microsoft** **Office Outlook 2003**.

3.  Individuare il messaggio di prova crittografato nella Posta in arrivo, quindi fare doppio clic su di esso.

4.  Quando il messaggio si apre, fare clic sul pulsante **Verifica crittografia** (indicato nella seguente schermata) per verificare la crittografia.

    [![](images/Cc875813.PECRI19(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri19_big(it-it,technet.10).gif)

5.  Dopo avere fatto clic sul pulsante **Verifica crittografia**, viene visualizzata la finestra di dialogo **Proprietà protezione dei messaggi**, che indica che il messaggio crittografato è valido.

    ![](images/Cc875813.PECRI20(it-it,TechNet.10).gif)

A questo punto, la crittografia del messaggio è stata verificata.

Una volta eseguiti questi passaggi, tutti gli elementi sono stati convalidati utilizzando S/MIME in Outlook 2003. Queste informazioni permettono di vedere in che modo funzionerà per gli utenti un sistema S/MIME che si avvale di Outlook.

##### Come verificare che Outlook Express sia stato configurato per ricevere posta elettronica assicurandone la riservatezza

Per verificare che si ricevano messaggi di posta elettronica configurati per le firme digitali e la crittografia è possibile utilizzare Outlook Express.

**Visualizzazione di un messaggio con firma digitale con Outlook Express**

1.  Accedere al proprio dominio come membro del gruppo Domain Users.

2.  Scegliere **Start**, **Tutti i programmi**, quindi **Outlook Express**.

3.  Se richiesto, immettere la password utente.

4.  Individuare il messaggio di prova con firma digitale nella Posta in arrivo e fare doppio clic su di esso.

5.  Quando il messaggio si apre, Outlook Express visualizza il seguente messaggio di spiegazione relativo alle firme digitali. Selezionare la casella di controllo **Non visualizzare più questa finestra**, quindi fare clic su **Continua**.

    [![](images/Cc875813.PECRI21(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri21_big(it-it,technet.10).gif)

6.  Per verificare la firma, fare clic sul pulsante **Verifica firma**.

    Dopo avere fatto clic sul pulsante **Verifica firma**, viene visualizzata la finestra di dialogo **Verifica della firma digitale in corso**, che indica se la firma digitale è valida.

    ![](images/Cc875813.PECRI22(it-it,TechNet.10).gif)

A questo punto, la firma digitale del messaggio è stata verificata.

**Visualizzazione di un messaggio crittografato con Outlook Express**

1.  Accedere al proprio dominio come membro del gruppo Domain Users.

2.  Scegliere **Start**, **Tutti i programmi**, quindi **Outlook Express**.

3.  Se richiesto, digitare la password utente.

4.  Individuare il messaggio di prova crittografato nella Posta in arrivo e fare doppio clic su di esso.

5.  Quando il messaggio si apre, Outlook Express visualizza il seguente messaggio di spiegazione relativo alla crittografia. Selezionare la casella di controllo **Non visualizzare più questa finestra**, quindi fare clic su **Continua**.

    [![](images/Cc875813.PECRI23(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875813.pecri23_big(it-it,technet.10).gif)

6.  Per verificare la firma, fare clic su **Verifica crittografia**.

    Dopo avere fatto clic sul pulsante **Verifica crittografia**, viene visualizzata la finestra di dialogo **Verifica crittografia in corso**, che indica se il messaggio crittografato è valido.

    ![](images/Cc875813.PECRI24(it-it,TechNet.10).gif)

A questo punto, la crittografia del messaggio è stata verificata.

Una volta eseguiti questi passaggi, tutti gli elementi sono stati convalidati utilizzando S/MIME in Outlook Express. Queste informazioni permettono di vedere in che modo funzionerà per gli utenti un sistema S/MIME che si avvale di Outlook Express.

##### Come risolvere i problemi relativi all'assicurazione della riservatezza della posta elettronica

In questa sezione vengono esaminati diversi problemi comuni che possono verificarsi in un sistema S/MIME basato su Exchange Server 2003. Sebbene l'elenco non sia esaustivo, fornisce informazioni sui problemi che potrebbero verificarsi nell'implementazione aziendale e consigli sui come risolvere tali problemi.

###### Problema: impossibile verificare la firma digitale del mittente

Questo problema può verificarsi quando il certificato digitale dell'autorità di certificazione principale o intermedia non è presente nell'archivio del computer locale di Exchange Server del destinatario.

###### Risoluzione

Per risolvere questo problema, importare il certificato digitale dell'autorità di certificazione principale o intermedia del mittente nella cartella Autorità di certificazione principale attendibili dell'archivio dei certificati del computer locale di Exchange Server del destinatario. L'importazione del certificato digitale dell'autorità di certificazione principale garantisce intrinsecamente l'affidabilità di ogni certificato digitale emesso dalla gerarchia delle autorità certificate principali. Le organizzazioni per le quali questa garanzia di affidabilità è vietata dai criteri di protezione interni potranno ricorrere, come alternativa, a strategie di certificazione incrociata. Per informazioni su come implementare la certificazione incrociata utilizzando un'autorità certificata di Windows Server 2003, visitare [Planning and Implementing Cross-Certification and Qualified Subordination Using Windows Server 2003](http://technet.microsoft.com/en-us/library/cc787237.aspx) (in inglese) all'indirizzo http://technet.microsoft.com/en-us/library/cc787237.aspx.

**Importazione del certificato digitale dell'autorità di certificazione principale del mittente nella cartella Autorità di certificazione principale attendibili**

1.  Accedere a Exchange Server del destinatario utilizzando un account che sia membro del gruppo Amministratori locale.

2.  Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **MMC**, quindi fare clic su **OK**.

3.  Fare clic su **File**, quindi su **Aggiungi/Rimuovi snap-in**.

4.  Nella scheda **Autonomo**, fare clic su **Aggiungi**.

5.  Selezionare **Certificati**, quindi fare clic su **Aggiungi**. Se richiesto, selezionare **Account del computer**, quindi fare clic su **Avanti**.

6.  Nella pagina **Seleziona computer**, selezionare **Computer locale (il computer su cui è in esecuzione la console)**, quindi fare clic su **Fine**.

7.  In MMC, espandere **Certificati (Computer locale)**, quindi espandere **Autorità di certificazione principale** **attendibili**.

8.  Nel riquadro dettagli, fare clic con il tasto destro del mouse su **Tutte le attività**, quindi scegliere **Importa**.

9.  Nella prima pagina di Importazione guidata certificati, fare clic su **Avanti**.

10. Nella finestra di dialogo **Nome file**, digitare il nome e la posizione del file contenente il certificato digitale della CA, quindi fare clic su **Avanti**.

11. Nella pagina **Archivio certificati**, selezionare **Mettere tutti i certificati nel seguente archivio**, assicurarsi che nella finestra di dialogo **Archivio certificati** sia visualizzato **Autorità di certificazione principale attendibili**, quindi fare clic su **Avanti**.

12. Nella pagina finale della procedura guidata, selezionare **Fine**.

Dopo avere importato il certificato digitale per l'autorità di certificazione principale del mittente, Exchange Server può convalidare il certificato digitale del mittente per conto del destinatario.

**Importazione del certificato digitale dell'autorità di certificazione intermedia del mittente nella cartella Autorità di certificazione intermedie**

1.  Accedere a Exchange Server del destinatario utilizzando un account che sia membro del gruppo Amministratori locale.

2.  Fare clic sul pulsante **Start**, scegliere **Esegui**, digitare **MMC**, quindi fare clic su **OK**.

3.  Fare clic su **File**, quindi su **Aggiungi/Rimuovi snap-in**.

4.  Nella scheda **Autonomo**, fare clic su **Aggiungi**.

5.  Selezionare **Certificati**, quindi fare clic su **Aggiungi**. Se richiesto, selezionare **Account** **del computer**, quindi fare clic su **Avanti**.

6.  Nella pagina **Seleziona computer**, selezionare **Computer locale (il computer su cui è in esecuzione la console)**, quindi fare clic su **Fine**.

7.  In MMC, espandere **Certificati (Computer locale)**, quindi espandere **Autorità di certificazione intermedie** **attendibili**.

8.  Nel riquadro dettagli, fare clic con il tasto destro del mouse su **Tutte le attività**, quindi scegliere **Importa**.

9.  Nella prima pagina di Importazione guidata certificati, fare clic su **Avanti**.

10. Nella finestra di dialogo **Nome file**, digitare il nome e la posizione del file contenente il certificato digitale della CA, quindi fare clic su **Avanti**.

11. Nella pagina **Archivio certificati**, selezionare **Mettere tutti i certificati nel seguente archivio**, assicurarsi che nella finestra di dialogo **Archivio certificati** sia visualizzato **Autorità intermedie**, quindi fare clic su **Avanti**.

12. Nella pagina finale della procedura guidata, selezionare **Fine**.

Dopo avere importato il certificato digitale per l'autorità di certificazione intermedia del mittente, Exchange Server può convalidare il certificato digitale del mittente per conto del destinatario.

###### Problema: impossibile accedere all'elenco di revoca certificati

Questo problema può verificarsi quando un punto di distribuzione degli elenchi di revoca dei certificati (CRL) nei certificati digitali è accessibile soltanto attraverso un firewall, oppure se Exchange Server dell'utente non dispone dei diritti di accesso al punto di distribuzione dei CRL.

###### Risoluzione

Per risolvere il problema eseguire una delle azioni seguenti.

-   Scaricare manualmente il CRL dal punto di distribuzione dei CRL e importarlo nell'archivio certificati del computer locale di Exchange Server dell'utente.

-   Installare e configurare un client firewall per i protocolli appropriati su Exchange Server del destinatario.

-   Concedere esplicitamente l'autorizzazione per l'account LocalSystem di Exchange Server dell'utente per accedere al punto di distribuzione dei CRL, oppure riconfigurare tale punto di distribuzione in modo tale che non richieda l'autenticazione.

**Importazione manuale di un CRL**

1.  Accedere a Exchange Server del destinatario utilizzando un account che sia membro del gruppo Amministratori locale.

2.  Scaricare il CRL dal punto di distribuzione dei CRL indicato nel certificato digitale.

3.  Fare clic con il tasto destro del mouse sul file **.cer** o **.crl**, scegliere **Installa certificato** o **Installa CRL**, quindi fare clic su **Avanti**.

4.  Quando si apre l'Importazione guidata certificati, fare clic su **Selezionare automaticamente l'archivio certificati secondo il tipo di certificato**.

###### Problema: vengono utilizzati certificati diversi se si utilizzano client di posta elettronica diversi

Questo problema può verificarsi perché sono presenti due attributi in Active Directory nell'ubicazione in cui è possibile archiviare i certificati digitali S/MIME: l'attributo **userCertificate** e l'attributo **userSMIMECertificate**. Per impostazione predefinita, Outlook cerca prima l'attributo **userSMIMECertificate** e utilizza qualsiasi certificato S/MIME appropriato trovato in questo attributo. Altri client di posta elettronica, incluso OWA, possono cercare prima l'attributo **userCertificate** e utilizza qualsiasi certificato S/MIME appropriato trovato in questo attributo.

Se negli attributi **userCertificate** e **userSMIMECertificate** sono archiviati diversi certificati digitali Outlook e OWA possono utilizzare certificati digitali differenti, poiché ognuno di essi fa riferimento ad attributi diversi di Active Directory.

###### Risoluzione

Per risolvere questo problema, assicurarsi che gli stessi certificati siano stati archiviati negli attributi the **userCertificate** e **userSMIMECertificate**. Per ulteriori informazioni, leggere l'articolo "[Outlook 2003 continua a utilizzare i certificati vecchi dopo aver migrato dal server di gestione delle chiavi a PKI](http://go.microsoft.com/fwlink/?linkid=3052&kbid=822504)" all'indirizzo http://go.microsoft.com/fwlink/?linkid=3052&kbid=822504.

###### Problema: Outlook Express tenta di firmare automaticamente i messaggi di posta elettronica

Per impostazione predefinita, se un utente risponde o inoltra un messaggio firmato utilizzando Outlook Express, Outlook Express abilita la firma digitale per il messaggio. Se l'utente tenta di inviare il messaggio e non dispone di un certificato valido per la firma, Outlook Express visualizza il messaggio di errore "**Non si dispone di un ID digitale."** e il messaggio non viene inviato.

###### Risoluzione

Per risolvere questo problema, disattivare la firma digitale del messaggio. Per ulteriori informazioni, leggere l'articolo "[Si visualizza un messaggio di errore quando si tenta all'inoltro o che risponde a un messaggio di posta elettronica firma digitale](http://go.microsoft.com/fwlink/?linkid=3052&kbid=816830)" all'indirizzo http://go.microsoft.com/fwlink/?linkid=3052&kbid=816830.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

Con la crescita di Internet degli ultimi anni, la posta elettronica è cambiata in maniera fondamentale. Non è più soltanto uno strumento organizzativo interno. Al contrario, adesso unisce le persone di diverse aziende, di diversi paesi e continenti e permette addirittura di condividere le informazioni tra i popoli del mondo, come se tutti si trovassero nello stesso edificio. La posta elettronica è senza dubbio il vantaggio più importante che Internet abbia offerto fino a oggi. Mano a mano che la posta elettronica si integra sempre di più nella vita delle persone e delle aziende, la sua importanza aumenta allo stesso ritmo.

La crescita senza precedenti della posta elettronica è stata permessa dall'adozione a livello mondiale del protocollo, o linguaggio, sottostante della posta elettronica su Internet: l'SMTP. Lo standard SMTP permette che sistemi di posta elettronica diversi collegati su Internet si scambino informazioni.

Tuttavia, nonostante tutti i vantaggi portati su Internet dallo standard SMTP, esso presenta un problema intrinseco. In origine il protocollo SMTP venne sviluppato per trasportare messaggi brevi e di relativa importanza in una rete chiusa, ma non per trasferire informazioni critiche e riservate in un mondo interconnesso. Chi ha sviluppato lo standard SMTP non poteva lontanamente immaginare il ruolo che avrebbe avuto oggi. Per questo motivo, il protocollo SMTP non era stato concepito per proteggere il tipo di informazioni che oggi vengono trasferite nelle reti odierne. Era stato concepito per trasferire informazioni più semplici su reti più semplici, da cui il nome Simple Mail Transfer Protocol (protocollo di trasferimento di posta semplice). AD esempio, SMTP invia informazioni su Internet con una modalità che consente a chiunque di leggere il messaggio.

Fortunatamente, lo standard S/MIME è risultato essere appropriato per migliorare i messaggi di posta elettronica SMTP attribuendo loro capacità di protezione. Grazie a S/MIME, la crittografia aiuta a proteggere i contenuti dei messaggi e le firme digitali a verificare l'identità del presunto mittente di un messaggio di posta elettronica.

L'implementazione di S/MIME per la posta elettronica richiede una soluzione che sia adatta a più prodotti e tecnologie.

**Download**

[Scarica il white paper Come proteggere la riservatezza della posta elettronica nei settori soggetti a normative](http://go.microsoft.com/fwlink/?linkid=71176)

[](#mainsection)[Inizio pagina](#mainsection)
