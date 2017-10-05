---
TOCTitle: Servizio server RMS
Title: Servizio server RMS
ms:assetid: '772d0a89-c9fb-4430-9434-38cd5add1e86'
ms:contentKeyID: 18824652
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747566(v=WS.10)'
---

Servizio server RMS
===================

Il servizio server viene eseguito solo sul cluster principale di RMS. Nel Servizio server vengono esposte le richieste fatte dai client mediante la pubblicazione in linea per ottenere un certificato concessore di licenze server.

Il file di applicazione del servizio Server, Server.asmx, è memorizzato nella directory virtuale Certification di IIS.

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
