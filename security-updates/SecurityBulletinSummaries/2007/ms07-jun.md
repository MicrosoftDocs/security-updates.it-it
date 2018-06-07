---
TOCTitle: 'MS07-JUN'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - giugno 2007'
ms:assetid: 'ms07-jun'
ms:contentKeyID: 61240012
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms07-jun(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - giugno 2007
================================================================

Data di pubblicazione: martedì 12 giugno 2007

**Versione:** 1.0

Questo riepilogo elenca bollettini sulla sicurezza rilasciati a giugno 2007.

Con il rilascio dei bollettini di giugno 2007, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 7 giugno 2007. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, è possibile sottoscrivere il [servizio di notifica sulla sicurezza Microsoft](http://go.microsoft.com/fwlink/?linkid=21163).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini mercoledì 13 giugno 2007 alle 11:00 Pacific Time (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di giugno](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032327013&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il Webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i Webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Critico (4)
-----------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-031                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**La vulnerabilità nel pacchetto di protezione Schannel in Windows può consentire l'esecuzione di codice in modalità remota (935840)**](http://technet.microsoft.com/security/bulletin/ms07-031)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Riepilogo**                   | Questo aggiornamento critico per la protezione risolve una vulnerabilità segnalata privatamente nel pacchetto di protezione Canale sicuro (Schannel) in Windows. Il pacchetto di protezione Schannel consente di implementare i protocolli di autenticazione standard per Internet, SSL (Secure Sockets Layer) e TLS (Transport Layer Security). Questa vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre una pagina Web appositamente predisposta utilizzando un browser Web di Internet o utilizza un'applicazione che prevede SSL/TLS. Tuttavia, i tentativi di sfruttare questa vulnerabilità causano in genere solo la chiusura del browser Web di Internet o dell'applicazione. Non è possibile connettersi alle risorse o ai siti Web tramite SSL o TLS fino al riavvio del sistema. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Software interessato**        | **Windows**. Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-033                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Aggiornamento cumulativo per la protezione di Internet Explorer (933566)**](http://technet.microsoft.com/security/bulletin/ms07-033)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Riepilogo**                   | Questo aggiornamento critico per la protezione risolve cinque vulnerabilità segnalate privatamente e una divulgata pubblicamente. Tutte queste vulnerabilità tranne una possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Una vulnerabilità può consentire lo spoofing e utilizza anche una pagina Web appositamente predisposta. In tutti i casi di esecuzione di codice in modalità remota, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. Nel caso di spoofing, è necessaria l'interazione dell'utente per sfruttare la vulnerabilità. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Software interessato**        | **Windows, Internet Explorer**. Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-034                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Aggiornamento cumulativo per la protezione di Outlook Express e Windows Mail (929123)**](http://technet.microsoft.com/security/bulletin/ms07-034)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Riepilogo**                   | Questo aggiornamento critico per la protezione risolve due vulnerabilità segnalate privatamente e due divulgate pubblicamente. Una di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza un messaggio di posta elettronica appositamente predisposto con Windows Mail in Windows Vista. Le altre vulnerabilità possono consentire l'intercettazione di informazioni personali se un utente visita una pagina Web appositamente predisposta con Internet Explorer e non può essere direttamente sfruttata in Outlook Express. Per le vulnerabilità legate all'intercettazione di informazioni personali, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer ed Enterprise Scan Tool, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Software interessato**        | **Windows, Outlook Express, Windows Mail**. Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-035                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità nell'API Win32 può consentire l'esecuzione di codice in modalità remota (935839)**](http://technet.microsoft.com/security/bulletin/ms07-035)                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Riepilogo**                   | Questo aggiornamento critico per la protezione risolve una vulnerabilità segnalata privatamente nell'API Win32. Questa vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota o l'acquisizione di privilegi più elevati se l'API interessata viene utilizzata localmente da un'applicazione appositamente predisposta. Di conseguenza, le applicazioni che utilizzano questo componente dell'API Win32 possono essere utilizzate per sfruttare la vulnerabilità. Ad esempio, Internet Explorer utilizza questa funzione dell'API Win32 quando effettua l'analisi di pagine Web appositamente predisposte. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Software interessato**        | **Windows**. Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

Importante (1)
--------------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-030                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità in Microsoft Visio possono consentire l'esecuzione di codice in modalità remota (927051)**](http://technet.microsoft.com/security/bulletin/ms07-030)                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Riepilogo**                   | Questo importante aggiornamento per la protezione risolve due vulnerabilità fornite tramite segnalazione responsabile e privata, nonché altri problemi di protezione identificati durante la ricerca. Le vulnerabilità segnalate privatamente potrebbero consentire l'esecuzione di codice in modalità remota se un utente apre un file di Visio appositamente predisposto. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. Per poter sfruttare queste vulnerabilità è necessaria l'interazione dell'utente. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Software interessato**        | **Office, Visio**. Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

Moderato (1)
------------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-032                                                                                                                                                                                                                                                                                                                       |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Windows Vista può consentire l'intercettazione di informazioni personali (931213)**](http://technet.microsoft.com/security/bulletin/ms07-032)                                                                                                                                                                                               |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello moderato risolve una vulnerabilità segnalata privatamente a Microsoft. Questa vulnerabilità può consentire agli utenti che non dispongono di adeguati privilegi di accedere ad archivi di dati sugli utenti locali incluse le password amministrative contenute nel Registro di sistema e nel file system locale. |
| **Livello di gravità massimo**  | [Moderato](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                   |
| **Effetti della vulnerabilità** | Intercettazione di informazioni personali                                                                                                                                                                                                                                                                                                                           |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                         |
| **Software interessato**        | **Windows**. Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                        |

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
[**MS07-030**](http://technet.microsoft.com/security/bulletin/ms07-030)
</td>
<td style="border:1px solid black;">
[**MS07-031**](http://technet.microsoft.com/security/bulletin/ms07-031)
</td>
<td style="border:1px solid black;">
[**MS07-032**](http://technet.microsoft.com/security/bulletin/ms07-032)
</td>
<td style="border:1px solid black;">
[**MS07-033**](http://technet.microsoft.com/security/bulletin/ms07-033)
</td>
<td style="border:1px solid black;">
[**MS07-034**](http://technet.microsoft.com/security/bulletin/ms07-034)
</td>
<td style="border:1px solid black;">
[**MS07-035**](http://technet.microsoft.com/security/bulletin/ms07-035)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità massimo**
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<th colspan="7">
Software Windows interessato
</th>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=5b8e728c-cb9f-4176-93a0-bf42d6387f93)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=3918ac76-ebb6-4886-9a9e-808eafb96b1b)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=8615e6f3-415b-4c23-ba52-7eef70a11d77)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=27c7f1b9-2d1d-40cb-ad7e-bfedb6156a9c)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=7e994340-c616-4f66-845b-7eaf095e968a)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=0ba12191-1e6f-443b-9150-7ab8b2deb7c2)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=7e994340-c616-4f66-845b-7eaf095e968a)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=0ba12191-1e6f-443b-9150-7ab8b2deb7c2)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 1
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=39e6c6d2-7e6f-4992-a731-36f44fe2d87f)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=d554dff4-bcfb-4bbc-8fa0-af2f939d2610)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=39e6c6d2-7e6f-4992-a731-36f44fe2d87f)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=d554dff4-bcfb-4bbc-8fa0-af2f939d2610)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=da424772-079c-4351-9759-8886e0f1ba79)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=170473d8-6bb1-4fbd-8494-a059dbfdf182)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=da424772-079c-4351-9759-8886e0f1ba79)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=170473d8-6bb1-4fbd-8494-a059dbfdf182)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP1 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=028592ff-2b69-472e-b186-bd2cc76bdfa4)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=f5e45e3c-4cac-41a5-99f7-42c2c2c73e99)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=028592ff-2b69-472e-b186-bd2cc76bdfa4)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=f5e45e3c-4cac-41a5-99f7-42c2c2c73e99)
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
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=cdf79d00-6f34-404b-8ad5-a2801ff35443)
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
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
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=89dde3f4-4123-4c97-86d8-00a83462c34b)
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<th colspan="7">
Componenti di Windows interessati dalla vulnerabilità
</th>
</tr>
<tr>
<td style="border:1px solid black;">
Internet Explorer 5.01 Service Pack 4 in Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=3b49f1ed-abe3-4dbd-a91d-973415658f6b)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Internet Explorer 6 Service Pack 1 in Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=5c958650-28d2-4dd0-96a8-dbfe79ce3f68)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Internet Explorer 6 per Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=60fb294e-a8e1-405e-a289-2d2723edf7ee)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Internet Explorer 6 per Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=086d6d6e-4703-4c6c-a7af-b6dafeeede5d)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Internet Explorer 6 per Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=7ed19127-5c2d-48e4-a8d1-090dc69fd68b)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Internet Explorer 6 per Windows Server 2003 x64 Edition Service Pack 1 e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=1449eb5d-6e4c-4332-8cb6-ab9ee59c9a95)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Internet Explorer 6 per Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=b628a3cc-a70c-478a-a10c-eee254ee34ab)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Internet Explorer 7 per Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=c2191703-8cbd-4959-9f84-e13f21173926)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Internet Explorer 7 per Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=69c526b8-8b07-42bc-9bed-e18deae21c8e)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Internet Explorer 7 per Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=a074d9c0-1fed-4753-845e-073cfce99f45)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Internet Explorer 7 per Windows Server 2003 x64 Edition Service Pack 1 e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=744acb43-64da-48cc-ae69-9386b597eabc)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Internet Explorer 7 per Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=069c1560-b5e5-4dfe-a18d-e0507d406028)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Internet Explorer 7 in Windows Vista
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=77287386-48eb-4aa9-9537-626a3093aaf7)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Internet Explorer 7 in Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=77287386-48eb-4aa9-9537-626a3093aaf7)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Outlook Express 6 per Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=27cca556-0872-4803-b610-4c895ceb99aa)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Outlook Express 6 in Windows XP Professional x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=1ea813bf-bddb-40f0-8960-b9debc8413e7)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Outlook Express 6 per Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=1ea813bf-bddb-40f0-8960-b9debc8413e7)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Outlook Express 6 in Windows Server 2003 Service Pack 1
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Basso](http://www.microsoft.com/downloads/details.aspx?familyid=93808a74-035c-4ab7-9283-c693d7bd82be)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Outlook Express 6 per Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Basso](http://www.microsoft.com/downloads/details.aspx?familyid=93808a74-035c-4ab7-9283-c693d7bd82be)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Outlook Express 6 in Windows Server 2003 x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=f63323a9-e285-45e5-84bd-71ae9da126e3)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Outlook Express 6 per Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=f63323a9-e285-45e5-84bd-71ae9da126e3)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Outlook Express 6 in Windows Server 2003 con SP1 per i sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Basso](http://www.microsoft.com/downloads/details.aspx?familyid=2e62e96e-6571-437d-a612-99175ac39025)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Outlook Express 6 in Windows Server 2003 con SP2 per i sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Basso](http://www.microsoft.com/downloads/details.aspx?familyid=2e62e96e-6571-437d-a612-99175ac39025)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Mail in Windows Vista
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=ee57de19-44ea-48f2-ae28-e76fd2018633)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Mail in Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=343db20f-7794-4423-b11d-885329fbdf78)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<th colspan="7">
Software Office interessato
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Visio 2002 Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=fc1d0483-27e8-4541-b81d-4a47973bea30)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Visio 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=c47f432e-8538-42fd-92c9-7e0f1d643e8e)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
</table>
 
