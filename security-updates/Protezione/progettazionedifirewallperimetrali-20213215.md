---
TOCTitle: Progettazione di firewall perimetrali
Title: Progettazione di firewall perimetrali
ms:assetid: '8c22adfe-c457-4d5d-8d48-d42f6f6e424a'
ms:contentKeyID: 20213215
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc700828(v=TechNet.10)'
---

Progettazione di firewall perimetrali
=====================================

##### In questa pagina

[](#eyaa)[Argomenti del modulo](#eyaa)
[](#exaa)[Obiettivi](#exaa)
[](#ewaa)[Ambito di applicazione](#ewaa)
[](#evaa)[Utilizzo del modulo](#evaa)
[](#euaa)[Linee guida per la configurazione](#euaa)
[](#etaa)[Attacchi al sistema e difesa](#etaa)
[](#esaa)[Definizione del dispositivo](#esaa)
[](#eraa)[Funzionalità firewall](#eraa)
[](#eqaa)[Classi di firewall](#eqaa)
[](#epaa)[Classe 1: firewall personale](#epaa)
[](#eoaa)[Classe 2: router con funzionalità firewall](#eoaa)
[](#enaa)[Classe 3: firewall hardware di fascia bassa](#enaa)
[](#emaa)[Classe 4: firewall hardware di fascia alta](#emaa)
[](#elaa)[Classe 5: firewall server di fascia alta](#elaa)
[](#ekaa)[Uso di firewall perimetrali](#ekaa)
[](#ejaa)[Regole per i firewall perimetrali](#ejaa)
[](#eiaa)[Requisiti hardware](#eiaa)
[](#ehaa)[Disponibilità del firewall](#ehaa)
[](#egaa)[Protezione](#egaa)
[](#efaa)[Scalabilità](#efaa)
[](#eeaa)[Prestazioni](#eeaa)
[](#edaa)[Consolidamento](#edaa)
[](#ecaa)[Standard e linee guida](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Riferimenti](#eaaa)

### Argomenti del modulo

Questo modulo consente di selezionare un prodotto firewall adatto alla rete perimetrale di una specifica organizzazione. In esso sono presentate le diverse classi di firewall disponibili ed evidenziate le funzionalità più significative. Sono inoltre fornite indicazioni per l'identificazione dei requisiti specifici dell'ambiente e per la scelta del prodotto più appropriato.

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Il modulo consente di:

-   Individuare le funzionalità necessarie nel firewall perimetrale.

-   Classificare i prodotti firewall.

-   Selezionare il prodotto più adatto quale firewall perimetrale.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Questo modulo si applica alle seguenti tecnologie:

-   Prodotti firewall basati su Ethernet/IP

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

La conoscenza del protocollo TCP/IP, dell'architettura di rete in uso e dei dispositivi presenti nella rete perimetrale è una condizione indispensabile per comprendere e utilizzare le informazioni contenute nel modulo. Può inoltre risultare utile stabilire quale tipo di traffico in ingresso da Internet può essere considerato valido.

Le linee guida di progettazione presentate nel modulo consentiranno di selezionare le funzionalità che il firewall deve garantire tenendo in considerazione fattori determinanti come crescita e costi. Nel modulo verranno inoltre fornite informazioni su alcune tra le intrusioni più pericolose allo scopo di poter identificare quelle che potrebbero verificarsi nell'ambiente in esame e in che modo impedirle. Oltre a installare il firewall può essere opportuno, ad esempio, configurare il server in maniera più restrittiva o consultare il provider di servizi Internet (ISP). Nel modulo sono inoltre definite differenti classi di firewall e avvalendosi delle linee guida di progettazione sarà possibile scegliere quale tra queste sia la più adeguata alle proprie esigenze. Le informazioni contenute nel modulo e la terminologia tecnica utilizzata consentiranno di discutere con i produttori di firewall dei prodotti offerti e di valutare quale sia la soluzione più adatta alle diverse esigenze.

[](#mainsection)[Inizio pagina](#mainsection)

### Linee guida per la configurazione

Le intrusioni nelle reti da parte di utenti interni ed esterni alle stesse sono ormai sempre più frequenti e rendono indispensabile l'installazione di una protezione contro tali eventi. Sebbene i firewall proteggano la rete, comportano anche dei costi in termini economici e creano ostacoli al flusso del traffico. È necessario quindi assicurarsi che il firewall in uso garantisca il miglior rapporto qualità-prezzo e la massima efficienza possibile.

#### Architettura di rete

In un'architettura di rete aziendale sono in genere presenti tre aree:

-   Rete di confine
    Si tratta della rete direttamente connessa a Internet tramite un router che fornisce un livello iniziale di protezione mediante il filtraggio di base del traffico di rete. Il router trasmette i dati alla rete perimetrale tramite un firewall perimetrale.

-   Rete perimetrale
    Si tratta di una rete marginale, definita spesso DMZ (Demilitarized Zone), che collega gli utenti in ingresso ai server Web o ad altri servizi. I server Web, a loro volta, sono collegate alle reti interne tramite un firewall interno.

-   Reti interne
    Si tratta di reti interne che collegano i server interni, come i sistemi SQL Server e gli utenti interni.

Queste reti sono illustrate nella figura 1.

![](images/Cc700828.SGFG15601(it-it,TechNet.10).gif "Architettura della rete aziendale")

Figura 1
*Architettura della rete aziendale*

#### Elementi propedeutici alla configurazione

Un firewall controlla i pacchetti IP in ingresso e blocca quelli che considera attacchi intrusivi. Alcune operazioni di blocco possono essere eseguite riconoscendo, per impostazione predefinita, che determinati pacchetti non sono validi oppure configurando il firewall affinché blocchi tali pacchetti. Il protocollo TCP/IP è stato progettato quando non esisteva la necessità di prendere in considerazione eventuali attacchi o intrusioni e ha, quindi, molti punti deboli. Ad esempio, il protocollo ICMP è stato progettato come un meccanismo di segnalazione interno a TCP/IP ma è soggetto alle azioni di utenti malintenzionati e ad attacchi di tipo DoS (Denial of Service). Un firewall perimetrale presenta in genere una capacità molto più limitata rispetto a un firewall interno poiché il traffico in ingresso è diretto unicamente al server Web o ad altri servizi specifici.

Sono disponibili diversi tipi di firewall, che si differenziano per prezzi, per funzionalità offerte e prestazioni. In genere, i firewall più costosi sono quelli che offrono il maggior numero di funzionalità e il grado più elevato di efficacia. In una parte successiva di questo modulo i firewall sono raggruppati in classi al fine di poterli distinguere, ma prima di sceglierne uno è necessario stabilire quali siano i requisiti che deve soddisfare, tenendo in considerazione i seguenti fattori:

-   **Budget**

-   **Infrastrutture esistenti**

-   **Disponibilità**

-   **Scalabilità**

-   **Funzionalità richieste**

##### Budget

Qual è il budget disponibile? Ogni firewall dell'ambiente deve garantire il più alto livello di servizio senza gravare eccessivamente sui costi. Tuttavia, occorre essere consapevoli che un firewall di fascia molto economica può causare seri problemi all'azienda. È consigliabile considerare anche a quale danno economico andrebbe incontro l'organizzazione a causa di un periodo di inattività provocato dalla sospensione del servizio conseguente a un attacco di tipo Denial of Service.

##### Infrastrutture esistenti

Sono presenti infrastrutture utilizzabili per ridurre i costi? Nell'ambiente potrebbero essere già presenti firewall riutilizzabili e router provvisti di una serie di funzionalità firewall. Il provider di servizi Internet spesso è in grado di implementare restrizioni firewall al collegamento in uso quali la *limitazione della velocità*, ovvero limitando la velocità di invio di determinati pacchetti per ridurre la possibilità che si verifichino attacchi di tipo DDoS (Distributed Denial of Service), durante i quali la rete viene attaccata contemporaneamente da numerosi computer. Chiedere all'ISP se tra i servizi disponibili è inclusa una funzione di filtro conforme alle specifiche indicate nei documenti RFC 1918 e 2827.

##### Disponibilità

È necessario che il firewall sia sempre disponibile? Nel caso di servizi server Web pubblici con utenti che richiedono una disponibilità costante, i periodi di inattività devono essere ridotti a zero. Tuttavia, poiché tutti i firewall sono soggetti a errori, occorre premunirsi per ridurre al minimo i rischi. La disponibilità di un firewall può essere migliorata in due modi:

-   Componenti ridondanti
    La duplicazione dei componenti più facilmente soggetti a malfunzionamenti, come l'alimentatore, migliora la capacità di recupero del firewall, poiché quando il primo componente viene meno può subentrare il secondo senza alcun effetto sul funzionamento del dispositivo. I firewall di fascia economica in genere non includono opzioni ridondanti e l'aggiunta di funzionalità di recupero comporta un aumento dei costi senza incrementare la potenza di elaborazione.

-   Duplicazione di dispositivi
    La duplicazione del dispositivo firewall consente di creare un sistema con capacità di recupero totale. Ma questo ha un costo considerevole, poiché richiede che siano duplicati tutti i cavi di rete e la connettività nei router o negli switch a cui è collegato il firewall. Tuttavia, a seconda del firewall in uso, tale operazione è in grado anche di raddoppiare la velocità effettiva disponibile. In teoria tutti i firewall, dai più piccoli ai più grandi, possono essere duplicati, ma in pratica è necessario che sia presente anche un meccanismo di commutazione software che potrebbe non essere disponibile nei firewall più piccoli.

##### Scalabilità

Qual è il requisito di velocità effettiva del firewall? La velocità effettiva può essere valutata in termini di bit al secondo e di pacchetti trasferiti al secondo. Se si tratta di una nuova iniziativa imprenditoriale non è possibile conoscere quali siano i requisiti di velocità effettiva e se l'iniziativa ha successo tali requisiti potrebbero crescere rapidamente. Per far fronte a tali incognite, occorre scegliere una soluzione firewall che preveda l'opzione di scalabilità verticale quando la velocità effettiva aumenta, aggiungendo altri componenti al firewall o installando altri firewall in parallelo.

##### Funzionalità

Quali sono le funzionalità firewall richieste? Sulla base delle valutazioni dei rischi condotte a fronte dei servizi forniti nell'organizzazione, è possibile determinare quali funzionalità firewall sono necessarie per proteggere le risorse che garantiscono i servizi. Se sono necessarie reti private virtuali (VPN), questo inciderà sulla progettazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Attacchi al sistema e difesa

Questa sezione include un riepilogo di alcuni degli attacchi al sistema più noti e illustra i motivi per cui è consigliabile utilizzare un servizio firewall come prima linea difensiva.

#### Attacchi esterni

Internet è lo strumento ideale per coloro che desiderano causare danni alle organizzazioni o appropriarsi di segreti commerciali per imporsi sulla concorrenza. Se si installa un firewall perimetrale e si esamina il registro delle intrusioni, si resterà stupefatti dal volume di tali attacchi. La maggior parte delle intrusioni si limitano a verificare se il computer risponde e a individuare i servizi in esecuzione. Sebbene sembri trattarsi di operazioni innocue, consentono ai pirati informatici di accedere al computer e attaccare il servizio, una volta rilevati i punti deboli del sistema.

#### Attacchi interni

Oltre a implementare una protezione per far fronte agli attacchi basati su Internet, è necessario proteggere le informazioni riservate. La maggior parte delle organizzazioni gestisce informazioni riservate che devono essere protette da determinati utenti della rete interna, inclusi dipendenti, fornitori, consulenti e clienti. Mentre il firewall perimetrale è destinato principalmente a proteggere la rete dalle intrusioni esterne, è possibile che alcuni utenti interni esperti tentino di accedere tramite Internet.

#### Tipi di intrusioni

I tentativi di intrusione possono assumere diverse forme e descriverle tutte non servirebbe a molto poiché ne vengono ideate di nuove ogni giorno. Alcune intrusioni, come il ping di un indirizzo server, possono sembrare inoffensive, ma dopo aver rilevato la presenza di un server, il pirata informatico può tentare di sferrare un attacco più serio. In altre parole, tutte le intrusioni devono essere considerate potenzialmente pericolose. Di seguito sono riportate alcune delle intrusioni più comuni:

-   Sniffer di pacchetti
    Uno sniffer è un'applicazione software o un dispositivo hardware che si connette alla LAN e acquisisce informazioni dai frame Ethernet. Lo scopo originale di questi sistemi era quello di analizzare e risolvere i problemi del traffico Ethernet o di eseguire ricerche approfondite nei frame per esaminare singoli pacchetti IP. Gli sniffer operano in modalità promiscua, ovvero, ascoltano ogni pacchetto sul cavo fisico. Molte applicazioni, come Telnet, inviano informazioni relative a nomi utente e password in forma di testo non crittografato, che può essere visualizzato da prodotti sniffer. Un pirata informatico può, quindi, con uno sniffer ottenere l'accesso a molte applicazioni.

    I firewall non sono in grado di proteggere il sistema dallo sniffing, poiché uno sniffer non genera alcun traffico di rete. Esistono diverse misure per contrastare lo sniffing, tra cui la più importante consiste nell'utilizzare password con crittografia avanzata, ma questo argomento non rientra nell'ambito del presente modulo.

-   Spoofing IP
    Lo spoofing IP consiste nel modificare l'indirizzo di origine di un pacchetto IP per nascondere l'identità del mittente. Poiché l'operazione di routing in Internet utilizza solo l'indirizzo di destinazione per inviare il pacchetto e ignora l'indirizzo di origine, un hacker può inviare un pacchetto dannoso al sistema e mascherare l'indirizzo di origine in modo che non sia possibile sapere da dove proviene. Lo spoofing non è necessariamente dannoso ma segnala che è in corso un'intrusione. L'indirizzo potrebbe essere esterno alla rete, per nascondere l'identità dell'intruso, o corrispondere a uno degli indirizzi interni attendibili con privilegi di accesso. Lo spoofing viene in genere utilizzato per gli attacchi di tipo Denial of Service, che verranno descritti in seguito.

    È possibile impedire lo spoofing IP implementando uno o entrambi i meccanismi descritti di seguito:

    -   Controllo dell'accesso
        Negare l'accesso ai pacchetti in ingresso da Internet che presentano un indirizzo di origine della rete interna.

    -   Filtro RFC 2827
        È importante garantire che il traffico in uscita non sia sottoposto a spoofing IP. Poiché i pacchetti di spoofing devono avere una rete di origine, è essenziale impedire che la propria rete venga utilizzata come origine dello spoofing. Di conseguenza, occorre bloccare tutto il traffico in uscita dalla rete che non presenta un indirizzo di origine incluso tra quelli allocati. Il provider di servizi Internet può anche riuscire a respingere il traffico di spoofing dalla rete verificando se l'indirizzo di origine appartiene alla rete dell'azienda. Questa tecnica è indicata come filtro RFC 2827. Per ulteriori informazioni sul modo in cui applicarla, rivolgersi all'ISP. L'applicazione di un filtro al traffico in uscita non comporta vantaggi diretti, ma se la stessa tecnica viene applicata dalle altre reti potrebbe impedire la trasmissione di traffico di spoofing alla rete in uso. La maggior parte dei firewall di ultima generazione prevede la capacità di impedire lo spoofing IP in ingresso.

-   Attacchi Denial-of-Service
    Gli attacchi DoS (Denial of Service) sono tra i più difficili da prevenire. A differenza di altri tipi di attacchi, non provocano danni permanenti alla rete, bensì tentano di interrompere il funzionamento della rete bersagliando un particolare computer, che può essere un server o una periferica di rete, o riducendo la velocità effettiva dei collegamenti di rete fino a compromettere le prestazioni al punto tale da causare malcontento tra i clienti e conseguenti danni all'organizzazione. L'attacco DDoS (Distributed DoS) viene sferrato da numerosi computer che concentrano il bombardamento sul sistema. I computer che attaccano il sistema non sono in realtà gli autori dell'attacco. Hanno semplicemente subito a loro volta intrusioni da parte di pirati informatici che hanno sfruttato vulnerabilità esistenti a livello di protezione per dare origine all'invio di elevati volumi di dati alla rete in modo da bloccare il collegamento all'ISP o uno dei dispositivi.

-   Attacchi a livello di applicazione
    Gli attacchi a livello di applicazione sono spesso i più pubblicizzati e, sfruttano, in genere, punti deboli molto noti di applicazioni quali server Web e server di database. Il problema, in particolare per i server Web, risiede nel fatto che tali sistemi sono progettati per consentire l'accesso a utenti pubblici sconosciuti e non considerabili attendibili. La maggior parte degli attacchi sfrutta difetti noti del prodotto, quindi la miglior difesa consiste nell'installare gli ultimi aggiornamenti messi a disposizione dai produttori. In pochi giorni, a partire dal suo rilascio nel gennaio 2003, il pericolosissimo worm SQL (Structured Query Language) Slammer ha compromesso 35.000 sistemi, sfruttando una nota vulnerabilità di Microsoft® SQL Server 2000 per cui Microsoft aveva già messo a disposizione, quattro mesi prima, una correzione nell'agosto 2002. Tale effetto dirompente è stato possibile perché molti amministratori non avevano applicato l'aggiornamento consigliato e non disponevano di firewall adeguati, che avrebbero potuto bloccare i pacchetti destinati alla porta utilizzata dal worm. In situazioni del genere, tuttavia, un firewall non è altro che una barriera; i produttori consigliano di applicare aggiornamenti a tutti i prodotti, soprattutto per evitare attacchi a livello di applicazione.

-   Ricognizione di rete
    La ricognizione di rete è il processo di scansione delle reti mirato a individuare indirizzi IP validi, nomi DNS (Domain Name System) e porte IP prima di lanciare un attacco. La ricognizione di rete in se stessa non è dannosa, ma sapere quali sono gli indirizzi in uso consente di lanciare attacchi mirati a danneggiare il sistema. Se si esaminano i registri di un firewall, infatti, si noterà che la maggior parte delle intrusioni è di questo tipo. Le operazioni più comuni includono la scansione delle porte di attesa TCP (Transport Control Protocol) e UDP (User Datagram Protocol) nonché di altre porte di attesa molto note come quelle utilizzate da Microsoft SQL Server, NetBIOS (Network Basic Input/Output System), HTTP (Hypertext Transfer Protocol) e SMTP (Simple Mail Transport Protocol). Tali letture richiedono una risposta, grazie alla quale l'hacker viene a sapere che il server esiste ed esegue uno di questi servizi. Molte operazioni di scansione possono essere evitate utilizzando un router di confine o un firewall. Molti servizi sono presenti per impostazione predefinita e non sono richiesti, ma la disattivazione di alcuni di essi può compromettere le funzionalità diagnostiche della rete.

-   Virus/Cavalli di Troia
    I virus in genere non possono essere rilevati dai firewall in quanto sono spesso incorporati in allegati di posta elettronica. I virus di tipo tradizionale tendevano a danneggiare solo il dispositivo infettato, mentre quelli di ultima generazione tendono a duplicarsi e a danneggiare altri computer locali o a diffondersi in Internet mediante l'invio di numerosi messaggi di posta elettronica con il virus in allegato. Gran parte di questi virus installa un programma Trojan Horse nel dispositivo contaminato. Un programma Trojan Horse può non provocare alcun danno diretto, ma invia informazioni all'hacker tramite Internet dal dispositivo in cui è installato. In questo modo il pirata informatico può sferrare un attacco mirato a tale dispositivo poiché conosce il software in esecuzione e le relative vulnerabilità. Sebbene la prima misura difensiva contro i virus consista nel mantenere costantemente aggiornato il software antivirus presente sul dispositivo, il firewall perimetrale può contribuire a limitare l'efficacia del programma Trojan Horse.

[](#mainsection)[Inizio pagina](#mainsection)

### Definizione del dispositivo

Un firewall è un meccanismo per il controllo del flusso del traffico IP tra due reti. I dispositivi firewall operano in genere a livello 3 del modello OSI, sebbene alcuni di essi possano operare anche a livelli più alti.

I firewall, in genere, offrono i seguenti vantaggi:

-   Difesa dei server interni dagli attacchi di rete.

-   Applicazione di criteri di accesso e utilizzo delle rete.

-   Monitoraggio del traffico e generazione di avvisi al rilevamento di operazioni sospette.

È importante notare che i firewall consentono di ridurre solo determinati rischi per la protezione. Non consentono, in genere, di evitare i danni che possono essere inflitti a un server sfruttando una vulnerabilità del software. I firewall devono essere implementati come parte integrante dell'architettura di protezione completa di un'organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Funzionalità firewall

A seconda delle funzionalità supportate da un firewall, il traffico viene consentito o bloccato mediante un'ampia gamma di tecniche che garantiscono diversi gradi di protezione. Le seguenti funzionalità firewall sono elencate in ordine crescente di complessità:

-   **Filtri di input della scheda di rete**

-   **Filtri di pacchetti statici**

-   **Conversione degli indirizzi di rete (NAT, Network Address Translation)**

-   **Stateful Inspection**

-   **Controllo a livello di circuito**

-   **Proxy**

-   **Filtraggio a livello di applicazione**

In generale, i firewall che prevedono funzionalità complesse supportano anche funzionalità più semplici. Tuttavia, prima di scegliere un prodotto è opportuno leggere con attenzione le informazioni messe a disposizione dal fornitore, poiché possono esistere sottili differenze tra le funzionalità presunte e reali di un firewall. Per scegliere un firewall occorre esaminare le funzionalità offerte e verificare che il prodotto garantisca le prestazioni indicate nelle specifiche.

#### Filtri di input della scheda di rete

Il filtraggio dell'input della scheda di rete consente di esaminare gli indirizzi di origine e di destinazione e altre informazioni del pacchetto in ingresso per bloccarlo o lasciarlo passare. Il filtro viene applicato solo al traffico in ingresso e non è in grado di controllare il traffico in uscita. La sua azione consiste nel confrontare gli indirizzi IP e i numeri di porta UDP e TCP, nonché il protocollo del traffico, TCP, UDP e GRE (Generic Routing Encapsulation).

Nel caso di un firewall perimetrale che protegge un server Web, il traffico in ingresso autorizzato deve essere in grado di accedere solo all'indirizzo IP del server stesso e, in genere, a una serie limitata di numeri di porte, tra cui 80 per HTTP o 443 per HTTPS. Sebbene questa funzionalità di controllo sia presente nel firewall perimetrale, può anche essere implementata nel router di confine.

Il filtraggio dell'input della scheda di rete consente di negare, in modo rapido ed efficace, l'accesso ai pacchetti in ingresso standard che soddisfano i criteri configurati nel firewall. Tuttavia, questa azione di filtro può essere facilmente aggirata, poiché si limita a far corrispondere le intestazioni del traffico IP, partendo dal presupposto che il traffico da filtrare segua gli standard IP e non sia stato alterato per eludere il filtraggio.

#### Filtri di pacchetti statici

Si tratta di filtri simili a quelli dell'input della scheda di rete; si limitano, infatti, a confrontare le intestazioni IP per stabilire se consentire o meno il passaggio del traffico attraverso l'interfaccia. Tuttavia, i filtri di pacchetti statici consentono di controllare le comunicazioni in uscita e in ingresso verso un'interfaccia. Inoltre, aggiungono alla funzione di filtraggio della scheda di rete la possibilità di controllare se il bit ACK (Acknowledged) sia impostato nell'intestazione IP. Il bit ACK indica se il pacchetto è una nuova richiesta o una richiesta di ritorno di una richiesta originale. Non consente di verificare che il pacchetto sia stato originariamente inviato dall'interfaccia che lo riceve; la sua funzione consiste esclusivamente nel controllare, sulla base delle convenzioni delle intestazioni IP, se il traffico in arrivo nell'interfaccia sia di ritorno.

Questa tecnica è valida solo per il protocollo TCP e non per quello UDP. Come il filtraggio dell'input della scheda di rete, anche il filtraggio di pacchetti statici è molto veloce ma le sue funzionalità sono limitate e può essere eluso predisponendo opportunamente il traffico.

Analogamente al filtraggio dell'input della scheda di rete, il filtraggio dei pacchetti statici deve essere implementato nel router di confine oltre che nel firewall perimetrale.

#### Conversione degli indirizzi di rete

All'interno della gamma di indirizzi IP mondiale, alcune serie di indirizzi vengono definite *indirizzi privati*. Questi indirizzi sono destinati all'utilizzo all'interno dell'organizzazione e non hanno alcun significato in Internet. Il traffico destinato a uno qualsiasi di questi indirizzi IP non può essere instradato attraverso Internet, quindi assegnare un indirizzo privato alle periferiche interne significa garantire loro una forma di protezione dalle intrusioni. Tuttavia accade spesso che le periferiche interne debbano accedere a Internet. In questo caso interviene la tecnologia di conversione degli indirizzi di rete (NAT) a convertire l'indirizzo privato in un indirizzo Internet.

Sebbene NAT non sia propriamente una tecnologia firewall, l'occultamento del reale indirizzo IP di un server impedisce agli autori degli attacchi di acquisire informazioni importanti sul server.

#### Stateful Inspection

In modalità Stateful Inspection tutto il traffico in uscita viene registrato in una tabella di stato. Quando il traffico di connessione ritorna all'interfaccia, viene eseguito un controllo nella tabella di stato per verificare che il traffico sia stato effettivamente originato dall'interfaccia. La tecnologia Stateful Inspection è leggermente più lenta del filtraggio di pacchetti statici. Tuttavia, garantisce che il traffico sia autorizzato a passare solo se corrisponde alle richieste del traffico in uscita. La tabella di stato contiene elementi quali gli indirizzi IP di destinazione e di origine, la porta chiamata e l'host di origine.

Alcuni firewall memorizzano nella tabella di stato più informazioni di altri riportando, ad esempio, i frammenti IP inviati e ricevuti. Il firewall può verificare che il traffico venga elaborato al momento della restituzione di tutte le informazioni frammentate o solo di una parte di esse. L'implementazione della funzionalità di Stateful Inspection varia a seconda del firewall, quindi occorre leggere attentamente la documentazione del dispositivo.

La funzionalità di Stateful Inspection consente, in genere, di ridurre i rischi associati alla ricognizione della rete e allo spoofing IP.

#### Controllo a livello di circuito

Con il filtraggio a livello di circuito è possibile esaminare le sessioni invece delle connessioni o dei pacchetti. Le sessioni vengono stabilite solo in risposta a una richiesta utente e possono includere più connessioni. Il filtraggio a livello di circuito garantisce un supporto incorporato per protocolli con connessioni secondarie, quali, ad esempio il protocollo FTP e i protocolli di flussi multimediali. Questo tipo di filtro consente, in genere, di ridurre i rischi associati agli attacchi di ricognizione di rete, DoS e di spoofing IP.

#### Firewall di tipo proxy

I firewall di tipo proxy richiedono informazioni da parte di un client. A differenza delle tecnologie firewall esaminate in precedenza, la comunicazione non avviene direttamente tra il client e il server in cui è installato il servizio. In questo caso il firewall proxy raccoglie le informazioni per il client e restituisce i dati ricevuti dal servizio al client. Poiché il server proxy ottiene le informazioni per un solo client, ne memorizza anche il contenuto nella cache del disco o della memoria. In questo modo, se un altro client richiede esattamente gli stessi dati, la richiesta può essere soddisfatta utilizzando la cache e, quindi, riducendo il traffico di rete e i tempi di elaborazione del server.

Nel caso delle sessioni non crittografate, come le sessioni FTP di sola lettura e HTTP, il firewall proxy crea sessioni separate con il client e il server, in modo che non vi sia mai una connessione diretta tra le due parti. Nelle sessioni crittografate, invece, il server proxy verifica che le informazioni di intestazione siano conformi agli standard di comunicazione SSL (Secure Sockets Layer) prima di consentire il passaggio del traffico. Tuttavia il proxy non può esaminare i dati in transito poiché utilizza una crittografia end-to-end definita dal client e dal server.

I vantaggi dell'utilizzo di un server proxy rispetto alle tecnologie firewall esaminate in precedenza includono i seguenti aspetti:

-   Nessuna connessione diretta tra client e server
    Il client e il server, in genere, non entrano in contatto diretto e, anche se ciò si verifica, come nel caso della comunicazione SSL, viene eseguito un controllo dell'intestazione di protocollo del traffico.

-   Caching nel server del contenuto dei siti richiesti con maggiore frequenza
    La funzione di caching consente di ridurre l'utilizzo della larghezza di banda e impedisce l'uscita dall'ambiente di richieste superflue.

-   Convalida dei protocolli in transito attraverso il server
    Oltre a convalidare il numero di porta utilizzato per la comunicazione, i server proxy convalidano anche i protocolli su cui si basa la comunicazione. I protocolli esaminati con maggiore frequenza sono quelli FTP di solo download, HTTP, SSL e alcuni servizi per l'invio di messaggi di solo testo, che non includono video, audio o trasferimenti di file.

-   Possibilità di configurare l'inoltro delle richieste in base a un ID utente
    I server proxy spesso possono essere configurati in modo da inoltrare richieste in base all'ID utente anziché considerare solo l'indirizzo IP di origine, la porta o il protocollo, consentendo in questo modo l'impostazione di limitazioni solo per utenti specifici.

Lo svantaggio principale di un server proxy è che richiede una potenza di elaborazione molto più elevata per eseguire il controllo del protocollo. Questo aspetto però sta assumendo un'importanza secondaria in quanto i livelli di potenza di elaborazione disponibili diventano sempre più elevati. Inoltre, i server proxy non possono contare sulla velocità effettiva di un firewall di tipo Stateful Inspection o con filtro dei pacchetti. Si potrebbe obiettare però che i vantaggi aggiunti del controllo dei protocolli sono fondamentali in una realtà in cui le reti a velocità elevata abbondano per gli utenti privati e la connessione a Internet diventa sempre più accessibile a nodi non attendibili, connessi tramite ISP con obblighi legali praticamente inesistenti a fornire servizi Internet attendibili.

La funzionalità proxy in genere contribuisce a ridurre il rischio associato alla ricognizione di rete, agli attacchi di tipo DoS e spoofing IP, a virus e Trojan horse e ad alcuni attacchi a livello di applicazione.

#### Filtraggio a livello di applicazione

Il livello più sofisticato di controllo del traffico del firewall è rappresentato dal filtraggio a livello di applicazione. Un buon filtro applicativo consente di analizzare un flusso di dati relativo a una determinata applicazione e garantire particolari attività di elaborazione, quali il controllo, lo screening o il blocco, il reindirizzamento e la modifica dei dati al passaggio attraverso il firewall.

Questo meccanismo viene utilizzato per proteggere il sistema da comandi SMTP non sicuri o attacchi sferrati contro server DNS interni. In genere, è possibile aggiungere al firewall strumenti di terze parti per lo screening del contenuto, quali applicazioni per il rilevamento dei virus, l'analisi lessicale e la classificazione dei siti.

Un firewall a livello di applicazione è in grado di controllare molti protocolli diversi sulla base del traffico che passa attraverso di esso. A differenza di un firewall di tipo proxy, che esamina in genere il traffico Internet di tipo HTTP, download FTP e SSL, il firewall applicativo ha maggiore controllo sui percorsi del traffico che passa attraverso di esso. Un firewall a livello di applicazione è, ad esempio, in grado di consentire il passaggio solo al traffico UDP generato all'interno dei limiti del firewall. Se un host Internet è impostato per eseguire la scansione delle porte di un firewall di tipo Stateful Inspection al fine di verificare se quest'ultimo consente il traffico DNS nell'ambiente, la scansione evidenzierebbe probabilmente che la ben nota porta associata al DNS è aperta, ma una volta in corso l'attacco, il firewall rifiuterebbe le richieste perché provenienti dall'esterno della rete. Un firewall a livello di applicazione potrebbe aprire le porte dinamicamente valutando se il traffico ha o meno un'origine interna alla rete.

La funzionalità firewall a livello applicativo consente di ridurre i rischi associati allo spoofing IP, agli attacchi di tipo DoS e ad alcuni attacchi a livello di applicazione, alla ricognizione di rete e a virus e Trojan horse. Tuttavia, questo genere di firewall presenta svantaggi simili a quelli del proxy in quanto richiede più potenza di elaborazione dei firewall di tipo Stateful Inspection o con funzionalità di filtraggio statico e rallentare ulteriormente, rispetto a questi ultimi, il passaggio del traffico. Quando si utilizza un firewall applicativo è molto importante stabilire quali siano le funzioni garantite a livello delle applicazioni.

La funzionalità a livello di applicazione garantisce che il traffico passato su una porta sia appropriato. A differenza dei firewall con filtro dei pacchetti e di tipo Stateful Inspection, che si limitano a controllare la porta e l'indirizzo IP di origine e di destinazione, i firewall che supportano la funzionalità di filtraggio a livello di applicazione possono esaminare i dati e i comandi che vengono passati.

La maggior parte dei firewall con funzionalità di filtro a livello di applicazione prevede il filtraggio solo del traffico con testo in chiaro quale, ad esempio, quello rappresentato da un servizio di messaggistica dipendente da un server proxy o da servizi HTTP e FTP. È importante ricordare che un firewall che supporta tale funzionalità può controllare il traffico in entrata e in uscita dall'ambiente. Un altro vantaggio dei firewall applicativi consiste nella possibilità di controllare il traffico DNS al passaggio attraverso il firewall per individuare comandi specifici del DNS. Questo ulteriore livello di protezione garantisce che gli utenti o i pirati informatici non possano mascherare informazioni nei tipi di traffico consentiti.

Se l'organizzazione ha un archivio in linea che raccoglie numeri di carta di credito e altre informazioni personali dei clienti, sarebbe prudente prendere tutte le precauzioni del caso al fine di garantire il più alto livello di protezione dei dati. In questo contesto è essenziale che i dati che richiedono un livello di protezione elevato vengano crittografati tra il computer dell'utente e i server Web mediante il protocollo SSL (Secure Sockets Layer).

In alcuni casi la funzionalità a livello applicativo viene utilizzata insieme al protocollo SSL. Questo protocollo è crittografato e il firewall non è in grado di interpretarne i comandi poiché sono posizionati all'interno del pacchetto crittografato. Ogni firewall che supporta la funzionalità di livello applicativo gestisce questa situazione in maniera diversa, quindi è importante leggere le specifiche fornite nella documentazione del firewall scelto.

Il problema risiede nel fatto che, quando è stata stabilita una sessione SSL e la crittografia è stata negoziata, non è previsto alcun controllo dei dati. Ad esempio, un client che utilizza un firewall con funzionalità di livello applicativo di tipo proxy richiede al firewall di stabilire una connessione a un server Web protetto. Il firewall e il server eseguono le operazioni iniziali di configurazione della connessione TCP, quindi il firewall passa la connessione al client affinché definisca la crittografia con il server. Quando la connessione viene passata al client, il firewall non può più controllare i dati.

Quando la funzionalità di livello applicativo viene utilizzata per esporre pubblicamente servizi Internet, sono disponibili le seguenti opzioni:

-   Interrompere il traffico SSL nel firewall
    In questo modo il firewall può controllare le connessioni SSL in ingresso per individuare il traffico Web valido e respingere il traffico mentre vengono decrittografati i dati per il servizio Internet.

-   Rigenerare il traffico SSL dal firewall al servizio Web esposto
    Questa soluzione è particolarmente efficace se si utilizzano credenziali di base, ad esempio nome utente e password in testo non crittografato, nel tunnel SSL. Se un utente cerca di eseguire un'operazione di sniffing sul traffico tra l'interfaccia interna del firewall e il servizio Web pubblicato, non potrà accedere al traffico poiché sarà stato nuovamente crittografato.

-   Consentire il passaggio del traffico SSL attraverso il firewall verso il server back-end
    Questa soluzione è essenzialmente l'opposto dell'approccio che prevede la connessione SSL tra il client interno e il server esterno.

Queste opzioni offrono molte opportunità per controllare quale livello di accesso concedere a una sessione crittografata all'interno di un ambiente. In genere è consigliabile mantenere il più possibile il traffico crittografato ai margini dell'ambiente poiché non è possibile in alcun modo conoscere cosa sia effettivamente contenuto in tale tunnel.

[](#mainsection)[Inizio pagina](#mainsection)

### Classi di firewall

In questa sezione sono riportate diverse classi di firewall, ciascuna delle quali garantisce determinate funzionalità. È possibile avvalersi di specifiche classi di firewall per rispondere a specifici requisiti di progettazione di un'architettura IT.

Il raggruppamento dei firewall in classi consente di separare l'hardware dai requisiti del servizio, in modo che questi possano essere basati sulle funzionalità delle classi. Se un firewall rientra in una determinata classe, ne consegue che supporta tutti i servizi di tale classe.

Di seguito sono riportate le diverse classi:

-   Firewall personali.

-   Router con funzionalità firewall.

-   Firewall hardware di fascia bassa.

-   Firewall hardware di fascia alta.

-   Firewall di tipo server.

Alcune classi presentano caratteristiche che si sovrappongono. La sovrapposizione consente di ascrivere un tipo di soluzione firewall a più classi. Molte classi supportano, inoltre, l'utilizzo di più modelli di hardware dello stesso fornitore, in modo che un'organizzazione sia libera di scegliere il modello più adatto alle esigenze presenti e future.

Oltre al prezzo e alla serie di funzionalità offerta, un altro fattore su cui è possibile basare la classificazione dei firewall è rappresentato dalle prestazioni o dalla velocità effettiva. Tuttavia, per la maggior parte dei firewall, i produttori non forniscono dati relativi alla velocità effettiva. Nei casi in cui tali valori vengono forniti, cosa che accade in genere per i dispositivi firewall di tipo hardware, non viene seguito alcun processo di misurazione standard e questo rende difficili i confronti tra i diversi produttori. Ad esempio, una delle unità di misura in uso è il numero di bit al secondo (bps), ma poiché il firewall passa di fatto pacchetti IP, questa unità di misura non ha alcun significato se non viene specificata la dimensione del pacchetto utilizzata per misurare la velocità.

Nelle seguenti sezioni le singole classi di firewall vengono definite in maggiore dettaglio.

[](#mainsection)[Inizio pagina](#mainsection)

### Classe 1: firewall personale

Un firewall personale è un servizio software che offre semplici funzionalità firewall per un PC. L'uso di firewall personali è cresciuto di pari passo all'aumento del numero di connessioni Internet permanenti, che si stanno rapidamente affermando su quelle remote.

Sebbene sia progettato per proteggere un singolo computer, un firewall personale è in grado di proteggere anche una rete di piccole dimensioni, se il computer in cui è installato condivide la connessione a Internet con altri computer della rete interna. Tuttavia, questo tipo di firewall ha prestazioni limitate e riduce anche le prestazioni del PC in cui è installato. I meccanismi di protezione sono in genere meno efficaci di quelli di una soluzione firewall dedicata, perché si limitano a bloccare gli indirizzi IP e delle porte, sebbene per un PC sia normalmente richiesto un livello di protezione più basso.

I firewall personali possono essere già forniti in un sistema operativo o essere disponibili a un costo estremamente ridotto. Svolgono bene la funzione per cui sono stati progettati ma, a causa delle prestazioni e delle funzionalità limitate, se ne sconsiglia l'utilizzo in una rete aziendale, anche se solo per filiali di piccole dimensioni. I firewall personali sono, tuttavia, particolarmente adatti a utenti mobili che operano su computer laptop.

Le capacità e il prezzo dei firewall personali possono variare in maniera significativa. Tuttavia, l'assenza di una specifica funzionalità, in particolare in un laptop, può non essere così importante. Nella tabella che segue sono riportate le funzionalità generalmente disponibili nei firewall personali.

**Tabella 1. Classe 1: firewall personali**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristica del firewall</th>
<th style="border:1px solid black;" >Valore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Funzionalità di base supportate</td>
<td style="border:1px solid black;">La maggior parte dei firewall personali supporta i filtri di pacchetti statici e le tecnologie NAT e Stateful Inspection, mentre solo alcuni supportano il controllo a livello di circuito e/o il filtraggio a livello di applicazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configurazione</td>
<td style="border:1px solid black;">Automatica (è disponibile anche l'opzione manuale)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco o autorizzazione degli indirizzi IP</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Blocco o autorizzazione del protocollo o dei numeri di porta</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco o autorizzazione dei messaggi ICMP in ingresso</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllo dell'accesso in uscita</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protezione delle applicazioni</td>
<td style="border:1px solid black;">Possibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Segnalazioni acustiche o avvisi visivi</td>
<td style="border:1px solid black;">Possibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">File di registro degli attacchi</td>
<td style="border:1px solid black;">Possibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Avvisi in tempo reale</td>
<td style="border:1px solid black;">Possibile</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VPN</td>
<td style="border:1px solid black;">No (nella maggior parte dei casi)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gestione remota</td>
<td style="border:1px solid black;">No (nella maggior parte dei casi)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto da parte del produttore</td>
<td style="border:1px solid black;">Diverse possibilità a seconda del prodotto</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Opzione di elevata disponibilità</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Numero di sessioni simultanee</td>
<td style="border:1px solid black;">Da 1 a 10</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Possibilità di aggiornamento modulare (hardware o software)</td>
<td style="border:1px solid black;">Da nessuna a limitata</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Categoria di prezzo</td>
<td style="border:1px solid black;">Bassa (prodotti in alcuni casi gratuiti)</td>
</tr>
</tbody>
</table>
  
I firewall personali offrono i seguenti vantaggi e svantaggi.
  
#### Vantaggi
  
Tra i vantaggi dei firewall personali sono inclusi:
  
-   Economicità  
    Quando è richiesto un numero limitato di licenze, i firewall personali sono una scelta estremamente economica. Nelle versioni del sistema operativo Microsoft Windows® XP è integrato un firewall personale. Sono inoltre disponibili, gratuitamente o a un costo ridotto, prodotti aggiuntivi che funzionano con altre versioni di Windows o altri sistemi operativi.
  
-   Semplicità di configurazione  
    I prodotti firewall personali hanno in genere configurazioni di base pronte all'uso con opzioni di configurazione semplici e dirette.
  
#### Svantaggi
  
Tra gli svantaggi dei firewall personali sono inclusi:
  
-   Difficoltà di gestione centralizzata  
    I firewall personali devono essere configurati in ogni client, causando quindi un ulteriore carico di gestione.
  
-   Esclusivo controllo di base  
    La configurazione tende a essere solo una combinazione di filtraggio di pacchetti statici e blocco di applicazioni basato sulle autorizzazioni.
  
-   Limitazioni delle prestazioni  
    I firewall personali sono progettati per proteggere un singolo PC. Se li si utilizza in un computer che funge da router per una rete di piccole dimensioni, le prestazioni ne risulteranno compromesse.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 2: router con funzionalità firewall
  
I router supportano in genere una o più delle funzionalità firewall descritte in precedenza; possono essere suddivisi in dispositivi di fascia bassa, progettati per le connessioni Internet, e router tradizionali di fascia alta. I router di fascia bassa offrono funzionalità firewall di base per bloccare o autorizzare indirizzi IP e numeri di porta specifici e si avvalgono della tecnologia NAT per nascondere gli indirizzi IP interni. Includono spesso la funzionalità firewall come opzione standard, ottimizzata per bloccare le intrusioni da Internet e, sebbene non richiedano alcuna configurazione, possono essere perfezionati con operazioni di configurazione.
  
I router di fascia alta possono essere configurati per restringere l'accesso bloccando le intrusioni più comuni, quali, ad esempio, i ping, e implementando altre restrizioni sugli indirizzi IP e le porte attraverso l'utilizzo di elenchi di controllo di accesso (ACL). In alcuni casi possono essere disponibili funzionalità firewall aggiuntive che garantiscono il filtraggio di pacchetti di tipo Stateful Inspection in alcuni router. Nei router di fascia alta, le funzionalità firewall sono simili a quelle di un dispositivo firewall hardware; hanno un costo più basso ma garantiscono anche una velocità effettiva più bassa.
  
**Tabella 2. Classe 2: router con funzionalità firewall**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristica del firewall</th>
<th style="border:1px solid black;" >Valore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Funzionalità di base supportate</td>
<td style="border:1px solid black;">La maggior parte dei router con funzionalità firewall supportano filtri di pacchetti statici. I router di fascia più bassa supportano in genere NAT, quelli di fascia più alta, invece, possono supportare il filtraggio in modalità Stateful Inspection e/o a livello di applicazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configurazione</td>
<td style="border:1px solid black;">In genere automatica per i router di fascia più bassa (con opzioni manuali). Spesso manuale nei router di fascia più alta.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco o autorizzazione degli indirizzi IP</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Blocco o autorizzazione del protocollo o dei numeri di porta</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco o autorizzazione dei messaggi ICMP in ingresso</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllo dell'accesso in uscita</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protezione delle applicazioni</td>
<td style="border:1px solid black;">Possibile</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Segnalazioni acustiche o avvisi visivi</td>
<td style="border:1px solid black;">Sì (nella maggior parte dei casi)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">File di registro degli attacchi</td>
<td style="border:1px solid black;">In molti casi</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Avvisi in tempo reale</td>
<td style="border:1px solid black;">In molti casi</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VPN</td>
<td style="border:1px solid black;">Frequente nei router di fascia più bassa, non così comune in quelli di fascia più alta. Per questa attività sono disponibili dispositivi o server dedicati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gestione remota</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto da parte del produttore</td>
<td style="border:1px solid black;">Di norma limitato nei router di fascia più bassa e di buon livello in quelli di fascia più alta.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Disponibilità dell'opzione di elevata disponibilità</td>
<td style="border:1px solid black;">Fascia bassa: No - Fascia alta: Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Numero di sessioni simultanee</td>
<td style="border:1px solid black;">10 - 1.000</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Possibilità di aggiornamento modulare (hardware o software)</td>
<td style="border:1px solid black;">Fascia bassa: No - Fascia alta: Limitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Categoria di prezzo</td>
<td style="border:1px solid black;">Da bassa ad alta</td>
</tr>
</tbody>
</table>
  
I router con funzionalità firewall offrono i seguenti vantaggi e svantaggi.
  
#### Vantaggi
  
Tra i vantaggi dei router con funzionalità firewall sono inclusi:
  
-   Economicità della soluzione  
    L'attivazione di una funzionalità firewall esistente nel router non comporta costi supplementari rispetto al prezzo del router e non richiede hardware aggiuntivo.
  
-   Possibilità di consolidamento della configurazione  
    La configurazione della funzionalità firewall può essere eseguita quando il router viene configurato per le normali operazioni, riducendo così al minimo le risorse di gestione necessarie. Questa soluzione è particolarmente adatta per le filiali, poiché consente di ridurre l'hardware di rete e di semplificarne la gestione.
  
-   Protezione degli investimenti  
    Il personale operativo ha dimestichezza con la configurazione e la gestione del router con funzionalità firewall, quindi non è richiesto un periodo di apprendimento. Il cablaggio della rete è semplificato poiché non devono essere installati componenti hardware aggiuntivi e, quindi, anche la gestione della rete diventa più semplice.
  
#### Svantaggi
  
Tra gli svantaggi dei router con funzionalità firewall sono inclusi:
  
-   Funzionalità limitata  
    In generale, i router di fascia bassa offrono solo funzionalità firewall di base. I router di fascia più alta in genere offrono funzionalità firewall di livello superiore, ma richiedono un elaborato processo di configurazione che in gran parte viene svolto mediante l'aggiunta di controlli che, se dimenticati, impediscono la corretta configurazione.
  
-   Esclusivo controllo di base  
    La configurazione tende a essere solo una combinazione di filtraggio di pacchetti statici e blocco di applicazioni basato sulle autorizzazioni.
  
-   Impatto sulle prestazioni  
    L'utilizzo della funzionalità firewall compromette le prestazioni del router e rallenta la funzione di routing, che costituisce l'attività principale del dispositivo.
  
-   Prestazioni del file di registro  
    L'utilizzo di un file di registro per rilevare le attività anomale può compromettere le prestazioni del router, in particolar modo quando subisce un attacco.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 3: firewall hardware di fascia bassa
  
Nella fascia più bassa delle classi di firewall hardware sono collocate le unità Plug-and-Play, che richiedono una configurazione praticamente nulla. Tali dispositivi spesso includono anche switch e/o funzionalità VPN. I firewall hardware di fascia bassa sono rivolti alle piccole aziende e all'uso interno da parte di grandi organizzazioni. Offrono in genere funzionalità di filtro statico e di gestione remota di base. I dispositivi forniti da grandi produttori possono eseguire lo stesso software utilizzato dai rispettivi omologhi di fascia alta, avvalendosi di un percorso di aggiornamento, se necessario.
  
**Tabella 3. Classe 3: firewall hardware di fascia bassa**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristica del firewall</th>
<th style="border:1px solid black;" >Valore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Funzionalità di base supportate</td>
<td style="border:1px solid black;">La maggior parte dei firewall hardware di fascia bassa supporta i filtri di pacchetti statici e la tecnologia NAT. In alcuni casi possono supportare anche la tecnologia Stateful Inspection e/o il filtro a livello di applicazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configurazione</td>
<td style="border:1px solid black;">Automatica (è disponibile anche l'opzione manuale)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco o autorizzazione degli indirizzi IP</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Blocco o autorizzazione del protocollo o dei numeri di porta</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco o autorizzazione dei messaggi ICMP in ingresso</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllo dell'accesso in uscita</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protezione delle applicazioni</td>
<td style="border:1px solid black;">No (nella maggior parte dei casi)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Segnalazioni acustiche o avvisi visivi</td>
<td style="border:1px solid black;">No (nella maggior parte dei casi)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">File di registro degli attacchi</td>
<td style="border:1px solid black;">No (nella maggior parte dei casi)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Avvisi in tempo reale</td>
<td style="border:1px solid black;">No (nella maggior parte dei casi)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VPN</td>
<td style="border:1px solid black;">In alcuni casi</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gestione remota</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto da parte del produttore</td>
<td style="border:1px solid black;">Limitato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Disponibilità dell'opzione di elevata disponibilità</td>
<td style="border:1px solid black;">No (nella maggior parte dei casi)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Numero di sessioni simultanee</td>
<td style="border:1px solid black;">&gt; 10 - 7.500</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Possibilità di aggiornamento modulare (hardware o software)</td>
<td style="border:1px solid black;">Limitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Categoria di prezzo</td>
<td style="border:1px solid black;">Bassa</td>
</tr>
</tbody>
</table>
  
I firewall hardware di fascia bassa offrono i seguenti vantaggi e svantaggi.
  
#### Vantaggi
  
Tra i vantaggi dei firewall hardware di fascia bassa sono inclusi:
  
-   Economicità  
    I firewall di fascia bassa hanno prezzi contenuti.
  
-   Semplicità di configurazione  
    Non è praticamente richiesta alcuna configurazione.
  
#### Svantaggi
  
Tra gli svantaggi dei firewall hardware di fascia bassa sono inclusi:
  
-   Funzionalità limitata  
    In generale, i firewall hardware di fascia bassa offrono solo funzionalità di base. Non possono essere eseguiti in parallelo per garantire la ridondanza.
  
-   Velocità effettiva estremamente ridotta  
    I firewall hardware di fascia bassa non sono progettati per gestire connessioni con velocità effettiva elevata e questo può causare colli di bottiglia.
  
-   Supporto tecnico limitato da parte del produttore  
    Trattandosi di prodotti con costi contenuti, il supporto del produttore in genere si limita alla posta elettronica e/o a un sito Web.
  
-   Aggiornabilità limitata  
    In genere, non è possibile eseguire aggiornamenti hardware, sebbene siano spesso disponibili aggiornamenti firmware periodici.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 4: firewall hardware di fascia alta
  
Nella fascia più alta delle classi di firewall hardware sono inclusi prodotti con prestazioni e capacità di recupero elevate, adatti alle grandi aziende o ai provider di servizi. Questi prodotti in genere garantiscono un livello di protezione ottimale, senza compromettere le prestazioni della rete.
  
È possibile garantire capacità di recupero aggiungendo un altro firewall come un'unità di hot standby, che gestisce la tabella delle connessioni attive mediante la sincronizzazione automatica con informazioni sullo stato.
  
È consigliabile utilizzare i firewall in ogni rete connessa a Internet, poiché le intrusioni sono all'ordine del giorno, così come gli attacchi DoS, i tentativi di acquisizione e di danneggiamento dei dati. Le unità firewall di fascia alta sono adatte all'installazione nelle sedi centrali o principali di un'azienda.
  
**Tabella 4. Classe 4: firewall hardware di fascia alta**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristica del firewall</th>
<th style="border:1px solid black;" >Valore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Funzionalità di base supportate</td>
<td style="border:1px solid black;">La maggior parte dei firewall hardware di fascia alta supporta i filtri di pacchetti statici e la tecnologia NAT. In alcuni casi possono supportare anche la tecnologia Stateful Inspection e/o il filtro a livello di applicazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configurazione</td>
<td style="border:1px solid black;">Manuale (nella maggior parte dei casi)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco o autorizzazione degli indirizzi IP</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Blocco o autorizzazione del protocollo o dei numeri di porta</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco o autorizzazione dei messaggi ICMP in ingresso</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllo dell'accesso in uscita</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protezione delle applicazioni</td>
<td style="border:1px solid black;">Potenziale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Segnalazioni acustiche o avvisi visivi</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">File di registro degli attacchi</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Avvisi in tempo reale</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VPN</td>
<td style="border:1px solid black;">Potenziale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gestione remota</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto da parte del produttore</td>
<td style="border:1px solid black;">Di buon livello</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Disponibilità dell'opzione di elevata disponibilità</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Numero di sessioni simultanee</td>
<td style="border:1px solid black;">&gt; 7.500 - 500.000</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Possibilità di aggiornamento modulare (hardware o software)</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Categoria di prezzo</td>
<td style="border:1px solid black;">Alta</td>
</tr>
</tbody>
</table>
  
I firewall hardware di fascia alta offrono i seguenti vantaggi e svantaggi.
  
#### Vantaggi
  
Tra i vantaggi dei firewall hardware di fascia alta sono inclusi:
  
-   Prestazioni elevate  
    I prodotti firewall hardware sono progettati per un singolo scopo e garantiscono livelli elevati di blocco delle intrusioni compromettendo solo minimamente le prestazioni.
  
-   Elevata disponibilità  
    I firewall hardware di fascia alta possono essere collegati tra loro per garantire una disponibilità e un bilanciamento del carico ottimali.
  
-   Sistemi modulari  
    Sia l'hardware che il software possono essere aggiornati per soddisfare esigenze in continua evoluzione. Gli aggiornamenti hardware possono includere porte Ethernet aggiuntive, mentre quelli software possono includere la funzione di rilevamento di nuovi metodi di intrusione.
  
-   Gestione remota  
    I firewall hardware di fascia alta offrono funzionalità di gestione remota migliori di quelle di prodotti omologhi di fascia bassa.
  
-   Capacità di recupero  
    I firewall hardware di fascia alta possono avere funzionalità di disponibilità e capacità di recupero come le modalità hot o active standby con una seconda unità.
  
-   Filtraggio a livello di applicazione  
    A differenza dei corrispettivi prodotti di fascia bassa, i firewall hardware di fascia alta consentono di filtrare le applicazioni più comuni ai livelli 4, 5, 6 e 7 del modello OSI.
  
#### Svantaggi
  
Tra gli svantaggi dei firewall hardware di fascia alta sono inclusi:
  
-   Costi elevati  
    I firewall hardware di fascia alta sono in genere costosi. Sebbene sia possibile acquistare alcuni prodotti per appena 100 euro, i costi salgono in modo significativo per i firewall di una rete aziendale, poiché il prezzo spesso dipende dal numero di sessioni simultanee, dalla velocità effettiva e dai requisiti di disponibilità.
  
-   Complessità di configurazione e gestione  
    Poiché i firewall hardware di fascia alta presentano capacità più sofisticate rispetto ai prodotti di fascia bassa, richiedono anche attività di configurazione e gestione più complesse.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Classe 5: firewall server di fascia alta
  
È disponibile un'ampia gamma di prodotti per l'aggiunta di capacità firewall a un server di fascia alta, che garantiscono una protezione rapida ed efficace nei sistemi hardware e software standard. I vantaggi di un approccio di questo tipo sono costituiti dall'uso di strumenti hardware o software già noti, con conseguente riduzione del numero di voci dell'inventario, formazione e gestione semplificata, affidabilità e possibilità di espansione. Molti dei prodotti firewall hardware di fascia alta sono implementati su piattaforme hardware standard con sistemi operativi standard (non visibili) e sono quindi molto simili da un punto di vista tecnico o in termini di prestazioni ai firewall di tipo server. Tuttavia, poiché il sistema operativo è ancora visibile, la funzionalità firewall del server può essere aggiornata per aumentarne la capacità di recupero con tecniche come il clustering.
  
Inoltre, poiché il firewall di tipo server altro non è che un server che esegue un sistema operativo molto comune, è possibile aggiungervi software e funzionalità di diversi fornitori, a differenza dei firewall hardware che devono utilizzare prodotti di un unico fornitore. La dimestichezza con il sistema operativo può consentire, inoltre, una protezione di tipo firewall più efficace, poiché la configurazione dei prodotti appartenenti ad alcune delle altre classi indicate richiede competenze di livello piuttosto elevato.
  
Questa classe è adatta a quelle situazioni in cui sono stati fatti elevati investimenti in una particolare piattaforma hardware o software, poiché l'uso della stessa piattaforma per il firewall rende più semplici le attività di gestione.
  
I prodotti di questa classe garantiscono inoltre funzionalità di caching di grande efficacia.
  
**Tabella 5. Classe 5: firewall server di fascia alta**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Caratteristica del firewall</th>
<th style="border:1px solid black;" >Valore</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Funzionalità supportate</td>
<td style="border:1px solid black;">La maggior parte dei firewall di tipo server di fascia alta supporta i filtri dei pacchetti statici e la tecnologia NAT. Può supportare anche la tecnologia Stateful Inspection e/o il filtraggio a livello di applicazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Configurazione</td>
<td style="border:1px solid black;">Manuale (nella maggior parte dei casi)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco o autorizzazione degli indirizzi IP</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Blocco o autorizzazione del protocollo o dei numeri di porta</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blocco o autorizzazione dei messaggi ICMP in ingresso</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllo dell'accesso in uscita</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protezione delle applicazioni</td>
<td style="border:1px solid black;">Potenziale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Segnalazioni acustiche o avvisi visivi</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">File di registro degli attacchi</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Avvisi in tempo reale</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto VPN</td>
<td style="border:1px solid black;">Potenziale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gestione remota</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Supporto da parte del produttore</td>
<td style="border:1px solid black;">Di buon livello</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Disponibilità dell'opzione di elevata disponibilità</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Numero di sessioni simultanee</td>
<td style="border:1px solid black;">Oltre 50.000 (su più segmenti di rete)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Possibilità di aggiornamento modulare (hardware o software)</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Altro</td>
<td style="border:1px solid black;">Sistema operativo di uso comune</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Categoria di prezzo</td>
<td style="border:1px solid black;">Alta</td>
</tr>
</tbody>
</table>
  
I firewall di tipo server offrono i seguenti vantaggi e svantaggi.
  
#### Vantaggi
  
Tra i vantaggi dei firewall di tipo server sono inclusi:
  
-   Prestazioni elevate  
    Quando vengono eseguiti su un server di dimensione adeguata, questi firewall sono in grado di offrire livelli di prestazioni elevati.
  
-   Integrazione e consolidamento di servizi  
    I firewall di tipo server possono utilizzare varie funzionalità del sistema operativo su cui sono in esecuzione. Ad esempio, un software firewall in esecuzione nel sistema operativo Windows Server(tm) 2003 può avvalersi della funzionalità Bilanciamento carico di rete incorporata nel sistema operativo. Inoltre, il firewall può fungere anche da server VPN, utilizzando di nuovo funzionalità di Windows Server 2003.
  
-   Disponibilità, capacità di recupero e scalabilità  
    Poiché questo firewall viene eseguito su hardware per PC standard, garantisce la disponibilità, la capacità di recupero e la scalabilità della piattaforma PC su cui viene eseguito.
  
#### Svantaggi
  
Tra gli svantaggi dei firewall di tipo server sono inclusi:
  
-   Necessità di hardware di fascia alta  
    Per garantire prestazioni elevate, la maggior parte dei firewall di tipo server richiede hardware di fascia alta in termini di CPU, memoria e interfacce di rete.
  
-   Esposizione alle vulnerabilità  
    Poiché i prodotti firewall di tipo server vengono eseguiti su sistemi operativi molto noti, sono esposti alle vulnerabilità presenti nel sistema operativo e nelle altre applicazioni software in esecuzione sul server. Sebbene ciò accada anche per i firewall hardware, questi ultimi hanno il vantaggio di avere sistemi operativi generalmente meno noti ai pirati informatici della maggior parte dei sistemi operativi server.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Uso di firewall perimetrali
  
Un firewall perimetrale risponde ai requisiti degli utenti esterni ai confini dell'organizzazione. I tipi di utente possono includere:
  
-   Trusted  
    Dipendenti dell'organizzazione, ad esempio impiegati di succursali, utenti remoti o utenti che lavorano da casa.
  
-   Semi-trusted  
    Partner aziendali dell'organizzazione, per i quali è previsto un livello di trust più alto di quello degli utenti non attendibili ma in genere più basso di quello dei dipendenti dell'organizzazione.
  
-   Untrusted  
    Ad esempio, utenti del sito Web pubblico dell'organizzazione.
  
È importante notare che il firewall perimetrale è particolarmente esposto agli attacchi esterni poiché un intruso che voglia accedere alla rete deve necessariamente violarlo. Di conseguenza esso diventa il primo ostacolo da infrangere.
  
I firewall utilizzati come risorsa di confine rappresentano la via d'accesso dell'organizzazione al mondo esterno. La classe di firewall implementata nelle grandi organizzazioni in questo contesto è solitamente un firewall hardware di fascia alta o di tipo server, sebbene alcune organizzazioni utilizzino firewall router. Quando si sceglie la classe firewall da utilizzare come firewall perimetrale, è necessario considerare diversi aspetti. Nella tabella che segue sono evidenziati tali fattori.
  
**Tabella 6. Fattori che determinano la scelta di una classe di firewall perimetrali**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Fattore da valutare</th>
<th style="border:1px solid black;" >Caratteristiche tipiche del firewall implementato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Funzionalità firewall richieste, secondo quanto specificato dall'amministratore della protezione</td>
<td style="border:1px solid black;">Occorre trovare un giusto compromesso tra il grado di protezione richiesto e il costo di un incremento della protezione in termini economici e di riduzione delle prestazioni. Sebbene molte organizzazioni desiderino ottenere la massima protezione da un firewall perimetrale, ne esistono alcune che non sono disposte ad accettare la conseguente riduzione delle prestazioni. Ad esempio, nei siti Web non collegati all'e-commerce dai volumi molto elevati, è possibile applicare livelli di protezione più bassi in considerazione dei livelli di velocità effettiva più alti ottenuti utilizzando i filtri di pacchetti statici invece del filtraggio a livello di applicazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Valutazione della tipologia di firewall, che potrà essere un dispositivo fisico dedicato o un firewall logico su un dispositivo fisico oppure potrà offrire anche altre funzionalità</td>
<td style="border:1px solid black;">In quanto punto di collegamento tra Internet e la rete aziendale, il firewall perimetrale è spesso implementato come dispositivo dedicato allo scopo di ridurre al minimo la superficie esposta agli attacchi e la possibilità di accesso alle reti interne in caso di violazione del dispositivo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Requisiti di gestibilità del dispositivo, secondo quanto specificato nell'architettura di gestione dell'organizzazione</td>
<td style="border:1px solid black;">È utilizzato in genere un metodo di registrazione e richiesto un meccanismo di monitoraggio degli eventi. È possibile scegliere di non consentire l'amministrazione remota per impedire a utenti malintenzionati di amministrare il dispositivo in remoto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Requisiti di velocità effettiva, probabilmente definiti dagli amministratori di rete e dei servizi dell'organizzazione</td>
<td style="border:1px solid black;">Questi requisiti variano da ambiente ad ambiente, ma la potenza dell'hardware del dispositivo o del server e le funzionalità firewall in uso determineranno la velocità effettiva globale della rete disponibile.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Requisiti di disponibilità</td>
<td style="border:1px solid black;">In quanto via d'accesso a Internet nelle grandi aziende, è spesso richiesto un elevato livello di disponibilità, soprattutto se il firewall perimetrale viene utilizzato per proteggere un sito Web che genera profitti per l'azienda.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Regole per i firewall perimetrali
  
Nella sezione che segue il termine "bastion host" viene utilizzato per indicare server situati nella rete perimetrale che forniscono servizi agli utenti interni ed esterni. Sono bastion host, ad esempio, i server Web e VPN.
  
In genere per il firewall perimetrale devono essere implementate le seguenti regole, per impostazione predefinita o con operazioni di configurazione:
  
-   Impedire tutto il traffico ad eccezione di quello autorizzato in modo esplicito.
  
-   Bloccare i pacchetti in ingresso che presentano un indirizzo IP di origine della rete interna o perimetrale.
  
-   Bloccare i pacchetti in uscita che presentano un indirizzo IP di origine esterno (il traffico può avere origine solo dai bastion host).
  
-   Consentire le query e le risposte DNS su base UDP dal resolver DNS ai server DNS in Internet.
  
-   Consentire le query e le risposte DNS su base UDP dai server DNS Internet all'advertiser DNS.
  
-   Consentire ai client esterni UDP di inviare query all'advertiser DNS e fornire una risposta.
  
-   Consentire le query e le risposte DNS su base TCP dai server DNS Internet all'advertiser DNS.
  
-   Consentire la posta in uscita dal bastion host SMTP in uscita a Internet.
  
-   Consentire la posta in ingresso da Internet al bastion host SMTP in ingresso.
  
-   Consentire al traffico che ha origine dai server proxy di raggiungere Internet.
  
-   Consentire il reindirizzamento delle risposte proxy da Internet ai server proxy della rete perimetrale.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Requisiti hardware
  
I requisiti hardware di un firewall perimetrale sono diversi a seconda che il firewall sia di tipo software o di tipo hardware, come indicato brevemente di seguito:
  
-   Firewall basati sull'hardware  
    Questi dispositivi eseguono in genere codice specifico su una piattaforma hardware personalizzata. Questi firewall vengono di norma scalati (e viene loro assegnato un prezzo) in base al numero di connessioni che sono in grado di gestire e alla complessità del software da eseguire.
  
-   Firewall basati sul software  
    Si tratta sempre di dispositivi configurati in base al numero di connessioni simultanee e alla complessità del software firewall. Esistono sistemi in grado di calcolare la velocità del processore, la dimensione della memoria e lo spazio su disco necessari per un server in base al numero di connessioni supportate. Occorre tener conto delle altre applicazioni software che potrebbero essere in esecuzione sul server firewall, come quelle per il bilanciamento del carico e VPN. Occorre valutare, inoltre, i metodi per garantire la scalabilità verticale e orizzontale del firewall. Questi metodi includono l'aumento della potenza del sistema mediante l'aggiunta di ulteriori processori, memoria e schede di rete e anche l'utilizzo di più sistemi e del bilanciamento del carico per distribuire l'attività del firewall su di essi (vedere la sezione "[Scalabilità](http://www.microsoft.com/italy/technet/security/guidance/perimeter_firewall_design/secmod156.mspx)" più avanti in questo modulo). Alcuni prodotti si avvalgono di sistemi con più processori simmetrici (SMP) per aumentare le prestazioni. Il servizio Bilanciamento carico di rete di Windows Server 2003 può garantire tolleranza d'errore, elevata disponibilità, efficienza e miglioramento delle prestazioni per alcuni prodotti firewall di tipo software.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Disponibilità del firewall
  
Per aumentare la disponibilità del firewall perimetrale, è possibile implementarlo come singolo dispositivo firewall con componenti ridondanti o come coppia ridondante di firewall che incorpora un meccanismo di failover e/o bilanciamento del carico. I vantaggi e gli svantaggi di tali opzioni sono riportati nelle sottosezioni che seguono.
  
#### Firewall singolo senza componenti ridondanti
  
Nella figura 2 è illustrato un firewall singolo senza componenti ridondanti:
  
![](images/Cc700828.SGFG15602(it-it,TechNet.10).gif "Firewall singolo senza componenti ridondanti")
  
Figura 2  
*Firewall singolo senza componenti ridondanti*
  
L'utilizzo di un firewall singolo senza componenti ridondanti offre i seguenti vantaggi e svantaggi.
  
##### Vantaggi
  
Tra i vantaggi di un firewall singolo senza ridondanza sono inclusi:
  
-   Economicità  
    Poiché è presente un solo firewall, i costi dell'hardware e delle licenze sono contenuti.
  
-   Semplicità di gestione  
    La gestione è semplificata poiché nel sito o nella rete aziendale è presente un solo firewall.
  
-   Origine di registrazione singola  
    Tutta la registrazione del traffico è centralizzata in un unico dispositivo.
  
##### Svantaggi
  
Tra gli svantaggi di un firewall singolo senza ridondanza sono inclusi:
  
-   Singolo punto di errore  
    Esiste un singolo punto di errore per l'accesso a Internet in ingresso e/o in uscita.
  
-   Possibile collo di bottiglia del traffico  
    La presenza di un unico firewall potrebbe costituire un collo di bottiglia del traffico in relazione al numero di connessioni e alla velocità effettiva richiesta.
  
#### Firewall singolo con componenti ridondanti
  
Nella figura 3 è illustrato un livello di firewall singolo con componenti ridondanti:
  
![](images/Cc700828.SGFG15603(it-it,TechNet.10).gif "Firewall singolo con componenti ridondanti")
  
Figura 3  
*Firewall singolo con componenti ridondanti*
  
L'utilizzo di un firewall singolo con componenti ridondanti offre i seguenti vantaggi e svantaggi.
  
##### Vantaggi
  
Tra i vantaggi di un firewall singolo con componenti ridondanti sono inclusi:
  
-   Economicità  
    Poiché è presente un solo firewall, i costi dell'hardware e delle licenze sono contenuti. Il costo dei componenti ridondanti, come l'alimentatore, non è alto.
  
-   Semplicità di gestione  
    La gestione è semplificata poiché nel sito o nella rete aziendale è presente un solo firewall.
  
-   Origine di registrazione singola  
    Tutta la registrazione del traffico è centralizzata in un unico dispositivo.
  
##### Svantaggi
  
Tra gli svantaggi di un firewall singolo con componenti ridondanti sono inclusi:
  
-   Singolo punto di errore  
    A seconda del numero di componenti ridondanti, potrebbe continuare a essere presente un singolo punto di errore per l'accesso a Internet in ingresso e/o in uscita.
  
-   Costo  
    Il costo è più elevato di quello di un firewall senza ridondanza, inoltre, potrebbe essere necessaria una classe di firewall più alta per poter incorporare la ridondanza.
  
-   Possibile collo di bottiglia del traffico  
    La presenza di un unico firewall potrebbe costituire un collo di bottiglia del traffico in relazione al numero di connessioni e alla velocità effettiva richiesta.
  
#### Firewall con tolleranza d'errore
  
Un set di firewall con tolleranza d'errore include un meccanismo per duplicare ogni firewall, come illustrato nella figura 4.
  
![](images/Cc700828.SGFG15604(it-it,TechNet.10).gif "Firewall con tolleranza d'errore")
  
Figura 4  
*Firewall con tolleranza d'errore*
  
L'utilizzo di un firewall con tolleranza d'errore offre i seguenti vantaggi e svantaggi.
  
##### Vantaggi
  
Tra i vantaggi di un set di firewall con tolleranza d'errore sono inclusi:
  
-   Tolleranza d'errore  
    L'uso di coppie di server o dispostivi consente di garantire il livello richiesto di tolleranza d'errore.
  
-   Registrazione centralizzata  
    Tutta la registrazione del traffico è centralizzata in una coppia di dispositivi strettamente collegati tra loro.
  
-   Possibilità di condivisione dello stato  
    A seconda del fornitore del dispositivo, i firewall di questo livello potrebbero essere in grado di condividere lo stato delle sessioni.
  
##### Svantaggi
  
Tra gli svantaggi di un set di firewall con tolleranza d'errore sono inclusi:
  
-   Aumento della complessità  
    L'impostazione e il supporto di questo tipo di soluzione sono più complessi a causa della natura a percorsi multipli del traffico di rete.
  
-   Complessità di configurazione  
    Le serie separate di regole firewall, se non correttamente configurate, possono provocare problemi di protezione e supporto.
  
Negli scenari esaminati il firewall poteva essere di tipo hardware o software. Nelle figure precedenti il firewall funge da punto di collegamento tra l'organizzazione e Internet, mentre il router di confine è posizionato all'esterno del firewall. Questo tipo di router è estremamente vulnerabile alle intrusioni, quindi richiede la configurazione di determinate funzionalità firewall. Senza una serie completa di funzionalità firewall è possibile implementare solo limitate capacità firewall e sarà necessario affidarsi al dispositivo firewall per impedire le intrusioni. In alternativa, il firewall può essere consolidato all'interno del router senza richiedere altri dispositivi firewall autonomi.
  
#### Configurazioni dei firewall con tolleranza d'errore
  
Quando si implementa un set di firewall con tolleranza d'errore (definito spesso cluster), esistono due tipologie di configurazione principali, descritte nelle sezioni che seguono.
  
##### Set di firewall con tolleranza d'errore di tipo attivo/passivo
  
In un set di firewall con tolleranza d'errore di tipo attivo/passivo un dispositivo gestisce tutto il traffico, mentre l'altro non svolge alcuna funzione. Entrambi i dispositivi in genere comunicano la disponibilità e/o lo stato della connessione ai nodi partner attraverso una convenzione. Questa comunicazione viene in genere definita "heartbeat"; ogni sistema invia segnalazioni all'altro diverse volte al secondo per verificare che il nodo partner stia gestendo le connessioni. Se il nodo passivo non riceve alcun heartbeat dal nodo attivo per uno specifico intervallo definito dall'utente, assume il ruolo attivo.
  
Nella figura 5 è illustrato un set di firewall con tolleranza d'errore di tipo attivo/passivo.
  
![](images/Cc700828.SGFG15605(it-it,TechNet.10).gif "Set di firewall con tolleranza d'errore di tipo attivo/passivo ")
  
Figura 5  
*Set di firewall con tolleranza d'errore di tipo attivo/passivo*
  
L'utilizzo di un set di firewall con tolleranza d'errore di tipo attivo/passivo offre i seguenti vantaggi e svantaggi.
  
##### Vantaggi
  
Tra i vantaggi di un set di firewall con tolleranza d'errore di tipo attivo/passivo sono inclusi:
  
-   Semplicità di configurazione  
    L'impostazione e le procedure di risoluzione dei problemi in questa configurazione risultano molto semplici, poiché è attivo un singolo percorso di rete alla volta.
  
-   Prevedibilità del carico di failover  
    Poiché l'intero carico di traffico passa al nodo passivo in caso di failover, il traffico che il nodo passivo deve gestire è facilmente pianificabile.
  
##### Svantaggi
  
Tra gli svantaggi di un set di firewall con tolleranza d'errore di tipo attivo/passivo sono inclusi:
  
-   Configurazione inefficiente  
    Il set di firewall con tolleranza d'errore di tipo attivo/passivo è inefficiente, poiché il nodo passivo non offre alcuna funzione utile alla rete durante il normale funzionamento.
  
##### Set di firewall con tolleranza d'errore di tipo attivo/attivo
  
In un set di firewall con tolleranza d'errore di tipo attivo/attivo, due o più nodi sono attivamente in attesa di tutte le richieste inviate a un indirizzo IP virtuale condiviso da ogni nodo. Il carico viene distribuito tra i nodi tramite algoritmi esclusivi del meccanismo di tolleranza d'errore in uso o tramite configurazione statica su base utente, in modo che la funzione di filtro di ogni nodo attivo venga svolta contemporaneamente su un traffico diverso. Nel caso in cui si verifichi un errore in un nodo, gli altri nodi distribuiranno l'elaborazione del carico assegnato al nodo non funzionante.
  
Nella figura 6 è illustrato un set di firewall con tolleranza d'errore di tipo attivo/attivo.
  
![](images/Cc700828.SGFG15606(it-it,TechNet.10).gif "Set di firewall con tolleranza d'errore di tipo attivo/attivo")
  
Figura 6  
*Set di firewall con tolleranza d'errore di tipo attivo/attivo*
  
L'utilizzo di un firewall con tolleranza d'errore di tipo attivo/attivo offre i seguenti vantaggi e svantaggi.
  
##### Vantaggi
  
Tra i vantaggi di un set di firewall con tolleranza d'errore di tipo attivo/attivo sono inclusi:
  
-   Maggiore efficienza  
    Poiché entrambi i firewall offrono un servizio alla rete, questa configurazione risulta più efficiente rispetto al set di firewall con tolleranza d'errore di tipo attivo/passivo.
  
-   Maggiore velocità effettiva  
    In situazioni di normale funzionamento, questa configurazione può gestire livelli più elevati di traffico di quelli gestibili dalla configurazione di tipo attivo/passivo, poiché entrambi i firewall sono in grado di fornire simultaneamente un servizio alla rete.
  
##### Svantaggi
  
Tra gli svantaggi di un set di firewall con tolleranza d'errore di tipo attivo/attivo sono inclusi:
  
-   Potenziale sovraccarico  
    Se si verifica un errore in un nodo, le risorse hardware degli altri nodi potrebbero non essere sufficienti a gestire la velocità effettiva totale richiesta. È importante tenere presente questo fattore nella consapevolezza che è probabile che si verifichi una riduzione delle prestazioni poiché, in caso di errore in un nodo, i nodi funzionanti devono assumersi il carico di lavoro aggiuntivo.
  
-   Aumento della complessità  
    Poiché il traffico di rete può passare attraverso due percorsi, la risoluzione dei problemi diventa più complessa.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Protezione
  
La sicurezza dei prodotti firewall è di fondamentale importanza. Sebbene non esistano standard per la sicurezza dei firewall, l'ICSA (International Computer Security Association), associazione indipendente, esegue un programma di certificazione mirato a verificare la sicurezza dei prodotti firewall in commercio. L'ICSA verifica un numero significativo di prodotti firewall attualmente in commercio (per ulteriori informazioni, visitare il sito Web in lingua inglese all'indirizzo [www.icsalabs.com](http://www.icsalabs.com)).
  
È indispensabile che un firewall risponda agli standard di sicurezza richiesti e, per verificare questa condizione, basta scegliere un prodotto che abbia ottenuto la certificazione ICSA. Inoltre, è consigliabile verificare se per il firewall scelto sono disponibili segnalazioni tecniche. In Internet sono disponibili diversi database delle vulnerabilità della protezione. Esaminando questi database sarà possibile stabilire quali vulnerabilità sono state precedentemente rilevate per il prodotto e quali siano le implicazioni.
  
Purtroppo tutti i prodotti, siano essi basati sull'hardware o sul software, presentano degli errori, comunemente noti come "bug". Oltre a determinare il numero e la gravità dei bug che hanno interessato il prodotto scelto, è importante valutare la capacità e la velocità di risposta del fornitore alle vulnerabilità esposte.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Scalabilità
  
In questa sezione sono indicati i requisiti di scalabilità di una soluzione firewall. La scalabilità dei firewall è in genere determinata dalle caratteristiche di prestazione del dispositivo in uso ed è buona norma scegliere un tipo di firewall che si possa adeguare agli scenari di utilizzo reali. Esistono due metodi di base per ottenere la scalabilità:
  
-   Scalabilità verticale (verso l'alto)  
    In dipendenza del fatto che il firewall sia un dispositivo hardware o una soluzione software in esecuzione su un server, è possibile ottenere diversi livelli di scalabilità aumentando la quantità di memoria, la potenza di elaborazione della CPU e la velocità effettiva delle interfacce di rete. Tuttavia, ogni dispositivo o server ha una serie finita di opzioni di scalabilità verticale. Ad esempio, se si acquista un server che includa socket per quattro CPU e si inizia a utilizzarne solo due, sarà sempre possibile aggiungerne altre due.
  
-   Scalabilità orizzontale (verso l'esterno)  
    Una volta esaurite le possibilità di scalabilità verticale di un server, diventa importante la scalabilità orizzontale. La maggior parte dei firewall (hardware e software) prevede la possibilità di scalabilità orizzontale mediante l'uso di qualche forma di bilanciamento del carico. In uno scenario del genere, più server vengono organizzati in un cluster e considerati come un unico sistema dai client in rete. Si tratta di una situazione simile a quella del cluster di tipo attivo/attivo descritto nella sezione "[Disponibilità del firewall](http://www.microsoft.com/italy/technet/security/guidance/perimeter_firewall_design/secmod156.mspx)" del presente modulo. La tecnologia utilizzata per garantire tale funzionalità può coincidere o meno con quella descritta in precedenza a seconda del fornitore.
  
Garantire la scalabilità verticale dei firewall hardware può essere difficile. Tuttavia, alcuni produttori di firewall hardware offrono soluzioni di scalabilità orizzontale poiché i loro prodotti possono essere disposti in pila per funzionare come una sola unità con bilanciamento del carico.
  
Alcuni firewall di tipo software sono progettati per assicurare la scalabilità verticale attraverso l'uso di più processori. La gestione di diversi processori in genere non è affidata al firewall, bensì al sistema operativo sottostante. Tuttavia, il firewall deve essere in grado di gestire l'hardware per poter utilizzare questa capacità in modo efficace. Questo approccio consente di scalare dispositivi singoli o ridondanti, diversamente dai firewall basati sull'hardware che devono in genere rispettare le limitazioni dell'hardware definite in fase di produzione. La maggior parte dei firewall è classificata in base al numero di connessioni simultanee gestibili. I dispositivi hardware devono spesso essere sostituiti, se i requisiti di connessione superano la disponibilità prevista per il modello di dispositivo a scala fissa.
  
Come si è già rilevato in precedenza, la tolleranza d'errore potrebbe essere incorporata nel sistema operativo di un server firewall. Nel caso di un firewall hardware, la tolleranza d'errore rappresenta probabilmente un costo aggiuntivo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Prestazioni
  
Sono disponibili varie tecnologie che consentono di migliorare le prestazioni di un firewall, tra cui:
  
-   Supporto Gigabit Ethernet/Fiber Channel.
  
-   Proxy, proxy Web inverso e caching.
  
-   Interfacce di gestione SSL.
  
-   Interfacce di gestione IPSec.
  
Nel caso dei firewall di tipo software, per ognuna di queste tecnologie sono disponibili in commercio soluzioni offerte da più fornitori e quindi a costi competitivi. Per i dispositivi hardware, invece, sebbene possano essere disponibili soluzioni simili di terze parti, spesso è possibile ottenerle solo dal produttore del firewall hardware.
  
Nelle sezioni che seguono sono descritte singolarmente queste tecnologie per il miglioramento delle prestazioni.
  
#### Supporto Gigabit Ethernet/Fiber Channel
  
Molti switch, router e firewall possono gestire le interfacce Gigabit Ethernet e la riduzione dei costi di queste interfacce ne ha aumentato la diffusione. Questa capacità in genere riduce il rischio che queste interfacce si trasformino in colli di bottiglia nell'implementazione dei firewall.
  
#### Proxy, proxy Web inverso e caching
  
La funzionalità di caching in genere è disponibile solo nei firewall di tipo software, poiché richiede l'uso di un disco per la memorizzazione nella cache del traffico o dei dati.
  
#### Interfacce di gestione SSL
  
Le schede di accelerazione SSL possono migliorare le prestazioni dei siti Web esposti pubblicamente che utilizzano la crittografia SSL poiché gestiscono l'elaborazione della crittografia al posto della CPU del firewall. Quando la crittografia SSL si conclude nel firewall, questi dispositivi offrono vantaggi significativi.
  
#### Interfacce di gestione IPSec
  
Le schede di accelerazione IPSec possono migliorare le prestazioni dei servizi esposti pubblicamente che utilizzano la crittografia IPSec, come VPN. Questi dispositivi gestiscono l'elaborazione della crittografia al posto della CPU del firewall. La gestione IPSec può essere utilizzata per il traffico tra l'interfaccia interna del firewall e un servizio pubblicato, garantendo così che il traffico in transito nella rete perimetrale sia crittografato tra gli host della rete stessa.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Consolidamento
  
Eseguire un consolidamento significa incorporare il servizio firewall in un altro dispositivo o incorporare altri servizi nel firewall. Tra i vantaggi del consolidamento sono inclusi:
  
-   Prezzo di acquisto più contenuto  
    Incorporando il servizio firewall in un altro servizio, ad esempio in un router, si risparmia il costo di un dispositivo hardware, sebbene il software firewall debba comunque essere acquistato. Analogamente, incorporando altri servizi nel firewall, è possibile evitare il costo di un dispositivo hardware aggiuntivo.
  
-   Riduzione dei costi di gestione e di inventario  
    La riduzione del numero di dispositivi hardware consente di abbassare i costi di gestione, poiché sono richiesti meno aggiornamenti hardware e il cablaggio e la gestione del sistema risultano semplificati.
  
-   Maggiori prestazioni  
    In base al tipo di consolidamento è possibile migliorare le prestazioni. Ad esempio, incorporando la funzionalità di caching del server Web nel firewall, è possibile evitare di utilizzare altri dispositivi consentendo ai servizi di comunicare tra loro a velocità elevata invece che attraverso un cavo Ethernet.
  
Tra gli esempi di consolidamento sono inclusi:
  
-   Aggiunta di servizi firewall al router di confine  
    La maggior parte dei router può prevedere un servizio firewall incorporato. Le funzionalità di tale servizio possono essere molto semplici nei router economici ed estremamente avanzate ed efficienti nei router di fascia alta. In pratica, anche se ci si avvale di un firewall perimetrale separato, il servizio firewall del router di confine deve essere sempre attivo per proteggere il router stesso e gli switch di confine.
  
-   Aggiunta di servizi firewall allo switch di confine  
    A seconda dello switch di confine selezionato, è possibile aggiungere il firewall perimetrale come blade, riducendo i costi e aumentando le prestazioni.
  
-   Aggiunta di cache proxy al firewall perimetrale  
    La funzione di caching proxy memorizza le pagine Web visitate con maggiore frequenza in modo che, alla successiva richiesta, la pagina verrà richiamata dalla cache senza dover accedere nuovamente al server Web. In questo modo si migliorano i tempi di risposta e si riduce il carico di lavoro del server Web. Questa funzionalità in genere può essere incorporata solo in un firewall server, poiché richiede un disco rigido locale per la cache.
  
Quando si ipotizza di consolidare altri servizi nello stesso server o dispositivo che eroga il servizio firewall, è necessario verificare che l'uso di un determinato servizio non comprometta disponibilità, sicurezza e gestibilità del firewall. Non vanno trascurate, inoltre, considerazioni relative alle prestazioni, poiché il carico generato da servizi aggiuntivi compromette le prestazioni del servizio firewall.
  
In alternativa al consolidamento di servizi nello stesso dispositivo o server che ospita il servizio firewall è possibile consolidare un dispositivo hardware firewall come blade in uno switch. Questa procedura è in genere meno costosa di qualsiasi tipo di firewall autonomo e consente di sfruttare le caratteristiche di disponibilità dello switch, come, ad esempio, il doppio alimentatore. Una tale configurazione è anche più semplice da gestire, poiché non implica l'uso di un dispositivo separato. Inoltre, la possibilità di utilizzare il bus dello switch invece di cavi esterni rende la soluzione più veloce.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Standard e linee guida
  
La maggior parte dei protocolli Internet che utilizzano la versione 4 del protocollo Internet (IPv4) può essere protetta da un firewall, sia nel caso di protocolli di basso livello come TCP e UDP sia per quelli di livello più alto come HTTP, SMTP e FTP. Occorre verificare che tutti i prodotti firewall in esame supportino il tipo di traffico richiesto. Alcuni firewall sono anche in grado di interpretare lo standard GRE (Generic Routing Encapsulation), ovvero il protocollo di incapsulamento per il protocollo PPTP (Point-to-Point Tunneling Protocol) utilizzato in alcune implementazioni VPN.
  
Alcuni firewall prevedono filtri a livello di applicazione incorporati per protocolli quali HTTP, SSL, DNS, FTP, SOCKS v4, RPC, SMTP, H. 323 e POP (Post Office Protocol).
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo modulo è stata indicata una procedura per scegliere i prodotti firewall più appropriati. Tale procedura tiene presenti tutti gli aspetti della progettazione dei firewall, inclusi i diversi processi di valutazione e classificazione necessari per ottenere una soluzione.
  
Nessun firewall è assolutamente sicuro. L'unico modo per garantire che la rete non possa essere attaccata elettronicamente dall'esterno è separarla da tutti gli altri sistemi e reti. Il risultato sarebbe una rete sicura ma praticamente inutilizzabile. I firewall consentono di implementare un livello di protezione adeguato per la connessione della rete a una rete esterna o l'unione di due reti interne.
  
Le strategie firewall e i processi di progettazione descritti in questo capitolo devono essere considerati solo una parte di una strategia di protezione globale, poiché anche il firewall più potente ha un valore limitato se esistono punti deboli in altre parti dell'ambiente. La sicurezza è un requisito indispensabile per ogni componente della rete e per ogni componente devono essere definiti criteri di protezione che consentano di ridurre i rischi inerenti all'ambiente.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riferimenti
  
Per ulteriori informazioni sulle caratteristiche e l'implementazione di servizi firewall, visitare i siti Web agli indirizzi indicati di seguito.
  
-   Per informazioni generali sui firewall: [Network Security: Firewalls (TechNet Library)](http://technet.microsoft.com/en-us/library/cc700820.aspx)
  
-   Per informazioni dettagliate sulla protezione in Microsoft Window Server 2003, fare riferimento al documento "Windows Server 2003 Security Center" disponibile all'indirizzo: <http://www.microsoft.com/windowsserver2003/technologies/security/default.mspx>
  
-   Per informazioni sul firewall Microsoft Internet Security & Acceleration Server e il prodotto proxy Web, fare riferimento all'indirizzo: <http://www.microsoft.com/isaserver/>
  
-   Per avvalersi del servizio di notifica gratuita tramite posta elettronica che Microsoft utilizza per inviare informazioni sulla sicurezza dei prodotti Microsoft agli utenti che hanno effettuato sottoscrizioni, visitare il sito Web Microsoft Security Notification Service all'indirizzo: [www.microsoft.com/technet/security/bulletin/notify.asp](http://www.microsoft.com/technet/security/bulletin/notify.asp)
  
-   Le risorse di protezione SANS (SysAdmin, Audit, Network, and Security) Institute sono disponibili all'indirizzo: [http://www.sans.org](http://www.sans.org/)
  
-   Il CERT (Computer Emergency Response Team) registra e pubblica avvisi di protezione e offre un servizio di consulenza sulla protezione all'indirizzo: [http://www.cert.org](http://www.cert.org/)
  
##### Download
  
-   [Windows Server System Reference Architecture](http://www.microsoft.com/downloads/details.aspx?familyid=d44e34ec-b4e2-49a1-9f40-9ed4ba3765df&displaylang=en)
  
[](#mainsection)[Inizio pagina](#mainsection)
