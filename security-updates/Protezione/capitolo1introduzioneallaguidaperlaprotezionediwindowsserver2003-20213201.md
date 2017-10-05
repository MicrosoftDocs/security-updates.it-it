---
TOCTitle: 'Capitolo 1: Introduzione alla Guida per la protezione di Windows Server 2003'
Title: 'Capitolo 1: Introduzione alla Guida per la protezione di Windows Server 2003'
ms:assetid: '8a6cda2e-32c2-4945-897f-0353cd6e908a'
ms:contentKeyID: 20213201
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163108(v=TechNet.10)'
---

Guida per la protezione di Windows Server 2003
==============================================

### Capitolo 1: Introduzione alla Guida per la protezione di Windows Server 2003

##### In questa pagina

[](#eiaa)[Panoramica](#eiaa)
[](#ehaa)[Riepilogo generale](#ehaa)
[](#egaa)[Destinatari della guida](#egaa)
[](#efaa)[Ambito di applicazione della guida](#efaa)
[](#eeaa)[Riepilogo dei capitoli](#eeaa)
[](#edaa)[Competenze e conoscenze](#edaa)
[](#ecaa)[Requisiti del software](#ecaa)
[](#ebaa)[Convenzioni di stile](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

La Guida per la protezione di *Windows* *Server* *2003*. Questa guida è stata redatta per fornire le migliori informazioni disponibili per valutare e determinare i rischi di protezione nell'organizzazione che potrebbero interessare Microsoft Windows Server 2003 con Service Pack 1 (SP1). I capitoli in questa guida forniscono istruzioni dettagliate su come migliorare le configurazioni di impostazione della protezione e le funzionalità in Windows Server 2003 per offrire la possibilità di difendersi da eventuali pericoli presenti nell'ambiente in oggetto. Questa guida è stata creata per i tecnici di sistema, i consulenti e gli amministratori di rete che lavorano in un ambiente Windows Server 2003 con SP1.

Questa guida è stata rivista e approvata dai team tecnici di Microsoft, consulenti, personale addetto al supporto tecnico oltre che da clienti e partner. Microsoft ha lavorato con i consulenti e i tecnici di sistema che hanno implementato Windows Server 2003, Windows XP e Windows 2000 in tutta una serie di ambienti per aiutare a stabilire le procedure migliori e più aggiornate per proteggere questi server e client. In questa guida sono descritte in modo dettagliato le migliori procedure.

La guida correlata, [*Pericoli e contromisure: impostazioni di protezione per*
*Windows Server 2003 ed il Windows XP*](http://technet.microsoft.com/it-it/library/dd162275) (disponibile all'indirizzo http://www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx), fornisce una panoramica dettagliata di tutte le principali impostazioni di protezione presenti in Windows Server 2003 con SP1 e in Windows XP con SP2. I capitoli dal 2 al 12 di questa guida contengono indicazioni, procedure e raccomandazioni dettagliate relative alla protezione, in modo da fornire un elenco delle operazioni che permetteranno di ottenere un elevato livello di protezione, per i computer dell'organizzazione che eseguono Windows Server 2003 con SP1. Per un approfondimento dei concetti illustrati in questa pubblicazione, consultare il *Microsoft Windows* *Server* *2003 Resource Kit*, *Microsoft Windows* *XP Resource Kit*, *Microsoft Windows* *2000 Security Resource Kit* e Microsoft TechNet.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo generale

A prescindere dall'ambiente in uso, è consigliabile prestare particolare attenzione alla protezione. Molte organizzazioni commettono l'errore di sottovalutare l'importanza dell'ambiente IT, in quanto i notevoli costi indiretti vengono generalmente esclusi. L'intera organizzazione potrebbe riportare danni ingenti in caso di attacco abbastanza grave ai server dell'ambiente. Ad esempio, un attacco che causa l'interruzione del sito Web aziendale e una perdita sostanziale in termini di fatturato o di fiducia del cliente potrebbe determinare il collasso dei profitti della società. Nella valutazione dei costi di protezione è consigliabile includere i costi indiretti associati a un eventuale attacco, nonché i costi dovuti alla perdita di funzionalità IT.

L'analisi della vulnerabilità, del rischio e dell'esposizione correlati alla protezione indica il compromesso tra utilizzabilità e protezione a cui sono soggetti tutti i sistemi in un ambiente di rete. In questa guida vengono presentate le principali contromisure di protezione disponibili in Windows XP, le vulnerabilità a cui rispondono e le potenziali conseguenze negative (se ve ne sono) dell'implementazione di ogni contromisura.

Inoltre, la guida fornisce i consigli specifici su come aumentare il livello di protezione dei computer che eseguono Windows Server 2003 con SP1 in tre ambienti aziendali distinti. L'ambiente Legacy Client (LC) supporta i sistemi operativi più vecchi come Windows 98. L'ambiente Enterprise Client (EC, Client organizzazione) è quello in cui Windows 2000 è la prima versione del sistema operativo Windows in uso. Il terzo ambiente è quello in cui la protezione riveste un ruolo talmente importante da rendere accettabili anche notevoli riduzioni della funzionalità e una maggiore complessità della gestione. Questo terzo ambiente è denominato Specialized Security – Limited Functionality (SSLF, Protezione Specializzata – Funzionalità Limitata). Le informazioni sono state organizzate in modo da risultare di facile accesso, consentendo di trovare rapidamente e determinare le impostazioni appropriate per i computer dell'organizzazione. Sebbene questa guida sia rivolta a utenti di organizzazioni, la maggior parte delle informazioni in essa contenute è valida per organizzazioni di tutte le dimensioni.

Per utilizzare in modo ottimale il materiale, è necessario leggere l'intera guida. È possibile fare riferimento anche alla guida correlata, [*Pericoli e contromisure: impostazioni di protezione per*
*Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), all'indirizzo http://www.microsoft.com/italy/technet/security/topics/serversecurity/tcg/tcgch00.mspx.

Il team che ha creato la guida si augura che gli argomenti trattati risultino utili, ricchi di informazioni e interessanti.

[](#mainsection)[Inizio pagina](#mainsection)

### Destinatari della guida

Questa guida è diretta principalmente a consulenti, specialisti della protezione, architetti di sistema e professionisti IT responsabili della pianificazione di applicazioni o dello sviluppo di infrastrutture e l'implementazione di Windows Server 2003. Questi ruoli comprendono le seguenti mansioni:

-   Architetti e addetti alla pianificazione responsabili dell'implementazione dei sistemi client all'interno dell'organizzazione.

-   Specialisti della protezione IT che si occupano esclusivamente della protezione delle piattaforme nelle organizzazioni di appartenenza.

-   Analisti e responsabili dei processi decisionali dell'azienda con il compito di soddisfare obiettivi e requisiti aziendali critici basati sul supporto tecnico per client.

-   Consulenti di servizi Microsoft e partner che necessitano di risorse dettagliate in relazione a informazioni utili per utenti e partner dell'organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione della guida

Questa guida si concentra su come creare e mantenere un ambiente sicuro per i computer che eseguono Windows Server 2003 con SP1 all'interno della propria organizzazione. Verranno illustrate le diverse fasi della procedura di protezione dei tre ambienti definiti nella guida e l'effetto di ogni impostazione dei server per le dipendenze dei client. Riportiamo di seguito la descrizione di questi servizi:

-   L'ambiente LC è composto da un dominio del servizio directory Active Directory con server membro e controller di dominio che eseguono Windows Server 2003 e alcuni computer client che eseguono Microsoft Windows 98 e Windows NT 4.0. Sui computer che eseguono Windows 98 deve essere installato il componente aggiuntivo Active Directory Client Extension (DSCLient). Per ulteriori informazioni consultare l'articolo della Microsoft Knowledge Base "[Come installare l'estensione client di Active Directory](http://support.microsoft.com/kb/288358/it)" all'indirizzo: http://support.microsoft.com/kb/288358/it.

-   L'ambiente client di organizzazione (LC) è composto da un dominio Active Directory con server membro e controller di dominio che eseguono Windows  Server 2003 con SP1 e computer client che eseguono Microsoft Windows 2000 e Windows XP.

-   L'ambiente SSLF è composto da un dominio Active Directory con server membro e controller di dominio che eseguono Windows  Server 2003 con SP1 e computer client che eseguono Windows 2000 e Windows XP. Tuttavia, le impostazioni SSLF sono talmente restrittive da non consentire il funzionamento di alcune applicazioni. Per questa ragione, le prestazioni dei server possono essere compromesse rendendone più difficile la gestione.

    I computer client non protetti dai criteri SSLF potrebbero inoltre avere problemi di comunicazione con i computer client e con i server protetti dai criteri SSLF. Per informazioni su come proteggere i computer client con impostazioni compatibili con SSLF, consultare la *Guida per la protezione di Windows XP*.

Per un gruppo di ruoli di server diversi vengono fornite le istruzioni su come aumentare la protezione dei computer in questi tre ambienti. Le contromisure descritte e gli strumenti forniti presumono che ogni server svolgerà un unico ruolo. Se è necessario abbinare i ruoli di alcuni dei server nell'ambiente in uso, è possibile personalizzare i modelli di protezione contenuti nel download che accompagna questa guida per creare la combinazione appropriata di servizi e di opzioni di protezione. I ruoli descritti in questa guida comprendono:

-   Controller di dominio

-   Server infrastruttura

-   File server

-   Server di stampa

-   Server IIS (Internet Information Services)

-   Server IAS (Internet Authentication Services)

-   Server Servizi certificati

-   Host Bastion

Le impostazioni consigliate in questa guida sono state completamente verificate in ambienti di prova che simulano gli ambienti client legacy, client di organizzazione e protezione specializzata/funzionalità limitata (SSLF, Specialized Security – Limited Functionality) descritti in precedenza. Le impostazioni si sono dimostrate valide nell'ambiente di prova, ma è indispensabile che l'organizzazione le verifichi in un contesto specifico che riproduca accuratamente l'ambiente di produzione in uso. Probabilmente sarà necessario apportare alcune modifiche ai modelli di protezione e alle procedure manuali descritte nella guida in modo da garantire il corretto funzionamento di tutte le applicazioni aziendali. Le informazioni dettagliate contenute nella guida correlata, *Pericoli e contromisure: impostazioni di protezione per Windows* *Server* *2003 e Windows* *XP* forniscono le istruzioni necessarie a valutare ogni contromisura specifica e a decidere quali sono pertinenti ai requisiti commerciali e all'ambiente esclusivo dell'organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo dei capitoli

La *Guida per la protezione di Windows* *Server* *2003* è composta da 13 capitoli. Ogni capitolo è basato sul processo completo necessario per l'implementazione e la protezione di Windows Server 2003 con SP1 nell'ambiente specifico. I capitoli iniziali descrivono come gettare le basi per meglio proteggere i server nell'organizzazione di appartenenza, mentre i rimanenti illustrano le procedure dedicate esclusivamente a ciascun ruolo di server.

#### Capitolo 1: Introduzione alla Guida per la protezione di Windows Server 2003

Questo capitolo introduce la *Guida per la protezione di Windows* *Server* *2003* e contiene una breve panoramica di ogni capitolo. Descrive gli ambienti client legacy, client di organizzazione e protezione specializzata/funzionalità limitata (SSLF, Specialized Security – Limited Functionality) e i computer in essi presenti.

#### Capitolo 2: Meccanismi di protezione avanzata di Windows Server 2003

Questo capitolo fornisce una panoramica dei principali meccanismi utilizzati per aumentare il livello di protezione di Windows Server 2003 con SP1 in questa guida: Configurazione guidata impostazioni di sicurezza (SCW) e criteri di gruppo Active Directory . Viene illustrata la modalità con cui SCW fornisce una struttura interattiva per creare, gestire e verificare i criteri di protezione per i server di Windows che svolgono ruoli diversi. Viene fornita anche una valutazione sulle capacità di SCW entro il contesto dei tre ambienti descritti nel Capitolo 1.

La seconda parte di questo capitolo contiene le descrizioni generali della struttura di Active Directory, di quella dell'unità organizzativa (OU), degli oggetti Criteri di gruppo (GPO), della struttura del gruppo amministrativo e del criterio di dominio. Questi argomenti sono discussi nel contesto dei tre ambienti descritti nel Capitolo 1 e forniscono una visione di un ambiente finale ideale e protetto.

Questo capitolo termina con un esame dettagliato di come questa guida combini le funzionalità migliori di SCW e gli approcci tradizionali basati su GPO per rafforzare Windows Server 2003 con SP1.

#### Capitolo 3: Criteri di dominio

In questo capitolo vengono analizzate le impostazioni del modello di protezione e le contromisure aggiuntive per i criteri a livello di dominio nei tre ambienti descritti nel Capitolo 1. Il capitolo non pone l'attenzione su un ruolo specifico del server, ma bensì sui criteri e sulle impostazioni specifiche utili per criteri di dominio di livello superiore.

#### Capitolo 4: Criterio di base per un server membro

In questo capitolo vengono analizzate le impostazioni del modello di protezione e le contromisure aggiuntive per ruoli diversi del server nei tre ambienti descritti nel Capitolo 1. L'obiettivo principale di questo capitolo è costituito dalla definizione di criteri di base dei server membro (MSBP) per i ruoli di server esaminati più avanti in questa guida.

I consigli contenuti in questo capitolo sono stati redatti per consentire alle organizzazioni di usare in tutta sicurezza le configurazioni di impostazione delle distribuzioni, nuove e già esistenti, di Windows Server 2003 con SP1. Si sono fatte delle ricerche e delle verifiche sulle configurazioni di protezione predefinite nell'ambito di Windows Server 2003 SP1 e i consigli contenuti in questo capitolo si prefiggono di fornire una protezione maggiore di quella offerta dalle impostazioni predefinite del sistema operativo. Di tanto in tanto si suggerisce un'impostazione meno restrittiva di quella presente nell'installazione predefinita di Windows Server 2003 con SP1 per fornire il supporto per gli ambienti client legacy.

#### Capitolo 5: Criterio di base per il controller di dominio

Il ruolo del server del controller di dominio è uno dei più importanti ruoli da proteggere in qualsiasi ambiente di Active Directory sui computer che eseguono Windows Server 2003 con SP1. La perdita o la compromissione di un controller di dominio potrebbe danneggiare seriamente i computer client, i server e le applicazioni che si affidano a tali controller per l’autenticazione, i criteri di gruppo e una directory LDAP (Lightweight Directory Access Protocol) centrale.

In questo capitolo è evidenziata la necessità di archiviare sempre i controller di dominio in posizioni fisiche protette, accessibili solo a personale amministrativo qualificato. Vengono esaminati i rischi legati alla collocazione dei controller di dominio in aree non protette e gran parte del capitolo è dedicata all'esposizione di considerazioni di protezione relative ai criteri di gruppo del controller di dominio consigliato.

I controller di dominio Active Directory richiedono un servizio DNS stabile e correttamente configurato. Per impostazione predefinita, Windows Server 2003 con SP1 integra le zone DNS nell'Active Directory, che consente ai controller di dominio di eseguire il servizio DNS e di rispondere alle richieste DNS per i client nel dominio Active Directory . Questo capitolo presuppone che il controller di dominio fornisca anche il servizio DNS e mette a disposizione le relative istruzioni.

#### Capitolo 6: Ruolo del server di infrastruttura

In questo capitolo, il ruolo del server di infrastruttura è definito come server DHCP o server WINS. Vengono forniti dettagli su come il Windows Server 2003 con i server di infrastruttura SP1 nell'ambiente in uso possono trarre vantaggio dalle impostazioni di protezione che non sono applicate dal criterio di base per un server membro (MSBP). Questo capitolo non contiene informazioni sulla configurazione per il servizio DNS, contenuto nel ruolo del controller di dominio.

#### Capitolo 7: Ruolo di File server

Questo capitolo si concentra sul ruolo del file server e sulle difficoltà collegate alla protezione elevata di tali server. I servizi più essenziali per i file server richiedono l'uso di protocolli relativi a NetBIOS Windows e di protocolli SMB e CIFS. I protocolli Server Message Block (SMB) e Common Internet File System (CIFS) sono di solito utilizzati per fornire l'accesso a utenti autenticati, ma se non sono protetti in modo adeguato, possono anche rivelare abbondanti informazioni a utenti non autenticati o a pirati informatici. A causa di questo pericolo, questi protocolli sono spesso disattivati negli ambienti con protezione elevata. Questo capitolo descrive come i file server che eseguono Windows Server 2003 con SP1 possono trarre vantaggio dalle impostazioni di protezione che non sono applicate dall'MSBP.

#### Capitolo 8: Ruolo del server di stampa

Questo capitolo si concentra sui server di stampa. Come i file server, i servizi più essenziali per i server di stampa richiedono l'uso di protocolli relativi a NetBIOS Windows e di protocolli SMB e CIFS. Come accennato in precedenza, questi protocolli sono spesso disattivati in ambienti con protezione elevata. Questo capitolo descrive come le impostazioni di protezione del server di stampa di Windows Server 2003 con SP1 possono essere rafforzate in vari modi non eseguiti dall'MSBP.

#### Capitolo 9: Ruolo del server Web

Questo capitolo descrive come, per proteggere a fondo i siti Web e le applicazioni, sia necessario proteggere un intero server IIS (compreso ciascun sito Web e applicazione eseguiti sul server IIS) da computer client presenti nell'ambiente in uso. I siti Web e le applicazioni devono inoltre essere protetti da altri siti Web e applicazioni eseguiti sullo stesso server IIS. Nel presente capitolo sono descritte in dettaglio anche le procedure necessarie a garantire che queste misure siano realizzate dai server IIS che eseguono Windows Server 2003 con SP1 nell'ambiente in uso.

Per impostazione predefinita, IIS non è installato nei sistemi della famiglia Microsoft Windows Server System . Durante l'installazione iniziale di IIS viene utilizzata una modalità altamente protetta, definita "bloccata", Per esempio, le impostazioni predefinite consentono a IIS di gestire solo il contenuto statico. Funzionalità quali le pagine ASP (Active Server Pages), ASP.NET, SSI (Server-Side Includes), Pubblicazioni WebDAV e le estensioni del server di Microsoft FrontPage dovranno essere abilitate manualmente dall'amministratore tramite il nodo Estensioni servizio Web in Gestione di Internet Information Services (IIS).

Le sezioni in questo capitolo espongono i dettagli su tutta una serie di impostazioni che possono essere utilizzate per aumentare la protezione dei server IIS nell'ambiente in uso. Per garantire che i server siano protetti, si pone l'enfasi sulla necessità di controllare, rilevare e rispondere a problematiche concernenti la protezione. Questo capitolo si concentra sui protocolli Web IIS e sulle applicazioni tipo HTTP e non contiene istruzioni sugli altri protocolli che IIS può fornire, come SMTP, FTP e NNTP.

#### Capitolo 10: Ruolo del server IAS

I server IAS (Internet Authentication Servers) offrono il servizio RADIUS (Remote Authentication Dial-In User Services), un protocollo di autenticazione basato su standard, progettato per verificare l'identità di client che accedono alle reti in modalità remota. Questo capitolo descrive il modo in cui i server IAS che eseguono Windows Server 2003 con SP1 possono trarre vantaggio dalle impostazioni di protezione che non sono applicate dall'MSBP.

#### Capitolo 11: Ruolo del server dei servizi certificati

I servizi certificati offrono i servizi di gestione della crittografia e dei certificati necessari a sviluppare un'infrastruttura a chiave pubblica (PKI) nell'ambiente server in uso. Questo capitolo descrive come i server IAS che eseguono Windows Server 2003 con SP1 possono trarre vantaggio dalle impostazioni di protezione non applicate dal criterio MSBP.

#### Capitolo 12: Ruolo degli host Bastion

I computer client possono accedere ai server host Bastion tramite Internet. In questo capitolo si spiega come questi computer esposti al pubblico siano esposti ad attacchi da parte di un vasto numero di utenti che possono rimanere completamente anonimi. Molte organizzazioni non estendono la loro infrastruttura di dominio a Internet. Per questa ragione, il contenuto di questo capitolo si concentra su come rafforzare i computer autonomi. Vengono forniti i dettagli su come gli host Bastion che eseguono Windows Server 2003 con SP1 possono trarre vantaggio dalle raccomandazioni di protezione contenute in questa guida per i computer membri di un dominio Active Directory.

#### Capitolo 13: Conclusioni

Il capitolo finale riesamina i punti salienti della guida offrendo brevi cenni su quanto discusso nei capitoli precedenti.

#### Appendice A: Formati e strumenti di protezione

Sebbene questa guida si concentri su come utilizzare SCW per creare i criteri che sono poi convertiti in modelli di protezione e in oggetti di Criteri di gruppo, ci sono tutta una serie di altri strumenti e formati di file che possono essere usati per ampliare o sostituire questa metodologia. Questa appendice fornisce una lista ristretta di questi strumenti e formati.

#### Appendice B: Impostazioni principali da considerare

Questa guida si occupa di molte contromisure e impostazioni di protezione, ma è importante comprendere che una parte di esse sono particolarmente importanti. Questa appendice descrive le impostazioni che avranno un maggiore impatto sulla protezione dei computer che utilizzano Windows Server 2003 con SP1.

#### Appendice C: Sommario di impostazione del modello di protezione

Questa appendice introduce la cartella di lavoro Microsoft Excel "Windows Server 2003 Security Guide Settings" contenuta con gli strumenti e i modelli nella [versione scaricabile](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en) di questa guida all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14846. Il presente foglio di calcolo è una copia originale completa sotto forma di modulo compatto e facile da usare di tutte le impostazioni consigliate per i tre ambienti che sono definiti in questa guida.

#### Appendice D: Verifica della Guida per la protezione di Windows  Server  2003

Questa guida contiene molte informazioni su come aumentare la protezione dei server con Windows Server 2003 con SP1, ma si consiglia il lettore di controllare e convalidare sempre tutte le impostazioni prima di implementarle in un ambiente di produzione.

Questa appendice contiene informazioni su come creare un ambiente di laboratorio di prova idoneo che può essere utilizzato per garantire la corretta implementazione delle impostazioni consigliate in un ambiente di produzione. Aiuta gli utenti a eseguire la convalida necessaria e minimizza l'ammontare di risorse necessarie a farlo.

#### Strumenti e modelli

Nella versione scaricabile della guida è allegata una raccolta di modelli di protezione, script e strumenti aggiuntivi per consentire all'organizzazione di valutare, verificare e implementare le contromisure consigliate. I modelli di protezione sono file di testo che possono essere importati nei criteri di gruppo basati sul dominio o applicati localmente tramite lo Snap-in Analisi e configurazione della protezione con Microsoft Management Console (MMC). Queste procedure sono descritte in dettaglio nel Capitolo 2, "Meccanismi di protezione avanzata di Windows Server 2003". Tra gli script contenuti in questa guida vi sono quelli per creare e collegare oggetti Criteri di gruppo oltre a script di prova che sono usati per verificare le contromisure consigliate. È stata allegata anche la cartella di lavoro di Excel che riassume le impostazioni del modello di protezione (di cui si è parlato nella "Appendice C" precedente).

I file che accompagnano questa guida sono collettivamente chiamati strumenti e modelli. Questi file sono contenuti in un file .msi nell'archivio WinZip autoestraente che contiene questa guida, disponibile nell'area di download di Microsoft all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14846. Dopo aver estratto i file dell'archivio, nel percorso specificato viene creata la seguente struttura di cartelle:

-   **\\Windows Server 2003 Security Guide Tools and Templates\\Security Templates**. Questa cartella contiene tutti i modelli di protezione discussi nella guida.

-   **\\Windows Server 2003 Security Guide Tools and Templates\\Test Tools.** Questa cartella contiene vari file e strumenti relativi alla "Appendice D: Verifica della Guida per la protezione di Windows Server 2003."

[](#mainsection)[Inizio pagina](#mainsection)

### Competenze e conoscenze

I professionisti IT che sviluppano, utilizzano e proteggono le installazioni di Windows Server 2003 e di Windows XP in un ambiente aziendale devono possedere le seguenti competenze e conoscenze:

-   Certificazione MCSE 2000 o 2003 con oltre due anni di esperienza in materia di protezione.

-   Conoscenza approfondita del dominio aziendale e di ambienti Active Directory.

-   Utilizzo degli strumenti di gestione, inclusi Microsoft Management Console (MMC), secedit, gpupdate e gpresult.

-   Esperienza nell'amministrazione di criteri di gruppo.

-   Esperienza nello sviluppo di applicazioni e workstation negli ambienti aziendali.

[](#mainsection)[Inizio pagina](#mainsection)

### Requisiti del software

I requisiti software necessari per l'utilizzo degli strumenti e dei modelli descritti in questa guida sono:

-   Windows Server 2003 Standard Edition con SP1, Windows Server 2003 Enterprise Edition con SP1 o Windows Server 2003 Datacenter Edition con SP1.

-   Un dominio Active Directory basato su Windows Server 2003.

-   Microsoft Excel 2000 o versioni successive.

[](#mainsection)[Inizio pagina](#mainsection)

### Convenzioni di stile

In questa guida vengono utilizzate le convenzioni di stile e la terminologia riportate di seguito.

**Tabella 1.1. Convenzioni di stile**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Elemento</th>
<th style="border:1px solid black;" >Significato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Grassetto</strong></td>
<td style="border:1px solid black;">Caratteri digitati esattamente come indicato, inclusi comandi, switch e nomi di file. Gli elementi dell'interfaccia utente sono riportati anche in grassetto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><em>Corsivo</em></td>
<td style="border:1px solid black;">I titoli di libri e di altre pubblicazioni importanti appaiono in corsivo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><em>&lt;Italic&gt;</em></td>
<td style="border:1px solid black;">Segnaposto in corsivo e parentesi ad angolo <em>&lt;file name&gt;</em> indicano le variabili.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Spaziatura fissa</td>
<td style="border:1px solid black;">Definisce i campioni di codici e script.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Nota</strong></td>
<td style="border:1px solid black;">Richiama l'attenzione del lettore su informazioni supplementari.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Importante</strong></td>
<td style="border:1px solid black;">Richiama l'attenzione del lettore su informazioni supplementari importanti.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questo capitolo ha fornito una panoramica dei principali fattori necessari alla protezione dei computer che eseguono Windows Server 2003 con SP1, già presi in considerazione e discussi più dettagliatamente nel resto della guida. Ora che si è capito come è stata strutturata questa guida, è possibile decidere se leggerla dall'inizio alla fine o se scegliere solo le sezioni che interessano.
  
È tuttavia importante tenere presente che per eseguire in modo corretto ed efficiente le operazioni di protezione è necessario acquisire nozioni di base in tutte le aree tematiche illustrate nella guida e non soltanto alcuni argomenti. Per questa ragione Microsoft consiglia la lettura della guida completa per trarre il massimo vantaggio da tutte le informazioni che contiene a livello d protezione dei computer che eseguono Windows Server 2003 con SP1 nell'organizzazione di appartenenza.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono informazioni aggiuntive sugli argomenti relativi alla protezione avanzata dei server che eseguono Windows Server 2003 con SP1.
  
-   Per ulteriori informazioni sulla protezione presso Microsoft, visitare la pagina [Trustworthy Computing](http://www.microsoft.com/mscorp/twc/default.mspx) all'indirizzo www.microsoft.com/mscorp/twc/default.msp .
  
-   Per ulteriori informazioni sulle soluzioni offerte da MOF alle imprese, visitare: [Microsoft Operations Framework](http://www.microsoft.com/technet/itsolutions/cits/mo/mof/default.mspx) all'indirizzo www.microsoft.com/technet/itsolutions/cits/mo/mof/default.msp .
  
-   Per informazioni sulle notifiche di protezione di Microsoft, visitare [Microsoft Security Bulletin Search](http://www.microsoft.com/technet/security/current.mspx) all'indirizzo www.microsoft.com/technet/security/current.aspx.
  
**Download**
  
[Utilizzo della Guida per la protezione di Windows Server 2003](http://www.microsoft.com/downloads/details.aspx?familyid=8a2643c1-0685-4d89-b655-521ea6c7b4db&displaylang=en)
  
**Notifiche di aggiornamento**
  
[Iscriversi per ottenere aggiornamenti e nuove versioni](http://go.microsoft.com/fwlink/?linkid=54982)
  
**Commenti e suggerimenti**
  
[Inviare commenti o suggerimenti](mailto:%20secwish@microsoft.com?subject=guida%20per%20la%20protezione%20di%20windows%20server%202003)
  
[](#mainsection)[Inizio pagina](#mainsection)
