---
TOCTitle: 'MS08-APR'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - aprile 2008'
ms:assetid: 'ms08-apr'
ms:contentKeyID: 61240018
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms08-apr(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - aprile 2008
================================================================

Data di pubblicazione: martedì 8 aprile 2008 | Aggiornamento: mercoledì 18 febbraio 2009

**Versione:** 1.3

Questo riepilogo elenca bollettini sulla sicurezza rilasciati ad aprile 2008.

Con il rilascio dei bollettini del mese di aprile 2008, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 3 aprile 2008. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/security/bulletin/notify).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 9 aprile 2008 alle 11:00 Pacific Time (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di aprile](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032357219&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Critico (5)
-----------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-018                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Microsoft Project può consentire l'esecuzione di codice in modalità remota (950183)**](http://go.microsoft.com/fwlink/?linkid=115454)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Project che potrebbe consentire l'esecuzione di codice in modalità remota se un utente apre un file Project appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Software interessato**        | **Microsoft Office.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-021                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in GDI può consentire l'esecuzione di codice in modalità remota (948590)**](http://technet.microsoft.com/security/bulletin/ms08-021)                                                                                                                                                                                                                                                                                                                                                                                           |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in GDI. Lo sfruttamento di queste vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota se un utente apre un file di immagine EMF o WMF appositamente predisposto. Sfruttando queste vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                            |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                              |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-022                                                                                                                                                                                                                                                                                                                                                                              |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità nei motori di script VBScript e JScript potrebbe consentire l'esecuzione di codice in modalità remota (944338)**](http://go.microsoft.com/fwlink/?linkid=108169)                                                                                                                                                                                                                                      |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft nei motori di script VBScript e JScript in Windows. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                           |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                    |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                   |
| **Software interessato**        | **Microsoft Windows. **Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                     |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-023                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Aggiornamento per la protezione dei kill bit ActiveX (948881)**](http://technet.microsoft.com/security/bulletin/ms08-023)                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità per un prodotto Microsoft segnalata privatamente. Questo aggiornamento contiene anche un kill bit per Yahoo! Music Jukebox. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                   |
| **Software interessato**        | **Microsoft Windows, Internet Explorer.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                     |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-024                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|---------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Aggiornamento cumulativo per la protezione di Internet Explorer (947864)**](http://technet.microsoft.com/security/bulletin/ms08-024)                                                                                                                                                                                                                                                                                                                                          |
| **Riepilogo**                   | Questo aggiornamento per la protezione di livello risolve una vulnerabilità segnalata privatamente a Microsoft. Tale vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                         |
| **Software interessato**        | **Microsoft Windows, Internet Explorer.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                        |

Importante (3)
--------------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-020                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità nel client DNS può consentire attacchi di spoofing (945553)**](http://go.microsoft.com/fwlink/?linkid=108231)                                                                                                                                                                                                                                                    |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft. Questa vulnerabilità di spoofing esiste nei client DNS di Windows e può consentire a un utente malintenzionato di inviare risposte appositamente predisposte alle richieste DNS, eseguendo lo spoofing o il reindirizzamento del traffico di Internet dalle posizioni legittime. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                   |
| **Effetti della vulnerabilità** | Spoofing                                                                                                                                                                                                                                                                                                                                                                              |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                              |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-025                                                                                                                                                                                                                                                                                                                |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità nel kernel di Windows può consentire l'acquisizione di privilegi più elevati (941693)**](http://go.microsoft.com/fwlink/?linkid=111956)                                                                                                                                                                                                 |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente nel kernel di Windows. Sfruttando questa vulnerabilità, un utente malintenzionato locale potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                          |
| **Effetti della vulnerabilità** | Acquisizione di privilegi più elevati                                                                                                                                                                                                                                                                                                                        |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                     |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                       |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-019                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità in Microsoft Visio possono consentire l'esecuzione di codice in modalità remota (949032)**](http://technet.microsoft.com/security/bulletin/ms08-019)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve alcune vulnerabilità segnalate privatamente in Microsoft Office Visio che potrebbero consentire l'esecuzione di codice in modalità remota se un utente apre un file Visio appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento non è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Software interessato**        | **Microsoft Office.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

Software interessato e posizioni per il download
------------------------------------------------

<span></span>
**Come utilizzare questa tabella**

È possibile utilizzare questa tabella per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se è necessario applicare i relativi aggiornamenti per la protezione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.

**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.

#### Sistema operativo Windows e suoi componenti

 
<table style="border:1px solid black;">
<caption>Microsoft Windows 2000</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-021"><strong>MS08-021</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=108169"><strong>MS08-022</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-023"><strong>MS08-023</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-024"><strong>MS08-024</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=108231"><strong>MS08-020</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=111956"><strong>MS08-025</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Windows 2000 Service Pack 4</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=caac000a-22b6-48cb-aa00-1a0bfe886de2">Microsoft Windows 2000 Service Pack 4</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=8e3ff44f-145b-4a68-9ad4-4a55d74b216e">VBScript 5.1 e JScript 5.1</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=8e3ff44f-145b-4a68-9ad4-4a55d74b216e">VBScript 5.6 e JScript 5.6</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=ba6d3aeb-e35a-47cc-bace-7bd9d58a9d3f">Microsoft Internet Explorer 5.01 Service Pack 4</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=ba6d3aeb-e35a-47cc-bace-7bd9d58a9d3f">Microsoft Internet Explorer 6 Service Pack 1</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=b051ae04-fe81-440d-9136-d6b239ca954e">Microsoft Internet Explorer 5.01 Service Pack 4</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=75d2dc78-e3a4-4ff6-9e2d-bf1935003e8e">Microsoft Internet Explorer 6 Service Pack 1</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=41326ade-96b6-47ce-9291-d4e3039471c4">Microsoft Windows 2000 Service Pack 4</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=8db9f328-da0e-4fb8-96c4-6d368b47c224">Microsoft Windows 2000 Service Pack 4</a><br />
(Importante)</td>
</tr>
</tbody>
</table>
 

 
<table style="border:1px solid black;">
<caption>Windows XP</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-021"><strong>MS08-021</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=108169"><strong>MS08-022</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-023"><strong>MS08-023</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-024"><strong>MS08-024</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=108231"><strong>MS08-020</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=111956"><strong>MS08-025</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows XP Service Pack 2</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=c2763dd8-a03e-4a48-aa86-a7ec00250a7a">Windows XP Service Pack 2</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=c0124698-3b94-4474-9473-22a2f39a4a56">VBScript 5.6 e JScript 5.6</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=9dbf002f-fe53-4cc7-a430-35f45c520d10">Windows XP Service Pack 2</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=36c641ad-953f-4b09-ba1c-9c383295e180">Microsoft Internet Explorer 6</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=e771efe8-8881-4f23-b5b0-15651a390ba9">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=893f4cef-0395-4c44-ba28-7a10b6e7dd48">Windows XP Service Pack 2</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=0e937f65-abd0-46dd-8883-5bfd70ea1178">Windows XP Service Pack 2</a><br />
(Importante)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=166f2ab5-913c-47a9-86fe-b814797b751e">Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=87b80ae3-e299-4d15-a135-3b1bcf943652">VBScript 5.6 e JScript 5.6</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=01400970-df68-4daf-aa39-2fc4f969974c">Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=85beacc0-8ca2-4ded-9c24-23348d05c735">Microsoft Internet Explorer 6</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=9364bf81-6505-4788-958d-a4bd29dc98ad">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=8fdd1207-6e93-4c43-bacc-fe3623a6ebe7">Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=a29bbd13-761f-44fa-8948-e1a8c244bd7a">Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2</a><br />
(Importante)</td>
</tr>
</tbody>
</table>
 

 
<table style="border:1px solid black;">
<caption>Windows Server 2003</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-021"><strong>MS08-021</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=108169"><strong>MS08-022</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-023"><strong>MS08-023</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-024"><strong>MS08-024</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=108231"><strong>MS08-020</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=111956"><strong>MS08-025</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=bee91d80-d49a-4d3d-82d6-d5aa63f54979">Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=88518aa6-e334-4529-aa63-0bf2ef417ce3">VBScript 5.6 e JScript 5.6</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=ad384fea-53be-4be3-8acb-1cd23a7f5405">Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2</a><br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=0444b76e-93fa-43c2-b1bc-a5c054529eb5">Microsoft Internet Explorer 6</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=9acd2a03-5530-49c8-9ea1-0bfaf259700d">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=214bd8f5-6eb2-414c-b013-c516a306d692">Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=d3b855a6-4648-4771-826d-11a151828eac">Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2</a><br />
(Importante)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=e3dde449-e062-4ce0-a9f4-433bff23e224">Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=12cefefc-8553-4dca-9850-c653371de61e">VBScript 5.6 e JScript 5.6</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=ffc5c893-cb24-4875-b0a7-6d5c7aa4d642">Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2</a><br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=5ebb5ef9-615f-4cab-bac5-6f45f1b94952">Microsoft Internet Explorer 6</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=a9e406aa-33e2-49b8-ab54-4a7328e46147">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=fd123394-a5d6-4b55-be74-2938f52ce922">Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=320fd100-35e1-4345-9399-796393235cbc">Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2</a><br />
(Importante)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=7886a802-f2b5-489c-b14b-631f4c4c0742">Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=fe22a828-cca4-4b51-bbd5-995c65fead21">VBScript 5.6 e JScript 5.6</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=94cf78d3-b6c3-41bc-993e-3af3be0d70f1">Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium</a><br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=63da8040-fda2-42c7-8543-26ad6f9811f2">Microsoft Internet Explorer 6</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=75a05d3a-92a0-4a00-95d4-e2b2f6755180">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=e0e63f03-904d-47ee-94fc-51a8dea668eb">Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=126426a7-be38-4327-89db-02d99d76589d">Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium</a><br />
(Importante)</td>
</tr>
</tbody>
</table>
 

 
<table style="border:1px solid black;">
<caption>Windows Vista</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-021"><strong>MS08-021</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=108169"><strong>MS08-022</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-023"><strong>MS08-023</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-024"><strong>MS08-024</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=108231"><strong>MS08-020</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=111956"><strong>MS08-025</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Vista e Windows Vista Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=9b51deb8-3873-4146-977f-7e3d0840a4c5">Windows Vista e Windows Vista Service Pack 1</a><br />
(Critico)</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=d7f14001-7f42-4ca0-9193-cdf061179b59">Windows Vista e Windows Vista Service Pack 1</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=d4e24966-6530-463a-9ee2-f6a9d000f998">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=8203d303-c855-4579-9bbf-b06ddf5c1b87">Windows Vista</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=9640cd8b-d749-4ddd-8af9-b298cebed969">Windows Vista e Windows Vista Service Pack 1</a><br />
(Importante)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=4ad6dcd1-6ea5-43bf-8bee-a5f507beadc6">Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1</a><br />
(Critico)</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=d33462b6-7391-482d-babe-fb4cd0beaa21">Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=295cf8f2-265e-4570-b708-21033337fe05">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=73f3a234-3973-4467-be7e-69efa7ee978c">Windows Vista x64 Edition</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=d56bb4fe-304e-45e0-95f2-fde2f47b2a04">Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1</a><br />
(Importante)</td>
</tr>
</tbody>
</table>
 

 
<table style="border:1px solid black;">
<caption>Windows Server 2008</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-021"><strong>MS08-021</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=108169"><strong>MS08-022</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-023"><strong>MS08-023</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-024"><strong>MS08-024</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=108231"><strong>MS08-020</strong></a></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=111956"><strong>MS08-025</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2008 per sistemi a 32 bit</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=006d5c47-53e6-4ee1-932c-497611804938">Windows Server 2008 per sistemi a 32 bit</a><br />
(Critico)</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=95691924-2813-4a86-9e11-99d853f8e606">Windows Server 2008 per sistemi a 32 bit</a><br />
(Basso)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=e57b4d94-19ad-4818-8311-a3f94be01a4b">Windows Internet Explorer 7</a>*<br />
(Critico)</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=4497333c-9418-4b91-83dc-0155735421c0">Windows Server 2008 per sistemi a 32 bit</a><br />
(Importante)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows Server 2008 per sistemi basati su x64</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=8909f144-655b-4f07-916f-fd967f1efb2b">Windows Server 2008 per sistemi x64</a><br />
(Critico)</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=920ae29b-19d0-4089-ac79-f2da824a2256">Windows Server 2008 per sistemi x64</a><br />
(Basso)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=93e9f52a-c7d0-4033-9c12-740665a219af">Windows Internet Explorer 7</a>*<br />
(Critico)</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=5aefc7a6-79a4-45a2-b534-35d0ec400dda">Windows Server 2008 per sistemi x64</a><br />
(Importante)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2008 per sistemi basati su Itanium</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=b7771a4a-4e4f-48d1-8551-bb8b778ca5a7">Windows Server 2008 per sistemi basati su Itanium</a><br />
(Critico)</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=66df79ac-8364-4922-9688-ebc7ec76d89f">Windows Server 2008 per sistemi basati su Itanium</a><br />
(Basso)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=acf948e8-c4a9-40da-b282-f5e584e77b05">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;">Nessuno</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=3080c26b-7456-41ef-8668-28f15bc7b8ce">Windows Server 2008 per sistemi basati su Itanium</a><br />
(Importante)</td>
</tr>
</tbody>
</table>
 

**\*Le installazioni di Windows Server 2008 con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questi aggiornamenti non interessano le edizioni supportate di Windows Server 2008, se Windows Server 2008 è stato installato utilizzando l'opzione di installazione Server Core, anche se i file interessati da queste vulnerabilità sono presenti nel sistema. L'aggiornamento viene comunque offerto agli utenti che dispongono dei file interessati, poiché i file dell'aggiornamento sono più recenti (con numeri di versione più elevati) rispetto a quelli attualmente presenti nel sistema. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

#### Suite e software Microsoft Office

 
<table style="border:1px solid black;">
<caption>Microsoft Project</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=115454"><strong>MS08-018</strong></a></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Project 2000 Service Release 1</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=fbe46241-b9da-40c6-803d-42eb6234be77">Project 2000 Service Release 1</a><br />
(KB949043)<br />
(Critico)</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Project 2002 Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=07a90718-6597-426d-9dca-a336d60c01b8">Project 2002 Service Pack 1</a><br />
(KB949005)<br />
(Importante)</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Project 2003 Service Pack 2</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=aaba07d6-e972-4e85-bccd-406aa2c4a4f4">Project 2003 Service Pack 2</a><br />
(KB948962)<br />
(Importante)</td>
<td style="border:1px solid black;"></td>
</tr>
</tbody>
</table>

 
<table style="border:1px solid black;">
<caption>Microsoft Visio</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-019"><strong>MS08-019</strong></a></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Visio 2002 Service Pack 2</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=0056a936-def5-40fa-bcfc-0ab0dd5c3964">Visio 2002 Service Pack 2</a><br />
(KB947896)<br />
(Importante)</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Visio 2003 Service Pack 2</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=18af0ce6-99a0-4471-8d26-9700a8a8e631">Visio 2003 Service Pack 2</a><br />
(KB947650)<br />
(Importante)</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Visio 2003 Service Pack 3</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=18af0ce6-99a0-4471-8d26-9700a8a8e631">Visio 2003 Service Pack 3</a><br />
(KB947650)<br />
(Importante)</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Visio 2007</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=0510a1bb-b464-452c-900f-7f4e58ed9c7e">Visio 2007</a><br />
(KB947590)<br />
(Importante)</td>
<td style="border:1px solid black;"></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Visio 2007 Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;amp;familyid=0510a1bb-b464-452c-900f-7f4e58ed9c7e">Visio 2007 Service Pack 1</a><br />
(KB947590)<br />
(Importante)</td>
<td style="border:1px solid black;"></td>
</tr>
</tbody>
</table>
  
Strumenti e informazioni sul rilevamento e sulla distribuzione  
--------------------------------------------------------------
  
<span></span>
**Security Central**
  
Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://www.microsoft.com/italy/technet/security/default.mspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).
  
Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it), [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/default.aspx?ln=it-it) e [Office Update.](http://office.microsoft.com/it-it/downloads/default.aspx) Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
  
Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).
  
