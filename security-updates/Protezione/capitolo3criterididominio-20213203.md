---
TOCTitle: 'Capitolo 3: Criteri di dominio'
Title: 'Capitolo 3: Criteri di dominio'
ms:assetid: '833fddab-0361-4209-bef6-ee3b14acd18d'
ms:contentKeyID: 20213203
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163113(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Capitolo 3: Criteri di dominio

##### In questa pagina

[](#ehaa)[Panoramica](#ehaa)
[](#egaa)[Criteri dominio](#egaa)
[](#efaa)[Criteri di account](#efaa)
[](#eeaa)[Criterio password](#eeaa)
[](#edaa)[Criterio di blocco account](#edaa)
[](#ecaa)[Criteri Kerberos](#ecaa)
[](#ebaa)[Opzioni di protezione](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

Questo capitolo utilizza la creazione di un ambiente di dominio per illustrare le modalità e le procedure di protezione di un'infrastruttura per Windows Server 2003 con Service Pack 1 (SP1).

Questo capitolo si concentra sui seguenti argomenti:

-   Impostazioni di protezione e contromisure a livello di dominio.

-   Come proteggere un dominio Windows Server 2003 per gli ambienti Legacy Client (LC), Enterprise Client (EC) e Specialized Security – Limited Functionality (SSLF) descritti nel Capitolo 1, "Introduzione alla Guida per la protezione di Windows Server 2003".

Queste informazioni forniscono una base di partenza e una visione per passare da un ambiente LC a uno SSLF nell'ambito di un'infrastruttura di dominio.

Windows Server 2003 con SP1 viene consegnato con valori predefiniti impostati su un livello di protezione noto ed elevato. Per semplificare l'utilizzo di questo materiale, nel presente capitolo vengono prese in esame soltanto le impostazioni che sono state modificate rispetto ai valori predefiniti. Per le informazioni di tutte le impostazioni predefinite, consultare la guida correlata, [*Pericoli e contromisure: Impostazioni di Protezione in Windows Server 2003 e*
*Windows XP*](http://www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx), che è disponibile all'indirizzo http://www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx.

[](#mainsection)[Inizio pagina](#mainsection)

### Criteri dominio

Le impostazioni di protezione dei criteri di gruppo possono essere applicate a diversi livelli in un'organizzazione. L'ambiente di base trattato nel Capitolo 2, "Meccanismi di protezione avanzata di Windows Server 2003" ha utilizzato i criteri di gruppo per applicare le impostazioni ai tre livelli gerarchici dell'infrastruttura di dominio elencati di seguito:

-   **Livello di dominio**. Per gestire requisiti di protezione comuni, come i criteri di account e password che devono essere applicati a tutti i server del dominio.

-   **Livello base**. Per gestire requisiti specifici di protezione dei server comuni a tutti i server nell'infrastruttura di dominio.

-   **Livello specifico per i ruoli**. Le impostazioni a questo livello gestiscono i requisiti per ruoli di server specifici. Ad esempio, i requisiti di protezione per i server di infrastruttura sono diversi da quelli dei server che eseguono Microsoft Internet Information Services (IIS).

Nelle seguenti sezioni del presente capitolo verranno esaminati in dettaglio solo i criteri a livello di dominio. Gran parte delle impostazioni di protezione del dominio illustrate sono relative ad account utente e password. Quando si prendono in considerazione queste impostazioni e consigli, tenere presente che tutte le impostazioni sono valide per ogni utente nei limiti del dominio.

#### Panoramica sui criteri di dominio

I criteri di gruppo rappresentano una soluzione estremamente efficace, in quanto consentono a un amministratore di configurare un computer di rete standard. Gli oggetti Criteri di gruppo (GPO) possono fornire una parte significativa di una soluzione di gestione della configurazione per qualsiasi organizzazione, poiché consentono agli amministratori di eseguire simultaneamente modifiche della protezione su tutti i computer del dominio o sui sottoinsiemi del dominio.

Le sezioni che seguono forniscono informazioni dettagliate sulle impostazioni di protezione che si possono usare per migliorare la protezione di Windows Server 2003 con SP1. Sono incluse tabelle che riassumono le impostazioni e delle descrizioni dettagliate di come conseguire gli obiettivi di protezione per ogni impostazione. Le impostazioni sono suddivise in categorie che corrispondono alla relativa presentazione nell'interfaccia utente dell'Editor di configurazione della protezione di Windows Server 2003.

È possibile applicare simultaneamente i seguenti tipi di modifiche della protezione mediante i criteri di gruppo:

-   Modifica delle autorizzazioni per il file system.

-   Modifica delle autorizzazioni per gli oggetti del Registro di sistema.

-   Modifica delle impostazioni nel Registro di sistema.

-   Modifica delle assegnazioni dei diritti utente.

-   Configurazione dei servizi di sistema.

-   Configurazione del controllo e dei registri eventi.

-   Impostazione dei criteri di account e password.

Questa guida consiglia la creazione di un nuovo Criterio di gruppo nella directory principale del dominio per applicare i criteri a livello di dominio trattati in questo capitolo. Questo metodo semplifica la verifica o la risoluzione dei problemi del nuovo Criterio di gruppo, in quanto se è necessario ripristinare le modifiche è sufficiente disabilitarlo. Tuttavia, alcune applicazioni progettate per funzionare con Active Directory apportano modifiche al Criterio di dominio predefinito incorporato. Queste applicazioni non saranno al corrente del nuovo Criterio di gruppo implementato, se si seguono i consigli contenuti in questa guida. Prima di implementare le nuove applicazioni aziendali, accertarsi di averle verificate con cura. Se si incontrano dei problemi, controllare per vedere se l'applicazione ha modificato i criteri di account, ha creato nuovi account utente, ha modificato i diritti utente o ha effettuato altre modifiche al criterio di dominio predefinito o ai criteri del computer locale.

[](#mainsection)[Inizio pagina](#mainsection)

### Criteri di account

I criteri di account, che includono le impostazioni di protezione Criterio password, Criterio di blocco account e Criterio Kerberos, riguardano solo i criteri di dominio per i tre ambienti descritti in questa guida. Il Criterio password consente di impostare un certo livello di complessità e definire la pianificazione delle modifiche per ambienti con un alto livello di protezione. Il Criterio di blocco account consente di registrare i tentativi di accesso mediante password non riusciti per avviare, se necessario, il blocco dell'account. I Criteri Kerberos sono utilizzati per gli account utente di dominio e determinano le impostazioni relative al protocollo di autenticazione Kerberos, quali la durata del ticket e l'imposizione.

[](#mainsection)[Inizio pagina](#mainsection)

### Criterio password

La modifica costante di password complesse consente di ridurre il rischio che un eventuale attacco alla password abbia successo. Le impostazioni del criterio password controllano la complessità e la durata delle password. In questa sezione viene descritta ogni impostazione specifica del criterio password e il modo in cui si collegano a ognuno dei tre ambienti descritti in questa guida: Legacy Client, Enterprise Client e Specialized Security – Limited Functionality.

Il fatto che i requisiti sono più rigidi per quanto riguarda lunghezza e complessità della password non significa necessariamente che utenti e amministratori utilizzeranno password complesse. Anche se il Criterio password può richiedere che gli utenti aderiscano ai requisiti di complessità tecnica, serve un ulteriore criterio di protezione forte per far sì che gli utenti creino password difficili da violare. Per esempio, la password "Colazione!" potrebbe essere conforme a tutti i requisiti di complessità delle password, tuttavia non è una password difficile da violare.

Se si è al corrente di certi aspetti dalla vita della persona che crea una password, si potrebbe essere in grado di indovinare la password, se è basata su cibi, macchine o film preferiti. Una strategia di programmi di protezione aziendali per la sensibilizzazione degli utenti alla scelta di password complesse prevede la creazione di un poster in cui sono descritti esempi di password deboli e l'affissione di tali poster in aree comuni, ad esempio vicino al distributore automatico o alla fotocopiatrice All'interno dell'organizzazione devono essere definite linee guida rigide relativamente alla creazione di password che devono includere i seguenti aspetti:

-   Non utilizzare parole di senso compiuto, in qualsiasi lingua, o contenenti errori di digitazione intenzionali.

-   Non creare una password nuova che semplicemente aumenti di una lettera quella attuale.

-   Evitare l'uso di password che inizino o finiscano con una cifra, perché possono essere indovinate più facilmente di quelle con una cifra nel mezzo.

-   Evitare l'utilizzo di password che possono essere facilmente individuate sulla base di informazioni personali (ad esempio i nomi di animali domestici, della squadra del cuore o di membri della famiglia).

-   Non utilizzare parole di uso comune.

-   Imporre la scelta di password che richiedono la digitazione sulla tastiera con entrambe le mani.

-   Imporre l'utilizzo di lettere maiuscole e minuscole, numeri e simboli in tutte le password.

-   Imporre l'utilizzo di spazi e di caratteri che possono essere inseriti solo premendo il tasto ALT.

Le linee guida appena menzionate dovrebbero essere adottate anche per tutte le password degli account di servizio dell'organizzazione.

#### Impostazioni del Criterio password

Nella tabella seguente sono inclusi i consigli per l'impostazione del Criterio password per i tre tipi di ambienti definiti in questa guida. È possibile configurare il Criterio password nella seguente posizione nell'Editor criteri di gruppo:

**Computer Configuration\\Windows Settings\\Security Settings\\Account Policies\\Password Policy**

Nelle sottosezioni che seguono la tabella sono contenute ulteriori informazioni sulle varie impostazioni.

**Tabella 3.1 Consigli sull'impostazione del Criterio password**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Impostazione</p></th>
<th><p>Legacy Client</p></th>
<th><p>Enterprise Client</p></th>
<th><p>Specialized Security – Limited Functionality</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Imponi cronologia delle password</p></td>
<td style="border:1px solid black;"><p>24 password memorizzate</p></td>
<td style="border:1px solid black;"><p>24 password memorizzate</p></td>
<td style="border:1px solid black;"><p>24 password memorizzate</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Validità massima password</p></td>
<td style="border:1px solid black;"><p>42 giorni</p></td>
<td style="border:1px solid black;"><p>42 giorni</p></td>
<td style="border:1px solid black;"><p>42 giorni</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Validità minima password</p></td>
<td style="border:1px solid black;"><p>1 giorno</p></td>
<td style="border:1px solid black;"><p>1 giorno</p></td>
<td style="border:1px solid black;"><p>1 giorno</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Lunghezza minima password</p></td>
<td style="border:1px solid black;"><p>8 caratteri</p></td>
<td style="border:1px solid black;"><p>8 caratteri</p></td>
<td style="border:1px solid black;"><p>12 caratteri</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Le password devono essere conformi ai requisiti di complessità</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Abilitato</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Archivia password mediante crittografia reversibile</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
</tbody>  
</table>
  
##### Imponi cronologia delle password
  
Questa impostazione del criterio determina il numero di nuove password univoche da associare a un account utente prima che sia possibile riutilizzare una vecchia password. Il valore deve essere compreso tra 0 e 24 password.
  
Il valore predefinito per l'impostazione **Imponi cronologia delle password** in Windows Server 2003 con SP1 è il massimo, vale a dire 24 password. Microsoft consiglia questo valore per tutti e tre gli ambienti dato che aiuta ad assicurare che le vecchie password non siano continuamente riutilizzate. Il riutilizzo di password causa una vulnerabilità inerente e se questo valore è impostato su di un valore basso, consente agli utenti di riciclare continuamente e ripetutamente un numero esiguo di password. Non esistono inoltre problemi noti correlati a questo consiglio per ambienti in cui sono presenti Legacy Client.
  
Per migliorare l'efficacia di questa impostazione del criterio, è possibile configurare l'impostazione **Validità minima password** in modo che le password non possano essere modificate immediatamente. Questa combinazione rende estremamente difficile riutilizzare le password, accidentalmente o intenzionalmente.
  
##### Validità massima password
  
Questa impostazione definisce il periodo durante il quale un pirata informatico che ha violato una password può utilizzarla per accedere a un computer di rete prima della relativa scadenza. L'intervallo di valori per questa impostazione va da 1 a 999 giorni. È possibile configurare l'impostazione **Validità massima password** per indicare la scadenza delle password in base alle esigenze specifiche dell'ambiente. Il valore predefinito per questa impostazione è 42 giorni.
  
La costante modifica delle password consente di prevenire che le password siano compromesse. La maggior parte delle password può essere violata se un pirata informatico dispone del tempo e della capacità di elaborazione necessari. Pertanto, tanto maggiore è la frequenza con cui la password viene modificata, tanto più ridotto sarà il periodo di tempo a disposizione di un pirata informatico per violarla. Tuttavia quanto più basso è il valore impostato, tanto maggiore potrà essere il numero di chiamate al supporto helpdesk.
  
Microsoft consiglia di lasciare l'impostazione **Validità massima password** sul valore predefinito di 42 giorni per tutti e tre gli ambienti definiti in questa guida. Questa configurazione garantisce che le password siano modificate periodicamente, ma non richiede che gli utenti le modifichino così spesso da non riuscire a ricordare quali sono. Per riuscire a stabilire un compromesso tra le esigenze di utilizzabilità e protezione, è possibile aumentare il valore per questa impostazione negli ambienti di Legacy Client e di Enterprise Client.
  
##### Validità minima password
  
L'impostazione del criterio determina il numero di giorni in cui una password deve essere utilizzata prima che un utente possa modificarla. L'intervallo di valori per l'impostazione di **Validità minima password** è tra 0 e 999 giorni; un valore 0 consente la modifica immediata della password. Il valore predefinito per l'impostazione è 1 giorno.
  
Il valore dell'impostazione **Validità minima password** deve essere inferiore a quello **Validità massima password**, a meno che l'opzione **Validità massima password** non sia configurata su **0** (il che significa che la password non ha scadenza). Se si desidera che l'impostazione **Imponi cronologia delle password** sia efficace, impostare un valore superiore a 0 per **Validità minima password**. Se non si specifica una validità minima delle password, gli utenti potranno usare ripetutamente le password in ciclo fino a quando non potranno riutilizzare una vecchia password preferita.
  
Microsoft consiglia di lasciare il valore predefinito di 1 giorno per **Validità minima password** per tutti e tre gli ambienti definiti in questa guida. Se questa impostazione è utilizzata unitamente a un valore altrettanto basso nell'impostazione **Imponi cronologia delle password**, gli utenti possono riciclare ripetutamente le medesime password. Per esempio, se l'impostazione **Validità minima password** è configurata su 1 giorno e l'impostazione **Imponi cronologia della password** è configurata su 2, gli utenti dovranno attendere solo 2 giorni prima di poter riutilizzare una vecchia password preferita. Se però l'impostazione **Validità minima password** è configurata su 1 giorno e l'impostazione **Imponi cronologia della password** su 24, gli utenti dovranno modificare la password ogni giorno per almeno 24 giorni prima di poter riutilizzare una password, fatto a quel punto improbabile.
  
##### Lunghezza minima password
  
Questa impostazione del criterio assicura che le password abbiano almeno un determinato numero di caratteri. Le password lunghe, costituite da otto o più caratteri, sono generalmente più sicure di quelle brevi. Quando si utilizza l'impostazione **Lunghezza minima password,** gli utenti non possono utilizzare password vuote e devono creare password costituite da un determinato numero di caratteri. Il valore predefinito per questa impostazione è sette caratteri.
  
Questa guida consiglia di configurare l'impostazione **Lunghezza minima password** su otto caratteri per gli ambienti Legacy Client e Enterprise Client. Questa configurazione è abbastanza lunga da assicurare una protezione adeguata e tuttavia sufficientemente corta da consentire agli utenti di ricordarla facilmente. Questa impostazione garantisce inoltre un elevato livello di difesa dagli attacchi al dizionario e di tipo "brute force".
  
(Gli attacchi al dizionario utilizzano elenchi di parole per decifrare una password basandosi sul metodo per tentativi ed errori. Gli attacchi di tipo "brute force" tentano ogni password possibile o ogni valore di testo codificato. L'efficacia di un attacco di tipo "brute force" dipende dalla lunghezza della password, dalle dimensioni del set di caratteri potenziale e dalla capacità di elaborazione a disposizione del pirata informatico.)
  
Questa guida consiglia di configurare la **Lunghezza minima password** su 12 caratteri per l'ambiente Specialized Security – Limited Functionality.
  
Ogni carattere aggiuntivo di una password ne aumenta la complessità in modo esponenziale. Ad esempio, una password di 7 cifre prevede un numero di combinazioni possibili pari a 267, o 1 x 107. Una password costituita da sette caratteri alfabetici con distinzione tra maiuscole e minuscole prevede un numero di combinazioni pari a 527. Una password alfanumerica di sette caratteri con distinzione tra maiuscole e minuscole e senza punteggiatura prevede un numero di combinazioni pari a 627. A una frequenza ipotetica di 1.000.000 tentativi di attacco al secondo, verrebbe violata in 40 giorni. Una password di otto caratteri prevede un numero di combinazioni possibili pari a 268, o 2 x 1011. Anche se il numero di combinazioni sembra particolarmente grande, a una frequenza di 1.000.000 di tentativi di attacco al secondo (capacità di cui sono dotate molte utilità per la violazione delle password), sarebbero sufficienti solo 59 ore per provare tutte le password possibili. Questi tempi aumentano significativamente per le password costituite da caratteri ALT e da altri caratteri speciali della tastiera, ad esempio ! o @.
  
Le password vengono archiviate nel database di Gestione account di protezione (SAM) o in Active Directory dopo essere passate in un algoritmo hash unidirezionale (non reversibile). Di conseguenza, l'unico modo per stabilire se si dispone della password corretta consiste nel farla passare nello stesso algoritmo hash unidirezionale e confrontarne i risultati. Negli attacchi al dizionario vengono eseguiti interi dizionari nel processo di crittografia per ricercare corrispondenze. Questo tipo di approccio, sebbene alquanto semplicistico, è molto efficace per individuare casi in cui siano state utilizzate parole comuni come "password" o "guest" per le password di account.
  
Le versioni meno recenti di Windows utilizzavano un tipo specifico di algoritmo di crittografia, noto come hash, quale l'hash di LAN Manager (LMHash). Questo algoritmo suddivide la password in blocchi di sette o meno caratteri e calcola poi un valore hash separato per ogni blocco. Anche se Windows 2000 Server, Windows XP e Windows Server 2003 utilizzano tutti un algoritmo di crittografia più nuovo, possono tuttavia calcolare e archiviare l'hash LM per la compatibilità con le versioni precedenti.
  
Quando vi sono dei valori hash LM, essi possono offrire una scorciatoia ai pirati informatici. Se una password è costituita da un massimo di sette caratteri, la seconda metà dell'hash LM viene risolta in un valore specifico in base al quale un pirata informatico può desumere che la password include meno di otto caratteri. Password con almeno otto caratteri consentono di rafforzare persino il più vulnerabile hash LM, in quanto le password più lunghe richiedono ai pirati informatici la crittografia di due parti per ogni password anziché di una sola. È possibile attaccare entrambe le metà di un hash LM in parallelo e, se la seconda metà dell'hash LM è soltanto di un carattere, soccomberà a un attacco di tipo "brute force" in pochi millisecondi. Di conseguenza, non offre alcun vantaggio a meno che non faccia parte del set di caratteri ALT.
  
Per questi motivi, non si consiglia di utilizzare password più corte al posto di quelle più lunghe. La richiesta di password di lunghezza minima che sono troppo lunghe può però generare un numero elevato di password digitate in modo non corretto, causando un aumento degli account bloccati e delle conseguenti chiamate al supporto helpdesk. Inoltre, la richiesta di password estremamente lunghe può ridurre effettivamente la protezione di un'organizzazione, in quanto è più probabile che gli utenti annotino su carta le relative password per non dimenticarle.
  
##### Le password devono essere conformi ai requisiti di complessità
  
Questa impostazione del criterio controlla tutte le nuove password quando sono create per accertarsi che siano conformi ai requisiti di complessità. Le regole dei criteri di Windows Server 2003 non possono essere modificate direttamente. Tuttavia è possibile creare una nuova versione del file Passfilt.dll per applicare un insieme di regole diverso. Per ulteriori informazioni sulla creazione di Passfilt.dll personalizzato, consultare l'articolo MSDN "[Sample Password Filter](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/secmgmt/security/sample_password_filter.asp)" all'indirizzo http://msdn.microsoft.com/library/default.asp?url=/library/en-us/secmgmt/  
security/sample\_password\_filter.asp.
  
È possibile definire un insieme di 20 o più caratteri in modo che possa essere memorizzato facilmente dagli utenti e garantisca un livello di protezione più elevato rispetto a una password di otto caratteri. Considerare la seguente password di 27 caratteri: **Mi sveglio sempre alle 7.30.** Questo tipo di password, in realtà costituita da una frase, può essere ricordata più facilmente di una password più breve del tipo **P@55w0rd**.
  
Quando viene abbinata a una **Lunghezza minima password** di 8 caratteri, questa impostazione rende più difficile sferrare un attacco di tipo "brute force". Se si includono lettere maiuscole, lettere minuscole e numeri, il numero di caratteri disponibili aumenta da 26 a 62. Una password di otto caratteri prevede quindi un numero di combinazioni possibili pari a 2,18 x 1014. A una frequenza di 1.000.000 tentativi al secondo, sarebbero necessari quasi 7 anni per provare tutte le combinazioni possibili.
  
Per queste ragioni, Microsoft consiglia che l'impostazione **Le password devono essere conformi ai requisiti di complessità** sia configurata come **Abilitata** per tutti e tre gli ambienti definiti in questa guida.
  
##### Archivia password mediante crittografia reversibile
  
Questa impostazione del criterio determina se il sistema operativo utilizza la crittografia reversibile per archiviare le password. Essa supporta le applicazioni che usano protocolli che richiedono delle password utente ai fini dell'autenticazione.
  
Le password archiviate con un metodo di crittografia reversibile possono essere captate più facilmente di quelle archiviate con crittografia non reversibile. Se questa impostazione è abilitata, la vulnerabilità aumenta.
  
Per questa ragione, Microsoft consiglia di configurare l'impostazione **Archivia password mediante crittografia reversibile** come **Disabilitata**, a meno che i requisiti dell'applicazione abbiano la priorità sulla protezione delle informazioni della password. Inoltre, gli ambienti che implementano il protocollo CHAP (Challenge – Handshake Authentication Protocol) tramite accesso remoto o servizio IAS e gli ambienti che usano l'autenticazione delle password in formato digest per i servizi IIS (Internet Information Services) richiedono l'abilitazione dell'impostazione di questo criterio.
  
#### Come impedire agli utenti di modificare una password tranne quando necessario
  
Anche se le impostazioni di Criterio password descritte nella sezione precedente forniscono tutta una serie di opzioni, alcune organizzazioni richiedono il controllo centralizzato su tutti gli utenti. Questa sezione descrive come evitare le modifiche di password da parte degli utenti, salvo nel caso in cui tali modifiche siano richieste.
  
Il controllo centralizzato delle password degli utenti è un elemento fondamentale di un sistema efficiente per la protezione di Windows Server 2003. È possibile utilizzare il Criterio di gruppo per regolare la validità minima e massima della password come discusso in precedenza; tenere tuttavia presente che la richiesta di modificare spesso la password può consentire agli utenti di ignorare l'impostazione relativa alla cronologia delle password nel proprio ambiente. I requisiti per le password troppo lunghe possono determinare inoltre un aumento del numero di chiamate all'helpdesk da parte degli utenti che hanno dimenticato le password.
  
Gli utenti possono modificare le relative password nel periodo compreso tra le impostazioni di validità minima e massima della password. La progettazione dell'ambiente Specialized Security – Limited Functionality richiede tuttavia che gli utenti modifichino le password solo quando il sistema operativo lo richiede, dopo che le password hanno raggiunto la **Validità massima password** di 42 giorni. Per impedire agli utenti di modificare le password (salvo in caso di richiesta), è possibile disabilitare l'opzione **Cambia password** nella finestra di dialogo **Protezione di Windows** visualizzata premendo CTRL+ALT+CANC. Gli utenti che ritengono molto importante la protezione potrebbero voler modificare più spesso le loro password e, per farlo, dovranno contattare un amministratore, facendo così aumentare i costi di assistenza.
  
È possibile implementare questa configurazione per un intero dominio utilizzando i criteri di gruppo oppure implementarla per uno o più utenti specifici, modificando il Registro di sistema. Per istruzioni più dettagliate su questa configurazione, consultare l'articolo della Microsoft Knowledge Base "[Come impedire agli utenti di modificare una password tranne quando necessario](http://support.microsoft.com/kb/324744/it)" all'indirizzo http://support.microsoft.com/kb/324744/it.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Criterio di blocco account
  
Il Criterio di blocco account è una funzionalità di protezione di Windows Server 2003 con SP1 che consente di bloccare un account utente dopo un determinato numero di tentativi di accesso non riusciti in un periodo specifico. Il numero di tentativi consentiti e il periodo di tempo sono basati sui valori configurati per quel criterio. Windows Server 2003 con SP1 registra i tentativi di accesso e il software del server può essere configurato in modo tale da disabilitare gli account dopo un numero preimpostato di tentativi di accesso non riusciti, quale risposta a potenziali attacchi.
  
Queste impostazioni dei criteri consentono di proteggere le password utente dai pirati informatici che tentano di identificarle e di ridurre il rischio di attacchi riusciti all'ambiente di rete. L'abilitazione dei criteri di blocco degli account farà probabilmente aumentare i costi di supporto, dato che gli utenti che dimenticano o digitano erroneamente le proprie password avranno ripetutamente bisogno di assistenza. Prima di abilitare le seguenti impostazioni, accertarsi che l'organizzazione sia disposta a far fronte a questi costi aggiuntivi. Per molte organizzazioni, una soluzione migliore e meno costosa consiste nel controllare automaticamente i registri eventi protezione per i controller di dominio e generare avvisi amministrativi se si verifica un tentativo apparente di scoprire le password degli account utente. Vedere il Capitolo 2, "Criteri a livello di dominio" della guida correlata, [*Pericoli e contromisure: Impostazioni di protezione in Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), per ulteriori informazioni su queste impostazioni e sulla loro interazione.
  
#### Impostazioni dei Criteri di blocco account
  
La seguente tabella riassume le impostazioni del Criterio di blocco account consigliate. Si può utilizzare l'Editor oggetti Criteri di gruppo per configurare queste impostazioni nei Criteri di gruppo di dominio al percorso seguente:
  
**Computer Configuration\\Windows Settings\\Security Settings\\Account Policies\\Account Lockout Policy**
  
Nelle sottosezioni che seguono la tabella sono contenute ulteriori informazioni sulle varie impostazioni.
  
**Tabella 3.2 Impostazioni dei Criteri di blocco account**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="25%" />  
<col width="25%" />  
<col width="25%" />  
<col width="25%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Impostazione</p></th>  
<th><p>Legacy Client</p></th>  
<th><p>Enterprise Client</p></th>  
<th><p>Specialized Security – Limited Functionality</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Blocca account per</p></td>
<td style="border:1px solid black;"><p>30 minuti</p></td>
<td style="border:1px solid black;"><p>30 minuti</p></td>
<td style="border:1px solid black;"><p>15 minuti</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Limite di blocchi dell'account</p></td>
<td style="border:1px solid black;"><p>50 tentativi di accesso non validi</p></td>
<td style="border:1px solid black;"><p>50 tentativi di accesso non validi</p></td>
<td style="border:1px solid black;"><p>10 tentativi di accesso non validi</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Reimposta blocco account dopo</p></td>
<td style="border:1px solid black;"><p>30 minuti</p></td>
<td style="border:1px solid black;"><p>30 minuti</p></td>
<td style="border:1px solid black;"><p>15 minuti</p></td>
</tr>  
</tbody>  
</table>
  
##### Blocca account per
  
Questa impostazione del criterio determina l'intervallo di tempo che deve trascorrere prima che venga sbloccato un account e un utente possa eseguire nuovamente un tentativo di accesso. Tramite questa impostazione è possibile specificare il numero di minuti in cui un account bloccato rimarrà non disponibile. Se l'opzione **Blocca account per** è impostata su 0, gli account rimarranno bloccati fino a quando un amministratore li sblocca. Il valore predefinito di Windows Server 2003 per questa impostazione del criterio è **Non definito**.
  
Sebbene possa sembrare conveniente configurare l'impostazione dell'opzione **Blocca account per** in modo che gli account non vengano mai sbloccati automaticamente, tale configurazione potrebbe determinare un aumento del numero di chiamate ricevute dall'helpdesk dell'organizzazione per lo sblocco di account bloccati accidentalmente.
  
Questa guida consiglia di configurare l'impostazione **Blocca account per** su **30 minuti** per gli ambienti Legacy Client e Enterprise Client e su **15 minuti** per gli ambienti Specialized Security - Limited Functionality. Questa configurazione consente di ridurre il sovraccarico durante un attacco di tipo DoS (Denial of Service). In un attacco DoS, il pirata informatico esegue intenzionalmente alcuni tentativi di accesso non riusciti per tutti gli utenti dell'organizzazione, bloccandone gli account. Le impostazioni consigliate consentono agli utenti bloccati di accedere nuovamente, in un intervallo di tempo accettabile, senza dover ricorrere all'assistenza dell'helpdesk. Le informazioni relative ai valori di queste impostazioni devono però essere comunicate agli utenti.
  
##### Limite di blocchi dell'account
  
Questa impostazione del criterio determina il numero di tentativi consentiti all'utente per accedere a un account prima che venga bloccato.
  
Gli utenti autorizzati possono bloccare direttamente i loro account in modi diversi e cioè digitando la password in modo non corretto o modificandola in un computer diverso da quello in cui hanno eseguito l'accesso. Il computer in cui viene digitata la password non corretta potrebbe cercare continuamente di autenticare l'utente e, dato che la password utilizzata per l'autenticazione non è valida, l'account utente verrà infine bloccato. Per evitare il blocco di utenti autorizzati, configurare l'impostazione **Limite di blocchi dell'account** su un numero più alto.
  
Poiché possono esistere pericoli sia quando l'impostazione **Limite di blocchi dell'account** è configurata sia quando non lo è, vengono definite contromisure distinte per ognuno dei due casi. È consigliabile valutare la scelta tra i due tipi di contromisure in base ai pericoli identificati e ai rischi da ridurre nella propria organizzazione.
  
-   Per impedire il blocco degli account, configurare il valore dell'impostazione **Limite di blocchi dell'account** su 0. Questa configurazione ridurrà inoltre le chiamate all'helpdesk in quanto gli utenti non possono bloccare accidentalmente i propri account. Inoltre, gli attacchi DoS che cercano intenzionalmente di bloccare gli account nell'organizzazione non riusciranno. Poiché questa impostazione non impedirà un attacco di tipo "brute force", è consigliabile configurarla solo se vengono soddisfatti esplicitamente entrambi i criteri seguenti:
  
    -   Il criterio password impone che tutti gli utenti dispongano di password complesse costituite da otto o più caratteri.
  
    -   È disponibile un meccanismo di controllo affidabile per avvisare gli amministratori quando nell'ambiente si verifica una serie di tentativi di accesso non riusciti. Ad esempio, il meccanismo di controllo deve monitorare l'evento di protezione 539, corrispondente a un "Errore di accesso. L'account è stato bloccato al momento del tentativo di accesso". Questo evento indica che l'account è stato bloccato durante il tentativo di accesso. Tuttavia questo evento non riguarda i tentativi di immissione della password non riusciti, bensì solo il blocco dell'account. Di conseguenza, gli amministratori devono monitorare anche i tentativi di utilizzo di password non valide.
  
-   Se non è possibile soddisfare i criteri sopra indicati, la seconda alternativa disponibile consiste nel configurare l'impostazione **Limite di blocchi dell'account** su un valore abbastanza elevato per consentire agli utenti di digitare accidentalmente la password in modo non corretto più volte senza bloccare direttamente i relativi account. Tale valore dovrebbe aiutare ad assicurare che un eventuale attacco "brute force" continui però a bloccare l'account.
  
Questa guida consiglia di configurare il valore dell'impostazione **Limite di blocchi dell'account** su **50** per gli ambienti Legacy Client e Enterprise Client, che dovrebbe fornire la protezione adeguata e un'utilizzabilità accettabile. Questo valore impedirà blocchi di account accidentali e ridurrà le chiamate all'helpdesk ma, come descritto sopra, non impedirà un tipo di attacco DoS. Questa guida consiglia però di configurare questo valore di impostazione del criterio su **10** per gli ambienti Specialized Security - Limited Functionality.
  
##### Reimposta blocco account dopo
  
Questa impostazione del criterio determina l'intervallo di tempo che deve trascorrere prima che l'impostazione **Limite di blocco dell'account** venga reimpostata su 0 e l'account venga sbloccato. Se viene definito un valore per **Limite di blocco dell'account**, il tempo di ripristino specificato deve essere inferiore o uguale al valore dell'impostazione **Blocca account per**.
  
L'impostazione **Reimposta blocco account dopo** funziona unitamente alle altre impostazioni. Se si lascia il valore predefinito di questa impostazione del criterio o si configura il relativo valore su un intervallo troppo lungo, l'ambiente potrebbe essere esposto a un attacco di tipo DoS (Denial of Service). Se non viene specificato alcun criterio per reimpostare il blocco dell'account, gli amministratori dovranno sbloccare manualmente tutti gli account. Al contrario, se viene configurato un intervallo di tempo ragionevole per questa impostazione, gli utenti rimarranno bloccati per il periodo impostato fino a quando tutti gli account non verranno sbloccati automaticamente.
  
Questa guida consiglia di configurare l'impostazione **Reimposta blocco account dopo** su 30 minuti per gli ambienti Legacy Client e Enterprise Client. Questa configurazione definisce un intervallo ragionevole che gli utenti accetteranno più facilmente senza che debbano ricorrere all'helpdesk. Questa guida consiglia però di configurare questa impostazione del criterio su 15 per gli ambienti Specialized Security – Limited Functionality.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Criteri Kerberos
  
I criteri Kerberos vengono utilizzati per gli account utente del dominio Questi criteri determinano le impostazioni relative al protocollo Kerberos versione 5, quali la durata del ticket e l'imposizione. I criteri Kerberos non sono disponibili nei criteri del computer locale. Se si riduce la durata dei ticket Kerberos, diminuisce il rischio che un pirata informatico si appropri di una password e la utilizzi per rappresentare un account utente valido. Tuttavia, il bisogno di gestire questi criteri incrementa il sovraccarico legato all'autorizzazione.
  
Nella maggior parte degli ambienti, è consigliabile non modificare i valori predefiniti di questi criteri. Dato che le impostazioni Kerberos sono incluse nel Criterio dominio predefinito e imposte qui, non verranno inserite nei modelli di protezione allegati a questa guida.
  
Questa guida consiglia di non apportare alcuna modifica ai criteri Kerberos predefiniti. Per ulteriori informazioni sulle impostazioni predefinite, consultare la guida correlata, [*Pericoli e contromisure: Impostazioni di Protezione in Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), disponibile all'indirizzo http://www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Opzioni di protezione
  
I tre diversi tipi di criteri di account trattati precedentemente in questo capitolo sono definiti a livello di dominio e imposti da tutti i controller di dominio nel dominio stesso. Un controller di dominio ottiene il criterio di account sempre dall'oggetto Criteri di gruppo Criterio dominio predefinito, anche se esiste un criterio di account diverso applicato all'unità organizzativa che contiene il controller di dominio.
  
Esistono tre impostazioni di opzioni di protezione simili ai criteri di account. Queste applicazioni devono essere applicate a livello dell'intero dominio e non all'interno di OU individuali. È possibile configurare queste impostazioni nell'Editor oggetti Criteri di gruppo alla seguente posizione:
  
**Configurazione del computer\\Impostazioni di Windows\\Impostazioni di protezione\\Criteri locali\\Opzioni di protezione**
  
#### Impostazioni delle opzioni di protezione
  
La seguente tabella riassume le impostazioni delle opzioni di protezione consigliate. Nelle sottosezioni che seguono la tabella sono contenute ulteriori informazioni sulle varie impostazioni.
  
**Tabella 3.3 Impostazioni delle opzioni di protezione**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="25%" />  
<col width="25%" />  
<col width="25%" />  
<col width="25%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Impostazione</p></th>  
<th><p>Legacy Client</p></th>  
<th><p>Enterprise Client</p></th>  
<th><p>Specialized Security – Limited Functionality</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Accesso di rete: consenti la conversione SID/NOME anonima</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
<td style="border:1px solid black;"><p>Disabilitato</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Protezione di rete: impone la disconnessione al termine dell'orario di accesso</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
<td style="border:1px solid black;"><p>Attivato</p></td>
</tr>  
</tbody>  
</table>
  
##### Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso
  
L'impostazione di questo criterio determina se scollegare gli utenti connessi a un computer locale al di fuori dell'orario di connessione valido per l'account. Questa impostazione ha effetto sul componente SMB (Service Message Block). Quando questo criterio è abilitato, le sessioni client con il servizio SMB vengono disconnesse forzatamente al termine dell'orario di accesso del client. Se questo criterio è disabilitato, la sessione client stabilita può continuare dopo il termine dell'orario di accesso del client. Se si abilita questa impostazione del criterio, è consigliabile abilitare anche l'impostazione **Protezione di rete: impone la disconnessione al termine dell'orario di accesso**.
  
Se nell'organizzazione è stato configurato l'orario di accesso per gli utenti, è consigliabile abilitare l'impostazione **Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso**. In caso contrario, gli utenti privi dei diritti di accesso alle risorse di rete al di fuori dell'orario di accesso, potrebbero continuare effettivamente a utilizzare tali risorse tramite le sessioni stabilite durante l'orario di accesso.
  
Questa guida consiglia di configurare l'impostazione **Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso** su **Abilitato** per i tre ambienti definiti nella guida. Se nell'organizzazione non viene utilizzato l'orario di accesso, questa impostazione del criterio non avrà alcun effetto.
  
##### Accesso di rete: consenti la conversione SID/NOME anonima
  
Questa impostazione del criterio determina se un utente anonimo può richiedere il SID di un altro utente.
  
Se l'impostazione **Accesso di rete: consenti conversione anonima SID/NOME** è abilitata in un controller di dominio, un utente a conoscenza degli attributi SID standard e noti di un amministratore potrebbe contattare un computer in cui è abilitato lo stesso criterio e utilizzare il SID per ottenere il nome dell'amministratore. Tale persona potrebbe quindi utilizzare il nome dell'account per avviare un attacco di determinazione della password.
  
Dato che la configurazione predefinita per l'impostazione **Accesso di rete: consenti conversione anonima SID/NOME** è impostata su **Disabilitato** sui computer membro, questi non saranno interessati da questa impostazione del criterio. L'impostazione predefinita per i controller di dominio è **Abilitato**. Se questa impostazione viene disabilitata, i computer che utilizzano i sistemi operativi più vecchi potrebbero non essere in grado di comunicare con domini basati su Windows Server 2003 con SP1. Alcuni esempi di tali computer sono:
  
-   Server con Servizio di Accesso remoto basati su Microsoft Windows NT 4.0.
  
-   Microsoft SQL Servers eseguito sui computer basati su Windows NT 3.x o Windows NT 4.0.
  
-   I server del Servizio di Accesso remoto in computer basati su Windows 2000 che si trovano nei domini di Windows NT 3.x o di Windows NT 4.0.
  
Questa guida consiglia di configurare l'impostazione **Accesso di rete: consenti conversione anonima SID/NOME** su **Disabilitato** per i tre ambienti definiti nella guida.
  
##### Protezione di rete: impone la disconnessione al termine dell'orario di accesso
  
L'impostazione di questo criterio determina se scollegare gli utenti connessi a un computer locale al di fuori dell'orario di connessione valido per l'account. Questa impostazione influisce sul componente SMB.
  
Se si abilita l'impostazione **Protezione di rete: impone la disconnessione al termine dell'orario di accesso,** le sessioni client con il server SMB vengono disconnesse forzatamente al termine dell'orario di accesso dell'utente. L'utente non sarà in grado di accedere al computer fino all'inizio del successivo orario di accesso pianificato. Se questa impostazione viene disabilitata, gli utenti potranno mantenere una sessione client stabilita anche dopo la scadenza dell'orario di connessione. Per gli account di dominio, è necessario definire questa impostazione nel Criterio dominio predefinito.
  
Questa guida consiglia di configurare l'impostazione **Protezione di rete: impone la disconnessione al termine dell'orario di accesso** su **Abilitato** per i tre ambienti definiti nella guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questo capitolo si è occupato del bisogno di rivedere tutte le impostazioni di dominio nell'organizzazione. Per ogni dominio può essere configurata una sola serie di criteri password, di blocco dell'account e del protocollo di autenticazione Kerberos versione 5. Altre impostazioni relative alla password e al blocco degli account avranno effetto solo su account locali dei server membro. Pianificare la configurazione di impostazioni che verranno applicate a tutti i server membro del dominio e verificare che tali impostazioni consentano di garantire un livello di protezione adeguato per l'organizzazione.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono informazioni aggiuntive relative ai criteri di dominio per i server con Windows Server 2003 con SP1.
  
-   Per le informazioni sulla capacità degli utenti anonimi di richiedere attributi identificatore di protezione per un altro utente, vedere [Accesso di rete: consenti conversione anonima SID/NOME](http://technet.microsoft.com/en-us/library/cc728431.aspx) all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/library/ServerHelp/  
    299803be-0e85-4c60-b0b5-1b64486559b3.mspx.
  
-   Per informazioni sulla protezione di rete e su come imporre la disconnessione al termine dell'orario di accesso, vedere “[The Mole \#32: Technical Answers from Inside Microsoft](http://technet.microsoft.com/en-us/library/dd316464.aspx)” all'indirizzo www.microsoft.com/technet/archive/community/columns/inside/techan32.msp.
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)
