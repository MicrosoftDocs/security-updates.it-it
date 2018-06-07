---
TOCTitle: 'MS13-MAR'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Marzo 2013'
ms:assetid: 'ms13-mar'
ms:contentKeyID: 61240085
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms13-mar(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Marzo 2013
===============================================================

Data di pubblicazione: martedì 12 marzo 2013 | Aggiornamento: venerdì 15 marzo 2013

**Versione:** 1.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a marzo 2013.

Con il rilascio dei bollettini sulla sicurezza di marzo 2013, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 7 marzo 2013. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini il 13 marzo 2013 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di marzo](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032538636&culture=en-us). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032538636&culture=en-us).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

### Informazioni sui bollettini

#### Riepiloghi

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=279923">MS13-021</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2809289)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve otto vulnerabilità segnalate privatamente e una vulnerabilità divulgata pubblicamente relative a Internet Explorer. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=275737">MS13-022</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Silverlight può consentire l'esecuzione di codice in modalità remota (2814124)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Silverlight che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato ospita un sito Web che contiene un'applicazione Silverlight appositamente predisposta, in grado di sfruttare questa vulnerabilità, e convince un utente a visualizzare il sito Web. L'utente malintenzionato può inoltre servirsi di siti Web manomessi e di siti Web che accettano o pubblicano contenuti o annunci pubblicitari inviati da altri utenti. Tali siti Web possono includere contenuti appositamente predisposti in grado di sfruttare questa vulnerabilità. Tuttavia, non è in alcun modo possibile per un utente malintenzionato obbligare gli utenti a visitare tale sito Web. L'utente malintenzionato deve convincere le vittime a visitare un sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che le indirizzi al sito. Può inoltre far visualizzare contenuti Web appositamente predisposti utilizzando banner pubblicitari o altre modalità di invio di contenuti Web ai sistemi interessati.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Microsoft Silverlight</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=276801">MS13-023</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Visio Viewer 2010 può consentire l'esecuzione di codice in modalità remota (2801261)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file Visio appositamente predisposto. Sfruttando tale vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=271610">MS13-024</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in SharePoint possono consentire l'acquisizione di privilegi più elevati (2780176)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve quattro vulnerabilità di Microsoft SharePoint e Microsoft SharePoint Foundation segnalate privatamente. Le vulnerabilità più severe possono consentire l'acquisizione di privilegi più elevati se un utente fa clic su un URL appositamente predisposto che lo indirizzi a un determinato sito SharePoint.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office, Software dei server Microsoft</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=282355">MS13-025</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft OneNote può consentire l'intercettazione di informazioni personali (2816264)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft OneNote. La vulnerabilità può consentire l'intercettazione di informazioni personali se un utente malintenzionato convince un utente ad aprire un file di OneNote appositamente predisposto.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=280673">MS13-026</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in</strong> <strong>Microsoft Office</strong> <strong>per Mac può consentire l'intercettazione di informazioni personali (2813682)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft Office per Mac. Questa vulnerabilità può consentire l'intercettazione di informazioni personali se un utente apre un messaggio di posta elettronica appositamente predisposto.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Intercettazione di informazioni personali</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=282639">MS13-027</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel possono consentire l'acquisizione di privilegi più elevati (2807986)</strong> <strong><br />
<br />
</strong>Questo aggiornamento per la protezione risolve tre vulnerabilità segnalate privatamente in Microsoft Windows. Queste vulnerabilità possono consentire l'acquisizione di privilegi più elevati se un utente malintenzionato riesce ad accedere a un sistema.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259).
  
Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.
  
