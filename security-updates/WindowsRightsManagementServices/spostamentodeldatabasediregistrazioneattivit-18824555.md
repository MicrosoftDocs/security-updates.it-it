---
TOCTitle: Spostamento del database di registrazione attività
Title: Spostamento del database di registrazione attività
ms:assetid: '34ea8045-dc94-422e-9601-29927cfc1534'
ms:contentKeyID: 18824555
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720238(v=WS.10)'
---

Spostamento del database di registrazione attività
==================================================

In base alla configurazione predefinita di RMS, il database di configurazione e quello di registrazione attività si trovano nello stesso server. Verificare regolarmente che in SQL Server vi sia spazio sufficiente per entrambi i database.

Se le dimensioni del database di registrazione attività aumentano eccessivamente, è possibile spostare il database in un server diverso in qualsiasi momento. Il database di registrazione attività non può essere spostato utilizzando il sito Web Amministrazione, ma è necessario effettuare le operazioni riportate di seguito.

1.  Disattivare la registrazione come descritto in “[Per attivare o disattivare la registrazione](https://technet.microsoft.com/8e672f95-566f-4070-9a2a-2f70f087148f)”, più avanti in questo argomento.
2.  Copiare il database di registrazione attività dal server di origine a quello di destinazione tramite SQL Server Enterprise Manager. Assicurarsi che le tabelle e le stored procedure vengano create nel nuovo database. Uno dei metodi che consentono di copiare il database consiste nell'utilizzare Copia guidata database di SQL Server Enterprise Manager.
3.  Modificare il database di configurazione in base ai nuovi nomi del database e del server. Nella tabella DRMS\_ClusterPolicies del database di configurazione per il cluster di cui si sta spostando il database, effettuare le operazioni riportate di seguito.
    -   Modificare il valore del criterio LoggingDatabaseServer in base al nuovo nome del server database.
    -   Modificare il valore del criterio LoggingDatabaseName in base al nuovo nome del database.

    | ![](images/Cc720238.note(WS.10).gif)Nota                                                                                                                                                                                                    |
    |--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Poiché SQL Server Enterprise Manager non consente l'utilizzo dei campi db\_variant, non può essere utilizzato per questa attività. In alternativa, è possibile utilizzare Query Analyzer, incluso in SQL Server, oppure un altro strumento per la modifica dei database. |

4.  Riavviare IIS in tutti i server del cluster.
5.  Riattivare la registrazione.
