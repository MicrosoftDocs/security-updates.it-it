---
TOCTitle: Come stimare la crescita dei database
Title: Come stimare la crescita dei database
ms:assetid: '87652cc2-b886-4797-8d40-356669768089'
ms:contentKeyID: 18824676
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747585(v=WS.10)'
---

Come stimare la crescita dei database
=====================================

Quando si valuta la quantità di memoria richiesta per i database RMS, occorre pianificare per il database di configurazione RMS una capacità minima di 10 megabyte (MB) e aggiungere 1 MB ogni 500 utenti. Il database di registrazione attività può trovarsi su un server di database diverso dal database di configurazione.

Se si utilizza la funzione di registrazione attività di RMS, il database di registrazione deve supportare una crescita di circa 1 MB per utente durante la fase iniziale di certificazione degli utenti, quando si verifica un grande numero di attività da registrare. Ad esempio, se la distribuzione supporta 1000 utenti, il database di registrazione aumenterà fino a 1 gigabyte (GB) quando ognuno degli utenti sarà stato attivato e certificato dal server di certificazione RMS. Nelle operazioni di routine, il database di registrazione può crescere alla velocità di 200 kilobyte (KB) al giorno per ogni utente (se si esegue un rollout in più fasi, stimare 1 MB aggiuntivo per ogni utente aggiunto al sistema).
