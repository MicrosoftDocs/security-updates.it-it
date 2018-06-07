---
TOCTitle: 'MS10-NOV'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - novembre 2010'
ms:assetid: 'ms10-nov'
ms:contentKeyID: 61240051
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms10-nov(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - novembre 2010
==================================================================

Data di pubblicazione: sabato 11 settembre 2010 | Aggiornamento: mercoledì 15 dicembre 2010

**Versione:** 2.0

Il presente riepilogo elenca i bollettini sulla sicurezza rilasciati a novembre 2010.

Con il rilascio dei bollettini del mese di novembre 2010, il presente riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente il 4 novembre 2010. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/advance).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti sui presenti bollettini in data 10 novembre 2010 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di novembre](https://msevents.microsoft.com/cui/webcasteventdetails.aspx?culture=en-us&eventid=1032454441). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/bulletin/summary).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=203241">MS10-087</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Office possono consentire l'esecuzione di codice in modalità remota (2423930)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e cinque vulnerabilità segnalate privatamente di Microsoft Office. La vulnerabilità con gli effetti più gravi sulla protezione può consentire l'esecuzione di codice in modalità remota se un utente apre o visualizza in anteprima un messaggio di posta elettronica in formato RTF appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=198186">MS10-088</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft PowerPoint possono consentire l'esecuzione di codice in modalità remota (2293386)</strong><br />
<br />
L'aggiornamento per la protezione risolve due vulnerabilità di Microsoft Office che potrebbero consentire l'esecuzione di codice in modalità remota al momento dell'apertura di un file PowerPoint appositamente predisposto. Tali vulnerabilità sono state segnalate a Microsoft privatamente. Sfruttando una di queste vulnerabilità, un utente malintenzionato potrebbe assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=199536">MS10-089</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Forefront Unified Access Gateway (UAG) possono consentire l'acquisizione di privilegi più elevati (2316074)</strong><br />
<br />
Questo aggiornamento per la protezione risolve quattro vulnerabilità segnalate privatamente in Forefront Unified Access Gateway (UAG). La più grave delle vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente visita un sito Web interessato che utilizza un URL appositamente predisposto. Tuttavia, non è in alcun modo possibile obbligare gli utenti a visitare un sito Web di questo tipo. L'utente malintenzionato dovrebbe invece invogliare le vittime a visitare il sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che le indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/bulletin/rating">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Forefront Unified Access Gateway</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità sono elencate in ordine decrescente sulla base del livello di valutazione del rischio e quindi del codice CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di sfruttamento della vulnerabilità entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/it-it/security/cc998259.aspx).
  
| ID bollettino                                             | Titolo della vulnerabilità                                                                                    | ID CVE                                                                            | Valutazione dell'Exploitability Index                                                                                       | Note fondamentali                                                                             |  
|-----------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|  
| [MS10-088](http://go.microsoft.com/fwlink/?linkid=198186) | Vulnerabilità legata al sovraccarico del buffer durante l'analisi dei dati in Power Point                     | [CVE-2010-2572](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2572)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                     |  
| [MS10-089](http://go.microsoft.com/fwlink/?linkid=199536) | XSS di UAG permette la vulnerabilità di tipo EOP                                                              | [CVE-2010-2733](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2733)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                     |  
| [MS10-089](http://go.microsoft.com/fwlink/?linkid=199536) | Problema di vulnerabilità di tipo XSS sul sito Web del Portale Mobile UAG in Forefront Unified Access Gateway | [CVE-2010-2734](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2734)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                     |  
| [MS10-087](http://go.microsoft.com/fwlink/?linkid=203241) | Vulnerabilità legata al sovraccarico del buffer durante l'analisi dei dati RTF                                | [CVE-2010-3333](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3333)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                     |  
| [MS10-087](http://go.microsoft.com/fwlink/?linkid=203241) | Vulnerabilità legata ai record di disegno in Office Art                                                       | [CVE-2010-3334](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3334)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                     |  
| [MS10-087](http://go.microsoft.com/fwlink/?linkid=203241) | Vulnerabilità legata alla gestione delle eccezioni in Disegno                                                 | [CVE-2010- 3335](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3335) | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                     |  
| [MS10-087](http://go.microsoft.com/fwlink/?linkid=203241) | Vulnerabilità legata al caricamento non sicuro delle librerie                                                 | [CVE-2010-3337](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3337)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | **Le informazioni sulla vulnerabilità sono state divulgate pubblicamente**                    |  
| [MS10-089](http://go.microsoft.com/fwlink/?linkid=199536) | Vulnerabilità di tipo XSS in Sginurl.asp                                                                      | [CVE-2010-3936](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3936)  | [**1**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | (Nessuna)                                                                                     |  
| [MS10-087](http://go.microsoft.com/fwlink/?linkid=203241) | Vulnerabilità legata al danneggiamento degli heap delle cause di underflow dei valori integer in Power Point  | [CVE-2010-2573](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2573)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | [MS10-088](http://go.microsoft.com/fwlink/?linkid=198186) risolve anche questa vulnerabilità. |  
| [MS10-088](http://go.microsoft.com/fwlink/?linkid=198186) | Vulnerabilità legata al danneggiamento degli heap delle cause di underflow dei valori integer in Power Point  | [CVE-2010-2573](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2573)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | [MS10-087](http://go.microsoft.com/fwlink/?linkid=203241) risolve anche questa vulnerabilità. |  
| [MS10-087](http://go.microsoft.com/fwlink/?linkid=203241) | Vulnerabilità legata a MSO Large SPID Read AV                                                                 | [CVE-2010-3336](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-3336)  | [**2**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Media probabilità di sfruttamento della vulnerabilità  | (Nessuna)                                                                                     |  
| [MS10-089](http://go.microsoft.com/fwlink/?linkid=199536) | Vulnerabilità legata allo spoofing di reindirizzamento UAG                                                    | [CVE-2010-2732](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2010-2732)  | [**3**](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Si tratta di una vulnerabilità legata soltanto allo spoofing                                  |
  
Software interessato e percorsi per il download  
-----------------------------------------------
  
<span></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle?**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma software o componente elencato, viene indicato il collegamento ipertestuale all'aggiornamento software disponibile e il livello di gravità dell'aggiornamento software.
  
**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.
  
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
Applicazioni e componenti Microsoft Office  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-087**](http://go.microsoft.com/fwlink/?linkid=203241)
</td>
<td style="border:1px solid black;">
[**MS10-088**](http://go.microsoft.com/fwlink/?linkid=198186)
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
Microsoft Office XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f32648e3-2fb5-472c-932f-360e5d3c0931)  
(KB2289169)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint 2002 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=3efbf9f6-734a-46ac-8f92-87b6ec819bfa)  
(KB2413272)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=07a6cf76-2cea-4c54-b66d-50e9eed108ac)  
(KB2289187)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft PowerPoint 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=108286d4-fb68-40d6-a7b1-64b3a4eb87ee)  
(KB2413304)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Office 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=be0c5878-60c0-4700-8836-50d369b51d04)  
(KB2289158)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2010 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=0b308508-0e1e-4e90-b2b8-7e32bfc5dbf4)  
(KB2289161)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2010 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=534c6a2a-e7c6-4adf-8b81-e009a2b5fff4)  
(KB2289161)  
(Critico)
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
[**MS10-087**](http://go.microsoft.com/fwlink/?linkid=203241)
</td>
<td style="border:1px solid black;">
[**MS10-088**](http://go.microsoft.com/fwlink/?linkid=198186)
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
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
Microsoft Office 2004 per Mac<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
Microsoft Office 2004 per Mac<sup>[1]</sup>
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=ad1b1984-b2b2-49b3-a1dd-385b77d9248a)  
(KB2476512)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office per Mac 2011
</td>
<td style="border:1px solid black;">
[Microsoft Office per Mac 2011](http://www.microsoft.com/downloads/details.aspx?familyid=8bd6ca3b-8004-4e8d-a09d-220dcbbce799)  
(KB2454823)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Convertitore file in formato XML aperto per Mac
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per MAC](http://www.microsoft.com/downloads/details.aspx?familyid=b846d255-a7d4-4a2c-a084-d434c29fe676)  
(KB2476511)  
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
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-087**](http://go.microsoft.com/fwlink/?linkid=203241)
</td>
<td style="border:1px solid black;">
[**MS10-088**](http://go.microsoft.com/fwlink/?linkid=198186)
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
[**Importante**](http://technet.microsoft.com/security/bulletin/rating)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Visualizzatore di Microsoft Power Point
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Visualizzatore PowerPoint Microsoft 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=df826b79-7398-45de-943c-6f6f0af1b4e3)  
(KB2413381)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS10-087**

<sup>[1]</sup>L'aggiornamento per la protezione di Microsoft Office 2004 per Mac non è attualmente disponibile.

**Note per MS10-088**

<sup>[1]</sup>L'aggiornamento per la protezione di Microsoft Office 2004 per Mac non è attualmente disponibile.

#### Software di accesso in modalità remota di Microsoft

 
<table style="border:1px solid black;">
<tr class="thead">
<th style="border:1px solid black;" >
</th>
<th style="border:1px solid black;" >
</th>
</tr>
<tr>
<th colspan="2">
Microsoft Forefront Unified Access Gateway
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS10-089**](http://go.microsoft.com/fwlink/?linkid=199536)
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
Microsoft Forefront Unified Access Gateway
</td>
<td style="border:1px solid black;">
[Forefront Unified Access Gateway 2010](http://www.microsoft.com/downloads/details.aspx?familyid=5f2ee08e-e289-47db-bd3f-7b9cfc1eb985)<sup>[1]</sup>
(KB2433585)  
(Importante)  
[Aggiornamento 1 di Forefront Unified Access Gateway 2010](http://www.microsoft.com/downloads/details.aspx?familyid=db0b70c8-1fa5-4d92-9888-3500c7566b19)<sup>[1]</sup>
(KB2433584)  
(Importante)  
[Aggiornamento 2 di Forefront Unified Access Gateway 2010](http://www.microsoft.com/downloads/details.aspx?familyid=4e3ee07a-771c-46ee-959f-82389bab67d7)<sup>[1]</sup>
(KB2418933)  
(Importante)
</td>
</tr>
</table>
 
**Note per MS10-089**

<sup>[1]</sup>Questo pacchetto di aggiornamento è disponibile soltanto nell'Area download Microsoft.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security Center](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://www.microsoft.com/italy/athome/security/default.mspx), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?pocid=&freetext=security%20update&displaylang=it) ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

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

-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS10-087
-   [team509](http://www.team509.com/), che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS10-087
-   Dyon Balding di [Secunia](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS10-087
-   Will Dorman di [CERT Coordination Center](http://www.cert.org/) per aver segnalato un problema descritto nel bollettino MS10-087
-   [Zero Day Initiative](http://www.tippingpoint.com/) di [Tipping Point](http://www.zerodayinitiative.com/) per aver segnalato un problema descritto nel bollettino MS10-087
-   Chaouki Bekrar del [VUPEN Vulnerability Research Team](http://www.vupen.com/) per aver segnalato un problema descritto nel bollettino MS10-087
-   Haifei Li di [FortiGuard Labs di Fortinet](http://www.fortiguard.com/) per aver segnalato un problema descritto nel bollettino MS10-087
-   Simon Raner di [ACROS Security](http://www.acrossecurity.com) per aver segnalato un problema descritto nel bollettino MS10-087
-   Alin Rad Pop di [Secunia Research](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS10-088
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/) per aver segnalato un problema descritto nel bollettino MS10-088
-   Eyal Gruner di [BugSec](http://www.bugsec.com/) per aver collaborato alla soluzione dei tre problemi descritti nel bollettino MS10-089

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](https://consumersecuritysupport.microsoft.com/default.aspx?mkt=it-it). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/?ln=it).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://support.microsoft.com/common/international.aspx).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (9 novembre 2010): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (9 novembre 2010): Per MS10-088: è stata corretta la versione interessata da "Visualizzatore PowerPoint Microsoft" a "Visualizzatore PowerPoint Microsoft 2007 Service Pack 2". La modifica è esclusivamente informativa. I clienti che hanno già aggiornato i propri sistemi, inclusi i clienti che hanno attivato l'aggiornamento automatico, non devono eseguire ulteriori operazioni. È possibile che i clienti che non hanno già installato questo aggiornamento debbano rivalutare la necessità di installarlo nei propri sistemi in base alle informazioni contenute nel software interessato modificato.
-   V1.2 (17 novembre 2010): Per MS10-087, è stato modificato l'Exploitability Index aggiungendo CVE-2010-2573 per risolvere il problema della vulnerabilità grazie al presente aggiornamento. La modifica è esclusivamente informativa.
-   V2.0 (15 dicembre 2010): Questo riepilogo dei bollettini è stato rivisto per comunicare che gli aggiornamenti per la protezione MS10-087 sono ora disponibili per Microsoft Office 2008 per Mac (KB2476512) e il convertitore file in formato XML aperto per Mac (KB2476511). Microsoft consiglia agli utenti di questo software di applicare gli aggiornamenti il prima possibile.

*Built at 2014-04-18T01:50:00Z-07:00*
