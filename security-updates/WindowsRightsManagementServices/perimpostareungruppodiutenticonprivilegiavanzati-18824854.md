---
TOCTitle: Per impostare un gruppo di utenti con privilegi avanzati
Title: Per impostare un gruppo di utenti con privilegi avanzati
ms:assetid: 'f2ef847e-2824-471f-9079-5c343094aba8'
ms:contentKeyID: 18824854
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747798(v=WS.10)'
---

Per impostare un gruppo di utenti con privilegi avanzati
========================================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Per potere essere designato come gruppo di utenti con privilegi avanzati per RMS, il gruppo deve essere presente in Active Directory e le proprietà di tale gruppo devono includere un indirizzo di posta elettronica, specificato come nome di dominio completo, uguale al nome account.

Impostazione di un gruppo di utenti con privilegi avanzati
----------------------------------------------------------

#### Per impostare un gruppo di utenti con privilegi avanzati

1.  Visualizzare la pagina **Amministrazione globale** e selezionare **Amministra RMS in questo sito Web** accanto al sito Web in cui si desidera impostare un gruppo di utenti con privilegi avanzati.

2.  Nell'area **Collegamenti per l'amministrazione,** selezionare **Impostazioni di protezione**.

3.  Nell'area **Utenti con privilegi avanzati,** scegliere **Attiva** per aggiungere un gruppo di utenti con privilegi avanzati.

4.  In **Nome gruppo utenti con privilegi avanzati,** digitare il nome di dominio completo, utilizzando il formato *nome\_gruppo*@*nome\_dominio.*com, di un gruppo esistente nella struttura di Active Directory in uso ai cui membri si desideri concedere i diritti per tutti i documenti protetti da RMS, quindi scegliere **Salva**.

    Per disattivare i diritti per il gruppo di utenti con privilegi avanzati, scegliere **Disattiva**.

Per ulteriori informazioni sull’esecuzione di questa procedura, vedere "[Utilizzo del gruppo di utenti con privilegi avanzati](https://technet.microsoft.com/0febcb3e-7124-4e51-971a-1013b928d33b)", più indietro in questo argomento.
