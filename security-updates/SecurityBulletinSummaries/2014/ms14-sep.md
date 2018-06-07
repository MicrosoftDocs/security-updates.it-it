---
TOCTitle: 'MS14-SET'
Title: 'Riepilogo dei bollettini Microsoft sulla sicurezza, settembre 2014'
ms:assetid: 'ms14-sep'
ms:contentKeyID: 62841232
ms:mtpsurl: 'https://technet.microsoft.com/it-IT/library/ms14-sep(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Riepilogo dei bollettini Microsoft sulla sicurezza, settembre 2014
==================================================================

Data di pubblicazione: 9 settembre 2014

**Versione:** 1.0

Questo riepilogo elenca i bollettini sulla sicurezza rilasciati a settembre 2014.

Con il rilascio dei bollettini sulla sicurezza di settembre 2014, questo riepilogo dei bollettini sostituisce la notifica anticipata relativa al rilascio di bollettini pubblicata originariamente in data 4 settembre 2014. Per ulteriori informazioni su questo servizio, vedere [Notifica anticipata relativa al rilascio di bollettini Microsoft sulla sicurezza](http://go.microsoft.com/fwlink/?linkid=217213).

Per informazioni su come ricevere automaticamente una notifica ogni volta che viene rilasciato un bollettino Microsoft sulla sicurezza, vedere il [servizio di notifica sulla sicurezza Microsoft](http://technet.microsoft.com/it-it/security/dd252948.aspx).

Microsoft mette a disposizione un Webcast per rispondere alle domande dei clienti su questi bollettini il 10 settembre 2014 alle 11:00 ora del Pacifico (USA e Canada). Per visualizzare il webcast mensile e per collegamenti a webcast aggiuntivi dei bollettini sulla sicurezza, vedere [Webcast dei bollettini Microsoft sulla sicurezza](http://technet.microsoft.com/security/dn756352).

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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;"><strong>Aggiornamento cumulativo per la protezione di Internet Explorer (2977629)<br />
<br />
</strong>Questo aggiornamento per la protezione risolve una vulnerabilità divulgata pubblicamente e trentasei vulnerabilità segnalate privatamente in Internet Explorer. La vulnerabilità con gli effetti più gravi sulla protezione può consentire l'esecuzione di codice in modalità remota se un utente visualizza una pagina Web appositamente predisposta in Internet Explorer. Sfruttando queste vulnerabilità, un utente malintenzionato può ottenere gli stessi diritti utente dell'utente corrente. Pertanto, i clienti con account configurati in modo da disporre solo di diritti limitati sono esposti all'attacco in misura inferiore rispetto a quelli che operano con privilegi di amministrazione.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Critico</a> <br />
Esecuzione di codice in modalità remota</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Internet Explorer</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=507670">MS14-053</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità in .NET Framework può consentire un attacco di tipo Denial of Service (2990931)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità segnalata privatamente di Microsoft .NET Framework. La vulnerabilità può consentire un attacco di tipo Denial of Service se un utente malintenzionato invia un numero limitato di richieste appositamente predisposte a un sito Web .NET interessato. Per impostazione predefinita, ASP.NET non viene installato quando Microsoft .NET Framework è installato su un'edizione supportata di Microsoft Windows. Per essere interessati da questa vulnerabilità, i clienti devono installare manualmente e attivare ASP.NET, registrandolo con IIS.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Denial of Service</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows,<br />
Microsoft .NET Framework</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=507672">MS14-054</a></td>
<td style="border:1px solid black;"><strong>Una vulnerabilità nell'Utilità di pianificazione di Windows può consentire l'acquisizione di privilegi più elevati (2988948)</strong><br />
<br />
Questo aggiornamento per la protezione risolve una vulnerabilità di Microsoft Windows che è stata segnalata privatamente. Tale vulnerabilità può consentire l'acquisizione di privilegi più elevati se un utente malintenzionato accede al sistema interessato ed esegue un'applicazione appositamente predisposta. Per sfruttare la vulnerabilità, è necessario disporre di credenziali di accesso valide ed essere in grado di accedere al sistema in locale. La vulnerabilità non può essere sfruttata in remoto o da utenti anonimi.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Acquisizione di privilegi più elevati</td>
<td style="border:1px solid black;">È necessario il riavvio</td>
<td style="border:1px solid black;">Microsoft Windows</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=507669">MS14-055</a></td>
<td style="border:1px solid black;"><strong>Alcune vulnerabilità in Microsoft Lync Server possono consentire un attacco di tipo Denial of Service (2990928)</strong><br />
<br />
Questo aggiornamento per la protezione risolve tre vulnerabilità segnalate privatamente in Microsoft Lync Server. La più grave di queste vulnerabilità può consentire un attacco di tipo Denial of Service se un utente malintenzionato invia una richiesta appositamente predisposta a un server Lync.</td>
<td style="border:1px solid black;"><a href="http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx">Importante</a> <br />
Denial of Service</td>
<td style="border:1px solid black;">Non è necessario riavviare il sistema</td>
<td style="border:1px solid black;">Microsoft Lync Server</td>
</tr>
</tbody>
</table>
  
 
  
Exploitability Index  
--------------------
  
<span id="sectionToggle1"></span>
La seguente tabella fornisce una valutazione di rischio per ciascuna delle vulnerabilità affrontate nei bollettini di questo mese. Le vulnerabilità vengono elencate in base ai codici identificativi dei bollettini e ai codici CVE. I bollettini includono solo le vulnerabilità che presentano un livello di gravità critico o importante.
  
Come utilizzare questa tabella
  
Utilizzare questa tabella per verificare le probabilità di esecuzione di codice e attacchi di tipo Denial of Service entro 30 giorni dalla pubblicazione del bollettino sulla sicurezza per ciascuno degli aggiornamenti per la protezione che è necessario installare. Si suggerisce di analizzare ciascuna delle voci riportate di seguito, confrontandole con la propria configurazione specifica, al fine di stabilire la corretta priorità di distribuzione degli aggiornamenti di questo mese. Per ulteriori informazioni sul significato dei livelli di gravità indicati e sul modo in cui vengono definiti, vedere [Microsoft Exploitability Index](http://technet.microsoft.com/security/cc998259).
  
Nelle colonne seguenti, "Versione più recente del software" fa riferimento alla versione più recente del software in questione e "Versioni meno recenti del software" fa riferimento a tutte le versioni precedenti supportate del software in questione, come elencato nelle tabelle "Software interessato" o "Software non interessato" nel bollettino.
  
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
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni sulle risorse in Internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2013-7331">CVE-2013-7331</a></td>
<td style="border:1px solid black;">0- Sfruttamento rilevato</td>
<td style="border:1px solid black;">0- Sfruttamento rilevato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Le informazioni sulla vulnerabilità sono state divulgate pubblicamente. Microsoft è a conoscenza di attacchi attivi limitati che tentano di sfruttare questa vulnerabilità.<br />
Questa vulnerabilità riguarda l'intercettazione di informazioni personali: l'utente malintenzionato può identificare la presenza di file sulle unità locali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-2799">CVE-2014-2799</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4059">CVE-2014-4059</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4065">CVE-2014-4065</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4079">CVE-2014-4079</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4080">CVE-2014-4080</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4081">CVE-2014-4081</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4082">CVE-2014-4082</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4083">CVE-2014-4083</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4084">CVE-2014-4084</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4085">CVE-2014-4085</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4086">CVE-2014-4086</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4087">CVE-2014-4087</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4088">CVE-2014-4088</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4089">CVE-2014-4089</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4090">CVE-2014-4090</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4091">CVE-2014-4091</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4092">CVE-2014-4092</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4093">CVE-2014-4093</a></td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4094">CVE-2014-4094</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4095">CVE-2014-4095</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4096">CVE-2014-4096</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4097">CVE-2014-4097</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4098">CVE-2014-4098</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4099">CVE-2014-4099</a></td>
<td style="border:1px solid black;">3- Sfruttamento improbabile</td>
<td style="border:1px solid black;">3- Sfruttamento improbabile</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">Questa vulnerabilità legata al danneggiamento della memoria può consentire un attacco di tipo Denial of Service.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4100">CVE-2014-4100</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4101">CVE-2014-4101</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4102">CVE-2014-4102</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4103">CVE-2014-4103</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4104">CVE-2014-4104</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4105">CVE-2014-4105</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4106">CVE-2014-4106</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4107">CVE-2014-4107</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4108">CVE-2014-4108</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4109">CVE-2014-4109</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4110">CVE-2014-4110</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=509961">MS14-052</a></td>
<td style="border:1px solid black;">Vulnerabilità legata al danneggiamento della memoria in internet Explorer</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4111">CVE-2014-4111</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=507670">MS14-053</a></td>
<td style="border:1px solid black;">Vulnerabilità legata ad attacchi di tipo Denial of Service in .NET Framework</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4072">CVE-2014-4072</a></td>
<td style="border:1px solid black;">3- Sfruttamento improbabile</td>
<td style="border:1px solid black;">3- Sfruttamento improbabile</td>
<td style="border:1px solid black;">Permanente</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=507672">MS14-054</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'Utilità di pianificazione</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4074">CVE-2014-4074</a></td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">1 - Sfruttamento più probabile</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">(Nessuna)</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=507669">MS14-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata ad attacchi di tipo Denial of Service in Lync</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4068">CVE-2014-4068</a></td>
<td style="border:1px solid black;">3- Sfruttamento improbabile</td>
<td style="border:1px solid black;">3- Sfruttamento improbabile</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.</td>
</tr>
<tr class="odd">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=507669">MS14-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata all'intercettazione di informazioni personali in Lync XSS</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4070">CVE-2014-4070</a></td>
<td style="border:1px solid black;">3- Sfruttamento improbabile</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Non applicabile</td>
<td style="border:1px solid black;">Questa vulnerabilità riguarda l'intercettazione di informazioni personali.</td>
</tr>
<tr class="even">
<td style="border:1px solid black;"><a href="http://go.microsoft.com/fwlink/?linkid=507669">MS14-055</a></td>
<td style="border:1px solid black;">Vulnerabilità legata ad attacchi di tipo Denial of Service in Lync</td>
<td style="border:1px solid black;"><a href="http://www.cve.mitre.org/cgi-bin/cvename.cgi?name=cve-2014-4071">CVE-2014-4071</a></td>
<td style="border:1px solid black;">3- Sfruttamento improbabile</td>
<td style="border:1px solid black;">Non interessato</td>
<td style="border:1px solid black;">Temporaneo</td>
<td style="border:1px solid black;">Si tratta di una vulnerabilità ad attacchi di tipo Denial of Service.</td>
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
<td style="border:1px solid black;" colspan="4">
**Windows Server 2003**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-052**](http://go.microsoft.com/fwlink/?linkid=509961)

</td>
<td style="border:1px solid black;">
[**MS14-053**](http://go.microsoft.com/fwlink/?linkid=507670)

</td>
<td style="border:1px solid black;">
[**MS14-054**](http://go.microsoft.com/fwlink/?linkid=507672)

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
<td style="border:1px solid black;">
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2977629)  
(Moderato)  
Internet Explorer 7  
(2977629)  
(Moderato)  
Internet Explorer 8  
(2977629)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 1.1 Service Pack 1  
(2972207)  
(Importante)  
Microsoft .NET Framework 2.0 Service Pack 2  
(2972214)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2973115)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2003 x64 Edition Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 6  
(2977629)  
(Moderato)  
Internet Explorer 7  
(2977629)  
(Moderato)  
Internet Explorer 8  
(2977629)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2972214)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2973115)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)

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
Internet Explorer 6  
(2977629)  
(Moderato)  
Internet Explorer 7  
(2977629)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2972214)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Windows Vista**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-052**](http://go.microsoft.com/fwlink/?linkid=509961)

</td>
<td style="border:1px solid black;">
[**MS14-053**](http://go.microsoft.com/fwlink/?linkid=507670)

</td>
<td style="border:1px solid black;">
[**MS14-054**](http://go.microsoft.com/fwlink/?linkid=507672)

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
<td style="border:1px solid black;">
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2977629)  
(Critico)  
Internet Explorer 8  
(2977629)  
(Critico)  
Internet Explorer 9  
(2977629)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2974268)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2974269)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972216)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Vista x64 Edition Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2977629)  
(Critico)  
Internet Explorer 8  
(2977629)  
(Critico)  
Internet Explorer 9  
(2977629)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2974268)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2974269)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972216)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Windows Server 2008**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-052**](http://go.microsoft.com/fwlink/?linkid=509961)

</td>
<td style="border:1px solid black;">
[**MS14-053**](http://go.microsoft.com/fwlink/?linkid=507670)

</td>
<td style="border:1px solid black;">
[**MS14-054**](http://go.microsoft.com/fwlink/?linkid=507672)

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
<td style="border:1px solid black;">
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi a 32 bit Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2977629)  
(Moderato)  
Internet Explorer 8  
(2977629)  
(Moderato)  
Internet Explorer 9  
(2977629)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2974268)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2974269)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972216)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi x64 Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2977629)  
(Moderato)  
Internet Explorer 8  
(2977629)  
(Moderato)  
Internet Explorer 9  
(2977629)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2974268)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2974269)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972216)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 per sistemi Itanium Service Pack 2

