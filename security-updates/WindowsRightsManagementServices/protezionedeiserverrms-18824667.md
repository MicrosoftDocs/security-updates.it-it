---
TOCTitle: Protezione dei server RMS
Title: Protezione dei server RMS
ms:assetid: '7e6c4d3a-6cfb-4e96-9dda-ead83f961a6e'
ms:contentKeyID: 18824667
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747574(v=WS.10)'
---

Protezione dei server RMS
=========================

È possibile utilizzare i consigli seguenti per la gestione degli account utente e delle impostazioni di protezione nei server RMS.

-   Le directory virtuali del sito Web utilizzato per l'amministrazione di RMS dispongono di elenchi di controllo di accesso discrezionale (DACL, Discretionary Access Control List) che consentono di limitare l'accesso agli amministratori locali. Un amministratore locale può creare un gruppo di protezione aggiuntivo per controllare ulteriormente l'accesso aggiungendo e rimuovendo i relativi membri e impostando voci di controllo dell'accesso (ACE, Access Control Entry) nelle pagine Web di amministrazione.
-   Per una maggiore protezione, modificare le impostazioni DACL per la pagina Web Impostazioni di protezione (SecurityPolicy.aspx). Per consentire il provisioning, la voce di controllo dell'accesso predefinita consente il controllo completo all'account tramite cui viene eseguito il provisioning di RMS. Al termine del processo di provisioning, è consigliabile modificare la voce ACE impostandola per un gruppo di protezione ristretto o individuale.
-   Oltre alle autorizzazioni e ai diritti per ogni server RMS, prestare particolare attenzione ai requisiti di protezione del database di configurazione, elemento indispensabile per la protezione dell'intera distribuzione. Per ulteriori informazioni, vedere "[Protezione del database di configurazione](https://technet.microsoft.com/e023b96f-81d0-45fb-8cc5-becaf6d47ae1)", più avanti in questo argomento.

Per ulteriori informazioni sulla protezione di Microsoft SQL Server™, vedere la pagina Web relativa alla protezione di **SQL Server** sul [sito Web di Microsoft](http://www.microsoft.com/) (http://www.microsoft.com/).

Per ulteriori informazioni sulla protezione di computer in cui è in esecuzione un membro della famiglia di sistemi operativi Microsoft Windows Server 2003, scaricare la "Windows Server 2003 Security Guide" (Guida alla protezione di Windows Server 2003) dall'area download Microsoft, disponibile nel [sito Web di Microsoft](http://www.microsoft.com/) (http://www.microsoft.com/).
