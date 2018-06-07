---
TOCTitle: 'MS10-OCT'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Ottobre 2010'
ms:assetid: 'ms10-oct'
ms:contentKeyID: 61240052
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms10-oct(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Ottobre 2010
=================================================================

Data di pubblicazione: martedì 12 ottobre 2010 | Aggiornamento: mercoledì 26 ottobre 2011

**Versione:** 4.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a ottobre 2010.

Con il rilascio dei bollettini del mese di ottobre 2010, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 7 ottobre 2010. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/advance).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 13 ottobre 2010 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di ottobre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032454437&culture=en-us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

Riepiloghi
----------

<span></span>
La seguente tabella riassume i bollettini sulla sicurezza di questo mese in ordine di gravità.

Per ulteriori informazioni sul software interessato, vedere la sezione successiva, **Software interessato e percorsi per il download**.

 
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
<th style="border:1px solid black;" >ID bollettino</th>
<th style="border:1px solid black;" >Titolo del bollettino e riepilogo</th>
<th style="border:1px solid black;" >Livello di gravità massimo e impatto della vulnerabilità</th>
<th style="border:1px solid black;" >Necessità di riavvio</th>
<th style="border:1px solid black;" >Software interessato</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=202013">MS10-071</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2360131)</strong><br />
<br />
Questo aggiornamento per la protezione risolve sette vulnerabilità segnalate privatamente e tre vulnerabilità divulgate pubblicamente relative a Internet Explorer. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201722">MS10-075</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità legata al servizio di condivisione di rete di Media Player può consentire l'esecuzione di codice in modalità remota (2281679)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel servizio di condivisione di rete di Microsoft Windows Media Player. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota nel momento in cui un utente malintenzionato invia un pacchetto RPC (Remote Procedure Call) appositamente predisposto a un sistema interessato. Tuttavia, l'accesso Internet ai file multimediali personali è disattivato per impostazione predefinita. In questa configurazione predefinita, la vulnerabilità può essere sfruttata solo da un utente malintenzionato all'interno della stessa subnet.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=194560">MS10-076</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel motore per caratteri Embedded OpenType può consentire l'esecuzione di codice in modalità remota (982132)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità nel motore per caratteri Embedded OpenType (EOT), componente di Microsoft Windows. Tale vulnerabilità è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo in remoto del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201704">MS10-077</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità</strong> <strong>in .NET Framework può consentire l'esecuzione di codice in modalità remota (2160841)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft .NET Framework che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota su un sistema client se un utente visualizza una pagina Web appositamente predisposta mediante un browser Web in grado di eseguire applicazioni XAML (XBAP). Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. La vulnerabilità può consentire anche l'esecuzione di codice in modalità remota su un sistema server che esegue IIS, se tale server consente l'elaborazione delle pagine ASP.NET e se un utente malintenzionato riesce a caricare ed eseguire una pagina ASP.NET appositamente predisposta in tale server, come può accadere nel caso di uno scenario di hosting Web.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=202016">MS10-072</a></td>
<td style="border:1px solid black;"><strong>Le vulnerabilità in SafeHTML possono consentire l'intercettazione di informazioni personali (2412048)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e una segnalata privatamente in Microsoft SharePoint e in Windows SharePoint Services. Le vulnerabilità possono consentire l'intercettazione di informazioni personali se un utente malintenzionato presenta lo script appositamente predisposto a un sito di destinazione che utilizza SafeHTML.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Software dei server Microsoft</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201093">MS10-073</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver</strong> <strong>in modalità kernel di Windows possono consentire l'acquisizione di privilegi più elevati (981957)</strong><br />
<br />
Questo aggiornamento per la protezione risolve diverse vulnerabilità divulgate pubblicamente nei driver in modalità kernel di Windows. La più grave delle vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede al sistema interessato ed esegue un'applicazione appositamente predisposta.
Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale. La vulnerabilità non può essere sfruttata in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201084">MS10-078</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità presenti nel driver del formato del carattere OpenType (OTF) possono consentire l'acquisizione di privilegi più elevati (2279986)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente nel driver di formato dei caratteri OpenType (OTF) di Windows. Questo aggiornamento per la protezione è considerato di livello importante per tutte le edizioni supportate di Windows XP e Windows Server 2003. Tutte le edizioni supportate di Windows Vista, Windows Server 2008, Windows 7 e Windows Server 2008 R2 non sono interessate dalla vulnerabilità.<br />
<br />
Le vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente visualizza un contenuto reso con un carattere OpenType appositamente predisposto. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale. La vulnerabilità non può essere sfruttata in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201696">MS10-079</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Word possono consentire l'esecuzione di codice in modalità remota (2293194)</strong><br />
<br />
Questo aggiornamento per la protezione risolve undici vulnerabilità di Microsoft Office segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file Word appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=200529">MS10-080</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (2293211)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tredici vulnerabilità di Microsoft Office segnalate privatamente. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file Excel appositamente predisposto o un file Lotus 1-2-3 appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201086">MS10-081</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nella libreria dei controlli comuni di Windows potrebbe consentire l'esecuzione di codice in modalità remota (2296011)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità presente nella libreria dei controlli comuni segnalata a Microsoft privatamente. Questa vulnerabilità può consentire l'esecuzione di codice in modalità remota durante la visualizzazione di una pagina Web appositamente predisposta. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato che sfrutti questa vulnerabilità può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201098">MS10-082</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Windows Media Player può consentire l'esecuzione di codice in modalità remota (2378111)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Windows Media Player che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se Windows Media Player apre contenuti multimediali appositamente predisposti ospitati su un sito Web dannoso. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=190553">MS10-083</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità nella Convalida COM nella Shell di Windows e in WordPad potrebbe consentire l'esecuzione di codice in modalità remota (2405882)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file appositamente predisposto mediante WordPad o seleziona o apre un file collegamento che si trova su una condivisione di rete o WebDAV. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201720">MS10-084</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Windows Local Procedure Call può consentire l'acquisizione di privilegi più elevati (2360937)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft Windows. Questo aggiornamento per la protezione è considerato di livello importante per tutte le edizioni supportate di Windows XP e Windows Server 2003. Tutte le edizioni supportate di Windows Vista, Windows Server 2008, Windows 7 e Windows Server 2008 R2 non sono interessate dalla vulnerabilità.<br />
<br />
La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede al sistema interessato ed esegue un codice appositamente predisposto che invia un messaggio LPC al server LRPC locale. Il messaggio può quindi consentire a un utente autenticato di accedere alle risorse in esecuzione nel contesto di un account NetworkService. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201705">MS10-085</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità presente in SChannel può consentire un attacco di tipo Denial of Service (2207566)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità del pacchetto di protezione Canale sicuro (SChannel) di Windows, che è stata segnalata privatamente. La vulnerabilità può consentire un attacco di tipo Denial of Service se un sistema interessato riceve un pacchetto a messaggi appositamente predisposto mediante il protocollo SSL (Secure Sockets Layer). Per impostazione predefinita, tutte le edizioni supportate di Windows Vista, Windows Server 2008, Windows 7 e Windows Server 2008 R2 non sono configurate per la ricezione del traffico di rete SSL.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201703">MS10-074</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità legata alle classi di Microsoft Foundation può consentire l'esecuzione di codice in modalità remota (2387149)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente nella libreria Microsoft Foundation Class (MFC). La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente è connesso con i diritti utente amministrativi e apre un'applicazione realizzata con la libreria MFC. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere le stesse autorizzazioni dell'utente connesso. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Moderato</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=201721">MS10-086</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei dischi condivisi del cluster di Windows può consentire la manomissione dei dati (2294255)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Windows Server 2008 R2 quando viene utilizzato come cluster di failover condiviso. La vulnerabilità può consentire la manomissione dei dati nelle condivisioni amministrative dei dischi del cluster di failover. Per impostazione predefinita, i server di Windows Server 2008 R2 non sono interessati da questa vulnerabilità. Questa vulnerabilità interessa solo i dischi del cluster utilizzati in un cluster di failover.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Moderato</a><br />
Manomissione</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità sono elencate in ordine decrescente sulla base del livello di valutazione del rischio e quindi del codice CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).
  
