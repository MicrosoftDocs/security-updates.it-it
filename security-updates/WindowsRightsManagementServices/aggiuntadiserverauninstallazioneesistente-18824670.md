---
TOCTitle: 'Aggiunta di server a un''installazione esistente'
Title: 'Aggiunta di server a un''installazione esistente'
ms:assetid: '7f3598ff-cd19-4daa-aa65-877f7f95a8ec'
ms:contentKeyID: 18824670
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747648(v=WS.10)'
---

Aggiunta di server a un'installazione esistente
===============================================

È possibile aggiungere server all'installazione di RMS qualora sia necessario per gestire aumenti di richieste o per sostituire server il cui funzionamento debba essere interrotto. In ogni installazione di RMS deve essere presente almeno un server di certificazione principale e possono essere presenti server di certificazione principale aggiuntivi in un cluster. Ogni installazione di RMS può inoltre includere server licenze autonomi o in cluster.

È possibile aggiungere server a un'installazione di RMS tramite uno dei metodi seguenti.

-   Aggiungere uno o più server RMS a un cluster di certificazione principale.
-   Aggiungere un nuovo server licenze autonomo.
-   Aggiungere uno o più server RMS a un cluster licenze.

**Aggiunta di server di certificazione principali**

In molti casi, l'aggiunta di uno o più server RMS a un cluster di certificazione principale rappresenta il metodo migliore per aumentare la disponibilità e la ridondanza della distribuzione. Un cluster di certificazione principale comprende uno o più server di certificazione principale. A differenza dei server licenze, che offrono solo servizi di gestione licenze e di pubblicazione, i server di certificazione principale offrono tutti i servizi di RMS.

Durante l'installazione e il provisioning, è possibile aggiungere un server a un cluster. Quando si esegue questa operazione, il nuovo server RMS viene automaticamente configurato come membro del cluster. Per informazioni dettagliate sull'installazione e il provisioning di un server RMS da aggiungere al cluster di certificazione principale, vedere "[Per installare RMS con Service Pack 1](https://technet.microsoft.com/dab20175-a690-43f8-b943-768d289daa0d)" e "[Per aggiungere un server a un cluster](https://technet.microsoft.com/db635238-5528-4bec-9cc6-8244e2b3d733)", più avanti in questo argomento.

Se si crea un cluster per la prima volta, oltre a eseguire il provisioning, è necessario configurare il software o l'hardware con le impostazioni di clustering e di bilanciamento del carico necessarie. Se è già stato implementato un cluster, è necessario configurare il software o l'hardware di bilanciamento del carico affinché questi possa essere utilizzato con il nuovo membro del cluster.

**Aggiunta di server licenze**

A differenza del server di certificazione principale che offre tutti i servizi di RMS, un server licenze offre solo servizi di gestione licenze e di pubblicazione.

I server licenze sono facoltativi e molto spesso vengono distribuiti per soddisfare necessità specifiche di gestione delle licenze, come nei casi descritti di seguito:

-   Per supportare requisiti di gestione dei diritti specifici di un reparto. Un gruppo all'interno dell'organizzazione potrebbe ad esempio avere requisiti di protezione diversi per quanto riguarda la gestione dei diritti rispetto al resto dell'organizzazione e potrebbe necessitare del controllo totale sull'implementazione delle licenze per il gruppo stesso. Poiché in una struttura può essere presente un solo server di certificazione principale, la configurazione di un altro server di certificazione principale non rappresenta una soluzione adeguata. In tal caso, è possibile configurare un server licenze o un cluster licenze dedicato alle esigenze del gruppo in questione. I criteri per i diritti per questo cluster o server licenze possono essere configurati separatamente.
-   Per supportare la gestione dei diritti per partner aziendali esterni, come parte di una Extranet che richieda una rigida separazione e un controllo delle risorse per determinati partner aziendali. Per ulteriori informazioni, vedere “[Configurazione dell'URL di una Extranet](https://technet.microsoft.com/88fec9ff-c96c-4d20-8856-0485e7507572)”, più avanti in questo argomento.
-   Per ripartire il carico delle attività legate alle licenze del server di certificazione principale. In tal modo, è possibile migliorare le prestazioni nelle organizzazioni in cui è presente un solo server di certificazione principale, piuttosto che un cluster di certificazione principale.

Nella maggior parte dei casi, è consigliabile aggiungere server RMS al cluster di certificazione principale per poter configurare la ridondanza e il bilanciamento del carico in tutti i server distribuiti. Sebbene anche i server licenze possano essere utilizzati per ripartire il carico delle richieste di elaborazione di licenze e di pubblicazione, nei server licenze non è possibile eseguire il bilanciamento del carico con il cluster di certificazione principale. A meno che non sussista l'esigenza specifica di distribuire server licenze separati, è consigliabile bilanciare il carico di tutti i server RMS includendoli come membri nel cluster di certificazione principale.

Per informazioni dettagliate sull'installazione e il provisioning di un server licenze RMS, vedere "[Per installare RMS con Service Pack 1](https://technet.microsoft.com/dab20175-a690-43f8-b943-768d289daa0d)" e "[Per eseguire il provisioning di un server licenze](https://technet.microsoft.com/4d67b898-0ba9-4eef-ab7d-ee0ca55a688e)", più avanti in questo argomento.
