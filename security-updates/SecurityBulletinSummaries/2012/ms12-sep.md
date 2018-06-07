---
TOCTitle: 'MS12-SEP'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Settembre 2012'
ms:assetid: 'ms12-sep'
ms:contentKeyID: 61240077
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms12-sep(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Settembre 2012
===================================================================

Data di pubblicazione: martedì 11 settembre 2012 | Aggiornamento: venerdì 21 settembre 2012

**Versione:** 2.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati in settembre 2012.

Con il rilascio dei bollettini sulla sicurezza di settembre 2012, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 19 settembre 2012. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 12 settembre 2012 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di settembre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032522555&culture=en-us). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032522555&culture=en-us).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti sul bollettino straordinario il 21 settembre 2012 alle 12:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di settembre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032529852&culture=en-us). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032529852&culture=en-us).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255505">MS12-063</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2744842)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e quattro vulnerabilità segnalate privatamente in Internet Explorer. Le vulnerabilità con gli effetti più gravi sulla protezione possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando una di queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=254184">MS12-061</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Visual Studio Team Foundation Server può consentire l'acquisizione di privilegi più elevati (2719584)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Visual Studio Team Foundation Server. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente fa clic su un collegamento appositamente predisposto in un messaggio di posta elettronica o se naviga a una pagina Web utilizzata per sfruttare la vulnerabilità. In tutti questi casi, comunque, non è in alcun modo possibile obbligare gli utenti ad eseguire queste azioni. L'utente malintenzionato deve invece convincere gli utenti a visitare un sito Web, in genere inducendoli a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che li indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Strumenti per gli sviluppatori Microsoft</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=261858">MS12-062</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in System Center Configuration Manager</strong> <strong>può consentire l'acquisizione di privilegi più elevati (2741528)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente in Microsoft System Center Operations Manager. La vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente visita un sito Web interessato attraverso un URL appositamente predisposto. Non è in alcun modo possibile obbligare gli utenti a visitare un sito Web di questo tipo. L'utente malintenzionato dovrebbe invece invogliare le vittime a visitare il sito Web, in genere inducendole a fare clic su un collegamento in un messaggio di posta elettronica o di Instant Messenger che le indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Software dei server Microsoft</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
**Come utilizzare questa tabella**
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259.aspx).
  
Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.

 
<table style="border:1px solid black;">
<thead>
<tr class="header">
<th style="border:1px solid black;" >ID bollettino</th>
<th style="border:1px solid black;" >Titolo della vulnerabilità</th>
<th style="border:1px solid black;" >ID CVE</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability per la versione più recente del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability per la versione meno recente del software</th>
<th style="border:1px solid black;" >Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service</th>
<th style="border:1px solid black;" >Note fondamentali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=254184">MS12-061</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al filtro XSS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1892">CVE-2012-1892</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=261858">MS12-062</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al filtro XSS riflesso</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2536">CVE-2012-2536</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255505">MS12-063</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free in OnMove</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1529">CVE-2012-1529</a></td>
<td style="border:1px solid black;">Non interessato[1]</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255505">MS12-063</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free nel listener di eventi</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2546">CVE-2012-2546</a></td>
<td style="border:1px solid black;">Non interessato[1]</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255505">MS12-063</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free del layout</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2548">CVE-2012-2548</a></td>
<td style="border:1px solid black;">Non interessato[1]</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">2</a> - Difficile costruire il codice dannoso</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255505">MS12-063</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free in cloneNode</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2557">CVE-2012-2557</a></td>
<td style="border:1px solid black;">Non interessato[1]</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255505">MS12-063</a></td>
<td style="border:1px solid black;">Vulnerabilità legata a un errore di tipo use-after-free in execCommand</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-4969">CVE-2012-4969</a></td>
<td style="border:1px solid black;">Non interessato[1]</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/it-it/security/cc998259.aspx">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Microsoft è a conoscenza di un limitato numero di attacchi che tentano di utilizzare questa vulnerabilità.</td>
</tr>
</tbody>
</table>
 

