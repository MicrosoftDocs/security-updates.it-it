---
TOCTitle: 'MS13-NOV'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Novembre 2013'
ms:assetid: 'ms13-nov'
ms:contentKeyID: 61240087
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms13-nov(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Novembre 2013
==================================================================

Data di pubblicazione: martedì 12 novembre 2013

**Versione:** 1.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a novembre 2013.

Con il rilascio dei bollettini sulla sicurezza di novembre 2013, questo riepilogo sostituisce la notifica anticipata sul rilascio pubblicata originariamente in data 7 novembre 2013. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 13 novembre 2013 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di novembre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032557383&culture=en-us).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2888505)</strong><br />
<br />
Questo aggiornamento per la protezione risolve dieci vulnerabilità in Internet Explorer segnalate privatamente. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando la più grave di tali vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325390">MS13-089</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nell'interfaccia GDI (Graphics Device Interface) di Windows può consentire l'esecuzione di codice in modalità remota (2876331)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza o apre un file di Windows Write appositamente predisposto in WordPad. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329834">MS13-090</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione dei kill bit ActiveX (2900986)</strong><br />
<br />
Questo aggiornamento per la protezione affronta una vulnerabilità che è stata segnalata privatamente. La vulnerabilità è stata riscontrata nel controllo ActiveX InformationCardSigninHelper Class. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer, utilizzando l'istanza del controllo ActiveX. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325392">MS13-091</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Office possono consentire l'esecuzione di codice in modalità remota (2885093)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità segnalate privatamente<strong></strong>in Microsoft Office. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un documento WordPerfect appositamente predisposto viene aperto in una versione interessata del software Microsoft Office. Sfruttando le vulnerabilità più gravi, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324692">MS13-092</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Hyper-V può consentire l'acquisizione di privilegi più elevati (2893986)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato invia un parametro di funzione appositamente predisposto in un'hypercall da una macchina virtuale esistente in esecuzione sull'hypervisor. La vulnerabilità può anche consentire attacchi di tipo Denial of Service sull'host Hyper-V se l'utente malintenzionato invia un parametro di funzione appositamente predisposto in un'hypercall da una macchina virtuale esistente in esecuzione sull'hypervisor.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325391">MS13-093</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nel driver di funzioni ausiliario di Windows può consentire l'intercettazione di informazioni personali (2875783)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'intercettazione di informazioni personali se un utente malintenzionato accede a un sistema interessato come utente locale ed esegue un'applicazione appositamente predisposta sul sistema progettato per concedere l'accesso a informazioni da un account con privilegi più elevati. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324873">MS13-094</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Outlook può consentire l'intercettazione di informazioni personali (2894514)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft Outlook. La vulnerabilità può consentire l'intercettazione di informazioni personali se un utente apre o visualizza in anteprima un messaggio di posta elettronica appositamente predisposto tramite un'edizione interessata di Microsoft Outlook. Un utente malintenzionato in grado di sfruttare questa vulnerabilità può venire a conoscenza di informazioni di sistema, quali indirizzo IP e porte TCP aperte, dal sistema di destinazione e altri sistemi che condividono la rete con esso.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320632">MS13-095</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità</strong> <strong>legata alle firme digitali può consentire attacchi di tipo Denial of Service (2868626)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire attacchi di tipo Denial of Service quando un servizio Web interessato elabora un certificato X.509 appositamente predisposto.</td>
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3871">CVE-2013-3871</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni personali in Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3908">CVE-2013-3908</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni personali in Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3909">CVE-2013-3909</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3910">CVE-2013-3910</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3911">CVE-2013-3911</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3912">CVE-2013-3912</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3914">CVE-2013-3914</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3915">CVE-2013-3915</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3916">CVE-2013-3916</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325357">MS13-088</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3917">CVE-2013-3917</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325390">MS13-089</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow di valori integer nell'interfaccia GDI (Graphics Device Interface)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3940">CVE-2013-3940</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=329834">MS13-090</a></td>
<td style="border:1px solid black;">Vulnerabilità di InformationCardSigninHelper</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3918">CVE-2013-3918</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Microsoft è a conoscenza di attacchi mirati limitati che tentano di sfruttare questa vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325392">MS13-091</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria nel formato file WPD</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0082">CVE-2013-0082</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325392">MS13-091</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla sovrascrittura del buffer dello stack di Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1324">CVE-2013-1324</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325392">MS13-091</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla sovrascrittura degli heap in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1325">CVE-2013-1325</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324692">MS13-092</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento degli indirizzi</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3898">CVE-2013-3898</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=325391">MS13-093</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni personali nel driver di funzioni ausiliario (ADF)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3887">CVE-2013-3887</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=324873">MS13-094</a></td>
<td style="border:1px solid black;">Vulnerabilità S/MIME AIA</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3905">CVE-2013-3905</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.<br />
<br />
Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=320632">MS13-095</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alle firme digitali</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-3869">CVE-2013-3869</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.</td>
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
[**MS13-088**](http://go.microsoft.com/fwlink/?linkid=325357)
</td>
<td style="border:1px solid black;">
[**MS13-089**](http://go.microsoft.com/fwlink/?linkid=325390)
</td>
<td style="border:1px solid black;">
[**MS13-090**](http://go.microsoft.com/fwlink/?linkid=329834)
</td>
<td style="border:1px solid black;">
[**MS13-092**](http://go.microsoft.com/fwlink/?linkid=324692)
</td>
<td style="border:1px solid black;">
[**MS13-093**](http://go.microsoft.com/fwlink/?linkid=325391)
</td>
<td style="border:1px solid black;">
[**MS13-095**](http://go.microsoft.com/fwlink/?linkid=320632)
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
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2888505)  
(Critico)  
Internet Explorer 7  
(2888505)  
(Critico)  
Internet Explorer 8  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2900986)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2868626)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2888505)  
(Critico)  
Internet Explorer 7  
(2888505)  
(Critico)  
Internet Explorer 8  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2900986)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2868626)  
(Importante)
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-088**](http://go.microsoft.com/fwlink/?linkid=325357)
</td>
<td style="border:1px solid black;">
[**MS13-089**](http://go.microsoft.com/fwlink/?linkid=325390)
</td>
<td style="border:1px solid black;">
[**MS13-090**](http://go.microsoft.com/fwlink/?linkid=329834)
</td>
<td style="border:1px solid black;">
[**MS13-092**](http://go.microsoft.com/fwlink/?linkid=324692)
</td>
<td style="border:1px solid black;">
[**MS13-093**](http://go.microsoft.com/fwlink/?linkid=325391)
</td>
<td style="border:1px solid black;">
[**MS13-095**](http://go.microsoft.com/fwlink/?linkid=320632)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2888505)  
(Importante)  
Internet Explorer 7  
(2888505)  
(Importante)  
Internet Explorer 8  
(2888505)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2900986)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2868626)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2888505)  
(Importante)  
Internet Explorer 7  
(2888505)  
(Importante)  
Internet Explorer 8  
(2888505)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2900986)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2868626)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2888505)  
(Importante)  
Internet Explorer 7  
(2888505)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2900986)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2868626)  
(Importante)
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
[**MS13-088**](http://go.microsoft.com/fwlink/?linkid=325357)
</td>
<td style="border:1px solid black;">
[**MS13-089**](http://go.microsoft.com/fwlink/?linkid=325390)
</td>
<td style="border:1px solid black;">
[**MS13-090**](http://go.microsoft.com/fwlink/?linkid=329834)
</td>
<td style="border:1px solid black;">
[**MS13-092**](http://go.microsoft.com/fwlink/?linkid=324692)
</td>
<td style="border:1px solid black;">
[**MS13-093**](http://go.microsoft.com/fwlink/?linkid=325391)
</td>
<td style="border:1px solid black;">
[**MS13-095**](http://go.microsoft.com/fwlink/?linkid=320632)
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
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2888505)  
(Critico)  
Internet Explorer 8  
(2888505)  
(Critico)  
Internet Explorer 9  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2900986)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2868626)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2888505)  
(Critico)  
Internet Explorer 8  
(2888505)  
(Critico)  
Internet Explorer 9  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2900986)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2868626)  
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
[**MS13-088**](http://go.microsoft.com/fwlink/?linkid=325357)
</td>
<td style="border:1px solid black;">
[**MS13-089**](http://go.microsoft.com/fwlink/?linkid=325390)
</td>
<td style="border:1px solid black;">
[**MS13-090**](http://go.microsoft.com/fwlink/?linkid=329834)
</td>
<td style="border:1px solid black;">
[**MS13-092**](http://go.microsoft.com/fwlink/?linkid=324692)
</td>
<td style="border:1px solid black;">
[**MS13-093**](http://go.microsoft.com/fwlink/?linkid=325391)
</td>
<td style="border:1px solid black;">
[**MS13-095**](http://go.microsoft.com/fwlink/?linkid=320632)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2888505)  
(Importante)  
Internet Explorer 8  
(2888505)  
(Importante)  
Internet Explorer 9  
(2888505)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2900986)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2868626)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2888505)  
(Importante)  
Internet Explorer 8  
(2888505)  
(Importante)  
Internet Explorer 9  
(2888505)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2900986)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2868626)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2888505)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2900986)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2868626)  
(Importante)
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
[**MS13-088**](http://go.microsoft.com/fwlink/?linkid=325357)
</td>
<td style="border:1px solid black;">
[**MS13-089**](http://go.microsoft.com/fwlink/?linkid=325390)
</td>
<td style="border:1px solid black;">
[**MS13-090**](http://go.microsoft.com/fwlink/?linkid=329834)
</td>
<td style="border:1px solid black;">
[**MS13-092**](http://go.microsoft.com/fwlink/?linkid=324692)
</td>
<td style="border:1px solid black;">
[**MS13-093**](http://go.microsoft.com/fwlink/?linkid=325391)
</td>
<td style="border:1px solid black;">
[**MS13-095**](http://go.microsoft.com/fwlink/?linkid=320632)
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
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2888505)  
(Critico)  
Internet Explorer 9  
(2888505)  
(Critico)  
Internet Explorer 10  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2900986)  
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
(2868626)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2888505)  
(Critico)  
Internet Explorer 9  
(2888505)  
(Critico)  
Internet Explorer 10  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2900986)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2868626)  
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
[**MS13-088**](http://go.microsoft.com/fwlink/?linkid=325357)
</td>
<td style="border:1px solid black;">
[**MS13-089**](http://go.microsoft.com/fwlink/?linkid=325390)
</td>
<td style="border:1px solid black;">
[**MS13-090**](http://go.microsoft.com/fwlink/?linkid=329834)
</td>
<td style="border:1px solid black;">
[**MS13-092**](http://go.microsoft.com/fwlink/?linkid=324692)
</td>
<td style="border:1px solid black;">
[**MS13-093**](http://go.microsoft.com/fwlink/?linkid=325391)
</td>
<td style="border:1px solid black;">
[**MS13-095**](http://go.microsoft.com/fwlink/?linkid=320632)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2888505)  
(Importante)  
Internet Explorer 9  
(2888505)  
(Importante)  
Internet Explorer 10  
(2888505)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2900986)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2868626)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2888505)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2900986)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2868626)  
(Importante)
</td>
</tr>
<tr>
<th colspan="7">
Windows 8 e Windows 8.1
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-088**](http://go.microsoft.com/fwlink/?linkid=325357)
</td>
<td style="border:1px solid black;">
[**MS13-089**](http://go.microsoft.com/fwlink/?linkid=325390)
</td>
<td style="border:1px solid black;">
[**MS13-090**](http://go.microsoft.com/fwlink/?linkid=329834)
</td>
<td style="border:1px solid black;">
[**MS13-092**](http://go.microsoft.com/fwlink/?linkid=324692)
</td>
<td style="border:1px solid black;">
[**MS13-093**](http://go.microsoft.com/fwlink/?linkid=325391)
</td>
<td style="border:1px solid black;">
[**MS13-095**](http://go.microsoft.com/fwlink/?linkid=320632)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2900986)  
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
(2868626)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 8 per sistemi x64
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(2900986)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(solo edizioni Pro ed Enterprise)  
(2893986)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(2868626)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(2900986)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(2868626)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64
</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(2900986)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(2868626)  
(Importante)
</td>
</tr>
<tr>
<th colspan="7">
Windows Server 2012 e Windows Server 2012 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-088**](http://go.microsoft.com/fwlink/?linkid=325357)
</td>
<td style="border:1px solid black;">
[**MS13-089**](http://go.microsoft.com/fwlink/?linkid=325390)
</td>
<td style="border:1px solid black;">
[**MS13-090**](http://go.microsoft.com/fwlink/?linkid=329834)
</td>
<td style="border:1px solid black;">
[**MS13-092**](http://go.microsoft.com/fwlink/?linkid=324692)
</td>
<td style="border:1px solid black;">
[**MS13-093**](http://go.microsoft.com/fwlink/?linkid=325391)
</td>
<td style="border:1px solid black;">
[**MS13-095**](http://go.microsoft.com/fwlink/?linkid=320632)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2888505)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2900986)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(edizioni Standard e Datacenter, solo Hyper-V Server 2012)  
(2893986)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2868626)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2012 R2
</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2888505)  
(Moderato)
</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(2900986)  
(Moderato)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(2868626)  
(Importante)
</td>
</tr>
<tr>
<th colspan="7">
Windows RT e Windows RT 8.1
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-088**](http://go.microsoft.com/fwlink/?linkid=325357)
</td>
<td style="border:1px solid black;">
[**MS13-089**](http://go.microsoft.com/fwlink/?linkid=325390)
</td>
<td style="border:1px solid black;">
[**MS13-090**](http://go.microsoft.com/fwlink/?linkid=329834)
</td>
<td style="border:1px solid black;">
[**MS13-092**](http://go.microsoft.com/fwlink/?linkid=324692)
</td>
<td style="border:1px solid black;">
[**MS13-093**](http://go.microsoft.com/fwlink/?linkid=325391)
</td>
<td style="border:1px solid black;">
[**MS13-095**](http://go.microsoft.com/fwlink/?linkid=320632)
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
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows RT
</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows RT  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows RT  
(2900986)  
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
(2868626)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows RT 8.1
</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2888505)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows RT 8.1  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Windows RT 8.1  
(2900986)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows RT 8.1  
(2868626)  
(Importante)
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
[**MS13-088**](http://go.microsoft.com/fwlink/?linkid=325357)
</td>
<td style="border:1px solid black;">
[**MS13-089**](http://go.microsoft.com/fwlink/?linkid=325390)
</td>
<td style="border:1px solid black;">
[**MS13-090**](http://go.microsoft.com/fwlink/?linkid=329834)
</td>
<td style="border:1px solid black;">
[**MS13-092**](http://go.microsoft.com/fwlink/?linkid=324692)
</td>
<td style="border:1px solid black;">
[**MS13-093**](http://go.microsoft.com/fwlink/?linkid=325391)
</td>
<td style="border:1px solid black;">
[**MS13-095**](http://go.microsoft.com/fwlink/?linkid=320632)
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
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
(2876331)  
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
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2868626)  
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
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2868626)  
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
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2868626)  
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
Windows Server 2012 (installazione Server Core)  
(2876331)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2893986)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2875783)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2868626)  
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
Windows Server 2012 R2 (installazione Server Core)  
(2876331)  
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
Windows Server 2012 R2 (installazione Server Core)  
(2868626)  
(Importante)
</td>
</tr>
</table>
 

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
[**MS13-091**](http://go.microsoft.com/fwlink/?linkid=325392)
</td>
<td style="border:1px solid black;">
[**MS13-094**](http://go.microsoft.com/fwlink/?linkid=324873)
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
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3  
(convertitori di formati file)  
(2760494)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
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
[**MS13-091**](http://go.microsoft.com/fwlink/?linkid=325392)
</td>
<td style="border:1px solid black;">
[**MS13-094**](http://go.microsoft.com/fwlink/?linkid=324873)
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
Microsoft Office 2007 Service Pack 3  
(convertitori di formati file)  
(2760415)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2007 Service Pack 3  
(2825644)  
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
[**MS13-091**](http://go.microsoft.com/fwlink/?linkid=325392)
</td>
<td style="border:1px solid black;">
[**MS13-094**](http://go.microsoft.com/fwlink/?linkid=324873)
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
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)  
(convertitori di formati file)  
(2553284)  
(Importante)  
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)  
(strumenti di correzione)  
(2760781)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2010 Service Pack 1 (edizioni a 32 bit)  
(2837597)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)  
(convertitori di formati file)  
(2553284)  
(Nessuno livello di gravità)  
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)  
(strumenti di correzione)  
(2760781)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2010 Service Pack 2 (edizioni a 32 bit)  
(2837597)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)  
(convertitori di formati file)  
(2553284)  
(Importante)  
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)  
(strumenti di correzione)  
(2760781)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2010 Service Pack 1 (edizioni a 64 bit)  
(2837597)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)  
(convertitori di formati file)  
(2553284)  
(Nessuno livello di gravità)  
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)  
(strumenti di correzione)  
(2760781)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2010 Service Pack 2 (edizioni a 64 bit)  
(2837597)  
(Importante)
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
[**MS13-091**](http://go.microsoft.com/fwlink/?linkid=325392)
</td>
<td style="border:1px solid black;">
[**MS13-094**](http://go.microsoft.com/fwlink/?linkid=324873)
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
Microsoft Office 2013 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 32 bit)  
(convertitori di formati file)  
(2768005)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2013 (edizioni a 32 bit)  
(2837618)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)  
(convertitori di formati file)  
(2768005)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2013 (edizioni a 64 bit)  
(2837618)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 RT
</td>
<td style="border:1px solid black;">
Microsoft Office 2013 RT  
(convertitori di formati file)  
(2768005)  
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Outlook 2013 RT  
(2837618)  
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

**MS13-088**

-   Simon Zuckerbraun, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3871)
-   Masato Kinugawa per aver segnalato la vulnerabilità legata all'intercettazione di informazioni personali in Internet Explorer (CVE-2013-3908)
-   Sergey Markov per aver segnalato la vulnerabilità legata all'intercettazione di informazioni personali in Internet Explorer (CVE-2013-3909)
-   Peter 'corelanc0d3r' Van Eeckhoutte di [Corelan](http://www.corelangcv.com/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3910)
-   Stephen Fewer di [Harmony Security](http://www.harmonysecurity.com/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3911)
-   lokihardt@ASRT, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria (CVE-2013-3912)
-   Un ricercatore anonimo, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3914)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3915)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3916)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3917)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2013-3917)

**MS13-089**

-   Hossein Lotfi di [Secunia Research](http://secunia.com/) per aver segnalato la vulnerabilità legata all'overflow dei valori integer nell'interfaccia GDI (CVE-2013-3940)

**MS13-090**

-   ucq e Daiki Fukumori di [Cyber Defense Institute, Inc.](http://www.cyberdefense.jp/) per aver segnalato la vulnerabilità di InformationCardSigninHelper (CVE-2013-3918)
-   [iSIGHT Partners](http://www.isightpartners.com/) per aver collaborato con noi allo studio della vulnerabilità di InformationCardSigninHelper (CVE-2013-3918)
-   Dan Caselden e Xiaobo Chen di [FireEye](http://www.fireeye.com/) per aver collaborato con noi allo studio della vulnerabilità di InformationCardSigninHelper (CVE-2013-3918)

**MS13-091**

-   Merliton per aver segnalato la vulnerabilità legata al danneggiamento della memoria nel formato file WPD (CVE-2013-0082)
-   Will Dormann di [CERT/CC](http://www.cert.org/) per aver segnalato la vulnerabilità legata alla sovrascrittura del buffer dello stack di Word (CVE-2013-1324)
-   Will Dormann di [CERT/CC](http://www.cert.org/) per aver segnalato la vulnerabilità legata alla sovrascrittura degli heap in Word (CVE-2013-1325)

**MS13-092**

-   thinktecture ([www.thinktecture.com](http://www.thinktecture.com)) &amp ERNW ([www.ernw.de](http://www.ernw.de); Felix Wilhelm) per conto di Bundesamt für Sicherheit in der Informationstechnik (BSI, German Federal Office for Information Security) per aver segnalato la vulnerabilità legata al danneggiamento degli indirizzi (CVE-2013-3898)

**MS13-094**

-   Alexander Klink di [n.runs professionals GmbH](https://www.nruns.com/) per aver segnalato la vulnerabilità S/MIME AIA (CVE-2013-3905)

**MS13-095**

-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata alle firme digitali (CVE-2013-3869)

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (12 novembre 2013): Pubblicazione del riepilogo dei bollettini.

*Built at 2014-04-18T01:50:00Z-07:00*
