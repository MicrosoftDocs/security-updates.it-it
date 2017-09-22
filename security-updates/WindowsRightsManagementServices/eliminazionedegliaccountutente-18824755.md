---
TOCTitle: Eliminazione degli account utente
Title: Eliminazione degli account utente
ms:assetid: 'bf73b141-d4d1-4807-a773-3aaff58b0db6'
ms:contentKeyID: 18824755
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747653(v=WS.10)'
---

Eliminazione degli account utente
=================================

Quando si elimina un account utente da Active Directory, la voce relativa al certificato per account con diritti dell'utente presente nella tabella delle chiavi dell'utente del database di configurazione del cluster di certificazione principale non viene eliminata automaticamente. Per questo motivo, la tabella delle chiavi dell'utente può raggiungere dimensioni molto elevate qualora vengano aggiunte nuove chiavi senza eliminare quelle precedenti.

Per mantenere aggiornato il database di configurazione, è possibile eseguire una stored procedure che consenta di eliminare una chiave utente in base al relativo identificatore di protezione (SID) ogni volta che l'account utente associato viene rimosso da Active Directory. In alternativa, è possibile eseguire periodicamente uno script che consenta di eliminare eventuali chiavi utente dal database di configurazione quando il relativo SID non esiste più in Active Directory. In questo modo, si provoca tuttavia la creazione di un carico di grandi dimensioni sia in SQL Server che in Active Directory.
