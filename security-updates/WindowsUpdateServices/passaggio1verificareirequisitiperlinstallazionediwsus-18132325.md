---
TOCTitle: 'Passaggio 1: Verificare i requisiti per l''installazione di WSUS'
Title: 'Passaggio 1: Verificare i requisiti per l''installazione di WSUS'
ms:assetid: '57d7f8ec-1523-4485-9967-604be9ba2aac'
ms:contentKeyID: 18132325
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720547(v=WS.10)'
---

Passaggio 1: Verificare i requisiti per l'installazione di WSUS
===============================================================

In questa guida sono disponibili istruzioni per l'installazione di Microsoft Windows Server Update Services (WSUS) nei sistemi operativi Microsoft Windows Server 2003, ad eccezione di Windows Server 2003, Web Edition e di tutte le versioni a 64 bit. Per ulteriori informazioni sui server che eseguono Microsoft Windows 2000 Server, vedere il white paper “Deploying Microsoft Windows Server Update Services” (informazioni in lingua inglese).

Di seguito vengono illustrati i requisiti di base per le installazioni in cui vengono utilizzate le opzioni predefinite. Per informazioni sui requisiti hardware e software per le altre installazioni, vedere il white paper “Deploying Microsoft Windows Server Update Services” (informazioni in lingua inglese).

Per un server che supporta fino a 500 client, è consigliabile utilizzare i requisiti hardware seguenti:

-   Processore a 1 gigahertz (GHz)
-   1 gigabyte (GB) di RAM

Requisiti software
------------------

Per installare WSUS con le opzioni predefinite, è necessario disporre di un computer in cui è installato il software seguente. Per ulteriori informazioni sui requisiti software di WSUS, vedere il white paper “Deploying Microsoft Windows Server Update Services” (informazioni in lingua inglese). Se uno di questi aggiornamenti richiede il riavvio del computer al termine dell'installazione, è necessario riavviare il server prima dell'installazione di WSUS.

-   Microsoft Internet Information Services (IIS) 6.0. Per istruzioni relative all'installazione di IIS, vedere il white paper “Deploying Microsoft Windows Server Update Services” (informazioni in lingua inglese) o la Guida in linea e supporto tecnico di Windows Server 2003.
-   Microsoft .NET Framework 1.1 Service Pack 1 per Windows Server 2003. Per scaricare questo software, visitare il sito Web [Area download Microsoft](http://go.microsoft.com/fwlink/?linkid=47358) all'indirizzo http://go.microsoft.com/fwlink/?LinkId=47358.
    In alternativa, è possibile visitare il sito Web http://www.windowsupdate.com, individuare gli aggiornamenti critici e i Service Pack e quindi installare Microsoft .NET Framework 1.1 Service Pack 1 per Windows Server 2003.
-   Servizio trasferimento intelligente in background (BITS) 2.0. BITS 2.0 per Windows Server 2003 non è attualmente disponibile nel sito Web Area download Microsoft. Per scaricare questo software, visitare il [sito Web Microsoft](http://go.microsoft.com/fwlink/?linkid=47357) in cui è disponibile una versione di valutazione di Windows Server Update Services all'indirizzo http://go.microsoft.com/fwlink/?LinkId=47357.

| ![](images/Cc720547.note(WS.10).gif)Nota                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Il software di database necessario per l'installazione di WSUS non è presente in questo elenco perché l'installazione predefinita di WSUS in Windows Server 2003 include il software di database Windows SQL Server™ 2000 Desktop Engine (WMSDE). |

Requisiti di spazio su disco
----------------------------

Per l'installazione di WSUS, il file system del server deve soddisfare i requisiti seguenti:

-   La partizione di sistema e la partizione in cui WSUS è installato devono essere formattate con il file system NTFS.
-   La partizione di sistema richiede almeno 1 GB di spazio disponibile.
-   Sono necessari almeno 6 GB di spazio disponibile per il volume in cui viene archiviato il contenuto di WSUS. È consigliabile disporre di 30 GB.
-   Sono necessari almeno 2 GB di spazio disponibile nel volume in cui viene installato Windows SQL Server 2000 Desktop Engine (WMSDE).

Requisiti di Aggiornamenti automatici
-------------------------------------

Aggiornamenti automatici è il componente client di WSUS. Per Aggiornamenti automatici non sono necessari requisiti hardware particolari ad eccezione della connessione alla rete. È possibile utilizzare Aggiornamenti automatici con WSUS nei computer che eseguono uno dei sistemi operativi seguenti:

-   Microsoft Windows 2000 Professional con Service Pack 3 (SP3) o Service Pack 4 (SP4), Windows 2000 Server con SP3 o SP4 oppure Windows 2000 Advanced Server con SP3 o SP4.
-   Microsoft Windows XP Professional con o senza Service Pack 1 o Service Pack 2.
-   Microsoft Windows Server 2003, Standard Edition, Windows Server 2003, Enterprise Edition, Windows Server 2003, Datacenter Edition oppure Windows Server 2003, Web Edition.