| ID bollettino                                             | Titolo della vulnerabilità                                                                                          | ID CVE                                                                           | Valutazione dell'Exploitability Index                                                                                       | Note fondamentali                                                                                                                                                                                                                                                                   |  
|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| [MS10-083](http://go.microsoft.com/fwlink/?linkid=190553) | Vulnerabilità legata alla convalida COM                                                                             | [CVE-2010-1263](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1263) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-076](http://go.microsoft.com/fwlink/?linkid=194560) | Vulnerabilità legata all'overflow dei valori interi dei caratteri Embedded OpenType                                 | [CVE-2010-1883](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1883) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Grazie ad ASLR presente sui sistemi operativi più recenti lo sfruttamento della vulnerabilità è più difficile                                                                                                                                                                       |  
| [MS10-078](http://go.microsoft.com/fwlink/?linkid=201084) | Vulnerabilità legata all'analisi dei caratteri OpenType                                                             | [CVE-2010-2740](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2740) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-078](http://go.microsoft.com/fwlink/?linkid=201084) | Vulnerabilità legata alla convalida dei caratteri OpenType                                                          | [CVE-2010-2741](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2741) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-073](http://go.microsoft.com/fwlink/?linkid=201093) | Vulnerabilità legata al layout di tastiera Win32k                                                                   | [CVE-2010-2743](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2743) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Questa vulnerabilità è stata divulgata pubblicamente ed è attualmente sfruttata nell'ecosistema di Internet**                                                                                                                                                                     |  
| [MS10-073](http://go.microsoft.com/fwlink/?linkid=201093) | Vulnerabilità legata alla creazione di classi di finestre Win32K                                                    | [CVE-2010-2744](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2744) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Le informazioni sulla vulnerabilità sono state divulgate pubblicamente**                                                                                                                                                                                                          |  
| [MS10-082](http://go.microsoft.com/fwlink/?linkid=201098) | Vulnerabilità legata al danneggiamento della memoria di Windows Media Player                                        | [CVE-2010-2745](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2745) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-081](http://go.microsoft.com/fwlink/?linkid=201086) | Vulnerabilità legata all'overflow degli heap Comctl32                                                               | [CVE-2010-2746](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2746) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata all'overflow dello stack in Word                                                               | [CVE-2010-3214](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3214) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata ai segnalibri in Word                                                                          | [CVE-2010-3216](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3216) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-084](http://go.microsoft.com/fwlink/?linkid=201720) | Vulnerabilità legata al sovraccarico del buffer del messaggio LPC                                                   | [CVE-2010-3222](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3222) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Le informazioni sulla vulnerabilità sono state divulgate pubblicamente**                                                                                                                                                                                                          |  
| [MS10-075](http://go.microsoft.com/fwlink/?linkid=201722) | Vulnerabilità legata a un errore di tipo use-after-free di RTSP                                                     | [CVE-2010-3225](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3225) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-077](http://go.microsoft.com/fwlink/?linkid=201704) | Vulnerabilità legata al compilatore JIT x64 di .NET Framework                                                       | [CVE-2010-3228](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3228) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata all'analisi dei formati file Excel                                                             | [CVE-2010-3232](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3232) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata al danneggiamento della memoria nel substream delle formule                                    | [CVE-2010-3234](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3234) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata al record BIFF delle formule                                                                   | [CVE-2010-3235](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3235) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata alle matrici fuori dai limiti                                                                  | [CVE-2010-3236](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3236) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata alla funzione futura negativa                                                                  | [CVE-2010-3238](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3238) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata all'analisi extra dei record fuori dai limiti                                                  | [CVE-2010-3239](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3239) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-071](http://go.microsoft.com/fwlink/?linkid=202013) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                              | [CVE-2010-3326](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3326) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-071](http://go.microsoft.com/fwlink/?linkid=202013) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                              | [CVE-2010-3328](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3328) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-071](http://go.microsoft.com/fwlink/?linkid=202013) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                              | [CVE-2010-3329](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3329) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-071](http://go.microsoft.com/fwlink/?linkid=202013) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                              | [CVE-2010-3331](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3331) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata ad un puntatore non inizializzato in Word                                                      | [CVE-2010-2747](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2747) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata al controllo limiti in Word                                                                    | [CVE-2010-2748](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2748) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata agli indici in Word                                                                            | [CVE-2010-2750](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2750) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata al valore restituito in Word                                                                   | [CVE-2010-3215](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3215) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata ai puntatori in Word                                                                           | [CVE-2010-3217](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3217) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata all'overflow degli heap in Word                                                                | [CVE-2010-3218](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3218) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata all'analisi degli indici in Word                                                               | [CVE-2010-3219](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3219) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata all'analisi in Word                                                                            | [CVE-2010-3220](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3220) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-079](http://go.microsoft.com/fwlink/?linkid=201696) | Vulnerabilità legata all'analisi in Word                                                                            | [CVE-2010-3221](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3221) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata all'overflow dei valori integer nell'analisi dei record di Excel                               | [CVE-2010-3230](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3230) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata al danneggiamento della memoria di analisi dei record di Excel                                 | [CVE-2010-3231](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3231) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata all'analisi delle cartelle di lavoro Lotus 1-2-3                                               | [CVE-2010-3233](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3233) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata al puntatore record Unisci celle                                                               | [CVE-2010-3237](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3237) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata al record matrice dei dati in tempo reale                                                      | [CVE-2010-3240](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3240) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata all'analisi lettura memoria fuori dai limiti                                                   | [CVE-2010-3241](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3241) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-080](http://go.microsoft.com/fwlink/?linkid=200529) | Vulnerabilità legata all'analisi dei tipi di record fantasma                                                        | [CVE-2010-3242](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3242) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                                                           |  
| [MS10-073](http://go.microsoft.com/fwlink/?linkid=201093) | Vulnerabilità legata al conteggio dei riferimenti Win32k                                                            | [CVE-2010-2549](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2549) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | **Le informazioni sulla vulnerabilità sono state divulgate pubblicamente**                                                                                                                                                                                                          |  
| [MS10-085](http://go.microsoft.com/fwlink/?linkid=201705) | Vulnerabilità ad attacchi di tipo Denial of Service dovuta al meccanismo di convalida di TLSv1                      | [CVE-2010-3229](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3229) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Il livello massimo di impatto sulla protezione riguarda solo gli attacchi di tipo Denial of Service                                                                                                                                                                                 |  
| [MS10-071](http://go.microsoft.com/fwlink/?linkid=202013) | Vulnerabilità legata alla disinfezione del contenuto HTML                                                           | [CVE-2010-3243](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3243) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | [MS10-072](http://go.microsoft.com/fwlink/?linkid=202016) risolve anche questa vulnerabilità. Il livello massimo di impatto sulla protezione riguarda solo l'intercettazione di informazioni personali.                                                                             |  
| [MS10-072](http://go.microsoft.com/fwlink/?linkid=202016) | Vulnerabilità legata alla disinfezione del contenuto HTML                                                           | [CVE-2010-3243](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3243) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | [MS10-071](http://go.microsoft.com/fwlink/?linkid=202013) risolve anche questa vulnerabilità. Il livello massimo di impatto sulla protezione riguarda solo l'intercettazione di informazioni personali.                                                                             |  
| [MS10-071](http://go.microsoft.com/fwlink/?linkid=202013) | Vulnerabilità legata alla disinfezione del contenuto HTML                                                           | [CVE-2010-3324](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3324) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | [MS10-072](http://go.microsoft.com/fwlink/?linkid=202016) risolve anche questa vulnerabilità. **Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.** Il livello massimo di impatto sulla protezione riguarda solo l'intercettazione di informazioni personali. |  
| [MS10-072](http://go.microsoft.com/fwlink/?linkid=202016) | Vulnerabilità legata alla disinfezione del contenuto HTML                                                           | [CVE-2010-3324](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3324) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | [MS10-071](http://go.microsoft.com/fwlink/?linkid=202013) risolve anche questa vulnerabilità. **Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.** Il livello massimo di impatto sulla protezione riguarda solo l'intercettazione di informazioni personali. |  
| [MS10-071](http://go.microsoft.com/fwlink/?linkid=202013) | Vulnerabilità legata all'intercettazione di informazioni personali durante l'elaborazione di caratteri speciali CSS | [CVE-2010-3325](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3325) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | **Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.** Il livello massimo di impatto sulla protezione riguarda solo l'intercettazione di informazioni personali.                                                                                               |  
| [MS10-071](http://go.microsoft.com/fwlink/?linkid=202013) | Vulnerabilità del modello di protezione tra domini legata all'intercettazione di informazioni personali             | [CVE-2010-3330](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3330) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Il livello massimo di impatto sulla protezione riguarda solo l'intercettazione di informazioni personali                                                                                                                                                                            |
  
Software interessato e percorsi per il download  
-----------------------------------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.
  
**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.
  
#### Sistema operativo Windows e suoi componenti

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="14">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-071**](http://go.microsoft.com/fwlink/?linkid=202013)
</td>
<td style="border:1px solid black;">
[**MS10-075**](http://go.microsoft.com/fwlink/?linkid=201722)
</td>
<td style="border:1px solid black;">
[**MS10-076**](http://go.microsoft.com/fwlink/?linkid=194560)
</td>
<td style="border:1px solid black;">
[**MS10-077**](http://go.microsoft.com/fwlink/?linkid=201704)
</td>
<td style="border:1px solid black;">
[**MS10-073**](http://go.microsoft.com/fwlink/?linkid=201093)
</td>
<td style="border:1px solid black;">
[**MS10-078**](http://go.microsoft.com/fwlink/?linkid=201084)
</td>
<td style="border:1px solid black;">
[**MS10-081**](http://go.microsoft.com/fwlink/?linkid=201086)
</td>
<td style="border:1px solid black;">
[**MS10-082**](http://go.microsoft.com/fwlink/?linkid=201098)
</td>
<td style="border:1px solid black;">
[**MS10-083**](http://go.microsoft.com/fwlink/?linkid=190553)
</td>
<td style="border:1px solid black;">
[**MS10-084**](http://go.microsoft.com/fwlink/?linkid=201720)
</td>
<td style="border:1px solid black;">
[**MS10-085**](http://go.microsoft.com/fwlink/?linkid=201705)
</td>
<td style="border:1px solid black;">
[**MS10-074**](http://go.microsoft.com/fwlink/?linkid=201703)
</td>
<td style="border:1px solid black;">
[**MS10-086**](http://go.microsoft.com/fwlink/?linkid=201721)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=3b029696-cf98-4935-b3d6-846110aaa4bb)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=c77ee103-7e97-44b2-bbf3-ee9f0de37fed)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=93580299-d764-417f-a7fa-ee441fea2bb3)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=c3799399-ca72-4dec-a2a2-3571ad0b2f63)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=3966d754-d298-4e4a-9ce6-8205accd2215)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=0553fc7c-deed-4594-a133-d621551310dc)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=912a7c20-8177-4f65-b986-43fca6375ec1)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 9 Series](http://www.microsoft.com/downloads/details.aspx?familyid=bbf153e7-e764-46a0-a33b-81b7288d346c)  
(Importante)  
[Windows Media Player 10](http://www.microsoft.com/downloads/details.aspx?familyid=bbf153e7-e764-46a0-a33b-81b7288d346c)  
(Importante)  
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=bbf153e7-e764-46a0-a33b-81b7288d346c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=211d95be-5630-4af5-85a7-c50268c475a9)  
(KB979687)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6049c879-b81a-4d10-b96b-b2837cb24834)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=22f46b3b-9be6-45ea-a639-9974324ce4bd)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=d494535a-b68e-4242-af85-5fa62f631ffc)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ff9c65fe-437c-426d-9096-dd89ff7927fd)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=05413f6c-b4be-4892-b4b3-c54dd01fd95d)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=860ff738-205d-430e-b223-b333813fc590)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)<sup>[1]</sup>
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7fd7c675-0675-4a87-a709-edc47a30f1e2)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1ad30596-bac6-4d48-8b15-0245960c443b)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6c651bca-adb1-4172-9714-cd5a6e5d2c2a)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 10](http://www.microsoft.com/downloads/details.aspx?familyid=0663e0e8-c5d1-4cd2-b6d3-ff78fb56bba1)  
(Importante)  
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=474b5618-dfe6-40de-b59b-1fd61a05749e)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4b6f0898-8f77-4ce1-9c96-2b17c496230b)  
(KB979687)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d690846c-5e0b-4216-84cd-d17e366dd16d)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=285627b9-242d-4247-a4c8-55dc89386b62)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="14">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-071**](http://go.microsoft.com/fwlink/?linkid=202013)
</td>
<td style="border:1px solid black;">
[**MS10-075**](http://go.microsoft.com/fwlink/?linkid=201722)
</td>
<td style="border:1px solid black;">
[**MS10-076**](http://go.microsoft.com/fwlink/?linkid=194560)
</td>
<td style="border:1px solid black;">
[**MS10-077**](http://go.microsoft.com/fwlink/?linkid=201704)
</td>
<td style="border:1px solid black;">
[**MS10-073**](http://go.microsoft.com/fwlink/?linkid=201093)
</td>
<td style="border:1px solid black;">
[**MS10-078**](http://go.microsoft.com/fwlink/?linkid=201084)
</td>
<td style="border:1px solid black;">
[**MS10-081**](http://go.microsoft.com/fwlink/?linkid=201086)
</td>
<td style="border:1px solid black;">
[**MS10-082**](http://go.microsoft.com/fwlink/?linkid=201098)
</td>
<td style="border:1px solid black;">
[**MS10-083**](http://go.microsoft.com/fwlink/?linkid=190553)
</td>
<td style="border:1px solid black;">
[**MS10-084**](http://go.microsoft.com/fwlink/?linkid=201720)
</td>
<td style="border:1px solid black;">
[**MS10-085**](http://go.microsoft.com/fwlink/?linkid=201705)
</td>
<td style="border:1px solid black;">
[**MS10-074**](http://go.microsoft.com/fwlink/?linkid=201703)
</td>
<td style="border:1px solid black;">
[**MS10-086**](http://go.microsoft.com/fwlink/?linkid=201721)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=f64af3cd-591d-4212-94a0-3bc9a4d9782a)  
(Importante)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=fbcf0e65-c9f4-47f8-b4fc-ae46a66ab339)  
(Importante)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=9af37f62-5585-4ff5-9dd3-3fa0b148ae08)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7b240b65-f3ca-465c-a606-b561999c1977)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8ef4378e-21ff-4290-96ba-e00a60f372d1)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f94763e7-b1db-4043-aa79-d5be1a42307d)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3b2eb449-ad55-4dfb-a3c5-aac767de6f45)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 10](http://www.microsoft.com/downloads/details.aspx?familyid=5479fd20-50d1-447a-8555-a98ce0723f71)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=13c08ec0-53ae-4b85-b669-8c88f6089259)  
(KB979687)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b31e18b0-da9f-4b3b-82c6-603e08b3b241)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d220f04e-9dbb-4b6d-924a-23065b48b8b6)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=12c3b950-b955-4820-9b4c-5206deb0cd3e)  
(Importante)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=59a715a5-10ff-40e6-88e0-096c9b640799)  
(Importante)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c8052f0c-e62c-46c4-bb59-d515fa388ea8)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=70c9e826-b80b-4a20-82d2-8e52e5cca839)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)<sup>[1]</sup>
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4a95c74b-cfd8-45b5-8887-777429d21745)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6fca5cab-7e11-4911-a6a8-f73f113b2963)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=54fc4bc6-f46c-447c-8307-afd8338e7ffb)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 10](http://www.microsoft.com/downloads/details.aspx?familyid=a9515e69-c147-4810-8c5a-6cb94c398a95)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=02519f9e-e1c5-48a1-8420-01898c45ec01)  
(KB979687)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1d73f0f1-6ec8-4304-a20e-345d8b6c225a)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=de908137-33e0-4f23-b32b-cc1bdbcb349c)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=97b3f6dc-8df5-4c93-aaee-f191498c7ce4)  
(Importante)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ba194be9-24f9-4c62-9aa9-9e98c81ddba1)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=bd5878bb-f565-4303-afed-4e17b44a02f2)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)<sup>[1]</sup>
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=21637cd8-c75c-43b4-9948-be7be54af6bf)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=e8f297e2-0dfd-421a-b598-a78199ad6baa)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=64f5c311-d74a-4665-9775-ac91c6885ed3)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=1064bccb-3ce6-4a72-8788-56d8021bca91)  
(KB979687)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=8fad4f77-7c89-4684-b957-9c00ced248d3)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=873dea9d-44cc-4e16-8a6d-dca678ce3a80)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="14">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-071**](http://go.microsoft.com/fwlink/?linkid=202013)
</td>
<td style="border:1px solid black;">
[**MS10-075**](http://go.microsoft.com/fwlink/?linkid=201722)
</td>
<td style="border:1px solid black;">
[**MS10-076**](http://go.microsoft.com/fwlink/?linkid=194560)
</td>
<td style="border:1px solid black;">
[**MS10-077**](http://go.microsoft.com/fwlink/?linkid=201704)
</td>
<td style="border:1px solid black;">
[**MS10-073**](http://go.microsoft.com/fwlink/?linkid=201093)
</td>
<td style="border:1px solid black;">
[**MS10-078**](http://go.microsoft.com/fwlink/?linkid=201084)
</td>
<td style="border:1px solid black;">
[**MS10-081**](http://go.microsoft.com/fwlink/?linkid=201086)
</td>
<td style="border:1px solid black;">
[**MS10-082**](http://go.microsoft.com/fwlink/?linkid=201098)
</td>
<td style="border:1px solid black;">
[**MS10-083**](http://go.microsoft.com/fwlink/?linkid=190553)
</td>
<td style="border:1px solid black;">
[**MS10-084**](http://go.microsoft.com/fwlink/?linkid=201720)
</td>
<td style="border:1px solid black;">
[**MS10-085**](http://go.microsoft.com/fwlink/?linkid=201705)
</td>
<td style="border:1px solid black;">
[**MS10-074**](http://go.microsoft.com/fwlink/?linkid=201703)
</td>
<td style="border:1px solid black;">
[**MS10-086**](http://go.microsoft.com/fwlink/?linkid=201721)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=4f656d16-2a7e-4d18-8a5a-ebf8a1a10e2b)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=191c8388-f1ef-45b6-9f07-d5654a973abe)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4a481825-d9ad-4a7c-aa89-f40fb9651961)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=29c4afb1-227d-4572-b136-a78ef7e1df77)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e9f735ab-d995-4209-b2dc-197f53fdee0f)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=95ceafc6-e37a-4c77-b16e-c9c94a7d89bd)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=95e24a63-d21a-4756-a16e-17a977595396)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=80c99d69-4b97-4af2-8f8e-f3b300a89a5a)<sup>[1]</sup>
(KB979687)  
(Importante)  
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dff92449-22ad-49a8-8b28-5295a8af5b8b)<sup>[1]</sup>
(KB979688)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4af2f6e6-6905-498c-bfba-a565976b3365)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=75ca4e2c-b0ae-46f4-a0fc-616510c41a55)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=02c6260c-8e21-401a-992d-884c6ff7141d)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=adeb3036-62fa-4a29-b82f-ff4a50c05996)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=15d8f81b-97b0-43d9-b218-1cdd759cb2ec)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=880ad9a0-6ddd-41f4-a608-171d59a31b6a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)<sup>[1]</sup>
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=738c8f70-b46a-4a59-bea6-078074a9c4db)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dfe7cd18-53a3-433e-9a33-bd96b04b4deb)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=277151a2-b74f-4da6-8203-e774af75e44c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b73951f2-a7eb-4c7c-bf60-fdcfee83574f)<sup>[1]</sup>
(KB979687)  
(Importante)  
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c9d2261f-bd9a-4495-a2f1-3c3b2208b01e)<sup>[1]</sup>
(KB979688)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8c56ba29-b2a8-47a8-a605-4c54c0a7fa7c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0a12ff95-ea5c-4c48-96c5-9494eb8f9f0d)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="14">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-071**](http://go.microsoft.com/fwlink/?linkid=202013)
</td>
<td style="border:1px solid black;">
[**MS10-075**](http://go.microsoft.com/fwlink/?linkid=201722)
</td>
<td style="border:1px solid black;">
[**MS10-076**](http://go.microsoft.com/fwlink/?linkid=194560)
</td>
<td style="border:1px solid black;">
[**MS10-077**](http://go.microsoft.com/fwlink/?linkid=201704)
</td>
<td style="border:1px solid black;">
[**MS10-073**](http://go.microsoft.com/fwlink/?linkid=201093)
</td>
<td style="border:1px solid black;">
[**MS10-078**](http://go.microsoft.com/fwlink/?linkid=201084)
</td>
<td style="border:1px solid black;">
[**MS10-081**](http://go.microsoft.com/fwlink/?linkid=201086)
</td>
<td style="border:1px solid black;">
[**MS10-082**](http://go.microsoft.com/fwlink/?linkid=201098)
</td>
<td style="border:1px solid black;">
[**MS10-083**](http://go.microsoft.com/fwlink/?linkid=190553)
</td>
<td style="border:1px solid black;">
[**MS10-084**](http://go.microsoft.com/fwlink/?linkid=201720)
</td>
<td style="border:1px solid black;">
[**MS10-085**](http://go.microsoft.com/fwlink/?linkid=201705)
</td>
<td style="border:1px solid black;">
[**MS10-074**](http://go.microsoft.com/fwlink/?linkid=201703)
</td>
<td style="border:1px solid black;">
[**MS10-086**](http://go.microsoft.com/fwlink/?linkid=201721)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=0107dd61-7b3e-4fcf-9743-d9ae594b2278)\*\*  
(Importante)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ea5b7c86-3878-43a9-a4bc-12e04bfbd06e)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=50386655-982e-4126-8261-2c972d695bbd)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4dff0ebe-ccba-4675-98ca-9903f1cb6763)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d5f079b0-d8e1-47fe-b9dd-41eeb463a93c)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=67eb3a70-9ca7-4184-b9fe-cc3e66b1bf36)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fd507e7a-4516-474b-8f33-7fa8fd2afa6d)\*\*<sup>[1]</sup>
(KB979687)  
(Importante)  
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4a8c2358-36ea-4757-abfc-5bffcad0a872)\*\*<sup>[1]</sup>
(KB979688)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0566915f-2a1b-474b-b5f1-e1a9cedd836a)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=952b3594-d980-45b1-8fa3-49403784afbf)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=139f3bb2-eefc-4cf4-9c15-de78f5a736c1)\*\*  
(Importante)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=71ecdb27-46aa-4db1-b86a-3268cda88632)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a6b2ae1d-9225-4495-8560-97860f87d7b4)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)\*\*<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=da7905a9-9587-4184-8fca-ecc636a3b67e)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8e88d9c5-eb57-4d39-a880-a478c5f286da)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 11](http://www.microsoft.com/downloads/details.aspx?familyid=33a06f0e-81ab-445a-bc89-14350ebfe688)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a x64 e Windows Server 2008 per sistemi a x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b5f53faf-61e2-4b4e-8b85-c5e8f38e5c30)\*\*<sup>[1]</sup>
(KB979687)  
(Importante)  
[Windows Server 2008 per sistemi a x64 e Windows Server 2008 per sistemi a x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=612ab78c-1ff1-45d2-96cc-ae831fb0a563)\*\*<sup>[1]</sup>
(KB979688)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=74ac2233-02ec-454c-8aa0-64b18071e16a)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=21128031-d935-4e2d-b001-c502a2d6022c)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=1a971fb2-7dc4-43bf-ae25-3a420bb1acf9)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a4e38a77-3835-47b3-bd86-6c039169abf5)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b9096046-8c7a-450c-b8c5-6e9fb001e6cd)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=76e46d08-22d9-4a0c-82cd-d2753d07efe6)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5efe55b0-d34d-4f00-98b2-cc0e9807a8b9)<sup>[1]</sup>
(KB979687)  
(Importante)  
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d30368cb-c6e8-403e-aaf6-425f96b6211e)<sup>[1]</sup>
(KB979688)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2fff281a-2221-42a3-a2b7-07b5c5e66ae7)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2eca0c38-73f5-4f83-ab62-97f979716a1d)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="14">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-071**](http://go.microsoft.com/fwlink/?linkid=202013)
</td>
<td style="border:1px solid black;">
[**MS10-075**](http://go.microsoft.com/fwlink/?linkid=201722)
</td>
<td style="border:1px solid black;">
[**MS10-076**](http://go.microsoft.com/fwlink/?linkid=194560)
</td>
<td style="border:1px solid black;">
[**MS10-077**](http://go.microsoft.com/fwlink/?linkid=201704)
</td>
<td style="border:1px solid black;">
[**MS10-073**](http://go.microsoft.com/fwlink/?linkid=201093)
</td>
<td style="border:1px solid black;">
[**MS10-078**](http://go.microsoft.com/fwlink/?linkid=201084)
</td>
<td style="border:1px solid black;">
[**MS10-081**](http://go.microsoft.com/fwlink/?linkid=201086)
</td>
<td style="border:1px solid black;">
[**MS10-082**](http://go.microsoft.com/fwlink/?linkid=201098)
</td>
<td style="border:1px solid black;">
[**MS10-083**](http://go.microsoft.com/fwlink/?linkid=190553)
</td>
<td style="border:1px solid black;">
[**MS10-084**](http://go.microsoft.com/fwlink/?linkid=201720)
</td>
<td style="border:1px solid black;">
[**MS10-085**](http://go.microsoft.com/fwlink/?linkid=201705)
</td>
<td style="border:1px solid black;">
[**MS10-074**](http://go.microsoft.com/fwlink/?linkid=201703)
</td>
<td style="border:1px solid black;">
[**MS10-086**](http://go.microsoft.com/fwlink/?linkid=201721)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[Nessuno](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi 32-bit
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=6595770f-e580-4613-a83a-3b8ee4cc30f1)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=1a3953fe-ba48-4980-a65d-74e3b756d53c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=f6cae091-e9f1-48e9-a035-4346b9c6fec6)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=b5b31499-d242-42bf-ac78-b787ffb4d602)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=bdff9057-381a-44e8-b093-84f07d8d7e3c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 12](http://www.microsoft.com/downloads/details.aspx?familyid=59a2ef36-9c32-488b-b5b1-30b5bcd83358)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=b0d46bc3-24db-4207-b6fc-46b8cc64f075)<sup>[1]</sup>
(KB979687)  
(Importante)  
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=4a422192-d7fa-47e5-9661-2c65eaefaf62)<sup>[1]</sup>
(KB979688)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=d7a08a66-08b4-421c-afad-f2f367d4a9f0)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=f09fbc23-cb6b-4525-8e41-8c14e8d03de9)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ffe364ee-e2ae-466c-b727-14b1a976a860)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=5759d2a3-7f35-4fa1-8ab4-17145839fa26)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=35882477-4e0a-4783-a4b4-0f1ea3398360)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)<sup>[1]</sup>
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=c47e8b74-8cfe-42d9-9362-8786687c88ad)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=35a2b1a9-6dd6-4a7e-bc0a-b4fcffa06b28)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 12](http://www.microsoft.com/downloads/details.aspx?familyid=00176d56-8a93-4780-96fc-a7ab715e7291)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=2de197c0-6d9e-460e-9509-f337fac8ee85)<sup>[1]</sup>
(KB979687)  
(Importante)  
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=03665687-8fd4-4afd-ac33-5f6824f51df8)<sup>[1]</sup>
(KB979688)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=50d27c23-5f69-40fa-b517-32c245009467)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=abc24826-b83a-4e01-be68-8e3a73c10494)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)<sup>[1]</sup>
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="14">
Windows Server 2008 R2
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-071**](http://go.microsoft.com/fwlink/?linkid=202013)
</td>
<td style="border:1px solid black;">
[**MS10-075**](http://go.microsoft.com/fwlink/?linkid=201722)
</td>
<td style="border:1px solid black;">
[**MS10-076**](http://go.microsoft.com/fwlink/?linkid=194560)
</td>
<td style="border:1px solid black;">
[**MS10-077**](http://go.microsoft.com/fwlink/?linkid=201704)
</td>
<td style="border:1px solid black;">
[**MS10-073**](http://go.microsoft.com/fwlink/?linkid=201093)
</td>
<td style="border:1px solid black;">
[**MS10-078**](http://go.microsoft.com/fwlink/?linkid=201084)
</td>
<td style="border:1px solid black;">
[**MS10-081**](http://go.microsoft.com/fwlink/?linkid=201086)
</td>
<td style="border:1px solid black;">
[**MS10-082**](http://go.microsoft.com/fwlink/?linkid=201098)
</td>
<td style="border:1px solid black;">
[**MS10-083**](http://go.microsoft.com/fwlink/?linkid=190553)
</td>
<td style="border:1px solid black;">
[**MS10-084**](http://go.microsoft.com/fwlink/?linkid=201720)
</td>
<td style="border:1px solid black;">
[**MS10-085**](http://go.microsoft.com/fwlink/?linkid=201705)
</td>
<td style="border:1px solid black;">
[**MS10-074**](http://go.microsoft.com/fwlink/?linkid=201703)
</td>
<td style="border:1px solid black;">
[**MS10-086**](http://go.microsoft.com/fwlink/?linkid=201721)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d8b563ce-5db1-4490-8a63-44833d55152b)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=b060c516-233a-4e1e-9237-698420e97b2f)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=98e0c6ac-c30b-4d39-8ed9-1fe69e7644e5)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=25fff010-3abc-45e6-979e-21d2bae49418)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Media Player 12](http://www.microsoft.com/downloads/details.aspx?familyid=4cf0e3b1-4b72-4f99-b716-2489ea42ed72)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=70622d35-4877-4cbb-bdbf-7648dc1ea8ed)\*\*<sup>[1]</sup>
(KB979687)  
(Importante)  
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=1c2ff242-65e3-4d47-bfca-4db30f809ed8)\*\*<sup>[1]</sup>
(KB979688)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=d356af2f-eadf-4bf2-82d1-efa0d01ac92d)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=e4d27aa6-9739-4e41-9536-5f0b8d26503c)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=1de12fdf-b439-4020-9313-a193d47dcfb2)\*  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)\*\*<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=bbaa9f46-8fc7-4c44-b38c-dc3d5210f63d)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=0ead2ed9-8b2f-496e-b7d1-3ad2b04be5cc)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=44080c75-036e-4bd0-914a-74ab72189ee3)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=d0742526-b5ec-4658-82f1-c3680f33a790)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=3cec2b70-f694-4c0d-bf82-96a4fd50675d)<sup>[1]</sup>
(KB979687)  
(Importante)  
[Windows Server 2008 R2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=f478020b-0305-47d5-bcb2-0758f292db29)<sup>[1]</sup>
(KB979688)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=334d39e6-8e4c-4e83-94c1-1db3d636e865)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=c1634278-5598-45e0-81c6-f18fb5ba54cf)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=1c607c7d-6144-4a39-beea-a31b62085047)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 4.0](http://www.microsoft.com/downloads/details.aspx?familyid=bbc22169-996f-48d1-beed-0ee0dc4fbf4f)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Nota per MS10-077**

<sup>[1]</sup>**.NET Framework 4.0 e .NET Framework 4.0 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4.0 e .NET Framework 4.0 Client Profile. .Net NET Framework 4.0 Client Profile è un sottoinsieme di .NET Framework 4.0. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4.0 sia .NET Framework 4.0 Client Profile. Per ulteriori informazioni, consultare l'articolo di MSDN, Installare .NET Framework.

**Nota per MS10-083**

<sup>[1]</sup>Nei casi in cui sono disponibili entrambi i pacchetti di aggiornamento per la protezione KB979687 e KB979688 per lo stesso sistema operativo, è necessario installare entrambi per essere protetti dalle vulnerabilità descritte nel bollettino MS10-083.

**Note per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server** **Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="3">
Applicazioni e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-079**](http://go.microsoft.com/fwlink/?linkid=201696)
</td>
<td style="border:1px solid black;">
[**MS10-080**](http://go.microsoft.com/fwlink/?linkid=200529)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Word 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f22d10fd-cb12-43e8-88d5-2116cf4317c4)  
(KB2328360)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=ea859881-2cc5-407b-a394-5d00c5d9fd97)  
(KB2345017)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Word 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=172f3743-cdfa-42d7-aeb4-27ba0e4139f7)  
(KB2344911)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=3d9a00b8-0f80-4d36-b92a-89b61350fb36)  
(KB2344893)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Word 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ccad4871-32f2-4982-a23e-9b5824397615)<sup>[1]</sup>
(KB2344993)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dc9b9af5-50b0-4a07-8923-a30fd5548760)<sup>[1]</sup>
(KB2345035)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Word 2010 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=6c3b8690-e568-42ed-a858-0cbdd5ea3669)  
(KB2345000)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Word 2010 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=f31a1f9b-02df-4a85-a7d1-7d1e31baa30f)  
(KB2345000)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Office per Mac
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-079**](http://go.microsoft.com/fwlink/?linkid=201696)
</td>
<td style="border:1px solid black;">
[**MS10-080**](http://go.microsoft.com/fwlink/?linkid=200529)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=464965fa-971a-49dd-bcee-c4d91fac86a9)  
(KB2422343)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=464965fa-971a-49dd-bcee-c4d91fac86a9)  
(KB2422343)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=abd05074-8ffc-41a4-a2f3-1d8047574552)  
(KB2422352)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=abd05074-8ffc-41a4-a2f3-1d8047574552)  
(KB2422352)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Convertitore file in formato XML aperto per Mac
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=5c759c46-ead3-44ea-b7c8-a308b3140d2e)  
(KB2422398)  
(Importante)
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=5c759c46-ead3-44ea-b7c8-a308b3140d2e)  
(KB2422398)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Altro software Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-079**](http://go.microsoft.com/fwlink/?linkid=201696)
</td>
<td style="border:1px solid black;">
[**MS10-080**](http://go.microsoft.com/fwlink/?linkid=200529)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Word Viewer
</td>
<td style="border:1px solid black;">
[Microsoft Word Viewer](http://www.microsoft.com/downloads/details.aspx?familyid=1cb5ab02-074d-4877-b378-7058959705ae)  
(KB2345009)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Excel Viewer
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Excel Viewer Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a833a94a-2dc0-4864-9c14-e196dc54c5a7)  
(KB2345088)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=553d28ae-c352-4985-97c3-e5038414be45)  
(KB2345043)  
(Importante)
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7391ec2f-12c9-483c-91d8-e3ec5754da1c)  
(KB2344875)  
(Importante)
</td>
</tr>
</table>
 
