---
TOCTitle: 'MS12-NOV'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Novembre 2012'
ms:assetid: 'ms12-nov'
ms:contentKeyID: 61240075
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms12-nov(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Security Bulletin Summary

Riepilogo dei bollettini Microsoft sulla sicurezza - Novembre 2012
==================================================================

Data di pubblicazione: martedì 13 novembre 2012 | Aggiornamento: mercoledì 14 novembre 2012

**Versione:** 2.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati in novembre 2012.

Con il rilascio dei bollettini sulla sicurezza di novembre 2012, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 8 novembre 2012. Per ulteriori informazioni su questo servizio, vedere la [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un webcast per rispondere alle domande dei clienti su questi bollettini in data 14 novembre 2012 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di novembre](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032522560&culture=it-it). Dopo questa data, il webcast sarà disponibile [su richiesta](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032522560&culture=it-it).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=268299">MS12-071</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2761451)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve tre vulnerabilità di Internet Explorer segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=260820">MS12-072</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nella Shell di Windows possono consentire l'esecuzione di codice in modalità remota (2727528)</strong> <strong><br />
<br />
</strong>Questo aggiornamento per la protezione risolve due vulnerabilità segnalate privatamente in Microsoft Windows. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente naviga a una cartella di sincronia file appositamente predisposta in Esplora risorse. Sfruttando questa vulnerabilità, un utente malintenzionato può eseguire codice non autorizzato nel contesto dell'utente corrente. Se l'utente corrente è connesso con privilegi di amministratore, un utente malintenzionato può assumere il controllo completo del sistema interessato. Potrebbe quindi installare programmi e visualizzare, modificare o eliminare dati oppure creare nuovi account con diritti utente completi. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=255026">MS12-074</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in .NET Framework possono consentire l'esecuzione di codice in modalità remota (2745030)</strong> <strong><br />
<br />
</strong>Questo aggiornamento per la protezione risolve cinque vulnerabilità in .NET Framework che sono state segnalate privatamente. La più grave di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente malintenzionato convince l'utente di un sistema di destinazione a utilizzare un file di configurazione automatica del proxy dannoso e poi inietta codice nell'applicazione attualmente in esecuzione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=270856">MS12-075</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità nei driver in modalità kernel di Windows possono consentire l'esecuzione di codice in modalità remota (2761226)</strong> <strong><br />
<br />
</strong>Questo aggiornamento per la protezione risolve tre vulnerabilità segnalate privatamente in Microsoft Windows. La vulnerabilità potrebbe consentire l'esecuzione di codice in modalità remota se un utente apre un documento appositamente predisposto o visita una pagina Web dannosa che incorpora i file di caratteri TrueType. Un utente malintenzionato deve convincere gli utenti a visitare il sito Web, in genere inducendoli a fare clic su un collegamento in un messaggio di posta elettronica che li indirizzi al sito.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=260964">MS12-076</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità di Microsoft Excel possono consentire l'esecuzione di codice in modalità remota (2720184)</strong> <strong><br />
<br />
</strong>Questo aggiornamento per la protezione risolve quattro vulnerabilità di Microsoft Office segnalate privatamente. Le vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente apra un file di Excel appositamente predisposto con una versione interessata di Microsoft Excel. Sfruttando tale vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a><br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=258247">MS12-073</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Internet Information Services (IIS) possono consentire l'intercettazione di informazioni personali (2733829)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e una vulnerabilità segnalata privatamente in Microsoft Internet Information Services (IIS). La vulnerabilità più grave può consentire l'intercettazione di informazioni personali se un utente malintenzionato invia comandi FTP appositamente predisposti al server.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Moderato</a><br />
Intercettazione di informazioni personali</td>
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
  
| ID bollettino                                             | Titolo della vulnerabilità                                                                       | ID CVE                                                                           | Valutazione dell'Exploitability per la versione più recente del software                                              | Valutazione dell'Exploitability per la versione meno recente del software                                               | Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service | Note fondamentali                                                          |  
|-----------------------------------------------------------|--------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|----------------------------------------------------------------------------|  
| [MS12-071](http://go.microsoft.com/fwlink/?linkid=268299) | Vulnerabilità legata a un errore di tipo use-after-free di CFormElement                          | [CVE-2012-1538](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1538) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS12-071](http://go.microsoft.com/fwlink/?linkid=268299) | Vulnerabilità legata a un errore di tipo use-after-free di CTreePos                              | [CVE-2012-1539](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1539) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Temporaneo                                                                       | (Nessuna)                                                                  |  
| [MS12-071](http://go.microsoft.com/fwlink/?linkid=268299) | Vulnerabilità legata a un errore di tipo use-after-free di CTreeNode                             | [CVE-2012-4775](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-4775) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS12-072](http://go.microsoft.com/fwlink/?linkid=260820) | Vulnerabilità legata all'underflow dei valori integer nella Sincronia file di Windows            | [CVE-2012-1527](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1527) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS12-072](http://go.microsoft.com/fwlink/?linkid=260820) | Vulnerabilità legata all'overflow dei valori integer nella Sincronia file di Windows             | [CVE-2012-1528](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1528) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Temporaneo                                                                       | (Nessuna)                                                                  |  
| [MS12-074](http://go.microsoft.com/fwlink/?linkid=255026) | Vulnerabilità legata all'elusione della riflessione                                              | [CVE-2012-1895](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1895) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS12-074](http://go.microsoft.com/fwlink/?linkid=255026) | Vulnerabilità legata all'intercettazione delle informazioni di protezione dall'accesso di codice | [CVE-2012-1896](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1896) | Non interessato                                                                                                       | [3](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Scarsa probabilità di sfruttamento della vulnerabilità | Non applicabile                                                                  | Questa vulnerabilità riguarda l'intercettazione di informazioni personali. |  
| [MS12-074](http://go.microsoft.com/fwlink/?linkid=255026) | Vulnerabilità legata al caricamento non sicuro delle librerie in .NET                            | [CVE-2012-2519](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2519) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS12-074](http://go.microsoft.com/fwlink/?linkid=255026) | Vulnerabilità legata a Web Proxy Auto-Discovery                                                  | [CVE-2012-4776](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-4776) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Permanente                                                                       | (Nessuna)                                                                  |  
| [MS12-074](http://go.microsoft.com/fwlink/?linkid=255026) | Vulnerabilità legata all'ottimizzazione della riflessione di WPF                                 | [CVE-2012-4777](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-4777) | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS12-075](http://go.microsoft.com/fwlink/?linkid=270856) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                | [CVE-2012-2530](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2530) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Permanente                                                                       | (Nessuna)                                                                  |  
| [MS12-075](http://go.microsoft.com/fwlink/?linkid=270856) | Vulnerabilità legata a un errore di tipo use-after-free di Win32k                                | [CVE-2012-2553](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2553) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Permanente                                                                       | (Nessuna)                                                                  |  
| [MS12-075](http://go.microsoft.com/fwlink/?linkid=270856) | Vulnerabilità legata all'analisi dei caratteri TrueType                                          | [CVE-2012-2897](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2897) | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Difficile costruire il codice dannoso                | [2](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Difficile costruire il codice dannoso                  | Permanente                                                                       | (Nessuna)                                                                  |  
| [MS12-076](http://go.microsoft.com/fwlink/?linkid=260964) | Vulnerabilità legata all'overflow degli heap SerAuxErrBar in Excel                               | [CVE-2012-1885](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1885) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS12-076](http://go.microsoft.com/fwlink/?linkid=260964) | Vulnerabilità legata al danneggiamento della memoria in Excel                                    | [CVE-2012-1886](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1886) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS12-076](http://go.microsoft.com/fwlink/?linkid=260964) | Vulnerabilità legata a un errore di tipo use-after-free di lunghezza non valida di SST in Excel  | [CVE-2012-1887](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-1887) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                  |  
| [MS12-076](http://go.microsoft.com/fwlink/?linkid=260964) | Vulnerabilità legata all'overflow dello stack in Excel                                           | [CVE-2012-2543](http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2012-2543) | Non interessato                                                                                                       | [1](http://technet.microsoft.com/it-it/security/cc998259.aspx) - Alta probabilità di sfruttamento della vulnerabilità   | Non applicabile                                                                  | (Nessuna)                                                                  |
  
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
<th colspan="6">
Windows XP  
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-071**](http://go.microsoft.com/fwlink/?linkid=268299)
</td>
<td style="border:1px solid black;">
[**MS12-072**](http://go.microsoft.com/fwlink/?linkid=260820)
</td>
<td style="border:1px solid black;">
[**MS12-074**](http://go.microsoft.com/fwlink/?linkid=255026)
</td>
<td style="border:1px solid black;">
[**MS12-075**](http://go.microsoft.com/fwlink/?linkid=270856)
</td>
<td style="border:1px solid black;">
[**MS12-073**](http://go.microsoft.com/fwlink/?linkid=266541)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**
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
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=fcc633d6-fe18-4220-9b68-ff1479e4dec5)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.0 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=f5472e86-2b2f-42bd-abca-6adf84973efa)  
(KB2698035)  
(solo Media Center Edition 2005 Service Pack 3 e Tablet PC Edition 2005 Service Pack 3)  
(Importante)  
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=17a110d1-ef31-4230-9f2a-0df190c28747)  
(KB2698023)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e7e75292-efcf-4c97-960c-958f81931cbf)  
(KB2729450)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=31f2c645-b171-4f11-884b-f5056ef57b4f)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
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
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=a736c3f0-0326-4a0a-9c12-f61bafa537bb)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=17a110d1-ef31-4230-9f2a-0df190c28747)  
(KB2698023)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e7e75292-efcf-4c97-960c-958f81931cbf)  
(KB2729450)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows XP Professional x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=828699ac-eb88-4ff8-9110-69c206f5ef54)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="6">
Windows Server 2003
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-071**](http://go.microsoft.com/fwlink/?linkid=268299)
</td>
<td style="border:1px solid black;">
[**MS12-072**](http://go.microsoft.com/fwlink/?linkid=260820)
</td>
<td style="border:1px solid black;">
[**MS12-074**](http://go.microsoft.com/fwlink/?linkid=255026)
</td>
<td style="border:1px solid black;">
[**MS12-075**](http://go.microsoft.com/fwlink/?linkid=270856)
</td>
<td style="border:1px solid black;">
[**MS12-073**](http://go.microsoft.com/fwlink/?linkid=266541)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=0383bdea-53d1-4799-b380-14da1595882a)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=efe0de22-8ca3-474e-acda-7203bf66d0a3)  
(KB2698032)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e7e75292-efcf-4c97-960c-958f81931cbf)  
(KB2729450)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=73f5dec6-ccda-426d-8d2c-a2db3e59734a)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=615a96fe-88a5-498b-ae20-bbfc43e3b652)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=17a110d1-ef31-4230-9f2a-0df190c28747)  
(KB2698023)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e7e75292-efcf-4c97-960c-958f81931cbf)  
(KB2729450)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dc9cd62a-c42d-4c54-bc14-7abd34aeb865)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=36962e96-0eaa-45a9-b2d6-6bec3242c73e)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=17a110d1-ef31-4230-9f2a-0df190c28747)  
(KB2698023)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e7e75292-efcf-4c97-960c-958f81931cbf)  
(KB2729450)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2003 con SP2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=e4ec19ea-06f2-4164-8e39-84f1d7a47ae7)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="6">
Windows Vista
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-071**](http://go.microsoft.com/fwlink/?linkid=268299)
</td>
<td style="border:1px solid black;">
[**MS12-072**](http://go.microsoft.com/fwlink/?linkid=260820)
</td>
<td style="border:1px solid black;">
[**MS12-074**](http://go.microsoft.com/fwlink/?linkid=255026)
</td>
<td style="border:1px solid black;">
[**MS12-075**](http://go.microsoft.com/fwlink/?linkid=270856)
</td>
<td style="border:1px solid black;">
[**MS12-073**](http://go.microsoft.com/fwlink/?linkid=266541)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Vista Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=205f1cf3-5431-4740-96c2-eaf019edeeeb)  
(KB2761451)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c19585e3-a358-40b0-80a3-8dbb25ba8557)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=17a110d1-ef31-4230-9f2a-0df190c28747)  
(KB2698023)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6d742523-5f51-4db7-b05f-a9055b36b090)  
(KB2729453)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=ca52497c-8023-42de-b707-2bc1bcee4579)  
(KB2729460)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=48f57fe1-e180-4b6b-87f5-8dd0c8e821d3)  
(KB2737083)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=c4b3fb44-338d-48be-9981-53fa2cf3094a)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.0 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=e1785af2-a211-467e-a696-d53840581bca)<sup>[1]</sup>
(KB2716513)  
(Moderato)  
[Servizio FTP Microsoft 7.5 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=b91091d0-176f-4ff9-98d2-74768b747c3a)<sup>[1]</sup>
(KB2716513)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=7e7b681c-c580-4671-a515-e5b469002c93)  
(KB2761451)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=31f5ad28-ffe9-4370-b3fc-62eb9fc0c4dd)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=17a110d1-ef31-4230-9f2a-0df190c28747)  
(KB2698023)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6d742523-5f51-4db7-b05f-a9055b36b090)  
(KB2729453)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=ca52497c-8023-42de-b707-2bc1bcee4579)  
(KB2729460)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=48f57fe1-e180-4b6b-87f5-8dd0c8e821d3)  
(KB2737083)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Vista x64 Edition Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=7a58e874-f3fc-4db8-8de0-cbfc6ebbf349)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.0 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=2db93767-f364-49c6-9a03-39604173771f)<sup>[1]</sup>
(KB2716513)  
(Moderato)  
[Servizio FTP Microsoft 7.5 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=0c499445-595f-459f-86cf-b821cbb5fa65)<sup>[1]</sup>
(KB2716513)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="6">
Windows Server 2008
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-071**](http://go.microsoft.com/fwlink/?linkid=268299)
</td>
<td style="border:1px solid black;">
[**MS12-072**](http://go.microsoft.com/fwlink/?linkid=260820)
</td>
<td style="border:1px solid black;">
[**MS12-074**](http://go.microsoft.com/fwlink/?linkid=255026)
</td>
<td style="border:1px solid black;">
[**MS12-075**](http://go.microsoft.com/fwlink/?linkid=270856)
</td>
<td style="border:1px solid black;">
[**MS12-073**](http://go.microsoft.com/fwlink/?linkid=266541)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=0161baaa-5d7b-4442-a202-41c64a73c9a8)  
(KB2761451)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=258048b5-d992-4821-8836-72262a7b5bb7)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=17a110d1-ef31-4230-9f2a-0df190c28747)  
(KB2698023)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6d742523-5f51-4db7-b05f-a9055b36b090)  
(KB2729453)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=ca52497c-8023-42de-b707-2bc1bcee4579)  
(KB2729460)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=48f57fe1-e180-4b6b-87f5-8dd0c8e821d3)  
(KB2737083)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=17b987db-0551-45c3-aab1-0cc11ae60dcc)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.0 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=cb3598ae-b647-4aaa-90fb-b4d8aa1cf211)<sup>[1]</sup>
(KB2716513)  
(Moderato)  
[Servizio FTP Microsoft 7.5 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=8b135d6f-0f6c-4bd5-bf64-d79ae16ac6a5)<sup>[1]</sup>
(KB2716513)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2
</td>
<td style="border:1px solid black;">
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=52f652bd-edc4-4450-91b4-f19401d2201c)  
(KB2761451)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=1c067cb2-71a5-4f8d-9b11-243c9e5318ce)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=17a110d1-ef31-4230-9f2a-0df190c28747)  
(KB2698023)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6d742523-5f51-4db7-b05f-a9055b36b090)  
(KB2729453)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=ca52497c-8023-42de-b707-2bc1bcee4579)  
(KB2729460)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=48f57fe1-e180-4b6b-87f5-8dd0c8e821d3)  
(KB2737083)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dd9bd994-41e3-46a1-9dfb-c6d89a3ef883)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.0 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=74d130a4-f42a-48af-87fc-349a1e107529)<sup>[1]</sup>
(KB2716513)  
(Moderato)  
[Servizio FTP Microsoft 7.5 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=b061a0b0-66e2-49a2-8d20-0c5a6948aecf)<sup>[1]</sup>
(KB2716513)  
(Moderato)
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 1.1 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=17a110d1-ef31-4230-9f2a-0df190c28747)  
(KB2698023)  
(Importante)  
[Microsoft .NET Framework 2.0 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=6d742523-5f51-4db7-b05f-a9055b36b090)  
(KB2729453)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi Itanium Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=fab87b20-398f-4043-9cbe-ffcae8e19ff0)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="6">
Windows 7
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-071**](http://go.microsoft.com/fwlink/?linkid=268299)
</td>
<td style="border:1px solid black;">
[**MS12-072**](http://go.microsoft.com/fwlink/?linkid=260820)
</td>
<td style="border:1px solid black;">
[**MS12-074**](http://go.microsoft.com/fwlink/?linkid=255026)
</td>
<td style="border:1px solid black;">
[**MS12-075**](http://go.microsoft.com/fwlink/?linkid=270856)
</td>
<td style="border:1px solid black;">
[**MS12-073**](http://go.microsoft.com/fwlink/?linkid=266541)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi 32-bit
</td>
<td style="border:1px solid black;">
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=279ac887-2420-48d7-bb85-c7cab49f7ff8)  
(KB2761451)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=22ab8987-2506-433f-9f12-0ab60d569949)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=bbdf1e16-67d9-413c-bad2-31d164fea0da)  
(KB2729451)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi 32-bit](http://www.microsoft.com/downloads/details.aspx?familyid=c222943e-9888-4fb9-b9a2-7a035311c887)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=77a4ae4e-a75c-490a-a0b1-137816ed5c89)  
(KB2716513)  
(Moderato)  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=fb265aa5-0e09-411a-a0fe-bbb42c409a81)  
(KB2719033)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=279ac887-2420-48d7-bb85-c7cab49f7ff8)  
(KB2761451)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=22ab8987-2506-433f-9f12-0ab60d569949)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=aa5b1e9c-3068-40e3-b04f-6a71f1a51d45)  
(KB2729452)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=ca52497c-8023-42de-b707-2bc1bcee4579)  
(KB2729460)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=48f57fe1-e180-4b6b-87f5-8dd0c8e821d3)  
(KB2737083)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi a 32 bit Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=c222943e-9888-4fb9-b9a2-7a035311c887)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=77a4ae4e-a75c-490a-a0b1-137816ed5c89)  
(KB2716513)  
(Moderato)  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=fb265aa5-0e09-411a-a0fe-bbb42c409a81)  
(KB2719033)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64
</td>
<td style="border:1px solid black;">
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=eb9babdc-3fac-4ce9-a7ca-85e26a9cb11d)  
(KB2761451)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=fc70708e-9de9-4618-b0ab-d9aa3e2baea0)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=bbdf1e16-67d9-413c-bad2-31d164fea0da)  
(KB2729451)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=50d7c25f-a67f-4946-b6db-70d9bd4dc178)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=bda21ea5-f160-4361-8ede-40f6a53a30da)  
(KB2716513)  
(Moderato)  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=52b6ed39-b7c1-4d49-a6a7-e6208fab24fa)  
(KB2719033)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=eb9babdc-3fac-4ce9-a7ca-85e26a9cb11d)  
(KB2761451)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=fc70708e-9de9-4618-b0ab-d9aa3e2baea0)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=aa5b1e9c-3068-40e3-b04f-6a71f1a51d45)  
(KB2729452)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=ca52497c-8023-42de-b707-2bc1bcee4579)  
(KB2729460)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=48f57fe1-e180-4b6b-87f5-8dd0c8e821d3)  
(KB2737083)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows 7 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=50d7c25f-a67f-4946-b6db-70d9bd4dc178)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=bda21ea5-f160-4361-8ede-40f6a53a30da)  
(KB2716513)  
(Moderato)  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=52b6ed39-b7c1-4d49-a6a7-e6208fab24fa)  
(KB2719033)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="6">
Windows Server 2008 R2
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-071**](http://go.microsoft.com/fwlink/?linkid=268299)
</td>
<td style="border:1px solid black;">
[**MS12-072**](http://go.microsoft.com/fwlink/?linkid=260820)
</td>
<td style="border:1px solid black;">
[**MS12-074**](http://go.microsoft.com/fwlink/?linkid=255026)
</td>
<td style="border:1px solid black;">
[**MS12-075**](http://go.microsoft.com/fwlink/?linkid=270856)
</td>
<td style="border:1px solid black;">
[**MS12-073**](http://go.microsoft.com/fwlink/?linkid=266541)
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
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=3d0a4455-b788-4ad7-be0c-5824f6103694)  
(KB2761451)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=800cd622-d271-41a4-bd21-a76177d2b272)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=bbdf1e16-67d9-413c-bad2-31d164fea0da)  
(KB2729451)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=114b596c-36e1-45f5-99e2-f5fdd96b1a30)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=87f3aa7a-ee84-4e7e-972c-e83a2a06a0ef)  
(KB2716513)  
(Moderato)  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=e1502884-1149-47b8-93af-7f82c5d83819)  
(KB2719033)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1
</td>
<td style="border:1px solid black;">
[Internet Explorer 9](http://www.microsoft.com/downloads/details.aspx?familyid=3d0a4455-b788-4ad7-be0c-5824f6103694)  
(KB2761451)  
(Moderato)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=800cd622-d271-41a4-bd21-a76177d2b272)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=aa5b1e9c-3068-40e3-b04f-6a71f1a51d45)  
(KB2729452)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=ca52497c-8023-42de-b707-2bc1bcee4579)  
(KB2729460)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=48f57fe1-e180-4b6b-87f5-8dd0c8e821d3)  
(KB2737083)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=114b596c-36e1-45f5-99e2-f5fdd96b1a30)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=87f3aa7a-ee84-4e7e-972c-e83a2a06a0ef)  
(KB2716513)  
(Moderato)  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=e1502884-1149-47b8-93af-7f82c5d83819)  
(KB2719033)  
(Moderato)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=bbdf1e16-67d9-413c-bad2-31d164fea0da)  
(KB2729451)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium](http://www.microsoft.com/downloads/details.aspx?familyid=70447115-957d-48a4-bc27-395abaf22149)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=92cd0488-03c2-400d-a506-eb2eb8fce7c7)  
(KB2716513)  
(Moderato)  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=1eea7e7f-83bf-40fc-a978-a4d08af8162a)  
(KB2719033)  
(Moderato)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=aa5b1e9c-3068-40e3-b04f-6a71f1a51d45)  
(KB2729452)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi Itanium Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=70447115-957d-48a4-bc27-395abaf22149)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=92cd0488-03c2-400d-a506-eb2eb8fce7c7)  
(KB2716513)  
(Moderato)  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=1eea7e7f-83bf-40fc-a978-a4d08af8162a)  
(KB2719033)  
(Moderato)
</td>
</tr>
<tr>
<th colspan="6">
Windows 8
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-071**](http://go.microsoft.com/fwlink/?linkid=268299)
</td>
<td style="border:1px solid black;">
[**MS12-072**](http://go.microsoft.com/fwlink/?linkid=260820)
</td>
<td style="border:1px solid black;">
[**MS12-074**](http://go.microsoft.com/fwlink/?linkid=255026)
</td>
<td style="border:1px solid black;">
[**MS12-075**](http://go.microsoft.com/fwlink/?linkid=270856)
</td>
<td style="border:1px solid black;">
[**MS12-073**](http://go.microsoft.com/fwlink/?linkid=266541)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 8 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=d7c93ade-f7e3-4b6f-b93d-894ca313282f)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=89faa423-42fa-48ff-be71-8fd58fa523a8)  
(KB2729462)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=c9778a0f-264e-476b-8e40-742e0ab56200)  
(KB2737084)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=b120a7a2-0eff-41d6-981e-60e5ecd55869)<sup>[2]</sup>
(KB2756872)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
[Windows 8 per sistemi a 32 bit](http://www.microsoft.com/downloads/details.aspx?familyid=24ce3f78-fb25-4f51-8bb0-8cebf19d8843)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows 8 per sistemi a 64 bit
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows 8 per sistemi a 64 bit](http://www.microsoft.com/downloads/details.aspx?familyid=7c4a17b7-bb7f-456c-9cb3-3a355e192734)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=89faa423-42fa-48ff-be71-8fd58fa523a8)  
(KB2729462)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=c9778a0f-264e-476b-8e40-742e0ab56200)  
(KB2737084)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=c7a417e6-72e5-4087-bb89-fb8e7f57894c)<sup>[2]</sup>
(KB2756872)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
[Windows 8 per sistemi a 64 bit](http://www.microsoft.com/downloads/details.aspx?familyid=72c49d94-757c-4da4-a895-96d0830bc667)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="6">
Windows Server 2012
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore** **del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-071**](http://go.microsoft.com/fwlink/?linkid=268299)
</td>
<td style="border:1px solid black;">
[**MS12-072**](http://go.microsoft.com/fwlink/?linkid=260820)
</td>
<td style="border:1px solid black;">
[**MS12-074**](http://go.microsoft.com/fwlink/?linkid=255026)
</td>
<td style="border:1px solid black;">
[**MS12-075**](http://go.microsoft.com/fwlink/?linkid=270856)
</td>
<td style="border:1px solid black;">
[**MS12-073**](http://go.microsoft.com/fwlink/?linkid=266541)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2012](http://www.microsoft.com/downloads/details.aspx?familyid=ad6189ae-9341-409b-a53e-486fef094fd0)  
(KB2727528)  
(Critico)
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=89faa423-42fa-48ff-be71-8fd58fa523a8)  
(KB2729462)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=c9778a0f-264e-476b-8e40-742e0ab56200)  
(KB2737084)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=0a7da3d1-a0ac-42a2-9929-b6d831deb9e3)<sup>[2]</sup>
(KB2756872)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
[Windows Server 2012](http://www.microsoft.com/downloads/details.aspx?familyid=2e69d496-25b4-4f24-97e0-47cb59c178aa)  
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="6">
Windows RT
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-071**](http://go.microsoft.com/fwlink/?linkid=268299)
</td>
<td style="border:1px solid black;">
[**MS12-072**](http://go.microsoft.com/fwlink/?linkid=260820)
</td>
<td style="border:1px solid black;">
[**MS12-074**](http://go.microsoft.com/fwlink/?linkid=255026)
</td>
<td style="border:1px solid black;">
[**MS12-075**](http://go.microsoft.com/fwlink/?linkid=270856)
</td>
<td style="border:1px solid black;">
[**MS12-073**](http://go.microsoft.com/fwlink/?linkid=266541)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)****
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)****
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Windows RT
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 4.5<sup>[3]</sup>
(KB2737084)  
(Importante)  
Microsoft .NET Framework 4.5<sup>[2]</sup><sup>[3]</sup>
(KB2756872)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
Windows RT<sup>[1]</sup>
(KB2761226)  
(Critico)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
<tr>
<th colspan="6">
Opzione di installazione Server Core
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-071**](http://go.microsoft.com/fwlink/?linkid=268299)
</td>
<td style="border:1px solid black;">
[**MS12-072**](http://go.microsoft.com/fwlink/?linkid=260820)
</td>
<td style="border:1px solid black;">
[**MS12-074**](http://go.microsoft.com/fwlink/?linkid=255026)
</td>
<td style="border:1px solid black;">
[**MS12-075**](http://go.microsoft.com/fwlink/?linkid=270856)
</td>
<td style="border:1px solid black;">
[**MS12-073**](http://go.microsoft.com/fwlink/?linkid=266541)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Livello di gravità aggregato**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
**Nessuno**
</td>
<td style="border:1px solid black;">
[**Critico**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
</td>
<td style="border:1px solid black;">
[**Moderato**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi a 32 bit Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=17b987db-0551-45c3-aab1-0cc11ae60dcc) (installazione Server Core)  
(KB2761226)  
(Importante)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.0 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=cb3598ae-b647-4aaa-90fb-b4d8aa1cf211)<sup>[1]</sup>
(KB2716513)  
(Moderato)  
[Servizio FTP Microsoft 7.5 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=8b135d6f-0f6c-4bd5-bf64-d79ae16ac6a5)<sup>[1]</sup>
(KB2716513)  
(Moderato)
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
Non applicabile
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
<td style="border:1px solid black;">
[Windows Server 2008 per sistemi x64 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=dd9bd994-41e3-46a1-9dfb-c6d89a3ef883) (installazione Server Core)  
(KB2761226)  
(Importante)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.0 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=74d130a4-f42a-48af-87fc-349a1e107529)<sup>[1]</sup>
(KB2716513)  
(Moderato)  
[Servizio FTP Microsoft 7.5 per IIS 7.0](http://www.microsoft.com/downloads/details.aspx?familyid=b061a0b0-66e2-49a2-8d20-0c5a6948aecf)<sup>[1]</sup>
(KB2716513)  
(Moderato)
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=bbdf1e16-67d9-413c-bad2-31d164fea0da)  
(KB2729451)  
(Critico)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64](http://www.microsoft.com/downloads/details.aspx?familyid=114b596c-36e1-45f5-99e2-f5fdd96b1a30) (installazione Server Core)  
(KB2761226)  
(Importante)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=87f3aa7a-ee84-4e7e-972c-e83a2a06a0ef)  
(KB2716513)  
(Moderato)  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=e1502884-1149-47b8-93af-7f82c5d83819)  
(KB2719033)  
(Moderato)
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5.1](http://www.microsoft.com/downloads/details.aspx?familyid=aa5b1e9c-3068-40e3-b04f-6a71f1a51d45)  
(KB2729452)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=f89c10fb-9f85-47b6-8204-d970d7e84e33)<sup>[1]</sup>
(KB2729449)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=ca52497c-8023-42de-b707-2bc1bcee4579)  
(KB2729460)  
(Critico)  
[Microsoft .NET Framework 4](http://www.microsoft.com/downloads/details.aspx?familyid=4c57041f-0ffc-47c9-82d9-8b1d24d27489)<sup>[1]</sup>
(KB2737019)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=48f57fe1-e180-4b6b-87f5-8dd0c8e821d3)  
(KB2737083)  
(Importante)
</td>
<td style="border:1px solid black;">
[Windows Server 2008 R2 per sistemi x64 Service Pack 1](http://www.microsoft.com/downloads/details.aspx?familyid=114b596c-36e1-45f5-99e2-f5fdd96b1a30) (installazione Server Core)  
(KB2761226)  
(Importante)
</td>
<td style="border:1px solid black;">
[Servizio FTP Microsoft 7.5 per IIS 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=87f3aa7a-ee84-4e7e-972c-e83a2a06a0ef)  
(KB2716513)  
(Moderato)  
[Internet Information Services 7.5](http://www.microsoft.com/downloads/details.aspx?familyid=e1502884-1149-47b8-93af-7f82c5d83819)  
(KB2719033)  
(Moderato)
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
Non applicabile
</td>
<td style="border:1px solid black;">
[Microsoft .NET Framework 3.5](http://www.microsoft.com/downloads/details.aspx?familyid=89faa423-42fa-48ff-be71-8fd58fa523a8)  
(KB2729462)  
(Critico)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=c9778a0f-264e-476b-8e40-742e0ab56200)  
(KB2737084)  
(Importante)  
[Microsoft .NET Framework 4.5](http://www.microsoft.com/downloads/details.aspx?familyid=0a7da3d1-a0ac-42a2-9929-b6d831deb9e3)<sup>[2]</sup>
(KB2756872)  
(Nessuno livello di gravità)
</td>
<td style="border:1px solid black;">
[Windows Server 2012](http://www.microsoft.com/downloads/details.aspx?familyid=2e69d496-25b4-4f24-97e0-47cb59c178aa) (installazione Server Core)  
(KB2761226)  
(Importante)
</td>
<td style="border:1px solid black;">
Non applicabile
</td>
</tr>
</table>
 
**Nota** **per MS12-073**

<sup>[1]</sup>Servizio FTP non predefinito per questo sistema operativo.

**Note per MS12-074**

<sup>[1]</sup>**.NET Framework 4 e .NET Framework 4 Client Profile interessati.** Le versioni 4 dei redistributable package .NET Framework sono disponibili in due profili: .NET Framework 4 e .NET Framework 4 Client Profile. .NET Framework 4 Client Profile è un sottoinsieme di .NET Framework 4. La vulnerabilità risolta in questo aggiornamento interessa sia .NET Framework 4 sia .NET Framework 4 Client Profile. Per ulteriori informazioni, vedere l'articolo di MSDN, [Installazione di .NET Framework](http://msdn.microsoft.com/it-it/library/5a4x27ek.aspx).

<sup>[2]</sup>I clienti che eseguono Microsoft .NET Framework 4.5 in Windows 8, Windows Server 2012 e Windows RT non sono interessati da questo problema. L'aggiornamento cumulativo a disponibilità generale per il client Windows 8 e per Windows Server 2012 (KB2756872), che è stato rilasciato il 10 ottobre 2012, contiene modifiche al sistema di difesa aggiuntive. I clienti che non hanno ancora installato questo aggiornamento sono incoraggiati a farlo come misura di difesa in profondità. Vedere la sezione Ulteriori Informazioni [nell'articolo della Microsoft Knowledge Base 2745030](http://support.microsoft.com/kb/2745030) per maggiori dettagli. Per i collegamenti di download e per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 2756872](http://support.microsoft.com/kb/2756872). Notare che il contenuto di questo aggiornamento non è correlato alla protezione.

<sup>[3]</sup>Gli aggiornamenti per la protezione di Windows RT sono forniti solo tramite [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).

**Nota** **per MS12-075**

<sup>[1]</sup>L'aggiornamento è disponibile solo tramite [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).

#### Applicazioni e software Microsoft Office

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
Applicazioni e componenti Microsoft Office
</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-076**](http://go.microsoft.com/fwlink/?linkid=260964)
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
Microsoft Office 2003 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2003 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=5bb12b2b-a8e2-4324-afee-e4d26dbc658f)  
(KB2687481)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 2
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2007 Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=e12aafe1-4445-4047-ad05-3db151a6fa4e)<sup>[1]</sup>
(KB2687307)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2007 Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=e12aafe1-4445-4047-ad05-3db151a6fa4e)<sup>[1]</sup>
(KB2687307)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2010 Service Pack 1 (edizioni a 32 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=37a1074d-bf4f-4b96-b394-1edc581748d0)  
(KB2597126)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)
</td>
<td style="border:1px solid black;">
[Microsoft Excel 2010 Service Pack 1 (edizioni a 64 bit)](http://www.microsoft.com/downloads/details.aspx?familyid=5db02eae-966e-41a9-8b64-ddda5f8b2e2a)  
(KB2597126)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Microsoft Office per Mac
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-076**](http://go.microsoft.com/fwlink/?linkid=260964)
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
Microsoft Office 2008 per Mac
</td>
<td style="border:1px solid black;">
[Microsoft Office 2008 per Mac](http://www.microsoft.com/downloads/details.aspx?familyid=d3d801a2-d57f-4b4c-970a-c296bc716521)  
(KB2764048)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office per Mac 2011
</td>
<td style="border:1px solid black;">
[Microsoft Office per Mac 2011](http://www.microsoft.com/downloads/details.aspx?familyid=0f4e073f-4fec-440d-a9bf-1e01ee9e92ad)  
(KB2764047)  
(Importante)
</td>
</tr>
<tr>
<th colspan="2">
Altro software Microsoft Office
</th>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
**Identificatore del bollettino**
</td>
<td style="border:1px solid black;">
[**MS12-076**](http://go.microsoft.com/fwlink/?linkid=260964)
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
Microsoft Excel Viewer
</td>
<td style="border:1px solid black;">
[Microsoft Excel Viewer](http://www.microsoft.com/downloads/details.aspx?familyid=a0917aeb-1e94-4142-bc20-5f1998ac249c)<sup>[2]</sup>
(KB2687313)  
(Importante)
</td>
</tr>
<tr>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 2
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office Service Pack 2](http://www.microsoft.com/downloads/details.aspx?familyid=79686714-9418-4516-81c3-555fe1ea9e84)  
(KB2687311)  
(Importante)
</td>
</tr>
<tr class="alternateRow">
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3
</td>
<td style="border:1px solid black;">
[Pacchetto di compatibilità Microsoft Office Service Pack 3](http://www.microsoft.com/downloads/details.aspx?familyid=79686714-9418-4516-81c3-555fe1ea9e84)  
(KB2687311)  
(Importante)
</td>
</tr>
</table>
 
**Noteper MS12-076**

<sup>[1]</sup>Per Microsoft Excel 2007, oltre al pacchetto di aggiornamento per la protezione KB2687307, i clienti devono installare anche l'aggiornamento per la protezione per il pacchetto di compatibilità Microsoft Office (KB2687311) per essere protetti dalle vulnerabilità descritte in questo bollettino.

<sup>[2]</sup>Microsoft Excel Viewer deve essere aggiornato a un livello di Service Pack supportato (Excel Viewer 2007 Service Pack 2 o Excel Viewer 2007 Service Pack 3) prima di installare questo aggiornamento. Per informazioni sui visualizzatori di Office supportati, vedere [l'articolo della Microsoft Knowledge Base 979860](http://support.microsoft.com/kb/979860).

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span></span>
**Security Central**

Gestione del software e degli aggiornamenti per la protezione necessari per la distribuzione su server, desktop e computer portatili dell'organizzazione. Per ulteriori informazioni, vedere il sito Web [TechNet Update Management Center](http://technet.microsoft.com/it-it/updatemanagement/default.aspx). [TechNet Security TechCenter](http://technet.microsoft.com/it-it/security/default.aspx) fornisce ulteriori informazioni sulla protezione dei prodotti Microsoft. I clienti possono visitare [Microsoft Safety &amp; Security Center](http://www.microsoft.com/italy/athome/security/default.mspx), dove queste informazioni sono disponibili anche facendo clic su "Aggiornamenti per la protezione".

Gli aggiornamenti per la protezione sono disponibili da [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it) e [Windows Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it). Gli aggiornamenti per la protezione sono anche disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".

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

#### Strumento di rimozione software dannoso di Microsoft Windows

Microsoft ha rilasciato una versione aggiornata dello strumento di rimozione del software dannoso su Windows Update, Microsoft Update, i Windows Server Update Services nell'Area download.

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

-   Jose A. Vazquez of spa-s3c.blogspot.com, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato due problemi descritti nel bollettino MS12-071
-   [Omair](http://krash.in/) per aver segnalato un problema descritto nel bollettino MS12-071
-   Cheng-da Tsai (Orange), Sung-ting Tsai e Ming-chieh Pan (Nanika) di [Trend Micro](http://www.trendmicro.com) per aver segnalato un problema descritto nel bollettino MS12-071
-   Tal Zeltzer, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato due problemi descritti nel bollettino MS12-072
-   Justin Royce di ProDX per aver segnalato un problema descritto nel bollettino MS12-073
-   James Forshaw di Context Information Security per aver segnalato quattro problemi descritti nel bollettino MS12-074
-   [Mateusz “j00ru" Jurczyk](http://j00ru.vexillium.org/) di [Google Inc.](http://www.google.com) per aver segnalato un problema descritto nel bollettino MS12-075
-   Eetu Luodemaa e Joni Vähämäki di [Documill](http://www.documill.com) per aver segnalato un problema descritto nel bollettino MS12-075
-   Sean Larsson, che collabora con [iDefense VCP](http://labs.idefense.com), per aver segnalato un problema descritto nel bollettino MS12-076
-   Un ricercatore anonimo, che collabora con [iDefense VCP](http://labs.idefense.com), per aver segnalato un problema descritto nel bollettino MS12-076
-   Un ricercatore anonimo, che collabora con [iDefense VCP](http://labs.idefense.com), per aver segnalato un problema descritto nel bollettino MS12-076
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP TippingPoint](http://www.hpenterprisesecurity.com/products/hp-tippingpoint-network-security/), per aver segnalato un problema descritto nel bollettino MS12-076

#### Supporto

-   I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).
-   Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617.aspx)
-   Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)
-   Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

#### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

#### Versioni

-   V1.0 (13 novembre 2012): Pubblicazione del riepilogo dei bollettini.
-   V1.1 (13 novembre 2012): Per MS12-075, sono stati corretti il titolo CVE e la valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service nell'**Exploitability Index** per CVE-2012-2897.
-   V 2.0 (14 novembre 2012): Per MS12-073, questo riepilogo dei bollettini è stato rivisto per specificare che l'aggiornamento KB2716513 su Windows Vista e Windows Server 2008 è ora disponibile attraverso tutti i canali di distribuzione, inclusi Windows Update e Microsoft Update. Vedere il bollettino MS12-073 per ulteriori dettagli.

*Built at 2014-04-18T01:50:00Z-07:00*
