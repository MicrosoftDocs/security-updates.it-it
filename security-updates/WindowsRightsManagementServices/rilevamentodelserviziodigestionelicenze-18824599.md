---
TOCTitle: Rilevamento del servizio di gestione licenze
Title: Rilevamento del servizio di gestione licenze
ms:assetid: '4eabbb76-b359-443a-b737-098c5659e9c6'
ms:contentKeyID: 18824599
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720269(v=WS.10)'
---

Rilevamento del servizio di gestione licenze
============================================

Il servizio di gestione licenze RMS emette le licenze d'uso che consentono agli utenti autenticati di utilizzare il contenuto protetto.

Questo servizio viene eseguito nei server o nei cluster di certificazione principale e licenze. Per inoltrare una richiesta di licenza d'uso, per prima cosa il client deve richiamare da Active Directory l'URL della directory virtuale Licensing del cluster di certificazione principale, in cui è ubicato il servizio di gestione licenze. Quindi, vi aggiunge il percorso del servizio di gestione licenze.

Ad esempio, l'URL della directory virtuale Licensing del cluster di certificazione principale è memorizzato in Active Directory nel formato seguente:

http://*nome\_server*/\_wmcs/Licensing

Quando un server richiede una licenza d'uso, aggiunge all'URL il nome del file del servizio di gestione delle licenze come indicato di seguito:

http://*nome\_server*/\_wmcs/Licensing/License.asmx

La posizione del servizio può essere su un server RMS o nell'account .NET Passport che emette la licenza di pubblicazione; l'URL è incluso nella licenza di pubblicazione.

| ![](images/Cc720269.note(WS.10).gif)Nota                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Qualora SSL sia stato abilitato sul server RMS, gli URL mostrati appariranno con l'indicazione dell'utilizzo del protocollo di connessione https://. |
