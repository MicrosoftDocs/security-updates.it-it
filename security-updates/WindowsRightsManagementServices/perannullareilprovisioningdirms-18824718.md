---
TOCTitle: Per annullare il provisioning di RMS
Title: Per annullare il provisioning di RMS
ms:assetid: '9fa63daa-5fb9-4afd-8371-b38248619857'
ms:contentKeyID: 18824718
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747706(v=WS.10)'
---

Per annullare il provisioning di RMS
====================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

I server rimossi vengono eliminati dalla tabella ClusterServer del database di configurazione. Quando si rimuove l'ultimo server di un cluster, il database dei servizi di directory viene eliminato da SQL Server. Quando si rimuove l'ultimo server di certificazione principale di un cluster, è necessario annullare manualmente la registrazione del punto di connessione del servizio di certificazione (SCP, Service Connection Point). Le operazioni di rimozione e disinstallazione non determinano la rimozione del punto di connessione del servizio da Active Directory.

Se si decide di disinstallare un server di certificazione principale prima di averne eseguito il provisioning, viene visualizzato un messaggio di avviso per indicare che il sito non è ancora stato rimosso e che il punto di connessione del servizio non viene rimosso da Active Directory. Tuttavia, se si sceglie **Sì** per continuare, il sito verrà rimosso automaticamente. L'operazione di disinstallazione non determina la rimozione del punto di connessione del servizio da Active Directory.

Annullamento del provisioning di RMS
------------------------------------

#### Per annullare il provisioning di RMS

1.  Accedere al server da cui si desidera rimuovere RMS.

2.  Visualizzare la pagina **Amministrazione globale**.

3.  Accanto al sito Web in cui è stato eseguito il provisioning di RMS, selezionare **Rimuovi RMS da questo sito Web** e scegliere **OK**.

4.  Fare clic su **Annulla registrazione URL** nella pagina Web del punto di connessione del servizio RMS per annullare la registrazione in Active Directory della connessione del servizio di certificazione.
