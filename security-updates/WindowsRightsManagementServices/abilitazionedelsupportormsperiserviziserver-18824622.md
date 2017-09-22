---
TOCTitle: Abilitazione del supporto RMS per i servizi server
Title: Abilitazione del supporto RMS per i servizi server
ms:assetid: '6288323c-0638-41b6-bef8-67a7c9433424'
ms:contentKeyID: 18824622
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747593(v=WS.10)'
---

Abilitazione del supporto RMS per i servizi server
==================================================

RMS può fornire anche certificati degli account con diritti e licenze d'uso alle applicazioni server abilitate per RMS. Nel configurare i servizi server è necessario tenere conto di alcuni fattori:

-   Gli elenchi di controllo di accesso discrezionale (DACL) sulla pipeline di RMS utilizzano per impostazione predefinita le impostazioni più sicure. Quando si utilizzano i servizi server RMS è necessario modificare i DACL.
-   Se il client RMS è installato su un server basato su Windows Server 2003 ed è abilitata la Protezione avanzata di Internet Explorer, è necessario aggiungere l'URL del cluster RMS all'area Siti attendibili di Internet Explorer.
-   Molti servizi server utilizzano funzioni avanzate dei servizi directory di Active Directory che sono disponibili solo se tutti i controller di dominio di Active Directory eseguono Windows Server 2003. Se si utilizzano servizi server (ad esempio Microsoft Office SharePoint Server 2007 o Microsoft Exchange Server 2007), tutti i controller di dominio dovrebbero eseguire Windows Server 2003 e i livelli di funzionalità del dominio e dell'insieme di strutture di Active Directory dovrebbero essere al livello di Windows Server 2003.

Elenco di controllo di accesso discrezionale (DACL) predefinito sulla pipeline di certificazione del server
-----------------------------------------------------------------------------------------------------------

Le applicazioni come Microsoft Office SharePoint Server 2007 o Microsoft Exchange Server 2007 sono abilitate per RMS e possono richiedere licenze d'uso per conto degli utenti. In un'installazione RMS predefinita, il DACL della pipeline di certificazione del server RMS è limitato e di conseguenza le applicazioni non possono ottenere certificati e licenze per i propri utenti. Se tuttavia tali computer utilizzano un'applicazione abilitata per RMS, è possibile abilitarne la partecipazione al sistema RMS configurando i DACL sulla pipeline di certificazione del server RMS.

Le applicazioni server abilitate per RMS si connetteranno al servizio di certificazione di RMS utilizzando il file ServerCertification.asmx.

Quando RMS crea questi file, i DACL dei file sono impostati in modo da consentire l'accesso solo ai processi di sistema. Si consiglia di creare un gruppo di protezione di Active Directory per i servizi server e di inserirvi gli oggetti Active Directory dei computer che richiedono licenze d'uso per conto degli utenti.

Dopo avere creato il gruppo, è possibile modificare il DACL del file ServerCertification.asmx per assegnare al gruppo le autorizzazioni di Lettura e& Esecuzione sul servizio. È inoltre necessario aggiungere il gruppo di servizio di RMS al DACL con le autorizzazioni di Lettura e& Esecuzione.

| ![](images/Cc747593.note(WS.10).gif)Nota                                                                     |
|-------------------------------------------------------------------------------------------------------------------------------------------|
| Se il cluster contiene più di un server RMS, il DACL del file ServerCertification.asmx deve essere modificato su ogni server del cluster. |

Per Microsoft Exchange Server 2007, è necessario aggiungere al gruppo dei servizi server l'oggetto computer Active Directory di ogni server Exchange. In caso contrario, il server testa di ponte Exchange non sarà in grado di richiedere licenze per conto degli utenti che hanno ricevuto il messaggio di posta elettronica.

Per Office SharePoint Server 2007, è necessario aggiungere al gruppo dei servizi server l'oggetto computer Active Directory del server che esegue Office SharePoint Server 2007. Se il server Office SharePoint Server 2007 è configurato in modo da utilizzare il server predefinito in Active Directory, è necessario aggiungere il gruppo di servizio di RMS e il gruppo creato per i servizi server al file ServiceLocater.asmx e assegnare le autorizzazioni di Lettura e& Esecuzione.

| ![](images/Cc747593.Important(WS.10).gif)Importante                                                                                                                                     |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IIS (Internet Information Services) deve essere riavviato dopo la modifica del DACL di ServerCertification.asmx e ServiceLocater.asmx. Per reimpostare IIS, eseguire il comando **iisreset** dal prompt dei comandi. |
