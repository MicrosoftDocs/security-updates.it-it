---
TOCTitle: 'Gestione di identità e accessi: Piattaforma e infrastruttura'
Title: 'Gestione di identità e accessi: Piattaforma e infrastruttura'
ms:assetid: '1d304833-bd34-49f9-9bff-d474225c7aa0'
ms:contentKeyID: 20200824
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536225(v=TechNet.10)'
---

Piattaforma e infrastruttura
============================

### Capitolo 3: Problemi e requisiti

Aggiornato: 29 aprile 2004

Per implementare un'infrastruttura efficace per la gestione di identità e accessi nella propria organizzazione, occorre scegliere una piattaforma tecnologica confrontando in modo critico i requisiti dell'organizzazione e le sue reali capacità tecnologiche. Questa analisi funzionale assicura che la soluzione soddisfi gli obiettivi aziendali allo stesso tempo mantenendo la piattaforma protetta e gestibile.

Il presente documento illustra questi aspetti in riferimento alla società fittizia Contoso Pharmaceuticals. Lo scenario di Contoso Pharmaceuticals intende fornire un approfondimento dei problemi che una normale organizzazione può dover affrontare quando si occupa di aspetti tipici della gestione di identità e accessi.

### Presentazione di Contoso Pharmaceuticals

Contoso Pharmaceuticals è una società fittizia con sede e principale stabilimento a Orlando, Florida, negli Stati Uniti. Contoso attualmente vanta 5.300 dipendenti ed entrate annue di 3,8 miliardi di dollari.

