---
TOCTitle: Per aggiungere un server a un cluster
Title: Per aggiungere un server a un cluster
ms:assetid: 'db635238-5528-4bec-9cc6-8244e2b3d733'
ms:contentKeyID: 18824800
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747690(v=WS.10)'
---

Per aggiungere un server a un cluster
=====================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Per ogni server, è possibile eseguire il provisioning di RMS in un unico sito Web. Se si desidera eseguire il provisioning di RMS in un sito Web diverso da quello predefinito, utilizzare Gestione Internet Information Services per aggiungere il sito Web prima di avviare il processo di provisioning. Se il sito Web di cui si desidera eseguire il provisioning non è visualizzato nell'elenco di siti Web, chiudere la pagina **Amministrazione globale**, aggiungere il sito Web e riavviare il processo.

Qualora si stia distribuendo RMS in un ambiente in cui il livello funzionale del dominio di Active Directory è impostato sulla modalità nativa di Microsoft Windows 2000, RMS potrebbe non leggere l'attributo **memberOf** degli oggetti di Active Directory quando si cerca di espandere l'appartenenza al gruppo. Per consentire la lettura dell'attributo **memberOf**, l'account di servizio di RMS deve utilizzare un account di dominio membro del gruppo incorporato Pre-Windows 2000-Compatible Access dell'insieme di strutture.

Aggiunta di un server a un cluster
----------------------------------

#### Per aggiungere un server a un cluster

1.  Dopo avere installato RMS in un server che si desidera aggiungere a un cluster di certificazione principale o a un cluster licenze, visualizzare la pagina **Amministrazione globale**.

2.  Accanto al sito Web in cui si desidera eseguire il provisioning di RMS, selezionare **Aggiungi questo server a un cluster**. È possibile selezionare il sito Web predefinito oppure un altro sito Web creato in Internet Information Services (IIS) a questo scopo.

    | ![](images/Cc747690.Warning(WS.10).gif)Avviso                                                                                                                                                                                                             |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Non è supportata l'esecuzione di altri servizi o siti Web nello stesso server di RMS. Questa operazione potrebbe implicare l'esecuzione di più applicazioni e servizi tramite lo stesso account di RMS e la conseguente esposizione delle chiavi private a operazioni non autorizzate. |

3.  Nell'area **Account di servizio di RMS,** digitare il nome dell'account in base al formato nome\_dominio\\nome\_utente e la password dell'account di servizio di RMS in cui viene eseguito RMS per le operazioni più comuni. Deve trattarsi di un account di dominio. Tutti i server di un cluster devono essere in esecuzione nello stesso account di servizio di RMS.

    | ![](images/Cc747690.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                               |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Per motivi di protezione, è consigliabile creare un account utente di dominio speciale da utilizzare come account di servizio di RMS, evitando di concedere autorizzazioni speciali a tale account. L'account di servizio di RMS non può essere lo stesso account di dominio utilizzato per l'installazione di Windows RMS con Service Pack 1. |

4.  Nell'area **Database di configurazione,** specificare i nomi del server di database e il nome del database di configurazione del cluster. Il database selezionato determina il cluster a cui viene aggiunto il server.

5.  Nell'area **Protezione della chiave privata,** selezionare il meccanismo utilizzato dal cluster per la protezione della chiave privata. Per la protezione della chiave privata basata su software predefinita, specificare la password utilizzata per crittografare la chiave privata al momento del provisioning del primo server nel cluster.

6.  Scegliere **Invia**.

    Qualora vengano visualizzati messaggi di errore, non chiudere la pagina. Correggere gli errori, utilizzare il comando IISReset dalla riga di comando e riavviare IIS, tornare alla pagina precedente e reimmettere le informazioni per il provisioning, quindi scegliere nuovamente **Invia**. Se viene visualizzato un messaggio di errore indicante il timeout della richiesta, chiudere la finestra, verificare che nel sistema siano soddisfatti i requisiti hardware minimi e riprovare a eseguire il provisioning del server.