<sup>[1]</sup>Internet Explorer 10 non è interessato da questa vulnerabilità.

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
<th colspan="2">
Windows XP
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-063**](http://go.microsoft.com/fwlink/?linkid=255505)
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
Windows XP Service Pack 3
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=967c9ef3-db48-4c2f-9a67-87851fd54962)  
(KB2744842)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=6ba78d4c-3657-4963-b2da-7a3763c6b5c9)  
(KB2744842)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=ac71ffe3-f077-4753-a238-47a2e9623363)  
(KB2744842)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=020b36c6-7050-4458-8762-bae35eb713cd)  
(KB2744842)  
(Critico)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=1e2e412a-be97-407e-9f02-fc074db3bb07)  
(KB2744842)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c727d956-be3e-4cd2-913c-f26cb6c33227)  
(KB2744842)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-063**](http://go.microsoft.com/fwlink/?linkid=255505)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità** **aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=7aaaa15b-87d8-4afc-b183-8ce5becda026)  
(KB2744842)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=aef34ce4-a6ce-4f5e-9892-0a7fbd90c3b4)  
(KB2744842)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d63e25ad-ab8c-425f-89cd-29cd2b7b69d6)  
(KB2744842)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=366feacb-16ad-455c-b2ad-5038f998c432)  
(KB2744842)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=baa47c53-2724-43ef-8590-d3733b47e75b)  
(KB2744842)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=84144e56-f653-4c92-bf49-d44d9ba10489)  
(KB2744842)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 6](http://www.microsoft.com/downloads/details.aspx?familyid=c28d6dc3-c2f0-4505-a545-85b7a0e3e2dc)  
(KB2744842)  
(Moderato)  
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=86c28695-86a5-4c17-82d6-7f98b3162aa6)  
(KB2744842)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="2">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-063**](http://go.microsoft.com/fwlink/?linkid=255505)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=053546fc-ed41-43c2-b4f2-b76334314f5c)  
(KB2744842)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=0a5a446d-0a48-4eec-b424-87339b34a3be)  
(KB2744842)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=daba1ef1-62db-43db-9d5b-495aa2d3550f)  
(KB2744842)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=cbe5681b-c28e-4a6a-9b97-0bfe44acf077)  
(KB2744842)  
(Critico)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=5642136e-68f6-42e8-b48e-1549733c6e7d)  
(KB2744842)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=aae496ef-fca2-4632-9a8f-2108722d2b28)  
(KB2744842)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-063**](http://go.microsoft.com/fwlink/?linkid=255505)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=df861b42-bcf2-4f7a-9019-f49e6725f5dc)  
(KB2744842)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=1d4f0f25-9539-4c38-babb-4af7f0f4c6cf)  
(KB2744842)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=0b2965d7-e0b2-4035-a9e4-f6badb389098)  
(KB2744842)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=fa9878c0-b7e5-43ac-b1eb-679e62cf62fc)  
(KB2744842)  
(Moderato)  
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=10bab7d4-0dd8-4fa7-b26c-715a68553707)  
(KB2744842)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=612a94ef-0950-41e8-9875-a8f0e71eba6f)  
(KB2744842)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 7](http://www.microsoft.com/downloads/details.aspx?familyid=ded887a4-a06d-4447-b19d-19d0f4928523)  
(KB2744842)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="2">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-063**](http://go.microsoft.com/fwlink/?linkid=255505)
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
Windows 7 per sistemi 32-bit
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=93591461-39ff-4cbd-8df3-88cb80ed6255)  
(KB2744842)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=b303f86a-df17-4961-b677-0c38bd6a86d3)  
(KB2744842)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=93591461-39ff-4cbd-8df3-88cb80ed6255)  
(KB2744842)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=b303f86a-df17-4961-b677-0c38bd6a86d3)  
(KB2744842)  
(Critico)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=e2083388-19a9-4754-9449-1dad2a7f7543)  
(KB2744842)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=01045ee2-c7c4-4078-969f-905fd7e8774f)  
(KB2744842)  
(Critico)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=e2083388-19a9-4754-9449-1dad2a7f7543)  
(KB2744842)  
(Critico)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=01045ee2-c7c4-4078-969f-905fd7e8774f)  
(KB2744842)  
(Critico)
</td>
</tr>
<tr>
<th colspan="2">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-063**](http://go.microsoft.com/fwlink/?linkid=255505)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d46ec8ea-b8c8-42d9-a201-f36eb97b91b8)  
(KB2744842)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=c44a0253-fefc-4ce6-9cfd-396fdea71f8d)  
(KB2744842)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=d46ec8ea-b8c8-42d9-a201-f36eb97b91b8)  
(KB2744842)  
(Moderato)  
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=c44a0253-fefc-4ce6-9cfd-396fdea71f8d)  
(KB2744842)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c132173b-f869-47ec-bb70-6307081473fe)  
(KB2744842)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 8](http://www.microsoft.com/downloads/details.aspx?familyid=c132173b-f869-47ec-bb70-6307081473fe)  
(KB2744842)  
(Moderato)
</td>
</tr>
</table>
 

#### Strumenti e software Microsoft per gli sviluppatori

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft Visual Studio Team Foundation Server
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-061**](http://go.microsoft.com/fwlink/?linkid=254184)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Visual Studio Team Foundation Server 2010 Service Pack 1
</td>
<td style="border:1px solid black;">
[Microsoft Visual Studio Team Foundation Server 2010 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=721c4a38-b255-4792-83a5-7526a680a79a)<sup>[1]</sup>
(KB2719584)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS12-061**

<sup>[1]</sup>Questo aggiornamento è cumulativo e sostituisce aggiornamenti cumulativi precedenti per il software specificato.

#### Software dei server Microsoft

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Microsoft System Center Configuration Manager
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-062**](http://go.microsoft.com/fwlink/?linkid=261858)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Systems Management Server 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Systems Management Server 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f3a3d8e1-d551-43b4-9d54-9536f30c074d)<sup>[1]</sup>
(KB2733631)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft System Center Configuration Manager 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft System Center Configuration Manager 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=89890c0e-118b-49ea-9fd1-6d23c674f9e8)<sup>[1]</sup>
(KB2721642)  
(Importante)
</td>
</tr>
</table>
 
