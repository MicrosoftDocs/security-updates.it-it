---
TOCTitle: 'MS12-FEB'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Febbraio 2012'
ms:assetid: 'ms12-feb'
ms:contentKeyID: 61240069
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms12-feb(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Febbraio 2012
==================================================================

Data di pubblicazione: martedì 14 febbraio 2012

**Versione:** 1.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati in febbraio 2012.

Con il rilascio dei bollettini sulla sicurezza di febbraio 2012, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 9 febbraio 2012. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 15 febbraio 2012 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di febbraio](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032499501). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217214).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=238387">MS12-008</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel di Windows possono consentire l'esecuzione di codice in modalità remota (2660465)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente e una divulgata pubblicamente in Microsoft Windows. La più critica di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota qualora un utente visiti un sito Web con contenuto appositamente predisposto o un'applicazione appositamente predisposta venga eseguita localmente. Non è in alcun modo possibile obbligare gli utenti a visitare un sito Web appositamente predisposto. L'utente malintenzionato deve invece convincere gli utenti a visitare il sito Web, in genere inducendoli a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che li indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=236989">MS12-010</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2647516)</strong><br />
<br />
Questo aggiornamento per la protezione risolve quattro vulnerabilità di Internet Explorer segnalate privatamente. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=238617">MS12-013</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità legata alla libreria di runtime C può consentire l'esecuzione di codice in modalità remota (2654428)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file multimediale appositamente predisposto presente su un sito Web o inviato come allegato di posta elettronica. Sfruttando tale vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=235370">MS12-016</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in .NET Framework e Microsoft Silverlight possono consentire l'esecuzione di codice in modalità remota (2651026)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e una vulnerabilità segnalata privatamente in Microsoft .NET Framework e in Microsoft Silverlight. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota in un sistema client se un utente visualizza una pagina Web appositamente predisposta mediante un browser Web in grado di eseguire applicazioni browser XAML (XBAP) o applicazioni Silverlight. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft .NET Framework,<br />
Microsoft Silverlight</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=238474">MS12-009</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel driver di funzioni ausiliario possono consentire l'acquisizione di privilegi più elevati (2645640)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Windows. Le vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede a un sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, un utente malintenzionato deve disporre di credenziali di accesso valide ed essere in grado di sfruttare tali vulnerabilità.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=238500">MS12-011</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft SharePoint possono consentire l'acquisizione di privilegi più elevati (2663841)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità di Microsoft SharePoint e Microsoft SharePoint Foundation segnalate privatamente. Queste vulnerabilità possono consentire l'acquisizione di privilegi più elevati o l'intercettazione di informazioni personali nel caso in cui un utente abbia fatto clic su un URL appositamente predisposto.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Software dei server Microsoft</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=239941">MS12-012</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità del Pannello di controllo Sistema di gestione colori può consentire l'esecuzione di codice in modalità remota (2643719)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente di Microsoft Windows. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file legittimo (come un file .icm o .icc) che si trova nella stessa directory di una libreria di un file di collegamento dinamico (DLL) appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=239945">MS12-014</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità nel codec Indeo può consentire l'esecuzione di codice in modalità remota (2661637)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente di Microsoft Windows. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file legittimo (ad esempio un file .avi) che si trova nella stessa directory di rete di una libreria di un file di collegamento dinamico (DLL) appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può eseguire codice non autorizzato nel contesto dell'utente collegato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato può assumere il controllo completo del sistema interessato. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=238400">MS12-015</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Visio Viewer 2010 possono consentire l'esecuzione di codice in modalità remota (2663510)</strong><br />
<br />
Questo aggiornamento per la protezione risolve cinque vulnerabilità di Microsoft Office segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file Visio appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).
  
Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.
  
