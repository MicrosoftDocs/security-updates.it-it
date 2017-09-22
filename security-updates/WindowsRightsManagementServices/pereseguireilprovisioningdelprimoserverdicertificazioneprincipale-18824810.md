---
TOCTitle: Per eseguire il provisioning del primo server di certificazione principale
Title: Per eseguire il provisioning del primo server di certificazione principale
ms:assetid: 'debc42f3-74ff-4c99-b7a4-4921fccdabc2'
ms:contentKeyID: 18824810
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747768(v=WS.10)'
---

Per eseguire il provisioning del primo server di certificazione principale
==========================================================================

Per eseguire questa procedura, è necessario avere effettuato l'accesso locale al sito Web di amministrazione con un account utente di dominio che faccia parte del gruppo Administrators nel computer in cui si sta effettuando l'accesso. La procedura può essere inoltre eseguita dai membri del gruppo Domain Admins. Se si utilizza un database di SQL Server remoto, l'account deve inoltre disporre del ruolo di creatori del database in SQL Server. Per garantire maggiore protezione, eseguire la procedura utilizzando **Esegui come**.

Per visualizzare la pagina **Amministrazione globale**, fare clic su **Start**, scegliere **Tutti i programmi**, quindi **Windows RMS** e infine **Amministrazione di Windows RMS**.

Per ogni server, è possibile eseguire il provisioning di RMS in un unico sito Web. Se si desidera eseguire il provisioning di RMS in un sito Web diverso da quello predefinito, utilizzare Gestione Internet Information Services per aggiungere il sito Web prima di avviare il processo di provisioning. Se il sito Web di cui si desidera eseguire il provisioning non è visualizzato nell'elenco di siti Web, chiudere la pagina **Amministrazione globale**, aggiungere il sito Web e riavviare il processo.

Qualora si stia distribuendo RMS in un ambiente in cui il livello funzionale del dominio di Active Directory è impostato sulla modalità nativa di Microsoft Windows 2000, RMS potrebbe non leggere l'attributo **memberOf** degli oggetti di Active Directory quando si cerca di espandere l'appartenenza al gruppo. Per consentire la lettura dell'attributo **memberOf**, l'account di servizio di RMS deve utilizzare un account di dominio membro del gruppo incorporato Pre-Windows 2000-Compatible Access dell'insieme di strutture.

Se si digita un URL personalizzato per il cluster, assicurarsi di registrarlo nel proprio DNS (Domain Name System) e verificarne il funzionamento. Se si sta eseguendo una distribuzione abilitata per Internet, verificare che l'URL sia disponibile sia in Internet che all'interno dell'organizzazione. Se per i file dei servizi Web è stato abilitato il protocollo SSL, per l'URL del cluster è necessario specificare HTTPS.

Provisioning del primo server di certificazione principale
----------------------------------------------------------

#### Per eseguire il provisioning del primo server di certificazione principale

1.  Dopo aver installato RMS in un server che rappresenterà il primo server di certificazione principale in un insieme di strutture di Active Directory, visualizzare la pagina **Amministrazione globale**.

2.  Accanto al sito Web in cui si desidera eseguire il provisioning di RMS, selezionare **Effettua il provisioning di RMS in questo sito Web**. È possibile selezionare il sito Web predefinito oppure un altro sito Web creato in Internet Information Services (IIS) a questo scopo.

    | ![](images/Cc747768.Warning(WS.10).gif)Avviso                                                                                                                                                                                                             |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Non è supportata l'esecuzione di altri servizi o siti Web nello stesso server di RMS. Questa operazione potrebbe implicare l'esecuzione di più applicazioni e servizi tramite lo stesso account di RMS e la conseguente esposizione delle chiavi private a operazioni non autorizzate. |

