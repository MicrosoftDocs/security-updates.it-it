---
TOCTitle: 'MS10-MAR'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - marzo 2010'
ms:assetid: 'ms10-mar'
ms:contentKeyID: 61240049
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms10-mar(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - marzo 2010
===============================================================

Data di pubblicazione: martedì 9 marzo 2010 | Aggiornamento: mercoledì 11 agosto 2010

**Versione:** 3.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a marzo 2010.

Con il rilascio dei bollettini del mese di marzo 2010, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 4 marzo 2010. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/advance).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 10 marzo 2010 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di marzo](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032427711&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

Per il bollettino straordinario sulla sicurezza aggiunto alla versione 2.0 del presente riepilogo dei bollettini, MS10-018, Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questo bollettino il 30 marzo 2010, alle 13:00 ora del Pacifico (USA e Canada). [Registrazione immediata per il webcast del 30 marzo alle 13:00](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032448112&culture=en-us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-018">MS10-018</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet (980182)</strong> <br />
<br />
Questo aggiornamento per la protezione risolve nove vulnerabilità segnalate privatamente a Microsoft e una vulnerabilità divulgata pubblicamente relative a Internet Explorer. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-016">MS10-016</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Windows Movie Maker può consentire l'esecuzione di codice in modalità remota (975561)</strong><br />
<br />
Il presente aggiornamento per la protezione risolve una vulnerabilità relativa a Windows Movie Maker e Microsoft Producer 2003 che è stata segnalata privatamente. Windows Live Movie Maker, disponibile per Windows Vista e Windows 7, non è interessato da questa vulnerabilità. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato invia un file di progetto di Movie Maker o Microsoft Producer appositamente predisposto e convince l'utente ad aprirlo. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows, Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-017">MS10-017</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Office Excel possono consentire l'esecuzione di codice in modalità remota (980150)</strong><br />
<br />
Questo aggiornamento per la protezione risolve sette vulnerabilità di Microsoft Office Excel segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota durante l'apertura di un file di Excel appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità sono elencate in ordine decrescente sulla base del livello di valutazione del rischio e quindi del codice CVE.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).
  
| ID bollettino                                                       | Titolo della vulnerabilità                                                                             | ID CVE                                                                           | Valutazione dell'Exploitability Index                                                                                       | Note fondamentali                                                            |  
|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|  
| [MS10-017](http://technet.microsoft.com/security/bulletin/ms10-017) | Vulnerabilità legata al danneggiamento della memoria record di Microsoft Office Excel                  | [CVE-2010-0257](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0257) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                    |  
| [MS10-017](http://technet.microsoft.com/security/bulletin/ms10-017) | Vulnerabilità legata all'overflow degli heap dei record MDXTUPLE di Microsoft Office Excel             | [CVE-2010-0260](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0260) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                    |  
| [MS10-017](http://technet.microsoft.com/security/bulletin/ms10-017) | Vulnerabilità legata all'overflow degli heap dei record MDXSET di Microsoft Office Excel               | [CVE-2010-0261](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0261) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                    |  
| [MS10-017](http://technet.microsoft.com/security/bulletin/ms10-017) | Vulnerabilità legata all'esecuzione di codice durante l'analisi di file XLSX di Microsoft Office Excel | [CVE-2010-0263](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0263) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                    |  
| [MS10-017](http://technet.microsoft.com/security/bulletin/ms10-017) | Vulnerabilità legata all'analisi dei record DbOrParamQry di Microsoft Office Excel                     | [CVE-2010-0264](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0264) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                    |  
| [MS10-016](http://technet.microsoft.com/security/bulletin/ms10-016) | Vulnerabilità legata all'overflow del buffer in Movie Maker e Producer                                 | [CVE-2010-0265](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0265) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                    |  
| [MS10-018](http://technet.microsoft.com/security/bulletin/ms10-018) | Vulnerabilità legata al danneggiamento della memoria di oggetti HTML                                   | [CVE-2010-0491](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0491) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                    |  
| [MS10-018](http://technet.microsoft.com/security/bulletin/ms10-018) | Vulnerabilità legata al danneggiamento della memoria di oggetti HTML                                   | [CVE-2010-0492](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0492) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                    |  
| [MS10-018](http://technet.microsoft.com/security/bulletin/ms10-018) | Vulnerabilità del modello di protezione tra domini per elementi HTML                                   | [CVE-2010-0494](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0494) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | L'esecuzione di codice è possibile solo su Windows 2000                      |  
| [MS10-018](http://technet.microsoft.com/security/bulletin/ms10-018) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                 | [CVE-2010-0806](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0806) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Questa vulnerabilità è attualmente sfruttata nell'ecosistema di Internet** |  
| [MS10-018](http://technet.microsoft.com/security/bulletin/ms10-018) | Vulnerabilità legata al danneggiamento della memoria nel rendering HTML                                | [CVE-2010-0807](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0807) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                    |  
| [MS10-017](http://technet.microsoft.com/security/bulletin/ms10-017) | Vulnerabilità legata alla confusione dei tipi di oggetto foglio di Microsoft Office Excel              | [CVE-2010-0258](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0258) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                    |  
| [MS10-017](http://technet.microsoft.com/security/bulletin/ms10-017) | Vulnerabilità legata alla memoria non inizializzata dei record FNGROUPNAME di Microsoft Office Excel   | [CVE-2010-0262](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0262) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                    |  
| [MS10-018](http://technet.microsoft.com/security/bulletin/ms10-018) | Vulnerabilità legata al danneggiamento della memoria in caso di race condition                         | [CVE-2010-0489](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0489) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                    |  
| [MS10-018](http://technet.microsoft.com/security/bulletin/ms10-018) | Vulnerabilità legata al danneggiamento della memoria                                                   | [CVE-2010-0805](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0805) | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                    |  
| [MS10-018](http://technet.microsoft.com/security/bulletin/ms10-018) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                 | [CVE-2010-0267](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0267) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | (Nessuna)                                                                    |  
| [MS10-018](http://technet.microsoft.com/security/bulletin/ms10-018) | Vulnerabilità legata all'intercettazione di informazioni personali in seguito alla codifica            | [CVE-2010-0488](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0488) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | (Nessuna)                                                                    |  
| [MS10-018](http://technet.microsoft.com/security/bulletin/ms10-018) | Vulnerabilità legata al danneggiamento della memoria non inizializzata                                 | [CVE-2010-0490](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0490) | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | (Nessuna)                                                                    |
  
Software interessato e percorsi per il download  
-----------------------------------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle?**
  
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
[**MS10-016**](http://technet.microsoft.com/security/bulletin/ms10-016)
</td>
<td style="border:1px solid black;">
[**MS10-018**](http://technet.microsoft.com/security/bulletin/ms10-018)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 5.01 Service Pack 4](http://www.microsoft.com/downloads/details.aspx?familyid=389da7a9-e0a3-4b5d-801e-0a38fc55dcec)  
(Critico)  
[Internet Explorer 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=daf199c4-da56-4a7f-80e6-3936ce5c267b)  
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
[**MS10-016**](http://technet.microsoft.com/security/bulletin/ms10-016)
</td>
<td style="border:1px solid black;">
[**MS10-018**](http://technet.microsoft.com/security/bulletin/ms10-018)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
[Movie Maker 2.1](http://www.microsoft.com/downloads/details.aspx?familyid=6301e462-02be-4b9a-bae9-7c4821b42d2d)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=2f2caa01-5cd1-45cb-9995-e34d933920d4)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=167ed896-d383-4dc0-9183-cd4cb73e17e7)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=46172617-293a-44c7-95b6-18202ab06a41)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Movie Maker 2.1](http://www.microsoft.com/downloads/details.aspx?familyid=cae81585-d0df-41b8-9277-ca02f1265056)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=6c711387-6853-477c-917e-820a97613cf9)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=aadb1d97-5cec-45ed-9967-aaf41a0bcdac)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=284d70ea-24a3-4e67-a2a8-e9f272f728db)  
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
[**MS10-016**](http://technet.microsoft.com/security/bulletin/ms10-016)
</td>
<td style="border:1px solid black;">
[**MS10-018**](http://technet.microsoft.com/security/bulletin/ms10-018)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=dc77f1c9-8240-42d9-aee9-30ac4f33bde7)  
(Importante)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=e957a7cf-e5ca-454d-b199-ec8fe6a6a2bf)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=53fc3285-63c4-487f-ad9a-7e1673aeffc7)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=2be85462-28ec-4184-a326-0459554b7213)  
(Importante)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=cb0e39f8-9730-4454-a0e3-479b610b1591)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=5201a0c5-8162-4809-b9d1-0e972b0f0066)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=04abea55-ea2f-423f-b410-5536ea184ea3)  
(Importante)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=7ebd99b4-da6b-4dff-9f89-6a86d275a3da)  
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
[**MS10-016**](http://technet.microsoft.com/security/bulletin/ms10-016)
</td>
<td style="border:1px solid black;">
[**MS10-018**](http://technet.microsoft.com/security/bulletin/ms10-018)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
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
[Movie Maker 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=ae2e9b75-1616-4fe3-91bb-e2e28252ff1c)<sup>[1]</sup>
(Importante)  
[Movie Maker 2.6](http://www.microsoft.com/downloads/details.aspx?familyid=ca2d1118-ca64-419d-86af-9396e61b90b0)<sup>[2]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=511aba0e-6f15-42cf-9c5d-b2f3e215b5a8)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c9584689-5196-4840-927c-23c8038f3382)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition, Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Movie Maker 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=e27f353e-deb6-4d61-8808-c751d20a42a1)<sup>[1]</sup>
(Importante)  
[Movie Maker 2.6](http://www.microsoft.com/downloads/details.aspx?familyid=6a1f4126-97f2-4aee-bfe1-05bd13a0667b)<sup>[2]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=c8933a45-62a7-4c19-be30-02e3a461f081)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=50809cc3-6baa-41b4-ba0a-596a1dd846ed)  
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
[**MS10-016**](http://technet.microsoft.com/security/bulletin/ms10-016)
</td>
<td style="border:1px solid black;">
[**MS10-018**](http://technet.microsoft.com/security/bulletin/ms10-018)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=42f8c1f2-ee55-47af-b113-8d9f4bd40c8f)\*\*  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c69a6dfe-66b1-4426-96a5-d64000296e76)\*\*  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=769043b5-df52-4446-9bd8-dc37d9fa00df)\*\*  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=e16c10d2-896d-48f3-bc76-5fa70881396a)\*\*  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=c1c2309d-22db-4dbf-ad95-3219847cd42d)  
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
[**MS10-016**](http://technet.microsoft.com/security/bulletin/ms10-016)
</td>
<td style="border:1px solid black;">
[**MS10-018**](http://technet.microsoft.com/security/bulletin/ms10-018)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c0145563-428e-47b6-b245-b59dce88ac0e)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=6172dbec-6bfc-40bd-a0d4-67c39fb41b87)  
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
[**MS10-016**](http://technet.microsoft.com/security/bulletin/ms10-016)
</td>
<td style="border:1px solid black;">
[**MS10-018**](http://technet.microsoft.com/security/bulletin/ms10-018)
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
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=8b7c664b-8612-458f-bd0a-cf28b67f8374)\*\*  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=82fa6f47-002f-4943-888c-2e852675e76e)  
(Moderato)
</td>
</tr>
</table>
 
**Nota per Windows Server 2008 e Windows Server 2008 R2**

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/italy/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/italy/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Note per MS10-016**

<sup>[1]</sup>Queste versioni di Windows Movie Maker vengono fornite con i sistemi operativi indicati.

<sup>[2]</sup>Windows Movie Maker 2.6 è un download facoltativo che può essere installato sui sistemi operativi indicati.

Vedere ulteriori categorie software nella sezione Software interessato e percorsi per il download, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Suite e software Microsoft Office

 
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
Applicazioni, sistemi e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-017**](http://technet.microsoft.com/security/bulletin/ms10-017)
</td>
<td style="border:1px solid black;">
[**MS10-016**](http://technet.microsoft.com/security/bulletin/ms10-016)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office XP
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e0136f62-60ce-4ebd-8660-be81eba29ae8)  
(KB978471)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=7e42793e-747b-48da-968a-1ec29ea37151)  
(KB978474)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office System 2007
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel 2007 Service Pack 1 e Microsoft Office Excel 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=03429f8a-8aab-4a59-97e4-7ce047f100a5)<sup>[1]</sup>
(KB978382)  
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
[**MS10-017**](http://technet.microsoft.com/security/bulletin/ms10-017)
</td>
<td style="border:1px solid black;">
[**MS10-016**](http://technet.microsoft.com/security/bulletin/ms10-016)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=ae5936f8-fe3f-4d23-a37c-d80f228e475e)  
(KB980837)  
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
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=e0ed1569-ab2f-407c-b728-4eddc463c385)  
(KB980839)  
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
[Convertitore file in formato XML aperto per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=4c5487d5-c912-4087-8c83-769e3fb78ea9)  
(KB980840)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Altro software Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-017**](http://technet.microsoft.com/security/bulletin/ms10-017)
</td>
<td style="border:1px solid black;">
[**MS10-016**](http://technet.microsoft.com/security/bulletin/ms10-016)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
Microsoft Office Excel Viewer
</td>
<td style="border:1px solid black;">
[Microsoft Office Excel Viewer Service Pack 1 e Microsoft Office Excel Viewer Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=010d0a4d-02a4-4142-963b-a38cd06cc897)  
(KB978383)  
(Importante)
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
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=314f076e-8f9d-46c2-b666-86599a02bf15)  
(KB978380)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office SharePoint Server 2007 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2007 Service Pack 1 e Microsoft Office SharePoint Server 2007 Service Pack 2 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=94ddf6ef-3392-4d77-a02b-3bc0470721cd)<sup>[2]</sup>
(KB979439)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office SharePoint Server 2007 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2007 Service Pack 1 e Microsoft Office SharePoint Server 2007 Service Pack 2 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=06f6bffb-3fad-4fb5-878b-39550812e9b5)<sup>[2]</sup>
(KB979439)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Producer 2003
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Producer 2003](http://www.microsoft.com/downloads/details.aspx?familyid=1b3c76d5-fc75-4f99-94bc-784919468e73)<sup>[3]</sup>
(Importante)
</td>
</tr>
</table>
 
**Note per MS10-017**

<sup>[1]</sup>Per Microsoft Office Excel 2007 Service Pack 1 e Microsoft Office Excel 2007 Service Pack 2, oltre al pacchetto di aggiornamento per la protezione KB978382, gli utenti devono installare anche l'aggiornamento per la protezione per il [pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 1 e il pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=314f076e-8f9d-46c2-b666-86599a02bf15) (KB978380) per essere protetti dalle vulnerabilità descritte nel bollettino.

<sup>[2]</sup>Questo aggiornamento si applica ai server che hanno installato Excel Services, come Microsoft Office SharePoint Server 2007 Enterprise e Microsoft Office SharePoint Server 2007 per siti Internet, nella loro configurazione predefinita. Microsoft Office SharePoint Server 2007 Standard non contiene Excel Services.

**Note per MS10-016**

<sup>[3]</sup>Questo download aggiorna l'installazione di Microsoft Producer 2003 alla nuova versione di Microsoft Producer. Microsoft Producer è disponibile solo in inglese.

Vedere ulteriori categorie software nella sezione Software interessato e percorsi per il download, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Nota** A partire dal 1 agosto, 2009, Microsoft non offre più alcun supporto per Office Update e Office Update Inventory Tool. Per continuare a ricevere gli ultimi aggiornamenti per i prodotti Microsoft Office, utilizzare [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Per ulteriori informazioni, vedere [Informazioni su Microsoft Office Update: Domande frequenti](http://office.microsoft.com/it-it/downloads/fx101321101040.aspx?pid=cl100570421040).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208(en-us).aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/it-it/library/bb735860(en-us).aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://go.microsoft.com/fwlink/?linkid=22939). Gli utenti di SMS 2.0 possono inoltre utilizzare Security Update Inventory Tool per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/systemcenter/configmgr/default.mspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/sms/bb676800.aspx)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/wsus/bb456965.aspx). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://www.microsoft.com/security/msrc/collaboration/mapppartners.aspx).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Damián Frizza di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato un problema descritto nel bollettino MS10-016
-   Nicolas Joly del [VUPEN Vulnerability Research Team](http://www.vupen.com/) per aver segnalato un problema descritto nel bollettino MS10-017
-   Sean Larsson di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato quattro problemi descritti nel bollettino MS10-017
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS10-017
-   Damián Frizza di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato un problema descritto nel bollettino MS10-017
-   [Secunia](http://secunia.com) per aver collaborato con noi allo studio di un problema descritto nel bollettino MS10-018
-   Daiki Fukumori di [Cyber Defense Institute Inc.](http://www.cyberdefense.jp/) per aver segnalato un problema descritto nel bollettino MS10-018
-   Alexander Kornbrust di [Red Database Security](http://www.red-database-security.com/) per aver segnalato un problema descritto nel bollettino MS10-018
-   Ivan Fratric di [iSIGHT Partners](http://www.isightpartners.com/) Global Vulnerability Partnership per aver segnalato un problema descritto nel bollettino MS10-018
-   Wushi di [team509](http://www.team509.com/), che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS10-018
-   Simon Zuckerbraun, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/), per aver segnalato un problema descritto nel bollettino MS10-018
-   Paul Stone di [Context Information Security](http://www.contextis.co.uk/) per aver segnalato un problema descritto nel bollettino MS10-018
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS10-018
-   ADLab di [VenusTech](http://www.venustech.com.cn/) per aver segnalato due problemi descritti nel bollettino MS10-018

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (9 marzo 2010): Pubblicazione del riepilogo dei bollettini.
-   V2.0 (30 marzo 2010): È stato aggiunto il Bollettino Microsoft sulla sicurezza MS10-018, aggiornamento cumulativo per Internet Explorer (980182). È stato inoltre aggiunto il collegamento al webcast del bollettino relativo al presente bollettino straordinario sulla sicurezza.
-   V3.0 (3 maggio 2010): È stata comunicata la disponibilità per il download di Microsoft Producer insieme al bollettino MS10-016.
-   V3.1 (11 agosto 2010): Windows Movie Maker 2.6 è stato rimosso come componente interessato in Windows 7 per MS10-016.

*Built at 2014-04-18T01:50:00Z-07:00*
