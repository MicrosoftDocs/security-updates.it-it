---
TOCTitle: Interruzione di server
Title: Interruzione di server
ms:assetid: '52005e2e-9563-4ba0-906c-3cc76f9c378f'
ms:contentKeyID: 18824602
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747568(v=WS.10)'
---

Interruzione di server
======================

In alcuni casi, potrebbe essere necessario interrompere il funzionamento di un server RMS, ad esempio in una delle situazioni descritte di seguito.

-   Problemi o aggiornamenti alle apparecchiature, che implicano la sostituzione di determinati server.
-   Diminuzione del traffico relativo a gestione delle licenze d'uso e di pubblicazione, che implica la rimozione delle autorizzazioni da alcuni server.
-   Necessità di rimuovere i server da specifiche posizioni per motivi legali, che implica la rimozione delle autorizzazioni da un intero cluster.
-   Fusioni o vendite di divisioni o di parti di un'organizzazione, che implicano un trasferimento delle risorse.
-   Fusioni di due organizzazioni che utilizzano RMS, che provoca la ridondanza delle due installazioni.

Prima di interrompere un server, eseguire il backup di tutti i database di RMS utilizzati dal server, in particolare del database di configurazione. Per ulteriori informazioni sul backup dei database, vedere “Backup e ripristino del sistema RMS” nella sezione "Pianificazione di una distribuzione di RMS", in questa documentazione. .

Dopo avere eseguito il backup dei database, sarà possibile rimuovere il server. I requisiti per la rimozione di un server RMS dipendono dal ruolo del server e dalla topologia dell'installazione di RMS.

-   **Rimozione di un server da un cluster**. Se il server di RMS che si desidera interrompere fa parte di un cluster nel quale sono presenti altri server RMS attivi e necessari, per rimuovere un singolo server dal cluster, è necessario rimuovere e disinstallare RMS dal server che si desidera interrompere, rimuovere l'hardware dal cluster e archiviare i database.
    | ![](images/Cc747568.note(WS.10).gif)Nota                                                                                           |
    |-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Solo i server del cluster di certificazione principale devono essere rimossi prima di disinstallare RMS. Questo processo non è necessario per i server licenze. |

-   **Interruzione di un server autonomo**. Se il server RMS che si desidera interrompere è un server autonomo, ovvero non fa parte di un cluster composto da più server, che deve essere sostituito con un nuovo server, attenersi alla seguente procedura. Rimuovere e disinstallare il server RMS esistente, rimuoverlo dalla rete e quindi installare ed eseguire immediatamente il provisioning di RMS nel server sostitutivo. Configurare il nuovo server RMS affinché vengano utilizzati lo stesso URL e lo stesso database di configurazione del server RMS interrotto. Fino a quando non vengono eseguiti l'installazione e il provisioning del server sostitutivo, gli utenti non potranno utilizzare i contenuti pubblicati dal server interrotto.
    | ![](images/Cc747568.Important(WS.10).gif)Importante                                                                                                                                                                                                                           |
    |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Se nel server RMS che viene sostituito viene utilizzato un modulo di protezione hardware, è necessario trasferire la struttura di protezione nel nuovo server prima di installare RMS ed eseguirne il provisioning. Per istruzioni, vedere la documentazione fornita con il modulo di protezione hardware. |

-   **Sostituzione di un'installazione di RMS con un'altra installazione di RMS esistente**. In alcuni casi, potrebbe rendersi necessario interrompere un'installazione di RMS e sostituirla con un'altra installazione esistente, ad esempio nel caso della fusione tra aziende che utilizzano RMS.

Quando si rimuove e si disinstalla un server, il server viene rimosso dalla tabella ClusterServer del database di configurazione e il database dei servizi di directory viene eliminato da SQL Server. Per le istruzioni sull'annullamento del provisioning e la disinstallazione di RMS, vedere "[Per annullare il provisioning di RMS](https://technet.microsoft.com/9fa63daa-5fb9-4afd-8371-b38248619857)" e "[Per disinstallare RMS](https://technet.microsoft.com/885e3b4f-ea32-466f-9f7f-d8440b0f7c28)", più avanti in questo argomento.
