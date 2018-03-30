---
TOCTitle: 'Progettazione dell''infrastruttura di router e switch'
Title: 'Progettazione dell''infrastruttura di router e switch'
ms:assetid: '4abd06d7-48ff-4fe2-90a0-77093480a3d7'
ms:contentKeyID: 20200859
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536260(v=TechNet.10)'
---

Progettazione dell'infrastruttura di router e switch
====================================================

##### In questa pagina

[](#ezaa)[Argomenti del modulo](#ezaa)
[](#eyaa)[Obiettivi](#eyaa)
[](#exaa)[Ambito di applicazione](#exaa)
[](#ewaa)[Utilizzo del modulo](#ewaa)
[](#evaa)[Linee guida di progettazione](#evaa)
[](#euaa)[Definizioni delle periferiche](#euaa)
[](#etaa)[Classi](#etaa)
[](#esaa)[Classi di switch](#esaa)
[](#eraa)[Classe 1 - Switch fissi di fascia bassa](#eraa)
[](#eqaa)[Classe 2 - Switch flessibili di fascia bassa](#eqaa)
[](#epaa)[Classe 3 - Switch di fascia media](#epaa)
[](#eoaa)[Classe 4 - Switch di fascia alta](#eoaa)
[](#enaa)[Router](#enaa)
[](#emaa)[Classi di router](#emaa)
[](#elaa)[Classe 1 - Router software](#elaa)
[](#ekaa)[Classe 2 - Router fissi di fascia bassa](#ekaa)
[](#ejaa)[Classe 3 - Router flessibili di fascia bassa](#ejaa)
[](#eiaa)[Classe 4 - Router di fascia media](#eiaa)
[](#ehaa)[Classe 5 - Router di fascia alta](#ehaa)
[](#egaa)[Classe 6 - Router ISP](#egaa)
[](#efaa)[Protezione](#efaa)
[](#eeaa)[Considerazioni sulla protezione dei router](#eeaa)
[](#edaa)[Considerazioni sulla protezione degli switch](#edaa)
[](#ecaa)[Riepilogo delle caratteristiche di una rete protetta](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Argomenti del modulo

In questo modulo vengono presi in esame alcuni metodi per la selezione di switch e router. Al fine di agevolare la scelta vengono inoltre descritte le funzionalità disponibili in queste periferiche. Switch e router sono raggruppati in una serie di classi, ciascuna delle quali è determinata dall'insieme di funzionalità che di norma comprende. L'analisi delle diverse classi consente di stabilire qual è il tipo di switch e di router più adatto alla propria organizzazione. Gli switch e i router disponibili sono numerosi e dal momento che sono tutti dotati di funzionalità simili, operare una scelta corretta può risultare difficile. In questo modulo ne vengono identificate le principali funzionalità, a fronte delle esigenze cui sono in grado di rispondere. Viene inoltre affrontato il problema della protezione di router e switch e, in particolare, della loro configurazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Il modulo consente di:

-   Scegliere gli switch e i router più appropriati per una specifica organizzazione.

-   Identificare gli aspetti essenziali per la protezione di router e switch.

-   Proteggere le configurazioni di router e switch.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Le informazioni contenute in questo modulo sono valide per le seguenti tecnologie:

-   Switch Ethernet.

-   Router Ethernet e IP (Internet Protocol).

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

Scopo del modulo è semplificare la scelta degli switch e dei router più adatti a una specifica organizzazione. Viene pertanto fornito un elenco di controllo con l'indicazione e la spiegazione delle funzionalità disponibili che consentirà di identificare quelle più adatte al proprio caso specifico. Switch e router vengono quindi classificati in base alle funzionalità offerte da ciascun gruppo. È improbabile che un unico switch o router risponda perfettamente a tutti i requisiti di un'organizzazione ma se questi ultimi vengono analizzati a fronte delle classi disponibili sarà possibile individuare i migliori prodotti per ogni situazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Linee guida di progettazione

Nella presente sezione vengono presi in esame i requisiti relativi a router e switch nelle reti aziendali, i tipi di periferiche in grado di soddisfarli e le opzioni disponibili per la loro distribuzione. Router e switch sono due componenti cruciali della rete e una scelta corretta contribuisce a garantire sia la velocità e l'affidabilità del servizio offerto dalla rete che la capacità di adattarsi alla rapida evoluzione delle esigenze.

#### Elementi di progettazione

Per progettare l'implementazione di switch e router è necessario aver definito i seguenti elementi:

-   **Architettura di rete.**

-   **Protocolli di routing.**

-   **Disponibilità.**

#### Architettura di rete

Prima di determinare qual è la classe di router e switch più indicata, dove e con quali relazioni reciproche verranno posizionate le periferiche e di quali funzionalità dovranno essere dotate, è necessario progettare la rete. La scelta delle classi di router e switch presuppone che siano disponibili le informazioni elencate di seguito, relative alla struttura della rete:

1.  Il numero delle periferiche attualmente presenti nella rete, di quelle che si è in procinto di collegare e la crescita stimata per il futuro.

2.  Quali periferiche devono comunicare con quali altre.

3.  La larghezza di banda necessaria tra periferiche diverse che devono poter comunicare.

4.  In quali punti della struttura della rete è necessario prevedere uno switch piuttosto che un router.

5.  Se e quante VLAN (Virtual Local Area Network) sono previste, quali host ciascuna VLAN dovrà comprendere e se è prevista l'esecuzione di routing tra le VLAN.

6.  Qual è la latenza accettabile.

#### Struttura della rete

Esistono molte strutture organizzative e numerosi modi per progettare architetture di rete a partire da esse. Ma due sono i modelli più diffusi, che è possibile utilizzare come base per la progettazione: l'architettura di switch multilivello, che potrebbe essere applicata alla sede centrale di un'organizzazione, e l'architettura per piccole filiali.

Nella figura 1 è illustrato un esempio di architettura multilivello, che normalmente viene adottata in situazioni che prevedono un livello per il sito Web pubblico e uno relativo al database di backend. Procedendo dal lato pubblico della rete verso l'interno, il primo segmento consiste in una rete di confine con un router di confine verso Internet che fornisce una prima funzione di firewall. Segue uno switch che collega il router a un firewall perimetrale, più robusto del primo. Il firewall perimetrale si connette tramite uno switch ai server Web della rete perimetrale, che a loro volta si connettono tramite un altro switch a un firewall interno. Quest'ultimo si connette, sempre mediante uno switch, ai server interni e ai PC degli utenti della rete backend. In questa figura è illustrata una struttura logica ma tutti gli switch potrebbero fisicamente essere VLAN separate sullo stesso switch. È preferibile che lo switch di confine sia una periferica a parte, poiché si trova in una zona meno sicura. Le funzioni di commutazione backend possono anche essere svolte da più switch, a seconda che si preferisca disporre di un unico grande switch o di diversi switch più piccoli.

![](images/Dd536260.SGFG4001(it-it,TechNet.10).gif "Architettura di switch multilivello")

Figura 1
*Architettura di switch multilivello*

Nella figura 2 è illustrata un'architettura adatta a piccole filiali. Comprende tre periferiche di rete: un modem, un router e uno switch, che possono essere combinate in un'unica o in due periferiche, a seconda della connessione di rete. Spesso i router economici incorporano uno switch Ethernet e una funzione di firewall, mentre per la connessione a banda larga nel router può anche essere incorporato un modem.

![](images/Dd536260.SGFG4002(it-it,TechNet.10).gif "Architettura per piccole filiali")

Figura 2
*Architettura per piccole filiali*

#### Protocolli di routing

Nella progettazione della rete, una decisione importante riguarda la scelta dei protocolli di routing da utilizzare per lo scambio delle informazioni di routing. Per i router sono necessarie tabelle di routing in cui sia indicato come raggiungere le reti di destinazione. Le tabelle possono essere configurate manualmente come route statiche che però sono adatte solo per reti di piccole dimensioni. In alternativa è possibile utilizzare protocolli di routing e in questo caso le tabelle di routing vengono sviluppate mediante il rilevamento automatico delle altre reti. Un eventuale collegamento in errore viene rimosso automaticamente dalla tabella di routing, in modo che il router sia sempre aggiornato sulla migliore route attiva per una determinata rete di destinazione.

Nell'elenco che segue sono descritti i due principali protocolli di routing standard utilizzati per le reti, i protocolli RIP e OSPF, oltre a un protocollo speciale, BGP.

-   Protocollo RIP (Routing Information Protocol)
    Il protocollo RIP è progettato per consentire lo scambio di informazioni di routing in internetwork piccole e medie ed è disponibile su numerosi router.

    Il principale vantaggio del protocollo RIP risiede nell'estrema facilità di configurazione, cui tuttavia fanno riscontro diversi svantaggi di non poco conto: il RIP non è in grado di gestire reti di grandi dimensioni, genera un traffico ingente ed è lento a reagire ai guasti della rete (tempo di convergenza). Per queste ragioni, in genere viene preso in considerazione esclusivamente per piccole reti locali(LAN). Ulteriori informazioni sul protocollo RIP sono disponibili all'indirizzo: [RIP for IP (TechNet Library)](http://technet.microsoft.com/en-us/library/cc736472.aspx) (in inglese).

-   Protocollo OSPF (Open Shortest Path First)
    OSPF è un protocollo di routing standard molto efficiente e con un buon grado di scalabilità che lo rende adatto anche alle reti di grandi dimensioni. Presenta il vantaggio di non generare che un minimo sovraccarico della rete, anche nel caso di grandi internetwork e inoltre reagisce rapidamente ai guasti dei collegamenti. I principali svantaggi di questo protocollo risiedono, invece, nella sua complessità e nella maggiore difficoltà di configurazione e amministrazione.

    Oggi OSPF è il protocollo di routing più diffusamente adottato nelle reti aziendali per la sua maggiore efficienza rispetto al RIP. Di solito è disponibile nei router medi o grandi e talvolta anche in quelli più piccoli. Ulteriori informazioni sul protocollo OSPF sono disponibili all'indirizzo: [OSPF (TechNet Library)](http://technet.microsoft.com/en-us/library/cc778874.aspx) (in inglese).

-   Protocollo BGP (Border Gateway Protocol)
    Il protocollo BGP è un protocollo di routing del gateway esterno utilizzato nei router connessi a Internet per fornire sia la disponibilità del routing che funzionalità di bilanciamento del carico. In genere il protocollo BGP è disponibile solo nei router più grandi e per la sua configurazione è opportuno consultare il proprio ISP (Internet Service Provider).

#### Disponibilità

Le reti richiedono un'elevata disponibilità, in proporzione alle loro dimensioni. Per rispondere a questa esigenza, è possibile configurare e posizionare router e switch in diversi modi. Due sistemi sono, ad esempio, la duplicazione di componenti quali alimentatori e moduli delle periferiche di rete o la duplicazione delle periferiche stesse. Quest'ultimo approccio è notevolmente più costoso ma consente di realizzare una soluzione completamente flessibile.

[](#mainsection)[Inizio pagina](#mainsection)

### Definizioni delle periferiche

In questa sezione vengono definiti i seguenti tipi di periferiche di rete:

-   **Switch**

-   **Router**

Si tratta di elementi fondamentali della rete, in quanto forniscono il collegamento tra tutti i segmenti della rete locale e della WAN.

#### Switch

Gli switch servono a collegare i segmenti fisici di una rete e a consentire il trasferimento dei dati tra di essi. Operano al livello 2 del modello OSI e indirizzano il traffico in base all'indirizzo di livello 2, ad esempio MAC Ethernet. Alcuni switch forniscono anche funzioni aggiuntive, ad esempio VLAN e commutazione di livello 3.

La configurazione degli switch è automatica. Dall'ascolto del traffico su ciascuna porta Ethernet viene infatti rilevato a quale porta è connessa ciascuna delle periferiche collegate. Lo switch quindi invia il traffico direttamente alla porta di destinazione. A meno che non sia necessario attivare funzionalità aggiuntive, gli switch non richiedono alcuna configurazione: un aspetto decisamente vantaggioso quando si installa una rete. Il processo di commutazione viene eseguito nell'hardware alla velocità nominale e senza alcuna latenza.

In origine gli switch collegavano i segmenti a più periferiche ma, col passare del tempo e con la diminuzione dei prezzi, divenne normale collegare una singola periferica a ogni porta. Questa configurazione viene definita Ethernet "commutata", in opposizione a Ethernet "condivisa". Con un'unica periferica attiva per porta non è possibile che si verifichino collisioni, per cui le prestazioni della rete migliorano e le periferiche possono funzionare in modalità full duplex, raggiungendo una velocità effettiva più elevata.

Il traffico di rete include i messaggi broadcast, che devono essere copiati su ciascuna porta e quindi, in una rete di grandi dimensioni, producono un impatto significativo. Poiché in genere gli utenti comunicano con un gruppo limitato di server e periferiche collegate, il traffico broadcast potrebbe essere inviato solo all'interno di tale gruppo. Uno dei metodi per ridurre il traffico broadcast consiste nel fornire uno switch a ciascun gruppo e quindi collegarli tra loro mediante un router, che non trasmette messaggi broadcast. Un altro sistema è utilizzare VLAN sullo switch. Una VLAN consiste in un gruppo di periferiche configurate in modo da comunicare come se fossero collegate allo stesso cavo, mentre invece si trovano su segmenti fisici di LAN differenti. Un broadcast trasmesso da un membro della VLAN raggiunge soltanto gli altri membri della stessa VLAN, circoscrivendo di conseguenza la diffusione del traffico broadcast.

#### Router

I router operano al livello 3 del modello OSI. Provvedono al passaggio del traffico tra due diverse reti IP, che possono essere LAN o WAN. Il processo di routing è costituito dall'esame dell'indirizzo IP di destinazione dei dati in ingresso e dall'invio dei dati attraverso una porta di uscita, sulla base di una tabella di routing. Le tabelle di routing possono essere configurate manualmente o mediante il rilevamento automatico reso possibile dai protocolli di routing ma, diversamente dagli switch, i router richiedono sempre alcune operazioni di configurazione.

Gli switch più grandi possono includere un router, di solito in una scheda aggiuntiva. In questi casi, che spesso vengono definiti commutazione di livello 3, dal punto di vista funzionale si tratta di routing vero e proprio.

[](#mainsection)[Inizio pagina](#mainsection)

### Classi

Router e switch sono stati suddivisi in classi al fine di identificare i diversi livelli di periferiche disponibili e le funzionalità che forniscono. L'inclusione di un router o uno switch in una specifica classe indica che la periferica in questione è in grado di supportare tutte le funzionalità proprie di tale classe.

Le classi generali di router e di switch sono composte da numerose funzionalità principali. In particolare, la potenza di elaborazione è uno dei criteri più importanti, insieme al grado di aggiornabilità, flessibilità e adattabilità. Switch e router di fascia bassa sono di norma progettati per svolgere una specifica attività e, per contenerne il prezzo, presentano una capacità di espansione scarsa o limitata. Man mano che si passa alle classi di livello superiore si avrà a disposizione non solo più potenza ma anche una maggiore capacità di espansione. Le classi più alte forniscono anche adattabilità.

La scelta dello switch o del router più appropriato può risultare complessa, poiché ciascun produttore vanta per i suoi prodotti il migliore, più veloce, più economico insieme di funzionalità. Per valutare correttamente i prodotti è opportuno distinguere tra caratteristiche e vantaggi. Una caratteristica è qualcosa di cui un prodotto è dotato o che esso è in grado di fare ma diventa un vantaggio solo se è utile a chi lo acquista. La capacità di connettersi a cavi in fibra ottica, ad esempio, oltre che a quelli in rame, rappresenta un vantaggio in un grande centro dati in cui ogni switch è connesso a un altro ma non avrebbe alcuna utilità in un piccolo ufficio con un unico switch.

La scelta di uno switch o un router deve essere preceduta dalla progettazione della rete e orientata di conseguenza. Probabilmente le strutture proponibili saranno più di una e occorrerà valutare le diverse architetture. Il prezzo di acquisto è certamente un criterio rilevante, ma devono essere considerati anche i costi di esercizio, poiché una periferica economica può presentare costi operativi elevati.

Per una grande organizzazione, una decisione di sostanziale importanza nella progettazione della rete riguarda l'opportunità di avere più switch o pochi grandi switch nella sede centrale. Quest'ultima è di solito l'opzione preferibile ma in parte dipende dalla disposizione fisica degli uffici. Molti piccoli switch possono comportare problemi di gestibilità ma gli switch più grandi possono richiedere VLAN ed essere più complessi da configurare.

#### Funzionalità comuni di switch e router

Di seguito sono elencate le funzionalità più comuni di switch e router e ogni funzionalità viene spiegata e valutata. L'elenco permette di controllare la rispondenza delle singole funzionalità alle esigenze specifiche di un'azienda. Ad esempio, la maggior parte delle aziende ha una grande sede centrale e molti piccoli uffici distaccati. Per la sede principale saranno probabilmente necessarie funzionalità quali adattabilità e scalabilità, mentre per i piccoli, ma numerosi, uffici l'economicità sarà un requisito auspicabile.

L'elenco qui fornito illustra le funzionalità comuni a switch e router, seguite da quelle specifiche degli uni o degli altri.

-   Scalabilità
    La possibilità di aggiungere porte Ethernet è in genere molto utile, specie negli switch delle sedi più estese, poiché il numero degli utenti e dei server può aumentare. Non è consigliabile installare uno switch che non sarà in grado di sostenere la crescita futura e dovrà quindi essere eliminato e sostituito. Gli switch sono tendenzialmente di tre tipi:

    -   A configurazione fissa, con un numero di porte Ethernet determinato.

    -   Flessibili, in cui è possibile aggiungere schede aggiuntive per incrementare il numero di porte.

    -   Completamente aggiornabili, in genere con un telaio vuoto e una buona espandibilità.

    L'espandibilità è una caratteristica utile anche nei router ma spesso non così essenziale come negli switch. Ciò che frequentemente si modifica nei router sono i collegamenti WAN o perché cambia la tecnologia WAN, ad esempio da ISDN a ADSL, o perché vengono implementati collegamenti WAN aggiuntivi.

    Sebbene la capacità di espansione sia sempre una caratteristica positiva, essa implica dei costi e, nel caso di filiali, router o switch a configurazione fissa possono essere i prodotti più validi.

<!-- -->

-   Supporto Ethernet ad alta velocità
    Oggi la velocità normale di una rete Ethernet è di 100 Mbps, rispetto agli originali 10 Mbps. Il costo della tecnologia Gigabit Ethernet sta diminuendo drasticamente, ma in genere il suo utilizzo è limitato si server e ai collegamenti backbone tra switch, perché le PC card sono ancora costose. Sta inoltre emergendo la tecnologia 10 Gbps Ethernet, che presumibilmente sostituirà la Gigabit Ethernet per i principali collegamenti backbone, non appena il suo costo scenderà. Tutti gli switch e i router dovrebbero supportare 100 Mbps Ethernet, mentre in genere solo i modelli di fascia medio-alta supportano velocità superiori.

<!-- -->

-   Adattabilità
    L'eventuale guasto di un componente dello switch o del router può bloccare l'intera unità, a meno che questa sia progettata con una struttura ridondante che le permetta di continuare a funzionare. Gli switch e i router di livello più alto possono includere componenti duplicati quali alimentatori, moduli e infrastrutture di commutazione, per impedire che un guasto pregiudichi il funzionamento generale. In una periferica di grandi dimensioni, dotata di numerose connessioni, questa è una caratteristica estremamente utile. In uno switch o in un router più piccolo, invece, il costo aggiuntivo può non essere giustificato. In alternativa è possibile prevedere il funzionamento parallelo di due switch o router, uno attivo e l'altro in hot standby, pronto a subentrare al primo nell'eventualità di un guasto. Il passaggio potrebbe essere gestito automaticamente mediante un apposito meccanismo.

<!-- -->

-   Gestibilità
    Gli switch cominciano a funzionare senza richiedere alcuna configurazione e "apprendono" la topologia della rete rilevando su quali porte sono collocate le singole periferiche mediante l'ascolto delle trasmissioni dei frame Ethernet. Tutti gli switch sono in grado di eseguire questa operazione, ma l'accesso alle periferiche è comunque necessario a scopo di monitoraggio o per ulteriori attività di configurazione. Gli switch di fascia più bassa non sono dotati di opzioni di configurazione, ma via via che si sale di livello aumentano anche le esigenze di configurazione, in proporzione alle funzionalità disponibili e proprio perché queste ultime possano essere utilizzate al meglio.

    Tutti i router, invece, devono essere configurati per definire gli indirizzi IP delle porte e il metodo da utilizzare per la costruzione delle tabelle di routing.

    La configurazione e la gestione delle periferiche richiedono l'accesso remoto dalla rete, che può ridurre sensibilmente i costi di gestione consentendo di risolvere eventuali problemi a distanza. Inoltre, mediante un software per la gestione della rete è possibile monitorare le periferiche e ottenere report automatici sugli errori.

<!-- -->

-   VoIP (Voice over IP)
    Voice over IP è la capacità di trasmettere conversazioni vocali sulla rete locale Ethernet o anche sulla WAN. Il vantaggio immediato è la riduzione dei cablaggi, poiché la voce condivide il cavo Ethernet con i dati e non richiede una rete con cavi telefonici separata, ma il beneficio più a lungo termine è rappresentato dalla maggiore flessibilità nella dislocazione di personale e apparecchiature. Il PBX tradizionale viene di solito sostituito da un PBX IP basato su una piattaforma PC standard invece che su hardware proprietario.

    Per un centro dati già munito di una rete telefonica, VoIP può non rappresentare un'esigenza a breve termine, ma potrà servire in futuro, con l'espandersi dell'organizzazione e l'evolversi delle esigenze. Per essere idonei a gestire VoIP, gli switch e i router devono presentare due caratteristiche:

    -   Supporto dello standard IEEE 802.1p, QoS (Quality of Service)
        Consente allo switch di assegnare priorità al traffico vocale e di dati, in modo che al primo sia riservata la precedenza nell'invio.

    <!-- -->

    -   Supporto dello standard IEEE 802.3af, alimentazione in linea per i telefoni IP
        Consente agli switch di fornire corrente a bassa tensione sui cavi Ethernet UTP di categoria 5 per alimentare i telefoni IP.

<!-- -->

-   Protezione
    La protezione è un requisito sempre più significativo in tutti i componenti della rete. L'argomento verrà discusso in dettaglio più avanti nel modulo ma nella valutazione di switch e router è necessario tener conto della presenza di funzionalità specifiche che siano in grado di semplificare l'implementazione della protezione.

    Gli aspetti della protezione coinvolti sono due: il primo è relativo alle intrusioni sulla rete, che la periferica può essere in grado di limitare, e il secondo concerne le intrusioni mirate alla periferica stessa. Anche la prima categoria può essere orientata alle periferiche. In questo senso è necessario considerare se la periferica, in particolare nel caso dei router, è dotata di funzionalità di firewall. Nella seconda categoria rientrano gli attacchi mirati alla configurazione della periferica. Per evitarli, va considerata la possibilità di implementare controlli aggiuntivi per circoscrivere il numero degli utenti autorizzati ad accedere alla configurazione.

    Di solito gli switch a basso costo non possono essere configurati e non hanno indirizzi IP, per cui sono relativamente immuni dagli attacchi che partono dalla rete. I router e gli switch più grandi sono in genere dotati di sofisticati meccanismi di controllo degli accessi e inoltre possono essere configurati in modo da limitare le intrusioni. Switch e router di fascia media sono probabilmente i più vulnerabili ma un buon sistema di firewall è sufficiente a eliminare le intrusioni dall'esterno.

    Infine, è possibile che le periferiche prevedano il supporto di VLAN e consentano di ottenere una migliore protezione limitando l'accesso degli utenti ai relativi server.

<!-- -->

-   Supporto tecnico
    In una rete di grandi dimensioni il supporto tecnico fornito dal produttore è estremamente importante. In genere, sarà commisurato al costo della periferica. Per le periferiche più economiche normalmente sarà previsto supporto tecnico solo tramite posta elettronica, senza tempi di risposta garantiti. Le periferiche più costose saranno presumibilmente anche più complesse, per cui può essere opportuno stipulare un contratto di assistenza. Acquistando tutti gli switch e i router dallo stesso produttore è possibile ridurre i problemi che tipicamente insorgono quando ciascuno dei produttori di periferiche che interagiscono attribuisce all'altro le cause delle difficoltà sperimentate dall'utente.

<!-- -->

-   Gamma di prodotti e "longevità" del produttore
    Può accadere che un'azienda fornisca il miglior switch o router di una determinata classe, ma che non ne produca affatto di altre classi. Al livello dei piccoli uffici, ad esempio, numerose aziende propongono prodotti validi a prezzi molto competitivi, ma in genere non offrono alcun prodotto adatto a una grande organizzazione. Altri aspetti di cui tener conto sono la longevità del produttore e il livello di assistenza che è in grado di fornire in caso di problemi. La concorrenza è spietata e molte piccole aziende potrebbero essere destinate a non sopravvivere.

<!-- -->

-   Costo
    Inevitabilmente il costo di acquisto è un fattore importante nella scelta di una periferica ma non va trascurato neppure il costo di esercizio. Spesso gli switch vengono classificati in base al prezzo per porta, che si calcola dividendo il costo totale dello switch per il numero di porte Ethernet che offre. Questa valutazione può essere utile soltanto per confrontare switch della stessa classe, poiché non tiene conto del fatto che le funzionalità aumentano man mano che si sale di livello. Gli switch più semplici, ad esempio, offrono probabilmente il miglior prezzo per porta ma sono anche quelli dotati del minor numero di funzionalità. Il metodo di raffronto dei costi descritto non è applicabile ai router, che è invece opportuno valutare in base alle prestazioni e alla flessibilità. Si può essere tentati di scegliere semplicemente la periferica dal prezzo più competitivo per una data classe. Ma è necessario tener conto anche dei costi di esercizio e di manutenzione, ad esempio confrontando i costi da sostenere per addestrare il personale sui metodi di configurazione nel caso dei diversi produttori.

<!-- -->

-   Prestazioni
    La potenza di elaborazione e le prestazioni di un router o switch sono più difficili da valutare rispetto a quelle di un computer, per il quale è possibile utilizzare la potenza della CPU come punto di partenza. Router e switch sono di solito basati sull'hardware proprietario del produttore e, sebbene contengano una CPU, essa non fornisce un'indicazione accurata della potenza complessiva. Le prestazioni degli switch si misurano sia in numero di bit al secondo(bps) che in pacchetti al secondo (pps), mentre per le prestazioni dei router si utilizza in genere soltanto questo secondo parametro. Spesso i produttori di router e switch non dichiarano le prestazioni dei propri prodotti. Non esiste, inoltre, uno standard di settore per la misurazione delle prestazioni, cosa che rende difficile operare confronti diretti. Anche i produttori di piccoli router tendono a non rivelare i dati sulle prestazioni.

#### Funzionalità specifiche degli switch

In questa sezione sono evidenziate le funzionalità proprie degli switch.

-   Protocollo Spanning Tree
    Il protocollo Spanning Tree viene utilizzato per calcolare il percorso migliore tra gli switch, laddove la rete presenti più switch e percorsi. L'operazione è necessaria per evitare che i dati vengano inviati su più percorsi contemporaneamente, con una conseguente duplicazione dei dati. Nelle reti molto estese è essenziale che gli switch supportino questo protocollo, che spesso non è invece disponibile negli switch più piccoli.

-   Supporto VLAN
    Le VLAN hanno la funzione di segmentare la rete in gruppi di computer con requisiti di comunicazione analoghi, riducendo in tal modo il traffico di rete. Possono essere impiegate in reti di qualsiasi dimensione, ma sono particolarmente utili nei casi in cui sono installati pochi switch molto grandi. Normalmente le VLAN non sono supportate negli switch a basso costo. Per una piccola rete si tratta di un aspetto irrilevante ma per le reti più estese il supporto delle VLAN è essenziale.

-   Connettività uplink
    Gli uplink vengono utilizzati per connettere reciprocamente gli switch della rete. Sebbene sia possibile connettere tutti gli switch mediante i normali collegamenti Ethernet, quelli di classe più alta supportano collegamenti a velocità maggiori con protocolli di trunking destinati specificamente alla connessione tra switch.

-   Consolidamento
    L'integrazione di altre funzioni all'interno dello switch può consentire di ridurre i costi e migliorare la gestibilità. Gli switch a basso costo destinati a piccole filiali, ad esempio, possono includere anche un router e un firewall, e a volte perfino un modem a banda larga. Oltre a ridurre i costi, questa possibilità semplifica anche la gestione, perché l'unità fisica è soltanto una. Anche gli switch di fascia alta possono includere un modulo router, caratteristica che viene definita commutazione di livello 3, nonché altre funzioni quali bilanciamento del carico e un firewall. Anche in questo caso, la gestione della rete risulta semplificata. L'opportunità del consolidamento deve essere valutata attentamente, poiché può comportare una riduzione dell'adattabilità, dal momento che un guasto totale della periferica implicherà l'indisponibilità di tutti i servizi consolidati.

[](#mainsection)[Inizio pagina](#mainsection)

### Classi di switch

In questa sezione vengono definite diverse classi di switch. Le classi non sono rigide e uno specifico modello prodotto da un'azienda può rientrare in più classi in funzione delle opzioni di aggiornamento che prevede, mentre due diversi modelli dello stesso produttore possono appartenere alla stessa classe. Le classi di switch trattate nella presente sezione sono le seguenti:

-   **Classe 1 - Switch fissi di fascia bassa**

-   **Classe 2 - Switch flessibili di fascia bassa**

-   **Classe 3 - Switch di fascia media**

-   **Classe 4 - Switch di fascia alta**

[](#mainsection)[Inizio pagina](#mainsection)

### Classe 1 - Switch fissi di fascia bassa

Gli switch di fascia bassa sono dotati di scarse funzionalità e capacità di espansione, oltre a non presentare alcuna tolleranza d'errore. Questa classe di switch è progettata per un numero fisso di porte Ethernet, di solito da 4 a 24, e alle limitazioni della connettività corrispondono prestazioni limitate.

Si tratta di switch economici, che mancano però di aggiornabilità e flessibilità. La connettività Ethernet è incorporata nell'hardware e le funzionalità delle periferiche, ad esempio il numero delle porte, non possono essere modificate con l'evolversi delle esigenze. Gli switch di fascia bassa sono progettati per funzionare in modo indipendente, senza coordinare il traffico con gli altri switch. Non sono in grado di supportare funzionalità quali il protocollo Spanning Tree, la gestione remota, gli uplink ad alta velocità e le VLAN. Gli uplink verso altri switch possono in genere essere supportati alle velocità Ethernet standard, tramite una porta speciale o un cavo Ethernet crossover. La funzione di switch può anche essere associata a un router.

In genere gli switch di questo tipo sono adatti a piccoli uffici, uffici di filiale di grandi aziende e utenti privati. Le carenti funzioni di gestione non hanno alcuna conseguenza per le piccole aziende e i privati ma rappresentano un punto debole significativo per le filiali di una grande azienda. Nella tabella 1 sono riepilogate le caratteristiche degli switch di Classe 1.

**Tabella 1: Classe 1 - Switch fissi di fascia bassa**

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Nessuna attività di configurazione richiesta o consentita</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nessuna possibilità di espansione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto del protocollo Spanning Tree normalmente non previsto</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporto VLAN non previsto</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nessuna possibilità di gestione remota</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporto tecnico limitato da parte del produttore</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VoIP non previsto</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Costo - Basso</td>
</tr>
</tbody>
</table>
  
#### Vantaggi
  
I vantaggi offerti dagli switch fissi di fascia bassa includono:
  
-   Economicità  
    In genere si tratta di periferiche economiche, perché semplici sia nella costruzione che quanto a funzionalità; la disponibilità di numerosi prodotti concorrenti contribuisce a contenere ulteriormente i prezzi. Nelle situazioni in cui è possibile ignorarne le carenze, offrono la maggiore convenienza, in termini di prezzo per porta, tra tutte le classi di switch.
  
-   Semplicità di configurazione  
    Di solito queste periferiche non prevedono alcuna opzione di configurazione e sono molto semplici da installare. Il rilevamento dell'ambiente di rete e la configurazione dello switch avvengono automaticamente. Nelle installazioni in sedi remote l'assenza di opzioni è un vantaggio perché rende impossibile qualsiasi alterazione della configurazione.
  
#### Svantaggi
  
Gli svantaggi degli switch fissi di fascia bassa includono:
  
-   Impossibilità di aggiornamento  
    Come conseguenza del basso costo di costruzione, queste periferiche non prevedono alcuna possibilità di aggiornamento, ad esempio per aggiungere porte Ethernet.
  
-   Nessuna opzione di configurazione e gestione  
    Queste periferiche non sono dotate di opzioni configurabili né di un programma di configurazione che consenta di eseguire gestione e monitoraggio remoti. Di solito le periferiche di questo tipo vengono installate in piccole sedi remote prive di supporto tecnico locale, per cui la mancanza di funzioni di monitoraggio può rappresentare una seria lacuna. Un'ulteriore conseguenza dell'assenza di opzioni di configurazione è che gli switch di questa classe non supportano il protocollo Spanning Tree né le VLAN e pertanto non si prestano a essere utilizzati per le reti delle sedi centrali di grandi aziende.
  
-   Supporto limitato  
    Per questa classe di router il supporto è in genere limitato e viene fornito attraverso siti Web, elenchi di domande frequenti e posta elettronica, senza livelli di servizio garantiti. La concorrenza è agguerrita, il ciclo di vita dei prodotti è breve e i modelli vengono sostituiti frequentemente, con il risultato che per i prodotti divenuti obsoleti il supporto tende a scemare. Le garanzie sono limitate alla sostituzione, entro tempi non specificamente assicurati. Se una periferica non più in garanzia si guasta non è conveniente farla riparare. Data la semplicità e l'economicità delle periferiche, il livello di supporto descritto può essere considerato accettabile.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 2 - Switch flessibili di fascia bassa
  
Gli switch flessibili di fascia bassa offrono funzionalità simili a quelli fissi, con in più la possibilità di aggiornare l'hardware se necessario. In genere è possibile incrementare il numero di porte Ethernet (maggiore che negli switch fissi), la flessibilità relativa agli uplink è maggiore (spesso fino a Gigabit Ethernet) ed è previsto il supporto del protocollo Spanning Tree. Normalmente questi switch forniscono un throughput più elevato per il traffico Ethernet rispetto a quelli fissi, poiché devono supportare un maggior numero di porte. Rispetto agli switch fissi di fascia bassa sono anche più costosi, in quanto aggiornabili e spesso dotati di funzioni di gestione remota e del supporto VLAN. Anche gli switch impilabili a configurazione fissa possono essere considerati appartenenti a questa classe, poiché dal punto di vista tecnico offrono le stesse funzionalità. L'espansione consiste però nell'affiancare nuovi switch a quelli esistenti: tutti gli switch vengono quindi connessi mediante bus ad alta velocità e agiscono come un unica periferica. Per il termine impilabile non esiste una definizione standard. Nel caso di alcuni produttori può indicare materialmente che gli switch possono essere sovrapposti, ma agli effetti dell'inclusione in questa classe presuppone la presenza di un bus ad alta velocità tra due switch, che verranno gestiti come un'unica periferica.
  
Gli switch flessibili di fascia bassa si prestano a essere utilizzati nelle situazioni in cui è prevista una crescita o quando uno switch fisso non fornirebbe un numero di porte sufficiente, ad esempio per interi piani di edifici, reparti, uffici di filiali remote o piccole organizzazioni. Il costo iniziale è maggiore rispetto agli switch fissi ma a lungo termine sarà possibile gestire la crescita delle esigenze senza dover sostituire la periferica. In genere gli switch flessibili di fascia bassa offrono un potenziale di connettività maggiore rispetto a quelli fissi, per cui possono essere utilizzati in uffici più grandi. Nella tabella 2 sono riepilogate le caratteristiche degli switch di Classe 2.
  
**Tabella 2: Classe 2 - Switch flessibili di fascia bassa**

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Aggiornabilità delle porte Ethernet</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Flessibilità delle porte di uplink</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Possibilità di aggiornamento a un maggior numero di porte Ethernet rispetto agli switch di Classe 1</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Protocollo Spanning Tree</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Configurabilità, gestibilità e accesso remoto</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Raramente, supporto VoIP</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VLAN</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Costo - Variabile, da basso a elevato</td>
</tr>
</tbody>
</table>
  
#### Vantaggi
  
I vantaggi offerti dagli switch flessibili di fascia bassa includono:
  
-   Economicità  
    Sebbene abbiano un costo per porta più elevato rispetto agli switch di Classe 1, offrono migliori funzionalità di gestione e possibilità di espansione, e restano pur sempre economici rispetto alle periferiche delle classi superiori.
  
-   Aggiornabilità  
    Sono previsti metodi per incrementare il numero di porte Ethernet, mediante l'aggiunta di porte all'unità base o il collegamento di unità aggiuntive a quella esistente, con una connessione diretta al bus interno. Le porte di uplink utilizzate per la connessione ad altri switch sono compatibili con diversi supporti per la connettività, da Gigabit Ethernet alle fibre ottiche, al rame.
  
-   Possibilità di configurazione  
    Gli switch di questo tipo supportano la configurazione del protocollo Spanning Tree e di VLAN, caratteristica che li rende idonei a essere utilizzati nelle reti aziendali. Inoltre, supportano la gestione e il monitoraggio remoti.
  
#### Svantaggi
  
Gli svantaggi degli switch flessibili di fascia bassa includono:
  
-   Aggiornabilità non flessibile  
    Di solito con queste periferiche la possibilità di aumentare le porte Ethernet è limitata, così come le possibili modifiche alle funzionalità delle porte di uplink. Con l'aggiunta di un'altra unità, inoltre, le porte disponibili aumentano considerevolmente, anche quando sarebbe sufficiente un piccolo incremento. Normalmente non sono previste opzioni per l'aggiunta di altre funzionalità, ad esempio la commutazione di livello 3.
  
-   Supporto VoIP raramente previsto  
    Anche nei casi in cui non rappresenta un requisito immediato, il supporto VoIP potrebbe diventare indispensabile se l'organizzazione decidesse di aggiornare la rete telefonica.
  
-   Adattabilità scarsa o limitata  
    Di solito questi switch presentano una scarsa adattabilità, che nella maggior parte dei casi sarà rappresentata da un alimentatore ridondante.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 3 - Switch di fascia media
  
Gli switch di fascia media sono più potenti e offrono una densità di porte e una capacità di espansione molto maggiori rispetto alle periferiche di Classe 2. Presentano inoltre un livello più elevato di gestibilità, ridondanza e adattabilità. In genere hanno un telaio modulare invece che fisso, con schede plug-in per le porte. Spesso sono disponibili telai di diverse dimensioni e con un numero di slot variabile. In genere queste periferiche includono più alimentatori ridondanti sostituibili a caldo, mentre le funzioni di adattabilità comprendono protocolli che consentono di gestire il passaggio a uno switch alternativo. Talvolta è anche disponibile un secondo modulo di gestione: si tratta dell'unità processore dello switch che fornisce adattabilità in caso di guasto.
  
Gli switch di questa classe possono essere utilizzati per provvedere alle funzioni di commutazione essenziali in organizzazioni di medie dimensioni, nelle filiali più estese o per aggregare divisioni di una grande azienda per la connessione a uno switch più grande. Questi router offrono una considerevole flessibilità e capacità di crescita per la connettività di reti WAN e LAN e tendenzialmente durano a lungo perché possono essere aggiornati per supportare nuove tecnologie. Nella tabella 3 sono riepilogate le caratteristiche degli switch di Classe 3.
  
**Tabella 3: Classe 3 - Switch di fascia media**

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Unità in telaio, con telai di diverse dimensioni</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Alimentatori ridondanti</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Elevata densità di porte Ethernet</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Porte di uplink flessibili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Configurabilità, gestibilità e accesso remoto</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Protocollo Spanning Tree</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VLAN</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporto VoIP</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Commutazione livello 3</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Alimentatore ridondante</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Modulo di gestione ridondante</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Costo - Elevato</td>
</tr>
</tbody>
</table>
  
#### Vantaggi
  
I vantaggi degli switch di fascia media includono:
  
-   Rapporto prezzo/prestazioni favorevole  
    Sebbene il prezzo dell'unità base degli switch di fascia media sia più alto rispetto alle periferiche di fascia bassa, il prezzo per porta si riduce considerevolmente per la possibilità di aumentare il numero di porte. Ciò è particolarmente vero per le unità dotate di telai più grandi.
  
-   Semplicità di configurazione  
    Le periferiche di questa classe sono dotate di funzionalità più complesse, ad esempio le VLAN, che richiedono configurazione. In genere presentano a questo scopo un'interfaccia grafica basata su browser oltre alla tradizionale riga di comando. Gli stessi strumenti possono essere utilizzati anche per la gestione e il monitoraggio remoti.
  
-   Gestibilità  
    La classe di switch in esame offre eccellenti funzionalità di gestione, grazie a strumenti software ottimizzati e a specifiche caratteristiche hardware.
  
-   Adattabilità  
    Man mano che aumenta il numero delle porte, il requisito dell'adattabilità diventa più critico e questa classe di switch è in grado di fornire un alimentatore e un modulo di gestione ridondanti opzionali.
  
-   Scalabilità e ciclo di vita esteso  
    Poiché questi switch sono basati su telai, tutte le opzioni di connettività sono costituite da schede plug-in. Ciò significa che l'unità può essere facilmente aggiornata via via che le esigenze si evolvono o che il costo di nuove tecnologie diviene accessibile. Di conseguenza, questi switch sono più longevi rispetto a quelli di fascia più bassa, che presto si è costretti a sostituire.
  
#### Svantaggi
  
Gli svantaggi degli switch di fascia media includono:
  
-   Costo più elevato  
    Il costo di base di queste periferiche è più elevato rispetto alle classi di livello inferiore, anche se la maggiore densità delle porte le rende più convenienti, specie se dotate di telai di grandi dimensioni.
  
-   Configurazione complessa  
    Il maggior numero di opzioni rende più complicata la configurazione, sebbene la difficoltà sia mitigata dagli strumenti con interfaccia grafica.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 4 - Switch di fascia alta
  
Gli switch di fascia alta offrono alte prestazioni, maggiore possibilità di espansione, eccellente tolleranza d'errore ed elevata disponibilità. La struttura dell'hardware è estremamente flessibile e fornisce numerose opzioni di connettività insieme ad altre caratteristiche, quali alimentatori e processori ridondanti che rendono il sistema altamente adattabile.
  
In queste periferiche hanno un ruolo importante i protocolli ad alta velocità come ATM (Asynchronous Transfer Mode), per il collegamento ad altre periferiche di rete. Gli switch di questa classe sono estremamente versatili quanto a compatibilità con i supporti hardware, ad esempio rame e fibra ottica, e sono sufficientemente potenti da gestire più collegamenti Gigabit Ethernet. Possono inoltre contenere un modulo che li abilita a fungere anche da router. Questa possibilità è particolarmente utile per il collegamento di VLAN. Nella tabella 4 sono riepilogate le caratteristiche degli switch di Classe 4.
  
**Tabella 4: Classe 4 - Switch di fascia alta**

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Unità con telaio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Alimentatori ridondanti</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Elevata densità di porte Ethernet</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Porte di uplink flessibili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto 10 Gigabit Ethernet</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configurabilità, gestibilità e accesso remoto</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protocollo Spanning Tree</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporto VLAN</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VoIP</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Commutazione livello 3</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Commutazione livello 4-7</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Funzionalità di protezione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Alimentatore ridondante</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modulo di gestione ridondante</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Costo - Elevato</td>
</tr>
</tbody>
</table>
  
#### Vantaggi
  
I vantaggi degli switch di fascia alta includono:
  
-   Rapporto prezzo/prestazioni favorevole  
    Come gli switch di Classe 3, anche questi hanno un prezzo di base elevato. Ma quando l'unità viene espansa e la densità delle porte aumenta, il costo per porta si riduce considerevolmente.
  
-   Gestibilità  
    Come la Classe 3, anche quella in esame offre eccellenti funzionalità di gestione grazie a strumenti software ottimizzati e a specifiche caratteristiche hardware.
  
-   Adattabilità  
    Man mano che aumenta il numero delle porte, il requisito dell'adattabilità diventa più critico. Gli switch di questa classe forniscono funzionalità avanzate per l'adattabilità, tra cui alimentatori ridondanti e sostituibili a caldo, moduli di gestione e infrastrutture di commutazione ridondanti.
  
-   Scalabilità e ciclo di vita esteso  
    Poiché questi switch sono basati su telai, tutte le opzioni di connettività sono costituite da schede plug-in. Ciò significa che l'unità può essere facilmente aggiornata via via che le esigenze si evolvono o che il costo di nuove tecnologie diviene accessibile. Di conseguenza, questi switch sono più longevi rispetto a quelli di fascia più bassa, che presto si è costretti a sostituire.
  
-   Protezione  
    Questa classe di switch di solito offre funzionalità avanzate per proteggere la rete da intrusioni.
  
-   Commutazione di livello 3-7  
    Per questa classe è prevista la commutazione di livello 3 (routing) opzionale. Possono anche essere disponibili altre funzionalità avanzate, quali commutazione di livello 4-7, bilanciamento del carico e firewall. Se disponibili come servizi incorporati, queste funzionalità risultano meno costose rispetto alle soluzioni con unità esterne e consentono di ottenere prestazioni migliori.
  
#### Svantaggi
  
Gli svantaggi degli switch di fascia alta includono:
  
-   Costo iniziale elevato  
    Il costo iniziale di queste unità basate su telaio è alto, perché include il costo di componenti quali il telaio, il modulo di gestione e l'alimentatore. Il prezzo per porta è proporzionale al numero di porte: è particolarmente alto per i telai che ne hanno meno ma si riduce con l'aumentare della densità.
  
-   Configurazione complessa  
    Le funzionalità aggiuntive comportano inevitabilmente una maggiore difficoltà di configurazione. La configurazione degli switch appartenenti a questa classe deve essere affidata a tecnici esperti.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Router
  
Per eseguire le diverse attività richieste dalla rete possono essere necessari numerosi router appartenenti a classi differenti, ad esempio quelli di confine verso Internet, i router interni che collegano le VLAN e quelli per piccoli uffici.
  
#### Funzionalità specifiche dei router
  
In questa sezione sono illustrate le funzionalità proprie dei router.
  
-   Protocolli di routing  
    Per i router di campus dovrebbe essere disponibile una gamma di protocolli di routing e la scelta dei router dovrebbe avvenire contestualmente alla progettazione della rete e alla scelta del protocollo. I protocolli di routing standard più comuni sono il RIP e l'OSPF, ma il RIP non è adatto a reti su larga scala.
  
-   Gamma di protocolli e collegamenti WAN  
    È necessario stabilire quali protocolli si intende utilizzare sui collegamenti WAN, allo stato e in futuro. È consigliabile scegliere router di fascia alta, per supportare diversi protocolli e collegamenti ad alta velocità, anche se al momento attuale non sono strettamente necessari. I piccoli uffici di filiale possono essere dotati di connessioni remote, ISDN o a banda larga, tutti metodi che i router di fascia bassa dovrebbero essere sufficienti a supportare. Per quanto le connessioni a banda larga possano rappresentare l'opzione migliore per la struttura degli uffici di filiale, esse non sono disponibili ovunque e per alcune sedi le connessioni remote o ISDN possono essere le uniche soluzioni disponibili.
  
-   Protocollo NAT (Network Address Translation)  
    Il protocollo NAT viene utilizzato nei router connessi a Internet per convertire un singolo indirizzo Internet univoco in più indirizzi di rete privata. In questo modo un unico indirizzo Internet può essere condiviso da più periferiche e, poiché non è possibile che un altro utente Internet acceda direttamente agli indirizzi privati, si ottiene una misura di protezione. Il protocollo NAT dovrebbe essere disponibile nei router di piccoli uffici connessi tramite Internet e anche nei router di confine in sedi più ampie.
  
-   Protocollo DHCP (Dynamic Host Configuration Protocol)  
    Il protocollo DHCP viene utilizzato per assegnare automaticamente indirizzi IP ai PC, in modo che non sia necessario configurarne manualmente gli indirizzi. L'impostazione dei PC ne risulta semplificata: è possibile configurarli per utilizzare DHCP e far sì che ricevano automaticamente un indirizzo quando vengono accesi e connessi alla rete. Il protocollo è utile anche per i computer laptop che vengono utilizzati in diversi luoghi, poiché fornisce automaticamente un indirizzo IP adatto alla sede in cui si trovano in quel momento. Nelle sedi centrali sarà disponibile un servizio DHCP eseguito su un server con sistema operativo Microsoft(R) Windows(R) 2000 o Microsoft(R) Windows Server™ 2003 ma nei piccoli uffici è possibile che non sia presente alcun server e pertanto può essere necessario che sia il router stesso ad assegnare gli indirizzi DHCP.
  
-   Firewall  
    I router possono offrire una funzionalità di firewall e questa caratteristica è utile in tutti i router connessi a Internet, ad esempio quelli di uffici di filiale o quelli di confine delle grandi sedi. Sebbene un router con funzionalità complete sia l'opzione preferibile per le grandi sedi, il router di confine si trova all'esterno del firewall ed è necessario che sia protetto.
  
-   Protocollo VRRP (Virtual Router Redundancy Protocol)  
    Presso le grandi sedi è possibile installare come misura di sicurezza periferiche di rete duplicate, con una periferica principale e l'altra in hot standby che diviene attiva solo se la prima si guasta. Il protocollo VRRP viene eseguito su un collegamento tra i router, in modo che ciascun router rilevi lo stato di attività dell'altro e quello attivo reagisca automaticamente in caso di interruzione del collegamento.
  
-   VPN (Virtual Private Network)  
    Le VPN vengono utilizzate per fornire privacy e protezione a connessioni tramite Internet. Si tratta di un sistema efficace per stabilire una linea privata attraverso un servizio pubblico, utile principalmente per singoli utenti che si connettono da casa o per piccole filiali che si connettono a una sede centrale. Il collegamento VPN può essere impostato con diversi metodi, in uno dei quali il processo viene avviato dal PC client, nel qual caso la connessione VPN non viene rilevata dal router. Ma è anche possibile configurare il router con collegamenti VPN da router a router che non coinvolgono gli utenti e questo può essere un requisito per le piccole filiali.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classi di router
  
Come per gli switch, anche per i router sono state definite più classi in cui i prodotti sono inclusi in funzione delle opzioni di cui sono dotati. Le classi di router trattate nella presente sezione sono le seguenti:
  
-   **Classe 1 - Router software**
  
-   **Classe 2 - Router fissi di fascia bassa**
  
-   **Classe 3 - Router flessibili di fascia bassa**
  
-   **Classe 4 - Router di fascia media**
  
-   **Classe 5 - Router di fascia alta**
  
-   **Classe 6 - Router ISP**
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 1 - Router software
  
I router software sono computer con un sistema operativo standard e in cui sono installate funzioni software che forniscono capacità di routing tra una rete locale e una WAN. Il computer offre le normali funzionalità, mentre le funzioni di routing vengono eseguite in background. In genere questi router forniscono accesso condiviso a Internet per un numero contenuto di computer a utenti privati o piccole aziende. Offrono prestazioni limitate perché il routing è una funzione eseguita come attività in background e non prioritaria. Le prestazioni dipendono anche dall'attività che viene eseguita in foreground. L'adattabilità è limitata a quella offerta dal computer. Poiché in genere si tratta di una workstation, dipende in particolare dal fatto che l'utente non decida di disattivarla. L'aggiornabilità e la flessibilità sono scarse, poiché il software supporta un insieme circoscritto di protocolli WAN. Un esempio della classe di router software è costituito da ICS (Internet Connection Sharing), disponibile nei sistemi operativi Windows 98, ME, 2000, 2003 e XP.
  
I router software sono utili nelle situazioni con pochi utenti locali ed esigenze limitate di accesso WAN. Vengono utilizzati sempre più spesso nelle famiglie in cui diversi utenti richiedono l'accesso a Internet su un'unica linea telefonica. Quando l'utilizzo diventa più intenso ed eccede la capacità di questa soluzione di routing, è possibile installare un router della classe immediatamente successiva. Nella tabella 5 sono riepilogate le caratteristiche dei router di Classe 1.
  
**Tabella 5: Classe 1 - Router software**

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Solo software</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Semplicità di configurazione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">NAT (Network Address Translation) incorporato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nessun protocollo di routing</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Fornito gratuitamente con il sistema operativo o a bassissimo costo</td>
</tr>
</tbody>
</table>
  
#### Vantaggi
  
I vantaggi dei router software includono:
  
-   Economicità  
    Questi router non richiedono hardware aggiuntivo a parte un modem e sono forniti insieme al sistema operativo o disponibili a basso costo. L'economicità è il loro principale vantaggio rispetto al quale, però, svantaggi quali la carenza di funzionalità e prestazioni possono avere un peso maggiore.
  
-   Semplicità di configurazione  
    Le possibilità di configurazione sono in genere limitate alla semplice attivazione della funzione di routing. Insieme al protocollo DHCP (Dynamic Host Configuration Protocol) verrà attivato anche il NAT e a ogni computer della rete interna verrà assegnato automaticamente un indirizzo privato.
  
#### Svantaggi
  
Gli svantaggi dei router software includono:
  
-   Instabilità delle prestazioni  
    Nel caso in esame la funzione di routing si basa sulla potenza di elaborazione di un singolo computer che in genere svolge anche altre attività. Di conseguenza, le prestazioni sono limitate e variabili. I router software sono adatti principalmente a situazioni in cui l'accesso a Internet è occasionale e non continuo. Sufficienti per un solo computer autonomo, offrono prestazioni insufficienti per la connessione di più computer o se l'utilizzo di Internet diviene più intenso.
  
-   Opzioni di configurazione limitate  
    Poiché non è disponibile alcun protocollo di routing, le opzioni di configurazione sono in genere trascurabili, limitate alle funzionalità elementari di firewall.
  
-   Nessuna adattabilità  
    L'adattabilità coincide con quella del computer su cui è installato il software router, il che spesso implica la completa assenza di adattabilità. Di conseguenza, il software di routing è particolarmente soggetto ad azioni degli utenti quali, ad esempio, lo spegnimento del computer.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 2 - Router fissi di fascia bassa
  
I router fissi di fascia bassa offrono in genere scarse prestazioni, funzionalità e capacità di espansione, oltre a non presentare alcuna tolleranza d'errore. I router di questa classe sono progettati per eseguire il routing di una rete locale Ethernet a una WAN. Le connessioni WAN sono normalmente limitate a un modem per la connessione remota, ISDN, collegamento X25, banda larga o modem via cavo. In genere il router sarà dotato di un hub o uno switch incorporato (che può anche includere la connettività wireless per i computer dotati di schede wireless) e può anche offrire semplici funzioni di firewall.
  
La connettività WAN è incorporata nell'hardware del router e non può essere modificata se le esigenze cambiano. I router sono però economici e la mancanza di aggiornabilità è la contropartita di questo vantaggio.
  
Questi router non hanno caratteristiche di adattabilità ma sono periferiche dedicate e possono essere lasciati permanentemente accesi. Poiché sono economici, per ottenere la ridondanza è possibile installarne un secondo. Offrono soltanto una gamma minima di protocolli di routing, quali RIP e OSPF ma in genere sono dotati di una funzionalità NAT che consente a più utenti interni sulla LAN di accedere a Internet tramite un unico indirizzo.
  
Anche le prestazioni sono limitate, ma migliori di quelle delle periferiche di Classe 1, poiché l'hardware è progettato specificamente per il routing e non vengono eseguite altre funzioni contemporaneamente.
  
I router di questa classe sono progettati per i piccoli uffici o per il telelavoro, per fornire accesso a Internet a chi lavora da casa oppure per permettere la connessione di piccole filiali agli uffici centrali in una struttura di rete gerarchica. In questo ruolo si è largamente diffusa la tecnologia ISDN, perché consente di stabilire la connessione solo nel momento in cui è necessario un trasferimento di dati. In questo modo il costoso collegamento WAN viene utilizzato in modo efficiente ed economicamente vantaggioso. Il costo dei router di Classe 2 è diminuito nel tempo e di conseguenza queste periferiche hanno fatto il loro ingresso nella fascia degli utenti privati fornendo, nei modelli più diffusi, connettività per Internet ISDN o a larga banda. Nella tabella 6 sono riepilogate le caratteristiche dei router di Classe 2.
  
**Tabella 6: Classe 2 - Router fissi di fascia bassa**

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Protocolli WAN limitati</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Hardware non aggiornabile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protocollo di routing RIP, talvolta OSPF</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Prestazioni limitate</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Spesso semplice configurazione</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nessuna tolleranza d'errore</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Switch o hub incorporato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Firewall incorporato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">NAT/DHCP incorporati</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporto tecnico limitato da parte del produttore</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Costo — Basso</td>
</tr>
</tbody>
</table>
  
#### Vantaggi
  
I vantaggi offerti dai router fissi di fascia bassa includono:
  
-   Economicità  
    Si tratta di router economici, in parte perché offrono prestazioni e funzionalità limitate, in parte a causa della forte concorrenza. Possono includere anche un hub o uno switch e un firewall, risultando quindi particolarmente convenienti per piccole reti.
  
-   Semplicità di configurazione  
    Data la concorrenza per questa classe di router e le opzioni limitate, la configurazione è in genere semplice e spesso prevede un browser e un'interfaccia grafica.
  
-   Gamma di opzioni per la connettività WAN  
    Molti dei router a basso costo supportano solo connessioni WAN ISDN o ADSL ma alcune periferiche di questa classe possono includere X25 e Frame Relay, anche se a un costo più alto. Il collegamento WAN deve essere scelto al momento dell'acquisto del router e non può essere cambiato se le esigenze mutano.
  
-   Funzionalità incorporate  
    Questi router forniscono NAT e DHCP per l'assegnazione automatica di indirizzi ai computer collegati. Come funzionalità opzionale possono fornire un hub o uno switch a quattro o a otto porte e oggi in molti casi includono anche un semplice firewall. La presenza di switch wireless incorporati è sempre più diffusa.
  
#### Svantaggi
  
Gli svantaggi dei router fissi di fascia bassa includono:
  
-   Aggiornabilità limitata  
    L'hardware dei router di questa classe non è aggiornabile, ma in genere lo è il firmware. Al momento dell'acquisto possono essere disponibili diverse opzioni relative a connettività WAN, numero di porte Ethernet e switch incorporati ma, una volta scelte, tali opzioni non potranno essere modificate. Va comunque considerato che, visto il basso costo iniziale, questi prodotti potranno essere dismessi e sostituiti senza troppi problemi se non saranno in grado di rispondere alle esigenze future.
  
-   Prestazioni limitate  
    Le prestazioni di questi router sono limitate. In genere i produttori non divulgano i dati sul throughput ma, in linea di massima, questi router sono adatti per un massimo di otto utenti, a seconda delle attività che vengono eseguite.
  
-   Supporto limitato  
    Per questa classe di router il supporto è in genere limitato e viene fornito attraverso siti Web, elenchi di domande frequenti e posta elettronica, senza livelli di servizio garantiti. La concorrenza è agguerrita, il ciclo di vita dei prodotti è breve e i modelli vengono sostituiti frequentemente, con il risultato che per i prodotti divenuti obsoleti il supporto tende a scemare. Le garanzie sono limitate alla sostituzione, entro tempi non specificamente assicurati. Se una periferica non più in garanzia si guasta non è conveniente farla riparare. Data la semplicità e l'economicità delle periferiche, il livello di supporto descritto può essere considerato accettabile.
  
-   Gestibilità e funzionalità limitate  
    Progettati per reti semplici, i router che rientrano in questa classe presentano funzionalità di gestione limitate. Nel caso delle sedi remote di una grande rete aziendale, questo aspetto rappresenta un punto debole. Anche le opzioni di routing in queste periferiche sono limitate e alcune funzionalità essenziali per gli utenti aziendali, come il protocollo di routing OSPF, possono essere del tutto assenti.
  
-   Nessuna adattabilità  
    In questa classe i router non presentano adattabilità.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 3 - Router flessibili di fascia bassa
  
I router flessibili di fascia bassa offrono funzioni simili a quelli fissi della stessa fascia, ma presentano hardware aggiornabile, che consente di espanderli di pari passo con l'evoluzione delle esigenze dell'organizzazione. In genere, questi router supportano diversi tipi di connettività WAN o più porte WAN e, se dotati di hub o switch Ethernet incorporati, la connessione di periferiche locali aggiuntive. Di solito offrono prestazioni migliori rispetto ai router fissi perché sono progettati in modo da supportare la massima espansione delle porte senza richiedere l'aggiornamento dei processori. In quanto aggiornabili, sono più costosi dei router fissi di fascia bassa. Come questi ultimi, offrono una gamma limitata di protocolli di routing.
  
Vengono frequentemente utilizzati in piccoli uffici o uffici di filiali in cui è prevista una crescita futura. Sebbene il loro costo iniziale sia maggiore, a lungo termine queste periferiche si rivelano più convenienti rispetto ai router fissi perché è possibile aggiornarle e non necessariamente sostituirle quando le esigenze aumentano. In genere i router flessibili di fascia bassa sono più potenti rispetto a quelli fissi, per cui possono essere utilizzati in uffici più grandi. Nella tabella 7 sono riepilogate le caratteristiche dei router di Classe 3.
  
**Tabella 7: Classe 3 - Router flessibili di fascia bassa**

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Aggiornabilità</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Ampia gamma di opzioni per la connettività WAN</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protocolli di routing RIP e OSPF</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporto VLAN</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VoIP</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nessuna tolleranza d'errore</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Switch o hub incorporato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Firewall incorporato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">NAT/DHCP incorporati</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Costo - Variabile, da basso a elevato</td>
</tr>
</tbody>
</table>
  
#### Vantaggi
  
I vantaggi offerti dai router flessibili di fascia bassa includono:
  
-   Economicità  
    Sebbene più costosi rispetto ai router di Classe 2, questi router sono comunque economici. Offrono un maggior numero di funzionalità, prestazioni migliori e aggiornabilità, caratteristiche che giustificano il prezzo più alto.
  
-   Semplicità di configurazione  
    Normalmente questi router vengono utilizzati in reti semplici e sono dotati di strumenti di configurazione con interfaccia grafica. Per le configurazioni più complesse è possibile ricorrere ai sistemi di configurazione mediante riga di comando.
  
-   Funzionalità avanzate  
    Questi router sono dotati di funzionalità avanzate quali OSPF, VoIP, firewall e NAT, pertanto si prestano a essere utilizzati come componenti nelle reti aziendali.
  
-   Aggiornabilità  
    I router di questa classe presentano una nutrita serie di opzioni per la connettività WAN e possono essere aggiornati nel tempo, per adeguarli a nuove esigenze. È possibile aggiornare sia la memoria, per migliorare le prestazioni, che il sistema operativo, per introdurre nuove funzionalità.
  
#### Svantaggi
  
Gli svantaggi dei router flessibili di fascia bassa includono:
  
-   Prestazioni limitate  
    Sebbene i produttori tendano a non dichiarare le prestazioni dei propri router, senz'altro le periferiche appartenenti a questa classe offrono prestazioni limitate e sono adatte a piccoli uffici o reparti, a seconda dell'attività che vi si svolge e del traffico WAN.
  
-   Opzioni di configurazione limitate  
    I router di questa classe sono dotati di un valido insieme di funzionalità che però è pur sempre limitato rispetto alle periferiche delle classi superiori.
  
-   Scarsa scalabilità  
    In genere è possibile aggiornare la connettività WAN, anche se limitatamente a un numero ristretto di opzioni ma non il numero di porte LAN.
  
-   Nessuna adattabilità  
    I router di questa classe presentano poche funzionalità in questo senso o non ne presentano affatto.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 4 - Router di fascia media
  
I router di fascia media offrono più potenza e possibilità di espansione rispetto ai router di Classe 3. Sono provvisti di più porte LAN e WAN con connettività Ethernet più veloce e supportano Gigabit Ethernet, fibre ottiche e rame. Possono essere disponibili protocolli aggiuntivi, in particolare per la connettività backbone, per la connessione ad altre periferiche di rete quali router o switch, piuttosto che a singoli computer. Di solito questi router vengono utilizzati per le connessioni remote da singoli computer di utenti che lavorano da casa o piccoli ISP (Internet Service Provider) con modem analogici o ISDN. Normalmente supportano anche VoIP, che consente la trasmissione simultanea di dati e voce sullo stesso cavo.
  
L'adattabilità hardware incorporata nei router di fascia media è scarsa o nulla, ma in alternativa è possibile utilizzare due router, uno principale e uno in standby, e appositi protocolli per garantire un rapido passaggio dall'uno all'altro in caso di guasto.
  
I router di questa classe possono essere utilizzati per provvedere alle funzioni di routing essenziali in organizzazioni di medie dimensioni, nelle filiali più estese o per aggregare divisioni di una grande azienda per la connessione a un router più grande. L'opzione di connessione remota viene frequentemente utilizzata nel telelavoro, per connettersi direttamente all'organizzazione senza passare attraverso Internet. Questi router offrono una considerevole flessibilità e capacità di crescita per la connettività di reti WAN e LAN e tendenzialmente durano a lungo perché possono essere aggiornati per supportare nuove tecnologie. Nella tabella 8 sono riepilogate le caratteristiche dei router di Classe 4.
  
**Tabella 8: Classe 4 - Router di fascia media**

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Aggiornabilità</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Ampia gamma di opzioni per la connettività WAN</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Prestazioni &gt;40 kpps</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Protocolli di routing RIP e OSPF</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VLAN</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporto VoIP</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nessuna tolleranza d'errore</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Firewall incorporato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protocollo di adattabilità VRRP</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">NAT/DHCP incorporati</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VPN</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Costo - Variabile, da basso a elevato</td>
</tr>
</tbody>
</table>
  
#### Vantaggi
  
I vantaggi dei router di fascia media includono:
  
-   Prestazioni  
    I router di questa classe hanno un throughput di almeno 40 kbps e possono essere considerati router di medie prestazioni, adatti a grandi filiali o organizzazioni di medie dimensioni.
  
-   Espansione e scalabilità  
    I router di questa classe hanno una considerevole capacità di espansione, consentono l'incremento del numero di porte e supportano numerosi tipi di connettività.
  
-   Insieme completo di funzionalità  
    Di solito questi router sono dotati di un insieme completo di funzionalità, tra cui un'ampia gamma di opzioni di connettività WAN, protocolli di routing, NAT, DHCP, firewall, VLAN, VoIP e VPN.
  
#### Svantaggi
  
Gli svantaggi dei router di fascia media includono:
  
-   Scarsa adattabilità  
    In genere queste periferiche non presentano adattabilità incorporata, anche se i modelli migliori possono avere alimentatori ridondanti. Tuttavia, supportano protocolli di routing ridondanti, ad esempio VRRP, che consentono di ottenere l'adattabilità mediante un router in standby.
  
-   Basse prestazioni e scarsa scalabilità  
    Difficilmente queste periferiche offrono la potenza o la connettività necessarie per essere utilizzate in una grande azienda.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 5 - Router di fascia alta
  
I router di fascia alta offrono prestazioni elevate, una notevole capacità di espansione, tolleranza d'errore e disponibilità. L'hardware ha una struttura flessibile e sono previste più opzioni di connettività, come nei router di Classe 4, oltre a opzioni aggiuntive quali alimentatori e processori multipli e altre funzionalità che rendono questi router altamente adattabili.
  
In queste periferiche hanno un ruolo importante i protocolli ad alta velocità come ATM e SONET, per il collegamento di altre periferiche di rete e la trasmissione di grandi volumi di dati tra diversi siti, mentre router o switch più piccoli provvedono alla connessione delle workstation. Questi router sono estremamente versatili e supportano numerosi protocolli WAN e LAN e diversi supporti hardware, tra cui rame e fibre ottiche. Nella tabella 9 sono riepilogate le caratteristiche dei router di Classe 5.
  
**Tabella 9: Classe 5 - Router di fascia alta**

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Unità basata su telaio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Ampia gamma di opzioni per la connettività WAN</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Prestazioni &gt;oltre 900 kpps</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Protocolli di routing RIP e OSPF</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VLAN</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporto VoIP</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Alimentatore ridondante</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Modulo di gestione ridondante</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Firewall incorporato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Protocollo di adattabilità VRRP</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">NAT/DHCP incorporati</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Supporto VPN</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Costo - Elevato</td>
</tr>
</tbody>
</table>
  
#### Vantaggi
  
I vantaggi dei router di fascia alta includono:
  
-   Prestazioni  
    I router di questa classe hanno un throughput di almeno 900 kbps, considerevolmente più elevato rispetto ai router della Classe 4, e possono pertanto essere considerati router ad alte prestazioni, adatti a essere utilizzati come gateway di WAN o router principali per medie e grandi organizzazioni.
  
-   Espansione e scalabilità  
    Basati su telaio, i router di Classe 5 hanno una considerevole capacità di espansione del numero di porte e supportano un'ampia gamma di tipi di connettività.
  
-   Insieme completo di funzionalità  
    Di solito questi router sono dotati di un insieme completo di funzionalità, tra cui un'ampia gamma di opzioni di connettività WAN, protocolli di routing, NAT, DHCP, firewall, VLAN, VoIP e VPN.
  
-   Adattabilità  
    Queste periferiche incorporano opzioni di adattabilità quali un alimentatore ridondante sostituibile a caldo e moduli di gestione ridondanti. Inoltre, supportano protocolli di routing ridondanti, ad esempio VRRP, in cui un router in standby esegue il monitoraggio del router principale e subentra se questo si guasta.
  
#### Svantaggi
  
Lo svantaggio dei router di fascia alta è il costo elevato. I prezzo iniziale è alto perché queste periferiche offrono notevoli capacità di aggiornamento e adattabilità, ma il prezzo per porta si riduce man mano che vengono aggiunte nuove porte al telaio.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 6 - Router ISP
  
I router ISP sono utilizzati dagli ISP sulla backbone di Internet. È anche possibile utilizzarli in una grande azienda, se si desidera ottenere il massimo delle prestazioni. Forniscono altissime prestazioni nonché disponibilità e adattabilità elevate e sono in grado di gestire centinaia e perfino migliaia di utenti, con connessioni ad alta velocità alla backbone di Internet. Nella tabella 10 sono riepilogate le caratteristiche dei router di Classe 5.
  
**Tabella 10: Classe 5 - Router di fascia alta**

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristiche</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Unità basata su telaio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Ampia gamma di opzioni per la connettività WAN</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ampia gamma di opzioni per la connettività LAN</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Prestazioni nell'ordine di milioni di pps</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ampie capacità di espansione</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Alimentatori ridondanti</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Moduli di gestione ridondanti</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Costo - Molto elevato</td>
</tr>
</tbody>
</table>
  
#### Vantaggi
  
I vantaggi dei router ISP includono:
  
-   Prestazioni elevate  
    I router di questa classe sono progettati per le grandi aziende o come backbone o edge router di ISP. Forniscono prestazioni estremamente elevate.
  
-   Scalabilità  
    Questi router sono basati su telaio e possono essere ampiamente aggiornati. I telai possono presentare un massimo di 16 slot e ogni singolo blade supporta più connessioni.
  
-   Ampia gamma di protocolli WAN/LAN  
    I router di questa classe supportano praticamente tutti i protocolli pertinenti, tra cui numerosi protocolli WAN ad altissima velocità, ad esempio OC 192.
  
#### Svantaggi
  
Gli svantaggi di questi router sono il costo elevato e la potenziale complessità di configurazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Protezione
  
L'attenzione al problema della protezione è fondamentale quando si progetta una rete, per la necessità di neutralizzare sia le intrusioni esterne provenienti da Internet che quelle interne, tentate da dipendenti o altri utenti autorizzati ad accedere alla rete interna. È necessario tener conto di quattro aspetti principali:
  
-   Controllo delle intrusioni attraverso lo switch o il router.
  
-   Controllo delle intrusioni dirette allo switch o al router.
  
-   Controllo dell'accesso amministratore allo switch o al router.
  
-   Protezione fisica dei router e degli switch.
  
Gli switch e i router consentono il passaggio di pacchetti attraverso la rete e sono il primo punto in cui è possibile adottare filtri per bloccare i tentativi di intrusione, seguito dal firewall, che fornisce funzioni di filtro più sofisticate. Il filtraggio serve anche a impedire gli attacchi mirati alle periferiche stesse. Quasi tutti gli switch e i router possono essere riconfigurati, pertanto è necessario adottare rigidi controlli per limitare il numero di utenti autorizzati ad accedere alle periferiche come amministratori. In genere i router e gli switch prevedono metodi di accesso back-door per escludere la protezione logica e pertanto dovrebbero essere resi fisicamente inaccessibili.
  
La maggior parte dei router presenta vulnerabilità specifiche e note, che in genere sono descritte nel sito Web del produttore, insieme ai possibili correttivi.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Considerazioni sulla protezione dei router
  
Il router è la prima linea difensiva ma anche la prima linea di attacco. Provvede al routing dei pacchetti e può essere configurato per bloccare o filtrare l'inoltro di tipi di pacchetti notoriamente vulnerabili o utilizzati per scopi non autorizzati, ad esempio ICMP (Internet Control Message Protocol) o SNMP (Simple Network Management Protocol). Il router può essere utilizzato per bloccare il traffico non autorizzato o indesiderato tra le reti. È necessario proteggere anche il router stesso contro eventuali modifiche non autorizzate della configurazione, utilizzando interfacce di amministrazione protette e non mancando mai di installare gli aggiornamenti e le patch più recenti.
  
Se il router non è sotto controllo non si ha la possibilità di proteggere la rete, se non facendo affidamento sui meccanismi di difesa messi in atto dall'ISP sui relativi router.
  
Quando si prende in esame il problema della protezione del router è utile avvalersi delle categorie di configurazione seguenti:
  
-   **Patch e aggiornamenti**
  
-   **Protocolli**
  
-   **Accesso amministrativo**
  
-   **Servizi**
  
-   **Controllo e registrazione**
  
-   **Rilevamento delle intrusioni**
  
#### Patch e aggiornamenti
  
È utile iscriversi ai servizi di gestione degli avvisi forniti dal produttore dell'hardware di rete, in modo da essere sempre aggiornati sui problemi relativi alla protezione e sulle patch. Quando si scoprono dei punti di vulnerabilità, e inevitabilmente se ne scoprono, i produttori seri rendono rapidamente disponibili delle patch, annunciandone la disponibilità tramite posta elettronica o sul proprio sito Web. È sempre opportuno collaudare gli aggiornamenti prima di implementarli in un ambiente di produzione.
  
#### Protocolli
  
Gli attacchi di tipo negazione del servizio (DoS, Denial of Service) spesso sfruttano le vulnerabilità a livello di protocollo, ad esempio causando il flooding della rete. Per contrastare questo tipo di attacco è possibile adottare le misure seguenti:
  
-   Utilizzare filtri "ingress" ed "egress".
  
-   Separare il traffico ICMP dalla rete interna.
  
-   Bloccare il Rileva route.
  
-   Controllare il traffico broadcast.
  
-   Bloccare altro traffico non necessario.
  
##### Utilizzare filtri "ingress" ed "egress"
  
Lo spoofing dei pacchetti è indicativo di sondaggi, attacchi e altre attività da parte di un aggressore competente. I router eseguono il routing dei pacchetti in base all'indirizzo di destinazione e normalmente ignorano l'indirizzo di origine, che può non essere quello dell'autore del pacchetto. I pacchetti in ingresso con un indirizzo interno possono denunciare un tentativo di intrusione o una sonda ed è opportuno impedirne l'accesso alla rete perimetrale. Analogamente, il router deve essere impostato in modo da eseguire il routing dei pacchetti in uscita solo se presentano un indirizzo IP interno valido. La verifica dei pacchetti in uscita non protegge da attacchi di tipo Denial of Service ma impedisce che vengano originati dalla propria rete: se le altre reti attivassero la stessa verifica sarebbe possibile evitarli del tutto.
  
Questo tipo di filtraggio consente anche di rintracciare facilmente il creatore fino all'origine reale, poiché l'aggressore sarebbe costretto a utilizzare un indirizzo valido e legittimamente raggiungibile. Per ulteriori informazioni, vedere "Network Ingress Filtering: Defeating Denial of Service Attacks Which Employ IP Source Address Spoofing", all'indirizzo <http://www.rfc-editor.org/rfc/rfc2267.txt> (in inglese).
  
##### Separare il traffico ICMP dalla rete interna
  
ICMP è un protocollo senza informazioni sullo stato basato su IP, che consente di verificare da un host all'altro le informazioni sulla disponibilità degli host. I messaggi ICMP comunemente utilizzati sono riportati nella tabella 11.
  
**Tabella 11: Messaggi ICMP comunemente utilizzati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Messaggio</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Richiesta echo (Ping)</td>
<td style="border:1px solid black;">Consente di stabilire se un nodo IP (host o router) è disponibile sulla rete</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Risposta echo (risposta Ping)</td>
<td style="border:1px solid black;">Risponde a una richiesta echo ICMP</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Destinazione irraggiungibile</td>
<td style="border:1px solid black;">Informa l'host dell'impossibilità di inoltrare un datagramma</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Richiesta di rallentamento dell'origine</td>
<td style="border:1px solid black;">Informa l'host della necessità di rallentare la velocità di invio dei datagrammi a causa della congestione della rete</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Reindirizza</td>
<td style="border:1px solid black;">Informa l'host di una route preferenziale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Tempo scaduto</td>
<td style="border:1px solid black;">Indica che la durata (TTL) di un datagramma IP è terminata</td>
</tr>
</tbody>
</table>
  
Il blocco del traffico ICMP al livello del router perimetrale esterno protegge da attacchi quali flussi continui di ping in cascata e altri attacchi di tipo Denial of Service. Altri punti deboli di ICMP ne rendono opportuno il blocco. Sebbene la richiesta echo ICMP, o Ping, possa essere utilizzata per la risoluzione dei problemi, essa può consentire anche il rilevamento delle periferiche e dell'architettura di una rete, per cui dovrebbe essere ignorata a meno di valide ragioni. Il Ping può essere utilizzato anche per un attacco di negazione di servizio Ping of Death, per cui è consigliabile bloccarlo.
  
##### Bloccare il Rileva route
  
Rileva route è un sistema per raccogliere informazioni sulla topologia della rete. Rileva le periferiche durante il trasferimento di un messaggio verso un sistema di destinazione ed è molto utile per stabilire se i dati viaggiano su route ottimali. La sua implementazione varia da produttore a produttore: alcuni usano un Ping con diversi valori TTL, altri usano un datagramma UDP. Il Ping variabile può essere controllato bloccando i messaggi ICMP nel modo precedentemente descritto, mentre il blocco del datagramma UDP può richiedere un ACL. Bloccando i pacchetti di questo tipo si impedisce a un eventuale aggressore di apprendere dettagli sulla rete.
  
##### Controllare il traffico broadcast
  
Il traffico broadcast può essere utilizzato per enumerare gli host di una rete e rappresenta un veicolo per gli attacchi di tipo negazione di servizio. Bloccando specifici indirizzi di origine, ad esempio, è possibile impedire che richieste echo non autorizzate provochino flussi continui di ping in cascata. Gli indirizzi di origine che dovrebbero essere filtrati sono elencati nella tabella 12.
  
**Tabella 12: Indirizzi di origine da filtrare**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Indirizzo di origine</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">0.0.0.0/8</td>
<td style="border:1px solid black;">Broadcast cronologico</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">10.0.0.0/8</td>
<td style="border:1px solid black;">Rete privata RFC 1918</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">127.0.0.0/8</td>
<td style="border:1px solid black;">Loopback</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">169.254.0.0/16</td>
<td style="border:1px solid black;">Collegamento di reti locali (indirizzi APIPA)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">172.16.0.0/12</td>
<td style="border:1px solid black;">Rete privata RFC 1918</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">192.0.2.0/24</td>
<td style="border:1px solid black;">TEST-NET</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">192.168.0.0/16</td>
<td style="border:1px solid black;">Rete privata RFC 1918</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">224.0.0.0/4</td>
<td style="border:1px solid black;">Multicast Classe D</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">240.0.0.0/5</td>
<td style="border:1px solid black;">Riservato Classe E</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">248.0.0.0/5</td>
<td style="border:1px solid black;">Non allocato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">255.255.255.255/32</td>
<td style="border:1px solid black;">Broadcast</td>
</tr>
</tbody>
</table>
  
##### Bloccare altro traffico non necessario
  
Il traffico in ingresso da Internet al router di confine proviene da utenti sconosciuti e non attendibili che richiedono accesso ai server Web della rete. È possibile limitare l'accesso esclusivamente a uno specifico elenco di numeri di porta e indirizzi IP. Utilizzando gli elenchi di controllo degli accessi (ACL), disponibili nella maggior parte dei router, è possibile far sì che solo il traffico con la combinazione di indirizzi e porte desiderata passi attraverso il router di confine, sul presupposto che gli altri indirizzi siano potenzialmente ostili.
  
**Nota:** i numeri di porta dell'esempio non fanno riferimento alle porte di uno switch intese come le prese fisiche in cui si inseriscono i cavi Ethernet ma al sistema di indirizzamento IP, in cui l'indirizzo IP viene esteso con un numero di porta TCP o UDP. I server Web, ad esempio, si trovano spesso sulla porta 80: l'indirizzo completo del servizio Web in un server con indirizzo IP 192.168.0.1 sarà 192.168.0.1:80.
  
I router e gli switch Cisco utilizzano un protocollo proprietario, CDP o Cisco Discovery Protocol, per il rilevamento di informazioni sulle periferiche adiacenti, ad esempio dei numeri di modello e del livello di revisione del sistema operativo. Dal punto di vista della protezione si tratta di un punto debole, poiché un utente non autorizzato potrebbe ottenere le stesse informazioni, per cui è decisamente opportuno disattivare CDP sul router di confine e anche sui router e sugli switch interni, a meno che non sia indispensabile per il software di gestione.
  
#### Accesso amministrativo
  
È necessario stabilire da dove si accederà al router per l'amministrazione. Si deve decidere a quali interfacce e porte si potrà accedere mediante una connessione di amministrazione e da quale rete o host dovranno essere eseguite le relative attività. L'accesso dovrà essere limitato a tali specifici percorsi. Tutte le interfacce di amministrazione connesse a Internet dovranno essere protette con crittografia e contromisure atte a evitare intrusioni. È inoltre necessario:
  
-   Applicare rigidi criteri per le password.
  
-   Utilizzare un sistema di controllo dell'accesso amministrativo.
  
-   Disattivare le interfacce inutilizzate.
  
-   Considerare l'opportunità di utilizzare route statiche.
  
-   Chiudere la configurazione basata sul Web.
  
-   Servizi.
  
-   Controllare e registrare.
  
-   Rilevare intrusioni.
  
-   Controllare l'accesso fisico.
  
##### Applicare rigidi criteri per le password
  
In primo luogo è indispensabile impostare la password per l'amministratore: molti sistemi vengono violati solo perché l'amministratore non ha stabilito una password. In secondo luogo, devono essere scelte password complesse. Mediante software di tipo Brute force per le password possono essere lanciati attacchi più sofisticati rispetto a quelli basati sull'utilizzo di un dizionario ed è possibile individuare le password più comuni in cui una lettera è sostituita con un numero. Una password come, ad esempio, "p4ssw0rd" può essere identificata. Nella creazione di password è consigliabile utilizzare sempre combinazioni di lettere maiuscole e minuscole, numeri e simboli. Per le attività di gestione sarà probabilmente necessario il protocollo SNMP e anche in questo caso, sebbene la protezione SNMP non sia affatto elevata, è indispensabile definire le password (stringa comunità) al momento della configurazione. SNMP v3 fornisce una protezione notevolmente migliore.
  
##### Utilizzare un sistema di controllo dell'accesso amministrativo
  
Per l'autenticazione dell'amministratore, invece di incorporarne il nome nella configurazione è preferibile utilizzare un sistema di tipo AAA, che consente di controllarne l'identità nonché stabilire e registrare le attività che è autorizzato a svolgere. Le tre A corrispondono a:
  
-   Autenticazione  
    Il processo di autenticazione e verifica di un utente. Per autenticare gli utenti è possibile utilizzare diversi metodi, ma il più diffuso consiste in una combinazione di nome utente e password.
  
-   Autorizzazione  
    Il processo che stabilisce a cosa un utente può accedere e quali attività può eseguire.
  
-   Accounting  
    La registrazione delle attività che un utente sta eseguendo o ha eseguito su una periferica.
  
    I sistemi AAA fanno riferimento a un database ubicato in un server centrale per autenticare l'amministratore al suo primo accesso e controllare quali attività tenta di eseguire durante la sessione di connessione. Uno dei principali vantaggi di questo sistema è la centralizzazione delle informazioni di protezione, per cui con un'unica procedura è possibile controllare l'accesso dell'amministratore a tutte le periferiche di rete e non è necessario impostare procedure di accesso separate per ciascuna periferica.
  
    Sono disponibili due sistemi di tipo AAA non proprietari:
  
    -   RADIUS (Remote Authentication Dial-in User Service)
  
    -   Kerberos
  
    Un altro sistema molto diffuso di questo tipo è TACACS+, che però è un sistema proprietario Cisco e pertanto può essere utilizzato solo per controllare l'accesso su periferiche Cisco.
  
##### Disattivare le interfacce inutilizzate
  
Nel router dovrebbero essere attivate solo le interfacce necessarie. Un'interfaccia inutilizzata non viene monitorata né controllata e probabilmente non viene aggiornata. Questo la rende vulnerabile a eventuali attacchi. In genere per l'accesso amministrativo viene utilizzato Telnet, per cui è opportuno limitare il numero di sessioni Telnet disponibili e impostare un timeout per assicurare che una sessione verrà chiusa se rimane inutilizzata per un tempo prestabilito.
  
##### Considerare l'opportunità di utilizzare route statiche
  
Le route statiche impediscono che dei pacchetti appositamente congegnati possano modificare le tabelle di routing. Un aggressore potrebbe tentare di modificare le route simulando un messaggio del protocollo di routing per provocare la negazione del servizio o per inoltrare richieste a un server inaffidabile. Se si utilizzano route statiche è possibile modificare il routing solo se l'interfaccia amministrativa è compromessa. Va però ricordato che le route statiche sono, appunto, statiche: non solo possono richiedere una configurazione complessa, ma se un collegamento si interrompe i router non eseguono il passaggio automatico per utilizzare una route alternativa.
  
##### Chiudere la configurazione basata sul Web
  
Se per accedere alla configurazione è possibile utilizzare un server Web incorporato, oltre che una modalità con riga di comando, è necessario disabilitare il servizio Web, che sarà probabilmente soggetto ai numerosi punti deboli della protezione TCP/IP.
  
##### Servizi
  
Nei router distribuiti, a ciascuna porta aperta è associato un servizio in ascolto. Per ridurre le possibilità di attacchi è consigliabile chiudere i servizi non necessari, ad esempio **bootps** e **Finger**, che si utilizzano di rado. Inoltre, è opportuno eseguire la scansione del router per rilevare quali porte sono aperte.
  
##### Controllare e registraree
  
In genere i router sono dotati di una risorsa di registrazione e sono in grado di registrare tutte le azioni di negazione che denunciano tentativi di intrusione. I router più recenti offrono una serie di funzionalità di registrazione che includono la capacità di impostare i livelli di gravità sulla base dei dati registrati. È buona norma pianificare i controlli in modo che i registri vengano ispezionati a scadenze periodiche per rilevare eventuali segni di intrusione e sonde.
  
##### Rilevare intrusioni
  
Con le restrizioni impostate per evitare attacchi TCP/IP, il router dovrebbe essere in grado di identificare un eventuale attacco in corso e di informare un amministratore del sistema.
  
Gli aggressori scoprono le priorità di protezione e tentano di aggirarle. I sistemi di rilevamento delle intrusioni (IDS, Intrusion Detection System) sono in grado di individuare il punto in cui l'aggressore tenta di attaccare.
  
##### Controllare l'accesso fisico
  
Come si è già detto, la maggior parte dei router è vulnerabile se l'aggressore può fisicamente accedere alle periferiche, che di solito presentano un metodo di accesso back-door che consente di sovrascrivere la configurazione esistente. Per questo motivo è bene collocarli in una stanza con accesso limitato.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Considerazioni sulla protezione degli switch
  
Come il router, anche lo switch deve essere protetto contro le modifiche alla configurazione. A questo scopo è necessario utilizzare interfacce di amministrazione protette, assicurarsi di installare gli aggiornamenti e le patch più recenti, controllare l'accesso amministrativo e proteggere fisicamente la periferica.
  
La protezione degli switch tende a essere sottovalutata rispetto a quella dei router, poiché questi ultimi rappresentano il primo punto di difesa dagli attacchi provenienti da Internet, ma un documento particolarmente utile è disponibile all'indirizzo [http://www.cisco.com/en/US/netsol/ns744/networking\_solutions\_program\_home.html](http://www.cisco.com/en/us/netsol/ns744/networking_solutions_program_home.html) (in inglese).
  
Nel documento vengono analizzati alcuni punti deboli noti degli switch e le possibili contromisure.
  
Molti dei concetti relativi alla protezione, fin qui definiti per i router, sono ugualmente applicabili agli switch, ad esempio il controllo degli accessi amministrativi. Poiché lo switch riceve e trasmette frame Ethernet e non pacchetti IP, esso non è in grado di controllare le intrusioni nel traffico IP. Questa capacità sarebbe comunque superflua, perché lo switch si trova sempre dietro a un router con funzioni di firewall o a un firewall.
  
Le categorie di configurazione elencate di seguito consentono di garantire la protezione della configurazione degli switch.
  
-   **Patch e aggiornamenti**
  
-   **VLAN**
  
-   **Utilizzare un sistema di controllo dell'accesso amministrativo**
  
-   **Le porte inutilizzate sono disattivate**
  
-   **Servizi**
  
-   **Crittografia**
  
#### Patch e aggiornamenti
  
Patch e aggiornamenti devono essere installati e collaudati non appena sono disponibili.
  
#### VLAN
  
Le LAN virtuali consentono di separare i segmenti della rete e di applicare il controllo degli accessi sulla base di regole di protezione. Una VLAN senza elenchi di controllo di accesso (ACL) fornisce un primo livello di protezione, limitando l'accesso ai membri della stessa VLAN. Tuttavia, in genere è necessario consentire il traffico tra VLAN: a ciò provvede il router che esegue il routing del traffico tra le sottoreti IP e il necessario controllo viene fornito mediante ACL.
  
Gli ACL tra le VLAN limitano il flusso di traffico tra diversi segmenti della rete. In genere viene utilizzato un semplice filtro di pacchetti statico e non filtri di pacchetti che utilizzano lo stato o proxying a livello dell'applicazione, che vengono eseguiti da numerosi firewall dedicati.
  
L'uso di ACL tra le VLAN fornisce un livello intermedio di protezione, bloccando le intrusioni provenienti dall'interno dell'azienda, mentre quelle esterne vengono già bloccate dalla rete di confine. Gli ACL per le VLAN possono essere anche implementati in aggiunta alle funzioni di filtro del firewall, in modo da ottenere un ulteriore livello di protezione. Lo svantaggio degli ACL implementati sulle VLAN è che possono influire negativamente sulle prestazioni e devono essere configurati in modo corretto ed efficiente.
  
#### Utilizzare un sistema di controllo dell'accesso amministrativo
  
Per controllare l'accesso amministrativo agli switch è possibile utilizzare gli stessi metodi descritti per i router.
  
#### Disattivare le porte inutilizzate
  
Le porte Ethernet inutilizzate dello switch devono essere disattivate, per evitare che gli hacker possano collegarvisi.
  
#### Servizi
  
È opportuno disattivare tutti i servizi inutilizzati, nonché il protocollo TFTP (Trivial File Transfer Protocol), eliminare i punti di amministrazione connessi a Internet e configurare ACL per limitare l'accesso amministrativo.
  
#### Crittografia
  
Sebbene non sia normalmente implementata al livello dello switch, la crittografia dei dati sulla rete consente di neutralizzare lo sniffing dei pacchetti nei casi in cui un monitor viene posizionato sullo stesso segmento commutato o dove lo switch è compromesso, consentendo lo sniffing tra i segmenti.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo delle caratteristiche di una rete protetta
  
Nella tabella 13 sono riepilogate le caratteristiche di una rete protetta. Le impostazioni di protezione sono estrapolate dalle indicazioni di esperti del settore e da applicazioni reali nell'ambito di distribuzioni sicure. La tabella riepilogativa può essere utilizzata come punto di riferimento per la valutazione di una nuova soluzione.
  
**Tabella 13: Riepilogo delle caratteristiche di una rete protetta**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Componente</th>
<th style="border:1px solid black;" >Caratteristica</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Router</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Patch e aggiornamenti</td>
<td style="border:1px solid black;">Al sistema operativo del router vengono applicate le patch software aggiornate.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protocolli</td>
<td style="border:1px solid black;">Le porte e i protocolli inutilizzati sono bloccati.<br />
Filtraggio &quot;ingress&quot; ed &quot;egress&quot; implementato.<br />
Il traffico ICMP è separato dalla rete interna.<br />
La funzione Rileva route è disattivata.<br />
Il traffico broadcast diretto non viene inoltrato.<br />
Viene eseguito lo screening di pacchetti ping di grandi dimensioni.<br />
I pacchetti RIP (Routing Information Protocol), se utilizzati, vengono bloccati al router più esterno.<br />
Viene utilizzato il routing statico.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso amministrativo</td>
<td style="border:1px solid black;">Vengono applicati criteri rigidi per le password di amministrazione.<br />
Viene utilizzato un sistema di controllo dell'accesso amministrativo<br />
Le interfacce di gestione inutilizzate nel router sono disattivate.<br />
L'amministrazione basata sul Web è disattivata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Servizi</td>
<td style="border:1px solid black;">I servizi inutilizzati sono disattivati (ad esempio <strong>bootps</strong> e <strong>Finger</strong>).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllo e registrazione</td>
<td style="border:1px solid black;">È attiva la registrazione per tutto il traffico respinto.<br />
I registri vengono archiviati e protetti centralmente.<br />
Viene eseguito il controllo dei registri per rilevare l'eventuale presenza di schemi atipici.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Rilevamento delle intrusioni</td>
<td style="border:1px solid black;">Sono attivi sistemi di rilevamento delle intrusioni (IDS, Intrusion Detection System) per individuare e segnalare attacchi in corso.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso fisico</td>
<td style="border:1px solid black;">L'accesso fisico alle periferiche è limitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Switch</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Patch e aggiornamenti</td>
<td style="border:1px solid black;">Le patch più recenti vengono collaudate e installate o vengono adottati sistemi per mitigare la minaccia costituita da vulnerabilità note.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VLAN</td>
<td style="border:1px solid black;">Vengono utilizzate VLAN e ACL.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Le porte inutilizzate sono disattivate</td>
<td style="border:1px solid black;">Le porte Ethernet inutilizzate sono disattivate.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Servizi</td>
<td style="border:1px solid black;">I servizi inutilizzati sono disattivati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Crittografia</td>
<td style="border:1px solid black;">Il traffico commutato viene crittografato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Altro</strong></td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Sincronizzazione dei registri</td>
<td style="border:1px solid black;">Tutti gli orologi delle periferiche dotate di capacità di registrazione sono sincronizzati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Accesso amministrativo alla rete</td>
<td style="border:1px solid black;">Per l'autenticazione degli utenti amministrativi viene utilizzato Kerberos o RADIUS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ACL di rete</td>
<td style="border:1px solid black;">La rete è strutturata in modo da consentire l'utilizzo di ACL su host e reti.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo modulo sono state fornite informazioni e opzioni intese a semplificare, nel contesto della progettazione di una rete, la scelta di periferiche adatte a rispondere ai requisiti di un'architettura di rete aziendale. Le caratteristiche delle periferiche sono state evidenziate nell'ottica di agevolare il processo di selezione.
  
Il processo di progettazione dell'infrastruttura definito nel modulo include la scelta della classe di periferiche più adatta in funzione dei livelli di servizio richiesti. Inoltre, scegliere le opzioni appropriate è importante perché consente di accertarsi che le periferiche possano essere supportate dal personale addetto alla rete dell'organizzazione e gestite mediante qualsiasi soluzione già adottata per la gestione della rete. Scopo di questa guida è fornire un insieme di specifiche idonee a integrarsi nell'architettura di rete dell'organizzazione, per consentire la progettazione e l'implementazione di una rete completa.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
Per informazioni sugli standard consultare i riferimenti seguenti:
  
-   Gli standard di protocollo per Internet compresi nelle RFC (Request for Comments) dell'IETF (Internet Engineering Task Force) sono reperibili all'indirizzo <http://www.ietf.org/rfc.html> (in inglese).
  
-   Gli standard Ethernet dell'IEEE (Institute of Electrical and Electronics Engineers, Inc.) sono reperibili all'indirizzo <http://standards.ieee.org/getieee802/> (in inglese).
  
Per quanto concerne le informazioni correlate sulla protezione, diversi produttori di router e switch hanno pubblicato le proprie raccomandazioni per la protezione delle reti, che spesso non sono valide soltanto per i prodotti in questione, ma possono essere vantaggiosamente applicate a tutte le reti. Fare riferimento alla documentazione seguente:
  
-   Cisco Systems pubblica la blueprint SAFE all'indirizzo [http://www.cisco.com/en/US/prod/collateral/wireless/wirelssw/ps1953/product\_implementation\_design\_guide09186a00800a3016.pdf](http://www.cisco.com/en/us/prod/collateral/wireless/wirelssw/ps1953/product_implementation_design_guide09186a00800a3016.pdf) (in inglese).
  
-   "Improving Security on Cisco Routers" all'indirizzo [http://www.cisco.com/en/US/tech/tk648/tk361/technologies\_tech\_note09186a0080120f48.shtml](http://www.cisco.com/en/us/tech/tk648/tk361/technologies_tech_note09186a0080120f48.shtml) (in inglese).
  
-   "Configuring Broadcast Suppression" all'indirizzo [http://www.cisco.com/en/US/products/hw/switches/ps708/products\_configuration\_guide\_chapter09186a00800eb778.html](http://www.cisco.com/en/us/docs/switches/lan/catalyst6500/catos/8.x/configuration/guide/bcastsup.html) (in inglese)
  
-   "Configuring VLANs" all'indirizzo [http://www.cisco.com/en/US/products/hw/switches/ps663/products\_configuration\_guide\_chapter09186a00800e47e1.html\#1020847](http://www.cisco.com/en/us/docs/switches/lan/catalyst6500/catos/8.x/configuration/guide/vlans.html) (in inglese)
  
-   "Network Ingress Filtering" all'indirizzo <http://www.rfc-editor.org/rfc/rfc2267.txt> (in inglese)
  
##### Download
  
-   [Windows Server System Reference Architecture](http://www.microsoft.com/downloads/details.aspx?familyid=d44e34ec-b4e2-49a1-9f40-9ed4ba3765df&displaylang=en)
  
[](#mainsection)[Inizio pagina](#mainsection)
