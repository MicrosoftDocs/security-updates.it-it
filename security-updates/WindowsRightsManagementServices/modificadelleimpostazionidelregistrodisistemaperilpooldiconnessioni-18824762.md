---
TOCTitle: Modifica delle impostazioni del Registro di sistema per il pool di connessioni
Title: Modifica delle impostazioni del Registro di sistema per il pool di connessioni
ms:assetid: 'c61d91db-a1ad-4ca5-a492-015da629afbc'
ms:contentKeyID: 18824762
ms:mtpsurl: 'https://technet.microsoft.com/it-it/library/Cc747660(v=WS.10)'
---

Modifica delle impostazioni del Registro di sistema per il pool di connessioni
==============================================================================

Per migliorare le prestazioni del sistema, è possibile utilizzare le voci delle chiavi del Registro di sistema per impostare le proprietà del pool di connessioni LDAP (Lightweight Directory Access Protocol) di Active Directory utilizzato da RMS.

Sui computer che eseguono la versione a 32 bit di Windows Server 2003, la seguente chiave del registro di sistema rappresenta il percorso completo della sottochiave delle voci del registro per il pool di connessioni:

**HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\DRMS\\1.0**

Sui computer che eseguono la versione a 64 bit di Windows Server 2003, la seguente chiave del registro di sistema rappresenta il percorso completo della sottochiave delle voci del registro per il pool di connessioni:

**HKEY\_LOCAL\_MACHINE\\SoftwareWOW6432Node\\Microsoft\\DRMS\\1.0**

Nella tabella seguente, sono elencate le voci che è possibile aggiungere per sovrascrivere le impostazioni del pool di connessioni di Active Directory predefinite. I valori visualizzati sono quelli predefiniti. Per ulteriori informazioni sulle modalità di creazione di un elenco di query in RMS e sull'utilizzo di tali impostazioni, vedere “Ottimizzazione delle impostazioni del pool di connessioni di Active Directory”, più indietro in questo argomento.

###  

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th style="border:1px solid black;" >Nome</th>
<th style="border:1px solid black;" >Tipo</th>
<th style="border:1px solid black;" >Valore predefinito</th>
<th style="border:1px solid black;" >Descrizione</th>
<th style="border:1px solid black;" >Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;">GC</td>
<td style="border:1px solid black;">String</td>
<td style="border:1px solid black;">name-1, ..., name-n</td>
<td style="border:1px solid black;">Elenco separato da virgole di cataloghi globali (tramite l'utilizzo di nomi DNS). Tramite questa chiave, è possibile imporre in RMS il solo utilizzo dei cataloghi globali specificati.</td>
<td style="border:1px solid black;">Se non si desidera che tramite RMS venga creato un elenco di query, utilizzare questa impostazione per specificare i cataloghi globali da utilizzare.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">MinGC</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">Numero minimo di cataloghi globali che devono essere disponibili prima che RMS possa essere avviato.</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">MaxGC</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">15</td>
<td style="border:1px solid black;">Numero massimo di cataloghi globali che verranno aggiunti all'elenco di query tramite l'algoritmo di rilevamento della topologia.</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">ThreshHoldAlive</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">Numero minimo di connessioni da cui deve essere inviata una risposta prima che tramite i servizi di rilevamento venga avviata la ricerca dei cataloghi globali da aggiungere all'elenco di query affinché in RMS vengano accettate le richieste.</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">RetryDown</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">5</td>
<td style="border:1px solid black;">Numero di volte in cui viene effettuato un nuovo tentativo con una connessione inattiva prima che venga dichiarato che tale connessione non risponde.</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">TimeRetryDown</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">300</td>
<td style="border:1px solid black;">Numero di secondi da attendere prima di effettuare un nuovo tentativo con una connessione inattiva.</td>
<td style="border:1px solid black;">Non è necessario modificare questa impostazione predefinita se non in casi eccezionali.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">TimeRetrySlow</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">30</td>
<td style="border:1px solid black;">Numero di secondi da attendere prima di effettuare un nuovo tentativo con una connessione lenta.</td>
<td style="border:1px solid black;">Non è necessario modificare questa impostazione predefinita se non in casi eccezionali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">WtRoundRobin</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1</td>
<td style="border:1px solid black;">Peso del round robin durante il bilanciamento del carico.</td>
<td style="border:1px solid black;">Importanza relativa del round robin nel bilanciamento del carico. 1 è il valore minimo.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">WtThreadCount</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">100</td>
<td style="border:1px solid black;">Peso del conteggio dei thread per connessione durante il bilanciamento del carico.</td>
<td style="border:1px solid black;">Importanza relativa di un bilanciamento dei thread basso.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">WtSlow</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">1,000</td>
<td style="border:1px solid black;">Peso della connessione lenta durante il bilanciamento del carico.</td>
<td style="border:1px solid black;">Importanza relativa della mancata lentezza della connessione.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">TimeOutForGC</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">5</td>
<td style="border:1px solid black;">Numero di secondi da attendere prima del timeout di una richiesta di aggiunta di un catalogo globale all'elenco di query.</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">LdapTimeOut</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">5</td>
<td style="border:1px solid black;">Numero di secondi da attendere prima del timeout durante l'esecuzione di API LDAP.</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">TopDownExpansionLDAPTimeOut</td>
<td style="border:1px solid black;">DWORD</td>
<td style="border:1px solid black;">40</td>
<td style="border:1px solid black;">Numero di secondi da attendere prima del timeout durante l'esecuzione di query LDAP con espansione dall'alto verso il basso.</td>
<td style="border:1px solid black;"></td>
</tr>
</tbody>
</table>
  
| ![](images/Cc747660.Caution(WS.10).gif)Attenzione                                                                                                                                          |  
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Apportando modifiche errate al Registro di sistema, è possibile danneggiare seriamente il sistema. Prima di apportare modifiche al Registro di sistema, effettuare il backup dei dati importanti presenti nel computer. |
