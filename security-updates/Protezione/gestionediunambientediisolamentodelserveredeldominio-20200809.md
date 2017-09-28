---
TOCTitle: Gestione di un ambiente di isolamento del server e del dominio
Title: Gestione di un ambiente di isolamento del server e del dominio
ms:assetid: '8ee8b43f-373a-4d73-b4c5-16cc8cd45596'
ms:contentKeyID: 20200809
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536209(v=TechNet.10)'
---

Isolamento del server e del dominio tramite IPsec e criteri di gruppo
=====================================================================

### Capitolo 6: Gestione di un ambiente di isolamento del server e del dominio

Aggiornato : febbraio 16, 2005

In questo capitolo vengono fornite istruzioni su come gestire una soluzione di isolamento dei server e dei domini dopo la corretta distribuzione nell'ambiente di produzione.

È importante che il personale del supporto sappia che questa soluzione di isolamento offre un ulteriore livello di protezione e che per la connessione di un host a una risorsa non basta disporre di una connessione di rete e di un indirizzo IP. Analogamente, il personale incaricato della gestione dei criteri IPSec e dei criteri di gruppo deve sapere che una sola opzione impostata in modo errato può limitare notevolmente la funzionalità degli host che utilizzano i criteri. Per questi motivi, i team di supporto devono poter disporre di un insieme di processi e procedure documentati e comunicati in modo ottimale, da utilizzare una volta che la soluzione è operativa.

Le informazioni fornite in questo capitolo sono volte ad assistere nello sviluppo di tali processi di gestione della soluzione. Idealmente, i contenuti di questo capitolo dovrebbero essere personalizzati per riflettere il più possibile le esigenze dell'organizzazione. La pianificazione preventiva è la chiave del successo della gestione di una soluzione di isolamento dei server e dei domini.

##### In questa pagina

