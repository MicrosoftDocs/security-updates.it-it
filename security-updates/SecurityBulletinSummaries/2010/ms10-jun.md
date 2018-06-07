---
TOCTitle: 'MS10-JUN'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Giugno 2010'
ms:assetid: 'ms10-jun'
ms:contentKeyID: 61240048
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms10-jun(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Giugno 2010
================================================================

Data di pubblicazione: martedì 8 giugno 2010 | Aggiornamento: martedì 13 settembre 2011

**Versione:** 2.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a giugno 2010.

Con il rilascio dei bollettini del mese di giugno 2010, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 3 giugno 2010. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/advance).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://go.microsoft.com/fwlink/?linkid=21163).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 9 giugno 2010 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di giugno](https://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032427727&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

Riepiloghi
----------

<span></span>
La seguente tabella riassume i bollettini sulla sicurezza di questo mese in ordine di gravità.

Per ulteriori informazioni sul software interessato, vedere la sezione successiva, **Software interessato e percorsi per il download**.

 
<table style="border:1px solid black;">
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=191065">MS10-033</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nella decompressione dei file multimediali possono consentire l'esecuzione di codice in modalità remota (979902)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Windows. Tali vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file multimediale appositamente predisposto o se riceve un flusso di contenuti appositamente predisposto da un sito Web o da un'applicazione che fornisce contenuti Web. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=185159">MS10-034</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione dei kill bit ActiveX (980195)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente per il software di Microsoft. Questo aggiornamento per la protezione è considerato di livello critico per tutte le edizioni supportate di Microsoft Windows 2000, Windows XP, Windows Vista e Windows 7 e di livello moderato per tutte le edizioni supportate di Windows Server 2003, Windows Server 2008 e Windows Server 2008 R2.<br />
<br />
Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta che crea un'istanza di un controllo ActiveX specifica con Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. Questo aggiornamento contiene anche i kill bit per quattro controlli ActiveX di terze parti.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=190898">MS10-035</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (982381)</strong><br />
<br />
Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente e una vulnerabilità divulgata pubblicamente relative a Internet Explorer. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=184917">MS10-032</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver di Windows in modalità kernel possono consentire l'acquisizione di privilegi più elevati (979559)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità divulgate pubblicamente e una vulnerabilità segnalata privatamente nei driver di Windows in modalità kernel. Le vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente visualizza un contenuto reso con un carattere TrueType appositamente predisposto.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=190554">MS10-036</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nella convalida COM in Microsoft Office può consentire l'esecuzione di codice in modalità remota (983235)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nella convalida COM in Microsoft Office. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file Excel, Word, Visio, Publisher o PowerPoint appositamente predisposto con una versione interessata di Microsoft Office. Non è possibile sfruttare la vulnerabilità automaticamente per posta elettronica. L'attacco è possibile solo se l'utente apre un allegato a un messaggio di posta elettronica.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=190508">MS10-037</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel driver OpenType CFF (Compact Font Format) può consentire l'acquisizione di privilegi più elevati (980218)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel driver OpenType CFF (Compact Font Format). La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente visualizza un contenuto reso con un carattere CFF appositamente predisposto. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale. La vulnerabilità non può essere sfruttata in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=191053">MS10-038</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Excel possono consentire l'esecuzione di codice in modalità remota ((2027452)</strong><br />
<br />
Questo aggiornamento per la protezione risolve quattordici vulnerabilità segnalate privatamente in Microsoft Office. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota durante l'apertura di un file di Excel appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=191905">MS10-039</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft SharePoint possono consentire l'acquisizione di privilegi più elevati (2028554)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e due vulnerabilità segnalate privatamente in Microsoft SharePoint. La vulnerabilità più grave può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato riesce a indurre un utente di un determinato sito SharePoint a fare clic su un collegamento appositamente predisposto.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office, Software dei server Microsoft</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=191788">MS10-040</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Internet Information Services può consentire l'esecuzione di codice in modalità remota (982666)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Internet Information Services (IIS). La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente riceve una richiesta HTTP appositamente predisposta. Sfruttando questa vulnerabilità, un utente malintenzionato può assumere il pieno controllo del sistema interessato.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=185042">MS10-041</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft .NET Framework può consentire alterazioni (981343)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft .NET Framework. La vulnerabilità può consentire la manomissione di contenuto XML firmato senza essere rilevata. Nelle applicazioni personalizzate, l'impatto sulla protezione dipende dalle modaltà con cui il contenuto firmato viene utilizzato nell'applicazione specifica. Gli scenari in cui i messaggi XML firmati vengono trasmessi attraverso un canale protetto (come SSL) non sono interessati da questa vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Alterazione</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Microsoft .NET Framework</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità sono elencate in ordine decrescente sulla base del livello di valutazione del rischio e quindi del codice CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/en-us/security/cc998259.aspx).
  
