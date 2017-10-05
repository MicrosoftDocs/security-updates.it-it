---
TOCTitle: 'Appendice B: Verifica della Guida per la protezione di Windows XP'
Title: 'Appendice B: Verifica della Guida per la protezione di Windows XP'
ms:assetid: '09c716f4-b167-49ec-8122-93e1b8c5f456'
ms:contentKeyID: 20213252
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163067(v=TechNet.10)'
---

Guida per la protezione di Windows XP
=====================================

### Appendice B: Verifica della Guida per la protezione di Windows XP

##### In questa pagina

[](#edaa)[Introduzione](#edaa)
[](#ecaa)[Ambiente di test](#ecaa)
[](#ebaa)[Metodologia di test](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

La funzione della *Guida per la protezione* di *Windows* XP è di fornire istruzioni di configurazione affidabili e ripetibili per proteggere i computer dotati di Microsoft Windows XP Professional con Service Pack 2 (SP2) in una varietà di ambienti.

La *Guida per la protezione* di *Windows* XP è stata verificata in un ambiente di laboratorio per assicurare che le istruzioni funzionino come previsto. È stata controllata l'uniformità della documentazione e tutte le procedure consigliate sono stato verificate dal team di testing della *Guida per la protezione* di *Windows* XP. I test sono stati eseguiti per verificare la funzionalità e per consentire agli utenti della guida di ridurre il numero di risorse necessarie per effettuare e verificare le proprie implementazioni della soluzione.

#### Ambito

La *Guida per la protezione* di *Windows* XP è stata verificata in un ambiente di laboratorio per due ambienti di protezione diversi: l'ambiente client di organizzazione (EC, Enterprise Client) e l'ambiente protezione specializzata/funzionalità limitata (SSLF, Specialized Security – Limited Functionality). Questi ambienti sono descritti nel Capitolo 2, "Configurazione dell'infrastruttura per il dominio di Active Directory". I test sono stati condotti in base ai criteri descritti nella successiva sezione "Obiettivi dei test".

Le verifiche del team di testing non prevedevano la valutazione della vulnerabilità dell'ambiente di laboratorio utilizzato per rendere sicura la soluzione della *Guida per la protezione* di *Windows* XP. Il test di penetrazione è stato eseguito dai partner commerciali.

#### Obiettivi dei test

Gli obiettivi del team di testing della *Guida per la protezione* di *Windows* XP erano i seguenti:

-   Assicurare che la configurazione e le impostazioni di criterio richieste per Windows XP Professional con SP2 si integrassero correttamente e come previsto in una rete di dominio basata su Windows Server™ 2003 per i due diversi ambienti di protezione.

-   Assicurare che i computer client Windows XP Professional SP2 fossero in grado di eseguire le attività e le applicazioni fondamentali elencate nei casi pratici di test correlati.

-   Verificare che tutti le istruzioni nella versione 2.1 della *Guida per la protezione* di *Windows* XP fossero chiare, complete e corrette da un punto di vista tecnico.

-   Verificare che i modelli di protezione funzionassero come previsto sul sistema operativo client Windows XP Professional SP2.

-   Verificare che le raccomandazioni relative ai modelli amministrativi e ai criteri di restrizione software funzionassero come previsto sul sistema operativo client Windows XP Professional SP2.

Infine, la guida deve essere ripetibile e utilizzabile in modo affidabile da un tecnico che abbia conseguito la certificazione MCSE (Microsoft Certified Systems Engineer) con due anni di esperienza.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambiente di test

L'ambiente di test consisteva in un servizio directory Windows Server 2003 SP1 Active Directory, computer per i ruoli di server dell'infrastruttura che hanno fornito il controller di dominio, servizi DNS e DHCP e gli altri computer per i ruoli di server delle applicazioni che hanno fornito i file, le stampanti, i servizi Web, la CA e i servizi di posta elettronica Microsoft Exchange 2003. I computer client desktop e portatili nel dominio hanno utilizzato Windows XP Professional con SP2.

La rete conteneva inoltre due computer client dotati di Windows XP Professional con SP2 in modalità workgroup, utilizzati per verificare modelli di protezione autonomi. I computer portatili nella rete di dominio sono stati riutilizzati per verificare modelli di protezione autonomi per i portatili. La figura seguente illustra la rete di test.

[![](images/Cc163067.SGFG0B01(it-it,TechNet.10).jpg)](https://technet.microsoft.com/it-it/cc163067.sgfg0b01_big(it-it,technet.10).jpg)

**Figura B.1 Rete utilizzata per verificare la Guida per la protezione di Windows XP in modalità autonoma e di dominio**

La rete nella figura seguente è stata sviluppata per verificare i modelli precedenti contenuti in questa guida.

[![](images/Cc163067.SGFG0B02(it-it,TechNet.10).jpg)](https://technet.microsoft.com/it-it/cc163067.sgfg0b02_big(it-it,technet.10).jpg)

**Figura B.2 Rete utilizzata per verificare i modelli precedenti di protezione contenuti in questa guida**

[](#mainsection)[Inizio pagina](#mainsection)

### Metodologia di test

Questa sezione descrive le procedure che sono stato seguite per verificare la *Guida per la protezione* di *Windows* XP.

Il team di testing ha allestito un laboratorio in cui sono state inserite le reti illustrate nella sezione precedente. Il team di testing ha eseguito due rapidi test di verifica funzionale (POC, Proof of Concept) e quindi due cicli di test più approfonditi. Durante ogni test il team si è impegnato a stabilizzare la soluzione.

Un ciclo di test è stato definito come una sequenza di due fasi di creazione incrementale:

1.  Fase di configurazione manuale del computer

2.  Fase di configurazione dei gruppi/criteri locali

I dettagli di ogni fase sono illustrati nella sezione "Fasi di un test". La sezione "Fase di preparazione del test" descrive i passaggi che sono stati seguiti per assicurare che l'ambiente di laboratorio non presentasse alcuna condizione che potesse causare errori nell'interpretazione dei risultati effettivi dei test dopo che entrambi gli ambienti erano stati verificati attraverso le due fasi di creazione incrementale.

Per ogni test sono stato eseguite diverse serie di casi pratici di test. Questi test sono illustrati nella sezione "Tipi di test" di questa appendice.

#### Fasi di un test

Questa soluzione è stato verificata attraverso le fasi descritte nelle seguenti sottosezioni. Tutti i problemi critici sorti in una fase di creazione sono stati documentati come errore e risolti nell'ambito della stessa fase, prima che il team di testing passasse alla successiva fase incrementale. Questo metodo ha consentito di risolvere rapidamente i problemi critici. Ha inoltre ridotto la necessità di risorse impiegate per il debug di problemi rilevati nelle fasi successive.

##### Fase di preparazione del test

In questa fase è stata configurata la rete di base alla quale è stata applicata la soluzione. I passaggi effettuati sono i seguenti:

**Per eseguire la fase di preparazione del test**

1.  Collegare i computer come illustrato nel diagramma di rete e installare le versioni appropriate del sistema operativo Windows su tutti i server e computer client.

2.  Creare e configurare i controller di dominio, i domini, e il ruolo di ogni server. Aggiungere i computer client Windows XP Professional con SP2 al dominio.

3.  Installare le applicazioni utente su tutti i computer client Windows XP Professional con SP2.

4.  Eseguire i test di verifica di base per confermare la correttezza della configurazione di rete. Assicurare l'accessibilità dei computer client ai servizi forniti dal controller di dominio e dai server membri (DNS, DHCP, CA, file, stampa, Web e posta elettronica).

5.  Eseguire le applicazioni installate per verificare che non siano presenti problemi di installazione e che tutte le applicazioni funzionino correttamente.

6.  Controllare il registro eventi per assicurarsi che non siano presenti errori.

7.  Una volta completati i passaggi precedenti, creare una copia dell'immagine di ciascun computer. Queste immagini di backup sono utilizzate per ripristinare la rete allo stato predefinito prima di avviare un nuovo test.

##### Fase di configurazione manuale

Questa fase costituisce spesso la fase iniziale di costruzione della protezione. Essa consiste nella seguente procedura di costruzione.

**Per eseguire la fase di configurazione manuale**

1.  Lo snap-in MMC (Microsoft Management Console) Gestione computer viene utilizzato per eseguire le modifiche alle impostazioni di criterio richieste, come l'account dell'amministratore locale e la password su ciascun computer membro. Completare i seguenti passaggi per assicurare la protezione degli account di dominio (account Guest e Administrator):

    1.  Disattivare l'account Guest.

    2.  Assicurarsi che l'account Administrator incorporato disponga di una password complessa e sia stato rinominato e che la descrizione predefinita dell'account sia stata rimossa.

    3.  Rispettare le ulteriori raccomandazioni della guida sulla protezione degli account di dominio.

2.  Eseguire tutta le altre procedure di protezione manuale applicabili come descritto in ogni capitolo della guida.

3.  Per i computer client Windows XP autonomi, creare manualmente un database protetto.

##### Fase di configurazione dei gruppi/criteri locali

In questa fase, gli oggetti Criteri di gruppo (GPO) vengono applicati a livello di dominio e di unità organizzativa (OU). I GPO vengono applicati alle diverse OU in base alle raccomandazioni del Capitolo 2, "Configurazione dell'infrastruttura per il dominio di Active Directory". Per i computer client Windows XP autonomi, vengono configurati criteri locali. Questa fase consiste nei seguenti passaggi.

**Per eseguire la fase di configurazione dei gruppi/criteri locali**

1.  Creare la struttura delle OU descritta per applicare le raccomandazioni relative ai criteri di gruppo presenti nella guida.

2.  Assegnare i computer client desktop e portatili Windows XP all'unità organizzativa appropriata.

3.  Identificare gli utenti di dominio e assegnarli alle unità organizzative appropriate, in modo da poter applicare i modelli amministrativi.

4.  Aggiungere un nuovo collegamento GPO per ogni OU.

    **Nota**: Potrebbe essere necessario elevare la priorità dei collegamenti GPO nell'elenco quando sono già presenti collegamenti predefiniti.

5.  Importare nel GPO il modello di protezione incluso nella guida.

6.  Per ogni scenario di ambiente nei vari capitoli, applicare i criteri di gruppo appropriati a ciascuna OU.

#### Dettagli sull'esecuzione del test

I capitoli 2-6 della *Guida per la protezione* di *Windows* XP forniscono le istruzioni per l'applicazione delle raccomandazioni per la protezione al dominio, ai computer desktop Windows XP, ai portatili Windows XP e ai computer client Windows XP autonomi per gli ambienti client di organizzazione (EC, Enterprise Client) e protezione specializzata/funzionalità limitata (SSLF, Specialized Security – Limited Functionality) definiti nella guida. Queste raccomandazioni sono integrate da una cartella di lavoro di Microsoft Excel, dai modelli di protezione, dai modelli amministrativi e dagli script automatici. Gli script automatici sono utilizzati per importare i modelli nel GPO locale sui computer client autonomi e protetti. Questa sezione illustra l'implementazione e la verifica delle raccomandazioni.

##### Capitolo 2: Configurazione dell'infrastruttura per il dominio di Active Directory

Completare le seguenti procedure per verificare questo capitolo.

**Per verificare la rete di base**

-   Completare i casi pratici di test per la verifica di base, in modo da assicurarsi che le copie dell'immagine funzionino correttamente. Se i casi pratici di test vengono completati con successo, i criteri iniziali sono stati rispettati.

**Per iniziare la fase di configurazione manuale**

1.  Sincronizzare l'ora di tutti i server membri di dominio e dei computer client Windows XP con il controller di dominio.

2.  Disattivare l'account Guest.

3.  Rinominare gli account Administrator e Guest.

4.  Modificare la password dell'amministratore.

**Per implementare la configurazione della struttura delle OU**

1.  Nel dominio corp.woodgrovebank.com, creare un'unità organizzativa con il nome "OU di reparto".

2.  Creare due sotto-OU nella OU di reparto. Assegnare loro i nomi "OU Windows XP" e "OU protetta per utenti di Windows XP".

3.  In OU Windows XP, creare quattro sotto-OU:

    -   OU per desktop EC

    -   OU per portatili EC

    -   OU per desktop SSLF

    -   OU per portatili SSLF

4.  Assegnare i computer Windows XP relativi a ciascun ambiente di protezione alle rispettive OU.

5.  Assegnare gli utenti di dominio che accederanno ai computer client Windows XP all'OU protetta per utenti di Windows XP.

6.  Creare e collegare un nuovo GPO denominato "Criteri di dominio" all'oggetto corp.woodgrovebank.com. Selezionare **Su** nella scheda Criteri di gruppo dell'oggetto di dominio nello snap-in MMC Utenti e computer di Active Directory per assegnare la priorità massima al nuovo GPO, quindi importare il modello di protezione appropriato (SSLF-domain.inf o EC-domain.inf) nel GPO.

7.  Eseguire **gpupdate /force** sul controller di dominio per scaricare le impostazioni dei criteri di gruppo più recenti.

##### Capitolo 3: Impostazioni di protezione per i client Windows XP

Questo capitolo descrive le impostazioni principali configurate attraverso i criteri di gruppo in un dominio Windows Server 2003. Il capitolo descrive le impostazioni di criterio per i due ambienti definiti, al fine di assicurare la protezione dei computer Windows XP con SP2 desktop e portatili.

**Per configurare le impostazioni dei modelli di protezione**

1.  Eseguire il test di distribuzione base per verificare che tutte le raccomandazioni della guida siano adatte all'ambiente. Esaminare le impostazioni di criterio raccomandate. Modificare le impostazioni dei modelli di protezione come necessario prima di distribuirli.

2.  Collegare i nuovi GPO alle due OU per desktop. Per l'ambiente client di organizzazione, importare il modello di protezione EC-desktop.inf nel GPO. Per l'ambiente protezione specializzata/funzionalità limitata, importare il modello di protezione SSLF-desktop.inf nel GPO.

3.  Collegare i nuovi GPO alle due OU per portatili. Per l'ambiente client di organizzazione, importare il modello di protezione EC-Laptop.inf nel GPO. Per l'ambiente protezione specializzata/funzionalità limitata, importare il modello di protezione SSLF-Laptop.inf nel GPO.

4.  Accedere a un client Windows XP ed eseguire il comando **gpupdate /force**. Quindi, riavviare il computer per assicurare che siano scaricate le impostazioni dei Criteri di gruppo più recenti.

5.  Eseguire i test elencati successivamente in questo documento.

##### Capitolo 4: Modelli amministrativi per Windows XP

Questo capitolo descrive la configurazione e l'applicazione delle impostazioni di criterio aggiuntive sui computer dotati di Microsoft Windows XP con SP2 utilizzando i modelli amministrativi.

**Per configurare le impostazioni dei modelli amministrativi**

1.  Eseguire il test di distribuzione base per verificare che tutte le raccomandazioni della guida siano adatte all'ambiente. Esaminare le impostazioni di criterio raccomandate. Modificare le impostazioni dei modelli amministrativi come necessario prima di distribuirli.

2.  Creare quattro nuovi GPO, uno per ciascuno dei quattro tipi di computer client Windows XP. Poiché esistono alcune differenze nelle impostazioni di criterio per i computer desktop e portatili, è consigliabile creare GPO separati per ciascuno di essi.

    -   Criteri dei modelli amministrativi per desktop EC

    -   Criteri dei modelli amministrativi per computer portatile EC

    -   Criteri dei modelli amministrativi per desktop SSLF

    -   Criteri dei modelli amministrativi per computer portatile SSLF

3.  Nei modelli amministrativi, configurare le impostazioni di configurazione del computer e le impostazioni di configurazione utente per ciascun GPO secondo le istruzioni fornite nel Capitolo 4, "Modelli amministrativi per Windows XP".

4.  Collegare i GPO alle rispettive OU.

5.  Accedere a un computer client Windows XP ed eseguire il comando **gpupdate /force**. Quindi, riavviare il computer per assicurare che siano scaricate le impostazioni dei Criteri di gruppo più recenti.

6.  Eseguire i test elencati successivamente in questa appendice.

##### Capitolo 5: Protezione per client Windows XP autonomi

Questo capitolo descrive le impostazioni di criterio principali impostate attraverso i criteri del computer locale. I valori di impostazione richiesti consentiranno di proteggere i computer desktop e portatili autonomi dell'organizzazione dotati di Windows XP con SP2.

**Per configurare le impostazioni di protezione sui client Windows XP autonomi**

1.  Eseguire il test di distribuzione base per verificare che tutte le raccomandazioni della guida siano adatte all'ambiente.

2.  Utilizzare lo snap-in MMC Analisi e configurazione della protezione per creare un database di protezione. Questo database sarà utilizzato per registrare i criteri locali. Istruzioni passo-passo sono fornite nel Capitolo 5, "Protezione di client Windows XP autonomi".

3.  Utilizzare lo snap-in Analisi e configurazione della protezione per applicare le impostazioni di criterio contenute nei file dei modelli di protezione autonomi. Istruzioni passo-passo sono fornite nel Capitolo 5, "Protezione di client Windows XP autonomi". È importante utilizzare lo snap-in Analisi e configurazione della protezione, perché le impostazioni di criterio dei servizi di sistema non possono essere applicate con lo snap-in Criteri del computer locale.

4.  Eseguire lo script automatico appropriato (contenuto in questa guida) per importare i modelli di protezione.

5.  Eseguire i test elencati successivamente in questa appendice.

##### Capitolo 6: Criteri di restrizione software per client Windows XP

Questo capitolo consente agli amministratori di identificare e controllare il software in esecuzione nel loro dominio. Lo strumento utilizzato per eseguire questo controllo è un meccanismo basato sui criteri chiamato criteri di restrizione software.

**Per configurare i criteri di restrizione software**

1.  Eseguire il test di distribuzione base per verificare che tutte le raccomandazioni della guida siano adatte all'ambiente.

2.  Localizzare l'OU creata per i computer desktop e portatili Windows XP. Per i computer client autonomi, le impostazioni di criterio si trovano nei criteri di protezione locali. Creare un nuovo GPO per l'OU Windows XP. Ricordare che questo nuovo GPO è utilizzato soltanto per i criteri di restrizione software.

3.  Configurare i criteri di restrizione software come segue:

    1.  Creare un criterio di restrizione software predefinito.

    2.  Configurare le regole di percorso.

    3.  Impostare le opzioni di criterio, come l'imposizione, i tipi di file designati e gli autori attendibili secondo le istruzioni fornite.

4.  Rivedere le impostazioni di criterio e reimpostare il criterio predefinito su **Non consentito**.

5.  Accedere a un client Windows XP ed eseguire il comando **gpupdate /force**. Quindi, riavviare il computer per assicurare che siano scaricate le impostazioni dei Criteri di gruppo più recenti.

6.  Eseguire i test elencati successivamente in questa appendice.

##### Verifica del download di criteri di gruppo sul client XP

Nelle sezioni precedenti, i GPO sono stato applicati alle OU, che a loro volta hanno applicato i GPO ai computer nelle OU. Completare i seguenti passaggi per confermare l'avvenuto scaricamento dei criteri di gruppo dal controller di dominio su un computer client Windows XP. Si presume che il computer client sia stato riavviato dopo che il GPO è stato collegato all'OU.

**Per verificare il download dei criteri di gruppo su un computer client Windows XP**

1.  Accedere al computer client Windows XP.

2.  Fare clic su **Start**, **Esegui**, digitare **rsop.msc** e premere INVIO.

3.  Nella console **Gruppo di criteri risultante**, espandere **Directory principale** e scorrere fino a **Configurazione computer**.

4.  Fare clic con il pulsante destro del mouse su **Configurazione computer** e scegliere **Proprietà**.

    L'elenco dei GPO viene visualizzato nel pannello **delle proprietà di configurazione del computer**. Il GPO applicato alla OU dovrebbe essere disponibile nell'elenco, e non dovrebbero essere presenti errori ad esso associati.

5.  Verificare le impostazioni di criterio dei modelli amministrativi.

    Nell'albero della cartella **Modelli amministrativi** sotto **Configurazione computer** o **Configurazione utente** dovrebbero essere visibili soltanto le impostazioni configurate nel GPO dei modelli amministrativi.

#### Tipi di test

Il team di testing ha eseguito i seguenti tipi di test durante le fasi di verifica per assicurare che i computer client Windows XP protetti siano in grado di eseguire attività fondamentali senza significativa perdita di funzionalità. È possibile fare riferimento alla cartella di lavoro Excel Windows XP Security Guide Test Cases.xls, che si trova nella cartella **\\Windows XP Security Guide Tools and Templates\\Test Tools** inclusa nel download di questa guida. Questa cartella di lavoro contiene l'elenco completo dei casi pratici di test che sono stati eseguiti per i computer client Windows XP basati su dominio e computer client Windows XP autonomi, oltre a dettagli quali gli scenari di testing, le fasi di esecuzione e i risultati previsti.

##### Test sulle applicazioni

Questi test controllano il corretto funzionamento delle applicazioni utente installate sui computer client Windows XP (come Office 2003 application suite, Windows Media Player e altri). Per ulteriori dettagli sui casi pratici di test, fare riferimento alla cartella di lavoro Microsoft Excel Windows XP Security Guide Test Cases.xls inclusa in questa guida.

##### Test degli script automatici

Per alcuni scenari dei casi pratici di test sono stati eseguiti script VBScript. Questi casi pratici di test sono relativi principalmente alla corretta funzionalità dei computer client Windows XP che utilizzano servizi basati sulla rete, come l'accesso al dominio, la modifica della password e l'accesso al server di stampa. I file VBScript di questi casi pratici sono disponibili nella cartella **\\Windows XP Security Guide Tools and Templates\\Test Tools**, contenuta nel download di questa guida.

##### Test di verifica di base

Questi casi pratici di test costituiscono un sottoinsieme dei test delle applicazioni, degli script automatici e di Internet. Si tratta di test di base che coprono una varietà di scenari diversi, come la capacità di eseguire le applicazioni installate sul client, test di comunicazione client-server, la capacità di accedere a Internet e di scaricare le patch e test che controllano gli errori sull'host. Questi casi pratici di test vengono eseguiti anche quando si stabilisce la rete di base nel corso della fase di preparazione del test.

##### Test sulla documentazione

Questi test confermano che le istruzioni, le procedure e le funzioni documentate nella guida all'implementazione sono esatte, non ambigue e complete. Per questi test non sono presenti casi pratici separati.

##### Test funzionali

Questi test sono destinati a verificare che il sistema configurato attraverso le linee guida per l'implementazione funzioni correttamente e come previsto. Verificano la funzionalità, l'integrità e l'efficacia delle procedure di creazione sui computer client desktop e portatili.

##### Test basati su Internet

Al giorno d'oggi è necessario per gli utenti accedere a Internet. Questi casi pratici di test assicurano che il blocco del computer client Windows XP non influenzi le funzionalità quotidiane più comuni (navigazione sui siti Web, utilizzo del servizio Windows Messenger e lo scaricamento di aggiornamenti critici dal sito Microsoft Update).

#### Criteri di riuscita o fallimento

Prima che i test fossero eseguiti, sono stato definiti i seguenti criteri per assicurare la prevenzione dei difetti e la correzione degli errori:

-   Tutti i casi pratici di test presi in esame devono essere superati con i risultati previsti, come descritto nel foglio di calcolo individuale di ogni caso pratico.

-   Un caso pratico di test è considerato superato quando il risultato effettivo corrisponde al risultato previsto documentato per il caso stesso. Se il risultato effettivo non corrisponde a quello previsto, il caso pratico di test viene considerato fallito, viene creato un errore e viene assegnato un punteggio di gravità.

-   Se un caso pratico è fallito, ciò non implica che la guida della soluzione sia errata. Ad esempio, l'interpretazione errata della documentazione del prodotto e una documentazione incompleta o inesatta possono causare il fallimento delle operazioni. Ogni operazione non riuscita viene analizzata per scoprirne la causa, in base ai risultati effettivi e ai risultati descritti nella documentazione del progetto. Le operazioni non riuscite vengono inoltre assegnate ai rispettivi responsabili dei prodotti Microsoft.

#### Criteri di rilascio

Il criterio di rilascio principale per la *Guida per la protezione* di *Windows* XP è stato collegato alla gravità degli errori non risolti. Tuttavia, sono state trattate anche altre questioni non relative agli errori. I criteri per il rilascio sono:

-   Non sono presenti errori non risolti con livello di gravità 1 e 2.

-   Tutti gli errori non risolti sono stati analizzati e suddivisi in categorie dal team e il relativo impatto è stato valutato a fondo.

-   Le guide della soluzione sono prive di commenti e revisioni.

-   La soluzione ha superato con successo tutti i casi pratici di test nell'ambiente di laboratorio.

-   Nell'ambito della soluzione, le istruzioni non sono in contraddizione tra loro.

#### Classificazione degli errori

La scale di gravità degli errori è descritta nella tabella seguente. La scala va da 1 a 4, dove 1 è il livello di gravità più alto e 4 il più basso.

**Tabella B.1 Classificazione della gravità degli errori**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Gravità</th>
<th style="border:1px solid black;" >Tipi più comuni</th>
<th style="border:1px solid black;" >Condizioni necessarie</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">– L'errore ha bloccato la creazione o ulteriori test.<br />
– L'errore ha causato accessibilità imprevista per l'utente.<br />
– I passaggi definiti nella documentazione non erano chiari.<br />
– I risultati o il comportamento di una funzione o di un processo contraddicono i risultati previsti (come documentato nella specifiche funzionali).<br />
– Rilevante mancanza di corrispondenza tra i file dei modelli di protezione e le specifiche funzionali.</td>
<td style="border:1px solid black;">– La soluzione non ha avuto successo.<br />
– L'utente non ha potuto utilizzare componenti importanti del sistema.<br />
– L'utente disponeva di privilegi di accesso che non dovrebbero essere consentiti.<br />
– L'accesso dell'utente a determinati server è stato bloccato quando invece doveva essere consentito.<br />
– Non sono stati ottenuti i risultati previsti.<br />
– I test non possono procedere senza essere eseguiti.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">– I passaggi definiti nella guida non sono chiari.<br />
– La documentazione relativa alla funzionalità è mancante (in questo caso, il test è stato bloccato).<br />
– La documentazione è mancante o inadeguata.<br />
– Incoerenza tra i file dei modelli di protezione e il contenuto della guida, mentre il file dei modelli di protezione corrisponde alle specifiche funzionali.</td>
<td style="border:1px solid black;">– L'utente non disponeva di una soluzione semplice per correggere la situazione.<br />
– L'utente non è stato in grado di trovare facilmente una soluzione.<br />
– Il sistema non era conforme ai requisiti aziendali di base.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">3</td>
<td style="border:1px solid black;">– Problema di formato documentato.<br />
– Lievi errori e imprecisioni nella documentazione.<br />
– Errori ortografici nel testo.</td>
<td style="border:1px solid black;">– L'utente disponeva di una soluzione semplice per correggere la situazione.<br />
– L'utente è stato in grado di trovare facilmente una soluzione.<br />
– L'errore non ha causato un'esperienza negativa per l'utente.<br />
– I requisiti aziendali di base sono funzionali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">4</td>
<td style="border:1px solid black;">– Suggerimenti.<br />
– Miglioramenti futuri.</td>
<td style="border:1px solid black;">– Chiaramente non relativo a questa versione.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questo documento consente a un'organizzazione che si serve della *Guida per la protezione* di *Windows* XP di conoscere le procedure e le fasi che sono stato utilizzate per verificare l'implementazione della soluzione in un ambiente di laboratorio. L'esperienza effettiva del team di testing della *Guida per la protezione* di *Windows* XP è illustrata in questo documento, che contiene le descrizioni dell'ambiente di test, i tipi di test, i criteri di rilascio ed i dettagli di classificazione degli errori.
  
Tutti i casi pratici di test presi in esame sono stati superati con i risultati previsti. Il team di testing ha confermato che la funzionalità richiesta era presente dopo che sono state applicate le raccomandazioni della *Guida per la protezione* di *Windows* XP per gli ambienti definiti.
  
##### Download
  
[![](images/Cc163067.icon_exe(it-it,TechNet.10).gif)Scaricare la Guida per la protezione di Windows XP](http://www.microsoft.com/downloads/details.aspx?familyid=2d3e25bc-f434-4cc6-a5a7-09a8a229f118&displaylang=en)
  
[](#mainsection)[Inizio pagina](#mainsection)
