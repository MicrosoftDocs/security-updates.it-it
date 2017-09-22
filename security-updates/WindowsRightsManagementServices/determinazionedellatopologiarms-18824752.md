---
TOCTitle: Determinazione della topologia RMS
Title: Determinazione della topologia RMS
ms:assetid: 'bf516f7d-b3a1-4e7f-971f-bfab1db41812'
ms:contentKeyID: 18824752
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747651(v=WS.10)'
---

Determinazione della topologia RMS
==================================

Nella topologia di base RMS, il cluster o il server di certificazione principale RMS di ogni insieme di strutture di Active Directory forniscono tutti i servizi RMS per un'organizzazione. Questa topologia RMS funziona bene sia in grandi che in piccole organizzazioni. In una topologia RMS distribuita, uno o più server licenze (noti anche come server licenze dipartimentali) possono fornire alcuni o tutti i servizi di gestione licenze a utenti e gruppi specifici dell'organizzazione. Benché il server di certificazione principale (o il cluster) continui a fornire la certificazione di account e di servizi proxy di attivazione per l'intera organizzazione, la topologia RMS distribuita è progettata per organizzazioni che hanno la necessità di licenze molto specifiche e che devono mantenere il controllo di RMS in un segmento della loro organizzazione.

Sebbene vi siano soltanto due topologie di base per RMS, i componenti delle topologie possono essere molto diversi. Per definire i componenti appropriati per l'organizzazione e creare la topologia giusta per la distribuzione di RMS, è necessario:

-   Valutare le esigenze e gli obiettivi dell'organizzazione.
-   Definire la modalità di utilizzo della gestione dei diritti.
-   Analizzare gli schemi di traffico e i carichi previsti per implementare un livello di servizio appropriato.

La definizione della topologia e la fase decisionale richieste per implementare la progettazione sono un processo iterativo che continuerà per tutta la pianificazione della distribuzione RMS.

In questa sezione vengono trattati gli argomenti seguenti:

-   [Identificazione dei componenti di base](https://technet.microsoft.com/c9ec225b-0e51-42f5-aff6-0aecb62e3b27)
-   [Definizione degli obiettivi della topologia](https://technet.microsoft.com/8275a04d-3e5b-40b0-be9d-2f31b7aeca6b)
-   [Definizione dell'ambito dell'implementazione di RMS](https://technet.microsoft.com/4b5fe1be-643e-47c4-bf9b-50d1e97108fb)
-   [Valutazione dei requisiti di scalabilità](https://technet.microsoft.com/89f0138c-946d-47d7-a286-041d4d9606a8)
-   [Fornitura della ridondanza e del bilanciamento del carico di lavoro](https://technet.microsoft.com/162d547c-78a7-4848-b43e-58e481832af2)
-   [Valutazione dei requisiti per la migrazione](https://technet.microsoft.com/cec07f45-dc52-4004-860b-5cc33e5fc209)
-   [Pianificazione dell'infrastruttura di server database](https://technet.microsoft.com/b12354bd-3143-4d1f-b5aa-450c4550653c)
-   [Pianificazione della distribuzione in insiemi di strutture](https://technet.microsoft.com/2dfb40b7-95b1-4362-b32e-72867544b705)
-   [Pianificazione degli utenti RMS esterni](https://technet.microsoft.com/107e1338-4dcf-4ed5-a49d-e875cc883db1)
-   [Pianificazione di una topologia RMS di base](https://technet.microsoft.com/fec3201e-201f-4faf-910e-fa44132af83d)
-   [Pianificazione di una topologia RMS distribuita](https://technet.microsoft.com/8773a1e0-6ac3-41f5-9866-5890cef08d04)
