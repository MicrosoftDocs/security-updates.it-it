---
TOCTitle: 'Guida alla gestione dei rischi di protezione: Capitolo 2: Analisi delle procedure di gestione dei rischi di protezione'
Title: 'Guida alla gestione dei rischi di protezione: Capitolo 2: Analisi delle procedure di gestione dei rischi di protezione'
ms:assetid: 'fbab4700-db53-4bfc-a595-3f5ec41291d7'
ms:contentKeyID: 20213237
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163152(v=TechNet.10)'
---

Guida alla gestione dei rischi di protezione
============================================

### Capitolo 2: Analisi delle procedure di gestione dei rischi di protezione

Pubblicato: 15/10/2004

Il capitolo inizia con un esame dei punti di forza e dei limiti degli approcci alla gestione dei rischi di tipo preventivo e reattivo, per poi passare alla valutazione e al confronto tra i due metodi tradizionali di gestione dei rischi di protezione, ovvero di tipo qualitativo o quantitativo. Il processo di gestione dei rischi di protezione Microsoft viene presentato come metodo alternativo in grado di assicurare il giusto equilibrio tra le due metodologie tradizionali e dimostratosi estremamente efficace in ambito Microsoft.

**Note:** al fine di predisporre una base di partenza per il processo di gestione dei rischi di protezione Microsoft è importante prendere in esame i diversi modi in cui le organizzazioni hanno affrontato la gestione dei rischi di protezione in passato. Questo capitolo potrà essere consultato rapidamente da lettori che possiedono già conoscenze approfondite di questo argomento; si consiglia invece una lettura attenta a chi non ha ancora molta dimestichezza con le questioni relative alla gestione dei rischi o alla protezione.

##### In questa pagina

