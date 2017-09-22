---
TOCTitle: Impostazione delle autorizzazioni nel file del servizio di registrazione secondaria
Title: Impostazione delle autorizzazioni nel file del servizio di registrazione secondaria
ms:assetid: '737bb69b-fe26-4057-9569-e632f7bbf295'
ms:contentKeyID: 18824651
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747627(v=WS.10)'
---

Impostazione delle autorizzazioni nel file del servizio di registrazione secondaria
===================================================================================

Il servizio di registrazione secondaria viene eseguito nel server di certificazione principale e consente di registrare un server licenze durante il processo di provisioning. Per impostazione predefinita, il servizio di registrazione secondaria consente di accedere solo all'account di sistema locale presente nel server di certificazione principale. Per eseguire il provisioning di un server licenze, è necessario accedere al server licenze con tale tipo di account. In alternativa, è necessario che un amministratore locale nel server di certificazione principale modifichi l'elenco DACL nel file del servizio di registrazione secondaria, SubEnrollService.asmx, per concedere l'accesso all'account utente che viene utilizzato per eseguire il provisioning nel server licenze. Il file SubEnrollService.asmx si trova nella directory virtuale Certification nel server di certificazione principale.
