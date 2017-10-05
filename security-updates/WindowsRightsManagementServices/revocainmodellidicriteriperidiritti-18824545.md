---
TOCTitle: Revoca in modelli di criteri per i diritti
Title: Revoca in modelli di criteri per i diritti
ms:assetid: '287c5b92-fcb5-4295-9c2b-4e37e643beb2'
ms:contentKeyID: 18824545
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc720226(v=WS.10)'
---

Revoca in modelli di criteri per i diritti
==========================================

Le condizioni di revoca vengono specificate in modelli di criteri per i diritti. I valori delle condizioni di revoca specificati in un modello di criteri per i diritti vengono catturati in un tag XrML REFRESH nella licenza di pubblicazione rilasciata in base a tale modello. Il tag REFRESH sarà indicato anche nella licenza d'uso risultante rilasciata dal server.

Nella tabella seguente vengono elencati i parametri presenti nel tag REFRESH.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Parametro</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ID</td>
<td style="border:1px solid black;">L'ID dell'elenco di revoche.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ADDRESS</td>
<td style="border:1px solid black;">Il percorso URL o UNC presso cui può essere ottenuto l'elenco di revoche.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PUBLICKEY</td>
<td style="border:1px solid black;">La chiave pubblica dell'autorità emittente dell'elenco di revoche. Questa chiave pubblica corrisponde alla chiave privata utilizzata per firmare l'elenco di revoche.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">INTERVALTIME</td>
<td style="border:1px solid black;">L'età massima dell'elenco di revoche espressa in giorni. Qualora l'elenco di revoche memorizzato nella cache risulti obsoleto rispetto a quanto specificato in INTERVALTIME, il client RMS può ricevere l'elenco delle revoche più aggiornato dall'indirizzo URL indicato in ADDRESS. Questo serve a garantire l'utilizzo di un elenco di revoche aggiornato.</td>
</tr>
</tbody>
</table>
  
Per ulteriori informazioni su come creare modelli di criteri per i diritti, vedere "Creazione e modifica dei modelli di criteri per i diritti" in "Gestione di un server RMS" in questa documentazione.
