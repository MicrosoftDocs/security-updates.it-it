---
TOCTitle: Servizio di gestione licenze RMS
Title: Servizio di gestione licenze RMS
ms:assetid: '5cad1baf-0304-4e82-b62d-83a4aac2140b'
ms:contentKeyID: 18824612
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720278(v=WS.10)'
---

Servizio di gestione licenze RMS
================================

Il servizio di gestione licenze, che emette le licenze d'uso, viene eseguito sul cluster principale di RMS e sugli eventuali cluster licenze. Le licenze d'uso consentono agli utenti di utilizzare il contenuto protetto con RMS.

Il file di applicazione del servizio di gestione delle licenze, License.asmx, è memorizzato nella directory virtuale Licensing di IIS.

| ![](images/Cc720278.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| È possibile distribuire un cluster licenze per delegare le richieste di licenze dal cluster principale. È inoltre possibile distribuire un server o un cluster licenze separato per un reparto, ad esempio per consentire a tale reparto di definire criteri personalizzati per i diritti. Per ulteriori informazioni su queste considerazioni, vedere "Identificazione dei componenti di base" in "Pianificazione e architettura di RMS", in questa documentazione. |

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
