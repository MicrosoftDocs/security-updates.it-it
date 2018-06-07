---
TOCTitle: 'MS09-MAY'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - maggio 2009'
ms:assetid: 'ms09-may'
ms:contentKeyID: 61240038
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms09-may(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - maggio 2009
================================================================

Data di pubblicazione: martedì 12 maggio 2009 | Aggiornamento: martedì 9 giugno 2009

**Versione:** 2.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a maggio 2009.

Con il rilascio dei bollettini del mese di maggio 2009, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 7 maggio 2009. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 13 maggio 2009 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di maggio](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?culture=en-us&eventid=1032395223). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</strong><br />
<br />
L'aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e diverse vulnerabilità segnalate privatamente in Microsoft Office PowerPoint, che potrebbero consentire l'esecuzione di codice in modalità remota se un utente apre un file di PowerPoint appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato potrebbe assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE.
  
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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0220">CVE-2009-0220</a></td>
<td style="border:1px solid black;">Per le versioni di Office compilate senza /GS:<br />
<a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">La protezione /GS applicata durante la compilazione di Office 2003 Service Pack 3 e versioni successive di Office rappresenta un fattore attenuante per la vulnerabilità e riduce sensibilmente il rischio per tali sistemi fino a <a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0221">CVE-2009-0221</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0222">CVE-2009-0222</a></td>
<td style="border:1px solid black;">Per le versioni di Office compilate senza /GS:<br />
<a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">La protezione /GS applicata durante la compilazione di Office 2003 Service Pack 3 e versioni successive di Office rappresenta un fattore attenuante per la vulnerabilità e riduce sensibilmente il rischio per tali sistemi fino a <a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0223">CVE-2009-0223</a></td>
<td style="border:1px solid black;">Per le versioni di Office compilate senza /GS:<br />
<a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">La protezione /GS applicata durante la compilazione di Office 2003 Service Pack 3 e versioni successive di Office rappresenta un fattore attenuante per la vulnerabilità e riduce sensibilmente il rischio per tali sistemi fino a <a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0224">CVE-2009-0224</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0225">CVE-2009-0225</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>2</strong></a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0226">CVE-2009-0226</a></td>
<td style="border:1px solid black;">Per le versioni di Office compilate senza /GS:<br />
<a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">La protezione /GS applicata durante la compilazione di Office 2003 Service Pack 3 e versioni successive di Office rappresenta un fattore attenuante per la vulnerabilità e riduce sensibilmente il rischio per tali sistemi fino a <a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0227">CVE-2009-0227</a></td>
<td style="border:1px solid black;">Per le versioni di Office compilate senza /GS:<br />
<a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">La protezione /GS applicata durante la compilazione di Office 2003 Service Pack 3 e versioni successive di Office rappresenta un fattore attenuante per la vulnerabilità e riduce sensibilmente il rischio per tali sistemi fino a <a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-0556">CVE-2009-0556</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><strong>Questa vulnerabilità è attualmente sfruttata nell'ecosistema di Internet.</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1128">CVE-2009-1128</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1129">CVE-2009-1129</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1130">CVE-2009-1130</a></td>
<td style="border:1px solid black;">Per le versioni di Office compilate senza /GS:<br />
<a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">La protezione /GS applicata durante la compilazione di Office 2003 Service Pack 3 e versioni successive di Office rappresenta un fattore attenuante per la vulnerabilità e riduce sensibilmente il rischio per tali sistemi fino a <a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1131">CVE-2009-1131</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms09-017">MS09-017</a></td>
<td style="border:1px solid black;">Alcune vulnerabilità di Microsoft Office PowerPoint possono consentire l'esecuzione di codice in modalità remota (967340)</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-1137">CVE-2009-1137</a></td>
<td style="border:1px solid black;">Per le versioni di Office compilate senza /GS:<br />
<a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>1</strong></a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">La protezione /GS applicata durante la compilazione di Office 2003 Service Pack 3 e versioni successive di Office rappresenta un fattore attenuante per la vulnerabilità e riduce sensibilmente il rischio per tali sistemi fino a <a href="http://technet.microsoft.com/security/cc998259.aspx"><strong>3</strong></a> - Scarsa probabilità di sfruttamento della vulnerabilità.</td>
</tr>
</tbody>
</table>
  
Software interessato e posizioni per il download  
------------------------------------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.
  
**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.
  
