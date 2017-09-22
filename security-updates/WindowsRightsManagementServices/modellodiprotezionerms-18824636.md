---
TOCTitle: Modello di protezione RMS
Title: Modello di protezione RMS
ms:assetid: '665db831-366d-4dca-9bb3-cc2912481fe1'
ms:contentKeyID: 18824636
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747598(v=WS.10)'
---

Modello di protezione RMS
=========================

Durante il funzionamento, RMS ottiene l'accesso a varie risorse, tra cui il server database, Active Directory, la coda dei messaggi e il disco rigido locale. Inoltre, il programma di installazione di RMS crea ed espone alcune risorse necessarie per il funzionamento, quali ad esempio voci SOAP, pagine Web, code di messaggi di registrazione attività e così via. Il programma di installazione di RMS configura i DACL per le risorse create ed esposte, oltre a configurare l'autenticazione IIS per ciascuna risorsa.

Questa sezione contiene informazioni su come RMS provvede a configurare la protezione sulle risorse utilizzate e su come ottiene l'accesso alle risorse durante le varie fasi di funzionamento, l'installazione, il provisioning e il funzionamento normale.

In questa sezione, vengono trattati gli argomenti seguenti:

-   [Gruppi di protezione RMS](https://technet.microsoft.com/25749a83-8c12-48ec-96ad-296d31fd55d4)
-   [Modalità di protezione per RMS](https://technet.microsoft.com/d7792293-5bb2-4232-9d48-e81e87ab6219)
-   [Protezione durante la configurazione di RMS](https://technet.microsoft.com/0a3d40b2-f27e-4e63-baff-a9c8433f5f91)
-   [Protezione durante il provisioning](https://technet.microsoft.com/9f1282c5-5642-4870-a9a4-c3a485f8ff76)
-   [Protezione durante il normale funzionamento di RMS](https://technet.microsoft.com/98f3d584-6320-4aa1-9959-7133cfdb6df7)
