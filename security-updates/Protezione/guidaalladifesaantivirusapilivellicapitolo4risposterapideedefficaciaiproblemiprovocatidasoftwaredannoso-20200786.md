---
TOCTitle: 'Guida alla difesa antivirus a più livelli, Capitolo 4: Risposte rapide ed efficaci ai problemi provocati da software dannoso'
Title: 'Guida alla difesa antivirus a più livelli, Capitolo 4: Risposte rapide ed efficaci ai problemi provocati da software dannoso'
ms:assetid: 'ea40994b-59ce-4104-9f16-8855021d68db'
ms:contentKeyID: 20200786
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536186(v=TechNet.10)'
---

Guida alla difesa antivirus a più livelli
=========================================

### Capitolo 4: Controllo della diffusione e ripristino

Pubblicato: 20 maggio 2004

##### In questa pagina

[](#egaa)[Introduzione](#egaa)
[](#efaa)[Passaggio 1: Conferma dell'infezione](#efaa)
[](#eeaa)[Passaggio 2: Risposta ai problemi](#eeaa)
[](#edaa)[Passaggio 3: Analisi del software dannoso](#edaa)
[](#ecaa)[Passaggio 4: Ripristino del sistema](#ecaa)
[](#ebaa)[Passaggio 5: Passaggi post ripristino](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

Nel presente capitolo vengono trattati diversi argomenti da tenere in considerazione per identificare le infezioni causate da software dannoso, limitarne la diffusione e trovare le soluzioni adatte per eliminare gli effetti indesiderati sui sistemi del proprio ambiente. Pertanto, è indispensabile ricorrere a soluzioni dirette e compatibili in grado di fornire risposte adeguate ai problemi e alle esigenze di ripristino. In genere, quando si verificano problemi causati da software dannoso si determina un senso di urgenza che non favorisce l'elaborazione di procedure accurate che possano essere considerate efficaci e risolutive anche in seguito.

Inoltre, è necessario tenere presente un altro punto importante. Poiché gli attacchi di software dannoso sono diventati sempre più complessi a causa dell'utilizzo di diversi metodi di payload, allo stato attuale non esiste un singolo processo universalmente applicabile in grado di garantirne la rimozione. È quindi probabile che per ogni attacco di software dannoso sia necessaria una soluzione specifica. Ciononostante, è fondamentale riuscire a definire processi logici in grado di identificare un attacco di software dannoso, limitarne la diffusione e garantire il ripristino del sistema.

Di seguito sono riportati i passaggi principali che devono essere inclusi in un processo di ripristino dalla diffusione di software dannoso:

1.  Conferma dell'infezione.

2.  Risposta ai problemi.

3.  Analisi del software dannoso.

4.  Ripristino del sistema.

5.  Passaggi post ripristino.

[](#mainsection)[Inizio pagina](#mainsection)

### Passaggio 1: Conferma dell'infezione

La capacità di stabilire rapidamente se il sistema è stato infettato assume un valore fondamentale per mettere un'organizzazione nelle condizioni di ridurre al minimo l'impatto provocato da un'infezione. Se si riesce a rilevare un'infezione in tempi rapidi e se ne identificano le caratteristiche sospette, è possibile ridurre l'infezione e il relativo impatto sugli utenti.

Esistono diversi tipi di malfunzionamenti del computer che possono essere confusi con comportamenti tipici di un virus. Quando si riceve una chiamata telefonica o un messaggio di posta elettronica da un utente in cui viene segnalata la presenza di un virus nel sistema, il personale del supporto tecnico deve innanzitutto verificare se il comportamento potrebbe essere causato dalla presenza di codice dannoso. Nell'elenco seguente vengono indicati alcuni esempi di sintomi tipici in cui l'utente potrebbe ravvisare un comportamento specifico di un virus:

-   "Si tenta di aprire un allegato di posta elettronica ma l'allegato non si apre. Inoltre, si rileva un comportamento inatteso del sistema".

-   "Si ricevono messaggi di risposta da contatti che chiedono il motivo per cui sono stati inviati file exe, zip o altri allegati che in realtà non sono mai stati inoltrati".

-   "L'esecuzione del programma antivirus si è bloccata e il computer continua a spegnersi".

-   "I programmi non funzionano correttamente e l'esecuzione di ognuno di essi appare *molto* rallentata".

-   "Nella cartella **Documenti** viene visualizzato un gruppo di file mai visto in precedenza".

-   "Molti file non si aprono o sembrano scomparsi".

Le osservazioni e i commenti degli utenti possono essere fondamentali in quanto gli utenti sono i primi a ravvisare un comportamento anomalo del sistema. Poiché la velocità di diffusione del software dannoso è molto rapida, il periodo di tempo compreso tra l'inizio dell'infezione e la disponibilità di una protezione efficace acquisisce un'importanza enorme. Inoltre, dato che la maggior parte delle infezioni si verifica durante questo lasso di tempo, è fondamentale identificare l'infezione rapidamente e verificarne la presenza per ridurre al minimo la diffusione e i danni che ne potrebbero conseguire.

Nella seguente sezione vengono descritti diversi passaggi che consentiranno di verificare con maggiore rapidità se il comportamento anomalo è provocato dalla diffusione o da un attacco di software dannoso.

Se il sistema viene infettato da un nuovo tipo di software dannoso, è probabile che l'utente sia il primo ad accorgersi di eventuali comportamenti anomali del sistema. Come descritto nel capitolo 3, "Difesa antivirus a più livelli" della presente guida, è probabile che le applicazioni antivirus vengano aggiornate in ritardo rispetto al rilascio di un nuovo software dannoso e che quindi non siano in grado di rilevarlo e neutralizzarlo. Il modo migliore per ottenere un sistema di avviso efficace è quello di fornire all'utente tutte le informazioni necessarie per riconoscere i segnali di un possibile attacco di software dannoso e collegamenti di comunicazione rapidi che consentano di segnalare il problema nel più breve tempo possibile.

#### Report sull'infezione

Quando si riceve una chiamata o un avviso relativo a un possibile nuovo attacco di software dannoso, per il personale di supporto tecnico è utile poter disporre di un processo definito che consenta di determinare in tempi rapidi se l'avviso segnala la presenza di un nuovo attacco. Nel seguente diagramma di flusso vengono descritti i passaggi principali previsti dal processo:

![](images/Dd536186.AVFG0401(it-it,TechNet.10).gif "Figura 4.1 Processo di report sull'infezione di software dannoso")

**Figura 4.1 Processo di report sull'infezione di software dannoso**

##### Report attività anomale

Le seguenti domande devono essere utilizzate per stabilire se l'attività anomala che ha generato l'avviso è causata da un nuovo attacco di software dannoso. Nella presente guida si presuppone che le domande vengano poste a un utente senza particolari competenze tecniche da un membro del personale del supporto IT dell'organizzazione.

###### Acquisizione delle informazioni di base

Le domande iniziali devono essere formulate per ottenere risposte che consentano di determinare in tempi brevi la vera natura dell'avviso e il livello di probabilità di un nuovo attacco di software dannoso. Come punto di partenza per questo processo è possibile utilizzare le seguenti domande di esempio che possono essere modificate in base ai requisiti dell'organizzazione:

-   Quali sono la data e l'ora del report?

-   Qual è l'attività anomala che ha richiesto il report?

-   Qual era l'attività in corso prima che si verificasse l'anomalia?

    -   Sono stati visitati siti Web diversi da quelli visitati abitualmente?

    -   Il sistema è stato recentemente spostato all'esterno della rete dell'organizzazione (ad esempio, in un aereoporto, in una rete domestica, in un'area sensibile Wi-Fi o in un hotel)?

    -   Sono apparsi annunci o finestre popup inusuali sullo schermo?

-   Quali processi anomali o inattesi sono attualmente in esecuzione?

-   Il computer in uso è una workstation o un server? Qual è il sistema operativo in uso e quali aggiornamenti per la protezione sono stati applicati?

-   Il computer o le periferiche ad esso collegate contengono dati critici?

-   L'utente si è connesso mediante un account con privilegi amministrativi?

-   L'utente utilizza una password complessa o una frase password?

-   Il sistema è già stato sottoposto ad attacchi di software dannoso?

Quest'ultima domanda è importante in quanto gli attacchi precedenti creano vulnerabilità che, se non vengono corrette, possono favorire ulteriori attacchi. Se la risposta a questa domanda è "Sì", è possibile passare alle altre domande riportate di seguito:

-   Quando si è verificato l'attacco precedente?

-   Chi ha gestito il caso e, se possibile, qual era il numero del caso?

-   Sono disponibili informazioni sulle operazioni eseguite in quella occasione?

###### Valutazione dei dati

Dopo aver esaminato le risposte alle domande sopra riportate, il personale del supporto tecnico valuta i dati acquisiti confrontandoli con quelli delle domande sottostanti per determinare se l'attacco di software dannoso è una causa probabile del report:

-   È possibile che il report sia il risultato di una caratteristica nuova o aggiornata del sistema, ma del tutto legittima?

-   È possibile che il report sia il risultato delle attività di un utente non autorizzato anziché di un hacker o di un intruso?

-   È possibile che il report sia il risultato di attività di sistema note?

-   È possibile che il report sia il risultato di modifiche autorizzate a programmi o sistemi?

Infine, per determinare se il report corrisponde a un avviso di worm o virus esistente, è necessario eseguire un controllo con origini di antivirus esterne (identificate nella sezione "Comunicazioni interne proattive" del capitolo 3, "Difesa antivirus a più livelli" della presente guida).

###### Acquisizione dei dettagli

A questo punto è possibile determinare se la probabile causa del problema è rappresentata da un nuovo attacco di software dannoso. In caso contrario, potrebbe essere necessario fare riferimento a un livello di informazioni tecniche più avanzato e richiedere un controllo fisico del sistema sospetto (o, se possibile, un controllo remoto) da parte del personale del supporto tecnico. Per acquisire informazioni più dettagliate e stabilire, in modo categorico, se il sistema è stato attaccato da un hacker o da codice dannoso, è possibile fare riferimento alle domande tecniche di esempio riportate di seguito:

-   Il firewall della periferica è stato attivato sopra o davanti alla periferica? In questo caso, quali sono le porte aperte per l'accesso a Internet?

-   Se si verificano arresti anomali delle applicazioni, contattare immediatamente i fornitori delle applicazioni per determinare la causa principale del problema, ad esempio le applicazioni Microsoft correnti includono strumenti per la segnalazione degli errori che consentono all'utente di inviare report di arresti anomali.

-   Sono stati rilasciati aggiornamenti per la protezione del sistema e tali aggiornamenti non sono stati installati?

-   Qual è il criterio password disponibile sul sistema? Qual è la lunghezza minima delle password? Quali sono i requisiti di complessità delle password?

-   Verificare la presenza di elementi nuovi o sospetti, ad esempio:

    -   account sul computer locale

    -   account nel gruppo Administrators

    -   servizi elencati nella console di gestione dei servizi

    -   eventi nei registri degli eventi

-   Esistono connessioni di rete riportate dall'utilità **netstat** basate su indirizzi IP esterni o indirizzi IP sospetti?

##### Risposta di attività anomale

Dopo aver acquisito ed esaminato le informazioni iniziali per determinare la natura dell'avviso, il personale del supporto tecnico dovrebbe essere in grado di stabilire se si è trattato di un falso allarme, di un falso avviso o di un attacco di software dannoso.

La creazione di un report di software dannoso falso è molto più semplice dello sviluppo di un virus o di un worm che invece comporta la generazione di molti falsi avvisi di software dannoso. Falsi allarmi, chiamate e avvisi comportano uno spreco considerevole di tempo e denaro. I falsi avvisi, inoltre, sono fastidiosi e tendono a mettere in dubbio il valore dei report di attacchi potenziali. Per una corretta gestione degli avvisi, è necessario tenere presente le seguenti considerazioni.

-   **Falsi allarmi**. Se il report è un falso allarme, è necessario registrare le informazioni sulle chiamate. Mediante la revisione periodica delle informazioni è possibile determinare se è necessario un ulteriore training degli utenti.

-   **Falsi avvisi**. È importante registrare sia i falsi avvisi sia le attività reali del software dannoso in quanto si tratta ancora di istanze di attacco in cui non viene utilizzato alcun codice dannoso. Nelle normali comunicazioni antivirus dell'organizzazione dovrebbe essere previsto lo scambio di informazioni relative a falsi avvisi o a pericoli concreti correlati a software dannoso. Queste informazioni potrebbero consentire agli utenti di riconoscere i falsi avvisi in anticipo riducendo eventuali perdite di produttività.

-   **Infezioni note**. Se si ritiene che il sistema sia stato infettato, il personale del supporto tecnico dovrà eseguire le procedure necessarie per determinare se l'infezione è causata da un attacco noto che può essere gestito con un'applicazione antivirus esistente. Sarà quindi necessario controllare l'applicazione antivirus del sistema per verificare se è aggiornata e in funzione. A questo punto è possibile effettuare l'analisi completa del sistema per tentare di eseguirne la pulitura. Se in seguito all'esecuzione dell'analisi l'infezione viene identificata ed eliminata, la chiamata verrà registrata e a tutti gli utenti verrà inviato un avviso in cui viene confermato che i sistemi antivirus sono aggiornati e funzionano in modo corretto. Se in seguito all'esecuzione dell'analisi non viene rilevato alcun tipo specifico di software dannoso, è possibile che sia in atto una nuova infezione per cui è consigliabile fare riferimento alla sezione "Processo di risposta ai problemi" riportata più avanti.

-   **Nuova infezione**. Se si ritiene che il sistema sia stato infettato da un nuovo attacco di software dannoso, è necessario eseguire una serie di azioni iniziali per fare in modo che il problema venga comunicato in maniera corretta. Queste azioni consentono al personale del supporto IT di seguire un processo uniforme in grado di garantire il corretto svolgimento delle azioni richieste. Le risposte alle domande iniziali sopra elencate consentiranno di stabilire quali delle seguenti azioni iniziali devono essere prese in considerazione in questa fase:

    -   Contattare il membro assegnato dal team di risposta alle emergenze con i dettagli relativi all'avviso.

    -   Se il computer sospetto è un server, contattare l'amministratore per verificare le conseguenze provocate dall'eventuale rimozione del computer dalla rete.

    -   Se il computer sospetto è una workstation, contattare gli utenti per verificare le conseguenze provocate dall'eventuale rimozione del computer dalla rete.

    -   Valutare l'attivazione di un avviso di livello elevato per avvertire gli utenti del sistema IT che l'attacco è stato rilevato.

A questo punto, il ruolo del personale del supporto tecnico è completo. La responsibilità della diffusione passerà al processo di risposta ai problemi e sarà necessario inviare una notifica ai membri del CSIRT (Computer Security Incident Response Team).

[](#mainsection)[Inizio pagina](#mainsection)

### Passaggio 2: Risposta ai problemi

Come indicato nel capitolo 3, "Difesa antivirus a più livelli" della presente guida, il CSIRT dovrà convocare al più presto possibile una riunione d'emergenza per consentire l'organizzazione del passo successivo del processo di risposta ai problemi dell'organizzazione. Per una descrizione dettagliata della modalità di creazione dei team di risposta alle emergenze e dei processi per la protezione e il ripristino di emergenza, fare riferimento allo stesso capitolo della presente guida.

Si presume che il CSIRT sia tra gli argomenti trattati nella guida. Il primo obiettivo del team, a questo punto, deve essere quello di determinare il meccanismo più immediato per il controllo della diffusione. Nella seguente sezione vengono fornite ulteriori informazioni utili per determinare le opzioni per il meccanismo scelto e i relativi componenti.

#### Controllo di emergenza della diffusione

Dopo che è stato confermato l'attacco di software dannoso, il primo passaggio richiesto per controllarne la diffusione è quello di verificare se i computer infetti sono isolati dalle periferiche. L'isolamento dei computer infetti è essenziale in quanto previene la diffusione del codice dannoso. Per ottenere tale isolamento è possibile ricorrere all'utilizzo di diversi meccanismi, anche se ognuno di essi avrà un impatto sulle operazioni normalmente svolte nell'ambito dell'organizzazione.

**Importante**: se si ritiene che l'organizzazione voglia intentare una causa civile o penale, Microsoft consiglia di consultare i rappresentanti legali dell'organizzazione prima di intraprendere altre azioni.

Se la diffusione è stata rilevata dalla comunità antivirus, è consigliabile fare riferimento alle informazioni indicate dal fornitore del programma antivirus per stabilire il livello di gravità della diffusione.

Se gran parte della comunità antivirus non è ancora al corrente della diffusione, sarà necessario sottoporre il problema al fornitore del programma antivirus quanto prima possibile. È possibile che venga richiesto di inviare alcuni esempi di software dannoso in file compressi o protetti da password per consentirne l'analisi. Il processo di individuazione degli esempi non è sempre così immediato e sarebbe opportuno che venisse preparato in anticipo. Per ulteriori informazioni sulla preparazione di esempi di software dannoso, vedere la sezione "Passaggio 3: Analisi del software dannoso" del presente capitolo.

Il successivo passaggio dell'azione da seguire prevede la limitazione immediata dell'attacco. Esistono tre opzioni di base da tenere in considerazione:

-   Disconnettere i sistemi violati dalla rete locale.

-   Se possibile, isolare le reti contenenti host infetti.

-   Se l'intera rete è stata violata o potrebbe essere violata, è necessario disconnetterla da tutte le reti esterne.

Sono disponibili molti altri passaggi tecnici più dettagliati che possono essere presi in considerazione, ad esempio il monitoraggio della rete per identificare e provare le porte di rete e gli indirizzi IP coinvolti nell'attacco. Tuttavia, se non viene completata un'analisi dettagliata del software dannoso, si corrono seri rischi di tralasciare un vettore di attacco che potrebbe diffondere ulteriormente l'infezione. L'unico meccanismo disponibile per l'organizzazione in grado di stabilire se il rischio è accettabile, è rappresentato da un report completo di verifica dei rischi di protezione. Questo report, oltre a determinare i rischi a cui si va incontro in seguito a un tentativo non riuscito di bloccare un attacco, consente di sottoporre clienti e organizzazioni partner ad attacchi potenzialmente infetti e utilizzati in modo inconsapevole. Se non viene completata l'analisi dei rischi prima dell'attacco, è consigliabile che l'organizzazione sia molto prudente e cerchi di ridurre al minimo le possibilità che l'attacco possa diffondersi selezionando il livello di isolamento più alto possibile.

Le opzioni sopra elencate rappresentano delle semplici linee guida. Lo svolgimento specifico dell'azione può variare in base a diversi fattori, ad esempio le esigenze commerciali, le impostazioni internazionali, l'impatto, il livello di gravità e ad altri fattori riconducibili all'organizzazione e alle circostanze che hanno provocato la diffusione.

#### Preparazione per il ripristino

Dopo aver attivato il meccanismo di controllo della diffusione, è necessario avviare il processo di ripristino attivo. Lo scopo generale del processo di ripristino è quello di garantire il raggiungimento dei seguenti obiettivi:

-   Riduzione drastica dei problemi relativi all'attività dell'organizzazione.

-   Ripristino del sistema nel più breve tempo possibile.

-   Acquisizione di informazioni tese a garantire una possibile prosecuzione.

-   Acquisizione di informazioni tese a garantire lo sviluppo di altre misure di protezione, se richieste.

-   Prevenzione contro altri attacchi dello stesso tipo nei sistemi ripristinati.

Purtroppo, i primi due obiettivi richiedono soluzioni a correzione rapida, mentre i restanti tre richiedono tempo per acquisire tutte le informazioni necessarie per comprendere la natura dell'attacco. Per soddisfare entrambe le esigenze, ovvero per risolvere il problema e acquisire tutti i dati più importanti, è opportuno prendere in considerazione l'utilizzo del processo indicato nella seguente figura. Questo processo non solo consente il rilascio del sistema infetto per il ripristino nel più breve tempo possibile, ma garantisce anche che i dati di analisi richiesti non vadano persi. Questi dati sono importanti sia perché verranno utilizzati dall'organizzazione per determinare se i sistemi ripristinati sono protetti in caso di attacchi futuri, sia perché rappresentano una prova evidente nel caso in cui si decida di intraprendere un'azione legale.

Per ottimizzare i tempi di ripristino, è necessario che i processi di ripristino del sistema e di analisi dei virus vengano eseguiti in diversi momenti.

[![](images/Dd536186.AVFG0402(it-it,TechNet.10).gif "Figura 4.2 Passaggi per il ripristino prima dell'analisi")](https://technet.microsoft.com/it-it/dd536186.avfg0402_big(it-it,technet.10).gif)

**Figura 4.2 Passaggi per il ripristino prima dell'analisi**

Il modo più rapido per consentire il ripristino di tutti i sistemi è quello di individuare un sistema infetto che possa essere utilizzato per l'analisi. Dopo averlo identificato, il sistema deve essere messo in quarantena e sottoposto ad analisi. (Per ulteriori informazioni sul processo di analisi, consultare la sezione "Passaggio 3: Analisi del software dannoso" del presente capitolo). Se non è possibile eseguire né la messa in quarantena né l'analisi, è disponibile un'altra soluzione mediante la quale è possibile ottenere un clone del sistema utilizzando un tipo di software specifico per l'acquisizione delle immagini. Se questa opzione è disponibile, è possibile acquisire l'immagine del sistema, rilasciare il computer originale per il ripristino e creare un sistema clone.

Nei casi in cui vengano acquisite delle prove o si decida di eseguire un'analisi più approfondita, è molto importante che l'immagine dei computer interessati venga acquisita nel più breve tempo possibile (prima dell'inizio delle attività di risoluzione dei problemi) in modo che l'infezione possa essere identificata, catalogata e gestita nel modo più appropriato ed efficace.

Infine, se non è possibile eseguire l'acquisizione dell'immagine, sarà necessario raccogliere un campione di dati di analisi prima che il sistema venga rilasciato per il ripristino. In teoria, il team di protezione dell'organizzazione dovrebbe sviluppare e gestire un tipo di toolkit per la risposta ai problemi. Questo toolkit potrebbe essere utilizzato per acquisire dati volatili e non volatili utili per risalire ai dati di analisi del sistema. Il toolkit, inoltre, potrebbe essere un sottoinsieme del toolkit di analisi del software dannoso più completo che verrà utilizzato nella sezione successiva del presente capitolo per scoprire e documentare tutti gli elementi del software dannoso. Tuttavia, la differenza sostanziale con il toolkit di risposta ai problemi sta nel fatto che questo toolkit consente di acquisire il livello minimo di informazioni di sistema richieste in tempi talmente rapidi da garantire il rilascio del sistema per il ripristino nel più breve tempo possibile.

[](#mainsection)[Inizio pagina](#mainsection)

### Passaggio 3: Analisi del software dannoso

Non appena viene contenuta la diffusione dell'attacco di software dannoso, è importante cercare di comprendere la natura della diffusione ed eseguire un'analisi più dettagliata del software dannoso. L'esecuzione non corretta di questo passaggio può aumentare le probabilità che si verifichino nuove infezioni, così come un'errata comprensione dei meccanismi del software dannoso potrebbe compromettere la pulitura dei sistemi e la protezione contro altri attacchi.

In teoria, l'analisi del software dannoso dovrebbe essere eseguita da un membro del team di protezione con un set di utilità e applicazioni dedicate da utilizzare per l'acquisizione automatica delle informazioni richieste. Di seguito sono riportati alcuni passaggi che consentono di comprendere la natura dell'attacco.

#### Analisi degli elementi del sistema operativo

Provare a identificare i file del sistema operativo che sono stati introdotti o modificati dall'attacco. Durante l'analisi, esaminare le modifiche relative alle aree seguenti:

-   Servizi e processi attivi.

-   Registro di sistema locale.

-   File inclusi nelle cartelle di sistema di Microsoft® Windows®.

-   Nuovi account utente o di gruppo, in particolare con privilegi amministrativi.

-   Cartelle condivise (incluse le cartelle nascoste).

-   File creati di recente con nomi normali ma in posizioni anomale.

-   Porte di rete aperte.

Nelle seguenti sezioni vengono descritte le tecniche che è possibile utilizzare per eseguire il controllo degli elementi di un sistema operativo.

##### Controllo di servizi e processi attivi

È probabile che nella memoria dei sistemi infetti siano stati introdotti nuovi processi.

Per ottenere un'interfaccia utente più intuitiva, è consigliabile utilizzare alcuni strumenti per la creazione di elenchi di processi specifici, ad esempio PsTools e il programma freeware Process Explorer. Questi strumenti sono disponibili sul sito Web Sysinternals all'indirizzo [http://www.sysinternals.com](http://www.sysinternals.com/) e consentono di visualizzare sia il percorso del file di immagine sia la struttura dei processi.

Per ridurre al minimo il numero delle voci nell'elenco dei processi e consentire l'identificazione di eventuali processi inaffidabili, è necessario chiudere tutte le applicazioni valide, comprese quelle in background quali Instant Messenger, gli strumenti di monitoraggio della posta elettronica o le utilità di terze parti che risiedono nella memoria.

Se non sono disponibili strumenti specifici, è possibile utilizzare Task Manager Windows incluso in tutti i sistemi Microsoft Windows per eseguire un rapido controllo dei processi attivi in esecuzione sul sistema. Tuttavia, poiché in Task Manager non viene visualizzato il percorso dell'immagine da cui è stato generato il processo, è impossibile determinare se eventuali attacchi di software dannoso eseguiti come "svrhost" corrispondano a processi legittimi o meno.

Per analizzare i processi attivi mediante l'utilizzo di Task Manager, è sufficiente attenersi alla procedura sottostante:

**Per analizzare i processi attivi eseguiti sui sistemi Windows**

1.  Premere contemporaneamente i tasti **CTRL**+**ALT**+**CANC** per visualizzare la finestra **Protezione di Windows** e selezionare **Task Manager**.

    **Nota**: nei sistemi Windows 9*x* verrà visualizzato un elenco dei programmi in esecuzione anziché l'applicazione Task Manager.

2.  Fare clic sulla scheda **Processi**.

3.  Ridimensionare la finestra Task Manager Windows per visualizzare tutti i processi attivi inclusi nella schermata.

4.  Selezionare l'opzione **Visualizza** dalla barra dei menu, quindi scegliere **Seleziona colonne.**

5.  Selezionare le caselle di controllo per le seguenti colonne:

    -   PID (Identific. processo)

    -   Utilizzo CPU

    -   Tempo CPU

    -   Utilizzo memoria

    -   Picchi utilizzo memoria

    -   Letture I/O

    -   Scritture I/O

6.  Scegliere **OK** e ridimensionare la finestra per visualizzare il maggior numero di colonne possibile.

Per ordinare le colonne è sufficiente fare clic sul titolo. Utilizzare questo metodo di ordinamento per ognuna delle colonne elencate e determinare le risorse utilizzate dai diversi processi.

**Nota**: per ottenere la stampa dell'elenco come copia di riferimento, attivare la finestra di Process Explorer o di Task Manager Windows e premere **ALT+STAMP** sulla tastiera. Negli Appunti del computer viene catturata la schermata dell'elenco che può essere incollata nell'applicazione Paint di Windows o in Microsoft Word per poi essere stampata.

Nella seguente figura sono indicati i dettagli relativi al processo attivo del worm Blaster in Task Manager di Microsoft Windows 2000® Server.

[![](images/Dd536186.AVFG0403(it-it,TechNet.10).gif "Figura 4.3 Visualizzazione del processo attivo del worm Blaster in Task Manager di Windows 2000")](https://technet.microsoft.com/it-it/dd536186.avfg0403_big(it-it,technet.10).gif)

**Figura 4.3 Visualizzazione del processo attivo del worm Blaster in Task Manager di Windows 2000**

**Nota**: è possibile che, per motivi di protezione, l'avvio di Task Manager venga bloccato dal software dannoso. In questo caso, è possibile utilizzare l'utilità della riga di comando **Tasklist** disponibile sui sistemi Microsoft Windows® XP e Windows Server™ 2003 (o l'utilità della riga di comando **TList** di Windows 2000) per generare un semplice elenco dei file di testo. È quindi possibile copiare i file su un supporto rimovibile per un'analisi ulteriore. Per generare un file di testo con l'elenco di tutti i processi attivi, utilizzare la sintassi della riga di comando riportata di seguito:

```
tasklist /v >TaskList.txt
```

Mediante la riga di comando indicata verrà creato il file **TaskList.txt** nella directory di lavoro corrente.

Quando si ha il sospetto che sul sistema venga eseguito software dannoso, è consigliabile controllare i processi facendo riferimento ai seguenti suggerimenti:

-   Controllare le istanze dei servizi Telnet e FTP (File Transfer Protocol) in esecuzione.

-   Se non si è sicuri di un processo, utilizzare un motore di ricerca su Internet, ad esempio Google, per cercare ulteriori informazioni in merito.

-   Controllare il percorso del file di immagine dei processi di cui si riconosce il nome dell'immagine.

-   Individuare i servizi in esecuzione e quelli interrotti.

Oltre al processo msblast.exe visualizzato nella figura precedente, esistono altri possibili processi sospetti, ovvero:

-   ServuFTP

-   Ocxdll.exe

-   Kill.exe

-   Mdm.exe

-   Mdm.scr

-   Mt.exe

-   Ncp.exe

-   Psexec.exe

-   Win32load.exe

###### Controllo delle cartelle di avvio

È possibile che in seguito a un tentativo di autoesecuzione del software dannoso, le cartelle di avvio del sistema subiscano delle modifiche.

**Nota**: il percorso di queste cartelle verrà modificato a seconda del sistema operativo analizzato. Le seguenti informazioni sono relative ai sistemi operativi Windows XP, Windows Server 2003 e Windows 2000.

Le cartelle di avvio presentano due aree che devono essere controllate. La prima è rappresentata dalla cartella **Tutti gli utenti** che in genere si trova nella seguente posizione predefinita:

C:\\Documents and Settings\\All Users\\Menu Avvio

La seconda è rappresentata dal percorso del profilo utente relativo all'account attualmente connesso, per quanto sarebbe importante controllare tutti i profili creati sul sistema e non solo l'account attualmente connesso. Queste informazioni si trovano in C:\\Documents and Settings\\*&lt;NomeUtente&gt;*\\Menu Avvio in cui il *&lt;NomeUtente&gt;* rappresenta l'ID di accesso degli utenti definiti sul sistema analizzato.

**Nota**: sui sistemi Microsoft Windows® 95 e Windows® 98 è possibile che il software dannoso riesca a rinominare la cartella di avvio. Per ulteriori informazioni su questo argomento, vedere l'articolo della Microsoft Knowledge Base "141900: Folder Other Than StartUp Launches Programs" (in inglese) su Microsoft.com all'indirizzo: <http://support.microsoft.com/?kbid=141900>

Controllare tutte le voci incluse nella cartella di avvio per accertarsi che durante l'avvio del sistema non venga eseguito alcun tentativo di esecuzione di software dannoso.

###### Controllo delle applicazioni pianificate

È inoltre possibile (solo di rado) che la presenza di software dannoso determini l'utilizzo del servizio Utilità di pianificazione di Windows e l'esecuzione di applicazioni non autorizzate. Per verificare che ciò non accada, è sufficiente attenersi alla procedura sottostante ed eseguire un semplice controllo della coda dell'Utilità di pianificazione:

**Per controllare la coda dell'Utilità di pianificazione**

1.  Fare clic su **Start**, quindi scegliere **Esegui**, digitare **at** e infine premere **INVIO**.

2.  Controllare l'elenco. Se vengono visualizzate applicazioni non autorizzate o sospette, creare un report per analisi future utilizzando il seguente comando:

    -   Fare clic su **Start**, quindi scegliere **Esegui**, digitare at &gt;C:\\AT\_Queue\_Report.txt e infine premere **INVIO**.

Eseguendo il comando specificato verrà creato un file di testo nella cartella principale dell'unità C: che dovrà essere spostato su un disco rimovibile per analisi future. Controllare il file di testo per determinare se nella coda sono pianificate eventuali applicazioni non autorizzate.

Dopo aver completato l'analisi dei processi attivi e di quelli pianificati, è possibile identificare il processo o i processi introdotti dall'attacco. Al termine del rilevamento, è necessario riavviare il sistema e ripetere l'analisi per stabilire se in seguito all'attacco sono state violate altre aree del sistema o se sono stati eseguiti processi inaffidabili all'avvio. In questo caso, sarà necessario completare l'analisi dei file di avvio del sistema e del Registro di sistema per individuare il meccanismo utilizzato per la gestione del processo o dei processi inaffidabili.

##### Analisi del Registro di sistema locale

Poiché il Registro di sistema completato è un archivio dati esteso e complesso, è consigliabile crearne una copia per eseguire un'analisi dettagliata al termine del processo di ripristino da un attacco.

Per eseguire il backup e il ripristino dell'intero Registro di sistema, è possibile utilizzare l'utilità di backup inclusa in tutte le versioni di Windows. Se l'utilità viene utilizzata regolarmente per eseguire il backup del disco rigido, è possibile includere nella procedura anche il Registro di sistema. Per eseguire il backup del Registro di sistema con l'applicazione di backup, selezionare **Stato del sistema** quando si scelgono le unità, i file e le cartelle che si desidera includere nel set di backup.

Poiché lo stato del sistema include altre informazioni specifiche del sistema nonché il Registro di sistema, le dimensioni dei file di backup possono corrispondere a centinaia di megabyte. In alternativa, è possibile utilizzare le utilità di modifica del Registro di sistema incluse nelle versioni di Windows. Queste utilità sono particolarmente indicate per eseguire una copia del Registro di sistema. In Windows XP e Windows Server 2003 sono inclusi due strumenti di modifica del Registro di sistema, **Regedit.exe** e lo strumento della riga di comando **Reg.exe**.

**Nota**: nei sistemi operativi Windows 2000 e Windows NT® viene utilizzato **Regedt32.exe** e sono richiesti gli strumenti del Resource Kit **RegBack.exe** *e* **RegRest.exe** per garantire le stesse funzionalità di **Regedit.exe** e **Reg.exe**. Per ulteriori informazioni su questi strumenti, vedere la pagina "Backing up and Restoring the Windows 2000 Registry" del *Resource Kit di Windows 2000* su Microsoft.com all'indirizzo:
[http://www.microsoft.com/windows2000/
techinfo/reskit/en-us/regentry/RegistryBackup.asp](http://www.microsoft.com/windows2000/techinfo/reskit/en-us/regentry/registrybackup.asp) (in inglese).

**Per eseguire una copia di backup del Registro di sistema mediante l'utilizzo di Regedit**

1.  Fare clic su **Start**, quindi scegliere **Esegui**, digitare regedit e infine premere **INVIO**.

2.  Nel riquadro a sinistra, selezionare **Computer locale**, quindi scegliere **Esporta** dal menu **File**.

3.  Nella casella **Nome file**, immettere il nome e il percorso per la copia del file del Registro di sistema.

4.  In **Intervallo di esportazione**, selezionare **Tutto**, quindi scegliere **Salva**.

Per informazioni dettagliate sull'utilizzo di **Regedit.exe** e **Reg.exe**, è possibile consultare la pagina "Registry Reference for Windows Server 2003" della guida sulla distribuzione di Windows Server 2003 all'indirizzo:
[http://www.microsoft.com/resources/documentation/WindowsServ/2003/all/deployguide/
en-us/RegistryBackup.asp](http://www.microsoft.com/resources/documentation/windowsserv/2003/all/deployguide/en-us/registrybackup.asp) (in inglese).

**Importante**: poiché il disco verrà esposto a software dannoso, è consigliabile evitare che venga condiviso da altri sistemi finché non viene trovato un metodo di controllo efficace.

Dopo aver completato il backup del Registro di sistema, è necessario verificare se sono presenti riferimenti a file anomali nelle aree seguenti:
        ```
Queste aree del Registro di sistema spesso diventano i principali obiettivi del codice dannoso perché consentono l'esecuzione automatica del software dannoso all'avvio del sistema. Ad esempio, il worm W32@.Mydoom.G@mm determina l'aggiunta del seguente valore:
        ```
nelle chiavi del Registro di sistema riportate di seguito:
        ```
Un'altra area presa recentemente in considerazione come obiettivo è la chiave seguente:
        ```
Questa chiave controlla i file dll caricati da Microsoft Internet Explorer (**Explorer.exe**). Il worm Mydoom e le relative varianti, ad esempio, determinano l'aggiunta di una voce nella chiave che consente di caricare file dll in grado di provocare una vulnerabilità e un attacco di backdoor.

Il worm W32.Netsky.D@mm determina l'eliminazione sia della chiave sopra indicata che delle chiavi seguenti:
        ```
##### Verifica della presenza di software dannoso e file danneggiati

Poiché la maggior parte del software dannoso comporta la modifica di uno più file presenti sul disco rigido del computer, il processo per l'identificazione di tali file potrebbe rivelarsi davvero difficile. Se il sistema è stato creato da un'immagine, è possibile confrontare il sistema infetto direttamente con il nuovo sistema creato dall'immagine.

Se questa opzione non è disponibile, è possibile identificare i file modificati eseguendo una ricerca sull'intero sistema di tutti i file modificati dall'introduzione del software dannoso nel sistema. La ricerca può essere eseguita mediante l'utilizzo dello strumento di ricerca di Windows. Nella seguente schermata viene indicato come restringere la ricerca dei file infetti mediante le opzioni avanzate del riquadro **Risultati ricerca**.

[![](images/Dd536186.AVFG0404(it-it,TechNet.10).gif "Figura 4.4 Finestra delle opzioni avanzate dei risultati della ricerca")](https://technet.microsoft.com/it-it/dd536186.avfg0404_big(it-it,technet.10).gif)

**Figura 4.4 Finestra delle opzioni avanzate dei risultati della ricerca**

Se le opzioni vengono configurate così come indicato nella figura, verranno indicati tutti i file creati nel giorno in cui il software dannoso è stato introdotto nel computer host (nell'esempio, il 27 aprile 2004).

È inoltre possibile creare un file di testo con l'elenco, a volte molto lungo, di tutti i file inclusi nella directory corrente e nelle relative sottodirectory.

**Per creare un elenco di tutti i file inclusi in una directory e nelle relative sottodirectory**

1.  Fare clic su **Start**, quindi scegliere **Esegui**, digitare cmd e infine premere **INVIO**.

2.  Passare alla directory che si desidera documentare.

3.  Al prompt dei comandi, digitare dir /s /-c /o:-d /t:c /q &gt; FileList.txt, quindi premere **INVIO**.

All'esecuzione del comando, nella directory corrente verrà creato il file di testo **FileList.txt** di cui è consigliabile eseguire una copia su un supporto rimovibile per ulteriori analisi.

**Nota:** per creare questo stesso tipo di elenco è possibile ricorrere all'utilizzo di altri strumenti e script. Tuttavia, lo scopo della presente sezione è quello di consentire all'utente di acquisire le informazioni in modo rapido utilizzando gli strumenti disponibili sul sistema. Se si è avuto tempo sufficiente per preparare un toolkit di risposta alle emergenze con script più avanzato, è preferibile utilizzare il toolkit anziché la procedura indicata di seguito.

Al termine della ricerca, è possibile ordinare i risultati in base al tipo per identificare più facilmente i file eseguibili che in genere rappresentano l'obiettivo del software dannoso. Nell'elenco seguente vengono indicati alcuni esempi dei tipi di file più comuni che possono contenere codice eseguibile:

\*.exe        \*.html        \*.cmd        \*.htm

\*.bat        \*.cpl        \*.pif        \*.pot

\*.vbs        \*.vbe         \*.js        \*.jse

\*.scr        \*.jpg         \*.doc        \*.xls

\*.mdb        \*.com        \*.ocx

**Nota:** l'elenco della ricerca potrebbe contenere un numero di voci talmente elevato da non consentire, in questa fase del processo, l'analisi di tutte le modifiche eseguite. Tuttavia, è importante salvare una copia dell'elenco o eseguirne una stampa per esaminare i probabili file di destinazione non appena si dispone di tempo sufficiente per farlo.

I seguenti file potrebbero indicare la presenza di software dannoso nel sistema:

-   DLL16.ini

-   DLL32.hlp

-   DLL32NT.hlp

-   Gates.txt

-   Gg.bat

-   Httpsearch.ini

-   Seced.bat

-   Xvpll.hlp

-   Psexec.bat

-   Lcp\_netbios.dll

Questi file, in genere utilizzati negli attacchi di software dannoso, vengono indicati per illustrare le tecniche di denominazione utilizzate per tentare di nascondere i file di software dannoso. Se non si è sicuri del nome di un file specifico, a volte è sufficiente eseguire una ricerca su Internet per acquisire ulteriori informazioni sulla natura dei file e stabilire se si tratta di file collegati a software dannoso. Tuttavia, è importante che la ricerca venga eseguita su un sistema non infetto, in quanto la stessa esplorazione di Internet può essere compromessa dagli attacchi di software dannoso.

È inoltre necessario tenere presente che in molti attacchi di software dannoso vengono utilizzati nomi di file di sistema validi, ma che tali file vengono inseriti in cartelle differenti per evitare che possano essere identificati dal servizio di protezione file di Windows. Ad esempio, il file **Svchost.exe**, che in passato è stato utilizzato da software dannoso, viene normalmente installato e protetto nella cartella %WINDIR%\\System32. Ad ogni modo, gli esempi di software dannoso in grado di creare file con lo stesso nome direttamente nella cartella %WINDIR% sono stati già esaminati. È importante controllare sia il percorso completo sia i nomi dei file.

Di seguito sono riportate alcune delle aree di destinazione comuni in cui vengono inclusi e modificati i file durante gli attacchi di software dannoso:

-   **%Windir%**. È la variabile assegnata alla cartella di installazione predefinita dei sistemi operativi Windows. In questa cartella sono inclusi importanti file eseguibili e di configurazione. Per impostazione predefinita, la variabile punterà ai seguenti percorsi di cartella:

    -   C:\\Windows (per i sistemi Windows 95/98/ME/XP e Windows Server 2003).

    -   C:\\Winnt\\ (per i sistemi Windows NT/2000).

-   **%System%**. È la variabile assegnata alla cartella di sistema sottostante la cartella di installazione predefinita dei sistemi operativi Windows. In questa cartella sono inclusi i file del sistema operativo host. Per impostazione predefinita, la variabile punterà ai seguenti percorsi di cartella:

    -   C:\\Windows\\System (per i sistemi Windows 95/98/ME).

    -   C:\\Winnt\\System32 (per i sistemi Windows NT/2000).

    -   C:\\Windows\\System32 (per i sistemi Windows XP e Windows Server 2003).

-   **%Temp%**. È la variabile assegnata al percorso utilizzato dalle applicazioni per la scrittura dei file temporanei. Per impostazione predefinita, la variabile è assegnata ai seguenti percorsi:

    -   C:\\Windows\\TEMP (per i sistemi Windows 95/98/ME).

    -   C:\\WINNT\\Temp (per i sistemi Windows NT/2000).

    -   C:\\Document and Settings\\*&lt;NomeUtente&gt;*\\Local Settings\\Temp (per i sistemi Windows XP e Windows Server 2003).

-   **%Temporary Internet Files%**. È la variabile utilizzata dalle applicazioni browser Internet per l'archiviazione dei file temporanei durante l'esplorazione del Web. Per impostazione predefinita, la variabile punta ai seguenti percorsi:

    -   C:\\Windows\\Temporary Internet Files (per i sistemi Windows 95/98/ME).

    -   C:\\Document and Settings\\*&lt;NomeUtente&gt;*\\Local Settings\\Temporary Internet Files (per i sistemi Windows NT/2000/XP e Windows Server 2003).

Se l'analisi dei file del sistema rivela la presenza di file infetti, sarà necessario copiare i file in un supporto rimovibile per analisi future. Ovviamente, poiché si tratta di file infetti, sarà necessario prevedere passaggi tali da limitare l'utilizzo di questi file solo ai processi stabiliti. Di seguito sono riportati alcuni passaggi che possono essere presi in considerazione per assicurare la protezione delle copie:

-   **Modifica dell'estensione del nome dei file**. Modificando l'estensione del nome dei file e assegnando un'estensione non riconosciuta dal sistema operativo, non sarà possibile eseguire il file in modo accidentale. Si può sostituire, ad esempio, l'ultima lettera del file **Avirus.exe** con un trattino in modo da ottenere **Avirus.ex\_**.

-   **Memorizzazione dei file infetti in un archivio protetto**. È consigliabile comprimere i file infetti e proteggere i file compressi mediante l'utilizzo di una password.

-   **Supporti specifici**. È consigliabile utilizzare dischi colorati o etichette di tipo non standard in modo da poter differenziare i supporti rimovibili da quelli standard.

-   **Custodia dei file in un luogo sicuro**. È consigliabile custodire i supporti con gli esempi del software dannoso in un luogo sicuro o in una qualsiasi struttura protetta.

-   **Utilizzo di archivi protetti per l'invio tramite posta elettronica**. In caso sia necessario inviare software dannoso sospetto tramite posta elettronica (ad esempio, al fornitore del programma antivirus), è consigliabile inoltrare i file di archivio protetti da password. Se il software dannoso viene inviato come normale allegato non protetto, è probabile che venga analizzato e rilevato dai gateway di posta elettronica.

    **Nota**: in molti attacchi di software dannoso vengono utilizzati archivi protetti per eludere le tecniche di analisi dei programmi antivirus. Di conseguenza, diverse organizzazioni bloccano o mettono in quarantena tutti i file archiviati in ingresso. Prima di inviare il file, è consigliabile verificare che il destinatario designato disponga di un simile meccanismo e che tale meccanismo sia attivato.

##### Controllo di utenti e gruppi

In molti attacchi di software dannoso vengono eseguiti tentativi per elevare i privilegi degli utenti del sistema o aggiungere nuovi account ai gruppi che dispongono di privilegi amministrativi. Di seguito sono indicate alcune impostazioni anomale da verificare:

-   Gruppi e account utente inconsueti.

-   Nomi utente inadatti.

-   Gruppi con appartenenza non valida per l'utente.

-   Diritti utente non validi.

-   Privilegi elevati di recente per account utente o di gruppo.

-   Infine, è necessario controllare che tutti i membri del gruppo Administrators siano validi.

Utilizzare lo snap-in MMC per gruppi e utenti locali per verificare la presenza di aggiunte insolite nel gruppo Administrators locale. Inoltre, controllare che nel registro di protezione del computer locale non siano presenti voci anomale. Ad esempio, alcune voci della categoria "Gestione account", tra cui l'evento 636, indicano che è stata eseguita l'aggiunta di un nuovo membro in un gruppo locale. In questi registri vengono indicate anche la data e l'ora in cui è avvenuta la modifica.

Se il sistema esaminato è un server Windows, utilizzare lo snap-in MMC per gruppi e utenti di Active Directory per esaminare anche l'appartenenza al gruppo di dominio. Per ulteriori informazioni sui gruppi e gli utenti predefiniti di Windows 2000, vedere la pagina "Default User Accounts and Groups" su Microsoft TechNet all'indirizzo:
[http://www.microsoft.com/technet/prodtechnol/windows2000serv/
evaluate/featfunc/07w2kadb.mspx](http://www.microsoft.com/technet/prodtechnol/windows2000serv/evaluate/featfunc/07w2kadb.mspx) (in inglese) e l'articolo della Knowledge Base "243330: Well Known Security Identifiers in Windows Server Operating Systems" in cui vengono fornite informazioni sugli identificatori di protezione più noti e sui gruppi e gli utenti ad essi associati, disponibile sul sito Microsoft.com all'indirizzo:
<http://support.microsoft.com/?kbid=243330> (in inglese).

**Nota:** benché le informazioni degli articoli facciano riferimento a Windows 2000, sono valide anche per Windows 2003 in cui non sono cambiati i gruppi predefiniti di base. Tuttavia, in Windows Server 2003 sono stati introdotti altri gruppi predefiniti, ovvero Servizio di rete e Servizio locale. Per ulteriori informazioni, verificare la configurazione predefinita del sistema.

##### Controllo delle cartelle condivise

Un altro sintomo tipico della presenza di software dannoso è l'utilizzo di cartelle condivise per la diffusione dell'infezione. Per verificare lo stato delle cartelle condivise nel sistema infetto, utilizzare lo snap-in MMC Gestione computer o eseguire **NetShare** *dalla riga di comando. Nelle seguenti tabelle vengono indicate le condivisioni predefinite di server e client Windows.*

**Nota:** per impostazione predefinita, nei computer Windows 9*x* non vengono condivisi né file né cartelle a meno che la condivisione file non sia attivata. Inoltre, nei client Windows 9*x* non esistono condivisioni "admin$" o condivisioni nascoste equivalenti, ma sono disponibili solo le cartelle o i volumi che vengono condivisi in modo specifico tramite la rete (impedendo qualsiasi tipo di violazione del sistema o l'installazione di software controllato in remoto).

**Tabella 4.1: Cartelle condivise predefinite di Windows XP**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Cartella condivisa</th>
<th style="border:1px solid black;" >Percorso condiviso</th>
<th style="border:1px solid black;" >Commento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ADMIN$</td>
<td style="border:1px solid black;">C:\Windows</td>
<td style="border:1px solid black;">Amministratore remoto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">C$</td>
<td style="border:1px solid black;">C:\</td>
<td style="border:1px solid black;">Condivisione predefinita.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">&lt;n&gt;$</td>
<td style="border:1px solid black;">&lt;n:&gt;\</td>
<td style="border:1px solid black;">Rappresenta una condivisione per la directory principale di ciascuna unità disco rigido sul sistema.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SharedDocs</td>
<td style="border:1px solid black;">C:\Documents and Settings\All Users\Documenti</td>
<td style="border:1px solid black;">Verrà aggiunto se è stata abilitata la condivisione locale dei file.</td>
</tr>
</tbody>
</table>
  
**Tabella 4.2: Condivisioni cartelle predefinite di Windows Server 2003 e Windows 2000 Server**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Cartella condivisa</th>
<th style="border:1px solid black;" >Percorso condiviso</th>
<th style="border:1px solid black;" >Commento</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ADMIN$</td>
<td style="border:1px solid black;">C:\Windows</td>
<td style="border:1px solid black;">Amministratore remoto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">C$</td>
<td style="border:1px solid black;">C:\</td>
<td style="border:1px solid black;">Condivisione predefinita.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">&lt;n&gt;$</td>
<td style="border:1px solid black;">&lt;n:&gt;\</td>
<td style="border:1px solid black;">Rappresenta una condivisione per la directory principale di ciascuna unità disco rigido sul sistema.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SharedDocs</td>
<td style="border:1px solid black;">C:\Documents and Settings\All Users\Documenti</td>
<td style="border:1px solid black;">Verrà aggiunto se è stata abilitata la condivisione locale dei file.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Wwwroot$</td>
<td style="border:1px solid black;">C:\inetpub\wwwroot</td>
<td style="border:1px solid black;">Verrà configurata se i servizi IIS sono stati installati come server Web.</td>
</tr>
</tbody>
</table>
  
È inoltre possibile esaminare le autorizzazioni per le condivisioni con lo strumento della riga di comando **SrvCheck** dalla pagina "Microsoft Windows Server 2003 Resource Kit Tools" su Microsoft.com all'indirizzo [http://go.microsoft.com/fwlink/?LinkId=4544](http://go.microsoft.com/fwlink/?linkid=4544) (in inglese).
  
Altre utilità di terze parti come **Dumpsec**, che è possibile scaricare dal sito Web SystemTools.com all'indirizzo [http://www.somarsoft.com](http://www.somarsoft.com/), possono essere utilizzate per la generazione dei report.
  
##### Controllo delle porte di rete aperte
  
In molti attacchi di software dannoso viene eseguito un tentativo per rendere più vulnerabili i sistemi violati in modo da attaccarli più facilmente in seguito. Una tecnica spesso utilizzata prevede l'apertura delle porte di rete che verranno utilizzate dall'utente malintenzionato in modo da ottenere un altro accesso al computer host.
  
Per esportare gli elenchi delle impostazioni delle porte di rete correnti sono disponibili diversi strumenti, tra cui **PortQRY**, incluso negli strumenti di supporto di Microsoft Windows Server 2003. Per ulteriori informazioni su questo strumento, consultare l'articolo della Knowledge Base "832919: New features and functionality in PortQry version 2.0" su Microsoft.com all'indirizzo: <http://support.microsoft.com/?kbid=832919> (in inglese).
  
In alternativa, è possibile utilizzare l'utilità della riga di comando **FPort** disponibile sul sito Foundstone all'indirizzo: [http://www.foundstone.com](http://www.foundstone.com/).
  
Infine, è possibile utilizzare l'utilità della riga di comando **NetStat** inclusa nei sistemi Windows che consente di verificare lo stato delle connessioni di rete correnti e delle porte di rete in attesa. Questo strumento può essere usato per ottenere la stampa completa dello stato delle porte e delle connessioni di rete.
  
**Per creare un report NETSTAT**
  
-   Sul computer host infetto fare clic su **Start**, quindi scegliere **Esegui**, digitare **Netstat -an** &gt;c:\\netstat\_report.txt e infine premere **INVIO**.
  
    **Nota:** se si esegue Netstat su Windows XP o versione successiva, è consigliabile utilizzare il comando seguente che consente di visualizzare nel report anche l'identificatore di processo (PID) associato:
  
    Netstat -ano &gt;c:\\netstat\_report.txt
  
Nella cartella principale dell'unità C: verrà creato il file di testo **netstat\_report.txt** (è possibile aggiungere anche la data al nome del file) . Il file deve essere salvato su un supporto rimovibile per analisi future.
  
##### Utilizzo di un analizzatore di protocolli di rete
  
Per creare un registro del traffico di rete con i dati trasmessi da e verso l'host infetto, è possibile utilizzare uno strumento per l'analisi dei protocolli di rete. Il file di traccia della rete deve essere salvato nel gruppo dei file di informazioni per analisi future.
  
Tra gli esempi di analizzatori di protocolli di rete che possono essere utilizzati per la creazione di file di traccia della rete sono inclusi il componente Network Monitor di Microsoft Systems Management Server (SMS) e altri strumenti di terze parti, tra cui l'analizzatore Ethereal disponibile sul sito Web Ethereal all'indirizzo: <http://www.ethereal.com/>.
  
##### Controllo ed esportazione dei registri degli eventi di sistema
  
È possibile utilizzare i registri degli eventi di sistema Windows per individuare un'ampia gamma di comportamenti anomali che possono essere esaminati per identificare le modifiche eseguite da software dannoso e per controllare quando tali modifiche sono avvenute. Per salvare i diversi tipi di file di registrazione degli eventi (applicazione, protezione e sistema) su un supporto rimovibile per ulteriori analisi, è consigliabile utilizzare la console di gestione Visualizzatore eventi. Per impostazione predefinita, i file vengono memorizzati nella directory C:\\Winnt\\System32\\Config\\ e vengono denominati **AppEvent.evt**, **SecEvent.evt** e **SysEvent.evt**. Tuttavia, quando il sistema è attivo i file sono bloccati e devono essere esportati mediante lo strumento di gestione Visualizzatore eventi.
  
Di seguito sono riportati alcuni suggerimenti in cui viene indicato come utilizzare i registri per determinare gli effetti provocati da un attacco di software dannoso:
  
-   Individuare le modifiche avvenute al momento dell'attacco sospetto.
  
-   Confrontare gli orari del registro eventi con gli orari di creazione e modifica dei file.
  
-   Individuare gli account creati o di cui è stata modificata la password al momento dell'intrusione sospetta.
  
Al termine del processo di analisi è possibile, a seconda della natura del software dannoso, ristabilire la connessione delle reti isolate. Ad esempio, se l'analisi evidenzia che la diffusione di software dannoso avviene solo tramite una specifica applicazione peer-to-peer, sarà sufficiente modificare i filtri del firewall perimetrale per bloccare le porte di rete utilizzate dall'applicazione e garantire il ripristino delle reti e degli altri servizi. Tale soluzione consente all'organizzazione di ritornare a un livello di comunicazione normale mentre viene avviato il processo di ripristino del sistema.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Passaggio 4: Ripristino del sistema
  
Dopo aver acquisito le informazioni richieste sull'attacco e averne stabilito la natura, è possibile avviare il processo di rimozione del software dannoso e di ripristino dei dati danneggiati dai sistemi infetti.
  
**Importante**: anche se si dispone di un'applicazione antivirus in grado di riconoscere e neutralizzare gli attacchi di software dannoso, Microsoft consiglia di determinare sempre la data e l'ora dell'infezione e di stabilire le cause che l'hanno provocata. Senza queste informazioni è difficile stabilire quali sistemi, supporti di backup o supporti rimovibili siano stati esposti all'attacco.
  
La modalità di completamento del processo dipende soprattutto dalla natura specifica dell'attacco di software dannoso. Tuttavia, per garantire il ripristino completo sia dei dati che dei sistemi, è possibile utilizzare il seguente processo avanzato:
  
1.  Ripristinare i dati danneggiati o mancanti.
  
2.  Rimuovere o pulire i file infetti.
  
3.  Verificare che i sistemi non contengano software dannoso.
  
4.  Riconnettere i computer alla rete.
  
Verificare che nel sistema non sia contenuto software dannoso è un passaggio fondamentale che non deve essere trascurato. In genere, molti dei pericoli correlati a software dannoso non vengono rilevati per lunghi periodi di tempo. Inoltre, le immagini di backup o i punti di ripristino del sistema possono includere file di sistema infetti in grado di causare altre infezioni se corrispondono all'origine del ripristino. Per questo motivo, è fondamentale verificare la data e l'ora della prima istanza di un attacco di software dannoso, se possibile. Quando si dispone di un indicatore di data e ora come riferimento, è possibile confrontare le date per determinare se le immagini di backup contengono lo stesso software dannoso.
  
#### Pulizia o ricostruzione
  
Quando si decide di ripristinare il sistema, si ha la possibilità di scegliere tra due opzioni. La prima prevede la pulitura del sistema e si basa sulle caratteristiche note dell'attacco per annullare in modo sistematico i danni provocati. La seconda invece comporta la ricostruzione o *azzeramento* del sistema. In ogni caso, decidere quale delle due opzioni utilizzare non è una scelta semplice.
  
Se si ha la certezza assoluta che gli elementi dell'attacco siano stati analizzati in modo adeguato e che la procedura di pulitura ripristinerà tutti gli elementi danneggiati, è consigliabile scegliere di eseguire la pulitura del sistema. Anche se i fornitori dei programmi antivirus in genere forniscono la documentazione richiesta, a volte potrebbero essere necessari diversi giorni per stabilire la natura dell'attacco. La pulitura del sistema spesso si lascia preferire in quanto ripristina lo stato originario del sistema con applicazioni e dati intatti. Inoltre, consente di ripristinare il normale utilizzo del sistema in tempi più rapidi rispetto alla procedura di ricostruzione. Tuttavia, in assenza di un'analisi dettagliata del codice dannoso, la pulitura del sistema potrebbe non rimuovere il software dannoso completamente.
  
Il rischio principale che si corre con la pulitura del sistema è rappresentato dalla possibilità che alcuni elementi dell'infezione iniziale, o altri attacchi e infezioni secondarie, non vengano scoperti né analizzati lasciando il sistema infetto o esposto all'esecuzione di software dannoso. A causa di questo rischio, molte organizzazioni decidono di procedere alla ricostruzione dei sistemi infetti per essere assolutamente certi della rimozione del software dannoso.
  
In genere, quando il sistema viene attaccato in corrispondenza dei punti in cui sono installati backdoor o rootkit, Microsoft consiglia di eseguire la ricostruzione del sistema. Per ulteriori informazioni su questi tipi di attacchi, vedere il capitolo 2, "Pericoli correlati a software dannoso" della presente guida. Diversi componenti di questi tipi di attacchi sono difficili da rilevare in modo affidabile e spesso si ripresentano nonostante i tentativi eseguiti per cercare di rimuoverli. Questi attacchi puntano a ottenere l'accesso non autorizzato ai sistemi violati il che consente a eventuali utenti malintenzionati di elevare i propri privilegi o installare software personalizzato. Per questi motivi, l'unico modo per essere assolutamente certi che il sistema non sia sottoposto a ulteriori attacchi di software dannoso è quello di ricostruirlo utilizzando supporti attendibili e di configurarlo in modo da eliminare i punti deboli che hanno favorito il verificarsi degli attacchi, ad esempio la mancanza di un aggiornamento di protezione o l'utilizzo di una password semplice.
  
Questo processo, inoltre, richiede l'acquisizione e la valutazione di tutti i dati utente necessari appartenenti al sistema infetto, la correzione degli elementi danneggiati, l'analisi dei dati per verificare che non contengano alcun software dannoso e infine il ripristino dei dati puliti nel nuovo sistema ricostruito.
  
La ricostruzione di un sistema richiede anche la reinstallazione di tutte le applicazioni precedentemente disponibili nonché la configurazione appropriata di ognuna di esse. La ricostruzione, pertanto, rappresenta il metodo più sicuro per eliminare un'infezione o neutralizzare un attacco, ma in genere richiede tempi di esecuzione molto più lunghi rispetto alla pulitura.
  
Per scegliere l'opzione più adatta per il proprio sistema, è sufficiente individuare la soluzione che si ritiene più affidabile per eliminare l'infezione e neutralizzare l'attacco in modo definitivo. Il tempo richiesto per la riparazione deve essere considerato come un aspetto secondario rispetto all'integrità e alla stabilità del sistema.
  
**Tabella 4.3: Vantaggi e svantaggi relativi alla pulitura e alla ricostruzione del sistema**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Pulitura</th>
<th style="border:1px solid black;" >Ricostruzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Processo semplice, se sono disponibili gli strumenti di pulitura.</td>
<td style="border:1px solid black;">Processo più complesso, specialmente se non viene installata una soluzione di backup e ripristino prima dell'infezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Minor numero di passaggi richiesti per garantire la pulitura dei dati.</td>
<td style="border:1px solid black;">Maggior numero di passaggi richiesti per l'acquisizione, il backup, la pulitura, l'analisi e il ripristino dei dati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Meno risorse richieste per l'utilizzo degli strumenti di rimozione rispetto a quelle necessarie per la ricostruzione dell'intero sistema.</td>
<td style="border:1px solid black;">Il processo di ricostruzione richiede molto tempo e risorse per poter essere completato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Rischio che l'infezione non venga eliminata completamente dal sistema.</td>
<td style="border:1px solid black;">Rischio ridotto che l'infezione non venga eliminata completamente dal sistema se il ripristino viene eseguito da supporti puliti e dati gestiti in modo adeguato.</td>
</tr>
</tbody>
</table>
  
**Nota:** se si decide di eseguire la pulitura di un sistema infetto, il team legale e il team di gestione dell'organizzazione devono eseguire un'analisi dei rischi per stabilire se si intende accettare il rischio di eventuali attacchi futuri nel caso in cui venga tralasciata una parte di codice dannoso durante il processo di pulitura.
  
#### Pulitura del sistema
  
Se gli attacchi e il comportamento del software dannoso sono documentati e le procedure di pulitura risultano testate e collaudate, è consigliabile prendere in considerazione la pulitura del sistema come opzione praticabile. Per le procedure documentate è possibile rivolgersi agli amministratori, mentre per ottenere gli strumenti automatici in grado di eliminare l'infezione dal sistema, è possibile contattare Microsoft o i fornitori di programmi antivirus. Entrambe le opzioni hanno lo scopo di annullare le azioni eseguite durante l'infezione al fine di ripristinare lo stato operativo originale del sistema. In genere, le procedure vengono rese disponibili solo per i virus e i worm principali e qualche giorno dopo l'inizio dell'infezione causata da software dannoso.
  
**Nota:** poiché molti attacchi di software dannoso sono basati su virus rilasciati ciclicamente, ad esempio MyDoom@A, MyDoom@B e così via, è molto importante utilizzare solo strumenti o procedure di pulitura che consentano di eliminare dal sistema versioni specifiche del software dannoso.
  
Se non è disponibile alcuno strumento automatico per eliminare il software dannoso dal sistema, è possibile eseguire questa operazione manualmente facendo riferimento alla procedura di base riportata di seguito:
  
1.  Arresto dei processi di esecuzione del software dannoso. È necessario terminare tutti i processi correlati al software dannoso attualmente in esecuzione nonché le voci eseguite automaticamente o le attività pianificate associate al software dannoso da rimuovere.
  
2.  Rimozione dei file introdotti da software dannoso. Questo passaggio richiede un'analisi dettagliata dei file inclusi nelle unità disco rigido dell'host per individuare i file contenenti software dannoso.
  
3.  Applicazione degli aggiornamenti o delle patch di protezione più recenti per ridurre le vulnerabilità evidenziate dall'attacco originale. Questo passaggio può richiedere diversi riavvii del sistema e la visita del sito Web Windows Update per verificare la disponibilità di aggiornamenti di protezione applicabili.
  
4.  Modifica delle password (di dominio o locali) che potrebbero essere state violate o delle password semplici e facilmente identificabili. Per ulteriori informazioni sull'impostazione di password complesse, vedere la pagina "Strong Passwords" su Microsoft.com all'indirizzo:  
    [http://www.microsoft.com/resources/documentation/WindowsServ/2003/enterprise/proddocs/  
    en-us/windows\_password\_tips.asp](http://www.microsoft.com/resources/documentation/windowsserv/2003/enterprise/proddocs/en-us/windows_password_tips.asp) (in inglese).
  
5.  Annullamento delle modifiche di sistema introdotte da software dannoso. Questo passaggio può richiedere il ripristino del file host locale e la configurazione del firewall nel sistema.
  
6.  Ripristino dei file utente modificati o eliminati da software dannoso.
  
Se si decide di eseguire i passaggi indicati manualmente, l'eliminazione dell'infezione dipenderà solo dall'esecuzione della procedura, in quanto solo in un secondo momento sarà possibile eseguire un confronto con le procedure di pulitura pubblicate per verificare se sono stati eseguiti tutti i passaggi necessari. In alternativa, se l'organizzazione dispone di un team di supporto antivirus, sarà il team a dover verificare che le procedure di verifica e risoluzione dei problemi utilizzate siano adeguate per identificare e limitare tutti i possibili vettori di attacco. Se le procedure vengono ritenute adeguate e invece non lo sono, potrebbe verificarsi una nuova infezione in tempi rapidi.
  
#### Ripristino o reinstallazione
  
Se si stabilisce che la migliore soluzione è la ricostruzione, è possibile ripristinare il sistema mediante un'immagine precedente, eseguirne una copia di backup se si è certi che è pulito o reinstallare il sistema da un supporto originale.
  
Se si sceglie di ripristinare il sistema da un'immagine precedente, è consigliabile tentare di salvare i dati dell'utente più recenti presenti sul sistema infetto per evitare che i dati creati e aggiornati nell'intervallo di tempo successivo al backup vadano persi. Se si ricostruisce il sistema da un supporto originale e non attraverso una copia di backup, l'unica possibilità di evitare la perdita di dati è quella di proteggerli dal sistema infetto prima dell'esecuzione del backup.
  
##### Recupero dei dati dal sistema infetto
  
La risorsa più preziosa di un sistema è rappresentata dai dati che vi sono contenuti. Per questo motivo, è fondamentale valutare attentamente come salvare, ripristinare e riparare i dati, eseguirne il backup e ripristinarli sul sistema al termine della ricostruzione.
  
Per ripristinare il sistema in modo completo, è necessario acquisire i seguenti tipi di dati in modo appropriato:
  
-   **Dati di configurazione del sistema operativo**. Questi dati comprendono tutte le impostazioni di configurazione richieste per ripristinare lo stato originale del sistema operativo e consentire il corretto funzionamento dei servizi sul computer host.
  
-   **Dati delle applicazioni**. Questi dati comprendono tutti i dati utilizzati e memorizzati dalle applicazioni installate sulla periferica host.
  
-   **Dati dell'utente**. Questi dati comprendono tutti i dati di configurazione, ad esempio profili utente e file generati dall'utente.
  
    **Nota**: è ovvio che gli stessi dati preservati siano seriamente esposti al rischio di infezioni. È quindi necessario prestare estrema attenzione durante l'utilizzo di questi dati finché non viene identificato un metodo di controllo affidabile.
  
È consigliabile eseguire il backup di tutti i dati su un supporto sicuro o in una posizione a cui sia impedito l'accesso e l'esecuzione da parte di sistemi e utenti non autorizzati. Se necessario, occorre utilizzare gli strumenti o le altre risorse disponibili per ripristinare i dati e archiviarli in modo sicuro finché non è possibile ripristinarli sul sistema ricostruito.
  
##### Ripristino da un'immagine o da una copia di backup
  
Per ripristinare i dati da un'immagine o da una copia backup, è necessario acquisire l'immagine mediante uno strumento di ripristino prima che l'infezione comprometta il sistema. È disponibile un gran numero di strumenti che consentono di semplificare drasticamente le operazioni di backup e ripristino dei dati di un sistema. Questi strumenti garantiscono un livello di protezione elevato non solo contro le infezioni causate da software dannoso, ma anche contro gli errori hardware e altri pericoli potenziali a cui è esposto il sistema. Anche se nella presente guida non viene presa in considerazione la configurazione di un'infrastruttura completa per il ripristino di emergenza, nelle sezioni seguenti verranno indicate alcune tecnologie chiave che possono essere utilizzate per risolvere eventuali problemi correlati ai programmi antivirus.
  
###### Windows System Restore
  
Windows System Restore (WSR) consente di proteggere i file critici di applicazioni e sistemi eseguendone il controllo, la registrazione e il backup prima che i file vengano modificati. È importante verificare se l'applicazione antivirus supporta WSR, in quanto in WSR viene creato un punto di ripristino che può essere esposto alle infezioni di software dannoso se viene utilizzato per pulire il sistema subito dopo un attacco iniziale. In questo caso, è possibile che il software dannoso possa essere reintrodotto nel sistema dal punto di ripristino infetto. Fortunatamente, nelle applicazioni antivirus abilitate WSR viene rilevata la presenza di software dannoso durante i processi di ripristino. Se vengono rilevati file infetti, nell'applicazione antivirus verrà eseguito un tentativo per modificarli, spostarli o eliminarli. Se i file vengono puliti in modo corretto, verranno automaticamente ripristinati da WSR. Tuttavia, se alcuni file non possono essere puliti e vengono eliminati o messi in quarantena, il processo di ripristino non verrà completato in quanto l'isolamento di un file determina uno stato di ripristino incoerente. In questo caso, in WSR verrà ripristinato lo stato precedente del sistema (prima dell'inizio dell'operazione di ripristino).
  
Per ulteriori informazioni sull'utilizzo delle applicazioni antivirus con questo servizio, vedere l'articolo della Knowledge Base "831829: How antivirus software and System Restore work together" su Microsoft.com all'indirizzo: <http://support.microsoft.com/?kbid=831829> (in inglese).
  
**Nota:** poiché i file delle firme dei virus vengono aggiornati per coprire gli attacchi di software dannoso, è possibile che le operazioni di ripristino non riuscite in precedenza vengano completate all'aggiornamento delle applicazioni antivirus. Al contrario, se si esegue il ripristino da un punto specifico ma un nuovo file della firma consente il rilevamento di un attacco in un file di cui è stato eseguito il backup e che non può essere pulito, è possibile che il processo di ripristino non venga completato.
  
Per ulteriori informazioni su Windows System Restore, vedere la pagina "How to Restore Windows XP to a Previous State" su Microsoft.com all'indirizzo:  
<http://www.microsoft.com/windowsxp/pro/using/itpro/managing/restore.asp> (in inglese).
  
###### Automated System Recovery
  
Automated System Recovery (ASR) consente di eseguire in modo rapido il backup dei volumi di avvio e dei volumi del sistema presenti sul computer assicurando il ripristino immediato del sistema in caso di errori o infezioni. Tuttavia, come per altri supporti di backup, è possibile che i file di backup ASR possano essere infettati da software dannoso. Per ulteriori informazioni sulla tecnologia ASR e sulla relativa modalità di utilizzo all'interno dell'organizzazione, vedere il white paper "How ASR Works" su Microsoft.com all'indirizzo: [http://www.microsoft.com/resources/documentation/WindowsServ/2003/all/deployguide/  
en-us/sdcbc\_sto\_axho.asp](http://www.microsoft.com/resources/documentation/windowsserv/2003/all/deployguide/en-us/sdcbc_sto_axho.asp).
  
###### Soluzione di backup di Windows
  
La soluzione di backup inclusa nei sistemi operativi Windows è particolarmente indicata per i reparti e le imprese di piccole e medie dimensioni. Tuttavia, come per WSR e ASR, è possibile che i file di backup contengano software dannoso infetto. Per questo motivo, se si utilizza questa soluzione è necessario accertarsi che nel sistema non venga ripristinato software dannoso e che tale software non venga riavviato. È inoltre necessario controllare e analizzare tutti i file di backup con un'applicazione antivirus aggiornata che sia in grado di rilevare e rimuovere il software dannoso prima che venga utilizzata l'immagine di backup per il ripristino del sistema. Per informazioni dettagliate sul ripristino di emergenza, incluse le operazioni di backup e ripristino, vedere la sezione "Planning for Disaster Recovery" di *Windows Server 2003 Deployment Kit* su Microsoft.com all'indirizzo: [http://www.microsoft.com/resources/documentation/  
WindowsServ/2003/all/deployguide/en-us/sdcbc\_sto\_gqda.asp](http://www.microsoft.com/resources/documentation/windowsserv/2003/all/deployguide/en-us/sdcbc_sto_gqda.asp) (in inglese).
  
##### Reinstallazione del sistema
  
Dopo aver verificato che i dati di backup siano affidabili, è possibile avviare il processo di ricostruzione del sistema. A questo punto del processo è consigliabile riformattare le unità, cambiare le dimensioni della partizione ed eseguire tutta la manutenzione richiesta per ottenere prestazioni ottimali del sistema al termine del ripristino. Se possibile, è consigliabile ricostruire i server utilizzando una condivisione integrata aggiornata completamente. Per ulteriori informazioni sulla creazione di installazioni integrate di Windows, vedere:
  
-   La sezione "Combination Installation" di *Microsoft Windows XP Hotfix Installation and Deployment Guide* su Microsoft.com all'indirizzo:
  
    [http://www.microsoft.com/WindowsXP/pro/downloads/  
    servicepacks/sp1/hfdeploy.asp\#the\_combination\_installation\_gxsi](http://www.microsoft.com/windowsxp/pro/downloads/servicepacks/sp1/hfdeploy.asp) (in inglese).
  
-   La sezione "Installing Windows 2000 with the Service Pack and Hotfixes" di *Windows 2000 Hotifx Installation and Deployment Guide* su Microsoft.com all'indirizzo:
  
    [http://www.microsoft.com/windows2000/downloads  
    /servicepacks/sp3/HFDeploy.htm\#installing\_windows\_2000\_with\_hotfixes\_ykot](http://www.microsoft.com/windows2000/downloads/servicepacks/sp3/hfdeploy.htm) (in inglese).
  
Se non è possibile eseguire la ricostruzione da un'origine integrata, si corre il rischio che il sistema venga infettato da software dannoso della rete prima che sia possibile connettersi al sito Web Windows Update per scaricare gli aggiornamenti di protezione e i Service Pack importanti. In questo caso, eseguire la reinstallazione attenendosi alla procedura seguente:
  
1.  Disconnettersi dalla rete. Il modo migliore è quello di scollegare la presa di alimentazione del computer dalla rete.
  
2.  Installare il sistema operativo dal supporto di installazione del sistema originale. Durante la procedura è indispensabile creare password complesse per gli amministratori locali di ogni computer. Tali password devono essere univoche per ogni computer.
  
3.  Avviare il sistema e accedere mediante l'account di amministratore locale.
  
4.  Attivare un firewall host sul sistema, ad esempio il Firewall connessione Internet di Windows XP.
  
    **Nota**: in Windows XP Service Pack 2 il Firewall connessione Internet è stato rinominato *Windows Firewall* ed è attivato per impostazione predefinita su tutte le connessioni di rete. Se il sistema si basa su Windows 2000 o una versione precedente, è consigliabile installare un firewall host di terze parti.
  
5.  Riconnettere il sistema alla rete. A questo punto, per ridurre i rischi durante la ricostruzione del sistema, è importante eseguire i passaggi riportati di seguito quanto prima possibile.
  
6.  Aggiornare il sistema installato di recente con gli aggiornamenti software più recenti. È importante tenere presente che non tutti gli aggiornamenti di protezione sono offerti dal sito Web Windows Update. Sul sito sono disponibili solo gli aggiornamenti principali per la protezione del sistema operativo e non gli aggiornamenti relativi ad altri prodotti, ad esempio SQL Server™, Front Page, Commerce Server e così via. Per questo motivo, è consigliabile visitare il sito Microsoft Security Bulletin Search su Microsoft TechNet all'indirizzo: <http://www.microsoft.com/technet/security/current.mspx> per verificare gli aggiornamenti specifici del prodotto.
  
7.  Installare un pacchetto antivirus, verificare che sia utilizzata la versione più recente del file della firma del virus ed eseguire un'analisi antivirus completa del sistema.
  
8.  Aumentare la protezione della configurazione del sistema facendo riferimento alle linee guida per la protezione avanzata dell'organizzazione. Per ulteriori informazioni sulla procedura, vedere il capitolo 3, "Difesa antivirus a più livelli" della presente guida.
  
9.  Verificare se nel sistema sono presenti altre vulnerabilità mediante l'utilizzo di uno strumento di analisi delle vulnerabilità, ad esempio Microsoft Baseline Security Analyzer (MBSA). Questo strumento può essere scaricato gratuitamente dal sito Microsoft.com all'indirizzo:  
    <http://www.microsoft.com/technet/security/tools/mbsahome.mspx>.
  
Dopo aver ricostruito il sistema e averlo analizzato per verificare che non vi siano contenuti file infetti, è possibile ripristinare i dati dell'utente.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Passaggio 5: Passaggi post ripristino
  
Nella seguente sezione vengono indicati i passaggi specifici che è necessario eseguire dopo aver controllato e ripristinato il sistema da un attacco di software dannoso iniziale. Per rafforzare i criteri generali dell'organizzazione relativi a utenti, processi e tecnologie, è importante completare i passaggi richiesti in questa fase.
  
#### Riunione di verifica post attacco
  
Questa riunione deve coinvolgere tutte le parti interessate e sollecitare la libera discussione degli argomenti trattati a vantaggio di tutti i partecipanti. In particolare, ai partecipanti verrà richiesto di:
  
-   Contattare il consulente legale per determinare se l'organizzazione intende intraprendere un'azione legale contro gli autori dell'attacco.
  
-   Contattare il consulente legale per determinare se l'organizzazione deve segnalare l'attacco alle autorità in caso di violazione di dati sensibili. Ad esempio, informazioni su carte di credito.
  
-   Assegnare un valore economico al danno causato dall'attacco per la creazione di report interni in cui siano inclusi i seguenti elementi:
  
    -   Le ore dedicate all'operazione di ripristino.
  
    -   Il costo per la riparazione delle apparecchiature danneggiate.
  
    -   La perdita di ricavi.
  
    -   Il costo o il danno provocato alle relazioni con partner e clienti.
  
    -   La perdita di produttività provocata dai dipendenti interessati.
  
    -   Il valore dei dati persi.
  
-   Provare a identificare le vulnerabilità utilizzate durante l'attacco per violare i sistemi.
  
-   Suggerire cambiamenti per i criteri di protezione antivirus su più livelli dell'organizzazione.
  
-   Suggerire cambiamenti per i criteri di protezione dell'organizzazione, ad esempio:
  
    -   Criteri password predefiniti avanzati.
  
    -   Criteri di controllo.
  
    -   Criteri per aggiornamenti di protezione.
  
    -   Criteri firewall.
  
#### Aggiornamenti post attacco
  
È consigliabile esaminare e valutare i risultati dei suggerimenti della riunione e accertarsi che vengano implementati all'interno dell'organizzazione nel più breve tempo possibile. Quando si individua una vulnerabilità specifica, è possibile ridurre l'esposizione del sistema utilizzando diverse soluzioni contemporaneamente.
  
È importante tenere presente che eventuali cambiamenti interessano i dipendenti, i processi e le tecnologie dell'organizzazione. L'analisi dei costi stimati in seguito all'attacco dell'organizzazione deve porre in evidenza i futuri vantaggi economici che l'organizzazione può trarre da una collaborazione interattiva tesa a scongiurare il verificarsi di altri attacchi.
  
A questo punto, se nell'organizzazione non è stata implementata alcuna soluzione di protezione antivirus su più livelli, vedere il capitolo 3, "Difesa antivirus a più livelli" della presente guida, per individuare gli elementi della soluzione che potranno garantire maggiori vantaggi per l'organizzazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Nel presente capitolo vengono forniti consigli e linee guida utili per ripristinare il sistema da un attacco di software dannoso in modo coerente ed equilibrato. È importante che i passaggi consigliati vengano eseguiti in modo uniforme perché, in caso di errori, si potrebbe esporre l'organizzazione ad altri attacchi di software dannoso. Eventuali errori, inoltre, potrebbero impedire all'organizzazione di intraprendere azioni legali contro gli autori dell'attacco.
  
Se nell'organizzazione è stata implementata una soluzione di protezione antivirus su più livelli, è probabile che non sia necessario utilizzarla spesso per neutralizzare gli attacchi. Tuttavia, se non si pianifica in anticipo la modalità di intervento corretta per gli scenari più difficili, è possibile esporre l'organizzazione a errori gravi nel caso in cui un attacco dovesse violare le protezioni antivirus.
  
Per prepararsi in anticipo a questa eventualità, è consigliabile formare lo staff di protezione sulle tecnologie di software dannoso comuni, incluse quelle descritte nel presente capitolo. Inoltre, sarebbe opportuno creare un toolkit per l'analisi di software dannoso contenente alcuni degli strumenti descritti nel presente capitolo, nonché script e altre utilità che possano essere utilizzate per acquisire e documentare in modo rapido le informazioni principali dei sistemi infetti. Questa preparazione consentirà di ridurre l'impatto sulle attività aziendali quando i sistemi verranno sottoposti a eventuali attacchi di software dannoso.
  
Ogni nuovo attacco può introdurre metodi differenti per violare o danneggiare i sistemi. Pertanto, Microsoft consiglia di visitare periodicamente il sito Web Microsoft Security Antivirus Information all'indirizzo: <http://www.microsoft.com/security/antivirus/>. Sul sito vengono fornite ulteriori informazioni sui programmi antivirus aggiornati e su come neutralizzare gli attacchi di software dannoso più recenti. L'utilizzo delle risorse incluse nel presente capitolo consente non solo di controllare in modo efficace l'impatto che potrebbe comportare la diffusione di software dannoso all'interno di un'organizzazione, ma anche di ripristinare il sistema in modo affidabile ed efficace.
  
[](#mainsection)[Inizio pagina](#mainsection)