</td>
<td style="border:1px solid black;">
Internet Explorer 7  
(2977629)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 2.0 Service Pack 2  
(2974268)  
(Importante)  
Microsoft .NET Framework 3.0 Service Pack 2  
(2974269)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Windows 7**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-052**](http://go.microsoft.com/fwlink/?linkid=509961)

</td>
<td style="border:1px solid black;">
[**MS14-053**](http://go.microsoft.com/fwlink/?linkid=507670)

</td>
<td style="border:1px solid black;">
[**MS14-054**](http://go.microsoft.com/fwlink/?linkid=507672)

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
<td style="border:1px solid black;">
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi a 32 bit Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2977629)  
(Critico)  
Internet Explorer 9  
(2977629)  
(Critico)  
Internet Explorer 10  
(2977629)  
(Critico)  
Internet Explorer 11  
(2977629)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2972211)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2973112)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972216)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 7 per sistemi x64 Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2977629)  
(Critico)  
Internet Explorer 9  
(2977629)  
(Critico)  
Internet Explorer 10  
(2977629)  
(Critico)  
Internet Explorer 11  
(2977629)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2972211)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2973112)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972216)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Windows Server 2008 R2**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-052**](http://go.microsoft.com/fwlink/?linkid=509961)

</td>
<td style="border:1px solid black;">
[**MS14-053**](http://go.microsoft.com/fwlink/?linkid=507670)

</td>
<td style="border:1px solid black;">
[**MS14-054**](http://go.microsoft.com/fwlink/?linkid=507672)

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
<td style="border:1px solid black;">
**Nessuno**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi x64 Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2977629)  
(Moderato)  
Internet Explorer 9  
(2977629)  
(Moderato)  
Internet Explorer 10  
(2977629)  
(Moderato)  
Internet Explorer 11  
(2977629)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2972211)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2973112)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972216)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2008 R2 per sistemi Itanium Service Pack 1

