---
TOCTitle: 'MS13-OCT'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Ottobre 2013'
ms:assetid: 'ms13-oct'
ms:contentKeyID: 61240088
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms13-oct(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Ottobre 2013
=================================================================

Data di pubblicazione: martedì 8 ottobre 2013 | Aggiornamento: mercoledì 6 novembre 2013

**Versione:** 1.2

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a ottobre 2013.

Con il rilascio dei bollettini sulla sicurezza di ottobre 2013, questo riepilogo sostituisce la notifica anticipata sul rilascio pubblicata originariamente in data 3 ottobre 2013. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 9 ottobre 2013 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di ottobre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032557381&culture=en-us).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

La seguente tabella riassume i bollettini sulla sicurezza di questo mese in ordine di gravità.

Per ulteriori informazioni sul software interessato, vedere la sezione successiva, **Software interessato**.

 
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324021">MS13-080</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2879017)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e otto vulnerabilità segnalate privatamente in Internet Explorer. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando la più grave di tali vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314048">MS13-081</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel di Windows possono consentire l'esecuzione di codice in modalità remota (2870008)</strong><br />
<br />
Questo aggiornamento per la protezione risolve sette vulnerabilità segnalate privatamente in Microsoft Windows. La più grave di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza contenuto condiviso che incorpora file di caratteri OpenType o TrueType. Sfruttando queste vulnerabilità, un utente malintenzionato può assumere il pieno controllo di un sistema interessato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=318048">MS13-082</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in .NET Framework possono consentire l'esecuzione di codice in modalità remota (2878890)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente e una vulnerabilità divulgata pubblicamente relative Microsoft .NET Framework. La più grave delle vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visita un sito Web che contiene un file di caratteri OpenType (OTF) appositamente predisposto utilizzando un browser capace di creare istanze di applicazioni XBAP.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314045">MS13-083</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nella libreria dei controlli comuni di Windows può consentire l'esecuzione di codice in modalità remota (2864058)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato invia una richiesta Web appositamente predisposta a un'applicazione Web di ASP.NET in esecuzione in un sistema interessato. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe eseguire codice non autorizzato senza autenticazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324028">MS13-084</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft SharePoint Server possono consentire l'esecuzione di codice in modalità remota (2885089)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente nel software Microsoft Office Server. La vulnerabilità più grave potrebbe consentire l'esecuzione di codice in modalità remota se un utente apre un file di Office appositamente predisposto in una versione interessata di Microsoft SharePoint Server, Microsoft Office Services o Web Apps.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Software dei server Microsoft</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324026">MS13-085</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (2885080)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Office. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file di Office appositamente predisposto con una versione interessata di Microsoft Excel o con altro software di Microsoft Office interessato. Sfruttando tale vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324027">MS13-086</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Word possono consentire l'esecuzione di codice in modalità remota (2885084)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Office. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un file appositamente predisposto è aperto in una versione interessata di Microsoft Word o di altro software Microsoft Office interessato. Sfruttando tale vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324590">MS13-087</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Silverlight può consentire l'intercettazione di informazioni personali (2890788)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Silverlight che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato ospita un sito Web che contiene un'applicazione Silverlight appositamente predisposta, in grado di sfruttare questa vulnerabilità, e convince un utente a visualizzare il sito Web. L'utente malintenzionato può inoltre servirsi di siti Web manomessi e di siti Web che accettano o pubblicano contenuti o annunci pubblicitari inviati da altri utenti. Tali siti Web possono includere contenuti appositamente predisposti in grado di sfruttare questa vulnerabilità. Tuttavia, non è in alcun modo possibile per un utente malintenzionato obbligare gli utenti a visitare tale sito Web. L'utente malintenzionato deve convincere le vittime a visitare un sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che le indirizzi al sito. Può inoltre far visualizzare contenuti Web appositamente predisposti utilizzando banner pubblicitari o altre modalità di invio di contenuti Web ai sistemi interessati.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Microsoft Silverlight</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259).
  
Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.

 
<table style="border:1px solid black;">
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID bollettino</th>
<th style="border:1px solid black;" >Titolo della vulnerabilità</th>
<th style="border:1px solid black;" >ID CVE</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability per la versione più recente del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability per la versione meno recente del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service</th>
<th style="border:1px solid black;" >Note fondamentali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324021">MS13-080</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3872">CVE-2013-3872</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324021">MS13-080</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3873">CVE-2013-3873</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324021">MS13-080</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3874">CVE-2013-3874</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324021">MS13-080</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3875">CVE-2013-3875</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324021">MS13-080</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3882">CVE-2013-3882</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324021">MS13-080</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3885">CVE-2013-3885</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324021">MS13-080</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3886">CVE-2013-3886</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324021">MS13-080</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3893">CVE-2013-3893</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Microsoft è a conoscenza di attacchi mirati che tentano sfruttare questa vulnerabilità in Internet Explorer 8 e Internet Explorer 9.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324021">MS13-080</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3897">CVE-2013-3897</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Microsoft è a conoscenza di attacchi mirati che tentano di sfruttare questa vulnerabilità in Internet Explorer 8.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314048">MS13-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi dei caratteri OpenType</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3128">CVE-2013-3128</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=318048">MS13-082</a><a href="http://go.microsoft.com/fwlink/?linkid=293350"></a>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314048">MS13-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al descrittore USB di Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3200">CVE-2013-3200</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314048">MS13-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free di Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3879">CVE-2013-3879</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314048">MS13-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi più elevati nel contenitore di app</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3880">CVE-2013-3880</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'intercettazione di informazioni personali che può consentire un'acquisizione di privilegi più elevati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314048">MS13-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla pagina NULL in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3881">CVE-2013-3881</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314048">MS13-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al doppio recupero del sottosistema del kernel grafico DirectX</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3888">CVE-2013-3888</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314048">MS13-081</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla tabella CMAP dei caratteri TrueType</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3894">CVE-2013-3894</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=318048">MS13-082</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi dei caratteri OpenType</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3128">CVE-2013-3128</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=314048">MS13-081</a><a href="http://go.microsoft.com/fwlink/?linkid=293350"></a>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=318048">MS13-082</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'espansione delle entità</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3860">CVE-2013-3860</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=318048">MS13-082</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi JSON</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3861">CVE-2013-3861</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.<br />
<br />
Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314045">MS13-083</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow di valori integer Comctl32</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3195">CVE-2013-3195</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324028">MS13-084</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Microsoft Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3889">CVE-2013-3889</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=324026">MS13-085</a><a href="http://go.microsoft.com/fwlink/?linkid=293350"></a>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324028">MS13-084</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'immissione di parametri</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3895">CVE-2013-3895</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324026">MS13-085</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Microsoft Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3889">CVE-2013-3889</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=324028">MS13-084</a><a href="http://go.microsoft.com/fwlink/?linkid=293350"></a>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324026">MS13-085</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Microsoft Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3890">CVE-2013-3890</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324027">MS13-086</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3891">CVE-2013-3891</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324027">MS13-086</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3892">CVE-2013-3892</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324590">MS13-087</a></td>
<td style="border:1px solid black;">Vulnerabilità in Silverlight</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3896">CVE-2013-3896</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'intercettazione di informazioni personali che può consentire l'elusione della funzione di protezione.</td>
</tr>
</tbody>
</table>
  
