---
TOCTitle: Servizio di registrazione secondaria RMS
Title: Servizio di registrazione secondaria RMS
ms:assetid: '6b05e71c-5e7d-467c-9e13-35ac14d3718a'
ms:contentKeyID: 18824631
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720289(v=WS.10)'
---

Servizio di registrazione secondaria RMS
========================================

Il servizio di registrazione secondaria viene eseguito solo sul cluster principale di RMS. Risponde alle richieste di certificati concessori di licenze server inviate durante il provisioning dai server dei cluster licenze.

Il file applicazione del servizio di registrazione secondaria, SubEnrollService.asmx, si trova nella directory virtuale Certification *Sito\_Web\_RMS*\\\_wmcs\\Certification\\, dove *Sito\_Web\_RMS* viene sostituito dal nome del sito Web in cui è stato eseguito il provisioning di RMS.

Per impostazione predefinita, l'accesso a questo servizio è consentito solo all'account SISTEMA locale. Per effettuare il provisioning e la registrazione di un server subordinato in un cluster licenze, l'account utente dell'amministratore del server licenze deve essere aggiunto all'elenco di controllo di accesso discrezionale (DACL) SubEnrollService.asmx con privilegi di controllo completo.

L'elenco di controllo di accesso predefinito su questo servizio è illustrato nella seguente tabella:

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Utente o gruppo</th>
<th style="border:1px solid black;" >Autorizzazione predefinita</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">SISTEMA</td>
<td style="border:1px solid black;">Controllo completo</td>
</tr>
</tbody>
</table>
