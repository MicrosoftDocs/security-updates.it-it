---
TOCTitle: 'MS14-JAN'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Gennaio 2014'
ms:assetid: 'ms14-jan'
ms:contentKeyID: 61597941
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms14-jan(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Gennaio 2014
=================================================================

Data di pubblicazione: martedì 14 gennaio 2014

**Versione:** 1.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a gennaio 2014.

Con il rilascio dei bollettini sulla sicurezza di gennaio 2014, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 9 gennaio 2014. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 15 gennaio 2014 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di gennaio](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032572876&culture=en-us).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=386452">MS14-001</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Word e nelle applicazioni Web di Office possono consentire l'esecuzione di codice in modalità remota (2916605)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve tre vulnerabilità segnalate privatamente<strong></strong>in Microsoft Office. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un file appositamente predisposto è aperto in una versione interessata di Microsoft Word o di altro software Microsoft Office interessato. Sfruttando tale vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Software dei server Microsoft</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=389579">MS14-002</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità del kernel</strong> <strong>di Windows</strong> <strong>può consentire l'acquisizione di privilegi più elevati (2914368)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft Windows. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede ad un sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=389578">MS14-003</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nei driver in modalità kernel di Windows può consentire l'acquisizione di privilegi più elevati (2913602)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente accede a un sistema ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=386402">MS14-004</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Dynamics AX può consentire attacchi di tipo Denial of Service (2880826)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Dynamics AX. La vulnerabilità può consentire un attacco di tipo Denial of Service se un utente malintenzionato invia dati appositamente predisposti a un'istanza AOS (Application Object Server) di Microsoft Dynamics AX interessata. Sfruttando questa vulnerabilità, un utente malintenzionato può impedire all'istanza AOS di destinazione di rispondere alle richieste del client.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Dynamics AX</td>
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=386452">MS14-001</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0258">CVE-2014-0258</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=386452">MS14-001</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0259">CVE-2014-0259</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=386452">MS14-001</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0260">CVE-2014-0260</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=389579">MS14-002</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al componente NDProxy del kernel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-5065">CVE-2013-5065</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Microsoft è a conoscenza di attacchi mirati limitati che tentano di sfruttare questa vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=389578">MS14-003</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla gestione di finestre Win32K</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0262">CVE-2014-0262</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=386402">MS14-004</a></td>
<td style="border:1px solid black;">Vulnerabilità legata ad attacchi di tipo Denial of Service nel filtro</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0261">CVE-2014-0261</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Permanente</td>
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
<th colspan="3">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-002**](http://go.microsoft.com/fwlink/?linkid=389579)
</td>
<td style="border:1px solid black;">
[**MS14-003**](http://go.microsoft.com/fwlink/?linkid=389578)
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
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2914368)  
(Importante)
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
Windows XP Professional x64 Edition Service Pack 2  
(2914368)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-002**](http://go.microsoft.com/fwlink/?linkid=389579)
</td>
<td style="border:1px solid black;">
[**MS14-003**](http://go.microsoft.com/fwlink/?linkid=389578)
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
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2914368)  
(Importante)
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
Windows Server 2003 x64 Edition Service Pack 2  
(2914368)  
(Importante)
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
Windows Server 2003 con SP2 per sistemi Itanium  
(2914368)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-002**](http://go.microsoft.com/fwlink/?linkid=389579)
</td>
<td style="border:1px solid black;">
[**MS14-003**](http://go.microsoft.com/fwlink/?linkid=389578)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-002**](http://go.microsoft.com/fwlink/?linkid=389579)
</td>
<td style="border:1px solid black;">
[**MS14-003**](http://go.microsoft.com/fwlink/?linkid=389578)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
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
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-002**](http://go.microsoft.com/fwlink/?linkid=389579)
</td>
<td style="border:1px solid black;">
[**MS14-003**](http://go.microsoft.com/fwlink/?linkid=389578)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2913602)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2913602)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-002**](http://go.microsoft.com/fwlink/?linkid=389579)
</td>
<td style="border:1px solid black;">
[**MS14-003**](http://go.microsoft.com/fwlink/?linkid=389578)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2913602)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2913602)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows 8 e Windows 8.1
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-002**](http://go.microsoft.com/fwlink/?linkid=389579)
</td>
<td style="border:1px solid black;">
[**MS14-003**](http://go.microsoft.com/fwlink/?linkid=389578)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit
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
Windows 8 per sistemi x64
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
Windows 8.1 per sistemi a 32 bit
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
Windows 8.1 per sistemi x64
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2012 e Windows Server 2012 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-002**](http://go.microsoft.com/fwlink/?linkid=389579)
</td>
<td style="border:1px solid black;">
[**MS14-003**](http://go.microsoft.com/fwlink/?linkid=389578)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012
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
Windows Server 2012 R2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Windows RT e Windows RT 8.1
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-002**](http://go.microsoft.com/fwlink/?linkid=389579)
</td>
<td style="border:1px solid black;">
[**MS14-003**](http://go.microsoft.com/fwlink/?linkid=389578)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows RT
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
Windows RT 8.1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Opzione di installazione Server Core
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-002**](http://go.microsoft.com/fwlink/?linkid=389579)
</td>
<td style="border:1px solid black;">
[**MS14-003**](http://go.microsoft.com/fwlink/?linkid=389578)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**[](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
(2913602)  
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
</tr>
</table>
 

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Office 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-001**](http://go.microsoft.com/fwlink/?linkid=386452)
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
Microsoft Word 2003 Service Pack 3  
(2863866)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Office 2007
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-001**](http://go.microsoft.com/fwlink/?linkid=386452)
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
Microsoft Office 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
Microsoft Word 2007 Service Pack 3  
(2837617)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Office 2010
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-001**](http://go.microsoft.com/fwlink/?linkid=386452)
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
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 1 (edizioni a 32 bit)  
(2863902)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 1 (edizioni a 32 bit)  
(2863901)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 2 (edizioni a 32 bit)  
(2863902)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 2 (edizioni a 32 bit)  
(2863901)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 1 (edizioni a 64 bit)  
(2863902)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 1 (edizioni a 64 bit)  
(2863901)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 2 (edizioni a 64 bit)  
(2863902)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 2 (edizioni a 64 bit)  
(2863901)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Office 2013 e Microsoft Office 2013 RT
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-001**](http://go.microsoft.com/fwlink/?linkid=386452)
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
Microsoft Office 2013 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Word 2013 (edizioni a 32 bit)  
(2827224)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Microsoft Word 2013 (edizioni a 32 bit)  
(Word PIA)  
(2863834)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)  
(2827224)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)  
(Word PIA)  
(2863834)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 RT
</td>
<td style="border:1px solid black;">
Microsoft Word 2013 RT  
(2827224)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Altro software Office
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-001**](http://go.microsoft.com/fwlink/?linkid=386452)
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
Pacchetto di compatibilità Microsoft Office Service Pack 3
</td>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3  
(2837615)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Word Viewer
</td>
<td style="border:1px solid black;">
Microsoft Word Viewer  
(2863867)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS14-001**

Questo bollettino riguarda più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

#### Microsoft Office Services e Web Apps

 
<table style="border:1px solid black;">
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
[**MS14-001**](http://go.microsoft.com/fwlink/?linkid=386452)
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
Word Automation Services  
(2837577)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 2
</td>
<td style="border:1px solid black;">
Word Automation Services  
(2837577)  
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
[**MS14-001**](http://go.microsoft.com/fwlink/?linkid=386452)
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
Word Automation Services  
(2837625)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Office Web Apps 2010
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-001**](http://go.microsoft.com/fwlink/?linkid=386452)
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
Microsoft Office Web Apps 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Microsoft Web Applications 2010 Service Pack 1  
(2837596)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Web Apps 2010 Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft Web Applications 2010 Service Pack 2  
(2837596)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Office Web Apps 2013
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-001**](http://go.microsoft.com/fwlink/?linkid=386452)
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
Microsoft Office Web Apps 2013
</td>
<td style="border:1px solid black;">
Microsoft Office Web Apps Server 2013  
(2863879)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS14-001**

Questo bollettino riguarda più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

#### Soluzioni Microsoft Enterprise Resource Planning (ERP)

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Dynamics AX 4.0
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-004**](http://go.microsoft.com/fwlink/?linkid=386402)
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
Microsoft Dynamics AX 4.0 Service Pack 2
</td>
<td style="border:1px solid black;">
Microsoft Dynamics AX 4.0 Service Pack 2  
(2920510)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Dynamics AX 2009
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-004**](http://go.microsoft.com/fwlink/?linkid=386402)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Dynamics AX 2009 Service Pack 1
</td>
<td style="border:1px solid black;">
Microsoft Dynamics AX 2009 Service Pack 1  
(2914058)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Dynamics AX 2012 e Microsoft Dynamics AX 2012 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS14-004**](http://go.microsoft.com/fwlink/?linkid=386402)
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
Microsoft Dynamics AX 2012
</td>
<td style="border:1px solid black;">
Microsoft Dynamics AX 2012  
(2914055)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Dynamics AX 2012 R2
</td>
<td style="border:1px solid black;">
Microsoft Dynamics AX 2012 R2  
(2914057)  
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

-   [Articolo della Microsoft Knowledge Base 894199](https://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
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
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](https://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

**MS14-001**

-   Mateusz Jurczyk, Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Word (CVE-2014-0258)
-   Mateusz Jurczyk, Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Word (CVE-2014-0259)
-   Mateusz Jurczyk, Ivan Fratric e Ben Hawkes di [Google Security Team](http://www.google.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Word (CVE-2014-0260)

**MS14-002**

-   [FireEye, Inc.](http://www2.fireeye.com/) per aver collaborato nella definizione della vulnerabilità legata al componente NDProxy del kernel (CVE-2013-5065)

**MS14-003**

-   Yujie Wen e Renguang Yuan di [Qihoo](http://www.360.cn/) per aver segnalato la vulnerabilità legata all'handle di finestra in Win32k (CVE-2014-0262)

**MS14-004**

-   Andrey Maykov, Lead Developer presso [FTO Project](http://www.fto.com.ru/), per aver segnalato la vulnerabilità legata ad attacchi di tipo Denial of Service nel filtro (CVE-2014-0261)

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (14 gennaio 2014): Pubblicazione del riepilogo dei bollettini.

*Built at 2014-04-18T01:50:00Z-07:00*
