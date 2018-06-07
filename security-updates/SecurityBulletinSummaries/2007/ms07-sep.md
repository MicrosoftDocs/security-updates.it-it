---
TOCTitle: 'MS07-SEP'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - settembre 2007'
ms:assetid: 'ms07-sep'
ms:contentKeyID: 61240017
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms07-sep(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - settembre 2007
===================================================================

Data di pubblicazione: martedì 11 settembre 2007 | Aggiornamento: mercoledì 12 settembre 2007

**Versione:** 1.1

Questo riepilogo elenca bollettini sulla sicurezza rilasciati a settembre 2007.

Con il rilascio dei bollettini del mese di settembre 2007, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 6 settembre 2007. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://go.microsoft.com/fwlink/?linkid=21163).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 12 settembre 2007 alle 11:00 Pacific Time (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di settembre](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032344690&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il Webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i Webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Critico (1)
-----------

<span></span>
| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-051                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Microsoft Agent può consentire l'esecuzione di codice in modalità remota (938827)**](http://technet.microsoft.com/security/bulletin/ms07-051)                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello critico risolve una vulnerabilità segnalata privatamente a Microsoft. In Microsoft Agent esiste una vulnerabilità legata all'esecuzione di codice in modalità remota causata dal modo in cui vengono gestiti alcuni URL appositamente predisposti. Tale vulnerabilità può consentire a un utente malintenzionato di eseguire codice in modalità remota su un sistema interessato. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Software interessato**        | **Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

Importante (3)
--------------

<span></span>
| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-052                                                                                                                                                                                                                                                                                                                                                                                            |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Crystal Reports per Visual Studio può consentire l'esecuzione di codice in modalità remota (941522)**](http://technet.microsoft.com/security/bulletin/ms07-052)                                                                                                                                                                                                                                                  |
| **Riepilogo**                   | Questo aggiornamento importante per la protezione risolve una vulnerabilità divulgata pubblicamente. Questa vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file RPT appositamente predisposto. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                      |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer ed Enterprise Update Scan Tool, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                               |
| **Software interessato**        | **Visual Studio.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                       |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-053                                                                                                                                                                                                                                                                                                                                                               |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Windows Services for UNIX può consentire l'acquisizione di privilegi più elevati (939778)**](http://technet.microsoft.com/security/bulletin/ms07-053)                                                                                                                                                                                                                               |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello importante risolve una vulnerabilità segnalata pubblicamente a Microsoft. In Windows Services for UNIX 3.0, Windows Services for UNIX 3.5 e Subsystem for UNIX-based Applications nei quali sono in esecuzione determinati file binari setuid esiste una vulnerabilità che può consentire a un utente malintenzionato di acquisire privilegi più elevati. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                         |
| **Effetti della vulnerabilità** | Acquisizione di privilegi più elevati                                                                                                                                                                                                                                                                                                                                                                       |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer ed Enterprise Update Scan Tool, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                |
| **Software interessato**        | **Windows Services for UNIX, Subsystem for UNIX-based Applications.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                       |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-054                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in MSN Messenger e Windows Live Messenger può consentire l'esecuzione di codice in modalità remota (942099)**](http://technet.microsoft.com/security/bulletin/ms07-054)                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in MSN Messenger e Windows Live Messenger. La vulnerabilità può consentire l'esecuzione di codice in modalità remota quando un utente accetta un invito di chat video o tramite webcam da un utente malintenzionato. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere pieno controllo del sistema interessato. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Rilevamento**                 | Questi prodotti forniscono funzionalità integrate per il rilevamento e la distribuzione automatici degli aggiornamenti. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Software interessato**        | **MSN Messenger, Windows Live Messenger.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

Software interessato e posizioni per il download
------------------------------------------------

<span></span>
**Come utilizzare questa tabella**

È possibile utilizzare questa tabella per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se è necessario applicare i relativi aggiornamenti per la protezione. Per ogni programma o componente elencato sono riportati l'effetto della vulnerabilità e un collegamento al relativo aggiornamento.

**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.

**Software interessato e posizioni per il download**

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
Dettagli        
</th>
<th style="border:1px solid black;" >
Dettagli        
</th>
<th style="border:1px solid black;" >
Dettagli        
</th>
<th style="border:1px solid black;" >
Dettagli        
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS07-051**](http://technet.microsoft.com/security/bulletin/ms07-051)
</td>
<td style="border:1px solid black;">
[**MS07-052**](http://technet.microsoft.com/security/bulletin/ms07-052)
</td>
<td style="border:1px solid black;">
[**MS07-053**](http://technet.microsoft.com/security/bulletin/ms07-053)
</td>
<td style="border:1px solid black;">
[**MS07-054**](http://technet.microsoft.com/security/bulletin/ms07-054)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo**
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<th colspan="5">
Sistemi operativi Windows
</th>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=7cd248ed-d154-4dce-89ef-ceefd2700965)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 1
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<th colspan="5">
Componenti del sistema operativo Windows
</th>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Services for UNIX 3.0 in Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=557f89fc-c5d9-4405-9007-1654abf92277)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Services for UNIX 3.5 in Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=70ae23c2-3ae8-4ea6-ba8d-8ac7e4f82663)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Services for UNIX 3.0 in Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=557f89fc-c5d9-4405-9007-1654abf92277)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Services for UNIX 3.0 in Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=70ae23c2-3ae8-4ea6-ba8d-8ac7e4f82663)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Services for UNIX 3.0 in Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=557f89fc-c5d9-4405-9007-1654abf92277)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Services for UNIX 3.5 in Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=70ae23c2-3ae8-4ea6-ba8d-8ac7e4f82663)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Subsystem for UNIX-based Applications in Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=8ab5cc43-0b9c-45eb-aa51-47568ab6ce3f)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Subsystem for UNIX-based Applications in Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=1d21e3e8-b5f6-4044-9db6-054af836492b)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Subsystem for UNIX-based Applications in Windows Vista
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=4d52e4f4-2888-42df-8163-85c648e65b29)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Subsystem for UNIX-based Applications in Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=4be667cc-c239-480b-a9a0-939bcd27f0de)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<th colspan="5">
Piattaforme e strumenti di sviluppo
</th>
</tr>
<tr>
<td style="border:1px solid black;">
Visual Studio .NET 2002 Service Pack 1  
(KB937057)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=2608c83b-e1b2-4449-9a0e-1e566aac3d76)**<sup>[2]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Visual Studio .NET 2003  
(KB937058)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=d612ad41-5a0d-4e13-99ea-d6a5589786d6)**<sup>[2]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Visual Studio .NET 2003 Service Pack 1  
(KB937059)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=0b10b04b-932c-4bff-9cbc-b3eeb15064b1)**<sup>[2]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Visual Studio 2005  
(KB937060)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=21073cc2-919c-40df-8ebb-aa3db06050d2)**<sup>[2]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Visual Studio 2005 Service Pack 1  
(KB937061)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=967d43c8-efba-4221-beb0-981e7deef33a)**<sup>[2]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<th colspan="5">
Altri prodotti interessati
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
MSN Messenger 6.2 in Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=cf49c56c-8b3e-4eae-9904-9505f47bed45&displaylang=en)**<sup>[3]</sup>**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
MSN Messenger 7.0 in Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=cf49c56c-8b3e-4eae-9904-9505f47bed45&displaylang=en)**<sup>[3]</sup>**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
MSN Messenger 6.2 in Windows XP Service Pack 2, Windows XP Professional x64 Edition, Windows XP Professional x64 Edition Service Pack 2, Windows Server 2003 Service Pack 1, Windows Server 2003 Service Pack 2, Windows Server 2003 x64 Edition, Windows Server 2003 x64 Edition Service Pack 2, Windows Vista e Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=d78f2ff1-79ea-4066-8ba0-ddbed94864fc&displaylang=en)**<sup>[3]</sup>**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
MSN Messenger 7.0 in Windows XP Service Pack 2, Windows XP Professional x64 Edition, Windows XP Professional x64 Edition Service Pack 2, Windows Server 2003 Service Pack 1, Windows Server 2003 Service Pack 2, Windows Server 2003 x64 Edition, Windows Server 2003 x64 Edition Service Pack 2, Windows Vista e Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=d78f2ff1-79ea-4066-8ba0-ddbed94864fc&displaylang=en)**<sup>[3]</sup>**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
MSN Messenger 7.5 in Windows XP Service Pack 2, Windows XP Professional x64 Edition, Windows XP Professional x64 Edition Service Pack 2, Windows Server 2003 Service Pack 1, Windows Server 2003 Service Pack 2, Windows Server 2003 x64 Edition, Windows Server 2003 x64 Edition Service Pack 2, Windows Vista e Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=d78f2ff1-79ea-4066-8ba0-ddbed94864fc&displaylang=en)**<sup>[3]</sup>**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Live Messenger 8.0 in Windows XP Service Pack 2, Windows XP Professional x64 Edition, Windows XP Professional x64 Edition Service Pack 2, Windows Server 2003 Service Pack 1, Windows Server 2003 Service Pack 2, Windows Server 2003 x64 Edition, Windows Server 2003 x64 Edition Service Pack 2, Windows Vista e Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=d78f2ff1-79ea-4066-8ba0-ddbed94864fc&displaylang=en)**<sup>[3]</sup>**
</td>
</tr>
</table>
 
