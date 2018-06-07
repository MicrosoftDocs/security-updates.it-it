---
TOCTitle: 'MS13-JUL'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Luglio 2013'
ms:assetid: 'ms13-jul'
ms:contentKeyID: 61240083
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms13-jul(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Luglio 2013
================================================================

Data di pubblicazione: martedì 9 luglio 2013 | Aggiornamento: martedì 27 agosto 2013

**Versione:** 3.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a luglio 2013.

Con il rilascio dei bollettini sulla sicurezza di luglio 2013, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 4 luglio 2013. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 10 luglio 2013 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di luglio](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032556406&culture=en-us). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032538733&culture=en-us).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299844">MS13-052</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in .NET Framework e Silverlight possono consentire l'esecuzione di codice in modalità remota (2861561)</strong><br />
<br />
Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente e due vulnerabilità divulgate pubblicamente in Microsoft.NET Framework e Microsoft Silverlight. La più grave di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota se un'applicazione fidata utilizza un modello di codice particolare. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework,<br />
Microsoft Silverlight</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301423">MS13-053</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità</strong> <strong>nei</strong> <strong>driver in modalità kernel di Windows possono consentire l'esecuzione di codice in modalità remota (2850851)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve due vulnerabilità divulgate pubblicamente e sei vulnerabilità segnalate privatamente in Microsoft Windows. La più grave di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza contenuto condiviso che include file di caratteri TrueType. Sfruttando questa vulnerabilità, un utente malintenzionato può assumere il pieno controllo del sistema interessato.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301531">MS13-054</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in</strong> <strong>GDI+</strong> <strong>può consentire l'esecuzione di codice in modalità remota (2848295)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Windows, Microsoft Office, Microsoft Lync e Microsoft Visual Studio. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza contenuto condiviso che include file di caratteri TrueType.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft Office,<br />
Microsoft Visual Studio,<br />
Microsoft Lync</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2846071)</strong> <strong><br />
<br />
</strong>Questo aggiornamento per la protezione risolve diciassette vulnerabilità in Internet Explorer segnalate privatamente. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando la più grave di tali vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309326">MS13-056</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft DirectShow può consentire l'esecuzione di codice in modalità remota (2845187)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota se un utente apre un file di immagine appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301528">MS13-057</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Runtime formato Windows Media può consentire l'esecuzione di codice in modalità remota (2847883)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file multimediale appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=308992">MS13-058</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Windows Defender può consentire l'acquisizione di privilegi più elevati (2847927)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Windows Defender per Windows 7 e Windows Defender installati in Windows Server 2008 R2. La vulnerabilità può consentire l'acquisizione di privilegi più elevati a causa dei nomi percorso utilizzati da Windows Defender. Un utente malintenzionato che sfrutti questa vulnerabilità potrebbe eseguire codice non autorizzato e acquisire il controllo completo del sistema interessato. Inoltre, può installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. L'utente malintenzionato deve essere in possesso di credenziali di accesso valide per sfruttare questa vulnerabilità. La vulnerabilità non può essere sfruttata da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Software di protezione Microsoft</td>
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299844">MS13-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi dei caratteri TrueType</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3129">CVE-2013-3129</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299844">MS13-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla violazione dell'accesso degli array</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3131">CVE-2013-3131</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299844">MS13-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'elusione della riflessione delegata</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3132">CVE-2013-3132</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299844">MS13-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'immissione anonima di metodo</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3133">CVE-2013-3133</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299844">MS13-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'allocazione degli array</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3134">CVE-2013-3134</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299844">MS13-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla serializzazione di oggetti delegati</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3171">CVE-2013-3171</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=299844">MS13-052</a></td>
<td style="border:1px solid black;">Vulnerabilità del puntatore NULL</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3178">CVE-2013-3178</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301423">MS13-053</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'allocazione della memoria in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1300">CVE-2013-1300</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301423">MS13-053</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1340">CVE-2013-1340</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service sulla versione più recente del software.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301423">MS13-053</a></td>
<td style="border:1px solid black;">Vulnerabilità in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1345">CVE-2013-1345</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service sulla versione più recente del software.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301423">MS13-053</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi dei caratteri TrueType</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3129">CVE-2013-3129</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301423">MS13-053</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni personali in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3167">CVE-2013-3167</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità legata all'intercettazione di informazioni personali che può consentire un'acquisizione di privilegi più elevati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301423">MS13-053</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al sovraccarico del buffer in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3173">CVE-2013-3173</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301423">MS13-053</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla lettura AV in Win32k</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3660">CVE-2013-3660</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Microsoft è a conoscenza di attacchi mirati che tentano di sfruttare questa vulnerabilità per l'acquisizione di privilegi più elevati.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301531">MS13-054</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi dei caratteri TrueType</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3129">CVE-2013-3129</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3115">CVE-2013-3115</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3143">CVE-2013-3143</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3144">CVE-2013-3144</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3145">CVE-2013-3145</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3146">CVE-2013-3146</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3147">CVE-2013-3147</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3148">CVE-2013-3148</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3149">CVE-2013-3149</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3150">CVE-2013-3150</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3151">CVE-2013-3151</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3152">CVE-2013-3152</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3153">CVE-2013-3153</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3161">CVE-2013-3161</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3162">CVE-2013-3162</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3163">CVE-2013-3163</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Microsoft è a conoscenza di attacchi mirati che tentano di sfruttare questa vulnerabilità attraverso Internet Explorer 8.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3164">CVE-2013-3164</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309324">MS13-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla codifica del carattere Shift JIS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3166">CVE-2013-3166</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=309326">MS13-056</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla sovrascrittura della memoria arbitraria in DirectShow</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3174">CVE-2013-3174</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=301528">MS13-057</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'esecuzione di codice in modalità remota nel decoder video WMV</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3127">CVE-2013-3127</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=308992">MS13-058</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un nome percorso errato in Windows Defender per Microsoft Windows 7</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3154">CVE-2013-3154</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
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
<th colspan="8">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-053**](http://go.microsoft.com/fwlink/?linkid=301423)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
</td>
<td style="border:1px solid black;">
[**MS13-055**](http://go.microsoft.com/fwlink/?linkid=309324)
</td>
<td style="border:1px solid black;">
[**MS13-056**](http://go.microsoft.com/fwlink/?linkid=309326)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS13-057**](http://go.microsoft.com/fwlink/?linkid=301528)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.0 Service Pack 3  
(solo Media Center Edition 2005 Service Pack 3 e Tablet PC Edition 2005 Service Pack 3)  
(2833951)  
(Importante)  
Microsoft .NET Framework 1.1 Service Pack 1  
(2833941)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2833940)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2844285)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2832411)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2840629)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2832407)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(Windows GDI+)  
(2834886)  
(Critico)  
Windows XP Service Pack 3  
(Solo Windows XP Tablet PC Edition 2005)  
(Journal)  
(2835364)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2846071)  
(Critico)  
Internet Explorer 7  
(2846071)  
(Critico)  
Internet Explorer 8  
(2846071)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Runtime formato Windows Media 11<sup>[1]</sup>
(wmvdecod.dll)  
(Solo Media Center Edition)  
(2834904)  
(Critico)  
Runtime formato Windows Media 9.5  
(wmvdmod.dll)  
(Solo Media Center Edition)  
(2834905)  
(Critico)  
Runtime formato Windows Media 9  
(wmvdmod.dll)  
(2803821)  
(Critico)  
Runtime formato Windows Media 9.5<sup>[2]</sup>
(wmvdmod.dll)  
(2834902)  
(Critico)  
Runtime formato Windows Media 9.5<sup>[3]</sup>
(wmvdmod.dll)  
(2834903)  
(Critico)  
Runtime formato Windows Media 11  
(wmvdecod.dll)  
(2834904)  
(Critico)  
wmv9vcm.dll (codec)  
(2845142)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.1 Service Pack 1  
(2833941)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2833940)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2844285)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2832411)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2832407)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
  
