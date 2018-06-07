---
TOCTitle: 'MS08-DEC'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - dicembre 2008'
ms:assetid: 'ms08-dec'
ms:contentKeyID: 61240020
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms08-dec(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - dicembre 2008
==================================================================

Data di pubblicazione: martedì 9 dicembre 2008 | Aggiornamento: mercoledì 29 aprile 2009

**Versione:** 6,0

Questo riepilogo elenca bollettini sulla sicurezza rilasciati a dicembre 2008.

Con il rilascio dei bollettini del mese di dicembre 2008, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 4 dicembre 2008. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 10 dicembre 2008 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i webcast dei bollettini sulla sicurezza di dicembre](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032374647). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Per il bollettino straordinario sulla sicurezza aggiunto alla versione 3.0 del presente riepilogo dei bollettini, MS08-078, Microsoft mette a disposizione due webcast per rispondere alle domande dei clienti su questi bollettini: il 17 dicembre 2008, all'1:00 ora del Pacifico (USA e Canada) e il 18 dicembre 2008, alle 11:00 ora del Pacifico. Registrazione immediata per il [webcast del 17 dicembre](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032399448&culture=en-us) e il [webcast del 18 dicembre](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032399449&culture=en-us). Successivamente, questi webcast saranno disponibili su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-071</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in GDI possono consentire l'esecuzione di codice in modalità remota (956802)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in GDI. Lo sfruttamento di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file di immagine WMF appositamente predisposto. Sfruttando queste vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-075</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Ricerca di Windows possono consentire l'esecuzione di codice in modalità remota (959349)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Ricerca di Windows. Tali vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre e salva un file di ricerca salvato all'interno di Esplora risorse o seleziona un URL di ricerca appositamente predisposto. Sfruttando queste vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-073">MS08-073</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (958215)</strong><br />
<br />
Questo aggiornamento per la protezione risolve quattro vulnerabilità segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-078">MS08-078</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento per la protezione di Internet Explorer (960714)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Internet Explorer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-070</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità dei file estesi (controlli ActiveX) del runtime di Visual Basic 6.0 possono consentire l'esecuzione di codice in modalità remota (932349)</strong><br />
<br />
Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente e una vulnerabilità divulgata pubblicamente dei controlli ActiveX per i file estesi del runtime di Microsoft Visual Basic 6.0. Tali vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente esplora un sito Web che presenta del contenuto appositamente predisposto. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Strumenti e software Microsoft per gli sviluppatori, Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-072</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (957173)</strong><br />
<br />
Questo aggiornamento per la protezione risolve otto vulnerabilità di Microsoft Office Word e Microsoft Office Outlook che possono consentire l'esecuzione di codice in modalità remota se un utente apre un file di Word o RTF (Rich Text Format) appositamente predisposto. Tali vulnerabilità sono state segnalate a Microsoft privatamente. Sfruttando queste vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-074</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (959070)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità riscontrate in Microsoft Office Excel che possono consentire l'esecuzione di codice in modalità remota al momento dell'apertura di un file Excel appositamente predisposto. Tali vulnerabilità sono state segnalate a Microsoft privatamente. Sfruttando queste vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-077</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità di Microsoft Office SharePoint Server può consentire l'acquisizione di privilegi più elevati (957175)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato elude l'autenticazione accedendo a un URL amministrativo in un sito SharePoint. Un attacco riuscito volto all'acquisizione di privilegi più elevati potrebbe risultare in un attacco di tipo Denial of Service o nell'intercettazione di informazioni personali.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office, Software dei server Microsoft</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-076</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità dei componenti Windows Media possono consentire l'esecuzione di codice in modalità remota (959807)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente relative ai seguenti componenti Windows Media: Windows Media Player, Runtime formato Windows Media e i Servizi Windows Media. La vulnerabilità più grave può consentire l'esecuzione di codice in modalità remota. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato che sfrutti questa vulnerabilità può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).

 
<table style="border:1px solid black;">
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID bollettino</th>
<th style="border:1px solid black;" >Titolo del bollettino</th>
<th style="border:1px solid black;" >ID CVE</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability Index</th>
<th style="border:1px solid black;" >Note fondamentali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-070</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità dei file estesi (controlli ActiveX) del runtime di Visual Basic 6.0 possono consentire l'esecuzione di codice in modalità remota (932349)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-3704">CVE-2008-3704</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Del codice dannoso è disponibile pubblicamente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-070</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità dei file estesi (controlli ActiveX) del runtime di Visual Basic 6.0 possono consentire l'esecuzione di codice in modalità remota (932349)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4252">CVE-2008-4252</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-070</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità dei file estesi (controlli ActiveX) del runtime di Visual Basic 6.0 possono consentire l'esecuzione di codice in modalità remota (932349)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4256">CVE-2008-4256</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-070</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità dei file estesi (controlli ActiveX) del runtime di Visual Basic 6.0 possono consentire l'esecuzione di codice in modalità remota (932349)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4253">CVE-2008-4253</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-070</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità dei file estesi (controlli ActiveX) del runtime di Visual Basic 6.0 possono consentire l'esecuzione di codice in modalità remota (932349)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4254">CVE-2008-4254</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-070</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità dei file estesi (controlli ActiveX) del runtime di Visual Basic 6.0 possono consentire l'esecuzione di codice in modalità remota (932349)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4255">CVE-2008-4255</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">La vulnerabilità interessa principalmente i sistemi Windows 2000. I sistemi operativi Windows XP SP2, Windows Server 2003 SP1 e successivi sono scarsamente interessati dalla vulnerabilità a causa di migliori protezioni degli heap.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-071</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità in GDI possono consentire l'esecuzione di codice in modalità remota (956802)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-3465">CVE-2008-3465</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-071</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità in GDI possono consentire l'esecuzione di codice in modalità remota (956802)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-2249">CVE-2008-2249</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-072</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (957173)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4024">CVE-2008-4024</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-072</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (957173)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4025">CVE-2008-4025</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-072</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (957173)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4026">CVE-2008-4026</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-072</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (957173)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4027">CVE-2008-4027</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-072</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (957173)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4028">CVE-2008-4028</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-072</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (957173)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4030">CVE-2008-4030</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-072</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (957173)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4837">CVE-2008-4837</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-072</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (957173)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4031">CVE-2008-4031</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-073">MS08-073</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (958215)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4258">CVE-2008-4258</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-073">MS08-073</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (958215)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4259">CVE-2008-4259</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-073">MS08-073</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (958215)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4261">CVE-2008-4261</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-073">MS08-073</a></td>
<td style="border:1px solid black;">Aggiornamento cumulativo per la protezione di Internet Explorer (958215)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4260">CVE-2008-4260</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-074</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (959070)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4265">CVE-2008-4265</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-074</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (959070)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4266">CVE-2008-4266</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-074</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (959070)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4264">CVE-2008-4264</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-075</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità in Ricerca di Windows possono consentire l'esecuzione di codice in modalità remota (959349)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4269">CVE-2008-4269</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-075</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità in Ricerca di Windows possono consentire l'esecuzione di codice in modalità remota (959349)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4268">CVE-2008-4268</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-076</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità dei componenti Windows Media possono consentire l'esecuzione di codice in modalità remota (959807)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-3009">CVE-2008-3009</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">È possibile creare del codice dannoso per sfruttare questa vulnerabilità. È tuttavia improbabile che si verifichino degli attacchi effettivi.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-076</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità dei componenti Windows Media possono consentire l'esecuzione di codice in modalità remota (959807)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-3010">CVE-2008-3010</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">È possibile creare del codice dannoso per sfruttare questa vulnerabilità. È tuttavia improbabile che si verifichino degli attacchi effettivi.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx">MS08-077</a></td>
<td style="border:1px solid black;">Una vulnerabilità di Microsoft Office SharePoint Server può consentire l'acquisizione di privilegi più elevati (957175)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4032">CVE-2008-4032</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">È possibile creare del codice dannoso per sfruttare questa vulnerabilità. È tuttavia probabile che eventuali attacchi provochino solo l'intercettazione di informazioni personali e non l'esecuzione di codice in modalità remota.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-078">MS08-078</a></td>
<td style="border:1px solid black;">Aggiornamento per la protezione di Internet Explorer (960714)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2008-4844">CVE-2008-4844</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità<br />
(pubblico al momento del rilascio del bollettino)</td>
<td style="border:1px solid black;">In alcuni attacchi attivi è stato rinvenuto del codice dannoso. Tuttavia, Internet Explorer viene eseguito in Modalità protetta con le installazioni predefinite di Windows Vista e Windows Server 2008, rendendo più difficile lo sfruttamento di tale vulnerabilità.</td>
</tr>
</tbody>
</table>
  
