---
TOCTitle: Protezione della distribuzione RMS
Title: Protezione della distribuzione RMS
ms:assetid: '6de8b636-a824-4844-aefc-f26347abfc14'
ms:contentKeyID: 18824637
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720291(v=WS.10)'
---

Protezione della distribuzione RMS
==================================

Una distribuzione di RMS è una risorsa dell'organizzazione che richiede gli stessi accorgimenti di protezione fisica e di rete richiesti per gli altri server strategici dell'infrastruttura. Un aspetto della distribuzione consiste nell'identificare i rischi e le contromisure da adottare per i server RMS.

RMS viene implementato come servizio Web, quindi è possibile controllare l'accesso a RMS in modo identico agli altri servizi Web, cioè utilizzando elenchi di controllo di accesso insieme al protocollo SSL (Secure Sockets Layer).

**Limitazione dell'accesso ai servizi Web RMS per mezzo di elenchi ACL**

L'accesso ai servizi RMS può essere limitato per mezzo degli elenchi di controllo di accesso. Ciascuna directory principale virtuale creata durante il provisioning di RMS su un sito Web ha una corrispondente struttura di cartelle che può essere protetta. La struttura di cartelle si trova per impostazione predefinita in &lt;unità sistema&gt;:\\&lt;*cartella\_web\_principale*&gt;\\\_wmcs, dove *cartella\_web\_principale* è il nome della cartella assegnata al sito Web su cui è stato eseguito il provisioning di RMS. Alcuni dei servizi Web, come il servizio di registrazione secondaria, il servizio di certificazione dei dispositivi mobili e il servizio di certificazione dei servizi server, sono limitati per impostazione predefinita, pertanto gli utenti o i gruppi per i quali si desidera abilitare l'uso del servizio devono essere aggiunti in modo esplicito all'elenco di controllo di accesso.

Il servizio di certificazione dei servizi server fornisce i certificati per account con diritti (RAC), utilizzabili per accedere ai servizi protetti da RMS quali, ad esempio, i servizi di collaborazione Web, i server di posta e i server di gestione documenti, in modo da supportare le estensioni di un sistema RMS come quelle elencate di seguito:

-   Un server di collaborazione sui documenti in cui gli utenti possano caricare documenti non protetti ma in cui sia automaticamente applicata ai documenti scaricati la protezione RMS, in conformità ai criteri per i diritti relativi al tipo di contenuto. Un esempio potrebbe essere Microsoft Office SharePoint Server 2007.
-   Un sistema di gestione documenti che funzioni come archivio generale e dei documenti, protetti e non protetti. Il sistema sarà in grado di indicizzare per la ricerca i documenti protetti con RMS, pur mantenendo i criteri per i diritti definiti dall'autore del contenuto.
-   Abilitazione del server di posta all'apertura rapida del contenuto protetto da RMS per rilevare la presenza di virus o messaggi indesiderati oppure per rispettare i requisiti di legge o i criteri aziendali per la posta.

Poiché questi scenari richiedono licenze per gli utenti, è necessario accertarsi che la possibilità di ottenere RAC sia limitata solo ai server della propria organizzazione approvati per tale funzione e adeguatamente protetti.

**Limitazione dell'accesso ai servizi Web RMS per mezzo di SSL**

Si consiglia di abilitare SSL (Secure Sockets Layer) e richiedere la crittografia a 128 bit per ciascun file dei servizi Web RMS. Questi file hanno l'estensione .asmx e sono situati nelle directory virtuali Gestione licenze, Certificazione e Amministrazione. SSL richiede che sul server sia installato un certificato SSL valido per il sito Web. Se si applica SSL alla cartella \_wmcs dell'installazione RMS, le sottocartelle e i file erediteranno l'impostazione. Per ulteriori informazioni su file e directory virtuali dei servizi Web, vedere "Internet Information Services (IIS)" nella sezione "Guida di riferimento tecnico di RMS" di questa documentazione.

| ![](images/Cc720291.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                       |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se si desidera aprire le pagine Web di amministrazione di Windows RMS da un browser in un computer remoto, è necessario attivare SSL. Tuttavia, anche se SSL è abilitato, non è possibile aprire la pagina **Amministrazione globale** da un computer remoto. Per ulteriori informazioni sull'amministrazione remota di RMS, vedere "Utilizzo della home page di amministrazione" nella sezione "Gestione di RMS" di questa documentazione. |

**Impostazione di una password sicura per la chiave privata**

La password della chiave privata viene utilizzata per generare e registrare in modo protetto la chiave privata nel database di configurazione RMS. Per garantire la massima protezione è necessaria una password sicura. Se è necessario scrivere la password, assicurarsi di conservarla in un'area fisicamente protetta.

| ![](images/Cc720291.Caution(WS.10).gif)Attenzione                                                                                                                                                                                                   |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se la password della chiave privata andasse perduta o non fosse nota e il server RMS dovesse disconnettersi in modo imprevisto, sarà necessario decrittografare tutti i documenti RMS, ricostruire l'ambiente RMS e crittografare nuovamente tutto con una nuova chiave privata. |
