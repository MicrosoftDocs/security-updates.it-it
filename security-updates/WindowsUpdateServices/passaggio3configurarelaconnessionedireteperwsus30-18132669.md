---
TOCTitle: 'Passaggio 3. Configurare la connessione di rete per WSUS 3.0'
Title: 'Passaggio 3. Configurare la connessione di rete per WSUS 3.0'
ms:assetid: 'dbc9d9f7-cf52-4539-9f9e-3e823273218a'
ms:contentKeyID: 18132669
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc708602(v=WS.10)'
---

Passaggio 3. Configurare la connessione di rete per WSUS 3.0
============================================================

Dopo aver installato WSUS 3.0, verrà automaticamente avviata la Configurazione guidata. È inoltre possibile avviare la procedura tramite la pagina **Opzioni** della console di WSUS 3.0.

Prima di iniziare il processo di configurazione assicurarsi di conoscere le risposte alle domande seguenti:

1. Il firewall del server è configurato per consentire ai client di accedere al server?

2. Questo computer può essere connesso al server padre, ad esempio Microsoft Update?

3. Si dispone del nome del server proxy e delle credenziali utente per il server proxy, se necessario?

Per impostazione predefinita, WSUS è configurato per l'utilizzo di Microsoft Update come origine degli aggiornamenti. Se si dispone di un server proxy nella rete, è possibile configurare WSUS per l'utilizzo del server proxy. Se è presente un firewall aziendale tra WSUS e Internet, potrebbe essere necessario configurare il firewall per consentire a WSUS di scaricare gli aggiornamenti.

| ![](images/Cc708602.note(WS.10).gif)Nota                                                                                                          |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Anche se il download degli aggiornamenti da Microsoft Update richiede la connessione a Internet, WSUS consente di importare gli aggiornamenti in reti non connesse a Internet. |

**Nel passaggio 3 vengono illustrate le procedure seguenti**:

-   Configurare il firewall.
-   Specificare il modo in cui il server scaricherà gli aggiornamenti, da Microsoft Update o da un altro server di WSUS.
-   Configurare le impostazioni del server proxy per consentire a WSUS di scaricare gli aggiornamenti.

**Per configurare il firewall**
-   Se è presente un firewall aziendale tra WSUS e Internet, potrebbe essere necessario configurare il firewall per consentire a WSUS di scaricare gli aggiornamenti. Per scaricare gli aggiornamenti da Microsoft Update, il server di WSUS utilizza la porta 80 per il protocollo HTTP e la porta 443 per il protocollo HTTPS. Questa impostazione non è configurabile.

-   Se l'organizzazione non consente alla porta 80 o alla porta 443 di essere aperte a tutti gli indirizzi, sarà possibile limitare l'accesso solo ai domini seguenti in modo che WSUS e Aggiornamenti automatici possano comunicare con Microsoft Update:

    -   http://windowsupdate.microsoft.com
    -   http://\*.windowsupdate.microsoft.com
    -   https://\*.windowsupdate.microsoft.com
    -   http://\*.update.microsoft.com
    -   https://\*.update.microsoft.com
    -   http://\*.windowsupdate.com
    -   http://download.windowsupdate.com
    -   http://download.microsoft.com
    -   http://\*.download.windowsupdate.com
    -   http://wustat.windows.com
    -   http://ntservicepack.microsoft.com

| ![](images/Cc708602.note(WS.10).gif)Nota                                                                                                                                                                                    |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Le istruzioni per la configurazione del firewall descritte sono valide per un firewall aziendale posizionato tra WSUS e Internet. Poiché WSUS avvia tutto il proprio traffico di rete, non è necessario configurare Windows Firewall nel server di WSUS. |

Anche se per la connessione tra Microsoft Update e WSUS le porte 80 e 443 devono essere aperte, è possibile configurare più server di WSUS per la sincronizzazione con una porta personalizzata.

Le due procedure seguenti presuppongono che si utilizzi la configurazione guidata. Nell'ultima sezione di questa procedura, sarà possibile ottenere informazioni su come avviare lo snap-in Amministrazione WSUS e configurare il server utilizzando la pagina **Opzioni**.

**Per specificare in che modo il server deve scaricare gli aggiornamenti**
1.  Nella Configurazione guidata, dopo aver scelto di partecipare al programma Analisi utilizzo Microsoft Update, fare clic su **Avanti** per selezionare il server padre.

2.  Se si sceglie la sincronizzazione da Microsoft Update, la procedura terminerà con questa pagina. Fare clic su **Avanti** o selezionare **Specifica server proxy** nel riquadro a sinistra.