Il successo della società si basa principalmente su una cultura aziendale focalizzata su un'attività pionieristica di ricerca e sviluppo. Contoso Pharmaceuticals è nota per il suo impegno nel servizio clienti e le sue strutture produttive a basso costo. Contoso ha conosciuto una grande espansione negli ultimi due anni, in parte dovuta all'acquisizione di una piccola società di forniture farmaceutiche, Fabrikam Ltd. (un'altra società fittizia) nel Regno Unito. Per rafforzare la posizione sul mercato della casa madre, sono previste molte altre acquisizioni di questo tipo.

#### Reparto IT

Il reparto IT di Contoso vanta alcune centinaia di dipendenti tecnici e addetti alla gestione. I 22 amministratori di sistema impiegati a tempo pieno gestiscono oltre 500 server di tutti i tipi, inclusi computer che eseguono sistemi operativi per server basati su Microsoft® Windows®, Sun ONE Directory Server 5.1 (già iPlanet Directory Server) e computer mainframe con applicazioni personalizzate e di terze parti. Gli amministratori inoltre gestiscono l'infrastruttura aziendale Microsoft Exchange Server e un portale interno Contoso per i dipendenti. I server rimanenti sono dedicati a servizi di archiviazione e stampa e a funzioni database.

L'amministrazione dei controller di dominio Microsoft Windows Server™ 2003 e del servizio directory Microsoft Active Directory® della società rappresenta una parte importante delle operazioni quotidiane. Una delle numerose attività svolte dagli amministratori del sistema è l'implementazione degli account in Active Directory.

Contoso offre un servizio di assistenza con numeroso personale esperto, disponibile 24 ore su 24, 7 giorni a settimana. Gli operatori di questo servizio forniscono assistenza per varie applicazioni, ad esempio di posta elettronica, elaborazione testi e aziendali, oltre che per reimpostare le password dei dipendenti esclusi per errore dai sistemi della società. Contoso inoltre impiega molti architetti che si occupano di protezione e dell'infrastruttura e riesaminano i requisiti IT dei reparti e dell'intera azienda per creare proposte finalizzate alle strategie, agli investimenti e agli standard IT.

#### Sistemi operativi

L'infrastruttura IT di Contoso Pharmaceuticals comprende un'ampia gamma di piattaforme di sistema e applicazioni. Benché la maggior parte dei sistemi sia costituita da server e client basati su Windows, Contoso dispone anche di sistemi critici per l'attività dell'azienda, compresi server che eseguono Sun ONE Directory Server 5.1 e workstation dotate di Sun Solaris 9. Attualmente i sistemi con Sun Solaris 9 sono gestiti tramite Network Information System (NIS).

Il layout Active Directory dell'Intranet di Contoso presenta un unico insieme di strutture con un dominio principale vuoto e un singolo dominio figlio. Tutti gli account originali degli utenti, dei servizi e dei computer Contoso sono stati trasferiti in Active Directory da domini Microsoft Windows NT® 4.0. Inoltre la società gestisce i server DNS (Domain Name System) esterni che supportano il dominio Internet Contoso.com. Questi server DNS sono separati da quelli interni che supportano l'insieme di strutture Active Directory dell'Intranet.

#### Archivi di identità aggiuntivi

Durante la sua recente acquisizione di Fabrikam Ltd., Contoso ha acquisito anche vari prodotti per l'infrastruttura, come Lotus Notes Release 5 per la messaggistica e un server che esegue Sun ONE Directory Server 5.1 e fornisce servizi directory e di autenticazione per un'applicazione Web personalizzata. Tali sistemi sono ancora necessari per supportare le attività aziendali degli ex-dipendenti Fabrikam nel breve periodo. La pianificazione a lungo termine richiede la migrazione dell'infrastruttura Fabrikam nell'ambiente Contoso esistente.

[](#mainsection)[Inizio pagina](#mainsection)

### Problemi tecnologici e aziendali

Contoso opera in un ambiente molto competitivo, nel quale i tempi di commercializzazione rappresentano un fattore chiave. Gli studi clinici richiedono grandi investimenti e un solo giorno di ritardo per consegnare i risultati o sottoporre un prodotto per l'approvazione della FDA (Food and Drug Administration) negli Stati Uniti può causare alla società perdite fino a un milione di dollari. Di conseguenza, l'interazione con utenti e partner è un elemento chiave delle operazioni della società. Le normative rappresentano un'altra considerazione essenziale, in quanto le ammende e le pene legali possono variare da milioni a decine di milioni di dollari.

Una delle sfide principali che Contoso deve affrontare riguarda l'espansione della qualità e dell'ambito della propria interazione con i clienti, i partner e i dipendenti in postazioni remote. Il ricorso a nuovi modi per interagire con i clienti e ottenerne i commenti, nonché comunicare i vantaggi dei prodotti dell'organizzazione, ha portato a molti miglioramenti. Fra questi, particolare importanza hanno i miglioramenti del processo di sviluppo prodotti, per soddisfare meglio le esigenze dei clienti, in quanto possono aumentare la quota di mercato della società. Tuttavia in passato il coinvolgimento dell'amministrazione ha reso questo processo costoso e difficile da gestire.

Contoso sa che migliorare le soluzioni tecnologiche utilizzate per collaborare con i partner porterà a una maggiore efficienza nel processo di sviluppo dei prodotti. Allo stesso tempo, i dipendenti tendono a lavorare sempre più in remoto e richiedono di accedere più facilmente ai dati, sia tramite la rete aziendale che via Internet.

Contoso ritiene che una piattaforma di gestione di identità e accessi debba migliorare la gestibilità e la protezione dell'infrastruttura, soprattutto nelle aree dove vengono gestite le identità digitali. Come obiettivo a lungo termine, la società desidera riunire gli archivi di identità duplicati per applicazioni distinte in un'unica struttura centralizzata in grado di assicurare una maggiore efficienza e minori errori nell'amministrazione, un costo totale di proprietà (TCO, Total Cost of Ownership) più basso e una superiore protezione.

Comunque, gli architetti e gli amministratori di Contoso sanno di dover affrontare alcuni aspetti a breve e medio termine prima di raggiungere tali obiettivi, in particolare dal punto di vista della protezione. La sezione "Pericoli e contromisure" riportata più avanti nel presente documento riassume le preoccupazioni per la protezione e le contromisure in grado di ridurre o neutralizzare i pericoli.

Contoso Pharmaceuticals ha identificato i seguenti requisiti chiave nel suo piano biennale per migliorare la gestione di identità e accessi.

-   Fornire l'infrastruttura tecnologica migliore possibile per sviluppare, valutare e commercializzare rapidamente i prodotti della società.

-   Aumentare il livello di efficienza e protezione dell'infrastruttura IT della società, in particolare gestendo le identità digitali, al fine di preparare la strada per una crescita aggiuntiva senza dover accumulare ulteriore sovraccarico amministrativo e complessità IT.

-   Raggruppare i meccanismi di protezione e riservatezza, e le tecnologie correlate, al fine di soddisfare i requisiti normativi del governo, quali il 21 Code of Federal Regulations (CFR) Part 11 (Part 11) della FDA e l'Health Insurance Portability and Accountability Act (HIPAA) del 1996.

Per soddisfare tali requisiti, Contoso ha iniziato un'esauriente revisione delle proprie applicazioni e processi più critici. La sezione seguente identifica queste risorse chiave.

#### Risorse IT chiave

Contoso Pharmaceuticals ha identificato alcune risorse IT che hanno la massima importanza per la società. Le risorse seguenti offrono capacità chiave per rispondere a essenziali problemi tecnici e dell'attività aziendale:

-   L'applicazione per le vendite e i contatti, accessibile tramite Extranet, e gli account utente dei dipendenti del reparto vendite.

-   L'applicazione per i partner di ricerca, accessibile tramite Extranet, e l'archivio Extranet delle identità dei partner.

-   L'applicazione per i commenti relativi alle dimostrazioni offerte ai clienti, accessibile tramite Extranet, e l'archivio Extranet delle identità dei clienti.

-   Dati delle applicazioni SAP e account utente SAP.

-   Infrastruttura della posta elettronica e account Microsoft Exchange.

-   Infrastruttura della posta elettronica e account Lotus Notes.

-   Applicazioni che utilizzano account utente Sun ONE Directory Server 5.1 e UNIX.

##### L'applicazione per le vendite e i contatti accessibile tramite Extranet

La forza vendite di Contoso trascorre buona parte del tempo fuori ufficio, facendo visita ai clienti e creando nuove opportunità commerciali. Lo staff può tenere traccia delle proprie vendite e dei relativi contatti grazie a un'applicazione e a un database Web nella rete perimetrale di Contoso, nota anche come DMZ (Demilitarized Zone). La riservatezza delle informazioni gestite da questa applicazione non è critica. Tuttavia, l'esposizione di questi dati potrebbe causare problemi a Contoso e ai suoi partner commerciali e avrebbe un impatto più ampio sulla percezione pubblica dell'attendibilità di Contoso.

La mancata disponibilità dell'applicazione costituirebbe il problema principale, poiché comprometterebbe gravemente l'efficacia della forza vendite.

##### Account utente dei dipendenti del reparto vendite

Gli account utente dei singoli dipendenti alle vendite possono accedere a materiale riservato in un ambito specifico, tramite Extranet. Inoltre questi account potrebbero essere utilizzati per cercare di attaccare tutta l'organizzazione Contoso e in particolare le risorse IT.

##### L'applicazione per i partner di ricerca, accessibile tramite Extranet

La collaborazione con i partner di ricerca è essenziale per lo sviluppo di nuovi prodotti, un'attività dalla quale dipende la futura espansione di Contoso. Gran parte della collaborazione ha luogo mediante una singola applicazione nella rete perimetrale di Contoso. Benché i dati nell'applicazione vengano spesso sottoposti a backup, un attacco all'applicazione riuscito potrebbe causare gravi problemi a Contoso: se i dati di ricerca venissero divulgati, la concorrenza guadagnerebbe un notevole margine di vantaggio e la società potrebbe subire azioni disciplinari.

##### L'archivio Extranet degli account dei partner

Gli account dei partner, rispetto a quelli dei dipendenti, godono di un accesso più limitato alle risorse IT di Contoso. In effetti possono accedere esclusivamente all'applicazione per i partner di ricerca. Tuttavia, se un singolo account o l'intero archivio venisse compromesso, come minimo sarebbe compromessa anche parte dell'applicazione. Ancora una volta, la concorrenza potrebbe acquistare un margine di vantaggio e la società subire un'azione disciplinare.

##### L'applicazione per le dimostrazioni offerte ai clienti, accessibile tramite Extranet

Il successo dei prodotti Contoso dipende dai primi commenti ricevuti dai clienti durante il ciclo di sviluppo dei prodotti. Uno dei modi in cui Contoso si avvantaggia della tecnologia è fornire un'applicazione Web mediante la quale i clienti possano facilmente sottoporre i propri commenti sui prodotti nella fase dimostrativa.

Contoso raccoglie quasi il 50% delle opinioni dei clienti utilizzando l'applicazione per i commenti sulle dimostrazioni offerte. Danneggiare l'applicazione significherebbe limitare gravemente la capacità dell'azienda di completare gli studi e sottoporre i risultati alla FDA, il che a sua volta potrebbe portare a un'azione disciplinare se la FDA avesse motivo di ritenere che la protezione dell'applicazione fosse stata compromessa.

##### L'archivio Extranet degli account dei clienti

Gli account dei clienti, rispetto a quelli dei dipendenti, godono di un accesso più limitato alle risorse IT di Contoso. In effetti possono accedere esclusivamente all'applicazione per i commenti sulle dimostrazioni offerte ai clienti. Tuttavia, se un singolo account o l'intero archivio venisse compromesso, come minimo sarebbe compromessa anche parte dell'applicazione. Un altro fattore negativo sarebbe il danno alle relazioni con la clientela, dovuto alla percezione che pratiche di protezione insufficienti presso Contoso potrebbero causare la divulgazione di informazioni riservate dei clienti. Anche questo potrebbe portare a un'azione disciplinare contro la società.

##### Dati delle applicazioni SAP e account utente SAP

Contoso ha implementato varie applicazioni per la pianificazione delle risorse d'impresa (ERP, Enterprise Resource Planning) basate su SAP. Alcune di queste applicazioni eseguono funzioni aziendali critiche e distribuiscono agli utenti dati riservati. Se i dati venissero compromessi, sarebbe danneggiata la capacità di Contoso di competere sul mercato e inoltre la società potrebbe subire ammende considerevoli per aver violato i requisiti normativi.

I singoli account utente consentono di accedere a materiale riservato nell'ambito dell'applicazione SAP. Ciò può causare la divulgazione di informazioni finanziarie presso gli investitori, con i prevedibili danni per Contoso.

##### Posta elettronica Microsoft Exchange

Contoso utilizza Microsoft Exchange Server e Microsoft Outlook® per la posta elettronica interna ed esterna. Se questi dati fossero compromessi, i concorrenti potrebbero venire a conoscenza di informazioni commerciali riservate e inoltre la società potrebbe subire un'azione disciplinare.

##### Posta elettronica Lotus Notes

Fabrikam Ltd. utilizzava Lotus Notes per la posta elettronica interna ed esterna; questo ambiente è stato sottoposto a migrazione durante la fusione con Contoso. Se questi dati fossero compromessi, i concorrenti potrebbero venire a conoscenza di informazioni commerciali riservate e inoltre la società potrebbe subire un'azione disciplinare.

##### Account utente Sun ONE Directory Server 5.1 e UNIX

Sun ONE Directory Server 5.1 fornisce servizi directory e supporto all'autenticazione per un'applicazione Web personalizzata, utilizzata da Fabrikam. Se questa applicazione e i relativi dati venissero compromessi, la concorrenza potrebbe acquistare un margine di vantaggio e la società subire un'azione disciplinare.

I singoli account utente UNIX possono accedere a materiale riservato in un ambito specifico presso Contoso. Inoltre questi account potrebbero essere utilizzati per cercare di attaccare tutta l'organizzazione Contoso e in particolare le risorse IT.

#### Completamento dell'analisi

Al termine dell'analisi delle proprie risorse IT, Contoso ha identificato i problemi seguenti con l'attuale piattaforma di gestione di identità e accessi:

-   Non esiste una strategia definita per ridurre il costo e la complessità della gestione delle identità digitali nell'ambiente di Contoso.

-   L'implementazione e la deimplementazione degli utenti nelle applicazioni personalizzate non sono procedure standard.

-   Le applicazioni in fase di sviluppo complicano l'infrastruttura IT quando aggiungono più archivi di identità.

-   I metodi di autenticazione spesso sono personalizzati per ciascuna applicazione oppure si tratta di meccanismi obsoleti standard nei sistemi precedenti. In entrambi i casi, l'implementazione è costosa e il grado di protezione spesso inadeguato rispetto ai numerosi pericoli dell'ambiente informatico attuale.

-   L'autorizzazione per le applicazioni è motivo di preoccupazione in quanto gli sviluppatori delle applicazioni tendono a implementare meccanismi dispendiosi, che fanno aumentare tempi e costi di sviluppo e manutenzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Pericoli e contromisure

In realtà molti problemi di protezione della gestione di identità e accessi sono vulnerabilità della protezione. Una vulnerabilità è un punto debole di un sistema informatico o dei relativi componenti che potrebbe essere sfruttata a scopo di violazione. Le vulnerabilità possono derivare da problemi con persone, processi o tecnologie. Gli esempi comprendono procedure di protezione del sistema, struttura dell'hardware o controlli interni. Le vulnerabilità possono presentarsi in qualsiasi punto delle difese della rete e la valutazione normalmente rientra nell'esame complessivo della protezione.

#### Pericoli attuali

Contoso Pharmaceuticals ha appena eseguito un'analisi complessiva della protezione della sua rete. Parte dell'analisi includeva la classificazione dei pericoli per la rete. Al momento di definire l'ambito del progetto di gestione di identità e accessi, Contoso ha stabilito di considerare prima di tutto gli attacchi potenziali da origini interne ed esterne. I pericoli interni sono rivolti all'Intranet, mentre quelli esterni sono specifici per l'Extranet.

#### Problemi e vulnerabilità della protezione

L'ambiente di Contoso presenta un numero di punti deboli correlati ai problemi aziendali e tecnologici descritti in precedenza in questo capitolo. Dal punto di vista della protezione, la soluzione di gestione identità e accessi di Contoso deve affrontare gli aspetti seguenti:

-   Contoso deve rendere disponibile un maggior numero di informazioni aziendali tramite applicazioni Web, ma i meccanismi di protezione implementati nella rete interna non sono abbastanza solidi o coerenti da consentire un ampio accesso alla rete.

-   È difficile analizzare le violazioni della protezione presso Contoso, poiché le prove legali fornite dai registri di controllo della protezione sono incomplete, sconnesse e disparate.

-   Gli attuali archivi delle identità per le applicazioni non sono protetti e un attacco diretto agli account utente che controllano non solo è possibile, ma probabile.

-   Gli attuali meccanismi di autenticazione per le applicazioni non sono sicuri e un attacco contro tali meccanismi non solo è possibile, ma probabile.

-   Gli attuali meccanismi di autorizzazione per le applicazioni sono progettati in modo inadeguato e un attacco contro tali meccanismi non solo è possibile, ma probabile.

La prima vulnerabilità mette in evidenza la sfida costante per la gestione di identità e accessi: i sistemi di interfaccia con i clienti, i partner o i dipendenti possono apportare vantaggi solo se tali utenti sono in grado di accedervi. In ogni caso, la concessione dell'accesso di per sé aumenta il rischio per la protezione.

Suddividendo ulteriormente queste categorie, l'analisi della protezione di Contoso ha identificato i seguenti punti deboli di processi e account, vulnerabili agli attacchi dall'esterno e dall'interno:

-   Implementazione account

-   Deimplementazione account

-   Account delle workstation UNIX

-   Autenticazione SAP

-   Protezione dati delle applicazioni SAP

-   Account dei dipendenti

-   Account dei partner

-   Account dei clienti

Le vulnerabilità degli account di dipendenti, partner e clienti sono simili, ma nel caso degli account dei dipendenti le implicazioni sono più gravi.

##### Implementazione account

Un'implementazione inefficiente o incompleta non rappresenta un pericolo diretto per la protezione, in quanto formalmente definisce solo il livello per l'impossibilità di accedere alle risorse delle applicazioni e della rete. Tuttavia, meccanismi inadeguati di implementazione account possono condurre ad altre pratiche che rappresentano un pericolo immediato per la protezione, ad esempio la condivisione degli account o l'accesso anonimo a risorse importanti.

Il rischio principale associato alla vulnerabilità dell'implementazione degli account è la loro condivisione. Secondo un recente resoconto dell'assistenza tecnica Contoso, questa pratica diffusa sta causando grandi volumi di chiamate, dovute a tentativi di accesso non riusciti, che determinano l'esclusione e il blocco dei relativi account e inducono molti utenti a ricorrere simultaneamente alla stessa identità per accedere alle risorse.

Un'indagine anonima sull'argomento, condotta dal reparto IT di Contoso, ha evidenziato che il motivo principale della condivisione è che gli account dei nuovi dipendenti, necessari per accedere alle applicazioni e alle risorse di rete, non vengono implementati con rapidità sufficiente. La condivisione dell'identità è diffusa soprattutto nel personale a contratto, che spesso deve attendere vari mesi prima di ricevere l'accesso appropriato per svolgere il proprio lavoro.

I supervisori affrontano il problema assegnando al personale temporaneo nomi utente e password definiti per altri utenti, che potrebbero anche non lavorare più per Contoso. Questa pratica straordinaria impedisce agli amministratori di rete o delle applicazioni identificare chi o che cosa stia effettivamente utilizzando le risorse della rete o accedendo ai dati delle applicazioni. Alcuni supervisori hanno persino acconsentito a fornire ai subordinati le informazioni del proprio account e password, permettendo in tal modo allo staff di accedere alle risorse e ai dati protetti dalle autorizzazioni di livello più elevato.

##### Deimplementazione account

La vulnerabilità causata dalla deimplementazione degli account rappresenta un problema molto più grave. Hacker o ex-dipendenti potrebbero utilizzare vecchi account, rimasti negli archivi o nelle directory delle identità per le applicazioni, allo scopo di accedere senza autorizzazione o danneggiare importanti informazioni riservate.

Il rischio principale associato a questa vulnerabilità è dovuto agli account non aggiornati. Un recente controllo di un archivio delle identità per un'applicazione specifica ha rivelato l'esistenza di account ancora attivi per dipendenti che avevano lasciato la società tre anni prima. Gli account non aggiornati offrono una backdoor tramite la quale un utente precedente o un intruso potrebbe attaccare i dati dell'applicazione.

Benché la vulnerabilità in relazione ai precedenti proprietari dell'account sia ovvia, è importante anche considerare che la password di un account non è stata modificata in tre anni. Gli account non aggiornati aumentano le opportunità che malintenzionati riescano a sferrare attacchi di tipo "brute force" alle password statiche, se non sono stati implementati criteri che richiedano di modificare le password e di escludere gli account in caso di errore all'accesso. Questi account possono quindi essere utilizzati per compromettere o danneggiare dati delle applicazioni critici per i processi aziendali di Contoso.

##### Account delle workstation UNIX

Contoso dispone di 40 workstation dotate di Sun Solaris 9 e utlizzate dal personale del reparto contabilità per lo svolgimento delle proprie funzioni quotidiane. Le workstation Solaris vengono amministrate tramite un singolo dominio NIS (Network Information Service).

Sun Microsystems ha sviluppato NIS per accentrare l'amministrazione dei sistemi UNIX. La funzionalità NIS generale è analoga a quella dei domini Windows NT 4.0. NIS è molto diffuso poiché gli amministratori UNIX esperti riescono a impostarlo e amministrarlo senza difficoltà, è ragionevolmente scalabile ed è supportato da quasi tutti i tipi di UNIX. Purtroppo le caratteristiche di protezione di NIS spesso non sono adeguate.

Uno dei problemi di protezione più importanti in NIS è che non consente di applicare criteri per la scadenza o la complessità delle password. Inoltre, tutti i server membri di un dominio NIS ricevono una copia del file delle password contenente la password crittografata di ciascun utente nel dominio.

Le password UNIX vecchie o vulnerabili rappresentano un pericolo per la protezione della rete, poiché consentono agli intrusi di procurarsi rapidamente una combinazione di password e account utente. È quindi possibile utilizzare l'account utente per sferrare attacchi contro sistemi che potrebbero essere protetti solo da attacchi anonimi. Su Internet sono molto diffusi gli strumenti che permettono di condurre attacchi di tipo "brute force" e del dizionario contro i file delle password. A Contoso, agli account utente UNIX non vengono applicati criteri per le password e il file dei criteri delle password NIS è largamente distribuito.

##### Autenticazione SAP

SAP è un server per applicazioni ERP molto noto e ampiamente distribuito e Contoso ha implementato numerose applicazioni per la pianificazione delle risorse d'impresa. Molte applicazioni di questo tipo eseguono funzioni critiche per l'azienda e distribuiscono dati riservati agli utenti. Di conseguenza, si tratta di informazioni critiche per l'attività di Contoso. Le interruzioni nella disponibilità delle applicazioni, nonché i danni, la perdita o l'esposizione dei dati potrebbero costare milioni di dollari alla società.

I meccanismi di autenticazione preesistenti e i protocolli di accesso ai dati forniti da SAP non sono in grado di proteggere i segreti dell'autenticazione (le password) quando vengono utilizzati per accedere all'applicazione. Le password degli utenti SAP possono essere intercettate da chiunque utilizzi una presa di rete su un segmento di rete di un utente.

##### Protezione dati delle applicazioni SAP

Per impostazione predefinita, i dati delle applicazioni SAP client/server inviati sulla rete non sono protetti. Qualsiasi intruso in grado di visualizzare il traffico di rete sul segmento di rete di un utente SAP può compromettere i dati delle applicazioni SAP appropriandosene o introducendo informazioni scorrette, con effetti potenzialmente gravi sulla coerenza dei dati del sistema SAP.

Lo scambio dei dati fra gli utenti e il server di applicazioni SAP è un fattore critico per l'attività dell'azienda. Ancora una volta, le interruzioni nella disponibilità delle applicazioni, nonché i danni, la perdita o l'esposizione dei dati potrebbero costare milioni di dollari alla società.

##### Account dei dipendenti

La vulnerabilità degli account dei dipendenti comporta due rischi principali: l'autenticazione tramite password non crittografate e la memorizzazione tramite password non crittografate su server non protetti. Queste vulnerabilità riguardano sia le reti interne che quelle esterne.

Quando i dipendenti del reparto Vendite di Contoso eseguono l'autenticazione per l'applicazione esterna di gestione vendite e contatti, spesso utilizzano le credenziali del proprio account aziendale. In questo modo però possono esporre le credenziali a pericoli esterni, se viene compromesso il server Web nella rete perimetrale, o agli amministratori delle applicazioni che non possono essere considerati attendibili per tali informazioni.

##### Autenticazione con password non crittografate

Un'analisi dell'utilizzo delle password nello scenario di Contoso ha dimostrato che i dipendenti dell'organizzazione di vendita della società si sono serviti delle password dei loro account aziendali per accedere a un'applicazione Web sui server nella rete perimetrale. L'applicazione per le vendite utilizza l'autenticazione di base tramite SSL (Secure Sockets Layer) per consentire l'accesso. Benché SSL sia efficace nel proteggere la password dell'utente nella rete, la password non crittografata è presente sul server dell'applicazione Web. Se il server dell'applicazione Web viene compromesso, le password degli utenti non crittografate possono essere accessibili.

Inoltre, non è stato implementato alcun criterio ufficiale, a livello di reparto o della società, per stabilire se la password per questa applicazione debba essere uguale o diversa da quella dell'account aziendale dell'utente; quindi molti dipendenti utilizzano la stessa password, in quanto ricordarne un'altra è difficile.

Ricorrendo a password di account valide, un intruso potrebbe ottenere l'accesso non autorizzato a file e servizi che non sarebbe possibile ottenere in altro modo. Se la password dell'account Extranet dell'utente è identica a quella dell'account aziendale, le informazioni disponibili potrebbero essere ancora di più.

##### Memorizzazione di password non crittografate su server non protetti

Per autenticare gli utenti, l'applicazione di gestione vendite e contatti confronta la password non crittografata ottenuta tramite l'autenticazione di base rispetto a un valore password contenuto in un database Microsoft SQL Server nella rete perimetrale. Ricorrendo a password di account valide, un intruso potrebbe ottenere l'accesso non autorizzato a file e servizi che non sarebbe possibile ottenere in altro modo.

I computer che eseguono SQL Server sono protetti dall'accesso diretto tramite Internet dal criterio IPSec (IP Security Protocol) e dalla struttura fisica della rete. Un attacco su un computer con SQL Server deve essere multilivello e rivolto ai server Web di interfaccia con l'esterno. Tuttavia, poiché non sono stati implementati criteri o tecnologie per impedire agli amministratori dell'applicazione di accedere alle password dei dipendenti, è molto più semplice organizzare l'attacco interno, che richiede soltanto che un amministratore di un'applicazione consulti le informazioni desiderate mentre l'applicazione è in esecuzione.

##### Account dei partner

Contoso ha implementato un'applicazione per i partner di ricerca che utilizza l'autenticazione basata su password. All'applicazione è associato un archivio locale di identità che contiene i nomi utente e le password e si trova in un database in un altro computer, separato dai server Web che gestiscono l'applicazione. Questa struttura è soggetta a vari problemi di gestione delle identità, ma presenta anche vulnerabilità della protezione.

La principale vulnerabilità della protezione riguarda il database degli account. Il database degli account conserva le password in formato non crittografato, in un'unica posizione per tutti gli account che utilizzano l'applicazione. Se utenti non autorizzati riescono ad accedere al database, possono compromettere tutti gli account. Inoltre, durante l'autenticazione, ogni server Web esegue una richiesta non autenticata al database affinché la password dell'utente venga confrontata con le credenziali presentate dall'utente stesso. Il processo richiede che la password non crittografata rimanga disponibile nella rete fisica perimetrale, il che comporta un rischio significativo.

##### Account dei clienti

Contoso ha implementato un'applicazione per i clienti che utilizza l'autenticazione basata su password. Le considerazioni e i rischi correlati a questa vulnerabilità sono gli stessi relativi alle vulnerabilità degli account dei partner.

#### Contromisure di protezione

Se si comprendono adeguatamente le vulnerabilità dell'organizzazione, è possibile scegliere contromisure per risolverle. La scelta di una contromisura di protezione appropriata dipende dalle vulnerabilità che occorre affrontare, dalla loro importanza e dalla probabilità che qualcuno possa avvantaggiarsene.

È particolarmente importante scegliere contromisure adeguate, poiché ciascuna può rispondere a varie vulnerabilità. Inoltre, l'implementazione di una contromisura può avere effetti positivi nell'affrontare altre vulnerabilità secondarie, non evidenziate nella valutazione iniziale dei pericoli. Su tali contromisure si basano i requisiti per la selezione di una piattaforma e del relativo utilizzo.

I requisiti di protezione per il piano d'azione di Contoso Pharmaceuticals comprendono quanto segue:

-   Implementazione e deimplementazione automatiche degli account utente.

-   Protocollo di autenticazione Kerberos versione 5.

-   Integrazione di GSS - API (Generic Security Services Application Programming Interface) e del protocollo Kerberos.

-   Autenticazione dei certificati client con crittografia.

-   Autenticazione delle password per Active Directory.

-   Autenticazione Microsoft Passport per Active Directory.

Al termine di ciascuna sezione sulle contromisure, un elenco riporta in dettaglio le vulnerabilità corrispondenti.

Oltre a implementare queste contromisure per la gestione di identità e accessi, Contoso ha adottato altre misure, fra le quali:

-   Implementazione di efficaci difese contro i virus, come elenchi di blocco indirizzi e filtri per gli allegati, nonché programmi antivirus per server e workstation.

-   Migliori procedure operative e criteri di formazione, concepiti per limitare il pericolo di un involontario utilizzo inappropriato del sistema.

-   Miglioramenti alla struttura fisica della rete e dei servizi, allo scopo di ridurre i pericoli meccanici, quali le interruzioni di alimentazione, i guasti hardware e il malfunzionamento della rete.

-   Piani di emergenza ben definiti in caso di disastri naturali come incendi, inondazioni e terremoti.

##### Implementazione e deimplementazione automatiche

Automatizzando l'implementazione e la deimplementazione degli account non soltanto si ottengono notevoli vantaggi in termini di produttività, ma si possono chiudere alle intrusioni numerosi punti deboli della protezione. Il più significativo è quando un dipendente abbandona la società e questa non ne disattiva l'account.

L'implementazione degli account può essere automatizzata in riferimento a un'origine autorevole sullo stato dei dipendenti e a un insieme noto di archivi di identità per le applicazioni, che gli amministratori possono gestire in modo centralizzato. Ad esempio, è possibile creare un'applicazione per le risorse umane allo scopo di generare una tabella degli stati dei dipendenti su base giornaliera. Quindi si può utilizzare un prodotto di integrazione identità per raggruppare gli stati dei dipendenti nell'applicazione per le risorse umane con gli stati delle identità digitali in archivi quali directory e applicazioni.

###### Considerazioni sulla distribuzione

Normalmente i prodotti per l'integrazione delle identità presentano una serie di elementi connettivi, o agenti di gestione, che creano un canale di comunicazione funzionale alla sincronizzazione delle informazioni sulle identità. Inoltre occorre una o più origini autorevoli per le identità digitali. Di solito le origini possono essere un sistema o un insieme di sistemi per le risorse umane, i database dei dipendenti temporanei, ecc., ma lo scenario varia, in certa misura, per ogni organizzazione.

###### Scenario relativo all'organizzazione Contoso

Contoso ha identificato la propria applicazione per le risorse umane come l'origine di informazioni autorevole per gli stati delle identità. La società ha scelto di distribuire un prodotto di implementazione e integrazione delle identità per gestire i dati corrispondenti in diversi archivi, come Active Directory, Lotus Notes Release 5 e Sun ONE Directory Server 5.1.

Quando l'applicazione per le risorse umane indica che occorre implementare un nuovo dipendente, il sistema aggiunge o attiva l'account corrispondente negli altri sistemi. Quando l'applicazione per le risorse umane notifica che un dipendente ha concluso il rapporto di lavoro con la società, il sistema rimuove o disattiva l'account corrispondente negli altri sistemi.

###### Problemi di protezione affrontati

Implementando un prodotto per l'integrazione delle identità è possibile affrontare problemi di protezione relativi all'implementazione o deimplementazione degli account.

Il documento "Aggregazione e sincronizzazione delle identità" in questa serie illustra come implementare Microsoft Identity Integration Server 2003, Enterprise Edition (MIIS 2003), un prodotto per l'integrazione delle identità che consente di implementare e deimplementare automaticamente gli account dei dipendenti.

##### Utilizzo del protocollo di autenticazione Kerberos versione 5

Il protocollo di autenticazione Kerberos versione 5, introdotto per le piattaforme Microsoft in Microsoft Windows 2000, offre molte caratteristiche di protezione auspicabili per un protocollo di autenticazione di rete. Il protocollo Kerberos versione 5 assicura un grado di protezione elevato, poiché si basa sulle tecnologie di crittografia e su una struttura intrinseca all'avanguardia. Il protocollo Kerberos inoltre garantisce superiori prestazioni, poiché si avvantaggia di una struttura di autenticazione centrale, il Centro distribuzione chiave (KDC, Key Distribution Center), di cui peraltro riesce a limitare il carico ricorrendo a ticket di durata relativamente prolungata.

###### Considerazioni sulla distribuzione

Nello scenario di Contoso, il KDC è dislocato in ciascun controller di dominio che esegue i servizi directory e di protezione Windows Server 2003. Dopo la configurazione, l'interoperabilità di Kerberos offre l'ulteriore vantaggio del Single Sign On (SSO) per i sistemi operativi basati su Windows ed eventualmente anche per i client UNIX.

###### Scenario relativo all'organizzazione Contoso

Gli amministratori di Contoso intendono configurare le workstation UNIX in modo che utilizzino il protocollo Kerberos versione 5 al fine di autenticare i controller di dominio Active Directory. Inoltre hanno deciso di configurare SAP R/3 affinché richieda l'autenticazione SNC (Secure Network Communications) in combinazione con il protocollo Kerberos versione 5.

###### Problemi di protezione affrontati

Implementare il protocollo di autenticazione Kerberos versione 5 contribuisce ad affrontare i problemi di protezione nelle aree seguenti:

-   Account delle workstation UNIX.

-   Autenticazione SAP.

-   Protezione dei dati delle applicazioni SAP.

Il documento "Gestione degli accessi a Intranet" in questa serie illustra l'implementazione del protocollo Kerberos versione 5, compreso come configurare l'autenticazione SNC in SAP R/3 e le workstation UNIX per eseguire l'autenticazione tramite Kerberos e Active Directory.

##### Utilizzo dell'integrazione di GSS-API e Kerberos con SAP

La versione 4.0 di SAP R/3 supporta SNC. Una modalità SNC consente l'integrazione con GSS-API e, tramite GSS-API, è possibile utilizzare il protocollo Kerberos versione 5.

Una modalità SNC permette l'integrazione con GSS-API, come illustrato in IETF RFC-2078. GSS-API garantisce la riservatezza e l'integrità dei dati, se utilizzata con un protocollo di protezione che supporta tali capacità. Kerberos versione 5 è un protocollo di questo tipo. Se si configurano il server di applicazioni SAP e il client dell'interfaccia utente grafica SAP in modo che utilizzino sia SAP SNC che il protocollo Kerberos versione 5, si garantisce la protezione completa dei dati delle applicazioni SAP da qualsiasi intercettazione.

###### Considerazioni sulla distribuzione

SAP R/3 non implementa il KDC, ma utilizza quello già installato nell'ambiente di rete. Nello scenario di Contoso, il KDC è dislocato su ciascun controller di dominio dotato di Windows 2000 Server o Windows Server 2003 con Active Directory. È necessario configurare SAP in modo che utilizzi il protocollo di autenticazione Kerberos versione 5. Tuttavia, dopo la configurazione, l'interoperabilità di Kerberos offre l'ulteriore vantaggio del Single Sign On nei sistemi operativi dei client basati su Windows e UNIX.

###### Scenario relativo all'organizzazione Contoso

Nello scenario di Contoso, gli amministratori hanno configurato SAP R/3 per l'utilizzo dell'autenticazione SNC e hanno implementato GSS - API con il protocollo Kerberos versione 5 per le workstation client basate su Windows, in modo da garantire la protezione dei dati delle applicazioni end-to-end.

###### Problemi di protezione affrontati

Implementare GSS-API e il protocollo Kerberos versione 5 contribuisce ad affrontare i problemi di protezione nelle aree seguenti:

-   Autenticazione SAP.

-   Protezione dei dati delle applicazioni SAP.

Il documento "Gestione degli accessi a Intranet" in questa serie illustra la configurazione del client SAP R/3 per l'utilizzo di SNC, al fine di integrare GSS-API e il protocollo Kerberos.

##### Utilizzo dell'autenticazione dei certificati client con la crittografia

TLS (Transport Layer Security) è la versione standard di SSL (Secure Sockets Layer) secondo IETF (Internet Engineering Task Force), sviluppata da Netscape Communications e descritta in IETF RFC – 2246. TLS è in grado di eseguire l'autenticazione dei client a chiave pubblica utilizzando un certificato digitale. Si tratta di una capacità molto potente poiché, dopo aver configurato un trust per l'infrastruttura a chiave pubblica (PKI, Public Key Infrastructure), per l'autenticazione è possibile utilizzare un certificato digitale x.509 e la chiave privata corrispondente, anziché password relativamente vulnerabili.

Per implementare questa soluzione, occorre creare un account shadow che rappresenti l'utente nell'insieme di strutture Active Directory esterno, gestito dai computer della rete perimetrale. Poiché questo account non utilizza mai la password per l'autenticazione, è possibile impostare una password particolarmente complessa, ad esempio formata da un valore casuale, generato per via crittografica, a 24 caratteri.

###### Considerazioni sulla distribuzione

L'account esterno è accessibile soltanto utilizzando un certificato X.509 valido, quindi è possibile che i dipendenti non abbiano accesso a un'importante applicazione aziendale se non accedono al certificato digitale X.509 e alla chiave privata corrispondente. In tal caso, l'organizzazione dovrebbe considerare se occorre concedere l'accesso temporaneo all'applicazione Extranet reimpostando la password dell'account (e comunicando la nuova password al dipendente) o creando un meccanismo in grado di emettere nuovi certificati attraverso l'Extranet o infine realizzando una connessione VPN (Virtual Private Network) alla rete interna.

Poiché i certificati dei client rendono le password superflue, devono essere protetti da appositi criteri per workstation.

###### Scenario relativo all'organizzazione Contoso

Gli architetti di Contoso hanno configurato l'applicazione per le vendite e i contatti in modo che richieda l'autenticazione dei certificati dei client e TLS. Ciò ha richiesto l'impostazione di un'autorità di certificazione e l'assegnazione di certificati al personale del reparto vendite.

###### Problemi di protezione affrontati

Implementare l'autenticazione dei certificati dei client basata sulla crittografia contribuisce ad affrontare problemi nelle aree seguenti:

-   Autenticazione con password in formato non crittografato.

-   Memorizzazione di password in formato non crittografato su server non protetti.

Il documento "Gestione degli accessi a Extranet" in questa serie illustra come configurare l'autenticazione dei certificati dei client basata sulla crittografia.

##### Autenticazione delle password per Active Directory

Active Directory consente di memorizzare informazioni molto riservate, quali le password degli account, in modo protetto. Nella maggior parte dei casi, le password non vengono memorizzate in modo da consentire l'identificazione della password originale. Active Directory utilizza hash crittografici (crittografia unidirezionale) della password, il che risulta sufficiente per l'autenticazione tramite i protocolli resi disponibili da Windows Server 2003. Gli stessi hash crittografici sono protetti con chiavi di crittografia accessibili solo al sistema operativo, per impedire ulteriormente la divulgazione di password molto riservate.

Active Directory offre inoltre i meccanismi per eseguire l'autenticazione basata su password in modo protetto. In altri termini, non è necessario inviare in rete informazioni sulla password non crittografate, tra il server delle applicazioni e l'archivio delle identità. Ad esempio, un meccanismo di autenticazione protetta è la connessione protetta tramite protocollo LDAP (Lightweight Directory Access Protocol) su SSL o TLS (LDAPS).

###### Considerazioni sulla distribuzione

Se per l'autenticazione si utilizza un altro archivio di account, di solito è necessario apportare una modifica al codice nell'applicazione. Le applicazioni che per l'autenticazione utilizzano una tabella di database devono essere aggiornate per Active Directory.

###### Scenario relativo all'organizzazione Contoso

Contoso ha aggiornato la propria applicazione per i partner di ricerca in modo da utilizzare Active Directory come archivio delle identità per gli account dei partner e come meccanismo per la gestione degli accessi.

###### Problemi di protezione affrontati

Implementare l'autenticazione delle password per Active Directory contribuisce ad affrontare i problemi di protezione nelle aree seguenti:

-   Autenticazione con password in formato non crittografato.

-   Memorizzazione di password in formato non crittografato su server non protetti.

Il documento "Sviluppo di applicazioni ASP.NET in grado di riconoscere le identità" in questa serie illustra come le applicazioni possano eseguire autenticazione e autorizzazione utilizzando Active Directory.

##### Autenticazione Microsoft Passport per Active Directory

Uno studio separato ha mostrato agli architetti di Contoso che i clienti trovano difficile gestire nomi utente e password per diversi siti Web. Secondo i risultati della ricerca, un mediatore di identità come Microsoft Passport potrebbe fornire l'autenticazione per i clienti che visitano il sito Web di Contoso, senza richiedere loro di mantenere un'identità aggiuntiva.

Questo approccio ha soddisfatto anche i requisiti di protezione dell'applicazione per i commenti sulle dimostrazioni offerte da Contoso, che hanno potuto eliminare completamente le password per gli account dei clienti. Gli utenti che visitano il sito Web di Contoso oggi vengono autenticati tramite la convalida di una credenziale Passport, seguita dalla mappatura dell'ID univoco Passport (PUID, Passport Unique ID) in riferimento a un account nell'insieme di strutture Active Directory esterno.

###### Considerazioni sulla distribuzione

Se per l'autenticazione si utilizza un servizio come Microsoft Passport, di solito è necessario apportare una modifica al codice nell'applicazione. Inoltre, per supportare autorizzazioni specifiche, è necessario implementare (in modo automatizzato) in Active Directory numerosi account Passport mappati, ricorrendo a un meccanismo scalabile e gestibile.

###### Scenario relativo all'organizzazione Contoso

Contoso ha riscritto la propria applicazione per la clientela, in modo da utilizzare Microsoft Passport e Active Directory come meccanismo di autenticazione e archivio di identità per gli account dei clienti.

###### Problemi di protezione affrontati

Implementare l'autenticazione Microsoft Passport per Active Directory risponde a quanto segue:

-   Autenticazione con password in formato non crittografato.

-   Memorizzazione di password in formato non crittografato su server non protetti.

Il documento "Gestione degli accessi a Extranet" in questa serie illustra come configurare l'autenticazione Microsoft Passport per Active Directory.

[](#mainsection)[Inizio pagina](#mainsection)

### Requisiti della piattaforma

I risultati dell'analisi sulle esigenze di protezione e aziendali di Contoso hanno identificato i requisiti che la piattaforma di gestione di identità e accessi deve soddisfare per la società. Le sezioni seguenti descrivono le aree chiave a cui deve rispondere la piattaforma.

#### Gestione degli accessi

I servizi di gestione accessi della piattaforma selezionata devono fornire servizi di autenticazione, autorizzazione e attendibilità in grado di soddisfare i requisiti seguenti:

-   I sistemi operativi client e server per le applicazioni client/server e i servizi di archiviazione e stampa devono interagire per garantire un'autenticazione sicura e fornire agli utenti un meccanismo SSO.

-   I diritti di autorizzazione generali devono derivare da informazioni globali sulle identità, benché tali dati possano essere globali solo in ambiti specifici, quali Intranet o la rete perimetrale.

-   L'infrastruttura deve implementare meccanismi di autorizzazione affidabili e gestibili.

-   La piattaforma deve offrire meccanismi flessibili per l'attendibilità, all'interno e all'esterno dell'organizzazione. I trust devono essere espliciti in una configurazione dell'infrastruttura a chiave pubblica o impliciti nei meccanismi del sistema operativo.

-   L'infrastruttura deve implementare meccanismi di configurazione dell'attendibilità sicuri e gestibili, in modo da integrare vari archivi di identità per l'acquisizione futura.

#### Servizi directory e di protezione

I servizi directory e di protezione della piattaforma selezionata devono supportare:

-   Memorizzazione protetta delle credenziali delle identità, in grado di interagire con meccanismi di autenticazione sicuri e standardizzati.

-   LDAP, per l'interoperabilità con applicazioni e servizi specifici.

-   Crittografia avanzata per le credenziali dell'utente e servizi che non devono distribuire all'esterno informazioni sulle credenziali (anche in formato crittografato).

-   Diversi tipi di credenziali per soddisfare i requisiti di numerosi protocolli di autenticazione, ad esempio Kerberos versione 5, biometrica, SSL e TLS.

-   Meccanismi di autenticazione basati su due fattori, compresi PKI e smart card (per la futura distribuzione).

-   Interoperabilità ottimizzata fra sistemi operativi client/server, tramite un insieme noto di protocolli di protezione e per applicazioni.

#### Gestione del ciclo di vita delle identità

Nella piattaforma selezionata, i servizi di gestione del ciclo di vita delle identità devono soddisfare i requisiti seguenti:

-   L'infrastruttura di gestione identità e accessi deve utilizzare un insieme comune di protocolli standardizzati per gestire gli archivi di identità dell'azienda.

-   Una singola directory deve fungere da archivio identità centralizzato per Intranet. Deve inoltre offrire servizi ridondanti, in caso di guasti hardware o della rete.

-   Una directory Extranet, isolata nella rete perimetrale, deve contenere gli account utente per clienti e partner.

#### Piattaforma delle applicazioni

La piattaforma selezionata deve supportare i requisiti delle applicazioni per Contoso:

-   Le applicazioni esistenti e pianificate devono utilizzare l'infrastruttura per le identità digitali, che devono risultare accessibili tramite protocolli comuni e standardizzati.

-   I server delle applicazioni devono essere dotati di supporto integrato per i protocolli di autenticazione avanzata quali Kerberos versione 5 e per l'autenticazione dei certificati dei client tramite SSL e TLS.

-   I server delle applicazioni devono essere in grado di implementare i metodi tradizionali di autorizzazione ACL (Access Control List) e controllo dell'accesso basato sui ruoli.

#### Controllo della protezione

La piattaforma selezionata deve supportare i requisiti di controllo della protezione di Contoso:

-   La piattaforma deve offrire capacità di controllo approfondito per tutte le operazioni di autenticazione, attendibilità, autorizzazione e configurazione.

-   La piattaforma deve esporre servizi di controllo gestibili ma specifici per tutti gli aspetti dell'infrastruttura del server e delle applicazioni.

[](#mainsection)[Inizio pagina](#mainsection)
