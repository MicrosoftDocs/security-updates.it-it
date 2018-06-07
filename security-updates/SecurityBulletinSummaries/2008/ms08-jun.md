---
TOCTitle: 'MS08-JUN'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - giugno 2008'
ms:assetid: 'ms08-jun'
ms:contentKeyID: 61240024
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms08-jun(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - giugno 2008
================================================================

Data di pubblicazione: martedì 10 giugno 2008 | Aggiornamento: mercoledì 1 aprile 2009

**Versione:** 2.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a giugno 2008.

Con il rilascio dei bollettini di giugno 2008, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 5 giugno 2008. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/policy).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini l'11 giugno 2008 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di giugno](http://msevents.microsoft.com/cui/webcasteventdetails.aspx?eventid=1032357225&eventcategory=4&culture=en-us&countrycode=us). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/default).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione e ad alta priorità pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

I bollettini sulla sicurezza di questo mese sono i seguenti, in ordine di gravità:

Critico (3)
-----------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-030                                                                                                                                                                                                                                                                                                                                                                                                                      |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità nello stack Bluetooth può consentire l'esecuzione di codice in modalità remota (951376)**](http://technet.microsoft.com/it-it/security/default.aspx)                                                                                                                                                                                                                                                                                          |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente relativa allo stack Bluetooth in Windows, che può consentire l'esecuzione di codice in modalità remota. Sfruttando questa vulnerabilità, un utente malintenzionato potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                        |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                             |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-031                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Aggiornamento cumulativo per la protezione di Internet Explorer (950759)**](http://technet.microsoft.com/it-it/security/default.aspx)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve due tipi di vulnerabilità: una segnalata a Microsoft privatamente e l'altra divulgata a Microsoft pubblicamente. Il tipo di vulnerabilità segnalato privatamente può consentire l'esecuzione di codice in modalità remota, se un utente visualizza con Internet Explorer una pagina Web appositamente predisposta. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. Il tipo di vulnerabilità segnalato pubblicamente può consentire l'intercettazione di informazioni personali, se un utente visualizza con Internet Explorer una pagina Web appositamente predisposta. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Software interessato**        | **Microsoft Windows, Internet Explorer.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-033                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità in DirectX possono consentire l'esecuzione di codice in modalità remota (951698)**](http://www.microsoft.com/italy/security/msrc/default.mspx)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Riepilogo**                   | L'aggiornamento per la protezione risolve due vulnerabilità di Microsoft DirectX che potrebbero consentire l'esecuzione di codice in modalità remota al momento dell'apertura di un file multimediale appositamente predisposto. Tali vulnerabilità sono state segnalate a Microsoft privatamente. Sfruttando una di queste vulnerabilità, un utente malintenzionato potrebbe assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. |
| **Livello di gravità massimo**  | [Critico](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

Importante (3)
--------------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-034                                                                                                                                                                                                                                                                                                                                                                                                                          |
|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in WINS può consentire l'acquisizione di privilegi più elevati (948745)**](http://technet.microsoft.com/security/bulletin/ms08-034)                                                                                                                                                                                                                                                                                                               |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente a Microsoft e presente in Windows Internet Name Service (WINS), che potrebbe consentire l'acquisizione di privilegi più elevati. Sfruttando questa vulnerabilità, un utente malintenzionato locale potrebbe assumere il pieno controllo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Effetti della vulnerabilità** | Acquisizione di privilegi più elevati                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                               |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                 |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-035                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Una vulnerabilità in Active Directory può consentire un attacco di tipo Denial of Service (953235)**](http://technet.microsoft.com/security/bulletin/ms08-035)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente relativa alle implementazioni di Active Directory in Microsoft Windows 2000 Server, Windows Server 2003 e Windows Server 2008, di ADAM (Active Directory Application Mode) se installato in Windows XP Professional e Windows Server 2003 e di AD LDS (Active Directory Lightweight Directory Service) se installato in Windows Server 2008. Sfruttando questa vulnerabilità, un utente malintenzionato può causare una condizione di attacco di tipo Denial of Service. In Windows XP Professional, Windows Server 2003 e Windows Server 2008 un utente malintenzionato deve disporre di credenziali di accesso valide per sfruttare questa vulnerabilità. Un utente malintenzionato potrebbe sfruttare la vulnerabilità impedendo al sistema di rispondere alle richieste o forzandone il riavvio automatico. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Effetti della vulnerabilità** | Denial of Service                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-036                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Alcune vulnerabilità nel protocollo PGM (Pragmatic General Multicast) possono consentire un attacco di tipo Denial of Service (950762)**](http://technet.microsoft.com/it-it/security/default.aspx)                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente nel protocollo PGM (Pragmatic General Multicast) che possono consentire un attacco di tipo Denial of Service se il sistema interessato riceve pacchetti PGM errati. Sfruttando questa vulnerabilità, un utente malintenzionato può causare il blocco del sistema e rendere necessario il riavvio per il ripristino del normale funzionamento. Si noti che la vulnerabilità ad attacchi di tipo Denial of Service non consente di eseguire codice o acquisire diritti utente più elevati, ma può impedire al sistema interessato di accettare richieste. |
| **Livello di gravità massimo**  | [Importante](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Effetti della vulnerabilità** | Denial of Service                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per l'aggiornamento è necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |

Moderato (1)
------------

<span></span>

| Identificatore del bollettino   | Bollettino Microsoft sulla sicurezza MS08-032                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Titolo del bollettino**       | [**Aggiornamento cumulativo per la protezione dei kill bit di ActiveX (950760)**](http://technet.microsoft.com/it-it/security/default.aspx)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Riepilogo**                   | Questo aggiornamento per la protezione risolve una vulnerabilità segnalata pubblicamente per l'API del motore di sintesi vocale Microsoft. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer e ha attivato la funzionalità di riconoscimento vocale di Windows. Gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. Questo aggiornamento include inoltre un kill bit per il software prodotto da BackWeb. |
| **Livello di gravità massimo**  | [Moderato](http://technet.microsoft.com/security/bulletin/rating)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Effetti della vulnerabilità** | Esecuzione di codice in modalità remota                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **Rilevamento**                 | Con Microsoft Baseline Security Analyzer, è possibile verificare se è necessario installare questo aggiornamento. Per questo aggiornamento potrebbe essere necessario riavviare il sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Software interessato**        | **Microsoft Windows.** Per ulteriori informazioni, vedere la sezione Software interessato e posizioni per il download.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |

Software interessato e posizioni per il download
------------------------------------------------

<span></span>
**Come utilizzare questa tabella**

È possibile utilizzare questa tabella per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se è necessario applicare i relativi aggiornamenti per la protezione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.

**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.

#### Sistema operativo Windows e server

 
<table style="border:1px solid black;">
<caption>Microsoft Windows 2000</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-030</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-031</strong></a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/security/msrc/default.mspx"><strong>MS08-033</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-034"><strong>MS08-034</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-035"><strong>MS08-035</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-036</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-032</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Moderato</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Microsoft Windows 2000 Service Pack 4</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=88990b23-d37f-4d02-a5a3-2ee389ade53c">Microsoft Internet Explorer 5.01 Service Pack 4</a><br />
(Importante)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=4c47cf8a-8100-4d43-855a-f225a3492b19">Microsoft Internet Explorer 6 Service Pack 1</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=65640123-a9e4-455c-a51a-9df28bd2d412">DirectX 7.0</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=c6a28d45-13cf-48c4-8f89-3417d552e90b">DirectX 8.1</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=4dc47e04-5e95-4636-a814-3f912d961461">DirectX 9.0, DirectX 9.0a, DirectX 9.0b o DirectX 9.0c</a><br />
(Critico)</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=cedfd988-232c-4cba-ac65-beb54b8946e0">Microsoft Windows 2000 Service Pack 4</a><br />
(Moderato)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Microsoft Windows 2000 Server Service Pack 4</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=aa8aa79f-c2cc-440c-9e5c-089143e6f814">Microsoft Windows 2000 Server Service Pack 4</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=53438880-9ea9-4975-9b85-2a1d3d232793">Active Directory</a><br />
(KB949014)<br />
(Importante)</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
</tr>
</tbody>
</table>

 
<table style="border:1px solid black;">
<caption>Windows XP</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-030</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-031</strong></a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/security/msrc/default.mspx"><strong>MS08-033</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-034"><strong>MS08-034</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-035"><strong>MS08-035</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-036</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-032</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Moderato</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows XP Service Pack 2 e Windows XP Service Pack 3</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=980bb421-950f-4825-8039-44cc961a47b8">Windows XP Service Pack 2 e Windows XP Service Pack 3</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=cc325017-3a48-4475-90e4-0c79a002fce3">Microsoft Internet Explorer 6</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=fbc31bde-0bf5-490c-96a8-071310d9464a">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=7aaa6427-1e22-4566-960c-836a3b9e5f36">DirectX 9.0, DirectX 9.0a, DirectX 9.0b o DirectX 9.0c</a><br />
(Critico)</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=36b14a81-5979-4e38-9ba3-ed83dfc17adf">Windows XP Service Pack 2 e Windows XP Service Pack 3</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=2d8957c2-e473-4dca-8d68-19fdaea36e26">Windows XP Service Pack 2 e Windows XP Service Pack 3</a><br />
(Moderato)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows XP Professional Service Pack 2 e Windows XP Professional Service Pack 3</td>
<td style="border:1px solid black;">(Vedere la riga Windows XP Service Pack 2 e Windows XP Service Pack 3)</td>
<td style="border:1px solid black;">(Vedere la riga Windows XP Service Pack 2 e Windows XP Service Pack 3)</td>
<td style="border:1px solid black;">(Vedere la riga Windows XP Service Pack 2 e Windows XP Service Pack 3)</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=7d6aec31-cfb4-470c-983e-78c6a3ebabfe">ADAM</a><br />
(KB949269)<br />
(Moderato)</td>
<td style="border:1px solid black;">(Vedere la riga Windows XP Service Pack 2 e Windows XP Service Pack 3)</td>
<td style="border:1px solid black;">(Vedere la riga Windows XP Service Pack 2 e Windows XP Service Pack 3)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=81ab56ca-933f-4974-a393-290a54c30a78">Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=c8783cfe-9da5-4842-ab3a-1e2be4fafc47">Microsoft Internet Explorer 6</a><br />
(Critico)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=19c0ccdc-95c9-4151-96b6-4f49b594ebe0">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=5e8e7e9d-828d-442c-acac-8d91e80dfb36">DirectX 9.0, DirectX 9.0a, DirectX 9.0b o DirectX 9.0c</a><br />
(Critico)</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=ef2e0b48-1bde-4ccc-8f40-2918c2568b2b">ADAM</a><br />
(KB949269)<br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=9e9d24ee-8183-428c-8067-168a8d85eaa1">Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=62874096-7d17-4116-9795-4756e2fb6dae">Windows XP Professional x64 Edition e Windows XP Professional x64 Edition Service Pack 2</a><br />
(Moderato)</td>
</tr>
</tbody>
</table>
 

 
<table style="border:1px solid black;">
<caption>Windows Server 2003</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-030</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-031</strong></a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/security/msrc/default.mspx"><strong>MS08-033</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-034"><strong>MS08-034</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-035"><strong>MS08-035</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-036</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-032</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Moderato</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=286aada6-a358-41f1-b81a-8de39b9f908a">Microsoft Internet Explorer 6</a><br />
(Moderato)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=a1ae9ad2-8329-4c96-b950-7534b3287eaa">Windows Internet Explorer 7</a><br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=2274ecb2-2802-47e2-84fd-6621fcb17758">DirectX 9.0, DirectX 9.0a, DirectX 9.0b o DirectX 9.0c</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=08fc90d5-23aa-4327-8aef-16bc5170769d">Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=a4aed117-3c76-4d80-b50e-8e07e2ef2f7d">Active Directory</a><br />
(KB949014)<br />
(Moderato)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=0a983ffb-4f5a-4b78-9bf5-813dcc5df8d3">ADAM</a><br />
(KB949269)<br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=1e8e2faf-009f-403b-a5fe-a47cf014db3a">Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=dadead99-09cb-4f2b-850d-e98a627cb9f8">Windows Server 2003 Service Pack 1 e Windows Server 2003 Service Pack 2</a><br />
(Basso)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=6604569a-3db0-47e7-bd30-7dfba8145386">Microsoft Internet Explorer 6</a><br />
(Moderato)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=fb0c70b4-ce9f-43d6-875a-3cfd0d3a2681">Windows Internet Explorer 7</a><br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=5ba63bb7-ed6d-4c59-88b3-456eda07e190">DirectX 9.0, DirectX 9.0a, DirectX 9.0b o DirectX 9.0c</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=71675ae8-d60a-4834-b358-2d8e761e62fc">Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=8298a6e4-d3e2-48ea-ac29-aa4dc5a8ec77">Active Directory</a><br />
(KB949014)<br />
(Moderato)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=334252db-4a7a-4161-bb71-2a20c0b5bd93">ADAM</a><br />
(KB949269)<br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=78bf92d8-63c4-4596-8425-8fcfea7f5582">Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=84f9b533-b0cb-46d1-b4a8-5c9469abbd22">Windows Server 2003 x64 Edition e Windows Server 2003 x64 Edition Service Pack 2</a><br />
(Basso)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=0262beb8-1eb5-4c2d-a50a-0c6c6e0c1f61">Microsoft Internet Explorer 6</a><br />
(Moderato)<br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=28d2913c-1c6b-4671-9892-de08698cd5a6">Windows Internet Explorer 7</a><br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=be71c002-2f64-49e9-9f4b-ba99c4f3caf6">DirectX 9.0, DirectX 9.0a, DirectX 9.0b o DirectX 9.0c</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=87affdc9-d9fe-413c-af30-f3d3b671ec72">Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=f6bf4b85-b91d-4378-a356-cd11f12cbbfd">Active Directory</a><br />
(KB949014)<br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=5b7e94fa-22ed-4f7c-b452-647b2e620113">Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium</a><br />
(Importante)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=ac35ce19-d761-4529-9f55-1e1b5b2447ad">Windows Server 2003 con SP1 per sistemi basati su Itanium e Windows Server 2003 con SP2 per sistemi basati su Itanium</a><br />
(Basso)</td>
</tr>
</tbody>
</table>
 

 
<table style="border:1px solid black;">
<caption>Windows Vista</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-030</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-031</strong></a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/security/msrc/default.mspx"><strong>MS08-033</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-034"><strong>MS08-034</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-035"><strong>MS08-035</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-036</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-032</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Moderato</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Vista e Windows Vista Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=6524debe-be50-44d1-8543-af0bfaf086ad">Windows Vista e Windows Vista Service Pack 1</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=6d68b39d-157f-4c3d-ac76-bc5a9386db59">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=4d4b305b-57f8-448d-92fa-3dcdd1f42ed7">DirectX 10.0</a><br />
(Critico)</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=ef2d2a4b-4831-41be-b5d0-8df5b01fd205">Windows Vista e Windows Vista Service Pack 1</a><br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=4af6575e-b061-45a6-b3d8-ecb32d76b2d3">Windows Vista e Windows Vista Service Pack 1</a><br />
(Moderato)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=6adee8b9-3455-4f3b-8bdd-2585c8ff83b8">Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=4cf92235-861e-4b74-bee3-8e977c8688d9">Windows Internet Explorer 7</a><br />
(Critico)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=b040cfad-2290-44f4-8f5a-5d1ed98a7265">DirectX 10.0</a><br />
(Critico)</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=0839fcf4-85ca-445e-896b-f634b10b6700">Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1</a><br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=67576acb-9cb6-4c76-9a72-dc5e5556b658">Windows Vista x64 Edition e Windows Vista x64 Edition Service Pack 1</a><br />
(Moderato)</td>
</tr>
</tbody>
</table>
 

 
<table style="border:1px solid black;">
<caption>Windows Server 2008</caption>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>Identificatore del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-030</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-031</strong></a></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/security/msrc/default.mspx"><strong>MS08-033</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-034"><strong>MS08-034</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/ms08-035"><strong>MS08-035</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-036</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/default.aspx"><strong>MS08-032</strong></a></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><strong>Livello di gravità massimo del bollettino</strong></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Critico</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Importante</strong></a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating"><strong>Moderato</strong></a></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2008 per sistemi a 32 bit</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=a8922e7e-9264-4e09-b8ad-c5420fed8690">Windows Internet Explorer 7</a><br />
(Moderato)<strong>**</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?displaylang=it&amp;familyid=c0c495f8-2a35-4638-a635-1e55dd15e062">DirectX 10.0</a><br />
(Critico)<strong>**</strong></td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=2981156e-2e2f-469e-91be-da127d50f3fc">Active Directory</a><br />
(KB949014)<br />
(Moderato)<strong>*</strong><br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=2981156e-2e2f-469e-91be-da127d50f3fc">AD LDS</a><br />
(KB949014)<br />
(Moderato)<strong>*</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=0466a6e7-fdca-4647-af62-449e5f20d1e4">Windows Server 2008 per sistemi a 32 bit</a><br />
(Moderato)<strong>**</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=8a507fba-8c93-4952-91e4-98e9e7affbd2">Windows Server 2008 per sistemi a 32 bit</a><br />
(Basso)<strong>***</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;">Windows Server 2008 per sistemi basati su x64</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=05b0e838-24d7-4387-b069-2604bbcc43b9">Windows Internet Explorer 7</a><br />
(Moderato)<strong>**</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=0b70fc2e-4e80-4ae8-8682-41ea04c24e4e">DirectX 10.0</a><br />
(Critico)<strong>**</strong></td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=b5cfe6f4-c5ba-4be9-a6b8-9381c40c85aa">Active Directory</a><br />
(KB949014)<br />
(Moderato)<strong>*</strong><br />
<br />
<a href="http://www.microsoft.com/downloads/details.aspx?familyid=b5cfe6f4-c5ba-4be9-a6b8-9381c40c85aa">AD LDS</a><br />
(KB949014)<br />
(Moderato)<strong>*</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=304898e6-21a7-476f-b9ed-7ac0d88a91e2">Windows Server 2008 per sistemi x64</a><br />
(Moderato)<strong>**</strong></td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=1a11499d-a008-407f-9084-a5189fa27015">Windows Server 2008 per sistemi x64</a><br />
(Basso)<strong>***</strong></td>
</tr>
<tr class="odd">
<td style="border:1px solid black;">Windows Server 2008 per sistemi basati su Itanium</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=640e1865-ebcc-4d69-a770-fd360020da1e">Windows Internet Explorer 7</a><br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=80ec83e0-cfb8-4a5e-9254-6679a7225b83">DirectX 10.0</a><br />
(Critico)</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=8907783b-e3fe-40b2-9fc8-4937e7d58b7e">Windows Server 2008 per sistemi basati su Itanium</a><br />
(Moderato)</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/downloads/details.aspx?familyid=59b1689c-e723-4d87-973e-4beac107a6f7">Windows Server 2008 per sistemi basati su Itanium</a><br />
(Basso)</td>
</tr>
</tbody>
</table>
 

**\*Sono interessate le installazione di Windows Server 2008 con opzione Server Core.** Per le edizioni supportate di Windows Server 2008, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*Le installazioni di Windows Server 2008 con opzione Server Core non sono interessate.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008, se Windows Server 2008 è stato installato utilizzando l'opzione di installazione dei componenti di base del server. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

**\*\*\*Sebbene l'installazione dei componenti di base del server di Windows Server 2008 non sia interessata da queste vulnerabilità, l'aggiornamento verrà comunque offerto.** Le vulnerabilità affrontate da questo aggiornamento non interessano le edizioni supportate di Windows Server 2008, se è stato installato utilizzando l'opzione di installazione dei componenti di base del server, anche se i file interessati da queste vulnerabilità sono presenti nel sistema. L'aggiornamento viene comunque offerto agli utenti che dispongono dei file interessati, poiché i file dell'aggiornamento sono più recenti (con numeri di versione più elevati) rispetto a quelli attualmente presenti nel sistema. Per ulteriori informazioni su questa opzione di installazione, vedere [Server Core](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008; vedere [Compare Server Core Installation Options](http://msdn.microsoft.com/it-it/library/ms723891(vs.85).aspx).

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

-   Sebastian Apelt, Peter Vreugdenhil e un ricercatore anonimo, che collaborano con [Tipping Point](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-031.
-   Mark Dowd, ricercatore presso la [IBM Internet Security Systems X-Force](http://xforce.iss.net/), per aver segnalato un problema descritto nel bollettino MS08-033.
-   Un ricercatore anonimo, collaboratore di [TippingPoint](http://www.tippingpoint.com/) e [Zero Day Initiative](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS08-033.
-   Alex Matthews e John Guzik di [Securify](http://www.securify.com/) per aver segnalato un problema descritto nel bollettino MS08-035.

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito del [Servizio Supporto Tecnico Clienti Microsoft](http://support.microsoft.com/?ln=it&x=15&y=11). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite.
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (10 giugno 2008): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (11 giugno 2008): È stata corretta la tabella Software interessato per Windows XP in modo da chiarire le voci per Windows XP Service Pack 2 e Windows XP Service Pack 3 per MS08-030, MS08-031, MS08-032, MS08-033 e MS08-036.
-   V2.0 (16 luglio 2008): DirectX 9.0a è stato aggiunto all'elenco del software interessato per MS08-033.
-   V2.1 (01 aprile 2009): Per il bollettino MS08-032, è stato chiarito che le installazioni dei componenti di base del server di Windows Server 2008 non sono interessate dalla vulnerabilità trattata nel bollettino, ma l'aggiornamento verrà offerto comunque. La modifica è esclusivamente informativa. Per gli utenti che utilizzano queste installazioni non è necessario installare questo aggiornamento.

*Built at 2014-04-18T01:50:00Z-07:00*
