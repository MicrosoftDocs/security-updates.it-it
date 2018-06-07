---
TOCTitle: 'MS10-JAN'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - gennaio 2010'
ms:assetid: 'ms10-jan'
ms:contentKeyID: 61240046
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms10-jan(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - gennaio 2010
=================================================================

Data di pubblicazione: martedì 12 gennaio 2010 | Aggiornamento: giovedì 21 gennaio 2010

**Versione:** 2.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a gennaio 2010.

Con il rilascio dei bollettini del mese di gennaio 2010, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il giorno 20 gennaio 2010. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 13 gennaio 2010 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di gennaio](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032427677&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Per il bollettino straordinario sulla sicurezza aggiunto alla versione 2.0 del presente riepilogo dei bollettini, MS10-002, Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questo bollettino il 21 gennaio 2010, alle 13:00 ora del Pacifico di PM (USA e Canada). [Registrazione immediata per il webcast del 21 gennaio alle 13:00](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032440627&culture=en-us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-001">MS10-001</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nel motore per caratteri Embedded OpenType possono consentire l'esecuzione di codice in modalità remota (972270)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un contenuto reso con carattere EOT (Embedded OpenType) appositamente predisposto in applicazioni client che eseguono il rendering dei caratteri EOT, come Microsoft Internet Explorer, Microsoft Office PowerPoint o Microsoft Office Word. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Può richiedere il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-002">MS10-002</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (978207)</strong><br />
<br />
Questo aggiornamento per la protezione risolve sette vulnerabilità segnalate privatamente a Microsoft e una vulnerabilità divulgata pubblicamente relative a Internet Explorer. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).
  
| ID bollettino                                                       | Titolo della vulnerabilità                                                                                             | ID CVE                                                                           | Valutazione dell'Exploitability Index                                                                                | Note fondamentali                                                                                                                                                                                                                                   |  
|---------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| [MS10-001](http://technet.microsoft.com/security/bulletin/ms10-001) | Vulnerabilità legata ad un difetto dei valori integer dei font compressi in Microtype Express nel decompressore LZCOMP | [CVE-2010-0018](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0018) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità | Questa valutazione dell'Exploitability Index interessa i sistemi che eseguono Microsoft Windows 2000. La probabilità di sfruttamento dei sistemi che eseguono Windows XP e sistemi operativi successivi è scarsa.                                   |  
| [MS10-002](http://technet.microsoft.com/security/bulletin/ms10-002) | Vulnerabilità legata alla gestione di filtri XSS contro attacchi tramite script                                        | [CVE-2009-4074](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2009-4074) | Nessuno                                                                                                              | L'esecuzione di codice non è possibile con questa vulnerabilità.                                                                                                                                                                                    |  
| [MS10-002](http://technet.microsoft.com/security/bulletin/ms10-002) | Vulnerabilità legata alla convalida dell'URL                                                                           | [CVE-2010-0027](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0027) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                           |  
| [MS10-002](http://technet.microsoft.com/security/bulletin/ms10-002) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                                 | [CVE-2010-0244](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0244) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                           |  
| [MS10-002](http://technet.microsoft.com/security/bulletin/ms10-002) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                                 | [CVE-2010-0245](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0245) | Nessuno                                                                                                              | I clienti che hanno applicato quanto indicato dal bollettino [MS09-072](http://technet.microsoft.com/security/bulletin/ms09-072) sono protetti perché questa vulnerabilità viene bloccata dalle modifiche contenute nell'aggiornamento di MS09-072. |  
| [MS10-002](http://technet.microsoft.com/security/bulletin/ms10-002) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                                 | [CVE-2010-0246](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0246) | Nessuno                                                                                                              | I clienti che hanno applicato quanto indicato dal bollettino [MS09-072](http://technet.microsoft.com/security/bulletin/ms09-072) sono protetti perché questa vulnerabilità viene bloccata dalle modifiche contenute nell'aggiornamento di MS09-072. |  
| [MS10-002](http://technet.microsoft.com/security/bulletin/ms10-002) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                                 | [CVE-2010-0247](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0247) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                                                                                                                                                                           |  
| [MS10-002](http://technet.microsoft.com/security/bulletin/ms10-002) | Vulnerabilità legata al danneggiamento della memoria HTML                                                              | [CVE-2010-0248](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0248) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità | (Nessuna)                                                                                                                                                                                                                                           |  
| [MS10-002](http://technet.microsoft.com/security/bulletin/ms10-002) | Vulnerabilità legata al danneggiamento della memoria HTML                                                              | [CVE-2010-0249](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0249) | [**1**](http://technet.microsoft.com/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità  | **Questa vulnerabilità è attualmente sfruttata nell'ecosistema di Internet.**                                                                                                                                                                       |
  
Software interessato e posizioni per il download  
------------------------------------------------
  
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
</tr>
<tr>
<th colspan="3">
Microsoft Windows 2000  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-001**](http://technet.microsoft.com/security/bulletin/ms10-001)
</td>
<td style="border:1px solid black;">
[**MS10-002**](http://technet.microsoft.com/security/bulletin/ms10-002)
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
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=47f85cbd-282e-4c92-9809-68bba49e0a12)  
(Critico)
</td>
<td style="border:1px solid black;">
[Internet Explorer 5.01 Service Pack 4 installato in Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=51e99e4f-1670-4b12-a9fe-e0ccf50cdabc)  
(Critico)  
[Internet Explorer 6 Service Pack 1 installato in Microsoft Windows 2000 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=a38aa9d0-c3fe-4d41-8805-7d5370263c1b)  
(Critico)
</td>
</tr>
<tr>
<th colspan="3">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-001**](http://technet.microsoft.com/security/bulletin/ms10-001)
</td>
<td style="border:1px solid black;">
[**MS10-002**](http://technet.microsoft.com/security/bulletin/ms10-002)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Basso**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2 e Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=793a6b3f-7660-40be-b7d5-7b0eec55e1cd)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6 per Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=207eecad-6e84-48e6-ae18-6794a3618ee0)  
(Critico)  
[Internet Explorer 7 per Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=3510c7d8-7e8f-479e-b6f9-5745a845664d)  
(Critico)  
[Internet Explorer 8 per Windows XP Service Pack 2 e Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=7c2948fb-f486-4801-bc21-bbf40d5a78c2)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=31609ce9-656a-4f7d-a501-709a31ca34c3)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6 per Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=eb2d8055-4d50-4f83-82b8-055c7b8f5422)  
(Critico)  
[Internet Explorer 7 per Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=cc5aea0b-e553-4f7f-a2cc-cba41bb87ae7)  
(Critico)  
[Internet Explorer 8 per Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=41b83fad-948b-4a9c-80ed-9c5a60bd35b4)  
(Critico)
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-001**](http://technet.microsoft.com/security/bulletin/ms10-001)
</td>
<td style="border:1px solid black;">
[**MS10-002**](http://technet.microsoft.com/security/bulletin/ms10-002)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Basso**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e1d6e338-dea9-458e-b35d-796e069d74d7)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6 per Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fea91227-44ad-4549-8732-497a8ceff870)  
(Moderato)  
[Internet Explorer 7 per Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=14726445-3ff4-463c-9fc1-c9b758079aca)  
(Critico)  
[Internet Explorer 8 per Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7d480c87-2ca9-4505-a59d-a6d73d001fa5)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=ddbcf231-9fde-4dc2-ad04-a01b69d1a980)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6 per Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=633e63f4-605b-43c4-8a4b-2730312a1c72)  
(Moderato)  
[Internet Explorer 7 per Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c8742230-16d8-4b2f-bd3e-8834c759856b)  
(Critico)  
[Internet Explorer 8 per Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3e2e740b-8417-4758-8468-15221249ec71)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=c71a13cf-7e2f-4b02-8684-1a4e4b46ddda)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6 per Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=b9308d50-ca66-43ff-9dc5-d05c90baa764)  
(Moderato)  
[Internet Explorer 7 per Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=5622f223-df9c-4a6a-bdf0-feebaf9920fd)  
(Critico)
</td>
</tr>
<tr>
<th colspan="3">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-001**](http://technet.microsoft.com/security/bulletin/ms10-001)
</td>
<td style="border:1px solid black;">
[**MS10-002**](http://technet.microsoft.com/security/bulletin/ms10-002)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Basso**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6387228c-eedc-4511-b3c6-8922606f4c84)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7 in Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=92495551-dedd-43d4-bb3a-51028bc5c6d6)  
(Critico)  
[Internet Explorer 8 in Windows Vista, Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5e2cbd7d-f64f-49e5-a159-1965ebfe2a92)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7b4f5089-13b1-421b-a00b-22632bba4229)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7 in Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3cb139b3-59f4-44ef-9911-4dd4e3b83e7d)  
(Critico)  
[Internet Explorer 8 in Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b7a7e8e7-f4c5-459d-ab6c-05a192e1e3f9)  
(Critico)
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-001**](http://technet.microsoft.com/security/bulletin/ms10-001)
</td>
<td style="border:1px solid black;">
[**MS10-002**](http://technet.microsoft.com/security/bulletin/ms10-002)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Basso**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e175c436-37e0-497f-8b7f-6cacaa25ad7c)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7 in Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8c4c91ec-1b2b-4176-bd77-45245b590329)\*\*  
(Critico)  
[Internet Explorer 8 in Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f5ce8582-af63-4870-bee3-0abeeefa1458)\*\*  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1b10a177-fd45-406f-8edc-b8d4b84881b7)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7 in Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4f9975b8-3f91-4116-9200-ef55ece75854)\*\*  
(Critico)  
[Internet Explorer 8 in Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=be11981c-d286-4e3c-94bf-d4e67a975d5a)\*\*  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e8bc9a24-a794-4827-a6bb-785c6b2189f4)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7 in Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9395547f-b620-4cbd-9ff5-11b76cd73859)  
(Critico)
</td>
</tr>
<tr>
<th colspan="3">
Windows 7
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-001**](http://technet.microsoft.com/security/bulletin/ms10-001)
</td>
<td style="border:1px solid black;">
[**MS10-002**](http://technet.microsoft.com/security/bulletin/ms10-002)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Basso**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=75491ad0-40a6-4efb-9574-d82210f6d0da)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8 in Windows 7 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=278443c1-15dc-436b-893b-ffea6d29d16d)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=8a53f0e9-0616-440e-90f2-a12524e1bee4)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8 in Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=a584cd0f-2e05-4e36-8858-0ffead637162)  
(Critico)
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2008 R2
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-001**](http://technet.microsoft.com/security/bulletin/ms10-001)
</td>
<td style="border:1px solid black;">
[**MS10-002**](http://technet.microsoft.com/security/bulletin/ms10-002)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Basso**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=308166e4-571b-4d6c-bd9f-3ed4afa4eafe)\*\*  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8 in Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=d3386793-a594-4bc5-8308-28b561d43087)\*\*  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=1d0da42b-9755-4fd2-afd1-0d023d187133)  
(Basso)
</td>
<td style="border:1px solid black;">
[Internet Explorer 8 in Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=9d137bab-8312-4240-af74-c65ba652fde0)  
(Critico)
</td>
</tr>
</table>
 
**Nota per Windows Server 2008 e Windows Server 2008 R2**

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/en-us/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Note** A partire dal 1 agosto, 2009, Microsoft non offre più alcun supporto per Office Update e Office Update Inventory Tool. Per continuare a ricevere gli ultimi aggiornamenti per i prodotti Microsoft Office, utilizzare [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it). Per ulteriori informazioni, vedere [Informazioni su Microsoft Office Update: Domande frequenti](http://office.microsoft.com/it-it/downloads/fx010402221040.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare Security Update Inventory Tool per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/sms/bb676800.aspx)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/wsus/bb456965.aspx). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://www.microsoft.com/security/msrc/mapp/partners.mspx).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Tavis Ormandy di [Google Inc.](http://www.google.com/) per aver segnalato un problema descritto nel bollettino MS10-001
-   [David Lindsay "thornmaker"](http://p42.us/) ed [Eduardo A. Vela Nava "sirdarckcat"](http://www.sirdarckcat.net/) per aver segnalato un problema descritto nel bollettino MS10-002
-   Lostmon Lords per aver segnalato un problema descritto nel bollettino MS10-002
-   Brett Moore, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS10-002
-   Wushi di [team509](http://www.team509.com/), collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS10-002
-   Sam Thomas di eshu.co.uk, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato alcuni problemi descritti nel bollettino MS10-002
-   Haifei Li del [FortiGuard Global Security Research Team](http://www.fortiguardcenter.com/) di Fortinet, per aver segnalato un problema descritto nel bollettino MS10-002
-   Peter Vreugdenhil di [VeriSign iDefense Labs](http://labs.idefense.com/), collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS10-002
-   Meron Sellem di [BugSec](http://www.bugsec.com/) per aver segnalato un problema descritto nel bollettino MS10-002

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) le seguenti aziende per la loro collaborazione e per aver fornito dettagli su un problema descritto nel bollettino MS10-002:

-   [Google Inc.](http://www.google.com/) e [MANDIANT](http://www.mandiant.com/)
-   [Adobe](http://www.adobe.com/)
-   [McAfee](http://www.mcafee.com/)

    French government CSIRT ([CERTA](http://www.certa.ssi.gouv.fr))

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://www.microsoft.com/italy/athome/security/support/default.mspx). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/default.aspx?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (12 gennaio 2010): Pubblicazione del riepilogo dei bollettini.
-   V2.0 (21 gennaio 2010): È stato aggiunto il Bollettino Microsoft sulla sicurezza **MS10-002, aggiornamento cumulativo per Internet Explorer (978207)**. È stato inoltre aggiunto il collegamento al webcast del bollettino relativo al presente bollettino straordinario sulla sicurezza.

*Built at 2014-04-18T01:50:00Z-07:00*
