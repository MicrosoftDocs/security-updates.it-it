---
TOCTitle: Protezione degli account critici e del servizio
Title: Protezione degli account critici e del servizio
ms:assetid: 'aed37382-e798-437b-8740-8a03412ed1ef'
ms:contentKeyID: 20213221
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc875826(v=TechNet.10)'
---

Protezione degli account critici e del servizio
===============================================

##### In questa pagina

[](#ehaa)[Introduzione](#ehaa)
[](#egaa)[Definizione](#egaa)
[](#efaa)[Sfide](#efaa)
[](#eeaa)[Soluzioni](#eeaa)
[](#edaa)[Riepilogo](#edaa)
[](#ecaa)[Appendice A: Servizi comuni](#ecaa)

### Introduzione

Il primo passo verso la protezione della rete di una media impresa è identificare le vulnerabilità che un utente malintenzionato potrebbe sfruttare. L'obiettivo principale di un utente malintenzionato che è riuscito a infiltrarsi in una rete è acquisire privilegi sempre più elevati, che gli consentano di ottenere un accesso maggiore dalla posizione vantaggiosa guadagnata. Se l'utente malintenzionato è riuscito ad acquisire privilegi più elevati, non resta molto da fare per fermarlo, a prescindere dal suo intento. Gli utenti malintenzionati possono ricorrere a diversi meccanismi per acquisire privilegi più elevati, ma essenzialmente si tratta di attività che compromettono gli account esistenti, specialmente quelli con privilegi a livello di amministratore.

Le reti delle medie imprese spesso adottano alcune misure di controllo della sicurezza sugli account utente standard, ma spesso non fanno altrettanto per gli account del servizio, rendendoli quindi vulnerabili e appetibili per gli utenti malintenzionati. Se un utente malintenzionato riesce a infiltrarsi nella rete al punto da compromettere un account critico con privilegi elevati, l'intera rete non potrà essere più considerata completamente affidabile a meno di non ricrearla. Pertanto, il livello di protezione per tutti i tipi di account è un aspetto molto importante per qualsiasi iniziativa inerente alla protezione della rete.

Oltre ai rischi rappresentati dalle minacce esterne per la rete di una media impresa, anche le minacce interne possono causare molti problemi. Le minacce interne sono costituite non solo dagli utenti malintenzionati ma anche da chi può causare danni inconsapevolmente. Ne sono un esempio i tentativi apparentemente innocui di eludere le misure di sicurezza da parte degli utenti che tentano di accedere alle risorse. Troppo spesso, per comodità, gli utenti e i servizi dispongono di un accesso con privilegi superiori al necessario. Sebbene questo approccio garantisca agli utenti l'accesso alle risorse necessarie per il proprio lavoro, aumenta il rischio di attacchi sulla rete.

#### Riepilogo

Come indicato nell'introduzione, la gestione della protezione per tutti i tipi di account di una rete è una questione di fondamentale importanza per gestire al meglio i rischi nella rete di una media impresa. È necessario prendere seriamente in considerazione le minacce interne ed esterne e la soluzione deve bilanciare l'esigenza di protezione con la funzionalità che una media impresa richiede per le risorse di rete.

Il presente documento aiuterà le medie imprese a comprendere i rischi associati agli account amministrativi, del servizio, connessi alle applicazioni e predefiniti. Queste informazioni forniranno alle medie imprese il punto di partenza per lo sviluppo e la distribuzione delle operazioni volte a ridurre questi rischi. A tal fine, è necessario discutere della natura di questi account, di come identificarli, di come stabilire adeguate autorizzazioni per il funzionamento e di come ridurre i rischi inerenti agli account del servizio elevati e agli account a livello di amministratore.

Come parte dell'iniziativa Microsoft Trustworthy Computing (in inglese), le impostazioni predefinite in Microsoft® Windows Server™ 2003 sono state ideate per proteggere il servizio Active Directory® da diverse minacce, ma alcune impostazioni per gli account amministrativi possono ancora essere modificate per aumentare il livello di protezione nell'ambiente di rete di una media impresa. Inoltre, i servizi non forniti con il sistema operativo Windows Server 2003 e installati da altre applicazioni devono anch'essi essere protetti. Nel presente documento verranno descritti i metodi per proteggere questi account e servizi oltre alle procedure consigliate per controllare la distribuzione e la gestione dei privilegi amministrativi.

#### Panoramica

Il presente documento è suddiviso in 4 sezioni principali che forniscono informazioni sulla protezione degli account amministratore e del servizio in una media impresa. La prima sezione è intitolata "Introduzione" ed è quella che si sta leggendo al momento. Il resto del documento è strutturato nel seguente modo:

-   **Definizione**. In questa sezione vengono fornite alcune informazioni di base e descrizioni della terminologia utilizzata nel documento.

-   **Sfide**. In questa sezione vengono descritti alcuni problemi comuni nelle medie imprese quando devono stabilire il motivo per cui è necessario proteggere gli account e alcuni problemi associati alla protezione degli account amministratore e del servizio.

-   **Soluzioni**. Questa sezione è suddivisa in tre sottosezioni che forniscono al lettore le informazioni sulle fasi degli approcci alla protezione degli account critici e del servizio in una media impresa. Queste sottosezioni sono:

    -   **Valutazione**. In questa sottosezione vengono descritte le considerazioni di base per la protezione degli account critici e del servizio e vengono illustrate le basi per la pianificazione delle soluzioni.

    -   **Sviluppo**. In questa sottosezione vengono utilizzate le informazioni contenute nella sottosezione "Valutazione" allo scopo di fornire soluzioni per sviluppare piani che consentano di potenziare la protezione degli account critici e del servizio.

    -   **Distribuzione e gestione**. In questa sottosezione vengono descritti i metodi consigliati per implementare account amministratore e del servizio protetti in una media impresa.

#### Destinatari

Questo documento tecnico mira a fornire assistenza ai professionisti IT a ai responsabili tecnici che si occupano della protezione degli account del servizio, delle applicazioni e a livello di amministratore in una rete Microsoft. Sebbene anche un pubblico non tecnico potrebbe ottenere informazioni sui principi di gestione degli account protetti, la comprensione dei concetti e delle procedure di gestione degli account di Microsoft Windows® e Active Directory è necessaria per trarre il massimo vantaggio dalle informazioni contenute in questo documento.

[](#mainsection)[Inizio pagina](#mainsection)

### Definizione

In questa sezione vengono fornite le definizioni di alcuni termini utilizzati nel documento e che possono richiedere una spiegazione.

-   **Servizi**. I servizi sono file eseguibili che vengono attivati all'avvio, da altri eventi o da istanze pianificate. I servizi spesso vengono eseguiti in background senza l'intervento dell'utente.

-   **Account del servizio**. In poche parole, un account del servizio viene spesso descritto come un qualsiasi account che non corrisponde a una persona reale. Si tratta spesso di account predefiniti utilizzati dai servizi per accedere alle risorse richieste e svolgere le proprie attività. Del resto, alcuni servizi richiedono veri account utente per eseguire determinate funzioni e molte imprese utilizzano ancora gli account di dominio per eseguire i servizi.

-   **Account amministrativo**. Sebbene esista un account amministratore predefinito sulle nuove installazioni del dominio Microsoft Windows o Active Directory, l'espressione account amministratore viene spesso utilizzata in generale per descrivere un con privilegi a livello di amministratore. Per chiarezza, in questo documento verranno illustrate le differenze tra i due.

-   **Gruppi amministrativi**. Questi gruppi possono variare in base ai servizi installati, ma possono anche includere i servizi creati automaticamente nei contenitori Builtin e Users. Questi gruppi comprendono anche i servizi con privilegi amministrativi creati e garantiti.

-   **Account critici**. Nel presente documento viene utilizzata l'espressione "account critico" per descrivere gli account predefiniti considerati ad alto rischio a causa di privilegi di livello elevato o dell'uso molto diffuso.

-   **Account limitato**. Un account limitato è un qualsiasi account che non fa parte di un gruppo amministrativo e che non dispone di privilegi elevati equivalenti a quelli di un account amministratore locale o di dominio. In genere, un account limitato fa parte del gruppo Domain Users o Local Users.

-   **Principio del privilegio minimo**. Il Department of Defense Trusted Computer System Evaluation Criteria, (DOD-5200.28-STD), conosciuto anche come Orange Book, è uno standard accettato per la protezione dei computer. Questa pubblicazione definisce il privilegio minimo come un principio che "richiede che a ciascun soggetto in un sistema venga concesso il set di privilegi più restrittivi, o il livello di autorizzazione più basso, necessari per svolgere le attività autorizzate. L'applicazione di questo principio limita il danno che può derivare da incidenti, errori o utilizzo non autorizzato".

[](#mainsection)[Inizio pagina](#mainsection)

### Sfide

Come spiegato nella precedente sezione, gli account a livello di amministratore e gli account del servizio non protetti rappresentano un rischio notevole per la rete di una media impresa. Considerata la complessità degli ambienti di rete e la velocità di crescita delle reti aziendali, è abbastanza comune trovare procedure di gestione degli account che presentano importanti vulnerabilità. Questi fattori rappresentano il motivo per cui gli account critici e i servizi eseguiti su una rete finiscono con il diventare un'attività di difficile gestione.

Alcuni dei problemi più comuni nelle medie imprese quando devono stabilire l'approccio adatto per la risoluzione dei problemi di protezione comprendono:

-   La protezione dalle minacce interne ed esterne relative alla gestione degli account e alle soluzioni alternative tentate dai dipendenti.

-   L'identificazione di tutti gli account delle applicazioni e del servizio in uso sui computer di rete e locali.

-   La protezione degli account sensibili del servizio, a livello di amministratore e relativi alle applicazioni.

-   L'identificazione degli account associati ai servizi e alle applicazioni.

-   L'isolamento degli account del servizio dai criteri di password dell'account utente.

[](#mainsection)[Inizio pagina](#mainsection)

### Soluzioni

Le soluzioni fornite in questo documento seguono il principio del privilegio minimo e l'approccio LUA (Least-privileged User Account, Account utente con privilegio minimo) per la gestione degli account del servizio, amministrativi e critici.

Gran parte della formazione e della documentazione relative alla protezione tratteranno del principio del privilegio minimo. Sebbene questo principio sia relativamente semplice da capire, è molto utile per migliorare notevolmente il profilo di protezione di qualsiasi impresa lo adotti. In poche parole, questo principio stabilisce che tutti gli account debbano disporre solo del numero minimo assoluto di privilegi necessario per completare le attività correnti. Il principio si applica non solo agli utenti ma anche ai computer e ai servizi utilizzati.

Il principio non solo fornisce protezione contro utenti malintenzionati e malware, ma aumenta anche il profilo di protezione di una società obbligando i professionisti IT a eseguire ricerche estensive per stabilire i privilegi di accesso richiesti da utenti, computer e applicazioni. La comprensione di queste informazioni consente di stabilire quali processi o impostazioni non sono al sicuro e richiedono dunque maggiore protezione ed è quindi essenziale per qualsiasi iniziativa inerente alla protezione.

Ad esempio, secondo il principio del privilegio minimo, una persona con il ruolo di amministratore di dominio deve utilizzare il privilegio di livello di amministratore di dominio solo quando esegue attività che richiedono questo livello di accesso. In caso contrario, un amministratore deve utilizzare un account con diritti di accesso standard. In questo modo verrebbero ridotte le minacce alla protezione derivanti da errori umani oltre ai danni causati nel caso in cui una workstation amministrativa fosse infettata da malware.

#### Valutazione

Per proteggere gli account critici e del servizio, è necessario identificare la natura di tali account, nonché le minacce ad essi associate. Tuttavia, è anche importante verificare che le conseguenze derivanti dalla modifica di questi account siano ben chiare per garantire che l'impatto sulle attività aziendali resti a livelli accettabili.

##### Gestione degli account amministratore e critici

Per proteggere gli account amministrativi e critici e i gruppi associati, è necessario sapere quali account e gruppi soddisfano il criterio richiesto. È anche importante conoscere l'ambito dei privilegi amministrativi e a quali si sistemi si riferiscono, specialmente quando questi gestiscono controller di dominio.

È dunque importante che chi legge questo documento abbia una visione chiara degli account a livello amministrativo dell'ambiente oltre che di tutti i controller di dominio e degli account che li gestiscono.

###### Gruppi e account amministrativi

Gli account a livello amministrativo in una rete Active Directory comprendono:

-   L'account amministratore predefinito, creato al momento dell'installazione di Active Directory sul primo controller di dominio in un dominio. Si tratta dell'account principale del dominio, quindi è necessario stabilire una password quando questo account viene creato.

-   Tutti gli account creati in un secondo momento e ai quali vengono concessi i privilegi amministrativi direttamente o in base al relativo posizionamento in un gruppo amministrativo.

I gruppi amministrativi in un dominio Active Directory possono variare in base ai servizi installati nel dominio stesso. Un dominio Active Directory di base comprenderà quanto segue:

-   Gruppi amministrativi automaticamente creati nel contenitore Builtin.

-   Gruppi amministrativi automaticamente creati nel contenitore Users.

-   Tutti i gruppi creati in un secondo momento, collocati all'interno di gruppi con privilegi amministrativi o che dispongono di per sé di privilegi amministrativi.

###### Amministratori del servizio e amministratori di dati

Esistono due tipi di privilegi amministrativi in un ambiente Windows Server 2003 Active Directory: amministratori del servizio e amministratori di dati

-   Gli account amministratore del servizio sono responsabili della gestione e della fornitura dei servizi directory, inclusa la gestione dei controller di dominio e di Active Directory.

-   Gli account amministratore dati gestiscono i dati memorizzati nel servizio directory, nei server dei membri di dominio e nelle workstation del dominio.

Sebbene sia possibile eseguire entrambi i ruoli in qualsiasi ambiente, è importante conoscere i gruppi e gli account predefiniti che sono amministratori del servizio. Gli account amministratore del servizio dispongono di un enorme potere nell'ambiente di rete e richiedono dunque la massima protezione. Questi account sono responsabili delle impostazioni a livello di directory, dell'installazione e della gestione del software e dell'applicazione di service pack e aggiornamenti del sistema operativo nei controller di dominio.

**Tabella 1. Gruppi e account amministratore del servizio predefiniti**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Contenitore</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Builtin</td>
<td style="border:1px solid black;">Questo gruppo ha pieno accesso a tutti i controller di dominio e a tutti i contenuti delle directory memorizzati in un dominio. Si tratta del gruppo amministratore del servizio principale e può modificare i livelli associativi di tutti gli altri gruppi amministrativi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Enterprise Admins</td>
<td style="border:1px solid black;">Users</td>
<td style="border:1px solid black;">Questo gruppo viene aggiunto automaticamente al gruppo Administrators di ciascun dominio e dispone dell'accesso completo alla configurazione di tutti i controller di dominio.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Domain Admins</td>
<td style="border:1px solid black;">Users</td>
<td style="border:1px solid black;">Questo gruppo viene aggiunto automaticamente al gruppo Administrators in tutti i domini di una foresta. Pertanto, il gruppo Domain Admins ha diritti su tutti i controller di dominio e sui dati memorizzati nella directory di un dominio e può modificare i livelli associativi di qualsiasi gruppo amministrativo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Schema Admins</td>
<td style="border:1px solid black;">Users</td>
<td style="border:1px solid black;">Questo gruppo ha privilegi amministrativi completi per lo schema Active Directory.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Account Operators</td>
<td style="border:1px solid black;">Builtin</td>
<td style="border:1px solid black;">Questo gruppo può creare e gestire gli account e i gruppi del dominio ma non può gestire gli account amministratore del servizio. Per impostazione predefinita, al gruppo non appartiene alcun membro e, pertanto, si consiglia di non utilizzarlo per le deleghe amministrative.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Backup Operators</td>
<td style="border:1px solid black;">Builtin</td>
<td style="border:1px solid black;">Questo gruppo accorda i privilegi per eseguire il backup e ripristinare le attività sui controller di dominio e non ha alcun membro per impostazione predefinita.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Server Operators</td>
<td style="border:1px solid black;">Builtin</td>
<td style="border:1px solid black;">Questo gruppo può eseguire attività di gestione sui controller di dominio e non ha membri per impostazione predefinita.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DS Restore Mode Administrator</td>
<td style="border:1px solid black;">Non memorizzato in Active Directory</td>
<td style="border:1px solid black;">Questo account viene creato durante il processo di installazione di Active Directory. Viene utilizzato per avviare il controller di dominio in modalità ripristino servizi directory e, sebbene non corrisponda all'account amministratore, ha pieno accesso al controller di dominio quando è in modalità ripristino servizi directory.</td>
</tr>
</tbody>
</table>
  
I gruppi e gli account amministratore del servizio elencati nella precedente tabella sono protetti da un processo in background che controlla e applica periodicamente un descrittore di protezione specifico contenente informazioni di protezione relative all'oggetto protetto. Questo processo si estende a tutti i membri di un gruppo amministratore del servizio e garantisce che qualsiasi tentativo non autorizzato di modificare il descrittore in un membro del gruppo amministrativo venga sovrascritto con le impostazioni protette contenute nella struttura di dati del descrittore di protezione.
  
Questa struttura di dati del descrittore di protezione si trova nell'oggetto AdminSDHolder. Pertanto, per modificare le autorizzazioni su uno dei gruppi amministratore del servizio o uno dei relativi account membro, il descrittore di protezione nell'oggetto AdminSDHolder deve essere modificato in modo tale che le modifiche vengano applicate in modo coerente. Le modifiche apportate al descrittore di protezione vengono applicate alle impostazioni predefinite di tutti gli account amministrativi protetti. È dunque necessario prestare molta attenzione quando si modificano le autorizzazioni in questo modo.
  
Per ulteriori informazioni sulla modifica delle autorizzazioni sugli account amministratore del servizio, vedere la [http://www.microsoft.com/downloads/details.aspx?familyid=2eaa45c7-d936-413e-9586-a8bb6ff739d9&displaylang;=en](http://www.microsoft.com/downloads/details.aspx?familyid=2eaa45c7-d936-413e-9586-a8bb6ff739d9&displaylang=en&tm)&tm; (in inglese) disponibile per il download all'indirizzo www.microsoft.com/downloads/details.aspx?FamilyID=4e734065-3f18-488a-be1e-f03390ec5f91&DisplayLang=en.
  
#### Gestione degli account delle applicazioni e del servizio
  
I servizi sono file eseguibili che vengono attivati spesso senza l'intervento dell'utente ed eseguiti automaticamente all'avvio del sistema operativo: ciò spiega perché i servizi e gli account del servizio siano spesso sottovalutati e considerati unico rischio di protezione in una rete aziendale. Anche se si è a conoscenza dei rischi di protezione, la gestione degli account del servizio può rivelarsi un'attività alquanto complessa, considerato che la semplice modifica di una password può richiedere molte altre modifiche per evitare danni.
  
Sebbene Windows Server 2003 disponga di servizi e account del servizio predefiniti protetti da minacce, molti servizi di terze parti e persino altri servizi Microsoft devono essere protetti perché richiedono una corretta esecuzione degli account del servizio. Questo requisito vale specialmente per gli strumenti di gestione aziendale, quali Microsoft Systems Management Server o IBM Tivoli, perché questi richiedono spesso l'uso di un account con diritti sull'intero dominio e anche su altri domini con relazioni di trust.
  
Inoltre, l'uso degli account di dominio per eseguire i servizi è ancora comune perché è più semplice gestire i servizi nel dominio piuttosto che sui singoli server, nonostante i rischi di protezione che ne derivano. I servizi memorizzano le informazioni sulla password e sull'account utente utilizzati nel Registro di sistema, sia per gli account locali che di dominio. Pertanto, quando un singolo computer risulta compromesso, l'utente malintenzionato può utilizzare queste informazioni per acquisire maggiori privilegi nel caso in cui i servizi utilizzino gli account di dominio. Se un servizio utilizza un account di dominio con livello amministrativo, un simile scenario potrebbe rappresentare una minaccia per l'intera rete.
  
##### Scenari di vulnerabilità degli account del servizio
  
La configurazione dei servizi in modo che utilizzino gli account di dominio per l'autenticazione porta a una potenziale esposizione a eventuali rischi. Il grado di esposizione ai rischi dipende da diversi fattori, tra cui:
  
-   **Il numero di server con servizi configurati per utilizzare gli account del servizio**. La vulnerabilità di una rete aumenta per ogni server che dispone di servizi autenticati per l'account di dominio eseguiti sul server. L'esistenza di questo tipo di server aumenta la possibilità che un utente malintenzionato possa danneggiare il server, che potrà essere utilizzato per acquisire privilegi per altre risorse di una rete.
  
-   **L'ambito dei privilegi per ogni account di dominio utilizzato dai servizi**. Maggiore è l'ambito dei privilegi di cui dispone un account del servizio, più alto è il numero di risorse che possono essere danneggiate dall'account. I privilegi a livello di amministratore del dominio sono particolarmente a rischio perché l'ambito della vulnerabilità per questi account comprende tutti i computer della rete, inclusi i controller di dominio. Poiché questi account dispongono di privilegi amministrativi per tutti i server membri, il livello di compromissione di un simile account sarebbe grave e tutti i computer e i dati del dominio potrebbero essere sospetti.
  
-   **Il numero di servizi configurati per l'uso degli account di dominio su determinati server**. Alcuni server presentano vulnerabilità specifiche che li rendono più esposti ad alcuni attacchi. Gli utenti malintenzionati tenteranno di sfruttare prima le vulnerabilità note. L'uso di un account di dominio da parte di un servizio vulnerabile presenta un rischio maggiore per gli altri sistemi, che potrebbero essere stati isolati invece in un singolo server.
  
-   **Il numero di account di dominio utilizzati per eseguire i servizi in un dominio**. Il monitoraggio e la gestione della protezione degli account del servizio richiedono maggiore attenzione rispetto agli account utente ordinari e ciascun account di dominio aggiuntivo utilizzato dai servizi non fa altro che complicare l'amministrazione di questi account. Posto che gli amministratori e gli amministratori della protezione devono sapere dove viene utilizzato ciascun account del servizio, l'individuazione delle attività sospette presenta la necessità di ridurre il numero di questi account.
  
I fattori indicati in precedenza portano ad alcuni possibili scenari di vulnerabilità, ciascuno con un diverso livello di rischio potenziale per la protezione. Il seguente diagramma e la seguente tabella descrivono questi scenari.
  
Per questi esempi si presume che gli account del servizio siano account di dominio e che ciascun account disponga di almeno un servizio su ciascun server utilizzato per l'autenticazione. Le seguenti informazioni descrivono gli account di dominio illustrati nella seguente figura.
  
-   L'Account A dispone di privilegi equivalenti a quelli di un amministratore per più di un controller di dominio.
  
-   L'Account B dispone di privilegi equivalenti a quelli di un amministratore per tutti i server membri.
  
-   L'Account C dispone di privilegi equivalenti a quelli di un amministratore per i server 2 e 3.
  
-   L'Account D dispone di privilegi equivalenti a quelli di un amministratore per i server 4 e 5.
  
-   L'Account E dispone di privilegi equivalenti a quelli di un amministratore per un solo server membro.
  
    ![](images/Cc875826.SCASA1(it-it,TechNet.10).gif)
  
    **Figura 1. Scenari di vulnerabilità degli account del servizio del dominio**
  
Nella seguente tabella vengono descritti gli scenari illustrati in dettaglio nella figura e nel testo precedenti e vengono classificati in base al grado di vulnerabilità.
  
**Tabella 2. Classificazione degli scenari di rischio per la protezione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Scenario</th>
<th>Descrizione</th>
<th>Livello di rischio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">L'Account A viene utilizzato da un servizio sul Server 1. Se il Server 1 viene compromesso, vengono scoperte le informazioni di autenticazione per l'Account A. In questa situazione l'utente malintenzionato ha accesso al controller di dominio DC1, dal quale tutte le risorse del dominio e le informazioni in esso contenute diventano vulnerabili.
Questa situazione rappresenta uno scenario di rischio critico. Gli account di dominio con privilegi equivalenti a quelli di un amministratore per il dominio o per un controller di dominio non devono mai essere utilizzati per eseguire i servizi su un server membro.</td>
<td style="border:1px solid black;">Critico</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">L'Account B viene utilizzato da un servizio sul Server 2. Anche l'Account B dispone di privilegi sul Server 1 in cui l'Account A esegue un servizio. Se l'Account B viene compromesso sul Server 2, l'utente malintenzionato ha lo stesso accesso descritto nello scenario 1, che espone il controller di dominio e l'intero dominio all'attacco.
L'Account C espone anche la rete allo stesso livello di rischio perché potrebbe essere utilizzato per compromettere il Server 2 in seguito a un attacco contro il Server 3, che a sua volta espone l'Account A e di conseguenza l'intero dominio.
Questi sono scenari di rischio elevato ma risolvibile posto che le minacce potenziali presentate nello Scenario 1 siano state risolte.</td>
<td style="border:1px solid black;">Elevato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">3</td>
<td style="border:1px solid black;">L'Account D viene utilizzato da un servizio in esecuzione sul Server 4 e sul Server 5. Se l'Account D viene compromesso, un utente malintenzionato può accedere a tutti i server nei punti in cui l'Account D dispone di privilegi. Se questi server non comprendono servizi che utilizzano account con un numero o un ambito maggiore di privilegi, questo scenario presenterà un rischio con priorità media perché la vulnerabilità transitiva dello Scenario 2 non esiste.</td>
<td style="border:1px solid black;">Medio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">4</td>
<td style="border:1px solid black;">L'Account E viene utilizzato da un servizio su un unico server, il Server 5, e non dispone di altri privilegi o associazioni di servizi. Questo scenario rappresenta un rischio di livello basso perché non consente di acquisire privilegi maggiori del singolo server.</td>
<td style="border:1px solid black;">Basso</td>
</tr>
</tbody>
</table>
  
I livelli di rischio descritti nei precedenti scenari possono essere spiegati ulteriormente come segue:
  
-   **Livello di rischio critico**. Questo rischio compromette immediatamente la protezione dell'intera rete e dell'intera impresa.
  
-   **Livello di rischio elevato**. Questo rischio può compromettere la protezione dell'intera rete ma non con lo stesso impatto di un rischio critico.
  
-   **Livello di rischio medio**. Questo rischio deve essere risolto poiché può interessare molti server, ma non espone un server di importanza critica alla vulnerabilità.
  
-   **Livello di rischio basso**. Questo rischio può compromettere un singolo server ma non i server di importanza critica.
  
#### Account di sistema
  
I servizi richiedono l'accesso degli account a risorse e oggetti gestiti dal sistema operativo sul quale vengono eseguiti. Se l'account utilizzato da un servizio non dispone dei privilegi necessari per l'accesso, lo snap-in dei servizi MMC concederà automaticamente all'account il diritto utente "Accesso come servizio" richiesto per il computer gestito.
  
Windows Server 2003 comprende i seguenti account locali predefiniti che vengono utilizzati come account di accesso per diversi servizi di sistema:
  
-   **Sistema locale**. L'account Sistema locale, che viene visualizzato come DOMAIN*\\&lt;nome computer&gt;*$ sulla rete e NT AUTHORITY\\System nel sistema locale, è un account locale predefinito che può avviare e fornire il contesto di protezione per i servizi. Questo potente account ha pieno accesso al computer locale, inclusi i servizi directory quando viene utilizzato sui controller di dominio. Sebbene, per impostazione predefinita, alcuni servizi siano configurati per utilizzare questo account in Windows Server 2003, è opportuno non utilizzarlo in modo diverso perché rappresenta un chiaro rischio di protezione, specialmente sui controller di dominio.
  
-   **Servizio locale**. L'account Servizio locale (NT AUTHORITY\\LocalService) è un account predefinito con privilegi limitati simili a un account utente locale autenticato. Questo accesso con limitazioni serve da salvaguardia nel caso in cui il servizio o il processo che lo utilizza sia compromesso. I servizi eseguiti come account Servizio locale accedono alle risorse di rete come sessione null. In altre parole, utilizzano credenziali anonime.
  
-   **Servizio di rete**. L'account Servizio di rete (NT AUTHORITY\\NetworkService) è un account predefinito con privilegi limitati simili all'account Servizio locale. Tuttavia, invece di utilizzare credenziali anonime, i servizi e i processi che utilizzano questo account accedono alle risorse di rete utilizzando le credenziali di un account computer.
  
**Nota**   La modifica delle impostazioni predefinite dei servizi può impedire il corretto funzionamento dei servizi principali. È necessario prestare attenzione quando si modificano le impostazioni **Tipo di avvio** e **Accesso come** per i servizi avviati automaticamente per impostazione predefinita.
  
#### Impostazioni predefinite di protezione per i servizi Windows Server 2003
  
Prima di Windows XP e Windows Server 2003, quasi tutti i servizi creati dal sistema operativo utilizzavano l'account Sistema locale per impostazione predefinita. Questa funzionalità causava evidenti rischi di protezione perché questi servizi avevano diritti illimitati sul computer locale. Le impostazioni predefinite vennero modificate con lo sviluppo di Windows Server 2003 per migliorare la protezione del sistema operativo. Di conseguenza, molti degli stessi servizi utilizzano attualmente gli account Servizio locale o Servizio di rete per impostazione predefinita, poiché presentano una vulnerabilità inferiore.
  
Esistono ancora alcuni servizi che richiedono l'uso dell'account Sistema locale, inclusi Aggiornamenti automatici, Browser di computer, Messenger e Windows Installer. I servizi che utilizzano ancora l'account Sistema locale per l'autenticazione non devono essere modificati per utilizzare altri account, altrimenti potrebbero insorgere gravi problemi e il corretto funzionamento dei servizi potrebbe risultare compromesso.
  
Nella seguente tabella vengono elencati gli account del servizio che non utilizzano più l'account Sistema locale in Windows Server 2003 e il tipo di account utilizzato in sostituzione:
  
**Tabella 3. Nuove impostazioni degli account del servizio di Windows Server 2003**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Servizio</th>
<th>Accesso come</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Avvisi</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Servizio Gateway di livello applicazione</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Registro di sistema remoto</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Smart card</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Helper NetBIOS di TCP/IP</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Telnet</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Gruppo di continuità</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">WebClient</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Acquisizione di immagini di Windows (WIA)</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Ora di Windows</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Servizio Rilevamento automatico proxy Web WinHTTP</td>
<td style="border:1px solid black;">Servizio locale</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Client DHCP</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Distributed Transaction Coordinator</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Client DNS</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Registrazione licenze</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Log prestazioni</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">RPC Locator</td>
<td style="border:1px solid black;">Servizio di rete</td>
</tr>
</tbody>
</table>
  
#### Sviluppo
  
Per sviluppare un piano di protezione degli account sensibili e amministrativi, è importante comprendere gli elementi fondamentali sui quali si basano tutte le procedure consigliate. Qualsiasi azione intrapresa per proteggere account e servizi prevede gli stessi principi di base che fanno parte a loro volta dei processi e delle procedure consigliate. In questa sezione vengono esaminati questi principi con i relativi aspetti più importanti.
  
##### Gestione degli account amministratore e critici
  
Le procedure consigliate per la protezione degli account amministrativi di Windows Server 2003 si basano sull'applicazione dei principi di privilegio minimo e sull'uso di un account utente con limitazioni. Il primo passo di questo processo consiste nello sviluppare una conoscenza completa dell'ambiente corrente. I seguenti fattori sono essenziali per lo sviluppo di un piano efficace per aumentare la protezione degli account amministratore e critici:
  
-   Conoscenza e documentazione dell'ambiente
  
-   Uso del principio del privilegio minimo
  
-   Uso dell'account utente con privilegio minimo
  
###### Conoscenza e documentazione dell'ambiente
  
Sebbene apparentemente scontato, questo primo, importante passaggio per il miglioramento della protezione relativa agli account con privilegi equivalenti a quelli di amministratore può risultare talvolta il più complesso dell'intero processo. Se una società non fa uso limitato e documentato di privilegi a livello di amministratore, può essere difficile stabilire se e dove sono applicati tali privilegi, specialmente per gli account locali.
  
Per quanto riguarda gli account di livello di amministratore e altri account sensibili, la conoscenza e la documentazione di un ambiente di rete comprende le seguenti informazioni: *chi* è autorizzato a utilizzare gli account amministratore, *perché* queste persone hanno accesso agli account amministrativi, *quali* attività sono adatte all'uso di credenziali amministrative e *dove* è sicuro utilizzare queste credenziali.
  
L'aspetto più importante della documentazione di queste informazioni è la determinazione dei processi e delle procedure adottati per controllare il punto in cui vengono utilizzati gli account amministrativi, il motivo per cui vengono utilizzati, le persone che li utilizzano e le operazioni eseguite quando questi erano in uso. Si consiglia di registrare queste informazioni in modo proattivo tramite i processi di provisioning, controllo delle modifiche e gestione degli eventi che richiedono l'autorizzazione e la registrazione di tutte le attività prima che queste possano essere completate. Questi processi consentono un controllo attento dell'uso dei privilegi amministrativi, che semplifica inoltre notevolmente il riconoscimento di attività sospette.
  
Come si vedrà in seguito nel presente documento, la conoscenza e la documentazione di un ambiente di rete sono la parte più importante del processo di miglioramento della protezione degli account critici. La determinazione dei processi e delle procedure consigliate per l'uso e il rilascio degli account sensibili è una parte fondamentale di questo processo e deve verificarsi prima dell'implementazione di qualsiasi altra informazione contenuta in questo documento.
  
###### Uso del principio del privilegio minimo
  
Il principio del privilegio minimo è probabilmente una delle operazioni più importanti che una società può eseguire per migliorare la protezione dell'ambiente di rete. Sebbene concedere i privilegi a livello amministrativo rappresenti il modo più semplice e rapido per risolvere i complessi problemi relativi ai diritti o ai privilegi, è anche il più rischioso. Inoltre, poiché è molto più semplice per gli amministratori di sistema utilizzare un account con privilegi amministrativi, queste procedure aumentano anche il profilo di rischio della rete per la quale sono responsabili.
  
L'applicazione essenziale di questo principio è la seguente: i privilegi amministrativi devono essere limitati all'uso da parte del personale autorizzato solo quando l'attività richiede la potenza inerente ai privilegi elevati. Sebbene possa sembrare oneroso implementare procedure che incorporano questo concetto, il livello di rischio a cui una società si espone non aderendo a questo principio è troppo elevato e non può essere ignorato.
  
Il livello di esposizione ai rischi più comuni che le reti possono affrontare è ridotto dall'applicazione di questo principio. Di seguito alcuni degli esempi di questi rischi:
  
-   Rootkit in modalità kernel
  
-   Programmi di registrazione chiavi a livello di sistema
  
-   Tentativi di intercettazione delle password
  
-   Eventi spyware e adware
  
-   Accesso non autorizzato ai dati
  
-   Installazioni trojan horse
  
-   Manipolazione del registro eventi
  
Quando l'uso degli account amministrativi è limitato, è ridotta anche la possibilità di utilizzare i privilegi elevati inerenti a questi account, aumentando il profilo di protezione della rete. Inoltre, rimuovendo la possibilità di apportare grandi modifiche al sistema operativo, ne risulta ridotta anche la possibilità che malware e spyware vengano installati ed eseguiti. Per questi motivi, l'applicazione del principio del privilegio minimo può avere un effetto notevole sulla protezione della rete.
  
###### Uso dell'account utente con privilegio minimo
  
Gli utenti dispongono regolarmente di privilegi amministrativi per i propri computer in molti ambienti aziendali, specialmente sui computer portatili. Sebbene esistano diversi motivi per i quali vengono concessi privilegi così estesi, tali decisioni espongono la società a elevati livelli di rischio.
  
L'uso di un approccio LUA combina le procedure consigliate che consentono alle società di utilizzare account non amministrativi per i computer con Windows XP. Il risultato di queste procedure è l'applicazione pratica del principio del privilegio minimo come applicato ai dispositivi client di Windows XP.
  
Poiché in questo documento vengono esaminati gli account amministrativi da un livello elevato e viene dedicata molta attenzione ai privilegi di rete, è anche importante considerare le conseguenze che gli account utente locali possono avere sulle workstation. Sebbene questo tipo di approccio mirato non verrà descritto in dettaglio in questo documento, ulteriori informazioni sono disponibili sul sito Web Microsoft. Per ulteriori informazioni, vedere il white paper "[Applying the Principle of Least Privilege to User Accounts on Windows XP](http://technet.microsoft.com/en-us/library/bb456992.aspx)" (in inglese) all'indirizzo http://technet.microsoft.com/en-us/library/bb456992.aspx o l'articolo "[Using a Least-Privileged User Account](http://www.microsoft.com/technet/security/secnews/articles/lpuseacc.mspx)" (in inglese) all'indirizzo www.microsoft.com/technet/security/secnews/articles/lpuseacc.mspx.
  
##### Gestione degli account del servizio
  
Come per la gestione degli account amministratore e critici, esistono tre problemi fondamentali relativi alla determinazione di un piano che contribuisca ad aumentare la protezione dei servizi in una media impresa. È importante che questi problemi vengano risolti durante le fasi di sviluppo e incorporati nelle procedure relative ai criteri di protezione:
  
-   Conoscenza e documentazione dell'ambiente
  
-   Uso del principio del privilegio minimo
  
-   Uso del principio del servizio minimo
  
###### Conoscenza e documentazione dell'ambiente
  
Questa fase può sembrare scontata, tuttavia molte società non sono pienamente consapevoli dei ruoli e dei servizi esistenti nell'ambiente di rete. Questa mancanza di conoscenza e documentazione può essere causata da diversi motivi, ma deriva generalmente dalla rapida crescita degli ambienti di rete e dalla mancanza di tempo e risorse necessarie per dedicare l'attenzione adeguata alla documentazione.
  
Per verificare se i computer sono protetti, è necessario conoscere quali servizi vengono eseguiti su questi ultimi e le relative proprietà. Queste informazioni sono importanti per la protezione dei server e dei relativi servizi, nonché degli account richiesti dai servizi stessi. Per questa attività è generalmente utile creare una tabella dei servizi, delle proprietà dei servizi e dei computer sui quali vengono utilizzati i servizi. La creazione di una simile tabella può essere complessa, ma i risultati ripagano lo sforzo. Inoltre, tenere aggiornata la tabella è relativamente semplice in seguito alla creazione e all'inserimento della stessa nel processo di distribuzione dell'applicazione e di configurazione del server.
  
Esistono numerosi strumenti che possono essere utili per la documentazione dei servizi e delle relative proprietà sulla rete, ad esempio:
  
-   **Strumento Controller del servizio (sc.exe)**. Questa utilità della riga di comando è compresa in Windows Server 2003 e Windows XP. Questo strumento fornisce un modo semplice per comunicare con il componente Gestione controllo servizi da una riga di comando per eseguire query e impostare le proprietà dei servizi.
  
-   **Strumento Service Controller List (sclist.exe)**. Windows 2000 Server Resource Kit è dotato di uno strumento in grado di elencare i servizi in esecuzione e arrestati nei computer locali e remoti. Sclist.exe può essere utilizzato per identificare i servizi eseguiti sui server remoti privi di monitor o distanti dall'amministratore.
  
-   **Strumentazione gestione Windows (WMI)**. Questo componente installato in Windows Server 2003 e Windows XP fornisce informazioni di gestione e funzionalità di controllo per gli ambienti aziendali. Gli amministratori possono utilizzare WMI per eseguire query e impostare le informazioni su computer, reti, applicazioni e servizi. Oltre a offrire la possibilità di utilizzare script per la gestione delle attività amministrative, WMI consente agli amministratori di identificare le dipendenze dei servizi e qualsiasi servizio dal quale questi ultimi dipendono.
  
-   **Riga di comando Strumentazione gestione Windows (WMIC)**. WMI comprende anche uno strumento da riga di comando, WMIC, che fornisce a WMI una semplice interfaccia accessibile tramite la riga di comando per le query e la gestione remota dei computer. I risultati delle query di WMIC possono essere formattati per leggere facilmente le tabelle HTML tramite un browser, ad esempio Internet Explorer.
  
###### Uso del principio del privilegio minimo
  
Microsoft è consapevole dell'importanza che ha la protezione e del ruolo essenziale che il principio del privilegio minimo riveste nella protezione degli ambienti di rete. Microsoft ha applicato il principio del privilegio minimo durante lo sviluppo di Windows Server 2003 per verificare se i servizi principali del sistema operativo utilizzavano già l'account con privilegio minimo e non richiedevano dunque ulteriore configurazione. Il punto cruciale di questo approccio è rappresentato dalla protezione dei servizi che non fanno parte del sistema operativo, ad esempio i servizi forniti come componenti di altri prodotti quali Microsoft SQL Server, Microsoft Operations Manager o altri prodotti software di terze parti.
  
Di conseguenza, il principio del privilegio minimo deve essere utilizzato quando si esegue qualsiasi altro servizio, anche se spesso è più semplice concedere un livello superiore di privilegi durante l'implementazione di nuovi prodotti. Ad esempio, i servizi devono utilizzare l'account Servizio locale, se possibile, per limitare gli attacchi al computer locale e non all'intero dominio. I servizi che richiedono l'accesso alla rete autenticato devono utilizzare l'account Servizio di rete, se possibile. I servizi che richiedono privilegi estesi devono utilizzare l'account Sistema locale. Infine, se un servizio richiede l'uso di un account amministratore a livello di dominio, il server o i server su cui il servizio viene eseguito devono essere considerati sistemi con protezione elevata allo stesso modo di altre risorse di rete sensibili o critiche e altri controller di dominio.
  
I criteri di gruppo possono anche essere utilizzati per controllare determinati servizi la cui esecuzione è concessa sui computer. Numerose proprietà possono essere controllate dal seguente percorso **Configurazione computer\\Impostazioni di Windows\\Impostazioni di protezione\\Servizi di sistema**, alla pagina **Proprietà** del servizio. Le impostazioni quali la modalità di avvio e le autorizzazioni che stabiliscono se gli account possono essere utilizzati per eseguire determinate operazioni sul servizio in questione (avvio o arresto, ad esempio) possono essere modificate.
  
L'implementazione del principio del privilegio minimo dipende dalla conoscenza dei sistemi in uso. Combinando questi due concetti chiave è possibile determinare quali servizi sono in esecuzione sui computer, il loro stato e le credenziali utilizzate per ciascun servizio e server. Solo a questo punto è possibile limitare efficacemente ciascun servizio affinché utilizzi solo i privilegi minimi necessari al funzionamento tramite processi adeguati di controllo delle modifiche, che semplificano anche la costante raccolta di documentazione relativa all'ambiente.
  
###### Uso del principio del servizio minimo
  
Infine, il principio del servizio minimo indica che i protocolli del sistema operativo e di rete disponibili in tutte le risorse di rete devono eseguire solo i servizi e i protocolli necessari per l'impresa. Ad esempio, se un server non deve ospitare applicazioni Web, il servizio Web deve essere disattivato o rimosso.
  
La maggior parte dei sistemi operativi e dei programmi installano in una configurazione predefinita più servizi e protocolli di quanto richiesto per l'uso comune. Pertanto, se possibile, è necessario utilizzare un processo di installazione personalizzato per controllare quali servizi e protocolli vengono attivati o installati durante un processo di applicazione. Questo approccio consente di documentare i processi creati durante un'installazione nel caso in cui venga successivamente stabilito che un servizio creato durante l'installazione non sia più necessario.
  
Durante la distribuzione di nuovi server o lo sviluppo di immagini server, si consiglia all'amministratore di sistema di lasciare aperti solo i servizi essenziali richiesti dal sistema operativo e chiudere tutti gli altri. I servizi disattivati possono essere attivati nuovamente, se necessario, per qualsiasi applicazione che il server deve eseguire. Ad esempio, è molto frequente disattivare i servizi Avvisi e Messenger sui sistemi operativi Windows precedenti a Windows Server 2003, perché questi non erano generalmente richiesti. La disattivazione di questi servizi aumentava il profilo di protezione del server distribuito senza danneggiarne le funzionalità.
  
Un'altra parte importante di questo principio è la giusta disposizione dei servizi. Ad esempio, il servizio Routing e Accesso remoto o Internet Information Service non devono mai trovarsi sui controller di dominio, perché ne aumentano la vulnerabilità. Se compromesso, un controller di dominio può anche concedere accesso illimitato al resto del dominio. Pertanto, le procedure consigliate di Microsoft prevedono che nessun servizio aggiuntivo, diverso da quelli indispensabili per il funzionamento, debba essere distribuito su un controller di dominio.
  
#### Distribuzione e gestione
  
Dopo le considerazioni chiave e i principi fondamentali, è possibile considerare a questo punto alcuni consigli specifici basati su questi concetti. L'esecuzione di una sola delle operazioni descritte può aumentare la protezione di una rete aziendale, ma, se eseguite insieme, queste diventano parte di una struttura di protezione completa che può ridurre notevolmente la vulnerabilità della rete di una media impresa.
  
##### Gestione degli account amministratore e critici
  
Per proteggere gli account amministrativi di una rete Microsoft Windows è possibile implementare numerose procedure consigliate. I seguenti metodi si sono dimostrati utili per ridurre la vulnerabilità associata a questi account e vengono generalmente utilizzati nelle reti delle medie imprese.
  
###### Separazione dei ruoli di amministratore di dominio e amministratore dell'organizzazione
  
Il ruolo di amministratore dell'organizzazione è il più importante in una foresta Active Directory. È necessario intraprendere alcune azioni per verificare che questo tipo di account sia protetto e che il suo uso sia attentamente controllato. Esistono due approcci alla gestione di questo tipo di account:
  
-   **Singolo account controllato**. Il primo approccio consiste nel limitare questo ruolo a un singolo account strettamente controllato per verificare che l'uso coincida solo con le richieste di controllo delle modifiche autorizzate di attività che ne richiedono l'uso. Qualsiasi evento monitorato che si verifica in questo account richiede un'indagine immediata e deve essere accompagnato da una sorta di evento richiesta di modifica autorizzata.
  
-   **Account temporaneo**. Un altro approccio consiste nel non impostare mai un simile account a meno che non sia necessario per eseguire un'attività autorizzata. In caso di una richiesta autorizzata, è possibile creare un account temporaneo, utilizzato per completare l'attività e in seguito eliminato. Poiché l'esigenza di un simile account è piuttosto rara, queste operazioni non rappresentano un sovraccarico amministrativo.
  
###### Separazione degli account utente e amministratore
  
Gli account sono generalmente associati agli utenti. Quando si utilizza il principio del privilegio minimo, gli account possono essere associati ad attività e non solo a ruoli, specialmente in caso di funzioni amministrative. Chi ricopre un ruolo di amministratore deve disporre di due account: uno per le operazioni giornaliere che è un account utente tipico e un altro che prevede privilegi amministrativi e deve essere utilizzato solo per le attività amministrative eseguite in una workstation amministrativa.
  
Gli account amministrativi devono poter eseguire solo le attività amministrative sulle workstation amministrative che fanno parte di una rete trusted simile ai controller di dominio. Gli account amministrativi e le workstation associate non devono avere accesso alla posta elettronica o a Internet e non devono essere accessibili quando non in uso. Gli amministratori devono disporre di diverse password per gli account standard e gli account amministratore e queste devono essere quanto più complesse possibile.
  
Queste semplici precauzioni riducono notevolmente l'esposizione ai rischi derivanti da questi account riducendo il contatto con il mondo esterno e limitandone l'uso in termini di tempo.
  
###### Uso del Servizio di accesso secondario
  
È possibile eseguire programmi in un account diverso da quello in cui ci si trova quando si utilizza il servizio Esegui come di Microsoft Windows 2000. Con Windows Server 2003 e Windows XP Professional questa stessa funzionalità è stata ridefinita come Servizio di accesso secondario.
  
Questo servizio consente agli amministratori di accedere a un computer con un account non amministrativo e di eseguire attività amministrative con credenziali di amministratore senza doversi disconnettere. Questa funzionalità riduce i rischi associati all'uso di credenziali amministrative applicando una sorta di separazione tra gli account utente e amministratore descritti in precedenza.
  
###### Esecuzione di sessioni separate di servizi terminal per l'amministrazione
  
Le connessioni Servizi terminal e Desktop remoto vengono generalmente utilizzate per gestire i server senza dover accedere fisicamente alla console server. Questo approccio non è solo efficace ma anche più sicuro rispetto all'uso di un account amministratore per accedere in modo interattivo al server, specialmente quando non si utilizza un account amministratore sul computer dal quale è stata stabilita la connessione. Al termine di un'attività, l'account amministratore deve essere disconnesso insieme alla sessione.
  
###### Ridenominazione dell'account amministratore predefinito
  
La ridenominazione dell'account amministratore predefinito resta una procedura comune in molte medie imprese e consente di ridurre la vulnerabilità dell'account stesso. Tuttavia, questo approccio impedisce solo pochi tipi di attacchi perché esistono numerosi strumenti e tecniche utilizzati dagli utenti malintenzionati per individuare l'account Administrator predefinito. Sebbene la ridenominazione dell'account predefinito possa essere utile, è sicuramente più efficace creare account amministratore secondari e disattivare gli account predefiniti originali, come verrà spiegato in seguito.
  
###### Creazione di account amministratore esca
  
Quando utilizzato con un meccanismo di difesa contro le intrusioni in grado di rilevare e inviare avvisi sull'attività di un determinato account, un account amministratore esca può agire da ulteriore livello di difesa contro tentativi di attacco a una rete. Anche da sola questa tecnica può rallentare l'azione degli utenti malintenzionati quando viene concesso un numero di tentativi di blocco dell'account maggiore rispetto agli account comuni e vengono fornite password complesse. Gli account amministratore esca non devono essere membri di gruppi di protezione con privilegi e devono essere monitorati per tutte le attività. Qualsiasi tentativo di utilizzare un simile account deve essere seguito da un'indagine immediata.
  
###### Creazione di account amministratore secondari e disattivazione di account predefiniti
  
Se chi occupa un ruolo amministrativo non dispone anche di un account univoco equivalente a quello amministrativo da utilizzare per le attività amministrative e se i Servizi terminal non vengono utilizzati per l'amministrazione dei server, si consiglia di creare un account amministratore secondario. Un account amministratore secondario agisce da elemento di sicurezza integrata contro la compromissione di un account amministratore principale e deve essere creato prima di disattivare l'account amministratore predefinito.
  
**Nota**    È importante assicurarsi che un altro account con i privilegi amministrativi adeguati sia stato creato prima di disattivare l'account amministratore predefinito. La disattivazione dell'account amministratore predefinito senza verificare l'esistenza di un altro account equivalente potrebbe causare una perdita di controllo amministrativo sul dominio e richiedere il ripristino o la reinstallazione del sistema.
  
###### Attivazione del blocco account per gli accessi remoti come amministratore
  
Sebbene l'account amministratore predefinito non possa essere bloccato, è possibile bloccare gli accessi che si servono di questo account. Per compiere questa attività, Microsoft Windows 2000 Server Resource Kit contiene un programma dalla riga di comando denominato Passprop.exe che consente il blocco account per gli accessi remoti. Quando questo strumento della riga di comando viene utilizzato con il commutatore /ADMINLOCKOUT, l'uso dell'accesso interattivo e remoto dell'account amministratore è soggetto ai criteri di blocco esistenti in Windows 2000 Server.
  
**Nota**    L'utilizzo di Passprop.exe /ADMINLOCKOUT in Windows Server 2003 influenzerà l'uso dell'accesso remoto e interattivo dell'account amministratore. Quando si utilizza questa funzionalità, è necessario dedicare una particolare attenzione in quanto, se il server è bloccato, non sarà possibile utilizzare l'account amministratore per l'amministrazione del server.
  
###### Creazione di password complesse per l'amministratore
  
Si consiglia l'uso di una password complessa per qualsiasi account con privilegi equivalenti a quelli di amministratore e per l'account amministratore predefinito. Le password complesse consentono di ridurre la probabilità che un utente malintenzionato riesca in un attacco di tipo "brute force" ad acquisire privilegi. Tali password sono composte, generalmente, dai seguenti elementi:
  
-   Minimo 15 caratteri
  
-   Non contiene mai nomi di account, nomi reali o nomi di società
  
-   Non contiene mai una parola completa, un termine in gergo o altri termini facilmente individuabili
  
-   Ha un contenuto differente dalle password utilizzate in precedenza e non incrementate
  
-   Utilizza almeno tre dei seguenti tipi di caratteri:
  
    -   Lettere maiuscole (A, B, C...)
  
    -   Lettere minuscole (a, b, c...)
  
    -   Numeri (0, 1, 2...)
  
    -   Simboli non alfanumerici (@, &, $...)
  
    -   Caratteri Unicode (€, ƒ, ?...)
  
###### Rilevazione automatica di password deboli
  
Esistono due approcci di base che gli strumenti di scansione delle password utilizzano durante la verifica dell'utilizzo di password deboli o vuote. Tali approcci sono:
  
-   **Scansione in linea della password**. La scansione in linea prevede diversi tentativi di collegamento utilizzando password con errori comuni, ad esempio l'uso del termine "password" come password o l'uso di password vuote. Uno strumento che utilizza questo metodo è Microsoft Baseline Security Analyzer (MBSA).
  
-   **Scansione non in linea della password**. La scansione non in linea prevede diversi meccanismi che utilizzano credenziali nella cache per verificare, e persino classificare, l'efficacia delle password di diversi account. Gli strumenti che utilizzano questo approccio presentano alcuni vantaggi rispetto al metodo precedente, ma implicano l'utilizzo di software di terze parti.
  
Nonostante siano disponibili strumenti di terze parti per la ricerca di password deboli, Microsoft fornisce Microsoft Baseline Security Analyzer (MBSA), scaricabile gratuitamente. MBSA è in grado di fornire una notifica di tutti gli account disattivati o bloccati rilevati durante l'enumerazione di tutti gli account utente per la ricerca dei seguenti errori di password:
  
-   Password vuote
  
-   Uso di nomi utente come password
  
-   Uso di nomi di computer come password
  
-   Uso di parole quali "password", "admin" o "administrator" come password
  
Per ulteriori informazioni, fare riferimento alla pagina Web [Microsoft Baseline Security Analyzer](http://www.microsoft.com/technet/security/tools/mbsahome.mspx) all'indirizzo www.microsoft.com/technet/security/tools/mbsahome.mspx.
  
###### Limitazione delle attività amministrative per i computer trusted
  
Le credenziali di amministratore rappresentano un obiettivo molto allettante per gli aspiranti intrusi, pertanto potrebbe essere molto difficile individuare i metodi utilizzati per accedervi. I dispositivi che registrano la sequenza di tasti e gli screen scraper sono alcuni degli strumenti tipici utilizzati per ottenere informazioni riservate mediante l'acquisizione della sequenza di tasti eseguita e dei caratteri immessi in un computer compromesso. Queste forme di malware possono essere molto furtive e difficili da individuare, tanto meno da rimuovere, dopo essere state installate su un computer.
  
Pertanto, si consiglia di verificare che gli account amministratore utilizzino meno computer possibili per ridurre la vulnerabilità verso tali minacce. Inoltre, quando si limitano le risorse su cui utilizzare gli account amministrativi, è importante verificare che tali sistemi siano affidabili e ben protetti. Sono disponibili molte tecniche in grado di proteggere le risorse riservate, ad esempio l'isolamento della rete mediante l'IPsec, che impone una maggiore protezione per determinati dispositivi senza alcun impatto sulla rete stessa.
  
Per ulteriori informazioni sull'utilizzo di IPsec per isolare domini e server, vedere la tecnologia [Server and Domain Isolation](http://www.microsoft.com/technet/itsolutions/network/sdiso/default.mspx) (in inglese) all'indirizzo www.microsoft.com/technet/itsolutions/network/sdiso/default.mspx.
  
###### Controllo di account e password
  
Il controllo degli account, effettuato regolarmente, consente di garantire l'integrità della protezione del dominio contro gli attacchi che comprendono l'acquisizione dei privilegi. Se gli utenti malintenzionati accedono a un account a livello di amministratore, possono introdurre delle vulnerabilità e schivare le misure di sicurezza. Ad esempio, gli utenti malintenzionati che riescono ad accedere ad un account equivalente a quello di amministratore possono creare account utente proxy, modificare l'appartenenza di un account e persino modificare i registri eventi per coprire i loro attacchi.
  
Tutti gli utenti e i gruppi amministrativi a livello di dominio, nonché tutti gli account e i gruppi dell'amministratore locale su server riservati devono essere controllati regolarmente. L'uso di tali credenziali amministrative deve essere monitorato per garantire che vengano utilizzate unicamente seguendo le linee guida imposte dai criteri interni e in accordo con tutti i processi interni stabiliti e ben documentati, ad esempio le procedure di controllo delle modifiche. I controlli regolari degli account assicurano il corretto svolgimento delle procedure nel corso delle attività amministrative, inoltre verificano che vengano seguiti i criteri relativi all'efficacia della password.
  
Il Visualizzatore eventi può essere uno strumento utile nel processo di controllo, se sono state seguite le istruzioni per proteggere i registri eventi da eventuali alterazioni. Per informazioni sull'utilizzo dei registri eventi per il monitoraggio della protezione della rete e sulle modalità con cui proteggere i dati del registro eventi, vedere la [*Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi*](http://technet.microsoft.com/it-it/library/dd547357.aspx) all'indirizzo http://technet.microsoft.com/it-it/library/dd547357.aspx.
  
###### Blocco della delega dell'account
  
L'autenticazione delegata si verifica quando un servizio di rete accetta una richiesta da un utente e assume l'identità di tale utente per avviare un nuovo collegamento ad altri servizi di rete. L'autenticazione delegata dispone di diverse applicazioni utili per le applicazioni a più livelli che utilizzano funzionalità Single Sign-On sulla rete. Microsoft Outlook Web Access (OWA) utilizza questo meccanismo per fornire un'interfaccia con database su altri computer.
  
Gli account amministratore devono essere designati come "L'account è sensibile e non può essere delegato". Questo approccio consente di proteggere le credenziali equivalenti a quelle di amministratore dalla rappresentazione tramite server contrassegnata come attendibile per la delega. Agli account di computer in Active Directory, che corrispondono ai computer non protetti fisicamente, deve essere negato il diritto di partecipare al processo di autenticazione delegata. Inoltre, lo stesso diritto deve essere negato agli account amministratore di dominio in quanto dispongono dell'accesso alle informazioni e alle risorse riservate in una rete.
  
Per ulteriori informazioni sulla delega dell'account, vedere [Enabling Delegated Authentication](http://technet.microsoft.com/en-us/library/cc780217.aspx) (in inglese) all'indirizzo http://technet.microsoft.com/en-us/library/cc780217.aspx.
  
###### Applicazione dell'autenticazione a più fattori per gli account amministratore
  
I gruppi Administrators, Enterprise Admins e Domain Admins contengono gli account con maggiori poteri di una rete aziendale. Di conseguenza, tali account devono essere maggiormente protetti.
  
I metodi di autenticazione a più fattori consentono di migliorare la protezione del processo di accesso richiedendo ulteriori informazioni di identificazione dagli utenti autorizzati. In questo modo, la quantità di informazioni che un utente malintenzionato deve acquisire per poter compromettere l'account aumenta. Come suggerito dal nome, un metodo di autenticazione a più fattori richiede diverse informazioni di identificazione. Generalmente, questo metodo potrebbe richiedere quanto segue:
  
-   Informazioni su ciò di cui l'utente dispone, ad esempio una smart card.
  
-   Informazioni note all'utente, ad esempio un codice (PIN).
  
-   Informazioni sull'identità dell'utente (generalmente indicata come biometrica), ad esempio un processo semplice simile alla scansione dell'impronta digitale per l'autenticazione.
  
L'uso dell'autenticazione a più fattori rimuove le vulnerabilità associate ai metodi di autenticazione basati sul nome utente e sulla password non crittografati mediante l'uso di una smart card che contiene un codice generato casualmente in grado di identificare il titolare dell'account. Ogni scheda contiene una chiave privata univoca che garantisce la singolarità delle informazioni di autenticazione.
  
Inoltre, l'uso di una smart card richiede l'uso di un PIN, un altro codice crittografato impostato dal proprietario della scheda e memorizzato sulla stessa. Nel processo di autenticazione, questo PIN rende disponibile per l'uso la chiave privata contenuta nella scheda; in caso contrario la chiave rimane crittografata e non utilizzabile.
  
Per ulteriori informazioni sui metodi di autenticazione a più fattori e sulle smart card, fare riferimento alla [*Guida alla pianificazione dell'accesso protetto mediante smart card*](http://go.microsoft.com/fwlink/?linkid=41313) all'indirizzo http://go.microsoft.com/fwlink/?LinkID=41313.
  
#### Gestione degli account delle applicazioni e del servizio
  
Sono disponibili anche diversi metodi che consentono di aumentare la protezione dei servizi e degli account del servizio. In questa sezione verranno descritti i metodi comprovati per migliorare la protezione dei servizi in ambienti di rete reali. Sebbene l'uso di questi metodi combinati possa migliorare notevolmente la sicurezza delle reti di aziende di medie dimensioni, la soluzione migliore consiste nel valutare la combinazione di approcci più adatta per ciascun ambiente aziendale.
  
##### Controllo dei servizi per le proprietà essenziali
  
Come descritto in precedenza, la prima fase del processo di sviluppo di un piano per la protezione dei servizi in un determinato ambiente prevede una conoscenza approfondita di tali servizi, dove vengono impiegati e il motivo per cui vengono utilizzati. Nonostante sembri un'attività relativamente semplice, potrebbe risultare incredibilmente difficile identificare quali servizi sono in esecuzione su ciascun computer e qual è il grado di gestione richiesto da tali servizi.
  
È necessario documentare e controllare ciascun server presente in un ambiente per determinare tutti i servizi in esecuzione e le credenziali di accesso utilizzate da ciascun servizio per l'autenticazione. Sono disponibili diversi strumenti che supportano gli amministratori nello svolgimento di questa attività, tra cui:
  
-   **System information in Microsoft Windows Server 2003**. System information può fornire un elenco completo delle proprietà di tutti i servizi in esecuzione su un computer locale. Tuttavia, questo strumento non offre un metodo molto efficace per il controllo di un numero elevato di server.
  
-   **Console di gestione dei servizi**. Nella console di amministrazione dei servizi, è possibile utilizzare la scheda **Connessione** della pagina **Proprietà** del servizio per stabilire l'account utilizzato da un servizio per l'autenticazione. La scheda **Dipendenze** può essere utilizzata anche per determinare quali sono i servizi da cui dipende il servizio specificato e quali sono i servizi che dipendono dal servizio visualizzato. Sfortunatamente, anche questo metodo risulta inefficace per il controllo di un numero elevato di server.
  
-   **Strumentazione gestione Windows (WMI**). WMI può essere utilizzato per ottenere informazioni sui servizi in esecuzione su tutti i server in una rete. Se viene utilizzato con degli script o con altri strumenti di programmazione, WMI può essere utile per ottenere dettagli di configurazione relativi a molti aspetti dei computer in rete, nonché delle modifiche apportate a tali computer.
  
-   **Riga di comando Strumentazione gestione Windows (WMIC)**. WMIC fornisce la stessa funzionalità di WMI sotto forma di strumento della riga di comando in grado di interagire con shell esistenti e altri programmi di utilità che possono essere estesi con script o altre applicazioni.
  
    Con il servizio WMIC, è possibile ottenere svariate informazioni sui servizi in esecuzione in una rete, tra cui:
  
    -   Descrizione
  
    -   DisplayName
  
    -   ErrorControl
  
    -   InstallDate
  
    -   PathName
  
    -   ProcessId
  
    -   StartMode
  
    -   StartName
  
    -   Stato
  
    -   Script
  
        Come indicato in precedenza, è possibile utilizzare WMIC per automatizzare la gestione dei computer remoti e locali mediante gli script.
  
-   **Altri strumenti di gestione aziendale**. Esistono svariati strumenti di gestione che possono essere utilizzati per supportare il controllo dei servizi server, tra cui:
  
    -   Microsoft Systems Management Server (SMS)
  
    -   IBM Tivoli
  
    -   HP OpenView
  
    -   Lieberman Software Service Account Manager
  
##### Determinazione dei servizi necessari
  
In occasione della prima installazione, Windows Server 2003 crea diversi servizi predefiniti e li configura affinché vengano eseguiti all'avvio del computer. Questi servizi predefiniti forniscono la compatibilità delle applicazioni e del client, oppure facilitano la gestione dei sistemi. Tuttavia, non in tutti gli ambienti è richiesto l'uso di tutti questi servizi. È necessario che tali servizi vengano esaminati per stabilire se sia possibile disattivare o meno alcuni di essi, riducendo così il profilo di vulnerabilità del server su cui sono in esecuzione.
  
Il processo di definizione dei servizi necessari e di quelli che possono essere disattivati può risultare complesso. Alcuni servizi forniscono risposte ovvie, ma altri potrebbero non presentare delle opzioni altrettanto definite. Nel determinare quali sono i servizi che possono essere disattivati, è possibile seguire due criteri principali:
  
-   Se non vi è alcun motivo specifico per l'utilizzo di un determinato servizio, questo può essere disattivato.
  
-   Se il servizio potrebbe essere utile in futuro, ma non attualmente, può essere disattivato.
  
I servizi necessari su server particolari dipendono principalmente dal ruolo dello specifico server. Ad esempio, il servizio Internet Information Services (IIS) deve essere utilizzato solo su un server Web o su un server delle applicazioni che utilizza un meccanismo di distribuzione basato sul Web. Se tale server non utilizza i servizi Telnet o i servizi di accesso remoto, questi devono essere disattivati su quel server.
  
Quando il software viene installato su un server, viene installata anche la relativa serie di servizi. Ad esempio, Microsoft Systems Management Services installerà il servizio Agente di controllo remoto Wuser32 per specificare la funzionalità del client remoto per gli aggiornamenti del software o per la gestione remota. È importante comprendere quali sono i servizi che potrebbero essere installati da un pacchetto software o su cui si potrebbe basare tale pacchetto nella determinazione dei servizi da disattivare.
  
##### Utilizzo di Configurazione guidata impostazioni di sicurezza
  
La configurazione guidata impostazioni di sicurezza, fornita con Windows Server 2003 Service Pack 1 (SP1), può essere utilizzata per configurare in modo rapido i server basati su requisiti funzionali, ad esempio il server Web o il controller di dominio, consentendo al tempo stesso agli amministratori di creare criteri di protezione che consentano di ridurre le vulnerabilità. La configurazione guidata impostazioni di sicurezza può essere utilizzata per scoprire quali sono i servizi in esecuzione sui server nella rete e le relative dipendenze.
  
**Per installare la configurazione guidata impostazioni di sicurezza su un server Windows Server 2003**
  
1.  Aprire il Pannello di controllo.
  
2.  Fare doppio clic su **Installazione applicazioni**.
  
3.  Fare clic su **Installazione componenti di Windows**.
  
4.  Selezionare la casella di controllo **Configurazione guidata impostazioni di sicurezza** in **Componenti** nella schermata **Componenti di Windows**.
  
5.  Fare clic su **Avanti**.
  
6.  Al termine del processo di installazione, fare clic su **Fine**.
  
La configurazione guidata impostazioni di sicurezza può essere utilizzato per ridurre la superficie di attacco dei computer su cui è in esecuzione Windows Server 2003 con SP1. Questa procedura guida gli amministratori nel processo di creazione dei criteri di protezione in base ai ruoli eseguiti da ogni server. L'espressione *ruolo del server* definisce la funzione principale di un computer all'interno di una rete; pertanto, i servizi necessari, le porte di ingresso e le impostazioni varieranno in base al ruolo eseguito da un server. Dopo aver creato i criteri, a seconda della configurazione, è possibile applicarli ai server.
  
##### Eliminazione dell'uso degli account amministratore di dominio per i servizi
  
Al termine della verifica di un server, dovrebbero essere disponibili informazioni sufficienti sull'ambiente che consentono di identificare ed eliminare tutte le possibili istanze degli account amministratore di dominio utilizzate per l'autenticazione del servizio. Se possibile, i servizi devono essere ridistribuiti mediante gli account Servizio locale, Servizio di rete o Sistema locale.
  
Gli sforzi atti a correggere gli account equivalenti a quelli di amministratore tramite i servizi devono concentrarsi fondamentalmente sulle seguenti situazioni:
  
-   Account utente con privilegi equivalenti a quelli di amministratore che effettuano l'accesso come servizio.
  
-   Account amministratore predefiniti che accedono come servizio.
  
-   Account amministratore di dominio che effettuano l'accesso come servizio a computer con protezione bassa.
  
##### Utilizzo di gerarchie di privilegio minimo per la distribuzione del servizio
  
Come affermato in precedenza nel presente articolo, i servizi devono utilizzare sempre l'account con privilegi minimi necessari per eseguire il servizio. Tutti i servizi che dispongono di privilegi maggiori rispetto a quelli necessari, devono essere ridistribuiti utilizzando gli account con privilegi inferiori.
  
Una gerarchia di privilegio minimo deve prendere in considerazione gli account per l'utilizzo del servizio nel seguente ordine decrescente di preferenza:
  
-   Servizio locale
  
-   Servizio di rete
  
-   Account utente locale univoco
  
-   Account utente dominio univoco
  
-   Sistema locale
  
-   Account amministratore locale
  
-   Account amministratore di dominio
  
##### Creazione di gruppi di server con protezione elevata per le eccezioni
  
I server con protezione elevata sono fondamentalmente server che contengono risorse o forniscono servizi da cui dipende l'azienda o che costituiscono un rischio di protezione elevato. Generalmente, i server che soddisfano criteri di questo tipo includono:
  
-   Controller di dominio.
  
-   Server che utilizzano i servizi per eseguire l'autenticazione con un account amministratore di dominio.
  
-   Server affidabili per la delega in una foresta.
  
-   Server utilizzati da gruppi aziendali riservati o che contengono dati aziendali critici, ad esempio un server delle risorse umane con informazioni sulla retribuzione.
  
-   Server che eseguono servizi resi affidabili per la delega in una foresta mediante la delega vincolata in Windows Server 2003.
  
La creazione di un gruppo di server con protezione elevata implica, generalmente, le seguenti attività:
  
1.  Identificare i server che devono essere designati come server con protezione elevata.
  
2.  Creare un gruppo di protezione universale per i server con protezione elevata in ciascuna foresta.
  
3.  Posizionare gli account dei computer dei server designati nei nuovi gruppi universali.
  
4.  Creare un gruppo locale di Account amministratore dominio in ciascun dominio.
  
5.  Posizionare tutti gli account equivalente all'utente amministratore di dominio nel nuovo gruppo locale.
  
6.  Creare un oggetto Criteri di gruppo in ogni dominio che limita l'uso degli account amministratore al livello di dominio per i servizi di tutti i computer assegnando i diritti utente **Nega accesso come servizio** e **Nega accesso come processo batch** e applicando le autorizzazioni **consenti-leggi** e **consenti-applica** sul GPO per il gruppo locale di dominio Account amministratore dominio creato.
  
7.  Utilizzare il filtro dei criteri di gruppo per il gruppo di server con protezione elevata su ogni GPO, in modo che ai membri di quel gruppo sia ancora consentito l'uso di account amministratore di dominio per i servizi. Questa funzionalità può essere ottenuta applicando le autorizzazioni **consenti-leggi** e **nega-applica** al GPO per il gruppo di server con protezione elevata.
  
La gestione dei membri del gruppo di server con protezione elevata deve utilizzare un processo del flusso di lavoro interno che valuta le richieste di aggiunte al gruppo. Questo processo prevede operazioni di convalida delle richieste e di valutazione dei rischi di protezione associati all'aggiunta di un server al gruppo. La base di questo processo può variare da un processo semplice, ad esempio richieste di posta elettronica a un account specifico, a un processo automatizzato dettagliato che utilizza un numero qualsiasi di strumenti di provisioning, ad esempio Zero Touch Provisioning (ZTP).
  
ZTP esula dallo scopo di questo documento in quanto si tratta di uno strumento studiato appositamente per gli ambienti di aziende di grandi dimensioni. Tuttavia, ulteriori informazioni su ZTP e altri strumenti simili sono disponibili sul sito Web Microsoft [Desktop Deployment Center](http://technet.microsoft.com/desktopdeployment/) all'indirizzo http://technet.microsoft.com/desktopdeployment/.
  
##### Gestione delle modifiche delle password dell'account di servizio
  
Quando gli account vengono assegnati a un servizio, Gestione controllo servizi (SCM) richiede la password corretta per l'account specifico prima di procedere con l'assegnazione. Se viene fornita una password non corretta l'assegnazione verrà rifiutata da SCM. La configurazione dei servizi per l'uso degli account Sistema locale, Servizio locale o Servizio di rete impedisce di gestire le password degli account in quanto vengono gestite dal sistema operativo.
  
Per gli altri account del servizio, SCM memorizza le password degli account nel database dei servizi. Dopo aver assegnato le password, SCM non verifica le password memorizzate in quel database, pertanto permane la password assegnata a un account utente in Active Directory. Ciò può essere causa di problemi quando:
  
1.  Un servizio viene configurato per l'utilizzo di un account utente specifico.
  
2.  Il servizio si avvia utilizzando l'account specificato con la password corrente.
  
3.  La password per l'account utente viene modificata mentre il servizio continua l'esecuzione.
  
4.  Il servizio continua l'esecuzione fino a quando non viene arrestato. Dopo l'arresto, non può essere riavviato poiché SCM tenta ancora di utilizzare la vecchia password. Le modifiche alla password in Active Directory non vengono sincronizzate con le password memorizzate nel database dei servizi.
  
Tutti i servizi che utilizzano un dominio standard o un account utente locale devono essere aggiornati con le nuove informazioni di autenticazione ogni qualvolta si modifica la password di quell'account utente. Questa operazione potrebbe richiedere molto tempo e grandi sforzi se i servizi e gli account utilizzati non sono documentati nel modo corretto.
  
Ovviamente, l'esistenza di un documento contenente informazioni sull'account per tutti i servizi utilizzati su tutti i server presenta un rischio di protezione univoco, pertanto per proteggere un documento di questo tipo è opportuno effettuare delle operazioni. Le organizzazioni di grandi dimensioni possono registrare queste informazioni in un file crittografato, che viene conservato in modalità non in linea e memorizzato in una posizione sicura. Le organizzazioni di piccole dimensioni possono semplicemente registrare le informazioni su carta in un raccoglitore riposto in un posto sicuro e non accessibile.
  
Alcune applicazioni possono anche utilizzare password dell'account del servizio, quali Exchange Server o SQL Server™, pertanto è necessaria particolare attenzione alla modifica di password rilevanti nell'interfaccia dell'applicazione.
  
Per informazioni sulle modalità di scrittura degli strumenti per automatizzare il processo di modifica delle password degli account del servizio, vedere l'articolo "[Changing the Password on a Service’s User Account](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/ad/ad/changing_the_password_on_a_serviceampaposs_user_account.asp)" (in inglese) all'indirizzo http://msdn.microsoft.com/library/default.asp?url=/library/en-us/ad/ad/changing\_the\_password\_on\_a\_serviceampaposs\_user\_account.asp.
  
##### Imposizione dell'uso di password complesse
  
Come indicato nella sezione corrispondente per gli account amministratore, l'uso di criteri password complessi deve essere severamente imposto su tutti gli account con privilegi equivalenti a quelli di amministratore, oltre che su tutti gli account del servizio. Per imporre regole di questo tipo, è possibile utilizzare Criteri di gruppo per applicare le date di scadenza della password, i limiti di lunghezza minimi e altre regole per le password complesse.
  
Per ulteriori informazioni sui criteri delle password complesse, vedere il white paper "[Account Passwords and Policies](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/bpactlck.mspx)" (in inglese) all'indirizzo http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/bpactlck.mspx 
  
Per ulteriori informazioni su come applicare le password complesse, vedere [*Windows Server 2003 Security Guide*](http://go.microsoft.com/fwlink/?linkid=14845) (in inglese) all'indirizzo http://go.microsoft.com/fwlink/?linkid=14845.
  
Le password vulnerabili rappresentano una delle vulnerabilità più comuni in una rete e quando vengono utilizzate con account con privilegi equivalenti a quelli di amministratore rappresentano uno dei modi più semplici tramite cui un malintenzionato può accedere alle risorse di rete. L'uso di strumenti di verifica automatizzati per il rilevamento degli account con privilegi equivalenti a quelli di amministratore che utilizzano password vulnerabili, dovrebbe essere un'attività pianificata a intervalli regolari ed seguita dai responsabili della protezione o della gestione di una rete.
  
Per eseguire tale operazione, lo strumento Microsoft Baseline Security Analyzer (MBSA) può effettuare la scansione di ciascun computer nella rete alla ricerca delle password vulnerabili. MBSA può enumerare tutti gli account utente e verificare le seguenti vulnerabilità correlate alle password:
  
-   Password vuote.
  
-   Password che corrispondono a nomi di account utente.
  
-   Password che corrispondono a nomi di computer.
  
-   Password che utilizzano il termine"password", "admin" o "administrator".
  
Se applicato, MBSA tenta di utilizzare ciascuna vulnerabilità elencata per modificare la password di un account. Quando viene rilevata una password vulnerabile, MBSA non modifica la password ma la contrassegna come un rischio di protezione. MBSA riporta anche tutti gli account disattivati o bloccati.
  
Nonostante MBSA rilevi le password vulnerabili più comuni, non fornisce funzionalità complete per il controllo delle password. Per queste esigenze, sul mercato sono disponibili strumenti e applicazioni di scansione non in linea di terze parti.
  
Per ulteriori informazioni su MBSA o per scaricare questo strumento, vedere la pagina Web [Microsoft Baseline Security Analyzer](http://www.microsoft.com/technet/security/tools/mbsahome.mspx) (in inglese) all'indirizzo www.microsoft.com/technet/security/tools/mbsahome.mspx.
  
**Nota**    MBSA ripristina tutti i criteri di blocco account individuati in un computer per impedire il blocco degli account durante il processo di scansione. Inoltre, MBSA esegue le scansioni delle password sui computer designati come controller di dominio.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Ovviamente, per migliorare la protezione degli account del servizio e critici in una rete aziendale di piccole dimensioni, è possibile eseguire diverse operazioni. Queste operazioni si basano, fondamentalmente, su pochi concetti chiave, ad esempio stabilire processi ben documentati e utilizzare le procedure che seguono il principio del privilegio minimo. La comprensione e l'utilizzo di questi pochi concetti chiave come base per la gestione dell'account consentirà di aumentare enormemente la protezione di qualsiasi rete.
  
In un ambiente aziendale di dimensioni medie, è possibile utilizzare un numero qualsiasi di procedure consigliate descritte in questo documento, sempre che siano ritenute adatte per i requisiti aziendali. Nonostante tutte queste procedure combinate aumenterebbero senza dubbio la sicurezza di qualsiasi rete, la soluzione migliore consiste nell'analizzare il potenziale impatto di ciascuna su una rete aziendale per stabilire la combinazione di approcci più compatibile.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Appendice A: Servizi comuni
  
La seguente tabella elenca e descrive in ordine alfabetico i servizi comuni di Windows Server 2003 e Windows XP. Sebbene questo elenco includa i servizi predefiniti e quelli che possono essere aggiunti a un computer, non si tratta di un elenco completo di tutti i servizi installabili su un computer, in quanto non include i servizi che potrebbero essere installati da pacchetti software di terze parti.
  
**Tabella A.1 Descrizioni dei servizi di Windows XP e Windows Server 2003**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Servizio</th>
<th>Nome del servizio</th>
<th>Accesso come</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">6to4</td>
<td style="border:1px solid black;">IP Version 6 Helper Service</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Attiva la connettività IPv6 sulle reti IPv4.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">AELookupSvc</td>
<td style="border:1px solid black;">Servizio di verifica compatibilità applicazioni</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Elabora le richieste di ricerca di compatibilità delle applicazioni al loro avvio. Il servizio deve essere attivato per poter ottenere gli aggiornamenti del software di compatibilità applicazioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Avvisi</td>
<td style="border:1px solid black;">Avvisi</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Questo servizio notifica gli avvisi amministrativi agli utenti e ai computer selezionati e, per la consegna, si basa sul servizio Messenger presenti sui computer client.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ALG</td>
<td style="border:1px solid black;">Servizio Gateway di livello applicazione</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Fornisce il supporto per i plugin che consentono ai protocolli di rete di passare attraverso il firewall e di lavorare con supporto ICS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">AppMgmt</td>
<td style="border:1px solid black;">Gestione applicazione</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce servizi di installazione software, quali Assegna, Pubblica e Rimuovi. Se disattivato, le applicazioni non possono essere installate tramite i servizi Active Directory, come IntelliMirror®.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">AppMgr</td>
<td style="border:1px solid black;">Gestione remota server</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Opera come provider dell'istanza WMI per gli oggetti degli avvisi di amministrazione remota e da provider di metodo WMI per le attività di gestione remote.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">aspnet_state</td>
<td style="border:1px solid black;">Servizio Stato di ASP.NET</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Fornisce supporto per gli stati di sessione out-of-process di ASP.NET.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">AudioSrv</td>
<td style="border:1px solid black;">Windows Audio</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce i dispositivi audio per i programmi basati su Windows.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">BINLSVC</td>
<td style="border:1px solid black;">Installazione remota</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">È il componente principale del server di installazione remota (RIS), che risponde alle richieste PXE per i computer abilitati all'avvio remoto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">BITS</td>
<td style="border:1px solid black;">Servizio trasferimento intelligente in background</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Fornisce un meccanismo di trasferimento di file in background per il gestore di coda. Quando questo servizio si arresta, il computer non è più in grado di utilizzare le funzioni di aggiornamento automatico.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Browser</td>
<td style="border:1px solid black;">Browser di computer</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce un elenco aggiornato dei computer in rete.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CertSvc</td>
<td style="border:1px solid black;">Servizi certificati</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Parte del sistema operativo principale che emette e gestisce i certificati digitali.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">cisvc</td>
<td style="border:1px solid black;">Servizio di indicizzazione</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce rapido accesso ai file tramite un linguaggio di query indicizzando i contenuti e le proprietà dei file.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ClipSrv</td>
<td style="border:1px solid black;">Cartella Appunti</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita il Visualizzatore Cartella appunti per creare e condividere le pagine di dati per la revisione da parte di utenti remoti.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ClusSvc</td>
<td style="border:1px solid black;">Servizi cluster</td>
<td style="border:1px solid black;">Account di dominio</td>
<td style="border:1px solid black;">Controlla le operazione del cluster di server e gestisce il database del cluster.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">COMSysApp</td>
<td style="border:1px solid black;">Applicazione di sistema COM+</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce la configurazione e la registrazione di componenti basati su COM+. I componenti COM+ non funzionano correttamente se questo servizio è disattivato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CORRTSvc</td>
<td style="border:1px solid black;">Servizio per il supporto di .NET Framework</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Avvisa i client sottoscrittori quando i processi specificati inizializzano il servizio runtime client.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CryptSvc</td>
<td style="border:1px solid black;">Servizi di crittografia</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce i servizi di gestione delle chiavi crittografiche per i computer basati su Windows.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DcomLaunch</td>
<td style="border:1px solid black;">Utilità di avvio processo server DCOM</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce parte dei servizi RPC che richiedono i privilegi del sistema locale in combinazione con il servizio RPCSS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Dfs</td>
<td style="border:1px solid black;">File system distribuito</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Integra diverse condivisioni di file posizionate nella rete in un unico spazio dei nomi logico. Necessario per la condivisione del volume SYSVOL.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DFSR</td>
<td style="border:1px solid black;">Replica di file system distribuiti</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Copia automaticamente gli aggiornamenti nei file e nelle cartelle tra i computer che fanno parte di un gruppo di replica comune (aggiunto in Windows Server 2003 R2).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Dhcp</td>
<td style="border:1px solid black;">Client DHCP</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Gestisce le informazioni sulla configurazione di rete DHCP registrando e aggiornando gli indirizzi IP.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DHCPServer</td>
<td style="border:1px solid black;">Server DHCP</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Questo servizio gestisce DHCP e assegna gli indirizzi IP ai computer client.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dmadmin</td>
<td style="border:1px solid black;">Servizio amministrativo di Gestione dischi logici</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Esegue i servizi di amministrazione per le richieste di gestione dei dischi e configura i dischi e i volumi. Questo servizio viene eseguito solo durante i processi di configurazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dmserver</td>
<td style="border:1px solid black;">Gestione dischi logici</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Rileva e controlla le nuove unità disco e invia le informazioni sul volume al servizio dmadmin. Non disattivare se nel computer sono in uso i dischi dinamici.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DNS</td>
<td style="border:1px solid black;">Server DNS</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita la risoluzione dei nomi DNS rispondendo alle query e aggiornando le richieste per i nomi DNS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Dnscache</td>
<td style="border:1px solid black;">Client DNS</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Consente di risolvere e memorizzare nella cache i nomi DNS e deve essere eseguito su ogni computer che esegue la risoluzione dei nomi DNS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ERSvc</td>
<td style="border:1px solid black;">Servizio di segnalazione errori</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Raccoglie, memorizza e crea report su errori o arresti imprevisti delle applicazioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Eventlog</td>
<td style="border:1px solid black;">Registro eventi</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Scrive gli eventi inviati da programmi, servizi e dal sistema operativo ai registri degli eventi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">EventSystem</td>
<td style="border:1px solid black;">COM+ Event System</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente la distribuzione automatica di eventi ai componenti COM dei quali viene eseguita la sottoscrizione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Compatibilità di Cambio rapido utente</td>
<td style="border:1px solid black;">Compatibilità di Cambio rapido utente</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente la gestione delle applicazioni che richiedono assistenza in ambienti multiutente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Fax</td>
<td style="border:1px solid black;">Servizio Fax</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Provider di funzioni fax compatibile con TAPI.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Groveler</td>
<td style="border:1px solid black;">Agente di archiviazione istanza singola</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Parte integrante del servizio di installazione remoto (RIS) che trova i file duplicati e copia l'originale in Archiviazione istanza singola.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">helpsvc</td>
<td style="border:1px solid black;">Guida in linea e supporto tecnico</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce l'accesso agli archivi e ai servizi che contengono i metadati e le informazioni relative agli argomenti per l'applicazione Guida in linea e supporto tecnico.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">HidServ</td>
<td style="border:1px solid black;">Accesso periferica Human Interface</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita l'accesso con input generico ai dispositivi USB, quali tastiere e mouse.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">HTTPFilter</td>
<td style="border:1px solid black;">SSL HTTP</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente l'esecuzione di funzioni SSL.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IAS</td>
<td style="border:1px solid black;">Servizio autenticazione Internet (IAS)</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Esegue l'autenticazione, l'autorizzazione, il controllo e l'amministrazione centralizzati degli utenti che si collegano a una rete.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IASJet</td>
<td style="border:1px solid black;">IAS Jet Database Access</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce l'autenticazione, l'autorizzazione e l'amministrazione dei servizi tramite il protocollo RADIUS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">IISADMIN</td>
<td style="border:1px solid black;">Servizio Amministrazione di IIS</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Consente l'amministrazione dei componenti IIS quali FTP ed estensioni dei servizi Web.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ImapiService</td>
<td style="border:1px solid black;">Servizio COM di masterizzazione CD IMAPI</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce la creazione dei CD tramite l'interfaccia COM IMAPI e, se richiesto, esegue operazioni di scrittura su CD-R.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Irmon</td>
<td style="border:1px solid black;">Monitor infrarossi</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita la condivisione di file tramite le connessioni a infrarossi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">IsmServ</td>
<td style="border:1px solid black;">Messaggistica tra siti</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita lo scambio dei messaggi tra computer in cui è in esecuzione Windows Server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">kdc</td>
<td style="border:1px solid black;">Centro distribuzione chiave Kerberos</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente l'accesso degli utenti tramite il protocollo di autenticazione Kerberos. Se il servizio viene arrestato, i client non possono accedere a un dominio.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">lanmanserver</td>
<td style="border:1px solid black;">Server</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Assicura il supporto RPC e la condivisione in rete di file, stampanti e named pipe.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Workstation Lanman</td>
<td style="border:1px solid black;">Workstation</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce connessioni e comunicazioni in rete per i servizi client.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">LicenseService</td>
<td style="border:1px solid black;">Registrazione licenze</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Progettato in origine per gestire le licenze CAL introdotte con Windows NT® Server 3.51. Deve essere abilitato solo da utenti di Microsoft Small Business Server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">LMHosts</td>
<td style="border:1px solid black;">Servizio guida TCP/IP NetBIOS</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Fornisce supporto per NetBIOS su TCP/IP e per la risoluzione dei nomi NetBIOS per i client.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">LPDSVC</td>
<td style="border:1px solid black;">Server di stampa TCP/IP</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita la stampa basata su TCP/IP tramite il protocollo LPD per la ricezione dei documenti dalle utilità LPD installate nelle piattaforme basate su UNIX.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">LSASS</td>
<td style="border:1px solid black;">Autorità di protezione locale</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce un'interfaccia per la gestione della protezione locale, dell'autenticazione di domini e dei processi Active Directory.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MacFile</td>
<td style="border:1px solid black;">File server per Macintosh</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente agli utenti Macintosh di archiviare e accedere ai file su Windows Server 2003.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MacPrint</td>
<td style="border:1px solid black;">Server di stampa per Macintosh</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente agli utenti Macintosh di utilizzare i servizi di stampa di Windows Server 2003.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MDM</td>
<td style="border:1px solid black;">Machine Debug Manager</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Gestisce il debug locale e remoto per le applicazioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Messenger</td>
<td style="border:1px solid black;">Messenger</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Invia i messaggi o li riceve dal servizio Avvisi. Non è correlato a Windows Messenger e, se disattivato, impedisce l'uso dei comandi net send e net name.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">mnmsrvc</td>
<td style="border:1px solid black;">Condivisione desktop remoto di NetMeeting</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente agli utenti autorizzati di accedere a Windows Desktop da altri computer tramite i servizi Windows NetMeeting®.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">mqds</td>
<td style="border:1px solid black;">Accodamento messaggi per i client di livello inferiore</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce l'accesso di Active Directory per le vecchie versioni di Windows che utilizzano il servizio di accodamento messaggi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Mqtgsvc</td>
<td style="border:1px solid black;">Trigger Accodamento messaggi</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente a un sistema basato su regole di controllare i messaggi in arrivo in un servizio di Accodamento messaggi e richiama i servizi di elaborazione messaggi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSDTC</td>
<td style="border:1px solid black;">Distributed Transaction Coordinator</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Coordina le transazioni distribuite su più computer, database, file system, code messaggi e altri programmi di gestione di risorse protette da transazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSExchange MTA</td>
<td style="border:1px solid black;">Stack Agente di trasferimento messaggi di Microsoft Exchange</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Fornisce il servizio di trasferimento messaggi compatibile con le versioni precedenti in un ambiente a modalità mista.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MSFTPSVC</td>
<td style="border:1px solid black;">Servizio Pubblicazione tramite FTP</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Fornisce la connettività e la gestione FTP tramite lo snap-in di IIS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSIServer</td>
<td style="border:1px solid black;">Windows Installer</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce l'installazione e la rimozione delle applicazioni applicando gruppi di regole di configurazione definite centralmente durante i processi di installazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">msmq</td>
<td style="border:1px solid black;">Accodamento messaggi</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Opera come infrastruttura di messaggistica e strumento di sviluppo per l'attivazione della messaggistica distribuita per i programmi Windows.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSSQL$UDDI</td>
<td style="border:1px solid black;">MSSQL$UDDI</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Fornisce servizi UDDI (Universal Description, Discovery and Integration) al modulo di gestione di database SQL Server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SERVER MSSQL</td>
<td style="border:1px solid black;">Server MSSQL</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Fornisce servizi MS SQL Server configurabili.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MSSQLServer ADHelper</td>
<td style="border:1px solid black;">MSSQL Server ADHelper</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita SQL Server e SQL Server Analysis Services per la pubblicazione delle informazioni in Active Directory.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">NetDDE</td>
<td style="border:1px solid black;">DDE di rete</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce il trasporto di rete e la protezione per lo scambio dinamico dei dati (DDE) per i programmi eseguiti nello stesso computer o in computer diversi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">NetDDEdsdm</td>
<td style="border:1px solid black;">DDE DSDM di rete</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce le condivisioni di rete DDE.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Netlogon</td>
<td style="border:1px solid black;">Netlogon</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce un canale di protezione tra i computer client e i controller di dominio per l'autenticazione di servizi e utenti.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Netman</td>
<td style="border:1px solid black;">Connessioni di rete</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce gli oggetti nella cartella Connessioni di rete.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Connessioni di rete</td>
<td style="border:1px solid black;">Connessioni di rete</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce gli oggetti nella cartella Rete e connessioni remote, da cui è possibile visualizzare la rete e le connessioni remote.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">NLA</td>
<td style="border:1px solid black;">Network Location Awareness</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Raccoglie e archivia le informazioni sulla configurazione di rete ed elabora le informazioni sulla modifica dei percorsi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">NntpSvc</td>
<td style="border:1px solid black;">Network News Transfer Protocol</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente ai computer di operare come server news NNTP.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">NtFrs</td>
<td style="border:1px solid black;">Replica file</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Copia automaticamente gli aggiornamenti nei file e nelle cartelle tra i computer che fanno parte di un set di repliche FRS comune.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">NtLmSsp</td>
<td style="border:1px solid black;">Provider supporto protezione LM NT</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Responsabile dell'autenticazione e della gestione degli oggetti dei criteri di protezione locale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Workstation NWC</td>
<td style="border:1px solid black;">Servizio client per NetWare</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Fornisce l'accesso al file NetWare e alle risorse di stampa.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">nwsapagent</td>
<td style="border:1px solid black;">Agente SAP</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Annuncia i servizi di rete in reti IPX utilizzando il protocollo IPX SAP.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">one point</td>
<td style="border:1px solid black;">Agente Microsoft Operations Manager 2000</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Agente Microsoft Operations Manager (MOM) 2000.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PlugPlay</td>
<td style="border:1px solid black;">Plug and Play</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente il riconoscimento delle modifiche apportate all'hardware senza l'input dell'utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PolicyAgent</td>
<td style="border:1px solid black;">Servizio IPsec</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce i criteri IPsec, avvia IKE e coordina le impostazioni dei criteri IPsec nel driver di protezione IP.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">POP3SVC</td>
<td style="border:1px solid black;">Servizio POP3 Microsoft</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Fornisce servizi di trasferimento e di recupero della posta elettronica.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Archiviazione protetta</td>
<td style="border:1px solid black;">Archiviazione protetta</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente l'archiviazione protetta dei dati riservati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">RasAuto</td>
<td style="border:1px solid black;">Auto Connection Manager di Accesso remoto</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Crea connessioni ai computer remoti ogni volta che i programmi fanno riferimento a nomi o indirizzi DNS o NetBIOS remoti.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">RasMan</td>
<td style="border:1px solid black;">Connection Manager di Accesso remoto</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce connessioni remote e VPN alle reti remote.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">RDSessMgr</td>
<td style="border:1px solid black;">Gestione sessione di assistenza mediante desktop remoto</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce e controlla la funzione Assistenza remota all'interno dell'applicazione Guida in linea e supporto tecnico.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Remote_
Storage_Server</td>
<td style="border:1px solid black;">Server di archiviazione remota</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Sposta e richiama i file da un supporto di archiviazione secondario.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Remote_
Storage_User_
Link</td>
<td style="border:1px solid black;">Notifica di Archiviazione remota</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Il servizio Remote_Storage_User_Link avvisa gli utenti quando tentano di leggere o scrivere file disponibili solo in tipi di supporti di archiviazione secondari.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">RemoteAccess</td>
<td style="border:1px solid black;">Routing e Accesso remoto</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Offre servizi di routing multiprotocollo e servizi di accesso remoto e VPN.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">RemoteRegistry</td>
<td style="border:1px solid black;">Servizio Registro di sistema remoto</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Abilita gli utenti locali a modificare le impostazioni del Registro di sistema con autorizzazioni adeguate.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">RpcLocator</td>
<td style="border:1px solid black;">RPC Locator</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Gestisce il database della risoluzione dei nomi RPC in modo che i client RPC possano individuare i server RPC. Per impostazione predefinita è disattivato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">RpcSs</td>
<td style="border:1px solid black;">Remote Procedure Call</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Svolge la funzione di mapping degli endpoint RPC e di servizio COM (Component Object Model)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">RSoPProv</td>
<td style="border:1px solid black;">Provider del gruppo di criteri risultante</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita le connessioni ai controller di dominio Windows, l'accesso al database WMI e simula RSoP per le impostazioni dei criteri di gruppo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">RSVP</td>
<td style="border:1px solid black;">QoS RSVP</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce l'uso delle richieste API GQoS (Generic Quality of Service) provenienti dalle applicazioni.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Sacsvr</td>
<td style="border:1px solid black;">Helper console di amministrazione speciale</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Esegue le attività di gestione remota quando un sistema operativo della famiglia Windows Server si arresta a causa di messaggi di errore di interruzione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SamSs</td>
<td style="border:1px solid black;">Gestione account di protezione</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce le informazioni sull'account utente e di gruppo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SCardSvr</td>
<td style="border:1px solid black;">Smart card</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Gestisce e controlla l'accesso alle smart card quando vengono inserite nel relativo lettore collegato al computer.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Schedule</td>
<td style="border:1px solid black;">Utilità di pianificazione</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente di eseguire le attività automatizzate.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">seclogon</td>
<td style="border:1px solid black;">Accesso secondario</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente la creazione di processi nel contesto di diverse identità di protezione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SENS</td>
<td style="border:1px solid black;">Notifica eventi di sistema</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Tiene traccia degli eventi di sistema e di alimentazione e li notifica ai sottoscrittori del COM+ Event System.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SharedAccess</td>
<td style="border:1px solid black;">Firewall connessione di Windows/Condivisione connessione Internet</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce servizi NAT, di indirizzamento e di risoluzione dei nomi per tutti i computer della rete quando viene abilitato Condivisione connessione Internet.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ShellHW
Rilevamento</td>
<td style="border:1px solid black;">Rilevamento hardware shell</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce notifiche per gli eventi hardware AutoPlay.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SimpTcp</td>
<td style="border:1px solid black;">Servizi semplificati TCP/IP</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Fornisce servizi TCP/IP semplificati come Echo, Discard, Daytime, Character Generator e Quote of the Day.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SMTPSVC</td>
<td style="border:1px solid black;">Protocollo SMTP (Simple Mail Transport Protocol)</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">È un agente di invio e inoltro SMTP. Accetta e accoda i messaggi di posta elettronica verso e da destinazioni remote.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SNMP</td>
<td style="border:1px solid black;">Servizio SNMP</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente di soddisfare le richieste SNMP in entrata dal computer locale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SNMPTRAP</td>
<td style="border:1px solid black;">Servizio Trap SNMP</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Riceve i messaggi Trap SNMP generati da agenti SNMP locali o remoti e li inoltra ai server di gestione SNMP.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Spooler</td>
<td style="border:1px solid black;">Spooler di stampa</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce tutte le code di stampa locali e di rete e controlla tutti i processi di stampa.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SQLAgent$
WEBDB</td>
<td style="border:1px solid black;">SQL Agent$ UDDI o WebDB</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;"> </td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SrvcSurg</td>
<td style="border:1px solid black;">Servizio Amministrazione remota</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Responsabile dell'esecuzione delle attività di Amministrazione remota all'avvio del server, inclusi l'aumento del numero di avvii del server e, se non sono state impostate la data e l'ora del server, la visualizzazione degli avvisi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">StiSvc</td>
<td style="border:1px solid black;">Acquisizione di immagini di Windows (WIA)</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Fornisce servizi di acquisizione immagini per scanner e fotocamere.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">srservice</td>
<td style="border:1px solid black;">Servizio di ripristino del sistema</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Controlla le modifiche al sistema e ai file delle applicazioni, quindi crea punti di ripristino facilmente identificabili.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SSDPSRV</td>
<td style="border:1px solid black;">Servizio di rilevazione SSDP</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Gestisce gli avvisi di presenza del dispositivo, gli aggiornamenti della cache e le notifiche SSDP.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">StiSvc</td>
<td style="border:1px solid black;">Windows Image Acquisition (WIA)</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Consente un'elevata comunicazione tra le applicazioni e i dispositivi di acquisizione immagini per il trasferimento efficiente delle immagini al computer.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SwPrv</td>
<td style="border:1px solid black;">Provider di copie replicate software Microsoft</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce il software per le copie shadow di file create dal servizio VSS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">SysmonLog</td>
<td style="border:1px solid black;">Avvisi e registri di prestazioni</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Raccoglie le informazioni sul registro delle prestazioni e sugli avvisi, viene eseguito quando è pianificato almeno un evento di raccolta dati delle prestazioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">TapiSrv</td>
<td style="border:1px solid black;">Telefonia</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce il supporto TAPI per i programmi che controllano le periferiche di telefonia e le connessioni vocali su IP.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TermService</td>
<td style="border:1px solid black;">Servizi terminal</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente a più client di accedere alle sessioni desktop virtuali di Windows in esecuzione sul server.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">TermServ
Licenze</td>
<td style="border:1px solid black;">Licenze Servizi terminal</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Fornisce le licenze ai client registrati quando si collegano a un terminal server e ne tiene traccia.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">tftpd</td>
<td style="border:1px solid black;">Trivial FTP Daemon</td>
<td style="border:1px solid black;"> </td>
<td style="border:1px solid black;">Ascolta e risponde alle richieste TFTP.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Temi</td>
<td style="border:1px solid black;">Temi</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce il supporto di visualizzazione per l'interfaccia grafica utente (GUI) di Windows XP.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TlntSvr</td>
<td style="border:1px solid black;">Telnet</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce servizi Telnet agli utenti Windows e supporta i tipi di sessione terminale ANSI, VT-100, VT52 e VTNT.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">TrkSvr</td>
<td style="border:1px solid black;">Manutenzione collegamenti distribuiti server</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Archivia le informazioni in modo che i file spostati tra i volumi possano essere registrati in ogni volume nel dominio. Viene eseguito su ogni controller di dominio.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TrkWks</td>
<td style="border:1px solid black;">Manutenzione collegamenti distribuiti client</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce i collegamenti tra il file system NTFS sul computer o nella rete, nonché garantisce che i tasti di scelta rapida e i collegamenti OLE funzionino dopo aver spostato e ridenominato i file di destinazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Tssdis</td>
<td style="border:1px solid black;">Directory di sessione di Servizi terminal</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente di tenere traccia delle sessioni dei servizi terminal disconnessi in un cluster per assicurare che gli utenti vengano riconnessi a tali sessioni.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Uploadmgr</td>
<td style="border:1px solid black;">Upload Manager</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce i trasferimenti di file sincroni e asincroni tra i client e i server in una rete.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">upnphost</td>
<td style="border:1px solid black;">Universal Plug and Play Device Host</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Implementa tutti i componenti richiesti per la registrazione e il controllo della periferica, nonché la risposta agli eventi per i dispositivi ospitati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">UPS</td>
<td style="border:1px solid black;">Gruppo di continuità</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Gestisce le comunicazioni con un gruppo di continuità (UPS, Uninterruptible Power Supply) collegato al computer tramite la porta seriale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VDS</td>
<td style="border:1px solid black;">Servizio dischi virtuali</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce un'interfaccia singola per la gestione di una virtualizzazione dell'archiviazione a blocchi se eseguita in un software del sistema operativo, in un archivio RAID o in altri motori di virtualizzazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VSS</td>
<td style="border:1px solid black;">Copia shadow del volume</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce le istantanee di volume utilizzate dalle applicazioni di backup.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">W32Time</td>
<td style="border:1px solid black;">Ora di Windows</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Gestisce la sincronizzazione di data e ora con NTP.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">W3SVC</td>
<td style="border:1px solid black;">Servizio Pubblicazione sul Web</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Contiene un programma di gestione dei processi e delle configurazioni per fornire servizi di pubblicazione Web.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">WebClient</td>
<td style="border:1px solid black;">WebClient</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Consente alle applicazioni Win32 di accedere ai documenti in Internet.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gestione risorse
di sistema
Windows</td>
<td style="border:1px solid black;">Gestione risorse di sistema Windows</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente una gestione basata sui criteri della CPU e del consumo della memoria per i processi in esecuzione in un'unica istanza del sistema operativo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">WinHttpAutoSvc</td>
<td style="border:1px solid black;">Servizio Rilevamento automatico proxy Web WinHTTP</td>
<td style="border:1px solid black;">Servizio locale</td>
<td style="border:1px solid black;">Implementa la rilevazione della configurazione proxy per i client WinHttp.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">winmgmt</td>
<td style="border:1px solid black;">Strumentazione gestione Windows</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce informazioni sulla gestione del sistema tramite più interfacce.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">WINS</td>
<td style="border:1px solid black;">Windows Internet Name Service</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita la risoluzione dei nomi NetBIOS e la replica WINS.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">WmdmPmSN</td>
<td style="border:1px solid black;">Numero di serie del dispositivo portatile</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente a WMDM di richiamare i numeri di serie da dispositivi musicali portatili collegati al computer.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Wmi</td>
<td style="border:1px solid black;">Estensioni driver di Strumentazione gestione Windows</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Controlla tutti i driver e i provider di analisi eventi configurati per pubblicare le informazioni su WMI o sull'analisi degli eventi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">WmiApSrv</td>
<td style="border:1px solid black;">WMI Performance Adapter</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Trasforma i contatori delle prestazioni forniti dai provider WMI in contatori che possono essere utilizzati da PDH tramite Reverse Adapter Performance Library.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">WMServer</td>
<td style="border:1px solid black;">Windows Media Services</td>
<td style="border:1px solid black;">Servizio di rete</td>
<td style="border:1px solid black;">Abilita Windows Media Services.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">wscsvc</td>
<td style="border:1px solid black;">Centro sicurezza PC</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Controlla le impostazioni e le configurazioni di protezione del sistema.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">wuauserv</td>
<td style="border:1px solid black;">Aggiornamenti automatici</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita il download degli aggiornamenti dal sito Web Microsoft Windows Update.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Wuser32</td>
<td style="border:1px solid black;">SMS Remote Control Agent</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Fornisce i servizi di gestione di computer remoti, ad esempio i servizi di controllo remoto e di trasferimento file remoti, per SMS 2003.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">WZCSVC</td>
<td style="border:1px solid black;">Configurazione automatica reti wireless</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Abilita la configurazione automatica di schede wireless IEEE 802.11 per le comunicazioni wireless.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">xmlprov</td>
<td style="border:1px solid black;">Servizio Provisioning di rete</td>
<td style="border:1px solid black;">Sistema locale</td>
<td style="border:1px solid black;">Consente di scaricare e gestire i file di configurazione XML dai servizi di provisioning di rete, quali Microsoft Wireless Provisioning Service (WPS).</td>
</tr>
</tbody>
</table>
  
**Download**
  
[Richiedi la guida Protezione degli account critici e del servizio](http://go.microsoft.com/fwlink/?linkid=73609)
  
[](#mainsection)[Inizio pagina](#mainsection)
