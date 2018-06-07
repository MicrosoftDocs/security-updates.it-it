---
TOCTitle: 'MS14-MAR'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Marzo 2014'
ms:assetid: 'ms14-mar'
ms:contentKeyID: 61597942
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms14-mar(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Riepilogo dei bollettini Microsoft sulla sicurezza - Marzo 2014
===============================================================

Data di pubblicazione: 11 marzo 2014 | Ultimo aggiornamento: 18 settembre 2014

**Versione:** 1.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a marzo 2014.

Con il rilascio dei bollettini sulla sicurezza di marzo 2014, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 6 marzo 2014. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 12 marzo 2014 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di marzo](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032572977&culture=en-us).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

Riepiloghi
----------

<span id="sectionToggle0"></span>
La seguente tabella riassume i bollettini sulla sicurezza di questo mese in ordine di gravità.

Per ulteriori informazioni sul software interessato, vedere la sezione successiva, **Software interessato**.

 
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2925418)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e diciassette vulnerabilità segnalate privatamente in Internet Explorer. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392071">MS14-013</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft DirectShow può consentire l'esecuzione di codice in modalità remota (2929961)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota se un utente apre un file di immagine appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392067">MS14-015</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel driver in modalità kernel di Windows possono consentire l'acquisizione di privilegi più elevati (2930275)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e una vulnerabilità segnalata privatamente in Microsoft Windows. La più grave di queste vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede al sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare tali vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392066">MS14-016</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel protocollo SAMR (Security Account Manager Remote) può consentire l'elusione della funzione di protezione (2934418)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'elusione della funzione di protezione se un utente malintenzionato prova ripetutamente ad associare password a un nome utente.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Elusione della funzione di protezione</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392070">MS14-014</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Silverlight può consentire l'elusione della funzione di protezione (2932677)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Silverlight che è stata segnalata privatamente. La vulnerabilità può consentire l'elusione della funzione di protezione se un utente malintenzionato ospita un sito Web che contiene un'applicazione Silverlight appositamente predisposta, progettata per sfruttare questa vulnerabilità, e convince un utente a visualizzare il sito Web. Tuttavia, non è in alcun modo possibile per un utente malintenzionato obbligare gli utenti a visitare tale sito Web. L'utente malintenzionato deve convincere le vittime a visitare un sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che le indirizzi al sito. Può inoltre far visualizzare contenuti Web appositamente predisposti utilizzando banner pubblicitari o altre modalità di invio di contenuti Web ai sistemi interessati.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Elusione della funzione di protezione</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Microsoft Silverlight</td>
</tr>
</tbody>
</table>
  
 
  
Exploitability Index  
--------------------
  
<span id="sectionToggle1"></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
Come utilizzare questa tabella
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259).
  
Nelle colonne seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.
  
<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0297">CVE-2014-0297</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0298">CVE-2014-0298</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0299">CVE-2014-0299</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0302">CVE-2014-0302</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0303">CVE-2014-0303</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0304">CVE-2014-0304</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0305">CVE-2014-0305</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0306">CVE-2014-0306</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0307">CVE-2014-0307</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0308">CVE-2014-0308</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0309">CVE-2014-0309</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0311">CVE-2014-0311</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0312">CVE-2014-0312</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0313">CVE-2014-0313</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0314">CVE-2014-0314</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0321">CVE-2014-0321</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0322">CVE-2014-0322</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Microsoft è a conoscenza di attacchi mirati che tentano di sfruttare questa vulnerabilità in Internet Explorer 10.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0324">CVE-2014-0324</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Microsoft è a conoscenza di attacchi mirati che tentano di sfruttare questa vulnerabilità in Internet Explorer 8.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392064">MS14-012</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4112">CVE-2014-4112</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392071">MS14-013</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in DirectShow</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0301">CVE-2014-0301</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392070">MS14-014</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'elusione di Silverlight DEP/ASLR</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0319">CVE-2014-0319</a></td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'elusione della funzione di protezione.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392067">MS14-015</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi più elevati in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0300">CVE-2014-0300</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392067">MS14-015</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni personali in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0323">CVE-2014-0323</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Si tratta di una vulnerabilità legata all'intercettazione di informazioni personali su versioni meno recenti del software.<br />
<br />
Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service sulla versione più recente del software.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392066">MS14-016</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'elusione della funzione di protezione SAMR</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0317">CVE-2014-0317</a></td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'elusione della funzione di protezione.</td>
</tr>
</tbody>
</table>
  
Software interessato  
--------------------
  
<span id="sectionToggle2"></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma o componente elencato è riportato anche il livello di gravità dell'aggiornamento software.
  
**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.
  
