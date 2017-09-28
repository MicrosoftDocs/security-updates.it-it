---
TOCTitle: Pianificazione dei requisiti dei cluster per RMS
Title: Pianificazione dei requisiti dei cluster per RMS
ms:assetid: 'ec4023eb-4d39-4551-9789-c8a2d973a55b'
ms:contentKeyID: 18824843
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747792(v=WS.10)'
---

Pianificazione dei requisiti dei cluster per RMS
================================================

Se si utilizza RMS in una distribuzione su cluster, assicurarsi di aver valutato il modo per affrontare le seguenti condizioni che potrebbero esistere nella propria organizzazione.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Condizione</th>
<th>Consiglio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Grande numero di computer desktop che utilizzano RMS.</td>
<td style="border:1px solid black;">Si può utilizzare Windows Update, uno script, o un metodo di distribuzione software come Systems Management Server (SMS) o Criteri di gruppo per installare e attivare il software del client Servizi Microsoft Windows Rights Management.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Numero elevato di richieste client.</td>
<td style="border:1px solid black;">Utilizzare un server con bilanciamento del carico, il servizio BIlanciamento del carico di rete (NLB), o un dispositivo hardware per il bilanciamento del carico per distribuire le richieste nel cluster.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Due schede di rete che utilizzano il servizio di indirizzamento IP virtuale per soddisfare le richieste Intranet ed Extranet.</td>
<td style="border:1px solid black;">Assicurarsi che qualsiasi registrazione DNS eseguita per esporre l'indirizzo IP virtuale alla Extranet esponga l'indirizzo anche all'Intranet.
Se la registrazione DNS non viene eseguita per l'Intranet, la richiesta interna della licenza d'uso non avrà esito Nel caso che sia impossibile modificare i record di risorse DNS, è possibile modificare la tabella host di ciascun server contenuto nel cluster in modo da eseguire il mapping dell'URL del cluster con l'indirizzo IP virtuale del cluster. La registrazione DNS deve essere eseguita prima del provisioning di RMS. Se il provisioning di RMS è già stato eseguito, si deve annullare il provisioning e ripetere la procedura.</td>
</tr>
</tbody>
</table>
