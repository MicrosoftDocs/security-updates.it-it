---
TOCTitle: Account e autorizzazioni necessari per RMS
Title: Account e autorizzazioni necessari per RMS
ms:assetid: '07a51daa-6823-41e6-b453-92f1a0592361'
ms:contentKeyID: 18824492
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720178(v=WS.10)'
---

Account e autorizzazioni necessari per RMS
==========================================

Nella tabella seguente, vengono specificati le autorizzazioni e i diritti utente necessari per distribuire e amministrare RMS.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attività</th>
<th>Account utente e autorizzazioni</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Installazione di RMS</td>
<td style="border:1px solid black;">Accedere utilizzando un account di dominio appartenente al gruppo Administrators locale.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Provisioning di RMS</td>
<td style="border:1px solid black;">Accedere utilizzando un account di dominio appartenente al gruppo Administrators locale. È inoltre necessario che l'account utilizzato abbia effettuato un accesso SQL con il ruolo di amministratore del sistema concesso sul database SQL Server, in modo da consentire a RMS di configurare i database.
Nel corso del provisioning, è necessario specificare l'account di servizio RMS, che deve essere già stato creato. È necessario che l'account sia un account utente di dominio standard, senza autorizzazioni aggiuntive. Tale account viene reso membro del gruppo di servizi RMS e utilizzato per l'esecuzione di RMS nel corso delle operazioni di routine.
Per le distribuzioni in un solo server in cui il database si trova nello stesso computer del server di certificazione principale, è possibile specificare l'Account di sistema locale. Tuttavia, per ragioni di protezione, è consigliabile specificare sempre l'account di servizio di RMS invece dell'Account di sistema locale. Quando il database si trova su un server distinto, è necessario specificare l'account di servizio di RMS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Amministrazione di RMS</td>
<td style="border:1px solid black;">Accedere utilizzando un account di dominio appartenente al gruppo Administrators locale. È possibile personalizzare le impostazioni di protezione per gestire l'accesso alle pagine Web di amministrazione.</td>
</tr>
</tbody>
</table>
  
| ![](images/Cc720178.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                   |  
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Per l'account utilizzato per accedere al server RMS, non sono necessarie ulteriori appartenenze a gruppi di dominio aggiuntivi, come ad esempio il gruppo Domain Admins. Per alcune attività amministrative specifiche, quali la registrazione del punto di connessione del servizio e la modifica dei criteri di protezione, è tuttavia necessario un account con ulteriori privilegi. |
