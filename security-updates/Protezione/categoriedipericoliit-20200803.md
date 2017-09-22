---
TOCTitle: Categorie di pericoli IT
Title: Categorie di pericoli IT
ms:assetid: '99595253-5084-448c-af9c-55ad203d2e73'
ms:contentKeyID: 20200803
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536203(v=TechNet.10)'
---

Isolamento del server e del dominio tramite IPsec e criteri di gruppo
=====================================================================

### Appendice D: Categorie di pericoli IT

Aggiornato: 16 febbraio 2005

In questa appendice vengono elencati i possibili pericoli e attacchi a cui può essere soggetta un'organizzazione e si illustra come una soluzione di isolamento dei server e dei domini sia in grado di ridurre tali rischi.

##### In questa pagina

[](#ecaa)[Pericoli identificati dal modello STRIDE](#ecaa)
[](#ebaa)[Altri pericoli](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Pericoli identificati dal modello STRIDE

In questa sezione vengono descritti i numerosi rischi di protezione della rete identificati dal modello STRIDE (ossia, problemi di manomissione, ripudio, diffusione non autorizzata di informazioni, negazione del servizio e aumento del livello dei privilegi) e le misure di protezione previste da questa soluzione al fine di ridurre tali rischi.

#### Pericoli di spoofing di identità

I pericoli di spoofing di identità comprendono qualsiasi azione per ottenere o accedere illegalmente e utilizzare le informazioni di autenticazione di un'altra persona, ad esempio nome utente o password. Questa categoria di pericoli include gli attacchi di tipo "man-in-the-middle" e le comunicazioni di host affidabili con host non affidabili.

##### Attacchi di tipo "man-in-the-middle"

Gli *attacchi di tipo "man-in-the-middle"* sono una tecnica comunemente impiegata dai pirati informatici consistente nel collocare un computer tra due computer che comunicano tra loro tramite una connessione di rete affinché il computer interposto rappresenti uno o entrambi i computer originali. Mediante questa tecnica, il pirata informatico dispone di un computer con una connessione attiva ai computer originali che gli consente di leggere e/o modificare i messaggi trasmessi da un computer all'altro, all'insaputa degli utenti dei due computer originali.

Alcuni provider di servizi Internet (ISP) hanno sviluppato filtri al fine di combattere gli attacchi di tipo "man-in-the-middle" e lo spoofing di messaggi di posta elettronica. Ad esempio, numerosi ISP autorizzano i loro utenti a inviare messaggi esclusivamente tramite i propri server, giustificando tale restrizione con la necessità di combattere la diffusione dei messaggi di posta indesiderata. Tuttavia, questa limitazione impedisce agli utenti autorizzati di utilizzare servizi di posta elettronica legittimi forniti da terzi e ciò non incontra il favore di molti utenti avanzati. Alcuni provider di servizi Internet via cavo tentano di bloccare il traffico audio o video al fine di costringere gli utenti a utilizzare i loro servizi VoIP (Voice over IP) o di streaming video. Altri esempi includono tentativi di divieto di alcune forme di traffico su reti private virtuali (VPN, Virtual Private Network), giustificati dal fatto che tali reti rappresenterebbero un servizio aziendale che comporterebbe, pertanto, tariffe di abbonamento più alte oppure tentativi di impedire agli utenti di gestire server all'interno di ambienti domestici.

Solitamente, i filtri applicati dagli ISP utilizzano le funzioni hardware di router con tipi di protocolli specifici, quali UDP (User Datagram Protocol) e TCP (Transmission Control Protocol), numeri di porta o flag TCP (pacchetti delle connessioni iniziali, ma non dati o conferme). Il criterio IPSec disabilita efficacemente questo tipo di filtraggio e pertanto ai provider ISP non rimangono che due opzioni estreme: bandire tutto il traffico IPSec o bandire il traffico con determinati dispositivi di pari livello identificati. Se molti utenti dell'ISP utilizzano IPSec, la scelta di una di queste opzioni potrebbe determinare forti ripercussioni commerciali per il provider.

##### Comunicazioni di host affidabili con host non affidabili

Questo pericolo racchiude in realtà diversi pericoli di minore entità e include i problemi dello spoofing di identità generico, la modifica dei dati tra gli endpoint di una trasmissione e l'ascolto e l'intercettazione non autorizzati. Tuttavia, il pericolo più rilevante è rappresentato dallo spoofing, in quanto questa tecnica è volta a indurre con l'inganno un host attendibile a credere di essere in comunicazione con un altro host attendibile. Non tutti gli host che vengono isolati nell'ambito di questa soluzione hanno necessità di comunicare con host non attendibili. Poiché il criterio IPSec determina il livello di protezione richiesto tra due host all'avvio della comunicazione mediante un meccanismo basato su criteri, per affrontare la maggior parte di questi problemi è necessario valutare attentamente i compromessi che si è disposti ad accettare in termini di protezione e comunicazione per pervenire quindi a una progettazione e un'implementazione di criteri IPSec che riflettano la scelta adottata. Nel capitolo 5, "Creazione dei criteri IPSec per i gruppi di isolamento", vengono illustrati i requisiti di comunicazione dello scenario della Woodgrove Bank, nonché la metodologia adottata dalla Woodgrove per creare criteri IPSec per la gestione delle modalità di comunicazione.

#### Manomissione dei dati

I pericoli di manomissione dei dati comprendono l'alterazione intenzionale dei dati. Esempi sono modifiche non autorizzate di dati permanenti (come l'alterazione di un sito Web), delle informazioni contenute in un database o dei dati trasmessi da un computer a un altro su una rete aperta. Appartiene a questa categoria il dirottamento di sessione.

##### Dirottamento di sessione

I meccanismi di autenticazione progettati correttamente e le password casuali lunghe sono in grado di resistere rispettivamente ai tentativi di sniffing della rete e agli attacchi del dizionario. I pirati informatici potrebbero tuttavia utilizzare il dirottamento di sessione per catturare una sessione dopo l'autenticazione e l'autorizzazione dell'utente. Il dirottamento di sessione può inoltre consentire a un pirata informatico di utilizzare i privilegi degli utenti autorizzati per modificare un database e persino installare software da utilizzare per ulteriori attacchi, anche senza essersi impossessato delle credenziali dell'utente. Il metodo più semplice per effettuare un dirottamento di sessione consiste nel tentare in primo luogo di collocare il computer da utilizzare per l'attacco in un punto del percorso della connessione mediante un apposito strumento di pirateria informatica. L'autore dell'attacco è così in grado di osservare lo scambio, subentrandovi al momento opportuno. Poiché il pirata informatico si trova lungo il percorso, può decidere di interrompere un lato della connessione TCP e mantenere l'altro lato utilizzando i parametri TCP/IP e i numeri di sequenza corretti. La crittografia e l'autenticazione tramite IPSec consentono di proteggere entrambi gli endpoint dai tentativi di dirottamento di sessione.

#### Ripudio

I pericoli di ripudio sono associati a utenti che negano di aver eseguito un'azione, mentre le altre parti non hanno modo di provare il contrario. Un esempio potrebbe essere quando un utente esegue un'operazione proibita in un sistema nel quale non esiste la possibilità di risalire a chi ha eseguito l'operazione. Il non ripudio si riferisce alla capacità di un sistema di combattere i pericoli di ripudio. Ad esempio, un utente che effettua un acquisto tramite un sito Web potrebbe dover firmare al ricevimento del prodotto. Il fornitore potrebbe quindi utilizzare la ricevuta firmata come prova che il cliente ha ricevuto il prodotto.

#### Diffusione non autorizzata di informazioni

I pericoli di diffusione non autorizzata delle informazioni sono relativi all'esposizione di informazioni a persone che non dovrebbero accedervi. Esempi sono la possibilità degli utenti di leggere file per i quali non avevano ricevuto le necessarie autorizzazioni di accesso o la possibilità che un intruso legga dati in transito tra due computer. I pericoli appartenenti a questa categoria includono le connessioni non autorizzate e lo sniffing della rete.

##### Connessioni non autorizzate

Diverse configurazioni di rete sono basate su un approccio alla protezione poco restrittivo in base al quale si concede l'accesso a una notevole quantità di dati provenienti dai computer all'interno del perimetro. A volte si tratta di accesso esplicito (come nel caso dei server Web della rete Intranet), a volte l'accesso è implicito in quanto manca una protezione efficace di alcune applicazioni. Talvolta si fa affidamento su semplici test degli indirizzi che i pirati informatici riescono ad aggirare con la contraffazione degli stessi.

Con il criterio IPSec, è possibile implementare un ulteriore controllo delle connessioni, ad esempio configurando regole dei criteri che rendano le applicazioni accessibili solo dopo l'esito positivo di una negoziazione IPSec.

##### Sniffing della rete

L'autore di un attacco può tentare di catturare il traffico di rete con due finalità: per ottenere copie di file importanti durante la loro trasmissione o per ottenere le password che gli consentirebbero di penetrare ulteriormente all'interno della rete. Per le reti broadcast, gli hacker utilizzano strumenti di sniffing dei pacchetti per registrare le connessioni TCP e ottenere copie delle informazioni trasmesse. Sebbene tali strumenti non funzionino molto bene per le reti commutate, il protocollo ARP (Address Resolution Protocol) può subire attacchi mediante altri strumenti appositamente predisposti, che reindirizzano il traffico IP attraverso il computer del pirata informatico, consentendogli di registrare tutte le connessioni.

Poiché alcuni protocolli, ad esempio il POP3 (Post Office Protocol 3) e l'FTP (File Transfer Protocol (FTP), inviano password non crittografate attraverso la rete, un pirata informatico che esegua lo sniffing della rete non avrebbe difficoltà a ottenere questo tipo di informazioni. Diverse applicazioni utilizzano un meccanismo challenge/response che evita il problema dell'invio di password in testo normale, ma migliora di poco la protezione. Il pirata informatico, pur non riuscendo a leggere direttamente la password, potrebbe comunque ottenere una copia del challenge/response mediante un attacco del dizionario. La crittografia tramite IPSec di tali comunicazioni consente di proteggere efficacemente contro lo sniffing della rete.

#### Negazione del servizio

Gli attacchi di negazione del servizio (DoS, Denial of Service) sono attacchi rivolti a specifici host o reti. Questo tipo di attacco prevede solitamente l'invio a un host o router di una quantità di traffico superiore a quella che l'host o il router è in grado di gestire in un determinato intervallo di tempo, provocando così l'incapacità della rete di gestire il traffico e la conseguente interruzione del flusso del traffico autorizzato. Gli attacchi di negazione del servizio possono avvenire in forma distribuita tra numerosi vettori di attacco ai danni di un obiettivo mirato. I computer oggetto dell'attacco vengono solitamente compromessi in qualche modo con l'installazione di un programma o uno script di software dannoso che consente agli autori dell'attacco di utilizzare tali computer per il flooding coordinato di traffico di rete verso altri computer o gruppi di computer. I computer violati vengono definiti *zombi* e questo tipo di attacco è detto *attacco di negazione del servizio distribuita (DDoS, Distributed Denial of Service)*.

IPSec richiede l'autenticazione prima che la comunicazione venga stabilita e consente pertanto di ridurre la maggior parte dei rischi di attacchi di negazione del servizio distribuita (ad eccezione degli attacchi da parte di utenti attendibili). In altri termini, il criterio IPSec rende innocui tutti gli attacchi di negazione del servizio distribuita basati su Internet, tuttavia un attacco di negazione del servizio che ha origine all'interno della rete aziendale potrebbe riuscire se l'host o gli host da cui proviene l'attacco possono autenticarsi e comunicare mediante IPSec.

##### Distinzione del traffico standard dal traffico soggetto ad attacchi

Subito dopo la diffusione del worm Slammer, nel gennaio 2003, è stato rilevato che sarebbe stato possibile evitare il sovraccarico delle reti con il traffico generato dal worm mediante l'adozione di una semplice regola per la limitazione del traffico UDP fino al 50 percento della larghezza di banda disponibile. In tal modo, il traffico UDP degli host infetti avrebbe rapidamente occupato tutto il 50 percento della larghezza di banda disponibile, ma l'altro 50 percento sarebbe rimasto disponibile per il traffico operativo. I bancomat avrebbero continuato a funzionare e gli amministratori sarebbero stati in grado di applicare patch e distribuire criteri tramite il protocollo TCP. Il criterio della limitazione del traffico UDP è semplicistico, ma il suo mantenimento può rappresentare un'affidabile rete di protezione.

Utilizzando il criterio IPSec per il traffico importante, gli amministratori sono in grado di applicare una versione leggermente più sofisticata del criterio UDP. In una situazione tipica, l'amministratore di rete può monitorare il traffico sulla rete determinando quanto di esso è traffico UDP, TCP, ICMP (Internet Control Message Protocol) e così via. In condizioni di stress, un algoritmo WFQ (Weighted Fair Queuing) consentirebbe di assicurare la condivisione delle risorse in base a uno schema standard. In effetti, è solitamente possibile programmare tale criterio per impostazione predefinita nei router, raccogliere i dati di tendenze e statistiche a lungo termine per i periodi di attività di rete standard e applicare i dati raccolti in forma di WFQ durante i periodi di elevata congestione del traffico.

##### Worm e attacchi di negazione del servizio

Recentemente, è emerso chiaramente come le reti siano vulnerabili agli attacchi di negazione del servizio, che vengono attuati inviando una quantità di traffico eccessiva al fine di saturare un server specifico oppure una determinata porzione della rete. Un tipo di attacco di negazione del servizio viene attuato con una modalità distribuita, che prevede l'invio simultaneo di traffico da parte di più computer verso un obiettivo prescelto e può essere particolarmente difficile da contrastare. Il worm CodeRed ha inizialmente tentato di insinuarsi all'interno di diversi server Web, tramite i quali gli autori dell'attacco intendevano inviare un sovraccarico di traffico verso il dominio della Casa Bianca degli Stati Uniti, whitehouse.gov. In realtà, i meccanismi utilizzati per la propagazione dei worm CodeRed, Nimda e Slammer non erano altro che attacchi di negazione del servizio rivolti alla rete Internet. Ogni singolo computer infetto ha tentato a sua volta di infettare indiscriminatamente centinaia di migliaia di altri obiettivi, provocando così l'interruzione del servizio di diverse reti locali e regionali a causa del sovraccarico di traffico.

Il criterio IPSec protegge in diversi modi contro gli attacchi di negazione del servizio e assicura un ulteriore livello di protezione alle potenziali vittime degli attacchi. Rallenta la diffusione degli attacchi sovraccaricando le risorse di elaborazione e permette ai gestori delle reti di distinguere tra i diversi tipi di traffico.

#### Aumento del livello dei privilegi

In presenza di questo tipo di pericolo, un utente privo di privilegi riesce a ottenere l'accesso con privilegi che gli consentono di violare o persino distruggere l'intero ambiente di sistema. Questi pericoli comprendono situazioni in cui l'autore di un attacco ha effettivamente superato tutte le barriere di difesa del sistema per sfruttare e danneggiare il sistema.

[](#mainsection)[Inizio pagina](#mainsection)

### Altri pericoli

Il modello STRIDE non comprende tutti i tipi di pericoli esistenti. Di seguito vengono illustrati altri contesti di pericolo e si descrive il potenziale impatto dei relativi rischi su una soluzione di isolamento dei server e dei domini.

#### Protezione fisica

Per protezione fisica si intende limitare l'accesso fisico a un sistema o a una risorsa al numero minimo di utenti che la richiedono. La protezione fisica rappresenta il livello di difesa più basso contro la maggior parte dei pericoli per la protezione IT. Tuttavia, molti attacchi alle reti aggirano totalmente la barriera offerta dalla protezione fisica. La protezione fisica riveste una notevole importanza ai fini di un approccio di difesa su più livelli. Forme di protezione fisica quali addetti alla sorveglianza, videocamere di controllo dei centri dati, controlli degli accessi ad ambienti in cui avvengono operazioni riservate, tessere di riconoscimento o la chiusura a chiave delle porte contribuiscono a prevenire la violazione delle periferiche aziendali. L'adozione di diversi metodi di protezione fisica è importante e consente di prevenire alcune delle più gravi violazioni della protezione dei centri dati.

È inoltre necessario sottolineare che la violazione dei sistemi di protezione fisica comporta sempre la violazione di *tutti* i livelli di protezione. Tutte le forme di protezione presentate nell'ambito della presente soluzione presuppongono che l'azienda abbia preventivamente adottato sistemi di protezione fisica adeguati. In caso contrario, verrebbe meno l'efficacia di tutte le altre misure di protezione eventualmente adottate.

#### Protezione della rete

Una rete è un sistema di computer connessi tra loro. La maggior parte dei protocolli e dei servizi progettati per le reti non sono stati creati con finalità di protezione dagli utenti malintenzionati. La disponibilità di risorse informatiche ad alta velocità, la facilità di accesso alle reti e l'ampia diffusione di Internet hanno favorito i tentativi da parte di pirati informatici di accedere a sistemi e servizi per sfruttarne le vulnerabilità o comprometterne il funzionamento. Numerosi pericoli di rete sono già stati descritti nel dettaglio in questa appendice. Ulteriori informazioni sulle modalità di protezione tramite IPSec da alcune tipologie di attacco alle reti sono disponibili nella sezione [IPSec](http://technet.microsoft.com/en-us/library/cc783420.aspx) del capitolo 19, "Configuring TCP/IP", del *Windows® XP Professional Resource Kit*, all'indirizzo www.microsoft.com/resources/documentation/Windows/
XP/all/reskit/en-us/prcc\_tcp\_naoc.asp.

#### Protezione dell'applicazione

La maggior parte degli attacchi alle applicazioni tentano di sfruttare le vulnerabilità esistenti nelle applicazioni o nel sistema operativo. Poiché viene implementato al livello di rete del modello OSI (Open Systems Interconnection), il criterio IPSec è in grado di determinare se un pacchetto è consentito o rifiutato prima che tale pacchetto raggiunga l'applicazione. Ciò significa che la protezione IPSec non avviene al livello dell'applicazione, tuttavia consente di proteggere il traffico dell'applicazione al livello inferiore.

#### Individuazione di persone vulnerabili

I punti deboli del comportamento umano possono venire sfruttati per ottenere l'accesso a un sistema o ottenere maggiori informazioni su di esso. Il potenziale autore di un attacco potrebbe, ad esempio, telefonare all'azienda che intende violare chiedendo il nome del supervisore responsabile di un determinato progetto, ad esempio un nuovo prodotto o servizio che l'azienda sta sviluppando e su cui l'autore dell'attacco desidera acquisire maggiori informazioni. Se chi risponde al telefono fornisce il nome del supervisore, eventualmente indicando anche l'ufficio in cui lavora o i suoi recapiti, l'autore dell'attacco ottiene maggiori informazioni che potrà così utilizzare per elaborare un attacco più mirato.

Poiché questo tipo di attacco è rivolto agli utenti anziché ai computer, il criterio IPSec non è in grado di offrire alcuna protezione. Analogamente, per prevenire la possibilità che un utente malintenzionato in grado di accedere ai sistemi isolati utilizzi impropriamente i diritti di accesso di cui dispone (in tal caso, si parla di *pirata informatico attendibile*), è necessario utilizzare tecnologie di protezione diverse.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

L'isolamento dei server e dei domini non consente ovviamente di risolvere tutti i pericoli esistenti in un'organizzazione. L'adeguata protezione degli ambienti IT può essere ottenuta solo con una comprensione approfondita delle opzioni di protezione disponibili unita a una profonda conoscenza delle difficoltà di natura tecnica esistenti.

**Scarica la soluzione completa**

[Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=33947)

[](#mainsection)[Inizio pagina](#mainsection)
