---
TOCTitle: 'MS07-AUG'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - agosto 2007'
ms:assetid: 'ms07-aug'
ms:contentKeyID: 61240007
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms07-aug(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - agosto 2007
================================================================

Data di pubblicazione: martedì 14 agosto 2007 | Aggiornamento: martedì 24 giugno 2008

**Versione:** 4.0

Questo riepilogo elenca bollettini sulla sicurezza rilasciati ad agosto 2007.

Con il rilascio dei bollettini di agosto 2007, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 9 agosto 2007. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/security/bulletin/notify).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 15 agosto 2007 alle 11:00 Pacific Time (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di agosto](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032344688&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il Webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i Webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Critico (6)
-----------

<span></span>
| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-042                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Microsoft XML Core Services può consentire l'esecuzione di codice in modalità remota (936227)**](http://technet.microsoft.com/security/bulletin/ms07-042)                                                                                                                                                                                                                                                                                                                                                                                                |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello critico risolve una vulnerabilità segnalata privatamente a Microsoft. Questa vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. La vulnerabilità può essere sfruttata tramite attacchi a Microsoft XML Core Services. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Software interessato**        | **Windows, XML Core Services.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-043                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità nell'automazione OLE può consentire l'esecuzione di codice in modalità remota (921503)**](http://technet.microsoft.com/security/bulletin/ms07-043)                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello critico risolve una vulnerabilità segnalata privatamente a Microsoft. Questa vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta. La vulnerabilità può essere sfruttata tramite attacchi al collegamento ed incorporamento di oggetti (OLE). Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Software interessato**        | **Windows, Visual Basic, Office per Mac**. Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                      |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-044                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Microsoft Excel può consentire l'esecuzione di codice in modalità remota (940965)**](http://technet.microsoft.com/security/bulletin/ms07-044)                                                                                                                                                                                                                                                                                                                                                  |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft, nonché altri problemi di protezione identificati durante la ricerca. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apre un file di Excel appositamente predisposto. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                      |
| **Software interessato**        | **Office**. Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                            |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-045                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Aggiornamento cumulativo per la protezione di Internet Explorer (937143)**](http://technet.microsoft.com/security/bulletin/ms07-045)                                                                                                                                                                                                                                                                                                                                                        |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello critico risolve tre vulnerabilità segnalate privatamente a Microsoft. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                  |
| **Software interessato**        | **Windows, Internet Explorer**. Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-046                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in GDI può consentire l'esecuzione di codice in modalità remota (938829)**](http://technet.microsoft.com/security/bulletin/ms07-046)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello critico risolve una vulnerabilità segnalata privatamente a Microsoft. Nel motore di rendering della grafica esiste una vulnerabilità legata all'esecuzione di codice in modalità remota causata dal modo in cui vengono gestite le immagini appositamente predisposte. Un utente malintenzionato potrebbe sfruttare la vulnerabilità creando un'immagine appositamente predisposta in grado di consentire l'esecuzione di codice in modalità remota, se un utente apre un allegato di posta elettronica appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Software interessato**        | **Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-050                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Vector Markup Language può consentire l'esecuzione di codice in modalità remota (938127)**](http://technet.microsoft.com/security/bulletin/ms07-050)                                                                                                                                                                                                                                                                                                                                              |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nell'implementazione di Vector Markup Language (VML) in Windows. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                             |
| **Software interessato**        | **Windows, Internet Explorer**. Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                           |

Importante (3)
--------------

<span></span>
| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-047                                                                                                                                                                                                                                                                                                                                                                                                                                |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Windows Media Player può consentire l'esecuzione di codice in modalità remota (936782)**](http://technet.microsoft.com/security/bulletin/ms07-047)                                                                                                                                                                                                                                                                                                   |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello importante risolve due vulnerabilità segnalate privatamente a Microsoft. Queste vulnerabilità potrebbero consentire l'esecuzione di codice se un utente visualizza un file appositamente predisposto in Windows Media Player. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                            |
| **Software interessato**        | **Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                 |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-048                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità in Windows Gadgets possono consentire l'esecuzione di codice in modalità remota (938123)**](http://technet.microsoft.com/security/bulletin/ms07-048)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Riepilogo**                   | Questo importante aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente a Microsoft., nonché altri problemi di protezione identificati durante la ricerca. Queste vulnerabilità potrebbero consentire a un utente malintenzionato remoto anonimo di eseguire codice con i privilegi di un utente connesso. Se un utente effettua una sottoscrizione a un feed RSS dannoso nel gadget Titoli RSS, aggiunge un file di contatti dannoso nel gadget Contatti o seleziona un collegamento dannoso nel gadget Meteo, un utente malintenzionato potrebbe potenzialmente eseguire codice nel sistema. In tutti i vettori di attacco, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Software interessato**        | **Windows** **Vista.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS07-049                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Virtual PC e Virtual Server può consentire l'acquisizione di privilegi più elevati (937986)**](http://technet.microsoft.com/security/bulletin/ms07-049)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello importante risolve una vulnerabilità segnalata privatamente a Microsoft. Si tratta di una vulnerabilità associata all'acquisizione di privilegi più elevati. La vulnerabilità in Microsoft Virtual PC e Microsoft Virtual Server potrebbe consentire a un sistema operativo guest di eseguire codice nel sistema operativo host o in un altro sistema operativo guest. Soltanto gli utenti del sistema operativo guest con autorizzazioni amministrative per tale possono sfruttare questa vulnerabilità. Gli utenti del sistema operativo guest privi di tali autorizzazioni amministrative non possono sfruttare questa vulnerabilità. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Effetti della vulnerabilità** | Acquisizione di privilegi più elevati                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Software interessato**        | **Virtual PC, Virtual Server.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

Software interessato e posizioni per il download
------------------------------------------------

<span></span>
**Come utilizzare questa tabella**

È possibile utilizzare questa tabella per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se è necessario applicare i relativi aggiornamenti per la protezione. Per ogni programma o componente elencato sono riportati l'effetto della vulnerabilità e un collegamento al relativo aggiornamento.

**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.

#### Software interessato e posizioni per il download dei bollettini da MS07-042 a MS07-046

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
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS07-042**](http://technet.microsoft.com/security/bulletin/ms07-042)
</td>
<td style="border:1px solid black;">
[**MS07-043**](http://technet.microsoft.com/security/bulletin/ms07-043)
</td>
<td style="border:1px solid black;">
[**MS07-044**](http://technet.microsoft.com/security/bulletin/ms07-044)
</td>
<td style="border:1px solid black;">
[**MS07-045**](http://technet.microsoft.com/security/bulletin/ms07-045)
</td>
<td style="border:1px solid black;">
[**MS07-046**](http://technet.microsoft.com/security/bulletin/ms07-046)
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
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
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
<th colspan="6">
Software Windows interessato
</th>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=5c35b6e8-732a-4451-b5d4-23ed63e6e792)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=8fc8340b-c2b3-4559-835c-caa00cf086b9)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=6e8de050-8589-4831-ae19-075c93509485)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=dc29475d-c0bb-4d35-8dd6-4ca1cac32315)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=b85bb583-dc61-4d37-b458-208f5bb07ece)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=3c81730a-981a-4649-b2d9-45144230d512)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=b85bb583-dc61-4d37-b458-208f5bb07ece)
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
Windows Server 2003 Service Pack 1
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=15d4d4fa-9bab-4da5-978e-f89c78c8086a)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=5374583d-de68-4d65-bca8-598d6b98b8b3)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=15d4d4fa-9bab-4da5-978e-f89c78c8086a)
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
Windows Server 2003 x64 Edition
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=6608d722-3ef8-4085-b771-7b17bb0ba06e)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=c3359f27-e03e-4a4f-b896-3bda39f69f7e)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=6608d722-3ef8-4085-b771-7b17bb0ba06e)
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
Windows Server 2003 con SP1 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=fc04451a-0696-4a21-b2b6-f02d4e2c33bf)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=92822479-2060-4357-a340-ed096f180b2b)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=fc04451a-0696-4a21-b2b6-f02d4e2c33bf)
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
Windows Vista
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
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
Windows Vista Service Pack 1
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
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
Windows Vista x64 Edition Service Pack 1
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
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
Windows Server 2008 per sistemi x64
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
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
<th colspan="6">
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=fcf9440f-bb36-4ed1-9b6b-74a4f055650b)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Internet Explorer 6 Service Pack 1 installato in Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=8db75461-4dca-43db-aa30-c7e67ce954ad)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=5d31d916-867f-4dbf-b8a4-c75ea83f4f51)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=b15b2442-d6da-41dd-a424-11c9893be595)
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
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=f2f9fb69-0399-4df0-9f5b-8f42a130c581)
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
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=d0bd886d-2c80-4dd7-82b7-1bd1f8d398cc)
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
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=bf41033a-d6f0-451e-9b69-4cbe2bb3f804)
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
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=7a2b4395-eaba-45ec-8d0c-932ebcc3d344)
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
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=cd7ed4d5-7790-41db-8b68-cfd59105ca36)
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
[Basso](http://www.microsoft.com/downloads/details.aspx?familyid=4f8daed8-9925-494d-b2f5-1e29f4040f6a)
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
[Basso](http://www.microsoft.com/downloads/details.aspx?familyid=34669ca2-46b0-4fbf-8fbd-ad7a13920103)
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
[Basso](http://www.microsoft.com/downloads/details.aspx?familyid=5bd7bcbd-528a-4a16-a39a-a5ff5f69a2e2)
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
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=9ae27b2f-aca4-4758-8ce4-a98f1ff6ba70)
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
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=53497e53-d10c-43af-ad56-9f07739a5284)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft XML Core Services 3.0 (KB936021) in Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=245214ea-76f9-4755-8a14-a74232e20c1c)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 3.0 (KB936021) in Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=dea6a48f-fb00-43f3-a374-3220f9759c2d)
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
Microsoft XML Core Services 3.0 (KB936021) in Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=b8862ca9-1203-4056-a257-29271838ac0d)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 3.0 (KB936021) in Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=12618ad0-aefd-4c9a-a769-4b14a7603d6e)
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
Microsoft XML Core Services 3.0 (KB936021) in Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=61bf00a9-aeea-431a-86d3-526a4a373bb7)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 3.0 (KB936021) in Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=b0285dd7-bf66-4226-9948-26e8aae99046)
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
Microsoft XML Core Services 3.0 (KB936021) in Windows Vista
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=c734d7de-5d87-4904-81c3-714db2cb8b0d)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 3.0 (KB936021) in Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=0a465d77-a737-4d26-82a1-570f9c788a8a)
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
Microsoft XML Core Services 4.0 (KB936181) installato in Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 4.0 (KB936181) in Windows XP Service Pack 2 e in Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
Microsoft XML Core Services 4.0 (KB936181) installato in Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 4.0 (KB936181) installato in Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
Microsoft XML Core Services 4.0 (KB936181) installato in Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 4.0 (KB936181) installato in Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
Microsoft XML Core Services 4.0 (KB936181) installato su Windows Vista e Windows Vista Service Pack 1
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 4.0 (KB936181) installato in Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
Microsoft XML Core Services 4.0 (KB936181) installato su Windows Server 2008 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 4.0 (KB936181) installato su Windows Server 2008 per sistemi x64
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
Microsoft XML Core Services 4.0 (KB936181) installato su Windows Server 2008 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=021e12f5-cb46-43df-a2b8-185639ba2807)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 6.0  
(KB933579) installato in Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=70c92e77-9e5a-41b1-a9d2-64443913c976)
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
Microsoft XML Core Services 6.0 (KB933579) installato in Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=70c92e77-9e5a-41b1-a9d2-64443913c976)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 6.0 (KB933579) installato in Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=70c92e77-9e5a-41b1-a9d2-64443913c976)
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
Microsoft XML Core Services 6.0 (KB933579) installato in Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=70c92e77-9e5a-41b1-a9d2-64443913c976)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 6.0 (KB933579) installato in Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=70c92e77-9e5a-41b1-a9d2-64443913c976)
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
Microsoft XML Core Services 6.0 (KB933579) installato in Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
[Moderato](http://www.microsoft.com/downloads/details.aspx?familyid=70c92e77-9e5a-41b1-a9d2-64443913c976)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft XML Core Services 6.0 (KB933579) in Windows Vista
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=14270529-3ae5-43bf-a471-722ab010d81e)
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
Microsoft XML Core Services 6.0 (KB933579) in Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=928da3d2-b0b9-447a-b37a-4350497fe563)
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
<th colspan="6">
Software Office interessato
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Excel 2000 Service Pack 3
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=082b98f7-9556-4f1f-823a-c41ddf5a7c9a)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Excel 2002 Service Pack 3
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=91308769-2577-4f9f-8209-06f2c8c8a86f)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Excel 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=b0130e9e-8845-4d79-aaa1-a21cc9388abe)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 2 con Microsoft XML Core Services 5.0 (KB936048)
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=a339cb7b-e08a-47f8-ac0b-df449191424a)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Excel Viewer 2003
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=c4a87572-3128-44f7-8069-95535a78500a)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Word Viewer 2003 con Microsoft XML Core Services 5.0 (KB936048)
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=a339cb7b-e08a-47f8-ac0b-df449191424a)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/mac/downloads.aspx)
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/mac/downloads.aspx)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Office System 2007 con Microsoft XML Core Services 5.0 (KB936960)
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=7a97478a-832c-4a6b-b074-0e18b1e4ed33)
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
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Groove Server 2007 con Microsoft XML Core Services 5.0 (KB936056)
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=e875613b-2f32-4f28-a635-664a25c95c18)
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
Microsoft Office SharePoint Server con Microsoft XML Core Services 5.0 (KB936056)
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=e875613b-2f32-4f28-a635-664a25c95c18)
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
<th colspan="6">
Altri prodotti interessati
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visual Basic 6.0 Service Pack 6 (KB924053)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=e1646fb0-29d5-4a6e-a8d2-304c4d7735b7)
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

