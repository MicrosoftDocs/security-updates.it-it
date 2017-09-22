---
TOCTitle: Protezione degli addetti ai lavori dalle minacce del social engineering
Title: Protezione degli addetti ai lavori dalle minacce del social engineering
ms:assetid: '2c21c5d6-325c-4eb9-b3be-873915701f6d'
ms:contentKeyID: 20213231
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc875841(v=TechNet.10)'
---

Come proteggere gli addetti ai lavori dalle minacce del social engineering
==========================================================================

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Minacce del social engineering e relative difese](#eeaa)
[](#edaa)[Progettazione delle difese contro le minacce del social engineering](#edaa)
[](#ecaa)[Implementazione delle difese contro le minacce del social engineering](#ecaa)
[](#ebaa)[Appendice 1: Elenchi di controllo dei criteri di protezione contro le minacce del social engineering](#ebaa)
[](#eaaa)[Appendice 2: Glossario](#eaaa)

### Introduzione

Questo documento è contenuto nella raccolta di indicazioni per la protezione delle aziende di medie dimensioni. Microsoft si augura che le informazioni seguenti possano agevolare la creazione di un ambiente IT più sicuro e maggiormente produttivo.

#### Destinatari del documento

Questo documento fornisce informazioni sulla gestione della protezione dalle minacce derivanti dal social engineering e sulle difese disponibili per resistere a questo tipo di attacchi. Il social engineering definisce essenzialmente minacce non tecniche alla sicurezza aziendale. L'ampia natura di queste potenziali minacce richiede che vengano fornite informazioni sulle minacce e sulle potenziali difese a una serie di membri del personale di gestione e tecnico di un'azienda, inclusi:

-   I dirigenti del consiglio di amministrazione

-   I responsabili delle operazioni tecniche e dei servizi

-   Il personale di supporto

-   Il personale addetto alla sicurezza

-   I dirigenti aziendali

#### panoramica

Per attaccare un'organizzazione, i pirati informatici dediti al social engineering sfruttano la credulità, la pigrizia, le buone maniere e perfino l'entusiasmo del personale aziendale. Quindi è difficile difendersi da un attacco di social engineering poiché le vittime potrebbero non rendersi conto di essere state ingannate o potrebbero preferire non ammetterlo davanti ad altre persone. Gli obiettivi di un pirata informatico dedito al social engineering, ovvero una persona che tenta di accedere senza autorizzazione ai sistemi informatici sono simili a quelli di qualsiasi altro pirata informatico: ottenere il denaro, le informazioni e le risorse IT dell'azienda attaccata.

Un pirata informatico che svolge un attacco di social engineering tenta di persuadere il personale aziendale a fornire informazioni grazie alle quali potrà utilizzare i sistemi o le risorse di sistema dell'azienda. Questo approccio è tradizionalmente noto come *truffa all'americana*. Molte aziende di piccole e medie dimensioni ritengono che gli attacchi dei pirati informatici siano un problema delle grandi multinazionali e organizzazioni poiché possono offrire gratificazioni finanziarie maggiori. Sebbene questo possa essere stato vero nel passato, l'aumento dei reati cibernetici fa comprendere che, oggi, i pirati informatici mirano a qualsiasi settore della comunità, dalle multinazionali, alle singole persone. I criminali possono derubare direttamente un'azienda, spostando fondi o risorse, ma possono anche utilizzare un'azienda come punto di attestamento dal quale perpetrare crimini contro altre persone. Davanti a un approccio simile, le autorità hanno maggiori difficoltà a risalire ai colpevoli.

Per proteggere il personale dagli attacchi di social engineering, è necessario sapere cosa aspettarsi, comprendere cosa vuole ottenere il pirata informatico e valutare il valore delle perdite per l'organizzazione. Disponendo di queste informazioni, è possibile aumentare l'efficacia dei criteri di protezione includendo anche le difese contro il social engineering. Questo documento presuppone che l'azienda abbia dei criteri di protezione che stabiliscono gli obiettivi, le pratiche e le procedure riconosciute, necessari per proteggere le risorse, i beni informativi e il personale dagli attacchi tecnologici e fisici. Le modifiche ai criteri di protezione permetteranno di fornire ai dipendenti delle informazioni su come reagire di fronte a una persona o a un'applicazione del computer che tenta di forzarli o persuaderli a esporre le risorse aziendali o a divulgare informazioni sulla sicurezza.

[](#mainsection)[Inizio pagina](#mainsection)

### Minacce del social engineering e relative difese

Il pirata informatico che realizza un attacco di social engineering si avvale di cinque principali vettori:

-   Internet

-   Telefono

-   Gestione dei rifiuti

-   Approcci personali

-   Reverse social engineering

Oltre a riconoscere i suddetti punti di ingresso, è necessario anche sapere cosa sperano di ottenere i pirati informatici. I loro obiettivi mirano al raggiungimento di elementi importanti per tutti, ovvero il denaro, l'avanzamento sociale e l'autostima. I pirati informatici desiderano impossessarsi del denaro e delle risorse altrui ed essere riconosciuti all'interno della società o del proprio gruppo di colleghi, in sostanza sentirsi importanti Sfortunatamente, questi obiettivi vengono raggiunti illegalmente tramite furti o danni ai sistemi informatici. Qualsiasi genere di attacco ha conseguenze costose poiché comporta perdite di denaro, di reddito, di risorse, di informazioni, di disponibilità o credibilità aziendale. Quando si progettano le difese contro tali minacce è importante valutare i costi di un eventuale attacco.

#### Minacce online

Nel mondo aziendale odierno, sempre più collegato in rete, il personale spesso risponde per via elettronica alle richieste e utilizza informazioni provenienti dall'interno e dall'esterno dell'azienda. Tale connettività permette ai pirati informatici di avvicinarsi al personale aziendale dalla relativa anonimità di Internet. Spesso la stampa diffonde notizie di attacchi online effettuati tramite posta elettronica, applicazioni popup e messaggistica immediata e che lanciano Trojan horse, worm e virus, denominati collettivamente *malware*, allo scopo di danneggiare o violare le risorse informatiche. Implementando delle potenti difese antivirus è possibile contrapporsi agli attacchi del malware.

**Nota**   Per ulteriori informazioni sulle difese antivirus, consultare la [*Guida alla difesa antivirus a più livelli*](http://go.microsoft.com/fwlink/?linkid=28732) all'indirizzo: http://go.microsoft.com/fwlink/?linkid=28732.

Il pirata informatico dedito al social engineering potrebbe persuadere un membro del personale a fornire informazioni avvalendosi di uno stratagemma oppure potrebbe infettare un computer con malware mediante un attacco diretto. Un attacco può fornire al pirata informatico delle informazioni che potranno consentire un ulteriore attacco con malware, tuttavia questo risultato non appartiene al social engineering. È quindi importante suggerire al personale il modo migliore per identificare ed evitare gli attacchi online di social engineering.

##### Minacce tramite posta elettronica

Molti membri del personale ricevono decine o centinaia di messaggi di posta elettronica ogni giorno, sia dai sistemi di posta aziendali che dai sistemi privati. Diventa difficile prestare la massima attenzione a ogni messaggio a causa del volume dei messaggi di posta elettronica. Questo fatto facilita invece l'intervento di un pirata informatico dedito al social engineering. Nella maggior parte dei casi, gli utenti di posta elettronica sono contenti di gestire la corrispondenza, che è l'equivalente elettronico di spostare fogli di carta dalla cassetta della corrispondenza in entrata e in uscita. Se il pirata informatico è in grado di fare una semplice richiesta che sia facile da accontentare, la vittima soddisferà tale richiesta senza neanche pensare a cosa sta facendo.

Per fare un esempio, un attacco molto semplice potrebbe essere l'invio di un messaggio di posta elettronica a un membro del personale in cui si affermi che il capo desidera ricevere la pianificazione completa delle ferie in occasione di una riunione e vuole che i nomi presenti nella lista vengano copiati nel messaggio. È facile fare scivolare un nome esterno nella lista copiata e falsificare (*spoofing)* il nome del mittente in modo tale che il messaggio sembri provenire da una fonte interna. Questa truffa viene definita "spoofing" ed è particolarmente semplice se il pirata informatico riesce ad accedere a un computer aziendale, poiché questo non comporta la violazione dei firewall perimetrali. Conoscere la pianificazione delle ferie di un reparto potrebbe non sembrare una reale minaccia alla sicurezza, significa però che il pirata informatico sa quando un membro del personale è assente. Il pirata informatico può impersonare il dipendente in ferie correndo minori rischi di essere scoperto.

Negli ultimi dieci anni, l'uso della posta elettronica come strumento di social engineering è diventato endemico. Il *phishing* implica l'uso della posta elettronica per ottenere da un utente informazioni personali identificabili o riservate. Ad esempio i pirati informatici possono inviare dei messaggi di posta elettronica che sembrano provenire da organizzazioni valide, quali banche o aziende partner.

La figura seguente mostra un collegamento apparentemente valido al sito di gestione degli account di Contoso.

![](images/Cc875841.HPISET01(it-it,TechNet.10).gif)

**Figura 1. Collegamento ipertestuale di messaggi di phishing**

Tuttavia, guardando più attentamente è possibile individuare due differenze:

-   Il testo contenuto nel messaggio di posta elettronica indica che il sito è sicuro, utilizzando il protocollo HTTPS, anche se il suggerimento a schermo indica che il sito si avvale del protocollo HTTP.

-   Il nome dell'azienda contenuto nel messaggio è "Contoso", tuttavia il collegamento conduce a un'azienda denominata "Comtoso".

Come indica il termine phishing (fare abboccare un pesce all'esca) tali approcci sono solitamente speculativi e contengono una richiesta generica di informazioni per un cliente. La mimetizzazione realistica utilizzata nei messaggi di posta elettronica, i loghi e caratteri aziendali e perfino numeri di telefono gratuiti dell'assistenza che sembrano veri, rendono il messaggio più credibile. All'interno di ogni messaggio di phishing è contenuta una richiesta di informazioni sull'utente, spesso mirata ad agevolare un aggiornamento o la prestazione di un servizio aggiuntivo. Esiste inoltre lo *spear-phishing*, un'estensione del pishing, in cui l'attacco è diretto a un obiettivo o un gruppo specifico all'interno di un reparto. Si tratta di un approccio molto più sofisticato, poiché le informazioni personali e relative all'azienda sono fondamentali per rendere credibile l'inganno. Per realizzare un attacco di questo tipo è necessario avere una maggiore conoscenza dell'obiettivo, ma le informazioni ottenute saranno più specifiche e dettagliate.

Anche in questo caso il messaggio di posta elettronica può contenere collegamenti ipertestuali che possono tentare un membro del personale a violare la protezione aziendale. Come indicato nella Figura 1, i collegamenti non conducono sempre l'utente nel luogo previsto o promesso. Esiste una serie di altre opzioni che il pirata informatico utilizza in un messaggio di phishing, incluse le immagini, che sono collegamenti ipertestuali tramite i quali viene scaricato malware, quali virus o spyware, ma anche il testo presentato all'interno di un'immagine che consente di aggirare i filtri di protezione dei collegamenti ipertestuali.  

La maggior parte delle misure di protezione tengono fuori gli utenti non autorizzati. Tuttavia un pirata informatico può aggirare molte difese se riesce a imbrogliare un utente e inserire nell'azienda un Trojan horse, un worm o un virus tramite un collegamento. Il collegamento ipertestuale potrebbe anche condurre un utente in un sito che si avvale di applicazioni popup per richiedere informazioni o per offrire assistenza.

È possibile utilizzare una matrice di vettori di attacco, obiettivi di attacco, descrizioni, con costi per l'azienda simili a quelli indicati nella tabella seguente, al fine di agevolare la classificazione degli attacchi e determinare il rischio che comportano per l'azienda. A volte una minaccia può comportare più di un rischio. Se questo è il caso, gli esempi seguenti evidenziano in grassetto i rischi e i rischi gravi.

**Tabella 1. Attacchi online tramite posta elettronica e relativi costi**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Obiettivi dell'attacco</p></th>
<th><p>Descrizione</p></th>
<th><p>Costo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Furto di informazioni aziendali</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico impersona un utente interno (spoofing) per ottenere informazioni aziendali.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p>
<p>Credibilità aziendale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Furto di informazioni finanziarie</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico ricorre alla tecnica del phishing (o dello spear-phishing) per richiedere informazioni riservate quali i dettagli di conto.</p></td>
<td style="border:1px solid black;"><p><strong>Denaro</strong></p>
<p><strong>Informazioni riservate</strong></p>
<p>Credibilità aziendale</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Download di malware</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico ricorre all'inganno per fare in modo che un utente utilizzi un collegamento ipertestuale o apra un allegato, infettando in questo modo la rete aziendale.</p></td>
<td style="border:1px solid black;"><p><strong>Disponibilità aziendale</strong></p>
<p>Credibilità aziendale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Download di software di pirati informatici</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico ricorre all'inganno per fare in modo che un utente utilizzi un collegamento ipertestuale o apra un allegato, scaricando così un programma del pirata informatico che sfrutta le risorse aziendali di rete.</p></td>
<td style="border:1px solid black;"><p><strong>Risorse</strong></p>
<p><strong>Credibilità aziendale</strong></p>
<p>Denaro</p></td>
</tr>
</tbody>
</table>
<p> </p>

Come nella maggior parte di queste truffe, si può resistere più efficacemente agli attacchi di social engineering avvicinandosi con scetticismo a qualsiasi cosa che arrivi senza preavviso nella casella di posta in arrivo. Affinché questo approccio sia supportato all'interno di un'organizzazione, è importante includere nei criteri di protezione delle indicazioni specifiche sull'uso della posta elettronica che interessi:

-   Gli allegati ai documenti.

-   I collegamenti ipertestuali nei documenti.

-   Le richieste di informazioni personali e aziendali dall'interno dell'azienda.

-   Le richieste di informazioni personali e aziendali provenienti dall'esterno dell'azienda.

Oltre a queste linee guida, è importante riportare degli esempi di attacchi di phishing. Se un utente riconosce una truffa basata sul phishing sarà molto più facile notare quelle di altro tipo.

###### Applicazioni popup e finestre di dialogo

Sarebbe irrealistico pensare che i membri del personale non utilizzino l'accesso Internet per attività non correlate all'azienda. La maggior parte dei dipendenti esplorano il Web per motivi personali, ad esempio per gli acquisti online o per fare ricerche. L'esplorazione personale del Web potrebbe portare i dipendenti, e quindi i sistemi informatici aziendali, a contatto con pirati informatici dediti al social engineering in genere. Sebbene essi potrebbero non mirare direttamente a tale azienda, potrebbero sfruttare il suo personale per tentare di accedere alle risorse aziendali. Uno degli obiettivi più diffusi è quello di incorporare un motore di posta all'interno dell'ambiente informatico di un'azienda dal quale il pirata informatico può lanciare attacchi di phishing o di altro tipo ad altre aziende o persone.

La figura seguente illustra come un collegamento ipertestuale possa sembrare un collegamento a un sito sicuro di gestione degli account (secure.contosa.com account\_id?Amendments), mentre la barra di stato indica che conduce l'utente in un sito di pirati informatici. In base al browser utilizzato, un pirata informatico può eliminare o riformattare le informazioni della barra di stato.

[![](images/Cc875841.HPISET02(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/cc875841.hpiset02_big(it-it,technet.10).gif)

**Figura 2. Collegamento ipertestuale a una pagina Web di phishing**

I due metodi più comuni per spingere un utente a fare clic su un pulsante all'interno di una finestra di dialogo consistono nell'avvertire di un problema, ad esempio visualizzando un messaggio di errore realistico di un sistema operativo o di un'applicazione, oppure nell'offrire dei servizi aggiuntivi, ad esempio il download gratuito di un programma che rende più veloce il computer dell'utente. Per gli utenti IT e del Web esperti questi metodi possono sembrare dei palesi inganni. Tuttavia, per gli utenti inesperti, tali applicazioni popup e finestre di dialogo possono causare timore o sembrare attraenti.

**Tabella 2. Attacchi online con popup e finestre di dialogo e relativi costi**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Obiettivi dell'attacco</p></th>
<th><p>Descrizione</p></th>
<th><p>Costo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Furto di informazioni personali</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico richiede le informazioni personali di un membro del personale</p></td>
<td style="border:1px solid black;"><p>Informazioni riservate</p>
<p>Denaro (membro del personale)</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Download di malware</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico inganna l'utente affinché utilizzi un collegamento ipertestuale o apra un allegato</p></td>
<td style="border:1px solid black;"><p>Disponibilità aziendale</p>
<p>Credibilità aziendale</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Download di software di pirati informatici</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico inganna l'utente affinché utilizzi un collegamento ipertestuale o apra un allegato</p></td>
<td style="border:1px solid black;"><p>Risorse</p>
<p>Credibilità aziendale</p>
<p>Denaro</p></td>
</tr>
</tbody>
</table>
<p> </p>

Proteggere gli utenti dalle applicazioni popup di social engineering è principalmente un'azione di consapevolezza. Per evitare il problema è possibile impostare una configurazione del browser predefinita che blocchi i popup e i download automatici, tuttavia alcuni popup possono aggirare le impostazioni del browser. Il metodo più efficace è assicurarsi che gli utenti sappiano che non devono fare clic sui popup, se non dopo averne verificato le proprietà con il personale di supporto. Di conseguenza, il personale aziendale deve essere fiducioso nei confronti del personale di supporto e sapere che non sarà giudicato se viene rilevato che stava esplorando il Web. Su questo rapporto di fiducia può influire la politica aziendale riguardante la navigazione personale su Internet.

###### Messaggistica immediata

La messaggistica immediata è un mezzo di comunicazione relativamente nuovo, ma si è guadagnato una grande popolarità come strumento aziendale; alcuni analisti ritengono che nel 2006 gli utenti di prodotti di messaggistica immediata saranno duecento milioni. L'immediatezza e la familiarità della messaggistica immediata la rendono una ricca riserva di caccia per gli attacchi di social engineering, infatti gli utenti la considerano alla stregua di un telefono e non l'associano alle potenziali minacce software. I due principali attacchi che vengono realizzati tramite la messaggistica immediata sono la consegna di un collegamento malware in un messaggio e la consegna di un file vero e proprio. Certamente la messaggistica immediata è un altro modo per richiedere informazioni in maniera semplice.

Se si parla di social engineering, una serie di potenziali minacce si nasconde nella messaggistica immediata. La prima è l'informalità che la caratterizza. La natura ciarliera della messaggistica immediata, insieme all'opzione di assegnarsi un nome fittizio o falso, indica che non è del tutto chiaro che si sta parlando con la persona con cui si crede di parlare, questo aumenta la possibilità di spoofing casuale.

La figura seguente illustra come funziona lo spoofing per la posta elettronica e per la messaggistica immediata.

![](images/Cc875841.HPISET03(it-it,TechNet.10).gif)

**Figura 3. Spoofing tramite messaggistica immediata e posta elettronica**

Il pirata informatico (in rosso) impersona un altro utente conosciuto e invia un messaggio di posta elettronica o di messaggistica immediata che la vittima riterrà provenire da una persona che conosce. La familiarità allenta le difese degli utenti, quindi sarà più probabile che utilizzino un collegamento o che aprano un allegato proveniente da una persona che conoscono, o meglio, che credono di conoscere. La maggior parte dei provider di messaggistica immediata permette l'identificazione degli utenti in base all'indirizzo di posta elettronica, questo può consentire a un pirata informatico, che ha identificato uno standard per gli indirizzi all'interno di un'azienda, di inviare inviti di contatto di messaggistica immediata ad altre persone nell'ambito dell'organizzazione. Questa funzionalità non rappresenta una minaccia, significa, tuttavia, che il numero di obiettivi all'interno dell'azienda aumenta notevolmente.

**Tabella 3. Attacchi tramite messaggistica immediata e relativi costi**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Obiettivi dell'attacco</p></th>
<th><p>Descrizione</p></th>
<th><p>Costo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Richiesta di informazioni aziendali riservate</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico utilizza lo spoofing per impersonare un collega di lavoro e richiedere informazioni aziendali.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p>
<p>Credibilità aziendale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Download di malware</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico ricorre all'inganno per fare in modo che un utente utilizzi un collegamento ipertestuale o apra un allegato, infettando in questo modo la rete aziendale.</p></td>
<td style="border:1px solid black;"><p><strong>Disponibilità aziendale</strong></p>
<p>Credibilità aziendale</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Download di software di pirati informatici</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico ricorre all'inganno per fare in modo che un utente utilizzi un collegamento ipertestuale o apra un allegato, scaricando così un programma del pirata informatico, ad esempio un motore di posta, che sfrutta le risorse aziendali di rete.</p></td>
<td style="border:1px solid black;"><p><strong>Risorse</strong></p>
<p><strong>Credibilità aziendale</strong></p>
<p>Denaro</p></td>
</tr>
</tbody>
</table>
<p> </p>

Se l'azienda desidera ottenere l'immediatezza e la riduzione dei costi che la messaggistica immediata può fornire, è necessario includere nei criteri di protezione aziendali delle difese specifiche riguardanti la messaggistica immediata. Per agevolare il controllo della messaggistica immediata in azienda è necessario stabilire le seguenti cinque regole per l'uso:

-   **Standardizzazione su un'unica piattaforma di messaggistica immediata**. Questa regola ridurrà gli interventi di assistenza e scoraggerà gli utenti a partecipare a una chat utilizzando il proprio provider di messaggistica immediata. Se si desidera un approccio più controllato per limitare le scelte degli utenti è possibile scegliere di bloccare le porte utilizzate dal servizio comune di messaggistica immediata.

-   **Definizione delle impostazioni di protezione dell'implementazione**. I client di messaggistica immediata offrono una serie di opzioni di protezione e privacy, ad esempio la scansione antivirus.

-   **Impostazione delle linee guida sui contatti**. È fondamentale raccomandare agli utenti di non accettare nuovi inviti di contatto in maniera predefinita.

-   **Impostazione degli standard per le password**. Le password di messaggistica immediata devono essere conformi agli standard per le password complesse impostati per le password host.

-   **Fornitura di una guida d'uso**. È importante elaborare per gli utenti una serie di linee guida basate sulle migliori pratiche, in cui si spieghi il ragionamento sottostante alle raccomandazioni fornite.

###### Minacce telefoniche

Il telefono rappresenta, per i pirati informatici dediti al social engineering un vettore di attacchi unico. È un mezzo familiare ma anche impersonale, poiché la vittima non può vedere il pirata informatico. Le opzioni di comunicazione per la maggior parte dei sistemi informatici possono trasformare anche il PBX (Private Branch Exchange) in un obiettivo attraente. Un altro attacco, forse grossolano, è il furto dei PIN delle carte di credito o delle schede telefoniche nelle cabine del telefono. Questo attacco viene comunemente effettuato nei confronti delle singole persone, tuttavia le carte di credito aziendali sono altrettanto utili. La maggior parte delle persone è cosciente del fatto che deve prestare attenzione quando utilizza un bancomat, ma se usa il PIN in una cabina telefonica diventa meno accorta.

Il VoIP (Voice over Internet Protocol) rappresenta un mercato in via di sviluppo che offre alle aziende vantaggi in termini di costi. Attualmente, a causa del numero di installazioni relativamente limitato, la pirateria informatica tramite VoIP non viene considerata una minaccia rilevante. Tuttavia, mano a mano che le aziende adottano questa tecnologia, lo spoofing tramite VoIP diventerà altrettanto diffuso quanto quello tramite posta elettronica e messaggistica immediata.

PBX (Private Branch Exchange)
Se un pirata informatico attacca un PBX ha tre obiettivi principali:

-   Richiedere informazioni, solitamente sfruttando l'imitazione di un utente legittimo, sia per accedere al sistema telefonico stesso, sia per ottenere l'accesso remoto ai sistemi informatici.

-   Ottenere l'accesso "gratuito" all'uso del telefono.

-   Ottenere l'accesso alla rete di comunicazione.

Ciascuno dei suddetti obiettivi è una variazione sul tema, in cui il pirata informatico chiama l'azienda e tenta di ottenere dei numeri telefonici che consentono di accedere direttamente al PBX oppure, tramite PBX, alla rete telefonica pubblica. Il termine che utilizza il pirata informatico per definire questa azione è *phreaking*. L'approccio più comune è fingere di essere un tecnico di telefonia e richiedere una linea esterna o una password per analizzare e risolvere i problemi riportati nel sistema telefonico interno, come illustrato nella figura seguente.

![](images/Cc875841.HPISET04(it-it,TechNet.10).gif)

**Figura 4. Attacchi telefonici tramite PBX**

Le richieste di informazioni o l'accesso tramite telefono sono una forma di attacco relativamente priva di rischio. Se la vittima diventa sospettosa o rifiuta di collaborare a una richiesta, il pirata informatico può semplicemente riattaccare. È necessario però comprendere che attacchi di questo genere sono sofisticati e non si limitano a una semplice chiamata all'azienda per richiedere ID utente e password. Solitamente il pirata informatico presenta uno scenario e chiede oppure offre aiuto, prima che avvenga la richiesta di informazioni personali o aziendali, come un fatto quasi senza importanza.

**Tabella 4. Attacchi tramite PBX (Private Branch Exchange) e relativi costi**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Obiettivi dell'attacco</p></th>
<th><p>Descrizione</p></th>
<th><p>Costo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Richiesta di informazioni aziendali</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico impersona un utente legittimo per ottenere informazioni riservate.</p></td>
<td style="border:1px solid black;"><p>Informazioni riservate</p>
<p>Credibilità aziendale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Richiesta di informazioni telefoniche</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico finge di essere un tecnico di telefonia per ottenere l'accesso al PBX e fare telefonate esterne.</p></td>
<td style="border:1px solid black;"><p>Risorse</p>
<p>Denaro</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Uso del PBX per accedere ai sistemi informatici</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico entra nei sistemi informatici tramite PBX per rubare o manipolare informazioni, infettare i sistemi con malware o utilizzare le risorse.</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
</tbody>  
</table>
  
La maggior parte degli utenti non conosce il sistema telefonico interno, a parte il telefono stesso. Questa è la difesa più importante che si possa implementare nei criteri di protezione. È insolito che i pirati informatici approccino gli utenti generici in questo modo. Le vittime più comuni fanno parte del personale della reception o del centralino. L'azienda deve stabilire che solo l'assistenza è autorizzata a fornire supporto ai fornitori telefonici. In questo modo, il personale autorizzato si occuperà delle chiamate tecniche di assistenza. Questo approccio permette al personale che viene preso di mira di reindirizzare le richieste in maniera rapida ed efficiente a un membro del personale qualificato.
  
###### Assistenza
  
L'assistenza, o help desk, è uno dei pilastri della difesa contro i pirati informatici, tuttavia, può diventare un obiettivo dei pirati informatici di social engineering. Sebbene il personale di supporto sia spesso consapevole delle minacce della pirateria informatica, è altresì addestrato ad aiutare e assistere i chiamanti, fornendo consigli e aiutandoli a risolvere i loro problemi. A volte l'entusiasmo che dimostra una persona dell'assistenza tecnica nel fornire una soluzione oltrepassa l'impegno preso di rispettare le procedure di protezione, ponendo un dilemma al personale di supporto. Applicando rigorosamente gli standard di protezione, richiedendo delle prove che confermino che la richiesta o la domanda proviene da un utente autorizzato, il personale potrebbe sembrare poco servizievole o addirittura di ostacolo. Il personale dei reparti produzione, vendite e marketing, se ritiene che il reparto IT non fornisca il servizio immediato che richiede, è incline a lamentarsi, inoltre, i senior manager a cui venga richiesto di provare la propria identità, spesso sono poco comprensivi nei confronti della scrupolosità del personale di supporto.
  
**Tabella 5. Attacchi telefonici all'assistenza e relativi costi**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Obiettivi dell'attacco</p></th>  
<th><p>Descrizione</p></th>  
<th><p>Costo</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Richiesta di informazioni</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico impersona un utente legittimo per ottenere informazioni aziendali.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Richiesta di accesso</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico impersona un utente legittimo per ottenere l'accesso ai sistemi aziendali.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p>
<p><strong>Credibilità aziendale</strong></p>  
<p><strong>Disponibilità aziendale</strong></p>  
<p><strong>Risorse</strong></p>
<p>Denaro</p></td>
</tr>
</tbody>
</table>
<p> </p>

Il personale di assistenza deve bilanciare le esigenze di protezione con quelle di efficienza aziendale, quindi i criteri e le procedure di protezione devono supportarlo. La richiesta di una verifica dell'identità, ad esempio la matricola del dipendente, il reparto e il nome del responsabile, non è eccessiva da parte di un analista dell'assistenza, perché tutti conoscono questi dati. Tuttavia tale verifica potrebbe non essere del tutto sicura, infatti un pirata informatico potrebbe avere rubato queste informazioni. Tuttavia si tratta di un inizio realistico. In verità, l'unico mezzo di identificazione preciso al 99,99% è il test del DNA con tampone, cosa evidentemente irrealistica.

È più difficile proteggere l'analista dell'assistenza da un pirata informatico che lavori all'interno dell'azienda o che abbia un contratto di collaborazione. Un pirata informatico di questo tipo ha una buona conoscenza delle procedure di lavoro interne e quindi avrà il tempo di assicurarsi di avere tutte le informazioni necessarie prima di effettuare la chiamata all'assistenza. In questa situazione, le procedure di protezione devono avere un duplice ruolo.

-   L'analista dell'assistenza deve garantire la presenza di un itinerario di controllo di tutte le azioni svolte. Se un pirata informatico riesce ad accedere alle informazioni o alle risorse tramite una chiamata all'assistenza, quest'ultima deve registrare tutte le attività in modo tale che sia possibile correggere o limitare qualsiasi eventuale danno o perdita. Se ogni chiamata attiva messaggio di posta elettronica automatico o manuale in merito al problema o alla richiesta, sarà più semplice per un dipendente che ha subito un furto di identità rendersi conto di cosa è accaduto e chiamare l'assistenza.

-   L'analista dell'assistenza deve disporre di una procedura ben strutturata sulle modalità di gestione dei tipi di chiamata. Ad esempio, se il responsabile del dipendente deve fare le richieste di modifica per l'accesso tramite posta elettronica, non possono essere effettuate modifiche non autorizzate o informali ai livelli di protezione.

Se gli utenti sono consapevoli di queste regole e la dirigenza ne supporta l'implementazione, sarà più difficile per i pirati informatici riuscire a violare la protezione o non essere scoperti. L'itinerario di controllo a 360 gradi è uno strumento estremamente prezioso per evitare le azioni di malintenzionati o scoprirle.

###### Minacce derivanti dalla gestione dei rifiuti

L'analisi illecita dei rifiuti, ovvero *dumpster diving* (rovistare nei rifiuti) come viene comunemente definita, è un'attività preziosa per i pirati informatici. I rifiuti cartacei di un'azienda possono contenere informazioni che offrono vantaggi immediati a un pirata informatico, ad esempio i numeri di conto e ID utente scartati, altrimenti possono servire come informazioni di base, ad esempio elenchi del telefono o organigrammi. Le informazioni di questo genere sono inestimabili per i pirati informatici dediti al social engineering, infatti consentono loro di sembrare credibili quando decidono di attaccare. Ad esempio, se il pirata informatico dimostra una buona conoscenza del personale di un reparto aziendale, probabilmente riuscirà meglio nell'approccio con la vittima; il personale interpellato sarà portato a pensare che una persona che conosce tante cose dell'azienda deve essere un dipendente valido.

I supporti elettronici possono essere ancora più utili. Se le aziende non dispongono di regole per la gestione dei rifiuti che includano lo smaltimento dei supporti inutilizzati, nelle unità disco rigido, nei CD-ROM e nei DVD sarà possibile trovare ogni genere di informazioni. Le caratteristiche di solidità dei supporti fissi e rimovibili significa che le persone responsabili della protezione IT devono stabilire criteri di gestione dei supporti che includano istruzioni per la cancellazione o la distruzione.

**Tabella 6. Attacchi tramite la gestione dei rifiuti e relativi costi**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Obiettivi dell'attacco</p></th>
<th><p>Descrizione</p></th>
<th><p>Costo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Rifiuti cartacei nei bidoni all'esterno dell'azienda</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico si impossessa della carta gettata nei cassonetti esterni per rubare importanti informazioni aziendali.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p>
<p>Credibilità aziendale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Rifiuti cartacei nei cestini all'interno dell'azienda</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico si impossessa della carta gettata nei cestini all'interno dell'ufficio, ignorando qualsiasi linea guida per la gestione dei rifiuti cartacei all'esterno dell'azienda.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p>
<p>Credibilità aziendale</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Smaltimento dei supporti elettronici  </p></td>
<td style="border:1px solid black;"><p>Il pirata informatico ruba le informazioni e le applicazioni dai supporti elettronici gettati via. Oppure può rubare il supporto stesso.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p>
<p>Risorse</p>
<p>Credibilità aziendale</p></td>
</tr>
</tbody>
</table>
<p> </p>

Il personale aziendale deve essere pienamente cosciente di cosa comporta gettare in un cestino documenti cartacei o supporti elettronici. Una volta che tali rifiuti vengono portati all'esterno dell'edificio la loro proprietà può diventare un problema di oscurità legale. Rovistare nei rifiuti, ovvero dumpster diving, potrebbe non essere ritenuto illegale in ogni circostanza, quindi è necessario assicurarsi di informare il personale sulle modalità di gestione dei materiali da smaltire. I rifiuti cartacei devono sempre essere sminuzzati e i supporti magnetici cancellati o distrutti. Se un oggetto da smaltire dovesse essere troppo grande o rigido per essere inserito in un distruggidocumenti, ad esempio un elenco telefonico, oppure se dovesse essere tecnicamente impossibile per l'utente distruggere tale oggetto, è necessario elaborare un protocollo specifico per lo smaltimento. Inoltre, i cassonetti dei rifiuti devono essere posizionati in una zona sicura e non accessibile al pubblico.

Quando vengono elaborati i criteri di gestione dei rifiuti è importante assicurarsi di rispettare le normative locali sulla salute e la sicurezza. Dal punto di vista sociale potrebbe avere valore l'adozione di strategie di gestione dei rifiuti ecologicamente corrette.

Oltre alla gestione dei rifiuti esterni, ovvero i documenti cartacei e i supporti elettronici che, una volta all'esterno, possono essere raggiunti da persone estranee, è necessaria anche la gestione dei rifiuti all'interno dell'azienda. Spesso i criteri di protezione trascurano questo problema, poiché spesso si ritiene che le persone a cui è stato concesso di accedere all'azienda siano fidate. Ovviamente non è sempre vero. Una delle misure più efficaci per la gestione dei rifiuti cartacei è la specifica relativa alla classificazione dei dati. Ovvero si definiscono diverse categorie di informazioni cartacee e si stabilisce in che maniera il personale deve gestirne lo smaltimento. Tra le categorie di esempio sono inclusi i tipi di informazioni seguenti.

-   **Riservate aziendali**. Tutti i documenti aziendali riservati devono essere sminuzzati prima di essere gettati in qualsiasi cestino.

-   **Private**. Tutti i documenti privati devono essere sminuzzati prima di essere gettati in qualsiasi cestino.

-   **Di reparto**. Tutti i documenti dei reparti devono essere sminuzzati prima di essere gettati nei cassonetti pubblici.

-   **Pubbliche**. I documenti pubblici possono essere gettati in qualsiasi cestino o utilizzati come carta da riciclare.

Per ulteriori informazioni sull'elaborazione della classificazione dei dati, vedere la pagina [Security Management SMF](http://go.microsoft.com/fwlink/?linkid=37696) (in inglese) su Microsoft® TechNet, all'indirizzo http://go.microsoft.com/fwlink/?linkid=37696.

###### Approcci personali

Il modo più semplice ed economico di cui dispone un pirata informatico per ottenere informazioni è quello di chiederle direttamente. Questo approccio può apparire rudimentale e ovvio, tuttavia costituisce la base di qualsiasi truffa fin dall'inizio dei tempi. I pirati informatici dediti al social engineering adottano quattro approcci principali e di provata riuscita:

-   **Intimidazione**. Questo approccio può comportare l'imitazione di una figura autorevole per costringere la vittima a soddisfare una richiesta.

-   **Persuasione**. Tra le forme più comuni di persuasione sono incluse le lusinghe e la presunzione di avere conoscenze importanti da parte del pirata informatico.

-   **Seduzione**. Questo approccio comporta una manovra di lunga durata e implica che un subalterno o un collega crei un rapporto per acquisire fiducia e, infine, per ottenere informazioni dalla vittima.

-   **Assistenza**. Questo approccio implica l'offerta di aiuto alla vittima dell'inganno. Per ottenere l'assistenza in questione, la vittima dovrà divulgare informazioni personali che permetteranno al pirata informatico di rubare l'identità della vittima.

La maggior parte delle persone presuppone che l'interlocutore sia sincero; questo è un fatto interessante, poiché è un fatto accertato che la maggior parte delle persone ammette di ricorrere alle bugie. (*The Lying Ape: An Honest Guide to a World of Deception*, (l'animale che mente: una guida onesta al mondo dell'inganno) Brian King, Icon Books Limited). La fiducia assoluta è uno degli obiettivi che il social engineering tenta di raggiungere.

Proteggere gli utenti da questo genere di approcci personali è davvero difficile. Alcuni utenti sono naturalmente disposti a diventare vittime di uno dei suddetti quattro attacchi di social engineering. La difesa contro un attacco basato sull'intimidazione è lo sviluppo di una cultura "del coraggio" all'interno dell'azienda. Se il comportamento normale in azienda è la gentilezza, il successo di un'intimidazione viene ridotto, infatti il singolo membro del personale sarà più portato a riferire ai superiori le situazioni di aggressione. Un atteggiamento di sostegno all'escalation dei problemi e del processo decisionale nell'ambito dei ruoli dirigenziali e di supervisione è la cosa peggiore che possa accadere ai pirati informatici dediti al social engineering. Il loro obiettivo è incoraggiare la vittima a prendere una decisione rapida, ma se il problema viene riferito a un superiore, le probabilità di raggiungere l'obiettivo si riduce.

La persuasione è sempre stato un metodo dell'uomo fondamentale per raggiungere obiettivi personali. Non è possibile eliminare questa caratteristica dalla forza lavoro aziendale, è tuttavia possibile fornire istruzioni rigorose su ciò che una persona deve o non deve fare. Il pirata informatico richiede o cerca di produrre sempre uno scenario in cui l'utente fornisca spontaneamente informazioni riservate. Campagne di consapevolezza costanti e istruzioni di base sui dispositivi di protezione, quali le password, sono la difesa migliore.

I pirati informatici hanno bisogno di tempo per ingraziarsi gli utenti aziendali; hanno bisogno di contatti regolari, cosa che probabilmente implica assumere il ruolo di un collega. Per la maggior parte delle aziende di medie dimensioni, la principale minaccia derivante dai colleghi è legata al personale di assistenza regolare o ai collaboratori esterni a contratto. Il gruppo delle risorse umane deve usare nei confronti del personale a contratto la stessa attenzione che pone nella selezione dei dipendenti che assume con contratto a tempo indeterminato. La maggior parte di questo lavoro può essere trasferita al fornitore di personale esterno a contratto. Per assicurarsi che il fornitore svolga il lavoro in maniera efficiente, l'azienda può richiedere di rispettare i criteri di selezione aziendali applicati al personale a tempo indeterminato. Se un pirata informatico dedito al social engineering dovesse ottenere un lavoro permanente presso l'azienda, la migliore difesa in questo caso sarà la consapevolezza del personale aziendale e il rispetto dei criteri di protezione delle informazioni.

Infine, gli attacchi basati sull'offerta di assistenza possono essere ridotti al minimo se l'azienda dispone di un'assistenza efficiente. Una persona che offre assistenza dall'interno spesso è il risultato dell'insoddisfazione nei confronti dei servizi di assistenza aziendali esistenti. Dunque, per assicurarsi che il personale contatti l'assistenza aziendale anziché un esperto interno non autorizzato o, peggio ancora, un esperto all'esterno dell'azienda, è necessario ricorrere a due elementi.

-   Specificare nei criteri di protezione che l'assistenza aziendale è l'unico posto a cui gli utenti devono ricorrere per riferire i problemi.

-   Garantire che l'assistenza disponga di un processo di risposta concordato nell'ambito del contratto del livello di servizio (SLA, Service Level Agreement) del reparto. Verificare regolarmente le prestazioni dell'assistenza per assicurarsi che gli utenti ricevano il corretto livello di risposta e di risoluzione dei problemi.

È fondamentale non sottovalutare l'importanza dell'assistenza aziendale per riuscire a fornire una difesa di alto livello contro gli attacchi di social engineering.

Approcci virtuali
Per sferrare i loro attacchi, i pirati informatici dediti al social engineering devono prendere contatto con le vittime. Solitamente, questo avviene utilizzando dei supporti elettronici, ad esempio un messaggio di posta elettronica o una finestra popup. I grandi volumi di posta indesiderata in arrivo nella maggior parte delle caselle di posta, fa sì che questa modalità di attacco abbia meno riscontro; infatti gli utenti sono più scettici nei confronti delle catene di sant'Antonio e delle richieste a carattere cospirativo che invitano a prendere parte a transazioni finanziarie "legali" e remunerative. Nonostante ciò, il volume di questo genere di posta e l'uso di motori di posta Trojan horse indicano che, per alcuni pirati informatici, questo tipo di attacco resta attraente, anche se con una percentuale di riuscita minimo. La maggior parte di questi attacchi sono personali e mirano a scoprire informazioni sull'identità della vittima. Tuttavia, per le aziende, l'abuso diffuso dei sistemi aziendali, quali computer e accesso a Internet, ovvero l'uso personale che ne fanno i dipendenti, significa che i pirati informatici sono in grado di entrare nella rete aziendale.

I telefoni offrono un metodo di approccio più personale e a volume ridotto. Il rischio limitato di essere arrestati indica che alcuni pirati informatici utilizzano il telefono come mezzo di approccio, principalmente per gli attacchi ai PBX e all'assistenza aziendale; la maggior parte degli utenti ha dei dubbi davanti a una telefonata in cui si richiedono informazioni su qualcuno che non si conosce personalmente.

Approcci fisici
Meno comune, ma più efficace per il pirata informatico, è il contatto personale diretto con una vittima. Soltanto il dipendente più sospettoso dubita della validità di una persona che si presenta e richiede od offre aiuto per un computer. Sebbene questi approcci comportino rischi di gran lunga maggiori per l'autore, i vantaggi sono ovvii. Il pirata informatico può ottenere l'accesso senza restrizioni ai sistemi informatici aziendali e penetrare all'interno di qualsiasi protezione tecnologica perimetrale esistente.

L'aumento della diffusione delle tecnologie mobili, che permettono agli utenti di collegarsi alle reti aziendali in viaggio o da casa, rappresenta un'altra grave minaccia alle risorse IT delle aziende. Gli attacchi possibili in questo caso includono il più semplice attacco basato sull'osservazione, in cui un pirata informatico, seduto in treno alle spalle dell'utente, riesce a ottenere l'ID e la password di accesso; ma esistono anche attacchi più sofisticati in cui viene fornito e installato un lettore di smart card o l'aggiornamento di un router da un tecnico dell'assistenza, estremamente gentile, che accede alla rete aziendale chiedendo allo stesso utente di fornire ID, password e magari di offrirgli una tazza di caffé. Un pirata informatico scrupoloso potrebbe perfino richiedere all'utente una firma di autorizzazione e così conserverebbe addirittura la sua firma. Tra questi tipi di attacchi si devono annoverare minacce quali i vicini che usano la larghezza di banda pagata dall'azienda per acceder a Internet tramite una rete LAN wireless non protetta.

Sebbene le grandi aziende dispongano di infrastrutture di protezione dei siti di alto livello, gli uffici di piccole e medie dimensioni potrebbero essere meno preparate. Il *tailgating*, ovvero una persona non autorizzata che si introduce in ufficio seguendo una persona dotata di passi, è un esempio molto semplice di attacco di social engineering. L'intruso apre la porta attraverso la quale l'utente autorizzato sta passando e quindi inizia una conversazione sul tempo o sulla partita domenicale, intanto superano insieme la zona della reception. In una grande azienda questo approccio non potrebbe funzionare, poiché le singole persone devono passare il badge in un tornello, né potrebbe funzionare in una piccola società dove tutti si conoscono. Tuttavia è l'approccio perfetto in un'azienda con un migliaio di dipendenti dove è normale che non tutti si conoscano. Se l'impostore ha già avuto accesso alle informazioni aziendali, ad esempio i nomi dei reparti, del personale o se conosce i protocolli interni, il diversivo della conversazione risulterà ancora più credibile.

La protezione di chi lavora da casa si limita solitamente alla tecnologia. I criteri di protezione devono includere dei firewall che garantiscano che i pirati informatici esterni non possano accedere alle reti. Oltre a questo requisito, la maggior parte delle aziende di medie dimensioni permettono ai dipendenti che lavorano da casa di gestire i propri criteri di protezione e perfino i backup.

**Tabella 7. Attacchi basati sull'accesso fisico e relativi costi**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Obiettivi dell'attacco</p></th>
<th><p>Descrizione</p></th>
<th><p>Costo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Furto di identità dell'utente mobile</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico osserva il legittimo utente mentre digita nel computer i dati di accesso e altri dettagli. Questo fatto può precedere il furto fisico del computer.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Furto di identità dell'utente che lavora da casa</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico si spaccia per un addetto al supporto IT o alla manutenzione, per accedere alla rete di una persona che lavora da casa e richiede l'ID utente e la password al fine di verificare che l'aggiornamento sia stato installato correttamente.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Contatto diretto in rete tramite la rete del dipendente che lavora da casa</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico accede alla rete aziendale, tramite la rete del dipendente che lavora da casa, spacciandosi per un tecnico dell'assistenza. In questo modo ottiene l'accesso senza restrizioni alla rete e alle risorse aziendali.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p>
<p><strong>Credibilità aziendale</strong></p>  
<p><strong>Disponibilità aziendale</strong></p>  
<p><strong>Risorse</strong></p>
<p>Denaro</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Accesso costante alla rete di un dipendente che lavora da casa</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico o l'utente locale accede a Internet con connessione a banda larga tramite una rete domestica priva di protezione.</p></td>
<td style="border:1px solid black;"><p><strong>Risorse</strong></p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Accesso non accompagnato agli uffici aziendali</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico si introduce negli uffici seguendo attraverso la porta un dipendente autorizzato.</p></td>
<td style="border:1px solid black;"><p>Informazioni riservate</p>
<p>Credibilità aziendale</p>  
<p>Disponibilità aziendale</p>  
<p>Denaro</p>
<p>Risorse</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Accesso all'ufficio aziendale di una singola persona</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico ottiene l'accesso all'ufficio di una singola persona dove può tentare di utilizzare il computer o i documenti cartacei curiosando negli archivi.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p>
<p><strong>Risorse</strong></p>
<p>Denaro</p></td>
</tr>
</tbody>
</table>
<p> </p>

Le difese contro le minacce di questo genere dipendono essenzialmente dall'implementazione delle procedure consigliate da parte degli utenti, sulla base di criteri di protezione aziendali efficaci che siano in grado di proteggere le tre aree seguenti:

-   Il sito aziendale

-   Il lavoro da casa

-   Il lavoro mobile

Dovrebbe essere impossibile accedere all'edificio o al sito di un'azienda senza l'autorizzazione appropriata. Il personale della reception deve essere gentile ma determinato quando tratta con il personale, con gli appaltatori e con i visitatori. Poche e semplici condizioni previste dai criteri di protezione aziendali renderanno praticamente impossibile un attacco fisico di social engineering all'interno dell'edificio. Tali condizioni potrebbero includere:

-   Passi con foto da mostrare ogni volta che un membro del personale entra nell'edificio o esce.

-   Un registro dei visitatori con obbligo di firma da parte del visitatore e controfirma della persona che va a visitare, sia in ingresso che in uscita.

-   Passi per i visitatori sempre in vista, con indicazione della data e obbligo di restituzione in uscita.

-   Un registro degli appaltatori con obbligo di firma da parte dell'appaltatore e controfirma dal membro del personale che ha autorizzato il lavoro, sia in ingresso che in uscita.

-   Passi per gli appaltatori sempre in vista, con indicazione della data e obbligo di restituzione in uscita.

Per assicurarsi che tutti si presentino all'addetto alla reception, l'azienda deve erigere delle barriere che garantiscano che i visitatori siano obbligati a passare direttamente davanti all'addetto alla reception per presentare le proprie credenziali o firmare il registro. Tali barriere non devono essere tornelli o barriere tra le quali essere pressati.

Ad esempio, l'area della reception può utilizzare oggetti rilassanti come un divano per indirizzare le persone verso l'addetto alla reception, come indicato nei due esempi illustrati nella figura seguente.

![](images/Cc875841.HPISET05(it-it,TechNet.10).gif)

**Figura 5. Progettazione della reception**

L'area della reception a sinistra permette a un visitatore non autorizzato di introdursi *(tailgating)* in azienda facendosi scudo di un dipendente autorizzato. Nell'esempio a destra qualsiasi visitatore è obbligato a passare davanti alla reception. La posizione del terminale del computer non copre la vista dell'addetto alla reception. Il passaggio deve essere abbastanza grande da permettere a chiunque di passarvi comodamente, incluse le persone su sedia a rotelle. È essenziale che i membri del personale addetto alla reception siano ben addestrati nell'accogliere e controllare coerentemente ogni persona che arriva. Ogni accesso all'edificio deve rispettare gli standard previsti e il personale deve utilizzare esclusivamente le entrate e le uscite autorizzate; non devono esistere porte di servizio.

Quando si erigono delle barriere o si implementa un sistema di gestione delle porte, è importante assicurarsi di rispettare i requisiti normativi di salute, sicurezza e accessibilità.

In casa non è realistico autorizzare ogni visitatore o fattorino. In realtà, la maggior parte delle persone è molto più attenta a chi fa entrare in casa che in ufficio. La cosa più importante è garantire che un attacco non riesca ad accedere alle risorse aziendali. Nel protocollo riguardante i servizi IT esterni devono essere incluse delle regole che stabiliscano le seguenti condizioni.

-   Ogni azione svolta dall'assistenza tecnica, che si tratti di una correzione o di un aggiornamento all'interno dell'azienda, deve essere pianificata e autorizzata dal personale di supporto.

-   Gli appaltatori e il personale interno che eseguono operazioni di manutenzione e installazione devono essere muniti di documento di identità, preferibilmente con foto.

-   L'utente deve contattare il reparto del supporto IT per comunicare l'orario di arrivo del tecnico e l'orario di completamento del lavoro.

-   A ogni lavoro è associato un foglio di lavoro che l'utente deve firmare.

-   L'utente non deve mai fornire i dati di accesso personali o effettuare l'accesso al computer per permettere a un tecnico di accedere.

Questo è un elemento cruciale. È compito del gruppo dei servizi IT assicurarsi che qualsiasi tecnico esterno disponga dell'accesso personale sufficiente per svolgere il lavoro. Se il tecnico non dispone di accesso utente sufficiente per completare un'attività deve contattare l'assistenza. Questo è un requisito essenziale, perché lavorare come tecnico per una società di servizi informatici è una delle attività più redditizie che possa trovare un potenziale pirata informatico. Infatti, in questo ruolo, diventerebbe allo stesso tempo una figura tecnica autorevole e una persona che offre assistenza.

I lavoratori mobili spesso utilizzano i propri computer in ambienti affollati, quali il treno, la stazione, l'aeroporto o i ristoranti. È evidente che è quasi impossibile assicurarsi che nessuno stia guardando mentre si digitano i dati al computer in ambienti di questo tipo, tuttavia i criteri di protezione aziendali devono fornire consigli su come ridurre al minimo i rischi per le informazioni personali e aziendali. Se i membri del personale utilizzano dei PDA (Personal Digital Assistant) è necessario includere informazioni sulla gestione della protezione e della sincronizzazione.

###### Reverse social engineering

*Reverse social engineering* è un concetto che indica una situazione in cui la vittima o le vittime fanno l'approccio iniziale e offrono al pirata informatico le informazioni che desidera. Uno scenario simile può apparire improbabile, tuttavia delle figure autorevoli, in particolare dal punto di vista tecnico o sociale, sono in grado di ricevere informazioni personali di vitale importanza, quali ID utente e password, proprio perché sembrano al di sopra di ogni sospetto. Ad esempio, nessun addetto all'assistenza chiederebbe a un chiamante l'ID utente o la password, poiché è in grado di risolvere i problemi senza queste informazioni. Molti utenti in difficoltà con il computer potrebbero fornire spontaneamente questi dati, vitali per la protezione, allo scopo di accelerare la risoluzione del problema. Il pirata informatico non dovrebbe neanche chiedere. Gli attacchi di social engineering non sono reattivi, come suggerisce questo scenario.

Un attacco di social engineering crea una situazione, consiglia una soluzione e fornisce assistenza quando viene richiesta, magari nella maniera semplice descritta nel seguente scenario.

Un collega di lavoro, che è in realtà un pirata informatico, rinomina o sposta un file in modo che la vittima creda di averlo perso. Il pirata informatico ipotizza che potrebbe riuscire a recuperare il file. La vittima, desiderosa di proseguire il suo lavoro, o preoccupata del fatto che la perdita di dati potrebbe essere colpa sua, accetta immediatamente l'offerta di aiuto. Il pirata informatico dichiara che l'operazione può essere effettuata se si accede con i dati personali dell'utente (vittima designata) e potrebbe però sostenere che i criteri di protezione aziendale lo vietano. La vittima prega il pirata informatico ad accedere con i suoi dati per cercare di ripristinare il file. Il pirata informatico accetta mostrandosi riluttante, ripristina il file originale e deruba la vittima di ID utente e password. In questo modo il pirata informatico si è creato una reputazione e potrà ricevere altre richieste di assistenza dai colleghi di lavoro. Questo approccio può aggirare i canali di supporto IT regolari e agevola il mantenimento dell'anonimato del pirata informatico.

Non sempre è necessario conoscere bene una vittima o incontrarla per realizzare un attacco di reverse social engineering. L'imitazione dei problemi utilizzando le finestre di dialogo può essere efficace in un attacco di reverse social engineering non specifico. La finestra di dialogo annuncia che esiste un problema o che è necessario eseguire un aggiornamento per proseguire. La finestra offre un programma da scaricare che consente di risolvere il problema. Una volta completato il trasferimento, il problema scompare e l'utente continua a lavorare, ignaro del fatto che la protezione è stata violata e che è stato scaricato un programma di malware.

**Tabella 8. Attacchi di reverse social engineering e relativi costi**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Obiettivi dell'attacco</p></th>
<th><p>Descrizione</p></th>
<th><p>Costo</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Furto di identità</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico riceve l'ID utente e la password dall'utente autorizzato.</p></td>
<td style="border:1px solid black;"><p>Informazioni riservate</p>
<p>Credibilità aziendale</p>  
<p>Disponibilità aziendale</p>  
<p>Denaro</p>
<p>Risorse</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Furto di informazioni</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico si avvale dell'ID utente e della password per accedere ai file aziendali.</p></td>
<td style="border:1px solid black;"><p><strong>Informazioni riservate</strong></p>
<p><strong>Denaro</strong></p>  
<p><strong>Risorse</strong></p>  
<p>Credibilità aziendale</p>
<p>Disponibilità aziendale</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Download di malware</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico ricorre all'inganno per fare in modo che un utente utilizzi un collegamento ipertestuale o apra un allegato, infettando in questo modo la rete aziendale.</p></td>
<td style="border:1px solid black;"><p><strong>Disponibilità aziendale</strong></p>
<p>Credibilità aziendale</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Download di software di pirati informatici</p></td>
<td style="border:1px solid black;"><p>Il pirata informatico ricorre all'inganno per fare in modo che un utente utilizzi un collegamento ipertestuale o apra un allegato, scaricando così un programma del pirata informatico, ad esempio un motore di posta, che sfrutta le risorse aziendali di rete.</p></td>
<td style="border:1px solid black;"><p><strong>Risorse</strong></p>
<p><strong>Credibilità aziendale</strong></p>
<p>Denaro</p></td>
</tr>
</tbody>
</table>
<p> </p>

Difendersi contro il reverse social engineering è probabilmente il compito più arduo. La vittima non ha motivo di sospettare il pirata informatico, poiché sente di avere il controllo della situazione. La difesa principale è stabilire nei criteri di protezione che tutti i problemi devono essere risolti rivolgendosi all'assistenza. Se gli addetti all'assistenza sono efficienti, gentili e senza pregiudizi, gli altri dipendenti si rivolgeranno a loro e non a persone non autorizzate o a conoscenti.

[](#mainsection)[Inizio pagina](#mainsection)

### Progettazione delle difese contro le minacce del social engineering

Avendo compreso la vastità delle minacce esistenti, sono necessarie tre fasi per progettare una difesa contro le minacce del social engineering rivolte al personale aziendale. Una difesa efficace è l'attività di progettazione. Spesso le difese sono reattive: si scopre una violazione e si erige una barriera per garantire che il problema non si verifichi nuovamente. Sebbene questo approccio dimostri un livello di consapevolezza, la soluzione arriva in ritardo se il problema è grave o comporta costi elevati. Per evitare questo scenario è necessario intraprendere le tre azioni seguenti.

-   **Sviluppare una struttura di gestione della protezione**. L'azienda deve definire una serie di obiettivi di protezione contro il social engineering e determinare quali membri del personale sono responsabili di occuparsi di questi obiettivi.

-   **Svolgere delle valutazioni di gestione dei rischi**. Minacce di questo genere non presentano lo stesso livello di rischio per aziende di diverso tipo. È necessario quindi riesaminare ciascuna minaccia derivante dal social engineering e razionalizzare il pericolo che ciascuna di esse può rappresentare per la singola organizzazione.

-   **Implementare le difese contro il social engineering nell'ambito dei criteri di protezione**. Devono essere elaborati per iscritto dei criteri e delle procedure in cui vengano stabilite le modalità di gestione, da parte del personale, delle situazioni che potrebbero essere catalogate come attacchi di social engineering. Questa fase presuppone l'esistenza di criteri di protezione, al di là della minaccia del social engineering. Se l'azienda non dispone di criteri di protezione, è necessario elaborarli. Gli elementi identificati nella valutazione dei rischi del social engineering danno il via all'azienda, tuttavia è necessario considerare anche altre potenziali minacce.

    Per ulteriori informazioni sui criteri di protezione, visitare il sito Web [Microsoft Security](http://www.microsoft.com/italy/security/default.mspx) all'indirizzo: www.microsoft.com/security.

#### Sviluppare una struttura di gestione della protezione.

Una struttura di gestione della protezione fornisce una vista globale di tutte le possibili minacce all'organizzazione aziendale derivanti dal social engineering e assegna ruoli di lavoro predefiniti, responsabili dello sviluppo dei criteri e delle procedure finalizzati a prevenire tali minacce. Questo approccio non significa che è necessario assumere delle persone la cui sola funzione sia garantire la protezione dei beni aziendali. Sebbene si tratti di un approccio valido per le grandi organizzazioni, la presenza di questi ruoli nelle aziende di medie dimensioni è raramente praticabile o auspicabile. L'esigenza fondamentale è accertarsi che un gruppo di persone si assuma le responsabilità principali dei seguenti ruoli di protezione:

-   **Sponsor della protezione**. Un senior manager, probabilmente a livello di consiglio di amministrazione, che disponga dell'autorità necessaria a garantire che tutto il personale prenda seriamente la questione della protezione aziendale.

-   **Responsabile della protezione**. Un dipendente di livello manageriale che si assuma la responsabilità di orchestrare lo sviluppo e il mantenimento dei criteri di protezione.

-   **Responsabile della protezione IT**. Un membro del personale tecnico che si assuma la responsabilità di sviluppare l'infrastruttura IT e i criteri e le procedure di protezione.

-   **Responsabile delle strutture di protezione**. Un membro del team delle strutture che si assuma la responsabilità dello sviluppo dei criteri e delle procedure di protezione del sito e delle operazioni.

-   **Responsabile della promozione della consapevolezza in materia di protezione**. Un membro del personale di livello manageriale, preferibilmente delle risorse umane o del reparto di sviluppo del personale, che si assuma la responsabilità dello sviluppo e dello svolgimento di campagne di promozione della consapevolezza in materia di protezione.

Questo gruppo, ovvero il Comitato direttivo per la protezione, rappresenta i facilitatori all'interno dell'azienda. In qualità di paladini della sicurezza, i membri del Comitato direttivo per la protezione devono stabilire gli obiettivi essenziali della struttura di gestione della protezione. Senza una serie di obiettivi definiti, è difficile promuovere la partecipazione di altre persone all'interno dell'azienda o misurare i risultati del progetto. L'attività iniziale del Comitato direttivo per la protezione è l'identificazione delle vulnerabilità al social engineering all'interno dell'azienda. La seguente tabella illustra in maniera semplice come abilitare rapidamente lo sviluppo di un quadro dei vettori di attacco.

**Tabella 9. Vulnerabilità dell'azienda ai vettori di attacco di social engineering**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Vettore di attacco</p></th>
<th><p>Descrizione dell'utilizzo aziendale</p></th>
<th><p>Commenti</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p><em>Online</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Posta elettronica</p></td>
<td style="border:1px solid black;"><p>Tutti gli utenti hanno Microsoft Outlook® sui computer desktop.</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Internet</p></td>
<td style="border:1px solid black;"><p>Gli utenti mobili dispongono di OWA (Outlook Web Access) oltre all'accesso con client Outlook.</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Applicazioni popup</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p>Attualmente non sono state implementate barriere tecnologiche contro i popup.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Messaggistica immediata</p></td>
<td style="border:1px solid black;"><p>L'azienda permette l'uso non gestito di una serie di prodotti di messaggistica immediata.</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><em>Telefono</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>PBX</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Assistenza</p></td>
<td style="border:1px solid black;"><p>Attualmente l'assistenza è una funzione di supporto occasionale fornita dal reparto IT.</p></td>
<td style="border:1px solid black;"><p>È necessario estendere la fornitura del supporto oltre l'area IT.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><em>Gestione dei rifiuti</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Interno</p></td>
<td style="border:1px solid black;"><p>Ogni reparto gestisce autonomamente lo smaltimento dei rifiuti.</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Esterno</p></td>
<td style="border:1px solid black;"><p>I cassonetti sono posizionati all'esterno del sito aziendale. La raccolta dei rifiuti ha luogo il giovedì.</p></td>
<td style="border:1px solid black;"><p>Attualmente non disponiamo di spazio per i cassonetti all'interno del sito.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><em>Approcci personali</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Protezione fisica</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Protezione in ufficio</p></td>
<td style="border:1px solid black;"><p>Tutti gli uffici restano aperti durante l'intera giornata.    </p></td>
<td style="border:1px solid black;"><p>Il 25% del personale lavora da casa.    Non esistono standard scritti in merito alla protezione dei dipendenti che lavorano da casa.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Lavoratori da casa</p></td>
<td style="border:1px solid black;"><p>Non esistono protocolli aziendali sulla manutenzione interna per i lavoratori da casa.</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><em>Altri elementi/Specifici dell'azienda</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Franchising all'interno dell'azienda</p></td>
<td style="border:1px solid black;"><p>Tutto il catering viene gestito tramite una società in franchising.</p></td>
<td style="border:1px solid black;"><p>L'azienda non dispone di informazioni sul personale di questa società e non esistono criteri di protezione che riguardano queste persone.</p></td>
</tr>  
</tbody>  
</table>
  
Quando il Comitato direttivo per la protezione ha acquisito una buona comprensione delle vulnerabilità, può dunque elaborare una tabella sulle Vulnerabilità dell'azienda ai vettori di attacco di social engineering (riportata nell'esempio precedente). Nella tabella sono definiti i protocolli aziendali riguardanti le aree potenzialmente vulnerabili dell'azienda. La conoscenza delle vulnerabilità permette al comitato di elaborare un progetto di base sui potenziali requisiti per i criteri di protezione.
  
Il Comitato direttivo per la protezione deve prima identificare le aree che possono rappresentare un rischio per l'azienda. Il processo deve includere tutti i vettori di attacco identificati in questo documento e gli elementi specifici dell'azienda, ad esempio l'uso di terminali pubblici e le procedure di gestione dell'ufficio.
  
#### Valutazione dei rischi
  
AI fini della protezione è necessario che l'azienda valuti il livello di rischio che un attacco può comportare per l'azienda stessa. Sebbene la valutazione dei rischi debba essere scrupolosa non deve richiedere troppo tempo. In base al lavoro svolto dal Comitato direttivo per la protezione per identificare gli elementi essenziali di una struttura di gestione della protezione, è possibile suddividere in categorie tali rischi e assegnare loro delle priorità. Le categorie di rischio includono:
  
-   Informazioni riservate
  
-   Credibilità aziendale
  
-   Disponibilità aziendale
  
-   Risorse
  
-   Denaro
  
Le priorità vengono stabilite identificando il rischio e calcolando il costo di prevenzione del rischio stesso; se la prevenzione del rischio ha costi maggiori di quelli che comporterebbe il verificarsi del rischio stesso, essa non può essere giustificata. La valutazione dei rischi può essere molto utile nello sviluppo definitivo dei criteri di protezione.
  
Ad esempio, il Comitato direttivo per la protezione potrebbe evidenziare il pericolo legato alla presenza di visitatori alla reception. Per un'azienda che non prevede più di 20 visitatori lo scenario da considerare ipotizza un solo addetto alla reception, un registro degli accessi e alcuni badge numerati per i visitatori. Al contrario, per un'azienda che prevede 150 visitatori in un'ora potrebbe essere necessario considerare uno scenario che ipotizza più di un addetto alla reception e terminali per la registrazione automatica. Sebbene l'azienda più piccola non possa giustificare i costi dei terminali di registrazione automatica, quella più grande non può giustificare il costo delle opportunità di affari perse a causa di lunghi ritardi.
  
In alternativa, un'azienda che non riceve mai visitatori e non dispone di personale esterno potrebbe ritenere che il rischio di lasciare documenti stampati in una stampante centralizzata in attesa che vengano ritirati sia minimo. Tuttavia, un'azienda con un personale non dipendente numeroso, potrebbe ritenere che per eludere il rischio legato alla presenza di informazioni potenzialmente riservate in una stampante l'unico modo possibile sia installare dispositivi di stampa locali presso ogni scrivania. L'azienda può ovviare a questo rischio stabilendo che un membro del personale accompagni il visitatore durante l'intera permanenza in azienda. Questa soluzione è molto meno dispendiosa, eccetto che in termini di tempo del personale.
  
Sulla base della valutazione dell'azienda effettuata nella matrice Vulnerabilità dell'azienda ai vettori di attacco di social engineering, il Comitato direttivo per la protezione può definire i requisiti per i criteri, i tipi di rischi e i livelli di rischio per l'azienda, come indicato nella tabella seguente.
  
**Tabella 10. Matrice sui rischi e i requisiti del Comitato direttivo per la protezione**

<p> </p>
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
<th><p>Vettore di attacco</p></th>  
<th><p>Possibili requisiti per i criteri</p></th>  
<th><p>Tipo di rischio Informazioni riservate Credibilità aziendale Disponibilità aziendale Risorse Denaro</p></th>  
<th><p>Livello di rischio Alto = 5 Basso = 1</p></th>  
<th><p>Azione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p>Serie di criteri scritti per la protezione contro il social engineering</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p>Modifiche per rendere il rispetto dei criteri parte del contratto standard dei dipendenti</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p>Modifiche per rendere il rispetto dei criteri parte del contratto standard degli appaltatori</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><em>Online</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Posta elettronica</p></td>
<td style="border:1px solid black;"><p>Criteri relativi ai tipi di allegati e alle modalità di gestione</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Internet</p></td>
<td style="border:1px solid black;"><p>Criteri per l'uso di Internet</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Applicazioni popup</p></td>
<td style="border:1px solid black;"><p>Criteri per l'uso di Internet, con particolare attenzione alle contromisure in caso di visualizzazione di finestre di dialogo inattese</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Messaggistica immediata</p></td>
<td style="border:1px solid black;"><p>Criteri per i client di messaggistica immediata supportati e per quelli ammissibili</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><em>Telefono</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>PBX</p></td>
<td style="border:1px solid black;"><p>Criteri per la gestione del supporto PBX</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Assistenza</p></td>
<td style="border:1px solid black;"><p>Criteri per la concessione dell'accesso ai dati</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><em>Gestione dei rifiuti</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Carta</p></td>
<td style="border:1px solid black;"><p>Criteri per la gestione dei rifiuti cartacei</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p>Linee guida per la gestione dei cassonetti</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Supporti elettronici</p></td>
<td style="border:1px solid black;"><p>Criteri per la gestione dello smaltimento dei supporti elettronici</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><em>Approcci personali</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Protezione fisica</p></td>
<td style="border:1px solid black;"><p>Criteri per la gestione dei visitatori</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Protezione in ufficio</p></td>
<td style="border:1px solid black;"><p>Criteri per la gestione di ID utente e password. Ad esempio, non scrivere la password su un foglietto adesivo e non metterlo sul monitor</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Lavoratori da casa</p></td>
<td style="border:1px solid black;"><p>Criteri per l'uso di computer portatili all'esterno dell'azienda</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><em>Altri elementi/</em><br />
<em>Specifici dell'azienda</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Franchising all'interno dell'azienda</p></td>
<td style="border:1px solid black;"><p>Criteri per il controllo dei dipendenti in franchising all'interno dell'azienda</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
</tbody>  
</table>
  
Il Comitato direttivo per la protezione deve raggiungere il consenso sull'importanza di un rischio. Ciascun gruppo avrà opinioni diverse sui rischi che possono comportare le diverse minacce.
  
Per ulteriori informazioni sulle metodologie e gli strumenti di valutazione dei rischi, visitare il sito Web [*Guida alla gestione dei rischi di protezione*](http://go.microsoft.com/fwlink/?linkid=30794) all'indirizzo http://go.microsoft.com/fwlink/?linkid=30794.
  
#### Il social engineering nei criteri di protezione
  
La dirigenza e il personale IT di un'azienda devono sviluppare dei criteri di protezione efficace e agevolarne l'implementazione all'interno dell'organizzazione. A volte, il punto centrale dei criteri di protezione è costituito dai controlli tecnologici che aiutano a proteggersi contro le minacce tecnologiche, quali virus e worm. I controlli tecnologici aiutano a difendere le tecnologie, quali i file di dati, i programmi e i sistemi operativi. Le difese contro il social engineering devono aiutare ad anticipare gli attacchi generici di social engineering contro i membri del personale.
  
Il Comitato direttivo per la protezione conosce le aree di protezione essenziali e dispone della valutazione dei rischi; di conseguenza delega le attività di produzione delle procedure, dei processi e della documentazione aziendale. La tabella seguente illustra come il Comitato direttivo per la protezione, con l'ausilio dei gruppi di interesse, può definire la documentazione necessaria per supportare i criteri di protezione.
  
**Tabella 11. Requisiti del Comitato direttivo per la protezione per i documenti e le procedure**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Requisiti per i criteri</p></th>  
<th><p>Requisiti per le procedure / documenti</p></th>  
<th><p>Azione il / data</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Serie di criteri scritti per la protezione contro il social engineering</p></td>
<td style="border:1px solid black;"><p>nessuna</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Modifiche per rendere il rispetto dei criteri parte del contratto standard dei dipendenti</p></td>
<td style="border:1px solid black;"><ol>
<li><p>Testo dei requisiti per i nuovi contratti (legale)</p></li>  
<li><p>Nuovo formato dei contratti per gli appaltatori</p></li>
</ol></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Modifiche per rendere il rispetto dei criteri parte del contratto standard degli appaltatori</p></td>
<td style="border:1px solid black;"><ol>
<li><p>Testo dei requisiti per i nuovi contratti (legale)</p></li>  
<li><p>Nuovo formato dei contratti per gli appaltatori</p></li>
</ol></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Criteri per la gestione dei visitatori</p></td>
<td style="border:1px solid black;"><ol>
<li><p>Procedura per la firma in ingresso e in uscita dei visitatori</p></li>  
<li><p>Procedura per l'accompagnamento dei visitatori</p></li>
</ol></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Linee guida per la gestione dei cassonetti</p></td>
<td style="border:1px solid black;"><ol>
<li><p>Procedura per lo smaltimento dei rifiuti cartacei (vedere Dati)</p></li>  
<li><p>Procedura per lo smaltimento dei supporti elettronici (vedere Dati)</p></li>
</ol></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Criteri per la concessione dell'accesso ai dati</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Criteri per la gestione dei rifiuti cartacei</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Criteri per la gestione dello smaltimento dei supporti elettronici</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Criteri per l'uso di Internet, con particolare attenzione alle contromisure in caso di visualizzazione di finestre di dialogo inattese</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Criteri per la gestione di ID utente e password. Ad esempio, non scrivere la password su un foglietto adesivo e metterlo sul monitor, e così via.</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Criteri per l'uso di computer portatili all'esterno dell'azienda</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Criteri per la gestione dei problemi di connessione alle applicazioni di partner (banche, istituti finanziari, acquisti, gestione delle scorte)</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
</tbody>  
</table>
  
È evidente che questo elenco potrebbe diventare piuttosto lungo. Si può decidere di assumere degli esperti per accelerare la realizzazione di questa parte del processo. Il Comitato direttivo per la protezione deve concentrare la propria attenzione sulle aree che considera di elevato valore, in base al processo di valutazione dei rischi.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Implementazione delle difese contro le minacce del social engineering
  
Dopo avere scritto e concordato i criteri di protezione, essi devono essere resi disponibili per il personale e il loro rispetto deve essere garantito. Sebbene sia possibile implementare i controlli tecnici senza conoscere i dipendenti aziendali, è importante ottenere il loro sostegno se si desidera erigere difese efficaci contro il social engineering. Per supportare l'implementazione è fondamentale sviluppare dei protocolli di risposta agli incidenti per il personale di assistenza.
  
#### Consapevolezza
  
Nulla può sostituire una buona campagna di promozione della consapevolezza quando vengono implementati gli elementi dei criteri di protezione riguardanti il social engineering. Anche l'implementazione è, ovviamente, una forma di social engineering, quindi il personale deve essere addestrato affinché conosca i criteri e capisca perché è stato deciso di applicarli, oltre che come deve reagire di fronte a un sospetto attacco. L'elemento chiave di un attacco di social engineering è la fiducia: la vittima si fida del pirata informatico. Per resistere a questo tipo di attacco è necessario stimolare il sano scetticismo presente nel personale verso qualsiasi cosa esca dall'ordinario; è importante invece generare fiducia nell'infrastruttura aziendale di supporto IT.
  
Gli elementi di una campagna di promozione della consapevolezza dipendono da come vengono comunicate le informazioni al personale aziendale. È possibile scegliere una formazione strutturata, meno riunioni formali, campagne con affissioni e altri eventi per pubblicizzare i criteri di protezione. Più si rafforzano i messaggi contenuti nei criteri, più la loro implementazione avrà esiti positivi. Sebbene sia possibile promuovere la consapevolezza nei confronti della protezione avvalendosi di un grande evento, è altrettanto importante che la protezione mantenga un ruolo di primo piano nell'ordine del giorno della dirigenza e del personale. La protezione fa parte della mentalità dell'azienda quindi è necessario assicurarsi del fatto che i suggerimenti su come mantenere viva la consapevolezza nei confronti della protezione devono provenire da ogni dipendente aziendale. Tutti i reparti aziendali e i diversi tipi di utenti, in particolare quelli che lavorano all'esterno dell'ufficio, devono manifestare la propria opinione.
  
#### Gestione degli incidenti
  
Se si verifica un attacco di social engineering è necessario assicurarsi che il personale di assistenza sappia come gestire l'incidente. Nelle procedure associate ai criteri di protezione devono essere inclusi dei protocolli di risposta; tuttavia per gestione degli incidenti si intende che l'attacco deve essere il punto di partenza per avviare ulteriori revisioni della protezione. La protezione è un viaggio piuttosto che una destinazione, infatti i vettori di attacco cambiano.
  
Ogni incidente fornisce un nuovo input per una revisione costante della protezione nell'ambito del modello di risposta agli incidenti, illustrato nella figura seguente.
  
![](images/Cc875841.HPISET06(it-it,TechNet.10).gif)
  
**Figura 6. Modello di risposta agli incidenti**
  
Mano a mano che si verificano nuovi incidenti il Comitato direttivo per la protezione deve valutare se essi rappresentano dei rischi nuovi o modificati per l'azienda e decidere di creare o rinnovare i criteri e le procedure in base ai risultati ottenuti. Qualsiasi emendamento ai criteri di protezione deve essere conforme agli standard aziendali di gestione delle modifiche.
  
Per gestire un incidente il personale dell'assistenza deve disporre di un protocollo di reporting degli incidenti efficace, che preveda la registrazione delle informazioni seguenti:
  
-   Nome dell'obiettivo dell'attacco
  
-   Reparto obiettivo dell'attacco
  
-   Data
  
-   Vettore di attacco
  
-   Descrizione dell'attacco
  
-   Descrizione del risultato
  
-   Effetto dell'attacco
  
-   Raccomandazioni
  
Registrando gli incidenti è possibile identificare i modelli e probabilmente prevenire ulteriori attacchi. Nell'Appendice 1 al presente documento è incluso un modello del modulo per il reporting degli incidenti.
  
#### Considerazioni operative
  
Quando la protezione viene riesaminata, è possibile diventare eccessivamente sensibili alle miriadi di potenziali minacce contro l'azienda. I criteri di protezione aziendale devono affermare che l'azienda ha lo scopo di svolgere affari. Se le proposte dell'azienda in merito alla protezione dovessero influire negativamente sulla redditività o sull'agilità commerciale dell'organizzazione, potrebbe essere necessario rivalutare i rischi. È fondamentale raggiungere un equilibrio tra protezione e usabilità operativa.
  
È anche importante rendersi conto del fatto che avere la reputazione di azienda consapevole della protezione può avere vantaggi in termini commerciali. Di conseguenza, non soltanto i pirati informatici saranno scoraggiati, ma il profilo commerciale dell'azienda migliorerà agli occhi dei clienti e dei partner.
  
#### Social engineering e il modello a più livelli di difesa
  
Il modello a più livelli di difesa suddivide in categorie le soluzioni di protezione contro i vettori di attacco, ovvero le aree vulnerabili che i pirati informatici potrebbero utilizzare per minacciare l'ambiente informatico. Tra i vettori di attacco sono inclusi:
  
-   **Criteri, procedure e consapevolezza**. Le regole scritte sviluppate dall'azienda per gestire tutte le aree di protezione e il programma di formazione che verrà applicato per aiutare i membri del personale a conoscere, comprendere e implementare queste regole.
  
-   **Protezione fisica**. Le barriere che consentono di gestire l'accesso alle strutture e alle risorse aziendali. È importante ricordare questo elemento: se si posizionano dei contenitori per i rifiuti all'esterno dell'azienda, ad esempio, essi si troveranno al di fuori della protezione fisica dell'azienda.
  
-   **Dati**. Le informazioni aziendali, ovvero i dettagli su account, posta, e così via. Quando vengono considerate le minacce derivanti dal social engineering è necessario includere nella pianificazione della protezione dei dati sia i materiali cartacei che quelli elettronici.
  
-   **Applicazione**. I programmi eseguiti dagli utenti aziendali. È necessario considerare in che modo i pirati informatici dediti al social engineering possono danneggiare applicazioni, ad esempio le applicazioni di posta elettronica e di messaggistica immediata.
  
-   **Host**. I server e i client utilizzati all'interno dell'organizzazione. Garantire la protezione degli utenti contro attacchi diretti su questi computer definendo delle linee guida rigorose sul software da utilizzare nei computer aziendali e su come gestire i dispositivi di protezione, quali ID e password.
  
-   **Rete interna**. La rete mediante la quale comunica il computer. Può trattarsi di una rete locale, wireless o di tipo WAN (Wide Area Network). Negli ultimi anni, la rete interna è divenuta meno "interna" a causa della diffusione del lavoro da casa e mobile. Pertanto, è necessario assicurarsi che gli utenti comprendano cosa devono fare per lavorare in sicurezza in tutti gli ambienti di rete.
  
-   **Perimetro**. Il punto di contatto tra le reti interne e quelle esterne, ad esempio Internet o le reti che appartengono ai partner commerciali dell'azienda come parte di una extranet. Gli attacchi di social engineering spesso tentano di violare il perimetro per attaccare dati, applicazioni e host mediante la rete interna.
  
![](images/Cc875841.HPISET07(it-it,TechNet.10).gif)
  
**Figure 7. Modello di protezione a più livelli di difesa**
  
Quando si progettano i sistemi di protezione, il modello a più livelli di difesa può aiutare a visualizzare le aree aziendali a rischio di minaccia. Il modello non è stato concepito specificamente per le minacce di social engineering, tuttavia ogni livello dovrebbe prevedere delle difese contro il social engineering.
  
Le difese che costituiscono il modello sono i criteri e le procedure di protezione e la consapevolezza dei rischi. Queste difese sono studiate per il personale dell'organizzazione e indicano cosa fare, quando fare qualcosa e chi deve farlo. I restanti livelli possono ottimizzare le difese, tuttavia la protezione deriva fondamentalmente dalla presenza di regole ben strutturate e note a tutti, volte a proteggere l'ambiente IT.
  
Per ulteriori informazioni sul modello di protezione a più livelli di difesa, vedere la pagina [Security Management SMF](http://go.microsoft.com/fwlink/?linkid=37696) (in inglese) su Microsoft TechNet all'indirizzo http://go.microsoft.com/fwlink/?linkid=37696.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Appendice 1: Elenchi di controllo dei criteri di protezione contro le minacce del social engineering
  
Nei documenti sono contenute diverse tabelle che vengono utilizzate per determinare le vulnerabilità del social engineering e i requisiti dei criteri di protezione. Le versioni di esempio delle tabelle sono disponibili in questa appendice affinché vengano copiate e popolate dalla singola azienda.
  
#### Vulnerabilità dell'azienda ai vettori di attacco di social engineering

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Vettore di attacco</p></th>  
<th><p>Descrizione dell'uso aziendale</p></th>  
<th><p>Commenti</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p><em>Online</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Posta elettronica</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Internet</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Applicazioni popup</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Messaggistica immediata</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><em>Telefono</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>PBX</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Assistenza</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><em>Gestione dei rifiuti</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Interno</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Esterno</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p><em>Approcci personali</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Protezione fisica</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Protezione in ufficio</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><em>Altri elementi/Specifici dell'azienda</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
</tbody>  
</table>
  
#### Matrice sui rischi e i requisiti del Comitato direttivo per la protezione

<p> </p>
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
<th><p>Vettore di attacco</p></th>  
<th><p>Possibili requisiti per i criteri</p></th>  
<th><p>Tipo di rischio Informazioni riservate Credibilità aziendale Disponibilità aziendale Risorse Denaro</p></th>  
<th><p>Livello di rischio Alto = 5 Basso = 1</p></th>  
<th><p>Azione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p><em>Online</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><em>Telefono</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><em>Gestione dei rifiuti</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><em>Approcci personali</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p><em>Altri elementi/</em><br />
<em>Specifici dell'azienda</em></p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
</tbody>  
</table>
  
#### Requisiti del Comitato direttivo per la protezione per i documenti e le procedure

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Requisiti per i criteri</p></th>  
<th><p>Requisiti per le procedure / documenti</p></th>  
<th><p>Azione il / data</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
</tbody>  
</table>
  
#### Elenco di controllo dell'implementazione dei criteri di protezione

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Azione</p></th>  
<th><p>Descrizione</p></th>  
<th><p>Azione il / data</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sviluppo dei criteri di protezione online</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Sviluppo dei criteri di protezione fisica</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sviluppo dei criteri di protezione telefonica</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Sviluppo dei criteri di protezione per la gestione dei rifiuti</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sviluppo dei criteri di gestione della protezione dell'assistenza</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Sviluppo di un modello di risposta agli incidenti</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Sviluppo di una campagna di promozione della consapevolezza</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>...</p></td>
<td style="border:1px solid black;"><p> </p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
</tbody>  
</table>
  
#### Report sugli incidenti

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Rappresentante dell'assistenza</p></td>
<td style="border:1px solid black;"><p>                     </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Nome dell'obiettivo dell'attacco</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Reparto obiettivo dell'attacco</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Data</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Vettore di attacco</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Descrizione dell'attacco</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Descrizione del risultato</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Effetto dell'attacco</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Raccomandazioni</p></td>
<td style="border:1px solid black;"><p> </p></td>
</tr>  
</tbody>  
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Appendice 2: Glossario

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Termine</p></th>  
<th><p>Definizione</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>accesso</p></td>
<td style="border:1px solid black;"><p>In termini di privacy, la capacità di una singola persona di visualizzare, modificare e contestare la precisione e la completezza delle informazioni personali raccolte sull'utente. L'accesso è un elemento dei principi relativi alle Fair Information Practices.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>software antivirus (AV)</p></td>
<td style="border:1px solid black;"><p>Programma concepito per rilevare e rispondere agli attacchi di malware, quali virus e worm. Le risposte possono comprendere il blocco dell'accesso utente ai file infetti, la pulizia dei file o dei computer infetti, la comunicazione all'utente sul rilevamento di un programma infetto.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>attacco</p></td>
<td style="border:1px solid black;"><p>Tentativo deliberato di compromettere la sicurezza di un computer o privare altre persone dell'uso del sistema.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>autenticazione</p></td>
<td style="border:1px solid black;"><p>Processo di convalida delle credenziali di una persona, di un processo di computer o di un dispositivo. Per l'autenticazione è necessario che la persona, il processo o il dispositivo che invia una richiesta fornisca credenziali che comprovino i contenuti e il mittente. Le forme più comuni di credenziali sono le firme digitali, smart card, dati biometrici e una combinazione di nomi utente e password.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>autorizzazione</p></td>
<td style="border:1px solid black;"><p>Processo che concede a una persona, al processo di un computer o a un dispositivo, l'accesso a determinati servizi, informazioni e funzionalità. L'autorizzazione viene concessa in base all'identità della persona, del processo di un computer o del dispositivo che richiede l'accesso, che viene verificato mediante autenticazione.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>gestione delle modifiche</p></td>
<td style="border:1px solid black;"><p>La procedura di gestione delle modifiche con l'ausilio di tecniche e metodi testati al fine di evitare nuovi errori e ridurre al minimo l'impatto delle modifiche.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>protezione del computer</p></td>
<td style="border:1px solid black;"><p>Protezione delle risorse informatiche mediante la tecnologia, i processi e la formazione.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>cracker</p></td>
<td style="border:1px solid black;"><p>Malintenzionato che si introduce in un computer avvalendosi di strategie tecnologiche o di social engineering.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>download</p></td>
<td style="border:1px solid black;"><p>Trasferimento della copia di un file da un computer remoto al computer richiedente per mezzo di un modem o di una rete.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>extranet</p></td>
<td style="border:1px solid black;"><p>Estensione dell'intranet di un'organizzazione utilizzata per facilitare le comunicazioni con i partner affidabili dell'organizzazione. Grazie all'extranet i partner affidabili possono ottenere un accesso limitato ai dati aziendali interni dell'organizzazione.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>firewall</p></td>
<td style="border:1px solid black;"><p>Soluzione di protezione che consente di isolare una parte di rete da un'altra, permettendo esclusivamente il passaggio del traffico autorizzato in base alle regole di filtraggio del traffico.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>malware</p></td>
<td style="border:1px solid black;"><p>Software che, se eseguito, realizza l'intento deliberatamente dannoso di un attacker. Ad esempio, virus, worm e Trojan horse sono codice dannoso.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>accesso alla rete</p></td>
<td style="border:1px solid black;"><p>Processo per accedere a un computer mediante una rete. Solitamente un utente prima accede interattivamente a un computer locale, quindi fornisce le credenziali di accesso per un altro computer della rete, ad esempio un server, che è autorizzato a utilizzare.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>password</p></td>
<td style="border:1px solid black;"><p>Stringa di caratteri immessa da un utente per verificare la sua identità in una rete o in un computer locale. Vedere anche password complessa.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>autorizzazioni</p></td>
<td style="border:1px solid black;"><p>Autorizzazione a eseguire operazioni associate a una determinata risorsa condivisa, quali file, directory o stampanti. Le autorizzazioni devono essere concesse dall'amministratore di sistema ai singoli account utente e gruppi amministrativi.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>PIN</p></td>
<td style="border:1px solid black;"><p>Codice di identificazione segreto, simile a una password, assegnato a un utente autorizzato. Il PIN viene utilizzato in combinazione con una carta bancomat o con una smart card, ad esempio per sbloccare una funzionalità autorizzata quale l'accesso a un conto bancario.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>informazioni personali d'identità</p></td>
<td style="border:1px solid black;"><p>Qualsiasi informazione correlata a una persona identificata o identificabile. Queste informazioni possono includere nome, paese, indirizzo, indirizzo di posta elettronica, numero di carta di credito, numero di previdenza sociale, codice fiscale, indirizzo IP, o qualsiasi identificativo univoco associato alle informazioni personali contenute in un altro sistema. Denominate anche informazioni o dati personali.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>informazioni personali</p></td>
<td style="border:1px solid black;"><p>Vedere informazioni personali d'identità.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>phreaker</p></td>
<td style="border:1px solid black;"><p>Utente malintenzionato che utilizza senza autorizzazione le infrastrutture PBX per fare telefonate.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>phisher</p></td>
<td style="border:1px solid black;"><p>Utente malintenzionato o sito Web dannoso volti a ingannare le persone affinché rivelino le proprie informazioni personali, quali password di account e numeri di carta di credito. Un phisher solitamente si avvale di messaggi di posta elettronica ingannevoli o pubblicità online come esca per attirare gli utenti non sospettosi in siti Web dannosi, dove gli utenti vengono poi portati a fornire informazioni personali.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>vulnerabilità fisica</p></td>
<td style="border:1px solid black;"><p>Incapacità di fornire protezione fisica a un computer, ad esempio lasciare che una workstation funzioni, senza dispositivi di protezione, in uno spazio accessibile agli utenti non autorizzati.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>privacy</p></td>
<td style="border:1px solid black;"><p>Il controllo dei clienti sulla raccolta, l'uso e la distribuzione delle proprie informazioni personali.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>rischio per la protezione del sistema</p></td>
<td style="border:1px solid black;"><p>Una vulnerabilità del software risolvibile tramite un avviso, un service pack o un aggiornamento della protezione Microsoft.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>messaggi indesiderati</p></td>
<td style="border:1px solid black;"><p>Messaggi di posta elettronica indesiderati di natura pubblicitaria. Definita anche posta indesiderata.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>spoofing</p></td>
<td style="border:1px solid black;"><p>Falsificazione di una trasmissione in modo che sembri provenire da un utente che in realtà non è l'utente che ha effettivamente eseguito l'azione.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>spyware</p></td>
<td style="border:1px solid black;"><p>Software in grado di visualizzare messaggi pubblicitari (ad esempio popup pubblicitari), raccogliere informazioni personali o modificare le impostazioni del computer, generalmente senza richiedere l'autorizzazione dell'utente in modo appropriato.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>password complessa</p></td>
<td style="border:1px solid black;"><p>Password che fornisce una difesa efficace contro l'accesso non autorizzato a una risorsa. Una password complessa si compone di almeno sei caratteri, non contiene il nome dell'account utente né parziale, né completo, inoltre contiene almeno tre delle seguenti categorie di caratteri: lettere maiuscole, lettere minuscole, numeri in base 10 e simboli presenti sulla tastiera, ad esempio !, @ e #.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Trojan horse</p></td>
<td style="border:1px solid black;"><p>Programma che sembra utile o innocuo ma che in realtà contiene codice nascosto e mirato a sfruttare o danneggiare il computer su cui viene eseguito. I programmi Trojan horse vengono più comunemente consegnati agli utenti tramite messaggi di posta elettronica che travisano lo scopo e la funzione del programma. Denominato anche codice Trojan.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>aggiornamento</p></td>
<td style="border:1px solid black;"><p>Pacchetto software che sostituisce una versione già installata con un versione più recente dello stesso software. Il processo di aggiornamento solitamente lascia intatti i dati e le preferenze del cliente, ma sostituisce il software esistente con la versione più recente.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>ID utente</p></td>
<td style="border:1px solid black;"><p>Nome univoco mediante il quale un utente può accedere a un computer.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>virus</p></td>
<td style="border:1px solid black;"><p>Codice scritto con l'esplicita intenzione di replicarsi. Un virus tenta di diffondersi da un computer all'altro inserendosi in un programma host. Può danneggiare hardware, software o dati. Confrontare con worm. Vedere anche la definizione fornita da Virus Info Alliance (f-secure.com).</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>vulnerabilità</p></td>
<td style="border:1px solid black;"><p>Qualsiasi punto debole, processo o atto amministrativo, oppure esposizione fisica che rende un computer predisposto a essere soggetto nell'uso a una minaccia.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>worm</p></td>
<td style="border:1px solid black;"><p>Codice dannoso che si autopropaga e che può distribuirsi automaticamente da un computer all'altro mediante le connessioni di rete. Un worm può intraprendere azioni dannose come utilizzare le risorse di una rete o di un sistema locale, causando un attacco di tipo negazione del servizio. Confrontare con virus.</p></td>
</tr>  
</tbody>  
</table>
  
**Download**
  
[Scarica il documento How to Protect Insiders from Social Engineering Threats (in inglese)](http://go.microsoft.com/fwlink/?linkid=71053)
  
[](#mainsection)[Inizio pagina](#mainsection)