**Note per MS10-079**

<sup>[1]</sup>Per Microsoft Word 2007 Service Pack 2, oltre al pacchetto di aggiornamento per la protezione KB2344993, i clienti devono installare anche l'aggiornamento per la protezione del Pacchetto di compatibilità di Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2 (KB2345043) per essere protetti dalle vulnerabilità descritte nel bollettino MS10-079.

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota per MS10-080**

<sup>[1]</sup>Per Microsoft Office Excel 2007 Service Pack 2, oltre al pacchetto di aggiornamento per la protezione KB2345035, i clienti devono installare anche l'aggiornamento per la protezione del Pacchetto di compatibilità di Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2 (KB2344875) per essere protetti dalle vulnerabilità descritte nel bollettino MS10-080.

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="3">
Microsoft SharePoint Services e Microsoft SharePoint Foundation
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-072**](http://go.microsoft.com/fwlink/?linkid=202016)
</td>
<td style="border:1px solid black;">
[**MS10-079**](http://go.microsoft.com/fwlink/?linkid=201696)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0
</td>
<td style="border:1px solid black;">
[Microsoft Windows SharePoint Services 3.0 Service Pack 2 (versioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=12fd97a9-6fb8-4b65-a497-a56587f114e1)  
(KB2345304)  
(Importante)  
[Microsoft Windows SharePoint Services 3.0 Service Pack 2 (versioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=58d1e91d-a037-485d-a6d9-80fbf403b108)  
(KB2345304)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Foundation 2010
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Foundation 2010](http://www.microsoft.com/downloads/details.aspx?familyid=fc146fcb-c2cb-4860-a0cd-4b09fa3f44eb)  
(KB2345322)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Microsoft SharePoint e Microsoft Groove Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-072**](http://go.microsoft.com/fwlink/?linkid=202016)
</td>
<td style="border:1px solid black;">
[**MS10-079**](http://go.microsoft.com/fwlink/?linkid=201696)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office SharePoint Server 2007
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2007 Service Pack 2 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=aee3f2de-ccf3-4d32-b468-eede4e8afcd4)<sup>[1]</sup>
(KB2345212)  
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 2 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=e5e60751-242a-4fdb-9852-6d94050d3d0e)<sup>[1]</sup>
(KB2345212)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Groove Server 2010
</td>
<td style="border:1px solid black;">
[Microsoft Groove Server 2010](http://www.microsoft.com/downloads/details.aspx?familyid=e032aef8-dd30-41c6-99bb-8cf0491451cc)  
(KB2346298)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Office Web Apps
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-072**](http://go.microsoft.com/fwlink/?linkid=202016)
</td>
<td style="border:1px solid black;">
[**MS10-079**](http://go.microsoft.com/fwlink/?linkid=201696)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Web Apps
</td>
<td style="border:1px solid black;">
[Microsoft Office Web Apps](http://www.microsoft.com/downloads/details.aspx?familyid=8fb56eb9-9601-4c1e-905a-9fe4802b2c8d)  
(KB2346411)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Web Apps](http://www.microsoft.com/downloads/details.aspx?familyid=8fb56eb9-9601-4c1e-905a-9fe4802b2c8d)<sup>[2]</sup>
(KB2346411)  
(Importante)  
[Microsoft Word Web App](http://www.microsoft.com/downloads/details.aspx?familyid=13b24264-ec3d-44e8-81e3-82ac767defd3)<sup>[2]</sup>
(KB2345015)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS10-072**

<sup>[1]</sup>Per le edizioni supportate di Microsoft Office SharePoint Server 2007, oltre al pacchetto di aggiornamento per la protezione KB2345212, i clienti devono installare anche l'aggiornamento per la protezione di Microsoft Windows SharePoint Services 3.0 (KB2345304) per essere protetti dalle vulnerabilità descritte nel bollettino MS10-072.

**Note per MS10-079**

<sup>[2]</sup>Per Microsoft Office Web Apps, i clienti devono installare sia l'aggiornamento per la protezione KB2346411 che l'aggiornamento per la protezione KB2345015 per essere protetti dalle vulnerabilità descritte nel bollettino MS10-079.

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208(en-us).aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/it-it/library/bb735860(en-us).aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://go.microsoft.com/fwlink/?linkid=22939). Gli utenti di SMS 2.0 possono inoltre utilizzare Security Update Inventory Tool per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/systemcenter/configmgr/default.mspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/sms/bb676800.aspx)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. I componenti del programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consentono di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/it-it/windowsserver/bb456965.aspx). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://www.microsoft.com/security/msrc/collaboration/mapppartners.aspx).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   [Sirdarckcat](http://www.sirdarckcat.net/) di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS10-071
-   Mario Heiderich per aver segnalato un problema descritto nel bollettino MS10-071
-   Takehiro Takahashi di [IBM ISS X-Force](http://www.iss.net/) per aver segnalato un problema descritto nel bollettino MS10-071
-   [Peter Vreugdenhil](http://vreugdenhilresearch.nl), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS10-071
-   Damián Frizza di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato un problema descritto nel bollettino MS10-071
-   Aldwin Saugere e Radoslav Vasilev di [Cigital](http://www.cigital.com/) per aver segnalato un problema descritto nel bollettino MS10-071
-   Rodrigo Rubira Branco di [Check Point](http://www.checkpoint.com/) IPS Research Center per aver segnalato un problema descritto nel bollettino MS10-071
-   [Sirdarckcat](http://www.sirdarckcat.net/) di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS10-072
-   Mario Heiderich per aver segnalato un problema descritto nel bollettino MS10-072
-   Sergey Golovanov, Alexander Gostev, Maxim Golovkin e Alexey Monastyrsky di [Kaspersky Lab](http://www.kaspersky.com) e Vitaly Kiktenko e Alexander Saprykin di [Design and Test Lab](http://www.dnt-lab.com) per aver segnalato un problema descritto nel bollettino MS10-073
-   Eric Chien di [Symantec](http://www.symantec.com/index.jsp) per aver segnalato un problema descritto nel bollettino MS10-073
-   Tarjei Mandt di [Norman](http://www.norman.com) per aver collaborato con noi allo studio di un problema descritto nel bollettino MS10-073
-   Carsten H. Eiram di [Secunia](http://secunia.com/) per aver collaborato con noi su un problema descritto nel bollettino MS10-074
-   Oleksandr Mirosh, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS10-075
-   Sebastian Apelt, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS10-076
-   Ivan Fratric di [iSIGHT Partners Global Vulnerability Partnership](https://gvp.isightpartners.com/) per aver segnalato un problema descritto nel bollettino MS10-076
-   Jeroen Frijters di [Sumatra](http://www.sumatra.nl/) per aver segnalato un problema descritto nel bollettino MS10-077
-   Sebastian Apelt di [Siberias](http://www.siberas.de/) per aver segnalato un problema descritto nel bollettino MS10-078
-   Diego Juarez di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato un problema descritto nel bollettino MS10-078
-   Chaouki Bekrar del [VUPEN Vulnerability Research Team](http://www.vupen.com/) per aver segnalato dieci problemi descritti nel bollettino MS10-079
-   Nicolas Joly del [VUPEN Vulnerability Research Team](http://www.vupen.com/) per aver segnalato un problema descritto nel bollettino MS10-079
-   Alin Rad Pop di [Secunia Research](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS10-079
-   Alin Rad Pop di [Secunia](http://secunia.com/) per aver segnalato due problemi descritti nel bollettino MS10-080
-   Chaouki Bekrar del [VUPEN Vulnerability Research Team](http://www.vupen.com/) per aver segnalato dieci problemi descritti nel bollettino MS10-080
-   Omair per aver segnalato un problema descritto nel bollettino MS10-080
-   Carsten H. Eiram di [Secunia](http://secunia.com/) per aver segnalato due problemi descritti nel bollettino MS10-080
-   Krystian Kloskowski (h07), in collaborazione con [Secunia](http://secunia.com/), per aver segnalato un problema descritto nel bollettino MS10-081
-   SkyLined di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS10-082
-   HD Moore di [Rapid7](http://www.rapid7.com/) per aver segnalato un problema descritto nel bollettino MS10-083
-   David Dewey di [IBM ISS X-Force](http://www.iss.net/) e Ryan Smith di [Accuvant](http://www.accuvant.com/), in precedenza collaboratore di [VeriSign iDefense Labs](http://labs.idefense.com/), per aver collaborato con noi alle modifiche al sistema di difesa contenute nel bollettino MS10-083
-   Il team di [Mu Test Suite](http://www.mudynamics.com/products/mu-test-suite.html) di [Mu Dynamics](http://www.mudynamics.com/) per aver segnalato un problema descritto nel bollettino MS10-085

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (12 ottobre 2010): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (13 ottobre 2010): Per MS10-077, il livello di gravità della vulnerabilità per Windows Server 2008 e Windows Server 2008 R2 è stato modificato in Importante. Inoltre, per MS10-082, è stato corretto il collegamento per il download per Windows Media Player 11 in Windows XP Professional x64 Edition Service Pack 2.
-   V2.0 (18 ottobre 2010): Per MS10-085, la descrizione del Riepilogo è stata modificata per chiarire che la vulnerabilità può essere sfruttata sui sistemi interessati configurati per la ricezione del traffico di rete SSL. La modifica è esclusivamente informativa. I clienti che hanno già aggiornato i propri sistemi, inclusi i clienti che hanno attivato l'aggiornamento automatico, non devono eseguire ulteriori operazioni. È possibile che i clienti che non hanno già installato questo aggiornamento debbano rivalutare la necessità di installarlo sui propri sistemi.
-   V3.0 (14 dicembre 2010): Questo riepilogo dei bollettini è stato rivisto per comunicare che: Per MS10-077, sono disponibili i nuovi pacchetti di aggiornamento per .NET Framework 4.0 per correggere un problema nell'installazione che potrebbe impedire la corretta installazione di altri aggiornamenti e/o prodotti. I clienti che hanno già aggiornato i propri sistemi non devono eseguire ulteriori operazioni. Per MS10-083, un aggiornamento aggiuntivo per Windows Vista Service Pack 2 (KB979688) e Windows Server 2008 Service Pack 2 (KB979688) per gli utenti che ha installato Windows Search 4.0 su Windows Vista Service Pack 1 o Windows Server 2008, che hanno installato poi l'aggiornamento per la protezione offerto in KB2405882 e che hanno poi eseguito la migrazione a Windows Vista Service Pack 2 o a Windows Server 2008 Service Pack 2. Il nuovo aggiornamento è disponibile dall'[articolo della Microsoft Knowledge Base 2405882](http://support.microsoft.com/kb/2405882).
-   V4.0 (22 febbraio 2011): Per MS10-077, una modifica di rilevamento offre ora i pacchetti di aggiornamento .NET Framework 4.0 di Microsoft ai clienti che installano .NET Framework 4.0 di Microsoft dopo aver installato Windows 7 per i sistemi x64 Service Pack 1, Windows Server 2008 R2 per i sistemi x64 Service Pack 1 o Windows Server 2008 R2 per i sistemi Itanium Service Pack 1. I clienti che con successo hanno aggiornato già i loro sistemi non devono effettuare alcuna operazione.
-   V4.1 (26 ottobre 2011): per MS10-077 è stata corretta l'applicabilità dell'installazione Server Core per .NET Framework 4 in Windows Server 2008 R2 per i sistemi x64.

*Built at 2014-04-18T01:50:00Z-07:00*
