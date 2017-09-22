---
TOCTitle: Servizio di precertificazione RMS
Title: Servizio di precertificazione RMS
ms:assetid: '09957294-167f-4f98-88e9-ae90fbeb26c1'
ms:contentKeyID: 18824514
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720191(v=WS.10)'
---

Servizio di precertificazione RMS
=================================

Il servizio di pre-certificazione viene eseguito solo sul cluster principale di RMS. Questo servizio consente al server di richiedere un certificato per account con diritti per conto di un utente, e può essere impiegato per sviluppare applicazioni personalizzate. Tra gli esempi di applicazioni che utilizzano questo servizio vi sono Microsoft Exchange Server 2007 e Microsoft Office SharePoint Server 2007.

Il file di applicazione del servizio di pre-certificazione, Precertification.asmx, è memorizzato nella directory virtuale Certification di IIS.

Per ulteriori informazioni sullo sviluppo di applicazioni personalizzate, vedere la documentazione di Windows Rights Management Services Technology nella libreria MSDN all'indirizzo [http://go.microsoft.com/fwlink/?LinkId=32972](http://go.microsoft.com/fwlink/?linkid=32972).

L'elenco di controllo di accesso predefinito su questo servizio è illustrato nella seguente tabella:

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
<td style="border:1px solid black;"><p>Gruppo di servizi RMS</p></td>
<td style="border:1px solid black;"><p>Lettura e Esecuzione</p></td>
</tr>  
<tr class="odd">
<td style="border:1px solid black;"><p>SISTEMA</p></td>
<td style="border:1px solid black;"><p>Controllo completo</p></td>
</tr>  
<tr class="even">
<td style="border:1px solid black;"><p>Utenti</p></td>
<td style="border:1px solid black;"><p>Lettura e Esecuzione</p></td>
</tr>  
</tbody>  
</table>
