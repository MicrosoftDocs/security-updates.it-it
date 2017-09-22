---
TOCTitle: Chiavi del concessore di licenze client
Title: Chiavi del concessore di licenze client
ms:assetid: '28781125-2692-4ff9-99b1-e09227d72966'
ms:contentKeyID: 18824540
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720221(v=WS.10)'
---

Chiavi del concessore di licenze client
=======================================

Gli autori possono acquisire il certificato concessore di licenze client per pubblicare il contenuto protetto con RMS pur non essendo connessi alla rete abilitata per RMS. Un certificato concessore di licenze client utilizza una coppia di chiavi RSA a 1024 bit.

Al fine di portare a termine le operazioni che seguono, nel client RMS è possibile impiegare la chiave pubblica del certificato concessore di licenze client durante l'emissione di una licenza di pubblicazione:

-   Crittografare la chiave simmetrica.
-   Firmare le licenze di pubblicazione rilasciate localmente mentre l'utente non è connesso alla rete.
