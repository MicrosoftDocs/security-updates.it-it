---
TOCTitle: Monitoraggio della protezione e identificazione degli attacchi
Title: Monitoraggio della protezione e identificazione degli attacchi
ms:assetid: 'a30af90e-ce18-47fc-a947-11f332ee4731'
ms:contentKeyID: 20213178
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc875806(v=TechNet.10)'
---

Monitoraggio della protezione e identificazione degli attacchi
==============================================================

##### In questa pagina

[](#egaa)[Introduzione](#egaa)
[](#efaa)[Definizione](#efaa)
[](#eeaa)[Le sfide per le aziende di medie dimensioni](#eeaa)
[](#edaa)[Soluzioni](#edaa)
[](#ecaa)[Riepilogo](#ecaa)
[](#ebaa)[Appendice A: Esclusione degli eventi non necessari](#ebaa)
[](#eaaa)[Appendice B: Implementazione delle impostazioni di Criteri di gruppo](#eaaa)

### Introduzione

Questo documento è contenuto nella raccolta di indicazioni per la protezione delle aziende di medie dimensioni. Microsoft si augura che le informazioni in esso contenute possano contribuire a creare ambienti informatici più sicuri e produttivi.

#### Riepilogo

I numerosi casi di minacce da software dannoso e gli incidenti che hanno dominato per anni il settore dei media sono serviti ad accrescere la consapevolezza del problema e a spingere la maggior parte delle aziende a investire tempo e risorse nella difesa contro questo diffuso problema di protezione. La minaccia più grande all'infrastruttura aziendale, tuttavia, potrebbe non essere costituita da un attacco proveniente dall'esterno, ad esempio un virus, ma risiedere nella stessa rete interna.

Gli attacchi lanciati dall'interno di una rete aziendale presentano un potenziale di danneggiamento molto alto, specialmente se eseguiti da personale che ricopre incarichi di fiducia che ha accesso a tutte le risorse di rete dell'azienda. Una volta esaminati attentamente i rischi posti sia dalle minacce esterne che da quelle interne, molte aziende decidono di avvalersi di sistemi in grado di monitorare le reti e rilevare gli attacchi provenienti da qualsiasi origine.

Per le aziende sottoposte a restrizioni normative, le procedure per il monitoraggio della protezione non sono un'opzione, bensì un requisito. Queste normative possono controllare perfino per quanto tempo e in che modo debbano essere conservati e archiviati i record relativi al monitoraggio della protezione. La continua evoluzione delle normative e il numero sempre più elevato di requisiti che le aziende controllate devono soddisfare per rendere sicure le loro reti, tenere traccia delle persone che accedono alle risorse e proteggere le informazioni private richiedono a tali aziende, in tutto il mondo, l'adozione di soluzioni efficaci per il monitoraggio della protezione.

Diversi sono i motivi per cui il monitoraggio della protezione e l'identificazione degli attacchi debbano riguardare da vicino anche le aziende di medie dimensioni che non necessitano di conformarsi ad alcun requisito di legge. Questi motivi includono le conseguenze a cui potrebbe andare incontro un'azienda qualora dovesse riuscire un attacco alla sua infrastruttura. Non solo potrebbero essere danneggiate le attività aziendali con le conseguenti mancanza di produttività e perdita monetaria, ma l'azienda potrebbe anche perdere la propria reputazione e, spesso, il tempo necessario a riguadagnare la propria reputazione è maggiore di quello richiesto per rimediare alle altre perdite che un attacco può causare.

Le funzionalità del registro di protezione disponibili in Microsoft Windows possono rappresentare il punto di partenza per una soluzione di monitoraggio della protezione. Tuttavia, i registri di protezione da soli non forniscono informazioni sufficienti per pianificare le risposte agli incidenti. Questi registri di protezione possono essere combinati con altre tecnologie che raccolgono e interrogano tali informazioni per formare il nucleo di una soluzione completa per il monitoraggio della protezione e l'identificazione degli attacchi.

L'obiettivo principale di un sistema di monitoraggio della protezione e identificazione degli attacchi consiste nel rilevare all'interno di una rete gli eventi sospetti che possono indicare attività dannose o errori procedurali. Questo documento descrive come sviluppare un piano per creare questo tipo di sistema nelle reti basate su Windows. Inoltre, fornisce istruzioni su come implementare, gestire e convalidare tale sistema.

#### Panoramica

Questo documento è costituito da quattro sezioni principali che illustrano i concetti e i temi essenziali per progettare e implementare una soluzione per il monitoraggio della protezione e l'identificazione degli attacchi che sia completa ed efficace. La prima sezione è costituita dalla presente "Introduzione". Le altre sezioni sono:

##### Definizione

In questa sezione vengono fornite informazioni utili per comprendere il processo di generazione e applicazione della soluzione presentata in questo documento.

##### Le sfide per le aziende di medie dimensioni

In questa sezione vengono illustrate le sfide a cui vanno incontro le aziende di medie dimensioni che devono adottare un sistema di monitoraggio della protezione e identificazione degli attacchi.

##### Soluzioni

In questa sezione, composta da due sottosezioni, vengono fornite informazioni dettagliate su come sviluppare, implementare, gestire e convalidare la soluzione presentata in questo documento. In "Sviluppo della soluzione" vengono illustrate le attività preliminari e i passaggi della pianificazione. In "Distribuzione e gestione della soluzione" vengono fornite informazioni utili per distribuire, gestire e convalidare un sistema di monitoraggio della protezione e identificazione degli attacchi.

#### Destinatari del documento

Questo documento illustra le problematiche legate alla privacy e alla sicurezza per le aziende di medie dimensioni, specialmente per quelle tenute alla protezione delle identità e ai controlli sull'accesso ai dati perché soggette a vincoli normativi. I destinatari di questo documento rientrano quindi nei profili che vanno dai manager/responsabili tecnici ai professionisti IT e agli implementatori di tecnologie che si occupano della pianificazione, della distribuzione, del funzionamento e, soprattutto, della protezione di una rete aziendale.

Sebbene alcune parti di questo documento siano utili per la maggior parte dei responsabili tecnici, è opportuno che i lettori abbiano familiarità con i problemi di protezione e i rischi relativi al proprio ambiente di rete e con i concetti legati ai servizi di registrazione degli eventi di Windows.

[](#mainsection)[Inizio pagina](#mainsection)

### Definizione

Questo documento utilizza il modello di elaborazione MOF (Microsoft Operations Framework) oltre alle funzioni SMF di gestione degli eventi e di amministrazione della protezione MOF.

In particolare, la soluzione presentata in questo documento consiglia l'uso di un approccio che prevede un processo continuo anziché di un approccio di distribuzione lineare al monitoraggio della protezione e all'identificazione degli attacchi. Nello specifico, questa soluzione è basata sui passaggi mostrati nella figura che segue:

![](images/Cc875806.SMAAD1(it-it,TechNet.10).gif)

**Figura 1. Applicazione di MOF**

Una soluzione di monitoraggio della protezione è effettivamente un processo continuo di pianificazione, implementazione, gestione e test, poiché questa è la vera natura del monitoraggio della protezione. Dal momento che le minacce alle reti aziendali cambiano continuamente, anche il sistema che monitora la protezione in una rete aziendale deve cambiare.

L'applicazione di questo processo per il monitoraggio della protezione si adatta a Security Management SMF, che tenta di effettuare quanto segue:

-   Valutare l'esposizione dell'azienda e identificare le risorse da proteggere.

-   Identificare i modi per ridurre i rischi a livelli accettabili.

-   Progettare un piano per attenuare i rischi di protezione.

-   Monitorare l'efficienza dei meccanismi di protezione.

-   Rivalutare regolarmente l'efficacia e i requisiti di protezione.

Per ulteriori informazioni su MOF, visitare il sito Web [Microsoft Operations Framework](http://www.microsoft.com/mof) (in inglese) all'indirizzo www.microsoft.com/mof. Per ulteriori informazioni su [Security Management SMF](http://www.microsoft.com/technet/itsolutions/cits/mo/smf/mofsmsmf.mspx), visitare il sito Web www.microsoft.com/technet/itsolutions/cits/mo/smf/mofsmsmf.mspx (in inglese).

La gestione dei rischi è un processo che consiste nel determinare il livello di rischio accettabile per un'organizzazione, valutando i rischi correnti e individuando i modi per raggiungere tale livello di rischio e gestirlo. Sebbene questo documento tratti alcuni concetti di gestione dei rischi e illustri alcuni passaggi che possono essere di aiuto valutazione dei rischi, la gestione dei rischi costituisce un tema a sé stante e una discussione approfondita su questo argomento merita un discorso a parte. Per ulteriori informazioni sull'analisi e sulle valutazioni dei rischi, visitare il sito Web [*Guida alla gestione dei rischi di protezione*](http://technet.microsoft.com/it-it/library/cc163151) all'indirizzo http://go.microsoft.com/fwlink/?linkid=30794.

[](#mainsection)[Inizio pagina](#mainsection)

### Le sfide per le aziende di medie dimensioni

Le aziende di medie dimensioni che devono costruire un efficace sistema di monitoraggio della protezione e istituire i criteri alla base di questa iniziativa si trovano di fronte a numerose sfide. Queste sfide includono:

-   La capacità di comprendere la necessità e i vantaggi della protezione dell'intero ambiente di rete da minacce interne ed esterne.

-   La progettazione di un sistema di monitoraggio della protezione e identificazione degli attacchi che sia efficace e includa i metodi atti a rilevare e prevenire i tentativi di elusione dei criteri stabiliti.

-   L'implementazione di criteri di monitoraggio efficaci e completi che non soltanto consentano di rilevare gli attacchi ma forniscano anche un quadro complessivo del livello di protezione di un ambiente per suggerire eventuali interventi di correzione.

-   La gestione di criteri e processi che mettano efficientemente in correlazione i report sulla protezione con i criteri stabiliti per facilitare gli sforzi amministrativi nell'identificazione delle attività sospette.

-   L'implementazione e l'applicazione di procedure e criteri aziendali efficienti, atti a supportare gli sforzi di monitoraggio della protezione nel rispetto delle esigenze gestionali e commerciali.

-   La determinazione di soglie di rischio accettabili per bilanciare l'usabilità e l'attenuazione dei rischi.

[](#mainsection)[Inizio pagina](#mainsection)

### Soluzioni

Come indicato in precedenza, un processo completo di monitoraggio della protezione non è solo di aiuto per quanto riguarda la necessità di eseguire analisi forensi ma può anche essere una misura di protezione attiva in grado di fornire informazioni utili prima, durante e dopo un attacco. Impiegando un archivio centralizzato per i report sulla protezione, è possibile rilevare un attacco mentre viene provato, mentre si verifica e immediatamente dopo che si è verificato e offrire a chi deve rispondere a tale attacco le informazioni necessarie per reagire nel modo più efficace, riducendo l'impatto dei tentativi di intrusione.

Conoscere tutti i vantaggi che possono derivare dall'implementazione del monitoraggio della protezione è fondamentale nella fase di concettualizzazione dello sviluppo della soluzione e fa sì che la progettazione e i criteri possano beneficiarne. Alcuni dei vantaggi derivanti dal monitoraggio della protezione includono:

-   L'identificazione e l'aggiornamento dei sistemi non conformi ai criteri di aggiornamento o di protezione per ridurre il profilo di vulnerabilità di un'azienda di medie dimensioni.

-   La produzione di informazioni che possono avvisare il personale dei possibili tentativi di intrusione prima che si verifichi un attacco vero e proprio, identificando le attività insolite.

-   La creazione e la protezione di informazioni sul controllo della sicurezza ai fini di migliorare l'analisi forense, che non soltanto soddisfa i requisiti normativi ma riduce anche l'impatto di qualsiasi attacco che potrebbe verificarsi.

-   L'esecuzione di analisi del livello di protezione per migliorare la sicurezza globale.

-   L'identificazione delle attività che si verificano al di fuori dei processi aziendali consolidati, siano esse intenzionali o casuali.

-   L'identificazione dei sistemi non gestiti presenti in una rete oppure l'aggiornamento delle periferiche vulnerabili.

#### Sviluppo della soluzione

Il problema della protezione è importante per molte aziende. Sebbene la maggior parte di esse impegni un livello ragionevole di risorse nella protezione fisica utilizzando metodi che vanno dai normali lucchetti agli elaborati controlli di accesso basati su badge magnetici, molte non si adoperano ancora a sufficienza per proteggere i dati da cui sono sempre più dipendenti.

Quando poi la protezione dei dati e i problemi di monitoraggio riescono a catturare la loro attenzione, le società concentrano in genere i loro sforzi sulla protezione del perimetro della rete, con l'impiego di firewall. Ma questo tipo di approccio lascia altre vulnerabilità che possono diventare obiettivo di attacchi. Secondo il documento [2004 E-Crime Watch Survey](http://www.cert.org/archive/pdf/2004ecrimewatchsummary.pdf) (in inglese), pubblicato dai servizi segreti degli Stati Uniti insieme al CERT Coordination Center e disponibile all'indirizzo www.cert.org/archive/pdf/2004eCrimeWatchSummary.pdf, il 29% degli attacker identificati è risultato costituito da risorse interne, tra cui dipendenti, consulenti ed ex dipendenti. Considerando queste informazioni, risulta evidente la necessità di un approccio multilivello alla protezione, che consenta di salvaguardarsi contro le minacce sia interne che esterne.

Un metodo utilizzato per affrontare in modo reattivo le minacce sia interne che esterne consiste nell'implementare un processo di registrazione dei controllo di protezione. Per registrare gli eventi di protezione, tutte le versioni di Microsoft Windows, da Microsoft Windows NT 3.1 alle versioni attuali, utilizzano un registro predefinito degli eventi di protezione. Ma, anche se questa funzionalità predefinita può essere utilizzata da sola per eseguire un'analisi forense in risposta a un'intrusione già avvenuta, è difficile utilizzarla da sola in maniera attiva per identificare un'attività di attacco preliminare o per allertare il personale appropriato quando si verificano tentativi di intrusione.

Come già indicato, i registri di protezione vengono spesso utilizzati in modo reattivo durante l'analisi forense di un incidente dopo che questo si è verificato. Tuttavia, nel documento [2005 Insider Threat Study](http://www.cert.org/archive/pdf/insidercross051105.pdf)(in inglese), pubblicato dai servizi segreti degli Stati Uniti e dal CERT, disponibile all'indirizzo www.cert.org/archive/pdf/insidercross051105.pdf, un'analisi dei risultati dello studio ha rivelato che il monitoraggio e la registrazione della protezione possono essere utilizzati non solo per l'analisi forense reattiva, ma anche per l'identificazione attiva. Inoltre, la maggior parte degli attacker, sia interni che esterni, tentano di nascondere le proprie tracce alterando i registri. Pertanto devono essere prese delle misure per proteggere i registri degli eventi di sistema. I registri degli eventi di sistema e gli altri metodi utilizzati per monitorare e rilevare gli attacchi risultano essere quindi un'arma strategica dell'arsenale dedicato alla protezione della rete, sempre che siano correttamente utilizzati e protetti.

Sebbene i registri degli eventi di sistema siano l'argomento centrale di questo documento, essi costituiscono soltanto il nucleo della metodologia di monitoraggio della protezione e identificazione degli attacchi. Altre questioni che dovrebbero essere prese in considerazione includono l'identificazione e l'aggiornamento dei sistemi non conformi ai criteri di protezione stabiliti o privi delle patch di vulnerabilità consigliate. Anche l'infrastruttura della rete interna dovrebbe essere monitorata e il controllo deve includere la sicurezza delle porte di commutazione (per impedire che i sistemi non gestiti abbiano accesso alla rete) e il monitoraggio della protezione wireless (per impedire connessioni non autorizzate o lo sniffing dei pacchetti). Molti di questi argomenti relativi al monitoraggio non rientrano nell'ambito di questo documento, ma meritano un'attenzione particolare in ogni buona soluzione per il monitoraggio della protezione.

##### Implementazione del monitoraggio della protezione

Le sottosezioni che seguono contengono alcune considerazioni sull'implementazione di un sistema di monitoraggio della protezione.

###### Registrazione degli eventi di protezione di Windows

Tutte le versioni di Microsoft Windows, da Microsoft Windows NT versione 3.1 e successive, sono in grado di registrare gli eventi di protezione utilizzando la funzionalità predefinita dei file di registro. In un ambiente basato su Microsoft Windows, questa funzionalità è alla base del monitoraggio della protezione. Tuttavia, senza altre utilità o strumenti aggiuntivi in grado di correlare queste informazioni risulta difficile utilizzare attivamente tale funzionalità perché le informazioni vengono disperse.

[![](images/Cc875806.SMAAD2(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875806.smaad2_big(it-it,technet.10).gif)

**Figura 2. Registro di protezione del Visualizzatore eventi**

Il registro degli eventi di protezione (mostrato nella figura precedente) utilizza un formato di file personalizzato per registrare i dati sul monitoraggio della protezione. Sebbene sia possibile leggere parti di questi record con un normale editor di testo, per vedere tutte le informazioni registrate in questi file è necessario un programma quale il Visualizzatore eventi. Il file del registro degli eventi di protezione (SecEvent.evt) risiede nella directory %systemroot%\\System32\\config. L'accesso ai registri degli eventi viene sempre gestito tramite il servizio Registro eventi e tale servizio applica i controlli di accesso a ogni registro.  Le autorizzazioni predefinite per il registro di protezione sono molto limitate, se confrontate con quelle relative agli altri registri del sistema. Solo gli amministratori possono accedere al registro di protezione per impostazione predefinita.

Nel registro degli eventi di protezione vengono registrati due tipi di eventi: operazioni riuscite e operazioni non riuscite. Gli eventi relativi alle operazioni riuscite indicano un'operazione eseguita da un utente, un servizio o un programma è stata completata. Gli eventi relativi alle operazioni non riuscite forniscono i dettagli sulle operazioni non sono state completate. Ad esempio, i tentativi di accesso che gli utenti non riescono a portare a termine sono esempi di eventi relativi a operazioni non riuscite, quindi possono essere registrati nel registro degli eventi di protezione se sono abilitati i controlli di accesso.

Le impostazioni di Criterio controllo di Criteri di gruppo, sotto Configurazione computer\\Impostazioni di Windows\\Criteri locali, consentono di controllare quali eventi creano le voci nei registri di protezione. Le impostazioni di Criterio controllo possono essere configurate tramite la console Impostazioni protezione locale oppure, a livello di sito, dominio o unità organizzativa (OU), tramite Criteri di gruppo con Active Directory.

###### Interpretazione degli eventi di controllo

Gli eventi di controllo vengono illustrati in maniera molto dettagliata in tutto il documento, pertanto è importante acquisire una conoscenza di base della loro struttura e delle informazioni in essi contenute.

![](images/Cc875806.SMAAD3(it-it,TechNet.10).gif)

**Figura 3. Finestra Proprietà evento**

Gli eventi sono costituiti da tre parti fondamentali: l'intestazione dell'evento, la descrizione dell'evento e una sezione contente dati binari.

Nell'intestazione dell'evento sono presenti i seguenti campi:

**Tabella 1. Intestazione dell'evento**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>Definizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Data</td>
<td style="border:1px solid black;">La data in cui si è verificato l'evento.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Ora</td>
<td style="border:1px solid black;">L'ora locale in cui si è verificato l'evento.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Tipo</td>
<td style="border:1px solid black;">Una classificazione del livello di gravità dell'evento o del tipo di evento. Gli eventi di controllo della protezione sono del tipo Operazioni riuscite oppure Operazioni non riuscite.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Origine</td>
<td style="border:1px solid black;">L'applicazione che ha registrato l'evento. Può trattarsi di un programma vero e proprio, come SQL Server, di un nome di driver o di un componente del sistema, ad esempio Protezione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Categoria</td>
<td style="border:1px solid black;">La classificazione dell'evento in base all'origine dell'evento. Questo dato è importante nei registri di controllo della protezione poiché corrisponde a un tipo di evento che può essere configurato in Criteri di gruppo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ID dell'evento</td>
<td style="border:1px solid black;">Questo codice identifica lo specifico tipo di evento. Nella precedente figura, l'ID dell'evento è il 680, che indica che un insieme di credenziali è stato passato al sistema di autenticazione da un processo locale, un processo remoto o un utente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Utente</td>
<td style="border:1px solid black;">Il nome utente della persona per conto di cui si è verificato l'evento. Questo nome corrisponde all'ID del client se l'evento è stato causato da un processo o all'ID primario se non è presente alcuna rappresentazione. Negli eventi relativi alla sicurezza, se possibile e se applicabile, vengono visualizzate sia le informazioni sull'ID primario che le informazioni sulla rappresentazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Computer</td>
<td style="border:1px solid black;">Il nome del computer in cui si è verificato l'evento.</td>
</tr>
</tbody>
</table>
  
Il campo della descrizione dell'evento contiene di fatto una serie di informazioni che variano a seconda dell'evento. Ad esempio, nel caso dell'evento 680 mostrato nella precedente figura, il campo **Codice errore:** contiene **0xC000006A**, che significa che è stata fornita una password non valida. Per ogni tipo di evento vengono visualizzate in questo campo le informazioni specifiche dell'evento.
  
Per gli eventi del registro degli eventi di Protezione di Windows, non utilizzare la sezione dei dati binari del record degli eventi.
  
###### Problemi tecnici
  
Per implementare un sistema di monitoraggio della protezione e identificazione degli attacchi basato sulla registrazione degli eventi di Protezione di Windows, è necessario risolvere i seguenti problemi:
  
-   **Gestire elevati volumi di eventi di protezione**. Per far fronte all'elevato volume di eventi di protezione che possono essere generati è necessario determinare con cura i controlli di protezione di cui tenere traccia. Queste considerazioni sono particolarmente importanti quando si ha a che fare con il controllo dell'accesso a file e oggetti, poiché tali accessi possono generare grandi quantità di dati.
  
-   **Archiviare e gestire le informazioni sugli eventi in un repository centrale**. L'archiviazione delle informazioni sugli eventi può coinvolgere terabyte di dati, a seconda della configurazione del sistema di monitoraggio. Questo è un fattore molto importante da tenere presente al momento di considerare i requisiti di analisi forense ed è descritto in dettaglio nella relativa sezione.
  
-   **Identificare le firme degli attacchi e rispondere con l'azione appropriata**. Per identificare i modelli di attività che possono segnalare un attacco, un revisore o una query configurata devono essere in grado di selezionare gli eventi associati a tali attività e incorporati nelle informazioni fornite. Una volta identificata un'attività sospetta, dovrebbe esistere un meccanismo in grado di richiedere una risposta appropriata e tempestiva.
  
-   **Evitare che il personale eluda i controlli di protezione**. Il personale dotato di privilegi elevati per la rete, soprattutto gli amministratori, dovrebbe essere suddiviso in compartimenti in modo da limitare l'accesso alle informazioni di controllo e fare sì che solo gli addetti alla protezione possano amministrare i sistemi di controllo.
  
###### Pianificazione della soluzione
  
Prima di implementare un sistema di monitoraggio della protezione e identificazione degli attacchi dovrebbero essere completate le attività riportate di seguito:
  
-   Rivedere le attuali impostazioni dei controlli di protezione.
  
-   Valutare i ruoli amministrativi e le normali attività utente.
  
-   Rivedere criteri e procedure aziendali.
  
-   Identificare i sistemi vulnerabili.
  
-   Stilare l'elenco delle risorse di elevato valore.
  
-   Identificare gli account sensibili o sospetti.
  
-   Stilare l'elenco dei programmi autorizzati.
  
Per ulteriori informazioni sui requisiti di archiviazione, vedere la sezione "Implementare l'analisi forense" più avanti in questo documento.
  
###### Rivedere le attuali impostazioni dei controlli di protezione
  
Le aziende dovrebbero rivedere le impostazioni correnti dei controlli di protezione e del registro degli eventi di protezione per avere una base da cui partire per le modifiche consigliate in questo documento. Questo tipo di revisione dovrebbe essere eseguito regolarmente dopo l'implementazione di una soluzione e deve essere attuato disponendo delle seguenti informazioni:
  
-   Impostazioni in vigore per i controlli di protezione.
  
-   Livello a cui si applicano le impostazioni (computer locale, sito, dominio o unità organizzativa).
  
-   Impostazioni correnti per il file di registro (limiti delle dimensioni e comportamento in caso di raggiungimento del limite massimo).
  
-   Altre impostazioni dei controlli di protezione applicabili (ad esempio, controllo dell'uso dei privilegi di backup e ripristino).
  
Le informazioni contenute in "Appendice B: Implementazione delle impostazioni dei criteri di gruppo" alla fine di questo documento possono essere utilizzate come aiuto per identificare le impostazioni da registrare. Per ulteriori informazioni sulle impostazioni dei controlli di protezione, vedere la [*Guida per la protezione di Windows Server 2003*](http://go.microsoft.com/fwlink/?linkid=14845) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14845.
  
###### Valutare i ruoli amministrativi e le normali attività utente
  
Fondamentale per l'implementazione di un'efficace soluzione di monitoraggio della protezione è assicurarsi che i titolari di un account amministrativo siano noti e che i loro ruoli e responsabilità siano chiari. Ad esempio, molte aziende includono gli amministratori nel gruppo Domain Admins perché possano creare nuovi account utente nel dominio. È possibile, tuttavia, che alcuni criteri aziendali specifichino che per la creazione di nuovi account sia consentita l'installazione di un solo sistema di fornitura. In una situazione del genere, un evento costituto dalla creazione di un account e avviato da un account amministrativo richiede un'immediata indagine.
  
La valutazione delle attività degli account utente è generalmente un'operazione molto più semplice, poiché tali account dispongono di un accesso molto più limitato alle risorse di rete rispetto agli account amministrativi. Ad esempio, dal momento che i normali utenti non hanno in genere la necessità di accedere al file system dei computer che risiedono entro il perimetro di una rete, non è necessario monitorare l'attività dei normali utenti su questi server.
  
###### Rivedere criteri e procedure aziendali
  
La revisione dei processi e delle procedure aziendali è molto simile alla valutazione dei ruoli e delle responsabilità degli amministratori, anche se non si limita solo a questo. Questo tipo di revisione dovrebbe includere, ad esempio, l'analisi del processo di creazione degli utenti e del processo di controllo delle modifiche. L'analisi dei meccanismi alla base del processo di approvazione e dell'itinerario di controllo di tutti gli eventi che si verificano nella rete è fondamentale per mettere in correlazione quelli che possono essere eventi di controllo autorizzati quelli che possono essere considerati tentativi di intrusione.
  
###### Identificare i sistemi vulnerabili
  
I sistemi vulnerabili sono i computer e i dispositivi di rete ai quali è più probabile che un attacker esterno provi ad accedere prima di tentare un altro tipo di approccio. Questi computer risiedono generalmente lungo il perimetro della rete, ma anche i dispositivi interni possono essere vulnerabili agli attacchi e non devono essere completamente ignorati.
  
Una revisione completa dei sistemi vulnerabili dovrebbe assicurare che:
  
-   Tutti i service pack e gli aggiornamenti della protezione pertinenti siano stati applicati.
  
-   Tutti i servizi e gli account utente non necessari siano stati disabilitati.
  
-   I servizi siano configurati per essere eseguiti ove possibile con l'account Servizio locale o Servizio di rete.
  
-   I servizi che richiedono le credenziali di account utente siano controllati affinché richiedano quel livello di accesso, soprattutto se tali account dispongono di privilegi di amministrazione.
  
-   Siano stati applicati modelli di criteri di protezione di elevato livello.
  
**Nota**   Questo processo di revisione non dovrebbe essere limitato ai computer vulnerabili residenti lungo il perimetro della rete. Una buona procedura richiede l'applicazione di questi controlli a tutti i computer della rete.
  
Per ulteriori informazioni su come configurare i servizi in modo che vengano eseguiti in modalità protetta, vedere [*The Services and Service Accounts Planning Guide*](http://technet.microsoft.com/it-it/library/dd550631.aspx) (in inglese) all'indirizzo http://technet.microsoft.com/it-it/library/dd550631.aspx.
  
###### Stilare l'elenco delle risorse di elevato valore
  
È probabile che la maggior parte delle aziende abbia già identificato le risorse di elevato valore che risiedono nelle loro reti, ma potrebbero non aver formalizzato queste informazioni nell'ambito di una politica organizzativa, documentando e dettagliando le protezioni previste per ogni risorsa. Ad esempio, è possibile che un'azienda faccia uso di elenchi di controllo di accesso (ACL) e di crittografia per l'archiviazione protetta dei record finanziari sensibili sulle partizioni del file system NTFS. Una corretta politica organizzativa, tuttavia, dovrebbe identificare tali record come file protetti a cui amministratori e utenti non autorizzati non dovrebbero tentare di accedere e informare amministratori e utenti di questa restrizione.
  
Qualsiasi modifica a un ACL utilizzato per proteggere tali file dovrebbe essere analizzata, soprattutto nel caso di modifiche relative alla proprietà, poiché questo tipo di eventi possono indicare tentativi illeciti di accedere ai file senza la dovuta autorizzazione. Poiché le modifiche di questo tipo dovrebbero essere molto rare, dovrebbero essere anche facili da rilevare una volta che le risorse di elevato valore sono state identificate e documentate.
  
###### Identificare gli account sensibili o sospetti
  
Tutti gli account sensibili dovrebbero essere esaminati per sapere quali di essi richiedono un maggiore livello di controllo. In questi account sono inclusi l'account Administrator predefinito, i membri dei gruppi Enterprise, Schema o Domain Admins e tutti gli account utilizzati dai servizi.
  
Oltre a controllare gli account sensibili, è importante anche regolare i livelli di controllo della protezione degli account di individui considerati a rischio o sospettati di partecipare ad attività poco chiare. Per ulteriori informazioni su come regolare i livelli di controllo della protezione per un singolo account utente, vedere la sezione "Violazioni dei criteri e soglie" più avanti in questo documento.
  
###### Stilare l'elenco dei programmi autorizzati
  
Per scoprire informazioni su una rete, un attacker deve eseguire dei programmi sui sistemi residenti sulla rete in questione. Applicando una restrizione ai programmi che possono essere eseguiti sulla rete, un'azienda può ridurre notevolmente la minaccia di un attacco esterno. Per stabilire l'elenco dei programmi autorizzati, è necessario eseguire un controllo su tutti i programmi che al momento sono autorizzati o identificati come necessari nell'ambiente di rete. Ogni programma sconosciuto che viene rilevato durante questo tipo di controllo dovrebbe essere considerato sospetto e immediatamente analizzato. L'uso di Microsoft Systems Management Server 2003 può essere di aiuto nell'esecuzione dei controlli del software, ma non è obbligatorio.
  
**Nota**   Per alcuni computer potrebbero essere richieste delle eccezioni, ad esempio nel caso delle workstation degli sviluppatori in cui si trovano eseguibili in fase di sviluppo che potrebbero non essere presenti nell'elenco dei programmi approvati. In base a un approccio più sicuro, tuttavia, le attività di sviluppo e di test dovrebbero essere eseguite solo in un ambiente di computer virtuale o in dominio di rete isolato e dedicato a tali attività.
  
##### Rilevare violazioni dei criteri e soglie
  
Le violazioni dei criteri costituiscono la più vasta categoria di problemi di protezione che richiedono un piano aziendale. Questi tipi di incidenti includono:
  
-   Creazione di account utente con metodi diversi dal processo stabilito.
  
-   Uso improprio o non autorizzato dei privilegi di amministrazione.
  
-   Uso degli account di servizio per l'accesso interattivo.
  
-   Tentativi di accesso ai file da parte di account utente non autorizzati.
  
-   Eliminazione di file a cui gli account utente sono autorizzati ad accedere.
  
-   Installazione ed esecuzione di software non approvato.
  
Sebbene la maggior parte delle violazioni dei criteri siano costituite da tentativi di accesso involontari, quali l'esplorazione di directory con restrizioni, tali violazioni sono generalmente le meno importanti poiché possono essere risolte da limitazioni dell'accesso e da buoni criteri per la gestione dei diritti. Quelle di tipo amministrativo sono le violazioni più importanti, indipendentemente dal fatto che siano intenzionali o involontarie, proprio per la natura stessa dei diritti amministrativi che vengono violati.
  
I privilegi degli account amministrativi garantiscono un notevole livello di accesso ai sistemi alle persone che richiedono questo tipo di autorità per eseguire le loro funzioni. Questa autorità, tuttavia, non implica l'autorizzazione all'uso dei sistemi che non rientrano nell'ambito di tali funzioni. Capacità quali la creazione e la modifica degli account utente, la visualizzazione di dati riservati e la modifica dei diritti di accesso ai dati sono talmente potenti da richiedere un'attenta preparazione dei mezzi atti a ridurre i rischi che esse comportano.
  
###### Modellazione delle minacce
  
Come risulta evidente, alcuni tipi di minacce possono essere attenuati con azioni di controllo, altri non possono essere attenuati e altri ancora non vengono attenuati con azioni di controllo, anche se lo potrebbero, perché il gioco non vale la candela. Un concetto importante da assimilare è che non tutte le vulnerabilità rappresentano una minaccia per la rete. Per decidere quali vulnerabilità vanno attenuate e quali no, può essere di aiuto applicare i principi della modellazione delle minacce.
  
La modellazione delle minacce è una tecnica di engineering che agevola l'identificazione di minacce e vulnerabilità e la creazione di contromisure adeguate al contesto dell'ambiente specifico. Questo processo prevede, generalmente, tre passaggi fondamentali:
  
-   Capire il punto di vista dell'attacker.
  
-   Identificare il profilo di protezione del sistema.
  
-   Stabilire e classificare le minacce più importanti.
  
Esaminare un ambiente di rete dal punto di vista di un attacker significa capire quali possono essere gli obiettivi più allettanti per una persona che desidera accedere alla rete e le condizioni che devono verificarsi perché l'attacco a tali obiettivi riesca. Una volta identificati gli obiettivi vulnerabili, è possibile esaminare l'ambiente per capire in che modo le misure di sicurezza esistenti possono influire sulle condizioni dell'attacco. Questo processo mette in luce le minacce più importanti che possono essere poi classificate in base al livello di rischio che rappresentano, i rimedi che possono costituire la soluzione migliore a queste minacce e se le conseguenze di tali rimedi in altre aree possono influire in modo positivo o negativo sul loro valore.
  
Di conseguenza, per avvalersi di un buon processo di modellazione delle minacce alla rete, è necessario mettere una atto alcuni passaggi specifici, basati sui seguenti requisiti:
  
1.  **Identificare le risorse critiche**. Per determinare le aree a cui è meglio assegnare le risorse di protezione è necessario creare l'elenco delle risorse critiche per le operazioni aziendali. Questo processo dovrebbe coinvolgere sia i proprietari dei processi aziendali che i proprietari delle tecnologie, poiché entrambi dovranno esprimere il loro parere circa le risorse che, se compromesse, potrebbero danneggiare l'azienda.
  
2.  **Identificare i possibili punti di attacco**. Anche questa fase di identificazione coinvolge due diversi punti di vista. In primo luogo, è necessario classificare i confini entro cui possono risiedere i dati sulla rete. Questi confini si trovano all'interno di una delle tre aree di autenticazione - critica, sensibile e pubblica - in base al danno che l'esposizione dei loro dati potrebbe provocare. In secondo luogo, un esame dal punto di vista tecnologico deve identificare i punti di attacco, per mezzo di alcuni vettori, e i punti di vulnerabilità che potrebbero esporre risorse critiche e sensibili. La combinazione di questi due tipi di informazioni aiuta a concentrare le iniziative di protezione solo sui punti in cui è possibile un accesso alle informazioni critiche.
  
3.  **Identificare le minacce reali**. Una volta identificate le risorse critiche e i possibili punti di accesso, è possibile creare un elenco delle cose che un attacker potrebbe fare per danneggiare l'azienda. Disponendo di questo elenco, è poi possibile concentrare le iniziative su minacce reali e specifiche.
  
    Per identificare le minacce reali, sono disponibili vari metodi. Uno di questi metodi è lo STRIDE. Lo STRIDE (Spoofing, Tampering, Repudiation, Information disclosure, Denial of Service, and Elevation of Privilege) esamina le minacce in base ai tipi di attacco che possono essere utilizzati: spoofing, alterazione, ripudio, intercettazione di informazioni, Denial of Service e acquisizione di privilegi più elevati. Esistono anche altre misure iterative, quali la suddivisione delle minacce per livello logico, ad esempio rete, host e applicazione. L'approccio alla suddivisione varia da azienda ad azienda in base alle esigenze dell'ambiente utilizzato.
  
4.  **Categorizzare e classificare le minacce**. Questo passaggio consiste nel mettere in pratica i principi comuni di gestione e valutazione dei rischi, classificando le minacce in base alla loro probabilità e all'impatto che potrebbero avere sull'azienda. Di seguito è riportata la formula standard che viene utilizzata:
  
    Rischio = Probabilità di sfruttamento x Potenziale impatto sull'azienda
  
    Questo documento non descrive tutti i metodi utilizzati in un processo del genere e tutti gli strumenti disponibili per facilitare questo tipo di valutazione del rischio. Per ulteriori informazioni sulla gestione dei rischi e su questi metodi, visitare il sito Web [*Guida alla gestione dei rischi di protezione*](http://technet.microsoft.com/it-it/library/cc163151) all'indirizzo http://technet.microsoft.com/it-it/library/cc163151.
  
5.  **Rimediare e rivalutare**. Il prodotto dei passaggi precedenti è un elenco delle minacce reali in grado di avere un impatto sull'azienda, classificate in base al rischio che presentano. Questo elenco permette di elaborare rimedi mirati, da valutare anche in base al loro rapporto costi-benefici. Dopo tutto, tra i vari modi per attenuare specifici rischi potrebbero essercene alcuni in grado di risolvere anche altre vulnerabilità, rendendo ancora più efficace l'iniziativa di protezione.
  
Anche dopo l'implementazione di un piano di rimedio, il metodo di modellazione delle minacce rimane un processo iterativo da eseguire su base regolare e con attività di rivalutazione costanti, in modo da assicurare che le attività di protezione siano le più efficaci e complete possibili.
  
###### Indagini sul background e revisioni
  
La maggior parte delle aziende esegue già una qualche forma di controllo del background dei futuri dipendenti, a cui però non fa seguire controlli successivi. Le aziende dovrebbero considerare la regolare esecuzione di questi controlli per tutta la durata del rapporto di lavoro, soprattutto per quanto riguarda le persone che ricoprono cariche critiche con accesso a informazioni riservate.
  
###### Accordi sui criteri per l'utilizzo dei computer
  
Gli accordi sull'utilizzo dei computer o della rete sono importanti per informare i dipendenti non solo su come possono impiegare le risorse aziendali ma anche dei criteri per monitorare l'attività della rete e l'utilizzo dei computer e delle possibili conseguenze che possono avere i tentativi di violazione a questi criteri.
  
Le dichiarazioni sui criteri di utilizzo hanno anche valore legale quando definiscono questi punti in termini espliciti e richiedono la firma del dipendente per accettazione dell'accordo. Se non si può provare che un dipendente era a conoscenza dei criteri di monitoraggio della protezione e dell'utilizzo consentito delle risorse aziendali, è molto difficile perseguire gli eventuali abusi.
  
È importante anche che venga emesso un avviso di accesso/utilizzo non autorizzato per ogni punto di accesso della rete aziendale, in modo da informare ogni persona che tenta di accedere alla rete che questa è privata e che chiunque tenti di eseguire un accesso non autorizzato sarà perseguito legalmente. I sistemi operativi Windows, ad esempio, possono visualizzare una dichiarazione che, in caso di tentativo di accesso, avvisa gli utenti del fatto che stanno cercando di accedere a una risorsa aziendale protetta e che l'accesso a tale risorsa non è autorizzato.
  
Anche se le questioni legali riguardanti l'esatta formulazione e l'utilizzo di questo tipo di documenti non rientrano nell'ambito di questa pubblicazione, è importante sottolineare la necessità di tali documenti e dei criteri sopra descritti. Su Internet è possibile trovare diversi esempi di queste dichiarazioni sull'utilizzo e sull'accesso, ma si consiglia di affidare la preparazione di questi documenti a uffici legali qualificati, poiché le leggi nazionali e internazionali sono estremamente severe a riguardo.
  
###### Separazione delle mansioni
  
Così come, ai fini di protezione, prestazioni e disponibilità, le varie funzionalità per i sistemi sono segmentate sulla rete aziendale, è importante anche provvedere alla duplicazione e alla separazione delle mansioni quando si pensa allo sviluppo dei requisiti di reclutamento del personale IT addetto alla protezione.
  
Ruoli che comportano l'accesso a o il controllo di dati e sistemi sensibili dovrebbero essere ridondanti ove possibile e ragionevole, non solo per evitare che la perdita di un membro dello staff significhi anche la perdita di informazioni importanti, ma anche per disporre di una funzione di protezione in caso di sabotaggio interno. Ad esempio, se le password degli amministratori sono note a una sola persona e questa persona abbandona l'azienda senza averle comunicate ad altri, effettuare un ripristino sarebbe impossibile.
  
Oltre alla ridondanza dei ruoli, è importante tenere separati i ruoli critici, soprattutto per quanto riguarda il monitoraggio della protezione. Le persone che gestiscono la rete non dovrebbero essere responsabili anche della revisione delle informazioni relative al controllo della protezione e il personale addetto alla protezione non dovrebbe avare gli stessi diritti amministrativi degli amministratori. Per ottimizzare la separazione delle mansioni, può rendersi necessario anche proteggere le informazioni dipartimentali dal personale amministrativo. Alcune aziende, ad esempio, proteggono informazioni sensibili come dati finanziari o personali facendo sì che ogni unità organizzativa disponga dei propri account per l'amministrazione o i sistemi.
  
**Nota**   Sebbene sia impossibile impedire ai titolari di account amministrativi di trovare una soluzione alternativa per ovviare alla separazione delle mansioni, è importante come minimo stabilire delle linee guida sugli utilizzi autorizzati affinché l'autorità amministrativa applichi il principio della separazione delle mansioni.
  
###### Convalidare la funzionalità di monitoraggio della protezione
  
Prima di implementare una soluzione di monitoraggio della protezione è necessario aver predisposto un accurato piano per la verifica costante di tale soluzione. Benché il test iniziale sia fondamentale per convalidare una soluzione di monitoraggio della protezione, un piano di test da effettuare regolarmente per verificare un ambiente in continua evoluzione come quello della protezione è altrettanto importante.
  
I test possono includere tentativi di intrusione e utilizzi dei privilegi di amministrazione per stabilire se la soluzione è efficace nel rilevare queste attività. Anche la ricerca delle ultime novità in termini di tecniche di protezione e profili di attacco è utile per capire se è necessario effettuare dei cambiamenti. Le minacce alle reti aziendali sono sempre diverse poiché gli attacker cercano di adeguarsi alle varie implementazioni della protezione. Ecco perché, per mantenere la loro efficacia, le tecniche di difesa e monitoraggio devono evolversi di continuo.
  
###### Stabilire i processi
  
Per separare gli eventi autorizzati da quelli non autorizzati, è necessario creare un piano per i processi di controllo delle modifiche obbligatorie e di gestione dei problemi. Questo tipo di piano può offrire un traccia cartacea dettagliata da utilizzare per ottenere una correlazione incrociata con le informazioni del registro di protezione. Mentre il processo di controllo dei problemi è ampiamente utilizzato nella maggior parte delle aziende, con l'aiuto dei ticket dell'help desk o di altri metodi di registrazione dei problemi, il processo di controllo delle modifiche viene spesso trascurato. Il controllo delle modifiche è un meccanismo necessario e può essere impiegato non solo per tenere traccia delle tendenze e per individuare le applicazioni o i sistemi problematici, ma anche come meccanismo di protezione di importanza vitale.
  
I processi di controllo delle modifiche dovrebbero essere applicati come procedura attiva, mentre le modifiche reattive dovrebbero essere consentite solo all'interno dei processi di gestione dei problemi. Un processo di controllo delle modifiche dovrebbe richiedere la revisione e l'approvazione di ogni modifica da parte delle persone preposte a questo incarico e dovrebbe includere i seguenti dettagli:
  
-   Nome del revisore
  
-   Nome del responsabile dell'implementazione
  
-   Tempo previsto per la modifica
  
-   Motivi della modifica
  
-   Modifiche da apportare
  
-   Sistemi interessati dalla modifica
  
-   Impatto aziendale
  
-   Effettivi risultati della modifica
  
Un altro processo fondamentale è il processo di predisposizione utente, da applicare tramite una procedura di aggiunta/modifica/eliminazione degli utenti che crei anche un itinerario di controllo in grado di impedire che vengano apportate modifiche non autorizzate agli account. Prima di stabilire questo processo, è necessario eseguire un controllo della protezione per gli account utente correnti, in modo da verificare la validità di tali account, e convalidare periodicamente l'elenco di questi account dopo ogni modifica.
  
L'uso di soluzioni automatiche di predisposizione utente e gestione delle identità, quali Microsoft Identity Integration Server (MIIS) 2003, può essere di aiuto, così come l'automazione delle modifiche agli account e dei processi alla base di queste attività. È importante ricordare che se si utilizzano queste soluzioni gli account di amministrazione conservano la capacità di creare nuovi account ma non avranno bisogno di utilizzarla, poiché gli account verranno creati dai processi stabiliti. A questo punto, tutti gli eventi associati alla creazione degli account, come l'evento 624, dovrebbero correlarsi solo all'account di MIIS 2003 o dell'altro servizio stabilito, utilizzato per la predisposizione automatica.
  
Anche se i media parlano continuamente di minacce esterne, l'esperienza insegna che le reti e i dati aziendali sono molto più soggetti a perdite o danni dovuti a problemi interni quali configurazioni errate o passaggi procedurali non corretti. Proteggersi da tutte le minacce, sia esterne che interne, è molto importante ma mentre i fornitori che possono aiutare l'azienda a difendersi dalle minacce esterne sono numerosi, non ce n'è nessuno che offra un pacchetto in grado di impedire gli errori commessi proprio dai responsabili della rete e della protezione. Il modo migliore di attenuare questi rischi è implementare e attuare solidi processi e procedure per il controllo delle modifiche eseguite nella rete.
  
###### Definire le risposte di protezione
  
Per limitare i danni che una violazione della protezione può causare, è importante sviluppare un buon piano di risposta e stabilire i processi di risposta agli incidenti. I report sugli incidenti, la formazione di un team in grado di rispondere rapidamente e un protocollo di emergenza sono buoni esempi di tali piani e processi. La tempestività e l'efficacia delle risposte può aumentare il profilo di protezione di un'azienda e limitare i danni effettivi e percepiti che un tentativo di intrusione può causare.
  
Un processo di risposta consolidato non solo aiuta a limitare il danno che un incidente vero può causare, ma funziona anche da deterrente in quanto informa le persone interne ed esterne del fatto che il verificarsi di un incidente darà adito a una risposta immediata e coordinata a tutte le violazioni della protezione.
  
###### Risorse umane
  
Secondo gli studi effettuati dal CERT e dai servizi segreti degli Stati Uniti, molti attacchi di origine interna potrebbero essere evitati se le aziende sapessero meglio se e come intervenire per rispondere alle minacce o ai cambiamenti comportamentali di un dipendente. In un'azienda, le risorse di maggior valore per quanto riguarda la protezione sono proprio i dipendenti, poiché possono capire quando un membro dello staff è scontento oppure avvisare il personale preposto se un visitatore esterno si comporta in maniera sospetta. In effetti, le prime cose che fa un gruppo esterno a cui viene affidato il controllo della protezione in un'azienda sono "farsi un giro" alla ricerca di password appuntate sulla carta, individuare dispositivi non protetti o effettuare dei tentativi di intrusione collegandosi alla rete interna.
  
Lo staff interno dell'azienda può costituire un importante livello di protezione contro le minacce interne ed esterne. Incoraggiare il principio della porta aperta per sollecitare le persone a parlare dei comportamenti sospetti dei colleghi o addestrare il personale di supporto a tenere conto dei report su attività inusuali dello staff sui computer può davvero contribuire a prevenire tentativi di intrusione o casi di malware. Anche la formazione interna è un importante metodo per insegnare ai dipendenti come individuare i tipi di funzionamento dei computer da riferire. La formazione, inoltre, può essere una misura preventiva contro gli attacchi di social engineering.
  
##### Correlare le violazioni dei criteri di protezione e gli eventi di controllo
  
La correlazione delle informazioni sugli eventi di protezione comporta la raccolta degli eventi di protezione da diversi sistemi e l'inserimento di questi dati in una posizione locale centralizzata. Una volta correlate le informazioni sulla protezione, il personale preposto può utilizzare il repository centrale per identificare le violazioni o gli attacchi esterni. Questo repository non è importante solo per l'analisi forense, ma anche per scoprire gli attacchi e risolvere le vulnerabilità. Oltre a diverse soluzioni di terze parti atte a questo scopo, esistono anche prodotti e strumenti Microsoft che possono aiutare a correlare i registri degli eventi di protezione e le altre informazioni sul controllo della protezione all'interno di un repository centrale. Tali prodotti e strumenti sono riportati di seguito.
  
###### EventCombMT
  
EventCombMT (multithreaded) è un componente della [*Guida per la protezione di Windows Server 2003*](http://technet.microsoft.com/it-it/library/cc163140), disponibile all'indirizzo http://technet.microsoft.com/it-it/library/Dd536253. Questo strumento può analizzare e raccogliere eventi dai registri degli eventi di più computer. Viene eseguito come applicazione multithreaded che permette all'utente di specificare qualsiasi numero di parametri per la scansione dei registri degli eventi, ad esempio:
  
-   ID degli eventi (singoli o multipli)
  
-   Intervalli di ID evento
  
-   Origini degli eventi
  
-   Testo specifico dell'evento
  
-   Durata dell'evento in minuti, ore o giorni
  
[![](images/Cc875806.SMAAD4(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875806.smaad4_big(it-it,technet.10).gif)
  
**Figura 4. EventCombMT**
  
In EventCombMT sono disponibili alcune specifiche categorie di ricerca predefinite, ad esempio i blocchi di account (mostrati nella figura precedente), che offrono funzionalità di ricerca per gli eventi riportati di seguito:
  
-   **529**. Accesso non riuscito (nome utente sconosciuto o password non valida)
  
-   **644**. Bloccato account utente
  
-   **675**. Preautenticazione non riuscita su un controller di dominio (password non valida)
  
-   **676**. Richiesta ticket di autenticazione non riuscita
  
-   **681**. Accesso non riuscito
  
Un altro evento relativo alla protezione che non risiede nel file del registro degli eventi di protezione è il 12294, che si trova nel Registro di sistema. È importante aggiungere questo evento a ogni ricerca, poiché consente di rilevare i tentativi di attacco all'account Administrator che è privo di un limite per il blocco ed è quindi un bersaglio vulnerabile e attraente per qualsiasi aspirante attacker.
  
**Nota**   L'evento 12294 è riportato come evento SAM (Security Accounts Manager) nel Registro di sistema, non nel registro degli eventi di protezione.
  
EventCombMT può salvare gli eventi in una tabella di database Microsoft SQL Server™, rivelandosi utile per l'analisi e l'archiviazione a lungo termine. Una volta archiviate in un database SQL Server, le informazioni ottenute dai registri degli eventi possono essere utilizzate da una vasta gamma di programmi, tra cui SQL Query Analyzer, Microsoft Visual Studio® .NET, e da alcune utilità di terze parti.
  
###### Log Parser 2.2
  
Log Parser è uno strumento Microsoft gratuito che può essere utilizzato per ricercare i dati in un registro, caricare i registri in un database SQL o in un file CSV e generare report dai registri degli eventi, dai file CSV o da altri formati di registro (inclusi i registri IIS per cui è stato originariamente creato).
  
Questo strumento per script dalla riga di comando può essere utilizzato come risorsa per correlare le informazioni dei registri degli eventi all'interno di una posizione centrale, analizzare gli eventi ritenuti interessanti e generare report. Il livello di dettaglio richiesto per gli script e l'interfaccia riga di comando non rientra nell'ambito del presente documento. Per ulteriori informazioni su Log Parser, sugli utilizzi di questo strumento e sulle risorse per gli script, vedere la pagina relativa a [Log Parser 2.2](http://www.microsoft.com/technet/scriptcenter/tools/logparser/default.mspx) (in inglese) all'indirizzo www.microsoft.com/technet/scriptcenter/tools/logparser/default.mspx e l'articolo "[How Log Parser 2.2 Works](http://technet.microsoft.com/en-us/library/bb878032.aspx)" (in inglese) all'indirizzo www.microsoft.com/technet/community/columns/profwin/pw0505.mspx.
  
###### EventQuery.vbs
  
EventQuery.vbs è uno strumento rilasciato con Windows XP. Può essere utilizzato per ottenere l'elenco degli eventi e le proprietà degli eventi da uno o più registri degli eventi. Per poter utilizzare questo script, è necessario che sia in esecuzione lo script host basato sui comandi (CScript.exe). Se il Windows Script Host predefinito non è stato impostato su CScript, è possibile effettuare questa operazione con il seguente comando:
  
<codesnippet language displaylanguage containsmarkup="false">Cscript //h:cscript //s //nologo  
```  
Questa utilità di script dalla riga di comando è estremamente flessibile e può accettare un elevato numero di parametri per regolare il filtraggio e il formato da applicare all'output. Per ulteriori informazioni sull'utilizzo di questo strumento e sui parametri disponibili, vedere l'argomento [Managing event logs from the Command Line](http://technet.microsoft.com/en-us/library/cc757231.aspx) (in inglese) presente in Windows XP Professional Product Documentation (in inglese) all'indirizzo www.microsoft.com/resources/documentation/windows/xp/all/proddocs/en-us/event\_commandline.mspx?mfr=true.
  
###### Registrazione di Internet Information Services (IIS).
  
La funzionalità di registrazione aggiuntiva disponibile con IIS (Internet Information Services) consente di sapere chi ha visitato il sito, a cosa ha avuto accesso e quando. I registri IIS riportato i tentativi (riusciti e non) di accesso a siti, cartelle virtuali e file, e possono essere configurati in modo da controllare selettivamente le informazioni per ridurre i requisiti di archiviazione e limitare la registrazione di informazioni non necessarie.
  
Questi registri possono essere archiviati in formato nativo sotto forma di file e successivamente filtrati con uno degli strumenti di analisi e confronto elencati in precedenza oppure possono essere archiviati direttamente in una posizione centralizzata utilizzando la funzione di registrazione database ODBC che consente di memorizzare le informazioni in un database SQL o in qualsiasi altro database compatibile con ODBC.
  
Alcune attività e sequenze di eventi andrebbero sottoposte a un monitoraggio serrato, ad esempio:
  
-   Un elevato numero di comandi non riusciti per tentare di eseguire file eseguibili o script.
  
-   Un numero eccessivo di tentativi di accesso non riusciti da parte di un unico indirizzo IP o intervallo di indirizzi IP, evento che può indicare un tentativo di attacco di tipo DoS o acquisizione di privilegi più elevati.
  
-   Tentativi non riusciti di accesso o modifica di file .bat o .cmd.
  
-   Tentativi non autorizzati di caricare file in una cartella contenente file eseguibili.
  
A cominciare da Windows Server 2003, in IIS sono disponibili nuove capacità di controllo predefinite da che possono essere utilizzate con le nuove capacità di registrazione, integrate direttamente nel registro degli eventi o rese accessibili tramite pagine ASP nelle soluzioni personalizzate. Per ulteriori informazioni su queste capacità e sulla loro implementazione, vedere la documentazione relativa a IIS.
  
###### Microsoft Internet Security and Acceleration Server
  
Microsoft Internet Security and Acceleration (ISA) Server è un pacchetto avanzato con memorizzazione dello stato e un firewall a livello di applicazione che offre anche funzionalità aggiuntive quali VPN e capacità proxy per il caching.
  
Oltre all'utilità di difesa attiva, ISA Server fornisce anche una funzione di monitoraggio della protezione grazie alla sua capacità di agire come strumento di controllo centralizzato e in grado di monitorare tutte le attività che richiedono l'attraversamento del perimetro della rete. Le capacità di registrazione di ISA Server includono la cattura del traffico sul firewall, l'attività proxy sul Web e i registri di screening dei messaggi SMTP. Questi registri possono essere filtrati, utilizzati per interrogazioni o monitorati in tempo reale utilizzando il visualizzatore registro in tempo reale predefinito (mostrato nella schermata seguente) o il dashboard di monitoraggio.
  
[![](images/Cc875806.SMAAD5(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875806.smaad5_big(it-it,technet.10).gif)
  
**Figura 5. Visualizzatore registro in tempo reale di Microsoft ISA Server 2004**
  
Oltre alla funzionalità di registrazione predefinita, ISA Server offre una funzione in grado di emettere avvisi tramite e-mail o voci del registro degli eventi e, addirittura, di avviare o arrestare i servizi. La capacità di registrare le attività sospette come voci del registro degli eventi è particolarmente rilevante nell'ambito di questo documento. Questa capacità consente di registrare e archiviare informazioni su possibili attacchi in una posizione centralizzata in cui si trovano i dati di altri registri degli eventi.
  
Oltre a questa funzionalità di registrazione e avviso, ISA Server dispone anche di altri strumenti predefiniti per l'identificazione delle intrusioni. Questi IDS (Intrusion Detection Services) di base sono concessi su licenza da Internet Security Systems e includono diversi filtri per pacchetti IP, filtri per applicazioni DNS e un filtro per applicazioni POP. Questi servizi sono in grado di rilevare molti tra i più diffusi tentativi di exploit delle vulnerabilità.
  
La funzionalità di identificazione delle intrusioni di ISA Server è in grado di registrare gli eventi e generare un avviso nel caso in cui venga scoperto un attacco potenziale. È anche in grado di terminare servizi o connessioni sospette. Alcuni dei profili di attacco che possono essere rilevati sono i seguenti:
  
-   WinNuke (attacchi fuori banda Windows)
  
-   Land Attack
  
-   Attacchi con scansione parziale IP
  
-   Bombe UDP
  
-   Scansione porte
  
-   Attacchi di overflow della lunghezza dei nomi host DNS
  
-   Trasferimenti di zone DNS da porte con privilegi o porte alte TCP/IP
  
In ognuno di questi casi, che si usi ISA Server o un'altra soluzione firewall e IDS, è importante considerare il perimetro della rete (conosciuto anche come DMZ, ovvero zona demilitarizzata, e sottorete schermata) al momento di progettare un sistema di monitoraggio della protezione e identificazione degli attacchi.
  
###### Microsoft Operations Manager 2005
  
Microsoft Operations Manager (MOM) esegue il monitoraggio dei server dell'ambiente di rete da una posizione centrale. L'agente MOM raccoglie gli eventi dai registri degli eventi e li inoltra al server di gestione MOM, che a sua volta li inserisce nel database MOM. Sia MOM 2005 che le versioni successive sono in grado di raccogliere gli eventi dai computer su cui non sono in esecuzione agenti MOM.
  
MOM utilizza le regole del suo Management Pack per identificare i problemi che influiscono sulla corretta funzionalità dei server. È possibile creare regole aggiuntive per eventi specifici in modo che, se si verifica uno di questi eventi, venga inviata una notifica di avviso tramite messaggi e-mail, messaggi popup o messaggi sui cercapersone.
  
Anche se MOM offre molte utili funzioni per il monitoraggio della protezione e l'identificazione degli attacchi, non è stato progettato per questo scopo. Le future versioni di MOM offriranno una maggiore funzionalità di raccolta dei dati dai registri di protezione.
  
###### Microsoft Systems Management Server 2003
  
Microsoft Systems Management Server (SMS) 2003 può monitorare e gestire i server e le workstation da una posizione centrale. Anche se pensato per attività di gestione, può offrire funzioni correlate alla protezione in una soluzione di monitoraggio della protezione proprio gestendo la distribuzione e il reporting degli aggiornamenti della protezione o eseguendo il reporting delle installazioni software non autorizzate.
  
La funzionalità di inventario di SMS può soddisfare un importante requisito di una soluzione di monitoraggio della protezione offrendo una soluzione di gestione dell'inventario centralizzata e in tempo reale che è fondamentale per ogni processo di controllo e monitoraggio della protezione.
  
##### Implementare l'analisi forense
  
L'analisi forense è un argomento talmente vasto da non poter essere trattato interamente in questo documento. In particolare, questo documento non tratta i requisiti di gestione delle prove dell'analisi forense e non descrive altri dati di questa analisi oltre alle informazioni fornite dai registri degli eventi di protezione.
  
L'analisi forense aiuta a determinare i tempi, la gravità e i risultati delle violazioni della protezione e a identificare i sistemi bersaglio degli attacker. Per essere valide, le informazioni raccolte dall'analisi forense devono contenere quanto segue:
  
-   Ora dell'attacco
  
-   Durata dell'attacco
  
-   Sistemi interessati dall'attacco
  
-   Modifiche effettuate durante l'attacco
  
Ancora una volta, a causa della complessità delle leggi che governano la procedura probatoria, i principali tipi di dati utilizzati dall'analisi forense, gli strumenti di analisi, la raccolta delle prove, la conservazione delle prove e le metodologie forensi, è impossibile trattare l'argomento in dettaglio in questo documento. Esistono tuttavia eccellenti risorse, quali il documento [First Responders Guide to Computer Forensics](http://www.cert.org/archive/pdf/frgcf_v1.3.pdf) del CERT disponibile all'indirizzo www.cert.org/archive/pdf/FRGCF\_v1.3.pdf, che possono essere consultate sui siti dedicati agli studi sulla protezione.
  
###### Problemi aziendali
  
Un piano per l'utilizzo dell'analisi forense si distingue dagli approcci alle altre soluzioni poiché anziché essere rivolto all'analisi in tempo reale degli incidenti implica lo studio degli incidenti dopo che si sono verificati. Questo è il motivo per cui questa analisi richiede che la cronologia dettagliata degli eventi raccolti dai vari sistemi venga conservata per un periodo di tempo più lungo. A causa di questo requisito, il sistema di analisi forense dovrebbe essere centralizzato e disporre di una capacità di archiviazione sufficiente a memorizzare un elevato numero di record in una struttura database appropriata.
  
Una delle decisioni da prendere per attenuare i rischi riguarda due fattori: per quanto tempo conservare i record per l'analisi forense e quale ciclo di memorizzazione utilizzare. Questi fattori possono avere un forte impatto sui requisiti di memoria e attrezzature del piano per l'analisi forense. Nella tabella che segue sono illustrati i tempi di conservazione più diffusi nelle aziende che hanno implementato un piano per l'analisi forense.
  
**Tabella 2. Limiti di archiviazione per l'analisi forense**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Commissionario archiviazione</th>
<th>Limiti archiviazione</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Archivio online (database)</td>
<td style="border:1px solid black;">21 giorni</td>
<td style="border:1px solid black;">Offre un rapido accesso ai dettagli degli eventi</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Archivio offline (backup)</td>
<td style="border:1px solid black;">180 giorni</td>
<td style="border:1px solid black;">Limite di archiviazione ragionevole per la maggior parte delle organizzazioni</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ambiente controllato</td>
<td style="border:1px solid black;">7 anni</td>
<td style="border:1px solid black;">Requisito di archiviazione per le aziende controllate</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Organismi di intelligence</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Requisito per gli organismi che si occupano di intelligence e difesa</td>
</tr>
</tbody>
</table>
  
**Nota**   Per quanto riguarda i limiti di archiviazione, alcune pratiche dei settori sottoposti a controllo (ad esempio, quelle utilizzate dalle aziende che gestiscono record di informazioni mediche) utilizzano indicazioni quali "da non conservare oltre" al posto di un periodo di conservazione prestabilito.
  
Un'opzione da considerare è l'utilizzo di database online per conservare i dati dell'analisi forense online e l'archiviazione dei dati più vecchi in un formato compresso, ad esempio testo con valori delimitati da virgole o formato CSV, per gli archivi offline. Se necessario, è possibile importare nuovamente i file CSV nel database online.
  
Per scegliere la soluzione migliore, è necessario considerare due importanti requisiti: poter analizzare rapidamente gli eventi recenti e poter recuperare anche i vecchi eventi, se necessario. Un piano che offra la combinazione ottimale di archiviazione online e offline non può comunque prescindere da una cronologia degli incidenti di protezione avvenuti nell'azienda e da un elenco delle risorse disponibili. Se possibile, è importante testare il sistema di raccolta degli eventi in un database sufficientemente grande, generare i report desiderati, verificare che questi vengano eseguiti in un lasso di tempo ragionevole e generare le informazioni utili.
  
Bisogna anche considerare la protezione dei dati per l'analisi forense, poiché l'accesso a tali informazioni è raramente necessario. Qualora l'accesso sia necessario, deve essere fornito a un gruppo ristretto di persone sicure, addette alla protezione. L'accesso a queste informazioni da parte degli amministratori deve essere severamente regolato da un processo di controllo delle modifiche consolidato che disponga di un maggiore capacità di sorveglianza. Nessun altro dovrebbe avere la capacità di accedere a queste informazioni, danneggiarne le raccolte o modificarle.
  
###### Problemi tecnici
  
La pianificazione di una soluzione di monitoraggio della protezione per l'analisi forense richiede misure precise per la raccolta e l'archiviazione protette e affidabili di un elevatissimo numero di eventi. I requisiti di monitoraggio della protezione sono simili a quelli descritti dettagliatamente in altri scenari di soluzione, ma hanno bisogno di maggiori risorse per l'archiviazione nei database e di un'efficiente gestione dei dati.
  
A tal fine, è consigliabile prendere in considerazione i seguenti fattori tecnici:
  
-   Archiviazione affidabile e protetta dei dati online.
  
-   Disponibilità di grandi quantità di spazio su dischi ad alte prestazioni per l'archiviazione online.
  
-   Sistemi di backup affidabili per la memorizzazione degli eventi più vecchi sui supporti di archiviazione.
  
-   Processi protetti per la gestione delle risorse di archiviazione.
  
-   Processi di ripristino testati per il recupero delle informazioni dai supporti di archiviazione di backup.
  
Queste problematiche non devono essere considerate come specifiche del monitoraggio della protezione, poiché sono già conosciute agli amministratori che si occupano di applicazioni quali i database OLTP (OnLine Transaction Processing). Diversamente dalle altre applicazioni database quali l'OLTP, però, un database di analisi forense deve gestire un numero di operazioni di scrittura maggiore di quello delle operazioni di lettura.
  
###### Requisiti
  
Per un programma di analisi forense davvero efficiente, è necessario soddisfare i seguenti requisiti:
  
-   Corretta configurazione delle impostazioni dei registri di protezione.
  
-   Consolidamento dei processi di controllo dell'accesso ai registri.
  
-   Punto di raccolta protetto e centralizzato e processo stabilito per i registri di protezione.
  
-   Archiviazione affidabile delle informazioni del monitoraggio della protezione.
  
-   Sviluppo di piani/programmi di archiviazione efficaci.
  
In ogni soluzione di analisi forense va tenuto conto dei requisiti, delle capacità e delle restrizioni normative dell'ambiente aziendale specifico, poiché possono variare.
  
#### Distribuzione e gestione della soluzione.
  
La capacità di identificare, valutare e neutralizzare un attacco è l'obiettivo finale di qualsiasi soluzione di monitoraggio della protezione e identificazione degli attacchi. Per questo motivo, la maggior parte di questa sezione sarà dedicata a una dettagliata descrizione di quelle voci del registro degli eventi che possono indicare la presenza di un attacco. Tenendo presente quanto esposto, un piano di monitoraggio della protezione e identificazione degli attacchi deve soddisfare i seguenti requisiti:
  
-   Rilevare le violazioni interne dei criteri
  
-   Identificare le origini esterne degli attacchi
  
-   Consentire un'efficiente e accurata analisi forense
  
La soluzione descritta in questo documento utilizza componenti simili per ognuno di questi tre requisiti. L'implementazione delle capacità di analisi forense propone altri requisiti che verranno esaminati successivamente.
  
##### Monitoraggio della protezione e identificazione degli attacchi
  
Il concetto di soluzione di monitoraggio della protezione e identificazione degli attacchi richiede la programmazione degli appropriati livelli di controllo della protezione per le seguenti aree:
  
-   Gestione degli account
  
-   Accesso ai file protetti
  
-   Modifiche ai criteri di protezione
  
-   Creazione ed eliminazione dei trust
  
-   Utilizzo dei diritti utente
  
-   Riavvii dei sistemi e modifiche dell'ora
  
-   Modifiche ai registri
  
-   Esecuzione di programmi sconosciuti
  
Il sistema di monitoraggio della protezione e identificazione degli attacchi raccoglie informazioni dai registri degli eventi di protezione e le inserisce in una posizione centrale. I revisori addetti alla verifica della protezione possono analizzare questi dati per scoprire attività sospette. Queste informazioni possono anche essere memorizzate e archiviate nel caso ci fosse bisogno di una successiva analisi forense.
  
Uno dei principali componenti di questa soluzione è la capacità di configurare una funzione di Microsoft Windows 2003 con Service Pack 1 (SP1) e Microsoft Windows XP con Service Pack 2 (SP2), chiamata controllo "per utente". I controlli per utente consentono di specificare diversi livelli di controllo per specifici account utente e quindi offrono una verifica più dettagliata degli account sensibili o sospetti.
  
###### Prerequisiti della soluzione
  
I prerequisiti di configurazione di questa soluzione di monitoraggio della protezione e identificazione degli attacchi sono i seguenti:
  
-   I server devono eseguire Windows Server 2003 SP1 o versioni successive e risiedere in un dominio Active Directory.
  
-   I computer client devono eseguire Windows XP SP2 o versioni successive come membri di un dominio Active Directory.
  
**Nota**   Se i computer all'interno del perimetro aziendale non risiedono in un dominio non possono essere configurati con le impostazioni di Criteri di gruppo per Active Directory. Tuttavia, per configurare questi sistemi, è possibile utilizzare modelli e criteri locali.
  
Questo documento tratta in modo particolare l'identificazione delle firme degli attacchi e non offre consigli sulla tecnologia specifica da utilizzare per la raccolta degli eventi di protezione, anche se indica alcune possibili soluzioni. Una volta deciso il meccanismo di raccolta adeguato, è possibile utilizzare gli eventi e le sequenze di eventi elencati nel documento per creare le query e gli avvisi atti a identificare un comportamento sospetto.
  
##### Violazioni dei criteri e soglie
  
Le nuove funzioni di Microsoft Windows Server 2003 e Microsoft Windows XP con SP2 offrono livelli di controllo selettivi per i singoli account utente. Ad esempio, è possibile impostare livelli di controllo per segnalare solo l'attività di accesso e di disconnessone di tutti gli utenti e, allo stesso tempo, tutta l'attività di un utente specifico. Il controllo selettivo per utente può essere utilizzato anche per ridurre il volume degli eventi nel registro di protezione, escludendo alcuni account dal controllo di certe attività. Questa funzionalità può essere utilizzata solo per gli account utente e non per i gruppi di protezione e di distribuzione. Gli account facenti parte del gruppo Administrators locale non possono essere esclusi dal controllo utilizzando il meccanismo di controllo selettivo per utente.
  
L'utilità della riga di comando che consente di impostare il criterio di controllo per utente per il controllo selettivo su Windows Server 2003 e Windows XP SP2 è Auditusr.exe. Le categorie valide per il controllo selettivo sono:
  
-   Eventi di sistema
  
-   Accesso/disconnessione
  
-   Accesso agli oggetti
  
-   Utilizzo dei privilegi
  
-   Analisi dettagliata
  
-   Modifica dei criteri
  
-   Gestione degli account
  
-   Accesso al servizio directory
  
-   Accesso account
  
Se Audituser.exe viene eseguita dalla riga di comando senza parametri, visualizza le impostazioni di controllo selettivo correnti che, inizialmente, possono essere prive di valori. I modi per popolare i parametri del controllo selettivo sono due: immettere manualmente i singoli parametri dalla riga di comando oppure specificare più parametri importando un file con le impostazioni del controllo per utente.
  
La sintassi di Audituser.exe è la seguente:
  
<codesnippet language displaylanguage containsmarkup="false">Audituser.exe /parametro accountutente:”categoria”  
```  
(o un elenco di categorie delimitate da virgole).
  
Ad esempio, per attivare il controllo delle operazioni non riuscite per le categorie relative agli eventi di sistema e agli accessi/disconnessioni dell'account LocalUser, è necessario immettere il seguente comando:
  
<codesnippet language displaylanguage containsmarkup="false">Audituser /if LocalUser:”Evento di sistema”,”Accesso/Disconnessione"  
```  
I parametri che è possibile specificare dalla riga di comando sono i seguenti:
  
-   **/is** – aggiunge o modifica una voce per l'inclusione delle operazioni riuscite
  
-   **/if** – aggiunge o modifica una voce per l'inclusione delle operazioni non riuscite
  
-   **/es** – aggiunge o modifica una voce per l'esclusione delle operazioni riuscite
  
-   **/es** – aggiunge o modifica una voce per l'esclusione delle operazioni non riuscite
  
-   **/r** – rimuove tutte le voci del controllo per utente di uno specifico account utente
  
-   **/ra** – rimuove tutte le voci del controllo per utente di tutti gli account utente
  
-   **/e** – esporta le impostazioni nel file specificato
  
-   **/i** – importa le impostazioni dal file specificato
  
Un file delle impostazioni del controllo per utente è un file di solo testo nel formato illustrato nella figura che segue.
  
![](images/Cc875806.SMAAD6(it-it,TechNet.10).gif)
  
**Figura 6. Esempio di file Auditusr.exe di importazione**
  
**Nota**   Perché l'importazione riesca, il file di importazione deve iniziare con la riga “Auditusr 1.0”, come indicato nella figura.
  
Il comando per importare il file delle impostazioni di controllo illustrato nella figura precedente dovrebbe essere:
  
<codesnippet language displaylanguage containsmarkup="false">Audituser /i percorso\\audit.txt  
```  
È possibile utilizzare questa utilità per stabilire le soglie per le informazioni della registrazione di controllo e ridurre così i requisiti di memoria e aumentare la probabilità di rilevare i tentativi di intrusione.
  
##### Correlazione tra le violazioni dei criteri di protezione e gli eventi di controllo
  
Anche se questa sezione non fa distinzioni tra le violazioni dei criteri causate da origini esterne o interne, è importante tenere presente che le violazioni interne possono essere per un'azienda altrettanto devastanti degli attacchi provenienti dall'esterno. Come precedentemente sottolineato in questo documento, una percentuale significativa degli attacchi dannosi hanno un origine interna e questa percentuale non include i danni accidentali causati dall'utilizzo inappropriato di privilegi elevati al di fuori dell'ambito procedurale stabilito.
  
A causa dei rischi correlati all'abuso accidentale o intenzionale di privilegi elevati da parte di origini interne, è importante stabilire criteri e procedure sull'utilizzo appropriato di tali privilegi e stabilire gli itinerari di controllo per la correlazione incrociata. Una volta istituiti un processo di gestione delle modifiche e un criterio di documentazione, è possibile sviluppare una correlazione che colleghi le informazioni di controllo agli eventi approvati e non approvati, facilitando così la capacità di rilevare i comportamenti sospetti all'interno dell'azienda. Questa sezione illustra come sviluppare questa correlazione descrivendo i diversi tipi di evento che è possibile registrare e il modo in cui questi possono influire su criteri e processi.
  
###### Accesso a computer non autorizzati
  
Il personale che si occupa di amministrazione e supporto utilizza sempre più servizi di gestione remota, ad esempio i Servizi terminal, per collegarsi ai sistemi remoti e gestirli. Questi sistemi andrebbero monitorati per controllare i tentativi di accesso interattivi e ogni tentativo di connessione dovrebbe essere esaminato per verificarne la validità. Questi controlli dovrebbero effettuare le seguenti azioni:
  
-   Identificare gli accessi con account di servizio.
  
-   Registrare i tentativi di accesso da parte di account utente non autorizzati.
  
-   Analizzare i tentativi provenienti da aree geografiche insolite.
  
-   Creare l'elenco dei tentativi effettuati da intervalli di indirizzi IP esterni.
  
Particolare attenzione dovrebbe essere rivolta al monitoraggio delle risorse di elevato valore. Queste risorse critiche dovrebbero risiedere su server specifici, configurati con impostazioni restrittive per il monitoraggio e il controllo dell'accesso.
  
La tabella che segue elenca gli eventi di controllo dell'accesso, da confrontare con gli elenchi degli account autorizzati se rilevati in sistemi di risorse di elevato valore.
  
**Tabella 3. Eventi di utilizzo di computer non autorizzati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">528</td>
<td style="border:1px solid black;">Accesso riuscito</td>
<td style="border:1px solid black;">Controllare il nome della workstation e il nome dell'account utente. Assicurarsi che l'indirizzo di rete dell'origine si trovi all'interno di una rete.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">529</td>
<td style="border:1px solid black;">Accesso non riuscito - Nome utente sconosciuto o password non valida</td>
<td style="border:1px solid black;">Controllare i tentativi in cui il nome dell'account di destinazione corrisponde a un account amministrativo o all'account amministrativo predefinito rinominato. Controllare anche la presenza di più accessi non riusciti sotto il limite di blocco dell'account.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">530</td>
<td style="border:1px solid black;">Accesso non riuscito - Violazione della restrizione sull'orario di accesso.</td>
<td style="border:1px solid black;">Indica un tentativo di accesso al di fuori dell'orario consentito. Controllare il nome dell'account utente e il nome della workstation.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">531</td>
<td style="border:1px solid black;">Accesso non riuscito - Account correntemente disattivato</td>
<td style="border:1px solid black;">Controllare il nome della workstation e il nome dell'account di destinazione. Questo evento può segnalare tentate intrusioni da parte di ex dipendenti e richiede un'indagine approfondita.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">532</td>
<td style="border:1px solid black;">Accesso non riuscito - L'account utente specificato è scaduto</td>
<td style="border:1px solid black;">Controllare il nome della workstation e il nome dell'account di destinazione. Questo evento può segnalare tentati abusi da parte di lavoratori assunti con incarico temporaneo o a contratto e richiede un'indagine approfondita.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">533</td>
<td style="border:1px solid black;">Accesso non riuscito - Utente non autorizzato ad accedere a questo computer</td>
<td style="border:1px solid black;">Indica il tentativo di accesso a workstation con restrizioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">534</td>
<td style="border:1px solid black;">Accesso non riuscito - Tipo di accesso non consentito</td>
<td style="border:1px solid black;">Controllare il tipo di accesso, il nome della workstation e il nome dell'account di destinazione. Questo evento indica un tentativo fallito di accedere interattivamente con le credenziali di un account di servizio anche se le impostazioni di Criteri di gruppo impediscono l'accesso interattivo con tali account.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">535</td>
<td style="border:1px solid black;">Accesso non riuscito - La password dell'account specificato è scaduta</td>
<td style="border:1px solid black;">Indica che un utente sta tentando l'accesso con un account la cui password è scaduta. Se l'evento si ripete senza che vengano registrate una modifica della password o una richiesta di supporto, può richiedere un'indagine immediata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">536</td>
<td style="border:1px solid black;">Accesso non riuscito - La componente NetLogon non è attiva</td>
<td style="border:1px solid black;">Assicurarsi che il servizio NetLogon sia in funzione. Se il servizio è in funzione, è richiesta un'indagine immediata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">540</td>
<td style="border:1px solid black;">Accesso riuscito</td>
<td style="border:1px solid black;">Questo evento è l'equivalente di rete dell'evento 528.</td>
</tr>
</tbody>
</table>
  
###### Trojan horse, rootkit e malware
  
L'evento 592 è particolarmente utile per rilevare la presenza di trojan horse, rootkit e altro malware, poiché viene generato ogni volta che viene avviato un nuovo processo. La presenza di questo evento richiede un'indagine immediata se il nome del file di immagine non corrisponde ad alcuno dei processi presenti nell'elenco dei programmi approvati.
  
Al contrario dei trojan horse e dei keystroke logger che sono relativamente facili da identificare, i rootkit agiscono in modo più subdolo. Possono essere identificati rilevando programmi sconosciuti che vengono avviati e arrestati in rapida successione. Se, però, un rootkit viene avviato, il sistema operativo non ha modo di identificarlo quindi non genera altri eventi.
  
I tentativi operati da un malware possono assumere la forma di allegati e-mail o siti Web infetti e possono provare ad acquisire privilegi più elevati se l'account che li esegue non dispone dei diritti richiesti per lanciare nuovi programmi. In questi casi, il software non autorizzato dovrebbe generare un evento di operazione non riuscita che andrebbe analizzato, soprattutto in presenza delle seguenti circostanze:
  
-   **Proliferazione di processi come LocalSystem**. I processi eseguiti come LocalSystem dovrebbero essere chiaramente definiti in un elenco di programmi approvati e possono includere processi quali Services.exe.
  
-   **Proliferazione di processi in orari inaspettati**. Se il sistema monitorato non utilizza processi batch pianificati, è necessario indagare sul verificarsi di alcune attività quali backup, CGI o script. Un'indagine è necessaria anche se tali eventi sono previsti ma si verificano in orari diversi da quelli pianificati.
  
**Tabella 4. Evento 592**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">592</td>
<td style="border:1px solid black;">Creazione di un nuovo processo</td>
<td style="border:1px solid black;">Controllare le voci relative al nome del file di immagine e al nome utente per verificare la presenza di processi non approvati, orari di avvio inaspettati o l'avvio e l'arresto in rapida successione di programmi sconosciuti.</td>
</tr>
</tbody>
</table>
  
###### Accedere alle risorse modificando le autorizzazioni per i file
  
È possibile utilizzare i privilegi amministrativi per accedere a file il cui accesso sarebbe normalmente negato modificando la proprietà dei dati e aggiungendo account all'elenco delle autorizzazioni in lettura per questi dati. È anche possibile nascondere questa attività in Windows Server 2003 ripristinando le impostazioni originali di proprietà e autorizzazioni.
  
L'identificazione di dati e risorse di elevato valore è molto importante, poiché sarebbe controproducente implementare il controllo dell'accesso agli oggetti per ogni file di una rete aziendale di medie dimensioni a causa della variabilità del volume di accessi che si verificano ogni giorno. Il controllo dell'accesso agli oggetti dovrebbe essere abilitato per i file e le cartelle sensibili. Le voci ACL non sono sufficienti come difesa contro i tentativi di accesso non autorizzato.
  
Per un'efficiente identificazione delle attività illecite è necessario rendere facilmente identificabili i seguenti fattori per tutti i file di elevato valore:
  
-   Quale oggetto è stato l'obiettivo del tentativo di accesso?
  
-   Quale account è stato utilizzato per richiedere l'accesso?
  
-   Quale account ha autorizzato l'accesso?
  
-   Che tipo di accesso è stato tentato?
  
-   L'evento è stato costituito da un'operazione riuscita o non riuscita?
  
-   Quale sistema è stato utilizzato per lanciare il tentativo?
  
Il visualizzatore eventi predefinito non dispone delle impostazioni di filtraggio sufficienti a identificare queste informazioni. Pertanto, per poter eseguire questa analisi, è necessario utilizzare EventCombMT o un altro meccanismo del genere.
  
Gli eventi di accesso agli oggetti riportati nella tabella che segue sono riferiti a tentativi di questa natura.
  
**Tabella 5. Eventi di modifica delle autorizzazioni per i file**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">560</td>
<td style="border:1px solid black;">Accesso concesso all'oggetto esistente</td>
<td style="border:1px solid black;">Indica la riuscita di una richiesta di concessione di accesso a un oggetto. Controllare l'ID di accesso primario, il nome utente del client e il nome utente primario per identificare l'accesso non autorizzato. Controllare il campo relativo agli accessi per determinare il tipo di operazione. Questo evento rileva solo le richieste di accesso e non indica se l'accesso si è realmente verificato o no.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">567</td>
<td style="border:1px solid black;">Utilizzata un'autorizzazione associata a un handle</td>
<td style="border:1px solid black;">Indica la prima istanza di un tipo di accesso a un oggetto e, se il campo relativo all'accesso include &quot;WRITE_DAC&quot;, che le autorizzazioni sono state modificate. Correlare con l'evento 560 confrontando i campi contenenti gli ID degli handle.</td>
</tr>
</tbody>
</table>
  
###### Accedere alle risorse reimpostando le password
  
Le modifiche alle password dovrebbero verificarsi solo nell'ambito di una struttura approvata di procedure consolidate. Livelli di controllo correttamente configurati dovrebbero registrare gli eventi di gestione account mostrati nella tabella che segue e correlare tali eventi con le procedure registrate per identificare le attività non conformi a tali procedure.
  
**Tabella 6. Eventi di reimpostazione delle password**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">627</td>
<td style="border:1px solid black;">Tentativo di modifica password</td>
<td style="border:1px solid black;">Indica una richiesta di modifica della password in cui il richiedente ha fornito la password originale. Confrontare il nome account primario con il nome account di destinazione per determinare se l'account richiedente è l'account modificato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">628</td>
<td style="border:1px solid black;">Impostazione o reimpostazione password dell'account utente</td>
<td style="border:1px solid black;">Indica la reimpostazione di una password eseguita da un'interfaccia amministrativa e non da un processo di modifica della password. Il richiedente dovrebbe essere un account autorizzato, ad esempio un account per l'help desk o per la reimpostazione self-service delle password.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">698</td>
<td style="border:1px solid black;">Modifica password per modalità di ripristino servizi di directory</td>
<td style="border:1px solid black;">Indica un tentativo di modificare la password per la modalità di ripristino dei servizi di directory su un controller di dominio. Controllare il nome account e l'IP della workstation. Questo evento richiede un'indagine immediata.</td>
</tr>
</tbody>
</table>
  
###### Modifica degli account utente
  
Qualsiasi modifica agli account (aggiunta, eliminazione o modifica) dovrebbe corrispondere a un processo consolidato che comporta l'avvio di un processo logico in più passaggi da parte di una richiesta ufficiale di un dipendente di livello dirigenziale. Tutti gli eventi della tabella riportata di seguito dovrebbero corrispondere a una richiesta ufficiale di modifica account. In caso contrario devono essere sottoposti a un'indagine immediata.
  
**Tabella 7. Eventi di modifica degli account utente**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">624</td>
<td style="border:1px solid black;">Creazione di un account utente</td>
<td style="border:1px solid black;">Indica che si è verificata la creazione di un account di rete.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">630</td>
<td style="border:1px solid black;">Eliminazione di un account utente</td>
<td style="border:1px solid black;">Indica che si è verificata l'eliminazione di un account di rete.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">642</td>
<td style="border:1px solid black;">Modifica di un account utente</td>
<td style="border:1px solid black;">Indica modifiche ad account utente di protezione non coperte dagli eventi 627-630.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">685</td>
<td style="border:1px solid black;">Modifica del nome di un account utente</td>
<td style="border:1px solid black;">Indica la modifica del nome di un account utente.</td>
</tr>
</tbody>
</table>
  
Per un'efficace identificazione dei problemi relativi alla gestione degli account, è necessario configurare query atte a:
  
-   Rilevare attività irregolari o inusuali sugli account.
  
-   Identificare gli account di tipo amministrativo che abusano dei privilegi per creare o modificare account.
  
-   Rilevare modelli di attività sugli account che non sono conformi ai criteri di protezione aziendali.
  
È anche importante confermare l'intervallo tra la creazione di un account e il primo accesso e la modifica della password. Se il nuovo account non viene utilizzato nell'intervallo previsto (un processo di creazione degli account registra di norma la data di inizio di un nuovo utente), è necessario disabilitare l'account e avviare un'indagine per scoprire il motivo del ritardo.
  
###### Modifiche all'appartenenza a un gruppo
  
Una buona prassi di protezione si basa sul principio del minimo privilegio, ovvero sul concedere agli account il livello di accesso minimo richiesto per l'esecuzione delle loro funzioni. Se si applica questa prassi, la maggior parte degli account diventano membri del gruppo predefinito Domain Users con appartenenza aggiuntiva a gruppi di protezione aziendale specifici.
  
Le modifiche all'appartenenza a un gruppo di protezione dovrebbero essere apportate solo nel rispetto di linee guida consolidate, soprattutto se si tratta di account con privilegi elevati. Queste modifiche dovrebbero essere eseguite solo da account creati per la gestione degli account, e tali eventi dovrebbero essere correlati a un processo consolidato per le modifiche di questo tipo. Qualsiasi modifica che non rientri in tale processo dovrebbe richiedere un'indagine immediata.
  
Gli eventi di controllo relativi alla gestione degli account e riportati nella tabella che segue illustrano in dettaglio le modifiche all'appartenenza ai gruppi.
  
**Tabella 8. Eventi di modifica dell'appartenenza ai gruppi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">631, 632,<br />
633, 634</td>
<td style="border:1px solid black;">Cambiato gruppo globale protetto</td>
<td style="border:1px solid black;">Esaminare il campo relativo al nome account di destinazione per determinare se il gruppo modificato era globale o disponeva di ampi privilegi di accesso.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">635, 636,<br />
637, 638</td>
<td style="border:1px solid black;">Cambiato gruppo locale protetto</td>
<td style="border:1px solid black;">Esaminare il campo relativo al nome dell'account di destinazione per determinare se il gruppo modificato era un gruppo Administrators, Server Operators o Backup Operators.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">639, 641,<br />
668</td>
<td style="border:1px solid black;">Cambiato gruppo protetto</td>
<td style="border:1px solid black;">Indica una modifica a un gruppo diversa da una modifica di eliminazione, creazione o modifica dell'appartenenza. Esaminare il nome dell'account di destinazione per assicurarsi che non sia stato alterato un gruppo con elevati privilegi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">659, 660, 661, 662</td>
<td style="border:1px solid black;">Cambiato gruppo universale protetto</td>
<td style="border:1px solid black;">Esaminare il nome dell'account di destinazione per assicurarsi che non sia stato alterato un gruppo con elevati privilegi, ad esempio Enterprise Admins.</td>
</tr>
</tbody>
</table>
  
**Nota**   L'appartenenza a un gruppo di distribuzione non fornisce l'accesso alle risorse di rete poiché questo tipo di gruppo non è basato su principi di protezione. L'appartenenza ad alcuni gruppi di distribuzione, tuttavia, può creare problemi di sicurezza, a seconda del gruppo. Ad esempio, l'inserimento di account utente in un gruppo di distribuzione gestionale o esecutivo può far sì che un utente riceva messaggi e-mail inappropriati per la sua posizione.
  
###### Tentativi di utilizzo di account non autorizzati
  
La promozione del primo controller di dominio Active Directory in una foresta crea un account di amministrazione che è membro sia del gruppo Domain Admin che del gruppo Enterprise Admin. Questo account richiede una protezione particolare, poiché è l'unico non interessato dalle impostazioni di blocco degli account. Pertanto, anche quando viene applicato un criterio di blocco degli account, questo account rimane particolarmente vulnerabile agli attacchi con dizionario.
  
Un monitoraggio della protezione davvero efficace dovrebbe essere in grado di identificare tutti i tentativi di accesso con questo account di amministrazione, anche se l'account è stato rinominato. Per ulteriori informazioni su come configurare i servizi in modo che vengano eseguiti in modalità protetta, vedere la [*Guida alla pianificazione della protezione degli account amministrativi*](http://technet.microsoft.com/it-it/library/cc162797) all'indirizzo http://technet.microsoft.com/it-it/library/cc162797.
  
Inoltre, i tentativi di accesso con account disabilitati o scaduti possono indicare che un ex dipendente o un lavoratore con incarico temporaneo o a contratto ha cercato di accedere alla rete senza disporre delle credenziali richieste. Tali eventi richiedono un'indagine immediata.
  
La tabella che segue elenca gli eventi che identificano un utilizzo non autorizzato degli account e fanno parte delle categorie di controllo relative all'accesso e all'accesso account.
  
**Tabella 9. Eventi di accesso non autorizzato**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">528
540</td>
<td style="border:1px solid black;">Accesso riuscito</td>
<td style="border:1px solid black;">L'evento 528 è un evento comune. L'evento 540, invece, richiede il controllo del nome dell'account di destinazione per determinare se è stato causato dall'account amministrativo predefinito.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">529</td>
<td style="border:1px solid black;">Accesso non riuscito - Nome utente sconosciuto o password non valida</td>
<td style="border:1px solid black;">Eseguire sempre un'indagine se il nome dell'account di destinazione corrisponde a un account amministrativo o all'account amministrativo predefinito rinominato. Un'indagine è richiesta anche se gli accessi riusciti sono appena sotto il limite di blocco dell'account. Controllare anche i tentativi in cui il nome dell'account di destinazione corrisponde a un account amministrativo o radice e se il nome del dominio è sconosciuto.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">531</td>
<td style="border:1px solid black;">Accesso non riuscito - Account disattivato</td>
<td style="border:1px solid black;">Esaminare il nome della workstation e il nome dell'account di destinazione per determinare l'origine. Questo evento richiede un'indagine poiché potrebbe essere un tentativo di intrusione da parte di ex dipendenti.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">532</td>
<td style="border:1px solid black;">Accesso non riuscito - Account scaduto</td>
<td style="border:1px solid black;">Esaminare il nome della workstation e il nome dell'account di destinazione per determinare l'origine. Questo evento richiede un'indagine poiché potrebbe essere un tentativo di intrusione da parte di ex dipendenti.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">576</td>
<td style="border:1px solid black;">Privilegi speciali assegnati al nuovo accesso</td>
<td style="border:1px solid black;">Indica l'assegnazione di un privilegio ovvero l'assegnazione a un nuovo account di privilegi amministrativi o della capacità di modificare l'itinerario di controllo. Confrontare il campo dell'ID accesso con gli eventi 528 o 540 per determinare facilmente se un account è riuscito a ottenere privilegi amministrativi.</td>
</tr>
</tbody>
</table>
  
Un altro problema di protezione relativo all'utilizzo non autorizzato delle credenziali degli account nasce dall'impiego di criteri di gestione delle password particolarmente restrittivi, quali l'uso di password complesse o di scadenze brevi. A volte gli utenti annotano o registrano in qualche modo le password per poterle ricordare. Questo problema è di particolare rilievo negli ambienti caratterizzati da un elevato numero di archivi di dati identificativi privi di servizi di gestione delle identità, che richiedono l'utilizzo di più password e account.
  
**Nota**   Per informazioni sulla gestione delle password negli ambienti eterogenei, vedere [Microsoft Identity and Access Management Series](http://go.microsoft.com/fwlink/?linkid=14841) (in inglese) all'indirizzo http://go.Microsoft.com/fwlink/?LinkId=14841.
  
Le organizzazioni devono evitare che gli utenti registrino le loro password, soprattutto utilizzando metodi poco sicuri, poiché persone non autorizzate potrebbero scoprire queste informazioni e utilizzarle per lanciare un attacco. Il monitoraggio di questo tipo di intrusione è possibile grazie alle informazioni della tabella precedente, ma comporta la correlazione incrociata di queste informazioni con la cronologia degli accessi riusciti per l'account utente in questione, al fine di creare un elenco delle workstation a cui tale account può accedere e poter effettuare un confronto.
  
**Nota**   È possibile limitare gli account utente all'uso di specifiche workstation utilizzando la funzionalità Active Directory predefinita. Tuttavia, per poter utilizzare questa funzionalità è necessario che la rete supporti il sistema di denominazione NetBIOS (Network Basic Input/Output System) fornito, ad esempio, da Windows Internet Naming Service (WINS).
  
###### Accesso interattivo con credenziali di account di servizio
  
Quando un servizio viene avviato, deve presentare le credenziali di accesso. A volte, alcuni servizi richiedono l'utilizzo di un account di dominio per eseguire servizi o connettersi a computer remoti. Alcuni servizi possono richiedere addirittura credenziali amministrative o devono interagire anche con il desktop.
  
In Windows Server 2003 e versioni successive, alcuni account di servizio (ad esempio, il servizio Avvisi) possono essere avviati con l'opzione **–LocalService**. Inoltre, i servizi che richiedono la connettività di rete possono utilizzare l'account del servizio di rete NT AUTHORITY\\Network Service. Tutti i servizi che richiedono gli account utente dovrebbero essere controllati per assicurarsi che gli account utilizzati siano protetti da password complesse. Il monitoraggio della protezione dovrebbe confermare che gli eventi di accesso relativi a tali account si verifichino solo quando vengono avviati i servizi associati. Per ulteriori informazioni su come aumentare la protezione degli account di servizio, vedere la [*Guida alla pianificazione della protezione dei servizi e degli account dei servizi*](http://technet.microsoft.com/it-it/library/dd550631.aspx) all'indirizzo http://technet.microsoft.com/it-it/library/dd550631.aspx.
  
Il principale problema di protezione per gli account di servizio si verifica quando tali account effettuano l'accesso in modalità interattiva anziché come servizio. Tali eventi si verificano solo se un account di servizio è stato compromesso da un intruso che effettua l'accesso con l'account in questione. Se l'account di servizio compromesso dispone di privilegi amministrativi, l'intruso ha ottenuto l'accesso a capacità importanti e può danneggiare il normale funzionamento dei servizi di rete.
  
Tutte le risorse a cui questo account di servizio può accedere dovrebbero essere identificate e non dovrebbero disporre di alcuna autorizzazione non motivata ad accedere a dati di elevato valore. Ad esempio, un account di servizio potrebbe richiedere occasionalmente l'accesso in scrittura a una directory di file registro, cosa che generalmente non succede. Anche gli account di servizio che possono interagire con il desktop richiedono una particolare attenzione poiché offrono maggiori opportunità di exploit agli attacker.
  
La tabella che segue elenca gli eventi relativi ad accesso utente e controllo accesso che identificano l'utilizzo non autorizzato delle credenziali di un account di servizio.
  
**Tabella 10. Eventi di accesso con credenziali di account di servizio**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">528</td>
<td style="border:1px solid black;">Accesso riuscito - Accesso da console o Servizi terminal</td>
<td style="border:1px solid black;">Indica che è in corso un attacco se il tipo di accesso è 10, se è coinvolto un account di servizio o se l'account di sistema locale è associato a questo evento. Questo evento richiede un'indagine immediata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">534</td>
<td style="border:1px solid black;">Accesso non riuscito - Tipo di accesso non consentito</td>
<td style="border:1px solid black;">Questo evento indica un tentativo fallito di accedere interattivamente con le credenziali di un account di servizio anche se le impostazioni di Criteri di gruppo lo vietano. Se si verifica questo evento, controllare il tipo di accesso, il nome della workstation e il nome dell'account di destinazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">600</td>
<td style="border:1px solid black;">Al processo è stato assegnato un token primario</td>
<td style="border:1px solid black;">Indica che un servizio sta utilizzando un account denominato per accedere a un sistema che esegue Windows XP o versioni successive. Correlare questo evento con le informazioni relative agli eventi 672, 673, 528 e 592 per indagare.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">601</td>
<td style="border:1px solid black;">Un utente ha tentato di installare un servizio</td>
<td style="border:1px solid black;">Questo evento non dovrebbe verificarsi spesso in un ambiente aziendale che dispone di criteri accettabili e ben definiti per le applicazioni e di un processo di standardizzazione del sistema. Se in un ambiente di questo tipo non vi è alcuna correlazione con i processi di controllo delle modifiche, questo evento richiede un'indagine immediata.</td>
</tr>
</tbody>
</table>
  
###### Esecuzione di programma non autorizzato
  
Gli account di livello amministrativo sono in grado di installare ed eseguire programmi e vengono quindi assegnati solo a personale fidato che ha bisogno di queste capacità per svolgere il proprio lavoro. A causa dei rischi associati al software non testato, è importante approntare un elenco dei software approvati e utilizzati su licenza e un processo per richiedere, testare e approvare le nuove applicazioni. Le applicazioni non approvate dovrebbero essere limitate a un ambiente di test isolato e non dovrebbero essere installate in un ambiente di rete di produzione in assenza di un processo di controllo delle modifiche consolidato. Anche in questo caso, dovrebbero essere autorizzate solo dopo essere state aggiunte a un elenco di software approvati.
  
La tabella che segue elenca gli eventi di registrazione dei processi che possono identificare l'utilizzo di programmi non autorizzati.
  
**Tabella 11. Eventi di esecuzione di programmi non autorizzati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">592</td>
<td style="border:1px solid black;">Creazione di un nuovo processo</td>
<td style="border:1px solid black;">Indica che è stato creato un nuovo processo. Esaminare i campi relativi al nome del file di immagine e al nome utente e confrontarli con l'elenco dei programmi autorizzati se l'azienda ha consolidati i criteri per i programmi autorizzati. Verificare la presenza di istanze in cui LocalSystem è utilizzato per lanciare un prompt dei comandi, poiché questo è un metodo molto diffuso per evitare la registrazione in un itinerario di controllo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">602</td>
<td style="border:1px solid black;">Creazione di un processo pianificato</td>
<td style="border:1px solid black;">Esaminare il nome di destinazione e l'ora dell'attività se tali eventi si verificano in orari inaspettati.</td>
</tr>
</tbody>
</table>
  
**Nota**   I controlli della protezione effettuati mediante registrazione dei processi sono in grado di identificare i programmi non autorizzati. La registrazione dei programmi, tuttavia, genera molte voci nel registro di protezione, quindi è necessario stare attenti al fatto che il numero degli eventi non sovraccarichi i meccanismi di identificazione della protezione.
  
###### Accesso a risorse non autorizzate
  
La tabella che segue riporta gli eventi di controllo di accesso agli oggetti che riguardano tentativi di accesso a risorse che l'utente non è autorizzato a utilizzare.
  
**Tabella 12. Eventi di tentativo di accesso a risorse non autorizzate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">560</td>
<td style="border:1px solid black;">Accesso rifiutato all'oggetto esistente</td>
<td style="border:1px solid black;">Esaminare il campo relativo al nome dell'oggetto per stabilire la risorsa a cui si è tentato di accedere e correlare il nome utente primario e il dominio primario o il nome utente del client e il dominio del client per determinare l'origine.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">568</td>
<td style="border:1px solid black;">Tentativo di creazione di un collegamento reale a un file controllato</td>
<td style="border:1px solid black;">Indica che un utente o un programma hanno tentato di creare un collegamento reale a un file o a un oggetto. Un collegamento reale permette a un account di manipolare un file senza creare un itinerario di controllo se l'account dispone dei diritti per l'oggetto in questione.</td>
</tr>
</tbody>
</table>
  
###### Utilizzo di sistemi operativi non autorizzati
  
L'utilizzo di sistemi operativi non autorizzati può causare notevoli problemi che vanno dalla riduzione della protezione agli exploit delle vulnerabilità, fino all'elevata probabilità di danneggiamento dei dati nei file system. Amministratori e utenti possono introdurre in una rete sistemi operativi non autorizzati avvalendosi dei seguenti metodi:
  
-   Personal computer collegati alla rete in modalità locale o remota.
  
-   Utilizzo di sistemi operativi avviabili da CD.
  
-   Reinstallazione di un sistema operativo Windows.
  
-   Utilizzo di immagini di PC virtuali.
  
I criteri aziendali possono specificare la modalità con cui gli utenti possono connettersi alla rete dalle località remote attraverso una rete privata virtuale o un servizio di accesso remoto e includono i requisiti per la connessione dei sistemi, quali il tipo di sistema operativo, il livello di aggiornamento e l'installazione di misure protettive come firewall personali e software antivirus. Per ulteriori informazioni su come garantire la conformità dei sistemi remoti ai criteri di protezione aziendali, vedere [*Implementing Quarantine Services with Microsoft Virtual Private Network Planning Guide*](http://go.microsoft.com/fwlink/?linkid=41307) (in inglese) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=41307.
  
Gli utenti possono anche utilizzare i CD di installazione di Windows XP e riavviare i propri computer per installare un sistema operativo non gestito. In questi casi può essere possibile individuare questo tipo di attività localizzando i tentativi di accesso da un account amministrativo con un nome di gruppo di lavoro non identificato o con il nome del gruppo di lavoro predefinito.
  
**Nota**   Alcune distribuzioni open source sono disponibili in formato avviabile da CD e consentono di utilizzare il sistema operativo senza installarlo su un sistema locale. Poiché il sistema operativo non viene effettivamente installato sul computer locale, è difficile individuare questa attività. In ogni caso, tentativi di accesso da parte di un account utente "principale" in un ambiente di rete omogeneo o da parte di nomi computer inaspettati possono indicare la presenza di un sistema operativo non autorizzato. È possibile prevenire questo tipo di attività disabilitando la capacità di avvio da CD nelle impostazioni del BIOS del computer e proteggendo con una password la configurazione BIOS, anche se questo approccio potrebbe non essere applicabile ad alcuni ambienti.
  
Le immagini di PC virtuali offrono un'emulazione completa di un ambiente computer in un computer host. Questa emulazione esegue il suo sistema operativo con i suoi nome computer, account utente, struttura di servizi di directory e programmi in un ambiente virtuale. Un'istanza di PC virtuale è anche in grado di avviarsi, eseguirsi e arrestarsi in modo indipendente dal sistema host, pertanto è poco probabile che generi eventi di controllo su questo sistema. Questa capacità del PC virtuale, unita alla possibilità di collegarsi alla rete dell'host, ottenere gli indirizzi IP ed eseguire il mapping delle unità condivise, presenta un certo numero di rischi di protezione che vanno dalla maggiore vulnerabilità delle password alla maggiore vulnerabilità agli exploit, poiché è difficile che sia controllata da un processo di aggiornamento consolidato e reso operativo nella rete. Dati i rischi che i PC virtuali presentano, è importante limitare l'uso di questo tipo di software a personale autorizzato e stabilire processi documentati per la creazione e l'utilizzo delle istanze di PC virtuale.
  
Per poter individuare l'utilizzo di sistemi operativi non autorizzati, una soluzione di monitoraggio della protezione deve essere in grado di rilevare quanto segue:
  
-   Account utente, nomi di computer, gruppi di lavoro o nomi di dominio non riconosciuti.
  
-   Indirizzi IP duplicati o non compresi nell'intervallo consentito.
  
-   Tentativi di accesso mediante l'account di amministrazione predefinito.
  
Gli eventi relativi alla registrazione dei processi e riportati nella tabella che segue possono aiutare a rilevare l'utilizzo di sistemi operativi non autorizzati.
  
**Tabella 13. Eventi di utilizzo di piattaforme non autorizzate**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">529</td>
<td style="border:1px solid black;">Accesso non riuscito - Nome utente sconosciuto o password non valida</td>
<td style="border:1px solid black;">Controllare i tentativi in cui il nome dell'account di destinazione corrisponde a un account amministrativo o principale e se il nome del dominio è sconosciuto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">533</td>
<td style="border:1px solid black;">Accesso non riuscito - Utente non autorizzato ad accedere a questo computer</td>
<td style="border:1px solid black;">Indica il tentativo di accesso a workstation con restrizioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">592</td>
<td style="border:1px solid black;">Creazione di un nuovo processo</td>
<td style="border:1px solid black;">Controllare i campi relativi al nome del file di immagine e al nome utente per assicurarsi che il programma sia autorizzato a essere utilizzato dall'account in questione.</td>
</tr>
</tbody>
</table>
  
###### Creare o interrompere le relazioni di trust
  
Le relazioni di trust permettono agli account di un dominio di accedere alle risorse residenti in un dominio diverso. Ovviamente, la creazione delle relazioni di trust non è un'operazione di routine e deve essere eseguita solo nell'ambito di un processo di controllo delle modifiche consolidato. Anche l'interruzione delle relazioni di trust è un'attività che dovrebbe essere eseguita solo dopo essere stata approvata da un processo di controllo delle modifiche e dopo un'attenta considerazione degli effetti dell'azione sulla rete.
  
Gli eventi di controllo relativi alla modifica dei criteri e riportati nella tabella che segue consentono di identificare le attività inerenti le relazioni di trust.
  
**Tabella 14. Eventi di modifica delle relazioni di trust**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">610<br />
611<br />
620</td>
<td style="border:1px solid black;">Una relazione di trust con un altro dominio è stata creata, eliminata o modificata</td>
<td style="border:1px solid black;">Questi eventi vengono generati dal controller di dominio che ha stabilito la relazione di trust. Questo evento richiede un'indagine immediata se non è correlato a un processo di controllo delle modifiche consolidato. Esaminare il campo relativo al nome utente per determinare l'account del richiedente.</td>
</tr>
</tbody>
</table>
  
###### Modifiche non autorizzate ai criteri di protezione
  
Le modifiche alle impostazioni approvate per i criteri di protezione dovrebbero avere luogo solo nell'ambito di un processo di controllo delle modifiche consolidato. Qualsiasi modifica che non rientri in tale processo di approvazione dovrebbe richiedere un'indagine immediata.
  
Le modifiche di questo tipo includono le modifiche a quanto segue:
  
-   Impostazioni di Criteri di gruppo
  
    -   Criteri password dell'account utente
  
    -   Criteri di blocco degli account utente
  
    -   Criteri di controllo
  
    -   Impostazioni del registro eventi applicabili al registro degli eventi di protezione
  
    -   Criteri IPSec
  
    -   Criteri di rete wireless (IEEE 802.1x)
  
    -   Criteri di chiave pubblica ed EFS (Encrypting File System)
  
    -   Criteri per la restrizione nell’uso del software applicativo
  
-   Impostazioni protezione
  
    -   Impostazioni dei diritti utente
  
    -   Criteri password dell'account utente
  
    -   Opzioni di protezione
  
L'elenco sopra riportato rappresenta solo i requisiti minimi, poiché la maggior parte delle aziende utilizza in genere anche altre impostazioni dei criteri di gruppo nel suo ambiente. I controlli di protezione dovranno identificare i tentativi di modifica delle impostazioni sia riusciti che non riusciti, poiché i tentativi riusciti dovrebbero corrispondere ad account dotati dell'autorizzazione necessaria ad apportare queste modifiche, come previsto dal processo di controllo consolidato.
  
La tabella che segue elenca gli eventi di controllo relativi alle modifiche dei criteri che identificano le modifiche a Criteri di gruppo e ai criteri del sistema locale.
  
**Tabella 15. Eventi di modifica dei criteri**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">612</td>
<td style="border:1px solid black;">Modifica dei criteri di controllo</td>
<td style="border:1px solid black;">Indica una modifica dei criteri di controllo. Questi eventi dovrebbero essere correlati con i criteri di controllo delle modifiche consolidati per determinare se le modifiche sono autorizzate o no.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">613<br />
614<br />
615</td>
<td style="border:1px solid black;">Modifica dei criteri IPSec</td>
<td style="border:1px solid black;">Indica una modifica dei criteri IPsec. Richiedono un'indagine se l'evento non si verifica all'avvio del sistema.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">618</td>
<td style="border:1px solid black;">Criteri recupero dati crittografati</td>
<td style="border:1px solid black;">Questi eventi si verificano quando sono in uso i criteri di recupero dei dati crittografati. Qualsiasi modifica che non rientri nei criteri specificati dovrebbe richiedere un'indagine immediata.</td>
</tr>
</tbody>
</table>
  
**Nota**   Per ulteriori informazioni sulle impostazioni di Criteri di gruppo, vedere la sezione "[Security Policy Settings](http://technet2.microsoft.com/windowsserver/en/library/bcd7ea4c-f989-4cee-969a-920f62f555111033.mspx?mfr=true)" (in inglese) all'indirizzo http://technet2.microsoft.com/WindowsServer/en/library/bcd7ea4c-f989-4cee-969a-920f62f555111033.mspx?mfr=true.
  
###### Tentativo di manomettere le credenziali
  
Gli attacker possono utilizzare diversi approcci per ottenere le credenziali di un account utente, lanciando attacchi con dizionario o attacchi di social engineering. Anche se l'approccio più conosciuto è l'attacco con dizionario a un singolo account, esiste anche l'utilizzo di un insieme di password per tutti gli account di un database dei servizi di directory. Nel secondo caso, è probabile che l'attacker abbia accesso al database delle directory dell'azienda oppure che abbia provato a indovinare il nome utente in base a un elenco di dipendenti di cui dispone. Per rilevare questo tipo di attacco è necessario avere la capacità di rilevare più tentativi di accesso non riusciti con più account, anche se non sono state superate le soglie per il blocco degli account.
  
Anche le reimpostazioni delle password sono un modo per ottenere il controllo delle informazioni sulle credenziali degli account. Poiché le operazioni di reimpostazione o modifica della password generano lo stesso evento sia se riescono sia se non riescono, un attacker può evitare di essere scoperto eludendo i criteri di blocco degli account. Per ostacolare questi tentativi, una soluzione di monitoraggio della protezione deve essere in grado di identificare i tentativi di modifica o di reimpostazione di più password che non rientrano nell'ambito di processi o criteri aziendali consolidati.
  
Anche se il riciclaggio delle password non costituisce un attacco (si verifica quando gli utenti cercano di evitare i criteri di riutilizzo delle password utilizzando script per riciclare la password originale dopo aver utilizzato altre password), può rappresentare comunque una minaccia alla protezione. In questi casi, il numero delle reimpostazioni delle password equivale all'incirca alla soglia di riutilizzo delle password e genera una rapida serie di eventi 627. L'implementazione di criteri di validità minima per le password può causare la mancata riuscita di questi tentativi.
  
La tabella che segue elenca gli eventi che possono essere generati a seguito di tentativi di attacco alle credenziali di autenticazione, ma anche a seguito di normali operazioni di rete, ad esempio quando utenti legittimi dimenticano la password.
  
**Tabella 16. Eventi di attacco alle credenziali di autenticazione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">529</td>
<td style="border:1px solid black;">Accesso non riuscito - Nome utente sconosciuto o password non valida</td>
<td style="border:1px solid black;">Controllare i tentativi in cui il nome dell'account di destinazione corrisponde a un account di amministrazione o con capacità di amministrazione che potrebbe non essere autorizzato alla modifica delle password. Controllare anche la presenza di più accessi non riusciti sotto il limite di blocco degli account. Correlare con gli eventi 529 e 539 per identificare i modelli dei blocchi di account continui.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">534</td>
<td style="border:1px solid black;">Accesso non riuscito - Tipo di accesso non consentito</td>
<td style="border:1px solid black;">Indica che un utente ha tentato l'accesso con un tipo di account non consentito, ad esempio un account di rete, di servizio, batch o interattivo. Controllare il tipo di accesso, il nome della workstation e il nome dell'account di destinazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">539</td>
<td style="border:1px solid black;">Bloccato account</td>
<td style="border:1px solid black;">Indica un tentativo di accesso con un account bloccato. Correlare con l'evento 529 per identificare i modelli dei blocchi continui.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">553</td>
<td style="border:1px solid black;">Rilevato attacco di tipo riproduzione di pacchetti (replay)</td>
<td style="border:1px solid black;">Indica che un pacchetto di autenticazione, generalmente Kerberos, ha rilevato un tentativo di accesso tramite la riproduzione delle credenziali di un utente. Sebbene questo evento possa anche indicare un'errata configurazione della rete, richiede comunque un'indagine immediata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">627</td>
<td style="border:1px solid black;">Tentativo di modifica password</td>
<td style="border:1px solid black;">Indica che una persona diversa dal titolare dell'account ha tentato di modificare una password se il campo relativo al nome dell'account primario non corrisponde al campo del nome dell'account di destinazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">628</td>
<td style="border:1px solid black;">Impostazione o reimpostazione password dell'account utente</td>
<td style="border:1px solid black;">Questa attività dovrebbe essere limitata agli account autorizzati, ad esempio a un account per l'help desk o per la reimpostazione self-service delle password.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">644</td>
<td style="border:1px solid black;">Account utente bloccato automaticamente</td>
<td style="border:1px solid black;">Indica il blocco di un account a seguito del numero di tentativi di accesso sequenziali non riusciti che ha superato il limite previsto per il blocco degli account. Correlare con gli eventi 529, 675, 681 e 676 (solo Windows 2000 Server). Fare riferimento anche alla voce relativa all'evento 12294 in questa tabella.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">675</td>
<td style="border:1px solid black;">Preautenticazione non riuscita</td>
<td style="border:1px solid black;">Indica un possibile problema di sincronizzazione dell'ora o la presenza di account computer non correttamente collegati al dominio. Correlare con l'evento 529 per determinare l'esatto motivo della mancata riuscita dell'accesso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">12294</td>
<td style="border:1px solid black;">Tentativo di blocco dell'account</td>
<td style="border:1px solid black;">Indica un possibile attacco di tipo &quot;brute force&quot; contro l'account di amministrazione predefinito. Poiché a questo account non vengono applicati i criteri di blocco, questo evento viene registrato come evento SAM 12294 nel registro degli eventi di sistema. Ogni verificarsi di questo evento richiede un'indagine immediata poiché può indicare l'utilizzo di un sistema operativo non autorizzato. Controllare la presenza di domini sconosciuti nel campo relativo al nome del dominio.</td>
</tr>
</tbody>
</table>
  
###### Exploit delle vulnerabilità
  
Per un attacker, le vulnerabilità sono un buon bersaglio da sfruttare per un tentativo di intrusione, poiché sono presenti su ogni computer e richiedono tempo e sforzi per essere sanate. Il periodo di tempo, o finestra, che intercorre tra la scoperta delle vulnerabilità e lo sviluppo degli exploit di tali vulnerabilità, si è ridotto con il tempo, il che significa che si è ridotto anche il tempo per sviluppare, testare e distribuire le patch per le vulnerabilità.
  
La miglior difesa dagli exploit delle vulnerabilità è ancora una efficace processo di gestione delle correzioni che possa testare e distribuire rapidamente nell'ambiente gli aggiornamenti della protezione. Alcuni servizi utili in questo processo sono Microsoft Systems Management Server (SMS) 2003 o Windows Software Update Service (WSUS).
  
Anche il monitoraggio della protezione sul perimetro di rete è particolarmente importante a questo riguardo, poiché i computer che risiedono su tale perimetro sono quelli immediatamente suscettibili di attacco. Se non è stato implementato un meccanismo in grado di rilevare un attacco nel momento in cui si verifica, un'organizzazione non può rendersi conto che c'è qualcosa che non va fino a quando la rete non viene compromessa. Ecco perché è fondamentale che i computer sul perimetro di rete siano attentamente monitorati al fine di rilevare una vasta gamma di eventi di controllo.
  
Oltre a quelli già discussi in precedenza, gli eventi più importanti descritti in dettaglio nella sezione “Tentativo di manomettere le credenziali" includono i tentativi di accesso non autorizzati e l'utilizzo improprio dei privilegi. La tabella che segue elenca alcuni eventi che possono identificare tali attacchi.
  
**Tabella 17. Eventi di vulnerabilità causati da exploit delle vulnerabilità tramite un attacco per acquisire privilegi più elevati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">528
538</td>
<td style="border:1px solid black;">Accesso e disconnessione locale</td>
<td style="border:1px solid black;">Correlare il campo relativo all'ID accesso se tali eventi si verificano sui computer perimetrali. Richiedono un'indagine immediata se i campi relativi al nome dell'account utente, all'ora o al nome della workstation contengono valori inaspettati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">551</td>
<td style="border:1px solid black;">Disconnessione avviata da utente</td>
<td style="border:1px solid black;">Questo evento può essere considerato equivalente all'evento 538, poiché un malfunzionamento di un token può impedire il controllo dell'evento 538 al cui posto, però, si verifica l'evento 551.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">576</td>
<td style="border:1px solid black;">Accesso con privilegi</td>
<td style="border:1px solid black;">Indica un accesso con account amministrativo, un accesso account con privilegi sufficienti a manomettere la TCP (Trusted Computing Base) o privilegi sufficienti ad assumere il controllo di un computer su un sistema Windows Server 2003 con SP1 o versioni successive. Nelle precedenti versioni di Windows, questo evento è considerato importante solo se associato a privilegi sensibili quali SeSecurityPrivilege o SeDebugPrivelege.</td>
</tr>
</tbody>
</table>
  
**Nota**   Nelle versioni di Windows precedenti a Windows Server 2003, l'evento 576 viene elencato nella categoria relativa all'utilizzo dei privilegi. In Windows Server 2003 e nelle versioni successive, l'evento viene elencato anche nella categoria relativa all'accesso. Pertanto, la visualizzazione di questo evento è dovuta alla configurazione delle impostazioni di controllo per queste due categorie.
  
###### Tentativi di eludere il controllo
  
Proprio come esistono diversi metodi per attaccare la rete di un'azienda, esistono anche diverse tecniche per nascondere questi tentativi ed eludere la loro rilevazione. Ad esempio, un attacker può modificare un criterio di protezione su un sistema o un dominio compromesso per impedire che i registri degli eventi riportino attività sospette o cancellare deliberatamente un registro di protezione in modo che le informazioni vadano perdute.
  
È possibile rilevare i tentativi di eludere una soluzione di monitoraggio della protezione con tali tecniche, ma l'impresa non è facile, poiché molti degli stessi eventi che possono verificarsi durante il tentativo di coprire le tracce di un'attività di intrusione sono eventi che si verificano normalmente in una tipica rete aziendale.
  
La tabella che segue elenca i vari tipi di evento che possono aiutare a identificare i tentativi di elusione del controllo da parte degli attacker che cercano di nascondere le prove di una violazione della protezione.
  
**Tabella 18. Eventi di elusione del controllo degli eventi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">512</td>
<td style="border:1px solid black;">Avvio di Windows</td>
<td style="border:1px solid black;">Si verifica generalmente dopo l'evento 513. I riavvii inaspettati richiedono un'indagine.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">513</td>
<td style="border:1px solid black;">Chiusura di Windows</td>
<td style="border:1px solid black;">Si verifica generalmente prima dell'evento 512. I computer di elevato valore dovrebbero essere riavviati solo da personale autorizzato e anche in questo caso solo in conformità a una procedura di controllo delle modifiche o di altro tipo che sia stata consolidata. Il verificarsi di questo evento su qualsiasi server richiede un'indagine immediata.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">516</td>
<td style="border:1px solid black;">Controllo non riuscito</td>
<td style="border:1px solid black;">Questo evento può verificarsi se un numero eccessivo di eventi sovraccarica il buffer del registro degli eventi o se il registro di protezione non è stato impostato per la sovrascrittura. Sebbene questi problemi possano essere prevenuti limitando il tipo di eventi da monitorare sulla maggior parte dei computer, i computer vulnerabili o di elevato valore richiedono un monitoraggio più ampio e attento per essere protetti.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">517</td>
<td style="border:1px solid black;">Cancellazione del registro degli eventi di protezione</td>
<td style="border:1px solid black;">I registri degli eventi di protezione non dovrebbero essere mai cancellati senza autorizzazione. Controllare i campi relativi al nome utente del client e al dominio del client per effettuare una correlazione incrociata con il personale autorizzato e i record delle approvazioni procedurali.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">520</td>
<td style="border:1px solid black;">Modifica dell'orario di sistema</td>
<td style="border:1px solid black;">Questa attività può essere utilizzata per fuorviare le indagini legali o fornire falsi alibi agli attacker. Controllare i campi relativi al nome utente del client e al dominio del client per effettuare una correlazione incrociata con il personale autorizzato, oltre a controllare il nome del processo per assicurarsi che sia elencato come %windir%\system32\svchost.exe.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">521</td>
<td style="border:1px solid black;">Impossibile registrare gli eventi</td>
<td style="border:1px solid black;">Si verifica quando Windows non è in grado di scrivere gli eventi nel registro degli eventi. Questo evento richiede un'indagine se si verifica sui sistemi di elevato valore.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">608</td>
<td style="border:1px solid black;">Assegnato privilegio ad account utente</td>
<td style="border:1px solid black;">Si verifica quando viene assegnato un nuovo privilegio a un account utente. Il registro degli eventi registra questa azione insieme al SID (Security Identifier) e non al nome dell'account utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">609</td>
<td style="border:1px solid black;">Rimosso privilegio da account utente</td>
<td style="border:1px solid black;">Si verifica quando viene rimosso un privilegio da un account utente. Il registro degli eventi registra questa azione insieme al SID (Security Identifier) e non al nome dell'account utente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">612</td>
<td style="border:1px solid black;">Modifica dei criteri di controllo</td>
<td style="border:1px solid black;">Anche se questo evento non indica necessariamente un problema, un attacker può modificare i criteri di controllo durante un attacco. Questo evento dovrebbe essere sottoposto a monitoraggio su controller di dominio e computer di elevato valore.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">621</td>
<td style="border:1px solid black;">Accesso al sistema concesso a un account</td>
<td style="border:1px solid black;">Si verifica quando a un utente viene concesso l'accesso a un sistema. Controllare i campi relativi al nome utente e all'account modificato se l'autorizzazione all'accesso è elencata come interattiva.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">622</td>
<td style="border:1px solid black;">Accesso al sistema rimosso da un sistema</td>
<td style="border:1px solid black;">Questo evento può segnalare il tentativo da parte di un attacker di rimuovere una prova relativa all'evento 621 o di negare il servizio ad altri account.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">643</td>
<td style="border:1px solid black;">Modifica dei criteri di protezione del dominio</td>
<td style="border:1px solid black;">Si verifica quando è in corso un tentativo di modificare le impostazioni dei criteri di gestione delle password o di altri criteri di protezione del dominio. Controllare il nome utente e correlarlo a eventuali record delle autorizzazioni.</td>
</tr>
</tbody>
</table>
  
##### Analisi forense
  
Sebbene l'analisi forense si basi su molti degli elementi discussi in questo documento, è profondamente diversa dalle altre soluzioni di monitoraggio e identificazione degli attacchi poiché si fonda sull'archiviazione e sull'analisi delle informazioni sulla protezione e viene utilizzata per rispondere agli attacchi dopo che si sono verificati. La maggior parte delle indagini forensi partono da un elenco di eventi associati a un particolare utente o sistema.
  
Il monitoraggio della protezione per l'analisi forense richiede quanto segue:
  
-   Archiviazione dei tipi di evento selezionati.
  
-   Stima del numero di eventi previsto per ogni giorno.
  
-   Impostazione dei limiti per l'archiviazione online, offline e le risorse di archiviazione.
  
-   Database scalabili, in grado di gestire il numero di eventi previsto.
  
-   Sistema di backup in grado di gestire il carico di eventi previsto per ogni giorno.
  
-   Criteri preimpostati per la gestione del sistema di archiviazione.
  
I tre principali fattori per determinare i requisiti di archiviazione per un programma di analisi forense sono i seguenti:
  
-   Il numero di eventi da registrare.
  
-   La frequenza con cui tali eventi vengono generati dai computer di destinazione.
  
-   La durata della disponibilità degli archivi online.
  
Una profonda conoscenza dei requisiti dell'azienda e delle informazioni fornite nelle precedenti sezioni consente di fare le scelte ottimali riguardo questi tre fattori e ottenere di conseguenza una capacità di archiviazione ragionevole.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Nei moderni ambienti di rete è chiaro che una soluzione efficace e completa per il monitoraggio della protezione e l'identificazione degli attacchi non è un'opzione ma una necessità per ogni azienda di medie dimensioni. Le minacce e i rischi che le reti aziendali si trovano di fronte sono numerosi e non hanno origine solo all'esterno del perimetro di rete ma anche all'interno, a causa di azioni intenzionali o accidentali. Un buon sistema di monitoraggio della protezione prende in considerazione tutti i rischi e richiede un'ottima conoscenza di questi rischi, oltre a quella dell'architettura e della rete aziendali, nonché di tutti i marchi delle minacce e delle attività potenziali che potrebbero mettere in pericolo i dati residenti sui sistemi della rete.
  
È ovvio che per Microsoft il problema della protezione è un problema molto serio ed è per questo che la società offre numerosi strumenti per dotare della massima efficacia ogni sistema di monitoraggio della protezione e identificazione degli attacchi. Windows Server 2003 e le altre versioni del sistema operativo Windows, con la loro funzionalità predefinita di registrazione dei controlli di protezione, sono un'ottima base per questa soluzione di monitoraggio della protezione. Se combinati con altri componenti quali Microsoft Operations Manager e EventCombMT e i necessari processi e criteri aziendali, consentono di sviluppare un sistema di monitoraggio efficace e completo.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Appendice A: Esclusione degli eventi non necessari
  
Gli eventi riportati nella tabella che segue vengono generalmente esclusi dalle query del monitoraggio della protezione poiché sono troppo frequenti e non forniscono di solito risultati utili se inclusi in una soluzione di monitoraggio della protezione.
  
**Tabella A1. Eventi non necessari**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID dell'evento</th>
<th>Evento</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">538</td>
<td style="border:1px solid black;">Disconnessione utente</td>
<td style="border:1px solid black;">Questo evento non indica necessariamente l'ora in cui un utente ha interrotto l'utilizzo di un sistema. Ad esempio, se il computer viene chiuso o perde la connettività di rete può non registrare affatto l'evento di disconnessione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">562</td>
<td style="border:1px solid black;">Un handle ad un oggetto è stato chiuso</td>
<td style="border:1px solid black;">Viene sempre registrato come attività riuscita.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">571</td>
<td style="border:1px solid black;">Contesto client eliminato da Gestione autorizzazioni</td>
<td style="border:1px solid black;">Evento previsto quando si utilizza Gestione autorizzazioni.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">573</td>
<td style="border:1px solid black;">Processo genera evento di controllo non di sistema con AuthZ API (Authorization Application Programming Interface)</td>
<td style="border:1px solid black;">Attività prevista.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">577<br />
578</td>
<td style="border:1px solid black;">Richiamato servizio con privilegi, operazione su oggetto con privilegi</td>
<td style="border:1px solid black;">Tipo di evento generato in grandi quantità che normalmente non contiene informazioni sufficienti a suggerire un'azione poiché non descrive l'operazione che si è verificata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">594</td>
<td style="border:1px solid black;">Un handle ad un oggetto è stato duplicato</td>
<td style="border:1px solid black;">Attività prevista.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">595</td>
<td style="border:1px solid black;">È stato ottenuto accesso indiretto ad un oggetto</td>
<td style="border:1px solid black;">Attività prevista.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">596</td>
<td style="border:1px solid black;">Backup della chiave principale della protezione dati</td>
<td style="border:1px solid black;">Attività prevista. Con le impostazioni predefinite, si verifica ogni 90 giorni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">597</td>
<td style="border:1px solid black;">Ripristino della chiave principale della protezione dati</td>
<td style="border:1px solid black;">Attività prevista.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">672</td>
<td style="border:1px solid black;">Richiesta ticket AS Kerberos</td>
<td style="border:1px solid black;">Non contiene informazioni aggiuntive se sono stati già raccolti i dettagli di controllo degli eventi di accesso 528 e 540. Questo evento indica che è stato concesso un TGT Kerberos e che l'accesso reale non avverrà fino alla concessione di un ticket di servizio, attività controllata dall'evento 673. Se PATYPE è PKINIT, l'accesso è avvenuto tramite smart card.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">680</td>
<td style="border:1px solid black;">Accesso account</td>
<td style="border:1px solid black;">Attività già registrata da altri eventi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">697</td>
<td style="border:1px solid black;">Richiamata API per controllo dei criteri di gestione delle password</td>
<td style="border:1px solid black;">Attività prevista.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">768</td>
<td style="border:1px solid black;">Collisione di spazi dei nomi di foresta</td>
<td style="border:1px solid black;">Questo evento non è un evento di protezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">769<br />
770<br />
771</td>
<td style="border:1px solid black;">Informazioni foresta trusted aggiunte, eliminate o modificate</td>
<td style="border:1px solid black;">Attività prevista. Questi eventi non devono essere confusi con l'aggiunta, la modifica o l'eliminazione dei trust veri e propri.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">832<br />
833<br />
834<br />
835<br />
836<br />
837<br />
838<br />
839<br />
840<br />
841</td>
<td style="border:1px solid black;">Eventi di replica di Active Directory</td>
<td style="border:1px solid black;">Questi eventi non sono eventi di protezione.</td>
</tr>
</tbody>
</table>
  
**Nota**   Escludere alcune informazioni da un controllo comporta alcuni rischi, ma il livello di rischio va rapportato ai vantaggi che derivano dalla riduzione del carico di lavoro dell'agente di analisi.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Appendice B: Implementazione delle impostazioni di Criteri di gruppo
  
Questa appendice è utile per controllare le impostazioni correnti dell'ambiente e include alcune impostazioni aggiuntive che influenzano il monitoraggio della protezione e l'identificazione degli attacchi. Per configurare correttamente gli eventi di controllo di Criteri di gruppo, è necessario applicare le impostazioni riportate nella tabella che segue.
  
**Tabella B1. Impostazioni dei controlli di protezione di Criteri di gruppo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Percorso criterio</th>
<th>Criterio</th>
<th>Impostazione criterio e commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/Criteri controllo</td>
<td style="border:1px solid black;">Controlla eventi accesso account</td>
<td style="border:1px solid black;">Abilitare il controllo delle operazioni riuscite per tutti i computer, poiché questo evento registra chi ha avuto accesso al computer. Abilitare il controllo delle operazioni non riuscite con cautela, poiché un attacker dotato di accesso alla rete ma senza credenziali potrebbe lanciare un attacco DoS (Denial of Service) forzando un computer a consumare le risorse registrando questi eventi. Abilitare con cautela anche il controllo delle operazioni riuscite, poiché questa impostazione può provocare attacchi DoS se i computer sono impostati in modo da eseguire la chiusura del sistema una volta che i registri di controllo hanno raggiunto la dimensione massima. Correlare tutti gli accessi come amministratore alle altre voci sospette.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/Criteri controllo</td>
<td style="border:1px solid black;">Controlla gestione degli account</td>
<td style="border:1px solid black;">Abilitare gli eventi relativi alle operazioni sia riuscite che non riuscite. Correlare tutte le voci di controllo relative alle operazioni riuscite con le autorizzazioni degli amministratori. Tutte le operazioni non riuscite dovrebbero essere considerate sospette.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/Criteri controllo</td>
<td style="border:1px solid black;">Controlla accesso al servizio directory</td>
<td style="border:1px solid black;">Il Criterio controller di dominio predefiniti abilita questa impostazione per impostazione predefinita. Configurare le impostazioni di controllo sugli oggetti directory sensibili utilizzando i SACL (System ACL) in Utenti e computer di Active Directory oppure Modifica ADSI. Un piano per l'implementazione dei SACL è consigliabile, così come il test dei SACL in un ambiente di test realistico prima di distribuire questi elenchi in un ambiente di produzione. Questo approccio consente di prevenire il sovraccarico dei registri di protezione impedendo l'inserimento di un volume eccessivo di dati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/Criteri controllo</td>
<td style="border:1px solid black;">Controlla eventi di accesso</td>
<td style="border:1px solid black;">Abilitare il controllo delle operazioni riuscite per tutti i computer, poiché questo evento registra chi ha avuto accesso al computer. Abilitare il controllo delle operazioni non riuscite con cautela, poiché un attacker con accesso alla rete ma senza credenziali potrebbe sferrare un attacco DoS generando un numero eccessivo di azioni non riuscite.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/Criteri controllo</td>
<td style="border:1px solid black;">Controlla accesso agli oggetti</td>
<td style="border:1px solid black;">Abilitare questa impostazione con cautela, poiché può dare adito a un volume molto elevato di eventi di controllo. Configurare le impostazioni di controllo solo per le cartelle di elevato valore, utilizzando i SACL, e controllare solo i tipi specifici di accesso a cui si è interessati. Se possibile, controllare solo gli eventi di protezione relativi alle operazioni di scrittura e non quelli relativi alle operazioni di lettura.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/Criteri controllo</td>
<td style="border:1px solid black;">Modifica del criterio di controllo</td>
<td style="border:1px solid black;">Abilitare il controllo sia delle operazioni riuscite che delle operazioni non riuscite. Eseguire la correlazione incrociata di tutti gli eventi relativi ad operazioni riuscite con le autorizzazioni amministrative.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/Criteri controllo</td>
<td style="border:1px solid black;">Controlla uso dei privilegi</td>
<td style="border:1px solid black;">Non abilitare il controllo dell'utilizzo dei privilegi a causa dell'elevato volume di eventi che questa configurazione potrebbe generare.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/Criteri controllo</td>
<td style="border:1px solid black;">Controlla tracciato processo</td>
<td style="border:1px solid black;">Abilitare questa impostazione sui computer vulnerabili e indagare immediatamente su attività applicative impreviste, isolando il sistema se necessario. Non abilitare questa impostazione su server Web CGI (Common Gateway Interface), sistemi di test, server che eseguono processi batch o workstation di sviluppatori poiché questa impostazione può causare il riempimento dei registri degli eventi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/Criteri controllo</td>
<td style="border:1px solid black;">Controlla eventi di sistema</td>
<td style="border:1px solid black;">Abilitare il controllo sia delle operazioni riuscite che delle operazioni non riuscite.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/Assegnazione diritti utente</td>
<td style="border:1px solid black;">Generazione controlli di protezione</td>
<td style="border:1px solid black;">Questa impostazione viene assegnata per impostazione predefinita a Sistema locale, Server locale e Servizio di rete. Questo diritto non dovrebbe essere assegnato ad account diversi dagli account di servizio. Un attacker può utilizzare questa impostazione per generare eventi spuri o vaghi nel registro di protezione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/Assegnazione diritti utente</td>
<td style="border:1px solid black;">Gestione file registro di controllo e di protezione</td>
<td style="border:1px solid black;">Utilizzare questa impostazione per impedire agli amministratori di apportare modifiche alle impostazioni di controllo relative a file e cartelle e al Registro di sistema. È consigliabile creare un gruppo di protezione per gli amministratori autorizzati a modificare le impostazioni di controllo e rimuovere il gruppo degli amministratori dalle impostazioni dei criteri di protezione locali. Solo i membri di un gruppo di protezione dovrebbero essere in grado di configurare il controllo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/Opzioni di protezione</td>
<td style="border:1px solid black;">Controllo: controllo accesso oggetti di sistema globale</td>
<td style="border:1px solid black;">Questa impostazione aggiunge i SACL agli oggetti di sistema denominati quali, mutex, semafori e periferiche MS-DOS. Le impostazioni predefinite di Windows Server 2003 non abilitano questa opzione. Non abilitare questa impostazione poiché potrebbe generare un elevato volume di eventi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri locali/Opzioni di protezione</td>
<td style="border:1px solid black;">Controllo: controllo utilizzo dei privilegi di backup e di ripristino</td>
<td style="border:1px solid black;">Le operazioni di backup e ripristino offrono l'opportunità di rubare dati eludendo gli ACL. Non abilitare questa impostazione poiché potrebbe generare un elevato volume di eventi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Criteri locali/Opzioni di protezione</td>
<td style="border:1px solid black;">Controllo: arresto del sistema immediato se non è possibile registrare i controlli di protezione</td>
<td style="border:1px solid black;">Abilitare questa impostazione solo dopo un'attenta valutazione e solo sui computer di elevato valore, poiché gli attacker possono utilizzarla per lanciare attacchi DoS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Registro eventi</td>
<td style="border:1px solid black;">Dimensione massima registro protezione</td>
<td style="border:1px solid black;">Le impostazioni consigliate dipendono dai volumi di eventi previsti e dalle impostazioni per la conservazione dei registri di protezione. Questa impostazione può utilizzare solo incrementi di 64 KB e la dimensione media di un evento è di 0,5 KB. In ambienti caratterizzati da volumi particolarmente elevati, questa impostazione può essere configurata fino a 250 MB, ma la dimensione totale di tutti i registri degli eventi messi insieme non può superare 300 MB.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Registro eventi</td>
<td style="border:1px solid black;">Impedisci accesso guest locale al registro di protezione</td>
<td style="border:1px solid black;">Windows Server 2003 abilita questa impostazione per impostazione predefinita. Non modificare.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Registro eventi</td>
<td style="border:1px solid black;">Gestione registro protezione per</td>
<td style="border:1px solid black;">Abilitare questa impostazione solo se il metodo di gestione selezionato è “Sovrascrivi eventi ogni giorno”. Se viene utilizzato un sistema di correlazione degli eventi che esegue il polling degli eventi, assicurarsi che il numero di giorni sia almeno tre volte il valore della frequenza di polling, in modo da consentire errori nel ciclo di polling.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Registro eventi</td>
<td style="border:1px solid black;">Criteri gestione registro protezione</td>
<td style="border:1px solid black;">Abilitare l'impostazione Non sovrascrivere eventi negli ambienti che richiedono un elevato livello di protezione. Per questi ambienti, è consigliabile stabilire le procedure per svuotare e archiviare i registri regolarmente, soprattutto se è abilitata l'impostazione Arresto del sistema immediato se non è possibile registrare i controlli di protezione.</td>
</tr>
</tbody>
</table>
  
**Download**
  
[Scarica il documento Monitoraggio della protezione e identificazione degli attacchi](http://go.microsoft.com/fwlink/?linkid=71717)
  
[](#mainsection)[Inizio pagina](#mainsection)
