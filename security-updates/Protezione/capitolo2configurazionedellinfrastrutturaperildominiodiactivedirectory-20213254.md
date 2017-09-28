---
TOCTitle: 'Capitolo 2: Configurazione dell''infrastruttura per il dominio di Active Directory'
Title: 'Capitolo 2: Configurazione dell''infrastruttura per il dominio di Active Directory'
ms:assetid: '620c0004-41a8-4d13-9a61-e6d879f9cc65'
ms:contentKeyID: 20213254
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163071(v=TechNet.10)'
---

Guida per la protezione di Windows XP
=====================================

### Capitolo 2: Configurazione dell'infrastruttura per il dominio di Active Directory

##### In questa pagina

[](#elaa)[Panoramica](#elaa)
[](#ekaa)[Progettazione della OU per supportare la gestione della protezione](#ekaa)
[](#ejaa)[Progettazione dell'oggetto Criteri di gruppo per supportare la gestione della protezione](#ejaa)
[](#eiaa)[Criteri di gruppo a livello di dominio](#eiaa)
[](#ehaa)[Impostazioni di Criterio password](#ehaa)
[](#egaa)[Impostazioni Criterio di blocco account](#egaa)
[](#efaa)[Impostazioni di Assegnazione diritti utente](#efaa)
[](#eeaa)[Impostazioni di Opzioni di protezione](#eeaa)
[](#edaa)[Criterio Kerberos](#edaa)
[](#ecaa)[Criteri di gruppo a livello di OU](#ecaa)
[](#ebaa)[Strumenti relativi ai criteri di gruppo](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

I criteri di gruppo sono una funzionalità del servizio directory Active Directory che facilita la gestione delle modifiche e delle configurazioni nei domini di Microsoft Windows Server 2003 e Microsoft Windows 2000 Server. Prima di applicare i criteri di gruppo ai computer client Microsoft Windows XP Professional con Service Pack 2 (SP2) nell'ambiente specifico, è necessario tuttavia eseguire alcune operazioni preliminari nel dominio.

Le impostazioni dei Criteri di gruppo vengono archiviate negli oggetti Criteri di gruppo (GPO) del database Active Directory. Gli oggetti Criteri di gruppo sono collegati ai contenitori, che includono siti di Active Directory, domini e unità organizzative (OU). Poiché i criteri di gruppo sono così strettamente integrati con Active Directory, prima di implementarli è importante acquisire una conoscenza di base della struttura di Active Directory e delle implicazioni relative alla protezione associate alla configurazione delle diverse opzioni di progettazione. Per ulteriori informazioni sulla progettazione di Active Directory, vedere il Capitolo 3, "Criteri di dominio", della *Guida per la protezione di Windows Server 2003*.

I criteri di gruppo rappresentano uno strumento essenziale per la protezione di Windows XP. In questo capitolo viene descritta in dettaglio la procedura di utilizzo dei criteri di gruppo per applicare e mantenere criteri di protezione coerenti in una rete da una posizione centrale.

Nella guida vengono illustrate le opzioni relative sia all'ambiente client di organizzazione (EC) sia all'ambiente protezione specializzata/funzionalità limitata (SSLF). Le impostazioni consigliate in questo capitolo per i computer client desktop e portatili sono le stesse e poiché si tratta di impostazioni particolari, esse vengono applicate a livello della radice di dominio invece che a livello di OU. Ad esempio, i criteri di blocco account e password per i domini di Windows  Server 2003 e Windows 2000 Server devono essere configurati attraverso un GPO collegato alla radice di dominio. I nomi dei file dei modelli di protezione di base per i due ambienti sono:

-   EC-Domain.inf

-   SSLF-Domain.inf

[](#mainsection)[Inizio pagina](#mainsection)

### Progettazione della OU per supportare la gestione della protezione

Un'unità organizzativa (OU) è un contenitore all'interno di un dominio di Active Directory. L'OU può contenere utenti, gruppi, computer e altre unità organizzative note come OU figlio. È possibile collegare un oggetto Criteri di gruppo (GPO) a una OU e le impostazioni di GPO saranno applicate agli utenti e ai computer contenuti nella OU e nelle OU figlio. Per facilitare l'amministrazione, è possibile delegare l'autorità amministrativa a ciascuna OU. Le OU rappresentano un metodo semplice per raggruppare utenti, computer e identità di protezione, nonché uno strumento efficiente per segmentare i confini amministrativi. Microsoft consiglia alle organizzazioni di assegnare utenti e computer a OU separate, in quanto alcune impostazioni vengono applicate solo agli utenti e altre solo ai computer.

È possibile delegare il controllo di un gruppo o di una singola OU tramite la Delega guidata del controllo nello strumento dello snap-in MMC (Microsoft Management Console) Utenti e computer di Active Directory. Per i collegamenti alla documentazione sulla delega dell'autorità, vedere la sezione "Ulteriori informazioni" alla fine di questo capitolo.

Uno degli obiettivi principali nella progettazione della struttura dell'unità organizzativa per qualsiasi ambiente è la costituzione di una base per l'implementazione sicura dei criteri di gruppo estesa a tutte le workstation di Active Directory, assicurando che queste rispondano agli standard di protezione dell'organizzazione. È necessario inoltre progettare la struttura dell'unità organizzativa in modo da fornire impostazioni di protezione adeguate per tipi specifici di utenti all'interno di un'organizzazione. Ad esempio, è possibile consentire agli sviluppatori di eseguire sulle workstation operazioni non permesse agli utenti medi. Per gli utenti di computer portatili, inoltre, potrebbero essere necessari requisiti di protezione leggermente diversi da quelli relativi agli utenti di computer desktop. Nella figura seguente è illustrata una struttura di OU semplice, ma sufficiente per la presentazione dei criteri di gruppo in questo capitolo. La struttura di questa unità organizzativa potrebbe essere diversa dai requisiti organizzativi del proprio ambiente.

![](images/Cc163071.XPSG0201(it-it,TechNet.10).gif)

**Figura 2.1 Una struttura di OU per computer WINDOWS XP**

#### OU di reparto

Poiché i requisiti di protezione all'interno di un'organizzazione variano spesso, potrebbe essere utile creare OU di reparto nell'ambiente. È possibile applicare le impostazioni di protezione del reparto ai computer e agli utenti nelle rispettive OU di reparto tramite un oggetto Criteri di gruppo.

##### OU protetta per utenti di Windows XP

Questa unità organizzativa contiene gli account per gli utenti negli ambienti EC e SSLF. Le impostazioni applicate a questa unità organizzativa sono descritte nella sezione "Configurazione utente" del Capitolo 4, "Modelli amministrativi per Windows XP".

##### OU per Windows XP

Questa unità organizzativa contiene OU figlio per ogni tipo di computer client Windows XP dell'ambiente. La guida contiene le istruzioni per i computer desktop e portatili. Per questo motivo sono state create una OU per desktop e una OU per portatili.

-   **OU per desktop**: questa unità organizzativa contiene computer desktop che rimangono connessi costantemente alla rete. Le impostazioni applicate a questa unità organizzativa sono illustrate in dettaglio nel Capitolo 3, "Impostazioni di protezione per client Windows XP" e nel Capitolo 4, "Modelli amministrativi per Windows XP".

-   **OU per portatili**: questa unità organizzativa contiene computer portatili per utenti mobili che non sono sempre connessi alla rete. Il Capitolo 3, "Impostazioni di protezione per client Windows XP" e il Capitolo 4, "Modelli amministrativi per Windows XP" forniscono una descrizione dettagliata delle impostazioni applicate a questa OU.

[](#mainsection)[Inizio pagina](#mainsection)

### Progettazione dell'oggetto Criteri di gruppo per supportare la gestione della protezione

Utilizzare i GPO per assicurare che a tutte le workstation o a tutti gli utenti all'interno di un'unità organizzativa vengano applicati impostazioni di criterio, diritti utente e funzionamenti specifici. L'utilizzo dei criteri di gruppo invece della configurazione manuale semplifica l'aggiornamento futuro di alcune workstation o di alcuni utenti con modifiche aggiuntive. La configurazione manuale è inefficiente, perché per ciascun computer client è necessario l'intervento di un tecnico. Inoltre, se le impostazioni di criterio nei GPO basati su domini sono diverse da quelle applicate in locale, le prime sovrascriveranno le seconde.

[![](images/Cc163071.XPSG0202(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163071.xpsg0202_big(it-it,technet.10).gif)

**Figura 2.2 Ordine di applicazione degli oggetti Criteri di gruppo**

Questa figura illustra l'ordine in cui i GPO vengono applicati a un computer membro della OU figlio, dall'ordine inferiore (1) a quello superiore (5). I criteri di gruppo vengono applicati a partire dai criteri locali di ogni workstation Windows XP. Dopo l'applicazione dei criteri locali, tutti gli oggetti Criteri di gruppo vengono applicati a livello di sito e quindi a livello di dominio.

Nel caso di computer client Windows XP nidificati in vari livelli delle unità organizzative, i GPO vengono applicati in ordine dal livello superiore della gerarchia a quello inferiore. Il GPO finale viene applicato dall'unità organizzativa contenente il computer client. Questo ordine di elaborazione dei GPO (criteri locali, sito, dominio, unità organizzativa padre e unità organizzativa figlio) è significativo, in quanto i GPO applicati in seguito nel processo sovrascriveranno quelli applicati in precedenza. I GPO dell'utente sono applicati nello stesso modo.

Le seguenti considerazioni vengono applicate quando si progettano i Criteri di gruppo.

-   Un amministratore deve impostare l'ordine in cui si collegano più oggetti Criteri di gruppo a un'unità organizzativa, altrimenti i criteri verranno applicati per impostazione predefinita nell'ordine in cui sono stati collegati all'unità organizzativa. Se viene configurata la stessa impostazione in più criteri, la priorità viene assegnata al primo criterio elencato per il contenitore.

-   È possibile configurare un GPO con l'opzione **Imposto**. Se si seleziona questa opzione, gli altri GPO non possono sovrascrivere le impostazioni configurate per questo GPO.

    **Nota**: In Windows 2000, l'opzione **Imposto** è denominata **Non sovrascrivere.**

-   È possibile configurare Active Directory, un sito, un dominio o un'unità organizzativa con l'opzione **Blocca l'eredità dei criteri**. Questa opzione blocca le impostazioni dei GPO di livello superiore nella gerarchia di Active Directory, a meno che non sia selezionata l'opzione **Imposto**. In altre parole, l'opzione **Imposto** ha priorità sull'opzione **Blocca l'eredità dei criteri**.

-   Le impostazioni dei criteri di gruppo si applicano a utenti e computer, in base alla posizione dell'oggetto utente o computer in Active Directory. In alcuni casi, gli oggetti utente possono richiedere l'applicazione di criteri in base alla posizione dell'oggetto computer e non alla posizione dell'oggetto utente. La funzionalità di loopback dei criteri di gruppo consente all'amministratore di applicare le impostazioni dei criteri di gruppo in base al computer a cui accede l'utente. Per ulteriori informazioni sul supporto della funzionalità di loopback, vedere il white paper relativo ai criteri di gruppo nella sezione "Ulteriori informazioni" alla fine di questo capitolo.

Nella figura seguente si espande la struttura dell'unità organizzativa preliminare per mostrare le possibili applicazioni dei GPO ai computer client Windows XP appartenenti alla OU per portatili e alla OU per desktop.

[![](images/Cc163071.XPSG0203(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163071.xpsg0203_big(it-it,technet.10).gif)

**Figura 2.3 Espansione della struttura dell'unità organizzativa per computer desktop e portatili basati su Windows XP**

Nell'esempio precedente, i computer portatili sono membri dell'unità organizzativa corrispondente. I primi criteri applicati sono i Criteri di protezione locali nei computer portatili. Poiché in questo esempio è presente un unico sito, nessun GPO viene applicato a livello di sito, lasciando il GPO di dominio come criterio successivo da applicare. Infine, viene applicato l'oggetto Criteri di gruppo per computer portatili.

**Nota**:** **i criteri per computer desktop non vengono applicati ai computer portatili in quanto questi non sono collegati a nessuna unità organizzativa della gerarchia contenente la OU per portatili. Inoltre, la OU protetta per utenti di Windows XP non dispone di un modello di protezione (file .inf) corrispondente, poiché include solo le impostazioni dei modelli amministrativi.

Per dimostrare come viene applicata la priorità, considerare uno scenario di esempio in cui l'impostazione di criterio **Consenti accesso tramite Servizi terminal** relativa all'OU Windows XP sia impostata sul gruppo **Administrators** e l'impostazione **Consenti accesso tramite Servizi terminal** relativa al GPO per computer portatili sia impostata sui gruppi **Power Users** e **Administrators.** In questo esempio, un utente con account incluso nel gruppo **Power Users** può accedere a un portatile tramite Servizi terminal, perché l'OU per portatili è figlio dell'OU Windows XP. Se l'opzione di criterio **Non sovrascrivere** nell'oggetto Criteri di gruppo per Windows XP è abilitata, solo gli utenti con account incluso nel gruppo **Administrators** possono accedere al computer client tramite Servizi terminal.

#### Modelli di protezione

I modelli di protezione sono file di testo che contengono i valori delle impostazioni di protezione e sono sottocomponenti dei GPO. Le impostazioni di criterio contenute nei modelli di protezione possono essere modificate nello snap-in Editor oggetti Criteri di gruppo di MMC e si trovano nella cartella **Configurazione computer\\Impostazioni di Windows\\Impostazioni protezione**. È inoltre possibile modificare questi file con lo snap-in Modelli di protezione di MMC o con un editor di testo come Blocco note. Microsoft consiglia di utilizzare lo snap-in Editor oggetti Criteri di gruppo per gestire le impostazioni di protezione nei modelli di protezione che si trovano nei GPO e lo snap-in Modelli di protezione per gestire le impostazioni di criterio che si trovano in modelli di protezione autonomi.

Alcune sezioni dei file modello contengono elenchi di controllo di accesso (ACL) specifici, definiti in base al linguaggio SDDL (Security Descriptor Definition Language). Per ulteriori informazioni sulla modifica dei modelli di protezione e sul linguaggio SDDL, vedere la sezione "Ulteriori informazioni" alla fine di questo capitolo.

##### Gestione dei modelli di protezione

È importante che i modelli di protezione di un ambiente di produzione vengano archiviati in una posizione sicura dell'infrastruttura. È consigliabile consentire l'accesso ai modelli di protezione solo agli amministratori responsabili dell'implementazione dei criteri di gruppo. Per impostazione predefinita, i modelli di protezione inclusi in Windows XP, Windows 2000 e Windows Server 2003 sono archiviati nella cartella **%SystemRoot%\\security\\templates**. Come descritto nel Capitolo 1, i modelli di protezione inclusi in questa guida vengono copiati nella cartella **\\Windows XP Security Guide Tools and Templates\\Security Templates** quando si esegue il file .msi contenuto nel file di archivio WinZip in cui si trova questa guida. (La versione scaricabile della guida è disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14840). È consigliabile copiare o spostare i modelli di protezione da questa cartella in una nuova posizione sui computer di prova quando si valutano e perfezionano le impostazioni per adattarle ai requisiti aziendali dell'organizzazione. Dopo che la verifica è stata completata, spostare le versioni finali dei modelli di protezione in una posizione centrale, come la posizione predefinita dei modelli di protezione incorporati.

La cartella **%SystemRoot%\\security\\templates** non viene replicata nei controller di dominio. Pertanto sarà necessario selezionare un controller di dominio in cui conservare la copia master dei modelli di protezione in modo che non si verifichino problemi di controllo della versione relativi ai modelli. Questa procedura consigliata assicura che venga modificata sempre la stessa copia dei modelli.

##### Importazione di un modello di protezione

La procedura seguente consente di importare un modello di protezione.

**Per importare un modello di protezione in un oggetto Criteri di gruppo**

1.  Selezionare la cartella **Impostazioni di Windows** nell'Editor oggetti Criteri di gruppo.

2.  Espandere la cartella **Impostazioni di Windows** e selezionare **Impostazioni protezione**.

3.  Fare clic con il pulsante destro del mouse sulla cartella **Impostazioni protezione**, quindi fare clic su **Importa criterio**.

4.  Selezionare il modello di protezione che si desidera importare, quindi fare clic su **Apri**. Le impostazioni del file vengono importate nell'oggetto Criteri di gruppo.

#### Modelli amministrativi

Impostazioni di protezione aggiuntive sono disponibili in file Unicode denominati Modelli amministrativi. Questi file contengono impostazioni del Registro di sistema che influiscono su Windows XP e sui suoi componenti, insieme ad altre applicazioni quale ad esempio Microsoft Office 2003. I modelli amministrativi possono includere sia le impostazioni del computer che le impostazioni dell'utente. Le impostazioni del computer sono archiviate nell'hive del Registro di sistema HKEY\_LOCAL\_MACHINE. Le impostazioni dell'utente sono archiviate nell'hive del Registro di sistema HKEY\_CURRENT\_USER.

##### Gestione dei modelli amministrativi

È importante archiviare in una posizione sicura dell'infrastruttura i modelli amministrativi utilizzati in un ambiente di produzione, esattamente come i modelli di protezione. È consigliabile consentire l'accesso a questa posizione solo agli amministratori responsabili dell'implementazione dei criteri di gruppo. I modelli amministrativi forniti con Windows XP e Windows Server 2003 sono archiviati nella directory **%systemroot%\\inf**. I modelli aggiuntivi per Office 2003 sono inclusi nel *Office 2003 Resource Kit*. È consigliabile non modificare i Modelli amministrativi forniti da Microsoft poiché potrebbero variare con le nuove versioni del Service Pack.

##### Aggiunta di un modello amministrativo ai criteri

Oltre ai modelli amministrativi forniti con Windows XP, è possibile applicare i modelli di Office 2003 agli oggetti Criteri di gruppo in cui si desidera configurare le impostazioni di Office 2003. In alternativa, è possibile creare Modelli amministrativi personalizzati specifici dell'organizzazione. La procedura seguente consente di inserire un modello amministrativo in un GPO.

**Per aggiungere un modello amministrativo a un GPO**

1.  Selezionare la cartella Modelli amministrativi nell'Editor oggetti Criteri di gruppo.

2.  Fare clic con il pulsante destro del mouse sulla cartella **Modelli amministrativi**, quindi fare clic su **Aggiunta/Rimozione modelli**.

3.  Nella finestra di dialogo **Aggiunta/Rimozione modelli**, fare clic su **Aggiungi**.

4.  Selezionare la cartella contenente i file dei modelli amministrativi.

5.  Selezionare il modello che si desidera aggiungere, fare clic su **Apri** e infine su **Chiudi**.

[](#mainsection)[Inizio pagina](#mainsection)

### Criteri di gruppo a livello di dominio

I criteri di gruppo a livello di dominio includono le impostazioni che si applicano a tutti i computer e gli utenti del dominio. Questa guida consiglia di configurare le impostazioni a livello di dominio in un nuovo GPO piuttosto che nel Criterio dominio predefinito incorporato. La ragione per questo suggerimento è che ciò facilita il ripristino delle impostazioni predefinite se le modifiche introdotte da questa guida causano dei problemi. È opportuno ricordare che alcune applicazioni configurano automaticamente il Criterio dominio predefinito e le impostazioni di criterio modificate da tali applicazioni possono essere in conflitto con quelle definite nell'oggetto Criteri di gruppo Criterio dominio descritte in questa guida. Tuttavia, il rischio che ciò si verifichi è limitato, perché solo alcune impostazioni sono configurate a livello di dominio. La protezione a livello di dominio è trattata in dettaglio nel Capitolo 3, "Criteri di Dominio" della [*Guida per la protezione di Windows Server 2003*](http://technet.microsoft.com/it-it/library/cc163140), disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14845.

[](#mainsection)[Inizio pagina](#mainsection)

### Impostazioni di Criterio password

Password complesse modificate regolarmente riducono il rischio di attacco della password. Le impostazioni di criterio password controllano la complessità e la durata della validità delle password e possono essere configurate soltanto dai Criteri di gruppo a livello di dominio. Per informazioni sull'impostazione dei criteri password su computer autonomi direttamente in Gestione account di protezione (SAM, Security Account Manager) locale, vedere il Capitolo 5, "Protezione di client Windows XP autonomi".

In questa sezione viene descritta ogni impostazione del criterio password per gli ambienti EC e SSLF.

È possibile configurare le impostazioni dei criteri password nella seguente posizione nell'Editor oggetti Criteri di gruppo:

**Computer Configuration\\Windows Settings\\Security Settings\\Account Policies\\Password Policy**

Nella tabella seguente sono incluse le raccomandazioni sulle impostazioni dei criteri password per i due tipi di ambienti protetti definiti in questa guida. Per maggiori informazioni su ciascuna impostazione consultare le sottosezioni seguenti.

**Tabella 2.1 Raccomandazioni sulle impostazioni dei criteri password**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazione</th>
<th>Valore predefinito del controller di dominio</th>
<th>EC</th>
<th>SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Imponi cronologia delle password</td>
<td style="border:1px solid black;">24 password</td>
<td style="border:1px solid black;">24 password</td>
<td style="border:1px solid black;">24 password</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Validità massima password</td>
<td style="border:1px solid black;">42 giorni</td>
<td style="border:1px solid black;">90 giorni</td>
<td style="border:1px solid black;">90 giorni</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Validità minima password</td>
<td style="border:1px solid black;">1 giorno</td>
<td style="border:1px solid black;">1 giorno</td>
<td style="border:1px solid black;">1 giorno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Lunghezza minima password</td>
<td style="border:1px solid black;">7 caratteri</td>
<td style="border:1px solid black;">8 caratteri</td>
<td style="border:1px solid black;">12 caratteri</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Le password devono essere conformi ai requisiti di complessità</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Consenti archiviazione password con crittografia reversibile per tutti gli utenti del dominio</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
</tbody>
</table>
  
#### Imponi cronologia delle password
  
Questa impostazione determina il numero delle nuove password univoche da associare a un account utente prima che sia possibile riutilizzare una vecchia password. Il valore di questa impostazione di criterio deve essere compreso tra 0 e 24 password. Il valore predefinito per Windows XP è 0 password, ma l'impostazione predefinita in un dominio è 24 password. Perché questa impostazione di criterio sia efficace, utilizzare l'impostazione **Validità minima password** per evitare che gli utenti modifichino ripetutamente la loro password.
  
Configurare l'impostazione **Imponi cronologia delle password** su **24 password** per i due ambienti di protezione definiti in questa guida.
  
#### Validità massima password
  
I valori per questa impostazione di criterio vanno da 1 a 999 giorni (è inoltre possibile impostare il valore su 0 per specificare che le password non perdono mai la loro validità). Questa impostazione di criterio definisce il periodo di tempo in cui un utente può utilizzare la password prima che scada. Il valore predefinito per questa impostazione di criterio è 42 giorni. La maggior parte delle password può essere violata; pertanto, maggiore è la frequenza con cui la password viene modificata, tanto più ridotta sarà la possibilità che un pirata informatico utilizzi una password violata. Tuttavia quanto più basso è il valore impostato, tanto maggiore è la possibilità di un aumento del numero di chiamate al supporto helpdesk.
  
Configurare l'impostazione **Validità massima password** sul valore **90 giorni** per i due ambienti di protezione definiti in questa guida.
  
#### Validità minima password
  
Questa impostazione di criterio determina il numero di giorni in cui una password deve essere utilizzata prima che l'utente possa modificarla. L'intervallo di valori per questa impostazione di criterio va da 1 a 998 giorni (è inoltre possibile impostare il valore su 0 per consentire modifiche immediate alle password). Il valore predefinito per questa impostazione di criterio è 0 giorni.
  
Il valore per l'impostazione **Validità minima password** deve essere inferiore a quello specificato per l'impostazione **Validità massima password**, a meno che il valore per l'impostazione **Validità massima password** sia configurato su 0 in modo da non specificare alcuna scadenza per le password. Se il valore per l'impostazione **Validità massima password** viene configurato su 0, il valore per questa impostazione di criterio può essere configurato su qualsiasi valore compreso tra 0 e 999.
  
Per attivare l'impostazione **Imponi cronologia delle password**, inserire un valore maggiore di 0. Se l'impostazione **Validità minima password** è 0, gli utenti potranno utilizzare ripetutamente le password in ciclo fino a quando ritroveranno una vecchia password preferita.
  
Configurare l'impostazione **Validità minima password** sul valore 1 giorno per i due ambienti di protezione definiti in questa guida. Questo valore scoraggia l'utilizzo ripetuto della stessa password da parte degli utenti, perché è necessario attendere un intero giorno prima di poterla modificare. Induce inoltre gli utenti a memorizzare le nuove password, perché devono utilizzarle per almeno un giorno prima di poterle reimpostare. Infine, non consente agli utenti di aggirare la restrizione **Imponi cronologia delle password.**
  
#### Lunghezza minima password
  
Questa impostazione di criterio determina il numero minimo di caratteri che costituiscono la password di un account utente. Ci sono molte teorie diverse sulla determinazione della lunghezza della password più adatta per un'organizzazione, ma forse "frase password" è un termine migliore rispetto a "password". In Microsoft Windows 2000 e nelle versioni successive, le frasi password possono essere piuttosto lunghe e possono contenere spazi. Pertanto, una frase del tipo "Vorrei un frullato al latte" è una frase password valida ed è notevolmente più complessa di una stringa costituita da 8 o 10 caratteri con numeri e lettere casuali e al tempo stesso è più semplice da ricordare. Ricordare che gli utenti devono essere informati sulla corretta selezione e conservazione delle password, soprattutto per ciò che riguarda la lunghezza.
  
Nell'ambiente EC, verificare che l'impostazione **Lunghezza minima password** sia configurata sul valore di **8 caratteri**. Questa impostazione di criterio prevede una lunghezza in grado di assicurare una protezione adeguata e tuttavia sufficientemente ridotta da consentire agli utenti di ricordare facilmente la password. Nell'ambiente SSLF, configurare il valore su **12 caratteri**.
  
#### Le password devono essere conformi ai requisiti di complessità
  
Questa impostazione controlla tutte le nuove password per assicurarne la conformità ai requisiti di base per le password complesse. Per impostazione predefinita, il valore per questa impostazione di criterio in Windows XP è configurato su **Disabilitato**, mentre in un dominio di Windows Server 2003 è **Abilitato**.
  
Ogni carattere aggiuntivo di una password ne aumenta la complessità in modo esponenziale. Ad esempio, una password costituita da sette caratteri alfabetici tutti minuscoli avrebbe 26(7) (approssimativamente 8 x 10(9) o 8 miliardi) combinazioni possibili. A una frequenza ipotetica di 1.000.000 di tentativi di attacco al secondo (capacità di cui sono dotate molte utilità per la violazione delle password), verrebbe violata in soli 133 minuti. Una password costituita da sette caratteri alfabetici con distinzione tra maiuscole e minuscole prevede un numero di combinazioni pari a 52(7). Una password alfanumerica di sette caratteri con distinzione tra maiuscole e minuscole e senza punteggiatura prevede un numero di combinazioni pari a 62(7). Una password di otto caratteri prevede un numero di combinazioni possibili pari a 26(8) (o 2 x 10(11)). Sebbene questo potrebbe sembrare un numero incredibilmente elevato, a una frequenza di 1.000.000 di tentativi di attacco al secondo sarebbero sufficienti solo 59 ore per provare tutte le password possibili. Tenere presente che questi tempi aumentano significativamente per le password costituite da caratteri ALT e da altri caratteri speciali della tastiera, ad esempio ! o @.
  
Il corretto utilizzo delle impostazioni password può rendere molto difficile, se non impossibile, eseguire un attacco di tipo "brute force".
  
#### Consenti archiviazione password con crittografia reversibile per tutti gli utenti del dominio
  
Questa impostazione di criterio determina se il sistema operativo memorizza le password utilizzando la crittografia reversibile e fornisce supporto per i protocolli di applicazione che richiedono la conoscenza della password dell'utente a fini di autenticazione. Le password memorizzate con la crittografia reversibile sono essenzialmente uguali a quelle in versione testo semplice. Per questo motivo, è consigliabile non abilitare questa impostazione di criterio a meno che i requisiti dell'applicazione non abbiano la priorità rispetto alla necessità di proteggere le informazioni della password. Il valore predefinito per questa impostazione di criterio è **Disabilitato**.
  
Questa impostazione di criterio è necessaria in caso di utilizzo del protocollo CHAP (Challenge – Handshake Authentication Protocol) tramite accesso remoto o Servizio di autenticazione Internet (IAS, Internet Authentication Service). È necessario inoltre in caso di utilizzo di Autenticazione del digest in Microsoft Internet Information Services (IIS).
  
Assicurarsi che l'impostazione **Consenti archiviazione password con crittografia reversibile per tutti gli utenti del dominio** sia configurata su **Disabilitato**, modalità in cui si trova nell'oggetto Criteri di gruppo di dominio predefinito di Windows Server 2003 e nei criteri di protezione locali delle workstation e dei server. Questa impostazione di criterio è impostata su **Disabilitato** anche nei due ambienti definiti in questa guida.
  
#### Come impedire agli utenti di modificare le password salvo in caso di richiesta
  
Oltre ai criteri password descritti precedentemente in questo capitolo, alcune organizzazioni presentano come requisito il controllo centralizzato di tutti gli utenti. In questa sezione viene descritta la procedura per impedire agli utenti di modificare le password salvo nel caso in cui venga richiesto di eseguire tale operazione.
  
Il controllo centralizzato delle password degli utenti è un elemento fondamentale di un sistema efficiente per la protezione di Windows XP. È possibile utilizzare i criteri di gruppo per impostare la validità minima e massima della password illustrata in precedenza. Tuttavia, i requisiti di frequente modifica della password possono permettere agli utenti di aggirare l'impostazione **Imponi cronologia delle password** dell'ambiente. I requisiti per le password troppo lunghe possono determinare inoltre un aumento del numero di chiamate all'help desk da parte degli utenti che hanno dimenticato le password.
  
Gli utenti possono modificare le relative password nel periodo compreso tra le impostazioni di validità minima e massima della password. La progettazione della protezione per l'ambiente protezione specializzata/funzionalità limitata prevede tuttavia che gli utenti modifichino le password solo quando il sistema operativo lo richiede, dopo che le password hanno raggiunto la validità massima di 42 giorni. Per ottenere questo livello di controllo, gli amministratori possono disattivare il pulsante **Modifica password** nella finestra di dialogo **Protezione Windows** che viene visualizzata premendo CTRL + ALT + CANC.
  
È possibile implementare questa configurazione per un intero dominio utilizzando criteri di gruppo oppure implementarla per uno o più utenti specifici modificando il Registro di sistema. Per informazioni dettagliate su questa configurazione, vedere l'articolo 324744 della Microsoft Knowledge Base, "[HOW TO: Impedire agli utenti di modificare una password tranne quando necessario in Windows Server 2003](http://support.microsoft.com/kb/324744/it)", disponibile all'indirizzo http://support.microsoft.com/kb/324744/it. Se si dispone di un dominio Windows 2000, vedere l'articolo 309799 della Microsoft Knowledge Base, "[Impedire agli utenti di modificare una password tranne quando necessario](http://support.microsoft.com/kb/309799/it)" all'indirizzo http://support.microsoft.com/kb/309799/it.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni Criterio di blocco account
  
Il Criterio di blocco account è una funzionalità di protezione di Active Directory che consente di bloccare un account utente e di impedire l'accesso dopo un determinato numero di tentativi di accesso non riusciti in un periodo specifico. I tentativi di accesso sono registrati dai controller di dominio. Il numero di tentativi consentiti e il periodo di tempo sono basati sui valori configurati per le impostazioni di blocco account. È inoltre possibile specificare la durata del blocco.
  
Queste impostazioni di criterio consentono di impedire ai pirati informatici di determinare le password degli utenti e riducono il rischio di attacchi riusciti nell'ambiente di rete. Tuttavia, un criterio di blocco account abilitato causerà probabilmente un maggior numero di problemi di supporto per gli utenti della rete. Prima di abilitare le seguenti impostazioni, assicurarsi che l'organizzazione sia in grado di affrontare questo ulteriore sovraccarico di gestione. Per molte organizzazioni, una soluzione migliore e meno costosa consiste nell'effettuare la scansione automatica dei registri eventi protezione per i controller di dominio e di generare allarmi amministrativi quando c'è la possibilità che qualcuno stia tentando di scoprire le password degli account utente.
  
È possibile configurare le impostazioni del criterio di blocco account nella seguente posizione nell'Editor oggetti Criteri di gruppo:
  
**Computer Configuration\\Windows Settings\\Security Settings\\Account Policies\\Account Lockout Policy**
  
La seguente tabella contiene le raccomandazioni per l'impostazione del criterio di blocco account per entrambi gli ambienti di protezione definiti in questa guida. Per maggiori informazioni su ciascuna impostazione consultare le sottosezioni seguenti.
  
**Tabella 2.2 Raccomandazioni per l'impostazione del criterio di blocco account**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazione</th>
<th>Valore predefinito del controller di dominio</th>
<th>EC</th>
<th>SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Blocca account per</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">15 minuti</td>
<td style="border:1px solid black;">15 minuti</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Limite di blocchi dell'account</td>
<td style="border:1px solid black;">0 tentativi di accesso non validi</td>
<td style="border:1px solid black;">50 tentativi di accesso non validi</td>
<td style="border:1px solid black;">10 tentativi di accesso non validi</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Reimposta blocco account dopo</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">15 minuti</td>
<td style="border:1px solid black;">15 minuti</td>
</tr>
</tbody>
</table>
  
#### Blocca account per
  
Questa impostazione di criterio determina l'intervallo di tempo che deve trascorrere prima che venga sbloccato un account e un utente possa eseguire nuovamente un tentativo di accesso. Tramite questa impostazione, è possibile esercitare tale controllo specificando il numero di minuti in cui l'account bloccato rimarrà non disponibile. Se il valore per questa impostazione di criterio viene configurato su 0, gli account selezionati rimarranno bloccati fino a quando un amministratore non li sblocca. Il valore predefinito di Windows XP per questa impostazione di criterio è **Non definito**.
  
Per ridurre il numero di chiamate di supporto all'help desk e per fornire un'infrastruttura sicura, configurare il valore per l'impostazione **Blocca account per** su **15** minuti per gli ambienti EC e SSLF definiti in questa guida.
  
Sebbene potrebbe sembrare opportuno configurare il valore di questa impostazione di criterio in modo da non sbloccare mai automaticamente gli account, è probabile che ciò causi un aumento delle chiamate ricevute dall'help desk per sbloccare gli account che sono stati bloccati per errore. Il valore di 15 minuti consigliato per l'impostazione si è rivelato un periodo di attesa ragionevole per gli utenti prima di effettuare nuovamente l'accesso agli account bloccati. Gli utenti dovrebbero essere informati sulla configurazione di questo criterio in modo che siano consapevoli che possono chiamare l'assistenza in caso di una necessità particolarmente urgente di recuperare l'accesso al loro computer.
  
#### Limite di blocchi dell'account
  
Questa impostazione di criterio determina il numero di tentativi di accesso che un utente può effettuare prima che un account sia bloccato. Gli utenti autorizzati possono bloccare un account digitando la password in modo non corretto, digitandone una errata o modificando la password in un computer diverso da quello in cui hanno eseguito l'accesso. Il computer in cui viene digitata la password non corretta tenterà continuamente di autenticare l'utente e, dato che la password utilizzata per l'autenticazione non è valida, l'account utente verrà infine bloccato. Per evitare il blocco accidentale di utenti autorizzati, impostare il limite di blocchi dell'account su un numero elevato. Il valore predefinito per questa impostazione di criterio è 0 tentativi di accesso non validi, il che disabilita la funzionalità di blocco account.
  
Configurare il valore per l'impostazione **Limite di blocchi dell'account** su **50** tentativi di accesso non validi per gli ambienti EC e su **10** per gli ambienti SSLF.
  
Poiché è possibile che un pirata informatico utilizzi questo stato di blocco per un attacco di tipo "Denial of Service" (DoS) attivando il blocco su un numero elevato di account, l'organizzazione deve determinare se utilizzare questa impostazione di criterio in base ai pericoli identificati e ai rischi da ridurre. Per questa impostazione è possibile scegliere tra due tipi di opzioni:
  
-   Configurare il valore di **Limite di blocchi dell'account** su **0** per assicurare che gli account non vengano bloccati. Questo valore di impostazione impedirà un attacco di tipo "Denial of Service" (DoS) mirato al blocco degli account dell'organizzazione. Ridurrà inoltre le chiamate all'help desk, perché gli utenti non potranno bloccare accidentalmente i loro account. Tuttavia, questo valore di impostazione non eviterà un attacco di tipo "brute force". È necessario considerare anche le seguenti strategie di difesa:
  
    -   Il criterio password impone che tutti gli utenti dispongano di password complesse costituite da 8 o più caratteri.
  
    -   Viene attivato un meccanismo di controllo affidabile per avvisare gli amministratori quando nell'ambiente si verifica una serie di blocchi degli account. Ad esempio, la soluzione di controllo deve monitorare l'evento di protezione 539, corrispondente a un errore di accesso. Questo evento indica che l'account è stato bloccato durante il tentativo di accesso.
  
La seconda opzione è:
  
-   Configurare **Limite di blocchi dell'account** su un valore che consentirà agli utenti di inserire accidentalmente la password errata più volte ma che bloccherà l'account se si verificherà un attacco di tipo "brute force". Un valore di impostazione di 50 tentativi di accesso non validi per gli ambienti EC e 10 per gli ambienti di tipo SSLF dovrebbero assicurare un'adeguata protezione e un'accettabile utilizzabilità. Questa configurazione impedirà blocchi di account accidentali e ridurrà le chiamate all'help desk ma, come descritto in precedenza, non impedirà un tipo di attacco "Denial of Service" (DoS).
  
#### Reimposta blocco account dopo
  
Questa impostazione di criterio determina l'intervallo di tempo prima che il **Limite di blocchi dell'account** si reimposti su zero. Il valore predefinito per questa impostazione di criterio è **Non definito**. Se viene definito il **Limite di blocco dell'account**, il tempo di ripristino deve essere inferiore o uguale al valore dell'impostazione **Blocca account per**.
  
Configurare il valore per l'impostazione **Reimposta blocco account dopo** su **15** minuti per gli ambienti EC e SSLF definiti in questa guida.
  
Se l'impostazione di criterio viene mantenuta sul valore predefinito o viene configurata su un intervallo troppo lungo, l'ambiente potrebbe essere esposto a un attacco di tipo DoS. Un pirata informatico potrebbe eseguire intenzionalmente alcuni tentativi di accesso non riusciti per tutti gli utenti dell'organizzazione, bloccandone gli account come descritto in precedenza. Se non viene determinato alcun criterio per reimpostare il blocco degli account, gli amministratori dovranno sbloccare manualmente tutti gli account. Al contrario, se viene configurato un intervallo di tempo ragionevole per questa impostazione, gli utenti rimarranno bloccati per il periodo impostato fino a quando tutti gli account non verranno sbloccati automaticamente. Il valore di impostazione consigliato di 15 minuti si è rivelato un periodo di tempo ragionevole che gli utenti sono disposti ad accettare, riducendo in questo modo il numero di chiamate effettuate all'help desk. Gli utenti dovrebbero essere informati sulla configurazione di questo criterio in modo che siano consapevoli che possono chiamare l'assistenza in caso di una necessità particolarmente urgente di recuperare l'accesso al loro computer.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di Assegnazione diritti utente
  
I diritti utente sono descritti dettagliatamente nel Capitolo 3, "Impostazioni di protezione per client Windows XP". Tuttavia, il diritto utente **Aggiunta del computer al dominio** dovrebbe essere assegnato a tutti i controller di dominio ed è quindi trattato in questo capitolo. Ulteriori informazioni sui server membri e sulle impostazioni del controller di dominio si trovano nei Capitoli 4 e 5 della *Guida per la protezione* di *Windows* *Server 2003*.
  
#### Aggiunta del computer al dominio
  
Questa impostazione di criterio consente all'utente di aggiungere un computer a un dominio specifico.
  
**Tabella 2.3 Raccomandazioni sulle impostazioni di assegnazione dei diritti utente**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazione</th>
<th>Valore predefinito del controller di dominio</th>
<th>EC</th>
<th>SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Aggiunta del computer al dominio</td>
<td style="border:1px solid black;">Authenticated Users</td>
<td style="border:1px solid black;">Amministratori</td>
<td style="border:1px solid black;">Amministratori</td>
</tr>
</tbody>
</table>
  
Per attivare l'impostazione **Aggiunta del computer al dominio**, questa deve essere assegnata all'utente in un GPO applicato a tutti i controller di dominio per il dominio. Un utente cui è stato concesso questo diritto può aggiungere al dominio fino a 10 workstation. Anche gli utenti che dispongono dell'autorizzazione alla **creazione di oggetti computer** per una OU o il Contenitore computer in Active Directory possono unire un computer e un dominio e aggiungere un numero illimitato di computer al dominio stesso, a prescindere dal fatto che sia stato loro assegnato il diritto utente **Aggiunta del computer al dominio**.
  
Per impostazione predefinita, tutti gli utenti del gruppo **Authenticated Users** possono aggiungere fino a 10 account di computer a un dominio di Active Directory. Questi nuovi account di computer vengono creati nel Contenitore computer.
  
In un dominio di Active Directory, ogni account di computer rappresenta un'identità di protezione completa con l'autorizzazione per l'autenticazione e l'accesso alle risorse del dominio. Alcune organizzazioni desiderano limitare il numero di computer in un ambiente di Active Directory in modo che sia possibile registrarli, eseguire build e gestirli in modo coerente. La possibilità per gli utenti di aggiungere computer al dominio ostacola questi sforzi di gestione. Inoltre, questo diritto utente consente agli utenti di eseguire attività più difficili da controllare, perché possono creare dei computer di dominio aggiuntivi non autorizzati.
  
Per questi motivi, il diritto utente **Aggiunta del computer al dominio** viene concesso solo al gruppo **Administrators** nei due ambienti definiti in questa guida.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Impostazioni di Opzioni di protezione
  
Il criterio di account deve essere definito in un GPO collegato a livello di dominio, come le impostazioni di criterio nel Criterio dominio predefinito. I controller di dominio ottengono sempre il criterio di account dai GPO a livello di dominio, anche se è presente una serie di criteri di account diversa in un GPO applicato alla OU che contiene il controller di dominio.
  
A livello di dominio esistono tre impostazioni delle opzioni di protezione simili ai criteri di account che dovrebbero essere prese in considerazione. È possibile configurare queste impostazioni delle opzioni di protezione nella seguente posizione dell'Editor oggetti Criteri di gruppo:
  
**Configurazione del computer\\Impostazioni di Windows\\Impostazioni di protezione\\Criteri locali\\Opzioni di protezione**
  
Nella tabella seguente sono incluse le raccomandazioni sull'impostazione delle opzioni di protezione per i due tipi di ambienti protetti definiti in questa guida. Per maggiori informazioni su ciascuna impostazione consultare le sottosezioni seguenti.
  
**Tabella 2.4 Raccomandazioni sull'impostazione delle opzioni di protezione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazione</th>
<th>Valore predefinito del membro di dominio</th>
<th>EC</th>
<th>SSLF</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Accesso di rete: consente la conversione SID/NOME anonima</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Disabilitato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protezione di rete: impone la disconnessione al termine dell'orario di accesso</td>
<td style="border:1px solid black;">Disabilitato</td>
<td style="border:1px solid black;">Attivato</td>
<td style="border:1px solid black;">Attivato</td>
</tr>
</tbody>
</table>
  
#### Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso
  
Questa impostazione di criterio determina se scollegare gli utenti connessi alla rete locale al di fuori dell'orario di connessione valido per l'account. Questa impostazione ha effetto sul componente SMB (Server Message Block). Quando questa impostazione di criterio è abilitata, le sessioni del computer client con il servizio SMB vengono disconnesse forzatamente al termine dell'orario di accesso del client. Se è disabilitata, la sessione del computer client stabilita può continuare dopo il termine dell'orario di accesso del client. Quando si abilita questa impostazione di criterio, assicurarsi che sia abilitata anche l'impostazione **Protezione di rete: impone la disconnessione al termine dell'orario di accesso**.
  
**Nota**:** **Il componente SMB è alla base della condivisione delle risorse nelle reti Windows. Le impostazioni che influiscono su questo componente influenzeranno anche le risorse condivise, le cartelle e le stampanti.
  
Se l'organizzazione ha configurato l'orario di accesso per gli utenti, è consigliabile attivare l'impostazione **Server di rete Microsoft: interrompe la connessione dei client al termine dell'orario di accesso**. In caso contrario, gli utenti che in teoria non possono accedere alle risorse di rete al di fuori del relativo orario di accesso potrebbero continuare effettivamente a utilizzare tali risorse tramite le sessioni stabilite durante l'orario di accesso.
  
Se l'orario di accesso non viene utilizzato nell'organizzazione, questa impostazione di criterio non avrà alcun effetto, anche se attivata. In caso di utilizzo dell'orario di accesso, le sessioni utente verranno chiuse al termine di tale orario.
  
#### Accesso di rete: consente la conversione SID/NOME anonima
  
L'impostazione **Accesso di rete: consenti conversione anonima SID/nome** determina se un utente anonimo può richiedere il SID di un altro utente. Se questa impostazione viene abilitata in un controller di dominio, un utente a conoscenza degli attributi SID di un amministratore potrebbe contattare un computer in cui è abilitato questo criterio e utilizzare il SID per ottenere le informazioni relative all'account dell'amministratore. Tale persona potrebbe quindi utilizzare l'account per avviare un attacco di determinazione della password. L'impostazione predefinita sui *computer membri* è impostata su **Disabilitato**. L'impostazione predefinita per i *controller di dominio* è invece impostata su **Abilitato**. Se questa impostazione di criterio è disabilitata, i seguenti sistemi potrebbero non essere in grado di comunicare con domini basati su Windows Server 2003:
  
-   Server con Servizio di Accesso remoto basati su Microsoft Windows NT 4.0.
  
-   I server del Servizio di Accesso remoto in computer basati su Windows 2000 che si trovano nei domini di Windows NT 3.*x* o di Windows NT 4.0.
  
-   Microsoft SQL Server in computer basati su Windows NT 3.*x* o su Windows NT 4.0.
  
-   SQL Server in computer basati su Windows 2000 che si trovano nei domini di Windows NT 3.*x* o di Windows NT 4.0.
  
-   Gli utenti del dominio risorse di Windows NT 4.0 che desiderano assegnare agli account utente le autorizzazioni per accedere ai file, alle cartelle condivise, e agli oggetti del Registro di sistema dai domini account che contengono i controller di dominio di Windows Server 2003.
  
#### Protezione di rete: impone la disconnessione al termine dell'orario di accesso
  
L'impostazione **Protezione di rete: imponi disconnessione al termine dell'orario di accesso** determina se disconnettere o meno gli utenti connessi alla rete locale al di fuori dell'orario di accesso valido del relativo account utente. Questa impostazione influisce sul componente SMB.
  
Se si attiva questa impostazione di criterio, le sessioni dei computer client con il server SMB saranno disconnesse quando l'orario di accesso dell'utente termina e non saranno in grado di accedere al sistema fino al successivo orario di connessione consentito. Se questa impostazione viene disabilitata, le sessioni del computer client stabilite verranno conservate anche dopo la scadenza dell'orario di connessione dell'utente. Perché abbia effetto sugli account di dominio, questa impostazione di criterio deve essere definita in un GPO collegato alla radice del dominio.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Criterio Kerberos
  
I criteri per il protocollo di autenticazione Kerberos versione 5 vengono configurati nei controller di dominio e non nei computer membri del dominio. Questo criterio determina le impostazioni Kerberos correlate, quali la durata del ticket e l'imposizione. Le impostazioni Kerberos non sono disponibili nei criteri del computer locale. Nella maggior parte degli ambienti, è consigliabile non modificare i valori predefiniti di queste impostazioni. Le indicazioni contenute in questa guida non prevedono alcuna modifica per il Criterio Kerberos. Per ulteriori informazioni su queste impostazioni, vedere la guida correlata [*Pericoli e contromisure: impostazioni di protezione per Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Criteri di gruppo a livello di OU
  
È necessario che le impostazioni di protezione incluse nella OU a livello di criteri di gruppo siano specifiche della OU. Queste impostazioni includono sia le impostazioni del computer sia quelle dell'utente. Per facilitare la gestione e migliorare la protezione, la sezione relativa ai criteri di restrizione software (SRP) è separata dalle altre impostazioni di protezione illustrate in questa guida. Il Capitolo 6, "Criteri di restrizione software per i client Windows XP", fornisce informazioni dettagliate su SRP.
  
#### Impostazioni di protezione dei criteri di gruppo
  
Sarà necessario creare un oggetto Criteri di gruppo per ogni categoria di computer Windows XP dell'ambiente. In questa guida, i computer portatili e desktop vengono suddivisi in unità organizzative separate per applicare oggetti Criteri di gruppo personalizzati per ognuna di queste categorie.
  
#### Impostazioni dei criteri di restrizione software
  
Creare GPO dedicati per la configurazione delle impostazioni dei criteri di restrizione software (SRP) nell'ambiente. Esistono importanti ragioni per cui è necessario mantenere le impostazioni dei criteri di restrizione software separate dalle impostazioni dei criteri di gruppo rimanenti. Una ragione è che SRP è concettualmente diverso dalle altre impostazioni dei criteri di gruppo. Le opzioni non sono abilitate o disabilitate e i valori non sono configurati. Invece, SRP richiede che gli amministratori identifichino la serie di applicazioni che saranno supportate, quali restrizioni saranno applicate e la modalità di gestione delle eccezioni. Un'altra ragione è la possibilità di eseguire un rapido ripristino nel caso in cui venga commesso un grave errore durante l'implementazione dei criteri SRP nell'ambiente di produzione: gli amministratori possono disabilitare temporaneamente i GPO in cui sono definite le impostazioni SRP senza influire sulle altre impostazioni di protezione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Strumenti relativi ai criteri di gruppo
  
In Windows XP sono presenti molti strumenti che facilitano l'utilizzo dei GPO. Nella sezione seguente viene presentata una breve panoramica di alcuni di questi strumenti. Per ulteriori informazioni su questi strumenti, vedere la Guida in linea di Windows XP.
  
#### Imposizione di un aggiornamento di criteri di gruppo
  
Active Directory aggiorna periodicamente i criteri di gruppo, ma è possibile imporre l'aggiornamento della versione nei computer client tramite GpUpdate, uno strumento della riga di comando fornito con Windows XP Professional. È necessario eseguire localmente lo strumento nei computer client.
  
Per aggiornare un computer locale con questo strumento, eseguire le seguenti operazioni al prompt dei comandi:
  
<codesnippet language displaylanguage containsmarkup="false">gpupdate /force  
```  
Dopo l'esecuzione di GpUpdate, verranno restituite le informazioni di conferma seguenti:
  
<codesnippet language displaylanguage containsmarkup="false">C:\\Documents and Settings\\administrator.MSSLAB&gt;gpupdate /force Refreshing Policy... User Policy Refresh has completed. Computer Policy Refresh has completed. To check for errors in policy processing, review the event log. C:\\Documents and Settings\\administrator.MSSLAB&gt;  
```  
Per i criteri di gruppo basati sull'utente, sarà necessario disconnettersi e quindi accedere di nuovo al computer utilizzato per verificare i criteri. È consigliabile aggiornare immediatamente i criteri relativi al computer.
  
Per visualizzare opzioni Gpupdate aggiuntive, eseguire le seguenti operazioni al prompt dei comandi:
  
<codesnippet language displaylanguage containsmarkup="false">gpupdate /?  
```  
#### Visualizzazione del Gruppo di criteri risultante
  
Due strumenti forniti con Windows XP consentono di determinare i criteri applicati ai computer dell'ambiente, nonché la data e l'ordine di applicazione.
  
-   **Snap-in RSoP**. Questo strumento (RSoP.msc) è uno snap-in MMC che visualizza le impostazioni aggregate di tutti i criteri applicati a un computer. È possibile eseguire lo strumento localmente oppure in modo remoto da un altro computer. Per ogni impostazione di criteri, lo strumento RSoP mostra l'impostazione del computer e l'oggetto Criteri di gruppo di origine.
  
-   **Gpresult**. GpResult è uno strumento della riga di comando che indica le statistiche relative all'ultima applicazione dei criteri di gruppo a un computer, gli oggetti Criteri di gruppo applicati e l'ordine di applicazione. Lo strumento riporta inoltre le informazioni relative a tutti i GPO applicati tramite filtri. È possibile utilizzare lo strumento GpResult in modo remoto o localmente nei computer client.
  
#### Console di gestione Criteri di gruppo
  
La Console di gestione Criteri di gruppo (GPMC) è uno snap-in di MMC disponibile come componente opzionale di Windows Server 2003 Service Pack 1. È utilizzato per gestire le attività relative ai criteri di gruppo. GPMC consente di pianificare, organizzare, distribuire, eseguire report e script e risolvere i problemi relativi all'applicazione dei GPO. Ulteriori informazioni sono disponibili sul sito di [GPMC](http://www.microsoft.com/windowsserver2003/gpmc/default.mspx) all'indirizzo www.microsoft.com/windowsserver2003/gpmc/default.mspx.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
I criteri di gruppo sono una funzionalità basata su Active Directory che consente di controllare ambienti relativi a utenti e computer nei domini di Windows Server 2003 e Windows 2000. Prima di applicare i criteri di gruppo ai computer desktop Windows XP dell'ambiente, è necessario eseguire alcune operazioni preliminari nel dominio.
  
Le impostazioni dei criteri di gruppo archiviate negli oggetti Criteri di gruppo (GPO) sui controller di dominio dell'ambiente sono collegate a siti Web, domini e unità organizzative contenuti all'interno della struttura di Active Directory. Prima di implementare i criteri di gruppo, è importante acquisire la conoscenza della struttura di Active Directory e delle implicazioni relative alla protezione associate alla configurazione delle diverse opzioni di progettazione.
  
I criteri di gruppo rappresentano uno strumento essenziale per la protezione di Windows XP. In questo capitolo è stata descritta in dettaglio la relativa procedura di utilizzo per applicare e mantenere criteri di protezione coerenti nella rete da una posizione centrale.
  
Vengono inoltre riportate informazioni sui diversi livelli dei criteri di gruppo e sugli strumenti speciali che è possibile utilizzare per l'aggiornamento dei criteri di gruppo nell'ambiente.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono ulteriori informazioni su argomenti relativi alla protezione di Windows XP Professional.
  
-   Per ulteriori informazioni sulla gestione e sulla progettazione di Active Directory, vedere il white paper "[Design Considerations for Delegation of Administration in Active Directory](http://technet.microsoft.com/en-us/magazine/2007.02.activedirectory.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/ad/windows2000/plan/addeladm.asp (in inglese).
  
-   Per ulteriori informazioni sulla progettazione di Active Directory, vedere il white paper "[Best Practice Active Directory Design for Managing Windows Networks](http://technet.microsoft.com/en-us/library/bb727085.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/ad/windows2000/plan/bpaddsgn.asp (in inglese).
  
-   Per ulteriori informazioni sui criteri di gruppo, vedere il white paper "[Step-by-Step Guide to Understanding the Group Policy Feature Set](http://technet.microsoft.com/en-us/library/bb742376.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/directory/  
    activedirectory/stepbystep/gpfeat.mspx.  
    Visitare inoltre l'home page dei [Criteri di gruppo](http://technet.microsoft.com/en-us/library/cc758751.aspx) di Windows Server 2003 all'indirizzo www.microsoft.com/windowsserver2003/technologies/management/grouppolicy/default.mspx (entrambe in inglese).
  
-   Per ulteriori informazioni sulla protezione di Windows XP, vedere "[Microsoft Windows XP Professional Resource Kit Documentation](http://technet.microsoft.com/en-us/library/bb491054.aspx)" all'indirizzo www.microsoft.com/WindowsXP/pro/techinfo/productdoc/resourcekit.asp (in inglese).
  
-   Per una panoramica sulle funzioni di protezione di Windows XP, vedere il white paper "[What's New in Security for Windows XP Professional and Windows XP Home Edition](http://technet.microsoft.com/en-us/library/bb457059.aspx)" all'indirizzo www.microsoft.com/technet/prodtechnol/winxppro/evaluate/xpsec.asp (in inglese).
  
-   Per ulteriori informazioni sui modelli amministrativi, vedere il white paper "[Implementing Registry-Based Group Policy](http://technet.microsoft.com/en-us/library/bb742499.aspx)" all'indirizzo www.microsoft.com/windows2000/techinfo/howitworks/management/rbppaper.asp (in inglese).
  
-   Per ulteriori informazioni sulla Console di gestione Criteri di gruppo (GPMC, Group Policy Management Console), vedere il [sito relativo](http://www.microsoft.com/windowsserver2003/gpmc/default.mspx) all'indirizzo http://www.microsoft.com/italy/windowsserver2003/gpmc/default.mspx (in inglese).
  
-   Per ulteriori informazioni sullo strumento Aggiornamento gruppo ([Gpupdate](http://technet.microsoft.com/en-us/library/bb490983.aspx)), vedere www.microsoft.com/technet/prodtechnol/winxppro/proddocs/refrGP.asp (in inglese).
  
-   Per ulteriori informazioni sullo strumento [Gruppo di criteri risultante](http://technet.microsoft.com/en-us/library/bb457060.aspx) (RSoP), vedere www.microsoft.com/technet/prodtechnol/winxppro/proddocs/RSPintro.asp (in inglese).
  
-   Per ulteriori informazioni sullo strumento Risultati criterio di gruppo ([Gpresult)](http://technet.microsoft.com/en-us/library/bb490915.aspx), vedere www.microsoft.com/technet/prodtechnol/winxppro/proddocs/gpresult.asp (in inglese).
  
##### Download
  
[![](images/Cc163071.icon_exe(it-it,TechNet.10).gif)Scaricare la Guida per la protezione di Windows XP](http://www.microsoft.com/downloads/details.aspx?familyid=2d3e25bc-f434-4cc6-a5a7-09a8a229f118&displaylang=en)
  
[](#mainsection)[Inizio pagina](#mainsection)
