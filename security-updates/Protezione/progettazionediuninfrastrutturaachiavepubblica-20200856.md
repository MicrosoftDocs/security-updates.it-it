---
TOCTitle: 'Progettazione di un''infrastruttura a chiave pubblica'
Title: 'Progettazione di un''infrastruttura a chiave pubblica'
ms:assetid: 'bb1d966b-e8c5-44f5-8d12-0cbb9ad74544'
ms:contentKeyID: 20200856
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536257(v=TechNet.10)'
---

Pianifica la protezione di una LAN wireless con Windows Server 2003 Certificate Services
========================================================================================

### Progettazione di un'infrastruttura a chiave pubblica

##### In questa pagina

[](#ejaa)[Argomenti del modulo](#ejaa)
[](#eiaa)[Obiettivi](#eiaa)
[](#ehaa)[Ambito di applicazione](#ehaa)
[](#egaa)[Utilizzo del modulo](#egaa)
[](#efaa)[Definizione dei requisiti del certificato](#efaa)
[](#eeaa)[Progettazione della gerarchia dell'Autorità di certificazione](#eeaa)
[](#edaa)[Configurazione dei certificati](#edaa)
[](#ecaa)[Creazione di un piano per la gestione dei certificati](#ecaa)
[](#ebaa)[Riepilogo](#ebaa)
[](#eaaa)[Ulteriori informazioni](#eaaa)

### Argomenti del modulo

Nel presente modulo verrà esaminato il processo di progettazione di un'infrastruttura a chiave pubblica (PKI, Public Key Infrastructure) basata su Servizi certificati Microsoft® Windows® 2003. Al fine di contenere i costi di distribuzione e gestione, viene presa in esame una configurazione semplice che si adatta facilmente alla procedura di rilascio di certificati per client di reti senza fili protette e infrastrutture WLAN (Wireless Local Area Network).

Per proteggere gli investimenti sostenuti per l'infrastruttura, la configurazione descritta di seguito è di tipo estendibile. Questo non significa necessariamente che sia possibile rilasciare qualsiasi tipo di certificato. Tuttavia, grazie all'aggiunta di ulteriori funzionalità, in futuro sarà possibile fare fronte a un più ampio set di requisiti di protezione rispetto a quelli descritti nel presente modulo.

[](#mainsection)[Inizio pagina](#mainsection)

### Obiettivi

Utilizzare questo modulo per:

-   Definire i requisiti dei certificati.

-   Progettare una gerarchia per l'autorità di certificazione (CA, Certification Authority).

-   Configurare certificati.

-   Creare un piano per la gestione dei certificati.

[](#mainsection)[Inizio pagina](#mainsection)

### Ambito di applicazione

Questo modulo si applica ai seguenti prodotti e tecnologie:

-   Microsoft Windows Server™ 2003

-   Servizi certificati Microsoft Windows 2003

-   Servizio Active Directory®

-   Internet Information Services (IIS) 6.0

[](#mainsection)[Inizio pagina](#mainsection)

### Utilizzo del modulo

In questo modulo vengono descritte la metodologia e la procedura richieste per pianificare e distribuire l'infrastruttura a chiave pubblica più adatta alle esigenze attuali e future dell'azienda. Oltre alla protezione della rete LAN senza fili, questa guida fornisce anche indicazioni su come soddisfare numerosi requisiti di protezione dell'organizzazione.

Per sfruttare al massimo il presente modulo:

-   Leggere il white paper "An Introduction to the Windows 2000 Public Key Infrastructure", in cui viene fornita un'introduzione generale ai concetti di base delle infrastrutture PKI e all'utilizzo di Servizi certificati. <http://technet.microsoft.com/en-us/library/cc768063.aspx> (in inglese).

-   Leggere il capitolo "Designing a Public Key Infrastructure" disponibile in *Microsoft Windows Server 2003 Resource Kit*, che consente di comprendere i principi e la terminologia dell'infrastruttura PKI. <http://technet.microsoft.com/en-us/library/cc773138.aspx> (in inglese).

-   Leggere il capitolo "Core PKI Services: Authentication, Integrity and Confidentiality", in cui vengono presentati i servizi principali associati a un'infrastruttura PKI. [http://www.microsoft.com/technet/security/topics/identity/corepki.asp](http://technet.microsoft.com/en-us/library/cc700808.aspx) (in inglese).

-   Leggere la guida introduttiva "Best Practices for Implementing a Microsoft Windows Server 2003 Public Key Infrastructure", in cui vengono descritte in maniera dettagliata le procedure ottimali per l'implementazione di un'infrastruttura PKI in Windows Server 2003. [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/maintain/operate/ws3pkibp.asp](http://technet.microsoft.com/en-us/library/cc772670.aspx) (in inglese).

[](#mainsection)[Inizio pagina](#mainsection)

### Definizione dei requisiti del certificato

In questa sezione vengono definiti i motivi per il rilascio di certificati da parte dell'infrastruttura PKI e i requisiti di protezione necessari.

#### Creazione di una dichiarazione delle procedure di certificazione

Durante la progettazione di un'infrastruttura PKI è necessario registrare le decisioni su modalità di rilascio e utilizzo dei certificati all'interno dell'organizzazione. Tali decisioni vengono definite criteri di certificazione. I documenti in cui vengono registrate sono invece denominati dichiarazioni dei criteri di certificazione e dichiarazioni delle procedure di certificazione (CPS, Certificate Practice Statements).

A livello formale, una dichiarazione dei criteri di certificazione è un insieme di regole che indicano l'applicabilità di un certificato a un gruppo specifico di client o applicazioni con requisiti di protezione comuni. Una dichiarazione CPS invece riguarda le procedure utilizzate all'interno di un'organizzazione per gestire il rilascio di certificati. Tale dichiarazione contiene la descrizione di come vengono interpretati i criteri di certificazione nel contesto delle procedure operative e dell'architettura di sistema aziendali.

In alcune organizzazioni e in specifici utilizzi di certificati, le dichiarazioni dei criteri e delle procedure di certificazione sono considerate documenti o dichiarazioni di non responsabilità con valore legale. In questo caso è generalmente necessario avvalersi di una consulenza legale specializzata, pertanto tale argomento esula dalla presente trattazione. In ogni caso, tali documenti non sono indispensabili per la creazione dell'infrastruttura PKI, quindi, in assenza di forti motivazioni legali o commerciali, è consigliabile evitare di investire tempo e denaro nella realizzazione e la gestione di dichiarazioni formali di procedure e criteri di certificazione.

Anche nei casi in cui non sia necessaria una dichiarazione CPS formale, è bene documentare i criteri di certificazione e le procedure operative. Da un lato i criteri di certificazione devono diventare parte integrante dei criteri di protezione generali adottati dall'organizzazione, dall'altro le procedure operative devono essere incluse tra le procedure per la gestione della protezione. Sarà possibile fare riferimento a questo processo come a una dichiarazione CPS informale.

In base all'utilizzo previsto per l'infrastruttura PKI, è necessario decidere se creare o meno una dichiarazione formale dei criteri e delle procedure di certificazione. Se si necessita di una dichiarazione CPS formale, sarà probabilmente necessario pubblicarla e includere i riferimenti corrispondenti nei certificati CA. Sebbene in questa guida non sia inclusa alcuna indicazione su come realizzare una dichiarazione CPS formale, istruzioni sulla pubblicazione sono disponibili nel modulo "[Implementazione dell'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536249)" della *Guida all'implementazione*. Le dichiarazioni CPS informali invece non necessitano generalmente di pubblicazione.

Nella parte restante di questo modulo viene spesso fatto riferimento alla documentazione di decisioni adottate in merito alle dichiarazioni CPS. Tali istruzioni sono ugualmente valide per dichiarazioni CPS formali e informali.

Nella parte finale del modulo, nella sezione "[Ulteriori informazioni](#xsltsection130121120120)", sono disponibili informazioni aggiuntive sulla creazione di una dichiarazione CPS.

#### Identificazione delle applicazioni dei certificati

Il primo passaggio del processo di progettazione di un'infrastruttura PKI consiste nell'identificare le applicazioni in cui verranno utilizzati i certificati. Per ogni applicazione è necessario documentare i tipi e il numero approssimativo di certificati necessari. In questa fase non viene richiesto di specificare alcun dettaglio sul certificato, ma solo di fornirne una breve descrizione.

Per la soluzione senza fili protetta è necessario disporre di certificati per client senza fili e per server RADIUS (Remote Authentication Dial-In User Service) Windows. I tipi di certificato vengono illustrati nella tabella riportata di seguito. Sebbene non sia effettivamente necessario, l'infrastruttura PKI consente inoltre di rilasciare certificati ai controller di dominio (impostazione predefinita quando viene installata una CA Windows 2003 Enterprise nell'insieme di strutture).

**Tabella 1. Requisiti dei certificati per la soluzione senza fili protetta**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Applicazione</th>
<th>Tipo di certificato</th>
<th>Numero di certificati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">WLAN protetta</td>
<td style="border:1px solid black;">Certificati di autenticazione client per utenti</td>
<td style="border:1px solid black;">Tutti gli utenti che richiedono l'accesso a WLAN</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Certificati di autenticazione client per computer</td>
<td style="border:1px solid black;">Tutti i computer della rete LAN senza fili</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Certificati di autenticazione server per il server IAS (Servizio di autenticazione Internet)</td>
<td style="border:1px solid black;">Tutti i server IAS</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Active Directory</td>
<td style="border:1px solid black;">Autenticazione del controller di dominio</td>
<td style="border:1px solid black;">Tutti i controller di dominio nell'insieme di strutture</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Certificati di replica di directory per la firma di messaggi di replica di SMTP (Simple Mail Transfer Protocol)</td>
<td style="border:1px solid black;">Tutti i controller di dominio nell'insieme di strutture</td>
</tr>
</tbody>
</table>
  
In futuro sarà possibile utilizzare l'infrastruttura PKI per il rilascio di certificati relativi alle applicazioni indicate nelle tabelle riportate di seguito.
  
**Tabella 2. Potenziali requisiti di certificati futuri**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Applicazione</th>
<th>Tipo di certificato</th>
<th>Numero di certificati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Rete privata virtuale (VPN) per accesso client</td>
<td style="border:1px solid black;">Autenticazione computer client (IPSec)</td>
<td style="border:1px solid black;">Tutti i client VPN remoti</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VPN branch-to-branch</td>
<td style="border:1px solid black;">Autenticazione server VPN (IPSec)</td>
<td style="border:1px solid black;">Tutti i router VPN</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Protezione IP (IPSec)</td>
<td style="border:1px solid black;">Autenticazione computer client</td>
<td style="border:1px solid black;">Tutti i computer client e server che richiedono IPSec</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Protezione Web</td>
<td style="border:1px solid black;">Autenticazione utenti di applicazioni Web della rete Intranet</td>
<td style="border:1px solid black;">Tutti gli utenti</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Server Web della rete Intranet</td>
<td style="border:1px solid black;">Server Web della rete Intranet protetta</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Crittografia file system (EFS)</td>
<td style="border:1px solid black;">Utente di EFS</td>
<td style="border:1px solid black;">Tutti gli utenti</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Ripristino dei dati EFS</td>
<td style="border:1px solid black;">Agenti di ripristino</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Posta elettronica protetta</td>
<td style="border:1px solid black;">Firma e crittografia di Secure/Multipurpose Internet Mail Extensions (S/MIME)</td>
<td style="border:1px solid black;">Tutti gli utenti di posta elettronica</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Ripristino di chiavi</td>
<td style="border:1px solid black;">Agenti di ripristino</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Smart card</td>
<td style="border:1px solid black;">Accesso con smart card</td>
<td style="border:1px solid black;">Utenti di dominio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Firma del codice</td>
<td style="border:1px solid black;">Firma macro e codice interno</td>
<td style="border:1px solid black;">Responsabile del rilascio del codice</td>
</tr>
</tbody>
</table>
  
#### Definizione dei client dei certificati
  
È necessario definire i client che utilizzeranno i certificati relativi alle applicazioni indicati nella sezione precedente. In questo contesto con il termine "client" si intende qualsiasi utente, processo software o dispositivo che utilizza i certificati rilasciati dall'infrastruttura PKI e quindi sono inclusi utenti, server, workstation, dispositivi di rete e così via. È necessario tenere in considerazione due principali categorie di client: il soggetto certificato e altri utenti del certificato.
  
I soggetti del certificato sono i client ai quali verrà rilasciato un certificato mediante l'infrastruttura PKI. Gli altri utenti dei certificati invece sono client che necessitano, ad esempio, di verificare i certificati o di individuarli in una directory, ma ai quali non verranno rilasciati certificati. I soggetti del certificato sono generalmente anche gli utenti del certificato.
  
Sia per i soggetti che per gli utenti, è necessario classificare ciascun tipo di client rispondendo alle seguenti domande:
  
-   Il client è una persona, un computer, un dispositivo o un processo software?
  
-   Su quali piattaforme (versione del sistema operativo) verranno utilizzati i certificati?
  
-   Qual è il percorso logico del client? Esiste, ad esempio, una connessione alla rete LAN interna, a un'organizzazione partner, a Internet e così via?
  
-   Il client è un membro del dominio? In caso affermativo, si trova in un dominio differente, in un insieme di strutture differente o in un dominio non attendibile?
  
-   Quale tipo di operazioni deve eseguire il client? Ad esempio, registrare certificati, firmare certificati, verificare trust dei certificati, individuare certificati in una directory e verificare lo stato di revoca dei certificati.
  
Questa categorizzazione si ripercuoterà su numerose decisioni relative alla progettazione, quali la modalità di rilascio del certificato, il livello di affidabilità che è possibile stabilire per un certificato specifico e la modalità di pubblicazione delle informazioni relative alla revoca dei certificati.
  
Le categorie di client disponibili in questa soluzione vengono riepilogate nella tabella che segue.
  
**Tabella 3. Categorie dei soggetti dei certificati**
  
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
<th>Certificato</th>
<th>Tipo di client</th>
<th>Piattaforma</th>
<th>Percorso</th>
<th>Dominio</th>
<th>Operazioni relative ai certificati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione client senza fili</td>
<td style="border:1px solid black;">Utente</td>
<td style="border:1px solid black;">Windows XP</td>
<td style="border:1px solid black;">Rete interna</td>
<td style="border:1px solid black;">Membro di dominio</td>
<td style="border:1px solid black;">- Registrazione<br />
- Autenticazione</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Autenticazione client senza fili</td>
<td style="border:1px solid black;">Computer</td>
<td style="border:1px solid black;">Windows XP</td>
<td style="border:1px solid black;">Rete interna</td>
<td style="border:1px solid black;">Membro di dominio</td>
<td style="border:1px solid black;">- Registrazione<br />
- Autenticazione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione server IAS</td>
<td style="border:1px solid black;">Computer</td>
<td style="border:1px solid black;">Microsoft Windows Server 2003</td>
<td style="border:1px solid black;">Rete interna</td>
<td style="border:1px solid black;">Membro di dominio</td>
<td style="border:1px solid black;">- Registrazione<br />
- Autenticazione<br />
- Canale protetto</td>
</tr>
</tbody>
</table>
 

In questa applicazione, gli utenti dei certificati saranno rappresentati dallo stesso set di client ma con ruoli invertiti. Il server Microsoft Internet Authentication Service (IAS), ad esempio, diventa l'utente dei certificati del client che deve eseguire la verifica.

**Tabella 4. Categorie degli utenti dei certificati**

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
<th>Certificato</th>
<th>Tipo di client</th>
<th>Piattaforma</th>
<th>Percorso</th>
<th>Dominio</th>
<th>Operazioni relative ai certificati</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione client senza fili</td>
<td style="border:1px solid black;">Computer</td>
<td style="border:1px solid black;">Windows Server 2003</td>
<td style="border:1px solid black;">Rete interna</td>
<td style="border:1px solid black;">Membro di dominio</td>
<td style="border:1px solid black;">- Verifica</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Autenticazione client senza fili</td>
<td style="border:1px solid black;">Computer</td>
<td style="border:1px solid black;">Windows Server 2003</td>
<td style="border:1px solid black;">Rete interna</td>
<td style="border:1px solid black;">Membro di dominio</td>
<td style="border:1px solid black;">- Verifica</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione server IAS</td>
<td style="border:1px solid black;">Computer utente</td>
<td style="border:1px solid black;">Windows XP</td>
<td style="border:1px solid black;">Rete interna</td>
<td style="border:1px solid black;">Membro di dominio</td>
<td style="border:1px solid black;">- Verifica</td>
</tr>
</tbody>
</table>
  
La tabella precedente consente di identificare le piattaforme e il tipo di operazioni da supportare. Sebbene non sia il caso di questo scenario, per altre applicazioni può risultare necessario il supporto di ricerche o verifiche di certificati per mezzo di client su Internet, la registrazione da piattaforme non Windows e così via. Poiché molti di questi aspetti devono essere decisi durante la fase iniziale del processo di progettazione, è importante individuare sin dall'inizio i potenziali requisiti dei certificati futuri.
  
Per quanto riguarda i requisiti futuri, in questa guida si presuppone quanto segue:
  
-   Sarà probabilmente necessaria la verifica dei certificati da client non Windows.
  
-   Sarà probabilmente necessaria la verifica dei certificati da Internet.
  
-   Sarà probabilmente necessario il supporto dei soggetti e degli utenti dei certificati su piattaforme diverse da Windows XP e Windows Server 2003.
  
Sebbene al momento la progettazione non riguardi necessariamente tali requisiti, sarà comunque possibile includerli facilmente.
  
#### Definizione dei requisiti di protezione dei certificati
  
La protezione di un certificato viene anche definita livello di garanzia e può essere considerata un punto di forza tra il soggetto certificato e il certificato stesso. Rappresenta inoltre il grado di certezza che la persona (o il dispositivo) che utilizza il certificato corrisponda realmente al soggetto indicato nel certificato. Il livello di garanzia è costituito da due aspetti principali:
  
-   Il rigore della registrazione e del processo di registrazione dei certificati. All'utente ad esempio viene richiesto di presentarsi di persona con un documento di identificazione per ottenere il certificato oppure è sufficiente disporre di un indirizzo di posta elettronica.
  
-   Il modo in cui viene archiviata la chiave privata: più è difficile copiare o compromettere la chiave, maggiore è la garanzia che essa sia in possesso del proprietario originale, ovvero il soggetto certificato.
  
Questi due aspetti sono strettamente correlati in quanto non esiste alcun motivo valido per sostenere costi onerosi per l'adozione di misure di protezione della chiave privata, se non si può essere certi dell'identità del proprietario della chiave privata. Allo stesso modo, un processo di registrazione complicato, che comprende approfonditi controlli in background e la rilevazione delle impronte digitali genetiche, è praticamente inutile senza un'adeguata e sicura archiviazione della chiave privata.
  
Il raggiungimento tuttavia di un elevato grado di protezione per un certificato comporta costi onerosi e spesso può risultare superfluo per diversi utilizzi dei certificati. Se non si desidera ottenere un elevato livello di garanzia per un certificato, è possibile far parte di un dominio autorizzato, in cui le credenziali del dominio vengono accettate come prova della registrazione di un certificato.
  
È necessario documentare lo scopo dei livelli di garanzia che vengono utilizzati nei criteri e nelle dichiarazioni sulle procedure di certificazione.
  
In questa guida vengono definiti i tre livelli di garanzia riportati nella tabella seguente.
  
**Tabella 5. Livelli di garanzia dei certificati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Livello</th>
<th>Requisiti di registrazione</th>
<th>Requisiti di archiviazione della chiave</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Basso</td>
<td style="border:1px solid black;">Approvazione automatica a seconda del dominio o altra password per l'identificazione</td>
<td style="border:1px solid black;">Chiavi software</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Media</td>
<td style="border:1px solid black;">Approvazione del Certificate Manager, controllo ID visivo (smart card) o firma dell'ufficio di registrazione</td>
<td style="border:1px solid black;">Chiavi software o token hardware a prova di manomissione (smart card o token USB)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Alta</td>
<td style="border:1px solid black;">Firma del responsabile della registrazione e approvazione del Certificate Manager</td>
<td style="border:1px solid black;">Token hardware a prova di manomissione (smart card o token USB)</td>
</tr>
</tbody>
</table>
  
Come è possibile notare, tali categorie presentano delle sovrapposizioni. Non si tratta di differenze strettamente tecniche, ma di differenze sui criteri dovute alle decisioni adottate per gestire i certificati all'interno dell'organizzazione. In generale, i certificati con garanzia elevata sono decisamente poco frequenti, mentre risultano essere molto comuni i certificati con garanzia bassa.
  
Le categorie di garanzia definite nella tabella precedente possono essere suddivise ulteriormente in tipi di soggetti differenti. La classificazione usata più comunemente è la seguente:
  
-   Computer: qualsiasi computer o dispositivo all'interno dell'organizzazione.
  
-   Utente interno: i dipendenti o il personale a tempo pieno con qualifica equivalente (ad esempio, collaboratori e così via).
  
-   Utente esterno: qualsiasi altra entità esterna all'organizzazione con la quale è in corso una collaborazione di tipo commerciale o legale (ad esempio, partner e clienti commerciali).
  
Il motivo di una simile distinzione consiste nel fatto che tipi differenti di soggetto adottano generalmente criteri diversi per i certificati, ovvero le condizioni che regolano il rilascio, la revoca, il rinnovo di un certificato e così via. Anche se non si dispone di piani specifici per una determinata categoria, è possibile documentare i criteri sui certificati che possono essere applicati a tale categoria affinché sia possibile preparare correttamente i criteri e le dichiarazioni CPS. Nella tabella seguente vengono descritti i risultati ottenuti dalla combinazione dei livelli di garanzia con le categorie di soggetti.
  
**Tabella 6. Categorie di protezione dei certificati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria di protezione dei certificati</th>
<th>Caratteristiche di esempio della categoria di protezione</th>
<th>Tipi di certificato di esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Certificati di computer</td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Certificati di computer con garanzia bassa</td>
<td style="border:1px solid black;">- Approvazione automatica basata sulle credenziali di dominio del computer<br />
- Rinnovo annuale</td>
<td style="border:1px solid black;">- Computer WLAN<br />
- IPSec</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Certificati di computer con garanzia media</td>
<td style="border:1px solid black;">- Approvazione del Certificate Manager obbligatoria<br />
- Archiviazione della chiave nel software<br />
- Rinnovo annuale</td>
<td style="border:1px solid black;">- Server Web<br />
- Autenticazione server IAS</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Certificati di computer con garanzia elevata</td>
<td style="border:1px solid black;">Nessuna</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Certificati per utenti interni</td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Certificati per utenti interni con garanzia bassa</td>
<td style="border:1px solid black;">- Approvazione automatica basata sulle credenziali di dominio dell'utente<br />
- Rinnovo annuale</td>
<td style="border:1px solid black;">Utente di EFS</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Certificati per utenti interni con garanzia media</td>
<td style="border:1px solid black;">- Approvazione del Certificate Manager o del responsabile della registrazione obbligatoria<br />
- Archiviazione della chiave su smart card o software<br />
- Rinnovo annuale</td>
<td style="border:1px solid black;">-Posta elettronica protetta<br />
- Autorizzazione finanziaria di basso valore<br />
- Accesso con smart card<br />
- Firma codice interno<br />
- Agente di ripristino dati<br />
- Agente di ripristino chiavi</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Certificati per utenti interni con garanzia elevata</td>
<td style="border:1px solid black;">- Verifica ID fisico del soggetto certificato obbligatoria<br />
- Approvazione del Certificate Manager obbligatoria<br />
- Firma dell'ufficio di registrazione su richiesta<br />
- Archiviazione della chiave su smart card<br />
- Rinnovo a sei mesi</td>
<td style="border:1px solid black;">- Autorizzazione finanziaria di alto valore<br />
- Firma del codice commerciale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Certificati utenti esterni</td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Certificati esterni con garanzia bassa</td>
<td style="border:1px solid black;">- Approvazione automatica basata sulle password assegnate in precedenza<br />
- Rinnovo annuale</td>
<td style="border:1px solid black;">Autenticazione client (autenticazione al sito Web Internet)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Certificati esterni con garanzia media</td>
<td style="border:1px solid black;">- Approvazione Certificate Manager obbligatoria<br />
- Archiviazione chiavi su smart card<br />
-Rinnovo a sei mesi</td>
<td style="border:1px solid black;">Autorizzazione finanziaria business-to-business (B2B)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Certificati esterni con garanzia elevata</td>
<td style="border:1px solid black;">- Verifica ID fisico del soggetto certificato obbligatoria<br />
- Approvazione del Certificate Manager obbligatoria<br />
- Firma dell'ufficio di registrazione su richiesta<br />
- Archiviazione della chiave su smart card<br />
- Rinnovo a sei mesi</td>
<td style="border:1px solid black;">Transazione B2B di valore molto elevato</td>
</tr>
</tbody>
</table>
  
**Nota:** in questa guida non è disponibile una definizione per i certificati di computer con garanzia elevata, in quanto non indispensabile se non si utilizza una classificazione specifica. In pratica, i certificati CA rientreranno in questa categoria, in particolare se si dispone di hardware di crittografia (HSM, Hardware Security Module) per l'archiviazione della chiave. Tuttavia, poiché si tratta di una categoria con uno scopo specifico e che non verrà utilizzata con le CA di emissione, in questa guida non vengono prese in considerazione le CA incluse in questa classificazione.
  
Benché non esistano delle ragioni tecniche per cui non sia possibile trattare allo stesso modo tipi di soggetti di certificati differenti, generalmente vengono definiti diversi criteri di protezione per tipi di soggetto differenti. I dipendenti interni ad esempio vengono trattati in maniera diversa rispetto al personale di altre organizzazioni. I diversi criteri di certificazione, e la loro inclusione in dichiarazioni CPS differenti, possono influire su come strutturare le CA per il rilascio di tipi di certificati differenti. Questo argomento verrà descritto successivamente in questo modulo.
  
È necessario inoltre verificare se lo stesso amministratore è in ultima analisi anche responsabile per il rilascio di certificati a queste tre categorie di utenti (o "entità finali" secondo la terminologia PKI). In numerose organizzazioni, la persona che può certificare la validità di un computer quale membro di dominio non è la stessa persona che può certificare l'identità di una società partner. Nella dichiarazione CPS è necessario pertanto stabilire queste relazioni di responsabilità.
  
##### Definizione della protezione dei certificati delle applicazioni
  
Le categorie di protezione dei certificati definite nella sezione precedente possono essere utilizzate per classificare i tipi di certificati per la progettazione, che vengono elencati nella seguente tabella.
  
**Tabella 7. Requisiti di protezione dei certificati**
  
<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di certificato</th>
<th>Categoria di protezione</th>
<th>Piattaforma</th>
<th>Posizione logica</th>
<th>Approvazione</th>
<th>Dimensione della chiave</th>
<th>Periodo di validità</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione client: Utente</td>
<td style="border:1px solid black;">Certificati di computer con garanzia bassa</td>
<td style="border:1px solid black;">- Windows XP<br />
- Windows Server 2003</td>
<td style="border:1px solid black;">Interna</td>
<td style="border:1px solid black;">Automatica (autenticazione dominio)</td>
<td style="border:1px solid black;">Media</td>
<td style="border:1px solid black;">Media</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Autenticazione client: Computer</td>
<td style="border:1px solid black;">Certificati per utenti con garanzia bassa</td>
<td style="border:1px solid black;">- Windows XP<br />
- Windows Server 2003</td>
<td style="border:1px solid black;">Interna</td>
<td style="border:1px solid black;">Automatica (autenticazione dominio)</td>
<td style="border:1px solid black;">Media</td>
<td style="border:1px solid black;">Media</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione server IAS</td>
<td style="border:1px solid black;">Certificati di computer con garanzia media</td>
<td style="border:1px solid black;">- Windows XP<br />
- Windows Server 2003</td>
<td style="border:1px solid black;">Interna</td>
<td style="border:1px solid black;">Manuale</td>
<td style="border:1px solid black;">Media</td>
<td style="border:1px solid black;">Media</td>
</tr>
</tbody>
</table>
  
Questi requisiti generali vengono perfezionati in profili di certificati specifici nella sezione "[Configurazione dei certificati](#xsltsection127121120120)" più avanti in questo modulo.
  
##### Combinazione degli scopi del certificato
  
È possibile unire una serie di funzioni dell'applicazione (o utilizzi) in un unico certificato affinché sia possibile utilizzare lo stesso certificato per firmare messaggi di posta elettronica, accedere alla rete e concedere l'accesso a un'applicazione. La combinazione di diverse funzioni comporta una riduzione del carico di gestione e archiviazione per i server di directory e certificati.
  
I certificati con diverse finalità presentano tuttavia alcuni svantaggi. Per applicazioni diverse ad esempio può rendersi necessario un processo di approvazione diverso per il certificato. Nella maggior parte dei casi si tratta di ragioni tecniche, anche se il motivo principale è generalmente dovuto al fatto che differenti applicazioni necessitano di livelli di protezione diversi per i certificati; pertanto, diversi livelli di garanzia uniscono il certificato al soggetto certificato stesso. Le differenze possono riguardare uno o tutti dei seguenti elementi:
  
-   Processo di approvazione del certificato
  
-   Lunghezza della chiave
  
-   Meccanismo di archiviazione della chiave
  
-   Durata del certificato
  
In questa guida è stata adottata la strategia di unire gli utilizzi dei certificati dotati dello stesso livello di protezione. I certificati di autenticazione client includeranno utilizzi per altre applicazioni con garanzia bassa, quali IPSec e autenticazione computer. Quando vengono definiti i requisiti per altri utilizzi dei certificati, è possibile includere anche tali utilizzi ed eseguire nuovamente il rilascio dei certificati; in questo caso è necessario imporre il rinnovo che può essere avviato dalla definizione del modello di certificato.
  
Poiché i certificati del server IAS sono considerati certificati con garanzia elevata, non sarà possibile combinare tali certificati con gli utilizzi delle applicazioni con garanzia bassa.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Progettazione della gerarchia dell'Autorità di certificazione
  
Per supportare le applicazioni aziendali basate sui certificati, è necessario definire una struttura di CA collegate che sarà responsabile del rilascio, della convalida, del rinnovo e della revoca dei certificati richiesti. Le autorità di certificazione, a loro volta, si avvalgono di un'infrastruttura IT sottostante per operazioni quali l'autenticazione dei soggetti dei certificati, la pubblicazione dei certificati e delle informazioni sulla revoca dei certificati.
  
L'obiettivo della creazione di un'infrastruttura CA consiste nel fornire un servizio affidabile agli utenti, una facilità di gestione agli amministratori e la flessibilità necessaria a far fronte alle esigenze attuali e future, garantendo contemporaneamente un livello di protezione ottimale per l'organizzazione.
  
#### Selezione di un modello di trust
  
La prima fase della progettazione di un'infrastruttura CA consiste nel determinare il modello di trust ottimale in base ai requisiti aziendali. I due modelli di base sono la gerarchia con CA principale e il trust di rete, sebbene sia possibile unire elementi di entrambi i modelli in un unico modello di trust misto. Per ulteriori informazioni su questi modelli, vedere: <http://technet.microsoft.com/en-us/library/cc773138.aspx> (in inglese).
  
In questa guida viene utilizzato il modello relativo alla gerarchia con CA principale, per i seguenti motivi:
  
-   È possibile adottare un maggiore livello di protezione per le autorità di certificazione non in linea rispetto alle autorità in linea. La creazione di uno o più livelli di CA non in linea consente di aumentare il livello globale di trust per i certificati rilasciati.
  
-   Le gerarchie con CA principale possono essere utilizzate senza una directory, consentendo pertanto il supporto di client esterni che non hanno accesso alla directory interna.
  
-   Poiché sono disponibili pochi ancoraggi di trust da mantenere e distribuire ai client, agli utenti è necessario distribuire solo il certificato CA principale.
  
-   Anche con una gerarchia con CA principale, è sempre possibile includere più ancoraggi (o radici) di trust in futuro grazie alla certificazione incrociata con altre gerarchie. La progettazione consente pertanto di eseguire diverse operazioni, quali fusioni di organizzazioni, affidando il controllo di certificati per fini specifici ai reparti e così via.
  
Per la soluzione proposta è sufficiente una singola CA principale.
  
##### Confronto tra CA principale di terze parti e interna
  
È possibile utilizzare una CA principale interna come ancoraggio di trust per l'infrastruttura PKI oppure i servizi di una CA commerciale. L'utilizzo di un certificato principale di terze parti implica che le CA di emissione vengono certificate dalla CA principale commerciale (di solito mediante una o più CA intermedie). Pertanto, tutti i certificati rilasciati dispongono in ultima analisi di ancoraggi di trust presso questa CA principale esterna.
  
**Nota:** è possibile affidare tutti i requisiti di certificazione dell'organizzazione a una CA commerciale, utilizzando un servizio di gestione in sede oppure ottenendo i certificati direttamente dall'autorità di certificazione. Generalmente non si tratta di una procedura economicamente vantaggiosa tranne che per le piccole organizzazioni o solo per alcuni utilizzi limitati dei certificati.
  
Se si utilizza un CA principale commerciale per i certificati rilasciati internamente, si ottiene una serie di vantaggi:
  
-   Alle parti esterne (ad esempio, i clienti che visitano il sito Web protetto o un'organizzazione partner che riceve un messaggio di posta elettronica firmato) viene garantita un'elevata affidabilità durante l'esecuzione di transazioni protette con l'organizzazione. Considerando pertanto attendibile la CA principale di terze parti, non sarà necessario verificare anche l'affidabilità dei certificati.
  
-   L'organizzazione può avvalersi della competenza di un provider di servizi qualificato, che comprende anche la conoscenza degli aspetti tecnici, legali e aziendali associati all'uso del certificato. Tuttavia, a meno che tutti certificati vengano rilasciati dall'autorità di certificazione, l'utente sarà comunque responsabile delle modalità di rilascio e utilizzo dei certificati, che sarà necessario documentare nella dichiarazione CPS.
  
Un simile approccio presenta tuttavia anche numerosi svantaggi:
  
-   Generalmente comporta costi elevati per ogni certificato.
  
-   L'autorità di certificazione può richiedere rigide misure di controllo e sicurezza per tutte le CA subordinate della CA principale commerciale.
  
-   Gli utenti e le periferiche interne devono avere accesso agli elenchi CRL delle autorità di certificazione di terze parti pubblicati su Internet.
  
-   Per alcune applicazioni può rendersi necessaria la disponibilità di estensioni o parametri specifici per i certificati CA principali e intermedi (ad esempio, accesso con smart card a Windows), non sempre disponibili presso l'autorità di certificazione.
  
-   L'accordo commerciale tra l'organizzazione e l'autorità di certificazione può limitare i tipi di certificati che è possibile rilasciare dalle CA subordinate, ad esempio i certificati server Web.
  
-   L'attendibilità di una CA principale commerciale potrebbe essere un ambito troppo vasto rispetto alle esigenze di protezione dell'organizzazione. Può rendersi necessario introdurre controlli specifici o un ulteriore livello di CA interne per distinguere i certificati rilasciati dall'organizzazione e quelli rilasciati da un'altra organizzazione, entrambe subordinate alla stessa CA principale.
  
Nonostante questi svantaggi, se si necessita di rilasciare un numero significativo di certificati che devono essere considerati attendibili da utenti esterni all'organizzazione, è consigliabile subordinare almeno una parte dell'infrastruttura PKI a una CA principale commerciale, anche se questo può comportare la creazione di due gerarchie separate.
  
In merito a questa guida, per la maggior parte dei certificati utilizzati all'interno dell'organizzazione viene utilizzata una gerarchia basata su una CA principale interna. I vantaggi che ne derivano sono i seguenti:
  
-   L'organizzazione mantiene il controllo diretto sull'ancoraggio di trust centrale, ovvero la CA principale, e sui criteri di protezione che controllano il rilascio e l'utilizzo dei certificati emessi.
  
-   È possibile rilasciare una grande quantità di certificati mediante l'infrastruttura PKI interna a costi relativamente ridotti.
  
-   Non esistono limitazioni sui tipi di certificati da rilasciare.
  
-   Non esiste alcuna ambiguità tra l'affidabilità dei certificati interni ed esterni.
  
-   È possibile pubblicare le informazioni sui controlli CRL e su AIA (Accesso alle informazioni dell'autorità, Authority Information Access) sia internamente che esternamente.
  
In questa guida si consiglia l'uso dei certificati di terze parti solo per i motivi che seguono, nel caso in cui non sia possibile controllare facilmente le radici attendibili degli utenti coinvolti:
  
-   Server Web Internet
  
-   Firma codice commerciale
  
-   Firma documento commerciale
  
##### Definizione di trust dei certificati esterni
  
Nella sezione precedente è stata presa in considerazione l'affidabilità dell'infrastruttura di certificazione di altre organizzazioni. Tuttavia, per stabilire il grado di affidabilità dei certificati all'interno dell'organizzazione, è necessario tenere in considerazione anche altri aspetti. In questo contesto, il termine "trust" o "attendibile" assume tre significati specifici:
  
-   La persona o l'entità che si ritiene attendibile.
  
-   Le operazioni o le attività per cui si ritiene attendibile una parte.
  
-   Il periodo di tempo per il quale si desidera mantenere tale affidabilità.
  
In merito ai certificati, il "soggetto" è l'autorità CA principale di emissione mentre "l'oggetto" sono gli utilizzi e le altre caratteristiche dei certificati che si desidera controllare. Il periodo di tempo invece consiste nel periodo di validità del certificato CA principale o, in alcuni casi, nel periodo di validità di un certificato specifico di trust incrociato da creare.
  
È possibile che sia necessario cambiare le relazioni di trust predefinite dell'organizzazione con parti esterne quando si stabilisce una nuova relazione commerciale con un'altra organizzazione o quando si desidera attivare alcune funzioni per gli utenti (ad esempio, considerare attendibili i certificati Web per consentire sessioni HTTP protette). È possibile eseguire alcune delle seguenti operazioni:
  
-   Distribuire il certificato CA di un'organizzazione partner (o di una nuova autorità di certificazione commerciale) affinché alcuni o tutti gli utenti possano considerare affidabili i certificati CA commerciali o dei partner.
  
-   Distribuire il certificato CA di un'autorità CA o un'infrastruttura PKI con uno scopo speciale all'interno dell'organizzazione dove non si desidera stabilire una relazione di trust.
  
-   Sostituire le radici commerciali "baked-in" (predefinite come attendibili) nelle radici dei client affinché sia possibile limitare gli utilizzi per i quali si ritengono affidabili i certificati emessi da tali radici. È possibile ad esempio decidere di considerare affidabili una determinata CA principale commerciale di posta elettronica e i certificati di server Web protetti, ma non i certificati di accesso con smart card.
  
Per raggiungere questi obiettivi, è possibile eseguire diverse operazioni:
  
-   Creare relazioni di subordinazione qualificata tra la CA principale interna e il certificato CA da considerare attendibili (operazione denominata anche certificazione incrociata). In questo caso, una delle CA interne deve firmare nuovamente il certificato CA esterno. Questa operazione consente essenzialmente di aggiungere la CA esterna all'infrastruttura PKI interna come subordinata affidabile della CA che appone la firma. È possibile inoltre porre delle restrizioni sul tipo di certificato, limitando con precisione gli utilizzi e i criteri dei certificati, i tipi dei nomi di soggetto o i criteri di rilascio da ritenere affidabili.
  
-   Creare un elenco dei certificati attendibili (CTL, Certificate Trust List). In questo modo viene definito un elenco delle CA principali attendibili e vengono specificati gli scopi per cui tali CA vengono considerate attendibili (ad esempio, posta elettronica protetta). Gli elenchi CTL vengono quindi distribuiti mediante gli oggetti Criteri di gruppo di Active Directory. Nonostante questo metodo sia vantaggioso, è di proprietà di Microsoft e quindi può essere utilizzato solo con Windows 2000 o client successivi. Questa opzione riguarda solo i client del dominio in cui viene applicato l'oggetto Criteri di gruppo.
  
-   Installare il certificato CA principale nell'archivio delle Autorità di certificazione attendibili di Active Directory incluso nel contenitore della configurazione. Nella CA principale e in tutte le CA subordinate viene quindi creato un trust non condizionale per tutti gli utenti e i dispositivi dell'insieme di strutture. In ogni caso si consiglia di prestare particolare attenzione prima di concedere questo tipo di trust e di utilizzarlo solo per le autorità CA sotto il controllo dell'organizzazione.
  
-   Distribuire un certificato CA principale affidabile a un sottoinsieme di utenti o computer mediante l'oggetto Criteri di gruppo. Si tratta di un'opzione simile alla precedente, che inoltre consente di specificare chi riceverà i certificati principali affidabili, ovvero gli utenti o i computer dell'oggetto Criteri di gruppo. Questa opzione riguarda solo gli utenti del dominio in cui viene applicato l'oggetto Criteri di gruppo.
  
-   Utilizzare il servizio di aggiornamento Microsoft Root Update, che consente alle Autorità di certificazione commerciali di distribuire con facilità nuovi certificati principali a numerosi utenti. Si consiglia di rimuovere questo servizio se si intende regolare le autorità CA principali affidabili.
  
-   Utilizzare l'oggetto Criteri di gruppo per disattivare i certificati principali affidabili di terze parti. A differenza di altri elementi dell'elenco, in questo modo l'affidabilità viene limitata piuttosto che aumentata. In tutti i computer dotati di Windows, e per i rispettivi utenti, è disponibile un insieme di certificati principali "baked in" (predefiniti come attendibili) che vengono installati per impostazione predefinita. Si tratta di una funzione comune anche in altri sistemi operativi e browser Web inclusi in diverse piattaforme. È possibile utilizzare l'oggetto Criteri di gruppo per disattivare le relazioni di trust automatiche per questi certificati principali. È quindi possibile utilizzare uno dei meccanismi descritti precedentemente per aggiungere nuovamente e in maniera selettiva i certificati affidabili necessari, con o senza limitazioni, a seconda delle esigenze di protezione.
  
    **Nota:** alcuni tipi di certificati principali non possono essere disattivati, in quanto vengono utilizzati dal sistema operativo per aspetti specifichi, quali il criterio della firma del driver. Poiché tali certificati sono necessari, non vengono disattivati dall'impostazione dell'oggetto Criteri di gruppo sopra citata.
  
In questa guida è disattivato il servizio Aggiorna certificati principali per le autorità CA. Si consiglia di verificare se utilizzare tale servizio in altri computer dell'organizzazione. È inoltre necessario verificare se disattivare i certificati principali di terze parti predefiniti per tutti gli utenti del dominio utilizzando l'oggetto Criteri di gruppo. Il certificato CA principale viene distribuito ai client importandolo nel contenitore dell'Autorità di certificazione attendibile.
  
##### Distribuzione dei certificati CA principali
  
I certificati CA principali vengono distribuiti automaticamente ai membri dell'insieme di strutture di Active Directory. Importando il certificato CA nel contenitore dell'Autorità di certificazione, i membri (computer e utenti) di tutti i domini dell'insieme di strutture installeranno tale certificato negli archivi locali delle CA principali affidabili. Si consiglia di utilizzare questo metodo per tutte le CA principali interne che necessitano di un ambito di trust esteso a tutto l'insieme di strutture.
  
Inoltre sarà necessario distribuire CA principali con un ambito di trust limitato oltre alle CA principali interne. Per ulteriori informazioni, vedere la sezione "[Estensione dell'infrastruttura CA"](#a1).
  
Per distribuire il certificato CA principale a utenti e computer su altre piattaforme o all'esterno dell'insieme di strutture, è necessario installare manualmente il certificato oppure utilizzare un altro metodo di distribuzione.
  
#### Definizione dei ruoli dell'Autorità di certificazione
  
Una volta definito il modello di trust e selezionata la strategia per le CA principali, è possibile pianificare l'infrastruttura CA restante. È quindi necessario definire i diversi ruoli da attribuire alle CA all'interno dell'organizzazione. È possibile configurare le Autorità di certificazione come CA principali o subordinate. Le CA subordinate possono, a loro volta, diventare CA di emissione o intermedie, in quanto rappresentano fasi di trust intermedie tra le CA emittenti e quelle principali.
  
##### CA principale
  
L'Autorità di certificazione principale riveste un ruolo fondamentale all'interno dell'organizzazione. Innanzitutto viene considerata esplicitamente affidabile da tutti gli utenti e dispositivi all'interno dell'organizzazione. Numerose decisioni in merito alla protezione (ad esempio, se consentire l'accesso a un utente, se considerare affidabile un messaggio di posta elettronica, se autorizzare una negoziazione di titoli pari a 10 milioni di euro) dipendono in ultima analisi dal grado di protezione della CA principale e dalla chiave privata che ne fornisce l'identità. Considerato che numerose operazioni dipendono dalla CA principale, la modifica di una chiave e di un certificato principali può rivelarsi un'operazione molto complessa che può provocare errori, nonché portare a saltuarie interruzioni del servizio di applicazioni e utenti per un periodo prolungato.
  
Per questo motivo, si consiglia di proteggere la chiave privata della CA principale nel modo più ampio possibile. A questo scopo, una delle procedure ottimali consiste nel scollegare la CA dalla rete per garantire un accesso piuttosto limitato; quindi diventa indispensabile adottare misure equivalenti per limitare l'accesso fisico al server. Come ulteriore misura di protezione delle chiavi della CA, si consiglia di utilizzare una periferica HSM (Hardware Security Module) dedicata, che consente di fornire una protezione aggiuntiva della chiave per le CA non in linea, oltre che aumentare in maniera significativa la protezione delle CA in linea.
  
In questa guida viene utilizzata una CA principale non in linea.
  
Per migliorare la protezione delle chiavi CA si consiglia di utilizzare una periferica HSM per la CA principale. Tali periferiche possono essere aggiunte anche dopo l'installazione della CA; in questo caso però sarà necessario rinnovare la CA con una nuova chiave anche se numerosi fornitori consentono di importare la chiave esistente.
  
##### CA di emissione e intermedie
  
Se l'Autorità di certificazione principale non è in linea, risulta praticamente impossibile rilasciare certificati quotidianamente. Per creare CA da utilizzare per il rilascio quotidiano di certificati, la CA principale certifica le CA subordinate a emettere certificati per suo conto. In questo modo la CA subordinata eredita l'attendibilità della CA principale, evitando eventuali rischi di protezione alla chiave della CA principale.
  
È possibile eseguire questa procedura anche in un secondo momento. Anziché rilasciare certificati direttamente, la CA subordinata consente di certificare un ulteriore livello di CA per l'emissione a entità finali (utenti e computer). In questo modo, oltre a fornire un livello di protezione aggiuntivo alla chiave della CA principale, è possibile ripartire i rischi tra le diverse CA subordinate. Una CA intermedia ad esempio può certificare CA di emissione interne, mentre un'altra CA intermedia può autorizzare CA a rilasciare certificati esterni. Ne derivano numerosi vantaggi:
  
-   Il rischio di manomissioni delle CA viene limitato a una parte ridotta dell'intera gerarchia PKI.
  
-   È possibile implementare criteri di certificati separati per tutti i settori della gerarchia CA.
  
-   Grazie alla riduzione del numero di volte che viene utilizzata la chiave CA principale, diminuiscono anche i rischi di violazione della chiave.
  
Nonostante ulteriori livelli di CA intermedie consentano di aumentare la sicurezza globale dell'infrastruttura PKI, ne derivano anche una complessità e un carico di gestione maggiori, in misura decisamente superiore rispetto ai costi delle licenze hardware o software. Per molte applicazioni pertanto i requisiti di protezione non sono sufficienti a giustificare una gerarchia a tre livelli, in particolare se le chiavi della CA sono protette mediante periferiche HSM.
  
In questa guida viene proposta una gerarchia a due livelli, in cui è possibile raggiungere un equilibrio accettabile tra livello di sicurezza ed economicità (in termini di carico di gestione) per soddisfare i requisiti immediati delle applicazioni, mantenendo al contempo la flessibilità per un'eventuale integrazione di applicazioni dei certificati in futuro, come delineato nella sezione "Definizione dei requisiti dei certificati".
  
**Nota:** è possibile che vi siano dei requisiti normativi in cui viene richiesto di utilizzare obbligatoriamente gerarchie a tre livelli, ma questo aspetto non rientra nell'ambito del documento.
  
##### Gerarchia CA proposta
  
Nella figura seguente è illustrata la gerarchia proposta, che riguarda l'implementazione della CA principale e di una CA di emissione. La CA di emissione rilascerà inizialmente certificati (tecnici) di valore basso per computer o utenti e certificati di valore alto per computer, quest'ultimi contrassegnati con il simbolo a forma di lucchetto.
  
![](images/Dd536257.SGFG17001(it-it,TechNet.10).jpg)
  
Figura 1  
*Gerarchia dell'Autorità di certificazione*
  
Questo processo consente di distribuire un'infrastruttura PKI completamente funzionale, in grado di supportare l'autenticazione della rete LAN senza fili protetta (802.1X) con un esborso relativamente ridotto per hardware e software, oltre che un carico di gestione decisamente basso.
  
**Nota:** è possibile estendere in diversi modi la progettazione di questa infrastruttura semplificata per soddisfare requisiti differenti. Questo aspetto viene illustrato nella sezione "Estensione dell'infrastruttura CA".
  
La CA di emissione viene inizialmente configurata per il rilascio dei seguenti tipi di certificati (inclusi in riquadri in grassetto nella figura precedente):
  
-   Autenticazione client - Utente
  
-   Autenticazione client - Computer
  
-   Autenticazione server IAS
  
I primi due elementi sono certificati con garanzia bassa e vengono rilasciati automaticamente in base alle credenziali di dominio dell'utente o del computer. Il possesso di questi certificati indica una relazione non più stretta con il soggetto di quanto non lo sia il possesso di un nome utente e di una password di dominio validi. Questo non significa tuttavia che l'utilizzo di certificati al posto di nomi e password di dominio, non presenti vantaggi tecnici e in merito alla protezione.
  
L'autenticazione del server IAS è classificata come un certificato con garanzia media, in quanto i server IAS forniscono una funzione di protezione elevata. L'emissione di questo tipo di certificato include generalmente controlli aggiuntivi in merito alla validità della richiesta, oltre a richiedere l'approvazione del Certificate Manager.
  
**Nota:** poiché nella Guida all'implementazione per la creazione di questo tipo di certificato non è stata attivata l'impostazione relativa all'approvazione del membro del gruppo Certificate Manager, nei server IAS è possibile rinnovare automaticamente i certificati scaduti evitando pertanto la disattivazione del servizio. Dopo aver eseguito i processi per esaminare attentamente e approvare la richiesta di certificato, si consiglia tuttavia di attivare il requisito relativo all'approvazione del Certificate Manager.
  
##### Requisiti hardware e software per le CA
  
In questa sezione vengono illustrati i requisiti hardware e software per le Autorità di certificazione.
  
**CA principale**
  
La CA principale necessita di minimi requisiti hardware e le prestazioni richieste sono simili all'utilizzo di un sistema operativo. Gli aspetti critici relativi a una CA principale invece riguardano l'affidabilità e la facilità di gestione a lungo termine. Si tratta di un sistema generalmente destinato a essere utilizzato a lungo e che rimane spento per lunghi periodi. Quando *è* in funzione, si richiede comunque che sia affidabile e che consenta di sostituire i componenti con facilità, possibilmente anche molti anni dopo che è stata interrotta la produzione del modello.
  
Tenendo presente questi aspetti, è necessario:
  
-   Scegliere un produttore noto in grado di offrire un adeguato servizio di supporto e manutenzione hardware a lungo termine. Si consiglia di richiedere al fornitore per quanti anni saranno disponibili i componenti di ricambio.
  
-   Utilizzare server piuttosto che workstation o computer portatili, in quanto i primi hanno una struttura maggiormente standardizzata e sono soggetti a minori modifiche.
  
-   Considerare la presenza di un sistema di riserva "disattivo" per gestire il ruolo della CA principale, in caso di guasti hardware che non è possibile riparare in tempi ragionevoli.
  
Si consiglia di considerare anche l'utilizzo di una periferica HSM per garantire un'ulteriore protezione.
  
Poiché la CA principale non necessita delle funzionalità aggiuntive incluse in Windows Server 2003 Enterprise Edition, viene utilizzata la versione Standard Edition.
  
**CA di emissione**
  
Nonostante per le CA di emissione si debbano rispettare determinati requisiti di prestazioni, questi sono alquanto ridotti visto che le attività di tale CA sono decisamente limitate. Persino durante la valutazione delle prestazioni con carichi eccessivi per una CA globale, il collo di bottiglia è generalmente causato dall'interazione con Active Directory, non dalla CA stessa. I requisiti di prestazione hardware sono pertanto minimi. Come per la CA principale, i fattori critici sono rappresentati dall'affidabilità e dalla facilità di gestione nella scelta dell'hardware.
  
Poiché in Servizi certificati viene utilizzata la stessa architettura di database di Active Directory, è possibile applicare molte linee guida identiche relative alle prestazioni. Come regola di base, in molte organizzazioni vengono adottate le stesse specifiche hardware utilizzate nei controller di dominio di Active Directory.
  
Per ulteriori informazioni sulle prestazioni delle CA, vedere la sezione "CA Capacity, Performance, and Scalability" nel modulo "Designing a Public Key Infrastructure" del Resource Kit.
  
Nel modulo "Implementazione dell'infrastruttura a chiave pubblica" della *Guida all'implementazione* è disponibile un profilo hardware. Oltre alle linee guida precedenti relative alla CA principale, è necessario tenere presente quanto riportato di seguito per la scelta dell'hardware del server per la CA di emissione:
  
-   Utilizzare schede di rete (NIC, Network Interface Card) ridondanti con il raggruppamento NIC.
  
-   Utilizzare almeno due volumi RAID 1 per archiviare i registri CA in un'unità di archiviazione fisica separata. Questa procedura consente di ottenere vantaggi in termini di prestazioni oltre a una maggiore capacità di recupero in caso di errori hardware.
  
-   Utilizzare tre volumi RAID 1 (invece che due) per l'archiviazione del sistema operativo, del database e dei registri di Servizi certificati per ottenere prestazioni ottimali.
  
-   Utilizzare unità e controller SCSI (Small Computer System Interface) ad alte prestazioni rispetto agli equivalenti IDE (Integrated Device Electronics) per ottenere migliori prestazioni e capacità di recupero. Le prestazioni del sottosistema dei dischi rappresentano il fattore fondamentale nel determinare le prestazioni CA globali.
  
-   Utilizzare una periferica HSM per aumentare il livello di protezione e le prestazioni delle operazioni di firma durante l'emissione di certificati.
  
A differenza della CA principale, per la CA di emissione *sono necessarie* le funzionalità aggiuntive di Windows Server 2003 Enterprise Edition.
  
**Utilizzo di più CA di emissione per la capacità di recupero del servizio**
  
In questa sezione vengono descritte le ragioni tecniche per cui si desidera installare più CA di emissione. L'utilizzo di diverse CA di emissione, per la registrazione di tipi di certificati differenti, può essere dovuto anche a ragioni di sicurezza e relative ai criteri. Questo aspetto verrà analizzato in una sezione successiva.
  
Poiché una singola CA di emissione con requisiti hardware limitati è sufficiente a soddisfare i requisiti di emissione dei tipi di certificati descritti precedentemente per un numero elevato di client, non è necessario disporre di più CA di emissione esclusivamente per migliorare le prestazioni. Si consiglia tuttavia di verificare, in base ai requisiti di disponibilità per le CA di emissione, se sia necessario distribuire più CA per registrare gli stessi tipi di certificati.
  
Una CA non presenta lo stesso tipo di problemi di disponibilità rispetto a numerosi servizi. Non è necessario infatti che i client contattino la CA per utilizzare o verificare un certificato. Un contatto diretto con un'Autorità di certificazione viene richiesto solo nei seguenti casi:
  
-   Registrazione di un nuovo certificato.
  
-   Rinnovo di un certificato.
  
-   Revoca di un certificato.
  
-   Pubblicazione di un nuovo CRL.
  
-   Rinnovo dello certificato CA.
  
**Nota:** in questo elenco non sono incluse le attività di gestione quotidiane, quali backup e monitoraggio, in quanto non comportano generalmente un'interazione con la CA, bensì si tratta di misure che consentono di mantenere la CA contattabile.
  
I requisiti di disponibilità per i servizi vengono illustrati in dettaglio nella seguente tabella.
  
**Tabella 8. Requisiti di disponibilità dei servizi CA**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Servizio CA</th>
<th>Requisiti di disponibilità</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Servizi di registrazione — Nuovo certificato</td>
<td style="border:1px solid black;">Si tratta di un aspetto significativo in quanto consente di impedire l'accesso di nuovi utenti alla rete o ad altri servizi che richiedono un certificato. È necessario valutare se il tempo necessario per il ripristino della CA dal backup è superiore al tempo che l'organizzazione può attendere per la registrazione di un certificato da parte di un nuovo utente. Se questo è il caso, è necessario disporre di più CA di emissione per i tipi di certificati in questione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Servizi di registrazione — Rinnovo certificato</td>
<td style="border:1px solid black;">Se viene utilizzata la funzione di rinnovo automatico con il tipo di certificato in questione, per impostazione predefinita questa operazione si verifica sei settimane prima della scadenza del certificato precedente. Mentre per quanto riguarda il tempo di ripristino dal backup per una CA viene generalmente misurato in ore. I certificati rinnovati manualmente vengono invece rinnovati dal proprietario. È possibile istituire un sistema di avviso automatico che avverte il proprietario quando i certificati critici necessitano di venire rinnovati.<br />
Altrimenti, i criteri di disponibilità sono gli stessi richiesti per la registrazione di un nuovo certificato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Revoca di un certificato</td>
<td style="border:1px solid black;">Normalmente un certificato può essere revocato solo dalla CA che lo ha emesso, pertanto una seconda CA non è necessaria.<br />
Se la revoca deve essere eseguita in tempi brevi, ovvero prima che la CA venga revocata, è possibile inserire voci di revoca negli elenchi CRL correnti, se si dispone del numero di serie del certificato da revocare e della chiave privata della CA (ripristinato in un computer differente).<br />
Si tenga presente che la latenza degli elenchi CRL è generalmente di uno o più giorni, pertanto a meno che il tempo di ripristino della CA sia superiore all'intervallo relativo alla successiva pubblicazione CRL, l'aggiornamento manuale del CRL non comporta grandi vantaggi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pubblicazione di un elenco CRL</td>
<td style="border:1px solid black;">In una CA è disponibile un elenco CRL univoco, pertanto una seconda CA non consentirebbe di aumentare la capacità di recupero della pubblicazione CRL, bensì solamente di ridurre l'impatto in caso di errori (meno del 100 percento dei certificati emessi dipende dall'elenco CRL non riuscito).<br />
L'accesso allo stato di revoca corrente è fondamentale in molte applicazioni dei certificati. Questo significa che presso i punti di distribuzione CRL pubblicati deve essere disponibile un elenco CRL non scaduto. In caso contrario, non sarà possibile utilizzare le applicazioni dei certificati sensibili alla revoca.<br />
Il periodo di recupero della CA non può essere superiore al periodo di sovrapposizione tra la scadenza del CRL precedente e l'emissione del nuovo CRL. In simili casi, è possibile firmare nuovamente un elenco CRL e quindi estenderne il periodo di validità.<br />
Questa procedura viene descritta nella <em>Guida operativa</em>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Rinnovo del certificato CA</td>
<td style="border:1px solid black;">Non è necessaria una seconda CA di emissione.<br />
Questa operazione deve essere eseguita tempestivamente per evitare problemi relativi al periodo di recupero di una CA. In caso contrario, è possibile firmare nuovamente il certificato CA mediante la chiave CA principale, prolungando il periodo di validità.</td>
</tr>
</tbody>
</table>
 

**Nota:** nella tabella precedente, è necessario valutare il tempo di recupero e la disponibilità della CA nel caso si verifichino problemi che vanno a influire sulla capacità della CA di fornire il servizio agli utenti finali. Tali problemi non si limitano a un malfunzionamento del server, bensì possono riguardare anche un'interruzione a livello di rete tra i siti. È pertanto necessario tenere presente tutti i fattori che possono influire sulla fornitura del servizio agli utenti quando si stabilisce il livello di disponibilità del servizio.

Se si gestisce correttamente il backup e il recupero delle CA, la scelta di utilizzare più CA per fornire la capacità di recupero del servizio è determinata esclusivamente dai requisiti di registrazione e di rinnovo. È necessario quindi confrontare il costo sostenuto per la mancanza di tali servizi con i costi di installazione e gestione necessari per la fornitura di CA aggiuntive.

Duplicando le CA di emissione, oltre a ottenere una maggiore disponibilità, è possibile aumentare le prestazioni, dimezzando la dimensione degli elenchi CRL, ma raddoppiandone il numero. Tali fattori non sono comunque determinanti in questo caso.

In questa guida, i problemi legati alla capacità di recupero vengono affrontati mediante un'attenta gestione delle CA, incluse procedure adeguate di backup e ripristino. È pertanto necessaria una singola CA di emissione.

##### Protezione della chiave della CA con periferiche HSM

Per migliorare significativamente la protezione della presente infrastruttura di base è possibile utilizzare periferiche HSM che consentono di proteggere le chiavi private di tutte le CA. Sebbene abbiano un costo piuttosto elevato, fino a superare il costo di un server CA, tali periferiche offrono un significativo livello di protezione. Questo significa che in numerose operazioni chiave che non sono protette da chiavi software (ad esempio l'esportazione e il back up delle chiavi), l'accesso è consentito solo agli utenti autorizzati.

##### Protezione delle CA

In questa sezione viene descritta la protezione delle CA, inclusa la protezione fisica e del sistema operativo, i controlli e il monitoraggio della protezione, nonché l'utilizzo di ruoli per delegare le responsabilità di gestione attraverso la CA.

**Protezione del sistema operativo**

La protezione della CA avviene mediante i criteri di protezione di Windows, le cui impostazioni si basano sul ruolo del server CA descritto nella *Windows Server 2003 Security Guide*.

Per ulteriori informazioni sulle impostazioni utilizzate per questo ruolo, leggere le sezioni pertinenti incluse in questa guida. Per informazioni dettagliate su come ottenere la presente guida, leggere la sezione "Ulteriori informazioni" nella parte finale di questo modulo.

Le impostazioni di protezione relative alla CA principale vengono applicate direttamente utilizzando i modelli di protezione, mentre le impostazioni della CA di emissione vengono applicate mediante i criteri di gruppo.

**Protezione fisica**

La protezione fisica dei server CA è un aspetto fondamentale. Se non è possibile controllare l'accesso fisico di base ai server, non sarà efficace alcun livello di protezione della rete o del sistema operativo.

La CA principale deve trovarsi in posizioni in cui l'accesso al server è controllato rigorosamente. L'accesso alla CA è raramente necessario (due o tre volte all'anno) e inoltre non è nemmeno indispensabile accendere il server. Per questo motivo è possibile sistemare il server in una postazione sicura che non è dotata delle funzionalità standard richieste per i sistemi informatici. Non è necessario ad esempio disporre di sistemi di rete, infrastrutture avanzate per server o sistemi di gestione alimentazione e temperatura.

Anche la CA di emissione deve trovarsi in una posizione in cui l'accesso fisico è controllato rigorosamente. In questo caso, la protezione fisica assume un'importanza rilevante in quanto esistono numerosi modi per violare la protezione di un sistema informatico, una volta che un pirata informatico può accedere fisicamente al sistema (simili attacchi possono riguardare anche la rete). Tale server deve rimanere sempre in linea e quindi deve essere situato in una postazione dotata di strutture standard per computer (controllo della temperatura, gestione dell'alimentazione, sistemi di ventilazione, antincendio e così via).

Se possibile, la postazione di entrambi i server deve essere il più possibile protetta da rischi esterni che potrebbero danneggiare le apparecchiature, ad esempio incendi, inondazioni e così via.

Un altro aspetto altrettanto importante consiste nel controllare l'accesso fisico e nel garantire la sicurezza fisica di backup, materiale rilevante e altri dati di configurazione. Tali informazioni devono venire memorizzate in una posizione differente rispetto ai server per consentire il recupero delle CA, nel caso in cui l'intero sito diventi inutilizzabile, a causa, ad esempio, di calamità naturali o di incendio.

**Gestione della protezione delle CA**

L'infrastruttura dei certificati è potenzialmente una risorsa di alto valore, che dipende essenzialmente dal modo in cui vengono creati i certificati all'interno dell'organizzazione, non solo nel presente ma anche in futuro. Per questo motivo è necessario installare, configurare e gestire le CA adottando delle misure di verifica e protezione più rigorose rispetto a quelle utilizzate per installare altre infrastrutture IT. Tali misure devono essere almeno equivalenti a quelle utilizzate per un controller di dominio o addirittura superiori.

La garanzia offerta da una CA dipende dall'alto livello di affidabilità, che deve essere impostato e gestito in maniera protetta. Se non si è in grado di garantire che la chiave privata della CA non sia stata copiata clandestinamente, non si potrà mai avere la certezza che un certificato presumibilmente rilasciato da una CA non sia stato contraffatto.

Poiché non è facile aumentare il livello di garanzia o affidabilità in un secondo momento, è necessario creare sin dall'inizio un elevato livello di affidabilità per la gestione della CA. Per migliorare l'affidabilità di un'organizzazione, è possibile ad esempio aumentare la certezza che la chiave privata della CA non sia stata rubata adottando itinerari di controllo o altre prove, in grado di garantire che gli accessi alla CA sono stati controllati accuratamente da un altro utente oppure, nel caso di una CA non in linea, che non è stata mai connessa in rete e così via.

La necessità di avere un livello di garanzia molto elevato diventa un aspetto particolarmente importante, nel caso in cui l'organizzazione si trovi a far fronte a una controversia legale in merito alla validità di un certificato che ha emesso. In casi simili, se si dispone di prove che documentano che le CA non potevano essere violate, vi sono maggiori probabilità di concludere con successo la controversia. L'analisi dettagliata di tale problema esula dagli argomenti trattati in questa guida, pertanto si consiglia di consultare revisori e consulenti legali per ulteriori informazioni.

Di seguito vengono riportati alcuni esempi sui tipi di procedure che è possibile adottare per migliorare in maniera significativa il livello di garanzia delle CA.

-   Assicurare la protezione fisica della CA per impedire l'accesso da parte di persone non autorizzate all'hardware o al supporto di backup della CA.

-   Eseguire tutte le procedure di installazione e configurazione in presenza di un testimone: registrare le principali procedure di installazione e richiedere la controfirma del testimone per confermarne la corretta esecuzione. In alternativa, è possibile filmare l'installazione e affidare una copia del filmato a una terza parte.

-   Eseguire tutte le operazioni di revoca ed emissione dei certificati mediante la CA principale in condizioni simili. Idealmente, tutti gli accessi alla CA principale dovrebbero essere controllati da un testimone.

-   Verificare che tutti gli utenti dotati di accesso amministrativo alle CA, dispongano anche di account individuali rintracciabili in modo univoco. Controllare tutte le operazioni relative alla CA.

-   Prendere in considerazione l'attivazione della separazione dei ruoli della CA.

Simili misure sono particolarmente importanti per il server CA principale, mentre la CA di emissione può avere un livello di garanzia inferiore a seconda dei tipi di certificati che si desidera rilasciare. Se ad esempio i certificati che vengono rilasciati hanno un valore relativamente basso (ad esempio l'autenticazione di rete utente e computer), la CA non necessita di un livello di protezione superiore a quello di un controller di dominio.

Se una CA principale ha un livello di garanzia elevato, è possibile aggiungere una CA di emissione con un livello di garanzia superiore per rilasciare certificati di valore superiore in un secondo momento. È possibile mantenere sia CA con garanzia elevata che CA esistenti con garanzia bassa. Se tuttavia la CA principale è installata e configurata in un ambiente con livello di protezione relativamente basso, sarà probabilmente necessario reinstallarla oppure creare una nuova CA principale, se si desidera rilasciare certificati di alto valore in un secondo momento.

**Controllo e monitoraggio della protezione**

Il controllo di Servizi certificati e del sistema operativo viene eseguito in tutte le CA. Per essere efficace, è necessario eseguire il monitoraggio ed esaminare eventuali elementi sospetti. Nel modulo "Gestione dell'infrastruttura a chiave pubblica" della *Guida operativa* viene esaminato il significato delle voci relative agli eventi di controllo di Servizi certificati.

**Ruoli di gestione**

Servizi certificati consente di fornire deleghe estremamente dettagliate dei ruoli amministrativi. Nella presente guida viene utilizzata questa funzione per fornire una maggiore flessibilità per la gestione dell'infrastruttura PKI. Ogni ruolo amministrativo principale definito da Servizi certificati è stato implementato utilizzando un gruppo di protezione del dominio oppure, per le CA non in linea, un gruppo di protezione locale. Inoltre, sono stati definiti altri due ruoli e gruppi di protezione per facilitare la delega dei compiti amministrativi ai componenti dell'infrastruttura PKI di Active Directory.

Si tenga presente che non esiste necessariamente il mapping uno-a-uno tra questi ruoli e i singoli utenti all'interno dell'organizzazione. In molte organizzazioni infatti vengono attribuiti più ruoli alla stessa persona. È possibile implementare facilmente questa opzione aggiungendo l'utente a uno o a tutti i gruppi di protezione elencati nella seguente tabella. Qualora invece l'organizzazione abbia adottato una separazione estremamente dettagliata delle responsabilità amministrative, è necessario utilizzare la funzione di Servizi certificati per implementare i ruoli.

Nella tabella seguente vengono illustrati i ruoli implementati e le rispettive mappature dei gruppi di protezione (dove implementati).

**Tabella 9. Ruoli principali di Servizi certificati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome del ruolo</th>
<th>Gruppo di protezione</th>
<th>Ambito</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Enterprise PKI Administrator</td>
<td style="border:1px solid black;">Enterprise PKI Admins</td>
<td style="border:1px solid black;">Insieme di strutture di Active Directory</td>
<td style="border:1px solid black;">Responsabile di tutta l'infrastruttura PKI: definisce tipi di certificati, criteri delle applicazioni, percorsi di trust e così via per l'azienda.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Enterprise PKI Publisher</td>
<td style="border:1px solid black;">Enterprise PKI Publishers</td>
<td style="border:1px solid black;">Insieme di strutture di Active Directory</td>
<td style="border:1px solid black;">Responsabile della pubblicazione di certificati affidabili principali, certificati CA secondari e di elenchi CRL nella directory.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CA Administrator</td>
<td style="border:1px solid black;">CA Admins</td>
<td style="border:1px solid black;">CA</td>
<td style="border:1px solid black;">Responsabile di configurazione a livello di server (ad esempio, installazione CA). Di solito coincide con gli amministratori PKI dell'organizzazione e con il ruolo amministratore.<br />
È possibile assegnare più amministratori CA a CA differenti se ciò è richiesto dall'utilizzo dei certificati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Administrator</td>
<td style="border:1px solid black;">Local Administrators</td>
<td style="border:1px solid black;">CA</td>
<td style="border:1px solid black;">Amministra il server e il sistema operativo CA. È inoltre responsabile del rinnovo del certificato CA. In genere viene condiviso con il ruolo di CA Administrator.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CA Auditor</td>
<td style="border:1px solid black;">CA Auditor</td>
<td style="border:1px solid black;">CA</td>
<td style="border:1px solid black;">Gestisce eventi di controllo, criteri e tutto ciò che riguarda gli eventi CA controllabili.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Certificate Manager</td>
<td style="border:1px solid black;">Certificate Manager</td>
<td style="border:1px solid black;">CA</td>
<td style="border:1px solid black;">Approva le richieste di certificati per cui è richiesta approvazione manuale e revoca certificati.<br />
Possono coesistere più responsabili dei certificati che si occupano dell'approvazione per CA differenti se l'utilizzo dei certificati lo richiede.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autorità di registrazione o responsabile registrazione</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">Profilo del certificato</td>
<td style="border:1px solid black;">È un'estensione del ruolo del responsabile certificati, che si occupa dell'approvazione e della firma di richieste di certificati in seguito a una verifica dell'identificatore (ID) fuori banda. Il ruolo può essere ricoperto da una persona o da un dispositivo di processo IT (ad esempio, scanner di impronte digitali e database).<br />
È possibile specificare autorità di registrazione differenti per profili di certificati diversi (modelli) e interessare più CA.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Key Recovery Agent</td>
<td style="border:1px solid black;">Non definito</td>
<td style="border:1px solid black;">CA</td>
<td style="border:1px solid black;">Detiene le chiavi per la decrittografia di chiavi private, archiviate nel database CA.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CA Backup Operator</td>
<td style="border:1px solid black;">CA Backup Operator</td>
<td style="border:1px solid black;">CA</td>
<td style="border:1px solid black;">Responsabile di backup e ripristino di server CA e di conservare in modo sicuro i supporti di backup.</td>
</tr>
</tbody>
</table>
  
Questi gruppi di protezione vengono implementati come gruppi universali di dominio e vengono applicati alla CA di emissione e alla directory. Per la CA principale, vengono implementati gruppi equivalenti come gruppi locali; in ogni caso non esiste un gruppo equivalente per gli amministratori e per gli autori PKI dell'organizzazione di una CA non in linea. In questa guida si presuppone che vengano utilizzati gli stessi gruppi di protezione per tutte le CA all'interno dell'organizzazione. In caso contrario, è necessario implementare gruppi separati per ogni CA per tutti i ruoli con ambito CA, quindi rinominarli in maniera appropriata, ad CA Admins — CA di emissione 1.
  
Poiché le autorità di registrazione (o responsabili della registrazione), l'archiviazione e il recupero della chiave non sono stati implementati in questa guida, non è stato definito un gruppo di protezione per i ruoli corrispondenti.
  
Infine è possibile imporre la separazione tra i ruoli CA per un'Autorità di certificazione. Se si attiva questa opzione, a tutti gli utenti membri di più gruppi di ruoli viene negato l'accesso ai privilegi di tutti i gruppi di ruolo. Questa funzione non è stata implementata in questa guida.
  
##### Integrazione di Active Directory
  
È possibile installare le CA in una delle due modalità disponibili: globale (enterprise) (o integrata in Active Directory) o autonoma. A differenza della modalità autonoma, le CA globali (enterprise) consentono di utilizzare Active Directory per archiviare le informazioni di configurazione, utilizzare Active Directory come autorità di registrazione e pubblicare automaticamente certificati emessi nella directory. Le CA autonome invece possono pubblicare certificati ed elenchi CRL nella directory, tuttavia fanno affidamento su Active Directory.
  
Per una descrizione dettagliata, vedere la sezione "Ulteriori informazioni" alla fine del modulo.
  
Poiché viene utilizzata in modalità non è in linea, è possibile configurare la CA principale solo come autonoma. Lo stesso vale per le CA intermedie non in linea se si sceglie di distribuirle nel proprio ambiente.
  
La CA di emissione viene configurata come CA globale (enterprise) per i seguenti motivi:
  
-   È necessario eseguire la registrazione e l'approvazione automatiche dei tipi di certificati utilizzati in questa guida.
  
-   In questa guida è necessario utilizzare i modelli dei certificati, che offrono numerosi vantaggi semplificando la gestione di più tipi di certificati (spesso mediante più CA).
  
-   Per il servizio IAS è necessario eseguire il mapping dei certificati affidabili in Active Directory per autenticare i client senza fili. Per consentire questa operazione, è necessario registrare la CA nell'archivio NTAuth.
  
-   È necessaria la pubblicazione automatica dei certificati per i corrispondenti oggetti computer o utente.
  
-   La CA necessita di una fonte affidabile per ottenere le informazioni sul nome del soggetto da utilizzare per le richieste di certificati e per i certificati rilasciati. In Active Directory queste informazioni sono disponibili mediante gli attributi computer e utente archiviati nella directory.
  
-   In futuro potrebbero essere necessari i certificati di accesso con smart card.
  
**Nota:** alcune di queste funzionalità vengono fornite per impostazione predefinita dalla CA globale (enterprise), sebbene possano essere disponibili anche con una CA autonoma correttamente configurata. In ogni caso, questo aspetto esula dagli argomenti trattati in questa guida.
  
**Domini in cui installare le autorità di certificazione**
  
Se nell'organizzazione è disponibile un insieme di strutture a più domini (o persino più insiemi di strutture), è necessario scegliere il dominio in cui installare le CA. Tale scelta può essere influenzata da diversi fattori, quali la necessità di delegare il controllo a diversi responsabili del dominio oppure le normative nazionali o locali relative alla fornitura di Servizi certificati in settori differenti dell'organizzazione.
  
La metodologia adottata più comunemente consiste nell'installazione delle CA nel dominio principale dell'insieme di strutture o in un dominio dedicato a attività di gestione. È necessario installare le CA in un dominio che rimarrà stabile per un lungo periodo di tempo. Dopo l'installazione infatti non è possibile modificare il nome della CA, l'appartenenza del dominio e il nome del dominio DNS (Domain Name System). È necessario inoltre evitare l'installazione delle CA in domini in cui non sia possibile garantire la protezione o l'integrità dell'account computer.
  
In questa guida, gli account del server CA (solo CA di emissione globali) vengono installati nel dominio principale dell'insieme di strutture oppure, nel caso di un insieme di strutture di dominio singolo, nel dominio stesso.
  
##### Mapping delle dichiarazioni sulle procedure di certificazione alle CA
  
Se si intende pubblicare la dichiarazione CPS, è necessario determinare l'ambito della CPS. È possibile creare una CPS per un'intera gerarchia CA o solo per una parte oppure è possibile disporre di una CPS per ogni CA.
  
Quest'ultima opzione, pur offrendo una maggiore flessibilità, aumenta il carico di gestione di più CPS. La procedura standard consiste nel creare una CPS separata per ogni CA o gruppo di CA con in comune criteri di certificazione, tipi di soggetto e livelli di protezione. Se esistono delle differenze significative tra le CA, è necessario utilizzare più CPS. Se si dispone invece di numerose CA identiche distribuite per ragioni di prestazioni o capacità di recupero, esse devono includere anche le stesse CPS.
  
Come si è già rilevato in precedenza, è piuttosto legittimo creare una CPS ma non pubblicarla. È possibile ad esempio evitare la pubblicazione della CPS esternamente se si ritiene che siano incluse informazioni operative e sulla protezione di tipo interno. È possibile inoltre scegliere di pubblicare una versione abbreviata della CPS in cui vengono elencati i criteri operativi importanti della CA, senza rivelare informazioni operative interne.
  
Se si decide di pubblicare la CPS in un modulo accessibile dal certificato CA, è necessario ottenere un identificatore oggetto (OID) dallo spazio dei nomi OID ufficiale, assegnato all'organizzazione in base allo standard ISO (International Standards Organization). La dichiarazione CPS rappresenta già un criterio di certificazione ed essendo univoco per l'organizzazione, è necessario disporre di un OID univoco globale per identificarlo.
  
È piuttosto comune includere anche una notifica utente in formato testo con alcune indicazioni sullo scopo o sull'origine del certificato. Poiché esiste il limite di 200 caratteri, non può essere tuttavia considerata un'alternativa a un documento CPS separato.
  
Una volta ottenuto l'OID della dichiarazione CPS e scelto un URI (Uniform Resource Identifier) in cui pubblicare la CPS, è possibile includere quest'ultima nei certificati CA. Tale procedura viene descritta nel modulo "Implementazione dell'infrastruttura a chiave pubblica" della *Guida all'implementazione*.
  
#### Supporto dell'infrastruttura IT
  
In questa guida, il sistema PKI si basa su altri servizi dell'infrastruttura per un corretto funzionamento. Nella figura seguente sono illustrati i principali servizi.
  
![](images/Dd536257.SGFG17002(it-it,TechNet.10).jpg)
  
Figura 2  
*Interazione della CA con l'infrastruttura IT*
  
Altri aspetti non illustrati nella figura ma comunque fondamentali per il funzionamento di Servizi certificati riguardano il sistema di monitoraggio, avviso e gestione. Tale infrastruttura viene illustrata in dettaglio nel modulo "Gestione dell'infrastruttura a chiave pubblica" della *Guida operativa*.
  
Nelle sezioni che seguono vengono descritti i servizi forniti da Active Directory e IIS.
  
##### Active Directory
  
Come si è già rilevato nella sezione precedente "Integrazione di Active Directory", Active Directory fornisce numerosi servizi fondamentali per l'infrastruttura PKI, tra cui la pubblicazione, la registrazione e il mapping degli account dei certificati, nonché l'archiviazione di trust e informazioni sulla configurazione.
  
Tutti questi servizi vengono forniti automaticamente per le CA globali, inoltre alcuni possono essere utilizzati anche per le CA autonome in linea. Le CA non in linea tuttavia non possono interagire direttamente con Active Directory per archiviare e recuperare informazioni.
  
In questa guida, la CA principale non in linea utilizza Active Directory per i seguenti servizi di pubblicazione:
  
-   Archivio di pubblicazione CRL e AIA: gli elenchi CRL e i certificati CA vengono pubblicati manualmente in Active Directory come richiesto, consentendo ai client del dominio (in tutto l'insieme di strutture) di eseguire il recupero da un controller di dominio locale.
  
-   Distribuzione di certificati incrociati e CA principale affidabile ai client del dominio: i certificati CA principali affidabili definiti in Active Directory vengono automaticamente distribuiti nell'archivio principale affidabile di tutti i client di Active Directory all'interno dello stesso insieme di strutture. I certificati incrociati vengono distribuiti automaticamente in maniera analoga ai client del dominio.
  
Active Directory viene utilizzato dalle CA di emissione per tutti i servizi descritti nella sezione Integrazione di Active Directory.
  
**Utilizzo di Active Directory per client non appartenenti a Active Directory**
  
È necessario considerare alcuni fattori per il supporto di client PKI che sono membri di un altro insieme di strutture di Active Directory non affidabili oppure che non sono membri di un insieme di strutture di Active Directory.
  
Se si desidera consentire a questi tipi di client esterni di recuperare certificati CA ed elenchi CRL utilizzando il protocollo LDAP (Lightweight Directory Access Protocol), è necessario tenere presente i seguenti aspetti:
  
-   Per i client esterni è necessario configurare un nome host LDAP esplicito per i percorsi CDP e AIA. Per ulteriori informazioni, vedere la sezione "Configurazione dei percorsi CDP e AIA" più avanti in questo modulo.
  
-   Per impostazione predefinita, i client esterni non possono eseguire query LDAP anonime in Active Directory. È necessario cambiare il valore **dsHeuristics** dell'insieme di strutture e concedere autorizzazioni di accesso esplicite all'account **Anonymous**. Per ulteriori informazioni, vedere la sezione "Ulteriori informazioni" alla fine del modulo.
  
    **Avviso:** con questa procedura è disponibile un protocollo LDAP anonimo su tutti i controller di dominio dell'insieme di strutture. Tuttavia i client non autenticati potranno accedere solo agli elementi con autorizzazioni esplicite per l'account **Anonymous**. Prima di procedere, valutare attentamente le implicazioni nel consentire l'accesso non autenticato alla directory.
  
-   Poiché i client esterni non ereditano le informazioni principali affidabili configurate nella directory, sarà necessario individuare un altro modo per configurare tali informazioni.
  
**Considerazioni per client Internet**
  
È necessario considerare alcuni aspetti importanti in merito alla configurazione CDP e AIA descritta nella sezione "Configurazione di percorsi CDP e AIA" più avanti in questo modulo.
  
Se viene richiesto di fornire ricerche di certificati per supportare client Internet, ad esempio ricerche di certificati di posta elettronica, può essere necessario creare una directory LDAP separata per l'utilizzo di client Internet. Considerate le implicazioni relative alla protezione, si consiglia di non utilizzare il metodo descritto in precedenza per l'attivazione di un protocollo LDAP anonimo all'interno dell'insieme di strutture di Active Directory. Creare invece un insieme di strutture separato in Active Directory, quindi replicare le informazioni dall'insieme di strutture interno utilizzando lo strumento Formato interscambio dati LDIF - LDAP, un prodotto di metadirectory, ad esempio Microsoft Metadirectory Services (MMS), o un altro prodotto per la sincronizzazione delle directory.
  
##### Internet Information Services (IIS)
  
In questa progettazione, IIS fornisce due servizi per l'infrastruttura PKI:
  
-   Pubblicazione delle informazioni CA, ad esempio elenchi CRL, certificati CA e, potenzialmente, documenti CPS.
  
-   Funzionalità per registrare certificati utilizzando un'interfaccia Web (opzione non utilizzata in questa guida).
  
**Utilizzo di IIS per la pubblicazione di informazioni CA**
  
In questa guida, le informazioni CDP e AIA relative alle CA principali e di emissione vengono pubblicate in un server Web e in Active Directory. L'utilizzo della pubblicazione HTTP consente alla più vasta gamma di client di recuperare le informazioni necessarie, oltre a fornire un servizio di backup per i client di Active Directory che accedono normalmente a tali informazioni mediante LDAP.
  
L'installazione di IIS per la CA di emissione, pur essendo una procedura comune per tale scopo, non rappresenta la soluzione ottimale. Se disponibile, è necessario utilizzare un altro server IIS per la pubblicazione di informazioni CRL e CA. È consigliabile limitare le modalità di accesso degli utenti alle CA, in quanto ogni protocollo e servizio aggiuntivi alla CA offrono ai pirati informatici un altro possibile punto di accesso al server. L'utilizzo di IIS consente inoltre di prevenire l'interruzione dell'attività della CA per manutenzione, in quanto può essere l'unico percorso CRL valido per molti client.
  
Nella *Guida all'implementazione*, la CA di emissione viene utilizzata per ospitare IIS per la pubblicazione di CRL e CA. Questa operazione è stata eseguita per semplificare il processo di creazione e per ridurre la necessità di hardware aggiuntivo. Tuttavia, se è possibile utilizzare altri percorsi, è necessario farlo. Non esiste infatti alcun requisito per ospitare i percorsi CDP e AIA su IIS.
  
**Utilizzo di pagine IIS per registrare certificati**
  
La CA non necessita di pagine di registrazione Web. Per impostazione predefinita, in questa guida tali pagine vengono installate nelle CA di emissione, sebbene sia possibile installarle su un altro server Web. Anche se consentono di semplificare le attività di registrazione, non è necessario installare le pagine IIS se non vengono utilizzate.
  
Per ulteriori informazioni sull'installazione e sull'utilizzo delle pagine Web di registrazione, vedere la sezione "Ulteriori informazioni" più avanti in questo modulo.
  
#### Configurazione dei percorsi CDP e AIA
  
I client devono poter accedere a un elenco CRL aggiornato per stabilire se un certificato è stato revocato. I client devono inoltre poter recuperare certificati CA per verificare che un certificato di entità finale sia collegato a una CA principale attendibile. Ogni CA deve codificare nei propri certificati uno o più URL che consentono di individuare i percorsi in cui i client possono ottenere informazioni in merito a tali certificati.
  
È necessario configurare entrambi i valori relativi ai percorsi per le CA, tenendo in considerazione i client che utilizzeranno i certificati. L'argomento relativo alla definizione dei client dei certificati è stato descritto in una sezione precedente.
  
##### CA principale
  
In questa guida, la CA principale viene configurata come segue:
  
-   I percorsi principali (primi dell'elenco) per CDP e AIA sono URL HTTP. Dato che l'elenco CRL della CA principale ha dimensioni ridotte (1 - 2 KB) e l'intervallo di pubblicazione è piuttosto lungo (sei mesi), è possibile pubblicarlo in un unico percorso senza provocare significativi colli di bottiglia, a causa di client che recuperano il CRL.
  
-   I percorsi secondari vengono configurati come URL LDAP in qualità di backup delle destinazioni HTTP. Poiché non viene utilizzato alcun nome host LDAP, i client dello stesso insieme di strutture recuperano le informazioni dai propri controller di dominio locali. I client esterni all'insieme di strutture non possono accedere a questa posizione.
  
In questa configurazione, i certificati della CA e le CA subordinate possono essere utilizzati dai client esterni all'insieme di strutture di Active Directory, in quanto vengono utilizzati i percorsi HTTP per impostazione predefinita.
  
##### CA di emissione
  
In questa guida, viene ottimizzata la CA di emissione per essere utilizzata da client interni di Active Directory. La CA viene configurata come segue:
  
-   I percorsi principali per gli URL CDP e AIA corrispondono ai percorsi di directory LDAP.
  
-   Negli URL CDP e AIA non viene specificato alcun nome host LDAP, quindi il client utilizza il server LDAP predefinito. Per i client di Active Directory, il server LDAP predefinito corrisponde ai controller di dominio locali. È possibile tuttavia che altri client LDAP non riescano a eseguire query per questi percorsi LDAP.
  
Questa configurazione è ideale per client dello stesso insieme di strutture delle CA. Gli elenchi CRL di base vengono pubblicati settimanalmente, mentre gli elenchi Delta CRL vengono pubblicati quotidianamente. Poiché per impostazione predefinita entrambi si trovano in Active Directory, i client recupereranno tali elenchi dai controller di dominio più vicini. In questo modo viene garantita la capacità di recupero e l'ottimizzazione del traffico di rete.
  
**Impostazione di CDP e AIA per client non appartenenti a Active Directory**
  
La configurazione precedente non è ottimale per i client che sono membri di un altro insieme di strutture di Active Directory o che non sono membri di un insieme di strutture (ad esempio, un router). Poiché questi client esterni non potranno accedere a CDP e AIA in LDAP, gli utenti esterni possono registrare ritardi significativi durante il tentativo di controllare la revoca e le informazioni AIA. Questi ritardi possono provocare errori nelle applicazioni in determinate circostanze.
  
Il supporto di questi client esula dagli argomenti trattati in questa guida. Tuttavia, per un eventuale supporto in questa configurazione, si consiglia di aggiungere una CA di emissione con percorsi CDP e AIA configurati per utilizzare solo URL HTTP.
  
Se si desidera utilizzare percorsi LDAP per questi client, è necessario tenere presente i seguenti aspetti:
  
-   Per i client esterni è necessario configurare un nome host LDAP esplicito per i percorsi CDP e AIA. Per apportare modifiche, è necessario emettere nuovamente (rinnovare) il certificato CA.
  
-   È necessario attivare l'accesso LDAP anonimo come descritto precedentemente in questo modulo.
  
**Considerazioni per client Internet**
  
Se si intende distribuire certificati all'esterno dell'organizzazione da utilizzare su Internet, è necessario tenere presente alcune considerazioni.
  
I certificati che includono URL LDAP interni possono fornire informazioni sulla struttura e sui nomi di Active Directory e della CA. Per evitare questo, è necessario eseguire le seguenti operazioni:
  
-   Utilizzare solo URL HTTP per i valori CDP e AIA della CA principale e per tutte le CA subordinate della catena.
  
-   Rilasciare certificati da utilizzare esternamente da una CA separata, in cui vengono utilizzati solo CDP HTTP e URI AIA.
  
In entrambi i casi, è necessario fornire una posizione HTTP secondaria per il recupero di CRL affinché i client possano utilizzarla, se la posizione principale non è disponibile.
  
Per ulteriori informazioni sull'utilizzo di CRL e CDP, vedere i riferimenti a tale argomento inclusi nella sezione "Ulteriori informazioni" nella parte finale del modulo.
  
#### Estensione dell'infrastruttura CA
  
Nella sezione "Definizione dei requisiti di protezione dei certificati" viene descritta la classificazione dei certificati in base al livello di protezione e al tipo di soggetto. Il motivo principale della separazione dei differenti tipi di soggetti consiste nella possibilità che vengano applicati a questi tipi di soggetti criteri di certificazione e procedure operative diverse (come documentato nelle dichiarazioni CPS).
  
In genere, viene applicata una dichiarazione CPS per ogni CA. Anche se è possibile adottare criteri differenti per controllare tipi di soggetto diversi in una singola CA, questo renderebbe la CPS più complessa e difficile da implementare correttamente. La strategia per estendere questa infrastruttura PKI e consentire il rilascio di certificati dotati di requisiti di protezione e criteri differenti, consiste nel creare ulteriori CA di emissione per la maggior parte dei tipi di soggetto. Questa procedura è illustrata nella seguente figura.
  
**Nota:** questa figura è solamente indicativa di come sia possibile estendere la gerarchia CA precedente. Nella propria organizzazione può essere necessaria una struttura più complessa, o al contrario più semplice, a seconda delle esigenze future. La pianificazione delle CA aggiuntive e delle funzionalità di certificazione deve basarsi sui requisiti aziendali e deve seguire un approccio simile a quello illustrato in questa guida per la progettazione della PKI semplificata.
  
![](images/Dd536257.SGFG17003(it-it,TechNet.10).jpg)
  
Figura 3  
*Estensione della gerarchia CA*
  
In questa figura viene illustrato come sia possibile estendere la gerarchia CA semplificata descritta precedentemente per far fronte a una più ampia gamma di requisiti dei certificati. Le nuove CA e funzionalità dei certificati vengono mostrate su sfondo grigio. Nella figura viene inoltre illustrato l'uso di certificati di valore elevato (simbolo a forma di lucchetto) e come le CA utente (interno ed esterno) una volta portate in linea, assumeranno il ruolo di rilasciare certificati utente di basso valore dalla prima CA.
  
Questa strategia relativa all'estensione dell'infrastruttura CA presuppone quanto segue:
  
-   La gestione dell'infrastruttura CA viene centralizzata, pertanto non è necessario delegare il controllo delle CA in base a divisioni organizzative o geografiche.
  
-   Gli standard comuni dei certificati vengono utilizzati in tutta l'organizzazione; questo significa che è stato accettato un certificato di un tipo determinato e sono stati concordati gli utilizzi e i criteri comuni in tutta l'organizzazione.
  
-   Non è richiesta alcuna interoperabilità con un'infrastruttura PKI esistente.
  
-   Sono richiesti livelli e criteri di protezione differenti per i diversi tipi di certificati indicati (e altri che potrebbero essere necessari).
  
Se tali presupposti non sono validi per la propria organizzazione, può rendersi necessaria una struttura più complessa. Per una descrizione dettagliata sulle diverse opzioni e approcci relativi all'estensione di un'infrastruttura CA, vedere il modulo "Designing a Public Key Infrastructure" incluso nel *Resource Kit*.
  
#### Subordinazione qualificata
  
Le definizioni dei certificati create possono essere utilizzate per definire i modelli dei certificati e per rilasciare certificati senza ulteriore personalizzazione. È possibile tuttavia limitare l'ambito dei certificati che possono essere rilasciati dalle CA, imponendo la delega dei certificati CA di emissione. La subordinazione qualificata, descritta in una sezione precedente, può essere utilizzata per controllare l'ambito e lo scopo dei trust all'interno dell'organizzazione mediante la creazione di certificati incrociati tra l'infrastruttura CA aziendale e quella di organizzazioni esterne. È possibile utilizzare la stessa tecnica per limitare i tipi e alcuni attributi di certificati all'interno della propria gerarchia CA. È possibile imporre una delle seguenti restrizioni per le CA di emissione:
  
-   Restrizioni di base: definire la lunghezza del percorso di certificazione richiesto e consentito per gli identificatori e il mapping dei criteri.
  
-   Restrizioni dei nomi: definire l'intervallo degli spazi dei nomi consentiti o esclusi dalla CA subordinata qualificata e dalle subordinate corrispondenti.
  
-   Criteri di emissione: definire il livello per cui l'organizzazione ritiene affidabile l'identità presentata per un certificato. Questi criteri vengono identificati in un certificato mediante gli oggetti OID.
  
-   Criteri delle applicazioni: definire le applicazioni che possono essere utilizzate assieme ad alcuni certificati specifici.
  
Queste regole sono codificate nel certificato emesso dalla CA principale (o intermedia); non possono essere ignorate senza eseguire il rinnovo del certificato CA. Questa funzionalità risulta particolarmente utile quando si desidera delegare il controllo su una CA ma è necessario limitare i tipi di certificati che possono essere rilasciati dalla CA.
  
Per l'infrastruttura PKI semplificata creata in questa guida, non è necessario utilizzare la subordinazione qualificata all'interno della gerarchia CA.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione dei certificati
  
In questa sezione viene descritta la modalità di configurazione dei certificati per soddisfare i requisiti precedentemente definiti all'interno del presente modulo.
  
#### Definizione dei parametri dei certificati
  
Per ciascun tipo di certificato richiesto, è necessario indicare il profilo del certificato relativo e convertirlo in un modello di certificato.
  
**Nota:** le CA autonome non utilizzano modelli di certificati. È necessario creare la richiesta tramite uno strumento, quale Certreq.exe, utilizzando il modulo presente nelle pagine Web di registrazione o creando la richiesta a livello di programmazione. Per la creazione di richieste di certificati, è possibile utilizzare i profili di certificati definiti in questo capitolo.
  
In una definizione di profilo di certificato sono compresi tutti gli elementi riportati di seguito:
  
-   Nome modello e nome visualizzato; è necessario definire uno standard di denominazione.
  
-   Lunghezza della chiave del certificato.
  
-   Periodo di validità del certificato.
  
-   Estensioni facoltative del certificato.
  
-   Criteri di registrazione e rinnovo.
  
-   Criteri relativi ai periodi di validità.
  
-   Criteri relativi all'utilizzo delle applicazioni.
  
-   Criteri relativi all'utilizzo delle chiavi.
  
-   Criteri relativi all'archiviazione delle chiavi.
  
-   Autorizzazione del certificato.
  
-   Creazione del nome del soggetto.
  
-   Agenti di registrazione del certificato.
  
-   Creazione della chiave.
  
-   Chiave e tipi di CSP.
  
La lunghezza, il periodo di validità, le opzioni di creazione della chiave e i criteri di registrazione e autorizzazione sono determinati dal livello di protezione del certificato richiesto e dai requisiti dell'applicazione indicati precedentemente in questo modulo.
  
#### Definizione della durata delle chiavi e dei certificati
  
Una serie di fattori influisce sulla durata dei certificati, quali il tipo di certificato, i requisiti di protezione dell'organizzazione, le procedure standard applicate nel settore interessato e la normativa in vigore. In generale, maggiore è la lunghezza delle chiavi, maggiore sarà la durata supportata per i certificati e le chiavi.
  
Di seguito vengono riportate le limitazioni alla lunghezza e al tipo di chiavi utilizzate:
  
-   Compatibilità: alcune applicazioni di certificati non supportano chiavi più lunghe di 2.048 bit. È inoltre possibile che la scelta del tipo di chiave influisca sulla compatibilità; generalmente, le chiavi RSA offrono maggiore compatibilità. Per tutte le CA della catena, è necessario tenere in considerazione la compatibilità sia in termini di lunghezza che in termini di tipo di chiave.
  
-   Prestazioni: per operazioni di firma e crittografia la capacità di elaborazione richiesta aumenta con la lunghezza delle chiavi. Per questo motivo, chiavi con lunghezza superiore a 2.048 bit non verranno utilizzate da CA che emettono un'elevata quantità di certificati.
  
-   Archiviazione: chiavi più lunghe richiedono certificati più grandi e quindi capacità di archiviazione maggiore nel database dei certificati. Se i certificati vengono pubblicati in Active Directory, aumenteranno anche i relativi requisiti di spazio di archiviazione. La dimensione e la frequenza di backup sarà direttamente proporzionale.
  
Quando si sceglie la durata dei certificati e delle chiavi, occorre considerare il grado di vulnerabilità delle chiavi e le relative conseguenze potenziali. I fattori indicati di seguito influiscono sulla durata prescelta dei certificati e delle chiavi.
  
-   Lunghezza della chiave privata: poiché chiavi di lunghezza maggiore sono più difficili da violare, ne è giustificata la maggiore durata.
  
-   Protezione CA: maggiore è il livello di protezione offerto dalla CA e dalla relativa chiave privata, maggiore sarà la durata della chiave.
  
-   Utilizzo di risorse hardware di crittografia: smart card e periferiche HSM (Hardware Security Module) rendono la chiave più sicura e ne giustificano la maggiore durata.
  
-   Attendibilità dei soggetti certificati: è possibile garantire una maggiore durata dei certificati ai dipendenti e ai computer interni rispetto agli utenti e ai computer esterni.
  
-   Numero di certificati firmati mediante una chiave CA: maggiore è il numero di accessi alla chiave, maggiore sarà la diffusione della chiave CA pubblica e maggiori saranno le probabilità di tentativi di violazione e eventuale compromissione.
  
Nella tabella riportata di seguito, vengono indicati la durata e i periodi di rinnovo delle chiavi per le CA e le entità finali utilizzate in questa guida.
  
**Tabella 10. Durata di certificati e chiavi**

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Soggetto certificato</th>
<th>Lunghezza della chiave</th>
<th>Durata della chiave</th>
<th>Intervallo di rinnovo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CA principale</td>
<td style="border:1px solid black;">4.096 bit</td>
<td style="border:1px solid black;">16 anni</td>
<td style="border:1px solid black;">8 anni</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CA di emissione</td>
<td style="border:1px solid black;">2.048 bit</td>
<td style="border:1px solid black;">8 anni</td>
<td style="border:1px solid black;">4 anni</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Entità finale</td>
<td style="border:1px solid black;">da 1.024 a 2.048 bit</td>
<td style="border:1px solid black;">Da 6 mesi a 2 anni</td>
<td style="border:1px solid black;">90 per cento del periodo di validità</td>
</tr>
</tbody>
</table>
  
I livelli di crittografia offerti dalle chiavi a 1.024 bit vengono considerati, attualmente, superiori alle esigenze più comuni. Dovrebbero infatti disporre di una durata media che superi abbondantemente il valore proposto, pari a 2 anni, per l'entità finale. L'utilizzo delle chiavi a 512 bit, tuttavia, non garantisce più un sufficiente grado di sicurezza, se non per applicazioni con requisiti di protezione estremamente ridotti, e pertanto non vengono utilizzate in questa soluzione.
  
Il livello di crittografia della chiave della CA di emissione rappresenta un compromesso tra prestazioni e protezione. Una chiave di questa dimensione dispone attualmente di una durata che supera abbondantemente il periodo di rinnovo quadriennale previsto.
  
Poiché la CA principale non presenta limiti reali in termini di prestazioni, è possibile impostare il livello di crittografia della chiave sul valore massimo pari a 16 kilobit. Per esigenze di compatibilità, il livello utilizzato è molto inferiore. Tuttavia, le chiavi a 4.096 bit dispongono di una durata che supera abbondantemente il periodo previsto di rinnovo pari a otto anni.
  
Le chiavi RSA vengono utilizzate da tutte le CA, sebbene il tipo di chiave utilizzato per le entità finali viene determinato dai requisiti dell'applicazione.
  
Sebbene sia possibile rinnovare un certificato con la stessa chiave, in questa configurazione tale operazione non è consentita per le chiavi CA utilizzate in circostanze normali. A ogni rinnovo di certificato verrà invece generata una nuova coppia di chiavi.
  
I certificati emessi dalle CA non possono disporre di un periodo di validità che superi quello della CA di emissione e da tutte quelle di livello superiore, compresa la principale. Se la durata prevista di un certificato CA è pari a un periodo di sei mesi, sarà possibile emettere solo certificati con una durata massima pari allo stesso periodo. In questa soluzione, pertanto, il rinnovo dei certificati emessi dalla CA è previsto a metà della durata prestabilita. La validità di tutti i certificati emessi da una CA non deve superare la metà del periodo di validità del certificato della CA di emissione.
  
In questo modo, i periodi massimi di validità per entità finali, CS di emissione e CA principali sono rispettivamente pari a quattro, otto e sedici anni. In questa soluzione, i certificati delle entità finali vengono comunemente conservati per un periodo massimo di due anni. In questo modo è possibile introdurre un livello CA intermedio aggiuntivo senza conseguenze rilevanti sulla struttura gerarchica della durata dei certificati.
  
#### Mapping dei requisiti di protezione con i parametri del certificato
  
Nella tabella seguente, vengono elencati i tipi di certificato precedentemente identificati nel documento e viene indicato come la categoria di protezione di ciascun tipo venga mappata con i parametri corrispondenti del profilo del certificato.
  
**Tabella 11. Parametri del certificato**

 
<table style="border:1px solid black;">
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di certificato</th>
<th>Criterio di emissione</th>
<th>Metodo di approvazione</th>
<th>Chiave</th>
<th>Periodo di validità</th>
<th>Archiviazione chiave</th>
<th>Esportazione chiave</th>
<th>CSP</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione client: utente</td>
<td style="border:1px solid black;">Basso</td>
<td style="border:1px solid black;">Automatica (autenticazione dominio)</td>
<td style="border:1px solid black;">1.024</td>
<td style="border:1px solid black;">1 anno</td>
<td style="border:1px solid black;">Software</td>
<td style="border:1px solid black;">No</td>
<td style="border:1px solid black;">Nominato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Autenticazione client: computer</td>
<td style="border:1px solid black;">Basso</td>
<td style="border:1px solid black;">Automatica (autenticazione dominio)</td>
<td style="border:1px solid black;">1.024</td>
<td style="border:1px solid black;">1 anno</td>
<td style="border:1px solid black;">Software</td>
<td style="border:1px solid black;">No</td>
<td style="border:1px solid black;">Nominato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Autenticazione server IAS</td>
<td style="border:1px solid black;">Medio</td>
<td style="border:1px solid black;">Manuale (Cert Manager)</td>
<td style="border:1px solid black;">1.024</td>
<td style="border:1px solid black;">1 anno</td>
<td style="border:1px solid black;">Software</td>
<td style="border:1px solid black;">No</td>
<td style="border:1px solid black;">Nominato</td>
</tr>
</tbody>
</table>
  
**Nota:** i valori della colonna CSP (Cryptographic Service Provider, provider di servizi di crittografia) serve per indicare che è necessario specificare il provider CSP consentito dal modello. I certificati del computer client e del server dispongono di requisiti CSP specifici.
  
#### Mapping dei requisiti del certificato con i parametri del modello del certificato
  
Spesso le applicazioni richiedono una configurazione dei certificati ben precisa. Il nome del soggetto deve essere formattato in modo specifico, devono essere compresi gli OID dei criteri dell'applicazione oppure l'emissione del certificato deve avvenire con un criterio specifico. Per l'applicazione è comunque necessario che l'utilizzo della chiave sia stato definito in modo corretto. Per una corretta definizione del profilo del certificato, è necessario richiedere tali parametri al proprietario o al fornitore dell'applicazione.
  
Nelle tabelle riportate di seguito, vengono indicati i requisiti dell'applicazione per i certificati richiesti da questa soluzione. Nelle tabelle vengono indicati i parametri CA e le proprietà del certificato, sulla base della configurazione riportata nei modelli di certificato. Nell'elenco è riportata una parte delle proprietà possibili.
  
**Nota:** ogni tipo di certificato mostrato di seguito si basa su un tipo di modello incorporato. Tuttavia, poiché i parametri del modello vengono modificati, sono utilizzate delle copie dei modelli incorporati. In questo modo, sarà possibile ripristinare facilmente i modelli incorporati, se necessario.
  
**Tabella 12. Autenticazione client: utente**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parametro del certificato</th>
<th>Valore richiesto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Pubblicazione Active Directory</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Utilizzo della chiave</td>
<td style="border:1px solid black;">Firma digitale</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Archiviazione della chiave</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Dimensione minima della chiave</td>
<td style="border:1px solid black;">1.024</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome del soggetto</td>
<td style="border:1px solid black;">Nome comune</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome alternativo del soggetto</td>
<td style="border:1px solid black;">Nome principale dell'utente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri dell'applicazione/utilizzo avanzato delle chiavi</td>
<td style="border:1px solid black;">Autenticazione client</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Provider del servizio di crittografia (CSP)</td>
<td style="border:1px solid black;">Microsoft Base Cryptographic Provider version 1.0<br />
Microsoft Enhanced Cryptographic Provider version 1.0</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ricavato dal modello</td>
<td style="border:1px solid black;">Sessione autenticata</td>
</tr>
</tbody>
</table>
  
**Tabella 13. Autenticazione client: computer**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parametro del certificato</th>
<th>Valore richiesto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Pubblicazione Active Directory</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Utilizzo della chiave</td>
<td style="border:1px solid black;">Firma digitale<br />
Crittografia chiave</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Archiviazione della chiave</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Dimensione minima della chiave</td>
<td style="border:1px solid black;">1.024</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome del soggetto</td>
<td style="border:1px solid black;">Nome comune</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome alternativo del soggetto</td>
<td style="border:1px solid black;">Nome DNS</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri dell'applicazione/utilizzo avanzato delle chiavi</td>
<td style="border:1px solid black;">Autenticazione client</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Provider del servizio di crittografia (CSP)</td>
<td style="border:1px solid black;">Microsoft RSA SChannel Cryptographic Provider</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ricavato dal modello</td>
<td style="border:1px solid black;">Autenticazione workstation</td>
</tr>
</tbody>
</table>
  
**Tabella 14. Autenticazione server mediante standard 802.1X**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Parametro del certificato</th>
<th>Valore richiesto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Pubblicazione di Active Directory</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Utilizzo della chiave</td>
<td style="border:1px solid black;">Firma digitale<br />
Crittografia chiave</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Archiviazione della chiave</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Dimensione minima della chiave</td>
<td style="border:1px solid black;">1.024</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Nome del soggetto</td>
<td style="border:1px solid black;">Nome comune</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome alternativo del soggetto</td>
<td style="border:1px solid black;">DNS</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Criteri dell'applicazione/utilizzo avanzato delle chiavi</td>
<td style="border:1px solid black;">Autenticazione server</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Provider del servizio di crittografia (CSP)</td>
<td style="border:1px solid black;">Microsoft RSA SChannel Cryptographic Provider</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ricavato dal modello</td>
<td style="border:1px solid black;">Servizio di Accesso remoto (RAS) e server IAS</td>
</tr>
</tbody>
</table>
  
#### Creazione di modelli di protezione
  
Il servizio Active Directory di Windows Server 2003 contiene le definizioni dei modelli di certificato impiegati per la gestione delle funzioni più comuni. Le CA di livello aziendale, per impostazione predefinita, sono configurate per l'emissione di diversi tipi di certificati incorporati. Le descrizioni di tutti i modelli incorporati sono reperibili all'interno della documentazione di Windows Server 2003 Enterprise Edition. Per ulteriori dettagli, vedere la sezione "Ulteriori informazioni" alla fine del modulo.
  
La maggior parte di questi tipi di modelli sono stati rimossi dalla CA nella soluzione, ovvero sono stati eliminati dalla cartella dei modelli utilizzati dall'Autorità di certificazione.
  
È possibile scegliere di utilizzare i modelli predefiniti, utilizzati dalla maggior parte delle applicazioni Windows basate su certificati, a seconda delle proprie esigenze. Nel caso sia necessario emettere altri tipi di certificati, è preferibile creare modelli appositamente personalizzati. L'utilizzo di modelli predefiniti, senza conoscerne le caratteristiche, comporta rischi legati all'attivazione accidentale di funzionalità. Il certificato Computer, creato per la sola autenticazione di client ad esempio, può anche essere utilizzato come certificato per server Web.
  
Per creare nuovi modelli, è necessario stabilirne uno predefinito che risponda quanto più possibile a specifiche esigenze e da cui creare un duplicato sul quale basare il nuovo modello. In questo modulo, la configurazione dei modelli è costituita da una semplice procedura di applicazione dei profili di certificato.
  
**Nota:** non è possibile creare un modello completamente nuovo. È necessario ricavarne uno da un modello esistente. I modelli computer e utente devono essere sempre ricavati da modelli simili non interscambiabili.
  
Durante la creazione e la modifica di modelli, è necessario conservare una registrazione dettagliata dei parametri del modello all'interno del sistema di gestione della configurazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Creazione di un piano per la gestione dei certificati
  
Dopo aver configurato i certificati per l'organizzazione, è necessario creare un piano per la gestione che ne copra l'intero periodo di validità. Per la creazione di un piano di gestione dei certificati, è necessario considerare quanto segue.
  
-   Come vengono elaborate le richieste e il rinnovo di certificati.
  
-   Come eseguire il mapping dei certificati con gli account utente.
  
-   Come gestire e distribuire elenchi CRL.
  
-   Strategie utilizzate per il ripristino dei dati crittografati.
  
#### Selezione dei metodi di registrazione e rinnovo
  
È possibile eseguire la registrazione e il rinnovo del certificato, tramite una delle seguenti procedure.
  
-   Registrazione automatica di Windows.
  
-   Registrazione in linea mediante Certificate Enrollment Wizard, che solitamente è possibile avviare dalla console di gestione dei certificati.
  
-   Registrazione in linea mediante l'utilizzo delle interfacce CryptoAPI o CAPICOM da applicazioni o da script.
  
-   Utilizzo dello strumento Certreq.exe per creare e inoltrare richieste, nonché per recuperare i certificati emessi.
  
    **Nota:** i quattro metodi sopra riportati rappresentano semplicemente differenti interfacce per la medesima modalità di registrazione in linea.
  
-   Registrazione tramite pagina Web.
  
-   Registrazione manuale non in linea: la procedura comporta la creazione di un file di richiesta tramite i metodi precedentemente descritti, l'invio della richiesta alla CA e il suo successivo inoltro tramite la console di gestione delle CA e il recupero tramite Microsoft Management Console).
  
Tutti questi metodi sono validi e appropriati se utilizzati in determinate circostanze. In questa soluzione vengono utilizzati i metodi di registrazione indicati di seguito.
  
-   Registrazione automatica di Windows. È preferibile utilizzare questo metodo, se possibile, per ridurre il carico di gestione dei certificati. È possibile utilizzare la procedura di registrazione automatica anche nel caso in cui sia necessaria un'approvazione manuale del certificato. Sebbene il certificato non venga emesso immediatamente, verrà inoltrata una richiesta all'Autorità di certificazione e la registrazione verrà completata a seguito dell'approvazione della richiesta.
  
-   Registrazione manuale non in linea: questo metodo viene utilizzato per tutte le procedure di registrazione e rinnovo dei certificati presso la CA principale.
  
Nessuno di questi metodi risulta adeguato per scenari più complessi, ad esempio, situazioni in cui sia necessaria la firma di una richiesta di certificato da parte di terzi prima dell'inoltro alla CA. La registrazione in linea basata su chiamate a procedure remote (RPC) non è supportata dalla maggior parte di piattaforme non Windows, ad esempio i router. Non è inoltre possibile eseguire la registrazione automatica in tutti i casi in cui è necessario definire il nome principale o alternativo del soggetto nella richiesta di certificato, piuttosto che demandarne la creazione al servizio Active Directory.
  
Per ovviare a situazioni di questo tipo, è necessario considerare uno dei metodi riportati di seguito.
  
-   Creare uno script CAPICOM da eseguire sul computer client autonomo, ad esempio all'interno di uno script di accesso.
  
-   Utilizzare lo strumento certereq.exe all'interno di un comando o di un file batch per creare e inoltrare richieste, nonché per recuperare e installare il certificato emesso.
  
-   È possibile creare una pagina Web personalizzata, in formato ASP o ASP .NET, utilizzando uno script CAPICOM per creare e inoltrare la richiesta. In questo modo è possibile fornire servizi di registrazione per un'ampia gamma di clienti, includendo complesse procedure a più fasi, ad esempio, quando è necessario utilizzare più firme per approvare una singola richiesta.
  
#### Mapping dei certificati con le identità
  
Il mapping di certificati con i soggetti denominati nei certificati rappresenta un argomento di discussione che supera gli obiettivi prefissati dal presente documento. È tuttavia necessario considerare due aspetti importanti.
  
-   Il modo in cui l'identità del soggetto certificato viene confermata prima dell'emissione dello stesso.
  
-   Il modo in cui l'identità del soggetto certificato viene determinata sulla base delle informazioni fornite nella directory.
  
Il primo aspetto riguarda la modalità di elaborazione della procedura di registrazione del certificato, argomento trattato nella sezione "Creazione dei criteri di emissione dei certificati". Il secondo problema si riferisce alle modalità con cui gli utenti (applicazioni e servizi) possono mappare correttamente l'identità del soggetto certificato con un'altra identità disponibile. Di seguito vengono riportati alcuni esempi.
  
-   Modalità con cui il controller di dominio identifica un utente sulla base del certificato di smart card, per consentire all'utente l'accesso al dominio, creare un token di accesso e così via.
  
-   Modalità con cui un utente di posta elettronica rileva il certificato di un altro utente a cui inviare un messaggio di posta elettronica protetto.
  
La maggior parte dei certificati vengono automaticamente mappati con identità di protezione (quali utenti e computer, ma non gruppi) di Active Directory nell'ambito della procedura di registrazione. Nei casi in cui Active Directory consente di definire il nome del soggetto principale o alternativo del certificato, il mapping sarà sempre esplicito. Nel nome del soggetto alternativo sarà contenuto il nome principale utente (UPN) e/o il nome di posta elettronica di un utente, il nome principale servizio (SPN) e/o il nome host DNS di un computer. I valori UPN e SPN saranno sempre univoci nell'insieme di strutture di Active Directory. È necessario che i nomi di posta elettronica e DNS siano univoci, sebbene per Active Directory non venga esplicitamente richiesto.
  
Se l'utente del certificato ha accesso alla directory, è sempre possibile la risoluzione dell'utente o del computer di Active Directory dal certificato e viceversa. È inoltre possibile importare manualmente o mappare altri certificati con oggetti utente o computer: il mapping di un oggetto Active Directory con un certificato è sempre possibile, ma non necessariamente il contrario.
  
Seguono alcuni tra i diversi esempi di casi in cui non è richiesto il mapping esplicito.
  
-   Server Web in cui l'identificatore principale corrisponde al nome host DNS del sito Web.
  
-   Situazioni in cui i certificati vengono emessi a identità che non dispongano di un equivalente in Active Directory, ad esempio un router o un utente di un'altra organizzazione.
  
Tutte le entità finali menzionate in questa guida dispongono del mapping esplicito con gli utenti e i computer di Active Directory.
  
Le CA rappresentano casi speciali poiché non vengono necessariamente mappate con oggetti computer. Tuttavia, generalmente verranno mappate con oggetti **Autorità di certificazione** nei contenitori di Accesso alle informazioni dell'autorità (AIA) e delle Autorità di certificazione attendibili.
  
#### Creazione dei criteri di emissione dei certificati
  
È necessario definire il metodo di approvazione del certificato almeno per ogni categoria di protezione (alta, media e bassa) e spesso anche per ogni categoria del soggetto certificato, quali computer, utente interno o esterno. È comunque molto improbabile che occorra definire i criteri con maggiore precisione. Nelle dichiarazioni delle procedure e dei criteri di certificazione occorre includere le scelte relative ai criteri adottati.
  
Il criterio di emissione rappresenta un'indicazione del tipo di procedura di approvazione certificati e del livello di protezione della chiave privata utilizzati nell'ambito della registrazione di un certificato. Tali informazioni sono codificate all'interno del certificato tramite ID oggetto in grado di rappresentare i singoli criteri. Il rigore della procedura di approvazione riflette il valore del certificato in fase di approvazione. L'obiettivo della procedura di approvazione o registrazione è fornire un livello di attendibilità che garantisca la corrispondenza tra il richiedente e il soggetto certificato. Il livello di crittografia della chiave rappresenta la misura del livello di attendibilità riposto nel soggetto certificato, in quanto unico possessore della chiave privata.
  
I livelli di garanzia offerti dai certificati utilizzati in questa guida sono stati definiti in precedenza nel presente modulo, nella sezione "Definizione dei requisiti di protezione dei certificati". È possibile indicare il livello di garanzia del certificato emesso, includendo un ID oggetto del criterio di emissione, corrispondente al livello di garanzia dei certificati. Il criterio di emissione può essere utilizzato da applicazioni e da individui per determinare il grado di affidabilità di un certificato specifico.
  
In Windows Server 2003 i tre livelli di garanzia definiti in precedenza vengono mappati con tre criteri di emissione predefiniti. Nella tabella seguente viene illustrato l'utilizzo di diversi criteri di emissione all'interno di questa guida. È necessario includere il criterio di emissione, almeno per i criteri a media e alta protezione, all'interno dei modelli di certificato in modo da facilitare l'identificazione di certificati con livelli di garanzia superiori. Il livello di garanzia dei certificati sprovvisti di un criterio di emissione viene considerato basso.
  
**Tabella 15. Livelli dei criteri di emissione dei certificati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Criterio di emissione</th>
<th>Requisiti di registrazione</th>
<th>Requisiti minimi di archiviazione della chiave</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Basso</td>
<td style="border:1px solid black;">Approvazione automatica a seconda dell'esito dell'autenticazione di dominio.<br />
Per le CA autonome, si tratta del livello di approvazione non autenticato, ovvero il caso in cui la CA emette il certificato senza eseguire la verifica del richiedente.</td>
<td style="border:1px solid black;">Chiavi software</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Medio</td>
<td style="border:1px solid black;">Approvazione del membro del gruppo Certificate Manager.<br />
All'interno del criterio, occorre definire i tipi di verifiche eseguite dal Certificate Manager prima dell'approvazione della richiesta.</td>
<td style="border:1px solid black;">Chiavi software o hardware.<br />
Con chiavi software è necessario utilizzare una protezione avanzata, in tutti i casi in cui è supportata dall'applicazione. Ad esempio, i certificati di computer non possono utilizzare una protezione con livello di crittografia elevato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Alto</td>
<td style="border:1px solid black;">Firma del responsabile della registrazione e approvazione del Certificate Manager.<br />
È necessario definire i tipi di controllo che devono essere eseguiti da responsabili della registrazione e dal Certificate Manager prima che la richiesta venga approvata.</td>
<td style="border:1px solid black;">Token hardware a prova di alterazione.<br />
Ad esempio, token di crittografia USB o smart card per un utente o HSM per un computer.</td>
</tr>
</tbody>
</table>
 

**Nota:** le motivazioni che possono portare alla definizione un numero maggiore o minore di criteri di rilascio o di livelli di garanzia dipendono solo dai requisiti dell'organizzazione.

#### Creazione dei criteri di revoca dei certificati

In alcune situazioni è necessario invalidare un certificato prima del termine del periodo di validità. La creazione di criteri per la revoca dei certificati comporta le seguenti attività:

-   Definizione delle condizioni di garanzia della revoca di un certificato.

-   Selezione di una posizione per la pubblicazione degli elenchi CRL.

-   Selezione dei tipi di elenchi CRL che si desidera utilizzare.

-   Creazione di pianificazioni per la pubblicazione di elenchi CRL.

La definizione delle condizioni di garanzia della revoca del certificato saranno comprese nel criterio del certificato, che può variare in base al tipo di certificato utilizzato. La variazione è più evidente per i certificati con livelli di garanzia e tipi di soggetto differenti, nonché per l'autorità di certificazione.

È necessario, inoltre, documentare l'eventuale l'utilizzo di codici motivo da utilizzare durante la revoca di un certificato. Nella tabella seguente vengono riportati i diversi codici motivo.

**Tabella 16. Codici di revoca dei certificati**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Codice motivo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Compromissione chiave</td>
<td style="border:1px solid black;">La chiave privata del certificato è stata compromessa o se ne sospetta la compromissione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Compromissione della CA</td>
<td style="border:1px solid black;">La chiave privata della CA è stata compromessa o se ne sospetta la compromissione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Modifica di affiliazione</td>
<td style="border:1px solid black;">Il soggetto è passato a un'altra organizzazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Sostituzione</td>
<td style="border:1px solid black;">È stato emesso un nuovo certificato in sostituzione di quello in uso.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Termine operatività</td>
<td style="border:1px solid black;">La CA non viene più utilizzata.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Sospensione certificato</td>
<td style="border:1px solid black;">L'utilizzo di un certificato deve essere temporaneamente sospeso: ad esempio, nel caso in cui l'utente abbia accidentalmente smarrito la smart card, pur non essendone certo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Non specificato</td>
<td style="border:1px solid black;">Qualsiasi motivo che non corrisponda ai codici precedentemente indicati.</td>
</tr>
</tbody>
</table>
  
**Importante:** utilizzare il codice motivo Sospensione certificato, solo nei casi di effettiva necessità. La sospensione e il successivo rilascio del certificato non consente in alcun modo di determinare lo stato di revoca del certificato e conseguentemente la validità di una firma effettuata da tale certificato in un dato momento.
  
Nella procedura di revoca, includere gli elementi riportati di seguito, che verranno archiviati in un registro di gestione delle modifiche o dei problemi di protezione.
  
-   Motivo della revoca del certificato.
  
-   Utente che ha richiesto la revoca del certificato.
  
-   Eventuale necessità del certificato in futuro: ad esempio, per la verifica delle firme o la decrittografia dei messaggi. In caso affermativo, considerare per quale delle procedure indicate sopra (verifica delle firme, decrittografia dei messaggi o utilizzo normale) potrebbe tornare utile.
  
-   Eventuali requisiti speciali dell'utente che revoca il certificato e che devono essere soddisfatti dall'amministratore, ad esempio nel caso in cui l'utente è un Certificate Manager.
  
-   Eventuale presenza di procedure operative documentare per l'organizzazione da adempiere per poter revocare i certificati, ad esempio l'esecuzione di un backup.
  
Esiste inoltre un'ampia varietà di parametri tecnici che regolamentano la revoca dei certificati, che è necessario includere nel criterio della CA.
  
In questa guida, i parametri riportati nelle tabelle seguenti sono destinati alle CA principali e di emissione.
  
**Tabella 17. Parametri di revoca dei certificati della CA principale**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Parametro</th>
<th>Valore prescelto</th>
<th>Motivo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Posizioni pubblicazioni CRL (CDP)</td>
<td style="border:1px solid black;">Percorso LDAP al contenitore CDP di Active Directory</td>
<td style="border:1px solid black;">La pubblicazione a tutti i controller di dominio (DC, Domain Controller) consente un accesso in locale facilitato a tutti gli utenti del dominio.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Percorso HTTP al server Web interno</td>
<td style="border:1px solid black;">La pubblicazione in un server Web consente di eseguire il backup del percorso LDAP e ai client non LDAP di accedere all'elenco CRL.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Tipo di CRL</td>
<td style="border:1px solid black;">Solo Base CRL</td>
<td style="border:1px solid black;">A causa del ridotto numero di certificati emessi, l'utilizzo di Delta CRL.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pianificazione pubblicazione</td>
<td style="border:1px solid black;">Sei mesi</td>
<td style="border:1px solid black;">Poiché tale procedura renda difficile la revoca dei certificati CA, l'impostazione del livello di protezione della CA richiede una certa attendibilità. Tuttavia, un periodo di tempo così esteso limita al minimo la gestione della CA principale.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo di sovrapposizione degli elenchi CRL, ovvero l'intervallo di tempo compreso tra la pubblicazione di un nuovo elenco CRL e la scadenza di un elenco CRL obsoleto.</td>
<td style="border:1px solid black;">10 giorni</td>
<td style="border:1px solid black;">Questa procedura prevede un margine di errore utilizzabile per il recupero del nuovo elenco CRL dalla CA principale.</td>
</tr>
</tbody>
</table>
  
**Tabella 18. Parametri di revoca dei certificati della CA di emissione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Parametro</th>
<th>Valore prescelto</th>
<th>Motivo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Posizioni pubblicazioni CRL (CDP)</td>
<td style="border:1px solid black;">Percorso LDAP al contenitore CDP di Active Directory, per gli elenchi CRL Base e Delta.</td>
<td style="border:1px solid black;">La pubblicazione in tutti i controller di dominio consente un accesso in locale facilitato a tutti gli utenti del dominio.<br />
Vedere la nota seguente relativa alla pubblicazione di CRL delta in Active Directory.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Percorso HTTP al server Web interno</td>
<td style="border:1px solid black;">La pubblicazione in un server Web consente di eseguire il backup del percorso LDAP e ai client non LDAP di accedere all'elenco CRL.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Tipo di CRL</td>
<td style="border:1px solid black;">Base CRL<br />
Delta CRL</td>
<td style="border:1px solid black;">Gli elenchi Delta CRL sono utili per ottimizzare il traffico di recupero degli elenchi CRL, offrendo un minimo intervallo di latenza prima della pubblicazione delle informazioni di revoca.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Pianificazione pubblicazione</td>
<td style="border:1px solid black;">Base CRL: sette giorni</td>
<td style="border:1px solid black;">Tale intervallo dovrà essere sufficientemente frequente da consentire ai sistemi che non riconoscono gli elenchi Delta CRL, di ricevere comunque informazioni di revoca relativamente aggiornate.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;">Delta CRL: un giorno</td>
<td style="border:1px solid black;">Per i client moderni, in grado di utilizzare gli elenchi Delta CRL, tale procedura offre un intervallo di latenza relativamente ridotto.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Periodo di sovrapposizione degli elenchi Base CRL, ovvero l'intervallo compreso tra la pubblicazione di un nuovo elenco CRL e la scadenza di un elenco CRL obsoleto</td>
<td style="border:1px solid black;">Quattro giorni</td>
<td style="border:1px solid black;">Questa procedura prevede un margine di errore utilizzabile per il recupero della CA, in caso quest'ultima non sia in grado di pubblicare un elenco Base CRL nei tempi prestabiliti. È stato prescelto un valore pari a quattro giorni prevedendo il caso limite di un arresto anomalo della CA durante un venerdì sera e della successiva individuazione il martedì successivo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Periodo di sovrapposizione degli elenchi Delta CRL</td>
<td style="border:1px solid black;">Un giorno</td>
<td style="border:1px solid black;">Poiché gli elenchi Delta CRL non sono fondamentali per il funzionamento del servizio, eventuali errori durante la pubblicazione di un elenco Delta CRL non determinano un evento catastrofico. Questo valore viene impostato in modo che si sovrapponga alla latenza della replica di Active Directory.</td>
</tr>
</tbody>
</table>
  
**Nota:** poiché vengono utilizzati elenchi Delta CRL con una durata relativamente ridotta (un giorno), è necessario assicurarsi che il valore massimo di latenza della replica di Active Directory sia inferiore al 50 per cento del periodo di pubblicazione dell'elenco Delta CRL. In caso contrario potrebbe verificarsi che i client dei certificati utilizzino informazioni di revoca non aggiornate o che il traffico dati legato alla replica delle directory verso siti a larghezza di banda limitata, subisca un rallentamento. È necessario impostare il periodo di sovrapposizione degli elenchi Delta CRL su un valore superiore al tempo massimo impiegato per la replica delle informazioni relative alle directory attraverso l'insieme di strutture.
  
Se la latenza di Active Directory supera questo valore o se si desidera evitare la generazione di tale traffico dati, è necessario aumentare il periodo di pubblicazione degli elenchi Delta CRL o evitare la pubblicazione degli elenchi Delta CRL nella directory. Se si modificano le posizioni degli elenchi CRL, sarà necessario emettere un nuovo elenco Base CRL.
  
#### Pianificazione del ripristino di chiavi e dati
  
Le procedure di ripristino delle chiavi e dei dati non rientrano negli obiettivi della presente guida. Nel caso si presenti la necessità di attuare le procedure sopra indicate, sarà necessario effettuarne una pianificazione e una gestione accurata per evitare la perdita di dati e la divulgazione accidentale dei dati crittografati.
  
Per ulteriori informazioni sull'argomento, leggere la sezione "Planning for Data Recovery and Key Recovery" del capitolo "Designing a Public Key Infrastructure" nel *Resource Kit* e l'omonimo white paper tecnico di Microsoft di prossima pubblicazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo modulo viene illustrata la procedura di progettazione di un'infrastruttura PKI per una soluzione di rete LAN senza fili protetta. Considerando la probabilità con cui verrà utilizzata per altre applicazioni, nella progettazione dell'infrastruttura PKI si è tenuto conto di tale problema. La proposta di progettazione riportata nella presente guida è sufficientemente flessibile da essere estesa a requisiti futuri. Se la procedura di progettazione è stata seguita attentamente, sarà possibile implementare un'infrastruttura PKI sufficientemente protetta e adeguatamente gestita da soddisfare criteri di protezione più rigidi inclusi in tali requisiti.
  
Le decisioni relative alla progettazione descritte nella presente guida verranno utilizzate nella *Guida all'implementazione* e nella *Guida operativa* per l'implementazione dell'infrastruttura PKI.
  
Nei moduli rimanenti della presente *Guida alla pianificazione* viene spiegato come progettare gli altri componenti principali indicati: l'infrastruttura RADIUS, implementata tramite il Servizio di Autenticazione Internet (IAS), e l'infrastruttura di protezione della rete LAN senza fili.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Ulteriori informazioni
  
In questo modulo viene mutuata una considerevole quantità di informazioni dal capitolo "Designing a Public Key Infrastructure" del *Resource Kit*. Poiché la struttura di entrambi i documenti è simile, è possibile fare riferimento alle informazioni generali pertinenti contenute nel capitolo del *Resource Kit*, disponibile all'indirizzo: [http://go.microsoft.com/fwlink/?LinkId=4735](http://go.microsoft.com/fwlink/?linkid=4735) (in inglese).
  
-   Per un'introduzione generale al concetto di PKI e all'utilizzo dei Servizi certificati in Windows 2000, vedere *An Introduction to the Windows 2000 Public-Key Infrastructure*, all'indirizzo: <http://technet.microsoft.com/en-us/library/cc768063.aspx> (in inglese).
  
-   Per una descrizione dettaglia sulle funzionalità avanzate dell'infrastruttura PKI in Windows Server 2003 e Windows XP, vedere *PKI Enhancements in Windows XP Professional and Windows Server 2003*, all'indirizzo: <http://technet.microsoft.com/en-us/library/bb457034.aspx> (in inglese).
  
-   Nella documentazione di Windows 2003 Server Enterprise Edition vengono illustrati i concetti chiave e le attività di gestione dei Servizi certificati. La documentazione è disponibile sul sito Internet all'indirizzo: <http://technet.microsoft.com/en-us/library/cc768063.aspx> (in inglese).
  
-   Per ulteriori informazioni sulla creazione di una dichiarazione delle procedure di certificazione, vedere il documento RFC2527, all'indirizzo: <http://www.ietf.org/rfc/rfc2527.txt> (in inglese).
  
-   Per alcuni esempi di dichiarazioni CPS, vedere [http://www.verisign.com/repository/CPS/](http://www.verisign.com/repository/cps/) (in inglese).
  
-   Per una spiegazione dettagliata sulle differenze tra le CA versione Enterprise e autonome, vedere la sezione seguente all'interno della documentazione relativa ai Servizi certificati: [http://technet.microsoft.com/en-us/library/bb457034.aspx](http://www.microsoft.com/technet/treeview/default.asp?url=/technet/prodtechnol/windowsserver2003/proddocs/entserver/sag_cscas.asp) (in inglese).
  
-   Per ulteriori informazioni sull'abilitazione dell'accesso LDAP anonimo in Windows Server 2003, vedere l'articolo Q326690 della Microsoft Knowledge Base all'indirizzo: <http://support.microsoft.com/default.aspx?scid=326690> (in inglese).
  
-   Per informazioni dettagliate sulla revoca dei certificati, vedere *Troubleshooting Certificate Status and Revocation*, all'indirizzo: <http://technet.microsoft.com/en-us/library/cc700843.aspx> (in inglese). La sezione relativa alle estensioni CDP si ricollega in particolar modo ad alcuni concetti presentati in questo modulo.
  
-   Per ulteriori informazioni sull'installazione e sull'utilizzo delle pagine di registrazione Web dei Servizi certificati, vedere il sito Internet all'indirizzo: [http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/server/sag\_CSprocsInstallWebClient.asp](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/server/sag_csprocsinstallwebclient.asp) (in inglese).
  
-   Le descrizioni di tutti i modelli incorporati sono reperibili all'interno della documentazione di Windows Server 2003 Enterprise Edition. <http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/ctcon_tshoot.asp> (in inglese).
  
[](#mainsection)[Inizio pagina](#mainsection)
