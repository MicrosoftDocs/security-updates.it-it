---
TOCTitle: Scelta di una strategia per la protezione di reti LAN senza fili
Title: Scelta di una strategia per la protezione di reti LAN senza fili
ms:assetid: '75982e03-46ab-485d-aeee-9e59665dc57f'
ms:contentKeyID: 20200841
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536242(v=TechNet.10)'
---

Protezione delle reti LAN senza fili con PEAP e password
========================================================

### Introduzione: Scelta di una strategia per la protezione di reti LAN senza fili

Aggiornato: 3 aprile 2004

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Vantaggi delle reti senza fili](#eeaa)
[](#edaa)[Come proteggere (realmente) la rete WLAN](#edaa)
[](#ecaa)[Selezione delle opzioni appropriate per le reti LAN senza fili](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Riferimenti](#eaaa)

### Introduzione

La tecnologia LAN senza fili (WLAN) costituisce un argomento alquanto controverso. Le organizzazioni che hanno già distribuito reti LAN senza fili sono preoccupate del grado di protezione offerto da queste soluzioni, mentre quelle che non le hanno ancora distribuite temono di perdere un'occasione vantaggiosa in termini di produttività degli utenti e costi di proprietà ridotti. Il dubbio che una LAN senza fili non sia una soluzione ideale per l'ambito aziendale in termini di protezione è ancora molto diffuso.

Fin dalla scoperta dei punti deboli della prima generazione di soluzioni di protezione per LAN senza fili, gli analisti e i fornitori di servizi di protezione di rete hanno concentrato tutti gli sforzi nel tentativo di risolvere tali problemi, riuscendo in alcuni casi a contribuire in maniera significativa alla causa della protezione in ambito senza fili. In altri casi gli interventi non si sono dimostrati efficaci: alcune soluzioni introducono altre vulnerabilità della protezione, altre proposte richiedono l'acquisto di componenti hardware molto costosi e altre ancora evitano il problema della protezione delle reti LAN senza fili usufruendo di un'altra tecnologia di protezione potenzialmente complessa, le reti private virtuali (VPN).

Allo stesso tempo l'istituto IEEE (Institute of Electrical and Electronic Engineers), insieme ad altri enti e consorzi di definizione degli standard, si sono dedicati scrupolosamente a ridefinire e migliorare gli standard della protezione senza fili allo scopo di consentire alle reti LAN senza fili di poter resistere all'ambiente di protezione ostile dell'inizio del ventunesimo secolo. Grazie all'impegno degli enti di definizione degli standard e delle aziende leader del settore, la definizione "protezione di reti LAN senza fili" non è più considerata un ossimoro. Le reti LAN senza fili possono ora essere distribuite e utilizzate con un alto grado di affidabilità.

Il presente documento introduce due soluzioni di protezione delle reti LAN senza fili sviluppate da Microsoft® e risponde ai dubbi relativi al livello di protezione raggiungibile nelle reti LAN senza fili e al modo migliore in cui proteggerle.

#### Panoramica sulle soluzioni senza fili

L'obiettivo principale di questo documento è di agevolare le organizzazioni nella scelta del metodo di protezione delle reti LAN senza fili più appropriato. Per raggiungere questo scopo, nel documento vengono esaminate in maniera dettagliata quattro aree principali:

-   Vantaggi delle reti LAN senza fili e problemi di protezione associati

-   Utilizzo degli standard di protezione delle reti LAN senza fili

-   Strategie alternative, come VPN e IPsec (Internet Protocol security)

-   Selezione delle opzioni appropriate per le reti LAN senza fili

Microsoft ha prodotto due soluzioni LAN senza fili basate su standard aperti formulati da enti quali IEEE, IETF (Internet Engineering Task Force) e Wi-Fi Alliance. Queste due soluzioni sono intitolate *Securing Wireless LANs—A Windows Server 2003 Certificate Services Solution* e *Protezione delle reti LAN senza fili con PEAP e password*. Come lasciano intuire i nomi, la prima soluzione utilizza certificati a chiave pubblica per autenticare utenti e computer nella rete LAN senza fili, mentre nel secondo caso vengono utilizzati semplici nomi utenti e password. In ogni modo, l'architettura di base delle due soluzioni è molto simile. Entrambe sono basate sull'infrastruttura di Microsoft Windows® Server™ 2003 e sui client Microsoft Windows XP e Microsoft Pocket PC 2003.

Sebbene non sia evidente dai titoli, i destinatari di queste due soluzioni sono diversi. *Securing Wireless LANs—A Windows Server 2003 Certificate Services Solution* è orientata principalmente alle grandi organizzazioni con ambienti IT relativamente complessi, mentre *Protezione delle reti LAN senza fili con PEAP e password* è notevolmente più semplice e può essere distribuita facilmente dalle organizzazioni di dimensioni minori.

Ciò non implica che l'autenticazione tramite password non possa essere utilizzata dalle organizzazioni più grandi o che l'autenticazione tramite certificati non sia adatta alle organizzazioni di dimensioni ridotte, bensì riflette il tipo di organizzazione in cui è più probabile che le diverse tecnologie vengano utilizzate. Nella figura che segue è illustrata una struttura decisionale per favorire la scelta della soluzione più adatta alla propria organizzazione. Le tre opzioni principali sono:

-   Chiave già condivisa WPA (Wi-Fi Protected Access) per imprese di dimensioni ridotte e uffici privati.

-   Protezione della rete LAN senza fili basata su password per organizzazioni che non utilizzano o richiedono certificati.

-   Protezione della rete LAN senza fili basata su certificati per organizzazioni che richiedono e possono distribuire certificati.

Queste opzioni verranno descritte nell'ambito del presente documento, insieme alla possibilità di unire le caratteristiche delle ultime due opzioni per produrre una soluzione ibrida.

[![](images/Dd536242.PEAP_i01(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536242.peap_i01_big(it-it,technet.10).gif)

**Figura 1: Struttura decisionale per soluzioni Microsoft per reti LAN senza fili**

[](#mainsection)[Inizio pagina](#mainsection)

### Vantaggi delle reti senza fili

L'attrattiva delle reti LAN senza fili per le imprese è evidente. La tecnologia LAN senza fili è una realtà diffusa, in varie forme, ormai da una decina d'anni, ma fino a poco tempo fa non era riuscita ad affermarsi. Solo quando la tecnologia affidabile, standardizzata e a costi ridotti ha risposto all'esigenza crescente di individuare metodi di lavoro flessibili e soluzioni di connettività sempre più estese, le reti LAN senza fili hanno realmente iniziato a decollare. La rapida diffusione di questa tecnologia ha però evidenziato una serie di punti deboli estremamente gravi nell'ambito della protezione della prima generazione di reti LAN senza fili. In questa sezione verranno esaminati i vantaggi (funzionalità) e svantaggi (protezione) delle reti LAN senza fili.

#### Vantaggi delle reti LAN senza fili

I vantaggi della tecnologia LAN senza fili possono essere suddivisi in due categorie principali: produttivi e operativi. I vantaggi produttivi includono una maggiore produttività dei dipendenti, processi aziendali più rapidi ed efficienti, e maggiori capacità di creazione di funzioni aziendali completamente nuove. I vantaggi operativi riguardano invece aspetti quali la riduzione dei costi di gestione o delle spese in conto capitale.

##### Vantaggi produttivi

I principali vantaggi produttivi delle reti LAN senza fili sono legati alla maggiore flessibilità e mobilità della forza lavoro.

I dipendenti non sono più costretti a svolgere il lavoro necessariamente dalla propria postazione e possono spostarsi agevolmente all'interno dell'ufficio senza disconnettersi dalla rete. Può essere utile esaminare alcuni esempi di come la maggiore mobilità e flessibilità della rete possa incidere positivamente sulla produttività.

-   I dipendenti che si spostano da un ufficio all'altro e i telelavoratori risparmiano tempo e fatica grazie all'accesso trasparente alla rete locale (LAN, Local Area Network) dell'organizzazione. Il collegamento è immediato e disponibile da qualsiasi posizione fisica coperta dalla rete senza fili: per effettuare una connessione non è più necessario cercare porte e cavi di rete o rivolgersi al personale IT.

-   I dipendenti possono restare in contatto da qualsiasi posizione all'interno dell'edificio. Utilizzando la posta elettronica, i calendari elettronici e le tecnologie chat, il personale può rimanere in linea anche durante una riunione o quando lavora lontano dalla postazione.

-   Le informazioni in linea sono sempre disponibili. Non è più necessario interrompere le riunioni quando un partecipante si allontana per recuperare il report del mese precedente o l'aggiornamento di una presentazione. Questo consente di migliorare notevolmente la qualità e la produttività delle riunioni.

-   Anche la flessibilità dell'organizzazione è maggiore. Poiché il personale non è più vincolato alla scrivania, gli spostamenti di postazione o persino dell'intero ufficio richiesti da un nuovo progetto o gruppo diventano più semplici e veloci.

-   L'integrazione di nuovi dispositivi e applicazioni all'interno dell'ambiente IT aziendale viene migliorata in maniera significativa. Dispositivi quali agende elettroniche (PDA) e Tablet PC, che fino a qualche tempo fa erano considerate elementi di svago e quindi marginali per l'ambiente IT, possono essere integrati e ritenuti più utili per le organizzazioni che utilizzano i collegamenti di rete senza fili. I dipendenti e i processi produttivi, che precedentemente non integravano tecnologie informatiche IT, ora possono beneficiare di computer, dispositivi e applicazioni di rete in aree precedentemente escluse dalla rete, quali ad esempio, stabilimenti di produzione, reparti ospedalieri, negozi e ristoranti.

I vantaggi non sono applicabili in ugual modo a tutte le organizzazioni. Ciò dipende dalla natura delle attività aziendali e, tra gli altri fattori, dalla dimensione e distribuzione geografica della forza lavoro.

##### Vantaggi operativi

I principali vantaggi operativi della tecnologia di rete WLAN, quali la riduzione dei costi di esercizio e degli investimenti, possono essere riepilogati come segue.

-   I costi di implementazione dell'accesso di rete negli edifici sono notevolmente ridotti e, sebbene gran parte dei locali degli uffici siano completamente cablati, è altrettanto vero che alcuni non lo sono affatto, ad esempio reparti di produzione, magazzini e negozi. Le reti possono anche essere estese in aree in cui risulterebbe impossibile accedere a reti cablate, ad esempio, all'aperto, in mare o addirittura sul campo di battaglia.

-   La rete può essere facilmente scalata per rispondere alle diverse esigenze legate all'evoluzione dell'azienda anche su base giornaliera, se necessario. È molto più semplice distribuire una maggiore concentrazione di punti di accesso senza fili in una determinata ubicazione che aumentare il numero di porte di rete.

-   Gli investimenti non saranno più vincolati a un edificio: l'infrastruttura di rete senza fili può essere spostata facilmente in un nuovo edificio, a differenza del cablaggio che in genere rappresenta una soluzione permanente.

#### Problemi di protezione nelle reti LAN senza fili

Nonostante tutti i vantaggi menzionati, alcuni problemi legati alla protezione delle reti LAN senza fili ne hanno limitato la diffusione, in particolar modo nei settori in cui la protezione è un aspetto prioritario, come l'ambito finanziario e governativo. Sebbene il rischio di trasmettere dati di rete non protetti ad altri utenti nelle vicinanze possa sembrare evidente, in un numero sorprendentemente elevato di casi le reti LAN senza fili vengono installate senza alcun sistema di sicurezza. La maggior parte delle imprese implementa qualche forma di protezione senza fili, tuttavia si tratta in genere di metodi basilari o di soluzioni datate che offrono una protezione inadeguata per gli standard attuali.

Quando vennero definiti i primi standard IEEE 802.11 per reti LAN senza fili, la protezione non aveva ancora assunto le caratteristiche di importanza acquisite di recente. Il livello di complessità delle minacce era notevolmente inferiore e la diffusione della tecnologia senza fili era ancora agli esordi. È in questo contesto che venne sviluppato il primo schema di protezione per reti LAN senza fili, denominato Wired Equivalent Privacy (WEP). La protezione WEP sottovalutò le misure necessarie per rendere il livello di protezione di una rete senza fili equivalente a quello di una rete cablata. I più recenti metodi di protezione per LAN senza fili sono invece progettati in modo specifico per un ambiente ostile come quello senza fili in cui non esiste un perimetro fisico o di rete ben definito.

È importante distinguere la protezione WEP statica di prima generazione, che si avvaleva di password condivise per proteggere la rete, e gli schemi di protezione adottati dalla crittografia WEP basati su servizi di autenticazione avanzata e gestione delle chiavi di crittografia. Quest'ultimo è uno schema di protezione completo che include l'autenticazione e la protezione dei dati e, in questo documento, verrà indicato come "WEP statico". Per WEP dinamico, invece, si intende solo il metodo di crittografia e verifica dell'integrità dei dati utilizzato nell'ambito di altre soluzioni di protezione avanzate descritte nel corso di questo documento.

I punti deboli della protezione individuati nel WEP statico hanno evidenziato come le reti LAN a cui era stata applicata questa soluzione erano vulnerabili a vari tipi di attacchi. Strumenti di controllo ampiamente diffusi come Airsnort e WEPCrack rendono l'accesso a reti senza fili protette mediante WEP statico un gioco da ragazzi. Ovviamente anche le reti LAN non protette sono esposte agli stessi rischi, la differenza è rappresentata solo dalla minore quantità di esperienza, tempo e risorse necessaria per portare a termine l'attacco.

Prima di esaminare il funzionamento delle più recenti soluzioni di protezione per reti LAN senza fili, è opportuno valutare i principali rischi a cui sono esposte queste reti. Tali rischi sono riepilogati nella tabella seguente.

**Tabella 1: Principali pericoli relativi alla protezione per reti LAN senza fili**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pericolo</th>
<th>Descrizione del pericolo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Divulgazione di dati</td>
<td style="border:1px solid black;">L'intercettazione non autorizzata di trasmissioni di rete può comportare la divulgazione di dati riservati e credenziali utente non protette, nonché la potenziale acquisizione di identità. Questa vulnerabilità potrebbe consentire a utenti malintenzionati e dotati di strumenti sofisticati di raccogliere informazioni sull'ambiente IT dell'azienda e di utilizzarle per attaccare altri sistemi o dati che altrimenti non sarebbero vulnerabili.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Intercettazione e modifica di dati trasmessi</td>
<td style="border:1px solid black;">Se un pirata informatico riesce a ottenere l'accesso alla rete,questi potrà inserire un computer per intercettare e modificare i dati di rete trasmessi tra due parti autorizzate in comunicazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Spoofing</td>
<td style="border:1px solid black;">La disponibilità dell'accesso alla rete interna consente agli intrusi di inviare dati apparentemente legittimi, ad esempio un messaggio di posta elettronica di spoofing, in modi che non sarebbero consentiti dall'esterno. Gli utenti, inclusi gli amministratori di sistema, tendono in genere a guardare con minor sospetto gli elementi di origine interna rispetto a quelli che provengono dall'esterno della rete aziendale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Denial of service (DoS)</td>
<td style="border:1px solid black;">Un utente malintenzionato può sferrare un attacco di tipo DoS in vari modi. Ad esempio, l'interruzione del segnale a livello di trasmissione radio può essere realizzata con strumenti a bassa tecnologia: ad esempio, un forno a microonde. Gli attacchi di rete possono essere molto sofisticati e puntare verso protocolli di rete senza fili di basso livello; oppure, quelli meno sofisticati, possono avere come obiettivo il sovraccarico della rete WLAN con un traffico casuale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Collegamento non autorizzato o furto di risorse</td>
<td style="border:1px solid black;">Un intruso potrebbe utilizzare la rete aziendale come punto di accesso non autorizzato a Internet. Sebbene non sia altrettanto dannoso di altri pericoli, questo attacco può ridurre la disponibilità dei servizi per gli utenti legittimi e introdurre virus o altri problemi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Rischi accidentali</td>
<td style="border:1px solid black;">Alcune caratteristiche delle reti LAN senza fili possono aumentare la gravità degli attacchi non intenzionali. Ad esempio, è possibile che un visitatore autorizzato avvii il proprio computer portatile senza l'intento di collegarsi alla rete, ma venga automaticamente collegato alla rete LAN senza fili. Il computer portatile del visitatore può rappresentare un punto di accesso alla rete per eventuali virus. Questo tipo di pericolo rappresenta un problema solo per reti WLAN non protette.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Reti WLAN inaffidabili</td>
<td style="border:1px solid black;">Anche se l'azienda non dispone ufficialmente di una rete LAN senza fili, potrebbe comunque sussistere il rischio che reti WLAN non gestite interferiscano con la rete aziendale. Componenti hardware WLAN di bassa qualità acquistati dai dipendenti possono esporre la rete a pericoli imprevisti.</td>
</tr>
</tbody>
</table>
  
I problemi legati alla protezione delle reti LAN senza fili, basati su WEP statico, hanno suscitato un notevole interesse nei mezzi di informazione. Sebbene esistano efficaci soluzioni per combattere questi pericoli, le organizzazioni di tutti i tipi restano diffidenti nei confronti delle reti LAN senza fili. Alcune hanno addirittura arrestato lo sviluppo di tecnologie WLAN o ne hanno vietato completamente l'uso. Di seguito sono elencati alcuni dei fattori principali che contribuiscono a generare questa confusione e al preconcetto diffuso che le reti LAN non possano essere sicure:
  
-   È difficile distinguere le tecnologie WLAN affidabili da quelle a rischio. Le imprese sono sospettose nei confronti di tutte le misure di protezione delle reti LAN senza fili dopo il susseguirsi di difetti scoperti nel WEP statico. L'elenco quasi illimitato di standard ufficiali e di soluzioni dei problemi per la protezione ha contribuito ad aumentare la confusione.
  
-   Il fatto che la rete senza fili sia invisibile non costituisce solo un fattore di instabilità psicologica, bensì ha determinato problemi concreti nella gestione della protezione da parte degli amministratori di reti. Mentre è possibile *vedere* un intruso che collega un cavo nella rete cablata, l'intruso nelle reti WLAN non è fisicamente individuabile. I tradizionali sistemi di difesa fisica rappresentati da muri o porte che proteggono la rete cablata non sono in grado di bloccare un intruso che si insinua nella rete senza fili.
  
-   C'è una maggiore consapevolezza dell'esigenza di proteggere le informazioni. Le imprese richiedono livelli di protezione molto più elevati nei propri sistemi e diffidano di qualsiasi tecnologia che possa introdurre delle vulnerabilità.
  
-   Come conseguenza di questa maggiore consapevolezza, si sta sviluppando un insieme crescente di regolamentazioni e legislazioni che regolano la protezione dei dati in un numero crescente di paesi e settori. Uno degli esempi più rappresentativi di questo fenomeno è costituito dall'HIPAA (Health Insurance Portability and Accountability Act) del 1996, che disciplina la gestione dei dati sanitari personali negli Stati Uniti.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Come proteggere (realmente) la rete WLAN
  
Da quando sono stati individuati i punti deboli delle reti LAN senza fili, come descritto in precedenza, i maggiori fornitori di servizi di reti, gli enti preposti alla definizione degli standard e gli analisti hanno dedicato un notevole impegno alla ricerca di soluzioni a queste vulnerabilità. Tutto ciò ha portato a formulare una serie di proposte ai problemi legati alla protezione delle reti WLAN. Di seguito sono riportati le principali alternative:
  
-   Non distribuire la tecnologia di rete WLAN
  
-   Utilizzare la protezione WEP statica 802.11
  
-   Utilizzare VPN per proteggere i dati nella WLAN
  
-   Utilizzare IPsec per proteggere il traffico della WLAN
  
-   Utilizzare l'autenticazione 802.1X e la crittografia dei dati per proteggere la WLAN
  
Queste soluzioni sono elencate in ordine indicativo, dalla meno soddisfacente alla più soddisfacente, in relazione alla combinazione di protezione, funzionalità e utilizzabilità che ciascuna opzione offre (sebbene in tale classificazione possa sussistere una componente soggettiva). L'opzione consigliata da Microsoft è rappresentata dall'ultima alternativa: l'utilizzo dell'autenticazione 802.1X e della crittografia dei dati della WLAN. Questo approccio è esaminato nella sezione successiva ed è confrontato con un elenco dei principali pericoli delle WLAN identificati in precedenza (Tabella 1). Nella sezione successiva a quella appena menzionata sono valutati anche i vantaggi e gli svantaggi principali degli altri approcci.
  
#### Protezione della rete LAN senza fili mediante l'autenticazione 802.1X e la crittografia dei dati
  
Questo approccio presenta numerosi aspetti positivi, sebbene la definizione stessa e la terminologia complessa non siano tra questi. Ma prima di esaminare i vantaggi delle soluzioni basate su questo approccio, è importante chiarire alcuni termini e descrivere il funzionamento di una soluzione di questo tipo.
  
##### Protezione di una rete LAN senza fili
  
La protezione di una rete LAN senza fili include tre elementi principali:
  
-   L'autenticazione degli utenti o dispositivi che si connettono alla rete, che consente di individuare in modo attendibile le origini di tutti i tentativi di connessione.
  
-   L'autorizzazione di un utente o dispositivo all'utilizzo della rete LAN senza fili, che consente di controllare a quali utenti concedere l'accesso.
  
-   La protezione dei dati trasmessi nella rete, in modo da impedire l'intercettazione e la modifica non autorizzata dei dati.
  
In aggiunta a questi elementi può essere necessaria una funzione di controllo, anche se gli strumenti di controllo consentono solo di verificare il funzionamento e rinforzare gli altri tre fattori.
  
###### Autenticazione e autorizzazione di rete
  
La protezione WEP statica si basa si un semplice segreto condiviso (password o chiave) per l'autenticazione nella WLAN. Chiunque disponga di questa chiave segreta può accedere alla WLAN. Lo standard WEP non prevedere un metodo per l'automazione dell'aggiornamento o della distribuzione di tali chiavi, quindi è estremamente difficile modificarle periodicamente. Un utente malintenzionato può sfruttare imperfezioni crittografiche in WEP per individuare le chiavi WEP statiche mediante strumenti elementari.
  
Per garantire un metodo più affidabile di autenticazione e autorizzazione, Microsoft e alcuni altri fornitori hanno proposto una struttura di protezione WLAN basata sul protocollo 802.1X. 802.1X è uno standard IEEE per l'autenticazione dell'accesso alla rete che può anche essere utilizzato per la gestione delle chiavi di protezione del traffico di rete. Il suo utilizzo non è limitato alle reti senza fili, bensì è implementata in numerosi switch di fascia alta della rete LAN cablata.
  
Il protocollo 802.1X richiede la presenza dell'utente di rete, di un dispositivo di accesso alla rete (o gateway) come un punto di accesso senza fili e un servizio di autenticazione e autorizzazione costituito da un server RADIUS (Remote Authentication Dial-In User Service). Il server RADIUS gestisce il processo di autenticazione delle credenziali dell'utente e di autorizzazione dell'accesso alla WLAN.
  
Lo standard 1X si basa su un protocollo IETF denominato EAP (Extensible Authentication Protocol) per gestire lo scambio di dati di autenticazione tra il client e il server RADIUS (inoltrati dal punto di accesso). EAP è un protocollo generico per l'autenticazione che supporta numerosi metodi di autenticazione, con password, certificati digitali o altri tipi di credenziali.
  
Poiché il protocollo EAP può essere inserito in un metodo di autenticazione, non esiste un tipo standard di autenticazione EAP da utilizzare. I metodi EAP applicabili ai diversi contesti possono essere vari, con tipi di credenziali e protocolli di autenticazione differenti. L'utilizzo dei metodi EAP nell'autenticazione delle reti WLAN è esaminato in una sezione successiva.
  
###### Protezione dei dati della rete LAN senza fili
  
L'autenticazione 1X e l'accesso alla rete rappresentano solo una parte della soluzione. L'altro componente importante è costituito dalla protezione del traffico della rete senza fili.
  
I difetti nella crittografia dei dati WEP descritti in precedenza possono essere mitigati se nel WEP è incluso un metodo che consente di aggiornare automaticamente le chiavi di crittografia a intervalli regolari. Gli strumenti utilizzati per violare il WEP statico devono raccogliere da uno a svariati milioni di pacchetti crittografati con la stessa chiave. Ma poiché le chiavi WEP statiche restano spesso invariate per settimane o mesi, un utente malintenzionato può facilmente raccogliere un volume così elevato di dati. Tutti i computer di una rete LAN senza fili condividono la stessa chiave statica, pertanto le trasmissioni di dati generate da tutti i computer della rete possono essere intercettate per facilitare l'individuazione della chiave.
  
Se si utilizza una soluzione basata sullo standard 802.1X, è possibile modificare frequentemente le chiavi di crittografia. Durante il processo di autenticazione della protezione 802.1X, il metodo EAP genera una chiave di crittografia specifica per ogni client. Per impedire la violazione della protezione WEP (descritta in precedenza), il server RADIUS impone la generazione periodica di nuove chiavi di crittografia. In questo modo, è possibile utilizzare gli algoritmi di crittografia WEP, presenti nei componenti WLAN più recenti, in maniera nettamente più affidabile.
  
###### WPA e 802.11i
  
Sebbene la rigenerazione dinamica delle chiavi dello standard 802.1X garantisca una protezione adeguata per la maggior parte degli scopi pratici, persistono ancora alcuni problemi:
  
-   WEP utilizza una chiave statica separata per le trasmissioni globali come il broadcast di pacchetti. Diversamente dalle chiavi specifiche per gli utenti, la chiave globale non viene rinnovata regolarmente. Sebbene in genere non vengono trasmessi dati riservati mediante broadcast, l'uso di una chiave statica per le trasmissioni globale fornisce a utenti malintenzionati la possibilità di scoprire informazioni sulla rete come gli indirizzi IP o i nomi di computer e utenti.
  
-   La protezione dell'integrità nel caso di frame di rete protetti tramite WEP è decisamente insufficiente. Utilizzando tecniche di crittografia, un utente malintenzionato può modificare le informazioni nel frame WLAN e aggiornare il valore di controllo dell'integrità senza che il destinatario lo rilevi.
  
-   Con il progressivo incremento della velocità di trasmissione nelle WLAN e il miglioramento delle capacità di elaborazione e delle tecniche di decrittazione, la frequenza di rinnovo delle chiavi WEP dovrà essere notevolmente aumentata. Ciò provocherebbe un carico eccessivo sui server RADIUS.
  
Per risolvere questi problemi, l'istituto IEEE sta sviluppando un nuovo standard di protezione WLAN denominato 802.11i, anche noto come RSN (Robust Security Network). La Wi-Fi Alliance, consorzio di fornitori Wi-Fi leader nel settore, ha utilizzato una prima versione della protezione 802.11i per pubblicare uno standard denominato WPA (Wi-Fi Protected Access). La protezione WPA include un ampio sottoinsieme delle funzioni presenti in 802.11i. In questo modo la Wi-Fi Alliance è riuscita imporre la conformità a questo standard per tutte le apparecchiature che portano il logo Wi-Fi e ha consentito ai fornitori di hardware di rete Wi-Fi di offrire un'opzione di protezione avanzata di serie prima del rilascio di 802.11i. Esso raggruppa un insieme di funzioni di protezione considerate, tra le tecniche attualmente disponibili, le più affidabili per la protezione di reti WLAN.
  
Lo standard WPA prevede due modalità: una basata su 802.1X e sull'autenticazione RADIUS (definita semplicemente WPA) e uno schema più semplice per gli ambienti SOHO che si avvale di una chiave già condivisa (definito WPA PSK). WPA combina un sistema di crittografia avanzata con il meccanismo di autenticazione e autorizzazione affidabile di 802.1X. La protezione dei dati WPA elimina le vulnerabilità note di WEP nei seguenti modi:
  
-   Utilizzando una chiave di crittografia univoca per ogni pacchetto
  
-   Utilizzando un vettore di inizializzazione molto più lungo, raddoppiando lo spazio della chiave mediante l'aggiunta di 128 supplementari di materiale delle chiavi
  
-   Aggiungendo un valore di controllo dell'integrità del messaggio firmato che non può essere manomesso o soggetto a spoofing
  
-   Incorporando un contatore di frame crittografato per ostacolare gli attacchi di riproduzione
  
Tuttavia, poiché WPA utilizza algoritmi di crittografia simili a quelli utilizzati da WEP, può essere implementato in componenti hardware esistenti con un semplice aggiornamento del firmware.
  
La modalità PSK di WPA consente inoltre alle piccole organizzazioni e ai privati di utilizzare una rete WLAN a chiave condivisa senza incorrere nelle vulnerabilità del WEP statico (ammesso che la chiave già condivisa in uso sia sufficientemente complessa da impedire attacchi di individuazione della password). Analogamente alla protezione WPA su base RADIUS e al WEP dinamico, vengono generate singole chiavi di crittografia per ogni client senza fili. La chiave già condivisa viene utilizzata come credenziale di autenticazione; quindi, se si dispone della chiave, si è autorizzati a utilizzare la rete WLAN e a ricevere una chiave di crittografia univoca per proteggere i dati.
  
Il rilascio dello standard 802.11i (RSN), previsto per la metà del 2004, garantirà un livello di protezione ancora più elevato per le reti LAN senza fili, inclusa una migliore protezione dagli attacchi di tipo DoS.
  
###### Metodi di autenticazione EAP
  
La protezione EAP supporta numerosi metodi di autenticazione. Tali metodi possono utilizzare diversi protocolli di autenticazione, come Kerberos, TLS (Transport Layer Security) e MS-CHAP (Microsoft-Challenge Handshake Authentication Protocol), con vari tipi di credenziali, tra cui password, certificati, password da utilizzare una sola volta e sistemi biometrici. Sebbene con 802.1X possa essere utilizzato virtualmente qualsiasi metodo EAP, non tutti sono adatti alle reti LAN senza fili e, in particolare, il metodo utilizzato deve essere adatto a un ambiente non protetto ed essere in grado di generare chiavi di crittografia.
  
I principali metodi EAP utilizzati per le reti WLAN sono EAP-TLS, PEAP (Protected EAP), TTLS (Tunneled TLS) e LEAP (Lightweight EAP). Tra questi, i metodi PEAP e EAP-TLS sono supportati da Microsoft.
  
**EAP-TLS**
  
EAP-TLS è probabilmente lo standard IETF (RFC 2716) più supportato su client senza fili e server RADIUS. Utilizza i certificati a chiave pubblica per autenticare sia i client senza fili che i server RADIUS, stabilendo una sessione TLS crittografata tra le due parti.
  
**PEAP**
  
PEAP è un metodo di autenticazione in due fasi. Nella prima fase viene stabilita una sessione TLS sul server che consente al client di autenticare il server mediante il certificato digitale. La seconda fase richiede un altro metodo EAP con tunnel nella sessione PEAP per autenticare il client sul server RADIUS. In questo modo PEAP può utilizzare vari metodi di autenticazione del client, incluse password con il protocollo MS-CHAP versione 2 (MS-CHAP v2) e certificati con tunnel EAP-TLS in PEAP. I tipi di metodi EAP come MS-CHAP v2 non garantiscono un livello di protezione sufficiente per poter essere utilizzati senza la protezione PEAP, in quanto risulterebbero vulnerabili ad attacchi del dizionario non in linea. PEAP è generalmente supportato nel settore e Microsoft Windows XP SP1 e Pocket PC 2003 includono un supporto incorporato per PEAP.
  
**TTLS**
  
TTLS è un protocollo in due fasi simile a PEAP che utilizza una sessione TLS per proteggere l'autenticazione di un client con tunnel. Oltre ai metodi EAP con tunnel, TTLS può anche avvalersi di versioni non EAP dei protocolli di autenticazione come CHAP, MS-CHAP e altri. Microsoft e Cisco non supportano TTLS, sebbene altri fornitori distribuiscano client TTLS per numerose piattaforme.
  
**LEAP**
  
LEAP è un metodo EAP proprietario sviluppato da Cisco che utilizza le password per autenticare i client. Nonostante sia molto diffuso, il protocollo LEAP funziona solo con hardware e software Cisco e di pochi altri fornitori. Presenta inoltre alcuni punti deboli noti, come la vulnerabilità ad attacchi del dizionario non in linea (che possono consentire a intrusi di violare le password degli utenti) e di tipo "man-in-the-middle". In un ambiente di dominio, LEAP può autenticare solo gli *utenti* nella WLAN, non i *computer*. Senza autenticazione dei computer, i criteri di gruppo del computer non potranno essere eseguiti correttamente, le impostazioni di installazione del software, i profili comuni e gli script di accesso possono generare errori e gli utenti non potranno modificare le password scadute.
  
Esistono soluzioni di protezione per reti LAN senza fili che utilizzano lo standard 802.1X con altri metodi EAP. Alcuni di questi metodi EAP, come EAP-MD5, presentano notevoli vulnerabilità se applicati a un ambiente WLAN e se ne sconsiglia pertanto l'utilizzo. Altri metodi supportano l'uso di password da utilizzare una sola volta e di altri protocolli di autenticazione, come Kerberos. Tuttavia questi metodi non hanno ancora avuto un impatto significativo nel settore delle reti LAN senza fili.
  
##### Vantaggi di 802.1X con protezione dei dati WLAN
  
I principali vantaggi di una soluzione 802.1X sono riepilogati nell'elenco seguente:
  
-   **Livello di protezione Alto:** lo schema di autenticazione avanzato consente l'uso di certificati client o di nomi utente e password.
  
-   **Crittografia avanzata:** i dati della rete vengono crittografati in maniera affidabile.
  
-   **Processi trasparenti:** l'autenticazione e la connessione alla rete LAN senza fili sono invisibili all'utente.
  
-   **Autenticazione di utenti e computer:** l'autenticazione degli utenti e dei computer può avvenire separatamente. In questo modo i computer possono essere gestiti anche se non vi sono utenti connessi.
  
-   **Costi ridotti:** l'hardware di rete presenta costi estremamente contenuti.
  
-   **Prestazioni elevate:** poiché la crittografia viene eseguita nell'hardware WLAN anziché dalla CPU del client, il processo di crittografia non incide sul livello di prestazioni del client.
  
Esistono tuttavia alcuni aspetti di una soluzione 802.1X da tenere in considerazione.
  
-   Sebbene lo standard 802.1X sia quasi universalmente accettato, l'uso di diversi metodi EAP non consente di garantire un'interoperabilità costante.
  
-   La tecnologia WPA è ancora nelle prime fasi della sua diffusione e potrebbe non essere disponibile in hardware datato.
  
-   La protezione RSN di nuova generazione (802.11i) deve essere ancora approvata e richiederà la distribuzione di aggiornamenti hardware e software (l'hardware di rete in genere richiederà l'aggiornamento del firmware).
  
Questi sono, in ogni caso, aspetti secondari e sono nettamente superati dai vantaggi di queste soluzioni; in particolar modo se confrontati con le significative lacune degli approcci alternativi esaminati in seguito.
  
###### Capacità di recupero della soluzione 802.1X rispetto ai rischi per la protezione
  
I principali pericoli per la protezione delle reti LAN senza fili sono stati descritti in sezioni precedenti del documento (Tabella 1). Tali rischi sono riproposti nella tabella che segue in relazione a una soluzione basata su 802.1X e sulla protezione dei dati della rete LAN senza fili.
  
**Tabella 2: Rischi potenziali per la sicurezza analizzati in relazione alla soluzione proposta**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pericolo</th>
<th>Riduzione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Divulgazione di dati</td>
<td style="border:1px solid black;">L'assegnazione e la modifica dinamica delle chiavi di crittografia a intervalli frequenti e il fatto che le chiavi sono univoche per ciascuna sessione utente significa che, se la frequenza di aggiornamento delle chiavi è adeguata, l'individuazione delle chiavi e l'accesso ai dati non è possibile con i mezzi attualmente conosciuti.
Il livello di protezione garantito da WPA è superiore grazie alla modifica delle chiavi di crittografia per i singoli pacchetti. La chiave globale, che protegge il traffico broadcast, viene rigenerata per ogni pacchetto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Intercettazione e modifica di dati trasmessi</td>
<td style="border:1px solid black;">Applicando meccanismi di verifica dell'integrità dei dati e di crittografia avanzata dei tra il client senza fili e il punto di accesso senza fili, non è possibile che un utente malintenzionato intercetti e modifichi i dati.
L'autenticazione reciproca tra client, server RADIUS e punto di accesso senza fili impedisce che questi possano essere utilizzati impropriamente da utenti malintenzionati.
Grazie a WPA la verifica dell'integrità dei dati è migliorata dall'uso del protocollo Michael.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Spoofing</td>
<td style="border:1px solid black;">L'autenticazione protetta sulla rete impedisce ad utenti non autorizzati di collegarsi alla rete e di introdurvi dati di spoofing dall'interno.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Negazione del servizio (DoS)</td>
<td style="border:1px solid black;">Gli attacchi a livello di rete, come quelli che generano un aumento del traffico o altri attacchi DoS, sono impediti dal controllo dell'accesso alla rete WLAN basato sullo standard 802.1X. Non esiste tuttavia alcun metodo di difesa in WEP o WPA contro gli attacchi di negazione del servizio (DoS) 802.11 DoS di basso livello. Questo problema verrà risolto dallo standard 802.11i.
In realtà, anche questo nuovo standard non sarà immune dall'interruzione della rete a livello di trasmissione radio.
Queste vulnerabilità sono caratteristiche delle WLAN 802.11 e sono comuni a tutte le altre opzioni esaminate nel corso di questo documento.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Collegamento non autorizzato o furto di risorse</td>
<td style="border:1px solid black;">L'uso non autorizzato della rete è impedito dall'elevata affidabilità dell'autenticazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Rischi accidentali</td>
<td style="border:1px solid black;">La connessione accidentale alla rete WLAN è impedita dall'autenticazione protetta.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Reti WLAN inaffidabili</td>
<td style="border:1px solid black;">Sebbene la soluzione non intervenga direttamente nella gestione dei punti di accesso senza fili inaffidabili, implementando una soluzione di rete senza fili protetta come questa, la motivazione di installare reti WLAN non ufficiali non avrà più ragione di esistere.
In ogni caso, è consigliabile creare e pubblicare un criterio che impedisca esplicitamente l'uso di reti LAN senza fili non approvate. È possibile applicare il criterio mediante strumenti software di individuazione degli indirizzi dell'hardware del punto di accesso senza fili e mediante apparecchiature portatili di rilevamento delle reti WLAN.</td>
</tr>
</tbody>
</table>
 

#### Altri approcci alla protezione delle reti LAN senza fili

Nella sezione precedente è stata descritta in dettaglio l'autenticazione 802.1X con protezione dei dati WLAN. In questa sezione verranno esaminate le altre quattro alternative alla protezione WLAN menzionate in precedenza (all'inizio della sezione "Come proteggere (realmente) la rete WLAN").

I quattro approcci sono:

-   Non distribuire la tecnologia di rete WLAN

-   Utilizzare la protezione WEP statica 802.11

-   Utilizzare VPN per proteggere i dati nella WLAN

-   Utilizzare IPsec per proteggere il traffico della WLAN

Le principali differenza tra questi approcci e una soluzione su base 802.1X sono riepilogate nella tabella seguente (sebbene l'opzione senza WLAN non sia inclusa perché non può essere confrontata con le altre). Le opzioni elencate sono descritte in maggiore dettaglio nelle sezioni successive.

**Tabella 3: Confronto degli approcci alla protezione WLAN**

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th>Funzionalità</th>
<th>WLAN 802.1X</th>
<th>WEP statico</th>
<th>VPN</th>
<th>IPsec</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione
avanzata (1)</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
<td style="border:1px solid black;">Sì,
escluso VPN che utilizzano l'autenticazione con chiave condivisa</td>
<td style="border:1px solid black;">Sì,
se utilizzano l'autenticazione di certificati o Kerberos</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Crittografia avanzata dei dati</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Connessione e riconnessione trasparente alla WLAN</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Autenticazione utente</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione
computer (2)</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Protezione traffico broadcast e multicast</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Richiesti dispositivi di rete aggiuntivi</td>
<td style="border:1px solid black;">Server RADIUS</td>
<td style="border:1px solid black;">No</td>
<td style="border:1px solid black;">Server VPN, server RADIUS</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso protetto alla WLAN</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
<td style="border:1px solid black;">No</td>
</tr>
</tbody>
</table>
  
(1) Molte implementazioni VPN basate sulla modalità di tunnel IPsec utilizzano uno schema insufficiente di autenticazione con chiave condivisa definito XAuth.
  
(2) L'autenticazione di computer implica che il computer resterà connesso alla WLAN e alla rete aziendale anche se nessun utente ha eseguito l'accesso. Questa capacità è necessaria per garantire il corretto funzionamento delle seguenti funzioni di dominio Windows:
  
-   Profili utenti comuni
  
-   Impostazioni dei criteri di gruppo del computer (in particolare gli script di avvio e il software distribuito)
  
-   Script di accesso utente e software distribuito mediante i criteri di gruppo
  
##### Alternativa 1—Rifiuto della tecnologia WLAN
  
La soluzione più ovvia per risolvere i problemi di protezione delle reti LAN senza fili è quella di evitarli completamento non distribuendo alcuna rete LAN senza fili. Oltre a non poter usufruire dei vantaggi delle WLAN delineati in questo documento, questa strategia non è del tutto priva di problemi. Le organizzazioni che adottano questo approccio devono affrontare quello che META Group definisce il "Price of Postponement" (conseguenze del rinvio) che non si limitano ai costi di un mancato guadagno. Lo studio di META Group è basato sull'analisi della crescita esponenziale che l'uso delle reti LAN cablate ha riscontrato in molte organizzazioni circa dieci anni addietro. Nella maggior parte dei casi i reparti IT centrali furono costretti a intervenire e riprendere in mano la situazione. Il costo legato alla riorganizzazione delle numerose LAN di reparto, indipendenti e spesso incompatibili, fu ingente. Per ulteriori informazioni, vedere l'articolo "How Do I Limit My Exposure Against the Wireless LAN Security Threat? The New Realities of Protecting Corporate Information", pubblicato da META Group il 18/12/2002.
  
Questo stesso pericolo si è ripresentato per le reti WLAN, soprattutto nelle organizzazioni di grandi dimensioni in cui è spesso impossibile vedere fisicamente ciò che accade in ogni ubicazione. Una distribuzione estesa e non gestita di reti WLAN, resa possibile dai costi estremamente bassi dei componenti, rappresenta potenzialmente lo scenario peggiore poiché espone l'organizzazione a tutti i rischi per la sicurezza delineati precedentemente, senza che il gruppo IT centrale se ne renda conto o sia in grado di intervenire per affrontarli.
  
Questo implica che, se la strategia dell'utente è quella di non adottare la tecnologia di rete WLAN, è necessario implementare questa strategia in modo attivo, anziché passivo. Questa decisione deve essere sostenuta con una politica chiaramente divulgata in modo da garantire che tutti i dipendenti siano ben informati su di essa e sulle conseguenze derivanti dalla sua violazione. Si consiglia inoltre di utilizzare strumenti di scansione e controlli dei pacchetti di rete per individuare l'uso illegale di apparecchiature senza fili nella rete.
  
##### Alternativa 2—Utilizzo della protezione di base 802.11 (WEP statico)
  
La protezione di base 802.11 (WEP statico) si avvale di una chiave condivisa per controllare l'accesso alla rete e utilizza la stessa chiave per crittografare il traffico senza fili. Questo semplice modello di autorizzazione è spesso integrato dall'applicazione di filtri alle porte sulla base degli indirizzi hardware della scheda di rete WLAN, sebbene questa soluzione non faccia parte dello standard 802.11. Il punto di forza principale di questo approccio è la sua semplicità. Sebbene fornisca un livello di protezione sulla rete WLAN non protetta, questo approccio presenta seri svantaggi di gestione e di protezione, in particolare in relazione alle organizzazioni di grandi dimensioni.
  
Gli svantaggi della soluzione WEP includono i seguenti aspetti:
  
-   Le chiavi WEP statiche possono essere scoperte in poche ore in una rete con traffico elevato utilizzando un PC con una scheda di rete WLAN e strumenti di pirateria informatica facilmente disponibili, come ad esempio Airsnort o WEPCrack.
  
-   Il problema più importante della protezione WEP è la mancanza di un meccanismo per l'assegnazione o l'aggiornamento dinamici della chiave di crittografia di rete. Senza il supporto di 802.1X e EAP per l'esecuzione di aggiornamenti regolari della chiave, l'algoritmo di crittografia utilizzato da WEP è vulnerabile agli attacchi di individuazione della chiave descritti in precedenza.
  
-   Le chiavi statiche possono essere modificate, ma questa operazione viene in genere eseguita manualmente nei punti di accesso e nei client senza fili, risultando quindi poco efficace. Inoltre, l'aggiornamento della chiave deve essere effettuato contemporaneamente nei client e nei punti di accesso per impedire l'interruzione della connessione del client. In pratica, questo processo è talmente complesso che le chiavi restano spesso invariate.
  
-   La chiave statica deve essere condivisa tra tutti gli utenti della WLAN e tutti i punti di accesso senza fili. Ma un segreto condiviso da un gran numero di persone è molto difficile che resti effettivamente segreto a lungo.
  
Il WEP fornisce alle reti WLAN un meccanismo di controllo dell'accesso molto limitato basato sulla conoscenza della chiave WEP. Quindi se si scopre il nome della rete, operazione molto semplice, o della chiave WEP, sarà possibile collegarsi alla rete.
  
Un metodo per migliorare la protezione è quello di configurare i punti di accesso senza fili in modo che questi consentano la connessione solo ad un insieme predefinito di indirizzi delle schede di rete client. Questo è comunemente noto come filtraggio dell'indirizzo MAC (Media Access Control): il livello MAC fa riferimento al firmware di basso livello della scheda di rete.
  
Tuttavia, anche il filtraggio dell'indirizzo della scheda di rete se utilizzato come controllo dell'accesso comporta una serie di problemi:
  
-   Scarsa gestibilità. È alquanto difficile gestire un elenco di indirizzi hardware per un elevato numero di client. Inoltre, anche la distribuzione e la sincronizzazione di questo elenco tra tutti i punti di accesso risulta un compito arduo.
  
-   Scalabilità limitata. I punti di accesso possono presentare una limitazione delle dimensioni della tabella dei filtri, restringendo il numero di client supportabili.
  
-   Non esiste alcun metodo per associare un indirizzo MAC ad un nome utente, per cui l'autenticazione può essere effettuata solo in relazione all'identità del computer e non dell'utente.
  
-   Un intruso potrebbe eseguire lo spoof dell'indirizzo MAC "consentito". Se questi è in grado di scoprire un indirizzo MAC legittimo, potrebbe facilmente utilizzare tale indirizzo, invece di quello prefissato della scheda di rete.
  
Le soluzioni con chiave già condivisa sono adatte solo a un numero ridotto di utenti e punti di accesso a causa della difficoltà nel gestire l'aggiornamento delle chiavi in più ubicazioni. Le imperfezioni crittografiche di WEP ne mettono in dubbio l'utilità anche in ambienti di dimensioni molto ridotte.
  
La modalità WPA con chiave già condivisa, tuttavia, garantisce un livello di protezione sufficiente con un sovraccarico di infrastruttura molto ridotto per le piccole organizzazioni. Inoltre, lo schema WPA PSK è supportato da un'ampia gamma di componenti hardware e i client WLAN possono essere configurati manualmente. Questa configurazione può essere considerata la soluzione ideale per gli ambienti SOHO.
  
##### Alternativa 3—Reti private virtuali
  
Le reti VPN rappresentano probabilmente la forma più comune di crittografia. In molti si affidano alla consolidata e affidabile tecnologia VPN per proteggere la riservatezza dei dati inviati tramite Internet. Quando vennero individuate le vulnerabilità del WEP statico, le reti VPN furono immediatamente proposte come la soluzione *ideale* per proteggere i dati trasmessi in una rete WLAN. Questo approccio è stato avallato da molti analisti come il Gartner Group e, come era immaginabile, è stato entusiasticamente promosso dai fornitori di soluzioni VPN.
  
La tecnologia VPN costituisce una soluzione eccellente per attraversare senza rischi una rete ostile come Internet, sebbene la qualità delle implementazioni VPN sia spesso variabile. Tuttavia, non è necessariamente la soluzione migliore per proteggere le reti LAN senza fili interne. Per questo tipo di applicazione, una VPN non offre vantaggi significativi in termini di protezione rispetto alle soluzioni 802.1X, mentre incrementa nettamente la complessità e i costi, riducendo l'utilizzabilità e rendendo inutilizzabili alcune funzionalità importanti.
  
**Nota:** questo aspetto è diverso dall'utilizzo delle reti VPN per proteggere il traffico nei punti strategici delle LAN pubbliche senza fili. Le VPN possono essere utilizzate efficacemente per proteggere i dati di rete degli utenti che si connettono tramite reti remote pericolose. In questo tipo di scenario gli utenti si aspettano che la connessione protetta sia più intrusiva e meno funzionale di una connessione LAN, ma non si aspettano tutto ciò all'interno del perimetro dell'azienda.
  
I vantaggi legati all'utilizzo delle reti VPN per proteggere le reti LAN senza fili includono i seguenti aspetti:
  
-   Nella maggior parte delle organizzazioni è già presente una rete VPN, quindi gli utenti e il personale IT ha già dimestichezza con la soluzione.
  
-   Poiché la protezione dei dati VPN in genere si basa sulla crittografia software, la modifica e l'aggiornamento degli algoritmi risultano più rapide rispetto alla crittografia basata sull'hardware.
  
-   È possibile utilizzare componenti hardware meno costosi in quanto la protezione VPN è indipendente dall'hardware WLAN (anche se il prezzo dell'hardware conforme allo standard 802.1X è tutt'altro che insignificante).
  
Gli svantaggi dell'utilizzo delle reti VPN al posto della protezione WLAN nativa includono:
  
-   Le VPN richiedono l'intervento costante dell'utente. I client VPN in genere richiedono l'intervento manuale dell'utente per avviare la connessione al server VPN. Di conseguenza, la connessione non risulterà mai trasparente come nel caso di una connessione a una LAN cablata. Nei client VPN non Microsoft possono essere richieste credenziali di accesso al momento della connessione oltre alle normali informazioni di accesso alla rete o al dominio. Se la connessione alla rete VPN si interrompe, a causa di un segnale WLAN insufficiente o perché l'utente si sposta tra i diversi punti di accesso, l'utente dovrà ripetere la connessione.
  
-   Poiché la connessione alla rete VPN può essere avviata solo dall'utente, un computer inattivo non verrà connesso alla VPN e, quindi alla rete LAN aziendale. Di conseguenza non sarà possibile gestire in remoto o controllare un computer a meno che non sia utilizzato da un utente. Analogamente, alcune impostazioni degli oggetti Criteri di gruppo di un computer, come gli script di avvio e il software assegnato al computer non verranno applicati.
  
-   I profili comuni, gli script di accesso e il software distribuito all'utente mediante gli oggetti Criteri di gruppo potrebbero non funzionare come previsto. A meno che l'utente non scelga di accedere tramite la connessione VPN dal prompt di accesso a Windows, il computer non si connetterà alla LAN aziendale fino a quando l'utente non avrà completato l'accesso e avviato la connessione VPN. Qualsiasi tentativo di proteggere la rete prima che l'utente abbia completato queste operazioni avrà esito negativo. Con un client VPN non Microsoft, potrebbe risultare impossibile eseguire un accesso completo al dominio tramite una connessione VPN.
  
-   Se il computer viene riattivato dalle modalità di standby o sospensione, la connessione alla VPN non viene ristabilita automaticamente. Dovrà essere ristabilita manualmente dall'utente.
  
-   Sebbene i dati all'interno del tunnel VPN siano protetti, la rete VPN non offre alcuna protezione per quanto riguarda la rete WLAN. Un intruso può accedere alla WLAN e tentare di sondare o attaccare qualsiasi dispositivo a essa connesso.
  
-   Il server VPN può diventare un collo di bottiglia. L'accesso di tutti i client WLAN alla rete LAN aziendale passa attraverso il server VPN. Le periferiche VPN in genere supportano un gran numero di client remoti a bassa velocità. di conseguenza, la maggior parte dei gateway VPN non sarà in grado di supportare decine o centinaia di client alla velocità effettiva della rete LAN.
  
-   Il costo dell'hardware aggiuntivo e della gestione costante delle periferiche VPN risulterà probabilmente molto più alto rispetto a una soluzione WLAN nativa. Ogni sito richiederà un server VPN specifico in aggiunto ai punti di accesso WLAN.
  
-   Le sessioni VPN sono più soggette a disconnessioni quando i client si spostano tra i punti di accesso. Sebbene le applicazioni spesso siano in grado di tollerare una disconnessione momentanea durante il passaggio tra i punti di accesso senza fili, in questi casi le sessioni VPN vengono spesso interrotte e l'utente dovrà riavviarle manualmente.
  
-   Il costo di una licenza software per server e client VPN, insieme al costo della distribuzione del software, può costituire un problema nel caso di soluzioni VPN non Microsoft. Altri aspetti problematici possono riguardare la compatibilità del software client VPN poiché i client non Microsoft spesso sostituiscono funzionalità essenziali di Windows.
  
-   Molti analisi e fornitori ritengono che la protezione VPN sia in ogni caso migliore rispetto alla protezione delle reti WLAN. Sebbene ciò possa essere vero per il WEP statico, non lo è necessariamente per le soluzioni basate su EAP 802.1X descritte in questo documento. In particolare, i metodi di autenticazione VPN sono spesso molto *meno* sicuri e, in ogni caso, nella migliore delle ipostesi non sono nettamente più affidabili. Ad esempio, le soluzioni WLAN supportate da Microsoft utilizzano esattamente gli stessi metodi di autenticazione EAP adottati dalle soluzioni VPN (EAP-TLS e MS-CHAP v2). Molte implementazioni VPN, in particolare quelle basate sulla modalità di tunnel IPsec, utilizzano l'autenticazione con chiave già condivisa (una password di gruppo). Questa soluzione è stata ampiamente screditata e sono stati evidenziati gravi problemi a livelli di protezione, di cui molti sono comuni al WEP statico.
  
-   Una rete VPN non prevede alcun tipo di protezione per la rete WLAN. Sebbene i dati all'interno dei tunnel VPN siano protetti, chiunque può collegarsi alla WLAN e tentare di attaccare client senza fili autorizzati e altri dispositivi della WLAN.
  
Le reti VPN sono particolarmente adatte a proteggere il traffico di reti pericolose, ovvero se l'utente si connette da una connessione a banda larga dalla propria abitazione o da un'area sensibile senza fili. In ogni caso, la rete VPN non è mai stata progettata per proteggere il traffico delle reti interne. Per molte organizzazioni l'utilizzo della VPN con queste funzioni risulterebbe troppo difficile e limitato per l'utente in termini di funzioni e, allo stesso tempo, troppo costoso e complesso per poter essere gestito in modo efficace dal reparto IT.
  
Nei rari casi in cui è richiesto un livello di protezione maggiore per una connessione o un tipo di traffico particolare, è possibile utilizzare un tunnel VPN o la modalità di trasporto IPsec *in aggiunta* alla protezione WLAN nativa. In questo modo le risorse di rete vengono utilizzate in modo più efficace.
  
##### Alternativa 4—Protezione IP
  
Il protocollo IPsec consente a due parti di pari livello in una rete di autenticarsi a vicenda e di autenticare o crittografare singoli pacchetti di rete. È possibile utilizzare IPsec per accedere in modo protetto a una rete tramite un'altra rete o semplicemente per proteggere i pacchetti IP trasmessi tra due computer.
  
Il tunnel IPsec è solitamente utilizzato nell'accesso client o nelle connessioni VPN tra sedi. La modalità di tunnel IPsec è un tipo di VPN basato sull'incapsulamento di un intero pacchetto IP all'interno di un pacchetto IPsec protetto. Ciò aggiunge un sovraccarico alla comunicazione, come per altre soluzioni VPN, che non è necessario per le comunicazioni tra sistemi della stessa rete. I vantaggi e gli svantaggi della modalità di tunnel IPsec sono stati esaminati nella sezione precedente dedicata alle reti VPN.
  
È anche possibile utilizzare IPsec per proteggere il traffico end-to-end tra due computer (senza tunneling) mediante la *modalità di trasporto*. Analogamente alla VPN, IPsec è una soluzione eccellente in molti casi, anche se, come risulterà chiaro in questa sezione, non può sostituire la protezione WLAN nativa implementata a livello dell'hardware.
  
Tra i vantaggi della modalità di trasporto IPsec vi sono i seguenti aspetti:
  
-   Non è richiesto l'intervento dell'utente. Diversamente dalle VPN, non sono richieste procedure di accesso particolari.
  
-   La protezione IPsec è indipendente dall'hardware WLAN e richiede solo una rete WLAN aperta, non autenticata. Diversamente dalle VPN, non sono richiesti server o dispositivi aggiuntivi poiché la protezione è negoziata direttamente tra i computer in comunicazione.
  
-   L'uso di algoritmi di crittografia non è vincolato dall'hardware WLAN.
  
Tra gli svantaggi dell'utilizzo di IPSec al posto della protezione WLAN nativa vi sono i seguenti aspetti:
  
-   IPSec utilizza solo l'autenticazione a livello di computer; non esiste alcun altro metodo per implementare uno schema di autenticazione basato sull'utente. Per molte organizzazioni questo non costituisce un problema, tuttavia, un utente *non autorizzato* che riesca ad accedere a un computer *autorizzato* potrà connettersi ad altri computer della rete protetti tramite IPSec.
  
    **Nota:** alcune implementazioni IPSec sulle piattaforme non Windows utilizzano solo l'autenticazione utente. Tuttavia, analogamente alle soluzioni VPN, il computer non è connesso alla rete quando l'utente non ha effettuato l'accesso, quindi alcune operazioni di gestione saranno impedite e le funzionalità delle impostazioni utente saranno disabilitate.
  
-   La gestione dei criteri IPSec potrebbe risultare complessa per le organizzazioni di grandi dimensioni. Il tentativo di applicare la protezione generale del traffico IP potrebbe interferire con gli usi più specializzati dell'IPSec dove la protezione end-to-end è richiesta.
  
-   La protezione avanzata richiede di crittografare tutto il traffico end-to-end, ma alcune periferiche non sono in grado di supportare IPSec. Questo impone la trasmissione in chiaro del traffico a queste periferiche. IPsec non fornisce alcuna protezione per queste periferiche, che saranno quindi esposte a chiunque si connetta alla rete WLAN.
  
-   Poiché la protezione IPSec viene applicata a livello di rete anziché a livello MAC, non è completamente trasparente a dispositivi di rete come i firewall. Alcune implementazioni IPSec non funzioneranno attraverso un dispositivo di rete NAT (Network Address Translation).
  
-   Le soluzioni IPSec end-to-end non possono proteggere il traffico broadcast o multicast poiché IPsec è basato sull'autenticazione reciproca e lo scambio di chiavi tra due parti.
  
-   Sebbene i dati all'interno dei pacchetti IPsec siano protetti, la rete WLAN non lo è. Di conseguenza un intruso può collegarsi alla WLAN e tentare di sondare o attaccare qualsiasi dispositivo a essa connesso o intercettare tutto il traffico non protetto tramite IPsec.
  
-   I processi di crittografia e decrittografia del traffico di rete IPsec determinano un utilizzo eccessivo della CPU del computer. Questo può sovraccaricare i server maggiormente utilizzati. Sebbene questo sovraccarico di elaborazione possa essere delegato a schede di rete specializzate, esse in genere non sono predefinite.
  
Analogamente alla tecnologia VPN, IPsec costituisce una soluzione eccellente per numerosi scenari di protezione ma non include la protezione delle reti WLAN né la protezione WLAN nativa.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Selezione delle opzioni appropriate per le reti LAN senza fili
  
Dall'argomento trattato in precedenza dovrebbe risultare chiaro che una soluzione WLAN 802.1X è di gran lunga la migliore delle alternative disponibili. Tuttavia, come è evidenziato nella sezione "Protezione di una rete LAN senza fili", dopo aver scelto di utilizzare una soluzione 802.1X è necessario decidere quali opzioni debbano costituire la soluzione.
  
Le due decisioni principali sono:
  
-   Se utilizzare password o certificati per autenticare gli utenti e i computer.
  
-   Se utilizzare WEP dinamico o la protezione dei dati della WLAN WPA.
  
Questi due aspetti sono indipendenti.
  
Come è stato illustrato in precedenza, Microsoft ha rilasciato due guide sulle soluzioni di protezione per reti LAN senza fili: in una è stata utilizzata l'autenticazione con password e nell'altra l'autenticazione con certificati. Queste soluzioni funzionano correttamente sia con WEP dinamico che con WPA.
  
#### Scelta della soluzione appropriata di protezione della rete LAN senza fili
  
Nel diagramma che segue sono riepilogati i passaggi della scelta tra le due soluzioni di protezione per reti LAN senza fili.
  
[![](images/Dd536242.PEAP_i02(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536242.peap_i02_big(it-it,technet.10).gif)
  
**Figura 2: Struttura decisionale per la soluzione per la protezione di reti LAN senza fili**
  
L'esito di questa scelta dipende dalle dimensioni e dai requisiti specifici dell'organizzazione. La maggior parte delle organizzazioni è in grado di utilizzare una delle due soluzioni WLAN Microsoft senza richiedere alcuna modifica. Ad esempio, la maggior parte delle organizzazioni di piccola o media grandezza sceglieranno la soluzione di autenticazione più semplice basata sulle password, descritta nella guida *Protezione delle reti LAN senza fili con PEAP e password*. Le organizzazioni più grandi tendono in genere a utilizzare la *soluzione* basata su certificati digitali descritta in *Securing Wireless LANs—A Windows Server 2003 Certificate Services*.
  
Sebbene ogni soluzione sia stata progettata per questi tipi di destinatari, è previsto un ampio margine di azione in entrambe le soluzioni. *Protezione delle reti LAN senza fili con PEAP e password* può essere distribuita da organizzazioni che gestiscono poche decine di utenti a organizzazioni con svariate migliaia di utenti. *La soluzioneSecuring Wireless LANs—A Windows Server 2003 Certificate Services* è applicabile a organizzazioni con poche centinaia o decine di migliaia di utenti (le organizzazioni con meno di 500 utenti in genere non dispongono delle risorse IT sufficienti per distribuire e gestire autorità di certificazione).
  
In nessuna delle due guide è esaminato un caso comune: grandi organizzazioni che distribuiscono soluzioni WLAN basate su password. Sebbene le specifiche tecniche della soluzione *Protezione delle reti LAN senza fili con PEAP e password* possano essere applicate in egual modo a imprese grandi e piccole, gran parte delle fasi di progettazione, pianificazione e utilizzo richieste dalle organizzazioni più grandi sono state omesse per maggiore semplicità. Fortunatamente, l'analogia dei componenti architettonici e tecnici utilizzati in entrambe le soluzioni consente di scambiare le parti delle soluzioni con relativa facilità. La soluzione *Protezione delle reti LAN senza fili con PEAP e password* include un'appendice in cui sono fornite indicazioni sulle parti rilevanti di ogni soluzione.
  
#### Scelta tra WEP dinamico e WPA
  
La protezione dei dati WEP, se combinata con l'autenticazione avanzata e l'aggiornamento dinamico delle chiavi fornito da 802.1X e EAP, offre un livello di protezione più che adeguato per la maggior parte delle organizzazioni. Tuttavia, lo standard WPA introduce un ulteriore miglioramento e offre livelli di protezione ancora più avanzati.
  
Le differenze tra l'utilizzo di WPA e del WEP dinamico nelle due soluzioni sono minime e la migrazione da un ambiente WEP dinamico a un ambiente WPA è estremamente semplice. Le principali modifiche nel passaggio dal WEP dinamico a WPA sono:
  
-   Se l'hardware di rete, ovvero i punti di accesso e le schede di rete senza fili, non supportano la protezione WPA, è necessario ottenere e distribuire appositi aggiornamenti firmware. Gli aggiornamenti del firmware per le schede di rete senza fili sono spesso inclusi negli aggiornamenti dei driver di rete.
  
-   È necessario abilitare WPA nei punti di accesso senza fili.
  
-   La configurazione dei client WLAN deve essere modificata per negoziare la protezione WPA anziché quella WEP.
  
-   Il periodo di timeout della sessione nel criterio di accesso remoto IAS (Internet Authentication Service), utilizzato per imporre l'aggiornamento della chiave WEP, deve essere incrementato per ridurre il carico sul server IAS.
  
    **Nota:** il servizio IAS costituisce l'implementazione Microsoft del server RADIUS ed è incluso in Windows Server 2003, ma non viene installato per impostazione predefinita.
  
La protezione WPA, se disponibile, dovrebbe essere la prima scelta. Tuttavia, è necessario valutare se uno dei seguenti aspetti può rendere problematico l'uso di WPA:
  
-   L'hardware di rete potrebbe non supportare ancora WPA. Ciò accade raramente con i nuovi dispositivi, ma potrebbe essere già disponibile un'ampia base di hardware precedente a WPA.
  
-   Il supporto per le impostazioni controllate dagli oggetti Criteri di gruppo è disponibile solo nel SP1 di Windows Server 2003 (previsto nel corso del 2004). Le versioni precedenti non includono questo supporto e le impostazioni WPA devono essere configurate manualmente nei client Windows XP.
  
-   WPA potrebbe non essere supportato da tutti i client; ad esempio, in Windows 2000 e versioni precedenti e Pocket PC attualmente non è incorporato il supporto per WPA.
  
Se si conclude che non sussistono ancora le premesse per distribuire WPA, è consigliabile distribuire una soluzione WEP dinamica e pianificare la migrazione a WPA quando le circostanze lo permetteranno.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questo documento dovrebbe avervi fornito tutte le informazioni necessarie per determinare la strategia di protezione della rete LAN senza fili. La prima parte del documento ha esaminato i vantaggi per le imprese delle reti senza fili e i pericoli che corrono le reti LAN non protette in modo adeguato. Nella sezione centrale è stato esaminato il modo in cui la protezione delle reti LAN senza fili basata su 802.1X, EAP e la protezione avanzata dei dati costituisce una soluzione efficace per combattere tali minacce. Sono stati evidenziati anche i meriti parziali di alcune alternative come le reti VPN, IPsec e WEP statico. Nella sezione finale sono state fornite indicazioni sul quali opzioni di protezione WLAN selezionare e quali delle soluzioni Microsoft di protezione delle WLAN potrebbe essere più adatta alle esigenze della propria organizzazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riferimenti
  
Questa sezione contiene rimandi a informazioni supplementari importanti e ad altro materiale attinente al contenuto di questo documento.
  
-   La soluzione Microsoft *Protezione delle reti LAN senza fili con PEAP e password* è disponibile al seguente URL:
  
    [http://go.microsoft.com/fwlink/?LinkId=23459](http://go.microsoft.com/fwlink/?linkid=23459)
  
-   La soluzione Microsoft *Securing Wireless LANs—A Windows Server 2003 Certificate Services Solution* è disponibile al seguente URL:
  
    [http://go.microsoft.com/fwlink/?LinkId=14843](http://go.microsoft.com/fwlink/?linkid=14843) (in inglese).
  
-   Per ulteriori informazioni tecniche su IEEE 802.11 e le tecnologie correlate, vedere la sezione "802.11 Wireless" della documentazione tecnica su Windows Server 2003 disponibile al seguente URL:
  
    [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    proddocs//w2k3tr\_wir\_intro.mspx](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/techref/w2k3tr_wir_intro.mspx) (in inglese).
  
-   Per ulteriori informazioni sullo standard 802.11, vedere la pagina Web relativa a IEEE 802.11 al seguente indirizzo URL:
  
    <http://www.ieee802.org/11/> (in inglese).
  
-   Per ulteriori informazioni sullo standard 802.1X, vedere la pagina Web relativa a IEEE 802.1X al seguente indirizzo URL:
  
    <http://www.ieee802.org/1/pages/802.1x.html> (in inglese).
  
-   Per ulteriori informazioni sullo standard EAP, consultare RFC 2284 al seguente URL:
  
    <http://www.ietf.org/rfc/rfc2284.txt?number=2284> (in inglese).
  
-   Per ulteriori informazioni sull'utilizzo delle reti senza fili, visitare il sito Microsoft specifico al seguente URL:
  
    <http://www.microsoft.com/wifi> (in inglese).
  
-   Per una spiegazione dettagliata dello standard PEAP e delle differenze rispetto a LEAP (e anche a EAP-TLS e EAP-MD5), vedere l'articolo "The Advantages of Protected Extensible Authentication Protocol (PEAP): A Standard Approach to User Authentication for IEEE 802.11 Wireless Network" disponibile al seguente URL:
  
    [http://www.microsoft.com/windowsserver2003/techinfo/  
    overview/peap.mspx](http://www.microsoft.com/windowsserver2003/techinfo/overview/peap.mspx) (in inglese).
  
**Scarica la soluzione completa**
  
[Protezione delle reti LAN senza fili con PEAP e password](http://go.microsoft.com/fwlink/?linkid=23481)
  
[](#mainsection)[Inizio pagina](#mainsection)
