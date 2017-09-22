---
TOCTitle: Fruizione del contenuto protetto con RMS
Title: Fruizione del contenuto protetto con RMS
ms:assetid: '3cf6d64b-1187-433c-bbb2-c68069bc3c30'
ms:contentKeyID: 18824574
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720251(v=WS.10)'
---

Fruizione del contenuto protetto con RMS
========================================

Quando gli utenti utilizzano contenuto protetto, vengono eseguiti due processi in modo trasparente all'utente. Per prima cosa, nel momento in cui l'utente apre il documento l'applicazione abilitata per RMS richiede una licenza d'uso. Quindi, l'applicazione abilitata per RMS esamina la licenza d'uso per stabilire se è necessario un elenco di revoche e verifica se uno dei certificati presenti nella catena di trust o del certificato per account con diritti è stato revocato. Una volta completate le due elaborazioni, viene eseguito il rendering del contenuto protetto con RMS da parte dell'applicazione abilitata per RMS, a condizione che diritti e revoche lo consentano.

Se è necessario un elenco di revoche, l'applicazione cercherà una copia locale di tale elenco che non sia scaduta. In caso di necessità, l'applicazione recupererà una copia aggiornata dell'elenco di revoche. L'applicazione applicherà quindi tutte le condizioni di revoca rilevanti nel contesto corrente.

Se non esistono condizioni di revoca che impediscono l'accesso al contenuto, l'applicazione visualizzerà il contenuto e l'utente potrà esercitare i diritti che gli sono stati assegnati.

È possibile configurare RMS in modo da elaborare le richieste di licenze d'uso ricevute dagli utenti esterni autorizzati. In questo modo gli utenti potranno condividere contenuto protetto attraverso Internet.

In questa sezione vengono trattati gli argomenti seguenti:

-   [Acquisizione della licenza d'uso](https://technet.microsoft.com/0b6cde34-418a-4dee-9d27-b65b93b535ac)
-   [Licenze d'uso e utenti esterni](https://technet.microsoft.com/02db9bda-180e-438f-863d-26252083a471)
