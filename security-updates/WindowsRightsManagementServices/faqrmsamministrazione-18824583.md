---
TOCTitle: 'FAQ - RMS: Amministrazione'
Title: 'FAQ - RMS: Amministrazione'
ms:assetid: '43f77336-5e62-4405-9efb-55417a402d62'
ms:contentKeyID: 18824583
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747547(v=WS.10)'
---

FAQ - RMS: Amministrazione
==========================

FAQ - Amministrazione di RMS
----------------------------

-   [Qual è il modo migliore per revocare le autorizzazioni per i documenti di un utente che lascia un'organizzazione?](#bkmk_1)
-   [Quando si stabiliscono relazioni di trust fra due organizzazioni per lo scambio di contenuti RMS, il certificato di licenza XrML che viene passato dall'organizzazione trusting deve essere trattato in modo speciale?](#bkmk_2)
-   [Come funziona RMS con i profili utente mobile?](#bkmk_3)
-   [Per quali motivi in un'organizzazione si potrebbero dover rimuovere le autorizzazioni da RMS?](#bkmk_4)
-   [In che cosa consiste il processo globale di rimozione delle autorizzazioni?](#bkmk_5)
-   [È possibile rimuovere le autorizzazioni da un server RMS in modo che alcuni utenti possano recuperare i documenti?](#bkmk_6)
-   [Cosa significa se il server non è in grado di accedere alla directory dell'applicazione?](#bkmk_7)
-   [È possibile utilizzare la traccia con il server RMS?](#bkmk_8)
-   [Cos'è lo sfalsamento degli orologi e come è possibile gestirlo?](#bkmk_9)

<span id="BKMK_1"></span>
#### Qual è il modo migliore per revocare le autorizzazioni per i documenti di un utente che lascia un'organizzazione?

In generale, è preferibile avere documenti concessi in licenza a gruppi di utenti definiti in Active Directory, piuttosto che a singoli account utente. Questo viene consigliato perché, se un utente lascia un'organizzazione, è possibile rimuovere l'utente dal gruppo Active Directory, in modo che l'utente non sia più in grado di leggere i documenti inviati al gruppo. Tuttavia, l'utente può ancora leggere i documenti che hanno licenze d'uso esistenti, a meno che i diritti dei documenti non siano impostati in modo che l'utente debba ottenere una licenza d'uso ogni volta che il documento viene aperto. Se quel diritto non è definito, l'unico modo per evitare che l'utente apra i documenti con licenze d'uso esistenti consiste nell'eliminare l'archivio delle licenze dal computer dell'utente.

<span id="BKMK_2"></span>
#### Quando si stabiliscono relazioni di trust fra due organizzazioni per lo scambio di contenuti RMS, il certificato di licenza XrML che viene passato dall'organizzazione trusting deve essere trattato in modo speciale?

Quando si stabilisce un dominio utente trusted o un dominio di pubblicazione trusted, si sceglie di stabilire una relazione di trust con l'organizzazione partner perché partecipi al sistema di gestione dei diritti. In tal modo si assume il rischio calcolato di un'eventuale compromissione delle informazioni derivante dalla relazione di trust con l'altra organizzazione. La procedura ottimale suggerisce di richiedere all'organizzazione partner l'invio del certificato concessore di licenze del proprio server RMS, attraverso un canale autenticato, come un messaggio di posta S/MIME, per attenuare il rischio che il certificato concessore di licenze venga manomesso prima dell'importazione nel server RMS.

<span id="BKMK_3"></span>
#### Come funziona RMS con i profili utente mobile?

I certificati per account con diritti (RAC) utilizzati per identificare gli utenti sono specifici dei computer. Quando si utilizzano profili utente mobile, al primo utilizzo di RMS su un dato computer, viene creato un nuovo RAC per l'utente sul computer.

<span id="BKMK_4"></span>
#### Per quali motivi in un'organizzazione si potrebbero dover rimuovere le autorizzazioni da RMS?

La rimozione delle autorizzazioni da RMS rimuove il server RMS dall'infrastruttura e rappresenta per gli utenti un modo per salvare il contenuto protetto con RMS, senza protezione. I motivi principali per cui si adotta una scelta di questo tipo in un'organizzazione sono tre:

-   Semplificazione dell'architettura del sistema, ad esempio consolidando i server in un cluster.
-   Migrazione di un ambiente dimostrativo pilota in un ambiente di produzione.
-   Fusione di server RMS, ad esempio in seguito a un'acquisizione.

<span id="BKMK_5"></span>
#### In che cosa consiste il processo globale di rimozione delle autorizzazioni?

Il processo di rimozione delle autorizzazioni viene avviato dal cluster principale di RMS abilitando il servizio di rimozione delle autorizzazioni. Quando si abilita il servizio di rimozione delle autorizzazioni, tutti gli altri servizi (ad esempio, la gestione di licenze e la certificazione) vengono disattivati. In seguito, quando viene utilizzata una funzionalità RMS da parte di qualsiasi applicazione utente abilitata per RMS, quest'ultima deve connettersi al servizio di rimozione delle autorizzazioni. Microsoft Office 2003 è un esempio di applicazione abilitata per RMS. In Office 2003 il client RMS viene indirizzato ai servizi RMS per mezzo di chiavi nel Registro di sistema. Una specifica chiave del Registro di sistema identifica il servizio di rimozione delle autorizzazioni. Una volta configurata questa chiave in modo da indirizzare il client al servizio di rimozione delle autorizzazioni, il cluster RMS concederà licenze d'uso con autorizzazioni complete (lettura, scrittura, copia, stampa, modifica e così via) per l'utente in relazione a tale contenuto, indipendentemente dalle autorizzazioni concesse all'utente in precedenza. È necessario richiedere agli utenti di rimuovere tutte le protezioni sui diritti da tutti i documenti che intendono conservare dopo la completa rimozione delle autorizzazioni dal cluster RMS. Terminata questa operazione, il cluster RMS può essere messo completamente fuori servizio.

Secondo le procedure ottimali, è consigliabile eseguire il backup del database di configurazione del cluster RMS, nel caso in cui fosse necessario recuperare un documento protetto con RMS dopo la rimozione del cluster. Senza la chiave privata del cluster RMS, solo l'autore del documento sarà in grado di aprire il contenuto protetto con RMS dopo la rimozione del server.

<span id="BKMK_6"></span>
#### È possibile rimuovere le autorizzazioni da un server RMS in modo che alcuni utenti possano recuperare i documenti?

È possibile applicare un elenco di controllo di accesso (ACL) al servizio Web di rimozione delle autorizzazioni (decommission.asmx) per controllare l'accesso al servizio di rimozione delle autorizzazioni, in modo che solo determinati utenti possano ottenere la chiave per decrittografare il contenuto protetto con RMS.

<span id="BKMK_7"></span>
#### Cosa significa se il server non è in grado di accedere alla directory dell'applicazione?

Questo errore si verifica talvolta quando si tenta di aprire per la prima volta il sito Web di amministrazione RMS dopo avere installato RMS. Dopo la notifica dell'errore, non è possibile configurare o amministrare RMS.

L'errore si verifica comunemente quando Internet Information Services (IIS) è in esecuzione nella modalità isolamento di IIS 5.0. Per disabilitare questa impostazione sul server e riavviare IIS e risolvere il problema, utilizzare la procedura riportata di seguito.

**Per disabilitare la modalità isolamento di IIS 5.0**
1.  Accedere al server RMS come membro del gruppo Administrators locale.

2.  Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione**, quindi **Gestione Internet Information Services (IIS)**.

3.  In **Gestione IIS** espandere il computer locale, fare clic con il pulsante destro del mouse su **Siti Web** e scegliere **Proprietà**.

4.  Fare clic sulla scheda **Servizio**, deselezionare la casella di controllo **Esegui il servizio WWW in modalità isolamento IIS 5.0**, quindi fare clic su **OK**.

5.  Questa modifica richiede il riavvio del servizio IIS. Quando viene chiesto di riavviare il servizio IIS, fare clic su **Sì**.

<span id="BKMK_8"></span>
#### È possibile utilizzare la traccia con il server RMS?

Poiché Rights Management Services è stato creato con Microsoft® .NET Framework, è possibile tener traccia degli eventi del sistema e risolvere gli eventuali problemi.

La traccia può essere implementata modificando il file Web.config o Machine.config. Quando si implementa la traccia nel file Machine.config, la traccia viene eseguita su tutti i componenti software contenuti nel computer; se invece si implementa la traccia nel file Web.config, la traccia viene eseguita solo per gli eventi che si verificano nei servizi Web.

**Per attivare la traccia**
1.  Aprire il file Machine.config oppure il file Web.config, quindi aggiungere le seguenti righe sotto la sezione &lt;system.diagnostics&gt; del file:

    
        ```
2.  Riavviare IIS eseguendo IISRESET a un prompt dei comandi.

3.  Dopo avere raccolto i dati necessari, rimuovere le righe dal file con estensione config aggiunto al passaggio 1.

4.  Riavviare IIS eseguendo IISRESET a un prompt dei comandi.

| ![](images/Cc747547.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                          |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quando si utilizza la traccia su un server RMS, possono verificarsi problemi nelle prestazioni, ad esempio ritardi più lunghi nelle acquisizioni di licenze d'uso e nell'emissione di certificati per account con diritti. Utilizzare la traccia solo in alcune circostanze per aiutare a diagnosticare e risolvere i problemi esistenti. |

<span id="BKMK_9"></span>
#### Cos'è lo sfalsamento degli orologi e come è possibile gestirlo?

Lo sfalsamento degli orologi si verifica quando l'ora dell'orologio di un computer è diversa da quella di un altro computer. Si tratta di un caso che si verifica di frequente, come accade con gli orologi da polso di due persone che si trovano in una stessa stanza. Lo sfalsamento dell'orologio può causare problemi nei casi in cui venga specificato un periodo di validità di una licenza.

La validità di una licenza viene impostata in base all'orologio del computer che esegue la pubblicazione. Lo sfalsamento dell'orologio può causare problemi con i periodi in due fasi del ciclo di pubblicazione e utilizzo:

-   Quando un'applicazione cerca di acquisire una licenza d'uso utilizzando una licenza di pubblicazione con un periodo di validità che, secondo l'orologio del server RMS, termina nel passato o inizia nel futuro. In questo caso la richiesta non viene soddisfatta. Questo può verificarsi quando un utente finale richiede una licenza d'uso oppure quando un'applicazione cerca di ottenere una prelicenza per un documento (acquisire una licenza d'uso per conto di un utente).
-   Se il periodo di validità della licenza è scaduto (o non è ancora iniziato), il tentativo di utilizzare la licenza avrà esito negativo. Altrimenti non saranno disponibili solo i diritti scaduti (o non ancora validi).

Se, ad esempio, l'orologio di un computer che esegue una pubblicazione è 15 minuti indietro rispetto all'orologio di un computer su cui si utilizza il contenuto e il computer che pubblica emette una licenza di pubblicazione che specifica una scadenza di 15 minuti per il contenuto, il computer su cui si utilizza il contenuto riceverà dal server una licenza d'uso inutilizzabile, poiché i diritti per visualizzare il contenuto concessi dalla licenza d'uso saranno già scaduti.

Non esistono soluzioni perfette per ovviare ai problemi dovuti allo sfalsamento dell'orologio. Una buona soluzione consiste nell'impostare un periodo di validità di un diritto che preceda l'ora corrente per i computer con orologi che sono indietro rispetto al proprio e, se possibile, estendere il periodo di validità della licenza di pubblicazione per gli utenti con orologi che sono avanti rispetto al proprio. È consigliabile tenere sempre in considerazione l'impatto dei problemi di sfalsamento degli orologi, specialmente quando si creano licenze di pubblicazione con brevi periodi di validità.
