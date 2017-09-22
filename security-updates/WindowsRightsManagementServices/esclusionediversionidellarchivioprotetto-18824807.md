---
TOCTitle: 'Esclusione di versioni dell''archivio protetto'
Title: 'Esclusione di versioni dell''archivio protetto'
ms:assetid: 'e287f026-aab2-43ab-93bc-48087da82f36'
ms:contentKeyID: 18824807
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747700(v=WS.10)'
---

Esclusione di versioni dell'archivio protetto
=============================================

Per assicurarsi che nei client sia in uso una versione minima del software client RMS, utilizzare la versione dell'archivio protetto associata al client per escludere le versioni precedenti del software client RMS. Quando si attiva questa funzionalità, è necessario specificare la versione minima più recente dell'archivio protetto firmata dal servizio di attivazione Microsoft. Attivare quindi l'esclusione dell'archivio protetto nel sito Web Amministrazione di ogni cluster in cui si desidera che venga applicata. Tutte le richieste di certificazione e di licenze vengono verificate per controllare che l'archivio protetto soddisfi i requisiti di versione minima.

Se è stata attivata l'esclusione in base alla versione dell'archivio protetto, i client in cui sono presenti versioni del software dell'archivio protetto precedenti alla versione specificata non potranno acquisire certificati per account con diritti o licenze d'uso, poiché le richieste verranno rifiutate. È necessario installare in questi client una nuova versione del software RMS per acquisire un nuovo archivio protetto in cui sia in uso la versione attuale del software.

Il client RMS per Service Pack 1 (SP1) utilizza una versione di archivio protetto superiore o uguale a 5.0.0.0. Impostando l'esclusione dell'archivio protetto alla versione minima, è possibile imporre a tutti i client RMS dell'organizzazione l'aggiornamento al client RMS per SP1 per poter utilizzare il contenuto protetto con RMS.

Se per un utente con un archivio protetto escluso sono state emesse in precedenza licenze per il contenuto, l'utente potrà continuare a utilizzare tale contenuto senza acquisire un nuovo archivio protetto.