</td>
<td style="border:1px solid black;">
Internet Explorer 8  
(2977629)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5.1  
(2972211)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2973112)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Windows 8 e Windows 8.1**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-052**](http://go.microsoft.com/fwlink/?linkid=509961)

</td>
<td style="border:1px solid black;">
[**MS14-053**](http://go.microsoft.com/fwlink/?linkid=507670)

</td>
<td style="border:1px solid black;">
[**MS14-054**](http://go.microsoft.com/fwlink/?linkid=507672)

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
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit

</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2977629)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2972212)  
(Importante)  
Microsoft .NET Framework 3.5  
(2973113)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2977766)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi a 32 bit  
(2988948)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8 per sistemi x64

</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2977629)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2972212)  
(Importante)  
Microsoft .NET Framework 3.5  
(2973113)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2977766)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows 8 per sistemi x64  
(2988948)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit

</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2977629)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2972213)  
(Importante)  
Microsoft .NET Framework 3.5  
(2973114)  
(Importante)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2977765)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi a 32 bit  
(2988948)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64

</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2977629)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2972213)  
(Importante)  
Microsoft .NET Framework 3.5  
(2973114)  
(Importante)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2977765)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows 8.1 per sistemi x64  
(2988948)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Windows Server 2012 e Windows Server 2012 R2**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-052**](http://go.microsoft.com/fwlink/?linkid=509961)

</td>
<td style="border:1px solid black;">
[**MS14-053**](http://go.microsoft.com/fwlink/?linkid=507670)

</td>
<td style="border:1px solid black;">
[**MS14-054**](http://go.microsoft.com/fwlink/?linkid=507672)

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
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012

</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2977629)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2972212)  
(Importante)  
Microsoft .NET Framework 3.5  
(2973113)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2977766)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012  
(2988948)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows Server 2012 R2

