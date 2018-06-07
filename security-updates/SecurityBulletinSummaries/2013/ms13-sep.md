---
TOCTitle: 'MS13-SEP'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Settembre 2013'
ms:assetid: 'ms13-sep'
ms:contentKeyID: 61240089
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms13-sep(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Settembre 2013
===================================================================

Data di pubblicazione: martedì 10 settembre 2013 | Aggiornamento: mercoledì 6 novembre 2013

**Versione:** 1.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati in settembre 2013.

Con il rilascio dei bollettini sulla sicurezza di settembre 2013, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 5 settembre 2013. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini l'11 settembre 2013 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di settembre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032557378&culture=en-us). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032557378&culture=en-us).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft SharePoint Server possono consentire l'esecuzione di codice in modalità remota (2834052)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e nove vulnerabilità segnalate privatamente di Microsoft Office Server. La vulnerabilità più grave può consentire l'esecuzione di codice in modalità remota nel contesto dell'account del servizio W3WP se un utente malintenzionato invia contenuti appositamente predisposti al server interessato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Software dei server Microsoft</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=307055">MS13-068</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Outlook può consentire l'esecuzione di codice in modalità remota (2756473)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Outlook. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre o visualizza in anteprima un messaggio di posta elettronica appositamente predisposto che utilizza un'edizione interessata di Microsoft Outlook. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2870699)</strong><br />
<br />
Questo aggiornamento per la protezione risolve dieci vulnerabilità in Internet Explorer segnalate privatamente. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando la più grave di tali vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320629">MS13-070</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in OLE può consentire l'esecuzione di codice in modalità remota (2876217)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota se un utente apre un file che contiene un oggetto OLE appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314046">MS13-071</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel file dei temi di Windows può consentire l'esecuzione di codice in modalità remota (2864063)<br />
</strong><br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente applica un tema di Windows appositamente predisposto al sistema in uso. In nessuno di questi casi un utente può essere forzato ad aprire il file o applicare il tema; affinché un attacco riesca, l'utente deve eseguire l'operazione in maniera consapevole.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Office possono consentire l'esecuzione di codice in modalità remota (2845537)<br />
</strong><br />
Questo aggiornamento per la protezione risolve tredici vulnerabilità segnalate privatamente<strong></strong>relative a Microsoft Office. Le vulnerabilità più gravi possono consentire l'esecuzione di codice in modalità remota se un file appositamente predisposto è aperto in una versione interessata del software Microsoft Office. Sfruttando le vulnerabilità più gravi, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293351">MS13-073</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (2858300)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità segnalate privatamente in Microsoft Office. Le vulnerabilità più gravi possono consentire l'esecuzione di codice in modalità remota se un utente apre un file di Office appositamente predisposto con una versione interessata di Microsoft Excel o con altro software di Microsoft Office interessato. Sfruttando le vulnerabilità più gravi, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=308989">MS13-074</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Access possono consentire l'esecuzione di codice in modalità remota (2848637)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità segnalate privatamente in Microsoft Office. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file di Access appositamente predisposto con una versione interessata di Microsoft Access. Sfruttando tale vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=318022">MS13-075</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Office IME (cinese) può consentire l'acquisizione di privilegi più elevati (2878687)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office IME (cinese) che è stata segnalata privatamente. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato effettua l'accesso e avvia Internet Explorer dalla barra degli strumenti in Microsoft Pinyin IME per il cinese semplificato. Un utente malintenzionato in grado di sfruttare questa vulnerabilità può eseguire codice arbitrario in modalità kernel. Questi è in grado di installare programmi, visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti amministrativi completi. Solo le implementazioni di Microsoft Pinyin IME 2010 sono interessate da questa vulnerabilità. Le altre versioni dell'IME per il cinese semplificato e le altre implementazioni IME non sono interessate.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320624">MS13-076</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel</strong> <strong>possono consentire l'acquisizione di privilegi più elevati (2876315)</strong><br />
<br />
Questo aggiornamento per la protezione risolve sette vulnerabilità segnalate privatamente in Microsoft Windows. Le vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede al sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare tali vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320630">MS13-077</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità legata alla Gestione controllo servizi di Windows può consentire l'acquisizione di privilegi più elevati (2872339)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente autenticato viene convinto a eseguire un'applicazione appositamente predisposta. Per sfruttare questa vulnerabilità, un utente malintenzionato deve disporre di credenziali di accesso valide ed essere in grado di accedere localmente o deve convincere un utente a eseguire un'applicazione appositamente predisposta.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=318021">MS13-078</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in FrontPage può consentire l'intercettazione di informazioni personali (2825621)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Front Page. Questa vulnerabilità può consentire l'intercettazione di informazioni personali se un utente apre un documento di FrontPage appositamente predisposto. La vulnerabilità non può essere sfruttata automaticamente; l'attacco è possibile solo se l'utente viene convinto ad aprire il documento appositamente predisposto.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320666">MS13-079</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Active Directory può consentire un attacco di tipo Denial of Service (2853587)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Active Directory. La vulnerabilità può consentire un attacco di tipo Denial of Service se un utente malintenzionato invia una query appositamente predisposta al servizio di LDAP (Lightweight Directory Access Protocol).</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;">Vulnerabilità ad attacchi di tipo Denial of Service in SharePoint</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0081">CVE-2013-0081</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Microsoft Office</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1315">CVE-2013-1315</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=293351">MS13-073</a>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla disattivazione di MAC</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1330">CVE-2013-1330</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;">Vulnerabilità XSS di SharePoint</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3179">CVE-2013-3179</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;">Vulnerabilità POST XSS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3180">CVE-2013-3180</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3847">CVE-2013-3847</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3848">CVE-2013-3848</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3849">CVE-2013-3849</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3857">CVE-2013-3857</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a><a href="http://go.microsoft.com/fwlink/?linkid=293350"></a>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3858">CVE-2013-3858</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a><a href="http://go.microsoft.com/fwlink/?linkid=293350"></a>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=307055">MS13-068</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al certificato dei messaggi</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3870">CVE-2013-3870</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3201">CVE-2013-3201</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Internet Explorer 11 non è interessato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3202">CVE-2013-3202</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Internet Explorer 11 non è interessato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3203">CVE-2013-3203</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Internet Explorer 11 non è interessato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3204">CVE-2013-3204</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Internet Explorer 11 non è interessato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3205">CVE-2013-3205</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Internet Explorer 11 non è interessato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3206">CVE-2013-3206</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Internet Explorer 11 non è interessato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3207">CVE-2013-3207</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Internet Explorer 11 non è interessato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3208">CVE-2013-3208</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Internet Explorer 11 non è interessato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3209">CVE-2013-3209</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Internet Explorer 11 non è interessato.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320631">MS13-069</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3845">CVE-2013-3845</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Internet Explorer 11 non è interessato.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320629">MS13-070</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla proprietà OLE</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3863">CVE-2013-3863</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Windows 8.1 e Windows Server 2012 R2 non sono interessati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=314046">MS13-071</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota nel file dei temi di Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0810">CVE-2013-0810</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Windows 8.1 e Windows Server 2012 R2 non sono interessati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione di entità esterne in XML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3160">CVE-2013-3160</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3847">CVE-2013-3847</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3848">CVE-2013-3848</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3849">CVE-2013-3849</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3850">CVE-2013-3850</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3851">CVE-2013-3851</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3852">CVE-2013-3852</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3853">CVE-2013-3853</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3854">CVE-2013-3854</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3855">CVE-2013-3855</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3856">CVE-2013-3856</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3857">CVE-2013-3857</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299217">MS13-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3858">CVE-2013-3858</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a>.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293351">MS13-073</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Microsoft Office</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1315">CVE-2013-1315</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità interessa anche <a href="http://go.microsoft.com/fwlink/?linkid=293350">MS13-067</a>.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293351">MS13-073</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Microsoft Office</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3158">CVE-2013-3158</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=293351">MS13-073</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione di entità esterne in XML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3159">CVE-2013-3159</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=308989">MS13-074</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Access</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3155">CVE-2013-3155</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=308989">MS13-074</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria del formato file Access</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3156">CVE-2013-3156</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=308989">MS13-074</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Access</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3157">CVE-2013-3157</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=318022">MS13-075</a></td>
<td style="border:1px solid black;">Vulnerabilità IME (cinese)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3859">CVE-2013-3859</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320624">MS13-076</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a più recuperi in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1341">CVE-2013-1341</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Windows 8.1 e Windows Server 2012 R2 non sono interessati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320624">MS13-076</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a più recuperi in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1342">CVE-2013-1342</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Windows 8.1 e Windows Server 2012 R2 non sono interessati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320624">MS13-076</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a più recuperi in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1343">CVE-2013-1343</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Windows 8.1 e Windows Server 2012 R2 non sono interessati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320624">MS13-076</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a più recuperi in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1344">CVE-2013-1344</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Windows 8.1 e Windows Server 2012 R2 non sono interessati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320624">MS13-076</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a più recuperi in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3864">CVE-2013-3864</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Windows 8.1 e Windows Server 2012 R2 non sono interessati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320624">MS13-076</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a più recuperi in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3865">CVE-2013-3865</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Windows 8.1 e Windows Server 2012 R2 non sono interessati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320624">MS13-076</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione di privilegi più elevati in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3866">CVE-2013-3866</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Questa è una vulnerabilità ad attacchi di tipo Denial of Service in Windows 8 e Windows Server 2012.<br />
<br />
Windows 8.1 e Windows Server 2012 R2 non sono interessati.<br />
<br />
Si tratta di una vulnerabilità legata all'intercettazione di informazioni personali che può consentire l'acquisizione di privilegi più elevati su altri software interessati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320630">MS13-077</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla condizione double free in Gestione controllo servizi</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3862">CVE-2013-3862</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Windows 8.1 e Windows Server 2012 R2 non sono interessati.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=318021">MS13-078</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla divulgazione XML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3137">CVE-2013-3137</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320666">MS13-079</a></td>
<td style="border:1px solid black;">Vulnerabilità legata ad attacchi di tipo Denial of Service anonimi remoti</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3868">CVE-2013-3868</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.<br />
<br />
Windows 8.1 e Windows Server 2012 R2 non sono interessati.</td>
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
<th colspan="7">
Windows XP
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-069**](http://go.microsoft.com/fwlink/?linkid=320631)
</td>
<td style="border:1px solid black;">
[**MS13-070**](http://go.microsoft.com/fwlink/?linkid=320629)
</td>
<td style="border:1px solid black;">
[**MS13-071**](http://go.microsoft.com/fwlink/?linkid=314046)
</td>
<td style="border:1px solid black;">
[**MS13-076**](http://go.microsoft.com/fwlink/?linkid=320624)
</td>
<td style="border:1px solid black;">
[**MS13-077**](http://go.microsoft.com/fwlink/?linkid=320630)
</td>
<td style="border:1px solid black;">
[**MS13-079**](http://go.microsoft.com/fwlink/?linkid=320666)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2870699)  
(Critico)  
Internet Explorer 7  
(2870699)  
(Critico)  
Internet Explorer 8  
(2870699)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2876217)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2864063)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2876315)  
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
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2870699)  
(Critico)  
Internet Explorer 7  
(2870699)  
(Critico)  
Internet Explorer 8  
(2870699)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2876217)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2864063)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2876315)  
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
<th colspan="7">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-069**](http://go.microsoft.com/fwlink/?linkid=320631)
</td>
<td style="border:1px solid black;">
[**MS13-070**](http://go.microsoft.com/fwlink/?linkid=320629)
</td>
<td style="border:1px solid black;">
[**MS13-071**](http://go.microsoft.com/fwlink/?linkid=314046)
</td>
<td style="border:1px solid black;">
[**MS13-076**](http://go.microsoft.com/fwlink/?linkid=320624)
</td>
<td style="border:1px solid black;">
[**MS13-077**](http://go.microsoft.com/fwlink/?linkid=320630)
</td>
<td style="border:1px solid black;">
[**MS13-079**](http://go.microsoft.com/fwlink/?linkid=320666)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2870699)  
(Moderato)  
Internet Explorer 7  
(2870699)  
(Moderato)  
Internet Explorer 8  
(2870699)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2876217)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2864063)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2876315)  
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
Internet Explorer 6  
(2870699)  
(Moderato)  
Internet Explorer 7  
(2870699)  
(Moderato)  
Internet Explorer 8  
(2870699)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2876217)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2864063)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2876315)  
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
Internet Explorer 6  
(2870699)  
(Moderato)  
Internet Explorer 7  
(2870699)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2876217)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2864063)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2876315)  
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
<th colspan="7">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-069**](http://go.microsoft.com/fwlink/?linkid=320631)
</td>
<td style="border:1px solid black;">
[**MS13-070**](http://go.microsoft.com/fwlink/?linkid=320629)
</td>
<td style="border:1px solid black;">
[**MS13-071**](http://go.microsoft.com/fwlink/?linkid=314046)
</td>
<td style="border:1px solid black;">
[**MS13-076**](http://go.microsoft.com/fwlink/?linkid=320624)
</td>
<td style="border:1px solid black;">
[**MS13-077**](http://go.microsoft.com/fwlink/?linkid=320630)
</td>
<td style="border:1px solid black;">
[**MS13-079**](http://go.microsoft.com/fwlink/?linkid=320666)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2870699)  
(Critico)  
Internet Explorer 8  
(2870699)  
(Critico)  
Internet Explorer 9  
(2870699)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2864063)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2870699)  
(Critico)  
Internet Explorer 8  
(2870699)  
(Critico)  
Internet Explorer 9  
(2870699)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2864063)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-069**](http://go.microsoft.com/fwlink/?linkid=320631)
</td>
<td style="border:1px solid black;">
[**MS13-070**](http://go.microsoft.com/fwlink/?linkid=320629)
</td>
<td style="border:1px solid black;">
[**MS13-071**](http://go.microsoft.com/fwlink/?linkid=314046)
</td>
<td style="border:1px solid black;">
[**MS13-076**](http://go.microsoft.com/fwlink/?linkid=320624)
</td>
<td style="border:1px solid black;">
[**MS13-077**](http://go.microsoft.com/fwlink/?linkid=320630)
</td>
<td style="border:1px solid black;">
[**MS13-079**](http://go.microsoft.com/fwlink/?linkid=320666)
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
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2870699)  
(Moderato)  
Internet Explorer 8  
(2870699)  
(Moderato)  
Internet Explorer 9  
(2870699)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2864063)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Active Directory Services  
(2853587)  
(Importante)  
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2870699)  
(Moderato)  
Internet Explorer 8  
(2870699)  
(Moderato)  
Internet Explorer 9  
(2870699)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2864063)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Active Directory Services  
(2853587)  
(Importante)  
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2870699)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2864063)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2876315)  
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
<th colspan="7">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-069**](http://go.microsoft.com/fwlink/?linkid=320631)
</td>
<td style="border:1px solid black;">
[**MS13-070**](http://go.microsoft.com/fwlink/?linkid=320629)
</td>
<td style="border:1px solid black;">
[**MS13-071**](http://go.microsoft.com/fwlink/?linkid=314046)
</td>
<td style="border:1px solid black;">
[**MS13-076**](http://go.microsoft.com/fwlink/?linkid=320624)
</td>
<td style="border:1px solid black;">
[**MS13-077**](http://go.microsoft.com/fwlink/?linkid=320630)
</td>
<td style="border:1px solid black;">
[**MS13-079**](http://go.microsoft.com/fwlink/?linkid=320666)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2870699)  
(Critico)  
Internet Explorer 9  
(2870699)  
(Critico)  
Internet Explorer 10  
(2870699)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2872339)  
(Importante)
</td>
<td style="border:1px solid black;">
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2870699)  
(Critico)  
Internet Explorer 9  
(2870699)  
(Critico)  
Internet Explorer 10  
(2870699)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2872339)  
(Importante)
</td>
<td style="border:1px solid black;">
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-069**](http://go.microsoft.com/fwlink/?linkid=320631)
</td>
<td style="border:1px solid black;">
[**MS13-070**](http://go.microsoft.com/fwlink/?linkid=320629)
</td>
<td style="border:1px solid black;">
[**MS13-071**](http://go.microsoft.com/fwlink/?linkid=314046)
</td>
<td style="border:1px solid black;">
[**MS13-076**](http://go.microsoft.com/fwlink/?linkid=320624)
</td>
<td style="border:1px solid black;">
[**MS13-077**](http://go.microsoft.com/fwlink/?linkid=320630)
</td>
<td style="border:1px solid black;">
[**MS13-079**](http://go.microsoft.com/fwlink/?linkid=320666)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
(2870699)  
(Moderato)  
Internet Explorer 9  
(2870699)  
(Moderato)  
Internet Explorer 10  
(2870699)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2872339)  
(Importante)
</td>
<td style="border:1px solid black;">
Active Directory Services  
(2853587)  
(Importante)  
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2870699)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2872339)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="7">
Windows 8
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-069**](http://go.microsoft.com/fwlink/?linkid=320631)
</td>
<td style="border:1px solid black;">
[**MS13-070**](http://go.microsoft.com/fwlink/?linkid=320629)
</td>
<td style="border:1px solid black;">
[**MS13-071**](http://go.microsoft.com/fwlink/?linkid=314046)
</td>
<td style="border:1px solid black;">
[**MS13-076**](http://go.microsoft.com/fwlink/?linkid=320624)
</td>
<td style="border:1px solid black;">
[**MS13-077**](http://go.microsoft.com/fwlink/?linkid=320630)
</td>
<td style="border:1px solid black;">
[**MS13-079**](http://go.microsoft.com/fwlink/?linkid=320666)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows 8 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2870699)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2870699)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2012
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-069**](http://go.microsoft.com/fwlink/?linkid=320631)
</td>
<td style="border:1px solid black;">
[**MS13-070**](http://go.microsoft.com/fwlink/?linkid=320629)
</td>
<td style="border:1px solid black;">
[**MS13-071**](http://go.microsoft.com/fwlink/?linkid=314046)
</td>
<td style="border:1px solid black;">
[**MS13-076**](http://go.microsoft.com/fwlink/?linkid=320624)
</td>
<td style="border:1px solid black;">
[**MS13-077**](http://go.microsoft.com/fwlink/?linkid=320630)
</td>
<td style="border:1px solid black;">
[**MS13-079**](http://go.microsoft.com/fwlink/?linkid=320666)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows Server 2012
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2870699)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Active Directory Services  
(2853587)  
(Importante)  
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
<tr>
<th colspan="7">
Windows RT
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-069**](http://go.microsoft.com/fwlink/?linkid=320631)
</td>
<td style="border:1px solid black;">
[**MS13-070**](http://go.microsoft.com/fwlink/?linkid=320629)
</td>
<td style="border:1px solid black;">
[**MS13-071**](http://go.microsoft.com/fwlink/?linkid=314046)
</td>
<td style="border:1px solid black;">
[**MS13-076**](http://go.microsoft.com/fwlink/?linkid=320624)
</td>
<td style="border:1px solid black;">
[**MS13-077**](http://go.microsoft.com/fwlink/?linkid=320630)
</td>
<td style="border:1px solid black;">
[**MS13-079**](http://go.microsoft.com/fwlink/?linkid=320666)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Windows RT
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2870699)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows RT  
(2876315)  
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
<th colspan="7">
Opzione di installazione Server Core
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-069**](http://go.microsoft.com/fwlink/?linkid=320631)
</td>
<td style="border:1px solid black;">
[**MS13-070**](http://go.microsoft.com/fwlink/?linkid=320629)
</td>
<td style="border:1px solid black;">
[**MS13-071**](http://go.microsoft.com/fwlink/?linkid=314046)
</td>
<td style="border:1px solid black;">
[**MS13-076**](http://go.microsoft.com/fwlink/?linkid=320624)
</td>
<td style="border:1px solid black;">
[**MS13-077**](http://go.microsoft.com/fwlink/?linkid=320630)
</td>
<td style="border:1px solid black;">
[**MS13-079**](http://go.microsoft.com/fwlink/?linkid=320666)
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
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
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
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Active Directory Services  
(2853587)  
(Importante)  
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Active Directory Services  
(2853587)  
(Importante)  
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2872339)
</td>
<td style="border:1px solid black;">
Active Directory Services  
(2853587)  
(Importante)  
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2876315)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Active Directory Services  
(2853587)  
(Importante)  
Active Directory Lightweight Directory Service (AD LDS)  
(2853587)  
(Importante)
</td>
</tr>
</table>
 

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="6">
Microsoft Office 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-068**](http://go.microsoft.com/fwlink/?linkid=307055)
</td>
<td style="border:1px solid black;">
[**MS13-072**](http://go.microsoft.com/fwlink/?linkid=299217)
</td>
<td style="border:1px solid black;">
[**MS13-073**](http://go.microsoft.com/fwlink/?linkid=293351)
</td>
<td style="border:1px solid black;">
[**MS13-074**](http://go.microsoft.com/fwlink/?linkid=308989)
</td>
<td style="border:1px solid black;">
[**MS13-075**](http://go.microsoft.com/fwlink/?linkid=318022)
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
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3  
(MSO)  
(2817474)  
(Importante)  
Microsoft Word 2003 Service Pack 3  
(2817682)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2003 Service Pack 3  
(2810048)  
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
<th colspan="6">
Microsoft Office 2007
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-068**](http://go.microsoft.com/fwlink/?linkid=307055)
</td>
<td style="border:1px solid black;">
[**MS13-072**](http://go.microsoft.com/fwlink/?linkid=299217)
</td>
<td style="border:1px solid black;">
[**MS13-073**](http://go.microsoft.com/fwlink/?linkid=293351)
</td>
<td style="border:1px solid black;">
[**MS13-074**](http://go.microsoft.com/fwlink/?linkid=308989)
</td>
<td style="border:1px solid black;">
[**MS13-075**](http://go.microsoft.com/fwlink/?linkid=318022)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
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
**Nessuno**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2007 Service Pack 3  
(2825999)  
(Critico)
</td>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3  
(MSO)  
(2760411)  
(Importante)  
Microsoft Office 2007 Service Pack 3  
(MSPTLS)  
(2597973)  
(Importante)  
Microsoft Word 2007 Service Pack 3  
(2767773)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2007 Service Pack 3  
(2760583)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Access 2007 Service Pack 3  
(2596825)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="6">
Microsoft Office 2010
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-068**](http://go.microsoft.com/fwlink/?linkid=307055)
</td>
<td style="border:1px solid black;">
[**MS13-072**](http://go.microsoft.com/fwlink/?linkid=299217)
</td>
<td style="border:1px solid black;">
[**MS13-073**](http://go.microsoft.com/fwlink/?linkid=293351)
</td>
<td style="border:1px solid black;">
[**MS13-074**](http://go.microsoft.com/fwlink/?linkid=308989)
</td>
<td style="border:1px solid black;">
[**MS13-075**](http://go.microsoft.com/fwlink/?linkid=318022)
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2010 Service Pack 1 (edizioni a 32 bit)  
(2794707)  
(Critico)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 1 (edizioni a 32 bit)  
(2760769)  
(Importante)  
Microsoft Word 2010 Service Pack 1 (edizioni a 32 bit)  
(2767913)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2010 Service Pack 1 (edizioni a 32 bit)  
(2760597)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Access 2010 Service Pack 1 (edizioni a 32 bit)  
(2687423)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Pinyin IME 2010 (versione a 32 bit)  
(2687413)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2010 Service Pack 2 (edizioni a 32 bit)  
(2794707)  
(Critico)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 2 (edizioni a 32 bit)  
(2760769)  
(Importante)  
Microsoft Word 2010 Service Pack 2 (edizioni a 32 bit)  
(2767913)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2010 Service Pack 2 (edizioni a 32 bit)  
(2760597)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Access 2010 Service Pack 2 (edizioni a 32 bit)  
(2687423)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2010 Service Pack 1 (edizioni a 64 bit)  
(2794707)  
(Critico)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 1 (edizioni a 64 bit)  
(2760769)  
(Importante)  
Microsoft Word 2010 Service Pack 1 (edizioni a 64 bit)  
(2767913)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2010 Service Pack 1 (edizioni a 64 bit)  
(2760597)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Access 2010 Service Pack 1 (edizioni a 64 bit)  
(2687423)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Pinyin IME 2010 (versione a 64 bit)  
(2687413)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2010 Service Pack 2 (edizioni a 64 bit)  
(2794707)  
(Critico)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 2 (edizioni a 64 bit)  
(2760769)  
(Importante)  
Microsoft Word 2010 Service Pack 2 (edizioni a 64 bit)  
(2767913)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Excel 2010 Service Pack 2 (edizioni a 64 bit)  
(2760597)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Access 2010 Service Pack 2 (edizioni a 64 bit)  
(2687423)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="6">
Microsoft Office 2013
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-068**](http://go.microsoft.com/fwlink/?linkid=307055)
</td>
<td style="border:1px solid black;">
[**MS13-072**](http://go.microsoft.com/fwlink/?linkid=299217)
</td>
<td style="border:1px solid black;">
[**MS13-073**](http://go.microsoft.com/fwlink/?linkid=293351)
</td>
<td style="border:1px solid black;">
[**MS13-074**](http://go.microsoft.com/fwlink/?linkid=308989)
</td>
<td style="border:1px solid black;">
[**MS13-075**](http://go.microsoft.com/fwlink/?linkid=318022)
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
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Excel 2013 (edizioni a 32 bit)  
(2768017)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Access 2013 (edizioni a 32 bit)  
(2810009)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Excel 2013 (edizioni a 64 bit)  
(2768017)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Access 2013 (edizioni a 64 bit)  
(2810009)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Excel 2013 RT  
(2768017)  
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
<th colspan="6">
Microsoft Office per Mac
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-068**](http://go.microsoft.com/fwlink/?linkid=307055)
</td>
<td style="border:1px solid black;">
[**MS13-072**](http://go.microsoft.com/fwlink/?linkid=299217)
</td>
<td style="border:1px solid black;">
[**MS13-073**](http://go.microsoft.com/fwlink/?linkid=293351)
</td>
<td style="border:1px solid black;">
[**MS13-074**](http://go.microsoft.com/fwlink/?linkid=308989)
</td>
<td style="border:1px solid black;">
[**MS13-075**](http://go.microsoft.com/fwlink/?linkid=318022)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Microsoft Office per Mac 2011
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Office per Mac 2011  
(2877813)  
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
<th colspan="6">
Altro software Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-068**](http://go.microsoft.com/fwlink/?linkid=307055)
</td>
<td style="border:1px solid black;">
[**MS13-072**](http://go.microsoft.com/fwlink/?linkid=299217)
</td>
<td style="border:1px solid black;">
[**MS13-073**](http://go.microsoft.com/fwlink/?linkid=293351)
</td>
<td style="border:1px solid black;">
[**MS13-074**](http://go.microsoft.com/fwlink/?linkid=308989)
</td>
<td style="border:1px solid black;">
[**MS13-075**](http://go.microsoft.com/fwlink/?linkid=318022)
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
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Pacchetto di compatibilità Microsoft Office Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3  
(2760823)  
(Importante)
</td>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3  
(2760588)  
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
Microsoft Word Viewer
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Word Viewer  
(2817683)  
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Excel Viewer
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Excel Viewer  
(2760590)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
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
Microsoft SharePoint Portal Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-067**](http://go.microsoft.com/fwlink/?linkid=293350)
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
Microsoft SharePoint Portal Server 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 2.0  
(2810061)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft SharePoint Server 2007
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-067**](http://go.microsoft.com/fwlink/?linkid=293350)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 3 (versioni a 32 bit)  
(2760420)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 3 (versioni a 64 bit)  
(2760420)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft SharePoint Server 2010
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-067**](http://go.microsoft.com/fwlink/?linkid=293350)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Microsoft SharePoint Foundation 2010 Service Pack 1 (wss)  
(2810067)  
(Critico)  
Microsoft SharePoint Server 2010 Service Pack 1 (coreserver)  
(2817393)  
(Critico)  
Microsoft SharePoint Server 2010 Service Pack 1 (wosrv)  
(2817372)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft SharePoint Foundation 2010 Service Pack 2 (wss)  
(2810067)  
(Critico)  
Microsoft SharePoint Server 2010 Service Pack 2 (coreserver)  
(2817393)  
(Critico)  
Microsoft SharePoint Server 2010 Service Pack 2 (wosrv)  
(2817372)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft SharePoint Server 2013
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-067**](http://go.microsoft.com/fwlink/?linkid=293350)
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
Microsoft SharePoint Server 2013
</td>
<td style="border:1px solid black;">
Microsoft SharePoint Foundation 2013  
(2817315)  
(Importante)  
Microsoft SharePoint Server 2013 (coreserverloc)  
(2810083)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS13-067**

Vedere ulteriori categorie software nella sezione **Software interessato**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software

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
[**MS13-067**](http://go.microsoft.com/fwlink/?linkid=293350)
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
(2760589)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2007 Service Pack 3 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Excel Services  
(2760589)  
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
[**MS13-067**](http://go.microsoft.com/fwlink/?linkid=293350)
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
Microsoft SharePoint Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Excel Services  
(2760595)  
(Critico)  
Microsoft Business Productivity Servers  
(2553408)  
(Critico)  
Word Automation Services  
(2760755)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 2
</td>
<td style="border:1px solid black;">
Excel Services  
(2760595)  
(Critico)  
Microsoft Business Productivity Servers  
(2553408)  
(Critico)  
Word Automation Services  
(2760755)  
(Critico)
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
[**MS13-067**](http://go.microsoft.com/fwlink/?linkid=293350)
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
Microsoft Office Web Apps 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Microsoft Excel Web App 2010 Service Pack 1  
(2760594)  
(Critico)  
Microsoft Word Web App 2010 Service Pack 1  
(2817384)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Web Apps 2010 Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft Excel Web App 2010 Service Pack 2  
(2760594)  
(Critico)  
Microsoft Word Web App 2010 Service Pack 2  
(2817384)  
(Critico)
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
[**MS13-067**](http://go.microsoft.com/fwlink/?linkid=293350)
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
(2817305)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS13-067**

Vedere ulteriori categorie software nella sezione **Software interessato**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software

#### Software di produttività

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Frontpage 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-078**](http://go.microsoft.com/fwlink/?linkid=318021)
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
Microsoft FrontPage 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft FrontPage 2003 Service Pack 3  
(2825621)  
(Importante)
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security TechCenter](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. I clienti possono visitare [Microsoft Safety &amp; Security Center](http://www.microsoft.com/italy/athome/security/default.mspx), dove queste informazioni sono disponibili anche facendo clic su "Aggiornamenti per la protezione".

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS13-001"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, vedere [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/wsus/default).

**SystemCenter Configuration Manager**

Gestione aggiornamenti software di System Center Configuration Manager semplifica la consegna e la gestione degli aggiornamenti dei sistemi IT in tutta l'azienda. Con System Center Configuration Manager, gli amministratori IT possono distribuire gli aggiornamenti dei prodotti Microsoft a diverse periferiche compresi desktop, portatili, server e dispositivi mobili.

La valutazione automatica della vulnerabilità disponibile in System Center Configuration Manager rileva la necessità di effettuare gli aggiornamenti ed invia relazioni sulle azioni consigliate. Gestione aggiornamenti software di System Center Configuration Manager si basa su Microsoft Windows Software Update Services (WSUS), un'infrastruttura di aggiornamento tempestiva conosciuta agli amministratori IT in tutto il mondo. Per ulteriori informazioni su System Center Configuration Manager, visitare il sito [Risorse tecniche di System Center](http://technet.microsoft.com/systemcenter/bb980621).

**Systems Management Server 2003**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali.

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager; vedere anche la sezione precedente, **System Center Configuration Manager**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/systemcenter/bb545936).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. I componenti del programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc749197), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971), consentono di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

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

**MS13-067**

-   Will Dormann di [CERT/CC](http://www.cert.org/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Microsoft Office (CVE-2013-1315)
-   Alexandre Herzog di [Compass Security AG](http://www.csnc.ch/) per aver segnalato la vulnerabilità legata alla disattivazione di MAC (CVE-2013-1330)
-   Benjamin Kunz Mejri di Vulnerability Research Laboratory per aver segnalato la vulnerabilità legata al filtro XSS in SharePoint (CVE-2013-3179)
-   Mateusz Jurczyk, Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato varie vulnerabilità legate al danneggiamento della memoria in Microsoft Word (CVE-2013-3847, CVE-2013-3848, CVE-2013-3849, CVE-2013-3857, CVE-2013-3858)

**MS13-068**

-   Alexander Klink di [n.runs AG](https://www.nruns.com/) per aver segnalato la vulnerabilità legata al certificato dei messaggi (CVE-2013-3870)

**MS13-069**

-   Jose Antonio Vazquez Gonzalez, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3201)
-   Jose Antonio Vazquez Gonzalez, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3202)
-   Arthur Gerkis, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3203)
-   Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3204)
-   Peter 'corelanc0d3r' Van Eeckhoutte di [Corelan](http://www.corelangcv.com/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3205)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3205)
-   Arthur Gerkis, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3206)
-   Arthur Gerkis, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3207)
-   Arthur Gerkis, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3208)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3209)
-   Jose Antonio Vazquez Gonzalez, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3845)

**MS13-070**

-   G. Geshev, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata alla proprietà OLE (CVE-2013-3863)

**MS13-071**

-   Eduardo Prado, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata all'esecuzione di codice in modalità remota nel file dei temi di Windows (CVE-2013-0810)

**MS13-072**

-   Timur Yunusov, Alexey Osipov e Ilya Karpov di [Positive Technologies](http://www.ptsecurity.com/) per aver segnalato la vulnerabilità legata alla risoluzione di entità XML esterne (CVE-2013-3160)
-   Mateusz Jurczyk, Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato molteplici vulnerabilità legate al danneggiamento della memoria in Microsoft Word (CVE-2013-3847, CVE-2013-3848, CVE-2013-3849, CVE-2013-3850, CVE-2013-3851, CVE-2013-3852, CVE-2013-3853, CVE-2013-3854, CVE-2013-3855, CVE-2013-3856, CVE-2013-3857, CVE-2013-3858)

**MS13-073**

-   Will Dormann di [CERT/CC](http://www.cert.org/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Microsoft Office (CVE-2013-1315)
-   Will Dormann di [CERT/CC](http://www.cert.org/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Microsoft Office (CVE-2013-3158)
-   Timur Yunusov, Alexey Osipov e Ilya Karpov di [Positive Technologies](http://www.ptsecurity.com/) per aver segnalato la vulnerabilità legata alla risoluzione di entità XML esterne (CVE-2013-3159)

**MS13-074**

-   Kaveh Ghaemmaghami di [Secunia SVCRP](http://secunia.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Access (CVE-2013-3155)
-   Kaveh Ghaemmaghami di [Secunia SVCRP](http://secunia.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria del formato file di Access (CVE-2013-3156)
-   Kaveh Ghaemmaghami di [Secunia SVCRP](http://secunia.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Access (CVE-2013-3157)

**MS13-075**

-   Wei Wang di [VulnHunt](http://www.vulnhunt.com/) per aver segnalato la vulnerabilità legata all'IME per il cinese (CVE-2013-3859)

**MS13-076**

-   [Gynvael Coldwind](http://gynvael.coldwind.pl/) e [Mateusz "j00ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc](http://www.google.com/) per aver segnalato la vulnerabilità legata al recupero multiplo in Win32k (CVE-2013-1341)
-   [Gynvael Coldwind](http://gynvael.coldwind.pl/) e [Mateusz "j00ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc](http://www.google.com/) per aver segnalato la vulnerabilità legata al recupero multiplo in Win32k (CVE-2013-1342)
-   [Gynvael Coldwind](http://gynvael.coldwind.pl/) e [Mateusz "j00ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc](http://www.google.com/) per aver segnalato la vulnerabilità legata al recupero multiplo in Win32k (CVE-2013-1343)
-   [Mateusz "j00ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc](http://www.google.com/) per aver segnalato la vulnerabilità legata al recupero multiplo in Win32k (CVE-2013-1344)
-   [Gynvael Coldwind](http://gynvael.coldwind.pl/) e [Mateusz "j00ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc](http://www.google.com/) per aver segnalato la vulnerabilità legata al recupero multiplo in Win32k (CVE-2013-3864)
-   [Gynvael Coldwind](http://gynvael.coldwind.pl/) e [Mateusz "j00ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc](http://www.google.com/) per aver segnalato la vulnerabilità legata al recupero multiplo in Win32k (CVE-2013-3865)
-   Guo Pengfei di [Qihoo 360 Security Center](http://www.360.cn/) per aver segnalato la vulnerabilità legata all'acquisizione di privilegi più elevati in Win32k (CVE-2013-3866)

**MS13-078**

-   Timur Yunusov di [Positive Technologies](http://www.ptsecurity.com/) per aver segnalato la vulnerabilità legata all'intercettazione di informazioni personali in XML (CVE-2013-3137)

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (10 settembre 2013): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (6 novembre 2013): Per MS13-067, è stato corretto il nome del prodotto per l'aggiornamento Microsoft Office Web Apps Server 2013 (2817305).

*Built at 2014-04-18T01:50:00Z-07:00*
