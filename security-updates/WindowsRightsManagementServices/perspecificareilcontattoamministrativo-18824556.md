---
TOCTitle: Per specificare il contatto amministrativo
Title: Per specificare il contatto amministrativo
ms:assetid: '31777458-5530-4ae0-ac1f-131b3d98dd35'
ms:contentKeyID: 18824556
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720237(v=WS.10)'
---

Per specificare il contatto amministrativo
==========================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

L'amministratore specificato tramite la procedura deve essere un amministratore locale nel server di certificazione principale, in quanto, ai fini dell'esecuzione del provisioning di un server licenze, gli utenti connessi devono disporre delle autorizzazioni per il file SubEnrollService.asmx nel server di certificazione principale. Nel caso in cui si tenti di eseguire il provisioning di un server licenze senza disporre delle autorizzazioni per tale file, è possibile richiedere tali autorizzazioni inviando una richiesta all'amministratore designato. Per ulteriori informazioni, vedere "[Impostazione delle autorizzazioni nel file del servizio di registrazione secondaria](https://technet.microsoft.com/737bb69b-fe26-4057-9569-e632f7bbf295)", più indietro in questo argomento.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Specifica del contatto amministrativo
-------------------------------------

#### Per specificare il contatto amministrativo

1.  Visualizzare la pagina **Amministrazione globale** e selezionare **Amministra RMS in questo sito Web** accanto al sito Web in cui si desidera specificare un contatto amministrativo.

2.  Nell'area **Collegamenti per l'amministrazione,** selezionare **Impostazioni certificazione**.

3.  Nell'area **Contatto amministrativo,** digitare l'indirizzo di posta elettronica dell'amministratore da contattare nel caso in cui si verifichino problemi di registrazione secondaria durante il provisioning di un server licenze, utilizzando il formato *nome\_utente*@*nome\_dominio*.com.

4.  Nella parte inferiore della pagina, scegliere **Invia**.
