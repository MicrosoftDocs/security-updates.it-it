---
TOCTitle: Domini di pubblicazione trusted
Title: Domini di pubblicazione trusted
ms:assetid: 'bca1c33a-d3ef-42b5-adbe-6e104979a71f'
ms:contentKeyID: 18824754
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747738(v=WS.10)'
---

Domini di pubblicazione trusted
===============================

Per impostazione predefinita, i server RMS non emettono licenze d'uso in base a licenze di pubblicazione emesse da server RMS appartenenti a cluster differenti. Esistono, tuttavia, situazioni in cui uno stesso server o cluster non può rilasciare sia licenze di pubblicazione che licenze d'uso per un particolare contenuto protetto. Ad esempio, ciò può accadere quando un determinato cluster RMS viene ritirato per essere sostituito da un altro, come accade durante la fusione di due società. In questa situazione, un cluster RMS deve avere la possibilità di emettere licenze d'uso in base alle licenze di pubblicazione create da un differente cluster RMS.

È possibile configurare un cluster RMS affinché consideri trusted le licenze di pubblicazione emesse da un differente cluster RMS, emettendo licenze d'uso in base a tali licenze di pubblicazione mediante l'implementazione di un dominio di pubblicazione trusted. A tale scopo, importare il certificato concessore di licenze server e la chiave privata dall'altro server e quindi aggiungerlo all'elenco di domini di pubblicazione trusted. Le chiavi private importate vengono utilizzate solo per la decrittografia di licenze di pubblicazione firmate e non per la firma di nuove licenze.

Per ulteriori informazioni e istruzioni dettagliate sui domini utente trusted, vedere "Aggiunta e rimozione di domini di pubblicazione trusted" e "Definire i criteri di trust" in "Gestione di un server RMS" in questa documentazione.
