---
TOCTitle: Servizio di pubblicazione RMS
Title: Servizio di pubblicazione RMS
ms:assetid: '4c0c8fe3-695c-4b2c-a2d3-cab9b52bbb25'
ms:contentKeyID: 18824591
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720267(v=WS.10)'
---

Servizio di pubblicazione RMS
=============================

Il servizio di pubblicazione, che emette le licenze di pubblicazione, viene eseguito sul server principale di RMS e sugli eventuali cluster licenze. Le licenze di pubblicazione definiscono i criteri in base a cui le licenze d'uso possono essere rilasciate.

Il file di applicazione del servizio di pubblicazione, Publish.asmx, è memorizzato nella directory virtuale Licensing di IIS.

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
<td style="border:1px solid black;">Administrators</td>
<td style="border:1px solid black;">Controllo completo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Gruppo di servizi RMS</td>
<td style="border:1px solid black;">Lettura e Esecuzione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">SISTEMA</td>
<td style="border:1px solid black;">Controllo completo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Utenti</td>
<td style="border:1px solid black;">Lettura e Esecuzione</td>
</tr>
</tbody>
</table>