**Sistema operativo Windows e suoi componenti**

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="5">
**Windows XP**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-012**](http://go.microsoft.com/fwlink/?linkid=392064)

</td>
<td style="border:1px solid black;">
[**MS14-013**](http://go.microsoft.com/fwlink/?linkid=392071)

</td>
<td style="border:1px solid black;">
[**MS14-015**](http://go.microsoft.com/fwlink/?linkid=392067)

</td>
<td style="border:1px solid black;">
[**MS14-016**](http://go.microsoft.com/fwlink/?linkid=392066)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2925418)  
(Critico)  
Internet Explorer 7   
(2925418)  
(Critico)  
Internet Explorer 8   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(con Active Directory Application Mode installato)  
(2933528)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2925418)  
(Critico)  
Internet Explorer 7   
(2925418)  
(Critico)  
Internet Explorer 8   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(con Active Directory Application Mode installato)  
(2933528)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="5">
**Windows Server 2003**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-012**](http://go.microsoft.com/fwlink/?linkid=392064)

</td>
<td style="border:1px solid black;">
[**MS14-013**](http://go.microsoft.com/fwlink/?linkid=392071)

</td>
<td style="border:1px solid black;">
[**MS14-015**](http://go.microsoft.com/fwlink/?linkid=392067)

</td>
<td style="border:1px solid black;">
[**MS14-016**](http://go.microsoft.com/fwlink/?linkid=392066)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2925418)  
(Moderato)  
Internet Explorer 7  
(2925418)  
(Moderato)  
Internet Explorer 8  
(2925418)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(con Active Directory installato)  
(2923392)  
(Importante)  
Windows Server 2003 Service Pack 2  
(con Active Directory Application Mode installato)  
(2933528)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2925418)  
(Moderato)  
Internet Explorer 7  
(2925418)  
(Moderato)  
Internet Explorer 8  
(2925418)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(con Active Directory installato)  
(2923392)  
(Importante)  
Windows Server 2003 x64 Edition Service Pack 2  
(con Active Directory Application Mode installato)  
(2933528)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2925418)  
(Moderato)  
Internet Explorer 7  
(2925418)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(con Active Directory installato)  
(2923392)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="5">
**Windows Vista**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-012**](http://go.microsoft.com/fwlink/?linkid=392064)

</td>
<td style="border:1px solid black;">
[**MS14-013**](http://go.microsoft.com/fwlink/?linkid=392071)

</td>
<td style="border:1px solid black;">
[**MS14-015**](http://go.microsoft.com/fwlink/?linkid=392067)

</td>
<td style="border:1px solid black;">
[**MS14-016**](http://go.microsoft.com/fwlink/?linkid=392066)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2925418)  
(Critico)  
Internet Explorer 8  
(2925418)  
(Critico)  
Internet Explorer 9   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(con Active Directory Lightweight Directory Service (AD LDS) installato)  
(2923392)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2925418)  
(Critico)  
Internet Explorer 8  
(2925418)  
(Critico)  
Internet Explorer 9   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(con Active Directory Lightweight Directory Service (AD LDS) installato)  
(2923392)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="5">
**Windows Server 2008**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-012**](http://go.microsoft.com/fwlink/?linkid=392064)

</td>
<td style="border:1px solid black;">
[**MS14-013**](http://go.microsoft.com/fwlink/?linkid=392071)

</td>
<td style="border:1px solid black;">
[**MS14-015**](http://go.microsoft.com/fwlink/?linkid=392067)

</td>
<td style="border:1px solid black;">
[**MS14-016**](http://go.microsoft.com/fwlink/?linkid=392066)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2925418)  
(Moderato)  
Internet Explorer 8  
(2925418)  
(Moderato)  
Internet Explorer 9   
(2925418)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(con Active Directory or Active Directory Lightweight Directory Service (AD LDS) installato)  
(2923392)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2925418)  
(Moderato)  
Internet Explorer 8  
(2925418)  
(Moderato)  
Internet Explorer 9   
(2925418)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(con Active Directory or Active Directory Lightweight Directory Service (AD LDS) installato)  
(2923392)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2925418)  
(Moderato)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="5">
**Windows 7**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-012**](http://go.microsoft.com/fwlink/?linkid=392064)

</td>
<td style="border:1px solid black;">
[**MS14-013**](http://go.microsoft.com/fwlink/?linkid=392071)

</td>
<td style="border:1px solid black;">
[**MS14-015**](http://go.microsoft.com/fwlink/?linkid=392067)

</td>
<td style="border:1px solid black;">
[**MS14-016**](http://go.microsoft.com/fwlink/?linkid=392066)

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
Nessuno

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2925418)  
(Critico)  
Internet Explorer 9   
(2925418)  
(Critico)  
Internet Explorer 10   
(2925418)  
(Critico)  
Internet Explorer 11   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2930275)  
(Importante)

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
Internet Explorer 8  
(2925418)  
(Critico)  
Internet Explorer 9   
(2925418)  
(Critico)  
Internet Explorer 10   
(2925418)  
(Critico)  
Internet Explorer 11   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="5">
**Windows Server 2008 R2**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-012**](http://go.microsoft.com/fwlink/?linkid=392064)

</td>
<td style="border:1px solid black;">
[**MS14-013**](http://go.microsoft.com/fwlink/?linkid=392071)

</td>
<td style="border:1px solid black;">
[**MS14-015**](http://go.microsoft.com/fwlink/?linkid=392067)

</td>
<td style="border:1px solid black;">
[**MS14-016**](http://go.microsoft.com/fwlink/?linkid=392066)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2925418)  
(Moderato)  
Internet Explorer 9   
(2925418)  
(Moderato)  
Internet Explorer 10   
(2925418)  
(Moderato)  
Internet Explorer 11   
(2925418)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(con Active Directory or Active Directory Lightweight Directory Service (AD LDS) installato)  
(2923392)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2925418)  
(Moderato)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="5">
**Windows 8 e Windows 8.1**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-012**](http://go.microsoft.com/fwlink/?linkid=392064)

</td>
<td style="border:1px solid black;">
[**MS14-013**](http://go.microsoft.com/fwlink/?linkid=392071)

</td>
<td style="border:1px solid black;">
[**MS14-015**](http://go.microsoft.com/fwlink/?linkid=392067)

</td>
<td style="border:1px solid black;">
[**MS14-016**](http://go.microsoft.com/fwlink/?linkid=392066)

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
Nessuno

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit

</td>
<td style="border:1px solid black;">
Internet Explorer 10   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi x64

</td>
<td style="border:1px solid black;">
Internet Explorer 10   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="5">
**Windows Server 2012 e Windows Server 2012 R2**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-012**](http://go.microsoft.com/fwlink/?linkid=392064)

</td>
<td style="border:1px solid black;">
[**MS14-013**](http://go.microsoft.com/fwlink/?linkid=392071)

</td>
<td style="border:1px solid black;">
[**MS14-015**](http://go.microsoft.com/fwlink/?linkid=392067)

</td>
<td style="border:1px solid black;">
[**MS14-016**](http://go.microsoft.com/fwlink/?linkid=392066)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012

</td>
<td style="border:1px solid black;">
Internet Explorer 10   
(2925418)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012  
(con Active Directory installato)  
(2923392)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 R2

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2925418)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(2929961)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(con Active Directory installato)  
(2923392)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="5">
**Windows RT e Windows RT 8.1**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-012**](http://go.microsoft.com/fwlink/?linkid=392064)

</td>
<td style="border:1px solid black;">
[**MS14-013**](http://go.microsoft.com/fwlink/?linkid=392071)

</td>
<td style="border:1px solid black;">
[**MS14-015**](http://go.microsoft.com/fwlink/?linkid=392067)

</td>
<td style="border:1px solid black;">
[**MS14-016**](http://go.microsoft.com/fwlink/?linkid=392066)

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
Nessuno

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
Windows RT

</td>
<td style="border:1px solid black;">
Internet Explorer 10   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows RT  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows RT 8.1

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2925418)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows RT 8.1  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="5">
**Opzione di installazione Server Core**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-012**](http://go.microsoft.com/fwlink/?linkid=392064)

</td>
<td style="border:1px solid black;">
[**MS14-013**](http://go.microsoft.com/fwlink/?linkid=392071)

</td>
<td style="border:1px solid black;">
[**MS14-015**](http://go.microsoft.com/fwlink/?linkid=392067)

</td>
<td style="border:1px solid black;">
[**MS14-016**](http://go.microsoft.com/fwlink/?linkid=392066)

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
Nessuno

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
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(con Active Directory or Active Directory Lightweight Directory Service (AD LDS) installato)  
(2923392)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(con Active Directory or Active Directory Lightweight Directory Service (AD LDS) installato)  
(2923392)  
(Importante)

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
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(con Active Directory or Active Directory Lightweight Directory Service (AD LDS) installato)  
(2923392)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(con Active Directory installato)  
(2923392)  
(Importante)

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
Windows Server 2012 R2 (installazione Server Core)  
(2930275)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2 (installazione Server Core)  
(con Active Directory installato)  
(2923392)  
(Importante)

</td>
</tr>
</table>
 
 

**Strumenti e software Microsoft per gli sviluppatori**

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Silverlight**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-014**](http://go.microsoft.com/fwlink/?linkid=392070)

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
<tr>
<td style="border:1px solid black;">
Microsoft Silverlight 5

</td>
<td style="border:1px solid black;">
Microsoft Silverlight 5 installato in Mac  
(2932677)  
(Importante)  
Microsoft Silverlight 5 Developer Runtime installato in Mac  
(2932677)  
(Importante)  
Microsoft Silverlight 5 installato in tutte le versioni supportate dei client Microsoft Windows  
(2932677)  
(Importante)  
Microsoft Silverlight 5 Developer Runtime installato in tutte le versioni supportate dei client Microsoft Windows  
(2932677)  
(Importante)  
Microsoft Silverlight 5 installato in tutte le versioni supportate dei server Microsoft Windows  
(2932677)  
(Importante)  
Microsoft Silverlight 5 Developer Runtime installato in tutte le versioni supportate dei server Microsoft Windows  
(2932677)  
(Importante)

</td>
</tr>
</table>
 
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span id="sectionToggle3"></span>
Sono disponibili diverse risorse per aiutare gli amministratori a distribuire gli aggiornamenti per la protezione.

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione.

Windows Server Update Services (WSUS), Systems Management Server (SMS) e System Center Configuration Manager (SCCM) aiutano gli amministratori a distribuire gli aggiornamenti per la protezione.

I componenti del programma Update Compatibility Evaluator compresi nell'Application Compatibility Toolkit sono utili per semplificare la verifica e la convalida degli aggiornamenti di Windows per le applicazioni installate.

Per informazioni su questi e altri strumenti disponibili, vedere [Strumenti per la sicurezza](http://technet.microsoft.com/security/cc297183). 

Ringraziamenti
--------------

<span id="sectionToggle4"></span>
Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

**MS14-012**

-   lokihardt@ASRT, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0297)
-   Amol Naik, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0297)
-   Edward Torkington di [NCC Group](https://www.nccgroup.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0297)
-   lokihardt@ASRT, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0298)
-   Jose A. Vazquez di Yenteasy - Security Research, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0299)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0302)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0303)
-   Hui Gao di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0304)
-   Zhibin Hu di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0304)
-   Tianfang Guo di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0305)
-   Jason Kratzer, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0306)
-   Jason Kratzer, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0307)
-   lokihardt@ASRT, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0308)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0308)
-   Jason Kratzer, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0308)
-   Amol Naik, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0309)
-   Scott Bell di [Security-Assessment.com](http://www.security-assessment.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0311)
-   Yujie Wen di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0311)
-   Simon Zuckerbraun, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0312)
-   [Omair](http://krash.in/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0313)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0314)
-   Zhibin Hu di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0314)
-   Liu Long di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0314)
-   Anil Aphale per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0314)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0321)
-   Yujie Wen di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0321)
-   Zhibin Hu di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0321)
-   Liu Long di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0321)
-   Abdul-Aziz Hariri di [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0321)
-   Yuki Chen di [Trend Micro](http://www.trendmicro.com) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0321)
-   [FireEye, Inc.](http://www2.fireeye.com/) per aver collaborato con noi allo studio della vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0322)
-   Liu Long di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0322)
-   Jose A. Vazquez di Yenteasy - Security Research, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4112)

