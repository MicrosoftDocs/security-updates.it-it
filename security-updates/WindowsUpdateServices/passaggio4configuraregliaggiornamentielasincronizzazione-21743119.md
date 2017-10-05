---
TOCTitle: 'Passaggio 4: Configurare gli aggiornamenti e la sincronizzazione'
Title: 'Passaggio 4: Configurare gli aggiornamenti e la sincronizzazione'
ms:assetid: 'deeaa7e1-9b50-45cb-9537-d75f70de3405'
ms:contentKeyID: 21743119
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd939924(v=WS.10)'
---

Passaggio 4: Configurare gli aggiornamenti e la sincronizzazione
================================================================

In questa sezione vengono illustrate le procedure di configurazione degli aggiornamenti che si desidera scaricare utilizzando Windows Server Update Services 3.0 Service Pack 2 (WSUS 3.0 SP2).

Procedure del passaggio 4
-------------------------

Tali procedure possono essere eseguite utilizzando sia la Configurazione guidata che la console di amministrazione WSUS.

1.  Salvare e scaricare informazioni relative al server padre e al server proxy.
2.  Scegliere la lingua degli aggiornamenti.
3.  Scegliere i prodotti per cui si desidera ricevere gli aggiornamenti.
4.  Scegliere le classificazioni degli aggiornamenti.
5.  Specificare la pianificazione per la sincronizzazione per questo server.

Dopo la configurazione della connessione di rete è possibile scaricare gli aggiornamenti sincronizzando il server di WSUS. La sincronizzazione ha inizio quando il server di WSUS contatta Microsoft Update. Dopo il contatto con WSUS, viene verificata la disponibilità di nuovi aggiornamenti rispetto all'ultima sincronizzazione. Quando il server WSUS viene sincronizzato per la prima volta, tutti gli aggiornamenti risultano disponibili e pronti per essere approvati per l'installazione. La sincronizzazione iniziale potrebbe richiedere molto tempo.

In questa sezione viene descritta la sincronizzazione con le impostazioni predefinite. In WSUS 3.0 SP2 sono inoltre disponibili opzioni che consentono di ridurre al minimo la larghezza di banda utilizzata durante la sincronizzazione.

Se si utilizza la Configurazione guidata di Windows Server Update Services
--------------------------------------------------------------------------

Nelle procedure del passaggio 3 è stata completata la configurazione del server padre e del server proxy. La prossima serie di procedure inizia alla pagina **Connetti al server padre** della Configurazione guidata.

**Salvare e scaricare informazioni relative al server padre e al server proxy**
1.  Nella pagina Connetti al server padre della Configurazione guidata fare clic sul pulsante **Avvia connessione**. Consente di salvare e aggiornare le impostazioni e raccogliere informazioni sugli aggiornamenti disponibili.

2.  Una volta stabilita la connessione sarà disponibile il pulsante **Interrompi connessione**. Se si verificano problemi di connessione fare clic su **Interrompi connessione**, correggere i problemi e riavviare la connessione.

3.  Al termine del download, fare clic su **Avanti**.

**Per scegliere la lingua degli aggiornamenti**
1.  La pagina Scelta lingue consente di ricevere aggiornamenti in tutte le lingue o da un sottoinsieme di lingue. Se si seleziona un sottoinsieme di lingue, sarà possibile risparmiare spazio su disco. È tuttavia importante scegliere tutte le lingue necessarie per tutti i client del server di WSUS.

    Se si sceglie di ottenere aggiornamenti solo per determinate lingue, selezionare **Scarica aggiornamenti solo nelle lingue seguenti** e selezionare le lingue delle quali si desidera ricevere gli aggiornamenti.

2.  Fare clic su **Avanti**.

**Per scegliere prodotti degli aggiornamenti**
1.  La pagina Scelta prodotti consente di specificare i prodotti per cui si desidera ottenere gli aggiornamenti. Selezionare le categorie dei prodotti, ad esempio Windows, o prodotti specifici, ad esempio Windows Server 2008. Se si seleziona una categoria di prodotti, verranno selezionati tutti i prodotti in essa contenuti.

2.  Fare clic su **Avanti**.

**Per scegliere le classificazioni degli aggiornamenti**
1.  La pagina Scelta classificazioni consente di specificare le classificazioni degli aggiornamenti che si desidera ottenere. Scegliere tutte le classificazioni o un loro sottoinsieme.

2.  Fare clic su **Avanti**.

**Per configurare la pianificazione della sincronizzazione**
1.  Nella pagina Imposta pianificazione della sincronizzazione scegliere se eseguire la sincronizzazione manualmente o automaticamente.

    Se si sceglie **Sincronizzazione manuale**, sarà necessario avviare il processo di sincronizzazione dalla console di amministrazione WSUS.

    Se si sceglie **Sincronizzazione automatica**, il server di WSUS verrà sincronizzato a intervalli specifici. Impostare l'ora della **prima sincronizzazione** e specificare il numero di **sincronizzazioni giornaliere** che si desidera vengano eseguite. Se, ad esempio, si specificano quattro sincronizzazioni giornaliere a partire dalle 3:00, queste verranno eseguite alle 3:00, alle 9:00, alle 15:00 e alle 21:00.