**<sup>[1]</sup>** È disponibile un aggiornamento per la protezione per questo sistema operativo. Per ulteriori dettagli, vedere il software o il componente interessato nella tabella e consultare il relativo bollettino sulla sicurezza.** **

#### Software interessato e posizioni per il download dei bollettini da MS07-047 a MS07-050

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
[**MS07-047**](http://technet.microsoft.com/security/bulletin/ms07-047)
</td>
<td style="border:1px solid black;">
[**MS07-048**](http://technet.microsoft.com/security/bulletin/ms07-048)
</td>
<td style="border:1px solid black;">
[**MS07-049**](http://technet.microsoft.com/security/bulletin/ms07-049)
</td>
<td style="border:1px solid black;">
[**MS07-050**](http://technet.microsoft.com/security/bulletin/ms07-050)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
<td style="border:1px solid black;">
[**Critico**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr>
<th colspan="5">
Software Windows interessato
</th>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 1
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP1 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi basati su Itanium
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=49a5bd84-da71-4529-b4d3-ac57dab59e01)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=24443f59-b908-480b-9b72-7094d4b5e128)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
**<sup>[1]</sup>**
</td>
</tr>
<tr>
<th colspan="5">
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=31e63d6f-b6b7-41d7-8ae6-dd7fcf89d477)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Internet Explorer 6 Service Pack 1 installato in Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=7099d33a-0ef6-423f-824e-757482517612)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=4447d74f-09ea-4be0-9dae-c243ce657fb7)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=98ccd207-f4d0-4625-aeab-0ebf1643a5fd)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=463535aa-e04e-4a30-b3ab-8cd6d8cdd13c)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=9d4375d4-fb9b-4771-bd6f-e5d23eedbc6b)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=c7be313b-3405-42e1-9e4b-0cb6bf3d2cb1)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=9f5da816-194c-478e-8a96-9421a0c52c9f)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=1c3168a9-d959-4137-868a-ec70da737c21)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=59884e97-4912-4a9a-8a31-8182ea2d24db)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=42060e27-de14-4d0c-92a0-138cb57fe2b5)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=a536206e-9d1b-49a8-81a1-53d46f2de973)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=2dd908a4-6152-4976-aaaa-01f5f37c9143)
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
[Critico](http://www.microsoft.com/downloads/details.aspx?familyid=592435bc-1d43-4544-bd8a-4a2d829dc1a1)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Media Player 7.1 in Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=9f46b1fc-ee7b-437f-9492-67d003711021)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Media Player 9 installato in Microsoft Windows 2000 Service Pack 4
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=bd4a6474-5fde-415e-840e-7d973cb71c95)
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
Windows Media Player 9 in Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=bd4a6474-5fde-415e-840e-7d973cb71c95)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Media Player 10 installato in Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=48f5a9d3-b859-4cb6-a68e-abde76a14782)
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
Windows Media Player 10 in Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=949580be-cbb3-4271-8ca0-0ead7f2d8801)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Media Player 10 in Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=8d9f1fdf-6d4c-44d4-9b5f-bdbe8ac28d7f)
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
Windows Media Player 10 in Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=2c04c7f2-728e-43bd-8574-26e411fcd129)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Media Player 11 installato in Windows XP Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=a690d042-1137-4aaf-bd0e-565ea04d1f2b)
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
Windows Media Player 11 in Windows XP Professional X64 Edition e Windows XP Professional X64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=bdc89f34-c1ff-46ab-b52d-c02d51c5c373)
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Media Player 11 in Windows Vista
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=80e5167c-4f75-4ce3-8b15-2f50958deec8)
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
Windows Media Player 11 in Windows Vista x64 Edition
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=bf30b714-d6e7-47ea-b79e-84c18370a661)
</td>
<td style="border:1px solid black;">
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
Microsoft Virtual PC 2004
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=cbdeaa50-7115-4673-97c4-10009f9c5c42)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Virtual PC 2004 Service Pack 1
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=17ffe5a2-3551-4858-93b6-5e25af87d808)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Virtual Server 2005 Standard Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=bc02ea6d-2884-4637-9894-3413a71329ee)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Virtual Server 2005 Enterprise Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=da474b6f-9f0c-43f6-b432-050f7e76967d)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Virtual Server 2005 R2 Standard Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=43fa1327-8e5e-4c92-901f-1ff2a0a087b4)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Virtual Server 2005 R2 Enterprise Edition
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/downloads/details.aspx?familyid=c2fc16c4-1fb0-4c09-b04a-684b40df8517)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Virtual PC per Mac versione 6.1
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/mac/downloads.aspx%20vpc)
</td>
<td style="border:1px solid black;">
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Virtual PC per Mac versione 7
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
</td>
<td style="border:1px solid black;">
[Importante](http://www.microsoft.com/mac/downloads.aspx%20vpc)
</td>
<td style="border:1px solid black;">
</td>
</tr>
</table>
 
**Note**

**<sup>[1]</sup>** È disponibile un aggiornamento per la protezione per questo sistema operativo. Per ulteriori dettagli, vedere il software o il componente interessato nella tabella e consultare il relativo bollettino sulla sicurezza.** **

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/updatemanagement/default.aspx). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it), [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Office Update.](http://office.microsoft.com/it-it/downloads/fx101321101040.aspx) Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "security\_patch". Infine, gli aggiornamenti per la protezione possono essere scaricati dal catalogo di Windows Update. Per ulteriori informazioni sul catalogo di Windows Update, vedere l'[articolo della Microsoft Knowledge Base 323166](http://support.microsoft.com/kb/323166).

**Informazioni sul rilevamento e sulla distribuzione**

Per gli aggiornamenti per la protezione di questo mese Microsoft ha fornito informazioni sul rilevamento e sulla distribuzione. Tali informazioni consentono inoltre ai professionisti IT di apprendere come utilizzare diversi strumenti per distribuire gli aggiornamenti per la protezione, quali Windows Update, Microsoft Update, Office Update, Microsoft Baseline Security Analyzer (MBSA), Office Detection Tool, Microsoft Systems Management Server (SMS), Extended Security Update Inventory Tool ed Enterprise Update Scan Tool (EST). Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 910723](http://support.microsoft.com/kb/910723/it).

**Microsoft Baseline Security Analyzer ed** **Enterprise** **Update Scan Tool**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21134).

