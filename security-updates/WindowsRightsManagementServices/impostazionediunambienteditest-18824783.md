---
TOCTitle: Impostazione di un ambiente di test
Title: Impostazione di un ambiente di test
ms:assetid: 'cdd96b05-49e2-4b6f-bfae-40b5c028ec66'
ms:contentKeyID: 18824783
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747673(v=WS.10)'
---

Impostazione di un ambiente di test
===================================

RMS si integra con l'infrastruttura Active Directory e i server di database esistenti, come quelli che eseguono Microsoft SQL Server™ 2000. A causa della natura critica di questi componenti di supporto, è opportuno eseguire un test completo di RMS in un ambiente di prova isolato prima di distribuirlo nella propria organizzazione. Questo richiede la configurazione nell'ambiente di prova di installazioni separate di Active Directory e di un server di database.

È opportuno iniziare con la configurazione più semplice consistente in un server RMS di un insieme di strutture con un server di database e un client. Dopo aver acquisito la necessaria familiarità con RMS, la configurazione può essere ampliata in modo da corrispondere il più possibile alla topologia che verrà distribuita nell'ambiente di produzione della propria organizzazione, aggiungendo altri insiemi di strutture e accessi esterni, se necessario. Anche se l'ambiente di prova potrebbe non includere tutti gli elementi ridondanti e le configurazioni a siti multipli del piano di distribuzione dell'organizzazione, si dovrebbe includere almeno un server che esegue ciascuno dei componenti di supporto che si desiderano distribuire.

L'elenco che segue descrive una possibile configurazione minima per un ambiente di prova da utilizzare per il test di una configurazione base di RMS:

-   Un controller di dominio che esegue Windows 2000 Server con Service Pack 3 (SP3) o versione successiva, con installato SQL Server 2000 con SP3a. SQL Server ospita i database RMS di registrazione attività, configurazione e servizi directory. Se il database si trova sullo stesso server di RMS, RMS può essere utilizzato con Microsoft SQL Server 2000 Desktop Engine (MSDE 2000) Versione A o SQL Server. Se verrà utilizzato un server remoto per il supporto dei database, è necessario SQL Server. Il client MSDE 2000 può essere scaricato dal sito Web di Microsoft.

| ![](images/Cc747673.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Windows 2000 Server con Service Pack 3 (SP3) è il requisito minimo per il controller di dominio, ma si consiglia Windows Server 2003 a causa dei miglioramenti nelle prestazioni dell'espansione dei gruppi di Active Directory. È consigliabile utilizzare MSDE per supportare i database di RMS solo in ambienti di verifica perché MSDE non supporta interfacce di rete. Inoltre, i termini d'uso MSDE 2000 specificano che è impossibile utilizzare gli strumenti client SQL Server per gestire MSDE 2000. Con questa restrizione, potrebbe essere impossibile visualizzare le informazioni di registrazione attività o modificare i dati registrati nel database di configurazione. |

-   Un server di certificazione principale Windows Server 2003, su cui sono stati eseguiti l'installazione e il provisioning di RMS. Man mano che il test procede come desiderato, è possibile aggiungere altri server per creare cluster di certificazione principale.
-   Un computer client che esegue Windows XP Professional, il client RMS e un'applicazione abilitata per RMS.
-   Account utente con attributi per gli indirizzi di posta elettronica in Active Directory.

Per informazioni sull'installazione e la configurazione di un'infrastruttura RMS di base, oltre che sull'applicazione dei requisiti dell'infrastruttura a un ambiente di produzione, vedere "[Configurazione di un'infrastruttura di base](https://technet.microsoft.com/3a0a3a47-e755-4455-bb22-0e05053723e4)", successivamente nell'argomento.
