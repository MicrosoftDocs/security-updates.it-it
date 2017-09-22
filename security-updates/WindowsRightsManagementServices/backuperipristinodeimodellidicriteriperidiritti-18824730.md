---
TOCTitle: Backup e ripristino dei modelli di criteri per i diritti
Title: Backup e ripristino dei modelli di criteri per i diritti
ms:assetid: 'a6ed3328-4128-45e8-9236-3de484b460de'
ms:contentKeyID: 18824730
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747625(v=WS.10)'
---

Backup e ripristino dei modelli di criteri per i diritti
========================================================

Per proteggere i dati preziosi relativi ai modelli di criteri per i diritti, eseguire regolarmente il backup dei dati del modello presenti nel database di configurazione su un supporto e riporre tale supporto in un luogo sicuro. Qualora si verifichi un errore di sistema, sarà quindi possibile ripristinare i modelli di criteri per i diritti dalla copia di backup.

Effettuare una delle operazioni descritte di seguito.

-   Eseguire il backup dell'intero database di configurazione che include i dati del modello di criteri per i diritti. Per ulteriori informazioni sul backup di un database di SQL Server, vedere la documentazione di SQL Server.
    oppure
-   Eseguire il backup dei dati del modello di criteri per i diritti presenti nel database di configurazione. A tale scopo, esportare il GUID e le informazioni TemplateData dalla tabella DRMS\_RightsTemplate in un nuovo file di testo. Per ulteriori informazioni sull'esportazione dei dati da un database di SQL Server, vedere la documentazione di SQL Server.

Se si desidera ripristinare i dati del modello di criteri per i diritti presente nel database di configurazione, estrarre il GUID e le informazioni TemplateData dalla tabella DRMS\_RightsTemplate nella copia di backup del database di configurazione oppure importare semplicemente i dati dal file di testo. Per ulteriori informazioni sull'esecuzione di queste operazioni, vedere la documentazione di SQL Server.

| ![](images/Cc747625.note(WS.10).gif)Nota                                                               |
|-------------------------------------------------------------------------------------------------------------------------------------|
| Per definire una pianificazione per l'esecuzione dei modelli di criteri per i diritti, rivolgersi all'amministratore di SQL Server. |
