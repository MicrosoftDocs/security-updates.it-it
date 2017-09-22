---
TOCTitle: Utilizzo della home page di amministrazione
Title: Utilizzo della home page di amministrazione
ms:assetid: '6c155977-bd0e-47d6-ac65-1746cddb505e'
ms:contentKeyID: 18824633
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720290(v=WS.10)'
---

Utilizzo della home page di amministrazione
===========================================

Dalla **home page di amministrazione,** è possibile visualizzare le informazioni relative al server o al cluster e accedere alle opzioni di amministrazione. Questa pagina è disponibile solo dopo che è stato eseguito il provisioning del server.

Per accedere a questa pagina Web dal server che si desidera amministrare, attenersi alla seguente procedura.

1.  Accedere come amministratore locale.
2.  Fare clic su **Start**, scegliere **Tutti i programmi**, fare clic su **Windows RMS** e selezionare **Amministrazione di Windows RMS**.
3.  Nella pagina **Amministrazione globale,** fare clic su **Amministra RMS in questo sito Web**.

Qualora sia stata attivata l'amministrazione remota tramite SSL (Secure Sockets Layer), sarà inoltre possibile accedere alla **home page di amministrazione** da un computer diverso attenendosi alla seguente procedura.

1.  Nella barra degli indirizzi del browser, digitare l'URL seguente:
    https://*nome\_cluster:numero\_porta*/\_wmcs/admin
    Dove *nome\_cluster:numero\_porta* rappresenta l'URL specificato per il cluster durante il provisioning. Specificare il numero della porta solo se diverso dalla porta predefinita 80.
2.  Quando richiesto, digitare le credenziali di un amministratore locale nel server in cui si sta eseguendo l'accesso.

Nella **home page di amministrazione,** vengono visualizzate le informazioni relative al cluster, ad esempio l'URL del cluster, il nome e il percorso del database di configurazione, la data di scadenza del certificato concessore di licenze server e così via. Vengono inoltre riportati i collegamenti alle pagine in cui è possibile configurare le seguenti opzioni di amministrazione per il cluster.

-   **Criteri di trust.**Per aggiungere e rimuovere domini trusted. Per ulteriori informazioni, vedere “[Gestione dei trust e dei criteri di trust](https://technet.microsoft.com/1c96ee74-fd28-4511-be21-087e2b04c3ee)”, più avanti in questo argomento.
-   **Modelli di criteri per i diritti**. Per creare e modificare modelli di criteri per i diritti. Per ulteriori informazioni, vedere “[Gestione dei modelli di criteri per i diritti](https://technet.microsoft.com/718286dc-3399-4556-96c9-ec3a33d31877)”, più avanti in questo argomento.
-   **Impostazioni registrazione attività**. Per attivare e disattivare la registrazione attività e visualizzare il nome del server e del database di registrazione attività. Per ulteriori informazioni, vedere “[Gestione della registrazione](https://technet.microsoft.com/8fccfc57-2135-494e-8e44-f6191bf5e4a0)”, più avanti in questo argomento.
-   **Impostazioni URL cluster Extranet.**Per specificare un URL disponibile esternamente per le richieste di certificazione account e di gestione delle licenze. Per ulteriori informazioni, vedere “[Configurazione dell'URL di una Extranet](https://technet.microsoft.com/88fec9ff-c96c-4d20-8856-0485e7507572)”, più avanti in questo argomento.
-   **Impostazioni proxy RMS.**Per specificare l'indirizzo del server proxy, il tipo di autenticazione e il nome utente da utilizzare per consentire al server RMS di connettersi a Internet tramite un server proxy. Per ulteriori informazioni, vedere “[Configurazione delle impostazioni proxy RMS](https://technet.microsoft.com/179d2970-62e9-4487-aa5b-f4334234991e)”, più avanti in questo argomento.
-   **Impostazioni di protezione.**Per reimpostare la password della chiave privata del server, specificare il gruppo di utenti con privilegi avanzati, i cui membri possono decrittografare tutti i contenuti protetti per i quali dispongono di una licenza, e rimuovere le autorizzazioni da RMS. Per ulteriori informazioni, vedere “[Gestione della protezione durante l'utilizzo di RMS](https://technet.microsoft.com/62050812-de4f-4392-8d63-f2f89aa01ed4)”, più avanti in questo argomento.
-   **Impostazioni certificazione.**Per specificare il periodo di validità dei certificati per account con diritti e l'eventuale contatto amministrativo. Questa opzione è disponibile solo nel cluster di certificazione principale e non nei server licenze. Per ulteriori informazioni, vedere “[Gestione dei certificati per account con diritti](https://technet.microsoft.com/49c5c2ba-e197-4e4b-b3b3-b3248f068bcc)”, più avanti in questo argomento.
-   **Criteri di esclusione.**Per specificare le esclusioni in base alla versione dell'archivio protetto, al certificato per account con diritti, alla versione di Windows o all'applicazione abilitata per RMS. Per ulteriori informazioni, vedere “[Gestione del criterio di esclusione](https://technet.microsoft.com/ee31e099-e095-4648-95da-0009fbeb48cb)”, più avanti in questo argomento.
-   **Report certificazione account RM.**Per visualizzare il numero di certificati per account con diritti emessi. Questa opzione è disponibile solo nel cluster di certificazione principale e non nei server licenze. Per ulteriori informazioni, vedere “[Tracciamento dei certificati per account con diritti](https://technet.microsoft.com/5bb0f3cf-fc44-4e60-a93f-c789d6f8a902)”, più avanti in questo argomento.

Nei restanti argomenti della presente sezione, vengono descritte le modalità di utilizzo di queste funzionalità. Per istruzioni dettagliate, vedere “[Procedure RMS](https://technet.microsoft.com/82032075-f361-438f-a2c4-93ab29ae6cff)”, più avanti in questo argomento.

| ![](images/Cc720290.note(WS.10).gif)Nota                                                                                                                                                                                                                                                    |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Per la configurazione di alcune funzioni, il sito Web Amministrazione di Windows RMS utilizza una finestra popup. Se si utilizza uno strumento di bloccaggio delle finestre di popup per il browser Web, configurare le impostazioni del browser per consentire i popup provenienti dal sito Web Amministrazione di RMS. |