3.  Nell'area **Database di configurazione,** l'opzione predefinita prevede la creazione del database di configurazione nel server locale. Per un database locale, è possibile utilizzare un server database quale SQL Server™ 2000 con SP3 o Microsoft SQL Server 2000 Desktop Engine (MSDE). Se si utilizza un database remoto oppure si esegue il server database sul server locale, ma l'istanza del server database ha un nome diverso da quello del server, selezionare **Database remoto** e immettere il nome del server database.

    | ![](images/Cc747768.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | È consigliabile utilizzare Microsoft SQL Server Desktop Engine per supportare i database di RMS solo in ambienti di verifica perché Microsoft SQL Server Desktop Engine non supporta interfacce di rete. Inoltre, le condizioni per l'utilizzo di Microsoft SQL Server Desktop Engine impediscono di utilizzare gli strumenti client di SQL Server client per modificare un database di Microsoft SQL Server Desktop Engine. A causa di questa limitazione, non sarà possibile visualizzare informazioni sulla registrazione attività né modificare dati memorizzati nel database di configurazione. |

4.  Nell'area **Account di servizio di RMS,** specificare l'account di servizio di RMS in cui si desidera eseguire RMS per le operazioni più comuni. Nel caso di un'installazione in un solo server, è possibile selezionare l'account di sistema locale o un account di dominio. Per tutte le altre installazioni è necessario specificare un account di dominio. Per un account di dominio specificare il nome account in base al formato *nome\_dominio*\\*nome\_utente* e quindi la password.

    | ![](images/Cc747768.Warning(WS.10).gif)Avviso                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
    |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Poiché l'account di sistema locale è autorizzato ad accedere a quasi tutte le risorse del sistema operativo, potrebbe creare problemi a livello di protezione. Se possibile, evitare l'utilizzo dell'account di sistema locale come account di servizio di RMS. Creare invece un account speciale di utente di dominio, da utilizzare come account di servizio RMS, senza concedergli alcuna autorizzazione speciale. L'account di servizio di RMS non può essere lo stesso account di dominio utilizzato per l'installazione di RMS. |

    | ![](images/Cc747768.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                               |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Per motivi di protezione, è consigliabile creare un account utente di dominio speciale da utilizzare come account di servizio di RMS, evitando di concedere autorizzazioni speciali a tale account. L'account di servizio di RMS non può essere lo stesso account di dominio utilizzato per l'installazione di Windows RMS con Service Pack 1. |

5.  Nell'area **URL cluster,** digitare l'URL del server o del cluster che verrà utilizzato per i client della rete interna. Per impostazione predefinita viene utilizzato il nome del server, ad esempio Contoso-cert. Se necessario, è possibile modificarlo, ad esempio per configurare un URL per il cluster o un bilanciatore del carico utilizzato dal cluster. È inoltre possibile selezionare HTTP o HTTPS. Per ulteriori informazioni sulla configurazione di un URL del cluster, vedere la sezione **Note** al termine della presente procedura. In seguito al provisioning, è possibile configurare un URL di cluster esterno nelle pagine Web di amministrazione da utilizzare con i client esterni alla rete interna.

6.  Nell'area **Protezione della chiave privata e registrazione,** selezionare il meccanismo per la protezione della chiave privata del server effettuando una delle seguenti operazioni.

    -   **Utilizzare la protezione chiave privata basata su software predefinita**. In questo caso, la chiave privata viene memorizzata nel database di configurazione di RMS. È necessario specificare una password complessa per la crittografia della chiave nel database.

    | ![](images/Cc747768.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                                                                                                                                                                      |
    |---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Conservare la password in un luogo sicuro per poterne disporre in futuro. Memorizzare una copia di backup del database di configurazione, protetta da password, in una posizione sicura. In questo modo, sarà possibile ripristinare RMS qualora il database di SQL Server sia danneggiato. Se per qualunque motivo si modifica la password, eseguire una nuova copia di backup del database di configurazione protetto da tale password e salvarli entrambi in una posizione sicura. |

    -   **Utilizzare un provider del servizio di crittografia (CSP, Cryptographic Service Provider)**. Per utilizzare un provider del servizio di crittografia o un modulo di protezione hardware (HSM, Hardware Security Module), deselezionare la casella di controllo **Utilizza protezione chiave privata basata su software predefinita**. Nell'elenco **Selezionare il provider del servizio di crittografia,** selezionare il CSP o il modulo di protezione hardware installato.

    | ![](images/Cc747768.note(WS.10).gif)Nota                                                                                |
    |------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Poiché per RMS è necessario un provider di crittografia RSA (Rivest-Shamir-Adleman), nell'elenco di CSP sono inclusi solo i provider di questo tipo. |

    | ![](images/Cc747768.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                 |
    |-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | È consigliabile utilizzare la protezione chiave privata basata su software predefinita o un modulo di protezione hardware. Se si utilizza un diverso provider del servizio di crittografia basato su software, assicurarsi di disporre delle corrette procedure di gestione della chiave organizzativa, ad esempio le procedure di backup e ripristino, per il provider prima di utilizzarlo con RMS. |

7.  Questo passaggio è valido solo nel caso in cui sia stato selezionato un CSP. Per specificare la coppia di chiavi del server da utilizzare, effettuare una delle seguenti operazioni.

    -   Nel caso di una nuova installazione, selezionare **Crea una nuova coppia di chiavi pubblica/privata**.
    -   Nel caso in cui si stia eseguendo il ripristino o l'aggiornamento di un server RMS esistente, selezionare **Utilizza una coppia di chiavi pubblica/privata esistente**. Nella sezione **Contenitore chiave esistente,** scegliere **Sfoglia** e selezionare il contenitore della coppia di chiavi del server.

    | ![](images/Cc747768.note(WS.10).gif)Nota                                 |
    |-------------------------------------------------------------------------------------------------------|
    | I CPS Base, Enhanced e Strong di Microsoft condividono lo stesso luogo di archiviazione della chiave. |

    | ![](images/Cc747768.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Se non si utilizza una coppia di chiavi esistente durante le operazioni di ripristino o di aggiornamento di un server RMS, è necessario eliminare gli archivi di licenze dei client RMS esistenti (eliminazione delle licenze d'uso e dei certificati per account con diritti) e fornire nuove licenze dal server per poter utilizzare il contenuto. |

8.  In **Connettività Internet del server,** specificare se il server effettua una connessione a Internet per ottenere un certificato concessore di licenze server.

    -   Selezionare **In linea** per connettersi automaticamente con il Servizio di Enrollment Microsoft e ottenere un certificato concessore di licenze server durante il processo di provisioning.
    -   Selezionare **Non in linea** se il server RMS non dispone di una connessione a Internet o se si desidera ottenere manualmente il certificato concessore di licenze e importarlo nel server RMS dopo il processo di provisioning.

9.  In **Nome certificato concessore di licenze server,** immettere un nome da utilizzare nel certificato concessore di licenze server. Per impostazione predefinita, viene utilizzato il nome del server.

10. Se nell'organizzazione viene utilizzato un server proxy per la connessione a Internet, selezionare la casella di controllo **Questo computer utilizza un server proxy per la connessione a Internet**, quindi digitare l'indirizzo e la porta del server proxy.

    Se il server proxy richiede l'autenticazione, selezionare il tipo e specificare il nome utente e la password utilizzabili per l'autenticazione. Se si utilizza l'autenticazione Windows integrata, è necessario specificare anche un dominio.

    | ![](images/Cc747768.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
    |--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Questa impostazione può essere modificata in seguito al processo di provisioning dalla pagina **Impostazioni di protezione** nel sito Web Amministrazione di RMS. Tuttavia, questa pagina non è disponibile prima della registrazione del server al Servizio di Enrollment Microsoft. Se nell'organizzazione viene richiesto di utilizzare un server proxy per la connessione a Internet, ma è stata selezionata l'opzione **Non in linea** per **Connettività Internet del server** che non consente la configurazione di un server proxy, non è possibile modificare le impostazioni né per il processo di registrazione nè per il server proxy prima di aver completato il processo di registrazione manuale o aver eseguito nuovamente il provisioning di RMS. |

11. In **Contatto amministrativo,** digitare l'indirizzo di posta elettronica dell'amministratore da contattare in caso di problemi durante il provisioning di altri server. Dopo avere eseguito il provisioning, sarà possibile modificare questo indirizzo di posta elettronica.

12. Nell'area **Revoca,** selezionare se si desidera consentire a terze parti di revocare il certificato concessore di licenze server. Se si seleziona questa opzione, digitare il percorso e il nome del file della chiave pubblica di terze parti.

13. Scegliere **Invia**.

    Quando si fa clic su **Invia**, si esegue il provisioning del servizio. Se è stata selezionata la registrazione in linea, viene avviato anche il processo di registrazione per il server di certificazione principale. Durante il processo, RMS genera una coppia di chiavi pubblica/privata e invia la chiave pubblica al Servizio di Enrollment Microsoft. Il Servizio di Enrollment Microsoft crea un certificato concessore di licenze server e lo invia nuovamente al database di configurazione entro pochi minuti. Se si utilizza la registrazione non in linea, è necessario completare l'attività descritta in "[Per registrare manualmente un server di certificazione principale](https://technet.microsoft.com/aecdebb5-b28b-4b58-937a-392bb6ce9643)" prima di configurare il server RMS.

    | ![](images/Cc747768.note(WS.10).gif)Nota                                                                                                                                                                                                                                                            |
    |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Il server potrà essere utilizzato solo dopo che il punto di connessione del servizio sarà stato registrato in Active Directory. Eseguire la procedura disponibile in "[Per registrare un punto di connessione del servizio](https://technet.microsoft.com/630cc3c3-9ed9-4423-8874-cbaceb43b353)" per completare questo processo. |

Per informazioni sull'esecuzione del provisioning di ulteriori server di certificazione principale e la loro aggiunta a un cluster, vedere "[Per aggiungere un server a un cluster](https://technet.microsoft.com/db635238-5528-4bec-9cc6-8244e2b3d733)", più avanti in questo argomento.
