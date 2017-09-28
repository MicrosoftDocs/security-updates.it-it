---
TOCTitle: Modifica delle impostazioni della cache di Active Directory
Title: Modifica delle impostazioni della cache di Active Directory
ms:assetid: '8789a7a5-2065-4fae-9104-e0a70f1f2fb6'
ms:contentKeyID: 18824679
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747586(v=WS.10)'
---

Modifica delle impostazioni della cache di Active Directory
===========================================================

Le impostazioni del Registro di sistema consentono di specificare il numero di voci che vengono memorizzate nella cache di Active Directory. Per migliorare il tempo di risposta alle richieste del client, è possibile modificare tali impostazioni. Per ulteriori informazioni, vedere “Ottimizzazione delle prestazioni dei servizi di directory”, più indietro in questo argomento. È inoltre possibile specificare il periodo di validità delle informazioni memorizzate nella cache.

Sui computer che eseguono la versione a 32 bit di Windows Server 2003, la seguente chiave del registro di sistema rappresenta il percorso completo della sottochiave delle voci della cache:

**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\DRMS\\1.0\\DirectoryServices**

Sui computer che eseguono la versione a 64 bit di Windows Server 2003, la seguente chiave del registro di sistema rappresenta il percorso completo della sottochiave delle voci della cache:

**HKEY\_LOCAL\_MACHINE\\SoftwareWOW6432Node\\Microsoft\\DRMS\\1.0\\DirectoryServices**

Nella tabella seguente, sono elencate le voci tramite le quali viene controllato il comportamento della cache in memoria.

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
<th>Nome</th>
<th>Tipo</th>
<th>Valore predefinito</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PrincipalCacheMax</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1,000</td>
<td style="border:1px solid black;">Numero massimo di entità e relativi indirizzi di posta elettronica e SID che è possibile memorizzare nella cache.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PrincipalCacheExpireMinutes</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">12</td>
<td style="border:1px solid black;">Periodo di validità delle informazioni memorizzate nella cache per le entità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">GroupIDCacheMax</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1,000</td>
<td style="border:1px solid black;">Numero massimo di gruppi e relativi indirizzi di posta elettronica e SID che è possibile memorizzare nella cache.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">GroupIDCacheExpireMinutes</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">12</td>
<td style="border:1px solid black;">Periodo di validità delle informazioni memorizzate nella cache per l'appartenenza al gruppo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">GroupMembershipCacheMax</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1,000</td>
<td style="border:1px solid black;">Numero massimo di contatti membri di un gruppo che è possibile memorizzare nella cache.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">GroupMembershipCacheExpireMinutes</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">12</td>
<td style="border:1px solid black;">Periodo di validità delle informazioni memorizzate nella cache per contatti che sono membri di un gruppo.</td>
</tr>
</tbody>
</table>
  
| ![](images/Cc747586.Caution(WS.10).gif)Attenzione                                                                                                                                          |  
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Apportando modifiche errate al Registro di sistema, è possibile danneggiare seriamente il sistema. Prima di apportare modifiche al Registro di sistema, effettuare il backup dei dati importanti presenti nel computer. |
  
| ![](images/Cc747586.note(WS.10).gif)Nota                                                                                                                                                                                                                                                                              |  
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Anche le voci del registro **PrincipalCacheExpireMinutes**, **GroupIDCacheExpireMinutes**, **GroupMembershipCacheExpireMinutes** e **ContactMembersofGroupCacheExpireMinutes** consentono di controllare la scadenza della cache nella cache locale di Active Directory memorizzata nel database dei servizi di directory sul server del database. |
