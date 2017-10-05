---
TOCTitle: 'Guida alla pianificazione - Architettura della soluzione di rete LAN senza fili protetta'
Title: 'Guida alla pianificazione - Architettura della soluzione di rete LAN senza fili protetta'
ms:assetid: '90ee676c-2215-4446-8db3-3acb99944ddd'
ms:contentKeyID: 20200843
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536244(v=TechNet.10)'
---

Capitolo 3: Architettura della soluzione di rete LAN senza fili protetta
========================================================================

Pubblicato: 11 ottobre 2004 | Aggiornato: 24/11/2004

##### In questa pagina

[](#efaa)[Introduzione](#efaa)
[](#eeaa)[Progettazione concettuale](#eeaa)
[](#edaa)[Criteri di progettazione della soluzione](#edaa)
[](#ecaa)[Progettazione logica della soluzione](#ecaa)
[](#ebaa)[Riesame dei criteri di progettazione](#ebaa)
[](#eaaa)[Riepilogo](#eaaa)

### Introduzione

Nel capitolo precedente, sono state illustrate le opzioni per la protezione delle reti LAN senza fili (WLAN) e le motivazioni della scelta dell'autenticazione senza fili basata sullo standard 802.1X con il protocollo EAP-TLS (Extensible Authentication Protocol-Transport Layer Security) per questa soluzione. In questo capitolo, vengono descritte l'architettura della soluzione e una progettazione logica ottenuta utilizzando i criteri di progettazione di un'azienda campione.  Queste informazioni possono essere utilizzate come base per l'implementazione della soluzione. La progettazione logica si basa su hardware di rete WLAN 802.1X, autenticazione RADIUS (Remote Authentication Dial-In User Service) e un'infrastruttura a chiave pubblica (PKI).

#### Prima di iniziare

È necessario comprendere i concetti della progettazione dell'infrastruttura IT, nonché dei suoi componenti chiave: i componenti di rete e WLAN, RADIUS, il servizio directory Active Directory® e le infrastrutture PKI, sebbene non sia richiesta una conoscenza approfondita di questi elementi.

#### Panoramica dei capitoli

Lo scopo di questo capitolo è:

-   Fornire una panoramica concettuale delle modalità di funzionamento di una soluzione di rete WLAN protetta basata sulle tecnologie 802.1X e EAP-TLS e dei componenti chiave di questo tipo di soluzione.

-   Definire i criteri di progettazione di questa soluzione per la progettazione logica e le fasi successive della progettazione tecnica dettagliata.

-   Produrre una progettazione logica coerente che costituisca le basi per una progettazione dettagliata nei capitoli seguenti.

-   Descrivere le modalità di scalabilità della soluzione per soddisfare le esigenze di aziende di dimensioni diverse.

-   Illustrare alcuni dei metodi di estensione della progettazione proposta o del suo utilizzo come base per la creazione di altre soluzioni di accesso alla rete, tra cui reti private virtuali (VPN) e controllo di accesso alla rete cablata, ed esaminare le modalità di impiego del componente PKI della progettazione come modello per una varietà di applicazioni di protezione.

Nei capitoli successivi, verrà esaminato il processo di progettazione dettagliato per ciascuno dei componenti principali della progettazione logica (WLAN, RADIUS e PKI) come preparazione per la creazione e l'implementazione della soluzione.

[](#mainsection)[Inizio pagina](#mainsection)

### Progettazione concettuale

Già nel capitolo precedente sono state descritte numerose vulnerabilità inerenti alla sicurezza delle reti senza fili. Queste vulnerabilità vengono, nel migliore dei casi, solo parzialmente eliminate mediante l'uso di tecnologie WEP (Wired Equivalent Privacy) come specificato nello standard IEEE (Institute of Electrical and Electronics Engineers) 802.11. La soluzione proposta in questa guida consente di migliorare la protezione delle comunicazioni di rete senza fili. A tal fine, la soluzione ideale deve presentare le seguenti caratteristiche:

-   Autenticazione affidabile dei client senza fili, inclusa l'autenticazione reciproca del client, del punto di accesso (AP, Access Point) senza fili e del server RADIUS.

-   Processo di autorizzazione per identificare gli utenti autorizzati ad accedere alla rete senza fili.

-   Controllo dell'accesso per consentire l'accesso alla rete solo ai client autorizzati.

-   Crittografia avanzata del traffico di rete senza fili.

-   Gestione protetta delle chiavi di crittografia.

-   Capacità di recupero da attacchi di negazione del servizio (DoS, Denial of Service).  

La combinazione dello standard 802.1X per il controllo degli accessi di rete con un metodo di autenticazione protetto come EAP-TLS soddisfa alcuni di questi requisiti. Il WEP di alto livello garantisce una crittografia relativamente protetta del traffico di rete, ma riduce le funzionalità di gestione delle chiavi. I metodi di gestione delle chiavi di crittografia WEP che utilizzano 802.1X ed EAP sono molto più affidabili di quelli basati sugli standard 802.11. Lo standard WPA (WiFi Protected Access) è una raccolta di standard di settore che comprende 802.1X ed EAP (tra gli altri miglioramenti) e un protocollo standardizzato per la gestione delle chiavi, noto come TKIP (Temporal Key Integrity Protocol). L’introduzione di questo standard rappresenta un notevole passo avanti per la protezione della rete WLAN ed è stato avallato dalla maggior parte degli analisti e dei fornitori.

**Nota:** nessuno dei miglioramenti WPA è in grado di risolvere i punti deboli DoS relativi alle tecnologie 802.11 e 802.1X. I punti deboli DoS non sono tanto gravi come quelli WEP e quasi tutti gli attacchi di questo tipo dimostrati causano solo un’interruzione temporanea della rete. Tuttavia, gli attacchi di negazione del servizio rappresentano ancora un serio problema per alcune organizzazioni che, probabilmente, non potrà essere risolto prima del rilascio dello standard IEEE 802.11i nel 2004.

Sebbene la protezione WPA sia ampiamente supportata, molti dispositivi e sistemi esistenti potrebbero non essere compatibili con questo standard. Di conseguenza, la soluzione per questa guida è stata realizzata per gestire entrambe le implementazioni di WPA e WEP dinamico. La maggior parte dei fornitori di hardware di rete vendono prodotti che supportano l'autenticazione 802.1X con WPA e chiavi WEP dinamiche. Relativamente allo scopo di questo capitolo di progettazione, i due approcci verranno trattati indistintamente poiché l'uso dell'uno rispetto all'altro non produce alcun impatto significativo sulla progettazione.

Nella figura seguente, viene riportata una vista concettuale della soluzione (autenticazione 802.1X EAP-TLS).

[![](images/Dd536244.03fig3-1(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-1_big(it-it,technet.10).gif)

**Figura 3.1 Soluzione concettuale basata sull'autenticazione 802.1X EAP-TLS**

Nella figura, sono illustrati quattro principali componenti:

-   **Client senza fili** Questo componente è un computer o una periferica in cui viene eseguita un'applicazione che richiede l'accesso alle risorse di rete. Il client è in grado di crittografare il traffico di rete, di archiviare e scambiare le credenziali in modo protetto (ad esempio chiavi o password).

-   **Punto di accesso senza fili** Nella terminologia di rete generica, questo componente è noto come NAS (Network Access Service), ma in termini di standard di rete viene denominato punto di accesso (AP). Il punto di accesso senza fili è in grado di implementare le funzioni di controllo dell'accesso per consentire o negare l'accesso alla rete e di crittografare il traffico senza fili. Inoltre, consente di condividere in modo protetto le chiavi di crittografia con il client al fine di proteggere il traffico di rete. Infine può inviare query a un servizio di autenticazione e di autorizzazione per le decisioni di autorizzazione.

-   **Servizio autenticazione (AS)** È in grado di archiviare e verificare le credenziali di utenti validi e di prendere decisioni di autorizzazione in base a un criterio di accesso. Inoltre consente di raccogliere le informazioni di accounting e di controllo sull'accesso client alla rete. Il server RADIUS è il componente principale del servizio di autenticazione, sebbene la directory e la CA contribuiscano a svolgere questa funzione.

-   **Rete interna** Si tratta di un'area protetta dei servizi di rete necessaria per l'applicazione client senza fili al fine di ottenere l'accesso.  

I numeri riportati nella figura illustrano il processo di accesso alla rete, che verrà descritto in dettaglio nella procedura riportata di seguito:

1.  Il client senza fili deve definire le credenziali con un servizio di autenticazione prima di stabilire l'accesso di rete senza fili. Questa operazione può essere eseguita mediante alcuni strumenti fuori banda, ad esempio un disco floppy oppure una rete cablata o altra rete protetta.

2.  Se il computer client è compreso nell'intervallo del punto di accesso senza fili, tenta di connettersi alla rete WLAN attiva su tale punto di accesso. La rete WLAN viene individuata in base al relativo identificatore del set di servizi (SSID). Il client rileva l'SSID della rete WLAN e lo usa per identificare le impostazioni corrette e il tipo di credenziali appropriato per questa rete.

    Il punto di accesso senza fili viene configurato in modo da consentire solo connessioni protette con l'autenticazione 802.1X. Quando il client tenta di connettersi al punto di accesso senza fili, quest'ultimo invia una richiesta al client, quindi imposta un canale con restrizioni che consente al client di comunicare solo con il server RADIUS. Questo canale blocca l'accesso al resto della rete. Il server RADIUS accetterà una connessione solo da un punto di accesso senza fili attendibile o da uno configurato come client RADIUS nel server IAS (Servizio autenticazione Internet) di Microsoft e in grado di fornire il segreto condiviso per tale client RADIUS.

    Il client tenta di eseguire l'autenticazione nel server RADIUS tramite il canale con restrizioni utilizzando l'autenticazione 802.1X. Durante la negoziazione EAP-TLS, il client stabilisce una sessione TLS (Transport Layer Security) con il server RADIUS. L'utilizzo di una sessione TLS è finalizzato ai seguenti scopi:

    -   Consente al client di eseguire l'autenticazione del server RADIUS; pertanto il client stabilirà la sessione esclusivamente con un server in possesso di un certificato ritenuto attendibile dal client stesso.

    -   Consente al client di fornire le sue credenziali dei certificati al server RADIUS.

    -   Protegge lo scambio di autenticazione dall'analisi del pacchetto.

    -   La negoziazione della sessione TLS genera una chiave che può essere utilizzata dal client e dal server RADIUS per stabilire chiavi principali comuni, le quali consentono di ricavare le chiavi utilizzate per la crittografia del traffico di rete WLAN.

    Durante questo scambio, il traffico all'interno del tunnel TLS è visibile solo al client e al server RADIUS e non viene mai esposto al punto di accesso senza fili.

3.  Il server RADIUS convalida le credenziali del client in base alla directory. Se il client viene autenticato, il server RADIUS raccoglie le informazioni che gli consentono di decidere se autorizzare o meno il client a utilizzare la rete WLAN. Il server utilizza le informazioni della directory (ad esempio, l'appartenenza ai gruppi) e le limitazioni definite nel relativo criterio di accesso (ad esempio, l'orario in cui è consentito l'accesso alla rete WLAN) per consentire o negare l'accesso al client. Il server RADIUS inoltra, quindi, tale decisione al punto di accesso.

4.  Se è stato consentito l'accesso al client, il server RADIUS trasmette la chiave principale del client al punto di accesso senza fili. A questo punto, il client e il punto di accesso condividono i dati della chiave comune, che possono utilizzare per crittografare e decrittografare il traffico WLAN che si scambiano.

    Se si utilizza il WEP dinamico per crittografare il traffico, le chiavi principali devono essere modificate periodicamente per impedire attacchi di recupero delle chiavi WEP. Questa operazione viene eseguita dal server RADIUS forzando regolarmente il client a eseguire una nuova autenticazione e a generare un nuovo set di chiavi.

    Se le comunicazioni vengono protette tramite WPA, i dati della chiave principale vengono utilizzati per ricavare le chiavi di crittografia dei dati, che vengono modificate per ogni pacchetto trasmesso. Per garantire la protezione delle chiavi, non è necessario che WPA forzi una nuova autenticazione periodica.

5.  Il punto di accesso stabilisce la connessione WLAN client alla rete LAN interna, fornendo al client un accesso senza restrizioni ai sistemi della rete interna. A questo punto, il traffico inviato tra il client e il punto di accesso viene crittografato.

6.  Se è necessario un indirizzo IP per il client, quest'ultimo può richiedere un lease DHCP (Dynamic Host Configuration Protocol) a un server della rete LAN. Dopo l'assegnazione dell'indirizzo IP, il client può iniziare a scambiare informazioni con i sistemi presenti sul resto della rete.

La figura riportata di seguito visualizza questo processo in maniera più dettagliata.

[![](images/Dd536244.03fig3-2(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-2_big(it-it,technet.10).gif)

**Figura 3.2 Processo di accesso 802.1X EAP-TLS**

In questa figura i singoli componenti vengono illustrati in maniera più dettagliata. Le sezioni successive di questo capitolo faranno riferimento a questa figura; tuttavia, per il momento, è necessario porre l'attenzione sui sottocomponenti del servizio di autenticazione: autorità di certificazione (CA, Certification Authority), directory e RADIUS. Sebbene questi sottocomponenti eseguano concettualmente una serie di attività relativamente semplici, per effettuare queste operazioni in modo protetto e in una modalità che sia scalabile, gestibile e affidabile, è necessaria un'infrastruttura alquanto sofisticata. La maggior parte dei processi di pianificazione, implementazione e gestione necessari a questo scopo è descritta nei restanti capitoli di questa guida.

[](#mainsection)[Inizio pagina](#mainsection)

### Criteri di progettazione della soluzione

Dopo aver descritto i concetti di base della soluzione, è necessario approfondire i principali criteri di progettazione per la soluzione. Tali criteri forniranno le istruzioni per convertire la soluzione in una progettazione che possa essere effettivamente implementata.

I criteri di progettazione sono ricavati in base ai requisiti di un'organizzazione tipica che implementa questa soluzione. Nelle sezioni seguenti vengono descritte questa organizzazione e i suoi principali requisiti tecnici.

#### Organizzazione di destinazione

L'organizzazione descritta in questa sezione è intesa solo a fornire un contesto per i criteri di progettazione. Quando si valuta l'idoneità della soluzione, è opportuno valutare se i criteri di progettazione sono validi per la propria azienda e non se la propria azienda corrisponde esattamente a quella descritta in questo capitolo.

L'organizzazione di destinazione per questa soluzione ha distribuito una rete WLAN in alcune sedi in modo da ridurre i costi di infrastruttura di rete ed aumentare la mobilità e la produttività del personale. L'organizzazione è consapevole delle esigenze inerenti alla protezione e ha già distribuito una serie di tecnologie per il miglioramento della protezione IT, ad esempio l'autenticazione di dominio, firewall Internet, programmi antivirus e una soluzione di accesso remoto o VPN. Ha già sviluppato piani a lungo termine al fine di utilizzare numerose altre applicazioni altamente protette (come ad esempio la crittografia dei file e la posta elettronica protetta).

La struttura di rete logico-fisica semplificata di questa organizzazione può somigliare a quella raffigurata nella seguente figura:

[![](images/Dd536244.03fig3-3(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-3_big(it-it,technet.10).gif)

**Figura 3.3 Diagramma schematico della rete e della struttura fisica dell'organizzazione di destinazione**

Sebbene nella figura siano raffigurati solo due filiali, rispettivamente di grandi e piccole dimensioni, in realtà potrebbero esistere diversi uffici di questo tipo. Per maggiore chiarezza, nell'esempio è riportato solo un piccolo numero di server e client  e questo non vuole essere in alcun modo indicativo delle dimensioni dell'organizzazione.

Entro certi limiti, le dimensioni dell'organizzazione di destinazione hanno relativamente scarso impatto sui criteri di progettazione della soluzione. All'estremità più piccola della scala, la sede centrale può ospitare alcune centinaia di dipendenti e possedere piccole filiali con decine di dipendenti. All'estremità più grande della scala, la sede centrale può ospitare migliaia di dipendenti e possedere uffici periferici con centinaia di dipendenti. Ad entrambe le estremità della scala, le organizzazioni presentano anche filiali più piccole con un numero non elevato di dipendenti.

#### Requisiti dell'organizzazione

I seguenti requisiti sono tipici dell'organizzazione descritta in questo scenario:

-   L'organizzazione deve migliorare la protezione della rete WLAN per eliminare o ridurre notevolmente i seguenti rischi:

    -   Intrusi che intercettano le trasmissioni di dati attraverso la rete WLAN.

    -   Intrusi che intercettano e modificano le trasmissioni di dati attraverso la rete WLAN.

    -   Intrusi o altri utenti non autorizzati che si collegano alla rete WLAN introducendo virus o altro codice dannoso sulla rete interna.

    -   Attacchi di negazione del servizio a livello di rete (piuttosto che a livello di trasmissione radio).

    -   Intrusi che utilizzano la rete aziendale WLAN per ottenere l'accesso a Internet.

-   Le misure di protezione non devono ridurre l'utilizzabilità della rete o indurre un aumento significativo delle chiamate all'helpdesk.

-   I costi di distribuzione e di gestione continuativa devono essere sufficientemente bassi da essere giustificabili per un numero relativamente piccolo di utenti (meno del 10% della forza lavoro) che utilizzano questa soluzione WLAN.

-   La progettazione deve supportare una vasta gamma di client e periferiche.

Oltre a questi requisiti esiste un numero di requisiti tecnici più generali:

-   Deve essere mantenuta una capacità di recupero in caso di guasti a singoli componenti.

-   Deve esistere una scalabilità per la gestione di livelli di utilizzo più elevati in futuro, possibilmente oltre il 100% della forza lavoro esistente. Il costo per il supporto di un numero maggiore di utenti deve essere minimo o almeno proporzionale all'espansione richiesta.

-   Riutilizzabilità dei componenti, se possibile.  La soluzione deve riutilizzare l'infrastruttura esistente e qualsiasi nuovo componente introdotto dalla soluzione deve poter essere riutilizzato in progetti futuri.

-   L'infrastruttura di gestione e di controllo esistente deve conformarsi facilmente alla nuova soluzione.

-   In caso di danni irreversibili (ad esempio, ripristinando i backup su hardware alternativo) devono essere mantenute le funzioni di recupero.

-   La soluzione deve essere conforme ai protocolli e ai formati standard di settore e,  laddove non esistono standard, deve essere in linea con standard futuri.

-   La soluzione deve fornire una protezione affidabile (compreso l’aggiornamento periodico) delle credenziali e delle chiavi.

-   Devono essere fornite informazioni di controllo totale per la registrazione utente e l'accesso client alla rete.

#### Criteri di progettazione della soluzione

Da questi requisiti, è possibile determinare i criteri riportati nella seguente tabella per supportare la progettazione della soluzione.

**Tabella 3.1: criteri di progettazione della soluzione**

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Fattore di progettazione</th>
<th style="border:1px solid black;" >Criteri</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Protezione</td>
<td style="border:1px solid black;">- Autenticazione e autorizzazione affidabili dei client senza fili.
- Controllo dell'accesso affidabile per limitare l'accesso alla rete ai client autorizzati.
- Crittografia di alto livello del traffico di rete senza fili.
- Gestione protetta delle chiavi di crittografia.
– Capacità di recupero in caso di attacchi di negazione del servizio.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Scalabilità</td>
<td style="border:1px solid black;">Progettazione di base con scalabilità crescente e decrescente per adattarsi a una vasta gamma di organizzazioni.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">- Numero min/max di utenti supportati.</td>
<td style="border:1px solid black;">- Da 500 a 15.000 utenti WLAN e oltre.
- Da 500 a 15.000 utenti dei certificati e oltre.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">- Numero di siti supportati.</td>
<td style="border:1px solid black;">- Siti di grandi dimensioni, con controller del dominio di autenticazione locale e IAS (Microsoft Internet Authentication Service), supportati con capacità di recupero in caso di guasti alla rete WAN (Wide Area Network).
- Siti di piccole dimensioni supportati senza capacità di recupero in casi di guasti alla rete WAN.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Riutilizzo dei componenti (uso dell’infrastruttura esistente)</td>
<td style="border:1px solid black;">Utilizzo di  Active Directory, dei servizi di rete e dei client Microsoft Windows® XP.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Riutilizzo dei componenti (utilizzabilità da parte delle applicazioni future)</td>
<td style="border:1px solid black;">- Supporto per altre applicazioni di accesso alla rete (accesso alla rete VPN e alla rete cablata 802.1X) mediante l’infrastruttura di autenticazione.
- Supporto per una varietà di applicazioni, quali EFS (Encrypting File System) e VPN, mediante l’infrastruttura PKI.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Disponibilità</td>
<td style="border:1px solid black;">Capacità di recupero in caso di guasto a singoli componenti o al collegamento di rete.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Espansione</td>
<td style="border:1px solid black;">- Espandibile per supportare capacità e standard futuri (ad esempio, 802.11i, WPA, 802.11a per WLAN).
- Infrastruttura di certificazione espandibile per supportare gli usi più frequenti dei certificati a chiave pubblica (posta elettronica protetta, accesso con smart card, firma del codice e protezione del servizio Web).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Facilità di gestione</td>
<td style="border:1px solid black;">Integrazione con le soluzioni di gestione aziendale esistenti (comprende il controllo del sistema e del servizio, il backup e la gestione della configurazione).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Struttura dell’organizzazione IT</td>
<td style="border:1px solid black;">Scelta del reparto IT centralizzato (almeno cinque ma generalmente 20-30 persone).</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Conformità agli standard</td>
<td style="border:1px solid black;">Adesione ai principali standard correnti e chiaro percorso di migrazione verso i principali standard futuri.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Progettazione logica della soluzione
  
In questa sezione viene descritta la progettazione logica e logico-fisica della soluzione. Questa presenta le specifiche e il posizionamento dei componenti attuali, sebbene non vengano inclusi i dettagli della progettazione fisica, come ad esempio le specifiche hardware del server.
  
#### Analisi della progettazione concettuale
  
Tramite la seguente figura (utilizzata in precedenza nel capitolo), questa sezione illustra il modo in cui i diversi componenti si combinano tra loro all’interno della progettazione complessiva.
  
[![](images/Dd536244.03fig3-4(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-4_big(it-it,technet.10).gif)
  
**Figura 3.4 Vista concettuale del processo di accesso alla rete**
  
#### Progettazione logica
  
La divisione dei componenti logici nella figura precedente facilitava la comprensione del processo di accesso alla rete WLAN. Tuttavia, per semplificare la distribuzione e la gestione, è preferibile raggruppare nuovamente i componenti.
  
Il raggruppamento dei componenti consente di esaminare l’intera progettazione in maniera modulare per un riutilizzo ottimale di tali componenti. Ad esempio, il componente PKI potrebbe essere implementato semplicemente per l'autenticazione degli utenti di rete WLAN. Tuttavia, questo potrebbe limitare la riutilizzabilità del componente PKI per altre applicazioni. Allo stesso modo, il componente RADIUS per la soluzione deve essere progettato tenendo presente ciò che le altre applicazioni potrebbero richiedere per eventuali usi futuri.
  
I servizi IT presenti nella progettazione vengono raggruppati nelle seguenti categorie:
  
-   Componenti WLAN - Client e punti di accesso senza fili
  
-   Componente RADIUS
  
-   Componente PKI - Autorità di certificazione (CA)
  
-   Componente dei servizi di infrastruttura
  
Quest'ultimo componente comprende una directory e servizi di rete di supporto, che sono costituiti da servizi IT che in genere esistono già nell’organizzazione, con cui la soluzione in qualche modo interagisce.
  
[![](images/Dd536244.03fig3-5(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-5_big(it-it,technet.10).gif)
  
**Figura 3.5 Progettazione logica della soluzione di rete WLAN protetta**
  
##### Livello logico-fisico
  
A livello logico-fisico, attualmente la progettazione illustra come questi componenti verranno implementati come server fisici, come verranno collegati tra loro e come verranno distribuiti tra i diversi siti dell’organizzazione di destinazione. Tuttavia, i numeri dei server riportati nella seguente figura sono generici. La definizione finale dei numeri e del posizionamento dei server verrà discussa nei capitoli successivi relativi alla pianificazione della presente guida.
  
###### Sedi centrali
  
Nella seguente figura viene illustrata l’implementazione del server nella sede centrale. Solo i tre componenti riportati nella parte superiore della figura rappresentano i nuovi server o i componenti che devono essere acquistati. I componenti dei servizi di infrastruttura esistono già nella maggior parte delle organizzazioni. Se l’organizzazione ha già distribuito l’apparecchiatura di rete WLAN in grado di supportare la tecnologia 802.1X, anche il componente di rete WLAN potrebbe già esistere.
  
[![](images/Dd536244.03fig3-6(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-6_big(it-it,technet.10).gif)
  
**Figura 3.6 Implementazione del server nella sede centrale**
  
###### Filiale di grandi dimensioni
  
Nella seguente figura è illustrata la struttura fisica di una filiale di grandi dimensioni, che si distingue dalla filiale di piccole dimensioni in quanto dispone di un controller di dominio locale. All’ufficio remoto viene distribuito un solo server IAS. Sebbene sia raffigurato come un server separato, il server IAS può essere eseguito come un servizio del controller di dominio.
  
**Nota:** se il collegamento WAN alla sede centrale è affidabile (vale a dire che esistono collegamenti di rete ridondanti) e non eccessivamente congestionato, la filiale di grandi dimensioni può utilizzare i servizi RADIUS della sede centrale invece dei propri. Questo argomento verrà discusso più avanti nel capitolo 5, "Progettazione di un'infrastruttura RADIUS per la protezione di reti LAN senza fili".
  
Tutti gli altri servizi (ad esempio, i servizi CA) vengono forniti dalla sede centrale.
  
[![](images/Dd536244.03fig3-7(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-7_big(it-it,technet.10).gif)
  
**Figura 3.7 Struttura fisica di una filiale di grandi dimensioni**
  
###### Filiale di piccole dimensioni
  
La filiale di piccole dimensioni può disporre di un'infrastruttura IT, ad esempio, un file server e una stampante, ma generalmente non dispone di un’infrastruttura di autenticazione. Alcune organizzazioni ritengono che questi uffici non richiedano o giustifichino alcun servizio WLAN. Per altre organizzazioni, invece, il fatto di utilizzare uffici temporanei, senza che sia necessario installare e gestire cavi di rete, rappresenta una prospettiva interessante.
  
Se i servizi WLAN sono necessari per gli uffici di piccole dimensioni che non dispongono di un controller di dominio locale, i punti di accesso senza fili locali si baseranno sul server IAS e sull’infrastruttura di autenticazione di dominio presenti nelle sedi centrali. Il problema principale di questo approccio è che la connettività di rete WLAN andrà persa se si verifica un guasto al collegamento WAN alla sede centrale. Questo problema può essere risolto (con costi aggiuntivi) fornendo una ridondanza WAN o distribuendo controller di dominio locali, sebbene non esista una facile soluzione a questo scenario.
  
Se la capacità di recupero della rete WAN o l'utilizzo di controller di dominio locali nelle piccole filiali dell'organizzazione è troppo costoso, un'alternativa è distribuire punti di accesso senza fili isolati tramite la modalità WPA con chiave già condivisa (PSK). Attualmente, tutti i punti di accesso senza fili certificati Wi-Fi supportano la protezione WPA. Sebbene sia molto più sicura del WEP statico, questa opzione richiede un ulteriore sovraccarico di gestione.
  
[![](images/Dd536244.03fig3-8(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-8_big(it-it,technet.10).gif)
  
**Figura 3.7 Struttura fisica di una filiale di piccole dimensioni**
  
##### Strategia di scalabilità
  
Uno dei principali criteri di progettazione è assicurare la scalabilità. La soluzione deve essere in grado di supportare implementazioni di diverse dimensioni a costi adeguati al tipo di implementazione (vale a dire che un’implementazione di 500 utenti deve avere un costo proporzionalmente inferiore a quella di 5000 utenti). La complessità dell’implementazione e della gestione della soluzione deve essere anche conforme al tipo di organizzazione.
  
###### Organizzazione di grandi dimensioni
  
Nella seguente figura sono illustrate le modalità di scalabilità della progettazione in modo da poter ospitare un elevato numero di utenti sia nella sede centrale che nelle filiali di grandi dimensioni. Inoltre è probabile che i server IAS utilizzino altre applicazioni di rete, come ad esempio VPN. Per ulteriori informazioni su questo argomento, consultare la sezione "Facilità di estensione della progettazione*"* di questo capitolo. Questo aspetto potenzialmente può incidere sul numero e sulla struttura esatta dei server. I server IAS supplementari vengono mostrati nella figura seguente solo a scopo illustrativo.
  
Gli ulteriori server richiesti per la versione adattata della soluzione sono raffigurati in grigio.
  
[![](images/Dd536244.03fig3-9(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-9_big(it-it,technet.10).gif)
  
**Figura 3.9 Soluzione adattata per un'organizzazione di grandi dimensioni**
  
###### Organizzazione di piccole dimensioni
  
Per le organizzazioni di piccole dimensioni, la soluzione può essere implementata con un numero contenuto di nuovi componenti hardware e software. Questo risultato si ottiene eseguendo il servizio IAS sui controller di dominio esistenti. Tale configurazione è stata già ampiamente collaudata dal gruppo IAS di Microsoft ed è consigliata per numerosi scenari. Nella seguente figura è illustrata questa variante della progettazione.
  
[![](images/Dd536244.03fig3-10(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-10_big(it-it,technet.10).gif)
  
**Figura 3.10 Soluzione adattata per un'organizzazione di piccole dimensioni**
  
Il componente RADIUS è ancora illustrato nella figura come un elemento logicamente separato (in modo da poter effettuare un confronto con la struttura della figura precedente), anche se è ora implementato come un servizio sui controller di dominio già esistenti. Gli unici server richiesti in questa versione della soluzione sono i server CA che risiedono nell'area dell’infrastruttura a chiave pubblica della progettazione della soluzione.
  
#### Facilità di estensione della progettazione
  
Un altro criterio chiave della progettazione della soluzione è la riutilizzabilità dei componenti in applicazioni future. È possibile riutilizzare i componenti RADIUS e PKI per fornire l’autenticazione e altri servizi di protezione per una varietà di applicazioni.
  
##### Altri servizi di accesso alla rete
  
La progettazione RADIUS di questa soluzione può fornire servizi di autenticazione, autorizzazione e accounting per altri server di accesso alla rete, quali l'autenticazione di rete cablata basata sullo standard 802.1X e l'autenticazione di accesso remoto e VPN.
  
###### Autenticazione di rete cablata basata sullo standard 802.1X
  
L’applicazione più semplice, che non richiede alcuna modifica della progettazione RADIUS WLAN di base, è l’autenticazione cablata 802.1X. Le organizzazioni dotate di un’infrastruttura di rete cablata ampiamente distribuita potrebbero incontrare delle difficoltà nel controllare l’uso non autorizzato della rete aziendale. Ad esempio, spesso è difficile impedire che i visitatori colleghino i computer portatili o che i dipendenti aggiungano computer non autorizzati alla rete. Alcune parti della rete, ad esempio i centri dati, possono essere designate come zone altamente protette. In queste zone altamente protette sono consentite solo periferiche autorizzate, escludendo persino i dipendenti con computer aziendali.
  
Nella figura seguente è illustrata la modalità di integrazione della soluzione di accesso a una rete cablata con la progettazione: nell'area con i margini in grassetto sono rappresentati i componenti cablati basati sullo standard 802.1X, mentre le altre aree della struttura contengono i servizi rilevanti visualizzati nella figura di progettazione precedente.
  
[![](images/Dd536244.03fig3-11(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-11_big(it-it,technet.10).gif)
  
**Figura 3.11 Utilizzo dell'autenticazione cablata 802.1X**
  
Le reti che utilizzano gli switch 802.1X svolgono un ruolo identico a quello dei punti di accesso senza fili all’interno della soluzione di base e possono sfruttare la stessa infrastruttura RADIUS per autenticare i client e autorizzare in modo selettivo l’accesso al segmento di rete appropriato. Questa versione della soluzione include i tipici vantaggi della centralizzazione della gestione degli account nella directory aziendale, lasciando i criteri di accesso alla rete sotto il controllo dell’amministratore della protezione della rete.
  
###### Autenticazione della connessione remota e VPN
  
Un altro servizio di accesso alla rete che potrebbe utilizzare i componenti RADIUS è la connessione remota e VPN. Specialmente nelle organizzazioni di grandi dimensioni, è probabile che sia necessario apportare alcune aggiunte alla progettazione, ad esempio l'aggiunta di proxy RADIUS. La struttura di questa soluzione estesa è illustrata nella seguente figura.
  
[![](images/Dd536244.03fig3-12(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-12_big(it-it,technet.10).gif)
  
**Figura 3.12 Estensione del componente RADIUS per il supporto della connessione VPN**
  
I server VPN di questa soluzione svolgono lo stesso ruolo NAS dei punti di accesso senza fili all’interno della progettazione di base: passano le richieste di autenticazione dei client all'infrastruttura RADIUS. Sebbene sia possibile passare le richieste RADIUS direttamente ai server IAS interni, è più sicuro utilizzare un livello proxy RADIUS per inoltrare le richieste ai server IAS interni.
  
Questa soluzione offre i vantaggi di sfruttare l’infrastruttura esistente e di centralizzare la gestione degli account, lasciando il controllo dei criteri di accesso sotto la supervisione dell’amministratore della protezione della rete. Alla strategia di protezione globale fornita dalla soluzione vengono aggiunti ulteriori miglioramenti, ad esempio la richiesta dell’autenticazione utente basata sulla smart card. Microsoft utilizza una configurazione molto simile per consentire al proprio personale interno di connettersi in modo sicuro alla rete aziendale.
  
L’accesso remoto funziona in modo analogo, utilizzando la funzionalità server di connessione remota del servizio Routing e accesso remoto di Windows, anziché le funzionalità VPN.
  
Un altro vantaggio derivante dall’uso del componente RADIUS (in particolare di IAS) in questo scenario consiste nella capacità di utilizzare i criteri di *quarantena*. Questo sistema sfrutta il servizio Routing e accesso remoto di Microsoft Windows Server 2003 e Connection Manager (il client di accesso remoto di Windows) per consentire o negare l'accesso in base allo stato di protezione del computer client. Mediante questa configurazione, IAS può verificare che il client soddisfi determinati requisiti quando si collega alla rete. Ad esempio, questa procedura controlla che il client disponga di software antivirus aggiornato o esegua una versione del sistema operativo approvata dall'azienda. Se uno di questi controlli ha esito negativo, il server RADIUS nega l'accesso del client alla rete. Pertanto è possibile che l'accesso venga negato anche a un utente o a un computer regolarmente autenticato nel caso in cui rappresenti un possibile pericolo per la protezione della rete aziendale.
  
##### Applicazioni PKI
  
Poiché i criteri di riutilizzabilità e di estensione della soluzione sono importanti, il componente PKI è stato progettato in modo da poter essere utilizzato in futuro per diverse applicazioni di protezione. Come verrà descritto nel capitolo successivo, la progettazione del componente PKI rappresenta pertanto una strategia di riduzione dei costi e della complessità come parte di una soluzione senza fili protetta e di mantenimento della flessibilità, in modo tale da essere utilizzata come base per altre applicazioni future.
  
Nella seguente figura vengono illustrate alcune delle applicazioni che il componente PKI può supportare, oltre all’applicazione senza fili protetta. Alcune di esse sono applicazioni relativamente semplici e possono utilizzare il componente PKI sviluppato in questa soluzione con qualche lieve o nessun cambiamento alla progettazione di base. Altre, come ad esempio la posta elettronica protetta e l’accesso con smart card, sono più complesse e quasi certamente richiedono una maggiore considerazione e un’estensione della progettazione PKI.
  
[![](images/Dd536244.03fig3-13(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536244.03fig3-13_big(it-it,technet.10).gif)
  
**Figura 3.13 Applicazioni PKI**
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riesame dei criteri di progettazione
  
Prima di chiudere il capitolo, è opportuno riesaminare i criteri di progettazione per questa soluzione per verificare fino a che punto la progettazione proposta rispetta gli obiettivi definiti precedentemente. Tale valutazione è riepilogata nell’elenco riportato di seguito. Molti di questi elementi verranno trattati in maniera dettagliata nei capitoli di progettazione successivi.
  
-   **Protezione** La soluzione include un’autenticazione, un’autorizzazione e un controllo dell’accesso affidabili. La crittografia avanzata (128 bit) è una funzione dei componenti hardware di rete ed è supportata dalla maggior parte delle periferiche attualmente disponibili. La gestione della protezione delle chiavi di crittografia viene fornita da una combinazione del client 802.1X Microsoft, delle schede di rete senza fili e del punto di accesso senza fili abilitati per lo standard 802.1X e del server RADIUS.
  
    La capacità di recupero dagli attacchi di negazione del servizio (DoS) rimane un'area che richiede dei miglioramenti. Gli standard di settore attuali (fino all’avvento della tecnologia 802.11i) sono ancora vulnerabili ad una varietà di attacchi DoS.
  
-   **Scalabilità** La progettazione di base si adatta ad una vasta gamma di organizzazioni, a costi ridotti, da poche centinaia a molte migliaia di utenti. La progettazione è flessibile anche relativamente alla struttura geografica e della rete. Gli uffici di piccole dimensioni senza controller di dominio locale dipendono dall’affidabilità della rete WAN o da una soluzione di protezione di livello inferiore.
  
-   **Riutilizzo dei componenti (uso dell'infrastruttura esistente)** La progettazione utilizza Active Directory e molti servizi di rete esistenti, ad esempio DHCP (Dynamic Host Configuration Protocol) e DNS (Domain Name System).
  
-   **Riutilizzo dei componenti da parte delle applicazioni future** La progettazione RADIUS, implementata utilizzando IAS, è pronta per l’uso oppure può essere facilmente estesa per supportare altre applicazioni di accesso alla rete (ad esempio accesso VPN, accesso alla rete cablata 802.1X e accesso remoto). Anche il componente PKI è capace di supportare semplici applicazioni a chiave pubblica, come EFS, e fornisce l'ambiente per operare con applicazioni più complesse, come l’accesso con smart card.
  
    Questo elemento soddisfa anche i criteri di **espansione**.
  
-   **Disponibilità** La progettazione della soluzione è dotata di capacità di recupero in caso di guasti a singoli componenti o al collegamento di rete presso la sede centrale e tutti gli uffici periferici in cui può essere distribuito un server RADIUS. Gli uffici di piccole dimensioni senza un server RADIUS locale sono vulnerabili ad eventuali guasti della rete WAN.
  
-   **Facilità di gestione** La facilità di gestione della soluzione non è un elemento importante nella progettazione, tuttavia questo requisito viene incluso nella progettazione dell’infrastruttura operativa.
  
-   **Struttura dell'organizzazione IT** Per la distribuzione e la gestione di una soluzione di questo tipo, è essenziale che il reparto IT abbia una certa esperienza nel campo delle reti WLAN.
  
-   **Conformità agli standard** La soluzione è conforme agli attuali standard di settore e ufficiali. Questo criterio assume particolare importanza nell’area della protezione della rete WLAN dove la soluzione è basata sul protocollo 802.1X, EAP-TLS e WPA o WEP dinamico a 128 bit. Microsoft recentemente ha annunciato un servizio di supporto per la protezione WPA per Windows XP, approvando standard di protezione della rete WLAN di alto livello. La progettazione supporterà sia il WPA che il WEP dinamico.
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Riepilogo
  
In questo capitolo è stata esaminata la progettazione concettuale di una soluzione di rete LAN senza fili protetta basata sul protocollo 802.1X ed EAP-TLS. I componenti chiave della soluzione sono stati illustrati a livello di architettura. Inoltre è stata descritta anche la struttura dell’organizzazione di destinazione per questa soluzione, nonché i criteri di progettazione utilizzati per realizzare la soluzione.
  
I criteri di progettazione sono stati utilizzati per tradurre la soluzione concettuale in una progettazione logica della soluzione. Questo ha richiesto un esame delle opzioni di implementazione per adattare la soluzione ad organizzazioni con diverse esigenze e dimensioni e uno studio delle modalità di estensione della progettazione di base in modo da fornire supporto per le altre applicazioni di protezione e di accesso alla rete. Infine sono stati riesaminati i principali criteri di progettazione in relazione alle caratteristiche della progettazione proposta. Quest’analisi dei criteri può essere utilizzata come base di partenza per il resto della Guida alla pianificazione.
  
I successivi tre capitoli analizzano in dettaglio la progettazione di ciascuno dei principali componenti della soluzione: il PKI, l’infrastruttura RADIUS e la progettazione di una rete WLAN protetta.
  
[](#mainsection)[Inizio pagina](#mainsection)
