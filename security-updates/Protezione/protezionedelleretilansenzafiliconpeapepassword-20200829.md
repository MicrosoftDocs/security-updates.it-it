---
TOCTitle: Protezione delle reti LAN senza fili con PEAP e password
Title: Protezione delle reti LAN senza fili con PEAP e password
ms:assetid: '0963a651-e6de-4b30-9650-d39533f63df0'
ms:contentKeyID: 20200829
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd536230(v=TechNet.10)'
---

Protezione delle reti LAN senza fili con PEAP e password
========================================================

### Capitolo 1: Protezione delle reti LAN senza fili con PEAP e password

Aggiornato: 2 aprile 2004

##### In questa pagina

[](#edaa)[Introduzione](#edaa)
[](#ecaa)[Panoramica della soluzione](#ecaa)
[](#ebaa)[Convenzioni di stile](#ebaa)
[](#eaaa)[Commenti, suggerimenti e supporto tecnico](#eaaa)

### Introduzione

Attualmente la tecnologia senza fili rappresenta uno degli argomenti più scottanti nell'ambito della New Economy: la maggior parte delle organizzazioni ha già implementato reti LAN senza fili o sta esaminando i vantaggi e svantaggi legati all'uso di questa tecnologia. I miglioramenti in termini di produttività riscontrati dagli utenti e l'attrattiva di reti che richiedono poca manutenzione rappresentano vantaggi indiscutibili per i settori IT. Tuttavia, alcuni importanti aspetti di protezione hanno reso estremamente cauti, se non contrari, i responsabili del settore IT circa l'introduzione di reti LAN senza fili nelle proprie organizzazioni. Al contempo, le soluzioni proposte da analisti e fornitori di servizi di rete per risolvere questi problemi sono sembrate eccessivamente complesse e costose per poter essere distribuite in modo efficace.

*Protezione delle reti LAN senza fili con PEAP e password* costituisce la seconda soluzione proposta da Microsoft® per le reti LAN senza fili ed è un'integrazione alla prima soluzione, *Securing Wireless LANs —a Certificate Services Solution*. Mentre la prima soluzione era orientata alle grandi organizzazioni, questa seconda proposta è nettamente più semplice e facile da distribuire essendo progettata per organizzazioni di piccole e medie dimensioni. La principale differenza tecnologica tra le due soluzioni è costituita, nel primo caso, dall'uso di certificati a chiave pubblica per l'autenticazione di utenti e computer nella rete LAN senza fili, mentre nel secondo caso viene utilizzata l'autenticazione basata sul nome utente e la password. Tra le altre caratteristiche specifiche di questa soluzione vi sono l'uso dell'hardware server esistente (anziché richiedere nuovi componenti), l'impiego di un modello amministrativo più semplice e l'automazione di un numero maggiore di attività di configurazione mediante script e impostazioni predefinite.

La documentazione di questa soluzione presenta due caratteristiche importanti che la distinguono dalle normali documentazioni sui prodotti per il sistema operativo Microsoft Windows® e da molti white paper tecnici rilasciati da Microsoft. In primo luogo questa guida è formulata sotto forma di *istruzioni*. Quando vengono fornite scelte di progettazione, le decisioni sono state effettuate sulla base dell'esperienza acquisita dalla distribuzione interna e dai commenti dei clienti ricevuti da Microsoft. La soluzione è basata su tali procedure consigliate ed è stata creata e collaudata nei laboratori Microsoft per garantirne il corretto funzionamento. Il secondo aspetto è rappresentato dal fatto che questa guida *end-to-end* racchiude tutto il ciclo di vita della pianificazione, creazione, verifica e gestione della soluzione.

Come verrà descritto in modo dettagliato nei prossimi capitoli, la soluzione è basata sullo standard IEEE (Institute of Electrical and Electronic Engineers) 802.1X e richiede un'infrastruttura RADIUS (Remote Authentication Dial-In User Service). È stata utilizzata un'architettura flessibile che può essere adattata a una vasta gamma di organizzazioni, da quelle con poche decine di utenti a quelle con diverse migliaia di utenti. La soluzione è stata creata e verificata mediante client Microsoft Windows® XP, client Microsoft Pocket PC 2003 e server Microsoft Windows Server™ 2003.

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica della soluzione

Questa guida è divisa in quattro sezioni corrispondenti alle diverse fasi del ciclo di vita della soluzione: pianificazione, implementazione, verifica e impiego. Tali fasi sono ulteriormente divise in capitoli.

[![](images/Dd536230.PEAP_101(it-it,TechNet.10).gif)](https://technet.microsoft.com/it-it/dd536230.peap_101_big(it-it,technet.10).gif)

**Figura 1.1 Panoramica della protezione di reti LAN senza fili**

La sezione dedicata alla pianificazione è costituita da un'introduzione, "Scelta di una strategia per la protezione di reti LAN senza fili" e dal capitolo 2, "Pianificazione dell'implementazione di reti LAN senza fili". I successivi quattro capitoli costituiscono la sezione relativa alla creazione e distribuzione. In questi capitoli sono fornite istruzioni per l'implementazione di server RADIUS con Windows Server 2003 IAS (Internet Authentication Service) e la distribuzione di client senza fili e dell'infrastruttura di supporto. Ogni capitolo include procedure dettagliate per l'installazione e la configurazione dei componenti software e la loro integrazione nella soluzione. Sono contenute anche procedure di verifica che consentono di ridurre eventuali errori.

La sezione della verifica prevede un solo capitolo in cui è illustrato il modo in cui accertare che la soluzione funzioni correttamente prima di distribuirla. Anche la sezione relativa al funzionamento include un solo capitolo in cui sono descritte le procedure per utilizzare, monitorare, modificare tutti i componenti della soluzione e per risolvere eventuali problemi attinenti a essi.

Insieme alla guida è fornita una serie di strumenti e script che consentono di automatizzare molte attività di implementazione e operazioni.

Nella sezione che segue sono descritti in maggiore dettaglio i singoli capitoli.

#### Scelta di una strategia per la protezione di reti LAN senza fili

Questo documento funge da introduzione alle due soluzioni di protezione delle reti LAN senza fili esaminate in precedenza. L'obiettivo di questo capitolo è di facilitare la scelta della strategia giusta per l'infrastruttura di protezione della propria rete senza fili. Vengono prese in esame le motivazioni che portano all'adozione della tecnologia WLAN e i problemi di protezione correlati. Vengono inoltre esaminate le diverse opzioni disponibili per far fronte ai problemi di sicurezza e viene delineata una soluzione basata su un sistema di autenticazione avanzato e di protezione dei dati della rete. È inclusa anche un'analisi dei meriti dei diversi approcci alla protezione delle reti LAN senza fili, tra cui le soluzioni di protezione nativa della rete LAN senza fili, le reti VPN (Virtual Private Network) e la protezione IP.

#### Capitolo 1: Protezione delle reti LAN senza fili con PEAP e password

In questo capitolo è fornita una panoramica sul contenuto della guida.

#### Capitolo 2: Pianificazione dell'implementazione della protezione di reti LAN senza fili

In questo capitolo viene descritta la struttura architettonica della soluzione di protezione della rete LAN senza fili. Sono trattati i seguenti argomenti:

-   Funzionamento di una soluzione per rete LAN senza fili basata sullo standard 802.1X e sul protocollo PEAP (Protected Extensible Authentication Protocol).

-   Descrizione dell'organizzazione a cui è destinata questa soluzione e del criterio chiave di progettazione della soluzione.

-   Sviluppo di una struttura per la soluzione di protezione della rete LAN senza fili basata sui requisiti dell'organizzazione di destinazione.

-   Descrizione del modo in cui scalare la struttura di base per le organizzazioni più estese.

-   Valutazione delle variazioni da apportare alla struttura per rispondere a requisiti esterni alla soluzione principale, ad esempio l'introduzione di una VPN o di reti 802.1X cablate.

Il capitolo è incentrato sulla progettazione di un'architettura RADIUS (mediante IAS, l'implementazione RADIUS inclusa in Windows Server) per garantire l'autenticazione avanzata e servizi di gestione delle chiavi. Nel capitolo sono anche esaminati i client senza fili supportati dalla soluzione e i requisiti di certificati.

#### Capitolo 3: Predisposizione dell'ambiente

In questo capitolo viene esaminata l'infrastruttura IT necessaria per supportare questa soluzione WLAN. È illustrata la preparazione del servizio Microsoft Active Directory, del protocollo DHCP (Dynamic Host Configuration Protocol), dei servizi DNS (Domain Name System) e dei requisiti di base della rete. Sono inoltre descritte le procedure necessarie per applicare le impostazioni di protezione e installare gli aggiornamenti di protezione richiesti ai server utilizzati nella soluzione.

#### Capitolo 4: Creazione dell'autorità di certificazione della rete

Questo capitolo esamina il modo in cui installare un'Autorità di certificazione (CA) semplice in un controller di dominio per fornire certificati ai server IAS. Le procedure che consentono di eseguire questa attività sono in gran parte automatizzate sulla base di script inclusi con la guida. Alla CA creata per questa soluzione è assegnato il compito specifico di rilasciare certificati ai server IAS e, quindi, richiede operazioni di manutenzione minime o nulle.

#### Capitolo 5: Creazione dell'infrastruttura di protezione per LAN senza fili

In questo capitolo vengono fornite istruzioni sul modo in cui distribuire i componenti di protezione WLAN, i server IAS e i punti di accesso senza fili. Il capitolo include istruzioni dettagliate per l'installazione di IAS su un controller di dominio (o server membro), la configurazione delle impostazioni e dei criteri IAS, l'impostazione dei punti di accesso senza fili per l'utilizzo dei server IAS e l'estensione delle impostazioni a tutti i server IAS.

#### Capitolo 6: Configurazione dei client delle reti LAN senza fili

Questo capitolo include le procedure di configurazione dei client supportati dalla soluzione. Le tre sezioni principali di questo capitolo sono dedicate al controllo dell'accesso di utenti e computer alla rete LAN senza fili, alla configurazione dei criteri di gruppo per i client Windows XP delle reti LAN senza fili e alla configurazione manuale delle impostazioni WLAN per i client Pocket PC 2003.

#### Capitolo 7: Testing della soluzione per reti LAN senza fili protette

Questo capitolo è basato sul piano di test utilizzato dal team Microsoft durante la verifica della soluzione. I capitoli dedicati alla fase di creazione (dal capitolo 3 al capitolo 6) contengono le procedure di test utilizzate in tutto il processo di creazione per verificare che le operazioni vengano svolte correttamente. Insieme a tali procedure è fornita una serie di test supplementari da eseguire prima della distribuzione della soluzione all'ambiente di produzione.

#### Capitolo 8: Gestione della soluzione per reti LAN senza fili protette

Questo capitolo è incentrato sul modo in cui garantire il corretto funzionamento dell'infrastruttura di protezione per reti LAN senza fili. La prima parte del capitolo include le principali attività operative necessarie per garantire il costante funzionamento del sistema. Tali attività sono divise in diverse categorie: attività di manutenzione giornaliera, monitoraggio e segnalazione di avvisi; introduzione di modifiche nell'ambiente; ottimizzazione delle prestazioni; risoluzione dei problemi. La sezione finale dedicata alla risoluzione dei problemi include una serie di diagrammi di flusso, tabelle e procedure associati a descrizioni dettagliate di alcuni strumenti e tecniche utilizzabili per individuare e risolvere i problemi.

#### Appendici

##### Appendice A: Utilizzo di PEAP nell'impresa

Questa soluzione è stata progettata per piccole e medie imprese, in contrasto con la soluzione per reti LAN senza fili basata su certificati (menzionata precedentemente), progettata per un'organizzazione molto estesa. Tuttavia, una soluzione per reti LAN senza fili che prevede l'utilizzo di PEAP e password può anche essere adottata da organizzazioni di grandi dimensioni.

Questa appendice illustra il modo in cui adattare la guida orientata alle imprese della soluzione per reti LAN senza fili basata su certificati allo scopo di distribuire una soluzione per reti LAN senza fili con PEAP e password.

##### Appendice B: Utilizzo di WPA nella soluzione

In questa appendice sono fornite informazioni sul supporto della protezione WPA (WiFi Protected Access) e sul modo in cui utilizzare questo standard al posto della protezione dei dati WEP (Wired Equivalent Privacy). Questa soluzione è stata progettata per supportare WPA e in tutta la guida si fa riferimento a questo standard. Tuttavia, la protezione WPA non era ancora universalmente supportata al momento dello sviluppo di questa soluzione, di conseguenza si è scelto di non utilizzare WPA come opzione predefinita.

##### Appendice C: Versioni del sistema operativo supportate

Questa appendice è costituita da una tabella in cui sono riportate le versioni del sistema operativo supportate per i client senza fili e per vari ruoli server in questa soluzione. Lo scopo di questa appendice è di risolvere eventuali dubbi sulla possibilità di utilizzare versioni alternative di Windows e di altre piattaforme nei vari ruoli della soluzione.

##### Appendice D: Script e file di supporto

Le procedure descritte nei capitoli dedicati all'implementazione e alle operazioni prevedono l'utilizzo di numerosi script e altri file di supporto. In questa appendice sono descritti tali script e il loro funzionamento. Queste informazioni sono fornite anche nel file SecuringWirelessLANs.rtf incluso con gli script.

[](#mainsection)[Inizio pagina](#mainsection)

### Convenzioni di stile

Nella tabella che segue sono descritte le convenzioni di stile utilizzate in questa guida.

**Tabella 1.1: Convenzioni di stile**

 
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
<td style="border:1px solid black;">Caratteri digitati esattamente come indicato, inclusi comandi e opzioni. Vengono riportati in grassetto anche gli elementi di interfaccia utente nel testo delle istruzioni.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><em>Corsivo</em></td>
<td style="border:1px solid black;">Il corsivo viene utilizzato in due casi specifici:
—Se utilizzato nel corpo del testo, indica il titolo di un altro documento.
—Se utilizzato nei comandi o nel codice (o in parti di testo che si riferiscono a un comando o al codice), indica un segnaposto per le variabili in cui è necessario fornire valori specifici. Ad esempio, <em>nomefile.ext</em> indica la necessità di sostituire il testo <em>nomefile.ext</em> in corsivo con il nome di file desiderato.
Lo stile corsivo è utilizzato in alcuni casi anche per enfatizzare parti del testo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Testo su schermo</td>
<td style="border:1px solid black;">Per il testo visualizzato sullo schermo (ad esempio, l'output di uno strumento della riga di comando) e per i comandi che devono essere digitati nella riga di comando.
Alcuni comandi superano le dimensioni previste per i margini della pagina. In tal caso, il testo del comando viene suddiviso su più righe, applicando un rientro alle righe successive (questa circostanza è segnalata da una nota posta dopo il comando).</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Spaziatura fissa</td>
<td style="border:1px solid black;">Esempi di codice e contenuto dei file di configurazione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">%SystemRoot%</td>
<td style="border:1px solid black;">Cartella di installazione del sistema operativo Windows Server.</td>
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
<td style="border:1px solid black;">Avvisa il lettore dei casi in cui l'inosservanza di un'azione specifica potrebbe provocare una perdita di dati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><strong>Attenzione</strong></td>
<td style="border:1px solid black;">Avvisa il lettore dei casi in cui l'inosservanza di un'azione specifica potrebbe provocare lesioni fisiche all'utente o danni all'hardware.</td>
</tr>
</tbody>
</table>
  
[](#mainsection)[Inizio pagina](#mainsection)
  
### Commenti, suggerimenti e supporto tecnico
  
#### Supporto
  
Per ulteriori informazioni sull'implementazione delle tecnologie esaminate in questa soluzione, contattare la sede Microsoft più vicina o un partner Microsoft Services.
  
-   Per trovare la sede Microsoft più vicina, immettere il seguente URL e selezionare il paese appropriato
  
    <http://www.microsoft.com/worldwide/>.
  
-   Per trovare un partner Microsoft nella propria area, consultare la sezione dei servizi di Microsoft Resource Directory, al seguente URL:
  
    <https://solutionfinder.microsoft.com>.
  
-   Per ulteriori informazioni sul supporto dei componenti di Windows Server 2003 utilizzati in questa soluzione, incluse misure correttive, offerte di supporto, risorse e livelli di supporto, consultare il seguente URL:
  
    [http://support.microsoft.com](http://support.microsoft.com/).
  
#### Commenti e suggerimenti
  
Microsoft è lieta di ricevere commenti e suggerimenti dei lettori su questo materiale. In particolare, si prega di valutare i seguenti aspetti:
  
-   Livello di utilità delle informazioni fornite.
  
-   Accuratezza delle procedure.
  
-   Livello di chiarezza e interesse dei capitoli.
  
-   Valutazione complessiva della soluzione.
  
I commenti possono essere inviati al seguente indirizzo di posta elettronica:[SecWish@Microsoft.com](mailto:secwish@microsoft.com?subject=feedback%20re:%20microsoft%20solution%20for%20secure%20wireless%20lans).
  
**Scarica la soluzione completa**
  
[Protezione delle reti LAN senza fili con PEAP e password](http://go.microsoft.com/fwlink/?linkid=23481)
  
[](#mainsection)[Inizio pagina](#mainsection)