Software interessato  
--------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma o componente elencato è riportato anche il livello di gravità dell'aggiornamento software.
  
**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.
  
#### Sistema operativo Windows e suoi componenti

 
<table style="border:1px solid black;">
<tr>
<th colspan="5">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2879017)  
(Critico)  
Internet Explorer 7  
(2879017)  
(Critico)  
Internet Explorer 8  
(2879017)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2847311)  
(Critico)  
Windows XP Service Pack 3  
(2862330)  
(Importante)  
Windows XP Service Pack 3  
(2862335)  
(Importante)  
Windows XP Service Pack 3  
(2868038)  
(Importante)  
Windows XP Service Pack 3  
(2883150)  
(Critico)  
Windows XP Service Pack 3  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2863239)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2861189)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2861697)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4  
(2861188)  
(Critico)
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
Internet Explorer 6  
(2879017)  
(Critico)  
Internet Explorer 7  
(2879017)  
(Critico)  
Internet Explorer 8  
(2879017)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2847311)  
(Critico)  
Windows XP Professional x64 Edition Service Pack 2  
(2862330)  
(Importante)  
Windows XP Professional x64 Edition Service Pack 2  
(2862335)  
(Importante)  
Windows XP Professional x64 Edition Service Pack 2  
(2868038)  
(Importante)  
Windows XP Professional x64 Edition Service Pack 2  
(2883150)  
(Critico)  
Windows XP Professional x64 Edition Service Pack 2  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2863239)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2861189)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2861697)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4  
(2861188)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2879017)  
(Moderato)  
Internet Explorer 7  
(2879017)  
(Moderato)  
Internet Explorer 8  
(2879017)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2847311)  
(Critico)  
Windows Server 2003 Service Pack 2  
(2862330)  
(Importante)  
Windows Server 2003 Service Pack 2  
(2862335)  
(Importante)  
Windows Server 2003 Service Pack 2  
(2868038)  
(Importante)  
Windows Server 2003 Service Pack 2  
(2883150)  
(Critico)  
Windows Server 2003 Service Pack 2  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2863239)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2861189)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2861697)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4  
(2861188)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2864058)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2879017)  
(Moderato)  
Internet Explorer 7  
(2879017)  
(Moderato)  
Internet Explorer 8  
(2879017)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2847311)  
(Critico)  
Windows Server 2003 x64 Edition Service Pack 2  
(2862330)  
(Importante)  
Windows Server 2003 x64 Edition Service Pack 2  
(2862335)  
(Importante)  
Windows Server 2003 x64 Edition Service Pack 2  
(2868038)  
(Importante)  
Windows Server 2003 x64 Edition Service Pack 2  
(2883150)  
(Critico)  
Windows Server 2003 x64 Edition Service Pack 2  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2863239)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2861189)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2861697)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4  
(2861188)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2879017)  
(Moderato)  
Internet Explorer 7  
(2879017)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2847311)  
(Critico)  
Windows Server 2003 con SP2 per sistemi Itanium  
(2862330)  
(Importante)  
Windows Server 2003 con SP2 per sistemi Itanium  
(2862335)  
(Importante)  
Windows Server 2003 con SP2 per sistemi Itanium  
(2868038)  
(Importante)  
Windows Server 2003 con SP2 per sistemi Itanium  
(2883150)  
(Critico)  
Windows Server 2003 con SP2 per sistemi Itanium  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2863239)  
(Importante)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2861697)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2879017)  
(Critico)  
Internet Explorer 8  
(2879017)  
(Critico)  
Internet Explorer 9  
(2879017)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2847311)  
(Critico)  
Windows Vista Service Pack 2  
(2855844)  
(Critico)  
Windows Vista Service Pack 2  
(2862330)  
(Importante)  
Windows Vista Service Pack 2  
(2862335)  
(Importante)  
Windows Vista Service Pack 2  
(2864202)  
(Importante)  
Windows Vista Service Pack 2  
(2868038)  
(Importante)  
Windows Vista Service Pack 2  
(2876284)  
(Importante)  
Windows Vista Service Pack 2  
(2883150)  
(Critico)  
Windows Vista Service Pack 2  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2863253)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2861190)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2861697)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4  
(2861188)  
(Critico)  
Microsoft .NET Framework 4.5  
(2861193)  
(Critico)  
Microsoft .NET Framework 4.5  
(2861208)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2864058)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2879017)  
(Critico)  
Internet Explorer 8  
(2879017)  
(Critico)  
Internet Explorer 9  
(2879017)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2847311)  
(Critico)  
Windows Vista x64 Edition Service Pack 2  
(2855844)  
(Critico)  
Windows Vista x64 Edition Service Pack 2  
(2862330)  
(Importante)  
Windows Vista x64 Edition Service Pack 2  
(2862335)  
(Importante)  
Windows Vista x64 Edition Service Pack 2  
(2864202)  
(Importante)  
Windows Vista x64 Edition Service Pack 2  
(2868038)  
(Importante)  
Windows Vista x64 Edition Service Pack 2  
(2876284)  
(Importante)  
Windows Vista x64 Edition Service Pack 2  
(2883150)  
(Critico)  
Windows Vista x64 Edition Service Pack 2  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2863253)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2861190)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2861697)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4  
(2861188)  
(Critico)  
Microsoft .NET Framework 4.5  
(2861193)  
(Critico)  
Microsoft .NET Framework 4.5  
(2861208)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2879017)  
(Moderato)  
Internet Explorer 8  
(2879017)  
(Moderato)  
Internet Explorer 9  
(2879017)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2847311)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2855844)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2862330)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2862335)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2864202)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2868038)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2876284)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2883150)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2863253)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2861190)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2861697)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4  
(2861188)  
(Critico)  
Microsoft .NET Framework 4.5  
(2861193)  
(Critico)  
Microsoft .NET Framework 4.5  
(2861208)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2864058)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2879017)  
(Moderato)  
Internet Explorer 8  
(2879017)  
(Moderato)  
Internet Explorer 9  
(2879017)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2847311)  
(Critico)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(2855844)  
(Critico)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(2862330)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(2862335)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(2864202)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(2868038)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(2876284)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(2883150)  
(Critico)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2863253)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2861190)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2861697)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4  
(2861188)  
(Critico)  
Microsoft .NET Framework 4.5  
(2861193)  
(Critico)  
Microsoft .NET Framework 4.5  
(2861208)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2864058)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2879017)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2847311)  
(Critico)  
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2862330)  
(Importante)  
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2862335)  
(Importante)  
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2864202)  
(Importante)  
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2868038)  
(Importante)  
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2876284)  
(Importante)  
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2883150)  
(Critico)  
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2863253)  
(Importante)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2861697)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2879017)  
(Critico)  
Internet Explorer 9  
(2879017)  
(Critico)  
Internet Explorer 10  
(2879017)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2847311)  
(Critico)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(2855844)  
(Critico)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(2862330)  
(Importante)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(2862335)  
(Importante)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(2864202)  
(Importante)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(2868038)  
(Importante)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(2876284)  
(Importante)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(2883150)  
(Critico)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2861191)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2861698)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2863240)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4.5  
(2861208)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2864058)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2879017)  
(Critico)  
Internet Explorer 9  
(2879017)  
(Critico)  
Internet Explorer 10  
(2879017)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2847311)  
(Critico)  
Windows 7 per sistemi x64 Service Pack 1  
(2855844)  
(Critico)  
Windows 7 per sistemi x64 Service Pack 1  
(2862330)  
(Importante)  
Windows 7 per sistemi x64 Service Pack 1  
(2862335)  
(Importante)  
Windows 7 per sistemi x64 Service Pack 1  
(2864202)  
(Importante)  
Windows 7 per sistemi x64 Service Pack 1  
(2868038)  
(Importante)  
Windows 7 per sistemi x64 Service Pack 1  
(2876284)  
(Importante)  
Windows 7 per sistemi x64 Service Pack 1  
(2883150)  
(Critico)  
Windows 7 per sistemi x64 Service Pack 1  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2861191)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2861698)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2863240)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4.5  
(2861208)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2879017)  
(Moderato)  
Internet Explorer 9  
(2879017)  
(Moderato)  
Internet Explorer 10  
(2879017)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2847311)  
(Critico)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2855844)  
(Critico)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2862330)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2862335)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2864202)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2868038)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2876284)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2883150)  
(Critico)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2861191)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2861698)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2863240)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4.5  
(2861208)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2864058)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2879017)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2847311)  
(Critico)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2855844)  
(Critico)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2862330)  
(Importante)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2862335)  
(Importante)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2864202)  
(Importante)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2868038)  
(Importante)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2876284)  
(Importante)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2883150)  
(Critico)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2861698)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2863240)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows 8
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2879017)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2847311)  
(Critico)  
Windows 8 per sistemi a 32 bit  
(2862330)  
(Importante)  
Windows 8 per sistemi a 32 bit  
(2862335)  
(Importante)  
Windows 8 per sistemi a 32 bit  
(2863725)  
(Importante)  
Windows 8 per sistemi a 32 bit  
(2864202)  
(Importante)  
Windows 8 per sistemi a 32 bit  
(2868038)  
(Importante)  
Windows 8 per sistemi a 32 bit  
(2883150)  
(Critico)  
Windows 8 per sistemi a 32 bit  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2861194)  
(Critico)  
Microsoft .NET Framework 3.5  
(2861704)  
(Importante)  
Microsoft .NET Framework 3.5  
(2863243)  
(Importante)  
Microsoft .NET Framework 4.5  
(2861702)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2864058)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2879017)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit  
(2847311)  
(Critico)  
Windows 8 per sistemi a 64 bit  
(2862330)  
(Importante)  
Windows 8 per sistemi a 64 bit  
(2862335)  
(Importante)  
Windows 8 per sistemi a 64 bit  
(2863725)  
(Importante)  
Windows 8 per sistemi a 64 bit  
(2864202)  
(Importante)  
Windows 8 per sistemi a 64 bit  
(2868038)  
(Importante)  
Windows 8 per sistemi a 64 bit  
(2883150)  
(Critico)  
Windows 8 per sistemi a 64 bit  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2861194)  
(Critico)  
Microsoft .NET Framework 3.5  
(2861704)  
(Importante)  
Microsoft .NET Framework 3.5  
(2863243)  
(Importante)  
Microsoft .NET Framework 4.5  
(2861702)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows Server 2012
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2879017)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2847311)  
(Critico)  
Windows Server 2012  
(2862330)  
(Importante)  
Windows Server 2012  
(2862335)  
(Importante)  
Windows Server 2012  
(2863725)  
(Importante)  
Windows Server 2012  
(2864202)  
(Importante)  
Windows Server 2012  
(2868038)  
(Importante)  
Windows Server 2012  
(2883150)  
(Critico)  
Windows Server 2012  
(2884256)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2861194)  
(Critico)  
Microsoft .NET Framework 3.5  
(2861704)  
(Importante)  
Microsoft .NET Framework 3.5  
(2863243)  
(Importante)  
Microsoft .NET Framework 4.5  
(2861702)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<th colspan="5">
Windows RT
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows RT
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2879017)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows RT  
(2847311)  
(Critico)  
Windows RT  
(2862330)  
(Importante)  
Windows RT  
(2862335)  
(Importante)  
Windows RT  
(2863725)  
(Importante)  
Windows RT  
(2864202)  
(Importante)  
Windows RT  
(2868038)  
(Importante)  
Windows RT  
(2883150)  
(Critico)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 4.5  
(2861702)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows RT  
(2864058)  
(Nessuno livello di gravità)
</td>
</tr>
<tr>
<th colspan="5">
Windows 8.1
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
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
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 11<sup>[1]</sup>
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
Windows 8.1 per sistemi a 64 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 11<sup>[1]</sup>
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
Windows Server 2012 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 R2
</td>
<td style="border:1px solid black;">
Internet Explorer 11<sup>[1]</sup>
(Moderato)
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
Windows RT 8.1
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
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
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows RT 8.1
</td>
<td style="border:1px solid black;">
Internet Explorer 11<sup>[1]</sup>
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
Opzione di installazione Server Core
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-080**](http://go.microsoft.com/fwlink/?linkid=324021)
</td>
<td style="border:1px solid black;">
[**MS13-081**](http://go.microsoft.com/fwlink/?linkid=314048)
</td>
<td style="border:1px solid black;">
[**MS13-082**](http://go.microsoft.com/fwlink/?linkid=318048)
</td>
<td style="border:1px solid black;">
[**MS13-083**](http://go.microsoft.com/fwlink/?linkid=314045)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2847311)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2862330)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2862335)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2864202)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2876284)  
(Importante)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2883150)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2864058)  
(Nessuno livello di gravità)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2847311)  
(Critico)  
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2862330)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2862335)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2864202)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2876284)  
(Importante)  
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2883150)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2847311)  
(Critico)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2862330)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2862335)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2864202)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2876284)  
(Importante)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2883150)  
(Critico)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2861698)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2863240)  
(Importante)  
Microsoft .NET Framework 4  
(2858302)  
(Importante)  
Microsoft .NET Framework 4.5  
(2861208)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2864058)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2847311)  
(Critico)  
Windows Server 2012 (installazione Server Core)  
(2862330)  
(Importante)  
Windows Server 2012 (installazione Server Core)  
(2862335)  
(Importante)  
Windows Server 2012 (installazione Server Core)  
(2863725)  
(Importante)  
Windows Server 2012 (installazione Server Core)  
(2864202)  
(Importante)  
Windows Server 2012 (installazione Server Core)  
(2883150)  
(Critico)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2861194)  
(Critico)  
Microsoft .NET Framework 3.5  
(2861704)  
(Importante)  
Microsoft .NET Framework 3.5  
(2863243)  
(Importante)  
Microsoft .NET Framework 4.5  
(2861702)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2864058)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 R2 (installazione Server Core)
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
 
