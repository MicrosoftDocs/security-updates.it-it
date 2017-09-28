---
TOCTitle: Tabelle di base del database di configurazione RMS
Title: Tabelle di base del database di configurazione RMS
ms:assetid: '8f9e15a2-92bc-41f7-a4fd-329567afb142'
ms:contentKeyID: 18824694
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747676(v=WS.10)'
---

Tabelle di base del database di configurazione RMS
==================================================

Nel presente argomento, vengono descritte le tabelle di base del database di configurazione di RMS.

DRMS\_ApplicationExclusionList
------------------------------

Nella tabella seguente, sono elencate le informazioni sulle applicazioni escluse.

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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Nome</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Nome dell'applicazione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VersionMinMajor</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Numero di versione principale minimo dell'applicazione</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VersionMinMinor</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Numero di versione secondario minimo dell'applicazione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VersionMinBuild</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Numero di versione della build minimo dell'applicazione</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VersionMinRevision</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Numero di versione della revisione minimo dell'applicazione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VersionMaxMajor</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Numero di versione principale massimo dell'applicazione</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VersionMaxMinor</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Numero di versione secondario massimo dell'applicazione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VersionMaxBuild</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Numero di versione della build massimo dell'applicazione</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">VersionMaxRevision</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Numero di versione della revisione massimo dell'applicazione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Descrizione</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Descrizione dell'applicazione</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dt_DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_AsynchronousQueue  
-----------------------
  
Nella tabella seguente, sono elencate le informazioni relative alla coda di messaggi.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">AsyncQueueID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">QueueName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Percorso della coda di messaggi</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_CaType  
------------
  
Nella tabella seguente, sono elencate le informazioni sul tipo di certificato emesso per il client.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">ID del certificato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TypeName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Desktop, MobileDevice o Server</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_ClusterConfiguration  
--------------------------
  
Nella tabella seguente, sono elencate le informazioni sul certificato concessore di licenze server in uso, incluso nella tabella DRMS\_LicensorCertificate.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">CurrentLicensorCertID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Certificato concessore di licenze attivo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_ClusterPolicies  
---------------------
  
Nella tabella seguente, sono elencate le informazioni sui percorsi in cui sono memorizzati i criteri del cluster.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PolicyID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">ID del criterio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PolicyName</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Nome del criterio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PolicyData</td>
<td style="border:1px solid black;">sql_variant</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Dati del criterio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_ClusterServer  
-------------------
  
Nella tabella seguente, sono elencate le informazioni sui server presenti nel cluster.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ServerID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">ID del server</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ServerName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Non specificato</td>
<td style="border:1px solid black;">Nome del computer per il server</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_GICExclusionList  
----------------------
  
Nella tabella seguente, sono elencate le informazioni sui certificati per account con diritti esclusi.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PublicKeyIndex</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PublicKey</td>
<td style="border:1px solid black;">PublicKey</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Byte della chiave pubblica</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">UserID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Indice ID utente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ExpirationDate</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Data di scadenza del certificato per account con diritti</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Descrizione</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">NOME associato alla chiave del certificato per account con diritti escluso</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dt_DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_LicensorCertificate  
-------------------------
  
Nella tabella seguente, sono elencate le informazioni relative al certificato concessore di licenze server attivo.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_CertID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">ID del criterio</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">s_CertGUIDType</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Tipo di ID della coppia di chiavi</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">s_CertGUID</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">GUID ID della coppia di chiavi</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">i_CertificateID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Puntatore al certificato effettivo</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dt_DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_LicensorPrivateKey  
------------------------
  
Nella tabella seguente, sono elencate le informazioni sulla chiave privata del certificato concessore di licenze server attivo.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PrivateKeyID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CertGUIDType</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Tipo di ID della coppia di chiavi</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CertGUID</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">GUID ID della coppia di chiavi</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PrivateKey</td>
<td style="border:1px solid black;">varbinary(2048)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Rappresentazione binaria della chiave</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CSP</td>
<td style="border:1px solid black;">nvarchar(512)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Nome del provider del servizio di crittografia (CSP)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CSPType</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Tipo di CSP</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">KeyContainerName</td>
<td style="border:1px solid black;">nvarchar(512)</td>
<td style="border:1px solid black;">Non specificato</td>
<td style="border:1px solid black;">Nome del contenitore della chiave</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">KeyNumber</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Numero della chiave</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_PassportDenyList  
----------------------
  
Nella tabella seguente, sono elencate le informazioni sugli account Microsoft® .NET Passport a cui non devono essere concesse le licenze.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">DenyID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DenyAddressPattern</td>
<td style="border:1px solid black;">nvarchar(500)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Nome utente/Nome dominio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_Plugin  
------------
  
