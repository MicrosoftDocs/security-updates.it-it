---
TOCTitle: Tabelle delle certificazioni del database di configurazione RMS
Title: Tabelle delle certificazioni del database di configurazione RMS
ms:assetid: 'd392663a-1a46-42f6-a71d-f0f2c1843566'
ms:contentKeyID: 18824789
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747760(v=WS.10)'
---

Tabelle delle certificazioni del database di configurazione RMS
===============================================================

Nel presente argomento, vengono descritte le tabelle di certificazione del database di configurazione di RMS. Nelle tabelle sono incluse informazioni sui certificati per account con diritti emessi per gli utenti dell'installazione.

UD\_Machines
------------

Nella tabella seguente, sono elencate le informazioni relative agli ID hardware di tutti i computer.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome</th>
<th style="border:1px solid black;" >Tipo di dati</th>
<th style="border:1px solid black;" >Valori NULL</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_MachineId</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">IDENTITY(1,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">b_PubKeyHash</td>
<td style="border:1px solid black;">binary(20)</td>
<td style="border:1px solid black;">(20) Non NULL</td>
<td style="border:1px solid black;">Hash dell'ID hardware</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_CreateDate</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Data e ora dell'aggiunta della voce alla tabella</td>
</tr>
</tbody>
</table>
  
UD\_PassportAuthIdentities  
--------------------------
  
Nella tabella seguente, sono elencate le informazioni relative alle informazioni di Microsoft® .NET Passport per gli utenti.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome</th>
<th style="border:1px solid black;" >Tipo di dati</th>
<th style="border:1px solid black;" >Valori NULL</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_UserId</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">i64_Puid</td>
<td style="border:1px solid black;">bigint</td>
<td style="border:1px solid black;">(50) NULL</td>
<td style="border:1px solid black;">ID utente di .NET Passport</td>
</tr>
</tbody>
</table>
  
UD\_UserMachine  
---------------
  
Nella tabella seguente, gli utenti certificati sono messi in relazione con le informazioni corrispondenti sul computer.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome</th>
<th style="border:1px solid black;" >Tipo di dati</th>
<th style="border:1px solid black;" >Valori NULL</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_MachineId</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">i_UserId</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_CreateDate</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Data e ora dell'aggiunta della voce alla tabella</td>
</tr>
</tbody>
</table>
  
UD\_Users  
---------
  
Nella tabella seguente, sono elencate le informazioni relative ai dati utente.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome</th>
<th style="border:1px solid black;" >Tipo di dati</th>
<th style="border:1px solid black;" >Valori NULL</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_UserId</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">IDENTITY(1,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">b_KeyData</td>
<td style="border:1px solid black;">varbinary(2000)</td>
<td style="border:1px solid black;">(2000) Non NULL</td>
<td style="border:1px solid black;">Chiave privata/pubblica dell'utente crittografata</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">i_KeyDataLength</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Lunghezza della chiave privata/pubblica non crittografata</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">b_PublicKey</td>
<td style="border:1px solid black;">PublicKey</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Chiave pubblica dell'utente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">i_EncryptionDbId</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Indice al certificato concessore di licenze utilizzato per crittografare la coppia chiave privata/pubblica</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">s_Certificate</td>
<td style="border:1px solid black;">ntext</td>
<td style="border:1px solid black;">Non specificato</td>
<td style="border:1px solid black;">Non utilizzato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_Expiration</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Data di scadenza della chiave dell'utente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dt_TemporaryExpiration</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Data e ora di scadenza per l'utilizzo temporaneo della chiave</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">f_Modified</td>
<td style="border:1px solid black;">bit</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Non utilizzato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">i_Quota</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Livello corrente della quota per l'utente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">i_WaitDays</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Numero di giorni prima che le richieste di quote aggiuntive vengano accettate</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dt_LastConsumption</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Data e ora dell'ultima certificazione utente aggiuntiva</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_CreateDate</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Data e ora dell'aggiunta della voce alla tabella</td>
</tr>
</tbody>
</table>
  
UD\_Windows AuthIdentities  
--------------------------
  
Nella tabella seguente, vengono elencati gli ID di tutti gli utenti certificati e autenticati Windows.
  
###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome</th>
<th style="border:1px solid black;" >Tipo di dati</th>
<th style="border:1px solid black;" >Valori NULL</th>
<th style="border:1px solid black;" >Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_UserId</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">s_Sid</td>
<td style="border:1px solid black;">Sid</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">ID di protezione (SID) dell'utente</td>
</tr>
</tbody>
</table>
