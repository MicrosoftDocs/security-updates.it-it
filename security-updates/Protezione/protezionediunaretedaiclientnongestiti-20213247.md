---
TOCTitle: Protezione di una rete dai client non gestiti
Title: Protezione di una rete dai client non gestiti
ms:assetid: '9a90dd07-0efb-4151-bf99-629448130645'
ms:contentKeyID: 20213247
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc875843(v=TechNet.10)'
---

Protezione di una rete dai client non gestiti
=============================================

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Definizione](#eeaa)
[](#edaa)[Problematiche](#edaa)
[](#ecaa)[Soluzioni](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Appendice A: Protezione accesso alla rete](#eaaa)

### Introduzione

Questo documento è contenuto nella raccolta di indicazioni per la protezione delle aziende di medie dimensioni. Microsoft si augura che le informazioni seguenti possano aiutare a creare un ambiente IT più sicuro e che garantiscano una maggiore produttività.

#### Riepilogo

Al giorno d'oggi, proteggere la rete di aziende di medie dimensioni e i dati che vi sono contenuti è un problema tutt'altro che semplice. Non è più sufficiente applicare misure difensive ai margini della rete e utilizzare soluzioni antivirus per proteggere i beni della rete e le informazioni riservate. Le organizzazioni e i professionisti impegnati nella sicurezza hanno capito che i rischi a cui è sottoposta una rete interna, sia intenzionali che accidentali, possono avere il potenziale di essere molto più pericolosi delle minacce che giungono dall'esterno.

Per far fronte al numero elevatissimo di vulnerabilità che mettono a rischio le aziende di medie dimensioni, sono stati fatti enormi investimenti in termini di tempo e risorse relativamente alla gestione delle patch, alle soluzioni antimalware e alle iniziative per la gestione delle identità. Per assicurare che tali investimenti vengano utilizzati a livello globale nelle aziende e per sfruttare al massimo l'efficacia degli investimenti, le aziende devono trovare soluzioni appropriate per applicare in modo efficiente i criteri di protezione.

I computer rogue, ovvero computer su cui vengono installati intenzionalmente programmi atti a danneggiare programmi o dati, sono sistemi che sostanzialmente non vengono considerati rischiosi poiché non c'è modo di determinare la loro conformità ai criteri di protezione che sono stati definiti. I computer rogue possono rappresentare un problema per gli amministratori dei sistemi e i professionisti della sicurezza. I sistemi non conformi possono rappresentare fonti di rischio, dalle vulnerabilità alle infezioni da parte di programmi malware fino a diventare potenziali piattaforme per gli attacchi. Tradizionalmente, questi sistemi sono difficili da gestire e da portare a uno stato di conformità.

In questo documento vengono descritti alcuni metodi che possono essere utilizzati per rendere conformi i sistemi tramite l'applicazione dei criteri di protezione. Con questo approccio è possibile sfruttare al massimo i vantaggi che derivano dall'impegno nella gestione dei rischi e aggiungere un ulteriore livello di protezione alle reti delle aziende di medie dimensioni in modo da ridurre i rischi che possono giungere dai computer untrusted e non gestiti.

#### Panoramica

Questo documento è costituito da quattro sezioni principali che illustrano i concetti e i principi associati alla protezione della rete di un'azienda di medie dimensioni contro eventuali azioni che possono giungere dai computer non gestiti. Di seguito è riportato un breve riepilogo delle quattro sezioni:

##### Introduzione

In questa sezione sono riportati un riepilogo generale del documento, una panoramica della struttura del documento e alcune informazioni relative a chi è destinato il documento.

##### Definizione

In questa sezione sono riportati alcuni dettagli e alcune definizioni che saranno utili per comprendere le soluzioni che verranno illustrate nel documento.

##### Problematiche

In questa sezione vengono descritti alcuni problemi comuni che un'azienda di medie dimensioni deve affrontare quando si deve stabilire il metodo per implementare una soluzione di protezione contro i computer non gestiti e untrusted. Questa è una sezione utile da utilizzare come riferimento generale in relazione ai problemi trattati in questo documento.

##### Soluzioni

In questa sezione vengono descritte le soluzioni per risolvere i problemi che possono generare i computer non gestiti, valutando i possibili approcci e prendendo in esame le problematiche che possono sorgere quando si sviluppano le strategie per risolverli. Riporta anche alcune informazioni sui metodi di distribuzione e di gestione.

#### Destinatari della guida

Questo documento è destinato ai professionisti IT e ai responsabili tecnici che devono prendere decisioni su come proteggere la rete delle aziende di medie dimensioni dalle minacce che possono giungere dalle periferiche non gestite. Sebbene gli utenti non tecnici possano comunque trovare utile questo documento per acquisire una conoscenza più approfondita sull'argomento della protezione, la conoscenza di base degli argomenti che vengono trattati di seguito è utile per capire a fondo e applicare i principi fondamentali discussi in questo documento.

Le specifiche tecnologie trattate in questo documento includono:

-   Autenticazione IEEE 802.1X

-   Criteri IPsec

-   Sicurezza della rete

-   Microsoft Systems Management Server 2003

-   Microsoft Windows Server 2003

-   Servizio directory di Active Directory

-   Microsoft Operations Management Server

-   Servizio di Autenticazione Internet (IAS) di Microsoft

-   Autenticazione RADIUS

[](#mainsection)[Inizio pagina](#mainsection)

### Definizione

Questo documento utilizza il modello di elaborazione MOF (Microsoft Operations Framework) oltre alle funzioni SMF di gestione dei servizi di amministrazione della protezione MOF.

In particolare, per aiutare a migliorare la protezione della rete contro le minacce che possono giungere dai computer non gestiti, nelle soluzioni presentate in questo documento viene consigliato l'uso di un approccio basato su processi continui anziché un approccio che si basa sulla distribuzione lineare.

In modo specifico, l'applicazione di queste soluzioni implica i passaggi mostrati nella figura seguente:

![](images/Cc875843.PNFUC01(it-it,TechNet.10).gif)

**Figura 1. Applicazione MOF**

Come mostrato nella figura, qualsiasi risposta a un problema di sicurezza che deriva dai sistemi non gestiti si basa su continui processi di verifiche e regolazioni e non solamente su operazioni di pianificazione e distribuzione. Le minacce a cui può essere sottoposta la rete di un'azienda di medie dimensioni mutano continuamente e i sistemi che proteggono tale rete devono essere costantemente aggiornati in modo da poter essere in grado di affrontare queste minacce.

L'applicazione delle soluzioni trattate in questo documento sono in linea con le funzioni SMF di gestione della protezione, descritte come indicato di seguito:

-   Valutare l'esposizione aziendale e identificare le risorse da proteggere.

-   Identificare i metodi per ridurre a livelli accettabili i rischi a cui sono sottoposte le periferiche non protette.

-   Progettare un piano per ridurre i rischi di protezione.

-   Monitorare l'efficacia dei meccanismi di protezione.

-   Rivalutare l'efficacia e i requisiti di protezione regolarmente.

Per ulteriori informazioni su MOF, visitare le pagine [Microsoft Operations Framework](http://www.microsoft.com/technet/itsolutions/cits/mo/mof/default.mspx) (in inglese) sul sito Web Microsoft TechNet all'indirizzo www.microsoft.com/technet/itsolutions/cits/mo/mof/default.mspx.

Per ulteriori informazioni sulle funzioni SMF di gestione della protezione, vedere la pagina [Security Management Functions](http://go.microsoft.com/fwlink/?linkid=37696) (in inglese) all'indirizzo http://go.Microsoft.com/fwlink/?LinkId=37696.

La gestione dei rischi è un processo che consiste nel determinare il livello di rischio accettabile di un'organizzazione, valutare i rischi correnti e individuare i modi per raggiungere tale livello di rischio e gestirlo. Sebbene questo documento tratti alcuni concetti legati alla gestione dei rischi, la gestione dei rischi costituisce un tema a sé stante e una discussione approfondita su questo argomento merita un discorso a parte. Per ulteriori informazioni sull'analisi e sulle valutazioni dei rischi, visitare il sito Web [*Guida alla gestione dei rischi di protezione*](http://technet.microsoft.com/it-it/library/cc163151) all'indirizzo http://technet.microsoft.com/it-it/library/cc163151

[](#mainsection)[Inizio pagina](#mainsection)

### Problematiche

Alcune delle problematiche relative alla protezione dai computer non gestiti includono:

-   Come impedire ai computer non gestiti di accedere alle risorse di rete.

-   Come rendere conformi i computer comuni con gli aggiornamenti e i criteri.

-   Come applicare i criteri di protezione definiti ai computer che si collegano alla rete in remoto.

-   Come proteggere una rete dalle periferiche rogue wireless.

-   Come rilevare i sistemi non gestiti, quali i computer portatili o i desktop dei fornitori, quando si collegano alla rete.

-   Come proteggersi dalle altre periferiche mobili, quali i palmtop e i palmari.

[](#mainsection)[Inizio pagina](#mainsection)

### Soluzioni

Nella sezione "Problematiche" sono stati presentati diversi fattori che devono essere presi in considerazione quando ci si vuole proteggere dalle minacce a cui i computer rogue non gestiti sottopongono la rete. Oltre a dover difendere la tradizionale rete cablata interna, è necessario anche intraprendere alcune azioni per proteggere la rete wireless e qualsiasi percorso di accesso remoto. Per affrontare tutti i possibili modi con il quale una periferica rogue può connettersi a una rete, la soluzione deve prendere in considerazione qualsiasi aspetto del problema.

Negli argomenti della sezione seguente vengono esaminate le problematiche elencate in precedenza utilizzando gli approcci seguenti:

-   Utilizzo del dominio IPsec e dell'isolamento dei server per impedire ai computer non gestiti di accedere alle risorse di rete.

-   Utilizzo dei servizi di quarantena VPN per applicare i criteri di protezione ai computer che si connettono alla rete in remoto.

-   Utilizzo dell'autenticazione 802.1X per applicare la protezione contro le periferiche untrusted wireless.

-   Utilizzo di SMS per rilevare i computer non gestiti quando si collegano alla rete.

**Nota**   Questo documento presuppone che il lettore abbia già implementato i processi per assicurare che i computer che fanno parte di strutture basate su domini di un'azienda di medie dimensioni siano conformi ai requisiti di protezione e installazione delle patch e che sia alla ricerca dei metodi con i quali applicare la conformità e la protezione contro le periferiche non conformi. Non è oggetto di questo documento spiegare in che modo rendere conformi i computer oppure utilizzare i metodi di aggiornamento automatico della protezione, quali WSUS o le funzioni di gestione delle patch di SMS.

#### Valutazione

In questa sezione vengono descritte alcune potenziali risposte che possono aiutare a risolvere il problema dei computer non gestiti nelle aziende di medie dimensioni. Inoltre, vengono trattate alcune delle decisioni che devono essere prese prima di implementare una qualsiasi di tali risposte. Tutte le risposte discusse in questa sezione hanno lo scopo di aumentare il livello di protezione della rete di un'azienda di medie dimensioni. Pertanto, se implementate come parte di un approccio di difesa capillare, utilizzate in combinazione tra loro le risposte possono creare una soluzione valida e avanzata ai problemi trattati nella sezione "Problematiche".

##### Utilizzo dell'IPsec per isolare i domini e i server

Isolare dal punto di vista fisico i computer e le reti non è un'idea nuova. È stata una soluzione adottata in modi diversi durante gli anni, soprattutto negli ambienti in cui le reti vengono utilizzate per motivi di sviluppo e di test. Tuttavia, il vecchio approccio basato sull'isolamento fisico non è adatto per proteggere i sistemi gestiti dai rischi potenziali che possono derivare dalle periferiche non gestite. Ciò è particolarmente vero negli ambienti di rete delle aziende moderne dove la tecnologia mobile sta prendendo il sopravvento e la domanda di soluzioni automatizzate e flessibili sta aumentando. Nella tabella seguente vengono riportati i comuni metodi di isolamento fisico utilizzati nel passato e le difficoltà associate al loro uso in questa capacità.

**Tabella 1. Approcci di isolamento delle reti**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Livello OSI</th>
<th>Approccio</th>
<th>Problemi</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Livello 1</td>
<td style="border:1px solid black;">Uso di un cablaggio separato per i segmenti che devono essere isolati dalla rete trusted.</td>
<td style="border:1px solid black;"><ul>
<li>Costi associati al collegamento di un nuovo cavo per ogni nuova connessione.</li>
<li>Attività di amministrazione aumentata a causa della gestione dei nuovi cavi in base agli spostamenti degli utenti.</li>
<li>Poca flessibilità e difficoltà di gestione man mano che l'azienda cresce.</li>
<li>Maggiori possibilità di distrazioni ed errori a causa degli elevati requisiti di gestione.</li>
</ul></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Livello 2</td>
<td style="border:1px solid black;">Uso delle VLAN per creare subnet logiche isolate dalla rete trusted.</td>
<td style="border:1px solid black;"><ul>
<li>Maggiori costi associati all'aggiornamento della struttura degli switch per il supporto delle VLAN.</li>
<li>Maggiore sovraccarico di amministrazione a causa della traccia delle modifiche alla rete, degli spostamenti degli utenti e delle risposte alle richieste di connessione di tipo guest.</li>
<li>Possibilità di distrazione ed errori quando si hanno numerosi spostamenti di utenti oppure vengono utilizzate periferiche mobili.</li>
</ul></td>
</tr>
</tbody>
</table>
 

Come dimostrato dalla tabella, la rete di un'azienda moderna richiede una soluzione più flessibile per applicare i requisiti di conformità tramite standard di protezione che possano aiutare a proteggerla dai sistemi non gestiti. Sebbene per risolvere questo problema siano state sviluppate soluzioni apposite da parte di terzi, tali soluzioni richiedono installazioni client su tutte le workstation gestite e aggiungono pertanto un livello in più di complessità alla rete. Fortunatamente, le versioni correnti di Microsoft Windows includono la funzionalità che aiuta a risolvere questo problema senza la necessità di aggiungere installazioni di software e affrontare curve di apprendimento relative all'amministrazione.

L'isolamento dei server e dei domini Microsoft permette agli amministratori IT di limitare le comunicazioni TCP/IP sfruttando le funzionalità IPsec e Criteri di gruppo di Active Directory incorporate. Ciò permette di ottenere i vantaggi seguenti:

-   Utilizzo di un livello di rete di tipo OSI, che permette di ampliare i limiti degli switch e dei router.

-   Indipendenza dai limiti della struttura degli switch e della rete fisica.

-   Costi contenuti grazie alla possibilità di utilizzare le funzioni di autenticazione incluse nei computer Windows.

-   Sistema automatizzato che non richiede continue attività di gestione a causa di modifiche alla rete e spostamenti di utenti.

-   Oltre all'autenticazione dei computer affidabili, vengono anche crittografate le comunicazioni tra i sistemi trusted.

-   Applicazione dei criteri di protezione e rifiuto delle richieste di connessione da parte delle periferiche non gestite.

-   Controllo e gestione delle risorse migliorati.

-   Capacità di isolare immediatamente le risorse in presenza di un attacco in corso.

Le preoccupazioni che erano sorte riguardo l'uso del protocollo IPsec per proteggere le comunicazioni sono state risolte dai recenti sviluppi conseguiti in risposta a tali problematiche. In modo specifico, le NAT (Network Address Translation) non rappresentano più una preoccupazione grazie alle funzioni di attraversamento NAT disponibili con le versioni correnti di Microsoft Windows, quali Windows Server 2003 e Microsoft Windows XP con Service Pack 2 (SP2). Inoltre, è possibile supportare le piattaforme non IPsec tramite la configurazione di elenchi di esenzioni e/o un'eccezione di fallback per consentire le comunicazioni di testo in chiaro con tali sistemi.

Le soluzioni di isolamento dei domini e dei server, presentate in questo documento, vengono utilizzate perfino nelle reti interne proprie di Microsoft. Oltre a consigliare queste soluzioni ai clienti, Microsoft dipende dal livello di protezione aggiuntivo che la soluzione fornisce e si è presa un impegno a lungo termine per supportare questo metodo di creazione di reti notevolmente sicure e gestibili per elaborazioni trusted.

###### Nozioni sull'isolamento dei domini e dei server

La creazione di una rete isolata comporta la separazione di diversi tipi di computer nella rete di un'azienda in base al tipo di accesso di cui devono disporre. In questo caso, i tipi di computer possono essere raggruppati in due categorie: gestiti e non gestiti. Per ottenere un livello funzionale di isolamento della rete, devono essere soddisfatte due condizioni principali. Le condizioni sono:

-   I computer che risiedono nella rete isolata possono stabilire le comunicazioni con tutti gli altri computer dell'intera rete, inclusi quelli che si trovano all'esterno della rete trusted.

-   I computer che risiedono all'esterno della rete isolata possono solo stabilire le comunicazioni con gli altri computer che si trovano anche loro all'esterno della rete; non possono stabilire le comunicazioni con i computer interni della rete trusted.

L'isolamento del dominio e del server IPsec utilizza le strutture di dominio esistenti tramite le impostazioni di Criteri di gruppo. Tutto ciò che occorre per creare una rete isolata è già previsto nei computer Windows XP, Windows 2000 Server e Windows Server 2003. Se vengono impostate le opzioni appropriate in Criteri di gruppo, il processo di inserimento di un nuovo computer nella rete isolata consiste semplicemente nell'aggiungere il computer al dominio.

![](images/Cc875843.PNFUC02(it-it,TechNet.10).gif)

**Figura 2. Isolamento della rete utilizzando i domini Active Directory**

Come illustrato nella figura precedente, qualsiasi computer che non è membro del dominio è considerato untrusted e pertanto risiede all'esterno della rete isolata. Qualsiasi sistema che risiede all'esterno della rete isolata non può avviare le comunicazioni IPsec e pertanto non può stabilire alcuna connessione con nessun sistema che si trova all'interno della rete isolata. Tuttavia, i membri del dominio isolato possono stabilire senza alcun tipo di vincolo comunicazioni di testo in chiaro con le periferiche che si trovano all'esterno della rete isolata.

Nella realtà, molte organizzazioni dispongono di computer e server che, sebbene siano gestiti e trusted, non sono inseriti in un dominio Active Directory oppure non sono in grado di utilizzare IPsec per svariati motivi. Tuttavia, queste organizzazioni hanno comunque la necessità di comunicare con i sistemi che si trovano all'interno della rete isolata. Per risolvere questo problema, è possibile creare un altro gruppo isolato (gruppo di confine) utilizzando gli elenchi di esenzioni come mostrato nella figura seguente.

[![](images/Cc875843.PNFUC03(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875843.pnfuc03_big(it-it,technet.10).gif)

**Figura 3. Isolamento della rete e gruppi di confine**

Un modello di isolamento della rete come questo consente di ridurre la superficie di protezione della rete di un'azienda. Tuttavia, questa soluzione da sola non può garantire che un sistema trusted rimanga conforme agli standard che lo hanno reso trusted. Questa non è una soluzione che può essere considerata completa per la protezione della rete. È una componente utile di un processo completo più grande che, insieme ad altre soluzioni, può ridurre i rischi a cui vengono sottoposte le reti delle moderne aziende di medie dimensioni. In modo specifico, se utilizzato con altre soluzioni di protezione, quale WSUS, SMS, MOM e così via, questo metodo di isolamento può essere impiegato per applicare la conformità ai criteri di protezione all'interno della rete isolata.

Altre soluzioni di protezione basate su Active Directory consentono di automatizzare le attività che assicurano una conformità continua ai criteri di protezione nell'ambito della rete isolata trusted. Di conseguenza, un gruppo di confine dovrà affidarsi ai diversi metodi per garantire che i computer al suo interno non diventino i punti vulnerabili nella soluzione della rete isolata. È necessario convalidare la conformità di tali computer prima che vengano aggiunti al gruppo di confine. Inoltre, i computer devono disporre di criteri e metodi specifici che possano garantire la loro continua conformità ai requisiti dei criteri di protezione dei sistemi trusted.

###### Nozioni su IPsec

IPsec è uno standard di protezione IP (Internet Protocol) costituito da un meccanismo di protezione generale di criteri basati sul livello IP per fornire l'autenticazione host-per-host. Per definizione, i criteri IPsec sono regole e impostazioni di protezione che controllano il flusso del traffico in ingresso e in uscita su un sistema host. I criteri sono gestiti centralmente in Active Directory utilizzando gli oggetti Criteri di gruppo per l'assegnazione dei criteri ai membri del dominio. Consentono di stabilire comunicazioni sicure tra i membri del dominio, che rappresentano l'elemento di base di questa soluzione.

Lo standard IPsec utilizza il protocollo di negoziazione IKE (Internet Key Exchange) per negoziare le opzioni tra due host in modo da stabilire il metodo con cui comunicare in modo protetto con IPsec. Gli accordi stabiliti tra i due host e i diversi parametri che definiscono la negoziazione vengono chiamati associazioni di protezione. Microsoft Windows utilizza uno dei tre metodi IKE seguenti:

-   Protocollo di autenticazione Kerberos versione 5

-   Certificati digitali X.509 con coppie di chiavi RSA corrispondenti

-   Chiavi già condivise con passphrase

**Nota**   Sebbene sia possibile utilizzare l'infrastruttura PKI come metodo di autenticazione, a causa dell'integrazione dell'autenticazione dei domini Windows 2000 (Kerberos) nel protocollo di negoziazione IKE, si consiglia di non utilizzare l'approccio del protocollo PKI.

La negoziazione Windows IKE può essere configurata per consentire le comunicazioni con i computer che non rispondono alla richiesta di negoziazione IKE. Questa funzionalità è chiamata azione di fallback in comunicazioni di testo in chiaro. Oltre a rappresentare un'azione essenziale durante il processo di implementazione, è anche particolarmente utile in questo contesto poiché consente ai sistemi del gruppo di confine di comunicare con i membri della rete isolata. Alle comunicazioni che il protocollo IPsec non è in grado di proteggere viene fatto riferimento come associazione di protezione software. Tali associazioni vengono registrate come un evento di controllo con esito positivo nel Registro protezione.

Oltre all'autenticazione, il protocollo IPsec è in grado di eseguire altre funzioni utili, incluse la capacità di gestire l'integrità e la crittografia del traffico di rete tramite l'uso delle opzioni AH (Authentication Headers) ed ESP (Encapsulating Security Payload). Sebbene sia possibile utilizzare le intestazioni AH per assicurare che un pacchetto non venga modificato durante la trasmissione, l'uso delle intestazioni per questa attività rende il protocollo non compatibile con la NAT (Network Address Translation). È possibile utilizzare l'opzione ESP, solitamente per crittografare il traffico, nella modalità di crittografia Null (ESP/Null). Questa modalità permette di verificare l'integrità dei dati ed è compatibile con la NAT.

È possibile utilizzare il protocollo IPsec anche in due modalità diverse: trasporto o tunnel. La modalità di trasporto IPsec è il metodo consigliato per proteggere il traffico tra due host. Funziona semplicemente inserendo un'intestazione dopo l'intestazione IP originale e quindi applicando la crittografia alla parte rimanente del pacchetto con l'opzione AH o ESP. La modalità tunnel viene solitamente utilizzata per i tunnel VPN da gateway a gateway, dove i pacchetti originali e le intestazioni IP vengono incapsulati interamente e una nuova intestazione IPsec sostituisce l'intestazione IP originale.

Per ulteriori informazioni, vedere il documento Microsoft [Server and Domain Isolation](http://www.microsoft.com/technet/itsolutions/network/sdiso/default.mspx) (in inglese) all'indirizzo www.microsoft.com/technet/itsolutions/network/sdiso/default.mspx.

###### Difesa a più livelli

![](images/Cc875843.PNFUC04(it-it,TechNet.10).gif)

**Figura 4. Difesa a più livelli con isolamento logico**

Nella figura precedente viene mostrato il modo in cui l'isolamento logico si adatta al modello di difesa a più livelli. Sebbene la figura tenda a dimostrare che l'isolamento dei domini e dei server applichi un livello di protezione ai computer host, come farebbe un firewall basato su host, di fatto l'isolamento interessa l'area di autenticazione delle comunicazioni di rete con l'ausilio del protocollo IPsec. Sebbene questa soluzione si estenda dall'host alla rete interna, non risiede interamente né da una parte né dall'altra poiché si tratta di una soluzione di "isolamento logico". Pertanto, le funzionalità seguenti non rientrano nel proprio ambito:

-   L'isolamento logico non può proteggere le periferiche di rete, ad esempio i router.

-   L'isolamento logico non può proteggere i collegamenti di rete, al contrario di come fanno l'accesso WPA 802.11i per la crittografia wireless e il protocollo EAP-TLS 802.1x per il controllo dell'accesso wireless.

-   L'isolamento logico non può fornire la protezione a tutti gli host della rete poiché è in grado di controllare solo i sistemi con credenziali di un computer trusted e criteri IPsec basati sul dominio.

-   L'isolamento logico non è adatto e non prevede un metodo di configurazione automatico che possa proteggere i percorsi a livello di applicazione, come invece fanno i protocolli HTTPS e SSL per le applicazioni Web.

È importante capire e considerare qual è il ruolo dell'isolamento logico in una soluzione completa per la difesa a più livelli. Da sola, questa soluzione non può garantire la protezione di tutto ciò che concerne l'infrastruttura di un'azienda di medie dimensioni. Tuttavia, se utilizzata come parte di una soluzione completa, può assumere un ruolo veramente importante.

##### Utilizzo dei servizi di quarantena VPN per proteggere il sistema dai computer remoti non gestiti

Dal punto di vista della protezione, i sistemi remoti che utilizzano soluzioni VPN per accedere alla rete di un'azienda pongono delle proprie problematiche. La maggior parte delle soluzioni di accesso remoto è in grado di convalidare solamente le credenziali di un utente remoto ma non di verificare che il computer remoto sia conforme ai criteri di protezione. Questo approccio di convalida rappresenta un problema poiché potenzialmente vanifica gli sforzi compiuti per proteggere una rete dalle minacce associate a problemi quali, ad esempio: file delle firme antimalware e livelli di aggiornamento della protezione obsoleti, impostazioni di routing non valide e protezione firewall non adeguata.

La funzione Controllo quarantena accesso alla rete di Microsoft Windows Server 2003 consente di risolvere questo problema. Questa funzione blocca l'accesso remoto a una VPN fin quando non è possibile constatare come conforme agli standard dei criteri di protezione correnti lo stato della configurazione del computer che sta tentando di connettersi.

###### Nozioni sui servizi di quarantena VPN

Controllo quarantena accesso alla rete è una funzione disponibile nella famiglia dei prodotti Windows Server 2003. Questa funzione blocca i normali servizi di accesso remoto fin quando i computer remoti che stanno tentando l'accesso non vengono esaminati e convalidati da un apposito script configurato dall'amministratore. Solitamente, quando viene avviata una sessione remota, l'utente viene autenticato e al computer remoto viene assegnato un indirizzo IP. A questo punto, la connessione viene messa in quarantena, ovvero l'accesso alla rete viene bloccato fin quando non viene eseguito lo script dell'amministratore sul computer remoto. Una volta completata l'esecuzione dello script e notificato al server di accesso remoto che il computer remoto soddisfa i criteri di rete configurati, la modalità quarantena viene rimossa e il computer remoto viene autorizzato ad accedere alla rete.

È possibile applicare le restrizioni seguenti a una connessione remota messa in quarantena:

-   È possibile configurare un gruppo di filtri di pacchetti di quarantena per limitare il tipo di traffico in uscita e in entrata di un client.

-   È possibile configurare la durata di una sessione di quarantena per limitare il periodo di tempo che un client può rimanere connesso fin quando si trova nello stato di quarantena.

È possibile utilizzare la funzione Controllo quarantena accesso alla rete come parte di una soluzione di protezione completa per applicare i criteri di protezione e assicurare che ai sistemi untrusted venga vietato l'accesso ai sistemi trusted. Pertanto, questa funzione non può essere considerata una vera e propria soluzione di protezione e da sola non è sufficiente per impedire le connessioni da parte di utenti malintenzionati che sono riusciti a ottenere un gruppo di credenziali valide.

**Nota**   La funzione Controllo quarantena accesso alla rete non è la funzione Protezione accesso alla rete, una nuova piattaforma per l'applicazione dei criteri che verrà inclusa nella prossima generazione della famiglia di sistemi operativi Windows Server Longhorn. Per ulteriori informazioni sulla funzione Protezione accesso alla rete, vedere l'"Appendice A: Protezione accesso alla rete" alla fine di questo documento.

###### Componenti della funzione Controllo quarantena accesso alla rete

[![](images/Cc875843.PNFUC05(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875843.pnfuc05_big(it-it,technet.10).gif)

**Figura 5. Componenti della funzione Controllo quarantena accesso alla rete di Windows**

Nella figura precedente sono rappresentati i componenti tipici di una soluzione di accesso remoto Windows che utilizza la funzione Controllo quarantena accesso alla rete. I componenti includono:

-   **Client di accesso remoto compatibile con la funzione di quarantena**. Questo componente è un computer con una versione del sistema operativo Windows in grado di supportare i profili CM creati con CMAK (Connection Manager Administration Kit), un kit di amministrazione fornito con Windows Server 2003. Questo supporto è disponibile in Windows a partire dalle versioni di Windows 98 Second Edition. In questi computer client deve essere installato un componente di notifica e deve essere presente uno script per i requisiti dei criteri di rete. Inoltre, i computer devono essere configurati per eseguire lo script come azione di post-connessione.

-   **Server di accesso remoto compatibile con la funzione di quarantena**. Questo componente è un computer Windows Server 2003 con il servizio Routing e Accesso remoto in esecuzione, che supporta l'uso di un componente listener e degli attributi VSA RADIUS MS-Quarantine-IPFilter e MS-Quarantine-Session-Timeout specifici di un fornitore insieme a un componente listener installato.

-   **Server RADIUS compatibile con la funzione di quarantena**. Questo componente è facoltativo e viene utilizzato quando si configura l'autenticazione RADIUS sul server di accesso remoto su cui è in esecuzione Windows Server 2003 e il servizio IAS per supportare le VSA RADIUS MS-Quarantine-IPFilter e MS-Quarantine-Session-Timeout.

-   **Risorse servizio in quarantena**. Questi componenti sono i server e i servizi a cui il client remoto può accedere mentre si trova nello stato di quarantena. Solitamente, questi componenti sono server che forniscono i servizi DNS, i profili CM oppure gli aggiornamenti della protezione per rendere i client conformi ai requisiti stabiliti.

-   **Database degli account**. Solitamente, questo componente dovrebbe essere il dominio Active Directory in cui sono memorizzati gli account utente e dove è possibile trovare le proprietà di connessione remota.

-   **Criterio di accesso remoto in quarantena**. Questo criterio è necessario per fornire le condizioni richieste affinché possano essere stabilite le connessioni di accesso remoto e per specificare gli attributi MS-Quarantine-IPFilter o MS-Quarantine-Session-Timeout.

###### Difesa a più livelli

![](images/Cc875843.PNFUC06(it-it,TechNet.10).gif)

**Figura 6. Difesa a più livelli e Controllo quarantena accesso alla rete**

Come mostrato nel modello di difesa di Microsoft della figura, la quarantena VPN occupa tre livelli del modello; host, rete interna e perimetro. Sebbene questa soluzione non protegga direttamente il client, protegge i server dalle minacce che possono essere introdotte dai client remoti che non soddisfano i requisiti di protezione. Inoltre protegge indirettamente anche i clienti remoti controllando che soddisfino i requisiti dei criteri per funzionare in modo appropriato e invitandoli a tenersi costantemente aggiornati.

Inoltre, questa soluzione aumenta la protezione della rete stessa dagli effetti dannosi che i computer remoti rogue possono generare quando non sono configurati correttamente, inclusa la propagazione di malware, che può avere effetti negativi sulle prestazioni della rete. Sebbene il perimetro possa sembrare un elemento poco importante in questo scenario, dal momento che questa soluzione non impedisca direttamente la possibilità di attacchi brute force alla VPN (che risiede sul perimetro), tuttavia pone l'attacker di fronte a un altro livello di protezione con il quale deve combattere per ottenere l'accesso diretto alle risorse che risiedono nella rete interna. E ciò anche nel caso in cui l'attacker sia riuscito a ottenere le credenziali per l'autenticazione.

##### Utilizzo dell'autenticazione 802.1X per proteggere il sistema contro i client wireless non gestiti

L'uso dello standard 802.1X IEEE (Electrical and Electronic Engineers) è più adatto alle attività di difesa delle reti wireless dagli accessi non autorizzati. A meno che un computer non sia configurato per essere autorizzato a comunicare nella rete, semplicemente non potrà comunicare. Sebbene questa soluzione funzioni correttamente nelle reti wireless, non è così efficiente nelle reti cablate, anche se può comunque essere impiegata. L'efficienza limitata di questa soluzione è il motivo per cui in questo documento viene consigliato un approccio combinato per applicare misure di protezione alla rete di un'azienda di medie dimensioni. Utilizzando una combinazione delle soluzioni più efficienti in grado di gestire tutti gli aspetti di una tipica rete di un'azienda, è possibile implementare una soluzione di difesa a più livelli decisamente più potente.

###### Nozioni sull'autenticazione IEEE 802.1X

L'autenticazione IEEE 802.1X è un meccanismo di controllo basato sulle porte che può essere configurato per richiedere l'autenticazione reciproca tra i client e una rete. Se implementata, qualsiasi periferica la cui autenticazione non viene accettata non potrà comunicare con la rete in questione.

L'autenticazione 802.1X supporta il protocollo EAP (Extensible Authentication Protocol) che prevede un numero di varianti. Tra queste, tre in particolare sono supportate dalle versioni correnti di Microsoft Windows pronte per l'uso:

-   **EAP-MD5**. Con la variante MD5, un server di autenticazione invia una richiesta a un client (supplicant) e il supplicant combina la richiesta con il proprio identificatore e passphrase. La risposta viene convertita in un hash MD5 e restituita al server di autenticazione, che la decrittografa e confronta la risposta con la richiesta originale. Se la risposta corrisponde, l'autenticazione ha luogo. Questo metodo non è sicuro nella maggior parte delle implementazioni poiché prevede l'invio di password che possono essere intercettate e decrittografate da terzi.

-   **PEAP (EAP Protected)**. Il metodo PEAP utilizza un certificato sul lato server e informazioni sull'autenticazione del client (quali i nomi utente e le password) per stabilire l'autenticazione reciproca. L'implementazione Microsoft di questo standard utilizza MS-CHAPv2, che per stabilire l'autenticazione si affida alle informazioni sull'account e sul dominio tradizionali e su un server RADIUS. Solitamente, questo metodo è considerato sufficientemente sicuro per gli ambienti di piccole dimensioni che non possono sostenere i requisiti, quali le infrastrutture e le attività di amministrazione aggiuntive, che prevede il metodo EAP-TLS.

-   **EAP-TLS**. Con questo metodo, un server di autenticazione imposta una sessione TLS (Transport Layer Security) con il supplicant per inviare al client un certificato digitale. Quando il supplicant riceve il certificato, lo convalida e quindi invia il proprio certificato in risposta. La risposta, a sua volta, viene convalidata dal server di autenticazione. Se entrambi i lati della comunicazione ritengono attendibili i certificati, l'autenticazione ha luogo. Questo approccio è più adatto per le reti che possono supportare un'infrastruttura PKI e i server di autenticazione RADIUS. Rappresenta, inoltre, l'opzione più sicura disponibile per le reti wireless, specialmente se utilizzata insieme allo standard 802.11i WPA2.

Affinché un client possa eseguire l'autenticazione, deve affidarsi a un autenticatore (un punto di accesso wireless o uno switch di rete) fin quando non viene autenticato dal server di autenticazione. Di conseguenza, durante l'handshake di autenticazione iniziale tutte le comunicazioni vengono inoltrate dall'autenticatore tra il supplicant e il server di autenticazione. Quando l'autenticazione è completata, il supplicant può accedere direttamente alla rete.

###### Motivi per cui il metodo 802.1X non è adatto alle reti cablate

Sebbene, generalmente, il metodo 802.1X sia adatto per la protezione delle reti wireless, presenta alcuni problemi se viene utilizzato per proteggere le reti cablate. Ad esempio, anche se il metodo 802.1X disponga di numerosi oggetti Criteri di gruppo di Active Directory che supportano l'implementazione nelle reti wireless, non supporta l'autenticazione 802.1X nelle reti cablate. Pertanto, in un'implementazione di questo tipo, il metodo 802.1X potrebbe richiedere un notevole carico di gestione. Inoltre, molte periferiche (switch, stampanti di rete e altre infrastrutture delle reti cablate) non supportano il metodo 802.1X. Pertanto, l'implementazione di questo tipo di metodo nella maggior parte delle reti delle aziende di medie dimensioni è probabile che possa richiedere costi elevati di aggiornamento.

Oltre ai costi di amministrazione e di infrastruttura associati a questo tipo di implementazione, l'uso di questi standard destinati alle reti wireless può presentare alcuni problemi nelle reti cablate. Ad esempio, poiché l'autenticazione 802.1X ha luogo solo quando una connessione viene stabilita e il metodo 802.1X non ha il controllo degli hub, tutto quello che un attacker deve fare è attaccare un hub verso la rete interna con un computer autenticato e utilizzare un computer “ombra” con il quale completare l'attacco.

**Nota**   Gli svantaggi e le vulnerabilità appena descritti non si applicano alle reti wireless. I problemi con la protezione 802.1X si presentano solo se il metodo viene utilizzato nelle reti cablate.

A causa di questi problemi, per l'isolamento dei domini e dei server si consiglia l'uso del metodo IPsec al posto del metodo 802.1X. Tuttavia, questa raccomandazione non implica il fatto che non sia possibile utilizzare in assoluto il metodo 802.1X nella rete di un'azienda di medie dimensioni. Come indicato in precedenza, il metodo 802.1X è uno strumento valido per i problemi di protezione nelle reti wireless ed è possibile aumentarne il livello di protezione solo aggiungendo una soluzione di isolamento delle reti basata su IPsec.

###### Difesa a più livelli

![](images/Cc875843.PNFUC07(it-it,TechNet.10).gif)

**Figura 7. Difesa a più livelli con la protezione wireless 802.1X**

Come mostrato nella figura precedente, la protezione wireless tramite l'autenticazione 802.1X occupa il livello della rete nel modello di difesa a più livelli. Sebbene possa sembrare che la protezione wireless copra anche il perimetro della rete, le reti wireless sono di fatto una parte della rete locale mentre il perimetro potrebbe estendersi oltre e comprendere reti esterne, quali Internet. Alcune parti dei metodi di protezione wireless prevedono componenti host; tuttavia, la protezione wireless non è progettata per proteggere direttamente gli host.

##### Utilizzo di SMS per rilevare e aggiornare i sistemi non gestiti

Microsoft Systems Management Server (SMS) 2003 viene spesso utilizzato per gestire i computer della rete e le informazioni sull'inventario dei beni, consegnare il software e gli aggiornamenti in modo da mantenere la conformità ai criteri di protezione e gestire le piattaforme e l'installazione del software. I metodi Network Discovery e Inventario di SMS 2003 sono oggetto di questo documento poiché offrono un metodo che può aiutare a rilevare i sistemi untrusted quando si collegano alla rete. Questa funzionalità fornisce anche un metodo per l'aggiornamento, in base ai criteri implementati come risposta all'uso dei computer non gestiti.

In questo documento si assume che il lettore abbia utilizzato il metodo SMS e altri metodi per rendere i computer membri del dominio conformi ai criteri di protezione; ciò potrebbe includere il fatto che siano installati tutti gli aggiornamenti della protezione più recenti. Pertanto, gli argomenti sulla gestione delle patch con SMS 2003 e altri strumenti non rientrano nell'ambito di questo documento. Per ulteriori informazioni su questi argomenti e altre informazioni correlate al metodo SMS, vedere il documento [Patch Management Using Systems Management Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=959ee7d6-7ddf-409a-9522-7d270bdcf12a&displaylang=en) (in inglese) all'indirizzo http://www.microsoft.com/downloads/details.aspx?familyid=E9EAB1BD-13E7-4E25-85C5-CE2D191C3D63&displaylang;=en oppure accedere alla home page [Microsoft Systems Management Server](http://www.microsoft.com/smserver/default.mspx) all'indirizzo www.microsoft.com/smserver/default.mspx.

###### Individuazione e documentazione dei beni esistenti

Per le aziende che hanno già implementato il metodo SMS, la documentazione dei beni esistenti sarà stata probabilmente già effettuata e quindi sarà stato anche generato l'inventario dei sistemi gestiti e non gestiti. Questo inventario deve contenere le informazioni sui requisiti e le procedure di aggiornamento della protezione per i computer che non sono gestiti dal metodo SMS, sia a causa del design oppure perché non sono previsti agenti per il tipo di client. I computer non gestiti possono includere le periferiche che si trovano nel perimetro coperto dalla protezione (conosciuto anche come rete perimetrale), computer di test oppure periferiche autonome.

È importante disporre di un elenco aggiornato delle periferiche che non vengono gestite dal server SMS, non solo a causa dei requisiti di protezione, ma anche perché questo elenco deve essere utilizzato per il confronto con qualsiasi nuova informazione di inventario in modo da determinare se i nuovi sistemi individuati siano sistemi autorizzati oppure sconosciuti. Per tenere sempre aggiornati questi elenchi è importante utilizzare un processo attivo che inserisca in tali elenchi i nuovi sistemi non gestibili che vengono aggiunti alla rete di un'azienda. Oltre alle informazioni sull'identità, questo processo deve essere utilizzato per proteggere tali sistemi e le assegnazioni di proprietà.

Sebbene il server SMS potrebbe non essere in grado di raccogliere informazioni sufficienti sui sistemi non gestiti, oltre all'indirizzo IP e al nome, spesso queste uniche informazioni sono sufficienti per determinare se le nuove periferiche di rete siano autorizzate o meno.

#### Sviluppo

Nella sezione "Valutazione" è stato spiegato che la combinazione di soluzioni diverse in grado di offrire funzioni specifiche nella rete di un'azienda di medie dimensioni è l'approccio più completo per proteggere tale rete. L'isolamento dei domini e dei server protegge la rete cablata per assicurare che solo i computer conosciuti e gestiti possano accedere alle risorse trusted. I servizi di quarantena VPN assicurano che i sistemi remoti che si connettono solo occasionalmente alla rete locale siano comunque conformi ai criteri di protezione. L'autenticazione 802.1X protegge la rete wireless in modo che solo le periferiche autorizzate possano stabilire le connessioni. In ultimo, il metodo SMS viene utilizzato per assicurare la conformità dei computer trusted e individuare i computer untrusted rogue quando si connettono alla rete. La combinazione di tutte queste soluzioni consente di proteggere una rete contro le connessioni non autorizzate e i computer rogue.

Oltre a descrivere i requisiti necessari per implementare tali soluzioni, questa sezione riporta anche alcuni dei potenziali problemi che devono essere risolti per assicurare che ogni soluzione sia l'approccio più appropriato per ciascun ambiente di un'azienda di medie dimensioni.

##### Utilizzo dell'IPsec per isolare i domini e i server

Per sviluppare un piano per isolare i domini e i server di una rete IPsec, è necessario determinare se la soluzione è idonea per un determinato ambiente di rete e raccogliere le informazioni sui prerequisiti per stabilire un piano di implementazione. Il concetto di isolamento delle reti IPsec è stato introdotto nella sezione "Valutazione" di questo documento. Ora che i vantaggi che possono derivare da questo approccio sono noti, è possibile valutarli per determinare tutti i possibili problemi che possono essere associati a un'implementazione di questo tipo. In questa sezione verranno trattate alcune problematiche correlate all'implementazione di una soluzione per isolare una rete IPsec, insieme ai requisiti di un'implementazione di questo tipo, che possono semplificare il processo decisionale.

###### Identificazione dell'architettura della rete

Poiché il protocollo IPsec è un livello stesso del protocollo IP, la conoscenza dettagliata dell'infrastruttura di rete corrente e del flusso del traffico è essenziale per assicurare la distribuzione della soluzione. Sebbene le informazioni relative agli schemi di indirizzamento IP, i layout delle subnet e i modelli di traffico della rete siano fattori importanti che richiedono attenzione, la documentazione dettagliata della segmentazione della rete e il modello di flusso del traffico della rete corrente sono assolutamente essenziali per sviluppare e distribuire con successo un piano efficiente di isolamento della rete.

**Nota**   I dettagli della documentazione dell'ambiente di rete non sono oggetto di questo documento. La creazione di tale documentazione è vitale per il successo di qualsiasi iniziativa mirata alla protezione totale della rete come, ad esempio, nel caso di questa soluzione. Pertanto, se non si dispone della documentazione e fin quando non ne viene completata la creazione, il livello di rischio a cui si viene esposti se si esegue comunque l'implementazione di progetti di questo tipo è elevatissimo.

La documentazione dell'architettura della rete deve essere la più accurata possibile e riportare i dettagli correnti con attenzione alle informazioni seguenti:

-   Dettagli e posizione del firewall e del bilanciamento del carico

-   Informazioni sulle periferiche della rete, tra cui dimensione della RAM, marca/modello e impostazioni MTU

-   Report sul traffico e utilizzo della rete

-   Uso della NAT

-   Segmentazione VLAN

-   Collegamenti della rete delle periferiche

-   Informazioni sul sistema di identificazione delle intrusioni

###### Identificazione del flusso del traffico di rete

Oltre alle informazioni sulle periferiche e sulle configurazioni che possono influenzare l'isolamento della rete IPsec, è importante esaminare i modelli di traffico di rete nella rete. Quando si raccolgono queste informazioni è importante tenere presente alcuni fattori, ad esempio in che modo le periferiche non Windows (quali i computer Linux) oppure le periferiche che utilizzano versioni di Windows precedenti a Windows 2000 SP4 comunicano con gli altri sistemi basati su Window. Altre considerazioni includono:

-   Le subnet sono state create per tipi specifici di traffico, ad esempio le comunicazioni con i mainframe?

-   Il traffico tra le diverse ubicazioni deve essere separato?

-   Esistono tipi di traffico che richiedono un elevato livello di protezione quale quello che può garantire la crittografia, ad esempio le comunicazioni con un database HR?

-   Esistono periferiche di protezione o regole firewall che possono impattare sull'implementazione, ad esempio il blocco UDP sulla porta 500?

-   In che modo comunicazioni le applicazioni? Ad esempio, viene utilizzata la funzione RPC (Remote Procedure Call), per la quale sono necessarie ulteriori considerazioni?

-   In che modo avvengono le comunicazioni tra gli host e i server? Vengono utilizzate connessioni a livello di porta/protocollo oppure vengono stabilite più sessioni tramite numerosi protocolli di tipo diverso?

###### Identificazione della struttura Active Directory

Per comprendere quale impatto può avere l'implementazione IPsec in una struttura Active Directory, oltre alle informazioni sulla rete determinate in precedenza è importante raccogliere informazioni sulla struttura della foresta Active Directory, sul layout dei domini, sul design delle unità organizzative e sulla topologia dei siti. Le informazioni dovrebbero includere:

-   Numero di foreste

-   Numero e nomi di domini

-   Numero e tipi di relazioni trust

-   Numero e nomi dei siti

-   Struttura delle unità organizzative e dei criteri di gruppo

-   Qualsiasi informazioni sui criteri IPsec esistenti (se il metodo IPsec viene effettivamente utilizzato)

###### Identificazione degli host

Alcune delle informazioni host importanti che devono essere raccolte, includono:

-   Nomi dei computer

-   Indirizzi IP, in special modo gli indirizzi statici

-   Indirizzi MAC

-   Versione del sistema operativo, inclusi i livelli di service pack e di revisione degli aggiornamenti rapidi

-   Appartenenza ai domini

-   Posizione fisica

-   Tipo e ruolo dell'hardware

###### Identificazione delle considerazioni sulla capacità IPsec

Quando si sviluppa un piano per implementare il protocollo IPsec ci sono alcune considerazioni sulla pianificazione della capacità di cui bisogna tenere conto. In particolare nel caso in cui si debba utilizzare la crittografia IPsec poiché impegna risorse host e sovraccarica la rete. Alcune considerazioni includono:

-   **Utilizzo della memoria del server**. Ciascuna sessione può impegnare fino a 5 KB di RAM.

-   Utilizzo CPU dei **server,** **delle workstation,** **e delle periferiche dell'infrastruttura**. Queste informazioni sono particolarmente significative per i server. Permette di controllare che le periferiche non siano già troppo sovraccariche.

-   **Latenza e utilizzo della rete**. Quando si utilizza il metodo IPsec, la latenza aumenta. Quando Microsoft ha implementato il protocollo IPsec, l'utilizzo della rete aumentò dall'1% al 3%.

-   **Uso della NAT e del tipo di crittografia**. Le comunicazioni AH non possono attraversare le NAT. Pertanto, è consigliabile utilizzare il metodo ESP per la crittografia delle comunicazioni. Il metodo ESP richiede maggior utilizzo rispetto alla crittografia AH, a meno che la crittografia ESP non venga utilizzata.

-   **Impatto Criteri di gruppo**. Gli oggetti Criteri di gruppo IPsec hanno un impatto sull'avvio del sistema e sui tempi di accesso. Prima e dopo le implementazioni dei test è opportuno prendere nota delle linee di base per determinare l'effetto reale su tali accessi.

###### Identificazione dei livelli di trust

Un'altra considerazione importante è determinare quali host partecipano a questa soluzione e in che misura. Per questa valutazione è necessario stabilire una chiara definizione delle condizioni che devono essere soddisfatte come trust e quale grado di trust deve esistere. Le informazioni seguenti possono facilitare questo processo fornendo alcune chiare definizioni di trust, i criteri necessari per soddisfare i determinati livelli di affidabilità e in che modo questi elementi impattano sul processo di pianificazione.

Esistono quattro stati di base che possono essere applicati a un host relativamente ai livelli di trust. A partire dal livello di affidabilità più alto, gli stati sono:

-   **Trusted**. Lo stato Trusted implica che l'host può gestire i rischi di protezione e che gli altri host trusted sono in grado di presupporre che da tale host non verrà mai eseguita un'azione dannosa. Sebbene questo stato non indica che l'host sia completamente protetto, assicura comunque che sia sotto la responsabilità di un reparto IT e controllato da alcuni meccanismi (processo automatico o documentato).

    Poiché l'host è trusted, le comunicazioni tra questo e altri host trusted non dovrebbero essere ostacolate dall'infrastruttura di rete. Dal momento che si può ritenere certo che da questo host non verrà eseguita alcuna azione dannosa, non c'è alcuna necessità di bloccare o filtrare il traffico che proviene dall'host per mezzo di firewall o altre misure di protezione simili.

-   **Trustworthy**. Lo stato Trustworthy indica che sebbene un computer sia in grado di diventare una periferica trusted, richiede ancora ulteriori modifiche o aggiornamenti alla configurazione per essere certificato come trusted. L'identificazione di questo tipo di computer è particolarmente importante durante la fase di progettazione, poiché fornisce alcune indicazioni utili sull'impegno, in termini di sforzi e denaro, a cui si potrebbe andare incontro per configurare una rete isolata.

-   **Known,** **Untrusted**. Esistono diversi motivi per cui un computer noto potrebbe non essere in grado di diventare una periferica trusted, dai finanziamenti limitati ai requisiti aziendali, fino alle problematiche dal punto di vista funzionale. Ad esempio, i fondi destinati a un progetto potrebbero non essere sufficienti per aggiornare tutti i computer, alcune Business Unit potrebbero avere la proprietà dei propri domini oppure un'applicazione di vecchia data potrebbe non essere compatibile con i sistemi operativi supportati correnti e quindi non eseguibile su un computer protetto.

    Indipendentemente dal motivo, è opportuno consultare i proprietari dei computer noti ma untrusted per determinare se è possibile fare qualcosa per rendere conformi i loro computer e per decidere in che modo affrontare questo problema pur mantenendo un profilo di rischio accettabile.

-   **Unknown,** **Untrusted**. Lo stato Unknown, Untrusted dovrebbe essere lo stato predefinito di tutti gli host. Gli host in questo stato non sono gestiti e le loro configurazioni sono sconosciute. In questa situazione, non è possibile assegnare alcuno stato trusted a questo tipo di periferiche. Dovrebbe essere chiaro che gli host con questo stato possono essere facilmente compromessi e utilizzati come piattaforme per attività dannose e pertanto possono porre l'azienda di fronte a un livello di rischio inaccettabile. Questa soluzione è progettata per ridurre il potenziale impatto sui sistemi di questo tipo.

###### Utilizzo delle informazioni raccolte

Una volta raccolte tutte le informazioni necessarie, sarà possibile sviluppare un piano di implementazione e determinare se la soluzione di isolamento della rete basato su IPsec è appropriata per l'ambiente di rete effettivo. Alcune delle considerazioni che possono influenzare l'implementazione della soluzione includono:

-   Costo degli aggiornamenti richiesti per rendere gli host conformi allo stato trusted e compatibili con i requisiti IPsec.

-   Costo degli aggiornamenti o delle sostituzioni dell'infrastruttura se le periferiche di rete correnti non supportano il protocollo IPsec.

-   Valutazione della possibile perdita di QoS basato su router a fronte dei vantaggi in termini di protezione che possono derivare dall'isolamento della rete, poiché l'impostazione della priorità basata sulle porte non funziona se viene implementato il protocollo IPsec, mentre continua a funzionare il QoS basato sugli indirizzi.

-   Network Monitor e le periferiche IDS potrebbero non funzionare quando si implementa il protocollo IPsec, in particolar modo se si utilizza la crittografia ESP. È possibile utilizzare i parser per risolvere il problema, se la periferica dispone di un parser IPsec.

-   L'implementazione del protocollo IPsec può richiedere aggiornamenti dell'hardware a causa del maggior utilizzo e numero di richieste a cui vengono sottoposti la CPU e la memoria dei server e delle periferiche di rete.

-   Anche la gestione può diventare un problema, poiché la latenza della rete potrebbe aumentare.

-   Anche la gestione dei fornitori e degli utenti guest potrebbe generare un sovraccarico eccessivo, poiché solitamente questi utenti fanno uso di periferiche untrusted e potrebbero avere diversi motivi per accedere alle risorse di rete nella rete isolata. Potrebbe diventare complesso gestire queste eccezioni, a causa del fatto che il numero e la frequenza aumentano costantemente. Tuttavia, è possibile limitare il problema utilizzando un'area di confine tra le reti trusted e quelle untrusted.

Questi problemi dimostrano quanto sia importante eseguire attività di pianificazione e test con attenzione prima di implementare modifiche che possano alterare l'intera rete, quali l'implementazione del protocollo IPsec e l'isolamento della rete. È opportuno valutare con estrema attenzione qualsiasi considerazione non solo per determinare il metodo da utilizzare per implementare la soluzione, ma anche per stabilire se sia possibile effettivamente implementare la soluzione a causa dello stato corrente della rete e dei costi finanziari e politici che sono necessari per rendere la rete conforme agli standard richiesti. Inoltre, è opportuno prendere in considerazione anche le distribuzioni limitate o incrementali come possibile strategia di implementazione meno invasiva.

L'isolamento della rete basato su IPsec è solo una parte di una soluzione completa. Ogni soluzione descritta in questa guida aiuta a implementare strategie di difesa contro le periferiche untrusted che possono connettersi alla rete. Tuttavia, è possibile utilizzare le singole soluzioni descritte, perché ciascuna è in grado da sola di aumentare il livello di protezione di una rete. Pertanto, anche se l'isolamento dei domini e dei server IPsec non è una soluzione accettabile al momento, può essere ritenuta ancora valida per implementare le altre soluzioni descritte in questa guida e perfino tornare utile all'isolamento della rete dopo che una rete è stata aggiornata e resa compatibile con i requisiti descritti in questo documento.

##### Utilizzo dei servizi di quarantena VPN per proteggere il sistema dai computer remoti non gestiti

In una sessione server di accesso remoto Windows standard, il server esegue le azioni seguenti quando un client di accesso remoto avvia una sessione:

1.  Il server di accesso remoto controlla i criteri di accesso remoto del client e consente la connessione.

2.  Il server verifica le autorizzazioni di accesso remoto dell'utente.

3.  Il server quindi autentica le credenziali utente utilizzando Active Directory o un altro tipo di servizio di autenticazione.

4.  Il server assegna un indirizzo IP al client remoto.

A questo punto, il client remoto dispone dell'accesso completo alla rete. Nessun controllo è stato eseguito per verificare i livelli di aggiornamento, la presenza o lo stato di aggiornamento del software antivirus o qualsiasi altra informazione correlata ai criteri di protezione. Questa funzionalità non è il massimo a cui si possa aspirare, poiché a volte è possibile che gli aggiornamenti, le modifiche alla configurazione o le patch non vengano applicati agli utenti remoti oppure ai computer in roaming.

Tuttavia, una connessione di tipo quarantena VPN è diversa, come mostrato nella figura e nell'elenco che seguono:

[![](images/Cc875843.PNFUC08(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875843.pnfuc08_big(it-it,technet.10).gif)

**Figura 8. Processo quarantena VPN**

1.  Il client remoto esegue uno script di pre-connessione di Connection Manager che verifica i prerequisiti di connessione di base (ad esempio, il livello di aggiornamento della protezione e la data del file della firma dei virus) e memorizza i risultati. Dopo l'esecuzione dello script, il client stabilisce una sessione di accesso remoto tramite un tunnel VPN.

2.  Il server di accesso remoto autentica le credenziali utente tramite RADIUS, che passa ad Active Directory il controllo delle credenziali.

3.  Una volta che Active Directory ha autenticato l'utente, il server di accesso remoto mette il client in quarantena applicando il criterio di accesso remoto. Durante lo stato di quarantena, l'accesso alla rete è limitato alle azioni specificate dal criterio di quarantena. È possibile ottenere l'accesso limitato tramite un filtro IP che autorizza l'accesso solo a determinate risorse che possono essere utilizzate per aggiornare un client allo stato di conformità oppure specificando un periodo di timeout, oltre il quale il client verrà automaticamente disconnesso.

4.  Uno script di post-connessione notifica al server di accesso remoto se il client è conforme ai requisiti specificati o meno. Se la connessione non soddisfa i requisiti entro il periodo di timeout, all'utente viene inviata un'apposita notifica e la connessione viene interrotta.

5.  Se lo script di post-connessione indica che il client ha soddisfatto i requisiti specificati, il server di accesso remoto rimuove il client dallo stato di quarantena eliminando le restrizioni del filtro IP e concedendo l'autorizzazione per l'accesso alle risorse di rete specificate dal criterio di accesso remoto.

Un client di accesso remoto può solo accedere alle risorse che risiedono nella rete in quarantena specificata. Ciò è valido sia che si tratti di una subnet separata sia che si tratti di un gruppo definito di server disponibili su Internet. Una rete in quarantena deve fornire le risorse che consentano a un client remoto di eseguire le attività per rendere conforme un computer remoto agli standard di sicurezza. Solitamente, tali risorse devono includere l'accesso a un server DNS per la risoluzione dei nomi, un file server da cui recuperare gli aggiornamenti e, in ultima ipotesi, un server Web per le istruzioni o gli aggiornamenti Web.

L'uso di una subnet in quarantena in questo processo potrebbe richiedere un periodo di timeout delle sessioni più lungo. Ciò, per assicurare che ci sia tempo sufficiente per scaricare e installare gli aggiornamenti sul computer client remoto. Per evitare questo problema, il computer client potrebbe essere reindirizzato all'uso di altre origini oppure di server disponibili su Internet, all'esterno della sessione VPN, sebbene questo approccio richieda uno script molto più complesso e potrebbe presentare altri problemi di protezione. In ogni caso, è lo script che determina il comportamento della quarantena e non la rete in quarantena stessa.

**Nota**   È possibile codificare in uno script i criteri IPsec se la soluzione di quarantena deve gestire i sistemi uniti di tipo non dominio. In questi casi, per supportare l'autenticazione IPsec è possibile utilizzare il comando netsh o l'eseguibile lpseccmd.exe per applicare semplici criteri con certificati. Il protocollo IPsec può essere utilizzato per i sistemi uniti basati su domini nelle configurazioni di quarantena VPN e come soluzione basata sui livelli.

###### Componenti client del servizio quarantena VPN

Come descritto nella sezione precedente, il primo passaggio del processo di quarantena VPN inizia con il client, in particolar modo con lo script di pre-connessione di Connection Manager. Connection Manager è una parte del kit CMAK (Connection Manager Administration Kit), che centralizza e automatizza la creazione e la gestione delle connessioni di rete e supporta diverse aree chiave di una configurazione di quarantena VPN, inclusi:

-   Controlli della protezione di pre-connessione per gestire in modo automatico le configurazioni dei computer client.

-   Controlli della protezione di post-connessione e convalide degli accessi.

Connection Manager consente agli amministratori di impostare azioni personalizzate tramite profili che possono essere distribuiti a più computer. Questa capacità semplifica il processo di connessione per gli utenti remoti, limitando il numero di impostazioni che tali utenti possono modificare. Alcune delle impostazioni che possono essere modificate includono:

-   Creazione di elenchi di numeri telefonici da utilizzare per le connessioni remote.

-   Personalizzazione di elementi grafici, icone, messaggi e testo della Guida in linea.

-   Esecuzione di azioni personalizzate di pre e post-connessione, che possono includere attività quali il ripristino del profilo del dialer o la configurazione di regole di filtro pacchetti di Windows Firewall.

Un altro componente CMAK è l'agente client (RQC.exe), che comunica con il Servizio quarantena accesso remoto (RQS.exe) sul server di accesso remoto utilizzando la porta TCP 7250. Quando viene stabilita una connessione di quarantena, il servizio RQS invia una chiave segreta condivisa all'agente client RQC. Se il client soddisfa le condizioni necessarie, l'agente client RQC invia la chiave condivisa per rimuovere il client dallo stato di quarantena.

I profili Connection Manager sono pacchetti dialer client autoestraenti e personalizzati di Connection Manager che possono essere creati e configurati utilizzando il kit CMAK. La procedura guidata CMAK consente agli amministratori di configurare il profilo, che può essere quindi distribuito utilizzando diversi metodi, a partire da Criteri di gruppo fino alla distribuzione del software Microsoft Systems Management Server (SMS) 2003. Quando lo script creato viene eseguito sul computer client, installa il profilo sul computer locale insieme alle impostazioni necessarie per stabilire le comunicazioni con i server di accesso remoto. Una volta completata l'installazione, per stabilire una connessione l'utente deve solo immettere il nome del profilo nel menu **Connetti** di Windows XP.

Per ulteriori informazioni sul kit CMAK, vedere la pagina [Connection Manager Administration Kit](http://technet2.microsoft.com/windowsserver/en/library/be5c1c37-109e-49bc-943e-6595832d57611033.mspx?mfr=true) (in inglese) sul sito Web Microsoft TechNet all'indirizzo http://technet2.microsoft.com/WindowsServer/en/library/be5c1c37-109e-49bc-943e-6595832d57611033.mspx?mfr=true.

###### Componenti server del servizio quarantena VPN

Il server di accesso remoto VPN è la parte centrale di questa soluzione con le funzioni seguenti:

-   Esegue il Servizio quarantena accesso remoto (RQS.exe).

-   Applica i criteri di accesso remoto per le impostazioni di accesso alla quarantena.

-   Negozia le comunicazioni con l'agente client.

-   Riceve le informazioni sulla conformità dei criteri dall'agente client.

-   Applica i criteri di accesso remoto per determinare le autorizzazioni di accesso alle risorse di rete.

Il Servizio quarantena accesso remoto è un componente facoltativo di Windows Server 2003 con Service Pack 1 e supporta le API necessarie per mettere in quarantena i computer client remoti e rimuoverli da questo stato dopo che l'agente client invia la notifica della conformità ai criteri. Questo servizio (RQS.exe) attende sulla porta TCP 7250 la notifica da parte del componente del lato client (RQC.exe) in cui viene comunicato che il computer client soddisfa i requisiti sui criteri. Questa capacità implica che affinché questa soluzione possa funzionare, qualsiasi firewall, inclusi i firewall host, devono consentire il traffico sulla porta TCP 7250.

###### Componenti di rete del servizio quarantena VPN

L'elenco dei componenti di rete seguente include sia i componenti obbligatori che quelli facoltativi. Questi sono i componenti che possono far parte di una soluzione di rete per il servizio di quarantena VPN.

-   **Server RADIUS per il Servizio autenticazione Internet (IAS, Internet Authentication Service) (consigliato)**. Sebbene i server IAS siano necessari solo se si utilizza il servizio RADIUS come provider di autenticazione, presentano alcuni vantaggi significativi rispetto ad altre soluzioni di autenticazione, inclusi il supporto EAP (Extensible Authentication Protocol) per l'autenticazione a due fattori basata sui certificati e sulle smart card. Se si adotta il metodo RADIUS, si consiglia di utilizzare il servizio IAS fornito con Windows Server 2003 in qualità di provider RADIUS, poiché sopporta gli attributi VSA MS-Quarantine Session Timeout e MS-Quarantine-IPFilter. Altri server RADIUS potrebbero non fornire questo supporto.

-   **Active Directory (consigliato)**. Active Directory funziona come database di autenticazione degli account utente e si integra con IAS e altri servizi. Se utilizzato insieme al servizio IAS, è in grado di supportare l'autenticazione a due fattori con certificati o altri metodi.

-   **Server DHCP (consigliato)**. I server DHCP vengono utilizzati per il provisioning degli indirizzi IP ai clienti remoti.

-   **Server DNS (consigliato)**. Un server DNS fornisce i servizi per la risoluzione dei nomi per consentire ai client della rete in quarantena di connettersi agli altri server (se disponibili) in modo da poter aggiornare allo stato di conformità i computer client remoti.

-   **Server WSUS (Windows Software Update Service) (facoltativo)**. I server WSUS sono in grado di fornire gli aggiornamenti della protezione e le correzioni rapide di cui hanno bisogno i computer remoti per soddisfare i requisiti che li consente di uscire dallo stato di quarantena. È possibile utilizzare anche altri metodi, inclusi SMS 2003 o perfino i servizi Windows Update standard, qualora sia necessario reindirizzare i computer verso origini esterne per gli aggiornamenti.

-   **File server (facoltativo)**. I file server possono essere utilizzati per fornire le condivisioni ai computer in quarantena che devono accedere agli aggiornamenti software e ai file della firma antivirus per soddisfare i requisiti dei criteri.

-   **Server Web (facoltativo)**. È possibile utilizzare i server Web nello stato di quarantena per fornire agli utenti le istruzioni per rimuovere i loro computer dallo stato di quarantena. Alcuni pacchetti di aggiornamento utilizzano anche i componenti Web per la consegna come, ad esempio, alcuni prodotti antivirus.

##### Utilizzo dell'autenticazione 802,1X per proteggere il sistema contro i client wireless non gestiti

Nella sezione precedente è stata introdotta l'autenticazione 802.1X come l'opzione più efficiente per proteggere le reti wireless dai computer untrusted. Sono stati descritti i diversi metodi 802.1X supportati in modo nativo nelle versioni correnti di Microsoft Windows ed è stato spiegato il motivo per cui l'autenticazione 802.1X non è poi così efficiente per le reti cablate, al contrario delle reti wireless. Con queste informazioni, è possibile esaminare le differenze tra i metodi supportati e determinare quale potrebbe essere il più adatto per i tipi diversi di ambienti di rete delle aziende di medie dimensioni.

###### Confronti 802.1X

Come discusso in precedenza, nelle versioni correnti di Microsoft Windows sono supportati tre metodi 802.1X. Tali metodi sono:

-   EAP-MD5

-   PEAP (EAP Protected)

-   EAP-TLS

Di questi tre metodi, il primo (EAP-MD5) è considerato il meno sicuro poiché prevede la trasmissione delle passphrase, che potrebbero essere intercettate. Al contrario, è opportuno prendere in considerazione le altre due opzioni (PEAP e EAP-TLS) per la distribuzione nelle reti delle aziende di medie dimensioni.

L'implementazione Microsoft del metodo PEAP utilizza Microsoft Challenge Handshake Authentication Protocol versione 2 (MS-CHAP v2). Questo protocollo è stato originariamente sviluppato come metodo di autenticazione VPN di connessione remota, ma è comunque indicato anche per il metodo PEAP poiché è in grado di supportare i criteri per le password utente avanzate tramite Active Directory. Questo approccio di implementazione è più semplice del metodo EAP-TLS e più economico in termini di risorse e costi iniziali, poiché non prevede un numero elevato di server e servizi aggiuntivi per l'implementazione. Sebbene questa soluzione richieda i certificati per i server di autenticazione, a causa del numero esiguo di certificati richiesti per l'implementazione è possibile fare in modo che siano i provider di certificati di terzi a generali.

Tuttavia, EAP-TLS è considerato il metodo di implementazione di autenticazione 802.1X più sicuro disponibile, poiché per l'autenticazione reciproca richiede i certificati sia sul client che sul server di autenticazione. Poiché l'implementazione di questo tipo di soluzione richiede un numero elevato di certificati, si consiglia di utilizzare un'infrastruttura basata sulle chiavi pubbliche. Di conseguenza, l'approccio EAP-TLS è quello con i costi di implementazione e supporto più elevati se confrontato con il metodo PEAP con MS-CHAP v2.

###### Processo decisionale 802.1X

Per semplificare il processo decisionale per la scelta di quale metodo di implementazione è da preferire per un determinato ambiente di rete, Microsoft ha sviluppato la struttura decisionale di autenticazione 802.1X seguente.

![](images/Cc875843.PNFUC09(it-it,TechNet.10).gif)

**Figura 9. Struttura decisionale 802.1X**

Il termine "azienda di grandi dimensioni" nel diagramma può creare confusione. Questo termine fa riferimento, generalmente, a qualsiasi azienda con almeno 500 dipendenti e un team IT di supporto di almeno 5 tecnici professionisti. In base a queste informazioni, è chiaro che le soluzioni indicate nel diagramma sono più adatte per gli ambienti delle aziende di medie dimensioni. Pertanto, il processo decisionale si evolve basandosi più che altro sulla possibilità di rischio e sul fattore economico.

La differenza principale tra i metodi PEAP ed EAP-TLS comporta la necessità di un'infrastruttura per certificati e questo è il motivo per cui, se non esistono requisiti particolari che richiedano standard di protezione più rigorosi, solitamente il metodo EAP-TLS è considerato come l'opzione più adatta per le aziende di grandi dimensioni, mentre il metodo PEAP per quelle più piccole. Oltre alle considerazioni sui costi, a volte le organizzazioni hanno anche la necessità di un'infrastruttura per certificati e ciò rappresenta un motivo in più per considerare un investimento nella PKI. Dopo tutto, se per la firma del codice o del contenuto Web protetto sono richiesti molti certificati, è ragionevole utilizzare solo l'investimento in questa infrastruttura per implementare il modulo più sicuro di autenticazione 802.1X.

###### Requisiti PEAP 802.1X

Un'implementazione PEAP con MS-CHAP v2 di Microsoft richiede almeno due server RADIUS IAS che funzionino come server per autenticare i client wireless utilizzando un database di account di Active Directory. Il numero dei server RADIUS è variabile in base al numero dei siti remoti o alla necessità di gestire i tentativi di autenticazione degli utenti.

La presenza di ubicazioni remote non implica automaticamente la necessità di altri server RADIUS IAS. Di conseguenza, se le ubicazioni remote non hanno connessioni con larghezza di banda elevata ridondanti oppure dispongono già di propri controller di dominio e altre risorse locali, per questi siti sarà necessario aggiungere altri server di autenticazione.

###### Requisiti EAP-TLS 802.1X

Come descritto in precedenza, il metodo EAP-TLS richiede più risorse rispetto alle implementazioni PEAP a causa dei requisiti di certificati aggiuntivi. Ovviamente, è possibile utilizzare provider di terzi per inviare i certificati richiesti a tutti i server di autenticazione e client wireless. Tuttavia, questo approccio ha dei costi più elevati rispetto all'implementazione di un'infrastruttura di certificati, a meno che il numero di client wireless non sia limitato a un numero esiguo di utenti.

Nel complesso, una semplice implementazione EAP-TLS potrebbe richiedere almeno quattro server, mentre ne occorrono molti di più per le reti di aziende di grandi dimensioni o distribuite su aree geografiche. Due dei quattro server dovranno funzionare come server RADIUS IAS ridondanti, mentre gli altri due come infrastruttura per i certificati. Si consiglia di posizionare uno dei due server di certificati (il server dei certificati principale) all'esterno della rete e di non connetterlo alla rete. Ciò significa che, in determinate circostanze, il numero dei server può essere ridotto di uno.

###### Utilizzo della crittografia WEP o WPA

Un altro problema relativo alla protezione wireless che deve essere preso in considerazione è se utilizzare o meno la crittografia wireless e, nel caso, quale standard adottare. Per l'ambiente di un'azienda di medie dimensioni ci sono veramente pochi motivi per cui è necessario considerare la mancanza di crittografia wireless. Tali motivi sono da associare alle aziende che forniscono connessioni Internet wireless con accesso pubblico. In caso contrario, per assicurare la protezione di una rete wireless è assolutamente necessario implementare una soluzione di crittografia wireless, insieme all'autenticazione 802.1X.

La crittografia wireless è disponibile in due formati principali, con un'ulteriore variante. I formati sono:

-   **WEP**. Lo standard WEP (Wired Equivalent Privacy) è stato parte dello standard IEEE 802.11 originale che utilizza la crittografia RC4 a 64 o 128 bit per proteggere le comunicazioni wireless. A causa di diverse imperfezioni che sono state rilevate nel tempo, questo metodo di crittografia è diventato estremamente vulnerabile agli attacchi alle porte in ascolto passive. Sono disponibili numerosi strumenti in grado di decodificare le trasmissioni WEP in breve tempo, a volte in pochi minuti. Solitamente, l'uso della crittografia WEP non è consigliato per gli ambienti di rete. Tuttavia, è possibile aumentarne la protezione utilizzando vari altri metodi, inclusi l'autenticazione 802.1X.

-   **WPA**. In risposta alla vulnerabilità dello standard WEP, un consorzio di aziende leader del settore, a cui fanno parte anche Microsoft e Wi-Fi Institute, ha creato lo standard WPA (Wi-Fi Protected Access) come implementazione parziale dello standard 802.11i che era ancora in fase di sviluppo. Questo standard offre un livello di crittografia più potente che utilizza il protocollo TKIP (Temporal Key Integrity Protocol) per la crittografia dei dati, decisamente superiore allo standard WEP di bassa qualità. La maggior parte dei punti di accesso wireless (WAP) di oggi supporta lo standard WPA, come anche tutte le versioni correnti del sistema operativo Microsoft Windows.

-   **WPA2**. Lo standard WPA2 (Wireless Protected Access 2) è stato creato nel settembre 2004 da Wi-Fi Alliance. È certificato come implementazione completa della specifica IEEE 802.11i, ratificata nel giugno 2004. Questo standard supporta i metodi di autenticazione EAP 802.1X o la tecnologia PSK (a cui, a volte, si fa riferimento con VPA in modalità Personal) e introduce un meccanismo di crittografia avanzato AES (Advanced Encryption Standard), che utilizza il protocollo CCMP (Counter-Mode/CBC-MAC Protocol). Questa implementazione della crittografia wireless è estremamente sicura. La maggior parte dei fornitori supporta lo standard WPA2, incluse le versioni correnti del sistema operativo Microsoft Windows.

Se possibile, è opportuno utilizzare lo standard WPA2 o WPA per proteggere i dati nelle comunicazioni wireless. Tuttavia, a causa del fatto che questi standard sono stati introdotti solo di recente sul mercato, potrebbe non essere possibile utilizzarli, specialmente qualora sia stato già fatto un investimento significativo in tecnologia wireless che non supporta questi standard. Come descritto in precedenza, è possibile aumentare il livello di protezione fornito dallo standard WEP configurando l'autenticazione 802.1X e modifiche frequenti alla coppia di chiavi. Anche in questo caso, tuttavia, l'uso dello standard WEP dovrebbe essere riservato alle reti wireless che si trovano in uno stato di transizione allo standard WPA o WPA 2.

##### Utilizzo di SMS per rilevare i sistemi non gestiti

Microsoft Systems Management Server (SMS) 2003 è uno strumento di gestione molto versatile in una rete Microsoft. Con SMS è possibile centralizzare diverse funzioni di gestione, inclusi la consegna del software, la distribuzione degli aggiornamenti della protezione e il controllo dei sistemi. Ciò consente di ottenere un inventario dei sistemi automatizzato e centralizzato con il quale implementare tali strumenti di indiscutibile utilità. Questo è il punto in cui ha luogo il rilevamento dei sistemi non gestiti.

SMS 2003 offre diversi metodi di individuazione che gli amministratori possono utilizzare per creare il database di raccolta computer, che contiene le informazioni su ogni computer della rete. Questi metodi di individuazione vanno dal metodo basato su Active Directory (che aggiorna la raccolta con i dettagli forniti dall'elenco degli account dei computer Active Directory) al metodo Network Discovery (che esamina in modo attivo la rete alla ricerca delle periferiche connesse). Questi metodi di individuazione possono essere configurati in modo che vengano eseguiti a intervalli di tempo predefiniti in modo da aggiornare i database delle raccolte.

Affinché sia possibile individuare i sistemi non gestiti quando sono connessi alla rete, è possibile configurare il metodo Network Discovery in modo che venga eseguito più frequentemente e quindi esaminare i risultati della ricerca a intervalli regolari per determinare se un nuovo sistema si sia connesso alla rete. Quando vengono stabilite connessioni di sistema di questo tipo, è possibile metterle a confronto con qualsiasi elenco di nuovi computer o di richieste di connessione alla rete per confermare se il nuovo sistema è autorizzato a utilizzare la rete.

###### Processo Network Discovery

Uno degli inconvenienti di questo approccio di individuazione dei sistemi non gestiti è che il server SMS potrebbe avere difficoltà a individuare i dettagli dei computer che utilizzano sistemi operativi diversi da Microsoft Windows. Infatti, perfino le versioni precedenti a Microsoft Windows 98 SE potrebbero non essere rilevate dai metodi di individuazione di SMS 2003, poiché non supportano le implementazioni WMI (Windows Management Interface). Di conseguenza, è necessario aggiungere script a questo processo di soluzione in modo che qualsiasi nuova periferica venga individuata non appena viene collegata alla rete. Nella figura seguente viene illustrato il modo in cui dovrebbe funzionare un processo di questo tipo.

![](images/Cc875843.PNFUC10(it-it,TechNet.10).gif)

**Figura 10. Processo di individuazione dei computer non gestiti SMS**

La figura mostra i metodi di individuazione che possono essere utilizzati per aggiungere tipi diversi di computer nel database di raccolta SMS. Esistono tre tipi diversi di computer:

-   **Sistemi gestiti a cui può accedere SMS**. Questi computer possono essere gestiti da SMS e sono già sotto il controllo da parte di SMS. Sono presenti nel database di raccolta SMS e devono essere configurati per la gestione automatica. Possono essere considerati parte della rete trusted e non richiedono ulteriori attenzione.

-   **Sistemi non gestiti a cui può accedere SMS**. Questi computer possono essere gestiti da SMS ma non sono sotto il controllo da parte di SMS. Possono o meno essere rilevati da SMS, a seconda della loro posizione nella rete (ad esempio, dietro o davanti i firewall). Questa categoria include i computer che sono gestiti tramite altri metodi. Questi computer devono essere presenti in un elenco di esenzioni, completo dei dettagli sulla gestione. Se non lo sono, devono essere considerati sistemi untrusted e potrebbero essere sottoposti a un'analisi più approfondita. Tali sistemi possono essere individuati da SMS, ad eccezione delle periferiche di rete che bloccano questo tipo di attività.

-   **Sistemi non gestiti a cui non può accedere SMS**. Questi computer non possono essere gestiti da SMS e non sono sotto il controllo di SMS. In questa categoria possono essere inclusi i sistemi conosciuti che sono gestiti tramite altri metodi. Questi computer devono essere presenti in un elenco di esenzioni, completo dei dettagli sulla gestione. Se non lo sono, devono essere considerati sistemi sconosciuti e untrusted e devono essere sottoposti a un'analisi più approfondita. Questi computer possono essere solo rilevati utilizzando processi diversi dalla funzione di individuazione di SMS, inclusi gli script di individuazione personalizzati.

A questo punto dovrebbe essere chiaro che il processo di individuazione dei sistemi non gestiti nella rete dipende dalla creazione di processi in grado di documentare i dettagli di ogni connessione di computer autorizzato che ha luogo nella rete. Tale documentazione deve includere i dettagli sul computer, se il computer è gestito tramite metodi automatizzati (quale, il metodo SMS) e, in caso contrario, quale processo viene utilizzato per tenere il computer conforme con i criteri di protezione stabiliti. Ovviamente, nella rete possono essere presenti computer autorizzati che non soddisfano gli standard di protezione. Tuttavia, questi computer devono essere forzati a rimanere nel perimetro di una rete untrusted che sia isolata dalla rete trusted.

Quando viene creato un documento di tipo "aggiunta computer" che indica che tutti i computer noti nella rete devono essere autorizzati, è possibile utilizzare queste informazioni per determinare quale computer è effettivamente autorizzato e quale no. Qualsiasi computer individuato nella rete che non è presente nell'elenco deve essere considerato sospetto e pertanto sottoposto immediatamente a un'ulteriore analisi.

#### Distribuzione e gestione

Nella sezione "Sviluppo" sono state fornite informazioni su quali dettagli sono necessari per creare i piani per la distribuzione. In questa sezione vengono descritti alcuni dei problemi correlati alla distribuzione e i processi che possono aiutare i responsabili dell'implementazione della tecnologia quando implementano le soluzioni oppure i decisori a capire meglio il comportamento di queste soluzioni in modo che possano avere idee più chiare su cosa sia appropriato per un determinato ambiente.

##### Utilizzo dell'IPsec per isolare i domini e i server

A causa della complessità associata all'isolamento di una rete IPsec, per la distribuzione della soluzione in una rete di produzione i responsabili dell'implementazione dovrebbero seguire un approccio in diverse fasi. Sono disponibili due metodi per effettuare la distribuzione in diverse fasi. Tali metodi si basano sul modo in cui vengono distribuiti i criteri IPsec: per gruppi o per criterio.

Indipendentemente dal metodo utilizzato, è importante utilizzare modelli di esempio di ciascun gruppo durante le fasi iniziali della distribuzione, oltre a valutare l'impatto della soluzione in un ambiente di test, se possibile. La distruzione del protocollo IPsec dovrebbe seguire un processo formale di richiesta di controllo delle modifiche che dettagli i piani di ripristino e le conferme da parte dei proprietari della tecnologia e dei processi aziendali.

###### Distribuzione del protocollo IPsec in base ai gruppi

Il metodo di distribuzione dell'isolamento di una rete IPsec in base ai gruppi utilizza i criteri IPsec completamente definiti ma controlla l'implementazione utilizzando gli ACL negli oggetti Criteri di gruppo che consegnano i criteri. Tutti i criteri IPsec avranno le esenzioni e le subnet di protezione completamente definite con le azioni filtro appropriate abilitate prima della distribuzione.

Quando la configurazione è completa, gli amministratori creano gli oggetti Criteri di gruppo per ciascun gruppo di criteri e di computer IPSec per gestire tali oggetti. Una volta creati, i criteri IPsec appropriati vengono assegnati all'oggetto Criteri di gruppo corrispondente. Gli oggetti Criteri di gruppo vengono collegati agli oggetti appropriati in Active Directory. A questo punto del processo non deve essere consegnato alcun criterio, poiché gli ACL che controllano le assegnazioni degli oggetti Criteri di gruppo sono vuoti.

Quando i computer pilota vengono identificati, è possibile inserire gli account dei computer corrispondenti nei gruppi di computer appropriati. In questo modo, il criterio IPsec verrà applicato una volta trascorso il successivo intervallo di polling dell'oggetto Criteri di gruppo. Man mano che vengono aggiunti altri computer all'elenco di distribuzione, è possibile inserire gli account corrispondenti nei gruppi appropriati per la consegna dei criteri.

Questo metodo richiede un'attenta pianificazione che assicuri che non vengano compromesse le comunicazioni. Ad esempio, se un server su cui è installata un'applicazione utilizzata da tutti gli host è stato inserito in un gruppo protetto che richiede comunicazioni crittografate con il metodo IPsec, le comunicazioni non saranno possibili per i computer che non sono stati ancora aggiunti ai gruppi e qualsiasi host che non è in grado di utilizzare la crittografia IPsec.

###### Distribuzione del protocollo IPsec in base ai criteri

L'approccio di questo metodo consiste nel creare criteri IPsec da zero durante la distribuzione e non prima della distribuzione in produzione effettiva. Quando si utilizza questo metodo, i criteri IPsec iniziali includono solo gli elenchi di eccezione senza regole impostate per i computer ai fini della negoziazione della protezione. Quando il criterio iniziale viene consegnato, gli amministratori possono creare una regola di protezione con un filtro che interessa solo una singola subnet. Man mano che il processo di distribuzione avanza, è possibile aggiungere altre subnet alla regola di protezione fin quando il criterio raggiunge la fine dello stato di distribuzione.

L'uso del metodo di distribuzione in fasi diverse ha il vantaggio che il protocollo IPsec viene negoziato solo per una piccola percentuale del traffico totale TCP/IP invece che per tutte le subnet, come nel caso dell'approccio di tipo gruppo per gruppo. Inoltre, questo metodo consente di testare tutti i percorsi di rete da una singola subnet, riducendo il numero di client che possono rimanere interessati da qualsiasi problema che si può verificare. Di conseguenza, il problema con questo approccio consiste nel fatto che viene applicato a tutti i computer del dominio o del gruppo di isolamento e non a computer specifici come nel caso dell'approccio gruppo per gruppo. Inoltre, tutti i computer dovranno gestire il ritardo di tre secondi per l'azione di "fallback in comunicazioni di testo in chiaro" in un punto del processo, quando vengono avviate le connessioni alle subnet specificate.

Questo approccio è indicato per le reti complesse con più subnet, ma non lo è per le reti di piccole dimensioni con un numero di subnet veramente esiguo.

###### Elenchi di esenzioni

Anche il miglior progetto di modello di isolamento della rete potrà incontrare alcuni vincoli quando viene implementato in un ambiente di produzione. Solitamente, i componenti principali di un ambiente di rete, quali i server DNS e i controller di dominio, presentano alcune problematiche che devono essere risolte. Questi sistemi devono essere messi sotto protezione ma devono anche essere resi disponibili per tutti i sistemi di una rete. Pertanto, devono lasciar passare le richieste di connessione in entrata. Altri problemi si possono manifestare quando il piano viene convertito in produzione. Tuttavia, esiste un metodo per risolvere questo tipo di problemi: gli elenchi di esenzioni.

Un elenco di esenzioni è un elenco di computer che non possono essere protetti tramite il metodo IPsec e dovranno essere implementati in ogni criterio IPsec definito. Poiché il metodo IPsec supporta solo il filtraggio statico, qualsiasi host aggiunto all'elenco di esenzioni consentirà il traffico sia in entrata che in uscita da tutte le parti della rete, trusted o untrusted. Per tale motivo, l'elenco di esenzioni dovrebbe contenere sempre il minor numero possibile di voci, poiché gli host che vi sono riportati avranno bisogno di ulteriore protezione tramite apposite misure sia di tipo hardware per i server che di tipo filtro stato firewall basato su host per limitare il rischio delle azioni dannose che possono derivare dalle periferiche non gestite. Può risultare utile posizionare gli host presenti nell'elenco di esenzioni in una singola subnet o VLAN per una gestione più semplice oppure consolidare le funzioni del server per ridurre il numero di host nell'elenco di esenzioni.

Alcuni degli host che potrebbe essere necessario aggiungere a un elenco di esenzioni includono:

-   Controller di dominio che non supportano le comunicazioni IPsec con i membri del dominio anche se forniscono i criteri IPsec ai membri del dominio ed eseguono l'autenticazione Kerberos su cui è basato l'isolamento della rete.

-   Host in cui le prestazioni scendono a un livello non accettabile. Le prestazioni possono diventare un serio problema negli host che devono gestire migliaia di client contemporaneamente e negli host in cui si ha un ritardo di tre secondi per l'azione di "fallback in comunicazioni di testo in chiaro", come nel caso dei server DHCP.

-   Host la cui implementazione IPsec non è conforme agli standard oppure che forniscono servizi a computer trusted e untrusted, senza utilizzare il metodo IPsec.

Come per i gruppi di confine, è necessario un processo di approvazione formale per gli host che devono essere inseriti negli elenchi di esenzioni.

**Nota**   È stata rilasciata la correzione rapida “Simple Policy” per Microsoft Windows XP e Windows Server 2003 che rende non più necessari gli elenchi di esenzioni. Per ulteriori informazioni vedere gli articoli della Knowledge Base n. [914841](http://support.microsoft.com/?kbid=914841) all'indirizzo http://support.microsoft.com/?kbid=914841 e n. all'indirizzo http://support.microsoft.com/?kbid=914842.

###### Considerazioni sulla gestione IPsec

Una volta implementati, i criteri IPsec influenzano le comunicazioni tra molti host nella rete. Pertanto, le modifiche che vengono apportate dopo l'implementazione potrebbero avere un impatto non indifferente su molti utenti. A causa di questo motivo, tutte le modifiche apportate a una rete di isolamento IPsec devono basarsi su un processo di gestione delle modifiche MOF standardizzato che include:

-   Richiesta di modifica (RFC)

-   Classificazione della modifica

-   Autorizzazione della modifica

-   Piano di sviluppo della modifica

-   Piano di rilascio della modifica

-   Revisione della modifica

Microsoft consiglia l'uso di Windows Server 2003 come piattaforma per la gestione IPsec. Per facilitare le attività di gestione, gli amministratori possono utilizzare lo snap-in Gestione criteri di protezione IP oppure il comando Netsh alla riga di comando alla console di Windows Server 2003. In caso contrario, la gestione dei criteri IPsec può diventare un impegno non trascurabile poiché vengono consegnati tramite Criteri di gruppo. Tuttavia, è possibile automatizzare l'aggiunta di nuovi computer alla rete trusted se viene creato e utilizzato un processo di tipo "aggiunta computer".

Tuttavia, è necessario considerare alcuni fattori quando è necessario apportare modifiche, tra cui:

-   Qualsiasi modifica in un'azione di tipo filtro utilizzata per una SA IPsec, comporterà l'eliminazione delle SA create sotto tali impostazioni dei criteri. Questa funzionalità crea un nuovo tentativo di modalità rapida se il traffico viene instradato e ciò può determinare la perdita del traffico di rete.

-   La modifica del metodo di autenticazione oppure del metodo di protezione della modalità principale, comporta l'eliminazione delle modalità principali esistenti da parte di IKE. In alcune circostanze, questa funzionalità potrebbe far fallire le negoziazioni in modalità principale IKE sul lato server con i client.

-   Quando si modificano i criteri IPsec in un oggetto Criteri di gruppo, è possibile incorrere in un periodo di ritardo (incluso il ritardo della replica Active Directory e il ritardo del polling oggetti Criteri di gruppo) della durata compresa tra minuti e ore, in base alle dimensioni e alla complessità dell'ambiente.

Un'altra considerazione sulla gestione riguarda il modo in cui isolare i computer sospetti quando il sistema è stato attaccato da un'infezione. Esistono diversi modi per gestire le attività dannose, tra cui:

-   **Isolamento del dominio di isolamento**. Modificando il filtro IPsec - Modalità richiesta protetta per disabilitare le comunicazioni non protette, la rete isolata può essere completamente separata dalla rete untrusted, qualora si sospetti che una periferica untrusted sia diventata una piattaforma per le attività dannose.

-   **Blocco delle porte sospette**. La creazione di elenchi filtro con due filtri unidirezionali consente di bloccare il traffico in base alle porte. Questo approccio deve essere utilizzato con attenzione, poiché si potrebbe bloccare il traffico necessario, quale i dati DNS. Ciò potrebbe comportare ulteriori modifiche all'IPsec o difficoltà di ripristino dello stato precedente.

-   **Isolamento dei domini secondari**. Modificando i criteri per un dominio in modo da utilizzare una chiave precondivisa piuttosto che il protocollo Kerberos per l'autenticazione IPsec, è possibile isolare un dominio dagli altri in una foresta.

-   **Isolamento dei gruppi predefiniti**. Utilizzando le chiavi precondivise o i certificati per l'autenticazione IPsec invece del protocollo Kerberos, è possibile creare gruppi di isolamento che utilizzano chiavi o certificati diversi che consentono di eseguire lo stesso tipo di funzionalità di isolamento.

##### Utilizzo dei servizi di quarantena VPN per proteggere il sistema dai computer remoti non gestiti

La distribuzione effettiva del controllo quarantena VPN richiede solitamente sei passaggi prima di qualsiasi altro processo di richiesta di gestione delle modifiche e altri processi di testo di pre-distribuzione previsti per una determinata organizzazione. I sei passaggi includono:

1.  Creazione delle risorse in quarantena.

2.  Creazione di script per convalidare le configurazioni client.

3.  Installazione del componente listener RQS.exe sui server di accesso remoto.

4.  Creazione di profili CM (Connection Manager) per i servizi di quarantena con Windows Server 2003 CMAK.

5.  Distribuzione dei profili CM ai computer client di accesso remoto.

6.  Configurazione dei criteri di accesso remoto in quarantena.

###### 1. Creazione delle risorse in quarantena

Se i client in quarantena devono utilizzare risorse interne per poter ottenere la conformità ai criteri di protezione stabiliti, sarà necessario impostare un gruppo di risorse accessibili di cui i client possono avvalersi per installare gli aggiornamenti di requisito e altro software necessario per garantire la loro protezione. Come spiegato nella sezione precedente, queste risorse generalmente includono un server dei nomi, alcuni file server e a volte anche alcuni server Web. Per definire le risorse in quarantena, inclusi la definizione dei server esistenti che risiedono nella rete interna e l'inserimento delle risorse richieste in una propria subnet separata, è possibile utilizzare due approcci diversi.

Il primo approccio relativo alla definizione dei singoli server può ridurre i costi associati all'aggiunta di tali server per la consegna degli aggiornamenti, poiché verranno utilizzati i server esistenti. Tuttavia, questo approccio richiede filtri pacchetto complessi nell'attributo MS-Quarantine-IPFilter del criterio di accesso remoto in quarantena.

Per l'inserimento delle risorse in quarantena in una singola subnet destinata ai servizi di quarantena potrebbe essere necessario aggiungere altri server all'ambiente di rete. Tuttavia, è richiesto un solo pacchetto filtro di input e di output per tutte le risorse in quarantena.

###### 2. Creazione di script di convalida

Gli script per i servizi di quarantena eseguono una serie di test che assicurano la conformità dei computer di accesso remoto ai criteri di protezione. Quanto i test vengono completati, lo script deve avviare il componente client RQC.exe (se il test è stato superato) oppure indirizzare il computer client alle risorse appropriate che gli consenta di ottenere la conformità. Naturalmente, lo script potrebbe anche semplicemente applicare un periodo di timeout di rete con un messaggio di errore se i criteri della rete specificano l'uso di questo approccio. Questi script possono essere costituiti semplicemente da un file batch con esecuzione dalla riga di comando oppure da una serie di file eseguibili complessi.

È possibile esaminare e scaricare alcuni script di esempio disponibili alla pagina* *[VPN Quarantine Sample Scripts](http://www.microsoft.com/downloads/details.aspx?familyid=a290f2ee-0b55-491e-bc4c-8161671b2462&displaylang=en) (in inglese) sul sito Web Area download Microsoft all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyID=a290f2ee-0b55-491e-bc4c-8161671b2462&displaylang=en.

###### 3. Installazione del componente RQS.exe sui server di accesso remoto

Il processo di installazione del Servizio quarantena accesso remoto (RQS.exe) su un computer Microsoft Windows Server 2003 è differente da quella dei server sui quali è presente il Service Pack 1 (SP1). In questa sezione viene descritta solo l'installazione su Windows Server 2003 con SP1, poiché si presuppone che tutti i sistemi siano aggiornati con i service pack e gli aggiornamenti della protezione più recenti.

**Per installare RQS.exe su un server Windows Server 2003 con SP1**

1.  Fare clic su **Start** e scegliere **Pannello di controllo**.

2.  Fare clic su **Installazione applicazioni**.

3.  Fare clic su **Installazione componenti di Windows**.

4.  Selezionare **Componenti** e quindi **Servizi di rete**.

5.  Fare clic su **Dettagli**.

6.  Selezionare **Sottocomponenti di Servizi di rete**, fare clic su **Servizio quarantena accesso remoto** e quindi su **OK**.

Questo processo installa ma non avvia il servizio di quarantena, che deve essere avviato manualmente da un amministratore una volta che la soluzione è stata completamente configurata e l'ambiente è stato preparato per l'implementazione.

Un ulteriore passaggio nel processo di installazione include la modifica delle stringhe delle versioni degli script, in modo che possano corrispondere alla stringa della versione configurata per il componente RQC.exe nello script del servizio di quarantena. È possibile configurare il componente RQS.exe in modo che possa accettare più stringhe di versioni di script che, a loro volta, vengono scritte nel Registro di sistema del server di accesso remoto nella chiave **HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\rqs\\AllowedSet**. Questo è il punto in cui tali impostazioni devono essere applicate tramite il tipo valore REG\_MULTI\_SZ. Solitamente, il valore **AllowedSet** è impostato su **RASQuarantineConfigPassed**, ma è possibile aggiungere altri valori di stringa.

###### 4. Creazione di profili CM per il servizio di quarantena

Il profilo CM per il servizio di quarantena è semplicemente un tipico profilo CM di accesso remoto con le seguenti aggiunte:

-   Un'azione di post-connessione che esegue lo script creato per verificare la conformità dei criteri della rete e lo script stesso. Questa operazione viene eseguita nella pagina Operazioni personalizzate della procedura guidata CMAK.

-   È necessario aggiungere al profilo anche un componente di notifica tramite la schermata **File aggiuntivi** della procedura guidata CMAK.

###### 5. Distribuzione dei profili CM

I profili CM per i servizi in quarantena creati devono essere distribuiti e installati su tutti i computer client di accesso remoto. Un profilo è un file eseguibile che deve essere eseguito su ciascun computer client di accesso remoto in modo che venga installato e venga quindi configurata la connessione alla rete del servizio di quarantena.

È possibile distribuire questi profili tramite un processo manuale. Ad esempio, un processo che invii agli utenti i profili come allegati insieme alle istruzioni. È anche possibile utilizzare processi automatizzati, tramite strumenti quali la distribuzione del software di SMS 2003. Sono disponibili diversi metodi di distribuzione e per ogni ambiente è previsto un approccio diverso.

###### 6. Configurazione dei criteri di accesso remoto in quarantena

La procedura per configurare un criterio di accesso remoto in quarantena cambia a seconda del fatto che il criterio venga configurato su un server IAS oppure presso un altro provider di autenticazione, come descritto di seguito:

-   Se la configurazione viene eseguita su un server RADIUS IAS, utilizzare lo snap-in Servizio di Autenticazione Internet.

-   Se la configurazione viene eseguita presso un provider di autenticazione Windows, utilizzare lo snap-in Routing e Accesso remoto.

Quando si crea un criterio, è necessario definire prima un criterio di accesso remoto nel normale modo. Quindi, aggiungere gli attributi MS-Quarantine-Session-Timeout e MS-Quarantine-IPFilter utilizzando la scheda **Avanzate** delle proprietà del profilo dei criteri di accesso remoto.

Se si utilizza il metodo RADIUS, il criterio di accesso remoto in quarantena dovrà essere replicato sugli altri server RADIUS, copiando la configurazione oppure creando il criterio manualmente su ciascun server.

##### Utilizzo dell'autenticazione 802,1X per proteggere il sistema contro i client wireless non gestiti

Come descritto nelle sezioni precedenti, le opzioni di protezione consigliate da Microsoft per la rete wireless di un'azienda di medie dimensioni sono, , a partire dalla più sicura:

-   WPA2/AES e EAP-TLS

-   WPA2/AES e PEAP-MS-CHAP v2

-   WPA/TKIP e EAP-TLS

-   WPA/TKIP e PEAP-MS-CHAP v2

Sebbene le opzioni EAP-TLS o PEAP-MS-CHAP v2 siano in grado di rendere la crittografia WEP più sicura, l'uso del metodo WEP come parte di una soluzione è consigliato solamente durante una transizione verso gli standard più affidabili WPA o WPA2.

I processi di implementazione EAP-TLS e PEAP-MS-CHAP v2 presentano alcune similarità. Entrambi richiedono l'uso di server Microsoft RADIUS IAS come parte della soluzione e certificati con lo stesso formato. Tuttavia, per il processo EAP-TLS i certificati sono richiesti sia sul computer client che sul server, mentre per il processo PEAP-MS-CHAP v2 sono necessari solo i certificati per i server di autenticazione. Questo è il motivo per cui si consiglia vivamente un'infrastruttura per i certificati quando si implementa il metodo EAP-TLS, poiché i costi per l'acquisto di certificati da provider terzi per tutti i client di una rete potrebbero essere proibitivi.

###### Autenticazione wireless con EAP-TLS e PEAP-MS-CHAP v2

I processi di implementazione dei metodi EAP-TLS e PEAP-MS-CHAP v2 richiedono un numero di dettagli che non sono oggetto di questo documento. Tuttavia, esistono già diverse fonti autorevoli che possono facilitare la progettazione e l'implementazione di soluzioni per la protezione delle reti wireless. Tali fonti sono:

-   [Deployment of Secure 802.11 Networks Using Microsoft Windows](http://technet.microsoft.com/en-us/library/bb457068.aspx) (in inglese). Questo documento pubblicato sul sito Web Microsoft TechNet fornisce informazioni sull'implementazione di entrambi gli approcci di autenticazione IEEE 802.1X ed è disponibile all'indirizzo http://technet.microsoft.com/en-us/library/bb457068.aspx.

-   [The Securing Wireless LANs with Certificate Services](http://go.microsoft.com/fwlink/?linkid=14844) (in inglese). È possibile scaricare questo documento all'indirizzo http://go.Microsoft.com/fwlink/?LinkId=14844. Fornisce risorse e informazioni dettagliate sull'implementazione EAP-TLS nelle reti Microsoft.

-   [The Securing Wireless LANs with PEAP and Passwords](http://go.microsoft.com/fwlink/?linkid=23481) (in inglese). È possibile scaricare questo documento all'indirizzo http://go.Microsoft.com/fwlink/?LinkId=23481. Fornisce informazioni dettagliate sull'implementazione PEAP-MS-CHAP v2 nelle reti Microsoft.

-   [The Wi-Fi Protected Access 2 (WPA2)/Wireless Provisioning Services Information Element (WPS IE) update for Windows XP with SP2](http://support.microsoft.com/default.aspx?scid=kb;en-us;893357) (in inglese). Questo documento, disponibile all'indirizzo http://support.microsoft.com/default.aspx?scid=kb;en-us;893357, è richiesto per il supporto dello standard WPA2 nelle piattaforme Microsoft Windows XP con SP2.

##### Utilizzo di SMS per rilevare e aggiornare i sistemi non gestiti

Come descritto nella sezione "Sviluppo", il processo di individuazione SMS è molto utile per la ricerca dei nuovi computer connessi alla rete quando possono essere gestiti dal server SMS. Inoltre, è stato anche spiegato che, durante il processo di individuazione, il server SMS potrebbe non essere in grado di identificare alcuni sistemi non gestibili e che per risolvere questo problema è necessario utilizzare un altro meccanismo.

Possono esserci diversi motivi che non consentono al server SMS di individuare i computer collegati a una rete. I motivi includono:

-   Il computer è collegato, ma non è acceso al momento del processo di individuazione e non dispone di un account nel dominio.

-   Il computer è collegato a una subnet, ma un firewall oppure un'altra periferica di rete impedisce le comunicazioni tra il server SMS e la subnet.

-   Il computer è collegato a una rete accessibile, ma utilizza un sistema operativo che il server SMS non è in grado di identificare.

Per affrontare queste eventualità, è necessaria una soluzione personalizzata che combini le capacità di SMS con script in grado di sopperire alle eccezioni che SMS non è in grado di gestire. È possibile utilizzare script personalizzati per analizzare la rete a intervalli regolari con un processo di pianificazione. Tali script potrebbero, ad esempio, individuare le periferiche che sono attive solo per brevi periodi di tempo. Questi script possono essere eseguiti anche da workstation o server che risiedono in altre subnet isolate, in modo da rilevare i sistemi non gestiti che si connettono a tali segmenti di rete non monitorati. Inoltre, questi script non tentano di eseguire processi di individuazione basati su WMI e non sono pertanto influenzabili dal tipo di sistema operativo in uso sui client non gestiti.

Per ulteriori informazioni sull'uso del metodo SMS per individuare le periferiche nella rete, vedere il documento [Patch Management Using Systems Management Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=959ee7d6-7ddf-409a-9522-7d270bdcf12a&displaylang=en) (in inglese) all'indirizzo http://www.microsoft.com/downloads/details.aspx?familyid=E9EAB1BD-13E7-4E25-85C5-CE2D191C3D63&displaylang;=en oppure accedere alla home page [Microsoft Systems Management Server](http://www.microsoft.com/smserver/default.mspx) all'indirizzo www.microsoft.com/smserver/default.mspx per altri collegamenti, tra i quali collegamenti alle risorse relative alle soluzioni di script SMS.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

In questo documento è stato dimostrato che è possibile utilizzare un approccio completo per semplificare la gestione delle problematiche associate ai sistemi non gestiti. Il metodo di isolamento della rete tramite IPsec è stato utilizzato per impedire ai sistemi non gestiti di ottenere l'accesso alle risorse di rete trusted e assicurare la conformità, impedendo ai computer non conformi di utilizzare i servizi della rete. È possibile utilizzare i servizi di quarantena VPN per semplificare l'applicazione dei requisiti di conformità ai computer mobili che utilizzano una soluzione di accesso remoto, ma raramente si connettono alla rete locale. È possibile utilizzare i metodi IEEE 802.1X e WPA/WPA2 per difendere i sistemi dalle periferiche rogue nella LAN wireless. In ultimo, è possibile utilizzare il metodo SMS e gli script di rilevamento per l'identificazione dei sistemi non gestiti e per facilitare l'aggiornamento dei computer gestiti installando le patch e gli aggiornamenti della protezione più recenti.

Sebbene queste soluzioni tecniche possano aiutare a risolvere molti problemi correlati alle periferiche non gestite e rogue, le soluzioni risultano più efficaci se combinate insieme a criteri di protezione validi e a rigidi processi di gestione delle modifiche. Quando le soluzioni, i criteri e i processi vengono tutti combinati insieme, il risultato è un'infrastruttura per un'azienda di medie dimensioni gestibile che può ridurre a livelli accettabili i costi di amministrazione e i rischi correlati alla sicurezza.

[](#mainsection)[Inizio pagina](#mainsection)

### Appendice A: Protezione accesso alla rete

Protezione accesso alla rete è una nuova funzione disponibile nella prossima generazione dei sistemi operativi Windows (Microsoft Windows Server Longhorn e Windows Vista) che fornirà la capacità di applicare la conformità ai criteri di integrità dei computer. Gli amministratori possono utilizzare la funzione Protezione accesso alla rete per impostare le soglie dei criteri di convalida dell'integrità tramite un'API che limita l'accesso alla rete ai computer che non soddisfano i requisiti di integrità quando si connettono alla rete.

La flessibilità di questa funzione consente agli amministratori di configurare soluzioni personalizzate che possano soddisfare i requisiti dei loro ambienti. Ad esempio, registrando semplicemente lo stato di integrità dei computer che si collegano alla rete, distribuendo automaticamente gli aggiornamenti del software oppure limitando la connettività dei sistemi che non soddisfano i requisiti di integrità. La funzione Protezione accesso alla rete è, inoltre, integrabile con le applicazioni di terzi e le soluzioni basate su programmi personalizzati e ciò consente di poter applicare in modo globale i criteri di integrità dei computer. Protezione accesso alla rete è una funzione completa. I suoi componenti di applicazione dei criteri consentono agli amministratori di imporre la conformità ai criteri di integrità tramite le reti DHCP, VPN, e 802.1X ed è compatibile con IPsec.

Per ulteriori informazioni sulla funzione Protezione accesso alla rete, vedere il documento [Network Access Protection](http://www.microsoft.com/technet/itsolutions/network/nap/default.mspx) (in inglese) all'indirizzo www.microsoft.com/technet/itsolutions/network/nap/default.mspx.

**Download**

[Scarica il documento Protezione di una rete dai client non gestiti](http://go.microsoft.com/fwlink/?linkid=71713)

[](#mainsection)[Inizio pagina](#mainsection)