Nella tabella seguente, sono elencate le informazioni relative ai plug-in.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PluginID</td>
<td style="border:1px solid black;">Int</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PluginTypeID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Tipo di plug-in</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">NameSpace</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Spazio dei nomi per il plug-in</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PluginName</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Nome del plug-in</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Ordinal</td>
<td style="border:1px solid black;">Int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Numero sequenziale relativo all'esecuzione del plug-in</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Path</td>
<td style="border:1px solid black;">nvarchar(512)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Percorso del file DLL</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">ObjectTypeName</td>
<td style="border:1px solid black;">nvarchar(50)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Non utilizzato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DebugMode</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Valore che indica se eseguire un plug-in in modalità di debug</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PublicKey</td>
<td style="border:1px solid black;">PublicKey</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Chiave pubblica del plug-in</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Version</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Versione del plug-in</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_AllowedPluginVersions  
---------------------------
  
Nella tabella seguente, sono elencate le informazioni sulle versioni di plug-in a cui è concessa la partecipazione al sistema RMS.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">RowID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PluginID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">VersionInfo</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">Non specificato</td>
<td style="border:1px solid black;">Versione del plug-in</td>
</tr>
</tbody>
</table>
  
DRMS\_PluginProperties  
----------------------
  
Nella tabella seguente, sono elencate le informazioni relative alle proprietà dei plug-in.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PropertyID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PluginID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">ID del plug-in a cui appartiene la proprietà</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">PropertyName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Nome della proprietà per i dati di configurazione</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PropertyValue</td>
<td style="border:1px solid black;">text</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Valore della proprietà per i dati di configurazione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_PluginType  
----------------
  
Nella tabella seguente, sono elencate le informazioni relative al tipo di plug-in.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">PluginTypeID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">PluginTypeName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Nome del plug-in</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_RightsTemplate  
--------------------
  
Nella tabella seguente, sono elencate le informazioni relative ai modelli di criteri per i diritti.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">Guid</td>
<td style="border:1px solid black;">nvarchar(128) (PK)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">GUID del modello di criteri per i diritti</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TemplateData</td>
<td style="border:1px solid black;">ntext</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Questo campo contiene i dati del modello XrML.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_TrustedCertificateAuthorities  
-----------------------------------
  
Nella tabella seguente sono elencate le informazioni relative alle autorità di certificazione trusted.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(1,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CertificateID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">ID del certificato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CertificateGUID</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">GUID del certificato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CaTypeID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Tipo di autorità di certificazione</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_TrustedEmailDomains  
-------------------------
  
Nella tabella seguente sono elencate le informazioni relative ai domini di posta elettronica considerati trusted nell'ambiente RMS.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">ID</td>
<td style="border:1px solid black;">int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">i_TrustedIdentityDomainID</td>
<td style="border:1px solid black;">int (FK)t</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">s_EmailDomainName</td>
<td style="border:1px solid black;">nvarchar(256)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Elenco dei nomi dei domini di posta elettronica validi per il dominio utenti trusted</td>
</tr>
</tbody>
</table>
  
DRMS\_TrustedIdentityDomain  
---------------------------
  
Nella tabella seguente, sono elencate le informazioni relative ai domini utente trusted e ai domini di pubblicazione trusted.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_TrustedIdentityDomainID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Indice interno</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">s_DomainType</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Tipo di dominio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">CertGUIDType</td>
<td style="border:1px solid black;">nvarchar(64)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Tipo di GUID del certificato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">CertGUID</td>
<td style="border:1px solid black;">nvarchar(128)</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">GUID del certificato</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">i_CertificateID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">ID del certificato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">i_allowSID</td>
<td style="border:1px solid black;">int</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">SID del dominio</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">S_friendlyname</td>
<td style="border:1px solid black;">nvarchar(255)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Nome descrittivo del certificato</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">dt_DateUpdated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp aggiornamento</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">dt_DateCreated</td>
<td style="border:1px solid black;">datetime</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Timestamp creazione</td>
</tr>
</tbody>
</table>
  
DRMS\_XrML\_Certificate  
-----------------------
  
Nella tabella seguente, sono elencate le informazioni relative ai certificati concessori di licenze server XrML a cui viene fatto riferimento nella tabella DRMS\_LicensorCertificate. Viene inoltre definita la catena di certificati.
  
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
<th>Tipo di dati</th>
<th>Valori NULL</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">i_CertificateID</td>
<td style="border:1px solid black;">Int (PK)</td>
<td style="border:1px solid black;">IDENTITY(100,1) Non NULL</td>
<td style="border:1px solid black;">Puntatore al certificato effettivo</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">s_Certificate</td>
<td style="border:1px solid black;">ntext</td>
<td style="border:1px solid black;">Non NULL</td>
<td style="border:1px solid black;">Puntatore al certificato effettivo</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">i_ParentCertificateID</td>
<td style="border:1px solid black;">int (FK)</td>
<td style="border:1px solid black;">NULL</td>
<td style="border:1px solid black;">Puntatore al certificato effettivo</td>
</tr>
</tbody>
</table>
