---
TOCTitle: Rimozione delle autorizzazioni di RMS
Title: Rimozione delle autorizzazioni di RMS
ms:assetid: 'dbcacce7-434d-48a7-a11d-ef9690d78b44'
ms:contentKeyID: 18824806
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747767(v=WS.10)'
---

Rimozione delle autorizzazioni di RMS
=====================================

Con rimozione delle autorizzazioni si indica l'intero processo di rimozione del server RMS e dei database ad esso associati da un'organizzazione. Questo processo permette di rimuovere RMS dall'infrastruttura senza perdere l'accesso alle informazioni protette con RMS. Di seguito vengono elencate le possibili cause per cui un'organizzazione potrebbe dover rimuovere un server RMS dalla propria infrastruttura:

-   Migrazione di un server di dimostrazione RMS da un ambiente pilota all'ambiente di produzione.
-   Semplificazione della struttura dell'architettura, mediante rimozione e consolidamento dei server licenze nel cluster principale RMS.
-   Fusione di server RMS (ad esempio, a seguito di una fusione o di un acquisto fra società) integrando due infrastrutture RMS in una sola.
-   Decisione di interrompere l'utilizzo di RMS per proteggere i contenuti.

Poiché un server RMS attivo è integrato sia con un server di database che con Active Directory e, naturalmente, lascia un intero insieme di contenuti protetto da una chiave contenuta nel server RMS, la rimozione di RMS dall'organizzazione richiede più passaggi della semplice rimozione del programma dal server. In questa sezione vengono descritti i passaggi in modo che sia possibile rimuovere le autorizzazioni dal server RMS, se necessario.

In questa sezione, vengono trattati gli argomenti seguenti:

-   [Nozioni sul processo di rimozione delle autorizzazioni](https://technet.microsoft.com/57bd9949-9433-437b-93ed-ffb2dff9992e)
-   [Abilitazione del servizio Rimozione autorizzazioni](https://technet.microsoft.com/45226e85-b50d-41cc-aca7-0f603f8509d5)
-   [Impostazione delle autorizzazioni sulla directory virtuale](https://technet.microsoft.com/45112111-9608-45b1-9a86-7b313d0a1579)
-   [Rimozione della protezione RMS dal contenuto](https://technet.microsoft.com/c30361e3-50d2-4474-a87d-d38de502cf9e)
-   [Rimozione del servizio Web (annullamento del provisioning di RMS)](https://technet.microsoft.com/68b4e2b0-b1b7-4b0a-8c1a-82ac27c1f12e)
-   [Rimozione dei file di programma di RMS](https://technet.microsoft.com/d1dc8a8b-f8de-487f-87b4-2174d449f0bc)
-   [Alternative alla rimozione delle autorizzazioni RMS](https://technet.microsoft.com/4d32f35e-997d-4d10-ab66-efe217e853f7)