**MS14-013**

-   Un ricercatore anonimo, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in DirectShow (CVE-2014-0301)

**MS14-014**

-   [NSFOCUS Information Technology Co., Ltd.](http://en.nsfocus.com/) per aver segnalato la vulnerabilità legata all'elusione di DEP/ASLR in Silverlight (CVE-2014-0319)

**MS14-015**

-   Alexander Chizhov per aver collaborato con noi sulla vulnerabilità legata all'intercettazione di informazioni personali in Win32k (CVE-2014-0323)

**MS14-016**

-   Andrew Barlett di Samba Team e Catalyst IT per aver segnalato la vulnerabilità legata all'elusione della funzione di protezione SAMR (CVE-2014-0317)
-   [Muhammad Faisal Naqvi](http://ae.linkedin.com/in/mfaisalnaqvi) del Pakistan per aver segnalato la vulnerabilità legata all'elusione della funzione di protezione (CVE-2014-0317)

Altre informazioni
------------------

<span id="sectionToggle5"></span>
### Strumento di rimozione software dannoso di Microsoft Windows

Per il rilascio dei bollettini che avviene il secondo martedì di ogni mese, Microsoft ha rilasciato una versione aggiornata dello Strumento di rimozione software dannoso di Microsoft Windows in Windows Update, Microsoft Update, Windows Server Update Services e nell'Area download. Non è disponibile alcuna versione dello Strumento di rimozione software dannoso di Microsoft Windows per i rilasci di bollettini sulla sicurezza straordinari.

### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](https://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/wsus/bb456965). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://go.microsoft.com/fwlink/?linkid=215201).

### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](https://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

### Supporto

I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).

Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617)

Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)

Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

### Versioni

-   V1.0 (11 marzo 2014): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (18 settembre 2014): Per MS14-012, è stata aggiunta una valutazione dell'Exploitability nell'Exploitability Index per CVE-2014-4112. La modifica è esclusivamente informativa.

*Pagina generata 18-09-2014 10:01Z-07:00.*
