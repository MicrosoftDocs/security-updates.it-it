---
TOCTitle: Menutenzione del database dei servizi di directory
Title: Menutenzione del database dei servizi di directory
ms:assetid: '911a62f2-c1d6-4091-99b0-b53211be27a7'
ms:contentKeyID: 18824698
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747680(v=WS.10)'
---

Menutenzione del database dei servizi di directory
==================================================

RMS contiene un database di servizi di directory che ospita il server di database, contenente le informazioni sugli utenti, gli identificatori (come gli indirizzi di posta elettronica), gli ID di protezione (SID), l'appartenenza a un gruppo e gli identificatori alternativi. Queste informazioni sono ottenute da query LDAP effettuate dal servizio licenze RMS nel catalogo globale di Active Directory e quindi memorizzate nella cache locale del database per migliorare il tempo di risposta del server quando gli utenti richiedono le licenze d'uso.

Poiché i dati memorizzati in questo database sono inseriti ed eliminati spesso, è incline alla frammentazione. Si dovrebbe eseguire periodicamente (quotidianamente o settimanalmente) una riorganizzazione del database basata sugli indici di tutte le tabelle del database DRMS\_DirectoryServices. Questo ricostruirà gli indici in modo che i dati non siano più frammentati. Senza l'intervento dell'amministratore, i dati frammentati possono generare prestazioni scarse ed errori sul server.

Se si utilizza SQL Server come server di database, la riorganizzazione del database può essere eseguita con Ottimizzazione di Windows o eseguendo uno script personalizzato con Agente SQL Server.

Se, quando si reindicizza il database, il registro delle transazioni cresce fino a dimensioni inaccettabili, si può ridurre la crescita passando dalla modalità di recupero completo alla modalità Bulk-Logged prima di eseguire la reindicizzazione.
