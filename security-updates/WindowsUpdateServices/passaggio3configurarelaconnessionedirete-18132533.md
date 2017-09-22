---
TOCTitle: 'Passaggio 3: Configurare la connessione di rete'
Title: 'Passaggio 3: Configurare la connessione di rete'
ms:assetid: 'cd77566d-7780-4ce4-aa56-41183c65c4a7'
ms:contentKeyID: 18132533
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc708559(v=WS.10)'
---

Passaggio 3: Configurare la connessione di rete
===============================================

Dopo l'installazione di WSUS, è possibile accedere alla console WSUS per configurare WSUS e iniziare a utilizzarlo. Per impostazione predefinita, WSUS è configurato per l'utilizzo di Microsoft Update come origine degli aggiornamenti. Se si dispone di un server proxy nella rete, configurare WSUS per l'utilizzo del server proxy mediante la console WSUS. Se è presente un firewall aziendale tra WSUS e Internet, potrebbe essere necessario configurare il firewall per consentire a WSUS di scaricare gli aggiornamenti.

| ![](images/Cc708559.note(WS.10).gif)Nota                                                                                                                                                                                                                                                   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Anche se il download degli aggiornamenti da Microsoft Update richiede la connessione a Internet, WSUS consente di importare gli aggiornamenti in reti non connesse a Internet. Per ulteriori informazioni, vedere il white paper “Deploying Microsoft Windows Server Update Services” (informazioni in lingua inglese). |

Nel passaggio 3 vengono illustrate le procedure seguenti:

-   Configurare il firewall per consentire a WSUS di scaricare gli aggiornamenti.
-   Aprire la console WSUS.
-   Configurare le impostazioni del server proxy per consentire a WSUS di scaricare gli aggiornamenti.

**Per configurare il firewall**
-   Se è presente un firewall aziendale tra WSUS e Internet, potrebbe essere necessario configurare il firewall per consentire a WSUS di scaricare gli aggiornamenti. Per scaricare gli aggiornamenti da Microsoft Update, il server di WSUS utilizza la porta 80 per il protocollo HTTP e la porta 443 per il protocollo HTTPS. Questa impostazione non è configurabile.

-   Se tali porte e protocolli non sono aperti a tutti gli indirizzi, è possibile limitare l'accesso solo ai domini seguenti in modo che WSUS e Aggiornamenti automatici possano comunicare con Microsoft Update:

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

| ![](images/Cc708559.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| I passaggi per la configurazione del firewall descritti sopra sono validi per un firewall aziendale posizionato tra WSUS e Internet. Poiché WSUS avvia tutto il proprio traffico di rete, non è necessario configurare Windows Firewall nel server di WSUS. Anche se per la connessione tra Microsoft Update e WSUS le porte 80 e 443 devono essere aperte, è possibile configurare più server di WSUS per la sincronizzazione con una porta personalizzata. Per ulteriori informazioni sulla sincronizzazione dei server di WSUS con una porta personalizzata, vedere il white paper “Deploying Microsoft Windows Server Update Services” (informazioni in lingua inglese). |

**Per aprire la console WSUS**
-   Nel server di WSUS, fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Strumenti di amministrazione** e quindi **Microsoft Windows Server Update Services**.

| ![](images/Cc708559.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Per utilizzare la console WSUS, è necessario essere membro del gruppo di protezione WSUS Administrators o Administrators locale nel server in cui WSUS è installato. Se in Windows Server 2003 non si aggiunge **http://&lt;***nome sito Web di WSUS***&gt;** all'elenco dei siti nell'area Intranet locale in Internet Explorer, è possibile che vengano richieste le credenziali a ogni apertura della console WSUS. Se si modifica l'assegnazione della porta in IIS dopo l'installazione di WSUS, è necessario aggiornare manualmente il collegamento presente nel menu di avvio. La console WSUS può inoltre essere aperta da Internet Explorer in ogni server o computer della rete immettendo l'URL seguente: **http://***nomeserverWSUS***/WSUSAdmin** |

**Per specificare un server proxy**
1.  Sulla barra degli strumenti della console WSUS fare clic su **Opzioni** e quindi fare clic su **Opzioni di sincronizzazione**.

2.  Nella casella **Server proxy** selezionare la casella di controllo **Usa un server proxy per la sincronizzazione** e quindi digitare il nome del server proxy e il numero di porta nelle caselle corrispondenti. La porta 80 è la porta predefinita.

3.  Se si desidera utilizzare le credenziali di un utente specifico per la connessione al server proxy, selezionare la casella di controllo **Usa credenziali utente per la connessione al server proxy** e quindi digitare il nome utente, il dominio e la password dell'utente nelle caselle corrispondenti. Se si desidera attivare l'autenticazione di base per l'utente che si connette al server proxy, selezionare la casella di controllo **Consenti autenticazione di base (password non crittografata)**.

4.  In **Attività** fare clic su **Salva impostazioni** e quindi fare clic su **OK** nella finestra di dialogo che verrà visualizzata.