| ID bollettino                                             | Titolo della vulnerabilità                                                                             | ID CVE                                                                           | Valutazione dell'Exploitability per la versione più recente del software                                              | Valutazione dell'Exploitability per la versione meno recente del software                                             | Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service | Note fondamentali                                                          |  
|-----------------------------------------------------------|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|----------------------------------------------------------------------------|  
| [MS13-021](http://go.microsoft.com/fwlink/?linkid=279923) | Vulnerabilità legata a un errore di tipo use-after-free in OnResize in Internet Explorer               | [CVE-2013-0087](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0087) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-021](http://go.microsoft.com/fwlink/?linkid=279923) | Vulnerabilità legata a un errore di tipo use-after-free in saveHistory in Internet Explorer            | [CVE-2013-0088](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0088) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-021](http://go.microsoft.com/fwlink/?linkid=279923) | Vulnerabilità legata a un errore di tipo use-after-free in CMarkupBehaviorContext in Internet Explorer | [CVE-2013-0089](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0089) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-021](http://go.microsoft.com/fwlink/?linkid=279923) | Vulnerabilità legata a un errore di tipo use-after-free in CCaret in Internet Explorer                 | [CVE-2013-0090](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0090) | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Difficile costruire il codice dannoso                | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-021](http://go.microsoft.com/fwlink/?linkid=279923) | Vulnerabilità legata a un errore di tipo use-after-free in CElement in Internet Explorer               | [CVE-2013-0091](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0091) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-021](http://go.microsoft.com/fwlink/?linkid=279923) | Vulnerabilità legata a un errore di tipo use-after-free in GetMarkupPtr in Internet Explorer           | [CVE-2013-0092](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0092) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-021](http://go.microsoft.com/fwlink/?linkid=279923) | Vulnerabilità legata a un errore di tipo use-after-free in onBeforeCopy in Internet Explorer           | [CVE-2013-0093](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0093) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-021](http://go.microsoft.com/fwlink/?linkid=279923) | Vulnerabilità legata a un errore di tipo use-after-free in removeChild in Internet Explorer            | [CVE-2013-0094](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0094) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-021](http://go.microsoft.com/fwlink/?linkid=279923) | Vulnerabilità legata a un errore di tipo use-after-free in CTreeNode in Internet Explorer              | [CVE-2013-1288](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1288) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.    |  
| [MS13-022](http://go.microsoft.com/fwlink/?linkid=275737) | Vulnerabilità legata alla duplice risoluzione del riferimento in Silverlight                           | [CVE-2013-0074](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0074) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                                                       | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-023](http://go.microsoft.com/fwlink/?linkid=276801) | Vulnerabilità legata alla confusione dei tipi di oggetto albero di Visio Viewer                        | [CVE-2013-0079](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0079) | Non interessato                                                                                                       | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Difficile costruire il codice dannoso                | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-024](http://go.microsoft.com/fwlink/?linkid=271610) | Vulnerabilità legata alla funzione di callback                                                         | [CVE-2013-0080](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0080) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-024](http://go.microsoft.com/fwlink/?linkid=271610) | Vulnerabilità XSS di SharePoint                                                                        | [CVE-2013-0083](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0083) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-024](http://go.microsoft.com/fwlink/?linkid=271610) | Vulnerabilità legata all'attraversamento delle directory in SharePoint                                 | [CVE-2013-0084](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0084) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS13-024](http://go.microsoft.com/fwlink/?linkid=271610) | Vulnerabilità legata al sovraccarico del buffer                                                        | [CVE-2013-0085](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0085) | Non interessato                                                                                                       | [3](http://technet.microsoft.com/security/cc998259) - Scarsa probabilità di sfruttamento della vulnerabilità          | Temporaneo                                                                       | Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.      |  
| [MS13-025](http://go.microsoft.com/fwlink/?linkid=282355) | Vulnerabilità legata alla convalida delle dimensioni del buffer                                        | [CVE-2013-0086](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0086) | Non interessato                                                                                                       | [3](http://technet.microsoft.com/security/cc998259) - Scarsa probabilità di sfruttamento della vulnerabilità          | Non applicabile                                                                  | Questa vulnerabilità riguarda l'intercettazione di informazioni personali. |  
| [MS13-026](http://go.microsoft.com/fwlink/?linkid=280673) | Vulnerabilità legata al caricamento non intenzionale di contenuto                                      | [CVE-2013-0095](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-0095) | [3](http://technet.microsoft.com/security/cc998259) - Scarsa probabilità di sfruttamento della vulnerabilità          | [3](http://technet.microsoft.com/security/cc998259) - Scarsa probabilità di sfruttamento della vulnerabilità          | Non applicabile                                                                  | Questa vulnerabilità riguarda l'intercettazione di informazioni personali. |  
| [MS13-027](http://go.microsoft.com/fwlink/?linkid=282639) | Vulnerabilità legata al descrittore USB di Windows                                                     | [CVE-2013-1285](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1285) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                  |  
| [MS13-027](http://go.microsoft.com/fwlink/?linkid=282639) | Vulnerabilità legata al descrittore USB di Windows                                                     | [CVE-2013-1286](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1286) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                  |  
| [MS13-027](http://go.microsoft.com/fwlink/?linkid=282639) | Vulnerabilità legata al descrittore USB di Windows                                                     | [CVE-2013-1287](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-1287) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | Permanente                                                                       | (Nessuna)                                                                  |
  
Software interessato e percorsi per il download  
-----------------------------------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.
  
**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.
  
#### Sistema operativo Windows e suoi componenti

 
<table style="border:1px solid black;">
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
[**MS13-021**](http://go.microsoft.com/fwlink/?linkid=279923)
</td>
<td style="border:1px solid black;">
[**MS13-027**](http://go.microsoft.com/fwlink/?linkid=282639)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=ace6994d-7482-40de-84ad-a87853a35860)  
(2809289)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=50c59794-4ec7-404a-b316-dae314521ebb)  
(2809289)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=7e5d96a7-d9f5-4832-b4f9-b6e0148c655b)  
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=ba528d03-b0a6-40a5-a6bd-13c062a8a877)  
(2807986)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=795cef4e-9c01-447f-916c-e52e69eca4a3)  
(2809289)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=16993a2c-1fe1-4c1e-bcd9-db1a7dd4a058)  
(2809289)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=66a08524-883d-4d67-82cc-2c0f55c56b31)  
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4f8a48d4-b1bb-465c-a232-d29fe94d1429)  
(2807986)  
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
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-021**](http://go.microsoft.com/fwlink/?linkid=279923)
</td>
<td style="border:1px solid black;">
[**MS13-027**](http://go.microsoft.com/fwlink/?linkid=282639)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=e3c911b3-7fdd-4105-a20a-eef65b0908e3)  
(2809289)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=0f58d63e-0d2c-41d2-9792-edbb2f4a539d)  
(2809289)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=e6b63da9-a414-40ee-b877-4fb0d62bacba)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=835651b7-79fb-4d50-b48e-f02173062253)  
(2807986)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=eaf2c568-089a-4c2f-bca6-da83f7332de9)  
(2809289)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=5a18b139-2773-44c8-85f9-8dce24249e71)  
(2809289)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d6feba92-f014-4521-b6c4-7f5f358a3ce3)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=9d5f1ed1-f33b-4c90-9b29-ee8ac587d31b)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=088fd3ec-62e1-4737-8132-6b51219ed37f)  
(2809289)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=799748d8-056d-4139-86e1-9bd0cb0151b4)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=28d441e7-abcf-4cc9-84e0-572e5b79aab7)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-021**](http://go.microsoft.com/fwlink/?linkid=279923)
</td>
<td style="border:1px solid black;">
[**MS13-027**](http://go.microsoft.com/fwlink/?linkid=282639)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=0bf77905-1199-4219-a67d-1e9ad3f63757)  
(2809289)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=76e328f8-4f86-4e50-b7e0-22db0385ab01)  
(2809289)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=c26f74fc-e224-4533-a4e3-b52125dca5cd)  
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=b8472bc7-9e20-4238-adcf-a1e1a91687a1)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=7b652bb4-7a0a-437b-bcc5-ebbbb820c559)  
(2809289)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=67b09398-ceb6-403c-bba4-261d9d9dea98)  
(2809289)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=3f1795a5-4376-4929-8748-743840ec2154)  
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e412c54a-a93d-4c5b-9b13-40b59d1dff35)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-021**](http://go.microsoft.com/fwlink/?linkid=279923)
</td>
<td style="border:1px solid black;">
[**MS13-027**](http://go.microsoft.com/fwlink/?linkid=282639)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=0303fcb1-34d5-47da-b6ee-18222fe3235a)  
(2809289)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=337068a5-9281-4db6-9ff1-5282cdfa0763)  
(2809289)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=c672c196-5072-468c-8d88-34534fa219fd)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f1ca4fe0-3ee3-4162-a9fa-48c54fc8b08e)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=f22b9327-1430-44cb-a609-ea1bb9b7b8f8)  
(2809289)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=0496cbfe-77d2-4de6-b78d-937225dc8974)  
(2809289)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=5c40f237-b4c8-41eb-a649-baad46dfa13c)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8b61f3e5-0cf9-4eab-8a59-829957135dd6)  
(2807986)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=09e4832c-b95e-4581-a73b-49cb6a60c1df)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=af2e8e83-fb8f-4ba5-83ec-8bd4347a5fe6)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-021**](http://go.microsoft.com/fwlink/?linkid=279923)
</td>
<td style="border:1px solid black;">
[**MS13-027**](http://go.microsoft.com/fwlink/?linkid=282639)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi 32-bit
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=b07b63d5-925d-4c4f-ae19-18a9b141eaa0)  
(2809289)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=54c619b7-e156-4f07-a90e-56ed9a618085)  
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=c72f78be-e6a8-43b4-9303-7c93dd11d502)  
(2807986)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=b07b63d5-925d-4c4f-ae19-18a9b141eaa0)  
(2809289)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=54c619b7-e156-4f07-a90e-56ed9a618085)  
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c72f78be-e6a8-43b4-9303-7c93dd11d502)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=610da6c6-e8a9-4726-ae54-11f01fb5ab2d)  
(2809289)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=86f2a369-d71d-4a36-95ed-d5be89cbbbae)  
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=6a8a22d6-0e6e-4d3b-afd0-d4841274ade0)  
(2807986)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=610da6c6-e8a9-4726-ae54-11f01fb5ab2d)  
(2809289)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=86f2a369-d71d-4a36-95ed-d5be89cbbbae)  
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=6a8a22d6-0e6e-4d3b-afd0-d4841274ade0)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-021**](http://go.microsoft.com/fwlink/?linkid=279923)
</td>
<td style="border:1px solid black;">
[**MS13-027**](http://go.microsoft.com/fwlink/?linkid=282639)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=cf5f65e1-93ae-4ec3-84d2-eb017efdc9d6)  
(2809289)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=c5018865-7162-4d8d-86fc-aacd6d5f0a37)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=84ba3686-14ed-4aac-8db1-4438aa9e0a2e)  
(2807986)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=cf5f65e1-93ae-4ec3-84d2-eb017efdc9d6)  
(2809289)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=c5018865-7162-4d8d-86fc-aacd6d5f0a37)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=84ba3686-14ed-4aac-8db1-4438aa9e0a2e)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=3436d1d1-bf20-40cc-8c51-f093da67c8a9)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=01498cd0-e27e-4256-8f21-7a6eeedfb77c)  
(2807986)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=3436d1d1-bf20-40cc-8c51-f093da67c8a9)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=01498cd0-e27e-4256-8f21-7a6eeedfb77c)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows 8
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-021**](http://go.microsoft.com/fwlink/?linkid=279923)
</td>
<td style="border:1px solid black;">
[**MS13-027**](http://go.microsoft.com/fwlink/?linkid=282639)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
[Internet Explorer 10](http://www.microsoft.com/downloads/details.aspx?familyid=7c348fe3-f4f0-4f22-8a7f-8563705c1f64)  
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 8 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=de4ec125-c337-4615-b39b-8456658dae22)  
(2807986)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit
</td>
<td style="border:1px solid black;">
[Internet Explorer 10](http://www.microsoft.com/downloads/details.aspx?familyid=0c503b83-5b13-41da-a5ff-7519bc244521)  
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 8 per sistemi a 64 bit](http://www.microsoft.com/downloads/details.aspx?familyid=c1539e94-0635-4f51-8172-a96a737d81d3)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows Server 2012
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-021**](http://go.microsoft.com/fwlink/?linkid=279923)
</td>
<td style="border:1px solid black;">
[**MS13-027**](http://go.microsoft.com/fwlink/?linkid=282639)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012
</td>
<td style="border:1px solid black;">
[Internet Explorer 10](http://www.microsoft.com/downloads/details.aspx?familyid=f9b299f1-8a73-40b2-9942-e6419496bb39)  
(2809289)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2012](http://www.microsoft.com/downloads/details.aspx?familyid=959c78e1-29d9-40a3-9eb3-1206c09e3752)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows RT
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-021**](http://go.microsoft.com/fwlink/?linkid=279923)
</td>
<td style="border:1px solid black;">
[**MS13-027**](http://go.microsoft.com/fwlink/?linkid=282639)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows RT
</td>
<td style="border:1px solid black;">
Internet Explorer 10<sup>[1]</sup>
(2809289)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="3">
Opzione di installazione Server Core
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-021**](http://go.microsoft.com/fwlink/?linkid=279923)
</td>
<td style="border:1px solid black;">
[**MS13-027**](http://go.microsoft.com/fwlink/?linkid=282639)
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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f1ca4fe0-3ee3-4162-a9fa-48c54fc8b08e) (installazione Server Core)  
(2807986)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=8b61f3e5-0cf9-4eab-8a59-829957135dd6) (installazione Server Core)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=84ba3686-14ed-4aac-8db1-4438aa9e0a2e) (installazione Server Core)  
(2807986)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=84ba3686-14ed-4aac-8db1-4438aa9e0a2e) (installazione Server Core)  
(2807986)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2012](http://www.microsoft.com/downloads/details.aspx?familyid=959c78e1-29d9-40a3-9eb3-1206c09e3752) (installazione Server Core)  
(2807986)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS13-021**

<sup>[1]</sup>Gli aggiornamenti per la protezione di Windows RT sono forniti tramite [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="4">
Software Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-023**](http://go.microsoft.com/fwlink/?linkid=276801)
</td>
<td style="border:1px solid black;">
[**MS13-025**](http://go.microsoft.com/fwlink/?linkid=282355)
</td>
<td style="border:1px solid black;">
[**MS13-026**](http://go.microsoft.com/fwlink/?linkid=280673)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visio Viewer 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Visio Viewer 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=b01b4410-1107-472f-bf96-234304e91e77)  
(2687505)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visio Viewer 2010 Service Pack 1 (edizione a 64-bit)
</td>
<td style="border:1px solid black;">
[Microsoft Visio Viewer 2010 Service Pack 1 (edizione a 64-bit)](http://www.microsoft.com/downloads/details.aspx?familyid=24065dd5-251b-4a3c-bb44-8d552a1f265e)  
(2687505)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visio 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Visio 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=7a1a21e7-3137-4201-a005-cc66379fc1c5)  
(2760762)  
(Nessun livello di gravità)<sup>[1]</sup>
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Visio 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Visio 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=7b7d39f0-a341-4d48-8177-329cccb5a7f1)  
(2760762)  
(Nessun livello di gravità)<sup>[1]</sup>
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Filter Pack Service Pack 1 (versione a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2010 Filter Pack Service Pack 1 (versione a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=f10db48f-a980-47bf-83a5-c0da4e615114)  
(2553501)  
(Nessun livello di gravità)<sup>[1]</sup>
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Filter Pack Service Pack 1 (versione a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2010 Filter Pack Service Pack 1 (versione a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=70d3372b-74a8-4b68-b6c4-18863835915d)  
(2553501)  
(Nessun livello di gravità)<sup>[1]</sup>
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft OneNote 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft OneNote 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=da4bfd31-65b9-496b-aa98-4fa8b729dcf3)  
(2760600)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft OneNote 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft OneNote 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=10fc7350-e1d4-40b6-a5d1-8670263faf05)  
(2760600)  
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=d7aef20a-922b-4495-b473-1afa4a7ac514)  
(2817449)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office per Mac 2011
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office per Mac 2011](http://www.microsoft.com/downloads/details.aspx?familyid=4960674b-1cb4-499a-999e-7aa4d4c49e5e)  
(2817452)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS13-023**

<sup>[1]</sup>I livelli di gravità non si applicano a questo aggiornamento per il software specificato perché i vettori di attacco conosciuti per la vulnerabilità sono bloccati.

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Silverlight
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-022**](http://go.microsoft.com/fwlink/?linkid=275737)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Silverlight 5 installato in Mac
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 5](http://www.microsoft.com/downloads/details.aspx?familyid=75eef049-1f39-47b4-9a1e-839974fc89b9) installato in Mac  
(2814124)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Silverlight 5 Developer Runtime installato in Mac
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 5 Developer Runtime](http://www.microsoft.com/downloads/details.aspx?familyid=75eef049-1f39-47b4-9a1e-839974fc89b9) installato in Mac  
(2814124)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Silverlight 5 installato in tutte le versioni supportate dei client Microsoft Windows
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 5](http://www.microsoft.com/downloads/details.aspx?familyid=75eef049-1f39-47b4-9a1e-839974fc89b9) installato in tutte le versioni supportate dei client Microsoft Windows  
(2814124)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Silverlight 5 Developer Runtime installato in tutte le versioni supportate dei client Microsoft Windows
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 5 Developer Runtime](http://www.microsoft.com/downloads/details.aspx?familyid=75eef049-1f39-47b4-9a1e-839974fc89b9) installato in tutte le versioni supportate dei client Microsoft Windows  
(2814124)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Silverlight 5 installato in tutte le versioni supportate dei server Microsoft Windows
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 5](http://www.microsoft.com/downloads/details.aspx?familyid=75eef049-1f39-47b4-9a1e-839974fc89b9) installato in tutte le versioni supportate dei server Microsoft Windows  
(2814124)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Silverlight 5 Developer Runtime installato in tutte le versioni supportate dei server Microsoft Windows
</td>
<td style="border:1px solid black;">
[Microsoft Silverlight 5 Developer Runtime](http://www.microsoft.com/downloads/details.aspx?familyid=75eef049-1f39-47b4-9a1e-839974fc89b9) installato in tutte le versioni supportate dei server Microsoft Windows  
(2814124)  
(Critico)
</td>
</tr>
</table>
 

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft SharePoint Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-024**](http://go.microsoft.com/fwlink/?linkid=271610)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Server 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a9e8acbd-90e5-4acd-aa8f-b743a352787b)<sup>[1]</sup>
(wasrv)  
(2553407)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft SharePoint Foundation
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS13-024**](http://go.microsoft.com/fwlink/?linkid=271610)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Foundation 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Foundation 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=293666ec-3290-4c6f-a7f6-b44c9b7fa0a6)  
(2687418)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS13-024**

<sup>[1]</sup>Per le edizioni supportate di Microsoft SharePoint Server 2010, oltre al pacchetto di aggiornamento per la protezione per Microsoft SharePoint 2010 (2553407), i clienti devono installare anche l'aggiornamento per la protezione per Microsoft SharePoint Foundation 2010 (2687418) per essere protetti dalle vulnerabilità descritte in questo bollettino.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security TechCenter](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. I clienti possono visitare [Microsoft Safety &amp; Security Center](http://www.microsoft.com/italy/athome/security/default.mspx), dove queste informazioni sono disponibili anche facendo clic su "Aggiornamenti per la protezione".

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS13-001"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, vedere [Microsoft Baseline Security Analyzer](http://technet.microsoft.com/it-it/security/cc184924.aspx).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/wsus/default).

**SystemCenter Configuration Manager**

Gestione aggiornamenti software di System Center Configuration Manager semplifica la consegna e la gestione degli aggiornamenti dei sistemi IT in tutta l'azienda. Con System Center Configuration Manager, gli amministratori IT possono distribuire gli aggiornamenti dei prodotti Microsoft a diverse periferiche compresi desktop, portatili, server e dispositivi mobili.

La valutazione automatica della vulnerabilità disponibile in System Center Configuration Manager rileva la necessità di effettuare gli aggiornamenti ed invia relazioni sulle azioni consigliate. Gestione aggiornamenti software di System Center Configuration Manager si basa su Microsoft Windows Software Update Services (WSUS), un'infrastruttura di aggiornamento tempestiva conosciuta agli amministratori IT in tutto il mondo. Per ulteriori informazioni su System Center Configuration Manager, visitare il sito [Risorse tecniche di System Center](http://technet.microsoft.com/systemcenter/bb980621).

**Systems Management Server 2003**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali.

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager; vedere anche la sezione precedente, **System Center Configuration Manager**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/systemcenter/bb545936).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://technet.microsoft.com/library/cc917507.aspx). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. I componenti del programma [Update Compatibility Evaluator](http://technet.microsoft.com/library/cc749197), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971), consentono di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Per il rilascio dei bollettini che avviene il secondo martedì di ogni mese, Microsoft ha rilasciato una versione aggiornata dello Strumento di rimozione software dannoso di Microsoft Windows in Windows Update, Microsoft Update, Windows Server Update Services e nell'Area download. Non è disponibile alcuna versione dello Strumento di rimozione software dannoso di Microsoft Windows per i rilasci di bollettini sulla sicurezza straordinari.

#### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/wsus/bb456965). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://go.microsoft.com/fwlink/?linkid=215201).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

**MS13-021**

-   Arseniy Akuney di [TELUS Security Labs](http://telussecuritylabs.com/) per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in OnResize in Internet Explorer (CVE-2013-0087)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in saveHistory in Internet Explorer (CVE-2013-0088)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in CMarkupBehaviorContext in Internet Explorer (CVE-2013-0089)
-   Stephen Fewer di [Harmony Security](http://www.harmonysecurity.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in CCaret in Internet Explorer (CVE-2013-0090)
-   SkyLined, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in CCaret in Internet Explorer (CVE-2013-0090)
-   Jose A Vazquez di Yenteasy - Security Research, che collabora con [Exodus Intelligence](https://www.exodusintel.com/), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in CElement in Internet Explorer (CVE-2013-0091)
-   [Aniway.Aniway@gmail.com](mailto:aniway.aniway@gmail.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in GetMarkupPtr in Internet Explorer (CVE-2013-0092)
-   [Aniway.Aniway@gmail.com](mailto:aniway.aniway@gmail.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in onBeforeCopy in Internet Explorer (CVE-2013-0093)
-   Simon Zuckerbraun, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/)[di HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata a un errore di tipo use-after-free in removeChild in Internet Explorer (CVE-2013-0094)
-   Gen Chen di [Venustech](http://www.venustech.com.cn/) ADLab per aver collaborato con Microsoft sulla vulnerabilità legata a un errore di tipo use-after-free in CTreeNode in Internet Explorer (CVE-2013-1288)
-   [Qihoo 360 Security Center](http://www.360.cn/) per aver collaborato con noi alla vulnerabilità legata a un errore di tipo use-after-free in CTreeNode in Internet Explorer (CVE-2013-1288)

**MS13-022**

-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata alla duplice risoluzione del riferimento in Silverlight (CVE-2013-0074)

**MS13-023**

-   [Aniway.Anyway@gmail.com](mailto:aniway.anyway@gmail.com), che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata alla confusione dei tipi di oggetto albero di Visio Viewer (CVE-2013-0079)

**MS13-024**

-   Emanuel Bronshtein di [BugSec](http://www.bugsec.com/) per aver segnalato la vulnerabilità legata alla funzione di callback (CVE-2013-0080)
-   Sunil Yadav di INR Labs ([Network Intelligence India](http://niiconsulting.com/)) per aver segnalato la vulnerabilità legata al filtro XSS in SharePoint (CVE-2013-0083)
-   Moritz Jodeit di [n.runs AG](http://www.nruns.com/) per aver segnalato la vulnerabilità legata all'attraversamento delle directory in SharePoint (CVE-2013-0084)

**MS13-025**

-   Christopher Gabriel di per aver segnalato la vulnerabilità legata alla convalida delle dimensioni del buffer (CVE-2013-0086)

**MS13-026**

-   [Nick Semenkovich](https://technet.microsoft.com/it-IT/mailto:semenko@alum.mit.edu) per aver segnalato la vulnerabilità legata al caricamento non intenzionale di contenuto (CVE- 2013-0095)

**MS13-027**

-   Andy Davis di NCC Group per aver segnalato la vulnerabilità legata al descrittore USB di Windows (CVE-2013-1285)
-   Andy Davis di NCC Group per aver segnalato la vulnerabilità legata al descrittore USB di Windows (CVE-2013-1286)
-   Andy Davis di NCC Group per aver segnalato la vulnerabilità legata al descrittore USB di Windows (CVE-2013-1287)

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617.aspx)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (12 marzo 2013): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (15 marzo, 2013) per MS13-026, è stato corretto il titolo del bollettino nella sezione **Riepiloghi**.

*Built at 2014-04-18T01:50:00Z-07:00*
