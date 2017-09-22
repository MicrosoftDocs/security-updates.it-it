---
TOCTitle: Per rilevare i certificati degli account con diritti
Title: Per rilevare i certificati degli account con diritti
ms:assetid: 'f9efac9f-c725-4bce-a89f-7691b0d8ffc0'
ms:contentKeyID: 18824839
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747752(v=WS.10)'
---

Per rilevare i certificati degli account con diritti
====================================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Questa funzionalità è disponibile solo nel cluster di certificazione principale e non in tutti i cluster o server licenze.

La procedura può essere utilizzata solo per valutare il numero di licenze d'uso ed è utile solo se si tratta di licenze fatturabili. Il numero visualizzato nella pagina Report certificazione account RM è approssimativo. Se il database di configurazione non è stato aggiornato eliminando gli utenti non più attivi, il numero non sarà corretto. Se vi sono inoltre utenti cui sono state rilasciate più licenze in più strutture, le licenze aggiuntive non sono incluse nel numero indicato.

Verifica dei certificati per account con diritti
------------------------------------------------

#### Per rilevare i certificati degli account con diritti

1.  Visualizzare la pagina **Amministrazione globale** e selezionare **Amministra RMS in questo sito Web** accanto al sito Web in cui si desidera verificare i certificati.

2.  Nell'area **Collegamenti per l'amministrazione,** selezionare Report certificazione account RM.

3.  In **Totale utenti certificati,** visualizzare il numero di utenti che hanno ricevuto certificati per l'account con diritti da questo cluster di certificazione principale.

Per ulteriori informazioni, vedere “[Tracciamento dei certificati per account con diritti](https://technet.microsoft.com/5bb0f3cf-fc44-4e60-a93f-c789d6f8a902)”, più indietro in questo argomento.
