---
TOCTitle: Registrazione di un client RMS
Title: Registrazione di un client RMS
ms:assetid: '9c1d07bf-7235-4694-8291-ac2e5b221f4a'
ms:contentKeyID: 18824712
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747613(v=WS.10)'
---

Registrazione di un client RMS
==============================

I computer client possono registrarsi con il servizio di pubblicazione RMS per ricevere un certificato concessore di licenze client RMS, il quale consente agli autori di pubblicare contenuto protetto con RMS anche utilizzando computer non connessi alla rete aziendale. In questo caso, è il computer client, invece della licenza di pubblicazione, a firmare ed emettere le licenze di pubblicazione che contengono le informazioni relative ai diritti di utilizzo per il contenuto protetto con RMS pubblicato da un determinato computer.

Il servizio di pubblicazione RMS emette i certificati concessore di licenze client.

Il processo di registrazione dei client include i passaggi seguenti:

1.  Il computer client invia il certificato per account con diritti dell'utente in una richiesta di registrazione al servizio di pubblicazione eseguito sul server o sul cluster di certificazione principale, oppure su un server o cluster licenze.
2.  Il server verifica che sia permessa la registrazione del client in base alle impostazioni dell'amministratore di rete, e che il certificato per account con diritti non sia presente in un elenco di esclusione all'interno del database di configurazione. Per ulteriori informazioni su come creare gli elenchi di esclusione, vedere "Gestione del criterio di esclusione" in "Gestione di un server RMS" in questa documentazione.
3.  Il servizio di pubblicazione crea una coppia di chiavi per il computer client. Crea un certificato concessore di licenze client e inserisce la chiave pubblica nel certificato. Crittografa la chiave privata con la chiave pubblica del certificato per account con diritti, quindi la inserisce nel certificato.
4.  Il servizio di pubblicazione rilascia un certificato concessore di licenze client al computer client.
