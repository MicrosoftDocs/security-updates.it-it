---
TOCTitle: 'MS10-MAY'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - maggio 2010'
ms:assetid: 'ms10-may'
ms:contentKeyID: 61240050
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms10-may(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - maggio 2010
================================================================

Data di pubblicazione: martedì 11 maggio 2010 | Aggiornamento: mercoledì 19 maggio 2010

**Versione:** 1.2

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a maggio 2010.

Con il rilascio dei bollettini del mese di maggio 2010, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 6 maggio 2010. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 12 maggio 2010 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di maggio](http://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032427724&culture=en-us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

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
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-030">MS10-030</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Outlook Express e Windows Mail può consentire l'esecuzione di codice in modalità remota (978542)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Outlook Express, Windows Mail e Windows Live Mail. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visita un server di posta elettronica dannoso. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms10-031">MS10-031</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Visual Basic, Applications Edition, può consentire l'esecuzione di codice in modalità remota (978213)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Visual Basic, Applications Edition. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un'applicazione host apre e inoltra un file appositamente predisposto a Visual Basic, Applications Edition. Se un utente è connesso con privilegi di amministrazione, un utente malintenzionato che sfrutti questa vulnerabilità può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office, Microsoft Visual Basic, Applications Edition</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità sono elencate in ordine decrescente sulla base del livello di valutazione del rischio e quindi del codice CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).
  
| ID bollettino                                                       | Titolo della vulnerabilità                                                             | ID CVE                                                                           | Valutazione dell'Exploitability Index                                                                                | Note fondamentali                                                                                                     |  
|---------------------------------------------------------------------|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|  
| [MS10-031](http://technet.microsoft.com/security/bulletin/ms10-031) | Vulnerabilità legata al danneggiamento della memoria stack in VBE6.DLL                 | [CVE-2010-0815](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0815) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità | (Nessuna)                                                                                                             |  
| [MS10-030](http://technet.microsoft.com/security/bulletin/ms10-030) | Vulnerabilità legata all'overflow dei valori integer in Outlook Express e Windows Mail | [CVE-2010-0816](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-0816) | [**2**](http://technet.microsoft.com/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità | Lo sfruttamento di Windows Vista e di sistemi operativi successivi è meno probabile grazie ai fattori attenuanti heap |
  
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
</tr>
<tr>
<th colspan="2">
Microsoft Windows 2000  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-030**](http://technet.microsoft.com/security/bulletin/ms10-030)
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
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 5.5 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=661f5de3-a593-4961-8e8d-2777797eb5c5)  
(KB978542)  
(Critico)  
[Microsoft Outlook Express 6 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=cda75174-b535-4559-a52d-b5ec3a1df349)  
(KB978542)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Windows XP
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-030**](http://technet.microsoft.com/security/bulletin/ms10-030)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=99707c3d-a3cb-47da-b38e-8ae0227fd703)  
(KB978542)  
(Critico)  
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=99707c3d-a3cb-47da-b38e-8ae0227fd703)<sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=44bc97bb-6f76-4c96-af72-69daaea80fff)  
(KB978542)  
(Critico)  
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=44bc97bb-6f76-4c96-af72-69daaea80fff)<sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Windows Server 2003
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-030**](http://technet.microsoft.com/security/bulletin/ms10-030)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
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
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=eb9742fc-0934-4b38-9ec4-3597fc71ec00)  
(KB978542)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=5678515a-97ea-4e00-8700-d3f2fcdc0efc)  
(KB978542)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Microsoft Outlook Express 6](http://www.microsoft.com/downloads/details.aspx?familyid=60ef635b-cb6d-402f-b904-e69b519d797f)  
(KB978542)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Windows Vista
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-030**](http://technet.microsoft.com/security/bulletin/ms10-030)
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
Windows Vista Service Pack 1 e Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Mail](http://www.microsoft.com/downloads/details.aspx?familyid=a970c869-24fe-4ef4-b189-7a6bac2411f1)  
(KB978542)  
(Critico)  
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=a970c869-24fe-4ef4-b189-7a6bac2411f1)<sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 1 e Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Mail](http://www.microsoft.com/downloads/details.aspx?familyid=9a7853b5-4f9f-4467-9530-eea2efd504a5)  
(KB978542)  
(Critico)  
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=9a7853b5-4f9f-4467-9530-eea2efd504a5)<sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Windows Server 2008
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-030**](http://technet.microsoft.com/security/bulletin/ms10-030)
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
Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Mail](http://www.microsoft.com/downloads/details.aspx?familyid=5f77a640-247c-4ed2-9fca-4b7344f4dc7c)\*\*  
(KB978542)  
(Critico)  
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=5f77a640-247c-4ed2-9fca-4b7344f4dc7c)\*\*<sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Mail](http://www.microsoft.com/downloads/details.aspx?familyid=b0eab011-5847-44e4-bc0d-5c5355e1e8d0)\*\*  
(KB978542)  
(Critico)  
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=b0eab011-5847-44e4-bc0d-5c5355e1e8d0)\*\*<sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium e Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Mail](http://www.microsoft.com/downloads/details.aspx?familyid=da01ae82-895e-4739-916f-a63b9095a076)  
(KB978542)  
(Critico)  
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=da01ae82-895e-4739-916f-a63b9095a076)<sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Windows 7
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-030**](http://technet.microsoft.com/security/bulletin/ms10-030)
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
Windows 7 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=1f0c17be-ba4c-4a1c-b9c3-8ac368800947)<sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=a70f15e1-512c-44ca-a308-928e237ac0ce)<sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Windows Server 2008 R2
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-030**](http://technet.microsoft.com/security/bulletin/ms10-030)
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
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=e2e25c02-38ce-4868-a01a-39fc7d2a4150)\*\* <sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Live Mail](http://www.microsoft.com/downloads/details.aspx?familyid=53ed1055-b5ee-4fde-9550-f8b401916467)<sup>[1]</sup>
(KB978542)  
(Importante)
</td>
</tr>
</table>
 
**Nota per Windows Server 2008 e Windows Server 2008 R2**

**\*\*Le installazioni di Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2 come indicato, se sono state installate mediante l'opzione di installazione Server Core. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli MSDN, [Server Core](http://msdn.microsoft.com/library/ms723891(vs.85).aspx) e [Server Core per Windows Server 2008 R2](http://msdn.microsoft.com/en-us/library/ee391631(vs.85).aspx). Si noti che l'opzione di installazione Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**Nota per MS10-030**

<sup>[1]</sup>Windows Live Mail è un componente preconfigurato su questo sistema operativo e deve essere installato separatamente perché si verifichi una vulnerabilità.

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
[**MS10-031**](http://technet.microsoft.com/security/bulletin/ms10-031)
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
Microsoft Office XP
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=72c23b0f-4e24-4334-bc8a-334adc8bc42b)<sup>[1]</sup>
(KB976380)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f8eac9bc-8389-4ac8-8b29-9a8180d9fd34)<sup>[1]</sup>
(KB976382)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office System 2007
</td>
<td style="border:1px solid black;">
[Microsoft Office System Service 2007 Pack 1 e Microsoft Office System 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=160ad53e-6475-4550-90c2-444e4abea730)<sup>[1]</sup>
(KB976321)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS10-031**

