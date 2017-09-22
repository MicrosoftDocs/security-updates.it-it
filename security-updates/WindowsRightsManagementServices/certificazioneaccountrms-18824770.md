---
TOCTitle: Certificazione account RMS
Title: Certificazione account RMS
ms:assetid: 'c9a385c5-6dbb-47f5-a80f-69718e6f9deb'
ms:contentKeyID: 18824770
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747750(v=WS.10)'
---

Certificazione account RMS
==========================

Il processo di certificazione account crea un certificato per account con diritti, il quale associa un account utente a uno specifico computer e permette all'utente di utilizzare il contenuto protetto con RMS da tale computer. La prima volta che un utente pubblica o tenta di utilizzare contenuto protetto con RMS da un computer client, l'applicazione abilitata per RMS invia la richiesta di un certificato per account con diritti al servizio certificazione account RMS.

Il servizio certificazione può autenticare l'utente mediante l'autenticazione di Windows, oppure tramite un certificato x.509 memorizzato in un dispositivo di crittografia hardware, ad esempio una smartcard. Una volta autenticato l'utente, il server RMS crea il relativo certificato per account con diritti basato sulle sue credenziali autenticate. La chiave privata dell'utente viene crittografata con la chiave pubblica del certificato computer RMS del computer client, mentre il certificato per account con diritti viene incluso nella chiave crittografata. Viene quindi emesso il certificato per account con diritti per l'applicazione che lo richiede, che lo memorizza sul computer o dispositivo al fine di renderlo disponibile per le successive richieste di licenze di pubblicazione o d'uso. Il certificato per account con diritti viene memorizzato anche nel database di configurazione.

La certificazione account segue il processo di attivazione del computer, poiché per richiedere il certificato per account con diritti è necessario il certificato computer RMS del computer client.

Gli utenti devono acquisire un certificato per account con diritti per ogni computer utilizzato. Qualora un utente utilizzi più computer, verrà emesso un certificato per account con diritti univoco per ciascuno di essi, ma tutti i computer conterranno la stessa coppia di chiavi relativa all'utente.

Quando un'applicazione abilitata per RMS richiede una licenza d'uso, il certificato per account con diritti viene incluso nella richiesta. Il servizio di gestione licenze impiega la chiave pubblica del certificato per account con diritti per crittografare la chiave del contenuto; ciò garantisce che solo l'utente autenticato sia in grado di utilizzare la licenza d'uso.

Il processo di certificazione degli account include i passaggi seguenti:

1.  Durante la prima pubblicazione o il primo tentativo di utilizzo di contenuto protetto con RMS da parte di un utente su un determinato computer, l'applicazione abilitata per RMS invia la richiesta di un certificato per account con diritti al servizio certificazione account eseguito sul server di certificazione principale.
2.  Il servizio di certificazione degli account autentica l'utente utilizzando l'autenticazione di Windows.
3.  Il servizio certificazione account crea un certificato per account con diritti per l'utente basato sulle sue credenziali autenticate. Il servizio crittografa la chiave privata dell'utente con la chiave privata del certificato computer RMS, quindi include la chiave crittografata nel certificato. Quindi, il servizio emette il certificato per account con diritti per l'applicazione che lo richiede.
4.  L'applicazione memorizza il certificato per account con diritti sul computer o dispositivo, in modo da renderlo disponibile per le successive richieste di licenze di pubblicazione o d'uso.

Il servizio certificazione account utilizzato dal client per richiedere il certificato per account con diritti dipende dal tipo di computer su cui è installato il client RMS. I computer desktop standard si connettono al servizio certificazione account (certification.asmx). I servizi server abilitati all'uso con RMS SP1 ricevono i certificati per account con diritti dal servizio certificazione server (ServeCertfication.asmx). I dispositivi mobili abilitati all'uso con RMS SP1 ricevono i certificati per account con diritti dal servizio di certificazione dei dispositivi mobili (MobileDeviceCertfication.asmx). Nelle installazioni predefinite di RMS SP1 è abilitato solo il servizio certificazione account.

Per ulteriori informazioni sull'impiego di RMS SP1 con dispositivi mobili e servizi server, vedere "Abilitazione del supporto server RMS per i dispositivi mobili e i servizi server" in Gestione di un server RMS, in questa documentazione.
