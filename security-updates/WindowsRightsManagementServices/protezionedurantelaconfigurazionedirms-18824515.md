---
TOCTitle: Protezione durante la configurazione di RMS
Title: Protezione durante la configurazione di RMS
ms:assetid: '0a3d40b2-f27e-4e63-baff-a9c8433f5f91'
ms:contentKeyID: 18824515
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720192(v=WS.10)'
---

Protezione durante la configurazione di RMS
===========================================

Durante l'installaazione e la configurazione dei file di RMS, nel programma di installazione di RMS vengono impiegate le credenziali dell'utente connesso. L'amministratore che esegue la procedura di installazione deve pertanto accedere con un account utente che sia membro del gruppo di amministratori locale. Questo account utente deve inoltre essere un account utente di dominio per tutte le installazioni, ad eccezioni di quelle di singoli computer.

Durante la procedura di installazione, viene avviato il servizio Windows Installer (Msiexec.exe). Questo servizio eredita il token dell'utente padre. Se successivamente vengono eseguite operazioni personalizzate di post-elaborazione, il servizio Msiexec.exe utilizzerà l'identità dell'utente connesso. Questo indipendentemente dal fatto che il processo sia avviato dall'interno di un browser o dalla riga di comando.

Il programma di installazione di RMS esegue le seguenti operazioni:

-   Copia i file nella cartella C:\\Programmi\\RMS. Questa cartella in genere consente l'accesso sia agli amministratori che agli utenti con privilegi avanzati. È possibile configurare l'unità e il percorso dei file durante il Programma di installazione.
-   Crea un sito Web di provisioning, chiamato sito Web Amministrazione di RMS, per impostazione predefinita sulla porta 5720. Questo sito Web punta ai file installati.
-   Crea un pool di applicazioni, chiamato WMCSProvisioningAppPool e lo associa al sito Web Amministrazione di RMS. L'account di servizio utilizzato da questo pool di applicazioni è Servizio di rete.
-   Installa i contatori di prestazioni.
-   Garantisce le autorizzazioni lettura e scrittura al gruppo di servizi RMS per la seguente chiave del Registro di sistema.
    Su computer in cui è in esecuzione la versione a 32 bit di Windows Server 2003:
    `HKEY_LOCAL_MACHINE\Software\Microsoft\DRMS\1.0`
    Su computer in cui è in esecuzione la versione a 64 bit di Windows Server 2003:
    `HKEY_LOCAL_MACHINE\Software\WOW6432Node\Microsoft\DRMS\1.0`