**Note**

**<sup>[1]</sup>** È disponibile un aggiornamento per la protezione per questo sistema operativo. Per ulteriori dettagli, vedere il software o il componente interessato nella tabella e consultare il relativo bollettino sulla sicurezza.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://go.microsoft.com/fwlink/?linkid=69903). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it), [Windows Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Office Update.](http://office.microsoft.com/it-it/downloads/default.aspx) Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security_patch) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "security\_patch". Infine, gli aggiornamenti per la protezione possono essere scaricati dal catalogo di Windows Update. Per ulteriori informazioni sul catalogo di Windows Update, vedere l'[articolo della Microsoft Knowledge Base 323166](http://support.microsoft.com/kb/323166).

**Informazioni sul rilevamento e sulla distribuzione**

Per gli aggiornamenti per la protezione di questo mese Microsoft ha fornito informazioni sul rilevamento e sulla distribuzione. Tali informazioni consentono inoltre ai professionisti IT di apprendere come utilizzare diversi strumenti per distribuire gli aggiornamenti per la protezione, quali Windows Update, Microsoft Update, Office Update, Microsoft Baseline Security Analyzer (MBSA), Office Detection Tool, Microsoft Systems Management Server (SMS), Extended Security Update Inventory Tool ed Enterprise Update Scan Tool (EST). Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 910723](http://support.microsoft.com/kb/910723).

**Microsoft Baseline Security Analyzer ed** **Enterprise** **Update Scan Tool**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134).

