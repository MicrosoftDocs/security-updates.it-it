---
TOCTitle: Per disinstallare RMS
Title: Per disinstallare RMS
ms:assetid: '885e3b4f-ea32-466f-9f7f-d8440b0f7c28'
ms:contentKeyID: 18824683
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747587(v=WS.10)'
---

Per disinstallare RMS
=====================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Disinstallazione di RMS
-----------------------

#### Per disinstallare RMS

1.  Accedere al server da cui si desidera disinstallare RMS.

    | ![](images/Cc747587.Important(WS.10).gif)Importante                                                                                                                                                                                                         |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Se si rimuove RMS da un server del cluster di certificazione principale, è prima necessario rimuoverlo selezionando **Rimuovi RMS da questo sito Web** nella pagina **Amministrazione globale**. Non è necessario rimuovere un server licenze prima di disinstallare RMS da tale server. |

2.  Scegliere **Installazione applicazioni** nel **Pannello di controllo**.

3.  Nella finestra di dialogo **Installazione applicazioni**, fare clic su **Servizi Microsoft Windows Rights Management (RMS)**, quindi su **Rimuovi** per rimuovere RMS SP1.
