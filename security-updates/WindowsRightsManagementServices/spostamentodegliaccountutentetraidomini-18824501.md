---
TOCTitle: Spostamento degli account utente tra i domini
Title: Spostamento degli account utente tra i domini
ms:assetid: '0010b0ea-07c0-41c9-81f7-5881343d1d55'
ms:contentKeyID: 18824501
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720179(v=WS.10)'
---

Spostamento degli account utente tra i domini
=============================================

Quando si esegue la configurazione e il provisioning di un server di certificazione principale in un'organizzazione, il server viene registrato in Active Directory in una configurazione per struttura come provider di servizi RMS. In un insieme di strutture di Active Directory è consentito un solo cluster di certificazione principale.

In generale, quando si sposta un account utente da un dominio a un altro nella stessa struttura, viene creato un nuovo SID per l'account utente nel nuovo dominio. Quando un utente tenta di acquisire un nuovo certificato per account con diritti dal server, l'utente viene visto come nuovo utente del server a causa del nuovo SID. Tramite il server, vengono generate nuove chiavi per l'utente e viene emesso il nuovo certificato per account con diritti utilizzando l'indirizzo di posta elettronica originale dell'utente. Quando l'utente cercherà di utilizzare il nuovo certificato per account con diritti con una licenza esistente, il SID e le chiavi non corrisponderanno e l'utente dovrà acquisire una nuova licenza. Lo stesso vale nel caso in cui si esegua lo spostamento di un account utente in un dominio di una struttura diversa.
