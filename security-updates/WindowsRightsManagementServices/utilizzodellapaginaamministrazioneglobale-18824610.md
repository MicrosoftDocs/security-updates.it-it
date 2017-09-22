---
TOCTitle: Utilizzo della pagina Amministrazione globale
Title: Utilizzo della pagina Amministrazione globale
ms:assetid: '57bbf402-2351-4dee-823c-27f4dd32447c'
ms:contentKeyID: 18824610
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747575(v=WS.10)'
---

Utilizzo della pagina Amministrazione globale
=============================================

Dalla pagina **Amministrazione globale** del sito Web Amministrazione, è possibile eseguire il provisioning di un server RMS e rimuoverlo, nonché modificare l'account di servizio di RMS.

Per accedere a questa pagina Web dal server che si desidera amministrare, attenersi alla seguente procedura.

1.  Accedere come amministratore locale.
2.  Fare clic su **Start**, scegliere **Tutti i programmi**, selezionare **Windows RMS**, quindi scegliere **Amministrazione di Windows RMS**.

Non è possibile accedere alla pagina **Amministrazione globale** da un browser installato in un computer remoto.

Se non è ancora stato eseguito il provisioning del server da cui si esegue l'accesso alla pagina **Amministrazione globale**, verranno visualizzate le opzioni seguenti per ogni sito Web in esecuzione nel server.

-   **Effettua il provisioning di RMS in questo sito Web**. Fare clic su questo collegamento se si tratta del primo server di cui si desidera eseguire il provisioning nel cluster. Verrà avviato il processo di provisioning durante il quale verranno installate le risorse di RMS, ad esempio le directory virtuali. I database verranno inoltre installati nel server database. Per ulteriori informazioni, vedere "[Per eseguire il provisioning del primo server di certificazione principale](https://technet.microsoft.com/debc42f3-74ff-4c99-b7a4-4921fccdabc2)", più avanti in questo argomento.
-   **Aggiungi RMS a un cluster**. Fare clic su questo collegamento se si desidera eseguire il provisioning del server e aggiungerlo a un cluster esistente. È possibile aggiungere un server al cluster di certificazione principale o a un cluster licenze. Verranno installate le risorse di RMS, ad esempio le directory virtuali. I database non verranno tuttavia creati, poiché nel server verranno utilizzati i database del cluster. Per ulteriori informazioni, vedere “[Per aggiungere un server a un cluster](https://technet.microsoft.com/db635238-5528-4bec-9cc6-8244e2b3d733)”, più avanti in questo argomento.

Se si accede alla pagina **Amministrazione globale** da un server di cui è già stato eseguito il provisioning, verranno visualizzate le ozioni descritte di seguito.

-   **Amministra RMS in questo sito Web.**Fare clic su questo collegamento per visualizzare la pagina Amministrazione cluster. Per ulteriori informazioni, vedere “[Utilizzo della home page di amministrazione](https://technet.microsoft.com/6c155977-bd0e-47d6-ac65-1746cddb505e)”, più avanti in questo argomento.
-   **Modifica account di servizio di RMS.**Fare clic su questo collegamento per specificare un diverso account di servizio di RMS in cui si desidera eseguire RMS. Per ulteriori informazioni, vedere “[Modifica dell'account di servizio di RMS](https://technet.microsoft.com/f257d66d-b823-41e4-bcb7-7c90eb295238)”, più avanti in questo argomento.
-   **Rimuovi RMS da questo sito Web.**Fare clic su questo collegamento per rimuovere RMS. Rimuovendo RMS, dal server vengono rimosse le applicazioni e le directory virtuali di RMS, ma non viene disinstallato RMS. Per ulteriori informazioni, vedere “[Per disinstallare RMS](https://technet.microsoft.com/885e3b4f-ea32-466f-9f7f-d8440b0f7c28)”, più avanti in questo argomento.

| ![](images/Cc747575.note(WS.10).gif)Nota                                                                                                                                                                                                                                                    |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Per la configurazione di alcune funzioni, il sito Web Amministrazione di Windows RMS utilizza una finestra popup. Se si utilizza uno strumento di bloccaggio delle finestre di popup per il browser Web, configurare le impostazioni del browser per consentire i popup provenienti dal sito Web Amministrazione di RMS. |
