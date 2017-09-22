---
TOCTitle: Per modificare le impostazioni proxy RMS
Title: Per modificare le impostazioni proxy RMS
ms:assetid: '8f50bd4d-26b1-4996-b361-722ee21607f3'
ms:contentKeyID: 18824696
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747594(v=WS.10)'
---

Per modificare le impostazioni proxy RMS
========================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per ulteriori informazioni sui metodi di autenticazione dei server proxy e sull'utilizzo in Windows Server 2003, vedere Guida in linea di Internet Information Services.

Modifica delle impostazioni del proxy RMS
-----------------------------------------

#### Per modificare le impostazioni proxy RMS

1.  Visualizzare la pagina **Amministrazione globale** e fare clic su **Amministra RMS in questo sito Web**.

2.  In **Amministrazione cluster**, fare clic su **Impostazioni di protezione**.

3.  Se in precedenza non è stato utilizzato un server proxy con RMS, selezionare la casella di controllo **Questo computer utilizza un server proxy per la connessione a Internet**. Nella pagina, verranno visualizzate altre impostazioni da specificare.

4.  Nella casella **Indirizzo,** digitare l'indirizzo IP o il nome DNS del server proxy da utilizzare.

5.  Nella casella **Porta,** digitare il numero di porta utilizzata dal server proxy per la connessione a Internet.

6.  Se non si utilizza il server proxy per la connessione alle risorse locali, selezionare la casella di controllo **Ignora server proxy per indirizzi locali**.

7.  Se necessario, selezionare la casella di controllo **Per il server proxy è necessaria l'autenticazione**.

    -   Selezionare dall'elenco il tipo di autenticazione tra **Di base**, **Del digest** o **Windows integrata**.
    -   Nella casella **Nome utente,** digitare il nome utente da specificare in risposta alla richiesta del server proxy.
    -   Nella casella **Password,** digitare la password da specificare in risposta alla richiesta del server proxy.
    -   Nella casella **Conferma password,** ridigitare la password fornita in precedenza per verificare di averla digitata correttamente.
    -   Se il server proxy utilizza l'autenticazione Windows integrata, nella casella **Dominio** digitare il dominio di appartenenza dell'utente.

8.  Scegliere **Invia**.
