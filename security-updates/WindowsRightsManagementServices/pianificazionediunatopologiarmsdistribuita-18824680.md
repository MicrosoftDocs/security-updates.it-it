---
TOCTitle: Pianificazione di una topologia RMS distribuita
Title: Pianificazione di una topologia RMS distribuita
ms:assetid: '8773a1e0-6ac3-41f5-9866-5890cef08d04'
ms:contentKeyID: 18824680
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747657(v=WS.10)'
---

Pianificazione di una topologia RMS distribuita
===============================================

In alcune circostanze, può essere necessario distribuire uno o più server licenze che non sono componenti del cluster di certificazione principale. Di solito, questo ha lo scopo di supportare reparti che richiedono un controllo diretto sull'emissione di licenze di pubblicazione e d'uso, come un ufficio legale con requisiti di protezione che necessitano di controllo a livello dipartimentale. Il cluster di certificazione principale offre il servizio di certificazione account per i server licenze. La combinazione di un cluster di certificazione principale e di una o più installazioni di server licenze viene detta topologia distribuita.

Si noti che, come il server di certificazione principale, anche i server licenze possono essere distribuiti in un cluster. Inoltre, analogamente al cluster di certificazione principale, il cluster licenze utilizzano un proprio servizio di bilanciamento del carico. In ogni server licenze o cluster licenze viene utilizzata un'istanza distinta di SQL Server per rendere disponibili i database di configurazione e di registrazione attività per il server o il cluster specifico.

Benché sia possibile configurare l'installazione RMS per eseguire solo i servizi di certificazione dall'installazione principale, oltre che gestire l'intero servizio licenze da uno o più server o cluster licenze, questa non è la configurazione tipica. Il numero di server fisici disponibili nel cluster di certificazione principale viene solitamente aumentato per soddisfare le esigenze di prestazioni e di ridondanza, invece di distribuire server licenze distinti, a meno che non sia necessario supporto a livello di reparto per la gestione delle licenze. Tale distribuzione viene illustrata nel diagramma riportato di seguito.

![](images/Cc747657.01fa5a85-5711-41aa-932a-124049d34186(WS.10).gif)

La costruzione di una topologia distribuita può aumentare i costi amministrativi per l'organizzazione, poiché una topologia distribuita è intrinsecamente più complessa. Se l'organizzazione ha più cluster licenze e più insiemi di strutture, può essere necessario sovrascrivere il registro di sistema dei computer client RMS per assicurarsi che inviino le richieste di licenza al server RMS corretto. È inoltre possibile che si verifichino problemi di trust tra i domini. Questo richiede di configurare ulteriormente i domini per permettere l'utilizzo del contenuto protetto con RMS.

Punti di connessione del servizio in una topologia distribuita
--------------------------------------------------------------

Quando si esegue il provisioning un server RMS, l'URL di un cluster viene aggiunto all'insieme di strutture Active Directory in un punto di connessione servizio (SCP). Esiste un SCP per il cluster di certificazione principale e per ogni cluster licenze di cui si è eseguito il provisioning nell'insieme di strutture. L'SCP del cluster di certificazione principale deve essere registrato prima di eseguire il provisioning di un cluster licenze. Quando si esegue il provisioning del cluster licenze, il processo di registrazione subordinata utilizza quell'URL per trovare il cluster di certificazione principale sulla rete e ottenere un certificato concessore di licenze server.

Se si distribuisce un cluster di certificazione principale piuttosto che un unico server di certificazione principale, ogni server del cluster deve poter essere indirizzato in modo virtuale a un URL condiviso.

Esistono molte implementazioni dell'indirizzamento virtuale, come il round-robin DNS, il servizio Bilanciamento carico di rete, soluzioni hardware e così via. Gli indirizzi virtuali consentono il bilanciamento del carico tra i server e rimuovono la dipendenza da un server specifico per la gestione di licenze e la pubblicazione.

RMS utilizza l'URL condiviso come URL di acquisizione licenze, oltre che come valore pubblicato che i computer degli utenti finali utilizzano quando cercano il proprio cluster RMS in Active Directory o nel registro di sistema. Nessun computer di utenti finali necessita di accesso diretto a un server presente in un cluster.