**Informazioni sul rilevamento e sulla distribuzione**
  
Per gli aggiornamenti per la protezione di questo mese Microsoft ha fornito informazioni sul rilevamento e sulla distribuzione. Tali informazioni consentono inoltre ai professionisti IT di apprendere come utilizzare diversi strumenti per distribuire gli aggiornamenti per la protezione, quali Windows Update, Microsoft Update, Office Update, Microsoft Baseline Security Analyzer (MBSA), Office Detection Tool, Microsoft Systems Management Server (SMS) ed Extended Security Update Inventory Tool (ESUIT). Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 910723](http://support.microsoft.com/kb/910723).
  
**Microsoft Baseline Security Analyzer**
  
Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).
  
**Windows Server Update Services**
  
Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire in modo rapido e affidabile la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Windows 2000 e versioni successive del sistema operativo.
  
Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/it-it/wsus/bb466208.aspx).
  
**Systems Management Server**
  
Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali. È disponibile la nuova versione di SMS, System Center Configuration Manager 2007. Vedere anche [System Center Configuration Manager 2007](http://technet.microsoft.com/it-it/library/bb735860.aspx). Per ulteriori informazioni su come gli amministratori possono utilizzare SMS 2003 per distribuire gli aggiornamenti per la protezione, vedere il sito relativo alla [Gestione delle patch per la protezione di SMS 2003](http://www.microsoft.com/italy/technet/security/bulletin/ms07-22939). Gli utenti di SMS 2.0 possono inoltre utilizzare [Software Updates Services Feature Pack](http://technet.microsoft.com/it-it/sms/bb676802.aspx) per semplificare la distribuzione degli aggiornamenti per la protezione. Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server](http://www.microsoft.com/italy/server/smserver/default.mspx).
  
**Nota**: SMS utilizza Microsoft Baseline Security Analyzer e lo strumento di rilevamento di Microsoft Office per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/it-it/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool, disponibile in [SMS 2003 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676767.aspx) e in [SMS 2.0 Administration Feature Pack](http://technet.microsoft.com/it-it/sms/bb676800.aspx).
  
### Altre informazioni
  
#### Strumento di rimozione software dannoso di Microsoft Windows
  
Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.
  
#### Aggiornamenti non correlati alla protezione e ad alta priorità su MU, WU e WSUS
  
Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:
  
-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche relative a Software Update Services e Windows Server Update Services nei contenuti del 2008. Include tutti i contenuti Windows.  
-   [Aggiornamenti nuovi, rivisti e rilasciati per i prodotti Microsoft diversi da Microsoft Windows](http://technet.microsoft.com/it-it/wsus/bb466214.aspx).
  
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
  
-   [National Cyber Security Center](http://www.ncsc.go.kr/eng/), Repubblica di Corea, per aver segnalato un problema descritto nel bollettino MS08-018  
-   Un utente anonimo per aver segnalato un problema descritto nel bollettino MS08-019  
-   Un utente anonimo per aver segnalato un altro problema descritto nel bollettino MS08-019  
-   Amit Klein di [Trusteer](http://www.trusteer.com/) per aver segnalato un problema descritto nel bollettino MS08-020  
-   Alla Berzroutchko di [Scanit](http://www.scanit.be/) per aver segnalato un problema descritto nel bollettino MS08-020  
-   Chris Ries di [Nominet UK](http://www.nominet.org.uk/) per aver segnalato un problema descritto nel bollettino MS08-020  
-   Jun Mao di [iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS08-021  
-   Sebastian Apelt di [Zero Day Initiative](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS08-021  
-   Thomas Garnier di [SkyRecon](http://www.skyrecon.com/) per aver segnalato un problema descritto nel bollettino MS08-021  
-   Yamata Li di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato un problema descritto nel bollettino MS08-021  
-   Peter Ferrie di [Symantec](http://www.symantec.com/) per aver segnalato un problema descritto nel bollettino MS08-022  
-   Un ricercatore anonimo che collabora con [iDefense VCP](http://labs.idefense.com/vcp/) per aver segnalato un problema descritto nel bollettino MS08-023  
-   Carsten Eiram di [Secunia](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS08-024  
-   Thomas Garnier di [SkyRecon](http://www.skyrecon.com/) per aver segnalato un problema descritto nel bollettino MS08-025
  
#### Supporto
  
-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).  
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://support.microsoft.com/?ln=it&x=15&y=11). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.  
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/).
  
#### Dichiarazione di non responsabilità
  
Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.
  
#### Versioni
  
-   V1.0 (08 aprile 2008): Pubblicazione del riepilogo dei bollettini.  
-   V1.1 (9 aprile 2008): aggiornamento del Riepilogo per il bollettino Microsoft sulla sicurezza MS08-018.  
-   V1.2 (16 aprile 2008): sono state aggiornate le informazioni sul finder per il bollettino MS08-021 e sono state chiarite le informazioni sul Software interessato per le suite e il software Microsoft Office.  
-   V1.3 (18 febbraio 2009): Aggiunta notazione sui Server Core non interessati di Windows Server 2008 per sistemi a 32 bit e Windows Server 2008 per sistemi a x64 per MS08-024.
  
*Built at 2014-04-18T01:50:00Z-07:00*
