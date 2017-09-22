---
TOCTitle: 'Guida alla pianificazione dell''accesso protetto mediante smart card'
Title: 'Guida alla pianificazione dell''accesso protetto mediante smart card'
ms:assetid: 'd2a7a146-1779-4f8d-b618-1fd51e24dd85'
ms:contentKeyID: 20213246
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc170941(v=TechNet.10)'
---

Guida alla pianificazione dell'accesso protetto mediante smart card
===================================================================

### Panoramica

Gli amministratori sono sempre più consapevoli dei possibili pericoli causati dall'accesso alle risorse di rete con autenticazione limitata all'uso di nomi utente e password. Eventuali utenti malintenzionati possono indovinare questi nomi utente o utilizzare le informazioni disponibili pubblicamente, come ad esempio gli indirizzi di posta elettronica stampati sui biglietti da visita, per identificare il nome di un utente. Una volta scoperto il nome utente, la relativa password rimane l'unico meccanismo di protezione che impedisce l'accesso a persone non autorizzate.

Se una password rimane segreta può essere molto efficace, anche quando usata come unico mezzo di protezione. Infatti, una password composta da più di 10 caratteri comprendente lettere casuali, numeri e caratteri speciali può risultare molto difficile da violare. Purtroppo, gli utenti non sono sempre in grado di memorizzare questo tipo di password, anche a causa delle normali limitazioni della mente umana.

Le ricerche svolte da George A. Miller, pubblicate nella rivista *The Psychological Review* nel 1956, dimostravano che la memoria a breve termine del cervello umano ha un limite compreso tra cinque e nove caratteri casuali, con un valore medio di sette. Tuttavia, la maggior parte dei suggerimenti relativi alla protezione raccomanda di utilizzare password casuali composte da un minimo di otto caratteri. Poiché la maggior parte degli utenti non è in grado di tenere a mente una password simile, molte persone decidono di annotare la password su carta.

È raro che un utente prenda le dovute precauzioni in merito alla propria password annotata, permettendo così a utenti malintenzionati di compromettere le credenziali di accesso. Laddove non è prevista alcuna limitazione circa la complessità delle password, gli utenti tendono a scegliere parole facili da ricordare, come ad esempio il termine "password" o altre parole semplici da indovinare.

Le passphrase sono password di maggiore lunghezza che gli utenti possono ricordare più facilmente. Microsoft® Windows® 2000 e le versioni successive del sistema operativo Windows supportano password di lunghezza massima di 127 caratteri. Passphrase complesse come "Amo giocare a calcetto!" aumentano in modo significativo le difficoltà che devono affrontare i programmi che usano metodi di attacco a forza bruta per violare una password e risultano più facili da memorizzare rispetto a un insieme casuale di lettere e numeri.

I sistemi di autenticazione a due fattori risolvono i problemi dell'autenticazione basata su un solo segreto mediante la richiesta di un secondo segreto. L'autenticazione a due fattori impiega una combinazione dei seguenti elementi:

-   Un oggetto di proprietà dell'utente, ad esempio un token hardware o una smart card.

-   Un elemento noto all'utente, come un numero di identificazione personale (PIN).

Le smart card e i relativi PIN costituiscono un sistema di autenticazione a due fattori sempre più popolare, affidabile e conveniente dal punto di vista dei costi. Una volta implementati i controlli necessari, per accedere alle risorse di rete l'utente deve disporre di una smart card e conoscere il relativo PIN. Il requisito a due fattori riduce in modo significativo la possibilità di accessi non autorizzati a una rete aziendale.

Le smart card forniscono un controllo di sicurezza particolarmente efficace in due scenari: la sicurezza degli account amministratore e la protezione degli accessi remoti. Questa guida è dedicata a questi due aspetti come aree prioritarie nelle quali implementare l'utilizzo delle smart card.

Poiché gli account a livello di amministratore dispongono di un numero elevato di diritti utente, la violazione di uno di essi può comportare accessi indesiderati a tutte le risorse di rete. È di importanza essenziale salvaguardare l'accesso a livello di amministratore dato che il furto delle credenziali di account di dominio a questo livello compromette l'integrità del dominio e dell'intero insieme di strutture, oltre a quello di eventuali altri insiemi di strutture trusting. L'autenticazione a due fattori è fondamentale per l'autenticazione dell'amministratore.

