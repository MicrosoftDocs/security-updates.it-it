---
TOCTitle: 'Modifica della password dell''account di servizio di RMS'
Title: 'Modifica della password dell''account di servizio di RMS'
ms:assetid: '435c9cef-b622-48b3-9d4d-4bf5cac7d52d'
ms:contentKeyID: 18824584
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720273(v=WS.10)'
---

Modifica della password dell'account di servizio di RMS
=======================================================

In base ai criteri di password specificati per i server RMS, la password dell'account di servizio di RMS potrebbe scadere periodicamente. Se la password scade, il funzionamento di RMS viene interrotto. È necessario pertanto modificare la password prima che scada.

**Utilizzo di un account di servizio di RMS**

Quando si utilizza un account di servizio di RMS, è possibile modificare la password in ogni server eseguendo la procedura seguente:

1.  Se il server si trova nel cluster, rimuoverlo dalla rotazione.
2.  Accedere al server con le credenziali dell'account di servizio di RMS.
3.  Modificare la password dell'account di servizio di RMS.
    Negli altri server in cui viene utilizzato lo stesso account di servizio di RMS si verificherà un'interruzione del servizio, poiché le credenziali memorizzate in questi server non saranno più valide in seguito alla modifica della password.
4.  Eseguire la disconnessione dal server.
5.  Accedere nuovamente al server utilizzando le credenziali di amministratore di RMS.
6.  Per configurare nuovamente l'identità utente nel server, nella pagina **Amministrazione globale** fare clic su **Modifica account di servizio di RMS** e quindi nella pagina **Modifica account di servizio di RMS** specificare dominio, nome utente e password.
7.  Riavviare IIS.
8.  Se necessario, inserire di nuovo il server nella rotazione.
9.  Ripetere i passaggi da 6 a 8 per ogni server del cluster.

Sebbene questo approccio sia il più semplice per modificare la password dell'account di servizio di RMS, può tuttavia causare tempi di inattività di RMS, poiché Active Directory viene aggiornato con la nuova password quando si modifica la password dell'account di servizio di RMS su un server. IIS riavvia periodicamente i pool di applicazioni e i pool che sono in esecuzione con le vecchie credenziali non si avviano fino a quando non viene modificata la password dell'account di servizio di RMS e non si riavvia IIS nel server. RMS non sarà operativo fino a quando il pool di applicazioni non riprenderà a funzionare.

**Utilizzo di due account di servizio di RMS**

Con questo metodo, i primi creano due account di servizio RMS che hanno criteri o date di scadenza diversi. Nel corso delle normali operazioni, RMS viene eseguito nel primo account. Quando si è pronti per modificare la password dell'account di servizio, eseguire la procedura seguente in ogni server RMS:

1.  Se il server si trova nel cluster, rimuoverlo dalla rotazione.
2.  Specificare il secondo account di servizio di RMS come account in cui eseguire RMS. Per le istruzioni sul modo per modificare l'account, vedere "[Modifica dell'account di servizio di RMS](https://technet.microsoft.com/f257d66d-b823-41e4-bcb7-7c90eb295238)", più avanti in questo argomento.
3.  Riavviare IIS.
4.  Se necessario, inserire di nuovo il server nella rotazione.

Una volta che tutti i server RMS utilizzano il secondo account di servizio RMS, è possibile modificare la password sul primo account di servizio RMS senza influire sul funzionamento del sistema RMS. In questo modo, è possibile passare tra i due account evitando i tempi di inattività di RMS.
