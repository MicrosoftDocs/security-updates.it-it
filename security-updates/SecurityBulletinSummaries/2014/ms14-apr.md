---
TOCTitle: 'MS14-APR'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza - Aprile 2014'
ms:assetid: 'ms14-apr'
ms:contentKeyID: 62171143
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms14-apr(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Riepilogo dei bollettini Microsoft sulla sicurezza - Aprile 2014
================================================================

Data di pubblicazione: 8 aprile 2014

**Versione:** 1.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati ad aprile 2014.

Con il rilascio dei bollettini sulla sicurezza di aprile 2014, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 3 aprile 2014. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 9 aprile 2014 alle 11:00 ora del Pacifico (USA e Canada). [Registrazione immediata per i Webcast dei bollettini sulla sicurezza di aprile](https://msevents.microsoft.com/cui/eventdetail.aspx?eventid=1032572978&culture=en-us).

Microsoft fornisce anche informazioni per aiutare i clienti a definire le priorità degli aggiornamenti mensili rispetto agli aggiornamenti non correlati alla protezione pubblicati lo stesso giorno degli aggiornamenti mensili. Vedere la sezione **Altre informazioni**.

Riepiloghi
----------

<span id="sectionToggle0"></span>
La seguente tabella riassume i bollettini sulla sicurezza di questo mese in ordine di gravità.

Per ulteriori informazioni sul software interessato, vedere la sezione successiva, **Software interessato**.

 
<table style="border:1px solid black;">
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>ID bollettino</strong></td>
<td style="border:1px solid black;"><strong>Titolo del bollettino e riepilogo</strong></td>
<td style="border:1px solid black;"><strong>Livello di gravità massimo e impatto della vulnerabilità</strong></td>
<td style="border:1px solid black;"><strong>Necessità di riavvio</strong></td>
<td style="border:1px solid black;"><strong>Software interessato</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393531">MS14-017</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Word e nelle applicazioni Web di Office possono consentire l'esecuzione di codice in modalità remota (2949660)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e due vulnerabilità segnalate privatamente di Microsoft Office. La più grave di queste vulnerabilità può consentire l'esecuzione di codice in modalità remota se un file appositamente predisposto è aperto o visualizzato in anteprima in una versione interessata del software Microsoft Office. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, i clienti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office,<br />
Microsoft Office Services,<br />
Microsoft Office Web Apps</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393743">MS14-018</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2950467)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve sei vulnerabilità di Internet Explorer segnalate privatamente. Queste vulnerabilità possono consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta con Internet Explorer. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, gli utenti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392069">MS14-019</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità legata al componente di gestione dei file in Windows può consentire l'esecuzione di codice in modalità remota (2922229)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente in Microsoft Windows. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente esegue file .bat e .cmd appositamente predisposti da un percorso di rete attendibile o semi-attendibile. Un utente malintenzionato non può in alcun modo obbligare gli utenti a visitare il percorso di rete o a eseguire i file appositamente predisposti. L'utente malintenzionato dovrebbe convincere gli utenti a intraprendere tale azione. Ad esempio, un utente malintenzionato potrebbe indurre gli utenti a fare clic su un collegamento che li indirizzi al percorso dei file appositamente predisposti e successivamente ad eseguirli.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393603">MS14-020</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in Microsoft Publisher può consentire l'esecuzione di codice in modalità remota (2950145)<br />
</strong><br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Office che è stata segnalata privatamente. La vulnerabilità può consentire l'esecuzione di codice in modalità remota se un utente apre un file appositamente predisposto con una versione interessata di Microsoft Publisher. Sfruttando tale vulnerabilità, un utente malintenzionato potrebbe acquisire gli stessi diritti utente dell'utente corrente. Pertanto, i clienti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Office</td>
</tr>
</tbody>
</table>
  
Exploitability Index  
--------------------
  
<span id="sectionToggle1"></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
Come utilizzare questa tabella
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259).
  
Nelle colone seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.
  
<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<tbody>
<tr class="odd">
<td style="border:1px solid black;"><strong>ID bollettino</strong></td>
<td style="border:1px solid black;"><strong>Titolo della vulnerabilità</strong></td>
<td style="border:1px solid black;"><strong>ID CVE</strong></td>
<td style="border:1px solid black;"><strong>Valutazione dell'Exploitability per la versione più recente del software</strong></td>
<td style="border:1px solid black;"><strong>Valutazione dell'Exploitability per la versione meno recente del software</strong></td>
<td style="border:1px solid black;"><strong>Valutazione dell'Exploitability relativa ad un attacco di tipo Denial of Service</strong></td>
<td style="border:1px solid black;"><strong>Note fondamentali</strong></td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393531">MS14-017</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al programma di conversione del formato file di Microsoft Office</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-1757">CVE-2014-1757</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">3</a> - Scarsa probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393531">MS14-017</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'overflow dello stack in Microsoft Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-1758">CVE-2014-1758</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393531">MS14-017</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria dei dati RTF in Word</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-1761">CVE-2014-1761</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.<br />
<br />
Microsoft è a conoscenza di attacchi mirati limitati che tentano di sfruttare questa vulnerabilità.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393743">MS14-018</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0325">CVE-2014-0325</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393743">MS14-018</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-1751">CVE-2014-1751</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393743">MS14-018</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-1752">CVE-2014-1752</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393743">MS14-018</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-1753">CVE-2014-1753</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393743">MS14-018</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-1755">CVE-2014-1755</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393743">MS14-018</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-1760">CVE-2014-1760</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=392069">MS14-019</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla gestione dei file in Windows</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-0315">CVE-2014-0315</a></td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=393603">MS14-020</a></td>
<td style="border:1px solid black;">Vulnerabilità legata alla risoluzione del riferimento di un puntatore arbitrario</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-1759">CVE-2014-1759</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;"><a href="http://technet.microsoft.com/security/cc998259">1</a> - Alta probabilità di sfruttamento della vulnerabilità</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
</tbody>
</table>
  
Software interessato  
--------------------
  
<span id="sectionToggle2"></span>
Le seguenti tabelle elencano i bollettini in base alla categoria del software e alla gravità del coinvolgimento.
  
**Come utilizzare queste tabelle**
  
Queste tabelle sono uno strumento per individuare gli aggiornamenti per la protezione che è necessario installare. Esaminare tutti i programmi e i componenti elencati per verificare se sono disponibili aggiornamenti per la protezione per la propria configurazione. Per ogni programma o componente elencato è riportato anche il livello di gravità dell'aggiornamento software.
  
**Nota** Può essere necessario installare più aggiornamenti per la protezione per ogni singola vulnerabilità. Per verificare quali aggiornamenti è necessario applicare, in base ai programmi o componenti installati nel sistema, esaminare attentamente la colonna relativa a ogni bollettino.
  
**Sistema operativo Windows e suoi componenti**

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="3">
**Windows XP**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-018**](http://go.microsoft.com/fwlink/?linkid=393743)

</td>
<td style="border:1px solid black;">
[**MS14-019**](http://go.microsoft.com/fwlink/?linkid=392069)

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
<tr>
<td style="border:1px solid black;">
Windows XP Service Pack 3

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2936068)  
(Critico)  
Internet Explorer 7   
(2936068)  
(Critico)  
Internet Explorer 8   
(2936068)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows XP Service Pack 3  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2936068)  
(Critico)  
Internet Explorer 7   
(2936068)  
(Critico)  
Internet Explorer 8   
(2936068)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows XP Professional x64 Edition Service Pack 2  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Windows Server 2003**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-018**](http://go.microsoft.com/fwlink/?linkid=393743)

</td>
<td style="border:1px solid black;">
[**MS14-019**](http://go.microsoft.com/fwlink/?linkid=392069)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2936068)  
(Moderato)  
Internet Explorer 7  
(2936068)  
(Moderato)  
Internet Explorer 8  
(2936068)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2936068)  
(Moderato)  
Internet Explorer 7  
(2936068)  
(Moderato)  
Internet Explorer 8  
(2936068)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium

</td>
<td style="border:1px solid black;">
Internet Explorer 6   
(2936068)  
(Moderato)  
Internet Explorer 7  
(2936068)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2003 con SP2 per sistemi Itanium  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Windows Vista**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-018**](http://go.microsoft.com/fwlink/?linkid=393743)

</td>
<td style="border:1px solid black;">
[**MS14-019**](http://go.microsoft.com/fwlink/?linkid=392069)

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
<tr>
<td style="border:1px solid black;">
Windows Vista Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2936068)  
(Critico)  
Internet Explorer 8  
(2936068)  
(Critico)  
Internet Explorer 9   
(2936068)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista Service Pack 2  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2936068)  
(Critico)  
Internet Explorer 8  
(2936068)  
(Critico)  
Internet Explorer 9   
(2936068)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Windows Server 2008**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-018**](http://go.microsoft.com/fwlink/?linkid=393743)

</td>
<td style="border:1px solid black;">
[**MS14-019**](http://go.microsoft.com/fwlink/?linkid=392069)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2936068)  
(Moderato)  
Internet Explorer 8  
(2936068)  
(Moderato)  
Internet Explorer 9   
(2936068)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2936068)  
(Moderato)  
Internet Explorer 8  
(2936068)  
(Moderato)  
Internet Explorer 9   
(2936068)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2936068)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Windows 7**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-018**](http://go.microsoft.com/fwlink/?linkid=393743)

</td>
<td style="border:1px solid black;">
[**MS14-019**](http://go.microsoft.com/fwlink/?linkid=392069)

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
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2936068)  
(Critico)  
Internet Explorer 9   
(2936068)  
(Critico)  
Internet Explorer 11   
(2936068)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2936068)  
(Critico)  
Internet Explorer 9   
(2936068)  
(Critico)  
Internet Explorer 11   
(2936068)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Windows Server 2008 R2**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-018**](http://go.microsoft.com/fwlink/?linkid=393743)

</td>
<td style="border:1px solid black;">
[**MS14-019**](http://go.microsoft.com/fwlink/?linkid=392069)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2936068)  
(Moderato)  
Internet Explorer 9   
(2936068)  
(Moderato)  
Internet Explorer 11   
(2936068)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2936068)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Windows 8 e Windows 8.1**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-018**](http://go.microsoft.com/fwlink/?linkid=393743)

</td>
<td style="border:1px solid black;">
[**MS14-019**](http://go.microsoft.com/fwlink/?linkid=392069)

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
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi x64

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2936068)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2936068)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Windows Server 2012 e Windows Server 2012 R2**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-018**](http://go.microsoft.com/fwlink/?linkid=393743)

</td>
<td style="border:1px solid black;">
[**MS14-019**](http://go.microsoft.com/fwlink/?linkid=392069)

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
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

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
Windows Server 2012  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 R2

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2936068)  
(Moderato)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Windows RT e Windows RT 8.1**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-018**](http://go.microsoft.com/fwlink/?linkid=393743)

</td>
<td style="border:1px solid black;">
[**MS14-019**](http://go.microsoft.com/fwlink/?linkid=392069)

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
<tr>
<td style="border:1px solid black;">
Windows RT

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows RT  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows RT 8.1

</td>
<td style="border:1px solid black;">
Internet Explorer 11   
(2936068)  
(Critico)

</td>
<td style="border:1px solid black;">
Windows RT 8.1  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Opzione di installazione Server Core**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-018**](http://go.microsoft.com/fwlink/?linkid=393743)

</td>
<td style="border:1px solid black;">
[**MS14-019**](http://go.microsoft.com/fwlink/?linkid=392069)

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
Windows Server 2008 per sistemi a 32 bit Service Pack 2 (installazione Server Core)  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2 (installazione Server Core)  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1 (installazione Server Core)  
(2922229)  
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
Windows Server 2012 (installazione Server Core)  
(2922229)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 R2 (installazione Server Core)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2 (installazione Server Core)  
(2922229)  
(Importante)

</td>
</tr>
</table>
 
 

**Applicazioni e software Microsoft Office**

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="3">
**Microsoft Office 2003**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-017**](http://go.microsoft.com/fwlink/?linkid=393531)

</td>
<td style="border:1px solid black;">
[**MS14-020**](http://go.microsoft.com/fwlink/?linkid=393603)

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
<tr>
<td style="border:1px solid black;">
Microsoft Office 2003 Service Pack 3

</td>
<td style="border:1px solid black;">
Microsoft Word 2003 Service Pack 3  
(2878303)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft Publisher 2003 Service Pack 3  
(2878299)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Microsoft Office 2007**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-017**](http://go.microsoft.com/fwlink/?linkid=393531)

</td>
<td style="border:1px solid black;">
[**MS14-020**](http://go.microsoft.com/fwlink/?linkid=393603)

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
<tr>
<td style="border:1px solid black;">
Microsoft Office 2007 Service Pack 3

</td>
<td style="border:1px solid black;">
Microsoft Word 2007 Service Pack 3  
(2878237)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft Publisher 2007 Service Pack 3  
(2817565)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Microsoft Office 2010**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-017**](http://go.microsoft.com/fwlink/?linkid=393531)

</td>
<td style="border:1px solid black;">
[**MS14-020**](http://go.microsoft.com/fwlink/?linkid=393603)

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
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 1 (edizioni a 32 bit)  
(2863926)  
(Critico)  
Microsoft Word 2010 Service Pack 1 (edizioni a 32 bit)  
(2863919)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 2 (edizioni a 32 bit)  
(2863926)  
(Critico)  
Microsoft Word 2010 Service Pack 2 (edizioni a 32 bit)  
(2863919)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 1 (edizioni a 64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 1 (edizioni a 64 bit)  
(2863926)  
(Critico)  
Microsoft Word 2010 Service Pack 1 (edizioni a 64 bit)  
(2863919)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2010 Service Pack 2 (edizioni a 64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Word 2010 Service Pack 2 (edizioni a 64 bit)  
(2863926)  
(Critico)  
Microsoft Word 2010 Service Pack 2 (edizioni a 64 bit)  
(2863919)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Microsoft Office 2013 e Microsoft Office 2013 RT**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-017**](http://go.microsoft.com/fwlink/?linkid=393531)

</td>
<td style="border:1px solid black;">
[**MS14-020**](http://go.microsoft.com/fwlink/?linkid=393603)

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
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Word 2013 (edizioni a 32 bit)  
(2863910)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 Service Pack 1 (edizioni a 32 bit)

</td>
<td style="border:1px solid black;">
Microsoft Word 2013 Service Pack 1 (edizioni a 32 bit)  
(2863910)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Office 2013 (edizioni a 64 bit)  
(2863910)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 Service Pack 1 (edizioni a 64 bit)

</td>
<td style="border:1px solid black;">
Microsoft Word 2013 Service Pack 1 (edizioni a 64 bit)  
(2863910)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 RT

</td>
<td style="border:1px solid black;">
Microsoft Word 2013 RT  
(2863910)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office 2013 RT Service Pack 1

</td>
<td style="border:1px solid black;">
Microsoft Word 2013 RT Service Pack 1  
(2863910)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Microsoft Office per Mac**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-017**](http://go.microsoft.com/fwlink/?linkid=393531)

</td>
<td style="border:1px solid black;">
[**MS14-020**](http://go.microsoft.com/fwlink/?linkid=393603)

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
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office per Mac 2011

</td>
<td style="border:1px solid black;">
Microsoft Office per Mac 2011  
(2939132)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="3">
**Altro software Office**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-017**](http://go.microsoft.com/fwlink/?linkid=393531)

</td>
<td style="border:1px solid black;">
[**MS14-020**](http://go.microsoft.com/fwlink/?linkid=393603)

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
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Word Viewer

</td>
<td style="border:1px solid black;">
Microsoft Word Viewer  
(2878304)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3

</td>
<td style="border:1px solid black;">
Pacchetto di compatibilità Microsoft Office Service Pack 3  
(2878236)  
(Critico)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
</table>
 
**Nota per MS14-017**

Questo bollettino riguarda più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

 

**Microsoft Office Services e Web Apps**

 
<table style="border:1px solid black;">
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft SharePoint Server 2010**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-017**](http://go.microsoft.com/fwlink/?linkid=393531)

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
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 1

</td>
<td style="border:1px solid black;">
Word Automation Services  
(2878220)  
(Critico)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2010 Service Pack 2

</td>
<td style="border:1px solid black;">
Word Automation Services  
(2878220)  
(Critico)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft SharePoint Server 2013**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-017**](http://go.microsoft.com/fwlink/?linkid=393531)

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
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2013

</td>
<td style="border:1px solid black;">
Word Automation Services  
(2863907)  
(Critico)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft SharePoint Server 2013 Service Pack 1

</td>
<td style="border:1px solid black;">
Word Automation Services  
(2863907)  
(Critico)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Office Web Apps 2010**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-017**](http://go.microsoft.com/fwlink/?linkid=393531)

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
<tr>
<td style="border:1px solid black;">
Microsoft Office Web Apps 2010 Service Pack 1

</td>
<td style="border:1px solid black;">
Microsoft Web Applications 2010 Service Pack 1  
(2878221)  
(Critico)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Web Apps 2010 Service Pack 2

</td>
<td style="border:1px solid black;">
Microsoft Web Applications 2010 Service Pack 2  
(2878221)  
(Critico)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="2">
**Microsoft Office Web Apps 2013**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-017**](http://go.microsoft.com/fwlink/?linkid=393531)

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
<tr>
<td style="border:1px solid black;">
Microsoft Office Web Apps 2013

</td>
<td style="border:1px solid black;">
Microsoft Office Web Apps Server 2013  
(2878219)  
(Critico)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Office Web Apps 2013 Service Pack 1

</td>
<td style="border:1px solid black;">
Microsoft Office Web Apps Server 2013 Service Pack 1  
(2878219)  
(Critico)

</td>
</tr>
</table>
 
**Nota per MS14-017**

Questo bollettino riguarda più di una categoria di software. Vedere le altre tabelle in questa sezione per il software aggiuntivo interessato.

 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span id="sectionToggle3"></span>
Sono disponibili diverse risorse per aiutare gli amministratori a distribuire gli aggiornamenti per la protezione.

-   Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione.
-   Windows Server Update Services (WSUS), Systems Management Server (SMS) e System Center Configuration Manager (SCCM) aiutano gli amministratori a distribuire gli aggiornamenti per la protezione.
-   I componenti del programma Update Compatibility Evaluator compresi nell'Application Compatibility Toolkit sono utili per semplificare la verifica e la convalida degli aggiornamenti di Windows per le applicazioni installate.

Per informazioni su questi e altri strumenti disponibili, vedere [Strumenti per la sicurezza](http://technet.microsoft.com/security/cc297183). 

Ringraziamenti
--------------

<span id="sectionToggle4"></span>
Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

**MS14-017**

-   Will Dormann di [CERT/CC](http://www.cert.org/) per aver segnalato la vulnerabilità legata al programma di conversione del formato file di Microsoft Office (CVE-2014-1757)
-   Yuhong Bao per aver segnalato la vulnerabilità legata all'overflow dello stack in Microsoft Word (CVE-2014-1758)
-   Drew Hintz, Shane Huntley e Matty Pellegrino del [Google Security Team](https://www.google.it/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria dei dati RTF in Word (CVE-2014-1761)

**MS14-018**

-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-0325)
-   Dr. Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-1751)
-   Dr. Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-1752)
-   Yuki Chen di [Trend Micro](http://www.trendmicro.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-1753)
-   096dc2a463051c0ac4b7caaf233f7eff e Amol Naik, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-1755)
-   Abdul-Aziz Hariri di [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-1760)

**Per MS14-019**

-   Stefan Kanthak per aver collaborato con noi allo studio della vulnerabilità legata alla gestione dei file in Windows (CVE-2014-0315)

**Per MS14-020**

-   Un ricercatore anonimo, che collabora con [VeriSign iDefense Labs](http://labs.idefense.com/), per aver segnalato la vulnerabilità legata alla risoluzione del riferimento di un puntatore arbitrario (CVE-2014-1759)

Altre informazioni
------------------

<span id="sectionToggle5"></span>
### Strumento di rimozione software dannoso di Microsoft Windows

Per il rilascio dei bollettini che avviene il secondo martedì di ogni mese, Microsoft ha rilasciato una versione aggiornata dello Strumento di rimozione software dannoso di Microsoft Windows in Windows Update, Microsoft Update, Windows Server Update Services e nell'Area download. Non è disponibile alcuna versione dello Strumento di rimozione software dannoso di Microsoft Windows per i rilasci di bollettini sulla sicurezza straordinari.

### Aggiornamenti non correlati alla protezione priorità su MU, WU e WSUS

Per informazioni sulle versioni non correlate alla protezione in Windows Update e Microsoft Update, vedere:

-   [Articolo della Microsoft Knowledge Base 894199](https://support.microsoft.com/kb/894199): Descrizione delle modifiche nei contenuti relative a Software Update Services e Windows Server Update Services. Include tutti i contenuti Windows.
-   [Aggiornamenti precedenti per Windows Server Update Services](http://technet.microsoft.com/wsus/bb456965). Visualizza tutti gli aggiornamenti nuovi, rivisti e rilasciati nuovamente per i prodotti Microsoft diversi da Microsoft Windows.

### Microsoft Active Protections Program (MAPP)

Per migliorare il livello di protezione offerto ai clienti, Microsoft fornisce ai principali fornitori di software di protezione i dati relativi alle vulnerabilità in anticipo rispetto alla pubblicazione mensile dell'aggiornamento per la protezione. I fornitori di software di protezione possono servirsi di tali dati per fornire ai clienti delle protezioni aggiornate tramite software o dispositivi di protezione, quali antivirus, sistemi di rilevamento delle intrusioni di rete o sistemi di prevenzione delle intrusioni basati su host. Per verificare se tali protezioni attive sono state rese disponibili dai fornitori di software di protezione, visitare i siti Web relativi alle protezioni attive pubblicati dai partner del programma, che sono elencati in [Microsoft Active Protections Program (MAPP) Partners](http://go.microsoft.com/fwlink/?linkid=215201).

### Strategie di protezione e community

**Strategie per la gestione degli aggiornamenti**

Per ulteriori informazioni sulle procedure consigliate da Microsoft per l'applicazione degli aggiornamenti per la protezione, consultare le [Informazioni sulla protezione per la gestione degli aggiornamenti](http://technet.microsoft.com/library/bb466251.aspx).

**Download di altri aggiornamenti per la protezione**

Sono disponibili aggiornamenti per altri problemi di protezione nei seguenti siti:

-   Gli aggiornamenti per la protezione sono disponibili nell'[Area download Microsoft](http://www.microsoft.com/downloads/results.aspx?displaylang=it&freetext=security%20update). ed è possibile individuarli in modo semplice eseguendo una ricerca con la parola chiave "aggiornamento per la protezione".
-   Gli aggiornamenti per i sistemi consumer sono disponibili in [Microsoft Update](http://www.update.microsoft.com/microsoftupdate/v6/vistadefault.aspx?ln=it-it).
-   Gli aggiornamenti per la protezione di questo mese presenti in Windows Update sono disponibili in Immagine CD ISO aggiornamenti della protezione e ad alta priorità nell'Area download. Per ulteriori informazioni, vedere l'[articolo della Microsoft Knowledge Base 913086](https://support.microsoft.com/kb/913086).

**IT Pro Security Community**

Imparare a migliorare la protezione e ottimizzare l'infrastruttura IT, collaborare con altri professionisti IT sugli argomenti di protezione in [IT Pro Security Community](http://technet.microsoft.com/security/cc136632.aspx).

### Supporto

I prodotti software elencati sono stati sottoposti a test per determinare quali versioni sono interessate dalla vulnerabilità. Le altre versioni sono al termine del ciclo di vita del supporto. Per informazioni sulla disponibilità del supporto per la versione del software in uso, visitare il [sito Web Ciclo di vita del supporto Microsoft](http://support.microsoft.com/common/international.aspx?rdpath=gp;%5Bln%5D;lifecycle).

Soluzioni per la protezione per i professionisti IT: [Risoluzione dei problemi e supporto per la protezione in TechNet](http://technet.microsoft.com/security/bb980617)

Guida alla protezione contro virus e malware del computer che esegue Windows: [Centro di supporto Virus a sicurezza](http://support.microsoft.com/contactus/cu_sc_virsec_master)

Supporto locale in base al proprio paese: [Supporto internazionale](http://support.microsoft.com/common/international.aspx)

### Dichiarazione di non responsabilità

Le informazioni disponibili nella Microsoft Knowledge Base sono fornite "come sono" senza garanzie di alcun tipo. Microsoft non rilascia alcuna garanzia, esplicita o implicita, inclusa la garanzia di commerciabilità e di idoneità per uno scopo specifico. Microsoft Corporation o i suoi fornitori non saranno, in alcun caso, responsabili per danni di qualsiasi tipo, inclusi i danni diretti, indiretti, incidentali, consequenziali, la perdita di profitti e i danni speciali, anche qualora Microsoft Corporation o i suoi fornitori siano stati informati della possibilità del verificarsi di tali danni. Alcuni stati non consentono l'esclusione o la limitazione di responsabilità per danni diretti o indiretti e, dunque, la sopracitata limitazione potrebbe non essere applicabile.

### Versioni

-   V1.0 (8 aprile 2014): Pubblicazione del riepilogo dei bollettini.

 

*Pagina generata 30-06-2014 14:26Z-07:00.*
