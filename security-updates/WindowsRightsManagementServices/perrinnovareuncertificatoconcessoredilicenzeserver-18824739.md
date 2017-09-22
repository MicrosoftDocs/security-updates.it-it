---
TOCTitle: Per rinnovare un certificato concessore di licenze server
Title: Per rinnovare un certificato concessore di licenze server
ms:assetid: 'affce9cf-8b46-4293-8e1c-ee06f2ca6537'
ms:contentKeyID: 18824739
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747636(v=WS.10)'
---

Per rinnovare un certificato concessore di licenze server
=========================================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Se si è selezionato il metodo di rinnovo non in linea e, per richiedere il certificato concessore di licenze server, si accede a Internet con un computer dotato di una migliore configurazione di protezione del browser, ad esempio un computer con Windows Server 2003 o Windows XP con Service Pack 2, assicurarsi di aver aggiunto l'URL del sito Web del Servizio di Enrollment all'area Siti attendibili per consentire il download del certificato concessore di licenze server. Tale URL è https://activation.drm.microsoft.com.

Se si utilizza il processo di Registrazione non in linea, assicurarsi che il computer dal quale viene inviata la richiesta di registrazione al Servizio di Enrollment Microsoft abbia GTE Cyber Trust Root CA installato nell'archivio certificati. Per impostazione predefinita, questa Autorità di certificazione (CA) è attendibile sui computer con Windows Server 2003. Se il computer dispone di una versione diversa di Windows, è possibile rendere attendibile questa CA installando gli ultimi aggiornamenti dei certificati da Windows Update.

Rinnovo di un certificato concessore di licenze server
------------------------------------------------------

#### Per rinnovare un certificato concessore di licenze server

1.  Visualizzare la pagina **Amministrazione globale** e selezionare **Amministra RMS in questo sito Web** accanto al sito Web in cui si desidera rinnovare un certificato.

2.  Nella pagina **Amministrazione,** fare clic sul pulsante **Rinnova** nell'area **Risorse del cluster**. Viene visualizzata la finestra di dialogo Rinnova.

3.  Se il server è connesso a Internet, selezionare l'opzione **In linea** e fare clic su **Rinnova** per rinnovare automaticamente il certificato concessore di licenze server.

4.  Se il server non è connesso a Internet, selezionare l'opzione **Non in linea** e fare clic sul pulsante **Esporta**. Viene visualizzata la finestra di dialogo **Download file**.

5.  Scegliere **Salva**. Viene visualizzata la finestra di dialogo **Salva con nome**.

    | ![](images/Cc747636.note(WS.10).gif)Nota                                                                                                                                       |
    |-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Nella finestra di dialogo **Download file**, non fare clic su **Apri**. Se si fa clic su **Apri**, viene visualizzato un messaggio di errore e il file per la richiesta di registrazione non viene salvato. |

6.  Fare clic su **Salva** per esportare la richiesta di rinnovo su un file. Per impostazione predefinita, il file viene salvato sul desktop e denominato *Nome\_server*RenewalRequest.xml, dove *nome\_server* viene sostituito dal nome del server RMS. È possibile salvare il file in un'altra posizione, scegliendola dal menu a discesa Salva in. Inoltre, si può modificare il nome predefinito del file immettendo una nuova voce in **Nome file**.

7.  Al termine dell'operazione di salvataggio del file per la richiesta di rinnovo, viene visualizzata la finestra di dialogo **Download completato**. Fare clic su **Apri** per visualizzare il codice XML nel file, ma non apportare alcuna modifica al file. Per aprire la cartella nella quale è salvato il file, fare clic su **Apri cartella**. Al termine della ricerca e della verifica della posizione del file, fare clic su **Chiudi**.

8.  Trasferire il file per la richiesta di rinnovo dal server a un computer in grado di connettersi a Internet, quindi andare al sito Web del [Servizio di Enrollment]() (https://go.microsoft.com/fwlink/?LinkId=25828).

9.  Seguire le istruzioni presenti sul sito Web per ottenere un certificato concessore di licenze server.

10. Trasferire quindi il certificato al server di certificazione principale.

11. Nell'area **Risorse del cluster,** fare clic su **Rinnova**. Viene visualizzata la finestra di dialogo **Rinnova**.

12. Nella finestra di dialogo **Rinnova**, fare clic sul pulsante **Sfoglia** e individuare il certificato concessore di licenze server scaricato, quindi fare clic sul pulsante **Importa**.

13. Fare clic su **Sì** per confermare che si desidera importare il certificato selezionato.

14. Dopo avere eseguito il rinnovo del certificato concessore di licenze server, l'area **Risorse del cluster** sarà aggiornata per visualizzare la nuova data di scadenza del certificato concessore di licenze server.

Per ulteriori informazioni sul rinnovo dei certificati concessori di licenze server, vedere "[Gestione dei certificati concessore di licenze server](https://technet.microsoft.com/549979ad-13ee-4abc-8281-3e002a5a9561)", più indietro in questo argomento.
