---
TOCTitle: 'Acquisizione della licenza d''uso'
Title: 'Acquisizione della licenza d''uso'
ms:assetid: '0b6cde34-418a-4dee-9d27-b65b93b535ac'
ms:contentKeyID: 18824518
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720194(v=WS.10)'
---

Acquisizione della licenza d'uso
================================

Per utilizzare il contenuto protetto con RMS, l'utente deve acquisire una licenza d'uso dal servizio di gestione licenze di RMS. Nella figura riportata di seguito viene illustrato il processo di richiesta e ricezione di una licenza d'uso.

![](images/Cc720194.37b8d28c-9749-4e81-bc6a-22692fefb8b6(WS.10).gif)

Il processo di acquisizione di una licenza d'uso si compone delle operazioni descritte di seguito:

1.  Attraverso un normale canale di distribuzione, l'utente riceve un file protetto che può essere aperto utilizzando un'applicazione abilitata per RMS. Se non dispone di un certificato per account con diritti sul computer o dispositivo impiegato, l'utente deve acquisirne uno.
2.  L'applicazione abilitata per RMS invia una richiesta di licenza d'uso al server da cui è stata emessa la licenza di pubblicazione per il contenuto protetto. Nella richiesta viene incluso il certificato per account con diritti dell'utente (che contiene la chiave pubblica dell'utente) e la licenza di pubblicazione (che contiene la chiave simmetrica del contenuto).
    Una licenza di pubblicazione rilasciata da un certificato concessore di licenze client include l'URL del server che ha rilasciato il certificato. In tale esempio la richiesta di licenza d'uso viene inoltrata al server che ha rilasciato il certificato concessore di licenze client e non al computer che ha rilasciato la licenza di pubblicazione.
3.  Il server licenze verifica che l'utente sia autorizzato e che sia indicato nella licenza di pubblicazione e quindi crea una licenza d'uso. Il server convalida il certificato per account dell'utente e quindi determina le autorizzazioni assegnate all'utente direttamente o tramite l'appartenenza a un gruppo.
    Il server decrittografa la chiave simmetrica del contenuto utilizzando la chiave privata del server, la crittografa nuovamente utilizzando la chiave pubblica del destinatario e quindi la aggiunge alla licenza d'uso. Questo passaggio serve a garantire che la chiave del contenuto e il contenuto protetto possano essere decrittografati solo dall'utente previsto.
    Il server aggiunge tutte le condizioni rilevanti alla licenza d'uso, ad esempio un'esclusione basata su un'applicazione o sulla versione di Windows. Queste condizioni vengono applicate dal client quando la licenza d'uso viene associata al contenuto protetto con RMS.
4.  Al termine della convalida, il server licenze restituisce la licenza d'uso al computer client dell'utente.
