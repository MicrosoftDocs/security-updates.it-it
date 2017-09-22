---
TOCTitle: 'Passaggio 5: Aggiornare e configurare Aggiornamenti automatici'
Title: 'Passaggio 5: Aggiornare e configurare Aggiornamenti automatici'
ms:assetid: '4ac8d574-f48e-4d9d-86c9-9aeb0f57e750'
ms:contentKeyID: 18132212
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720533(v=WS.10)'
---

Passaggio 5: Aggiornare e configurare Aggiornamenti automatici
==============================================================

Per i computer client di WSUS è necessaria una versione compatibile di Aggiornamenti automatici. Durante il programma di installazione di WSUS, IIS viene configurato automaticamente per distribuire la versione più recente di Aggiornamenti automatici a tutti i computer client che contattano il server di WSUS.

| ![](images/Cc720533.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Molte versioni di Aggiornamenti automatici vengono aggiornate automaticamente alla versione compatibile con WSUS dopo il puntamento al server di WSUS. La versione di Aggiornamenti automatici inclusa in Windows XP senza Service Pack non viene invece aggiornata automaticamente. Per istruzioni relative a un ambiente in cui è disponibile Windows XP senza Service Pack e non è mai stato utilizzato Software Update Services (SUS), vedere il white paper “Deploying Microsoft Windows Server Update Services” (informazioni in lingua inglese). |

La modalità ottimale per la configurazione di Aggiornamenti automatici varia in base all'ambiente di rete. In un ambiente Active Directory è possibile utilizzare un oggetto Criteri di gruppo basato su Active Directory. In un ambiente non Active Directory è possibile utilizzare l'oggetto Criteri di gruppo locale. A seconda che venga utilizzato l'oggetto Criteri di gruppo locale o un oggetto Criteri di gruppo archiviato in un controller di dominio, è necessario puntare i computer client al server di WSUS e quindi configurare Aggiornamenti automatici.

Le istruzioni seguenti sono valide per una rete che esegue Active Directory gestita mediante Criteri di gruppo. Per eseguire le procedure illustrate di seguito, è necessario avere già impostato Criteri di gruppo e conoscerne l'utilizzo. È necessario creare un nuovo oggetto Criteri di gruppo per le impostazioni di WSUS e quindi collegarlo a livello di dominio.

Per ulteriori informazioni su Criteri di gruppo, vedere la [pagina relativa a Criteri di gruppo](http://go.microsoft.com/fwlink/?linkid=47375) all'indirizzo http://go.microsoft.com/fwlink/?LinkID=47375.

Nel passaggio 5 vengono illustrate le procedure seguenti:

-   Caricare il modello amministrativo di WSUS.
-   Configurare Aggiornamenti automatici.
-   Puntare i computer client al server di WSUS.
-   Avviare manualmente il rilevamento nel computer client.

Eseguire le tre procedure seguenti in un oggetto Criteri di gruppo basato su Active Directory.

**Per aggiungere il modello amministrativo di WSUS**
1.  Nell'Editor oggetti Criteri di gruppo fare clic su uno dei nodi di **Modelli amministrativi**.

2.  Scegliere **Aggiunta/Rimozione modelli** dal menu **Azione**.

3.  Fare clic su **Aggiungi**.

4.  Nella finestra di dialogo **Modelli criteri** fare clic su **wuau.adm** e quindi su **Apri**.

5.  Nella finestra di dialogo **Aggiunta/Rimozione modelli** fare clic su **Chiudi**.

**Per configurare il comportamento di Aggiornamenti automatici**
1.  Nell'Editor oggetti Criteri di gruppo espandere **Configurazione computer**, **Modelli amministrativi**, nonché **Componenti di Windows** e quindi fare clic su **Windows Update**.

2.  Nel riquadro dei dettagli fare doppio clic su **Configura aggiornamenti automatici**.

3.  Fare clic su **Attivata** e quindi su una delle opzioni seguenti:

    -   **Avviso per download e installazione.** Se si seleziona questa opzione, per tutti gli utenti che accedono con privilegi di amministratore vengono visualizzate una notifica prima del download e una prima dell'installazione degli aggiornamenti.
    -   **Download e avviso installazione.** Se si seleziona questa opzione, il download degli aggiornamenti viene avviato automaticamente. Al termine del download, per tutti gli utenti che accedono con privilegi di amministratore viene visualizzata una notifica prima dell'installazione degli aggiornamenti.
    -   **Download e pianifica installazione.** Se Aggiornamenti automatici è configurato per l'esecuzione di un'installazione pianificata, è inoltre necessario impostare il giorno e l'ora per l'installazione pianificata ricorrente.
    -   **Consenti scelta impostazioni all'amministratore locale.** Se si seleziona questa opzione, gli amministratori locali possono utilizzare Aggiornamenti automatici nel Pannello di controllo per selezionare l'opzione di configurazione desiderata, ad esempio l'ora dell'installazione pianificata. Gli amministratori locali non possono disattivare Aggiornamenti automatici.

4.  Fare clic su **OK**.

| ![](images/Cc720533.note(WS.10).gif)Nota                                                                            |
|--------------------------------------------------------------------------------------------------------------------------------------------------|
| L'opzione **Consenti scelta impostazioni all'amministratore locale** viene visualizzata solo se Aggiornamenti automatici è compatibile con WSUS. |

**Per puntare il computer client al server di WSUS**
1.  Nell'Editor oggetti Criteri di gruppo espandere **Configurazione computer**, **Modelli amministrativi**, nonché **Componenti di Windows** e quindi fare clic su **Windows Update**.

2.  Nel riquadro dei dettagli fare doppio clic su **Specificare la posizione del servizio di aggiornamento Microsoft nella rete Intranet**.

3.  Fare clic su **Attivata** e digitare l'URL HTTP dello stesso server di WSUS nelle caselle **Impostare il servizio di aggiornamento nella rete Intranet per il rilevamento degli aggiornamenti** e **Impostare il server per le statistiche nella rete Intranet**. Ad esempio, digitare **http://***nomeserver* in entrambe le caselle.

4.  Fare clic su **OK**.

| ![](images/Cc720533.note(WS.10).gif)Nota                                                                                                                                                                                                                                            |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se si utilizza l'oggetto Criteri di gruppo locale per il puntamento di questo computer a WSUS, tale impostazione diverrà immediatamente effettiva e il computer verrà visualizzato nella console WSUS entro 20 minuti circa. È possibile rendere più rapido questo processo avviando manualmente il rilevamento. |

Dopo la configurazione di un computer client, è necessario attendere alcuni minuti per la visualizzazione del computer stesso nella pagina **Computer** della console WSUS. Un computer client configurato mediante un oggetto Criteri di gruppo basato su Active Directory verrà visualizzato in tale pagina 20 minuti circa dopo l'aggiornamento di Criteri di gruppo, ovvero dopo l'applicazione di tutte le nuove impostazioni nel computer client. Per impostazione predefinita, i Criteri di gruppo vengono aggiornati in background ogni 90 minuti con un offset casuale compreso tra 0 e 30 minuti. Se si desidera che i Criteri di gruppo vengano aggiornati prima, è possibile accedere a un prompt dei comandi nel computer client e digitare: **gpupdate /force**.

Nei computer client configurati mediante l'oggetto Criteri di gruppo locale i Criteri di gruppo vengono applicati immediatamente. L'applicazione diverrà effettiva dopo 20 minuti circa.

Dopo l'applicazione dei Criteri di gruppo, è possibile avviare manualmente il rilevamento. Se si esegue tale operazione, non è necessario attendere 20 minuti per il contatto tra il computer client e WSUS.

**Per avviare manualmente il rilevamento in base al server di WSUS**
1.  Nel computer client fare clic sul pulsante **Start** e quindi scegliere **Esegui**.

2.  Digitare **cmd** e quindi fare clic su **OK**.

3.  Al prompt dei comandi digitare **wuauclt.exe /detectnow**. Questa opzione della riga di comando indica ad Aggiornamenti automatici di contattare immediatamente il server di WSUS.