Software interessato e posizioni per il download  
------------------------------------------------
  
<span></span>
**Come utilizzare questa tabella**
  
È possibile utilizzare questa tabella per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se è necessario applicare i relativi aggiornamenti per la protezione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.
  
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
</tr>
<tr>
<th colspan="6">
Microsoft Windows 2000  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-071**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-075**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-073**](http://technet.microsoft.com/security/bulletin/ms08-073)
</td>
<td style="border:1px solid black;">
[**MS08-078**](http://technet.microsoft.com/security/bulletin/ms08-078)
</td>
<td style="border:1px solid black;">
[**MS08-076**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=3b775fb1-1077-455d-af4a-4ccb5237974f)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 5.01 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=c242ba42-556b-4c87-bf33-9d99166ff096)  
(Critico)  
[Microsoft Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c0583745-7e57-4265-9429-c3415cb8465f)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 5.01 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=d3e18732-47f1-40ce-999c-d1fd283bf138)  
(Critico)  
[Microsoft Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=124c14b6-9323-4f6f-902b-727aa56444bc)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 6.4](http://www.microsoft.com/downloads/details.aspx?familyid=c33d558e-45f9-4e85-b48c-03bd0e8cb4bc)  
(KB954600)  
(Importante)  
[Runtime formato Windows Media 7.1 e Runtime formato Windows Media 9.0](http://www.microsoft.com/downloads/details.aspx?familyid=6a459497-0ab8-41cb-87d0-b551631d8d8a)  
(KB952069)  
(Importante)  
[Servizi Windows Media 4.1](http://www.microsoft.com/downloads/details.aspx?familyid=58b7d241-cef6-48fa-aa52-017695f71db1)  
(KB952068)  
(Importante)
</td>
</tr>
<tr>
<th colspan="6">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-071**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-075**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-073**](http://technet.microsoft.com/security/bulletin/ms08-073)
</td>
<td style="border:1px solid black;">
[**MS08-078**](http://technet.microsoft.com/security/bulletin/ms08-078)
</td>
<td style="border:1px solid black;">
[**MS08-076**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2 e Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=2151fbba-c464-4d1e-82d4-5b096e82bed0)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=af9a6cb0-725d-490c-9858-16ec40e98560)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=1b582695-b3cc-4c65-bc4b-d673c9a6d82a)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=1d83e0af-46fa-4bfc-ba57-635435a7ef2d)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=0190a289-164e-41a7-8c01-fa1aaed3f531)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 6.4](http://www.microsoft.com/downloads/details.aspx?familyid=99241309-e644-4088-a8f3-38837fab4037)  
(KB954600)  
(Importante)  
[Runtime formato Windows Media 9.0, Runtime formato Windows Media 9.5 e Runtime formato Windows Media 11](http://www.microsoft.com/downloads/details.aspx?familyid=504f816c-f554-4b93-ac28-b085574d9bac)  
(solo Windows XP Service Pack 2)  
(KB952069)  
(Importante)  
[Runtime formato Windows Media 9.0, Runtime formato Windows Media 9.5 e Runtime formato Windows Media 11](http://www.microsoft.com/downloads/details.aspx?familyid=ad76fcf3-a2f9-4e36-bd1b-c1536749173c)  
(solo Windows XP Service Pack 3)  
(KB952069)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=2247f6a5-aa33-4c68-9ea8-a63488d126d3)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=60bf9851-24fe-4658-8333-d353e82063c7)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=107cf54b-29d4-4c54-b091-2b5b3ffbf49d)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=a585cb73-2c1a-4fa8-862a-ad6aeaeaf2f8)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=9ba71e23-8cef-4399-b215-983b0dcf5cb5)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 6.4](http://www.microsoft.com/downloads/details.aspx?familyid=946d47c9-b208-4fab-8ef6-774413d61bc8)  
(KB954600)  
(Importante)  
[Runtime formato Windows Media 9.5](http://www.microsoft.com/downloads/details.aspx?familyid=644ef023-ee40-45b0-9c9d-c76d9fab0005)  
(KB952069)  
(Importante)  
[Runtime formato Windows Media 9.5 x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=ae9e8b07-5354-42f3-a226-ba2193244524)  
(KB952069)  
(Importante)  
[Runtime formato Windows Media 11](http://www.microsoft.com/downloads/details.aspx?familyid=2dadc017-2be5-4240-ab8f-0291756dca6b)  
(KB952069)  
(Importante)
</td>
</tr>
<tr>
<th colspan="6">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-071**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-075**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-073**](http://technet.microsoft.com/security/bulletin/ms08-073)
</td>
<td style="border:1px solid black;">
[**MS08-078**](http://technet.microsoft.com/security/bulletin/ms08-078)
</td>
<td style="border:1px solid black;">
[**MS08-076**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0c396796-0929-4cd2-99e8-3c0f7075a89e)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=d53adf6f-9501-4862-a1ca-57eb4d40cd75)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=9cdd4f9e-c578-405c-af9e-628f2d77fdf4)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=d81e9cf9-ce0c-463a-a359-49a348cb89ae)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=388847ec-817e-45cf-8fa7-32c7e1f57f80)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 6.4](http://www.microsoft.com/downloads/details.aspx?familyid=2315ce20-2f46-42c2-bb40-045f003409d7)  
(KB954600)  
(Importante)  
[Runtime formato Windows Media 9.5](http://www.microsoft.com/downloads/details.aspx?familyid=d8958248-c889-499e-a6a9-3b394cdb27ea)  
(KB952069)  
(Importante)  
[Servizi Windows Media 9](http://www.microsoft.com/downloads/details.aspx?familyid=e71abc2d-d60e-444a-9b7b-062c5805fe9e)  
(KB952068)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6d5c7d2f-1a82-4cdf-b3f2-b2c2390c6a64)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=5e37cb34-32be-4bbe-87f3-c4e1974e4d00)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=7c36f92c-d8a0-4b70-b85f-83588a0299a0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=015df302-d79f-43a1-b5c5-32ac04de0510)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=2ae17caf-6204-470e-8480-380d3d505657)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Media Player 6.4](http://www.microsoft.com/downloads/details.aspx?familyid=4c29bed9-1b88-4d2f-80a5-305c2bedd89f)  
(KB954600)  
(Importante)  
[Runtime formato Windows Media 9.5](http://www.microsoft.com/downloads/details.aspx?familyid=2278022e-a716-46c0-bedf-d626933bd815)  
(KB952069)  
(Importante)  
[Runtime formato Windows Media 9.5 x64 Edition](http://www.microsoft.com/downloads/details.aspx?familyid=ae9e8b07-5354-42f3-a226-ba2193244524)  
(KB952069)  
(Importante)  
[Servizi Windows Media 9](http://www.microsoft.com/downloads/details.aspx?familyid=e0030155-1a9a-46cc-bbc8-6d0d1ed65c1f)  
(KB952068)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=1edb62b4-3d0f-4891-b4b3-8f8bc4e7bdfe)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=0da4e424-4682-4401-a226-7d8f1be19d44)  
(Moderato)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=3811030d-5958-4b91-b5b8-20587dc7c4d6)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=18016305-7f72-47f6-ab4c-94282289bf5f)  
(Critico)  
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=97d6c093-f68d-4ddf-8e3c-f29662a1940f)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="6">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-071**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-075**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-073**](http://technet.microsoft.com/security/bulletin/ms08-073)
</td>
<td style="border:1px solid black;">
[**MS08-078**](http://technet.microsoft.com/security/bulletin/ms08-078)
</td>
<td style="border:1px solid black;">
[**MS08-076**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista e Windows Vista Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=cddf9cf6-bdeb-4429-823a-879387a428d7)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0dcc5373-0435-42d5-864d-298e5bb122d9)  
(KB958623)  
(Importante)  
[Windows Vista e Windows Vista Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5b1b65f0-6848-47c6-bdd5-be3c0621b323)  
(KB958624)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=3f62030a-9ce2-4c92-b948-143a6881921e)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=7887111d-4fac-4823-bdd2-a18d9468fdf0)  
(Critico)
</td>
<td style="border:1px solid black;">
[Runtime formato Windows Media 11](http://www.microsoft.com/downloads/details.aspx?familyid=1fcdc8dd-26d9-4d1a-8b3f-7b6a21a95999)  
(KB952069)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=73dc3775-b6f0-40f1-bd36-6b5fb80eb2fa)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=2112c5c8-7c9f-4491-b127-b1093085e105)  
(KB958623)  
(Importante)  
[Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=eb1d0ffe-1644-457b-9e82-768bd4c7f7ab)  
(KB958624)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=d8800493-fba4-41f8-bde5-a53eeaf89d54)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=69979d92-8d45-47fe-ac4c-c2f1f23cf1fb)  
(Critico)
</td>
<td style="border:1px solid black;">
[Runtime formato Windows Media 11](http://www.microsoft.com/downloads/details.aspx?familyid=8839f6cd-dfbf-448c-bf1e-1da9bb5f3f25)  
(KB952069)  
(Importante)
</td>
</tr>
<tr>
<th colspan="6">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-071**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-075**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-073**](http://technet.microsoft.com/security/bulletin/ms08-073)
</td>
<td style="border:1px solid black;">
[**MS08-078**](http://technet.microsoft.com/security/bulletin/ms08-078)
</td>
<td style="border:1px solid black;">
[**MS08-076**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=bbed9e8b-e75e-44ef-ba1d-fd6f852c1f67)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=90ab7e6f-5ae7-4f55-8838-868fc98d8a16)\*\*\*  
(KB958623)  
(Importante)  
[Windows Server 2008 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=470d506f-77ae-4a44-8598-df645f484295)\*\*\*  
(KB958624)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=45a0de3c-c7d1-4314-a456-1f7428b7c90a)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=5552e564-dd1c-4e2a-9a42-6317522c884d)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Runtime formato Windows Media 11](http://www.microsoft.com/downloads/details.aspx?familyid=91ec4195-bc1c-444e-a7b0-ebde46c088fa)  
(KB952069)  
(Importante)  
[Servizi Windows Media 2008](http://www.microsoft.com/downloads/details.aspx?familyid=ffb5d945-7f98-4849-b020-ed4873fa42df)\*  
(KB952068)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
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
[Servizi Windows Media 2008](http://www.microsoft.com/downloads/details.aspx?familyid=ffb5d945-7f98-4849-b020-ed4873fa42df)\*  
(KB952068)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi basati su x64
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=48aecf4c-1296-490d-ba37-a28e3ec19bd6)\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=e1deab57-ada2-4b12-9157-5615e7b0071d)\*\*\*  
(KB958623)  
(Importante)  
[Windows Server 2008 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=e41f23e4-6a2f-4ebb-b425-d241a08da316)\*\*\*  
(KB958624)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=405b28db-47d7-4d6b-90e6-834c0a409323)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=889c6eb1-7d1f-4e60-b637-535cb6e4e443)\*\*  
(Critico)
</td>
<td style="border:1px solid black;">
[Runtime formato Windows Media 11](http://www.microsoft.com/downloads/details.aspx?familyid=8cab6fe8-161d-4d8c-9772-eb3174a2c3c3)  
(KB952069)  
(Importante)  
[Servizi Windows Media 2008](http://www.microsoft.com/downloads/details.aspx?familyid=0204a366-5641-4036-9cb0-a46d04af9d72)\*  
(KB952068)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
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
[Servizi Windows Media 2008](http://www.microsoft.com/downloads/details.aspx?familyid=0204a366-5641-4036-9cb0-a46d04af9d72)\*  
(KB952068)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=9bfe15cd-02ff-45cf-85c8-5ff1e6c1a871)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=48bed90d-c243-4969-8e54-326d9a7af343)  
(KB958623)  
(Importante)  
[Windows Server 2008 per sistemi basati su Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=83de2263-de2a-4c13-96ba-ecfebdaf0bb9)  
(KB958624)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=f0d4f321-941e-4da7-958f-582c75542ee8)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=06cb502a-6818-4599-aa24-6eddb83e4b84)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Nota per MS08-078**

