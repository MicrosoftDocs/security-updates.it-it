---
TOCTitle: Per aggiungere un dominio di pubblicazione trusted
Title: Per aggiungere un dominio di pubblicazione trusted
ms:assetid: '731416d8-ddf4-4d4a-9f1a-bbd1ea48fe3c'
ms:contentKeyID: 18824648
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747624(v=WS.10)'
---

Per aggiungere un dominio di pubblicazione trusted
==================================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Se si utilizza un modulo di protezione hardware per proteggere la chiave privata di RMS e si sta importando un certificato concessore di licenze server da un'installazione di RMS in cui è utilizzato un metodo di protezione della chiave privata basato su software, specificare una password della chiave privata nella pagina **Impostazioni di protezione** di ciascun server RMS del cluster prima di importare il certificato.

Aggiunta di un dominio di pubblicazione trusted
-----------------------------------------------

#### Per aggiungere un dominio di pubblicazione trusted

1.  Visualizzare la pagina **Amministrazione globale** e selezionare **Amministra RMS in questo sito Web** accanto al sito Web in cui si desidera aggiungere un dominio di pubblicazione trusted.

2.  Nell'area **Collegamenti per l'amministrazione,** selezionare **Criteri di trust**.

3.  Nell'area **Domini di pubblicazione trusted,** scegliere **Sfoglia**. Individuare il certificato del dominio di pubblicazione che si desidera aggiungere e fare doppio clic su tale certificato. In **Password per decrittografare il file da importare,** digitare la password necessaria per decrittografare il file e scegliere **Importa**.

    Nel file protetto da password, sono presenti il certificato concessore di licenze, la chiave privata, se memorizzata nel software, e i modelli di criteri per i diritti.

4.  Il nome del dominio verrà visualizzato nell'elenco **Domini di pubblicazione trusted**.

Per ulteriori informazioni sull'esecuzione di questa procedura, vedere "[Aggiunta e rimozione di domini di pubblicazione trusted](https://technet.microsoft.com/d87b502d-5497-4ccd-badf-f6807d587cee)".