| ID bollettino                                             | Titolo della vulnerabilità                                                                                         | ID CVE                                                                            | Valutazione dell'Exploitability per la versione più recente del software                                                | Valutazione dell'Exploitability per la versione meno recente del software                                               | Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service | Note fondamentali                                                                                                                   |  
|-----------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|  
| [MS12-008](http://go.microsoft.com/fwlink/?linkid=238387) | Vulnerabilità legata a un errore di tipo use-after-free del layout della tastiera                                  | [CVE-2012-0154](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0154)  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                                                                           |  
| [MS12-008](http://go.microsoft.com/fwlink/?linkid=238387) | Vulnerabilità legata alla violazione dell'accesso GD                                                               | [CVE-2011-5046](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-5046)  | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Difficile costruire il codice dannoso                  | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Difficile costruire il codice dannoso                  | Permanente                                                                       | Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.                                                             |  
| [MS12-009](http://go.microsoft.com/fwlink/?linkid=238474) | Vulnerabilità legata all'acquisizione di privilegi più elevati in AfdPoll                                          | [CVE-2012-0148](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0148)  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Permanente                                                                       | X64 è sfruttabile, x86 no.                                                                                                          |  
| [MS12-009](http://go.microsoft.com/fwlink/?linkid=238474) | Vulnerabilità legata all'acquisizione di privilegi più elevati nel driver di funzioni ausiliario                   | [CVE-2012-0149](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0149)  | Non interessato                                                                                                         | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Permanente                                                                       | Solo Windows Server 2003 è interessato.                                                                                             |  
| [MS12-010](http://go.microsoft.com/fwlink/?linkid=236989) | Vulnerabilità legata all'esecuzione di codice in modalità remota nel layout HTML                                   | [CVE-2012-0011](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0011)  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Temporaneo                                                                       | (Nessuna)                                                                                                                           |  
| [MS12-010](http://go.microsoft.com/fwlink/?linkid=236989) | Vulnerabilità legata all'intercettazione di informazioni personali tramite byte Null                               | [CVE-2012-0012](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0012)  | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Non interessato                                                                                                         | Non applicabile                                                                  | Questa vulnerabilità riguarda l'intercettazione di informazioni personali.                                                          |  
| [MS12-010](http://go.microsoft.com/fwlink/?linkid=236989) | Vulnerabilità legata all'esecuzione di codice in modalità remota in VML                                            | [CVE-2012- 0155](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0155) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non interessato                                                                                                         | Temporaneo                                                                       | (Nessuna)                                                                                                                           |  
| [MS12-011](http://go.microsoft.com/fwlink/?linkid=238500) | Vulnerabilità XSS in inplview.aspx                                                                                 | [CVE-2012-0017](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0017)  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non interessato                                                                                                         | Non applicabile                                                                  | (Nessuna)                                                                                                                           |  
| [MS12-011](http://go.microsoft.com/fwlink/?linkid=238500) | Vulnerabilità XSS in themeweb.aspx                                                                                 | [CVE-2012-0144](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0144)  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non interessato                                                                                                         | Non applicabile                                                                  | (Nessuna)                                                                                                                           |  
| [MS12-011](http://go.microsoft.com/fwlink/?linkid=238500) | Vulnerabilità XSS in wizardlist.aspx                                                                               | [CVE-2012- 0145](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0145) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non interessato                                                                                                         | Non applicabile                                                                  | (Nessuna)                                                                                                                           |  
| [MS12-012](http://go.microsoft.com/fwlink/?linkid=239941) | Vulnerabilità legata al caricamento non sicuro delle librerie del Pannello di controllo Sistema di gestione colori | [CVE-2010-5082](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-5082)  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.                                                             |  
| [MS12-013](http://go.microsoft.com/fwlink/?linkid=238617) | Vulnerabilità legata al sovraccarico al buffer in msvcrt.dll                                                       | [CVE-2012-0150](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0150)  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Temporaneo                                                                       | (Nessuna)                                                                                                                           |  
| [MS12-014](http://go.microsoft.com/fwlink/?linkid=239945) | Vulnerabilità legata al caricamento non sicuro delle librerie nel codec audio Indeo                                | [CVE-2010-3138](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3138)  | Non interessato                                                                                                         | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.                                                             |  
| [MS12-015](http://go.microsoft.com/fwlink/?linkid=238400) | Vulnerabilità legata al danneggiamento della memoria del formato file VSD                                          | [CVE-2012-0019](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0019)  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non interessato                                                                                                         | Non applicabile                                                                  | Questa vulnerabilità riguarda Visio Viewer 2010 e Visio Viewer 2010 Service Pack 1 (le uniche versioni supportate di Visio Viewer). |  
| [MS12-015](http://go.microsoft.com/fwlink/?linkid=238400) | Vulnerabilità legata al danneggiamento della memoria del formato file VSD                                          | [CVE-2012-0020](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0020)  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non interessato                                                                                                         | Non applicabile                                                                  | Questa vulnerabilità riguarda Visio Viewer 2010 e Visio Viewer 2010 Service Pack 1 (le uniche versioni supportate di Visio Viewer). |  
| [MS12-015](http://go.microsoft.com/fwlink/?linkid=238400) | Vulnerabilità legata al danneggiamento della memoria del formato file VSD                                          | [CVE-2012-0136](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0136)  | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Non interessato                                                                                                         | Non applicabile                                                                  | Questa vulnerabilità riguarda Visio Viewer 2010 e Visio Viewer 2010 Service Pack 1 (le uniche versioni supportate di Visio Viewer). |  
| [MS12-015](http://go.microsoft.com/fwlink/?linkid=238400) | Vulnerabilità legata al danneggiamento della memoria del formato file VSD                                          | [CVE-2012-0137](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0137)  | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Non interessato                                                                                                         | Non applicabile                                                                  | Questa vulnerabilità riguarda Visio Viewer 2010 e Visio Viewer 2010 Service Pack 1 (le uniche versioni supportate di Visio Viewer). |  
| [MS12-015](http://go.microsoft.com/fwlink/?linkid=238400) | Vulnerabilità legata al danneggiamento della memoria del formato file VSD                                          | [CVE-2012-0138](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0138)  | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Non interessato                                                                                                         | Non applicabile                                                                  | Questa vulnerabilità riguarda Visio Viewer 2010 e Visio Viewer 2010 Service Pack 1 (le uniche versioni supportate di Visio Viewer). |  
| [MS12-016](http://go.microsoft.com/fwlink/?linkid=235370) | Vulnerabilità legata agli oggetti non gestiti in .NET Framework                                                    | [CVE-2012-0014](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0014)  | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                                                                           |  
| [MS12-016](http://go.microsoft.com/fwlink/?linkid=235370) | Vulnerabilità legata al danneggiamento degli heap in .NET Framework                                                | [CVE-2012-0015](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-0015)  | Non interessato                                                                                                         | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.                                                             |
  
Software interessato e percorsi per il download  
-----------------------------------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.
  
**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.
  
#### Sistema operativo Windows e suoi componenti

 
<table style="border:1px solid black;">
<tr>
<th colspan="8">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-008**](http://go.microsoft.com/fwlink/?linkid=238387)
</td>
<td style="border:1px solid black;">
[**MS12-010**](http://go.microsoft.com/fwlink/?linkid=236989)
</td>
<td style="border:1px solid black;">
[**MS12-013**](http://go.microsoft.com/fwlink/?linkid=238617)
</td>
<td style="border:1px solid black;">
[**MS12-016**](http://go.microsoft.com/fwlink/?linkid=235370)
</td>
<td style="border:1px solid black;">
[**MS12-009**](http://go.microsoft.com/fwlink/?linkid=238474)
</td>
<td style="border:1px solid black;">
[**MS12-012**](http://go.microsoft.com/fwlink/?linkid=239941)
</td>
<td style="border:1px solid black;">
[**MS12-014**](http://go.microsoft.com/fwlink/?linkid=239945)
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
Nessuno
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=832afe5e-d61e-4554-b889-9174df042b32)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=a7d59fa8-0a49-4985-9f14-92218d3b5cea)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=6025c5d6-696c-49cd-9264-96af5766d318)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=5b37f5b1-207f-4fa1-9769-c873d672e80c)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5269e18b-d4f0-4c64-8df8-283a2ca66c59)  
(KB2633880)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=32e5c9ad-b610-4afb-b6f0-bb0b5fbdd1f6)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ff2c141c-08b4-42c6-9f66-580f8678c01f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=96d404e7-8928-494e-8a3c-3897817cda7b)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=b40bc334-edbc-48d5-9196-b7fb0e19966e)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=2fc9d519-94b3-4b56-92fd-4c0ccf8210fe)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5269e18b-d4f0-4c64-8df8-283a2ca66c59)  
(KB2633880)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=82f5c503-d2ea-4fed-8f9d-f30bee2f60b3)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-008**](http://go.microsoft.com/fwlink/?linkid=238387)
</td>
<td style="border:1px solid black;">
[**MS12-010**](http://go.microsoft.com/fwlink/?linkid=236989)
</td>
<td style="border:1px solid black;">
[**MS12-013**](http://go.microsoft.com/fwlink/?linkid=238617)
</td>
<td style="border:1px solid black;">
[**MS12-016**](http://go.microsoft.com/fwlink/?linkid=235370)
</td>
<td style="border:1px solid black;">
[**MS12-009**](http://go.microsoft.com/fwlink/?linkid=238474)
</td>
<td style="border:1px solid black;">
[**MS12-012**](http://go.microsoft.com/fwlink/?linkid=239941)
</td>
<td style="border:1px solid black;">
[**MS12-014**](http://go.microsoft.com/fwlink/?linkid=239945)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Nessuno
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
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f0e6e06d-89db-45ad-9660-7959c6f9b546)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=c4642890-2fba-45da-bbe9-fcaa84e4aa0c)  
(Nessun livello di gravità<sup>[1]</sup>)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=9e157b88-2c11-44dc-b13d-1051f9c39890)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=bf8ad019-e710-4e16-be4f-8168df5c5343)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5269e18b-d4f0-4c64-8df8-283a2ca66c59)  
(KB2633880)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5ee4bef7-b355-4aae-8bba-834a16d44744)  
(Importante)
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
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b81decda-9d82-4ffb-baae-78b190e553ea)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=c4a52801-55b5-4eef-9db3-c29a45863198)  
(Nessun livello di gravità<sup>[1]</sup>)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=f162ad36-c096-43ba-a440-ec4d3fb54c21)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ef4a9002-b2da-40af-abc0-737565fea179)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5269e18b-d4f0-4c64-8df8-283a2ca66c59)  
(KB2633880)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b53cf810-0ea3-4cb0-91f9-de1406ccfc96)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
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
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=8dcd71c8-82ad-4f86-b386-7f1ea09e157f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=3b42f935-7f59-4871-a01f-480033c3ad40)  
(Nessun livello di gravità<sup>[1]</sup>)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=24fe7c08-4736-455b-9b98-1b6a65718143)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5269e18b-d4f0-4c64-8df8-283a2ca66c59)  
(KB2633880)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=3b18d22d-e192-498b-a105-b946a5f5bfad)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="8">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-008**](http://go.microsoft.com/fwlink/?linkid=238387)
</td>
<td style="border:1px solid black;">
[**MS12-010**](http://go.microsoft.com/fwlink/?linkid=236989)
</td>
<td style="border:1px solid black;">
[**MS12-013**](http://go.microsoft.com/fwlink/?linkid=238617)
</td>
<td style="border:1px solid black;">
[**MS12-016**](http://go.microsoft.com/fwlink/?linkid=235370)
</td>
<td style="border:1px solid black;">
[**MS12-009**](http://go.microsoft.com/fwlink/?linkid=238474)
</td>
<td style="border:1px solid black;">
[**MS12-012**](http://go.microsoft.com/fwlink/?linkid=239941)
</td>
<td style="border:1px solid black;">
[**MS12-014**](http://go.microsoft.com/fwlink/?linkid=239945)
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
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5852118c-fc39-45e2-8b44-ce1401d310e2)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=6ec23c7e-0166-47dc-ae86-c49b505206bb)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=bbf627df-0bc0-478f-aa34-a7e5f039e589)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=d287496a-411c-4c1b-9d98-bacc553041ae)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c503c7b1-24f8-40a4-8283-c1e4abf90b57)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=aab7826d-539b-4e36-b3a1-afa94b37dbe7)  
(KB2633874)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5161d16d-1037-49d5-8d4d-c353288cb41c)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=b30a8cc5-b9ad-476f-928c-c49c993d0e80)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=3a8b966a-bf34-42fd-8758-9a5e8e3c7689)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=22cc0245-1877-4c76-914f-dd68f6cd45f0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ddbd9fcf-10c4-4089-88c0-c2a6c288222b)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=aab7826d-539b-4e36-b3a1-afa94b37dbe7)  
(KB2633874)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=73e240a6-2d5e-4ceb-8500-8dacca0e4a43)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-008**](http://go.microsoft.com/fwlink/?linkid=238387)
</td>
<td style="border:1px solid black;">
[**MS12-010**](http://go.microsoft.com/fwlink/?linkid=236989)
</td>
<td style="border:1px solid black;">
[**MS12-013**](http://go.microsoft.com/fwlink/?linkid=238617)
</td>
<td style="border:1px solid black;">
[**MS12-016**](http://go.microsoft.com/fwlink/?linkid=235370)
</td>
<td style="border:1px solid black;">
[**MS12-009**](http://go.microsoft.com/fwlink/?linkid=238474)
</td>
<td style="border:1px solid black;">
[**MS12-012**](http://go.microsoft.com/fwlink/?linkid=239941)
</td>
<td style="border:1px solid black;">
[**MS12-014**](http://go.microsoft.com/fwlink/?linkid=239945)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=45c6c511-a4fa-4c3b-af26-6c113f6f5f5e)\*\*\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=21f7dba4-fe97-487e-8b37-45914e106db0)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=98d5b024-0eda-4e5d-ba9d-b828ad3d048e)\*\*  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=025a5af0-39f1-481c-920c-43d2b3d85dc5)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0c1812af-f57d-455d-a81d-5e03db99b2f7)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=aab7826d-539b-4e36-b3a1-afa94b37dbe7)  
(KB2633874)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3f6f89b3-3bc8-4325-b8d8-9a5a398b99c6)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=046932cf-0671-49e6-8ddf-98abfc97c5f0)\*\*\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=2cd8e296-dae8-41ce-8373-f8a71b4555e9)\*\*  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=246f9995-fe19-43d0-8f67-0e91eb961bab)\*\*  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=c216e01d-2f46-4a46-bdc7-9d0fe98193a3)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e1b66bb5-ea12-44a5-807a-f21ede0dc76d)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=aab7826d-539b-4e36-b3a1-afa94b37dbe7)  
(KB2633874)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0e06e77d-7e5d-4d57-98b2-0817f68a1ebb)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=35e6bd04-594f-42ef-97f8-abcf578b4f10)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=304bd0c5-f4ee-4f8c-89b4-4cbaaf418679)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=05c0e6eb-c641-43ab-958a-f43933cdbba7)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3a96ab34-8f45-48bf-a98b-9e683b50aaa0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=aab7826d-539b-4e36-b3a1-afa94b37dbe7)  
(KB2633874)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=56cbeba9-0c39-4418-9042-7244ac9d03db)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d1d51b26-2d01-42a9-9bb1-9fb82c1fb914)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="8">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-008**](http://go.microsoft.com/fwlink/?linkid=238387)
</td>
<td style="border:1px solid black;">
[**MS12-010**](http://go.microsoft.com/fwlink/?linkid=236989)
</td>
<td style="border:1px solid black;">
[**MS12-013**](http://go.microsoft.com/fwlink/?linkid=238617)
</td>
<td style="border:1px solid black;">
[**MS12-016**](http://go.microsoft.com/fwlink/?linkid=235370)
</td>
<td style="border:1px solid black;">
[**MS12-009**](http://go.microsoft.com/fwlink/?linkid=238474)
</td>
<td style="border:1px solid black;">
[**MS12-012**](http://go.microsoft.com/fwlink/?linkid=239941)
</td>
<td style="border:1px solid black;">
[**MS12-014**](http://go.microsoft.com/fwlink/?linkid=239945)
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
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=3e5ca1bf-9415-412c-9dff-dd1abc57e74d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=8b423683-cd29-4049-82d6-f0845842e7f0)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=c83a9c74-a5a7-4b3e-ba36-7a7024d99fd8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=403f355c-2273-42ac-8263-d662f5d7740c)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows 7 per sistemi a 32 bit:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5a5f3ee7-ca49-41c8-aeec-7c76b66712fc)  
(KB2633879)  
(Critico)  
Solo Windows 7 per sistemi a 32 bit Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=243e8c64-8b6e-4cea-9e99-58d4b1ad35b5)  
(KB2633873)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=78cbbe02-a3d3-4cef-9b54-a3e78c1b885a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=a5d00138-4e24-4a07-92dd-3d8a14476197)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=bbc9d6ae-9ec5-401f-bf16-4811b63709d1)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8bd8e804-ca4d-4326-bc60-345e2975b7aa)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows 7 per sistemi x64:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5a5f3ee7-ca49-41c8-aeec-7c76b66712fc)  
(KB2633879)  
(Critico)  
Solo Windows 7 per sistemi x64 Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=243e8c64-8b6e-4cea-9e99-58d4b1ad35b5)  
(KB2633873)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=299d107d-ab9f-42b6-8f94-a2f1d242c127)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-008**](http://go.microsoft.com/fwlink/?linkid=238387)
</td>
<td style="border:1px solid black;">
[**MS12-010**](http://go.microsoft.com/fwlink/?linkid=236989)
</td>
<td style="border:1px solid black;">
[**MS12-013**](http://go.microsoft.com/fwlink/?linkid=238617)
</td>
<td style="border:1px solid black;">
[**MS12-016**](http://go.microsoft.com/fwlink/?linkid=235370)
</td>
<td style="border:1px solid black;">
[**MS12-009**](http://go.microsoft.com/fwlink/?linkid=238474)
</td>
<td style="border:1px solid black;">
[**MS12-012**](http://go.microsoft.com/fwlink/?linkid=239941)
</td>
<td style="border:1px solid black;">
[**MS12-014**](http://go.microsoft.com/fwlink/?linkid=239945)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6b228ad6-d5a4-4b91-8aa8-0874deb22116)\*\*\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=3074a898-54bb-44ff-a8f4-77f831c28771)\*\*  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=1896a6da-f7ee-484b-a97c-455fce7b82b8)\*\*  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d868c5ef-165a-46a0-b832-e6ca55a910f9)\*  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 solo per sistemi x64:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5a5f3ee7-ca49-41c8-aeec-7c76b66712fc)\*  
(KB2633879)  
(Critico)  
Windows Server 2008 R2 solo per sistemi x64:  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi x64 Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=243e8c64-8b6e-4cea-9e99-58d4b1ad35b5)\*  
(KB2633873)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)\*<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=576192d3-f050-4718-a7da-c84fce6bf744)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=8c51e09b-51c3-4860-836e-6bcffde75f04)\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=922b2438-0cfc-49e3-b9a0-52c68b69126a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=7f7c0bc3-fc26-4ee8-aedb-c251247cbeb5)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=e5416371-495b-4dc7-a239-f9185f968969)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows Server 2008 R2 per sistemi Itanium:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=5a5f3ee7-ca49-41c8-aeec-7c76b66712fc)  
(KB2633879)  
(Critico)  
Solo Windows Server 2008 R2 per sistemi Itanium Service Pack 1:  
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=243e8c64-8b6e-4cea-9e99-58d4b1ad35b5)  
(KB2633873)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=70aadf34-abdc-4577-8da9-a0669dccc119)<sup>[1]</sup>
(KB2633870)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=d6a9b2c9-7582-4953-8ab1-a55c63fcc8dc)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=fba58a1b-9d9f-4a10-b1df-08a0ebfa2358)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Note per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*\*\*L'installazione di Server Core è interessata.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica un livello inferiore di gravità quando l'installazione viene eseguita usando l'opzione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione di un'installazione Server Core](http://technet.microsoft.com/it-it/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Nota per MS12-010**

<sup>[1]</sup>I livelli di gravità non sono applicabili a questo aggiornamento per il software specificato perché i vettori di attacco conosciuti per la vulnerabilità trattata in questo bollettino sono bloccati in una configurazione predefinita. Tuttavia, come misura di difesa in profondità, Microsoft consiglia ai clienti di questo software di applicare questo aggiornamento per la protezione.

**Nota per MS12-016**

<sup>[1]</sup>**.NET Framework 4 e .NET Framework 4 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4 e .NET Framework 4 Client Profile. .NET Framework 4 Client Profile è un sottoinsieme di .NET Framework 4. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4 sia .NET Framework 4 Client Profile. Per ulteriori informazioni, vedere l'articolo di MSDN, [Installazione di .NET Framework](http://msdn.microsoft.com/it-it/library/5a4x27ek.aspx).

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Altro software Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-015**](http://go.microsoft.com/fwlink/?linkid=238400)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visio Viewer 2010 e Microsoft Visio Viewer 2010 Service Pack 1 (edizione a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Visio Viewer 2010 e Microsoft Visio Viewer 2010 Service Pack 1 (edizione a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=173dc4e6-31b4-42ec-808c-f8cd005517ab)  
(KB2597170)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visio Viewer 2010 e Microsoft Visio Viewer 2010 Service Pack 1 (edizione a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Visio Viewer 2010 e Microsoft Visio Viewer 2010 Service Pack 1 (edizione a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=34b234e1-1322-4edc-829c-7bc2fbd99338)  
(KB2597170)  
(Importante)
</td>
</tr>
</table>
 

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft SharePoint Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-011**](http://go.microsoft.com/fwlink/?linkid=238500)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 e Microsoft SharePoint Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Server 2010 e Microsoft SharePoint Server 2010 Service Pack 1 (moss)](http://www.microsoft.com/downloads/details.aspx?familyid=44a8eb5a-e469-4d36-b5a0-7e030c1d3244)  
(KB2597124)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft SharePoint Foundation
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-011**](http://go.microsoft.com/fwlink/?linkid=238500)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Foundation 2010 e Microsoft SharePoint Foundation 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Foundation 2010 e Microsoft SharePoint Foundation 2010 Service Pack 1 (sts)](http://www.microsoft.com/downloads/details.aspx?familyid=dd348109-953b-4154-b265-85e4694238e6)  
(KB2553413)  
(Importante)
</td>
</tr>
</table>
 

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Silverlight
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-016**](http://go.microsoft.com/fwlink/?linkid=235370)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Silverlight 4
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c3602f0-9781-4374-8fef-669ddd2c0d40) installato in Mac  
(KB2668562)  
(Critico)  
[Microsoft Silverlight 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c3602f0-9781-4374-8fef-669ddd2c0d40) installato in tutte le versioni supportate dei client Microsoft Windows  
(KB2668562)  
(Critico)  
[Microsoft Silverlight 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c3602f0-9781-4374-8fef-669ddd2c0d40) installato in tutte le versioni supportate dei server Microsoft Windows  
(KB2668562)  
(Critico)
</td>
</tr>
</table>
 
**Nota per MS12-016**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/it-it/default.aspx). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/default.aspx).