3.  Se si sceglie di eseguire la sincronizzazione da un altro server di WSUS, specificare il nome del server e la porta su cui tale server comunicherà con il server padre.

4.  Per utilizzare SSL, selezionare la casella di controllo **Usa SSL per la sincronizzazione delle informazioni sugli aggiornamenti**. In tal caso i server utilizzeranno la porta 443 per la sincronizzazione. È consigliabile accertarsi che sia questo server sia il server padre supportino SSL.

5.  Se si tratta di un server di replica, selezionare la casella di controllo **Replica del server padre**.

6.  A questo punto la configurazione del server padre è completata. Fare clic su **Avanti** o selezionare **Specifica server proxy** dal pannello sinistro.

**Per configurare le impostazioni del server proxy**
1.  Nella pagina **Specifica server proxy** della configurazione guidata selezionare la casella di controllo **Usa un server proxy per la sincronizzazione** e quindi digitare il nome del server proxy e il numero di porta nelle caselle corrispondenti. La porta 80 è la porta predefinita.

2.  Se si desidera utilizzare le credenziali di un utente specifico per la connessione al server proxy, selezionare la casella di controllo **Usa credenziali utente per la connessione al server proxy** e quindi digitare il nome utente, il dominio e la password dell'utente nelle caselle corrispondenti. Se si desidera attivare l'autenticazione di base per l'utente che stabilisce la connessione al server proxy, selezionare la casella di controllo **Consenti autenticazione di base (password non crittografata)**.

3.  A questo punto la configurazione del server proxy è completata. Fare clic su **Avanti** per accedere alla pagina successiva in cui è possibile avviare la configurazione del processo di sincronizzazione.

Le due procedure seguenti presuppongono che si utilizzi lo snap-in Amministrazione WSUS per la configurazione. Queste due procedure illustrano come avviare lo snap-in Amministrazione WSUS e configurare il server utilizzando la pagina **Opzioni**.

**Per avviare la console di amministrazione WSUS**
-   Per avviare la console di amministrazione WSUS, fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Microsoft Windows Server Update Services 3.0**.

| ![](images/Cc708602.note(WS.10).gif)Nota                                                                                                                                                                                                                                                  |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Per utilizzare tutte le funzionalità della console WSUS è necessario essere membro del gruppo di protezione WSUS Administrators o Administrators locale nel server in cui è installato WSUS. I membri del gruppo di protezione Reporter WSUS, tuttavia, hanno accesso di sola lettura alla console di amministrazione. |

**Per specificare un'origine degli aggiornamenti e un server proxy**
1.  Nella console WSUS fare clic su **Opzioni** nel riquadro sinistro sotto al nome del server e quindi fare clic su **Origine aggiornamenti e server proxy** nel pannello centrale.

2.  Verrà visualizzata una finestra di dialogo con le schede **Origine aggiornamenti** e **Server proxy**.

3.  Nella scheda **Origine aggiornamenti** selezionare il percorso da cui questo server scaricherà gli aggiornamenti. Se si sceglie la sincronizzazione da Microsoft Update, impostazione predefinita, la procedura terminerà con questa pagina.

4.  Se si sceglie di eseguire la sincronizzazione da un altro server di WSUS, sarà necessario specificare la porta in cui i server comunicheranno. La porta predefinita è la porta 80. Se si sceglie una porta differente, sarà necessario assicurarsi che entrambi i server siano in grado di utilizzare tale porta.

5.  È inoltre possibile specificare se utilizzare SSL quando si esegue la sincronizzazione dal server padre di WSUS. In tal caso i server utilizzeranno la porta 443 per la sincronizzazione dal server padre.

6.  Se il server è una replica del secondo server di WSUS, selezionare la casella di controllo **Replica del server padre**. In questo caso tutti gli aggiornamenti devono essere approvati solo nel server padre di WSUS.

7.  Nella scheda **Server proxy** selezionare la casella di controllo **Usa un server proxy per la sincronizzazione** e quindi digitare il nome del server proxy e il numero di porta nelle caselle corrispondenti. La porta 80 è la porta predefinita.

8.  Se si desidera utilizzare le credenziali di un utente specifico per la connessione al server proxy, selezionare la casella di controllo **Usa credenziali utente per la connessione al server proxy** e quindi digitare il nome utente, il dominio e la password dell'utente nelle caselle corrispondenti. Se si desidera attivare l'autenticazione di base per l'utente che si connette al server proxy, selezionare la casella di controllo **Consenti autenticazione di base (password non crittografata)**.

9.  Fare clic su **OK** per salvare le impostazioni.
