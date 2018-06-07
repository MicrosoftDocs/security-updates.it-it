---
TOCTitle: 'MS11-MAR'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - marzo 2011'
ms:assetid: 'ms11-mar'
ms:contentKeyID: 61240061
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms11-mar(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - marzo 2011
===============================================================

Data di pubblicazione: martedì 8 marzo 2011 | Aggiornamento: mercoledì 16 marzo 2011

**Versione:** 1.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a marzo 2011.

Con il rilascio dei bollettini sulla sicurezza di marzo 2011, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 3 marzo 2011. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/advance).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 9 marzo 2011 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di marzo](https://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032455049&eventcategory=4). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=207841">MS11-015</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Windows Media possono consentire l'esecuzione di codice in modalità remota (2510030)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in DirectShow e una vulnerabilità segnalata privatamente in Windows Media Player e Windows Media Center. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota durante l'apertura di un file Microsoft Digital Video Recording (.dvr-ms) appositamente predisposto. In nessuno di questi casi un utente può essere forzato ad aprire il file; affinché un attacco riesca, l'utente deve eseguire l'operazione in maniera consapevole.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=207892">MS11-017</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità del client desktop remoto può consentire l'esecuzione di codice in modalità remota (2508062)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità del client desktop remoto di Windows che è stata divulgata pubblicamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file legittimo di configurazione del desktop remoto (.rdp) situato nella stessa cartella di rete di un file della libreria appositamente predisposto. L'attacco è possibile solo se l'utente visita un file system remoto o una condivisione WebDAV di dubbia provenienza e apre un documento da questa posizione che è poi caricato da un'applicazione vulnerabile.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=209774">MS11-016</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Groove può consentire l'esecuzione di codice in modalità remota (2494047)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft Groove che può consentire l'esecuzione di codice in modalità remota se un utente apre un file legittimo collegato a Groove situato nella stessa directory di rete di un file della libreria appositamente predisposto. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
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
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità sono elencate in ordine decrescente sulla base del livello di valutazione del rischio e quindi del codice CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).
  
