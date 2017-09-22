---
TOCTitle: 'Modifica dell''account di servizio di RMS'
Title: 'Modifica dell''account di servizio di RMS'
ms:assetid: 'f257d66d-b823-41e4-bcb7-7c90eb295238'
ms:contentKeyID: 18824838
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747736(v=WS.10)'
---

Modifica dell'account di servizio di RMS
========================================

Durante l'installazione, tramite RMS viene creato nel computer locale il gruppo di servizi RMS a cui vengono concesse le autorizzazioni appropriate per tutte le risorse necessarie per il funzionamento di RMS. Quando si esegue il provisioning di RMS in un server, si definisce l'account di servizio di RMS tramite un account di dominio. L'account di servizio di RMS non può essere lo stesso account di dominio utilizzato per l'installazione di RMS. Tale account viene inserito come membro nel gruppo di servizi RMS e riceve le autorizzazioni associate al gruppo. Nel corso delle operazioni di routine, RMS viene eseguito nell'account di servizio di RMS.

L'account di servizio di RMS può essere modificato in qualunque momento. Quando l'account viene modificato, quello specificato in precedenza viene automaticamente rimosso dal gruppo di servizi RMS e il nuovo account viene inserito in tale gruppo come membro.

| ![](images/Cc747736.Important(WS.10).gif)Importante                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Per motivi di sicurezza, è consigliabile creare un account utente speciale da utilizzare esclusivamente come account di servizio di RMS. Inoltre, è preferibile non assegnare a questo account autorizzazioni aggiuntive. |

| ![](images/Cc747736.note(WS.10).gif)Nota                                                              |
|------------------------------------------------------------------------------------------------------------------------------------|
| L'account di servizio di RMS non può essere lo stesso account di dominio utilizzato per l'installazione di RMS con Service Pack 1. |