2.  Fare clic su **Avanti**.

3.  Nella pagina Operazione completata è possibile avviare la console di amministrazione WSUS mantenendo la selezione della casella di controllo **Avvia lo snap-in Amministrazione di Windows Server Update Services** ed è possibile avviare la prima sincronizzazione mantenendo la selezione della casella di controllo **Avvia sincronizzazione iniziale**.

4.  Fare clic su **Fine**.

 
    <table style="border:1px solid black;">
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th style="border:1px solid black;" ><img src="images/Dd939924.Important(WS.10).gif" />Importante</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td style="border:1px solid black;">Non è possibile salvare le modifiche di configurazione apportate durante la sincronizzazione del server. Attendere il completamento della sincronizzazione, quindi apportare le modifiche desiderate.
    </td>
    </tr>
    </tbody>
    </table>
 

Se si utilizza la console di amministrazione WSUS
-------------------------------------------------

Nelle procedure seguenti viene descritto come eseguire i passaggi di configurazione utilizzando la console di amministrazione WSUS.

**Per scegliere i prodotti e le classificazioni degli aggiornamenti**
1.  Nel riquadro **Opzioni** fare clic su **Prodotti e classificazioni**. Viene visualizzata una finestra di dialogo con le schede **Prodotti** e **Classificazioni**.

2.  Nella scheda **Prodotti** selezionare la categoria di prodotti o i prodotti specifici per cui si desidera che il server riceva aggiornamenti oppure selezionare **Tutti i prodotti**.

3.  Nella scheda **Classificazioni** selezionare le classificazioni degli aggiornamenti desiderate oppure selezionare **Tutte le classificazioni**.

4.  Fare clic su **OK** per salvare le selezioni.

**Per scegliere i file degli aggiornamenti e le lingue**
1.  Nel riquadro **Opzioni** selezionare **File degli aggiornamenti e lingue**. Viene visualizzata una finestra di dialogo con le schede **File degli aggiornamenti** e **Lingue degli aggiornamenti**.

2.  Nella scheda **File degli aggiornamenti** è possibile scegliere se **memorizzare i file degli aggiornamenti in locale sul server** o procedere all'installazione da Microsoft Update. Se si decide di memorizzare i file degli aggiornamenti su questo server, sarà possibile decidere se eseguire il download unicamente degli aggiornamenti approvati o di eseguire il download dei file per l'installazione rapida.

3.  Se nella scheda **Lingue degli aggiornamenti** si archiviano i file degli aggiornamenti in locale, scegliere **Scarica gli aggiornamenti per tutte le lingue** (impostazione predefinita) o **Scarica aggiornamenti solo nelle lingue specificate**. Se il server di WSUS dispone di server figli, questi riceveranno gli aggiornamenti solo nelle lingue specificate dal server padre.

4.  Fare clic su **OK** per salvare le impostazioni.

**Per sincronizzare il server di WSUS**
1.  Nel riquadro **Opzioni** fare clic su **Pianificazione della sincronizzazione**.

2.  Nella scheda **Imposta pianificazione della sincronizzazione** scegliere se eseguire la sincronizzazione manualmente o automaticamente.

    Se si sceglie **Sincronizzazione manuale**, sarà necessario avviare il processo di sincronizzazione dalla console di amministrazione WSUS.

    Se si sceglie **Sincronizzazione automatica**, il server di WSUS verrà sincronizzato a intervalli specifici. Impostare l'ora della **prima sincronizzazione** e specificare il numero di **sincronizzazioni giornaliere** che si desidera vengano eseguite. Se, ad esempio, si specificano quattro sincronizzazioni giornaliere a partire dalle 3:00, queste verranno eseguite alle 3:00, alle 9:00, alle 15:00 e alle 21:00.

3.  Fare clic su **OK** per salvare le selezioni.

4.  Nel riquadro di spostamento della console di amministrazione WSUS, selezionare **Sincronizzazioni**.

5.  Fare clic con il pulsante destro del mouse o spostarsi nel riquadro **Azioni** sulla destra, quindi scegliere **Sincronizza**.

    Se non viene visualizzato il riquadro **Azioni** a destra della console, fare clic su **Visualizza** sulla barra degli strumenti della console, scegliere **Personalizza** e assicurarsi che sia selezionata la casella di controllo **Riquadro azioni**.

6.  Al termine della sincronizzazione, fare clic su **Aggiornamenti** nel riquadro sinistro per visualizzare l'elenco degli aggiornamenti.

Passaggio successivo
--------------------

[Passaggio 5: Configurare gli aggiornamenti del client](https://technet.microsoft.com/5ae60ead-3e94-456c-a692-c0f193ea5d5a).

Risorse aggiuntive
------------------

[Guida dettagliata a Windows Server Update Services 3.0 SP2](https://technet.microsoft.com/4b504edc-93b3-45b0-a7e8-d0107f1a4442)
