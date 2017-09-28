---
TOCTitle: 'Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi - Capitolo 3'
Title: 'Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi - Capitolo 3'
ms:assetid: '79c1ce91-0b3f-450c-a1d1-2dde34e9ebf3'
ms:contentKeyID: 20200865
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536266(v=TechNet.10)'
---

Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi
==============================================================================================

### Capitolo 3 - Problemi e requisiti

Aggiornato: 23 maggio 2005

##### In questa pagina

[](#eeaa)[Introduzione](#eeaa)
[](#edaa)[Rilevazione delle violazioni dei criteri](#edaa)
[](#ecaa)[Individuazione degli attacchi esterni](#ecaa)
[](#ebaa)[Implementazione dell'analisi legale](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

In una strategia di protezione efficace è fondamentale eseguire una valutazione accurata delle minacce che possono colpire la rete. Come per i problemi di sicurezza fisica negli ambienti di lavoro, i rischi di protezione dei dati sulla rete aziendale possono essere valutati in base a diversi criteri. I diversi punti di vista dipendono da numerosi fattori, ad esempio il settore industriale in cui opera l'azienda, l'importanza dei dati presenti nella rete ed eventuali esperienze precedenti di attacchi alla rete. Per ulteriori informazioni sulla gestione dei rischi di protezione, vedere [The Security Risk Management Guide](http://www.microsoft.com/technet/security/topics/policiesandprocedures/secrisk/default.mspx) all'indirizzo http://www.microsoft.com/technet/security/topics/policiesandprocedures
/secrisk/default.mspx (informazioni in lingua inglese).

I dati forniti dai partner e dai clienti Microsoft, uniti alle informazioni ricavate dalla rete aziendale di Microsoft, consentono di individuare i tre aspetti principali relativi al monitoraggio della protezione e alla rilevazione degli attacchi, ovvero:

-   Rilevazione delle violazioni dei criteri

-   Individuazione degli attacchi esterni

-   Implementazione dell'analisi legale

In questo capitolo verrà descritto ciascuno scenario, mentre nel Capitolo 4 "Progettazione della soluzione" verrà illustrato come configurare il sistema di monitoraggio della protezione e di archiviazione al fine di affrontare in modo adeguato queste minacce.

Per poter individuare eventuali attività insolite all'interno di una rete, è necessario avere un'idea ben chiara di ciò che è considerato normale nell'ambiente di rete. Lo scopo di questa guida è di consentire di distinguere un comportamento tipico da uno insolito.

Per individuare le anomalie è inoltre necessario implementare un modello standard di protezione su tutti i computer. In assenza di questo modello, non sarà possibile individuare i computer che non soddisfano i requisiti di base della protezione. Per ulteriori informazioni sull'implementazione di modelli di protezione, vedere gli [articoli su procedura](http://www.microsoft.com/technet/itsolutions/howto/default.mspx) relativi al problema della protezione all'indirizzo http://www.microsoft.com/technet/itsolutions/howto/default.mspx (informazioni in lingua inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Rilevazione delle violazioni dei criteri

La maggior parte dei problemi di protezione che le organizzazioni devono affrontare è costituita dalle violazioni dei criteri, che comprendono le seguenti azioni:

-   Creazione di account utente all'esterno del processo appropriato

-   Utilizzo dei privilegi di amministratore senza la corretta autorizzazione

-   Utilizzo degli account dei servizi per l'accesso interattivo

-   Tentativi di accesso a file per i quali non si dispone dell'autorizzazione

-   Eliminazione di file per i quali non si dispone dell'autorizzazione per l'accesso

-   Esecuzione di programmi non approvati

Il tipo più comune di violazione dei criteri riguarda i tentativi di accesso involontari da parte degli utenti, ad esempio il tentativo di aprire una directory per la quale non si dispone delle autorizzazioni necessarie. In questo caso, tuttavia, per impedire agli utenti di causare danni significativi è in genere sufficiente definire limitazioni di accesso e concedere diritti limitati. Una minaccia molto più grave è rappresentata dalle violazioni dei criteri da parte degli amministratori, sia volontarie che accidentali.

La presenza di amministratori di rete non affidabili costituisce una grave minaccia per un'organizzazione. Per poter svolgere il proprio lavoro, infatti, gli amministratori devono disporre di livelli elevati di privilegi e diritti di accesso al sistema. Gli amministratori hanno la possibilità di creare account utente, reimpostare password, nonché modificare i diritti di proprietà relativi a file e cartelle. Tuttavia, la possibilità di eseguire una determinata procedura non implica che siano effettivamente autorizzati a eseguirla. È inoltre necessario tenere presente che gli amministratori dispongono di diritti per l'accesso a risorse di rete che non sono autorizzati a vedere, ad esempio informazioni finanziarie riservate.

#### Problemi aziendali

Per la maggior parte delle organizzazioni, la rilevazione delle violazioni dei criteri deve avere un'importanza cruciale, a causa della probabilità che si possa verificare una violazione e della potenziale gravità del danno provocato. La corretta implementazione del sistema di rilevazione e prevenzione delle violazioni dei criteri implica le seguenti problematiche aziendali:

-   Controlli preliminari rigorosi prima dell'assunzione di nuovo personale e, periodicamente, dei dipendenti già assunti

-   Controlli di protezione indipendenti sulle azioni degli amministratori

-   Controlli periodici del sistema di monitoraggio della protezione

-   Individuazione rapida di eventuali violazioni della protezione

-   Verifica dell'entità della violazione della protezione

-   Limitazione del danno che può essere causato dalle violazioni della protezione

In genere, prima di assumere un nuovo dipendente, le organizzazioni effettuano controlli di protezione adeguati. In molti casi, tuttavia, questi controlli non vengono ripetuti per gli utenti interni.

È estremamente importante che gli utenti interni accettino esplicitamente i termini e le condizioni previsti dai requisiti per il monitoraggio della protezione della rete. Gli utenti devono essere consapevoli che un qualsiasi tentativo di apertura di file o di accesso a un oggetto condiviso per le quali non dispongono dell'autorizzazione necessaria verrà riportato nei registri di protezione. Gli utenti che devono utilizzare file particolarmente importanti devono sapere che nei registri di protezione saranno memorizzati tutti i tentativi di accesso a questi file.

**Nota: **è sempre più difficile perseguire legalmente o licenziare dipendenti senza poter dimostrare che essi erano pienamente consapevoli del sistema interno di monitoraggio della protezione nonché delle conseguenze dei tentativi intenzionali di accesso o distruzione di dati riservati. È possibile che le normative in materia di diritti umani e protezione dei dati richiedano anche il consenso esplicito da parte dell'utente.

##### Separazione delle responsabilità

All'interno delle organizzazioni dovrebbe essere implementata una separazione rigorosa delle responsabilità, in modo che il controllo delle azioni degli amministratori sia affidato a persone o gruppi differenti, ad esempio il reparto che si occupa della protezione o del controllo. Per evitare che il controllore si trasformi a sua volta in una minaccia per l'azienda, è inoltre opportuno che il gruppo che si occupa del controllo non disponga dell'autorizzazione per l'esecuzione di azioni amministrative.

##### Test delle funzioni di monitoraggio

È opportuno che nelle organizzazioni vengano svolti regolarmente alcuni test per verificare la correttezza delle funzioni di monitoraggio. È possibile, ad esempio, utilizzare test di penetrazione o un account amministratore di prova per verificare il corretto funzionamento degli avvisi. Questi test dovrebbero essere eseguiti ogni settimana in giorni differenti, per impedire a un utente malintenzionato di utilizzare il test di penetrazione come opportunità di attacco.

##### Definizione dei processi di protezione e delle risposte

Per individuare rapidamente eventuali violazioni della protezione all'interno di un'organizzazione, è necessario che sia disponibile una serie completa di processi che definiscono il modo in cui devono essere eseguite determinate operazioni sulla rete. Si supponga, ad esempio, che per creare gli account utente (provisioning) venga utilizzato un sistema di gestione delle identità quale MIIS (Microsoft Identity Integration Server) 2003. Anche se gli amministratori possono creare gli account utente direttamente, presso le organizzazioni dovrebbe essere stabilito un criterio che impedisce agli amministratori di eseguire questa operazione. In questo modo, se il sistema di monitoraggio della protezione rileva l'evento 624 (creazione di un account utente), tale evento deve essere collegato all'account di provisioning di MIIS 2003 e non all'account di un singolo amministratore.

Per limitare i danni causati dalle violazioni della protezione, è necessario definire risposte appropriate in caso di possibili problemi, ad esempio la rapida mobilizzazione del personale interno addetto alla protezione. La velocità e l'efficacia delle risposte ai problemi possono contribuire a migliorare significativamente il profilo di protezione di un'organizzazione. La consapevolezza che un qualsiasi problema di protezione sarà seguito da un'attenta fase di analisi riduce infatti la probabilità che gli utenti o gli amministratori tentino di violare un criterio di protezione.

Le notizie riportate dai media segnalano spesso minacce alle reti provenienti da origini esterne. L'esperienza, tuttavia, dimostra che la probabilità di perdita di dati o di attacchi da parte di utenti malintenzionati esterni è molto più bassa rispetto al rischio di perdita di dati a causa di un errore di configurazione da parte degli amministratori della rete. Anche se è consigliabile non abbassare mai la guardia nei confronti delle minacce esterne, occorre tenere presente che molte organizzazioni preferiscono fornire soluzioni che impediscono l'accesso alla rete da parte degli utenti esterni non autorizzati, poiché si tratta di soluzioni abbastanza facili da implementare. Nessuna organizzazione è invece in grado di fornire una soluzione che impedisca agli amministratori di compiere errori o di comportarsi in modo disonesto.

#### Problemi tecnici

Per implementare un valido sistema di monitoraggio della protezione e di rilevazione degli attacchi basato sulla registrazione degli eventi di protezione di Windows, è necessario prevedere soluzioni efficaci per le seguenti problematiche:

-   **Gestione di volumi elevati di eventi di protezione**. Per riuscire a gestire l'enorme quantità di eventi di protezione, è necessario valutare con attenzione le impostazioni di controllo della protezione che devono essere attivate. Questo risulta particolarmente importante per il controllo dell'accesso ai file e agli oggetti, che può generare una grande quantità di dati.

-   **Memorizzazione e gestione di grandi quantità di eventi in un archivio centrale**. L'archiviazione degli eventi può richiedere la gestione di enormi quantità di dati. Poiché si tratta di un requisito tecnico che riguarda soprattutto l'analisi legale, verrà illustrato in dettaglio nella sezione "Implementazione dell'analisi legale" più avanti in questo capitolo.

-   **Individuazione degli schemi di attacco**. Per individuare le firme di attacco, è necessario conoscere gli schemi degli eventi che indicano un attacco. Si consiglia di rispondere sempre in maniera appropriata e tempestiva quando viene rilevata una firma di attacco che individua un'intrusione.

-   **Limitazione dei privilegi degli amministratori in modo che non possano eludere i controlli di protezione**. Per impedire agli amministratori di aggirare i controlli di protezione, è necessario suddividere le responsabilità degli amministratori e creare o allocare un gruppo di specialisti della protezione che abbia il compito di sorvegliare i controlli degli amministratori.

#### Problemi di protezione

L'individuazione dei problemi di protezione costituisce l'aspetto principale di un sistema di monitoraggio della protezione e di rilevazione degli attacchi. Un sistema valido deve essere in grado di individuare le seguenti situazioni:

-   Tentativi di accesso alle risorse mediante la modifica delle autorizzazioni file

-   Tentativi di accesso alle risorse mediante la reimpostazione delle password

-   Creazione di nuovi utenti

-   Inserimento degli utenti nei gruppi

-   Utilizzo di account amministrativi non autorizzati

-   Tentativi di accesso alla console mediante l'utilizzo di credenziali degli account dei servizi

-   Esecuzione di programmi non autorizzati

-   Danneggiamento volontario dei file (escluso il danneggiamento causato da errori del disco)

-   Introduzione di sistemi operativi non autorizzati

-   Creazione o eliminazione di relazioni di trust

-   Tentativi di accesso con un account non corretto, ad esempio un account amministrativo generale

-   Modifiche non autorizzate ai criteri di protezione

Per individuare correttamente queste azioni, è necessario conoscere le sequenze di eventi tipiche ed essere in grado di distinguere tali sequenze dagli altri eventi di protezione.

#### Requisiti della soluzione

Per poter rilevare le violazioni dei criteri a livello di organizzazione e protezione, la soluzione deve includere:

-   Procedure di protezione ben definite in grado di controllare tutte le operazioni di rete

-   Insieme completo di registri di controllo della protezione

-   Insieme centralizzato e affidabile di registri di protezione con filtri appropriati per l'analisi

-   Livelli regolabili di controlli di protezione

-   Analisi di eventuali discrepanze, ad esempio omissioni, record mancanti e così via

Per poter individuare gli errori di configurazione, la soluzione deve includere:

-   Procedure di gestione delle modifiche ben definite (compresa la fase di convalida) in grado di controllare tutte le operazioni di rete

-   Insieme completo di registri di controllo della protezione

-   Insieme centralizzato e affidabile di registri di protezione

-   Analisi automatica dei registri di protezione in modo da individuare eventuali modifiche apportate alla configurazione

Per ulteriori informazioni sull'implementazione di una soluzione di questo tipo, vedere il Capitolo 4 "Progettazione della soluzione".

[](#mainsection)[Inizio pagina](#mainsection)

### Individuazione degli attacchi esterni

Esistono due tipi di attacchi esterni, quelli eseguiti dagli utenti malintenzionati e quelli messi in atto da applicazioni dannose. Questi due tipi di attacchi presentano caratteristiche e profili di rischio differenti. Gli utenti malintenzionati sono in grado di acquisire informazioni sulla rete di destinazione e di calibrare il proprio attacco in funzione di tali informazioni. Le applicazioni dannose, invece, possono colpire più computer e lasciare backdoor che possono essere sfruttate dagli utenti malintenzionati.

Il termine applicazioni dannose è in genere utilizzato per fare riferimento a numerose minacce, ad esempio virus, worm e trojan horse. Sebbene queste applicazioni possano risultare fastidiose e causare anche danni di una certa gravità, gli attacchi di questo tipo risultano più facili da bloccare rispetto a quelli effettuati direttamente dalle persone.

**Nota: **in questa guida non vengono fornite informazioni sugli attacchi che riguardano dispositivi hardware, ad esempio un keystroke logger, poiché un sistema di monitoraggio della protezione non è in grado di rilevare questi dispositivi.

#### Problemi aziendali

In questa guida vengono affrontati i problemi aziendali causati da attacchi esterni che tentano di penetrare all'interno della rete e che possono essere rilevati a livello di applicazione o di presentazione. Il monitoraggio della protezione non risulta particolarmente utile per l'individuazione di un attacco di tipo Distributed Denial of Service (DDoS). In questo caso, tuttavia, è possibile ricorrere ad altri meccanismi, ad esempio i registri di Microsoft Internet Information Services (IIS), che sono in grado di determinare la durata, il tipo di pacchetto e l'indirizzo IP effettivo (eventualmente sottoposto a spoofing) e di fornire altri dettagli sull'attacco DDoS.

L'individuazione delle applicazioni dannose è molto importante per qualsiasi tipo di organizzazione, soprattutto per quelle che operano nel settore finanziario o che devono rispettare specifiche normative. La principale preoccupazione di tali organizzazioni, ad esempio, riguarda la presenza di applicazioni spyware, che possono trovarsi in un server o in una workstation e comunicare informazioni riservate a entità esterne.

Uno degli aspetti più problematici delle applicazioni dannose consiste nella difficoltà di determinare la presenza di tali applicazioni all'interno della rete. Uno scenario particolarmente allarmante è dato dalla presenza di un rootkit o un programma simile che assume il controllo completo di un computer, mascherando quindi il fatto che il computer sia sotto il controllo di un utente malintenzionato. In questo caso è molto difficile essere sicuri che nei computer non siano in esecuzione applicazioni dannose, poiché il rootkit potrebbe riuscire a nasconderle.

#### Problemi tecnici

La maggior parte degli attacchi alle organizzazioni è opera di utenti malintenzionati inesperti che utilizzano script preconfigurati per sfruttare le eventuali vulnerabilità del sistema. I pericoli maggiori, tuttavia, provengono dal gruppo ristretto degli utenti malintenzionati esperti che, grazie anche allo scambio di informazioni, possono utilizzare diversi tipi di attacco per tentare di penetrare in una rete.

**Nota: **in questa guida, con il termine utente malintenzionato si intende una persona che esegue volontariamente un attacco. Di conseguenza, un virus, un worm o un trojan horse non sono compresi in questa categoria.

Il modo migliore per individuare le applicazioni dannose consiste nel tenere traccia dei processi. In questo modo, è possibile individuare ogni programma che viene avviato o arrestato in una workstation o un server. Il lato negativo di questo approccio è dato dalla generazione di un numero elevato di eventi, la maggior parte dei quali privi di interesse.

Esistono due aree in cui l'analisi dei processi può risultare difficile:

-   **Server Web che utilizzano Common Gateway Interface (CGI)**, in cui viene creato un nuovo processo ogni volta che si accede a una pagina.

-   **Workstation di sviluppo**, in cui le build delle applicazioni creano molti processi in breve tempo.

Questi fattori possono portare rapidamente alla creazione di un numero molto elevato di eventi o alla creazione continua di alcuni eventi. In entrambi i casi, sarà necessario applicare una serie di filtri allo scopo di separare gli eventi di attacco da quelli legittimi.

#### Problemi di protezione

Gli attacchi esterni determinano considerevoli problemi di protezione, poiché gli utenti malintenzionati hanno a disposizione diversi metodi di intrusione nella rete. Di seguito sono elencati i principali meccanismi utilizzati dagli utenti malintenzionati esterni per penetrare nelle reti:

-   Individuazione delle password

-   Modifica o reimpostazione delle password

-   Sfruttamento dei punti di vulnerabilità

-   Utilizzo di un inganno per indurre un utente a eseguire un'applicazione dannosa

-   Utilizzo della procedura di escalation dei privilegi per compromettere altri computer (questa tecnica è denominata *island-hopping*)

-   Installazione di un rootkit o di un trojan horse

-   Utilizzo di una workstation non autorizzata

-   Utilizzo di un attacco di *phishing*, in cui un messaggio di posta elettronica fraudolento contiene un collegamento a un sito Web dannoso

Il metodo principale per la rilevazione degli utenti malintenzionati e delle applicazioni dannose consiste nel tenere traccia dei processi. Questo metodo deve essere utilizzato con attenzione e integrato nei criteri di restrizione software in Criteri di gruppo. È estremamente importante che vengano definiti criteri molto rigorosi per indicare quali programmi possono essere eseguiti sui computer all'interno delle reti perimetrali.

**Nota: **i criteri di restrizione software possono avere effetti indesiderati sui computer portatili o a livello di ambiente dell'organizzazione. Si consiglia di creare sempre nuovi oggetti Criteri di gruppo per gestire i criteri di restrizione software e di non applicare restrizioni software tramite l'oggetto Criterio dominio predefinito.

Per ulteriori informazioni sull'utilizzo dei criteri di restrizione software, vedere [Using Software Restriction Policies to Protect Against Unauthorized Software](http://technet.microsoft.com/en-us/library/bb457006.aspx) all'indirizzo http://www.microsoft.com/technet/prodtechnol/winxppro/maintain/rstrplcy.mspx (informazioni in lingua inglese).

#### Requisiti della soluzione

I requisiti della soluzione per l'individuazione degli utenti malintenzionati esterni coincidono con quelli per l'individuazione delle minacce interne, ad esempio:

-   Utilizzo di una strategia di difesa a più livelli per l'implementazione della protezione

-   Insieme completo di registri di controllo della protezione

-   Insieme centralizzato e affidabile di registri di protezione

-   Analisi automatica dei registri di protezione in modo da individuare le firme di attacco

I requisiti della soluzione per la rilevazione delle applicazioni dannose coincidono con alcuni dei requisiti per l'individuazione delle minacce interne, ad esempio:

-   Procedure efficaci per il controllo di eventuali programmi software non autorizzati in esecuzione sulla rete

-   Registri di controllo della protezione correttamente configurati

-   Insieme centralizzato e affidabile di registri di protezione con filtri appropriati

-   Analisi automatica dei registri di protezione allo scopo di individuare comportamenti sospetti, se necessario con l'utilizzo di programmi di terze parti

Per ulteriori informazioni sulla protezione dagli attacchi dei virus, vedere [Guida alla difesa antivirus a più livelli](http://technet.microsoft.com/it-it/library/cc162791) all'indirizzo http://www.microsoft.com/technet/security/guidance/avdind\_0.mspx (informazioni in lingua inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Implementazione dell'analisi legale

L'analisi legale consente di tenere traccia del momento in cui si è verificato l'attacco, della gravità e delle conseguenze di una violazione della protezione e di individuare i sistemi che sono stati compromessi dagli utenti malintenzionati. Durante questa analisi è necessario registrare le seguenti informazioni:

-   Data e ora dell'attacco

-   Durata dell'attacco

-   Computer interessati dall'attacco

-   Eventuali modifiche apportate alla rete dall'utente malintenzionato

Poiché l'analisi legale è un argomento molto esteso, non sarà possibile trattarlo in maniera esauriente in questa guida. In particolare, non verranno discussi i requisiti per la raccolta delle prove dell'analisi legale e verranno presi in considerazione soltanto i dati ottenuti dal registro eventi protezione.

#### Problemi aziendali

L'analisi legale è diversa dagli altri scenari poiché i problemi non vengono analizzati in tempo reale ma soltanto dopo che si sono verificati. Lo scopo dell'analisi legale è di fornire un elenco dettagliato di tutti gli eventi di interesse che si sono verificati in uno o più computer. Il sistema di analisi deve essere in grado di gestire e archiviare grandi quantità di dati in un database appropriato.

Una decisione fondamentale riguarda il tempo di archiviazione dei dati legali. Le organizzazioni devono riuscire a determinare il periodo massimo di validità dei dati legali, trascorso il quale le informazioni diventano obsolete. Nella seguente tabella sono indicati i tempi di mantenimento tipici per i dati legali.

**Tabella 3.1. Limiti di archiviazione per l'analisi legale**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Fattori di archiviazione</p></th>
<th><p>Limite di archiviazione</p></th>
<th><p>Commenti</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Archiviazione in linea (database)</p></td>
<td style="border:1px solid black;"><p>21 giorni</p></td>
<td style="border:1px solid black;"><p>Fornisce l'accesso rapido agli eventi recenti</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Archiviazione non in linea (backup)</p></td>
<td style="border:1px solid black;"><p>180 giorni</p></td>
<td style="border:1px solid black;"><p>Limite accettabile per la maggior parte delle organizzazioni</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Ambiente con requisiti normativi</p></td>
<td style="border:1px solid black;"><p>7 anni</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Servizi segreti</p></td>
<td style="border:1px solid black;"><p>Permanente</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>
</tbody>
</table>
  
**Nota: **alcune organizzazioni, ad esempio ospedali ed enti pubblici, anziché definire un periodo minimo di mantenimento preferiscono specificare un limite massimo oltre il quale i dati devono essere eliminati.
  
In alternativa, è possibile utilizzare database in linea per mantenere gli eventi relativi alle ultime tre settimane e quindi archiviare quelli meno recenti in un formato particolarmente adatto alla compressione, ad esempio file di testo CSV, per l'archiviazione non in linea. Se necessario, sarà possibile successivamente importare questi file CSV nel database a scopo di analisi.
  
Indipendentemente dal sistema utilizzato, è necessario assicurarsi che i requisiti per l'analisi rapida degli eventi recenti siano soddisfatti e che sarà possibile eventualmente ripristinare gli eventi meno recenti. Per determinare la combinazione migliore dei tempi di mantenimento dei dati per l'archiviazione in linea e non in linea si consiglia di basarsi sulla propria esperienza in fatto di eventi di protezione all'interno dell'ambiente di lavoro corrente.
  
#### Problemi tecnici
  
Per implementare un valido sistema di monitoraggio della protezione per l'analisi legale è necessario disporre di una grande quantità di eventi attendibili. I requisiti per il monitoraggio della protezione sul client sono simili a quelli previsti per gli altri scenari. In questo caso, tuttavia, è necessario disporre di un database di archiviazione di dimensioni molto maggiori e di un sistema di gestione dei dati estremamente efficiente.
  
Di seguito sono riportati i requisiti di carattere tecnico:
  
-   Sistema protetto e affidabile per l'archiviazione dei dati in linea
  
-   Disponibilità di grandi quantità di spazio su dischi ad alte prestazioni per l'archiviazione in linea
  
-   Sistema affidabile per il backup degli eventi meno recenti su supporti di archiviazione
  
-   Gestione dello spostamento dei backup meno recenti in un archivio appropriato, se necessario
  
-   Ripristino delle informazioni dai backup precedenti
  
Questi requisiti non riguardano esclusivamente il monitoraggio della protezione. Gli amministratori del database, infatti, hanno la necessità di gestire problematiche analoghe per le applicazioni, ad esempio i database per l'elaborazione delle transazioni in linea (OLTP). Tuttavia, a differenza delle applicazioni OLTP e delle altre applicazioni di database tradizionali, nei database utilizzati per l'analisi legale occorre gestire un numero di operazioni di scrittura molto maggiore rispetto a quelle di lettura.
  
#### Problemi di protezione
  
In genere, la quantità dei dati raccolti per l'analisi legale cresce continuamente. In casi molto rari, è possibile che una determinata persona, ad esempio il responsabile della protezione di un'azienda, abbia l'esigenza di accedere a tali informazioni. È importante che nessun altro possa accedere a queste informazioni oppure interrompere la raccolta o modificare i dati. La protezione sul database deve essere assoluta. In altri termini, l'accesso ai dati relativi alla protezione deve essere consentito soltanto a una o due persone fidate.
  
#### Requisiti della soluzione
  
Di seguito sono riportati i requisiti della soluzione per l'implementazione dell'analisi legale:
  
-   Registri di controllo della protezione correttamente configurati
  
-   Controllo protetto delle voci dei registri di protezione
  
-   Insieme centralizzato e protetto di registri di protezione
  
-   Sistema affidabile per l'archiviazione delle informazioni relative al monitoraggio della protezione
  
-   Meccanismi di archiviazione efficaci
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo capitolo sono stati descritti i requisiti della soluzione per i tre scenari contenuti nella guida. Nel Capitolo 4 "Progettazione della soluzione" verrà illustrato come integrare questi elementi in modo da creare un sistema per il monitoraggio della protezione e la rilevazione degli attacchi.
  
##### Download
  
[![](images/Dd536266.icon_exe(it-it,TechNet.10).gif)Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://go.microsoft.com/fwlink/?linkid=41310)
  
[](#mainsection)[Inizio pagina](#mainsection)