La vulnerabilità risolta dal bollettino MS08-078 è stata segnalata dopo il rilascio di Windows Internet Explorer 8 Beta 2. Ai clienti che utilizzano Windows Internet Explorer 8 Beta 2 si consiglia di scaricare e applicare l'aggiornamento nei sistemi in uso.

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

**Note per Windows Server 2008**

**\*Sono interessate le installazione di Windows Server 2008 con opzione Server Core.** Per le edizioni supportate di Windows Server 2008, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Windows Server 2008 con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008, se Windows Server 2008 è stato installato utilizzando l'opzione di installazione Server Core. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*\*Le installazioni di Windows Server 2008 con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questi aggiornamenti non interessano le edizioni supportate di Windows Server 2008, se Windows Server 2008 è stato installato utilizzando l'opzione di installazione Server Core, anche se i file interessati da queste vulnerabilità sono presenti nel sistema. L'aggiornamento viene comunque offerto agli utenti che dispongono dei file interessati, poiché i file dell'aggiornamento sono più recenti (con numeri di versione più elevati) rispetto a quelli attualmente presenti nel sistema. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

#### Suite e software Microsoft Office

 
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
</tr>
<tr>
<th colspan="5">
Applicazioni, sistemi e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-070**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-072**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-074**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-077**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2000 Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=43e8c4d8-307b-48f6-ac99-a9617421d40a)  
(KB956328)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f39d2a49-f861-4f2d-bf91-94a8a85af40c)  
(KB958435)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=3ef41412-50b3-4077-b0e3-9a3704d2f876)  
(KB956329)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=72076e21-2aa3-48e8-883a-c3cb756fc72a)  
(KB958372)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=45c81c60-4b1b-4246-839b-198ebc4eeae2)  
(KB956357)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=6c0771e5-fcd4-4365-b903-1a3bd95d9e66)  
(KB958436)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office System 2007
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2007](http://www.microsoft.com/downloads/details.aspx?familyid=5b51cb5e-3899-4257-82cf-7e92fa619c37)  
(KB956358)  
(Importante)  
[Microsoft Office Outlook 2007](http://www.microsoft.com/downloads/details.aspx?familyid=5b51cb5e-3899-4257-82cf-7e92fa619c37)  
(KB956358)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2007](http://www.microsoft.com/downloads/details.aspx?familyid=68bb8d99-f28b-4efd-9314-3eee0bb00ccf)  
(KB958437)\*\*\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office System 2007 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Word 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5b51cb5e-3899-4257-82cf-7e92fa619c37)  
(KB956358)  
(Importante)  
[Microsoft Office Outlook 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=5b51cb5e-3899-4257-82cf-7e92fa619c37)  
(KB956358)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=68bb8d99-f28b-4efd-9314-3eee0bb00ccf)  
(KB958437)\*\*\*\*  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office FrontPage
</td>
<td style="border:1px solid black;">
[Microsoft Office FrontPage 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=0a6130ae-c5b4-43cb-afe3-ab6a55b9d9ea)\*  
(KB957797)  
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
Microsoft Office Project
</td>
<td style="border:1px solid black;">
[Microsoft Office Project 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=89a44042-a629-40f3-800a-0bb45fc36591)  
(KB949045)  
(Critico)  
[Microsoft Office Project 2007](http://www.microsoft.com/downloads/details.aspx?familyid=2fbf6a5b-ff35-4a2d-9fa0-4e62b6486fe6)  
(KB949046)  
(Critico)  
[Microsoft Office Project 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=2fbf6a5b-ff35-4a2d-9fa0-4e62b6486fe6)  
(KB949046)  
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
<th colspan="5">
Microsoft Office per Mac
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-070**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-072**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-074**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-077**](http://technet.microsoft.com/it-it/security/default.aspx)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
[Microsoft Office 2004 per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=eca13ad8-62ae-41a8-b308-41e2d1773820)\*\*  
(KB960402)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=eca13ad8-62ae-41a8-b308-41e2d1773820)\*\*  
(KB960402)  
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
[Microsoft Office 2008 per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=ab31a564-43d2-45bd-98bf-19e9ca477b62)\*\*  
(KB960401)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=ab31a564-43d2-45bd-98bf-19e9ca477b62)\*\*  
(KB960401)  
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
[Convertitore file in formato XML aperto per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=edb6cd8f-832c-4123-8982-ac0c601ea0a7)\*\*  
(KB960403)  
(Importante)
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=edb6cd8f-832c-4123-8982-ac0c601ea0a7)\*\*  
(KB960403)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="5">
Altro software Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-070**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-072**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-074**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
<td style="border:1px solid black;">
[**MS08-077**](http://technet.microsoft.com/it-it/security/default.aspx)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Works
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Works 8](http://www.microsoft.com/downloads/details.aspx?familyid=1537d181-90d9-4bb5-b5ae-8d9990a349af)\*\*\*  
(KB959487)  
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
Microsoft Office Excel Viewer
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel Viewer 2003](http://www.microsoft.com/downloads/details.aspx?familyid=4b3989ef-02b8-4bd2-b2ab-c3716079936e)  
(KB958434)  
(Importante)  
[Microsoft Office Excel Viewer 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=4b3989ef-02b8-4bd2-b2ab-c3716079936e)  
(KB958434)  
(Importante)  
[Microsoft Office Excel Viewer](http://www.microsoft.com/downloads/details.aspx?familyid=9dbb35c1-aa7a-481b-a330-8ba916ddd443)  
(KB958442)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Word Viewer
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Word Viewer 2003 Service Pack 3 e Microsoft Office Word Viewer](http://www.microsoft.com/downloads/details.aspx?familyid=70de7c3c-519f-4f4a-a03f-027f80b5415c)  
(KB956366)  
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
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007](http://www.microsoft.com/downloads/details.aspx?familyid=55430121-4476-48b8-9f6f-4a60fa0b2970)  
(KB956828)  
(Importante)  
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=55430121-4476-48b8-9f6f-4a60fa0b2970)  
(KB956828)  
(Importante)
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007](http://www.microsoft.com/downloads/details.aspx?familyid=99cca4ed-f1f9-4cfd-a986-edbec82ced4f)  
(KB958439)  
(Importante)  
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=99cca4ed-f1f9-4cfd-a986-edbec82ced4f)  
(KB958439)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office SharePoint Server 2007
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
[Microsoft Office SharePoint Server 2007 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=f8f73997-6f4c-4b43-aa50-5c8276e83d3e)  
(KB956716)  
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=f8f73997-6f4c-4b43-aa50-5c8276e83d3e)  
(KB956716)  
(Importante)  
[Microsoft Office SharePoint Server 2007 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=a7fda284-273c-42ab-8188-433beaacca86)  
(KB956716)  
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=a7fda284-273c-42ab-8188-433beaacca86)  
(KB956716)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS08-070**
Per ulteriori file di aggiornamento, vedere anche la sezione seguente, **Strumenti e software Microsoft per gli sviluppatori**. Questo bollettino è relativo sia a Microsoft Office che a Strumenti e software Microsoft per gli sviluppatori.