Se MBSA 1.2.1 non supporta il rilevamento di uno specifico aggiornamento per la protezione, Microsoft rilascia una versione di Enterprise Update Scan Tool (EST) per tale aggiornamento. Per ulteriori informazioni su EST, visitare la pagina Web di [Enterprise Update Scan Tool.](http://support.microsoft.com/default.aspx?id=894193)

**Nota** Dopo il 9 ottobre 2007, il file MSSecure.XML utilizzato da MBSA 1.2.1 non verrà più aggiornato. Dopo questa data, non verranno aggiunti nuovi aggiornamenti per la protezione al file MSSecure.XML utilizzato da MBSA 1.2.1 e non verranno rilasciate nuove versioni di Enterprise Scan Tool. Per ulteriori informazioni, visitare il sito Web [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134).

**Software Update Services**

Microsoft Software Update Services (SUS) consente agli amministratori di eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione sia nei server basati su Windows 2000 e Windows Server 2003 sia nei computer desktop che eseguono Windows 2000 Professional o Windows XP Professional.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Software Update Services, visitare il sito [Software Update Services](http://go.microsoft.com/fwlink/?linkid=21133).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://go.microsoft.com/fwlink/?linkid=50120).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. Per ulteriori informazioni sull'utilizzo di SMS 2003 per la distribuzione degli aggiornamenti per la protezione, visitare il sito [Gestione delle patch per la protezione con SMS 2003](http://go.microsoft.com/fwlink/?linkid=22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://go.microsoft.com/fwlink/?linkid=33340) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://go.microsoft.com/fwlink/?linkid=33341). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://go.microsoft.com/fwlink/?linkid=33387) e in [SMS 2.0 Administration Feature Pack](http://go.microsoft.com/fwlink/?linkid=21161).

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

Tenere presente che questo strumento **non** è distribuito tramite Software Update Services (SUS).

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU, WSUS e SUS

Per questo mese:

-   Microsoft ha rilasciato sette aggiornamenti **non correlati alla protezione** e ad alta priorità su Microsoft Update (MU) e Windows Server Update Services (WSUS).
-   Microsoft non ha rilasciato alcun aggiornamento **non correlato alla protezione** e ad alta priorità per Windows su Windows Update (WU) e Software Update Services (SUS).

Tenere presente che queste informazioni riguardano **soltanto** gli aggiornamenti **non correlati alla protezione** e ad alta-priorità su Microsoft Update, Windows Update, Windows Server Update Services e Software Update Services rilasciati lo stesso giorno del riepilogo dei bollettini sulla sicurezza. **Non** vengono fornite informazioni sugli aggiornamenti **non correlati alla protezione** rilasciati in altri giorni.

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione delle patch](http://go.microsoft.com/fwlink/?linkid=21168).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security_patch) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "security\_patch".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Zone Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://go.microsoft.com/fwlink/?linkid=21164).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Un ricercatore anonimo che collabora con [iDefense VCP](http://idefense.com/) per aver segnalato un problema descritto nel bollettino [MS07-033](http://technet.microsoft.com/security/bulletin/ms07-033).
-   Tom Cross di [ISS](http://www.iss.net/) per aver collaborato con Microsoft su un problema descritto nel bollettino [MS07-033](http://technet.microsoft.com/security/bulletin/ms07-033).
-   Un ricercatore anonimo che collabora con [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino [MS07-033](http://technet.microsoft.com/security/bulletin/ms07-033).
-   Sam Thomas, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino [MS07-033](http://technet.microsoft.com/security/bulletin/ms07-033).
-   Will Dorman di [CERT/CC](http://www.cert.org/certcc.html) per aver segnalato un problema descritto nel bollettino [MS07-033](http://technet.microsoft.com/security/bulletin/ms07-033).
-   cocoruder di [Fortinet Security Research](http://www.fortinet.com/) per aver collaborato con noi su un problema descritto nel bollettino [MS07-033](http://technet.microsoft.com/security/bulletin/ms07-033).
-   Billy Rios per aver segnalato un problema descritto nel bollettino [MS07-035](http://technet.microsoft.com/security/bulletin/ms07-035).
-   Thomas Lim di [COSEINC](http://www.coseinc.com/) per aver segnalato un problema descritto nel bollettino [MS07-031](http://technet.microsoft.com/security/bulletin/ms07-031).
-   [SANS ISC](http://isc.sans.org/) per aver collaborato con noi su un problema descritto nel bollettino [MS07-034](http://technet.microsoft.com/security/bulletin/ms07-034).
-   Yosuke Hasegawa di [WebAppSec.JP](https://www.webappsec.jp/) per aver segnalato un problema descritto nel bollettino [MS07-034](http://technet.microsoft.com/security/bulletin/ms07-034).
-   Robbie Sohlman per aver segnalato un problema descritto nel bollettino [MS07-032](http://technet.microsoft.com/security/bulletin/ms07-032).

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://go.microsoft.com/fwlink/?linkid=21131). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://go.microsoft.com/fwlink/?linkid=21155).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (12 giugno 2007): Pubblicazione del riepilogo dei bollettini.

*Built at 2014-04-18T01:50:00Z-07:00*