| ID bollettino                                             | Titolo della vulnerabilità                                                     | ID CVE                                                                           | Valutazione dell'Exploitability Index                                                                                    | Note fondamentali                                                                                                      |  
|-----------------------------------------------------------|--------------------------------------------------------------------------------|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|  
| [MS11-016](http://go.microsoft.com/fwlink/?linkid=209774) | Vulnerabilità legata al caricamento di librerie non sicure in Microsoft Groove | [CVE-2010-3146](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3146) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | **Questa vulnerabilità è stata divulgata pubblicamente e potrebbe essere disponibile codice PoC ("proof-of-concept")** |  
| [MS11-017](http://go.microsoft.com/fwlink/?linkid=207892) | Vulnerabilità legata al caricamento di librerie non sicure nel desktop remoto  | [CVE-2011-0029](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0029) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | **Le informazioni sulla vulnerabilità sono state divulgate pubblicamente**                                             |  
| [MS11-015](http://go.microsoft.com/fwlink/?linkid=207841) | Vulnerabilità legata al caricamento di librerie non sicure in DirectShow       | [CVE-2011-0032](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0032) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | **Questa vulnerabilità è stata divulgata pubblicamente e potrebbe essere disponibile codice PoC ("proof-of-concept")** |  
| [MS11-015](http://go.microsoft.com/fwlink/?linkid=207841) | Vulnerabilità di DVR-MS                                                        | [CVE-2011-0042](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0042) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - In caso di sfruttamento sistematico della vulnerabilità | (Nessuna)                                                                                                              |
  
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
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-015**](http://go.microsoft.com/fwlink/?linkid=207841)
</td>
<td style="border:1px solid black;">
[**MS11-017**](http://go.microsoft.com/fwlink/?linkid=207892)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=d8284bfa-ed6c-4647-9fb0-588e53173775)  
(KB2479943)  
(Critico)  
[Windows XP Media Center Edition 2005 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=b1be30de-7e88-467d-aee2-68f88e6a7355)  
(KB2502898)  
(Critico)
</td>
<td style="border:1px solid black;">
[Client Remote Desktop Connection 5.2](http://www.microsoft.com/downloads/details.aspx?familyid=1aed6080-feab-4b5e-9d26-6a3f4b92434d)  
(KB2483618)  
(Importante)  
[Client Remote Desktop Connection 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=d67e4d8c-aeb9-45e6-9555-7456c5540475)  
(KB2481109)  
(Importante)  
[Client Remote Desktop Connection 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=6a01992e-c9a1-4dc9-a3ef-7410b81f17e6)  
(KB2483614)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5270b5d3-3720-42a2-a8cf-67089c0cc658)  
(KB2479943)  
(Critico)
</td>
<td style="border:1px solid black;">
[Client Remote Desktop Connection 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=6d4539ef-4a05-4c7d-9489-436f7b7a3ebe)<sup>[1]</sup>
(KB2481109)  
(Importante)
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
[**MS11-015**](http://go.microsoft.com/fwlink/?linkid=207841)
</td>
<td style="border:1px solid black;">
[**MS11-017**](http://go.microsoft.com/fwlink/?linkid=207892)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Client Remote Desktop Connection 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=641d5d12-0790-4551-831a-e78febad17a7)<sup>[1]</sup>
(KB2481109)  
(Importante)  
[Interfaccia utente multilingue (MUI) del client Remote Desktop Connection 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=6fec0d06-042d-4e55-9843-009edd7d26ce)<sup>[2]</sup>
(KB2483619)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Client Remote Desktop Connection 6.0](http://www.microsoft.com/downloads/details.aspx?familyid=78dbb9cf-8a18-4f0a-8edf-f1ce0c993c63)<sup>[1]</sup>
(KB2481109)  
(Importante)
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
[**MS11-015**](http://go.microsoft.com/fwlink/?linkid=207841)
</td>
<td style="border:1px solid black;">
[**MS11-017**](http://go.microsoft.com/fwlink/?linkid=207892)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 1 e Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f9f1dde2-2219-4bf1-a497-edd011577b96)<sup>[1]</sup>
(KB2479943)  
(Critico)  
[Windows Media Center TV Pack per Windows Vista (edizioni a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=1bc240b3-1938-4350-b26f-67b81a79f8a0))<sup>[2]</sup>
(KB2494132)  
(Critico)
</td>
<td style="border:1px solid black;">
[Client Remote Desktop Connection 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=e3ea7690-386b-4cdf-889f-b3914921c56f)  
(KB2481109)  
(Importante)  
[Client Remote Desktop Connection 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=3c30f67e-7c31-4553-ba3e-e056df1bf8eb)  
(KB2483614)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e11d00df-d1cf-4a33-a1be-6721cdff5995)<sup>[1]</sup>
(KB2479943)  
(Critico)  
[Windows Media Center TV Pack per Windows Vista (edizioni a 64 bit](http://www.microsoft.com/downloads/details.aspx?familyid=cd4c5a80-db24-4696-a248-1286c3b9f550))<sup>[2]</sup>
(KB2494132)  
(Critico)
</td>
<td style="border:1px solid black;">
[Client Remote Desktop Connection 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=5735bed6-0e3d-46a4-85d0-14ec34a82edd)  
(KB2481109)  
(Importante)  
[Client Remote Desktop Connection 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=8025482b-f58f-4f5a-a133-5563c65b21f6)  
(KB2483614)  
(Importante)
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
[**MS11-015**](http://go.microsoft.com/fwlink/?linkid=207841)
</td>
<td style="border:1px solid black;">
[**MS11-017**](http://go.microsoft.com/fwlink/?linkid=207892)
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
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Client Remote Desktop Connection 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=31d790c9-92f9-4a2b-800b-8e8d2b570bb9)\*\*  
(KB2481109)  
(Importante)
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
[Client Remote Desktop Connection 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=5b0a8eb5-4bc2-4054-b952-58aa645afcf5)\*\*  
(KB2481109)  
(Importante)
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
[Client Remote Desktop Connection 6.1](http://www.microsoft.com/downloads/details.aspx?familyid=25da7e00-745d-4d98-9dd8-52a8a4340404)  
(KB2481109)  
(Importante)
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
[**MS11-015**](http://go.microsoft.com/fwlink/?linkid=207841)
</td>
<td style="border:1px solid black;">
[**MS11-017**](http://go.microsoft.com/fwlink/?linkid=207892)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=1be77daa-29b1-4dae-a87f-2cb8f7e6a305)  
(KB2479943)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows 7 per sistemi a 32 bit:  
[Client Remote Desktop Connection 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=0768a5f4-da28-4b2e-8aff-d68f890df3e6)  
(KB2483614)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=56fb24ce-65c7-4573-b613-e424ccc1a3a6)  
(KB2479943)  
(Critico)
</td>
<td style="border:1px solid black;">
Solo Windows 7 per sistemi x64:  
[Client Remote Desktop Connection 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=935adb10-1e7e-4501-b543-8247b88f6d18)  
(KB2483614)  
(Importante)
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
[**MS11-015**](http://go.microsoft.com/fwlink/?linkid=207841)
</td>
<td style="border:1px solid black;">
[**MS11-017**](http://go.microsoft.com/fwlink/?linkid=207892)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6f45658a-1db8-4ef5-b840-4d0180d4d90e)\*\*  
(KB2479943)  
(Importante)
</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 solo per sistemi x64:  
[Client Remote Desktop Connection 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=3fcb2e11-591e-484a-a992-2f1d563e6d17)\*\*  
(KB2483614)  
(Importante)
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
[Client Remote Desktop Connection 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=c29b6487-78f0-421c-810c-c5e45d6a2352)  
(KB2483614)  
(Importante)
</td>
</tr>
</table>
 
**Nota per Windows Server 2008 e Windows Server 2008 R2**

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione dell'installazione dei componenti di base del server](http://technet.microsoft.com/it-it/library/ee441255(ws.10).aspx) e [Manutenzione dell'installazione dei componenti di base del server](http://technet.microsoft.com/en-us/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Note per MS11-015**

<sup>[1]</sup>Vedere la nota <sup>[2]</sup> seguente relativa al Windows Media Center TV Pack per Windows Vista.

<sup>[2]</sup>Windows Media Center TV Pack per Windows Vista è disponibile come componente facoltativo solo nelle installazioni OEM (Original Equipment Manufacturer) delle edizioni Home Premium e Ultimate di Windows Vista. I clienti che hanno installato questo componente facoltativo nei propri sistemi devono installare entrambi gli aggiornamenti disponibili. Nel rispetto delle procedure consigliate, Microsoft consiglia di installare l'aggiornamento del sistema operativo (KB2479943) prima dell'aggiornamento del Windows Media Center TV Pack (KB2494132).

**Note per MS11-017**

<sup>[1]</sup>Questo download effettua l'aggiornamento del client Remote Desktop Connection 6.0 ad una versione del client Remote Desktop Connection 6.1 non interessata dalla vulnerabilità.

<sup>[2]</sup>Questo download effettua l'aggiornamento dell'interfaccia utente multilingue (MUI) del client Remote Desktop Connection 6.0 ad una versione dell'interfaccia utente multilingue (MUI) del client Remote Desktop Connection 6.1 non interessata dalla vulnerabilità.

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
Programmi Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-016**](http://go.microsoft.com/fwlink/?linkid=209774)
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
Microsoft Groove 2007
</td>
<td style="border:1px solid black;">
[Microsoft Groove 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=3981ab53-1082-4155-9000-11d8a976ff33)  
(KB2494047)  
(Importante)
</td>
</tr>
</table>
 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208(en-us).aspx).

**System Center Configuration Manager 2007**

La Gestione aggiornamenti software di Configuration Manager 2007 semplifica la consegna e la gestione degli aggiornamenti dei sistemi IT in tutta l'azienda. Con Configuration Manager 2007, gli amministratori IT possono consegnare gli aggiornamenti dei prodotti Microsoft a diverse periferiche compresi desktop, portatili, server e dispositivi mobili.

La valutazione automatica della vulnerabilità disponibile in Configuration Manager 2007 rileva la necessità di effettuare gli aggiornamenti ed invia relazioni sulle azioni consigliate. La Gestione aggiornamenti software di Configuration Manager 2007 si basa su Microsoft Windows Software Update Services (WSUS), un'infrastruttura di aggiornamento tempestiva conosciuta agli amministratori IT in tutto il mondo. Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare Configuration Manager 2007 per implementare gli aggiornamenti, vedere [Gestione aggiornamenti software](http://www.microsoft.com/systemcenter/en/us/configuration-manager/cm-software-update-management.aspx). Per ulteriori informazioni su Configuration Manager, visitare [System Center Configuration Manager](http://www.microsoft.com/systemcenter/en/us/configuration-manager.aspx).

**Systems Management Server 2003**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali.

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=dm;en-us;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager 2007; vedere anche la sezione precedente, **System Center Configuration Manager 2007**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/en/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f&displaylang=en). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/en-us/systemcenter/bb545936.aspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d&displaylang=en)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet.microsoft.com/it-it/library/cc766043(ws.10).aspx), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

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

-   Matthew Watchinski di [Sourcefire VRT](http://www.sourcefire.com/services/sf_vrt.html) per aver segnalato un problema descritto nel bollettino MS11-015
-   HD Moore di [Rapid 7](http://www.rapid7.com/) per aver segnalato un problema descritto nel bollettino MS11-016
-   Eyal Gruner di [Versafe Anti Fraud](http://www.versafe-login.com/) per aver segnalato un problema descritto nel bollettino MS11-017

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (8 marzo 2011): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (16 marzo 2011): È stato eliminato il riferimento errato a Windows XP Home Edition Service Pack 3 e Windows XP Tablet PC Edition Service Pack 3 nelle note per MS11-015 riportate nella sezione **Software interessato e percorsi per il download**, poiché non interessati. La modifica è esclusivamente informativa. Non sono previste modifiche ai file di aggiornamento per la protezione o per la logica di rilevamento. Microsoft consiglia di eseguire subito l'aggiornamento ai clienti che dispongono di queste edizioni di Windows XP e che non lo hanno ancora installato. I clienti che hanno già installato questo aggiornamento non devono eseguire ulteriori operazioni.

*Built at 2014-04-18T01:50:00Z-07:00*