**Note**

**<sup>[1]</sup>** È disponibile un aggiornamento per la protezione per questo sistema operativo. Per ulteriori dettagli, vedere il software o il componente interessato nella tabella e consultare il relativo bollettino sulla sicurezza.** **

**<sup>[2]</sup>** Non tutte le edizioni di questa versione di Visual Studio sono interessate. Vedere il bollettino sulla sicurezza appropriato per un elenco specifico di edizioni interessate.** **

**<sup>[3]</sup>** Per questo software, è anche possibile eseguire un aggiornamento in linea dal servizio MSN Messenger o Windows Live Messenger. Per ulteriori informazioni, vedere il relativo bollettino sulla sicurezza.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://msdn2.microsoft.com/it-it/embedded/aa731232.aspx3). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it), [Windows Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Office Update.](http://office.microsoft.com/it-it/downloads/default.aspx) Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security_patch) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "security\_patch". Infine, gli aggiornamenti per la protezione possono essere scaricati dal catalogo di Windows Update. Per ulteriori informazioni sul catalogo di Windows Update, vedere l'[articolo della Microsoft Knowledge Base 323166](http://support.microsoft.com/kb/323166).

**Informazioni sul rilevamento e sulla distribuzione**

Per gli aggiornamenti per la protezione di questo mese Microsoft ha fornito informazioni sul rilevamento e sulla distribuzione. Tali informazioni consentono inoltre ai professionisti IT di apprendere come utilizzare diversi strumenti per distribuire gli aggiornamenti per la protezione, quali Windows Update, Microsoft Update, Office Update, Microsoft Baseline Security Analyzer (MBSA), Office Detection Tool, Microsoft Systems Management Server (SMS), Extended Security Update Inventory Tool ed Enterprise Update Scan Tool (EST). Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 910723](http://support.microsoft.com/kb/910723).

**Microsoft Baseline Security Analyzer ed** **Enterprise** **Update Scan Tool**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134).

