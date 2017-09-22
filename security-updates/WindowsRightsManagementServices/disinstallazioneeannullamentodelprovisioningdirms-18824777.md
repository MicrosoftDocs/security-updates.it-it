---
TOCTitle: Disinstallazione e annullamento del provisioning di RMS
Title: Disinstallazione e annullamento del provisioning di RMS
ms:assetid: 'cae1ed5b-f716-41f0-8e14-7cbfef405331'
ms:contentKeyID: 18824777
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747753(v=WS.10)'
---

Disinstallazione e annullamento del provisioning di RMS
=======================================================

Potrebbe rendersi necessario rimuovere RMS da un server per vari motivi. Nel caso di un server di certificazione principale, il primo passaggio consiste nella rimozione di RMS dal server. A tale scopo, nella pagina **Amministrazione globale** del server che si desidera rimuovere, fare clic su **Rimuovi RMS da questo sito Web**. Non è necessario rimuovere un server licenze prima di disinstallare RMS.

| ![](images/Cc747753.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quando si rimuove l'ultimo server di certificazione principale in una struttura di Active Directory, l'oggetto punto di connessione del servizio viene rimosso da Active Directory. Se non si rimuove il server prima di disinstallare RMS, non è possibile eseguire il provisioning di un nuovo server di certificazione principale nella struttura fino a quando non si rimuove manualmente l'oggetto punto di connessione del servizio da Active Directory. |

Disinstallare RMS.

Quando si rimuove e si disinstalla RMS da un server autonomo o dall'ultimo server di un cluster, viene rimosso il database dei servizi di directory. I database di configurazione e di registrazione attività non vengono rimossi. Se, tuttavia, si aggiorna o si reinstalla RMS nel server, il database di registrazione attività viene sovrascritto da un nuovo database.

Quando si rimuove e si disinstalla RMS da un server in un cluster, i database di configurazione, di registrazione attività e dei servizi di directory del cluster non vengono rimossi. La tabella DRMS\_ClusterServer del database di configurazione viene aggiornata per indicare che il server è stato rimosso dal cluster.

Per ulteriori informazioni sull'interruzione dei server e sui relativi problemi, vedere “[Interruzione di server](https://technet.microsoft.com/52005e2e-9563-4ba0-906c-3cc76f9c378f)”, più indietro in questo argomento.
