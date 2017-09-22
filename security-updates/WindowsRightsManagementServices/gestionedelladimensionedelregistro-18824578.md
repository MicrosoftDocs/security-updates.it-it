---
TOCTitle: Gestione della dimensione del registro
Title: Gestione della dimensione del registro
ms:assetid: '431b32b3-02f0-4666-b52c-183eb65154fd'
ms:contentKeyID: 18824578
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720271(v=WS.10)'
---

Gestione della dimensione del registro
======================================

Tramite il servizio di registrazione attività, vengono inviate al database di SQL Server grandi quantità di dati. È consigliabile controllare regolarmente il database di registrazione attività per assicurarsi che nel disco vi sia spazio sufficiente per i dati. Se si ritiene che le quantità di dati siano troppo elevate e che alcune informazioni non siano necessarie, è possibile impostare alcuni filtri di SQL Server affinché nei file di registro vengano memorizzati solo i dati necessari. Per informazioni sulle modalità di filtro delle informazioni di registrazione attività, vedere la Guida di SQL Server Enterprise Manager.

Se le dimensioni del database di registrazione attività sono eccessive rispetto allo spazio disponibile nel disco, spostare il database in un server diverso, come descritto in "[Spostamento del database di registrazione attività](https://technet.microsoft.com/34ea8045-dc94-422e-9601-29927cfc1534)", più aventi in questo argomento.

| ![](images/Cc720271.Important(WS.10).gif)Importante                                                                                                                                                                                                                                                                                                                                                                   |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| È inoltre possibile utilizzare Monitor di sistema per monitorare regolarmente la dimensione della coda di messaggi di registrazione attività in uscita. Se la dimensione della coda aumenta in modo considerevole, assicurarsi che il servizio listener di registrazione attività stia funzionando correttamente. Per ulteriori informazioni sull'utilizzo di Monitor di sistema, vedere Guida in linea e supporto tecnico di Windows Server 2003. |
