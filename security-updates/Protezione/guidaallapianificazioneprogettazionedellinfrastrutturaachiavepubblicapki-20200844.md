---
TOCTitle: 'Guida alla pianificazione - Progettazione dell’infrastruttura a chiave pubblica (PKI)'
Title: 'Guida alla pianificazione - Progettazione dell’infrastruttura a chiave pubblica (PKI)'
ms:assetid: 'e120bd92-b1e8-41e2-91a9-55953fb40348'
ms:contentKeyID: 20200844
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536245(v=TechNet.10)'
---

Capitolo 4: Progettazione dell’infrastruttura a chiave pubblica (PKI)
=====================================================================

Pubblicato: 11 ottobre 2004 | Aggiornato: 24/11/04

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Definizione dei requisiti del certificato](#eeaa)
[](#edaa)[Progettazione della gerarchia dell’Autorità di certificazione](#edaa)
[](#ecaa)[Configurazione dei profili di certificati](#ecaa)
[](#ebaa)[Creazione di un piano per la gestione dei certificati](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

Nel capitolo precedente è stata descritta una progettazione logica per una soluzione senza fili protetta basata su un'infrastruttura a chiave pubblica (PKI). In questo capitolo viene descritto il processo di progettazione di un'infrastruttura PKI basata su Servizi certificati Microsoft® Windows® 2003 per tale soluzione. Al fine di contenere i costi di distribuzione e gestione, viene presa in esame una configurazione semplice che si adatta facilmente alla procedura di rilascio di certificati per client di reti senza fili protette e infrastrutture WLAN (Wireless Local Area Network).

Sebbene l'obiettivo principale sia progettare un'infrastruttura PKI in grado di supportare la protezione per le reti WLAN, tenere presente che tale infrastruttura gioca un ruolo importante anche nell'infrastruttura di protezione globale e che in futuro sarà possibile utilizzarla con numerose altre applicazioni dell'ambiente. Per proteggere gli investimenti sostenuti per l’infrastruttura, la configurazione descritta di seguito è di tipo espandibile. Ciò significa che, sebbene la progettazione non sia in grado di rilasciare qualsiasi tipo di certificato, consente tuttavia l’aggiunta di ulteriori funzionalità, che in futuro permetteranno di fare fronte a un più ampio set di requisiti di protezione rispetto a quelli descritti nel presente capitolo.

Gli obiettivi principali del presente capitolo sono tre. Il primo consiste nella discussione delle decisioni relative alla progettazione della soluzione e le motivazioni di tali scelte. Il secondo consiste nel fornire all'utente alcune informazioni di base relative alla progettazione per consentirgli di scegliere l'infrastruttura PKI più adatta alle proprie esigenze. Il terzo consiste nell'indicare le modalità con cui è possibile estendere la soluzione di base per soddisfare esigenze di protezione che non rientrano nell'ambito di tale guida.

Frasi quali “Questa soluzione utilizza l'opzione...” o “Questa progettazione utilizza...” presenti nel capitolo si riferiscono a decisioni che fanno parte della progettazione della soluzione, implementate nei capitoli relativi alla Guida alla creazione o alla Guida operativa della soluzione.

Frasi quali “È necessario decidere...” indicano invece elementi per i quali è necessario prendere decisioni in base alle proprie esigenze. In genere, questi casi si trovano in parti di testo nelle quali viene discusso come estendere la soluzione per soddisfare le maggiori esigenze di protezione della propria organizzazione. Alcuni argomenti offrono quindi informazioni più dettagliate che consentono di comprendere tutte le implicazioni delle scelte a disposizione, rendendo superfluo il ricorso a ulteriori documenti.

#### Prima di iniziare

È necessario avere una buona conoscenza dei principi di base e della terminologia relativa all'infrastruttura PKI. Se non si è esperti, fare riferimento agli articoli elencati nella sezione “Ulteriori informazioni” alla fine del presente capitolo.

Prima di continuare, è necessario conoscere il contenuto del capitolo “Designing a Public Key Infrastructure” incluso nel *Microsoft Windows Server*™ *2003 Deployment Kit*. Per maggiori dettagli su dove reperire queste informazioni, vedere la sezione "Ulteriori informazioni" alla fine del presente capitolo. Il presente capitolo segue la struttura del capitolo “Designing a Public Key Infrastructure” del Deployment Kit per semplificare il riferimento alle informazioni di base e alle descrizioni dettagliate pertinenti qui contenute.

Nella sezione "Ulteriori informazioni" sono disponibili anche i collegamenti a informazioni aggiuntive relative alla pianificazione e alla progettazione di un'infrastruttura PKI di Windows Server 2003.

#### Panoramica dei capitoli

La pianificazione e la distribuzione di un'infrastruttura PKI in grado di soddisfare le esigenze presenti e future di un'organizzazione non è un compito facile. Di solito, un'infrastruttura PKI non è ideata per fornire la soluzione a un unico problema di protezione, bensì per rispondere a una serie di requisiti di protezione sia interni che aziendali, nei casi di collaborazioni con clienti esterni o partner commerciali.

Nel seguente diagramma di flusso viene illustrata la struttura del capitolo.

![](images/Dd536245.04fig4-1(it-it,TechNet.10).gif)

**Figura 4.1. Struttura del capitolo per la pianificazione di Servizi certificati**

Le quattro procedure principali sono:

-   **Definizione dei requisiti del certificato** Questa procedura comprende l'individuazione dei problemi di protezione che si desidera risolvere. Tale procedura si basa sulle specifiche applicazioni e sugli utenti che richiedono un maggior livello di protezione, sulla posizione degli utenti e sul grado di protezione avanzata richiesto. Non è possibile iniziare a creare un'infrastruttura PKI prima di aver definito i requisiti aziendali e di protezione.

-   **Progettazione della gerarchia dell’autorità di certificazione** In base a una serie di fattori, è necessario creare un'infrastruttura di autorità di certificazione (CA). Questo passaggio prevede la definizione di un modello di trust, la determinazione del numero di CA richieste, delle modalità di gestione delle CA e delle modalità di estensione dell'infrastruttura PKI, tramite l'introduzione di CA aggiuntive o la definizione di relazioni di trust con altre organizzazioni. Inoltre, questo passaggio descrive le procedure di integrazione dell'infrastruttura PKI con altre tecnologie dell'infrastruttura IT, quali il servizio directory Active Directory® e Microsoft Internet Information Services (IIS).

-   **Configurazione dei profili di certificati** In questo passaggio è possibile decidere i tipi di certificati da utilizzare, il grado di crittografia delle chiavi associate con tali certificati, il loro periodo di validità e la possibilità di renderli rinnovabili.

-   **Creazione di un piano per la gestione dei certificati** In questo passaggio vengono descritte le modalità di emissione dei certificati agli utenti finali, le modalità di elaborazione delle richieste di certificati e le modalità di gestione e distribuzione degli elenchi di revoca certificati (CRL, Certificate Revocation List).

[](#mainsection)[Inizio pagina](#mainsection)

### Definizione dei requisiti del certificato

In questa sezione vengono definiti i motivi per il rilascio di certificati da parte dell’infrastruttura PKI e i requisiti di protezione necessari.

#### Creazione di una dichiarazione delle procedure di certificazione

Durante la progettazione di un’infrastruttura PKI è necessario registrare le decisioni su modalità di rilascio e utilizzo dei certificati all’interno dell’organizzazione. Tali decisioni vengono definite criteri di certificazione. I documenti in cui vengono registrate sono invece denominati dichiarazioni dei criteri di certificazione e dichiarazioni delle procedure di certificazione (CPS, Certificate Practice Statements).

A livello formale, i *criteri di certificazione* (CP, Certificate Policy) sono un insieme di regole con cui opera un'infrastruttura PKI. Tali criteri indicano, ad esempio, l’applicabilità di un certificato a un gruppo specifico di client o applicazioni con requisiti di protezione comuni. Una *dichiarazione* delle *procedure* di *certificazione* (CPS) invece riguarda le procedure utilizzate all’interno di un’organizzazione per gestire il rilascio di certificati. Tale dichiarazione contiene la descrizione di come vengono interpretati i criteri di certificazione nel contesto delle procedure operative e dell'architettura di sistema aziendali. Un documento CP è destinato all'intera organizzazione. Una dichiarazione CPS, invece, è specifica per una CA, sebbene le CA possano disporre di una CPS comune se eseguono gli stessi processi, ad esempio nel caso si distribuisca il carico CA su più server per ragioni di prestazioni o capacità di recupero.

In alcune organizzazioni e in specifici utilizzi di certificati, le dichiarazioni dei criteri e delle procedure di certificazione sono considerate documenti o dichiarazioni di non responsabilità con valore legale. In questo caso è generalmente necessario avvalersi di una consulenza legale specializzata, pertanto tale argomento esula dalla presente trattazione. In ogni caso, tali documenti non sono indispensabili per la creazione dell’infrastruttura PKI, quindi, in assenza di forti motivazioni legali o commerciali, è consigliabile evitare di investire tempo e denaro nella realizzazione e la gestione di dichiarazioni formali di procedure e criteri di certificazione.

Anche nei casi in cui non sia necessaria una dichiarazione CP o CPS formale, è bene documentare i criteri di certificazione e le procedure operative. Da un lato i criteri di certificazione devono diventare parte integrante dei criteri di protezione generali adottati dall’organizzazione, dall’altro le procedure operative devono essere incluse tra le procedure per la gestione della protezione. Sarà possibile fare riferimento a questo processo come a una dichiarazione CPS informale.

In base all’utilizzo previsto per l’infrastruttura PKI, è necessario decidere se creare o meno una dichiarazione formale dei criteri e delle procedure di certificazione. Se si necessita di una dichiarazione CPS formale, sarà probabilmente necessario pubblicarla e includere i riferimenti corrispondenti nei certificati CA. Sebbene in questa guida non sia inclusa alcuna indicazione su come realizzare una dichiarazione CPS formale, istruzioni sulla pubblicazione sono disponibili nel capitolo 7, “Implementazione dell’infrastruttura a chiave pubblica”. Le dichiarazioni CPS informali invece non necessitano generalmente di pubblicazione.

Nella parte restante di questo capitolo viene spesso fatto riferimento alla documentazione di decisioni adottate in merito alle dichiarazioni CPS. Tali istruzioni sono ugualmente valide per dichiarazioni CPS formali e informali.

Per ulteriori informazioni sulla produzione di dichiarazioni CPS, consultare la sezione “Ulteriori informazioni” alla fine di questo capitolo.

#### Identificazione delle applicazioni dei certificati

Il primo passaggio del processo di progettazione di un’infrastruttura PKI consiste nell’identificare le applicazioni in cui verranno utilizzati i certificati. Per ogni applicazione è necessario documentare i tipi e il numero approssimativo di certificati necessari. In questa fase non viene richiesto di specificare alcun dettaglio sul certificato, ma solo di fornirne una breve descrizione.

Per la soluzione senza fili protetta è necessario disporre di certificati per client senza fili e per server RADIUS (Remote Authentication Dial-In User Service) Windows. Il server RADIUS di Microsoft è un componente di Windows Server, chiamato Servizio autenticazione Internet (IAS, Internet Authentication Service).

I tipi di certificato richiesti vengono illustrati nella tabella riportata di seguito. Sebbene non sia effettivamente necessario per questa soluzione, l’infrastruttura PKI consente inoltre di rilasciare certificati ai controller di dominio (impostazione predefinita quando viene installata una CA Windows 2003 Enterprise nell’insieme di strutture).

**Tabella 4.1. Requisiti dei certificati per la soluzione senza fili protetta**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Applicazione</p></th>
<th><p>Tipo di certificato</p></th>
<th><p>Numero di certificati</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>WLAN protetta</p></td>
<td style="border:1px solid black;"><p>Certificati di autenticazione client per utenti.</p></td>
<td style="border:1px solid black;"><p>Tutti gli utenti che richiedono l’accesso a WLAN.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Certificati di autenticazione client per computer.</p></td>
<td style="border:1px solid black;"><p>Tutti i computer della rete LAN senza fili.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Certificati di autenticazione server per i server IAS.</p></td>
<td style="border:1px solid black;"><p>Tutti i server IAS.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Active Directory</p></td>
<td style="border:1px solid black;"><p>Autenticazione del controller di dominio.</p></td>
<td style="border:1px solid black;"><p>Tutti i controller di dominio nell’insieme di strutture.</p></td>
</tr>  
</tbody>  
</table>
  
In futuro sarà possibile utilizzare l’infrastruttura PKI per il rilascio di certificati relativi alle applicazioni indicate nelle tabelle riportate di seguito.
  
**Tabella 4.2. Potenziali requisiti di certificati futuri**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Applicazione</p></th>  
<th><p>Tipo di certificato</p></th>  
<th><p>Numero di certificati</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Rete privata virtuale (VPN) per accesso client</p></td>
<td style="border:1px solid black;"><p>Autenticazione computer client (IPsec)</p></td>
<td style="border:1px solid black;"><p>Tutti i client VPN remoti</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>VPN branch-to-branch</p></td>
<td style="border:1px solid black;"><p>Autenticazione server VPN (IPsec)</p></td>
<td style="border:1px solid black;"><p>Tutti i router VPN</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Protezione IP (IPsec)</p></td>
<td style="border:1px solid black;"><p>Autenticazione computer client</p></td>
<td style="border:1px solid black;"><p>Tutti i computer client e server che richiedono IPsec.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Protezione Web</p></td>
<td style="border:1px solid black;"><p>Autenticazione utenti di applicazioni Web della rete Intranet.</p></td>
<td style="border:1px solid black;"><p>Tutti gli utenti</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Server Web della rete Intranet</p></td>
<td style="border:1px solid black;"><p>Server Web della rete Intranet protetta</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Crittografia file system (EFS)</p></td>
<td style="border:1px solid black;"><p>Utente di EFS</p></td>
<td style="border:1px solid black;"><p>Tutti gli utenti</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Ripristino dei dati EFS</p></td>
<td style="border:1px solid black;"><p>Agenti di ripristino</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Posta elettronica protetta</p></td>
<td style="border:1px solid black;"><p>Firma e crittografia di Secure/Multipurpose Internet Mail Extensions (S/MIME)</p></td>
<td style="border:1px solid black;"><p>Tutti gli utenti di posta elettronica</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Ripristino di chiavi</p></td>
<td style="border:1px solid black;"><p>Agenti di ripristino</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Smart card</p></td>
<td style="border:1px solid black;"><p>Accesso con smart card</p></td>
<td style="border:1px solid black;"><p>Domain users</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Firma del codice</p></td>
<td style="border:1px solid black;"><p>Firma macro e codice interno</p></td>
<td style="border:1px solid black;"><p>Responsabile del rilascio del codice</p></td>
</tr>  
</tbody>  
</table>
  
#### Definizione dei client dei certificati
  
È necessario definire i client che utilizzeranno i certificati relativi alle applicazioni indicati nella sezione precedente. In questo contesto con il termine “client" si intende qualsiasi utente, processo software o dispositivo che utilizza i certificati rilasciati dall’infrastruttura PKI, ad esempio utenti, server, workstation e dispositivi di rete. Per comprendere le modalità di rilascio e utilizzo dei certificati all’interno dell’organizzazione, è necessario tenere in considerazione due principali categorie di client: il soggetto certificato (o *entità finale*) e altri utenti del certificato.
  
Le entità finali sono i client ai quali viene rilasciato un certificato mediante l’infrastruttura PKI. Nei campi **Oggetto** o **Nome alternativo oggetto** del certificato sono presenti una o più voci con cui è possibile identificare il client (ad esempio, un nome host, un indirizzo di posta elettronica o un nome distinto della directory) come proprietario del certificato. All'altra categoria di utenti dei certificati, invece, appartengono i client che necessitano di verificare, ad esempio, i certificati di entità finali o di individuarli in una directory, ma ai quali non vengono necessariamente rilasciati certificati dall'infrastruttura PKI.
  
Questa distinzione può essere illustrata dal seguente esempio: se un utente Internet effettua acquisti su un sito Web protetto diventa un utente del certificato SSL (Secure Sockets Layer) del sito. Il sito Web è quindi un'entità finale del certificato: la sua identità (www.woodgrovebank.com) è codificata nel campo **Oggetto** del certificato. Tra tutti gli utenti del certificato, solo il soggetto del certificato può utilizzare la chiave privata del certificato. Nota: i *soggetti* del certificato sono quasi sempre *utenti* del proprio certificato e, spesso, anche dei certificati degli altri.
  
**Nota:** “entità finale” è il termine tecnicamente corretto, ma nel capitolo verrà spesso usato il termine più descrittivo “soggetto del certificato”.
  
Sia per i soggetti che per gli utenti dei certificati, è necessario classificare ciascun tipo di client rispondendo alle seguenti domande:
  
-   Il client è una persona, un computer, un dispositivo o un processo software?
  
-   Su quali piattaforme (versione del sistema operativo) verranno utilizzati i certificati?
  
-   Qual è il percorso di rete del client? Esiste, ad esempio, una connessione alla rete LAN interna, a un’organizzazione partner o a Internet?
  
-   Il client è un membro del dominio? In caso affermativo, si trova in un dominio o in un insieme di strutture differente rispetto alla CA? Si trova in un dominio non attendibile?
  
-   Quale tipo di operazioni deve eseguire il client? Ad esempio, registrare certificati, firmare certificati, verificare trust dei certificati, individuare certificati in una directory e verificare lo stato di revoca dei certificati.
  
Questa categorizzazione si ripercuoterà su numerose decisioni relative alla progettazione, quali la modalità di rilascio del certificato, il livello di affidabilità che è possibile stabilire per un certificato specifico e la modalità di pubblicazione delle informazioni relative alla revoca dei certificati.
  
Le categorie di client disponibili in questa guida vengono descritte in dettaglio nella tabella che segue.
  
**Tabella 4.3. Categorie dei soggetti dei certificati (entità finali)**
  
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
<th><p>Certificato</p></th>  
<th><p>Tipo di client</p></th>  
<th><p>Piattaforma</p></th>  
<th><p>Ubicazione</p></th>  
<th><p>Dominio</p></th>  
<th><p>Operazioni relative ai certificati</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazione client senza fili</p></td>
<td style="border:1px solid black;"><p>User</p></td>
<td style="border:1px solid black;"><p>Windows XP</p></td>
<td style="border:1px solid black;"><p>Rete interna</p></td>
<td style="border:1px solid black;"><p>Membro di dominio</p></td>
<td style="border:1px solid black;"><p>-registrazione</p>
<p>–autenticazione</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Autenticazione client senza fili</p></td>
<td style="border:1px solid black;"><p>Autenticazione</p></td>
<td style="border:1px solid black;"><p>Windows XP</p></td>
<td style="border:1px solid black;"><p>Rete interna</p></td>
<td style="border:1px solid black;"><p>Membro di dominio</p></td>
<td style="border:1px solid black;"><p>-registrazione</p>
<p>–autenticazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazione server IAS</p></td>
<td style="border:1px solid black;"><p>Autenticazione</p></td>
<td style="border:1px solid black;"><p>Microsoft Windows Server™ 2003</p></td>
<td style="border:1px solid black;"><p>Rete interna</p></td>
<td style="border:1px solid black;"><p>Membro di dominio</p></td>
<td style="border:1px solid black;"><p>-registrazione</p>
<p>–autenticazione</p>
<p>–canale protetto</p></td>
</tr>
</tbody>
</table>
<p> </p>

In questa applicazione, gli utenti dei certificati saranno rappresentati dallo stesso set di client ma con ruoli invertiti. Il server IAS, ad esempio, diventa l’utente dei certificati del client che deve eseguire la verifica. In genere, la verifica riguarda il corretto collegamento a una CA principale attendibile e la corrispondenza tra la firma fornita dal client e la chiave pubblica presente nel certificato del client. Il certificato può anche essere soggetto a un controllo delle revoche. Per una descrizione dettagliata dell'argomento, vedere il documento *Troubleshooting Certificate Status and Revocation.* Per un elenco completo di riferimenti relativi all'argomento, vedere* *la sezione “Ulteriori informazioni” alla fine di questo capitolo.

**Tabella 4.4. Categorie degli utenti dei certificati**

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
<th><p>Certificato</p></th>
<th><p>Tipo di client</p></th>
<th><p>Piattaforma</p></th>
<th><p>Ubicazione</p></th>
<th><p>Dominio</p></th>
<th><p>Operazioni relative ai certificati</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazione client senza fili</p></td>
<td style="border:1px solid black;"><p>–Computer</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
<td style="border:1px solid black;"><p>Rete interna</p></td>
<td style="border:1px solid black;"><p>Membro di dominio</p></td>
<td style="border:1px solid black;"><p>–verifica</p>
<p>–controllo revoca</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Autenticazione client senza fili</p></td>
<td style="border:1px solid black;"><p>–Computer</p></td>
<td style="border:1px solid black;"><p>Windows Server 2003</p></td>
<td style="border:1px solid black;"><p>Rete interna</p></td>
<td style="border:1px solid black;"><p>Membro di dominio</p></td>
<td style="border:1px solid black;"><p>–verifica</p>
<p>–controllo revoca</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazione server IAS</p></td>
<td style="border:1px solid black;"><p>–Utente</p>
<p>–Computer</p></td>
<td style="border:1px solid black;"><p>Windows XP</p></td>
<td style="border:1px solid black;"><p>Rete interna</p></td>
<td style="border:1px solid black;"><p>Membro di dominio</p></td>
<td style="border:1px solid black;"><p>–verifica</p></td>
</tr>  
</tbody>  
</table>
  
La tabella precedente consente di identificare le piattaforme e il tipo di operazioni da supportare. Sebbene non sia il caso di questo scenario WLAN, per altre applicazioni dell'ambiente può risultare necessario il supporto di ricerche o verifiche di certificati per mezzo di client su Internet   o la registrazione da piattaforme non Windows. Poiché molti di questi aspetti devono essere decisi durante la fase iniziale del processo di progettazione, è importante individuare sin dall’inizio i potenziali requisiti dei certificati futuri.
  
Per quanto riguarda i requisiti futuri, in questa guida si presuppone quanto segue:
  
-   Sarà probabilmente necessaria la verifica dei certificati da client non Windows.
  
-   Sarà probabilmente necessaria la verifica dei certificati da Internet.
  
-   Sarà probabilmente necessario il supporto dei soggetti e degli utenti dei certificati su piattaforme diverse da Windows XP e Windows Server 2003.
  
Sebbene al momento la progettazione non soddisfi necessariamente tutti questi requisiti, sarà comunque possibile includerli facilmente.
  
#### Definizione dei requisiti di protezione dei certificati
  
La protezione di un certificato viene anche definita livello di garanzia e può essere considerata un punto di forza tra il soggetto certificato e il certificato stesso. Rappresenta inoltre il grado di certezza che la persona (o il dispositivo) che utilizza il certificato corrisponda realmente al soggetto indicato nel certificato. Il livello di garanzia è costituito da due aspetti principali:
  
-   Il rigore della registrazione e del processo di registrazione dei certificati. All’utente ad esempio viene richiesto di presentarsi di persona con un documento di identificazione per ottenere il certificato oppure è sufficiente disporre di un indirizzo di posta elettronica.
  
-   Il modo in cui viene archiviata la chiave privata: più è difficile copiare o compromettere la chiave, maggiore è la garanzia che essa sia in possesso del proprietario originale, ovvero il soggetto certificato.
  
Questi due aspetti sono strettamente correlati in quanto non esiste alcun motivo valido per sostenere costi onerosi per l’adozione di misure di protezione della chiave privata, se non si può essere certi dell’identità del proprietario della chiave privata. Allo stesso modo, un processo di registrazione complicato, che comprende approfonditi controlli in background e la rilevazione delle impronte digitali genetiche, è praticamente inutile senza un’adeguata e sicura archiviazione della chiave privata.
  
Il raggiungimento tuttavia di un elevato grado di protezione per un certificato comporta costi onerosi e spesso può risultare superfluo per diversi utilizzi dei certificati. Se non si desidera ottenere un elevato livello di garanzia per un certificato, è possibile far parte di un dominio autorizzato, in cui le credenziali del dominio vengono accettate come prova della registrazione di un certificato.
  
È necessario documentare lo scopo dei livelli di garanzia che vengono utilizzati nei criteri e nelle dichiarazioni sulle procedure di certificazione.
  
In questa guida vengono definiti i tre livelli di garanzia riportati nella tabella seguente.
  
**Tabella 4.5. Livelli di garanzia dei certificati**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Livello</p></th>  
<th><p>Requisiti di registrazione</p></th>  
<th><p>Requisiti di archiviazione della chiave</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Standard</p>
<p>(Basso)</p></td>
<td style="border:1px solid black;"><p>Approvazione automatica a seconda del dominio o altra password per l’identificazione.</p></td>
<td style="border:1px solid black;"><p>Chiavi software</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Medio</p></td>
<td style="border:1px solid black;"><p>Approvazione del responsabile certificati, controllo ID visivo (smart card) o firma del responsabile della registrazione.</p></td>
<td style="border:1px solid black;"><p>Chiavi software o token hardware a prova di manomissione (smart card o token USB).</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Alto</p></td>
<td style="border:1px solid black;"><p>Firma del responsabile della registrazione e approvazione del responsabile certificati.</p></td>
<td style="border:1px solid black;"><p>Token hardware a prova di manomissione (smart card o token USB).</p></td>
</tr>  
</tbody>  
</table>
  
Le categorie presentano delle sovrapposizioni. Non si tratta di differenze strettamente tecniche, ma di differenze sui criteri, dovute alle decisioni adottate per gestire i certificati all’interno dell’organizzazione. In generale, i certificati con garanzia elevata sono decisamente poco frequenti, mentre risultano essere molto comuni i certificati con garanzia standard.
  
**Importante:** in questo capitolo, in riferimento ai certificati vengono utilizzate le espressioni "valore standard" e "garanzia standard" invece di "valore basso" e "garanzia bassa", poiché questi ultimi sono connotati negativamente, mentre "standard" riflette più precisamente il significato desiderato.
  
Le categorie di garanzia definite nella tabella precedente possono essere suddivise ulteriormente in tipi di soggetti differenti. Le categorie più comuni sono:
  
-   Computer: qualsiasi computer o dispositivo all’interno dell’organizzazione.
  
-   Utente interno: i dipendenti o il personale a tempo pieno con qualifica equivalente (ad esempio, i collaboratori).
  
-   Utente esterno: qualsiasi altra entità esterna all’organizzazione  con la quale è in corso una collaborazione di tipo commerciale o legale (ad esempio, partner e clienti commerciali).
  
Il motivo di una simile distinzione consiste nel fatto che tipi differenti di soggetto adottano generalmente criteri diversi per i certificati, ovvero le condizioni che regolano il rilascio, la revoca o il rinnovo di un certificato. Anche se non si dispone di piani specifici per una determinata categoria, è possibile documentare i criteri sui certificati che possono essere applicati a tale categoria affinché sia possibile preparare correttamente i criteri e le dichiarazioni CPS. Nella tabella seguente vengono descritti i risultati ottenuti dalla combinazione dei livelli di garanzia con le categorie di soggetti.
  
**Tabella 4.6. Categorie di protezione dei certificati**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Categoria di protezione dei certificati</p></th>  
<th><p>Caratteristiche di esempio della categoria di protezione</p></th>  
<th><p>Tipi di certificato di esempio</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><strong>Certificati di computer</strong></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Certificati di computer con garanzia standard</p></td>
<td style="border:1px solid black;"><p>–Approvazione automatica basata sulle credenziali di dominio del computer.</p>
<p>–Rinnovo annuale.</p></td>
<td style="border:1px solid black;"><p>–Computer WLAN</p>
<p>–IPsec</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Certificati di computer con garanzia media</p></td>
<td style="border:1px solid black;"><p>–Approvazione del responsabile certificati obbligatoria.</p>
<p>–Archiviazione della chiave nel software.</p>
<p>–Rinnovo annuale.</p></td>
<td style="border:1px solid black;"><p>–Server Web</p>
<p>–Autenticazione server IAS</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Certificati di computer con garanzia elevata</p></td>
<td style="border:1px solid black;"><p>–Approvazione del responsabile certificati.</p>
<p>–Archiviazione della chiave nel modulo HSM (Hardware Security Module).</p></td>
<td style="border:1px solid black;"><p>–Autorità di certificazione</p>
<p>–Servizio orario protetto</p>
<p>–Autorità di registrazione</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Certificati per utenti interni</strong></td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Certificati per utenti interni con garanzia standard</p></td>
<td style="border:1px solid black;"><p>–Approvazione automatica basata sulle credenziali di dominio dell'utente.</p>
<p>–Rinnovo annuale.</p></td>
<td style="border:1px solid black;"><p>Utente di EFS</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Certificati per utenti interni con garanzia media</p></td>
<td style="border:1px solid black;"><p>–Approvazione del responsabile certificati o del responsabile della registrazione obbligatoria.</p>
<p>–Archiviazione della chiave su smart card o software.</p>
<p>–Rinnovo annuale.</p></td>
<td style="border:1px solid black;"><p>–Posta elettronica protetta</p>
<p>–Autorizzazione finanziaria di basso valore</p>  
<p>–Accesso con smart card</p>  
<p>–Firma codice interno</p>  
<p>–Agente di ripristino dati</p>
<p>–Agente di ripristino chiavi</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Certificati per utenti interni con garanzia elevata</p></td>
<td style="border:1px solid black;"><p>–Verifica ID fisico del soggetto certificato obbligatoria.</p>
<p>–Approvazione del responsabile certificati obbligatoria.</p>  
<p>–Firma dell’ufficio di registrazione su richiesta.</p>  
<p>–Archiviazione della chiave su smart card.</p>
<p>–Rinnovo a sei mesi.</p></td>
<td style="border:1px solid black;"><p>–Autorizzazione finanziaria di alto valore</p>
<p>–Firma del codice commerciale</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Certificati (utenti) esterni</td>
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><br />
</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Certificati esterni con garanzia standard</p></td>
<td style="border:1px solid black;"><p>–Approvazione automatica basata sulle password assegnate in precedenza.</p>
<p>–Rinnovo annuale.</p></td>
<td style="border:1px solid black;"><p>Autenticazione client (autenticazione al sito Web Internet)</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Certificati esterni con garanzia media</p></td>
<td style="border:1px solid black;"><p>–Approvazione del responsabile certificati obbligatoria.</p>
<p>–Archiviazione della chiave su smart card.</p>
<p>–Rinnovo a sei mesi.</p></td>
<td style="border:1px solid black;"><p>Autorizzazione finanziaria business-to-business (B2B)</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Certificati esterni con garanzia elevata</p></td>
<td style="border:1px solid black;"><p>–Verifica ID fisico del soggetto certificato obbligatoria.</p>
<p>–Approvazione del responsabile certificati obbligatoria.</p>  
<p>–Firma dell’ufficio di registrazione su richiesta.</p>  
<p>–Archiviazione della chiave su smart card.</p>
<p>–Rinnovo a sei mesi.</p></td>
<td style="border:1px solid black;"><p>Transazione B2B di valore molto elevato</p></td>
</tr>  
</tbody>  
</table>
  
**Nota:** se non si utilizza una classificazione specifica, non è necessario crearne una. Potrebbe essere necessario utilizzare un sistema di classificazione più semplice o più complesso. Inoltre, non tutte le combinazioni producono necessariamente tipi di certificato destinati alla distribuzione.
  
Benché non esistano delle ragioni tecniche per cui non sia possibile trattare allo stesso modo tipi di soggetti di certificati differenti, generalmente vengono definiti diversi criteri di protezione per tipi di soggetto differenti. I dipendenti interni ad esempio vengono trattati in maniera diversa rispetto al personale di altre organizzazioni. I diversi criteri di certificazione, e la loro inclusione in dichiarazioni CPS differenti, possono influire su come strutturare le CA per il rilascio di tipi di certificati differenti. Questo argomento verrà descritto successivamente nel presente capitolo.
  
È necessario inoltre verificare se lo stesso amministratore è in ultima analisi anche responsabile per il rilascio di certificati a queste tre categorie di utenti (o “entità finali” secondo la terminologia PKI). In numerose organizzazioni, la persona che può certificare la validità di un computer quale membro di dominio non è la stessa persona che può certificare l’identità di una società partner. Nella dichiarazione CPS è necessario pertanto stabilire queste relazioni di responsabilità.
  
##### Definizione della protezione dei certificati delle applicazioni
  
Le categorie di protezione dei certificati definite nella sezione precedente possono essere utilizzate per classificare i tipi di certificati per la progettazione, che vengono elencati nella seguente tabella.
  
**Tabella 4.7. Requisiti di protezione dei certificati**
  
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
<th><p>Tipo di certificato</p></th>  
<th><p>Categoria di protezione</p></th>  
<th><p>Piattaforma</p></th>  
<th><p>Posizione logica</p></th>  
<th><p>Approvazione</p></th>  
<th><p>Chiave</p>  
<p>Dimensioni</p></th>  
<th><p>Periodo di validità</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazione client - Utente</p></td>
<td style="border:1px solid black;"><p>Certificati di computer con garanzia standard</p></td>
<td style="border:1px solid black;"><p>–Windows XP</p>
<p>–Windows Server 2003</p></td>
<td style="border:1px solid black;"><p>Interna</p></td>
<td style="border:1px solid black;"><p>Automatico</p>
<p>(autenticazione di dominio)</p></td>
<td style="border:1px solid black;"><p>Media</p></td>
<td style="border:1px solid black;"><p>Media</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Autenticazione client - Computer</p></td>
<td style="border:1px solid black;"><p>Certificati per utenti con garanzia standard</p></td>
<td style="border:1px solid black;"><p>–Windows XP</p>
<p>–Windows Server 2003</p></td>
<td style="border:1px solid black;"><p>Interna</p></td>
<td style="border:1px solid black;"><p>Automatico</p>
<p>(autenticazione di dominio)</p></td>
<td style="border:1px solid black;"><p>Media</p></td>
<td style="border:1px solid black;"><p>Media</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazione server IAS</p></td>
<td style="border:1px solid black;"><p>Certificati di computer con garanzia media</p></td>
<td style="border:1px solid black;"><p>–Windows XP</p>
<p>–Windows Server 2003</p></td>
<td style="border:1px solid black;"><p>Interna</p></td>
<td style="border:1px solid black;"><p>Manuale</p></td>
<td style="border:1px solid black;"><p>Media</p></td>
<td style="border:1px solid black;"><p>Media</p></td>
</tr>  
</tbody>  
</table>
  
Questi requisiti generali vengono perfezionati in profili di certificati specifici nella sezione "Configurazione dei profili di certificati" più avanti in questo capitolo.
  
##### Combinazione degli scopi del certificato
  
È possibile unire una serie di funzioni dell’applicazione (o utilizzi) in un unico certificato affinché sia possibile utilizzare lo stesso certificato per firmare messaggi di posta elettronica, accedere alla rete e concedere l’accesso a un’applicazione. La combinazione di diverse funzioni comporta una riduzione del carico di gestione e archiviazione per i server di directory e certificati.
  
I certificati con diverse finalità presentano tuttavia alcuni svantaggi. Per applicazioni diverse ad esempio può rendersi necessario un processo di approvazione diverso per il certificato. Nella maggior parte dei casi, si tratta di ragioni tecniche, anche se il motivo principale è generalmente dovuto al fatto che differenti applicazioni necessitano di livelli di protezione diversi per i certificati; pertanto, diversi livelli di garanzia uniscono il certificato al soggetto certificato stesso. Le differenze possono riguardare uno o tutti i seguenti elementi:
  
-   Processo di approvazione del certificato
  
-   Lunghezza della chiave
  
-   Meccanismo di archiviazione della chiave
  
-   Durata del certificato
  
Per questo motivo, la strategia di unire gli utilizzi dei certificati dotati dello stesso livello di protezione è generalmente la migliore. Il tipo di certificati di autenticazione client utilizzato in questa guida   include utilizzi per altre applicazioni con garanzia standard, quali IPSec e autenticazione computer. Quando vengono definiti i requisiti per altri utilizzi dei certificati, è possibile includere anche tali utilizzi ed eseguire nuovamente il rilascio dei certificati; in questo caso è necessario imporre il rinnovo che può essere avviato dalla definizione del modello di certificato.
  
I certificati del server IAS sono tuttavia considerati certificati con garanzia media. Il pericolo associato a un certificato server non autorizzato è molto maggiore di quello associato a un certificato client dannoso. Per questo motivo, si consiglia di trattare i certificati server con più cautela e di non combinarli con gli utilizzi delle applicazioni con garanzia standard.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Progettazione della gerarchia dell’Autorità di certificazione
  
Per supportare le applicazioni aziendali basate sui certificati, è necessario definire una struttura di CA collegate che sarà responsabile del rilascio, della convalida, del rinnovo e della revoca dei certificati richiesti. Le autorità di certificazione, a loro volta, si avvalgono di un’infrastruttura IT sottostante per operazioni quali l’autenticazione dei soggetti dei certificati, la pubblicazione dei certificati e delle informazioni sulla revoca dei certificati.
  
L’obiettivo della creazione di un’infrastruttura CA consiste nel fornire un servizio affidabile agli utenti, una facilità di gestione agli amministratori e la flessibilità necessaria a far fronte alle esigenze attuali e future, garantendo contemporaneamente un livello di protezione ottimale per l’organizzazione.
  
#### Selezione di un modello di trust
  
La prima fase della progettazione di un’infrastruttura CA consiste nel determinare il modello di trust ottimale in base ai requisiti aziendali. I due modelli di base sono la gerarchia di trust e il trust di rete, sebbene sia possibile unire elementi di entrambi i modelli in un unico modello di trust misto. Per ulteriori informazioni su questi modelli, vedere il capitolo “Designing a Public Key Infrastructure” disponibile nella sezione "Ulteriori informazioni" nel *Windows Server 2003 Deployment Kit*.
  
La soluzione presentata nella guida utilizza il modello di gerarchia di trust per i seguenti motivi:
  
-   È possibile adottare un maggiore livello di protezione per le autorità di certificazione non in linea rispetto alle autorità in linea. La creazione di uno o più livelli di CA non in linea consente di aumentare il livello globale di trust per i certificati rilasciati.
  
-   Le gerarchie possono essere utilizzate più facilmente senza una directory, consentendo pertanto il supporto di client esterni che non hanno accesso alla directory interna. Generalmente, i trust di rete richiedono directory che consentano agli utenti di cercare certificati incrociati CA per la creazione di una catena di trust. La catena di trust nelle gerarchie è sempre esplicita.
  
-   Poiché sono disponibili pochi ancoraggi di trust da mantenere e distribuire ai client, agli utenti è necessario distribuire solo il certificato CA principale.
  
-   Anche con una gerarchia con CA principale, è sempre possibile includere più ancoraggi (o radici) di trust in futuro grazie alla certificazione incrociata con altre gerarchie. La progettazione consente pertanto di eseguire diverse operazioni, quali fusioni di organizzazioni, affidando il controllo di certificati per fini specifici ai reparti.
  
Per la soluzione proposta è sufficiente una singola CA principale.
  
##### Confronto tra CA principale di terze parti e interna
  
È possibile utilizzare una CA principale interna come ancoraggio di trust per l’infrastruttura PKI oppure i servizi di una CA commerciale. L’utilizzo di un certificato principale di terze parti implica che le CA di emissione vengono certificate dalla CA principale commerciale (di solito mediante una o più CA intermedie). Pertanto, tutti i certificati rilasciati dispongono in ultima analisi di ancoraggi di trust presso questa CA principale esterna.
  
**Nota:** sebbene questa procedura non sia considerata esplicitamente in questa guida, è possibile affidare tutti i requisiti di certificazione dell’organizzazione a una CA commerciale, utilizzando un servizio di gestione in sede oppure ottenendo i certificati direttamente dall’autorità di certificazione. Generalmente non si tratta di una procedura economicamente vantaggiosa tranne che per le piccole organizzazioni o solo per alcuni utilizzi limitati dei certificati. Questa decisione non ha alcuna relazione con l'utilizzo di un certificato interno o di un certificato principale di terze parti, sebbene queste due questioni siano spesso confuse.
  
Se si utilizza un CA principale commerciale per i certificati rilasciati internamente, si ottiene una serie di vantaggi:
  
-   Alle parti esterne (ad esempio, i clienti che visitano il sito Web protetto o un’organizzazione partner che riceve un messaggio di posta elettronica firmato) viene garantita un’elevata affidabilità durante l’esecuzione di transazioni protette con l’organizzazione. Considerando pertanto attendibile la CA principale di terze parti, non sarà necessario verificare anche l’affidabilità dei certificati.
  
-   L’organizzazione può avvalersi della competenza di un provider di servizi qualificato, che comprende anche la conoscenza degli aspetti tecnici, legali e aziendali associati all’uso del certificato. Tuttavia, a meno che tutti certificati vengano rilasciati dall’autorità di certificazione, l’utente sarà comunque responsabile delle modalità di rilascio e utilizzo dei certificati, che sarà necessario documentare nella dichiarazione CPS.
  
Un simile approccio presenta tuttavia anche numerosi svantaggi:
  
-   Generalmente comporta costi elevati per ogni certificato.
  
-   L’autorità di certificazione può richiedere rigide misure di controllo e sicurezza per tutte le CA subordinate della CA principale commerciale.
  
-   Gli utenti e le periferiche interne devono avere accesso agli elenchi CRL delle autorità di certificazione di terze parti pubblicati su Internet.
  
-   Per alcune applicazioni può rendersi necessaria la disponibilità di estensioni o parametri specifici per i certificati CA principali e intermedi (ad esempio, accesso con smart card a Microsoft Windows), non sempre disponibili presso l’autorità di certificazione.
  
-   L’accordo commerciale tra l’organizzazione e l’autorità di certificazione può limitare i tipi di certificati che è possibile rilasciare dalle CA subordinate, ad esempio i certificati server Web.
  
-   L’attendibilità di una CA principale commerciale potrebbe essere un ambito troppo vasto rispetto alle esigenze di protezione dell’organizzazione. Può rendersi necessario introdurre controlli specifici o un ulteriore livello di CA interne per distinguere i certificati rilasciati dall’organizzazione e quelli rilasciati da un’altra organizzazione, entrambe subordinate alla stessa CA principale.
  
Nonostante questi svantaggi, se si necessita di rilasciare un numero significativo di certificati che devono essere considerati attendibili da utenti esterni all’organizzazione, è consigliabile subordinare almeno una parte dell’infrastruttura PKI a una CA principale commerciale, anche se questo può comportare la creazione di due gerarchie separate.
  
In merito a questa guida, per la maggior parte dei certificati utilizzati all’interno dell’organizzazione viene utilizzata una gerarchia basata su una CA principale interna. Questo approccio offre i seguenti vantaggi:
  
-   L’organizzazione mantiene il controllo diretto sull’ancoraggio di trust centrale, ovvero la CA principale, e sui criteri di protezione che controllano il rilascio e l’utilizzo dei certificati emessi.
  
-   È possibile rilasciare una grande quantità di certificati mediante l’infrastruttura PKI interna a costi relativamente ridotti.
  
-   Non esistono limitazioni sui tipi di certificati da rilasciare.
  
-   Non esiste alcuna ambiguità tra l’affidabilità dei certificati interni ed esterni.
  
-   È possibile pubblicare le informazioni sui controlli CRL e su AIA (Accesso alle informazioni dell’autorità, Authority Information Access) sia internamente che esternamente.
  
Se la gestione delle CA principali attendibili degli utenti dei certificati è troppo complessa, si consiglia di utilizzare una CA principale esterna. Con questa soluzione, è possibile utilizzare i certificati di terze parti e una CA principale esterna per i servizi elencati di seguito:
  
-   Server Web Internet
  
-   Firma codice commerciale
  
-   Firma documento commerciale
  
-   Posta elettronica protetta con trust esterno
  
##### Definizione di trust dei certificati esterni
  
Nella sezione precedente è stata presa in considerazione l’affidabilità dell’infrastruttura di certificazione di altre organizzazioni. Tuttavia, per stabilire il grado di affidabilità dei certificati all’interno dell’organizzazione, è necessario tenere in considerazione anche altri aspetti. In questo contesto, il termine "trust" o “attendibile” assume tre condizioni specifiche:
  
-   La persona o l’entità che si ritiene attendibile.
  
-   Le operazioni o le attività per cui si ritiene attendibile una parte.
  
-   Il periodo di tempo per il quale si desidera mantenere tale affidabilità.
  
In merito ai certificati, il “soggetto” è l’autorità CA di emissione mentre “l’oggetto” sono gli utilizzi e le altre caratteristiche dei certificati che si desidera controllare. Il periodo di tempo invece consiste nel periodo di validità del certificato CA principale o, in alcuni casi, nel periodo di validità di un certificato specifico di trust incrociato da creare.
  
È possibile che sia necessario cambiare le relazioni di trust predefinite dell’organizzazione con parti esterne quando si stabilisce una nuova relazione commerciale con un’altra organizzazione o quando si desidera attivare alcune funzioni per gli utenti (ad esempio, considerare attendibili i certificati Web per consentire sessioni HTTP protette). Ad esempio, è possibile eseguire alcune delle seguenti operazioni:
  
-   Distribuire il certificato CA di un’organizzazione partner (o di una nuova autorità di certificazione commerciale) affinché alcuni o tutti gli utenti possano considerare affidabili i certificati CA commerciali o dei partner.
  
-   Distribuire il certificato CA di un’autorità CA o un’infrastruttura PKI con uno scopo speciale all’interno dell’organizzazione per il quale non si desidera stabilire una relazione di trust.
  
-   Sostituire le radici commerciali pre-esistenti nell'archivio principale dei client, affinché sia possibile limitare gli utilizzi dei certificati ritenuti affidabili. È possibile ad esempio decidere di considerare affidabili una determinata CA principale commerciale di posta elettronica e i certificati di server Web protetti, ma non i certificati di accesso con smart card.
  
Per raggiungere questi obiettivi, è possibile eseguire diverse operazioni:
  
-   Creare relazioni di subordinazione qualificata tra la CA principale interna e il certificato CA da considerare attendibili (operazione denominata anche certificazione incrociata). In questo caso, una delle CA interne deve firmare nuovamente il certificato CA esterno. Questa operazione consente di aggiungere efficacemente la CA esterna all’infrastruttura PKI interna come subordinata affidabile della CA che appone la firma. È possibile inoltre porre delle restrizioni sul tipo di certificato, limitando con precisione gli utilizzi e i criteri dei certificati, i tipi dei nomi di soggetto o i criteri di rilascio da ritenere affidabili.
  
    **Importante:** il soggetto di subordinazione qualificata o di certificazione incrociata è complesso e richiede un metodo di implementazione particolarmente difficile. Vedere il documento tecnico *Planning and Implementing Cross-Certification and Qualified Subordination Using Windows Server 2003* nella sezione “Ulteriori informazioni" alla fine di questo capitolo.
  
-   Creare un elenco dei certificati attendibili (CTL, Certificate Trust List). In questo modo viene definito un elenco delle CA principali attendibili e vengono specificati gli scopi per cui tali CA vengono considerate attendibili (ad esempio, posta elettronica protetta). Gli elenchi CTL vengono quindi distribuiti mediante gli oggetti Criteri di gruppo di Active Directory. Nonostante questo metodo sia vantaggioso, è di proprietà di Microsoft. Di conseguenza, gli elenchi CTL possono essere utilizzati solo con Windows 2000 o client successivi. Questa opzione riguarda solo i client del dominio in cui viene applicato l’oggetto Criteri di gruppo degli elenchi CTL.
  
-   Installare il certificato CA principale nell’archivio delle Autorità di certificazione attendibili di Active Directory incluso nel contenitore della configurazione. Nella CA principale e in tutte le CA subordinate viene quindi creato un trust non condizionale per tutti gli utenti e i dispositivi dell’insieme di strutture. In ogni caso si consiglia di prestare particolare attenzione prima di concedere questo tipo di trust e di utilizzarlo solo per le autorità CA sotto il controllo dell’organizzazione.
  
-   Distribuire un certificato CA principale affidabile a un sottoinsieme di utenti o computer mediante l’oggetto Criteri di gruppo. Si tratta di un’opzione simile alla precedente, che inoltre consente di specificare chi o cosa riceverà i certificati principali affidabili, ovvero gli utenti o i computer dell’oggetto Criteri di gruppo. Questa opzione riguarda solo gli utenti del dominio in cui viene applicato l’oggetto Criteri di gruppo.
  
-   Utilizzare il servizio di aggiornamento Microsoft Root Update, che consente alle autorità di certificazione commerciali di distribuire con facilità nuovi certificati principali a numerosi utenti. Si consiglia di rimuovere questo servizio da tutti i sistemi aziendali se si intende regolare le autorità CA principali affidabili.
  
-   Utilizzare l’oggetto Criteri di gruppo per disattivare i certificati principali affidabili di terze parti. A differenza di altri elementi dell’elenco, in questo modo l’affidabilità viene limitata piuttosto che aumentata. In tutti i computer dotati di Windows, e per i rispettivi utenti, è disponibile un insieme di certificati principali che vengono installati per impostazione predefinita. Si tratta di una funzione comune anche in altri sistemi operativi e browser Web inclusi in diverse piattaforme. È possibile utilizzare l’oggetto Criteri di gruppo per disattivare le relazioni di trust automatiche per questi certificati principali. È quindi possibile utilizzare uno dei meccanismi descritti precedentemente per aggiungere nuovamente e in maniera selettiva i certificati affidabili necessari, con o senza limitazioni, a seconda delle esigenze di protezione.
  
    **Nota:** alcuni tipi di certificati principali non possono essere disattivati, in quanto vengono utilizzati dal sistema operativo per aspetti specifichi, quali il criterio della firma del driver. Poiché tali certificati sono necessari, non vengono disattivati dall’impostazione dell’oggetto Criteri di gruppo.
  
In questa guida è disattivato il servizio Aggiorna certificati principali per le autorità CA. Si consiglia di disattivare tale servizio in altri computer dell’organizzazione. Si consiglia inoltre di disattivare i certificati principali di terze parti predefiniti per tutti gli utenti del dominio utilizzando l’oggetto Criteri di gruppo. Nel capitolo 7, "Implementazione dell’infrastruttura a chiave pubblica”, questi elementi vengono descritti in maggior dettaglio.
  
Il certificato della CA principale dell'infrastruttura PKI descritto in questa guida viene distribuito ai client importandolo in Active Directory, come verrà illustrato nella prossima sezione.
  
##### Distribuzione dei certificati CA principali
  
I certificati CA principali vengono distribuiti automaticamente ai membri dell’insieme di strutture di Active Directory. Importando il certificato CA nel contenitore dell’Autorità di certificazione, i membri (computer e utenti) di tutti i domini dell’insieme di strutture installeranno tale certificato negli archivi locali delle CA principali affidabili. Si consiglia di utilizzare questo metodo per tutte le CA principali interne che necessitano di un ambito di trust esteso a tutto l’insieme di strutture.
  
Inoltre sarà necessario distribuire CA principali con un ambito di trust limitato oltre alle CA principali interne. Per ulteriori informazioni, vedere la sezione “Estensione dell’infrastruttura CA” più avanti in questo capitolo.
  
Per distribuire il certificato CA principale a utenti e computer su altre piattaforme o all’esterno dell’insieme di strutture, è necessario installare manualmente il certificato oppure utilizzare un altro metodo di distribuzione.
  
#### Definizione dei ruoli dell’Autorità di certificazione
  
Una volta definito il modello di trust e selezionata la strategia per le CA principali, è possibile pianificare l’infrastruttura CA restante. È quindi necessario definire i diversi ruoli da attribuire alle CA all’interno dell’organizzazione. È possibile configurare le autorità di certificazione come CA principali o subordinate. Le CA subordinate possono, a loro volta, diventare CA di emissione o intermedie, in quanto rappresentano fasi di trust intermedie tra le CA emittenti e quelle principali.
  
##### CA principale
  
L’autorità di certificazione principale riveste un ruolo fondamentale all’interno dell’organizzazione. Innanzitutto viene considerata esplicitamente affidabile da tutti gli utenti e dispositivi all’interno dell’organizzazione. Numerose decisioni in merito alla protezione (ad esempio, se consentire l’accesso a un utente, se considerare affidabile un messaggio di posta elettronica, se autorizzare una negoziazione di titoli pari a 10 milioni di euro) dipendono in ultima analisi dal grado di protezione della CA principale e dalla chiave privata che ne fornisce l’identità. Considerato che numerose operazioni dipendono dalla CA principale, la modifica di una chiave e di un certificato principali può rivelarsi un’operazione molto complessa che può provocare errori, nonché portare a saltuarie interruzioni del servizio di applicazioni e utenti per un periodo prolungato.
  
Per questo motivo, si consiglia di proteggere la chiave privata della CA principale nel modo più ampio possibile. A questo scopo, una delle procedure ottimali consiste nello scollegare la CA dalla rete per garantire un accesso piuttosto limitato. Si consiglia di adottare misure equivalenti per limitare l’accesso fisico al server. Come ulteriore misura di protezione delle chiavi della CA, si consiglia di utilizzare una periferica HSM (Hardware Security Module) dedicata, che consente di fornire una protezione aggiuntiva della chiave per le CA non in linea, oltre che aumentare in maniera significativa la protezione delle CA in linea.
  
La soluzione descritta nella presente guida utilizza una CA principale non in linea.
  
**Importante:** per migliorare la protezione delle chiavi CA, si consiglia di utilizzare una periferica HSM per la CA principale. È possibile aggiungere tali periferiche anche dopo l’installazione della CA, ma la procedura risulta più semplice e sicura se eseguita all'inizio. In questo caso però sarà necessario rinnovare la CA con una nuova chiave anche se numerosi fornitori consentono di importare la chiave esistente.
  
##### CA di emissione e intermedie
  
Se l’autorità di certificazione principale non è in linea, risulta praticamente impossibile rilasciare certificati quotidianamente. Per creare CA da utilizzare per il rilascio quotidiano di certificati, la CA principale certifica le CA subordinate a emettere certificati per suo conto. In questo modo la CA subordinata eredita l’attendibilità della CA principale, evitando eventuali rischi di protezione alla chiave della CA principale.
  
È possibile eseguire questa procedura anche in un secondo momento. Anziché rilasciare certificati direttamente, la CA subordinata consente di certificare un ulteriore livello di CA per l’emissione a entità finali (utenti e computer). In questo modo, oltre a fornire un livello di protezione aggiuntivo alla chiave della CA principale, è possibile ripartire i rischi tra le diverse CA subordinate. Una CA intermedia ad esempio può certificare CA di emissione interne, mentre un’altra CA intermedia può autorizzare CA a rilasciare certificati esterni. Questo metodo offre i seguenti vantaggi:
  
-   Il rischio di manomissioni delle CA viene limitato a una parte ridotta dell’intera gerarchia PKI.
  
-   È possibile implementare criteri di certificati separati per tutti i settori della gerarchia CA.
  
-   Grazie alla riduzione del numero di volte che viene utilizzata la chiave CA principale, diminuiscono anche i rischi di violazione della chiave.
  
Nonostante ulteriori livelli di CA intermedie consentano di aumentare la sicurezza globale dell’infrastruttura PKI, ne derivano anche una complessità e un carico di gestione maggiori, in misura decisamente superiore rispetto ai costi delle licenze hardware o software. Per molte applicazioni, i requisiti di protezione non sono sufficienti a giustificare una gerarchia a tre livelli, in particolare se le chiavi della CA sono protette mediante periferiche HSM.
  
La soluzione descritta nella presente guida propone una gerarchia a due livelli, in cui è possibile raggiungere un equilibrio accettabile tra livello di sicurezza ed economicità, mantenendo al contempo la flessibilità per un’eventuale integrazione di applicazioni dei certificati in futuro (come delineato, ad esempio, nella precedente sezione “Definizione dei requisiti del certificato”).
  
**Nota:** possibili discussioni su requisiti normativi in cui viene richiesto di utilizzare obbligatoriamente gerarchie a tre livelli non rientrano nell’ambito del documento. Ovviamente, tali requisiti prevalgono su qualsiasi altra considerazione.
  
##### Gerarchia CA proposta
  
Nella figura seguente è illustrata la gerarchia proposta, che riguarda l’implementazione della CA principale e di una CA di emissione. La CA di emissione rilascerà inizialmente certificati con garanzia standard (a volte definiti "tecnici") per computer o utenti e certificati di valore alto per computer.
  
[![](images/Dd536245.04fig4-2(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536245.04fig4-2_big(it-it,technet.10).gif)
  
**Figure 4.2. Gerarchia dell’autorità di certificazione**
  
Questo processo consente di distribuire un’infrastruttura PKI completamente funzionale, in grado di supportare l’autenticazione della rete LAN senza fili protetta (802.1X) con un esborso relativamente ridotto per hardware, software e costi di gestione.
  
**Nota:** è possibile estendere in diversi modi la progettazione di questa infrastruttura semplificata per soddisfare requisiti differenti. Questo argomento viene illustrato nella sezione "Estensione dell’infrastruttura CA".
  
La CA di emissione viene inizialmente configurata per il rilascio dei seguenti tipi di certificati (inclusi nei riquadri in grassetto nel diagramma precedente):
  
-   Autenticazione client - Utente
  
-   Autenticazione client - Computer
  
-   Autenticazione server IAS
  
I primi due elementi sono certificati con garanzia standard e vengono rilasciati automaticamente in base alle credenziali di dominio dell’utente o del computer. Il possesso di questi certificati indica una relazione non più stretta con il soggetto di quanto non lo sia il possesso di un nome utente e di una password di dominio validi. Tuttavia, è importante sottolineare che l’utilizzo di certificati al posto di nomi e password di dominio presenta vantaggi tecnici e in merito alla protezione.
  
L’autenticazione del server IAS è classificata come un certificato con garanzia media, in quanto i server IAS forniscono una funzione di protezione elevata. L’emissione di questo tipo di certificato include generalmente controlli aggiuntivi in merito alla validità della richiesta, oltre a richiedere l’approvazione del responsabile certificati.
  
**Nota:** nel capitolo della Guida alla creazione in cui viene descritta la creazione di questo tipo di certificato, non è stata attivata l’impostazione relativa all’approvazione del membro del gruppo Responsabile certificati, quindi nei server IAS è possibile rinnovare automaticamente i certificati scaduti evitando pertanto la disattivazione del servizio. Dopo aver eseguito i processi per esaminare attentamente e approvare la richiesta di certificato, si consiglia tuttavia di attivare il requisito relativo all’approvazione del responsabile certificati.
  
##### Requisiti hardware e software per le CA
  
In questa sezione vengono illustrati i requisiti hardware e software per le Autorità di certificazione.
  
###### CA principale
  
La CA principale necessita di minimi requisiti hardware e Per eseguire Windows Server 2003, non è necessario che la specifica del computer sia maggiore del requisito minimo. Le caratteristiche critiche dell'hardware per la CA principale sono affidabilità e facilità di gestione. Di solito, la CA principale risiede su un computer con un ciclo di vita esteso, ma che sia spento per la maggior parte del tempo. Quando il computer *è* in funzione, si richiede comunque che sia affidabile e che, per risolvere possibili guasti hardware, consenta di sostituire i componenti con facilità, possibilmente anche molti anni dopo che è stata interrotta la produzione del modello.
  
Tenendo conto di queste considerazioni, Microsoft consiglia di:
  
-   Scegliere un produttore di computer noto in grado di offrire un adeguato servizio di supporto e manutenzione hardware a lungo termine. Si consiglia di richiedere al fornitore per quanti anni saranno disponibili i componenti di ricambio.
  
-   Utilizzare server piuttosto che workstation o computer portatili, in quanto i primi hanno una struttura maggiormente standardizzata e sono soggetti a minori modifiche.
  
-   Considerare la presenza di un sistema di riserva  per gestire il ruolo della CA principale, in caso di guasti hardware che non è possibile riparare in tempi brevi.
  
-   Tenere una copia del supporto di installazione originale, dei driver e delle patch in modo da poter ripristinare il sistema se si verifica un guasto.
  
-   Si consiglia di considerare anche l’utilizzo di una periferica HSM per garantire un’ulteriore protezione.
  
La CA principale non necessita delle funzionalità aggiuntive incluse in Windows Server 2003 Enterprise Edition. Per questo motivo, la soluzione descritta nella presente guida utilizza Windows Server 2003 Standard Edition.
  
###### CA di emissione
  
Nonostante per le CA di emissione si debbano rispettare determinati requisiti di prestazioni, questi sono alquanto ridotti visto che le attività di tale CA sono decisamente limitate. Persino durante la valutazione delle prestazioni con carichi eccessivi per una CA dell'organizzazione, la limitazione è generalmente causata dall’interazione con Active Directory, non dalla CA stessa. I requisiti di prestazione hardware sono pertanto minimi. Come per la CA principale, i fattori critici sono rappresentati dall’affidabilità e dalla facilità di gestione nella scelta dell’hardware.
  
Poiché in Servizi certificati viene utilizzata la stessa tecnologia di database di Active Directory, è possibile applicare molte linee guida identiche relative alle prestazioni. Come regola di base, in molte organizzazioni vengono adottate le stesse specifiche hardware utilizzate nei controller di dominio di Active Directory.
  
Per ulteriori informazioni sulle prestazioni delle CA, vedere la sezione "CA Capacity, Performance, and Scalability" nel capitolo "Designing a Public Key Infrastructure" indicato nei riferimenti riportati alla fine di questo capitolo.
  
Nel capitolo 7, “Implementazione dell’infrastruttura a chiave pubblica”, è disponibile un profilo hardware. Oltre alle linee guida precedenti relative alla CA principale, è necessario tenere presente quanto riportato di seguito per la scelta dell’hardware del server per la CA di emissione:
  
-   Utilizzare schede di rete (NIC, Network Interface Card) ridondanti con il raggruppamento NIC.
  
-   Utilizzare almeno due volumi RAID 1 (Redundant Array of Independent Disks) per archiviare i registri CA in un’unità di archiviazione fisica separata. Questa procedura consente di ottenere vantaggi in termini di prestazioni oltre a una maggiore capacità di recupero in caso di errori hardware.
  
-   Utilizzare tre volumi RAID 1 (invece che due) su volumi fisici separati per l’archiviazione del sistema operativo, del database e dei registri di Servizi certificati per ottenere prestazioni ottimali.
  
-   Utilizzare unità e controller SCSI (Small Computer System Interface) ad alte prestazioni rispetto agli equivalenti IDE (Integrated Device Electronics) per ottenere migliori prestazioni e capacità di recupero. Oltre all'interazione con Active Directory, le prestazioni del sottosistema dei dischi rappresentano il fattore fondamentale nel determinare le prestazioni CA globali.
  
-   Utilizzare una periferica HSM per aumentare il livello di protezione e le prestazioni delle operazioni di firma durante l’emissione di certificati.
  
A differenza della CA principale, per la CA di emissione sono *necessarie* le funzionalità aggiuntive di Windows Server 2003 Enterprise Edition per supportare modelli di certificato modificabili e l'autoregistrazione dei certificati degli utenti.
  
###### Utilizzo di più CA di emissione per la capacità di recupero del servizio
  
In questa sezione vengono descritte le ragioni tecniche per cui si desidera installare più CA di emissione. L’utilizzo di diverse CA di emissione, per la registrazione di tipi di certificati differenti, può essere dovuto anche a ragioni di sicurezza e relative ai criteri. Questo aspetto verrà analizzato in una sezione successiva del capitolo.
  
Poiché una singola CA di emissione con un hardware limitato è sufficiente a soddisfare i requisiti di emissione dei tipi di certificati descritti precedentemente per un numero elevato di client, non è necessario disporre di più CA di emissione esclusivamente per migliorare le prestazioni. Si consiglia tuttavia di verificare, in base ai requisiti di disponibilità per le CA di emissione, se sia necessario distribuire più CA per registrare gli stessi tipi di certificati.
  
Una CA non presenta lo stesso tipo di problemi di disponibilità rispetto a numerosi servizi. Non è necessario infatti che i client contattino la CA per utilizzare o verificare un certificato. Un contatto diretto dei client con un’autorità di certificazione viene richiesto solo nei seguenti casi:
  
-   Registrazione di un nuovo certificato.
  
-   Rinnovo di un certificato.
  
-   Revoca di un certificato.
  
-   Pubblicazione di un nuovo CRL.
  
-   Rinnovo dello certificato CA.
  
I requisiti di disponibilità per i servizi vengono illustrati in dettaglio nella seguente tabella.
  
**Tabella 4.8. Requisiti di disponibilità dei servizi CA**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Servizio CA</p></th>  
<th><p>Requisiti di disponibilità</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Servizi di registrazione - Nuovo certificato</p></td>
<td style="border:1px solid black;"><p>Si tratta di un aspetto significativo in quanto consente di impedire l’accesso di nuovi utenti alla rete o ad altri servizi che richiedono un certificato. È necessario valutare se il tempo necessario per il ripristino della CA dal backup è superiore al tempo che l’organizzazione può attendere per la registrazione di un certificato da parte di un nuovo utente. La maggior parte delle organizzazioni ha rilevato che il costo legato all'attesa del ripristino della CA è minore rispetto al costo di gestione di CA aggiuntive. In alternativa, è necessario disporre di più CA di emissione per i tipi di certificati in questione.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Servizi di registrazione - Rinnovo certificato</p></td>
<td style="border:1px solid black;"><p>Se viene utilizzata la funzione di rinnovo automatico con il tipo di certificato in questione, per impostazione predefinita questa operazione si verifica sei settimane prima della scadenza del certificato precedente. Il tempo di ripristino dal backup per una CA, invece, viene generalmente misurato in ore. I certificati rinnovati manualmente vengono invece rinnovati dal proprietario. È possibile istituire un sistema di avviso automatico che avverte il proprietario quando i certificati critici necessitano di venire rinnovati.</p>
<p>Altrimenti, i criteri di disponibilità sono gli stessi richiesti per la registrazione di un nuovo certificato.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Revoca di un certificato</p></td>
<td style="border:1px solid black;"><p>Normalmente un certificato può essere revocato solo dalla CA che lo ha emesso, pertanto una seconda CA non è necessaria.</p>
<p>Se la revoca deve essere eseguita in tempi brevi, ovvero prima che la CA venga revocata, è possibile inserire voci di revoca negli elenchi CRL correnti, se si dispone del numero di serie del certificato da revocare e della chiave privata della CA (ripristinati in un computer differente).</p>
<p>Si tenga presente che la latenza degli elenchi CRL è generalmente di uno o più giorni, pertanto a meno che il tempo di ripristino della CA sia superiore all’intervallo relativo alla successiva pubblicazione CRL, l’aggiornamento manuale del CRL non comporta grandi vantaggi.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Pubblicazione di un elenco CRL</p></td>
<td style="border:1px solid black;"><p>In una CA è disponibile un elenco CRL univoco, pertanto una seconda CA non consentirebbe di aumentare la capacità di recupero della pubblicazione CRL, bensì solamente di ridurre l’impatto in caso di errori (meno del 100 percento dei certificati emessi dipende dall’elenco CRL non riuscito).</p>
<p>L’accesso allo stato di revoca corrente è fondamentale in molte applicazioni dei certificati. Questo significa che presso i punti di distribuzione CRL pubblicati deve essere disponibile un elenco CRL non scaduto. In caso contrario, non sarà possibile utilizzare le applicazioni dei certificati sensibili alla revoca.</p>
<p>Il periodo di recupero della CA non può essere superiore al periodo di sovrapposizione tra la scadenza del CRL precedente e l’emissione del nuovo CRL. In simili casi, molto rari peraltro, è possibile firmare nuovamente un elenco CRL e quindi estenderne il periodo di validità. Questa procedura viene descritta nella Guida operativa.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Rinnovo del certificato CA</p></td>
<td style="border:1px solid black;"><p>Non è necessaria una seconda CA di emissione.</p>
<p>Questa operazione deve essere eseguita tempestivamente per evitare problemi relativi al periodo di recupero di una CA. In caso contrario, è possibile firmare nuovamente il certificato CA mediante la chiave CA principale, prolungando il periodo di validità.</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Nota**: nella tabella precedente, è necessario valutare il tempo di recupero e la disponibilità della CA nel caso si verifichino problemi che vanno a influire sulla capacità della CA di fornire il servizio agli utenti finali. Tali problemi non si limitano a un malfunzionamento del server, bensì possono riguardare anche un’interruzione a livello di rete tra i siti. È pertanto necessario tenere presente tutti i fattori che possono influire sulla fornitura del servizio agli utenti quando si stabilisce il livello di disponibilità del servizio.

Se si gestisce correttamente il backup e il recupero delle CA, la scelta di utilizzare più CA per fornire la capacità di recupero del servizio è determinata esclusivamente dai requisiti di registrazione e di rinnovo. È necessario quindi confrontare il costo sostenuto per la mancanza di tali servizi con i costi di installazione e gestione necessari per la fornitura di CA aggiuntive.

Oltre a una maggiore disponibilità, più CA di emissione offrono migliori prestazioni in termini di emissione di certificati, dimezzando la dimensione degli elenchi CRL. Nella presente guida, nessuno dei fattori fin qui descritti è significativo per la soluzione. In questa guida, i problemi legati alla capacità di recupero vengono affrontati mediante un’attenta gestione delle CA, incluse procedure adeguate di backup e ripristino. È pertanto necessaria una singola CA di emissione.

###### Protezione della chiave della CA con periferiche HSM

Per migliorare significativamente la protezione della presente infrastruttura di base, è possibile utilizzare periferiche HSM che consentono di proteggere le chiavi private di tutte le CA. Sebbene abbiano un costo piuttosto elevato, fino a superare il costo di un server CA, tali periferiche offrono un significativo livello di protezione per l'ambiente. In questo modo è possibile limitare l'accesso per le operazioni con chiave CA solo agli utenti autorizzati. Le operazioni a carattere riservato (ad esempio l’esportazione e il back up delle chiavi) sono generalmente protette da più smart card. Il livello di protezione in questo caso è maggiore rispetto a quello ottenuto solo con chiavi basate su software, che possono essere copiate dalla CA da qualsiasi membro del gruppo Amministratori o Operatori backup locale.

Oltre agli enormi vantaggi per la protezione, le periferiche HSM consentono anche di velocizzare le operazioni di CA indirizzando il carico di lavoro dalla CPU a processori dedicati di accelerazione crittografica.

##### Protezione delle CA

In questa sezione viene descritta la protezione delle CA, inclusa la protezione fisica e del sistema operativo, i controlli e il monitoraggio della protezione, nonché l’utilizzo di ruoli per delegare le responsabilità di gestione attraverso la CA.

###### Protezione del sistema operativo

La protezione della CA avviene mediante i criteri di protezione di Windows, le cui impostazioni si basano sul ruolo del server CA descritto nella *Guida per la protezione di Windows Server 2003*.

Per ulteriori informazioni sulle impostazioni utilizzate per questo ruolo, vedere il capitolo 7, “Implementazione dell'infrastruttura a chiave pubblica”.

Le impostazioni di protezione relative alla CA principale vengono applicate direttamente utilizzando i modelli di protezione, mentre le impostazioni della CA di emissione vengono applicate mediante i criteri di gruppo.

###### Protezione fisica

La protezione fisica dei server CA è un aspetto fondamentale. Se non è possibile controllare l’accesso fisico di base ai server, non sarà efficace alcun livello di protezione della rete o del sistema operativo.

La CA principale deve trovarsi in posizioni in cui l’accesso al server è controllato rigorosamente. L’accesso alla CA è raramente necessario (due o tre volte all’anno) e, anche in questi casi, non è indispensabile accendere il server. Per questo motivo è possibile sistemare il server in una postazione sicura di archiviazione non dotata delle funzionalità standard richieste per i sistemi informatici. Non è necessario ad esempio disporre di sistemi di rete, infrastrutture avanzate per server o speciali sistemi di gestione per l'alimentazione e la temperatura.

Anche la CA di emissione deve trovarsi in una posizione in cui l’accesso fisico è controllato rigorosamente. In questo caso, la protezione fisica assume un’importanza rilevante in quanto esistono numerosi modi per violare la protezione di un sistema informatico, una volta che un pirata informatico può accedere fisicamente al sistema (simili attacchi possono riguardare anche la rete). Poiché tale server deve rimanere sempre in linea, deve essere situato in una postazione dotata di strutture standard per computer (controllo della temperatura, gestione dell’alimentazione, sistemi di ventilazione e antincendio).

Se possibile, la postazione di entrambi i server deve essere il più possibile protetta da rischi esterni che potrebbero danneggiare le apparecchiature, ad esempio incendi o inondazioni.

Un altro aspetto altrettanto importante consiste nel controllare l’accesso fisico e nel garantire la sicurezza fisica di backup, materiale rilevante e altri dati di configurazione. Tali informazioni devono venire memorizzate in una posizione differente rispetto ai server per consentire il recupero delle CA, nel caso in cui l’intero sito diventi inutilizzabile, a causa, ad esempio, di calamità naturali o di incendi.

###### Gestione della protezione delle CA

L’infrastruttura dei certificati è potenzialmente una risorsa di alto valore, che dipende essenzialmente dal modo in cui vengono utilizzati i certificati all’interno dell’organizzazione, non solo nel presente ma anche in futuro. Per questo motivo è necessario installare, configurare e gestire le CA adottando delle misure di verifica e protezione più rigorose rispetto a quelle utilizzate per installare altre infrastrutture IT. Tali misure devono essere almeno equivalenti a quelle utilizzate per un controller di dominio e in alcuni casi addirittura superiori.

La garanzia offerta da una CA dipende dall’alto livello di affidabilità, che deve essere impostato e gestito in maniera protetta. Se non si è in grado di garantire che la chiave privata della CA non sia stata copiata clandestinamente, non si potrà mai avere la certezza che un certificato presumibilmente rilasciato da una CA non sia stato contraffatto.

Poiché non è facile aumentare il livello di garanzia o affidabilità retroattivamente, è necessario creare sin dall’inizio un elevato livello di affidabilità per tutte le interazioni della CA. Per migliorare l’affidabilità di un’organizzazione, è possibile ad esempio aumentare la certezza che la chiave privata della CA non sia stata compromessa, adottando itinerari di controllo o altre prove in grado di garantire la legittimità di tutti gli accessi alla CA. Ad esempio, tutte le operazioni amministrative sulle CA sono state eseguite in presenza di un'altra persona oltre l'amministratore oppure sono state registrate su video. Nel caso di una CA non in linea, che non è stata mai connessa in rete, la possibilità di compromissione è notevolmente ridotta.

La necessità di avere un livello di garanzia molto elevato diventa un aspetto particolarmente importante, nel caso in cui l’organizzazione si trovi a far fronte a una controversia legale in merito alla validità di un certificato che ha emesso. In casi simili, se si dispone di prove che documentano che le CA non potevano essere violate, vi sono maggiori probabilità di concludere con successo la controversia. L’analisi dettagliata di tale problema esula dagli argomenti trattati in questa guida, pertanto si consiglia di consultare revisori e consulenti legali per ulteriori informazioni.

Di seguito vengono riportati alcuni esempi sui tipi di procedure che è possibile adottare per migliorare in maniera significativa il livello di garanzia delle CA.

-   Assicurare la protezione fisica della CA per impedire l’accesso da parte di persone non autorizzate all’hardware o al supporto di backup della CA.

-   Eseguire tutte le procedure di installazione e configurazione in presenza di un testimone: registrare le principali procedure di installazione e richiedere la controfirma del testimone per confermarne la corretta esecuzione. In alternativa, è possibile filmare l’installazione e affidare una copia del filmato a una terza parte di fiducia.

-   Eseguire tutte le operazioni di revoca ed emissione dei certificati mediante la CA principale in condizioni simili. Idealmente, tutti gli accessi alla CA principale dovrebbero essere controllati da un testimone.

-   Verificare che tutti gli utenti dotati di accesso amministrativo alle CA, dispongano anche di account individuali rintracciabili in modo univoco. Controllare tutte le operazioni relative alla CA.

-   Prendere in considerazione l’attivazione della separazione dei ruoli della CA (l'argomento verrà discusso in dettaglio più avanti nel capitolo).

Simili misure sono particolarmente importanti per il server CA principale, mentre la CA di emissione può avere un livello di garanzia inferiore a seconda dei tipi di certificati che si desidera rilasciare. Se ad esempio la CA non rilascia certificati di valore elevato, ma solo certificati standard come l’autenticazione di rete utente e computer, la CA non necessita di un livello di protezione superiore a quello di un controller di dominio.

Se una CA principale ha un livello di garanzia elevato, è possibile aggiungere una CA di emissione con un livello di garanzia superiore per rilasciare certificati di valore superiore in un secondo momento. È possibile mantenere sia CA con garanzia elevata che CA esistenti con garanzia standard. Se tuttavia la CA principale è installata e configurata in un ambiente con livello di protezione relativamente basso, sarà probabilmente necessario reinstallarla oppure creare una nuova CA principale, se si desidera rilasciare certificati di alto valore in un secondo momento.

###### Monitoraggio e controllo della protezione

Il controllo di Servizi certificati e del sistema operativo viene eseguito in tutte le CA. Per essere efficace, è necessario eseguire il monitoraggio del controllo ed esaminare eventuali elementi sospetti. Per ulteriori informazioni sul significato delle voci relative agli eventi di controllo di Servizi certificati, vedere il capitolo 11, "Gestione dell'infrastruttura a chiave pubblica".

###### Ruoli di gestione

Servizi certificati consente un notevole livello di controllo sulle deleghe dei ruoli amministrativi. Nella presente guida, questa funzione viene utilizzata per fornire una maggiore flessibilità per la gestione dell’infrastruttura PKI. Ogni ruolo amministrativo principale definito da Servizi certificati è stato implementato utilizzando un gruppo di protezione del dominio oppure, per le CA non in linea, un gruppo di protezione locale. Inoltre, sono stati definiti altri due ruoli e gruppi di protezione per facilitare la delega dei compiti amministrativi ai componenti dell’infrastruttura PKI di Active Directory.

Si tenga presente che non esiste necessariamente il mapping uno-a-uno tra questi ruoli e i singoli membri del personale IT all’interno dell’organizzazione. In molte organizzazioni infatti vengono attribuiti più ruoli alla stessa persona. È possibile implementare facilmente questa opzione aggiungendo l’utente a uno o a tutti i gruppi di protezione elencati nella seguente tabella. Qualora invece l’organizzazione abbia adottato sistema di separazione delle responsabilità amministrative più complesso, è necessario utilizzare la funzione di Servizi certificati per implementare i ruoli.

Nella tabella seguente vengono illustrati i ruoli implementati e le rispettive mappature dei gruppi di protezione (dove implementati).

**Tabella 4.9. Ruoli principali di Servizi certificati**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Nome del ruolo</p></th>
<th><p>Gruppo di protezione</p></th>
<th><p>Ambito</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Enterprise PKI Administrator</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Admins</p></td>
<td style="border:1px solid black;"><p>Insieme di strutture di Active Directory</p></td>
<td style="border:1px solid black;"><p>Responsabile di tutta l’infrastruttura PKI: definisce tipi di certificati, criteri delle applicazioni, percorsi di trust e così via per l’azienda.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Enterprise PKI Publisher</p></td>
<td style="border:1px solid black;"><p>Enterprise PKI Publishers</p></td>
<td style="border:1px solid black;"><p>Insieme di strutture di Active Directory</p></td>
<td style="border:1px solid black;"><p>Responsabile della pubblicazione di certificati affidabili principali, certificati CA secondari e di elenchi CRL nella directory.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>CA Administrator</p></td>
<td style="border:1px solid black;"><p>CA Admins</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Responsabile della configurazione CA. Di solito coincide con i ruoli di Amministratore PKI dell’organizzazione e Amministratore.</p>
<p>È possibile assegnare più amministratori CA a CA differenti se ciò è richiesto dall’utilizzo dei certificati.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Administrator</p></td>
<td style="border:1px solid black;"><p>Local Administrators</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Amministra il server e il sistema operativo CA. Responsabile dell'installazione della CA e del rinnovo del certificato CA. In genere viene condiviso con il ruolo di CA Administrator.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>CA Auditor</p></td>
<td style="border:1px solid black;"><p>CA Auditor</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Gestisce gli eventi di controllo e i criteri degli eventi controllabili dalle CA.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Responsabile certificati</p></td>
<td style="border:1px solid black;"><p>Responsabile certificati</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Approva le richieste di certificati per cui è richiesta l'approvazione manuale e revoca i certificati.</p>
<p>Possono coesistere più responsabili certificati che si occupano dell'approvazione per CA differenti se l'utilizzo dei certificati lo richiede.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Autorità di registrazione</p>
<p>oppure</p>
<p>Responsabile registrazione</p></td>
<td style="border:1px solid black;"><p>Non definito</p></td>
<td style="border:1px solid black;"><p>Profilo del certificato</p></td>
<td style="border:1px solid black;"><p>È un'estensione del ruolo del responsabile certificati, che si occupa dell'approvazione e della firma di richieste di certificati in seguito a una verifica dell'identificatore (ID) fuori banda.</p>
<p>Il ruolo può essere ricoperto da una persona o da un dispositivo di processo IT (ad esempio, scanner di impronte digitali e database).</p>
<p>È possibile specificare autorità di registrazione differenti per profili di certificati diversi (modelli) e interessare più CA.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Key Recovery Agent</p></td>
<td style="border:1px solid black;"><p>Non definito</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Detiene le chiavi per la decrittografia di chiavi private, archiviate nel database CA.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>CA Backup Operator</p></td>
<td style="border:1px solid black;"><p>CA Backup Operator</p></td>
<td style="border:1px solid black;"><p>CA</p></td>
<td style="border:1px solid black;"><p>Responsabile di backup e ripristino di server CA e di conservare in modo sicuro i supporti di backup.</p></td>
</tr>  
</tbody>  
</table>
  
Questi gruppi di protezione vengono implementati come gruppi universali di dominio e vengono applicati alla CA di emissione e alla directory. Per la CA principale, vengono implementati gruppi equivalenti come gruppi locali; in ogni caso non esiste un gruppo equivalente per gli amministratori e per gli autori PKI dell’organizzazione di una CA non in linea. In questa guida si presuppone che vengano utilizzati gli stessi gruppi di protezione per tutte le CA all’interno dell’organizzazione. In caso contrario, è necessario implementare gruppi separati per ogni CA per tutti i ruoli con ambito CA, quindi rinominarli in maniera appropriata, ad esempio Amministratori CA - CA di emissione 1.
  
Poiché le autorità di registrazione (o responsabili della registrazione) e l’archiviazione e il recupero della chiave non sono stati implementati in questa guida, non sono stati definiti gruppi di protezione per i ruoli corrispondenti.
  
Infine è possibile imporre la separazione tra i ruoli CA per un’autorità di certificazione. Se si attiva questa opzione, a tutti gli utenti membri di più gruppi di ruoli viene negato l’accesso ai privilegi di tutti i gruppi di ruolo. La separazione dei ruoli non è stata implementata in questa guida.
  
##### Integrazione di Active Directory
  
È possibile installare le CA in una delle due modalità disponibili: dell'organizzazione (di grandi dimensioni) (o integrata in Active Directory) o autonoma. A differenza della modalità autonoma, le CA dell'organizzazione consentono di: utilizzare Active Directory per archiviare le informazioni di configurazione, utilizzare Active Directory come autorità di registrazione e pubblicare automaticamente certificati emessi nella directory. Le CA autonome invece possono pubblicare certificati ed elenchi CRL nella directory, ma non fanno affidamento su Active Directory.
  
Per una descrizione dettagliata, vedere la sezione “Ulteriori informazioni” alla fine del capitolo.
  
Poiché viene utilizzata in modalità non in linea, è possibile configurare la CA principale solo come server autonomo. Lo stesso vale per le CA intermedie non in linea se si sceglie di distribuirle nel proprio ambiente.
  
La CA di emissione viene configurata come CA dell'organizzazione di grandi dimensioni per i seguenti motivi:
  
-   È necessario eseguire la registrazione e l’approvazione automatiche dei tipi di certificati utilizzati in questa guida.
  
-   In questa guida è necessario utilizzare i modelli dei certificati, che offrono numerosi vantaggi semplificando la gestione di più tipi di certificati (spesso mediante più CA).
  
-   Per il servizio IAS è necessario eseguire il mapping dei certificati affidabili in Active Directory per autenticare i client senza fili. Per consentire questa operazione, è necessario registrare la CA nell’archivio NTAuth.
  
-   È possibile, sebbene non necessaria per questa soluzione, la pubblicazione automatica dei certificati per i corrispondenti oggetti computer o utente.
  
-   La CA necessita di una fonte affidabile per ottenere le informazioni sul nome del soggetto da utilizzare per le richieste di certificati e per i certificati rilasciati. In Active Directory queste informazioni sono disponibili mediante gli attributi computer e utente archiviati nella directory.
  
-   In futuro potrebbero essere necessari i certificati di accesso con smart card, che grazie alle CA dell'organizzazione possono essere implementati più facilmente.
  
    **Nota:** alcune di queste funzionalità vengono fornite per impostazione predefinita dalla CA dell'organizzazione, sebbene possano essere disponibili anche con una CA autonoma correttamente configurata. L'argomento viene descritto in dettaglio nella documentazione di Servizi certificati. Vedere il riferimento alla fine del presente capitolo.
  
###### Installazione delle CA nei domini
  
Se nell’organizzazione è disponibile un insieme di strutture a più domini (o persino più insiemi di strutture), è necessario scegliere i domini in cui installare le CA. Tale scelta può essere influenzata da diversi fattori, quali la necessità di delegare il controllo a diversi responsabili del dominio oppure le normative nazionali o locali relative alla fornitura di certificati in settori differenti dell’organizzazione.
  
La metodologia adottata più comunemente consiste nell’installazione delle CA nel dominio principale dell’insieme di strutture o in un dominio dedicato a attività di gestione. È necessario installare le CA in un dominio che rimarrà stabile per un lungo periodo di tempo (dopo l'installazione non è possibile modificare il nome della CA, l'appartenenza del dominio e il nome del dominio DNS). È necessario inoltre evitare l’installazione delle CA in domini in cui non sia possibile garantire la protezione o l’integrità dell’account computer. Sebbene possa semplificare la gestione centralizzata, non è necessario installare le CA nello stesso dominio.
  
In questa guida, gli account del server CA (solo CA di emissione globali) vengono installati nel dominio principale dell’insieme di strutture oppure, nel caso di un insieme di strutture di dominio singolo, nel dominio stesso.
  
##### Mapping delle dichiarazioni sulle procedure di certificazione alle CA
  
Se si intende pubblicare la dichiarazione CPS, è necessario determinare l’ambito della CPS. È possibile creare una CPS per un’intera gerarchia CA o solo per una parte oppure è possibile disporre di una CPS per ogni CA.
  
Quest’ultima opzione, pur offrendo una maggiore flessibilità, aumenta il carico di gestione di più CPS. La procedura standard consiste nel creare una CPS separata per ogni CA o gruppo di CA con in comune criteri di certificazione, tipi di soggetto e livelli di protezione. Se esistono delle differenze significative tra le CA, è necessario utilizzare più CPS. Se si dispone invece di numerose CA identiche distribuite per ragioni di prestazioni o capacità di recupero, esse devono includere anche le stesse CPS.
  
Come si è già rilevato in precedenza, è piuttosto legittimo creare una CPS, ma non pubblicarla. È possibile ad esempio evitare la pubblicazione della CPS esternamente se si ritiene che siano incluse informazioni operative e sulla protezione di tipo interno. È possibile inoltre scegliere di pubblicare una versione abbreviata della CPS in cui vengono elencati i criteri operativi importanti della CA, senza rivelare informazioni operative interne.
  
Se si decide di pubblicare la CPS e renderne nota la posizione nel certificato CA, è necessario ottenere un identificatore oggetto (OID) dallo spazio dei nomi OID ufficiale, assegnato all’organizzazione in base allo standard ISO (International Standards Organization). Il criterio di certificazione è univoco per l’organizzazione, pertanto è necessario disporre di un OID univoco globale per identificarlo.
  
Tale OID del criterio CP è codificato in ciascun certificato dell'organizzazione come estensione del certificato. Un'“*estensione del certificato*” è un tipo di campo per i dati del certificato. Come parte dell'estensione, viene fornito anche un URL che indirizza alla dichiarazione CPS per la CA che emette un particolare certificato.
  
È piuttosto comune includere anche una notifica utente in formato testo con alcune indicazioni sullo scopo o sull’origine del certificato. Poiché esiste il limite di 200 caratteri, non può essere tuttavia considerata un’alternativa a un documento CPS separato.
  
Per ulteriori informazioni su come vengono codificati i criteri OID e gli URL per le CPS in un certificato, vedere RFC 3280*, Internet X.509 Public Key Infrastructure Certificate and CRL Profile* nella sezione "Ulteriori informazioni" alla fine di questo capitolo.
  
Una volta ottenuto l’OID della dichiarazione CP e scelto un URL in cui pubblicare la CPS, è possibile includere quest’ultima nei certificati CA. Tale procedura viene descritta nel capitolo 7, “Implementazione dell’infrastruttura a chiave pubblica”.
  
#### Supporto dell’infrastruttura IT
  
In questa guida, il sistema PKI si basa su altri servizi dell’infrastruttura per un corretto funzionamento. Nel diagramma seguente sono illustrati i principali servizi, Active Directory e IIS, e l'interazione con le CA e i client dei certificati.
  
[![](images/Dd536245.04fig4-3(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536245.04fig4-3_big(it-it,technet.10).gif)
  
**Figura 4.3. Interazione della CA con l’infrastruttura IT**
  
Altri aspetti non illustrati nel diagramma, ma comunque fondamentali per il corretto funzionamento di Servizi certificati, riguardano il sistema di monitoraggio, avviso e gestione. Tale infrastruttura viene illustrata in dettaglio nel capitolo 11, “Gestione dell’infrastruttura a chiave pubblica”. Nelle sezioni che seguono vengono descritti i servizi forniti all'infrastruttura PKI da Active Directory e IIS.
  
##### Active Directory
  
Come si è già rilevato nella sezione precedente, "Integrazione di Active Directory", Active Directory fornisce numerosi servizi fondamentali per l’infrastruttura PKI, tra cui la pubblicazione, la registrazione e il mapping degli account dei certificati, nonché l’archiviazione di trust e informazioni sulla configurazione.
  
Tutti questi servizi vengono forniti automaticamente per le CA globali, inoltre alcuni possono essere utilizzati anche per le CA autonome in linea. Le CA non in linea tuttavia non possono interagire direttamente con Active Directory per archiviare e recuperare informazioni.
  
In questa guida, il certificato CA della CA principale non in linea viene pubblicato nell'archivio principale attendibile di Active Directory. In questo modo, il certificato della CA principale viene distribuito automaticamente nell’archivio principale attendibile di tutti i client di Active Directory all’interno dell'insieme di strutture.
  
La CA principale può utilizzare Active Directory anche per i seguenti servizi di pubblicazione (opzioni non utilizzate in questa guida):
  
-   Pubblicazione CRL:  i client del dominio (in tutto l'insieme di strutture) possono eseguire il recupero di elenchi CRL da un controller di dominio locale pubblicato in Active Directory.
  
-   Distribuzione di certificati incrociati ai client del dominio: i certificati incrociati pubblicati in Active Directory vengono distribuiti automaticamente all'archivio dei certificati di ciascun client di Active Directory dell'insieme di strutture.
  
Active Directory viene utilizzato dalle CA di emissione per tutti i servizi descritti nella sezione "Integrazione di Active Directory".
  
###### Utilizzo di Active Directory per client non appartenenti a Active Directory
  
È necessario considerare alcuni fattori per il supporto di client PKI che sono membri di un altro insieme di strutture di Active Directory non affidabili oppure che non sono membri di un insieme di strutture di Active Directory.
  
Se si desidera consentire a questi tipi di client esterni di recuperare certificati CA ed elenchi CRL utilizzando il protocollo LDAP (Lightweight Directory Access Protocol), è necessario tenere presente i seguenti aspetti:
  
-   Per i client esterni, è necessario configurare un nome host LDAP esplicito per i percorsi CDP e AIA. Per ulteriori informazioni, vedere la sezione "Configurazione dei percorsi CDP e AIA" più avanti in questo capitolo.
  
-   Per impostazione predefinita, i client esterni non possono eseguire query LDAP anonime in Active Directory. È necessario cambiare il valore **dsHeuristics** dell’insieme di strutture e concedere autorizzazioni di accesso esplicite all’account anonimo. Per ulteriori informazioni, vedere la sezione "Ulteriori informazioni" alla fine del capitolo.
  
    **Avviso**: con questa procedura, è disponibile un protocollo LDAP anonimo su tutti i controller di dominio dell’insieme di strutture. Tuttavia i client non autenticati potranno accedere solo agli elementi con autorizzazioni esplicite per l’account anonimo. Prima di procedere, valutare attentamente le implicazioni nel consentire l’accesso non autenticato alla directory.
  
-   Poiché i client esterni non ereditano le informazioni principali affidabili configurate nella directory, sarà necessario individuare un altro modo per configurare tali informazioni.
  
###### Considerazioni per client Internet
  
È necessario considerare alcuni aspetti importanti in merito alla configurazione CDP e AIA per i client esterni all'organizzazione (ad esempio, client Internet). Tale configurazione è descritta nella sezione "Configurazione dei percorsi CDP e AIA" più avanti in questo capitolo.
  
Se viene richiesto di fornire ricerche di certificati per supportare client Internet, ad esempio ricerche di certificati di posta elettronica, può essere necessario creare una directory LDAP separata per i client Internet. Considerate le implicazioni relative alla protezione, si consiglia di non utilizzare il metodo descritto in precedenza per l’attivazione di un protocollo LDAP anonimo all’interno dell’insieme di strutture di Active Directory. Creare invece un insieme di strutture separato in Active Directory, quindi replicare le informazioni dall’insieme di strutture interno utilizzando lo strumento LDIFDE, un prodotto di metadirectory, ad esempio Microsoft Metadirectory Services, o un altro prodotto per la sincronizzazione delle directory.
  
##### Internet Information Services (IIS)
  
In questa progettazione, IIS fornisce due servizi per l’infrastruttura PKI:
  
-   Pubblicazione delle informazioni CA, ad esempio elenchi CRL, certificati CA e, potenzialmente, documenti CPS.
  
-   Funzionalità per registrare certificati utilizzando un’interfaccia Web, particolarmente utile per i client non Windows (opzione non utilizzata in questa guida).
  
###### Utilizzo di IIS per la pubblicazione di informazioni CA
  
In questa guida, le informazioni CDP e AIA relative alle CA principali e di emissione vengono pubblicate in un server Web. L’utilizzo della pubblicazione HTTP consente alla più vasta gamma di client di recuperare le informazioni necessarie,
  
L’installazione di IIS per la CA di emissione, pur essendo una procedura comune per tale scopo, non rappresenta sempre la soluzione ottimale. Se disponibile, utilizzare un altro server IIS per la pubblicazione di informazioni CRL e CA. È consigliabile limitare le modalità di accesso degli utenti alle CA, in quanto ogni protocollo e servizio aggiuntivi alla CA offrono ai pirati informatici un altro possibile punto di accesso al server. L’utilizzo di IIS consente inoltre di prevenire l’interruzione dell’attività della CA per manutenzione, in quanto può essere l’unico percorso CRL valido per molti client.
  
Nella Guida alla creazione, la CA di emissione viene utilizzata per ospitare IIS per la pubblicazione di CRL e CA. Questa operazione è stata eseguita per semplificare il processo di creazione e per ridurre la necessità di hardware aggiuntivo. Microsoft consiglia tuttavia di scegliere posizioni separate, se possibile.
  
###### Utilizzo di pagine di registrazione IIS per registrare certificati
  
Le pagine di registrazione IIS sono utili in numerosi scenari: per la registrazione di client non di dominio, di client non Windows o client browser diversi da Microsoft Internet Explorer.
  
La CA non necessita invece di pagine di registrazione Web. Per impostazione predefinita, in questa guida tali pagine vengono installate nella CA di emissione, sebbene sia possibile installarle su un server Web separato (il server deve eseguire IIS 5.0 o versioni successive per supportare le pagine ASP). Anche se consentono di semplificare le attività di registrazione, non è necessario installare le pagine di registrazione se non vengono utilizzate. Per ulteriori informazioni sull’installazione e sull’utilizzo delle pagine Web di registrazione, vedere il riferimento nella sezione "Ulteriori informazioni" più avanti in questo capitolo.
  
#### Configurazione dei percorsi CDP e AIA
  
I client devono poter accedere a un elenco CRL aggiornato per stabilire se un certificato è stato revocato. I client devono inoltre poter recuperare certificati CA per verificare che un certificato di entità finale sia collegato a una CA principale attendibile. Ogni CA deve codificare nei propri certificati uno o più URL che consentano di individuare i percorsi che i client possono utilizzare per ottenere informazioni in merito a tali certificati.
  
Le modalità di configurazione per CDP e AIA per ciascuna CA dipendono dai tipi di client che utilizzano i certificati. Ad esempio, i certificati potrebbero essere destinati solo a utenti e computer membri di un insieme di strutture Active Directory oppure anche a periferiche e utenti esterni. L’argomento relativo alla definizione dei client dei certificati è stato descritto in una sezione precedente.
  
##### CA principale
  
In questa guida, la CA principale viene configurata come segue:
  
-   I percorsi principali (primi dell’elenco) per CDP e AIA sono URL HTTP. Dato che l’elenco CRL della CA principale ha dimensioni ridotte (1-2 KB) e l’intervallo di pubblicazione è piuttosto lungo (sei mesi), è possibile pubblicarlo in un unico percorso senza provocare significative limitazioni ai client che recuperano il CRL.
  
-   I percorsi secondari vengono configurati come URL LDAP per creare un backup delle destinazioni HTTP. Poiché non viene utilizzato alcun nome host LDAP, i client dello stesso insieme di strutture recuperano le informazioni dai propri controller di dominio locali. I client esterni all’insieme di strutture non possono accedere a questa posizione.
  
In questa configurazione, i certificati della CA e delle CA subordinate possono essere utilizzati dai client esterni all’insieme di strutture di Active Directory, in quanto vengono utilizzati i percorsi HTTP per impostazione predefinita.
  
##### CA di emissione
  
In questa guida, viene ottimizzata la CA di emissione per essere utilizzata da client interni di Active Directory. La CA viene configurata come segue:
  
-   I percorsi principali per gli URL CDP e AIA corrispondono ai percorsi di directory LDAP.
  
-   Negli URL CDP e AIA non viene specificato alcun nome host LDAP, quindi il client utilizza il server LDAP predefinito. Per i client di Active Directory, il server LDAP predefinito corrisponde ai controller di dominio locali. È possibile tuttavia che altri client LDAP non riescano a eseguire query per questi percorsi LDAP.
  
Questa configurazione è ideale per client dello stesso insieme di strutture delle CA. Gli elenchi CRL di base vengono pubblicati settimanalmente, mentre gli elenchi Delta CRL vengono pubblicati quotidianamente. Poiché per impostazione predefinita entrambi si trovano in Active Directory, i client recupereranno tali elenchi dal controller di dominio più vicino. In questo modo viene garantita la capacità di recupero e l’ottimizzazione del traffico di rete.
  
###### Impostazione di CDP e AIA per il supporto a client esterni
  
La configurazione precedente non è ottimale per i client che sono membri di un altro insieme di strutture di Active Directory o che non sono membri di un insieme di strutture (ad esempio, un router). Poiché questi client esterni non potranno accedere a CDP e AIA in LDAP, gli utenti esterni possono registrare ritardi significativi durante il tentativo di controllare la revoca e le informazioni AIA. Questi ritardi possono provocare errori nelle applicazioni per gli utenti esterni.
  
Se esiste la possibilità che i certificati vengano utilizzati da client esterni all'insieme di strutture di Active Directory, è necessario configurare i valori CDP e AIA in modo tale da utilizzare gli URL HTTP come percorsi principali al posto degli URL LDAP.
  
Per includere URL LDAP utilizzabili dagli utenti esterni, attenersi alla seguente procedura:
  
-   Configurare un nome host LDAP esplicito per i percorsi CDP e AIA. Non è possibile utilizzare il percorso Null predefinito (LDAP:///). Per modificare un percorso CDP o AIA per una CA, è necessario emettere nuovamente (rinnovare) il certificato CA.
  
-   Attivare l’accesso LDAP anonimo come descritto precedentemente in questo capitolo.
  
###### Considerazioni per client Internet
  
Se si intende distribuire certificati all’esterno dell’organizzazione da utilizzare su Internet, è necessario tenere presente alcune considerazioni.
  
I certificati che includono URL LDAP interni possono fornire informazioni sulla struttura e sui nomi di Active Directory e della CA. Per evitare questo, è necessario eseguire le seguenti operazioni:
  
-   Utilizzare solo URL HTTP per i valori CDP e AIA della CA principale e per tutte le CA subordinate della catena.
  
-   Rilasciare certificati da utilizzare esternamente da una CA separata, in cui vengono utilizzati solo CDP HTTP e URI AIA.
  
In entrambi i casi, è necessario fornire una posizione HTTP secondaria per il recupero di CRL affinché i client possano utilizzarla, se la posizione principale non è disponibile.
  
Per ulteriori informazioni sull’utilizzo di CRL e CDP, vedere i riferimenti a tale argomento inclusi nella sezione "Ulteriori informazioni" alla fine del capitolo.
  
#### Estensione dell’infrastruttura CA
  
Nella sezione "Definizione dei requisiti di protezione dei certificati" viene descritta la classificazione dei certificati in base al livello di protezione e al tipo di soggetto. Il motivo principale della separazione dei differenti tipi di soggetti consiste nella possibilità che vengano applicati a questi tipi di soggetti criteri di certificazione e procedure operative diverse (come documentato nelle dichiarazioni CPS).
  
In genere, viene applicata una dichiarazione CPS per ogni CA. Anche se è possibile adottare criteri differenti per controllare tipi di soggetto diversi in una singola CA, questo renderebbe la CPS più complessa e difficile da implementare correttamente. La strategia per estendere questa infrastruttura PKI e consentire il rilascio di certificati dotati di requisiti di protezione e criteri differenti, consiste nel creare ulteriori CA di emissione per la maggior parte dei tipi di soggetto. Questa configurazione è illustrata nella figura seguente.
  
**Nota:** questa figura indica solo come sia possibile estendere la gerarchia CA precedente. Nella propria organizzazione può essere necessaria una struttura più complessa, o al contrario più semplice, a seconda delle esigenze future. Non esiste una pianificazione giusta o sbagliata dell'infrastruttura PKI in senso assoluto: la pianificazione delle CA aggiuntive e delle funzionalità di certificazione deve basarsi sui requisiti di protezione dell'azienda. Quando si tenta di estendere l'infrastruttura PKI per soddisfare altre esigenze relative ai certificati, è necessario seguire un approccio simile a quello descritto per la progettazione della PKI semplificata.
  
[![](images/Dd536245.04fig4-4(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536245.04fig4-4_big(it-it,technet.10).gif)
  
**Figura 4.4. Estensione della gerarchia CA**
  
In questo diagramma viene illustrato come sia possibile estendere la gerarchia CA semplificata descritta precedentemente per far fronte a una più ampia gamma di requisiti dei certificati. Le nuove CA e funzionalità dei certificati vengono mostrate su sfondo grigio. Nel diagramma viene inoltre illustrato l’uso di certificati di valore elevato (simbolo a forma di chiave e di lucchetto) e come le CA utente (interno ed esterno) una volta portate in linea, assumeranno il ruolo di rilasciare certificati utente standard dalla prima CA.
  
Questa strategia relativa all’estensione dell’infrastruttura CA presuppone quanto segue:
  
-   La gestione dell’infrastruttura CA viene centralizzata, pertanto non è necessario delegare il controllo delle CA in base a divisioni organizzative o geografiche.
  
-   Gli standard comuni dei certificati vengono utilizzati in tutta l’organizzazione; questo significa che è stato accettato un certificato di un tipo determinato e sono stati concordati gli utilizzi e i criteri comuni in tutta l’organizzazione.
  
-   Non è richiesta alcuna interoperabilità con un’infrastruttura PKI esistente.
  
-   Sono richiesti livelli e criteri di protezione differenti per i diversi tipi di certificati indicati (e altri che potrebbero essere necessari).
  
Se tali presupposti non sono validi per la propria organizzazione, può rendersi necessaria una struttura diversa. Per una descrizione dettagliata sulle diverse opzioni e approcci relativi all’estensione di un’infrastruttura CA, vedere il riferimento "Designing a Public Key Infrastructure" riportato alla fine del presente capitolo.
  
##### Subordinazione qualificata
  
Le definizioni dei certificati create possono essere utilizzate per definire i modelli dei certificati e per rilasciare certificati senza ulteriore personalizzazione. Durante l'estensione della PKI, è comunque possibile limitare l’ambito dei certificati che possono essere rilasciati dalle CA, imponendo la delega dei certificati CA di emissione.
  
La subordinazione qualificata, descritta in una sezione precedente, può essere utilizzata per controllare l’ambito e lo scopo dei trust all’interno dell’organizzazione mediante la creazione di certificati incrociati tra l’infrastruttura CA aziendale e quelle di organizzazioni esterne. È possibile utilizzare la stessa tecnica per limitare i tipi e alcuni attributi di certificati all’interno della propria gerarchia CA. Una trattazione dettagliata di questo argomento esula dall’ambito di questo capitolo. Per ulteriori informazioni su questo argomento, vedere il riferimento al documento *Planning and Implementing Cross-Certification and Qualified Subordination Using Windows Server 2003* alla fine di questo capitolo.
  
Per l’infrastruttura PKI creata in questa guida, non è necessario utilizzare la subordinazione qualificata all’interno della gerarchia CA.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Configurazione dei profili di certificati
  
In questa sezione viene descritta la modalità di configurazione dei certificati per soddisfare i requisiti precedentemente definiti all'interno del presente capitolo.
  
#### Definizione dei parametri dei certificati
  
Per ciascun tipo di certificato richiesto, è necessario indicare il profilo del relativo certificato e quindi convertire i parametri del profilo in modelli di certificato che controllano i tipi di certificato emessi dalla CA.
  
**Nota:** le CA autonome non utilizzano modelli di certificati. È necessario creare la richiesta tramite uno strumento, quale Certreq.exe, utilizzando il modulo presente nelle pagine Web di registrazione o creando la richiesta a livello di programmazione. Se si utilizza una CA autonoma, è comunque necessario definire i profili per ciascun tipo di certificato e utilizzare tali profili per creare le richieste di certificato per la CA autonoma.
  
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
  
La lunghezza, il periodo di validità, le opzioni di creazione della chiave e i criteri di registrazione e autorizzazione sono determinati dal livello di protezione del certificato richiesto e dai requisiti dell'applicazione indicati precedentemente in questo capitolo.
  
#### Definizione della durata delle chiavi e dei certificati
  
Una serie di fattori influisce sulla durata dei certificati, quali il tipo di certificato, i requisiti di protezione dell'organizzazione, le procedure standard applicate nel settore interessato e la normativa in vigore. In generale, maggiore è la lunghezza delle chiavi, maggiore sarà la durata supportata per i certificati e le chiavi.
  
Di seguito vengono riportate le limitazioni alla lunghezza e al tipo di chiavi utilizzate:
  
-   Compatibilità: alcune applicazioni di certificati non supportano chiavi più lunghe di 2048 bit. È possibile che la scelta del tipo di chiave influisca anche sulla compatibilità. Generalmente, le chiavi RSA offrono maggiore compatibilità, tuttavia per determinate applicazioni potrebbe essere necessario utilizzare altri tipi di chiave. Per tutte le CA della catena, è necessario tenere in considerazione la compatibilità sia in termini di lunghezza che in termini di tipo di chiave.
  
-   Prestazioni: per operazioni di firma e crittografia la capacità di elaborazione richiesta aumenta con la lunghezza delle chiavi. Per questo motivo, chiavi con lunghezza superiore a 2048 bit non verranno utilizzate da CA che emettono un'elevata quantità di certificati.
  
-   Archiviazione: chiavi più lunghe richiedono certificati più grandi e quindi capacità di archiviazione maggiore nel database dei certificati. Se i certificati vengono pubblicati in Active Directory, aumenteranno anche i relativi requisiti di spazio di archiviazione. La dimensione e la frequenza di backup sarà direttamente proporzionale.
  
Quando si sceglie la durata dei certificati e delle chiavi, occorre considerare il grado di vulnerabilità delle chiavi e le relative conseguenze potenziali. I fattori indicati di seguito influiscono sulla durata prescelta dei certificati e delle chiavi.
  
-   Lunghezza della chiave privata: poiché chiavi di lunghezza maggiore sono più difficili da violare, ne è giustificata la maggiore durata.
  
-   Protezione CA: maggiore è il livello di protezione offerto dalla CA e dalla relativa chiave privata, maggiore sarà la durata della chiave.
  
-   Utilizzo di risorse hardware di crittografia: smart card e periferiche HSM (Hardware Security Module) rendono la chiave più sicura e ne giustificano la maggiore durata.
  
-   Attendibilità dei soggetti certificati: è possibile garantire una maggiore durata dei certificati ai dipendenti e ai computer interni rispetto agli utenti e ai computer esterni.
  
-   Numero di certificati firmati mediante una chiave CA: maggiore è il numero di accessi alla chiave, maggiore sarà la diffusione della chiave CA pubblica e maggiori saranno le probabilità di tentativi di violazione e eventuale compromissione.
  
Nella tabella riportata di seguito, vengono indicati la durata e i periodi di rinnovo delle chiavi per le CA e le entità finali utilizzate in questa guida.
  
**Tabella 4.10. Durata di certificati e chiavi**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="25%" />  
<col width="25%" />  
<col width="25%" />  
<col width="25%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Soggetto certificato</p></th>  
<th><p>Lunghezza della chiave</p></th>  
<th><p>Durata della chiave</p></th>  
<th><p>Intervallo di rinnovo</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>CA principale</p></td>
<td style="border:1px solid black;"><p>4096 bit</p></td>
<td style="border:1px solid black;"><p>16 anni</p></td>
<td style="border:1px solid black;"><p>8 anni</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>CA di emissione</p></td>
<td style="border:1px solid black;"><p>2048 bit</p></td>
<td style="border:1px solid black;"><p>8 anni</p></td>
<td style="border:1px solid black;"><p>4 anni</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Entità finale</p></td>
<td style="border:1px solid black;"><p>da 1024 a 2048 bit</p></td>
<td style="border:1px solid black;"><p>Da 6 mesi a 2 anni</p></td>
<td style="border:1px solid black;"><p>90 per cento del periodo di validità</p></td>
</tr>  
</tbody>  
</table>
  
In termini di lunghezza della chiave, le chiavi a 1024 bit vengono attualmente considerate superiori alle esigenze crittoanalitiche più comuni. Dovrebbero infatti disporre di una durata media che superi abbondantemente il valore proposto, pari a 2 anni, per l'entità finale. L'utilizzo delle chiavi a 512 bit non garantisce più un sufficiente grado di protezione, se non per applicazioni con requisiti di protezione estremamente ridotti e pertanto non vengono utilizzate in questa soluzione.
  
Il livello di crittografia della chiave della CA di emissione rappresenta un compromesso tra prestazioni e protezione. Una chiave di questa dimensione dispone attualmente di una durata che supera abbondantemente il periodo di rinnovo quadriennale previsto.
  
Poiché la CA principale non presenta limiti reali in termini di prestazioni, è possibile impostare il livello di crittografia della chiave sul valore massimo pari a 16 kilobit. Per esigenze di compatibilità, il livello utilizzato nella presente guida è molto inferiore. Tuttavia, le chiavi a 4096 bit dispongono di una durata che supera abbondantemente il periodo previsto di rinnovo pari a otto anni.
  
Le chiavi RSA vengono utilizzate da tutte le CA, sebbene il tipo di chiave utilizzato per le entità finali viene determinato dai requisiti dell'applicazione.
  
Sebbene sia possibile rinnovare un certificato con la stessa chiave, tale operazione non è consigliata  in circostanze normali. A ogni rinnovo di certificato verrà invece generata una nuova coppia di chiavi.
  
I certificati emessi dalle CA non possono disporre di un periodo di validità che superi quello della CA di emissione e da tutte quelle di livello superiore, compresa la principale. Se la durata prevista di un certificato CA è pari a un periodo di sei mesi, sarà possibile emettere solo certificati con una durata massima pari allo stesso periodo. In questa soluzione, pertanto, il rinnovo dei certificati emessi dalla CA è previsto a metà della durata prestabilita. La validità di tutti i certificati emessi da una CA non deve superare la metà del periodo di validità del certificato della CA di emissione.
  
In questo modo, i periodi massimi di validità per entità finali, CS di emissione e CA principali sono rispettivamente pari a quattro, otto e sedici anni. In questa soluzione, i certificati delle entità finali vengono conservati per un periodo massimo di due anni. In questo modo è possibile introdurre un livello CA intermedio aggiuntivo senza conseguenze rilevanti sulla struttura gerarchica della durata dei certificati.
  
#### Mapping dei requisiti di protezione con i parametri del certificato
  
Nella tabella seguente, vengono elencati i tipi di certificato precedentemente identificati nel capitolo e viene indicato come la categoria di protezione di ciascun tipo venga mappata con i parametri corrispondenti del profilo del certificato.
  
**Tabella 4.11. Parametri del certificato**

<p> </p>
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
<th><p>Tipo di certificato</p></th>  
<th><p>Criterio di emissione</p></th>  
<th><p>Metodo di approvazione</p></th>  
<th><p>Chiave</p></th>  
<th><p>Periodo di validità</p></th>  
<th><p>Archiviazione delle chiavi</p></th>  
<th><p>Esportazione chiave</p></th>  
<th><p>CSP</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazione client - Utente</p></td>
<td style="border:1px solid black;"><p>Bassa</p></td>
<td style="border:1px solid black;"><p>Automatico (autenticazione dominio)</p></td>
<td style="border:1px solid black;"><p>1024</p></td>
<td style="border:1px solid black;"><p>1 anno</p></td>
<td style="border:1px solid black;"><p>Software</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Nominato</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Autenticazione client - Computer</p></td>
<td style="border:1px solid black;"><p>Bassa</p></td>
<td style="border:1px solid black;"><p>Automatico</p>
<p>(autenticazione dominio)</p></td>
<td style="border:1px solid black;"><p>1024</p></td>
<td style="border:1px solid black;"><p>1 anno</p></td>
<td style="border:1px solid black;"><p>Software</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Nominato</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Autenticazione server IAS</p></td>
<td style="border:1px solid black;"><p>Media</p></td>
<td style="border:1px solid black;"><p>Manuale (Cert Manager)</p></td>
<td style="border:1px solid black;"><p>1024</p></td>
<td style="border:1px solid black;"><p>1 anno</p></td>
<td style="border:1px solid black;"><p>Software</p></td>
<td style="border:1px solid black;"><p>No</p></td>
<td style="border:1px solid black;"><p>Nominato</p></td>
</tr>  
</tbody>  
</table>
  
**Note:**   
il criterio “Low” riportato nella colonna **Criterio di emissione** si riferisce al criterio di certificazione predefinito “Low Assurance” di Servizi certificati. Tale criterio è equivalente alla garanzia o al livello di protezione standard descritti in una sezione precedente.  
Il valore “Nominato” nella colonna **CSP** (Cryptographic Service Provider, provider di servizi di crittografia) serve per indicare che è necessario specificare il provider CSP consentito dal tipo di certificato nel modello e non lasciarlo decidere al client. I certificati del computer client e del server dispongono di requisiti CSP specifici.
  
#### Mapping dei requisiti del certificato con i parametri del modello del certificato
  
Spesso le applicazioni richiedono una configurazione dei certificati ben precisa. Il nome del soggetto deve essere formattato in modo specifico, devono essere compresi gli OID dei criteri dell'applicazione oppure l'emissione del certificato deve avvenire con un criterio specifico. Per l'applicazione è comunque necessario che l'utilizzo della chiave sia stato definito in modo corretto. Per una corretta definizione del profilo del certificato, è necessario richiedere tali parametri al proprietario o al fornitore dell'applicazione.
  
Nelle tabelle riportate di seguito, vengono indicati i requisiti dell'applicazione per i certificati richiesti da questa soluzione. Nelle tabelle vengono indicati i parametri CA e le proprietà del certificato, sulla base della configurazione riportata nei modelli di certificato. Nell'elenco è riportata una parte delle proprietà possibili.
  
**Nota:** ciascun tipo di certificato descritto di seguito si basa su un tipo di modello incorporato. Invece di modificare i modelli originali per ottenere le impostazioni richieste, copiare i modelli incorporati e apportare le modifiche necessarie alle copie. In questo modo, sarà possibile ripristinare facilmente i modelli incorporati, se necessario.
  
**Tabella 4.12. Autenticazione client - Utente**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Parametro del certificato</p></th>  
<th><p>Valore richiesto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome del modello di certificato</p></td>
<td style="border:1px solid black;"><p>Autenticazione client - Utente</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Pubblicazione di Active Directory</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Utilizzo della chiave</p></td>
<td style="border:1px solid black;"><p>Firma digitale</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Archiviazione della chiave</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Dimensione minima della chiave</p></td>
<td style="border:1px solid black;"><p>1024</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Nome del soggetto</p></td>
<td style="border:1px solid black;"><p>Nome comune</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome alternativo del soggetto</p></td>
<td style="border:1px solid black;"><p>Nome principale dell'utente</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Criteri dell'applicazione/utilizzo avanzato delle chiavi</p></td>
<td style="border:1px solid black;"><p>Autenticazione client</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Provider del servizio di crittografia (CSP)</p></td>
<td style="border:1px solid black;"><p>Microsoft Base Cryptographic Provider versione 1.0</p>
<p>Microsoft Enhanced Cryptographic Provider versione 1.0</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Ricavato dal modello</p></td>
<td style="border:1px solid black;"><p>Sessione autenticata</p></td>
</tr>  
</tbody>  
</table>
  
**Tabella 4.13. Autenticazione client - Computer**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Parametro del certificato</p></th>  
<th><p>Valore richiesto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome del modello di certificato</p></td>
<td style="border:1px solid black;"><p>Autenticazione client - Computer</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Pubblicazione di Active Directory</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Utilizzo della chiave</p></td>
<td style="border:1px solid black;"><p>Firma digitale</p>
<p>Crittografia chiave</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Archiviazione della chiave</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Dimensione minima della chiave</p></td>
<td style="border:1px solid black;"><p>1024</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Nome del soggetto</p></td>
<td style="border:1px solid black;"><p>Nome comune</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome alternativo del soggetto</p></td>
<td style="border:1px solid black;"><p>Nome DNS</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Criteri dell'applicazione/utilizzo avanzato delle chiavi</p></td>
<td style="border:1px solid black;"><p>Autenticazione client</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Provider del servizio di crittografia (CSP)</p></td>
<td style="border:1px solid black;"><p>Microsoft RSA SChannel Cryptographic Provider</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Ricavato dal modello</p></td>
<td style="border:1px solid black;"><p>Autenticazione workstation</p></td>
</tr>  
</tbody>  
</table>
  
**Tabella 4.14. Autenticazione server mediante standard 802.1X**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="50%" />  
<col width="50%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Parametro del certificato</p></th>  
<th><p>Valore richiesto</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome del modello di certificato</p></td>
<td style="border:1px solid black;"><p>Autenticazione server mediante standard 802.1X</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Pubblicazione di Active Directory</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Utilizzo della chiave</p></td>
<td style="border:1px solid black;"><p>Firma digitale</p>
<p>Crittografia chiave</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><p>Archiviazione della chiave</p></td>
<td style="border:1px solid black;"><p>No</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Dimensione minima della chiave</p></td>
<td style="border:1px solid black;"><p>1024</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Nome del soggetto</p></td>
<td style="border:1px solid black;"><p>Nome comune</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Nome alternativo del soggetto</p></td>
<td style="border:1px solid black;"><p>Nome DNS</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Criteri dell'applicazione/utilizzo avanzato delle chiavi</p></td>
<td style="border:1px solid black;"><p>Autenticazione server</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Provider del servizio di crittografia (CSP)</p></td>
<td style="border:1px solid black;"><p>Microsoft RSA SChannel Cryptographic Provider</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Ricavato dal modello</p></td>
<td style="border:1px solid black;"><p>Server RAS e IAS</p></td>
</tr>  
</tbody>  
</table>
  
#### Creazione dei modelli di certificato
  
Il servizio Active Directory di Windows Server 2003 contiene un insieme di modelli di certificato predefiniti per la gestione delle funzioni più comuni. Le CA di livello aziendale, per impostazione predefinita, sono configurate per l'emissione di diversi tipi di certificati incorporati. Le descrizioni di tutti i modelli incorporati sono reperibili all'interno della documentazione di Windows Server 2003 Enterprise Edition. Per ulteriori dettagli, vedere la sezione "Ulteriori informazioni" alla fine del capitolo.
  
Nella presente guida, la maggior parte dei modelli predefiniti sono stati rimossi dalla CA, ovvero sono stati eliminati dalla cartella dei modelli della console di gestione dell'autorità di certificazione. Non eliminare le definizioni dei modelli dalla directory.
  
È possibile scegliere i modelli predefiniti, utilizzati dalla maggior parte delle applicazioni Windows basate su certificati (ad esempio Crittografia file system (EFS), autenticazione VPN e altre), a seconda delle proprie esigenze. Nel caso sia necessario emettere altri tipi di certificati, è preferibile creare modelli appositamente personalizzati. L'utilizzo di modelli predefiniti, senza conoscerne le caratteristiche, comporta rischi legati all'attivazione accidentale di funzionalità. Ad esempio, il certificato Computer, creato per la sola autenticazione di client, può anche essere utilizzato come certificato per server Web.
  
Per creare nuovi modelli, è necessario individuarne uno predefinito che risponda quanto più possibile ai requisiti del profilo del certificato e da cui creare un duplicato sul quale basare il nuovo modello. La configurazione dei modelli è costituita da una semplice procedura di selezione degli attributi da associare ai profili di certificato descritti nella presente sezione.
  
**Nota:** non è possibile creare un modello completamente nuovo. È necessario eseguire la copia da un modello esistente e modificarlo secondo le proprie esigenze. I modelli computer e utente devono essere sempre ricavati da modelli simili non interscambiabili.
  
Durante la creazione e la modifica di modelli, è necessario conservare una registrazione dettagliata dei parametri del modello all'interno del sistema di gestione della configurazione.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Creazione di un piano per la gestione dei certificati
  
Dopo aver configurato i certificati per l'organizzazione, è necessario creare un piano per la gestione che ne copra l'intero periodo di validità. Per la creazione di un piano di gestione dei certificati, è necessario considerare quanto segue.
  
-   Come vengono elaborate le richieste e il rinnovo di certificati
  
-   Come eseguire il mapping dei certificati con gli account utente
  
-   Come gestire e distribuire elenchi CRL
  
-   Strategie utilizzate per il ripristino dei dati crittografati
  
#### Selezione dei metodi di registrazione e rinnovo
  
È possibile eseguire la registrazione e il rinnovo del certificato tramite una delle seguenti procedure (è possibile utilizzarle tutte per il rinnovo dei certificati).
  
-   Registrazione automatica di Windows.
  
-   Registrazione in linea mediante Certificate Enrollment Wizard, che solitamente è possibile avviare dalla console di gestione dei certificati.
  
-   Registrazione in linea mediante l'utilizzo delle interfacce CryptoAPI o CAPICOM da applicazioni o da script.
  
-   Utilizzo dello strumento Certreq.exe per creare e inoltrare richieste, nonché per recuperare i certificati emessi.
  
    **Nota:** i quattro metodi sopra riportati rappresentano semplicemente differenti interfacce per la medesima modalità di registrazione in linea.
  
-   Registrazione tramite pagina Web.
  
-   Registrazione manuale non in linea: la procedura comporta la creazione di un file di richiesta tramite i metodi precedentemente descritti, l'invio della richiesta alla CA e il suo successivo inoltro tramite la console di gestione delle CA e il recupero tramite Microsoft Management Console.
  
Tutti questi metodi sono validi e appropriati se utilizzati in determinate circostanze. In questa soluzione vengono utilizzati i metodi di registrazione indicati di seguito.
  
-   Registrazione automatica di Windows. È preferibile utilizzare questo metodo, se possibile, per ridurre il carico di gestione dei certificati. È possibile utilizzare la procedura di registrazione automatica anche nel caso in cui sia necessaria un'approvazione manuale del certificato. Sebbene il certificato non venga emesso immediatamente, verrà inoltrata una richiesta all'Autorità di certificazione e la registrazione verrà completata a seguito dell'approvazione della richiesta.
  
-   Registrazione manuale non in linea: questo metodo viene utilizzato per tutte le procedure di registrazione e rinnovo dei certificati presso la CA principale.
  
Nessuno di questi metodi risulta adeguato per scenari più complessi, ad esempio, situazioni in cui sia necessaria la firma di una richiesta di certificato da parte di terzi prima dell'inoltro alla CA. La registrazione in linea basata su RPC non è supportata dalla maggior parte di piattaforme non Windows, ad esempio i router. Non è inoltre possibile eseguire la registrazione automatica in tutti i casi in cui è necessario definire il nome principale o alternativo del soggetto nella richiesta di certificato, piuttosto che demandarne la creazione al servizio Active Directory.
  
Per ovviare a situazioni di questo tipo, è necessario considerare uno dei metodi riportati di seguito.
  
-   Creare uno script CAPICOM da eseguire sul computer client autonomo, ad esempio all'interno di uno script di accesso.
  
-   Utilizzare lo strumento certereq.exe all'interno di un comando o di un file batch per creare e inoltrare richieste, nonché per recuperare e installare il certificato emesso.
  
-   È possibile creare una pagina Web personalizzata, in formato ASP o Microsoft ASP .NET, utilizzando uno script CAPICOM per creare e inoltrare la richiesta. In questo modo è possibile fornire servizi di registrazione per un'ampia gamma di client, includendo complesse procedure a più fasi, ad esempio, quando è necessario utilizzare più firme per approvare una singola richiesta.
  
#### Mapping dei certificati con le identità
  
Il mapping di certificati con i soggetti denominati nei certificati rappresenta un argomento di discussione che supera gli obiettivi prefissati dal presente capitolo. È tuttavia necessario considerare due aspetti importanti.
  
-   Il modo in cui l'identità del soggetto certificato viene confermata prima dell'emissione dello stesso.
  
-   Il modo in cui l'identità del soggetto certificato viene determinata sulla base delle informazioni fornite nella directory.
  
Il primo aspetto riguarda la modalità di elaborazione della procedura di registrazione del certificato, argomento trattato nella sezione "Creazione di criteri dei certificati". Il secondo problema si riferisce alle modalità con cui gli utenti (applicazioni e servizi) possono mappare correttamente l'identità del soggetto certificato con un'altra identità disponibile. Di seguito vengono riportati alcuni esempi.
  
-   Modalità con cui il controller di dominio identifica un utente sulla base del certificato di smart card, per consentire all'utente l'accesso al dominio e la creazione di un token di accesso.
  
-   Modalità con cui un utente di posta elettronica rileva il certificato di un altro utente a cui inviare un messaggio di posta elettronica protetto.
  
La maggior parte dei certificati vengono automaticamente mappati con identità di protezione (quali utenti e computer) di Active Directory nell'ambito della procedura di registrazione. Active Directory consente di definire il nome del soggetto e il nome alternativo del soggetto del certificato per creare un mapping implicito tra il certificato e l'identità di protezione nominata nel certificato. Nel nome alternativo del soggetto sarà contenuto l'UPN o il nome di posta elettronica di un utente, il nome principale servizio (SPN) o il nome host DNS di un computer o di un processo informatico. I valori UPN e SPN sono sempre univoci nell'insieme di strutture di Active Directory. È necessario che i nomi di posta elettronica e DNS siano univoci, sebbene per Active Directory non venga esplicitamente richiesto. Anche altri servizi di Windows, ad esempio IIS e IAS, sono in grado di eseguire il mapping dei certificati con le identità degli utenti o dei computer.
  
**Nota:** il mapping dei certificati non è associato alla pubblicazione dei certificati. Con mapping di certificati si indica la presenza di alcuni attributi del certificato (di solito il nome alternativo del soggetto) che identificano in modo univoco un oggetto nella directory. Un server IAS utilizza tale funzione per determinare l'identità di un utente o di un computer da un certificato presentato. IAS utilizza il mapping implicito piuttosto che l'individuazione dei certificati in una directory. La pubblicazione del certificato e la relativa funzione di ricerca dei certificati indicano la posizione corrente nella directory dei certificati come attributi di oggetti computer o utente. Un utente può quindi cercare un altro utente nella directory e recuperare certificati appartenenti a questa persona.
  
È inoltre possibile importare manualmente o mappare altri certificati con oggetti utente o computer, utilizzando la console di gestione Utenti e computer di Active Directory.
  
Esistono, d'altra parte, numerosi casi in cui il mapping diretto a un oggetto directory non è richiesto, tra cui:
  
-   Server Web in cui l'identificatore principale corrisponde al nome host DNS del sito Web.
  
-   Situazioni in cui i certificati vengono emessi a identità che non dispongano di un equivalente in Active Directory, ad esempio un router o un utente di un'altra organizzazione.
  
Tutte le entità finali menzionate in questa guida dispongono del mapping diretto (e implicito) con gli utenti e i computer di Active Directory.
  
Le CA rappresentano casi speciali poiché non vengono necessariamente mappate con oggetti computer. Tuttavia, generalmente verranno mappate con oggetti autorità di certificazione nei contenitori di accesso alle informazioni dell'autorità (AIA) e delle autorità di certificazione attendibili.
  
#### Creazione di criteri dei certificati
  
È necessario definire il metodo di approvazione del certificato almeno per ogni categoria di protezione (alta, media e standard) e spesso anche per ogni categoria del soggetto certificato, quali computer e utente interno o esterno. È comunque molto improbabile che occorra definire i criteri con maggiore precisione. Nelle dichiarazioni delle procedure e dei criteri di certificazione, occorre includere le scelte relative ai criteri adottati.
  
I diversi criteri di certificazione vengono utilizzati per indicare il tipo di procedura di approvazione dei certificati e del livello di protezione della chiave privata utilizzati nell'ambito della registrazione di un certificato. Tali informazioni possono essere codificate (ma non è obbligatorio) all'interno del certificato tramite oggetti OID in grado di rappresentare i singoli criteri. Il rigore della procedura di approvazione riflette il valore del certificato in fase di emissione. L'obiettivo della procedura di approvazione o registrazione è fornire un livello di attendibilità che garantisca la corrispondenza tra il richiedente e il soggetto certificato. Il livello di crittografia della chiave rappresenta la misura del livello di attendibilità riposto nel soggetto certificato, in quanto unico possessore della chiave privata.
  
I livelli di garanzia offerti dai certificati utilizzati in questa guida sono stati definiti in precedenza nella sezione "Definizione dei requisiti di protezione dei certificati" del presente capitolo. È possibile indicare il livello di garanzia del certificato emesso, includendo un OID del criterio di certificazione corrispondente al livello di garanzia dei certificati. Il criterio può essere utilizzato da applicazioni e da utenti per determinare il grado di affidabilità di un certificato specifico.
  
In Windows Server 2003, i tre livelli di garanzia definiti in precedenza vengono mappati con tre criteri di certificazione predefiniti, chiamati Criteri di emissione in MMC Modelli di certificato. La tabella seguente fornisce ulteriori dettagli sull'utilizzo dei diversi criteri di certificazione nella presente guida. È necessario includere gli OID dei criteri  , almeno per i certificati con garanzia media ed elevata, all'interno dei modelli di certificato in modo da facilitare l'identificazione di certificati con livelli di garanzia superiori. I certificati senza criteri del certificato vengono considerati con garanzia standard.
  
**Tabella 4.15. Livelli dei criteri di emissione dei certificati**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Criteri (di emissione) dei certificati</p></th>  
<th><p>Requisiti di registrazione</p></th>  
<th><p>Requisiti minimi di archiviazione della chiave</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Bassa</p>
<p>(Standard)</p></td>
<td style="border:1px solid black;"><p>Approvazione automatica a seconda dell'esito dell'autenticazione di dominio.</p>
<p>Per le CA autonome, si tratta del livello di approvazione non autenticato, ovvero il caso in cui la CA emette il certificato senza eseguire la verifica del richiedente.</p></td>
<td style="border:1px solid black;"><p>Chiavi software</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Media</p></td>
<td style="border:1px solid black;"><p>Approvazione del responsabile certificati.</p>
<p>All'interno del criterio, occorre definire i tipi di verifiche eseguite dal responsabile certificati prima dell'approvazione della richiesta.</p></td>
<td style="border:1px solid black;"><p>Chiavi software o hardware.</p>
<p>Con le chiavi software, è necessario utilizzare una protezione avanzata, in tutti i casi in cui è supportata dall'applicazione. Ad esempio, i certificati di computer non possono utilizzare una protezione con livello di crittografia elevato.</p></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><p>Alto</p></td>
<td style="border:1px solid black;"><p>Firma del responsabile della registrazione e approvazione del responsabile certificati</p>
<p>È necessario definire i tipi di controllo che devono essere eseguiti dai responsabili della registrazione e dal responsabile certificati prima che la richiesta venga approvata.</p></td>
<td style="border:1px solid black;"><p>Token hardware a prova di alterazione.</p>
<p>Ad esempio, token di crittografia USB o smart card per un utente o HSM per un computer.</p></td>
</tr>
</tbody>
</table>
<p> </p>

**Nota:** le motivazioni che possono portare alla definizione di un numero maggiore o minore di criteri dei certificati o di livelli di garanzia dipendono solo dai requisiti dell'organizzazione.

#### Definizione dei criteri di revoca dei certificati

In alcune situazioni è necessario invalidare un certificato prima del termine del periodo di validità. La creazione di criteri per la revoca dei certificati comporta le seguenti attività:

-   Definizione delle condizioni di garanzia della revoca di un certificato.

-   Selezione di una posizione per la pubblicazione degli elenchi CRL.

-   Selezione dei tipi di elenchi CRL che si desidera utilizzare.

-   Creazione di pianificazioni per la pubblicazione di elenchi CRL.

Nei criteri di certificazione, occorre includere la definizione delle condizioni di garanzia della revoca di un certificato, che può variare in base al tipo di certificato utilizzato. La variazione è più evidente per i certificati con livelli di garanzia e tipi di soggetto differenti, nonché per l'autorità di certificazione.

È necessario, inoltre, documentare l'eventuale l'utilizzo di codici motivo da utilizzare durante la revoca di un certificato. Nella tabella seguente vengono riportati i diversi codici motivo.

**Tabella 4.16. Codici di revoca dei certificati**

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Codice motivo</p></th>
<th><p>Descrizione</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Compromissione chiave</p></td>
<td style="border:1px solid black;"><p>La chiave privata del certificato è stata compromessa o se ne sospetta la compromissione.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Compromissione della CA</p></td>
<td style="border:1px solid black;"><p>La chiave privata della CA è stata compromessa o se ne sospetta la compromissione.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Modifica di affiliazione</p></td>
<td style="border:1px solid black;"><p>Il soggetto è passato a un'altra organizzazione.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Sostituzione</p></td>
<td style="border:1px solid black;"><p>È stato emesso un nuovo certificato in sostituzione di quello in uso.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Termine operatività</p></td>
<td style="border:1px solid black;"><p>La CA non è più operativa.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Sospensione certificato</p></td>
<td style="border:1px solid black;"><p>L'utilizzo di un certificato deve essere temporaneamente sospeso: ad esempio, nel caso in cui l'utente abbia accidentalmente smarrito la smart card, pur non essendone certo.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Non specificato</p></td>
<td style="border:1px solid black;"><p>Qualsiasi motivo che non corrisponda ai codici precedentemente indicati.</p></td>
</tr>  
</tbody>  
</table>
  
**Importante:** utilizzare il codice motivo Sospensione certificato solo nei casi di effettiva necessità. La sospensione e il successivo rilascio del certificato non consentono in alcun modo di determinare lo stato di revoca del certificato e conseguentemente la validità di una firma effettuata da tale certificato in un dato momento.
  
Nella procedura di revoca, includere gli elementi riportati di seguito, che verranno archiviati in un registro di gestione delle modifiche o dei problemi di protezione.
  
-   Motivo della revoca del certificato.
  
-   Utente che ha richiesto la revoca del certificato.
  
-   Eventuale necessità del certificato in futuro: ad esempio, per la verifica delle firme o la decrittografia dei messaggi. In caso affermativo, considerare per quale delle procedure indicate sopra (verifica delle firme, decrittografia dei messaggi o utilizzo normale) potrebbe tornare utile.
  
-   Eventuali requisiti speciali dell'utente che revoca il certificato e che devono essere soddisfatti dall'amministratore, ad esempio nel caso in cui l'utente è un responsabile certificati.
  
-   Eventuale presenza di procedure operative documentate per l'organizzazione da adempiere per revocare i certificati, ad esempio l'esecuzione di un backup.
  
Esiste inoltre un'ampia varietà di parametri tecnici che regolamentano la revoca dei certificati, che si consiglia di includere nel criterio della CA. In questa guida, i parametri riportati nelle tabelle seguenti sono destinati alle CA principali e di emissione.
  
**Tabella 4.17. Parametri di revoca dei certificati della CA principale**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Parametro</p></th>  
<th><p>Valore prescelto</p></th>  
<th><p>Motivo</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Posizioni pubblicazioni CRL (CDP)</p></td>
<td style="border:1px solid black;"><p>Percorso HTTP al server Web interno</p></td>
<td style="border:1px solid black;"><p>La pubblicazione nel server Web consente di eseguire il backup del percorso LDAP e ai client non LDAP di accedere all'elenco CRL.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Percorso LDAP al contenitore CDP di Active Directory</p></td>
<td style="border:1px solid black;"><p>La pubblicazione a tutti i controller di dominio consente un accesso in locale facilitato a tutti gli utenti del dominio.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Tipo di CRL</p></td>
<td style="border:1px solid black;"><p>Solo Base CRL</p></td>
<td style="border:1px solid black;"><p>A causa del ridotto numero di certificati emessi, l'utilizzo di Delta CRL.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Pianificazione pubblicazione</p></td>
<td style="border:1px solid black;"><p>Sei mesi</p></td>
<td style="border:1px solid black;"><p>Poiché tale procedura renda difficile la revoca dei certificati CA, l'impostazione del livello di protezione della CA richiede una certa attendibilità. Tuttavia, un periodo di tempo così esteso limita al minimo la gestione della CA principale.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Periodo di sovrapposizione degli elenchi CRL, ovvero l'intervallo di tempo compreso tra la pubblicazione di un nuovo elenco CRL e la scadenza di un elenco CRL obsoleto.</p></td>
<td style="border:1px solid black;"><p>10 giorni</p></td>
<td style="border:1px solid black;"><p>Questa procedura prevede un margine di errore utilizzabile per il recupero del nuovo elenco CRL dalla CA principale.</p></td>
</tr>  
</tbody>  
</table>
  
**Tabella 4.18. Parametri di revoca dei certificati della CA di emissione**

<p> </p>
<table style="border:1px solid black;">  
<colgroup>  
<col width="33%" />  
<col width="33%" />  
<col width="33%" />  
</colgroup>  
<thead>  
<tr class="header">  
<th><p>Parametro</p></th>  
<th><p>Valore prescelto</p></th>  
<th><p>Motivo</p></th>  
</tr>  
</thead>  
<tbody>  
<tr class="odd">
<td style="border:1px solid black;"><p>Posizioni pubblicazioni CRL (CDP)</p></td>
<td style="border:1px solid black;"><p>Percorso LDAP al contenitore CDP di Active Directory, per gli elenchi CRL Base e Delta.</p></td>
<td style="border:1px solid black;"><p>La pubblicazione a tutti i controller di dominio consente un accesso in locale facilitato a tutti gli utenti del dominio.</p>
<p>Vedere la nota seguente relativa alla pubblicazione di Delta CRL in Active Directory.</p></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Percorso HTTP al server Web interno</p></td>
<td style="border:1px solid black;"><p>La pubblicazione nel server Web consente di eseguire il backup del percorso LDAP e ai client non LDAP di accedere all'elenco CRL.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Tipo di CRL</p></td>
<td style="border:1px solid black;"><p>Base CRL</p>
<p>Delta CRL</p></td>
<td style="border:1px solid black;"><p>Gli elenchi Delta CRL sono utili per ottimizzare il traffico di recupero degli elenchi CRL, offrendo un minimo intervallo di latenza prima della pubblicazione delle informazioni di revoca.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Pianificazione pubblicazione</p></td>
<td style="border:1px solid black;"><p>Base CRL: sette giorni</p></td>
<td style="border:1px solid black;"><p>Tale intervallo dovrà essere sufficientemente frequente da consentire ai sistemi che non riconoscono gli elenchi Delta CRL, di ricevere comunque informazioni di revoca relativamente aggiornate.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><br />
</td>
<td style="border:1px solid black;"><p>Delta CRL: un giorno</p></td>
<td style="border:1px solid black;"><p>Per i client moderni, in grado di utilizzare gli elenchi Delta CRL, tale procedura offre un intervallo di latenza relativamente ridotto.</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Periodo di sovrapposizione degli elenchi Base CRL, ovvero l'intervallo compreso tra la pubblicazione di un nuovo elenco CRL e la scadenza di un elenco CRL obsoleto</p></td>
<td style="border:1px solid black;"><p>Quattro giorni</p></td>
<td style="border:1px solid black;"><p>Questa procedura prevede un margine di errore utilizzabile per il recupero della CA, in caso quest'ultima non sia in grado di pubblicare un elenco Base CRL nei tempi prestabiliti. È stato prescelto un valore pari a quattro giorni prevedendo il caso limite di un arresto anomalo della CA durante un venerdì sera e della successiva individuazione il martedì successivo.</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Periodo di sovrapposizione degli elenchi Delta CRL</p></td>
<td style="border:1px solid black;"><p>1 giorno</p></td>
<td style="border:1px solid black;"><p>Poiché gli elenchi Delta CRL non sono fondamentali per il funzionamento del servizio, eventuali errori durante la pubblicazione di un elenco Delta CRL non determinano un evento catastrofico. Questo valore viene impostato in modo che si sovrapponga alla latenza della replica di Active Directory.</p></td>
</tr>  
</tbody>  
</table>
  
**Nota:** poiché vengono utilizzati elenchi Delta CRL con una durata relativamente ridotta (un giorno), è necessario assicurarsi che il valore massimo di latenza della replica di Active Directory sia inferiore al 50 per cento del periodo di pubblicazione dell'elenco Delta CRL. In caso contrario potrebbe verificarsi che i client dei certificati utilizzino informazioni di revoca non aggiornate o che il traffico dati legato alla replica delle directory verso siti a larghezza di banda limitata, subisca un rallentamento. Impostare il periodo di sovrapposizione degli elenchi Delta CRL su un valore superiore al tempo massimo impiegato per la replica delle informazioni relative alle directory attraverso l'insieme di strutture.  
Se la latenza di Active Directory supera questo valore o se si desidera evitare la generazione di tale traffico di dati, aumentare il periodo di pubblicazione degli elenchi Delta CRL o evitare la pubblicazione degli elenchi Delta CRL nella directory. Se si modificano le posizioni degli elenchi CRL, sarà necessario emettere un nuovo elenco Base CRL.  
La latenza della replica non rappresenta un problema significativo quando si utilizzano percorsi HTTP piuttosto che URL LDAP per la pubblicazione di Delta CRL.
  
#### Pianificazione del ripristino di chiavi e dati
  
Le procedure di ripristino delle chiavi e dei dati non rientrano negli obiettivi della presente guida. Nel caso si presenti la necessità di attuare le procedure sopra indicate, sarà necessario effettuarne una pianificazione e una gestione accurata per evitare la perdita di dati e la divulgazione accidentale dei dati crittografati.
  
Per ulteriori informazioni sull'argomento, leggere le sezioni “Planning for Data Recovery and Key Recovery” e “Designing a Public Key Infrastructure” disponibili nel "*Windows Server 2003 Deployment Kit*" e il documento tecnico Microsoft "Key Archival and Management in Windows Server 2003".
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
Nel presente capitolo viene illustrata la procedura di progettazione di un'infrastruttura a chiave pubblica (PKI, Public key Infrastructure) per una soluzione di rete LAN senza fili protetta (WLAN). Considerando la probabilità che in molte organizzazioni l'infrastruttura PKI verrà utilizzata per altre applicazioni, nella progettazione presentata nella presente guida si è tenuto conto di tale problema. La progettazione presentata nel presente capitolo è abbastanza flessibile da consentirne l'estensione per soddisfare numerosi requisiti futuri. È possibile utilizzare queste informazioni per progettare un'infrastruttura PKI sufficientemente protetta da soddisfare criteri di protezione più rigidi di quelli richiesti dall'applicazione WLAN.
  
Le decisioni relative alla progettazione descritte nel presente capitolo verranno utilizzate nella Guida alla creazione e nella Guida operativa per l'implementazione dell'infrastruttura PKI. Tali informazioni sono illustrate in dettaglio nei capitoli 7 e 11 della guida.
  
Nei capitoli rimanenti della presente Guida alla pianificazione, viene spiegato come progettare gli altri componenti principali indicati: l'infrastruttura RADIUS, implementata tramite il Servizio autenticazione Internet (IAS), e l'infrastruttura di protezione della rete LAN senza fili.
  
#### Ulteriori informazioni
  
I riferimenti elencati di seguito forniscono informazioni fondamentali e dettagliate relative a molti degli argomenti trattati nel capitolo:
  
-   Il capitolo del *Windows Server 2003 Deployment Kit* “[Designing a Public Key Infrastructure](http://go.microsoft.com/fwlink/?linkid=4735)” all’indirizzo http://go.microsoft.com/fwlink/?LinkId=4735.
  
-   Per un’introduzione generale ai concetti di base delle infrastrutture PKI e all’utilizzo di Servizi certificati in Windows 2000, vedere [*An Introduction to the Windows 2000 Public-Key Infrastructure*](http://www.microsoft.com/technet/archive/windows2000serv/evaluate/featfunc/pkiintro.mspx) all'indirizzo http://www.microsoft.com/technet/archive/windows2000serv/evaluate/  
    featfunc/pkiintro.mspx.
  
-   Per una descrizione dettagliata delle funzionalità avanzate dell'infrastruttura PKI in Windows Server 2003 e Windows XP, vedere [*PKI Enhancements in Windows XP Professional and Windows Server 2003*](http://technet.microsoft.com/en-us/library/bb457034.aspx) all'indirizzo http://technet.microsoft.com/en-us/library/bb457034.aspx .
  
-   Nella documentazione di Windows 2003 Server Enterprise Edition [Public Key Infrastructure](http://technet.microsoft.com/en-us/library/cc779826.aspx) vengono illustrati i concetti chiave e le attività di gestione dei Servizi certificati. La documentazione è disponibile sul sito Internet all'indirizzo http://technet.microsoft.com/en-us/library/cc779826.aspx
  
-   Per ulteriori informazioni sulla creazione di una dichiarazione delle procedure di certificazione, vedere il documento RFC2527, [*Internet X.509 Public Key Infrastructure Certificate Policy and Certification Practices Framework,*](http://www.ietf.org/rfc/rfc2527.txt.) all'indirizzo www.ietf.org/rfc/rfc2527.txt.
  
-   Per un esempio di dichiarazione CPS, vedere la pagina [VeriSign Certification Practice Statement (CPS)](http://www.verisign.com/repository/cps/) all'indirizzo www.verisign.com/repository/CPS.
  
-   Per ulteriori informazioni su come vengono codificati i criteri OID e gli URL per le CPS in un certificato, vedere il documento RFC 3280, [*Internet X.509 Public Key Infrastructure Certificate and CRL Profile*](http://www.ietf.org/rfc/rfc3280.txt.), all'indirizzo www.ietf.org/rfc/rfc3280.txt.
  
-   Per ulteriori informazioni sulla subordinazione qualificata, vedere il documento tecnico [*Planning and Implementing Cross-Certification and Qualified Subordination Using Windows Server 2003*](http://technet.microsoft.com/en-us/library/cc787237.aspx) all'indirizzo http://technet.microsoft.com/en-us/library/cc787237.aspx
  
-   Per una spiegazione dettagliata sulle differenze tra le CA versione Enterprise e le CA autonome, vedere la sezione[Certification Authorities](http://technet.microsoft.com/en-us/library/cc738346.aspx) nella documentazione di Servizi certificati all'indirizzo http://technet.microsoft.com/en-us/library/cc738346.aspx .
  
-   Per ulteriori informazioni sull'abilitazione dell'accesso LDAP anonimo in Windows Server 2003, vedere l'articolo Q326690 della Microsoft Knowledge Base “[Anonymous LDAP operations to Active Directory are disabled on Windows Server 2003 domain controllers](http://support.microsoft.com/default.aspx?scid=326690)" all'indirizzo http://support.microsoft.com/default.aspx?scid=326690.
  
-   Per informazioni dettagliate sulla revoca dei certificati, vedere[*Troubleshooting Certificate Status and Revocation*](http://technet.microsoft.com/en-us/library/cc700843.aspx) all'indirizzo http://technet.microsoft.com/en-us/library/cc700843.aspx . La sezione relativa alle estensioni CDP si ricollega in particolar modo ad alcuni concetti presentati in questo capitolo.
  
-   Per ulteriori informazioni sull'installazione e sull'utilizzo delle pagine di registrazione Web di Servizi certificati, vedere la pagina Web dedicata alla [documentazione del prodotto Windows Server 2003](http://www.microsoft.com/windowsserver2003/proddoc/default.mspx) all'indirizzo http://www.microsoft.com/windowsserver2003/proddoc/default.mspx, quindi effettuare una ricerca per Security, Public Key Infrastructure, Certificate Services, How to... e Set up a Certification Authority.
  
-   Per istruzioni dettagliate sui modelli di certificato, vedere [*Implementing and Administering Certificate Templates in Windows Server 2003*](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/ws03crtm.mspx) all'indirizzo http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    technologies/security/ws03crtm.mspx.
  
-   Le descrizioni di tutti i modelli incorporati sono reperibili all'interno della documentazione di Windows Server 2003 nella sezione [Troubleshooting](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/proddocs/entserver/ctcon_tshoot.mspx) all'indirizzo http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    proddocs/entserver/ctcon\_tshoot.mspx.
  
-   Per ulteriori informazioni sulla registrazione automatica dei certificati, vedere [*Certificate Autoenrollment in Windows Server 2003*](http://technet.microsoft.com/en-us/library/cc778954.aspx) all'indirizzo http://technet.microsoft.com/en-us/library/cc778954.aspx .
  
-   Per informazioni relative all'archiviazione e alla gestione delle chiavi in Windows Server 2003, vedere il documento tecnico [*Key Archival and Management in Windows Server 2003*](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/kyacws03.mspx)all'indirizzo http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    technologies/security/kyacws03.mspx.
  
-   Per ulteriori informazioni sugli scenari avanzati relativi alla registrazione dei certificati, vedere il documento[*Advanced Certificate Enrollment and Management*](http://technet.microsoft.com/en-us/library/cc782583.aspx) all'indirizzo http://technet.microsoft.com/en-us/library/cc782583.aspx .
  
-   Per informazioni dettagliate sull'implementazione di un'infrastruttura PKI di Windows Server 2003, vedere il documento "[Best Practices for Implementing a Microsoft Windows Server 2003 Public Key Infrastructure](http://www.microsoft.com/technet/prodtechnol/windowsserver2003/technologies/security/ws3pkibp.mspx)" all'indirizzo http://www.microsoft.com/technet/prodtechnol/windowsserver2003/  
    technologies/security/ws3pkibp.mspx.
  
-   Ulteriori informazioni sull'implementazione sono disponibili in Microsoft Systems Architecture version 2.0 Implementation Guide, che può essere scaricata dal sito Web [Windows Server System Reference Architecture](http://www.microsoft.com/downloads/details.aspx?familyid=d44e34ec-b4e2-49a1-9f40-9ed4ba3765df&displaylang=en)http://www.microsoft.com/downloads/details.aspx?familyid=D44E34EC-B4E2-49A1-9F40-9ED4BA3765DF&displaylang;=en .
  
[](#mainsection)[Inizio pagina](#mainsection)