**Nota per MS12-062**

<sup>[1]</sup>Questo aggiornamento è disponibile soltanto nell'Area download Microsoft.

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security TechCenter](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. I clienti possono visitare [Microsoft Safety &amp; Security Center](http://www.microsoft.com/italy/athome/security/default.mspx), dove queste informazioni sono disponibili anche facendo clic su "Aggiornamenti per la protezione".

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/it-it/default.aspx). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

Per i clienti che utilizzano Microsoft Office per Mac, Microsoft AutoUpdate per Mac può contribuire a mantenere aggiornato il proprio software Microsoft. Per ulteriori informazioni sull'utilizzo di Microsoft AutoUpdate per Mac, vedere [Verifica automatica degli aggiornamenti software](http://mac2.microsoft.com/help/office/14/en-us/word/item/ffe35357-8f25-4df8-a0a3-c258526c64ea).

Infine, gli aggiornamenti per la protezione possono essere scaricati dal [catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/home.aspx). Il catalogo di Microsoft Update è uno strumento che consente di eseguire ricerche, disponibile tramite Windows Update e Microsoft Update, che comprende aggiornamenti per la protezione, driver e service pack. Se si cerca in base al numero del bollettino sulla sicurezza (ad esempio, "MS12-001"), è possibile aggiungere tutti gli aggiornamenti applicabili al carrello (inclusi aggiornamenti in lingue diverse) e scaricarli nella cartella specificata. Per ulteriori informazioni sul catalogo di Microsoft Update, vedere le [domande frequenti sul catalogo di Microsoft Update](http://catalog.update.microsoft.com/v7/site/faq.aspx).

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

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/it-it/default.aspx). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](http://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

#### Ringraziamenti

Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

-   Sunil Yadav di INR Labs ([Network Intelligence India](http://niiconsulting.com/)) per aver segnalato un problema descritto nel bollettino MS12-061
-   Andy Yang di [Stratsec](http://www.stratsec.net) per aver segnalato un problema descritto nel bollettino MS12-062
-   Un ricercatore anonimo, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato un problema descritto nel bollettino MS12-063
-   [Rosario Valotta](https://sites.google.com/site/tentacoloviola) per aver segnalato un problema descritto nel bollettino MS12-063
-   Stephen Fewer di [Harmony Security](http://www.harmonysecurity.com/), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.hpenterprisesecurity.com/products/hp-tippingpoint-network-security/), per aver segnalato un problema descritto nel bollettino MS12-063
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.hpenterprisesecurity.com/products/hp-tippingpoint-network-security/), per aver segnalato un problema descritto nel bollettino MS12-063
-   Un ricercatore anonimo che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [TippingPoint](http://www.hpenterprisesecurity.com/products/hp-tippingpoint-network-security/), per aver segnalato un problema descritto nel bollettino MS12-063
-   [Mitre](http://www.mitre.org/) per aver collaborato con noi allo studio di un problema descritto nel bollettino MS12-063

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617.aspx)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (11 settembre 2012): Pubblicazione del riepilogo dei bollettini.
-   V2.0 (21 settembre 2012): È stato aggiunto il bollettino Microsoft sulla sicurezza MS12-063, aggiornamento cumulativo per la protezione di Internet Explorer (2744842). È stato inoltre aggiunto il collegamento al webcast del bollettino relativo al presente bollettino straordinario sulla sicurezza.

*Built at 2014-04-18T01:50:00Z-07:00*
