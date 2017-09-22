---
TOCTitle: Ritiro dei modelli di criteri per i diritti
Title: Ritiro dei modelli di criteri per i diritti
ms:assetid: '32bf98c7-edda-4507-a4b8-4c11bddd6e60'
ms:contentKeyID: 18824557
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720239(v=WS.10)'
---

Ritiro dei modelli di criteri per i diritti
===========================================

Per interrompere un modello di criteri per i diritti, è necessario eliminarlo. Questa procedura è descritta in “[Per eliminare un modello di criteri per i diritti](https://technet.microsoft.com/9c9a1496-cf55-4c65-a4c6-9fe245edce00)”, più avanti in questo argomento. In genere, non è tuttavia consigliabile eliminare i modelli di criteri per i diritti. Se si desidera interrompere un modello di criteri per i diritti, è necessario rimuoverne tutte le copie presenti nei computer degli utenti. Questa operazione è necessaria perché quando un autore utilizza un modello di criteri per i diritti per pubblicare un contenuto, viene inviata una richiesta al server RMS. Tramite RMS, viene utilizzata una copia del modello di criteri per i diritti memorizzato nel database per rispondere alla richiesta. Se il modello non esiste, la richiesta non viene soddisfatta.

| ![](images/Cc720239.note(WS.10).gif)Nota                                                                     |
|-------------------------------------------------------------------------------------------------------------------------------------------|
| Un modello di criteri per i diritti può essere interrotto creando uno script che consenta di rimuoverlo da tutti i computer degli utenti. |
