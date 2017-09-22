---
TOCTitle: Pianificazione di una topologia RMS di base
Title: Pianificazione di una topologia RMS di base
ms:assetid: 'fec3201e-201f-4faf-910e-fa44132af83d'
ms:contentKeyID: 18824841
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747755(v=WS.10)'
---

Pianificazione di una topologia RMS di base
===========================================

La topologia RMS di base consiste in uno o più server fisici che fungono da cluster di certificazione principale. Tale cluster consente la certificazione, la gestione di licenze e la pubblicazione nell'organizzazione. Ad eccezione delle distribuzioni di dimensioni molto contenute, più server fisici vengono solitamente configurati come cluster con un unico URL. Il cluster viene creato eseguendo il provisioning del primo server, in modo da creare il server di certificazione principale, quindi aggiungendo server al cluster finché non si è raggiunto il numero di server di certificazione principali necessari per supportare l'attività pianificata. Nella figura riportata di seguito viene illustrata tale topologia.

![](images/Cc747755.a3332719-4d25-4694-a89a-7c31fd97ca3b(WS.10).gif)

I server aggiunti a un cluster condividono gli stessi database di configurazione e di registrazione attività, ovvero dei database SQL Server. È possibile installare SQL Server sul server di certificazione principale o su un server distinto.

Il bilanciamento del carico viene configurato su tutti i server disponibili nel cluster di certificazione principale. Tutte le richieste di certificati e licenze vengono passate al cluster di certificazione principale tramite l'URL comune specificato durante la configurazione del primo server del cluster.

Se verrà supportato un numero piccolo di client, sarà possibile configurare RMS su un unico server con un database locale. Tutte le operazioni di certificazione e di gestione licenze nell'organizzazione verranno eseguite dal server. In questa configurazione è disponibile un singolo punto di errore, quindi è consigliabile eseguire backup regolari della configurazione.
