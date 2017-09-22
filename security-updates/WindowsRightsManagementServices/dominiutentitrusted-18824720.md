---
TOCTitle: Domini utenti trusted
Title: Domini utenti trusted
ms:assetid: 'a09b883f-f455-4c46-a4fd-d37b689e1d24'
ms:contentKeyID: 18824720
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747618(v=WS.10)'
---

Domini utenti trusted
=====================

Per impostazione predefinita, RMS non emette licenze d'uso per gli utenti i cui certificati per account con diritti sono stati emessi da un dominio utente differente. Il dominio utente è un'installazione di RMS composta da un cluster di certificazione principale, da server o cluster licenze facoltativi e dai database associati.

RMS può essere configurato in modo da elaborare questo tipo di richiesta importando il certificato concessore di licenze server o un altro dominio utente, quindi aggiungendolo all'elenco dei domini utente trusted. Quando si esegue questa operazione, gli utenti i cui certificati per account sono stati rilasciati dal dominio utenti trusted possono inviare richieste di licenze d'uso alla propria installazione. Queste licenze d'uso verranno elaborate come se fossero richieste da utenti interni.

| ![](images/Cc747618.note(WS.10).gif)Nota                                                                                                    |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Il cluster di certificazione principale appare automaticamente nell'elenco dei domini utente trusted per tutti i server RMS che fanno parte di una stessa installazione. |

È possibile consentire a utenti di domini utenti diversi di condividere contenuto protetto. Questo scenario è descritto negli esempi seguenti:

-   La propria organizzazione lavora a stretto contatto con un'altra organizzazione per la stesura di documenti riservati che si desidera condividere e proteggere. Anche l'altra organizzazione esegue RMS. Le due organizzazioni possono reciprocamente aggiungere le proprie installazioni di RMS all'elenco dei domini utente trusted, in modo che gli utenti di entrambe possano lavorare insieme su contenuto protetto, scambiando il materiale attraverso Internet o un'Extranet.
-   È possibile avere una sola installazione di RMS in ogni insieme di strutture di Active Directory. La propria organizzazione ha distribuito più insiemi di strutture di Active Directory, ognuno dei quali esegue RMS. Gli utenti desiderano condividere contenuto protetto con altri utenti, indipendentemente dall'insieme di strutture in cui risiedono. Per poterlo fare, è possibile aggiungere l'installazione di RMS degli altri insiemi di strutture all'elenco dei domini utente trusted presenti in ciascun insieme di strutture.
-   Gli utenti della propria organizzazione collaborano insieme agli utenti di un'altra organizzano alla redazione di documenti riservati che desiderano proteggere. L'altra organizzazione non esegue RMS. Gli utenti che fanno parte di altre organizzazioni possono disporre di account .NET Passport; inoltre, .NET Passport può essere aggiunto all'elenco dei domini utente trusted dell'installazione di RMS. Gli utenti di entrambe le aziende potranno ora lavorare su contenuto protetto e scambiarlo attraverso Internet.

Per ulteriori informazioni e istruzioni dettagliate sui domini utente trusted, vedere "Aggiunta e rimozione di domini utenti trusted" e "Definire i criteri di trust" in "Gestione di un server RMS" in questa documentazione.