(2840628)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(Windows GDI+)  
(2834886)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2846071)  
(Critico)  
Internet Explorer 7  
(2846071)  
(Critico)  
Internet Explorer 8  
(2846071)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Runtime formato Windows Media 9.5  
(wmvdmod.dll)  
(2803821)  
(Critico)  
Runtime formato Windows Media 9.5 x64  
(wmvdmod.dll)  
(2834902)  
(Critico)  
Runtime formato Windows Media 11  
(wmvdecod.dll)  
(2834904)  
(Critico)  
wmv9vcm.dll (codec)  
(2845142)  
(Critico)
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
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-053**](http://go.microsoft.com/fwlink/?linkid=301423)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
</td>
<td style="border:1px solid black;">
[**MS13-055**](http://go.microsoft.com/fwlink/?linkid=309324)
</td>
<td style="border:1px solid black;">
[**MS13-056**](http://go.microsoft.com/fwlink/?linkid=309326)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS13-057**](http://go.microsoft.com/fwlink/?linkid=301528)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.1 Service Pack 1  
(2833949)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2833940)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2844285)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2832411)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2840629)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2832407)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(Windows GDI+)  
(2834886)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2846071)  
(Moderato)  
Internet Explorer 7  
(2846071)  
(Moderato)  
Internet Explorer 8  
(2846071)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Runtime formato Windows Media 9.5  
(wmvdmod.dll)  
(2803821)  
(Critico)  
wmv9vcm.dll (codec)  
(2845142)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.1 Service Pack 1  
(2833941)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2833940)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2844285)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2832411)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2840629)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2832407)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(Windows GDI+)  
(2834886)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2846071)  
(Moderato)  
Internet Explorer 7  
(2846071)  
(Moderato)  
Internet Explorer 8  
(2846071)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Runtime formato Windows Media 9.5  
(wmvdmod.dll)  
(2803821)  
(Critico)  
Runtime formato Windows Media 9.5 x64  
(wmvdmod.dll)  
(2834902)  
(Critico)  
Runtime formato Windows Media 11  
(wmvdmod.dll)  
(2834904)  
(Critico)  
wmv9vcm.dll (codec)  
(2845142)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.1 Service Pack 1  
(2833941)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2833940)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2844285)  
(Importante)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2840629)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(Windows GDI+)  
(2834886)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2846071)  
(Moderato)  
Internet Explorer 7  
(2846071)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
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
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-053**](http://go.microsoft.com/fwlink/?linkid=301423)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
</td>
<td style="border:1px solid black;">
[**MS13-055**](http://go.microsoft.com/fwlink/?linkid=309324)
</td>
<td style="border:1px solid black;">
[**MS13-056**](http://go.microsoft.com/fwlink/?linkid=309326)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS13-057**](http://go.microsoft.com/fwlink/?linkid=301528)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.1 Service Pack 1  
(2833941)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2833947)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2844287)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2832412)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2840629)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2832407)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)  
Microsoft .NET Framework 4.5  
(2835622)  
(Critico)  
Microsoft .NET Framework 4.5  
(2833957)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840642)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(DirectWrite)  
(2835361)  
(Critico)  
Windows Vista Service Pack 2  
(Windows GDI+)  
(2834886)  
(Critico)  
Windows Vista Service Pack 2  
(Journal)  
(2835364)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2846071)  
(Critico)  
Internet Explorer 8  
(2846071)  
(Critico)  
Internet Explorer 9  
(2846071)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 11  
(wmvdecod.dll)  
(2803821)  
(Critico)  
wmv9vcm.dll (codec)  
(2845142)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.1 Service Pack 1  
(2833941)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2833947)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2844287)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2832412)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2840629)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2832407)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)  
Microsoft .NET Framework 4.5  
(2835622)  
(Critico)  
Microsoft .NET Framework 4.5  
(2833957)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840642)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(DirectWrite)  
(2835361)  
(Critico)  
Windows Vista x64 Edition Service Pack 2  
(Windows GDI+)  
(2834886)  
(Critico)  
Windows Vista x64 Edition Service Pack 2  
(Journal)  
(2835364)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2846071)  
(Critico)  
Internet Explorer 8  
(2846071)  
(Critico)  
Internet Explorer 9  
(2846071)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 11  
(wmvdecod.dll)  
(2803821)  
(Critico)  
wmv9vcm.dll (codec)  
(2845142)  
(Critico)
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
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-053**](http://go.microsoft.com/fwlink/?linkid=301423)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
</td>
<td style="border:1px solid black;">
[**MS13-055**](http://go.microsoft.com/fwlink/?linkid=309324)
</td>
<td style="border:1px solid black;">
[**MS13-056**](http://go.microsoft.com/fwlink/?linkid=309326)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS13-057**](http://go.microsoft.com/fwlink/?linkid=301528)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.1 Service Pack 1  
(2833941)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2833947)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2844287)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2832412)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2840629)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2832407)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)  
Microsoft .NET Framework 4.5  
(2835622)  
(Critico)  
Microsoft .NET Framework 4.5  
(2833957)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840642)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(DirectWrite)  
(2835361)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(Windows GDI+)  
(2834886)  
(Critico)  
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(Journal)  
(2835364)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2846071)  
(Moderato)  
Internet Explorer 8  
(2846071)  
(Moderato)  
Internet Explorer 9  
(2846071)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 11\[4\]  
(wmvdecod.dll)  
(2803821)  
(Critico)  
wmv9vcm.dll (codec) \[5\]  
(2845142)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.1 Service Pack 1  
(2833941)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2833947)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2844287)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2832412)  
(Critico)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2840629)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2832407)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)  
Microsoft .NET Framework 4.5  
(2835622)  
(Critico)  
Microsoft .NET Framework 4.5  
(2833957)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840642)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(DirectWrite)  
(2835361)  
(Critico)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(Windows GDI+)  
(2834886)  
(Critico)  
Windows Server 2008 per sistemi x64 Service Pack 2  
(Journal)  
(2835364)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2846071)  
(Moderato)  
Internet Explorer 8  
(2846071)  
(Moderato)  
Internet Explorer 9  
(2846071)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 11\[4\]  
(wmvdecod.dll)  
(2803821)  
(Critico)  
wmv9vcm.dll (codec) \[5\]  
(2845142)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.1 Service Pack 1  
(2833941)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2833947)  
(Critico)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2844287)  
(Importante)  
Microsoft .NET Framework 3.5 Service Pack 1  
(2840629)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(Windows GDI+)  
(2834886)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2846071)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
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
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-053**](http://go.microsoft.com/fwlink/?linkid=301423)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
</td>
<td style="border:1px solid black;">
[**MS13-055**](http://go.microsoft.com/fwlink/?linkid=309324)
</td>
<td style="border:1px solid black;">
[**MS13-056**](http://go.microsoft.com/fwlink/?linkid=309326)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS13-057**](http://go.microsoft.com/fwlink/?linkid=301528)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2832414)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2833946)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2840631)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2844286)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)  
Microsoft .NET Framework 4.5  
(2833957)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840642)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(DirectWrite)  
(2835361)  
(Critico)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(Windows GDI+)  
(2834886)  
(Critico)  
Windows 7 per sistemi a 32 bit Service Pack 1  
(Journal)  
(2835364)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2846071)  
(Critico)  
Internet Explorer 9  
(2846071)  
(Critico)  
Internet Explorer 10  
(2846071)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 12  
(wmvdecod.dll)  
(2803821)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2832414)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2833946)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2840631)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2844286)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)  
Microsoft .NET Framework 4.5  
(2833957)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840642)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(DirectWrite)  
(2835361)  
(Critico)  
Windows 7 per sistemi x64 Service Pack 1  
(Windows GDI+)  
(2834886)  
(Critico)  
Windows 7 per sistemi x64 Service Pack 1  
(Journal)  
(2835364)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2846071)  
(Critico)  
Internet Explorer 9  
(2846071)  
(Critico)  
Internet Explorer 10  
(2846071)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 12  
(wmvdecod.dll)  
(2803821)  
(Critico)
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
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-053**](http://go.microsoft.com/fwlink/?linkid=301423)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
</td>
<td style="border:1px solid black;">
[**MS13-055**](http://go.microsoft.com/fwlink/?linkid=309324)
</td>
<td style="border:1px solid black;">
[**MS13-056**](http://go.microsoft.com/fwlink/?linkid=309326)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS13-057**](http://go.microsoft.com/fwlink/?linkid=301528)
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
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2832414)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2833946)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2840631)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2844286)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)  
Microsoft .NET Framework 4.5  
(2833957)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840642)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(DirectWrite)  
(2835361)  
(Critico)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(Windows GDI+)  
(2834886)  
(Critico)  
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(Journal)  
(2835364)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2846071)  
(Moderato)  
Internet Explorer 9  
(2846071)  
(Moderato)  
Internet Explorer 10  
(2846071)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 12\[4\]  
(wmvdecod.dll)  
(2803821)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2833946)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2840631)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2844286)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(DirectWrite)  
(2835361)  
(Critico)  
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(Windows GDI+)  
(2834886)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2846071)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<th colspan="8">
Windows 8
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-053**](http://go.microsoft.com/fwlink/?linkid=301423)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
</td>
<td style="border:1px solid black;">
[**MS13-055**](http://go.microsoft.com/fwlink/?linkid=309324)
</td>
<td style="border:1px solid black;">
[**MS13-056**](http://go.microsoft.com/fwlink/?linkid=309326)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS13-057**](http://go.microsoft.com/fwlink/?linkid=301528)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;" colspan="2">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2832418)  
(Critico)  
Microsoft .NET Framework 3.5  
(2833959)  
(Critico)  
Microsoft .NET Framework 3.5  
(2840633)  
(Importante)  
Microsoft .NET Framework 3.5  
(2844289)  
(Importante)  
Microsoft .NET Framework 4.5  
(2833958)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840632)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(DirectWrite)  
(2835361)  
(Critico)  
Windows 8 per sistemi a 32 bit  
(Journal)  
(2835364)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2846071)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 12  
(wmvdecod.dll)  
(2803821)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2832418)  
(Critico)  
Microsoft .NET Framework 3.5  
(2833959)  
(Critico)  
Microsoft .NET Framework 3.5  
(2840633)  
(Importante)  
Microsoft .NET Framework 3.5  
(2844289)  
(Importante)  
Microsoft .NET Framework 4.5  
(2833958)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840632)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit  
(DirectWrite)  
(2835361)  
(Critico)  
Windows 8 per sistemi a 64 bit  
(Journal)  
(2835364)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2846071)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 12  
(wmvdecod.dll)  
(2803821)  
(Critico)
</td>
</tr>
<tr>
<th colspan="8">
Windows Server 2012
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-053**](http://go.microsoft.com/fwlink/?linkid=301423)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
</td>
<td style="border:1px solid black;">
[**MS13-055**](http://go.microsoft.com/fwlink/?linkid=309324)
</td>
<td style="border:1px solid black;">
[**MS13-056**](http://go.microsoft.com/fwlink/?linkid=309326)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS13-057**](http://go.microsoft.com/fwlink/?linkid=301528)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
<td style="border:1px solid black;" colspan="2">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2832418)  
(Critico)  
Microsoft .NET Framework 3.5  
(2833959)  
(Critico)  
Microsoft .NET Framework 3.5  
(2840633)  
(Importante)  
Microsoft .NET Framework 3.5  
(2844289)  
(Importante)  
Microsoft .NET Framework 4.5  
(2833958)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840632)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(DirectWrite)  
(2835361)  
(Critico)  
Windows Server 2012  
(Journal)  
(2835364)  
(Critico)

</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2846071)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2845187)  
(Critico)
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 12\[4\]  
(wmvdecod.dll)  
(2803821)  
(Critico)
</td>
</tr>
<tr>
<th colspan="8">
Windows RT
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-053**](http://go.microsoft.com/fwlink/?linkid=301423)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
</td>
<td style="border:1px solid black;">
[**MS13-055**](http://go.microsoft.com/fwlink/?linkid=309324)
</td>
<td style="border:1px solid black;">
[**MS13-056**](http://go.microsoft.com/fwlink/?linkid=309326)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS13-057**](http://go.microsoft.com/fwlink/?linkid=301528)
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
**Nessuno**
</td>
<td style="border:1px solid black;" colspan="2">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows RT
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 4.5  
(2833958)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840632)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows RT  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows RT  
(DirectWrite)  
(2835361)  
(Critico)
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2846071)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
Windows Media Player 12  
(wmvdecod.dll)  
(2803821)  
(Critico)
</td>
</tr>
<tr>
<th colspan="8">
Opzione di installazione Server Core
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-053**](http://go.microsoft.com/fwlink/?linkid=301423)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
</td>
<td style="border:1px solid black;">
[**MS13-055**](http://go.microsoft.com/fwlink/?linkid=309324)
</td>
<td style="border:1px solid black;">
[**MS13-056**](http://go.microsoft.com/fwlink/?linkid=309326)
</td>
<td style="border:1px solid black;" colspan="2">
[**MS13-057**](http://go.microsoft.com/fwlink/?linkid=301528)
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
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;" colspan="2">
**Nessuno**
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
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(Windows GDI+)  
(2834886)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
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
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(Windows GDI+)  
(2834886)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2833946)  
(Critico)  
Microsoft .NET Framework 3.5.1  
(2840631)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2844286)  
(Importante)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2835393)  
(Critico)  
Microsoft .NET Framework 4<sup>[1]</sup>
(2840628)  
(Importante)  
Microsoft .NET Framework 4.5  
(2833957)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840642)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(Windows GDI+)  
(2834886)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2832418)  
(Critico)  
Microsoft .NET Framework 3.5  
(2833959)  
(Critico)  
Microsoft .NET Framework 3.5  
(2840633)  
(Importante)  
Microsoft .NET Framework 3.5  
(2844289)  
(Importante)  
Microsoft .NET Framework 4.5  
(2833958)  
(Critico)  
Microsoft .NET Framework 4.5  
(2840632)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2850851)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(DirectWrite)  
(2835361)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;" colspan="2">
Non applicabile
</td>
</tr>
</table>
 