**System Center Configuration Manager 2007**

La Gestione aggiornamenti software di Configuration Manager 2007 semplifica la consegna e la gestione degli aggiornamenti dei sistemi IT in tutta l'azienda. Con Configuration Manager 2007, gli amministratori IT possono consegnare gli aggiornamenti dei prodotti Microsoft a diverse periferiche compresi desktop, portatili, server e dispositivi mobili.

La valutazione automatica della vulnerabilità disponibile in Configuration Manager 2007 rileva la necessità di effettuare gli aggiornamenti ed invia relazioni sulle azioni consigliate. La Gestione aggiornamenti software di Configuration Manager 2007 si basa su Microsoft Windows Software Update Services (WSUS), un'infrastruttura di aggiornamento tempestiva conosciuta agli amministratori IT in tutto il mondo. Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare Configuration Manager 2007 per implementare gli aggiornamenti, vedere [Gestione aggiornamenti software](http://www.microsoft.com/systemcenter/en/us/configuration-manager/cm-software-update-management.aspx). Per ulteriori informazioni su Configuration Manager, visitare [System Center Configuration Manager](http://www.microsoft.com/systemcenter/en/us/configuration-manager.aspx).

**Systems Management Server 2003**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali.

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=dm;en-us;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager 2007; vedere anche **System Center Configuration Manager 2007**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/en/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f&displaylang=en). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/it-it/systemcenter/bb545936.aspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d&displaylang=en)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. I componenti del programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consentono di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/it-it/windowsserver/bb456965.aspx). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://go.microsoft.com/fwlink/?linkid=215201).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/it-it/default.aspx). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Tarjei Mandt di [Azimuth Security](http://www.azimuthsecurity.com/) per aver segnalato un problema descritto nel bollettino MS12-008
-   Tarjei Mandt di [Azimuth Security](http://www.azimuthsecurity.com/) per aver segnalato due problemi descritti nel bollettino MS12-009
-   [Jan Schejbal](http://janschejbal.wordpress.com/) per aver segnalato un problema descritto nel bollettino MS12-010
-   Stephen Fewer di [Harmony Security](http://www.harmonysecurity.com/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato due problemi descritti nel bollettino MS12-010
-   Jason Hullinger di [HP Cloud Services](http://www.hpcloud.com/) per aver segnalato un problema descritto nel bollettino MS12-010
-   John Hollenberger per aver segnalato un problema descritto nel bollettino MS12-011
-   Rocco Calvi di stratsec per aver segnalato un problema descritto nel bollettino MS12-011
-   Giorgio Fedon di Minded Security per aver collaborato con noi a un aggiornamento del sistema di difesa nel bollettino MS12-011
-   Alexander Gavrun, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS12-013
-   Xin Ouyang di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato cinque problemi descritti nel bollettino MS12-015
-   Jeroen Frijters di [Sumatra](http://www.sumatra.nl/) per aver segnalato un problema descritto nel bollettino MS12-016

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto &amp; Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (14 febbraio 2012): Pubblicazione del riepilogo dei bollettini.

*Built at 2014-04-18T01:50:00Z-07:00*
