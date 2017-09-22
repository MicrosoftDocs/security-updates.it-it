---
TOCTitle: Rilevamento del Servizio certificazione account
Title: Rilevamento del Servizio certificazione account
ms:assetid: '293a2f91-4712-45ec-8b74-7533f4144cbd'
ms:contentKeyID: 18824543
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720224(v=WS.10)'
---

Rilevamento del Servizio certificazione account
===============================================

Mediante il servizio Certificazione account RMS, gli utenti possono ottenere i certificati per account con diritti. Ciascun certificato per account con diritti (RAC, Rights Account Certificate) è valido solo su uno specifico computer o dispositivo e richiede che l'utente che richiede il certificato disponga di un certificato computer valido.

Il servizio di certificazione degli account viene eseguito solo nel server o nel cluster di certificazione principale. Per inoltrare una richiesta di certificazione account, per prima cosa il client richiama da Active Directory l'indirizzo URL della directory virtuale Certification del server di certificazione principale, in cui si trova il servizio certificazione account. Fatto ciò, vi aggiunge il percorso del servizio certificazione account.

Ad esempio, l'URL certificazione del server di certificazione principale è memorizzato in Active Directory nella forma indicata di seguito:

http://*nome\_server*/\_wmcs/Certification

Quando richiede un certificato per account con diritti, il client aggiunge all'URL il nome del file del servizio certificazione account, come indicato di seguito:

http://*nome\_server*/\_wmcs/Certification/Certification.asmx

| ![](images/Cc720224.note(WS.10).gif)Nota                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Qualora SSL sia stato abilitato sul server RMS, gli URL mostrati appariranno con l'indicazione dell'utilizzo del protocollo di connessione https://. |
