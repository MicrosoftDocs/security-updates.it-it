---
TOCTitle: 'MS11-SEP'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Settembre 2011'
ms:assetid: 'ms11-sep'
ms:contentKeyID: 61240065
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms11-sep(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Settembre 2011
===================================================================

Data di pubblicazione: martedì 13 settembre 2011 | Aggiornamento: martedì 13 settembre 2011

**Versione:** 1.1

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a settembre 2011.

Con il rilascio dei bollettini sulla sicurezza di settembre 2011, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente l'8 settembre 2011. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://go.microsoft.com/fwlink/?linkid=21163).

Microsoft metterà a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 14 settembre 2011 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di settembre](https://msevents.microsoft.com/cui/eventdetail.aspx?culture=en-us&eventid=1032487951). Dopo questa data, il webcast sarà disponibile su richiesta. Per ulteriori informazioni, vedere i [riepiloghi e i webcast dei bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217214).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225825">MS11-070</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in WINS può consentire l'acquisizione di privilegi più elevati (2571621)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente di Windows Internet Name Service (WINS). La vulnerabilità potrebbe consentire l'acquisizione di privilegi più elevati, se un utente riceve un pacchetto di replica WINS appositamente predisposto in un sistema interessato che esegua il servizio WINS. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=223632">MS11-071</a></td>
<td style="border:1px solid black;"><strong>La vulnerabilità dei componenti di Windows può consentire l'esecuzione di codice in modalità remota (2570947)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft Windows. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file rich text format (.rtf), un file di testo (.txt) o un documento Word (.doc) legittimo situato nella stessa directory di rete di un file della libreria di collegamento dinamico (DLL) appositamente predisposto. Sfruttando questa vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente locale. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225047">MS11-072</a></td>
<td style="border:1px solid black;"><strong>Le vulnerabilità in Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (2587505)</strong><br />
<br />
Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente in Microsoft Office. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota durante l'apertura di un file di Excel appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione. L'installazione e la configurazione di Convalida file di Office (OFV) per evitare l'apertura di file sospetti blocca i vettori di attacco per sfruttare le vulnerabilità descritte in CVE-2011-1986 e CVE-2011-1987.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Software dei server Microsoft</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225103">MS11-073</a></td>
<td style="border:1px solid black;"><strong>Le vulnerabilità in Microsoft Office possono consentire l'esecuzione di codice in modalità remota (2587634)</strong><br />
<br />
Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Office. Le vulnerabilità potrebbero consentire l'esecuzione di codice in modalità remota se un utente apre un file di Office appositamente predisposto o se un utente apre un file di Office legittimo situato nella stessa directory di rete di un file della libreria appositamente predisposto. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente connesso. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=204797">MS11-074</a></td>
<td style="border:1px solid black;"><strong>Le vulnerabilità in Microsoft SharePoint possono consentire l'acquisizione di privilegi più elevati (2451858)</strong><br />
<br />
Questo aggiornamento per la protezione risolve cinque vulnerabilità segnalate privatamente ed una vulnerabilità divulgata pubblicamente in Microsoft SharePoint e Windows SharePoint Services. Le vulnerabilità più gravi possono consentire l'acquisizione di privilegi più elevati se un utente fa clic su un URL appositamente predisposto o visita un sito Web appositamente predisposto. Per le vulnerabilità più gravi, gli utenti di Internet Explorer 8 e Internet Explorer 9 che accedono a un sito SharePoint nell'Area Internet corrono meno rischi, poiché per impostazione predefinita il filtro XSS in Internet Explorer 8 e Internet Explorer 9 consente di bloccare gli attacchi nell'Area Internet. Tuttavia, il filtro XSS in Internet Explorer 8 e Internet Explorer 9 non è attivato per impostazione predefinita nell'Area Intranet.</td>
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=21140">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Software dei server Microsoft</td>
</tr>
</tbody>
</table>
 

Exploitability Index
--------------------

<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.

**Come utilizzare questa tabella**

Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui essi vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).

Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.

 
<table style="border:1px solid black;">
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID bollettino</th>
<th style="border:1px solid black;" >Titolo della vulnerabilità</th>
<th style="border:1px solid black;" >ID CVE</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa all'esecuzione di codice per la versione più recente del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa all'esecuzione di codice per le versioni meno recenti del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service</th>
<th style="border:1px solid black;" >Note fondamentali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225825">MS11-070</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'acquisizione locale di privilegi più elevati in WINS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1984">CVE-2011-1984</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=223632">MS11-071</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al caricamento non sicuro delle librerie nei componenti di Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1991">CVE-2011-1991</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225047">MS11-072</a></td>
<td style="border:1px solid black;">Vulnerabilità WriteAV di tipo Use after Free in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1986">CVE-2011-1986</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225047">MS11-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'indicizzazione delle matrici fuori limite in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1987">CVE-2011-1987</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225047">MS11-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento dell'heap in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1988">CVE-2011-1988</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">2</a> - Media probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225047">MS11-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'analisi dell'espressione condizionale in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1989">CVE-2011-1989</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225047">MS11-072</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'indicizzazione delle matrici fuori limite in Excel</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1990">CVE-2011-1990</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225103">MS11-073</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al caricamento non sicuro delle librerie nel componente Office</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1980">CVE-2011-1980</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=225103">MS11-073</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al puntatore oggetti non inizializzato in Office</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1982">CVE-2011-1982</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=204797">MS11-074</a></td>
<td style="border:1px solid black;">Vulnerabilità XSS nel calendario di SharePoint</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-0653">CVE-2011-0653</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=204797">MS11-074</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla disinfezione del contenuto HTML</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1252">CVE-2011-1252</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali<br />
<br />
Le informazioni sulla vulnerabilità sono state divulgate pubblicamente</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=204797">MS11-074</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'introduzione di uno script Editform</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1890">CVE-2011-1890</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=204797">MS11-074</a></td>
<td style="border:1px solid black;">Vulnerabilità di tipo XSS relativa ai dettagli di contatto</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1891">CVE-2011-1891</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=204797">MS11-074</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla divulgazione remota di file SharePoint</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1892">CVE-2011-1892</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">3</a> – Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=204797">MS11-074</a></td>
<td style="border:1px solid black;">Vulnerabilità XSS di SharePoint</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2011-1893">CVE-2011-1893</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/en-us/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
</tbody>
</table>
  
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
[**MS11-070**](http://go.microsoft.com/fwlink/?linkid=225825)
</td>
<td style="border:1px solid black;">
[**MS11-071**](http://go.microsoft.com/fwlink/?linkid=223632)
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
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=70f944b0-9bf0-4168-b150-67d2ff68df2d)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=4b9debed-edbb-43e1-b755-0faf01980289)  
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
[**MS11-070**](http://go.microsoft.com/fwlink/?linkid=225825)
</td>
<td style="border:1px solid black;">
[**MS11-071**](http://go.microsoft.com/fwlink/?linkid=223632)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1e6ac3b2-752e-49a0-84e5-5a8dfe955299)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=d44274d2-0401-4fd8-bc4f-c59f6d81c34f)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f9378339-c58e-4e84-9427-85aeb35b0d99)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=935720ee-cee0-42c2-965e-ce1b07e95e1a)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=c35c71a8-13b4-47a6-9763-06f6f65327b1)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=78c2ac72-da89-42a4-bff9-79551b5d3c4e)  
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
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-070**](http://go.microsoft.com/fwlink/?linkid=225825)
</td>
<td style="border:1px solid black;">
[**MS11-071**](http://go.microsoft.com/fwlink/?linkid=223632)
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
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=15840336-4886-4a1b-8c1e-2c535c3938f7)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e80739b4-89bb-4317-8381-991244a71cb8)  
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
[**MS11-070**](http://go.microsoft.com/fwlink/?linkid=225825)
</td>
<td style="border:1px solid black;">
[**MS11-071**](http://go.microsoft.com/fwlink/?linkid=223632)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a9039660-3cc2-470d-a0a5-a70f78074495)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=05c39ab3-7b57-4147-8913-df5df6005799)\*  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5ea78a9b-b1f7-4e94-b69e-c984e1622ae9)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1499d988-fd55-4317-b859-ec170907d547)\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6e2d2ea9-0af6-4d23-875d-3211722cd62f)  
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
[**MS11-070**](http://go.microsoft.com/fwlink/?linkid=225825)
</td>
<td style="border:1px solid black;">
[**MS11-071**](http://go.microsoft.com/fwlink/?linkid=223632)
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
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit e Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=76b99ab2-7e99-4aad-a419-7996bae05c48)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 e Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0f6d32de-d3ff-4af9-9b26-a4f12581f5fe)  
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
[**MS11-070**](http://go.microsoft.com/fwlink/?linkid=225825)
</td>
<td style="border:1px solid black;">
[**MS11-071**](http://go.microsoft.com/fwlink/?linkid=223632)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi a x64 e Windows Server 2008 R2 per sistemi a x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=f58cf343-946c-4e74-bd9c-40ac934a4986)\*  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 e Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=a8a451bd-3e5c-4845-9941-daabd9418776)\*  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium e Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0fdfb1f9-20b3-4d61-8019-33d1003290c8)  
(Importante)
</td>
</tr>
</table>
 
**Nota per Windows Server 2008 e Windows Server 2008 R2**

**\*L'installazione Server Core è interessata da questo aggiornamento.** Per le edizioni supportate di Windows Server 2008 o Windows Server 2008 R2, a questo aggiornamento si applica il medesimo livello di gravità indipendentemente dal fatto che l'installazione sia stata effettuata usando l'opzione Server Core o meno. Per ulteriori informazioni su questa modalità di installazione, vedere gli articoli di TechNet, [Gestione dell'installazione dei componenti di base del server](http://technet.microsoft.com/en-us/library/ee441255(ws.10).aspx) e [Manutenzione dell'installazione dei componenti di base del server](http://technet.microsoft.com/en-us/library/ff698994(ws.10).aspx). Si noti che l'opzione di installazione di Server Core non è disponibile per alcune edizioni di Windows Server 2008 e Windows Server 2008 R2; vedere [Opzioni di installazione Server Core a confronto](http://www.microsoft.com/windowsserver2008/en/us/compare-core-installation.aspx).

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="4">
Applicazioni e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-072**](http://go.microsoft.com/fwlink/?linkid=225047)
</td>
<td style="border:1px solid black;">
[**MS11-073**](http://go.microsoft.com/fwlink/?linkid=225103)
</td>
<td style="border:1px solid black;">
[**MS11-074**](http://go.microsoft.com/fwlink/?linkid=204797)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=dee4f3d7-bc4b-47fd-8e3f-9d2b0e82d0f6)  
(KB2553072)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=7faa2f90-2e64-4dbf-ac93-bb8cffc9b5fe)  
(KB2584052)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=498ac241-d728-4944-abac-ec8444ca6418)  
(KB2553073)<sup>[1]</sup>
(Importante)  
[Microsoft Office 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=df04b9ce-2daa-4b4d-a944-a873075656f9)  
(KB2553089)<sup>[1]</sup>
(Importante)  
[Microsoft Office 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=90eef02b-db1f-4fdd-bb1d-408063671e4d)  
(KB2553090)<sup>[1]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=34bbee95-0e83-4705-8bfe-02e4fb22f8e7)  
(KB2584063)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 e Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2010 e Microsoft Excel 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=4612c6e4-ac29-4cc4-9da5-88779ea3643e)  
(KB2553070)  
(Importante)  
[Microsoft Office 2010 e Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=1fd15144-5547-4927-8583-8d9b06819226)  
(KB2553091)  
(Importante)  
[Microsoft Office 2010 e Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=18840d78-944f-400a-addc-dce7e570a569)  
(KB2553096)  
(Importante)
</td>
<td style="border:1px solid black;">
[Per Microsoft Office 2010 e Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=3c8fd04a-9df6-4726-a9bc-811f49665981)  
(KB2584066)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 e Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2010 e Microsoft Excel 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=d40db27b-1318-4ca7-b44f-c90bb6342109)  
(KB2553070)  
(Importante)  
[Microsoft Office 2010 e Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=f83800aa-6403-4341-afea-d363e54d5831)  
(KB2553091)  
(Importante)  
[Microsoft Office 2010 e Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=92787e00-6f30-4020-9c1a-70270be5a623)  
(KB2553096)  
(Importante)
</td>
<td style="border:1px solid black;">
[Per Microsoft Office 2010 e Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=85360dc1-99e7-4e3e-be6f-3795e8a8122f)  
(KB2584066)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="4">
Microsoft Office per Mac
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-072**](http://go.microsoft.com/fwlink/?linkid=225047)
</td>
<td style="border:1px solid black;">
[**MS11-073**](http://go.microsoft.com/fwlink/?linkid=225103)
</td>
<td style="border:1px solid black;">
[**MS11-074**](http://go.microsoft.com/fwlink/?linkid=204797)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2004 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2004 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=868f4d9f-3498-4d59-a017-59204553889c)  
(KB2598782)  
(Importante)
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
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=afa79cfc-6e8a-4d0b-88aa-0d7e05031e44)  
(KB2598781)  
(Importante)
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
Microsoft Office per Mac 2011
</td>
<td style="border:1px solid black;">
[Microsoft Office per Mac 2011](http://www.microsoft.com/downloads/details.aspx?familyid=535fcf4a-eeb2-44eb-b2a6-9c512509c49d)  
(KB2598783)  
(Importante)
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
Convertitore file in formato XML aperto per Mac
</td>
<td style="border:1px solid black;">
[Convertitore file in formato XML aperto per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=9796588d-238f-4694-9598-1aa8d2becb55)  
(KB2598785)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="4">
Microsoft Office Groove e Microsoft SharePoint Workspace
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-072**](http://go.microsoft.com/fwlink/?linkid=225047)
</td>
<td style="border:1px solid black;">
[**MS11-073**](http://go.microsoft.com/fwlink/?linkid=225103)
</td>
<td style="border:1px solid black;">
[**MS11-074**](http://go.microsoft.com/fwlink/?linkid=204797)
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
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Groove 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Groove 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5ea6192b-55e5-4ca4-8d91-cc768ede8277)  
(KB2552997)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft SharePoint Workspace 2010 e Microsoft SharePoint Workspace 2010 Service Pack 1 (edizioni a 32)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Workspace 2010 e Microsoft SharePoint Workspace 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=f6ee7e43-9da9-4b96-abd0-390cfcacb885)  
(KB2566445)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Workspace 2010 e Microsoft SharePoint Workspace 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Workspace 2010 e Microsoft SharePoint Workspace 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=234efac1-4f09-41f5-90a9-4a3c2e81c05e)  
(KB2566445)  
(Importante)
</td>
</tr>
<tr>
<th colspan="4">
Altro software Microsoft Office
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-072**](http://go.microsoft.com/fwlink/?linkid=225047)
</td>
<td style="border:1px solid black;">
[**MS11-073**](http://go.microsoft.com/fwlink/?linkid=225103)
</td>
<td style="border:1px solid black;">
[**MS11-074**](http://go.microsoft.com/fwlink/?linkid=204797)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
Nessuno
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Excel Viewer Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Excel Viewer Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=f82ca5da-a55a-487c-8170-46a40000c8e3)  
(KB2553075)  
(Importante)
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
Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e PowerPoint 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=01093f22-06b7-4c9b-bff9-f54ac5d73bf8)  
(KB2553074)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Note per MS11-072**

<sup>[1]</sup>Per Microsoft Excel 2007 Service Pack 2, oltre al pacchetto di aggiornamento per la protezione KB2553073, KB2553089 e KB2553090, i clienti devono installare anche l'aggiornamento per la protezione del pacchetto di compatibilità Microsoft Office per i file in formato Word, Excel e Power Point 2007 Service Pack 2 (KB2553074) per essere protetti dalle vulnerabilità descritte in questo bollettino.

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Nota per MS11-074**

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="3">
Microsoft SharePoint Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-072**](http://go.microsoft.com/fwlink/?linkid=225047)
</td>
<td style="border:1px solid black;">
[**MS11-074**](http://go.microsoft.com/fwlink/?linkid=204797)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office SharePoint Server 2007 Service Pack 2 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Excel Services](http://www.microsoft.com/downloads/details.aspx?familyid=dd532201-485c-4270-88d3-63bd3f24327e)  
(KB2553093)<sup>[2]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2007 Service Pack 2 (coreserver) (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=ad52c341-13ce-4b53-87b4-269cb3f41275)  
(KB2508964)<sup>[1]</sup>
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 2 (oserver) (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=fd6189c9-ab3b-441f-a901-6ac7f3b202aa)  
(KB2553001)<sup>[1]</sup>
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 2 (sserverx) (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=d9601fae-4a80-45cd-a49b-ef441856d7e4)  
(KB2553002)<sup>[1]</sup>
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 2 (dlc) (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=55b60e2f-ec68-4ccb-803a-5d03add8a1f1)  
(KB2553003)<sup>[1]</sup>
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office SharePoint Server 2007 Service Pack 2 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Excel Services](http://www.microsoft.com/downloads/details.aspx?familyid=1086a5b0-e441-4e26-a8d1-924a20121dde)  
(KB2553093)<sup>[2]</sup>
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2007 Service Pack 2 (coreserver) (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=e5e60751-242a-4fdb-9852-6d94050d3d0e)  
(KB2508964)<sup>[1]</sup>
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 2 (oserver) (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=b1466366-e2ae-498e-b964-135e034e7348)  
(KB2553001)<sup>[1]</sup>
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 2 (sserverx) (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=bb788c8d-8383-4e53-ac05-2a7dd9b83e70)  
(KB2553002)<sup>[1]</sup>
(Importante)  
[Microsoft Office SharePoint Server 2007 Service Pack 2 (dlc) (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=e8e1a5bb-a552-45fe-8e81-e05fbfbb57ee)<sup>[1]</sup>
(Importante)  
(KB2553003)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office SharePoint Server 2010 e Microsoft Office SharePoint Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Excel Services](http://www.microsoft.com/downloads/details.aspx?familyid=0c150328-6a15-4852-a09c-4063142bd946)  
(KB2553094)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office SharePoint Server 2010 e Microsoft Office SharePoint Server 2010 Service Pack 1 (osrchwfe)](http://www.microsoft.com/downloads/details.aspx?familyid=c17eb04d-cbbc-457e-a424-4ee26b7a9654)  
(KB2494022)  
(Importante)  
[Microsoft Office SharePoint Server 2010 e Microsoft Office SharePoint Server 2010 Service Pack 1 (osrv)](http://www.microsoft.com/downloads/details.aspx?familyid=2a80a849-b712-47d4-9def-9395ee54a265)  
(KB2560885)  
(Importante)  
[Microsoft Office SharePoint Server 2010 e Microsoft Office SharePoint Server 2010 Service Pack 1 (pplwfe)](http://www.microsoft.com/downloads/details.aspx?familyid=b84c2bcb-0327-4916-871e-7a5c19b8c41b)  
(KB2560890)  
(Importante)  
[Microsoft Office SharePoint Server 2010 e Microsoft Office SharePoint Server 2010 Service Pack 1 (ppsmawfe)](http://www.microsoft.com/downloads/details.aspx?familyid=1597f295-02a9-4479-9d52-f18f0e83eaba)  
(KB2566456)  
(Importante)  
[Microsoft Office SharePoint Server 2010 e Microsoft Office SharePoint Server 2010 Service Pack 1 (dlc)](http://www.microsoft.com/downloads/details.aspx?familyid=e6b666a4-a795-441c-9bda-23e2de2e7b05)  
(KB2566954)  
(Importante)  
[Microsoft Office SharePoint Server 2010 e Microsoft Office SharePoint Server 2010 Service Pack 1 (ppsmamui)](http://www.microsoft.com/downloads/details.aspx?familyid=57592ce4-5d99-45c2-830f-380d67af8899)  
(KB2566958)  
(Importante)  
[Microsoft Office SharePoint Server 2010 e Microsoft Office SharePoint Server 2010 Service Pack 1 (wosrv)](http://www.microsoft.com/downloads/details.aspx?familyid=dd64a635-1e55-4b4d-9718-9b94c31c5625)  
(KB2566960)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Office Forms Server
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-072**](http://go.microsoft.com/fwlink/?linkid=225047)
</td>
<td style="border:1px solid black;">
[**MS11-074**](http://go.microsoft.com/fwlink/?linkid=204797)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
</td>
<td style="border:1px solid black;">
Nessuno
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Forms Server 2007 Service Pack 2 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Forms Server 2007 Service Pack 2 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=c4c8ad7e-50bd-460e-9678-d8c72c6ee7ab)  
(KB2553005)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Forms Server 2007 Service Pack 2 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Forms Server 2007 Service Pack 2 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=7390b526-f411-45a4-8587-8077b473ac17)  
(KB2553005)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Groove Server
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-072**](http://go.microsoft.com/fwlink/?linkid=225047)
</td>
<td style="border:1px solid black;">
[**MS11-074**](http://go.microsoft.com/fwlink/?linkid=204797)
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
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office Groove Data Bridge Server 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Groove Data Bridge Server 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=5958247e-204e-409c-bdc1-7aff06e854b8)  
(KB2552999)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Groove Management Server 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Office Groove Management Server 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6b5b4caf-6a95-487d-ac17-c4435225af3a)  
(KB2552998)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Groove Server 2010 e Microsoft Groove Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Groove Server 2010 e Microsoft Groove Server 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=71c0f217-5112-4dca-b9aa-46c69f6099e4)  
(KB2508965)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Microsoft Office Web Apps
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-072**](http://go.microsoft.com/fwlink/?linkid=225047)
</td>
<td style="border:1px solid black;">
[**MS11-074**](http://go.microsoft.com/fwlink/?linkid=204797)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
<td style="border:1px solid black;">
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Web Apps 2010 e Microsoft Office Web Apps 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Excel Web App 2010 e Microsoft Excel Web App 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=73d49094-a9cf-407e-8921-1b22fbc30427)  
(KB2553095)  
(Importante)
</td>
<td style="border:1px solid black;">
[Microsoft Office Web Apps 2010 e Microsoft Office Web Apps 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=288a7394-b8d5-4445-bd4c-65bbf4b10eaf)  
(KB2566449)  
(Importante)  
[Microsoft Word Web App 2010 e Microsoft Word Web App 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=152ff9f4-d720-41af-8f89-793133ece037)  
(KB2566450)  
(Importante)
</td>
</tr>
<tr>
<th colspan="3">
Windows SharePoint Services e Microsoft SharePoint Foundation
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS11-072**](http://go.microsoft.com/fwlink/?linkid=225047)
</td>
<td style="border:1px solid black;">
[**MS11-074**](http://go.microsoft.com/fwlink/?linkid=204797)
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
[**Importante**](http://go.microsoft.com/fwlink/?linkid=21140)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 2.0
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows SharePoint Services 2.0](http://www.microsoft.com/downloads/details.aspx?familyid=71e32745-cb05-4b87-a447-741ccdac7450)  
(KB2494007)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 2 (versioni a 32 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows SharePoint Services 3.0 Service Pack 2 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=0f306cbd-a652-4e77-b394-1a6dc38ba83c)  
(KB2493987)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Windows SharePoint Services 3.0 Service Pack 2 (versioni a 64 bit)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft Windows SharePoint Services 3.0 Service Pack 2 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=3137e4c6-783d-4461-88bd-90da064e3105)  
(KB2493987)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Foundation 2010 e Microsoft SharePoint Foundation 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft SharePoint Foundation 2010 e Microsoft SharePoint Foundation 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=0db799e2-896f-464b-8cd5-ecf2014f0588)  
(KB2494001)  
(Importante)
</td>
</tr>
</table>
 
**Note per MS11-072**

<sup>[2]</sup>Questo aggiornamento si applica ai server che hanno installato Excel Services, come Microsoft Office SharePoint Server 2007 Enterprise e Microsoft Office SharePoint Server 2007 per siti Internet, nella loro configurazione predefinita. Microsoft Office SharePoint Server 2007 Standard non contiene Excel Services.

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

**Note per MS11-074**

<sup>[1]</sup>Per le edizioni supportate di Microsoft Office SharePoint Server 2007, oltre ai pacchetti di aggiornamento per la protezione di Microsoft Office SharePoint 2007 (KB2508964, KB2553001, KB2553002 e KB2553003), i clienti devono installare anche l'aggiornamento per la protezione di Microsoft Windows SharePoint Services 3.0 (KB2493987) per essere protetti dalle vulnerabilità descritte in questo bollettino.

Vedere ulteriori categorie software nella sezione **Software interessato e percorsi per il download**, per ulteriori file di aggiornamento sotto lo stesso identificativo del bollettino. Questo bollettino riguarda più di una categoria di software.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://go.microsoft.com/fwlink/?linkid=69903). [TechNet Security Center](http://go.microsoft.com/fwlink/?linkid=21171) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. Gli utenti di sistemi consumer possono visitare [Sicurezza a casa](http://go.microsoft.com/fwlink/?linkid=85102), in cui queste informazioni sono disponibili anche facendo clic su "Latest Security Updates" (Ultimi aggiornamenti per la protezione).

Gli aggiornamenti per la protezione sono disponibili dai siti Web [Microsoft Update](http://go.microsoft.com/fwlink/?linkid=40747) e [Windows Update](http://go.microsoft.com/fwlink/?linkid=21130). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://go.microsoft.com/fwlink/?linkid=21129). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=96155). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS07-036"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://go.microsoft.com/fwlink/?linkid=97900).

**Informazioni sul rilevamento e sulla distribuzione**

Microsoft fornisce informazioni sul rivelamento e la distribuzione degli aggiornamenti sulla protezione. Questa guida contiene raccomandazioni e informazioni che possono aiutare i professionisti IT a capire come utilizzare i vari strumenti per il rilevamento e la distribuzione di aggiornamenti per la protezione. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 961747](http://support.microsoft.com/kb/961747).

**Microsoft Baseline Security Analyzer**

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione. Per ulteriori informazioni su MBSA, visitare il sito [Microsoft Baseline Security Analyzer](http://go.microsoft.com/fwlink/?linkid=21134).

**Windows Server Update Services**

Utilizzando Windows Server Update Services (WSUS), gli amministratori possono eseguire la distribuzione dei più recenti aggiornamenti critici e per la protezione nei sistemi operativi Microsoft Windows 2000 e versioni successive, Office XP e versioni successive, Exchange Server 2003 ed SQL Server 2000 e in Microsoft Windows 2000 e versioni successive del sistema operativo.

Per ulteriori informazioni su come eseguire la distribuzione di questo aggiornamento per la protezione con Windows Server Update Services, visitare il sito [Windows Server Update Services](http://technet.microsoft.com/en-us/wsus/default.aspx).

**System Center Configuration Manager 2007**

La Gestione aggiornamenti software di Configuration Manager 2007 semplifica la consegna e la gestione degli aggiornamenti dei sistemi IT in tutta l'azienda. Con Configuration Manager 2007, gli amministratori IT possono consegnare gli aggiornamenti dei prodotti Microsoft a diverse periferiche compresi desktop, portatili, server e dispositivi mobili.

La valutazione automatica della vulnerabilità disponibile in Configuration Manager 2007 rileva la necessità di effettuare gli aggiornamenti ed invia relazioni sulle azioni consigliate. La Gestione aggiornamenti software di Configuration Manager 2007 si basa su Microsoft Windows Software Update Services (WSUS), un'infrastruttura di aggiornamento tempestiva conosciuta agli amministratori IT in tutto il mondo. Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare Configuration Manager 2007 per implementare gli aggiornamenti, vedere [Gestione aggiornamenti software](http://www.microsoft.com/systemcenter/en/us/configuration-manager/cm-software-update-management.aspx). Per ulteriori informazioni su Configuration Manager, visitare [System Center Configuration Manager](http://www.microsoft.com/systemcenter/en/us/configuration-manager.aspx).

**Systems Management Server 2003**

Microsoft Systems Management Server (SMS) offre una soluzione aziendale altamente configurabile per la gestione degli aggiornamenti. Tramite SMS gli amministratori possono identificare i sistemi Windows che richiedono gli aggiornamenti per la protezione ed eseguire la distribuzione controllata di tali aggiornamenti in tutta l'azienda, riducendo al minimo le eventuali interruzioni del lavoro degli utenti finali.

**Nota** System Management Server 2003 non è più incluso nel supporto "Mainstream" a partire dal 12 gennaio 2010. Per ulteriori informazioni sul ciclo di vita dei prodotti, visitare [Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=dm;en-us;lifecycle). È disponibile la nuova versione di SMS, System Center Configuration Manager 2007; vedere anche **System Center Configuration Manager 2007**.

Per ulteriori informazioni sulle modalità con cui gli amministratori possono utilizzare SMS 2003 per implementare gli aggiornamenti per la protezione, vedere [Scenari e procedure per Microsoft Systems Management Server 2003: Distribuzione software e gestione patch](http://www.microsoft.com/downloads/en/details.aspx?familyid=32f2bb4c-42f8-4b8d-844f-2553fd78049f&displaylang=en). Per informazioni su SMS, visitare il sito [Microsoft Systems Management Server TechCenter](http://technet.microsoft.com/en-us/systemcenter/bb545936.aspx).

**Nota** SMS utilizza Microsoft Baseline Security Analyzer per offrire il più ampio supporto possibile per il rilevamento e la distribuzione degli aggiornamenti inclusi nei bollettini sulla sicurezza. Alcuni aggiornamenti non possono essere tuttavia rilevati tramite questi strumenti. In questi casi, per applicare gli aggiornamenti a computer specifici è possibile utilizzare le funzionalità di inventario di SMS. Per ulteriori informazioni su questa procedura, vedere la sezione per la [distribuzione degli aggiornamenti software utilizzando la funzione di distribuzione software SMS](http://go.microsoft.com/fwlink/?linkid=33341). Alcuni aggiornamenti per la protezione richiedono diritti di amministrazione dopo il riavvio del sistema. Per installare tali aggiornamenti è possibile utilizzare Elevated Rights Deployment Tool (disponibile nello [SMS 2003 Administration Feature Pack](http://www.microsoft.com/downloads/en/details.aspx?familyid=7bd3a16e-1899-4e0b-bb99-1320e816167d&displaylang=en)).

**Update Compatibility Evaluator e Application Compatibility Toolkit**

Gli aggiornamenti vanno spesso a sovrascrivere gli stessi file e le stesse impostazioni del Registro di sistema che sono necessari per eseguire le applicazioni. Ciò può scatenare delle incompatibilità e aumentare il tempo necessario per installare gli aggiornamenti per la protezione. Il programma [Update Compatibility Evaluator](http://technet2.microsoft.com/windowsvista/en/library/4279e239-37a4-44aa-aec5-4e70fe39f9de1033.mspx?mfr=true), incluso nell'[Application Compatibility Toolkit](http://www.microsoft.com/downloads/details.aspx?familyid=24da89e9-b581-47b0-b45e-492dd6da2971&displaylang=en), consente di semplificare il testing e la convalida degli aggiornamenti di Windows, verificandone la compatibilità con le applicazioni già installate.

L'Application Compatibility Toolkit (ACT) contiene gli strumenti e la documentazione necessari per valutare e attenuare i problemi di compatibilità tra le applicazioni prima di installare Microsoft Windows Vista, un aggiornamento di Windows, un aggiornamento Microsoft per la protezione o una nuova versione di Windows Internet Explorer nell'ambiente in uso.

### Altre informazioni

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

#### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](http://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/en-us/wsus/bb456965.aspx). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

#### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://go.microsoft.com/fwlink/?linkid=215201).

#### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://go.microsoft.com/fwlink/?linkid=21168).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://go.microsoft.com/fwlink/?linkid=21129). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://go.microsoft.com/fwlink/?linkid=40747).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://go.microsoft.com/fwlink/?linkid=21164).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Nicolas Economou di [Core Security Technologies](http://www.coresecurity.com/) per aver segnalato un problema descritto nel bollettino MS11-070
-   Un ricercatore anonimo di [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS11-072
-   Sean Larsson di [VeriSign iDefense Labs](http://labs.idefense.com/) per aver segnalato un problema descritto nel bollettino MS11-072
-   Un ricercatore anonimo di [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS11-072
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.tippingpoint.com/)per aver segnalato un problema descritto nel bollettino MS11-072
-   Omair, che collabora con [Zero Day Initiative](http://www.tippingpoint.com/) di [TippingPoint](http://www.zerodayinitiative.com/), per aver segnalato un problema descritto nel bollettino MS11-072
-   Parvez Anwar, che collabora con [Secunia Research](http://secunia.com/) per aver segnalato un problema descritto nel bollettino MS11-073
-   David Warren di [CERT/CC](http://www.cert.org/) per aver segnalato un problema descritto nel bollettino MS11-073
-   Andrew Connell di [Critical Path Training, LLC](http://www.criticalpathtraining.com/) per aver segnalato un problema descritto nel bollettino MS11-074
-   David Feldman di [Raytheon](http://www.raytheon.com/) per aver segnalato un problema descritto nel bollettino MS11-074
-   Adi Cohen di [IBM Rational Application Security](http://blog.watchfire.com/) per aver segnalato un problema descritto nel bollettino MS11-074
-   [Trend Micro](http://www.trendmicro.com/)per aver collaborato con noi allo studio di un problema descritto nel bollettino MS11-074
-   Pedro Jimenez di [ITT](http://www.itt.com/) per aver segnalato un problema descritto nel bollettino MS11-074
-   [Soluzione di verifica automatica per la protezione delle applicazioni di Seeker](http://www.seekersec.com/)per aver segnalato un problema descritto nel bollettino MS11-074
-   Nicolas Grégoire di [Agarri](http://www.agarri.fr/) per aver segnalato un problema descritto nel bollettino MS11-074
-   Jim LaValley di [LaValley Consulting, LLC](http://www.lavalley.net) per aver segnalato un problema descritto nel bollettino MS11-074
-   Irene Abezgauz di [Seeker](http://www.seekersec.com) per aver collaborato con noi a un aggiornamento di difesa in profondità incluso nel bollettino MS11-074

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://go.microsoft.com/fwlink/?linkid=21742).
-   Per usufruire dei servizi del supporto tecnico, visitare il sito Web del [Security Support](http://go.microsoft.com/fwlink/?linkid=21131). Le chiamate al supporto tecnico relative agli aggiornamenti per la protezione sono gratuite. Per ulteriori informazioni sulle opzioni di supporto disponibili, visitare il sito [Microsoft Aiuto & Supporto](http://support.microsoft.com/).
-   I clienti internazionali possono ottenere assistenza tecnica presso le filiali Microsoft locali. Il supporto relativo agli aggiornamenti di protezione è gratuito. Per ulteriori informazioni su come contattare Microsoft per ottenere supporto, visitare il sito per [supporto e assistenza internazionale](http://go.microsoft.com/fwlink/?linkid=21155).

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (13 settembre 2011): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (13 settembre 2011): Per MS11-074, aggiunta del collegamento di aggiornamento per l'aggiornamento di Microsoft Office SharePoint Server 2010 e Microsoft Office SharePoint Server 2010 Service Pack 1 (pplwfe) (KB2560890).

*Built at 2014-04-18T01:50:00Z-07:00*
