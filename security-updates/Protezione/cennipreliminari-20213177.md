---
TOCTitle: Cenni preliminari
Title: Cenni preliminari
ms:assetid: '4b39a172-9fbd-43c6-9027-727d2686aadd'
ms:contentKeyID: 20213177
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc163159(v=TechNet.10)'
---

Isolamento del server e del dominio tramite IPsec e criteri di gruppo
=====================================================================

### Cenni preliminari

Pubblicato: 17 marzo 2005

Microsoft sa che le organizzazioni di grandi dimensioni devono affrontare sfide sempre più impegnative nel proteggere il perimetro delle proprie reti. La crescita delle aziende e la conseguente evoluzione delle relazioni commerciali rendono talvolta impossibile il controllo degli accessi fisici alla rete. Per validi motivi aziendali, clienti, fornitori e consulenti devono poter accedere alla rete aziendale mediante dispositivi mobili. L'avvento delle reti e delle tecnologie di connessione senza fili hanno semplificato più che mai l'accesso alla rete. Questa aumentata connettività significa che i membri di dominio della rete interna sono esposti maggiormente a rischi significativi provenienti da altri computer sulla stessa rete interna, nonché a violazioni della protezione del perimetro.

Il concetto di isolamento logico illustrato in questa guida comprende due soluzioni: isolamento del server, per garantire che il server accetti solo le connessioni di rete provenienti da membri di domini attendibili o da un determinato gruppo di membri di un dominio, e isolamento del dominio, per isolare i membri del dominio da connessioni non attendibili. Queste soluzioni possono essere utilizzate separatamente o insieme all'interno di una soluzione completa di isolamento logico.

In sostanza, l'isolamento di server e domini consente agli amministratori IT di limitare le comunicazioni TCP/IP dei membri di dominio che sono computer attendibili. È infatti possibile configurare tali computer in modo da consentire solo le connessioni in ingresso provenienti da altri computer attendibili o da un determinato gruppo di computer considerati attendibili. Il controllo degli accessi viene gestito centralmente tramite Criteri di gruppo per Microsoft® Active Directory®, che controlla i diritti di accesso alla rete. È possibile garantire la protezione di gran parte delle connessioni alla rete TCP/IP senza apportare modifiche all'applicazione, in quanto IPsec interviene a livello di rete, inferiore al livello applicazione, fornendo protezione end-to-end tra computer per l'autenticazione e a livello di pacchetto. Il traffico di rete può essere autenticato, o autenticato e crittografato, in diversi scenari personalizzabili.

##### In questa pagina

[](#ebaa)[Vantaggi per le aziende](#ebaa)
[](#eaaa)[Destinatari della guida](#eaaa)

### Vantaggi per le aziende

Fra i vantaggi derivanti dall'introduzione di un livello di difesa a isolamento logico, figurano:

-   **Protezione aggiuntiva**. Un livello di difesa a isolamento logico garantisce protezione aggiuntiva per tutti i computer gestiti della rete.

-   **Maggiore controllo sugli utenti che possono accedere a informazioni specifiche**. Utilizzando questa soluzione, i computer non potranno automaticamente accedere a tutte le risorse di rete tramite una semplice connessione alla rete.

-   **Costi più contenuti**. Questa soluzione è generalmente molto meno costosa da implementare rispetto a una soluzione di isolamento fisico.

-   **Aumento del numero di computer gestiti**. Se le informazioni di un'organizzazione sono disponibili solo ai computer gestiti, tutti i dispositivi dovranno diventare sistemi gestiti per consentire l'accesso agli utenti.

-   **Livelli di protezione migliori contro attacchi provenienti da software dannoso**. La soluzione di isolamento limiterà notevolmente la capacità di un computer non attendibile di accedere a risorse attendibili. Per questo motivo, un attacco proveniente da software dannoso presente su un computer non attendibile non avrà esito positivo perché la connessione non sarà autorizzata, anche nel caso in cui l'hacker ottenga un nome utente e una password validi.

-   **Un meccanismo per crittografare i dati di rete**. Con l'isolamento logico è possibile richiedere che tutto il traffico di rete tra computer selezionati venga crittografato.

-   **Isolamento di emergenza rapido**. Questa soluzione fornisce un meccanismo che consente di isolare rapidamente ed efficacemente risorse specifiche all'interno della rete in caso di attacco.

-   **Controllo migliorato**. Questa soluzione consente di controllare e registrare l'accesso alla rete tramite risorse gestite.

[](#mainsection)[Inizio pagina](#mainsection)

### Destinatari della guida

Questa guida si propone di fornire supporto per la realizzazione di una soluzione di isolamento di server e domini in tutte le fasi del ciclo di vita IT, a iniziare dalla valutazione iniziale e dalla fase di approvazione alla distribuzione, al testing e alla gestione della soluzione completata. Per questo motivo, i vari capitoli che costituiscono la guida sono stati creati per soddisfare le esigenze di una molteplicità di lettori.

Il capitolo 1 si rivolge essenzialmente ai dirigenti aziendali durante la fase decisionale, in cui devono stabilire se l'organizzazione potrà trarre vantaggio o meno da un progetto di isolamento del server e del dominio. La lettura del capitolo non richiede competenze tecniche specifiche, fatta eccezione per la conoscenza delle esigenze aziendali e di protezione dell'organizzazione.

I capitoli relativi alla pianificazione (capitoli 2, 3 e 4) sono destinati agli architetti tecnici e ai professionisti IT che si occupano della progettazione di una soluzione personalizzata per l'organizzazione. Un buon livello di conoscenze tecniche delle tecnologie interessate e dell'infrastruttura dell'organizzazione è necessario per poter trarre il massimo vantaggio da questi capitoli.

Il capitolo 5 e le appendici sono destinati al personale del supporto tecnico che si occuperà dei piani di distribuzione della soluzione dell'organizzazione. La guida contiene inoltre alcune raccomandazioni su come completare con successo la distribuzione della soluzione e sui passaggi pratici necessari per creare l'ambiente di laboratorio di prova.

Il capitolo 6 è da considerarsi materiale di riferimento per il funzionamento quotidiano della soluzione una volta implementata e resa operativa. Alcuni processi e procedure operativi illustrati in questo capitolo devono essere integrati nel contesto delle operazioni dell'organizzazione.

Il capitolo 7 fornisce informazioni sulla risoluzione dei problemi relativi alla distribuzione di una soluzione di isolamento del server e del dominio. Poiché IPsec interessa principalmente le comunicazioni di rete, tali informazioni e tecniche di risoluzione dei problemi forniscono un valido aiuto alle organizzazioni che intendono implementare IPsec come parte della soluzione.

#### Commenti e suggerimenti

Microsoft è lieta di ricevere commenti e suggerimenti dei lettori su questo materiale. Sono particolarmente gradite le osservazioni sui seguenti argomenti:

-   Livello di utilità delle informazioni fornite.

-   Accuratezza delle procedure.

-   Livello di chiarezza e interesse dei capitoli.

-   Valutazione complessiva della soluzione.

Inviare i commenti e i suggerimenti (in lingua inglese) al seguente indirizzo di posta elettronica: [SecWish@Microsoft.com](mailto:secwish@microsoft.com?subject=feedback%20re:%20microsoft%20solution%20for%20secure%20wireless%20lans)

**Scarica la soluzione completa**

[Isolamento del server e del dominio tramite IPsec e criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=33947)

[](#mainsection)[Inizio pagina](#mainsection)