Le organizzazioni possono fornire un importante livello aggiuntivo di protezione mediante l'implementazione di smart card per gli utenti che devono disporre di connettività remota alle risorse di rete. L'autenticazione a due fattori è particolarmente importante per gli utenti remoti poiché per le connessioni remote non è possibile fornire altre forme di controllo fisico sugli accessi. L'autenticazione a due fattori mediante smart card può aumentare il livello di protezione del processo di autenticazione degli utenti remoti che si connettono attraverso collegamenti a una rete privata virtuale (VPN).

##### In questa pagina

[](#eeaa)[La sfida per le aziende](#eeaa)
[](#edaa)[I Vantaggi per le aziende](#edaa)
[](#ecaa)[Destinatari della guida](#ecaa)
[](#ebaa)[Prerequisiti per i lettori](#ebaa)
[](#eaaa)[Panoramica della Guida alla pianificazione](#eaaa)
[](#ebbb)[Risorse correlate](#ebbb)
[](#eacc)[Commenti e suggerimenti](#eacc)

### La sfida per le aziende

La violazione delle credenziali degli account amministratore su computer connessi a un dominio può mettere a rischio l'integrità dell'intero dominio, dell'insieme di strutture in cui si trova il dominio e di altri insiemi di strutture e domini con relazioni di trust con l'insieme di strutture in questione. La violazione degli account di accesso remoto può causare l'accesso a informazioni sensibili da parte di utenti malintenzionati attraverso connessioni remote o VPN.

La sfida aziendale di salvaguardare le connessioni di accesso remoto e di amministratore consiste nel fornire un adeguato livello di protezione che non limiti l'utilizzabilità. Nelle organizzazioni che impiegano l'autenticazione a due fattori per migliorare la protezione, il sistema opera a livelli di efficienza ottimale solamente a condizione che gli utenti siano in grado di accedere alle informazioni necessarie per svolgere il proprio lavoro. Pertanto, riuscire a bilanciare i vantaggi dell'autenticazione a due fattori e quelli dell'utilizzabilità risulta di importanza fondamentale.

[](#mainsection)[Inizio pagina](#mainsection)

### I Vantaggi per le aziende

L'utilizzo delle smart card per proteggere gli account critici può garantire i seguenti vantaggi per le aziende:

-   **Maggiore protezione dei dati sensibili**. Le smart card riducono il pericolo di accessi non autorizzati mediante l'impiego di credenziali rubate poiché l'utente malintenzionato dovrebbe sia rubare la smart card che ottenerne il PIN.

-   **Migliore protezione per le credenziali di accesso**. Per le credenziali di accesso, le smart card utilizzano certificati digitali difficili da contraffare.

-   **Superiore livello di conformità alle normative**. La capacità di verificare l'identità dell'utente connesso fornisce una maggiore credibilità ai registri di controllo monitorati.

-   **Minore probabilità di ripudio**. L'autenticazione mediante smart card riduce le possibilità che le persone possano negare le operazioni effettuate.

-   **Migliore integrazione con i sistemi di gestione degli accessi**. Alcune smart card possono funzionare anche come chiavi per la gestione degli accessi fisici, ad esempio per aprire porte chiuse a chiave e controllate e accedere a un sito fisico oppure per spostarsi tra i diversi settori di un sito. La combinazione di smart card e chiave rende più facile il controllo del livello esatto di accesso alla rete e fisico di un utente o amministratore, oltre a ridurre il pericolo di violazioni della protezione.

[](#mainsection)[Inizio pagina](#mainsection)

### Destinatari della guida

I destinatari della guida comprendono i responsabili dei processi decisionali, gli architetti di impresa e gli amministratori della sicurezza aziendale incaricati di pianificare, distribuire o gestire collegamenti di accesso remoto e protezione di rete. Le informazioni fornite saranno utili anche ai consulenti coinvolti in operazioni di pianificazione, distribuzione o gestione di reti basate su Windows.

Le informazioni della guida hanno valore per organizzazioni di qualunque dimensione che richiedano una forte protezione dell'identità e un efficace controllo dell'accesso ai dati.

[](#mainsection)[Inizio pagina](#mainsection)

### Prerequisiti per i lettori

Per comprendere le soluzioni presentate nella guida, i lettori dovrebbero capire e avere familiarità con le seguenti aree e tecnologie di Microsoft Windows Server™ 2003:

-   Routing e accesso remoto, comprendenti i componenti delle VPN

-   Servizi certificati e infrastruttura a chiave pubblica (PKI, Public Key Infrastructure)

-   Servizio di directory Active Directory®

-   Criteri di gruppo

La guida illustra i quadranti Operatività e Supporto del modello di elaborazione di Microsoft Operations Framework (MOF). Vengono discusse anche le funzioni di gestione dei servizi (SMF, Service Management Function) Amministrazione della protezione e Gestione delle emergenze all'interno di MOF. Per ulteriori informazioni su MOF, consultare il sito Web di [Microsoft Operations Framework](http://www.microsoft.com/mof) all'indirizzo www.microsoft.com/mof.

[](#mainsection)[Inizio pagina](#mainsection)

### Panoramica della Guida alla pianificazione

Questa guida si compone di quattro capitoli che trattano i problemi e i concetti fondamentali richiesti per la pianificazione dell'autenticazione mediante smart card. I capitoli sono i seguenti:

**Capitolo 1: Introduzione**

Questo capitolo fornisce un riepilogo generale, esamina i problemi da risolvere in un ambiente aziendale e illustra i vantaggi ottenibili con l'implementazione dell'autenticazione mediante smart card. Inoltre, il capitolo indica i destinatari consigliati della guida, elenca i prerequisiti per i lettori e fornisce una panoramica sui capitoli e sugli scenari di soluzione.

**Capitolo 2: Tecnologie delle smart card**

Questo capitolo evidenzia gli approcci all'impiego delle smart card per la protezione di account critici. Vengono inoltre discussi gli elementi fondamentali per i due scenari di soluzione illustrati nei capitoli 3 e 4. Infine, il capitolo introduce la Woodgrove Bank, l'organizzazione su cui si basano i due scenari di soluzione.

**Capitolo 3: Utilizzo di smart card per la protezione degli account amministratore**

Questo capitolo descrive le considerazioni relative alla progettazione per la protezione degli account amministratore mediante smart card. Il capitolo esamina quindi i problemi e i requisiti di Woodgrove Bank. Vengono illustrati il concetto della soluzione, i prerequisiti, l'architettura della soluzione e la soluzione operativa per lo scenario in questione. Infine, il capitolo riassume le possibili opzioni per l'estensione della soluzione per incorporare il processo di gestione delle modifiche.

**Capitolo 4: Utilizzo di smart card per la protezione degli account di accesso remoto**

Questo capitolo descrive le considerazioni relative alla progettazione per la protezione degli accessi remoti mediante smart card. Il capitolo esamina quindi problemi e requisiti per l'implementazione di accessi remoti protetti per Woodgrove Bank. Vengono illustrati il concetto della soluzione, i prerequisiti, l'architettura della soluzione e la soluzione operativa per lo scenario in questione. Infine, il capitolo riassume come estendere la soluzione al fine di incorporare il controllo degli accessi fisici.

[](#mainsection)[Inizio pagina](#mainsection)

### Risorse correlate

Consulta le [altre soluzioni per la protezione](http://www.microsoft.com/technet/community/columns/sectip/st0805.mspx) sviluppate dal team MSSC (Microsoft Solutions for Security and Compliance).

[](#mainsection)[Inizio pagina](#mainsection)

### Commenti e suggerimenti

Il team MSSC (Microsoft Solutions for Security and Compliance) è interessato a eventuali commenti e suggerimenti su questa e altre soluzioni per la protezione.

Hai un commento? Saremo lieti di leggerlo nel [blog sulle soluzioni per la protezione](http://blogs.technet.com/secguide) per professionisti IT (in inglese).

Oppure invia consigli e suggerimenti tramite posta elettronica all'indirizzo: [SecWish@microsoft.com.](mailto:secwish@microsoft.com) Rispondiamo spesso ai commenti e ai suggerimenti inviati a questa casella di posta.

Grazie per la collaborazione.

##### Download

[Scarica la guida alla pianificazione dell'accesso protetto mediante smart card](http://go.microsoft.com/fwlink/?linkid=41314)

##### Notifiche di aggiornamento

[Iscriviti per ricevere informazioni su aggiornamenti e nuovi rilasci](http://go.microsoft.com/fwlink/?linkid=54982)

##### Commenti

[Inviaci i tuoi commenti o suggerimenti](mailto:secwish@microsoft.com?oggetto=guida%20alla%20pianificazione%20dell'accesso%20protetto%20mediante%20smart%20card)

[](#mainsection)[Inizio pagina](#mainsection)
