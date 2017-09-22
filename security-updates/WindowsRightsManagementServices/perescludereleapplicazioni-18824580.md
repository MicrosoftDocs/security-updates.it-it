---
TOCTitle: Per escludere le applicazioni
Title: Per escludere le applicazioni
ms:assetid: '422f2ddd-bcf4-45f1-905a-b8bad30fd7dd'
ms:contentKeyID: 18824580
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720262(v=WS.10)'
---

Per escludere le applicazioni
=============================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

I criteri di esclusione vengono applicati dal client quando la licenza d'uso viene associata ai contenuti protetti.

Esclusione di applicazioni o interruzione dell'esclusione di applicazioni
-------------------------------------------------------------------------

#### Per escludere le applicazioni

1.  Visualizzare la pagina **Amministrazione globale** e selezionare **Amministra RMS in questo sito Web** accanto al sito Web in cui si desidera controllare le versioni delle applicazioni che possono essere utilizzate con il contenuto protetto con RMS.

2.  Nell'area dei **collegamenti** di **Amministrazione**, selezionare **Criteri di esclusione**.

3.  Nell'area **Esclusione basata su un'applicazione,** scegliere **Attiva** per escludere un'applicazione o un componente abilitato per RMS.

    Per disattivare l'esclusione delle applicazioni, scegliere **Disattiva**.

4.  Digitare il nome del file dell'applicazione o del componente da escludere, digitare i numeri di versione minima e massima da escludere utilizzando il formato *x*.*x*.*x*.*x* e scegliere **Escludi applicazione**.

    Per eliminare un'applicazione o un componente dall'elenco di esclusione, selezionare il nome del file e scegliere **Elimina le applicazioni selezionate dall'elenco di esclusione**.

    | ![](images/Cc720262.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                             |
    |-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | In RMS, è necessario specificare la versione dell'applicazione con un formato di quattro cifre separate da punti (\#.\#.\#.\# ). Tuttavia, in alcune applicazioni, la versione viene specificata con numeri di due o tre cifre delimitati da punti. In questo caso, inserire .0 dove necessario per rendere compatibile il numero della versione con il formato richiesto da RMS. |

#### Interruzione dell'esclusione di applicazioni

1.  Visualizzare la pagina **Amministrazione globale** e selezionare **Amministra RMS in questo sito Web** accanto al sito Web in cui si desidera controllare le versioni delle applicazioni che possono essere utilizzate con il contenuto protetto con RMS.

2.  Nell'area dei **collegamenti** di **Amministrazione**, selezionare **Criteri di esclusione**.

3.  Nell'area di **esclusione Applicazioni**, fare clic su **Disattiva**.

Per ulteriori informazioni sull'esecuzione di questa procedura, vedere "[Esclusione di applicazioni](https://technet.microsoft.com/b68ae4b2-b9ba-44ae-90cb-c88df600ec86)", più indietro nell'argomento.