| ID bollettino                                             | Titolo della vulnerabilità                                                                              | ID CVE                                                                           | Valutazione dell'Exploitability Index                                                                                       | Note fondamentali                                                                                                                                                 |  
|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| [MS10-032](http://go.microsoft.com/fwlink/?linkid=184917) | Vulnerabilità legata alla creazione di una finestra in Win32k                                           | [CVE-2010-0485](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0485) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-039](http://go.microsoft.com/fwlink/?linkid=191905) | Vulnerabilità legata al filtro XSS in Help.aspx                                                         | [CVE-2010-0817](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0817) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Questa vulnerabilità è stata segnalata per la prima volta nell'[advisory Microsoft sulla sicurezza 983438](http://technet.microsoft.com/security/advisory/983438) |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata all'overflow dello stack di oggetti Excel                                          | [CVE-2010-0822](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0822) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata al danneggiamento della memoria nei record di Excel                                | [CVE-2010-0824](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0824) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata al danneggiamento della memoria nei record di Excel                                | [CVE-2010-1245](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1245) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata al danneggiamento della memoria nel server RTD di Excel                            | [CVE-2010-1246](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1246) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata al danneggiamento della memoria in Excel                                           | [CVE-2010-1247](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1247) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata al danneggiamento della memoria di un file HFPicture in Excel                      | [CVE-2010-1248](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1248) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata al danneggiamento della memoria in Excel                                           | [CVE-2010-1249](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1249) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata al danneggiamento della memoria di un file EDG in Excel                            | [CVE-2010-1250](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1250) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata all'oggetto ADO in Excel                                                           | [CVE-2010-1253](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1253) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata alle autorizzazioni di un XML aperto di Office per Mac                             | [CVE-2010-1254](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1254) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-035](http://go.microsoft.com/fwlink/?linkid=190898) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                  | [CVE-2010-1259](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1259) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-035](http://go.microsoft.com/fwlink/?linkid=190898) | Vulnerabilità legata al danneggiamento della memoria                                                    | [CVE-2010-1262](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1262) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-036](http://go.microsoft.com/fwlink/?linkid=190554) | Vulnerabilità legata alla convalida COM                                                                 | [CVE-2010-1263](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1263) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-033](http://go.microsoft.com/fwlink/?linkid=191065) | Vulnerabilità legata alla decompressione di file multimediali                                           | [CVE-2010-1879](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1879) | [**1**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                                                                                         |  
| [MS10-035](http://go.microsoft.com/fwlink/?linkid=190898) | Vulnerabilità del modello di protezione tra domini legata all'intercettazione di informazioni personali | [CVE-2010-0255](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0255) | [**2**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | Questa vulnerabilità è stata segnalata per la prima volta nell'[advisory Microsoft sulla sicurezza 980088](http://technet.microsoft.com/security/advisory/980088) |  
| [MS10-032](http://go.microsoft.com/fwlink/?linkid=184917) | Vulnerabilità legata alla convalida errata di dati in Win32k                                            | [CVE-2010-0484](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0484) | [**2**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                         |  
| [MS10-037](http://go.microsoft.com/fwlink/?linkid=190508) | Vulnerabilità legata al danneggiamento della memoria nei driver dei caratteri OpenType/CFF              | [CVE-2010-0819](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0819) | [**2**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata al danneggiamento della memoria di analisi dei record di Excel                     | [CVE-2010-0821](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0821) | [**2**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata al danneggiamento della memoria in Excel                                           | [CVE-2010-0823](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0823) | [**2**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata al danneggiamento dello stack dei record in Excel                                  | [CVE-2010-1251](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1251) | [**2**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                         |  
| [MS10-038](http://go.microsoft.com/fwlink/?linkid=191053) | Vulnerabilità legata alla variabile stringa in Excel                                                    | [CVE-2010-1252](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1252) | [**2**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                         |  
| [MS10-032](http://go.microsoft.com/fwlink/?linkid=184917) | Vulnerabilità legata all'analisi di un carattere TrueType in Win32k                                     | [CVE-2010-1255](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1255) | [**2**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                         |  
| [MS10-040](http://go.microsoft.com/fwlink/?linkid=191788) | Vulnerabilità legata al danneggiamento della memoria durante l'autenticazione di IIS                    | [CVE-2010-1256](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1256) | [**2**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                         |  
| [MS10-033](http://go.microsoft.com/fwlink/?linkid=191065) | Vulnerabilità legata alla decompressione di file multimediali MJPEG                                     | [CVE-2010-1880](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1880) | [**2**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                         |  
| [MS10-041](http://go.microsoft.com/fwlink/?linkid=185042) | Vulnerabilità legata all'elusione dell'autenticazione del troncamento HMAC della firma XML              | [CVE-2009-0217](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0217) | [**3**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Questa è una vulnerabilità legata allo spoofing ed alla manomissione di dati                                                                                      |  
| [MS10-035](http://go.microsoft.com/fwlink/?linkid=190898) | Vulnerabilità legata all'intercettazione di informazioni personali in toStaticHTML                      | [CVE-2010-1257](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1257) | [**3**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Questa vulnerabilità interessa anche il bollettino [MS10-039](http://go.microsoft.com/fwlink/?linkid=191905)                                                      |  
| [MS10-039](http://go.microsoft.com/fwlink/?linkid=191905) | Vulnerabilità legata all'intercettazione di informazioni personali in toStaticHTML                      | [CVE-2010-1257](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1257) | [**3**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Questa vulnerabilità interessa anche il bollettino [MS10-035](http://go.microsoft.com/fwlink/?linkid=190898)                                                      |  
| [MS10-039](http://go.microsoft.com/fwlink/?linkid=191905) | Vulnerabilità legata ad attacchi di tipo Denial of Service della pagina Guida di SharePoint             | [CVE-2010-1264](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-1264) | [**3**](http://technet.microsoft.com/en-us/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | (Nessuna)                                                                                                                                                         |
  
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
</tr>
<tr>
<th colspan="8">
Microsoft Windows 2000  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-032**](http://go.microsoft.com/fwlink/?linkid=184917)
</td>
<td style="border:1px solid black;">
[**MS10-033**](http://go.microsoft.com/fwlink/?linkid=191065)
</td>
<td style="border:1px solid black;">
[**MS10-034**](http://go.microsoft.com/fwlink/?linkid=185159)
</td>
<td style="border:1px solid black;">
[**MS10-035**](http://go.microsoft.com/fwlink/?linkid=190898)
</td>
<td style="border:1px solid black;">
[**MS10-037**](http://go.microsoft.com/fwlink/?linkid=190508)
</td>
<td style="border:1px solid black;">
[**MS10-040**](http://go.microsoft.com/fwlink/?linkid=191788)
</td>
<td style="border:1px solid black;">
[**MS10-041**](http://go.microsoft.com/fwlink/?linkid=185042)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=60c8579b-1540-40d8-80a0-956edadd63ce)  
(Importante)
</td>
<td style="border:1px solid black;">
[Quartz.dll (DirectShow) (DirectX 9)](http://www.microsoft.com/downloads/details.aspx?familyid=a51c53bd-f9c1-4d53-8ed2-034fd57bc75a)<sup>[1]</sup>
(KB975562)  
(Critico)  
[Windows Media Format Runtime 9](http://www.microsoft.com/downloads/details.aspx?familyid=8417c0ac-bb6d-48f1-8237-77a4bdd8ccb2)<sup>[2]</sup>
(KB978695)  
(Critico)  
[Windows Media Encoder 9 x86](http://www.microsoft.com/downloads/details.aspx?familyid=5b5398c1-5b30-4162-95b6-948d9be103bf)  
(KB979332)  
(Importante)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=1f929739-08a1-4faf-9ccf-5f1f43c5bb9e)  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=d3955983-0079-476e-a488-99713097259c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 5.01 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=0a6c09e5-c655-41a0-a133-78d55267a527)  
(Nessun livello di gravità)<sup>[1]</sup>
[Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e2f27eeb-54be-40be-a00e-72867090b8e7)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=5d645891-31e9-42c4-b12b-eb351473fd0c)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5e55ee58-f00a-4237-bddc-492b63a18b96)  
(KB979906)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=43810ead-1fcc-4a97-ad82-00ee42c27bad)  
(KB979909)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-032**](http://go.microsoft.com/fwlink/?linkid=184917)
</td>
<td style="border:1px solid black;">
[**MS10-033**](http://go.microsoft.com/fwlink/?linkid=191065)
</td>
<td style="border:1px solid black;">
[**MS10-034**](http://go.microsoft.com/fwlink/?linkid=185159)
</td>
<td style="border:1px solid black;">
[**MS10-035**](http://go.microsoft.com/fwlink/?linkid=190898)
</td>
<td style="border:1px solid black;">
[**MS10-037**](http://go.microsoft.com/fwlink/?linkid=190508)
</td>
<td style="border:1px solid black;">
[**MS10-040**](http://go.microsoft.com/fwlink/?linkid=191788)
</td>
<td style="border:1px solid black;">
[**MS10-041**](http://go.microsoft.com/fwlink/?linkid=185042)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2 e Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=023a777a-3d83-4a4e-8029-da8b095b074b)  
(Importante)
</td>
<td style="border:1px solid black;">
[Quartz.dll (DirectShow)](http://www.microsoft.com/downloads/details.aspx?familyid=e77d5af8-e8e0-425c-a809-4cf274e17cc5)  
(KB975562)  
(Critico)  
Solo Windows XP Service Pack 2:  
[Windows Media Format Runtime 9, Windows Media Format Runtime 9.5 e Windows Media Format Runtime 11](http://www.microsoft.com/downloads/details.aspx?familyid=bf8b9b46-ba28-4f48-9dac-6a90b7d592d3)  
(KB978695)  
(Critico)  
Solo Windows XP Service Pack 3:  
[Windows Media Format Runtime 9, Windows Media Format Runtime 9.5 e Windows Media Format Runtime 11](http://www.microsoft.com/downloads/details.aspx?familyid=ebbccd82-c637-4c88-86ea-d39ae713c085)  
(KB978695)  
(Critico)  
[Windows Media Encoder 9 x86](http://www.microsoft.com/downloads/details.aspx?familyid=5b5398c1-5b30-4162-95b6-948d9be103bf)  
(KB979332)  
(Importante)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=55c05cb8-aa6c-460b-9aa7-084842dab280)  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=8c3f2e81-c0ea-494a-a47c-4f8982effb49)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=bfe87761-ed9e-4fec-a393-d7fddb919db4)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=fc02fc7e-ee85-4377-b54c-012fa60a8c9c)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=9cff9aba-7743-4c33-87c7-37d06ed60a21)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b42a17c5-997e-4504-ba5b-bfa62166b460)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Solo Windows XP Media Center Edition 2005:  
[Microsoft .NET Framework 1.0 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=c658c108-abd3-4c24-898d-34d490151394)  
(KB979904)  
(Importante)  
Solo Windows XP Media Center Edition 2005 e Windows XP Tablet PC Edition 2005:  
[Microsoft .NET Framework 1.0 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=c658c108-abd3-4c24-898d-34d490151394)  
(KB979904)  
(Importante)  
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5e55ee58-f00a-4237-bddc-492b63a18b96)  
(KB979906)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=1b41e880-d774-4292-b2aa-2a66568142c9)  
(KB982865)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=43810ead-1fcc-4a97-ad82-00ee42c27bad)  
(KB979909)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8e3aac9d-7747-435f-9678-f621e314e070)  
(Importante)
</td>
<td style="border:1px solid black;">
[Quartz.dll (DirectShow)](http://www.microsoft.com/downloads/details.aspx?familyid=7914fdae-9a7a-4a10-8ce7-c621eb903452)  
(KB975562)  
(Critico)  
[Windows Media Format Runtime 9.5](http://www.microsoft.com/downloads/details.aspx?familyid=b56839e3-e7d3-48da-b90c-d403d8dbeed2)  
(KB978695)  
(Critico)  
[Windows Media Format Runtime 9.5 x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=80006082-55f2-4857-9d2c-276c758b5555)<sup>[3]</sup>
(KB978695)  
(Critico)  
[Windows Media Format Runtime 11](http://www.microsoft.com/downloads/details.aspx?familyid=d2887448-9d3c-472f-a0bd-ab083a65eafc)  
(KB978695)  
(Critico)  
[Windows Media Encoder 9 x86](http://www.microsoft.com/downloads/details.aspx?familyid=94c654f0-f70f-4fbd-84de-797be20fc3b9)  
(KB979332)  
(Importante)  
[Windows Media Encoder 9 x64](http://www.microsoft.com/downloads/details.aspx?familyid=2b7a3cb7-151c-4184-9865-f197ef6ee8e7)  
(KB979332)  
(Importante)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=c110d26e-9a1e-4e47-9ce2-4068f2733a2f)  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f3e462fb-df95-4b79-a8bc-5359c2967503)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=7780af61-a206-49aa-a805-a49bdcbb5419)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=6c7cda29-161e-49b4-976a-c718c0aa11a0)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=37cd7533-ddad-4d0d-85c0-1491308e1ff8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dc835b94-3368-4c1c-8f29-40517c73540e)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5e55ee58-f00a-4237-bddc-492b63a18b96)  
(KB979906)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=1b41e880-d774-4292-b2aa-2a66568142c9)  
(KB982865)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=43810ead-1fcc-4a97-ad82-00ee42c27bad) (KB979909)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-032**](http://go.microsoft.com/fwlink/?linkid=184917)
</td>
<td style="border:1px solid black;">
[**MS10-033**](http://go.microsoft.com/fwlink/?linkid=191065)
</td>
<td style="border:1px solid black;">
[**MS10-034**](http://go.microsoft.com/fwlink/?linkid=185159)
</td>
<td style="border:1px solid black;">
[**MS10-035**](http://go.microsoft.com/fwlink/?linkid=190898)
</td>
<td style="border:1px solid black;">
[**MS10-037**](http://go.microsoft.com/fwlink/?linkid=190508)
</td>
<td style="border:1px solid black;">
[**MS10-040**](http://go.microsoft.com/fwlink/?linkid=191788)
</td>
<td style="border:1px solid black;">
[**MS10-041**](http://go.microsoft.com/fwlink/?linkid=185042)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=79a11dcd-5d88-4d83-beae-6580ef6fc2c0)  
(Importante)
</td>
<td style="border:1px solid black;">
[Quartz.dll (DirectShow)](http://www.microsoft.com/downloads/details.aspx?familyid=fc15c43b-d48f-4872-8f9d-ed973170db9a)  
(KB975562)  
(Critico)  
[Windows Media Format Runtime 9.5](http://www.microsoft.com/downloads/details.aspx?familyid=bb580e94-8c02-46f1-b7f6-e7d4373cb1c5)  
(KB978695)  
(Critico)  
[Windows Media Encoder 9 x86](http://www.microsoft.com/downloads/details.aspx?familyid=5b5398c1-5b30-4162-95b6-948d9be103bf)  
(KB979332)  
(Importante)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=0ddf95ac-dd49-4cb1-b6f6-bd4e987b0f06)  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3c0bd349-aa77-47de-ba1d-1fcc72dcad28)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=bfb9acdb-2d9c-4c22-963c-8b9ce247350f)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=f0187b69-3ed9-494c-89f1-90a35e22078c)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ebab6101-fcf1-4842-b22d-893a20c1c10f)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ca49b5b5-db8e-4ebc-9a3c-b1ace09ac3c0)  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=0761c207-5465-4f42-b61f-bd02efcef27d)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f82e1b73-7f8b-4f4c-8187-4050a11db44c)  
(KB979907)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=1b41e880-d774-4292-b2aa-2a66568142c9)  
(KB982865)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=43810ead-1fcc-4a97-ad82-00ee42c27bad)  
(KB979909)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f42cc5d4-1bea-4a4a-8a08-b3eb92503588)  
(Importante)
</td>
<td style="border:1px solid black;">
[Quartz.dll (DirectShow)](http://www.microsoft.com/downloads/details.aspx?familyid=d28ecdf7-9fd4-437e-9db7-c6b579248abe)  
(KB975562)  
(Critico)  
[Windows Media Format Runtime 9.5](http://www.microsoft.com/downloads/details.aspx?familyid=41faf16f-c7a8-4ce0-b388-a65478576163)  
(KB978695)  
(Critico)  
[Windows Media Format Runtime 9.5 x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=80006082-55f2-4857-9d2c-276c758b5555)<sup>[3]</sup>
(KB978695)  
(Critico)  
[Windows Media Encoder 9 x86](http://www.microsoft.com/downloads/details.aspx?familyid=94c654f0-f70f-4fbd-84de-797be20fc3b9)  
(KB979332)  
(Importante)  
[Windows Media Encoder 9 x64](http://www.microsoft.com/downloads/details.aspx?familyid=2b7a3cb7-151c-4184-9865-f197ef6ee8e7)  
(KB979332)  
(Importante)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=77b1d55c-b015-4863-aab0-6463b90d4bf7)  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4aa0ec4f-5502-4f2a-9732-975518c34444)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=81644c43-22c0-4c61-b395-3264516516a6)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=50b8ee2e-31f8-473d-83d1-822c89c28070)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=87e13912-f861-4985-ab9d-260a5898dfd4)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b0794e7e-c925-4672-b7a5-4bb3f847f045)  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=023572ff-ce5d-4428-a96b-1245db6ff312)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5e55ee58-f00a-4237-bddc-492b63a18b96)  
(KB979906)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=1b41e880-d774-4292-b2aa-2a66568142c9)  
(KB982865)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=43810ead-1fcc-4a97-ad82-00ee42c27bad)  
(KB979909)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=50efb1cf-9d89-4522-929d-f87fd98d6fe8)  
(Importante)
</td>
<td style="border:1px solid black;">
[Quartz.dll (DirectShow)](http://www.microsoft.com/downloads/details.aspx?familyid=7f101f4c-dcc8-474c-a844-fe0c45d6697c)  
(KB975562)  
(Critico)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=f34bc115-022b-46b0-9517-806bd0fc73c5)  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=55d9d7f0-f9d9-4833-b5cc-eb87a62da6a8)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=abcdc3bb-4659-4b63-a9bd-e448f8bed90a)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=123bf547-9005-451f-9eba-97a68037304e)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=6e76ebea-bde1-4352-a283-dd71c2cc51a1)  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=f1f3e524-8ac6-4210-a3a8-4ffc58a606ea)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5e55ee58-f00a-4237-bddc-492b63a18b96)  
(KB979906)  
(Importante)  
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=1b41e880-d774-4292-b2aa-2a66568142c9)  
(KB982865)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=43810ead-1fcc-4a97-ad82-00ee42c27bad)  
(KB979909)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-032**](http://go.microsoft.com/fwlink/?linkid=184917)
</td>
<td style="border:1px solid black;">
[**MS10-033**](http://go.microsoft.com/fwlink/?linkid=191065)
</td>
<td style="border:1px solid black;">
[**MS10-034**](http://go.microsoft.com/fwlink/?linkid=185159)
</td>
<td style="border:1px solid black;">
[**MS10-035**](http://go.microsoft.com/fwlink/?linkid=190898)
</td>
<td style="border:1px solid black;">
[**MS10-037**](http://go.microsoft.com/fwlink/?linkid=190508)
</td>
<td style="border:1px solid black;">
[**MS10-040**](http://go.microsoft.com/fwlink/?linkid=191788)
</td>
<td style="border:1px solid black;">
[**MS10-041**](http://go.microsoft.com/fwlink/?linkid=185042)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7cb64633-d2a0-4e38-be35-ec32ea655a04)  
(Importante)
</td>
<td style="border:1px solid black;">
Solo Windows Vista Service Pack 1:  
[Quartz.dll (DirectShow)](http://www.microsoft.com/downloads/details.aspx?familyid=b64107f2-990a-42df-a75a-5bf371709fd6)  
(KB975562)  
(Critico)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=75e4c9cb-a55a-4e2a-9c97-60a40353cae3)  
(KB979482)  
(Critico)  
[Windows Media Encoder 9 x86](http://www.microsoft.com/downloads/details.aspx?familyid=9fab91da-1528-4df9-a2dd-90e57a3c24cf)  
(KB979332)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2ddaa4b3-1a98-4183-94af-ebdae4e7b76a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=661c9528-917d-4df6-a330-c89f39dc5ce4)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=640f9216-3e99-46b6-aac8-cd051eedad3c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=363b503a-2e1e-4284-a029-9695d2acfcb6)  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=01382926-2313-4769-a0a5-262c4f9f18a1)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5e55ee58-f00a-4237-bddc-492b63a18b96)  
(KB979906)  
(Importante)  
Solo Windows Vista Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=3ffa2aa2-96a6-4317-8a81-c0ab6d570778)  
(KB979913)  
(Importante)  
Solo Windows Vista Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=818acb7e-f984-4793-9418-bb01ed8cfb68)  
(KB979911)  
(Importante)  
Solo Windows Vista Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=14c2fa85-f73e-4b62-84ca-d5ea7439aebb) (KB979910)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=bbfc4d80-67eb-4deb-9595-cb67942a0df2)  
(Importante)
</td>
<td style="border:1px solid black;">
Solo Windows Vista x64 Edition Service Pack 1:  
[Quartz.dll (DirectShow)](http://www.microsoft.com/downloads/details.aspx?familyid=0754addb-2f04-45c9-8594-174b8b8b297c)  
(KB975562)  
(Critico)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=c9f033f6-f587-494d-b968-1316f1deed06)  
(KB979482)  
(Critico)  
[Windows Media Encoder 9 x86](http://www.microsoft.com/downloads/details.aspx?familyid=63bba49e-6d80-47b3-b109-fa9b2392af4f)  
(KB979332)  
(Importante)  
[Windows Media Encoder 9 x64](http://www.microsoft.com/downloads/details.aspx?familyid=e19aeef8-6bef-45ee-bc9f-3e4b81a58e33)  
(KB979332)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ddf55e74-dbaa-45f7-ac5b-ae3da24e0e33)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=d9f5feb0-fa1a-40c1-9971-9b8af6f0b4a5)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=3076d1ea-7716-4b54-8ec4-660374f14dcb)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3f512b86-3a99-47f7-a90e-1ae9b291385c)  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=7fb6f2b8-c7a6-4239-99f3-cf3aacf89b0f)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5e55ee58-f00a-4237-bddc-492b63a18b96)  
(KB979906)  
(Importante)  
Solo Windows Vista x64 Edition Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=3ffa2aa2-96a6-4317-8a81-c0ab6d570778)  
(KB979913)  
(Importante)  
Solo Windows Vista x64 Edition Service Pack 1:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=818acb7e-f984-4793-9418-bb01ed8cfb68)  
(KB979911)  
(Importante)  
Solo Windows Vista x64 Edition Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=14c2fa85-f73e-4b62-84ca-d5ea7439aebb)  
(KB979910)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-032**](http://go.microsoft.com/fwlink/?linkid=184917)
</td>
<td style="border:1px solid black;">
[**MS10-033**](http://go.microsoft.com/fwlink/?linkid=191065)
</td>
<td style="border:1px solid black;">
[**MS10-034**](http://go.microsoft.com/fwlink/?linkid=185159)
</td>
<td style="border:1px solid black;">
[**MS10-035**](http://go.microsoft.com/fwlink/?linkid=190898)
</td>
<td style="border:1px solid black;">
[**MS10-037**](http://go.microsoft.com/fwlink/?linkid=190508)
</td>
<td style="border:1px solid black;">
[**MS10-040**](http://go.microsoft.com/fwlink/?linkid=191788)
</td>
<td style="border:1px solid black;">
[**MS10-041**](http://go.microsoft.com/fwlink/?linkid=185042)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=22d550fe-ba35-4750-a9d6-624858b67c94)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit soltanto:  
[Quartz.dll (DirectShow)](http://www.microsoft.com/downloads/details.aspx?familyid=18fd814b-51f3-470b-a5bd-97be752298d9)\*\*  
(KB975562)  
(Critico)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=5c5e2dfc-0078-4f2a-9c2e-75e45bb7638e)\*  
(KB979482)  
(Critico)  
[Windows Media Encoder 9 x86](http://www.microsoft.com/downloads/details.aspx?familyid=1ce1e47f-b1c3-4480-bafd-74f8b12e2171)\*\*  
(KB979332)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a06b9f42-47ac-4ff2-ac32-e4958cdb611e)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=bed14484-7fc5-455d-b996-3192467543cc)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=24ed08c7-a474-4458-8269-3b9de5e22385)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e78ad607-d209-48c4-b0f3-ed4c70993174)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=84a54246-5d9e-49e2-8170-af48b43f984d)\*<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5e55ee58-f00a-4237-bddc-492b63a18b96)\*\*  
(KB979906)  
(Importante)  
Solo Windows Server 2008 per sistemi a 32 bit:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=3ffa2aa2-96a6-4317-8a81-c0ab6d570778)\*\*  
(KB979913)  
(Importante)  
Solo Windows Server 2008 per sistemi a 32 bit:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=818acb7e-f984-4793-9418-bb01ed8cfb68)\*\*  
(KB979911)  
(Importante)  
Solo Windows Server 2008 per sistemi a 32 bit Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=14c2fa85-f73e-4b62-84ca-d5ea7439aebb)\*\*  
(KB979910)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=09025626-4116-4a31-8700-215382898ee2)\*  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 solo per sistemi x64:  
[Quartz.dll (DirectShow)](http://www.microsoft.com/downloads/details.aspx?familyid=4e40da51-23ee-44f0-9ea0-99bda8cca731)\*\*  
(KB975562)  
(Critico)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=bfc0b62c-2d79-48dd-896f-d05057c02e8c)\*  
(KB979482)  
(Critico)  
[Windows Media Encoder 9 x86](http://www.microsoft.com/downloads/details.aspx?familyid=93cc5ace-6382-4a2f-875b-9348b7e198a6)\*\*  
(KB979332)  
(Importante)  
[Windows Media Encoder 9 x64](http://www.microsoft.com/downloads/details.aspx?familyid=d650a7d7-5620-4bb7-a7ad-0848dd28dae3)\*\*  
(KB979332)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6d0a3f7c-2617-4bc6-a4c7-cda26c6471e1)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=a24554e8-213b-4c24-b062-ec424d64128e)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=cf84469b-ce6d-45e8-8336-7b4501c6cf91)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=85f6fc5d-efd1-4351-b4c0-b9b7080e6173)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=38286e43-89a6-4895-8ff9-69452df38706)\*<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5e55ee58-f00a-4237-bddc-492b63a18b96)\*\*  
(KB979906)  
(Importante)  
Solo Windows Server 2008 per sistemi x64:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=3ffa2aa2-96a6-4317-8a81-c0ab6d570778)\*\*  
(KB979913)  
(Importante)  
Solo Windows Server 2008 per sistemi x64:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=818acb7e-f984-4793-9418-bb01ed8cfb68)\*\*  
(KB979911)  
(Importante)  
Solo Windows Server 2008 per sistemi x64 Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=14c2fa85-f73e-4b62-84ca-d5ea7439aebb)\*\*  
(KB979910)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0035cfe2-d38d-41cd-b704-ec1feda307d8)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium soltanto:  
[Quartz.dll (DirectShow)](http://www.microsoft.com/downloads/details.aspx?familyid=120c68f5-4575-4e2a-912a-eed52736c403)  
(KB975562)  
(Critico)  
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=6e5753ab-848d-475f-917d-ba70f70b65f5)  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=38347fa6-5946-4bb5-9fea-a5b2f4e7c1f2)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=dee5c0c0-b844-490d-8daf-6e6ec8a39e35)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c6f1aae5-e8fd-4121-89b2-b97c571e8223)  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=8ad19eba-9821-48b4-a942-4ee4f002f913)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5e55ee58-f00a-4237-bddc-492b63a18b96)  
(KB979906)  
(Importante)  
Solo Windows Server 2008 per sistemi Itanium:  
[Microsoft .NET Framework 2.0 Service Pack 1 e Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=3ffa2aa2-96a6-4317-8a81-c0ab6d570778)  
(KB979913)  
(Importante)  
Solo Windows Server 2008 per sistemi Itanium:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=818acb7e-f984-4793-9418-bb01ed8cfb68)  
(KB979911)  
(Importante)  
Solo Windows Server 2008 per sistemi Itanium Service Pack 2:  
[Microsoft .NET Framework 2.0 Service Pack 2 e Microsoft .NET Framework 3.5 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=14c2fa85-f73e-4b62-84ca-d5ea7439aebb)  
(KB979910)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows 7
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-032**](http://go.microsoft.com/fwlink/?linkid=184917)
</td>
<td style="border:1px solid black;">
[**MS10-033**](http://go.microsoft.com/fwlink/?linkid=191065)
</td>
<td style="border:1px solid black;">
[**MS10-034**](http://go.microsoft.com/fwlink/?linkid=185159)
</td>
<td style="border:1px solid black;">
[**MS10-035**](http://go.microsoft.com/fwlink/?linkid=190898)
</td>
<td style="border:1px solid black;">
[**MS10-037**](http://go.microsoft.com/fwlink/?linkid=190508)
</td>
<td style="border:1px solid black;">
[**MS10-040**](http://go.microsoft.com/fwlink/?linkid=191788)
</td>
<td style="border:1px solid black;">
[**MS10-041**](http://go.microsoft.com/fwlink/?linkid=185042)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi 32-bit
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=3e0ff389-4612-4c92-bbff-bb45b5bdfc6a)  
(Importante)
</td>
<td style="border:1px solid black;">
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=63567e99-087d-4804-953a-f23bdeba7772)  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=5bce87fe-dcbb-4638-b248-3f0755537b00)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=5c835885-9375-4882-a92f-4d4cfcacc005)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=969af8d6-f6da-4dd1-a7d7-2de54a5a8978)  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=588167cb-f62a-4fb8-8a18-ac15dc322495)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a49532d7-53f6-4190-aaf6-b1a818924764)  
(KB979916)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=2b1e4aff-605a-4e94-88f9-135ce35f0646)  
(Importante)
</td>
<td style="border:1px solid black;">
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=6c261dbf-14c6-4071-8523-e8ba8059fa54)  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=ee68ecd0-5b8a-4c1e-bdee-bd8616558d43)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=5cfc5776-0c6b-4092-bc98-94df077c60d8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=b069e5b2-aa2d-452e-b687-8734b5ba0051)  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=1c45d0c8-1629-470b-8167-c6bf66054595)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a49532d7-53f6-4190-aaf6-b1a818924764)  
(KB979916)  
(Importante)
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2008 R2
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-032**](http://go.microsoft.com/fwlink/?linkid=184917)
</td>
<td style="border:1px solid black;">
[**MS10-033**](http://go.microsoft.com/fwlink/?linkid=191065)
</td>
<td style="border:1px solid black;">
[**MS10-034**](http://go.microsoft.com/fwlink/?linkid=185159)
</td>
<td style="border:1px solid black;">
[**MS10-035**](http://go.microsoft.com/fwlink/?linkid=190898)
</td>
<td style="border:1px solid black;">
[**MS10-037**](http://go.microsoft.com/fwlink/?linkid=190508)
</td>
<td style="border:1px solid black;">
[**MS10-040**](http://go.microsoft.com/fwlink/?linkid=191788)
</td>
<td style="border:1px solid black;">
[**MS10-041**](http://go.microsoft.com/fwlink/?linkid=185042)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Critico**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=4272277f-b2dd-4406-8bbd-bc461c9923b8)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=1331f2bc-7479-4be7-a413-52afb488a330)\*  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=901f7c89-02af-4f87-8592-dad318997d77)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=7c4ff5ae-eadd-431e-b982-d5f179efb8c0)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=45242c7c-3752-44bf-a766-024ad7d28f53)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=5d9b7705-6280-4d2e-94fa-3160b3ce5cfa)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a49532d7-53f6-4190-aaf6-b1a818924764)\*  
(KB979916)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=7d636f82-e828-468c-ac36-808ff9d37c7f)  
(Importante)
</td>
<td style="border:1px solid black;">
[Asycfilt.dll (componente COM)](http://www.microsoft.com/downloads/details.aspx?familyid=7a1ee54f-3f73-4557-9071-5af236e70937)  
(KB979482)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=4958b221-2776-43d7-9e1c-1e1cb318a694)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=52c04d85-911f-47be-852e-c9bb4934744d)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=0a271fb5-da5b-4a17-9593-e56b9a843b8f)  
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=869e900a-0063-4d8b-9b7c-7d12f6be12cd)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=a49532d7-53f6-4190-aaf6-b1a818924764)  
(KB979916)  
(Importante)
</td>
</tr>
</table>
 
**Note per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/en-us/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/en-us/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2. Vedere [Opzioni di installazione Server Core a confronto](http://www.microsoft.com/windowsserver2008/en/us/compare-core-installation.aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/en-us/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/en-us/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2. Vedere [Opzioni di installazione Server Core a confronto](http://www.microsoft.com/windowsserver2008/en/us/compare-core-installation.aspx).

**Nota per MS10-033**

<sup>[1]</sup>L'aggiornamento per Quartz.dll (Direct Show) (DirectX 9) interessa anche DirectX 9.0a, DirectX 9.0b e DirectX 9.0c.

<sup>[2]</sup>Questo pacchetto di aggiornamento interessa il Runtime SDK formato Windows Media 9 su Microsoft Windows 2000 dotato dell'aggiornamento per lettori multimediali abilitati per DRM (KB891122). Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 974316](http://support.microsoft.com/kb/974316).

<sup>[3]</sup>Se è stata installata una versione di Runtime formato Windows Media 9.5 x64 Edition, è necessario applicare gli aggiornamenti per la protezione di Runtime formato Windows Media 9.5 e Runtime formato Windows Media 9.5 x64 Edition per essere completamente protetti dalla vulnerabilità trattata nel bollettino MS10-033.

**Nota per MS10-035**

<sup>[1]</sup>Livelli di gravità non sono applicabili a questo aggiornamento perché le vulnerabilità trattate in questo bollettino non interessano questo software. Tuttavia, questo aggiornamento viene offerto per risolvere un problema di regressione presente a partire dal bollettino [MS09-054](http://go.microsoft.com/fwlink/?linkid=163979). Vedere il bollettino [MS10-035](http://go.microsoft.com/fwlink/?linkid=190898) per maggiori dettagli.

**Nota per MS10-040**

<sup>[1]</sup>Questo sistema operativo risulta interessato solo quando è installata la protezione estesa per l'autenticazione. Vedere l'[articolo della Microsoft Knowledge Base 973917](http://support.microsoft.com/kb/973917).

#### Applicazioni e software Microsoft Office

 
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
</tr>
<tr>
<th colspan="4">
Applicazioni, sistemi e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-036**](http://go.microsoft.com/fwlink/?linkid=190554)
</td>
<td style="border:1px solid black;">
[**MS10-038**](http://go.microsoft.com/fwlink/?linkid=191053)
</td>
<td style="border:1px solid black;">
[**MS10-039**](http://go.microsoft.com/fwlink/?linkid=191905)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft Office XP Service Pack 3<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=fec14a92-79a1-4281-8ee2-659b2dfd283f)  
(KB982299)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=80fdd134-2a86-4115-aea1-841f19af92e3)  
(KB982311)  
(Importante)  
[Microsoft Office Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=757b5d8f-ade5-4896-b152-43f76516bcf1)<sup>[2]</sup>
(KB982133)  
(Importante)  
[Microsoft Office PowerPoint 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6b6204c1-559f-45a5-8f6c-a1e216192efc)<sup>[2]</sup>
(KB982157)  
(Importante)  
[Microsoft Office Publisher 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=87bac893-81ec-4ede-aca1-a9aa48b92cd4)<sup>[2]</sup>
(KB982122)  
(Importante)  
[Microsoft Office Visio 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=1595ada3-bb4f-40f6-8137-23eba918bc8a)<sup>[2]</sup>
(KB982126)  
(Importante)  
[Microsoft Office Word 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d2c40eb5-1149-4466-840c-84f406f64245)<sup>[2]</sup>
(KB982134)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=757b5d8f-ade5-4896-b152-43f76516bcf1)  
(KB982133)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office System 2007 Service Pack 1 e Microsoft Office System 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[2007 Microsoft Office System Service Pack 1 e 2007 Microsoft Office System Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6deb4fb0-cbfc-40df-8f62-35fa1db0e167)  
(KB982312)  
(Importante)  
[Microsoft Office Excel 2007 Service Pack 1 e Microsoft Office Excel 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1b2599f0-1e5d-463c-b100-6c6a1b17b2ec)<sup>[3]</sup>
(KB982308)  
(Importante)  
[Microsoft Office PowerPoint 2007 Service Pack 1 e Microsoft Office PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=decb834d-3958-45cc-a5ae-4283adb2462a)<sup>[3]</sup>
(KB982158)  
(Importante)  
[Microsoft Office Publisher 2007 Service Pack 1 e Microsoft Office Publisher 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6a74b986-1e99-4aa1-828f-757a36896f65)<sup>[3]</sup>
(KB982124)  
(Importante)  
[Microsoft Office Visio 2007 Service Pack 1 e Microsoft Office Visio 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d5df052e-1f38-4308-bcca-296cff22729b)<sup>[3]</sup>
(KB982127)  
(Importante)  
[Microsoft Office Word 2007 Service Pack 1 e Microsoft Office Word 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7e9708f0-8cd6-4f0b-8585-bccc54fa2755)<sup>[3]</sup>
(KB982135)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2007 Service Pack 1 e Microsoft Office Excel 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1b2599f0-1e5d-463c-b100-6c6a1b17b2ec)<sup>[1]</sup>
(KB982308)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="4">
Microsoft Office per Mac
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-036**](http://go.microsoft.com/fwlink/?linkid=190554)
</td>
<td style="border:1px solid black;">
[**MS10-038**](http://go.microsoft.com/fwlink/?linkid=191053)
</td>
<td style="border:1px solid black;">
[**MS10-039**](http://go.microsoft.com/fwlink/?linkid=191905)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=16c71ab8-9284-407a-856a-93c67995f125)  
(KB2028866)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=d46255bd-6470-4106-9fe2-ea67acd3f1bd)  
(KB2028864)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Convertitore file in formato XML aperto per Mac
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=b6ca7b05-cf97-43a2-95eb-7b5caf7c1528)  
(KB2078051)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="4">
Altro software Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-036**](http://go.microsoft.com/fwlink/?linkid=190554)
</td>
<td style="border:1px solid black;">
[**MS10-038**](http://go.microsoft.com/fwlink/?linkid=191053)
</td>
<td style="border:1px solid black;">
[**MS10-039**](http://go.microsoft.com/fwlink/?linkid=191905)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Excel Viewer Service Pack 1 e Microsoft Office Excel Viewer Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel Viewer Service Pack 1 e Microsoft Office Excel Viewer Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=033b3bf3-7826-4064-b001-11e4dce2d91a)  
(KB982333)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7f89a734-cda4-4abb-9a10-f6dfe560e8d0)  
(KB982331)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office InfoPath 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office InfoPath 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=4f79d376-0ea2-4218-9200-3c34c83ba336)  
(KB980923)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office InfoPath 2007 Service Pack 1 e Microsoft Office InfoPath 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office InfoPath 2007 Service Pack 1 e Microsoft Office InfoPath 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=bfa8765a-7970-4feb-996c-7c27d71c97c6)  
(KB979441)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office SharePoint Server 2007 Service Pack 1 e Microsoft Office SharePoint Server 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2007 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=52a55423-f33b-4cd1-919d-806972a553df)<sup>[1]</sup>
(KB979445)  
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 2 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=52a55423-f33b-4cd1-919d-806972a553df)<sup>[1]</sup>
(KB979445)  
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=4d84a25b-532f-4319-9ab2-90e5b82ebd90)<sup>[1]</sup>
(KB979445)  
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 2 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=4d84a25b-532f-4319-9ab2-90e5b82ebd90)<sup>[1]</sup>
(KB979445)  
(Importante)
</td>
</tr>
</table>
 
