---
TOCTitle: 'Configurazione dell''URL di una Extranet'
Title: 'Configurazione dell''URL di una Extranet'
ms:assetid: '88fec9ff-c96c-4d20-8856-0485e7507572'
ms:contentKeyID: 18824682
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747661(v=WS.10)'
---

Configurazione dell'URL di una Extranet
=======================================

Se si desidera che l'installazione di RMS consenta di supportare utenti della Extranet, è possibile aggiungere un server licenze o un cluster dedicato all'utilizzo da parte della Extranet.

Quando si esegue il provisioning di un server licenze Extranet, specificare un URL del cluster per tale server, come per qualsiasi altro server RMS. Solitamente, l'URL specificato è un URL interno cui gli altri utenti della Extranet non possono accedere. Si tratta dell'URL utilizzato da RMS per il rilevamento del servizio. L'URL deve essere valido all'interno dell'organizzazione.

Se si aggiunge un URL cluster Extranet a un server RMS già in uso, è necessario ottenere nuovi certificati concessori di licenze client dagli attuali client RMS in modo da consentire l'accesso al cluster Extranet per la gestione licenze.

Per ulteriori informazioni , vedere "[Per aggiungere un URL di un cluster Extranet](https://technet.microsoft.com/12c83186-ce9e-4100-bbd1-d87a885331c7)", più avanti in questo argomento.