[](#eeaa)[Prima di iniziare](#eeaa)
[](#edaa)[Gestione delle modifiche](#edaa)
[](#ecaa)[Considerazioni sul backup e il ripristino](#ecaa)
[](#ebaa)[Riduzione dei rischi delle infezioni di rete](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Prima di iniziare

Le indicazioni fornite in questo capitolo presuppongono la conoscenza approfondita dei concetti relativi a Microsoft® Operations Framework (MOF) e a IPSec. È inoltre necessaria la conoscenza delle seguenti aree di Microsoft® Windows 2000 Server (o versioni successive):

-   Operazioni di base e manutenzione di Microsoft Windows Server™ 2003, compreso l’utilizzo di strumenti quali Visualizzatore eventi, Gestione computer e NTBackup.

-   Servizio directory di Active Directory®, inclusi la struttura e gli strumenti di Active Directory, la gestione di utenti, gruppi e altri oggetti Active Directory e l’uso dei criteri di gruppo.

-   Concetti alla base della protezione dei sistemi Windows, quali utenti, gruppi, controllo, elenchi di controllo di accesso (ACL), utilizzo dei modelli di protezione e applicazione dei modelli di protezione mediante i criteri di gruppo o gli strumenti della riga di comando.

-   Conoscenza dei concetti fondamentali relativi alle reti e in particolare a IPSec e al protocollo TCP/IP.

-   La conoscenza di Windows Scripting Host e di Microsoft Visual Basic® Scripting Edition (VBScript) consente di utilizzare al meglio gli script forniti con la soluzione, ma non è essenziale.

Prima di proseguire con gli argomenti di questo capitolo, è necessario avere letto gli altri capitoli della guida e conoscere a fondo l'architettura e la progettazione della soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Gestione delle modifiche

Uno dei principali obiettivi dei processi di gestione delle modifiche è assicurare che tutte le parti interessate da un'imminente modifica siano consapevoli del relativo impatto. Poiché molti sistemi hanno strette correlazioni al loro interno, le modifiche apportate a una parte del sistema potrebbero avere importanti ripercussioni su un'altra parte. Per ridurre o eliminare eventuali effetti negativi, il processo di gestione delle modifiche tenta di identificare tutti i sistemi e i processi interessati prima di rendere effettive le modifiche. Generalmente, l’ambiente di destinazione (o gestito) è l'ambiente di produzione, ma potrebbe includere anche gli ambienti di integrazione delle chiavi, di test e di distribuzione graduale.

Tutte le modifiche apportate all’ambiente IPSec devono seguire il processo standard di gestione delle modifiche MOF:

1.  **Richiesta di modifica**. L’inizializzazione formale di una modifica mediante l’invio di una richiesta di modifica (RFC).

2.  **Classificazione della modifica**. L’assegnazione di una priorità e di una categoria alla modifica, considerando come criteri l’urgenza e il relativo impatto sull’infrastruttura o sugli utenti. Tale assegnazione influisce sulla velocità e sul percorso dell'implementazione.

3.  **Autorizzazione della modifica**. La considerazione e l'approvazione o il rifiuto della modifica da parte del responsabile delle modifiche e del consiglio di approvazione delle modifiche, costituito da rappresentanti aziendali e del reparto IT.

4.  **Sviluppo della modifica**. La pianificazione e lo sviluppo della modifica, un processo che può variare notevolmente a seconda degli obiettivi e include le analisi delle fasi principali intermedie.

5.  **Rilascio della modifica**. Il rilascio e la distribuzione della modifica nell’ambiente di produzione.

6.  **Analisi della modifica**. Un processo successivo all'implementazione che verifica se la modifica ha raggiunto gli obiettivi stabiliti e determina se mantenere o meno tale modifica.

Le procedure di questa sezione illustrano come sviluppare alcune delle modifiche principali che probabilmente sarà necessario apportare regolarmente nell'ambiente IPSec. Ciascuna procedura di sviluppo di una modifica è affiancata da una procedura di rilascio in cui sono descritte le modalità di distribuzione della modifica nell'ambiente di produzione.

#### Modifica dei criteri IPSec

È importante tenere presenti le modalità con cui le modifiche apportate ai criteri IPSec influiscono sulle comunicazioni. Come nella distribuzione graduale iniziale, l'aspetto più importante è la tempistica delle modifiche in quanto questa determina la capacità di implementare una modifica e i tempi richiesti per il ripristino della modifica.

##### Ritardi nell'applicazione dei criteri

Quando viene sostituito un criterio IPSec assegnato a un oggetto Criteri di gruppo (GPO, Group Policy Object), si verificano necessariamente alcuni ritardi. Si assiste a un ritardo nella replica da parte di Active Directory dell'attributo GPO contenente l'assegnazione del dominio e anche il ritardo nel polling dei client membri di dominio che utilizzano i criteri di gruppo per il rilevamento della modifica nel GPO. Tali ritardi possono essere di meno di un minuto nelle sedi di piccole dimensioni, mentre raggiungono alcune ore nelle aziende operanti su scala globale. Microsoft consiglia di testare e documentare questi ritardi (minimi, massimi e medi) per un determinato ambiente aziendale affinché sia possibile prevedere il tempo richiesto per il primo impatto e il completamento della distribuzione graduale quando viene introdotta una modifica.

Quando i contenuti di un criterio IPSec già assegnato vengono modificati, si verificano ritardi analoghi. Si assiste pertanto al ritardo nella replica da parte di Active Directory degli oggetti dei criteri IPSec e al ritardo nel polling del servizio per i criteri IPSec sui computer membri. È possibile creare una condizione per cui la replica dell'assegnazione di un criterio nel GPO avviene prima della replica del criterio IPSec; in tal modo i client si comportano come se disponessero dell'assegnazione di un criterio IPSec basato sul dominio, senza essere in grado di recuperarlo. In tal caso, gli host Windows 2000 e Windows XP non riescono ad applicare il criterio basato sul dominio e non applicano neppure eventuali criteri locali eventualmente assegnati.

Per gestire correttamente i ritardi nella replica di Active Directory, è necessario *in primo luogo* verificare che tutti gli oggetti (GPO, criteri IPSec e così via) siano stati creati, *quindi* assegnare i criteri IPSec nei GPO.

##### Modifiche che influiscono sulla connettività IPSec

Nell'ambito dei criteri e dei gruppi che compongono una soluzione IPSec, vi sono diverse aree che influiscono sulla connettività. In questa sezione vengono fornite informazioni su come alcune modifiche possono influire sulla connettività IPSec dal punto di vista della modifica dei criteri per i server quando i client non dispongono degli ultimi aggiornamenti. Se la modalità principale o rapida IKE (Internet Key Exchange) non riesce a causa di una modifica, il flusso del traffico si arresta non appena le associazioni di protezione (SA) IPSec correnti diventano inattive o scade la loro durata in byte o secondi.

In questa sezione viene descritto l'impatto della maggior parte delle modifiche che è possibile apportare alla funzionalità client-server IPSec. Non si presuppone l'adozione della configurazione dei criteri IPSec della Woodgrove Bank. Ai fini di questa discussione, i client possono disporre di criteri simili a quelli dello scenario di esempio della Woodgrove Bank (in cui l'inizializzazione IKE per i server avviene tramite filtri client) oppure possono utilizzare solo la regola di risposta predefinita (non prevista nello scenario della Woodgrove).

###### Modifiche alla modalità principale

La modifica di un metodo di autenticazione o di un metodo di protezione in modalità principale comporta l'eliminazione da parte di IKE delle modalità principali esistenti, ma non influisce sulle SA in modalità rapida IPSec esistenti. Le nuove SA in modalità principale vengono generate alla successiva rigenerazione delle chiavi della modalità rapida.

Solitamente, la modifica dei criteri per i server non influisce sulla capacità dei client esistenti di rigenerare le chiavi della modalità principale. Tuttavia, alcune modifiche sul lato server che possono determinare l'esito negativo della negoziazione in modalità principale IKE dei client includono:

-   Il passaggio a un nuovo metodo di autenticazione (solo per i certificati) senza l'inclusione dei metodi di autenticazione precedenti che il client è in grado di utilizzare.

-   Il passaggio al metodo di protezione in modalità principale 3DES/SHA1/DH1 o DH2 con client configurati per utilizzare solo il metodo DES/SHA1/DH1.

-   L'attivazione di PFS (Perfect Forward Secrecy) in modalità principale senza l'aggiornamento dei criteri per il client e il server per consentire l'utilizzo di tale modalità principale.

-   L'attivazione di PFS in modalità rapida senza l'aggiornamento dei criteri per il client e il server per consentire l'utilizzo di tale modalità principale.

Le seguenti modifiche dei criteri per i server non influiscono sulla capacità dei client di rigenerare le chiavi delle SA in modalità principale:

-   Intervallo di polling per le modifiche dei criteri (poiché non si tratta di un'impostazione della modalità principale IKE)

-   Chiavi di sessione che utilizzano la stessa chiave principale (ad esempio il numero di modalità rapide per modalità principale IKE)

-   L'aggiunta di un nuovo metodo di protezione sconosciuto ai client

-   La modifica delle impostazioni avanzate di scambio delle chiavi dei criteri IPSec per i parametri di durata **Autentica e genera una nuova chiave** per la SA in modalità principale IKE

###### Modifiche alla modalità rapida

Qualsiasi modifica apportata a un'operazione filtro utilizzata per una SA IPSec provoca l'eliminazione delle SA IPSec esistenti che erano state stabilite in base alle relative impostazioni dei criteri. Se il flusso del traffico è attivo, viene pertanto tentata una nuova modalità rapida. Anche se una parte del traffico potrebbe andare persa durante questa modifica, le connessioni TCP dovrebbero venire ripristinate. Tuttavia, per i trasferimenti di dati ad alta velocità, con l'eliminazione immediata di una SA IPSec il traffico in uscita viene ignorato fino a quando non viene stabilita la nuova modalità rapida. Ad esempio, un burst di pacchetti di un flusso di dati video, a seguito del quale il ripristino TCP non riesce, provoca il ripristino della connessione dell'applicazione video.

Le modifiche dei criteri per i server che influiscono sulla capacità dei client IPSec attivi di rigenerare le chiavi della modalità rapida includono:

-   **Il passaggio da un filtro più generico a un filtro più specifico**. Questo tipo di modifica avviene, ad esempio, quando un server viene avviato con un filtro per *tutto il traffico* e in seguito questo filtro viene rimosso, mentre rimane attivo un filtro per il *solo traffico TCP*. Per evitare problemi, quando si aggiungono filtri specifici, si consiglia di mantenere attivi anche i filtri più generici. Ad esempio, se i client dispongono di un criterio di risposta predefinita e il criterio del server è stato cambiato da "tutto il traffico" in "solo traffico TCP", il filtro più specifico sarà soggetto al traffico in uscita sul server, che stabilirà una nuova SA IPSec per il solo traffico TCP quando sarà attiva la risposta predefinita per i client. Il filtro "tutto il traffico" verrà in seguito eliminato (dopo due ore) su tutti i client e potrà quindi essere eliminato senza problemi dal criterio del server.

    Se viene aggiunto al server un filtro più specifico che prevede un'operazione autorizzata, il traffico verrà immediatamente permesso e potrebbe venire ignorato da un client con un filtro di risposta predefinita IPSec più generico. Se ad esempio viene aggiunto un filtro di esenzione del traffico ICMP (Internet Control Message Protocol) sul server, ma sui client tutto il traffico verso il server è già protetto, i client proteggeranno il traffico ICMP in uscita, riceveranno una risposta ICMP non crittografata e ignoreranno il pacchetto, poiché il filtro di risposta predefinita IPSec corrente prevede la protezione di tutto il traffico. Questo esempio riguarda solo il traffico ICMP tra il server e il client e il comportamento atteso è sempre una perdita di traffico ICMP dopo la richiesta di protezione di tutto il traffico con il client da parte del server. A seconda delle situazioni, ciò può rappresentare o meno un problema operativo importante.

-   **Passaggio tra metodi di protezione o tipi di incapsulamento incompatibili**. Ad esempio, il passaggio dalla modalità di trasporto ESP solo 3DES/SHA1 alla modalità 3DES/MD5. È possibile evitare le negoziazioni in modalità rapida IKE non riuscite a causa di questo tipo di modifica includendo i metodi di protezione o i tipi di incapsulamento precedenti come ultima scelta per il metodo di protezione. Una volta verificato che tutte le SA IPSec utilizzano il nuovo metodo di incapsulamento, è possibile eliminare il metodo precedente nella parte inferiore dell'elenco dei metodi di protezione.

-   **Totale disabilitazione di una regola necessaria al client al fine di determinare la modalità principale o rapida IKE**. In modalità rapida, il filtro viene eliminato affinché le negoziazioni in modalità principale o rapida IKE vengano regolate da un diverso filtro oppure non vi sia un filtro preposto a tale operazione.

-   **Modifica di un'operazione filtro dalla negoziazione della protezione all'autorizzazione o blocco**. Il traffico autorizzato o bloccato in modo esplicito non richiede la rigenerazione delle chiavi poiché non fa più parte del canale di comunicazione protetto tramite IPSec.

-   **Deselezione della casella di controllo di ritorno alla modalità non crittografata**. A seguito di questa azione, i client attualmente connessi disporranno della connettività per tutta la durata della SA debole. Quando la SA scade o diventa inattiva, a seguito di nuovo traffico in uscita dal server IKE tenterà la negoziazione di una nuova modalità principale e riconoscerà l'impostazione di non ritorno alla modalità non crittografata. I client che non sono in grado di rispondere correttamente alla negoziazione IKE non riusciranno a connettersi. Questo comportamento, tuttavia, potrebbe essere ricercato intenzionalmente.

-   **Deselezione della casella di controllo di autorizzazione delle comunicazioni non protette**. Questa azione provoca la disconnessione dei client che non dispongono di filtri IPSec per l'azionamento dell'inizializzazione della modalità principale IKE. I client che utilizzano la regola di risposta predefinita rimangono connessi finché il filtro dinamico per la risposta predefinita diventa inattivo due ore dopo il termine del traffico sul server e in seguito non saranno più in grado di riconnettersi.

Le seguenti modifiche dei criteri per i server non influiscono sulla capacità dei client di rigenerare le chiavi delle SA in modalità rapida:

-   L'aggiunta di un filtro che non soddisfa i requisiti del traffico delle SA IPSec correnti non influisce su questo tipo di traffico. Ad esempio, se vengono aggiunti a un criterio del server filtri di autorizzazione per un nuovo indirizzo IP del controller di dominio.

-   Una modifica nella durata di una SA IPSec dell'operazione filtro, in termini di byte o di tempo.

-   La modifica dell'operazione filtro da Autorizza a Negozia protezione. Se i client possono rispondere, saranno in grado di negoziare una connessione protetta per questo tipo di traffico.

#### Procedure di modifica dei criteri IPsec

Nelle seguenti sezioni, vengono descritte le procedure di modifica dei criteri IPSec distribuiti tramite gli oggetti Criteri di gruppo (GPO). Anche se i passaggi descritti di seguito sono basati sull'utilizzo dello snap-in MMC Gestione criteri di protezione IP, nei sistemi Windows Server 2003, tutte le operazioni indicate possono essere effettuate mediante lo strumento della riga di comando Netsh.

Microsoft consiglia di utilizzare come stazione di gestione dei criteri la piattaforma Windows Server 2003, in quanto offre le migliori funzionalità di scripting e monitoraggio.

Le operazioni di esportazione e importazione dei criteri IPSec per Windows sono state previste a scopo di backup e ripristino. La funzione di esportazione copia tutti gli oggetti dei criteri IPSec nella posizione di archiviazione affinché tutti i relativi oggetti vengano catturati durante il backup. L'esportazione è il metodo consigliato di spostamento di tutti i criteri di dominio correnti nella posizione di archiviazione locale per l'esecuzione di test. Poiché vi sono possibilità di errore, è importante eliminare tutti gli oggetti che non si desidera esportare (compresi i criteri, gli elenchi filtri e le operazioni filtri) dall'archivio locale, prima di utilizzare la funzione di esportazione. Microsoft sconsiglia l'importazione di archivi locali esportati all'interno dei domini per evitare la possibilità che versioni precedenti degli oggetti vadano a sovrascrivere le versioni più recenti presenti nei domini, provocando l'interruzione dei collegamenti tra gli oggetti.

Il metodo consigliato per la creazione dei criteri IPSec e le integrazioni di rilievo agli oggetti esistenti, quali l'aggiunta di filtri all'elenco filtri corrente, è l'utilizzo di script da riga di comando. Generalmente, quando è necessario apportare modifiche importanti a un criterio IPSec, è consigliabile creare una nuova versione del criterio.

Una volta creato il criterio, sarà possibile rendere operative le modifiche utilizzando gli script oppure lo snap-in MMC Gestione criteri di protezione IP. Dopo aver creato e attivato il criterio IPSec, l'utilizzo dello snap-in MMC Gestione criteri di protezione IP è consigliato per apportare modifiche di minore entità.

Poiché lo strumento della riga di comando di Windows 2000 **Ipsecpol.exe** supporta solo la creazione dei criteri, è possibile utilizzare lo snap-in MMC per gestire i criteri in Windows 2000 Active Directory. L'aggiunta di un nuovo oggetto con lo stesso nome non è consentita nei comandi Netsh **add**. Per questo motivo, e poiché gli script vengono spesso eseguiti diverse volte, è necessario includere negli script Netsh i passaggi iniziali di eliminazione degli oggetti dei criteri esistenti prima di aggiungerne dei nuovi. L'eliminazione di un oggetto inesistente restituisce un messaggio di errore inatteso che arresta l'esecuzione dello script.

L'eliminazione di un criterio IPSec di dominio già assegnato a un GPO rende il collegamento del GPO non valido. Per riassegnare la versione aggiornata di un criterio IPSec, è necessario modificare il GPO.

**Nota:** anche se nella sezione seguente vengono presentate le modalità di modifica dei criteri IPSec direttamente all'interno di Active Directory, si presuppone che le modifiche siano state testate su un sistema locale o in un ambiente di test prima della distribuzione nell'ambiente di produzione.

##### Modifica dell'assegnazione di un criterio IPSec a un gruppo di isolamento

Per modificare un criterio IPSec assegnato a un gruppo di isolamento, è possibile sostituire il criterio IPSec esistente con un nuovo criterio.

La console di gestione Criteri di gruppo (GPMC, Group Policy Management Console) consente di cambiare il criterio IPSec distribuito da un determinato GPO. Dopo l'identificazione del nuovo criterio IPSec e del GPO che distribuisce il criterio corrente, effettuare i passaggi seguenti.

**Per modificare il criterio IPSec assegnato a un gruppo di isolamento**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare la console di gestione Criteri di gruppo.

3.  Espandere **Insieme di strutture:** ***&lt;nome dominio&gt;***, espandere **Domini**, quindi espandere ***&lt;nome dominio&gt;***.

4.  Fare clic con il pulsante destro del mouse su ***Nome GPO***, quindi scegliere **Modifica**.

5.  Espandere **Configurazione computer**, **Impostazioni di Windows**, **Impostazioni di protezione** e infine fare clic su **Criteri di protezione IP su Active Directory (*nome dominio*)**.

6.  Nel riquadro destro, fare clic con il pulsante destro del mouse su ***&lt;Nome criterio IPSec&gt;***, quindi scegliere **Assegna**.

7.  Verificare che ***&lt;Nome criterio IPSec&gt;*** sia assegnato, quindi chiudere l'Editor oggetti Criteri di gruppo e la console di gestione Criteri di gruppo.

#### Modifica di un criterio IPSec esistente nel dominio

A seguito delle estensioni della funzionalità IPSec in Windows XP e successivamente in Windows Server 2003, il formato di archiviazione dei criteri IPSec è stato cambiato per tener conto delle impostazioni relative alle estensioni di funzionalità. Accertarsi di non utilizzare una versione precedente dello snap-in MMC Gestione criteri di protezione IP per visualizzare o modificare un criterio contenente tali funzionalità estese. Facendo clic su **OK** durante la visualizzazione di un componente del criterio, le impostazioni esistenti vengono sovrascritte con le impostazioni nella memoria corrente, anche se non sono state apportate modifiche. I service pack di Windows XP e Windows 2000 Service Pack 4 (SP4) contengono aggiornamenti che consentono di rilevare le nuove versioni dei criteri al fine di evitare questo potenziale problema. Tuttavia, lo snap-in MMC non riuscirà a salvare le modifiche, comportandosi come se fosse stato negato l'accesso, e utilizzerà i messaggi di errore esistenti al momento del rilascio del prodotto. Analogamente, se l'utente che esegue lo snap-in MMC dispone solo dell'autorizzazione di accesso in lettura agli oggetti dei criteri IPSec, le modifiche non verranno salvate e si verificherà un errore di accesso negato. In Windows Server 2003, se non si intende apportare modifiche, utilizzare lo snap-in MMC Gestione criteri di protezione IP in modalità sola lettura. Infine, lo snap-in MMC non consente di immettere ID utente e password diversi durante la connessione a un computer o dominio remoti. L'utente deve accedere al desktop con le autorizzazioni appropriate per apportare le modifiche richieste.

##### Modifica di un elenco filtri di una regola esistente

Talvolta, è necessario modificare un elenco filtri di una regola esistente per aggiungere, rimuovere o modificare un elemento filtro. A tale scopo è possibile utilizzare lo snap-in MMC Gestione criteri di protezione IP. Tenere presente che l'ordine dei filtri all'interno dell'elenco non influisce sull'ordine in cui il driver IPSec elabora i pacchetti. I filtri di tutti gli elenchi filtri in tutte le regole di un criterio IPSec sono ordinati in base a un algoritmo interno di valutazione di priorità. Per apportare una modifica, è necessario verificare manualmente che il filtro non sia un duplicato di un altro filtro utilizzato dal criterio IPSec. In fase di test della modifica, è necessario assegnare localmente il criterio a un computer al fine di utilizzare lo snap-in MMC Monitor di protezione IP o l'output della riga di comando per visualizzare l'ordine esatto dei filtri e rilevare eventuali duplicati.

**Per aggiungere un computer a un elenco filtri**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare lo snap-in MMC Gestione criteri di protezione IP e orientarlo al dominio.

3.  Fare clic con il pulsante destro del mouse su **Criteri di protezione IPSec su Active Directory** e scegliere **Gestisci elenchi filtri IP e operazioni filtro**.

4.  Nella finestra **Gestisci elenchi filtri IP e operazioni filtro** della scheda **Gestisci elenchi filtri IP**, fare clic sull'elenco filtri delle ***esenzioni***, quindi selezionare **Modifica**.

5.  Verificare che la casella di controllo **Utilizza Aggiunta guidata** sia deselezionata.

6.  Nella finestra di dialogo **Elenco filtri IP**, fare clic su **Aggiungi**.

7.  Verificare che nella casella di riepilogo a discesa **Indirizzo di origine** venga visualizzato **Qualsiasi indirizzo IP**.

8.  Fare clic su **Indirizzo IP specifico** nella casella di riepilogo a discesa **Indirizzo di destinazione**.

9.  Digitare l'indirizzo IP specifico nella casella di testo **Indirizzo IP**.

10. Verificare che sia selezionata la casella di controllo **Speculare**.

11. Digitare nella scheda **Descrizione** una descrizione appropriata per l'elemento filtro.

12. Fare clic su **OK**, quindi di nuovo su **OK**.

13. Chiudere lo snap-in MMC Gestione criteri di protezione IP.

    **Nota:** una volta aggiunto il nuovo sistema a un elenco filtri per le esenzioni, è necessario aggiungere l'account del computer al gruppo di protezione No IPSec.

**Per modificare la voce relativa a un computer di un elenco filtri**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare lo snap-in MMC Gestione criteri di protezione IP e orientarlo al dominio.

3.  Fare clic con il pulsante destro del mouse su **Criteri di protezione IPSec su Active Directory** e scegliere **Gestisci elenchi filtri IP e operazioni filtro**.

4.  Nella finestra **Gestisci elenchi filtri IP e operazioni filtro** della scheda **Gestisci elenchi filtri IP**, fare clic sull'elenco filtri delle ***esenzioni***, quindi selezionare **Modifica**.

5.  Verificare che la casella di controllo **Utilizza Aggiunta guidata** sia deselezionata.

6.  Nell'elenco **Filtri IP**, fare clic sul filtro corrispondente a ***&lt;*n*ome computer&gt;***, quindi selezionare **Modifica**.

7.  Modificare la voce nella casella di testo **Indirizzo IP**, inserendo il nuovo indirizzo IP.

8.  Fare clic su **OK**, quindi di nuovo su **OK**.

9.  Chiudere lo snap-in MMC Gestione criteri di protezione IP.

**Per rimuovere una voce da un elenco filtri**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare lo snap-in MMC Gestione criteri di protezione IP e orientarlo al dominio.

3.  Fare clic con il pulsante destro del mouse su **Criteri di protezione IPSec su Active Directory** e scegliere **Gestisci elenchi filtri IP e operazioni filtro**.

4.  Nella finestra **Gestisci elenchi filtri IP e operazioni filtro** della scheda **Gestisci elenchi filtri IP**, fare clic sull'elenco filtri delle ***esenzioni***, quindi selezionare **Modifica**.

5.  Nell'elenco **Filtri IP**, fare clic sul filtro corrispondente a ***&lt;*n*ome computer&gt;***.

6.  Nella finestra di dialogo **Elenco filtri IP**, fare clic su **Rimuovi**.

7.  Scegliere **Sì** per rimuovere l'elemento filtro.

8.  Fare clic su **OK**, quindi di nuovo su **OK**.

9.  Chiudere lo snap-in MMC Gestione criteri di protezione IP.

    **Nota:** una volta rimosso il sistema da un elenco filtri per le esenzioni, è necessario rimuovere l'account del computer dal gruppo di protezione No IPSec.

##### Modifica di un'operazione filtro di una regola esistente

In un criterio IPSec, a ogni regola corrisponde un'operazione filtro che verrà eseguita quando la regola è applicabile. Anche se è possibile assegnare un nuovo criterio IPSec ai computer che utilizzano la nuova combinazione di operazione filtro e regola, può essere più logico modificare le operazioni filtro associate alle regole di criteri IPSec già esistenti. Se, ad esempio, esiste un criterio IPSec personalizzato per un insieme di computer, è più logico cambiare l'operazione filtro assegnata alla regola, anziché generare un criterio IPSec ex-novo.

È possibile configurare una regola di un criterio IPSec affinché utilizzi una nuova operazione filtro mediante lo snap-in MMC Gestione criteri di protezione IP.

**Per modificare un'operazione filtro di una regola esistente**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare lo snap-in MMC Gestione criteri di protezione IP e orientarlo al dominio.

3.  Nel riquadro destro, fare clic con il pulsante destro del mouse su ***&lt;nome criterio IPSec&gt;***,** **quindi scegliere **Proprietà**.

4.  Nell'elenco **Regole di protezione IP**, fare clic su ***&lt;nome regola&gt;***, quindi scegliere **Modifica**.

5.  Nell'elenco **Operazioni filtro** della scheda **Operazione filtro**, fare clic su ***&lt;nuova operazione filtro&gt;*** per selezionare il pulsante adiacente.

6.  Fare clic su **OK**, quindi di nuovo su **OK**.

7.  Chiudere lo snap-in MMC Gestione criteri di protezione IP.

##### Modifica del metodo di autenticazione per una regola esistente

Il metodo di autenticazione predefinito per i criteri IPSec è il protocollo Kerberos versione 5. Nel corso del tempo, può essere necessario cambiare il metodo di autenticazione associato a una regola esistente, se, ad esempio, viene distribuita un'infrastruttura a chiave pubblica (PKI, Public Key Infrastructure) per consentire l'autenticazione dei computer tramite certificati.

Sebbene siano richieste informazioni diverse a seconda del metodo di autenticazione scelto, le procedure di base per l'aggiunta dei diversi metodi di autenticazione sono simili tra loro. Ad esempio, per utilizzare una chiave già condivisa è necessario identificare tale chiave e utilizzare i certificati riconosciuti dall'autorità di certificazione (CA). Per aggiungere una nuova opzione di autenticazione a una regola IPSec esistente, attenersi alla procedura seguente.

**Per aggiungere un'opzione a una regola esistente**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare lo snap-in MMC Gestione criteri di protezione IP e orientarlo al dominio.

3.  Nel riquadro destro, fare clic con il pulsante destro del mouse su ***&lt;nome criterio IPSec&gt;***, quindi scegliere **Proprietà**.

4.  Nell'elenco **Regole di protezione IP**, fare clic su ***&lt;nome regola&gt;***, quindi scegliere **Modifica**.

5.  Nella scheda **Metodi di autenticazione**, fare clic su **Aggiungi**.

6.  Fare clic sul pulsante accanto alla nuova opzione di autenticazione, quindi configurare le opzioni eventualmente richieste.

7.  Scegliere **OK**.

8.  Nell'elenco **Ordine di preferenza metodo di autenticazione**, utilizzare i pulsanti **Sposta su** e **Sposta giù** per ordinare i metodi di autenticazione.

    **Nota:** per rimuovere un metodo di autenticazione, fare clic sull'elenco **Ordine di preferenza metodo di autenticazione**, quindi scegliere **Rimuovi**.

9.  Fare clic su **OK**, quindi di nuovo su **OK**.

10. Chiudere lo snap-in MMC Gestione criteri di protezione IP.

##### Aggiunta di una nuova regola a un criterio IPSec esistente

Aggiungendo nuove regole ai criteri IPSec esistenti, è possibile limitare o consentire maggiormente le comunicazioni tra computer dell'ambiente. Ad esempio, se un sistema che supporta IPSec deve poter comunicare con i sistemi di un determinato gruppo di isolamento, ma i criteri utilizzati non sono derivati dall'infrastruttura IPSec, è possibile modificare il criterio del gruppo di isolamento affinché consenta le comunicazioni.

In questo esempio, sarebbe necessario applicare un criterio che consenta le comunicazioni all'host IPSec non gestito. È inoltre necessario determinare un metodo di autenticazione condiviso, che può essere basato su certificati oppure su una chiave già condivisa. È possibile creare una nuova regola all'interno del criterio IPSec esistente affinché il gruppo di isolamento consenta il traffico una volta determinato il metodo di autenticazione.

I passaggi necessari sono la creazione di un nuovo elenco filtri nella directory, l'associazione di tale elenco al criterio esistente e la configurazione del meccanismo di autenticazione affinché includa il nuovo metodo di autenticazione.

**Per creare un nuovo elenco filtri per indirizzare tutto il traffico verso un computer specifico**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare lo snap-in MMC Gestione criteri di protezione IP e orientarlo al dominio.

3.  Fare clic con il pulsante destro del mouse su **Criteri di protezione IPSec su Active Directory** e scegliere **Gestisci elenchi filtri IP e operazioni filtro**.

4.  Nella scheda **Gestisci elenchi filtri IP e operazioni filtro**, fare clic su **Aggiungi**.

5.  Nella casella di testo **Nome**, digitare un nome appropriato per l'elenco filtri.

6.  Nella casella di testo **Descrizione**, digitare una descrizione appropriata per l'elenco filtri.

7.  Verificare che la casella di controllo **Utilizza Aggiunta guidata** sia deselezionata.

8.  Nella finestra di dialogo **Elenco filtri IP**, fare clic su **Aggiungi**.

9.  Verificare che nella casella di riepilogo a discesa **Indirizzo di origine** venga visualizzato **Qualsiasi indirizzo IP**.

10. Fare clic su **Indirizzo IP specifico** nella casella di riepilogo a discesa **Indirizzo di destinazione**.

11. Nella casella di testo **Indirizzo IP**, digitare l'indirizzo IP del computer.

12. Verificare che sia selezionata la casella di controllo **Speculare**.

    **Nota:** per impostazione predefinita, con questa procedura viene creata una regola che corrisponde a tutto il traffico da qualsiasi indirizzo IP a uno specifico indirizzo IP. Se è necessario far corrispondere la regola a una porta o un protocollo specifici, è necessario effettuare ulteriori configurazioni nella scheda **Protocollo**.

13. Digitare nella scheda **Descrizione** una descrizione appropriata per l'elemento filtro.

14. Fare clic su **OK**, quindi di nuovo su **OK**.

**Per modificare un criterio IPSec affinché utilizzi un nuovo elenco filtri e una nuova operazione filtro**

1.  Fare clic con il pulsante destro del mouse su ***&lt;nome criterio IPSec&gt;***, quindi scegliere **Proprietà**.

2.  Verificare che la casella di controllo **Utilizza Aggiunta guidata** sia deselezionata.

3.  Scegliere **Aggiungi**.

4.  Nell'elenco **Filtro IP** della scheda **Elenco filtri IP**, fare clic sul pulsante di opzione per ilnuovo elenco filtri.

5.  Nell'elenco **Operazioni filtro** della scheda **Operazione filtro**, fare clic sul pulsante di opzione **Operazione filtro**.

6.  Nella scheda **Metodi di autenticazione**, fare clic su **Aggiungi**.

7.  Fare clic sul pulsante accanto al nuovo metodo di autenticazione, quindi configurare le opzioni eventualmente richieste.

    **Nota:** il nuovo metodo di autenticazione deve essere negoziabile sia da parte dell'iniziatore che del risponditore, ad esempio una chiave già condivisa o i certificati. Se necessario, rimuovere il protocollo Kerberos dall'elenco selezionandolo e facendo clic sul pulsante **Rimuovi**.

8.  Scegliere **OK**.

9.  Se sono elencati più metodi di autenticazione, è possibile ordinarli nell'elenco **Ordine di preferenza metodo di autenticazione** utilizzando i pulsanti **Sposta su** e **Sposta giù**.

10. Fare clic su **OK**, quindi di nuovo su **OK**.

11. Chiudere lo snap-in MMC Gestione criteri di protezione IP.

#### Spostamento di host tra gruppi di isolamento

Per diversi motivi, può essere necessario spostare periodicamente gli host da un gruppo di isolamento a un altro. È importante conoscere le implicazioni che le variazioni dell'appartenenza ai gruppi determinano a livello di comunicazioni e traffico. Nella sezione seguente si descrive la procedura che consente di aggiungere o rimuovere gli host dai gruppi.

##### Aggiunta o rimozione di un host da un elenco esenzioni

È possibile aggiungere o rimuovere un host dall'elenco esenzioni modificando gli elenchi filtri delle esenzioni IPSec e il gruppo di protezione per il quale non viene utilizzato IPSec. Per eseguire questa operazione, attenersi alla procedura descritta in precedenza nella sezione "Modifica di un elenco filtri di una regola esistente" in questo capitolo.

Per completare questa operazione, è necessario conoscere l'elenco filtri delle esenzioni, il nome dell'host e il relativo indirizzo IP.

#### Aggiunta o rimozione di host e utenti da gruppi esistenti

La procedura di aggiunta o rimozione di un host da un gruppo di accesso di rete (NAG, Network Access Group) varia in base al ruolo ricoperto dall'host all'interno del gruppo. Se l'host ha la funzione di iniziatore, è sufficiente aggiungere o rimuovere l'host dal gruppo NAG. Tuttavia, se l'host ha il ruolo di risponditore, è necessario applicare o rimuovere il criterio che controlla l'aggiornamento del diritto "Accedi al computer dalla rete". Se il sistema ha entrambi i ruoli di iniziatore e risponditore, è necessario effettuare entrambe le operazioni.

##### Aggiunta o rimozione di iniziatori da un gruppo di accesso di rete esistente

Per aggiungere o rimuovere un iniziatore da un gruppo di accesso di rete, è sufficiente modificare il relativo gruppo di protezione utilizzando i normali strumenti di gestione gruppi.

**Per modificare un gruppo di accesso di rete in relazione a un computer specifico**

1.  Accedere al controller di dominio come amministratore e avviare Utenti e computer di Active Directory.

2.  Espandere il dominio, quindi fare clic su **Utenti**.

3.  Nel riquadro destro, fare clic con il pulsante destro del mouse su ***&lt;gruppo di accesso di rete&gt;*** e scegliere **Proprietà**.

4.  Per aggiungere un computer al gruppo:

    1.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.

    2.  Fare clic sul pulsante **Tipi di oggetto**, selezionare la casella di controllo **Computer**, quindi fare clic su **OK**.

    3.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare *&lt;nome computer&gt;*, quindi fare clic su **OK**.

    4.  Scegliere **OK**.

5.  Per rimuovere un computer dal gruppo:

    1.  Fare clic sulla scheda **Membri**.

    2.  Nell'elenco **Membri**, fare clic su ***&lt;nome computer&gt;,*** quindi scegliere **Rimuovi**.

    3.  Scegliere **Sì** per rimuovere l'account ***&lt;nome computer&gt;***.

    4.  Scegliere **OK**.

        **Nota:** il momento in cui l'account dell'host viene aggiunto al gruppo non coincide con il momento in cui l'host è in grado di accedere alla risorsa soggetta a restrizioni. Questo ritardo è dovuto al tempo necessario per le operazioni di replica e al tempo richiesto per gli aggiornamenti del ticket di sessione sul server che ospita la risorsa soggetta a restrizioni (se il ticket è contenuto nella cache).

##### Aggiunta o rimozione di utenti da un gruppo di accesso di rete esistente

Anche se lo scopo primario dei gruppi di isolamento è quello di definire gli host autorizzati all'avvio delle comunicazioni con una risorsa soggetta a restrizioni, è possibile utilizzare tali gruppi per definire gli utenti autorizzati ad accedere alla risorsa. Se non è necessario limitare l'accesso a una risorsa con una modalità simile ai NAG, è possibile concedere al gruppo Utenti dominio il diritto "Accedi al computer dalla rete" sui risponditori. Se invece è necessario limitare l'accesso a una risorsa, viene creato un gruppo Utenti NAG.

Per aggiungere o rimuovere un utente soggetto a restrizioni da un gruppo Utenti NAG, è sufficiente modificare il relativo gruppo di protezione utilizzando i normali strumenti di gestione gruppi. Questa procedura è richiesta solo se è stato creato e assegnato al gruppo di accesso di rete un gruppo Utenti NAG; se si utilizza il gruppo Utenti dominio, questa procedura non è necessaria.

**Per modificare un gruppo Utenti NAG in relazione a un utente specifico**

1.  Accedere al controller di dominio come amministratore e avviare Utenti e computer di Active Directory.

2.  Espandere il dominio, quindi fare clic su **Utenti**.

3.  Nel riquadro destro, fare clic con il pulsante destro del mouse sul gruppo di protezione ***Utenti NAG*** e scegliere **Proprietà**.

4.  Per aggiungere un utente al NAG:

    1.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.

    2.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare *&lt;nome utente&gt;* e fare clic su **OK**.

    3.  Scegliere **OK**.

5.  Per rimuovere un computer dal NAG:

    1.  Fare clic sulla scheda **Membri**.

    2.  Nell'elenco **Membri**, fare clic su ***&lt;nome utente&gt;,*** quindi scegliere **Rimuovi**.

    3.  Scegliere **Sì** per rimuovere l'account ***&lt;nome utente&gt;***.

    4.  Scegliere **OK**.

        **Nota:** il momento in cui l'account utente viene aggiunto al gruppo non coincide con il momento in cui l'utente è in grado di accedere alla risorsa soggetta a restrizioni. Questo ritardo è dovuto al tempo necessario per le operazioni di replica e al tempo richiesto per gli aggiornamenti del ticket di sessione sul server che ospita la risorsa soggetta a restrizioni (se il ticket è contenuto nella cache).

##### Aggiunta o rimozione di risponditori da un gruppo di accesso di rete esistente

Per rimuovere un host risponditore da un NAG esistente, è possibile rimuovere l'assegnazione del GPO che configura il diritto "Accedi al computer dalla rete" sul risponditore. L'applicazione dell'oggetto Criteri di gruppo può essere controllata mediante gli strumenti standard di applicazione criteri di Active Directory. Tuttavia, in questa guida si presuppone l'assegnazione del GPO a un'unità organizzativa creata allo scopo di contenere gli account dei computer di dominio dei risponditori. È sufficiente togliere un account di computer dall'unità organizzativa dei risponditori perché questo non riceva più il GPO assegnato; inoltre, l'accesso non sarà più soggetto a restrizioni. In tal caso, il computer tornerebbe a utilizzare il criterio del dominio di isolamento. Nel caso in cui l'account del computer appartenga a un gruppo di protezione locale di dominio composto da gruppi di accesso di rete, è necessario rimuovere l'account anche da questo gruppo.

Dopo la rimozione da un NAG, è importante verificare che gli host membri di più NAG siano ancora in grado di comunicare con gli altri NAG.

#### Aggiunta di nuovi gruppi di accesso di rete

Il processo di creazione di un nuovo NAG è piuttosto semplice. In primo luogo è necessario creare un gruppo locale di dominio per controllare l'accesso alla risorsa e un GPO per aggiornare il diritto "Accedi al computer dalla rete" sugli host che fungono da server nel NAG. È quindi necessario applicare il GPO così creato ai server e identificare gli host che appartengono al gruppo.

L'appartenenza al NAG è richiesta per i soli iniziatori. In altri termini, se due server che appartengono allo stesso gruppo di isolamento non avviano mai comunicazioni tra di loro, non è necessario aggiungerli al NAG per il relativo gruppo di isolamento. Tuttavia, sarà necessario aggiungere al NAG i due server che devono comunicare tra loro insieme a tutti gli altri iniziatori.

Se un server ha la funzione di risponditore all'interno di più NAG, è importante accertarsi che dopo l'applicazione del GPO tutti i gruppi di protezione NAG a cui appartiene il server siano inclusi nel diritto "Accedi al computer dalla rete" del sistema. Eventualmente potrebbero essere richiesti ulteriori GPO al fine di consentire a computer specifici di soddisfare questa esigenza.

##### Creazione di un nuovo gruppo di accesso di rete per i computer iniziatori

Attenersi alla procedura seguente per creare un nuovo NAG.

**Per creare un nuovo NAG per i computer iniziatori**

1.  Accedere al controller di dominio come amministratore e avviare Utenti e computer di Active Directory.

2.  Fare clic con il pulsante destro del mouse sul contenitore **Utenti**, scegliere **Nuovo**, quindi **Gruppo**.

3.  Nella casella di testo **Nome gruppo**, digitare un nome appropriato per il gruppo.

4.  Fare clic sul **gruppo di protezione Locale al dominio** e scegliere **OK**.

5.  Fare clic con il pulsante destro del mouse sul gruppo appena creato, quindi scegliere **Proprietà**.

6.  Nella casella di testo **Descrizione**, digitare una descrizione appropriata per il gruppo.

7.  Scegliere **OK**.

##### Aggiunta di account di computer iniziatori a un gruppo di accesso di rete

Attenersi alla procedura seguente per aggiungere a un nuovo NAG gli account degli iniziatori.

**Per aggiungere al nuovo NAG gli account degli iniziatori**

1.  Accedere al controller di dominio come amministratore e avviare Utenti e computer di Active Directory.

2.  Espandere il dominio, quindi fare clic su **Utenti**.

3.  Nel riquadro destro, fare clic con il pulsante destro del mouse sul gruppo* ****Iniziatori NAG***, quindi selezionare **Proprietà**.

4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.

5.  Fare clic sul pulsante **Tipi di oggetto**, selezionare la casella di controllo **Computer**, quindi fare clic su **OK**.

6.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare *&lt;nome iniziatore&gt;* e fare clic su **OK**.

7.  Scegliere **OK**.

Se è necessario limitare ulteriormente gli utenti del dominio a cui consentire l'accesso alla risorsa soggetta a restrizioni, si deve creare un gruppo per gli utenti NAG soggetti a restrizioni. Diversamente, è possibile utilizzare il gruppo Utenti dominio.

##### Creazione di un nuovo gruppo di accesso di rete per gli utenti soggetti a restrizioni

Attenersi alla procedura seguente per creare un nuovo NAG per gli utenti soggetti a restrizioni.

**Per creare un nuovo NAG per gli account utente**

1.  Accedere al controller di dominio come amministratore e avviare Utenti e computer di Active Directory.

2.  Fare clic con il pulsante destro del mouse sul contenitore **Utenti**, scegliere **Nuovo**, quindi **Gruppo**.

3.  Nella casella di testo **Nome gruppo**, digitare un nome appropriato per il gruppo.

4.  Fare clic sul **gruppo di protezione Locale al dominio** e scegliere **OK**.

5.  Fare clic con il pulsante destro del mouse sul gruppo appena creato, quindi scegliere **Proprietà**.

6.  Nella casella di testo **Descrizione**, digitare una descrizione appropriata per il gruppo.

7.  Scegliere **OK**.

##### Aggiunta di account utente con restrizioni a un gruppo di accesso di rete

Attenersi alla procedura seguente per aggiungere a un nuovo NAG gli utenti soggetti a restrizioni.

**Per aggiungere al nuovo NAG gli account utente**

1.  Accedere al controller di dominio come amministratore e avviare Utenti e computer di Active Directory.

2.  Espandere il dominio, quindi fare clic su **Utenti**.

3.  Nel riquadro destro, fare clic con il pulsante destro del mouse sul gruppo* ****Utenti NAG***, quindi selezionare **Proprietà**.

4.  Selezionare la scheda **Membri** e fare clic su **Aggiungi**.

5.  Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare *&lt;nome utente&gt;* e fare clic su **OK**.

6.  Scegliere **OK**.

##### Creazione di un GPO per concedere il diritto "Accedi al computer dalla rete"

Il diritto "Accedi al computer dalla rete" viene concesso ai NAG appropriati tramite un GPO.

Nella tabella seguente viene riportato un esempio di GPO utilizzato per implementare i nomi del NAG e dei gruppi ad esso associati a cui è necessario concedere il diritto "Accedi al computer dalla rete".

**Tabella 6.1. Esempio di definizione di criterio NAG**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome GPO</th>
<th>Nome gruppo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><em>&lt;Nome criterio implementazione NAG&gt;</em></td>
<td style="border:1px solid black;"><em>&lt;Nome NAG&gt;</em>
Amministratori
Operatori backup
<em>Utenti NAG</em> o Utenti dominio</td>
</tr>
</tbody>
</table>
 

**Nota:** come minimo, devono essere aggiunti tutti i gruppi elencati. L'amministratore dovrà determinare se è necessario concedere il diritto anche ad altri gruppi.
Il gruppo Utenti dominio viene aggiunto per impostazione predefinita. Se l'amministratore desidera limitare l'accesso da parte degli utenti, oltre che dei computer, dovrà creare un gruppo *Utenti NAG* simile a quello per gli account di computer in cui inserire gli account utente selezionati.

**Per creare un GPO con cui concedere il diritto "Accedi al computer dalla rete"**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare la console di gestione Criteri di gruppo.

3.  Espandere **Insieme di strutture:** ***&lt;nome dominio&gt;***, espandere **Domini**, quindi espandere ***&lt;nome dominio&gt;***.

4.  Fare clic con il pulsante destro del mouse su **Oggetti criteri di gruppo**, quindi fare clic su **Nuovo**.

5.  Nella casella di testo **Nome**, digitare *&lt;Nome GPO&gt;*, quindi fare clic su **OK**.

6.  Fare clic con il pulsante destro del mouse su ***&lt;Nome GPO&gt;***, quindi scegliere **Modifica**.

7.  Espandere **Configurazione computer**, espandere **Impostazioni di Windows**, **Impostazioni di protezione**, **Criteri locali** e infine fare clic su **Assegnazione diritti utente**.

8.  Nel riquadro destro, fare clic con il pulsante destro del mouse su "Accedi al computer dalla rete" e scegliere **Proprietà**.

9.  Selezionare la casella di controllo **Definisci le impostazioni relative ai criteri**.

10. Fare clic sul pulsante **Aggiungi utente o gruppo**.

11. Fare clic sul pulsante **Sfoglia**.

12. Nella casella di testo **Immettere i nomi degli oggetti da selezionare**, digitare i nomi dei gruppi elencati nella tabella precedente, separati dal punto e virgola, quindi scegliere **OK**.

13. Scegliere **OK**.

14. Chiudere l'Editor oggetti Criteri di gruppo e la console di gestione Criteri di gruppo.

##### Distribuzione dei GPO di un gruppo di accesso di rete

Per distribuire i GPO di un NAG, questi devono in primo luogo venire collegati a una posizione all'interno dell'ambiente di dominio per consentirne l'applicazione ai risponditori appropriati nel NAG. L'applicazione dell'oggetto Criteri di gruppo può essere controllata mediante gli strumenti standard di applicazione criteri di Active Directory. Fornire istruzioni dettagliate in merito esula dagli argomenti trattati all'interno della guida in quanto la procedura varia a seconda della struttura delle unità organizzative e dei metodi di gestione utilizzati all'interno dell'organizzazione.

#### Disabilitazione di IPSec in un gruppo di isolamento

I criteri IPSec possono venire disabilitati modificando i GPO preposti alla loro distribuzione. Per disabilitare un criterio IPSec, è necessario configurare il relativo GPO in modo che le impostazioni del computer vengano disabilitate.

**Per disabilitare le impostazioni del computer relative a un GPO**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare la console di gestione Criteri di gruppo.

3.  Espandere **Insieme di strutture:** ***&lt;nome dominio&gt;***, **Dominio** e ***&lt;nome dominio&gt;***, quindi espandere **Oggetti criteri di gruppo**.

4.  Fare clic con il pulsante destro del mouse su ***&lt;Nome GPO&gt;***, selezionare **Stato GPO,** quindi scegliere **Impostazioni configurazione computer attivate**.

5.  Chiudere la console di gestione Criteri di gruppo.

#### Riabilitazione di IPSec in un gruppo di isolamento

I criteri IPSec che sono stati disabilitati possono venire nuovamente abilitati modificando i GPO preposti alla loro distribuzione. Per riabilitare un criterio IPSec, è necessario configurare il relativo GPO in modo che le impostazioni del computer vengano riabilitate.

**Per abilitare le impostazioni del computer relative a un GPO**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare la console di gestione Criteri di gruppo.

3.  Espandere **Insieme di strutture:** ***&lt;nome dominio&gt;***, **Dominio** e ***&lt;nome dominio&gt;***, quindi espandere **Oggetti criteri di gruppo**.

4.  Fare clic con il pulsante destro del mouse su ***&lt;Nome GPO&gt;***, selezionare **Stato GPO**, quindi scegliere **Attivato**.

5.  Chiudere la console di gestione Criteri di gruppo.

#### Rimozione di IPSec da un gruppo di isolamento

I criteri IPSec possono venire rimossi modificando i GPO preposti alla loro distribuzione. Per rimuovere un criterio IPSec, è necessario configurare il relativo GPO in modo che il criterio non sia più assegnato.

**Per annullare l'assegnazione di un criterio IPsec di un GPO**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare la console di gestione Criteri di gruppo.

3.  Espandere **Insieme di strutture:** ***&lt;nome dominio&gt;***, espandere **Domini**, quindi espandere ***&lt;nome dominio&gt;***.

4.  Fare clic con il pulsante destro del mouse su ***&lt;Nome GPO&gt;***, quindi scegliere **Modifica**.

5.  Espandere **Configurazione computer**, **Impostazioni di Windows**, **Impostazioni di protezione** e infine fare clic su **Criteri di protezione IP su Active Directory (*nome dominio*)**.

6.  Nel riquadro destro, fare clic con il pulsante destro del mouse su ***&lt;Nome criterio IPSec&gt;***, quindi scegliere **Annulla assegnazione**.

7.  Verificare che ***&lt;Nome criterio IPSec&gt;*** non sia più assegnato, quindi chiudere l'Editor oggetti Criteri di gruppo e la console di gestione Criteri di gruppo.

[](#mainsection)[Inizio pagina](#mainsection)

### Considerazioni sul backup e il ripristino

In questa sezione vengono fornite informazioni su come valutare i processi relativi al backup e al ripristino dei componenti della soluzione di isolamento dei server e dei domini.

#### Backup di Active Directory

I criteri IPSec non vengono memorizzati all'interno degli oggetti Criteri di gruppo che li distribuiscono. Le funzionalità di backup e ripristino dei criteri di gruppo consentono unicamente di raccogliere informazioni sui criteri IPSec assegnati agli oggetti Criteri di gruppo, ma non agiscono direttamente sui criteri stessi.

Anche se un backup completo dello stato del sistema di un controller di dominio consente di acquisire i dati relativi ai criteri IPSec, è possibile utilizzare i comandi di menu **Esporta criteri** e **Importa criteri** dello snap-in MMC Gestione criteri di protezione IP per eseguire il backup e il ripristino dei criteri IPSec.

**Nota:** è importante proteggere i backup dei criteri IPSec. Tuttavia, il file di backup eredita le autorizzazioni del file system NTFS della directory in cui è memorizzato e i dati contenuti nel file non sono crittografati o firmati. È pertanto necessario proteggere le informazioni di configurazione IPSec contenute in questi file mediante le autorizzazioni o le procedure di protezione appropriate. L'accesso a tali file di backup dovrebbe essere consentito ai soli amministratori di IPSec autorizzati.

Per ulteriori informazioni sul backup dei dati dello stato del sistema di un computer che esegue Windows Server 2003, vedere la pagina [To back up System State data](http://www.microsoft.com/resources/documentation/windowsserv/2003/standard/proddocs/en-us/ntbackup_backup_sysstate.asp) sul sito Microsoft.com all'indirizzo www.microsoft.com/resources/documentation/windowsserv/2003/standard/
proddocs/en-us/ntbackup\_backup\_sysstate.asp.

#### Ripristino degli host

Nei computer per i quali il criterio IPSec è stato ripristinato tramite il backup (backup su nastro e basato su immagine), il criterio che viene applicato può essere una copia memorizzata nella cache del criterio IPSec basato su Active Directory o di un criterio IPSec locale.

Se al computer è stato assegnato un criterio IPSec basato su Active Directory, il servizio IPSec tenterà di recuperare l'ultima copia del criterio IPSec assegnato da Active Directory prima di applicare la copia del criterio memorizzata nella cache. Durante tale processo, il servizio IPSec invia in primo luogo una query al servizio DNS (Domain Name System), richiedendo l'elenco degli indirizzi IP di tutti i controller di dominio. Se gli oggetti dei criteri IPSec sono stati eliminati da Active Directory, viene applicata la copia del criterio memorizzata nella cache.

L'elenco degli indirizzi IP dei controller di dominio nella copia memorizzata nella cache del criterio IPSec basato su Active Directory potrebbe essere stato cambiato in modo sostanziale dopo il backup del criterio IPSec (ad esempio, nel frattempo possono essere stati aggiunti nuovi controller di dominio). In tal caso, le comunicazioni con gli attuali controller di dominio potrebbero essere bloccate e pertanto quando il computer tenta di stabilire connessioni remote protette tramite IPSec, le autenticazioni basate sul protocollo Kerberos avrebbero esito negativo. Il computer potrebbe inoltre non riuscire a ricevere gli aggiornamenti dei criteri di gruppo. Questo problema può essere risolto nel modo seguente:

1.  Accedere localmente al computer e arrestare il servizio IPSec in esecuzione su di esso.

2.  Riavviare il computer in Modalità provvisoria con rete e configurare il servizio IPSec per l'avvio manuale oppure disabilitare il servizio IPSec per consentire le comunicazioni protette con IPSec con gli indirizzi IP dei nuovi controller di dominio.

[](#mainsection)[Inizio pagina](#mainsection)

### Riduzione dei rischi delle infezioni di rete

In alcune circostanze, ad esempio durante la diffusione di virus o in caso di intrusioni, può essere necessario interrompere tempestivamente le comunicazioni al fine di assicurare la protezione dell'ambiente. Nelle sezioni seguenti vengono descritte diverse modalità di isolamento degli host che partecipano a comunicazioni autenticate. Per la loro stessa natura, tali metodi non consentono di isolare l'infrastruttura o i server esentati in quanto è importante che i server infrastruttura *non* vengano isolati al fine di consentire ai sistemi di aggiornare i criteri IPSec dal dominio.

**Nota:** sebbene tali metodi di isolamento abbiano validità tecnica, non sono stati testati in un ambiente di prova. Prima di adottare tali metodi, si raccomanda pertanto di testarli in un ambiente di laboratorio.

#### Isolamento del dominio di isolamento

Gli host all'interno del dominio di isolamento possono avviare comunicazioni con host ritenuti non attendibili. Nel caso sia necessario bloccare rapidamente questo tipo di traffico, è possibile modificare l'operazione filtro IPSEC – Modalità di richiesta protetta (Ignora in ingresso, Consenti in uscita) in modo che il diritto "Consenti comunicazioni non protette con computer senza IPSec" sia disabilitato. Una volta trascorso il periodo di tempo del polling IPSec, è necessario bloccare le comunicazioni di tutti gli host del dominio di isolamento con i sistemi che non appartengono all'ambiente IPSec.

**Per modificare l'operazione filtro IPSEC – Modalità di richiesta protetta (Ignora in ingresso, Consenti in uscita)**

1.  Accedere al controller di dominio come amministratore.

2.  Avviare lo snap-in MMC Gestione criteri di protezione IP e orientarlo al dominio.

3.  Fare clic con il pulsante destro del mouse su **Criteri di protezione IPSec su Active Directory** e scegliere **Gestisci elenchi filtri IP e operazioni filtro**.

4.  Nella scheda **Gestisci operazioni filtro IP**, fare clic sull'operazione filtro **IPSEC – Modalità di richiesta protetta (Ignora in ingresso, Consenti in uscita),** quindi selezionare **Modifica**.

5.  Selezionare o deselezionare la casella di controllo **Consenti comunicazioni non protette con computer senza IPSec**.

6.  Scegliere **OK**.

7.  Scegliere **OK**.

Una volta impostata questa opzione, il criterio bloccherà tutto il traffico di rete destinato agli host non attendibili. Dopo aver risolto il problema, è infine possibile ripristinare le comunicazioni riabilitando l'opzione corrispondente.

#### Blocco delle porte

I criteri IPSec distribuiti ai computer nella LAN interna aziendale sono configurati per consentire le comunicazioni su tutte le porte. Tale approccio semplifica la configurazione e la gestione dell'ambiente. Tuttavia, se un host che utilizza IPSec viene infettato da software dannosi, come virus e worm, è probabile che diffonda l'infezione ad altri computer. A seconda dei criteri abilitati sul computer, l'infezione può diffondersi a host sia attendibili che non.

I criteri IPSec consentono di ridurre la diffusione dei software dannosi bloccando esplicitamente le porte utilizzate da tali software. Il limite principale di questo approccio è il ritardo con cui tutti i computer rilevano le modifiche ai criteri che contengono filtri di blocco. Inoltre, il flooding della rete da parte di alcuni worm rende difficile il recupero delle modifiche ai criteri IPSec. Poiché questi worm utilizzano porte necessarie anche per servizi critici quali DNS, l'aggiornamento dei criteri dopo l'applicazione dei filtri di blocco sugli host risulta difficoltoso. Il blocco può essere attuato con la creazione di una regola che blocchi il traffico da qualsiasi indirizzo IP a una porta specifica utilizzata da una determinata tipologia di software dannoso. Tale regola deve essere aggiunta a tutti i criteri utilizzati nell'ambiente. Una volta rimosso il software dannoso, sarà quindi possibile rimuovere la regola dai criteri.

Dopo aver identificato le porte e i protocolli utilizzati da determinate forme di software dannoso, creare un elenco filtri che corrisponda ai criteri delle comunicazioni utilizzate dal software dannoso in base alla procedura "Aggiunta di una nuova regola a un criterio IPSec esistente" descritta in precedenza nella sezione "Modifica dei criteri IPSec" in questo capitolo. Non appena si decide di bloccare le porte mediante i criteri del dominio, è necessario ridurre l'intervallo di polling del criterio IPSec. Una volta superato il pericolo, sarà possibile incrementare nuovamente l'intervallo di polling.

Tuttavia, anziché creare un filtro per qualsiasi indirizzo IP verso uno specifico indirizzo IP, è necessario creare un filtro per il traffico da "Indirizzo IP" a qualsiasi indirizzo IP. Di solito, i filtri di tipo speculare non vengono utilizzati. È necessario un elenco filtri che contenga due filtri unidirezionali, uno per il traffico in ingresso per una porta nota e uno per il traffico in uscita per una porta nota. Ad esempio, i seguenti filtri bloccano la porta SQL 1433 che viene sfruttata dal worm SQLSlammer:

Da Qualsiasi indirizzo IP -&gt; Indirizzo IP, TCP, src \*, dst 1433, non speculare

Da Indirizzo IP -&gt; Qualsiasi indirizzo IP, TCP, src \*, dst 1433, non speculare

Naturalmente, questi filtri bloccano anche le connessioni delle applicazioni SQL e dovranno essere rimossi una volta superato il pericolo di diffusione del worm. È importante evitare di bloccare l'accesso alle porte critiche per il funzionamento dell'infrastruttura, come le porte DNS, a meno che questa misura non sia assolutamente inevitabile. Poiché viene definito un preciso indirizzo IP, questi filtri sono più specifici dei filtri di subnet dell'esempio della Woodgrove Bank che negoziano IPSec per tutto il traffico sulla rete interna.

Una volta creato il filtro, aggiungere una regola a tutti i criteri IPSec del dominio di isolamento e di gruppo per associare l'elenco filtri all'operazione filtro IPSec – Blocca. È opportuno includere nella configurazione dei criteri una regola che associ un elenco filtri IPSec vuoto utilizzato per le porte bloccate all'azione di blocco. Questo elenco potrà essere utilizzato per le regole di tutti i criteri IPSec e abilitato in modo che i membri del dominio possano controllarlo a ogni intervallo di polling. In alternativa, disabilitando la regola, il polling del servizio IPSec rileverà quando la regola è abilitata nei diversi criteri dei singoli gruppi di isolamento.

Se per un qualche motivo il blocco delle porte impedisce a IPSec di accedere ad Active Directory per ottenere il criterio aggiornato, l'amministratore potrà arrestare e riavviare il servizio IPSec sul computer o riavviare il computer stesso. All'avvio del servizio IPSec, questo tenterà di scaricare la versione più aggiornata del criterio IPSec assegnato prima di applicare la versione precedente memorizzata nella cache.

#### Isolamento solo all'interno di un dominio figlio

Se è necessario isolare un intero dominio dal resto dei domini dell'insieme di strutture, è possibile configurare il criterio per tale dominio in modo che utilizzi una chiave già condivisa anziché il protocollo Kerberos. Tale approccio consente ai computer del dominio figlio di mantenere le comunicazioni con gli altri sistemi dello stesso dominio, ma blocca al contempo le comunicazioni con i sistemi esterni al dominio a cui solitamente è consentito l'accesso.

Ogni criterio del dominio figlio dovrà essere modificato affinché utilizzi esclusivamente una chiave già condivisa per la regola IPSec - Subnet organizzative protette. È inoltre necessario rimuovere qualsiasi metodo di autenticazione esistente, ad esempio il protocollo Kerberos. Per configurare i metodi di autenticazione, attenersi alla procedura descritta in precedenza nella sezione "Modifica del metodo di autenticazione per una regola esistente" in questo capitolo.

Se il criterio prevede ulteriori regole di autenticazione, anche queste dovranno venire configurate affinché utilizzino una chiave già condivisa. Sarà quindi necessario configurare in questo modo tutti i criteri del dominio figlio da isolare. Per ridurre al minimo i casi di autenticazioni della modalità principale IKE non riuscite, è possibile inserire l'autenticazione tramite chiave già condivisa al primo posto nell'ordine di priorità dell'elenco dei metodi di autenticazione, seguita dal metodo basato sul protocollo Kerberos. Una volta che tutti i computer avranno aggiornato i loro criteri, sarà possibile rimuovere il metodo di autenticazione Kerberos. Un processo analogo viene utilizzato per ripristinare l'autenticazione per il protocollo Kerberos e rimuovere la chiave già condivisa una volta superato il pericolo.

#### Isolamento di gruppi predefiniti

L'implementazione dei gruppi di accesso di rete è una delle modalità di isolamento di un gruppo predefinito di computer, tuttavia l'utilizzo di chiavi già condivise o certificati consente di ottenere gli stessi risultati. La differenza principale rispetto ai gruppi di accesso di rete consiste nel fatto che è necessario creare criteri distinti per ogni gruppo di computer al fine di proteggere il traffico tra i computer che dispongono di una chiave già condivisa o un certificato. Tale soluzione richiede un'ulteriore pianificazione del traffico e delle comunicazioni, in particolare se un sistema appartiene a più gruppi.

Il principale svantaggio delle chiavi già condivise è il fatto che sono memorizzate nel formato non crittografato e pertanto risultano facilmente leggibili, ovvero la loro segretezza può venire violata, da parte di un client all'interno del dominio. Questo svantaggio non rappresenta tuttavia un problema se il valore della chiave precondivisa viene utilizzato solo per fornire un isolamento temporaneo durante la diffusione di un worm.

In ragione della limitazione del modo con cui IKE controlla le restrizioni dei certificati a livello di CA principale, anziché di CA di emissione, risulta necessario distribuire una CA principale per ciascun gruppo.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo

Nel presente capitolo sono state fornite informazioni e descritti i processi e le procedure di gestione, manutenzione e modifica di una soluzione di isolamento dei server e dei domini già distribuita e funzionante.

Tali processi e procedure devono essere documentati e comunicati in modo ottimale a tutto il personale coinvolto nella gestione quotidiana degli host all'interno dell'ambiente. Poiché non è possibile eliminare completamente l'eventualità che una piccola modifica apportata a un criterio IPSec disabiliti un percorso di comunicazione protetto, tali processi e procedure devono essere progettati in modo da evitare che la mancata comprensione da parte di un operatore delle conseguenze che derivano da una modifica porti all'introduzione di errori.

**Scarica la soluzione completa**

[Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=33947)

[](#mainsection)[Inizio pagina](#mainsection)
