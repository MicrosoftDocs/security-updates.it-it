---
TOCTitle: 'Licenze d''uso e utenti esterni'
Title: 'Licenze d''uso e utenti esterni'
ms:assetid: '02db9bda-180e-438f-863d-26252083a471'
ms:contentKeyID: 18824493
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720176(v=WS.10)'
---

Licenze d'uso e utenti esterni
==============================

Con RMS, gli autori possono condividere il contenuto protetto con utenti esterni autorizzati attraverso Internet. Mediante RMS, è possibile offrire la stessa protezione per il contenuto pubblicato a utenti interni ed esterni, poiché i diritti associati al contenuto devono essere concessi in licenza da un server RMS. In questo modo le organizzazioni possono condividere e collaborare su documenti riservati, ad esempio contratti, attraverso Internet.

Normalmente, l'utente esterno ottiene l'accesso a RMS attraverso Internet. Gli utenti esterni che possono accedere direttamente alla rete interna, ad esempio tramite una connessione VPN, da un punto di vista funzionale sono equiparabili agli utenti interni. Il processo di acquisizione della licenza d'uso è simile a quello descritto in precedenza in "[Acquisizione della licenza d'uso](https://technet.microsoft.com/0b6cde34-418a-4dee-9d27-b65b93b535ac)" in questo argomento, sia per gli utenti all'interno dell'organizzazione di pubblicazione, sia per quelli all'esterno. L'utente non deve necessariamente appartenere alla rete dell'autore o avere un account utente in tale rete per poter richiedere una licenza d'uso.

Di seguito sono elencati tutti i requisiti previsti:

-   L'utente deve avere un certificato per account con diritti valido.
-   L'utente deve avere accesso al server licenze RMS che ha emesso la licenza di pubblicazione, il quale può trovarsi nell'Intranet o in un'Extranet.
-   L'installazione di RMS che ha emesso il certificato per account dell'utente deve essere presente nella lista dei domini utenti trusted dell'installazione RMS che ha emesso la licenza d'uso.

Le licenze d'uso possono essere ottenute dai tipi seguenti di utenti esterni:

-   Utenti i cui account fanno parte di una diversa struttura di Active Directory in cui sia disponibile un'installazione RMS. In questa configurazione, l'installazione di RMS nell'altra struttura di Active Directory deve essere definita come domini utenti trusted.
-   Utenti in un'altra organizzazione in cui viene eseguita un'installazione di RMS già presente nella lista dei domini utenti trusted di questa installazione.
-   Utenti che dispongono di certificati per account con diritti basati su .NET Passport se il servizio di certificazione di Microsoft RMS è presente nella lista dei domini utenti trusted di questa installazione.

Se necessario, è possibile aggiungere alla lista dei domini utenti trusted un'organizzazione separata o un'altra installazione di RMS presente nell'organizzazione. Dopo aver aggiunto un dominio, è possibile definire i domini di posta elettronica da considerare trusted in tale dominio e scegliere se considerare trusted gli identificatori di protezione (SID, Security IDentifier) presenti in tale dominio.

Mediante altre organizzazioni o installazioni di RMS presenti all'interno dell'organizzazione, è possibile aggiungere l'installazione di RMS alla lista dei domini utenti trusted, in modo che dai server RMS sia possibile elaborare le richieste di licenze d'uso degli utenti.

Per ulteriori informazioni su come creare domini utenti trusted tra RMS e altre organizzazioni, vedere "[Domini utenti trusted](https://technet.microsoft.com/a09b883f-f455-4c46-a4fd-d37b689e1d24)", più avanti in questo argomento, oppure "Aggiunta e rimozione di domini di pubblicazione trusted" in "Utilizzo di un server RMS" in questa documentazione.
