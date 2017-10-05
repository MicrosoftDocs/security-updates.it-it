---
TOCTitle: Definizioni delle chiavi RMS
Title: Definizioni delle chiavi RMS
ms:assetid: 'b052305c-1db7-434a-bad9-26d704156776'
ms:contentKeyID: 18824746
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747729(v=WS.10)'
---

Definizioni delle chiavi RMS
============================

La tabella che segue elenca le chiavi utilizzate in un sistema RMS.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Chiave</th>
<th style="border:1px solid black;" >Utilizzo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Chiavi del server</td>
<td style="border:1px solid black;"><strong>Chiave pubblica</strong>
Crittografa la chiave del contenuto presente in una licenza di pubblicazione affinché solo il server RMS possa richiamare la chiave del contenuto ed emettere le licenze d'uso in base a tale licenza di pubblicazione.
<strong>Chiave privata</strong>
Firma tutti i certificati e le licenze rilasciati dal server.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Chiavi del computer</td>
<td style="border:1px solid black;"><strong>Chiave pubblica</strong>
Crittografa la chiave privata di un certificato per account con diritti.
<strong>Chiave privata</strong>
Decrittografa un certificato per account con diritti.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Chiavi del concessore di licenze client</td>
<td style="border:1px solid black;"><strong>Chiave pubblica</strong>
Crittografa la chiave simmetrica del contenuto nelle licenze di pubblicazione che rilascia.
<strong>Chiave privata</strong>
Firma le licenze di pubblicazione rilasciate localmente mentre l'utente non è connesso alla rete.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Chiavi dell'utente</td>
<td style="border:1px solid black;"><strong>Chiave pubblica</strong>
Crittografa la chiave del contenuto presente in una licenza d'uso affinché solo un determinato utente possa utilizzare il contenuto protetto con RMS mediante tale licenza.
<strong>Chiave privata</strong>
Consente all'utente di utilizzare il contenuto protetto con RMS.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Chiavi del contenuto</td>
<td style="border:1px solid black;">Crittografa il contenuto protetto con RMS nel momento in cui l'autore lo pubblica.</td>
</tr>
</tbody>
</table>