Se MBSA 1.2.1 non supporta il rilevamento di uno specifico aggiornamento per la protezione, Microsoft rilascia una versione di Enterprise Update Scan Tool (EST) per tale aggiornamento. Per ulteriori informazioni su EST, visitare la pagina Web di [Enterprise Update Scan Tool.](http://support.microsoft.com/kb/894193/it)

**Nota** Dopo il 9 ottobre 2007, il file MSSecure.XML utilizzato da MBSA 1.2.1 non verrà più aggiornato. Dopo questa data, non verranno aggiunti nuovi aggiornamenti per la protezione al file MSSecure.XML utilizzato da MBSA 1.2.1 e non verranno rilasciate nuove versioni di Enterprise Scan Tool. Per ulteriori informazioni, visitare il sito Web [Microsoft Baseline Security Analyzer](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21134).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208.aspx).

**Systems Management Server**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. Per ulteriori informazioni sull'utilizzo di SMS 2003 per la distribuzione degli aggiornamenti per la protezione, visitare il sito [Gestione delle patch per la protezione con SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33340) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).

**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33341). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-33387) e in [SMS 2.0 Administration Feature Pack](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21161).

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS

Per questo mese:

-   Microsoft ha rilasciato quattro aggiornamenti **non correlati alla protezione** e ad alta priorità su Microsoft Update (MU) e Windows Server Update Services (WSUS).
-   Microsoft ha rilasciato due aggiornamenti **non correlati alla protezione** e ad alta priorità per Windows su Windows Update (WU).

