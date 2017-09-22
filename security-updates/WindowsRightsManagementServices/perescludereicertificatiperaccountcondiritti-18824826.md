---
TOCTitle: Per escludere i certificati per account con diritti
Title: Per escludere i certificati per account con diritti
ms:assetid: 'e5cd9dec-ac29-437e-8515-dc697ec75edf'
ms:contentKeyID: 18824826
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747785(v=WS.10)'
---

Per escludere i certificati per account con diritti
===================================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Queste condizioni vengono applicate dal client quando la licenza d'uso viene associata ai contenuti protetti.

Esclusione dei certificati per account con diritti
--------------------------------------------------

#### Per escludere i certificati per account con diritti

1.  Visualizzare la pagina **Amministrazione globale** e selezionare **Amministra RMS in questo sito Web** accanto al sito Web in cui si desidera escludere i certificati per account con diritti.

2.  Nell'area **Collegamenti per l'amministrazione,** selezionare **Criteri di esclusione**.

3.  Nell'area Esclusione basata sui certificati per account con diritti, scegliere **Attiva** per escludere un certificato per account con diritti di un utente.

4.  Selezionare il metodo da utilizzare per specificare il certificato per account che si desidera escludere.

    -   Per escludere il certificato per account in base al nome utente, fare clic su **Nome utente** relativo al certificato per account con diritti da escludere, digitare il nome dell'utente da escludere in base al formato *nome\_utente*@*nome\_dominio.com* e scegliere **Aggiungi.** Utilizzare questa opzione per escludere i certificati per gli account degli utenti interni che dispongono di account utente Active Directory.
    -   Per escludere un certificato per account in base alla chiave pubblica, fare clic su **Stringa della chiave pubblica** relativa al certificato per account con diritti da escludere, digitare la stringa della chiave pubblica relativa al certificato per account appropriata e scegliere **Aggiungi**. Utilizzare questa opzione per escludere i certificati per account di utenti esterni che non dispongono di account utente Active Directory.

    | ![](images/Cc747785.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                   |
    |-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Per eliminare un certificato per account da un elenco di esclusione, selezionare il certificato per account con diritti escluso nell'elenco e scegliere **Elimina le chiavi pubbliche selezionate dall'elenco di esclusione**. L'utente che possiede il certificato per account potrà a questo punto ottenere una licenza per il contenuto protetto con RMS nel server. |

    | ![](images/Cc747785.note(WS.10).gif)Nota                          |
    |------------------------------------------------------------------------------------------------|
    | Per disattivare l'esclusione dei certificati per account con diritti, scegliere **Disattiva**. |

Per ulteriori informazioni sull'esecuzione di questa procedura, vedere "[Esclusione dei certificati per account con diritti](https://technet.microsoft.com/cba5e901-942c-4d06-9865-e6c4648c95e6)", più indietro nell'argomento.