#### Suite e software Microsoft Office

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Applicazioni, sistemi e componenti Microsoft Office  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-017**](http://technet.microsoft.com/security/bulletin/ms09-017)
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
Microsoft Office 2000 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office PowerPoint 2000 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f443312a-ac74-4ebc-a4ac-7a756aa67894)  
(KB957790)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office PowerPoint 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=a24ec7ab-c1c7-4ddb-8b6e-107f1af67f49)  
(KB957781)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office PowerPoint 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=ccfa978b-3340-40db-a45d-c880ba36b106)  
(KB957784)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office System Service 2007 Pack 1 e Microsoft Office System 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Office PowerPoint 2007 Service Pack 1 e Microsoft Office PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=11f8380f-ffb6-4c22-a89c-3dc55d0f9834)  
(KB957789)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Office per Mac
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS09-017**](http://technet.microsoft.com/security/bulletin/ms09-017)
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
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=5557bfb7-ebb4-4c42-8042-41e830c4e550)  
(KB969661)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=58326da2-eb75-4b42-b1bc-e70319defb58)  
(KB971822)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Convertitore file in formato XML aperto per Mac
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=9d6d9eaa-8442-4184-8886-faab2803bde6)  
(KB971824)  
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
[**MS09-017**](http://technet.microsoft.com/security/bulletin/ms09-017)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Visualizzatore di PowerPoint
</td>
<td style="border:1px solid black;">
[Visualizzatore di PowerPoint 2003](http://www.microsoft.com/downloads/details.aspx?familyid=6a57e6ed-bd24-406f-87bb-117391e083e0)  
(KB969615)  
(Importante)  
[Visualizzatore di PowerPoint 2007 Service Pack 1 e visualizzatore di PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=141b8338-5c52-4326-a9e4-d2f2d8940d9c)  
(KB970059)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e1d3a4c3-538a-4f98-8d60-250803a80e2a)  
(KB969618)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Works 8.5
</td>
<td style="border:1px solid black;">
[Microsoft Works 8.5](http://www.microsoft.com/downloads/details.aspx?familyid=628280fe-e035-4274-85f2-393d9bad543c)  
(KB967043)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Works 9
</td>
<td style="border:1px solid black;">
[Microsoft Works 9](http://www.microsoft.com/downloads/details.aspx?familyid=f6fa110e-45c6-450f-ae47-c89a06e3f762)  
(KB967044)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS09-017**

Microsoft ha rilasciato di nuovo il bollettino MS09-017 per fornire gli aggiornamenti per la protezione per Microsoft Office 2004 per Mac, Microsoft Office 2008 per Mac, il convertitore file in formato XML aperto per Mac, Microsoft Works 8.5 e Microsoft Works 9. I clienti che utilizzano questo software devono applicare l'aggiornamento immediatamente.

Al momento del primo rilascio del bollettino MS09-017 questi aggiornamenti per la protezione non erano ancora disponibili. Quando Microsoft ha rilasciato il bollettino MS09-017, sul regolare ciclo di rilascio dei bollettini erano disponibili alcuni pacchetti di aggiornamento per la protezione per un'intera linea di prodotti in grado di proteggere la maggior parte degli utenti a rischio. Il nuovo bollettino completa la serie di aggiornamenti per software interessati dalle vulnerabilità trattate in questo bollettino.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

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

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti nuovi, rivisti e rilasciati per i prodotti Microsoft diversi da Microsoft Windows](http://technet.microsoft.com/wsus/dd573344.aspx).

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

-   Un ricercatore anonimo, di [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato due problemi descritti nel bollettino MS09-017
-   Sean Larsson di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato due problemi descritti nel bollettino MS09-017
-   Nicolas Joly di [VUPEN Security](http://www.vupen.com/) per aver segnalato un problema descritto nel bollettino MS09-017
-   Marsu Pilami di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato diversi problemi descritti nel bollettino MS09-017
-   Nicolas Joly di [VUPEN Security](http://www.vupen.com/) per aver segnalato un problema descritto nel bollettino MS09-017
-   Marsu Pilami, di [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS09-017
-   Ling e Wushi del [team509](http://www.team509.com/), che collaborano con [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), e Sean Larsson di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS09-017
-   Carsten H. Eiram di [Secunia](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS09-017

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://www.microsoft.com/italy/athome/security/support/default.mspx). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (12 maggio 2009): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (13 ,aggio 2009): è stata rimossa una nota a piè di pagina non corretta per MS09-017 che riguarda gli aggiornamenti per la protezione KB969618 e KB957789 per le versioni supportate di Microsoft Office PowerPoint 2007.
-   V2.0 (09 giugno 2009): riepilogo rivisto per comunicare il nuovo rilascio di MS09-017, al fine di fornire aggiornamenti per la protezione per Microsoft Office 2004 per Mac, Microsoft Office 2008 per Mac, il convertitore file in formato XML aperto per Mac, Microsoft Works 8.5 e Microsoft Works 9. I clienti che utilizzano questo software devono applicare l'aggiornamento immediatamente.

*Built at 2014-04-18T01:50:00Z-07:00*
