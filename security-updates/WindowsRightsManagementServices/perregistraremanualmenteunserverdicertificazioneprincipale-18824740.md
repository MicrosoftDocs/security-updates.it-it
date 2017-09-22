---
TOCTitle: Per registrare manualmente un server di certificazione principale
Title: Per registrare manualmente un server di certificazione principale
ms:assetid: 'aecdebb5-b28b-4b58-937a-392bb6ce9643'
ms:contentKeyID: 18824740
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747727(v=WS.10)'
---

Per registrare manualmente un server di certificazione principale
=================================================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web Amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando Esegui come.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Se si utilizza il processo di Registrazione non in linea, impedire i tentativi di connessione al server RMS da parte dei client RMS per ottenere le licenze fino a quando non sia stata completata la registrazione. Se i client tentano di connettersi a un server RMS non registrato, nei servizi Web si verifica una condizione di errore che ne impedisce l'utilizzo. Se non si possono escludere tali tentativi, è consigliabile reimpostare IIS dopo il completamento della registrazione per eliminare le possibili condizioni di errore.

Se si è selezionato il metodo Registrazione non in linea e per richiedere il certificato concessore di licenze server si accede a Internet con un computer dotato di una migliore configurazione di protezione del browser, ad esempio un computer con Windows Server 2003 o Windows XP Service Pack 2, assicurarsi di aver aggiunto l'URL del sito Web del Servizio di Enrollment all'area Siti attendibili per consentire il download del certificato concessore di licenze server. Tale URL è https://activation.drm.microsoft.com.

Se si utilizza il processo di Registrazione non in linea, assicurarsi che il computer dal quale viene inviata la richiesta di registrazione al Servizio di Enrollment Microsoft abbia GTE Cyber Trust Root CA installato nell'archivio certificati. Per impostazione predefinita, questa Autorità di certificazione (CA) è attendibile sui computer con Windows Server 2003. Se il computer dispone di una versione diversa di Windows, è possibile rendere attendibile questa CA installando gli ultimi aggiornamenti dei certificati da Windows Update.

Registrazione manuale di un server di certificazione principale
---------------------------------------------------------------

#### Per registrare manualmente un server di certificazione principale

1.  Dopo avere installato RMS sul server scelto come server di certificazione principale, aprire la pagina **Amministrazione globale**, quindi fare clic su **Amministra RMS in questo sito Web** accanto al sito Web sul quale si desidera importare il certificato concessore di licenze server principale.

2.  Nell'area **Risorse del cluster,** fare clic su **Registra**. Viene visualizzata la finestra di dialogo **Registra**.

3.  Selezionare l'opzione **Non in linea** e fare clic sul pulsante **Esporta**. Viene visualizzata la finestra di dialogo **Download file**.

4.  Scegliere **Salva**. Viene visualizzata la finestra di dialogo **Salva con nome**.

    | ![](images/Cc747727.note(WS.10).gif)Nota                                                                                                                                       |
    |-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Nella finestra di dialogo **Download file**, non fare clic su **Apri**. Se si fa clic su **Apri**, viene visualizzato un messaggio di errore e il file per la richiesta di registrazione non viene salvato. |

5.  Fare clic su **Salva** per esportare la richiesta di registrazione su un file. Per impostazione predefinita, il file viene salvato sul desktop e denominato *Nome\_server*EnrollRequest.xml, dove *nome\_server* viene sostituito dal nome del server RMS. È possibile salvare il file in un'altra posizione, scegliendola dal menu a discesa **Salva in**. Inoltre, si può modificare il nome predefinito del file immettendo una nuova voce in **Nome file**.

6.  Al termine dell'operazione di salvataggio del file per la richiesta di registrazione, viene visualizzata la finestra di dialogo **Download completato**. Fare clic su **Apri** per visualizzare il codice XML nel file, ma non apportare alcuna modifica al file. Per aprire la cartella nella quale è salvato il file, fare clic su **Apri cartella**. Al termine della ricerca e della verifica della posizione del file, fare clic su **Chiudi**.

7.  Trasferire il file per la richiesta di registrazione dal server a un computer in grado di connettersi a Internet, quindi andare al [sito Web del servizio Enrollment]().

8.  Seguire le istruzioni presenti sul sito Web per ottenere un certificato concessore di licenze server.

9.  Trasferire quindi il certificato al server di certificazione principale.

10. Nell'area **Risorse del cluster,** fare clic su **Registra**. Viene visualizzata la finestra di dialogo **Registra**.

11. Nella finestra di dialogo **Registra**, fare clic sul pulsante **Sfoglia** e individuare il certificato concessore di licenze server scaricato, quindi fare clic sul pulsante **Importa**.

12. Fare clic su **Sì** per confermare che si desidera importare il certificato selezionato.

13. L'area **Risorse del cluster** sarà aggiornata per visualizzare il certificato concessore di licenze server.
