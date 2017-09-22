---
TOCTitle: Panoramica dei concetti relativi ai criteri IPSec
Title: Panoramica dei concetti relativi ai criteri IPSec
ms:assetid: '0a238f1d-2b3f-4422-bf89-365138356224'
ms:contentKeyID: 20200800
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536200(v=TechNet.10)'
---

Isolamento del server e del dominio tramite IPsec e criteri di gruppo
=====================================================================

### Appendice A: Panoramica dei concetti relativi ai criteri IPSec

Aggiornato: 16 febbraio 2005

In questa appendice viene fornita una panoramica dettagliata dei termini, processi e concetti di IPSec. L'appendice intende fornire le nozioni indispensabili per la comprensione di IPSec, come descritto nella guida *Isolamento del server e del dominio tramite IPsec e criteri di gruppo*.

Il contenuto di questa appendice è stato pubblicato originariamente nel white paper "[Using Microsoft Windows IPSec to Help Secure an Internal Corporate Network Server](http://www.microsoft.com/ipsec)" (disponibile in lingua inglese all'indirizzo www.microsoft.com/ipsec), che è stato prodotto in collaborazione da Microsoft e Foundstone Strategic Security.

Le altre informazioni contenute nel white paper descrivono il primo modello per l'utilizzo di IPSec per proteggere l'accesso di rete ai server Microsoft® Windows® interni che elaborano o memorizzano dati riservati. Sebbene queste informazioni aggiuntive non siano necessarie per comprendere la guida *Isolamento del server e del dominio tramite IPsec e criteri di gruppo*, sono comunque utili come informazioni di carattere generale.

##### In questa pagina

[](#ehaa)[Introduzione](#ehaa)
[](#egaa)[Filtri dei criteri IPSec](#egaa)
[](#efaa)[Processo di negoziazione IKE](#efaa)
[](#eeaa)[Metodi di protezione](#eeaa)
[](#edaa)[Modalità di incapsulamento e formati di trasmissione del protocollo IPSec](#edaa)
[](#ecaa)[Autenticazione IKE](#ecaa)
[](#ebaa)[Metodi di autenticazione IKE e ordine di preferenza dei metodi di protezione](#ebaa)
[](#eaaa)[Opzioni della negoziazione di protezione](#eaaa)

### Introduzione

Quando si crea un criterio IPSec, si configurano le regole IPSec (che determinano il comportamento di IPSec) e le impostazioni IPSec (che vengono applicate indipendentemente dalle regole configurate). Dopo aver configurato un criterio IPSec, è necessario assegnarlo a un computer per applicarlo. Benché in un computer possano coesistere più criteri IPSec, è possibile assegnare a un computer solo un criterio IPSec alla volta.

Una regola IPSec stabilisce quali tipi di traffico devono venire esaminati tramite il protocollo IPSec, se il traffico è consentito, bloccato o se è negoziata la protezione, come autenticare un peer IPSec e altre impostazioni. Quando si configura una regola IPSec, si impostano un elenco di filtri contenente uno o più filtri, un'operazione filtro, i metodi di autenticazione, un tipo di connessione e una modalità di incapsulamento IPSec (modalità di trasporto o modalità di tunnel). Una regola IPSec è solitamente configurata per uno scopo specifico (ad esempio, per bloccare tutto il traffico in ingresso da Internet verso la porta TCP 135).

I filtri definiscono il traffico da ispezionare, in modo analogo a una regola del firewall, con indirizzi IP di origine e di destinazione, protocolli e numeri di porta, se applicabili. Un'operazione filtro definisce i requisiti di protezione per il traffico di rete. È possibile configurare un'operazione filtro per consentire, bloccare o negoziare la protezione (negoziare IPSec). Se si configura un'operazione filtro per negoziare la protezione, occorre anche configurare i metodi di protezione per lo scambio delle chiavi (e il loro ordine di preferenza), stabilire se accettare il traffico iniziale non protetto in ingresso, se consentire comunicazioni non protette con i computer che non supportano IPSec e se utilizzare PFS (Perfect Forward Secrecy).

Le impostazioni e i metodi di protezione dello scambio delle chiavi determinano i formati di trasmissione del protocollo IPSec AH (Authentication Header) o IPSec ESP (Encapsulated Security Payload), gli algoritmi di crittografia e hash, la durata delle chiavi e le altre impostazioni necessarie per configurare sia la modalità principale IKE (Internet Key Exchange) sia le associazioni di protezione (SA) IPSec. Un'associazione di protezione (SA) è un accordo sulle impostazioni di protezione associate al materiale delle chiavi. L'SA creata durante la prima fase di negoziazione IKE è denominata SA in modalità principale IKE (o anche SA in modalità principale ISAKMP). L'SA in modalità principale IKE protegge la negoziazione IKE stessa. Le SA create durante la seconda fase di negoziazione IKE sono denominate SA IPSec (o anche SA in modalità rapida IKE, perché ogni negoziazione in modalità rapida IKE negozia l'SA IPSec per ogni direzione). Le SA IPSec proteggono il traffico delle applicazioni.

In questa sezione vengono fornite informazioni sui seguenti importanti concetti dei criteri IPSec:

-   Processo di negoziazione IKE

-   Filtri dei criteri IPSec

-   Metodi di protezione

-   Formati di trasmissione del protocollo IPSec

-   Autenticazione IKE

-   Metodo di autenticazione IKE e ordine di preferenza dei metodi di protezione

-   Opzioni di negoziazione della protezione

Per ulteriori informazioni sui concetti relativi ai criteri IPSec, consultare la Guida in linea e supporto tecnico di Microsoft Windows Server™ 2003.

[](#mainsection)[Inizio pagina](#mainsection)

### Filtri dei criteri IPSec

I filtri sono la parte più importante di un criterio IPSec. Se non si specificano i filtri corretti nei criteri dei client o dei server, o se gli indirizzi IP cambiano prima che vengano aggiornati i filtri dei criteri, la protezione potrebbe non essere garantita. I filtri IPSec sono inseriti nel livello IP dello stack dei protocolli di rete TCP/IP sul computer in modo che possano esaminare (filtrare) tutti i pacchetti IP in ingresso o in uscita. Fatta eccezione per un breve ritardo, che è necessario per negoziare una relazione di protezione tra due computer, IPSec è trasparente per le applicazioni degli utenti finali e i servizi del sistema operativo. I filtri vengono associati a un'operazione filtro corrispondente mediante la regola di protezione in un criterio IPSec. Windows IPSec supporta sia la modalità di tunnel IPSec sia la modalità di trasporto IPSec come opzioni della regola. La configurazione della regola in modalità di tunnel IPSec è molto diversa dalla configurazione in modalità di trasporto.

Le regole di filtraggio associate a un criterio IPSec sono simili alle regole dei firewall. Utilizzando l'interfaccia grafica utente fornita dallo snap-in MMC Gestione criteri di protezione IP, è possibile configurare IPSec in modo che consenta o blocchi determinati tipi di traffico in base alle combinazioni degli indirizzi di origine e di destinazione e a specifici protocolli e porte.

**Nota:** Windows IPSec non è un firewall basato su host con funzionalità complete e non supporta le funzionalità di filtraggio di tipo dinamico o stateful, come il controllo del bit prestabilito durante l'handshake TCP per la verifica della direzione in cui può avvenire la comunicazione.

#### I filtri IPSec

Gli elenchi di filtri non sono altro che elenchi delle subnet note e degli indirizzi IP dell'infrastruttura. È fondamentale capire come tutti i filtri contenuti in tutte le regole si combineranno per assicurare i necessari controlli degli accessi in ingresso e in uscita. In questa sezione vengono fornite le informazioni più importanti per comprendere in che modo i filtri IPSec influiscono sull'elaborazione dei pacchetti.

Lo snap-in MMC Monitor di protezione IP di Windows Server 2003 fornisce la vista più dettagliata dell'ordinamento dei filtri IPSec. Quando il servizio IPSec elabora un set di regole di un criterio IPSec, i filtri vengono copiati e suddivisi in due tipi per assicurare il controllo delle due fasi della negoziazione IKE:

1.  **Filtri della modalità principale IKE**. Questi filtri utilizzano solo gli indirizzi di origine e di destinazione dei filtri definiti nel criterio IPSec per il controllo della modalità principale IKE. Ogni filtro specifico della modalità principale IKE è associato a un criterio di negoziazione in modalità principale IKE che definisce:

    -   I metodi di protezione della modalità principale IKE definiti per il criterio IPSec nelle impostazioni di scambio delle chiavi, quali la forza della chiave principale Diffie-Hellman e gli algoritmi di crittografia e integrità utilizzati per proteggere la negoziazione IKE stessa.

    -   La durata della modalità principale IKE e i limiti relativi al numero di chiavi di sessione generate da una stessa chiave principale.

    -   Il metodo o i metodi di autenticazione.

2.  **Filtri della modalità rapida IKE**. Questi filtri contengono informazioni complete sui filtri relativamente a indirizzi, protocolli e porte. La modalità rapida IKE negozia questa definizione di filtro per determinare quale traffico può essere protetto all'interno di una coppia di associazioni di protezione IPSec. Ogni filtro specifico ha un peso corrispondente e un insieme di metodi di protezione che definiscono:

    -   Le opzioni per l'incapsulamento AH o ESP in modalità di trasporto o di tunnel.

    -   Un elenco di algoritmi di crittografia e integrità.

    -   La durata delle associazioni di protezione IPSec espressa in kilobyte e secondi.

    -   Le impostazioni di protezione PFS (Perfect Forward Secrecy).

I filtri specifici della modalità rapida IKE costituiscono l'elenco dei filtri ricevuti e applicati dal driver IPSec. Il driver IPSec associa tutto il traffico IP in ingresso e in uscita a questi filtri, nell'ordine specificato in base al peso più elevato. Nella seguente sezione dedicata al processo di negoziazione IKE viene descritto come IKE negozia e gestisce le associazioni di protezione IPSec utilizzando questi controlli dei criteri.

I filtri definiti nei criteri IPSec sono considerati filtri "generici" perché dovranno probabilmente essere interpretati dal servizio IPSec quando il criterio viene applicato. Il servizio IPSec interpreta tutti i filtri generici come filtri specifici al momento dell'applicazione (o della modifica) del criterio IPSec nel computer. I filtri specifici hanno un algoritmo integrato per il calcolo del peso, o ordine, che si riferisce anche al livello di specificità del filtro quando viene selezionato il traffico. Un peso elevato corrisponde a un filtro più specifico. Tutti i filtri specifici sono ordinati in base al peso. Il peso del filtro viene valutato considerando dapprima l'indirizzo IP, poi i protocolli e infine le porte che possono essere definiti all'interno del filtro. Questo metodo assicura che l'ordine delle regole in un criterio e l'ordinamento dei filtri in ciascun elenco di filtri non incidano sull'applicazione dei filtri da parte del driver IPSec durante l'elaborazione dei pacchetti. I pacchetti vengono associati dapprima ai filtri più specifici per ridurre al minimo il tempo necessario a elaborare ogni pacchetto in base all'insieme totale dei filtri. L'operazione filtro che corrisponde al filtro più specifico associato a un pacchetto è l'unica operazione effettuata per quel pacchetto. Il filtro più generico che può essere definito è quello che corrisponde a qualsiasi indirizzo IP e a tutti i protocolli e le porte. Ad esempio, si considerino le seguenti quattro definizioni di filtri:

-   Qualsiasi &lt;-&gt; Qualsiasi, Qualsiasi protocollo

-   Qualsiasi &lt;-&gt; 192.168.1.0/24, Qualsiasi protocollo

-   Qualsiasi &lt;-&gt; 192.168.1.10/24, Qualsiasi protocollo

-   Qualsiasi &lt;-&gt; 192.168.1.10/24, Qualsiasi porta di origine TCP, Porta di destinazione 25

Il filtro Qualsiasi &lt;-&gt; Qualsiasi è il filtro più generico che è possibile definire. È supportato solo da Windows Server 2003 e da Windows XP Service Pack 2 (SP2). In genere, questo filtro è utilizzato assieme a un'azione di blocco per ottenere un comportamento predefinito di rifiuto totale del traffico. Se questo filtro viene utilizzato per bloccare tutto il traffico, i restanti filtri più specifici potrebbero essere considerati eccezioni del primo filtro. In Windows 2000, il filtro più generico supportato è Qualsiasi &lt;-&gt; Subnet, Qualsiasi protocollo o, se non si utilizzano subnet, Qualsiasi &lt;-&gt; Indirizzo IP.

Tutti i quattro filtri vengono associati al traffico in ingresso da qualsiasi indirizzo IP a 192.168.1.10 sulla porta TCP 25 con le corrispondenti risposte in uscita dalla porta 25. Il quarto filtro è quello più specifico perché specifica un indirizzo IP di destinazione, protocollo e numero di porta. Quando tutti i quattro filtri vengono applicati dal driver IPSec, un pacchetto in ingresso destinato alla porta TCP 25 viene associato solamente al quarto filtro, ossia a quello più specifico. Se un sistema remoto invia traffico TCP a qualsiasi porta diversa da 25 a 192.168.1.10, il traffico viene associato al terzo filtro. Infine, se il traffico viene inviato a qualsiasi indirizzo IP della subnet 192.168.1.0 ad eccezione di 192.168.1.10, il secondo filtro è quello più specifico per il traffico.

#### Possibili problemi di configurazione dei filtri

Quando si definiscono i filtri, non è possibile utilizzare alcune combinazioni delle opzioni degli indirizzi di origine e di destinazione. Come è stato osservato in precedenza, è opportuno evitare i filtri da qualsiasi indirizzo IP a qualsiasi indirizzo IP per gli host che eseguono Windows 2000.

In linea di massima, più sono i filtri in un criterio, maggiore sarà l'impatto sulle prestazioni di elaborazione dei pacchetti, che si manifesta come riduzione della velocità effettiva, maggiore utilizzo della memoria non di paging del kernel e maggiore utilizzo della CPU. L'esatto impatto sulle prestazioni è molto difficile da stimare perché dipende dal volume complessivo del traffico, dalla quantità di traffico protetto con IPSec in fase di elaborazione e dal carico sulla CPU del computer. Di conseguenza, i test sulle prestazioni delle configurazioni dei criteri IPSec devono essere presi in considerazione già nella fase di pianificazione. È probabile che l'impatto di alcune centinaia di filtri non si faccia notare, tranne nei computer ad alta velocità effettiva.

Windows 2000 non dispone di ottimizzazioni per la gestione di grandi quantità di filtri. Il driver IPSec deve analizzare l'intero elenco dei filtri in sequenza per trovare una corrispondenza.

In Windows XP e Windows Server 2003, sono state aggiunte molte ottimizzazioni per accelerare l'elaborazione dei filtri in modo che sia possibile utilizzare maggiori quantità di filtri in un criterio IPSec. Sono stati ottimizzati tutti i filtri con il formato Da &lt;Indirizzo IP&gt; A &lt;Indirizzo IP&gt; (a prescindere dal protocollo o dalle porte) utilizzando l'Utilità di classificazione pacchetti generica, che garantisce un'analisi estremamente veloce. Questa utilità può gestire un numero praticamente illimitato di filtri senza provocare una riduzione delle prestazioni. Di conseguenza, i lunghi elenchi di esenzioni che utilizzano Da &lt;Indirizzo IP&gt; A &lt;Indirizzo IP di esenzione specifica&gt; sono ora facilmente supportati, a condizione che nel kernel vi sia sufficiente memoria non di paging per memorizzare l'intero elenco dei filtri. I filtri che non hanno un indirizzo IP specifico di origine e di destinazione non possono essere ottimizzati dall'Utilità di classificazione pacchetti generica, il che significa che i filtri di tipo Qualsiasi indirizzo IP &lt;-&gt; Indirizzo IP specifico (o Subnet IP specifica) richiederanno una ricerca sequenziale. Ma l'implementazione è comunque migliore rispetto a Windows 2000.

L'utilizzo di Indirizzo IP può essere appropriato in molti casi, ma può anche causare problemi per gli host con molti indirizzi IP, ad esempio un server Web che ospita molti siti Web virtuali. Può anche provocare un ritardo nella disponibilità del filtraggio dei pacchetti nel driver IPSec se vi è una grande quantità di filtri che utilizzano Indirizzo IP. Il servizio IPSec elabora i filtri durante l'avvio del servizio e quando si verifica un cambiamento di indirizzo. Il ritardo può dar luogo a una finestra di vulnerabilità o a ritardi nello stabilire una connessione protetta tramite IPSec. Anche in questo caso, i test sulle prestazioni devono confermare l'accettabilità dell'impatto di una particolare configurazione di criteri.

Indirizzo IP può essere il filtro più appropriato da utilizzare quando si consente o si nega il traffico verso una specifica porta o protocollo. Ad esempio, nella configurazione dei criteri IPSec per la Woodgrove Bank, i filtri Indirizzo IP vengono utilizzati per creare un filtro più specifico che consente al traffico ICMP (Internet Control Message Protocol) di essere inviato e ricevuto in forma di testo non crittografato fra tutti i computer.

Se un client portatile nell'organizzazione riceve una regola Indirizzo IP &lt;-&gt; Qualsiasi indirizzo IP e viene poi collocato su una rete esterna, il client portatile potrebbe non riuscire a comunicare in quell'ambiente. Se al client è consentito il ritorno alla modalità non crittografata, il client avrà tre o più secondi di ritardo nello stabilire una connessione con ogni destinazione. Se la destinazione risponde con una risposta IKE, la negoziazione IKE non riuscirà perché IKE non potrà eseguire l'autenticazione tramite il trust tra domini (Kerberos). Ovviamente, se gli indirizzi privati RFC 1918 sono utilizzati come subnet della rete interna, i client portatili ne subiranno le conseguenze quando si connettono alle reti di hotel, reti domestiche e ad altre reti interne. Se i client portatili hanno problemi di connettività, potrebbero aver bisogno dei diritti di amministratore locale per interrompere il servizio IPSec durante le connessioni ad altre reti. Di conseguenza, quando i client si connettono alla rete interna può essere necessario utilizzare uno script di accesso al dominio per controllare se il servizio IPSec è in esecuzione.

Windows 2000 non era stato originariamente progettato per consentire il filtraggio dei pacchetti con indirizzi multicast e broadcast perché questo traffico non poteva essere protetto tramite la negoziazione IKE. Di conseguenza, i tipi di pacchetti multicast e broadcast facevano parte delle esenzioni predefinite originarie che aggiravano i filtri IPSec. Per una spiegazione dettagliata sulle implicazioni per la protezione derivanti dalle esenzioni predefinite e sulle modifiche implementate dal Service Pack 3 per eliminarne alcune per impostazione predefinita, vedere l'articolo della Microsoft Knowledge Base 811832 "[IPSec Default Exemptions Can Be Used to Bypass IPSec Protection in Some Scenarios](http://support.microsoft.com/kb/811832)" all'indirizzo http://support.microsoft.com/kb/811832 (in lingua inglese). L'integrazione di TCP/IP con IPSec in Windows XP e Windows Server 2003 è stata potenziata per filtrare tutti i tipi di pacchetti IP. Tuttavia, dato che IKE non può negoziare la protezione per il traffico multicast e broadcast, il filtraggio è supportato in modo limitato. Per informazioni sulla rimozione delle esenzioni predefinite e il livello di supporto del filtraggio per il traffico multicast e broadcast, vedere l'articolo della Knowledge Base 810207 "[Rimozione delle esenzioni predefinite per IPSec in Windows Server 2003](http://support.microsoft.com/kb/810207)" all'indirizzo http://support.microsoft.com/kb/810207. Windows XP SP2 supporta le stesse funzionalità di filtraggio Qualsiasi &lt;-&gt; Qualsiasi di Windows Server 2003.

[](#mainsection)[Inizio pagina](#mainsection)

### Processo di negoziazione IKE

Il protocollo IKE serve a stabilire una relazione di trust protetta tra ogni computer, negoziare le opzioni di protezione e generare dinamicamente il materiale condiviso e segreto delle chiavi di crittografia. Per garantire l'esito positivo e la protezione delle comunicazioni, IKE esegue un'operazione in due fasi: negoziazione fase 1 (modalità principale) e negoziazione fase 2 (modalità rapida). La riservatezza e l'autenticazione possono essere assicurate durante ogni fase dall'utilizzo di algoritmi di crittografia e autenticazione che sono accettati dai due computer durante le negoziazioni di protezione.

#### Negoziazione in modalità principale

Durante la negoziazione in modalità principale, i due computer definiscono un canale protetto e autenticato. In primo luogo, vengono negoziati i seguenti parametri dei criteri IPSec: l'algoritmo di crittografia (DES o 3DES), l'algoritmo di integrità (MD5 o SHA1), il gruppo Diffie-Hellman da utilizzare per il materiale delle chiavi di base (Gruppo 1, Gruppo 2 o, in Windows Server 2003, Gruppo 2048) e il metodo di autenticazione (protocollo Kerberos versione 5, certificato a chiave pubblica o chiave già condivisa). Lo scambio Diffie-Hellman dei valori pubblici termina dopo la negoziazione dei parametri dei criteri IPSec. L'algoritmo Diffie-Hellman serve a generare chiavi condivise, simmetriche e segrete tra i computer. Al termine dello scambio Diffie-Hellman, il servizio IKE su ogni computer genera la chiave principale utilizzata per proteggere l'autenticazione. La chiave principale viene utilizzata assieme ai metodi e agli algoritmi di negoziazione per autenticare le identità. L'iniziatore della comunicazione propone quindi una possibile SA al risponditore. Il risponditore invia una risposta con cui accetta questa SA o propone un'alternativa. Il risultato di una negoziazione in modalità principale IKE è una SA in modalità principale.

#### Negoziazione in modalità rapida

Durante la negoziazione in modalità rapida, viene definita una coppia di SA IPSec per proteggere il traffico delle applicazioni, che può includere pacchetti inviati su TCP, UDP (User Datagram Protocol) e altri protocolli. Vengono negoziati dapprima i seguenti parametri dei criteri: il formato di trasmissione del protocollo IPSec (AH o ESP), l'algoritmo hash per l'integrità e l'autenticazione (MD5 o SHA1) e l'algoritmo per la crittografia (DES o 3DES), nel caso in cui questa sia necessaria. In questo periodo di tempo, viene raggiunto un accordo comune sul tipo di pacchetti IP da trasportare nella coppia di SA IPSec definita. Dopo aver negoziato i parametri dei criteri IPSec, viene aggiornato o scambiato il materiale delle chiavi di sessione (le chiavi di crittografia e la durata delle chiavi, in secondi e kilobit, per ogni algoritmo).

Ogni SA IPSec viene identificata da un valore SPI (Security Parameter Index, indice del parametro di protezione), riportato nell'intestazione IPSec di ogni pacchetto inviato. Un valore SPI identifica l'SA IPSec in ingresso, mentre l'altro identifica l'SA IPSec in uscita.

#### SA in modalità principale IKE e SA IPSec

Ogni volta che si utilizza IPSec per proteggere il traffico, vengono definite una SA in modalità principale IKE e due SA IPSec. Nello scenario di esempio, per le comunicazioni protette con IPSec che avvengono tra CORPCLI e CORPSRV vengono definite le seguenti SA:

CORPCLI \[IP1\] **&lt;--------** SA in modalità principale IKE \[IP1, IP2\] **-----&gt;** \[IP2\] CORPSRV

CORPCLI \[IP1\] **----------** SA IPSec \[SPI=x\] **------------------&gt;** \[IP2\] CORPSRV

CORPCLI \[IP1\] **&lt;--------** SA IPSec \[SPI=y\] **---------------** \[IP2\] CORPSRV

Dove:

-   IP1 è l'indirizzo IP di CORPCLI.

-   IP2 è l'indirizzo IP di CORPSRV.

-   x è il valore SPI che identifica l'SA IPSec in ingresso per CORPSRV proveniente da CORPCLI.

-   y è il valore SPI che identifica l'SA IPSec in uscita da CORPSRV per CORPCLI.

Come indicato in questo riepilogo, l'SA in modalità principale IKE tra CORPCLI e CORPSRV è bidirezionale. Uno dei due computer può avviare una negoziazione in modalità rapida utilizzando la protezione fornita dall'SA in modalità principale IKE. Le SA IPSec non dipendono dallo stato dei protocolli di livello superiore. Ad esempio, le connessioni TCP possono essere stabilite e terminate mentre le SA IPSec continuano, e le SA IPSec possono scadere prima della fine di una connessione TCP. IKE tenta di rinegoziare utilizzando la negoziazione in modalità rapida per definire due nuove coppie di SA IPSec prima dello scadere della durata della coppia di SA IPSec esistente, così da evitare l'interruzione della connessione. Sebbene questo processo venga comunemente detto rigenerazione delle chiavi dell'associazione di protezione (SA) IPSec, in realtà vengono definite due nuove SA IPSec. La durata dell'SA in modalità principale IKE è misurata solo in base al tempo e al numero di tentativi di definizione dell'SA IPSec (e non in base al numero di byte dei dati trasferiti nel protocollo IKE). L'SA in modalità principale IKE scade indipendentemente dalla coppia di SA IPSec. Se è necessaria una nuova coppia di SA IPSec, viene rinegoziata automaticamente una SA in modalità principale IKE (quando è già scaduta una SA in modalità principale). In base alla configurazione della IETF (Internet Engineering Task Force), IKE deve essere in grado di rigenerare l'SA in modalità principale e di negoziare la modalità rapida IKE in una delle due direzioni. Pertanto il metodo di autenticazione configurato nei criteri IPSec su entrambi i computer per l'SA in modalità principale IKE deve consentire l'esito positivo dell'autenticazione nella direzione dalla quale è iniziata la negoziazione IKE in modalità principale. Analogamente, le impostazioni dei criteri IPSec nell'operazione filtro per la modalità rapida devono consentire una corretta negoziazione in modalità rapida bidirezionale.

[](#mainsection)[Inizio pagina](#mainsection)

### Metodi di protezione

I metodi di protezione vengono utilizzati durante la negoziazione in modalità principale IKE per definire gli algoritmi di crittografia e hash e il gruppo Diffie-Hellman utilizzato per creare l'SA in modalità principale e proteggere il canale di negoziazione IKE. I metodi di protezione vengono anche utilizzati durante la negoziazione in modalità rapida per definire la modalità di incapsulamento (di trasporto o tunnel), il formato di trasmissione del protocollo IPSec (AH o ESP), gli algoritmi di crittografia e hash e la durata delle chiavi utilizzate per creare le SA in ingresso e in uscita in modalità rapida.

[](#mainsection)[Inizio pagina](#mainsection)

### Modalità di incapsulamento e formati di trasmissione del protocollo IPSec

IPSec protegge i dati in un pacchetto IP fornendo protezione con crittografia per un payload IP. La protezione fornita dipende dalla modalità in cui IPSec è utilizzato e dal formato di trasmissione del protocollo. È possibile utilizzare IPSec in modalità di trasporto o di tunnel.

#### Modalità di incapsulamento IPSec

In genere, la modalità di tunnel IPSec** serve a proteggere il traffico da un sito all'altro (denominato anche traffico gateway-to-gateway o router-to-router) tra le reti, ad esempio le reti connesse tramite Internet. Quando viene utilizzata la modalità di tunnel IPSec, il gateway mittente incapsula l'intero pacchetto IP originale creando un nuovo pacchetto IP che viene protetto da uno dei formati di trasmissione del protocollo IPSec (AH o ESP). Per informazioni su IPSec in modalità di tunnel, consultare il capitolo “Deploying IPSec” della guida *Deploying Network Services* nel [Windows Server 2003 Deployment Kit](http://technet.microsoft.com/en-us/library/cc738134.aspx) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=8195 (in lingua inglese).

La modalità di trasporto IPSec serve a proteggere le comunicazioni host-to-host ed è la modalità predefinita di Windows IPSec. Quando viene utilizzata la modalità di trasporto IPSec, IPSec crittografa solo il payload IP e non l'intestazione IP. Windows IPSec è utilizzato in modalità di trasporto soprattutto per proteggere le comunicazioni end-to-end (come quelle tra i client e i server).

#### Formati di trasmissione del protocollo IPSec

IPSec supporta due formati di trasmissione: AH o ESP. La modalità di trasporto IPSec incapsula il payload IP originale con un'intestazione IPSec (AH o ESP).

#### AH

AH garantisce l'autenticazione dell'origine dei dati, l'integrità dei dati e la protezione antireplay per l'intero pacchetto (sia l'intestazione IP che il payload di dati trasportati nel pacchetto), ad eccezione dei campi nell'intestazione IP, per i quali è consentita la modifica in transito. AH non garantisce la segretezza dei dati, ovvero non crittografa i dati. I dati sono leggibili ma protetti da eventuali modifiche e falsificazioni. Come mostrato nella figura seguente, l'integrità e l'autenticazione sono assicurate dal posizionamento dell'intestazione AH tra l'intestazione IP e i dati TCP.

[![](images/Dd536200.SGFG0A01(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536200.sgfg0a01_big(it-it,technet.10).gif)

**Figura A.1 Intestazione di autenticazione in un pacchetto**

Per utilizzare AH, accedere alle proprietà della regola appropriata, aprire la finestra di dialogo **Impostazioni personalizzate metodo di protezione**, selezionare la casella di controllo **Integrità dati e indirizzi, senza crittografia (AH)** e specificare l'algoritmo di integrità da utilizzare.

#### ESP

ESP garantisce l'autenticazione dell'origine dei dati, l'integrità dei dati, la protezione antireplay e dispone di un'opzione di segretezza per il solo payload IP. Nella modalità di trasporto, ESP non protegge l'intero pacchetto con un checksum di crittografia. L'intestazione IP non è protetta. Come mostrato nella figura seguente, l'intestazione ESP è posizionata prima dei dati TCP, mentre l'appendice ESP e l'appendice di autenticazione ESP sono posizionate dopo i dati TCP.

[![](images/Dd536200.SGFG0A02(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536200.sgfg0a02_big(it-it,technet.10).gif)

**Figura A.2 Dati ESP in un pacchetto**

Per utilizzare ESP, accedere alle proprietà della regola appropriata, aprire la finestra di dialogo **Impostazioni personalizzate metodo di protezione**, selezionare la casella di controllo **Integrità dati con crittografia (ESP)** e specificare gli algoritmi di integrità e crittografia da utilizzare.

[](#mainsection)[Inizio pagina](#mainsection)

### Autenticazione IKE

IKE utilizza l'autenticazione reciproca tra computer per definire le comunicazioni attendibili e richiede l'utilizzo di uno dei seguenti metodi di autenticazione: protocollo Kerberos versione 5, un certificato a chiave pubblica (PKI) X.509 versione 3 o una chiave già condivisa. I due endpoint della comunicazione devono avere almeno un metodo di autenticazione in comune, altrimenti la comunicazione non riesce.

#### Processo di autenticazione IKE

Durante la negoziazione IKE, l'iniziatore IKE propone un elenco di metodi di autenticazione al risponditore IKE. Il risponditore utilizza l'indirizzo IP di origine dell'iniziatore per identificare quale filtro controlla la negoziazione IKE. L'elenco dei metodi di autenticazione che corrisponde al filtro nel criterio IPSec del risponditore viene utilizzato per selezionare un metodo di autenticazione dall'elenco dell'iniziatore. Il risponditore risponde quindi all'iniziatore per comunicargli il metodo di autenticazione accettato. Se l'autenticazione con il metodo scelto non riesce, IKE non fornisce un metodo per tentare con un altro metodo di autenticazione. Se l'autenticazione ha esito positivo e la negoziazione in modalità principale viene completata, l'SA in modalità principale dura otto ore. Se si continua a trasmettere dati dopo otto ore, l'SA in modalità principale viene rinegoziata automaticamente.

#### Metodi di autenticazione IKE

È importante scegliere il metodo di autenticazione appropriato per il criterio IPSec. Una regola del criterio IPSec associa ogni indirizzo IP contenuto in un filtro a un elenco di metodi di autenticazione in modo che IKE possa scegliere quale elenco di metodi di autenticazione utilizzare con ogni indirizzo IP.

#### Autenticazione tramite il protocollo Kerberos versione 5

Il protocollo Kerberos versione 5 è lo standard di autenticazione predefinito nei domini Windows 2000 e Windows Server 2003 con servizio Active Directory. Qualsiasi computer nel dominio o in un dominio attendibile può utilizzare questo metodo di autenticazione.

Quando si utilizza l'autenticazione Kerberos, durante la negoziazione in modalità principale ogni peer IPSec invia l'identità del proprio computer in formato non crittografato all'altro peer. L'identità del computer resta non crittografata finché non viene crittografato l'intero payload di identità nella fase di autenticazione della negoziazione in modalità principale. Un hacker potrebbe inviare un pacchetto IKE per far sì che il peer IPSec che risponde riveli l'identità del proprio computer e il dominio di appartenenza. Per questo motivo, al fine di proteggere i computer che sono connessi a Internet, si consiglia l'utilizzo dell'autenticazione tramite certificati.

Per impostazione predefinita, in Windows 2000 fino al Service Pack 3 incluso e in Windows XP, il traffico Kerberos è esentato dal filtraggio IPSec. Per eliminare l'esenzione per il traffico Kerberos, è necessario modificare il Registro di sistema e aggiungere un filtro IPSec appropriato per proteggere questo traffico. Per informazioni sulle esenzioni predefinite in Windows 2000 e Windows Server 2003, consultare le sezioni Special IPSec considerations e [Creating, modifying, and assigning IPSec policies](http://technet.microsoft.com/en-us/library/cc738367.aspx) nel sito Web Microsoft all'indirizzo
www.microsoft.com/resources/documentation/WindowsServ/
2003/standard/proddocs/en-us/sag\_IPSECbpSpecial.asp (in lingua inglese).

#### Autenticazione tramite certificati a chiave pubblica

In Windows 2000 Server, è possibile utilizzare Servizi certificati per gestire automaticamente i certificati dei computer per IPSec per l'intera durata dei certificati. Integrato con Active Directory e i criteri di gruppo, Servizi certificati semplifica la distribuzione dei certificati attivando l'autoregistrazione e il rinnovo degli stessi e fornendo diversi modelli di certificato predefiniti compatibili con IPSec. Per utilizzare i certificati per l'autenticazione IKE, è necessario definire un elenco ordinato di Autorità di certificazione principali (CA) accettabili, non un certificato specifico da utilizzare. Entrambi i computer devono avere un'Autorità di certificazione principale comune nella configurazione dei criteri IPSec e i client devono avere un certificato computer associato.

Durante il processo di selezione del certificato, IKE esegue una serie di controlli per garantire che siano soddisfatti i requisiti specifici per il certificato computer. Ad esempio, il certificato computer deve avere una chiave pubblica di lunghezza superiore a 512 bit e utilizzare una chiave con firma digitale.

**Nota:** i certificati ottenuti da Servizi certificati con l'opzione avanzata impostata su **Abilita protezione avanzata chiave privata** non funzionano per l'autenticazione IKE, perché non è possibile immettere il numero di identificazione personale (PIN) richiesto per accedere alla chiave privata di un certificato computer durante la negoziazione IKE.

#### Chiavi già condivise

Se non si utilizza l'autenticazione Kerberos e non si ha accesso a una CA, si può utilizzare una chiave già condivisa. Ad esempio, è possibile che un computer autonomo di una rete debba utilizzare una chiave già condivisa perché né l'autenticazione Kerberos (tramite l'account di dominio del computer) né i certificati di una CA possono attivare un'autenticazione IKE in alcuni scenari.

**Importante**: le chiavi già condivise si implementano facilmente ma possono essere compromesse se non sono utilizzate correttamente. Microsoft non consiglia l'utilizzo dell'autenticazione tramite chiavi già condivise in Active Directory perché il valore delle chiavi non viene memorizzato in un luogo protetto ed è quindi difficile mantenerlo segreto. Il valore delle chiavi già condivise è memorizzato in forma di testo non crittografato in un criterio IPSec. Un criterio IPSec locale può essere visualizzato da qualsiasi membro del gruppo Administrators locale e può essere letto da qualsiasi servizio di sistema che abbia diritti utente per il sistema locale. Per impostazione predefinita, qualsiasi utente non autenticato del dominio può visualizzare una chiave già condivisa se è memorizzata in un criterio IPSec basato su Active Directory. Inoltre, se un hacker riesce ad acquisire i pacchetti di negoziazione IKE, i metodi pubblicati possono consentire all'hacker di scoprire i valori delle chiavi già condivise.
Per ulteriori informazioni, consultare l'articolo

L'autenticazione tramite chiavi già condivise è fornita a fini di interoperabilità e compatibilità con gli standard RFC. Se è necessario ricorrere all'autenticazione tramite chiavi già condivise, utilizzare un valore casuale per la chiave con lunghezza pari o superiore a 25 caratteri e una chiave già condivisa diversa per ogni coppia di indirizzi IP. Queste procedure danno luogo a regole di protezione diverse per ogni destinazione e fanno sì che una chiave già condivisa eventualmente violata comprometta solo i computer che condividono la chiave.

#### Controllo dell'elenco di revoche dei certificati (CRL) IPSec

Se si utilizza l'autenticazione basata sui certificati, è possibile attivare anche il controllo dell'elenco di revoche dei certificati (CRL) IPSec. Per impostazione predefinita, in Windows 2000 i CRL IPSec non vengono controllati automaticamente durante l'autenticazione dei certificati IKE.

**Per attivare il controllo dell'elenco di revoche dei certificati (CRL) IPSec**

**Attenzione**: modifiche non corrette al Registro di sistema potrebbero danneggiare gravemente il sistema. Prima di apportare modifiche al Registro di sistema, è consigliabile eseguire il backup di tutti i dati importanti presenti nel computer.

1.  In **HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\**
    **Services\\PolicyAgent\\**, aggiungere una nuova chiave Oakley, con una voce DWORD denominata StrongCrlCheck.

2.  Assegnare a questa voce un valore compreso tra 0 e 2, dove:

    -   Il valore **0** disattiva il controllo del CRL (impostazione predefinita in Windows 2000).

    -   Il valore **1** attiva il controllo del CRL; in questo caso, la convalida del certificato non riesce solo se il certificato viene revocato (impostazione predefinita in Windows XP e Windows Server 2003). Altri problemi che possono verificarsi durante il controllo del CRL (quali la revoca di un URL non raggiungibile) non impediscono la convalida del certificato.

    -   Il valore **2** attiva il controllo avanzato del CRL; in questo caso, il controllo dell'elenco è necessario e la convalida del certificato non riesce se si verifica un errore qualsiasi durante l'elaborazione del CRL. Impostare questo valore della chiave del Registro di sistema per ottenere una maggiore protezione.

3.  Quindi, eseguire una delle operazioni seguenti:

    -   Riavviare il computer.

    -   Arrestare e poi riavviare il servizio IPSec eseguire i comandi **net stop policyagent** e **net start policyagent** al prompt dei comandi.

        **Nota**: il controllo del CRL IPSec non garantisce la negazione immediata della convalida dei certificati quando un certificato viene revocato. Vi è infatti un ritardo fra il momento in cui il certificato revocato viene inserito in un CRL aggiornato e pubblicato e il momento in cui il computer che esegue il controllo del CRL IPSec recupera questo elenco. Il computer non recupera un nuovo CRL prima della scadenza del CRL corrente o della successiva pubblicazione del CRL. I CRL sono memorizzati nella cache e nella cartella \\Documents and Settings\\*Nome utente*\\Impostazioni locali\\Temporary Internet Files tramite la funzione CryptoAPI. Dato che i CRL permangono anche dopo aver riavviato il computer più volte, se si verifica un problema nella cache dei CRL, non è possibile risolverlo riavviando il computer.

[](#mainsection)[Inizio pagina](#mainsection)

### Metodi di autenticazione IKE e ordine di preferenza dei metodi di protezione

È possibile configurare una regola IPSec per specificare un solo metodo di autenticazione o di protezione. In alternativa, è possibile specificare un elenco preferito di metodi di autenticazione e di protezione. L'ordine di preferenza si applica ai metodi di autenticazione e di protezione in modo che per ogni metodo sia possibile specificare la preferenza, da quello preferito a quello meno utilizzato. Ad esempio, è possibile specificare che siano previsti entrambi i metodi di autenticazione tramite il protocollo Kerberos versione 5 e i certificati a chiave pubblica e assegnare a Kerberos una preferenza maggiore, come mostrato nella figura seguente.

![](images/Dd536200.SGFG0A03(it-it,TechNet.10).gif)

**Figura A.3 Ordine di preferenza dei metodi di autenticazione**

Se un client tenta di connettersi a CORPSRV ma accetta solo certificati a chiave pubblica per l'autenticazione, CORPSRV utilizzerà questo metodo di autenticazione e continuerà a stabilire la connessione. La negoziazione IKE deve essere eseguita utilizzando il metodo di autenticazione selezionato, altrimenti la comunicazione verrà bloccata. Se la negoziazione non riesce, IKE non tenterà di utilizzare un altro metodo di autenticazione. Lo stesso principio si applica ai metodi di protezione, dove, ad esempio ESP potrebbe essere preferito ad AH.

[](#mainsection)[Inizio pagina](#mainsection)

### Opzioni della negoziazione di protezione

È possibile specificare se un criterio IPSec consente l'utilizzo della modalità non crittografata (ovvero il ricorso a comunicazioni non protette), del passthrough in ingresso e delle impostazioni PFS per le chiavi di sessione nella scheda **Metodi di protezione****, accessibile dalle proprietà di un'operazione filtro. È possibile definire le impostazioni PFS per le chiavi principali nella finestra di dialogo **Impostazioni scambio chiave**, accessibile dalle proprietà generali di una regola.

#### Modalità non crittografata

Nel caso in cui sia consentito il ritorno alla modalità non crittografata, il traffico sarà protetto da IPSec quando possibile (se il computer all'altra estremità della connessione supporta IPSec e il suo criterio contiene un'operazione filtro e un filtro complementari), ma il traffico può essere inviato in modo non protetto se il peer non ha un criterio IPSec per rispondere alla richiesta di negoziazione di protezione. Se il peer non risponde alla richiesta di negoziazione di protezione entro tre secondi, viene creata una SA per il traffico non crittografato (si tratta di una SA trasferibile). Le SA trasferibili consentono le normali comunicazioni TCP/IP senza l'incapsulamento IPSec. Si tenga presente che, sebbene IPSec non protegga questo traffico, un'altra applicazione potrebbe proteggerlo, ad esempio la crittografia LDAP (Lightweight Directory Access Protocol) o i meccanismi di autenticazione RPC (Remote Procedure Call). Se il peer non risponde entro tre secondi e la negoziazione di protezione non riesce, le comunicazioni associate al filtro corrispondente vengono bloccate.

La modalità non crittografata è un'impostazione che consente l'interoperabilità con i seguenti computer:

-   Computer che eseguono versioni di Windows precedenti a Windows 2000

-   Computer che eseguono Windows 2000 o versioni successive in cui non sono stati configurati criteri IPSec

-   Computer che eseguono sistemi operativi non prodotti da Microsoft che non supportano IPSec

Per attivare o disattivare la modalità non crittografata, selezionare o deselezionare la casella di controllo **Consenti comunicazioni non protette con computer senza IPSec** nella scheda **Metodi di protezione****, accessibile dalle proprietà di un'operazione filtro.

È possibile attivare o disattivare questa opzione per i criteri dei client. Se si seleziona questa opzione e il server non risponde alla richiesta del client di negoziare la protezione, è possibile consentire al client di utilizzare il testo non crittografato. Se si deseleziona questa casella di controllo e il server non risponde alla richiesta del client di negoziare la protezione, le comunicazioni vengono bloccate. In alcuni casi è utile attivare la modalità non crittografata. IKE consente però di utilizzare questa opzione solo se non vi è alcuna risposta. Per motivi di sicurezza, Windows IPSec non consente comunicazioni non protette se la negoziazione IKE non riesce o se si verifica un problema durante la negoziazione IKE (dopo la risposta), ad esempio in caso di mancata autenticazione o mancato accordo sui parametri di protezione.

Nelle implementazioni iniziali, si consiglia di selezionare questa casella di controllo in modo che il client possa ricorrere al testo non crittografato e stabilire la connettività iniziale quando IPSec è disattivato nel server.

#### Passthrough in ingresso

Quando è attivato il passthrough in ingresso, il normale traffico TCP/IP in ingresso (traffico che non è protetto da IPSec, ad esempio i pacchetti TCP SYN) viene accettato se corrisponde al filtro in ingresso associato all'operazione filtro. Il pacchetto di risposta del protocollo di livello superiore (ad esempio un pacchetto TCP SYN ACK) viene associato al filtro in uscita corrispondente e avvia una negoziazione di protezione. Vengono quindi negoziate due SA IPSec e il traffico è protetto da IPSec in entrambe le direzioni. L'opzione passthrough in ingresso consente a un server di utilizzare la regola di risposta predefinita per avviare la negoziazione di protezione con i client. Quando si attiva la regola di risposta predefinita nei criteri IPSec dei client, i client non devono mantenere un filtro che contenga l'indirizzo IP del server. Se non si attiva la regola di risposta predefinita nei criteri IPSec dei client, non è necessario attivare l'opzione passthrough in ingresso nei criteri IPSec del server. Inoltre, non si deve mai attivare questa opzione nei computer connessi a Internet.

Per attivare o disattivare il passthrough in ingresso, deselezionare la casella di controllo **Accetta comunicazioni non protette, ma rispondi sempre usando IPSec** nella scheda **Metodi di protezione****, accessibile dalle proprietà di un'operazione filtro.

#### PFS per le chiavi di sessione e le chiavi principali

PFS è un meccanismo che determina se il materiale esistente per una chiave principale può essere utilizzato per derivare una nuova chiave di sessione. PFS fa sì che la violazione di una sola chiave consenta l'accesso ai soli dati protetti da PFS, non necessariamente all'intera comunicazione. Per ottenere questo risultato, PFS contribuisce a evitare che una chiave utilizzata per proteggere una trasmissione possa generare chiavi aggiuntive. Il meccanismo PFS per le chiavi di sessione può essere utilizzato senza riautenticazione e richiede meno risorse rispetto al PFS per le chiavi principali. Quando l'impostazione PFS per le chiavi di sessione è attivata, viene eseguito un nuovo scambio di chiavi Diffie-Hellman per generare le informazioni della nuova chiave principale.

Se si attiva l'impostazione PFS per le chiavi di sessione in un criterio di un server, è necessario attivarlo anche nel criterio del client. È possibile attivare l'impostazione PFS per le chiavi di sessione selezionando la casella di controllo **Utilizza chiave di sessione PFS (Perfect Forward Secrecy)** nella finestra di dialogo **Impostazioni scambio chiave**, accessibile dalle proprietà generali di una regola. L'impostazione PFS per le chiavi principali richiede la riautenticazione e utilizza molte risorse. Richiede infatti una nuova negoziazione in modalità principale per ogni negoziazione in modalità rapida. È possibile configurare l'impostazione PFS per le chiavi principali selezionando la casella di controllo **PFS (Perfect Forward Secrecy) chiave master**. Se si attiva l'impostazione PFS per le chiavi principali in un criterio di un server, non è necessario attivarla nel criterio del client. Dato che l'attivazione di questa funzione comporta un sovraccarico significativo del sistema, si consiglia di attivare PFS per le chiavi di sessione o per le chiavi principali *esclusivamente* in ambienti ostili dove il traffico IPSec può essere attaccato da hacker sofisticati che possono tentare di compromettere la protezione con crittografia avanzata fornita da IPSec.

**Scarica la soluzione completa**

[Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=33947)

[](#mainsection)[Inizio pagina](#mainsection)
