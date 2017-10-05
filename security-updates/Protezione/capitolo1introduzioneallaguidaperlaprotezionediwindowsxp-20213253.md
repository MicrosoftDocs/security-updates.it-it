---
TOCTitle: 'Capitolo 1: Introduzione alla Guida per la protezione di Windows XP'
Title: 'Capitolo 1: Introduzione alla Guida per la protezione di Windows XP'
ms:assetid: '4eddb4e4-fd7b-444c-8484-bb8ee220c0e1'
ms:contentKeyID: 20213253
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163069(v=TechNet.10)'
---

Guida per la protezione di Windows XP
=====================================

### Capitolo 1: Introduzione alla Guida per la protezione di Windows XP

##### In questa pagina

[](#ehaa)[Panoramica](#ehaa)
[](#egaa)[Riepilogo generale](#egaa)
[](#efaa)[Destinatari della guida](#efaa)
[](#eeaa)[Ambito della guida](#eeaa)
[](#edaa)[Panoramica dei capitoli](#edaa)
[](#ecaa)[Contenuto del download](#ecaa)
[](#ebaa)[Convenzioni di stile](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Panoramica

La *Guida per la protezione di Windows XP*. Questa guida è stata progettata per offrire le migliori informazioni disponibili necessarie alla valutazione e alla determinazione dei rischi per la protezione specifici del sistema operativo Microsoft Windows XP Professional con Service Pack 2 (SP2) nell'ambiente. I capitoli di questa guida forniscono informazioni dettagliate sulla configurazione delle funzionalità e delle impostazioni di protezione migliorate di Windows XP, quando è possibile gestire i pericoli identificati all'interno del sistema. In particolare, la guida è stata progettata tenendo conto delle esigenze specifiche di consulenti, progettisti o tecnici di sistema che si occupano di ambienti Windows XP.

Le informazioni in questa guida sono state revisionate e approvate da team di progettazione Microsoft, consulenti, personale del supporto tecnico, clienti e partner per renderla:

-   **affidabile**, in quanto basata sulle esperienze effettuate sul campo;

-   **autorevole**, in virtù delle valide informazioni disponibili;

-   **accurata**, in quanto sottoposta a convalida e verifica tecnica;

-   **operativa**, poiché illustra le procedure corrette da utilizzare;

-   **specifica**, perché consente di risolvere problemi di protezione effettivi.

Le procedure consigliate di protezione dei computer client e server sono state sviluppate da consulenti e tecnici di sistema che hanno implementato Windows XP Professional, Microsoft Windows Server™ 2003 e Windows 2000 in una varietà di ambienti. Queste procedure sono descritte in dettaglio in questa guida. Le indicazioni, procedure e raccomandazioni passo a passo vengono fornite anche per consentire di potenziare la protezione dei computer dell'organizzazione dotati di Windows XP Professional con SP2.

Per un approfondimento dei concetti illustrati in questo materiale, vedere *Pericoli e contromisure: impostazioni di protezione per Windows* *Server 2003 e Windows* *XP*, il *Microsoft Windows* *XP Resource Kit*, il *Microsoft Windows* *Server 2003 Resource Kit*, il *Microsoft Windows Security Resource Kit* e Microsoft TechNet.

Questa guida è stata creata originariamente per Windows XP con SP1. Questa versione aggiornata indica i significativi miglioramenti della protezione forniti da Windows XP con SP2 ed è stata sviluppata e verificata con computer dotati di Windows XP Professional con SP2. Tutti i riferimenti a Windows XP presenti in questa guida si intendono rivolti a Windows XP con SP2, a meno di indicazioni contrarie.

[](#mainsection)[Inizio pagina](#mainsection)

### Riepilogo generale

A prescindere dal tipo di ambiente, si consiglia di prendere in seria considerazione le questioni di protezione. Molte organizzazioni sottovalutano l'importanza dell'ambiente IT, in quanto i costi indiretti significativi vengono generalmente esclusi. Se si verifica un attacco abbastanza grave ai server dell'ambiente, l'intera organizzazione potrebbe riportare danni ingenti. Ad esempio, un attacco che causa l'indisponibilità del sito Web aziendale e una perdita sostanziale in termini di fatturato o di fiducia del cliente potrebbe determinare il collasso dei profitti della società. Nella valutazione dei costi di protezione, è consigliabile includere i costi indiretti associati a un eventuale attacco, nonché i costi dovuti alla perdita di funzionalità IT.

L'analisi della vulnerabilità, del rischio e dell'esposizione correlati alla protezione indica il compromesso tra utilizzabilità e protezione a cui sono soggetti tutti i sistemi in un ambiente di rete. In questa guida vengono presentate le principali contromisure di protezione disponibili in Windows XP con SP2, le vulnerabilità a cui rispondono e le potenziali conseguenze negative dell'implementazione di ogni contromisura.

La guida fornisce raccomandazioni specifiche su come ottimizzare la protezione dei computer dotati di Windows XP con SP2 in tre ambienti comuni:

-   **Enterprise Client (EC).** I computer client in questo ambiente sono ubicati in un dominio del servizio Active Directory e devono comunicare soltanto con sistemi dotati di Windows 2000 o versioni successive del sistema operativo Windows.

-   **Autonomo (SA).** I computer client in questo ambiente non appartengono a un dominio Active Directory e possono avere bisogno di comunicare con sistemi dotati di Windows NT 4.0.

-   **Specialized Security – Limited Functionality (SSLF)**. L'importanza della protezione in questo ambiente è così grande che una perdita significativa di funzionalità e di facilità di gestione è accettabile. Per esempio, i computer ad uso militare e dei servizi segreti operano in questo tipo di ambiente.

La guida è organizzata in modo da risultare di facile accesso, consentendo di trovare rapidamente le informazioni necessarie per determinare le impostazioni appropriate per i computer Windows XP con SP2 dell'organizzazione. Sebbene questa guida sia rivolta a utenti di organizzazioni, la maggior parte delle informazioni in essa contenute è valida per organizzazioni di tutte le dimensioni.

Per utilizzare in modo ottimale il materiale, è necessario leggere l'intera guida. Il team che ha creato la guida si augura che gli argomenti trattati risultino utili, ricchi di informazioni e interessanti. Per ulteriori informazioni, vedere la guida correlata [*Pericoli e contromisure: impostazioni di protezione per Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), che è possibile scaricare all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159.

[](#mainsection)[Inizio pagina](#mainsection)

### Destinatari della guida

Questa guida è rivolta principalmente a consulenti, specialisti della protezione, architetti di sistema e professionisti IT responsabili della pianificazione dello sviluppo di applicazioni o infrastrutture e dell'installazione di workstation Windows XP in un ambiente di organizzazione. La guida non è destinata agli utenti privati ma è rivolta a persone che svolgono le seguenti mansioni:

-   Architetti di sistema e addetti alla pianificazione responsabili della gestione dell'architettura per i computer delle organizzazioni di appartenenza.

-   Specialisti della protezione IT che si occupano della protezione delle piattaforme informatiche all'interno di un'organizzazione.

-   Analisti e responsabili dei processi decisionali dell'azienda con il compito di soddisfare obiettivi e requisiti aziendali critici che richiedono il supporto IT per computer desktop o portatili.

-   Consulenti di servizi Microsoft e partner che necessitano di strumenti di trasferimento delle informazioni per utenti e partner dell'organizzazione.

#### Competenze e conoscenze

Le conoscenze e le competenze seguenti costituiscono i prerequisiti per gli amministratori e gli architetti incaricati dello sviluppo, dell'installazione e della protezione di computer client Windows XP in un'organizzazione.

-   Certificazione MCSE 2000 con oltre due anni di esperienza in materia di protezione o qualifica equivalente.

-   Conoscenza approfondita del dominio aziendale e di ambienti Active Directory.

-   Utilizzo degli strumenti di gestione, inclusi MMC, Secedit, Gpupdate e Gpresult.

-   Esperienza nell'amministrazione dei criteri di gruppo.

-   Esperienza nell'installazione delle applicazioni e dei computer client in ambienti di organizzazione.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito della guida

Nella guida viene descritta la procedura di creazione e mantenimento di un ambiente protetto per computer desktop e portatili dotati di Windows XP Professional con SP2. La guida illustra le diverse fasi della procedura di protezione di tre diversi ambienti e l'effetto di ogni impostazione per computer desktop e portatili installati in ciascuno di questi ambienti. Le informazioni si riferiscono agli ambienti client di organizzazione (EC, Enterprise Client) e protezione specializzata/funzionalità limitata (SSLF, Specialized Security – Limited Functionality).

Le impostazioni che non sono specificatamente consigliate come parte di questa guida non sono documentate. Per una descrizione dettagliata di tutte le impostazioni di protezione in Windows XP, fare riferimento alla guida correlata [*Pericoli e contromisure: impostazioni di protezione per Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159.

#### Enterprise Client

L'ambiente Enterprise Client (EC) consiste in un dominio di Active Directory di Windows 2000 o Windows Server 2003. I computer client di questo ambiente verranno gestiti tramite criteri di gruppo applicati a siti, domini e unità organizzative (OU). I criteri di gruppo rappresentano un metodo centralizzato per la gestione dei criteri di protezione nell'ambiente.

#### Ambiente autonomo

L'ambiente Stand-Alone Client (SA) include computer client che non possono essere assegnati a un dominio o computer che non fanno parte di un dominio Windows NT 4.0. È necessario configurare questi computer client tramite le impostazioni Criterio locale. La gestione di computer autonomi può risultare di gran lunga più complessa rispetto alla gestione di account utente e criteri in un dominio basato su Active Directory.

#### Specialized Security – Limited Functionality

L'ambiente Specialized Security – Limited Functionality (SSLF) fornisce impostazioni di protezione elevata per i computer client. Quando vengono applicate queste impostazioni dei criteri di protezione, la funzionalità utente potrebbe essere notevolmente ridotta, perché è limitata a funzioni specifiche richieste solo per le operazioni necessarie. L'accesso è limitato ad applicazioni, servizi e ambienti di infrastruttura approvati. In altre parole, le impostazioni dei criteri di protezione degli ambienti SSLF si riferiscono solo ad alcuni sistemi in un numero ristretto di organizzazioni, come l'esercito o i servizi segreti. Queste impostazioni tendono a favorire la protezione rispetto alla facilità di gestione e all'utilizzabilità; dovrebbero essere utilizzate soltanto sui computer la cui violazione causerebbe ingenti perdite finanziarie o la morte. In pratica, le impostazioni SSLF non rappresentano una scelta ragionevole per la maggior parte delle organizzazioni.

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica dei capitoli

Windows XP con SP2 è la versione più affidabile del sistema operativo client Windows ad oggi, con funzionalità di protezione e privacy migliorate. La protezione complessiva di Windows XP è stata migliorata per garantire la sicurezza delle attività e un ambiente protetto all'interno dell'organizzazione. La *Guida per la protezione* di *Windows* XP è composta da sette capitoli, e i capitoli dal due al sei descrivono le procedure richieste per creare tale ambiente. Ciascuno di questi capitoli utilizza un processo end-to-end progettato per proteggere computer basati su Windows XP.

#### Capitolo 1: Introduzione alla Guida per la protezione di Windows XP

Questo capitolo contiene informazioni generali sulla guida, gli utenti a cui è rivolta, i problemi presentati e lo scopo complessivo.

#### Capitolo 2: Configurazione dell'infrastruttura per il dominio di Active Directory

È possibile utilizzare criteri di gruppo per gestire ambienti utente e di computer nei domini di Windows Server 2003 e Windows 2000. I criteri di gruppo costituiscono uno strumento essenziale per la protezione di Windows XP ed è possibile utilizzarli per applicare e mantenere criteri di protezione coerenti in una rete da una posizione centrale. Questo capitolo descrive le operazioni preliminari che devono essere effettuate nel dominio prima di applicare i Criteri di gruppo ai computer client Windows XP.

Le impostazioni dei Criteri di gruppo vengono archiviate negli oggetti Criteri di gruppo (GPO) sui controller di dominio. I GPO sono collegati a siti, domini e unità organizzative (OU) all'interno della struttura di Active Directory. Poiché i criteri di gruppo sono così strettamente integrati con Active Directory, prima di implementarli è importante acquisire una conoscenza di base della struttura di Active Directory e delle implicazioni relative alla protezione.

#### Capitolo 3: Impostazioni di protezione per i client Windows XP

In questo capitolo vengono illustrate le impostazioni di protezione per computer client Windows XP che è possibile configurare tramite i criteri di gruppo in un dominio di Active Directory di Windows 2000 o Windows Server 2003. La guida non descrive tutte le impostazioni disponibili, ma soltanto le impostazioni utili per la protezione di un ambiente dai pericoli più comuni. La guida consente inoltre agli utenti di continuare a eseguire sui propri computer le normali attività di lavoro. Le impostazioni configurate dovrebbero essere basate sugli obiettivi di protezione dell'organizzazione.

#### Capitolo 4: Modelli amministrativi per Windows XP

In questo capitolo vengono descritte le impostazioni che è possibile aggiungere a Windows XP tramite i modelli amministrativi. I modelli amministrativi sono file Unicode che possono essere utilizzati per la configurazione di impostazioni basate sul Registro di sistema che regolano il funzionamento di vari servizi, applicazioni e componenti del sistema operativo. Esistono molti Modelli amministrativi utilizzabili con Windows XP e tali modelli contengono centinaia di impostazioni.

#### Capitolo 5: Protezione per client Windows XP autonomi

Sebbene la maggior parte di questa guida si concentri su ambienti EC (Enterprise Client) e SSLF (Specialized Security – Limited Functionality), questo capitolo descrive anche la configurazione di computer client Windows XP autonomi. Microsoft consiglia di distribuire Windows XP in una infrastruttura di dominio Active Directory, ma è consapevole che non è sempre possibile. Questo capitolo fornisce indicazioni sull'applicazione delle impostazioni consigliate su computer client Windows XP con SP2 che non appartengono a un dominio Windows 2000 o Windows Server 2003.

#### Capitolo 6: Criteri di restrizione software per client Windows XP

Questo capitolo fornisce una panoramica sui criteri di restrizione software, in modo da consentire ad amministratori con un meccanismo basato su criteri di identificare e limitare il software che può essere eseguito nel loro dominio. Gli amministratori possono utilizzare i criteri di restrizione software per impedire l'esecuzione di programmi non autorizzati ed evitare la diffusione di virus, cavalli di Troia o altro codice dannoso. I criteri di restrizione software sono completamente integrati in Active Directory e nei criteri di gruppo e possono essere utilizzati anche in un ambiente senza un'infrastruttura di dominio Windows Server 2003 quando applicati soltanto al computer locale.

#### Capitolo 7: Conclusioni

Il capitolo finale riesamina i punti importanti della guida, in una breve panoramica su quanto discusso nei capitoli precedenti.

#### Appendice A: Impostazioni principali da considerare

Sebbene questa guida descriva molte contromisure di protezione e impostazioni di protezione, è importante capire che una parte di esse sono particolarmente importanti. Questa appendice descrive le impostazioni che avranno l'impatto maggiore sulla protezione dei computer dotati di Windows XP con SP2.

#### Appendice B: Verifica della Guida per la protezione di Windows XP

Questa appendice descrive come la *Guida per la protezione* di *Windows* XP è stata verificata in un ambiente di laboratorio per assicurare che essa funzioni come previsto.

[](#mainsection)[Inizio pagina](#mainsection)

### Contenuto del download

Nella guida è inclusa una raccolta di modelli di protezione, script e file aggiuntivi per consentire la valutazione, la verifica e l'implementazione delle contromisure consigliate da parte dell'organizzazione.

I modelli di protezione sono file di testo che possono essere importati nei criteri di gruppo basati sul dominio o applicati localmente tramite lo snap-in MMC (Microsoft Management Console) Analisi e configurazione della protezione. Le procedure che descrivono come realizzare queste operazioni si trovano nel Capitolo 2, "Configurazione dell'infrastruttura per il dominio di Active Directory". È possibile utilizzare gli script contenuti in questa guida per implementare le contromisure consigliate su workstation autonome.

Nel contenuto del download è inclusa anche la cartella di lavoro Microsoft Excel "Impostazioni della Guida per la protezione di Windows XP", che descrive le impostazioni presenti in ciascuno dei modelli di protezione.

I file che accompagnano questa guida sono denominati generalmente strumenti e modelli. Questi file sono inclusi in un file .msi all'interno dell'archivio WinZip autoestraente che contiene questa guida, disponibile nell'area di download del sito Web Microsoft all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14840. Quando si esegue il file .msi, nel percorso specificato viene creata la seguente struttura di cartelle:

-   **\\Windows XP Security Guide Tools and Templates\\Security Templates**. Questa cartella contiene tutti i modelli di protezione trattati nei Capitoli 2 e 3 della guida. Contiene inoltre un foglio di lavoro di Excel che riassume tutte le raccomandazioni nella guida.

-   **\\Windows XP Security Guide Tools and Templates\\SCE Update**. Questa cartella contiene script e file di dati per aggiornare automaticamente l'interfaccia utente dell'Editor di configurazione della protezione come descritto nel Capitolo 3 della guida.

-   **\\Windows XP Security Guide Tools and Templates\\Stand Alone Clients**. Questa cartella contiene tutti gli script di esempio e i modelli utilizzati per rafforzare i computer autonomi, che sono trattati nel Capitolo 5 della guida.

-   **\\Windows XP Security Guide Tools and Templates\\Test Tools**. Questa cartella contiene gli strumenti relativi alla "Appendice B: Verifica della Guida per la protezione di Windows XP".

[](#mainsection)[Inizio pagina](#mainsection)

### Convenzioni di stile

In questa guida vengono utilizzate le seguenti convenzioni di stile.

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
<td style="border:1px solid black;">Caratteri digitati esattamente come indicato, inclusi comandi, switch<br />
e nomi di file. Anche gli elementi dell'interfaccia utente sono riportati in grassetto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><em>Corsivo</em></td>
<td style="border:1px solid black;">I titoli dei libri e altre pubblicazioni essenziali sono riportati in <em>corsivo.</em></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><em>&lt;Corsivo&gt;</em></td>
<td style="border:1px solid black;">I segnaposto in corsivo e le parentesi ad angolo &lt;<em>nome file</em>&gt; rappresentano le variabili.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><pre><code>Monospace font</code></pre></td>
<td style="border:1px solid black;">Vengono definiti gli esempi di codice e di script.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Nota</strong></td>
<td style="border:1px solid black;">Richiama l'attenzione del lettore su informazioni supplementari.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Importante</td>
<td style="border:1px solid black;">Richiama l'attenzione del lettore su essenziali informazioni supplementari.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Questo capitolo rappresenta un'introduzione alla *Guida per la protezione* di *Windows* XP e riassume i capitoli della guida. Dopo aver letto le informazioni sull'organizzazione della guida, è possibile individuare come sfruttare in modo ottimale i vantaggi delle opzioni principali di protezione incorporate in Windows XP con SP2.
  
Per eseguire in modo corretto ed efficiente le operazioni di protezione è necessario acquisire nozioni di base in tutte le aree tematiche illustrate nella guida e non soltanto in un singolo argomento. Pertanto, è consigliabile implementare tutte le raccomandazioni in questa guida che sono appropriate per l'organizzazione, come parte di un'ampia architettura di protezione a più livelli.
  
#### Ulteriori informazioni
  
I seguenti collegamenti forniscono ulteriori informazioni su argomenti relativi alla protezione di Windows XP Professional.
  
-   Per ulteriori informazioni sulle impostazioni di protezione che è possibile configurare su Microsoft Windows XP, vedere la guida correlata [*Pericoli e contromisure: impostazioni di protezione per Windows Server 2003 e Windows XP*](http://technet.microsoft.com/it-it/library/dd162275), disponibile all'indirizzo http://go.microsoft.com/fwlink/?LinkId=15159.
  
-   Per informazioni sull'implementazione della protezione sui server analogamente a quando trattato in questa guida, vedere la [*Guida per la protezione di Windows Server 2003.*](http://technet.microsoft.com/it-it/library/cc163140) Le raccomandazioni in questa guida sono progettate per essere applicate ai server che devono supportare i computer client Windows XP configurati come descritto nei capitoli rimanenti. È disponibile in linea all'indirizzo http://go.microsoft.com/fwlink/?LinkId=14845.
  
-   Per informazioni su una più efficace gestione dei rischi per la protezione nell'organizzazione, vedere la [Guida alla gestione dei rischi di protezione](http://technet.microsoft.com/it-it/library/cc163151) all'indirizzo http://go.microsoft.com/fwlink/?LinkID=30794.
  
-   Per informazioni su come minimizzare l'impatto di software dannoso, vedere la [Guida alla difesa antivirus a più livelli](http://technet.microsoft.com/it-it/library/cc162791) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=28732.
  
-   Per informazioni su come ridurre la dipendenza dall'utilizzo di password per l'autenticazione nell'organizzazione, vedere la [Guida alla pianificazione dell'accesso protetto mediante smart card](http://technet.microsoft.com/it-it/library/cc170941) all'indirizzo www.microsoft.com/italy/technet/security/topics/networksecurity/securesmartcards/default.mspx.
  
-   Per informazioni su un più efficace controllo e intervento su potenziali violazioni di protezione nell'organizzazione, vedere la [Guida alla pianificazione del monitoraggio della protezione e della rilevazione degli attacchi](http://technet.microsoft.com/it-it/library/cc162797) all'indirizzo www.microsoft.com/italy/technet/security/topics/auditingandmonitoring/securitymonitoring/default.mspx.
  
-   Per ulteriori dettagli sul supporto fornito da [Microsoft Operations Framework (MOF)](http://www.microsoft.com/mof) all'organizzazione, vedere il sito www.microsoft.com/italy/technet/itsolutions/mo/mof/default.mspx.
  
-   Per informazioni sulla [protezione](http://www.microsoft.com/italy/security/) di Microsoft Windows, vedere il sito www.microsoft.com/italy/security/.
  
-   Per informazioni sul servizio [Microsoft Security Notification Service](http://www.microsoft.com/technet/security/bulletin/notify.mspx), vedere il sito www.microsoft.com/technet/security/bulletin/notify.asp.
  
##### Download
  
[![](images/Cc163069.icon_exe(it-it,TechNet.10).gif)Scaricare la Guida per la protezione di Windows XP](http://www.microsoft.com/downloads/details.aspx?familyid=2d3e25bc-f434-4cc6-a5a7-09a8a229f118&displaylang=en)
  
[](#mainsection)[Inizio pagina](#mainsection)
