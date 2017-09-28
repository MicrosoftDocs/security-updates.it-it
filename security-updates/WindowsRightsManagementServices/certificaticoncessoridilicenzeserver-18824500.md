---
TOCTitle: Certificati concessori di licenze server
Title: Certificati concessori di licenze server
ms:assetid: '0b35fbcd-25a9-4587-898d-9a30fd1d3c5b'
ms:contentKeyID: 18824500
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720184(v=WS.10)'
---

Certificati concessori di licenze server
========================================

Mediante un certificato concessore di licenze server è possibile concedere ai server RMS il diritto di emettere certificati e licenze. Durante il provisioning del primo server di certificazione principale nella distribuzione di RMS, il Servizio di Enrollment Microsoft rilascia il certificato concessore di licenze server. Questo processo viene definito registrazione. Questo certificato contiene la chiave pubblica del server di certificazione principale ed è firmato con la chiave privata del Servizio di registrazione. Gli altri server aggiunti al cluster di certificazione principale condividono questo certificato.

Durante il provisioning, il primo server licenze all'interno di un cluster riceve un certificato concessore di licenze server dal server o dal cluster di certificazione principale di RMS, durante un processo indicato come registrazione secondaria. Questo certificato contiene la chiave pubblica del server licenze ed è firmato con la chiave privata del server o del cluster di certificazione principale. Gli altri server aggiunti al cluster licenze condividono questo certificato.

Nella tabella seguente vengono elencati i diritti concessi ai server dai certificati concessori di licenze server.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Diritto di rilasciare</th>
<th>Certificato concessore di licenze server rilasciato a un server di certificazione principale</th>
<th>Certificato concessore di licenze server rilasciato a un server licenze</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Certificati per account con diritti</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Licenze di pubblicazione</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Licenze d'uso</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Certificati concessori di licenze server subordinati</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">No</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Certificati concessori di licenze client</td>
<td style="border:1px solid black;">Sì</td>
<td style="border:1px solid black;">Sì</td>
</tr>
</tbody>
</table>
  
| ![](images/Cc720184.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| In RMS, non è necessario disporre di server o cluster licenze separati, ma questi possono essere impiegati per ripartire il carico delle richieste legate alle licenze che deriva dal cluster di certificazione principale. È inoltre consigliabile configurare server licenze per organizzazioni interne che richiedono un controllo diretto sulla pubblicazione di contenuto protetto. Ad esempio, i criteri aziendali generali implementati nei modelli di criteri per i diritti del server o del cluster di certificazione principale potrebbero non specificare alcuni diritti richiesti da un particolare reparto. In tal caso, il reparto potrebbe distribuire un server o un cluster licenze separato per la memorizzazione dei modelli di criteri per i diritti e la gestione delle richieste di licenza. |