**Nota per MS08-077**
Per ulteriori file di aggiornamento, vedere anche la sezione seguente, **Software dei server Microsoft**. Questo bollettino è relativo sia a Suite e software Microsoft Office che a Software dei server Microsoft.

**Nota per Microsoft Office Frontpage in MS08-070**
\*Questo aggiornamento si applica soltanto alle versioni in cinese semplificato (Cina), pan-cinese (Hong Kong), cinese tradizionale (Taiwan) e coreano di Frontpage 2002 Service Pack 3.

**Nota per Microsoft Office per MAC in MS08-072 e MS08-074**
\*\*Gli aggiornamenti corrispondenti sono identici tra MS08-072 e MS08-074. Poiché le vulnerabilità sono negli stessi file, questi aggiornamenti sono uguali per entrambi i bollettini.

**Nota per Works 8 in MS08-072**
\*\*\*Per ricevere questo aggiornamento per la protezione, gli utenti di Microsoft Works 8.0 devono eseguire preventivamente l'aggiornamento a Works 8.5, come descritto in [Microsoft Works Update](http://www.microsoft.com/products/works/international/update_1001.mspx). Devono effettuare tale aggiornamento tutti i clienti che utilizzano Microsoft Works 8.0, Works Suite 2004 e Works Suite 2005. Works 8.5 è già incluso in Works Suite 2006.

