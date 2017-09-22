---
TOCTitle: Servizio proxy di attivazione RMS
Title: Servizio proxy di attivazione RMS
ms:assetid: '6b9d33ef-466b-405b-a768-54e5615d6770'
ms:contentKeyID: 18824634
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747608(v=WS.10)'
---

Servizio proxy di attivazione RMS
=================================

Tutte le richieste di attivazione del computer in RMS versione 1.0 passano attraverso il servizio proxy di attivazione, che viene eseguito solo sul cluster principale di RMS. È necessario attivare un computer client prima di poterlo impiegare con RMS per la pubblicazione o l'utilizzo di contenuto protetto con RMS. A partire da RMS con Service Pack 1, il client è “ad attivazione automatica” e non richiede l'impiego del server proxy di attivazione o del servizio di attivazione Microsoft per generare un archivio protetto e un certificato computer.

Il servizio proxy di attivazione inoltra le richieste di attivazione del computer dai client RMS versione 1.0 al servizio di attivazione Microsoft, il quale restituisce un archivio protetto personalizzato e un corrispondente certificato computer RMS univoci per utente e computer specifici. Il servizio proxy di attivazione inoltra quindi di nuovo questi elementi al client richiedente.

Il file di applicazione del servizio proxy di attivazione, Activation.asmx, è memorizzato nella directory virtuale Certification di IIS. L'elenco di controllo di accesso predefinito su questo servizio è illustrato nella seguente tabella:

###  

<p> </p>
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Utente o gruppo</th>
<th>Autorizzazione predefinita</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><p>Administrators</p></td>
<td style="border:1px solid black;"><p>Controllo completo</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Guests</p></td>
<td style="border:1px solid black;"><p>Lettura e Esecuzione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>Gruppo di servizi RMS</p></td>
<td style="border:1px solid black;"><p>Lettura e Esecuzione</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>SISTEMA</p></td>
<td style="border:1px solid black;"><p>Controllo completo</p></td>
</tr>  
</tbody>  
</table>