**Note per MS13-052**

<sup>[1]</sup>**.NET Framework 4 e .NET Framework 4 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4 e .NET Framework 4 Client Profile. .NET Framework 4 Client Profile è un sottoinsieme di .NET Framework 4. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4 sia .NET Framework 4 Client Profile. Per ulteriori informazioni, vedere l'articolo di MSDN, [Installazione di .NET Framework](http://msdn.microsoft.com/library/5a4x27ek).

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota per** **MS13-053** **e** **MS13-055**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota** **per** **MS13-054**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Noteper MS13-057**

<sup>[1]</sup>Questo aggiornamento viene offerto solo sui sistemi che sono stati aggiornati a Runtime formato Windows Media 11 o Windows Media Player 11.
<sup>[2]</sup>Questo aggiornamento viene offerto solo sui sistemi con Runtime formato Windows Media 9.5 NL in esecuzione.
<sup>[3]</sup>Questo aggiornamento viene offerto solo sui sistemi con Runtime formato Windows Media 9.5 L in esecuzione.
\[4\]Questo aggiornamento viene offerto solo se è attivata la funzionalità Desktop Experience opzionale.
\[5\]Questo aggiornamento viene offerto solo se è attivata la funzionalità Desktop Experience opzionale ed è presente il codec wmv9vcm.dll. Consultare il bollettino per ulteriori informazioni.

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Software Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
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
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3  
(2817480)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3  
(2687309)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)  
(2687276)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)  
(2687276)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS13-054**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr>
<th colspan="3">
Microsoft Visual Studio
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
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
Microsoft Visual Studio .NET 2003 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft Visual Studio .NET 2003 Service Pack 1<sup>[1]</sup>
(2856545)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Silverlight
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Silverlight 5
</td>
<td style="border:1px solid black;">
[**MS13-052**](http://go.microsoft.com/fwlink/?linkid=299844)
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
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
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
Microsoft Silverlight 5 installato in Mac  
(2847559)  
(Critico)  
Microsoft Silverlight 5 Developer Runtime installato in Mac  
(2847559)  
(Critico)  
Microsoft Silverlight 5 installato nelle versioni a 32 bit dei client Microsoft Windows  
(2847559)  
(Critico)  
Microsoft Silverlight 5 installato nelle versioni x64 dei client Microsoft Windows  
(2847559)  
(Critico)  
Microsoft Silverlight 5 Developer Runtime installato in tutte le versioni supportate dei client Microsoft Windows  
(2847559)  
(Critico)  
Microsoft Silverlight 5 installato nelle versioni a 32 bit dei server Microsoft Windows  
(2847559)  
(Critico)  
Microsoft Silverlight 5 installato nelle versioni x64 dei server Microsoft Windows  
(2847559)  
(Critico)  
Microsoft Silverlight 5 Developer Runtime installato in tutte le versioni supportate dei server Microsoft Windows  
(2847559)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Nota per MS13-052**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Noteper MS13-054**

<sup>[1]</sup>Questo aggiornamento è disponibile soltanto nell'Area download Microsoft.

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Software e piattaforme delle comunicazioni Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Lync
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-054**](http://go.microsoft.com/fwlink/?linkid=301531)
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
Microsoft Lync 2010 (32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 (32 bit)  
(2843160)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Lync 2010 (64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 (64 bit)  
(2843160)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee  
(installazione a livello utente)
</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee  
(installazione a livello utente)  
(2843162)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee  
(installazione a livello amministratore)
</td>
<td style="border:1px solid black;">
Microsoft Lync 2010 Attendee  
(installazione a livello amministratore)  
(2843163)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync 2013 (32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Lync 2013 (32 bit)  
(2817465)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Lync Basic 2013 (32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Lync Basic 2013 (32 bit)  
(2817465)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync 2013 (64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Lync 2013 (64 bit)  
(2817465)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Lync Basic 2013 (64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Lync Basic 2013 (64 bit)  
(2817465)  
(Critico)
</td>
</tr>
</table>
 
**Nota per MS13-054**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software

#### Software di protezione Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Software antispyware
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-058**](http://go.microsoft.com/fwlink/?linkid=308992)
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
Windows Defender per Windows 7 (x86)
</td>
<td style="border:1px solid black;">
Windows Defender per Windows 7 (x86)  
(2847927)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Defender per Windows 7 (x64)
</td>
<td style="border:1px solid black;">
Windows Defender per Windows 7 (x64)  
(2847927)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Defender installato su Windows Server 2008 R2 (x64)
</td>
<td style="border:1px solid black;">
Windows Defender installato su Windows Server 2008 R2 (x64)  
(2847927)  
(Importante)
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security TechCenter](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. I clienti possono visitare [Microsoft Safety & Security Center](http://www.microsoft.com/italy/athome/security/default.mspx), dove queste informazioni sono disponibili anche facendo clic su "Aggiornamenti per la protezione".

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

**MS13-052**

-   Ling Chuan Lee e Lee Yee Chan di [F-13 Laboratory](http://www.f13-labs.net/) per aver segnalato la vulnerabilità legata all'analisi dei caratteri TrueType (CVE-2013-3129)
-   Alon Fliess per aver segnalato la vulnerabilità legata alla violazione dell'accesso degli array (CVE-2013-3131)
-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata all'elusione della riflessione delegata (CVE-2013-3132)
-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata all'immissione anonima di metodo (CVE-2013-3133)
-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata alla serializzazione di oggetti delegati (CVE-2013-3171)
-   Vitaliy Toropov per aver segnalato la vulnerabilità del puntatore NULL (CVE-2013-3178)

**MS13-053**

-   Jon Butler e Nils di MWR Labs, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata all'allocazione della memoria in Win32k (CVE-2013-1300)
-   Alexander Chizhov di [Dr.Web](http://drweb.com/) per aver segnalato la vulnerabilità legata alla risoluzione del riferimento in Win32k (CVE-2013-1340)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata alla gestione di Windows in Win32k (CVE-2013-1345)
-   Ling Chuan Lee e Lee Yee Chan di [F13 Laboratory](http://www.f13-labs.net/) per aver segnalato la vulnerabilità legata all'analisi dei caratteri TrueType (CVE-2013-3129)
-   Yinliang di [Tencent PC Manager](http://guanjia.qq.com) per aver segnalato la vulnerabilità legata all'intercettazione di informazioni personali in Win32k (CVE-2013-3167)
-   [Mateusz "j00ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc](http://www.google.com/) per aver segnalato la vulnerabilità legata al sovraccarico del buffer in Win32k (CVE-2013-3172)
-   Wen Yujie e Guo Pengfei di [Qihoo 360 Security Center](http://www.360.cn/) per aver segnalato la vulnerabilità legata al sovraccarico del buffer in Win32k (CVE-2013-3173)

**MS13-054**

-   Ling Chuan Lee e Lee Yee Chan di [F13 Laboratory](http://www.f13-labs.net/) per aver segnalato la vulnerabilità legata all'analisi dei caratteri TrueType (CVE-2013-3129)

**MS13-055**

-   Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3115)
-   SkyLined, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3143)
-   Simon Zuckerbraun, che collabora con [Zero Day Initiative](http://www.hpenterprisesecurity.com/products) di [HP](http://www.zerodayinitiative.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3144)
-   Toan Pham Van, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3145)
-   Toan Pham Van, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3146)
-   [Aniway.Anyway@gmail.com](mailto:aniway.anyway@gmail.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3147)
-   Bluesea, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria (CVE-2013-3148)
-   Bluesea, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria (CVE-2013-3149)
-   [Omair](http://krash.in/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria (CVE-2013-3150)
-   Toan Pham Van, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3151)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3152)
-   e6af8de8b1d4b2b6d5ba2610cbf9cd38, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria (CVE-2013-3153)
-   Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3161)
-   Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3162)
-   Jose Antonio Vazquez Gonzalez, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3163)
-   Scott Bell di [Security-Assessment.com](http://www.security-assessment.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3164)
-   Masato Kinugawa per aver segnalato la vulnerabilità legata alla codifica del carattere Shift JIS (CVE-2013-3166)
-   Mark Yason di IBM X-Force per aver collaborato con noi alle modifiche al sistema di difesa contenute in questo bollettino (CVE-2013-4015)

**MS13-056**

-   Andrés Gómez Ramírez per aver segnalato la vulnerabilità legata alla sovrascrittura della memoria arbitraria in DirectShow - CVE-2013-3174

**MS13-057**

-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata all'esecuzione di codice in modalità remota nel decoder video WMV (CVE-2013-3127)

**MS13-058**

-   Alton Blom di [Reserve Bank of Australia](http://www.rba.gov.au/) per aver segnalato la vulnerabilità legata a un nome percorso errato in Windows Defender per Microsoft Windows 7 (CVE-2013-3154)

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (9 luglio 2013): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (9 luglio 2013): Per MS13-055, è stata rivista la Valutazione dell'Exploitability dell'**Exploitability Index** per CVE-2013-3163. Microsoft è a conoscenza di attacchi mirati che tentano sfruttare questa vulnerabilità attraverso Internet Explorer 8. La modifica è esclusivamente informativa.
-   V2.0 (13 agosto 2013): Per MS13-052, bollettino rivisto per rilasciare gli aggiornamenti 2840628, 2840632, 2840642, 2844285, 2844286, 2844287 e 2844289. Per MS13-057, bollettino rivisto per rilasciare l'aggiornamento 2803821 per Windows 7 e Windows 2008 R2. I clienti dovrebbero installare gli aggiornamenti rilasciati pertinenti ai propri sistemi. Vedere i rispettivi bollettini per i dettagli.
-   Versione 3.0 (27 agosto 2013): Bollettino per MS13-057 rivisto per rilasciare di nuovo l'aggiornamento 2803821 per la protezione di Windows XP, Windows Server 2003, Windows Vista e Windows Server 2008; l'aggiornamento 2834902 per la protezione di Windows XP e Windows Server 2003; l'aggiornamento 2834903 per la protezione di Windows XP; l'aggiornamento 2834904 per la protezione di Windows XP e Windows Server 2003 e l'aggiornamento 2834905 per la protezione di Windows XP. I clienti di Windows XP, Windows Server 2003, Windows Vista e Windows Server 2008 dovrebbero installare le nuove versioni degli aggiornamenti. Per ulteriori informazioni, consultare il bollettino.

*Built at 2014-04-18T01:50:00Z-07:00*