**Nota per Microsoft Office Excel 2007 e Microsoft Office Excel 2007 Service Pack 1 nel bollettino MS08-074**
\*\*\*\*For Microsoft Office Excel 2007 e Microsoft Office Excel 2007 Service Pack 1, oltre al pacchetto di aggiornamento per la protezione KB958437, i clienti devono installare anche l'aggiornamento per la protezione per il [Pacchetto di compatibilità di Microsoft Office per i file in formato Word, Excel e PowerPoint 2007](http://www.microsoft.com/downloads/details.aspx?familyid=99cca4ed-f1f9-4cfd-a986-edbec82ced4f) (KB958439) per essere protetti dalle vulnerabilità descritte nel bollettino MS08-074. Per i clienti che hanno già installato entrambi i pacchetti di aggiornamento KB958437 e KB958439, non è necessario eseguire una nuova installazione.

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Visual Studio
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-070**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual Basic
</td>
<td style="border:1px solid black;">
[File estesi del runtime di Microsoft Visual Basic 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=e27eebcb-095d-43ec-a19e-4a46e591715c)  
(KB926857)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Studio .NET
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio .NET 2002 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=afad980d-7f27-49d9-aa23-b762c7b94cd6)  
(KB958392)  
(Critico)  
[Microsoft Visual Studio .NET 2003 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6ac7cf8f-d046-43a8-b4ef-253153d65aed)  
(KB958393)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual FoxPro
</td>
<td style="border:1px solid black;">
[Microsoft Visual FoxPro 8.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a6977f81-f7f6-486b-96ad-8d296d79f205)  
(KB958369)  
(Critico)  
[Microsoft Visual FoxPro 9.0 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=386d27a6-b2c7-4acc-bf3e-edcbc7358172)  
(KB958370)  
(Critico)  
[Microsoft Visual FoxPro 9.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5b1f28a9-da8d-463a-8ae4-dfc8fcc6c41a)  
(KB958371)  
(Critico)
</td>
</tr>
</table>
 