**Note per MS10-036**

<sup>[1]</sup>Nessun aggiornamento disponibile. Consultare il bollettino per i dettagli.

<sup>[2]</sup>Oltre a questo aggiornamento, i clienti devono installare anche l'aggiornamento per Microsoft Office 2003 Service Pack 3 (KB982311) per essere protetti dalla vulnerabilità descritta in questo bollettino.

<sup>[3]</sup>Oltre a questo aggiornamento, i clienti devono installare anche l'aggiornamento per Microsoft Office System 2007 Service Pack 1 e Microsoft Office System 2007 Service Pack 2 (KB982312) per essere protetti dalla vulnerabilità descritta in questo bollettino.

**Nota per MS10-038**

<sup>[1]</sup>Oltre a questo aggiornamento, i clienti devono installare anche l'aggiornamento per la protezione per il pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e il pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2 (KB982308) per essere protetti dalle vulnerabilità descritte nel bollettino.

**Note per MS10-039**

<sup>[1]</sup>Per le edizioni supportate di Microsoft Office SharePoint Server 2007, oltre al pacchetto di aggiornamento per la protezione KB979445, i clienti devono installare anche l'aggiornamento per la protezione di Microsoft Windows SharePoint Services 3.0 (KB983444) per essere protetti dalle vulnerabilità descritte in questo bollettino.

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Windows SharePoint Services
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-039**](http://go.microsoft.com/fwlink/?linkid=191905)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 1 e Microsoft Windows SharePoint Services 3.0 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Windows SharePoint Services 3.0 Service Pack 1 e Microsoft Windows SharePoint Services 3.0 Service Pack 2 (versioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=3841ceda-d0af-4e5e-8a1a-7dd954850783)  
(KB983444)  
(Importante)  
[Microsoft Windows SharePoint Services 3.0 Service Pack 1 e Microsoft Windows SharePoint Services 3.0 Service Pack 2 (versioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=94bc76d4-78e4-4bda-8922-36c3a9d3854f)  
(KB983444)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS10-039**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://go.microsoft.com/fwlink/?linkid=69903). [TechNet Security Center](http://go.microsoft.com/fwlink/?linkid=21171) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://go.microsoft.com/fwlink/?linkid=85102), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://go.microsoft.com/fwlink/?linkid=40747) e [Windows Update](http://go.microsoft.com/fwlink/?linkid=21130). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://go.microsoft.com/fwlink/?linkid=21129). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Note** A partire dal 1 agosto, 2009, Microsoft non offre più alcun supporto per Office Update e Office Update Inventory Tool. Per continuare a ricevere gli ultimi aggiornamenti per i prodotti Microsoft Office, utilizzare [Microsoft Update](http://go.microsoft.com/fwlink/?linkid=40747). Per ulteriori informazioni, vedere [Informazioni su Microsoft Office Update: Domande frequenti](http://office.microsoft.com/en-us/downloads/fx010402221033.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=50120).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/en-us/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://go.microsoft.com/fwlink/?linkid=22939). Gli utenti di SMS 2.0 possono inoltre utilizzare Security Update Inventory Tool per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://go.microsoft.com/fwlink/?linkid=21158).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://go.microsoft.com/fwlink/?linkid=33341). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2.0 Administration Feature Pack](http://go.microsoft.com/fwlink/?linkid=21161)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet2.microsoft.com/windowsvista/en/library/4279e239-37a4-44aa-aec5-4e70fe39f9de1033.mspx?mfr=true), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/en-us/wsus/bb456965.aspx). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://www.microsoft.com/security/msrc/mapp/partners.mspx).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://go.microsoft.com/fwlink/?linkid=21168).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://go.microsoft.com/fwlink/?linkid=21129). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://go.microsoft.com/fwlink/?linkid=40747).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://go.microsoft.com/fwlink/?linkid=21164).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Sebastien Renaud del [VUPEN Vulnerability Research Team](http://www.vupen.com/) per aver segnalato un problema descritto nel bollettino MS10-032
-   [Secunia Research](http://secunia.com/) per avere collaborato con noi allo studio di un problema descritto nel bollettino MS10-032
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato due problemi descritti nel bollettino MS10-033
-   Shaun Colley di [NGS Software](http://www.ngssoftware.com/) per aver segnalato un problema descritto nel bollettino MS10-034
-   Chris Ries di Carnegie Mellon University Computing Services per aver segnalato un problema descritto nel bollettino MS10-034
-   Chris Weber di [Casaba Security](http://www.casabasecurity.com/) per aver segnalato un problema descritto nei bollettini MS10-035 e MS10-039
-   Takeshi Terada di [Mitsui Bussan Secure Directions, Inc.](http://www.mbsd.jp/) per aver segnalato un problema descritto nel bollettino MS10- 035
-   Michal Zalewski di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS10-035
-   Chris Rohlf di [Matasano Security](http://www.matasano.com/) per aver segnalato due problemi descritti nel bollettino MS10-035
-   Peter Vreugdenhil, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS10-035
-   David Dewey di [IBM ISS X-Force](http://www.iss.net/) e Ryan Smith di [Accuvant](http://www.accuvant.com/), in precedenza collaboratore di [VeriSign iDefense Labs](http://labs.idefense.com/), per avere collaborato con noi alle modifiche al sistema di difesa contenute nel bollettino MS10-036
-   Chris Carton di Laserforce International, che collabora con [Secunia](http://secunia.com/), per aver segnalato un problema descritto nel bollettino MS10-037
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS10-038
-   Nicolas Joly del [VUPEN Vulnerability Research Team](http://www.vupen.com/) per aver segnalato un problema descritto nel bollettino MS10-038
-   Bing Liu di [FortiGuard Labs di Fortinet](http://www.fortiguard.com/) per aver segnalato un problema descritto nel bollettino MS10-038
-   Carsten Eiram di [Secunia](http://secunia.com/) per aver segnalato due problemi descritti nel bollettino MS10-038
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS10-038
-   Rick Glaspie di Gilbert Public Schools a Gilbert, Arizona, per aver segnalato un problema descritto nel bollettino MS10-038
-   Rik Jones del Dallas County Community College District per aver segnalato un problema descritto nel bollettino MS10-039
-   Arian Evans di [WhiteHat Security](http://www.whitehatsec.com) per aver segnalato il problema dell'elusione della convalida delle richieste ASP.NET, risolto nel bollettino MS10-041 mediante una modifica al sistema di difesa

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://go.microsoft.com/fwlink/?linkid=21131). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://go.microsoft.com/fwlink/?linkid=21155).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (8 giugno 2010): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (9 giugno 2010): Sono state riviste le note per il bollettino MS10-033 nella sezione **Software interessato e percorsi per il download**.
-   V2.0 (13 settembre 2011): È stato rilasciato nuovamente il bollettino MS10-035 per offrire nuovamente gli aggiornamenti per Internet Explorer su Microsoft Windows 2000 e Windows XP per risolvere un problema di rilevamento. Non sono previsti aggiornamenti ai file sull'aggiornamento per la protezione. I clienti che hanno già aggiornato i propri sistemi non devono eseguire ulteriori operazioni.

*Built at 2014-04-18T01:50:00Z-07:00*
