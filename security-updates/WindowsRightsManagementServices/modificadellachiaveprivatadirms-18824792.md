---
TOCTitle: Modifica della chiave privata di RMS
Title: Modifica della chiave privata di RMS
ms:assetid: 'da32137e-394a-42b2-9552-ba20f4547c23'
ms:contentKeyID: 18824792
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747765(v=WS.10)'
---

Modifica della chiave privata di RMS
====================================

Durante il provisioning, RMS crea una chiave privata di RMS per il server. Tale chiave è crittografata e memorizzata nel database di configurazione. È consigliabile eseguire il backup e memorizzare la chiave privata in un luogo protetto. Inoltre, si consiglia l'utilizzo di un modulo di protezione hardware per la protezione della chiave privata di RMS, poiché questa viene utilizzata nello schema di crittografia per tutti i contenuti protetti dal server RMS. Se, per qualche ragione, la chiave privata di RMS viene compromessa, è necessario rimuovere RMS dal server ed eseguire nuovamente il provisioning per ottenere una nuova chiave privata.

Se il server era stato utilizzato per proteggere il contenuto, è necessario avvisare tutti i proprietari e ripubblicare il contenuto utilizzando il server RMS con la nuova chiave privata. È inoltre necessario distruggere tutte le copie del contenuto protetto con la chiave privata compromessa, poiché queste non possono più essere considerate adeguatamente protette.

| ![](images/Cc747765.Important(WS.10).gif)Importante                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Indipendentemente dal fatto che il server sia stato registrato con il Servizio di Enrollment Microsoft, il server deve ripetere il processo di provisioning per ottenere una nuova chiave privata. Se si prova semplicemente la registrazione a un server RMS, verrà utilizzata la chiave privata di RMS compromessa. |