<sup>[1]</sup>Questi aggiornamenti per Microsoft Office interessano tutte le applicazioni Microsoft Office supportate e altro software Microsoft Office contenente il componente Office vulnerabile condiviso. Questo include, ma non solo, le versioni supportate di Microsoft Office Visio e Microsoft Office Project.

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Microsoft Visual Basic for Applications
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-031**](http://technet.microsoft.com/security/bulletin/ms10-031)
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
Microsoft Visual Basic for Applications
</td>
<td style="border:1px solid black;">
[Microsoft Visual Basic for Applications](http://www.microsoft.com/downloads/details.aspx?familyid=436a8a66-352e-44d1-a610-c825083ad24a)<sup>[1]</sup>
(KB974945)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Basic for Applications SDK
</td>
<td style="border:1px solid black;">
Microsoft Visual Basic for Applications SDK<sup>[2]</sup><sup>[3]</sup>
(Critico)
</td>
</tr>
</table>
 
**Nota per MS10-031**

<sup>[1]</sup>Questo pacchetto di aggiornamento interessa le versioni supportate del runtime di Microsoft Visual Basic, Applications Edition (Vbe6.dll) ed è disponibile soltanto nell'Area download Microsoft.

<sup>[2]</sup>Le versioni supportate di VBA SDK sono Microsoft Visual Basic for Applications SDK 6.3, Microsoft Visual Basic for Applications SDK 6.4 e Microsoft Visual Basic for Applications SDK 6.5.

<sup>[3]</sup>La versione aggiornata di Visual Basic for Applications SDK che risolve la vulnerabilità descritta in questo bollettino è disponibile per i fornitori di software indipendenti (ISV) dalla [Summit Software Company](http://www.summsoft.com/).

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

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

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://go.microsoft.com/fwlink/?linkid=22939). Gli utenti di SMS 2.0 possono inoltre utilizzare Security Update Inventory Tool per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

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

-   Francis Provencher di Protek Research Lab per aver segnalato un problema descritto nel bollettino MS10-030
-   [NSFocus Security Team](http://www.nsfocus.com/) per aver segnalato un problema descritto nel bollettino MS10-031

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://www.microsoft.com/italy/athome/security/support/default.mspx). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/default.aspx?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (11 maggio 2010): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (12 maggio 2010): Sono stati corretti i requisiti di riavvio in MS10-030.
-   V1.2 (19 maggio 2010): Sono stati rimossi i riferimenti non corretti nel bollettino MS10-030 a Windows Mail se installato in Windows 7 e Windows Server 2008 R2. Inoltre, è stata aggiunta una nota al software interessato nel bollettino MS10-031 per chiarire che gli aggiornamenti per Microsoft Office interessano tutte le applicazioni Microsoft Office supportate e altro software Microsoft Office contenente una versione vulnerabile di VBE6.dll.

*Built at 2014-04-18T01:50:00Z-07:00*
