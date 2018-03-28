---
TOCTitle: Approcci per le medie imprese alla protezione contro la posta indesiderata in un ambiente Exchange Server
Title: Approcci per le medie imprese alla protezione contro la posta indesiderata in un ambiente Exchange Server
ms:assetid: '3eed9be9-ffd4-4138-9384-d8d849ad979c'
ms:contentKeyID: 20213189
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc875815(v=TechNet.10)'
---

Approcci alla protezione contro la posta indesiderata in un ambiente Exchange Server
====================================================================================

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Definizione](#eeaa)
[](#edaa)[Sfide](#edaa)
[](#ecaa)[Soluzioni](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Riferimenti](#eaaa)

### Introduzione

Questo documento è contenuto nella raccolta di indicazioni per la protezione delle aziende di medie dimensioni. Microsoft auspica che le seguenti informazioni risultino utili per la creazione di ambiente informatico più sicuro e produttivo.

#### Riepilogo

I messaggi di posta elettronica non richiesti, anche noti come posta indesiderata, sono messaggi inviati da un unico mittente con l'intento di comunicare simultaneamente con più cassette postali. L'obiettivo dello spammer, che rappresenta anche il metodo grazie al quale guadagna denaro, è inviare il messaggio all'utente finale per indurlo ad aprirlo e leggerlo. Esistono numerose tecniche utilizzate dagli spammer per inserire i messaggi in aree grigie nelle quali essi non possono essere facilmente rilevabili a livello di gateway.

Alcune ricerche di settore hanno rilevato che oltre il 40% dei messaggi di posta in arrivo è costituito da posta indesiderata. Questo flusso sempre crescente di posta indesiderata continua a rappresentare un'importante sfida per le medie imprese. La posta indesiderata non è solo fastidiosa, ma può anche trasformarsi in un costo aggiuntivo se si calcolano le potenziali perdite di produttività e le ulteriori risorse richieste per fronteggiarla.

Pertanto, è necessario individuare una soluzione concreta che consenta lo sviluppo di approcci in grado di bloccare la posta indesiderata.

Microsoft® Exchange Server 2003 con Service Pack 2 (SP2) comprende un'infrastruttura che integra diversi metodi di protezione contro la posta indesiderata in uno o più ambienti Exchange Server. Questa infrastruttura è chiamata Exchange Server 2003 Anti-Spam Framework e comprende filtri a diversi livelli: di connessione, di protocollo e di contenuto.

Gli approcci contenuti in questa infrastruttura consentono agli amministratori e agli utenti finali di filtrare e classificare precisamente la posta indesiderata. In questo modo, è possibile distinguere i messaggi indesiderati dai messaggi commerciali legittimi e decidere quale azione intraprendere.

L'obiettivo principale dell'infrastruttura è fornire agli amministratori e agli utenti soluzioni sufficientemente flessibili applicabili sia sul lato server che sul lato client. Questo documento illustra in dettaglio gli approcci citati, il funzionamento di ciascuno all'interno dell'infrastruttura e in che modo possono essere integrati. Presenta inoltre piani di valutazione e sviluppo, nonché una guida fase per fase nella sezione Distribuzione e gestione.

**Nota**   Microsoft fornisce anche un importante servizio che consente di contrastare la posta indesiderata. Questo servizio è chiamato Exchange Hosted Services o EHS. EHS è formato da quattro diversi servizi che contribuiscono alla protezione nelle medie imprese contro il malware inviato tramite posta elettronica, soddisfano i requisiti di conservazione ai fini della conformità, crittografano i dati per tutelarne la riservatezza e proteggono l'accesso alla posta elettronica durante e in seguito a eventuali situazioni di emergenza.
Il punto centrale di Exchange Hosted Services si basa su una rete distribuita di data center posizionati nei punti chiave della struttura di Internet. Ciascun data center contiene server con tolleranza di errore e bilanciamento del carico da sito a sito e da server a server.
Una descrizione dettagliata del servizio non è prevista nella presente guida. Per ulteriori informazioni, fare riferimento al white paper [Microsoft Exchange Hosted Services Overview](http://www.microsoft.com/exchange/services/services.mspx) (in inglese) all'indirizzo www.microsoft.com/exchange/services/services.mspx.

#### Panoramica

Questo documento comprende quattro sezioni principali nelle quali vengono illustrate le opzioni e soluzioni che consentono approcci concreti alla protezione contro la posta indesiderata nell'ambiente Exchange Server. Le quattro sezioni sono: Introduzione, Definizione, Sfide e Soluzioni.

##### Introduzione

Questa sezione offre un riepilogo del documento, nonché una panoramica della struttura e alcune informazioni relative ai destinatari.

##### Definizione

In questa sezione vengono forniti i dettagli relativi alla definizione e alla panoramica di Exchange Server 2003 Anti-Spam Framework. Questi dettagli sono utili per comprendere più approfonditamente le soluzioni riportate nel presente documento.

##### Sfide

In questa sezione vengono descritte alcune delle sfide affrontate da una media impresa nella scelta delle modalità di filtro della posta indesiderata tramite i diversi livelli forniti da Anti-Spam Framework.

##### Soluzioni

In questa sezione vengono discusse soluzioni concrete per la risoluzione dei problemi associati alla posta elettronica non richiesta. Vengono infatti valutati gli approcci e i piani di sviluppo rivolti a tali problemi e vengono fornite le informazioni fase per fase sulla distribuzione e la gestione dei seguenti metodi:

-   Protezione a livello di connessione

    -   Filtro connessioni IP

    -   Elenco indirizzi bloccati in tempo reale

-   Protezione a livello di protocollo

    -   Blocco mittenti e destinatari

    -   ID mittente

-   Protezione a livello di contenuto

    -   Filtro messaggi intelligente di Exchange

    -   Posta elettronica indesiderata di Outlook 2003 e Outlook Web Access

Oltre a Exchange Server 2003 Anti-Spam Framework, è fondamentale riconoscere l'importanza del ruolo della consapevolezza degli utenti nella lotta alla posta indesiderata negli ambienti Exchange Server. Questo argomento verrà discusso alla fine della sezione "Distribuzione e gestione".

#### Destinatari della guida

Questo documento è destinato principalmente ai professionisti IT e ai responsabili della gestione aziendale che si occupano della pianificazione e dell'implementazione degli approcci per la protezione contro la posta indesiderata in un ambiente Exchange Server nelle medie imprese. Questi professionisti possono ricoprire i seguenti ruoli:

-   **Architetti di sistema**. Responsabili della progettazione dell'intera infrastruttura del server, dello sviluppo di strategie e criteri di distribuzione dei server, del rafforzamento del sistema e del contributo alla progettazione della connettività di rete.

-   **Responsabili di reparti IT**. Responsabili tecnici con poteri decisionali e responsabili del personale IT che si occupa dell'infrastruttura, della distribuzione di desktop e server, nonché dell'amministrazione e delle operazioni tra siti per i server Exchange.

-   **Amministratori di sistemi**. Responsabili della pianificazione e della distribuzione della tecnologia tra server Microsoft Exchange, nonché della valutazione e delle decisioni relative a nuove soluzioni tecnologiche.

-   **Amministratori di messaggistica Exchange**. Responsabili dell'implementazione e della gestione della messaggistica organizzativa.

[](#mainsection)[Inizio pagina](#mainsection)

### Definizione

Exchange Server 2003 Anti-Spam Framework è una soluzione per la protezione contro la posta indesiderata nell'ambiente Exchange Server. Il rilascio di Exchange Server 2003 SP2 migliora l'infrastruttura grazie alla tecnologia standard per l'autenticazione della posta elettronica chiamata filtro ID mittente. Questa tecnologia consente di ridurre la quantità di posta indesiderata che giunge nella posta in arrivo dell'utente.

In questa sezione viene illustrato in dettaglio Exchange Server 2003 Anti-Spam Framework.

#### Exchange Server 2003 Anti-Spam Framework

Exchange Server 2003 applica la protezione contro la posta indesiderata su tre livelli diversi: a livello di connessione, a livello di protocollo e a livello di contenuto, come mostrato nella seguente figura.

![](images/Cc875815.AFSESE01(it-it,TechNet.10).gif "Figura 1. I tre livelli di protezione contro la posta indesiderata")

**Figura 1. I tre livelli di protezione contro la posta indesiderata**

La protezione a livello di connessione analizza l'host di connessione SMTP, la protezione a livello di protocollo analizza il mittente e il destinatario del messaggio, mentre la protezione a livello di contenuto valuta il contenuto del messaggio. Questi tipi di protezione contro la posta indesiderata vengono descritti singolarmente e in maggior dettaglio nelle seguenti sottosezioni.

##### Protezione a livello di connessione

La protezione a livello di connessione è una delle più efficaci barriere di difesa contro la posta indesiderata poiché, quando è attivata, il messaggio indesiderato non riesce a introdursi all'interno della media impresa. Come mostrato nella seguente figura, la protezione a livello di connessione funziona tramite l'analisi di tutte le connessioni SMTP in ingresso, che rappresentano la più probabile fonte di posta indesiderata.

[![](images/Cc875815.AFSESE02(it-it,TechNet.10).gif "Figura 2. Protezione a livello di connessione")](https://technet.microsoft.com/it-it/cc875815.afsese02_big(it-it,TechNet.10).gif)

**Figura 2. Protezione a livello di connessione**

Se l'host di connessione SMTP viene identificato come host che invia posta indesiderata o che generalmente non invia messaggi SMTP, la connessione può essere rifiutata, eliminando così costosi passaggi per determinare la natura del messaggio in ingresso. A tal fine, in Exchange Server 2003 sono disponibili due tipi di filtro a livello di connessione.

###### Filtro connessioni IP

Con Exchange Server 2003, è possibile scegliere esplicitamente di negare le connessioni SMTP basate su indirizzi IP. Questo approccio rappresenta il metodo più rudimentale per la protezione di un server Exchange poiché si basa sulla gestione manuale degli elenchi di filtro delle connessioni. Per negare le connessioni SMTP in ingresso da uno specifico host per una determinata ragione (inclusa la probabilità che sia fonte di posta indesiderata), è necessario agire a questo livello.

Le connessioni SMTP possono essere consentite esplicitamente. Per ricevere la posta da un host SMTP bloccato identificato come fonte di posta indesiderata, è possibile consentire i messaggi dall'host SMTP specificato; in caso contrario, tali messaggi vengono rifiutati.

###### Elenco indirizzi bloccati in tempo reale

Un metodo più dinamico per fornire protezione a livello di connessione è attraverso l'uso di elenchi indirizzi bloccati in tempo reale (RBL). Gli elenchi di indirizzi bloccati comprendono indirizzi IP riconosciuti come fonti di posta indesiderata, di inoltro aperto o parti di un ambito di indirizzi IP che non dovrebbe includere un host SMTP, ad esempio un indirizzo IP del pool di connessione remota Microsoft MSN®.

I provider di terze parti dell'elenco di indirizzi bloccati raccolgono indirizzi IP che si adattano a ciascun profilo. Quando un host di invio avvia una sessione SMTP con un sottoscrittore al servizio di elenchi di indirizzi bloccati, quest'ultimo inoltra una query di tipo DNS (Domain Name System) al provider degli elenchi di indirizzi bloccati con l'indirizzo IP dell'host connesso. Il provider risponde quindi con un codice che indica se l'host connesso è presente in un elenco e, facoltativamente, specifica tale elenco.

Il processo di filtro degli elenchi di indirizzi bloccati in tempo reale viene descritto di seguito e illustrato nella figura in basso.

1.  Un host SMTP si connette al server Exchange Server 2003 attraverso la porta 25 del protocollo TCP.

2.  Il server Exchange Server 2003 inoltra la query al provider degli elenchi di indirizzi bloccati configurato per verificare che l'host di connessione SMTP non sia nell'elenco di indirizzi bloccati.

3.  Se l'host di connessione SMTP non si trova nell'elenco di indirizzi bloccati, la connessione viene consentita. In caso contrario, la connessione viene interrotta.

[![](images/Cc875815.AFSESE03(it-it,TechNet.10).gif "Figura 3. Funzionamento del filtro con l'elenco di indirizzi bloccati in tempo reale")](https://technet.microsoft.com/it-it/cc875815.afsese03_big(it-it,TechNet.10).gif)

**Figura 3. Funzionamento del filtro con l'elenco di indirizzi bloccati in tempo reale**

Prima di Exchange Server 2003 SP2, la funzionalità di filtro connessioni non era disponibile in presenza di firewall o host SMTP intermediari tra Exchange e l'identità di invio (Exchange è posizionato dietro la rete perimetrale) poiché il filtro connessioni precedente a Exchange Server 2003 SP2 prendeva in considerazione solo l'host di connessione. Quando un host intermediario (ad esempio un firewall o altre apparecchiature SMTP) si trova tra l'host di invio ed Exchange, viene considerato solo l'host intermediario.

Con il rilascio di Exchange Server 2003 SP2, il server Exchange esegue correttamente il filtro connessioni da qualsiasi luogo all'interno della media impresa. Questa funzionalità può essere utilizzata fornendo elenchi di indirizzi IP perimetrici e una configurazione per l'intervallo IP in Gestore di sistema di Exchange. In questo modo, l'ID mittente e la funzionalità degli elenchi di indirizzi bloccati in tempo reale analizzano l'indirizzo IP da connettere all'host SMTP intermediario, ad esempio un firewall.

##### Protezione a livello di protocollo

[![](images/Cc875815.AFSESE04(it-it,TechNet.10).gif "Figura 4. Protezione a livello di protocollo")](https://technet.microsoft.com/it-it/cc875815.afsese04_big(it-it,TechNet.10).gif)

**Figura 4. Protezione a livello di protocollo**

Una volta che il messaggio SMTP supera la protezione a livello di connessione, la fase successiva di difesa è a livello del protocollo SMTP. Il dialogo SMTP tra l'host di invio SMTP e l'host di ricezione SMTP viene analizzato per verificare le autorizzazioni di mittente e destinatari e determinare il nome del dominio SMTP del mittente.

###### Blocco mittenti e destinatari

Un altro metodo per ridurre manualmente la posta indesiderata consiste nel definire i singoli mittenti o domini dai quali non si desidera accettare messaggi. Il blocco mittenti consente di specificare i singoli indirizzi o domini SMTP da bloccare. Con Exchange Server 2003, è anche possibile impedire il recapito di messaggi con l'indirizzo del mittente non specificato e archiviare i messaggi filtrati.

Il filtro destinatari consente di filtrare i messaggi inviati a uno specifico destinatario. È anche possibile filtrare i destinatari non elencati nella directory, benché in questo modo si rischia di esporre l'azienda a un attacco per la raccolta di indirizzi di posta SMTP, noto come attacco di tipo directory harvest (DHA). In questa situazione, le risposte del server Exchange ai comandi *RFC2821 RCPT TO:* vengono analizzate in cerca di indirizzi SMTP validi. Il protocollo SMTP riconosce i destinatari autorizzati durante una sessione SMTP utilizzando una risposta *250 2.1.5*. Quando viene inviato un messaggio di posta elettronica a un destinatario inesistente, il server Exchange restituisce un errore di tipo *550 5.1.1 Utente sconosciuto*. Pertanto, uno spammer può scrivere un programma automatico che utilizzi nomi comuni o termini di dizionario per creare indirizzi di posta elettronica in uno specifico dominio. Il programma può quindi raccogliere tutti gli indirizzi di posta elettronica che restituiscono *250 2.1.5 to RCPT TO: SMTP* e ignorare tutti quelli che provocano errori di tipo *550 5.1.1 Utente sconosciuto*. Lo spammer può quindi vendere indirizzi di posta elettronica validi o utilizzarli per l'invio di posta indesiderata.

Questa minaccia può essere mitigata utilizzando un metodo noto come *tarpitting*. La funzionalità di tarpitting SMTP di Microsoft Windows Server™ 2003 SP1 consente agli amministratori di inserire un ritardo configurabile prima di restituire le risposte per il protocollo SMTP. L'host che genera l'attacco non resta in attesa della risposta per un tempo sufficientemente lungo.

Per ulteriori informazioni, vedere l'articolo della Microsoft Knowledge Base "[Funzionalità tar pit SMTP per Microsoft Windows Server 2003](http://support.microsoft.com/?kbid=842851)" at http://support.microsoft.com/?kbid=842851.

###### ID mittente

Una delle più recenti aggiunte alle difese contro la posta indesiderata in Exchange Server 2003 è il filtro ID mittente. Questa funzionalità in Exchange Server 2003 SP2 tenta di verificare che l'host di invio SMTP sia approvato per l'invio dei messaggi dal dominio specificato nell'indirizzo di posta elettronica di invio. In molti messaggi indesiderati viene eseguito lo spoofing in modo che il messaggio sembri provenire da un indirizzo di posta elettronica attendibile. Inducendo il destinatario a credere che il messaggio di posta elettronica provenga da un'autorità attendibile (rappresentante di banca, servizio clienti e altro), gli utenti possono essere portati a rivelare informazioni riservate che consentono il furto d'identità o altri tipi di frodi. L'ID mittente tenta di ridurre o eliminare i messaggi di spoofing.  

Per il funzionamento del sistema, sono richieste due parti dell'ID mittente. La prima parte è un record DNS noto come record SPF (Sender Policy Framework). Il record SPF definisce i server autorizzati a inviare gli indirizzi SMTP per il dominio dell'utente. Non è necessario che l'ID mittente sia configurato per avere un record SPF. La seconda parte è un host SMTP che supporta l'ID mittente, ad esempio Exchange Server 2003 SP2.

Il record SPF viene aggiunto alla zona DNS in modo che le altre organizzazioni con l'ID mittente possano verificare che i messaggi ricevuti presumibilmente dal dominio specificato siano inviati dai server autorizzati nel record SPF. Le figure e le procedure descritte di seguito mostrano il funzionamento del processo, nel primo caso senza record SPF, quindi con l'inserimento di tale record.

1.  Un messaggio viene inviato al server Exchange Server 2003 dall'host SMTP di posta indesiderata fabrikam.com con l'ID mittente attivato. L'indirizzo del mittente è susanf@nwtraders.com.

2.  Il server Exchange inoltra le query al sistema DNS per il record SPF di nwtraders.com.

3.  Poiché nwtraders.com non dispone di un record SPF, il messaggio viene consentito dopo l'ID mittente.

[![](images/Cc875815.AFSESE05(it-it,TechNet.10).gif "Figura 5. Ricezione di posta indesiderata in un'organizzazione senza ID mittente/record SPF")](https://technet.microsoft.com/it-it/cc875815.afsese05_big(it-it,TechNet.10).gif)

**Figura 5. Ricezione di posta indesiderata in un'organizzazione senza ID mittente/record SPF**

Northwind Traders aggiunge quindi un record SPF alla zona DNS di nwtraders.com come descritto di seguito:

1.  Un messaggio viene inviato al server Exchange Server 2003 dall'host SMTP di posta indesiderata fabrikam.com con l'ID mittente attivato. L'indirizzo del mittente è susanf@nwtraders.com.

2.  Il server Exchange inoltra le query al sistema DNS per il record SPF di nwtraders.com.

3.  Poiché l'indirizzo IP di invio (208.217.184.82) non è compreso nell'elenco di indirizzi IP consentiti per l'invio di posta elettronica a nwtraders.com come definito nell'SPF (131.107.76.156), il messaggio viene gestito dall'ID mittente.

[![](images/Cc875815.AFSESE06(it-it,TechNet.10).gif "Figura 6. Posta indesiderata rilevata in un'organizzazione con ID mittente/record SPF ")](https://technet.microsoft.com/it-it/cc875815.afsese06_big(it-it,TechNet.10).gif)

**Figura 6. Posta indesiderata rilevata in un'organizzazione con ID mittente/record SPF**

Implementando l'ID mittente, è possibile ridurre significativamente la posta indesiderata inviata (con spoofing) dai domini che dispongono di un record SPF. Tuttavia, è necessario tenere presente che la protezione dell'ID mittente è valida solo per le organizzazioni che dispongono di record SPF.

In Microsoft.com, il 59% dei messaggi in ingresso che superano il filtro a livello di connessione viene bloccato a livello di protocollo.

##### Protezione a livello di contenuto

[![](images/Cc875815.AFSESE07(it-it,TechNet.10).gif "Figura 7. Protezione a livello di contenuto")](https://technet.microsoft.com/it-it/cc875815.afsese07_big(it-it,TechNet.10).gif)

**Figura 7. Protezione a livello di contenuto**

Dopo aver applicato il filtro a livello di connessione e di protocollo per determinare se un messaggio in ingresso sia indesiderato, la successiva linea di difesa consiste nell'analizzare il contenuto del messaggio stesso, concentrandosi su indizi comuni che indichino posta elettronica non richiesta. Gli spammer sono alla costante ricerca di metodi nuovi e creativi per evitare che i messaggi vengano rilevati come indesiderati in modo da consentire il superamento dei filtri del contenuto e riuscire a entrare nelle caselle di posta in arrivo degli utenti.

###### Filtro messaggi intelligente di Exchange

Filtro messaggi intelligente (IMF) è un filtro per il contenuto progettato appositamente per Exchange. Si basa su una tecnologia brevettata di apprendimento automatico sviluppata da Microsoft Research nota come tecnologia Microsoft SmartScreen®. SmartScreen viene attualmente utilizzato da MSN, Microsoft Hotmail®, Microsoft Office Outlook® 2003 ed Exchange. IMF è stato progettato, sulla base di milioni di messaggi, per distinguere le caratteristiche dei messaggi di posta elettronica attendibile da quelle di posta indesiderata. IMF analizza la probabilità che un messaggio in ingresso sia attendibile o indesiderato. Contrariamente ad altre tecnologie di filtro, IMF utilizza le caratteristiche individuate su un campione statisticamente rilevante di messaggi di posta elettronica. Il fatto che il campione IMF includa anche messaggi attendibili oltre alla posta indesiderata riduce la probabilità di errore infatti, la capacità di individuare le caratteristiche dei due tipi di messaggi aumenta la precisione di IMF.

IMF viene installato sui server Exchange che accettano i messaggi SMTP in ingresso da Internet. Quando un utente esterno invia messaggi di posta elettronica a un server Exchange sul quale è installato IMF, IMF valuta il contenuto testuale dei messaggi e assegna a ciascuno di essi un valore basato sulla probabilità che tale messaggio sia indesiderato. Questo valore, compreso tra 1 e 9, viene memorizzato come una proprietà del messaggio nota come valore del livello di probabilità di posta indesiderata (SCL) che resta associato al messaggio quando viene inviato ad altri server Exchange. Il processo completo viene illustrato nella seguente figura.

[![](images/Cc875815.AFSESE08(it-it,TechNet.10).gif "Figura 8. Processo di Filtro messaggi intelligente di Exchange")](https://technet.microsoft.com/it-it/cc875815.afsese08_big(it-it,TechNet.10).gif)

**Figura 8. Processo di Filtro messaggi intelligente di Exchange**

Dopo aver assegnato un valore SCL al messaggio con IMF, il messaggio viene valutato sulla base di due soglie configurate dall'amministratore nel modo seguente:

1.  **Configurazione blocco gateway: blocca messaggi con un valore SCL maggiore o uguale a**. Se il valore SCL di un messaggio è maggiore o uguale al valore impostato per la soglia, è possibile effettuare una delle seguenti azioni sul messaggio:

    -   Archivio

    -   Elimina

    -   Nessuna operazione

    -   Rifiuta

2.  **Configurazione archivio posta indesiderata: sposta messaggi con un valore SCL maggiore di**. Se il valore del messaggio è maggiore di quello impostato nella soglia, il messaggio viene spostato nella cartella di posta indesiderata della posta in arrivo dell'utente, a meno che l'utente non abbia inserito il mittente nell'elenco dei mittenti attendibili.

###### Anti-phishing

Il phishing è un tipo di frode ideato allo scopo di rubare l'identità di un utente. Con il phishing, gli autori della frode contattano gli utenti con falsi pretesti e cercano di convincerli a rivelare i dati personali più importanti, come il numero della carta di credito, le password, i dati relativi ad account e altre informazioni (ad esempio, utilizzando un messaggio di posta elettronica che chiede di verificare le informazioni relative all'account).

Exchange Server 2003 SP2 aggiunge una tecnologia anti-phishing a IMF in modo che i messaggi di phishing vengano assegnati e gestiti dagli SCL appropriati.

###### Valutazione personalizzata

Exchange Server 2003 SP2 fornisce anche una funzionalità di valutazione personalizzata che consente agli amministratori di personalizzare il comportamento di IMF in base alle frasi rilevate nel corpo e/o nell'oggetto di un messaggio di posta elettronica.

La funzione di valutazione personalizzata viene implementata inserendo un file XML chiamato MSExchange.UceContentFilter.xml nella stessa directory dei file MSExchange.UceContentFilter.dll e .dat nel server su cui è installato IMF. Quando il server virtuale SMTP viene avviato e IMF viene inizializzato, viene caricato il file XML.

Il file XML definisce le frasi alle quali il filtro IMF può assegnare minore o maggiore enfasi. Questa funzionalità consente di personalizzare il filtro IMF nel caso in cui occorra rispettare determinati requisiti aziendali relativi all'accettazione o al rifiuto dei messaggi sulla base di frasi alle quali, in caso contrario, sarebbe assegnato un diverso valore SCL da IMF.

In Microsoft.com, il 38% dei messaggi in ingresso che superano il filtro a livello di connessione e di protocollo vengono bloccati dal filtro IMF.

###### Posta elettronica indesiderata di Outlook 2003 e Outlook Web Access

Se un messaggio supera tutte le difese contro la posta indesiderata basate su server, il client di Outlook 2003 può agire sui messaggi a cui è assegnato un valore SCL maggiore o uguale all'impostazione di configurazione archivio posta indesiderata del filtro IMF. I messaggi che superano tale impostazione vengono inviati alla cartella di cartella di posta indesiderata della posta in arrivo di Outlook 2003.

Outlook 2003 e Outlook Web Access per Exchange Server 2003 consentono inoltre di creare un elenco di mittenti attendibili, i cui messaggi vengono sempre accettati, nonché un elenco di mittenti bloccati, i cui messaggi vengono sempre rifiutati. Nell'archivio delle cassette postali, indipendentemente dal valore SCL assegnato al messaggio, Exchange inoltra tutti i messaggi dei mittenti attendibili alla posta in arrivo dell'utente e tutti i messaggi dei mittenti bloccati alla cartella di posta indesiderata dell'utente. Tuttavia, se un messaggio di posta elettronica è stato bloccato dalla soglia del gateway, esso non viene recapitato nella posta in arrivo dell'utente poiché non è mai arrivato all'archivio delle cassette postali.

[](#mainsection)[Inizio pagina](#mainsection)

### Sfide

Il flusso di messaggi di posta elettronica commerciali indesiderati, spesso offensivi e talvolta fraudolenti, comunemente noti come posta indesiderata, sta ledendo il diritto collettivo di utilizzare la posta elettronica come canale di comunicazione e di legittimo commercio elettronico.

Per molte persone e in diverse aree geografiche, la posta indesiderata è diventata un problema di dimensioni tali da annullare la validità della posta in arrivo come efficace area di comunicazione poiché la posta attendibile si perde nell'oceano dei messaggi indesiderati. Per le medie imprese, la posta indesiderata non è altro che un costo aggiuntivo legato alla messaggistica in termini di consumo di server e reti e di utilizzo dei dischi.

La sfida delle medie imprese consiste, dunque, nel consentire lo scambio di messaggi di posta elettronica attendibili e bloccare quelli indesiderati. In altre parole, devono studiare soluzioni per proteggersi dalla posta indesiderata in un ambiente Exchange Server.

Microsoft Exchange Server 2003 con SP2 utilizza diversi metodi di filtro per la riduzione della posta indesiderata. Questi metodi rappresentano le soluzioni su più livelli per la posta indesiderata e comprendono la protezione a livello di connessione, a livello di protocollo e a livello di contenuto di cui si è parlato brevemente nel presente documento. Questi metodi sono flessibili: una volta compreso chiaramente il meccanismo su cui si basa ciascun metodo, gli amministratori e gli utenti IT possono adattare il livello di protezione contro la posta indesiderata alle proprie esigenze. Grazie a queste soluzioni, le medie imprese possono equilibrare l'accesso alla posta elettronica e il filtro della posta indesiderata.

È importante che gli amministratori e gli implementatori di Exchange comprendano il funzionamento e le modalità di integrazione di tali metodi al fine di ridurre la quantità complessiva di posta indesiderata recapitata nella posta in arrivo degli utenti. La seguente figura illustra l'approccio a più livelli per la protezione contro la posta indesiderata.

[![](images/Cc875815.AFSESE09(it-it,TechNet.10).gif "Figura 9. Exchange Server 2003 Anti-Spam Framework")](https://technet.microsoft.com/it-it/cc875815.afsese09_big(it-it,TechNet.10).gif)

**Figura 9. Exchange Server 2003 Anti-Spam Framework**

[](#mainsection)[Inizio pagina](#mainsection)

### Soluzioni

In questa sezione vengono illustrati valutazione, sviluppo, distribuzione e gestione delle soluzioni Microsoft Exchange Server 2003 Anti-Spam Framework per la protezione contro la posta indesiderata nell'ambiente delle medie imprese.

#### Valutazione

Per un'efficace difesa contro la posta indesiderata, è necessario valutare il sistema di posta elettronica complessivo di Exchange Server 2003, inclusi gli strumenti disponibili e le soluzioni per utilizzarli al meglio. Nella strategia di valutazione del rischio, è necessario condurre un'analisi accurata dell'ambiente.

Microsoft Exchange Server 2003 Anti-Spam Framework è una raccolta di metodi che comprendono i filtri connessioni, protocolli e contenuti. Comprendere il funzionamento e le possibilità di integrazione di ciascuno di questi metodi è essenziale per garantire una difesa ottimale. Inoltre, la conoscenza di queste tecnologie da parte degli utenti aumenta le possibilità di implementarle e gestirle nella maniera più corretta.

È opportuno porsi le seguenti domande:

1.  Exchange Server 2003 è installato?

    Per sfruttare i metodi forniti da Exchange Server 2003 Anti-Spam Framework, Exchange Server 20003 deve essere installato sulla piattaforma Windows appropriata.

    **Nota**   Microsoft Exchange Server 2003 può essere installato su Windows 2003 o Windows 2000 con SP3 o versione successiva. I requisiti dettagliati per l'installazione di Exchange Server non rientrano nell'ambito della presente guida. Vedere l'argomento [Installing New Exchange 2003 Servers](http://technet.microsoft.com/en-us/library/bb123643(exchg.65).aspx) (in inglese) sul sito Web Microsoft TechNet all'indirizzo http://technet.microsoft.com/en-us/library/bb123643(EXCHG.65).aspx.

2.  Exchange 2003 SP2 è applicato a Exchange Server?

    Exchange Server 2003 SP2 è un aggiornamento cumulativo che migliora l'ambiente di messaggistica Exchange Server 2003 grazie a:

    -   Miglioramenti alla posta elettronica mobile

    -   Funzionalità avanzate delle cassette postali

    -   Migliore protezione contro la posta indesiderata

    SP2 offre una protezione migliorata contro la posta indesiderata (descritta precedentemente nel presente documento) per garantire un ambiente di messaggistica protetto e affidabile. Questa protezione avanzata comprende:

    -   Filtro messaggi intelligente di Exchange aggiornato e incorporato, basato sulla tecnologia di filtro brevettata SmartScreen sviluppata da Microsoft Research.

    -   Nuovo supporto per il protocollo di autenticazione per la posta elettronica ID mittente che impedisce schemi di phishing e spoofing.

3.  Server virtuale SMTP predefinito è attivato in Gestore di sistema di Exchange?

    Il filtro destinatari, il filtro intelligente, il filtro ID mittente e il filtro connessioni sono configurati nelle impostazioni globali e devono essere attivati anche a livello SMTP. Pertanto, SMTP deve essere attivato prima di apportare le modifiche a tali servizi.

4.  Nelle workstation client è installato Outlook 2003?

    I server possono essere configurati con tutti i requisiti necessari, ma se nei client sono installate versioni obsolete di Outlook, non sarà possibile sfruttare i vantaggi dei metodi offerti da Microsoft Exchange Server 2003 Anti-Spam Framework.

    Se vengono rispettati tutti i requisiti per Exchange Server 2003 e i relativi client, è possibile utilizzare i seguenti metodi:

    -   Protezione a livello di connessione

        Filtro connessioni IP

        Elenchi di blocco in tempo reale

    -   Protezione a livello di protocollo

        Blocco mittenti e destinatari

        ID mittente

    -   Protezione a livello di contenuto

        Filtro messaggi intelligente di Exchange

        Posta elettronica indesiderata di Outlook 2003 e Outlook Web Access

#### Sviluppo

La sezione relativa alla valutazione ha sollevato alcune domande e fornito risposte su Exchange Server 2003 e i requisiti relativi ai client che consentono di trarre vantaggio da Microsoft Exchange Server 2003 Anti-Spam Framework.

Le soluzioni per proteggere l'ambiente Exchange dalla posta indesiderata comprendono anche la protezione dei client e la formazione degli utenti. Tutti questi approcci devono essere utilizzati per eliminare la posta indesiderata dall'ambiente Exchange.

I metodi di protezione contro la posta indesiderata forniti da Microsoft Exchange Server 2003 Anti-Spam Framework possono essere implementati immediatamente se sono soddisfatti i seguenti requisiti:

-   Exchange Server 2003 è stato installato sulle piattaforme Windows appropriate.

-   Outlook 2003 e Outlook Web Access sono installati e configurati.

-   Tutte le patch e gli aggiornamenti più recenti consigliati sono stati applicati, incluso Service Pack 2.

Una migliore comprensione del funzionamento di ciascun metodo e delle possibili integrazioni consente un'implementazione più efficace. In questa sezione verrà completata la descrizione avviata in precedenza relativa ai metodi necessari per la distribuzione e la gestione.

##### Protezione a livello di connessione

Exchange Server 2003 SP2 include il filtro connessioni che confronta l'indirizzo IP del server di connessione con un elenco di indirizzi IP rifiutati (anche noto come elenco di indirizzi bloccati in tempo reale). Il confronto degli indirizzi IP viene eseguito subito dopo l'avvio della sessione SMTP, consentendo alla media impresa di bloccare le connessioni ai gateway durante le prime fasi di inoltro del messaggio. Prima che un server nell'elenco di indirizzi bloccati in tempo reale sia in grado di inoltrare i messaggi, la connessione viene interrotta. Questo approccio ottimizza le prestazioni a livello di messaggistica e di rete.

Le medie imprese possono definire un filtro connessioni in Exchange Server 2003 SP2 creando manualmente un elenco globale connessioni accettate e un elenco globale connessioni rifiutate oppure utilizzando database gestiti da terze parti di indirizzi IP noti bloccati.

La maggior parte dei server Exchange Server 2003 SP2 vengono distribuiti oltre il perimetro dell'organizzazione e non sono a diretto contatto con Internet. Questa posizione rende meno utile il filtro connessioni poiché questa funzionalità si basa sull'individuazione dell'indirizzo IP del mittente originale per inoltrare la query DNS. Il rilascio di SP2 ha risolto questo problema introducendo un nuovo algoritmo di analisi delle intestazioni che consente il recupero dell'indirizzo IP Exchange Server 2003 SP2 con il filtro connessioni distribuito può essere posizionato ovunque all'interno dell'organizzazione e il filtraggio può essere eseguito allo stesso modo che sul perimetro.

###### Filtro connessioni IP

Una media impresa può creare un proprio elenco statico di indirizzi IP rifiutati. Come indicato anche dal nome, l'elenco globale connessioni rifiutate contiene gli indirizzi IP e le reti da cui i messaggi di posta elettronica non vengono mai accettati. Viceversa, una media impresa può creare un elenco globale connessioni accettate, ossia un elenco di indirizzi IP e di reti a cui l'organizzazione non applica criteri di blocco o di filtro della posta elettronica. L'elenco globale connessioni accettate può comprendere gli indirizzi IP corrispondenti a filiali o partner commerciali con cui la media impresa intrattiene relazioni ritenute affidabili. In queste circostanze, per non rischiare la presenza di falsi positivi, l'azienda può aggiungere gli indirizzi IP attendibili dei server di posta del mittente all'elenco globale connessioni accettate.

###### Elenchi di blocco in tempo reale

Un elenco di indirizzi bloccati in tempo reale è un database basato su DNS di indirizzi IP di fonti note e verificate di posta indesiderata. Gli elenchi di indirizzi bloccati in tempo reale vengono forniti da società che si occupano del costante monitoraggio di Internet e del rilevamento delle fonti note di posta indesiderata. Quando vengono rilevati, gli indirizzi IP infetti vengono aggiunti a un database dell'elenco di indirizzi bloccati in tempo reale. Tali elenchi sono spesso forniti gratuitamente oppure a pagamento nel caso in cui l'amministratore di messaggistica richieda servizi estesi.

Exchange Server 2003 SP2 consente l'utilizzo di elenchi di indirizzi bloccati in tempo reale di terze parti. Quando è configurato per l'utilizzo di un elenco di indirizzi bloccati in tempo reale di terze parti, il server Exchange Server 2003 SP2 confronta l'indirizzo IP del server di invio con il database dell'elenco di indirizzi bloccati in tempo reale e rifiuta la connessione se rileva una corrispondenza.

Poiché la funzionalità dell'elenco di indirizzi bloccati in tempo reale basa le decisioni di filtro sull'indirizzo IP del server di invio piuttosto che sul contenuto del messaggio, gli elenchi di indirizzi bloccati in tempo reale vengono inclusi tecnicamente in una categoria separata di software per la posta indesiderata di terze parti. L'elenco di indirizzi bloccati in tempo reale funziona come un custode, impedendo ai messaggi provenienti da server notoriamente dannosi o sospetti di entrare nell'ambiente dell'organizzazione. Un messaggio che supera la difesa dell'elenco di indirizzi bloccati in tempo reale si avvicina alla rete, tuttavia deve ancora superare la verifica del contenuto eseguita al successivo livello di protezione dalla posta indesiderata, ad esempio il filtro messaggio intelligente.

A causa del volume delle query DNS associate all'elenco di indirizzi bloccati in tempo reale inoltrate da Microsoft IT su base quotidiana (decine di milioni), Microsoft IT trasferisce una copia mirror dell'elenco di indirizzi bloccati in tempo reale ai server DNS locali a intervalli predeterminati e regolari (solitamente, più volte al giorno). Molti provider di elenchi richiedono copie locali degli elenchi di indirizzi bloccati in tempo reale per volumi di query superiori a 250.000 al giorno. Il trasferimento di una copia dell'elenco di indirizzi bloccati in tempo reale è noto come trasferimento di zona dal provider dell'elenco. Microsoft IT ha configurato i gateway Exchange Server 2003 SP2 per inoltrare query DNS basate sull'elenco di indirizzi bloccati in tempo reale confrontandole con i server DNS locali specificati.

##### Protezione a livello di protocollo

Una volta che il messaggio SMTP supera la protezione a livello di connessione, la fase successiva di difesa è a livello del protocollo SMTP. Il dialogo SMTP tra l'host di invio SMTP e l'host di ricezione SMTP viene analizzato per verificare le autorizzazioni di mittente e destinatari e determinare il nome del dominio SMTP del mittente.

###### Blocco mittenti e destinatari

La funzionalità filtro destinatari di Exchange Server 2003 SP2 consente alle medie imprese di proteggersi o ridurre l'impatto del bombardamento mirato di posta. Spesso, i destinatari di questo tipo di attacchi non hanno necessità di ricevere alcun messaggio da Internet. Il filtro destinatari rifiuta i messaggi a livello del gateway basati su criteri quali il destinatario del messaggio.

Sebbene non sia uno strumento di difesa efficace quanto le soluzioni contro la posta indesiderata in tempo reale, il filtro destinatari può essere molto utile per ridurre il rischio di attacchi di bombardamento di posta. Di recente, l'uso del filtro destinatari ha consentito a Microsoft IT di bloccare milioni di messaggi indirizzati a pochi destinatari in un solo giorno.

###### ID mittente

La struttura ID mittente è un protocollo di tecnologie di autenticazione per la posta elettronica che consente di risolvere i problemi legati a spoofing e phishing verificando il nome di dominio da cui proviene il messaggio. L'ID mittente convalida l'origine del messaggio di posta elettronica verificando l'indirizzo IP del mittente sulla base del presunto proprietario del dominio di invio.

L'ID mittente cerca di verificare che ciascun messaggio di posta elettronica provenga dal dominio Internet specificato per l'invio. Questa verifica viene eseguita controllando l'indirizzo del server di invio del messaggio di posta elettronica rispetto a un elenco registrato di server che il proprietario del dominio ha autorizzato per l'invio di posta elettronica. Questa verifica viene eseguita automaticamente dal provider di servizi Internet (ISP) o dal server di posta del destinatario prima che il messaggio venga recapitato all'utente. Il risultato del controllo dell'ID mittente può essere utilizzato come input aggiuntivo alle attività di filtro già eseguite dal server di posta. Una volta autenticato il mittente, il server di posta può considerare i comportamenti passati, i modelli di traffico e la reputazione del mittente, nonché applicare filtri contenuto convenzionali per decidere se recapitare la posta al destinatario.

##### Protezione a livello di contenuto

Idealmente, la posta indesiderata non dovrebbe mai raggiungere il livello del client, ma in realtà qualche messaggio riesce ad arrivare fino ai computer desktop degli utenti. Una delle ragioni principali è che alcuni messaggi di posta elettronica attendibili, ad esempio le newsletter, condividono spesso le caratteristiche della posta indesiderata, pertanto non è opportuno impostare la soglia di filtro a un livello tanto basso da eliminare tutti i messaggi sospetti. Inoltre, gli utenti potrebbero avere preferenze individuali che non rientrano nelle impostazioni standardizzate dell'azienda.

###### Filtro messaggi intelligente di Exchange

Il filtro attraverso cui la posta elettronica in ingresso proveniente da Internet deve passare inizialmente è il Filtro messaggi intelligente, in esecuzione sui server gateway Exchange Server 2003 SP2 posizionati al margine più estremo dell'ambiente di messaggistica. Il filtro messaggi intelligente utilizza SCL, PCL (punteggio del livello di probabilità di phishing, uno dei fattori che attivano le assegnazioni SCL finali) e la struttura ID mittente incorporata in Exchange Server 2003 SP2. Il filtro messaggio Internet classifica alcune parti dei messaggi, esegue l'analisi dei messaggi su base euristica e assegna un valore SCL da 0 a 9 a ciascun messaggio analizzato. Più alto è il valore assegnato al messaggio, maggiore è la probabilità che si tratti di posta indesiderata.

Exchange Server 2003 SP2 incorpora i dati e gli aggiornamenti più recenti nel filtro messaggi intelligente. I miglioramenti al filtro IMF e gli aggiornamenti bisettimanali assicurano un elevato grado di attenzione verso l'identificazione della posta indesiderata e la riduzione dei falsi positivi. Questi miglioramenti comprendono nuove capacità nella difesa contro la posta indesiderata, tra cui il blocco delle frodi tramite phishing. Le frodi tramite phishing tentano con l'inganno di indurre gli utenti a fornire informazioni riservate spacciando le richieste come provenienti da siti Web attendibili.

L'ambiente Exchange Server 2003 SP2 può essere configurato per eseguire azioni di filtro su messaggi con valori SCL maggiori delle soglie configurate dagli amministratori. Il filtro messaggi intelligente utilizza due soglie impostate in Exchange Server 2003 SP2: la soglia del gateway e la soglia di memorizzazione.

###### Posta elettronica indesiderata di Outlook 2003 e Outlook Web Access

-   **Filtro posta indesiderata**. Outlook 2003 utilizza tecnologia all'avanguardia sviluppata da Microsoft Research per stabilire se un messaggio debba essere considerato come posta indesiderata sulla base di diversi fattori, ad esempio l'orario di invio, il contenuto e la struttura del messaggio. Il filtro non individua mittenti o tipi di messaggi di posta elettronica particolari, ma utilizza l'analisi avanzata per determinare la probabilità che il destinatario possa considerare il messaggio come posta indesiderata.

    Per impostazione predefinita, questo filtro è impostato su valori bassi al fine di intercettare i messaggi di posta elettronica palesemente indesiderati. I messaggi individuati dal filtro vengono spostati in una speciale cartella di posta indesiderata a cui è possibile accedere in un secondo momento. Se si desidera, è possibile impostare questo filtro in maniera più restrittiva (rischiando però di intercettare erroneamente un maggior numero di messaggi attendibili) o persino impostare Outlook 2003 in modo che elimini in modo definitivo i messaggi di posta elettronica appena vengono ricevuti. Ulteriori informazioni sul filtro posta indesiderata.

-   **Elenco Mittenti attendibili**. Se un messaggio di posta elettronica viene erroneamente contrassegnato come posta indesiderata dal filtro, è possibile aggiungere facilmente il mittente del messaggio all'elenco Mittenti attendibili. Gli indirizzi di posta elettronica e i nomi di dominio presenti in tale elenco non vengono mai gestiti come posta indesiderata, indipendentemente dal contenuto del messaggio. I contatti sono ritenuti attendibili per impostazione predefinita e i messaggi che provengono da questi mittenti non vengono mai considerati come posta indesiderata. Se l'azienda utilizza Microsoft Exchange Server, anche i messaggi interni all'organizzazione non vengono mai inclusi nella posta indesiderata. È possibile configurare Outlook 2003 in modo che accetti solo i messaggi dell'elenco Mittenti attendibili, consentendo all'utente di avere il totale controllo sui messaggi ricevuti.

-   **Elenco mittenti bloccati**. I messaggi di posta elettronica provenienti da alcuni indirizzi di posta elettronica o da nomi di domini possono essere facilmente bloccati aggiungendo i mittenti all'elenco mittenti bloccati. I messaggi provenienti da persone e nomi di dominio presenti in tale elenco verranno sempre considerati come posta indesiderata, indipendentemente dal contenuto del messaggio.

-   **Elenco Destinatari attendibili**. Se l'utente è membro di un elenco o di un gruppo di posta elettronica, può aggiungerlo all'elenco Destinatari attendibili. Tutti i messaggi inviati agli indirizzi di posta elettronica o ai nomi di dominio presenti in questo elenco non vengono considerati come posta indesiderata, indipendentemente dal mittente o dal contenuto del messaggio.

-   **Aggiornamento automatico**. È possibile aggiornare periodicamente il filtro posta indesiderata sul sito Web Microsoft per disporre sempre dei metodi più recenti per bloccare i messaggi di posta indesiderata. Microsoft si impegna a fornire aggiornamenti periodici per il filtro posta indesiderata.

#### Distribuzione e gestione

La capacità di comprendere in che modo ciascuno dei metodi inclusi in questa struttura funzioni e le modalità di integrazione dei diversi metodi rappresenta l'obiettivo principale di Microsoft Exchange Server 2003 Anti-Spam Framework. Una volta compreso l'ambito della struttura, la corretta distribuzione e gestione di queste tecnologie consentirà alle medie imprese di proteggersi in modo efficace dalla posta indesiderata negli ambienti Microsoft Exchange Server. Per poter contribuire a tale protezione, gli utenti devono disporre delle nozioni fondamentali sull'argomento per poter gestire i computer client nei propri ambienti. Inoltre, come componenti della gestione continuativa, verranno discussi anche il monitoraggio e la risoluzione dei problemi relativi al filtro messaggi intelligente.

Le seguenti funzionalità devono essere configurate sia a livello delle impostazioni globali che a livello dell'SMTP. Il tema della consapevolezza degli utenti verrà discusso alla fine di questa sezione.

In questa sezione vengono illustrate le procedure dettagliate per:

-   Protezione a livello di connessione

    -   Filtro connessioni IP

    -   Elenchi di blocco in tempo reale

-   Protezione a livello di protocollo

    -   Blocco mittenti e destinatari

    -   ID mittente

-   Protezione a livello di contenuto

    -   Filtro messaggi intelligente di Exchange

    -   Posta elettronica indesiderata di Outlook 2003 e Outlook Web Access

##### Protezione a livello di connessione

Exchange Server 2003 supporta il *filtro connessioni* in base agli elenchi di indirizzi bloccati in tempo reale. Questa funzionalità consente di controllare un indirizzo IP in ingresso confrontandolo con un provider di elenchi di indirizzi bloccati in tempo reale (RBL) per le categorie che si desidera filtrare. Se si rileva una corrispondenza nell'elenco del provider RBL, il protocollo SMTP invia un errore *550 5.x.x* in risposta al comando *RCPT TO* e viene inviata una risposta personalizzata di errore al mittente. È possibile utilizzare diversi filtri connessione e stabilire l'ordine di priorità in base al quale applicarli.

Quando si crea un filtro connessioni, viene stabilita una regola utilizzata da SMTP per eseguire una ricerca DNS sull'elenco fornito da un servizio RBL di terze parti. Il filtro connessioni cerca le corrispondenze di ciascun indirizzo IP in ingresso con l'elenco di indirizzi bloccati fornito da terze parti. Il provider RBL invia una delle seguenti risposte:

-   **Impossibile trovare l'host**. Questa risposta indica che l'indirizzo IP non è presente nell'elenco di indirizzi bloccati specificato.

-   **127.0.0.x**. Questa risposta è un codice stato risposta e indica che è stata rilevata una corrispondenza per l'indirizzo IP nell'elenco di indirizzi bloccati. La x varia a seconda del provider utilizzato.

Se l'indirizzo IP in ingresso viene individuato nell'elenco, il protocollo SMTP restituisce un errore *5.x.x* in risposta al comando *RCPT TO* (il comando SMTP inviato dal server di connessione per identificare il destinatario del messaggio).

###### Provider di elenchi di indirizzi bloccati in tempo reale

Poiché i vari provider di elenchi di indirizzi bloccati in tempo reale offrono diversi tipi di elenchi e servizi, le medie imprese devono valutare attentamente le possibili soluzioni prima di scegliere un provider. Due tra i più noti provider sono [Spam Haus](http://www.spamhaus.org/) all'indirizzo www.spamhaus.org e [Spam Cop](http://www.spamcop.net/) all'indirizzo www.spamcop.net.

Le risposte alle seguenti domande possono facilitare una scelta più consapevole del provider RBL:

-   **Qualità dell'elenco**. È previsto qualcuno che controlli che i nuovi indirizzi IP aggiunti all'elenco siano effettivamente mittenti di posta indesiderata? Le aggiunte all'elenco possono essere apportate da chiunque?

-   **Protezione dell'elenco**. Sono previsti controlli di protezione dell'elenco? È previsto qualcuno che controlli che gli indirizzi IP nell'elenco non siano stati aggiunti per errore o per scopi illeciti?

-   **Processo di aggiornamento dell'elenco**. Che cos'è il processo di verifica? Se l'aggiunta all'elenco è un processo automatico, è opportuno che anche la rimozione venga automatizzata una volta che la ricezione di posta indesiderata si interrompe. Con quale frequenza vengono aggiornati gli elenchi?

-   **Processo di trasferimento dell'elenco**. Il provider consente trasferimenti completi o incrementali di tipo BIND (Berkeley Internet Name Domain) direttamente compatibili con il sistema DNS di Windows?

-   **Supporto dal provider degli elenchi di indirizzi bloccati**. Quale livello di supporto viene offerto dal provider?

###### Filtro connessioni IP

**Per configurare il filtro connessioni IP**

1.  Da Gestore di sistema di Exchange, espandere il contenitore **Impostazioni globali**.

2.  Fare clic con il pulsante destro del mouse su **Recapito messaggi**, quindi scegliere **Proprietà**.

3.  Scegliere la scheda **Filtro connessioni**.

4.  Scegliere tra **Accetta**, **Nega** o **Eccezione**. Nel seguente esempio, viene selezionato Nega.

5.  È possibile selezionare un **Indirizzo IP singolo** o un **Gruppo di indirizzi IP**, come illustrato nella seguente schermata.

    [![](images/Cc875815.AFSESE10(it-it,TechNet.10).gif "AFSESE10.GIF")](https://technet.microsoft.com/it-it/cc875815.afsese10_big(it-it,TechNet.10).gif)

###### Elenco indirizzi bloccati in tempo reale (RBL)

**Per configurare la funzionalità di elenco di indirizzi bloccati in tempo reale a livello delle Impostazioni globali**

1.  Da Gestore di sistema di Exchange, espandere il contenitore **Impostazioni globali**.

2.  Fare clic con il pulsante destro del mouse sull'oggetto **Recapito messaggi**, quindi selezionare **Proprietà**.

3.  Scegliere la scheda **Filtro connessioni**.

4.  Per creare una regola filtro connessione, scegliere **Aggiungi** (come mostrato nella seguente schermata).

    [![](images/Cc875815.AFSESE11(it-it,TechNet.10).gif "AFSESE11.GIF")](https://technet.microsoft.com/it-it/cc875815.afsese11_big(it-it,TechNet.10).gif)

5.  Nel campo **Nome visualizzato**, immettere un nome per il filtro connessioni.

6.  In **Suffisso DNS del provider**, immettere il suffisso DNS del provider (ad esempio, contoso.com).

7.  In **Messaggio di errore personalizzato da restituire**, è possibile immettere, facoltativamente, un messaggio di errore personalizzato da restituire al mittente. Se il campo viene lasciato vuoto, verrà utilizzato un messaggio di errore predefinito:

    *&lt;Indirizzo IP&gt;* è stato bloccato da *&lt;Nome regola filtro connessione&gt;*

    È possibile generare un messaggio personalizzato utilizzando le seguenti variabili:

    -   **%0**. Indirizzo IP di connessione

    -   **%1**. Nome regola del filtro connessioni

    -   **%2**. Provider RBL

    Ad esempio, se si desidera che il messaggio venga visualizzato in questo modo:

    L'indirizzo IP *&lt;indirizzo IP&gt;* è stato bloccato dal seguente provider RBL *&lt;nome provider RBL&gt;*.

    immettere il seguente testo nel campo **Messaggio di errore personalizzato da restituire**:

    L'indirizzo IP %0 è stato rifiutato dal provider RBL %2.

    **Nota**   Exchange sostituisce %0 con l'indirizzo IP di connessione e %2 con il provider RBL.

8.  Per configurare i codici di stato restituiti dal provider RBL da associare al filtro connessioni specificato, scegliere **Codice di stato restituito**. Viene visualizzata la seguente finestra di dialogo.

    ![](images/Cc875815.AFSESE12(it-it,TechNet.10).gif "AFSESE12.GIF")

9.  Selezionare una delle seguenti opzioni nella finestra di dialogo **Codice di stato restituito**:

    -   **Corrispondenza regola filtro con qualsiasi codice restituito**. La regola filtro connessione corrisponde a qualsiasi codice di stato restituito, ricevuto dal servizio provider. Questa regola imposta il valore predefinito che corrisponde al filtro connessioni in qualsiasi stato restituito.

        Esempi:

        **127.0.0.1**. Elenco blocco

        **127.0.0.2**. Inoltro aperto noto

        **127.0.0.4**. Indirizzo IP remoto

    <!-- -->

    -   **Corrispondenza regola filtro con la seguente maschera**. La regola filtro connessione corrisponde ai codici di stato restituiti, ricevuti dal servizio provider e interpretati da una maschera. Immettere la maschera per il filtraggio sulla base delle maschere utilizzate dai provider.

        Esempi:

        **0000 | 0001**. Elenco blocco

        **0000 | 0010**. Inoltro aperto

        **0000 | 0011**. Inoltro aperto o elenco blocco

        **0000 | 0100**. Host remoto

        **0000 | 0101**. Remoto o elenco blocco

        **0000 | 0110**. Remoto o inoltro aperto

        **0000 | 0111**. Remoto, inoltro aperto o elenco blocco

    <!-- -->

    -   **Corrispondenza regola filtro con qualsiasi delle seguenti risposte**. La regola filtro connessione corrisponde ai codici di stato restituiti, ricevuti dal servizio provider tramite i valori specifici dei seguenti codici di stato restituiti.

10. Fare clic su **OK**.

Anche le funzionalità Mittente, Destinatario, Filtro messaggi intelligente e Filtro connessioni devono essere applicate a livello SMTP per un corretto funzionamento. Per applicarle, completare la seguente procedura.

**Per attivare le funzionalità di filtro a livello SMTP**

1.  Avviare Gestore di sistema di Exchange.

2.  Espandere **Server**.

3.  Espandere ***&lt;nome server&gt;*** (server di posta da configurare).

4.  Espandere **Protocolli**.

5.  Espandere **SMTP**.

6.  Fare clic con il pulsante destro del mouse su **Server virtuale SMTP predefinito** e scegliere **Proprietà**.

7.  Nelle proprietà di **Server virtuale SMTP predefinito**, scegliere **Avanzate**.

8.  In **Avanzate**, scegliere **Modifica**.

9.  In **Identità**, selezionare la casella di controllo **Applica filtro di connessione** per applicare il filtro impostato precedentemente (come mostrato nella seguente schermata).

    [![](images/Cc875815.AFSESE13(it-it,TechNet.10).gif "AFSESE13.GIF")](https://technet.microsoft.com/it-it/cc875815.afsese13_big(it-it,TechNet.10).gif)

#### Protezione a livello di protocollo

Una volta che il messaggio SMTP supera la protezione a livello di connessione, la fase successiva di difesa è a livello del protocollo SMTP. Il dialogo SMTP tra l'host di invio SMTP e l'host di ricezione SMTP viene analizzato per verificare le autorizzazioni di mittente e destinatari e determinare il nome del dominio SMTP del mittente.

##### Filtro destinatari

Utilizzare la funzionalità Filtro destinatari per impedire l'invio di messaggi inviati a particolari indirizzi di destinatari.

**Per configurare il filtro destinatari**

1.  Avviare Gestore di sistema di Exchange.

2.  Espandere il contenitore **Impostazioni globali**.

3.  Fare clic con il pulsante destro del mouse su **Recapito messaggi**, quindi scegliere **Proprietà**.

4.  Scegliere la scheda **Filtro destinatari**.

5.  Selezionare **Filtra destinatari non presenti nella directory**.

6.  Scegliere **Aggiungi**, quindi aggiungere l'indirizzo del destinatario (come mostrato nella seguente schermata).

    [![](images/Cc875815.AFSESE14(it-it,TechNet.10).gif "AFSESE14.GIF")](https://technet.microsoft.com/it-it/cc875815.afsese14_big(it-it,TechNet.10).gif)

##### Filtro ID mittente

Utilizzare le opzioni del filtro ID mittente per configurare le azioni dell'ID mittente. Quando si utilizzano queste opzioni, è possibile specificare in che modo il server deve gestire i messaggi che hanno prodotto errori durante la convalida dell'ID mittente. La funzionalità ID mittente è uno standard del settore che è possibile usare per fornire una maggiore protezione contro la posta commerciale indesiderata e gli schemi di phishing.

Per impostazione predefinita, il filtro ID mittente è impostato su **Accetta**. Tuttavia, è possibile attivare il filtro ID mittente oltre il perimetro della rete. A tale scopo, specificare gli indirizzi IP nella rete interna da escludere dal filtro ID mittente.

**Per configurare il filtro ID mittente**

1.  Avviare Gestore di sistema di Exchange.

2.  Espandere il contenitore **Impostazioni globali**.

3.  Fare clic con il pulsante destro del mouse su **Recapito messaggi**, quindi scegliere **Proprietà**.

4.  Scegliere la scheda **Filtro ID mittente**.

5.  Selezionare le opzioni desiderate del filtro ID mittente (come mostrato nella seguente schermata).

    ![](images/Cc875815.AFSESE15(it-it,TechNet.10).gif "AFSESE15.GIF")

#### Protezione a livello di contenuto

Il filtro contenuti in Exchange Server 2003 SP2 si basa sulla tecnologia SmartScreen di apprendimento automatico sviluppata da Microsoft Research, incorporata nel filtro messaggi intelligente (IMF). I messaggi provenienti da Internet arrivano al gateway SMTP di Exchange, quindi giungono in Exchange Server Anti-Spam Framework. I livelli precedenti della soluzione Exchange per la protezione contro la posta indesiderata (filtro connessioni, filtro mittente e filtro destinatari) consentono di bloccare l'invio dei messaggi prima dell'effettiva ricezione dei dati del messaggio. Se un messaggio supera tutti i filtri descritti, il corpo del messaggio arriva a destinazione.

Il filtro IMF è in grado di valutare con precisione quale sia la probabilità che un messaggio di posta elettronica in ingresso sia attendibile o indesiderato.

##### Filtro messaggi intelligente di Exchange

Il filtro messaggi intelligente di Exchange è un componente molto importante per la difesa contro la posta indesiderata e si basa su un filtro compatibile per SCL che fornisce capacità di filtro dei messaggi avanzate sul lato server progettate specificamente per arginare l'impatto della posta indesiderata. Per informazioni specifiche, vedere il sito Web [Exchange Intelligent Message Filter](http://go.microsoft.com/fwlink/?linkid=21607) all'indirizzo http://go.microsoft.com/fwlink/?linkid=21607.

**Per configurare il filtro messaggi intelligente di Exchange**

1.  Avviare Gestore di sistema di Exchange.

2.  Espandere il contenitore **Impostazioni globali**.

3.  Fare clic con il pulsante destro del mouse su **Recapito messaggi**, quindi scegliere **Proprietà**.

4.  Scegliere la scheda **Filtro messaggi intelligente**.

5.  In **Bloccare i messaggi con un livello di sicurezza della protezione contro la posta indesiderata maggiore o uguale a** (mostrato nella seguente schermata), selezionare il livello desiderato.

    La scala di valori SCL va da 0 a 9. Più alto è il valore, maggiore è la probabilità si tratti di un messaggio di posta indesiderata.

    [![](images/Cc875815.AFSESE16(it-it,TechNet.10).gif "AFSESE16.GIF")](https://technet.microsoft.com/it-it/cc875815.afsese16_big(it-it,TechNet.10).gif)

##### Posta elettronica indesiderata di Outlook 2003 e Outlook Web Access

Sia Outlook 2003 che Outlook Web Access 2003 includono funzionalità che consentono di proteggere gli utenti dalla posta indesiderata. Tali funzionalità includono:

-   **Elenchi di indirizzi bloccati e di mittenti attendibili gestiti dall'utente**. Gli elenchi di indirizzi bloccati e di mittenti attendibili utilizzati da Outlook 2003 e Outlook Web Access sono memorizzati nella cassetta postale dell'utente. Poiché entrambi i programmi utilizzano lo stesso elenco, non è necessario conservare entrambe le versioni.

-   **Blocco del contenuto esterno**. Outlook 2003 e Outlook Web Access 2003 ostacolano l'utilizzo dei beacon da parte dei mittenti di messaggi di posta indesiderata al fine di recuperare indirizzi di posta elettronica. I messaggi in ingresso che includono contenuti che potrebbero essere utilizzati come beacon attivano la visualizzazione di un messaggio di avviso in Outlook e Outlook Web Access, indipendentemente dall'effettiva presenza del beacon. Se gli utenti ritengono attendibile il messaggio, possono fare clic sul messaggio di avviso per scaricare il contenuto. In caso contrario, si consiglia di eliminare il messaggio senza attivare beacon che potrebbero avvisare un mittente di posta indesiderata.

-   **Gestione migliorata della posta indesiderata**. Con Outlook 2003, è possibile creare regole per la ricerca di frasi specifiche nei messaggi di posta elettronica e per lo spostamento automatico dei messaggi contenenti tali frasi dalla posta in arrivo a una cartella specificata (ad esempio la cartella di posta indesiderata o di posta eliminata). Gli utenti possono anche eliminare in modo definitivo la posta indesiderata sospetta invece di spostarla in una cartella specificata.

-   **Filtro posta indesiderata**. Outlook 2003 include un filtro posta indesiderata che ricerca gli attributi comuni di posta indesiderata. L'aggiornamento di tali attributi avviene simultaneamente a quello di Office. Per ciascun attributo sospetto, Outlook incrementa il valore di un contatore. Maggiore è il numero del contatore per un determinato messaggio di posta, più è alta la probabilità che si tratti di posta indesiderata. Configurare il livello di protezione contro la posta indesiderata nella finestra di dialogo **Opzioni posta indesiderata**.

**Per configurare il filtro posta indesiderata di Outlook 2003**

1.  In Outlook 2003, fare clic su **Azione** nella barra dei menu.

2.  Selezionare **Posta indesiderata**, quindi **Opzioni posta indesiderata** (come mostrato nella seguente schermata).

    [![](images/Cc875815.AFSESE17(it-it,TechNet.10).gif "AFSESE17.GIF")](https://technet.microsoft.com/it-it/cc875815.afsese17_big(it-it,TechNet.10).gif)

3.  Viene visualizzata la finestra di dialogo mostrata nella seguente schermata che consente agli utenti di scegliere il livello desiderato di protezione contro la posta indesiderata.

    [![](images/Cc875815.AFSESE18(it-it,TechNet.10).gif "AFSESE18.GIF")](https://technet.microsoft.com/it-it/cc875815.afsese18_big(it-it,TechNet.10).gif)

**Per configurare il filtro posta indesiderata in Outlook Web Access (OWA)**

1.  Accedere all'account di Outlook Web Access.

2.  Fare clic su **Opzioni**.

3.  Scegliere **Gestione elenchi Posta indesiderata**.

4.  Selezionare la funzionalità appropriata da **Visualizza o modifica elenco** (come mostrato nella seguente schermata).

    [![](images/Cc875815.AFSESE19(it-it,TechNet.10).gif "AFSESE19.GIF")](https://technet.microsoft.com/it-it/cc875815.afsese19_big(it-it,TechNet.10).gif)

5.  **Aggiungi**, **Modifica** o **Rimuovi** gli indirizzi di posta elettronica del mittente.

**Nota**   Quando gli utenti iniziano a utilizzare queste funzionalità per la posta indesiderata o se apportano modifiche alle opzioni, è necessario verificare su base periodica i messaggi rimossi dalla posta in arrivo per assicurarsi che non siano stati spostati messaggi attendibili. Gli aggiornamenti per le funzionalità di posta indesiderata in Outlook 2003 vengono elencati nella sezione **Office Update** del sito Web [Microsoft Office Online](http://go.microsoft.com/fwlink/?linkid=24393) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=24393.

#### Monitoraggio e risoluzione dei problemi relativi al filtro messaggi intelligente

Le attività di monitoraggio e risoluzione dei problemi con il filtro messaggi intelligente di Microsoft Exchange possono essere eseguite tramite il Visualizzatore eventi e il Monitor di sistema. In questa sezione vengono fornite informazioni dettagliate su come eseguire il monitoraggio e la risoluzione dei problemi.

##### Uso del Visualizzatore eventi

Nel Visualizzatore eventi, il Registro applicazioni e il Registro eventi sistema contengono errori, avvisi ed eventi informativi relativi al funzionamento di Exchange, del servizio SMTP e di altre applicazioni. Per identificare la causa dei problemi legati al filtro messaggi intelligente, esaminare attentamente i dati contenuti nel Registro applicazioni e nel Registro eventi sistema. Il filtro messaggi intelligente scrive gli eventi nel Visualizzatore eventi mediante l'origine MSExchangeTransport e la categoria protocollo SMTP.

**Per trovare gli eventi legati al filtro messaggi intelligente tramite il Visualizzatore eventi**

1.  Fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Strumenti di amministrazione** e fare clic su **Visualizzatore eventi**.

2.  Nella struttura della console, fare clic su **Registro applicazioni**.

3.  Per visualizzare il registro in ordine alfabetico e individuare rapidamente una voce per un servizio Exchange, scegliere **Origine** nel riquadro dei dettagli (come mostrato nella seguente schermata).

    [![](images/Cc875815.AFSESE20(it-it,TechNet.10).gif "AFSESE20.GIF")](https://technet.microsoft.com/it-it/cc875815.afsese20_big(it-it,TechNet.10).gif)

4.  Per filtrare il registro al fine di elencare le voci di eventi registrati per il filtro messaggi intelligente, scegliere **Filtra** nel menu **Visualizza**.

5.  In **Proprietà - Registro applicazioni**, utilizzare l'elenco origine **Evento** per selezionare **MSExchangeTransport**.

6.  Nell'elenco **Categoria**, selezionare **Protocollo SMTP**.

##### Uso di Monitor di sistema e di Avvisi e registri di prestazioni

Il filtro messaggi intelligente ha diversi contatori delle prestazioni che possono essere utilizzati per monitorarne le prestazioni e il funzionamento.

**Per utilizzare Monitor di sistema e Avvisi e registri di prestazioni**

1.  Fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Strumenti di amministrazione** e fare clic su **Prestazioni**.

2.  Evidenziare **Monitor di sistema**, quindi fare clic sul pulsante **+** per aggiungere i contatori.

3.  Nella finestra di dialogo **Aggiungi contatori**, in **Oggetto prestazioni**, selezionare **Filtro messaggi intelligente di Microsoft Exchange** (come mostrato nella seguente schermata).

    [![](images/Cc875815.AFSESE21(it-it,TechNet.10).gif "AFSESE21.GIF")](https://technet.microsoft.com/it-it/cc875815.afsese21_big(it-it,TechNet.10).gif)

#### Consapevolezza degli utenti

Come per qualsiasi altra cosa, ad esempio la battaglia contro i virus, la protezione delle workstation da utenti non autorizzati o il blocco della posta indesiderata, la sola tecnologia non basta a difendere i sistemi da rischi e attacchi. Con un'adeguata formazione, gli utenti possono svolgere un ruolo significativo nella gestione della posta indesiderata. Agli utenti devono essere fornite istruzioni su come evitare o filtrare i messaggi indesiderati nel proprio ambiente Outlook,

ad esempio:  

-   Non rispondere mai alle richieste di informazioni finanziarie o personali inviate per posta elettronica.

-   Non fornire mai la propria password.

-   Non aprire file allegati ai messaggi di posta elettronica sospetti.

-   Non rispondere a messaggi di posta elettronica sospetti o non richiesti.

-   Configurare le opzioni di posta indesiderata in Outlook 2003 come descritto nella precedente sezione "Posta elettronica indesiderata di Outlook 2003 e Outlook Web Access" del presente documento.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

Molte medie imprese basano numerosi processi aziendali critici sulla funzionalità di Microsoft Exchange Server 2003. Una significativa percentuale delle attività quotidiane dipende dai servizi forniti da Exchange Server.

Il flusso sempre crescente di posta indesiderata continua a rappresentare un'importante sfida per le medie imprese. La posta indesiderata non è solo fastidiosa, ma può anche sovraccaricare le reti e causare sprechi di tempo, denaro e altre risorse per gli individui e le aziende di tutto il mondo.

In questo documento è stato mostrato in che modo è possibile ridurre la posta indesiderata negli ambienti Exchange Server 2003. Exchange Server 2003 Anti-Spam Framework integra approcci di protezione contro la posta indesiderata che forniscono una flessibilità sufficiente agli amministratori e agli utenti finali per ridurre la posta indesiderata e aumentare i livelli di produttività.

[](#mainsection)[Inizio pagina](#mainsection)

### Riferimenti

Per scaricare il documento [Microsoft Exchange Server 2003 Anti-Spam Framework Overview](http://download.microsoft.com/download/0/e/6/0e6a7113-dda4-4fd7-aaba-b9e264700225/anti-spam.doc) (in inglese), andare sull'Area download Microsoft all'indirizzo http://download.microsoft.com/download/0/E/6/0E6A7113-DDA4-4FD7-AABA-B9E264700225/Anti-Spam.doc.

L'argomento [Better Protection Against Spam](http://www.microsoft.com/exchange/evaluation/sp2/overview.mspx) (in inglese) della panoramica di Exchange Server 2003 SP2 è disponibile all'indirizzo www.microsoft.com/exchange/evaluation/sp2/overview.mspx\#antispam.

Ulteriori informazioni su [Exchange Intelligent Message Filter](http://www.microsoft.com/technet/prodtechnol/exchange/downloads/2003/imf/default.mspx) (IMF) (in inglese) e i relativi aggiornamenti sono disponibili nel sito Microsoft TechNet all'indirizzo www.microsoft.com/technet/prodtechnol/exchange/downloads/2003/imf/default.mspx.

Il white paper "[Messaging Hygiene at Microsoft: How Microsoft IT Defends Against Spam, Viruses, and E-Mail Attacks](http://technet.microsoft.com/en-us/library/bb735195.aspx)" (in inglese) è disponibile nel sito Microsoft TechNet all'indirizzo http://technet.microsoft.com/en-us/library/bb735195.aspx.

L'articolo "[Blocco degli indirizzi in tempo reale in Exchange Server 2003](http://www.microsoft.com/technet/prodtechnol/exchange/2003/insider/block_lists.mspx)" è disponibile nel sito Microsoft TechNet all'indirizzo www.microsoft.com/technet/prodtechnol/exchange/2003/insider/Block\_Lists.mspx.

L'articolo della Microsoft Knowledge Base "[Configurazione del filtro connessioni affinché utilizzi elenchi RBL (Realtime Block List) e del filtro destinatari in Exchange 2003](http://support.microsoft.com/default.aspx?scid=823866)" è disponibile all'indirizzo http://support.microsoft.com/default.aspx?scid=823866.

**Download**

[Scarica il documento Approaches to Fighting Spam in an Exchange Server Environment (in inglese)](http://go.microsoft.com/fwlink/?linkid=71052)

[](#mainsection)[Inizio pagina](#mainsection)
