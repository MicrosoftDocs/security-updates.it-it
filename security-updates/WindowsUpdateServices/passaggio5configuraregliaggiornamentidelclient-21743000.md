---
TOCTitle: 'Passaggio 5: Configurare gli aggiornamenti del client'
Title: 'Passaggio 5: Configurare gli aggiornamenti del client'
ms:assetid: '5ae60ead-3e94-456c-a692-c0f193ea5d5a'
ms:contentKeyID: 21743000
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Dd939830(v=WS.10)'
---

Passaggio 5: Configurare gli aggiornamenti del client
=====================================================

In Windows Server Update Services 3.0 (WSUS 3.0 SP2), durante l'installazione di WSUS, IIS viene configurato automaticamente per distribuire la versione più recente di Aggiornamenti automatici a tutti i computer client che contattano il server di WSUS.

La modalità ottimale per la configurazione di Aggiornamenti automatici varia in base all'ambiente di rete. In un ambiente in cui viene utilizzato il servizio directory Active Directory®, è possibile utilizzare un oggetto Criteri di gruppo basato sul dominio esistente oppure crearne uno nuovo. In un ambiente senza Active Directory è possibile utilizzare l'oggetto Criteri di gruppo locale. In questo passaggio, è necessario configurare Aggiornamenti automatici e fare in modo che i computer client puntino al server di WSUS.

Le procedure seguenti sono valide per una rete che esegue Active Directory, gestita mediante Criteri di gruppo. Per eseguire queste procedure, è necessario avere familiarità con Criteri di gruppo e utilizzarli per gestire la rete.

Per ulteriori informazioni su Criteri di gruppo, vedere il sito Web Techcenter di Criteri di gruppo all'indirizzo [http://go.microsoft.com/fwlink/?LinkID=47375](http://go.microsoft.com/fwlink/?linkid=47375) (le informazioni potrebbero essere in lingua inglese).

 
-

Procedure del passaggio 5
-------------------------

Al passaggio 4 è stata completata la configurazione degli aggiornamenti da scaricare. Utilizzare queste procedure per configurare gli aggiornamenti automatici per i computer client.

1.  Configurare Aggiornamenti automatici in Criteri di gruppo.
2.  Puntare un computer client al server di WSUS.
3.  Avviare manualmente il rilevamento in base al server di WSUS.

Eseguire le prime due procedure sull'oggetto Criteri di gruppo basato sul dominio desiderato, quindi continuare con la terza procedura a un prompt dei comandi nel computer client.

**Per configurare Aggiornamenti automatici**
1.  In Console Gestione Criteri di gruppo cercare l'oggetto Criteri di gruppo per il quale si desidera configurare WSUS e fare clic su **Modifica**.

2.  In Console Gestione Criteri di gruppo espandere **Configurazione computer**, **Modelli amministrativi** e **Componenti di Windows**, quindi fare clic su **Windows Update**.

3.  Nel riquadro dei dettagli fare doppio clic su **Configura aggiornamenti automatici**.

4.  Fare clic su **Attivata** e quindi su una delle opzioni seguenti:

    -   **Avviso per download e installazione**. Se viene selezionata questa opzione, per tutti gli utenti che accedono con privilegi di amministratore verranno visualizzate una notifica prima del download e una prima dell'installazione degli aggiornamenti.
    -   **Download e avviso installazione**. Se viene selezionata questa opzione, il download degli aggiornamenti verrà avviato automaticamente. Al termine del download, per tutti gli utenti che accedono con privilegi di amministratore viene visualizzata una notifica prima dell'installazione degli aggiornamenti.
    -   **Download e pianifica installazione**. Se viene selezionata questa opzione, il download degli aggiornamenti verrà avviato automaticamente, quindi l'installazione verrà eseguita nel giorno e all'ora specificati.
    -   **Consenti scelta impostazioni all'amministratore locale**. Se viene selezionata questa opzione, gli amministratori locali possono utilizzare Aggiornamenti automatici nel Pannello di controllo per selezionare un'opzione di configurazione. ad esempio l'ora dell'installazione pianificata. Gli amministratori locali non possono disattivare Aggiornamenti automatici.

5.  Fare clic su **OK**.

**Per puntare i computer client al server di WSUS**
1.  Nel riquadro dei dettagli di **Windows Update** fare doppio clic su **Specifica il percorso del servizio di aggiornamento Microsoft nella rete Intranet**.

2.  Fare clic su **Attivata** e digitare l'URL HTTP dello stesso server di WSUS nelle caselle **Impostare il servizio di aggiornamento nella rete Intranet per il rilevamento degli aggiornamenti** e **Impostare il server per le statistiche nella rete Intranet**. Ad esempio, digitare *http://nomeserver* in entrambe le caselle e quindi fare clic su **OK**.

 
<table style="border:1px solid black;">
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th><img src="images/Dd939830.note(WS.10).gif" />Nota</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Se si utilizza l'oggetto Criteri di gruppo locale per puntare il computer a WSUS, tale impostazione diverrà immediatamente effettiva e il computer verrà visualizzato nella console di amministrazione WSUS in breve tempo. È possibile rendere più rapido questo processo avviando manualmente il rilevamento.
</td>
</tr>
</tbody>
</table>
 

Dopo la configurazione di un computer client, è necessario attendere alcuni minuti per la visualizzazione del computer stesso nella pagina **Computer** della console di amministrazione WSUS. Un computer client configurato mediante un oggetto Criteri di gruppo basato sul dominio verrà visualizzato nella pagina circa 20 minuti dopo l'aggiornamento di Criteri di gruppo, ovvero dopo l'applicazione di tutte le nuove impostazioni relative ai criteri nel computer client. Per impostazione predefinita, l'aggiornamento di Criteri di gruppo viene eseguito in background ogni 90 minuti con un offset casuale compreso tra 0 e 30 minuti. Se si desidera eseguire quanto prima l'aggiornamento di Criteri di gruppo, è possibile accedere a un prompt dei comandi nel computer client e digitare**gpupdate /force**.

Nei computer client configurati mediante l'oggetto Criteri di gruppo locale, Criteri di gruppo viene applicato immediatamente. L'aggiornamento diverrà effettivo dopo circa 20 minuti.

Se il rilevamento viene eseguito manualmente non sarà necessario attendere 20 minuti per il contatto tra il computer client e WSUS.

**Per avviare manualmente il rilevamento in base al server di WSUS**
1.  Nel computer client fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

2.  Digitare **cmd** nella casella **Apri**, quindi fare clic su **OK**.

3.  Al prompt dei comandi digitare **wuauclt.exe /detectnow**. Questa opzione della riga di comando indica ad Aggiornamenti automatici di contattare immediatamente il server di WSUS.

Passaggio successivo
--------------------

[Passaggio 6: Configurare i gruppi di computer](https://technet.microsoft.com/70518732-2179-4e41-9609-7f9999867f41).

Risorse aggiuntive
------------------

[Guida dettagliata a Windows Server Update Services 3.0 SP2](https://technet.microsoft.com/4b504edc-93b3-45b0-a7e8-d0107f1a4442)
