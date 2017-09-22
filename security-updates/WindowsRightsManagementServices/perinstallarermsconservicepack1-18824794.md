---
TOCTitle: Per installare RMS con Service Pack 1
Title: Per installare RMS con Service Pack 1
ms:assetid: 'dab20175-a690-43f8-b943-768d289daa0d'
ms:contentKeyID: 18824794
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747689(v=WS.10)'
---

Per installare RMS con Service Pack 1
=====================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Il computer in cui si installa RMS deve essere un server membro del dominio oppure un controller di dominio. Non è possibile distribuire RMS in un server autonomo in un gruppo di lavoro.

| ![](images/Cc747689.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Non eseguire il provisioning di RMS in altri server prima di completare l'installazione e il provisioning nel primo server di certificazione principale. Per informazioni, vedere "[Per eseguire il provisioning del primo server di certificazione principale](https://technet.microsoft.com/debc42f3-74ff-4c99-b7a4-4921fccdabc2)", "[Per eseguire il provisioning di un server licenze](https://technet.microsoft.com/4d67b898-0ba9-4eef-ab7d-ee0ca55a688e)" oppure "[Per aggiungere un server a un cluster](https://technet.microsoft.com/db635238-5528-4bec-9cc6-8244e2b3d733)", più avanti in questo argomento. |

| ![](images/Cc747689.Important(WS.10).gif)Importante                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| È possibile installare RMS SP1 su un server su cui è in esecuzione la versione precedente di RMS. Tuttavia, se RMS è stato rimosso, utilizzare Installazione applicazioni per eliminare completamente l'applicazione prima di provare a installare RMS SP1. |

Installazione di RMS con Service Pack 1
---------------------------------------

#### Per installare RMS con Service Pack 1

1.  Accedere al server in cui si desidera installare RMS SP1 con un account di dominio che faccia parte del gruppo Administrators locale.

2.  Quando viene visualizzata la finestra di dialogo **introduttiva**, controllare l'elenco di software da installare e scegliere **Avanti**.

3.  Nella finestra di dialogo **Contratto di Licenza,** leggere il contratto, selezionare **Accetto** e scegliere **Avanti**.

4.  In **Cartella,** accettare la cartella predefinita oppure specificarne una nuova e scegliere **Avanti**.

5.  Nella finestra di dialogo **Conferma installazione,** scegliere **Installa** per avviare l'installazione.

6.  Quando viene visualizzata la finestra di dialogo **Installazione completata**, scegliere **Chiudi**.

    | ![](images/Cc747689.note(WS.10).gif)Nota                                                                                                                 |
    |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Se viene visualizzato un messaggio di errore che indica che è in corso il riavvio dell'applicazione, aggiornare la pagina **Amministrazione globale** in Microsoft Internet Explorer. |

È inoltre possibile installare RMS da un prompt dei comandi. Per le istruzioni, vedere "[Installazione del server RMS dal prompt dei comandi](https://technet.microsoft.com/b55b1e2a-dd14-4168-a37f-9cdedbec660b)", più avanti in questo argomento.