**Nota per MS08-070**
Per ulteriori file di aggiornamento, vedere anche la sezione seguente, **Suite e software Microsoft Office**. Questo bollettino è relativo sia a Suite e software Microsoft Office che a Strumenti e software Microsoft per gli sviluppatori.

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
Server di ricerca
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS08-077**](http://technet.microsoft.com/it-it/security/default.aspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Search Server
</td>
<td style="border:1px solid black;">
[Microsoft Search Server 2008 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=f8f73997-6f4c-4b43-aa50-5c8276e83d3e)\*  
(KB956716)  
(Importante)  
[Microsoft Search Server 2008 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=a7fda284-273c-42ab-8188-433beaacca86)\*\*  
(KB956716)  
(Importante)
</td>
</tr>
</table>
 
**Note per MS08-077**

\* Comprende Microsoft Search Server 2008 Express (edizioni a 32 bit)

\*\* Comprende Microsoft Search Server 2008 Express (edizioni a 64 bit)

Per ulteriori file di aggiornamento, vedere anche la sezione seguente, **Suite e software Microsoft Office**. Questo bollettino è relativo sia a Suite e software Microsoft Office che a Software dei server Microsoft.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/updatemanagement/default.aspx). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it), [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Office Update.](http://office.microsoft.com/it-it/downloads/default.aspx) Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Informazioni sul rilevamento e sulla distribuzione**

Per gli aggiornamenti per la protezione di questo mese Microsoft ha fornito informazioni sul rilevamento e sulla distribuzione. Tali informazioni consentono inoltre ai professionisti IT di apprendere come utilizzare diversi strumenti per distribuire gli aggiornamenti per la protezione, quali Windows Update, Microsoft Update, Office Update, Microsoft Baseline Security Analyzer (MBSA), Office Detection Tool, Microsoft Systems Management Server (SMS) ed Extended Security Update Inventory Tool (ESUIT). Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 910723](http://support.microsoft.com/kb/910723).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://technet.microsoft.com/it-it/sms/bb676802.aspx) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/it-it/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676767.aspx) e in [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676800.aspx).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc766043.aspx), incluso nell'[Application Compatibility Toolkit 5.0](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche relative a Software Update Services e Windows Server Update Services nei contenuti del 2008. Include tutti i contenuti Windows.
-   [Aggiornamenti nuovi, rivisti e rilasciati per i prodotti Microsoft diversi da Microsoft Windows](http://technet.microsoft.com/it-it/wsus/bb466214.aspx).

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://www.microsoft.com/security/msrc/mapp/partners.mspx).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/it-it/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/it-it/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://www.microsoft.com/italy) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   ADLab di [VenusTech](http://www.venustech.com.cn/) per aver segnalato diversi problemi descritti nel bollettino MS08-070
-   Jason Medeiros di [Affiliated Computer Services](http://www.acs-inc.com/) per aver segnalato un problema descritto nel bollettino MS08-070
-   Carsten Eiram di [Secunia Research](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS08-070
-   Mark Dowd di [McAfee Avert Labs](http://www.avertlabs.com/) per aver segnalato un problema descritto nel bollettino MS08-070
-   Brett Moore di [Insomnia Security](http://www.insomniasec.com/) per avere segnalato un problema descritto nel bollettino MS08-070
-   CHkr\_D591, che collabora con [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-070
-   Michal Bucko di [CERT/CC](http://www.cert.org/) per aver segnalato un problema descritto nel bollettino MS08-070
-   Il [Security Intelligence Analysis Team](http://www.symantec.com/) di Symantec per avere collaborato con noi allo studio di un problema descritto nel bollettino MS08-070
-   Jun Mao di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS08-071
-   Juan Caballero, collaboratore del gruppo [Bitblaze presso la Carnegie Mellon University e la UC Berkeley](http://bitblaze.cs.berkeley.edu/), per aver segnalato un problema descritto nel bollettino MS08-071
-   Ricardo Narvaja di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato un problema descritto nel bollettino MS08-072
-   Dyon Balding di [Secunia Research](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS08-072
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS08-072
-   Wushi, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-072
-   Aaron Portnoy di [TippingPoint DVLabs](http://dvlabs.tippingpoint.com/) per aver segnalato alcuni problemi descritti nel bollettino MS08-072
-   Wushi del [team509](http://www.team509.com/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-072
-   Wushi e Ling, collaboratori di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-072
-   Carlo Di Dato (Shinnai) per aver segnalato un problema descritto nel bollettino MS08-073
-   Brett Moore, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-073
-   Chris Weber di [Casaba Security](http://www.casabasecurity.com/) per aver segnalato un problema descritto nel bollettino MS08-073
-   Jun Mao di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS08-073
-   Joshua J. Drake di [Verisign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS07-074
-   Claes M Nyberg di [signedness.org](http://www.signedness.org/) per aver segnalato un problema descritto nel bollettino MS08-074
-   Dyon Balding di [Secunia](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS07-074
-   Andre Protas di [eEye Digital Security](http://www.eeye.com/) per aver segnalato un problema descritto nel bollettino MS08-075
-   Nate McFeters per aver segnalato un problema descritto nel bollettino MS08-075
-   Un utente anonimo per aver segnalato un problema descritto nel bollettino MS08-077

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://support.microsoft.com/?ln=it&x=15&y=11). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (9 dicembre 2008) : Pubblicazione del riepilogo dei bollettini.
-   V2.0 (10 dicembre 2008): È stata corretta la tabella Software interessato per MS08-076 per registrare Runtime formato Windows Media 9.5 e Runtime formato Windows Media 11 come aggiornamenti separati in Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2. Sono stati inoltre eliminati i riferimenti errati a Runtime formato Windows Media 11 x64 Edition in Windows XP Professional x64 Edition, Windows XP Professional x64 Edition Service Pack 2, Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2 per MS08-076.
-   V3.0 (17 dicembre 2008): è stato aggiunto il bollettino Microsoft sulla sicurezza MS08-078, Aggiornamento per la protezione di Internet Explorer (960714). Sono stati inoltre aggiunti i collegamenti ai webcast dei bollettini relativi al presente bollettino straordinario sulla sicurezza.
-   V3.1 (18 dicembre 2008): Per MS08-078, aggiunta notazione sui Server Core non interessati di Windows Internet Explorer 7 in Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a x64.
-   V3.2 (07 gennaio 2009): Microsoft Office Word Viewer 2003 è stato rimosso dalla tabella Software interessato per MS08-072.
-   V4.0 (13 gennaio 2009): Microsoft ha rilasciato un nuovo bollettino MS08-076 allo scopo di offrire nuovi pacchetti di aggiornamento per Runtime formato Windows Media 9.5 in Windows XP Service Pack 2 (KB952069) e in Windows XP Service Pack 3 (KB952069). I clienti che utilizzano tutte le altre versioni supportate e interessate di componenti Windows Media e hanno già applicato i pacchetti di aggiornamento per la protezione originali MS08-076 non devono eseguire alcuna operazione. Anche Windows Media Player 6.4 e Servizi Windows Media 4.1 sono stati inclusi nell'elenco Software interessato in tutte le edizioni di Microsoft Windows 2000 Service Pack 4 per MS08-076; agli utenti ai quali è stato offerto questo aggiornamento, KB954600 per Windows Media Player 6.4 o KB952068 per Servizi Windows Media 4.1, ma che non lo hanno ancora installato, si consiglia di eseguirne l'installazione. Infine, Microsoft Office Word Viewer è stato inserito nell'elenco di software interessato per MS08-072; i clienti che hanno installato l'aggiornamento per la protezione KB956366 non devono eseguire una nuova installazione.
-   V5.0 (28 gennaio 2009): È stata aggiunta una nota a piè di pagina per il bollettino MS08-074 nella tabella **Software interessato**, riguardante i pacchetti di aggiornamento per la protezione KB958437 e KB958439 per le versioni supportate di Microsoft Office Excel 2007. Non sono previsti aggiornamenti per la protezione di file binari o per il rilevamento. Per gli utenti che utilizzano Microsoft Office Excel 2007 o Microsoft Office Excel 2007 Service Pack 1 e hanno già installato gli aggiornamenti KB958437 e KB958439, non è necessario eseguire una nuova installazione.
-   V6.0 (29 aprile 2009): Servizi Windows Media 2008 (KB952068) nelle edizioni a 32 bit e nelle edizioni x64 di Windows Server 2008 Service Pack 2 è stato aggiunto come software interessato per MS08-076. Si tratta di una modifica che riguarda esclusivamente il rilevamento; non sono state effettuate modifiche ai file binari. Per i clienti che hanno già installato l'aggiornamento KB952068 non è necessario eseguire una nuova installazione.

*Built at 2014-04-18T01:50:00Z-07:00*
