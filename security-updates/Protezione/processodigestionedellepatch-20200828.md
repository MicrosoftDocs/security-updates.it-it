---
TOCTitle: Processo di gestione delle patch
Title: Processo di gestione delle patch
ms:assetid: '02c8db36-3545-42df-9c89-d5bfd9b2661c'
ms:contentKeyID: 20200828
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536229(v=TechNet.10)'
---

Processo di gestione delle patch
================================

Introduzione
------------

Aggiornato: 1 giugno 2007

##### In questa pagina

[](#ezc)[Argomenti del modulo](#ezc)
[](#e4c)[Obiettivi](#e4c)
[](#epd)[Ambito di applicazione](#epd)
[](#esd)[Utilizzo del modulo](#esd)
[](#e3f)[Panoramica sulla gestione degli aggiornamenti](#e3f)
[](#eyg)[Terminologia relativa alla protezione](#eyg)
[](#eigac)[In che modo Microsoft provvede a correggere il software dopo il rilascio](#eigac)
[](#ealac)[L'importanza di una gestione degli aggiornamenti proattiva](#ealac)
[](#eabae)[Requisiti per una corretta gestione degli aggiornamenti](#eabae)
[](#ekbae)[Operazioni efficienti](#ekbae)
[](#enbae)[Strumenti e tecnologie](#enbae)
[](#epoae)[Processi efficienti di gestione dei progetti](#epoae)
[](#eyoae)[L'approccio in quattro fasi alla gestione degli aggiornamenti](#eyoae)
[](#eqqae)[Risorse correlate](#eqqae)
[](#eyqae)[Commenti e suggerimenti](#eyqae)

Argomenti del modulo
--------------------

In questo modulo viene presentata la gestione degli aggiornamenti e viene spiegato perché sia essenziale per i sistemi aziendali. Viene illustrata la terminologia relativa alla protezione e vengono descritte le vulnerabilità comuni e i tipi di pericoli. Inoltre vengono spiegati i processi utilizzati in Microsoft per sviluppare e rilasciare gli aggiornamenti software e viene mostrato come siano correlati alle azioni da intraprendere per una gestione proattiva degli aggiornamenti per la protezione. Infine viene presentato il processo di gestione degli aggiornamenti in quattro fasi consigliato da Microsoft. Ulteriori dettagli in merito sono contenuti nei moduli successivi.

Scopo di questo modulo è presentare i problemi principali relativi alla gestione degli aggiornamenti in un ambiente basato sul sistema operativo Microsoft Windows e descrivere gli strumenti, le tecnologie e i processi principali consigliati da Microsoft a supporto di questa attività.

[](#top)[Inizio pagina](#top)

Obiettivi
---------

Il modulo consente di:

-   Esaminare le procedure di attivazione di una gestione IT sicura e i costi di una protezione non adeguata.

-   Capire cosa significa il termine "gestione degli aggiornamenti" e la terminologia di base relativa alla protezione.

-   Analizzare le principali vulnerabilità e la loro relazione con le valutazioni di gravità Microsoft, le categorie di pericoli e i tipi di agenti di pericolo esistenti attualmente.

-   Esaminare in che modo Microsoft provvede a correggere il software dopo il rilascio e la terminologia Microsoft relativa agli aggiornamenti software.

-   Vedere gli esempi sull'importanza della gestione proattiva degli aggiornamenti per la protezione.

-   Stabilire le tecnologie e gli strumenti di gestione degli aggiornamenti più appropriati per il proprio ambiente.

-   Descrivere gli elementi di base dell'approccio in quattro fasi alla gestione degli aggiornamenti.

[](#top)[Inizio pagina](#top)

Ambito di applicazione
----------------------

Questo modulo si applica a tutti i prodotti e a tutte le tecnologie Microsoft.

[](#top)[Inizio pagina](#top)

Utilizzo del modulo
-------------------

In questo modulo viene presentata un'introduzione alla gestione degli aggiornamenti per la protezione, comprensiva dei termini e dei concetti chiave, degli strumenti e delle tecnologie, nonché una panoramica del processo consigliato di gestione degli aggiornamenti articolato in quattro fasi. Vengono forniti esempi di attacchi storici e viene indicato in che modo li si sarebbe potuti evitare se fosse stata attuata una gestione appropriata e proattiva degli aggiornamenti per la protezione.

Per trarre il massimo vantaggio dal modulo:

-   Leggere il documento "MOF Executive Overview" all'indirizzo <http://technet.microsoft.com/en-us/library/cc543224.aspx> (in inglese). In questo articolo viene descritta l'origine di Microsoft Operations Framework (MOF), ne vengono spiegati gli obiettivi di progettazione e vengono riassunti il modello di processo, il modello di team e il modello di rischio. Sono inoltre indicati collegamenti ad altri white paper che trattano del modello di processo MOF (Microsoft Operations Framework), delle funzioni di gestione dei servizi (SMF, Service Management Function) MOF e del modello di team MOF. Da ultimo, vengono date indicazioni per lo svolgimento di attività IT efficienti. Tre delle funzioni SMF - Gestione dei cambiamenti, Gestione della configurazione e Gestione del rilascio - rivestono un'importanza cruciale per la gestione degli aggiornamenti.

-   Leggere il white paper "Standardizing the Patch Experience" all'indirizzo <http://technet.microsoft.com/en-us/library/cc700838.aspx> (in inglese). In questo documento sono riportati i miglioramenti in atto da parte dei gruppi di produzione in seno a Microsoft finalizzati alla semplificazione e standardizzazione dell'attività di aggiornamento totale e costante dei sistemi. L'articolo funge anche da mappa per aiutare l'utente a pianificare e sfruttare i miglioramenti apportati nel processo di gestione degli aggiornamenti, man mano che si rendono disponibili.

-   Leggere l'articolo "Deploying Microsoft Windows Server Update Services" che può essere scaricato dal sito Microsoft TechNet all'indirizzo <http://technet.microsoft.com/en-us/library/cc720507.aspx> (in inglese)

-   Leggere l'introduzione "Microsoft Baseline Security Analyzer", all'indirizzo <http://technet.microsoft.com/security/cc184924.aspx> (in inglese).

-   Leggere gli articoli "SMS 2003 Concepts" e "SMS 2003: Planning and Deployment Guide" all'indirizzo <http://technet.microsoft.com/en-us/library/cc181834.aspx> (in inglese).

-   Leggere i quattro moduli elencati qui di seguito in cui viene descritto dettagliatamente il processo di gestione degli aggiornamenti in quattro fasi:

    -   [Fase 1 del processo di gestione degli aggiornamenti - Valutazione"](http://technet.microsoft.com/it-it/library/cc700830.aspx)

    -   ["Fase 2 del processo di gestione degli aggiornamenti - Identificazione"](http://www.microsoft.com/italy/technet/security/guidance/patchmanagement/secmod195.mspx)

    -   ["Fase 3 del processo di gestione degli aggiornamenti - Stima e pianificazione"](http://technet.microsoft.com/it-it/library/cc700840.aspx)

    -   ["Fase 4 del processo di gestione degli aggiornamenti - Distribuzione"](http://technet.microsoft.com/it-it/library/cc700833.aspx)

-   Utilizzare le Technical Library WSUS e SMS per altri materiali di riferimento specifici. Queste librerie si trovano all'indirizzo:

    -   [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese)

    -   [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese)

[](#top)[Inizio pagina](#top)

Panoramica sulla gestione degli aggiornamenti
---------------------------------------------

Con gestione degli aggiornamenti si intende il processo di controllo della distribuzione e manutenzione dei rilasci software provvisori negli ambienti di produzione. Questo processo aiuta a mantenere l'efficienza operativa, a superare le vulnerabilità della protezione e a conservare la stabilità dell'ambiente di produzione.

Se l'organizzazione non è in grado di stabilire e mantenere un livello noto di affidabilità all'interno dei propri sistemi operativi e del software applicativo, potrebbe trovarsi esposta a numerose falle in termini di protezione che, se sfruttate, potrebbero portare a perdite economiche e di proprietà intellettuale. Per ridurre al minimo questo pericolo è necessario configurare correttamente i sistemi, utilizzare il software più recente e installare gli aggiornamenti consigliati.

Al momento di stabilire il potenziale impatto finanziario di una cattiva gestione degli aggiornamenti, è opportuno considerare i seguenti aspetti:

-   Tempi di inattività:

    Quanto costano i tempi di inattività dei computer nell'ambiente? Cosa accade se vengono interrotti sistemi aziendali critici? Stabilire il costo dell'opportunità di una mancata produttività degli utenti finali, della perdita di transazioni su sistemi critici e della perdita di opportunità commerciali durante un incidente. La maggior parte degli attacchi provoca tempi di inattività, a causa dell'attacco stesso o delle corrispondenti azioni di riparazione richieste per il ripristino. Alcuni attacchi hanno lasciato i computer inattivi per diversi giorni.

-   Tempi di riparazione:

    Quanto costa risolvere un problema di vasta portata che interessa l'ambiente? Quanto costa reinstallare un computer? E se si dovessero reinstallare tutti i computer? Molti attacchi alla protezione richiedono una reinstallazione completa per essere certi che non abbiano lasciato punti deboli attraverso i quali possano giungere nuovi pericoli.

-   Integrità dei dati dubbia:

    Nel caso in cui un attacco danneggi l'integrità dei dati, qual è il costo del loro recupero dall'ultimo backup corretto conosciuto o della conferma della loro correttezza ai clienti e ai partner?

-   Perdita di credibilità:

    Quanto costa la perdita di credibilità nei confronti dei clienti? Qual è il costo della perdita di uno o più clienti?

-   Pubbliche relazioni negative:

    Qual è l'impatto, sull'organizzazione, di relazioni pubbliche negative? Di quanto potrebbe scendere il valore o la reputazione dell'azienda se viene vista come partner non affidabile? Quale sarebbe l'impatto della mancata protezione delle informazioni personali dei propri clienti, quali ad esempio i numeri delle carte di credito?

-   Difese legali:

    Quale potrebbe essere il costo della difesa dell'organizzazione in caso di un'azione legale intentata a seguito di un attacco? Le organizzazioni che forniscono servizi importanti ad altri hanno visto mettere sotto processo la gestione (o la mancanza di gestione) degli aggiornamenti.

-   Furto della proprietà intellettuale:

    Quali sono i costi da sostenere nel caso in cui la proprietà intellettuale dell'organizzazione venga rubata o distrutta?

La valutazione e la gestione dell'integrità del software in un ambiente di rete tramite un programma ben definito di gestione degli aggiornamenti è il primo passo importante per assicurare la protezione delle informazioni, a prescindere dalle restrizioni all'accesso fisico a un computer.

[](#top)[Inizio pagina](#top)

Terminologia relativa alla protezione
-------------------------------------

In questa sezione vengono spiegati i termini chiave da recepire quando si attua il processo di gestione degli aggiornamenti per la protezione. Nella Tabella 1 vengono descritti i termini chiave sulla protezione utilizzati in questi moduli.

**Tabella 1: Termini importanti sulla protezione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Termine</th>
<th style="border:1px solid black;" >Definizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Vulnerabilità</td>
<td style="border:1px solid black;">Software, hardware, una procedura poco sicura, una funzione o una configurazione che potrebbe costituire un punto debole sfruttabile durante un attacco. Chiamata anche esposizione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pericolo</td>
<td style="border:1px solid black;">Una fonte di pericolo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Agente di pericolo</td>
<td style="border:1px solid black;">La persona o il processo che attacca un sistema sfruttando una sua vulnerabilità, violando il criterio di protezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Attacco</td>
<td style="border:1px solid black;">Un agente di pericolo che tenta di sfruttare le vulnerabilità per fini indesiderati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Contromisura</td>
<td style="border:1px solid black;">Configurazioni software, hardware o procedure che riducono il rischio in un ambiente di computer. Chiamata anche protezione o attenuazione.</td>
</tr>
</tbody>
</table>
  
### Vulnerabilità
  
Il software può diventare vulnerabile a un attacco per diversi motivi. Nella Tabella 2 sono elencate diverse tipiche vulnerabilità software.
  
**Tabella 2: Vulnerabilità software**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Termine</th>
<th style="border:1px solid black;" >Definizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Sovraccarico del buffer (overflow)</td>
<td style="border:1px solid black;">Un buffer non controllato in un programma che può sovrascrivere il codice del programma con nuovi dati. Se il codice del programma viene sovrascritto con un nuovo codice eseguibile, il funzionamento del programma viene cambiato secondo le intenzioni del pirata informatico.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Incremento dei privilegi (escalation)</td>
<td style="border:1px solid black;">Permette agli utenti o ai pirati informatici di ottenere privilegi superiori in determinate circostanze.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Errore di convalida (codice sorgente)</td>
<td style="border:1px solid black;">Permette a dati non validi di avere conseguenze indesiderate.</td>
</tr>
</tbody>
</table>
  
### Valutazione della gravità della vulnerabilità di MSRC
  
Microsoft Security Response Center (MSRC) si serve della valutazione della gravità per aiutare gli utenti a stabilire la gravità delle vulnerabilità e l'urgenza dei relativi aggiornamenti software. Nella Tabella 3 sono elencate le valutazioni utilizzate da MSRC per classificare la gravità di una vulnerabilità.
  
**Tabella 3: Valutazioni della gravità della vulnerabilità**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Valutazione</th>
<th style="border:1px solid black;" >Definizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Critica</td>
<td style="border:1px solid black;">Una vulnerabilità che, se sfruttata, potrebbe portare alla propagazione di un worm Internet senza azioni da parte dell'utente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Importante</td>
<td style="border:1px solid black;">Una vulnerabilità che, se sfruttata, potrebbe compromettere la riservatezza, l'integrità o la disponibilità dei dati dell'utente o delle risorse di elaborazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Moderata</td>
<td style="border:1px solid black;">Il pericolo è attenuato molto da fattori quali una configurazione predefinita, il controllo o la difficoltà di sfruttare il punto debole.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Bassa</td>
<td style="border:1px solid black;">Una vulnerabilità molto difficile da sfruttare o il cui impatto è minimo.</td>
</tr>
</tbody>
</table>
  
Per ulteriori informazioni sulle valutazioni della gravità della vulnerabilità di MSRC, vedere il bollettino sulla sicurezza Severity Rating System di Microsoft Security Response Center all'indirizzo: <http://www.microsoft.com/technet/security/bulletin/rating.mspx>.
  
### Categorie di pericolo
  
Microsoft ha sviluppato il modello STRIDE, riassunto nella Tabella 4, per classificare i pericoli software. Queste categorie vengono spesso utilizzate nei bollettini sulla sicurezza Microsoft per descrivere la natura di una vulnerabilità della protezione.
  
**Tabella 4: Modello STRIDE delle categorie di pericolo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Termine</th>
<th style="border:1px solid black;" >Definizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Spoofing (falsificazione) dell'identità</td>
<td style="border:1px solid black;">Ottenere illegalmente l'accesso e utilizzare le informazioni di autenticazione di un'altra persona, ad esempio il nome utente o la password.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Manomissione dei dati</td>
<td style="border:1px solid black;">La modifica non autorizzata dei dati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ripudio</td>
<td style="border:1px solid black;">Associato agli utenti che negano di aver eseguito un'azione, senza che ci sia però modo di dimostrare il contrario (il non ripudio si riferisce alla capacità di un sistema di contrastare i pericoli di ripudio e include tecniche quali la firma per un pacchetto ricevuto in maniera che la ricevuta firmata possa essere utilizzata come prova).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Divulgazione di informazioni</td>
<td style="border:1px solid black;">L'esposizione delle informazioni a persone che non dovrebbero avervi accesso, ad esempio l'accesso ai file senza possedere i diritti appropriati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Denial of Service</td>
<td style="border:1px solid black;">Un tentativo esplicito di impedire agli utenti legittimi di utilizzare un servizio o un sistema.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Incremento (Escalation) di privilegi</td>
<td style="border:1px solid black;">Quando un utente senza privilegi ottiene un accesso con privilegi. Ne è un esempio il caso di un utente senza privilegi che trova la maniera di venire aggiunto al gruppo Administrators.</td>
</tr>
</tbody>
</table>
  
**Nota:** per ulteriori informazioni sul modello STRIDE e sul modo in cui Microsoft forma gli sviluppatori per scrivere codice sicuro, vedere LeBlanc, [Writing Secure Code, Second Edition](http://www.microsoft.com/learning/en/us/books/5957.aspx), Redmond, WA: Microsoft Press, 2002. (<http://www.microsoft.com/learning/en/us/books/5957.aspx>, in inglese).
  
Ulteriori informazioni e articoli utili sono disponibili nel sito Web Alliance all'indirizzo:
  
[http://www.cl.cam.ac.uk/~rja14/tcpa-faq.html](http://www.cl.cam.ac.uk/%7erja14/tcpa-faq.html)
  
### Agenti di pericolo
  
I pericoli dannosi sono attacchi lanciati dall'interno o dall'esterno di una rete con l'intento di danneggiare o creare seri problemi a un'organizzazione. I pericoli non dannosi in genere provengono da dipendenti poco esperti che non sono consapevoli dei pericoli per la protezione e delle vulnerabilità. Nella Tabella 5 vengono descritti diversi agenti di pericoli dannosi.
  
**Tabella 5: Agenti di pericolo**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Termine</th>
<th style="border:1px solid black;" >Definizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Virus</td>
<td style="border:1px solid black;">Un programma intrusivo che infetta i file del computer inserendovi copie di codice autoreplicante e che cancella i file critici, modifica il sistema o effettua altre azioni che possono danneggiare i dati presenti nel computer o il computer stesso. Un virus si allega a un programma host.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Worm</td>
<td style="border:1px solid black;">Un programma autoreplicante, spesso dannoso come un virus, che può diffondersi da un computer all'altro senza prima infettare i file.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Cavallo di Troia</td>
<td style="border:1px solid black;">Software o messaggi di posta elettronica che si dichiarano utili e benigni, ma che di fatto hanno scopi distruttivi o forniscono l'accesso a un pirata informatico.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Mail bomb</td>
<td style="border:1px solid black;">Un messaggio di posta elettronica dannoso inviato a un destinatario ignaro. Quando il destinatario apre il messaggio di posta elettronica o esegue il programma, la mail bomb esegue un'azione dannosa sul suo computer.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Pirata informatico</td>
<td style="border:1px solid black;">La persona o l'organizzazione che compie un attacco.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Adware</td>
<td style="border:1px solid black;">Qualsiasi applicazione o programma software nel quale vengono visualizzati banner pubblicitari o finestre popup durante l'esecuzione. L'adware è considerato &quot;spyware&quot; e viene installato all'insaputa dell'utente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Spyware</td>
<td style="border:1px solid black;">Qualsiasi software che raccoglie di nascosto informazioni sugli utenti tramite la connessione di questi ultimi e a loro insaputa, generalmente per scopi pubblicitari. Le applicazioni spyware sono generalmente allegate come componente nascosto di programmi freeware o shareware scaricabili da Internet. Tuttavia, è necessario sottolineare che la maggior parte di applicazioni shareware e freeware non vengono fornite con spyware. Una volta installato, lo spyware monitora l'attività dell'utente su Internet e trasmette le informazioni in background ad altri. Lo spyware può anche raccogliere informazioni su indirizzi di posta elettronica e persino password e numeri di carte di credito. Lo spyware è simile a un trojan horse poiché viene installato involontariamente dagli utenti insieme ad altri programmi. Un modo diffuso di essere colpiti dallo spyware consiste nello scaricare alcuni prodotti per lo scambio di file peer-to-peer oggi disponibili.</td>
</tr>
</tbody>
</table>
  
**Nota:** mentre i pericoli automatizzati quali i virus sono scritti per sfruttare specifiche vulnerabilità, un pirata informatico che prende di mira un'organizzazione non ha queste limitazioni. Cercherà di compromettere un ambiente con qualsiasi mezzo disponibile.
  
Gli attacchi diretti possono essere sferrati localmente o in modalità remota e possono includere un'accurata ricerca dei molti possibili punti vulnerabili, compresi quelli software, password non sicure, configurazioni di protezione non adeguate e vulnerabilità dei criteri di protezione o di formazione.
  
[](#top)[Inizio pagina](#top)
  
In che modo Microsoft provvede a correggere il software dopo il rilascio  
------------------------------------------------------------------------
  
L'impegno di Microsoft è volto a proteggere i clienti dalle vulnerabilità della protezione. Nel quadro di questo impegno, Microsoft mette a disposizione aggiornamenti software periodici. Per ulteriori informazioni in merito, vedere il white paper "Trustworthy Computing", all'indirizzo <http://www.microsoft.com/italy/about/twc/twc_whitepaper.mspx> (in inglese).
  
Ogni gruppo di produzione Microsoft include un team di progettazione di supporto che sviluppa gli aggiornamenti software per i problemi riscontrati dopo il rilascio del prodotto.
  
Quando Microsoft viene a conoscenza di una vulnerabilità della protezione, MSRC e i gruppi di produzione appropriati valutano e verificano il problema. Successivamente, il team di progettazione di supporto del gruppo di produzione crea e testa un aggiornamento per la protezione per porre rimedio al problema, mentre MSRC lavora con chi l'ha segnalato per coordinare il rilascio di informazioni pubbliche sotto forma di un bollettino sulla sicurezza contenente i dettagli sull'aggiornamento per la protezione.
  
Microsoft distribuisce infine l'aggiornamento software tramite il Microsoft Download Center e altri servizi, tra cui:
  
Aggiornamenti automatici:
  
-   Microsoft Windows Update
  
-   Microsoft Office Update
  
-   Microsoft Update
  
Aggiornamenti iniziati (definiti) dall'utente
  
-   Microsoft Systems Management Server (SMS) 2003
  
-   Microsoft Windows Server Update Service (WSUS)
  
Poco prima del rilascio dell'aggiornamento software, MSRC pubblica un bollettino sulla sicurezza pertinente.
  
**Nota**: gli aggiornamenti per la protezione vengono sviluppati per diverse versioni del sistema operativo e delle applicazioni. Per conoscere i livelli di supporto disponibili per le varie versioni software, è possibile esaminare le politiche sul ciclo di vita dei prodotti Microsoft all'indirizzo:
  
[http://support.microsoft.com/default.aspx?scid=fh;\[LN\];lifecycle.](http://support.microsoft.com/default.aspx?scid=fh;%5bln%5d;lifecycle)
  
In genere, gli aggiornamenti per la protezione vengono resi disponibili per i prodotti supportati non solo sul service pack corrente ma anche su quello precedente. Tuttavia, dato che questo non sempre avviene, per essere certi è consigliabile controllare le politiche sul ciclo di vita dei propri prodotti.
  
Microsoft consiglia ai clienti di utilizzare la soluzione di gestione degli aggiornamenti più adatta alle proprie esigenze. In generale, WSUS risolve scenari semplici di gestione degli aggiornamenti, mentre Systems Management Server (SMS) 2003 supporta esigenze di gestione degli aggiornamenti più avanzate. Nella Tabella 6 sono riportate le scelte degli utenti più diffuse in base ai diversi segmenti per dimensione dell'organizzazione:
  
**Tabella 6: Segmenti per dimensione dell'organizzazione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Tipo cliente</th>
<th style="border:1px solid black;" >Scenario</th>
<th style="border:1px solid black;" >Scelta cliente</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Media o grande impresa</td>
<td style="border:1px solid black;">L'organizzazione richiede una soluzione di aggiornamento singola e flessibile con un livello esteso di controllo che consenta di aggiornare (e distribuire) tutti i sistemi operativi e le applicazioni Windows e di fornire una soluzione integrata di gestione delle risorse.</td>
<td style="border:1px solid black;">SMS 2003</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Media o grande impresa</td>
<td style="border:1px solid black;">L'organizzazione richiede una soluzione per la sola gestione degli aggiornamenti che fornisca una funzionalità di aggiornamento semplice per i software Microsoft in grado di supportare Windows 2000 e versioni successive, Office 2003, Office XP, Exchange Server 2000 e versioni successive, SQL Server 2000 e versioni successive.</td>
<td style="border:1px solid black;">WSUS1</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Piccole aziende</td>
<td style="border:1px solid black;">L'azienda dispone di almeno un server Windows e di un amministratore IT.</td>
<td style="border:1px solid black;">WSUS1</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Piccole aziende</td>
<td style="border:1px solid black;">Tutti gli altri scenari</td>
<td style="border:1px solid black;">Microsoft Update o Windows Update2</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Cliente</td>
<td style="border:1px solid black;">Tutti gli altri scenari</td>
<td style="border:1px solid black;">Microsoft Update o Windows Update2</td>
</tr>
</tbody>
</table>
  
1 I clienti possono utilizzare un altro strumento di aggiornamento oppure il processo di aggiornamento manuale per le versioni e le applicazioni del sistema operativo non supportate da WSUS o da Microsoft Update.
  
2 Microsoft Update è il nuovo servizio di aggiornamenti ospitati su Web che fornisce aggiornamenti per il software Microsoft aggiuntivo. Microsoft Update sarà disponibile insieme al prossimo rilascio di WSUS. Windows Update resterà disponibile.
  
### Terminologia relativa agli aggiornamenti software
  
Nella Tabella 7 sono elencati i termini standard Microsoft correnti per gli aggiornamenti software, in vigore dal 30 giugno 2003. Tenere presente che il termine patch non è più utilizzato da Microsoft per descrivere un aggiornamento software, fatta eccezione per la definizione patch di protezione o quando si descrive il processo di gestione degli aggiornamenti (una terminologia ampiamente recepita nel settore del software).
  
**Tabella 7: Terminologia Microsoft per gli aggiornamenti software**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Termine</th>
<th style="border:1px solid black;" >Definizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Patch di protezione</td>
<td style="border:1px solid black;">Una correzione a rilascio pubblico per uno specifico prodotto, mirata a eliminare le vulnerabilità della protezione. Spesso a una patch di protezione è associato un livello di gravità che fa riferimento alla valutazione della gravità, effettuata da MSRC, della vulnerabilità che si prefigge di eliminare.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Aggiornamento critico</td>
<td style="border:1px solid black;">Una correzione a rilascio pubblico per uno specifico problema, mirata a eliminare un bug critico, non legato alla protezione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Aggiornamento</td>
<td style="border:1px solid black;">Una correzione a rilascio pubblico per uno specifico problema, mirata a eliminare un bug non critico, non legato alla protezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Aggiornamento rapido (hotfix)</td>
<td style="border:1px solid black;">Un singolo pacchetto composto da uno o più file utilizzati per risolvere un problema in un prodotto. Gli aggiornamenti rapidi riguardano una situazione specifica di un utente, sono disponibili solo tramite il supporto Microsoft e non possono essere distribuiti al di fuori dell'organizzazione del cliente senza il consenso legale scritto di Microsoft. I termini QFE (Quick Fix Engineering), patch e aggiornamento sono stati utilizzati in passato come sinonimi di aggiornamento rapido.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Rollup di aggiornamento</td>
<td style="border:1px solid black;">Una raccolta di patch di protezione, aggiornamenti critici, aggiornamenti e aggiornamenti rapidi, rilasciati come offerta cumulativa o mirata a un singolo componente quale Microsoft Internet Information Services (IIS) o Microsoft Internet Explorer. Permette di semplificare la distribuzione di aggiornamenti software multipli.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Service pack</td>
<td style="border:1px solid black;">Un insieme cumulativo di aggiornamenti rapidi, patch di protezione, aggiornamenti critici e aggiornamenti dal rilascio del prodotto, compresi molti dei problemi risolti che non sono stati resi disponibili tramite nessun altro aggiornamento software. I service pack possono contenere anche un numero limitato di modifiche o funzionalità richieste dal cliente. I service pack vengono pubblicamente distribuiti e testati da Microsoft, più di qualsiasi altro aggiornamento software.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Service pack integrato</td>
<td style="border:1px solid black;">La combinazione di un prodotto con un service pack in un unico pacchetto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Feature pack</td>
<td style="border:1px solid black;">Il rilascio di una nuova caratteristica che aggiunge funzionalità a un prodotto. Solitamente inclusa nel prodotto al rilascio successivo.</td>
</tr>
</tbody>
</table>
  
**Nota:** dato che queste definizioni sono nuove, numerosi strumenti e risorse esistenti non utilizzano i termini così come sono definiti nella tabella sopra riportata.
  
[](#top)[Inizio pagina](#top)
  
L'importanza di una gestione degli aggiornamenti proattiva  
----------------------------------------------------------
  
Il software Microsoft è stato oggetto di numerosi attacchi e vulnerabilità ampiamente pubblicizzati. Molte organizzazioni che hanno adottato una gestione proattiva degli aggiornamenti non sono state colpite da questi attacchi perché hanno agito sulla base delle informazioni rese disponibili da Microsoft prima dell'attacco.
  
Nella Tabella 8, vengono riportati diversi attacchi storici, accompagnati dalla relativa data. In ogni caso, era stato precedentemente rilasciato un bollettino MSRC in cui venivano identificati i punti vulnerabili e veniva descritto come evitare che in futuro fossero sfruttati (tramite aggiornamenti software e altre contromisure). Nell'ultima colonna della tabella, Giorni disponibili prima dell'attacco, sono riportati i giorni di cui l'organizzazione disponeva per implementare le raccomandazioni MSRC ed evitare attacchi futuri.
  
**Tabella 8: Esempi di attacchi storici e relativi bollettini MSRC**
  
<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome dell'attacco</th>
<th style="border:1px solid black;" >Data in cui è stato pubblicamente scoperto</th>
<th style="border:1px solid black;" >Gravità MSRC</th>
<th style="border:1px solid black;" >Bollettino MSRC</th>
<th style="border:1px solid black;" >Data del bollettino MSRC</th>
<th style="border:1px solid black;" >Giorni disponibili prima dell'attacco</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Zotob</td>
<td style="border:1px solid black;">14 agosto 2005</td>
<td style="border:1px solid black;">Critico</td>
<td style="border:1px solid black;">MS05-039</td>
<td style="border:1px solid black;">9 agosto 2005</td>
<td style="border:1px solid black;">5</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Trojan.Kaht</td>
<td style="border:1px solid black;">5 maggio 2003</td>
<td style="border:1px solid black;">Critico</td>
<td style="border:1px solid black;">MS03-007</td>
<td style="border:1px solid black;">17 marzo 2003</td>
<td style="border:1px solid black;">49</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SQL Slammer</td>
<td style="border:1px solid black;">24 gennaio 2003</td>
<td style="border:1px solid black;">Critico</td>
<td style="border:1px solid black;">MS02-039</td>
<td style="border:1px solid black;">24 luglio 2002</td>
<td style="border:1px solid black;">184</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Sasser</td>
<td style="border:1px solid black;">1 maggio 2004</td>
<td style="border:1px solid black;">*</td>
<td style="border:1px solid black;">MS04-011</td>
<td style="border:1px solid black;">15 maggio 2004</td>
<td style="border:1px solid black;">14</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Blaster</td>
<td style="border:1px solid black;">12 agosto 2003</td>
<td style="border:1px solid black;">*</td>
<td style="border:1px solid black;">MS03-026</td>
<td style="border:1px solid black;">27 agosto 2003</td>
<td style="border:1px solid black;">25</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Klez-E</td>
<td style="border:1px solid black;">17 gennaio 2002</td>
<td style="border:1px solid black;">*</td>
<td style="border:1px solid black;">MS01-020</td>
<td style="border:1px solid black;">29 marzo 2001</td>
<td style="border:1px solid black;">294</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nimda</td>
<td style="border:1px solid black;">18 settembre 2001</td>
<td style="border:1px solid black;">*</td>
<td style="border:1px solid black;">MS00-078</td>
<td style="border:1px solid black;">17 ottobre 2000</td>
<td style="border:1px solid black;">336</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Code Red</td>
<td style="border:1px solid black;">16 luglio 2001</td>
<td style="border:1px solid black;">*</td>
<td style="border:1px solid black;">MS01-033</td>
<td style="border:1px solid black;">18 giugno 2001</td>
<td style="border:1px solid black;">28</td>
</tr>
</tbody>
</table>
  
\*Bollettini rilasciati prima della divulgazione dei livelli di gravità stabiliti da MSRC.
  
Questi moduli sono progettati per contribuire a evitare attacchi futuri come questi, con un'attenzione particolare alla colonna Giorni disponibili prima dell'attacco nella tabella.
  
**Nota:** la gestione proattiva degli aggiornamenti rappresenta un modo efficace di limitare gli attacchi mirati alle vulnerabilità software conosciute. Nella tabella precedente non sono riportati gli attacchi diretti e intenzionali sferrati da persone all'interno o al di fuori dell'organizzazione presa di mira, che hanno cercato e tentato di sfruttare le vulnerabilità della protezione con intenti criminali.
  
Per una migliore comprensione delle relazioni tra i bollettini MSRC e le opportunità che essi danno alle organizzazioni che desiderano un ambiente sicuro, nelle prossime sezioni vengono descritti brevemente due attacchi storici:
  
-   Code Red
  
-   Worm SQL Slammer
  
### Come evitare gli attacchi, Esempio 1: Code Red
  
Code Red è un worm che si è diffuso molto rapidamente e poteva avere un grande impatto. Il 16 luglio 2001, il worm Code Red originale si è diffuso a 250.000 computer in sole nove ore. Tra i vari effetti vi sono stati il rallentamento della velocità di Internet, interruzioni di pagine Web e danneggiamenti, nonché gravi problemi alle applicazioni aziendali e personali quali la posta elettronica e l'e-commerce.
  
Code Red sfruttava una vulnerabilità di sovraccarico del buffer all'interno di IIS per eseguire un codice nei server Web. IIS è installato per impostazione predefinita con Microsoft Windows Server 2000 ed è utilizzato da molte applicazioni.
  
Alcune organizzazioni hanno evitato Code Red seguendo le indicazioni riportate in MS01-033, un bollettino sulla sicurezza MSRC rilasciato il 18 giugno 2001, 28 giorni prima della diffusione di Code Red.
  
Per ulteriori informazioni su questo bollettino sulla sicurezza, inclusi gli aspetti tecnici e le contromisure, vedere:
  
[http://www.microsoft.com/technet/security/bulletin/ms01-033.mspx.](http://www.microsoft.com/technet/security/bulletin/ms01-033.mspx)
  
### Come evitare gli attacchi, Esempio 2: SQL Slammer
  
SQL Slammer (o Sapphire) è un worm che colpisce i sistemi Microsoft SQL Server™ 2000 e Microsoft Data Engine (MSDE) 2000 e provoca un elevato volume di traffico di rete sia in Internet sia sulle reti private interne, che si comporta (alcuni potrebbero dire non intenzionalmente) come un vero attacco di negazione del servizio.
  
Alle 21:30 circa, ora del Pacifico, di venerdì 24 gennaio 2003, SQL Slammer ha provocato un fortissimo aumento del traffico di rete in tutto il mondo. Da un'analisi del worm SQL Slammer emerge che:
  
-   Ha impiegato circa 10 minuti per diffondersi in tutto il mondo, il che ne ha fatto il worm più rapido finora conosciuto.
  
-   Nelle prime fasi, il numero di host compromessi raddoppiava ogni 8 secondi e mezzo.
  
-   Al culmine, raggiunto dopo circa tre minuti dal suo rilascio, analizzava la rete a oltre 55 milioni di indirizzi IP (Internet Protocol) al secondo.
  
-   Ha infettato almeno 75.000 server, ma probabilmente il numero è molto superiore.
  
SQL Slammer sfruttava una vulnerabilità di sovraccarico del buffer, identificata per prima da Microsoft nel bollettino sulla sicurezza MS02-039 (luglio 2002), 184 giorni prima dell'attacco e nuovamente nel bollettino sulla sicurezza MS02-061. Ad ogni bollettino venivano offerte una patch di protezione e le contromisure appropriate.
  
Per ulteriori informazioni su questo bollettino sulla sicurezza, inclusi gli aspetti tecnici e le contromisure, vedere:
  
[http://www.microsoft.com/technet/security/bulletin/ms02-039.mspx.](http://www.microsoft.com/technet/security/bulletin/ms02-039.mspx)
  
**Insegnamenti tratti da SQL Slammer**
  
Una delle sfide con cui si sono confrontate le organizzazioni per evitare il worm SQL Slammer è stata la natura ubiquitaria di MSDE e di SQL Server, determinata dal fatto che sono installati e utilizzati da molti altri prodotti.
  
L'attacco di SQL Slammer ha permesso di apprendere tre importanti lezioni sulla natura delle vulnerabilità della protezione:
  
-   Una conoscenza accurata di tutti i computer, i prodotti e le tecnologie presenti nell'ambiente è un importante prerequisito per poter gestire correttamente gli aggiornamenti.
  
-   Per essere efficace, un attacco non richiede che le risorse ad alto valore siano vulnerabili. Il worm SQL Slammer è riuscito a interrompere operazioni mission-critical tramite computer vulnerabili e di poco valore nella stessa rete.
  
-   Una singola distribuzione di una patch di protezione può non essere sufficiente per eliminare una vulnerabilità. Altrettanto importante è l'analisi regolare mirata a identificare la ricorrenza delle vulnerabilità, associata alla relativa gestione per risolvere i problemi.
  
[](#top)[Inizio pagina](#top)
  
Requisiti per una corretta gestione degli aggiornamenti  
-------------------------------------------------------
  
Dato che la gestione degli aggiornamenti mira a conferire a un'organizzazione il controllo sugli aggiornamenti software che distribuisce, qualsiasi organizzazione che pianifichi di aggiornare il proprio ambiente operativo deve accertarsi che questo sia contraddistinto da:
  
-   Operazioni eseguite in maniera efficiente, incluse persone consapevoli del proprio ruolo e delle proprie responsabilità.
  
-   Tecnologie e strumenti adeguati per un'efficiente gestione degli aggiornamenti.
  
-   Processi efficienti di gestione dei progetti.
  
[](#top)[Inizio pagina](#top)
  
Operazioni efficienti  
---------------------
  
MOF, il modello di processo MOF, le funzioni di gestione dei servizi (SMF, Service Management Function) MOF e il modello di team MOF forniscono indicazioni per lo svolgimento di attività IT efficienti. Tre delle funzioni SMF - Gestione dei cambiamenti, Gestione della configurazione e Gestione del rilascio - rivestono un'importanza cruciale per la gestione degli aggiornamenti.
  
[](#top)[Inizio pagina](#top)
  
Strumenti e tecnologie  
----------------------
  
In questa sezione verranno presi in esame gli strumenti automatici che le organizzazioni di qualsiasi dimensione possono utilizzare per gestire e controllare l'installazione degli aggiornamenti software. Esistono tre tecnologie Microsoft principali per la gestione degli aggiornamenti aziendali di sistemi basati su Windows.
  
-   Windows Server Update Services
  
-   Systems Management Server 2003
  
### Windows Server Update Services (WSUS)
  
WSUS è uno strumento gratuito che permette di installare un servizio per scaricare tutti gli aggiornamenti critici, gli aggiornamenti della protezione e i service pack non appena vengono pubblicati nel sito Web Microsoft Update all'indirizzo <http://update.microsoft.com>.
  
Dopo aver approvato questi aggiornamenti, WSUS li renderà automaticamente disponibili a tutti i server preconfigurati con Microsoft Windows Server™ 2003 e Windows 2000 e ai desktop con Windows XP Professional e Windows Vista.
  
La priorità degli aggiornamenti della protezione è stabilita da Microsoft Security Response Center (MSRC). Per una presentazione di MSRC e delle regole utilizzate nel processo decisionale, vedere <http://www.microsoft.com/security/msrc/default.mspx>.
  
WSUS fornisce quanto segue:
  
-   Ulteriori aggiornamenti per i prodotti Microsoft in più categorie
  
-   Possibilità di scaricare automaticamente gli aggiornamenti da Microsoft Update per prodotto e tipo.
  
-   Supporto per più lingue per i clienti di tutto il mondo.
  
-   Efficienza ottimizzata della larghezza di banda mediante il Servizio trasferimento intelligente in background (BITS) 2.0 (BITS 2.0 non viene installato da Update Services ed è disponibile in Microsoft Update).
  
-   Possibilità di specificare gli aggiornamenti per computer specifici e gruppi di computer.
  
-   Possibilità di verificare che gli aggiornamenti siano adatti a ciascun computer prima dell'installazione. Questa funzionalità viene eseguita automaticamente per gli aggiornamenti di livello critico e per quelli per la protezione.
  
-   Opzioni di distribuzione flessibili.
  
-   Funzionalità di report.
  
-   Opzioni di database flessibili.
  
-   Funzionalità di migrazione e di importazione/esportazione dei dati.
  
-   Espansione tramite API (Application Programming Interface).
  
Le funzionalità WSUS possono essere suddivise in due componenti: lato server e lato client. La seguente tabella illustra le funzionalità su ciascun lato di WSUS:

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Funzionalità lato server</th>
<th style="border:1px solid black;" >Funzionalità lato client</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Aggiornamenti per Windows, Office, Exchange Server e SQL Server con supporto aggiuntivo e prolungato per il prodotto</td>
<td style="border:1px solid black;">Gestione efficace ed estensibile del servizio Aggiornamenti automatici</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Impostazione del download automatico per aggiornamenti specifici</td>
<td style="border:1px solid black;">Aggiornamento automatico per i computer client</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Azioni automatizzate per gli aggiornamenti eseguite previa autorizzazione dell'amministratore</td>
<td style="border:1px solid black;">Rilevamento automatico degli aggiornamenti applicabili</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Possibilità di determinare l'applicabilità degli aggiornamenti prima di installarli</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Personalizzazione</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Sincronizzazione delle repliche</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Creazione di report</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Espansione</td>
<td style="border:1px solid black;"></td>
</tr>
</tbody>
</table>
  
WSUS consente agli amministratori IT di distribuire gli aggiornamenti più recenti per i prodotti Microsoft in Microsoft Windows Server™ 2003 e Windows 2000, nonché nei desktop con Windows XP Professional e Windows Vista. L'uso di WSUS consente un controllo completo della distribuzione degli aggiornamenti rilasciati tramite Microsoft Update nei computer della rete.
  
Il componente server WSUS viene installato in un computer dotato di sistema operativo Windows 2000 Server con Service Pack 4 (SP4) o Windows Server 2003 all'interno del firewall aziendale. Il server WSUS fornisce le funzionalità necessarie agli amministratori per gestire e distribuire gli aggiornamenti tramite uno strumento basato su Web per WSUS 2.0 al quale è possibile accedere da Internet Explorer in qualsiasi computer Windows della rete aziendale o tramite MMC per WSUS 3.0 al quale è possibile accedere dallo snap-in MMC in qualsiasi computer Windows della rete aziendale. WSUS 3.0 richiede MMC 3.0. Inoltre, un server Windows Server Update Services può rappresentare l'origine degli aggiornamenti per altri server Windows Server Update Services.
  
Il componente del computer client WSUS viene eseguito nei sistemi operativi Windows Vista, Windows XP, Windows 2000 con SP3 e Windows Server 2003. Aggiornamenti automatici permette ai computer client e server di ricevere gli aggiornamenti da Microsoft Update o da un server con WSUS.
  
WSUS non fornisce funzionalità di analisi e di controllo, pertanto una soluzione di gestione degli aggiornamenti basata su WSUS richiede anche l'utilizzo dello strumento Microsoft Baseline Security Analyzer 2.0.
  
**Nota**: in questa pagina viene fornito un riepilogo della panoramica sul prodotto WSUS. Per leggere l'intera panoramica sul prodotto per WSUS 2.0, fare clic [qui](http://www.microsoft.com/downloads/details.aspx?familyid=2478d594-a29c-483c-9dc1-9740bf3081a5&displaylang=en), mentre per WSUS 3.0 fare clic [qui](http://www.microsoft.com/downloads/details.aspx?familyid=1b5eac37-bd48-41fd-869b-f9b06fa64a61&displaylang=en).
  
#### Per approfondimenti
  
-   Foglio dati
  
    -   [WSUS 2.0](http://technet.microsoft.com/en-us/library/cc708472.aspx)
  
    -   [WSUS 3.0](http://technet.microsoft.com/en-us/library/cc708528.aspx)
  
-   Guide dettagliate
  
    -   [WSUS 2.0](http://technet.microsoft.com/en-us/library/cc708573.aspx)
  
    -   [WSUS 3.0](http://technet.microsoft.com/en-us/library/cc708508.aspx)
  
-   Guida alla distribuzione
  
    -   [WSUS 2.0](http://technet.microsoft.com/en-us/library/cc708572.aspx)
  
    -   [WSUS 3.0](http://technet.microsoft.com/en-us/library/cc708556.aspx)
  
-   Guida operativa
  
    -   [WSUS 2.0](http://technet.microsoft.com/en-us/library/cc708572.aspx)
  
    -   [WSUS 3.0](http://technet.microsoft.com/en-us/library/cc708540.aspx)
  
Un riepilogo delle informazioni sull'utilizzo di WSUS e MBSA a sostegno della gestione degli aggiornamenti è contenuto nei seguenti moduli:
  
-   [Fase 1 del processo di gestione degli aggiornamenti - Valutazione"](http://technet.microsoft.com/it-it/library/cc700830.aspx)
  
-   ["Fase 2 del processo di gestione degli aggiornamenti - Identificazione"](http://technet.microsoft.com/it-it/library/cc700831.aspx)
  
-   ["Fase 3 del processo di gestione degli aggiornamenti - Stima e pianificazione"](http://technet.microsoft.com/it-it/library/cc700840.aspx)
  
-   ["Fase 4 del processo di gestione degli aggiornamenti - Distribuzione"](http://technet.microsoft.com/it-it/library/cc700833.aspx)
  
Per informazioni dettagliate sull'utilizzo di WSUS e MBSA per supportare la gestione degli aggiornamenti, vedere [Windows Server Update Services (WSUS) Technical Library](http://technet.microsoft.com/en-us/library/cc706995.aspx) (in inglese).
  
### Microsoft Baseline Security Analyzer (MBSA) 2.0.1
  
Microsoft Baseline Security Analyzer (MBSA) 2.0.1 è uno strumento facile da usare che consente alle piccole e medie imprese di valutare il proprio livello di protezione sulla base dei consigli per la protezione Microsoft. In questo articolo viene discussa la disponibilità di MBSA 2.0.1.
  
MBSA 2.0.1 rileva i prodotti attualmente supportati da Microsoft Update, il catalogo centrale di aggiornamenti per i prodotti Microsoft. Microsoft Update sostituisce Windows Update. Windows Update aggiorna solo i prodotti del sistema operativo Microsoft Windows. Microsoft Update ospita la logica di rilevamento per MBSA 2.0.1 e altri strumenti.
  
MBSA 2.0.1 verifica se mancano degli aggiornamenti per la protezione e compila un report sul rispetto, in un computer, delle normali procedure consigliate per la protezione, ad esempio le password complesse. Inoltre, identifica eventuali opzioni di configurazione che lasciano il computer esposto a potenziali vulnerabilità della protezione. MBSA può anche essere configurato per creare un report sugli aggiornamenti già approvati in un server WSUS, ma non ancora installati.
  
MBSA 2.0.1 esegue un'analisi per identificare le vulnerabilità amministrative in Microsoft Windows Vista, Windows 2000, Windows XP, Windows Server 2003, Microsoft Internet Information Services (IIS) 5.0, 5.1 e 6.0, Microsoft Internet Explorer 5.01, 5.5 e 6.0 (incluso Internet Explorer 6.0 per Windows XP SP2 e Internet Explorer 6.0 per Windows Server 2003), Microsoft SQL Server 7.0 e SQL Server 2000, Microsoft Office 2000, Office XP e Office 2003. MBSA 2.0.1 supporta solo le analisi remote per Windows Vista. La futura versione MBSA 2.1 supporterà anche le analisi locali dei sistemi Windows Vista.
  
MBSA 2.0.1 include diversi miglioramenti e nuove funzionalità rispetto alla versione precedente 1.2.1. Si consiglia ai clienti di utilizzare MBSA 2.0. Per scaricare MBSA, visitare la home page di MBSA nel seguente sito Web Microsoft:  
<http://technet.microsoft.com/security/cc184924.aspx>
  
MBSA 2.0.1 include le importanti funzionalità riportate di seguito:
  
-   Livelli di gravità
  
-   Analisi locali e remote per aggiornamenti per la protezione di Microsoft Office XP e successivi
  
-   Istruzioni aggiuntive per l'invidivuazione degli aggiornamenti e per l'adozione di azioni adeguate
  
-   Identificativi CVE per gli aggiornamenti supportati
  
-   Contenuto migliorato della guida
  
-   Compatibilità con Windows Server Update Services
  
-   Registrazione automatica a Microsoft Update e aggiornamento degli agenti
  
-   Rilevamento degli aggiornamenti in Windows XP Embedded e nelle versioni a 64 bit di Microsoft Windows
  
Anche se MBSA offre la possibilità di identificare in un livello di dominio/subnet ciò che è richiesto per proteggere un particolare computer, non indica nessun metodo per distribuire gli aggiornamenti a quei computer o per configurarli. Per questo motivo, è opportuno utilizzare MBSA assieme a WSUS per fornire una soluzione di gestione degli aggiornamenti. MBSA fornisce tuttavia informazioni su come porre rimedio alle vulnerabilità riscontrate, compresi i collegamenti agli articoli della Knowledge Base e ai white paper.
  
MBSA 2.0.1 fornisce un'interfaccia grafica per visualizzare i report generati per ogni computer e può anche essere gestito tramite script dalla riga di comando. MBSA copia un file XML archiviato in Microsoft Download Center per accertarsi che utilizzi un elenco corrente dei dettagli di valutazione per i nuovi aggiornamenti software legati alla protezione.
  
Ulteriori informazioni su MBSA sono reperibili all'indirizzo [http://www.microsoft.com/msba](http://www.microsoft.com/mbsa) (in inglese).
  
### Systems Management Server 2003
  
Microsoft Systems Management Server (SMS) 2003 è il meccanismo preferenziale per la distribuzione e la gestione degli aggiornamenti software in un gran numero di client. Fornisce le seguenti funzionalità, essenziali per una corretta distribuzione:
  
-   Funzioni di inventario per stabilire quanti computer sono stati distribuiti e per identificarne posizioni e ruoli.
  
-   Funzioni di inventario per identificare quali applicazioni e aggiornamenti software sono stati installati e quali devono essere installati nei computer distribuiti.
  
-   Funzioni di pianificazione che permettono a un'organizzazione di distribuire gli aggiornamenti software al di fuori delle normali ore di ufficio o in ore che comportano un impatto minimo sulle operazioni dell'azienda.
  
-   Report sullo stato che permette agli amministratori di monitorare l'andamento dell'installazione.
  
I programmi di analisi dell'inventario di SMS 2003 sono vitali per la gestione efficiente degli aggiornamenti software. Vengono utilizzati per creare un inventario degli aggiornamenti applicabili e installati per ogni computer client, utilizzando un'origine automatizzata di logica di rilevamento. I dati risultanti sono inclusi nell'inventario di Systems Management Server, mentre le funzionalità di reporting basate su Web forniscono una visione completa dello stato. In genere, i dati dell'inventario sono limitati alle voci rilasciate da Microsoft sotto forma di bollettini sulla sicurezza.
  
SMS 2003 include i seguenti strumenti (disponibili anche in SMS 2.0 Software Update Services Feature Pack):
  
-   Security Update Inventory Tool
  
-   Microsoft Office Inventory Tool for Updates
  
-   Distribute Software Updates Wizard
  
-   Inventory Tool for Microsoft Updates
  
**Nota:** la versione di valutazione del successivo rilascio di SMS, chiamata System Center Configuration Manager 2007, è ora disponibile per il download all'indirizzo <http://technet.microsoft.com/configmgr/cc761485.aspx> (in inglese). Grazie ai notevoli investimenti in semplificazione, configurazione, distribuzione e protezione, Configuration Manager 2007 rende radicalmente più facile la distribuzione dei sistemi, l'automazione delle attività, la gestione della conformità e la gestione della protezione basata su criteri, aumentando l'agilità dell'azienda.
  
#### Security Update Inventory Tool
  
Security Update Inventory Tool si basa sulle funzionalità di inventario di SMS e sfrutta la potenza di MBSA per analizzare ogni client al fine di individuare gli aggiornamenti della protezione. I dati risultanti sono inclusi nell'inventario di SMS e lo stato completo viene fornito tramite i report basati su Web. Questo strumento non è installato nei siti SMS per impostazione predefinita, ma fa parte degli SMS 2003 Software Update Scanning Tools e può essere scaricato da [http://www.microsoft.com/downloads/details.aspx?FamilyId=2C93DA1D-48A0-4E5C-991F-87E08954F61B&displaylang=en](http://www.microsoft.com/downloads/details.aspx?familyid=2c93da1d-48a0-4e5c-991f-87e08954f61b&displaylang=en) (in inglese).
  
#### Microsoft Office Inventory Tool for Updates
  
Microsoft Office Inventory Tool for Updates utilizza il Microsoft Office Inventory Tool esistente per effettuare analisi automatizzate e continue dei client SMS per individuare gli aggiornamenti Office installati o applicabili. Questo è uno degli strumenti per l'analisi di SMS 2003 SP1. Questi dati sono convertiti e inclusi nell'inventario di SMS e possono essere visualizzati anche tramite report basati su Web. Questo strumento non è installato nei siti SMS per impostazione predefinita, ma fa parte degli SMS 2003 Software Update Scanning Tools e può essere scaricato da [http://www.microsoft.com/downloads/details.aspx?FamilyId=2C93DA1D-48A0-4E5C-991F-87E08954F61B&displaylang=en](http://www.microsoft.com/downloads/details.aspx?familyid=2c93da1d-48a0-4e5c-991f-87e08954f61b&displaylang=en) (in inglese).
  
#### Distribute Software Updates Wizard
  
Distribute Software Updates Wizard confronta gli aggiornamenti disponibili con l'inventario dei computer client per stabilire gli aggiornamenti mancanti e quelli installati in precedenza. Sono installati solo gli aggiornamenti necessari, mentre quelli ridondanti o non necessari vengono ignorati o differiti, riducendo pertanto il carico del sistema.
  
Distribute Software Updates Wizard fornisce le seguenti funzionalità:
  
-   Aggiunta all'inventario dello stato degli aggiornamenti software di tutti i client, sulla base delle nuove informazioni sugli aggiornamenti della protezione.
  
-   Esame e autorizzazione degli aggiornamenti identificati come mancanti.
  
-   Personalizzazione dei pacchetti e degli annunci in base a ogni aggiornamento o serie di aggiornamenti.
  
-   Distribuzione degli annunci di aggiornamento ai computer che utilizzano le funzionalità di distribuzione del software SMS.
  
-   Notifiche in stile Windows Update e un'esperienza eccellente dell'utente finale.
  
-   Utilizzo di timer per permettere agli utenti di salvare e chiudere le applicazioni e, opzionalmente, di posporre gli aggiornamenti o di scegliere di non riavviare il sistema.
  
Ulteriori informazioni su SMS 2003 sono reperibili all'indirizzo <http://www.microsoft.com/smserver> (in inglese).
  
Un riepilogo delle informazioni sull'utilizzo di SMS e MBSA a sostegno della gestione degli aggiornamenti è contenuto nei seguenti moduli:
  
-   [Fase 1 del processo di gestione degli aggiornamenti - Valutazione"](http://technet.microsoft.com/it-it/library/cc700830.aspx)
  
-   ["Fase 2 del processo di gestione degli aggiornamenti - Identificazione"](http://technet.microsoft.com/it-it/library/cc700831.aspx)
  
-   ["Fase 3 del processo di gestione degli aggiornamenti - Stima e pianificazione"](http://technet.microsoft.com/it-it/library/cc700840.aspx)
  
-   ["Fase 4 del processo di gestione degli aggiornamenti - Distribuzione"](http://technet.microsoft.com/it-it/library/cc700833.aspx)
  
Per informazioni dettagliate sull'utilizzo di SMS 2003 per il supporto della gestione degli aggiornamenti, vedere [Technical Library for Systems Management Server 2003](http://technet.microsoft.com/en-us/library/cc181833.aspx) (in inglese).
  
### Strumenti e tecnologie a confronto
  
Nella Tabella 10 vengono confrontate le funzionalità fornite da SMS 2003 e WSUS.
  
**Tabella 10: Funzionalità di gestione degli aggiornamenti**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Funzionalità</th>
<th style="border:1px solid black;" >WSUS</th>
<th style="border:1px solid black;" >SMS 2003</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Piattaforme supportate per il contenuto</td>
<td style="border:1px solid black;">Windows 2000, Windows Server 2003, Windows XP</td>
<td style="border:1px solid black;">Windows NT 4.0, Windows 2000, Windows Server 2003, Windows XP, Windows 98</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Tipi di contenuto supportati</td>
<td style="border:1px solid black;">Windows 2000+, Exchange 2000+, SQL Server 2000+, Office XP+ con supporto avanzato</td>
<td style="border:1px solid black;">Tutte le patch di protezione, i service pack e gli aggiornamenti per le piattaforme summenzionate. Supporta anche installazioni di patch di protezione, aggiornamenti e applicazioni per Microsoft e altre applicazioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Personalizzazione del contenuto in base ai sistemi</td>
<td style="border:1px solid black;">Sì, per contenuti Microsoft</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Ottimizzazione della larghezza di banda della rete</td>
<td style="border:1px solid black;">Sì, per la distribuzione degli aggiornamenti</td>
<td style="border:1px solid black;">Sì, per la distribuzione degli aggiornamenti e la sincronizzazione dei server</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Controllo di distribuzione delle patch</td>
<td style="border:1px solid black;">Facile</td>
<td style="border:1px solid black;">Avanzato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Flessibilità di pianificazione e installazione delle patch</td>
<td style="border:1px solid black;">Controllata dall'amministratore (automatica) o dall'utente (manuale)</td>
<td style="border:1px solid black;">Controllata dall'amministratore con capacità di pianificazione dettagliate</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Report sullo stato di installazione delle patch</td>
<td style="border:1px solid black;">Sì, per contenuti Microsoft</td>
<td style="border:1px solid black;">Completo: stato di installazione, risultato e dettagli di conformità</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pianificazione della distribuzione</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Gestione dell'inventario</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Controllo della conformità</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
</tr>
</tbody>
</table>
  
[](#top)[Inizio pagina](#top)
  
Processi efficienti di gestione dei progetti  
--------------------------------------------
  
Per ottenere i migliori risultati, è necessario considerare l'utilizzo del processo di gestione degli aggiornamenti delineato in questo modulo come un progetto, utilizzando un processo efficiente di gestione dei progetti.
  
Molte organizzazioni hanno metodologie proprie che devono essere tutte compatibili con le linee guida fornite in questo modulo. Microsoft consiglia di utilizzare Microsoft Solutions Framework (MSF) per la gestione dei progetti. Per ulteriori informazioni su MSF, vedere [http://www.microsoft.com/downloads/details.aspx?familyid=A71AC896-1D28-45A4-880C-8B0CC8265C63&displaylang=en](http://www.microsoft.com/downloads/details.aspx?familyid=a71ac896-1d28-45a4-880c-8b0cc8265c63&displaylang=en) (in inglese).
  
[](#top)[Inizio pagina](#top)
  
L'approccio in quattro fasi alla gestione degli aggiornamenti  
-------------------------------------------------------------
  
Il processo di gestione degli aggiornamenti consigliato da Microsoft è articolato in quattro fasi e interessa la gestione degli aggiornamenti software, mirata a fornire all'organizzazione il controllo sulla distribuzione e la manutenzione dei rilasci software temporanei nell'ambiente di produzione.
  
Le quattro fasi sono:
  
### Valutazione
  
Il processo ha inizio con la valutazione di quanto è presente nell'ambiente di produzione, dei pericoli per la protezione, delle vulnerabilità a cui si potrebbe venire esposti e del livello di preparazione dell'organizzazione per rispondere ai nuovi aggiornamenti software.
  
Per informazioni più dettagliate sulla fase di valutazione, vedere il modulo "[Fase 1 del processo di gestione degli aggiornamenti - Valutazione](http://technet.microsoft.com/it-it/library/cc700830.aspx)".
  
### Identificazione
  
L'obiettivo durante la fase di identificazione consiste nello scoprire nuovi aggiornamenti software in modo affidabile, stabilire se sono pertinenti per l'ambiente di produzione e se un aggiornamento rappresenta un cambiamento normale o di emergenza.
  
Per informazioni più dettagliate sulla fase di identificazione, vedere il modulo "[Fase 2 del processo di gestione degli aggiornamenti - Identificazione](http://www.microsoft.com/italy/technet/security/guidance/patchmanagement/secmod195.mspx)".
  
### Stima e pianificazione
  
L'obiettivo, nella fase di stima e pianificazione, consiste nel prendere una decisione sulla distribuzione o meno dell'aggiornamento software, nello stabilire cosa serve per la sua distribuzione e nel testare l'aggiornamento software in un ambiente simile a quello di produzione per controllare che non comprometta le applicazioni e i sistemi critici per l'attività dell'azienda.
  
Per informazioni più dettagliate sulla fase di stima e pianificazione, vedere il modulo "[Fase 3 del processo di gestione degli aggiornamenti - Stima e pianificazione](http://technet.microsoft.com/it-it/library/cc700840.aspx)".
  
### Distribuzione
  
L'obiettivo durante la fase di distribuzione è quello di distribuire correttamente l'aggiornamento software approvato nell'ambiente di produzione in maniera che sia conforme a tutti i requisiti di qualsiasi Service Level Agreement (SLA) di distribuzione in atto.
  
Per informazioni più dettagliate sulla fase di distribuzione, vedere il modulo "[Fase 4 del processo di gestione degli aggiornamenti - Distribuzione](http://technet.microsoft.com/it-it/library/cc700833.aspx)".
  
Nella Figura 1 sono illustrati il processo e le sue quattro fasi.
  
[![](images/Dd536229.secmod193_1(it-it,TechNet.10).gif "Figura 1")](https://technet.microsoft.com/it-it/dd536229.secmod193_1(it-it,technet.10).gif)  
**Figura 1. Il processo di gestione degli aggiornamenti in quattro fasi consigliato da Microsoft**
  
Questo processo in quattro fasi si basa sulle funzioni di gestione dei servizi (SMF, Service Management Function) MOF Gestione dei cambiamenti, Gestione del rilascio e Gestione della configurazione, reperibili all'indirizzo [http://www.microsoft.com/technet/itsolutions/cits/mo/default.mspx](http://www.microsoft.com/technet/solutionaccelerators/msf/default.mspx) (in inglese).
  
[](#top)[Inizio pagina](#top)
  
Risorse correlate  
-----------------
  
Consultare le [altre soluzioni per la protezione](http://www.microsoft.com/technet/community/columns/sectip/st0805.mspx) sviluppate dal team Microsoft Solutions for Security and Compliance (MSSC).
  
[](#top)[Inizio pagina](#top)
  
Commenti e suggerimenti  
-----------------------
  
Il team Microsoft Solutions for Security and Compliance (MSSC) è interessato a eventuali commenti e suggerimenti su questa e altre soluzioni per la protezione.
  
Hai un commento? Saremo lieti di leggerlo nel [blog sulle soluzioni per la protezione](http://blogs.technet.com/secguide) per professionisti IT (in inglese).
  
Oppure invia consigli e suggerimenti tramite posta elettronica all'indirizzo: [SecWish@microsoft.com](mailto:secwish@microsoft.com). Rispondiamo spesso ai commenti e ai suggerimenti inviati a questa casella di posta.
  
Grazie per la collaborazione.
  
[](#top)[Inizio pagina](#top)
