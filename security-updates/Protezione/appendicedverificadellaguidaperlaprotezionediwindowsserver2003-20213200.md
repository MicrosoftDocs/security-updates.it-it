---
TOCTitle: 'Appendice D: Verifica della Guida per la protezione di Windows Server 2003'
Title: 'Appendice D: Verifica della Guida per la protezione di Windows Server 2003'
ms:assetid: '6aec7740-ad4a-4bbb-916c-16b8da021179'
ms:contentKeyID: 20213200
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163106(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Appendice D: Verifica della Guida per la protezione di Windows Server 2003

##### In questa pagina

[](#edaa)[Panoramica](#edaa)
[](#ecaa)[Ambiente di test](#ecaa)
[](#ebaa)[Verifica della metodologia](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

La *Guida per la protezione di Windows Server 2003* è stata redatta per fornire consigli di configurazione sperimentati e ripetibili per i computer con Microsoft Windows* *Server**2003 con il Service Pack 1 (SP1) in una vasta gamma di ambienti.

La *Guida per la protezione di Windows Server 2003* è stata controllata in ambienti di prova per assicurare che funzioni come previsto. La coerenza della documentazione e le procedure consigliate sono state verificate dal team addetto al controllo della *Guida per la protezione di Windows Server 2003*. I test sono stati eseguiti per verificare la funzionalità, ma anche per facilitare la riduzione di risorse necessarie a chi utilizza la guida per creare e verificare le proprie implementazioni.

#### Ambito

La *Guida per la protezione di Windows Server 2003* è stata verificata in un laboratorio di test che ha simulato tre ambienti di protezione diversi: Legacy Client(LC), Enterprise Client (EC) e Protezione specializzata/funzionalità limitata (SSLF). Questi ambienti sono descritti nel Capitolo 1, "Introduzione alla Guida per la protezione di Windows* * Server* *2003". I test sono stati eseguiti in base ai criteri descritti nella seguente sezione "Obiettivi della prova".

Una valutazione di vulnerabilità del laboratorio di test che è stato utilizzato per ottenere la soluzione della *Guida per la protezione di Windows Server 2003* non rientrava nelle competenze del team di test.

#### Obiettivi dei test

Il team addetto al test della *Guida per la protezione di Windows Server 2003* si è prefisso di ottenere i seguenti obiettivi:

-   Convalidare le modifiche consigliate nelle impostazioni di protezione per i tre livelli di protezione definiti nella guida. Tra le ragioni che giustificano queste modifiche risultano:

    -   Modifiche causate dal rilascio di SP1 per Windows* *Server* *2003.

    -   Utilizzo del nuovo strumento Configurazione guidata impostazioni di protezione sicurezza (SCW) messo a disposizione da SP1 e delle nuove funzionalità come il Windows Firewall.

    -   Feedback interno ed esterno ricevuto per la versione precedente della guida.

-   Verificare che le modifiche delle impostazioni di protezione e di configurazione consigliate nella Guida siano conformi ai requisiti degli ambienti LC, EC e SSLF.

-   Verificare che i server membri del dominio con protezione avanzata siano in grado di eseguire correttamente gli incarichi propri dei rispettivi ruoli.

-   Verificare che la comunicazione tra i computer client e i controller di dominio non sia compromessa.

-   Verificare che tutte le istruzioni siano chiare, complete e tecnicamente corrette.

E per finire, la Guida deve essere riproducibile e facilmente utilizzabile da parte di un tecnico MSCE (Microsoft Certified Systems Engineer) con due anni di esperienza.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambiente di test

Le reti del laboratorio di test sviluppate per controllare questa Guida sono simili a quelle usate per la versione precedente. Sono state sviluppate tre reti distinte ma simili, una per ciascun ambiente definito.

Ogni rete di test era composta da un insieme di strutture per il servizio directory Active Directory con Windows* * Server* *2003 con SP1, computer per i ruoli di server di infrastruttura che fornivano il controller di dominio, servizi DNS, VINCE e DHCP e altri computer per i ruoli di server delle applicazioni che fornivano file, stampa e servizi Web. La rete EC comprendeva anche computer per Servizi certificati e i ruoli di server IAS mentre il ruolo di server host Bastion (BH) faceva parte della rete SSLF. Inoltre, le reti EC e SSLF comprendevano Microsoft Operations Manager (MOM) 2005 e Systems Management Server (SMS) 2003 per gestire e controllare i server membro di dominio e i computer client. Queste reti comprendevano anche il Microsoft Exchange* *Server 2003 per il servizio di posta elettronica.

I computer client nelle diverse reti utilizzavano Windows XP Professional con SP2 e Windows 2000 Professional con SP4. La rete LC comprendeva anche i computer client con sistemi operativi Windows 98 SR2 e Windows NT 4.0 workstation con SP6a.

Il seguente schema illustra la rete del laboratorio di test sviluppata per l'ambiente EC.

[![](images/Cc163106.apdxd_fg01(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163106.apdxd_fg01_big(it-it,technet.10).gif)

**Figura D.1 Diagramma logico della rete del laboratorio di test per l'ambiente EC**

Per verificare la replica delle informazioni tra i controller di dominio con protezione aumentata, l'insieme di strutture di Active Directory era composto da due siti. Un sito era quello dell'ufficio principale con un dominio principale vuoto e un dominio figlio composto dal server menzionato in precedenza e dai computer client. Il secondo sito era semplicemente composto da un unico secondo controller di dominio del dominio figlio.

Il seguente schema illustra la rete del laboratorio di test sviluppata per l'ambiente SSLF.

[![](images/Cc163106.apdxd_fg02(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc163106.apdxd_fg02_big(it-it,technet.10).gif)

**Figura D.2 Diagramma logico della rete del laboratorio di test per l'ambiente EC**

[](#mainsection)[Inizio pagina](#mainsection)

### Verifica della metodologia

Questo capitolo descrive le procedure implementate per verificare la *Guida per la protezione di Windows Server 2003.*

Il team addetto ai test ha messo a punto un laboratorio di test che incorporava le tre reti descritte nella sezione precedente. È stata eseguita una veloce verifica funzionale (POC) seguita da due cicli di test più vigorosi. Dopo ogni verifica superata con successo, il team ha cercato di stabilizzare la soluzione.

Per ciclo di test si intende una sequenza delle fasi descritte di seguito:

1.  Fase di creazione della configurazione della protezione

    -   Fase di configurazione manuale

    -   Fase di configurazione dei Criteri di gruppo

2.  Fase di verifica dell'esecuzione

I dettagli di ogni fase sono forniti nella seguente sezione "Fasi nel superamento di una prova". La sezione "Fase di preparazione del test" descrive i punti eseguiti per garantire che l'ambiente del laboratorio fosse privo di qualsiasi problema che avrebbe potuto causare un'interpretazione erronea dei risultati di test reali dopo l'aumento della protezione dei tre ambienti durante le prime due fasi di creazione incrementali. Viene anche denominato stato "baseline".

#### Fasi nel superamento di un test

Le fasi di superamento di un test sono descritte nelle seguenti sottosezioni. Qualunque problema importante sorto durante la fase di creazione è stato documentato come errore e risolto in quella fase prima che il team di test passasse alla fase successiva del test. Questo metodo ha garantito l'implementazione nella rete della corretta configurazione di protezione e ha convalidato la precisione dei risultati dei test eseguiti.

##### Fase di preparazione del test

In questa fase si prepara la configurazione di base alla quale viene applicata la soluzione durante la fase di creazione della configurazione della protezione. Per ciascuno dei tre ambienti LC, EC e SSLF sono state eseguite le seguenti fasi:

**Completamento della fase di preparazione dei test**

1.  Collegare in rete i computer come illustrato nel diagramma di rete e installare le corrette versioni del sistema operativo di Windows su tutti i computer server e client.

2.  Creare e configurare il dominio, i controller di dominio e i due siti.

3.  Aggiungere e configurare ogni server membro e i server di gestione. Aggiungere anche i computer client al dominio.

4.  Eseguire i test di verifica fondamentali per ogni ruolo di server per confermare la corretta configurazione di rete e dell'applicazione.

5.  Controllare il registro eventi di ogni server membro nella rete per accertarsi che non vi siano errori a livello di applicazione o sistema.

6.  Verificare l'accessibilità del computer client ai servizi forniti dal controller di dominio e dai server membro (DNS, DHCP, CA, file, stampa, Web e posta elettronica). Controllare i registri di evento sui computer client per verificare che non ci siano errori.

7.  Verificare che tutte le applicazioni, i servizi e gli agenti richiesti siano installati su ogni membro di dominio. Verificare ad esempio che l'agente MOM sia installato su tutti i server che saranno gestiti dal server MOM.

8.  Dopo aver completato le fasi precedenti, creare una copia dell'immagine di ogni computer. Queste copie delle immagini sono utilizzate per ripristinare la rete alla configurazione di base prima di iniziare il superamento di un nuovo test.

##### Fase di creazione della configurazione della protezione

L'obiettivo di questa fase era quello di seguire le procedure nella guida per configurare il dominio, i controller di dominio e i server membri a un livello più sicuro di quello della configurazione di base.

###### Fase di configurazione manuale

Questa fase è spesso la prima nella creazione della protezione. I consigli per la protezione avanzata manuale contenuti in ogni capitolo sono stati implementati in questa fase.

**Nota**: alcune di queste fasi possono essere valide per la rete in oggetto e altre no. Riesaminare attentamente ogni procedura per capirne l'impatto sulla rete in oggetto.

**Esecuzione della fase di configurazione manuale**

1.  Utilizzare lo Snap-in MMC (Microsoft Management Console) di gestione del computer per eseguire le modifiche dell'impostazione del criterio prescritto (come l'account di amministratore locale e la password) su ogni computer membro. Completare i seguenti punti per proteggere gli account di dominio:

    1.  Accertarsi che l'account Amministratore locale incorporato abbia una password complicata, che sia stato rinominato e che la descrizione predefinita sia stata eliminata.

    2.  Rinominare gli account Guest sull'host e disabilitarli.

    3.  Incorporare qualsiasi consiglio supplementare contenuto in questa guida su come meglio proteggere gli account di dominio.

2.  Aggiungere qualsiasi gruppo o account di protezione esclusivo alle impostazioni dei diritti utente come descritto nei capitoli.

3.  Eseguire tutte le altre procedure manuali per la protezione avanzata come indicato in ogni capitolo. Per esempio, abilitare la configurazione degli scaricamenti della memoria manuali e della segnalazione degli errori.

###### Fase di configurazione dei Criteri di gruppo

Lo scopo di questa fase è quello di creare e applicare gli oggetti Criteri di Gruppo (GPO) a livello di dominio e di unità organizzativa (OU). I GPO sono applicati a OU diverse in base ai consigli nel Capitolo 2, "Meccanismi di protezione avanzata di Windows* *Server* *2003".

Il Service Pack 1 per Windows Server 2003 ha introdotto alcuni nuovi strumenti e funzionalità che hanno richiesto la modifica del progetto di implementazione dei Criteri di gruppo rispetto alla versione precedente.

SCW è uno strumento di riduzione della superficie esposta agli attacchi utilizzato per creare la serie richiesta di criteri di protezione per ciascuno dei ruoli di server discussi in questa guida. La disponibilità di SCW ha causato le due importanti modifiche esposte di seguito per la Fase di configurazione dei criteri di gruppo:

-   I filtri IPsec forniti con la precedente versione di questa guida sono stati sostituiti dalle configurazioni della porta di Windows Firewall che erano state create con SCW.

-   I modelli di protezione contenuti nella guida devono essere utilizzati unitamente a SCW per creare i file del modello di protezione di XML. Questi modelli sono poi convertiti nei GPO corrispondenti utilizzando lo strumento della riga di comando Scwcmd.

Le seguenti fasi sono state ripetute per ciascuno dei tre ambienti di protezione:

**Creazione degli oggetti Criteri di Gruppo**

1.  Verificare che tutte le applicazioni, i servizi e gli agenti richiesti siano installati su ogni membro di dominio nella rete di base. Per esempio, accertarsi che l'agente MOM sia stato installato su tutti i server membro di dominio che saranno gestiti da MOM.

2.  Utilizzare lo Snap-in Utenti e computer di Active* *Directory per creare la struttura OU descritta.

3.  Creare il GPO dei Criteri di dominio con il modello di protezione .inf. Questa fase non richiede l'uso di SCW.

4.  Utilizzare lo strumento SCW per creare modelli di protezione XML per ogni ruolo di server descritto nella guida. Le fasi normative sono descritte nel Capitolo 2, "Meccanismi di protezione avanzata di Windows* *S*erver *2003" e in ogni capitolo sul ruolo del server individuale. Quando si esegue questa fase, allegare il modello di protezione .inf pertinente per il ruolo di server. I file del modello sono allegati alla versione scaricabile di questa guida.

5.  Utilizzare lo strumento della riga di comando Scwcmd per convertire i modelli di protezione XML creati nella fase precedente in GPO.

6.  Ripetere la fase 4 sul server host Bastion per creare il modello di protezione XML di host Bastion e poi usare SCW di nuovo per convertirlo e applicarlo al GPO locale.

Dopo aver creato i GPO, paragonare le impostazioni alle istruzioni contenute nei vari capitoli per identificare eventuali configurazioni inesatte.

A questo punto, tutti i server membri di dominio risiedono nell'OU dei computer. Questi server sono poi spostati nelle rispettive OU all'interno dell'unità operativa del server membro.

Il compito successivo (descritto nella seguente procedura) consiste nell'applicare ciascuno di questi GPO alle rispettive OU. Lo strumento Console di gestione dei criteri di gruppo (GPMC) è stato utilizzato per collegare il GPO all'OU. Il GPO del Criterio di controller di dominio è stato collegato per ultimo.

Le seguenti fasi sono state eseguite al fine di completare il resto della fase di creazione della configurazione di protezione:

**Applicazione degli oggetti Criteri di Gruppo**

1.  Collegare il GPO Criteri di dominio all'oggetto di dominio.

    **Nota**: se i collegamenti GPO predefiniti sono già presenti o se ci sono GPO multipli, potrebbe essere necessario aumentare il livello dei collegamenti del GPO nell'elenco di priorità.

2.  Utilizzare lo strumento Console di gestione Criteri di gruppo per collegare il GPO del Criteri di base dei server membro all'OU dei server membro. (È inoltre possibile eseguire questo punto con lo Snap-in MMC Utenti e computer di Active* *Directory.)

3.  Collegare ogni GPO del ruolo di server individuale all'OU del ruolo del server pertinente.

4.  Collegare il GPO dei criteri del controller di dominio all'OU del Controller di dominio.

5.  Per garantire l'applicazione delle impostazioni dei criteri di gruppo più recenti, eseguire **gpudpate /force** al prompt dei comandi su tutti i Controller di dominio. Quindi riavviare tutti i controller di dominio uno alla volta, iniziando da quello del dominio primario. Dar tempo sufficiente ad Active* *Directory per replicare le modifiche tra i siti.

    **Importante**: è molto importante riavviare i controller di dominio dopo aver applicato il GPO dei criteri del controller di dominio. Se non si esegue questo punto, si potrebbero replicare gli errori nella cartella del Servizio Directory o in quella dell'applicazione del Visualizzatore eventi.

6.  Ripetere la fase 5 su tutti i server membri del dominio.

7.  Controllare se il Visualizzatore eventi presenta degli errori. Riesaminare i registri di errore per localizzare i guasti e risolvere qualsiasi problema.

8.  Sul server host Bastion, utilizzare lo strumento SCW per applicare il modello di protezione XML sul GPO locale del server.

###### Verifica dello scaricamento dei Criteri di gruppo sui computer dei server membro

Le procedure precedenti hanno creato i GPO e li hanno applicati alle OU per configurare i computer in quelle stesse OU. Completare i seguenti punti per confermare l'avvenuto scaricamento dei Criteri di gruppo dai Controller di dominio sui computer dei server membro. (Si presume che i computer dei server membro siano stati riavviati dopo il collegamento del GPO all'OU.)

**Verifica dello scaricamento dei Criteri di gruppo su un computer di server membro**

1.  Accedere al computer del server membro.

2.  Fare clic su **Start**, **Esegui**, digitare **rsop.msc** e premere INVIO.

3.  Nella console **Gruppo di criteri risultante**, espandere la **Directory principale** e navigare alla **Configurazione del computer.**

4.  Fare clic con il pulsante destro del mouse su **Configurazione del computer** e quindi su **Proprietà.**

    L'elenco di GPO visualizzerà il pannello **Proprietà di configurazione del computer**. Il GPO che è stato applicato all'OU deve essere disponibile nell'elenco e non ci dovrebbero essere errori.

##### Fase di verifica dell'esecuzione

Questa fase esegue i casi pratici di test che sono stati sviluppati dal team di test. La fase di esecuzione dei test cerca di identificare quanto segue:

-   Potenziali eventi problematici a livello di applicazione, protezione o sistema causati da processi usati per aumentare la protezione del dominio, dei controller di dominio, dei server membro o del server host Bastion.

-   Perdita di disponibilità di un servizio o di funzionalità causata da una modifica alla configurazione di protezione dei server nella rete.

-   Inesattezze tecniche tra ciò che è documentato nei capitoli e l'implementazione fisica nel laboratorio di test.

Il team di test ha eseguito la serie di casi pratici di test riportati nella cartella \\**Windows Server 2003 Security Guide Tools and Templates\\Test Tools**. (Gli strumenti e i modelli sono allegati alla versione scaricabile di questa guida.) Questi test sono stati eseguiti su ciascuna delle tre reti separate ad eccezione di quelli usati per verificare componenti disponibili solo su una rete, come ad esempio i Servizi certificati, disponibili solo nell'ambiente EC. Oltre a questi casi pratici di test, è stata eseguita la verifica manuale in tempi diversi, ad esempio per controllare periodicamente i registri del Visualizzatore eventi o per verificare problematiche specifiche scoperte nella versione precedente della guida. Tutte le problematiche riscontrate sono state registrate in un database e i dati sono stati analizzati e suddivisi in categorie dal team di sviluppo fino allo loro risoluzione.

Nel prossimo capitolo sono contenute ulteriori informazioni sui vari tipi di test eseguiti.

#### Tipi di test

Il team di test ha eseguito i seguenti tipi di test durante le fasi di test per accertarsi che il dominio protetto, i controller di dominio e i server membro non abbiamo subito una perdita notevole di funzionalità. Si potrebbero voler consultare le cartelle di lavoro di Excel nella cartella **\\Windows Server 2003 Security Guide Tools and Templates\\Test Tools** allegate al download di questa guida e che contengono l'elenco completo dei casi pratici di test eseguiti sia per i server autonomi sia per quelli di dominio con Windows Server 2003 con SP1. Inoltre sono stati forniti i dettagli sugli scenari di test, sulle fasi di esecuzione e sui risultati previsti.

Questi test sono stati eseguiti parecchie volte. E, fatto più importante, essi sono stati eseguiti prima e dopo l'implementazione delle impostazioni di protezione descritte in questa guida. Questo metodo ha aiutato il team di test a identificare potenziali errori e qualsiasi variazione nella funzionalità per i ruoli di server elencati.

##### Test lato client

Questi casi pratici di test sono stati eseguiti sui computer client nella rete. Lo scopo principale di questi test era quello di garantire che i servizi di dominio (come l'autenticazione, i diritti di accesso, la risoluzione dei nomi e così via) e i servizi basati sull'applicazione (come file, stampa e Web) siano disponibili sui computer client dopo la protezione avanzata dei server di rete. Per l'ambiente LC, questi test hanno garantito che i computer client che eseguono Windows * *NT* *4,0 SP6a e Windows* *98 fossero in grado di autenticare mediante il dominio Active* *Directory di Windows* *Server* *2003.

##### Test di creazione della documentazione

Questi test confermano che le istruzioni, le procedure e le funzioni documentate nella guida all'implementazione sono esatte, non ambigue e complete. Per questi test non sono stati elencati casi pratici.

##### Verifiche dello script

Alcuni degli scenari di test di client sono stati creati in VBScript. Questi casi pratici si occupano principalmente della funzionalità propria dei computer client di Windows XP che utilizzano servizi di rete come l'accesso di dominio, la modifica di password e l'accesso al server di stampa. I file VBScript per questi casi pratici sono disponibili nella cartella **\\Windows Server 2003 Security Guide Tools and Templates\\Test Tools** allegata alla versione scaricabile di questa guida.

##### Test lato server

Questi casi pratici sono stati sviluppati per verificare la funzionalità e l'effetto delle procedure di costruzione sui Windows* *Server* *2003 con SP1 che erano stati protetti seguendo i consigli contenuti in questa guida. Sono stati verificati tutti i ruoli di server descritti in questa guida. Sono stati verificati anche i ruoli dei server aggiuntivi che erano stati inclusi nella rete di test, come Exchange, MOM e SMS.

#### Criteri di superamento o meno dei test

Prima dell'esecuzione dei test, sono stati definiti i seguenti criteri per garantire la prevenzione dei difetti e la risoluzione degli errori:

-   Tutti i casi pratici devono superare il test ottenendo i risultati previsti descritti nei rispettivi fogli di lavoro individuali.

-   Si ritiene che un caso pratico abbia superato la prova se il risultato ottenuto corrisponde a quello previsto documentato per tale caso. Se il risultato effettivo non corrisponde a quello previsto, si ritiene che il caso pratico non abbia superato la prova e si crea un errore al quale viene assegnato un punteggio in base alla gravità.

-   Se un caso pratico non supera il test, non si presume che le istruzioni per la soluzione fossero necessariamente sbagliate. Per esempio, il mancato superamento del test potrebbe essere stato causato dall'interpretazione erronea della documentazione del prodotto o dal fatto che la documentazione è incompleta o inesatta. Ogni fallimento è stato analizzato per scoprirne la causa in base ai risultati reali e ai risultati descritti nella documentazione del progetto. I fallimenti sono anche stati assegnati ai proprietari dei rispettivi prodotti di Microsoft.

#### Criteri di rilascio

Il criterio principale per il rilascio della *Guida per la protezione di Windows Server 2003* si basava sulla gravità degli errori ancora non risolti. Si sono discusse anche altre problematiche che non erano state evidenziate dagli errori. I criteri per il rilascio sono:

-   Assenza di errori non risolti con livelli di severità 1 e 2.

-   Tutti gli errori non risolti sono stati analizzati e suddivisi in categorie dal team che è a conoscenza del loro impatto.

-   Le guide delle soluzioni sono prive di commenti e segni di revisione.

-   La soluzione permette ai casi pratici di superare i test nel laboratorio di test.

-   Nell'ambito della soluzione, le istruzioni non sono in contraddizione tra di loro.

#### Classificazione degli errori

La scala di severità dell'errore è descritta nella seguente tabella. La scala va da 1 a 4, dove 1 è il livello di errore più grave e 4 quello meno grave.

**Tabella D.1 Classificazione della severità dell'errore**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Severità</th>
<th style="border:1px solid black;" >I tipi più comuni</th>
<th style="border:1px solid black;" >Condizioni necessarie</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">– L'errore impedisce la creazione o ulteriori test<br />
. – L'errore ha causato l'accessibilità non prevista dell'utente.<br />
– I punti descritti nella documentazione non erano chiari.<br />
– I risultati o il comportamento di una funzione o del processo contraddicono i risultati previsti (come documentato nella specifica funzionale.)<br />
– Grave discrepanza tra i file del modello di protezione e la specifica funzionale.</td>
<td style="border:1px solid black;">– La soluzione non funziona.<br />
– L'utente non ha potuto iniziare a usare componenti importanti del computer o della rete.<br />
– L'utente ha accesso a privilegi che non dovrebbero essere consentiti.<br />
– È stato bloccato l'accesso dell'utente a certi server che avrebbero dovuto essere consentiti.<br />
– Non sono stati ottenuti i risultati previsti.<br />
– Non è possibile continuare con i test senza aver prima risolto questi problemi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">2</td>
<td style="border:1px solid black;">– I punti definiti nella guida non sono chiari.<br />
– La funzionalità documentata manca (in questo caso, il test è stato bloccato).<br />
– La documentazione manca o è inadeguata.<br />
– Incoerenze tra i file del modello di protezione e il contenuto nella guida, ma il file del modello di protezione è conforme alle specifiche funzionali.</td>
<td style="border:1px solid black;">– L'utente non è riuscito a trovare una soluzione per ovviare il problema.<br />
– L'utente non è riuscito a pensare facilmente a una soluzione del problema.<br />
– I principali fabbisogni aziendali non sono stati soddisfatti dal computer o dalla rete.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">3</td>
<td style="border:1px solid black;">– Problemi di formato documentati.<br />
– Errori e inesattezze nella documentazione.<br />
– Errori ortografici nel testo.</td>
<td style="border:1px solid black;">– L'utente ha trovato una semplice soluzione per ovviare il problema.<br />
– L'utente ha potuto trovare facilmente una soluzione.<br />
– L'errore non causa esperienze negative agli utenti.<br />
– I principali requisiti aziendali rimangono funzionali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">4</td>
<td style="border:1px solid black;">– Suggerimenti.<br />
– Miglioramenti futuri.</td>
<td style="border:1px solid black;">– Chiaramente non destinati a questa versione.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questa appendice permette a un'organizzazione che utilizza la *Guida per la protezione di Windows Server 2003* di capire le procedure e le fasi adottate per verificare l'implementazione della soluzione in un laboratorio di test. In questa appendice si descrive l'esperienza reale del team di test addetto alla *Guida per la protezione di Windows Server 2003* e si riportano le descrizioni dell'ambiente di test, dei tipi di test, dei criteri di rilascio e dei dettagli della classificazione degli errori.
  
Tutti i casi pratici eseguiti dal team di test hanno superato i test con i risultati previsti. Il team di test ha confermato la disponibilità della funzionalità richiesta dopo aver seguito i consigli contenuti nella *Guida per la protezione di Windows Server 2003* per gli ambienti definiti.
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://go.microsoft.com/fwlink/?linkid=14846)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)