</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2977629)  
(Moderato)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 3.5  
(2972213)  
(Importante)  
Microsoft .NET Framework 3.5  
(2973114)  
(Importante)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2977765)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2  
(2988948)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Windows RT e Windows RT 8.1**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-052**](http://go.microsoft.com/fwlink/?linkid=509961)

</td>
<td style="border:1px solid black;">
[**MS14-053**](http://go.microsoft.com/fwlink/?linkid=507670)

</td>
<td style="border:1px solid black;">
[**MS14-054**](http://go.microsoft.com/fwlink/?linkid=507672)

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
<td style="border:1px solid black;">
[**Importante**](http://www.microsoft.com/italy/technet/security/bulletin/rating.mspx)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows RT

</td>
<td style="border:1px solid black;">
Internet Explorer 10  
(2977629)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2977766)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows RT  
(2988948)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Windows RT 8.1

</td>
<td style="border:1px solid black;">
Internet Explorer 11  
(2977629)  
(Critico)

</td>
<td style="border:1px solid black;">
Microsoft .NET Framework 4.5.1/4.5.2  
(2977765)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows RT 8.1  
(2988948)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;" colspan="4">
**Opzione di installazione Server Core**

</td>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-052**](http://go.microsoft.com/fwlink/?linkid=509961)

</td>
<td style="border:1px solid black;">
[**MS14-053**](http://go.microsoft.com/fwlink/?linkid=507670)

</td>
<td style="border:1px solid black;">
[**MS14-054**](http://go.microsoft.com/fwlink/?linkid=507672)

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
Non applicabile

</td>
<td style="border:1px solid black;">
Non applicabile

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
Non applicabile

</td>
<td style="border:1px solid black;">
Non applicabile

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
Microsoft .NET Framework 3.5.1  
(2972211)  
(Importante)  
Microsoft .NET Framework 3.5.1  
(2973112)  
(Importante)  
Microsoft .NET Framework 4  
(2972215)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2972216)  
(Importante)

</td>
<td style="border:1px solid black;">
Non applicabile

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
Microsoft .NET Framework 3.5  
(2972212)  
(Importante)  
Microsoft .NET Framework 3.5  
(2973113)  
(Importante)  
Microsoft .NET Framework 4.5/4.5.1/4.5.2  
(2977766)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012 (installazione Server Core)  
(2988948)  
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
Microsoft .NET Framework 3.5  
(2972213)  
(Importante)  
Microsoft .NET Framework 3.5  
(2973114)  
(Importante)  
Microsoft .NET Framework 4.5.1/4.5.2  
(2977765)  
(Importante)

</td>
<td style="border:1px solid black;">
Windows Server 2012 R2 (installazione Server Core)  
(2988948)  
(Importante)

</td>
</tr>
</table>
 
 

**Software e piattaforme delle comunicazioni Microsoft**

 
<table style="border:1px solid black;">
<tr>
<th colspan="2">
**Microsoft Lync Server**

</th>
</tr>
<tr>
<td style="border:1px solid black;">
**Identificatore del bollettino**

</td>
<td style="border:1px solid black;">
[**MS14-055**](http://go.microsoft.com/fwlink/?linkid=507669)

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
<tr>
<td style="border:1px solid black;">
Microsoft Lync Server 2010

</td>
<td style="border:1px solid black;">
Microsoft Lync Server 2010  
(Server)  
(2982385)  
(Nessun livello di gravità) <sup>[1]</sup>
Microsoft Lync Server 2010  
(Response Group Service)  
(2982388)  
(Importante)

</td>
</tr>
<tr>
<td style="border:1px solid black;">
Microsoft Lync Server 2013

</td>
<td style="border:1px solid black;">
Microsoft Lync Server 2013  
(Server)  
(2986072)  
(Importante)  
Microsoft Lync Server 2013  
(Response Group Service)  
(2982389)  
(Importante)  
Microsoft Lync Server 2013  
(Componenti di base)  
(2992965)  
(Importante)  
Microsoft Lync Server 2013  
(Web Components Server)  
(2982390)  
(Importante)

</td>
</tr>
</table>
 
**Nota per MS14-055**

\[ 1\]I livelli di gravità non si applicano a questo aggiornamento per il software specificato; tuttavia, come misura di difesa in profondità, Microsoft consiglia ai clienti del software di applicare questo aggiornamento per la protezione per aumentare la protezione contro possibili nuovi vettori di attacco identificati in futuro.

 

Strumenti e informazioni sul rilevamento e sulla distribuzione
--------------------------------------------------------------

<span id="sectionToggle3"></span>
Sono disponibili diverse risorse per aiutare gli amministratori a distribuire gli aggiornamenti per la protezione.

Microsoft Baseline Security Analyzer (MBSA) consente di eseguire la scansione di sistemi locali e remoti, al fine di rilevare eventuali aggiornamenti di protezione mancanti, nonché i più comuni errori di configurazione della protezione.

Windows Server Update Services (WSUS), Systems Management Server (SMS) e System Center Configuration Manager (SCCM) aiutano gli amministratori a distribuire gli aggiornamenti per la protezione.

I componenti del programma Update Compatibility Evaluator compresi nell'Application Compatibility Toolkit sono utili per semplificare la verifica e la convalida degli aggiornamenti di Windows per le applicazioni installate.

Per informazioni su questi e altri strumenti disponibili, vedere [Strumenti per la sicurezza](http://technet.microsoft.com/security/cc297183). 

Ringraziamenti
--------------

<span id="sectionToggle4"></span>
Microsoft [ringrazia](http://go.microsoft.com/fwlink/?linkid=21127) i seguenti utenti per aver collaborato alla protezione dei sistemi dei clienti:

**MS14-052**

-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-2799)
-   [Adlab di Venustech](http://www.venustech.com.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-2799)
-   [Adlab di Venustech](http://www.venustech.com.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4059)
-   AbdulAziz Hariri di [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4065)
-   56e7aec02099b976120abfda31254b05, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4079)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4080)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4081)
-   [Adlab di Venustech](http://www.venustech.com.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4081)
-   Yuki Chen di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4082)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4082)
-   [Adlab di Venustech](http://www.venustech.com.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4083)
-   [Adlab di Venustech](http://www.venustech.com.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4084)
-   [KnownSec Team](http://www.knownsec.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4084)
-   Sky, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4085)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4086)
-   Liu Long di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4086)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4087)
-   Zhibin Hu di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4087)
-   Hui Gao di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4088)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4089)
-   Garage4Hackers, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4090)
-   Yuki Chen di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4091)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4092)
-   A3F2160DCA1BDE70DA1D99ED267D5DC1EC336192, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4092)
-   Jason Kratzer, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4092)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4093)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4094)
-   Yuki Chen di [Trend Micro](http://www.trendmicro.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4095)
-   cloudfuzzer, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4096)
-   AbdulAziz Hariri di [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4096)
-   Yuki Chen di [Trend Micro](http://www.trendmicro.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4096)
-   Yuki Chen di [Trend Micro](http://www.trendmicro.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4097)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4097)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4098)
-   SkyLined, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4099)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4100)
-   Xin Ouyang di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4101)
-   José A. Vázquez di Yenteasy, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4101)
-   Liu Long di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4102)
-   AbdulAziz Hariri di [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4103)
-   Liu Long di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4104)
-   Yuki Chen di [Trend Micro](http://www.trendmicro.com), che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4105)
-   Bo Qu di [Palo Alto Networks](http://www.paloaltonetworks.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4106)
-   AbdulAziz Hariri di [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4107)
-   Un ricercatore anonimo, che collabora con [Zero Day Initiative](http://www.zerodayinitiative.com/) di [HP](http://www.hpenterprisesecurity.com/products), per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4108)
-   John Villamil (@day6reak) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4109)
-   [KnownSec Team](http://www.knownsec.com/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4110)
-   Yujie Wen di [Qihoo 360](http://www.360.cn/) per aver segnalato la vulnerabilità legata al danneggiamento della memoria in Internet Explorer (CVE-2014-4111)
-   Masato Kinugawa e [Google Security Team](https://www.google.it/) per aver collaborato con noi alle modifiche al sistema di difesa in profondità contenute in questo bollettino

**MS14-053**

-   Alexander Klink di [Cynops GmbH](http://www.cynops.de/) per aver segnalato la vulnerabilità ad attacchi di tipo Denial of Service in .NET Framework (CVE-2014-4072)

**MS14-054**

-   James Forshaw di [Context Information Security](http://www.contextis.com/) per aver segnalato la vulnerabilità legata all'Utilità di pianificazione (CVE-2014-4074)

**MS14-055**

-   Peter Schraffl di [Telecommunication Software GmbH](http://www.telecomsoftware.com/) per aver segnalato la vulnerabilità ad attacchi di tipo Denial of Service in Lync (CVE-2014-4068)
-   Noam Rathaus, che collabora con il team [SecuriTeam Secure Disclosure](http://www.beyondsecurity.com/ssd.html) di Beyond Security, per aver segnalato la vulnerabilità legata all'intercettazione di informazioni personali in Lync XSS (CVE-2014-4070)

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

-   V1.0 (9 settembre 2014): Pubblicazione del riepilogo dei bollettini.

*Pagina generata 18-09-2014 16:20Z-07:00.*
