---
TOCTitle: 'Guida alla pianificazione della protezione di reti LAN senza fili: introduzione'
Title: 'Guida alla pianificazione della protezione di reti LAN senza fili: introduzione'
ms:assetid: '1ba7635e-55a4-4cd6-b7c7-20249a5acea3'
ms:contentKeyID: 20200853
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536254(v=TechNet.10)'
---

Pianifica la protezione di una LAN wireless con Windows Server 2003 Certificate Services
========================================================================================

### Guida alla pianificazione della protezione di reti LAN senza fili: introduzione

##### In questa pagina

[](#edaa)[Argomenti del modulo](#edaa)
[](#ecaa)[Destinatari della Guida](#ecaa)
[](#ebaa)[Convenzioni di stile](#ebaa)

### Argomenti del modulo

La *Guida alla pianificazione della protezione di reti LAN senza fili* si applica alla soluzione *Microsoft® Windows® Server™ 2003 Certificate Services*. Il presente è il primo di diversi gruppi di moduli che costituiscono la Guida. Gli obiettivi principali della *Guida alla pianificazione* sono due: facilitare l'utente nel prendere decisioni informate rispetto all'adeguatezza di questa soluzione per la propria attività; offrire un'approfondita descrizione della progettazione tecnica relativa alla soluzione e di tutte le considerazioni che sono alla base delle decisioni che hanno portato al progetto.

La Guida è divisa in tre parti, concatenate in una progressione logica. Nella prima parte, "[Scelta di una strategia di rete senza fili protetta](http://technet.microsoft.com/it-it/library/dd536255)", vengono prese in esame le motivazioni aziendali che portano all'adozione di reti LAN senza fili (WLAN, Wireless LAN) e messe a confronto con i rischi di sicurezza che possono rendere vulnerabili molte implementazioni WLAN. La discussione viene utilizzata come base per proporre una strategia di protezione per l'implementazione delle reti WLAN. Nella seconda parte, "[Architettura della soluzione di rete LAN senza fili protetta](http://technet.microsoft.com/it-it/library/dd536256)", partendo dalla strategia WLAN proposta, viene elaborato un progetto di soluzione logica, identificando i componenti principali da implementare. I moduli "[Progettazione di un'infrastruttura a chiave pubblica](http://technet.microsoft.com/it-it/library/dd536257)", "[Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili](http://technet.microsoft.com/it-it/library/dd536258)" e "[Progettazione della protezione di reti LAN senza fili mediante lo standard 802.1X](http://technet.microsoft.com/it-it/library/dd536259)", rappresentano l'ultima parte, ma anche la più importante, della Guida. Illustrano inoltre come progettare in dettaglio ognuno dei componenti identificati nel modulo "Architettura della soluzione di rete LAN senza fili protetta." Il contenuto di questi moduli è descritto in maggior dettaglio più avanti.

A differenza di altre guide alla pianificazione, questa intende fornire indicazioni ben precise sull'implementazione. Lo scopo è quello di produrre un singolo progetto funzionale che possa essere utilizzato come riferimento per questo tipo di soluzione. Nei punti del documento in cui si rendono disponibili diverse opzioni di progettazione, vengono discusse le motivazioni delle decisioni prese e, dove necessario, vengono indicate strategie facoltative. L'intento è di offrire agli utenti informazioni sufficienti a discostarsi dal progetto nel caso in cui siano necessarie modifiche funzionali alla propria attività. La finalità complessiva della Guida è tuttavia quella di arrivare a una singola soluzione implementabile che faccia riferimento a soluzioni già operative e verificate, che funzionino esattamente come descritto.

#### Guida alla pianificazione della protezione di reti LAN senza fili: introduzione

In questo modulo vengono fornite le informazioni di base che illustrano il resto della Guida.

#### Scelta di una strategia di rete senza fili protetta

Questo modulo si incentra sulla scelta di una soluzione per la protezione di una rete senza fili. Vengono prese in esame le motivazioni che portano un'azienda all'adozione della tecnologia WLAN e i problemi legati alla protezione che vanno considerati per poter adottare la soluzione senza problemi. Il modulo analizza quindi come risolvere i problemi di protezione e propone una soluzione basata sull'autenticazione avanzata e la protezione dei dati, che prevede l'utilizzo di certificati a chiave pubblica. Le decisioni si basano sulle esigenze di protezione previste per organizzazioni di medie e grandi dimensioni e tengono conto tanto delle necessità immediate di protezione avanzata quanto di prospettive a lungo termine che dimostrino come la soluzione protegga l'investimento che su di essa è stato fatto.

#### Architettura della soluzione di rete LAN senza fili protetta

Questo modulo illustra la progettazione di una soluzione per la protezione di una rete senza fili. Il punto di partenza è una panoramica sul funzionamento di una soluzione WLAN basata sugli standard 802.1X ed EAP. I componenti chiave della soluzione sono indicati di seguito.

-   Infrastruttura WLAN che supporta l'autenticazione avanzata e gli standard di protezione dei dati.

-   Infrastruttura di autenticazione RADIUS (Remote Authentication Dial-in User Service).

-   Infrastruttura a chiave pubblica (PKI, Public key Infrastructure).

I requisiti di protezione indicati nel modulo precedente vengono inseriti nel profilo dell'organizzazione di destinazione e utilizzati per elaborare un insieme di criteri di progettazione per la soluzione. Viene quindi illustrata la progettazione logica basata su questi criteri e sono indicate le opzioni per adeguare questo schema a organizzazioni di dimensioni diverse.

Infine, il modulo illustra come il progetto proposto possa essere utilizzato come base per la creazione di altre soluzioni di accesso alla rete, ad esempio una rete privata virtuale (VPN, Virtual Private Network) e un controllo di accesso alla rete cablata. Viene infine proposta una breve discussione sull'utilizzo del componente PKI a supporto di una vasta gamma di servizi e applicazioni di protezione.

#### Progettazione di un'infrastruttura a chiave pubblica

Questo modulo prende in esame la progettazione di un'infrastruttura PKI basata su Servizi certificati Microsoft. Oltre alla protezione della rete WLAN, è probabile che molte organizzazioni intendano utilizzare la propria infrastruttura PKI per altre applicazioni, quali posta elettronica protetta, crittografia di file, accesso con smart card e così via. Il progetto dovrà pertanto integrare una soluzione di certificazione relativamente semplice e a basso costo per reti WLAN protette e una che fornisca la protezione e la flessibilità necessarie per supportare numerose e differenti applicazioni.

È necessario che la documentazione del certificato sia seguita dalla definizione di un'adeguata gerarchia dell'autorità di certificazione (CA, Certification Authority). Vengono inoltre presi in esame aspetti quali l'integrazione delle CA con il servizio directory Microsoft Active Directory®, con Microsoft Internet Information Services (IIS) e con altre infrastrutture PKI. Infine, viene descritto lo sviluppo di un piano di gestione dei certificati e la creazione di modelli di certificato.

#### Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili

Questo modulo offre una progettazione dettagliata dell'infrastruttura RADIUS utilizzata per fornire servizi di autenticazione avanzata e di gestione protetta delle chiavi nella rete WLAN. Viene inoltre illustrata una panoramica del modo in cui l'infrastruttura RADIUS, implementata utilizzando il servizio IAS (Internet Authentication Service) di Microsoft, possa essere utilizzata per fornire un'ampia soluzione di gestione dell'accesso alla rete e come si applichi in particolare alle reti WLAN. Nel modulo vengono elencati i requisiti ambientali per la soluzione e discusse in dettaglio le decisioni relative alla progettazione di un'infrastruttura RADIUS per una rete WLAN basata sullo standard 802.1X. Vengono inoltre considerate le strategie di gestione per la manutenzione nel tempo dell'infrastruttura del server IAS.

#### Progettazione della protezione di reti LAN senza fili mediante lo standard 802.1X

Questo modulo descrive l'architettura e la progettazione di aspetti legati alla protezione delle reti senza fili. Non vengono prese in esame le problematiche di progettazione che non fanno riferimento alla protezione. Gli argomenti trattati descrivono come una soluzione basata sullo standard 802.1X può risolvere le vulnerabilità di protezione nelle reti WLAN basate su WEP (Wired Equivalent Privacy), come scegliere tra l'utilizzo di certificati o di password e, infine, come identificare i requisiti per una distribuzione efficace. Nelle sezioni successive viene presa in esame la selezione delle opzioni di protezione WLAN e la configurazione di tali opzioni nei criteri di accesso per infrastrutture RADIUS, punti di accesso (AP) senza fili e client, mediante l'utilizzo dei criteri di gruppo. Infine, il modulo analizza alcune questioni chiave relative alla distribuzione, ad esempio i profili comuni e l'avvio della configurazione di client senza fili.

[](#mainsection)[Inizio pagina](#mainsection)

### Destinatari della Guida

Questa Guida è rivolta principalmente a progettisti e responsabili dei processi decisionali aziendali nei settori IT, sebbene per questi ultimi risulti particolarmente pertinente solo il modulo "Scelta di una strategia di rete senza fili protetta". I progettisti IT potranno prestare particolare attenzione ai moduli "Scelta di una strategia di rete senza fili protetta" e "Architettura della soluzione di rete LAN senza fili protetta", nonché a tutti i punti principali dei moduli rimanenti. In alcune organizzazioni, i vari componenti della soluzione possono essere gestiti da diversi gruppi. In questo caso, i singoli specialisti potranno focalizzarsi sui moduli relativi ai propri ambiti di esperienza.

I progettisti IT potranno inoltre approfondire i contenuti della *Guida all'implementazione*, della *Guida operativa* e della *Guida per i test*, in modo da verificare che queste siano coerenti con le strategie IT globali dell'organizzazione.

I professionisti IT addetti alle fasi di implementazione, distribuzione e gestione della soluzione potranno approfondirne l'architettura e il progetto complessivo.

Tutta la Guida, ma in particolare gli ultimi moduli, si rivolge ai professionisti IT che si occupano di sicurezza. È fondamentale che i responsabili della sicurezza IT dell'organizzazione abbiano letto e approvato le indicazioni di progettazione, implementazione e operatività prima di procedere con la distribuzione e prima che il sistema entri nella fase di produzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Convenzioni di stile

**Tabella 1. Convenzioni di stile**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Significato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Grassetto</strong></td>
<td style="border:1px solid black;">Caratteri digitati esattamente come indicato, inclusi comandi e opzioni. Vengono riportati in grassetto anche gli elementi di interfaccia utente nel testo delle istruzioni.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><em>Corsivo</em></td>
<td style="border:1px solid black;">Segnaposto per variabili nei punti in cui è necessario inserire valori specifici. Ad esempio, <em>Nomefile.ext</em> indica che è necessario sostituire il testo in corsivo <em>nomefile.ext</em> con il nome del file di propria scelta.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Testo su schermo</td>
<td style="border:1px solid black;">Indica il testo visualizzato sullo schermo.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">
<pre><code>Spaziatura fissa</code></pre>
<br />
</td>
<td style="border:1px solid black;">Esempi di codice.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">%SystemRoot%</td>
<td style="border:1px solid black;">Cartella di installazione del sistema operativo Microsoft Windows 2000.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Nota</strong></td>
<td style="border:1px solid black;">Richiama l'attenzione del lettore su informazioni supplementari.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Importante</strong></td>
<td style="border:1px solid black;">Richiama l'attenzione del lettore su informazioni supplementari essenziali per il completamento dell'operazione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Avviso</strong></td>
<td style="border:1px solid black;">Avvisa il lettore che l'inosservanza di un'azione specifica potrebbe provocare una perdita di dati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Attenzione</strong></td>
<td style="border:1px solid black;">Avvisa il lettore che l'inosservanza di un'azione specifica potrebbe provocare lesioni fisiche all'utente o danni all'hardware.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
