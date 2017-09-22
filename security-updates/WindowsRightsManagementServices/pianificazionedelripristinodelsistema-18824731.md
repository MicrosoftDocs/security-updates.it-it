---
TOCTitle: Pianificazione del ripristino del sistema
Title: Pianificazione del ripristino del sistema
ms:assetid: 'a7779ffd-7a94-4e13-b846-0ffd00608e02'
ms:contentKeyID: 18824731
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747718(v=WS.10)'
---

Pianificazione del ripristino del sistema
=========================================

Gli errori di sistema si verificano per molte cause accidentali: errori nell'hardware, inondazioni, sovracorrente, errori nel software, ecc. Una distribuzione efficace deve includere i piani per recuperare velocemente il sistema in caso di errori. In un sistema RMS, il requisito principale per proteggere le funzionalità RMS è eseguire regolarmente il backup della chiave privata del server e dei database RMS, soprattutto del database di configurazione. Questa operazione consente di mantenere i modelli di criteri per i diritti, le chiavi e altri dati necessari per consentire l'accesso a licenze precedenti e contenuto pubblicato. Se l'installazione RMS esistente diviene non disponibile, è possibile installare RMS su altri server e quindi eseguire il provisioning di RMS specificando il database di configurazione di backup come database da utilizzare. La nuova installazione di backup sarà identica all'installazione precedente nel momento in cui è stato eseguito l'ultimo backup.

In questa sezione, vengono trattati gli argomenti seguenti:

-   [Preperazione del ripristino del sistema](https://technet.microsoft.com/885c047f-1e3b-4bf5-8248-3a4505759cbb)
-   [Backup di sistema per RMS](https://technet.microsoft.com/c29894da-ee00-428c-8d48-80d8e5a83678)
-   [Backup e ripristino del sistema RMS](https://technet.microsoft.com/c11f3ac1-e512-402b-bf13-9ff21f5fe745)
-   [Backup e ripristino dei modelli di criteri per i diritti](https://technet.microsoft.com/a6ed3328-4128-45e8-9236-3de484b460de)
