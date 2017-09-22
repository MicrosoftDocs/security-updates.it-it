---
TOCTitle: Impostazione delle autorizzazioni sulla directory virtuale
Title: Impostazione delle autorizzazioni sulla directory virtuale
ms:assetid: '45112111-9608-45b1-9a86-7b313d0a1579'
ms:contentKeyID: 18824587
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747549(v=WS.10)'
---

Impostazione delle autorizzazioni sulla directory virtuale
==========================================================

Una volta abilitata, la rimozione delle autorizzazioni è disponibile come servizio. Il servizio di rimozione delle autorizzazioni è tuttavia una directory virtuale IIS a cui sono associate autorizzazioni di accesso. Perché gli utenti possano utilizzare il servizio, occorre impostare le autorizzazioni per la directory virtuale e per il file effettivo, decommission.asmx.

Per impostazione predefinita, è stata abilitata l'autenticazione Windows integrata per la directory virtuale, ma solo gli account di sistema e di amministrazione hanno accesso al file effettivo. Quando si specificano le autorizzazioni per il DACL del file decommission.asmx, è possibile concedere l'accesso a uno specifico gruppo di utenti considerato attendibile per la rimozione dell'effettiva protezione RMS oppure è possibile abilitare per tutti l'accesso al servizio.

Prima che gli utenti possano iniziare a utilizzare il servizio di rimozione delle autorizzazioni, l'applicazione dell'utente deve essere modificata in modo che le richieste di licenza d'uso possano essere inviate alla nuova pipeline di rimozione delle autorizzazioni. Nel caso di Microsoft Office System 2003, questa operazione avviene mediante l'aggiunta di una voce di registro nel computer dell'utente. Se si utilizza Office 2003, per eseguire questo passaggio si può utilizzare la procedura indicata di seguito:

1.  Aprire l'Editor del Registro di sistema.
2.  Portarsi su `HKEY_CURRENT_USER\Software\Microsoft\Office\11,0\Common\DRM` e aggiungere una nuova chiave denominata `Decommissioning`.
3.  Sotto la chiave Decommissioning, aggiungere il seguente nuovo **Valore Stringa**, sostituendo *server-licenze* con il nome del proprio server RMS:
    `http://`*server-licenze*`/_wmcs/licensing`
4.  Fare clic con il pulsante destro del mouse e selezionare **Modifica** per specificare i dati del valore che punta al servizio di rimozione delle autorizzazioni:
    `http://`*server-licenze*`/_wmcs/decommission`

| ![](images/Cc747549.note(WS.10).gif)Nota                                                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quando nell'organizzazione sono disponibili più server RMS in modalità Rimozione autorizzazioni, è possibile che esistano più voci per questa chiave. |