**Nota per MS13-080**

<sup>[1]</sup>Per Internet Explorer 11, i clienti devono applicare l'aggiornamento cumulativo di Windows RT 8.1, Windows 8.1 e Windows Server 2012 R2: Ottobre 2013 (2883200). Notare che l'aggiornamento cumulativo 2883200 contiene le modifiche sia relative sia non relative alla protezione. Per ulteriori informazioni e i collegamenti di download disponibili, vedere [l'articolo della Microsoft Knowledge Base 2883200](http://support.microsoft.com/kb/2883200).

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="3">
Microsoft Office 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-085**](http://go.microsoft.com/fwlink/?linkid=324026)
</td>
<td style="border:1px solid black;">
[**MS13-086**](http://go.microsoft.com/fwlink/?linkid=324027)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Microsoft Word 2003 Service Pack 3  
(2826020)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Office 2007
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-085**](http://go.microsoft.com/fwlink/?linkid=324026)
</td>
<td style="border:1px solid black;">
[**MS13-086**](http://go.microsoft.com/fwlink/?linkid=324027)
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
Microsoft Office 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft Excel 2007 Service Pack 3  
(2827324)  
(Importante)  
Microsoft Office 2007 Service Pack 3  
(2760585)  
(Importante)  
Microsoft Office 2007 Service Pack 3  
(2760591)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Word 2007 Service Pack 3  
(2827330)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Office 2010
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-085**](http://go.microsoft.com/fwlink/?linkid=324026)
</td>
<td style="border:1px solid black;">
[**MS13-086**](http://go.microsoft.com/fwlink/?linkid=324027)
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
**Nessuno**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2010 Service Pack 1 (edizioni a 32 bit)  
(2826033)  
(Importante)  
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)  
(2826023)  
(Importante)  
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)  
(2826035)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2010 Service Pack 1 (edizioni a 64 bit)  
(2826033)  
(Importante)  
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)  
(2826023)  
(Importante)  
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)  
(2826035)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2010 Service Pack 2 (edizioni a 32 bit)  
(2826033)  
(Importante)  
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)  
(2826023)  
(Importante)  
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)  
(2826035)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2010 Service Pack 2 (edizioni a 64 bit)  
(2826033)  
(Importante)  
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)  
(2826023)  
(Importante)  
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)  
(2826035)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Office 2013
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-085**](http://go.microsoft.com/fwlink/?linkid=324026)
</td>
<td style="border:1px solid black;">
[**MS13-086**](http://go.microsoft.com/fwlink/?linkid=324027)
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
**Nessuno**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2013 (edizioni a 32 bit)  
(2827238)  
(Importante)  
Microsoft Office 2013 (edizioni a 32 bit)  
(2817623)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2013 (edizioni a 64 bit)  
(2827238)  
(Importante)  
Microsoft Office 2013 (edizioni a 64 bit)  
(2817623)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 RT
</td>
<td style="border:1px solid black;">
Microsoft Excel 2013 RT  
(2827238)  
(Importante)  
Microsoft Office 2013 RT  
(2817623)  
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
[**MS13-085**](http://go.microsoft.com/fwlink/?linkid=324026)
</td>
<td style="border:1px solid black;">
[**MS13-086**](http://go.microsoft.com/fwlink/?linkid=324027)
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
**Nessuno**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office per Mac 2011
</td>
<td style="border:1px solid black;">
Microsoft Office per Mac 2011  
(2889496)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Altro software Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-085**](http://go.microsoft.com/fwlink/?linkid=324026)
</td>
<td style="border:1px solid black;">
[**MS13-086**](http://go.microsoft.com/fwlink/?linkid=324027)
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
Pacchetto di compatibilità Microsoft Office Service Pack 3
</td>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3  
(2827326)  
(Importante)
</td>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3  
(2827329)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Excel Viewer
</td>
<td style="border:1px solid black;">
Microsoft Excel Viewer  
(2827328)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft SharePoint Server 2007
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-084**](http://go.microsoft.com/fwlink/?linkid=324028)
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
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 3 (wssloc) (versioni a 32 bit)  
(2596741)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 3 (wssloc) (versioni a 64 bit)  
(2596741)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft SharePoint Server 2010
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-084**](http://go.microsoft.com/fwlink/?linkid=324028)
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
Microsoft SharePoint Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Microsoft SharePoint Foundation 2010 Service Pack 1 (wssloc)  
(2589365)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft SharePoint Foundation 2010 Service Pack 2 (wssloc)  
(2589365)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft SharePoint Server 2013
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-084**](http://go.microsoft.com/fwlink/?linkid=324028)
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
Microsoft SharePoint Server 2013
</td>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2013 (pptserver)  
(2760561)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS13-084**

Vedere ulteriori categorie software nella sezione **Software interessato**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Microsoft Office Services e Web Apps

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft SharePoint Server 2007
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-084**](http://go.microsoft.com/fwlink/?linkid=324028)
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
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Excel Services  
(2827327)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Excel Services  
(2827327)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft SharePoint Server 2010
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-084**](http://go.microsoft.com/fwlink/?linkid=324028)
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
Microsoft SharePoint Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Excel Services  
(2826029)  
(Importante)  
Word Automation Services  
(2826022)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 2
</td>
<td style="border:1px solid black;">
Excel Services  
(2826029)  
(Importante)  
Word Automation Services  
(2826022)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft SharePoint Server 2013
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-084**](http://go.microsoft.com/fwlink/?linkid=324028)
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
Microsoft SharePoint Server 2013
</td>
<td style="border:1px solid black;">
Excel Services  
(2752002)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2013
</td>
<td style="border:1px solid black;">
Word Automation Services  
(2826036)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Office Web Apps 2010
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-084**](http://go.microsoft.com/fwlink/?linkid=324028)
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
Microsoft Office Web Apps 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Microsoft Web Applications 2010 Service Pack 1  
(2826030)  
(Importante)  
Microsoft Excel Web App 2010 Service Pack 1  
(2826028)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Web Apps 2010 Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft Web Applications 2010 Service Pack 2  
(2826030)  
(Importante)  
Microsoft Excel Web App 2010 Service Pack 2  
(2826028)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Office Web Apps 2013
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-084**](http://go.microsoft.com/fwlink/?linkid=324028)
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
Microsoft Office Web Apps 2013
</td>
<td style="border:1px solid black;">
Microsoft Office Web Apps Server 2013  
(2827222)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS13-084**

Vedere ulteriori categorie software nella sezione **Software interessato**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

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
[**MS13-087**](http://go.microsoft.com/fwlink/?linkid=324590)
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
Microsoft Silverlight 5
</td>
<td style="border:1px solid black;">
Microsoft Silverlight 5 installato in Mac  
(2890788)  
(Importante)  
Microsoft Silverlight 5 Developer Runtime installato in Mac  
(2890788)  
(Importante)  
Microsoft Silverlight 5 installato in tutte le versioni supportate dei client Microsoft Windows  
(2890788)  
(Importante)  
Microsoft Silverlight 5 Developer Runtime installato in tutte le versioni supportate dei client Microsoft Windows  
(2890788)  
(Importante)  
Microsoft Silverlight 5 installato in tutte le versioni supportate dei server Microsoft Windows  
(2890788)  
(Importante)  
Microsoft Silverlight 5 Developer Runtime installato in tutte le versioni supportate dei server Microsoft Windows  
(2890788)  
(Importante)
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
Sono disponibili diverse risorse per aiutare gli amministratori a distribuire gli aggiornamenti per la protezione.

-   Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione.
-   Windows Server Update Services (WSUS), Systems Management Server (SMS) e System Center Configuration Manager (SCCM) aiutano gli amministratori a distribuire gli aggiornamenti per la protezione.
-   I componenti del programma Update Compatibility Evaluator compresi nell'Application Compatibility Toolkit sono utili per semplificare la verifica e la convalida degli aggiornamenti di Windows per le applicazioni installate.

Per informazioni su questi e altri strumenti disponibili, vedere [Strumenti per la sicurezza](http://technet.microsoft.com/security/cc297183).

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Per il rilascio dei bollettini che avviene il secondo martedì di ogni mese, Microsoft ha rilasciato una versione aggiornata dello Strumento di rimozione software dannoso di Microsoft Windows in Windows Update, Microsoft Update, Windows Server Update Services e nell'Area download. Non è disponibile alcuna versione dello Strumento di rimozione software dannoso di Microsoft Windows per i rilasci di bollettini sulla sicurezza straordinari.

#### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/wsus/bb456965). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://go.microsoft.com/fwlink/?linkid=215201).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

**MS13-080**

-   [Aniway.Anyway@gmail.com](mailto:aniway.anyway@gmail.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3872)
-   Jose A. Vazquez di Yenteasy - Security Research, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3873)
-   Amol Naik, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3874)
-   Un ricercatore anonimo, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3874)
-   Jose A. Vazquez di Yenteasy - Security Research, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3875)
-   Ivan Fratric di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3882)
-   Jose A. Vazquez di Yenteasy - Security Research per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3882)
-   Jose A. Vazquez di Yenteasy - Security Research per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3885)
-   Jose A. Vazquez di Yenteasy - Security Research, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3886)
-   Yoshihiro Ishikawa di [LAC Co.](http://www.lac.co.jp/) per aver collaborato con Microsoft sulla vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3893)
-   Hoodie22, che collabora con il National Cyber Security Centre of the Netherlands, per aver collaborato con noi alla vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3897)
-   Daniel Chechik di Trustwave SpiderLabs Team per aver collaborato con noi alla vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3897)
-   Renato Ettisberger di [IOprotect GmbH](http://ioprotect.ch/) per aver collaborato con noi alla vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3897)

**MS13-081**

-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata all'analisi dei caratteri OpenType (CVE-2013-3128)
-   Andy Davis di [NCC Group](http://www.nccgroup.com/) per aver segnalato la vulnerabilità legata al descrittore USB di Windows (CVE-2013-3200)
-   Lucas Bouillot di ANSSI per aver segnalato la vulnerabilità legata al descrittore USB di Windows (CVE-2013-3200)
-   Seth Gibson e Dan Zentner di [Endgame](http://www.endgame.com/) per aver segnalato la vulnerabilità legata alla pagina NULL in Win32k (CVE-2013-3881)
-   ZombiE, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata alla tabella CMAP dei caratteri TrueType (CVE-2013-3895)

**MS13-082**

-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata all'analisi dei caratteri OpenType (CVE-2013-3128)
-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata all'espansione di entità (CVE-2013-3860)

**MS13-083**

-   孙晓山 per aver segnalato la vulnerabilità legata all'overflow di valori integer Comctl32 (CVE-2013-3195)

**MS13-084**

-   Mateusz Jurczyk, Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Microsoft Excel (CVE-2013-3889)
-   Nutan kumar panda per aver segnalato la vulnerabilità legata all'immissione di parametri (CVE-2013-3895)
-   Ari Elias-Bachrach e Angela Kelso dei [National Institutes of Health](http://nih.gov/) per aver collaborato con noi alle modifiche al sistema di difesa contenute in questo bollettino

**MS13-085**

-   Mateusz Jurczyk, Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Microsoft Excel (CVE-2013-3889)
-   Mateusz Jurczyk, Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Microsoft Excel (CVE-2013-3890)

**MS13-086**

-   Yuhong Bao per aver segnalato la vulnerabilità legata al danneggiamento della memoria (CVE-2013-3891)
-   Mateusz Jurczyk, Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria (CVE-2013-3892)

**MS13-087**

-   Vitaliy Toropov per aver segnalato la vulnerabilità in Silverlight (CVE-2013-3896)

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (8 ottobre 2013): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (10 ottobre 2013): Per MS13-080, è stata rimossa una valutazione dell'Exploitability nell'Exploitability Index per CVE-2013-3871. L'inclusione di questo CVE nel testo originale del bollettino sulla sicurezza era un errore di documentazione. La risoluzione di CVE-2013-3871 verrà illustrata in un futuro aggiornamento per la protezione. La modifica è esclusivamente informativa. Per MS13-082, è stato rivisto il bollettino per indicare che le installazioni Server Core di Windows Server 2012 sono interessate dalla vulnerabilità risolta nell'aggiornamento 2861194. Non sono previste modifiche alla logica di rilevamento o ai pacchetti di aggiornamento per la protezione. I clienti che hanno già aggiornato i propri sistemi non devono eseguire ulteriori operazioni.
-   V1.2 (6 novembre 2013): Per MS13-084, è stato corretto il nome del prodotto per l'aggiornamento Microsoft Office Web Apps Server 2013 (2827222).

*Built at 2014-04-18T01:50:00Z-07:00*