Se MBSA 1.2.1 non supporta il rilevamento di uno specifico aggiornamento per la protezione, Microsoft rilascia una versione di Enterprise Update Scan Tool (EST) per tale aggiornamento. Per ulteriori informazioni su EST, visitare la pagina Web di [Enterprise Update Scan Tool.](http://support.microsoft.com/default.aspx?id=894193)

**Nota** Dopo il 9 ottobre 2007, il file MSSecure.XML utilizzato da MBSA 1.2.1 non verrà più aggiornato. Dopo questa data, non verranno aggiunti nuovi aggiornamenti per la protezione al file MSSecure.XML utilizzato da MBSA 1.2.1 e non verranno rilasciate nuove versioni di Enterprise Scan Tool. Per ulteriori informazioni, visitare il sito Web [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=50120).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. Per ulteriori informazioni sull'utilizzo di SMS 2003 per la distribuzione degli aggiornamenti per la protezione, visitare il sito [Gestione delle patch per la protezione con SMS 2003](http://go.microsoft.com/fwlink/?linkid=22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://go.microsoft.com/fwlink/?linkid=33340) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://go.microsoft.com/fwlink/?linkid=33341). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://go.microsoft.com/fwlink/?linkid=33387) e in [SMS 2.0 Administration Feature Pack](http://go.microsoft.com/fwlink/?linkid=21161).

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per questo mese:

-   Microsoft non ha rilasciato aggiornamenti **non correlati alla protezione** e ad alta priorità su Microsoft Update (MU) e Windows Server Update Services (WSUS).
-   Microsoft non ha rilasciato aggiornamenti **non correlati alla protezione** e ad alta priorità per Windows su Windows Update (WU).

Tenere presente che queste informazioni riguardano **soltanto** gli aggiornamenti **non correlati alla protezione** e ad alta-priorità su Microsoft Update, Windows Update e Windows Server Update Services rilasciati lo stesso giorno del riepilogo dei bollettini sulla sicurezza. **Non** vengono fornite informazioni sugli aggiornamenti **non correlati alla protezione** rilasciati in altri giorni.

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione delle patch](http://go.microsoft.com/fwlink/?linkid=21168).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security_patch) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "security\_patch".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://go.microsoft.com/fwlink/?linkid=21164).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Il Vulnerability Research Team di [Assurent Secure Technologies](http://www.assurent.com/) per aver segnalato un problema descritto nel bollettino [MS07-051](http://technet.microsoft.com/security/bulletin/ms07-051)
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino [MS07-051](http://technet.microsoft.com/security/bulletin/ms07-051)
-   Un ricercatore anonimo che collabora con [iDefense VCP](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino [MS07-051](http://technet.microsoft.com/security/bulletin/ms07-051).
-   Brian A. Reiter di WolfeReiter per aver collaborato con noi su un problema descritto nel bollettino [MS07-053](http://technet.microsoft.com/security/bulletin/ms07-053)
-   Woo Shi di [team 509](http://www.team509.com/) per aver segnalato un problema descritto nel bollettino [MS07-054](http://technet.microsoft.com/security/bulletin/ms07-054)

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://go.microsoft.com/fwlink/?linkid=21131). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://go.microsoft.com/fwlink/?linkid=21155).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (11 settembre 2007): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (12 settembre 2007): Modificate le informazioni sulla necessità di riavvio e aggiunti collegamenti per il download per il bollettino MS07-045.

*Built at 2014-04-18T01:50:00Z-07:00*