Tenere presente che queste informazioni riguardano **soltanto** gli aggiornamenti **non correlati alla protezione** e ad alta-priorità su Microsoft Update, Windows Update e Windows Server Update Services rilasciati lo stesso giorno del riepilogo dei bollettini sulla sicurezza. **Non** vengono fornite informazioni sugli aggiornamenti **non correlati alla protezione** rilasciati in altri giorni.

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione delle patch](http://www.microsoft.com/italy/technet/security/bulletin/ms07-21168).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "security\_patch".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086/it).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/it-it/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://www.microsoft.com/italy) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Un ricercatore anonimo che collabora con [VeriSign iDefense VCP](http://idefense.com/) per aver segnalato un problema descritto nel bollettino [MS07-042](http://technet.microsoft.com/security/bulletin/ms07-042).
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino [MS07-042](http://technet.microsoft.com/security/bulletin/ms07-042).
-   Un ricercatore anonimo che collabora con [VeriSign iDefense VCP](http://idefense.com/) per aver segnalato un problema descritto nel bollettino [MS07-043](http://technet.microsoft.com/security/bulletin/ms07-043).
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino [MS07-043](http://technet.microsoft.com/security/bulletin/ms07-043).
-   Dyon Balding di [Secunia](http://secunia.com/) per aver segnalato un problema descritto nel bollettino [MS07-044](http://technet.microsoft.com/security/bulletin/ms07-044).
-   [NSFocus Security Team](http://www.nsfocus.com/) per aver segnalato un problema descritto nel bollettino [MS07-045](http://technet.microsoft.com/security/bulletin/ms07-045).
-   Brett Moore di [Security-Assessment.com](http://www.security-assessment.com/) per aver segnalato un problema descritto nel bollettino [MS07-045](http://technet.microsoft.com/security/bulletin/ms07-045).
-   [eEye Digital Security](http://www.eeye.com/) per aver segnalato un problema descritto nel bollettino [MS07-046](http://technet.microsoft.com/security/bulletin/ms07-046).
-   Piotr Bania, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayintiative.com/), per aver segnalato un problema descritto nel bollettino [MS07-047](http://technet.microsoft.com/security/bulletin/ms07-047).
-   Aviv Raff di [Finjan](http://www.finjan.com/) per aver segnalato un problema descritto nel bollettino [MS07-048](http://technet.microsoft.com/security/bulletin/ms07-048).
-   Aviv Raff di [iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino [MS07-048](http://technet.microsoft.com/security/bulletin/ms07-048).
-   Rafal Wojtczuk di [McAfee Avert Labs](http://www.avertlabs.com/) per aver collaborato con noi su un problema descritto in [MS07-049](http://technet.microsoft.com/security/bulletin/ms07-049).
-   [eEye Digital Security](http://www.eeye.com/) per aver segnalato un problema descritto nel bollettino [MS07-050](http://technet.microsoft.com/security/bulletin/ms07-050).

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://support.microsoft.com/). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (14 agosto 2007): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (29 agosto 2007): Tabella Software interessato aggiornata per modificare la sezione Software Office interessato nel bollettino MS07-044 da "Office 2000", "Office XP" e "Office 2003" a, rispettivamente, "Excel 2000", "Excel 2002" ed "Excel 2003".
-   V2.0 (13 novembre 2007): tabella Software interessato aggiornata per includere i collegamenti per il download aggiornati per il bollettino MS07-049. È disponibile un aggiornamento per la protezione rivisto per l'installazione in Microsoft Virtual PC 2004, Microsoft Virtual PC 2004 Service Pack 1, Microsoft Virtual Server 2005 Standard Edition, Microsoft Virtual Server 2005 Enterprise Edition, Microsoft Virtual Server 2005 R2 Standard Edition e Microsoft Virtual Server 2005 R2 Enterprise Edition.
-   V3.0 (9 gennaio 2008): tabella Software interessato aggiornata per aggiungere Microsoft Word Viewer 2003 in MS07-042. L'aggiornamento per Microsoft Office 2003 Service Pack 2 si applica anche a Microsoft Word Viewer 2003.
-   V4.0 (24 giugno 2008): Tabella Software interessato aggiornata per aggiungere Windows XP Service Pack 3, Windows Vista Service Pack 1, Windows Vista x64 Edition Service Pack 1, Windows Server 2008 per sistemi a 32 bit, Windows Server 2008 per sistemi x64 e Windows Server 2008 per sistemi basati su Itanium in MS07-042 per l'aggiornamento KB936181 per Microsoft XML Core Services 4.0. Si tratta di una modifica relativa solo al rilevamento. Non sono previste modifiche ai file binari.

*Built at 2014-04-18T01:50:00Z-07:00*