[](#ecaa)[Approcci alla gestione dei rischi a confronto](#ecaa)
[](#ebaa)[Approcci alla definizione delle priorità dei rischi](#ebaa)
[](#eaaa)[Il processo di gestione dei rischi di protezione Microsoft](#eaaa)

### Approcci alla gestione dei rischi a confronto

Molte organizzazioni vengono introdotte alla gestione dei rischi di protezione in seguito alla necessità di affrontare un problema di protezione di lieve entità. Ad esempio, il computer di un dipendente è stato infettato da un virus e un dirigente dell'ufficio, che ha assunto per l'occasione il ruolo di esperto informatico, deve capire come eliminare il virus senza distruggere il computer o i dati in esso contenuti. Indipendentemente dall'evento iniziale, con l'aumento dei problemi di protezione che producono un impatto sulle attività aziendali, molte organizzazioni affrontano le frustrazioni derivanti dalla necessità di gestire un problema dopo l'altro. Di conseguenza desiderano trovare un'alternativa all'approccio reattivo che consenta innanzitutto di ridurre le probabilità che i problemi di protezione si verifichino. Le organizzazioni che riescono a gestire con efficacia i rischi si evolvono nella direzione di un approccio di tipo preventivo, che tuttavia, come verrà illustrato nel corso di questo capitolo, rappresenta solo un aspetto della soluzione.

#### L'approccio reattivo

Molti professionisti IT sono oggi sottoposti a enormi pressioni: devono completare le attività di loro competenza nel modo più rapido possibile, riducendo al minimo i disagi per gli utenti. Quando si verifica un evento di protezione, molti professionisti IT si accorgono di avere solo il tempo di contenere il problema, capire cosa è successo e ripristinare i sistemi interessati il più tempestivamente possibile. Alcuni tentano di risalire alle cause dell'evento, ma anche questa attività può apparire un lusso a chi dispone di risorse estremamente limitate. Se un approccio di tipo reattivo può risultare una tattica efficace per affrontare i rischi di protezione già divenuti veri e propri problemi, un minimo di rigore nell'applicare tale approccio può contribuire a ottimizzare l'utilizzo delle risorse disponibili all'interno dell'organizzazione.

I problemi di protezione più recenti sono un'ottima base da cui partire per prevedere i problemi futuri ed essere pronti ad affrontarli. In altre parole, un'organizzazione che affronta i problemi di protezione in modo calmo e razionale, determinando al contempo le cause che hanno permesso al problema di verificarsi, sarà in grado di proteggersi meglio dai rischi e rispondere più velocemente a problemi analoghi in futuro.

L'esame approfondito delle risposte ai problemi di protezione esula dagli argomenti trattati in questa guida, tuttavia l'adozione delle sei procedure seguenti durante le attività di risposta ai problemi consente di gestirli in modo rapido ed efficiente:

1.  **Protezione della vita e dell'incolumità delle persone**. Naturalmente questo obiettivo deve sempre avere priorità assoluta. Se, ad esempio, tra i computer interessati vi sono sistemi di sostegno di funzioni vitali, arrestarli potrebbe non essere un'opzione praticabile. In tal caso una possibilità di intervento consiste nell'isolare logicamente i sistemi sulla rete riconfigurando router e switch senza interferire con il funzionamento dei sistemi in questione.

2.  **Contenimento dei danni**. Il contenimento degli effetti negativi prodotti da un attacco consente di limitare eventuali danni ulteriori. È importante proteggere tempestivamente dati, software e hardware. Ridurre al minimo l'interruzione delle risorse di elaborazione è importante, ma mantenere i sistemi in funzione durante un attacco potrebbe comportare problemi più gravi e di maggiore portata a lungo termine. Se, ad esempio, l'ambiente aziendale viene attaccato da un worm, il danno potrebbe essere limitato scollegando tutti i server dalla rete, anche se a volte questa scelta comporta più problemi che vantaggi. È consigliabile prendere una decisione di questo tipo sulla base delle proprie conoscenze della rete e dei computer in uso e solo dopo aver adeguatamente riflettuto. Se si ritiene che l'operazione non produrrà effetti negativi, o che i vantaggi ottenuti risulteranno comunque superiori agli svantaggi, le attività di contenimento devono cominciare al più presto e prevedere in primo luogo la disconnessione dalla rete di tutti i sistemi interessati. Se i danni non possono essere contenuti isolando i server, accertarsi di monitorare attivamente le azioni dell'hacker al fine di porre rimedio ai danni in modo tempestivo. In ogni caso, prima di arrestare i server verificare che tutti i file di registro siano stati salvati al fine di conservare le informazioni in essi contenute come prove dell'attacco che potranno servire all'organizzazione (o ai suoi legali) in un secondo tempo.

3.  **Valutazione dei danni**. Creare immediatamente una copia dei dischi rigidi di tutti i server interessati e conservarla per uso legale. Procedere quindi alla valutazione dei danni. Subito dopo aver completato la procedura di contenimento e aver creato delle copie dei dischi rigidi, determinare tempestivamente l'entità dei danni provocati durante l'attacco. Questa operazione è importante al fine di ripristinare al più presto l'operatività dell'organizzazione conservando al contempo una copia dei dischi rigidi per le successive indagini. Quando non è possibile valutare i danni in modo tempestivo, è opportuno implementare un piano di emergenza per consentire il proseguimento delle attività aziendali e produttive. A questo punto l'organizzazione può decidere di coinvolgere le forze dell'ordine in merito al problema; è tuttavia consigliabile stabilire e mantenere rapporti di collaborazione con le autorità competenti prima del verificarsi di un incidente in modo da sapere chi contattare e conoscere le modalità di collaborazione in caso di problemi gravi. È inoltre necessario informare immediatamente il reparto legale dell'azienda che potrà così determinare se sussistono le condizioni per intentare un'azione legale e rivalersi su qualcuno per i danni subiti.

4.  **Determinazione della causa dei danni**. Per determinare l'origine dell'attacco è necessario capire a quali risorse era diretto e quali vulnerabilità sono state sfruttate per accedere ai computer o interrompere i servizi. Esaminare la configurazione del sistema, il livello di patch, i registri di sistema, i registri di controllo e gli itinerari di controllo sia dei computer colpiti direttamente che delle periferiche di rete che indirizzano il traffico verso di essi. Questi controlli spesso consentono di scoprire il punto di origine dell'attacco all'interno del sistema e di individuare le altre risorse interessate, ma devono essere effettuati sui computer stessi e non sulle copie dei dischi create nel passaggio 3. Tali copie dovranno rimanere intatte per consentire alle forze dell'ordine e ai legali dell'azienda di utilizzarli per risalire ai responsabili dell'attacco. Se è necessario creare una copia di backup dei dischi per effettuare dei test volti a determinare la causa dei danni, creare un'altra copia dei dischi che hanno subito l'attacco e lasciare intatte le unità copiate nel passaggio 3.

5.  **Riparazione dei danni**. Nella maggior parte dei casi, è di fondamentale importanza procedere immediatamente alla riparazione dei danni, in modo da ripristinare quanto prima le attività aziendali e recuperare i dati perduti durante l'attacco. I piani e le procedure di continuità operativa dell'organizzazione devono includere una strategia di ripristino. Il team di risposta ai problemi di protezione deve rendersi disponibile per la gestione del processo di recupero e ripristino o per assistere il team responsabile. Nel corso del ripristino vengono eseguite le procedure di emergenza per limitare l'ulteriore estensione dei danni e isolarli. Prima di rendere perfettamente operativi i computer ripristinati, verificare di aver limitato tutte le vulnerabilità sfruttate durante il problema di protezione per evitare una nuova infezione.

6.  **Analisi della risposta e aggiornamento dei criteri**. Completate le fasi di documentazione e ripristino, è utile procedere a un'analisi completa del processo. Il team individuerà le fasi eseguite con esito positivo e gli errori commessi. Quasi sempre verrà identificata la necessità di modificare alcuni processi in modo da renderli più efficaci per le future evenienze. Il piano di risposta ai problemi di protezione conterrà inevitabilmente dei punti deboli. Lo scopo di questa attività post-attacco è la ricerca di opportunità di miglioramento. Eventuali difetti rilevati costituiscono la base di partenza per un'ulteriore pianificazione della risposta ai problemi di protezione volta a migliorare la gestione dei problemi futuri.

Questa metodologia è illustrata nella figura seguente.

![](images/Cc163152.rmch0201(it-it,TechNet.10).gif)

**Figura 2.1 Processo di risposta ai problemi**

#### L'approccio preventivo

La gestione dei rischi di protezione preventiva offre numerosi vantaggi rispetto all'approccio di tipo reattivo. Anziché aspettare che si verifichi il peggio e rispondere successivamente ai problemi, si riduce innanzitutto la possibilità che i problemi si verifichino. Allo scopo di proteggere le risorse più importanti dell'organizzazione vengono elaborati piani che prevedono l'implementazione di controlli in grado di ridurre il rischio che le vulnerabilità vengano sfruttate dagli hacker o tramite software dannosi o uso inappropriato involontario. La seguente analogia illustra meglio il concetto. L'influenza è una malattia respiratoria mortale che, nei soli Stati Uniti, colpisce ogni anno milioni di persone. Di queste, oltre 100.000 vengono ricoverate negli ospedali e circa 36.000 muoiono in seguito alla malattia. Si potrebbe decidere di affrontare il pericolo dell'influenza curandosi con i farmaci adatti solo dopo essere stati contagiati. In alternativa, si potrebbe scegliere di farsi vaccinare prima che inizi la stagione dell'influenza.

È evidente che le organizzazioni non possono abbandonare completamente le attività di risposta ai problemi. Un approccio preventivo efficace può contribuire a ridurre significativamente il numero di problemi di protezione che si manifesteranno nel futuro, ma non può assicurare la loro completa eliminazione. Le organizzazioni devono perciò continuare a migliorare i loro processi di risposta ai problemi e contemporaneamente sviluppare approcci preventivi a lungo termine.

Nelle sezioni presentate più avanti in questo capitolo e negli altri capitoli della guida verrà esaminata nel dettaglio la gestione dei rischi di protezione di tipo preventivo. Tutte le metodologie di gestione dei rischi hanno in comune alcune procedure di alto livello:

1.  Identificazione dei beni aziendali.

2.  Determinazione del danno causato all'organizzazione da un attacco nei confronti di un bene.

3.  Identificazione delle vulnerabilità che un attacco potrebbe sfruttare.

4.  Determinazione delle modalità di riduzione del rischio di attacco mediante l'implementazione dei controlli appropriati.

[](#mainsection)[Inizio pagina](#mainsection)

### Approcci alla definizione delle priorità dei rischi

Le espressioni *gestione dei rischi* e *valutazione dei rischi* sono frequentemente utilizzate all'interno di questa guida e, seppure correlate, non sono intercambiabili. Il processo di gestione dei rischi di protezione Microsoft definisce la gestione dei rischi come l'insieme delle attività volte a gestire i rischi ad un livello accettabile in tutta l'azienda. Per valutazione dei rischi si intende il processo di identificazione dei rischi aziendali e la definizione delle relative priorità.

Esistono diversi metodi per la definizione delle priorità e la valutazione dei rischi, tuttavia molti di essi sono basati su uno dei due approcci oppure sulla loro combinazione: gestione dei rischi di tipo qualitativo o quantitativo. Per i collegamenti ad altre metodologie di valutazione dei rischi, consultare l'elenco delle risorse all'interno della sezione "Ulteriori informazioni" alla fine del Capitolo 1, "Introduzione alla Guida alla gestione dei rischi di protezione". Le prossime sezioni di questo capitolo presentano un riepilogo della valutazione dei rischi di tipo qualitativo e quantitativo, il confronto tra i due metodi e una breve descrizione del processo di gestione dei rischi di protezione Microsoft che illustra come quest'ultimo combini aspetti di entrambi gli approcci.

#### Valutazione dei rischi quantitativa

Lo scopo di una valutazione dei rischi di tipo quantitativo è cercare di calcolare valori numerici obiettivi per ogni componente rilevato durante la valutazione e l'analisi costi-benefici. Si esegue ad esempio una stima del valore reale di ogni bene aziendale analizzandone il costo in termini di sostituzione del bene, perdita di produttività o reputazione del marchio e altri costi aziendali diretti o indiretti. Si cerca di adottare lo stesso tipo di obiettività quando si valutano l'esposizione del bene, il costo dei controlli e tutti gli altri valori identificati durante il processo di gestione dei rischi.

**Nota**: l'obiettivo di questa sezione è illustrare alcune delle procedure di alto livello previste dalla valutazione quantitativa dei rischi, non quello di fornire istruzioni per l'adozione di questo approccio nei progetti di gestione dei rischi di protezione.

Questo approccio presenta alcuni punti deboli che difficilmente possono essere superati. In primo luogo non esiste un modalità rigorosa e formale per calcolare il valore effettivo di beni e controlli. In altri termini, se apparentemente l'attribuzione di un valore finanziario sembra offrire un maggiore livello di dettaglio e precisione, in realtà nasconde il fatto che i numeri ottenuti sono comunque basati su stime. Come è possibile calcolare con estrema precisione l'impatto che un problema di protezione ampiamente noto al pubblico può avere sulla reputazione di un marchio? Si potrebbero esaminare dati cronologici, ma molto spesso non sono disponibili.

In secondo luogo, le organizzazioni che hanno tentato di applicare in modo meticoloso tutti gli aspetti della gestione quantitativa dei rischi hanno trovato il processo estremamente costoso. Questi progetti implicano solitamente tempi molto lunghi per il completamento del primo ciclo integrale e generalmente coinvolgono gran parte del personale in discussioni incessanti sui dettagli relativi alle diverse modalità di calcolo di valori finanziari specifici. In terzo luogo, per le organizzazioni che possiedono beni di valore elevato, il costo dell'esposizione può risultare talmente elevato che anche il budget destinato alla riduzione dei rischi aumenta in modo esponenziale. Questo scenario è tuttavia poco realistico: nessuna organizzazione spenderebbe mai tutto il suo budget per proteggere uno solo dei suoi beni o anche i suoi cinque beni più importanti.

##### Dettagli dell'approccio quantitativo

A questo punto è utile fornire una panoramica generale dei vantaggi e degli svantaggi della valutazione dei rischi di tipo quantitativo. Il resto della sezione prenderà in esame alcuni dei fattori e dei valori che vengono generalmente presi in considerazione durante una valutazione quantitativa dei rischi, quali la stima dei beni, il costo dei controlli, la determinazione del ritorno sull'investimento nella protezione (ROSI), il calcolo della previsione di perdita singola (SLE), del tasso di occorrenza annuo (ARO) e della previsione di perdita annua (ALE). Non verrà tuttavia fornito un esame completo di tutti gli aspetti della valutazione quantitativa dei rischi; sarà unicamente condotta una breve analisi di alcuni dei dettagli di questo approccio al fine di evidenziare la soggettività dei numeri su cui sono basati tutti i calcoli del processo.

###### Stima dei beni

La determinazione del valore monetario di un bene è una parte importante della gestione dei rischi di protezione. I dirigenti delle aziende spesso si basano sul valore di un bene per determinare quanto tempo e denaro è opportuno spendere per garantirne la protezione. Molte organizzazioni redigono un elenco dei valori dei beni nell'ambito dei loro piani di continuità aziendale. È tuttavia importante osservare come i numeri ottenuti siano stime soggettive: non esistono strumenti o metodi oggettivi per determinare il valore di un bene. Per assegnare un valore a un bene, calcolare i seguenti tre fattori primari:

-   **Il valore complessivo attribuito al bene dall'organizzazione**. Calcolare o stimare il valore del bene in termini direttamente finanziari. Si consideri un esempio semplificato relativo all'impatto di un'interruzione temporanea di un sito Web di e-commerce che in genere funziona sette giorni la settimana, 24 ore al giorno, generando un reddito medio di $2.000 l'ora derivante dagli ordini dei clienti. È possibile affermare che il valore annuo del sito Web in termini di fatturato è pari a $17.520.000.

-   **L'impatto finanziario immediato in caso di perdita del bene**. Semplificando deliberatamente l'esempio e supponendo che il sito generi una percentuale di reddito costante ogni ora e resti inutilizzabile per sei ore, l'esposizione calcolata corrisponde allo 0,000685 percento all'anno. Se si moltiplica tale percentuale di esposizione per il valore annuo del bene, è possibile prevedere che le perdite attribuibili in modo diretto alla mancata operatività del sito corrisponderanno in questo caso a $12.000. In realtà, i siti Web di solito generano un reddito che varia notevolmente in base all'ora del giorno, al giorno della settimana, alla stagione, alle campagne di marketing effettuate e ad altri fattori. Inoltre, alcuni clienti potrebbero trovare un sito Web alternativo che preferiscono al sito originale. In alcuni casi quindi la perdita di utenti è un fenomeno normale. Calcolare la perdita di reddito è un'operazione piuttosto complessa se eseguita in modo preciso, prendendo in considerazione tutte le possibili tipologie.

-   **L'impatto indiretto in caso di perdita del bene**. In questo esempio, l'azienda prevede di dover spendere $10.000 in pubblicità per contrastare la pubblicità negativa derivante da tale incidente. Inoltre l'azienda prevede una perdita pari allo 0,01 percento delle vendite annue, ovvero di $17.520. Sommando le spese pubblicitarie aggiuntive alla perdita di fatturato annuo, è possibile prevedere un totale di $27.520 di perdite indirette.

###### Determinazione della previsione di perdita singola

La previsione di perdita singola è l'importo totale di reddito perduto in seguito a una singola occorrenza del rischio. Si tratta di un importo monetario assegnato a un singolo evento che rappresenta la perdita potenziale per l'azienda nel caso venisse sfruttata una vulnerabilità. La previsione di perdita singola è simile all'impatto di un'analisi qualitativa dei rischi. Determinare la previsione di perdita singola moltiplicando il valore del bene per il fattore di esposizione. Il fattore di esposizione rappresenta la percentuale di perdita relativa a un bene in seguito al verificarsi di un pericolo. Se a una Web farm viene attribuito un valore di $150.000 e un incendio provoca danni pari, secondo una stima, al 25 percento del suo valore, in questo caso la previsione di perdita singola sarà di $37.500. Si tratta, tuttavia, di un esempio molto semplificato; potrebbe essere necessario considerare altre tipologie di spesa.

###### Determinazione del tasso di occorrenza annuo

Il tasso di occorrenza annuo corrisponde al numero di volte per cui è ragionevole attendersi che il rischio si verifichi nel corso di un anno. Questo genere di stima è molto difficile da effettuare in quanto i dati statistici disponibili sono molto scarsi. Le uniche informazioni raccolte fino ad oggi non sono di dominio pubblico essendo di proprietà di alcune compagnie di assicurazione di beni immobili. Per stimare il tasso di occorrenza annuo, è possibile basarsi sulle esperienze passate e consultare esperti di gestione dei rischi di protezione e consulenti aziendali. Il tasso di occorrenza annuo è simile alla probabilità di un'analisi qualitativa dei rischi e presenta una gamma di valori che si estende dallo 0% (mai) al 100% (sempre).

###### Determinazione della previsione di perdita annua

La previsione di perdita annua corrisponde all'importo monetario totale che l'organizzazione perderà in un anno se non viene presa alcuna iniziativa per ridurre il rischio. Calcolare tale valore moltiplicando la previsione di perdita singola per il tasso di occorrenza annuo. La previsione di perdita annua è simile alla classificazione relativa di un'analisi qualitativa del rischio.

Ad esempio, se un incendio presso la stessa Web farm dell'azienda provoca $37.500 di danni e la probabilità, o tasso di occorrenza annuo, di un incendio è pari a 0,1 (a indicare una volta ogni dieci anni), allora il valore della previsione di perdita annua in questo caso sarà di $3.750 ($37.500 x 0,1 = $3.750).

La previsione di perdita annua è un valore che l'organizzazione può utilizzare per definire il budget per l'istituzione di controlli o misure di protezione atte a evitare che si verifichino danni di questo tipo (in questo caso $3.750 o meno all'anno) e per assicurare un livello di protezione adeguato. Per definire la cifra da investire per proteggere l'ambiente dai pericoli potenziali, è importante quantificare le reali possibilità di rischio e i danni, in termini monetari, che potrebbero derivarne.

###### Determinazione del costo dei controlli

La determinazione del costo dei controlli richiede una stima accurata dei costi di acquisizione, collaudo, distribuzione, funzionamento e mantenimento di ogni singolo controllo. I costi da calcolare includono l'acquisto o lo sviluppo della soluzione di controllo, la sua distribuzione, configurazione e manutenzione, la comunicazione agli utenti di nuovi criteri o procedure relativi al nuovo controllo, la formazione degli utenti e del personale IT sulle procedure da seguire per utilizzare e supportare la soluzione di controllo, il monitoraggio del controllo e le misure atte a contrastare la perdita di comodità d'uso o di produttività che l'adozione del controllo potrebbe determinare. Ad esempio, per ridurre il rischio di danni da incendi per la Web farm, l'organizzazione dell'esempio precedente potrebbe prendere in considerazione la distribuzione di un sistema automatizzato di estintori. Questo richiederebbe l'affidamento della progettazione e installazione del sistema a una società esterna, che dovrebbe in seguito continuare a monitorare il suo corretto funzionamento nonché eseguire verifiche periodiche e, occasionalmente, provvedere al rifornimento delle sostanze chimiche utilizzate.

###### Ritorno sull'investimento nella protezione (ROSI)

Stimare il costo dei controlli utilizzando la seguente equazione:

(previsione di perdita annua prima del controllo) – (previsione di perdita annua dopo il controllo) – (costo annuo del controllo) = ROSI

Ad esempio, la previsione di perdita annua derivante dal pericolo di un attacco a un server Web è di $12.000 e dopo l'implementazione della contromisura proposta è pari a $3.000. Il costo annuo sostenuto per il funzionamento e la manutenzione della contromisura di protezione è di $650, perciò il ROSI risulta essere di $8.350 l'anno e si ottiene con la seguente equazione: $12.000 - $3.000 - $650 = $8.350.

###### Risultati dell'analisi quantitativa dei rischi

Gli elementi di input che derivano dall'analisi quantitativa del rischio forniscono obiettivi e risultati ben definiti. In genere i risultati delle procedure precedenti permettono di conoscere quanto segue:

-   Valori monetari assegnati ai beni

-   Elenco completo dei pericoli significativi

-   Probabilità che si realizzi ciascun pericolo

-   Perdita potenziale per l'azienda per ciascun pericolo nei 12 mesi

-   Contromisure, controlli e azioni consigliate

A questo punto risulta evidente che tutti i calcoli sopra indicati sono basati su stime soggettive. Le cifre fondamentali alla base dei risultati ottenuti non derivano infatti da equazioni oggettive o insiemi di dati statistici, ma sono prodotte sulla base delle opinioni di coloro che eseguono la valutazione. Il valore dei beni, le previsioni di perdita singola, i tassi di occorrenza annui e il costo dei controlli sono tutti numeri definiti dai partecipanti al processo (generalmente ottenuti dopo molti compromessi e lunghe discussioni).

#### Valutazione qualitativa dei rischi

Il principale elemento che differenzia la valutazione qualitativa dei rischi da quella di tipo quantitativo è che la prima non richiede l'assegnazione di valori finanziari fissi ai beni, alle perdite stimate e al costo dei controlli, ma prevede invece il calcolo di valori relativi. L'analisi dei rischi implica di solito l'utilizzo di una combinazione di questionari e workshop aperti che coinvolgono gruppi diversificati di persone che operano all'interno dell'organizzazione, come gli esperti della protezione delle informazioni, i responsabili e il personale IT, i proprietari e gli utenti dei beni aziendali e i dirigenti di alto livello. Se utilizzati, i questionari vengono generalmente distribuiti da alcuni giorni ad alcune settimane prima del workshop iniziale. I questionari consentono di raccogliere informazioni, che si riveleranno estremamente utili durante il workshop, su beni e controlli esistenti. Nel corso del workshop, i partecipanti procederanno all'identificazione dei beni e alla stima dei loro valori relativi. Successivamente cercheranno di capire a quali rischi potrebbero essere esposti i diversi beni e di identificare quali tipi di vulnerabilità potrebbero venire sfruttate da attacchi futuri. A questo punto di solito gli esperti della protezione delle informazioni e gli amministratori di sistema sottopongono alla valutazione dei partecipanti una serie di controlli per la riduzione dei rischi e le informazioni relative al costo approssimato di ogni controllo. I risultati ottenuti vengono infine presentati alla direzione aziendale che li sottoporrà a un'analisi costi-benefici.

È dunque evidente che il processo alla base delle valutazioni qualitative è molto simile a quello previsto dall'approccio quantitativo. La differenza sta nei dettagli. I confronti tra il valore di due beni sono relativi e i partecipanti non trascorrono molto tempo a tentare di attribuire ai beni una valutazione finanziaria precisa. La stessa differenza tra i due approcci emerge anche quando si passa a calcolare il possibile impatto determinato dal verificarsi di un rischio e il costo per l'implementazione dei controlli.

L'approccio qualitativo offre infatti il vantaggio di non richiedere il calcolo preciso del valore dei beni, del costo dei controlli, e così via. Il processo risulta perciò molto meno impegnativo per il personale coinvolto. I progetti di gestione qualitativa dei rischi iniziano generalmente a dare i primi risultati significativi dopo alcune settimane dal loro avvio, mentre molte organizzazioni che scelgono l'approccio quantitativo devono aspettare mesi, e a volte anche anni, prima di vedere qualche risultato apprezzabile. Lo svantaggio dell'approccio qualitativo è che le cifre ottenute sono vaghe e per alcuni responsabili dei processi decisionali aziendali, in particolare quelli con competenze finanziarie o amministrative, è difficile accettare il fatto che il progetto di valutazione dei rischi è fondamentalmente basato su valori puramente relativi.

#### I due approcci a confronto

Entrambi gli approcci alla gestione dei rischi di protezione presentano vantaggi e svantaggi specifici. Se in alcune situazioni può essere opportuno adottare l'approccio quantitativo, le organizzazioni di dimensioni ridotte o con risorse limitate probabilmente preferiranno l'approccio qualitativo. Nella tabella seguente sono riepilogati i vantaggi e gli svantaggi offerti da entrambi gli approcci:

**Tabella 2.1: Vantaggi e svantaggi dei due diversi approcci alla gestione dei rischi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" > </th>
<th style="border:1px solid black;" >Approccio quantitativo</th>
<th style="border:1px solid black;" >Approccio qualitativo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Vantaggi</strong></td>
<td style="border:1px solid black;">– Le priorità dei rischi vengono definite in base all'impatto finanziario; le priorità dei beni vengono definite in base al valore finanziario.
– I risultati facilitano la gestione dei rischi in base al ritorno sull'investimento nella protezione (ROSI).
– I risultati possono essere espressi con la terminologia gestionale (ad es. valori monetari e probabilità sono espressi come percentuali specifiche).
– La precisione del processo aumenta nel tempo, man mano che l'organizzazione raccoglie dati cronologici basati sulle passate esperienze.</td>
<td style="border:1px solid black;">– Permette una maggiore visibilità e comprensione della classificazione dei rischi.
– Semplifica il raggiungimento del consenso sulle decisioni.
– Non è necessario quantificare la frequenza dei pericoli.
– Non è necessario determinare il valore finanziario dei beni.
– Semplifica il coinvolgimento di personale non esperto in materia di protezione o informatica.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Svantaggi</strong></td>
<td style="border:1px solid black;">– I valori di impatto assegnati ai rischi sono basati sulle opinioni soggettive dei partecipanti.
– Il processo richiesto per raggiungere il consenso e risultati credibili è estremamente lungo.
– I calcoli richiesti possono essere complessi e richiedere molto tempo.
– I risultati sono presentati esclusivamente in termini monetari e possono risultare di difficile comprensione per i partecipanti non esperti in materia.
– Il processo presuppone un alto grado di esperienza ed è perciò difficile fornire una guida adeguata ai partecipanti</td>
<td style="border:1px solid black;">– La differenziazione tra i principali rischi risulta insufficiente.
– È difficile giustificare l'investimento nell'implementazione dei controlli in quanto non esiste una base per l'analisi costi-benefici.
– I risultati dipendono dalla qualità del team di gestione dei rischi di protezione.</td>
</tr>
</tbody>
</table>
 

Nel passato, l'approccio alla gestione dei rischi di protezione di tipo quantitativo era decisamente predominante; recentemente la situazione è cambiata e sono sempre più numerosi i professionisti che ammettono che attenersi rigidamente alle procedure previste dalla gestione quantitativa comporta progetti di lunga durata e difficili da gestire che producono pochi vantaggi tangibili. Come verrà illustrato nei capitoli seguenti, il processo di gestione dei rischi di protezione Microsoft combina il meglio di entrambe le metodologie in un unico approccio di tipo ibrido.

[](#mainsection)[Inizio pagina](#mainsection)

### Il processo di gestione dei rischi di protezione Microsoft

Il processo di gestione dei rischi di protezione Microsoft è un approccio ibrido che combina al suo interno gli elementi più validi dei due metodi tradizionali. Come verrà spiegato più nel dettaglio nei capitoli seguenti, l'esclusivo approccio alla gestione dei rischi di protezione offerto da questa guida è notevolmente più veloce rispetto al tradizionale metodo quantitativo e tuttavia offre risultati più dettagliati e più facilmente sottoscritti da parte dei dirigenti rispetto al tipico approccio qualitativo. Dalla combinazione dell'immediatezza e chiarezza dell'approccio qualitativo con il rigore dell'approccio quantitativo nasce l'esclusivo processo di gestione dei rischi di protezione proposto in questa guida e caratterizzato da efficacia e semplicità d'uso. L'obiettivo del processo è consentire alle persone interessate di comprendere le diverse procedure previste dalla valutazione. Si tratta dunque di un approccio decisamente più semplice rispetto a quello di tipo quantitativo, che riduce al minimo le resistenze ai risultati delle fasi di analisi dei rischi e di supporto alle decisioni e consente perciò di raggiungere e mantenere per tutta la durata del processo un consenso più ampio e in tempi più brevi.

Il processo di gestione dei rischi di protezione Microsoft si articola in quattro fasi. La prima è la fase di valutazione dei rischi che prevede aspetti propri di entrambe le metodologie quantitativa e qualitativa. Un approccio qualitativo offre gli strumenti per una rapida classificazione di tutti i rischi di protezione esistenti. I rischi più gravi così identificati vengono quindi esaminati più in dettaglio mediante l'approccio quantitativo, fino a ottenere un elenco più breve contenente solo i rischi principali corredati di informazioni dettagliate.

Nel corso della fase successiva di supporto alle decisioni, vengono proposte e valutate le potenziali soluzioni di controllo dei rischi contenuti nell'elenco più breve, quindi le soluzioni migliori vengono sottoposte al Comitato direttivo per la protezione dell'organizzazione in forma di raccomandazioni per la riduzione dei principali rischi. Durante la terza fase di implementazione dei controlli, i responsabili della riduzione dei rischi procedono all'attuazione delle soluzioni di controllo. La quarta e ultima fase di misurazione dell'efficacia del programma viene utilizzata per verificare che i controlli stiano effettivamente generando il livello di protezione previsto e per rilevare eventuali cambiamenti nell'ambiente, come applicazioni o strumenti di attacco nuovi che possono modificare il profilo di rischio dell'organizzazione.

Poiché la gestione dei rischi di protezione Microsoft è un processo continuo, il ciclo ricomincia dall'inizio ad ogni valutazione di un nuovo rischio. La frequenza di ripetizione del ciclo varia da un'organizzazione all'altra; molte aziende ritengono sufficienti cicli di durata annuale purché vulnerabilità, rischi e beni vengano sottoposti a monitoraggio preventivo.

![](images/Cc163152.rmch0202(it-it,TechNet.10).gif)

**Figura 2.2 Fasi del processo di gestione dei rischi di protezione Microsoft**

Nella Figura 2.2 qui sopra vengono illustrate le quattro fasi del processo di gestione dei rischi di protezione Microsoft. Nel Capitolo 3, "Panoramica della gestione dei rischi di protezione", viene fornita una descrizione globale del processo. Nei capitoli seguenti verranno spiegate nel dettaglio le diverse procedure e attività associate a ognuna delle singole fasi del processo.

[](#mainsection)[Inizio pagina](#mainsection)
