---
TOCTitle: Protezione durante il normale funzionamento di RMS
Title: Protezione durante il normale funzionamento di RMS
ms:assetid: '98f3d584-6320-4aa1-9959-7133cfdb6df7'
ms:contentKeyID: 18824710
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747609(v=WS.10)'
---

Protezione durante il normale funzionamento di RMS
==================================================

Una volta eseguita l'installazione e il provisioning di RMS, i servizi Web di RMS vengono eseguiti come applicazioni IIS, con accesso a diverse risorse di sistema che richiedono autenticazione e autorizzazione. Tutte le risorse di sistema richiedono autenticazione e non possono essere configurate in altro modo. La parte rimanente della pagina descrive il progetto dell'autorizzazione in RMS.

I servizi Web di RMS vengono eseguiti all'interno del contesto di un pool di applicazioni IIS. Ogni pool di applicazioni di IIS dispone di un'identità univoca che può corrispondere a un account utente di dominio, a un account utente locale, all'account locale Servizio di rete o all'account di sistema locale. Ognuno di questi account dispone di livelli di autorizzazione variabili all'interno del sistema. Quando viene eseguito il provisioning di RMS, è possibile scegliere di eseguire i servizi Web di RMS come account del sistema locale, oppure come account utente di dominio. Quindi, questo account diviene l'identità del pool di applicazioni per il pool di applicazioni di RMS. Il pool di applicazioni per il sito Web Amministrazione globale è "DRMS Application Pool". Il pool di applicazioni per il sito Web di cui viene eseguito il provisioning è denominato "\_DRMSAppPool1." Il servizio di registrazione attività di RMS viene eseguito come un servizio di Windows separato nello stesso account specificato per l'identità del pool di applicazioni di RMS.

Le risorse necessarie ai servizi Web di RMS per l'accesso comprendono alcuni file e cartelle nel sistema, database e procedure memorizzate sul server database, il registro locale, Active Directory, la cache di assembly, la memoria e altri processi in esecuzione sul sistema. Il servizio di registrazione attività di RMS deve anche poter accedere alla coda di registrazione sul sistema locale. A ognuna di queste risorse sono associati DACL specifici che definiscono gli utenti autorizzati ad accedere alla risorsa e le operazioni che è possibile eseguire sulla risorsa. 

Per semplificare l'assegnazione delle autorizzazioni e la gestione degli account di servizio, tutte le autorizzazioni necessarie vengono assegnate al gruppo del servizio RMS locale creato da RMS durante il provisioning. Poiché è un membro del gruppo, l'account del servizio RMS riceve tutte le autorizzazioni assegnate al gruppo stesso.

Nell'elenco seguente vengono riepilogate le autorizzazioni assegnate al gruppo del servizio RMS:

-   Autorizzazione di lettura per le directory principali virtuali
-   Autorizzazione di scrittura per la directory della cache dell'assembly
-   Autorizzazione di scrittura per la directory temporanea di sistema
-   Autorizzazione di scrittura per la coda della registrazione attività
-   Autorizzazione di lettura per Active Directory

Utilizzando Microsoft SQL Server 2000 come server database, notare l'impiego di un metodo leggermente differente per assegnare le autorizzazioni rispetto a quanto avviene in Windows Server 2003. Il provisioning di RMS crea un accesso per l'account di servizio di RMS su SQL Server. Se si è scelto di eseguire il provisioning di RMS mediante l'account di sistema locale, viene creato un accesso a SQL Server utilizzando il formato *DOMINIO\\nome\_computer*t, dove *DOMINIO* è il nome del dominio Active Directory di cui il computer è membro, mentre *nome\_computer* è il nome del server. Viene creato un ruolo SQL chiamato rms\_service a cui vengono assegnate tutte le autorizzazioni necessarie. L'accesso dell'account di servizio di RMS viene aggiunto a questo gruppo. All'account di servizio di RMS non viene concessa alcuna autorizzazione esplicita.

Inoltre, SQL Server assegna un proprietario (DBO, DataBase Owner) a ciascun database. Durante il provisioning, la proprietà del database viene assegnata come segue:

-   Come DBO del database di configurazione viene definito l'account di dominio utilizzato per il provisioning di RMS.
-   Come DBO dei database dei servizi di directory e di registrazione attività viene definito l'account di servizio di RMS

Le autorizzazioni relative a tutte le risorse create da RMS sono state selezionate molto attentamente durante la progettazione di RMS, con una particolare attenzione alla protezione. Non dovrebbero esistere particolari motivi per modificare le autorizzazioni assegnate durante il provisioning per le risorse. Se dopo il provisioning si ha la necessità di cambiare account o password utente dell'account di servizio, ciò è possibile dalla pagina Web Amministrazione globale di RMS. Per ulteriori informazioni, vedere "Per modificare l'account di servizio di RMS" in "Gestione di un server RMS" in questa documentazione.
