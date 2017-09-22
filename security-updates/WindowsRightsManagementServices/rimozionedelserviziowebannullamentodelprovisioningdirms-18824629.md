---
TOCTitle: 'Rimozione del servizio Web (annullamento del provisioning di RMS)'
Title: 'Rimozione del servizio Web (annullamento del provisioning di RMS)'
ms:assetid: '68b4e2b0-b1b7-4b0a-8c1a-82ac27c1f12e'
ms:contentKeyID: 18824629
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747602(v=WS.10)'
---

Rimozione del servizio Web (annullamento del provisioning di RMS)
=================================================================

Dopo aver rimosso le autorizzazioni dal server RMS e aver eliminato tutta la protezione RMS, il servizio Web può essere rimosso con la procedura descritta di seguito:

-   Dalla pagina **Amministrazione globale**, selezionare **Rimuovi RMS da questo sito Web**.

Il passaggio successivo dipende dal tipo di server da rimuovere, anche se in ogni caso sarà RMS ad essere rimosso da IIS.

-   Se il server fa parte di un cluster (e non è l'ultimo server del cluster), non è necessario alcun passaggio aggiuntivo.
-   Se il server è soltanto un server licenze, rimuovere il database dei servizi directory, conservando i database di configurazione e registrazione attività (quelli utilizzati dal server di certificazione che è ancora in servizio)
-   Se il server è il server RMS finale dell'organizzazione, conservare i database di configurazione e registrazione attività, ma rimuovere il punto di connessione al servizio (SCP) in Active Directory.
