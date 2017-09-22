---
TOCTitle: Rilevamento del servizio di pubblicazione
Title: Rilevamento del servizio di pubblicazione
ms:assetid: '5d500841-a202-4865-b5d2-d0775d4e1bbc'
ms:contentKeyID: 18824616
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747580(v=WS.10)'
---

Rilevamento del servizio di pubblicazione
=========================================

Il servizio di pubblicazione RMS emette le licenze di pubblicazione impiegate per proteggere il contenuto. Questo servizio rilascia inoltre certificati concessori di licenze client, che consentono agli utenti di pubblicare contenuto mentre non sono connessi alla rete aziendale.

Il servizio di pubblicazione è disponibile nel cluster di certificazione principale o nei server licenze. Un'applicazione abilitata per RMS richiede il servizio quando un autore pubblica contenuto protetto con RMS. Per inviare una richiesta di servizio di pubblicazione, per prima cosa l'applicazione richiama da Active Directory l'URL della directory virtuale Licensing sul server, in cui è ubicato il servizio di pubblicazione. Fatto ciò, vi aggiunge il percorso del servizio di pubblicazione.

Ad esempio, l'URL della directory virtuale Licensing di un server è memorizzato in Active Directory nel seguente formato:

http://*nome\_server*/\_wmcs/Licensing

Quando un server richiede una licenza di pubblicazione, aggiunge all'URL il nome del file del servizio di pubblicazione come indicato di seguito:

http://*nome\_server*/\_wmcs/Licensing/Publish.asmx

Qualora a RMS risulti che il certificato per account con diritti sia basato sull'autenticazione utente di Windows, la posizione del servizio di pubblicazione viene determinata mediante l'insieme di strutture di Active Directory. Questa considerazione è valida sia per gli utenti interni che per quelli esterni che si connettono alla rete aziendale tramite una rete privata virtuale (VPN, Virtual Private Network).

Qualora a RMS risulti che il certificato per account con diritti sia basato su Microsoft® .NET Passport, la posizione del servizio di pubblicazione sarà nell'account .NET Passport specificato nel contenuto protetto con RMS.

| ![](images/Cc747580.note(WS.10).gif)Nota                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Qualora SSL sia stato abilitato sul server RMS, gli URL mostrati appariranno con l'indicazione dell'utilizzo del protocollo di connessione https://. |
